---
author: zx
categories:
  - g-games
date: "2010-08-03T13:38:45+00:00"
title: 20100603 弈 小试锋芒
---
启用了新的复盘程序，感谢这位热心的 [无有角](http://blog.sina.com.cn/wuyoujiao1108) 网友提供的 [FlashGoView](http://blog.sina.com.cn/s/blog_3db1e5d50100gcoi.html)，虽然并没有开源，但起码是过度时期可以接受的方案，也比截图更直观、更精悍了。  
有空的话，会做一款基于JavaScript的sgf解析器。

20130601更新：发现了一个基于JavaScript的sgf渲染的wgo.js

另外，对sgf文件格式还不了解，本来给一个sgf文件就能说明问题了的：）

执白中盘胜  

<link rel="stylesheet" href="/wgo/wgo.player.css">
<script src="/wgo/wgo.min.js"></script>
<script src="/wgo/wgo.player.min.js"></script>

<div id="wgo-20100603" style="width: 600px; margin: 1em auto;"></div>
<script>
new WGo.Player.BasicPlayer(document.getElementById("wgo-20100603"), { sgfFile: "20100603.sgf" });
</script>

[棋谱下载](20100603.sgf)
