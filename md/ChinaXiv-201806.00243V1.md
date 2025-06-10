# 基于POPNSGA-II的配电网故障恢复重构

周生海尹航²顾颖王翀柏峰

（1.国家电网冀北电力有限公司检修分公司北京 1011002.国家电网冀北电力有限公司承德供电公司承德 067000)

![](images/531b99d48e6fb69b4c86a1d71b39ce73d40a43a3ce1e55c0dd32d19d68e3faa8.jpg)

周生海男 1986年生，工程师，主要从事继电保护专业方面的工作。

摘要：快速的非支配排序遗传算法（NSGA-II）可以使每次进化过程中得到的个体分布均匀，具有较好的收敛性和鲁棒性。本文分析了当前遗传算法（GA）的缺陷，将 NSGA-II应用到配电网的故障恢复重构中，并提出通过一种 Pareto 寻优路径(POP)控制选择操作的方法，一方面可以扩大搜索面积、避免陷入局部最优；另一方面可以适时地停止进化、减少多余的计算。另外，本文根据模糊集理论确定故障恢复重构的最终解决方案，使NSGA-II算法适用于恢复重构问题。算例结果表明，POPNSGA-II算法与GA、NSGA-II算法相比具有更强的寻优能力，是一种解决配电网故障恢复重构问题的新方法。

关键词：快速的非支配排序遗传算法 配电网故障恢复重构Pareto 寻优路径 模糊集理论POPNSGA-II

中图分类号：TM743

![](images/9b73fa9466749fa1f42603bdbf1e6ab76d56fce7fd6f75c3091760855199a86a.jpg)

# Service Restoration Reconfiguration in Distribution Systems Based on Pareto Optimizing Path NSGA-II

Zhou ShenghailYin Hang² Gu Yin1 Wang Chong'Bai Fengl (1.State Grid Jibei Electric Power Co.,Ltd.Maintenance Branch Beijing101100 China 2. State Grid Jibei Electric Power Co.,Ltd. Chengde Power Supply Company Chengde 067000 China ）

尹航男1985年生，工程师，主要从事调度运行专业方面的工作。

Abstract: Fast non-dominated sorting genetic algorithm (NSGA-II) can obtain uniformly distributed individualities in the every evolutionary process and has more convergence and more excellent robustness. In this paper, the defects of the current genetic algorithm (GA) are analyzed, then NSGA-II is applied to service restoration reconfiguration in distribution systems,and a method of controlling the selecting operation by the Pareto optimizing path (POP) is provided. On one hand this method can expand the region of searching and avoid to get into local optimum, on the other it can stop evolving duly and reduce the unnecessary calculation.In addition,the final service restoration reconfiguration method is confirmed based on the fuzzy set theory. The simulation results show that POP NSGA-II have more ability of optimizing than GA and NSGA-II. It should be a new method for service restoration reconfiguration in distribution systems.

Keywords: NSGA-II, service restoration reconfiguration in distribution systems, POP, fuzzy set theory, POP NSGA-II

# 1 引言

配电网故障恢复重构的目的是在故障定位和故障隔离以后，通过改变开关的开合状态，在满足电气约束条件的前提下，将非故障失电区域负荷转供到其他正常运行的支路上以恢复对非故障失电区域负荷的供电，从而提高系统的自愈能力和供电可靠性[1-2]

当前，随着分布式能源的接入和用户供电可靠性要求的提高，配电网的运行方式更加多变，网络的复杂度不断增大，影响因素不断增多，使系统内发生故障的可能性以及故障所影响的区域相应增大，直接影响到用户的供电安全和满意度，同时也损害了供电企业的经济利益。为减少用户和供电企业的损失，故障恢复重构作为智能电网的重要功能成为关注的热点之一。故障恢复重构一方面需采用最少的开关操作次数和线路损耗来恢复最多非故障失电负荷；另一方面，还需满足网络拓扑结构、线路裕量等电气约束。因此，配电网的故障恢复重构是一种高度非线性化、多目标、多约束的优化问题[3-6]。

目前求解此类问题的方法主要有启发式搜索算法[7-9]和智能算法[10-12]。启发式搜索算法以禁忌搜索算法（Tabu Search，TS）[13]效果较好，但是为了降低计算量，禁忌长度和禁忌表的集合不宜太大，而禁忌长度太小容易循环搜索，禁忌表太小容易陷入局部最优解。智能算法中以遗传算法（GeneticAlgorithm，GA）[14-16]应用较多。然而，尽管近几年国内外众多学者对遗传算法进行了大量的改进，产生了克隆遗传算法（CloneGeneticAlgorithm，CGA）[7]、免疫遗传算法（ImmuneGeneticAlgorithm，IGA）、模拟退火遗传算法等混合算法，并取得了较好的效果，但是这些算法仍然是通过设置权重因子（WeighFactor，WF）将多目标问题转化为单目标问题，寻优结果受WF的影响较大，寻优能力不稳定。

