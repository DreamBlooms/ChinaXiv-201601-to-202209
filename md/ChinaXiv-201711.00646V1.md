# 基于精细时程积分的快速动态自适应小波配点法

张文华 宇波

（中国石油大学（北京）机械与储运工程学院，油气管道输送安全国家工程实验室/城市油气输配技术北京市重点实验室，北京102249)

摘要：动态自适应多尺度小波配点法（AWCM）能有效地模拟具有间歇性的物理现象，此方法是近几年发展起来的非常新颖的数值计算方法。为了增强该方法识别与跟踪解的奇异性的能力，并提高数值计算稳定性与计算效率，本文将精细时程积分算法与之相结合形成了快速动态自适应多尺度小波配点法。为了实现这一算法，本文给出了构造动态自适应网格配点集的新方法，构建了以小波（或尺度函数）系数为变量的时程推进公式。通过求解一维 Burgers 方程，证明了本文方法具有更加良好的数值计算性质。

关键词：小波；动态自适应网格；精细时程积分；间歇性中图分类号：TK123 文献标识码：A

# A Fast Dynamically Adaptive Wavelet Collocation Method

# Based on the Precise Time-integration

ZHANG WenhuaYUBo (NationalEngineringLaboratoryforPipeline Safety/BeijingKeyLaboratoryofUrbanOilandGasDistributionTechnology,China University of Petroleum(Beijing),Beijing 102249, China)

Abstract: The dynamically adaptive wavelet collcation method (AWCM) is a new method developed recently for simulating the physical phenomenon with intermitency eficiently.Inorder to enhance the stabilityand effciencyof computation and the ability of identifying and tracking singularity,anew method is established combined the precise time-integration method with AWCM. In this method,a new way to generate dynamic adaptive grids is proposed and the time marching equations as functions of wavelet (or scale function) coefficients are set up. Validated by solving one- dimensional Burgers equation，it is found that the new method provided in this paper presents good performance of computation.

Key words: Wavelet; Dynamically adaptive grids; Precise time-integration; intermittency

# 0前言

在计算流体力学方面，小波方法构成了一个非常新颖的研究领域。此方法最早可追溯到1990年，Glowiski 等[1]使用小波方法成功求解椭圆型与双曲型偏微分方程。Vasilyev在此方面做出了巨大的贡献。1995年，在求解偏微分方程配点法与小波多分辨分析的基础上，提出了多尺度小波配点法2。1996年，在其提出的多尺度小波配点法的基础上深入研究，利用小波所具有的信号奇异性检测能力构建了动态自适应多尺度小波配点法[3]。2000 年，在第二代小波的基础上构建了求解偏微分方程的第二代小波配点法[4]。在小波方法求解湍流流动方面，最早使用的方法是基于小波的直接数值模拟（WDNS)，此方法充分考虑了湍流流动的间歇性来降低计算复杂度。其次是1999 年 Farge 等[5提出的相干涡模拟方法（CVS)，此方法利用小波将湍流流动分解为拟序部分与随机背景流动部分，前者直接计算，而后者建立简化模型求解。2004 年，Goldstein 等[提出了随机相干涡自适应大涡模拟（SCALES)，此方法继承了相干涡模拟的跟踪湍流流动高含能拟序结构的能力，同时使用了大涡模拟（LES）模化低含能随机背景湍流的方法。

1994 年，钟万勰院士提出了结构动力学的精细时程积分法，此算法只在空间上使用近似的离散格式，对于线性问题此方法是一种半解析数值模拟方法，通过此算法对时层推进使用的常指数矩阵进行精细计算，使其在时间上具有很高精度。

本文综合考虑数值计算效率与稳定性，提出了一种基于精细时程积分的快速动态自适应多尺度小波配点法。

# 1 计算方法

