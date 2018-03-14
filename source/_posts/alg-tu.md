
---
title: 算法笔记：图论
date: 2017-06-20
tags: ["算法"]
---

## 前言
~~算法系列不需要前言~~    
本系列力求以尽可能简洁的语言对传统算法作可理解的描述，不贴代码/伪代码。    
不是错题本，不是OJ参考答案(这个在[这里](https://github.com/mieruko0713/mieruko_algorithms))，只是总结   
      
   
## 图的遍历
### 深度优先搜索
深度优先搜索以"深度"作为第一关键词，每次都是沿着路径到不能再前进时才退回到最近的岔道口。    

### 广度优先搜索
广度优先搜索以"广度"作为第一关键词，每次以扩散的方式向外访问顶点。   
使用BFS遍历图需要用到一个队列，通过反复取出队首顶点，将该顶点可到达的未曾加入过队列的顶点全部入队，直到队列为空时遍历结束。    
    
## 最短路径
最短路径是图论中一个很经典的问题：    
给定图(V,E)，求一条从起点到终点的路径，使这条路径上经过的所有边的边权之和最小。   

### 单源最短路-迪杰斯特拉算法
对图设置集合S，存放已被访问的顶点，然后每次从集合中选择与起点s的距离最短的一个顶点u，访问并加入集合S。   
然后令u为中介点，优化从起点s到所有通过u能抵达的顶点之间的距离。这样操作n次（n为顶点个数），直到集合S已包含了所有的顶点。    


### 多源最短路-佛洛依德算法
如果存在顶点K，使以K作中介点时顶点i和顶点j的当前最短距离缩短，就使用顶点K作为i和j的中介点，基于此来优化i和j之间的距离。    
