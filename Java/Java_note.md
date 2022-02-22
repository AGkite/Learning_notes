**equals()方法和"=="的区别**

**"=="的作用:**

基本数据类型：

byte,short,char,int,long,float,double,boolean之间的比较，应用双等号"==",比较的是它们的**值**。

引用数据类型：

用"=="进行比较的时候，比较的是它们在内存中的存放**地址**（**堆内存地址**）。

**equals()作用**

语法：str1.equals(str2)

引用数据类型：默认情况下比较的是**地址值**。

Object类中定义equals()方法的源码：

```java
public boolean equals(Object anObject) 
{
    if (this == anObject) 
    {
        return true;
    }
    if (anObject instanceof String) 
    {
        String anotherString = (String)anObject;
        int n = value.length;
        if (n == anotherString.value.length) 
        {
            char v1[] = value;
            char v2[] = anotherString.value;
            int i = 0;
            while (n-- != 0) 
            {
                if (v1[i] != v2[i])
                {    
                    return false;
                }
                i++;
            }
            return true;
        }
    }
    return false;
}
```

总结：

" =="：比较的是两个字符串内存地址的数值是否相等（**数值比较**）

 equals()：比较的是两个字符串的内容（**内容比较**）

**字符串相等判断的时候都使用equals()。**