本文所采用的是基于插值小波变换的动态自适应多尺度小波配点法。由于小波变换只能在能量有限的函数空间 $L ^ { 2 } ( f )$ 进行，因此本文只针对 $L ^ { 2 } ( f )$ 空间函数展开讨论。以一维Burgers波动为例进行介绍，其无量纲控制方程为：

$$
\frac { \partial u } { \partial t } + u \frac { \partial u } { \partial x } = \frac { 1 } { \mathrm { R e } } \frac { \partial ^ { 2 } u } { \partial ^ { 2 } x }
$$

# 1.1插值小波变换离散偏微分方程

对 $u ( x )$ 进行如下小波变换：

$$
u _ { J } \left( \boldsymbol { x } \right) = \sum _ { k _ { 0 } = 0 } ^ { 2 ^ { j _ { 0 } } } u \left( x _ { j _ { 0 } k _ { 0 } } \right) \phi _ { j _ { 0 } k _ { 0 } } \left( \boldsymbol { x } \right) + \sum _ { j \ge j _ { 0 } } \sum _ { k = 0 } ^ { 2 ^ { j } } \alpha _ { j k } \psi _ { j k } \left( \boldsymbol { x } \right)
$$

原函数 $u ( x )$ 关于 $x$ 的各阶导数可以由尺度函数$\phi ( k )$ 与小波函数 $\psi \big ( k \big )$ 的各阶导数来计算：

$$
u _ { J } ^ { ( m ) } \left( x \right) = \sum _ { k _ { 0 } = 0 } ^ { 2 ^ { j _ { 0 } } } u \left( x _ { j _ { 0 } k _ { 0 } } \right) { \phi _ { j _ { 0 } k _ { 0 } } } ^ { m } \left( x \right) + \sum _ { j \ge j _ { 0 } } \sum _ { k = 0 } ^ { 2 ^ { j } } \alpha _ { j k } { \psi _ { j k } } ^ { m } \left( x \right)
$$

将式（2）、式（3）代入方程（1）得到一维Burgers的半离散方程：

