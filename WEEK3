### Algorithm

```kotlin
class Solution {    fun groupThePeople(groupSizes: IntArray): List> {        var groups = mutableListOf>()        var n = groupSizes.size        var index = 0        for (size in groupSizes) {            if (size >= 0) {                val list = mutableListOf()                for (i in IntRange(index, n - 1)) {                    if (groupSizes[i] == size && list.size < size) {                        list.add(i)                        groupSizes[i] = -1                    }                }                groups.add(list)            }        }        return groups    }}
```

### Review

[https://www.vlang.io/#faq](https://www.vlang.io/#faq)

FAQ 很清楚的介绍了 V 的特性和未来开发计划。

1.  无 GC 类似 Rust
    
2.  编译速度很快，自举实现的版本编译完成只需要
    
3.  简单的并行（Concurrency）编程，类似 GO 的 routine
    

### Tips

[https://termux.com/](https://termux.com/)

Termux is an **Android terminal emulator and Linux environment app** that works directly with no rooting or setup required. A minimal base system is installed automatically - additional packages are available using the APT package manager.

### Share

这周整了很长一段时间 OpenCV ， 准备做一个人脸认证的 SDK。

跨平台编译 Android 和 iOS 的 SDK 比想象中的麻烦。虽然官方发布有标准版的 SDK 预编译版本，但是我需要使用的 MACE 模块在 opencv\_contrib 库中，需要自己单独编。查了下官方的文档，发现都是好几年前的老板本的，网上的博客也都是寥寥几句，在自己的 Linux 虚拟机和 macOS 上编译本平台是没问题，跨平台编译 Android 的怎么也不行，不是 Python 版本就是 C++ 的 TEST 不通过，最后在 https://github.com/opencv/opencv/issues/11693#issuecomment-394662592 现任维护者的问题评论中找到正确的编译方法。

C++ 领域知识还是比较匮乏，希望今年结束前能通过 这个 SDK 来入下门。
