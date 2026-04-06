---
author: zx
category:
  - t:-tech
cover:
  alt: coding-gd12f75a25_1920
  image: /wp-content/uploads/2022/04/coding-gd12f75a25_1920.jpg
date: "2021-09-29T02:00:00+00:00"
title: 通过命令行将 ANSI/GBK 编码文件批量转为 UTF-8 编码
---
使用的是 `iconv` 命令，用命令行批量转换。

## 安装

`iconv` 支持 Linux、Windows、macOS，其中 macOS 自带，部分 Linux 系统自带，若提示 `command not found` 则说明需要另外安装。

### Linux

项目主页： [libiconv - GNU Project - Free Software Foundation (FSF)](http://www.gnu.org/software/libiconv/)  

```
root@zx:~# wget https://ftp.gnu.org/pub/gnu/libiconv/libiconv-1.16.tar.gz && cd libiconv-1.16
root@zx:~# ./configure --prefix=/usr/local
root@zx:~# make && make install
root@zx:~# ln -s /usr/local/lib/* /usr/lib
```

### Windows

项目主页： [LibIconv for Windows](http://gnuwin32.sourceforge.net/packages/libiconv.htm)  

```
1、下载可执行程序：
https://udomain.dl.sourceforge.net/project/gnuwin32/libiconv/1.9.2-1/libiconv-1.9.2-1.exe；
2、双击根据提示安装；
3、将 libiconv 安装目录加入到系统环境变量中，或执行 iconv 时使用完整路径。
```

## 使用

### 单个文件

#### 直接显示到控制台

```
root@zx:~# iconv  zedex.cn.lrc   -f GBK  -t utf-8
```

#### 改变编码并保存到文件

```
root@zx:~# iconv  zedex.cn.lrc   -f GBK  -t utf-8 -o  zedex.cn.utf8.lrc
```

### 批量文件

比如嵌套目录下的文件：

```
//通过 find -type d（查找目录）命令，将当前zedex.cn 文件夹里的目录递归的找出来，
然后通过 mkdir 命令，将找出来的目录递归地复制到 utf/vircloud.net 中

root@zx:~# find zedex.cn -type d -exec mkdir -p utf/{} \;

//通过 find -type f （查找文件）命令，将当前 vircloud.net 文件夹里的文件递归的找出来，
然后通过 iconv 命令，批量的转换为 utf-8 文件，并复制到 utf/zedex.cn 中

root@zx: ~# find zedex.cn -type f -exec iconv -f GBK -t UTF-8 {} -o utf/{} \;
```

* * *