$$
\begin{array} { c }  { \displaystyle { \frac { \hat { \alpha } { \boldsymbol { u } } _ { J } ( { \boldsymbol { x } } _ { n } , t ) } { \hat { \alpha } t } = \frac { 1 } { \mathrm { R e } } \Bigg [ \sum _ { k _ { 0 } = 0 } ^ { 2 ^ { j _ { 0 } } } u \left( { x } _ { j _ { 0 } k _ { 0 } } \right) { \phi } _ { j _ { 0 } k _ { 0 } } ^ { \prime } \left( { \boldsymbol { x } } _ { n } \right) + \sum _ { j \ge j _ { 0 } } \sum _ { k = 0 } ^ { 2 ^ { j } } \alpha _ { j k } { \psi } _ { j k } ^ { \prime } \left( { \boldsymbol { x } } _ { k } + { \boldsymbol { x } } _ { k } \right) } } \\ { { - u _ { J } ( { \boldsymbol { x } } _ { n } , t ) \Bigg [ \sum _ { k _ { 0 } = 0 } ^ { 2 ^ { j _ { 0 } } } u \left( { x } _ { j _ { 0 } k _ { 0 } } \right) { \phi } _ { j _ { 0 } k _ { 0 } } ^ { \prime } \left( { \boldsymbol { x } } _ { n } \right) + \sum _ { j \ge j _ { 0 } } \sum _ { k = 0 } ^ { 2 ^ { j } } \alpha _ { j k } { \psi } _ { j k } ^ { \prime } \left( { \boldsymbol { x } } _ { n } \right) \Bigg ] } } \end{array}
$$

式中，下标 $J$ 一 -最细尺度;

$u _ { J } ( x _ { n } , t ) \longrightarrow u$ 在最细尺度配点集的第 $n$ 个配置点上的近似值;

$u \left( x _ { j _ { 0 } k _ { 0 } } \right)$ 最粗尺度配点集的第 $k _ { 0 }$ 个配置点尺度函数 $\phi _ { j _ { 0 } k _ { 0 } } \left( x \right)$ 的系数;

$\phi _ { j _ { 0 } k _ { 0 } } ^ { \prime } \left( x _ { n } \right)$ ——最粗尺度配点集的第 $k _ { 0 }$ 个配置点尺度函数 $\phi _ { j _ { 0 } k _ { 0 } } \left( x \right)$ 在最细尺度配点集的第 $n$ 个配置点上一阶导数;

$\phi _ { j _ { 0 } k _ { 0 } } ^ { \prime \prime } \left( x _ { n } \right)$ 一最粗尺度配点集的第 $k _ { 0 }$ 个配置点尺度函数 $\phi _ { j _ { 0 } k _ { 0 } } \left( x \right)$ 在最细尺度配点集的第 $n$ 个配置点上二阶导数;

αjk——尺度j配点集的第k个配置点小波函数

Yjk(x)的系数;

$\psi _ { j k } ^ { \prime } \left( x _ { n } \right)$ ——尺度 $j$ 配点集的第 $k$ 个配置点小波函数 $\psi _ { j k } \left( x \right)$ 在最细尺度 $J$ 配点集的第 $n$ 个配置点上一阶导数；

$\psi _ { j k } ^ { \prime \prime } \left( x _ { n } \right)$ ——尺度 $j$ 配点集的第 $k$ 个配置点小波函数 $\psi _ { j k } \left( x \right)$ 在最细尺度 $J$ 配点集的第 $n$ 个配置点上二阶导数。

# 1.2基于精细时程积分的多尺度插值小波配点法

半离散方程（4）可以写成如下矩阵形式：

$$
\frac { \partial \mathbf { U } } { \partial t } = \frac { 1 } { \operatorname { R e } } \mathbf { S } _ { 2 } \mathbf { C } - \operatorname { d i a g } ( \mathbf { U } ) \mathbf { S } _ { 1 } \mathbf { C }
$$

式中，向量C由小波（或尺度函数）系数构成；向量 $\mathbf { S } _ { 1 }$ 、 $\mathbf { S } _ { 2 }$ 分别由小波（或尺度函数）一阶、二阶导数构成。

半离散方程（5）中向量 $\mathbf { U }$ 与向量C存在下式关系：

$$
\mathbf { U } = \mathbf { S } _ { 0 } \mathbf { C }
$$

向量 $\mathbf { S } _ { 0 }$ 由小波（或尺度函数）构成。

矩阵 ${ \bf S } _ { 0 }$ 是满秩矩阵，存在逆矩阵 ${ \mathbf { S } _ { 0 } } ^ { - 1 }$ ，可得：

$$
\mathbf { C } = \mathbf { S } _ { 0 } ^ { - 1 } \mathbf { U }
$$

将式（7）代入式（5）可得：

$$
\frac { \partial \mathbf { U } } { \partial t } = \mathbf { H } \mathbf { U } + \mathrm { d i a g } \left( \mathbf { U } \right) \mathbf { M } \mathbf { U }
$$

式中， $\mathbf { H } = \frac { 1 } { \mathrm { R e } } \mathbf { S } _ { 2 } \mathbf { S } _ { 0 } ^ { - 1 }$ ， $\mathbf { M } = \mathbf { S } _ { 1 } \mathbf { S } _ { 0 } ^ { - 1 }$ 。

方程（8）构成了 $\mathbf { U }$ 关于 $t$ 的常微分方程，具有解析解：

$$
\begin{array} { r l } & { \mathbf { U } \big ( t _ { i } \big ) = \exp \big [ \mathbf { H } ( t _ { i } - t _ { i - 1 } ) \big ] \mathbf { U } \big ( t _ { i - 1 } \big ) } \\ & { \qquad - \exp ( \mathbf { H } t _ { i } ) \int _ { t _ { i - 1 } } ^ { t _ { i } } \mathrm { d i a g } \big [ \mathbf { U } \big ( t \big ) \big ] \mathbf { M } \mathbf { U } \big ( t \big ) d t } \end{array}
$$

等式(9)右端第二项是Burgers 方程的非线性项，为了实现积分需要进行线性化处理，在 $t = t _ { i }$ 处Taylor展开：

$$
\begin{array} { r l } & { \mathrm { d i a g } \big [ \mathbf { U } \left( t \right) \big ] \mathbf { M } \mathbf { U } \left( t \right) = r _ { 0 } + r _ { 1 } \left( t _ { i } - t _ { i - 1 } \right) } \\ & { r _ { 0 } = \mathrm { d i a g } \big [ \mathbf { U } \left( t _ { i } \right) \big ] \mathbf { M } \mathbf { U } \left( t _ { i } \right) } \end{array}
$$

$$
r _ { 1 } = \left\{ \begin{array} { l } { \displaystyle \mathrm { d i a g } \Bigg [  { \frac { \partial { \bf U } } { \partial t } } \Bigg | _ { t = t _ { i } } \Bigg ] { \bf M } { \bf U } \left( t _ { i } \right) } \\ { \displaystyle + \mathrm { d i a g } \Big [ { \bf U } \left( t _ { i } \right) \Big ] { \bf M } \Bigg (  { \frac { \partial { \bf U } } { \partial t } } \Bigg | _ { t = t _ { i } } \Bigg ) \Bigg ] } \end{array} \right.
$$

将式（10）代入式（9）并整理可得方程（8）的时层推进公式：

$$
\begin{array} { c } { \mathbf { U } \left( t _ { i } \right) = \mathbf { T U } \left( t _ { i - 1 } \right) + \left( \mathbf { T } - \mathbf { I } \right) \mathbf { H } ^ { - 1 } \left( r _ { 0 } + \mathbf { H } ^ { - 1 } r _ { 1 } \right) } \\ { - \mathbf { H } ^ { - 1 } r _ { 1 } \left( t _ { i } - t _ { i - 1 } \right) } \end{array}
$$

其中，指数矩阵 $\mathbf { T } = \exp \left[ \mathbf { H } ( t _ { i } - t _ { i - 1 } ) \right]$ 可以精确求解,首先将 $T$ 表示成以下形式：

$$
\begin{array} { l } { { \displaystyle { \bf T } = \exp \left[ { \bf H } ( t _ { i } - t _ { i - 1 } ) \right] = \exp \left[ { \bf H } \tau \right] ^ { 2 ^ { M } } } \ ~ } \\ { { \displaystyle \tau = \frac { \Delta t } { 2 ^ { M } } = \frac { t _ { i } - t _ { i - 1 } } { 2 ^ { M } } } } \end{array}
$$

取 $\mathit { M } = 2 0 \ , \ \tau$ 将是一个非常小的时间量， $\mathbf { H } \tau$ 接近于零矩阵。将 $\exp \left[ \mathbf { H } \tau \right]$ 在零矩阵处 Taylor展开：${ \begin{array} { r l } & { \exp \left[ \mathbf { H } { \boldsymbol { \tau } } \right] = \mathbf { I } + \mathbf { T } \mathbf { a } } \\ & { = \mathbf { I } + \mathbf { H } { \boldsymbol { \tau } } + \left( \mathbf { H } { \boldsymbol { \tau } } \right) ^ { 2 } \left[ \mathbf { I } + \left( \mathbf { H } { \boldsymbol { \tau } } \right) / 3 + \left( \mathbf { H } { \boldsymbol { \tau } } \right) ^ { 2 } / 1 2 \right] { \boldsymbol { \Biggl / } } 2 } \end{array} }$ (13)

值得注意的是Ta接近零矩阵，必须与单位阵I分开存储以保证其精度。将Ta按照下式进行 $M$ 次迭代：

$$
\mathbf { T } \mathbf { a } _ { 2 } = \left( \mathbf { I } + \mathbf { T } \mathbf { a } _ { 1 } \right) ^ { 2 } - \mathbf { I } = 2 \mathbf { T } \mathbf { a } _ { 1 } + \mathbf { T } \mathbf { a } _ { 1 } ^ { 2 }
$$

$$
\begin{array} { r } { \mathbf { T } \mathbf { a } _ { 3 } = \left( \mathbf { I } + \mathbf { T } \mathbf { a } _ { 2 } \right) ^ { 2 } - \mathbf { I } = 2 \mathbf { T } \mathbf { a } _ { 2 } + \mathbf { T } \mathbf { a } _ { 2 } ^ { 2 } } \\ { \vdots } \end{array}
$$

$$
\mathbf { T a } _ { M } = \left( \mathbf { I } + \mathbf { T a } _ { M - 1 } \right) ^ { 2 } - I = 2 \mathbf { T a } _ { M - 1 } + \mathbf { T a } _ { M - 1 } ^ { 2 }
$$

可以得到T矩阵的高精度解T=I+Tam°

# 1.3时层推进的动态自适应网格的新方法

在传统的动态自适应多尺度小波配点法实施过程中，为了使数值计算能够跟踪解的奇异性，不仅保留了已求解的上一时层上满足条件 $\left| c _ { n } ^ { j } \right| \geq a _ { j } ^ { 1 / 2 } \varepsilon$ （204（ $a _ { j } ^ { 1 / 2 }$ 为与尺度有关常数， $\boldsymbol { \varepsilon }$ 为小波系数阈值）的配置点，还要保留待求解的当前时层可能对解的奇异性有贡献的重要配置点。由于数值计算的时间步长较小，解的奇异性只能从上一时层配置点迁移到其附近配置点，因此，当前时层上可能对解的奇异性有贡献的重要配置点位于上一时层满足条件$\left| c _ { n } ^ { j } \right| \geq a _ { j } ^ { 1 / 2 } \varepsilon$ （ $a _ { j } ^ { 1 / 2 }$ 为与尺度有关常数， $\boldsymbol { \varepsilon }$ 为系数阈值)的相邻配置点。

