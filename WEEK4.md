## Algorithm

https://leetcode-cn.com/problems/find-numbers-with-even-number-of-digits

```swift
class Solution {
    func findNumbers(_ nums: [Int]) -> Int {
        var count: Int = 0
        for i in nums {
            if(String(i).count % 2 == 0) {
                count += 1
            }
        }
        return count
    }
}
```

数字先转为字符串，根据字符串中字符的数字是否为偶数来判断位数是否偶数。

## Review

[IntelliJ Platform Roadmap for 2020
](https://blog.jetbrains.com/idea/2019/12/intellij-platform-roadmap-for-2020/)

这是一篇 JetBrains 公司的博客，讲他们明年（2020 年） IntelliJ 开发平台的路线图。主要是优化性能问题和针对现代的开发流程做一些探索。性能优化方面主要是解决界面卡死和索引慢的问题，通过一系列的重构、重写来达到耗时操作全部异步完成，从根本上解决问题。对协同编程也有一定的开发计划，可能会支持 Master-Slave 编辑器的方式来达到协同编程目的。还有云编程的支持，包括在云上执行和调试功能。

## Tips

Name Well; Rename When Needed. Name to express your intent to readers, and rename as soon as that intent shifts.
From The Pragmatic Programmer, 20th Anniversary Edition.

## Share

这周测试了 OpenCV 的人脸检测和人脸识别算法（MACE），算是失败了，无法用于实际的项目中。本来打算用 OpenCV 来替代之前使用的虹软离线 SDK。他们的 SDK 还没有支持 Android 10， 而且一个 armv7a 的库就要 40M 还多，太占用空间了。

OpenCV + contrib 的库虽然编译完了 armv7a 平台才不到 7M，但是人脸检测的速度和精度默认情况下都没有虹软的 SDK 高，而且 MACE 识别算法在训练完了 11 张相同的人脸后，在后续相同的人脸数据中均给出 false 的识别结果，实在是太让人失望了。

下周打算再从人脸的规格统一和方向取正方面在做些调整，同时尝试静态的提供一些正向训练人脸数据和测试数据，确认 MACE 算法是否可用。
