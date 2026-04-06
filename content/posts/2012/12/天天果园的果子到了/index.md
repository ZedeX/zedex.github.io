---
author: zx
category:
  - l:-life
date: "2012-12-28T13:56:00+00:00"
summary: |-
  天天果园的果子到了。{{ double-space-with-newline }}[![image](/wp-content/uploads/2014/07/wpid-mmexport1406559566141.jpg)](/wp-content/uploads/2014/07/wpid-mmexport1406559566141.jpg)

  整体感觉：物流是自建（也可能是外包，有没有知道内幕的？）的冷链，速度基本没问题，上海地区昨天下单今早就到了。朋友圈的反馈，北京、厦门、广州的小伙伴们也是今早就到了，重庆、成都、青岛、武汉要今天下午，还有部分城市要隔天到货，沈阳地区估计需要3天左右。基本上可以打80分。
title: 天天果园的果子到了
---
天天果园的果子到了。  
[![image](/wp-content/uploads/2014/07/wpid-mmexport1406559566141.jpg)](/wp-content/uploads/2014/07/wpid-mmexport1406559566141.jpg)

整体感觉：物流是自建（也可能是外包，有没有知道内幕的？）的冷链，速度基本没问题，上海地区昨天下单今早就到了。朋友圈的反馈，北京、厦门、广州的小伙伴们也是今早就到了，重庆、成都、青岛、武汉要今天下午，还有部分城市要隔天到货，沈阳地区估计需要3天左右。基本上可以打80分。

[![image](/wp-content/uploads/2014/07/wpid-mmexport1406559568811.jpg)](/wp-content/uploads/2014/07/wpid-mmexport1406559568811.jpg)[![image](/wp-content/uploads/2014/07/wpid-mmexport1406559571495.jpg)](/wp-content/uploads/2014/07/wpid-mmexport1406559571495.jpg)

结论是：华东、华中、华南、华北、西南的一二线城市的冷链运输一般隔天即到，东北需要3天（有没有西北的样本点？）。冷链运输问题基本解决。

果子质量：新鲜，但是没有完全成熟，可能是为了在路上保鲜吧，但结果就是没有办法买来就吃，需要常温再放几天。打65分。  
[![image](/wp-content/uploads/2014/07/wpid-mmexport1406559574097.jpg)](/wp-content/uploads/2014/07/wpid-mmexport1406559574097.jpg)

[![image](/wp-content/uploads/2014/07/wpid-mmexport1406559576734.jpg)](/wp-content/uploads/2014/07/wpid-mmexport1406559576734.jpg)[![image](/wp-content/uploads/2014/07/wpid-mmexport1406559581926.jpg)](/wp-content/uploads/2014/07/wpid-mmexport1406559581926.jpg)[![image](/wp-content/uploads/2014/07/wpid-mmexport1406559584508.jpg)](/wp-content/uploads/2014/07/wpid-mmexport1406559584508.jpg)

问题：运输周期和果品成熟度之间有不可调和的矛盾--因为在包装的时候无法判定运输到哪里去，所以为了保质要预留路上的果实成熟缓冲期。这一点上短期内无法解决，体验还是没有百果园这种“冷链到点，终端零售”好。

要解决这个问题，需要建模：一是果实成熟度的计算公式，不同果实不一样，同种果实不同品种甚至不同产地可能都会有差别，所以公式要自学习，每一批量（per SKU）大数据反馈，参数化校正; 二是果实成熟度在一定温度下随时间变化的曲线，每SKU的果实每个温度有一条曲线; 第三，根据产地果实成熟度预判到达目的地时的果实成熟度，在客户下单的时候根据距离反推需要什么样的果实，在下单的时候去采集相应的果实。

这只是理想状况，实际情况是生产的果园、物流公司、电商平台都是相互独立的，要走的路还很长。
