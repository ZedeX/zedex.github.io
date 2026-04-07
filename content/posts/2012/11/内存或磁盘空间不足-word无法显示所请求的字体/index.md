---
author: zx
categories:
  - t-tech
date: "2012-11-22T07:01:11+00:00"
tag:
  - 优化
  - 字体
title: 内存或磁盘空间不足 Word无法显示所请求的字体
---
最近整理字体，整理好之后将所有字体安装到系统中备用，今日打开Office Word程序时，却收到这样的警告：

![内存或磁盘空间不足 Word无法显示所请求的字体](/wp-content/uploads/2013/02/out-of-memory-microsoft-office-word-font-request-1.png)

同时Word中只有最基本的几个字体了。

![out-of-memory-microsoft-office-word-font-request](/wp-content/uploads/2013/02/out-of-memory-microsoft-office-word-font-request-2.png)

后来将虚拟磁盘设置扩大，并且把不常用的字体卸载掉，才解决这个问题。

印象中Photoshop也会在软件启动时预先读取系统所有字体，不但增大内存使用量，而且导致软件启动速度变慢、缓存会增大许多，并且在点击字体下拉菜单选择字体时，会因为要显示预览字体而花费额外渲染时间。

所以还是养成好习惯，不常用的字体不要安装到系统为好。
