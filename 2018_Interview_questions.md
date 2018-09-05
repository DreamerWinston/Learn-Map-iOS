# 2018年iOS开发面试题

- 算法题
	- 强连通分量
	- 算法原理：（Tarjan）
- 腾讯面试
	- 一个UIImageView添加到视图上以后,内部是如何渲染到手机上的,请简述其流程
	- 二维码登录的逻辑是如何实现的
- YY面试题
	- 1、property 常用的后面修饰符，你回答的越多越好，但是，他会一个个问用法，然后再问你为啥，有啥特殊情况，怎么处理
	- 2、MLeakFinder 的源码看了没，怎么实现的？你能怎么去用到你的代码中？
	- 3、OC、JS 交互，具体的实现方式，JS 中的一个按钮点击后，webView都进行了哪些操作？从这个按钮中你能获取到哪些信息，能够做哪些处理？
	- 4、UILabel、UIButton、UITableView 跟 NSObject 啥关系？具体讲讲
	- 5、A 里有B、C 两个view，B中有两个按钮E、F，当我点击F按钮，编译器进行了哪些操作？
	- 6、AOP解释下，可以用到哪些地方，有啥优缺点？

- By. 面试之道
	- Swift
		* 类和结构体有什么区别
		- Swift是面向对象还是函数式的编程语言
		- 在swift中,什么是可选型
		- 在swift中,什么是泛型
		- 说明并比较关键词:Open,Public,Internal,File-private,Private
		- Strong,Weak,Unowned的区别
		- 在Swift中,如何理解copy-on-write
		- 什么是属性观察(Property Observer)
		- 在结构体中如何修改成员变量的方法
		- 如何用Siwft实现或 || 操作
		- 实现一个函数:输入是任意一个整数,输出为输入的整数+2
		- Swift为什么将String,Array和Dictionary设计成值类型
		- 如何用Swift将协议(protocol) 中的部分方法设计成可选(optional)
		- 协议的代码实践
		- Swift和Objective-C如何混编,方法如何调用
		- 初始化方法有什么异同
		- 协议有什么异同
		- 谈谈OC与Swift动态特性的理解
		- 语言特性代码实战
		- Swift和Objective-C的自省有什么不同
		- 比较关键词:Serial Concurrent Sync 和Async
	- Objective-C
		- 什么是ARC
		- 什么情况下会出现循环引用
		- 说明并比较关键词:Strong ,Weak ,Assign和Copy
		- 说明并比较关键词:Atomatic 和nonatomic
		- Atomic是百分之百线程安全的吗
		- 说明并比较关键词: __ weak 和__ block
		- 什么是block? 他和代理的区别是什么
		- 属性声明代码风格考察
		- 架构解耦代码考察
		- 内存管理语法考察
		- 多线程语法考察
		- 以scheduledTimerWithTimeInterval 的方式触发的timer,在滑动页面上的列表时timer会暂停,为什么?该如何解决
		- message send 如果找不到对象,后续会如何处理
		- 什么是method swizzling
		- 能否通过Category给已有的类添加属性
		- LLDB中的p和po有什么区别
		- Buildtime issues 和Runtime issues的区别
	- 架构与设计模式
		- 说说你平常用到的设计模式
		- 什么是MVC
		- Objective-C和Swift在单例模式的设计模式
		- 什么是装饰模式
		- 什么是观察者模式
		- 什么是备忘录模式
		- 比较苹果官方的MVC架构的优点和缺点
		- MVC架构的代码实战
		- MVCS中的S为什么要单独拆分出来
		- MVP和MVC有什么异同
		- MVVM中的ViewModel作用是什么
		- 比较MVC MVP MVVM三种架构
		- VIPER之间的各个组件是如何交互的
		- 什么是OOP? 在iOS开发中有什么优点
		- OOP在iOS开发中有什么缺点
		- POP相比OOP有哪些优势
	- UI控件和基本布局
		- 要在UIView上定义一个Label有几种方式
		- Storyboard/Xib和纯代码构建UI相比 有哪些优点和缺点
		- Auto Layout 和Frame 在UI布局和渲染上有什么区别
		- UIView 和CALayer有什么区别
		* 说明比较关键词:Frame ,Bounds,Center
		- 说明比较方法:layoutifNeeded ,layoutSubviews setNeedsLayout
		- 说明比较关键词:Safe Area ,SafeAreaLayoutGuide,SafeAreaInsets
		- 在iOS中实现动画的方式有几种
		- 控制屏幕上的圆形小球,使其右滑动200个point
		- 在iOS开发中如何保证UI在iPhone\iPad\iPad分屏情况下依然适用
		- 如何使用Drag&drop实现图片拖动功能
		- 说明并比较关键词:contentView \ contentInset \contentSize \contentOffset
		- 说明UITableViewCell 的重用机制
		- 说明并比较协议 UItableviewDataSource 和UItableViewDelegate
		- 实现一个10行的列表,每行随机显示一个0~100的整数,用户可以删除\可以移动任意一行,下拉列表中的数字重新刷新
		- UICollectionView的Supplementary Views和Decoration Views分别代表什么
		- 如果一个列表视图滑动很慢,那么该怎么优化
		- 说说实现预加载的方法
		- 如何用UICollectionView实现瀑布流界面
		- 在iOS开发中,如何实现编码和解码
		- 说一说iOS开发中的数据持久化的方案
		- 要给UIbutton增加点击后抖动的效果,该怎样实现
		- POP的代码实现
		- 试用Swift实现二分搜索算法
	- 测试与发布
		- 一个App崩溃了,可能是什么原因造成的
		- 在模拟机完成所有测试之后,就不需要在真机上再进行测试了吗
		- 为什么在单元测试中引入代码模块要用@testable关键词
		- 单元测试的代码实战
		- 说一说iOS中的性能测试
		- 说一说iOS开发中的UI测试
		- 如何检查测试覆盖率
		- 什么是iOS中的AppID
		- 什么是iOS中的Code Signing
		- 什么是iOS中的App Thinning
		- 向App Store 提交App时有哪些原因可能被拒.
	- 线程
		- 在iOS开发中,对于并发操作有哪种方式
		- 串行队列的代码实战
		- 并行队列的代码实战
		- 举例说明iOS并发编程的三大问题
		- 竞态条件的代码实践
		- 比较GCD的实战:dispatch_async dispatch_after dispatch_once dispatch_group
		- GCD中全局队列有哪种优先级
		- 试比较Operations 中的关键词:Operation BlockOperation OperationQueue
		- 如何在OperationQueue中取消某个Operation
		- 在实际开发中,主线程和其他线程有什么使用场景
	- 网络层
		* 说一说HTTP中的GET与POST的区别
		- 说一说Seesion和Cookie的概念
		- 说明网络协议Ajax Poling 、Long Polling 、WebSockets和Server-Sent Event
		- 在一个HTTPS连接的网络中,输入账号和密码并单击登录按钮后,到服务器返回这个请求,这期间经历了什么
		- 说明并比较类:URLSessionTask URLSessionDataTask URLSessionUploadTask URLSeesionDownloadTask
		- 什么是Complention Handler
		- 设计一个方法,在给定API的网址的条件下,返回用户数据
		- 在iOS开发中,本地消息通知的流程是怎么样的
		- 说一说在iOS开发中,远程消息推送原理
	- 分析与优化
		- 怎样解决EXC_BAD_ACCESS
		* App启动时间过长,应该怎样优化
		* 如何使用Xcode检测代码中的循环引用.


