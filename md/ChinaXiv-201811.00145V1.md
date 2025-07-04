# 一种基于单纯形搜索的粒子群优化算法\*

胡锦帆，张晓伟，袁岐江，张为军，程崇东(电子科技大学 数学科学学院，成都 611731)

摘要：为了改善粒子群优化算法的求解性能，提出了一种基于单纯形搜索和粒子群优化的混合算法。该算法一方面自适应地确定惯性权重、认知以及社会参数来达到免参数目的，另一方面利用单纯形搜索来引导部分粒子的搜索方向，从而加速算法收敛。数值实验结果表明，与传统的粒子群算法和其他基于单纯形的粒子群算法相对比，该算法在评估次数、求解精度方面表现良好。

关键词：直接搜索；单纯形搜索；粒子群优化 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.06.0465

# Particle swarm optimization based on simplex search

Hu Jinfan, Zhang Xiaowei†, Yuan Qijiang, Zhang Weijun, Cheng Chongdong (School ofMathematical Sciences,UniversityofElectronic Science&TechnologyofChina,Chengdu6l1731,China)

Abstract: Inorder to improve the performanceofparticle swarmoptimization,thepaper proposedahybrid algorithmbased on simplex search and particle swarmoptimization.Ontheone hand,the algorithmdetermines the inertia weightadaptively, cognitionand socialparametersforthe purposeofavoiding parameters.Ontheotherhand,the simplexsearchisused to guide the direction of several particles,thus the convergenceofthe algorithm isaccelerated.Theresultsof numerical experiments showthat the proposed algorithmhas better performance than thecompared algorithms in terms offunction evaluations and accuracy.

Keywords:direct search; simplex search; particle swarm optimization

# 0 引言

粒子群算法是由Kennedy和Eberhart于1995年提出，它通过模拟鸟群觅食过程中的迁徙和群聚行为来寻找全局最优解[1-3]。1998年 Shi等人引入了惯性权重机制，使得粒子群算法的性能得到进一步改善[4-8]。与传统优化方法相比，粒子群算法具有如下优点：不需要目标函数导数等解析信息，具有很好的通用性；不易陷入局部最优，具有较强的鲁棒性；流程简单，易于实现。然而，粒子群算法的启发式机制往往使得算法易于早熟，而且对于特定问题，算法性能过多依赖于对参数的设定。如今许多改进算法也未能很好解决参数设置过多，且参数设置依靠经验[9,10]，而对于简洁的无参数改进算法而言，算法易早熟收敛[1]。单纯形搜索能够利用问题本身较弱的解析性质，理论基础丰富，搜索具有针对性，收敛速度较快，并且和粒子群优化有着天然的共性，便于取长补短。考虑到这两个算法的特点，出现了许多基于单纯形的粒子群算法[12-14]。

近年来，有许多基于单纯形搜索的粒子群优化算法研究成果，并在工程领域到广泛应用[15\~19]。2007年，Fan 和 Zahira 提出了一种求解无约束优化问题的混合算法，该算法将单纯形搜索与粒子群算法相结合，以提高粒子群优化的收敛速率，其采用的算法结构为后续算法设计提供了思路，但该算法参数设置较多，且对较高维数的优化测试函数的求解性能有待进一步提高[16]。2008年，Hsu 和Gao 在粒子群优化中嵌入了单纯形搜索机制，该机制每隔 $k$ 次粒子群优化算法迭代便执行1次单纯形搜索，从而不但可以减少函数评估次数，而且较好地平衡了搜索和探索之间的矛盾，但是数值实验部分几乎只评估了2-5维优化函数的求解性能[17]。2010年，任小康等人提出了一种基于单纯形法的量子粒子群优化算法，该算法先用量子粒子群算法进行全局搜索，然后依据种群适应度标准差确定是否利用单纯形法进行局部搜索[18]，但是如何根据种群适应度标准差判断种群是否陷入“早熟”是个困难的事情，从而限制了算法的进一步推广。2018年，武可栋等人在粒子群优化算法的初始化过程中加入了单纯形搜索，利用单纯形法对初始值进行预处理[19],并针对20个10维测试函数进行了数值模拟，实验结果表明其相比标准粒子群优化算法具有更高的求解精度，但是该算法存在参数设置困难，评估次数较多的缺点。

为了改善粒子群优化算法的求解性能，本文提出了一种基于单纯形搜索的粒子群优化算法，该方法一方面利用类电磁机制原理[12]自适应地确定惯性权重、认知以及社会参数来达到免参目的，另一方面利用单纯形搜索来干预每次搜索方向及步长，从而加速算法收敛。

# 1 粒子群算法

粒子群算法（particle swarm optimization，PSO）的思想来源于对鸟群飞行或觅食过程中的迁徙和群集行为[1\~3,13,14]。鸟仅仅是追踪它有限数量的邻居，但最终的整体结果是整个鸟群好像在一个中心的控制之下，即复杂的全局行为是由简单规则的相互作用引起的。不同于达尔文“适者生存，优胜劣汰”进化思想，粒子群优化算法是通过个体之间的协作来寻找最优解。

PSO 算法描述如下：

a)初始化种群 $P ( t )$ ，速度 $V ( t )$ ，认知系数 $\scriptstyle { c _ { 1 } }$ ，社会系数 $c _ { 2 }$ 惯性权重 $w$ ，令 $t = 0$ ：

b)计算每一个粒子 $X _ { i } \in P ( t )$ 的适应值，个体经历最优位置（204号 $g _ { i } \left( t \right)$ ，种群全局最优位置 $G ( t )$ ：

c)更新每一个粒子 $X _ { i } \in P ( t )$ 的速度 $V _ { i , j } \left( t + 1 \right)$ 和位置$X _ { i } \left( t + 1 \right)$ ：

for $X _ { i } ( t ) \in P ( t )$

for （204 $j = 1$ to $n$

