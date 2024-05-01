# Chapter2 Modeling in the Frequency Domain

拉普拉斯变换的定义：

$$\mathscr{L}[f(t)]=F(s)=\int_{0-}^{\infty}f(t)e^{-st}dt$$

其中: $s=\sigma+j\omega$

拉普拉斯变换跟傅里叶变换差异？拉普拉斯变换的适用范围更广，其更容易达到收敛条件。

$$\mathscr{L}^{-1}[F(s)]=\dfrac{1}{2\pi j}\int_{\sigma-j\infty}^{\sigma+j\infty}F(s)e^{st}ds=f(t)u(t)$$

## 参考及引用
