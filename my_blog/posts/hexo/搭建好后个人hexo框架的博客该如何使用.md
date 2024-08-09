---
title: 搭建好后个人hexo框架的博客该如何使用
date: 2024-06-22 06:48:15
cover: http://ababll5.asia/vip/2024/07/22/669d3a7098579.jpg
tags:
   教程
---

上次我们搭建好了基于hexo框架的个人博客今天我就来教大家如何使用
=

# 创建博文
```
hexo new "新博文标题"
```
然后在
`hexo`根目录下找到`source` 里面的`_posts`找到你刚创建的`项目名.md`用记事本或VScode编辑它（个人推荐VScode）  

打开后
-

```md
---
title: 搭建好后个人hexo框架的博客该如何使用     //标题
date: 2024-06-22 06:48:15                   //日期
tags:                                      //标签
   
---

之后就是md语法写的博客了
(我的主题是Butterfly，我也推荐用这个主题想装的请看后文)
```
写完后记得保存然后`hexo g`生成一遍不然网站上不会出现

# 如何安装好看的主题

虽然自带的主题不好看，但hexo框架支持很多个主题。不过现在2024年了很多主题已经不再维护了，在这里我推荐一款还在维护的主题`Butterfly`(2024年6.22)
本文参考Butterfly官方文档https://butterfly.js.org/posts/21cfbf15/  
想要安装首先得右键hexo的根目录用git bash打开(都会了吧上次之前那一篇"hexo+github搭建教程"讲过)

### 安装
参考的官方文档https://butterfly.js.org/posts/21cfbf15/    我的不保证全新，具体以官方文档为准  
-

稳定版
-
```powershell
git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly
```
测试版(可能有问题)
-
```powershell
git clone -b dev https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly
```
装插件(如果你没有 pug 以及 stylus 的渲染器，请下载安装：)
-
```powershell
npm install hexo-renderer-pug hexo-renderer-stylus --save
```
最后
-
打开hexo 根目录下的`_config.yml`把里面的`theme`设为`theme: butterfly`(想快速找到`theme`Windows用户可以在记事本里ctrl+f搜索`theme`)然后就可以`hexo g` `hexo s`测试了

# 注意
我只介绍了最基本的  
=
看官方文档https://butterfly.js.org/posts/21cfbf15/  还有更好玩好看的设置，我就不多介绍了
-