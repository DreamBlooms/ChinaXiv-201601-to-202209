# 基于改进HBA算法的生鲜闭环供应链网络鲁棒优化设计\*

董海a，林国栋b

(沈阳大学a.应用技术学院;b.机械工程学院，沈阳110044)

摘要：针对生鲜闭环供应链网络设计问题，建立了一种基于生鲜闭环供应链网络的鲁棒优化模型，以解决供应链网络中的不确定性问题。首先，针对涵盖5个节点的生鲜供应链网络结构，建立了多周期，多产品，以最小化成本，最小环境影响为目标的混合整数规划模型，采用模糊折中规划与区间数据鲁棒优化方法进行处理；其次，在原有蜜獾算法的基础上，引入差分进化原则，增强算法的全局搜索能力与收敛速度；最后，通过 Matlab 数值分析与仿真实例表明，所提鲁棒优化模型与蜜獾算法在求解生鲜闭环供应链网络设计问题中具有明显优势。

关键词：闭环供应链网络设计；生鲜供应链；差分蜜獾算法；鲁棒优化 中图分类号：F253;F272 doi:10.19734/j.issn.1001-3695.2022.03.0097

# Robust optimization design of fresh closed-loop supply chain network based on improved honey badger algorithm

Dong Haia,Lin Guodongb (a.SchoolofAppliedTechnology,b.SchoolofMechanicalEngineering,Shenyang Universityhenyang0044,China)

Abstract: Aimingatthedesignofthefreshfoodclosed-loopsupplychainnetwork,thispaperintroducedarobustoptimization model based on thefresh food closed-loop supplychain network,which was established to solve theuncertainty problem in thesupplychainnetworkdesign.Firstly,forthenetwork structureoffresh fodsupplychaincovering5odes,withthe goal of minimizingcost and minimizing environmental impact,a mixed integer programming model is established,and the compromise planningand interval data robust optimization method are used for processing.Secondly,based onthe original honey badger algorithm,the principleof diferential evolution is introduced to enhance theglobal search ability and convergence speedofthealgorithm.Finaly,itisshownthatthereareobvious advantages fortherobustoptimizationmodel proposed in this paperandthe diferential honey badger algorithm can solve theclosed loopoffresh food insupplychain network design problems efciently through Matlab numerical analysis and simulation examples.

Keywords:closed-loopsupplychain networkdesign；fresh supplychain;diferential honey badgeralgorithm;robust optimization method

# 0 引言

由于自然资源短缺、工业产品残留对人类生活和环境危害等问题的出现，逆向物流和闭环供应链的设计已引起研究人员和决策者的高度重视。生鲜供应链因其易损耗，难调节等问题逐步成为供应链领域的研究热点。

