**简化版的桶排序**

**问题描述** ：将同学们的分数从低到高进行排序，总共有5个同学，分别考了5 分、 3 分、5 分、 2 分和 8 分（满分是 10 分）。

**时间复杂度**：O(M+N)，M为桶的个数，N为待排序数的个数

```c
#include<stdio.h>
int main()
{
    int a[11],i,j,t;
    for(i=0;i<=10;i++)
    {
        a[i]=0;//初始化为0
    }
    for(i=1;i<=5;i++)//循环读入5个数
    {
        scanf("%d",&t);//把每个数读到变量t中
        a[t]++;//进行计数
    }
    for(i=0;i<=10;i++)//以次判断a[0]~a[10]
    {
        for(j=1;j<=a[i];j++)
        {
            printf("%d",i);
        }
    }
    getchar();getchar();
    //getchar();相当于system("pause");
    return 0;
}
```

---

**冒泡排序**

**基本思想**：每次比较两个相邻的元素，如果它们的顺序错误就把它们交换。

**时间复杂度**：O(N^2^)

```c
#include<stdio.h>
int main()
{
    int a[100],i,j,t,n;
    scanf("%d",&n);//输入一个数n，表示接下来有n个数
    for(i=1;i<=n;i++)//循环读入n个数到数组a中
    {
        scanf("%d",&a[i]);
    }
    //冒泡排序的核心部分
    for(i=1;i<=n-1;i++)//n个数排序，只用进行n-1趟
    {
        for(j=1;j<=n-1;j++)
        {
            if(a[j]<a[j+1])//比较大小并交换
            {
                t=a[j];a[j]=a[j+1];a[j+1]=t;
            }
        }
    }
    for(i=1;i<=n;i++)//输出结果
    {
        printf("%d",a[i]);
    }
    getchar();getchar();
    return 0;
}
```

```C
//冒泡排序分数于人名关联起来
#include <stdio.h>
struct student
{
	char name[21];
	char score;
};//这里创建了一个结构体用来存储姓名和分数
int main()
{
	struct student a[100],t;
	int i,j,n;
	scanf("%d",&n); //输入一个数n
	for(i=1;i<=n;i++) //循环读入n个人名和分数
		scanf("%s %d",a[i].name,&a[i].score);
		//按分数从高到低进行排序
	for(i=1;i<=n-1;i++)
	{
		for(j=1;j<=n-i;j++)
		{
			if(a[j].score<a[j+1].score)//对分数进行比较
				{ t=a[j]; a[j]=a[j+1]; a[j+1]=t; }
		}
	}
	for(i=1;i<=n;i++)//输出人名
		printf("%s\n",a[i].name);
	getchar();getchar();
	return 0;
}

```

---

**快速排序**

**算法思路**：首先在这个序列中选择一个基准数temp，先从右往左找一个小于 temp的数，再从左往右找一个大于 temp 的数，然后交换它们。这里用两个变量 i 和 j代表两个哨兵，分别指向序列最左边和最右边。右边的哨兵j先出动，找到小于基准数的数之后停下，然后左边的哨兵i找到大于基准数的数之后停下，两两交换。直到两个哨兵碰头，再将基准数归位。接下来继续处理左边的，再继续处理右边的这是一个递归调用函数的过程。

**时间复杂度**：O(NlogN)

```c
#include<stdio.h>
int a[101],n;//定义全局变量，这两个变量需要在子函数中使用
void quicksort(int left,int right)
{
    int i,j,t,temp;
    if(left>right)
    {return 0;}
    temp=a[left];//temp中存的就是基准数
    i=left;
    j=right;
    while(i!=j)
    {
        //顺序很重要，要先从右往左找
        while(a[j]>=temp && i<j)
        {j--;}
        //再从左往右找
        while(a[i]<=temp && i<j)
        {i++;}
        //交换两个数再数组中的位置
        if(i<j)//哨兵i和哨兵j没有相遇时
        {
            t=a[i];
            a[i]=a[j];
            a[j]=t;
        }
    }
    //最终将基准数归位，此时i=j
    a[left]=a[j];
    a[j]=temp;
    quicksort(left,i-1);//继续处理左边，这里是一个递归的过程
    quicksort(i+1,right);
    return 0;
}
int main()
{
    int i,j;
    //读入数据
    scanf("%d",&n);
    for(i=1;i<=n;i++)
    {
        scanf("%d",&a[i]);
    }
    quicksort(1,n);//快速排序调用
    //输出排序后的结果
    for(i=1;i<=n;i++)
    {
        printf("%d",a[i]);
    }
    getchar();getchar();
    return 0;
}
```

---





























