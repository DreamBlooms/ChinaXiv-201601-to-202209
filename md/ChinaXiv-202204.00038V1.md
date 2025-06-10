# 基于局部并行搜索的分布式约束优化算法框架

石美凤，杨海，陈媛，肖诗川，廖鑫，何颖(重庆理工大学 计算机科学与工程学院，重庆 400054)

摘要：针对当前局部搜索算法在求解大规模、高密度的分布式约束优化问题(DCOPs)时，求解困难且难以跳出局部最优取得进一步优化等问题，提出一种基于局部并行搜索的分布式约束优化算法框架(LPOS)，算法中Agent 通过自身的取值并行地搜索局部所有邻居取值来进一步扩大对解空间的搜索，从而避免算法过早陷入局部最优。为了保证算法的收敛性与稳定性，设计了一种自适应平衡因子K来平衡算法对解的开发和继承能力。并在理论层面证明了并行搜索优化算法可以扩大对解空间的搜索，自适应平衡因子K可以实现平衡目的。综合实验结果表明，基于该算法框架的算法在求解低密度和高密度DCOPs时性能都优于目前最新的算法。特别是在求解高密度DCOPs中有显著的提升。

关键词：分布式约束优化问题；多智能体系统；局部搜索算法；并行搜索优化 中图分类号：TP13 doi:10.19734/j.issn.1001-3695.2022.02.0035

Local parallel search framework for distributed constraint optimization problems

Shi Meifeng, Yang Hai†, Chen Yuan, Xiao Shichuan, Liao Xin, He Ying (College of Computer Science& Engineering,Chongqing University of Technology,chongqing 40054,China)

