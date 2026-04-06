---
author: zx
category:
  - t:-tech
date: "2014-06-18T02:16:47+00:00"
summary: |-
  最近网络不稳定，上国外网站都上不去，一查是DNS的问题。所以找了一个解决方案：建议在可控的最上级路由器上进行配置，以便网内所有设备上网而不必单独设置DNS。

  国内服务器：

  1\. OpenerDNS：

  `42.120.21.30`

  2\. 114DNS：{{ double-space-with-newline }}`114.114.114.114
  114.114.115.115`

  3\. oneDNS：{{ double-space-with-newline }}`112.124.47.27`

  4\. aliDNS：{{ double-space-with-newline }}`223.5.5.5
  223.6.6.6`

  国际服务器：
title: DNS池及配置方案
---
最近网络不稳定，上国外网站都上不去，一查是DNS的问题。所以找了一个解决方案：建议在可控的最上级路由器上进行配置，以便网内所有设备上网而不必单独设置DNS。

国内服务器：

1\. OpenerDNS：

`42.120.21.30`

2\. 114DNS：  
`114.114.114.114
114.114.115.115`

3\. oneDNS：  
`112.124.47.27`

4\. aliDNS：  
`223.5.5.5
223.6.6.6`

国际服务器：

1\. Google DNS  
`8.8.8.8
8.8.4.4`

2.V2EX DNS：  
`199.91.73.222
178.79.131.110`

3\. OpenDNS  
`208.67.222.222
208.67.220.220`

推荐方案：

主DNS：openerDNS  
`42.120.21.30`

备DNS：aliDNS  
`223.5.5.5`

主DNS方便我们访问Google各项服务，备DNS确保我们的高可用性。

附：上海电信对各DNS跟踪的结果：

（跳跃节点越少越好，节点间数值越小越好，各位可根据自己网络的实际情况选择质量好、速度快的DNS。）  
:->tracert 42.120.21.30

Tracing route to 42.120.21.30 over a maximum of 30 hops

1 7 ms 8 ms 7 ms 124.74.56.69  
2 9 ms 7 ms 11 ms ow4157.sta.net.cn \[124.74.227.157\]  
3 8 ms 8 ms 8 ms 124.74.215.137  
4 \* 13 ms \* 124.74.166.114  
5 \* \* \* Request timed out.  
6 11 ms 10 ms 11 ms 101.95.211.122  
7 14 ms 14 ms 15 ms 42.120.246.78  
8 14 ms 15 ms 14 ms 42.120.244.182  
9 15 ms 15 ms 15 ms 42.120.244.230  
10 \* \* \* Request timed out.  
11 15 ms 15 ms 14 ms 42.120.21.30

Trace complete.

:->tracert 114.114.114.114

Tracing route to public1.114dns.com \[114.114.114.114\]  
over a maximum of 30 hops:

1 8 ms 8 ms 8 ms 124.74.56.69  
2 11 ms 7 ms 7 ms ow4157.sta.net.cn \[124.74.227.157\]  
3 8 ms 8 ms 8 ms 124.74.254.1  
4 11 ms 11 ms 11 ms 202.101.63.210  
5 15 ms 11 ms 11 ms 202.97.55.46  
6 \* \* \* Request timed out.  
7 17 ms 16 ms 16 ms 58.213.224.170  
8 14 ms 14 ms 14 ms public1.114dns.com \[114.114.114.114\]

Trace complete.

:->tracert 114.114.115.115

Tracing route to public2.114dns.com \[114.114.115.115\]  
over a maximum of 30 hops:

1 8 ms 7 ms 7 ms 124.74.56.69  
2 10 ms 11 ms 7 ms ow4149.sta.net.cn \[124.74.227.149\]  
3 13 ms 11 ms 11 ms 124.74.215.41  
4 10 ms 11 ms 11 ms 202.101.63.126  
5 12 ms 15 ms 15 ms 202.97.55.34  
6 20 ms 19 ms 16 ms 218.2.182.74  
7 16 ms 15 ms 16 ms 58.213.224.170  
8 14 ms 14 ms 14 ms public2.114dns.com \[114.114.115.115\]

