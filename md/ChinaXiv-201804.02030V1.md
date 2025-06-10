# 基于改进自适应遗传算法的移动WSN覆盖方法

朱利民1，赵丽²

(1．河南工学院 计算机科学与技术系，河南 新乡 453000;2.山西大学 软件学院，太原 030013)

摘要：针对传统的WSN覆盖模型的弊端，尤其是如果一个传感器失效，K-覆盖模型需要至少k个传感器节点监测其范围内是否有目标需要覆盖，提出了一种基于改进自适应遗传算法的移动 WSN 覆盖方法，在能量资源有限的前提下，尽可能长时间的对指定的目标进行连续监测。该算法考虑到了移动传感器是可以连续和变速运动的，从而能够保证所有目标都在它们的覆盖范围内。仿真结果表明，在使用移动节点的情况下，与其他常用模型相比，改进方法的生存周期和数据包数量都有明显提高。

关键词：无线传感器网络；自适应；改进遗传算法；K-覆盖；移动节点 中图分类号：TP393.02 doi:10.3969/j.issn.1001-3695.2017.12.0765

Mobile WSN coverage method based on improved adaptive genetic algorithm

Zhu Limin1, Zhao Li² (1.DeptofComputerScience&TechnologyHenan InstituteofTechnology，Xinxiang Henan 4530,China;2.Schoolof Software Shanxi University,Taiyuan O3oo13,China)

Abstract: Aimingatthdrawbacksofthecasical Wcoveragemodel,speciallifsnsordies,K-coverage modelruires atleast ksensor nodes to monitor whether tereisatarget withinitscoveragearea.This paper proposedamobile WSNcoverage method basedon improved adaptive geneticalgorithm,which provided continuous monitoring of specified targets forlongest possible time with limited energy resources.Thealgorithmtook into acount that the motionsensorcould moveat variable speeds continuouslyto ensure that alltargets were within theircoverage.Simulationresults show that in thecaseof mobile nodes,the life span and the numberof data packets of the improved method areobviously improved compared with other commonly models.

Key Words: wirelesssensor networks; adaptation; improved genetic algorithm; K-coverage; mobile node

# 0 引言

无线传感器网络（wirelesssensornetwork，WSN）广泛应用于工业、环境监测、健康管理以及农业等诸多领域[1]。由于能量有限，WSN传感器只能在有限的时间内保持有效，所以人们将传感器划分为不同的组，即传感器覆盖，使得每个覆盖在一定持续时间内监视目标，以实现传感器的最优化使用，增加传感器网络的寿命。这么做可以激活所部署的冗余传感器以覆盖目标区域，这个问题是就是一个K-覆盖问题，即需要最少 $k$ 个传感器节点来监测一个目标区域[2]。

在众多的目标覆盖方法中，目标通常被假定为是已知的，并且每个目标被一个传感器覆盖。但是，当传感器能量耗尽时，这些算法的效果往往达不到要求。在文献[3]中，研究者引入了流分解算法（flowdecompositionalgorithm，FDA)，并与文献[4]中提出的固定定向传感器调度问题（fixeddirectional sensorscheduling problem，FDSSP）进行了比较。FDA的目标是将最大的流分解为一组单独的流，每一个单流代表一个Sink 路径的源。该路径的传感器形成一个覆盖，通过该路径的流量等于该覆盖的寿命。FDSSP则寻求固定的定向传感器时间表，使寿命最大化。此外，还必须要考虑传感器网络的拓扑，传感器激活的模式等因素，以确定最佳的网络管理解决方案。Yang在文献[5]中提出了可变功率寿命（Variable-PowerLifetime Network，VP-NL）调度方案，假定每个传感器可以动态地改变其操作功率来调节其感测范围。在VP-NL中，作者提出了一种多项式算法，并进行了大量的实验和数值仿真，验证了算法的有效性。随着传感器的普及，无线传感器网络不再是静止的，这大大拓展了传感器网络在动物运动追踪和环境监测领域的应用范围。在许多情况下，监测整个地区可能是不必要的，特别是考虑到观测过程的动态性质。当传感器配备运动功能时，监测多个目标点而不是整个区域会提高网络性能并允许基于时间依赖的覆盖。在移动传感器网络中，将目标覆盖范围与传感器连接到数据接收器仍然是一个巨大的挑战。