$$
\begin{array} { r l } & { V _ { i , j } ( t + 1 ) = w \cdot V _ { i , j } ( t ) } \\ { } & { + c _ { 1 } \cdot r a n d \cdot \big ( g _ { i , j } ( t ) - X _ { i , j } ( t ) \big ) } \\ { } & { + c _ { 2 } \cdot r a n d \cdot \big ( G _ { j } ( t ) - X _ { i , j } ( t ) \big ) } \end{array}
$$

end

$$
X _ { i } ( t + 1 ) = X _ { i } ( t ) + V _ { i } ( t + 1 )
$$

end

d)若满足终止条件，停机；否则， $t = t + 1$ ，转b)。

这里， $V _ { i , j } ( t )$ 表示 $V _ { i } ( t )$ 的第 $j$ 个分量， $X _ { i , j } ( t )$ 表示 $X _ { i } ( t )$ 的第 $j$ 个分量， $\mathbf { \Omega } _ { n }$ 表示维数，即分量个数； $\scriptstyle { c _ { 1 } }$ 和 $c _ { 2 }$ 是两个正常数； $w$ 是惯性权重，rand 是一个(0,1)之间的随机数。

在步骤c)中，式（1）说明粒子的速度取决于上次的速度更新，它自己所到达的历史最佳位置和全种群中所有粒子的历史最佳位置;式(2)表明每个粒子的位置在搜索域中的更新方式。

# 2 单纯形搜索

单纯形（simplex）是代数拓扑中的基本概念，是三角形和四面体的一种泛化。 $n$ 维单纯形是一个由 $^ { n + 1 }$ 个点组成的凸包。例如：1维单纯形就是线段；2维单纯形就是三角形；3维单纯形就是一个四面体。

单纯形搜索（Nelder-mead simplex search，简称NM）[20]通过反射、扩展、压缩等一系列初等几何变换操作来寻求问题的最优解。每次变换后，试图用一个更好的顶点替换当前已知最

差点。

以最优化问题 $\operatorname* { m i n } _ { X \in R ^ { 2 } } f ( X )$ 为例,分别计算3个顶点 $X _ { \mathit { h i g h } }$ ，$X _ { s e c }$ ， $X _ { l o w }$ 的函数值 $f _ { h i g h } \mathrm { ~ , ~ } f _ { \mathrm { s e c } } \mathrm { ~ , ~ } f _ { l o w }$ 。不妨假设， $f _ { h i g h } > f _ { \mathrm { s e c } } > f _ { l o w }$ 。基本操作(图1\~4)如下：

a）反射。取 $X _ { \mathit { l o w } }$ 和 $X _ { s e c }$ 的中点 $X _ { c e n t }$ ，计算反射点$X _ { _ { r e f } } = X _ { _ { c e n t } } + \left( X _ { _ { c e n t } } - X _ { _ { h i g h } } \right) \circ$ （204

b）扩展。若 $f _ { l o w } > f _ { r e f }$ ，则计算扩展点 $X _ { e x p } = X _ { c e n t } + 2 ^ { * } \big ( X _ { r e f } - X _ { c e n t } \big ) \ \circ$

c）压缩。(a)若 $f _ { h i g h } > f _ { r e f } \geq f _ { s e c }$ ，计算向外压缩点$X _ { c o n t } = X _ { c e n t } + 0 . 5 * \left( X _ { r e f } - X _ { c e n t } \right)$

若 $f _ { r e f } > f _ { c o n t }$ ，用 $X _ { c o n t }$ 取代 $X _ { \mathit { h i g h } }$ ；

(b）若 $f _ { r e f } \geq f _ { h i g h }$ ，计算向内压缩点$X _ { c o n t } = X _ { c e n t } + 0 . 5 * \left( X _ { h i g h } - X _ { c e n t } \right)$

若 $f _ { h i g h } > f _ { c o n t }$ ，用 $X _ { c o n t }$ 取代 $X _ { \mathit { h i g h } }$ 。

d)收缩。若 $f _ { _ { c o n t } } ~ > ~ f _ { _ { h i g h } }$ ，则向最好点 $X _ { l o w }$ 收缩其余顶点, 即对 $\begin{array} { r } { \forall i } \end{array} , \quad i \neq l o w , X _ { i } = 0 . 5 ^ { * } \big ( X _ { i } + X _ { l o w } \big ) \ \mathrm { ~ o ~ }$ （20

![](images/e995ac8e464aa3944d2ac1adc739b9129a3629fe698b72cd044e020f1756db1d.jpg)  
图1反射操作

![](images/592b6cca4b29c91d84f9ead35b683e3677deb67915ce3fb03d0024045b79fc8c.jpg)  
图2扩展操作

Fig.2Expansion

![](images/247fa28c2efe2d21c709ff45e58d6cfcee97d2227f7d989dc44a571b3a11bf48.jpg)  
Fig.1 Reflection

![](images/193e31f46c002bedbb778ebcf3fa65bcf018428cf66f45e830bab9d538d2f650.jpg)  
图3压缩操作  
Fig.3 Contraction

# 图4收缩操作

Fig.4 Shrink

NM算法描述如下：

a)计算 $n$ 维单纯形的 $n { + } 1$ 顶点 $X _ { i }$ 的函数值 $f _ { i } \mid = 1 , \cdots , n$ ，选取最差解 $X _ { \mathit { h i g h } }$ ，次差解 $X _ { s e c }$ ，最好解 $X _ { l o w }$ ，中点$X _ { _ { c e n t } } = 0 . 5 ^ { * } ( X _ { _ { l o w } } + X _ { _ { s e c } } )$ ，及其对应函数值为 $f _ { h i g h } , f _ { s e c } , f _ { l o w }$ ，fcent

