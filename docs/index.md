# Quant Research Knowledge Base

!!! quote "Philosophy"
    **"Probability is the logic of science."** — E. T. Jaynes
    
    这是一个基于 **Docs as Code** 理念构建的个人量化研究知识库。旨在将数理统计、随机过程与金融工程的理论体系，与 Python 量化实战代码深度融合，为博士入学考试及未来的量化职业生涯打下坚实的数理基础。

---

## 🗺️ 知识图谱 (Knowledge Architecture)

本项目采用模块化结构，目前规划的核心板块如下：

* :material-function: **[概率论与测度 (Probability & Measure)](01_Probability/01_basic_concepts.md)**
    * 从柯尔莫哥洛夫公理体系出发，深入理解测度、可测函数与随机变量本质。
    * 涵盖大数定律、中心极限定理及各类收敛性的严格证明。
* :material-chart-bell-curve: **数理统计推断 (Statistical Inference)** *(Construction)*
    * 参数估计（MLE/矩估计）、假设检验（N-P引理）、贝叶斯推断。
    * 线性模型与广义线性模型 (GLM)。
* :material-finance: **金融随机分析 (Stochastic Calculus)** *(Planned)*
    * 布朗运动、伊藤引理 (Itô's Lemma)、Girsanov 定理。
    * 鞅理论 (Martingales) 与无套利定价原理。
* :material-code-json: **量化实战与算法 (Quant & Coding)** *(Planned)*
    * Python 数据分析 (Pandas/Numpy)、机器学习算法实现。
    * 常见量化策略回测与绩效分析。

---

## 🛠️ 工具链 (The Stack)

本知识库的构建依赖于现代化的工程工具，不仅仅是记笔记，更是对工程能力的训练：

| 组件 | 作用 | 核心价值 |
| :--- | :--- | :--- |
| **VS Code** | 编辑器 | 统一的代码与文档编写环境，支持 Jupyter 交互 |
| **Git / GitHub** | 版本控制 | 追踪每一次思维迭代，实现“知识的时光机” |
| **MkDocs** | 渲染引擎 | 将 Markdown 实时编译为现代化的静态网站 |
| **LaTeX** | 数学排版 | 呈现 $\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$ 等复杂公式 |

---

## 📅 当前进度 (Status)

!!! abstract "2026年2月 - 冲刺阶段"
    目前正在集中攻克 **概率论基础** 模块。
    
    * [x] **测度论基础与公理化定义** :material-check:
    * [x] **概率论发展简史与金融应用** :material-check:
    * [ ] **随机变量及其分布** (In Progress) :material-clock-outline:
    * [ ] **多维随机变量与变换** (Todo)
    * [ ] **大数定律与极限定理** (Todo)

---

<div style="text-align: center;">
    <a href="01_Probability/01_basic_concepts/" class="md-button md-button--primary">开始学习：概率论的基本概念</a>
</div>