---
author: zx
category:
  - t:-tech
cover:
  alt: laptop-2620118_1920
  image: /wp-content/uploads/2022/04/laptop-2620118_1920.jpg
date: "2021-03-07T13:59:00+00:00"
title: 小米摄像头视频文件批量合并处理脚本
---
小米摄像头的视频记录文件是每分钟保存成一个文件的，后期存档和查看很不方便，对此，我编写了几个小脚本方便自动化的处理其原始视频文件。

思路如下：

1. 导出监控
1. 遍历审查所有视频/截图内容，删除不必要的文件
1. 创建待处理清单
1. 利用ffmpeg压缩所有文件

![](/wp-content/uploads/2022/04/laptop-2620118_1920.jpg)

具体脚本如下：

1\. 导出监控，有两种方式：  
方式1：通过小米监控摄像头的NAS同步设置  
方式2：手工同步：需要每次在APP中设置 推出储存卡，然后手工取下存储卡，并通过 读卡器，将视频和截图文件保存到电脑上

方式1更方便，但是没有图片截图，后面审查工作会比较费时间，可以通过批处理来生成缩略图：

```
for /f "delims=" %%i in ('dir *.mp4 /b /s') do (ffmpeg -v quiet -y -i %%i -ss 1 -f image2 %%i.jpeg)
```

2\. 遍历审查所有视频/截图内容，审查完后删除当前文件夹下及所有子目录下的jpeg图片来删除缩略图，命令如下：

```
del /f /s /q *.jpeg
```

3\. 创建待处理清单：

```
dir /s /b > files.lst
```

4\. 增加文件头尾辅助字符，以符合ffmpeg的待处理文件清单格式：

```
@echo off
cd /d "%~dp0"
set "fd=temp"
md "%fd%" 2>nul
@echo off
cd /d "%~dp0"
set "fd=temp"
md "%fd%" 2>nul
for /f "delims=" %%a in ('dir /a-d/b *.lst') do (
    echo;"%%a"
    (for /f "tokens=1*delims=:" %%b in ('findstr /n .* "%%a"') do (
        set "f=%%c"
        if defined f (echo;file '%%c') else (echo;)
    ))>"%fd%\%%a"
    del "%%a"
    move /y "%fd%\%%a" "%%a"
)
echo;%w% +%#%%#% %zx%
rd temp
```

5\. 压缩所有文件

```
for %%i in (*.lst) do (ffmpeg -hide_banner -f concat -safe 0 -i %%i -c:v libx265 -b:v 384k -c:a aac -s 1280x720 -vf scale=1280:720 -vf fps=20 %%i.mp4)
```

6\. 删除清单lst文件

```
del /f /s /q *.lst

```

批处理打包下载：

[xiaomi\_camera\_videos\_bat](/wp-content/uploads/2021/06/xiaomi_camera_videos_bat.zip) [下载](/wp-content/uploads/2021/06/xiaomi_camera_videos_bat.zip)

* * *

### 更新：2022-05-01 升级版

```
@ECHO off
@REM 删除视频截图并把当前文件下所有文件压缩成mp4
setlocal enabledelayedexpansion

:1
@REM 查找系统进程有没有FFMPEG
tasklist /nh|find /i "ffmpeg.exe" >nul
if ERRORLEVEL 0 (
	@REM 如果有，就等待10秒
	sleep 10
	goto 1
	)

@REM 如果没有就执行下面的命令

@REM 删除所有图片
del /f /s /q *.jpeg

@REM 将所有目录及子目录下文件放在temp.txt
dir /s /b > temp.txt

@REM 给temp.txt的每一行增加 file ''以方便ffmpeg处理
cd /d "%~dp0"
set "fd=temp"
md "%fd%" 2>nul
for /f "delims=" %%a in ('dir /a-d/b *.txt') do (
    echo;"%%a"
    (for /f "tokens=1*delims=:" %%b in ('findstr /n .* "%%a"') do (
        set "f=%%c"
        if defined f (echo;file '%%c') else (echo;)
    ))>"%fd%\%%a"
    del "%%a"
    move /y "%fd%\%%a" "%%a"
)
echo;%w% +%#%%#% %zx%
rd temp

@REM 把即将压缩的文件命名为YYYYMMDDHH-HH格式
dir /a:d /b > _dirlist.txt
set /p a=<_dirlist.txt
for /f "delims=" %%i in (_dirlist.txt) do (
	@REM 找出最后一行的文本内容
	set b=%%i
	)
@REM 截取前10位和后2位 组成文件名
set filename=%a:~0,10%-%b:~-2%
del _dirlist.txt

@REM 把temp.txt里面的非mp4内容删除
@REM 这里偷懒用到了Cygwin下的cat iconv grep命令 如有DOS方式请告知
@REM 在Cygwin下用iconv貌似一直无法输出正确的编码，但是在DOS下却能，奇怪
cat temp.txt|iconv -f GBK -t UTF-8|grep .mp4>%filename%.txt
del temp.txt

@REM 开始压缩
ffmpeg -hide_banner -hwaccel dxva2 -f concat -safe 0 -i "%filename%".txt -c:v hevc_qsv -b:v 384k -c:a aac -vf "scale=1280:-1, fps=20" "%filename%.mp4"

@REM 删除临时文件
del %filename%.txt

```
