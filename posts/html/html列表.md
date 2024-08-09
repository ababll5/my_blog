---
title: html列表标签
date: 2024-07-17 11:11:12
cover: https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20240716170406.jpg
tags:
    - html
    - web
---



# 使用场景

网页排版

特点：按照行的方式，整齐显示类容

种类：无需列表、有序列表、自定义列表



# 无序列表

在网页中表示一组无顺序之分的列表，如新闻列表

组成

- `ul` 表示无序列表的整体，用于包裹标签
- `li`表示无序列表的每一项，用于包含每一行的内容



特点

列表每一项都有一个黑点如下

- 

 

注意

ul标签只允许包含li标签

li标签可以包含任何内容 



水果变量

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <ul>
        <li>香蕉</li>
        <li>榴莲</li>
    </ul>
</body>
</html>
```



# 有序列表



- `ol` 表示无序列表的整体，用于包裹标签
- `li`表示无序列表的每一项，用于包含每一行的内容

规则同上



例子 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <ol>
        <li>张三:100分</li>
        <li>李四:80分</li>
    </ol>
</body>
</html>
```



# 自定义列表



![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240717114453.png)

特点

- dd钱会默认显示缩进效果  



注意

- dl标签只允许dt/dd标签

- dt/dd标签可以包含任意内容

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <dl>
        <dt>帮助中心</dt>
        <dd>联系客服</dd>
        <dd>账户管理</dd>
    </dl>
</body>
</html>
```

