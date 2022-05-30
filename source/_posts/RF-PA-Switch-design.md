---
title: RF_PA_Switch_design
date: 2022-05-16 15:42:50
tags:
categories: SDR_Project
---
# 频段选通开关设计
搞个这干嘛你说，发射直接来个信号选通完了。
这样只不过让功放功能独立一下，没用啊。

## 实现方法
基于凌特(LINEAR，现在被ADI收购了)射频功率检测芯片LTC5507的选通开关设计。
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220516154953.4xyyxuk1hqo0.webp)
1管脚使能，等于VCC时候芯片开启，7us到20us就可以开启
* 改变外部电容修改频率检测范围
* C1,C2足够大，使得高于某一频率的信号可以通过
* C1,C2建议使用瓷片电容，容抗小于5Ω以减少C2上纹波，C1=C2
$$
C2(\mu f) \geq \frac{1}{30 freq}
$$

电压比较器使用LM393进行比较，
大于基准电压开

交给杜少凯师弟完成设计。

## 电路设计
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220519171556.1xb3e0aiq3wg.webp)
* 输入使用RC滤波电路，高通滤波
  https://zhuanlan.zhihu.com/p/148159402

  滤掉100兆以下的,留下电容位和电阻位以供观测。100pF左右。
* 单刀双路开关
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/O1CN01jxPYU428lgOfEn7oa_!!49027973.65nfv5w9eeo0.webp)

* 晚上找器件，周六买回来


截止频率：
$$
F_{cut\ off}=\frac{1}{2\pi RC}
$$
* 
## 测试方法
1.看是不是要在手里这两个大功放上面测试，直接拿信号发生器发射信号，看电平输出。
2.画个评估板PCB，买芯片，测试
3.找模型看实在capture上仿真还是在ADS上仿真

## 技能学习
1.Cadence17.4入门使用

2.PCB抄板


## PCB画板
* SMA端口地线最后接地直接表层敷铜
* 先画信号电源线
* 再查阻抗匹配等