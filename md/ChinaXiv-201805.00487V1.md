# 求解0-1背包问题的混合蝙蝠算法

万晓琼，张惠珍(上海理工大学 管理学院，上海 200093)

摘要：针对基本蝙蝠算法易陷入局部最优、收敛速度慢等缺点，对其进行优化研究。基于0-1背包问题的具体特征，在基本蝙蝠算法原有概念和框架的基础上，引入遗传算法中的交叉机制以及反置算子建立全新的位置转移方式和局部搜索规则；加入贪心策略进行解的可行化和充分利用，增强局部搜索能力，加快算法收敛速度，构建全新的混合蝙蝠算法。将混合蝙蝠算法应用于两组0-1背包算例，仿真实验结果优于自适应元胞粒子群算法、基本蝙蝠算法和贪心二进制蝙蝠算法。结果验证了该混合算法求解0-1背包问题的可行性和有效性。

关键词：0-1背包问题；蝙蝠算法；遗传算法；反置算子；贪心策略中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.01.0137

# Hybrid bat algorithm for solving O-1 knapsack problem

Wan Xiaoqiong, Zhang Huizhen† (SchoolofManagement,University ofShanghai for Science&Technology,Shanghai20o093,China)

Abstract: Inorder toovercome the shortcomings of the basic bat algorithm,suchas easytofallinto local optimumand slow convergencespeed,theoptimizationstudywascarredout.Thispaperproposedanewhybridbatalgorithmbasedontheoriginal features,frameworkofthebasicbatalgorithmand specificcharacteristicsof theO-1knapsack problem.Thehybridalgorithm introduced thecrossovermechanismofthe genetic algorithmandtheinverseoperatortoconstructabrand-newlocationtransfer methodandlocalsearchrule.Thegreedystrategywasaddedtomake thesolution feasibleandfullutilized,enhancing thelocal search abilityand speeding up theconvergence.This hybridbatalgorithm was apliedtotwo sets ofO-1knapsack cases.The simulationresults exceeded adaptive celular particle swarmoptimization,basic batalgorithmand greedy binarybatalgorithm. The results verify the feasibility and effectiveness ofthe hybrid algorithm in solving O-1 knapsack problem.

Key words: O-1 knapsack problem; bat algorithm; genetic algorithm; inverse operator; greedy strategy

# 0 引言

