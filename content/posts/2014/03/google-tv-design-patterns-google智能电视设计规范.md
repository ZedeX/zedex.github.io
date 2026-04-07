---
author: zx
categories:
  - i-internet
  - t-tech
date: "2014-03-02T04:36:25+00:00"
summary: |-
  ![google tv](http://daichuanqing.com/wp-content/uploads/2014/03/google-tv.jpg)

  这是为运行在Google TV 上的Android应用程序所作的用户界面开发准则。虽然运行在手机和Google TV上的安卓应用程序几乎没有不同，但在用户界面上，两者还是有区别。

  电视的观看环境通常被描述为“10英尺环境”，电视屏幕也被描述为“10英尺的用户界面”。当你为10英尺环境创建应用程序时，请记住以下基础概念：

  **从传统上意义来说，10英尺环境适合消费内容**

  - 10英尺环境是娱乐环境，不是工作环境。
  - 10英尺环境通常是一个社会环境，不是单用户环境。

  **10** **英尺用户界面的观看体验是电脑和电视的结合**

  - 电视屏幕兼有电脑和电视的特点。
  - 显示分辨率类似电脑，但受到电视特点的影响。
  - 在TV屏幕上的色彩是不同的。

  **电视设备拥有高品质的声音**

  - 电视设备通常连接到最好的音响系统。
  - 不像电脑，用户期望电视设备发音，并且希望不会被打扰。

  **10** **英尺用户界面需要简单和可见的导航**

  - 建立从左到右、从上到下的导航。
  - 降低对鼠标的要求。
  - 提供可视反馈。

  **基于内容区域的用户界面模式，最适合于10英尺用户界面**

  - 区域本身与设备类型无关。
  - 不同的设备类型有特定的区域安排。
  - 许多不同的用户界面可以基于区域的概念。
tag:
  - google
title: Google TV Design Patterns | Google智能电视设计规范
---
![google tv](http://daichuanqing.com/wp-content/uploads/2014/03/google-tv.jpg)

这是为运行在Google TV 上的Android应用程序所作的用户界面开发准则。虽然运行在手机和Google TV上的安卓应用程序几乎没有不同，但在用户界面上，两者还是有区别。

电视的观看环境通常被描述为“10英尺环境”，电视屏幕也被描述为“10英尺的用户界面”。当你为10英尺环境创建应用程序时，请记住以下基础概念：

**从传统上意义来说，10英尺环境适合消费内容**

- 10英尺环境是娱乐环境，不是工作环境。
- 10英尺环境通常是一个社会环境，不是单用户环境。

**10** **英尺用户界面的观看体验是电脑和电视的结合**

- 电视屏幕兼有电脑和电视的特点。
- 显示分辨率类似电脑，但受到电视特点的影响。
- 在TV屏幕上的色彩是不同的。

**电视设备拥有高品质的声音**

- 电视设备通常连接到最好的音响系统。
- 不像电脑，用户期望电视设备发音，并且希望不会被打扰。

**10** **英尺用户界面需要简单和可见的导航**

- 建立从左到右、从上到下的导航。
- 降低对鼠标的要求。
- 提供可视反馈。

**基于内容区域的用户界面模式，最适合于10英尺用户界面**

- 区域本身与设备类型无关。
- 不同的设备类型有特定的区域安排。
- 许多不同的用户界面可以基于区域的概念。

### 1.十英尺的环境

当你为十英尺环境创建Android应用程序时，你应该牢记一些基本理念。这些基本理念将“十英尺环境”与电脑和移动设备区别开来。

最基本的理念是，在传统意义上，电视设备是用来展示消费性内容的。在很长的一段历史中，电视都作为一种被动接收广播信息的系统。Google TV 将电视从广播系统变为双向交互系统，这对许多观众来说是一个巨大的改变。对老年观众，特别是认为自己是“电脑盲”的人来说，这一改变就有些棘手了。另一方面，与互联网一同成长的年轻观众对这一改变就没有那么大反应，甚至渴望着接触它。

电视在本质上是被动接受，这通常被称为“后仰”体验。即使是愿意与电视互动的观众也不愿意互动得太多。他们想后仰靠在沙发上并享受着互动过程，而不是像用电脑或手机一样要高度集中注意力。

另外，Google TV 旨在提升传统的电视观看体验的目标——可以更轻松，可以一起观看和分享的体验。从这个更传统的方法开始，你能够将你的应用程序与电视屏幕上展示的其他系统区别开。

### 2.电视显示

当你设计你的应用程序时，牢记Google TV 的显示在根本上是与电脑或移动设备不同的。除开它的尺寸大小因素，电视显示出的信息总量比电脑或移动设备的要少。你应该提供更少的UI，可能需要自动化处理某些任务，而不是要求用户去互动。

以下是一些UI设计准则：

1. **使用手机作为UI模型。** 现代电视的尺寸具有欺骗性。尽管现代电视的屏幕对角线通常大于40英寸，成比例地，观众坐在电视前比坐在电脑显示屏前要远。观众感受到的是，电视屏幕尺寸比电脑显示器要小。当你在设计UI时，你可以使用手机作为 “模型”来模拟这种体验。
1. **在页面上的元素之间应该留出更多的空白空间，避免屏幕上杂乱的外观。** 要做到这一点，需要综合使用更大的外边距和内边距。这对“触屏”UI也同样是一个好建议。
1. **电视总是横屏的。** 在电视上，水平方向的可用空间比垂直方向上的可用空间要多。将屏幕上的导航控件水平放置，为内容部分节省下垂直空间。

#### **2.1 高清显示分辨率**

电视屏幕在根本上与电脑显示器与移动设备屏幕不同。显示器和移动设备屏幕直接使用（大体上）可寻址的像素。相较之下，电视使用的是落后十年的显示图像的模拟方式。了解这一不同点，再与Google TV 协同合作是非常重要的。

**2.1.1 电脑和移动设备的显示分辨率**

电脑显示器有一个最大的显示分辨率，这个分辨率通常小于或等于显卡分辨率。显卡决定最大分辨率，显示器决定像素密度（每英寸的像素数量）。移动设备的分辨率和像素密度往往是固定的。

因为对电脑的显示分辨率很简单，根据用户的偏好设置，电脑操作系统能自动处理分辨率和像素密度的问题。

Android系统使用同一套应用程序来运行多种移动设备。为了做到这一点，Android系统根据设备屏幕大小和像素密度来按比例缩放UI。此外，你可以提供可替换的UI资源，为不同设备准备最好的UI体验。

**2.1.2 电视显示分辨率**

电视（即使是最现代化的那些电脑）有基于扫描线的显示分辨率。Google TV 支持3种扫描线值的高清电视：720p，1080i和1080p，这代表720逐行扫描线，1080隔行扫描线和1080逐行扫描线（Android将后两者视作等同）。720值意味着电视可以在屏幕的垂直方向上“寻址”720条不同的线；1080值则意味着电视可以在垂直方向上“寻址”1080条线。

水平分辨率由电视的长宽比来决定。目前几乎所有的电视都使用16：9的长宽比（16个水平像素对应9个垂直像素），所以1080的电视机的分辨率是1920 x 1080。

这些线有多高，每条线之间的“宽”是多少？也就是说电视的实际像素密度是多少？这取决于不同的制造商，但是Android将这些数值抽象显示为与密度无关的像素单位（缩写 dp）。

Google TV Android 应用程序得益于Android的缩放技术。总之，你应该为1080p的规格来设计UI，允许Android系统将你的UI缩小到720p的规格，因为缩小图形的效果通常要优于放大的效果。为了得到最好的图片缩放效果，如果可能的话，给他们提供9-patch格式的图片。Android为Google TV 提供的缩放设置如下表所示。

[![screen](http://daichuanqing.com/wp-content/uploads/2014/03/screen.png)](http://daichuanqing.com/wp-content/uploads/2014/03/screen.png)

**注释：**

- 可寻址的屏幕尺寸是可见的像素数目。
- 密度定义是Android 根据dp来定义的。在 “设计与开发”一章中的“可选资源”一节中有相关描述。要了解更多关于可选资源的信息，可以阅读“Android开发准则”中的“支持多种屏幕”一章。
- 确定当前显示器的屏幕尺寸和分辨率，使用“ [显示单位](https://developers.google.com/tv/android/docs/gtv_displayguide)”中的dpi与屏幕分辨率。

**2.1.3 过扫描**

另一个难题是过扫描。由于历史原因，电视制造商必须在正常屏幕尺寸的外侧预留出空白边，能够被电路寻址，但是不被用来显示电视信号。这些空白区域就是过扫描区域（或者就简称为“过扫描”）。Android应用程序不能在过扫描区域显示。

不幸地是，过扫描也因为制造商的不同而不同。所以围绕你的UI的空白边也多种多样。如果你为一部有显示过扫描的电视设计UI，你也许在不经意间将过扫描区域当作UI和电视边框之间的空白边使用了。如果之后你在一部几乎没有过扫描的电视上运行你的应用程序，UI将几乎没有空白边，这些元素可能很难识别。

为了处理这个问题，为你的UI提供额外的10%的空白边，并使用一个非绝对定位的布局。如图1所示。

[![image1](http://daichuanqing.com/wp-content/uploads/2014/03/image1.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image1.png)

图1 屏幕分辨率和尺寸

#### **2.2 色彩**

与电脑显示器相比，电视屏幕有更高的对比度和饱和度。考虑到这点，在使用纯色的时候要考虑一下准则：

1. 谨慎地使用纯白色（#FFFFFF）。纯白色在电视屏幕上会引起振动或图像重影。用#F1F1F1(hex)或者240/240/240(RGB)来代替使用纯白色。
1. 避免使用明亮的白色系，红色系和橙色系，因为这些颜色在电视上显示会特别严重的失真。
1. 了解不同的电视显示模式，包括标准、锐利、电影/剧场，游戏等等。确保你的应用能适应这些全部的电视模式。
1. 避免使用大面积的色彩渐变，因为它们可能会导致色带。
1. 如果可能，在低质量的显示器上测试你的应用程序。这些设备可能有较差的伽马值和颜色设置。

#### **2.3 文本**

对电视来说，避免纤细字体或者有过宽、过窄笔画的字体。使用简单无衬线字体并选用抗锯齿功能来增加易读性。目前，Google TV只支持Droid Serif 字体族，但是你可以使用嵌入字体来创建一个更个性化的外观。然而，牢记嵌入字体会拖慢系统运行。

以下是一些提高文本易读性的方法：

1. 每个段落限制90个单词。
1. 将长句改为几个短句，让用户可以快速浏览。
1. 在每行保持5-7个单词，不要少于3个单词，也不要多于12个单词。
1. 在电视上，在深色背景上的浅色文字比在浅色背景上的深色文字更容易阅读。
1. 使用Android的标准字体尺寸。例如，标准的小字体字号为14sp，在1080p的屏幕上，这相当于28点的字号。
1. 为屏幕文本设置比印刷文本更大的行间距。

## 3.声音和UI

使用Google TV的电视往往连接着最好的家用扬声系统。不像在电脑上那样，在电视上，声音不被认为是干扰因素，所以设法在你的UI中使用声音。牢记以下几点：

1. 使用适宜起居室环境的声音。
1. 默认一个低的初始值。
1. 假设你的用户在使用你的应用时，他们将会观看电视或听音乐。提供一个简单的方式将你的应用静音。不要完全依赖音频信号来完成交互，而要适量使用。
1. Android 有声音焦点的概念，允许应用程序排外地请求音频的播放。所以，如果你的应用程序中的主要功能依赖于声音（如媒体播放器），你应该请求排外的声音焦点。如果应用程序在后台播放媒体，你应该建立一个声音焦点改变监听器，并且尊重其他应用程序对声音焦点的请求。更多的信息可以 [在这里可以找到](http://developer.android.com/reference/android/media/AudioManager.html)。

## 4.导航设计

Google TV 设备通常包含一个键盘和用来控制光标的定位设备。许多用户在观看电视时，将会把这些设备放在手边。这两种方式可能会组合在一个单独的物理设备里，这个设备还可能包含鼠标。键盘显然是用来输入文本的。指示设备是导航板（D-pad）的一个变体，观众可以用来定位光标或者焦距在某个UI元素上。在键盘或指示设备（或两者兼有）上的附加按钮也许会提供更多的传统遥控功能，如控制开关、回放等等。

如果有鼠标的话，可以通过鼠标在屏幕控制鼠标，点击鼠标下的UI按钮。再次提醒，在传统上，电视是一种广播系统而不是对话系统。用户也许不会有使用方向导航键或者鼠标的经验。即使是有经验的电脑用户也会发现在电视上使用鼠标的困难。

以下是几条在Google TV 的应用中的设计UI 导航的准则：

1. 用方向键导航而不是鼠标导航。用户可能对使用电视遥控器的这种导航方式更加熟悉。
1. 如果你选择使用鼠标导航，要为鼠标提供超大的选择界面。将可点击的按钮做得大大的，这样用户可以更容易地将光标定位在它们上面。
1. 避免复杂或者静谧的鼠标导航。不要使用拖放和下拉菜单。这些在电视环境中很难控制。
1. 为导航提供高度明显的UI反馈。当光标转移到选项界面上，展开或高亮显示导航。使用过渡和移动，为继续或倒退操作提供视觉提示。例如，如果用户选择一项操作后，一个新的页面从右侧滑入，用户也许凭直觉明白，按下方向键盘的左键将会返回到前一页。

你的目标是提供一个导航机制，用户可以通过它很快地知道自己将要去到哪里。

再次提醒各位，电视既不是电脑也不是移动设备。没有触屏，它的鼠标（如果有的话）很难控制。为了模拟用户在使用TV导航时的思维模式，尝试在不使用鼠标的情况下，在运行Android应用的模拟器中使用导航。界面有多直观？做些什么能让它们表现得更好？ **?**

#### **4.1 方向键导航**

方向键控制器将运动限制在上、下、左、右。使用方向键中间的Enter或OK键触发光标所在的操作。

用户需要方向导航键快速简单的交互。牢记用户是在一定距离之外导航，也许还可能是在黑暗中！

当你为方向键导航进行设计时，遵循以下准则：

1. 确保方向箭头按钮可以导航至屏幕上所有可见的控件。
1. 如果你使用某个方向键来滚动一个列表，确保用户能选择在列表中的某个元素，而且某个元素被选择后，这个列表仍然能够滚动。
1. 如果有多个项目在应用程序中被选择，确保用户能清楚得知道自己现在选择的是哪一项。
1. 确保在你的应用程序的任何可以使用方向键盘的UI项目中，提供了全部的“选中”、“聚焦”和“选中并聚集”的状态

了解更多关于方向键导航的信息，请阅读“Google TV Android开发准则”中的“UI 控件准则”一章。

#### **4.2 鼠标导航**

在电视屏幕上，鼠标移动的是一个小而远的光标箭头。因为鼠标控制器本身是触板或轨迹球而不是传统有滑球的鼠标，所以鼠标控制是比较困难的。帮助你的用户使用鼠标：

1. 放大每一个光标可以访问的UI控件（比如链接或按钮），并在控件周围留出足够的空白。
1. 增加一个“hover”状态，当光标经过控件的时候，这个控件外观会发生变化。
1. 使用箭头指示让用户知道在屏幕外有可访问的内容。使用箭头作为控件，点击后转到页面外。 **?**

#### **4.3 导航帮助**

对大多数的用户来说，十英尺环境里的导航是新鲜的。使用帮助按钮或操作栏按钮触发对话框，给他们提供文本帮助。内容覆盖以下这些：

1. 方向导航键：它们可以切换页面吗？他们能打开上下文或导航菜单吗？
1. 返回按钮：它能返回前一页吗？可以撤销上一个动作吗？它可以关闭一个弹出窗口吗？
1. 媒体按键：按下播放/暂停键会如何？按下快进/快退呢？
1. 其它按键：是取消或关闭弹出窗口的按键吗？例如，ESC键能关闭一个弹出窗口吗？

你也许希望在用户第一次使用你的应用时，自动显示帮助对话框。

#### **4.4 垂直滚动**

垂直页面滚动对于桌面浏览器来说是基本的，这种方式在电视中可能就不是那么好用了。滚动可能生涩缓慢，重要的信息可能被隐藏在屏幕之外。因为用户不理解这种滚动是可以持续的。

相反的，使用水平布局，并且提供页面间的视觉过渡。如果要使用垂直滚动，将其范围限制在页面中的细节区域。保持左侧导航栏固定。除此之外，保持上下文易于理解，这将会更好得易于用户理解。

#### **4.5 类别导航**

将类别（你将会放进菜单或标签中的项目）放在屏幕的左侧。在电视上，水平方向的空间比较充裕，但垂直方向上则是有限的。在屏幕上尽量一直保持类别选择，为此你也许不得不去减少类别的数目。如果你要将手机应用移到电视上，考虑重新设计或者至少测试复杂嵌套的、有许多子目录的导航。

#### **4.6 选择**

在电视屏幕上，不容易将光标定位在选项上，为了帮助用户做选择，遵循以下准则：

1. 当光标停留在控件上时（即hover状态），高亮显示选择的控件。
1. 确保可选的控件足够大，并为文本标签留出足够的额外空白边。
1. 不要使用传统的小控件，例如在窗口角落使用“关闭”按钮。这样既可能很难发现，又可能很不容易选择，甚至两者兼有。
1. 避免使用鼠标关闭弹出窗口，举个例子，用户点击窗口之外的地方，PC应用程序就会关闭。这种方式在十英尺环境中是不明显的。相反的，为关闭对话框提供一个清楚明确的控件，并确保方向键盘能访问到它。
1. 不需要用户选择首要控件来激活它，而是要让首要或默认的控件处在激活状态（聚焦其上），并且高亮显示。
1. 如果窗口或对话框的一部分需要滚动，那么自动聚焦其上，或者允许它在没有聚焦的时候可以滚动。让用户在滚动元素之前先点击它是强人所难的做法。

#### **4.7 上下文、选择和焦点**

应用程序的通行状态包括上下文、选择和焦点。上下文通常是一套分类，而选择是用户已经选中的分类。焦点是在光标下的控件或元素。这些控件或元素都应该有与众不同的高亮状态，而且高亮的机制在整个应用程序中应该保持一致。

举个例子，如果是一个都是影片的屏幕上，应用程序提供一行显示不同类别的上下文标签。例如“全部电影”、“最新发行”、“流行”、“编辑推荐”等等。如果用户选择了其中的一个标签，“选中”状态应该在视觉上与正在变动的“聚焦”状态不同，以此来指出当前屏幕导航所在的位置。如图2所示：

[![image2](http://daichuanqing.com/wp-content/uploads/2014/03/image2.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image2.png)

图2 选择与焦点

对Google TV应用程序来说，方向键聚焦状态等同与鼠标hover状态。这是用户理解应用程序状态的主要方式，它可以帮助用户预测出如何移动焦点或进行选择。

#### **4.8 焦点与焦点预期**

就像踩着石头跨过小溪一样，用户考虑如何在那些可以接受聚焦的UI元素间移动，并避开那些不能聚焦的。用与众不同的视觉特征来帮助用户，像在可以聚焦的元素上加上轮廓。区别可聚焦和不可聚焦元素，可以帮助用户了解你的UI。将元素用网格形式排列是帮助用户的另一个方式（如图3）。

![image3](http://daichuanqing.com/wp-content/uploads/2014/03/image3.png)

图3 UI导航的网格模式

对于方向键盘的上、下、左、右控制方式来说，网格是最显而易见的映射。如果不使用网格，元素可能会倾斜，在不同基线上，或在不同的垂直中心线上。这会强迫用户从上到下、从左到右重复切换，或者会让用户感到困惑，不知道如何去移动焦点。

某些元素，像可滚动列表，可能会与网格排列相矛盾（见图4），在这种情况下，你应该尽可能将默认状态下的焦点放在离网格近的地方。

[![image4](http://daichuanqing.com/wp-content/uploads/2014/03/image4.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image4.png)

图4 可滚动排列与网格布局

#### **4.9 视觉指示**

为界面中可选择、可导航的项目添加指示或高亮状态，是一个好做法。这种做可以启示用户。期望用户探索界面，自己摸索什么是可选择，什么是不可选择的做法是不可取的。假设UI是直觉上就可以知道的想法也同样不可接受。应该仔细标注、解析UI来获得用户的认可与忠诚。

#### **4.10 过渡**

应用程序中使用过渡能启发用户，但也可能会把他们搞糊涂。确保过渡能够传达某种含义，而不仅仅是提供视觉愉悦。以下是一些准则：

1. 避免重载整个页面，因为这会引起最强烈的延迟感受。
1. 对于只影响一个片段的任何操作，过渡应该处于这个片段内。
1. 确保进度信息是有意义和明确的，动画图像应该能指示出完成了多少进度，还有多少工作未完成。
1. 不要为网格中的每一个元素显示loading动画。在网格中的12个项目都在加载动画，杂乱的界面会让用户难以浏览。

### 5.用户界面设计

当你设计用户界面，牢记以下准则：

1. 保持设计的一致性。
1. 保持元素行为的一致性。
1. 保持所有重要的操作和选项可见，包括搜索、设置、返回等等。在十英尺环境中，不可见的元素容易被记住，即便它们是在屏幕以外或者在遥控器上。

#### **5.1 跨设备的UI**

你有一个移动设备上的应用程序，并且你想将它转移到10英尺环境中。如何将1英尺的UI 转换为10英尺的UI？记住，最重要的是，更大未必是更好的。平板比智能手机好，电脑比平板好，但是电视要比电脑好吗？

[![image5](http://daichuanqing.com/wp-content/uploads/2014/03/image5.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image5.png)

图5 屏幕尺寸比较

你可能认为42”屏幕是最强大的，但是情况并非如此。智能手机通常比电视有更强的处理能力。电视中的高清视频和音频是预先渲染的，所以电视所需要的只是与广播源中的高宽带连接。换句话说，大多数电视的信息处理工作是由广播源完成的，而不是电视本身。

考虑到这点，编写应用程序要将用户界面最小化，为用户考虑越多越好。

## 6.区域和模式

实现优秀电视UI的最简单的方法是去使用区域和模式的结构。将两者结合，它们能强调出一种由UI元素视觉语言建立的清晰和简洁的体验。

#### **6.1 区域**

区域是Google TV UI中用来浏览内容的基本部分。每个区域对应一个Android Activity组件。对于Google TV来说，区域使用了从左到右的层级而不是像手机和电脑UI一样从上到下的层级。这是因为电视屏幕是水平方向的，便于反映前面提到的简单导航。

[![image6](http://daichuanqing.com/wp-content/uploads/2014/03/image6.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image6.png)

图6 应用中的区域

电视屏幕包含从左到右的三个区域（如图6），你可以调整它们的尺寸来适应应用程序的要求，或者你能简单得使用它们的默认尺寸。

因为全局区域在应用程序中始终保留着，所以不应该让这部分占用太多屏幕控件。相比之下，细节区域包含了用户想要看的内容，所以你应该尽可能得给这个区域留出足够大的空间。最后，让上下文区域的尺寸居中显示，既能显示当前选择，也能显示没有限制的细节。

#### **6.2 区域样例**

图7 是一个基于区域的UI样例，图8 显示了区域本身。

[![image7](http://daichuanqing.com/wp-content/uploads/2014/03/image7.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image7.png)

图7 应用程序例子

#### 6.3 全局区域

全局区域（图8中的区域1）处于屏幕的最左边。这个区域包含了应用程序层级中所有的顶级“全局”项目。它提供了快速访问的操作，用户可以在任何地方使用应用程序。这个区域也包含了应用程序的全部分类，以及应用程序的logo。在全局区域中的选择，会相应得改变右侧区域中的显示内容——不管是上下文还是详情区域，这取决于应用程序的层次深度。

![image8](http://daichuanqing.com/wp-content/uploads/2014/03/image81.png)

图8 示例应用程序中的区域

#### 6.4 上下文区域

上下文区域（在图8 中的区域2）位于全局区域的右侧，这里显示上下文详情或是选项。除了上下文的详情外，上下文区域也可以包含次级模式，像分页、菜单，筛选器等等，用户可以在这个中间层级执行具体操作。这个区域是可选的。

#### 6.5 详细区域

详细区域（图8中的区域3）在最右侧显示。详细区域通常是最大的区域，显示应用程序的内容。与上下文区域一样，详细区域可以包含不同的次级模式，包括内容展架、情节/分集浏览，列表等等。

下图展示了电视、平板和手机的区域与模式的样例：

[![tv_zones](http://daichuanqing.com/wp-content/uploads/2014/03/tv_zones.png)](http://daichuanqing.com/wp-content/uploads/2014/03/tv_zones.png)

图9 电视区域? [![tv_patterns](http://daichuanqing.com/wp-content/uploads/2014/03/tv_patterns.png)](http://daichuanqing.com/wp-content/uploads/2014/03/tv_patterns.png)

图10 电视模式

[![tablet_zones](http://daichuanqing.com/wp-content/uploads/2014/03/tablet_zones.png)](http://daichuanqing.com/wp-content/uploads/2014/03/tablet_zones.png)

图11 平板区域

[![tablet_patterns](http://daichuanqing.com/wp-content/uploads/2014/03/tablet_patterns.png)](http://daichuanqing.com/wp-content/uploads/2014/03/tablet_patterns.png)

图12 平板模式

[![phone_zones](http://daichuanqing.com/wp-content/uploads/2014/03/phone_zones.png)](http://daichuanqing.com/wp-content/uploads/2014/03/phone_zones.png)

图13 手机区域

[![phone_patterns](http://daichuanqing.com/wp-content/uploads/2014/03/phone_patterns.png)](http://daichuanqing.com/wp-content/uploads/2014/03/phone_patterns.png)

图14 手机模式

#### **6.5 模式（片段）**

模式是区域的次级结构，它包含UI控件与显示内容。通常情况下，将一个独立的模式实现为一个Android片段。Android提供UI布局和小部件帮助开发者实现许多应用程序的基本需求。图15 显示了一些Google TV区域系统中的模式：

[![image9](http://daichuanqing.com/wp-content/uploads/2014/03/image91.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image91.png)

图15 模式和区域

Android提供的模式模版包括左侧标签栏、菜单、列表、筛选器、分页等等。Google TV模式与其他设备上为人所熟悉的模式表现一致，这样你就可以重复使用。如果你在手机应用程序中有一个列表，你可以将同样的列表放入到Google TV UI中适合的区域中。这种方式简化并且加速了应用程序的转移。甚至更好，Android默认将模式尺寸放大到适应10英尺的环境。对于熟悉应用的用户来说，这些模式是容易识别的。

#### **6.6 基本模式**

内容展架 [![image12](http://daichuanqing.com/wp-content/uploads/2014/03/image12.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image12.png)

内容网格 [![image13](http://daichuanqing.com/wp-content/uploads/2014/03/image13.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image13.png)

内容列表 [![image14](http://daichuanqing.com/wp-content/uploads/2014/03/image14.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image14.png)

级联式内容列表![image15](http://daichuanqing.com/wp-content/uploads/2014/03/image15.png)

细节展开?![image16](http://daichuanqing.com/wp-content/uploads/2014/03/image16.png)

二级标签页 [![image17](http://daichuanqing.com/wp-content/uploads/2014/03/image171.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image171.png)

### **7.排序与筛选**

用户需要排序与筛选列表内容，你需要在你的用户界面中提供这些便利。在电脑或触摸屏上，开发者通常要在列表左上方或屏幕的左侧的下拉菜单来提供这些选项。在十英尺环境中考虑实现UI，要牢记方向键盘的局限性。

在图16中，橙色区域表示控制排序和筛选下方列表的模式。注意，在最小化状态下，标签和被选中项目都清晰地传达给了用户。? [![image21](http://daichuanqing.com/wp-content/uploads/2014/03/image21.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image21.png)

图16 排序和筛选模式

当用户将焦点移动到区域中，它将会展开（图17）显示全部可用选项，并且也显示出当前选中的项目。 [![image22](http://daichuanqing.com/wp-content/uploads/2014/03/image22.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image22.png)

图17 排序和筛选模式，展开状态

如果列表包含排序和筛选选项，你可以需要更多的选项列表。图18 和图19 显示了排序和筛选模式的多选项版本，包括最小化和展开状态。 [![image23](http://daichuanqing.com/wp-content/uploads/2014/03/image23.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image23.png)

图18 多选项版本，最小化 [![image24](http://daichuanqing.com/wp-content/uploads/2014/03/image24.png)](http://daichuanqing.com/wp-content/uploads/2014/03/image24.png)

图19 多选项列表，展开状态

注意，展开视图演示了各种选择项并将选项高亮显示的多种方法。

标签A的选项被选中时，字体会加粗。如果标签B被选择，文本就会显示“全部选项”。标签C使用复选框来指示哪个选项被选中。标签D显示的则是没有任何选项被选中时的效果。

如果可能的话，用户选择选项时，应该更新列表。这给用户提供了有用的反馈，并且应用程序的反应也会更加灵敏。这不需要一个特定的“确认筛选”按钮，也避免了全屏幕的刷新。记住，当用户返回到左侧栏或向表格下方导航时，应该再次最小化选项，并显示当前被选中的项目。

**方向导航键的交互陷阱**

方向导航键盘与UI模式的交互，更加强调了左右层级的优势。在更好的绿色样例（图20）中，划分了三个区域：全局、列表和确认内容。当用户从分类到确认内容逐步缩小选择时，他们是从左到右移动焦点。任何区域内的导航被限制在上下方向。这样就很容易在长列表中选择项目并确认选择。

![image25](http://daichuanqing.com/wp-content/uploads/2014/03/image25.png)

图20 一个令人向往的区域与模式组织方式

在不令人期待的红色样例（图21）中，层次结构保持不便，但变为垂直排列。用户使用导航在区域间上下移动。区域内导航并不是一致的，在顶部和底部区域内是左右导航，但是在中间区域内的确是上下导航。

在触屏设备上，这个布局是比较容易掌握的，因为用户能抬起手指，在区域间内跳跃点击。然而，在方向导航的设备上，用户不能在区域间跳跃操作。如果用户想要从全局区域的顶部到底部的确认按钮，他们必须滚过中间列表的每一项。如果列表包含了50个项目的话，这得是多大的负担！使用从左到右的层级列表来防止这个陷阱。

![image26](http://daichuanqing.com/wp-content/uploads/2014/03/image26.png)

图21 令人不悦的区域和模式布局

### 8.UI 性能

大量的调研显示，用户更喜欢运行速度更快的应用程序，所以你应该在视觉表现和运行速度之间做平衡。同样的，电视设备之间的运算能力相差较大，所以它们可能不如在工作站中那样渲染迅速。在为应用设计大量复杂的动画之前，考虑并测试用户满意度方面的影响。

应用程序表现得是否良好，用户才是最终的评判者。

在开发应用程序的过程中，某些操作需要多少时间，在Android测试工具中要使用多少个实例对象，以此来测试应用程序的性能表现。尽管如此，还是要记得，这些指标对最终用户来说并不是至关重要的，因为他们的评价标准是不同的。

举个例子，用户可能通过应用程序的操作是否快捷和流畅，对输入的反馈是否及时来判断应用程序的性能。如果应用程序拖慢了Google TV中的其他应用，用户可能就不喜欢这个应用了。这些反应就是用户对应用程序性能的感受。对应用程序的感受如何，才是用户评价的最重要指标。

实现最佳性能感受的途径，并不总是获得与绝对意义上最快性能的途径一样。确保应用程序不要执行太多代码，避免运行时不能频繁得刷新屏幕并且获取用户输入。在某些情况下，为了取得平衡——将一个项目划分为多个部分，这样在运行时屏幕可以刷新各个部分。

以下是一些你应该考虑的性能问题：

1. 应用程序启动迅速吗？
1. 应用程序的动画是流畅还是卡顿？
1. 视频内容是流畅的还是卡顿的？
1. 音频片段是持续播放的，还是能暂停再继续播放？
1. 当一个长时间运行的操作正在进行时，窗口会闪烁还是会变成空白？
1. 当你在应用程序中键入文字时，输入文字是紧随输入还是落后显示？
1. 点击之后的反馈及时吗，还是有所延误？
1. 当你的应用在运行时，其他应用会反应延迟吗？

## 9.附加提示

成功的TV UI 在概念和设计上是简单的。要制作易于理解和使用的UI，牢记以下提示：

**在开始工作时，确定你的界面中什么才是重要的。**

- 根据优先级组织内容、控件和交互行为。
- 抛弃所有不需要的元素。

**只使用一种视觉导航模式或是一种信息层级。**

- 引导用户适应所有UI的心理模型。
- 依赖用户从浏览器或应用中学习到的使用习惯。

**一键访问最重要的操作。**

- 突出显示屏幕上的其它操作，不要隐藏菜单中的关键特性。
- 关键功能应该只有几个。
- 总是为用户显示返回到之前页面的简单方式。不要依赖后退按钮。

**当能做到的时候，预计用户的下一步操作，为用户做出选择。**

- 例如，将光标移动到下一个输入框，或者是默认选中列表中的第一项。

**避免使用抽象图标**

- 使用简单、明确的标签。

**限制垂直滚动**

- 设想当你的内容尺寸增加时，你的内容如何缩放。如果一个列表变得10倍长呢？
- 如果必须要滚动，应该确保最下方的部分在屏幕上总是可见的。

**使用窗口小部件**

- 窗口小部件是一组有限的应用程序功能，用户可以从主界面中链接到应用程序。
- 将它们作为信息快捷键。例如，使用时钟小部件来显示时间。
- “Android开发指南”介绍了应用程序部件的设计和编码。

**使用Android的图标设计准则。**

- 图标通过UI来帮助用户。
- Android的图标设计界面准则确保你的UI能在现在还是将来都很运行良好。
- 你可以自定义应用程序的任何部分，包括图标，但是将来发布的Android系统可能与自定义部分表现不一致。

更多关于图标的信息，参考Android开发者指南

# Google TV Design Patterns

1. [The 10ft Environment](#Environment)
1. [TV Displays](#Display)
1. [Sound and the UI](#Sound)
1. Navigation Design
1. User Interface Design
1. UI Zones and Patterns
1. UI Performance
1. [Additional Tips](#Tips)

This is a guide to developing user interfaces for Android applications running on Google TV. Although there are few internal differences between an Android application for a phone and one for Google TV, there are differences in the user interface.

The viewing environment of a television is commonly referred to as the? **ten foot (10ft) environment**?and the television screen as the? **10ft UI**. When you create apps for the 10ft environment, remember these basic concepts:

- **The 10ft environment is traditionally for consuming content.**
  - The 10ft environment is a fun environment, not a work environment.
  - The 10ft environment is usually a social environment, not a single-user environment.
- **The viewing experience for a 10ft UI is a mix of computer and TV.**
  - TV screens have both computer-like and TV-like characteristics
  - Display resolution is computer-like, but is affected by TV characteristics.
  - Color is different on TV screens.
- **TVs have high-quality sound.**
  - TVs are usually connected to the best sound system.
  - Unlike computers, users expect sound from a TV and don't find it disruptive.
- **The 10ft UI requires simple and visible navigation tools.**
  - Set up navigation to progress from left to right and top to bottom.
  - Limit the need for a mouse.
  - Provide visual feedback.
- **The 10ft UI works best with well-established UI patterns based on content zones.**
  - Zones themselves are independent of device types.
  - The arrangement of zones are particular to device types.
  - Many different UIs can be based on the zone concept.

Read about each of these concepts (and more) in the following sections.

## The 10ft Environment

When you create Android applications for the 10ft environment you should remember some basic ideas that differentiate this environment from computers or mobile devices.

The most fundamental idea is that the television has traditionally been for consuming content. It has a long history as a passive system for broadly sending information to people; that is, it's a broadcast system. Google TV changes television from a broadcast to a interactive two-way system, and this is a big change for many viewers. Changes like this can be tough for older viewers, especially those who classify themselves as "computer illiterate". On the other hand, younger viewers who have grown up with the Internet have little difficulty with the change, and may even be eager to accept it.

The idea that TV is fundamentally passive is part of what is commonly called the "lean-back" experience. Even viewers who are willing to interact with their TV don't want to work too hard during the interaction; they want to lean back and enjoy themselves. They don't want the highly-involved experience of computers or smart phones.

In addition, Google TV is aimed at enhancing the traditional relaxed, group, shared experience of TV viewing. You'll be able to differentiate your application from other systems that display on TV screens by working with this more traditional approach.

## TV Displays

When you're designing your application, remember that Google TV display is fundamentally different from that of a computer or mobile device. Despite its size, it displays less information overall than for a computer or mobile UI. You'll need to provide less UI, and you may want to automate some tasks instead of asking for user interaction.

Here are some guidelines for your UI design:

1. **Use a mobile phone as the model for the UI.** A modern TV's size is deceptive. Even though modern TVs are usually larger than 40" diagonally, viewers sit proportionally farther from them than from a computer monitor, The viewer's perception is that the TV is smaller than a monitor. To simulate this experience, use a mobile phone as your "model" when you design your UI.
1. **To avoid a cluttered appearance on the screen, provide more blank space between elements on the page.** To do this, use a combination of larger margins and more padding. This is good advice for "touch" UIs as well.
1. **TVs are always in "landscape".** On a TV, available space runs left-to-right rather than top-to-bottom. Put on-screen navigational controls on the left or right side of the screen and save vertical space for content.

### High-Definition Display Resolutions

TVs are fundamentally different from computer monitors or mobile device screens. Monitors and mobile screens use (in essence) directly addressable pixels. TVs, in contrast, use a system based on the decades-old analog method of displaying a picture. Knowing the difference is important in working with Google TV.

#### Computer and mobile device display resolution

A computer monitor has a maximum display resolution that is usually less than or equal to the resolution of the graphics card; it's the graphics card that determines the maximum resolution and the monitor that determines the number of pixels per inch (the pixel density). A mobile device's resolution and pixel density are usually fixed.

Since display resolution for computers is simple, computer operating systems handle resolution and pixel density issues automatically, based on the user's resolution preferences.

Android is designed to handle many types of mobile devices with the same application. To do this, Android scales the UI based on a device's screen size and pixel density. In addition, you can provide alternative resources for your UI to provide the best UI experience for different devices.

#### TV display resolution

TVs (even the most modern ones) have a display resolution based on scan lines. There are three scan line values available for the HD TV displays supported by Google TV: 720p, 1080i, and 1080p, which stand for 720 progressive scan lines, 1080 interlaced scan lines, and 1080 progressive scan lines (the last two are equivalent to Android). The 720 value means that the TV can "address" 720 distinct lines from the top to the bottom of the screen; 1080 means that the TV addresses 1080 lines from top to bottom.

The horizontal resolution is derived from the TV's aspect ratio. Nearly all TVs now use an aspect ratio of 16:9 (16 horizontal pixels for every 9 vertical ones), so the resulting display resolution for a TV set to 1080 is 1920 x 1080.

How "tall" the lines are, and how "wide" each line is (the actual pixel density) for TVs varies by manufacturer, but Android abstracts the values to a density-independent pixel measurement (abbreviated? `dp`).

Google TV Android applications benefit from Android's scaling technology. In general, you should design your UI for 1080p, and then allow Android to scale your UI down to handle 720p, since downscaling (removing information) is usually better than upscaling (interpolating information). To get the best scaling results for images, provide them as 9-patch image elements if possible. The scaling settings that Android uses for Google TV are listed in? [table 1](#table1).

Table 1. Settings used by Android for Google TV UIs

TV settingAddressable screen size (in pixels)Density identifierscreen density (in? `dp`)Display resolution (in `dp`)Screen size identifier720p1280 x 720 px`tvdpi`213960 x 540`large`1080p1920 x 1080 px`xhdpi`320960 x 540`large`

**Notes:**

- Addressable screen size is the number of pixels visible.
- The density identifier is the Android identifier for the number of density-independent pixels ( `dp`). This is described in the section "Alternative resources" in the topicDesigning and Developing. You can also read more about alternative resources in the topic? [Supporting Multiple Screens](http://developer.android.com/guide/practices/screens_support.html)?in the? [Android Developers Guide](http://developer.android.com/).
- To determine the screen size and resolution for the current display, use the dpi and screen resolution from the? `DisplayMetrics`?object.

To learn more about display resolution and Google TV, please read the topic? [Display Guidelines](https://developers.google.com/tv/android/docs/gtv_displayguide)?in the?Google TV Android Developer's Guide.

#### Overscan

An additional complication is overscan. For historical reasons, TV manufacturers must set aside margins along the outside of the normal screen size that are addressable by the circuitry but are not used to display the TV signal. These margins are the overscan area (or simply "overscan"). Android applications can't display in the overscan.

Unfortunately, the amount of overscan varies by manufacturer, so the margin around your UI also varies. If you design your UI for a TV that has significant overscan, you may inadvertently use the overscan as a margin between your UI and the TV's bezel. If you then run your application on a TV with almost no overscan, the UI will have almost no margin, and its elements may be hard to read.

To handle this, provide an extra 10% margin for your UI, and use a Layout that does not use absolute positioning. The diagram in?figure 1?demonstrates this.

![](https://developers.google.com/tv/android/images/image1.png)

**Figure 1. Screen resolutions and dimensions**

### Color

TV screens have higher contrast and saturation levels than computer monitors. To account for this, follow these guidelines when working with solid colors:

1. Use pure white ( `#FFFFFF`) sparingly. Pure whites cause vibrancy or image ghosting in TV displays. Instead use? `#F1F1F1`?(hex) or? `240`/ `240`/ `240`?(RGB).
1. Avoid bright whites, reds, and oranges, because they cause particularly bad distortion.
1. Be aware of various display modes that TVs may have, including Standard, Vivid, Cinema/Theater, Game, and so forth. Be sure to test your application in all these modes.
1. Avoid using large spanning gradients, because they may result in banding.
1. If possible, test your application on lower quality displays which may have poor gamma and color settings.

### Text

For TV, avoid lightweight fonts or fonts that have both very narrow and very broad strokes. Use simple sans-serif fonts and use anti-aliasing to increase readability. Currently, Google TV only supports the Droid Sans and Droid Serif font families, but you can use font embedding to create a more customized appearance. However, remember that font embedding slows system performance.

Here are some ways to improve the readability of your text:

1. Limit each paragraph to no more than 90 words.
1. Break text into small chunks that users can quickly scan.
1. Keep line lengths around 5 to 7 words per line. Never go shorter than 3 or longer than 12.
1. Light text on a dark background is slightly easier to read on a TV, compared to dark text on a light background.
1. Use Android's standard font sizes. For example, the standard? `small`?font size is? `14sp`, which results in 28 point text on a 1080p screen.
1. Use larger vertical line spacing (more leading) for onscreen text than you would for print text.

## Sound and the UI

The TV used with Google TV will often be connected to the best speakers in the household. Sound is not disruptive on TV, as it often is on a computer, so think of ways to use sound in your UI. Keep in mind:

1. Use sounds that are appropriate to a living room environment.
1. Default to a low volume.
1. Assume that your users will be watching TV or listening to music as they use your application. Provide a simple way to mute your application. Don't make interactions entirely dependent on audio cues, and use cues in moderation.
1. Android has the concept of Audio Focus, which allows applications to request exclusive access to playback of audio. So if you primary function of your application depends on Audio (e.g. media player) you should request exclusive Audio Focus, and if you application plays back media in a background service, you should implement an AudioFocusChangeListener and respect other applications requests for Audio Focus. More information can be found? [here](http://developer.android.com/reference/android/media/AudioManager.html).

## Navigation Design

Google TV devices always include a keyboard and a pointing device that controls the cursor. Many users will have these next to them as they view TV. The two may be combined into a single physical device, and this device may also include a mouse controller. The keyboard is obviously provided for text input. The pointing device is a variation of a directional pad (D-pad) that a viewer uses to position the cursor or highlight a UI element. Additional buttons on the keyboard or pointing device (or both) may be provided for more traditional remote control functions such as controlling power, playback, and so forth. If a mouse controller is present, it controls a mouse pointer on the screen and provides buttons for "clicking" the UI under the mouse pointer. Remember again that TV is traditionally a broadcast rather than a conversational system. Your users may not have much practice using a D-pad or cursor. Even experienced computer users will find that using a mouse on a TV is difficult.

Here are some guidelines for designing UI navigation in Google TV Android apps:

1. Depend on D-pad navigation instead of mouse navigation. Users will probably be more familiar with this type of navigation from using it on a TV remote.
1. If you choose to use mouse navigation, use over-large selection surfaces for the mouse. Make clickable buttons big, so that users can easily position the mouser pointer over them.
1. Avoid complex or precise mouse navigation. Don't use drag-and-drop or drop-down menus. These are very hard to control in the TV environment.
1. Provide highly obvious UI feedback to navigation. Expand a selection surface when it receives focus, or highlight it. Use transitions and movements that provide visual cues for proceeding or reversing the action. For example, if the user selects an action that causes a new page to slide in from the right, they may intuitively understand that pressing D-Pad Left will return them to the previous page.

Your goal is to provide a navigation scheme in which the user can quickly learn to predict how to move.

Remember again, a TV is neither a computer nor a mobile device. It does not have a touchscreen, and its mouse (if it has one) is hard to control. To stimulate your thinking about TV navigation, try navigating in a computer application without using the mouse, or in an Android application running on the emulator. How intuitive were the interfaces? What would you do to make them better?

### D-pad navigation

The D-pad controller limits movement to up, down, left, and right. Action under the cursor is triggered by an Enter or OK button in the center of the D-pad.

Users need D-pad interactions that are fast and easy. Remember that users are navigating at a distance, and perhaps in the dark!

When you design navigation for D-pad, follow these guidelines:

1. Ensure that the arrow keys can navigate to all the visible controls on the screen.
1. If you use an arrow key to scroll a list, ensure that users can select an element in the list and that the list still scrolls when an element is selected.
1. If there is multiple items to be selected in your application make sure it is always clear which item is currently selected.
1. Make sure you provide all "selected", "focused" and "selected AND focused" states for any D-pad navigable items in your applications UI.? [Learn More](http://developer.android.com/guide/topics/resources/drawable-resource.html#State). List

To learn more about D-pad navigation, please read the topic?UI Controls Guidelines?in the?Google TV Android Developers Guide.

### Mouse navigation

On a TV screen, the mouse moves a pointer arrow that is small and distant. Mouse control is also difficult because the control itself is usually a pad or ball rather than a traditional mouse "puck". To assist your users with the mouse:

1. Enlarge each UI control that is a mouse pointer target (such as a link or button), and provide ample padding within the control.
1. Add a hover state to controls that changes their appearance when the mouse cursor is over them.
1. Use arrow indicators to make users aware that content is available off-screen. Use the arrows as controls that move to the off-screen content when clicked.

### Navigation assistance

Navigation in a 10ft environment will be new to most of your users. Provide them with written help, using a dialog triggered by a help button or action bar icon. Some topics to cover are:

1. The D-pad arrow keys: Do they move between pages? Can they open context or navigation menus?
1. The Back button: Does it move to a previous page? Can it undo an action? Does it close a pop-up?
1. Media keys: What does play/pause do? What do skip forward and skip backward do?
1. Other keys: Are there keys for Cancel or for closing a pop-up? For example, does ESC close a pop-up dialog?

You may want to display the help dialog automatically when a user starts your application for the first time.

### Vertical scrolling

Vertical page scrolling, while fundamental on a desktop browser, may not be as appealing on a TV. Scrolling may be jerky and slow, and important information may be hidden off-screen because users don't understand that the scrolling can continue.

Use horizontal layouts instead, and provide visual transitions between pages. If you use vertical scrolling, limit it to your detail area in the center of the page, while leaving your left navigation bar stationary. Besides keeping an understandable context, this will have better perceived performance.

### Category navigation

For categories (items you would put in a menu or tabs), use the left side of the screen. On a TV, screen space is plentiful on the sides, but vertical space is precious. Try to keep the category selection on-screen at all times. You may have to reduce the number of categories to do this. If you are migrating an existing phone application to TV, consider reworking or at least testing complicated nested navigation that uses many subcategories.

### Selection

On a TV, positioning the cursor for selection can be inexact. To help the user make selections, follow these guidelines:

1. Highlight selection controls when the selection pointer is over them (a "hover state").
1. Make selection controls large and provide extra padding around the text label.
1. Don't use inherently small controls such as "close" boxes in a window corner. These are either impossible to see or very difficult to select, or both.
1. Avoid using mouse clicks to close pop-up dialogs. For example, PC applications often close a dialog when the user clicks elsewhere; this is not obvious in the 10ft environment. Instead, provide an explicit control for closing the dialog, and ensure that D-pad navigation can access it.
1. Don't require the user to select the primary control to make it active. Make the primary or default control active (give it focus) and highlight it to indicate this.
1. If part of the window or dialog requires scrolling, give it focus or allow it to be scrolled without having focus. Requiring the user to click on an element before scrolling it is obtrusive.

### Context, selection, and focus

The current state of an application includes a context, a selection, and a focus. The context is usually a set of categories, while the selection is the category the user has selected. The focus is control or element "under" the pointer. Each of these should have its own distinctive highlight, and the highlighting scheme should remain consistent across the application.

For example, if a user is looking at a screen full of movies, the application can provide a row of contextual tabs that offer different categories such as "All Movies", "New Releases", "Popular", "Editor's Picks", and so forth. If a user selects one of the tabs, the selected state of that tab should remain visually distinct from the moving focus state that indicates the current screen position for navigation, as demonstrated in?figure 2:

![](https://developers.google.com/tv/android/images/image2.png)

**Figure 2. Selection and focus**

For a Google TV application, D-pad focus is equivalent to mouse hover state. It is the primary way that users see the application state, and it helps users predict how they should move the focus or make a selection.

### Focus and focus prediction

Like hopping stones to cross a stream, a user must think about moving along UI elements that accept focus and avoiding those that can't. One way to help users in this task is to give distinctive visual treatments such as outline boxes to focusable elements (also demonstrated in?figure 2). Distinguishing between focusable elements and those that can't get focus is one way you can help your user understand your UI. Another way to help users is to align elements to a grid ( [figure 3](#figure3)).

![](https://developers.google.com/tv/android/images/image3.png)

**Figure 3. Grid pattern for UI navigation**

A grid is the most obvious mapping to a D-pad's Up-Down-Left-Right controls. If you don't use a grid, then your elements could align diagonally or on different baselines or on different vertical centers. This either forces the user to switch repeatedly from up-down to left-right, or leaves the user confused about the proper move to make.

Some elements such as scrolling lists may defy exact grid alignment (see? [figure 4](#figure4)). In this case, you should try to make the default focus as close to a grid as possible.

![](https://developers.google.com/tv/android/images/image4.png)

**Figure 4. Scrolling alignment and grid layout**

### Visual indicators

It's good practice to add indicators or highlights to selectable and navigable items in your UI. These are called? **affordances**. Expecting users to "explore" the UI to find what is and is not selectable is not acceptable, nor is the assumption that your UI is "intuitive". You build user acceptance and loyalty with a UI that is carefully marked out and explained.

### Transitions

Transitions in your application can either educate or confuse your user. Ensure that your transitions convey meaning rather than simply provide entertainment. Here are some guidelines:

1. Avoid reloading the entire page, because it causes the largest perceived latency.
1. For any action that affects only a? `Fragment`, keep the transition entirely within the? `Fragment`.
1. Make "progress" messages meaningful and specific. Animated images should indicate how much progress has been made, and how much work is left to do.
1. Don't show a "loading" animation for every element in a grid. Doing this for every item in a grid of 12 items results in a cluttered UI that users find hard to watch.

## User Interface Design

When you design your UI, remember the following guidelines:

1. Keep the design consistent.
1. Keep element behavior consistent.
1. Keep all the important actions and options visible, including search, settings, back, and so forth. In the 10ft environment, elements that are not visible are forgotten, even if they're in an off-screen part of the UI or on the remote.

To assist you, Android offers a large set of standard UI controls and several ways of customizing them with a consistent theme.

### UIs across devices

You have an Android application for mobile devices that you want to migrate to the 10ft environment. How do you convert a 1ft UI to a 10ft UI? Remember, above all, that bigger is not always better. Tablets are better than smart phones, and computers are better than tablets, but are TVs better than computers?

**Figure 5: Comparative screen sizes**

You may assume that the 42" screen is the most capable, but this is not the case. A smart phone usually has more processing power than a TV. The HD video and audio coming from a TV is pre-rendered, so all it needs is a high-bandwidth connection to the broadcast source. In other words, most of the processing for normal TV is done by the broadcaster, not by the TV set.

To accommodate this, write applications that minimize user interaction. The more your app does for the user, the better.

## UI Zones and Patterns

The easiest way to make a good TV UI is to use a structure of zones and patterns. Together, they emphasize a clean and concise experience built from a visual "vocabulary" of UI elements.

### Zones

Zones are a fundamental part of a Google TV UI for browsing content. Each zone corresponds to an Android? `Activity`?component. For Google TV, zones use a left-to-right hierarchy instead of the top-to-bottom hierarchy of phone and computer UIs. This reflects a TV's horizontal screen aspect as well as the need for simple navigation noted previously.

![](https://developers.google.com/tv/android/images/image6.png)

**Figure 6. Application zones**

A TV screen contains three zones ( [figure 6](#figure6)) that progress hierarchically from left to right. You can adjust their size to match your application needs, or you can simply use their default sizes.

Because the global zone persists throughout the life of the application, you should not allow it to take up too much screen space. In contrast, the detail zone contains the material that users want to see, so you should give it as much screen space as possible. Finally, make the contextual zone an intermediate size that best holds options for the current display without restricting the detail.

### Zone example

[Figure 7](#figure7)?is an example of a UI based on zones, and? [figure 8](#figure8)?shows the zones themselves.

![](https://developers.google.com/tv/android/images/image7.png)

**Figure 7. Example application.**

#### Global Zone

The global zone (area 1 in? [figure 8](#figure8)) is the leftmost on the screen. This zone holds all of the top-level "global" items in your application hierarchy. It provides gives quick access to operations that users might want to use from anywhere in your application. It also contains all the categories for your application and your application's logo. A selection in the global zone changes the content to the right of it in the either the contextual zone or the detail zone, depending on the depth of your hierarchy.

![](https://developers.google.com/tv/android/images/image8.png)

**Figure 8. Zones in the example application**

#### Contextual Zone

The contextual zone (area 2 in? [figure 8](#figure8)) is to the right of the global zone in cases where you want context-based details or options. In addition to the details that identify context, the contextual zone can contain sub-patterns such as pagination, menus, filters, and so forth that allow your users to take specific action at this intermediate level. This zone is optional.

#### Detail Zone

The detail zone (area 3 in? [figure 8](#figure8)) is rightmost. It is usually the largest zone, and displays your application's content. Like the contextual zone, the detail zone can contain different sub-patterns, including content shelves, episode browsers, lists, and so forth.

The following images show examples of zones and patterns for TVs, tablets, and phones:

![](https://developers.google.com/tv/android/images/tv_zones.png)

**Figure 9. TV Zones**

![](https://developers.google.com/tv/android/images/tv_patterns.png)

**Figure 10. TV Patterns**

![](https://developers.google.com/tv/android/images/tablet_zones.png)

**Figure 11. Tablet Zones**

**Figure 12. Tablet Patterns**

**Figure 13. Phone zones**

![](https://developers.google.com/tv/android/images/phone_patterns.png)

**Figure 14. Phone patterns**

### Patterns (Fragments)

Patterns are sub-structures of zones that containing UI controls and displays. Typically, you implement an individual pattern as an Android? [Fragment](http://developer.android.com/reference/android/app/Fragment.html). Android provides UI layouts and widgets that help you implement many of the basic needs of applications.? [Figure 15](#figure15)?shows some patterns within the Google TV zone system:

**Figure 15. Patterns and zones**

The pattern templates provided by Android include left tabs, menus, lists, filters, paging, and so forth. Google TV patterns correspond directly to familiar patterns on other devices, so you can re-use them. If you have a list in a phone application, you can put the same list into an appropriate zone in your Google TV UI. This simplifies and speeds up porting your applications. Even better, Android defaults to scaling the pattern to the 10ft environment, and the pattern remains recognizable to users who are familiar with your application.

### Basic Patterns

#### Content Shelf

![](https://developers.google.com/tv/android/images/image12.png)

#### Content Grid

![](https://developers.google.com/tv/android/images/image13.png)

#### Content List

![](https://developers.google.com/tv/android/images/image14.png)

#### Cascading Content List

![](https://developers.google.com/tv/android/images/image15.png)

#### Extended details

![](https://developers.google.com/tv/android/images/image16.png)

#### Sub-section tabs

![](https://developers.google.com/tv/android/images/image17.png)

### Sorting and Filtering

You'll often want to provide ways for the user to sort and filter lists displayed in your UI. On a computer or touch screen, you usually provide these options in a drop-down menu at the top left hand side of the list, or on the left side of the screen. Remember the limitations of D-pad navigation as you review some ways to implement this UI in the 10ft environment.

In? [figure 16](#figure16), the orange area marks the area within the pattern that controls sorting and filtering the list below it. Notice that in this minimized state, both the label and selected option are clearly communicated to the user.

![](https://developers.google.com/tv/android/images/image21.png)

**Figure 16. Sort and filter pattern**

When the user moves into the area, it expands ( [figure 17](#figure17)) to expose all the available options, and it also displays the option that is currently selected.

![](https://developers.google.com/tv/android/images/image22.png)

**Figure 17. Sort and filter pattern, expanded.**

You may need more than one list of options if your list contains both sort and filter options.? [Figure 18](#figure18)?and? [figure 19](#figure19)?show the multiple option version of the sort and filter pattern in both its minimized and expanded states.

![](https://developers.google.com/tv/android/images/image23.png)

**Figure 18. Multiple option lists, minimized.**

![](https://developers.google.com/tv/android/images/image24.png)

**Figure 19. Multiple option lists, expanded.**

Notice that the expanded view demonstrates various ways to make selections and highlight them.

The options under A have bold text if they are selected. Under B, the text? **All Options**?is displayed if all options are selected. C uses check boxes to indicate which options are selected. D shows the result if no options are selected.

If possible, you should update the list as users select options. This provides useful feedback to the user, and makes the application appear more responsive. It also eliminates the need for a specific "Apply Filters" button and full screen refresh. Remember that as the user navigates backwards to the left bar or navigates down to the list, you should minimize the options once again, and display the currently selected options.

#### D-pad interaction traps

The D-pad navigation's interaction with these UI patterns further emphasizes the benefit of a left-to-right hierarchy. In the preferred example ( [figure 20](#figure20)) in green, the three zones provide a global, list, and confirmation context. As the user narrows a selection from category to item to confirmation, they move left to right. Any inter-zone navigation is confined to up and down. This makes it easy to select an item from a long list and then confirm the selection.

![](https://developers.google.com/tv/android/images/image25.png)

**Figure 20. A desirable zone and pattern organization.**

In the undesirable red example ( [figure 21](#figure21)), the hierarchy is the same but it's laid out vertically. Users navigate up and down to move from zone to zone. Intra-zone navigation is inconsistent; in the top and bottom zones navigation within the zone is left to right, but within the center zone navigation is up and down.

On a touchscreen device, this layout is relatively easy to handle, because users can skip between zones by picking up their finger. However, on a D-pad device, users can't skip zones. If users want to move from the global zone at the top to the confirmation buttons at the bottom, they must scroll through every item in the list in the center zone. This is a tremendous burden if the list contains 50 items! Using a left to right hierarchy prevents this trap.

![](https://developers.google.com/tv/android/images/image26.png)

**Figure 21. Undesirable zone and pattern layout.**

## UI Performance

Studies overwhelming show that users prefer fast applications, so you should balance visual appeal with fast performance. Also, TV devices vary considerably in their power, so they may not render as quickly as your workstation. Before you use a large number of complex animations for your application, consider and test the impact on user satisfaction.

Users are the ultimate judges of whether your application performs well.

As you develop your application, try measuring your application performance in terms of how long certain operations take or how many instances of objects are created using Android's testing tools. Remember, though, that these metrics aren't important to end users, who judge performance by different criteria.

For example, users may judge your application based on how quickly and smoothly it operates, and how quickly it responds to input. They may not like your application if it slows down the rest of Google TV. These reactions are the users' perceived performance of your application, and perceived performance is the most important metric.

The way to achieve the best perceived performance isn't always the same as the way to get the absolute fastest performance. Make sure your application never executes so much code that the runtime isn't able to frequently update the screen and gather user input. In some cases, achieving this balance involves dividing up a program task into parts so that at runtime the screen can update between parts.

Here are some performance questions you can ask:

1. Does your application start immediately?
1. Are your application's animations smooth or choppy?
1. Does video content look smooth or choppy?
1. Do audio clips play continuously, or do they pause and resume?
1. Do windows flicker or turn blank while a long operation is running?
1. When you type text into the application, does the text input keep up, or does it lag behind?
1. If you click in the UI is the response immediate, or is there a delay?
1. Do other applications respond poorly when your application is running?

## Additional Tips

Successful TV UIs are simple in both concept and design. Remember these tips for producing a UI that is easy to understand and use:

- **Identify the vital parts of your interface before you start work.**
  - Group your content, controls, and interactions by priority.
  - Discard anything non-essential elements.
- **Use one visible mode of navigation or one information hierarchy.**
  - Guide users to a mental "model" that works for all of your UI.
  - Rely on habits that your users have picked up from browsers or apps.
- **Make the primary action reachable in one click.**
  - Make the other onscreen actions prominent. Don't hide key features in a menu.
  - Use only a few key features.
  - Always display an easy way for users to return to their previous location. Don't rely on the back button.
- **Anticipate and select the user's next action when you can.**
  - For instance, move the insertion point into the next text box, or select the first item in a list.
- **Avoid the temptation to use abstract icons.**
  - Use short, clear labels and test them with users.
- **Limit vertical scrolling.**
  - Think about how your content will scale when it increases in size. What if a list becomes ten times longer?
  - If you must scroll, make sure a portion of the lowest section is always visible on the screen.
- **Use app widgets.**
  - App widgets are a limited set of app features that users can link to from the Home screen.
  - Use them for information shortcuts. For example, use a clock widget to display the time.
  - The Android Developers Guide describes? [app widget design and coding](http://developer.android.com/guide/topics/appwidgets/index.html).
- **Use Android's icon guidelines.**
  - Icons help guide your users through UI.
  - Android's icon guidelines help ensure your UI will work today and in the future.
  - You can customize any part of your app, including the icons, but custom work may not appear the same in future Android releases.
  - Refer to the Android Developers Guide for more information about icons.

```
本文由江南大学设计学院研究卢孩翻译，查看原文《Google TV Design Patterns》
```