快速的非支配排序遗传算法(FastNon-dominatedSorting Genetic Algorithm，NSGA-II）[19-21]的思想是协调各目标函数之间的关系，对种群进行快速分组，使个体均匀分布在目标空间中，再通过选择、交叉、变异等操作找出使各目标函数均达到最优的解集。该算法通过非支配排序组别和拥挤距离体现个体之间的优劣性，能够较好地避免权重设置对寻优结果带来的影响。本文将NSGA-II应用于配电网的故障恢复重构，并对选择操作进行了改进，提出一种

Pareto寻优 路 径（Pareto OptimizingPath，POP）,一方面有效地加快了收敛速度，扩大了搜索面积,避免了陷入局部最优；另一方面，可以准确地判断进化进度，进而适时地停止进化。最后通过算例表明了这种方法的可行性与良好的寻优效果，为解决配电网故障恢复重构问题提供了一种新的思路。

# 2 配电网故障恢复重构的数学模型

恢复重构需要考虑的因素包括恢复供电量、开关操作、线路损耗，停电时间、电压分布等目标函数和线路容量、网络拓扑，支路电流和节点电压等约束条件。为方便描述，本文主要考虑部分目标和约束条件。

# 2.1 目标函数

（1）尽量恢复更多非故障失电负荷的供电，即

$$
\left\{ \begin{array} { l l } { \displaystyle \operatorname* { m a x } f _ { 1 } ( x ) = \sum _ { i = 1 } ^ { n } P _ { i } S _ { i } } \\ { \displaystyle \operatorname* { m a x } f _ { 2 } ( x ) = \sum _ { i = 1 } ^ { n } Q _ { i } S _ { i } } \end{array} \right.
$$

(2）尽量减少开关操作次数，即

$$
\operatorname* { m a x } { f _ { 3 } ( x ) } = \sum _ { i = 1 } ^ { n } \Bigl | K _ { i } - S _ { i } \Bigr |
$$

(3）尽量减少线路损耗，即

$$
\operatorname* { m a x } { f _ { 4 } ( x ) } = \sum _ { i = 1 } ^ { n } S _ { i } r _ { i } \frac { P _ { i } ^ { \prime 2 } + Q _ { i } ^ { \prime 2 } } { U _ { i } ^ { \prime 2 } }
$$

式中： $x$ 为当前网络的状态，与参与重构的所有支路闭合有关； $S _ { i }$ 为第 $i$ 个支路的闭合情况， $^ { 6 6 } 0 ^ { 9 }$ 为打开， $^ { * } 1 ^ { * }$ 为闭合； $P _ { i }$ 和 $Q _ { i }$ 为与第 $i$ 个支路相连节点的额定有功功率和无功功率； $K _ { i }$ 为第 $i$ 个支路最初的闭合状态； ${ { { \cal P } } } _ { i } ^ { \prime }$ 、 ${ \underline { { Q _ { i } } } } ^ { \prime }$ 和 ${ U _ { i } ^ { \prime } }$ 分别为支路 $i$ 上的有功功率、无功功率以及末端的节点电压； $r _ { i }$ 为支路 $i$ 的电阻； $n$ 为参与重构的所有支路总数。

# 2.2约束条件

（1）线路容量约束，即

$$
\left\{ \begin{array} { l l } { P _ { i } ^ { \prime } { \leqslant } P _ { i \mathrm { m a x } } ^ { \prime } } & { i { = } 1 , 2 , { \cdots } , n } \\ { Q _ { i } ^ { \prime } { \leqslant } Q _ { i \mathrm { m a x } } ^ { \prime } } & { i { = } 1 , 2 , { \cdots } , n } \end{array} \right.
$$

（2）配电网辐射网络运行约束，即无“回路”。

（3）节点电压约束，即

$$
U _ { i \mathrm { m i n } } \leqslant U _ { i } \leqslant U _ { i \mathrm { m a x } } \quad i = 1 , 2 , \cdots , m
$$

式中， $P _ { \mathrm { i m a x } } ^ { \prime }$ 和 $\mathcal { Q } _ { \mathrm { i m a x } } ^ { \prime }$ 为支路 $i$ 允许流过的最大有功功率、无功功率； $U _ { i }$ 、 $U _ { i \mathrm { m a x } }$ 和 $U _ { i \mathrm { m i n } }$ 为节点 $i$ 的电压及电压上下限； $\mathbf { \nabla } _ { m }$ 为节点总数。

# 3NSGA-II在恢复重构中的应用

# 3.1快速的非支配排序遗传算法

与传统GA相比，NSGA-II算法同样需要通过选择、交叉、变异等操作产生新一代个体；不同的是两类算法处理多目标问题的方式，GA算法使用权重因子将多目标转化为单目标进而得到适应度函数值，并以此体现个体的优劣性，而NSGA-II算法通过非支配排序分类程序，将多目标简化至一个适应度函数，并且定义了拥挤距离估计某个体周围的解密度，判断个体的差异，从而避免了权重对寻优结果产生的影响。

NSGA-II需要对非支配排序、拥挤距离进行计算，其具体实现原理和方法在文献[20]中有所介绍，本文不再赘述。

# 3.2基于NSGA-II的故障恢复重构的算法流程

NSGA-II算法已经在一些实际工程中得到了广泛的应用。文献[21-23]分别提出将NSGA-II算法应用于含分布式电源的配网重构、无功优化和电网规划等问题。本文尝试将NSGA-II算法应用于配电网的故障恢复重构，其具体实现步骤如下：

（1）编码。本文采取二进制方式，将参与重构  
的所有开关进行编号， $^ { 6 6 } 0 ^ { 9 }$ 和“1”分别代表开关当  
前状态为“打开”和“闭合”。(2）产生随机初始种群。随机产生一个大小为  
$N$ 的初始种群 $P _ { 0 }$ 。(3）目标函数值计算。通过潮流计算获得每个  
染色体的目标函数值。(4）非支配排序和虚拟适应度计算。(5）选择运算。选择操作采用精英策略，即  
保留父代中的优良个体直接进入子代，它是遗传算  
法以概率1收敛的必要条件，目的是使进化朝着  
Pareto最优解的方向进行，并且避免染色体在局部  
拥挤。因此，选择算子要保证种群中优良的个体以  
最大的概率生存，从而提高全局最优和计算效率。(6）交叉和变异。交叉可以保留父代染色体中

优良的基因，变异可以避免种群个体的性状过于单一，两者相互配合可使遗传算法具有良好的搜索能力。正态变异算子是基于正态分布的变异操作。

（7）判断终止条件。判断是否达到预设的最大迭代次数或者寻找到最优方案，如果是终止迭代，则输出计算结果，否则，应返回步骤（3）继续迭代。

# 4基于Pareto 寻优路径的NSGA-II

# 4.1Pareto 寻优路径

Pareto 寻优路径（POP）主要包含两方面信息：Pareto寻优方向（Pareto Optimizing Tend，T）和Pareto最优解集 $F _ { 1 }$ 中染色体的数目（ChromosomeNumber, $\mathrm { C } ^ { N u m }$ ）

（1）Pareto寻优方向 $( T )$ 。当进化过程进行到第 $n$ 次时，由精英策略可以得到Pareto最优解集$F _ { 1 }$ ，它体现了当前进化的最高水平。那么，定义第$n + 1$ 次Pareto寻优方向值 $T _ { n + 1 }$ 为

$$
T _ { n + 1 } = \left\{ \begin{array} { c c } { { T _ { n } + 1 , C _ { ( n + 1 ) i } \succ C _ { n j } } } & { { \exists i = 1 , 2 , \cdots , N _ { n + 1 } ; j = 1 , 2 , \cdots , N _ { n } } } \\ { { T _ { n } , C _ { ( n + 1 ) i } = C _ { n j } } } & { { \forall i = 1 , 2 , \cdots , N _ { n + 1 } ; j = 1 , 2 , \cdots , N _ { n } } } \end{array} \right.
$$

式中， $C _ { ( n + 1 ) i }$ 为进化到第 $n + 1$ 次时 $F _ { 1 }$ 中第 $i$ 个染色体； $C _ { n j }$ 为进化到第 $n$ 次时 $F _ { 1 }$ 中第 $j$ 个染色体；$C _ { ( n + 1 ) i } \succ C _ { n j }$ 为染色体 $C _ { n j }$ 被 $C _ { ( n + 1 ) i }$ 所支配； $T _ { n }$ 为第 $n$ 次寻优方向值， $n = 1$ 时， $T _ { 1 } = 0$ 。通过对比连续两次进化中Pareto 最优解集 $F _ { 1 }$ 的变化情况，得到Pareto寻优方向 $T _ { \circ }$ $T$ 可以如实地反映进化的方向，跟踪进化的轨迹。

(2) $F _ { 1 }$ 中染色体的数目 $( C ^ { N u m } )$ 。由于NSGA-II算法所得到最优解的个数未知， $C ^ { N u m }$ 的变化同样可以反映进化情况。

由式（6）和 $C ^ { N u m }$ 的变化可以导出 POP 的计算式为

$$
P O P _ { n + 1 } = \left\{ \begin{array} { c c } { { P O P _ { n } } } & { { T _ { n + 1 } = T _ { n } \bigcap C _ { n + 1 } ^ { N u m } = C _ { n } ^ { N u m } } } \\ { { P O P _ { n } + 1 } } & { { \sharp _ { \star } ^ { \star } / { \sharp } } } \end{array} \right.
$$

其中， $C _ { n } ^ { N u m }$ 为进化到第 $n$ 次时 $F _ { 1 }$ 中染色体的数目。

$T$ 和 $C ^ { N u m }$ 相互配合可以体现 $F _ { 1 }$ 中染色体的变化。当 $F _ { 1 }$ 中仅增加了目标值相同的染色体而 $T$ 不变，或者 $C ^ { N u m }$ 不变而 $F _ { 1 }$ 中的染色体已经被更优的个体所取代，只要父代 $F _ { 1 }$ 有更新动作，POP就能如实反映出来，即在进化中，只要子代种群找到更优的或者与父代最优个体目标值相同但基因不同的新个体，POP均能体现。

# 4.2虚拟适应度

虚拟适应度是目标空间中的每一点（个体）

与同层相邻两点之间的局部拥挤距离。以 $F ( x ) =$ $( f _ { 1 } ( x ) , f _ { 2 } ( x ) , \cdots , f _ { k } ( x ) )$ 为例，令 $k = 2$ ，则图1目标空间中第 $i$ 点的拥挤距离等于该点在同一组别中相邻的点i-1和 $i + 1$ 在目标1轴和目标2轴的距离之和，即为点i-1和点 $i + 1$ 组成的矩形周长的1/2。

![](images/660ffcb1143b97cd5d6fece514a36d134a484e8168c019fa6f2500dcf501d6ae.jpg)  
图1局部拥挤距离示例图  
Fig.1Crowding distance in local space

# 4.3POP选择算子

根据Pareto寻优路径，选择规模 $s$ 的大小定义为

$$
S _ { n } = \left\{ \begin{array} { c c } { { N } } & { { B < B _ { \mathrm { m i n } } } } \\ { { N + \displaystyle \frac { N } { 2 } ( B - B _ { \mathrm { m i n } } ) } } & { { B _ { \mathrm { m i n } } \leqslant B \leqslant B _ { \mathrm { m a x } } } } \end{array} \right.
$$

式中， $N$ 为初始种群大小； $B$ ， $B _ { \mathrm { m a x } }$ ， $B _ { \mathrm { m i n } }$ 分别为POP 连续不发生变化的次数及上下限。

由式（8）可知，当连续 $B _ { \mathrm { m i n } }$ 进化没有进展时，则选择规模 $S$ 将随着 $B$ 的增大不断递增，搜索面积和搜索能力不断提高。当 $B = B _ { \operatorname* { m a x } }$ 时，进化依然没有进展，则程序停止，当前 $F _ { 1 }$ 为最优解集。

投入POP选择算子使算法增加的计算量 $\Delta M$ 为

$$
\begin{array} { r } { \Delta M = \frac { \displaystyle \frac { \left[ \frac { N } { 2 } + ( B _ { \operatorname* { m a x } } - B _ { \operatorname* { m i n } } ) \frac { N } { 2 } \right] ( B _ { \operatorname* { m a x } } - B _ { \operatorname* { m i n } } ) } { 2 } } { \displaystyle - \frac { N } { 4 } [ ( B _ { \operatorname* { m a x } } - B _ { \operatorname* { m i n } } ) + 1 ] ( B _ { \operatorname* { m a x } } - B _ { \operatorname* { m i n } } ) } } \end{array}
$$

由式（9）可知，在寻优没有进展的情况下，适当地增加选择规模的大小，可增加全局和局部搜索面积，进而减少局部收敛的可能性，避免出现早熟的现象；同时，计算最大增加量相当于多进化$( B _ { \mathrm { m a x } } - B _ { \mathrm { m i n } } + 1 ) ( B _ { \mathrm { m a x } } - B _ { \mathrm { m i n } } ) / 4$ 次。因此，只要合理地控制 $B _ { \mathrm { m a x } }$ 、 $B _ { \mathrm { m i n } }$ ，POP选择算子并不会增加计算负担。

# 4.4相似度交叉算子

相似度交叉算子（SemblanceCrosser，SC）需要对比两个父代染色体之间的基因相差值 $S _ { \mathrm { C } }$ 。当 $S _ { \mathrm { C } } =$ 0或者 $S _ { \mathrm C } = 1$ 时，采用SBX随机产生的子代染色体总与父代相同，这样不利于种群的进化，相似度交叉算子采取基因重组策略，即父代染色体的所有基因随机进行排列组合产生子代；当 $S _ { \mathrm C } > 1$ 时，见表1，若随机交叉点在 $1 \sim 4$ ， $8 \sim 9$ 的位置，则交换交叉点两侧的基因产生的子代同样与父代相同。因此，相似度交叉算子随机选取基因5、6、7作为交叉点。

# 表1相似度交叉算子示意图

Tab.1 Chart of semblance crosser   

<html><body><table><tr><td>基因编号</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td></tr><tr><td>父代1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>1</td><td>0</td><td>1</td></tr><tr><td>父代2</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td></tr></table></body></html>

相似度交叉算子可提高种群的进化效率，避免无效进化，进而加快收敛速度。

# 4.5确定最优方案

在实际应用中，恢复重构问题最终需要的方案只有一个，因此决策者需要根据实际情况在 $F _ { 1 }$ 中确定最优解。本文采取模糊集理论确定最优方案[24]。$F _ { 1 }$ 中个体的满意度可表示为

$$
h = 1 - \frac { 1 } { N _ { \mathrm { o b j } } } \sum _ { i = 1 } ^ { N _ { \mathrm { o b j } } } \frac { f _ { i - \mathrm { m a x } } - f _ { i } } { f _ { i - \mathrm { m a x } } - f _ { i - \mathrm { m i n } } }
$$

式中， $i { \in } \{ 1 , 2 , \cdots , N _ { \mathrm { o b j } } \}$ ， $N _ { \mathrm { o b j } }$ 为目标函数的个数； $f _ { i }$ 为目标函数； $f _ { i \mathrm { - } \operatorname* { m a x } }$ 和 $f _ { i - \operatorname* { m i n } }$ 为 $F _ { 1 }$ 中第 $i$ 个目标函数的最大值和最小值。

最后将具有最大 $h$ 值的个体作为最优方案。

# 4.6基于POPNSGA-II的恢复重构流程图

由 NSGA-II算法流程和Pareto寻优路径的提出，可得到基于POPNSGA-II算法的配电网故障恢复重构的流程图如图2所示。

# 5 算例验证和分析

本算例是PG&E69节点单电源的配网系统，其原始网络结构如图3所示。

图3中实线 $3 \sim 2 2$ 为运行支路，虚线1、2、23、24为联络支路。初始状态时，运行支路全部闭合，联络支路全部打开，网络参数见文献[25]。假设节点10-11发生故障，故障切除后，故障点下游区域的节点 $1 1 \sim 2 7$ 、 $5 6 \sim 5 9$ 都会失去供电。为验证算法，以恢复最大供电负荷有功功率 $f _ { 1 }$ 、无功功率 $f _ { 2 }$ 和最小开关操作次数 $f _ { 3 }$ 为目标函数，以重构后保持辐射状网络、满足联络支路容量为约束条件，分别采用禁忌克隆遗传算法（TabuSearchClonalGenetic Algorithm，TSCGA）、传统NSGA-I算法和本文算法对算例进行配电网故障恢复重构的仿真计算。各算法的运行参数设置如下：初始种群规模为100，最大迭代次数为200，交叉概率为0.9，变异概率为0.1，POP 选择算子投入时Pareto寻优路径连续不变最小次数 $B _ { \mathrm { m i n } } = 5$ ，最大次数即停止条件 $B _ { \mathrm { m a x } } = 1 0$ 。联络支路1、2、24可提供的最大有功功率分别为350、300、 $2 5 0 \mathrm { k W }$ ，无功功率分别为250、200、150kvar。由于算法均采用了随机操作，为真实体现算法的寻优效果，每种算法连续运行100次，所得结果为平均值。另外，为分析权重对GA 算法的影响，在TSCGA算法中将考虑所有步长为0.1的权重系数W组合，因篇幅所限，只给出几种寻优结果，见表2。

![](images/1985a4bdf45baa0ecef42128aacac5e1f317ac796a0894dff19a1b07d3a1fd20.jpg)  
图2算法流程图

![](images/3fed2ffbc3db5acc9e926cb5d95055e926664ead0903aa5beedc7bae4e6e4290.jpg)  
Fig.2Flow chart of calculation   
图3PG&E69节点配网系统Fig.3PG&E 69 bus system

表2中稳定性为100次计算结果中相同最优解个数所占的比例。从表2可以看出，由于TSCGA算法的寻优结果偏重于W分配较高的目标值，使W分配较低的目标值对遗传操作的影响极小，所以不能保证所有目标值都达到最优；同时，稳定性受W的影响较大，即每次寻优结果存在较高的差异。

三种算法的计算结果见表3。表3中，POP

表2TSCGA算法的计算结果  
Tab.2The computing result of TSCGA   

<html><body><table><tr><td>权重分配</td><td>0.8/0.1/0.1</td><td>0.7/0.2/0.1</td><td>0.6/0.2/0.20</td><td>0.5/0.2/0.3</td></tr><tr><td>f/kW</td><td>681.493 9</td><td>668.387 6</td><td>630.8342</td><td>586.741 2</td></tr><tr><td>f/kvar</td><td>431.234 4</td><td>422.587 4</td><td>411.685 3</td><td>388.2864</td></tr><tr><td>f3/次</td><td>6.57</td><td>9.33</td><td>8.75</td><td>8.15</td></tr><tr><td>时间/s</td><td>6.5878</td><td>6.6748</td><td>6.536 6</td><td>6.672 7</td></tr><tr><td>稳定性(%)</td><td>81</td><td>76</td><td>69</td><td>65</td></tr></table></body></html>

NSGA-II与NSGA-II算法相比，POPNSGA-II算法增大了 $F _ { 1 }$ 的规模，为操作者提供了更多的选择；另一方面，POPNSGA-II算法通过提高进化效率，减小了迭代次数、缩短了进化时间、提高了寻优结果的稳定性和质量。

Tab.3The computing results of three algorithms   

<html><body><table><tr><td>算法</td><td>NSGA-II</td><td>POP NSGA-II</td><td>TSCGA(0.8/0.1/0.1)</td></tr><tr><td>f/kW</td><td>695.8</td><td>701.5</td><td>681.493 9</td></tr><tr><td>f/kvar</td><td>460.1</td><td>469.6</td><td>431.234 4</td></tr><tr><td>f/次</td><td>6.994</td><td>6.369</td><td>9.576</td></tr><tr><td>时间/s</td><td>6.753 4</td><td>6.286 4</td><td>6.2878</td></tr><tr><td>迭代次数</td><td>68.668</td><td>59.482</td><td>78.659</td></tr><tr><td>F中个体数</td><td>8.159</td><td>11.615</td><td></td></tr><tr><td>稳定性(%)</td><td>91</td><td>99</td><td>81</td></tr></table></body></html>

图4为采用相同初始种群和随机操作时，POPNSGA-II算法和NSGA-II算法单次计算的Pareto 寻优路径。在进化初期，由于本文算法采用相似度交叉算子，所以其进化不断向Pareto最优解方向进行，进化效率较高；在迭代次数达到一定程度以后，两种算法均进入了进化缓慢阶段，由于POP选择算子的投入，POPNSGA-II算法通过适时增加种群规模、交叉和变异操作，进而产生更多的新个体、加大搜索面积，及时跳出局部最优，有效地避免了早熟。在此方法中，POP选择算子共投入使用11次，由式（9）得到增加的计算量相当于11次遗传操作；当迭代次数达到45次时，由Pareto寻优路径判定程序停止。而传统的NSGA-II算法两次陷入局部最优，在连续15次的进化中，没有任何进展。表4为两种算法本次的计算结果。

![](images/9e28ad272b5993acba6fb82d96eb1594b37377f71cf3101521008534f99ecefd.jpg)  
图4Pareto 寻优路径 Fig.4Pareto optimizing path

表3三种算法的计算结果   
表4两种算法的单次计算结果  
Tab.4The computing results of two algorithms once   

<html><body><table><tr><td>算法</td><td>NSGA-II</td><td>POP NSGA-II</td></tr><tr><td>F中最优解个数</td><td>9</td><td>14</td></tr><tr><td>最终方案动作开关</td><td>1,2,4,5,15,21,24</td><td>1,2,4,12,21,24</td></tr><tr><td rowspan="3">恢复重构效果</td><td>fi =695.8kW</td><td>fi=703.8kW</td></tr><tr><td>f=478.6kvar</td><td>f2= 484.1kvar</td></tr><tr><td>f=7</td><td>f=6</td></tr></table></body></html>

# 6 结论

本文将NSGA-II算法应用于配电网的故障恢复重构问题。通过Pareto寻优路径控制选择操作，一方面在进化受阻、缓慢的情况下，加大搜索面积，减小陷入局部最优的可能性；另一方面，适时地停正进化，避免多余的计算。同时，应用模糊集理论在最优解集 $F _ { 1 }$ 中确定输出方案，使NSGA-II算法完全适用于故障恢复重构问题。PG&E69节点的算例说明POPNSGA-II算法的恢复重构效果和 $F _ { 1 }$ 中最优解个数均优于传统的 NSGA-II算法。

# 参考文献

[1] 张浩，和敬涵，尹航，等．电网孤岛重构的云计 算策略[J]．中国电机工程学报，2011，31(34)： 77-84. Zhang Hao,He Jinghan,Yin Hang,et al. Power grid islands service restoration based on cloud computing[J]. Proceedings of the CSEE,2011, 31(34): 77-84.   
[2] 张浩，和敬涵，薄志谦，等．基于动态规划算法的 故障恢复重构[J]．电工技术学报，2011，26(12)： 162-167. Zhang Hao,He Jinghan,Bo Zhiqian,et al. Service restoration based on dynamic programming[J]. Transactions of China Electrotechnical Society, 2011, 26(12): 162-167.   
[3] LimSI,Lee SJ,ChoiMS, et al. Service restoration methodology for multiple fault case in distribution systems[J].IEEE Transactions on Power Systems, 2006,21(4): 1638-1644.   
[4] Manjunath K,Mohan MR.A new hybrid multiobjective quick service restoration technique for electric power distribution systems[J]. International Journal of Electrical Power& Energy Systems,2007, 29: 51-64.   
[5]Huang C M. Multi-objective service restoration of distribution systems using fuzzy cause-effect networks[J]. IEEE Transactions on Power Systems, 2003,18(2): 867-874.   
[6] 陈竟成，徐德超，于尔铿，等．配电网故障恢复 系统[J]．电力系统自动化，2000，24(4)：46-51. Chen Jingcheng,Xu Dechao,Yu Erkeng,et al. Distribution fault detection, isolation and restoration system in a distribution management system[J]. Automation of Electric Power Systems,2000,24(4): 46-51.   
[7] Raju G K V, Bijwe P R. An efficient algorithm for minimum loss reconfiguration of distribution system based on sensitivity and heuristics[J]. IEEE Transactions on Power Systems, 2008, 23(3): 1401- 1407.   
[8] Shirmohammadi D, Hong H W. Reconfiguration of electric distribution networks for resistive line losses reduction[J]. IEEE Transactions on Power Delivery, 1989, 4(2): 1492-1498.   
[9] 陈根军，李继洸，唐国庆．基于Tabu 搜索的配 电网络重构算法[J]．中国电机工程学报，2002, 22(10): 28-33. Chen Genjun, Li Jiguang, Tang Guoqing. A tabu search approach to distribution network reconfiguration for loss reduction[J]. Proceedings of the CSEE,2002,22(10): 28-33.   
[10]徐廷炜，贾嵘．基于人工免疫思想的蚁群算法 (AIACS)在配电网重构中的应用[J]．电力系统保 护与控制，2010，38(18)：89-93. Xu Yanwei, Jia Rong.Application of artificial immune theory-based ant colony system (AIACS) in reconfiguration of distribution networks[J]. Power System Protection and Control, 2010, 38(18): 89- 93.   
[11]于永哲，黄家栋．基于改进模拟植物生长法的 配电网络重构[J]．电力系统保护与控制，2010, 38(2): 40-43. Yu Yongzhe, Huang Jiadong. Reconfiguration of distribution network based on improved plant growth simulation algorithm[J]. Power System Protection and Control, 2010, 38(2): 40-43.   
[12]李振坤，陈星莺，余昆，等．配电网重构的混合粒 子群算法[J]．中国电机工程学报，2008，28(31)： 35-41. Li Zhenkun, Chen Xingying, Yu Kun,et al. Hybrid particle swarm optimization for distribution network reconfiguration[J]. Proceedings of the CSEE,2008, 28(31): 35-41.   
[13]黄弦超，舒隽，张粒子，等．免疫禁忌混合智能 优化算法在配电网检修优化中的应用[J]．中国电 机工程学报，2004，24(11)：96-100. Huang Xianchao,Shu Jun, Zhang Lizi, et al. Distribution maintenance scheduling using an intelligent optimal approach mixed with immune algorithm and tabu search[J]. Proceedings of the CSEE,2004,24(11): 96-100.   
[14]唐斌，罗安，王击．改进遗传算法的编码策略 及其在配电网重构中的应用[J]．继电器，2004, 32(13): 35-39. Tang Bin, Luo An, Wang Ji. The improved encoding strategy of genetic algorithm and its application in reconfiguration of distribution networks[J]. Relay, 2004, 32(13): 35-39.   
[15]邹必昌，龚庆武，李勋．基于负荷平衡的配电网重 构遗传算法研究[J]．电力系统保护与控制，2011, 39(6): 80-93. Zou Bichang, Gong Qingwu, Li Xun. Research on network reconfiguration GA in distribution system based on load balancing[J]. Power System Protection and Control, 2011, 39(6): 80-93.   
[16]王韶，马晶晶，周鑫，等．配电网重构的蜜蜂型遗 传算法[J]．电力系统保护与控制，2010，38(16)： 62-67. Wang Shao,Ma Jingjing, Zhou Xin,et al. Bee evolution genetic algorithm for distribution network reconfiguration[J]. Power System Protection and control,2010,38(16): 62-67.   
[17]周辉，王击，罗安，等．克隆遗传算法与模拟退 火算法相结合的配电网重构[J]．继电器，2007, 35(7): 41-45. Zhou Hui,Wang Ji,Luo An,et al. Distribution network reconstruction based on the combination of CGA and SA[J]. Relay,2007, 35(7): 41-45.   
[18]王林川，梁栋，于冬皓，等．基于遗传和禁忌搜 索混合算法的配电网重构[J]．电力系统保护与控 制．2009．37(6)：27-31 Wang Linchuan,Liang Dong,Yu Donghao,et al. Distribution network reconfiguration based on genetic/tabu search hybrid algorithm[J].Power System Protection and Control, 2009,37(6):27-31.   
[19] Sbalzarini I F,Muller S,Koumoutsakos P. Multiobjective optimization using evolutionary algorithms[C].Center for Turbulence Research, Proceedings of the Summer Program,20oo: 63-74.   
[20] Srinivas N,Deb K.Multiobjective function optimization using nondominated sorting genetic algorithms[J]. Evol. Comput.,1995,2(3): 221- 248.   
[21] Kalyanmoy Deb,Amrit Pratap,Sameer Agarwal, et al.A fast and elitist multiobjective genetic algorithm:NSGA-II[J].IEEE Transactions on Evolutionary Computation,2002,6(2): 182-197.   
[22] 黄弦超．含分布式电源的配电网故障恢复模型[J]. 电力系统保护与控制，2011，39(19)：52-57. Huang Xianchao.Model of service restoration of distribution systems with distributed generation[J]. Power System Protection and Control,2011,39(19): 52-57.   
[23] 冯士刚，艾芊．带精英策略的快速非支配排序遗 传算法在多目标无功优化中的应用[J]．电工技术 学报，2007，22(12)：146-151. Feng Shigang,Ai Qian.Application of fast and elitist non-dominated sorting generic algorithm in multi-objective reactive power optimization[J]. Transactions of China Electrotechnical Society, 2007,22(12): 146-151.   
[24] 王秀丽，李淑慧，陈皓勇，等．基于非支配遗传 算法及协同进化算法的多目标多区域电网规划[J] 中国电机工程学报，2006，26(16)：11-15. Wang Xiuli, Li Shuhui, Chen Haoyong,et al.Multiobjective and multi-district transmission planning based on NSGA-II and cooperative co-evolutionary algorithm[J].Proceedings of the CSEE,2006, 26(16): 11-15.   
[25] 陈水利，李敬功，王向公．模糊集理论及其应用 [M]．北京：科学出版社，2005.   
[26] 刘健，毕鹏翔，董海鹏．复杂配电网简化分析与 优化[M]．北京：中国电力出版社，2002.