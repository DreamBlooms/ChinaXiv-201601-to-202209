# 移动云计算中能效感知的计算卸载机制研究

杨凡，任丹

(湖北文理学院 计算机工程学院，湖北 襄阳 441053)

摘要：移动云计算可以将任务从移动设备计算卸载至云端以增强设备计算能力，而如何实现能效计算卸载机制是当前的主要挑战。为了解决该问题，以降低移动设备能耗和应用完成时间为目标，将计算卸载问题形式化为满足任务顺序与截止时间约束的能效代价最小化问题，并提出一种动态能效感知计算卸载算法。算法由三个子算法组成：计算卸载选择、时钟频率控制及传输功率分配。实验结果表明，通过局部计算时优化调整移动设备CPU时钟频率，以及云端计算时自适应分配传输功率，新算法可以有效降低应用执行能效代价，同时确保满足约束条件，提高执行效率。

关键词：移动云计算；计算卸载；能效代价；无线信道 中图分类号：TP302 doi:10.3969/j.issn.1001-3695.2018.02.0085

# Energy-aware computation offloading mechanism in mobile cloud computing

Yang Fan, Ren Dan (School ofComputer Engineering Hubei University ofArts& Science,Xiangyang Hubei 441053,China)

Abstract:Mobile cloud computing can significantly enhance computation capability of mobile devices by offloading computation from the mobile devices onto thecloud.Howtoachieveenergy-effcient computationoffoading remainsa chalenge isue.For solving this problem,withreducing energyconsumption and shorting application completion time as an objective,thisalgorithmwas proposed.Thealgorithmwillformulatecomputationofloadingproblemintotheenergy-eficiency cost minimizationproblem whilesatisfyingthetask-dependencyrequirementsandthecompletion deadlineconstraint.And,a dynamic and energy-aware computation ofoading algorithm is presented.The algorithm consistsof threesub-algorithmof computation ofloading selection,clock frequencycontrolandtransimision power alocation.Experimentalresultsshowthat thealgorithmcan efectivereducetheenergy-eficiencycost byoptimalyadjusting the CPUclock frequencyofmobiledevices inlocalcomputing,andadaptingthe tansmisionpowerincloudcomputingwhileensures tosatisfytheconstraintsandenhance the scheduling efficiency.

Key words: mobile cloud computing; computation ofloading; energy-efficient cost; wireless channel

# 0 引言

目前，以智能手机、笔记本电脑为主的智能移动设备由于其便携性、简洁性得到了越来越广泛的应用，这类移动设备也将成为支持计算密集型应用的主要平台类型，服务于交互式游戏、图形图像处理、电子商务及在线社交网络服务等在内的众多领域[1]。技术层面上而言，以上领域主要涉及复杂应用类型，需要移动设备上具有高性能计算能力、内存和长周期的电池容量[2]。然而，由于物理尺寸的限制，移动设备通常是资源受限的。尤其是，电池有限的电源供给是移动设备面临的最大挑战[3]。

随着3G、4G和Wi-Fi等无线通信技术的发展，移动云计算 MCC（MobileCloudComputing）已经成为解决以上问题的有效手段[4]。移动云计算可以将资源丰富且计算能力更强的云扩展至资源受限的移动设备端以增强移动设备的处理能力。为了实现该目标，MCC需要将移动设备端的资源密集型计算通过无线访问方式迁移至云端，即所谓的计算卸载（computationoffloading)。MCC中的移动应用需要分割为可执行于移动设备上的任务序列，此时称为局部执行（localexecution)；执行于云端时则称为云端执行（cloudexecution）。移动云计算可以选择性地通过应用的计算卸载至云端的方式提高移动设备的性能，并且节省移动设备的能耗，延长其工作时间。

尽管基于计算卸载技术的MCC可以较好的提高移动设备端的能力，但仍有诸多问题有待解决，而主要问题之一是如何实现高能效的计算卸载。为了实现MCC中移动设备的能耗节省和应用执行的高性能目标，本文重点解决了以下问题：a）哪些应用任务需要卸载至云端计算？b)在局部移动设备上执行任务时如何决定CPU运行时钟频率，实现能耗优化？c）卸载任务至云端时移动设备端如何分配传输功率，以进一步优化能耗？

# 1 相关研究

移动计算环境中的计算卸载问题已经存在很多研究，目前涉及算法主要分为两种类型：基于性能保证的计算卸载算法[5\~9]；基于能量优化的计算卸载算法[10～13]。

基于性能保证的计算卸载算法目标是提高移动设备的性能，如应用任务完成时或利用云资源的吞吐量等。此时，以资源密集为主的应用任务需要卸载至云端执行。如文献[5]提出使用虚拟机模型运行可信和资源密集型应用的调度算法，文献[6]提出CloneCloud动态卸载安卓代码至云端执行，文献[7]利用细粒度方式进行应用分割后进行计算卸载，以及文献[7,8]设计多用户计算分割以优化数据流的方式降低任务完成时间。然而，以上工作没有考虑能效的优化，也没有考虑移动设备上执行的应用任务间的顺序依赖对计算卸载策略的影响。

另一方面，基于能量优化的计算卸载算法目标是降低移动设备的能耗。此时，通过计算卸载降低任务计算开销可以实现该目标，因此，计算密集型应用需要计算卸载于云端执行。如文献[10]中设计了一种最小化能耗的任务调度算法，文献[11]设计的基于随机无线信道的能效最优移动云计算调度框架，文献[12]针对移动任务的协作式任务执行框架，以及文献[13]基于Laypunov优化法设计的动态计算卸载能耗优化算法。然而，以上工作并未做到真正的能耗优化，如局部调度时的CPU时钟频率控制，以及计算卸载至云端时的传输功率分配问题。文献[14]虽考虑了能耗与应用完成时间的同步优化，但所涉及的是独立任务集类型，任务间不存在顺序依赖，且未考虑计算卸载决策时的资源分配。同样地，文献[15]虽同时进行双目标优化，但在局部计算时未优化时钟频率，云端计算时且优化传输功率分配，这同样会导致能耗的增加。

然而，以上工作并没有同时考虑应用完成时间和移动设备能耗两个因素，本文将提出一种动态的计算卸载算法，在应用完成时间和任务执行顺序依赖约束下以最小化能耗和完成时间为目标，实现移动云计算环境中的任务调度优化。算法分三步进行：应用任务的计算卸载选择；局部执行时移动设备CPU的运行频率调整；计算卸载时传输功率分配。

# 2 模型描述

# 2.1系统模型