对传统的动态自适应多尺度小波配点法的不规则配点集的构造方法进行分析，并通过数值试验进行验证，给出以下结论：当时间步长 $\Delta t$ 过大，传统的动态自适应多尺度小波配点法不能跟踪解的奇异性，其不规则配点集的构造方法是影响数值计算稳定性的重要原因。

为了增强数值计算的稳定性，本文改进了动态自适应网格构建方法一一边求解边生成的方法。在基于精细时程积分的快速动态自适应多尺度小波配点法的实施步骤中给出此方法：

（1）选择插值小波，构造时层推进所需的矩阵A、B与 $\mathbf { S } _ { 1 }$ ：

（2）假设在不规则配点集 $G _ { \geq } ^ { t _ { i - 1 } }$ 上获得了上一时层的尺度函数或小波函数系数 $c _ { n } ^ { i - 1 }$ ，计算 $t ^ { i - 1 }$ 时层 $\boldsymbol { u }$ 函数在配点集 $G$ 上的近似解 $u _ { n } ^ { i - 1 }$ ；

（3）在配点集 $G$ 中最粗尺度的尺度空间配点集 $G _ { 0 }$ 上，计算当前时层系数cnG；

（4）假设配点集 $G$ 中较小尺度的小波空间配点集$G _ { 2 }$ 与 $G _ { 0 }$ 、 $G _ { 1 }$ 合并形成 ${ G } _ { 2 } ^ { + }$ ，在 ${ G } _ { 2 } ^ { + }$ 中 $G _ { 2 }$ 上的配置点与 $G _ { 0 }$ 、 $G _ { 1 }$ 中的配置点相间构成临点。若 $G _ { 2 }$ 中配置点相邻配置点的系数 $\left. c _ { n \in G _ { 0 } \cup G _ { 1 } } ^ { i } \right. \geq a _ { j } ^ { 1 / 2 } \varepsilon$ ，则计算此配置点上的系数cneG；