背包问题(knapsackproblem,KP）是运筹学中一个典型的NP-Complete 组合优化问题，旨在寻求满足背包约束的条件下具有最大价值的物品装载方案，现实生活中的诸多问题都可被归结为背包算例，如投资决策问题、任务调度问题、货物装载问题、材料切割问题等。背包问题一般可以分为三类：0-1背包问题（O-1knapsackproblem,O-1KP）[1、完全背包问题和多重背包问题，其中0-1背包问题是最基本的背包问题，包含了背包问题设计状态以及方程的最基本思想，其他类型的背包问题也可以转化为0-1背包问题进行求解。本文旨在对0-1背包问题进行研究。

0-1背包问题自提出以来，一直是众多学者研究的热点。从已有的研究成果可以看出，目前求解该问题的算法主要可以分为两类：精确算法和启发式算法。精确算法如：分支定界法23]、动态规划法、回溯法5、贪心算法等。精确算法虽然可以求得优化问题的最优解，但无法解决随着物品数量的增加而产生的“组合爆炸”问题，启发式算法的出现，为解决此类问题开辟了一条新途径。现在已有多种启发式算法被用来解决0-1背包问题，如蚁群算法[8]、和声算法[9-11]、遗传算法[12.13]、粒子群算法[14.15]、狼群算法[16]、鲸鱼算法[17]、蜻蜓算法[18]等。上述算法在解决0-1背包问题时取得了一定的成果，同时也显现出易早熟、后期收敛速度慢等不足。为了克服单一启发式算法的缺点，运用混合算法求解组合优化问题成为趋势，如混合遗传算法[19]、基于遗传算子的蚁群算法[20]、基于贪心策略的遗传算法[21]等。

蝙蝠算法（bat algorithm,BA）[22]是剑桥大学学者 YangXinshe基于蝙蝠回声定位行为于2010年提出的一种启发式算法，具有参数少、结构简单、鲁棒性强等优点。然而，与其他启发式算法相似，基本蝙蝠算法也存在易陷入局部最优和收敛速度慢等缺点。针对这些缺点，本文在基本蝙蝠算法原有概念和结构的基础上，引入遗传算法中的交叉机制提高全局搜索能力，加入反置算子和贪心策略增强局部搜索能力，设计出全新的混合蝙蝠算法（hybrid batalgorithm,HBA）来求解O-1背包问题，并与文献[23,24]的0-1背包算例相对比，结果验证了该算法在寻优能力和收敛速度上均有较大优势。

# 1 0-1 背包问题

0-1背包问题是经典的组合优化问题，具体可以描述为：给定有重量限制的背包以及具有重量和价值的 $n$ 个待装物品，求解目标为在背包载重限制下选择物品装入背包并使得装入物品价值最大。该问题数学模型表示如下：

$$
\begin{array} { l } { m a x ~ F ( x ) = \displaystyle \sum _ { i = 1 } ^ { n } v _ { i } x _ { i } } \\ { s . t . ~ \displaystyle \sum _ { i = 1 } ^ { n } w _ { i } x _ { i } \leq C } \end{array}
$$

$$
x _ { i } = \left\{ \begin{array} { l l } { { 1 , \frac { { \mathcal H } { \mathcal W } _ { \sf H } ^ { \mit \mit \perp } } { \mit \Psi } i } } \\ { { 0 , \phantom { \frac { { \mathcal H } } { \mit \Theta } } \frac { \partial } { \partial \mit \Psi } \left| \right| } } \end{array} \right.
$$

模型中， $I = \{ \ : i \mid i = 1 , 2 , \ldots n \}$ 为物品集; $v = \{ \mathbf { v } _ { i } \mid i =$ 1,2，...n}为物品价值集； $\mathbf { w } = \{ \mathbf { w } _ { i } \mid i = 1 , 2 , \ldots n \}$ 为物品重量集； $c$ 为背包载重量；目标函数式（1）表示最大化装入背包物品价值；约束式（2）保证装入背包物品的总重量不超出背包载重量；约束式（3）中 $x _ { i }$ 为决策变量。

# 2 混合蝙蝠算法

蝙蝠算法是自然界中蝙蝠群体回声定位行为的智能模拟，是一种搜索全局近似解的智能优化算法。蝙蝠个体是蝙蝠算法的基本单元，它们通过嘴巴和鼻孔向外发射很强的超声波，并通过超凡的大耳廓接收回音，再依据发出超声波和接收到回声之间的时差、到达两耳之间的强度差、回声定位波形变化建立空间三维场景来感知猎物或障碍物的距离、方位以及性质，进而制定捕捉猎物和躲避障碍物的计划。算法思想可以概括为：蝙蝠种群随机散布于 $n$ 维问题空间内，把它们映射为优化问题空间内的 $s$ 个解，所优化问题的目标函数对应解的适应度值，适应度值决定解的优劣，算法的优化过程即为蝙蝠种群的其他个体调整响度、脉冲发射率在解空间中追随最优蝙蝠的迭代过程。

# 2.1求解0-1背包问题的混合蝙蝠算法

蝙蝠算法最初被用来求解函数优化问题，近几年有学者提供新的改进思想和方法去解决离散问题。在本文中，为了把蝙蝠算法应用于0-1背包问题，在求解优化问题的过程中，利用二进制编码方式初始化蝙蝠位置，在蝙蝠位置更新规则中引入遗传算法的交叉机制，利用反置算子构建全新的局部搜索规则，称之为混合蝙蝠算法，下文从初始化蝙蝠位置、蝙蝠速度与位置更新、局部搜索以及音量和脉冲的更新四个方面来介绍混合

蝙蝠算法。

# 2.1.1初始化蝙蝠位置规则

根据0-1背包问题解的性质，本文采用二进制编码方式随机初始化蝙蝠种群位置。用1\*n维向量xi=(xi，Xi2,,Xin)表示第i只蝙蝠的初始位置，其中 $x _ { i j } \in \{ 0 , 1 \} , 1 \leq j \leq n$ ，当$x _ { i j } = 1$ 时，物品 $j$ 装入背包，反之，物品 $j$ 不装入背包。具体映射关系如式（4）所示。

$$
x _ { i j } = \left\{ \begin{array} { c l } { 1 , } & { \ r a n d > 0 . 5 } \\ { 0 , } & { \ r a n d \leq 0 . 5 } \end{array} \right.
$$

2.1.2蝙蝠速度与位置更新规则

1）速度更新规则

由于离散优化问题的特殊性，在初始化蝙蝠位置以及后续速度定义、位置转移编码都是一步到位的，故删去基本蝙蝠算法中频率 $f$ 这个参数。重新定义第 $i$ 只蝙蝠 $x _ { i }$ 和最优蝙蝠 $x _ { * }$ 之间的Manhattan 距离为蝙蝠的速度。则第 $i$ 只蝙蝠在定义的搜索空间中第 $t$ 时刻 $\boldsymbol { v } _ { i } ^ { t }$ 的更新公式为

$$
v _ { i } ^ { t } = \sum _ { j = 1 } ^ { n } \bigl | x _ { i j } - x _ { * j } \bigr |
$$

# 2）位置更新规则

本文采用遗传算法中的交叉机制进行位置转移，一只蝙蝠对应一条染色体，位置更新过程主要可以分为两步：

a)子代遗传父代的相同基因。具体为：设最优蝙蝠 $\mid x _ { * }$ 为父代1，第 $i$ 只蝙蝠 $x _ { i }$ 为父代2，对比父代1、2相应的基因位，当基因相同（即相应基因位上同为1或0）时，将相应基因直接遗传给子代；当基因不同时，子代相应基因位以通配符 $*$ 填充，记此时的子代蝙蝠位置为 $\boldsymbol { \cdot } \boldsymbol { x } _ { m i d }$ 。

b) $x _ { m i d }$ 中通配符的个数为 $v _ { i } ^ { t }$ ，即为第 $i$ 只蝙蝠的转移速度，对于这 $v _ { i } ^ { t }$ 个不同的基因，设置追随概率 ${ \cdot } p _ { f o l }$ ，建立转移公式如式（6）所示。

$$
x _ { n e w } = x _ { m i d } \big ( v _ { i } ^ { t } , ~ p _ { f o l } \big )
$$

具体为：当 $r a n d > p _ { f o l }$ 时，子代追随最优蝙蝠，遗传父代1的对应基因，反之，遗传父代2的对应基因，最后更新子代蝙蝠位置为 $x _ { n e w }$ 。利用这种交叉机制，一方面子代可以遗传父代优秀的基因。另一方面，加入追随概率 ${ \cdot } p _ { f o l }$ ，增添跟从最优蝙蝠的随机性以维持蝙蝠种群的多样化，一定程度上克服了基本蝙蝠算法容易早熟的缺点。以 $n = 6$ 为例，具体交叉重组过程如图1所示。

# 2.1.3局部搜索规则

本文采用的局部搜索方式有两种，一为利用反置算子对最优蝙蝠进行局部搜索；二为使用贪心策略对不可行解和非充分利用解进行局部搜索。

# 1）反置算子

相对于其他智能优化算法，蝙蝠算法可以通过比较脉冲发生率 $r _ { i }$ 和随机数的大小，实现对全局搜索和局部搜索之间动态转换。即当 $r a n d > r _ { i }$ 时，在当前最优解集中选取一个最优蝙蝠，进行随机游走，产生局部新解。由于二进制编码的特殊性，基本蝙蝠算法的局部搜索方式并不能取得优异结果。本文引入反置算子设置全新的局部搜索规则，具体为：反置概率 $p _ { n o t }$ 随机选取最优蝙蝠的 ${ { n } * { p } _ { { { n o t } } } }$ 个基因进行反置处理，最后更新局部新解 $x _ { n e w }$ 。这种随机反置的局部搜索方式使得随着迭代次数增加而趋于相似的蝙蝠种群容易跳出局部最优。对于选定的基因位$j _ { n o t } \in J _ { n o t }$ 具体优化方法如下：

$$
x _ { n e w j _ { n o t } } = \left\{ \begin{array} { l l } { \ 1 , \quad } & { x _ { * j _ { n o t } } = 0 } \\ { \ 0 , \quad } & { x _ { * j _ { n o t } } = 1 } \end{array} \right.
$$

![](images/747cde9df5d7e813c8f8742f27808bfb1a8b04663b1f7e59bf3704d60a9406b7.jpg)  
图1蝙蝠算法位置更新过程

2）贪心策略

a）对不可行解进行贪心策略。0-1背包问题作为具有约束条件的组合优化问题，在蝙蝠位置随机初始化、位置更新以及反置算子局部搜索部分均有可能产生无效解，即装入物品总重量超出背包重量限制，针对这些不可行解若直接舍弃，则会丢失已搜索到的信息，导致算法收敛速度变慢，故本文引入贪心策略对不可行解进行局部搜索：计算已装入背包物品的价值比$v o l _ { i } = v _ { i } / w _ { i }$ ，依次舍去低价值比的物品，直至剩余物品总重量不超出背包载重。

b)对可行解进行贪心策略。由于初始化解的随机性和可行化解的限制，可能导致背包容量的不充分利用，针对这部分解采用贪心策略进行局部搜索：计算未装入背包的物品价值比$v o l _ { i } = v _ { i } / w _ { i }$ ，依次加入高价值比的物品，直至背包利用率达到最大。

# 2.1.4蝙蝠音量和脉冲发生率更新规则

在蝙蝠接近猎物时，超声波音量逐渐降低，脉冲发生率逐步提高。音量 $A _ { i } ^ { t }$ 和脉冲发生率 ${ \bf \nabla } \cdot { \bf { \vec { \tau } } } ^ { t }$ 的更新公式为

$$
A _ { i } ^ { t } = \alpha A _ { i } ^ { t - 1 }
$$

$$
r _ { i } ^ { t } = r _ { i } ^ { 0 } ~ \{ 1 - e x p [ - \gamma ( t - 1 ) ] \}
$$

其中： $\alpha$ 为音量衰减系数， $\gamma$ 为脉冲发生率增长系数， $r _ { i } ^ { 0 }$ 为最大脉冲频率。对任意 $0 < \alpha < 1$ ， $\gamma > 0$ ，可以看出： $A _ { i } ^ { t }  0$ ， $r _ { i } ^ { t } $ $r _ { i } ^ { 0 }$ ，as $t \to \infty$ 。

# 2.2求解0-1背包问题的混合蝙蝠算法设计

通过对基本蝙蝠算法的改造，设计出全新的求解0-1背包问题的混合蝙蝠算法。具体步骤如下：

a)初始化蝙蝠种群。蝙蝠种群大小为 $s$ ，第i只蝙蝠的位置为 $x _ { i }$ ，速度为 $\boldsymbol { v } _ { i }$ ，追随概率 ${ { p } _ { f o l } }$ ，反置概率 $p _ { n o t }$ ，音量为 $A _ { i } ^ { 0 }$ ，脉冲发生率为 $r _ { i } ^ { 0 }$ ，最大迭代次数 $N _ { - } g e n$ ，并根据式（4）初始化蝙蝠位置。

