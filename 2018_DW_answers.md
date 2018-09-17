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