Abstract: Inorder to solve the problem that it is diffcult togetoutof thelocal optimum toachieve further optimization in large-scale dense Distributed Constraint Optimization Problems(DCOPs）.This paper proposed a local paralel search framework(LPOS)for solving algorithms of DCOPs.In LPOS,the Agent searches all the value assignmentsof its local neighbors in parallaccording toits curent valueassgnment to further expand thesearchofsolutionspace,soas toavoid thealgorithmfallng intolocaloptimumprematurely.Inordertoensuretheconvergenceofthealgorithm,tis paperdesigned an adaptive equilibrium factorK tobalance the explorationand exploitation abilityofthe DCOPssolving algorithms.At the theoreticalanalysis,it proved that the LPOS can expandthe searchof solution space andthe Kcanachieve thebalance.The experimentalresultsdemonstrate that theperformanceof the proposed LPOS isbetter thanthe-state-of-the-artalgorithms in both lowdensityand high densitySpecificall,LPOS significantly superior to thecompetitors when solving high density DCOPs.

Keywords:distributed constrainedoptimization problem;multi-agentsystem；local search algorithm;local paralel optimization

# 0 引言

随着分布式协同运作的人工智能的出现，多智能体系统(MAS)[I已经成为人工智能的一个重要分支。而分布式约束优化问 题(Distributed Constraint Optimization Problems，DCOP)[2]作为智能体协同调度的一个重要框架，是解决分布式智能系统建模和目标之间协同优化的关键技术。DCOP强调通过局部智能体之间的信息交互以达到全局最优，且具有很强的容错性以及很高的并行性，适用于求解规模大、难度高的组合问题，以分布并行计算的方式快速有效地解决这些问题。目前在任务调度[3]、传感器网络[4.5]、微电网优化控制等领域得到了广泛的应用。然而，由于DCOPs是NP难问题[7]，随着问题规模和复杂程度的增加，完备算法所产生的指数级通信和时间而导致了其应用的局限性。而非完备算法则是通过放弃找到问题的最优解，通过较少的通信和时间成本来寻找次优解，如此便能够很好的应用于大规模的分布式应用模型问题。因此，在近几年非完备算法备受青睐。

非完备算法通常包括以下三类：基于局部搜索的算法[8-12]、基于推理的算法[13\~18]和基于采样的算法[19\~22]。而局部搜索算法是DCOPs 中最流行的非完备算法，其每个Agent 都是根据局部约束条件和从所有相邻Agent接收到的信息进行优化的，例如DSA[23]、DBA[24]和MGM[25]等。然而，局部搜索算法又具有容易陷入局部最优的缺点。近年来，Chen等人提出一种基于遗传算法(GA-based framework,LSGA)[26]的框架,利用遗传算子的能力改进局部搜索算法。但交叉算子在优化过程中破坏了交叉块中Agent与邻居之间的协调性，使得Agent只能依靠自身的局部信息(局部代价以及取值频次)指标来衡量当前解的优劣，仍然不能避免算法陷入局部最优。而Yu 等人提出了一种局部决策(Partial Decision Scheme,PDS)[27]的框架，该算法框架通过忽略其中一个邻居来搜索有希望的决策分区，从而提高Agent的局部利益。然而在大规模高密度的问题中，Agent周围会有大量邻居，此时PDS起到的效果甚微，难以取得进一步的优化。

因此，针对在大规模高密度配置下，分布式约束优化问题难以被进一步优化的问题，本文提出了一种基于局部并行搜索策略(LocallParallel Optimization Search,LPOS)的分布式约束优化算法框架，该框架根据Agent自身取值发送给周围所有邻居并行地同时搜索自身值域以寻找到最小代价取值来进一步扩大算法对解空间的探索，从而提升算法解的质量。

# 1 介绍

# 1.1分布式约束优化问题

分布式约束优化问题(Distributed Constraint OptimizationProblems,DCOP)由一个四元组 ${ < } \mathrm { A }$ ，X，D, $\mathrm { F } >$ 表示，其中：（204号 $A = \left\{ \mathsf { a } _ { 1 } , a _ { 2 } , \cdots a _ { m } \right\}$ 为 Agent的集合; $\frac { { \underline { { \mathrm { r \_ m a x - r \_ c u r r e n t } } } } } { \mathrm { r \_ m a x } }$ 为变量的集合，并且变量由所属 Agent 进行赋值，每一个Agent负责一个或多个变量的取值； Ci-Cmi.K<i-Cmin为一个有限值域的集合，Di为X集合中对应变量xi的取值值域； $F = \{ f _ { 1 } , f _ { 2 } , \cdots f _ { k } \}$ 为Agent之间约束关系的集合，每一条约束对应着非负映射$f _ { i } : D _ { i _ { 1 } } \times \dots \times D _ { i _ { k } } \to R ^ { + }$ ，它包含了当前约束的所有变量组合以及其对应的代价。

DCOP也可以用约束图来直观地表示。在约束图中每个变量由其对应的Agent控制赋值，每个Agent仅知道关于控制变量上的约束；各Agent在赋值时必须相互协调，使全局目标(如约束函数之和)最优。DCOP 可抽象描述为由节点和边组成的约束图，每个节点对应一个Agent，边表示节点之间存在约束关系，约束函数表示约束各变量的任意赋值组合的收益(代价)。

如图1表示了一个二元约束关系的DCOP约束图，其中变量r_max，每一个Agent 控制一个变量 $X _ { i }$ $f _ { i j }$ 表示 $X _ { \mathrm { i } }$ 和 $X _ { j }$ 之间的约束函数。

![](images/717d5eee2787788e7619e093590501a9f079306d6d2c7a8c39301d28e213be7a.jpg)  
图1DCOP实例Fig.1Example of DCOP

由于Agent可以控制一个或者多个变量，为了便于理解与讨论，本文假设每个Agent只控制一个变量 $X _ { i }$ ，它仅知道与该变量相关的约束函数。在DCOP中，每个Agent与邻居共享约束函数，Agent之间相互协调找到使4个约束函数之和最优的变量赋值，因此DCOP的解可以被定义为

$$
\boldsymbol { \sigma } ^ { * } = \underset { d _ { i } \in D _ { i } } { \arg \operatorname* { m i n } } \sum _ { f _ { i j } \in F } f _ { i j } ( x _ { i } = d _ { i } , x _ { j } = d _ { j } )
$$

# 1.2DSA算法与MGM2算法

随机搜索算法(DSA)的基本思想是按照一个预先设定的概率 $\mathrm { ~ \bf ~ P ~ }$ 来进行决策。首先，Agent将控制变量进行随机取值$X _ { i }$ ，并且将取值发送给周围所有邻居，然后各个Agent进行重复迭代。在每一次迭代中，Agent先搜集周围邻居发送的值，然后根据邻居的取值搜索自身值域，并计算取值 $X _ { i }$ 时局部代价与取值 $X _ { j }$ 时局部代价差值 $\Delta$ ；若 $\Delta \geqslant 0$ 且随机生成数小于P，则更新值并发送给周围邻居。通过DSA算法能够很快找到次优解，但也极容易陷入局部最优，导致求解质量不好。

而 MGM2算法是一种在策略上比较保守的算法，通过两个Agent组合成联合体的方式进行决策，只有Agent之间收益最大的Agent才能改变自身取值，否则只能等待下一轮的决策。MGM2 算法与DSA算法思想类似，Agent 将控制变量进行随机取值 $X _ { i }$ ，然后进行迭代。在每一次迭代中，Agent先搜集周围邻居发送的值，然后选取能够让Agent局部代价降低 $\Delta _ { \mathrm { i } }$ 最多的值；并将 $\Delta _ { \mathrm { i } }$ 发送给周围邻居；若 $\Delta { > } \Delta _ { \mathrm { i } }$ ，则更新值并发送给周围邻居。MGM2算法虽能在一定程度上改善算法陷入局部最优的问题，但也造成了组合体之间太过关注自身代价而导致算法不能进一步找到更到的解。

# 1.3LSGA 框架与 PDS 框架

基于遗传算法的框架[26](LSGA)利用遗传算子(包括选择算子、交叉算子和变异算子)的能力改进局部搜索算法。选择算子由每个个体执行，根据一个适应度函数来评估其基因，并通过适应度函数去取决个体的局部效益和基因值的出现频率。然而由于交叉算子破坏了交叉块中Agent与邻居之间的协调性，导致Agent只能通过自身局部信息进行评估当前解的质量，因此基于遗传算法框架并不能避免算法陷入局部最优。

而局部决策框(PDS)[27]架是当算法陷入局部最优时，通过Agent 忽略局部其中一个邻居的策略，以扩大搜索解空间而进一步寻求更优的解。但当面对大规模、高密度的DCOPs问题时，仅通过忽略局部一个邻居的策略已难以取得进一步的优化。

因此，本文针对当前局部搜索算法在求解大规模、高密度的DCOPs问题中，难以得进一步优化等问题，提出了一种基于局部并行搜索的分布式约束优化算法框架(LPOS)。

# 2 局部并行搜索优化算法框架算法步骤及实例分析

# 2.1算法框架步骤

局部并行搜索优化算法框架

a）随机搜索算法初始化；b）检测Agent处于局部最优状态，并计算并行搜索优化  
概率 $P O P _ { i }$ ·c）生成随机数 $a _ { i } \in ( 0 , ~ 1 )$ d)若 $a _ { i } { < } P O P _ { i }$ ，则进行并行搜索优化；e）随机选择一个邻居 $x _ { b }$ f将 $x _ { b }$ 取值发送给Agent，并搜索自身值域选择与 $x _ { b }$ 之  
间代价最小值 $\nu _ { i }$ ，然后发送给周围所有邻居；g）计算Agent局部代价增益 $g _ { i }$ h)若 $\mathrm { g } _ { \mathrm { i } } { > } 0$ ，则将更新为Agent当前取值；i)若 $\mathrm { g } _ { \mathrm { i } } { \leqslant } 0$ ，则进一步计算决策优化消息 $\mathrm { { V } ^ { * } \mathrm { { m } } }$ j）计算全局代价增益 $\mathbf { g } _ { \mathrm { c } }$ k)若 $g _ { c } { > } 0$ ，则更新为Agent当前取值，否则重复进行 $\mathbf { c } { \sim } \mathbf { j }$