b)蝙蝠速度和位置更新。计算得出最优蝙蝠 $x _ { * }$ ，运用式（5）更新蝙蝠速度 $v _ { i } ^ { t }$ ，利用遗传算法的交叉机制更新蝙蝠位置xnew

c)局部搜索。若 $r a n d > r _ { i }$ ，根据式（7）对最优解集中选取的最优解进行局部搜索,得出局部新解xnew。

d)更新满意解。若 $r a n d < A _ { i }$ 且 $F ( x _ { n e w } ) < F ( x _ { * } )$ ，更新当前满意解及其对应的目标函数值。

e)更新音量和脉冲发生率。通过式（8）减小 $A _ { i }$ ，式（9)增大 $r _ { i }$ 。

f)排列蝙蝠并找到当前最优蝙蝠 $x _ { * }$ 。

$\mathrm { g } ) N \_ i t e r = N \_ i t e r + 1$ ，若 ${ \dot { \cdot } } N _ { - } i t e r > N _ { - } g e n$ ，则结束搜索并输出结果,否则转b)。

（注：在初始化蝙蝠种群、蝙蝠位置更新和反置算子局部搜索后均要使用贪心策略进行解的可行化和充分利用。)

# 3 仿真实验与分析

为了验证本文提出的混合蝙蝠算法的有效性，文章选用两组算例测试其求解性能。第1组算例选用文献[23]的9个0-1背包问题进行测试，并将其求解结果与自适应元胞粒子群算法(adaptive cellular particle swarm optimization,ACPSO)[23]的测试结果进行对比分析。第2组算例选用文献[24]的三个0-1背包问题进行测试，并与基本蝙蝠算法以及贪心二进制蝙蝠算法（greedybinarybatalgorithm，GBBA）[24]进行比较分析。