b)计算反射点 $X _ { \it { r e f } } = X _ { \it { c e n t } } + \left( X _ { \it { c e n t } } - X _ { \it { h i g h } } \right)$ 以及对应函数值为fref°

c)进行单纯形变换：

if $\begin{array} { l l } { f _ { r e f } } & { > } & { f _ { l o w } } \end{array}$ （204号if $f _ { r e f } \geq f _ { \mathrm { s e c } }$ （204号

计算压缩点 $X _ { c o n t } = X _ { c e n t } + 0 . 5 ^ { * } ( X _ { h i g h } - X _ { c e n t } )$ （204号

如果 $f _ { c o n t } < f _ { h i g h }$ ，则 $X _ { \mathit { \Pi } _ { h i g h } } = X _ { \mathit { \Pi } _ { c o n t } }$ ；否则向 $X _ { l o w }$ 进行收缩操作。

elseif $f _ { h i g h } > f _ { r e f } \geq f _ { s e c }$

$$
X _ { c o n t } = X _ { c e n t } + 0 . 5 * \big ( X _ { r e f } - X _ { c e n t } \big )
$$

如果 $f _ { c o n t } < f _ { h i g h }$ ，则 $X _ { \mathit { \Pi } _ { h i g h } } = X _ { \mathit { \Pi } _ { c o n t } }$ ；否则向 $X _ { l o w }$ 进行收缩操作。

end

$$
X _ { h i g h } = X _ { r e f }
$$

else

计算扩展点 $X _ { \mathrm { e x p } } = X _ { \mathrm { c e n t } } + 2 ^ { * } \big ( X _ { r e f } - X _ { c e n t } \big )$ ，如果 $f _ { e x p } <$ $f _ { r e f l }$ ，则 $X _ { \mathit { h i g h } } = X _ { \mathit { e x p } }$ ；否则， $X _ { h i g h } = X _ { r e f }$ 。

end

通过步骤c)的操作，新单纯形的 $n + 1$ 个顶点中至少存在一个顶点进行了改变。

# 3 基于单纯形搜索的粒子群优化算法

# 3.1PSO 算法改进

在传统粒子群优化中，第 $i$ 个粒子的位置更新基于三个因素，见式（1）（2)。然而，在基于单纯形搜索的粒子群优化算法（Nelder-mead simplex particle swarm optimization，NM-PSO)中，对于第 $t$ 代种群 $P ( t )$ 中第 $i$ 个粒子 $X _ { i } ( t )$ ，通过式（3）\~（5）更新：

$$
V _ { i } = F _ { 0 } + F _ { 1 } + F _ { 2 }
$$

$$
\begin{array} { r } { T _ { i } ( t ) = X _ { r 3 } ( t ) + V _ { i } } \end{array}
$$

$$
X _ { i } ( t + 1 ) = T _ { i } ( t ) \quad { \mathrm { ~ i f ~ } } \ f \left( T _ { i } ( t ) \right) < f _ { i } ( t )
$$

这里:

$$
\begin{array} { r l } & { F _ { 0 } = \big ( X _ { r 1 } ( t ) - X _ { r 3 } ( t ) \big ) ^ { * } \big [ f ( X _ { r 3 } ( t ) ) - f \big ( X _ { r 1 } ( t ) \big ) \big ] / D } \\ & { F _ { 1 } = \big ( g _ { r 2 } ( t ) - X _ { r 3 } ( t ) \big ) ^ { * } \big [ f \big ( X _ { r 3 } ( t ) \big ) - f \big ( g _ { r 2 } ( t ) \big ) \big ] / D } \\ & { F _ { 2 } = \big ( G ( t ) - X _ { r 3 } ( t ) \big ) ^ { * } \big [ f \big ( X _ { r 3 } ( t ) \big ) - f \big ( G ( t ) \big ) \big ] / D } \end{array}
$$

$$
D = f _ { \mathit { h i g h } } - f _ { \mathit { l o w } }
$$

参考点 $X _ { r 1 } ( t ) \ , \ X _ { r 2 } ( t )$ ，基点 $X _ { r 3 } ( t )$ 为任意选取的其他三个不同的粒子，即i≠rl≠r2≠r3。

式（5）采用了贪婪选择机制更新粒子 $X _ { i } ( t )$ ，即，仅仅当候选粒子 $T _ { i } ( t )$ 的评估值 $f \left( T _ { i } ( t ) \right)$ 小于粒子 $X _ { r 3 } ( t )$ 的评估值 $f _ { i } ( t )$ 时，用候选粒子替换掉 $X _ { i } \left( t \right)$ 。式（4）是利用基点 $X _ { r 3 } ( t )$ 以及其与参考点之间的信息共享来构造候选粒子 $T _ { i } ( t )$ 。

$F _ { 0 }$ 记录了参考点 $X _ { r 1 } ( t )$ 与基点 $X _ { r 3 } ( t )$ 之间的交流信息。当$f _ { r 1 } ( t ) < f _ { r 3 } ( t )$ 时， $S _ { 0 } \triangleq \big [ f ( X _ { r 3 } ( t ) ) - f \left( X _ { r 1 } ( t ) \right) \big ] / D > 0 \ , F _ { 0 }$ 将引导$X _ { r 3 } ( t )$ 向 $X _ { r 1 } ( t )$ 方向搜索，而且，评估值差异越大，在方向$\left( X _ { r 1 } ( t ) - X _ { r 3 } ( t ) \right)$ 上搜索步长 $S _ { 0 }$ 就越多，反之，差异越小， $S _ { 0 }$ 就越多；当 $f _ { r 1 } ( t ) \geq f _ { r 3 } ( t )$ 时， $S _ { 0 } < 0 \ , \ F _ { 0 }$ 将引导 $X _ { r 3 } ( t )$ 在其邻域内搜索，这时搜索步长 $S _ { 0 }$ 刻画了邻域的大小，而且，评估值差异越大，邻域 $S _ { 0 }$ 就越小，反之，差异越小，邻域就越大。因此，通过这种方式，一方面可以很好地平衡局部搜索和全局探索之间的矛盾，另一方面算法自适应地在加速收敛和提高种群多样性之间转换。

