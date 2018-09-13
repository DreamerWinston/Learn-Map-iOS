# 2017年iOS开发面试题

本面试题均为网上搜集,面试题答案均为本人搜集整理.

不想看答案的可以先根据题目自测一下.

暂时以答案以及外链的形式展示给大家,有什么建议可以私信我.

## 题目列表
1. dSYM你是如何分析的?
2. 多线程有哪几种你更倾向于哪一种?
3. 单例弊端?
4. 如何把异步线程转换成同步任务进行单元测试?
5. 介绍下App启动的完成过程?
6. 比如App启动过慢，你可能想到的因素有哪些?
7. 0x8badf00d表示是什么?
8. 怎么防止反编译?
9. 说说你遇到到的技术难点?
1. 说说你了解的第三方原理或底层知识?
2. 怎么判断某个 cell 是否显示在屏幕上?
3. 进程和线程的区别?
4. TCP 与 UDP 区别?
5. TCP 流量控制?
6. 数组和链表的区别?
7. UIView 生命周期?
8. 如果页面 A 跳转到 页面 B，A 的 viewDidDisappear 方法和 B 的 viewDidAppear 方法哪个先调用?
9. block 循环引用问题?
1. ARC 的本质?
2. RunLoop 的基本概念，它是怎么休眠的?
3. Autoreleasepool 什么时候释放，在什么场景下使用?
4. 如何找到字符串中第一个不重复的字符?
5. 哈希表如何处理冲突?
6. MVC具有什么样的优势，各个模块之间怎么通信，比如点击 Button 后 怎么通知 Model?
7. 两个无限长度链表（也就是可能有环） 判断有没有交点?
8. UITableView的相关优化?
9. KVO、Notification、delegate各自的优缺点，效率还有使用场景?
1. 如何手动通知KVO?
2. Objective-C 中的copy方法?
3. runtime 中，SEL和IMP的区别?
4. autoreleasepool的使用场景和原理?
5. RunLoop的实现原理和数据结构，什么时候会用到?
6. block为什么会有循环引用?
7. 有没有自己设计过网络控件?
8. CoreData的使用，如何处理多线程问题?
9. 如何设计图片缓存?
1. 有没有自己设计过网络控件?
2. NSOperation和GCD的区别介绍下内存的几大区域?
3. 你是如何组件化解耦的?
4. runtime如何通过selector找到对应的IMP地址?
5. runloop内部实现逻辑?
6. 你理解的多线程?
7. GCD执行原理?
8. 怎么防止别人反编译你的app?
9. YYAsyncLayer如何异步绘制?
1. 优化你是从哪几方面着手?
2. 简单说一下APP的启动过程，从main文件开始说起?
3. 内存分区情况?
4. 你是否接触过OC的反射机制,简单聊一下概念和使用?
5. 队列和栈?
6. import与include 与@class?
7. Pt与px的区别?
8. imageName和imageWithContextOfFile的区别?
9. didReceiveMemoryWarning?
1. \#define的语法 以及标准宏?
2. const与static的作用和区别 auto变量?
3. atomic和non-atomic的区别?
4. load与initialize的区别?
5. Weak strong copy assign的区别?
6. SEL isa super cmd是什么?
7. Malloc和New的区别?
8. 懒加载(What  is  lazy  loading  ?)?
9. selector和method 有什么不同?
1. C语言相关Sprintf,strcpy,memcpy如何使用及区别?
2. 代理和通知的区别?
3. 什么是SEL 如何声明一个SEL,通过哪些方法能够,调用SEL包装起来的方法?
4. UDID与UUID的区别?
5. CPU与GPU?
6. CFSocket CFNetwork BSD Socket?
7. 编译连接 id 与instancetype的区别?
8. app内存你是如何分析的?
9. @synthesize 与 @dynamic区别?
1. Swift与Objective-C的区别?
2. NSProxy与NSObject区别?
3. hybrid开发?
4. 你会如何存储用户的一些敏感信息，如登录的token?
5. Block在内存中的位置?
6. iOS app为什么内存没有泄露，内存却降不下来?
7. 单例会有什么弊端?
8. 什么时候会使用Core Graphics，以及使用步骤?
9. 如何实现夜间模式?
1. 离屏渲染及其优化方式?

## 答案以及推荐链接

### dSYM你是如何分析的？
答案:
推荐链接:

### 多线程有哪几种你更倾向于哪一种？
答案:
推荐链接:

### 单例弊端？
答案:
推荐链接:

### 如何把异步线程转换成同步任务进行单元测试？
答案:
推荐链接:

### 介绍下App启动的完成过程？
答案:
推荐链接:

### 比如App启动过慢，你可能想到的因素有哪些？
答案:
推荐链接:

### 0x8badf00d表示是什么？
答案:
推荐链接:

### 怎么防止反编译？
答案:
推荐链接:

### 说说你遇到到的技术难点？
答案:
推荐链接:

### 说说你了解的第三方原理或底层知识？
答案:
推荐链接:

### 怎么判断某个 cell 是否显示在屏幕上？
答案:
推荐链接:

### 进程和线程的区别？
答案:
推荐链接:

