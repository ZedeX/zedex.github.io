---
author: zx
category:
  - t:-tech
date: "2018-04-05T08:07:50+00:00"
summary: |-
  想在命名文件的时候，根据当前日期和时间来命名生成的文件，但是默认的方法在生成文件名的时候，会间断性报错，排查了之后发现是因为DOS输出的%date%和%time%会在有单字的时候，在前面填充一个空格，而这个空格会截断DOS命令，导致出错。

  解决方法有2个，第一个是直接在系统设置里，或者注册表里改系统日期和时间格式，如图所示：

  ![](/wp-content/uploads/2019/12/change-date-format-1.png)![](/wp-content/uploads/2019/12/change-date-format-2.png)

  或直接导入注册表：（请将以下文字保存为“日期时间格式.reg”文件）

  `Windows Registry Editor Version 5.00`

  `[HKEY_CURRENT_USER\Control Panel\International]
  "sLongDate"="yyyy-MM-dd"
  "sShortDate"="yyyy-MM-dd"
  "sTimeFormat"="HH:mm:ss"
  "sShortTime"="HH:mm"
  "sYearMonth"="yyyy-MM"`

  因为作为一般用户，貌似只有Word在插入日期时间的时候会用到这个值，其他地方没有会遇到使用这个值得地方，所以改动应该不会带来什么副作用。其他经常要跟时间打交道的同学请综合评估影响。

  第二个方法，在DOS环境中排查%date%、%time%输出的空格，替换为0:，代码如下：
title: 如何让DOS输出的日期和时间在只有单字符时补0
---
想在命名文件的时候，根据当前日期和时间来命名生成的文件，但是默认的方法在生成文件名的时候，会间断性报错，排查了之后发现是因为DOS输出的%date%和%time%会在有单字的时候，在前面填充一个空格，而这个空格会截断DOS命令，导致出错。

解决方法有2个，第一个是直接在系统设置里，或者注册表里改系统日期和时间格式，如图所示：

![](/wp-content/uploads/2019/12/change-date-format-1.png)![](/wp-content/uploads/2019/12/change-date-format-2.png)

或直接导入注册表：（请将以下文字保存为“日期时间格式.reg”文件）

`Windows Registry Editor Version 5.00`

`[HKEY_CURRENT_USER\Control Panel\International]
"sLongDate"="yyyy-MM-dd"
"sShortDate"="yyyy-MM-dd"
"sTimeFormat"="HH:mm:ss"
"sShortTime"="HH:mm"
"sYearMonth"="yyyy-MM"`

因为作为一般用户，貌似只有Word在插入日期时间的时候会用到这个值，其他地方没有会遇到使用这个值得地方，所以改动应该不会带来什么副作用。其他经常要跟时间打交道的同学请综合评估影响。

第二个方法，在DOS环境中排查%date%、%time%输出的空格，替换为0:，代码如下：

`set zxmonth=%date:~5,2%
if "%date:~5,1%" == " " set zxmonth=0%date:~6,1%
set zxday=%date:~8,2%
if "%date:~8,1%" == " " set zxday=0%date:~9,1%
set zxhour=%time:~0,2%
if "%time:~0,1%" == " " set zxhour=0%time:~1,1%
set zxminute=%time:~3,2%
if "%time:~3,1%" == " " set zxminute=0%time:~4,1%
set zxsecond=%time:~6,2%
if "%time:~6,1%" == " " set zxsecond=0%time:~7,1%
@echo %date:~2,2%-%zxmonth%-%zxday%-%zxhour%-%zxminute%-%zxsecond%`
