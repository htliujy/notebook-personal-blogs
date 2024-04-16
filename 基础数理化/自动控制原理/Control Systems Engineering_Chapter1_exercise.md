# Control Systems Engineering_Chapter1_exercise

1、电位器的输入，输出和增益：
答：

input: angle, $\theta$;
output: Voltage, $V_o$;
gain: 

$$G = \frac{50V-(-50V)}{10Turns \cdot 2\pi rad/Turn}$$

得到：

$$G = 1.5915 V/rad$$

2、暂缺

......

18、RL 电路：
a、当输入v(t)为单位阶跃信号u(t)，系统的微分方程：

$$Ldi/dt + Ri = u(t)$$

b、零状态响应（答案用的是寻找特征方程的方法来得到答案的）

$$i(t) = \frac{u(t)}{R}(1-e^{-(R/L)t})$$

参考答案中的输入u(t)没有量纲，导致计算结果i的量纲是导纳而不是电流。

c、Make a plot of your solution if R/L = 1
答：略

不过R/L应该有量纲，此处未写。

20、 解方程（假设零初始条件）

a. $\dfrac{dx}{dt}+7x=5\cos2t$

b. $\dfrac{d^2x}{dt^2}+6\frac{dx}{dt}+8x=5\sin3t$

c. $\dfrac{d^2x}{dt^2}+8\dfrac{dx}{dt}+25x=10u(t)$

解答：

a. 先求对应齐次方程的解，对应齐次方程的特征方程为：
$$\lambda+7=0\implies\lambda=-7$$

那么有对应齐次方程的解为：

$$x_h = c_1e^{-7x}$$

对于特解，假设特解的形式为：$x_p = c_2sin(2t) + c_3cos(2t)$，有：

$$x'_p = 2[c_2cos(2t) -c_2sin(2t)]$$

带入原方程得到：

$$2[c_2cos(2t) -c_3sin(2t)] + 7 [c_2sin(2t) + c_3cos(2t)]= 5cos(2t)$$

得到：

$$2c_2 + 7c_3 = 5$$
$$7c_2 - 2c_3 = 0$$

解出：

$$c_2 = \dfrac{10}{53}$$

$$c_2 = \dfrac{35}{53}$$

那么通解为：

$$x = c_1e^{-7t} + \dfrac{10}{53}sin(2t) + \dfrac{35}{53}cos(2t)$$

带入初始条件：$x(0)=0$得到$c_1 = -\dfrac{35}{53}$

最终得到：

$$x = -\dfrac{35}{53}e^{-7t} + \dfrac{10}{53}sin(2t) + \dfrac{35}{53}cos(2t)$$