根据步骤 b)，当检测到处于局部最优状态(ILB)[27]时，Agent根据式(6)计算并行优化概率 $P O P _ { i }$ 进行局部并行搜索；并行优化概率 $P O P _ { i }$ 通过式(2)局部代价水平Li与当前迭代次数水平以及式(7)平衡因子K的乘积计算；当求得的代价较大时，局部代价水平会相对较大，且平衡因子K也会较大，迭代次数水平仅为控制进程收敛的线性不变函数，故最终的 $P O P _ { i }$ 会较大，使得当前Agent有更大的概率改变自身的取值，探索求取更优的解，以此降低 $P O P _ { i }$ 的值来稳定解的质量。

$$
L _ { \mathrm { i } } = \frac { c _ { \mathrm { i } } - c _ { \mathrm { m i n } } } { c _ { \mathrm { m a x } } - c _ { \mathrm { m i n } } } , c _ { \mathrm { m a x } } \neq c _ { \mathrm { m i n } }
$$

$$
\begin{array} { l } { \displaystyle \mathrm { c } _ { \mathrm { i } } = \sum _ { j \in n e i g h b o u r I D } c _ { i j } \left( x _ { i } = a _ { i } , x _ { j } = a _ { j } \right) , } \\ { \displaystyle a _ { i } \in D _ { i } , a _ { j } \in D _ { j } } \end{array}
$$

$$
\begin{array}{c} { \bf c } _ { \mathrm { m i n } } = \operatorname* { m i n } _ { a ^ { \prime } _ { i } \in D _ { i } } \sum _ { \substack { j \in n e i g h b o u r I D } } c _ { i j } \left( x _ { i } = a ^ { \prime } _ { i } , \right.  \\ { \left. \left( x _ { i } = a ^ { \prime } _ { i } , x _ { j } = a ^ { \prime } _ { j } \right) \right) } \end{array}
$$

$$
{ \bf c } _ { \mathrm { m a x } } = \operatorname* { m a x } _ { a _ { i } ^ { \prime } \in D _ { i } } \sum _ { j \in n e i g h b o u r I D } c _ { i j } \left( { x _ { i } = a _ { i } ^ { \prime } , x _ { j } = a _ { j } ^ { \prime } } \right)
$$

其中， $a _ { i }$ 和 $a _ { j }$ 分别是 $x _ { i }$ 和它的邻居 $x _ { j }$ 的当前值。 $c _ { i j }$ 是 $x _ { i }$ 当前解的局部代价。式(4)与式(5)中， $c _ { m i n }$ 和 $c _ { m a x }$ 分别是 $x _ { i }$ 的局部代价的最大值和最小值， $\boldsymbol { a } _ { \ i } ^ { \prime }$ 的初始值为原始算法处于ILB时的取值。neighbourID是 $x _ { i }$ 周围所有邻居。由式(2)可知， $L _ { i }$ 越大，当前的局部代价越差。

