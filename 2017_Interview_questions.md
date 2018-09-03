# 2017年iOS开发面试题

- 阿里面试题
	- dSYM你是如何分析的？
	- 2.多线程有哪几种？你更倾向于哪一种？
	- 3.单例弊端？
	- 4.如何把异步线程转换成同步任务进行单元测试？
	- 5.介绍下App启动的完成过程？
	- 6.比如App启动过慢，你可能想到的因素有哪些？
	- 7.0x8badf00d表示是什么？
	- 8.怎么防止反编译？
	- 9.说说你遇到到的技术难点？
	- 10.说说你了解的第三方原理或底层知识？
	- 1.怎么判断某个 cell 是否显示在屏幕上
	-     2.    进程和线程的区别
	-     3.    TCP 与 UDP 区别
	-     4.    TCP 流量控制
	-     5.    数组和链表的区别
	-     6.    UIView 生命周期
	-     7.    如果页面 A 跳转到 页面 B，A 的 viewDidDisappear 方法和 B 的 viewDidAppear 方法哪个先调用？
	-     8.    block 循环引用问题
	-     9.    ARC 的本质
	-    10.    RunLoop 的基本概念，它是怎么休眠的？
	-    11.    Autoreleasepool 什么时候释放，在什么场景下使用？
	-    12.    如何找到字符串中第一个不重复的字符
	-    13.    哈希表如何处理冲突
	- MVC具有什么样的优势，各个模块之间怎么通信，比如点击 Button 后 怎么通知 Model？
	- 2.两个无限长度链表（也就是可能有环） 判断有没有交点
	- 3.UITableView的相关优化
	- 4.KVO、Notification、delegate各自的优缺点，效率还有使用场景
	- 5.如何手动通知KVO
	- 6.Objective-C 中的copy方法
	- 7.runtime 中，SEL和IMP的区别
	- 8.autoreleasepool的使用场景和原理
	- 9.RunLoop的实现原理和数据结构，什么时候会用到
	- 10.block为什么会有循环引用
	- 11.有没有自己设计过网络控件？ 
	- 12.CoreData的使用，如何处理多线程问题
	- 13.如何设计图片缓存？
	- 14.有没有自己设计过网络控件？
	- 15.NSOperation和GCD的区别 
	- 介绍下内存的几大区域？
	- 2.你是如何组件化解耦的？
	- 3.runtime如何通过selector找到对应的IMP地址
	- 4.runloop内部实现逻辑？
	- 5.你理解的多线程？
	- 6.GCD执行原理？
	- 7.怎么防止别人反编译你的app？
	- 8.YYAsyncLayer如何异步绘制？
	- 9.优化你是从哪几方面着手？

* 简单说一下APP的启动过程，从main文件开始说起
* Swift与Objective-C的区别
- 编译连接 id 与instancetype的区别
* @synthesize 与 @dynamic区别
- NSProxy与NSObject区别
- imageName和imageWithContextOfFile的区别
- UDID与UUID的区别
- CPU与GPU
- Pt与px的区别
- import与include 与@class
- CFSocket CFNetwork BSD Socket
* app内存你是如何分析的？
* Block在内存中的位置
* iOS app为什么内存没有泄露，内存却降不下来
* 内存分区情况
* 队列和栈
- 单例会有什么弊端？
* 什么时候会使用Core Graphics，以及使用步骤？
* 你会如何存储用户的一些敏感信息，如登录的token
- didReceiveMemoryWarning
- 代理和通知的区别

* #define的语法 以及标准宏
* const与static的作用和区别 auto变量
- C语言相关Sprintf,strcpy,memcpy如何使用及区别
* Malloc和New的区别
- 你是否接触过OC的反射机制,简单聊一下概念和使用
- 什么是SEL 如何声明一个SEL,通过哪些方法能够,调用SEL包装起来的方法
- 懒加载(What  is  lazy  loading  ?)
- selector和method 有什么不同
- atomic和non-atomic的区别
- SEL isa super cmd是什么
- load与initialize的区别
- Weak strong copy assign的区别
* hybrid开发
* 如何实现夜间模式？
- 离屏渲染及其优化方式