假设区域内有 $N$ 个移动设备，标识为集合 $N { = } \{ 1 , 2 , { \ldots } , N \}$ ，每个移动设备均拥有计算密集型应用需要执行。MCC中的移动应用可分割为顺序的 $M$ 个任务，表示为集合 $M = \{ 1 , 2 , . . . , M \}$ 。通常，移动设备可以通过两种类型的通信方式将计算应用卸载至云端，即：移动网络或访问点方式，如图1所示。

![](images/fb54ac6156e29532c2194b67ed978d04c1025fd926f8646b0aadd3fd6e83a1bd.jpg)  
图1移动云计算环境

利用如图2的有向无循环任务图 $G \mathrm { = } ( V , E )$ 描述任务间的顺序关系。图 $G$ 中的每个节点 $i \in V$ 表示一个任务，有向边 $e ( i , j )$ 表示任务i与任务 $j$ 间的顺序约束，即：任务 $j$ 不能在其前驱任务 $i$ 完成前开始执行。

![](images/a215515791085c4692d7b10c202d1420b4745e8edf308943249c84b78a5953cc.jpg)  
图2应用任务结构图

# 2.2通信模型

移动云计算中通信方式以无线访问方式为主，无线访问点可以是Wi-Fi访问点或蜂窝网络中的基站。移动设备与无线访问点间的信道服从静态衰减模型。令 $a _ { m , n } \boxed { \begin{array} { r l } \end{array} } \{ 0 , 1 \}$ 表示移动设备$n$ 的任务 $\mathbf { \nabla } _ { m }$ 的计算卸载决策， $a _ { m , n } { = } 1$ 表明移动设备 $n$ 选择通过无线信道将任务 $m$ 计算卸载至云端， $a _ { m , n } { = } 0$ 表明移动设备 $n$ 选择在其局部设备上执行任务 $\mathbf { \nabla } _ { m }$ 。令所有移动设备的所有任务的决策表示为矩阵 $A { = } \{ a _ { m , n } | m \backslash \ U { , } n \backslash \ U \}$ 。对于一个给定的向量 $A$ ，可以计算移动设备 $n$ 的任务 $m$ 进行计算卸载时的上传数据速率为

$$
R _ { m , n } ( A ) = W \log _ { 2 } ( 1 + \frac { P _ { m , n } ^ { T } H _ { m , n } } { \sigma _ { m , n } ^ { 2 } + \sum _ { i \neq m , j \neq n , a _ { i , j } = 1 } P _ { i , j } ^ { T } H _ { i , j } } )
$$

其中 $: P _ { m , n } ^ { T }$ 为移动设备 $n$ 通过无线信道卸载任务 $m$ 的传输功率,$H _ { m , n }$ 为由于路径衰减原因传输任务 $\mathbf { \nabla } _ { m }$ 时的信道增益， $\sigma _ { m , n } ^ { 2 }$ 为与传输信道链路相关的热噪声功耗， $W$ 为信道带宽。由式(1)可知，若多个移动设备同步通过无线访问信道进行计算卸载，将会导致严重的干扰和数据传输速率的下降。

# 2.3计算模型

令 $D _ { m , n }$ 为移动设备 $n$ 的任务 $m$ 的计算输入数据量， $L _ { m , n }$ 为计算负载，表示为完成任务 $\mathbf { \nabla } m$ 需要的CPU 周期总量。令 $F T _ { k , n } ^ { - }$ 、$F T _ { k , n } ^ { + }$ 、 $F T _ { k , n } ^ { c }$ 、 $F T _ { k , n } ^ { - }$ 分别表示移动设备 $n$ 的任务 $\mathbf { \nabla } _ { m }$ 的局部计算完成时间、无线传输时间（即任务被卸载至云端执行）、云端计算时间和无线接收数据时间。以下讨论局部计算和云端计算时应用的能耗开销和完成时间开销。

# 1） 局部计算

令 $f _ { m , n }$ 为移动设备 $n$ 的任务 $m$ 在局部执行时移动设备的计算能力，以CPU的时钟频率表示。不同移动设备可拥有不同的计算能力，且一个移动设备的不同任务可执行于不同的CPU频率上。则局部计算时移动设备 $n$ 的任务 $m$ 的执行时间为

$$
T _ { m , n } ^ { l } = \frac { L _ { m , n } } { f _ { m , n } }
$$

移动设备的能耗为

$$
E _ { m , n } ^ { l } = \kappa L _ { m , n } f _ { m , n } ^ { 2 }
$$

其中： $\boldsymbol { \kappa }$ 表示与芯片相关的电容切换因子，通常设置为 $\kappa { = } 1 0 ^ { - 1 2 }$ 。  
可以看出，调整CPU的频率可以实现执行时间和能耗的优化。

一个任务被执行前，其所有直接前驱任务必须已经完成。以下给出任务就绪时间的概念。

定义1就绪时间。一个任务的就绪时间定义为其所有直接前驱任务完成的最早时间。对于局部执的移动设备 $n$ 的任务$m$ 的就绪时间则为

$$
R T _ { m , n } ^ { l } = \operatorname* { m a x } _ { k \in p r e d ( m ) } \operatorname* { m a x } \{ F T _ { k , n } ^ { l } , F T _ { k , n } ^ { r } \}
$$

其中： $p r e d ( m )$ 为任务 $\mathbf { \nabla } _ { m }$ 的直接前驱任务集。

由于对于多种应用类型而言，其输出数据量通常远小于输入数据量，因此，本文忽略从云端返回数据至移动设备时的传输时间和能耗。基于该假设，式(4)可重写为

$$
R T _ { m , n } ^ { l } \geq ( 1 - a _ { k , n } ) F T _ { k , n } ^ { l } + a _ { k , n } F T _ { k , n } ^ { c } , k \in p r e d ( m )
$$

上式表明，若不考虑从无线信道接收任务 $k$ 的结果的时间，一旦任务 $k$ 完成，任务 $\mathbf { \nabla } _ { m }$ 可立即开始执行。

显然，移动设备 $n$ 的任务 $\mathbf { \nabla } _ { m }$ 在局部执行时的完成时间为局部执行时间与局部计算时的就绪时间之和，即

$$
F T _ { m , n } ^ { l } = T _ { m , n } ^ { l } + R T _ { m , n } ^ { l }
$$

根据式(2)和(3)，可以计算能效代价EEC。

定义2能效代价EEC。EEC定义为执行任务的能耗与完成时间的权重之和。因此，移动设备 $n$ 的任务 $\mathbf { \nabla } _ { m }$ 在局部执行时的EEC为

