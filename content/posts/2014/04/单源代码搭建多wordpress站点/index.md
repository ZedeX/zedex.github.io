---
author: zx
category:
  - t:-tech
date: "2014-04-12T04:01:15+00:00"
tag:
  - wordpress
title: 单源代码搭建多WordPress站点
---
本文讨论的方法是使用一套WordPress源代码，实现多站点各自的内容、模板、附件及可定制功能的实现方法。

### 前提条件

- 几个站必须在同一个主机空间
- 几个站的固定链接样式必须一样
- 每一个网站创建一个独立的MySQL数据库，或同一个数据库不同表头
- 将每个域名都解析到同一个网站目录

### 主体流程

1. 配置域名系统指向到同一空间
1. 配置每个站点单独的数据库（如使用同一个数据库不同表头，则此步忽略）
1. 修改wp-config.php信息，根据不同域名设置不同的初始化值，达到使用不同变量的目的。
1. 根据域名依次安装每个WordPress
1. 配置每个系统的各自变量：媒体文件存放地址、CDN、备份计划等

### 主要实现方法

#### wp-config.php文件的配置

`if($_SERVER["HTTP_HOST"]=="www.domain1.com" || $_SERVER["HTTP_HOST"]=="domain1.com"){`

define('DB\_NAME', 'database\_name\_1');  
define('DB\_USER', 'username\_1');  
define('DB\_PASSWORD', 'password\_1');  
define('DB\_HOST', 'host\_1');  
define('DB\_CHARSET', 'utf8');  
define('DB\_COLLATE', '');  
$table\_prefix = 'wp1\_';  
define('WPLANG', 'zh\_CN');

}else if($\_SERVER\["HTTP\_HOST"\]=="www.domain2.net" \|\| $\_SERVER\["HTTP\_HOST"\]=="domain2.net"){

define('DB\_NAME', 'database\_name\_2');  
define('DB\_USER', 'username\_2');  
define('DB\_PASSWORD', 'password\_2');  
define('DB\_HOST', 'host\_2');  
define('DB\_CHARSET', 'utf8');  
define('DB\_COLLATE', '');  
$table\_prefix = 'wp2\_';  
define('WPLANG', 'zh\_CN');

}

如果多余2个域名，则按需增加判断部分，另可根据wpconfig.php强大的配置功能达到特定目的，具体参见：http://codex.wordpress.org/Editing/_wp-config.php( [中文](http://codex.wordpress.org/zh-cn:%E7%BC%96%E8%BE%91_wp-config.php))

#### wp-content信息的配置

（推荐）  
由于默认安装共享了/wp-content/文件夹下的信息，如果想针对不同站点指定不同的插件、模板、上传目录，需要针对修改，可通过自定义wp-config.php文件或在WP后台设置达到目的。

如果不修改可能会遇到上传文件名相同、架构不良好插件的配置覆盖（通过文件保存配置信息的插件），备份恢复困难等潜在风险。