Trace complete.

:->tracert 112.124.47.27

Tracing route to 112.124.47.27 over a maximum of 30 hops

1 7 ms 14 ms 8 ms 124.74.56.69  
2 9 ms 8 ms 8 ms ow4149.sta.net.cn \[124.74.227.149\]  
3 12 ms 10 ms 11 ms 124.74.210.125  
4 \* 11 ms 9 ms 101.95.218.90  
5 \* \* \* Request timed out.  
6 11 ms 11 ms 11 ms 101.95.211.118  
7 17 ms 16 ms 16 ms 42.120.246.74  
8 32 ms 17 ms 15 ms 42.120.244.174  
9 17 ms 17 ms 17 ms 42.120.244.246  
10 \* \* \* Request timed out.  
11 67 ms 15 ms 16 ms 112.124.47.27

Trace complete.

:->tracert 223.5.5.5

Tracing route to public1.alidns.com \[223.5.5.5\]  
over a maximum of 30 hops:

1 9 ms 8 ms 8 ms 124.74.56.69  
2 8 ms 11 ms 12 ms ow4149.sta.net.cn \[124.74.227.149\]  
3 26 ms 18 ms 15 ms 124.74.215.233  
4 \* 12 ms \* 101.95.218.182  
5 \* \* \* Request timed out.  
6 10 ms 11 ms 11 ms 101.95.211.118  
7 15 ms 16 ms 16 ms 42.120.246.74  
8 15 ms 15 ms 15 ms 42.120.244.174  
9 16 ms 15 ms 15 ms 42.120.244.238  
10 \* \* \* Request timed out.  
11 14 ms 15 ms 15 ms public1.alidns.com \[223.5.5.5\]

Trace complete.

:->tracert 223.6.6.6

Tracing route to public2.alidns.com \[223.6.6.6\]  
over a maximum of 30 hops:

1 7 ms 8 ms 7 ms 124.74.56.69  
2 10 ms 7 ms 8 ms ow4157.sta.net.cn \[124.74.227.157\]  
3 11 ms 13 ms 9 ms 124.74.210.101  
4 \* \* \* Request timed out.  
5 \* \* \* Request timed out.  
6 12 ms 11 ms 11 ms 101.95.211.126  
7 15 ms 17 ms 16 ms 42.120.246.78  
8 15 ms 15 ms 15 ms 42.120.244.198  
9 17 ms 17 ms 16 ms 42.120.244.246  
10 \* \* \* Request timed out.  
11 16 ms 16 ms 15 ms public2.alidns.com \[223.6.6.6\]

Trace complete.

:->tracert 8.8.8.8

Tracing route to google-public-dns-a.google.com \[8.8.8.8\]  
over a maximum of 30 hops:

1 7 ms 8 ms 8 ms 124.74.56.69  
2 11 ms 11 ms 7 ms ow4157.sta.net.cn \[124.74.227.157\]  
3 12 ms 11 ms 11 ms 124.74.215.33  
4 11 ms 11 ms 12 ms 61.152.86.174  
5 10 ms 10 ms 10 ms 202.97.33.58  
6 9 ms 9 ms 10 ms 202.97.33.2  
7 40 ms 39 ms 40 ms 202.97.61.2  
8 \* 38 ms \* 202.97.62.214  
9 39 ms \* 44 ms 209.85.241.58  
10 \* 64 ms \* 209.85.241.99  
11 \* 67 ms \* 209.85.243.23  
12 \* \* \* Request timed out.  
13 \* 64 ms \* google-public-dns-a.google.com \[8.8.8.8\]  
14 \* 64 ms \* google-public-dns-a.google.com \[8.8.8.8\]  
15 \* \* \* Request timed out.  
16 \* \* \* Request timed out.  
17 63 ms \* \* google-public-dns-a.google.com \[8.8.8.8\]  
18 \* \* \* Request timed out.  
19 \* \* 435 ms google-public-dns-a.google.com \[8.8.8.8\]

Trace complete.
