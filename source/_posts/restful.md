---
title: 对RESTful架构的理解
date: 2016-09-08
tags: ["RESTful"]
---
## 前言
阅读《AngularJS高级程序设计》这本书的第三章，作者对一些概念也是解释的很随意，直接来了一句“我觉得传递json就实现了RESTful”就把我们打发了。实在忍不了，上网搜了一大堆解释，都扯的云里雾里的，现在差不多有点头绪了，记录一下，防止自己以后再蒙圈。    

## 一句话概括RESTful
URL定位资源，用HTTP动词（GET,POST,DELETE,PUT）描述操作。    

## 为什么会有RESTful
上面那句绝不是耍流氓，仔细想想RESTful难道不就是这样的吗？？？？    
要知道RESTful的特性和意义，就必须了解RESTful之前的那个时代。在"古代"网页是前端后端融在一起的，比如之前的PHP，JSP等。近年来移动互联网的发展，各种类型的客户端层出不穷，RESTful可以通过一套统一的接口为 Web，iOS和Android提供服务。另外对于广大平台来说，比如Facebook platform，微博开放平台，微信公共平台等，它们不需要有显式的前端，只需要一套提供服务的接口，于是RESTful更是它们最好的选择。在RESTful架构下，服务器的核心任务是提供数据和改变数据状态，它就是围着数据转，其它的事情让前端去做。相应的，前端就要渲染页面和处理简单的商务逻辑（AngularJS之流就登场了）。    

## RESTful的翻译式理解
REST -- REpresentational State Transfer    
翻译过来叫“表现层状态转移”     
这个名字太恶心了，看名字谁知道你想干啥啊。表现层是啥？？？转移到哪里去？？你给我说清楚啊？？？？（掀桌）     
其实可以这样理解，“表现层”就是数据的表现形式，可以是json，可以是xml，“状态转移”就是这个数据对应的状态的改变，就是我们老生常谈的增删改查。     
现在我们瞅瞅上面那句“URL定位资源，用HTTP动词（GET,POST,DELETE,PUT）描述操作。”的解释，是不是没啥问题？定位资源（表现层），描述操作（状态转移）。    

## RESTful的特点
其实上面也已经说了个差不多，我们来做个总结。    
所谓RESTful，它本质是一种架构设计方式，它的特点是面向*资源*，资源是核心，服务器端不必操心你的网页长什么样，不必操心一些琐碎的逻辑，我就给你提供操作数据资源的服务。因此在REST里面：    
- 一切都被认为是一种资源
- 每个资源有唯一的url标识
- 客户端程序在建立起的资源url上发送请求，使用*请求方法*表示期望的操作。
- 无状态

## RESTful给前端带来了什么
其实我到觉得是前端的变化促使了RESTful的产生。随着我们客户端形式的多样化，pc端已经远远不能满足人们的需要，如果一台服务器同时负责pc端页面的渲染，移动端页面的渲染，那不仅服务器会感到很疲惫，它渲染出来的内容咋样还是另一说，另外在使用原生的手机应用时，更是不可能指望把一切都交给服务器端。况且，现在前端能做的事情越来越多了，一些业务逻辑完全可以用js来做，于是乎，服务器端似乎只需要管好数据就行了，RESTful应运而生。    
RESTful架构使得前后端变得泾渭分明，同时因为前后端逻辑的分离，使一台服务器完全可以同时为web页面，安卓和ios应用同时提供服务。说明白点，服务器统一提供一套RESTful API（这里的api不再是我们平时表达的函数接口的意思，而是数据接口），web+ios+android作为同等公民调用API。各端发展到现在，都有一套比较成熟的框架来帮开发者事半功倍。（比如我现在正在学的AngularJS！）    

## 挖坑
写了这么多，都是在给最近正在上手的AngularJS做铺垫。    
立个flag：    
下一篇文章绝对要把Angular中的mvc模式整明白！    
