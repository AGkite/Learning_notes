**替换空格**

题目地址：https://leetcode.cn/problems/ti-huan-kong-ge-lcof

题目：

```
请实现一个函数，把字符串 s 中的每个空格替换成"%20"。

示例 1：
输入：s = "We are happy."
输出："We%20are%20happy."

限制：
0 <= s 的长度 <= 10000
```

解法一：

```java
class Solution {
    public String replaceSpace(String s) {
        return s.replace(" ","%20");
    }
}
```

解法二：

```java
class Solution {
    public String replaceSpace(String s) {
        String str="";
      for(int i=0;i<s.length();i++){
         
          if(s.charAt(i)==' '){
              str+="%20";
              continue;
          }
          str+=s.charAt(i);
      }
      return str;
    }
}
```

