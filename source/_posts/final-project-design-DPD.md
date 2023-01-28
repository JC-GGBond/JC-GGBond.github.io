---
title: final_project_design_DPD
date: 2022-10-20 15:55:06
tags:
categories: final project DPD
mathjax: true
---
# Final project DPD design



## Source signal generation
信源信号：

5G NR up link or down link for test

* 目前使用MATLAB helperPACharGenerateOFDM/Tones函数可以生成时域信号，分别为5G 64QAM OFDM信号和双音信号

* 基带信号使用MATLAB生成不同信号类型和带宽的5G NR测试模型(NR-TMs),标称测试时不同信号具有不同的PAPR值

* (郁博组测试方法)测试时候分成不同发射功率，不同信号带宽，不同信号类型?(查TM3.X)为一个确定发射状态,
上采样到X MHz，滤带外分量，
上变频2.4GHz,
预推动后发射。
接衰减器后接信号分析仪(高老师)接收，
给PC进行处理.
每组信号6000训练，150000验证.
训练时候的数据选择发射的信号峰值包络.

使用matlab模块:

见白皮书(Testing 5G NR Devices with Standard Waveforms)

https://www.mathworks.com/content/dam/mathworks/white-paper/gated/5g-nr-testing-white-paper.pdf


## DUT (Device Under Test)
曹中华师兄PA,多带CGH40010 GaN,
别人论文里可能是一个Doherty测试，
可以把不同带的信号测试作为文章的创新点之一.
标称一下测试时使用PA的峰值输出功率多少dBm.


## PA model
* MM会议看见的，清深唐仙组CNN复卷积+soft-attention，50dB+NMSE矫正，
* 东南余超郁博，分段模型，矢量开关，OMP剪枝。

## DPD Coefficient Extraction
DPD系数提取方法,
迭代学习控制方法(Iterative Learning Control,ILC)





## Parameter estimation


