---
title: html标签学习
date: 2024-07-16 16:12:30
cover: https://cdn.jsdelivr.net/gh/ababll5/tuchuang@img/img/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20240716161403.jpg
tags:
   - html
   - web
---



# 文本格式化标签

<img src="https://cdn.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240716170135.png"/>

重要的用右边的标签（起到提示作用，提示你这个很重要）

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>03文本格式化</title>
</head>

<body>
    <b>加粗1</b>
    <strong>加粗2</strong>
    <br>

    <u>下划线1</u>
    <ins>下划线2</ins>
    <br>

    <i>斜线1</i>
    <em>斜线2</em>
    <br>

    <s>删除1</s>
    <del>删除2</del>

</body>

</html>
```





# 媒体标签



## 图片标签

- 在网页中现实图片

- 书写格式`<img src = "图片" `

- 双引号里面的属性写在标签内

- 标签可以同时存在多个属性

- 属性之间要用空格隔开
- 属性之间没有顺序之分

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>04-图片标签</title>
</head>
<body>
    <img src="./640.gif">
</body>
</html>
```



### 图片标签alt属性

`<img src="./没有图片" alt="加载失败">`

属性值: 替换文本

- 当图片加载失败时，就会现实alt中的文本
- 当图片加载成功时就不会现实alt中的文本



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>04-图片标签</title>
</head>
<body>
<img src="./没有图片" alt="加载失败">
</body>
</html>
```



###  图片标签title属性

`<img src="./图片" alt="替换文本" title="提示文本">`

属性值： 提示文本

​    当鼠标悬停在图片时显示的文本

title属性不止在图片标签，还可以用于其他标签



### 图片标签width和height属性

属性名：width(图片宽度)、height(图片高度) 

注意

- 只设置其中一个属性，另一个会自动等比例缩放（图片不会变形）

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>04-图片标签</title>
</head>
<body>
    <img src="./图片" alt="加载失败" title="提示文本" width="200">
</body>
</html>
```



- 如果同时设置两个属性，图片可能会变形

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>04-图片标签</title>
</head>
<body>
    <img src="./图片" alt="加载失败" title="提示文本" width="200" height="114">
</body>
</html>
```



所以正式的代码中只用写一个就好了,好处就是图片不会变形

<hr>

### 路径

同级`./图片`

下级`文件夹/图片`

上级`../图片`



## 音频标签

在页面插入音频

`<audio src="音频" controls></audio>`

![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240717082139.png)

音频标签目前只支持三种格式 ： mp3、Wav、ogg



## 视频标签

网页插入视频

```html
 <video src=""></video>
```

![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240717090634.png)

同上

视频标签支持格式: mp4 、webM、ogg



## 超链接

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <a href="https://blog.ababll5.cn/">点我去博客</a>
</body>
</html>
```

项目开发初期不知大链接填什么时可以写"#"代表空连接

还有一个好玩的就是在属性a之间再加其他标签 例如：

```html
<a href="./06-音频.html"><button>点我去音频</button></a>
```

这样，原本的字就变成了按钮，按按钮跳转，也可以加其他标签特别灵活，自己琢磨吧



### 超链接中的target属性

目标网页打开的形式

![](https://fastly.jsdelivr.net/gh/ababll5/tuchuang@img/img/20240717092626.png)

示例：

```html
<a href="https://blog.ababll5.cn/" target="_blank">点我去博客</a>
```

