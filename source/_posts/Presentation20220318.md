---
title: Presentation20220318
date: 2022-03-18 13:09:09
tags:
categories: Presentation
---
# Presentation 2022.03.18

## Modeling & Coding
在上次组会对Matlab中DPD模块搭建simulink框图；

本次对具体的两个数据集自己编写代码进行dpd建模。

## dataset
Center Frequency:491520000 491.52MHz

原信号x，过功放经CFR后去增益信号d，用x去建模d

**评价dpd性能指标：**

* err=d-F(X),共计16384个点,实际输出-预测的输出,**这个也可以反应到功率谱上，也就是对e进行功率谱密度绘制，显得更小
* NMSE：归一化均方误差(Normalized Mean Square Error)，预测信号$y_d(n)$与实际输出信号y(n)差异大小
$$
NMSE=10\log_{10}{\frac{\sum_{n=1}^{N}|y_{arr}(n)-d(n)|^2}{\sum_{n=1}^{N}|d(n)|^2}}
$$
### dataset1
20Mh宽带信号
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/Massive-MIMO-Competition/x&d.53kiy4e24qw0.webp)

### dataset2
40MHz带频率间隔的调制信号
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/Massive-MIMO-Competition/x&d_00.5wpnrqnenm80.webp)

## test result

### MP_Full + lms


$$
y_{MP}(n)=\sum_{k=1}^{K} \sum_{q=0}^{Q-1} a_{kq} x(n-q)|x(n-q)|^{k-1}
$$
K=5,Q=2参数量15:

dataset1

**AfMPDPD_NMSE = -31.89 dB**
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/MP_full/predict.4v4ymhwxd6s0.webp)

![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/MP_full/lmserror.38vvikmu0ca0.webp)

dataset2

**AfMPDPD_NMSE = -17.20 dB**
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/MP_full/predict_00.3y3lbdgh178.webp)
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/MP_full/lmserror_00.5k1a2eloig40.webp)

### MP_odd + lms
$$
y_{MP}(n)=\sum_{k=1,k=odd}^{K} \sum_{q=0}^{Q-1} a_{kq} x(n-q)|x(n-q)|^{k-1}
$$
K=5,Q=2且只取奇阶参数量9:

dataset1
**AfMPDPD_NMSE = -32.48 dB**
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/Massive-MIMO-Competition/predict.y2z54m0yya8.webp)
dataset2
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/Massive-MIMO-Competition/lmserror.1k795xqfgeu8.webp)
**AfMPDPD_NMSE = -14.84 dB**
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/Massive-MIMO-Competition/predict_00.7jz21q0k7b0.webp)
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/Massive-MIMO-Competition/lmserror_00.5gvgdzwykqo0.webp)

### GMP + lms

$$
\begin{aligned}
y_{GMP}(n)=& \sum_{k=0}^{K_{a}-1} \sum_{l=0}^{L_{a}-1} a_{k l} x(n-l)|x(n-l)|^{k} \\
&+\sum_{k=1}^{K_{b}} \sum_{l=0}^{L_{b}-1} \sum_{m=1}^{M_{b}} b_{k l m} x(n-l)|x(n-l-m)|^{k} \\
\end{aligned}
$$
K_a=5;
L_a=3;
K_b=4;
L_b=4;
M_b=3;
参数量68

dataset1
**AfMPDPD_NMSE = -35.20 dB**
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/GMP_1/predict.632l7h75q2w0.webp)
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/GMP_1/lmserror.4y18gsr3q340.webp)
dataset2
**AfMPDPD_NMSE = -19.82 dB**
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/GMP_1/predict_00.69xjbq53bao0.webp)
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/GMP_1/lmserror_00.63rsngyohwo0.webp)