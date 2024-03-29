﻿﻿﻿﻿﻿**c++基础**

**三目运算符**

作用：通过三目运算符实现简单的判断

语法：表达式1  ？  表达式2  ：  表达式3

解释：若表达式1值为True，执行表达式2，返回表达式2的结果

​			若表达式1值为False，执行表达式3，返回表达式3的结果

示例：

```c++
int main()
{
    int a=10;
    int b=20;
    int c=0; 
    c = a>b ? a : b;		//c++中三目运算符返回的是变量，可以继续赋值
    cout<<"c="<<c<<endl;
}
```

---

**switch语句**

作用：执行多条件分支语句

语法：

```c++
switch(表达式)
{
    case 结果1:执行语句;break;
    case 结果2:执行语句;break;
        ……
    default:执行语句;break;
}
```

---

**for循环**

作用：满足循环条件，执行循环语句

语法：for(起始表达式；条件表达式；末尾循环体){循环语句；}

示例：

```c++
int main()
    for (int i=0;i<10;i++)
    {
        cout<<i<<endl;
    }
```

---

**struct结构体**

作用：结构体允许内部的元素是不同类型的，弥补数组只能装同种类型的数据。

定义：

```c++
#include <iostream>
struct student 	//结构体类型的声明与定义分开
{
	int age;       //年龄
	float score;   //分数
	char sex;      //性别
};
int main ()
{
	struct student a={ 18,95,'f'}; //定义结构体变量
	cout<<"年龄："<<a.age <<"分数："<<a.score <<"性别："<<a.sex<<"\n";
	return 0;
}
```

---

**动态变量的创建**

作用：未知数组个数时可动态申请空间

语法：new 类型名;    （这个操作在内存中称为堆（heap））

示例：

```c++
//动态产生一个int型的变量，将20存于其中
int *p;
p = new int;
*p = 20;

//创建动态变量时，还可以指定空间中的初值
int *p = new int(10);
//相当于
int *p = new int;
*p = 10;
```

**用new操作创建一个一维数组**

语法：new 类型名 [元素个数]

```c++
//用new操作创建一个一维数组
int *p;
p = new int[10];//在堆上申请的数组是不会进行初始化，结果为随机值
```

动态数组与普通数组区别

```c++
int n;
p = new int [2*n];
//非法 int p[2*n]; 普通数组在编译时就要确定的常量
```

---

**动态变量的回收**

说明：c++程序运行运行期间，动态变量不会消亡。因此可用delete操作，回收某个动态变量。防止内存泄漏。

语法：收回一个动态变量

​			delete 指针变量；

​			收回一个动态数组

​			delete [] 指针变量；

示例：

```c++
int *p = new int(10);
delete p;

//数组用法
int n; 
int *p = new int[n];
cin>>n;
for(int i = 0; i < n; i++)
{
	cout << p[i] << endl;
}
delete []p;
```

---

**vector容器**

作用：像容器一样存放各种类型的对象，相当于一个能够存放任意类型的**动态数组**。

语法：

```c++
#include<vector>//使用前提，需包含头文件
using namespace std;
vector<int>arr//建立一个vector，int为数组元素的数据类型，arr为动态数组名
```

---

**extern**

作用：使得变量或者函数可以跨文件被访问。