本文仿真实验所用硬件环境为Intel(R)CoreTMi5-3320 CPU$@ 2 . 6 0 \mathrm { G H z }$ ，2.0GB内存，64位Windows8操作系统，编程语言为MATLAB $\mathrm { R } 2 0 1 5 \mathrm { a }$ 。文献[23]自适应元胞粒子群算法的仿真计算环境为CoreTM2Duo CPU为 $2 . 9 3 \mathrm { G H z }$ ，内存 $1 . 9 3 \mathrm { G B }$ ，操作系统WindowsXP，编程语言为 MATLAB。文献［24］贪心二进制蝙蝠算法的仿真实验所用的硬件环境为 Intel $\textsuperscript { \textregistered }$ Core TMDuo CPUT24001.83GHz，内存为1GB，操作系统为WindowsXP2002，编程语言为 $\mathrm { V C } + + 6 . 0$ 。

为体现算法对比结果的公平性，本文求解第1组算例的蝙蝠种群大小s、最大迭代次数 $N _ { - } g e n$ 、单个算例运行次数T和文献[23]的粒子群算法中的种群大小、最大迭代次数及单个算例运行次数设置相同，即 $s = 5 0$ ， $N _ { - } g e n = 5 0 0$ ， $\mathrm { T } = 3 0$ 。其他参数遵从算法的具体特征，设置为：初始音量 $A _ { i } ^ { 0 } = 0 . 2 5$ ，初始脉冲发生率 $r _ { i } ^ { 0 } = 0 . 5$ ， $\alpha = \gamma = 0 . 9$ ，追随概率 $p _ { f o l } = 0 . 5$ ，反置概率 $p _ { n o t } = 0 . 2$ 。

表1给出第1组9个测试算例的维数、物品重量集w、物品价值集 $v$ 、背包载重量 $c$ 以及已知最优值。

表 $\mathrm { ~ 1 ~ } 0 \mathrm { - } 1$ 背包问题的9组仿真算例  

