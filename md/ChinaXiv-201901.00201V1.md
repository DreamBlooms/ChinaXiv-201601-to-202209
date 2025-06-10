# 基于改进遗传算法的稀疏重构算法

潘美虹+，郑芹

(南京航空航天大学 电子信息工程学院，南京 211106)

摘要：稀疏重构算法中凸松弛法在恢复效率方面、贪婪追踪法在恢复精度方面存在不足，基于遗传算法迭代优化的思想，结合模拟退火以及多种群算法的优势，提出了基于模拟退火遗传算法和基于多种群遗传算法的启发式稀疏重构算法。所提算法均从传统遗传算法易陷入局部最优解的缺陷出发，分别通过保持个体间的差异性和提高种群多样性来搜索待求稀疏信号的全局最优解，并通过理论分析证明了所提算法参数选取及搜索策略的有效性。此外，以阵列信号处理中空间信源的波达方向（DOA）估计问题为例，验证所提算法的有效性。仿真结果表明，相较于正交匹配追踪OMP 算法和基于I1范数奇异值分解的I1-SVD算法，所提算法提高了DOA估计的精度，且降低了运算复杂度，使其快速收敛至全局最优解。

关键词：多种群遗传算法；模拟退火遗传算法；DOA估计；稀疏重构 中图分类号：TP20 doi:10.19734/j.issn.1001-3695.2018.10.0727

Sparse reconstruction algorithm based on improved genetic algorithm

Pan Meihong+, Zheng Qin (College ofElectronic& Information Engineering,NanjingUniversityofAeronautics&Astronautics,Nanjing21106, China)

Abstract:Convex relaxation methods present drawback in termsof computational complexity,meanwhile,greedypursuit methods have disadvantages in their reconstruction accuracy.Basedon the inspiration of iterative optimizationof genetic algorithm and combining with the advantages of simulated annealing and multi-population algorithm,we propose two heuristic sparse reconstruction algorithms basedon simulated annealinggenetic algorithm and multi-population genetic algorithm.The proposed algorithms aimatthedefectsof thetraditional geneticalgorithmthatoften trapped inthe local optimal solutions.Inorder to solve this,we implement two strategies to search globaloptimal solutionsofthe sparse reconstructionvia maintaining the diferencesamong individualsandincreasingthe diversityofthe population,respectively. The validityof the proposed algorithmson parameterselections and search strategy is proved bytheoretical analysis.The proposed algorithms canbe appliedtothe DOA estimationof multiplespatial sources inarraysignal processng to verifythe effectivenessSimulation results show that,compared with the OMP algorithmand l1-SVDalgorithm,the proposed algorithms have improved the accuracy and reduced the computational complexity，which can converge to the global optimal solution in a fast manner.

Key words:multi-population geneticalgorithm；simulatedannealing genetic algorithm；DOA estimation;sparse reconstruction

# 0 引言

随着压缩感知理论的提出，很多学者在稀疏重构方法上做了大量研究，提出了很多有效的重构算法，形成了相对完备的理论和算法体系，并在处理实际问题中得到了广泛应用。目前所提出的重构算法主要分为贪婪追踪法和凸松弛法[1]两类。这两类算法存在各自的优点和缺陷，贪婪算法在恢复效果方面不如凸优化算法，但实现起来相对简单快速；而凸优化算法的计算效率不如贪婪算法，但具有较好的稳定性和理论保证。由于稀疏重构问题是一个非凸的组合优化问题，目前还没有快速精确求解该问题的确定性方法[2.3]。而前面提到的两大类重构算法只能对其进行近似求解，并且在稀疏度较小情况下不能获取有效的重构。

稀疏重构问题本质是组合优化问题。遗传算法（geneticalgorithm，GA）是一种求解组合优化问题很有效的算法。目前基于遗传算法的稀疏重构方法已有一些初步的研究，文献[4]中提出了一种模拟退火与贪婪算法相结合的稀疏重构算法，在不同信噪比下对图像进行重构来比较该算法与BP算法以及OMP算法的重构精度，结果表明相同条件下，该算法重构误差更低。文献[5]提出了一种基于10范数最小化的模拟退火稀疏重构方法，该方法相对于贪婪追踪算法，提高了重构精度以及重构效率。文献[6]基于粒子群优化算法，结合贪婪追踪的思想，提出了一种新的稀疏重构算法，该方法比一般的重构算法具有更快的重构速率。文献[7]把粒子群优化算法用于稀疏分解的最优匹配原子的搜索来降低稀疏分解复杂度，从而提高用稀疏分解理论进行信号处理的计算效率。文献[8]将遗传算法应用于变换域稀疏缺失样本信号的重构。文献[9]提出了一种基于遗传算法（GA）的测量矩阵优化方法来解决压缩感知的逆合成孔径雷达稀疏成像问题。文献[10]提出了一种基于遗传算法和正则化先验模型的单幅图像SR重建方法，结合遗传算法和迭代收缩算法来处理正则化先验模型，避免陷入局部最优解。本文同时采用贪婪追踪法和凸松弛法的思想，结合改进的遗传算法提出了新的稀疏重构算法。由于单一的遗传算法在迭代后期个体适应度趋于一致，使得整个种群的进化停滞不前，从而很容易陷入局部最优解。鉴于模拟退火算法更强的全局搜索能力，将其与遗传算法相结合，在降温过程对适应度进行拉伸来保证算法有效快速地收敛到全局最优解。多种群遗传算法则突破单种群优化的框架，通过多个设有不同控制参数的种群协同进化，同时兼顾了算法的全局搜索和局部搜索性能。协同进化过程中保留各种群的最优个体，并通过移民算子将最优个体传播到所有种群，迭代结束后从所有最优个体中选出一个最优个体作为最终解。

