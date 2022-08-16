[**Java API文档**](http://www.oracle.com/technetwork/java/api-141528.html)

# **Java学习笔记**

## **运算符**

### **位移运算符**

"<<"(左移)：a<<b表示将二进制形式的a逐位b，最低位空出的b位补0.

例：

```java
int a=17;	a<<2=68//即17扩大了2*2=4倍
```

">>"(带符号右移)：a>>b表示将二进制形式的a逐位右移b位，最高位空出的b位补原来的符号位（即正数补0，负数补1）

例：

```java
int a=17;	a>>2=17/2*2=4
```

">>>"(无符号右移)：a>>>b表示将二进制形式的a逐位右移b位，最高位空出的b位一律补0。

例：

```java
int a=17;	a>>>2=17/2*2=4
```

---

### **算术运算符**

**四舍五入**

1、System.out.printf

```java
double a = 1.2356;
System.out.printf("%.2f",a);//"%.nf" n为正整数，四舍五入保留小数点后n位
```

2、DecimalFormat

```java
import java.text.DecimalFormat;
double a = 1.2356;
DecimalFormat df = new DecimalFormat("#.##");//"#.##"小数点后面的#个数代表保留小数个数
String format = df.format(a);
System.out.println(a);
```

3、Math.round()

```java
double a = 1.2356;
double round = Math.round(a*100)/100.0;
System.out.println(round);
```

---

## **流程控制**

### **循环控制**

#### break语句

语法：break	标签 ；

带标签的continue语句

语法：continue	标签；

```java
outer:for(int i=0;i<3;i++)
	{
		inter:for(int j=0;j<5;j++)
			{
				if(j==0)
				{
					break outer;//跳出外层循环，程序结束
				}
				else if(j%2==0)
				{
					continue outer;//跳至外层循环，从下一个i值开始执行
				}
			}
	}

```

---

## **字符串**

### **String类**

**charAt()方法**

作用：返回char指定索引处的值。  指数范围为0至length() - 1 。 

语法：

```Java
public char charAt(int index)
```

示例：

```java
public class Test {
    public static void main(String args[]) {
        String s = "ABCDEFGHIJK";
        char result = s.charAt(6);
        System.out.println(result);
    }
}
//运行结果：G
```

**length()方法**

作用：length() 方法用于返回字符串的长度。空字符串的长度返回 0。

语法：

```java
public int length()
```

示例：

```java
public class Test {
        public static void main(String args[]) {
                String Str = new String("abcdefghijk");
                System.out.print("字符串 Str1 长度 :");
                System.out.println(Str.length());
        }
}
//运行结果：11
```

**replace()方法**

作用：replace() 方法通过用 newChar 字符替换字符串中出现的所有 searchChar 字符，并返回替换后的新字符串。

语法：

```java
public String replace(char searchChar, char newChar)    
```

示例：

```java
public class Test{
    public static void main(String args[]){
        String str = new String("newoneooo");
        System.out.println(str.replace('o','a'));
    }
}
//运行结果：newaneaaa
```

**equals()方法和"=="的区别**

**"=="的作用:**

基本数据类型：

byte,short,char,int,long,float,double,boolean之间的比较，应用双等号"==",比较的是它们的**值**。

引用数据类型：

用"=="进行比较的时候，比较的是它们在内存中的存放**地址**（**堆内存地址**）。

**equals()作用**

语法：str1.equals(str2)

字符串：比较字符串的内容

引用数据类型：默认情况下比较的是**地址值**。

示例：

```java
String s1 = "Hello";              // String 直接创建
String s2 = "Hello";              // String 直接创建
String s3 = s1;                   // 相同引用
String s4 = new String("Hello");  // String 对象创建
String s5 = new String("Hello");  // String 对象创建
 
s1 == s1;         // true, 相同引用
s1 == s2;         // true, s1 和 s2 都在公共池中，引用相同
s1 == s3;         // true, s3 与 s1 引用相同
s1 == s4;         // false, 不同引用地址
s4 == s5;         // false, 堆中不同引用地址
 
s1.equals(s3);    // true, 相同内容
s1.equals(s4);    // true, 相同内容
s4.equals(s5);    // true, 相同内容
```

总结：

" =="：比较的是两个字符串内存地址的数值是否相等（**数值比较**）

 equals()：比较的是两个字符串的内容（**内容比较**）

**字符串相等判断的时候都使用equals()。**

---

## **I/O(输入/输出)**

输出

```java
System.out.print("hello_world");//输出不换行
System.out.println("hello_world");//输出换行
```

输入单个字符

```java
import java.io.*;
import java.util.*;
public class Test{
    public static void main(String[] args)throws IOException{
        char c=(char)System.in.read();//输入单个字符
        System.out.println(c);
    }
}

```

Scanner输入

```java
import java.io.*;
import java.util.*;
public class Test{
    public static void main(String[] args)throws IOException{
        Scanner in=new Scanner(System.in);
        
        int a=in.nextInt();//输入一个整数
        System.out.println(a);
         
        double b=in.nextDouble();//输入一个双精度的浮点数
        System.out.println(b);
         
        String str1=in.next();//输入字符串，遇到分号则输入终止
        System.out.println(str1);
         
        String str2=in.nextLine();//输入一行，中间可有多个空格
        System.out.println(str2);
    }
}
```

---

**练习：**

题目：编写一个程序，从编号1~50的学生中随机抽取一等奖1名，二等奖2名，三等奖3名，任何一名

学生不能重复获奖，抽奖循序是：先抽三等奖，再抽二等奖，最后抽一等奖。

```java
public class StudentRandom {
    public static void main(String[] args) {
        int [] stu = new int[6];
        for (int i = 0; i < 6; i++) {
            stu[i]=(int)(Math.random()*50+1);
            for(int j=0;j<i;j++){
                if(stu[j]==stu[i]){
                    stu[j]=(int)(Math.random()*50+1);
                    j=-1;
                }
            }
        }
        System.out.println("获得一等奖学生："+stu[0]+"\n获得二等奖学生"+stu[1]+","+stu[2]+"\n获得三等奖学生"+stu[3]+","+stu[4]+","+stu[5]);
    }
}

```

题目：编写Calculator.java 程序,

实现功能：从命令行输入两个操作数和一个运算符,

参数格式为：操作数1 运算符 操作数2

其中,两个操作数为double类型,运算符为“+”、“-”、“*”、“/”中的一个,运行程序输出运算结果。

```java
import java.util.*;
import static java.lang.Double.parseDouble;
public class Calculator {
    public static void main(String[] args) {
        double num = 0;
        System.out.println("请输入算术表达式：");
        Scanner sin = new Scanner(System.in);
        String str = sin.next();
        int n =str.length();
        for (int i = 0; i < n; i++) {
            switch (str.charAt(i)) {
                case '+' -> num = parseDouble(str.substring(0, i)) + parseDouble(str.substring(i + 1));
                case '-' -> num = parseDouble(str.substring(0, i)) - parseDouble(str.substring(i + 1));
                case '*' -> num = parseDouble(str.substring(0, i)) * parseDouble(str.substring(i + 1));
                case '/' -> num = parseDouble(str.substring(0, i)) / parseDouble(str.substring(i + 1));
            }
        }
        System .out.println(str+"="+num);
    }
}
```

---

## **集合类**

### **List集合**

List集合中元素**可以重复**，各元素的顺序就是对象插入的顺序。

#### **LinkedList**

**常用于创建链表**

LinkedList 实现了List 接口，能对它进行列表操作。

LinkedList 实现了Deque 接口，即能将LinkedList当作双端队列使用。

LinkedList 实现了Cloneable接口，能克隆。

**常用方法**

**增**
 public void addFirst(E e)，添加到第一个元素

 public void addLast(E e)，添加到最后一个元素

 public boolean offer(E e)，向链表末尾添加元素，返回是否成功

 public boolean offerFirst(E e)，头部插入元素，返回是否成功

 public boolean offerLast(E e)，尾部插入元素，返回是否成功

**删**

public void clear()，清空链表

 public E removeFirst()，删除并返回第一个元素

 public E removeLast()，删除并返回最后一个元素

 public boolean remove(Object o)，删除某一元素，返回是否成功

 public E remove(int index)，删除指定位置的元素

 public E poll()，删除并返回第一个元素

 public E remove()，删除并返回第一个元素

**查**

public boolean contains(Object o)，判断是否含有某一元素

public E peek()，返回第一个元素

public E peekFirst()，返回头部元素

public E peekLast()，返回尾部元素

**改**

public E set(int index, E element)，设置指定位置的元素

---