### TCP 与 UDP 区别？
答案:
推荐链接:

### TCP 流量控制？
答案:
推荐链接:

### 数组和链表的区别？
答案:
推荐链接:

### UIView 生命周期？
答案:
推荐链接:

### 如果页面 A 跳转到 页面 B，A 的 viewDidDisappear 方法和 B 的 viewDidAppear 方法哪个先调用？
答案:
推荐链接:

### block 循环引用问题？
答案:
推荐链接:

### ARC 的本质？
答案:
推荐链接:

### RunLoop 的基本概念，它是怎么休眠的？
答案:
推荐链接:

### Autoreleasepool 什么时候释放，在什么场景下使用？
答案:
推荐链接:

### 如何找到字符串中第一个不重复的字符？
答案:
推荐链接:

### 哈希表如何处理冲突？
答案:
推荐链接:

### MVC具有什么样的优势，各个模块之间怎么通信，比如点击 Button 后 怎么通知 Model？
答案:
推荐链接:

### 两个无限长度链表（也就是可能有环） 判断有没有交点？
答案:
推荐链接:

### UITableView的相关优化？
答案:
推荐链接:

### KVO、Notification、delegate各自的优缺点，效率还有使用场景？
答案:
推荐链接:

### 如何手动通知KVO？
答案:
推荐链接:

### Objective-C 中的copy方法？
答案:
推荐链接:

### runtime 中，SEL和IMP的区别？
答案:
推荐链接:

### autoreleasepool的使用场景和原理？
答案:
推荐链接:

### RunLoop的实现原理和数据结构，什么时候会用到？
答案:
推荐链接:

### block为什么会有循环引用？
答案:
推荐链接:

### 有没有自己设计过网络控件？
答案:
推荐链接:

### CoreData的使用，如何处理多线程问题？
答案:
推荐链接:

### 如何设计图片缓存？
答案:
推荐链接:

### 有没有自己设计过网络控件？
答案:
推荐链接:

### NSOperation和GCD的区别介绍下内存的几大区域？
答案:
推荐链接:

### 你是如何组件化解耦的？
答案:
推荐链接:

### runtime如何通过selector找到对应的IMP地址？
答案:
推荐链接:

### runloop内部实现逻辑？
答案:
推荐链接:

### 你理解的多线程？
答案:
推荐链接:

### GCD执行原理？
答案:
推荐链接:

### 怎么防止别人反编译你的app？
答案:
推荐链接:

### YYAsyncLayer如何异步绘制？
答案:
推荐链接:

### 优化你是从哪几方面着手？
答案:
推荐链接:

### 简单说一下APP的启动过程，从main文件开始说起？
答案:
推荐链接:

### 内存分区情况？
答案:
推荐链接:

### 你是否接触过OC的反射机制,简单聊一下概念和使用？
答案:
推荐链接:

### 队列和栈？
答案:
推荐链接:

### import与include 与@class？
答案:
推荐链接:

### Pt与px的区别？
答案:
推荐链接:

### imageName和imageWithContextOfFile的区别？
答案:
推荐链接:

### didReceiveMemoryWarning？
答案:
推荐链接:

### \#define的语法 以及标准宏？
答案:
推荐链接:

### const与static的作用和区别 auto变量？
答案:
推荐链接:

### atomic和non-atomic的区别？
答案:
推荐链接:

### load与initialize的区别？
答案:
推荐链接:

### Weak strong copy assign的区别？
答案:
推荐链接:

### SEL isa super cmd是什么？
答案:
推荐链接:

### Malloc和New的区别？
答案:
推荐链接:

### 懒加载(What  is  lazy  loading  ?)？
答案:
推荐链接:

### selector和method 有什么不同？
答案:
推荐链接:

### C语言相关Sprintf,strcpy,memcpy如何使用及区别？
答案:
推荐链接:

### 代理和通知的区别？
答案:
推荐链接:

### 什么是SEL 如何声明一个SEL,通过哪些方法能够,调用SEL包装起来的方法？
答案:
推荐链接:

### UDID与UUID的区别？
答案:
推荐链接:

### CPU与GPU？
答案:
推荐链接:

### CFSocket CFNetwork BSD Socket？
答案:
推荐链接:

### 编译连接 id 与instancetype的区别？
答案:
推荐链接:

### app内存你是如何分析的？
答案:
推荐链接:

### @synthesize 与 @dynamic区别？
答案:
推荐链接:

### Swift与Objective-C的区别？
答案:
推荐链接:

### NSProxy与NSObject区别？
答案:
推荐链接:

### hybrid开发？
答案:
推荐链接:

### 你会如何存储用户的一些敏感信息，如登录的token？
答案:
推荐链接:

### Block在内存中的位置？
答案:
推荐链接:

### iOS app为什么内存没有泄露，内存却降不下来？
答案:
推荐链接:

### 单例会有什么弊端？
答案:
推荐链接:

### 什么时候会使用Core Graphics，以及使用步骤？
答案:
推荐链接:

### 如何实现夜间模式？
答案:
推荐链接:

### 离屏渲染及其优化方式？
答案:
推荐链接:


