---
author: zx
categories:
  - u-uncategoried
cover:
  alt: windows-11-6379123_1920
  image: /wp-content/uploads/2022/07/windows-11-6379123_1920.png
date: "2021-11-11T01:40:00+00:00"
title: Windows  11  优化全案
---
Windows 11 发售了，但是Explorer从用户体验角度变化太大，对于生产力工具来说降低了很多，比如任务栏不支持全部显示、右键菜单实用性降低等。对此，需要一个能够沿用 Windows 10 的使用体验方式，所以写了本文。

### 优化1：任务栏图标全部显示

Windows 11 的任务栏图标只能合并，不支持不合并的分开模式，这样导致在打开多个相同的应用时任务栏图标始终是合并的，对于习惯拆分的人来说很难用。

解决方案是用Windows10的explorer.exe替换Windows 11的。

1. 从其他系统拷贝explorer.exe文件到待替换系统的某个位置
1. 进入管理员模式的命令行
1. 删除Windows系统内的explorer.exe
1. 用xcopy替换成Win 10的
1. 打开注册表regedit，设置不合并图标：在任务管理器上点文件--运行新任务，输入 regedit 打开注册表编辑器。定位到路径 "计算机\\HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced"
1. 在右侧窗口查找 TaskbarGlomLevel 值，如果没有就新建 DWORD32 值，将数据设置为 2，关闭注册表编辑器。PS：值为 0，始终合并；1，已满时合并；2，从不合并
1. 运行桌面资源管理器：在任务管理器上点文件-运行新任务，输入 explorer.exe 运行

启动后再看任务栏就不会合并了。

这时候发现任务栏右侧是没有任何图标的，连时间也没有了，我们接着需要把时间调出来。在设置里配置是不管用的，需要配置图标。

配置通知区域图标：在任务管理器上点文件-运行新任务，输入

```
shell:::{05d7b0f4-2121-4eff-bf6b-ed3f69b894d9}
```

运行

把下面的“始终在任务栏显示所有图标和通知”勾上，然后点下面的“启用或关闭系统图标”把下面的图标启用了，时间等图标就出来了。

### 优化2：右键菜单默认显示全部选项

Windows11系统，右键菜单默认是折叠的，下面介绍如何将右键菜单恢复到Windows10（展开）模式。

![](/wp-content/uploads/2022/07/image.png)

解决方案：通过注册表修改

```
reg add "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32" /f /ve
taskkill /f /im explorer.exe & start explorer.exe
```

改回：

```
reg delete "HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}" /f
taskkill /f /im explorer.exe & start explorer.exe
```
