---
layout: post
title: NCTF 逆向 2 题题解
tags: NCTF Write-up Reverse
---

* 目录：
{:toc}

### 80 Hello,RE! 
* 题目:  
![](http://r.photo.store.qq.com/psb?/V11aPCg53lyBwf/SmRlvayblhs3xutKcX5CDznXRG09iggTZjLLkbOj99Y!/r/dHABAAAAAAAA){: width="80%"}

* 链接: [题目地址](http://115.28.150.176/wireshark.pcapng)

* 题解:

1. 把 pcapng 下载下来

2. 用 wireshark 打开

3. 分值这么低的题, 一般先找找字符串...所以, 用 wireshark 的`显示过滤器`:  
输入`http.request.uri matches "flag"` 
![](http://r.photo.store.qq.com/psb?/V11aPCg53lyBwf/yoR*j.98hY.bNskxG1gBDvHevW2BJXmzmbXMc*NlLdw!/r/dHABAAAAAAAA){: width="100%"}
该 HTTP 请求是 GET, 按理下文应该有返回包, 所以跟踪该 TCP 流:
![](http://r.photo.store.qq.com/psb?/V11aPCg53lyBwf/FQOhD*lLRP87txf2Yc7MIFssNb7M*irOsbKtEnJEX0g!/r/dG8BAAAAAAAA){: width="100%"}
或者直接访问 [http://115.28.150.176/misc/flag.php](http://115.28.150.176/misc/flag.php) 也可得到 flag. 

* flag：nctf{wireshark_is_easy}
<hr>

### 200 wireshark 2