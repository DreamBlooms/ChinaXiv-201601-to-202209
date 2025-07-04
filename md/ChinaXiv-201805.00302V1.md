# 基于MODCPSO算法的三值FPRM电路面积与延时优化

王铭波1，汪鹏君1，符强1²，张会红1(1.宁波大学 信息科学与工程学院，浙江 宁波 31521;2.宁波大学科学技术学院，浙江 宁波 315212)

摘要：针对三值固定RM(fixedpolarityreed-muler，FPRM)逻辑电路面积与延时综合优化问题进行了研究，提出了一种基于竞争行为多目标离散粒子群算法(Multi-Objective Discrete Competitive Particle Swarm Optimization，MODCPSO)的极性搜索方案。首先在MODCPSO算法中，引入竞争行为机制，将种群划分为不同的团队，从各个团队中随机抽取两个粒子进行比较，令较差的粒子向着较好的粒子进行速度和位置的更新。同时引入变异机制，令种群粒子能够跳出局部最优解，继续更新进化。然后，结合三值 FPRM极性转换技术和 MODCPSO 算法搜索电路面积与延时的最佳极性。最后，利用PLA格式的 MCNCBenchmark 电路实现算法测试，并与 DPSO 算法、MODPSO 算法进行了性能对比。实验结果验证了MODCPSO算法的有效性。

关键词：竞争行为机制；多目标离散粒子群算法；三值FPRM电路；极性搜索 中图分类号：TN79 doi: 10.3969/j.issn.1001-3695.2017.07.0709

# Delay and area optimization for ternary FPRM circuits based on MODCPSO algorithm

Wang Mingbo1, Wang Pengjun1, Fu Qiang1,², Zhang Huihongl (1.Dept.ofInformationSience&Engineering,Ningbo UniversityNingbo Zhejiang315211,China;2.CollgeofScience& Technology Ningbo University, Ningbo Zhejiang 315212, China)

Abstract:To solve thearea anddelaysynthesisoptimization problemofternaryFPRMcircuits,this paper proposed a multiobjective discretecompetitive particle swarmoptimization(MODCPSO）.Firstly,the algorithm introduced thecompetition mechanism.Thepopulation was divided intodiferent teams,and two particles wererandomly selected from each team for comparison,sothat thepoorparticlesupdate theirspeedand position towardsthebetterparticles.Meanwhile,theparticles could avoid falling into local minima through mutation mechanism.Secondly,combined with the polarity conversion technique, MODCPSO wouldsearch thebestpolarity fromthe ternaryFPRMcircuits.Finall,the experimentresultofPLAformat MCNC Benchmark circuits shows that the MODCPSO algorithm has good performance in optimization,compared with the other algorithms.

KeyWords:competitive mechanism; multi-objectivediscrete particle swarmoptimization(MODCPSO); termaryFPRMcircuit; polarity search

# 0 引言

Boolean逻辑和RM逻辑是三值逻辑函数的两种主要表现形式。与传统的Boolean逻辑电路相比，基于RM逻辑的电路（如算术逻辑电路、奇偶校验电路等）在面积、功耗、速度和可测性等方面具有明显的优势。其中，三值固定极性是RM逻辑中一种常见的逻辑表达式。 $n$ 变量的RM逻辑函数共有 $3 ^ { n }$ 个三值FPRM表达式，每一种表达式繁简不一，对应电路的面积与延时也不相同。因此，极性对于电路面积与延时等性能指标

具有重要影响[1]。

三值FPRM电路面积与延时最佳极性搜索问题是一个多目标优化问题。目前，国内外相关研究主要通过加权系数法[2.3]将该问题转换为单目标优化问题。但是，加权系数法存在几个问题：a)权重系数无法确定，设置不同的加权系数，最终结果可能不同；b)加权系数法对Pareto前沿曲线的形状较为敏感，较难获取前沿曲线凹区域的最优解；c权重系数的选取需要先验知识，但是这些先验知识往往是未知的。因此，近年来有学者采用多目标优化思想综合优化电路的性能。如文献[4]采用Pareto支配方式对MPRM电路面积和可靠性进行多目标优化。文献[5]提出了一种多目标离散粒子群算法求解大规模FPRM电路面积与延时优化问题。

