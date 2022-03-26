**MySQL压缩包安装**

将压缩包解压到D盘

![](images/Snipaste_2022-03-12_12-04-47.png)

在mysql安装目录下手动创建my.ini文件并填入以下内容

```shell
[mysql]
# 设置mysql客户端默认字符集
default-character-set=utf8
[mysqld]
# 设置3306端口
port = 3306
# 设置mysql的安装目录
basedir=D:\\mysql-8.0.28-winx64
# 设置 mysql数据库的数据的存放目录，MySQL 8+ 不需要以下配置，系统将自动生成data
# datadir=D:\\mysql-8.0.28-winx64\\data
# 允许最大连接数
max_connections=20
# 服务端使用的字符集默认为8比特编码的latin1字符集
character-set-server=utf8
# 创建新表时将使用的默认存储引擎
default-storage-engine=INNODB
```

配置环境变量

将mysql下的bin文件夹的绝对路径复制到系统变量中的path中

![](images/Snipaste_2022-03-12_11-08-00.png)

以管理员身份打开cmd，初始化mysql，mysql8.0之后自动生成data文件夹。

```mysql
mysqld  --initialize-insecure //初始化mysql,但暂不设置root密码
```

![](images/Snipaste_2022-03-12_11-14-55.png)

初始化后mysql安装目录下将产生data文件，里面存放着mysql初始的数据库

![](images/Snipaste_2022-03-12_12-06-28.png)

```mysql
mysqld install mysql	//安装mysql服务
```

![](images/Snipaste_2022-03-12_11-18-35.png)

登录mysql

```mysql
//免密码登录mysql
mysql -uroot

//切换数据库
use mysql;
 
//修改root用户的密码为123456，根据需要自己设置
alter user 'root'@localhost identified by '123456';
 
//刷新权限,修改密码或授权用户后必须要使用才可退出mysql,不然会导致进入不了mysql
flush privileges;
 
//退出mysql
quit 或 exit
```

![](images/Snipaste_2022-03-12_11-46-11.png)

```mysql
mysql -uroot -p	//之后输入密码，使用mysql
```

注意：

图形化界面连接mysql时可能出现mysqli_real_connect(): The server requested authentication method unknown to the client [caching_sha2_password]报错。

![](images/Snipaste_2022-03-12_11-28-02.png)

解决办法：

1.升级图形化界面版本（推荐）

2.更改数据库root用户的加密方式

```mysql
alter user 'root'@localhost identified with mysql_native_password BY '123456';
```

![](images/Snipaste_2022-03-12_11-57-16.png)

即可成功登录图形化界面

![](images/Snipaste_2022-03-12_11-59-17.png)

---

**mysql创建数据库**

进入mysql后查看有哪些数据库

```mysql
show databases;
```

![](images/Snipaste_2022-03-12_14-00-18.png)

创建一个新的数据库

```mysql
mysql> create database db_admin;//创建一个名为db_admin的数据库
mysql> use db_admin;//选择数据库
//创建数据表
mysql> create table tb_productategory( 
	-> id int(10) auto_increment primary key not null comment'系统自动编号',
	-> name varchar(50> not null comment'类别名称',
    -> level int(11) null comment'类别名称',
	-> pid int(11)null comment'父节点类型ID'); 
```

创建成功后用show或DESC命令查看表的结构

```mysql
show colunmns from tb_productategory;
desc tb_productategory;
```

![](images/Snipaste_2022-03-12_00-06-01.png)

查看当前数据库中有哪些表

```mysql
use db_product;
show tables;
```

![](images/Snipaste_2022-03-12_14-04-42.png)

组合主键

```mysql
create table abc(
id int(10) auto_increment not null commrnt'系统自动编号',
path varchar(225) not null comment'文件路径信息',
constraint primary key (id,path));	//设置组合主键
)
```

![](images/Snipaste_2022-03-14_23-28-44.png)

---

**导入.sql文件到数据库**

首先查看MySQL服务器配置信息

```mysql
show variables like '%char%';
```

更改字符集防止导入后出现乱码

```mysql
set names gbk;
//同时修改以下三个值
character_set_client
character_set_connection
character_set_results
```

![](images/Snipaste_2022-03-18_14-31-31.png)

导入.sql文件

```mysql
source /路径……/db_logistics.sql
```

![](images/Snipaste_2022-03-18_14-39-10.png)

---

**更改数据库**

添加字段到数据表

```mysql
alter table 表名 add 字段 类型 ……;
```

![](images/Snipaste_2022-03-18_15-20-29.png)

![](images/Snipaste_2022-03-18_16-26-22.png)

创建时间字段指定缺省值为插入记录时的系统日期和时间

![](images/Snipaste_2022-03-18_16-34-19.png)

设置数据表中字段唯一性

```mysql
alter table 数据表 add unique(字段); 
```

![](images/Snipaste_2022-03-18_15-53-28.png)

删除表中的字段

```mysql
alter table 表名 drop 字段名;
```

![](images/Snipaste_2022-03-18_17-34-50.png)

更改数据表名

```mysql
rename table 原表名 to 新表名;
```

![](images/Snipaste_2022-03-18_17-37-05.png)

给数据表中字段设置外键

```mysql
alter table 表名1 add foreign key(表名1中字段) references 表名2(表名2中字段);
```

![](images/Snipaste_2022-03-18_17-54-23.png)
