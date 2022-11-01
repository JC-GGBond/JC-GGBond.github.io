---
title: DPD_in_Matlab_overall
date: 2022-10-19 16:01:45
tags:
categories: final project DPD
mathjax: true
---
# SDR in MATLAB
MATLAB官方MATLAB+RF宣讲:
https://ww2.mathworks.cn/videos/smart-rf-model-and-design-119258.html?s_tid=srchtitle_%25E5%25B0%2584%25E9%25A2%2591_1

上海贝尔DPD宣讲：
chrome-extension://ikhdkkncnoglghljlkmcimlnlhkeamad/pdf-viewer/web/viewer.html?file=https%3A%2F%2Fwww.mathworks.com%2Fcontent%2Fdam%2Fmathworks%2Fmathworks-dot-com%2Fcompany%2Fevents%2Fconferences%2Fmatlab-tour-china%2F2015%2Fproceedings%2Fmatlab-rf-development-application-in-numbers.pdf

这个应该是之前看过，回忆一下

射频建模设计

Simulink+SimRF：射频前端，射频系统级设计


## SimRF
里面具有PA,Mixer,S,filter,LC,耦合器等等

### RF toolbox:射频链路预算分析


### DPD in Matlab
https://ww2.mathworks.cn/videos/search.html?q=DPD&page=1

* 2021.02.26:RF Power Amplifier Behavioral Modeling using MATLAB

https://ww2.mathworks.cn/videos/rf-power-amplifier-behavioral-modeling-using-matlab-1614963392123.html?s_tid=srchtitle_DPD_5

典型线性化方法里：DPD,包络监测envelop tracking，CFR crest-factor reduction 

要用同类型的信号去测试和实际验证

给功放供电，连接TX,RX

数次不同输入功率下的信号测量

PA model参数估计

(他用的是NI 的PXIe,一个VST测试单元，像矢量信源+矢量分析仪)

测量PA的栅压和Ic

再有了模型数据之后，可以用simulink里面的示例，进行测试：Power Amplifier Characterization & Digital Predistortion to compensate for Power Amplifier Nonlinearities


**(所以我要用什么东西生成和接受信号，集成在SDR里)**

例程中测试信号选用双音信号和5G-OFDM，64QAM调制信号！

oversampling:几倍采样下，一般5倍，就是ADC的。

例程搞得真好！

MATLAB真的是伟大的公司！是工程师与科学家的智慧结晶！也是学子圣经，含有自由的力量！

## Power Amplifier Characterization
1.select，生成合适信号去测试
```
function: helperPACharGenerateOFDM Generate OFDM signal
    [X,R,N] = helperPACharGenerateOFDM generates a 5G-like OFDM waveform,
    X, at a sample rate of R. N is the suggested number of frames.

    helperPACharGenerateTones Generate two complex tones
    [X,R,N] = helperPACharGenerateTones generates a two tone waveform,
    X, at a sample rate of R. N is the suggested number of frames.

If testSignal is "OFDM", this example uses a 5G-like OFDM waveform with 64-QAM modulated signals for each subcarrier. If testSignal is "Tones", this example uses two tones at 1.8 MHz and 2.6 MHz, to test the intermodulation caused by the PA.

example:
    switch testSignal
    case "OFDM"
        bw = 100e6;
        [txWaveform,sampleRate,numFrames] = helperPACharGenerateOFDM(bw);
    case "Tones"
        bw = 3e6;
        [txWaveform,sampleRate,numFrames] = helperPACharGenerateTones();
    end
```
查一下这个5G OFDM QAM信号为啥没有子载波