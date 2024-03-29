**基本标签**

```html
<!--DOCTYPE告知浏览器使用的规范-->
<!DOCTYPE html>

<html lang="en">
<!--head标签代表网页头部-->
    <head>
        <!--meta描述性标签，描述网站信息，一般用来做SEO-->
        <meta charset="utf-8">
        <meta name="keywords" content="html">
        <meta name="description" content="学习html">
        
        <!--title网站标题-->
        <title>newone博客</title>
    </head>
    
<!--body标签代表网页主体-->
<body>
    <!--标题标签-->
    <h1>一级标签</h1>
    <h2>二级标签</h2>
    <h3>三级标签</h3>
    <h4>四级标签</h4>
    <h5>五级标签</h5>
    <h6>六级标签</h6>
    
    <!--段落标签-->
    <p>123</p>
    <p>456</p>
    <p>789</p>
    
    <!--hr水平线标签-->
    <hr/>
    
    <!--换行标签-->
    123<br/>
    456<br/>
    789<br/>

    <!--粗体，斜体-->
    粗体：<strong>ABCDEFG</strong>
    斜体：<em>ABCDEFG</em>
    
    <!--特殊符号-->
    空格
    <p>123   4556</p>
    <p>123&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;456</p>
    大于号
    <p>2&gt;1</p>
    小于号
    <p>1&lt;2</p>
    版权符号
    &copy;版权所有@newone
</body>
</html>
```

**图像标签**

```html
<img src="../resources/images/1.jpg" alt="图片" title="悬停文字" width="200" height="200">
<!--
src 为路径可以为绝对路径和相对路径（推荐）
alt 图片名字
title 鼠标悬停在图片上时显示
width 图片宽度
height 图片高度
-->
```

**超链接标签**

**文字超链接**

```html
<a href="图像标签.html" target="_blank">点击我跳转到图像标签页面</a>
<a href="https://www.howonenew.com" target="_self">点击我跳转到博客</a>
<!--
href:必填，表示要跳转到那个页面
target:表示窗口在哪里打开
_blank:在新标签中打开
_self:在本网页中打开
-->
```

**图片超链接**

```html
<a href="图像标签.html">
  <img src="../resources/images/1.jpg" alt="图片" title="头像" width="200" height="200">
</a>
```

**锚标签**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>

</body>
</html>
```

**列表**

作用：多用于网页底部分类栏

```html
<!--有序列表-->
<ol>
    <li>c/c++</li>
    <li>Java</li>
    <li>python</li>
    <li>go</li>
</ol>
<!--无序列表-->
<ul>
    <li>c/c++</li>
    <li>Java</li>
    <li>python</li>
    <li>go</li>
</ul>
<!--自定义列表
dl:标签
dt:列表名称
dd:列表内容
-->
<dl>
    <dt>学科</dt>

    <dd>c/c++</dd>
    <dd>Java</dd>
    <dd>python</dd>
    <dd>go</dd>
</dl>
```

![](images/Snipaste_2022-03-17_15-09-17.png)

**表格**

```html
<!--表格table
行: tr
列: td
-->
<table border="1px"><!--border 设置边框大小-->
    <tr>
        <td colspan="4" align="center">学生成绩</td>
        <!--colspan 合并列
			rowspan 合并行
			align   内容居中
		-->
    </tr>
    <tr>
        <td>姓名</td>
        <td>语文</td>
        <td>数学</td>
        <td>英语</td>
    </tr>
    <tr>
        <td>小明</td>
        <td>90</td>
        <td>100</td>
        <td>90</td>
    </tr>
    <tr>
        <td>李华</td>
        <td>90</td>
        <td>90</td>
        <td>100</td>
    </tr>
    <tr>
        <td rowspan="2">平均分</td>
        <td>90</td>
        <td>95</td>
        <td>95</td>
    </tr>
</table>
```

![](images/Snipaste_2022-03-17_15-05-25.png)

**媒体元素**

作用：添加媒体娱乐到网页

```html
<video src="../resources/video/schoolweb.mp4" controls autoplay></video>
<audio src="../resources/audio/陈奕迅-黄金时代.mp3" controls autoplay></audio>
<!--音频和视频
src:资源路径
controls:控制条
autoplay:自动播放
-->
```

**内联框架**

作用：在网页中内联（嵌入）另一个网页

配合超链接标签可以主动跳转到网页

```html
<iframe src="" name="skip" frameborder="0" width="500px" height="600px"></iframe>
<a href="http://www.howonenew.com" target="skip">点击跳转</a>
```

**表单**

作用：注册用户窗口

```html
<!--表单form
action:表单提交的位置，网站或请求处理地址
method:post , get 提交方式
get方式提交在url中可以看到提交信息，不安全，但高效
post方式提交较安全，可传输大文件
-->
<form action="媒体元素.html" method="post">
<!--文本输入框：input type="text"-->
    <p>名字：<input type="text" name="username"></p>
    <p>密码：<input type="password" name="pwd"></p>
    <p>
        <input type="submit">
        <input type="reset">
    </p>
</form>
```

![](images/Snipaste_2022-03-20_17-38-04.png)

**特殊字符**

| 显示结果 | 说明         | Entity Name | Entity Number |
| -------- | ------------ | ----------- | ------------- |
|          | 显示一个空格 | \&nbsp;      | \&#160;        |
| <        | 小于         | \&lt;        | \&#60;         |
| >        | 大于         | \&gt;        | \&#62;         |
| &        | &符号        | \&amp;       | \&#38;         |
| "        | 双引号       | \&quot;      | \&#34;         |
| ©        | 版权         | \&copy;      | \&#169;        |
| ®        | 注册商标     | \&reg;       | \&#174;        |
| ×        | 乘号         | \&times;     | \&#215;        |
| ÷        | 除号         | \&divide;    | \&#247;        |
