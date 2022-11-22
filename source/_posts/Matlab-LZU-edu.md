---
title: Matlab_LZU_edu
date: 2022-11-11 15:42:01
tags:
categories: Matlab
mathjax: true
---
# Matlab 兰大校园培训

真巧，看了相关的视频有阮卡佳讲的化繁为简SDR设计，
这次兰大买了MATLAB就是阮卡佳和Mathworks会务组就杨嘉琛来讲。
真的神奇。

## 基础，把帮助文档安装到本地！！！

自定进度在线课程，新出的功能

分类器APP？
自动KNN，SVM之类的。

## 并行运算培训
MATLAB里面的左下角有显示什么什么正忙，
计算资源不够。

可以使用学院超算中心资源进行加速。

MATLAB避免使用过多for循环。

并行计算这个真的很好啊，可以simulink加速啊什么的。
原来我跑一个仿真用那么长时间。

* 首先进行代码优化，减少for循环
* 找到硬件资源，进行多核运算
* 具体操作，Parallel里进行修改
* 对代码进行修改。
    * 比如for变成par-for(很多条件不支持，必须从1开始啊,不能循环套循环的)(真他妈费劲- -)
    * feval-parfeval
    * sim-parsim。
* 有的APP里面直接点那个parallel按键就行。
