数组中重复的数字

题目地址：https://leetcode.cn/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof

题目：

```
找出数组中重复的数字。

在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。

示例 1：
输入：
[2, 3, 1, 0, 2, 5, 3]
输出：2 或 3 

限制：
2 <= n <= 100000
```

解法一：

```java
class Solution {
    public int findRepeatNumber(int[] nums) {
        int t=0;int i=0;
        int n=nums.length;
        int [] box = new int[n];
        for (i=0;i<n;i++){
            t=nums[i];
            box[t]++;
        }    
        for(i=0;i<n;i++){    
            if(box[i]>1){
                break;
            }
        }
        return i;
    }
}
```

