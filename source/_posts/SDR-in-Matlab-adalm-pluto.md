---
title: SDR_in_Matlab_adalm_pluto
date: 2022-10-19 16:13:12
tags:
categories: final project DPD
mathjax: true
---
# AD9361+ZYNQ7000 adalm-pluto(ZYNQ7010+AD9363) 下的SDR design
真巧，看了相关的视频有阮卡佳讲的化繁为简SDR设计，
这次兰大买了MATLAB就是阮卡佳和Mathworks会务组来讲。
真的神奇。

**ZYNQ是一款内嵌了ARM的FPGA**

https://ww2.mathworks.cn/videos/simplify-the-implementation-of-software-defined-radio-in-hardware-1510052703793.html?s_tid=srchtitle_%25E5%25B0%2584%25E9%25A2%2591_5



## RF system design
antenna RF mix_signal digital_hardware digital_hardware DSP Software architecture

## SDR
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221019163110.3bilj05ujd40.webp)

模拟前端：FMC:可调RF卡

数字前端:FPGA或SOC片上系统

基带处理:主机


## design
### 端到端仿真

### over the air测试空口测试(此时数字前端没有不数到ARM，FPGA里)
射频前端+PC端MATLAB设计


MATLAB开发了硬件接口模块：ZYNQ-SDR radio I/O
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221019164021.42bjmmn9tns0.webp)


以太网口速率限制问题：SDR硬件厂商已经用burst解决(数据缓冲)

以对象函数调用方式访问端口
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221019164330.6fj3cauxiew0.webp)

repeated waveform transmitter 存储信号，不断连续发送信号，相当于把SDR当成发生器！
就是我DPD的信源
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221019204354.50ezws24pb80.webp)

网址视频里有演示LTE发送过程：26分钟处

他这个一套流程，相当于LTE从头撸到尾发射接收，真的牛逼，能看到源码就好了

![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221019205112.27z3qn16l2jo.webp)






### 原型与实现(C代码)(此时把数字前端部署到ARM和FPGA上)

基于模型设计的理念:
系统搭建simulink，算法实现C+HDL,集成和部署

![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221019205722.3fcg43dqqi00.webp)

自动代码生成:
Embedded coder:C

HDL Coder: HDL


HW.SW:硬件模块和软件模块

HDL Workflow Advisor:卧槽一步一步教你做仿真
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221019210242.4xjifcppj5w0.webp)

![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221019210738.6kek05uo8ng0.webp)