$$
Z _ { m , n } ^ { l } = \gamma _ { m , n } ^ { E } E _ { m , n } ^ { l } + \gamma _ { m , n } ^ { T } F T _ { m , n } ^ { l }
$$

其中： $0 { \leq } { \gamma } _ { m , n } ^ { E } { \leq } 1$ ， $0 { \leq } \gamma _ { m , n } ^ { T } { \leq } 1$ ，分别表示任务 $m$ 在计算能耗与完成时间上的权重因子。

为了满足用户需求，允许不同移动设备选择不同的权重因子进行决策。例如：对于拥有较低电池能量的移动设备可选择更大的 $\gamma _ { m , n } ^ { E }$ ，以便在决策制定时节省更多能量；而当移动设备运行时延敏感型应用时（如在线电影、音乐等)，可选择更大的γ$\mathbf { \Pi } _ { m , n } ^ { T }$ 以降低时延。

2）云端计算

对于云端计算，移动设备 $n$ 将卸载其计算任务 $\mathbf { \nabla } _ { m }$ 至云端执行，云端执行计算任务后返回结果至移动设备 $n$ 。任务 $\mathbf { \nabla } _ { m }$ 在云端执行过程包括三个阶段：传输阶段、云端计算阶段和接收阶段。

根据2.2节描述的通信模型，可以计算移动设备 $n$ 卸载任务 $\mathbf { \nabla } m$ 时的传输时间和能耗分别为

$$
T _ { m , n } ^ { c , t r s } ( A ) = \frac { D _ { m , n } } { R _ { m , n } ( A ) }
$$

$$
E _ { m , n } ^ { c , t r s } ( A ) = P _ { m , n } ^ { T } \cdot T _ { m , n } ^ { c , t r s } ( A )
$$

进一步，可以计算任务 $\mathbf { \nabla } _ { m }$ 在云端的执行时间为

$$
T _ { m , n } ^ { c , e x e } = \frac { L _ { m , n } } { f _ { c } }
$$

其中： $f _ { c }$ 为云端处理单元的时钟频率，且假设 $f _ { c }$ 是固定的，计算期间不发生改变。

由于云端通常拥有足够的能量执行卸载任务，因此，本文不考虑任务在云端的计算能耗。

考虑到移动应用任务间通常具有依赖性，任务 $\mathbf { \nabla } _ { m }$ 在云端的就绪时间定义为

$$
R T _ { m , n } ^ { c } = \operatorname* { m a x } \{ F T _ { m , n } ^ { t } , \operatorname* { m a x } _ { k \in p r e d ( m ) } F T _ { k , n } ^ { c } \}
$$

可以看出，若任务 $\mathbf { \nabla } _ { m }$ 的直接前驱任务 $k$ 在局部执行，则 $F T$ $\mathbf { \Pi } _ { k , n } ^ { c } { = } 0$ 。因此， $\mathfrak { m a x } _ { k \sqcup p r e d ( m ) } \{ F T _ { k , n } ^ { c } \}$ 可视为任务 $\mathbf { \nabla } _ { m }$ 的所有直接前驱任务卸载至云端已经完成的时间。此外，只要任务已被完全卸载至云端或所有直接前驱任务已经在云端完成执行，任务 $m$ 即可在云端立即执行，即

$$
R T _ { m , n } ^ { c } \geq F T _ { m , n } ^ { t } , R T _ { m , n } ^ { c } \geq \operatorname* { m a x } _ { k \in p r e d ( m ) } F T _ { k , n } ^ { c }
$$

若忽略接收任务 $\mathbf { \nabla } m$ 结果的时间，移动设备 $n$ 的任务 $m$ 在云端的完成时间为执行时间与就绪时间之和，即

$$
F T _ { m , n } ^ { c } = T _ { m , n } ^ { c , e x e } + R T _ { m , n } ^ { c }
$$

因此，从式(8)\~(10)可计算移动设备 $n$ 的任务 $\mathbf { \nabla } _ { m }$ 在云端的EEC为：

$$
Z _ { m , n } ^ { c } = \gamma _ { m , n } ^ { T } F T _ { m , n } ^ { c } + \gamma _ { m , n } ^ { E } E _ { m , n } ^ { c , t r s } ( A )
$$

从式(14)可以看出，移动设备 $n$ 较低的数据传输速率 $R _ { m , n }$ 将导致无线访问的高能耗和延长卸载任务于云端的时间。

# 3 问题形式化

给定移动设备 $n$ 的应用任务序列集合 $M$ ，该应用的EEC计算为

$$
Z _ { n } = \sum _ { m = 1 } ^ { M } Z _ { m , n } = \sum _ { m = 1 } ^ { M } ( 1 - a _ { m , n } ) Z _ { m , n } ^ { l } + a _ { m , n } Z _ { m , n } ^ { c }
$$

算法目标是选择最优计算卸载决策 $\boldsymbol { A } ^ { * }$ 、CPU时钟频率控制决策 $\boldsymbol { F } ^ { * }$ 和传输功率分配决策 $P ^ { * }$ ，使得能效代价EEC达到最小化。综合以上模型，所有移动设备的能效计算卸载决策问题可形式化为一个约束最小化问题，即

$$
\operatorname* { m i n } _ { A , F , P } \sum _ { n = 1 } ^ { N } Z _ { n }
$$

约束条件如下：

$$
\begin{array} { r l } & { C 1 \colon \displaystyle \sum _ { m = 1 } ^ { M } ( 1 - a _ { m , n } ) F T _ { m , n } ^ { l } + a _ { m , n } ( F T _ { m , n } ^ { c } ) \leq T _ { n , \mathrm { m a x } } } \\ & { C 2 \colon ( 1 - a _ { k , n } ) F T _ { k , n } ^ { l } + a _ { k , n } F T _ { k , n } ^ { c } \leq R T _ { m , n } ^ { l } , k \in p r e d ( m ) } \\ & { C 3 \colon F T _ { m , n } ^ { t } \leq R T _ { m , n } ^ { c } } \\ & { C 4 \colon \displaystyle \operatorname* { m a x } _ { k \in p r e d ( m ) } F T _ { k , n } ^ { c } \leq R T _ { m , n } ^ { c } } \\ & { C 5 \colon a _ { m , n } \in \{ 0 , 1 \} } \\ & { C 6 \colon \forall m \in M , n \in N } \end{array}
$$

