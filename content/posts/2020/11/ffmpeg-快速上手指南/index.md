---
author: zx
category:
  - t:-tech
cover:
  alt: iphone-1836071_1920
  image: /wp-content/uploads/2022/04/iphone-1836071_1920.jpg
date: "2020-11-04T03:06:00+00:00"
summary: |-
  FFmpeg是一个十分方便的多媒体文件全家桶，我在治理摄像头视频存档的时候，发现很多视频编辑软件的底层都是FFmpeg实现的，所以就直接拿FFmpeg来作为视频编辑工具。发现网上很多教程要不就是只言片语，要不就是整段的官方文档，很难有半个小时之内就能看懂上手掌握其基本用法的文章，故有此文。

  ![](/wp-content/uploads/2022/04/iphone-1836071_1920.jpg)
title: FFmpeg 快速上手指南
---
FFmpeg是一个十分方便的多媒体文件全家桶，我在治理摄像头视频存档的时候，发现很多视频编辑软件的底层都是FFmpeg实现的，所以就直接拿FFmpeg来作为视频编辑工具。发现网上很多教程要不就是只言片语，要不就是整段的官方文档，很难有半个小时之内就能看懂上手掌握其基本用法的文章，故有此文。

![](/wp-content/uploads/2022/04/iphone-1836071_1920.jpg)

下载 FFmpeg: https://www.FFmpeg.org/Download.html

完整文档: https://www.ffmpeg.org/ffmpeg.html

## 基本转换

```
ffmpeg -i in.mp4 out.avi

```

### 将 MKV 文件重组为 MP4

```
ffmpeg -i in.mkv -c:v copy -c:a copy out.mp4

```

### 高质量的编码

使用 crf (恒定速率因子)参数控制输出质量。通透系数越低，质量越高(范围: 0-51)。默认值为23，从视觉上看，无损数据压缩对应于-crf 18。使用预设参数来控制压缩过程的速度。更多信息: https://trac.ffmpeg.org/wiki/encode/h.264

```
ffmpeg -i in.mp4 -preset slower -crf 18 out.mp4
```

## 修剪

不重新编码:

```
ffmpeg -ss [start] -i in.mp4 -t [duration] -c copy out.mp4
```