同样的处理思路， $F _ { 1 }$ 记录了参考点 $X _ { r 2 } ( t )$ 的个体经历最优gr2(t)与基点Xr3(t)之间的信息。

因为必有 $f _ { l o w } ( t ) \leq f _ { r 3 } ( t )$ ，所以 $F _ { 2 }$ 引导基点 $X _ { r 3 } ( t )$ 向种群全局最优 $G ( t )$ 方向搜索。

这种引入两个粒子间的信息交流机制类似于电磁机制。把每个粒子都当作一个点电荷，函数值越好（小）点电荷电量越高，对其他粒子的吸引力越强。一个粒子的下一步搜索方向是其他粒子对它施加的“合力”，因此这种机制不仅仅有利于改善算法性能[12.21]，而且能够达到免参数目的。

# 3.2算法描述

a)初始化种群，种群规模 $\scriptstyle \mathrm { P O P } = 3 n + 1$ ，变异系数 $\mathrm { C r } { = } 0 . 1$ ，（204号 $t = 0$ ：

b)排序。计算函数值 $f _ { i } ( t )$ ，并按照函数值从小到大进行排序；

c)单纯形搜索。将前 $n { + } 1$ 个最好的粒子作为单纯形顶点，执行NM算法，改进 $\mathtt { n } { + } 1$ 个顶点中最差粒子；

d)粒子群优化。以剩余的 $2 n$ 个粒子构成粒子种群 $P ( t )$ ，对每一个粒子 $X _ { i } ( t ) \in P ( t )$ ，

(a)按照式（4）计算候选粒子 $T _ { i } \left( t \right) = X _ { r 3 } \left( t \right) + F _ { 0 } + F _ { 1 } + F _ { 2 }$ ：

(b)边界检查。对 $\forall j$ ，如果 ${ T _ { i , j } } ( t ) < L B$ ，则 $T _ { i , j } ( t ) = L B$ ；如果 $T _ { i , j } ( t ) > U B$ ，则 $T _ { i , j } ( t ) = U B$ ；

(c)贪婪选择。如果 $f \left( T _ { i } ( t ) \right) ~ < ~ f _ { i } ( t )$ ，则 $X _ { i } \left( t + 1 \right) = T _ { i } \left( t \right)$ ，否则 $X _ { i } \left( t + 1 \right) = X _ { i } \left( t \right)$ ；

(d)变异。对 $\forall j$ ，如果rand $> \mathrm { C r }$ ，则 $X _ { i , j } ( t + 1 ) = X _ { i , j } ( t )$ ：

e)如果满足终止条件，则停机；否则， $t = t + 1$ ，转步骤b)。

为了增加种群的多样性，避免算法过早陷入局部最优，在步骤c中，NM算法只执行一步迭代，步骤d)中，增加了变异操作。

# 4 数值实验

# 4.1对照算法介绍

本文将比较包括本文算法在内的五个算法的数值实验结果。首先介绍其他四种对照算法。

1）惯性权重递减粒子群算法（degressive inertiaweight particle swarm optimization，DPSO)

在标准粒子群算法中，惯性权重 $w$ 对 $V _ { i , j } \left( t \right)$ ，即该粒子上次速度更新的影响力相比另外两个分量占据主要位置，所以，当 $w$ 值较大时， $V _ { i , j } \left( t \right)$ 的范数较大，每次迭代粒子的“前进距离”较长，有利于全局搜索以找到最优解所在的邻域。反之，当 $w$ 较小时，三个分量对迭代方向影响力相近，使算法在一个相对较小的区域内能够更精确地搜索，即加强了局部搜索的能力[5]。因此，如果使惯性权重 $w$ 能够随迭代次数递减，则算法在运行前期全局搜索能力加强，在运行后期局部搜索能力加强，能够使算法整体性能提高。惯性权重 $w$ 的递减公式如下：

$$
w = w _ { m a x } - \left( \frac { i t e r } { i t e r _ { m a x } } \right) \times \left( w _ { m a x } - w _ { m i n } \right)
$$

其中: $w _ { m a x }$ ， $w _ { m i n }$ 分别为设定的 $w$ 的最大值和最小值，Shi 等人推荐这两个参数的值分别为1.4 和 $0 ^ { [ 7 ] }$ ，iter， $i t e r _ { m a x }$ 分别为当前迭代次数和最大迭代次数。

![](images/debf9379197a6596e68253307beb589d3ec0ff02eda97568ef8451c537bd77fd.jpg)  
图5NM-PSO流程图  
Fig.5FlowchartofNM-PSO

采用此算法作为比较算法之一的原因是，此算法也采用自适应参数的机制，只是这个自适应机制较为简单，NM-PSO的自适应机制较为复杂，经过对比能够显现出算法在使用自适应参数机制由简单到精密的性能提升。

2）随机惯性权重粒子群算法（random inertia weight particleswarm optimization，RPSO）

RPSO 是将PSO 中的惯性权重 $w$ 改为[0.5,1]中的均匀分布随机数，即 $w =$ rand（0.5,1）[5]。其余步骤均与PSO保持一致。

3）混合单纯形粒子群算法[16]（hybrid simplex particle swarmoptimization，HSPSO)

HSPSO算法在每一次迭代中，一方面利用单纯形法对最好的前 $\mathbf { N } { + } \mathbf { l }$ 个粒子进行更新，另一方面利用粒子群优化算法对剩余的2N 粒子进行改进。在单纯形法每一次执行中，只需迭代一次，便用新的粒子替换原单纯形的最差顶点，这样不仅可以大大降低算法的计算复杂度，而且有效地保持了算法的求解性能[16]。