（5）与步骤（4）相类似的计算其他小波空间配点集上的系数 ${ c _ { n } } ^ { i }$ ，最终在配点集 $G$ 上获得当前时层可能对解的奇异性有贡献的配点上的系数 $c _ { n } ^ { i }$ ：

（6）通过式 $\left| c _ { n } ^ { i } \right| \geq a _ { j } ^ { 1 / 2 } \varepsilon$ 保留配置点，构造当前时层的不规则配点集 $G _ { \geq } ^ { t _ { i } }$ ，计算 $t ^ { i }$ 时层 $u$ 函数在配点集 $G$ 上的近似解 ${ u _ { n } } ^ { i }$ ：  
（7）重复（2） $\sim$ （6）进行时层推进，直至获得最终时层 $\mathbf { \Psi } _ { t }$ 上 $u$ 函数的近似解 ${ u _ { n } } ^ { e n d }$ 。

# 2算例分析与讨论

# 2.1问题描述

方程（1）给出了一维无量纲Burgers方程，计算区域为(0,2)， $\mathrm { R e } { = } 1 0 0 0$ ，给定其初始条件与边界条件为： $u ( x , 0 ) = \sin ( \pi x ) , \qquad u ( 0 , t ) = u ( 2 , t ) = 0 \ ,$ 0

