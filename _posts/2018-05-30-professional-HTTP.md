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

3、<a href="#3">第三章<a/>

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

***

<a id="3" href="javascript:void(0)"></a>
#### 第三章
    主要讲报文

###### 报文流

    报文方向: 流入[服务器]; 流出[从服务器流出]。
    报文流向对象: 上游、下游  => 报文始终是从上游流向下游。上、下游的概念是相对的

###### 报文的组成部分、语法

    组成部分：起始行[请求行、响应行], 首部, 实体

> 起始行

        请求行: <method> <request-url> <version>
        响应行: <version> <status-code> <reason-phrase>

###### method

    种类: GET, HEAD, OPTIONS, POST, PUT, DELETE, TRACE
    安全方法: GET, HEAD

> GET和HEAD的区别: HEAD不会返回实体

> PUT和POST的区别: PUT是将请求的主体部分存储在服务器上, POST是向服务器发送需要处理的数据

###### status-code

    1xx     信息性状态码
        100：服务器、客户端、代理[客户端请求中带有实体部分, 服务器必须要给出响应]

    2xx     成功状态码
    3xx     重定向状态码
    4xx     客户端错误状态码
    5xx     服务器错误状态码

###### headers

    通用首部
        信息性首部, 通用缓存首部[Cache-Control, Pragma]

    请求首部
        Accept首部, 信息性首部, 条件请求首部, 安全请求首部, 代理请求首部

    响应首部
        信息性首部, 协商首部, 安全响应首部
    实体首部
        信息性首部[Allow, Location], 内容首部, 实体缓存首部[ETag, Expires, Last-Modified]