粒子群算法、遗传算法、免疫算法均是用来解决组合优化问题较为有效的智能算法，被广泛应用于工程问题中[6-8]。其中,粒子群算法相比其他智能算法，具有鲁棒性好、收敛速度快等特点。因此，该算法在解决多目标优化问题中受到了越来越多的关注。但是，由于种群全局最优粒子牵引作用过强，算法容易发生过早收敛现象。于是，国内外学者提出了许多改进方案，并取得一定成果。如文献[9]提出一种多目标量子粒子群算法，采用共享学习机制和双势阱模型避免算法发生过早收敛的现象文献[10]提出了一种分群多目标粒子群算法，采用方向向量法划分子区域，不同子区域采用不同的搜索策略进行寻优操作，保持算法的多样性。

鉴于此，为了弱化种群全局最优粒子的影响，本文提出了一种基于竞争行为的多目标离散粒子群算法，并用该算法求解三值FPRM电路面积与延时最佳极性搜索问题。首先，将电路极性映射为种群粒子；然后结合极性转换算法和面积与延时估算模型搜索三值FPRM电路最佳极性；最后选择多个MCNCBenchmark电路进行测试，验证算法的有效性。

# 1 三值表达式及面积与延时估算模型

# 1.1 三值FPRM表达式

任一 $n$ 变量的三值逻辑函数 $f ( x _ { n } , x _ { n - 1 } , . . . , x _ { 0 } )$ 均有 $3 ^ { n }$ 个固定极性，每个极性对应一种三值FPRM逻辑表达式。极性 $p$ 的三值FPRM表达式为

$$
\begin{array} { r } { { \underset { f } { \overset { \triangledown } { \boldsymbol { p } } } } ( { \boldsymbol { x } } _ { n } , { \boldsymbol { x } } _ { n - 1 } , \cdots , { \boldsymbol { x } } _ { 0 } ) = \underset { i = 0 } { \overset { { \triangledown } { \boldsymbol { 3 } } ^ { n } - 1 } { \boldsymbol { \sum } } } { \boldsymbol { b } } _ { i } \cdot \overset { n - 1 } { \underset { j = 0 } { \overset { { \triangledown } { \boldsymbol { \operatorname { I } } } } { \boldsymbol { \operatorname { I } } } } } { \boldsymbol { \overset { i } { \operatorname { j } } } } } \end{array}
$$

其中： $\oplus \sum$ 为模3加运算； $b _ { i }$ 为与项系数， $b _ { i } \in \{ 0 , 1 , 2 \}$ ； $i$ 为与项序数，用三进制可表示 $( i _ { n } , i _ { n - 1 } , . . . . , i _ { 0 } )$ ; $p$ 为极性，可表示为 $( p _ { n } , p _ { n } .$ $_ { 1 , . . . , p _ { 0 } ) }$ $\prod _ { j = 0 } ^ { n - 1 } \dot { x } _ { j } ^ { i _ { j } }$ $p$ $i$ $\dot { x } _ { j } ^ { i _ { j } }$ 的表示形式，如表1所示。

表1 $\dot { x } _ { j } ^ { i _ { j } }$ 查找表  

