---
author: zx
category:
  - t:-tech
date: "2014-06-06T07:38:32+00:00"
title: Beyond Compare 文件大小不一致但是内容一致的解决方案
---
这个问题困扰我多年。

拿WordPress举例：

从下面两图可见文件大小不一致，但是Beyond Compare可以比较出内容一致，从而将比较结果显示为“相同”（=）

![diff-size-same-content-01](/wp-content/uploads/2014/06/diff-size-same-content-01.png)![diff-size-same-content-02](/wp-content/uploads/2014/06/diff-size-same-content-02.png)

但是内容不一致的文件会被比较出来，如readme.html文件，下图反映了这一情况。

![diff-size-same-content-03](/wp-content/uploads/2014/06/diff-size-same-content-03.png)

需要做的设置如下：将文件夹的比较设置中，“比较”选项卡中的“需要打开的文件”设置为“基于规则的比较”

![diff-size-same-content-04](/wp-content/uploads/2014/06/diff-size-same-content-04.png)![diff-size-same-content-05](/wp-content/uploads/2014/06/diff-size-same-content-05.png)

如果将“文本比较”中“重要”选项卡中的“比较行尾（PC/Mac/Unix）”选中的话…

![diff-size-same-content-06](/wp-content/uploads/2014/06/diff-size-same-content-06.png)![diff-size-same-content-07](/wp-content/uploads/2014/06/diff-size-same-content-07.png)

行尾不同也会被认为是不同的文件（默认“基于规则的比较”是会忽略这种不同的）。

![diff-size-same-content-08](/wp-content/uploads/2014/06/diff-size-same-content-08.png)
