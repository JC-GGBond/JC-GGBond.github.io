---
title: Presentation20211128
date: 2022-01-27 23:56:51
tags:
categories: Presentation
mathjax: true
---
<h1 align = "center">
    Presentation 2021.11.28<br>
    Adaptive Filter Theory
</h1>




## 1.Future innovation points: Algorithm optimization



## 2.Algorithm comparison

### 2.1 LS（method of least squares）

#### Target:

$$
min||\vec z-Y\alpha||_{2}^2
$$

#### So:

$$
\frac{\partial ||\vec z-Y\alpha||_{2}^2}{\partial \alpha}=\frac{\partial (\vec z^{H}\vec z-2\alpha^{H}Y^{H}\vec z+\alpha^{H}Y^{H}Y\alpha)}{\partial \alpha}=2(Y^{H}Y\alpha-Y^{H}\vec z)\\
$$

#### Let it equal to zero:

$$
\alpha=(Y^{H}Y)^{-1}Y^{H}\vec z
$$

### 2.2 LMS (least mean squares)

$$
y(n)=\hat{w}^{H}(n)u(n)\\
e(n)=d(n)-y(n)\\
\hat{w(n+1)}=\hat{w(n)}+\mu u(n)e^{*}(n)
$$



### 2.3 RLS (Recursive least squares)

$$
e(n)=y(n)-\boldsymbol{w}^{\mathrm{H}}(n-1) \boldsymbol{x}(n) \\
\boldsymbol{k}(n)=\frac{\boldsymbol{P}(n-1) \boldsymbol{x}(n)}{\lambda+\boldsymbol{x}^{\mathrm{H}}(n) \boldsymbol{P}(n-1) \boldsymbol{x}(n)} \\
\boldsymbol{P}(n)=\frac{1}{\lambda}\left[\boldsymbol{P}(n-1)-\boldsymbol{k}(n) \boldsymbol{x}^{\mathrm{H}}(n) \boldsymbol{P}(n-1)\right] \\
\boldsymbol{w}(n)=\boldsymbol{w}(n-1)+\boldsymbol{k}(n) e^{*}(n)
$$



### 2.4 Comparison

#### Basic：Wiener filter

$$
e(n)=d(n)-y(n)
$$

actually we need $y(n)$ to divide Gain here
$$
J=\mathbb{E}[e^{2}(n)]\\
\nabla_{k}J=0
$$
get Canonical equation,Wiener-Hoof equation

| LS                                     | LMS                         | RLS                |
| -------------------------------------- | --------------------------- | ------------------ |
| Matrix operation, a lot of calculation | Stochastic gradient descent | more Fast than LMS |





## 3.Hardware platform

### Adalm-pluto


