---
author: zx
category:
  - i:-internet
date: "2008-05-15T17:57:53+00:00"
summary: |-
  Google Analytics 跟踪代码迁移手册{{ double-space-with-newline }}-从urchin.js到ga.js

  > **目录**{{ double-space-with-newline }}新版中有什么变化？ / 新跟踪代码的优势 / 我可以仍旧使用urchin.js吗？ / 新的跟踪代码和旧的兼容吗？ / 跟踪代码是什么？ / 基础跟踪代码 / 跟踪实际页面浏览量 / 跟踪下载文件 / 多用户跟踪同一页面 / 跟踪子域 / 使用链接跟踪跨域用户 / 使用表单跟踪跨域用户 / 电子交易处理 / 增加搜索引擎源 / 区分用户类型 / 为子目录限制cookies / 控制数据搜集选项 / 控制会话过期时间 / 控制活动转化过期时间 / 定制活动表单 / 使用锚点在URL中传递数据 / 设置关键字忽视参数 / 控制数据采样率 / 使用Google Analytics和Urchin

  {{ double-space-with-newline }}花费了大概6个小时左右的“作品”。其中有四处不确定意思正确，不过应该不影响理解：
title: Google Analytics 跟踪代码迁移手册 - 简体中文
---
Google Analytics 跟踪代码迁移手册  
-从urchin.js到ga.js

> **目录**  
新版中有什么变化？ / 新跟踪代码的优势 / 我可以仍旧使用urchin.js吗？ / 新的跟踪代码和旧的兼容吗？ / 跟踪代码是什么？ / 基础跟踪代码 / 跟踪实际页面浏览量 / 跟踪下载文件 / 多用户跟踪同一页面 / 跟踪子域 / 使用链接跟踪跨域用户 / 使用表单跟踪跨域用户 / 电子交易处理 / 增加搜索引擎源 / 区分用户类型 / 为子目录限制cookies / 控制数据搜集选项 / 控制会话过期时间 / 控制活动转化过期时间 / 定制活动表单 / 使用锚点在URL中传递数据 / 设置关键字忽视参数 / 控制数据采样率 / 使用Google Analytics和Urchin


花费了大概6个小时左右的“作品”。其中有四处不确定意思正确，不过应该不影响理解：

1. **单词granular的用法**：愿意为“颗粒状的”，我想这是是不是指可以提供更多更“琐碎”的报告数据，所以翻译成了“更细化的”。
1. **单词organic的用法**：经常在Google Analytics中看到这个单词了，但是没有深究其意思，到了较真的时候就不知道它的意思了。在这里我将organic traffic意译成了“来自搜索引擎的流量”。
1. **单词segmente的用法**：原意为“分割”。我没用过这个词，但是翻译过来的“分割”好像有从物理上“割”的意味；然后我看到了下面的举例，所以我在这里翻译成了“将……分类”。
1. **单词campaign的用法**：campaign原意有“活动”的意思。我想这里应该指用户使用浏览器访问网站，的所有记录（因为从下面例子中可以看出，Google给出了一个相当长的时间参数值\[ [31536000是一年的秒数](http://www.google.com/search?q=31536000s%3D%3Fyear "查看31536000秒等能够换算成多少年？")\]），所以也翻译成“活动”。
1. **下面这句话：“Track campaigns with custom field names by passing your desired names to these campaign functions on your landing pages, enabling Google Analytics to recognize the campaign information in your manually tagged URLs.”** 我意译为：“在‘着陆’页面把您所需要的名称传递给这些活动，本功能可以跟踪带有定制表单名称的活动。开启Google Analytics来识别来自您手动标定的URL中的这些活动信息。”可能和原意会有一些出入，但我想对站长来说应该能够理解吧！

下载地址：英文原版（已失效）  
简体中文版下载页面  
[备用存档-Google Analytics迁移手册简体中文版](./wp-content/uploads/2008/05/gatcmigrationguidecn.pdf "点击这里使用备用存档下载Google Analytics迁移手册简体中文版")

想要转载的朋友，请先跟在下通告一声，谢谢。