- [`-ss`](http://ffmpeg.org/ffmpeg-all.html#Main-options) 指定开始时间，例如 `00:01:23.000` or 或 `83` (in seconds) (以秒计)
- [`-t`](http://ffmpeg.org/ffmpeg-all.html#Main-options) 指定剪辑的持续时间(同样的格式)
- -to 提供结束时间 `-to`.
- [`-c`](http://ffmpeg.org/ffmpeg-all.html#Main-options) 将第一个视频、音频和字幕比特流从输入复制到输出文件，而不重新编码它们。这不会影响质量，并使命令在秒内运行

带有重新编码:

如果您省略了-c 复制选项，ffmpeg 将根据您选择的格式自动重新编码输出的视频和音频。要获得高质量的视频和音频，请分别阅读 x264编码指南和 AAC 编码指南。

例如:

```
ffmpeg -ss [start] -i in.mp4 -t [duration] -c:v libx264 -c:a aac -strict experimental -b:a 128k out.mp4
```

## 多路视频和音频从另一个视频

从 in0.mp4复制视频，从 in1.mp4复制音频:

```
ffmpeg -i in0.mp4 -i in1.mp4 -c copy -map 0:0 -map 1:1 -shortest out.mp4
```

- 用 [-c copy](http://ffmpeg.org/ffmpeg.html#Stream-copy) 将会进行流复制，而不是重新编码，所以不会有质量损失。如果你想重新编码，请参阅 [FFmpeg Wiki: H.264 Encoding Guide 264编码指南](https://trac.ffmpeg.org/wiki/Encode/H.264).
- `-shortest` 选项将导致输出持续时间与最短输入流的持续时间相匹配
- 参见 [`-map` option documentation 期权文件](http://ffmpeg.org/ffmpeg.html#Advanced-options) 了解更多信息

## 合并多个视频文件

首先，创建一个文本文件。

```
file 'in1.mp4'
file 'in2.mp4'
file 'in3.mp4'
file 'in4.mp4'
```

然后，运行 ffmpeg:

```
ffmpeg -f concat -i list.txt -c copy out.mp4
```

## 延迟播放音频/视频

延迟视频3.84秒:

```
ffmpeg -i in.mp4 -itsoffset 3.84 -i in.mp4 -map 1:v -map 0:a -vcodec copy -acodec copy out.mp4
```

延迟音频3.84秒:

```
ffmpeg -i in.mp4 -itsoffset 3.84 -i in.mp4 -map 0:v -map 1:a -vcodec copy -acodec copy out.mp4
```

## 嵌入字幕

使用 libass 库(请确保您的 ffmpeg 安装在配置中包含该库 -- enable-libass)。

首先将字幕转换为. ass 格式:

```
ffmpeg -i sub.srt sub.ass
```

然后用视频过滤器添加它们:

```
ffmpeg -i in.mp4 -vf ass=sub.ass out.mp4
```

## 从视频中提取帧

从1到5秒以及11到15秒之间提取所有帧:

```
ffmpeg -i in.mp4 -vf select='between(t,1,5)+between(t,11,15)' -vsync 0 out%d.png
```

每秒只提取一帧:

```
ffmpeg -i in.mp4 -fps=1 -vsync 0 out%d.png
```

## 旋转视频

顺时针旋转90度:

```
ffmpeg -i in.mov -vf "transpose=1" out.mov
```

对于转置参数，您可以传递:

```
0 = 90CounterCLockwise and Vertical Flip (default)
1 = 90Clockwise
2 = 90CounterClockwise
3 = 90Clockwise and Vertical Flip
```

使用-vf“ transpose = 2，transpose = 2”表示180度。

## Download "Transport Stream" video streams 下载「传送流」视频流

1. 找到播放列表文件，例如使用 Chrome > F12 > Network > Filter: m3u8
1. 下载并连接视频片段:

```
ffmpeg -i "path_to_playlist.m3u8" -c copy -bsf:a aac_adtstoasc out.mp4
```

如果出现“ Protocol‘ https not on whitelist‘ file，crypto’!”错误，请添加 Protocol \_ whitelist 选项:

```
ffmpeg -protocol_whitelist "file,http,https,tcp,tls" -i "path_to_playlist.m3u8" -c copy -bsf:a aac_adtstoasc out.mp4
```

## 静音音频

将前90秒的音频替换为静音:

```
ffmpeg -i in.mp4 -vcodec copy -af "volume=enable='lte(t,90)':volume=0" out.mp4
```

以静音取代1’20”至1’30”之间的所有声音:

```
ffmpeg -i in.mp4 -vcodec copy -af "volume=enable='between(t,80,90)':volume=0" out.mp4
```

## 去隔行

去隔行使用“另一个去隔行过滤器”。

```
ffmpeg -i in.mp4 -vf yadif out.mp4
```

## 从图片创建一个视频幻灯片

参数:-r 标记图像帧率(每个图像的反时间) ;-vf fps = 25标记输出的真实帧率。

```
ffmpeg -r 1/5 -i img%03d.png -c:v libx264 -vf fps=25 -pix_fmt yuv420p out.mp4
```

## 从视频中提取图像

- 提取所有帧: `ffmpeg -i input.mp4 thumb%04d.jpg -hide_banner`
- 每秒提取一帧: `ffmpeg -i input.mp4 -vf fps=1 thumb%04d.jpg -hide_banner`
- 只提取一帧: `ffmpeg -i input.mp4 -ss 00:00:10.000 -vframes 1 thumb.jpg`

## 元数据: 更改标题

```
ffmpeg -i in.mp4 -map_metadata -1 -metadata title="My Title" -c:v copy -c:a copy out.mp4
```