- By. MJ底层原理
	- OC对象本质
		- 一个NSObject对象占用多少内存？
		- 对象的isa指针指向哪里？
		- OC的类信息存放在哪里？
	- KVO & KVC
		- iOS用什么方式实现对一个对象的KVO？(KVO的本质是什么？)
		- 如何手动触发KVO？
		- 直接修改成员变量会触发KVO么？
		- 通过KVC修改属性会触发KVO么？
		- KVC的赋值和取值过程是怎样的？原理是什么？
	- Category
		- Category的使用场合是什么？
		- Category的使用场合是什么？
		- Category和Class Extension的区别是什么？
		- Category中有load方法吗？load方法是什么时候调用的？load 方法能继承吗？
		- load、initialize方法的区别什么？它们在category中的调用的顺序？以及出现继承时他们之间的调用过程？
		- Category能否添加成员变量？如果可以，如何给Category添加成员变量？
	- Block
		- block的原理是怎样的？本质是什么？
		- __block的作用是什么？有什么使用注意点？
		- block的属性修饰词为什么是copy？使用block有哪些使用注意？
		- block的属性修饰词为什么是copy？使用block有哪些使用注意？
	- Runtime
		- 讲一下 OC 的消息机制
		- 消息转发机制流程
		- 什么是Runtime？平时项目中有用过么？p具体应用
	- Runloop
		* 讲讲 RunLoop，项目中有用到吗？
		- runloop内部实现逻辑？
		- runloop和线程的关系？
		- timer 与 runloop 的关系？
		- 程序中添加每3秒响应一次的NSTimer，当拖动tableview时timer可能无法响应要怎么解决？
		- runloop 是怎么响应用户操作的， 具体流程是什么样的？
		- 说说runLoop的几种状态
		- runloop的mode作用是什么？
	- 多线程
		- 你理解的多线程？
		* iOS的多线程方案有哪几种？你更倾向于哪一种？
		- 你在项目中用过 GCD 吗？
		- GCD 的队列类型
		- 说一下 OperationQueue 和 GCD 的区别，以及各自的优势
		- 线程安全的处理手段有哪些？
		- OC你了解的锁有哪些？在你回答基础上进行二次提问；
		* 请问下面代码的打印结果是什么？
		* 请问下面代码的打印结果是什么？
	- 性能优化
		- 你在项目中是怎么优化内存的？
		- 优化你是从哪几方面着手？
		- 列表卡顿的原因可能有哪些？你平时是怎么优化的？
		* 遇到tableView卡顿嘛？会造成卡顿的原因大致有哪些？
	- 架构与设计模式
		- 讲讲 MVC、MVVM、MVP，以及你在项目里具体是怎么写的？
		- 你自己用过哪些设计模式？
		- 一般开始做一个项目，你的架构是如何思考的？

