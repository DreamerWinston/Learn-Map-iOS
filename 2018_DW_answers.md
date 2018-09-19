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

## 属性 可以与set方法和get方法 三者同时存在吗,如果不行,请说明原因?

### 推荐文章
- 苹果官方文档对于@synthesize的定义
	- https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/ObjectiveC/Chapters/ocProperties.html
	- https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/ObjectiveC/Chapters/ocDefiningClasses.html
- iOS开发中@synthesize obj=obj的意义详解
  - https://www.jianshu.com/p/6d80cacab384

### 答案
- set方法和get方法为什么不能同时重写
	- 会报错，同时重写，就与@property声明的成员属性不一致，导致@synthesize无法生效
- @synthesize的意义
	- 在Xcode4.4版本之前@property和@synthesize的功能是独立分工的：
	    @property的作用是：自动的生成成员变量set/get方法的声明如代码：
	        @property int age; 它的作用和下面两行代码的作用一致
	        - (void)setAge:(int)age;
	        - (int)age;
	    注意：属性名称不要加前缀_ 否则生成的get/set方法中也会有下划线
	-  @synthesize的作用是实现@property定义的方法代码如：
	        @synthesize age
	        将@property中定义的属性自动生成get/set的实现方法而且默认访问成员变量age
	  
	-  如果指定访问成员变量_age的话代码如：@synthesize age = _age；意思是：把@property中声明的age成员变量生成get/set实现方法，并且在实现方法内部，访问_age这个成员变量，也就意味着给成员 _age 赋值
	
	- 注意：访问成员变量 _age 如果在.h文件中没有定义_age成员变量的话，就会在.m文件中自动生成@private类型的成员变量_age
	
***
## Runtime机制是什么?有没有写过方法欺骗?简述一下?

### 推荐文章
- iOS开发之Runtime
 - https://www.jianshu.com/p/d32b96720937
### 答案
- 什么是Runtime？
	- Objective-C的动态性是由Runtime API来支撑的
	- Runtime API提供的接口基本都是C语言的，源码由C\C++\汇编语言编写
- 什么是消息机制
	- OC中的方法调用，其实都是转换为objc_msgSend函数的调用
	- 也就是消息机制
	- 消息机制分为三部分：消息发送、动态方法解析、消息转发
- 方法欺骗method swizzling
	- class_replaceMethod
	- method_exchangeImplementations
***
## GCD和NSOperation的区别之处,请分别说一下特点?

### 推荐文章

### 答案
- 多线程方案都有哪些
	- pthread
	- NSThread
	- GCD
	- NSOperation
- GCD和NSOperation的优劣之处
	- GCD 充分利用设备的多核 充分利用设备的多核 C语言
	- NSOperation 基于GCD（底层是GCD）比GCD多了一些更简单实用的功能 更加面向对象 基于OC
***
## Reachability是用来判断网络状态的,请简述一下其原理?

### 推荐文章
- https://developer.apple.com/documentation/systemconfiguration/scnetwork
- https://developer.apple.com/documentation/systemconfiguration/scnetworkconnection-g7e

### 答案
- Reachability并不能检测到服务器是否真的可达，只能检测设备是否连接到局域网，以及用的WiFi还是WWAN。即：把设备网络关了，立马检测出NotReachable，连接到路由器立马检测出是ReachableViaWiFi
- 导入<SystemConfiguration/SystemConfiguration.h>
- SCNetwork 
通过SCNetworkReachabilityFlags 来区别网络变更
- NotReachable
- WWAN
- WiFi
- Unknown

***
## LayoutSubviews这个方法一般在什么情况下调用的?

### 推荐文章
- https://www.jianshu.com/p/d1ce00f08b7f
- https://www.jianshu.com/p/2ef48c2f0c97

### 答案

1. init方法不会调用 
2. addSubview方法等时候会调用 
3. bounds改变的时候调用 
4. scrollView滚动的时候会调用scrollView的layoutSubviews方法(所以不建议在scrollView的layoutSubviews方法中做复杂逻辑) 
5. 旋转设备的时候调用 
6. 子视图被移除的时候调用 

***
