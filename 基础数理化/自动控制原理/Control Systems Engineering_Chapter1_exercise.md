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

## 参考及引用

[1] Control Systems Engineering 7th Ed - Nise.
