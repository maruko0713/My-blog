---
title: HTTP协议学习总结
date: 2016-11-25
tags: ["HTTP"]
---
## HTTP协议的特点
- 简单快速: 统一资源符（uri）是固定的
- 灵活: 可以传输不同的数据类型
- 无连接: 每连接一次都会断掉
- 无状态: 对于之前的交互没有记录。HTTP 协议是没有办法记住之前的一次请求的，服务端是无法区分下一次连接和上一次连接者的身份的

## HTTP报文的组成部分
请求报文： 请求行 请求头 空行 请求体
响应报文： 状态行 响应头 空行 响应体

请求行:  
> GET/POST [url] HTTP/[version]   GET / HTTP/1.1

请求头 是一些key-value值: 
> Host: miemie.com    
  User-Agent: curl/7.43.0    
  Accept: */*

状态行：
> HTTP[版本号] [状态码] [状态信息]
> HTTP/1.1 200 OK

响应头:
>[ header 名]: [ header 值]
这些信息基本上都是用来描述后面要介绍的响应主体数据的



## HTTP方法
GET(获取资源),POST(传输资源),PUT(更新资源),DELETE(删除资源),HEAD(获得报文首部),OPTION


## POST和GET的区别    
- GET请求的参数会被完整保存在浏览器历史记录里，而POST不会
- GET请求传输的参数是有长度限制的，而POST没有
- 对参数的数据类型，GET只能接受ASCII字符，而POST没有限制
- GET参数通过URL来传递，而POST通过请求体来传递
## HTTP状态码
1xx：指示信息-表示信息已接收，继续处理
2xx：成功
3xx：重定向
4xx：客户端错误-请求有语法错误或者请求无法实现
5xx：服务器错误

200：请求成功   
301：永久重定向   
302：临时重定向  
400：请求有语法错误，不能被服务器所理解
403：资源禁止被访问     
404：请求资源不存在     
500：服务器内部错误  
  
## 什么是持久连接
HTTP持久连接可以重用已建立的TCP连接，减少三次握手的RTT延迟。浏览器在请求时带上 connection: keep-alive 的头部，服务器收到后就要发送完响应后保持连接一段时间，浏览器在下一次对该服务器的请求时，就可以直接拿来用。
当使用KEEP-ALIVE模式时，KEEP-ALIVE功能使客户端到服务端的连接持续有效，当有后续请求时，该功能避免了建立或者重新建立连接。    

## 什么是管线化
它是建立在持久连接之上，是把所有请求一并发给服务器，但是服务器需要按照顺序一个一个响应，而不是等到一个响应回来才能发下一个请求


## tip
管线化机制以持久连接为前提，仅HTTP/1.1支持此技术   
只有GET和HEAD支持管线化，而POST有所限制   
   