国内外学者对于生鲜供应链的研究方向大多集中在定价与库存策略、保鲜努力和协调优化等方面。冯颖等[1在考虑生鲜农产品随机产出和价值损耗等特性前提下，分别构建了离岸价格和到岸价格两种模式下的分散决策博弈模型。马雪丽等[2]研究三级供应链冷链系统下由第三方物流承担生鲜品的保鲜与低碳责任时，冷链系统的保鲜、碳减排及定价等决策问题，提出了批发价格和两部收费相结合的契约激励机制。Mohammadi等[3]针对生鲜产品易腐败，浪费等问题，开发了一种基于保存技术投资的新型协调机制，提高了整体供应链的利润水平。闻卉等[4]针对自然灾害对产出的影响因素，建立基于政府、零售商和农户的三阶段Stackelberg博弈模型，对比分析在政府不同补贴政策以及零售商的合作偏好行为下，政府的最优补贴率和零售商的最优收购价格。邱慧聪等[5]针对碳税政策的生鲜绿色供应链网络优化问题，设计了成本与碳排放量平衡优化的生鲜品绿色供应链网络结构，并建立多目标混合整数模型。刘墨林等[通过构建集中式与分散式下的生鲜电商供应链决策模型，并设计“收益共享-双向成本分担”契约，实现了生鲜电商供应链的完美协调与帕累托改进。王磊等[7]构建了受生鲜农产品新鲜度和价格影响的消费者时变效用函数，并通过建立由零售商和供应商组成的两级生鲜农产品供应链利润模型，实现供应商的最优保鲜努力和零售商的最优定价。

在闭环供应链网络研究方面，孙嘉轶等[8基于消费者偏好与公平关切，建立了单双渠道的闭环供应链网络决策模型；张鑫等9针对不确定条件下的可持续闭环供应链网络设计的问题，建立了以最小成本和环境影响、最大社会影响为目标且带有模糊参数的多目标闭环供应链网络规划模型；董海等[10]研究了电网中断条件下的生鲜闭环供应链网络多目标模糊优化设计模型，解决了生鲜供应链网络设计中的不确定性问题；朱晨等[11研究了由零售商主导的双渠道闭环供应链协调问题，采用利润共享一费用分担契约实现供应链的协调；王道平等[12]研究了信息非对称下考虑制造商回收行为的闭环供应链协调问题，运用伊藤过程阐释回收率的随机演化过程，构建分散决策模型，获得制造商与零售商的最优均衡解；Yavari等[13]研究不确定条件下易腐产品的绿色闭环供应链网络的设计问题，设计了创新型混合整数规划鲁棒优化模型；Dey等[14]分析了在闭环供应链网络设计中制造商作为斯塔克尔伯格领导者时，两个竞争零售商的不同博弈策略。

闭环供应链网络优化设计问题是一个典型的NP-hard问题。近年来，该领域的最新研究多采用智能算法来求解此类非线性优化问题[15\~17]。蜜獾算法(HBA)是由Hashima等[19]于2021年提出。该算法模拟了蜜獾的挖掘和寻找蜂蜜的动态搜索行为，因其实验结果良好，结构简单，可以有效求解大规模优化问题[20]，具有广泛且良好的应用前景。然而原始蜜獾算法在处理大规模问题时全局搜索能力，收敛速度等方面还有一定的改进空间，可将其与其他算法或理念相结合，提高该算法的收敛速度和寻优能力。

综上所述，生鲜闭环供应链网络优化设计的相关研究和文献相对较少，且对于模型中的不确定性参数的处理方式略显单一。因此，本文将建立一个考虑环境影响的生鲜闭环供应链网络多目标优化模型，并采用模糊规划方法将多目标转换为单目标模型，再通过区间鲁棒优化对模型中的不确定性参数进行处理；在原HBA算法基础上，引入差分进化原则对其进行改进以求解所提模型；最后通过实例验证所提模型的可行性与算法的优越性。

# 1 模型建立

# 1.1问题描述

本文将研究由供应商、生产商、仓库、零售商和收集中心组成的多产品、多时期、多梯队的生鲜闭环供应链网络设计问题。其供应链网络运行如下：首先通过现有的供应链网络与运输方式，将生产所需的材料从供应商运送到生产商；产品通过仓库从制造商运送到零售商。不满意的产品被退回并保存在收集中心。在收集中心，将可用的退回物品作为半成品发送给制造商。其中，零售商的需求与退货率处于一个不确定性的状态。具体供应链网络结构如图1所示。

![](images/e115a0300a1f93a203d9ca71910a305f5e83e85cfef11009da4dc1f54f725580.jpg)  
图1生鲜闭环供应链网络结构示意图 Fig.1Schematic diagram of fresh closed-loop supply chain network structure

# 1.2模型假设及符号定义

本文假设如下：a）所有设施的潜在位置、容量和成本参数都是预先确定的；b)每个零售商仅从一个仓库接收其所有需求；c）零售商退回的所有产品只能送到一个收集中心，每个零售商只将其退回的产品发送到一个收集中心；d)每个产品的百分比作为退回产品发送回收集中心；e）从供应商到制造商、从制造商到仓库以及从收集中心到制造商的单位运输成本是固定的，其运输成本与运输量正相关；f)从仓库到零售商以及从零售商到收集中心的运输成本是静态的，与运输量无关，预先分配的卡车在仓库、零售商和收集中心之间的每个时期都有行程；g）零售商处于固定位置且设施的能力(供应商、生产商、仓库、零售商和收集中心)是有限的。

本文以乳制品供应链网络为例，定义符号，相关参数、符号和决策变量如下所示。符号定义如下。 $A$ 代表收集中心的潜在位置的集合， $a \in A$ ； $I$ 代表产品， $i \in I$ ， $i _ { b }$ 和 $i _ { c }$ 分别代表单源产品和再利用产品， $\boldsymbol { i } _ { b } \in \boldsymbol { I }$ ， $i _ { c } \in I$ ： $M$ 代表制造商的潜在位置集合， $m \in M$ . $R$ 表示零售商的固定地点集合， $r \in R$ $s$ 表示供应商的固定地点集合， $s \in S$ . $t$ 表示时间段 $, t \in T$ ： $W$ 表示仓库的潜在位置集合， $w \in W$ 。

参数定义如下： $k _ { i }$ 表示产品 $i$ 的退货率； $L A _ { a }$ 表示收集中心 $\boldsymbol { a }$ 的容量； $L M _ { m }$ 表示制造商 $\mathbf { \nabla } m$ 的生产能力； $L S _ { s }$ 表示供应商 $s$ 的供货能力； $L W _ { w }$ 表示仓库 $w$ 的容量； $p _ { i }$ 表示产品 $i$ 的生命周期； $F C A _ { a }$ 、 $F C M _ { m }$ 以及 $F C W _ { w }$ 分别表示建立收集中心a、制造商 $m$ 、仓库 $w$ 的固定成本； $C O M _ { i m t }$ 表示制造商 $m$ 在$t$ 时间段内生产产品 $i$ 的单位成本； $D R _ { i r t }$ 表示零售商 $\boldsymbol { r }$ 在 $t$ 时间段对产品 $i$ 的需求； $E A _ { a }$ 、 $E M _ { m }$ 、 $E W _ { w }$ 分别表示建立收集中心 $\mathbf { \Omega } _ { a }$ ，制造商 $\mathbf { \nabla } _ { m }$ 和仓库 $w$ 的环境影响； $E I A _ { i a }$ ， $E I M _ { i m }$ 、$E I R _ { i r }$ 、 $E I W _ { i w }$ 分别表示产品 $i$ 储存在收集中心 $a$ ，制造商 $\mathbf { \nabla } m$ ，零售商 $\boldsymbol { r }$ 以及仓库 $w$ 四处的环境影响； $E T A _ { j a m }$ 表示将产品 $j$ 从收集中心 $\mathbf { \Omega } _ { a }$ 运往制造商 $\mathbf { \nabla } _ { m }$ 的环境影响； $E T M i m w$ 表示将产品 $i$ 从制造商 $m$ 运输至仓库 $w$ 的环境影响； $E T S _ { s m }$ 表示供应商 $s$ 向制造商 $\mathbf { \nabla } _ { m }$ 运输的环境影响； $E T R A _ { r a }$ 表示预分配卡车从零售商 $\boldsymbol { r }$ 到收集中心 $\boldsymbol { a }$ 行程的环境影响； $E T W _ { w r }$ 表示预分配的卡车从仓库 $w$ 到零售商 $\boldsymbol { r }$ 行程的环境影响； $H C A _ { i a }$ ， $H C M _ { i m }$ $H C R _ { i r }$ ， $H C W _ { i w }$ 分别表示产品 $i$ 在收集中心 $\mathbf { \Omega } _ { a }$ 、制造商 $m$ 、零售商 $\boldsymbol { r }$ 以及仓库 $w$ 四处的单位库存成本。

$\boldsymbol { \Theta } _ { i }$ 表示产品 $i$ 的使用系数；若产品 $j$ 能作为产品 $i$ 的原材料，则 $Q _ { i j }$ 为1，否则为0； ${ \pmb \sigma } _ { i }$ 表示生产其他产品所需的退货产品 $i$ 的百分比； $P C R A _ { i r a t }$ ， $P C S M _ { s m t }$ 表示在 $t$ 时间内，为收集中心 $\mathbf { \Omega } _ { a }$ 从零售商 $\boldsymbol { r }$ 处购买产品 $i$ 的单位采购成本以及为制造商 $m$ 从供应商 $s$ 处采购原材料的单位采购成本；$T C A M i a m t$ 、 $T C M W _ { i m w t }$ 分别表示在 $\mathbf { \Psi } _ { t }$ 时间内，产品 $i$ 从收集中心 $a$ 运送至制造商 $\mathbf { \nabla } _ { m }$ 以及从制造商 $\mathbf { \nabla } _ { m }$ 运至仓库 $w$ 的单位运输成本； $T C S _ { s m t }$ 表示在 $t$ 时间内，从供应商 $s$ 运送至制造商$m$ 的原材料的单位运输成本； $T C R A _ { r a t }$ 、 $T C W R _ { w r t }$ 分别表示在$\mathbf { \Psi } _ { t }$ 时间内，从零售商 $\boldsymbol { r }$ 到收集中心 $a$ 以及从仓库 $w$ 到零售商$\boldsymbol { r }$ 的固定运输成本；若产品能从零售商 $\boldsymbol { r }$ 运送至仓库 $w$ ，则$U _ { r w }$ 值为1，反之为0；若产品能从零售商 $\boldsymbol { r }$ 运送至收集中心$a$ ，则 $V _ { r a }$ 值为1，否则为0。

决策变量符号定义如下： $N _ { i m t }$ 表示在 $\mathbf { \chi } _ { t }$ 时间内，制造商$m$ 生产的产品 $i$ 的数量； $I L A _ { i a t }$ 、 $I L M _ { i m t }$ 、 $I L R _ { i r t }$ 、 $I L W _ { i w t }$ 分别表示在 $t$ 时间段内，产品 $i$ 在收集中心 $a$ 、制造商 $m$ 、零售商$\boldsymbol { r }$ 以及仓库 $w$ 中的库存水平； $N _ { s m t }$ 表示在 $t$ 时间内，从供应商 $s$ 运至制造商 $m$ 的原材料数量； $N W R _ { i w r t }$ 、 $N R A _ { i r a t }$ 、NAMiamt$N M W _ { i m w t }$ 分别表示在 $t$ 时间内，产品 $i$ 从仓库 $w$ 发货至零售商 $\boldsymbol { r }$ 、从零售商 $\boldsymbol { r }$ 运送到收集中心 $\mathbf { \Omega } _ { a }$ 、收集中心 $\mathbf { \Delta } _ { a }$ 运送到制造商 $m$ 以及从制造商 $\mathbf { \nabla } _ { m }$ 运至仓库 $w$ 的产品数量； $O A , O M , O W$ 以及OR分别表示收集中心，生产商，仓库以及零售商的状态，若上述四个供应链节点处于开放状态则值为1，否则为0。目标函数 $Z _ { 1 }$ 为最小化网络成本， $Z _ { 2 }$ 为最小化环境影响(以$\mathrm { C O } _ { 2 }$ 排放量为衡量标准)。

$Z _ { 1 } =$ 各设施的总库存成本 $^ +$ 建立制造商、仓库和收集中心的总固定成本 $\cdot +$ 设施之间的总运输成本 $+$ 生产加工各类产品的总生产成本。

$Z _ { 2 } =$ 各设施保持库存时的 $\mathrm { C O } _ { 2 }$ 排放量 $^ +$ 建立制造商、仓库和收集中心的 $\mathrm { C O } _ { 2 }$ 排放量 $^ { \cdot + }$ 运输的 $\mathrm { C O } _ { 2 }$ 排放量。

$$
\begin{array} { r l } { M \mu _ { 0 } ^ { \mathrm { { S } } } [ \alpha \sum _ { i } ^ { \infty } \sum _ { \ell = 1 } ^ { \infty } H C \Lambda _ { i \ell } , \times H M _ { m + 1 } \overset { \mathrm { S } } { \underset { \mathrm { t r } } { = } } + \underset { \stackrel { \mathrm { T } } { \sum } } { \sum } \sum _ { \ell } ^ { \infty } H C \Lambda _ { i \ell } , \times H M _ { m + 1 } \overset { \mathrm { S } } { \underset { \mathrm { t r } } { = } } + \underset { \stackrel { \mathrm { T } } { \sum } } { \sum } \frac { H C \Lambda _ { i \ell } } { \gamma } , \quad } & { } \\ { L R _ { 0 } ^ { \mathrm { S } } [ \alpha \sum _ { i } ^ { \infty } \sum _ { \ell = 1 } ^ { \infty } H C \Lambda _ { i \ell } , \times H A _ { m + 1 } + \underset { \ell = 1 } { \overset { \mathrm { S } } { \sum } } \Gamma ( \bar { X } \Lambda _ { i \ell } , \times H A _ { m } ) + \underset { \ell = 1 } { \overset { \mathrm { S } } { \sum } } \Gamma ( \mathcal { H } \Lambda _ { i \ell } , \times } \\ { \ o W _ { - 1 } ^ { + } \sum _ { \ell } ^ { \infty } A _ { m } ) \mathrm { s o l i d } + \underset { \ell = 1 } { \overset { \mathrm { S } } { \sum } } \underset { \mathrm { t r } } { = } \sum \underset { \ell = 1 } { \overset { \mathrm { T } } { \sum } } C \Lambda _ { m } ^ { \mathrm { S } } [ \mathcal { H } A _ { m } , \times H _ { m + 1 } ^ { \mathrm { S } } ] } \\ { \underset { M \mathrm { W } _ { i \ell , m } ^ { \mathrm { S } } [ \alpha , 1 ] } { \overset { \mathrm { S } } { \sum } } \underset { \mathrm { t r } } { = } \underset { \overset { \mathrm { T } } { \sum } } { \sum } \sum _ { \ell } ^ { \infty } W \Lambda _ { i \ell } , \quad } & { + \underset { \ell = 1 } { \overset { \mathrm { S } } { \sum } } \underset { \mathrm { T } } { \sum } \sum _ { \ell } ^ { \infty } \sum _ { \ell = 1 } ^ { \infty } H W _ { i \ell m } \mathrm { S } _ { \ell m } ^ { \mathrm { S } } } \\ { \underset { \mathrm { T } } { \overset { \mathrm { S } } { \sum } } \underset { \mathrm { t r } } { \overset { \mathrm { S } } { \sum } } \sum _ { \ell } ^ { \infty } Y \bar { Z } ( \mathcal { H } \mathcal { H } _ { m + 1 } ^ { \mathrm { S } } \otimes \mathrm { T } \mathcal { Q } _ { m } ) ^ { \mathrm { T } } } \\  \underset { \mathrm { T } } { = } \sum _ { i } ^ { \infty } \underset { \mathrm { T } } { = }  \overset { \mathrm { T } }  \end{array}
$$

$$
\begin{array} { r l } { { } } & { { M i n Z _ { 2 } { = } ( \displaystyle \sum _ { i } \displaystyle \sum _ { m } { \sum _ { n } { \cal Z } } { { { E I M } _ { i n } } \times { { I L } } _ { i n t } } + \displaystyle \sum _ { i } \displaystyle \sum _ { w } { \sum _ { \tau } { \cal E } } { { { E I M } _ { i n } } \times { { I L } } _ { i n t } } + } } \\ { { } } & { { ~ \displaystyle \sum _ { i } \displaystyle \sum _ { a } { \sum _ { \tau } { { E I A } _ { a } } \times { { I L } } _ { i a t } } + \displaystyle \sum _ { i } \displaystyle \sum _ { \tau } { \sum _ { \tau } { { E I R } _ { i n } } \times { I L } _ { i n t } } + } } \\ { { } } & { { ~ ( \displaystyle \sum _ { m } { { E M } _ { m } } \times { { O M } } + \displaystyle \sum _ { w } { { E W } _ { w } } \times { O W } + \displaystyle \sum _ { a } { { E A } _ { a } } \times { O A } ) + } } \\ { { } } &  { ( \displaystyle \sum _ { s } \displaystyle \sum _ { m } { \sum _ { \tau } { { E T S } _ { m } } \times { { N } _ { a n t } } } + \displaystyle \sum _ { i } \displaystyle \sum _ { m } { \sum _ { w } { \tau } _ { \tau } { { E T } } _ { i a m } } \times { N } { M } _ { i a m { { \mathrm { { e m } } } t } } + } \\ { { } } & { { ~ \displaystyle \sum _ { s } \displaystyle \sum _ { \tau } { { E T N } _ { i n t } } \times { { U } _ { m } } + \displaystyle \sum _ { \tau } { { E T R } _ { i a m } } \times { V } _ { m } + } } \\ { { } } & { { ~ \displaystyle \sum _ { \tau } { \displaystyle \sum _ { j } \displaystyle \sum _ { a } \sum _ { m } { \sum _ { \tau } { { E T A } _ { j m } } \times { Q } _ { i } } \times { N A } _ { j m a } } ) } } \end{array}
$$

式(3)和(4)分别表示零售商和仓库中有充足的输入。

$$
\sum _ { t } D R _ { i n } \leq \sum _ { w } \sum _ { t } N W R _ { i w r t } , \forall i , r
$$

$$
\sum _ { m } \sum _ { t } N M W _ { i m w t } \geq \sum _ { r } \sum _ { t } N W R _ { i w r t } , \forall i , w
$$

式(5)表示从每个零售商返回到收集中心的产品数量都是其需求的一部分。

$$
\sum _ { a } \sum _ { t } N R A _ { i r a t } \leq \sum _ { t } D R _ { i r t } \times k _ { i } \quad \forall i , r
$$

式(6)表示每个收集中心的输入流大于输出流。

$$
\sum _ { r } \sum _ { t } \sigma _ { i } \times N R A _ { i r a t } \geq \sum _ { m } \sum _ { t } N A M _ { i a m t } \quad \forall i , a
$$

式(7)表示每个制造商的输入和输出之间的平衡。

$$
\sum _ { s } \sum _ { t } N _ { s m t } \ge \sum _ { i } \sum _ { w } \sum _ { t } \theta _ { i } \times N M W _ { i m w t } - \sum _ { i } \sum _ { j } \sum _ { a } \sum _ { t } \theta _ { i } \times Q _ { i j } \times N A M _ { j a m t } , \forall m
$$

式(8)讨论了每个制造商的产量至少应该与从制造商送到仓库的产品一样多。

$$
\sum _ { t } N _ { i m t } \geq \sum _ { w } \sum _ { t } N M W _ { i m w t } \mathrm { ~ } , \forall i , m
$$

式(9)至(12)分别表示制造商、供应商、仓库和收集中心的容量限制。

$$
\sum _ { i } N _ { i m t } \leq L M _ { m } \times O M \ , \forall m , t
$$

$$
\sum _ { m } N _ { s m } \leq L S _ { s } , \forall s , t
$$

$$
\sum _ { i } I L W _ { i w ( t - 1 ) } + \sum _ { i } \sum _ { m } N M W _ { i m w t } \le L W _ { w } \times O W , \ \forall w , t
$$

$$
\sum _ { i } I L A _ { i a ( t - 1 ) } + \sum _ { i } \sum _ { r } N R A _ { i r a t } \leq L A _ { a } \times O A , \forall a , t
$$

式(13)\~(16)表示制造商、仓库、收货中心、零售商各时间段内每种产品的库存水平。

$$
I L M _ { i m t } = N _ { i m t } + I L M _ { i m ( t - 1 ) } - \sum _ { w } N M W _ { i m w t } , \ \forall i , m , t
$$

$$
I L W _ { i w t } = \sum _ { m } { N M W } _ { i m w t } + I L W _ { i w ( t - 1 ) } - \sum _ { r } { N W R } _ { i w t } , \ : \forall i , w , t
$$

$$
I L A _ { i a t } = \sum _ { r } N R A _ { i r a t } + I L A _ { i a ( t - 1 ) } - \sum _ { m } N A M _ { i a m t } \ , \forall i , a , t
$$

$$
I L A _ { i a t } = \sum _ { w } N W R _ { i w r t } + I L R _ { i r ( t - 1 ) } - D R _ { i r t } , \forall i , r , t
$$

式(17)确保产品只能由现有的制造商生产。

$$
O M \le \sum _ { i } \sum _ { t } N _ { i m t } \le M \times O M , \ \forall m
$$

式(18)(19)确保产品从生产商发送到仓库或收集中心。

$$
O W \le \sum _ { i } \sum _ { m } \sum _ { t } N M W _ { i m w t } \le M \times O M , \forall w
$$

$$
O A \le \sum _ { i } \sum _ { r } \sum _ { t } N R A _ { i r a t } \le M \times O A , \forall a
$$

式(20)(21)确保任何非链接设施之间没有转运物流。

$$
U _ { w r } \leq \sum _ { i } \sum _ { t } N W R _ { i w r t } \leq M \times U _ { w r } \ , \forall w , r
$$

$$
V _ { r a } \leq \sum _ { i } \sum _ { t } N R A _ { i r a t } \leq M \times V _ { r a } \mathrm { ~ , ~ } \forall r , a
$$

式(22)表示每个零售商只从一个仓库接收产品，式(23)表示每个零售商只将返回的产品发送到一个收集中心。

$$
\sum _ { w } U _ { w r } \le 1 , \quad \forall r
$$

$$
\sum _ { a } V _ { r a } \leq 1 , \forall r
$$

式(24)表示收集中心发送的所有退货产品必须在同一时间被用于生产再制造产品。

$$
N A M _ { i c m t } \geq \sum _ { a } \sum _ { j } Q _ { i j } \times N A M _ { i a m t } , \forall i , m , t
$$

式(25)表示产品 $i$ 在每个仓库的库存水平在下一个 $P _ { i } ( \vec { p } ^ { \mathrm { : } }$ 品 $i$ 的生命周期)连续期间内始终小于产品 $i$ 的总出库量。

$$
I L W _ { i w t } \leq \sum _ { r } \sum _ { l = t } ^ { t + ( p _ { i } - 1 ) } N W R _ { i w r l } \ , \ \forall i , w , t
$$

式(26)确保零售商在每个时期的每个产品的库存水平小于下一个 $P _ { i }$ 连续时期的总需求。

$$
I L R _ { i n } \leq \sum _ { t } ^ { t + ( p _ { i } - 1 ) } D R _ { i r t } \ , \ \forall i , r , t
$$

# 2 模型处理

# 2.1多目标处理

由于本文所建的两个目标函数 $Z _ { 1 }$ 与 $Z _ { 2 }$ 在某种程度上存在冲突，即 $Z _ { 1 }$ 目标函数表现较优时可能会导致另外的子目标函数 $Z _ { 2 }$ 表现不佳。为了实现帕累托最优，本文将采用模糊折中规划方法进行多目标处理。根据文献[20]中描述，模糊折中规划法的具体数学表达式如下：

$$
L p = \left[ \sum _ { i = 1 } ^ { k } \lambda _ { i } ^ { p } \left[ f _ { i } - { f _ { i } } ^ { * } \right] ^ { p } \right] ^ { \frac { 1 } { p } }
$$

其中 $p$ 属于 $[ 1 , \infty ]$ 中的正整数； $f _ { i } ^ { * }$ 表示各个子目标函数 $f _ { i }$ 的对应的理想解，即 $f _ { i } ^ { * } { = } \mathrm { m i n } ( f _ { i } )$ ; $\lambda _ { i }$ 表示赋予各个子目标的权重，且属于 $( 0 , \ \infty )$ 。从而本文的多目标模型将等价转换如下：

$$
\mathrm { m i n } \Biggl ( w _ { 1 } \Biggl ( { \frac { Z _ { 1 } - Z _ { 1 } ^ { * } } { Z _ { 1 } ^ { * } } } \Biggr ) ^ { p } + w _ { 2 } \Biggl ( { \frac { Z _ { 2 } - Z _ { 2 } ^ { * } } { Z _ { 2 } ^ { * } } } \Biggr ) ^ { p } \Biggr ) ^ { \frac { 1 } { p } }
$$

其中 $w _ { i }$ 为各个子目标函数的相对权重，且 $w _ { i }$ 为 $\lambda _ { i }$ 与 $p$ 的乘积。通过改变参数 $p$ 的值可以得到不同的有效解，最常见的值是 $p { = } 1$ 、2和 $\infty$ 。

# 2.2鲁棒处理

为了将确定性模型扩展到不确定环境中，本文假设退货率、需求为不确定性参数，鲁棒方法主要有两阶段：首先是构建不确定参数区间对不确定参数进行处理描述；其次是采用鲁棒对等式进行转换，将鲁棒模型转换为等价的混合整数规划模型进行求解。

本文采用设置不确定集区间考虑不确定性参数的偏差范围[21，提出闭环供应链模型的鲁棒对应形式。此外，本文定义了参数 $d = D R _ { i r t }$ ， $k { = } K _ { i }$ 。不确定参数 $D \widetilde { R _ { i r t } }$ ， $\widetilde { K _ { i } }$ 具有相同独立分布，并且在范围 $\left[ d - d , d + d \right]$ ， $\left[ k - k , k + k \right]$ 中分布对称。此外，不确定性预算 $I ^ { 0 }$ 取值[0,1]。

由于假设需求与退货率是不确定的，并且考虑鲁棒优化模型中最坏情况参数对模型和算法的影响，即本文只考虑需求和退货率的不确定参数的正偏差。不确定性参数主要集中于约束式(3)(5)(26)。以约束式(3)为例，该约束左侧含有不确定参数，将其不确定参数值记为 $A _ { j }$ ， $j { \in } J$ ，而 $J$ 表示这个约束中不确定性参数的数量索引集合；根据文献[21]定义 $A _ { j } = A _ { j } + A _ { j } \xi _ { j }$ ，其中 $A _ { j }$ 被称为标称值， $A _ { j }$ 表示 $A _ { j }$ 的最大偏离值； $\pmb { \xi } _ { j } \in U$ ， $U$ 表示一个有界的闭集，而 $\xi _ { j }$ 则在不确定集 $U$ 中选择以控制 $\widetilde { A _ { j } }$ 的上下限度。根据上述定义内容，约束式(3)可表示为

$$
d \bigg ( 1 + d \times \frac { \mu _ { 1 } } { \vert i \vert \times \vert r \vert } \bigg ) \leq \sum _ { w } \sum _ { t } N W R _ { i w r t } , \forall i , r
$$

其中： $\mu _ { l }$ 表示需求的保守性参数， $\mu _ { 1 } \in [ 0 , | i | \times | r | ]$ 0

综上所述，引入 $\widetilde { d _ { j } }$ 表示供应链中产品需求的不确定性，即 $d _ { j } = d _ { j } + d _ { j } \zeta _ { j }$ ， $\xi _ { j } \in U$ ， $j \in J _ { \circ } \forall j$ 为控制 $\widetilde { d _ { j } }$ 的独立随机变量。根据上述文献定义及规则，引入辅助变量 $Y _ { j }$ 。此外，不确定性预算 $I ^ { 0 }$ 取值[0,1]。

可得到相关约束与鲁棒等价模型 $Z ^ { * }$ 如下。约束中$\scriptstyle \varepsilon = D \widetilde { R _ { i r t } } \times \widetilde { K i }$ ： $\beta ^ { * } { = } \sum _ { t } ^ { t + ( p _ { i } - 1 ) } D R _ { i r t }$ 。除此之外， $\mu _ { 2 } \in [ 0 , | i | \times | r | \times | t | ]$ 。

$$
\mathrm { M i n } \{ Z _ { 1 } , Z _ { 2 } \}
$$

$$
\sum _ { i = 1 } ^ { n } \Biggl [ \sum _ { j = 1 } d _ { j } \times d _ { j } \times I ^ { 0 } + Y _ { j } \zeta _ { j } \Biggr ] + Z \leq Z ^ { * }
$$

$$
\sum _ { a } \sum _ { t } N R A _ { i r a t } \leq \varepsilon \Biggl ( 1 + \varepsilon \times \frac { \mu _ { 1 } } { | i | \times | r | } \Biggr ) , \quad \forall i , r
$$

$$
\sum _ { i } \sum _ { r } \sum _ { t } I L R _ { i r t } \leq \beta _ { * } \bigg ( 1 + \beta _ { * } \frac { \mu _ { 2 } } { | i | \times | r | \times | t | } \bigg ) , \quad \forall i , r , t
$$

$$
0 \leq Y _ { j } \leq d ; 0 \leq \zeta _ { j } \leq J
$$

其他约束条件不变。

# 3 求解方法

# 3.1编码处理

考虑到供应链网络设计问题中的多层级、多周期的复杂性，本文选用矩阵实数编码方法：假设种群规模为 $P ^ { \prime }$ ，第 $\varrho$ 代种群 ${ \cal W } _ { \it Q } { = } \{ K _ { 1 } , K _ { 2 } , . . . , K _ { P ^ { \prime } } \}$ ，其中 $K _ { j }$ 代表第 $\varrho$ 代的第 $j$ 个个体， $j \in [ 1 , P ^ { \prime } ]$ ， $Q \in [ 1 , t _ { \operatorname* { m a x } } ]$ ；定义 $K _ { j } { = } ( C _ { a b } ) _ { m \times n }$ ， $C _ { a b }$ 表示矩阵元素， $a \in [ 1 , m ]$ ； $b \in [ 1 , n ]$ 。除此之外，矩阵 $K _ { j }$ 的大小跟供应链网络中的层级、节点设置数有关，并且矩阵元素 $C _ { a b }$ 主要反映与上层供应者的物流或者供货关系。例如 $K _ { j }$ 为一个3$\times 4$ 阶的矩阵，则表示该供应链网络模型分为3层，节点数最多设置为4， $C _ { 2 1 } { = } ( 5 3 , 0 , 4 8 , 0 )$ 则表示第2层的第1个节点接收分别来自上层供应者第1个节点53的单位供货量与第3个节点48的单位供货量，0则表示该两节点间没有供货关系。

# 3.2原始蜜獾算法

# 3.2.1种群的初始化

HBA的基本思想是通过模拟蜜獲的觅食行为进行优化。式(34)初始化蜜獾的数量(种群大小N)及其各自的位置。

$$
x _ { i } = l b _ { i } + r _ { 1 } \times \left( u b _ { i } - l b _ { i } \right)
$$

其中： $\boldsymbol { r } _ { 1 }$ 为[0,1]的随机数。 $x _ { i }$ 代表种群 $N$ 中第 $i$ 个蜜獾的位置；而 $l b _ { i }$ 和 $u b _ { i }$ 分别是搜索域的下限和上限。

3.2.2捕食强度

蜜獾的捕食强度与猎物的集中强度以及其与第 $i$ 个蜜獾的距离有关。 $I _ { i }$ 是猎物的气味强度；如果气味高，运动就快，反之亦然。具体定义如下：

$$
I _ { i } = r _ { 2 } \times \frac { S } { 4 \pi d _ { i } ^ { 2 } }
$$

其中： $s$ 代表猎物的集中强度与气味强度， $d _ { i }$ 表示猎物和第 $i$ 只獾之间的距离， $S = ( x _ { i } - x _ { i + 1 } ) ^ { 2 }$ ； $d _ { i } = x _ { p r e y } - x _ { i }$ 。 $r _ { 2 }$ 为[0,1]的随机数。

# 3.2.3更新密度因子

密度因子 $( a )$ 控制时间变化的随机性，以确保算法两阶段的平稳过渡。根据式(36)更新随迭代次数减少的递减因子$\alpha$ ，减少时间的随机性。

$$
\alpha = C \times \exp \left( \frac { - t } { t _ { \mathrm { m a x } } } \right)
$$

其中： $t _ { m a x }$ 表示最大迭代次数； $C$ 表示一个大于1的常数(默认值设为2)。

# 3.2.4更新粒子位置

正如上文所述，HBA粒子位置更新过程采用“挖掘模

式”和“蜂蜜模式”，该算法使用改变搜索方向的标志 $F$ 确保能有更多的机会对搜索空间进行严格扫描，以跳出局部最优的困局。

1)挖掘模式

在挖掘模式中，蜜獾的运动路线类似于心形，通过式(37)可以模拟运动路线轨迹。

$$
\begin{array} { c } { x _ { n e w } = x _ { p r e y } + F _ { 1 } \times \beta \times I \times x _ { p r e y } + } \\ { F _ { 1 } \times r _ { 3 } \times \alpha \times d _ { i } \times \left| \cos ( 2 \pi r _ { 4 } ) \times \left[ 1 - \cos \left( 2 \pi r _ { 5 } \right) \right] \right| } \end{array}
$$

其中， $x _ { n e w }$ 代表蜜獾的新位置， $x _ { p r e y }$ 代表猎物的位置全局最佳位置， $\beta { \geq } 1$ (默认值为6)描述的是蜜獾获得食物的能力，$d _ { i }$ 是猎物和第 $i$ 只蜜獾之间的距离， $r _ { 3 } , r _ { 4 }$ 和 $\mathbf { \sigma } _ { r 5 }$ 是0到1之间的三个不同的随机数， $F _ { 1 }$ 作为改变搜索方向的标志，由式(38)确定：

$$
F _ { 1 } = \left\{ { \begin{array} { r l } { 1 } & { { } { i f \ r _ { 6 } \leq 0 . 5 } } \\ { - 1 } & { { } { \mathrm { e l s e } } , } \end{array} } \right.
$$

$r _ { 6 }$ 属于0到1的随机数，蜜獾在挖掘模式中主要依赖于对猎物的嗅觉强度 $I _ { i }$ 、猎物的距离 $d _ { i }$ 和时间搜索影响因子 $\scriptstyle a$ 进行搜索。

2)蜂蜜模式

蜂蜜模式中，蜜獾跟随导蜜鸟到达蜂巢的情况可以模拟为式(39)。

$$
\begin{array} { r } { x _ { n e w } = x _ { p r e y } + F _ { 1 } \times r _ { 7 } \times \alpha \times d _ { i } } \end{array}
$$

其中， $r _ { 7 }$ 为0到1的随机数， $\alpha$ 和 $F _ { 1 }$ 由式(36)(38)确定。由式(39)可以看出，蜜獲根据距离信息 $d _ { i }$ ，在目前发现的猎物位置 $x _ { p r e y }$ 附近进行搜索。在这一阶段，搜索行为会受到随时间变化因子 $( a )$ 的影响。

# 3.3差分蜜獾算法

为改进原始蜜獾算法处理大规模问题时易陷入局部最优，收敛速度慢等缺陷，本文将差分进化算法(DifferentialEvolutionAlgorithm，DEA)中的交叉变异原则引入到原始蜜獾算法中，形成差分蜜獾算法(DifferentialHoney BadgerAlgorithm，DHBA)。在选择新位置与个体时，通过执行差分进化交叉变异策略，使得DHBA具有全局搜索范围更广、种群更具多样性。具体DE/rand/1/bin交叉变异策略如下：

1)变异策略

$$
V _ { i D , j } = X _ { \mathit { p r e y } , j } + F _ { 2 } \times r a n d ( X _ { \mathit { r } 8 , j } - X _ { \mathit { r } 9 , j } )
$$

其中， $X _ { p r e y }$ 代表当前搜索区域内的最优位置， $F _ { 2 }$ 为缩放系数且为(0，1)间的常数， $X _ { r 8 , j \setminus \ r _ { 9 , j } }$ 为种群中的随机个体， $r _ { 8 }$ 、$\mid r 9 \mid$ 属于种群 $N$ 中的互不相同的整数。

2)交叉操作

$$
u \left\{ { \begin{array} { l } { V _ { i D , j } , \mathrm { ~ i f ~ r a n d ( 0 , 1 ) \leq C R } } \\ { X _ { p r e y , j } , \mathrm { ~ o t h e r w i s e } } \end{array} } \right.
$$

其中rand(0,1)是(0,1)服从上均匀分布的随机数， $C R$ 为交叉概率且属于[0,1]。DHBA具体算法流程如图2所示。

# 4 算例验证

本文以沈阳某奶制品制造厂商为例，该公司供应链网络范围主要覆盖市内五个行政区，由5个节点组成，其中包括3个供应商、5个制造中心、4个仓库、17个零售商以及3个收集中心。该公司主要生产两类奶制品，回收中心只回收其中一类产品，且只考虑固定单一的运输方式。除此之外，根据企业实际情况，各个参数值都服从均匀随机分布，需求不确定性 $D \widetilde { R i r t } \in [ 4 0 0 , 2 0 0 0 ]$ ，退货率不确定性 $\widetilde { K _ { i } } \in [ 0 , 1 ]$ ，供应链网络具体参数值设置如下表1所示。

# 4.1鲁棒模型验证

为验证本文所设计的鲁棒优化模型的稳定性与可行性，针对需求不确定的情况生成了表2中的5个测试问题，相应参数如表1所示。

![](images/0594f52b9bd03af8955a5cef96c176ba276f972bc6507d5ff5245a4292d3c695.jpg)  
图2DHBA 算法流程

Tab.1Corresponding parameter Settings   

<html><body><table><tr><td>参数</td><td>取值范围</td></tr><tr><td>LSs,LMm,LWw,LAa</td><td>10000~40000</td></tr><tr><td>HCMim,HCWiw,HCAia,HCRir,i,Comimt</td><td>5~15</td></tr><tr><td>FCMm,FCWw,FCAa</td><td>5000~80000</td></tr><tr><td>TCSsmt,TCMWimwt,TCAMiamt,PCRAirat,PCSmst,</td><td>10~40</td></tr><tr><td>TCW wrt,TCRArat,DRirt</td><td>500~3000</td></tr><tr><td>ETSsm,ETMimw,ETWwr,ETRrc,ETAjam,EMm,EAa</td><td>1~20</td></tr><tr><td>EIMim,EIWiw,EIRir,EIAia</td><td>0.9~4,56</td></tr><tr><td>Oi，</td><td>0.04~1</td></tr></table></body></html>

<html><body><table><tr><td>测试问题</td><td>S</td><td>M</td><td>W</td><td>R</td><td>A</td><td>DRirt</td></tr><tr><td>1</td><td>3</td><td>4</td><td>6</td><td>4</td><td>2</td><td>553</td></tr><tr><td>2</td><td>5</td><td>4</td><td>4</td><td>6</td><td>3</td><td>674</td></tr><tr><td>3</td><td>5</td><td>5</td><td>7</td><td>6</td><td>2</td><td>540</td></tr><tr><td>4</td><td>10</td><td>3</td><td>7</td><td>3</td><td>4</td><td>832</td></tr><tr><td>5</td><td>15</td><td>7</td><td>8</td><td>4</td><td>4</td><td>976</td></tr></table></body></html>

表3为在需求不确定条件下，鲁棒模型与确定性模型中各个目标函数的对比情况。由表3可知，鲁棒模型相较于确定模型具有明显的优势，总成本函数 $Z _ { 1 }$ 的平均函数值下降了 $34 . 3 7 \%$ ，环境影响函数 $Z _ { 2 }$ 平均函数值下降了 $2 2 . 7 1 \%$ 。

表3需求不确定条件下鲁棒模型与确定模型的对比情况

Tab.2Robust model testing problems   
Tab.3Comparison of robust model and deterministic model unde   

<html><body><table><tr><td colspan="4">uncertaindemandconditions</td></tr><tr><td rowspan="2">测试问题</td><td colspan="2">鲁棒优化模型</td><td colspan="2">确定性模型</td></tr><tr><td>Zi/105</td><td>Z2/105</td><td>Zi/105</td><td>Z2/105</td></tr><tr><td>1</td><td>76.1</td><td>53.4</td><td>100.3</td><td>87.5</td></tr><tr><td>2</td><td>83.9</td><td>71.2</td><td>130.8</td><td>101.6</td></tr><tr><td>3</td><td>75.2</td><td>54.5</td><td>97.3</td><td>88.2</td></tr><tr><td>4</td><td>96.4</td><td>77.8</td><td>160.9</td><td>129.3</td></tr><tr><td>5</td><td>141.7</td><td>121.4</td><td>192.5</td><td>151.8</td></tr></table></body></html>

# 4.2 敏感性分析

为进一步验证本文所提模型的可靠性，本文将零售商的需求不确定性 $D \widetilde { R _ { i r t } }$ 与供应链网络成本、环境影响函数进行敏感性分析并将其范围设置为[400,1400]。考虑到市场竞争环境下，供应链网络设计中应优先考虑企业的效益与成本，其次就是对环境的影响。因此，最终综合各类实际情况，将$w _ { 1 , w _ { 2 } }$ 权重设置为0.7与0.3，并将零售商的退货率设为0.2。根据表1与实际案例中的数据，采用DHBA进行计算，各目标函数值随需求不确定性的变化情况如图3所示(单位：需求量/吨)。

![](images/ab0dd254c585907568610d18d62426b1e16e2a468a319cf8a04e971ea0caf735.jpg)  
Fig.2DHBA algorithm flow表1相应参数设置  
图3需求对供应链成本、环境成本的影响 Fig.3Influence of demand on supply chain cost and environmental cost

从图3可知，在[400,800]内，成本函数与环境函数总体趋势一样，然而[800,1400]内随着零售商的需求量的增加，供应商与制造商的供货与生产量也随之快速增加，即成本呈快速上升趋势；然而环境成本函数总体受需求不确定性的波动性较为缓和，其主要原因在于权重的相关设置，在现实情况中，作为供应链上层的决策者可以根据实际政策与自身偏好决定其权重值的分配。

# 4.3算法性能测试

为综合评价本文采用的DHBA算法性能，将其与目前较为主流的非支配排序遗传算法(NSGA-II)、改进的鲸鱼群算法(IWOA)[22]，以及原始蜜獾算法(HBA)在MatlabR2018b上运行并进行比较。Matlab软件的运行计算机环境为：处理器为R7-4800HRTX2060，内存16G，操作系统为Windows11的手提电脑。

本文针对目标函数共生成5个测试问题如表4，各个节点参数设置如表1，并将种群规模都设置为50，最大迭代限制为400次。其次为了验证本文所提多目标鲁棒优化模型，同时避免偶然性，本文设置两种场景，即 $^ { w _ { 1 } , w _ { 2 } }$ 权重设置为(0.5，0.5)(0.8，0.2)并采用DHBA，NSGA-II以及IWOA对所提模型分别进行求解计算，其具体结果如表5所示，算法仿真对比如图4。

表2鲁棒模型测试问题  
表4测试问题  
Tab.4Test problem   

<html><body><table><tr><td>Test Problem</td><td>S</td><td>M</td><td>W</td><td>R</td><td>A</td></tr><tr><td>1</td><td>6</td><td>3</td><td>5</td><td>12</td><td>3</td></tr><tr><td>2</td><td>9</td><td>5</td><td>9</td><td>15</td><td>7</td></tr><tr><td>3</td><td>13</td><td>6</td><td>10</td><td>13</td><td>5</td></tr><tr><td>4</td><td>15</td><td>8</td><td>14</td><td>23</td><td>11</td></tr><tr><td>5</td><td>19</td><td>12</td><td>20</td><td>21</td><td>6</td></tr></table></body></html>

由表5可知，在两种权重下的计算结果中，DHBA获得最优解的能力均超过了NSGA-II与IWOA，从而说明了差分进化蜜獾算法求解本文多目标问题的有效性与可行性。除此之外，计算结果还表明，DHBA表现并非完美，在局部范围中，其寻优速度与NSGA-II相比，还有一定的提升空间。

从图4可知，在[0.30]阶段中，HBA的收敛速度略微超过DHBA、NSGA-II与IWOA，其余三者在初始阶段收敛速度大致相同；在[32,51]时间区间内，DHBA快速收敛，其速度优于其他三者。在[55,90]中，IWOA算法收敛速度最优，但从整体上观察，中期过快的收敛速度极易导致其陷入局部最优，可通过引入其他全局搜索策略进行改进；NSGA-II在寻优能力上表现仅次于DHBA，其收敛速度与DHBA 相差无几。

表5两种权重下各算法下的最优解

Tab.5Optimal solution of each algorithm under two kinds of weights   

<html><body><table><tr><td>测试问题</td><td>W1</td><td>W2</td><td>DHBA/106</td><td>时间/s</td><td>NSGA-II/106</td><td>时间/s</td><td>IWOA/106</td><td>时间/s</td><td>HBA/106</td><td>时间/s</td></tr><tr><td rowspan="2">1</td><td>0.5</td><td>0.5</td><td>3.0564</td><td>26.64</td><td>3.1107</td><td>27.01</td><td>3.2461</td><td>34.86</td><td>3.6015</td><td>21.89</td></tr><tr><td>0.8</td><td>0.2</td><td>3.498</td><td>59.76</td><td>3.5693</td><td>48.7</td><td>3.3736</td><td>51.9</td><td>4.081</td><td>44.72</td></tr><tr><td rowspan="2">2</td><td>0.5</td><td>0.5</td><td>3.1938</td><td>73.96</td><td>3.3785</td><td>71.13</td><td>3.3919</td><td>77.24</td><td>3.8239</td><td>67.94</td></tr><tr><td>0.8</td><td>0.2</td><td>3.5409</td><td>102.38</td><td>3.5809</td><td>94.87</td><td>3.6831</td><td>114.56</td><td>4.217</td><td>84.16</td></tr><tr><td rowspan="2">3</td><td>0.5</td><td>0.5</td><td>3.5982</td><td>112.45</td><td>3.646</td><td>122.61</td><td>3.601</td><td>147.75</td><td>3.8333</td><td>130.45</td></tr><tr><td>0.8</td><td>0.2</td><td>3.7311</td><td>154.01</td><td>3.7586</td><td>143.57</td><td>3.7715</td><td>149.32</td><td>4.4025</td><td>155.62</td></tr><tr><td rowspan="2">4</td><td>0.5</td><td>0.5</td><td>3.9883</td><td>136.79</td><td>4.1461</td><td>133.91</td><td>4.1243</td><td>132.7</td><td>4.3761</td><td>122</td></tr><tr><td>0.8</td><td>0.2</td><td>4.399</td><td>169.41</td><td>4.4736</td><td>171.8</td><td>4.4245</td><td>167.21</td><td>4.7791</td><td>163.93</td></tr><tr><td rowspan="2">5</td><td>0.5</td><td>0.5</td><td>4.5498</td><td>235.87</td><td>4.5875</td><td>223.9</td><td>4.5617</td><td>253.12</td><td>4.676</td><td>273.12</td></tr><tr><td>0.8</td><td>0.2</td><td>4.7932</td><td>301.44</td><td>4.7977</td><td>289.03</td><td>4.8045</td><td>324</td><td>5.037</td><td>310.4</td></tr></table></body></html>

从表5可知，HBA在求解目标问题时，其前期的收敛速度超过了DHBA、NSGA-II与IWOA算法，但却陷入了局部最优。从图4中，可直观的了解到HBA与DHBA最优值的寻取相差较大，但从另一方面验证了引入差分进化原则的有效性，其可有效的改进HBA算法的全局寻优能力。从整体上看，DHBA在最优值选取上表现最优，但其收敛速度还有待加强，后续研究可从HBA中各参数的调整，以及挖掘模式与蜂蜜的动态搜索模式进行改进。

![](images/04b5669761ccec725f582e006a268b645bb7bbcb2d73f437c95ac8ba45d34efb.jpg)  
图4平均函数值与迭代求解时间图  
Fig.4Average function value and iteration solution speed

# 5 结束语

针对生鲜闭环供应链网络鲁棒优化设计问题，建立多目标优化模型，采用DHBA进行求解，具体结论如下：

a)本文建立了以最小网络成本，最小环境影响的多目标函数，并通过模糊折中规划方法对其进行多目标处理，同时使用区间数据鲁棒优化方法对目标函数中的不确定性参数进行优化。

b)在原始HBA算法的基础上，通过引入差分进化变异和交叉策略增强了算法的搜索能力与收敛速度，并将其与NSGA-I、IWOA、原始蜜獾算法在Matlab软件上进行仿真对比，算例结果表明，DHBA算法在处理多目标NP-Hard问题时具有收敛速度快，搜索最优值优势明显等特点。

c)现实中生鲜闭环供应链网络问题涵盖更多的不确定性因素，本文考虑了需求，退货率的不确定性，下一步的研究方向将考虑生鲜供应链网络中的配送时间和生鲜新鲜度对闭环供应链设计时的影响，以确保所研究问题更贴切现实生产。

