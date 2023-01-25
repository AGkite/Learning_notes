#### [剑指 Offer 04. 二维数组中的查找](https://leetcode.cn/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/)

在一个 n * m 的二维数组中，每一行都按照从左到右 **非递减** 的顺序排序，每一列都按照从上到下 **非递减** 的顺序排序。请完成一个高效的函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。

**示例:**

现有矩阵 matrix 如下：

```
[
  [1,   4,  7, 11, 15],
  [2,   5,  8, 12, 19],
  [3,   6,  9, 16, 22],
  [10, 13, 14, 17, 24],
  [18, 21, 23, 26, 30]
]
```

给定 target = `5`，返回 `true`。

给定 target = `20`，返回 `false`。

**限制：**

```
0 <= n <= 1000
0 <= m <= 1000
```

**注意：**本题与主站 240 题相同：https://leetcode-cn.com/problems/search-a-2d-matrix-ii/

解法一：

```java
class Solution {
    public boolean findNumberIn2DArray(int[][] matrix, int target) {
       for(int [] a:matrix){
           for(int i=0;i<a.length;i++){
               if(target==a[i]){
                   return true;
               }
           }
       }
       return false;
    }
}
```

解法二：

```java
class Solution {
    public boolean findNumberIn2DArray(int[][] matrix, int target) {
       for(int j=0;j<matrix.length;j++){
           for(int i=0;i<matrix[j].length;i++){
               if(target==matrix[j][i]){
                   return true;
               }
           }
       }
       return false;
    }
}
```

解法三：

```java
class Solution {
    public boolean findNumberIn2DArray(int[][] matrix, int target) {
        for(int [] a : matrix){
            int n = search(a,target);
            if(n>=0){
                return true;
            }
        }
        return false;
    }
    public int search(int [] nums,int target){
        int low = 0;
        int heigh = nums.length-1;
        while(low<=heigh){
            int mid = (heigh-low)/2+low;
            int k = nums[mid];
            if(k==target){return mid;}
            else if(k>target){heigh = mid-1;}
            else{low = mid+1;}
        }
        return -1;
    }
}
```

