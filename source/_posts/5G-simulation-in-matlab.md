---
title: 5G_simulation_in_matlab
date: 2022-10-20 09:48:13
tags:
categories: final project DPD
mathjax: true
---
# 5G 无线系统仿真与原型实现

白皮书集合：
https://www.mathworks.com/solutions/wireless-communications/5g.html

华为5G视角：
chrome-extension://ikhdkkncnoglghljlkmcimlnlhkeamad/pdf-viewer/web/viewer.html?file=https%3A%2F%2Fwww.mathworks.com%2Fcontent%2Fdam%2Fmathworks%2Ftag-team%2FObjects%2Fh%2F80861v00_Huawei_QA.pdf

进入新的领域需要支撑，并不希望从零开始

光通信里面好像也要用到预失真


研讨会视频:
2017的，稍微有点老但是概述很好的
https://ww2.mathworks.cn/videos/the-road-to-5g-simulating-and-prototyping-wireless-systems-1510052713234.html?s_tid=srchtitle_%25E5%25B0%2584%25E9%25A2%2591_6

5G：NR：new radio 新空口


LTE System toolbox下面的5G library

![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221020095820.636mjp5yrek0.webp)

simulink里面的RF Blockset

## 实现流程:
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221020100157.60vwzufsflc0.webp)


![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221020104950.5fwaxp4i8do0.webp)


**使用 MATLAB 开发 5G NR 设计电子书**
https://ww2.mathworks.cn/campaigns/offers/5g-technology-ebook.html

https://ww2.mathworks.cn/campaigns/offers/deploying-5g-nr-on-fpgas-white-paper.html

看上面两个电子书完成SDR设计

可以完成simulink到C，但是不能直接变成电路

## 支持包工具
* 5G信道模型
* 新的模型F/W-OFDM
* 仿真链路


5G信号人为的增加了PAPR，使得对模拟器件，PA的线性有较强的要求。
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221020101131.6mi2sj8an4c0.webp)

![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221020101317.7ft4aponovg0.webp)
看文章里面用的5G NR信号用的具体是哪个。


### 天线/相控阵设计
beamforming:省PA

1个LTE frame是1ms

可以把HFSS和CST导入MATLABantenna APP里

### AD9361设计prototype
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/final-project-DPD/微信截图_20221020103650.3jt8m5u7weg0.webp)

## 工作人员功能
少数的5-10人组成一个算法团队，快速的做原型验证。都是算法工程师。
Ericsson试验台：HDL 
https://www.mathworks.com/videos/radio-testbed-design-using-hdl-coder-92636.html?s_tid=srchtitle_radio%20test%20bed%20design_1

关注自动代码生成





**20170620当天视频有华为员工分享DPD design!**



