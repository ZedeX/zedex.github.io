---
author: zx
categories:
  - i-internet
cover:
  alt: cdn-zedex
  image: /wp-content/uploads/2019/06/cdn-zedex.png
date: "2019-06-19T08:13:16+00:00"
title: 开启了HTTPS服务
---
一直以来我的博客处于访问的边缘地带，我也没有精力去折腾新科技。本着“能用就行”的最低标准指导原则，一直很out的没用https。

最近忽然发现阿里云主机可以一键开启https服务，所以就手欠点了一下，就赫然开启了……

就是这么简单

![](/wp-content/uploads/2019/06/cdn-zedex.png)

但是访问时还是会被Chrome浏览器定义为“不安全的访问”。经查，是由于CDN默认没有开启https协议服务，开启一下，然后等待CDN同步，一切就都搞定了。

感谢阿里云、感谢七牛、感谢Denis。
