---
author: zx
categories:
  - t-tech
date: "2008-10-24T07:04:33+00:00"
tag:
  - wordpress
title: WordPress更换域名方法
---
一般只要执行以下mysql命令，就可完成域名的修改（注意某些数据库需要修改wp\_开头的表名）：

修改option\_value里的站点url和主页地址：

> UPDATE wp\_options SET option\_value = replace(option\_value, 'http://www.old-domain.com', 'http://www.new-domain.com') WHERE option\_name = 'home' OR option\_name = 'siteurl';

修改文章中内部链接及附件的地址：

> UPDATE wp\_posts SET post\_content = replace(post\_content, 'http://www.old-domain.com', 'http://www.new-domain.com');

修改文章默认的永久链接：

> UPDATE wp\_posts SET guid = replace(guid, 'http://www.old-domain.com','http://www.new-domain.com');
