---
title: 5G_physicallayer_modeling_Matlab
date: 2022-10-26 19:20:05
tags:
categories: final project DPD
mathjax: true
---
# 5G物理层算法仿真过程
* 总presentation
https://ww2.mathworks.cn/videos/understanding-and-modeling-the-5g-nr-physical-layer-1576072995802.html
* 5G小知识点视频
https://www.mathworks.com/videos/series/5g-explained.html

* 白皮书
5g-nr-testing-white-paper.pdf

他这个仿真是整个的，
包括上下信道等等等等，
空口物理层仿真的，
所以可以总览看看，
关注信号生成的。

## 理解5G NR物理层
 URLLC(Ultrareliable and low latency)超可靠低时延,eMBB(Enhanced Mobile Broadband)增强型宽带高速率高带宽,mMTC(Massive Machine Type Comms)大流量高能效低运营功率，
 
 出现了好多次了这几个概念词

有关5G的优势，看PPT吧，放在链路建立文档里了

https://github.com/JC-GGBond/JC-GGBond.github.io/blob/hexo/source/understandingandmodelingthe5gnrphysicallayer.pdf 

使用大括号引用文件链接(插入页面里面，看书签)

## 4/5G代际差距

反正就是5G比4G适用范围广，低时延，频带宽，带宽大，载波间距可调，频率分配部署方式灵活？(freq allocation),好像是不用终端监控整个接受频带的信号，频谱感知？减少stand by功率消耗。

* 两个频段Sub6G(TDD/FDD)和MMWave(TDD)
但是4/5 G的载波间隔不同，
5G具有更大的载波间隔，
使得OFDM信号周期更短。
2倍的载波间隔使得OFDM信号周期除以2。

操还得复习OFDM。复习通信原理。

## 5G link

* 感觉他涉及到整个协议规划，
包括同步(详见MATLAB示例：NR Synchronization Procedures)啊，
波束赋形啊，
小区选择啊,
上下行uplink/downlink信道控制,
编解码众多设计。

* **波形生成示例：5G Toolbox——Examples下的三个例子：
5G NR Downlink Waveform Generation、5G NR Uplink Carrier Waveform Generation、5G NR-TM and FRC Waveform Generation.非常好的例子，直接演示生成信号数据。** 
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/20220127/微信截图_20221112161707.53j5buronpc0.webp)

* CORESETs(Control Resource Sets)
控制发射时候的时频资源划分的可能。
限制带宽，节省资源。

* 信道相关名词：PUSCH信道 主要用于传输上行数据业务、
PDSCH(Physical Downlink Shared channel)信道 传输下行业务数据、
PDCCH(Control Channel)信道 传输控制信息。 
其中控制信息包括PDSCH和PUSCH数据的时频域位置信息还有一个PUCCH信道 主要用来传输反馈信息 有下行反馈ack/back CQI PMI RI等等这些构成了4/5G主要的物理信道

* DCI(Downlink control information)
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/20220127/微信截图_20221111140102.39gngep6rom0.webp)原来极化码用在这里。

* Scrambling 加扰

* 接入步骤
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/20220127/微信截图_20221112160330.5k48ey6truc0.webp)

## 5G Toolbox in matlab 

* Matlab toolbox 应用
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/20220127/微信截图_20221112161141.4dc5p454l6w0.webp)
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/20220127/微信截图_20221112161609.oa6h3c3xvi8.webp)

* 硬件移植为C/C++
Matlab coder

https://ww2.mathworks.cn/products/matlab-coder.html


* ACLR测量
![](https://cdn.staticaly.com/gh/JC-GGBond/image-JC@master/20220127/微信截图_20221112161837.7fmpw4qadns0.webp)





