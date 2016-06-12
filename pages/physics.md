---
layout: page
title: 量子雷达原理（一）-- 量子场论
categories: physics
...

# 预备知识 {#prelim}

## 经典动力学

在量子理论中，经典动力学对动态系统的物理规律有两种表述方法较为重要：**拉格朗日**表述和**哈密顿**表述。

### 拉格朗日表述 

物理系统由若干广义坐标 $q_a: a = 1, \cdots, n$ 
来描述，其运动规律由系统的**拉格朗日量(Lagrangian)** $L = L(q_a, 
\dot{q_a})$决定。 

**作用量(action)**定义为
$$
S = \int_{t_1}^{t_2}{L(q_a, \dot{q_a})dt}
$$

**最小作用量原理**: 系统运行的实际路径是使得作用量达到极值的路径。

\begin{align}
\delta S & = \int\_{t\_1}^{t\_2}{\delta Ldt} \\\
& = \int\_{t\_1}^{t\_2}{\Big(\frac{\partial L}{\partial q\_a}\delta q\_a + 
\frac{\partial L}{\partial \dot{q\_a}}\delta \dot{q}\_a \Big)dt} \\\
& = \int\_{t\_1}^{t\_2}{\Big[\frac{\partial L}{\partial q\_a}\delta q\_a 
- \frac{d}{dt}\left(\frac{\partial L}{\partial\dot{q}\_a}\right)\delta{q}\_a \Big]dt} 
+ \int\_{t\_1}^{t\_2}{\Big[\frac{d}{dt}\left(\frac{\partial 
L}{\partial\dot{q}\_a}\right)\delta{q}\_a + \frac{\partial 
L}{\partial\dot{q}\_a}\delta\dot{q}\_a \Big] dt} \\\
& =  \int\_{t\_1}^{t\_2}{\Big[\frac{\partial L}{\partial q\_a} 
- \frac{d}{dt}\left(\frac{\partial L}{\partial\dot{q}\_a}\right) \Big]\delta{q}\_adt} 
+ \Big(\frac{\partial L}{\partial\dot{q}\_a}\delta{q}\_a\Big)\Big\vert\_{t\_1}^{t\_2}   
\end{align}
其中 $\delta{q}\_a$是路径的变分，由于端点固定，$\delta{q}\_a(t\_1) = 
\delta{q}\_a(t\_2) = 0$.

根据**最小作用量原理**， 对所有满足上述条件的$\delta{q}_a(t)$，有$\delta{S} = 0$， 可以导出

$$
\frac{\partial L}{\partial q_a} - \frac{d}{dt}\left(\frac{\partial L}{\partial\dot{q}_a}\right)  = 0
$$

这就是**拉格朗日运动方程**.


> 定义(**连续对称**): 如果单参数映射
> 
> $$
> q_a(t) \rightarrow Q_a(s, t) \qquad s \in \mathbb{R}
> $$
> 
> 满足$Q_a(0, t) = q_a(t)$ 且
> 
> $$
> \frac{\partial}{\partial s}L(Q_a(s,t), \dot{Q}_a(s,t), t) = 0
> $$
> 
> 则称为系统的一个**连续对称**.

定义(**守恒量**): 如果广义坐标$q_a$及其导数$\dot{q}_a$和时间$t$的函数 $F(q_a, 
\dot{q}_a, t)$, 对于满足**拉格朗日运动方程**的任意函数$q_a(t)$都满足

$$
\frac{dF}{dt} = \frac{\partial F}{\partial{q}_a}\dot{q}_a
+ \frac{\partial{F}}{\partial\dot{q}_a}\ddot{q}_a 
+ \frac{\partial{F}}{\partial{t}} = 0
$$

则称$F$为**守恒量**.


**Noether 定理**:

> 每一种连续对称性都对应一个守恒量。


证明： 对应的守恒量为 

$$
F = \frac{\partial{L}}{\partial\dot{q}_a}
\frac{\partial{Q}_a}{\partial{s}}\Big\vert_{s=0}
$$

因为

\begin{align}
\frac{dF}{dt} & =
\frac{d}{dt}\Big(\frac{\partial{L}}{\partial\dot{q}\_a}\Big)  
\frac{\partial{Q}\_a}{\partial{s}}\Big\vert\_{s=0} + 
\frac{\partial{L}}{\partial\dot{q}\_a}
\frac{\partial\dot{Q}\_a}{\partial{s}}\Big\vert\_{s=0}  
\\\ & = \frac{\partial{L}}{\partial{q}\_a}
\frac{\partial{Q}\_a}{\partial{s}}\Big\vert\_{s=0} + 
\frac{\partial{L}}{\partial\dot{q}\_a}
\frac{\partial\dot{Q}\_a}{\partial{s}}\Big\vert\_{s=0}  
\qquad\qquad \text{根据拉格朗日运动方程}
\\\ & =  \frac{\partial}{\partial{s}}{L(Q\_a(s, t), \dot{Q}\_a(s,t), t)}\Big\vert\_{s=0}
\\\ &= 0
\end{align}


注： 为使表达简洁，上面的表达式采用了**爱因斯坦求和规则**，
同一项中下标重复出现则需对该指标所有可能的值进行求和，
即省略求和符号$\sum\_{a=1}^{n}$.

## 哈密顿表述

**哈密顿(Hamilton)表述** 是对 **拉格朗日表述** 进行 **勒让德(Legendre)变换** 得到的等价表述。

系统的**哈密顿量**定义为
$$
H(q, p) = p^a\dot{q}_a - L
$$
其中, 
$$
p^a = \frac{\partial{L}}{\partial{q_a}}
$$
称为**动量**.