4）单纯形粒子群算法[19]（simplex method particle swarm optimization，SMPSO)

在粒子群优化算法产生随机初始值后，使用单纯形法对初始值进行处理，使用处理后的初始值进行粒子群优化算法的后续步骤。经过单纯形法处理后的初始值如果已经接近全局最优解，则经过粒子群算法的迭代会很快收敛到全局最优解，即使处理后的初始值陷入了局部最优解，粒子群算法也会有很大的概率使得结果跳出局部最优解。这种处理方法可以有效发挥这两种算法的各自优势[19]。

# 4.2数值实验数据

五种算法分别对10个30维测试函数（见附录）独立进行50次数值实验，数值结果见表1-4，图4.2.1-10，各算法的参数设置如下：

1）DPSOPOP=3\*30+1，C1=c2=1.494， Wmax $w _ { \mathrm { m a x } } = 1 . 4$ ， ${  { w _ { m i n } } } ^ { = }$ （202）RPSOPO $\scriptstyle \mathrm { P = } 3 ^ { * } 3 0 + 1$ ， $c _ { 1 } { = } c _ { 2 } { = } 1 . 4 9 4$ ， $w =$ rand(0.5,1)3）HSPSO[16]I $\scriptstyle \mathtt { O P } = 3 ^ { * } 3 0 + 1$ ， $c _ { 1 } { = } 0 . 6$ ， $c _ { 2 } { = } 1 . 6$ ， $w =$ rand(0.5,1),变异系数lambda $_ { . = 0 . 8 5 }$ 反射系数 $\mathrm { { r = } } 1 . 7 5$ 扩展系数 $\mathrm { e } { = } 2 . 7 5$ 压缩系数 $\mathrm { c } { = } 0 . 7 5$ 4）SMPSO[19]PO $\mathrm { P } { = } 3 { \ast } 3 0 { + } 1$ ， $_ { c 1 } { = } 1 . 5$ ， $c _ { 2 } { = } 2 . 5$ ， $w { = } i$ rand(0.5,1)

表1\~3分别记录了每个算法50次运行的最好解、最差解、平均值与理论准确解之间的误差；表4记录了每个算法50 次运行结果的方差。图6-15反映了50次运行结果的平均值随评价次数变化的情况。为了图形对比明显，对纵坐标取对数变换。

表1最好解与准确解的误差  
Table 1 Error between the best solution and the exact solution   

<html><body><table><tr><td>函数名</td><td>DPSO</td><td>HSPSO</td><td>NM-PSO</td><td>RPSO</td><td>SMPSO</td></tr><tr><td>Ackley</td><td>1.80E-12</td><td>1.82E-07</td><td>2.52E-09</td><td>1.31E-05</td><td>1.8E-06</td></tr><tr><td>Sphere</td><td>6.72E-20</td><td>1.74E-10</td><td>2.36E-13</td><td>3.46E-07</td><td>1.17E-09</td></tr><tr><td>Rosenbrock</td><td>0.591478</td><td>7.632082</td><td>10.0137</td><td>4.090019</td><td>4.31444</td></tr><tr><td>Rastrigin</td><td>25.86892</td><td>14.00768</td><td>4.72E-12</td><td>18.9097</td><td>8.954632</td></tr><tr><td>Griewank</td><td>6.51E-14</td><td>3.52E-07</td><td>5.7E-08</td><td>0.000207</td><td>1.47E-06</td></tr><tr><td>Styblinski-tang</td><td>28.27347</td><td>70.68362</td><td>2.89E-05</td><td>0.7069</td><td>18.24352</td></tr><tr><td>Levy</td><td>8.34E-15</td><td>4.01E-09</td><td>1.09E-11</td><td>1.83E-05</td><td>1.21E-08</td></tr></table></body></html>

<html><body><table><tr><td>Exponential</td><td>3.33E-16</td><td>0</td><td>1.11E-16</td><td>8.43E-14</td><td>5.55E-16</td></tr><tr><td>Zakharov</td><td>2.47734</td><td>0.00044</td><td>0.412443</td><td>49.60656</td><td>5.132545</td></tr><tr><td>Schwefel 2.22</td><td>8.42E-05</td><td>1.41E-05</td><td>3.55E-08</td><td>4.03E-05</td><td>4.93E-07</td></tr></table></body></html>

![](images/a991180e5aed969c7a35d2a36410c5727a9a439c4e474259f683c3210401b936.jpg)  
图6Ackley函数平均值随评估次数的变化

Table2 Error between the worst solution and the exact solutior   
表3平均解与准确解的误差  

<html><body><table><tr><td>函数名</td><td>DPSO</td><td>HSPSO</td><td>NM-PSO</td><td>RPSO</td><td>SMPSO</td></tr><tr><td>Ackley</td><td>3.734012</td><td>1.98E-06</td><td>4.11E-08</td><td>0.003062</td><td>0.00088</td></tr><tr><td>Sphere</td><td>6.95E-13</td><td>1.06E-08</td><td>1.36E-11</td><td>4.3E-05</td><td>1.79E-06</td></tr><tr><td>Rosenbrock</td><td>323.1116</td><td>3.03E+03</td><td>134.3423</td><td>530.7808</td><td>118.3099</td></tr><tr><td>Rastrigin</td><td>94.52081</td><td>85.56606</td><td>3.054697</td><td>77.60666</td><td>39.79833</td></tr><tr><td>Griewank</td><td>0.08128</td><td>0.071211</td><td>0.021834</td><td>0.056881</td><td>0.061479</td></tr><tr><td>Styblinski-tang</td><td>226.1875</td><td>240.3243</td><td>14.13675</td><td>169.8959</td><td>169.6432</td></tr><tr><td>Levy</td><td>6.522771</td><td>6.546213</td><td>1.35E-09</td><td>4.365262</td><td>0.003875</td></tr><tr><td>Exponential</td><td>9.33E-15</td><td>4.33E-15</td><td>4.44E-16</td><td>2.65E-11</td><td>1.39E-13</td></tr><tr><td>Zakharov</td><td>95.01998</td><td>126.6204</td><td>13.16558</td><td>1118.755</td><td>96.28544</td></tr><tr><td>Schwefel2.22</td><td>0.097455</td><td>6.327632</td><td>1.51E-07</td><td>0.002097</td><td>1.14E-05</td></tr></table></body></html>

