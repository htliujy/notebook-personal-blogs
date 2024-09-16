# 光子能量与LED电压

光子基本量子关系式<sup>[1]</sup>:

$$E=h\nu=\boldsymbol{\hbar}\omega$$

$$p=\frac h\lambda=\boldsymbol{\hbar}k$$

其中

- $E$为能量；
- $h$为普朗克常数：$6.62607015×10^{-34} J·s$；
- ${\displaystyle \hbar }$为约化普朗克常数或称狄拉克常数，${\displaystyle \hbar =h/{2\pi }}$；
- $ν$为频率；
- $ω$为角频率，$ω = 2πν$；
- $p$为动量的大小；
- $λ$为波长；
- $k$为波数。

光在真空中的速度为：

$$c = 299792458m/s$$

2.99792458
所以$\nu = \dfrac{c}{\lambda }$

$$
\begin{aligned}
E &=h\nu \\
&= \dfrac{hc}{\lambda} \\
&= \frac{1.9864458571489287*10^{-25}}{\lambda}J\cdot m
\end{aligned}
$$

## 光谱

可见光谱<sup>[2]</sup>:

<div  align="center">
<img src="./.assets/%E5%85%89%E5%AD%90%E8%83%BD%E9%87%8F%E4%B8%8ELED%E7%94%B5%E5%8E%8B/Linear_visible_spectrum-zh-%E5%85%89%E8%B0%B1.svg" width = "100%" height = "100%" alt="图片" align=center />
</div>

那么如果led为绿色，波长为(495+570)/2 nm= 533nm

$$
\begin{aligned}
E_{533nm} &= \frac{1.9864458571489287*10^{-25}}{\lambda}J\cdot m \\
&= \frac{1.9864458571489287*10^{-25}}{533nm}J\cdot m \\
&= 3.726915*10^{-19} J
\end{aligned}
$$

电子电荷

$$ e = -1.602176634×10^{-19} C$$

转为电子伏特：

$$
\begin{aligned}
\frac{E_{533nm}}{e} &= \dfrac{3.726915*10^{-19} J }{|-1.602176634×10^{-19}| C} \\
&= 2.326157569 V
\end{aligned}
$$

## LED 正向导通压降与光子能量的关系

发光二极管只能够往一个方向导通（通电），叫作正向偏置；当电流流过时，电子与空穴（电子空穴）在其内复合而发出单色光，这叫“电致发光效应”<sup>[3]</sup>.

不论怎么解释，比如，能量守恒定律，还是从最基本的原理出发，LED的正向导通压降，都应该大于等于电子与空穴的能级差，而理论上电子与空穴的能级差应该等于光子的能量。

那么，一个发出533nm的绿光LED，其电压应不小于2.326V，如果只是指示二极管，其电流小，导通电阻忽略，其他效应忽略，那就应该是2.326V。

$$E_{533nm} = 2.326157569 eV$$

同理，临界红外，750nm，其正向导通电压应为：

$$
\begin{aligned}
E_{750nm} &= 1.65842 eV
\end{aligned}
$$

临界紫外380nm的LED(如果有的话)：

$$
\begin{aligned}
E_{750nm} &= 3.2627 eV
\end{aligned}
$$

很明显，一些光耦的驱动端压降为1.0V左右，是红外光。

<font face="黑体" color=red>疑问：</font>

计算是单色LED，其光谱有多窄，在计算LED正偏电压时，视其为单色光是否合理？

## 参考及引用

[1] 光子. wikipedia. <https://zh.wikipedia.org/wiki/%E5%85%89%E5%AD%90>
[2] 光谱. wikipedia. <https://zh.wikipedia.org/wiki/%E5%85%89%E8%B0%B1>
[3] 发光二极管. wikipedia. <https://zh.wikipedia.org/zh-cn/%E7%99%BC%E5%85%89%E4%BA%8C%E6%A5%B5%E7%AE%A1>