<html><body><table><tr><td>Pj</td><td>i</td><td></td><td>pj</td><td>ij</td><td></td><td>Pi</td><td>ij</td><td></td></tr><tr><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>1</td><td>2</td><td>0</td><td>1</td></tr><tr><td>0</td><td>1</td><td>Xj</td><td>1</td><td>1</td><td>x1</td><td>2</td><td>1</td><td>x2</td></tr><tr><td>0</td><td>2</td><td>x</td><td>1</td><td>2</td><td>(x，④1)²</td><td>2</td><td>2</td><td>(x，④2）²</td></tr></table></body></html>

当已知某一极性的三值FPRM表达式时，通过极性转换算法可以获得另一极性表达式。文献[11]提出了一种基于列表技术的极性转换算法，可以实现Boolean最小项与RM逻辑表达式的转换，以及不同极性RM逻辑表达式的转换。

# 1.2面积与延时估算模型

在电路设计中，通常采用门电路单位延时模型来估算电路延时。首先将电路的多输入门分解为二输入模3加门和二输入模3乘门；然后将二输入门数表示电路面积，关键路径的传输延时和表示电路延时。对于一个二输入门 $f$ 的输出延时 $t _ { f }$ 为

$$
t _ { f } ~ = 1 + \operatorname* { m a x } ( t _ { f _ { - } a } , { } ^ { t } { } _ { f _ { - } b } )
$$

其中 $: t f _ { - } a$ 和 $t f _ { - } b$ 为节点 $f$ 二输入门的输入延时。

多输入门的分解方式不同，电路延时也会不同，其中类Huffman算法[12]是获取电路最短延时的常用方法。对于分解后的电路网络，二输入模3加门数为Mod_3A，模3乘门数为Mod_3M，关键路径的二输入门总数为 $n u m ( k e y )$ 。因此，三值FPRM电路的面积与延时模型分别为

$$
a r e a = \mathbf { M o d \_ 3 A } \mathbf { + M o d \_ 3 M }
$$

$$
d e l a y \ = \ \sum _ { f = 1 } ^ { n u m \left( k e y \right) } t _ { f }
$$

# 1.3 多目标优化模型

电路极性决定了电路面积与延时大小，只有获取最佳极性，才能综合优化电路的面积与延时。传统的加权系数法通过设置电路面积与延时的加权系数，将其转换为单目标优化问题搜索最佳极性。但是，电路面积与延时不一定呈现相同的变化趋势。因此，需要采用多目标优化方法综合优化面积与延时，得到目标函数为

$$
\operatorname* { m i n } F ( p ) = \operatorname* { m i n } [ a r e a ( p ) , d e l a y ( p ) ]
$$

其中， $a r e a ( p )$ 和delay $\scriptstyle ( p )$ 分别表示极性 $p$ 对应电路面积和延时。

假设 $p _ { 1 }$ 和 $p _ { 2 }$ 为电路的两个极性，若 $p _ { 1 }$ 占优于 $p _ { 2 }$ ，或者$p _ { 1 }$ 支配 $p _ { 2 }$ ，记做 $p _ { 1 } \succ p _ { 2 }$ 。当且仅当

$$
\left. \begin{array} { c } { { a r e a ( p _ { 1 } ) \leq a r e a ( p _ { 2 } ) } } \\ { { d e l a y ( p _ { 1 } ) \leq d e l a y ( p _ { 2 } ) } } \end{array} \right\}
$$

若极性 $p _ { 1 }$ 不被其他极性支配，则 $p _ { 1 }$ 为满足面积与延时Pareto关系的最佳极性之一，而Pareto最优解集则是所有Pareto最佳极性的集合。

# 2 基于MODCPSO 算法的三值FPRM电路面积与延时优化

# 2.1多目标离散粒子群算法

粒子群算法是一种模拟鸟类捕食行为的群智能算法。在寻优过程中，粒子通过跟踪个体最优粒子 $p _ { i }$ 和全局最优粒子 $p _ { g }$ 改变自身飞行速度和位置，从而达到算法寻优的效果。假设在$D$ 维搜索空间中，第 $i$ 个粒子的速度 $\nu _ { i } { = } ( \nu _ { i 1 } , \nu _ { i 2 } , . . . , \nu _ { i D } )$ ，位置 $\scriptstyle x _ { i } = ( x _ { i 1 } ,$ $x _ { i 2 } , . . . , x _ { i D } )$ ，个体最优粒子 $p _ { i } { = } ( p _ { i 1 } , p _ { i 2 } , . . . , p _ { i D } )$ ，全局最优粒子$p _ { g } { = } ( p _ { g 1 } , p _ { g 2 } , . . . , p _ { g D } ) .$ 。在算法迭代过程中，粒子的速度和位置更新公式如式(7)和(8)所示。

$$
\begin{array} { r } { \nu _ { i d } \left( t + 1 \right) = \omega \nu _ { i d } \left( t \right) + c _ { 1 } r _ { 1 } \left( p _ { i d } \left( t \right) - x _ { i d } \left( t \right) \right) } \\ { + c _ { 2 } r _ { 2 } \left( p _ { g d } \left( t \right) - x _ { i d } \left( t \right) \right) } \end{array}
$$

