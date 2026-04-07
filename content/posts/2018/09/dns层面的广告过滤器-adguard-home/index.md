---
author: zx
categories:
  - i-internet
  - t-tech
cover:
  alt: AdGuardHome
  image: /wp-content/uploads/2020/12/AdGuardHome.jpg
date: "2018-09-05T03:37:08+00:00"
summary: |-
  AdGuard是优秀的广告过滤工具，其公司推出了一系列广告过滤工具包括：浏览器插件层面的广告过滤器、各操作系统（Windows、iOS、Android、Mac、Linux等）层面的广告过滤器，也卖带广告过滤功能的路由器设备，最近还推出了AdGuard DNS，只要将DNS地址设置为94.140.14.14或94.140.15.15即可，但是速度据国内的朋友反馈很不理想。不过这个问题现在可以解决了。

  ![](/wp-content/uploads/2020/12/AdGuardHome.jpg)

  AdGuard推出了新的产品AdGuard Home，这是一个在局域网里提供DNS的服务，然后通过DNS过滤广告域名的手段来过滤广告，并且只要在路由器或者主服务器上部署，并且把路由器的DNS设置为这台提供DNS的服务器地址，这样局域网内的全部机器都可以不做任何部署动作即可获得过滤广告的效果，而且速度也是非常快的。
title: DNS层面的广告过滤器：AdGuard Home
---
AdGuard是优秀的广告过滤工具，其公司推出了一系列广告过滤工具包括：浏览器插件层面的广告过滤器、各操作系统（Windows、iOS、Android、Mac、Linux等）层面的广告过滤器，也卖带广告过滤功能的路由器设备，最近还推出了AdGuard DNS，只要将DNS地址设置为94.140.14.14或94.140.15.15即可，但是速度据国内的朋友反馈很不理想。不过这个问题现在可以解决了。

![](/wp-content/uploads/2020/12/AdGuardHome.jpg)

AdGuard推出了新的产品AdGuard Home，这是一个在局域网里提供DNS的服务，然后通过DNS过滤广告域名的手段来过滤广告，并且只要在路由器或者主服务器上部署，并且把路由器的DNS设置为这台提供DNS的服务器地址，这样局域网内的全部机器都可以不做任何部署动作即可获得过滤广告的效果，而且速度也是非常快的。

dGuard Home功能非常强大，基本可以满足一般使用需求。它支持自定义配置过滤列表，服务器通过定期拉取云端的过滤列表可以做到动态更新，也可以通过Web服务一键更新AdGuard Home产品本身。另外也支持IPv6、DNS-over-HTTPS、DNS-over-TLS、DNS-over-QUIC等主流甚至前瞻性的DNS服务，日常使用完全够了。

下载安装十分简单，在Github上：https://github.com/AdguardTeam/AdGuardHome/releases/

Windows下可以通过

```
AdGuardHome.exe -s install
```

将应用程序注册成系统服务，以便开机即用。
