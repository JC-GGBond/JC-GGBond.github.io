---
title: PA_design
date: 2022-09-18 15:24:15
tags:
categories: hardware_skills 
---
# PA design

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

## Load pull
目的：找出功放最大输出功率时的最佳外部负载阻抗ZL

ADS操作