- By. iOS大咖程序员
	* runloop是什么／runloop的概念？
	* NSRunLoop 和 CFRunLoopRef？
	* runloop应用场景？
	* runloop和线程的关系？
	* runloop对外接口／runloop的几个类？
	* Runloop内部逻辑
	* Runtime是什么
	* 为什么需要Runtime
	* Runtime 的作用
	* Runtime的相关术语，你知道的有哪些？
	* Runtime与消息的关系？
	- 如何交换系统的方法？
	- 如何让 Category 支持属性？(使用runtime)
	- Toll-Free Bridging 是什么？什么情况下会使用？
	- performSelector:withObject:afterDelay: 内部大概是怎么实现的，有什么注意事项么？
	- runtime 如何实现 weak 属性？
	- runtime如何通过selector找到对应的IMP地址？（分别考虑类方法和实例方法）
	- 使用runtime Associate方法关联的对象，需要在主对象dealloc的时候释放么？
	- _objc_msgForward函数是做什么的？直接调用它将会发生什么？
	- 能否向编译后得到的类中增加实例变量？能否向运行时创建的类中添加实例变量？为什么？
	- 简述下Objective-C中调用方法的过程（runtime）
	- 什么是method swizzling（俗称黑魔法）
	* 编译过程中都做了哪些事情
	* 字典实现原理
	- 如何访问并修改一个类的私有属性
	* 你使用过Objective-C的运行时编程（Runtime Programming）么？如果使用过，你用它做了什么？你还能记得你所使用的相关的头文件或者某些方法的名称吗？
	* Core开头的系列的内容。是否使用过CoreAnimation和CoreGraphics。UI框架和CA，CG框架的联系是什么？分别用CA和CG做过些什么动画或者图像上的内容。（有需要的话还可以涉及Quartz的一些内容）
	* UIScrollView 大概是如何实现的，它是如何捕捉、响应手势的？
	* 是否使用过CoreText或者CoreImage等？如果使用过，请谈谈你使用CoreText或者CoreImage的体验。
	* 直接调用_objc_msgForward函数将会发生什么？
	* main()之前的过程有哪些？

- 如何交换系统的方法？
- 如何让 Category 支持属性？(使用runtime)
- Toll-Free Bridging 是什么？什么情况下会使用？
- performSelector:withObject:afterDelay: 内部大概是怎么实现的，有什么注意事项么？
- runtime 如何实现 weak 属性？
- runtime如何通过selector找到对应的IMP地址？（分别考虑类方法和实例方法）
- 使用runtime Associate方法关联的对象，需要在主对象dealloc的时候释放么？
- _objc_msgForward函数是做什么的？直接调用它将会发生什么？
- 能否向编译后得到的类中增加实例变量？能否向运行时创建的类中添加实例变量？为什么？
- 简述下Objective-C中调用方法的过程（runtime）
- 什么是method swizzling（俗称黑魔法）