$$
x _ { i d } \left( t + 1 \right) = r o u n d \left( \frac { M } { 1 + e ^ { - \nu _ { i d } \left( t + 1 \right) } } \right) + \left( M - 1 \right) \cdot k \cdot r _ { 3 } 
$$

其中： $\omega$ 为惯性权重因子； $c _ { 1 }$ 和 $c _ { 2 }$ 为学习因子； $r _ { 1 } , \ r _ { 2 }$ 和 $r _ { 3 }$ 为[0,1]范围的随机数；round $\iota ( x )$ 表示对 $x$ 进行取整操作； $M$ 为 $x _ { i d }$ 取值状态； $k$ 为随机整数。

设置外部档案库用来存放当前迭代获取的Pareto最优解集，并采用轮盘赌的方式从外部档案库中选取全局最优粒子 $p _ { g }$ 。在下一次迭代过程中，将外部档案粒子与种群粒子进行非支配关系比较，更新外部档案。当外部档案中的粒子数超过了档案库规模时，通过删减拥挤度较大粒子来保持外部档案库粒子的均匀分布性。

在多目标离散粒子群(multi-objective discrete particle swarmoptimization,MODPSO)算法中，由于全局最优粒子对种群个体的牵引作用过强，导致算法容易发生过早收敛的现象。因此，为了改善这一问题，引入竞争行为机制，提出了一种基于竞争行为的多目标离散粒子群算法。

# 2.2基于竞争行为机制的多目标离散粒子群算法

在MODPSO算法中，由于每个粒子所受到的牵引作用过于集中，因此导致算法容易陷入局部最优解。图1所示为MODPSO算法搜索多峰函数最小值的动态搜索图。在图1中，无论粒子 $x _ { 1 } ( t )$ 或 $x _ { 2 } ( t )$ 是否在局部最优解的搜索空间范围内，由于全局最优粒子 $p _ { g } ( t )$ 和个体最优粒子 $p 1 ( t ) , ~ p _ { 2 } ( t )$ 的影响，最终将令 $x _ { 1 } ( t )$ 和 $x _ { 2 } ( t )$ 陷入局部最优解，导致种群发生过早收敛的现象。

鉴于此，本文引入竞争行为机制，首先将种群平均划分为两个团队，然后从两个团队中各自随机抽取一个粒子进行比较，令较差粒子 $x _ { l } ( t )$ 向着较好粒子 $x _ { w } ( t )$ 进行速度和位置的更新，如图2 所示。通过两个团队之间信息的相互交流，使得粒子 $x _ { l } ( t )$ 能够跳出局部最优解的搜索空间，有效避免了由于全局最优粒子和个体最优粒子的集中作用而引起种群过早趋同问题。其中，较差粒子 $x _ { l } ( t )$ 的速度更新公式如下所示：

$$
\begin{array} { c } { { \nu _ { l d } \left( t + 1 \right) = \omega \nu _ { l d } \left( t \right) + c _ { 1 } r _ { 1 } \left( x _ { w d } \left( t \right) - x _ { l d } \left( t \right) \right) } } \\ { { { } } } \\ { { { } + c _ { 2 } r _ { 2 } \left( m e a n ( x _ { d } \left( t \right) ) - x _ { l d } \left( t \right) \right) } } \end{array}
$$

其中：vld、 $x _ { l d }$ 为较差粒子速度和位置； $x _ { w d }$ 为较好粒子位置；mean $( x _ { d } )$ 为种群粒子位置的平均值，有利于粒子个体向种群团队获取进化信息。根据式(9)可知，通过不同粒子的比较，较好粒子和种群其他粒子将共同影响较差粒子速度和位置的更新。

为了增强算法的多样性，本文引入了变异机制。由于种群粒子位置采用三进制编码方式，所以在变异过程中，本文采用基因位变异方式。设置变异概率 $\boldsymbol { P _ { m } }$ 和[0\~1]范围的随机数 $c _ { d }$ 若 $c _ { d } \geqslant P _ { m }$ ，对粒子第 $d$ 位进行变异，将原值0变为1，1变为2，2变为0；若否，则对该位不进行变异操作。

