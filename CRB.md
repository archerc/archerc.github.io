# 信号宽度的估计精度分析
设信号模型为
$$
y(t) = x(t; T) + w(t)
$$

其中, $w(t)$为复高斯平稳白噪声随机过程，方差为$\sigma^2 = 1$。

$$
x(t;T) = \left\{ 
\begin{array}{rl}
A & t_0 \le t < t_0 + T \\
0 & \text{else} 
\end{array} 
\right.
$$

对数似然函数为
$$
\begin{aligned}
\ln p(\mathbf{y}|T) & = \sum_{t=t_0}^{t_N}{\ln p(y(t)|T)} \\\\
& = \sum_{t=t_0}^{t_N}{\left[- \| y(t) - x(t; T) \|^2  + \text{const}\right]} \\\\
& = - \sum_{t=t_0}^{t_N}{|y(t)|^2} - \sum_{t=t_0}^{t_N}{|x(t; T)|^2} + \sum_{t=t_0}^{t_N}{2\operatorname{Re}[x^{\ast}(t; T) y(t)]} + \text{const} \\\\
& = - |A|^2 \lceil{T}\rceil + \sum_{t=t_0}^{t_0 + T}{2\operatorname{Re}[y(t)]} + \text{const} \\\\
\end{aligned}
$$

如果将$T$视为连续变量，上式并不是关于$T$的处处可导函数: 

- 在$T$为非整数处，对数似然函数对$T$的导数为0；

- 但是在$T$为整数处，对数似然函数对$T$不可导。

估计理论中克莱美罗界(CRB)为
$$
\operatorname{var}(\hat{\theta}) \ge \frac{1}{I(\theta)} = {\mathbb{E}\left[
\left(\frac{\partial \ln p(\mathbf{y}|\theta)}{\partial\theta}\right)^2
\right]}^{-1}
= - {\mathbb{E}\left[\frac{\partial^2 \ln p(\mathbf{y}|\theta)}{\partial\theta^2}
\right]}^{-1}
$$
上式成立是有条件的，即

$$
\frac{\partial}{\partial\theta}\ln p(\mathbf{y}|\theta)
$$
必须存在。

而在$T$为整数时，$\frac{\partial}{\partial{T}}\ln p(\mathbf{y}|T)$ 不存在。

结论： 将$T$分解成整数部分和小数部分，分别进行估计。

对于整数部分，可以通过比较似然函数的大小来估计，这实质上是一个$N$元假设检验问题，需要通过错误概率来描述估计的准确程度，均方根误差的概念不适用。

对于小数部分，因为对数似然函数与小数部分无关，实质上无法估计，也就无所谓精度。