采用在时间上具有一阶精度的显式格式的动态自适应多尺度小波配点法与一阶精度的基于精细时程积分的快速动态自适应多尺度小波配点法进行求解；边界处采用对称延拓；将计算区域均匀离散为$2 ^ { 1 0 } \mathrm { + } 1$ 个配置点。

# 2.2计算结果分析

设定小波阈值 $\varepsilon { = } 1 0 ^ { - 5 }$ ， $\triangle \mathrm { t } { = } 1 0 ^ { - 4 }$ ，使用本文提出的基于精细时程积分的快速动态自适应多尺度小波配点法对上述两类物理问题进行求解，图1给出了各无量纲时间上的数值计算结果，以及数值计算所使用的动态网格配置点。观察图1，Burgers 方程从光滑的初始物理量场逐渐发展为局部具有强烈奇异性的物理量场，局部的奇异点意味着局部的高频波动，导致细尺度配置点上小波系数增大；随着数值解局部奇异性的增强，数值计算能够相应增加细尺度配置点，体现了算法具有识别奇异点的能力。

![](images/b2b73a6a0c50c236b4f609c967f7ace7c71d9cf249873286be42330d792e63af.jpg)  
图1Burgers方程的解与配置点的时间演化过程 Fig.1Time evolution of solutions of Burgers equation and collocation points

为了对比两种算法的稳定性，在时间步长$\Delta { t } = \boldsymbol { 1 0 } ^ { - 4 }$ 、 ${ \Delta } t { = } 1 0 ^ { - 3 }$ ，小波阈值 $\varepsilon { = } 1 0 ^ { - 5 }$ 条件下进行数值模拟。图2给出了一维Burgers方程使用两种算法在各时间步长下的计算结果与配置点使用情况。从图 2中可以看出，在 $\Delta t { = } 1 0 ^ { - 4 }$ 、 ${ \Delta } t { = } 1 0 ^ { - 3 }$ 时间步长下，本文方法都能够有效地识别、捕捉与跟踪解的奇异点，并对物理问题进行精确模拟，传统方法在较小时间步长 $\Delta { t } = \boldsymbol { 1 0 } ^ { - 4 }$ 条件下，同样可以精确模拟物理过程，然而在较大时间步长 $\Delta t { = } 1 0 ^ { - 3 }$ 条件下，随着解的奇异性增强，误差逐渐积累放大，当 $\scriptstyle { t = 0 . 3 8 }$ 时，开始产生振荡，数值计算发散。上述结果充分说明了本文提出的新算法具有更高的数值计算稳定性，其原因为： $\textcircled{1}$ 尽管两种算法在时间上都具有一阶精度，但是本算法在时层推进方面是基于精细时程积分方法，能有效抑制误差的放大； $\textcircled{2}$ 传统方法不规则配点集的构造方法必须要求较小的时间步长，否则将失去跟踪解的奇异点的能力，而本文算法的不规则配点的构造对时间步长没有要求。