![](images/b21ffe51b1f31827fc05a160f8ceaa5d7f3a9ef501739fba365ed78103763eb4.jpg)  
图1MODPSO 算法动态搜索图

![](images/8f9640d3cec2b81c4ff464d0f605bcba87955e6a2ee834d3452532add9fed8ba.jpg)  
图2MODCPSO 算法动态搜索图

# 2.3基于MODCPSO 算法的三值FPRM电路面积与延时最佳极性搜索方案

a)初始化种群粒子和个体最优粒子的速度和位置，并计算每个粒子对应电路的面积和延时；

b)计算种群粒子的非支配关系(rank)，并将存在Pareto非支配关系的粒子放入外部档案库(rep);

c)将种群平均分为两个团队，各从两个团队中随机抽取一个粒子进行比较；

d)若两个粒子存在优劣关系，根据式(8)、(9)更新较差粒子的速度和位置，并计算相应电路面积与延时；若不存在优劣关系，对两个粒子同时进行变异操作，并计算电路面积与延时；

e)重复步骤cd)，直至团体中所有粒子均已完成比较操作；

f)将更新后的种群粒子与rep中的粒子一同计算非支配关系，并更新rep 解集；

g）若rep中的粒子数超过了档案规模，删减拥挤度较大的粒子；

h)重复步骤c)\~g)，直至最大迭代次数，输出rep中粒子的面积与延时。

算法的时间复杂度为 ${ \mathrm { O } } ( N ^ { 2 } )$ ， $N$ 为种群粒子数。

# 3 实验数据与分析

为验证MODCPSO 算法求解三值FPRM电路面积与延时最佳极性搜索问题的有效性，将 MODCPSO 算法与文献[5]的MODPSO算法和文献[12]的离散粒子群算法(DiscreteParticleSwarmOptimization,DPSO)进行性能对比。参数设置如下：DPSO 算法采用加权系数法搜索最优极性，权重系数均为0.5;

MODPSO和MODCPSO算法采用多目标优化方法搜索最优极性解集，外部档案规模为20。其他参数：学习因子 ${ c _ { 1 } } \mathrm { { = } } { c _ { 2 } } \mathrm { { = } } 2 . 0$ 种群规模为40，最大迭代次数为120代，惯性权重 $\omega$ 最大值和最小值分别为0.9、0.4，最大飞行速度为4.0， $k { = } 0 . 2$ ， $\scriptstyle \mathbf { M } = 3$ 。

表2给出了三种算法各自运行MCNCBenchmark电路获取最佳极性的电路面积和延时。其中，“name”和“input”表示电路名称和输入变量数，“area”和“delay”表示三种算法各自运行5次最佳极性电路面积和延时的累加值，“area%"和"delay%”表示面积和延时优化率，计算公式：

<html><body><table><tr><td colspan="2">areal(area2)-area3</td></tr><tr><td>area%=</td><td></td></tr><tr><td></td><td>area3</td></tr></table></body></html>

$$
d e l a y \% = \frac { d e l a y 1 ( d e l a y 2 ) – d e l a y 3 } { d e l a y 3 }
$$

其中：areal(delay1)、area2(delay2)、area3(delay3)表示DPSO、MODPSO和MODCPSO搜索到最佳极性电路面积和延时。

MODPSO与MODCPSO算法采用多目标优化方法搜索最优极性解集，在实验结果比较过程中较难验证算法的优劣性。因此需要对Pareto 解集进行处理，选取一个综合优化电路面积

与延时的极性进行结果对比。本文采用归一化机制，计算Pareto解集中每个极性的fitness，并将fitness最小的极性作为最佳极性进行比较，fitness计算公式如下：

$$
f i t n e s s _ { i } = \frac { a r e a _ { i } } { \underset { i = 1 } { m } } + \frac { d e l a y _ { i } } { \underset { i = 1 } { m } }
$$

其中： $\mathbf { \nabla } _ { m }$ 为Pareto 解集中最优解的个数。

