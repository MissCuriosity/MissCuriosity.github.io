---
layout: post
title:  "HTTP权威指南"
# subtitle: "because they lacked opposable thumbs and the brainpower to build a space program."
date:   2017-05-30
category: HTTP
# background: '/img/posts/01.jpg'
---

#### 目录
1、<a href="#1">第一章<a/>

2、<a href="#2">第二章<a/>

<a id="1" href="javascript:void(0)"></a>
#### 第一章
    主要描述了客户端如何从服务器获取资源

###### 计算机网络五层协议结构
![](http://img.hb.aicdn.com/8194fc8b8384808bca2cb20ef6d52f9f890fefffd196-jpCich_fw658)

###### 如何利用HTTP请求和响应报文操纵远程服务器上的多媒体资源

    在这个过程中需要通过`DNS服务`来解析域名以获取服务器IP地址

![](http://img.hb.aicdn.com/e84c3c06b84c0c498968f5d6af4fdfca474eb4333423d-1kxxgz_fw658)

###### 初识TCP

三大特性
* 无差错的数据连接
* 按需传输（数据总会按照发送的顺序到达）
* 未分段的数据流（可以在任意时刻以任意尺寸将数据发送出去）

***

<a id="2" href="javascript:void(0)"></a>
#### 第二章
    主要描述关于URL的细节

###### URL语法

    概念: 统一资源定位符, 是互联网上标准资源的地址

    语法: <scheme>://<user>:<password>@<host>:<port>/<path>;<params>?<query>#<frag>

    scheme: HTTP, FTP, SMTP, file
    frag: 一小片或一小部分资源名称。不会被发送到服务器, 是客户端在服务器获取响应后在客户端进行响应操作
    path: 由多个path segment组成[由/分割开], 每一个path segment都会有自己对应的params
    port: HTTP中默认80, HTTPS默认443
    query: 名/值对 组成，多个 名/值对 由 = 连接

###### URL种类

* 绝对地址[有方案]
* 快捷方式[无方案]

> 快捷方式

* 相对URL

    从 基础URL 中获取方案、主机、端口、路径等 相对URL 中缺失的部分

* 自动扩展地址[和代理使用时, 可能会有一些与预期不一样的骚操作]

    方式: 主机名扩展、历史扩展

###### URL字符集

    会对特殊字符进行转义
