## Algorithm

参加双周赛的一个题目：[5295. 和为零的N个唯一整数](https://leetcode-cn.com/problems/find-n-unique-integers-sum-up-to-zero/)

```kotlin
class Solution {
    fun sumZero(n: Int): IntArray {
        var values = mutableListOf<Int>()
        if (n == 1) return intArrayOf(0)
        return if (n % 2 == 0) {
            for (i in 1..n / 2) {
                values.add(i)
                values.add(-1 * i)
            }
            return values.toIntArray()
        } else {
            for (i in 1 until n / 2) {
                values.add(i)
                values.add(-1 * i)
            }
            values.add(2 * n + 1)
            values.add(n * -1)
            values.add(n * -1 - 1)
            return values.toIntArray()
        }
    }
}
```
暴力解法 😁

## Review

[8 Steps to a Successful User Group](https://blog.jetbrains.com/blog/2019/08/15/8-steps-to-a-successful-user-group/)

介绍了一个建立成功用户组织的 8 步工作法：
* 找到合伙人（合作一起分担工作）
* 找到赞助人（提供场地、礼物之类的）
* 找到场地
* 邀请演讲人
* 恪守计划
* 让用户组活动常规化
* 和活动参加人员聊天
* 给用户组活动准备一些小礼品：T恤、贴纸之类的


## Tips
[Dagger 依赖关系可视化](https://arunkumar.dev/introducing-scabbard-a-tool-to-visualize-dagger-2-dependency-graphs/)

最近在推上看到一个刚发布的可视化的工具 0.1.0 版本， 看起来非常不错大家可以看看。纯 kotlin 编写的，超级棒。

## Share

本周公司分配了一个党建后台 APP 的产品开发任务，看来过年前是要忙一阵子了。

这周尝试用 Kotlin-MPP 来搭建一个基础的跨平台 App 骨架，参考了官方的 KontlinConf 2019 APP。

SharedCode 用了 Ktor + MPP, Android 用 Kotlin+Jetpack, iOS 用 SwiftUI. 坑挖的有点大，网络层的封装不大好，IDE 支持还不是很好，经常出现无法理解的报错。看了 KotlinConf 2019 里面 MPP 相关的视频，发现还是和官方说的一样，还是处于试验阶段，产品暂时就还是先用 纯原生的开发吧。

Android 用 Jetpack Navigation 组件搞了一点，设计师搞得效果图用了不少 Material 的元素，准备直接用 MDC 控件来干了。下周继续。