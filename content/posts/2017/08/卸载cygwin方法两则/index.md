---
author: zx
categories:
  - t-tech
date: "2017-08-11T02:31:10+00:00"
title: 卸载Cygwin方法两则
---
[Cygwin](http://cygwin.com/) 是一个Windows下使用Linux环境的平台，安装简单、环境独立（也可以把Cygwin\\bin目录增加到Windows系统的PATH环境中，在cmd中调用Linux命令），比微软提供的Linux环境都方便不少，因为是真机资源，性能也比虚拟机好很多。

卸载也很简单，把文件夹整个删除即可，但是因为权限配置问题，每次删除都会留下一些不能被删除的“尾巴”，还要通过一些辅助软件才能彻底清空。

在网上搜索之后，发现两个比较好的一次性清理干净的做法。如下：

第一个方法：在CMD下键入如下命令，其中D:\\cygwin是Cygwin的安装目录

> SET DIRECTORY\_NAME="D:\\cygwin"  
C:\\windows\\system32\\TAKEOWN /f %DIRECTORY\_NAME% /r /d y  
C:\\windows\\system32\\ICACLS %DIRECTORY\_NAME% /grant administrators:F /t  
PAUSE

这段代码的作用是把Cygwin文件夹下的所有文件的所有权都赋予给管理员用户，去除了诸如SYSTEM用户等的权限，然后再直接删除目录即可

第二个方法：在Cygwin安装文件执行的时候，选中uninstall，如图，然后执行安装过程。  
![](/wp-content/uploads/2019/10/cygwin-uninstall.png)

使用愉快！
