---
title: PA_design
date: 2022-09-18 15:24:15
tags:
categories: hardware_skills 
mathjax: true
---
# PA design by 徐兴福ADS设计

## 非线性指标
估计最常问的也就是那个三阶互调失真IMD3和三阶截断点IP3

IMD3:3-order Inter modulation distortion 
$$
\Delta=P_{f_{1}}-P_{2f_{2}-f_{1}}\ (\mathbf{dBc})
$$

IP3: 3rd-order Intercept Point, IP3，是输出的dBm

基频信号线性延长线和三阶交调失真信号IMD3的虚拟延长线交点
$$
P_{IP3}(\mathbf{dBm})\approx P_{1\mathbf{dB}}(\mathbf{dBm})+10.6\mathbf{dB}
$$

## 功放
线性功放A、AB、B、C

开关功放D、E、F

## Load pull
目的：找出功放最大输出功率时的最佳外部负载阻抗ZL

ADS操作

### 1.导入管子模型

### 2.载入ADS FET curve tracer模板

Insert template

### 3.扫参仿真
$$
V_{DS},I_{DS},每个V_{GS}一条线
$$
找静态工作点


### 4.稳定性判别
要求稳定性因子＞1

### 5.Load pull
确定负载阻抗点

### 6.Source pull
确定输入阻抗点

### 7.输出匹配电路
* 共轭匹配方式，保证功率最大。
* 匹配避免跨过等Q值圆
* 理想微带线转化真实微带线

### 输入匹配电路
依旧为共轭匹配

### 偏置？

### 原理图S参数仿真

### HB仿真，Harmonic Distortion
谐波仿真

### 原理图优化调谐

### 生成Layout

# PA design by 曹中华师兄