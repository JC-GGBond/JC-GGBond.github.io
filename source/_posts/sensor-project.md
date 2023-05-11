---
title: sensor_project
date: 2023-01-15 21:11:21
tags:
categories: Sensor_Project
---
# 物理院传感器项目

## Paper1: A full sample-type magneto-impedance (MI) magnetometer with programmable circuit for high compatibility

AIP Advance: 水刊


具有
* 高兼容性
* 可编程电路的
* 全采样型
* 磁阻抗（MI）型磁强计


应该是要关注那个模拟开关运放电路.





长光所磁强计:
http://www.jl1.cn/product_view.aspx?id=1500


好像是用在卫星上面的

指标：
工作模式

应答式和自主上传

量程

-2 Gauss～+2Gauss

分辨率

≤ 70μGauss

精度（25℃）

0.8%～1%（@±1Gauss）

数据更新率

10Hz

输出接口

RS422

供电电压

+12V

工作电流

45mA～80mA

功耗

≤1W

环境适应性

温度：-10℃～+45℃

外包络尺寸

Φ（98±0.2）mm×（80±0.2）mm

重量

0.4kg±0.03kg

、


WIKI:
https://zh.wikipedia.org/wiki/%E7%A3%81%E5%BC%BA%E8%AE%A1



## Amorphous wire MI micro sensor using C-MOS IC multivibrator

采用C-MOS IC多谐振荡器的非晶丝MI(磁阻)微型传感器










## 模拟电路模块功能

在激励电路的作用下，
磁强计三分量探头探测的分量输出均为与激励信号同频的微弱交流信号，
经过前级放大和交流耦合后，通过相敏解调电路将交流信号
转换为直流信号并进行积分运算；
并采用闭环控制的工作模式，
将积分输出的电压信号通过 U/I 转换模块转换为电流信号反馈到磁强计探头端，
的 offset 电流带组成反馈环路；积分电路的电压信
号通过低通滤波后输出。模拟电路的设计作用在
于：采用交流耦合和闭环控制工作模式，提高磁强
计的灵敏度和分辨率，稳定磁强计工作状态。