![](images/ee32cb33b6c61f270fd58ac02b576bfb071f1e2e51af56e6a5ad6a2b19cfcdf3.jpg)  
Fig.6Variations of mean valueswith evaluations forAckley function

表2最差解与准确解的误差  

<html><body><table><tr><td>函数名</td><td>DPSO</td><td>HSPSO</td><td>NM-PSO</td><td>RPSO</td><td>SMPSO</td></tr><tr><td>Ackley</td><td>0.95083</td><td>6.13E-07</td><td>1.03E-08</td><td>0.000165</td><td>5.63E-05</td></tr><tr><td>Sphere</td><td>2.13E-14</td><td>3.1E-09</td><td>2.02E-12</td><td>6.98E-06</td><td>2.19E-07</td></tr><tr><td>Rosenbrock</td><td>57.4121</td><td>231.3918</td><td>59.97354</td><td>64.70934</td><td>41.96105</td></tr><tr><td>Rastrigin</td><td>55.61811</td><td>44.35636</td><td>0.590349</td><td>41.96631</td><td>17.85171</td></tr><tr><td>Griewank</td><td>0.015881</td><td>0.015977</td><td>0.000619</td><td>0.012978</td><td>0.013808</td></tr><tr><td>Styblinski-tang</td><td>138.5399</td><td>142.4982</td><td>0.346304</td><td>90.87972</td><td>77.35274</td></tr><tr><td>Levy</td><td>2.085249</td><td>1.308247</td><td>2.15E-10</td><td>0.413019</td><td>7.97E-05</td></tr><tr><td>Exponential</td><td>1.31E-15</td><td>3.82E-16</td><td>1.18E-16</td><td>2.8E-12</td><td>2.7E-14</td></tr><tr><td>Zakharov</td><td>17.26885</td><td>26.82361</td><td>4.285058</td><td>402.4986</td><td>34.16138</td></tr><tr><td>Schwefel2.22</td><td>0.009718</td><td>0.126662</td><td>8.22E-08</td><td>0.000425</td><td>2.73E-06</td></tr></table></body></html>

表4数值解的方差

![](images/9058471e3c981c7cdc5201dbe149ff1f7b42383d45b8d165a8de2c8e4b5f024f.jpg)  
Fig.7Variations of mean values with evaluations for Sphere function   
图8Rosenbrock函数平均值随评估次数的变化

Table 3Error between the mean solution and the exact solutior   
Table 4Variance of the solution   

<html><body><table><tr><td>函数名</td><td>DPSO</td><td>HSPSO</td><td>NM-PSO</td><td>RPSO</td><td>SMPSO</td></tr><tr><td>Ackley</td><td>0.808365</td><td>1.34E-13</td><td>6.14E-17</td><td>1.86E-07</td><td>2.09E-08</td></tr><tr><td>Sphere</td><td>9.93E-27</td><td>5.46E-18</td><td>5.21E-24</td><td>8.76E-11</td><td>1.81E-13</td></tr><tr><td>Rosenbrock</td><td>4878.856</td><td>5.21E+05</td><td>1000.014</td><td>7922.594</td><td>796.9568</td></tr><tr><td>Rastrigin</td><td>203.6541</td><td>373.4897</td><td>0.651505</td><td>173.3405</td><td>34.57248</td></tr><tr><td>Griewank</td><td>0.00038</td><td>0.000301</td><td>9.68E-06</td><td>0.000178</td><td>0.000284</td></tr><tr><td>Styblinski-tang</td><td>1631.403</td><td>1426.172</td><td>4.162142</td><td>1175.893</td><td>997.812</td></tr><tr><td>Levy</td><td>2.415501</td><td>1.831068</td><td>9.04E-20</td><td>0.545345</td><td>3E-07</td></tr><tr><td>Exponential</td><td>1.96E-30</td><td>4E-31</td><td>2.22E-33</td><td>2.22E-23</td><td>1.07E-27</td></tr><tr><td>Zakharov</td><td>378.6455</td><td>1181.804</td><td>8.551882</td><td>62813.37</td><td>480.7299</td></tr><tr><td>Schwefel 2.22</td><td>0.00041</td><td>0.80075</td><td>8.06E-16</td><td>2.33E-07</td><td>4.82E-12</td></tr></table></body></html>

![](images/d8f495c05129af3972de008e12e268c39417a058c909b602a62e823fbf3f5699.jpg)  
图7Sphere 函数平均值随评估次数的变化  
Fig.8Variations of mean values with evaluations for Rosenbrock   
图9Rastrigin 函数平均值随评估次数的变化  
Fig.9Variations of mean values with evaluations forRastrigin function

![](images/54e1f3e256bbc209d25af3d34808c5bbaf12372157d65a033873b0a610bcbc86.jpg)  
图10Griewank 函数平均值随评估次数的变化

![](images/ddd260d591b780c52ad2fe1fd62f0286463d02e0b7ed1049092d9868fd938575.jpg)  
Fig.10Variations of mean values with evaluations for Griewank function

![](images/8626cd1c0b4cf695c6d04b2ba74366172d743cd57adad54a6c3a68529bbec537.jpg)  
图11Styblinski-Tang 函数平均值随评估次数的变化  
图12Levy函数平均值随评估次数的变化

