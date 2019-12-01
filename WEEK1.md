## Algorithm

https://leetcode-cn.com/explore/featured/card/top-interview-questions-easy/1/array/21/

```java
class Solution {
		public int removeDuplicates(int[] nums) {
        int length = 1;
        for (int i = 0; i < nums.length - 1; i++) {
            if (nums[i] != nums[i + 1]) {
                nums[length] = nums[i + 1];
                length++;
            }
        }
        return length;
  	}
}
```

```kotlin
class Solution {
  fun removeDuplicates(nums: IntArray): Int {
      var length = 1
      for (i in 0 until nums.size - 1) {
        if (nums[i] != nums[i + 1]) {
        nums[length] = nums[i + 1]
          length++
        }
      }
      return length
    }
}
```

```swift
class Solution {
   func removeDuplicates(_ nums: inout [Int]) -> Int {
       guard nums.count > 0 else {
        	return 0
       };
       var length = 1
       for i in 0..<nums.count - 1 {
          if (nums[i] != nums[i + 1]) {
              nums[length] = nums[i + 1]
              length += 1
          }
       }
       return length
    }
}
```

### Review

https://www.nginx.com/blog/dynamic-modules-development/
这篇文章讨论了 Nginx 插件的发展到动态化模块的原型，以及未来。下面的评论也很好，都要看看。我是从评论里看到这个文章里讨论的插件未来形式已经坑了 😄。

### Tips

编译 nginx 动态模块的时候，在 ./configure 后面一定要加上 --with-compat, 不然会报二进制文件不兼容问题。第一次看官方的文章 https://www.nginx.com/blog/compiling-dynamic-modules-nginx-plus/ 并没有特别说明，以为是兼容 Nginx 和 Nginx Plus 用的。

### Share

本周分享一下声明式界面开发的一点想法：

React 火了之后，跟着 Flutter 、SwiftUI 和 Jetpack Compose 都出来了。

React 虽然在前端开发领域和 Vue 部分上下，但是在移动客户端上，基本属于被抛弃的技术了，以后估计也难有作为。新入门的人最好不要在 ReactNative 上花时间了，Weex 也一样。 坑太多。

Flutter 用了一段时间，很多缺陷，看看那 ISSUES 列表上过万的数字实在是不香。

SwiftUI 和 Jetpack Compose 都属于原生开发的加强和扩展，可以采用渐进的方式慢慢替代原有的实现，不像 React 和 Flutter ，学习和迁移成本都比较高。 Swift 和 Kotlin 作为非常像的一类现代语言，非常值得投入。准备年前用这两种方法重写公司内部的一款大概 5K 代码的小 App。
