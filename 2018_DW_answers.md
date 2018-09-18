# By.筑梦师Winston

## 1、NSCache类当中是如何解决NSDictionary时间复杂度问题的.请说明其原理.

### 推荐文章
- iOS开发之哈希表、时间复杂度、链表
https://www.jianshu.com/p/88dfc8f405ab
- swift探究 NSCache https://www.jianshu.com/p/9c45328b4c7c
- 聊聊NSCache
https://www.jianshu.com/p/e850f8d120b0
- 苹果文档 https://developer.apple.com/documentation/foundation/nscache
- Swift 苹果开源NSCache https://github.com/apple/swift-corelibs-foundation/blob/master/Foundation/NSCache.swift
- 被忽视和误解的NSCache
https://www.jianshu.com/p/e456b7b9f52d
- 时间复杂度和空间复杂度的故事 https://www.cnblogs.com/mafeng/p/6831731.html
- NSCache源码分析 https://github.com/nixzhu/dev-blog/blob/master/2015-12-09-nscache.md

### 答案

- NSCache是一个类似NSDictionary一个可变的集合。
提供了可设置缓存的数目与内存大小限制的方式。
保证了处理的数据的线程安全性。
缓存使用的key不需要是实现NSCopying的类。
当内存警告时内部自动清理部分缓存数据。

- NSCache在实现缓存功能时比可变字典更方便，最重要的是它是线程安全的，而NSMutableDictionary不是线程安全的，在多线程环境下使用NSCache是更好的选择。

- 在查看Swift开源的NSCache实现后,我们发现NSCache内部会处理缓存问题,不需要我们手动管理,内部实现是NSCacheEntry 就是对“键值对”的封装,所有的 entry 会组成一个链表，以 cost 排序（但这要建立在每个 entry 的 cost 不相同的前提下）

- 一般来说在开发中有两种形式,一是通过占用更多的空间而提升运行效率也就是牺牲空间换取更低的时间复杂度

- 使用NSCache是为了以空间换时间（占用访问速度更快的内存，节省IO时间），自然是期望其带来性能提升，这就要求用“键”访问缓存得到“值”的速度非常快。不过受限于系统资源，NSCache 会自动管理缓存里的内容（通常是移除一些键值），这就和字典不一样了。
***

## 应用启动时是用怎样加载所有依赖的Mach-O文件的?

### 推荐文章

- Mach-O系列文章
	- https://mp.weixin.qq.com/s/I60p2M-IHDmeUanDUkFdVw
	- https://mp.weixin.qq.com/s/fdDPyjRkVf9AdWiikBagHg
	- https://www.jianshu.com/p/54d842db3f69
	- https://www.jianshu.com/p/8498cec10a41
- iOS开发-APP启动main()调用之前的加载过程
https://www.jianshu.com/p/c603a1e69126
- 深入理解iOS App的启动过程
https://blog.csdn.net/Hello_Hwc/article/details/78317863?locationNum=9&fps=1
- 腾讯bugly App优化
	- https://mp.weixin.qq.com/s/Kf3EbDIUuf0aWVT-UCEmbA
- 今日头条iOS端启动速度优化
	- https://techblog.toutiao.com/2017/01/17/iosspeed/
- 程序启动原理
	- https://www.jianshu.com/p/e29177a8bed1

### 答案

- 什么是Mach-O
	- 首先是我们的代码经过Xcode编译、链接、签名为.app文件
	- 再通过zip压缩为.ipa包
	- 我们的代码最终会成为.app文件中的iOS可执行文件，文件格式是Mach-O