本文将所提算法用于阵列信号处理中空间信源的DOA估计来验证算法的有效性。目前基于遗传算法的DOA估计方法已有一些研究：文献[11]提出将遗传算法应用于MUSIC谱峰搜索来实现DOA估计问题，解决搜索维度过高而导致的算法效率低的问题；文献[12]则结合模拟退火与遗传算法，将其应用于加权子空间的DOA估计中来提高估计精度。本文将稀疏重构的思想与改进的遗传优化算法相结合，用于DOA估计，并与正交匹配追踪算法以及基于奇异值分解的11范数最小化的凸优化算法进行比较，验证算法在估计精度以及运算效率上的改善。

# 1 稀疏重构模型描述

稀疏信号 $\textbf { x }$ 经过感知矩阵A压缩测量后记为 $\mathbf { y } = A \mathbf { x }$ ，该方程是一个欠定方程组，有无穷多个解，但由于 $x$ 的稀疏性，因此通过对 $\mathbf { x }$ 稀疏度的最小化约束，方程就可以得到唯一的解。考虑实际中更一般的情况，建立含噪的稀疏优化模型如下：

$$
\begin{array} { r } { \hat { \pmb { x } } = a r g \ m i n \left\| \pmb { x } \right\| _ { 0 } \qquad s t . \left\| \pmb { y } - \pmb { A } \pmb { x } \right\| _ { 2 } \le \varepsilon } \end{array}
$$

其中： $\textbf { x }$ 是一个稀疏信号， $\textbf { x }$ 中大多数元素为0或者接近0;$\textbf { y }$ 是观测向量 $\pmb { y } = \pmb { A } \pmb { x } + \pmb { n } , \pmb { y } \in \mathbb { C } ^ { M \times 1 } , \pmb { x } \in \mathbb { C } ^ { L \times 1 }$ ； $\scriptstyle \varepsilon = \parallel n \parallel _ { 2 }$ 是一个与噪声相关的误差界；I表示求0范数，用来求解向量中的非0元素个数，设信号稀疏度为 $\mathrm { ~ \bf ~ K ~ }$ ，则 $K = \parallel x \parallel _ { 0 }$ ，满足 $K < M \ll L$ ，$\textbf { x }$ 中非0元素所在位置的集合称为向量 $\textbf { x }$ 的支撑。

考虑更一般的情况，观测信号为时域的多次采样，记为$\pmb { Y } = \pmb { A } \pmb { X } + \pmb { N } , \pmb { Y } \in \mathbb { C } ^ { M \times T } , \pmb { A } \in \mathbb { C } ^ { M \times L } , \pmb { X } \in \mathbb { C } ^ { L \times T }$ ， $\pmb { N } \in \mathbb { C } ^ { M \times T }$ 。其中： $T$ 表示采样数。用 $\Re ( X ) = \{ 1 \leq i \leq n | X _ { i , \cdot } \neq \pmb { \theta } \}$ 来表示 $\mathbf { X }$ 的行支撑。 $X _ { i , \cdot }$ 表示矩阵 $\mathbf { X }$ 的第 $i$ 行。于是建立多观测信号的稀疏重构模型如下：

$$
\begin{array} { r l } { m i n \ \left| \ \mathfrak { R } ( X ) \right| } & { { } s . t . \left\| A X - \pmb { Y } \right\| _ { F } \le \delta } \end{array}
$$

其中：H表示求一个集合的势,集合的势是用来度量集合中元素个数的属性；Il表示Frobenius范数。

# 2 基于改进遗传算法的稀疏重构算法

遗传算法包括目标函数、编码方式、初始解、新解产生机制、终止条件五个基本元素[4]。将遗传算法与稀疏重构算法相结合，从这五个元素入手进行模型设计。

# 1）目标函数

在稀疏度K已知情况下，问题式(2)可以转换为m $\begin{array} { r l } { \dot { \boldsymbol { n } } \ \lVert \boldsymbol { A } \boldsymbol { X } - \boldsymbol { Y } \rVert _ { F } } & { { } \boldsymbol { s . t . } \big | \mathfrak { R } ( \boldsymbol { X } ) \big | \le K } \end{array}$

求解该问题，首先需要寻找一个满足 $\vert \hat { \Omega } \vert = K$ 的行支撑估

计，基于这个行支撑估计，用最小二乘法得到解的估计：

$$
\hat { X } _ { \hat { \Omega } , \bullet } = A _ { \hat { \Omega } } ^ { + } Y , \hat { X } _ { s - \hat { \Omega } , \bullet } = \pmb { \theta } , S = \{ 1 , 2 , . . . , L \}
$$

当 $\mathbf { X }$ 是该稀疏重构的问题的解，则可以得到

$$
\left\| A _ { \hat { \Omega } } A _ { \hat { \Omega } } ^ { + } Y - Y \right\| _ { F } = \operatorname* { m i n } _ { | \Re ( X ) | \leq K } \left\| A X - Y \right\| _ { F }
$$

上述式子等价于

$$
\hat { \Omega } = \arg \operatorname* { m i n } _ { | \Omega | = K } \big \| A _ { \hat { \Omega } } A _ { \hat { \Omega } } ^ { + } Y - Y \big \| _ { F }
$$

式（5）和（6）说明稀疏重构的本质就是寻找符合上述约束的行支撑估计 $\hat { \Omega }$ 。

因此可以定义函数：

$$
f ( { \hat { \Omega } } ) = { \frac { \left\| \mathbf { \nabla } A _ { { \hat { \Omega } } } A _ { { \hat { \Omega } } } ^ { + } \mathbf { { \boldsymbol { Y } } } - \mathbf { { \boldsymbol { Y } } } \right\| _ { F } } { \left\| \mathbf { { \boldsymbol { Y } } } \right\| _ { F } } }
$$

作为遗传算法的目标函数，即适应度函数。最小化该目标函数来得到稀疏矩阵 $\mathbf { X }$ 的行支撑估计。

优化目标：

$$
\operatorname* { m i n } _ { \Omega \subset \Theta } f ( \Omega )
$$

