\# 测度论视角下的概率基础 (Measure-Theoretic Probability)



\## 1. 为什么我们需要测度论？

在初等概率论中，我们往往假设样本空间 $\\Omega$ 是有限的或可数的。但在量化金融（如布朗运动、随机微积分）中，我们需要处理连续时间与无限维空间。此时，传统的概率定义会失效，必须引入\*\*柯尔莫哥洛夫公理体系\*\*。



\### 1.1 概率空间的三要素 $(\\Omega, \\mathcal{F}, P)$

一个严谨的概率模型由三个部分组成：



1\.  \*\*样本空间 (Sample Space, $\\Omega$)\*\*：所有可能结果的集合。

2\.  \*\*$\\sigma$-代数 (Event Space, $\\mathcal{F}$)\*\*：所有“可测量”事件的集合。它必须满足：

&nbsp;   - $\\Omega \\in \\mathcal{F}$

&nbsp;   - 若 $A \\in \\mathcal{F}$，则 $A^c \\in \\mathcal{F}$ （对补集封闭）

&nbsp;   - 若 $A\_1, A\_2, ... \\in \\mathcal{F}$，则 $\\bigcup\_{i=1}^{\\infty} A\_i \\in \\mathcal{F}$ （对可列并封闭）

3\.  \*\*概率测度 (Probability Measure, $P$)\*\*：将事件映射到 $\[0, 1]$ 的函数，满足 $P(\\Omega)=1$ 且具有\*\*可列可加性\*\*。



> \*\*考点\*\*：

> “为什么我们需要 $\\sigma$-代数，而不是直接对 $\\Omega$ 的所有子集定义概率？”

> \*\*回答\*\*：因为在不可数空间（如实数轴）上，存在“不可测集”（如维塔利集合）。如果对所有子集定义概率，会导致矛盾。$\\sigma$-代数帮我们剔除了那些无法定义概率的“怪异集合”。



\## 2. 随机变量的本质

随机变量 $X$ 并不是一个“变量”，而是一个\*\*可测函数 (Measurable Function)\*\*：



$$

X: \\Omega \\rightarrow \\mathbb{R}

$$



它将抽象的样本点 $\\omega$ 映射为实数 $x$。

\*\*定义\*\*：对于任意实数 $x$，集合 $\\{\\omega \\in \\Omega: X(\\omega) \\leq x\\}$ 必须属于 $\\sigma$-代数 $\\mathcal{F}$。这保证了我们可以计算 $P(X \\leq x)$。



\## 3. Python 模拟：理解“几乎处处收敛”

虽然测度论很抽象，但我们可以用代码模拟其极限行为。



```python

import numpy as np

import matplotlib.pyplot as plt



\# 模拟：大数定律的收敛过程

np.random.seed(42)

n\_samples = 1000

\# 抛硬币：+1 或 -1

coin\_flips = np.random.choice(\[-1, 1], size=n\_samples)

\# 计算累积均值

cumulative\_means = np.cumsum(coin\_flips) / np.arange(1, n\_samples + 1)



plt.figure(figsize=(10, 6))

plt.plot(cumulative\_means, label='Sample Mean')

plt.axhline(0, color='r', linestyle='--', label='True Expectation (0)')

plt.title('Convergence of Sample Mean to Expectation (LLN)')

plt.xlabel('Number of Trials')

plt.ylabel('Average Value')

plt.legend()

plt.grid(True)

plt.show()