从表2测试结果可以看出，MODCPSO算法与DPSO、MODPSO 算法相比，MODCPSO 算法能搜索到更小面积和更短延时电路的极性。对于newtpla 电路，MODCPSO 算法比其他两种算法面积的优化率分别为 $1 8 . 9 9 \%$ 和 $1 7 . 6 7 \%$ 。虽然在misex1电路测试中，MODCPSO算法搜索的最佳极性电路面积有所增加，但是就整体测试结果而言，MODCPSO 算法比DPSO 和MODPSO算法，面积与延时平均优化率分别为 $6 . 5 7 \%$ 、 $0 . 8 3 \%$ 和 $4 . 5 6 \%$ ， $1 . 1 2 \%$ 。最后，将三种算法5次迭代结果进行方差计算，DPSO算法面积与延时方差分别为33.07和0.22，MODPSO算法的方差分别为26.21和0.15，MODCPSO算法的方差分别为15.20和0.13，表现出了MODCPSO 算法良好的鲁棒性。

表2MODCPSO算法与其他算法最优极性的实验数据和优化率  

<html><body><table><tr><td colspan="2">benchmark</td><td colspan="2">DPSO</td><td colspan="2">MODPSO</td><td colspan="2">MODCPSO</td><td colspan="3">MODCPSO 相对 DPSO 的优化率 MODCPSO 相对 MODPSO 的优化率</td></tr><tr><td>name</td><td>input</td><td>area</td><td>delay</td><td>area</td><td>delay area</td><td>delay</td><td>area %</td><td>delay%</td><td>area %</td><td>delay%</td></tr><tr><td>p82</td><td>5</td><td>183</td><td>38</td><td>175</td><td>40</td><td>175 38</td><td>4.57%</td><td>0.00%</td><td>0.00%</td><td>5.26%</td></tr><tr><td>z4ml</td><td>7</td><td>611</td><td>47</td><td>604</td><td>48 585</td><td>46</td><td>4.44%</td><td>2.17%</td><td>3.25%</td><td>4.35%</td></tr><tr><td>inc</td><td>7</td><td>652</td><td>50</td><td>638</td><td>49 635</td><td>49</td><td>2.68%</td><td>2.04%</td><td>0.47%</td><td>0.00%</td></tr><tr><td>dc2</td><td>8</td><td>320</td><td>45</td><td>321</td><td>45 310</td><td>45</td><td>3.23%</td><td>0.00%</td><td>3.55%</td><td>0.00%</td></tr><tr><td>luc</td><td>8</td><td>242</td><td>40</td><td>245</td><td>42 240</td><td>40</td><td>0.83%</td><td>0.00%</td><td>2.08%</td><td>5.00%</td></tr><tr><td>misex1</td><td>8</td><td>375</td><td>45</td><td>378</td><td>45 390</td><td>45</td><td>-3.85%</td><td>0.00%</td><td>-3.08%</td><td>0.00%</td></tr><tr><td>newcond</td><td>11</td><td>7287</td><td>66</td><td>7584</td><td>65 7202</td><td>65</td><td>1.18%</td><td>1.54%</td><td>5.30%</td><td>0.00%</td></tr><tr><td>t4</td><td>12</td><td>316</td><td>45</td><td>297</td><td>45 275</td><td>45</td><td>14.91%</td><td>0.00%</td><td>8.00%</td><td>0.00%</td></tr><tr><td>br1</td><td>12</td><td>563</td><td>46</td><td>563</td><td>45 515</td><td>45</td><td>9.32%</td><td>2.22%</td><td>9.32%</td><td>0.00%</td></tr><tr><td>table3</td><td>14</td><td>30194</td><td>76</td><td>29544</td><td>75 28147</td><td>75</td><td>7.27%</td><td>1.33%</td><td>4.96%</td><td>0.00%</td></tr><tr><td>dk48</td><td>15</td><td>12800</td><td>71</td><td>12398</td><td>70 11505</td><td>70</td><td>11.26%</td><td>1.43%</td><td>7.76%</td><td>0.00%</td></tr><tr><td>newtpla</td><td>15</td><td>9864</td><td>70</td><td>9755</td><td>70 8290</td><td>70</td><td>18.99%</td><td>0.00%</td><td>17.67%</td><td>0.00%</td></tr><tr><td>cm163a</td><td>16</td><td>1181</td><td>55</td><td>1135</td><td>55</td><td>1135 55</td><td>4.05%</td><td>0.00%</td><td>0.00%</td><td>0.00%</td></tr><tr><td colspan="7">average save%</td><td>6.57%</td><td>0.83%</td><td>4.56%</td><td>1.12%</td></tr></table></body></html>