其中： $\Theta$ 是集合 $S = \{ 1 , 2 , \cdots , L \}$ 中所有势为 $\mathrm { ~ \bf ~ K ~ }$ 的子集组成的集合。

# 2）编码方式

将稀疏信号的非0行所在位置集合$\Omega \subseteq S , | \Omega | = K , S = \{ 1 , 2 , . . . L \}$ ，即稀疏矩阵 $\mathbf { X }$ 的行支撑，作为种群的个体。个体采用十进制编码，长度为 $\mathrm { ~ \bf ~ K ~ }$ ，个体上的基因代表非零行所在的位置标号。

# 3）初始解

设种群规模为popsize，每个解表示一个可行解的编码。为了让算法能够快速收敛到全局最优解，将遗传算法初始种群中的个体设定为比较接近最优解的支撑集集合，是一种有效的方法。本文遗传算法基于贪婪追踪的思想，采用阈值法来设定初始种群，得到一个初始解；然后在该初始解的小范围内进行随机波动，来得到遗传算法的初始解集合$p o p ^ { 0 } = \{ \Omega _ { 1 } , \Omega _ { 2 } , . . . , \Omega _ { p o p s i z e } \}$ 。个体产生方式如下：

$$
\{ \Omega _ { k , i } = \Omega _ { 0 , i } + r \mid r = r a n d i ( - 1 0 , 1 0 ) \}
$$

$\Omega _ { 0 } = \{ \{ \| A _ { \cdot , j } ^ { T } Y \| _ { 2 } \} _ { j = 1 } ^ { L }$ 中前K个最大值对应的下标集合}

基于以上理论，提出基于模拟退火遗传算法的稀疏重构算法（simulated annealing genetic algorithm based sparsereconstruction，SAGA-SR）和基于多种群遗传算法的稀疏重构 算 法（multi-population genetic algorithm based sparsereconstruction,MPGA-SR)。从单一遗传算法易陷入局部最优解的缺陷出发，通过改变稀疏解的搜索策略来提高算法收敛于全局最优解的概率，从而减小算法的重构误差。SAGA-SR利用了模拟退火算法以一定概率接受较差解的迭代策略，从而避免陷入局部最优解，以提高算法的全局搜索能力。MPGA-SR则脱离单种群优化的框架，通过多个设有不同控制参数的种群协同进化来实现最优解的搜索。该算法同时兼顾了算法的全局搜索和局部搜索能力。

新解更新策略在遗传算法中是非常重要的过程，决定了算法的计算量和搜索结果。不同算法解的更新机制不同，因此本文针对两种算法分别进行具体描述。

# 2.1 SAGA-SR 算法设计

SAGA结合了模拟退火算法的全局寻优能力和遗传算法 的局部寻优能力，使得求解结果收敛于全局最优解的概率提

高[1}{1]。

1）新解产生机制

在迭代优化过程中，为了保持种群的多样性，引入一个早熟判断标志：

$$
\Delta ^ { g } = f _ { \mathrm { m a x } } ^ { g } - f ^ { \prime }
$$

其中： $f _ { \operatorname* { m a x } } ^ { g }$ 为第 $\mathbf { g }$ 代种群最优个体的适应度值；$f ^ { \prime } { = } \frac 1 { H } \sum _ { i \in I } f _ { i } { ^ { g } } , I { = } \{ i | f _ { i } { ^ { g } } > \overline { { f } } { ^ { g } } \}$ ； $\overline { { f } } ^ { g }$ 和 $f _ { i } ^ { g }$ 分别表示第 $\mathbf { g }$ 次迭代，种群所有个体适应度均值以及个体 $i$ 的适应度值；H表示当前种群中个体适应度值大于种群适应度均值的个体数。由 $\Delta ^ { g }$ 动态调节交叉和变异概率：

$$
p _ { c } = p _ { c 0 } ( 1 - \frac { 1 } { 1 + e ^ { - T \Delta ^ { g } } } )
$$

$$
p _ { m } = p _ { m 0 } ( 1 - \frac { 1 } { 1 + e ^ { - T \Delta ^ { g } } } )
$$

其中： $p _ { c 0 }$ 和 $p _ { m 0 }$ 是初始的交叉和变异概率。

种群更新策略基于模拟退火的思想，产生下一代种群：

