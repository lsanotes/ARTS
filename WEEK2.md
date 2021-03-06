# ARTS

## WEEK2

### Algorithm

参加了 LeetCode 周赛 166 [https://leetcode.com/contest/weekly-contest-166](https://leetcode.com/contest/weekly-contest-166)

贴个虽然答案正确，但是超时的算法。后面会改进下通过测试。

```kotlin
class Solution {
    fun smallestDivisor(nums: IntArray, threshold: Int): Int {
        var divisor = 1
        while (divisor > 0) {
            var sum = 0
            for (i in nums) {
                sum += kotlin.math.ceil((i * 1.0) / divisor).toInt()
            }
            if(sum <= threshold) {
                break
            }
            divisor++
        }
        return divisor
    }
}
```

### Review

[https://www.linux.com/news/linux-technology-new-year-ebpf-0/](https://www.linux.com/news/linux-technology-new-year-ebpf-0/)

这条新闻报道 内核虚拟机 - eBPF， 评价非常高，又是低消耗，又是高级的 Tracing。反正就是特性多，又不咋消耗性能，以后内核模块啥的可以退下了，都是 eBPF 程序的世界了。

下面是 SAP 开发者 [Gaurav Gupta](https://www.linkedin.com/in/gaurav-gupta-2437aa36/?originalSubdomain=in)去年十月份在 All Things Open 大会上的[发言](https://youtu.be/ug3lYZdN0Bk) 和 [PPT]([https://docs.google.com/presentation/d/1tnhlVqddPQ7wvhxp0_YiqCrowjB29RqV3sK2U7dKPug/edit#slide=id.g2f9bf84c2d_2_79](https://docs.google.com/presentation/d/1tnhlVqddPQ7wvhxp0_YiqCrowjB29RqV3sK2U7dKPug/edit#slide=id.g2f9bf84c2d_2_79))。

[https://docs.google.com/presentation/d/1tnhlVqddPQ7wvhxp0_YiqCrowjB29RqV3sK2U7dKPug/edit#slide=id.g2f9bf84c2d_2_79



### Tips

很多时候 Linux 发行版上的软件并不是最新的，而官方库的更新速度实在让人抓狂，这时候 LinuxBrew 就是比直接自己编译源码更好的方案了。因为基本是二进制的包，还可以使用清华的镜像。

[https://linuxbrew.sh/](https://linuxbrew.sh/)

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install.sh)"
```

### Share

[http://www.brendangregg.com/ebpf.html](http://www.brendangregg.com/ebpf.html)


工作久了就会遇到各种奇葩的问题，这些问题的根源并不在应用框架层面，需要深入到系统底层去找。这时候一个趁手的工具就非常的重要的，你总不想手调内核代码吧？估计很多应用开发工程师也没有这个时间去学习和掌握内核调试技术。但是 BPF 框架还是值得去研究一下的，无论是 IO 还是 网络层面的问题，掌握这个利器，什么问题都能给他查的明明白白。
