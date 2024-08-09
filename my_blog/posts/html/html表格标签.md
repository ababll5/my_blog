---
title: html表格标签
date: 2024-07-18 07:48:53
cover: https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/f48ea1bf7c687d9e390337b54fff743.jpg
tags:
    - web
    - html
---



# 表格基本使用



![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718073532.png)

嵌套



```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <table border="1" width="600" height="300">
        <tr>
            <td>姓名</td>
            <td>年龄</td>
            <td>成绩</td>
        </tr>
        <tr>
            <td>张三</td>
            <td>18</td>
            <td>100</td>
        </tr>
        <tr>
            <td>李四</td>
            <td>19</td>
            <td>80</td>
        </tr>
    </table>
</body>

</html>
```



不过此时的表格还不像表格，这时我们就要在**table**标签中加一点属性

![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718083326.png)

不过实际开发中这对于央视效果推荐使用**css**来设置

> 效果展示

![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718084806.png)





# 表格标题和表头单元格标签

在表格中表示整体大标题和一列小标题

![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718084046.png)



> **注意** 
>
> > caption在table标签内
> >
> > th在tr标签内(用于替换td标签)



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <table border="1" width="600" height="300">
        <caption><h3>学生信息</h3></caption>
        <tr>
            <th>姓名</th>
            <th>年龄</th>
            <th>成绩</th>
        </tr>
        <tr>
            <td>张三</td>
            <td>38</td>
            <td>100</td>
        </tr>
        <tr>
            <td>李四</td>
            <td>19</td>
            <td>80</td>
        </tr>
    </table>
</body>
</html>
```



> 效果展示

![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718085334.png)





# 表格结构标签(了解)

让表格结构分组

![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718085840.png)





> 大概就是

![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718085932.png)

> 注意
>
> >**表格结构标签内部用于包裹tr标签**
> >
> >表格结构标签可以省略(意思是，不一定要用到这个结构)



# 合并单元格

水平或垂直的多个单元格合并起来

> 前



![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718090833.png)![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718090857.png)



> 后

![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718091132.png)![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718091251.png)



## 那么如何合并呢

1 首先得名曲合并哪几个单元格

2 通过上面的原则，再确定保留谁删除谁

- 向下合并——只保留上面的
- 左右合并——只保留最左边的

<br>

3 合并

![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240718092808.png)

> 注意
>
> >
> >
> >