$$
\Omega _ { i } = \left\{ \Omega _ { i } ^ { g } \begin{array} { l l } { f ( \Omega _ { i } ^ { g - 1 } ) < f ( \Omega _ { i } ^ { g } ) } \\ { \Omega _ { i } ^ { g - 1 } } & { r > \exp ( - ( f ( \Omega _ { i } ^ { g - 1 } ) - f ( \Omega _ { i } ^ { g } ) ) / T ) } \end{array} \right.
$$

其中： $i = 1 , . . . , p o p s i z e$ ； $\mathrm { ~ \bf ~ r ~ }$ 为介于0与1之间的随机数。

根据种群中个体的值，计算稀疏重构问题稀疏解：

$$
\hat { X } _ { \hat { \Omega } , \bullet } ^ { g } = A _ { \hat { \Omega } } ^ { + } Y , \hat { X } _ { s - \hat { \Omega } , \bullet } ^ { g } = \pmb { \theta }
$$

2）终止条件

定义信噪比为 $S N R { = } 1 0 { \log _ { 1 0 } } \frac { \parallel A X ^ { * } \parallel _ { F } ^ { 2 } } { \parallel N \parallel _ { F } ^ { 2 } }$ AX，给定一个最优解的$\Omega ^ { * }$ ， $X ^ { * }$ 是该解对应的稀疏矩阵，由式子（14）计算得到，对该最优解 $\Omega ^ { * }$ 求目标函数的上界。 $\textbf { I }$ 是单位矩阵， $\mathbf { N }$ 是噪声矩阵。

$$
\begin{array} { r l } & { f ( \Omega ^ { * } ) = \mid \mid ( I - A _ { \Omega ^ { * } } A _ { \Omega ^ { * } } ^ { + } ) N \mid \mid _ { F } / \mid \mid A X ^ { * } + N \mid \mid _ { F } } \\ & { \leq \mid N \mid \mid _ { F } / \mid Y \mid _ { F } } \\ & { \leq \mid \mid N \mid \mid _ { F } / ( \mid \mid A X ^ { * } \mid \mid _ { F } - \mid \mid N \mid \mid _ { F } ) } \\ & { = ( 1 0 ^ { S N / 2 0 } - 1 ) ^ { - 1 } } \end{array}
$$

因此可以令 $\varepsilon = ( 1 0 ^ { S N R / 2 0 } - 1 ) ^ { - 1 }$ 作为迭代终止的条件。从算法的计算时间和收敛性两方面考虑，设定两个终止条件，满足任意一个条件都将终止算法，即：如果种群中最优个体的适应度函数值满足 $f ( \Omega _ { b e s t } ) < \varepsilon$ ，或者迭代次数达到参数设定的最大允许迭代的次数maxiter，则算法终止；当条件 $f ( \Omega _ { b e s t } ) < \varepsilon$ 先满足时，可以提前终止算法，避免多余的迭代，提高计算效率；当算法陷入局部最优解时，通过第二个条件，可在有限次迭代之后结束，避免算法陷入死循环。SAGA-SR算法的具体实现步骤如下所示。

算法1：基于模拟退火遗传算法的稀疏重构算法输入参数：感知矩阵A，稀疏度K，种群规模popsize，交叉概率 $p _ { m }$ ，变异概率 $p _ { c }$ ，初始温度 $T _ { 0 }$ ，冷却系数 $\xi$ ，终止参数 $\varepsilon$ ，最大迭代次数maxiter。

初始化：第 $\boldsymbol { \mathsf { k } }$ （ $1 \leq k \leq p o p s i z e$ ）个个体编码为 $\Omega _ { k } ^ { 0 }$ ，由式（8）确定，设迭代次数 $\scriptstyle { { \bf g } = 1 }$ ，令 ${ \sf T } = { \sf T } _ { \sf \Theta }$ 。

a)选择。依据目标函数 $f ( \Omega _ { k } ) , k = 1 , \ldots$ popsize选择最优个体保留下来，并淘汰最差的个体。

b)交叉变异。以概率pc选择一组个体，个体间随机配对，采用单点交叉的方式做交叉操作，以概率 ${ \mathsf p } _ { \mathsf m }$ 对各个体上的基因做变异操作，得到新种群。

c)将新种群中的个体 $\Omega _ { \ast } , k = 1 , . . . , p o p s i z e$ 代入式（14）得到$X _ { \mathit { k } } , \mathit { k } { = } 1 , . . . , p o p s i z e$ ，然后用式（7）计算当前种群个体适应度 $f ( \Omega )$ ，根据式（10）计算早熟判断标志 $\Delta ^ { g }$ ，然后由式(11)和(12)更新交叉

变异概率。

d）计算当前种群个体的适应度函数值 $f ( \Omega _ { \kappa } ^ { g } ) , k = 1 , . . . , p o p s i z e$ ，根据式(13)的更规则，来产生下一代种群。

e）更新温度 $T = \xi T$ 。

终止判断：当 $f ( \Omega _ { b e s t } ) < \varepsilon$ 或 $g >$ maxiter算法结束，得到最优解Qbesr =arg=min.{f(Ω)}。将该个体代入式（14）中，即可输出稀疏重构问题的最终解 $X _ { b e s t }$ ；否则 $\scriptstyle { \mathbf { g } = \mathbf { g } + 1 }$ ，转 $\mathsf { a } ) \sim \mathsf { e } )$ 。

# 2.2 MPGA-SR 算法设计

MPGA利用多种群并行遗传思想改进遗传算法性能[1.3],不同种群赋以不同的控制参数各自独立进化。各种群中，交叉算子是产生新个体的主要算子，决定算法的全局搜索能力；变异算子则是产生新个体的辅助算子，决定算法的局部搜索能力。该算法能够避免单种群进化过程中出现的过早收敛现象，并且也能加快收敛速度。

# 1）新解产生机制

第i个种群的控制参数（交叉概率和变异概率）如下：