# 参考文献：

[1]冯颖，王远芳，张炎治，等．随机产出下商务模式对生鲜农产品供应 链运作的影响[J]．系统工程理论与实践，2020,40(10):2631-2647. (FengYing,Wang Yuanfang,Zhang Yanzhi,etal.Influence of business model on fresh agricultural supply chain operation under stochastic output[J]. System Engineering-Theory& Practice,2020,40(10): 2631- 2647.)

[2]马雪丽，赵颖，柏庆国，等．考虑保鲜努力与碳减排努力的生鲜品三 级冷链最优决策与协调[J/OL]．中国管理科学：1-15[2022-03-06]. http://kns.cnki.net/kcms/detail/112835.g320 210926.1435.004.html. (Ma Xueli,Ying Zhao,Qingguo Bai et al.Optimal decision and coordination of fresh products three-stage cold chain considering preservation efforts and carbon emission reduction efforts [J/OL]. Chinese Journal of Management Science:1-15 [2022-03-06]. http://kns. cnkinet/k cms/detail/112835g3202109261435004html.)

[3]Mohammadi H,Ghazanfari M,Pishvaee M S,et al.Fresh-product supply chain coordination and waste reduction using a revenue and preservation technology investment sharing contract:A real-life case study [J]. Journal of CleanerProduction,2019,213:262-282.

