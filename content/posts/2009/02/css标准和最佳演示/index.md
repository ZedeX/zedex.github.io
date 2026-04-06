---
author: zx
category:
  - t:-tech
date: "2009-02-21T05:53:22+00:00"
summary: |-
  原文：CSS Standards & Best Practices{{ double-space-with-newline }}译者： [FlyChina](http://127.0.0.1/)

  CSS是用来定义网站的 **用户界面** 或将显示和内容区分开来的。

  由于CSS被广泛地使用在几乎所有网站上，所以让我们花些时间来创建样式表并确保它符合良好的标准。下面的技巧会极大地在开发过程中帮助CSS初学者。

  # 索引

  本处的定义将帮助你和其他开发者了解网站和CSS文件，还将帮助你们了解CSS文件中的内容。索引部分知识一个格式化了的 **CSS注释段落**。

  - 给出CSS文件的 **作者信息**
  - 定义网站的 **设计**（列数，静态/动态）\[columns, static/liquid\]
  - 持续跟踪文件 **版本**（当文件有多个作者或未来需要有升级更新的时候非常有用）
title: CSS标准和最佳演示
---
原文：CSS Standards & Best Practices  
译者： [FlyChina](/)

CSS是用来定义网站的 **用户界面** 或将显示和内容区分开来的。

由于CSS被广泛地使用在几乎所有网站上，所以让我们花些时间来创建样式表并确保它符合良好的标准。下面的技巧会极大地在开发过程中帮助CSS初学者。

# 索引

本处的定义将帮助你和其他开发者了解网站和CSS文件，还将帮助你们了解CSS文件中的内容。索引部分知识一个格式化了的 **CSS注释段落**。

- 给出CSS文件的 **作者信息**
- 定义网站的 **设计**（列数，静态/动态）\[columns, static/liquid\]
- 持续跟踪文件 **版本**（当文件有多个作者或未来需要有升级更新的时候非常有用）

# 锚点

锚点就好像在同一个CSS文件中的 **书签** 一样，锚点使你清晰地浏览整个CSS文件按并且使它很有组织。

锚点需要在CSS的索引（上面提到的）处定义，因为CSS没有自己的锚点系统，所以我在文档中使用了一个简单的技巧定义锚点。

方法是用一个比较罕见的字符来定义注释，当你想找某个锚点时，你就可以从索引处复制并查找锚点的定义符，并找到该锚点。

# 重定义

重定义是用来覆盖HTML默认的标签样式，把它们进行重定义的方法。你是否见过这样的CSS代码，它只是想把那个特定的元素加上样式！

CSS中一个非常美丽的用法是 **上下文选择器**，让我们使用它：

# 命名规则

一个很关键的因素将元素给出精确无误并且干净有效的名字，这将 **避免混乱** 并让你更容易快捷地读懂你的CSS。

# 速写

CSS中的速写功能是你可以将许多同类型的属性合并成一个的属性。

CSS速写使开发过程更简单并且让你的CSS文件干净、简短、可读，下面是几个例子：

**进一步阅读：**

- CSS速写手册（已失效）
- [CSS速写简介](http://www.sitepoint.com/article/introduction-css-shorthand/ "Introduction to CSS Shorthand")
- [有效利用CSS速写属性](http://www.456bereastreet.com/archive/200502/efficient_css_with_shorthand_properties/ "Efficient CSS with shorthand properties")

# Sprites

（译者注：翻译成精灵好像并不能对文章加深感性认识，反倒在真正看到英文的时候不理解了，所以干脆不译。）

将所有的背景图片合并到 **一张** 并且使用背景定位来显示不同的部分，这就是我们所说的CSS Sprites。

CSS Sprites能够减少 **HTTP请求** 的数量，节省 **带宽**，使得读取更快。同时也可以避免图像不稳定现象（比如当鼠标经过一张图片时可以显示另一张图片的效果，后一张图片将在慢速的因特网连接中等待半天才会出现）。

CSS Sprites最佳并且最受欢迎的例子是苹果公司网站上的菜单系统：

**进一步阅读：**

- 详解CSS Sprites的使用方法
- [CSS Sprites：它们是什么，它们为什么牛逼，以及怎样使用他们](http://css-tricks.com/css-sprites-what-they-are-why-theyre-cool-and-how-to-use-them/ "CSS Sprites: What They Are, Why They’re Cool, and How To Use Them")
- [CSS Sprites：使图片切片灭亡之吻](http://www.alistapart.com/articles/sprites/ "CSS Sprites: Image Slicing’s Kiss of Death")

# 明确化

[选择器明确化](http://juicystudio.com/article/selector-specificity.php "Selector Specificity") 是当好几个规则都可以被相同的元素使用时，优先使用哪一个的过程。

简单说来，每个CSS选择器都有 **权重**。选择器的所有权重的总和决定了它在文档中的 **属性**。当CSS文档很大，以至于你不知道元素哪个权重较大时，明确化就能起到很大的帮助。

**进一步阅读：**

- [CSS明确化：你应当知道的几件事](http://www.smashingmagazine.com/2007/07/27/css-specificity-things-you-should-know/ "CSS Specificity: Things You Should Know")
- CSS明确化（已失效）

# 属性重置

全局属性重置确保一个网站在所有浏览器中显示几乎一样。在每一个案例中，不同的浏览器给所有网站使用它们自己的默认样式设置集，这将使我们的网站在不同的浏览器中显示不一样。 **全局属性重置** 将改正这种情况并让你从绝对一致的基础开始建立网站。

我并不总是推荐使用CSS框架，但是CSS重置你还是需要用到的。现在有许多不同的重置方法，从简单的到复杂的。

**进一步阅读：**

- [CSS框架和CSS重置：从零开始学设计](http://www.smashingmagazine.com/2007/09/21/css-frameworks-css-reset-design-from-scratch/ "CSS Frameworks + CSS Reset: Design From Scratch")
- [CSS工具：重置CSS](http://meyerweb.com/eric/tools/css/reset/ "CSS Tools: Reset CSS")
- [使用YUI重置CSS](http://developer.yahoo.com/yui/reset/ "YUI Reset CSS")

# Hacks

即便是一个完美的CSS，它也不能在所有浏览器中产生完全一致的显示，每个浏览器有对CSS不同的解释方法。总而言之，如果你需要你的网站在所有浏览器中保持一致，你不得不使用CSS Hacks。

使用CSS Hacks将减少CSS验证时产生的错误，这一点我同意。要实现这点，一个可选的方法是每个浏览器使用单一不同的CSS文件并通过在HTML中包含判定浏览器的标签来告诉浏览器应该使用哪个特定的CSS。我经常在我所有的项目中创建一个 **"fuck-ie.css"** :) （译者注：此处作者用脏话表达了他对IE的愤怒。如果翻译成“和IE交配.css”，世界会不会和谐一些？）

使用这种方法后，你的“主CSS文件”将通过验证，与此同时，"fuck-ie.css" 文件也会通过验证，但是只在IE浏览器中覆盖“主CSS文件”。

**进一步阅读：**

- [CSS hacks](http://www.webdevout.net/css-hacks "CSS hacks")
- [特定浏览器的CSS Hacks简介](http://www.sitepoint.com/article/browser-specific-css-hacks/ "Introduction to Browser-Specific CSS Hacks")

# 验证

在创建CSS的时候就验证它总是很必要的，浙江确保你的CSS **没有错误** 并且可以被所有浏览器正确地解释。

W3C验证器是一个非常流行的在线CSS验证工具。

如果你有什么更多的技巧想加到本文中，请在文章评论中分享他们，我们希望这能帮到你。