$$
P O P _ { \mathrm { i } } = L _ { \mathrm { i } } \cdot { \frac { \mathrm { r } _ { \mathrm { - } } \mathrm { m a x } \mathrm { - } \mathrm { r } _ { \mathrm { - } } \mathrm { c u r r e n t } } { \mathrm { r } _ { \mathrm { - } } \mathrm { m a x } } } \cdot K
$$

$$
K = \left( \frac { r _ { - } \operatorname* { m a x } - r _ { - } c u r r e n t } { r _ { - } \operatorname* { m a x } } \right) ^ { L _ { i } }
$$

其中，r_current 和 $\mathrm { \ r \ m a x }$ 分别表示当前迭代次数和最大迭代次数。最大迭代次数被用作局部搜索的终止条件。由式(6)与(7)可知， $x _ { i }$ 的 $L _ { i }$ 越大，局部并行搜索优化的概率越大， $P O P _ { i }$ 的影响会随着迭代次数的增加而逐渐减弱。

K是自适应平衡因子，平衡因子的作用是平衡优化过程中算法的探索和对当前期望解的开发能力。根据算法求解时的代价大小自适应地动态调整K值的大小。根据式(7)可知，随着迭代次数的增加，K值总体趋势逐渐减小，有利于算法收敛与稳定，而局部代价水平的大小使算法能够自适应的调整算法对解的探索与开发的能力。

根据步骤d)，当 $x _ { i }$ 处于ILB以及满足 $P O P _ { i }$ 时，进行并行搜索优化。

根据步骤e)，首先， $x _ { i }$ 随机选择它的一个邻居。然后， $x _ { i }$ 分别通过式(8)\~(10)计算新值 $a _ { i \setminus a _ { j } ^ { \prime } } ^ { \prime }$ 和最小局部代价 ${ \bf c } _ { \mathrm { m i n } } ^ { \prime }$ 。 $\boldsymbol { a } _ { \ i } ^ { \prime }$ 和 $\boldsymbol { a ^ { \prime } } _ { j }$ 分别是 $x _ { i }$ 和 $x _ { j }$ 对应于 $ { \mathbf { c } } _ { \mathrm { m i n } } ^ { \prime }$ 的值。

$$
\mathbf { a } _ { i } ^ { \prime } = \underset { i \neq D _ { i } } { \arg \operatorname* { m i n } } \ \sum _ { \underset { j \neq b } { j \in n e i g h b o u r I D } } c _ { i j } \left( x _ { i } = a _ { i } ^ { \prime } , x _ { j } = a _ { j } ^ { \prime } \right)
$$

$$
\mathbf { a } _ { \ j } ^ { \prime } = \mathop { \bf { a r g } } _ { \ j \in n e i g h b o u r I D } c _ { i j } \left( x _ { i } = a _ { \ i } ^ { \prime } , x _ { j } = a _ { \ j } ^ { \prime } \right)
$$

$$
\mathrm { \bf ~ c } _ { \mathrm { \tiny ~ m i n } } ^ { \prime } = \sum _ { \stackrel { j \in n e i g h b o u r I D } { j \ne b } } c _ { i j } \left( x _ { i } = \mathrm { \bf a } _ { i } ^ { \prime } , x _ { j } = a _ { \mathrm { \tiny ~ j } } ^ { \prime } \right) +
$$

$$
c _ { i b } \left( x _ { i } = a _ { \ i } ^ { \prime } , x _ { j } = x _ { b } \right)
$$

$$
{ \bf g } _ { \mathrm { i } } = c _ { i } - c _ { \mathrm { ~ \tiny ~ m i n } } ^ { \prime }
$$

根据步骤 $\mathrm { g } ) \sim$ 步骤j)， $x _ { i }$ 通过式(11)计算局部代价的增益$g _ { i }$ ，并通过决定是否将其当前值更改为 $\boldsymbol { a } _ { \ i } ^ { \prime }$ ；如果 $g _ { i }$ 不大于0,则进行计算决策信息 $V _ { \mathrm { ~ \scriptsize ~ m ~ } } ^ { * }$ 与全局代价增益 $g _ { c }$ ，若 $g _ { c } { < } o$ 则意味着 $x _ { i }$ 选择邻居 $x _ { b }$ 进行局部并行搜索优化不能改善其状态， $x _ { i }$ 将保持当前值，然后重复步骤c)\~步骤j)。

其中，决策信息 $V _ { \mathrm { ~ \scriptsize ~ m ~ } } ^ { * }$ 根据式(12)改变其值 $V _ { \mathrm { ~ \bf ~ k ~ } } ^ { * }$ ，通过选择邻居 $x _ { b }$ 之外的每个邻居的值来搜索其解空间，从而找到邻居 $x _ { j }$ ，使 $x _ { i j }$ 的代价最小。然后， $x _ { i }$ 通过式(13)(14)计算 $x _ { i }$ 的新值 $\boldsymbol { a } _ { \ i } ^ { \prime }$ 和全局代价 $g _ { c }$ 。

