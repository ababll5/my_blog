---
title: 初试html
date: 2024-07-15 16:09:21
cover: https://pic.imge.cc/2024/07/15/6694e973a6e6c.jpg
tags:
   - web
   - html
---

# 前言

c++学的有些累了，最近想学学三大前端 html、css、js

首先先学学html 

# html学习

html的代码就不能叫函数了，叫元素



### 第一个html的代码

>  输出hello world

`index.html`

```html
<!DOCTYPE html>
<html>
<head>  <!--头部元素-->
    <meta charset="utf-8">
    <title>你好世界</title>   <!--网站标题-->
</head>
    
<body> <!--可见页面的内容-->
    <h1>hello world</h1>  <!--标题-->
    <p>hello world</p>    <!--文章-->
</body>

</html>
```

- **<!DOCTYPE html>** 声明为 HTML5 文档
- **<html>** 元素是 HTML 页面的根元素
- **<head>** 元素包含了文档的元（meta）数据，如 **<meta charset="utf-8">** 定义网页编码格式为 **utf-8**。
- `<title>`元素描述了文档的标题
- `<body> `元素包含了可见的页面内容
- `<h1>` 元素定义一个大标题
- `<p>` 元素定义一个段落



### 基础

#### html标题

```html
<h1>这是一个标题</h1>
<h2>这是一个标题</h2>
<h3>这是一个标题</h3>
```

以此类推由 h1~h6



#### html段落

`<p>`

```html
<p>这是一个段落。</p>
<p>这是另外一个段落。</p>
<p>
    hello
    <hr>
    <br>
    world
</p>
```

`<br>`可以起到在一个`<p>`中换行的作用

`<hr>`可以创建一条水平线

也可以使用`<pre>`这样你怎么打的字，就输出什么样



#### html链接

`<a>`

```html
<a href="blog.aball5.cn">这是一个链接</a>
```



#### html图像

` <img>`

```html
<img src="图片地址" width="宽" height="高" />
```



剩下的都参考的[菜鸟教程]([HTML URL | 菜鸟教程 (runoob.com)](https://www.runoob.com/html/html-url.html))