[4]闻卉，王先甲，陶建平，等．零售商合作偏好下生鲜农产品供应链的 政府补贴机制与优化策略[J].运筹与管理,2021,186(09):100-106 (Wen Hui，Wang Xianjia,Tao Jianping，et al.Government subsidy mechanism and optimization strategy of fresh agricultural supply chain under retailer cooperative preference [J].Operations Research and Management,201,186 (09):100-106.)

[5]邱慧聪，陈伟炯，梁承姬．基于碳税的生鲜品绿色供应链网络优化 研究[J]．企业经济，2015,418(06):11-16.(Qiu Huicong,Chen Weijiong,Liang Chengji.Research on network optimization of fresh products green supply chain based on carbon tax [J].Enterprise Economics,2015,418 (06): 11-16.)

[6]刘墨林，但斌，马崧萱．考虑保鲜努力与增值服务的生鲜电商供应链最优决策与协调[J]．中国管理科学,2020,190(08):76-88.(LiuMolin，Dan Bin，Ma Songxuan．Optimal decision making andcoordination of fresh supply chain considering preservation effort andvalue-added service [J]. Chinese Journal ofManagement Science,2020,190 (08): 76-88.)

[7]王磊，但斌．考虑零售商保鲜和消费者效用的生鲜农产品供应链协 调[J].运筹与管理,2015,122(05):44-51.(WangLei,Dan Bin.Supply chain coordination of fresh agricultural products considering retailer's preservation and Consumer's utility [J].Operations Research and

Management,2015,122 (05):44-51.)

