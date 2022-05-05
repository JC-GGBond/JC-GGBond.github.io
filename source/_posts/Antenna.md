---
title: Antenna
date: 2022-05-05 15:30:21
tags:
categories: Antenna
---
# Antenna Intro
## 常见天线
### LW 长线天线（Long Wire Antenna）
长线天线是一种很常见的天线形式，在早期应用较多，主要就是一
根长的电线，可以采用从 1.5 平方毫米到 6 平方毫米的金属线，一般建议为使用多股软铜线，对改善带宽和阻抗有帮助。长线天线的长度为谐振频率的 1/2 或 1/4 波长。长线天线计算公式是：天线长度=300×缩短系数/2×（谐振频率 MHz），谐振频率一般指需要工作的主要频率，缩短系数=0.93~0.97 之间，根据情况具体调整。长线天线常见的是使用 1：9 巴伦，或者是不使用巴伦。在使用 1：9 巴伦时，主振子为长线天线，副振子需要匹配 1/4 或 1/8波长的振子。长线天线常见的架设形式是水平架设和倒 L 架设，这两种架设方式的极化方式是不同的，水平架设一般是水平极化，而倒 L 架设包括了垂直极化和水平极化两种极化方式。
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220505153636.263y8vnc1ecg.webp)

### DP半波偶极天线（Dipole Antenna）
这也是一种相对比较常见的天线形式，主要形式是对称的 2 个振子，
一般使用 1：1 的巴伦。半波偶极天线的每个振子长度=300×缩短系数/4×谐振频率，谐振频率为 MHz，其中的缩短系数=0.93~0.97 不等。每个振子均为谐振频率波长的 1/4 左右。这种类型的天线可以水平架设、倒 V 架设、倾斜架设。每种架设方式的辐射仰角和通信距离有一定的差异
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220505154153.133noc58ujio.webp)

![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220505154202.1aaf5ph7cta8.webp)
### 温顿天线（Windom Antenna）
温顿天线是馈电点在偏离中心约 17%的地方的天线。这种天线可以工作在基本谐振频率的偶次倍数上，温顿天线有 2 根长度不等的天线，一般使用 1：4 的巴伦，也有使用１：６巴伦的，不过需要谨慎。温顿天线的计算公式是：振子 1 长度=300×缩短系数×0.33/2×谐振频率；振子 2 长度=300×缩短系数×0.66/２×谐振频率，其中的缩短系数根据具体情况调整，缩短系数=0.93~0.97 不等。温顿天线也是一种可以同时工作在多个波段的天线。
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220505154357.6jonqpw7z4w0.webp)

### 八木天线（Yagi Antenna）
八木天线于上个世纪 20 年代被发明出来，是一种比较复杂的天线，使用多个平行振子，八木天线具有较强的方向性，适合远距离通信使用，常见的有 VHF/UHF 八木天线、短波八木天线等。
八木天线是一种多单元端射阵列，至少包括一个单独的激励单元和一个单独的寄生单元，这些单元被平行安放在一根支撑杆上并且相互分开。当无源单元被安放在激励单元后面，与最大辐射方向相反时，称为反射器；当被安放在无源单元前面时，则称为引向器。八木天线使用在 V/U 频段时，尺寸相对较小，可以接收数十千米至数百千米范围内的信号，八木天线使用在短波时，尺寸比较大，可以比较容易的接收上万千米远的信号。
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220505161850.2t3xnwcm3z20.webp)
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220505161901.6v3ufd1wq740.webp)
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220505161910.53l7rfutn4c0.webp)


### 小环天线（Loop Antenna）
小环天线也是一种常见的天线，通常将 1/10 波长的环状天线称为小环天线，
小环天线是一个线圈。小环天线中的电流分布与一个线圈的电流分布是相同的。该天线具有一定的方向性和抗干扰性，在一些场合下适用于接收。小环天线的发射效率相对受限。
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220505161920.46e255ncdcu0.webp)
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220505161930.76u97gzbjv00.webp)
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220505161939.410h96byj140.webp)
### GP 天线
这是一种常见的简单天线形式，一般采用 1/4 谐振频率波长的振子和 1/4 波长的地网安装即可。
一些 GP 天线带有加感线圈或者是陷波器，可以在一定程度上缩短物理尺寸，或者是兼顾多个波段的使用。该天线的极化方式呈垂直极化，适合 DX 远距离通信。这种类型的天线背景噪音较偶极天线略大，对干扰信号和背景噪音比较敏感，但是架设相对容易。
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/SDR_project/微信截图_20220505161951.4juzt7az1xg0.webp)