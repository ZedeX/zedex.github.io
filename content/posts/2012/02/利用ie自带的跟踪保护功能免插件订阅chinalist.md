---
author: zx
category:
  - t:-tech
date: "2012-02-13T11:38:10+00:00"
title: 利用IE自带的跟踪保护功能免插件订阅ChinaList
---
点击下面的链接来将EasyList，ChinaList或其他广告屏蔽列表添加到IE中。注意仅对IE9和IE10有效。  
（99%的用户只要用第一个就可以了）

[ChinaList+EasyList](javascript:window.external.msAddTrackingProtectionList('http://easylist-msie.adblockplus.org/chinalist+easylist.tpl', 'ChinaList+EasyList'))

[EasyList](javascript:window.external.msAddTrackingProtectionList('http://easylist-msie.adblockplus.org/easylist.tpl', 'EasyList'))

[EasyPrivacy+EasyList](javascript:window.external.msAddTrackingProtectionList('http://easylist-msie.adblockplus.org/easyprivacy+easylist.tpl', 'EasyPrivacy+EasyList'))

[Fanboy Adblock List](javascript:window.external.msAddTrackingProtectionList('http://www.fanboy.co.nz/adblock/ie/fanboy-noele.tpl', 'Fanboy Adblock List'))

[Fanboy Tracking List](javascript:window.external.msAddTrackingProtectionList('http://www.fanboy.co.nz/adblock/ie/fanboy-tracking.tpl', 'Fanboy Tracking List'))

更新：IE11点击微软官方的屏蔽广告链接：http://www.iegallery.com/PinnedSites

这个功能其实是利用JavaScript调用IE私有方法msAddTrackingProtectionList直接将特定列表添加到追踪保护功能.

追踪保护功能是IE9的新增功能，反跟踪工具可自动向网站和在线广告网络发送信息，要求不跟踪自己的行为。该系统只有在网络公司同意尊重用户选择时才有用。到目前为止，各大在线广告网络还未就如何尊敬用户选择达成一致。所以我们只好自己手动添加。

广告列表来源： [ChinaList](http://code.google.com/p/adblock-chinalist/)（这份列表会在志愿者的维护下添加、验证并自动更新，用户只要一次添加即可一直用下去。）