![](images/93d890ef8909d73824cce0f21a34095482f01f5f67cced08120b5191c5fc6fd5.jpg)  
图2两种算法计算结果与配置点  
Fig.2 Comparisons of Solutions and collocation points using twc method

表1给出了两种算法在各时间步长与小波阈值条件下CPU时间，从表1中可以看出，传统算法在较高时间步长下计算发散，在较低时间步长下CPU时间远高于本文方法，其计算时间是本文算法的10倍左右。

表1计算时间对比  
  

<html><body><table><tr><td colspan="4">TableIComparisonsolCPOtime</td></tr><tr><td rowspan="2">计算时间</td><td colspan="2">本文算法</td><td colspan="2">传统算法</td></tr><tr><td>ε=10-5</td><td>ε=10-4</td><td>ε=10-5</td><td>ε=10-4</td></tr><tr><td>△t=10-4</td><td>46.13s</td><td>37.83s</td><td>420.63s</td><td>383.84s</td></tr><tr><td>△t=10-3</td><td>5.63s</td><td>4.55s</td><td>发散</td><td>发散</td></tr></table></body></html>

# 3结论

本文结合传统的动态自适应多尺度配点法与精细时程积分算法的优点，提出了一个新算法。为了实现这一算法，本文进行了如下工作：

（1）给出了动态自适应网格不规则配点集构造的新方法，从而使配点集的构造不约束时间步长的大小，提高计算稳定性；

（2）构建了以尺度函数或小波函数系数为变量的时程推进公式。

数值试验证明了本文方法具有识别、捕捉与跟踪解的奇异性的能力；通过数值计算对比证明了本文提出的新算法优于传统算法，主要体现在：本文提出的算法数值计算的稳定性更强、计算效率更高，在相同的条件下，计算效率提高了约10倍。

参考文献   
[1] Glowinski R., Lawton W.,Ravaehol M.,and Tenenbaum. Wavelets solution of linear and nonlinear elliptic,parabolic and hyperbolic problems in one space dimension[J]. Computing Methods in Applied Sciencesand Engineering， SIAM Philadelphia,1990,55-120   
[2] Olegv. Vasilyev Samuel Paolucci and Mihir Sen. A multilevel wavelet collocation method for solving partial differential equations in a finite domain[J]. Journal of Computational Physics,1995,120:33-47   
[3] Olegv. Vasilyev and Samuel Paolucci. A dynamically adaptive multilevel wavelet collocation method for solving partial differential equations in a finite domain[J].Journal of Computational Physics,1996,125: 498-512   
[4]Olegv.VasilyevandChristopher Bowman. Second-generation wavelet collocation method for the solution of partial differential equations[J]. Journal of Computational Physics,2000,165: 660-693   
[5] Farge M, Schneider K and Kevlahan N. Non-Gaussianity and coherent vortex simulation for twodimensional turbulence using an adaptive orthogonal wavelet basis[J]. Phys.Fluids,1999, 11(2): 187-201   
[6] Goldstein DE and Vasilyev OV. Stochastic coherent adaptive large eddy simulation method[J].Phys.Fluids,2004,16(2): 497-513   
[7] 钟万勰．结构动力方程的精细时程积分法[J].大连理工 大学学报,1994,34(2):131-136   
Zhong Wanxie.On precise time-integration method for structural dynamics[J]. Journal of Dalian University of Technol0gy, 1994, 34(2): 131-13