当监控和军事应用需要可靠的监测能力时，通常需要非固定的K-覆盖。由于无线传感器的能量限制以及更换或充电的不可行性，传感器必须密集布置。然而，保持所有的传感器活跃将会使他们的能量消耗过快。目前不同的生物启发式优化算法已被用于无线传感器网络。例如，使用粒子群优化（particleswarmoptimization，PSO）[6来优化模糊隶属度函数，以获得关于传感器节点的电池寿命的最佳结果。文献[7]采用混合群体智能算法对模糊规则表进行优化，利用所提出的算法将所有传感器节点聚类为平衡群。文献[8]利用萤火虫群优化（glowwormswarm optimization，GSO）[9]算法提高覆盖。但是GSO和PSO等算法的使用可能会在搜索能力方面有所限制。另外，遗传算法（geneticalgorithm，GA）由三个关键的遗传要素组成，即交叉，变异和选择，交叉和变异要素为新解提供了多样性，交叉在子空间内提供有限的多样性，而变异要素可以通过探索遥远的子空间来提供更好的多样性。

本文提出了一种基于改进自适应遗传算法的移动WSN 覆盖方法来优化无线传感器网络的覆盖范围，在能量有限的情况下，尽可能长时间的监视特定目标。传感器节点是非平稳的，可以在现场移动以收集数据。在本文中，数据传输周期是收集目标数据并传输给基站的时间段。本文算法提出了一种优化传感器覆盖的方法，其目标是通过确定传感器覆盖的模式来最大化网络寿命。基于一系列因素，例如每个传感器的覆盖范围、预期的消耗能量、到基站的距离以及目标位置，改进遗传算法确定各传感器节点的覆盖范围，并决定由哪个节点负责将数据传送到基站。因此，本文所提出的模型能够确保监测区域被最少数量的传感器完全覆盖。

本文主要提出两点改进。首先，提出了一种基于GA的覆盖形成方法，可以产生所有可能的传感器覆盖。其次，提出了一项无线传感器网络覆盖管理方法，可以在不同传感器覆盖之间进行切换，以最大化网络寿命。为了形成传感器覆盖，所提出的模型基于如下假设：

a）目标的位置是已知的，它们是静止的；  
b）所有节点都能够向基站传输数据；  
c）所有传感器节点具有相同数量的初始能量；  
d）传感器网络在每次数据传输之后进行调整；  
e)该区域有一个基站，在每一轮之后，为下一轮构建网络;  
f)当传感器改变其模式(活动/睡眠)时，会发生数据传输。

# 1 相关工作

