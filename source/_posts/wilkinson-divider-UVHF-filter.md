---
title: wilkinson_divider_UVHF_filter
date: 2022-10-04 13:46:47
tags:
categories: SDR_Project
---
# wilkinson_divider_UVHF_filter
## power divider 
徐兴福ADS

* 频带范围：108-200 225-400，也就通带范围108-400
* 回波损耗：$C_{11}>20dB$
* 插入损耗 $C_{12}<3.3dB,C_{13}<3.3dB$
* 隔离度 $C_{23}>25dB$

中心频率：254MHz


50欧姆传输线线宽：1.521810mm

$\frac{4}{\lambda}$波长传输线,70.7欧姆阻抗，线宽0.789182mm,
长度168.973mm

功分器的S11达不到要求，带宽太宽了



## filter solutions

椭圆：阶数相同的条件下有着最小的通带和阻带波动

巴特沃斯：最大限度平坦，没有纹波，而在阻频带则逐渐下降为零

切比雪夫:通带或阻带上频率响应幅度等波纹波动的滤波器

原来filter solutions被HFSS母公司收购了，成了HFSS插件了

点advanced进入filter quick模式

7阶低通hourglass(好像这个边缘更陡峭)，200MHz
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/SDR/微信截图_20221005110137.2vnpbzb1yqa0.webp)

![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/SDR/微信截图_20221005110746.72is4h6ogm80.webp)

5阶椭圆带通
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/SDR/微信截图_20221005111555.55hg8vyxv2g0.webp)

![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/SDR/微信截图_20221005111642.2z9yz5ehvrq0.webp)



截止10.05晚，选择椭圆低通7阶，在225MHz有-10dB衰减，在200MHz以内有-1dB以内插损。

带通选择5阶椭圆带通，225MHz插损-1.364dB,在400MHz插损-0.179dB。640MHz以上-10dB衰减。
