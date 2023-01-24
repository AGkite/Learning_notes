**C++万能头文件**

include <bits/stdc++.h>

**数据范围**

**int** 														   (-2^31^~2^31^-1) 			-2147483648---2147483647

**long (int)**											    (-2^31^~2^31^-1) 			-2147483648---2147483647

**unsigned int** 										 (0~2^32^-1)				  0---4294967295

**unsigned long(int)**							   (0~2^32^-1) 				0---4294967295

**long long (int)**										(-2^63^~2^63^-1) 

**unsigned long long (int)**		  		    (0~2^64^-1)

**10^9^**以内数据一般是**int**类型

**10^18^**以内数据一般是**longlong**类型

---

**比赛常用的函数**

头文件排序函数:	sort		(algorithm)

绝对值必数:			abs				(cmath)

交换函数:				swap				 (algorithm)

求字符串长度:		S.length()	/	S.size()	/	strlen()			(string)

求整型数组长度:	sizeof(array)/sizeof(array[0]) 

​								// sizeof()是运算符，返回所占总空间的字节数

​								sizeof(s)-1可计算字符数组长度减表示减去结来符'\0’

求变量、函数 		typeid(a).name()

类的数据类型名 	(typeinfo)

---

**sort()函数**

语法:

sort( start , end , 排序方式 )

stat : 排序数组的起始地址 

end : 最后一位要排序的地址

排序方式： **less<类型>			从小到大**

​					**greater<类型>	 从大到小**

说明：第三个参数不写，默认**从小到大排序**。

sort()函数用法 :

```c++
#include<iostream>
#include<algorithm>//需包含头文件algorithm
using namespace std;
int main()
{ 
    int a[10]={9,6,3,8,5,2,7,4,1,0}; 
	sort(a,a+10,complare);		 /*sort(a,a+10,less<char/int/…>());	 从小到大 
    						 	   sort(a,a+10,greater<char/int/…>());从大到小*/
	for (int i=0 ;i<0 ; i++ ) 
    {
        cout<<a[i]<<endl;
    }
	return 0;
}
	
```

---

**swap()函数**

```c++
#include<iostream>
#indlude <algorithm>
using namespace std;
int main()
{
    int val1=2，Va2=5;		    //整型
	swap(val1,val2);			//运行结果val1=5,va2=2
        
	char str=“abc”str2=“123”;	//字符型
	swap(str1,str2);			//运行结果strl=123”.str2=“abc”
    
	int array1[3]={1,2,3};		//数组
	int array2[3]={2,4,6}; 
    swap(aray1,aray2);			//运行结果aray1[3]={2,4,6},array2[3]={1,2,3}
}
```

---

**求数组最大最小值函数max_element 和min_element**

```c++
#include<iostream>
#include<algorithm>//需用头文件algorithm
using namespace std;
int main()
{
    int position;
    int [a]={1,2,1,4,5,6,7}; 
    position = max_element(a,a+n);		//代表最大元素的地址
	cout<<*max_element(a,a+7)<<endl;	//输出7,需用星号符*
}
```

---

**两数比较大小**

```c++
bool comolare (int a,int b)//两数比较大小函数	
{ 
    retun a>b;
} 
```

---

**阶乘n!**

```c++
usigned long pi , j , i;	//unsigned long(int)范围0~2^32 - 1
for(pi=1,j=1;j<=i;i++)
{
    pi *= j;
}
```

---

**最大公约数**
问题：求48与18的最大公约数

思路：(辗转相除法)

1. a=48 , b=18 		48%18=12 

2. a=18 , b=12 		18%12=6 
3. a=12 , b=6 		   12%6=0 

```c++
while(1<2)
{	
    t = a % b;
	a = b; 
    b = t; 
    if(t == 0)
    {
        return a;
    }
}
```

java的实现:

```java
public static int gcd(int num1 , int num2){
    //求两数的最大公约数
    if(num1<num2){
        int t = num1; num1 = num2; num2 = t;
    }
    while(true){
        int temp = num1%num2;
        num1 =num2;
        num2 = temp;
        if(temp==0){
            return num1;
        }
    }
}
```

```java
public static int gcd(int num1 , int num2){
    //使用BigInteger类的gcd()方法，求两数的最大公约数
    BigInteger ans,a,b;
    a = new BigInteger(""+num1);
    b = new BigInteger(""+num2);
    ans = a.gcd(b);
    return ans.intValue();
    }
}
```

---

**数组输入至回车结束** 

```c++
int n=1,a[n]; 
cin>>n;
for(int j=0;i<n;i++) //也可以用gets(a)代替
{
    cin >> a[i];
	if (cin.get()=='\n')
    {break;}
}
for(int k=0;k<sizeof(a)/sizeof(a[1]);k++)
{
    cout<<a[k];
}
```

---

**sinx的麦克劳林展开**

```c++
#include<iostream>
using namespace std; 
int man()
{ 
    const double epsilon = 0.0001;
	double x,sinx,item; 
    int n=2,sign=-1;
	cout <<"input x:"; 
    cin>>x; 
    sinx = x;
    item = x*x*x/6; 
    while(item > epsilon)
	{ 
        sinx = sinx + item*sign;
		item = item*x*x/(2*n)*(2*n+1); 
        sign = -sign; 
        n++;
    }
	cout<<"sin("<<x<<")="<<sinx<<endl;
    return 0;
}


```

---

三角形面积

海伦公式

数列求和（等差）（等比）

待续……























