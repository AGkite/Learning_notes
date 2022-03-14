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

文字超链接

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

图片超链接

```html
<a href="图像标签.html">
  <img src="../resources/images/1.jpg" alt="图片" title="头像" width="200" height="200">
</a>
```

锚标签

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

