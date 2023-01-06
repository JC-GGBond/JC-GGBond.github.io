---
title: thesis_architecture
date: 2022-10-20 16:23:36
tags:
categories: final project DPD
mathjax: true
---

看其他人的硕士毕业论文确定整个文章的结构.


## Background


### 使用MATLAB+SDR的意义
https://ww2.mathworks.cn/videos/simplify-the-implementation-of-software-defined-radio-in-hardware-1510052703793.html?s_tid=srchtitle_%25E5%25B0%2584%25E9%25A2%2591_5

在日益复杂的无线通信协议标准发展下，
分离组件单独设计的传统开发模式过程繁琐，
组合调试难度大。

MATLAB提出了基于模型设计的设计流程。


可以灵活高效的，
进行软件无线电设备的原型实现。



### non-linear distortion

### DPD Block diagram


### PA model
**MP（Memory Polynomial）:**
$$
z(n)=\sum_{k=1}^{K}\sum_{q=0}^{Q}a_{kq}x(n-q)|x(n-q)|^{k-1}
$$
**Plug the above formula  into the variables in the block diagram:**
$$
z(n)=\vec y \alpha
$$
**Which:**
$$
\vec y=[\phi_{10}(y(n)),\phi_{11}(y(n)),\phi_{12}(y(n)),\phi_{13}(y(n)),\dots\dots,\phi_{KQ}(y(n))]\\
\phi_{kq}(y(n))=y(n-q)|y(n-q)|^{k-1}\\
$$
**and:**
$$
\alpha=[a_{10},\dots \dots,a_{1Q},a_{21},\dots \dots,a_{KQ}]^{T}
$$

---



### Calculation algorithm


**Select:**
$$
\vec y_{o}=[y(n),y(n+1),\dots\dots,y(n+N-1)]^{T}
$$
**Now:**
$$
\vec z=Y\alpha
$$
**Which:**
$$
\vec z=[z(n),z(n+1),\dots\dots,z(n+N-1)]\\
Y=[\phi_{10}(\vec y_{o}),\phi_{11}(\vec y_{o}),\phi_{12}(\vec y_{o}),\phi_{13}(\vec y_{o}),\dots\dots,\phi_{KQ}(\vec y_{o})]
$$

---



### 3.2 Optimize algorithm

#### 3.2.1 LS  (Least Square)

**Target:**
$$
min||\vec z-Y\alpha||_{2}^2
$$
**So：**
$$
\frac{\partial ||\vec z-Y\alpha||_{2}^2}{\partial \alpha}=\frac{\partial (\vec z^{H}\vec z-2\alpha^{H}Y^{H}\vec z+\alpha^{H}Y^{H}Y\alpha)}{\partial \alpha}=2(Y^{H}Y\alpha-Y^{H}\vec z)\\
$$
**Let it equal to zero:**
$$
\alpha=(Y^{H}Y)^{-1}Y^{H}\vec z
$$
**Q:**

$r(Y^{H}Y)\le min\{r(Y^{H}),r(Y)\}$，$inv(Y^{H}Y)$ **may not exist**

---



#### 3.2.2 QR decomposition

**Principle：**

$Y \in \mathbb{R}^{m\times n} ,m\ge n$， $Y=QR$，**while** $Q\in \mathbb{R}^{m\times m}$**is orthogonal matrix**，$R\equiv  \left[\begin{array}{c} \hat{R} \\0 \end{array} \right] \in \mathbb{R^{m\times n}}$，$\hat{R} \in \mathbb{R^{n\times n}}$ **is Upper triangular matrix**

**Let:** $Y=QR$
$$
\alpha=(R^{H}Q^{H}QR)^{-1}R^{H}Q^{H}\vec z\\
$$
**Because:**  $Q^{H}Q=E$
$$
\alpha=R^{-1}R^{-H}R^{H}Q^{H}\vec z\\
\alpha=R^{-1}Q^{H}\vec z\\
R\alpha=Q^H\vec z
$$
$\alpha$ **can be solved by solving homogeneous equations from bottom to top**
