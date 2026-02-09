# 测度论视角下的概率基础 (Measure-Theoretic Probability)

## 1. 为什么我们需要测度论？

在初等概率论中，我们往往假设样本空间 $\Omega$ 是有限的或可数的。但在量化金融（如布朗运动、随机微积分）中，我们需要处理连续时间与无限维空间。此时，传统的概率定义会失效，必须引入**柯尔莫哥洛夫公理体系**。

### 1.1 概率空间的三要素 $(\Omega, \mathcal{F}, P)$

一个严谨的概率模型由三个部分组成：

1.  **样本空间 (Sample Space, $\Omega$)**：所有可能结果的集合。
2.  **$\sigma$-代数 (Event Space, $\mathcal{F}$)**：所有“可测量”事件的集合。它必须满足三个条件：
    * $\Omega \in \mathcal{F}$ （全集在其中）
    * 若 $A \in \mathcal{F}$，则 $A^c \in \mathcal{F}$ （对补集封闭）
    * 若 $A_1, A_2, ... \in \mathcal{F}$，则 $\bigcup_{i=1}^{\infty} A_i \in \mathcal{F}$ （对可列并封闭）
3.  **概率测度 (Probability Measure, $P$)**：将事件映射到 $[0, 1]$ 的函数，满足 $P(\Omega)=1$ 且具有**可列可加性**（$\sigma$-additivity）。

> **💡 考点**
>
> **Q:** 为什么我们需要 $\sigma$-代数，而不是直接对 $\Omega$ 的所有子集定义概率？
>
> **A:** 因为在不可数空间（如实数轴）上，存在“不可测集”（如维塔利集合）。如果强行对所有子集定义概率，会导致数学上的矛盾。$\sigma$-代数帮我们剔除了那些无法定义概率的“怪异集合”，保证了概率论的相容性。

---

## 2. 随机变量的本质

随机变量 $X$ 并不是一个“变量”，而是一个**可测函数 (Measurable Function)**：

$$
X: \Omega \rightarrow \mathbb{R}
$$

它将抽象的样本点 $\omega$ 映射为实数 $x$。

**定义**：对于任意实数 $x$，集合 $\{\omega \in \Omega : X(\omega) \leq x\}$ 必须属于 $\sigma$-代数 $\mathcal{F}$。

$$
X^{-1}((-\infty, x]) \in \mathcal{F}, \quad \forall x \in \mathbb{R}
$$

这保证了我们可以计算 $P(X \leq x)$，即累积分布函数 (CDF) 是存在的。

---