$$
\left\{ \begin{array} { l l } { p _ { c } ^ { i } = p _ { c } + \eta q _ { c } } \\ { p _ { m } ^ { i } = p _ { m } + \lambda q _ { m } } \end{array} \right. { i = 1 , . . . , p o p n u m }
$$

其中： $p _ { c } , p _ { m } \in ( 0 , 1 )$ 是常数，分别表示交叉概率的下限以及变异概率的下限； $\eta$ 和 $\lambda$ 分别是介于0与1之间的随机数；$q _ { c } , q _ { m } \in ( 0 , 0 . 5 )$ 分别表示交叉概率以及变异概率最大可变化的幅度；popnum表示种群个数。

选取和保留每个子种群的优秀个体，各种群间通过移民算子进行联系来促进子种群的进化，从而实现多种群协同进化。移民操作如下：

$$
\left\{ \begin{array} { l l } { \Omega _ { w o r s t } ^ { i } = \Omega _ { b e s t } ^ { i - 1 } } \\ { \Omega _ { w o r s t } ^ { i } = a r g ~ m a x \{ f ( p o p _ { i } ) \} } { \mathrm { ~ } } i = 1 , . . . , p o p n u m  \\ { \Omega _ { b e s t } ^ { i - 1 } = a r g ~ m i n \{ f ( p o p _ { i - 1 } ) \} } \end{array} \right.
$$

第i个种群中个体的更新策略：

$$
\begin{array} { r l } & { \Omega _ { a } ^ { i } = \left\{ \begin{array} { l l } { \Omega _ { a } ^ { i n e w } } & { f ( \Omega _ { a } ^ { i n e w } ) < f ( \Omega _ { a } ^ { i } ) } \\ { \Omega _ { a } ^ { i } } & { f ( \Omega _ { a } ^ { i n e w } ) > f ( \Omega _ { a } ^ { i } ) } \end{array} \right. } \\ & { \Omega _ { b } ^ { i } = \left\{ \begin{array} { l l } { \Omega _ { b } ^ { i n e w } } & { f ( \Omega _ { b } ^ { i n e w } ) < f ( \Omega _ { b } ^ { i } ) } \\ { \Omega _ { b } ^ { i } } & { f ( \Omega _ { b } ^ { i n e w } ) > f ( \Omega _ { b } ^ { i } ) } \end{array} \right. \left. i = 1 , . . . , p o p n u m \right. } \end{array}
$$

其中： $\Omega _ { u } ^ { i n e w } , \Omega _ { b } ^ { i n e w }$ 为第 $i$ 个种群第a和 $\boldsymbol { \mathbf { b } }$ 个个体进行进化操作后的新个体； $f ( \Omega ^ { i } )$ 和 $f ( \Omega ^ { i n e w } )$ 分别表示遗传操作前后个体适应度值，由式（7）计算得到。

算法中移民算子的功能：以源种群中的最优个体代替目标种群中的最差个体，达到多种群协同进化的目的。同时选出各种群中的最优个体，并将其放入精华种群加以保存，保证各种群产生的最优个体不被破坏。

# 2）终止条件

给定目标函数值的上界 $\varepsilon$ ，计算方式同式（15)，从精华种群中选出最优个体 $\Omega _ { o p t }$ 。若该个体满足 $f ( \Omega _ { o p t } ) < \varepsilon$ ，则算法终止；当算法迭代次数达到最大迭代次数仍不满足目标函数值小于 $\varepsilon$ 的条件，则算法也会终止。设置最大迭代次数是为了避免求解结果陷入局部最优解时，算法陷入死循环，作用同上。MPGA-SR算法的具体实现步骤如下所示。

算法2：基于多种群遗传算法的稀疏重构算法输入参数：感知矩阵A，稀疏度 $\kappa$ ，子种群规模popsize，子种群数目 popnum，子种群i的交叉概率 $\varepsilon$ ，变异概率 $p _ { m } ^ { i }$ ， $\scriptstyle { i = 1 }$ ....popnum,终止参数 $\varepsilon$ ，最大迭代次数maxiter。

初始化：产生popnum 个初始种群 $p o p _ { k }$ $k = 1 , \dots$ ,popnum，对各种群中个体进行编码，编码方式基于式（8)，设迭代次数 $\scriptstyle { \mathbf { g } = 1 }$ 。

a)选择。根据式（7）计算所有个体目标函数值f(),i=1..,popsize $\Omega _ { \boldsymbol { \imath } } \in p o p _ { k }$ $k = 1 , \dots$ ,popnum，目标函数值越小个体越优，从每个子种群中选择最优个体保留下来，并淘汰最差的个体。

b)对 popnum 个子种群进行更新操作：

从第 $\textit { i }$ 个种群随机选取个体 $\Omega _ { a } ^ { i }$ 和 $\Omega _ { b } ^ { i }$ 按照交叉概率 $p _ { c } ^ { i }$ 做交叉操作产生新的个体 $\Omega _ { u } ^ { i n e w }$ 和 $\Omega _ { b } ^ { i n e w }$ ，计算新个体的适应度值，利用式(18)对每个种群中的个体进行更新。

对交叉操作后的种群按照变异概率 $p _ { m } ^ { i }$ 进行变异操作，并更新种群，处理方法同上。

c)对popnum个子种群进行移民操作，设置初始移民次数 $\scriptstyle { \mathfrak { m } } = { \mathfrak { \theta } }$

基于式（17）的移民策略，找出第i个种群的最优个体 $\Omega _ { b e s t } ^ { i }$ ：以及目标种群 $_ { i + 1 }$ 的最差个体 $\Omega _ { w o r s t } ^ { i + 1 }$ ，用 $\Omega _ { b e s t } ^ { i }$ 替换第 $_ { i + 1 }$ 个种群的Ωrst。

判断各种群之间是否完成移民，若m<popnum，则 $m = m + 1$ ，继续移民操作，否则转d)。

d)从每个子种群中选出各自的最优个体，放入精华种群中保存，以免最优个体被破坏。然后转a)。终止判断：在精华种群中选出全局最优个体 $\Omega _ { o p t }$ ，$\Omega _ { \it { b p t } } = a r g _ { \sum _ { k = 1 , \dots , p o p n u m } } \{ f ( \Omega _ { \it { b e s t , k } } ) \}$ ，若该个体满足 $f ( \Omega _ { o p t } ) < \varepsilon$ 或$g > m a x i t e r$ ，则终止算法，得到最优解，将该个体代入式（14）中，即可输出稀疏重构问题的最终解 $X _ { o p t }$ ；否则 $g = g + 1$ ，转a)。

# 3 算法复杂度分析

SAGA-SR算法的计算量主要集中在初始解的选择过程以及迭代更新过程中计算目标函数的过程，计算每个个体的初始解利用了阈值法，该步骤的计算复杂度分别为O(MLT)、每个个体的更新过程。计算量主要集中在d)计算目标函数的过程，其复杂度为 $\mathrm { O } ( M K ^ { \{ 2 \} } ) { + } \mathrm { O } ( M K T )$ ，因此 SAGA-SR 算法每次迭代的复杂度为 $\mathrm { O } ( M L T { \times } p o p s i z e ) { + } \mathrm { O } ( p o p s i z e \times$ $M K ^ { \{ 2 \} } ) { + } \mathrm { O } ( \mathrm { p o p s i z e } { \times } M K T )$ 。考虑算法的最大迭代次数为maxiter,可以得到SAGA-SR 算法复杂度为 $O ( M L T { \times } p o p s i z e ) { + }$ $O ( p o p s i z e \times M K ^ { \{ 2 \} } { \times } m a x i t e r ) + O ( p o p s i z e \times M K T { \times } m a x i t e r ) ,$ 0