<html><body><table><tr><td>算例</td><td>维数</td><td>背包问题</td><td>已知最优</td></tr><tr><td>KP1</td><td>10</td><td>w = (95,4,60,32,23,72,80,62,65,46); v = (55,10,47,5,4,50,8,61,85,87); C =269</td><td>295</td></tr><tr><td>KP2</td><td>20</td><td>w=(92,4,43,83,84,68,92,82,6,44,32,18,56,83,25,96,70,48,14,58);v=[44,46,90,72,91,40,75,35,8,54,78,40, 77,15,61,17,75,29,75,63]; C = 878</td><td>1024</td></tr><tr><td>KP3</td><td>20</td><td>w=(44,46,90,72,91,40,75,35,8,54,78,40,77,15,61,17,75,29,75,63)v=(92,4,43,83,84,68,92,82,6,44,28, 56,83,25,96,70,48,14,58); C = 878</td><td>1042</td></tr><tr><td>KP4</td><td>50</td><td>w =(95,39,69,63,49,104,56,58,47,23,17,129,91,28,77,125,73,5,103,63,76,23,47,79,119,125,26,19,79, 56,50,75,12,26,31,43,41,38,29,21,14,9,3,17,8,8,9,7,4,5);v =(293,291,290,280,278,274,269,265,248, 247,245,245,241,234,229,228,222,216,214,191,191,187,171,170,164,152,142,132,131,126,122,116, 112,111,110,106,77,76,74,73,69,67,42,41,35,33,30,29,28,26); C = 959</td><td>4882</td></tr><tr><td>KP5</td><td>100</td><td>22,96,49,81,48,37,28,6,84,19,55,88,38,51,52,79,55,70,53,64,99,61,85,1,64,32,60,42,45,34,22,497,3, 1,78,43,85,24,96,32,99,57,23,8,10,74,59,89,95,40,46,65,6,89,84,83,6,19,45,59,26,13,8,26,5.9);v = (297, 295,293,292,291,289,284,284,283,283,281,280,279,277,276,275,273,264,260,257,250,236,236,235,3 5,233,232,232,228,218,217,214,211,08,205,204,203,201,196,194,193,93,192,191,190,187,874,1 84,184,181,179,176,173,172,171,160,128,123,114,113,107,105,101,100,100,99,98,97,94,94,93,91,80,7 4,73,72,63,63,62,61,60,56,53,52,50,48,46,40,40,35,28,22,22,18,15,12,11,6,5); C = 3820</td><td>15170</td></tr><tr><td>KP6</td><td>100</td><td>w=(54,183,106,82,0,58,71,166,117,90,90,91,205,128,110,89,63,6,140,86,30,91,156,31,7099,14, 98,178,16,140,31,24,197,101,73,169,73,92,159,71,102,144,151,27,131,209,164,177,177,29,146,17,53 ,164,146,43,170,180,171,130,183,5,113,207,57,13,163,20,63,12,24,9,42,6,109,170,108,46,69,43,175,81 ,5,34,146,148,114,60,174,56,82,4726,02,83,58,4,21,14);v=(597,596,593,586,581,568,567,560,54 9,548,547,529,529,527,520,491,482,478,475,475,466,462,459,458,454,451,449,443,442,421,410,409,3 95,394,390,77,75,6661347,334,2,15,313311,09296,295,294,89,285,279,277,276,,48， 246,245,238,237,232,231,230,225,192,184,183,176,174,171,169,165,165,154,153,150,149,147,143,4 0,138,134,132,127,124,123,114,111,104,89,74,63,62,58,55,48,27,22,12,6); C =6718</td><td></td></tr><tr><td>KP7</td><td>100</td><td>w=(94,81,8,62,21,83,85,45,48,81,4,64,59,97,96,14,21,59,34,8,36,2,3,65,26,48,25,17,11,97,43,23,24,48, 56,73,54,15,98,99,47,93,78,68,24,52,8,89,100,7,9,46,8,40,77,46,76,78,7,32,92,11,93,75,6,60,64,15,99,3 0,99,61,17,3,31,34,76,68,79,91,95,25,73,43,89,9,2,31,71,24,19,70,76,14,50,85,40,78,2,6)v=(4,08, 18,39,57,4,74,86,77,59,4574,99,46,6899,83,23,8580,41,58,11,35,73,100,2,79,58,70,40,6,9,26,2,92,4 0,45,65,50,0,537,41414,72,41,46,76,13,78,77,77,43,1,32,2,,731,46,55,95</td><td></td></tr><tr><td>KP8</td><td>100</td><td>w=(94,81,8,62,21,3,85,45,48,81,4,64,59,97,96,14,21,59,34,68,6,2,3,65,26,48,25,17,11,97,43,23,4,48 56,73,54,15,98,99,47,93,78,68,24,52,8,89,100,7,9,46,8,40,77,46,76,78,7,32,92,11,93,75,6,60,64,15,99,3 0,99,61,17,3,31,34,76,68,9,915,25,,43,8992,1,71,24,19,70,76,14,50,5,40,78,2,6)v=(4,, 18,39,57,4,74,86,77,59,4574,99,46,6899,83,23,8580,41,58,11,35,73,100,2,79,58,70,40,6,9,26,2,92,4 0,45,65,50,80,53,37,84,14,14,72,41,46,76,13,78,77,77,49,29,63,61,32,2,6,47,31,46,5,85,9,64,524,5 ,26,50,81,89,61,44,95,40,27,83,81,85,32,60,91,44,54,31,48,50,94,32,83,24,40,43,11); C =2499</td><td></td></tr><tr><td>KP9</td><td>100</td><td>w=(94,81,8,62,21,3,5,45,48,81,4,64,59,97,96,14,21,59,34,68,36,2,3,65,26,48,25,17,1,97,43,23,4,8, 56,73,54,15,98,99,47,93,78,68,24,52,8,89,00,7,9,46,8,40,77,46,76,78,7,32,92,11,93,75,6,60,64,15,99,3 0,99,61,17,3,31,34,76,68,79,91,95,25,73,43,89,9,12,31,71,24,19,70,76,14,50,85,40,78,12,6)=(94,088, 18,39,57,4,74,86,77,59,4574,99,46,6899,83,23,8580,41,58,11,35,73,100,2,79,58,70,40,6,9,26,2,924 0,45,65,50,80,53,37,84,14,14,72,41,46,76,3,78,77,77,49,2963,61,32,2,6,47,31,46,35,85,9,64,52,4,5 ,26,50,81,89,61,44,95,40,27,83,81,85,32,60,91,44,54,31,48,50,94,32,83,24,40,43,11); C =3998.4</td><td>4986</td></tr></table></body></html>

每个算例独立测试30次，结果如表2所示。其中，实验最优值、实验平均值、实验最差值由30次运行结果对比得出；总消耗时间为30次独立实验的运行总时间；成功次数为30次测试中找到当前最优解的次数；最小迭代次数、平均迭代次数、最大迭代次数为找到最优值的前提下对比实验结果得出。表2中 ACPSO算法的实验结果均来自文献[23]。

由表2可看出，对于算例KP9，HBA算法得出的实验最优解为4987，实验平均值为4986.5，优于ACPSO给出的已知最优值4986，说明HBA的全局搜索能力优于ACPSO；对于算例KP1\~KP8，从成功次数可以看出，HBA运行的结果除算例KP6以外，其他算例30 次测试均能达到最优值，而ACPSO 只有KP1、KP5、KP8能 $100 \%$ 达到最优值，二者对比说明HBA寻优的鲁棒性较强；且从迭代次数的三个实验指标可以看出，HBA能在较低的迭代次数中达到最优解，除KP5算例外，均远优于ACPSO，说明HBA具有较快的收敛速度。综合HBA的成功次数以及寻优成功的迭代次数两个方面分析，HBA消耗的总时间显然优于ACPSO。综合所有的实验指标可以看出，HBA的寻优能力远优于ACPSO，在求解0-1背包问题中具有较强的求解性能。

表2 实验结果对比  

<html><body><table><tr><td>算例</td><td>算法</td><td>维数</td><td>当前最</td><td>实验最</td><td>实验平</td><td>实验最</td><td>消总</td><td>成功</td><td>最小</td><td>平次数</td><td>最大</td></tr><tr><td rowspan="2">KP1</td><td>ACPSO</td><td rowspan="2">10</td><td rowspan="2"></td><td>295</td><td>295</td><td>295</td><td>0.19</td><td>30</td><td>1</td><td>1.80</td><td>6</td></tr><tr><td>295</td><td>295</td><td>295</td><td>295</td><td>0.63</td><td>30</td><td>1</td><td>1.00</td></tr><tr><td rowspan="2">KP2</td><td>HBA ACPSO</td><td rowspan="2">20</td><td rowspan="2"></td><td>1024</td><td>1.0212e +003</td><td>1018</td><td>50.44</td><td>16</td><td>1</td><td>194.19</td><td>1 441</td></tr><tr><td>1024</td><td>1024</td><td>1024</td><td>1024</td><td>0.62</td><td>30</td><td>1</td><td></td></tr><tr><td rowspan="2">KP3</td><td>HBA ACPSO</td><td rowspan="2">20</td><td rowspan="2"></td><td>1042</td><td>1.0393e +003</td><td>1037</td><td>56.45</td><td>14</td><td>49</td><td>1.43 235.00</td><td>4 474</td></tr><tr><td>1042</td><td>1042</td><td>1042</td><td>1042</td><td>3.29</td><td></td><td></td><td></td></tr><tr><td rowspan="2">KP4</td><td>HBA ACPSO</td><td rowspan="2"></td><td rowspan="2"></td><td></td><td>4.8571e +003</td><td>4834</td><td>131.90</td><td>30</td><td>1</td><td>27.23</td><td>142 421</td></tr><tr><td>50 4882</td><td>4882</td><td>4882</td><td></td><td></td><td>5</td><td>91</td><td>133.93</td></tr><tr><td rowspan="2">KP5</td><td>HBA ACPSO</td><td rowspan="2"></td><td rowspan="2">15170</td><td>4882</td><td>15170</td><td>4882 15170</td><td>1.51</td><td>30</td><td>1</td><td>6.73</td><td>39</td></tr><tr><td>100</td><td>15170</td><td></td><td></td><td>0.94</td><td>30</td><td>1</td><td>1.00</td><td>1</td></tr><tr><td rowspan="2">KP6</td><td>HBA ACPSO</td><td rowspan="2"></td><td rowspan="2">26559</td><td>15170</td><td>15170 2.6527e +004</td><td>15170 26525</td><td>0.91 367.52</td><td>30</td><td>1</td><td>1.83</td><td>2</td></tr><tr><td>100</td><td>26559</td><td></td><td></td><td></td><td>1</td><td>45</td><td>45.00</td><td>45</td></tr><tr><td rowspan="2">KP7</td><td>HBA ACPSO</td><td rowspan="2"></td><td rowspan="2">2660</td><td>26559</td><td>2.6551e+004</td><td>26534</td><td>35.47</td><td>14</td><td>2</td><td>10.43</td><td>103</td></tr><tr><td>100</td><td>2660</td><td>2660</td><td>2660</td><td>203.25</td><td>13</td><td>20</td><td>190.38</td><td>417</td></tr><tr><td rowspan="2">KP8</td><td>HBA ACPSO</td><td rowspan="2"></td><td rowspan="2">4143</td><td>2660</td><td>2660</td><td>2660</td><td>1.27</td><td>30</td><td>1</td><td>2.47</td><td>5</td></tr><tr><td>100</td><td>4143</td><td>4143</td><td>4143</td><td>37.73</td><td>30</td><td>4</td><td>58.83</td><td>162</td></tr><tr><td rowspan="2"></td><td>HBA</td><td></td><td></td><td>4143</td><td>4143</td><td>4143</td><td>1.45</td><td>30</td><td>3</td><td>4.57</td><td>9</td></tr><tr><td>ACPSO</td><td>100</td><td></td><td>4986</td><td>4986</td><td>4986</td><td>0.80</td><td>30</td><td>1</td><td>1.00</td><td>1</td></tr><tr><td rowspan="2">KP9</td><td></td><td></td><td>4986</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>HBA</td><td></td><td></td><td>4987</td><td>4.9865e+003</td><td>4986</td><td>31.17</td><td>15</td><td>2</td><td>4.73</td><td>33</td></tr></table></body></html>

为充分测试各算法的求解性能，体现对比公平性，本文在测试第2组算例时，混合蝙蝠算法中初始音量 $A _ { i } ^ { 0 } = 0 . 0 0 5$ 、初始脉冲发生率 $r _ { i } ^ { 0 } = 0 . 7 5$ 、音量衰减系数 $\alpha = 0 . 9 5$ 、脉冲发生率增长系数 $\gamma = 0 . 7$ 、单个算例测试次数 $\mathrm { T } = 5 0$ 均沿用文献[24]的设置，追随概率 $p _ { f o l }$ 、反置概率 $p _ { n o t }$ 同第1组算例。第2组算例选用文献[24]的3个算例，其中算例1、算例2和第1组算例中的KP1、KP2相同，具体见表1；算例3如表3所示。

对3个算例分别进行测试，结果如表4、表5所示。表4为BA、GBBA与HBA求解算例1\~3达到最大迭代次数时的目标函数值的比较。对比50次测试结果得出最差值、平均值和最优值；表5为BA、GBBA与HBA求解算例1\~3的收敛性比较，当算法在最大迭代次数限制内达到最优值时为寻优成功，记录下迭代次数，对比50次运行结果得出最小数、平均数和成功率。表4、表5中GBBA的实验结果均来自文献[24]。对于算例3，在目标函数值的对比中最大迭代次数设置为300，在收敛比较中最大迭代次数设置为500，为了实验对比结果的公平性，本文和文献[24]设置相同。

表4BA、GBBA与HBA求解算例1\~3的目标函数值比较  

<html><body><table><tr><td>算例</td><td>维数</td><td>背包问题</td><td>已知最优值</td></tr><tr><td>算例3</td><td>50</td><td>w= [438,754,699,587,789,912,819,347,511,287,541,784,676,198,572,914,988, 4,355,569,144,272,531,556,741,489,321,84,194,483,205,607,399,747,118,651, 806,9,607,121,370,999,494,743,967,718,397,589,193,369];v=[72,490,651,33,8 83,489,359,337,267,441,70,934,467,661,220,329,440,774,595,98,424,37,807,32 0,501,309,834,851,34,459,111,253,159,858,793,145,651,856,400,285,405,95, 391,19,96,273,152,473,448,231];C=11258;</td><td>16102</td></tr></table></body></html>

表30-1背包问题的仿真  

<html><body><table><tr><td>算例</td><td>算法</td><td>种模</td><td>最大</td><td>最差值</td><td>平均值</td><td>最优值</td></tr><tr><td rowspan="3">算例1</td><td>BA</td><td rowspan="3">4</td><td rowspan="3">300</td><td>158</td><td>226.42</td><td>295</td></tr><tr><td>GBBA</td><td>294</td><td>294.80</td><td>295</td></tr><tr><td>HBA</td><td>294</td><td>294.90</td><td>295</td></tr><tr><td rowspan="3">算例2</td><td>BA</td><td rowspan="3">4</td><td rowspan="3">300</td><td>813</td><td>918.36</td><td>995</td></tr><tr><td>GBBA</td><td>1018</td><td>1019</td><td>1024</td></tr><tr><td>HBA</td><td>1018</td><td>1023.40</td><td>1024</td></tr><tr><td rowspan="3">算例3</td><td>BA</td><td rowspan="3">15</td><td rowspan="3">300</td><td>7989</td><td>10126.12</td><td>12224</td></tr><tr><td>GBBA</td><td>16012</td><td>16053</td><td>16102</td></tr><tr><td>HBA</td><td>16029</td><td>16086.84</td><td>16102</td></tr></table></body></html>

表5BA、GBBA与HBA求解算例 $\boldsymbol { \mathrm { 1 \widetilde { 3 } } }$ 的收敛性比较  

<html><body><table><tr><td>算例</td><td>算法</td><td>种群 规模</td><td>最大迭 代次数</td><td>最小数</td><td>平均数</td><td>成功率</td></tr><tr><td rowspan="3">算例1</td><td>BA</td><td rowspan="3">15</td><td rowspan="3">300</td><td>4</td><td>5</td><td>3/50</td></tr><tr><td>GBBA</td><td>5</td><td>5.3</td><td>47/50</td></tr><tr><td>HBA</td><td>1</td><td>11.56</td><td>50/50</td></tr><tr><td rowspan="3">算例2</td><td>BA</td><td rowspan="3">15</td><td rowspan="3">300</td><td>4</td><td>4</td><td>1/50</td></tr><tr><td>GBBA</td><td>8</td><td>19.29</td><td>41/50</td></tr><tr><td>HBA</td><td>1</td><td>13.26</td><td>50/50</td></tr><tr><td rowspan="3">算例3</td><td>BA</td><td></td><td></td><td>0</td><td>0</td><td>0/50</td></tr><tr><td>GBBA</td><td>15</td><td>500</td><td>10</td><td>33.56</td><td>18/50</td></tr><tr><td>HBA</td><td></td><td></td><td>2</td><td>65.95</td><td>44/50</td></tr></table></body></html>

由表4的最优值可以看出HBA 和GBBA均能求得算例1\~3 的最优解，而基本BA算法仅能求得算例1的最优解，表明改进BA算法一定程度上克服了BA易陷入局部最优的缺点，寻优能力均优于BA。由表4的平均值可以看出HBA的求解结果均优于另外两种算法，且从表5的成功率可以看出，对于算例1和算例2，HBA算法均能 $100 \%$ 求得最优解，求解算例3的成功率也优于其他两种算法，综合两个实验指标可以看出HBA的平均求解精度和求解鲁棒性均优于BA和GBBA。综合表4、5可以看出，HBA求解0-1背包问题的综合能力优于BA和GBBA。

为了更直观地展现出HBA的求解效果，图2\~4给出BA和HBA求解算例1\~3的迭代过程图。如图所示，HBA能在较小的迭代次数内求得最优值，而BA在进行一定的迭代次数后就陷入了局部最优，由此可以看出HBA克服了BA易早熟以及收敛速度慢的缺点，全局搜索能力和收敛速度均远优于BA。

![](images/1916cb56d5e63ae5751c49f08024adad8375a9817125d6a6422e543e697b7fde.jpg)  
图2求解算例1的迭代过程图

![](images/57bad84449a1c88aa15a4c2bd0087b6a76ace87be492f177c76bf77fb83a2562.jpg)  
图3求解算例2的迭代过程图

![](images/d7a217a71fb201c14ebc0dc2bec2a72c5ddb4004fc1710fc4dc9e84614396c1d.jpg)  
图4求解算例3的迭代过程图

# 4 结束语

本文针对0-1背包问题的具体特征，在基本蝙蝠算法的框架基础上加入遗传算法、反置算子和贪心策略，利用四者各自优点，实现优势互补，设计出一种全新的混合蝙蝠算法。该算法克服了基本蝙蝠算法易陷入局部最优和收敛速度慢的缺点。通过对0-1背包算例的仿真对比研究，本文提出的混合蝙蝠算法的综合求解能力优于自适应元胞粒子群算法、基本蝙蝠算法和贪心二进制蝙蝠算法，是求解0-1背包问题的一种有效方法。

# 参考文献：

[1]Fayard D,Plateau G.Resolution of the O-1 knapsack problem comparison of methods [J].Mathematical Programming,1975,8(1):272-307.   
[2]盛红波，孙娟，孙小玲.0-1 多项式背包问题的一种精确算法 [J].上海 大学学报：自然科学版,2006,12(4):389-393.(Sheng Hongbo,Sun Juan, Sun Xiaoling.A rigor method for solving O-1 polynomial knapsack problem [J].Joural of the Shanghai University: Natural Science,20o6,12 (4):389- 393.)   
[3]Shen Jingcheng,Shigeoka K,Ino F,et al.An out-of-core branch and bound method for solving the O-1 knapsack problem ona GPU[J].International Conference on Algorithms & Architectures for Parallel Processing,2017: 254-267.   
[4]Elkihel M,Baz D E.An efficient dynamic programming parallel algorithm for the O-1 kanpsack problem[J].Parallel Computing-advances & Current Issues-the International Conference Parco,2015:298-305.

[5]徐颖．回溯法在0-1背包问题中的应用[J].软件导刊,2008(12):54-55. (Xu Ying. Application of backtracking method in 0-1 knapsack problem [J]. Software Guide,2008 (12): 54-55.)

[6] 史岚，张义宏，吕建辉．基于绝对贪心和预期效率的0-1 背包问题优化 [J].计算机应用研究,2014,31(3):684-687.(Shi Lan,Zhang Yihong,Lv Jianhui. Optimization algorithm of O-1 knapsack problem based on absolute greedy and expected efficiency [J].Application Research of Computers 2014,31(3): 684-687.)   
[7]胡小兵，黄席樾．基于蚁群优化算法的 0-1 背包问题求解[J]．系统工 程学报,2005,20 (5):520-523.(Hu Xiaobing,Huang Xiyue.Solving 0-1 knapsack problem based on ant colony optimization algorithm [J]. Journal of Systems Engineering,2005,20 (5): 520-523.)   
[8]秦玲，白云，章春芳等．解0-1 背包问题的蚁群算法[J].计算机工程, 2006,32 (6): 212-214.(Qin Ling,Bai Yun,Zhang Chunfang,et al.Ant colony algorithm for 0-1 knapsack problem [J]. Computer Engineering, 2006,32 (6): 212-214.)   
[9] 李若平，欧阳海滨，高立群，等．学习型和声搜索算法及其在0-1 背包 问题中的应用[J].控制与决策，2013,28(2):205-210.(Li Ruoping, Ouyang Haibin, Gao Liqun,et al.Learned harmony search algorithm and its application to O-1 knapsack problems [J]. Control and Decision,2013,28 (2): 205-210. )   
[10] Wang Ling,Yang Ruixin,Xu Yin,et al.An improved adaptive binary Harmony Search algorithm [J].Information Sciences,2013,232(5): 58-87.   
[11] Zou Dexuan,Gao Liqun,Li S,et al. Solving O-1 knapsack problem by a novel global harmony search algorithm [J]. Applied Soft Computing Journal, 2011,11 (2): 1556-1564.   
[12]王莉，绍定宏，陆金桂．基于遗传算法的0//1 背包问题求解[J].计算 机仿真,2006,23(3):154-156.(Wang Li,Shao Dinghong,Lu Jingui. The genetic algorithm of solving O//1 knapsack problem [J].Computer Simulation,2006,23 (3): 154-156.)   
[13] Caro F.A flipping local search genetic algorithm for the multidimensional

0-1 knapsack problem [C]// Proc of Spanish Association Conference on Current Topics in Artificial Intelligence.20o5:21-30.

[14] Zhang Guoli,Wei Yi.An improved particle swarm optimization algorithm for solving O-1 knapsack problem [J]. International Conference on Machine

Learning & Cybernetics,2008,2: 915-918.   
[15] Haddar B,Khemakhem M,Rhimi H.A quantumparticle swarm optimization for the O-1 generalized knapsack sharing problem [J].Natural Computing,2016,15 (1): 153-164.   
[16]吴虎胜，张凤鸣，战仁军，等．求解0-1背包问题的二进制狼群算法[J]. 系统工程与电子技术,2014,36(8):1660-1667.(Wu Husheng,Zhang Fengming,Zhan Renjun,et al.A binary wolf pack algorithm for solving 0- 1 knapsack problem[J].Systems Engineringand Electronics,2014,36 (8): 1660-1667. )   
[17] Abdel-Basset M, El-Shahat D,Sangaiah A K.A modified nature inspired meta-heuristic whale optimization algorithm for solving O-1 knapsack problem [J]. International Journal ofMachine Learning & Cybernetics,2017 (1): 1-20.   
[18] Abdel-Basset M,Luo Qifang,Miao Fahui,et al.Solving O-1 knapsack problems by binary dragonflyalgorithm [Cl// Proc of International Conference on Intelligent Computing.2017: 491-502.   
[19] Cotta C,Troya JM.Ahybrid genetic algorithm for the O-1 multiple knapsack problem [J].Artificial Neural Nets & Genetic Algorithms,1998: 250-254.   
[20] Hu Zhijun,LiRong.Ant colony optimization algorithm for the O-1 knapsack problem based on genetic operators [C]// Advanced Materials Research. 2011: 973-977.   
[21] Zhao Jiangfei, Huang Tinglei,Pang Fei,et al.Genetic algorithm based on greedy strategy in the O-1 knapsack problem [C]// Proc of International Conference on Genetic & Evolutionary Computing.2010:105-107.   
[22] Yang Xinshe.A new metaheuristic bat-inspired algorithm [J]. Computer Knowledge & Technology,2010,284: 65-74.   
[23]李枝勇，马良，张惠珍．求解0//1 背包问题的自适应元胞粒子群算法 [J].计算机工程,2014,40(10):198-203.(Li Zhiyong,Ma Liang,Zhang Huizhen.Adaptive cellular particle swarm algorithm for solving 0/1 knapsack problem [J]. Computer Engineering,2014,40 (10): 198-203.)   
[24]吴聪聪，贺毅朝，陈凝瑛，等．求解0-1背包问题的二进制蝙蝠算法[J]. 计算机工程与应用,2015,51(19):71-74.(Wu Congcong,He Yichao,Chen Yiying,et al. Binary bat algorithm for solving 0-1 knapsack problem [J]. Computer Engineering and Application,2015,51(19): 71-74.)