![](images/8abbdd9b2daa95764602b7007b6e0fb8d03d0824560054c8975e813c614c5a7e.jpg)  
Fig.11Variations of mean values with evaluations for Styblinski-Tan   
Fig.12Variations of mean values with evaluations forLevy function   
图13Exponential函数平均值随评估次数的变化  
Fig.13Variations of mean values with evaluations forExponential

![](images/288bcd54cf5d19f2717810338241f97fbf92efcccfff9cc7641e5b81778b410b.jpg)  
图14Zakharov 函数平均值随评估次数的变化

![](images/cc6cf8ba9de8a84e435f0f218162db23c7ff6e068bc1dad8f992f09d5864f973.jpg)  
Fig.14Variations of mean values with evaluations for Zakharov function   
图15Schwefel2.22函数平均值随评估次数的变化  
Fig.15Variations of mean values with evaluations for Schwefel 2.22

function

# 4.3 数值实验分析

# 4.3.1表格数据分析

观察表4，NM-PSO在计算数值结果的方差上明显优于其他算法，仅对测试函数 sphere上方差略大于DPSO，表明NM-PSO 在运行的稳定性和结果的稳定性上明显高于其他算法。观察表3，NM-PSO在运算结果的平均误差方面也处于总体领先，对大部分测试函数，NM-PSO领先其他算法多个数量级，仅对测试函数rosenbrock运算的平均值与其他算法差距不大，说明NM-PSO对运算结果的平均误差优于其他算法，算法的稳定性强，结果也更精确。对表1和2,对测试函数Rastrigin、Styblinski-Tang、Exponential 和 schwefel2.22，NM-PSO 的计算结果优于其他所有算法，但对测试函数Rosenbrock，NM-PSO表现不佳，这可能是因为测试函数具有某些特殊的性质，观察表2可以得出在8个测试函数的最差解结果中，本文算法都处于领先地位，特别在Rastrigin、Styblinski-Tang、Levy、Exponential、Zakharov、Schwefel2.22上领先了1个数量级及以上，尤其levy函数达到了9个数量级，体现NM-PSO跳出局部最优的能力，可以看出本算法的稳定性是远远好于其他算法的。对表格的分析总体表明，NM-PSO在绝大多数测试函数下性能表现最佳，即使对表现不佳的测试函数，性能也不会处于完全劣势，所以NM-PSO求解能力总体处于领先水平。

# 4.3.2图表数据分析

对测试函数Rastrigin、Styblinski-Tang、Levy本文算法NM-PSO在平均求解精度上相比其他四个算法表现具有压倒性的优势。并且NM-PSO在跳出局部最优解方面展示出了强大的能力，在进行了大约20000\~40000次目标函数调用后，其余四个算法陷入了局部最优解，在之后的调用中，最优解基本没有再改进，反观本算法，最终的最优值要好上102\~104数量级。对于测试函数Ackley、Griewank、Exponential、Zakharov、Schwefel2.22,本算法在平均求解精度对其他算法虽然没有领先太多，但收敛速度（纵坐标下降速度）全都好于其余四个算法，在同样的函数评估次数下，只有HSPSO算法在Griewank测试的前半段性能与本算法不相上下，其余情况NM-PSO算法皆能够取得最好效果。对于测试函数 sphere，三个基于单纯形的粒子群算法效果均好于RPSO算法，但比DPSO算法差，这可能是单纯形与粒子群算法融合结构决定的。在对Rosenbrock算法进行数值实验时，五个算法均未能很好的达到全局最优，误差都在102数量级。更具体地，对比同样基于单纯形的算法HSPSO,SMPSO，测试函数Ackley表明，三个函数在最终结果，收敛速度方面均要好于传统粒子群算法，且其中本文算法依旧是最优。对于函数 Rastrigin、Griewank、Levy、Exponential、Zakharov 三个算法中总有两者要好于传统算法，体现了单纯形搜索带来的好处。进一步比较三者，本文算法 NM-PSO 更是有三者中最佳的性能。

通过上述对10个测试函数的数值实验分析得出结论：在大部分测试函数下，NM-PSO算法总体上求解精度较高，性能表现优越。

# 5 结束语

为了提高粒子群优化算法的求解性能，本文一方面借鉴电磁机制原理设计了一种PSO迭代方式，另一方面利用单纯形搜索来加速算法收敛。数值实验表明，具有免参数特征的NM-PSO能够很好地平衡局部搜索和全局探索之间的矛盾。借鉴传统优化方法的成熟理论、技巧来指导设计进化算法是本文的初衷，如何设计一种更好、更简洁的算法融合方式是本文今后研究的重点。

# 参考文献：

[1]Kennedy J.Particle swarm optimization [M]//Encyclopedia of machine learning. Boston: Springer,2011: 760-766.   
[2]Clerc M，Kennedy J.The particle swarm-explosion，stability，and convergence in a multidimensional complex space [J].IEEE Trans on Evolutionary Computation,2002,6(1): 58-73.   
[3]Kennedy J.Swarm intelligence [M]//Handbook of nature-inspired and innovative computing.Boston: Springer, 2006:187-219.   
[4]Shi Yuhui,Eberhart R.A modified particle swarm optimizer [C]//Proc of IEEE International Conference on Evolutionary Computation,IEEE World

Congress on Computational Intelligence.Piscataway,NJ:IEEE Press,1998: 69-73.

