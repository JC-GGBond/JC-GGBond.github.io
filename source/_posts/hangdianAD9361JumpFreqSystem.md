---
title: hangdianAD9361JumpFreqSystem
date: 2022-05-12 10:18:04
tags:
categories: SDR_Project
---
# 杭电任继安用AD9361做的调频系统
牛逼的
## 设计流程
为实现快速频率跳动在主机中完成对射频芯片的快速频跳的设计，
并完成与主机匹配从机跳频的接收。

1.利用射频模块中快速锁模式实现更快频率的配置，减少锁相环校准的时间，
更快速完成射频模块中发射载波频率和接收载波频率设定。
并且如需要更换跳频频点，无需更换硬件平台，
只需重新配置所需频率，通过基带处理器 FPGA 预存至射频模块中，
实现频率快速更换。

2、为了制作快跳高扩通信系统主机与从机硬件平台。利用 Cadence  Allegro
软件设计本文所述的硬件平台，设计射频模块部分、基带处理器部分和整体系统供电方案，
完成此快跳高扩系统主机与从机的硬件电路制作。

3、为了满足跳频扩频特性，设计了一种针对此项目特定的数据帧。
在数据帧中加入了前导序列、同步序列、勤务定时序列。
前导序列为了提高从机接收的数据信噪比和保证信号采样时幅度的大致稳定。
同步序列为了确定数据帧的位置用于帧定时同步，以及跳频图案同步。 

 
