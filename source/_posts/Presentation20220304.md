---
title: Presentation20220304
date: 2022-03-04 13:03:35
tags:
categories: Presentation
---
# Presentation 2022.03.04

## Modeling & Coding

### Modeling using matlab 

Simulink + simRF
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/20220304/dpd-twotone.79pcie42wlg0.webp)

Spectrum Analyzer
without dpd
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/20220304/without-dpd.6r3ecdmg2b40.webp)

after dpd
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/20220304/dpd.25xuh144t40w.webp)

### Coding

#### MP

$$
y(n)=\sum_{k=1}^K\sum_{q=0}^Q x(n-q)|x(n-q)|^{k-1}
$$

```
% try to realise the MP function
function MP_coef=Memory_Polymonial_model(x,y,memlen,K)
%as the matlab language syntax from 1 to N
%MP: q=0:Q  k=1:K
%actually the memlen is Q+1;degree is k
x=x(:);
%原矩阵按每一列摞起来成为N*1
y=y(:);
xlen=length(x);

xrow=reshape((memlen:-1:1)'+(0:xlen:xlen*(K-1)),1,[]);

%reshape(([memlen,memlen-1,memlen-2,...,1]'+[0:xlen:xlen*(K-1)]),1,[])

% caculate the delay matrix
xVec=(0:xlen-memlen)'+xrow;

%compute the delay matrix
%.^ power(A ,B)得到时延项矩阵
%.*按对应元素相乘
xPow=x.*(abs(x).^(0:K-1));

%天秀啊，矩阵元素查找
%A(B)=A(B(i,j))=C;得到一个与B同样大小的矩阵
%其中C（i,j）=先把A=A=(:),然后C（i，j）=A(第B(i,j))
xVec=xPow(xVec);

%\ mldivide Ax=B 求x 相当于解系数项，跳过了前1,2,...,memlen-1项的y(n)
coef=xVec\y(memlen:xlen);

%reshape(coef,memlen,size of (coef)/memlen)相当于再拆，拆成系数项矩阵而不是一个长列。
MP_coef=reshape(coef,memlen,numel(coef)/memlen);

```

#### LMS

$$
y(n)=w^T(n)u(n)\\
e(n)=d(n)-y(n)\\
w(n+1)=w(n)+2\mu e^*(n)x(n)
$$

```
clear all;
clc;
%% data generate
% original signal
N=1000;%sample numble
data=sign(rand(N,1)-0.5);%1000*1;rand() (0,1);-0.5->(-0.5,0.5);sign()>0=1 <0=-1
% give filter taps value to calculate the first output
w=[0.8783 -0.5806 0.6537 -0.3223 0.6577 -0.0582 0.2895 -0.2710];
% caculate filter output
output=conv(data,w);%M+N-1
snr=20;
output=awgn(output,snr,'measured'); 
%% LMS

% initialization

M=8;%w.size
error_whole=zeros(1000,1);
%for k =1:100 单纯的循环没有意义。
w_lms=zeros(1,8);
for i=M:N
    input=data(i:-1:i-M+1);%8*1
    error=output(i)-w_lms*input;%1*8*8*1
    mu=0.04;
    w_lms=w_lms+mu*error*input';
    error_whole(i)=error_whole(i)+error^2;
end
%end

%% plot
figure;
error_dB=zeros(1,1000);
for p =8:1000
error_dB(p)=10*log10(error_whole(p));
end
plot(error_dB);
axis tight;         % 使用紧凑的坐标轴
legend('LMS算法');       % 图例
title('LMS算法误差曲线');  % 图标题
xlabel('样本');                     % x轴标签
ylabel('误差/dB');                  % y轴标签
grid on;                            % 网格线

    
```

One epoch
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/20220304/lms.3kri5yn5v6w0.webp)

Averange
![](https://cdn.jsdelivr.net/gh/JC-GGBond/image-JC@master/20220304/multiple-rand-signal-lms-averange.170glmzkdta8.webp)

## Paper reading

decomposition dpd

sub6G & mmwave

sub6G：

PC generated a 5G NR waveform of 64-quadrature amplitude modulation (QAM),BW = 100 MHz, and PAPR = 9.1 dB after crest factor reduction.（CFR消峰） Next, download the signal into the vector signal generator (R&S, SMW200A). Then, the signal was upconverted to 2.4 GHz.（SMW）

**For me,all in SDR with AD9363.**

 After a preamplifier, it was fed into a symmetrical Doherty PA using two Wolfspeed CGH40010 GaN transistors (CREE Inc.) with an average output power of 32.1 dBm. The 1-dB compression point of PA is P1 d B = 41 dBm.

**Choose PA**

At last, the spectrum analyzer (Keysight, N9030A) captured in-phase and quadrature (I/Q) data  fter the attenuator and sent them back to PC for coefficients extraction and predistortion.

**Demodulation and FFT**
用不同的PA模型测试，对比不同文章NMSE 25 27 35 28

mmwave:

the center frequency was selected as 28 GHz and the modulation BWs were 400 and 800 MHz. 

The test signals employed are a 5G NR waveform with the PAPR of around 9 dB by crest factor reduction and the BW of 400 and 800 MHz with 64-QAM.

 First, the ultrabroadband signals were generated in PC and downloaded into a vector signal generator (R&S, SMW200A).

Then, it was upconverted to an mmWave frequency at 28 GHz. Later, a Ka-band PA (SAGE Millimeter,Inc., Torrance, CA, USA) transmitted the signal with gain =45 dB and P1dB = 26 dBm. The average output power is set as 18.2 dBm.

A coupler was used to send a small portion of the amplified signal to the spectrum analyzer (R&S, FSW).
At last, FSW captured I/Q data and sent them back to PC.