$$
\begin{array} { l } { { \mathrm { V ^ { * } } _ { k } = \displaystyle \arg \operatorname* { m i n } _ { j \in n e i g h b o u r I D } \sum _ { a ^ { \prime } i \in D _ { i } } c _ { i j } \left( V ^ { * } _ { m } = a ^ { \prime } _ { i } , x _ { j } = a ^ { \prime } _ { j } \right) + } } \\ { { \mathrm { } \operatorname* { m i n } _ { a ^ { \prime } j \in D _ { j } } c _ { i j } \left( V ^ { * } _ { m } = a ^ { \prime } _ { i } , x _ { j } = a ^ { \prime } _ { j } \right) } } \end{array}
$$

$$
\mathbf { a ^ { \prime } } _ { i } = \arg \operatorname* { m i n } _ { a _ { i } ^ { \prime } \in D _ { i } } c _ { i j } \left( x _ { i } = a _ { i } ^ { \prime } , x _ { j } = a _ { j } ^ { \prime } \right)
$$

$$
\begin{array} { l } { \displaystyle \mathbf { g } _ { \mathrm { c } } = \sum _ { { j \in n e i g h b o u r I D } } c _ { i j } \left( x _ { i } = a _ { i } , x _ { j } = a _ { j } \right) - } \\ { \displaystyle \left( \sum _ { j \in n e i g h b o u r I D } ^ { \sum } c _ { i j } \left( x _ { i } = a _ { i } ^ { \prime } , x _ { j } = a _ { j } ^ { \prime } \right) \right) } \\ { \displaystyle \left( \sum _ { j \neq b } \left( x _ { i } = a _ { i } ^ { \prime } , x _ { j } = x _ { b } \right) \right. } \end{array}
$$

# 2.2局部并行搜索算法框架实例

以图1为例来说明本文所提策略的基本思想。假设所有的 Agent在多轮之后处于ILB状态，且取值分配都为1，并在下一轮将它们的值1发送给它们的邻居。

若此时进行局部决策PDS，当 $x _ { I }$ 选择邻居 $x _ { 3 }$ 进行忽略，以寻求打开解空间时，本文发现当 $\scriptstyle x _ { I } = 1$ 与 $\scriptstyle x 3 = 1$ 时已经是最小值了，已经无法跳出当前取值改变现状。因此本文尝试采用局部并行搜索策略(LPOS)，以迭代次数800为终止条件[24]，将其邻居即neighbourID $= \{ x _ { I } , x _ { 2 } \}$ 进行局部并行搜索以达到进一步扩大对解空间的探索，从而寻找到更小的局部代价。也就是说，对于 $x _ { 3 }$ 的局部而言，通过式(4)(5)分别计算出局部最大值 $\scriptstyle c _ { m a x } = 4 + 4 + 5 = 1 3$ 与最小值 $c _ { m i n } { = } 1 + 1 + 1 { = } 3$ ， $x _ { I }$ 与 $x _ { 2 }$ 同时收到取值 $x _ { 3 } = 1$ ，然后分别并行的搜索遍历自身值域，寻找最小代价取值。对于图1，通过式(3)计算代价，当 $\scriptstyle x _ { I } = 1$ 时代价为1，当 $\scriptstyle x _ { I } = 2$ 时代价为2，故此时会选择 $\scriptstyle x _ { I } = 1$ ；同时计算当 $x _ { 2 } { = } 1$ 时代价为2，当 $\scriptstyle x _ { 2 } = 2$ 时代价为1，故此时会选择 $x _ { 2 } { = } 2$ 。一轮局部并行搜索完成，通过式(8)(9)计算可知最终局部取值为：$\scriptstyle x _ { I } = 1$ ， $\scriptstyle x _ { 2 } = 2$ ， $\scriptstyle x 3 = 1$ ；代价 $\cot 1 + 3 + 1 = 5$ ，通过式(2)计算$L _ { 1 } = \frac { 5 - 1 } { 1 3 - 1 } = 0 . 3 3 3$ ，通过式(7) $K = \left( { \frac { 8 0 0 - 1 } { 8 0 0 } } \right) ^ { 0 . 3 3 3 } = 0 . 9 9 9 5 8 3$ ，通过式(6)计算可知 $P O P _ { \mathrm { i } } = 0 . 3 3 3 ^ { * } 0 . 9 9 8 7 5 ^ { * } 0 . 9 9 9 5 8 3 = 0 . 3 3 2 4$ ，然后再通过式(10)计算 $\scriptstyle x _ { 4 } = 2$ 时最终代价为 $5 + 1 = 6$ ，根据式(11)计算可知当所有Agent取值为1时， $\mathrm { g } _ { \mathrm { i } } = 4 { + } 1 { + } 2 { + } 2 { - } 6 { = } 3 { > } 0$ ；根据算法步骤 d)可知，若随机生成数 $a _ { i } { \geq } P O P _ { i } { = } 0 . 3 3 2 4$ ，则将当前所有Agent取值为1更改为 $\scriptstyle x _ { I } = 1$ ， $x _ { 2 } { = } 2$ ， $\scriptstyle x _ { 3 } = 1$ ， $x _ { 4 } = 2$ 。使得算法能够跳出当前局部最优，进行进一步优化。

