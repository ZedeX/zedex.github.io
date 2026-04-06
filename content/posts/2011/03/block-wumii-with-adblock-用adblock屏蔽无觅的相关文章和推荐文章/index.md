---
author: zx
category:
  - t:-tech
date: "2011-03-20T12:46:15+00:00"
summary: |-
  无觅太多啦，到处无觅，就有觅了。非诚勿扰，屏蔽之。

  熟手直接看 [步骤4](/wp-content/uploads/2011/07/adblock-block-wumii311.png#adblock-wumii-filter)

  方法：

  1、安装 [Adblock](http://goo.gl/FTjA9) 之后找到Adblock的Option选项；
title: Block Wumii with Adblock 用Adblock屏蔽无觅的相关文章和推荐文章
---
无觅太多啦，到处无觅，就有觅了。非诚勿扰，屏蔽之。

熟手直接看 [步骤4](/wp-content/uploads/2011/07/adblock-block-wumii311.png#adblock-wumii-filter)

方法：

1、安装 [Adblock](http://goo.gl/FTjA9) 之后找到Adblock的Option选项；

![](/wp-content/uploads/2011/07/adblock-block-wumii13.png)

2、切换Option中的标签到Customize；

![](/wp-content/uploads/2011/07/adblock-block-wumii211.png)

3、点击Manually edit your filters后的Edit按钮；

![](/wp-content/uploads/2011/07/adblock-block-wumii311.png)



4、输入如下内容

> ##DIV\[class="wumii-related-items-div"\]  
##DIV\[id="wumiiDisplayDiv"\]  
##DIV\[id="wumiiBtnDiv"\]

完。

代码解释：  
Adblock的filter规则是

> URL##标签\[匹配条件\]

如果##前啥也不加就表示匹配任何URL。所以上面的语句翻译成白话就是，把 _所有网站_ 中 _DIV_ 标签中 _class="wumii-related-items-div"_ 的DIV揪出来砍了。其他两个也是这意思。

引申阅读：  
Adblock自己带了个很方便的工具“Block an ad on this page”，有点Firebug那个inspect工具的意思，可以指定一个目标狙击。用这个可以很方便的定位想阻止的非诚内容。

不过道高一尺魔高一丈，有一个方法也可以阻止这个inspect工具的嗅探，就是在z-index建一个最高级别的层，别的层都在它下面，这样inspect就只能抓到最上面那个空层了。怕麻烦的人可能就会放弃，不过还是可以从源代码着手搞定。但，谁那么有空啊，呵呵。

还有个Adblock无法解决的问题，就是它是基于id和class定位的，跟CSS和JS的标签选择器一样，如果DIV中不加选择器，Adblock表示无能为力。（除非此页面就一个DIV，不然所有的DIV都会被过滤，feedburner在RSS中加的Email this，share me什么的就是这么干的）

* * *

更新： [屏蔽Google Reader中的无觅广告](/wp-content/uploads/2011/07/adblock-block-wumii311.png?p=6091)