[参考](https://quizlet.com/explanations/textbook-solutions/control-systems-engineering-7th-edition-9781118963579/chapter-1-problems-20-a9f33c4b-c455-4471-b941-cc6629fa0409)

b. 对应齐次方程求解：

齐次方程的特征方程为：

$$\lambda^2+6\lambda+8=0$$

求得根为$\lambda = -2$或$\lambda = -4$

那么有：

$$x_h = c_1e^{-2x} + c_2e^{-4x}$$

假定特解的形式为：

$$x_p = c_3sin(3t) +c_4cos(3t)$$

有：$y'= 3c_3cos(3t)-3c_4sin(3t)$以及$y'' = -9c_3sin(3t)-9c_4cos(3t)$，带入原返程得到：

$$-9c_3sin(3t)-9c_4cos(3t) + 6[3c_3cos(3t)-3c_4sin(3t)] + 8[c_3sin(3t) +c_4cos(3t)]= 5sin(3t)$$

化简得到

$$cos(3t)(-9c_4 + 18c_3 + 8c_4) = 0$$

$$sin(3t)(-9c_3 - 18c_4 + 8c_3) = 5sin(3t)$$

解方程：

$$18c_3 - c_4 = 0$$

$$-c_3 - 18c_4 = 5$$

得到$c_3 = -\dfrac{1}{65}$, $c_4 = -\dfrac{18}{65}$，因此通解为：

$$x = c_1e^{-2x} + c_2e^{-4x} - \dfrac{1}{65} sin(3t) - \dfrac{18}{65} cos(3t)$$

根据零初始条件：$x(0)= 0$以及$x'(0)=0$

有

$$c_1 + c_2 - \dfrac{18}{65} = 0$$

$$-2c_1 -4c_2 - 3\dfrac{1}{65} = 0$$

求得$c_1 = \dfrac{15}{26}$, $c_2 = -\dfrac{3}{10}$

解得x为：

$$x = \dfrac{15}{26}e^{-2x} - \dfrac{3}{10}e^{-4x} - \dfrac{1}{65} sin(3t) - \dfrac{18}{65} cos(3t)$$

c. 假设应齐次方程的解为：

$$x = c_1 e^{\lambda t}$$

特征方程为：

$$\lambda^2 +8\lambda +25 = 0$$

解得$\lambda = \frac{-8± \sqrt{64 - 100}}{2}$,也就是$\lambda = -4 ± 3i$

那么有对应齐次方程的解为

$$
\begin{aligned}
x_h &= c_1e^{(-4+3i)t} + c_2e^{(-4-3i)t} \\
&= e^{-4t}(c_1e^{3it}+c_2e^{-3it})\\
&= e^{-4t}[c_1 cos(3t) + c_1 i sin(3t) + c_2 cos(3t) -c_2i sin(3t)]\\
&= e^{-4t}[acos(3t) + b i sin(3t)]
\end{aligned}
$$

疑问，$bi$中的i可否省略，也就是将常量$i$融入$b$变量中

假设其特解为：

$$x_p = C$$

解得 $C= \dfrac{2}{5}$

那么有：

$$x = e^{-4t}[acos(3t) + b i sin(3t)] + \dfrac{2}{5}$$

$$
\begin{aligned}
x' &= -4e^{-4t}[acos(3t) + b i sin(3t)]+e^{-4t}[-3asin(3t) +3bicos(3t)]\\
\end{aligned}
$$

将零初始条件$x(0) = 0$, $x'(0)=0$ 带入，得到：

$$a + \dfrac{2}{5} = 0 \implies a = -\dfrac{2}{5}$$

$$-4a + 3 bi = 0 \implies bi = -\dfrac{8}{15}$$

带入x方程，得到：

$$x = e^{-4t}[-\dfrac{2}{5}cos(3t) -\dfrac{8}{15}sin(3t)] + \dfrac{2}{5}$$

21、解方程

a.

$$\dfrac{d^{2}x}{dt^{2}}+2\dfrac{dx}{dt}+2x=\sin2t$$
$$x(0)=2;\dfrac{dx}{dt}(0)=-3$$

解：假设特解为：

$$x_p = Acos(2t) + Bsin(2t)$$

那么有$x'_p = -2Asin(2t) + 2Bcos(2t)$, $x''_t = -4A cos(2t) -4B sin(2t)$，带入原方程，得到：

$$[-4A cos(2t) -4B sin(2t)] +2 [-2Asin(2t) + 2Bcos(2t)] + 2[Acos(2t) + Bsin(2t)] = sin(2t)$$

得到

$$sin(2t)(-4B -4A+ 2B) = sin(2t) \implies -2B - 4A = 1$$

同理，得到：

$$(4B -2A= 0)$$

求得：$A = -\dfrac{1}{5}$,$B = -\dfrac{1}{10}$，代入设定特解方程，得到：

$$x_p = -\dfrac{1}{5}cos(2t) -\dfrac{1}{10}sin(2t)$$

求齐次方程的通解，设为

$$x_h = C' e^{\lambda t}$$

其特征方程为：

$$\lambda ^2 +2 \lambda + 2 =0$$

解得$\lambda = -1 ± i$, 因此：

$$x_h = e^{-t}[Ccos(t)+Dsin(t)]$$

$$
\begin{aligned}
x &= x_p + x_h \\
&= -\dfrac{1}{5}cos(2t) -\dfrac{1}{10}sin(2t) + e^{-t}[Ccos(t)+Dsin(t)]
\end{aligned}
$$

再根据初始条件，可得：

$$-\dfrac{1}{5} + C = 2 \implies C = \dfrac{11}{5}$$

$$-\dfrac{1}{5} + (-C +D)= -3 \implies D = -\dfrac{15}{5} + \dfrac{1}{5} +\dfrac{11}{5} = -\dfrac{3}{5}$$

最终解为：

$$x = -\dfrac{1}{5}cos(2t) -\dfrac{1}{10}sin(2t) + e^{-t}[\dfrac{11}{5}cos(t)-\dfrac{3}{5}sin(t)]$$

b.

$$\dfrac{d^{2}x}{dt^{2}}+2\dfrac{dx}{dt}+x=5e^{-2t}+t$$

$$x(0)=2;\dfrac{dx}{dt}(0)=1$$

解答：

假设特解的形式为：

$$x_p =Ae^{-2t} + Bt + C$$

那么有$x' = -2Ae^{-2t} + B$, $x'' = 4Ae^{-2t}$，带入原方程，有：

$$4Ae^{-2t} + 2(-2Ae^{-2t} + B) + Ae^{-2t} + Bt + C = 5e^{-2t}+t$$

得到：

$$e^{-2t}(4A -4A+A) = 5e^{-2t}$$

$$2B + C = 0$$

$$Bt = t$$

得到$A = 5$, $B = 1$, $C = -2$.

特征方程为：

$$\lambda ^2 +2 \lambda + 1 = 0$$

解得：$lambda = -1$，重根。

那么对应的解为:

$$x_h = (Dt + E)e^{-t}$$

因此，又：

$$
\begin{aligned}
x &= x_p + x_h\\
&=(Dt + E)e^{-t} + Ae^{-2t} + Bt + C\\
&=Dte^{-t} + Ee^{-t}+ 5e^{-2t} + t -2
\end{aligned}
$$

将初始条件$x(0)=2;\dfrac{dx}{dt}(0)=1$代入，得到：

$$x(0) = E + 5 -2 = 2 \implies E = -1$$

$$
\begin{aligned}
\dfrac{dx}{dt}(0) &= De^{-t} -Dte^{-t} -Ee^{-t} -10e^{-2t} + 1 \\
&= D -E - 10 + 1\\
&= 1
\end{aligned}
$$

得到 $$D = 9$$, 将D，E的值带入，得到最终解：

$$x(t) = 9te^{-t} - e^{-t}+ 5e^{-2t} + t -2$$

c.

$$\frac{d^{2}x}{dt^{2}}+4x=t^{2}$$

$$x(0)=1;\frac{dx}{dt}(0)=2$$

解答

假设特解的形式为$x = At^2 + Bt + C$，有$x' = 2At + B$,$x''= 2A$，那么：

$$2A + 4(At^2 + Bt + C) = t^2$$

得到$A= \frac{1}{4}$, $B = 0$, $C = -\frac{1}{8}$

对应齐次方程的特征方程为：$\lambda ^2 + 4 = 0$

解得$\lambda = ±2i$

那么对应齐次方程的通解为：

$$x_h = Dsin(2t) + E cos(2t)$$

$$
\begin{aligned}
x &= x_p+ x_h\\
&= \frac{1}{4}t^2 -\frac{1}{8} + Dsin(2t) + E cos(2t)
\end{aligned}
$$

根据初始条件$x(0)=1;\frac{dx}{dt}(0)=2$

可以得到：

$$-\frac{1}{8} + E = 1 \implies E = \frac{9}{8}$$

$$2D = 2 \implies D = 1$$

将D，E的值带入x的解，最终得到：

$$x(t) = \frac{1}{4}t^2 -\frac{1}{8} + sin(2t) + \frac{9}{8}cos(2t)$$

## 参考及引用

[1] Control Systems Engineering 7th Ed - Nise.
[2] 参考答案. <https://quizlet.com/explanations/textbook-solutions/control-systems-engineering-7th-edition-9781118963579/chapter-1-problems-20-a9f33c4b-c455-4471-b941-cc6629fa0409>