MPGA-SR算法的计算量主要集中在每个子种群的初始解的选择、迭代更新过程目标函数的计算以及从所有种群中选取精华种群这三个过程中。考虑popnum个子种群，每个子种群的规模为popsize，阈值法选取初始解，该步骤在一次迭代中的计算复杂度为 $\begin{array} { r } { \mathrm { O } ( p o p n u m { \times } p o p s i z e { \times } M L T ) } \end{array}$ ，算法a)计算个体目标函数复杂度为 $\mathbf { O } ( p o p n u m \times$ popsizexMK{21) $_ { + \mathrm { O } ( }$ popnumxpopsize $\mathbf { \nabla } \times \mathbf { M K T }$ )，d)选取精华种群，计算复杂度为 $\mathrm { O } ( p o p n u m { \times } \mathbf { M } \mathbf { K } ^ { \{ 2 \} } ) { + } \mathrm { O } ( p o p n u m { \times } \mathbf { M } \mathbf { K } \mathbf { T } )$ 。针对整个算法的最大迭代次数maxiter，可以得到MPGA-SR 算法复杂O(MLTxpopsize $\times$ popnum） +O(popsize $\because$ (popnum+1)xMK(2}xmaxiter) $+ \mathrm { O } ($ (popsize $\therefore x$ (popnum $+ 1$ ） $\mathbf { \times M K T } \times$ maxiter)。

# 4 算法的有效性验证

贪婪追踪类算法选用典型的OMP 算法[,4]，凸优化算法采用奇异值分解 $l _ { 1 }$ 范数最小化算法[1}{5]，对OMP、 $l _ { 1 }$ -SVD、GA-SR、SAGA-SR、MPGA-SR这五种算法进行性能比较。

# 4.1 DOA 估计问题

本节针对K-稀疏信号的恢复问题，以空间信源的波达方向(directionofarrival)估计[1.6作为仿真实验，将本文提出算法与贪婪追踪类算法中的正交匹配追踪算法（OMP）、凸松弛类算法中的基于1范数约束的凸优化算法（ $l _ { 1 }$ -SVD）法进行比较，以验证本文所提方法在估计精度和估计效率上的性能提高。

考虑K个窄带相干信号分别从 $\theta _ { 1 } , \theta _ { 2 } , . . . , \theta _ { K }$ 入射到M个各向同性的传感器构成的均匀线阵上。阵元间距为d，快拍数为 $T$ ，阵列流型矩阵为 $\pmb { A } = [ a ( \theta _ { 1 } ) , a ( \theta _ { 2 } ) , . . . , a ( \theta _ { K } ) ]$ ，则建立信号模型：

$$
\pmb { X } ( t ) = \pmb { A } \pmb { S } ( t ) + \pmb { N } ( t ) , t = 1 , . . . , T
$$

将空间角度均匀划分为 $L$ 等份，构造方向矩阵$\overline { { A } } ( \Theta ) = [ a ( \theta _ { 1 } ) , a ( \theta _ { 2 } ) , . . . , a ( \theta _ { L } ) ]$ ，其中：

$a ( \theta _ { i } ) = [ 1 , e ^ { - j 2 \pi d \sin \theta _ { i } / \lambda } , . . . , e ^ { - j 2 \pi ( M - 1 ) d \sin \theta _ { i } / \lambda } ] ^ { T }$ 。采用稀疏重构方法进行求解,建立优化模型如下：

$$
X ( t ) = \overline { { A } } ( \Theta ) S _ { L } ( t ) + N ( t ) , t = 1 , . . . , T
$$

$$
\begin{array} { r } { \operatorname* { m i n } \| X - \overline { { A } } S _ { L } \| _ { F } \quad s . t . \big | \mathfrak { R } ( S _ { L } ) \big | { \le } K } \end{array}
$$

对算法进行有效性验证，以估计误差作为评判准则。分别对以下两种情况进行蒙特卡洛实验，每一点进行200次蒙特卡洛实验。估计误差用估计值与实际值之间的均方根误差来描述：

$$
R M S E = \sqrt { \frac { 1 } { Q K } { \sum _ { k = 1 } ^ { K } } { \sum _ { q = 1 } ^ { Q } } ( \hat { \theta } _ { k , q } - \theta _ { k } ) ^ { 2 } }
$$

其中： $\boldsymbol { Q }$ 为蒙特卡洛实验次数； $\mathrm { ~ \bf ~ K ~ }$ 为信源个数； $\hat { \theta } _ { k , q }$ 表示第 $q$ 次蒙特卡洛实验对第 $k$ 个信号的估计值；$\theta _ { 1 } = 2 2 . 6 ^ { \circ } , \theta _ { 2 } = 2 7 . 2 ^ { \circ } , \theta _ { 3 } = 3 5 . 9 ^ { \circ }$ 表示第 $k$ 个信号的真实值。

# 4.2重构误差随快拍数及信噪比的变化

考虑一个阵元数为 $\scriptstyle \mathrm { m = 2 0 }$ 的均匀直线阵列。智能算法参数设置：种群规模为100，交叉概率为0.85，变异概率为0.05，进化代数为50。模拟退火遗传算法的初始温度为5，降温系数为0.9。多种群遗传算法，种群数为5，种群规模为100，各种群的交叉概率是0.8\~0.9间的随机数，变异概率为$0 . 0 5 { \sim } 0 . 1$ 之间的随机数。

仿真1假设入射信号为3个远场窄带独立信号，信源的入射角度分别为 $\theta _ { 1 } = 2 2 . 6 ^ { \circ } , \theta _ { 2 } = 2 7 . 2 ^ { \circ } , \theta _ { 3 } = 3 5 . 9 ^ { \circ }$ 。固定信噪比为$1 0 ~ \mathrm { d B }$ ，快拍数从100开始以20为步长变化到400，图1(a)为五种算法估计结果的均方根误差随快拍数变化曲线。

仿真2假设入射信号为3个远场窄带独立信号，信源的入射角度分别为 $\theta _ { 1 } = 2 2 . 6 ^ { \circ } , \theta _ { 2 } = 2 7 . 2 ^ { \circ } , \theta _ { 3 } = 3 5 . 9 ^ { \circ }$ 。固定快拍数为200，信噪比从-10dB开始以2dB为步长变化到 $2 \ 0 \mathrm { d B }$ ，图1(b)为五种算法估计结果的均方根误差随信噪比变化曲线。

图1在不同快拍以及不同信噪比下的仿真结果表明所提算法的DOA估计误差明显优于OMP算法。图1(a)的实验结果表明MPGA-SR 算法比 $l _ { 1 }$ -SVD 算法估计性能更优。图1(b)表明在信噪比低情况下， $l _ { 1 }$ -SVD算法估计误差明显大于其他算法，表明了本文所提的两种算法在低信噪比下估计的有效性。对比三种基于遗传算法的估计结果，MPGA-SR算法的估计精度优于SAGA-SR，且SAGA-SR算法的估计精度优于GA-SR算法，验证了改进遗传算法的有效性。

# 4.3重构误差随角度间隔及稀疏度的变化

算法参数与5.2节设置相同。阵元数设为20，固定信噪比 $1 0 ~ \mathrm { d B }$ ，快拍数200。对算法的角度分辨性能以及不同稀疏度下的估计误差进行仿真。

仿真3固定其中一个入射角度为 $3 5 . 7 ^ { \circ }$ ，另外一个角度与固定角的之间的间隔从1°开始，以 $1 ^ { \circ }$ 为步长变化到 $3 0 ^ { \circ }$ 。图2(a)为五种算法角度偏差随空间入射角之间的角度间隔变化曲线。

仿真4空间信源的入射角度为 $\theta _ { 1 } = 2 2 . 6 ^ { \circ }$ ， $\theta _ { 2 } = 2 7 . 2 ^ { \circ }$ ，$\theta _ { 3 } = 3 5 . 9 ^ { \circ }$ 。通过变化阵元数来改变观测信号的稀疏度。稀疏度定义为K/M，K为信源数，M为阵元数。阵元数从3开始以3为步长变化到36。图2(b)为五种算法估计结果的均方根误差随稀疏度变化曲线。

![](images/49c33db2315a34c5f5d2d9479910a50aa51909aea37f9f9af7a8787dd49e2eb4.jpg)  
图1估计误差随信噪比以及快拍数变化性能比较Fig.1Performance comparison of algorithms with RMSE versussnapshot and SNR

图2(a)是角度估计偏差随角度间隔变化仿真结果。当两个信源之间角度相差小于 $1 0 ^ { \circ }$ 时，OMP算法的角度估计偏差明显大于其他四种算法；随着两个信源的角度间隔增大，各算法的角度估计偏差都趋于0，且基于遗传算法的DOA角度分辨性能优于OMP和 $l _ { 1 }$ -SVD算法，MPGA-SR和SAGA-SR算法均优于GA-SR 算法。图2(b)为均方根误差随稀疏度变化曲线。OMP算法对稀疏度极为敏感，在稀疏度接近1时，估计误差急剧增大， $l _ { 1 }$ -SVD 算法的估计误差则与智能算法相近。针对三种智能算法，MPGA-SR算法有更好的估计精度，且SAGA-SR算法优于GA-SR算法。仿真结果验证了智能算法用于DOA估计的有效性，以及混合智能算法的优越性。

# 4.4算法分析

对100次估计结果进行对比，估计参数设置：阵元数20，快拍数200，信噪比为 $1 0 ~ \mathrm { d B }$ ，空间信源 $\theta _ { 1 } = 2 2 . 6 ^ { \circ } , \theta _ { 2 } = 2 7 . 2 ^ { \circ }$ ，$\theta _ { 3 } = 3 5 . 9 ^ { \circ }$ 得到100 次估计的结果的均值如表1所示，算法迭代曲线如图3所示。

表1几种算法在100 次优化中的结果  
Table1Results of 10O runs.   

<html><body><table><tr><td>实际DOA</td><td>22.6°</td><td>27.2°</td><td>35.9°</td><td>RMSE</td></tr><tr><td>OMP估计</td><td>23.6°</td><td>28.2°</td><td>37.7°</td><td>1.7467</td></tr><tr><td>l-SVD估计</td><td>22.6°</td><td>27.1°</td><td>36.6°</td><td>0.1667</td></tr><tr><td>GA-SR估计</td><td>22.1°</td><td>26.8°</td><td>36.7</td><td>0.3500</td></tr><tr><td>SAGA-SR估计</td><td>22.3°</td><td>27.0°</td><td>36.4°</td><td>0.1267</td></tr><tr><td>MPGA-SR 估计</td><td>22.6°</td><td>26.9°</td><td>35.7°</td><td>0.0433</td></tr></table></body></html>

图3为100次估计中，GA-SR稀疏重构算法、SAGA-SR算法和MPGA-SR稀疏重构算法的遗传迭代过程。从图中可以看出这三种遗传算法均能以较快的速度收敛，迭代五次后算法均已收敛到最优解附近。表1列出了100次估计中各算法的DOA估计结果以及相对于实际角度的误差。表2对几种算法的运行时间进行了比较，OMP算法的运行时间最短，$l _ { 1 }$ -SVD算法耗时最长且远大于其他四种算法。遗传算法以及改进遗传算法的运算时间介于OMP算法与 $l _ { 1 }$ -SVD算法之间，且接近于OMP算法。本文所提的两种改进遗传算法的估计精度略优于 $l _ { 1 }$ -SVD 算法，计算效率远高于 $l _ { 1 }$ -SVD算法，因此本文提出的算法在重构精度和运算时间上相比于压缩感知类重构算法都有明显改善。

![](images/aedde50a9ff891e1897d2e3edbc556314c924935930394e01c0aa75b3b5a167e.jpg)  
Fig.2Performance comparison of algorithms with estimation bias versus angle interval and RMSE versus number of array elements

图2估计误差随角度间隔及稀疏度变化性能比较

# 5 结束语

本文算法为求解稀疏重构问题而设计，解的形式是稀疏信号非零元素所在位置的支撑集，算法采用全局寻优策略，因此重构结果受初始解的影响较小。而贪婪追踪类和凸松弛类算法受初始解的影响较大，该类算法是在初始解的周围开始迭代寻优，不容易收敛到最优解。SAGA-SR 算法引入模拟退火算法以一定概率接受恶化解的策略，保持种群的多样性，从而抑制算法过早收敛，提高算法的全局寻优能力。MPGA-SR算法在基本遗传算法的基础上引入多个子种群对解空间进行并行搜索，兼顾了算法的全局和局部搜索能力，降低了遗传控制参数对优化结果的影响，并且对抑制未成熟收敛有明显效果。将所提算法用于DOA估计中，OMP算法以及 $l _ { 1 }$ -SVD算法进行比较，验证了本文所提算法在改善重构精度和提高运算效率方面的有效性。

![](images/698679092bdd8925d72d241314423df0cfe27b11dd2fc38348fd9bb871783794.jpg)  
图3100次迭代收敛曲线  
Fig.3Convergence curve of1OO iterations

表2几种算法在100 次优化中的平均运算时间  
Table 2Average runing time of 1Oo runs   

<html><body><table><tr><td>算法</td><td>OMP</td><td>GA-SR</td><td>SAGA-SR</td><td>MPGA-SR</td><td>l1-SVD</td></tr><tr><td>时间/s</td><td>0.025</td><td>1.114</td><td>1.216</td><td>1.437</td><td>23.701</td></tr></table></body></html>

# 参考文献：

[1]Zhang Zheng，Xu Yong，Yang Jian，et al．A survey of sparse representation:algorithms and applications [J].IEEE Access,2O15(3): 490-530.   
[2]Li E,Shafiee M J,Kazemzadeh F,et al. Sparse reconstruction of compressive sensing multi-spectral data using an inter-spectral multi-layered conditional random field model [J].IEEE Access,2017 (4): 5540-5554.   
[3]Foucart S,Rauhut H.A mathematical introduction to compressive sensing [J]. Journal of the Japan Statistical Society Japanese Issue,2015 (44): 61-69.   
[4]Liang Ruihua, Du Xinpeng, Zhao Qingbo,et al. Sparse signal recovery based on simulated annealing [J]，Applied Mechanics and Materials, 2013 (321-324): 1295-1298.   
[5] Du Xinpeng,Cheng Lizhi, Chen Daiqiang.A simulated annealing algorithm for sparserecovery byl0 minimization[J]. Neurocomputing, 2014,131(9):98-104.   
[6] 刘鲁锋，杜新鹏，成礼智．一种基于粒子群优化的稀疏恢复算法 [J]，电子与信息学报 2013,35(11):2733-2738.(Liu Lufeng，Du Xinpeng ，Cheng Lizhi. A sparse recovery algorithm based on particle swarmoptimization [J].Jounal of Electronics& Information Technology,2013,35 (11): 2733-2738.）   
[7] 王春光，刘金江，孙即祥．基于粒子群优化的稀疏分解最优匹配原 子搜索算法[J]．国防科技大学学报，2008 (2)：83-87.(Wang Chunguang,Liu Jinjiang,Sun Jixiang. Algorithm of searching for the best matching atoms based on particle swarm optimization in sparse decomposition [J].Journal of National University of Defense Technology,2008 (2): 83-87.)   
[8]Brajovi M, Lutovac B,Orovi I, et al. Sparse signal recovery based on concentration measures and genetic algorithm [Cl// Proc of the 13th Symposium on Neural Networksand Applications.Piscataway NJ: IEEE Press,2016: 22-24.   
[9] Chen Yijun， Zhang Qun，Luo Ying，et al. Measurement matrix optimization for isar sparse imaging based on genetic algorithm [J]. IEEE Geoscience and Remote Sensing Leters，2016，13 (12): 1875-1879.   
[10]Li Yangyang，Wang Yang，Li Yaxiao，et al.Singleimage super-resolution reconstruction based on genetic algorithm and regularization prior model [J]. Information Sciences An International Journal,2016,372 (C): 196-207.   
[11]张雪.MUSIC 谱峰搜索遗传算法研究及其 FPGA 实现[D].哈尔滨： 哈尔滨工业大学，2013.(Zhang Xue.The MUSIC spectral peak searching based on genetic algorithm and its FPGA implementation [D]. Harbin: Harbin Institute of Technology,2013.)   
[12] 贾伟娜，刘顺兰．模拟退火遗传算法在 DOA 估计技术中的应用[J]. 计算机工程与应用,2014,50(12):266-270.(Jia Weina,Liu Shunlan. Application of simulated annealing geneticalgorithm in DOA estimation technique [J]. Computer Engineering and Applications,2014, 50 (12): 266-270)   
[13] Du Xinpeng,Cheng Lizhi, Liu Lufeng. A swarm intelligence algorithm for joint sparse recovery [J]. IEEE Signal Processing Letters,2013,20 (6): 611-614.   
[14] Liu Jing,Zhou Weidong,Juwono F H,et al. Reweighted smoothed l0-norm based DOA estimation for MIMO radar[J]. Signal Processing, 2017,137 (C): 44-51.   
[15] Hosseini S M,Sadeghzadeh R A, Virdee B S. DOA estimation using multiple measurement vector model with sparse solutions in linear array scenarios[J]．Eurasip Journal on Wireless Communications& Networking,2017,2017 (1): 58.   
[16] Shi Zhiguo,Zhou Chengwei,Gu Yujie,et al. Source estimation using coprime array:a sparse reconstruction perspective [J].IEEE Sensors Journal,2017,17 (3): 755-765.