其中， $A { = } \{ a _ { m , n } | m \backslash \mathop { M , n } \backslash \mathop { N } \}$ ， $F { = } \{ f _ { m , n } | m \sqcap M , n \sqcap N \}$ ， $P { = } \{ P _ { \ m , n } ^ { \ T }$ $\lvert m \rvert \neg M , n \rvert \neg N \}$ 。条件C1给出完成时间约束，即移动设备 $n$ 的所有任务的总完成时间需不超过截止时间 $T _ { n , m a x }$ 的限制；条件C2确保任务仅能在其所有直接前驱完成后才可以开始执行，即任务顺序依赖要求；条件C3给出云端任务顺序约束，即确保任务仅能在完全卸载至云端后才可以开始执行；条件C4给出另一云端任务顺序约束，即确保任务只有在其所有直接前驱任务已经在云端完成执行后才可以开始执行；条件C5为计算卸载决策约束，即任务仅能在移动设备上局部执行或卸载至云端执行。

求解式(16)中带有整数约束 $a _ { m , n } \boxed { \mathrm { ~ 1 ~ } } \{ 0 , 1 \}$ 的最优化问题是使其变为混合整数规划问题，而该问题通常是非凸和NP问题。利用松驰法，首先需要将二进制计算卸载决策变量 $a _ { m , n }$ 变为0至1间的实数，即： $0 { \leq } a _ { m , n } { \leq } 1$ 。