- 应用启动的过程
	- 应用启动的过程可以分为两种，main函数之前和main函数以后做了什么
	- dyld加载流程（main函数之前）
		- 设置上下文信息，配置进程是否受限
		- 配置环境变量，获取当前运行架构
		- 加载可执行文件，生成一个ImageLoader对象
		- 检查共享缓存是否映射到了共享区域
		- 加载所有插入的库 （import library）
		- 链接主程序
		- 链接所有插入的库，执行符号替换
		- 编译、签名、替换原来生成的insertDylib.dylib，设置环境变量，运行App
		- 执行初始化方法 +load  constructor
		- 寻找主程序入口 =>main函数
	- main函数以后
		- 先执行main函数，main内部会调用UIApplicationMain函数,
		- 1)、根据传入的第三个参数创建UIApplication对象或它的子类对象。如果该参数为nil,直接使用该UIApplication来创建。(该参数只能传人UIApplication或者是它的子类)
		(2)、根据传入的第四个参数创建AppDelegate对象,并将该对象赋值给第1步创建的UIApplication对象的delegate属性。
		(3)、开启一个事件循环,循环监控应用程序发生的事件。每监听到对应的系统事件时，就会通知AppDelegate。
		- 有两种情况
			- 有Storyboard
				- 应用程创建一个UIWindow对象(继承自UIView),并设置为AppDelegate的window属性。
				加载Info.plist文件，读取最主要storyboard文件的名称。
				加载最主要的storyboard文件，创建白色箭头所指的控制器对象。并且设置控制器为UIWindow的rootViewController属性(根控制器)。
				展示UIWindow,展示之前会将添加rootViewController的view到UIWindow上面(在这一步才会创建控制器的view),其内部会执行该行代码:[window addSubview: window.rootViewControler.view];
			- 无Storyboard
				- 首先会调用delegate对象的application:didFinishLaunchingWithOptions:方法。
				在application:didFinishLaunchingWithOptions:方法中需要主动创建 UIWindow对象。并设置为AppDelegate的window属性。
				主动创建一个 UIViewController对象，并赋值给window的rootViewController属性。
				调用 window的makeKeyAndVisible方法显示窗口。

*** 

## 什么是冷启动,什么是热启动?

### 推荐文章
- 腾讯Bugly App优化 https://mp.weixin.qq.com/s/Kf3EbDIUuf0aWVT-UCEmbA

### 答案

- 冷启动与热启动
	- 当用户按下home键的时候，iOS的App并不会马上被kill掉，还会继续存活若干时间。理想情况下，用户点击App的图标再次回来的时候，App几乎不需要做什么，就可以还原到退出前的状态，继续为用户服务。这种持续存活的情况下启动App，我们称为热启动，
	- 相对而言冷启动就是App被kill掉以后一切从头开始启动的过程。
- 如何测量启动过程耗时
	- 在Xcode的菜单中选择Project→Scheme→Edit Scheme...，然后找到 Run → Environment Variables →+，添加name为DYLD_PRINT_STATISTICSvalue为1的环境变量。 
***
## 有没有做过项目的优化,请列举你所知道main()函数之前耗时的因素都有哪些,点击应用响应时间多少ms之内不会让用户察觉到？

### 推荐文章
- 腾讯bugly优化
	- https://mp.weixin.qq.com/s/Kf3EbDIUuf0aWVT-UCEmbA
- 今日头条iOS端优化
	- https://techblog.toutiao.com/2017/01/17/iosspeed/

### 答案

- 400ms之内
	- 400ms内完成main()函数前的加载的建议值是怎样定出来的呢？其实我也没有太深究过这个问题，但是，当用户点击了一个App的图标时，iOS做动画到闪屏图出现的时长正好是这个数字，我想也许跟这个有关。
- main()函数之前耗时的影响因素
	- 动态库加载越多，启动越慢。
	- ObjC类越多，启动越慢
	- C的constructor函数越多，启动越慢
	- C++静态对象越多，启动越慢
	- ObjC的+load越多，启动越慢
- main()函数之后耗时的影响因素
	- 执行main()函数的耗时
	- 执行applicationWillFinishLaunching的耗时
	- rootViewController及其childViewController的加载、view及其subviews的加载

***