[5]Eberhart R C, Shi Yuhui. Tracking and optimizing dynamic systems with particle swarms [Cl//Proc ofCongress on Evolutionary Computation. 2001: 94-100.   
[6]Shi Yuhui,Eberhart R C.Parameter selection in particle swarm optimization [Cl// Proc of International Conferenceon Evolutionary Programming Berlin: Springer,998:591-600.   
[7]Eberhart R C,Shi Yuhui. Comparison between genetic algorithms and particle swarm optimization [C]// Proc of International conference on evolutionary programming.Berlin: Springer,1998: 611-616.   
[8]Eberhart RC,Shi Yuhui. Comparing inertia weights and constriction factors in particle swarm optimization [C]// Proc of Congress on Evolutionary Computation.2000:84-88.   
[9] 阳春华，钱晓山，桂卫华．一种混沌差分进化和粒子群优化混合算法 [J].计算机应用研究,2011,28 (2).(Yang Chunhua, Qian Xiaoshan,Gui Weihua.A hybrid algorithm for chaotic difference evolution and particle swarm optimization [J] Application Research of Computers,2011,28 (2)   
[10]李洪亮，侯朝桢，周绍生．一种高效的改进粒子群优化算法[J].计算 机工程与应用,2008,44(1):14-16.(LiHongliang,Hou Chaozhen,Zhou Shaosheng. An efficient improved particle swarm optimization algorithm [J] Computer Engineering and Applications,2008,44(1):14-16)   
[11] Kennedy J. Bare bones particle swarms [C]// Proc of Swarm Intelligence Symposium. 2003: 80-87.   
[12] Birbil \$i,Fang S C.An electromagnetism-like mechanism forglobal optimization[J].Journal of Global Optimization,2003,25 (3):263-282.   
[13] LoengarovA,Tereshko V.Aminimal model ofhoneybee foraging[Cl/ Proc of IEEE Swarm Intell.Symp.2006: 175-182.   
[14] Marini F,Walczak B.Particle swarm optimization (PSO): a tutorial [J]. Chemometricsand Intelligent Laboratory Systems,2015,149:153-165   
[15] Zahara E,Kao YT.Hybrid Nelder-mead simplex search and particle swarm optimization for constrained engineering design problems [J].Expert Systems with Applications,2009,36 (2): 388-886.   
[16] Fan SK S,Zahara E.A hybrid simplex search and particle swarm optimization for unconstrained optimization [J].European Journal of Operational Research,2007,181(2): 527-548.   
[17] Hsu C C,Gao C H. Particle swarm optimization incorporating simplex search and center particle for global optimization [C]//Proc of IEEE Conference on Soft Computing in Industrial Applications. 2008: 26-31.   
[18]任小康，郝瑞芝，孙正兴,等．基于单纯形法的量子粒子群优化算法 [J]．微电子学与计算机,2010(1):154-157.(Ren XiaoKang,Hao Ruizhi, Sun Zhengxing,et al. Quantum particle swarm optimization algorithm based on simplex method [J] Microelectronics and Computer Science,2010 (1): 154-157. )   
[19]武可栋，韦增欣，杨天山．一种使用单纯形法优化的粒子群算法[J]. 数学的实践与认识,2018,48（7):199-205.(Wu Kedong,WeiZengxin,

Yang Tianshan.A particle swarm optimization algorithm using simplex method [J]. Journal of Mathematics in Practice and Theory, 2018,48(7): 199-205.)

[20] Conn A R,Scheinberg K,Vicente L N.Introduction to derivative-free optimization [M]//MOS-SIAM Series on Optimization,2009:141-162

[21] Trelea IC.The particle swarm optimization algorithm: convergence analysis and parameter selection [J].Information processing letters,2oo3,85(6): 317-325.

# 附录：

下面表格列出了所有测试函数的维数，取值范围、最优值（表5）以及解析式（表6）。

表510个测试函数信息  
表6测试函数  
Table 6Test Functions   

<html><body><table><tr><td>函数名</td><td>维数</td><td>取值范围</td><td>最优值</td></tr><tr><td>Ackley</td><td>30</td><td>[-32,32]</td><td>0</td></tr><tr><td>Sphere</td><td>30</td><td>[-100,100]</td><td>0</td></tr><tr><td>Rosenbrock</td><td>30</td><td>[-30,30]</td><td>0</td></tr><tr><td>Rastrigin</td><td>30</td><td>[-5.12,5.12]</td><td>0</td></tr><tr><td>Griewank</td><td>30</td><td>[-600,600]</td><td>0</td></tr><tr><td>Styblinski-tang</td><td>30</td><td>[-5,5]</td><td>-1174.9797</td></tr><tr><td>Levy</td><td>30</td><td>[-10,10]</td><td>0</td></tr><tr><td>Exponential</td><td>30</td><td>[-1,1]</td><td>-1</td></tr><tr><td>Zakharov</td><td>30</td><td>[-5,10]</td><td>0</td></tr><tr><td>Schwefel 2.22</td><td>30</td><td>[-10,10]</td><td>0</td></tr></table></body></html>

Table 5Information of10 Test Functions   

<html><body><table><tr><td>函数名</td><td>解析式</td></tr><tr><td>Ackley</td><td>f(x）=-20*xp[-.2²)-ex(∑(x) + 20 + exp(1)</td></tr><tr><td>Sphere</td><td>f(x)=∑</td></tr><tr><td>Rosenbrock</td><td>f(x)=∑[100(xi+1-x²)² +(x −1)²]</td></tr><tr><td>Rastrigin</td><td>f(x)=∑[x²-10cos(2πxi)}+10n</td></tr><tr><td>Griewank</td><td>（）-1+</td></tr><tr><td>Styblinski- tang</td><td>f(x)=≥(x²-16x²+5x)</td></tr><tr><td>Levy</td><td>f(x)= sin²(πw)+∑(w -1)²[1+10sin²(πw +1)]</td></tr><tr><td></td><td>+(wn −1)2[1+ sin²(2πwn)] where w=1+x-1,i=1,,n</td></tr><tr><td>Exponential</td><td>f（x)=-exp(-0.5∑x²）</td></tr><tr><td>Zakharov</td><td>f(x）=∑²+(∑0.5ix）+(≥.5ix where i²=-1</td></tr><tr><td></td><td></td></tr><tr><td>Schwefel 2.22</td><td>f(x)=∑x1+x1 i=1</td></tr></table></body></html>