[8]孙嘉轶，陈伟，杨双飞，等．考虑消费者偏好及公平关切的闭环供应 链决策研究[J/OL].计算机集成制造系统：1-17[2022-03-06]. http://knscnkinet/kcms/detail/115946.tp202 10320.1814.002.html. (Sun Jiayi,Chen Wei,Yang Shuangfei,et al.Considering consumer preferences and fairness concerns of closed-loop supply chain decisionmaking research [J/OL]. Computer integrated manufacturing system: 1-   
17 [2022-03-06].http://knscnkinet/kcms/detail/115946.tp.20210320.   
1814.002.html.) [9]张鑫，赵刚，李伯棠．可持续闭环供应链网络设计的多目标模糊规 划问题[J]．控制理论与应用,2020,37(03):513-527.(Zhang Xin, Zhao Gang，Li Botang.Multi-objective fuzzy programming for sustainable closed-loop supply chain network design [J].Control Theory & Applications,2020,37(03): 513-527.) [10]董海，吴瑶．电网中断下基于DWOA的生鲜产品闭环供应链网络多 目标模糊优化设计[J].计算机应用研究，2021,356(06):1694- $1 6 9 8 + 1 7 0 3$ .(Dong Hai,Wu Yao.Multi-objective Fuzzy Optimization design of Fresh Product closed-loop Supply Chain Network based on DWOA under Power grid Interruption [J].Application Research of Computers,201,356 (06): 1694-1698+1703.) [11]朱晨，张骥骧．考虑零售商双渠道和回收品质量的闭环供应链定价 与协调[J]．计算机集成制造系统，2021,283(11):3318-3328.(Zhu Chen,Zhang Jixiang.Pricing and coordination in closed-loop Supply chain with Retailer dual channel and Recycled Product Quality [J]. Computer Integrated Manufacturing Systems,2021,283 (11):3318-   
3328.) [12]王道平，梁思涵，王婷婷．信息非对称下考虑制造商回收行为的闭 环供应链协调[J].控制与决策，2021,36(07):1723-1731.(Wang Daoping,Liang Sihan，Wang Tingting. Coordination of closed-loop supply chain considering manufacturer's recycling behavior under information asymmetry [J].Control and Decision,2021,36 (07):1723-   
1731.)   
[13] Yavari M,Geraeli M.Heuristic method for robust optimization model for green closed-loop supply chain network design of perishable goods [J]. Journal of Cleaner Production,2019,226:282-305.   
[14] Dey S.K,Giri B.C.Analyzing a closed-loop sustainable supply chain with duopolistic retailers under different game structures [J].CIRP Journal of Manufacturing Science and Technology,2021,33:222-233.   
[15] Tirkolaee EB,Goli A,Ghasemi P,et al. Designing a sustainable closedloop supply chain network of face masks during the COVID-19 pandemic:Pareto-based algorithms [J].Journal of Cleaner Production, 2022,333:130056.   
[16] Mogale D G,De A,Ghadge A,et al.Multi-objective modelling of sustainable closed-loop supply chain network with price-sensitive demand and consumer's incentives[J].Computers& Industrial Engineering,2022,168:108105.   
[17] Fathollahi-Fard A M,Dulebenets MA,Hajiaghaei-Keshteli M,et al. Two hybrid meta-heuristic algorithms for a dual-channel closed-loop supply chain network design problem in the tire industry under uncertainty [J].Advanced Engineering Informatics,2021,50:101418.   
[18] Hashim FA, Houssein E H,Hussain K,et al. Honey Badger Algorithm: New metaheuristic algorithm for solving optimization problems [J]. Mathematics and Computers in Simulation,2022,192:84-110.   
[19]Han E,Ghadimi N.Model identification of proton-exchange membrane fuel cells based on a hybrid convolutional neural network and extreme learning machine optimized by improved honey badger algorithm [J]. Sustainable Energy Technologies and Assessments,2022,52:102005.   
[20] Wadhwa V,Ravindran A.R. Vendor selection in outsourcing. Computers & Operations Research,2007,34(12):3725-3737.   
[21] Bertsimas D, Sim M. The price of robustness [J]. Operations research, 2004,52 (1):35-53.   
[22] Li,S.H.；Luo,X.H.；Wu,L.Z.An improved whale optimization algorithm for locating critical slip surface of slopes.Advances in Engineering Software,2021,157:103009.