# 3 实验分析

为了验证LPOS算法框架的有效性与优越性，本文在随机DCOP、图着色问题以及无尺度网络问题中与基于PDS框架的算法、基于LSGA框架的算法以及GDBA算法进行性能比较分析。考虑到DCOP非完备算法的随机性，实验设计将对每一种模式生成的问题进行30次独立求解，并取30次统计结果进行对比。为了保证实验的公平性，根据文献[27]，本文对于所有的实验都统一采用800次迭代次数作为终止条件，具体实验配置[24,26,27]如表1所示。

表1实验参数配置  
Tab.1Experimental parameter configuration   

<html><body><table><tr><td>问题类型</td><td>值域</td><td>问题密度</td><td>Agent数量</td></tr><tr><td>随机DCOP</td><td>10</td><td>0.1(低) 0.6(高)</td><td>150</td></tr><tr><td>无尺度网络</td><td>10</td><td>3(低) 10(高)</td><td>150</td></tr><tr><td>图着色</td><td>3</td><td>0.05</td><td>200</td></tr></table></body></html>

为了方便对比LPOS_DSA、LPOS_MGM2 和PDS_DSA、PDS_MGM2[27]以 及LSGA_DSA、LSGA_MGM2[27]和GDBA[27算法之间性能的差异，图 $2 { \sim } 6$ 给出了这7种算法在三类问题中的收敛曲线图以及表2、3分别为LPOS_DSA与LPOSMGM2较其他算法在性能上的提升率。

![](images/73cca90a289004cb534a3e7164aff1ffcae9ec7acca7ff47e51d4353651cd39f.jpg)  
图2各算法在低密度随机DCOP中收敛曲线图  
Fig.2Comparison of each algorithm on sparse configuration of random dcops

![](images/434f296386409a0e20040928e3eb38875ee8eca3672f459379a3dadbbf3623a7.jpg)  
图3各算法在高密度随机DCOP中收敛曲线图

![](images/7aa4939c68ca24e352641bcb1a879042667226dda03cef085f858f26f725c115.jpg)  
Fig.3Comparison of each algorithm on dense configuration of random dcops

![](images/30425aced2e35965d06f27e231593cea3b50c5878f3687c1ec9d13a3ada1cb5c.jpg)  
Fig.4Comparison ofeach algorithm on sparse configuration of scale-free network   
图5各算法在高密度无尺度网络中收敛曲线图

![](images/8bdc8264c9b911f1aa54791b3aa3563f4e7fa85a572729d6f2e496a187616419.jpg)  
图4各算法在低密度无尺度网络中收敛曲线图  
Fig.5Comparison of each algorithm on dense configuration of scale-free network   
图6各算法在图着色问题中收敛曲线图  
Fig.6Comparison of each algorithm on configuration of graph coloring dcops

从图2与3可以看出，在随机DCOP问题中，在低密度与高密度问题下，PDSDSA算法与LSGADSA算法都以很快的速率下降并随后收敛，导致算法不能够找到更好的解，PDSMGM2算法与LSGAMGM2算法由于MGM2算法本身采取较为保守的策略进行求解导致在随机DCOP问题中表现都比较差；而LPOSDSA算法与LPOSMGM2算法通过并行搜索优化的策略，并采用自适应平衡因子K在求解过程中进行平衡解的开发与继承能力，使得LPOS_DSA 算法与LPOSMGM2算法都能够以较缓的速率下降代价，充分的进行寻求更优的解，以避免快速陷入局部最优。如表二、表三中所示，LPOS_DSA 算法较PDS_DSA 算法、LSGA_DSA算法和GDBA算法在低密度随机DCOP问题中在性能上分别有 $2 . 2 2 \%$ 、 $1 . 3 4 \%$ 和 $4 . 9 \%$ 的提升，在高密度随机DCOP问题中分别有 $1 . 3 4 \%$ 、 $0 . 6 2 \%$ 和 $1 . 1 7 \%$ 的提升；而LPOS_MGM2算法较PDS_MGM2算法与LSGA_MGM2算法在低密度随机DCOP问题中有 $2 4 . 5 5 \%$ 与 $2 . 8 5 \%$ 的提升，而在高密度随机DCOP问题中有 $1 2 . 1 3 \%$ 和 $4 . 1 8 \%$ 的提升。

在无尺度网络问题中，如图4、5所示，在低密度与高密度问题下，LSGA_DSA、LSGA-MGM2与GDBA算法都在迭代次数150次左右达到收敛，使得算法不能进一步寻找到更优的解，而PDSDSA在低密度问题中根据其忽略周围其中一个邻居的策略是的算法不断扩大搜索解空间，最终求得比较优秀的解，但对于高密度问题，此策略作用已经非常微小，也在150次左右的迭代次数就已经收敛；而LPOSDSA算法与LPOSMGM2算法通过并行搜索优化策略，不断进行解空间的探索，以较缓的速率进行收敛，有效的避免了快速陷入局部最优的问题。最终在表二与表三中可以看出，LPOS_DSA算法较PDS_DSA算法、LSGA_DSA算法和GDBA算法在低密度无尺度网络问题中在性能上分别有 $2 . 2 2 \%$ 、 $8 . 2 5 \%$ 和$8 . 2 5 \%$ 的提升，在高密度无尺度网络问题中分别有 $5 . 0 5 \%$ 、$4 . 2 5 \%$ 和 $4 . 0 8 \%$ 的提升；而LPOS_MGM2算法较PDS_MGM2算法与LSGAMGM2算法在低密度无尺度网络问题中有$2 . 2 2 \%$ 与 $8 . 2 5 \%$ 的提升，且在高密度无尺度网络中有 $1 9 . 6 6 \%$ 和 $7 . 6 8 \%$ 的提升。

由于图着色问题是最大约束满足问题，它约束代价取值为0或者1，相比其他问题会简单很多。如图6所示，各算法都能够快速收敛，而LPOSDSA算法通过并行搜索优化策略在200次迭代后还能继续寻找到明显由于其他算法的解。在表二与表三中可以看出，LPOS_DSA算法相较于PDS_DSA算法、LSGA_DSA算法和GDBA算法在性能上分别有 $2 9 . 8 \%$ ，$24 \%$ 和 $3 8 . 9 \%$ 的提升；而LPOS_MGM2算法较于PDS_MGM2算法与LSGA_MGM2算法则有 $2 . 2 4 \%$ 与 $8 . 2 6 \%$ 的提升。

Tab.2Upgrade rate of LPOS_DSA   

<html><body><table><tr><td rowspan="2">算法</td><td colspan="2">随机DCOP</td><td colspan="2">无尺度网络</td><td>图着色</td></tr><tr><td>0.1</td><td>0.6</td><td>3</td><td>10</td><td></td></tr><tr><td>PDS_DSA</td><td>2.22%</td><td>1.34%</td><td>2.22%</td><td>5.05%</td><td>29.8%</td></tr><tr><td>LSGA_DSA</td><td>1.34%</td><td>0.62%</td><td>8.25%</td><td>4.25%</td><td>24%</td></tr><tr><td>GDBA</td><td>4.9%</td><td>1.17%</td><td>8.25%</td><td>4.08%</td><td>38.9%</td></tr></table></body></html>

表3LPOS_MGM2 算法提升率

表2LPOS_DSA算法提升率  
Tab.3Upgrade rate ofLPOS_MGM2   

<html><body><table><tr><td rowspan="2">算法</td><td colspan="2">随机DCOP</td><td colspan="2">无尺度网络</td><td>图着色</td></tr><tr><td>0.1</td><td>0.6</td><td>3</td><td>10</td><td></td></tr><tr><td>PDS MGM2</td><td>24.6%</td><td>12.1%</td><td>2.22%</td><td>19.7%</td><td>2.24%</td></tr><tr><td>LSGA_MGM2</td><td>2.85%</td><td>4.18%</td><td>8.25%</td><td>7.68%</td><td>8.26%</td></tr></table></body></html>

# 4 结束语

本文提出一种基于局部并行搜索优化的分布式约束优化算法框架(LPOS)。该算法框架通过Agent自身取值发送给周围所有邻居并行地同时搜索自身值域来进一步扩大对解空间的搜索。此外，还设计一种自适应的平衡因子K以平衡算法在搜索过程中对解的开发与继承能力，有效避免了算法快速陷入局部最优的问题。实验结果表明，与其他算法框架相比，基于局部并行搜索优化算法框架的算法在解的质量上都有较大的提升，特别是在高密度问题中具有更好的效果。未来的研究工作将通过群体算法的策略应用于局部并行搜索过程中以加快收敛速度；同时，将算法框架应用于连续型分布式约束优化问题也是一个重要的方面。

# 参考文献：

[1]Pujol G. Multi-agent coordination Dcops and beyond [J]. Proceedings International Joint Conference on Artificial Intelligence,2011,22 (3): 28-38.   
[2]Mailler R.，Lesser V. Solving distributed constraint optimization problems using cooperative mediation [C]// Proceedings of the International Conference on Autonomous Agents and Multiagent Systems,2004: 438-445.   
[3]肖宇，许炜，程文青．一种基于分布式约束满足的资源优化模型[J]. 计算机应用研究,2009,26(3):864-866.(Xiao Yu,Xu Wei,Cheng Wenqing. Resource allocation optimization model based on DCSP [J]. Application Research of Computers,2009,26 (3): 864-866.)   
[4] Farinelli A，Rogers A，Jennings N. Agent-based decentralised coordination for sensor networks using the max-sum algorithm [J]. Autonomous agents and multi-agent systems,2014,28 (3): 337-380.   
[5]Muldoon C,Hare G,Grady M,et al. Distributed constraint optimization forresource limited sensor networks [J]. Science of Computer Programming,2013,78 (5): 583-593.   
[6]Fioretto F,Pontelli E,Yeoh W.Distributed Constraint Optimization Problems and Applications [J]. Artificial Intelligence,2016,10 (6): 23- 47.   
[7] 刘燕丽．基于冲突的 NP 难问题完备算法的研究[D].湖北：华中科 技大学,2019.   
[8]Deng Yancheng，Chen Ziyu， Chen Dingding，et al.AsymDPOP: Complete Inference for Asymmetric Distributed Constraint Optimization Problems.[J].Trans on Fundamentals of Electronics,2019,19 (5): 1182- 1189.   
[9]Arshad M, Silaghi M.Distributed simulated annealing[C]//Distributed Constraint Problem Solving and Reasoning in Multi-Agent Systems, 2004: 1-12.   
[10] Uribe L,Lara A,Deb K,et al.A New Gradient Free Local Search Mechanism for Constrained Multi-objective Optimization Problems [J]. Swarm and Evolutionary Computation,2021,10 (9): 31-38.   
[11] Okamoto S,Zivan R，Nahon，A.Distributed breakout: Beyond satisfaction [C]//In Proceedings of the Twenty-Fifth International Joint Conference on Arificial Intelligence,2016: 447-453.   
[12]张元恪．基于局部搜索和遗传策略的网络关键节点算法研究[D]. 辽宁：大连理工大学,2021.   
[13]张文昕．分布式约束优化问题推理求解算法的可扩展性优化研究 [D]．重庆：重庆大学,2020.   
[14] Rogers A,Farinelli A，Stranders R．，et al.Bounded approximate decentralsed coordination Via the max-sum algorithm [J].Artiticial Intelligence,2011,17 (5): 730-759.   
[15] Rollon E,Larrosa,J. Improved bounded max.sum for distributed constraint optimization [J].In Principles and practice of constraint programming,2012: 624-632.   
[16] Rollon E,Larrosa J. Decomposing utility functions in bounded max-sum for distributed constraint optimization [J].In Principles and practice of constraint programming,2014: 646-654.   
[17] Zivan R,Peled H. Max/min-sum distributed constraint optimization through value propagation on an alternating dag [J].In Proceedings of the llth International conference on cutonomous agents and multiagent systems,2012:265-272.   
[18] Chen, Ziyu, Deng, Yancheng,Wu Tengfei, et al. A class of iterative refined max sum algorithms via non-consecutive value propagation strategies [J]. Autonomous Agents and Multi-Agent Systems,2018 (32): 822-860.   
[19] Ottens B,Dimitrakakis C,Faltings B.An upper confidence bound approach to distributed constraint optimization problems [J]. Trans on Intelligent Systems and Technology,2017 (8): 69.   
[20] Nguyen D, Yeoh W, Zivan R.A linear-space sampling-based dcop algorithm[J].Journal of Arificial Intelligence Research,2019 (64): 705- 748.   
[21] Zivan R,Okamoto S,Peled H.Explorative anytime local search for distributed constraint optimization [J]. Artificial Intellgence,2014 (212): 1-26.   
[22]张海鹏，张扬帆，孙俊．基于Levy 分布的柔软自适应演化采样算法 [J]．计算机应用研究,2019,36(7):1994-1997.(Zhang Haipneg,Zhang Yangfan, Sun Jun.Evolutionary sampling approach with soft adaptive Levy probability distribution.[J].Application Research of Computers, 2019,36 (7): 1994-1997.)   
[23]余泽鹏．基于局部搜索的分布式约束优化问题求解算法研究[D]. 重庆：重庆大学,2017.   
[24]Hirayama K,Yokoo M.The distributed breakout algorithms [J]. Artificial Intelligence,2005,161 (1): 89-115.   
[25]MaheswaranR.,Pearce J,Tambe M.A graphical game-based approach [J].Proceedings of the International Conference on Paralll and Distributed Computing Systems,2004: 432-439.   
[26] Chen Ziyu,Liu Lizhen,He Jingyuan,et al.A genetic algorithm based framework for local search algorithms for distributed constraint optimization problems [J].Autonomous Agents and Multi-Agent Systems,2020:34-41.   
[27] Yu Zepeng,Chen Ziyu,He Jingyuan.A Partial Decision Scheme for Local Search Algorithms for Distributed Constraint Optimization Problems [C]// The International Conference on Autonomous agents and multi-agent systems,2017,175 (2):730-759.