经过上述**勒让德(Legendre)变换**， **拉格朗日运动方程**变为如下的**哈密顿运动方程**:

$$
\dot{q}^a = \frac{\partial{H}}{\partial{p^a}}, \qquad
\dot{p}^a = - \frac{\partial{H}}{\partial{q_a}}
$$

哈密顿表述具有某种对称性：这里广义坐标$q_a$与对应的广义动量$p^a$的地位是平等的，
\\((q, p)\\) 所有可能的取值集合称为**相空间**。


**泊松括号**:  $f(q, p)$和$g(q, p)$是两个相空间上的函数，它们的**泊松括号**定义为
$$
\{f, g\} = \frac{\partial{f}}{\partial{q}_a}\frac{\partial{g}}{\partial{p}^a} 
- \frac{\partial{f}}{\partial{p}^a}\frac{\partial{g}}{\partial{q}_a} 
$$

泊松括号具有以下性质：

\begin{align}
\{f, g\} & = -\{g, f\} \\\
\{p^a, p^b\} & 
= \frac{\partial{p^a}}{\partial{q_i}} \frac{\partial{p^b}}{\partial{p^i}} 
- \frac{\partial{p^a}}{\partial{p^i}} \frac{\partial{p^b}}{\partial{q_i}} 
  = \frac{\partial{p^a}}{\partial{q_b}} - \frac{\partial{p^b}}{\partial{q_a}} 
  = \frac{\partial^2{L}}{\partial{q_b}\partial{q_a}} - \frac{\partial^2{L}}{\partial{q_a}\partial{q_b}} 
= 0 \\\
\{q_a, q_b\} & 
= \frac{\partial{q_a}}{\partial{q_i}} \frac{\partial{q_b}}{\partial{p^i}} 
- \frac{\partial{q_a}}{\partial{p^i}} \frac{\partial{q_b}}{\partial{q_i}} 
  = \frac{\partial{q_b}}{\partial{p^a}} - \frac{\partial{q_a}}{\partial{p^b}} 
  = \Big(\frac{\partial{p^a}}{\partial{q_b}}\Big)^{-1} - \Big(\frac{\partial{p^b}}{\partial{q_a}}\Big)^{-1}
= 0 \\\
\{q_a, p^b\} & 
= \frac{\partial{q_a}}{\partial{q_i}} \frac{\partial{p^b}}{\partial{p^i}} 
- \frac{\partial{q_a}}{\partial{p^i}} \frac{\partial{p^b}}{\partial{q_i}} 
= \delta_{a}^{b} \\\
\end{align}


## 量子力学

在经典力学中，系统的状态用相空间的一个点$(q_a, p_a)$来表示； 
在量子力学中，系统的状态用**希尔伯特空间**中的一个向量$\mid\psi\rangle$来表示。
经典力学中的物理量$f(q,p)$ 对应为量子力学中的酉算子$\hat{f}$。

两个算子$\hat{f}$与$\hat{g}$的対易算子定义如下：
$$
[\hat{f}, \hat{g}] = \hat{f}\hat{g} - \hat{g}\hat{f}
$$

经典的泊松括号与量子理论的対易算符有如下对应关系：
$$
\{, \} \longleftrightarrow -\frac{i}{\hbar}[, ]
$$
特别地，
$$
[\hat{q}_a, \hat{q}_b] = 0, \quad  [\hat{p}^a, \hat{p}^b] = 0, \quad [\hat{q}_a, \hat{p}^b] = i\hbar\delta_{a}^{b}
$$
这一过程称为**经典量子化**.


量子系统的特性由**哈密顿算子** $\hat{H}$ 决定。动力学方程由如下的**薛定谔方程**给出
$$
i\hbar\frac{d}{dt}\left|\psi\right\rangle = \hat{H} \left|\psi\right\rangle
$$

量子系统的**定态**是指哈密顿算子的本征态$|\psi\rangle$
$$
\hat{H} |\psi\rangle = E |\psi\rangle 
$$
它具有确定的能量，对应的本征值$E$即能量。

上面的**薛定谔方程**是在**薛定谔表象**中描述量子系统的，即状态\\(\|\psi\rangle\\)随时间演化，而算子\\(\hat{O}\\)不随时间变化。

**海森堡表象**则刚好相反，即状态\\(\|\psi\rangle\\)不随时间变化，而算子\\(\hat{O}\\)随时间演化。两者之间的关系为

\begin{align}
|\psi\rangle_H &= e^{i\hat{H}t/\hbar} |\psi\rangle_S \\\
\hat{O}_H &= e^{i\hat{H}t/\hbar} \hat{O}_S e^{-i\hat{H}t/\hbar} 
\end{align}

算子的演化方程为
$$
\frac{d}{dt}\hat{O}_H  = \frac{i}{\hbar}[\hat{H}, \hat{O}_H]
$$

两者的等价性通过
$$
\langle{\psi_H\lvert\hat{O}_H\rvert\phi_H}\rangle = 
\langle{\psi_S\lvert e^{-i\hat{H}t/\hbar} \hat{O}_H e^{i\hat{H}t/\hbar} \rvert\phi_S}\rangle = 
\langle{\psi_S\lvert \hat{O}_S \rvert\phi_S}\rangle  
$$
证明。

除此之外，还存在**狄拉克表象**，它是薛定谔表象和海森堡表象的混合，常用于研究物质与场的相互作用，也称为**相互作用表象**.

采用自然单位使$\hbar = 1$， 可以省略$\hbar$；在上下文意义明确的情况下，可以省略算子的$\hat{}$。 

## 狭义相对论

## 傅里叶变换

## 狄拉克delta函数

## 复变函数


