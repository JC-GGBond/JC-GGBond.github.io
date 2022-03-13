---
title: Presentation20201023
date: 2022-01-27 23:18:02
tags:
categories: Presentation
mathjax: true
---
<h1 align="center">
    Presentation in 20201023
</h1>


<h2 align ="center">Speaker: Jingci Zhu</h2>

## Preface

I want to use another form to show the works of mine during the last two weeks in this presentation ! (Actually, I learned this way in last two weeks!)

╮(￣▽ ￣)╭╮(￣▽ ￣)╭╮(￣▽ ￣)╭╮(￣▽ ￣)╭╮(￣▽ ￣)╭╮(￣▽ ￣)╭╮(￣▽ ￣)╭╮(￣▽ ￣)╭╮(￣▽ ￣)╭

__Q__: What is __markdown__ ?

​		__Markdown__ is one lightweight markup language. Lightweight markup languages use simple markup syntax to  describe simple format description.

For example:

~~~html
<h3 align = "center">
    hello, Prof.Zhang and every student in 404 lab! 
</h3>
<h6 align = "center">
    Here is the second Presentation by Jingci Zhu.
</h6>
~~~

Well, we can see the result:

<h3 align = "center">
    Hello, Prof.Zhang and every student in 404 lab! 
</h3>
<h6 align = "center">
    Here is the second Presentation by Jingci Zhu.
</h6>




We can find it is simple and fast to use __markdown__ to edit our text! At the same time, it can also show the code with highlights as you just saw.

By the way, the app which I edited this text is __Typora__. It is one __markdown__ editor.



<h3 align = "center">
    Well, Let's start the presentation!
</h3>




## Contents

[1.Something about the last presentation](# 1.Something about the last presentation)

[2.Electromagnetic theory](2.Electromagnetic theory)

### 1.Something about the last presentation

* The principle of dipole antenna

  	A dipole means one positive and one negative charge placed a distance apart. As the Coulomb low:

  $$
  \vec{F}=k \frac{q_{1} q_{2}}{r^{2}} \overrightarrow{e_{r}}
  $$

   we can know their have interaction force between two charges, which makes them do __simple harmonic motion__.That means they doing __sinusoidal motion__.

  

Consider the oscillating electric dipoles as a __sinusoidal current__ :
$$
i(t)=I * \cos (\omega t)=\operatorname{Re}\left[I e^{j \omega t}\right]
$$
Use micro element method:
$$
J d V^{\prime}=e_{z} \frac{I}{\Delta s^{\prime}} \Delta s^{\prime} d z^{\prime}=e_{z} I d z
$$
At the same time, as the maxwell' s functions and field theory, we use potential method to describe time-varying electromagnetic field:
$$
\nabla \cdot \vec{B}=0 \quad  \quad \vec{B}=\nabla \times \vec{A}
$$
So get the A(r),
$$
\vec{A(r)}=\frac{u_{0}}{4 \pi} \int_{l} \frac{e_{z} I}{\left|r-r^{\prime}\right|} e^{-j k\left|r-r^{\prime}\right|}
$$


$$
\begin{array}{c}
\vec{A(r)}=e_{z} \frac{u_{0} I l}{4 \pi r} e^{-j k r} \\
\end{array}
$$

 while I<<r, we can approximate it.
$$
\left\{\begin{array}{l}
A_{r}=A_{z} \cos (\theta)=\frac{u_{0} I l}{4 \pi r} \operatorname{cosi}(\theta) e^{-j k r} \\
A_{\theta}=-A_{z} \sin (\theta)=\frac{u_{0} I l}{4 \pi r} \sin (\theta) e^{-j k r} \\
A_{\phi}=0
\end{array}\right.
$$
Finally, use maxwell's functions to get __E__ and __H__.
$$
\vec{H}=\frac{1}{u_{0}}\nabla  \times \vec{A}
$$

$$
\vec{E}=\frac{1}{j \omega \varepsilon_{0}} \nabla \times \vec{H}
$$

(The derivation of the powerline equation is complicated and is omitted here)

Next, we will simulate the radiation process.

* Figure __Powerline__

  

* Gif of __radiation__

  

* Figure in __far field__

  

  ### 2.Electromagnetic theory

  * __TE and TM__

    

  * __Plane wave,  spherical wave, cylindrical wave,__

    The differences of them are the different Equiphase surface.

    

  * __Linear polarization, circular polarization, elliptic polarization__

    The path of an electric vector as a radio wave travels

    

    ### 3.Works for course: __Electromagnetic mathematical__

    * Why the formula below is an cylindrical wave?

    $$
    E=\frac{E_{max}}{\sqrt{r}}cos(kr-\omega t)
    $$

    Use matlab to solve it:

    ~~~matlab
    Emax=5;
    r=0.01:0.01:4;
    k=pi;
    w=2*pi;
    for t=0.01:0.01:10
        for i=1:400
            E(i)=(Emax/sqrt(r(i)))*cos(k*r(i)-w*t);
        end
    plot(r,E,'.');
    ~~~

    Get the result:

    __Figure in a moment in time __

    (__Cylindrical coordinates__ ，and X label is the __radius__, Y label is the __Electric field intensity__)

    

    __Gif of it__:

    

    ​                                                 

    * __Bessel function__

      

  ### 4.Our 'academic' Trip to ShangHai for IME 2020  (☆＿☆)

  * __My focus__



  

##  Reference

1. [The simulation of dipole radiation](https://wenku.baidu.com/view/34f5586f79563c1ec5da71b1.html)
2. MATLAB SIMULATION FOR ELECTROMAGNETIC FIELDS AND MICROWAVE TECHNOLOGY



<h1 align ="center">Thanks To Your Careful Guidence</h1>