以下研究拥有松驰优化变量 $a _ { m , n }$ 的最优化问题(16的凸性。

定理1有约束条件 $C 1 { \sim } C 6$ 的最优化问题(16)的凸性可对应于最优化变量 $\{ a _ { m , n } \}$ 、 $\{ f _ { m , n } \}$ 和 $\{ P _ { m , n } ^ { T } \}$ 定义的优化问题。

证明需要证明式(16)中的目标函数 $Z _ { m , n }$ 是拥有优化变量$\{ a _ { m , n } \}$ 、 $\{ f _ { m , n } \}$ 和 $\{ P _ { m , n } ^ { T } \}$ 的凸函数，然后再展示 ${ \mathrm { C l } } \sim { \mathrm { C } } 5$ 的凸性。由于篇幅的限制，证明略。

定理1表明式(16的优化问题拥有零对偶间隔，且满足斯莱特约束条件。而零对偶间隔的结论则提供了求解式(16)对偶问题的最优求解方案。

# 4算法设计

# 4.1 对偶问题形式化

计算卸载策略可以通过求解式(16)的对偶问题得到。首先，定义优化问题(16)的Lagrangian函数为 $L ( \omega , \mu , A , F , P ) ,$ Lagrangian乘子 $\omega = [ \omega _ { n } , n \mathrm { = } 1 , . . . , N ] ^ { \mathrm { T } }$ 对应于完成时间约束条件C1， $\omega _ { n }$ 表示移动设备 $n$ 的应用总完成时间应不超过最大完成时间的代价，Lagrangian乘子 $\mu { = } [ \mu _ { m , n } , m { = } 1 , . . . , M , n { = } 1 , . . . , N ] ^ { \mathrm { T } }$ 对应于云端任务顺序约束条件C3， $\mu _ { m , n }$ 表示云端任务仅在完全卸载至云端后执行的代价。

最优化问题式(16)的对偶问题则为

$$
\operatorname* { m a x } _ { \omega , \mu } \operatorname* { m i n } _ { A , F , P } L ( \omega , \mu , A , F , P )
$$

式(17)的对偶问题可分解为两个层次：层次1即内层最小化问题，由 $N$ 个拥有相同结构的子问题组成，可以分布式方法求解；层次2即外部最大化问题，是对偶问题的主问题。

以下设计分布式子算法分别求解计算卸载决策选择、时钟频率控制和传输功率分配三个子问题。

# 4.2计算卸载选择

计算卸载选择子算法的目标是在满足任务顺序约束的前提下，决定哪些任务需要卸载至云端执行，从而最小化完成应用的能效代价EEC。令 $C o s t _ { m , n } ^ { l } \mathrm { = } Z _ { m , n } ^ { l } + \omega _ { n } F T _ { m , n } ^ { l }$ 表示局部设备的计算代价， $C o s t _ { m , n } ^ { c } { = } Z _ { m , n } ^ { c } { + } \omega _ { n } F T _ { m , n } ^ { c }$ 表示云端计算代价。最优计算卸载选择决策可通过求解以下最小化问题得到：

$$
\operatorname* { m a x } _ { a _ { m , n } } C o s t _ { m , n } ^ { l } + a _ { m , n } ( C o s t _ { m , n } ^ { c } - C o s t _ { m , n } ^ { l } )
$$

约束条件为C2、C4 和C5。

显然，式(18)表示的目标函数是关于变量 $a _ { m , n }$ 的线性函数，且可以观察到，若 $C o s t _ { m , n } ^ { c } { \ge } C o s t _ { m , n } ^ { l }$ ，当 $a _ { m , n } \bigsqcup [ 0 , 1 ]$ 最小时式(18)达到最小;若 $C o s t _ { m , n } ^ { c } { < } C o s t _ { m , n } ^ { l }$ ，当 $a _ { m , n } \boxed { | 0 , 1 ] }$ 最大时式(18)达到最小，即如图3所示。因此，计算卸载选择策略如下：

$$
a _ { m , n } = \left\{ \begin{array} { l l } { 1 , i f \ C o s t _ { m , n } ^ { c } < C o s t _ { m , n } ^ { l } } \\ { 0 , o t h e r w i s e } \end{array} \right.
$$

![](images/557aa0a21fa01b88467283dbfa9980bdac1bf0af4d4e4c03b8b22eb1679f92cd.jpg)  
图3目标函数最小值

该结果表明当云端计算代价比局部计算代价更小时，任务$\mathbf { \nabla } _ { m }$ 卸载至云端计算更合理。同时从 $\boldsymbol { C o s t _ { m , n } ^ { c } }$ 和 $C o s t _ { m , n } ^ { l }$ 的定义可以看出，任务的计算卸载选择决策不仅取决于具体任务的时钟频率和传输功率，而且还与其直接前驱的最大完成时间和数据上传速率相关。

# 4.3时钟频率控制决策

时钟频率控制决策的目标是局部计算时设置最优移动设备CPU的时钟频率，使应用执行的能效代价EEC最小。显然，当

$a _ { m , n } { = } 0$ 时即任务局部执行时才会执行该策略。该策略可通过求解以下优化问题得到：

$$
\operatorname* { m i n } _ { f _ { m , n } } Z _ { m , n } ^ { l } + \omega _ { n } F T _ { m , n } ^ { l } + \mu _ { m , n } ( F T _ { m , n } ^ { t } - R T _ { m , n } ^ { c } )
$$

约束条件为C2和C4。

容易证明优化问题(20)是关于 $f _ { m , n }$ 的凸问题。式(20)的目标函数 $F ( f _ { m , n } )$ 可重写为

$$
\begin{array} { r l } { F ( f _ { m , n } ) = \gamma _ { m , n } ^ { E } \kappa L _ { m , n } f _ { m , n } ^ { 2 } + \mu _ { m , n } ( F T _ { m , n } ^ { t } - R T _ { m , n } ^ { c } ) } & { { } } \\ { + ( \gamma _ { m , n } ^ { T } + \omega _ { n } ) ( L _ { m , n } f _ { m , n } ^ { - 1 } + R T _ { m , n } ^ { l } ) } & { { } } \end{array}
$$

由于 $R T _ { m , n } ^ { l }$ 、 $F T _ { m , n } ^ { t }$ 和 $R T _ { m , n } ^ { l }$ 与 $f _ { m , n }$ 无关，利用标准凸优化方法和KKT条件，可求解时钟频率控制策略为

$$
\frac { a _ { m , n } } { \omega _ { m , n } ^ { ' } + P _ { m , n } ^ { T } H _ { m , n } } + 1 = \ln ( 1 + \frac { P _ { m , n } ^ { T } H _ { m , n } } { \omega _ { m , n } ^ { ' } } )
$$

其中： $a _ { m , n } = ( \boldsymbol { \gamma } _ { m , n } ^ { T } + \omega _ { n } ) H _ { m , n } / \boldsymbol { \gamma } _ { m , n } ^ { E } - \omega _ { m , n } ^ { - }$ 和$\begin{array} { r } { \dot { \varpi _ { m , n } } = \sigma _ { m , n } ^ { 2 } + \sum _ { i \neq m , j \neq n , a _ { i , j } = 1 } P _ { m , n } ^ { T } H _ { i , j } } \end{array}$ PHi,j分别表示热噪声功耗和从云端接收数据时的干扰。

不难看出，最优传输功率即为(26)的解，即左右两个等式的交叉点，定义左右两个式子分别为 $\varphi ( P _ { m , n } ^ { T } )$ 和 $\psi ( P _ { m , n } ^ { T } )$ ，如图4所

$$
\varphi ( P _ { m , n } ^ { T } ) = \frac { a _ { m , n } } { \dot { \varpi _ { m , n } } + P _ { m , n } ^ { T } H _ { m , n } } + 1
$$

$$
f _ { m , n } = \sqrt [ 3 ] { \frac { \boldsymbol { \gamma } _ { m , n } ^ { T } + \omega _ { n } } { 2 \kappa \boldsymbol { \gamma } _ { m , n } ^ { E } } }
$$

可以看出，移动设备 $n$ 执行任务 $\mathbf { \nabla } _ { m }$ 的时钟频率取决于计算完成时间权重因子、能耗权重因子以及应用总完成时间代价。

# 4.4传输功率分配

传输功率分配策略的目标是优化分配移动设备在每个任务上的传输功率，使得云端计算任务时的EEC最小。显然，该策略仅在 $a _ { m , n } { = } 1$ 即计算任务需要卸载至云端执行时才有效。传输功率分配策略可通过求解以下最小化问题得到：

$$
\displaystyle \operatorname* { m i n } _ { P _ { m , n } ^ { T } } \sum _ { n = 1 } ^ { N } \sum _ { m = 1 } ^ { M } Z _ { m , n } ^ { c } + \omega _ { n } F T _ { m , n } ^ { c } + \mu _ { m , n } ( F T _ { m , n } ^ { t } - R T _ { m , n } ^ { c } )
$$

约束条件为C2和 $C 4$ 。

令 $Y ( P _ { m , n } ^ { T } )$ 表示目标函数式(23)，根据式(8)\~(14)，基于两种不同的 $R T _ { m , n } ^ { c }$ 值可以计算两种不同形式的 $Y ( P _ { m , n } ^ { T } )$

情形1若 $F T _ { m , n } ^ { t } { > } \mathrm { m a x } _ { k \perp p r e d ( m ) } F T _ { k , n } ^ { c }$ ，即： $R T _ { m , n } ^ { x } { = } F T _ { m , n } ^ { x }$ 。 $Y ( P _ { m , n } ^ { T } )$ 时， $Y ( P _ { m , n } ^ { T } )$ 可重写为：

$$
Y ( P _ { m , n } ^ { T } ) = \sum _ { n = 1 } ^ { N } \sum _ { m = 1 } ^ { M } [ ( \gamma _ { m , n } ^ { T } + \omega _ { n } ) ( T _ { m , n } ^ { c , e x e } + F T _ { m , n } ^ { t } ) + \gamma _ { m , n } ^ { E } E _ { m , n } ^ { c , t r s } ( A ) ]
$$

其中, $F T _ { m , n } ^ { \ast } = T _ { m , n } ^ { c , t r s } \left( A \right) + R T _ { m , n } ^ { t r s } \circ$ （ $R T _ { m , n } ^ { e r s }$ 表示任务 $\mathbf { \nabla } _ { m }$ 通过无线发送信道传输的就绪时间，为常量。

情形2若 $F T _ { m , n } ^ { \prime } { \leq } \mathrm { m a x } _ { k \cup p r e d ( m ) } F T _ { k , n } ^ { c }$ ，即 $R T _ { m , n } ^ { \prime } \mathrm { = m a x } _ { k \perp p r e d ( m ) } F T _ { k , n } ^ { c }$ 是与 $P _ { m , n } ^ { T }$ 无关的函数，则 $Y ( P _ { m , n } ^ { T } )$ 可重写为：

$$
Y ( P _ { m , n } ^ { T } ) = \sum _ { n = 1 } ^ { N } \sum _ { m = 1 } ^ { M } [ ( \gamma _ { m , n } ^ { T } + \omega _ { n } ) ( T _ { m , n } ^ { c , e x e } + R T _ { m , n } ^ { c } )
$$

$$
+ \gamma _ { m , n } ^ { E } E _ { m , n } ^ { c , t r s } ( A ) + \mu _ { m , n } ( F T _ { m , n } ^ { t } - R T _ { m , n } ^ { c } ) ]
$$

以下先给出情形1中的传输功率分配策略。

利用定理1容易证明式(24)中的 $Y ( P _ { m , n } ^ { T } )$ 是关于 $P _ { m , n } ^ { T }$ 的凸函数。利用KKT条件，传输功率分配策略可由下式求解：

（204号 $\psi ( P _ { m , n } ^ { T } ) = \ln ( 1 + \frac { P _ { m , n } ^ { T } H _ { m , n } } { \omega _ { m , n } ^ { ' } } )$ 然而，由于式(26)是一个超越方程，通常不存在对于 $P _ { m , n } ^ { T }$ 的封闭式解，因此，仅能通过牛顿迭代法获得近似解，即传输功率 $P _ { m , n } ^ { T }$ 通常下式迭代更新：

$$
P _ { m , n } ^ { T } ( t + 1 ) = P _ { m , n } ^ { T } ( t ) - \frac { \varphi ( P _ { m , n } ^ { T } ( t ) ) - \psi ( P _ { m , n } ^ { T } ( t ) ) } { \varphi ^ { \prime } ( P _ { m , n } ^ { T } ( t ) ) - \psi ^ { \prime } ( P _ { m , n } ^ { T } ( t ) ) }
$$

其中， $\varphi ^ { \prime } ( )$ 和 $\psi _ { \mathrm { { } } } ^ { \prime } ( \boldsymbol { \mathbf { \rho } } )$ 分别为关于 $P _ { m , n } ^ { T } ( t )$ 的一阶偏导。

![](images/9555615ad9277d1e679c513a3203d62033a310255363e222af0ab6159768a08b.jpg)  
图4交叉点

类似情形1，情形2的传输功率 $P _ { m , n } ^ { T }$ 可迭代更新为

$$
P _ { m , n } ^ { T } ( t + 1 ) = P _ { m , n } ^ { T } ( t ) - \frac { \phi ( P _ { m , n } ^ { T } ( t ) ) - \psi ( P _ { m , n } ^ { T } ( t ) ) } { \phi ^ { \prime } ( P _ { m , n } ^ { T } ( t ) ) - \psi ^ { \prime } ( P _ { m , n } ^ { T } ( t ) ) } \cdot
$$

$$
\phi ( P _ { m , n } ^ { T } ( t ) ) = \frac { \beta _ { m , n } } { \omega _ { m , n } ^ { - } + P _ { m , n } ^ { T } H _ { m , n } }
$$

$$
\beta _ { m , n } = \mu _ { m , n } H _ { m , n } / \gamma _ { m , n } ^ { E } - \omega _ { m , n } ^ { \mathrm { ~ ~ } } \circ
$$

从式(26)和(28)可以看出，最优传输功率与权重因子、无线信道条件和干扰是相关的。

# 4.5Lagrangian 乘子更新

式(17)中层次2的主问题可以通过次梯度法进行求解。对于给定的 $A$ ， $F$ ， $P$ 集合，Lagrangian 乘子可按下式进行更新：

$$
\omega _ { n } ( k + 1 ) = [ \omega _ { n } ( k ) + \chi ( k ) ( T _ { n , \mathrm { m a x } } -
$$

$$
\sum _ { m = 1 } ^ { M } ( 1 - a _ { m , n } ) F T _ { m , n } ^ { l } + a _ { m , n } F T _ { m , n } ^ { c } ] ^ { + }
$$

$$
\begin{array} { r } { \mu _ { m , n } ( k + 1 ) = [ \mu _ { m , n } ( k ) + \chi ( k ) ( R T _ { m , n } ^ { c } - R T _ { m , n } ^ { t } ) ] ^ { + } } \end{array}
$$

其中： $k { > } 0$ 为迭代次数， $\chi ( \boldsymbol { k } )$ 为正迭代步长。那么，在式(29)(30)中更新的Lagrangian 乘子可用于更新式(19)(22)(27)(28)中的分配策略。

算法具体执行过程如算法1所示。算法时间复杂度为$O ( M { \times } I t e r _ { m a x } { \times } I t e r _ { p o w e r } )$ ， $I t e r _ { m a x }$ 为算法的最大迭代次数，Iterpower为求解传输功率的牛顿迭代法的迭代次数， $\boldsymbol { \varepsilon }$ 为无穷小实数。

算法1能效感知的计算卸载算法

1. Input:M,pred(m),Ir   
2. Output:最优分配策略 $\{ A , F , P \}$   
3. Initialize $D _ { m , n } , L _ { m , n } , \gamma _ { m , n } ^ { E } , \gamma _ { m , n } ^ { T } , \chi ( t ) , \omega _ { n } , \mu _ { m , n } , \{ f _ { m , n } \} , \{ P _ { m , n } ^ { T } \} , t \gets 1$   
4. for $m { = } 1$ to $M$ （204号   
5. while $t \leq I t e r _ { m a x } , | \mu _ { m , n } ( t + 1 ) - \mu _ { m , n } ( t ) | > \varepsilon$   
6. /阶段1：计算卸载选择决策/   
7. compute $R _ { m , n }$ $T _ { m , n }$ and $E _ { m , n } ^ { i }$ by (1)、(2) and (3)   
8. if pred(m)==□   
9. $R T _ { m , n } ^ { \phantom { \dagger } } { = } 0 , R T _ { m , n } ^ { r s } { = } 0$   
10. else   
11. compute $R T _ { { m } , { n } } ^ { \scriptscriptstyle * } \mathrm { = m a x } _ { k \perp p r e d ( m ) } \mathrm { m a x } \{ F T _ { { k } , { n } } ^ { \scriptscriptstyle * } , F T _ { { k } , { n } } ^ { \scriptscriptstyle * } \}$ 一   
12. compute $R T _ { m , n } ^ { r s } { = } \mathrm { m a x } _ { k \perp p r e d ( m ) } \{ F T _ { k } ^ { \perp } \}$ （204号   
13. endif   
14. compute $F T _ { m , n } ^ { i }$ by (6)and $Z _ { m , n } ^ { i }$ by (7)   
15. compute $C o s t _ { m , n } ^ { c } \mathrm { = } Z _ { m , n } ^ { c } \mathrm { + } \omega _ { n } F T _ { m , n } ^ { c }$   
16. compute $T _ { m , n } ^ { v , t r s }$ $E _ { m , n } ^ { c , t r s }$ ， $T _ { m , n } ^ { e x e }$ by (8)-(10)   
17. compute $F T _ { m , n } { = } T _ { m , n } ^ { v s } + R T _ { m , n } ^ { v s }$ （204号   
18. （204号 $\mathrm { i f } p r e d ( m ) = = \square$ （204号   
19. $R T _ { m , n } ^ { x } \mathrm { = } T _ { m , n } ^ { v , t r s }$ （204号   
20. else   
21. compute $R T _ { m , n } ^ { x }$ by (11)   
22. endif   
23. compute $F T _ { m , n } ^ { x } , Z _ { m , n } ^ { x }$ by (13-14)   
24. compute $C o s t _ { m , n } ^ { c } { = } Z _ { m , n } ^ { c } { + } \omega _ { n } F T _ { m , n } ^ { c }$ （204号   
25. 证 $C o s t _ { m , n } ^ { c } { < } C o s t _ { m , n } ^ { c }$   
26. $a _ { m , n } { = } 1$ （20   
27. else   
28. （204号 $a _ { m , n } { = } 0$   
29. endif   
30. 证 $a _ { m , n } { = } { = } 1$ （204号   
31. /阶段2：时钟频率控制/   
32. compute the clock frequency $f _ { m , n }$ by (22)   
33. $P _ { m , n } ^ { T } ( t { + } 1 ) { = } P _ { m , n } ^ { T } ( t )$ （204号   
34. else   
35. /阶段3：传输功率控制/   
36. $f _ { m , n } ( t { + } 1 ) { = } f _ { m , n } ( t )$   
37. i $\because F T _ { m , n } ^ { \mathrm { { r } } } \mathrm { > m a x } _ { k \perp p r e d ( m ) } F T _ { k , n } ^ { \mathrm { { r } } }$   
38. compute $P _ { m , n } ^ { T }$ by(22) using Newton iteration method   
39. else   
40. compute $P _ { m , n } ^ { T }$ by(24) using Newton iteration method   
41. endif   
42. endif   
43. /更新Lagrangian乘子/   
44. update Lagrangian multipliers $\omega _ { n } ( t { + } 1 ) , \mu _ { m , n } ( t { + } 1 )$ by (29-30)   
45. （204 $\scriptstyle t = t + 1$   
46. end while   
47. end for

# 5 数值仿真与性能评估

# 5.1实验配置

移动云计算环境中包括 $N { = } 2 0$ 个移动智能设备，随机分布于 $1 0 0 \mathrm { m } ^ { * } 1 0 0 \mathrm { m }$ 的区域中，无线访问基站位于区域的中心。对于无线访问，设置信道带宽 $W { = } 5 \mathrm { M H z }$ ，热噪声功率 $\sigma _ { m , n } ^ { 2 } { = } 5 0 \mathrm { d B m }$ 。从移动设备 $n$ 至访问点 $s$ 的信道增益 $\scriptstyle H _ { m , n } = d _ { n , s } ^ { s }$ ， $d _ { n , s }$ 为两者间的距离， $\varsigma ^ { = } 4$ 为路径衰减因子。两个权重初始均设置为 $\gamma _ { m , n } ^ { E } { = } \gamma _ { m , n } ^ { T } { = } 0 . 5$ 。迭代次数 $I t e r _ { m a x } { = } 2 0 0$ ， $I t e r _ { p o w e r } { = } 1 0 0$ ，常量 $\scriptstyle \varepsilon = 1 0 ^ { - 6 }$ 。

为了评估计算卸载策略的性能，利用[8]中的计算分割方法将应用分割为100个任务。移动设备CPU最大频率配置为$2 . 5 \mathrm { G H z }$ ，RAM为2GB，云服务器配置4个双核心3.4GHzXeonCPU，RAM为 $1 2 8 \mathrm { G }$ 。计算任务的数据量和总的CPU周期数（即计算负载）服从高斯分布 $C N ( \mu _ { 1 } , \sigma _ { 1 } ^ { 2 }$ )和 $\mathrm { C N } ( \mu _ { 2 } , \sigma _ { 2 } ^ { 2 } )$ ，均值$\scriptstyle \mu _ { 1 } = 2 0 0 \mathrm { K B }$ ， $\scriptstyle \mu _ { 2 } = 1 0 0 0 { \mathrm { M e g a } }$ 周期，标准差 $\scriptstyle \sigma _ { 1 } = 5 0$ 和 $\scriptstyle \sigma _ { 2 } = 1 0 0$ 。分割任务数以10个任务作为观察目标，其任务结构和依赖性如图2所示。利用负载输入数据率LDR 描述任务的复杂性，定义$L D R _ { m , n } { = } L _ { m , n } / D _ { m , n }$ 。将10个任务的输入数据LDRs设置为[11.056,5.499,11.35,3.011,9.522,4.742,5.052,5.786,3.676,3.925]进行实验仿真。

# 5.2实验结果

1）收敛性

本实验观察任务复杂性对算法收敛性的影响。图5显示了任务 $2 { \sim } 5$ 得到的EEC的收敛性情况。选择任务 $2 { \sim } 5$ 是由于它们拥有相同的直接前驱任务1。可以看出：a、算法在所有任务上在100次迭代内可以完成收敛；b、拥有越大LDR的任务收敛速度越慢，即任务复杂性将增加收敛时间；c、拥有越大LDR将拥有更大能效代价EEC。因此，对任务进行计算分割时，应选择合适的LDR改进能效代价和降低执行时延。

10080 0 0Q 0666666666666A 口□□□□口□□□□口□日□□有发器 60 9 四{γ>眇會{>◇>◇仑↑γ>处 -LDR4=3.01140 --- ·LDR2=5.499DA ?20 - - O - -LDR5=9.522-- -LDR3=11.3500 50 100 150 200迭代次数

2）权重因子 $\gamma _ { m , n } ^ { E }$ 和 $\gamma _ { m , n } ^ { T }$ 对性能的影响

本实验观察不同前驱任务数量下两个权重因子对能耗和计算完成时间的影响，结果如图6所示，实验测试了权重因子 $\gamma _ { m , n } ^ { E }$ 和 $\gamma _ { m , n } ^ { T }$ 分别为(0.8,0.2)、(0.5,0.5)和(0.2.0.8)三种情况的结果。可以看出，对于给定的任务，能耗会随着能耗因子 $\gamma _ { m , n } ^ { E }$ 的增加而降低，而对于完成时间则结果是相反的，这是由于能耗因子 $\gamma _ { m , n } ^ { E }$ 的增加会导致 $a _ { m , n }$ 和 $\varphi ( P _ { m , n } ^ { T } )$ 的增加，进而会导致云端执行时传输功率的降低。同时，对于拥有相同数量直接前驱的任务，前驱任务的 LDR值对完成时间的影响比能耗更大。且更多的直接前驱会导致轻微的能耗增加和完成时间的增加，如任务9和10。

![](images/cc1fbee7e6f1fad85cea88171947aadb0adca448fa28edeb4b7e11a1623b3558.jpg)  
图5不同LDR下能效代价变化  
图6权重因子能性能的影响

3） 能效代价EEC

本实验比较算法与另外两种算法，即局部执行算法和云端执行算法，同时带有完成时间约束，进行性能比较。基准算法1为局部调度算法，基准算法2为云端调度算法。局部调度算法将所有任务调度至移动设备上执行，不进行计算卸载。云端调度算法则将所有任务均卸载至云端执行。引入这两种基准算法可以观察计算卸载对能效代价的影响。图7是三种算法在能效代价上的结果。可以看出，比较局部调度算法，新算法能够极大降低能效代价，当趋于稳定时新算法几乎可以降低4倍能效代价。这是由于新算法能够优化地选择任务在局部设备或进行计算卸载至云端执行。另外，比较云端调度算法，新算法也拥有更低的能效代价。当完成时间约束较低时，云端调度算法无法应用。随着完成时间约束变长，云端调度算法变得可用，且其能效代价出现轻微下降。然而，新算法的能效代价仍低于云端调度算法约两倍。这证明新算法中时钟频率控制和传输功率分配机制是有效可行的。

8000 亻 ◇{→-↑>I◇│>→   
7000 ? ·局部调度算法 Q Q .端调度算法   
4000 血;白·凹·;白·四   
3000 O Q   
2000 o -@-0- ○-0   
1000 0.2 0.4 0.6 0.8 1 1.2 截止时间约束

4） 能耗与完成时间

本实验比较新算法、文献[10]和文献[14]算法在能耗和任务完成时间上的性能，结果如图8所示。可以看出，当输入数据量较少时，文献[14]算法拥有最少的能耗。然而，随着输入数据量的增加，能耗会快速增加，这是由于该算法拥有自适应的能耗控制机制。因此，对于大规模输入数据，新算法和算法8能够通过自适应调整时钟频率和传输功率降低能耗。同时，新算法比较文献[10]拥有更低的能耗，这是由于新算法不仅利用了动态频率/电压调整机制控制局部调度时的CPU时钟频率，而且还利用了传输功率分配机制降低了云端执行能耗。另外，从图中还可以看出，新算法的任务完成时间在输入数据量较大时增加也比较缓慢。

![](images/5112f60176672f92a91e352ea7eb292e895dc693d536d0120ae24815db815646.jpg)  
图7能效代价

![](images/42b127f8cbfecaaa8fbad6d4bdbb77c692a398b9fcd912cbb4319748ba439364.jpg)  
图8任务规模对性能的影响

# 6 结束语

提出了一种移动云计算中基于能效感知的计算卸载算法，算法可以在满足应用完成时间截止限制和任务顺序依赖约束的条件下联合最小化计算能耗和完成时间，实现能效感知的计算卸载与资源调度。算法具体由三个子算法构成：计算卸载选择、时钟频率控制及传输功率分配。实验结果证实了算法在降低能耗与提高任务调度效率方面的有效性。进一步的研究可考虑基于移动设备移动性的计算卸载策略，研究移动模型对策略的影响，并进一步降低能效代价。

# 参考文献：

[1]Muraleedharan R.Cloud-vision: real-time face recognition using a mobilecloudlet-cloud acceleration architecture [C]//Proc of IEEE Symposium on Computers and Communications.2012: 59-66.   
[2]Shiraz M, Gani A,Khokhar RH,et al.Areview on distributed application processing frameworks in smart mobile devices for mobile cloud computing [J].IEEE Communications Surveys & Tutorials,2013,15(3):1294-1313.   
[3]Ma Cui,Yang Yang.A battery-aware scheme for routing in wireless Ad hoc networks [J].IEEE Trans on Vehicular Technology,2011,60(8):3919-3932.   
[4]李继蕊，李小勇，高云全，等,5G 网络下移动云计算节能措施研究[J], 计算机学报,2017,40(7):1491-1516.(LiJirui,LiXiaoyong,Gao Yunquan, et al.Energy saving research on mobile cloud computing in 5G[J],Chinese Journal of Computers,2017,40(7): 1491-1516.)   
[5]Yang S,Kwon D, YiH,et al. Techniques to minimize state transfer costs for dynamic execution offloading in mobile cloud computing [J].IEEE Trans on Mobile Computing,2014,13 (11):2648-2660.   
[6]Chun B G,Ihm S,Maniatis P,et al. CloneCloud: elastic execution between mobile device and cloud [C]//Proc of International Conference on Computer Systems. New York: ACM Press,2011: 301-314.   
[7]Yang Liu,Cao Jin,Tang Sao,et al.A framework for partitioning and execution of data stream applications in mobile cloud computing [J].ACM SIGMETRICS Performance Evaluation Review,2013,40 (4): 23-32.   
[8]Yang Lei,Cao Jiannong，Cheng Hui,et al. Multi-user computation partitioning for latency sensitive mobile cloud applications [J]. IEEE Trans on Computers,2015,64 (8): 2253-2266.   
[9]Kaewpuang R, Niyato D,Wang Ping,et al.A framework for cooperative resource management in mobile cloud computing [J]. IEEE Journal on Selected Areas in Communications,2013,31(12): 2685-2700.   
[10] Lin Xing, Wang Yao, Xie Qin,et al. Task scheduling with dynamic voltage and frequency scaling for energy minimization in the mobile cloud computing environment[J].IEEE Trans on Services Computing,2015,8 (2): 175-186.   
[11] Zhang Wan,Wen Yan,Guan Ken,et al. Energy-optimal mobile cloud computing under stochastic wireless channel [J]. IEEE Trans on Wireless Communications,2013,12(9): 4569-4581.   
[12] Zhang Wen, Wen Yin,Wu Du.Collaborative task execution in mobile cloud computing under a stochastic wireless channel [J]. IEEE Trans on Wireless Communications,2015,14 (1): 81-93.   
[13] Huang Dong,Wang Ping,Niyato D.A dynamic offloading algorithm for mobile computing [J].IEEE Trans on Wireless Communications,2012,11 (6): 1991-1995.   
[14] Chen Xue. Decentralized Computation offloading game for mobile cloud computing [J].IEEE Trans on Parallel& Distributed Systems,2014,26(4): 974-983.   
[15]胡海洋，刘润华，胡华．移动云计算环境下任务调度的多目标优化方法 [J]．计算机研究与发展，2017,54(9):1909-1919.(Hu Haiyang,Liu Runhua,Hu Hua.Multi-objective optimization for task scheduling in mobile cloud computing [J],Journal ofComputer Research and Development,2017, 54 (9): 1909-1919.)