---
title: PCB_design
date: 2022-05-26 15:35:23
tags:
categories: hardware_skills 
---
# PCB画板学习
李增PCB设计

## PCB层构成
电源层、地层、信号层。
信号层用来进行信号布线。

多层PCB构成

https://www.bilibili.com/read/cv16860517?spm_id_from=444.41.list.card_article.click

![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220526153845.2z2vr4qj19o0.webp)

## 四层板和两层板
四层板可以阻抗计算中减少线宽，
回流路径短，
省走线。

## 如何判断层数
布线密度：
* 找飞线最密的地方，有交叉的至少需要2层。如果最密的地方2层可以搞定，那就可以两层搞定。

## 常用叠层
* 元件面，焊接面为完整地平面
* 无相邻平行布线层
* 信号层尽可能与地平面相邻
* 关键信号与地层相邻，不跨分割区
  

  叠层方案：
  信号01，地02，电源03，信号04.

  重要信号线走表层

## 电源相对地内缩一个毫米

## 每面走线一个方向，比如上层都是竖向，下层都是横向

## 天线上下端不能有铺铜

## 封装大小
https://blog.csdn.net/li707414287/article/details/99239656