目标覆盖问题在无线传感器网络中引起了广泛关注。文献[4]提出了一种选择互斥的传感器节点集合的启发式算法。集合的成员都可以完全覆盖整个区域，但任何时候只有一个成员是活动的。该算法在完全保留覆盖范围的同时实现了显著的节能效果。Cardi 等人[10提出了一种通过将传感器重组为最大数量的不相交集合覆盖来延长传感器网络寿命的方法。此外，来自当前有效集合的传感器还可以被用于传输所收集的信息、监视目标等。这个方法取得了有竞争力的结果，并且在产生不连续传感器覆盖的数量增加的方面，其性能超过了Slijepcevic 和Potkonjak 的算法。文献[11]根据简单随机抽样理论和最优化算法建立了二次优化的数学模型，优化了网络的覆盖。

有许多研究采用生物启发式算法来优化K-覆盖问题。文献[12]将粒子群优化算法和多策略融合方法结合起来用于无线传感器网络的覆盖。文献[13]将粒子群优化和模拟退火算法结合起来用于无线传感器网络的节能覆盖。文献[14]将鱼群算法用于无线传感器网络的覆盖优化。文献[15]利用基于生物地理学算法优化了K-覆盖问题，并将该算法的性能与遗传算法进行了比较。结果表明，基于生物地理学的算法性能优于遗传算法。

# 2 问题描述

令 $N = ( T , S )$ 是一个无线传感器网络，其中S={s,s,.sm}是传感器节点，m 是传感器的数量其感测范围为 $R _ { s }$ ； $T = \{ t _ { 1 } , t _ { 2 } , . . . , t _ { n } \}$ 是一组待测目标集合， $n$ 是待测目标的数量。图1展示了一组无线传感网络中传感器和目标的例子。每个目标都要被不少于一个的传感器感测到，例如，目标 $t _ { 1 }$ 被传感器 $s _ { 1 }$ 和 $s _ { 3 }$ 感测。所收集到的节点数据被汇聚节点处理。如果一个传感器节点能够获取或者传播数据，那么它就是一个活动节点。如果一个传感器节点不执行任何任务，那么它就处于休眠状态。

![](images/7089d182f063c4f38800011607a2f2e2d5df822dd4279a8890edb85eae9b9c0a.jpg)  
图1无线传感网络节点分布

网络的寿命可以定义为网络从建立开始到有1个或更多的目标不能够被传感器所覆盖结束。在连接目标覆盖（connectedtargetcoverage，CTC）问题中，可以使用最大覆盖树（maximumcover tree，MCT）建模。

本文所提出的模型能够识别最大数量的非互斥的传感器集合，称为传感器覆盖，其边界为 $C _ { \mathrm { m a x } }$ 。在某一时刻，所有的目标都能够被覆盖，且传感器覆盖中只有一个是活动的。令 $c$ 为传感器覆盖的集合，也就是 $C = \{ C _ { 1 } , C _ { 2 } , . . . , C _ { \operatorname* { m a x } } \}$ 。对于每一个传感器覆盖 $C _ { k } ( C _ { k } \in C )$ ，都足以覆盖网络中的每一个目标。一个传感器覆盖 $C _ { k }$ 的生存周期可以表示为 $X ( C _ { k } )$ ，它不能够超过$C _ { k }$ 中的任意一个传感器的剩余能量，这个具有最小剩余能量的传感器节点的寿命被称作是最小寿命，也就是$X ( C _ { k } ) = \operatorname* { m i n } ( C _ { k } ( b _ { i } ) )$ 。

节能目标覆盖问题可以描述为一个最大化所有传感器覆盖的生存周期的优化问题。因此，目标覆盖问题的目标是在传感器覆盖的所有集合中找到具有最大聚合网络寿命的完整的传感器覆盖族。最大化 $\sum p x _ { p }$ ，其中

$$
\sum _ { p } B _ { i p } x _ { p } \leq b _ { i } \big ( \forall s _ { i } \big )
$$

其中： $p$ 表示传感器覆盖的序号， $x _ { p }$ 表示传感器的覆盖，x≥O(∀Cp)，si表示第i个传感器节点，bi表示传感器s的寿命， $C _ { p }$ 表示第 $p$ 个传感器覆盖， $B$ 是约束矩阵的约束，可以表示为如下形式：

$$
B _ { i j } = \left\{ { \begin{array} { r l } { 1 } & { { } \ s _ { i } \in C _ { p } } \\ { 0 } & { { } \ \not \equiv \not \equiv \not | \not \equiv } \end{array} } \right.
$$

# 3 基于改进自适应遗传算法的移动WSN覆盖方法

本文模型使用改进遗传算法的目标是最大化网络的寿命。这一模型主要由三部分组成。第一部分，称之为编码阶段，整个系统被初始化，也就是说，将传感器节点分布在工作区域，然后用二进制染色体对该区域内的传感器节点进行编码；第二个阶段称之为优化阶段，利用改进的遗传算法形成初始种群。改进的遗传算法在每一轮运行后选择最佳的覆盖头节点。依靠传感器的感测范围和目标位置，将会形成覆盖；第三个阶段称之为验证阶段，每一组染色体都会被测试以确保可以覆盖所有目标。通过获得所有可能的覆盖，便可以计算每种覆盖的预期能量消耗，以便确定下一轮活动中选择哪一种覆盖。

# 3.1自适应遗传算法

遗传算法是一种采用随机搜索以优化选择结果的方法，在其搜索过程中，根据适者生存的理论，通过一系列选择、交叉、变异等进化操作，使得信息有规律的在个体之间相互交换，这其中引入了适应度的概念来判定个体的优劣，如果某个个体的适应度较高，它就会被继承到下一代；相反，如果某个个体的适应度较低，就会被淘汰。通过多次迭代运算，最终算法能找到最好的个体，得到最优解。

遗传算法虽说能通过一系列运算找到最优个体，但由于其计算参数是固定的，不能随着实际环境的变化作出动态调整，结果就是求出的最优解精度达不到要求。经过分析可知，影响其性能的主要因素在于，个体在适应环境的过程中，为了使自身的适应度更高，其遗传行为发生了意外的变化。由此，自适应遗传算法（adaptive genetic algorithms，AGA）被提出。在 AGA中，如果群体的适应度处于较为集中的状态，则交叉概率 $P _ { c }$ 和变异概率 $\boldsymbol { P _ { m } }$ 的值会变大；反之，如果群体的适应度处于较为分散的状态， $P _ { c }$ 和 $\boldsymbol { P _ { m } }$ 的值将会减小。两种参数概率根据式（3）

（4）自动调整自身的值：

$$
\begin{array} { r } { P _ { c } \mathrm { = } \left\{ \begin{array} { l l } { \displaystyle \mathrm { k } _ { 1 } ( f _ { \mathrm { m a x } } - f ^ { ^ { \prime } } ) / ( f _ { \mathrm { m a x } } - f _ { a \nu e } ) } & { f ^ { ^ { \prime } } \geq f _ { a \nu e } } \\ { \displaystyle \mathrm { k } _ { 2 } } & { f ^ { ^ { \prime } } < f _ { a \nu e } } \end{array} \right. } \\ { P _ { m } \mathrm { = } \left\{ \begin{array} { l l } { \displaystyle \mathrm { k } _ { 3 } ( f _ { \mathrm { m a x } } - f ) / ( f _ { \mathrm { m a x } } - f _ { a \nu e } ) } & { f \geq f _ { a \nu e } } \\ { \displaystyle \mathrm { k } _ { 4 } } & { f < f _ { a \nu e } } \end{array} \right. } \end{array}
$$

其中： $f _ { \mathrm { m a x } }$ 表示最高适应度， $f _ { a \nu e }$ 表示适应度的均值， $f ^ { ' }$ 表示多个交叉个体中的适应度比较高的个体的适应度， $f$ 表示产生变异的个体适应度，且 $0 < \mathbf { k } _ { 1 } , \mathbf { k } _ { 2 } , \mathbf { k } _ { 3 } , \mathbf { k } _ { 4 } \leq 1$ 。分析可知，自适应遗传算法利用固定值调整 $P _ { c }$ 和 $\boldsymbol { P _ { m } }$ ，能够改善较差的个体，但是固定值的使用有可能会导致较差个体中包含的优秀基因的缺失，容易使群体的多样性遭到破坏，算法容易陷入局部最优。为了减小局部最优出现的概率，本节提出一种改进的遗传算法。

# 3.2改进的自适应遗传算法

以种群适应度的密集度自动调节 $P _ { c }$ 和 $\boldsymbol { P _ { m } }$ 的值，给出计算公式为

$$
P _ { c } = \left\{ \begin{array} { l l } { \displaystyle { \mathrm { a r c s i n } ( \frac { f _ { a w } } { f _ { \mathrm { m a x } } } ) } } & { \displaystyle { \mathrm { a r c s i n } ( \frac { f _ { a w } } { f _ { \mathrm { m a x } } } ) } < \frac { \pi } { 6 } } \\ { \displaystyle { \frac { \pi } { 2 } } } & { \displaystyle { \mathrm { a r c s i n } ( \frac { f _ { a w } } { f _ { \mathrm { m a x } } } ) } } \\ { \displaystyle { \mathrm { k } _ { 1 } ( 1 - \frac { \mathrm { a r c s i n } ( \frac { f _ { a w } } { f _ { \mathrm { m a x } } } ) } { \frac { \pi } { 2 } } ) } } & { \displaystyle { \mathrm { a r c s i n } ( \frac { f _ { a w } } { f _ { \mathrm { m a x } } } ) \ge \frac { \pi } { 6 } } } \end{array} \right.
$$

$$
P _ { m } = \left\{ \begin{array} { c c } { \displaystyle { \mathrm { a r c s i n } ( \frac { f _ { a w } } { f _ { \mathrm { m a x } } } ) } } & { } \\ { \displaystyle { \mathrm { k } _ { 2 } ( 1 - \frac { \pi \mathrm { s i n } ( \frac { f _ { a w } } { f _ { \mathrm { m a x } } } ) } { \frac { \pi } { 2 } } ) } } & { \displaystyle { \mathrm { a r c s i n } ( \frac { f _ { a w } } { f _ { \mathrm { m a x } } } ) } < \frac { \pi } { 6 } } \\ { \displaystyle { \mathrm { a r c s i n } ( \frac { f _ { a w } } { f _ { \mathrm { m a x } } } ) } } & { } \\ { \displaystyle { \mathrm { k } _ { 2 } \frac { \pi } { 2 } } } & { \displaystyle { \mathrm { a r c s i n } ( \frac { f _ { a w } } { f _ { \mathrm { m a x } } } ) \ge \frac { \pi } { 6 } } } \end{array} \right.
$$

其中： $\arcsin ( \frac { f _ { a \nu e } } { f _ { \operatorname* { m a x } } } )$ 的使用能够使算法非线性地适应实际场景。如果ar $\sin ( \frac { f _ { a v e } } { f _ { \operatorname* { m a x } } } ) < \frac { \pi } { 6 }$ 成立，则意味着适应度平均值偏离最大适应度值， $\arcsin ( \frac { f _ { a \nu e } } { f _ { \operatorname* { m a x } } } )$ 的值小于 $\frac { \pi } { 6 }$ 越多，种群中个体的差异度越大，即种群越丰富，这时更容易通过自适应增加 $P _ { c }$ 的值选出优质个体，同时还能自适应减小 $\boldsymbol { P _ { m } }$ 的值以加快收敛速度。

同理，当arc $\sin ( \frac { f _ { a v e } } { f _ { \operatorname* { m a x } } } ) \geq \frac { \pi } { 6 }$ 成立时，意味着适应度平均值和最大适应度值相近， $\arcsin ( \frac { f _ { a \nu e } } { f _ { \operatorname* { m a x } } } )$ 的值大于 $\frac { \pi } { 6 }$ 越多，种群中个体的差异越不明显，即种群不丰富，此时自适应减小 $P _ { c }$ 的值并且自适应增加 $\boldsymbol { P _ { m } }$ 的值，更容易跳出局部最优，获得全局最优解。

综上所述，改进的自适应遗传算法的执行步骤如下：

a）生成初始群体，并初始化种群大小、收敛条件和染色体长度等基本要素。

b）计算种群中个体的适应度值。

c）计算收敛条件并判断，如果满足条件，就输出结果，不满足的话，转到步骤(4)。

d）如果arcsin $( \frac { f _ { a v e } } { f _ { \operatorname* { m a x } } } ) \geq \frac { \pi } { 6 }$ 成立，则表明种群适应度处于集中状态，则按照变异、交叉、选择的顺序执行操作；若不满足此条件，则表明种群适应度处于分散状态，种群表现出明显的多样性，应按照交叉、变异、选择的顺序执行操作。

e）返回步骤b)。

本文改进的遗传算法根据最优保存策略使每一代的最优个体得以保留，还能保证产生的最优个体不受交叉、变异等操作的影响，以确保算法的收敛性。

# 3.3覆盖头节点选择因素

在寻找合适的覆盖头时，需要考虑以下的网络属性：覆盖头与基站之间的距离；剩余电量；预期能量消耗。同时，选择下一轮的活动覆盖时会考虑预期能量消耗。覆盖的能量消耗 $E$ 包括组成覆盖所有传感器的总能量消耗。正常传感器节点 $s$ 的能量消耗 $E _ { s }$ 是以下情况所消耗的能量总和：

a）获取 $\mathbf { \xi } _ { l }$ 比特的数据所消耗的能量 $E _ { s } ^ { A } ( l )$ 口b）接受 $l ^ { \prime }$ 比特的数据所消耗的能量 $E _ { s } ^ { R } ( l ^ { \prime } )$ 。c）处理 ${ \mathbf { } } l ^ { \mathfrak { n } }$ 比特的数据所消耗的能量 $E _ { s } ^ { P } ( l ^ { \prime \prime } )$ 。d）将 ${ \mathbf { } } l ^ { \mathfrak { n } }$ 比特的数据传输距离为 $d$ 的长度所消耗的能量$E _ { s } ^ { T } ( l ^ { \prime \prime } , d ) \cdot$ 0

e）传感器从位置x移动到位置y所消耗的能量E(x,y)。由以上分析，可得：

$\begin{array} { r } { E _ { s } = E _ { s } ^ { A } \left( l \right) + E _ { s } ^ { R } \left( l ^ { \prime } \right) + E _ { s } ^ { P } \left( l ^ { \prime \prime } \right) + E _ { s } ^ { T } \left( l ^ { \prime \prime } , d \right) + E _ { s } ^ { M } \left( x , y \right) \left( 7 \right) } \end{array}$ 其中： $\boldsymbol { E } _ { s } ^ { R } = \boldsymbol { E } _ { i } + l ^ { \prime } \boldsymbol { E } ^ { * }$ ， $E _ { i }$ 表示待机能量开销， $E _ { s } ^ { T } = E _ { i } + l ^ { \prime \prime } d ^ { n }$ ，$n = 4$ 表示长距离传输， $n = 2$ 表示短距离传输， $\boldsymbol { E } ^ { * }$ 表示降低能量消耗的波速成形所消耗的能量。

假定一个一阶无线电模型，对于一个具有 $N _ { s }$ 个成员的覆盖，其能量开销是所有节点成员的传输、接受和移动的能量开销的总和，可以通过式（8）计算。

$$
E = \sum _ { i = 1 } ^ { N _ { s } - 1 } E _ { i , s } ^ { T } + \left( k E _ { s } ^ { R } + E _ { s , B } ^ { T } \right) + E _ { s } ^ { M }
$$

其中，第一项是从覆盖的普通成员传输到覆盖头传递信息所消耗的总能量， $E _ { s } ^ { R }$ 是头节点 $s$ 从成员节点处接收消息所消耗的能量， $\boldsymbol { E } _ { s , B } ^ { T }$ 是头节点 $s$ 传输聚合信息到基站所消耗的能量， $E _ { s } ^ { \scriptscriptstyle M }$ 是传感器移动所消耗的能量。在本文所提出的模型中，假定工作区域可以被基站完全控制。通过每个周期接收从传感器节点发来的数据，基站可以估计目标的移动速度和前进方向。

在计算一个传感器节点传输或者接收一个长度为 $l$ 比特的消息的能量时，本文使用了下面的方程用于计算传输能量消耗$\boldsymbol { E } ^ { T }$ 和接收能量消耗 $E ^ { R }$ ：

$$
E ^ { T } = E _ { e } + l d ^ { n }
$$

$$
\boldsymbol { E } ^ { R } = \boldsymbol { E } _ { e } + l \boldsymbol { E } ^ { * }
$$

其中， $E _ { e }$ 是待机能量消耗， $d$ 是发送端和接收端之间的距离。根据发射机和接收机之间的距离，传输能量消耗 $\boldsymbol { E } ^ { T }$ 与距离的不同阶数成比例，并且可以用合适的功率项 $n$ 来建模。在本文的模型中，使用 $n = 4$ 作为长距离传输，也就是从覆盖头节点到基站的传输， $n = 2$ 作为短距离传输，也就是从传感器节点到头节点的传输。式（10）中的 $\boldsymbol { E } ^ { * }$ 表示降低能量消耗的波速成形所

消耗的能量。

一个传感器 $s$ 移动能量开销 $E _ { s } ^ { \scriptscriptstyle M }$ 依赖于能量感知距离 $\overrightarrow { \varepsilon D }$ ，而 $\overrightarrow { \varepsilon D }$ 可以通过起始点 $x$ 到终点 $y$ 的欧氏距离 $\varrho _ { d }$ 计算得到，计算时还应考虑环境中的障碍，比如树或建筑物。每个障碍 $h$ 都具有一个权重 $w$ 表示其消耗传感器节点能量的能力。令$W = \{ w _ { 1 } , w _ { 2 } , . . . , w _ { n } \}$ ，因此对于一个传感器 $s$ ，其感测范围为 $f$ 中包含 $\mathbf { \Omega } _ { n }$ 个障碍 $h$ ，可以表示为

$$
\overrightarrow { \varepsilon D } _ { s } = \rho _ { d } \left\{ x , y \right\} + \sum _ { i = 0 } ^ { n } h _ { i } w _ { i }
$$

可以通过式（12）得到一个节点 $s$ 的剩余能量：

$$
\overset { \cdot } { E } _ { s } = E \left( 0 \right) - \sum _ { t = 1 } ^ { T } \left( E _ { s } ^ { T } \left( t \right) + E _ { s } ^ { R } \left( t \right) + E _ { s } ^ { M } \left( t \right) \right)
$$

其中： $E ( 0 )$ 表示节点的初始能量， $\mathbf { \Phi } _ { t }$ 表示传输阶段网络寿命。需要注意的是，除非一个节点在一个周期内成为了覆盖头，否则它的接受能量消耗 $E ^ { R }$ 始终为0。在实际应用中，每个节点的剩余能量都在每轮结束后进行更新。

# 3.4染色体编码

染色体中的每个基因代表该领域中的传感器节点。基因的值可以是1或0，其中1表示相应的节点作为覆盖头，0表示非头节点。

改进的遗传算法通过交叉和变异操作产生新的染色体，并对每个染色体的适应性进行评估。交叉操作是通过用交叉概率确定的两个随机选择的染色体来进行的一种调节操作。如果没有交叉，父代的染色体信息将会不变地复制给后代。改变交叉概率改变了搜索过程的进化速度。在实际应用中，交叉概率的值接近于1。

突变操作涉及改变染色体内随机选择的基因的值。类似地，算法使用突变概率来调节突变的表现。与交叉概率不同，突变概率通常相当小。变异操作可以创造全新的物种，这是摆脱局部最优的手段。

# 4 仿真分析

# 4.1实验设置

表1列出了实验中所使用的网络参数，使用MATLABR2014a对算法进行仿真。在本文的实验中，网络寿命从网络开始覆盖第一个目标节点开始计算。每个实验均进行了40次，并统计了40次的平均性能。

# 4.2仿真结果分析

本小节所有的实验都是在动态场中进行的，以测量传感器移动性对覆盖时间的影响。

图2描述了在 $\scriptstyle \mathrm { K } = 3$ 的情况下，传输周期数与覆盖目标百分比的关系，其中节点被随机放置在一个 $1 0 0 \mathrm { m } \times 1 0 0 \mathrm { m }$ 环境覆盖10个目标。如图2中所展示的那样，随着网络传输的继续，活动节点的数量逐渐减少，这是因为更多的节点耗尽了它们的能量。和FDSSP 算法、FDA算法以及VP_NL算法相比，相同情况下，本文算法能够获得更好的覆盖目标百分比，本文所提出的模型通过使传感器移动来增加了目标的覆盖时间，从而延长了网络寿命。

表1网络参数  

<html><body><table><tr><td>属性</td><td>值</td></tr><tr><td>节点数量</td><td>100</td></tr><tr><td>初始化节点能量</td><td>1J</td></tr><tr><td>待机状态能量</td><td>50 nJ/bit</td></tr><tr><td>数据聚合能量</td><td>5 nJ/bit</td></tr><tr><td>放大能耗（覆盖头到基站）</td><td>d≥d 10 pJ/bit/m²</td></tr><tr><td></td><td>d<do 0.0013 pJ/bit/m²</td></tr><tr><td>放大能耗（节点到覆盖头)</td><td>d≥d Ejs /10=Efs1</td></tr><tr><td>数据包尺寸</td><td>d<d Emp /10= Emp1 400 bits</td></tr></table></body></html>

![](images/54be15112e1153684a19eb4fa4b1f3c42ee04fc917bef1e9b6099cce3e6377cc.jpg)  
图2 $K = 3$ 时传输周期数和覆盖目标百分比的关系

图3描述了传感器的感测范围与平均移动距离的关系。在这个实验中，使用了50个传感器，其中K的值分别为1，2，3。在第一次实验中，传感器分布在 $1 0 0 \mathrm { m } \times 1 0 0 \mathrm { m }$ 的范围中（见图3（a))，而第二次的实验中，传感器分布于 $2 0 0 \mathrm { m } \times 2 0 0 \mathrm { m }$ 的范围内（见图3(b)）。

如图3所展示的那样，传感器的感测范围会对平均移动距离产生重要影响，因为同一时刻有更多的传感器覆盖相同的区域，这意味着感测范围越大，越多的目标被同一个传感器节点覆盖。因此，便不再需要额外的移动传感器去覆盖一个相同的目标。

![](images/c24a49bdc313fcd53d9bb8afced5a4b1f0b3c9df1fd1508b5b29d9183b81cb55.jpg)  
图3传感器的感测范围和平均移动距离的关系

图4描述了传感器的感测范围与平均剩余能量的关系，T表示待覆盖目标的个数。由图可知，在同样的情况下，感测范围较大的传感器比其他传感器消耗更多的能量。相应地，传感器节点的平均剩余能量随着感测范围的减小而增加。图4用两种不同的情况证明了这个事实。在图4（a）中，50个移动传感器节点分布在 $1 0 0 \mathrm { m } { \times } 1 0 0 \mathrm { m }$ 的工作范围中，图4（b）中，则在该范围内分配50个静止的传感器进行相同的实验。

![](images/499ac792ca2fca4ad32acdc06ca874e2f176d7d2e563454eb131c2701c7c45d4.jpg)  
图4传感器感测范围和平均剩余能量的关系

网络吞吐量全权取决于传感器到基站传输的数据量。因此，网络的寿命越长，网络的吞吐量越高。图5所示描述了传感器的周期数与数据包数量的关系。在实验中，100个移动的传感器节点被均匀地分布在（a) $1 0 0 \mathrm { m } \times 1 0 0 \mathrm { m }$ 和（b) $2 0 0 \mathrm { m } \times 2 0 0 \mathrm { m }$ 两种范围内。由图5可以看出，随着周期数的增加，数据包数量也在增加，网络吞吐量与K值成反比。换句话说，随着覆盖等级的提高，网络的吞吐量逐渐下降。这是因为提高了覆盖等级之后，传感器需要消耗更多的能量来传输收集到的数据，因此，会降低网络的使用寿命，从而降低了网络的吞吐量。

![](images/140738b6a37e370341b63fa97e882327ec38fbdcc03d6e89f6c5717dd2461793.jpg)  
图5周期数和数据包数量的关系

# 5 结束语

本文提出了两种优化传感器网络的方法，一种是基于遗传算法的覆盖形成方法，可以创建所有可能的传感器覆盖，另外一种是在不同传感器覆盖之间切换的管理方法，可以最大化网络寿命。本文所提出的模型使用改进的遗传算法来优化无线传感器网络的覆盖要求，以在能量资源有限的情况下尽可能长时间地连续监测指定的目标；本文的模型考虑了移动传感器的连续和变速运动，以保持所有目标都同时处于覆盖范围内。仿真结果证明在使用移动节点的情况下，改进方法的网络寿命和网络吞吐量都有明显提高。

# 参考文献：

[1]明勇，王华军.WSN中考虑节点磨损的分布式自稳定网络寿命优化算法[J].计算机应用研究,2016,33(3):827-831.

[2] 李钟翔，陈蕾.一种基于人工鱼群算法的 K 覆盖WiFi 热点安置方案 [J]．华东师范大学学报：自然科学版,2015,35(1):151-160.   
[3]Wan X,Wu J,Shen X.Maximal lifetime scheduling for roadside sensor networks with survivability, \$k\$[J].IEEE Trans on Vehicular Technology, 2015,64(11): 5300-5313.   
[4]Slijepcevic S,Potkonjak M.Power efficient organization of wireless sensor networks [Cl//Proc of IEEE International Conference on Communications. 2001.   
[5]Yang Q, Guinduiz D. Variable-power scheduling for perpetual target coverage in energy harvesting wireless sensor networks [C]//Proc of International Symposium on Wireless Communication Systems.2015.   
[6] 谭跃，谭冠政，邓曙光．基于遗传交叉和多混沌策略改进的粒子群优化 算法[J].计算机应用研究,2016,33(12):3643-3647.   
[7]Zahedi Z M,AkbariR, Shokouhifar M,etal. Swarm intelligence based fuzzy routing protocol for clustered wireless sensor networks [J].Expert Systems with Applications,2016,55(1): 313-328.   
[8]Liao WH, Kao Y,Li Y S.A sensor deployment approach using glowworm swarm optimization algorithm in wireless sensor networks [J]. Expert Systems with Applications,2011,38(10):12180-12188.   
[9]李亚洲，郑向伟，肖宪翠．合作型协同多目标群搜索算法[J].小型微 型计算机系统,2016,37(3):567-571.   
[10] Cardei M,Du D Z. Improving wireless sensor network lifetime through power aware organization [J].Wireless Networks,20o5,11(3):333-340.   
[11]杜晓玉，孙力娟，郭剑，等．异构无线传感器网络覆盖优化算法[J]. 电子与信息学报,2014,36(3):696-702.   
[12]谢承旺，邹秀芬，夏学文，等．一种多策略融合的多目标粒子群优化算 法[J]．电子学报,2015,43(8):1538-1544.   
[13] Xue W,MaJJ, Sheng W, et al.Distributed particle swarm optimization and simulated annealing for energy-eficient coverage in wireless sensor networks [J]. Sensors,2007,7(5): 628-648.   
[14]Huang YY,LI Keqing.Coverage optimization of wireless sensor networks based on artificial fish swarm algorithm [J].Application Research of Computers,2013,30 (2): 554-556.   
[15] Wang G,Guo L,Duan H,et al.Dynamic deployment of wireless sensor networks by biogeography based optimization algorithm [J].Journal of Sensor& Actuator Networks,2012,1(2): 86-96.