为了更好地观察MODCPSO算法的搜索性能，将13个测试电路在5次迭代过程中面积与延时的最优解分别进行累加，分析三种算法的进化过程，如图3和4所示。

从图3和4中可以看出，DPSO和MODPSO算法在早期迭代过程中便已经收敛，陷入了局部最优解，但是MODCPSO算法还能继续更新进化。同时，MODCPSO算法比DPSO 和MODPSO算法能搜索到更优的极性，电路面积与延时更小。

# 4 结束语

针对三值FPRM电路面积与延时最佳极性搜索问题，本文提出了一种基于MODCPSO 算法的极性搜索方案：在种群寻优的过程中，采用竞争行为机制，将种群划分为两个团队，令两个团队中的粒子进行比较，较差的粒子向着较好的粒子进行更新操作，避免算法发生过早收敛的现象。同时，引入变异机制令种群粒子能够跳出局部最优解，提高算法的优化性能。最后，通过13个Benchmark电路进行仿真测试，实验结果表明：与DPSO和MODPSO算法搜索到的最优极性相比，MODCPSO算法具有更好的优化效率和鲁棒性。

![](images/b084e99e997dae8c6998c9b9bfa0aaae6dd14350e02079b134c0c430140b0393.jpg)  
图3面积迭代进化曲线

![](images/55d3c9decc33db4f3703131b12ebe7077944c7ebfbdb2abe23b3612f71dd90cf.jpg)  
图4延时迭代进化曲线

# 参考文献：

[1]Vijayakumari C K,Mythili P,James R K,et al.Optimal design of combinational logic circuits using genetic algorithm and reed-muller universal logic modules [C]// Proc of International Conference on Embedded Systems.2014:1-6.   
[2]Wang Pengjun,Li Kangping,Zhang Hhuihong.PMGA and its application in area and power optimization for ternary FPRM circuit [J].Journal of Semiconductors,2016,37(1):126-130.   
[3]马雪娇，厉琼莹，夏银水，等．基于双逻辑门级图形表示的功耗优化技 术[J]．计算机辅助设计与图形学学报,2017,29(3):509-518.   
[4]卜登立，江建慧．基于Pareto支配的MPRM电路面积与可靠性优化[J]. 电子学报,2016,11(11):2653-2659.   
[5] 符强，汪鹏君，童楠，等．基于 MODPSO 算法的 FPRM 电路多约束极 性优化方法[J]．电子与信息学报,2017,39(3):717-723.   
[6]Wang Mingan, Shuo Feng,He Chunhui,et al.An artificial immune system algorithm with social learning and its application in industrial PID controller design[J].Mathematical Problems in Engineering,2017,2017(2017)1-13.   
[7]Ni Qingjian,Pan Qianqian,Du Huimin, etal.A novel cluster head selection algorithm based on fuzzy clustering and particle swarm optimization [J]. IEEE//ACM Trans on Computational Biology and Bioinformatics,2017,14 (1): 76-84.   
[8]Keshanchi B, Souri A, Navimipour N J.An improved genetic algorithm for task scheduling in the cloud environments using the priority queues: formal verification simulation,and statistical testing [J]. Journal of Systems and Software,2017,124 (2): 1-21.   
[9] Xu Suhui,Mu Xiaodong,Dong Chai,et al.Multi-objective quantumbehaved particle swarm optimization algorithm with double-potential well and share-learning [J]. Optik: International Journal for Light and Electron Optics,2016,127 (12): 4921-4927.   
[10] Dai Cai,Wang Yuping,Ye Miao.A new multi-objective particle swarm optimization algorithm based on decomposition [J]. Information Sciences, 2015,325 (2015): 541-557.   
[11] Yu Haizhen,Wang Pengjun, Zhang Yuejun.A ternary polarity conversion technique for fixed polarity Reed-Muller expansions [C]// Procof International Conference on Signal Processing.2016: 1-5.   
[12]王振海，汪鹏君，俞海珍，等．基于PSO算法的FPRM电路延时与面积 优化[J].电路与系统学报,2012,17(5):75-80.