---
author: zx
categories:
  - t-tech
cover:
  alt: programming-1873854_1920
  image: /wp-content/uploads/2020/11/programming-1873854_1920.png
date: "2018-09-30T04:54:34+00:00"
title: 小米盒子4C优化
---
之前买了一个小米盒子4C，想着正好用废旧硬盘一起合体，给小孩子放早教视频。后来每次使用速度越来越慢，系统更新后那速度更是惨不忍睹，默认的桌面每次都要拉网络资源、渲染加载，从开机到系统对遥控器有反应起码要三分钟以上，所以想优化一波。

最初的方案是想先root然后刷精简系统，后来发现并没有立等可取的root方案，只好自己手动操作，记录如下：

1. 开启开发者模式：开启ADB、允许USB调试、允许安装未签名apk，允许远程安装apk；  

1. 安装第三方桌面、播放器、文件浏览器，我安装的是当贝的桌面、播放器（播放器自带文件浏览器），当然，也可以用adb远程连接盒子后远程安装，具体见步骤5；  

1. 电脑连接盒子：第一次连接时需要在盒子界面上授权，另外第一次远程安装apk时也需要盒子界面上授权；  
 adb connect 盒子IP   
 默认端口号5555  

1. 看看都有哪些程序包：  
 adb shell pm list package  

1. 安装oplayer：  
adb install -r /path/to/apk/com.olimsoft.android.oplayer.apk  
注意在adb上载完成后，需要在盒子界面授权，点击确认安装  

1. 删除没用的，注意，因为没有root权限所有有些系统包是相当于“禁用”了，并没有物理删除，但是只要能达到优化的目的对我来说就可以了  
adb shell pm uninstall --user 0 包名（详细清单见后）  

1. 重启试试

我本有个担心是删除了MIUI TV的桌面，会进不去桌面，没想到再删除MIUI TV桌面后，当贝桌面会自动接管，省了不少事情。

删除的包：  
adb shell pm uninstall --user 0 com.android.dreams.basic  
adb shell pm uninstall --user 0 com.android.providers.calendar  
adb shell pm uninstall --user 0 com.android.printspooler  
adb shell pm uninstall --user 0 com.droidlogic  
adb shell pm uninstall --user 0 com.miui.tv.analytics  
adb shell pm uninstall --user 0 com.miui.systemAdSolution  
adb shell pm uninstall --user 0 com.mitv.tvhome  
adb shell pm uninstall --user 0 com.mitv.screensaver  
adb shell pm uninstall --user 0 com.mitv.shoplugin  
adb shell pm uninstall --user 0 com.moretv.android  
adb shell pm uninstall --user 0 com.xiaomi.devicereport  
adb shell pm uninstall --user 0 com.xiaomi.gamecenter.sdk.service.mibox  
adb shell pm uninstall --user 0 com.xiaomi.mibox.lockscreen  
adb shell pm uninstall --user 0 com.xiaomi.miplay  
adb shell pm uninstall --user 0 com.xiaomi.mitv.advertise  
adb shell pm uninstall --user 0 com.xiaomi.mitv.tvpush.tvpushservice  
adb shell pm uninstall --user 0 com.xiaomi.mitv.calendar  
adb shell pm uninstall --user 0 com.xiaomi.screenrecorder  
adb shell pm uninstall --user 0 com.xiaomi.statistic  
adb shell pm uninstall --user 0 com.xiaomi.voicecontrol  
adb shell pm uninstall --user 0 mitv.service  
adb shell pm uninstall --user 0 com.xiaomi.mitv.tvmanager  
adb shell pm uninstall --user 0 com.mitv.tvhome  
adb shell pm uninstall --user 0 com.xiaomi.mitv.settings  
adb shell pm uninstall --user 0 com.duokan.airkan.tvbox  
adb shell pm uninstall --user 0 com.xiaomi.tweather  
adb shell pm uninstall --user 0 com.xiaomi.mimusic2  
adb shell pm uninstall --user 0 com.mitv.care  
adb shell pm uninstall --user 0 com.xiaomi.account  
adb shell pm uninstall --user 0 com.xm.webcontent  
adb shell pm uninstall --user 0 com.xiaomi.mitv.providers.settings  
adb shell pm uninstall --user 0 com.xiaomi.mitv.pay  
adb shell pm uninstall --user 0 com.gitvdemo.video  
adb shell pm uninstall --user 0 com.mitv.gallery  
adb shell pm uninstall --user 0 com.xiaomi.account.auth

保留的包：  
com.xiaodianshi.tv.yst  
com.android.providers.media  
com.sohu.inputmethod.sogou.tv  
com.android.externalstorage  
com.android.htmlviewer  
com.dianshijia.newlive  
com.android.providers.downloads  
com.dangbei.tvlauncher  
com.mitv.codec.update  
com.btkanba.tv  
com.ktcp.video  
com.android.defcontainer  
com.dangbei.lerad.videoposter  
com.android.pacprocessor  
com.miui.daemon  
com.android.certinstaller  
android  
com.android.backupconfirm  
com.android.provision  
com.android.statementservice  
com.xiaomi.mitv.mediaexplorer  
com.xiaomi.mitv.systemui  
com.android.providers.settings  
com.android.sharedstoragebackup  
com.mitv.videoplayer  
com.android.inputdevices  
hdpfans.com  
com.xiaomi.mitv.smartshare  
com.xiaomi.tv.nameservice  
com.google.android.webview  
com.android.keychain  
com.xiaomi.upnp  
com.android.packageinstaller  
com.svox.pico  
com.android.proxyhandler  
com.mitv.mivideoplayer  
com.android.settings  
com.dbappstore.lite  
com.android.vpndialogs  
com.android.shell  
com.android.providers.userdictionary  
com.duoduo.child.story4tv  
com.xiaomi.mitv.remotecontroller.service  
com.android.location.fused  
com.android.systemui  
com.tv.kuaisou  
com.android.providers.contacts  
com.android.captiveportallogin  
com.miui.core

因为只是想优化启动和加载速度，就没有纠结每一个包具体干什么用，可能删的不是太干净，还好，够用即可，此记。
