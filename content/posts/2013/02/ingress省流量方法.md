---
author: zx
categories:
  - g-games
date: "2013-02-03T09:01:07+00:00"
title: Ingress省流量方法
---
前置条件：  
1、安卓要ROOT，因为本方法是修改HOST  
2、找到安卓下  
/etc/hosts  
或  
/system/etc/hosts

添加如下列：

> 127.0.0.1 mw2.google.com  
127.0.0.1 www.panoramio.com  
127.0.0.1 lh2.ggpht.com  
127.0.0.1 lh5.ggpht.com  
127.0.0.1 lh6.ggpht.com  
127.0.0.1 lh7.ggpht.com  
127.0.0.1 lh4.ggpht.com  
127.0.0.1 lh3.ggpht.com  
127.0.0.1 lh8.ggpht.com  
127.0.0.1 lh1.ggpht.com

本段目的是将INGRESS里PORTAL的图片屏蔽，经过统计，流量会减少50%以上。
