# 基于人工蜂群算法的指控结构适应性调整方法

孙鹏la,²，武君胜1b，陈冠宇2，张杰勇²

(1．西北工业大学 a.计算机学院;b.软件与微电子学院，西安 710072;2.空军工程大学 信息与导航学院，西安710077)

摘要：为应对战场环境的复杂性和不确定性，指挥控制结构的适应性调整成为研究重点。描述了兵力组织的基本实体和指挥控制结构，给出决策实体负载测度的方法，建立两种战场情况下的指挥控制结构适应性调整优化模型，设计求解问题模型的人工蜂群算法，并给出人工蜂群算法的具体步骤和流程，最后进行案例仿真，基于人工蜂群算法的调整方法得到了良好的指控结构调整效果，证明了人工蜂群算法在指挥控制结构适应性调整方面的可行性。

关键词：指挥控制组织；组织结构；适应性调整；人工蜂群算法中图分类号：TP391.9 doi:10.3969/j.issn.1001-3695.2017.09.0919

# Adaptive adjustment of command and control structure based on artificial bee colony algorithm

Sun Pengla, 2, Wu Junshenglb, Chen Guanyu², Zhang Jieyong² (1.a.SchoolofComputer Science,b.SchoolofSoftwareMicro-electronics,Northwestern Polytechnical University,Xi'an 710072,China; 2.Collge of Information & Navigation,Air Force Engineering University,Xi'an 7107, China)

Abstract:Inordertodealwiththecomplexityanduncertaintyofbatlefieldenvironment,theresearchonadaptiveadjustment of command and control structure has become a hotspot.The basic entity and command and control structure of army organizationare introduced.The methodofdecision-making entity'sload measurement is given.And,theoptimization model ofadaptive adjustmentofcommandand control structure is establised under two kindsof batlefield conditionrespectively. Then,artificialbeecolonyalgorithisusedtoolvetisoptiizationproblem.Teoncretestepsand procssofteartificial beecolonyalgorithmare given.Finally,thecase simulation iscarriedout.The adjustment method basedontheartificialbee colonyalgorithmhasobtained agood efectoftheadjustment ofcommandandcontrolstructure,which proves the feasibility of the artificial bee colony algorithm in adapting and adjusting the command and control structure.

Key Words:commandandcontrolorganization;organizational structure;adaptiveadjustment;artificialbeecolonyalgorithm

# 0 引言

兵力组织是一个作战整体，组织中的各个作战单元围绕着特定作战目而紧密联系。在未来复杂多变的信息化战场上，组织面临的环境变化更加激烈和复杂[1]。任务执行过程中，行动计划可能发生改变，也会出现决策实体失效、平台损毁等突发情况[2]。兵力组织需要具备适应性的调整能力，以应对不断变化的战场形势[31，从而在和敌方的对抗中夺取战场的控制权，达到既定的作战目标。

兵力组织的核心表现为兵力组织指控结构，为使兵力组织指控结构能应对动态变化的战场环境，则要求指控结构可以针对战场环境变化进行适应性的调整。为此，文献[3]提出了基于粒度计算的组织结构适应性设计方法；文献[4]考虑了响应时间、平均备份数和负载均衡等参数，采用着色Petri网研究组织结构的适应性调整；文献[5]考虑了在任务需求改变，任务增加等任务变化下的组织结构调整问题。文献[6]提出了基于滚动时域的动态适应性优化方法，提高了决策层结构动态调整的性能。

以上分析表明，当前关于兵力组织指控结构适应性调整问题的研究，已经取得一定的成果，但仍存在着一些局限，其中以下两个方面就需要进一步研究：a)在对组织当前结构的性能进行评估时，往往未把组织过去状态对当前结构所造成的影响作为考虑因素；b)兵力组织内会出现决策实体损毁的情况，目前对损毁后决策实体的接替问题研究较少。针对这两个方面的问题，本文给出了指控结构性能测度方法，在两种战场环境变化的情况下，建立组织结构适应性调整模型，基于人工蜂群算法寻找模型的最优解。

# 1 指挥控制组织

# 1.1 兵力组织的实体

组织内的实体主要包含任务实体(task,T)、平台实体(platform,P)和决策实体(decision-maker,DM)[6]。

a）任务实体也称做战任务或任务，是兵力组织为实现既定作战目标所采取的必要军事行动。在一般的任务一平台关系中，单个任务的完成需要调用一个或多个平台。组织中任务实体的集合，记为 ${ \mathbf { S } ^ { \mathrm { T } } } { = } \{ { \mathrm { T } _ { 1 } } , { \mathrm { T } _ { 2 } } , { \mathrm { . . . } } , { \mathrm { T } _ { N T } } \}$ ， $\mathbf { \Psi } _ { N T }$ 为任务实体的数量。

b)平台实体也称为平台资源或平台，在组织中承载作战资源，是直接执行和完成作战任务的基本单元，如战机编队、步兵连等。组织中平台实体的集合，记为SP={P,，P,.,PNP}，NP为任务实体的数量。

c）决策实体也称为决策单元，是组织中负责实施指挥控制活动的单元，根据决策实体的职责，可把决策实体分为战役决策实体(operational decision-maker,ODM)和战术决 策实体(tacticaldecision-maker,TDM)。战役决策实体是对整个兵力组织进行全局层面的集中控制，战术决策实体控制平台实体执行具体的作战任务。组织中通常只有一个战役决策实体ODM，存在多个战术决策实体。组织中战术决策实体的集合，记为STDM ={TDM,TDM,，TDMND}，ND 为战术决策实体的总数。

# 1.2兵力组织的结构

兵力组织的结构可分为决策层、任务层和平台层，这三层中各个实体之间紧密联系[7]，共同构成了兵力组织的结构，如图1所示。

![](images/97432a0344d4a2ec473834aa179cccb968c635e08e3f6d9322a5e20608326147.jpg)  
图1兵力组织结构

在图1中，兵力组织结构里各实体之间的关系包括了指控关系 $R _ { \mathrm { O D M - T D M } }$ 和 $R _ { \mathrm { T D M - P } }$ 、协作关系 $R _ { \mathrm { T D M - T D M } }$ 、分配关系 $R _ { \mathrm { T - P } }$ 、执行关系 $R _ { \mathrm { T D M - T } }$ 和时序关系 $R _ { \mathrm { T - T } }$ 。指控关系 $R _ { \mathrm { O D M - T D M } }$ 禾 和RTDM-P’分别是指战役决策实体对各战术决策实体的指挥控制关系和战术决策实体对平台实体的指挥控制关系；协作关系 RTDM-TDM‘是指战术决策实体间互相沟通与合作的关系；分配关系Rr-p，是指任务实体和所需平台实体间的需求关系；执行关系RTDM-T’是指战术决策实体对任务实体的执行关系；时序关系 $R _ { \mathrm { { T - T } } }$ ，则是指任务在执行上的先后顺序。

战术决策实体对平台实体的指控关系 $R _ { \mathrm { T D M - P } }$ ,由矩阵$M ^ { \mathrm { T D M - P } } = ( m _ { i j } ^ { \mathrm { T D M - P } } ) _ { N D \times N P }$ 表示，若 $\mathrm { T D M } _ { i }$ 指挥控制平台 $P _ { j }$ ，则$m _ { i j } ^ { \mathrm { T D M - P } } = 1$ ，若 $\mathrm { T D M } _ { i }$ 不指控平台 $P _ { _ j }$ ， $m _ { i j } ^ { \mathrm { T D M - P } } = 0$ 。

战术决策实体间的协作关系RTDM-TDM 可由矩阵$\boldsymbol { M } ^ { \mathrm { T D M - T D M } } = ( m _ { i j } ^ { \mathrm { T D M - T D M } } ) _ { N D \times N D }$ 表示，若 $\mathrm { T D M } _ { i }$ 与 $\mathrm { T D M } _ { j }$ 之间存在协作，则 $m _ { i j } ^ { \mathrm { T D M - T D M } } = 1$ ，否则 $m _ { i j } ^ { \mathrm { T D M - T D M } } = 0$ 。

平台实体对任务实体的分配、处理关系 $R _ { \mathrm { T } - \mathrm { P } }$ ,可由矩阵$\boldsymbol { M } ^ { \mathrm { T - P } } = ( m _ { i j } ^ { \mathrm { T - P } } ) _ { N T \times N P }$ 表示，其中若平台 $P _ { j }$ 被分配执行任务 $T _ { i }$ ，则 $m _ { i j } ^ { \mathrm { { T } - P } } { = } 1$ ，若平台 $P _ { j }$ 未被分配执行任务 $T _ { i }$ ，则 $m _ { i j } ^ { \mathrm { T - P } } { = } 0$ 。

战术决策实体对任务实体的执行关系 $R _ { \mathrm { T D M - T } }$ ，由矩阵$M ^ { \mathrm { T D M - T } } = ( m _ { i j } ^ { \mathrm { T D M - T } } ) _ { N D \times N T }$ 表示，若 $\mathrm { T D M } _ { i }$ 需执行任务 $T _ { j }$ ，则$m _ { i j } ^ { \mathrm { T D M - T } } = 1$ ，若 $\mathrm { T D M } _ { i }$ 不执行任务 $T _ { _ j }$ ，则 $m _ { i j } ^ { \mathrm { T D M - P } } = 0$ 。（20 $\boldsymbol { M } ^ { T - P }$ 和 $M ^ { \mathrm { T D M - P } }$ 确定后， $M ^ { \mathrm { T D M - T } } = ( m _ { i j } ^ { \mathrm { T D M - T } } ) _ { N D \times N T }$ 可由下式确定

$$
m _ { i j } ^ { \mathrm { T D M - T } } = \left\{ \begin{array} { l l } { { 1 , } } & { { \dddot { \sharp } m _ { i k } ^ { \mathrm { T D M - P } } = 1 , } } \end{array} \right. m _ { j k } ^ { \mathrm { T - P } } = 1 , ~ 1 \leq k \leq N P
$$

任务间的时序关系 $R _ { \mathrm { { T - T } } }$ 可由矩阵 $\boldsymbol { M } ^ { \mathrm { T - T } } = ( \boldsymbol { m } _ { i j } ^ { \mathrm { T - T } } ) _ { N T \times N T }$ 表示，若 $\mathrm { T } _ { i }$ 是 $\mathrm { T } _ { j }$ 的直接前导任务，则 $m _ { i j } ^ { \mathrm { { T - T } } } = 1$ ，否则 $m _ { i j } ^ { \mathrm { { T - T } } } = 0$ 。

# 1.3兵力组织的性能测度

作战过程中，执行同样的行动计划，采用不同的指控结构，战术决策实体的工作负载有所不同。这是因为，不匹配该行动计划的指控结构，组织内各战术决策实体承担的任务差异较大，增加了组织内沟通协作的次数，致使战术决策实体的负载增加。据此，可以根据指控结构中战术决策实体的负载水平来衡量组织指控结构的性能。

下面定义战术决策实体的负载测度。战术决策实体的负载通常分为局部负载和全局负载两类，局部负载又称为任务负载，是战术决策实体在执行其作战任务的过程中指挥控制平台实体，同时与其他战术决策实体进行局部协作而承担的工作负载。

对于 $\forall \mathbf { T D M } _ { i } \in S _ { \mathrm { { T D M } } }$ ，战术决策实体 $\mathrm { T D M } _ { i }$ 执行其负责的某一任务 $T _ { j }$ 时，其指挥控制的平台实体的集合为$S _ { \mathrm { T D M } _ { i } - \mathrm { T } _ { j } } ^ { \mathrm { P } } = \{ P _ { k } \left| m _ { i k } ^ { \mathrm { T D M - P } } = 1 , \ m _ { j k } ^ { \mathrm { T - P } } = 1 , 1 \le \mathrm { k } \le N P \} \right.$ ，在此任务 $T _ { j }$ 上与 $\mathrm { T D M } _ { i }$ 进行协作来完成任务的其他战术决策实体的集合为$S _ { \mathrm { T D M } _ { i } - \mathrm { T } _ { j } } ^ { \mathrm { T D M } } = \left\{ \mathrm { T D M } _ { k } \left| m _ { k j } ^ { \mathrm { T D M - T } } = 1 , k \neq i , 1 \leq k \leq N D \right. \right\}$ ，因此定义 $\mathrm { T D M } _ { i }$ （204号执行任务 $T _ { j }$ 的负载为

$$
\mathbf { W } _ { \mathrm { T D M } _ { i } } ^ { T _ { j } } = { \boldsymbol { \omega } } _ { C 2 } \cdot \left\| \mathbf { S } _ { \mathrm { T D M } _ { i } - \mathrm { T } _ { j } } ^ { \mathrm { P } } \right\| + { \boldsymbol { \omega } } _ { \mathrm { T C } } \cdot \left\| \mathbf { S } _ { \mathrm { T D M } _ { i } - \mathrm { T } _ { j } } ^ { \mathrm { T D M } } \right\|
$$

其中： $\omega _ { C 2 }$ 为指控负载系数， $\omega _ { \mathrm { r c } }$ 是指协作负载系数， $\left. \boldsymbol { S } _ { \mathrm { T D M } _ { i } - \mathrm { T } _ { j } } ^ { \mathrm { P } } \right.$ 是指集合 $S _ { \mathrm { T D M } _ { i } - \mathrm { T } _ { j } } ^ { \mathrm { P } }$ 里元素的数目， $\left. \boldsymbol { S } _ { \mathrm { T D M } _ { i } - \mathrm { T } _ { j } } ^ { \mathrm { T D M } } \right.$ 是指集合 $S _ { \mathrm { T D M } _ { i } - \mathrm { T } _ { j } } ^ { \mathrm { T D M } }$ 里元素的数目。定义 $\mathrm { T D M } _ { i }$ 在整个作战周期里面承受的负载为

$$
\mathbf { W } _ { \mathrm { T D M } _ { i } } ^ { \mathrm { T } } = \sum _ { T _ { j } \in S _ { \mathrm { T D M } _ { i } } ^ { \mathrm { T } } } W _ { \mathrm { T D M } _ { i } } ^ { T _ { j } } + W _ { \mathrm { T D M } _ { i } } ^ { t }
$$

其中： $W _ { \mathrm { T D M } _ { i } } ^ { t }$ 是指 $\mathrm { T D M } _ { i }$ 在时刻 $\mathbf { \Phi } _ { t }$ 之前执行任务所承受的负载。

根据式(4)可以得到组织中所有 $\mathrm { T D M }$ 的负载均方根${ \mathrm { R M S } } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ （Root Mean Square， RMS）。

$$
\begin{array} { r } { \mathrm { R M S } _ { \mathrm { T D M } } ^ { \mathrm { T } } = \sqrt { \displaystyle \frac { 1 } { N D } { \sum _ { i = 1 } ^ { N D } } { \left( W _ { \mathrm { T D M } } ^ { \mathrm { T } } \right) ^ { 2 } } } } \\ { = \sqrt { \left( W _ { \mathrm { T D M } } ^ { \mathrm { T } } \right) ^ { 2 } + \frac { N D - 1 } { N D } D _ { T D M } ^ { \mathrm { T } } } } \end{array}
$$

其中： $\boldsymbol { W } _ { \mathrm { T D M } } ^ { \mathrm { T } } = \frac { 1 } { N D } \sum _ { i = 1 } ^ { N D } \boldsymbol { W } _ { \mathrm { T D M } _ { i } } ^ { \mathrm { T } }$ 是组织中全部 $\mathrm { T D M }$ 的负载均值;  
$D _ { \mathrm { T D M } } ^ { \mathrm { T } } = \frac { 1 } { N D - 1 } { \sum _ { i = 1 } ^ { N D } ( W _ { \mathrm { T D M } _ { i } } ^ { \mathrm { T } } - W _ { \mathrm { T D M } } ^ { \mathrm { T } } ) ^ { 2 } }$ 是全部 $\mathrm { T D M }$ 负载的方差。

（204 ${ \mathrm { R M S } } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 越小，意味着兵力组织中战术决策实体任务负载的均值和方差维持在较低水平，组织结构的设计越合理。故选用负载均方根 ${ \mathrm { R M S } } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 衡量兵力组织指控结构的性能。

# 2 问题描述及建模

在充满多种不确定性因素的战场环境里，各种复杂的情形都有出现的可能，对兵力组织指控结构的性能影响最大的情况主要是行动计划发生改变和战术决策实体遭到破坏而失效两类，因此，本文基于这两类情形，研究兵力组织指控结构的适应性调整问题。

# 2.1 行动计划变化

# 2.1.1问题描述

兵力组织在作战的进程之中，面对战场环境的不确定性，会发生任务增加、平台损毁等突发状况，既定的行动计划会因此发生改变。如果行动计划发生改变，那么原有战术决策实体与平台和任务实体之间的关系，将不能应对新的战场情况，需要对行动计划改变之前的兵力组织指控结构进行适应性调整，以保证在新的行动计划下，调整出最合理的兵力组织指控结构，即性能最优。

# 2.1.2建立模型

行动计划发生改变后，通过调整指挥控制结构可以提升兵力组织的性能，应当注意，性能得到提高的同时，组织结构的变化会给组织的稳定性带来不利影响，这就是组织的调整代价，兵力组织结构的适应性调整，不能超过组织能承受的最大代价。

评估兵力组织指控结构的调整代价需要考虑平台控制权转移的数目 $N P ^ { \mathrm { T r a n s } }$ 。平台控制权转移是指，某一平台实体，在兵力组织指控结构进行适应性调整前，原本受 $\mathrm { T D M } _ { i }$ 指挥控制，调整过后，变为由 $\mathrm { T D M } _ { j }$ 指挥控制，平台实体的指挥控制权发生了转移。调整前战术决策实体与平台实体间的指挥控制关系$R _ { \mathrm { T D M - P } } ^ { \mathrm { l } }$ 可用矩阵 $M _ { 1 } ^ { \mathrm { T D M - P } } = ( m 1 _ { i j } ^ { \mathrm { T D M - P } } ) _ { N D \times N P }$ 来表示，调整变化过后战术决策实体与平台实体间的指控关系 $R _ { \mathrm { T D M - P } } ^ { 2 }$ 可用矩阵（204 $M _ { 2 } ^ { \mathrm { T D M - P } } = ( m 2 _ { i j } ^ { \mathrm { T D M - P } } ) _ { N D \times N P }$ 来表示。

在适应性调整过程里，控制权发生转移的平台数量 $N P ^ { \mathrm { T r a n s } }$ 为

$$
{ \cal N P } ^ { \mathrm { T r a n s } } = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N D } \sum _ { j = 1 } ^ { N P } \Bigl | m 2 _ { i j } ^ { \mathrm { T D M - P } } - m 1 _ { i j } ^ { \mathrm { T D M - P } } \Bigr |
$$

综上，行动计划发生改变的情况下，兵力组织指挥控制结构适应性调整的模型

$$
\begin{array} { c } { \displaystyle \operatorname* { m i n } { \mathrm { R M S } _ { \mathrm { T D M } } ^ { \mathrm { T } } } } \\ { \displaystyle \operatorname* { s . t } . \left. N P ^ { \mathrm { T r a n s } } = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N D } \sum _ { j = 1 } ^ { N P } \left| m 2 _ { i j } ^ { \mathrm { T D M - P } } - m 1 _ { i j } ^ { \mathrm { T D M - P } } \right| \leq \sigma \right. } \\ { \displaystyle \left. \sum _ { i = 1 } ^ { N D } m 2 _ { i j } ^ { \mathrm { T D M - P } } = 1 , j = 1 , 2 , . . . , N P \right. } \end{array}
$$

其中：优化的目标是使 $\mathrm { T D M }$ 的负载均方根 ${ \mathrm { R M S } } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 最小化，负载均方根越小，进行适应性调整后的兵力组织指控结构的性能越优。第一个约束条件表示，调整代价在组织的承受范围以内，$\sigma$ 代表组织所能承受的平台控制权发生转移的最大数目；第二个约束条件表示，组织内每个平台实体仅能由一个战术决策实体进行指挥控制。

# 2.2战术决策实体失效

# 2.2.1问题描述

战场上，兵力组织中的战术决策实体是各种实体中，最受双方关注和打击频率最高的对象。作战过程中，某一战术决策实体受到毁坏而失效后，该战术决策实体所指挥控制的平台实体和执行的任务实体，应当由其他战术决策实体进行接替指挥，并继续执行原来的任务。战术决策实体的损毁，会降低指控结构的性能，但进行适应性调整，选择出合适的替代者，则可以提高受损后指控结构的性能。

# 2.2.2建立模型

假设调整前组织中有 $N D$ 个正常的战术决策实体，战术决策实体与平台实体之间的指挥控制关系 $R _ { \mathrm { T D M - P } } ^ { \mathrm { l } }$ ，可用矩阵（204号 $M _ { 1 } ^ { \mathrm { T D M - P } } = ( m 1 _ { i j } ^ { \mathrm { T D M - P } } ) _ { N D \times N P }$ 表示。某个战术决策实体失效后，战术决策实体数量变为 $N D - 1$ ，失效后的战术决策实体与平台实体间的指控关系 $R _ { \mathrm { T D M - P } } ^ { 2 }$ ，可用矩阵 $M _ { 2 } ^ { \mathrm { T D M - P } } = ( m 2 _ { i j } ^ { \mathrm { T D M - P } } ) _ { ( N D - 1 ) \times N P }$ 表示。记失效的战术决策实体为 $\mathrm { T D M } _ { B }$ ，其指挥控制的平台实体组成的集合为 $S _ { \mathrm { T D M } _ { B } } ^ { \mathrm { P } }$ ，集合中平台实体的数目为 $\boldsymbol { \varepsilon }$ ；有效的战术决策实体指挥控制的平台实体组成的集合为 $S _ { \mathrm { T D M } _ { N D - B } } ^ { \mathrm { P } }$ 。综上，战术决策实体失效后，兵力组织指控结构的适应性调整模型为

$$
\begin{array} { r l } & { \qquad \mathrm { m i n ~ R M S _ { T D M } ^ { T } } } \\ & { \qquad \mathrm { s . t . } \left\{ \begin{array} { l l } { \displaystyle { \sum _ { i = 1 } ^ { N D - 1 } m 2 _ { i j } ^ { \mathrm { { T D M } \mathrm { - } P } } = 1 , \mathrm { P } \in S _ { \mathrm { T D M } _ { N D - B } } ^ { \mathrm { P } } } } \\ { \displaystyle { \sum _ { i = 1 } ^ { N D - 1 } \sum _ { j = 1 } ^ { N P } \left| m 2 _ { i j } ^ { \mathrm { { T D M } \mathrm { - } P } } - m 1 _ { i j } ^ { \mathrm { { T D M } \mathrm { - } P } } \right| = \varepsilon } , \mathrm { P } \in S _ { \mathrm { T D M } _ { N D - B } } ^ { \mathrm { P } } } \end{array} \right. } \end{array}
$$

式(7)中，优化的目标是使 $\mathrm { T D M }$ 的负载均方根 ${ \mathrm { R M S } } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 最小化；第一个约束条件表示调整后的组织内，集合 $S _ { \mathrm { T D M } _ { N D } } ^ { \mathrm { P } }$ 里的每个平台实体仅能由一个战术决策实体进行指挥控制。第二个约束条件表示，在进行调整的过程中，控制权发生转移的平台实体的数目是集合 $S _ { \mathrm { T D M } _ { B } } ^ { \mathrm { P } }$ 中的平台数，即战术决策实体失效后其所有平台控制权发生转移。

# 3 人工蜂群算法

以上两种情况对应的数学模型，本质上都是求解组合优化的问题，可以采用智能算法进行求解。2005年，土耳其Erciyes大学的Karaboga教授，根据蜂群觅食行为的过程，提出了人工蜂群算法(artificial bee colony,ABC)[8]。并在组合优化、路径规划等优化问题上显示出了良好的性能[8\~16]。因此本文选择基于人工蜂群算法对模型进行求解。

# 3.1人工蜂群算法的关键要素

# 3.1.1初始化

遇到突发状况后的战术决策实体与平台实体间的指挥控制关系为 $R _ { \mathrm { T D M - P } } ^ { 1 }$ ，用矩阵 $M _ { \mathrm { 1 } } ^ { \mathrm { T D M - P } }$ 表示。寻找模型的最优解，即找到能使战术决策实体任务负载均方根 ${ \mathrm { R M S } } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 最小的战术决策实体一平台实体系矩阵 $M ^ { \mathrm { T D M - P } }$ ，矩阵的形式如式（8）所示。

$$
\begin{array}{c} M ^ { \mathrm { T ^ { \mathrm { D M - P } } = { [ \begin{array} { l l l l l l } { 0 } & { 0 } & { \cdots } & { 0 } & { \cdots } & { 1 } \\ { 1 } & { 0 } & { \cdots } & { 0 } & { \cdots } & { 0 } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } & { \vdots } & { \vdots } \\ { 0 } & { 0 } & { \cdots } & { 1 } & { \vdots } & { 0 } \\ { \vdots } & { \vdots } & { \cdots } & { \vdots } & { \ddots } & { \vdots } \\ { 0 } & { 1 } & { \cdots } & { 0 } & { \cdots } & { 0 } \end{array} ] } } } \end{array} ] 
$$

$M ^ { \mathrm { T D M - P } }$ 为 $\mathrm { ~ D ~ }$ 行 $\mathrm { ~ \bf ~ P ~ }$ 列的矩阵，其中 $\mathrm { ~ D ~ }$ 和 $\mathrm { ~ \bf ~ P ~ }$ 分别表示遭遇突发状况后指控结构内战术决策实体和平台实体的可用数目，矩阵里 $( i , j )$ 为1代表平台 $\mathrm { \mathbf { P } _ { i } }$ 受战术决策实体 $\mathrm { T D M } _ { j }$ 指挥控制。

结合组织内每个平台实体仅能由一个战术决策实体进行指挥控制的约束条件，以及每个战术决策实体至少指挥控制一个平台实体。生成和 $M _ { \mathrm { 1 } } ^ { \mathrm { T D M - P } }$ 矩阵相比，只有一个平台实体控制权发生转移的所有关系矩阵 $\mathrm { M } { = } \{ \mathbf { \Gamma } M \} ^ { \mathrm { T D M - P } }$ ， $M 2 ^ { \mathrm { { T D M - P } } }$ ..$M N ^ { \mathrm { { T D M - P } } } \}$ ，作为算法的初始解，N为符合条件的关系矩阵总数。

# 3.1.2适应度函数

原有的指挥控制结构在遇到行动计划发生改变和战术决策实体失效的情况后，进行适应性调整。调整的目的是为了得到最优的指控组织结构，以使组织内所有战术决策实体的任务负载均方根 ${ \mathrm { R M S } } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 最小，因而把得到最小的负载均方根作为本算法的优化目标。

$$
\mathrm { m i n \ R M S _ { T D M } ^ { T } }
$$

式（4）给出了目标函数式（9）中 ${ \mathrm { R M S } } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 的详细计算方法。

适应度函数是为了评价解的好坏和作为计算轮盘赌算法选择概率的依据。调整过程中，负载均方根的值越小，说明此解对应的指挥控制结构性能越好，对应的适应度 $\it { f i t _ { i } }$ 越大，因此定义适应度函数如下：

$$
f i t _ { i } = \frac { 1 } { \mathbf { R M S } _ { i } }
$$

${ \mathrm { R M S } } _ { i }$ 为在第 $i$ 个指控战术决策实体一平台实体关系矩阵$M ^ { \mathrm { T D M - P } }$ 下的负载均方根值。

# 3.1.3搜索过程

采用人工蜂群算法求解此问题，在每一次迭代过程内都包含了全局搜索和局部搜索。全局搜索是为了找出进行局部搜索

的解，局部搜索即为邻域搜索。

每次迭代，按照均方根 ${ \mathrm { R M S } } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 由小至大的顺序对 $N$ 个$M ^ { \mathrm { T D M - P } }$ 进行排序，选择排序在前 $N / 2$ 的解，对每个解进行领域搜索，（在本算法里，邻域指的是和当前 $M ^ { \mathrm { T D M - P } }$ 矩阵相比有一个平台的控制权发生转移的矩阵集合，邻域中的可行解同样必须满足约束条件)，邻域搜索采用贪婪准则，计算出邻域内所有$M ^ { \mathrm { T D M - P } }$ 对应的均方根 $\mathrm { R M S } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ ，选取使 ${ \mathrm { R M S } } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 最小的$M ^ { \mathrm { T D M - P } }$ 作为邻域搜索找到的新解，若新解对应的 ${ \mathrm { R M S } } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 优于原解，则用新的 $M ^ { \mathrm { T D M - P } }$ 替代原有解，并与 $M _ { \mathrm { 1 } } ^ { \mathrm { T D M - P } }$ 对比，计算控制权发生转移的平台数是否超出组织结构的承载能力，若超出控制权转移的最大范围则仍保留原解。

解集 M 更新之后，由式（10）计算每个解的适应度 fti，由式（11）计算被观察蜂选中进行搜索的概率。

$$
P _ { i } = \frac { \displaystyle f i t _ { i } } { \displaystyle \sum _ { i = 1 } ^ { N } f i t _ { i } }
$$

根据所有解的概率值，通过轮盘赌的方式在 $N$ 个解中随机选择出 $N / 4$ 个解进行邻域搜索，搜索过后更新解集 $\mathrm { ~ \bf ~ M ~ }$ 。本次迭代结束，以上就是一次迭代的搜索过程。

若未达到最大迭代次数maxCycle，则进入下一次迭代。若达到最大迭代次数，则将本次迭代结束后解集M中使均方根（204号 $\mathrm { R M S } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 最小的 $M ^ { \mathrm { T D M - P } }$ 矩阵作为指控结构适应性调整的结果（204号 $M _ { \mathrm { 2 } } ^ { \mathrm { T D M - P } }$ ,最为本算法得到的最优战术决策实体与平台实体的指控关系，该指控结构的所有战术决策实体任务负载均方根$\mathrm { R M S } _ { \mathrm { T D M } } ^ { \mathrm { T } }$ 是由本文所提算法得到的最小值。

# 3.2人工蜂群算法的基本步骤

人工蜂群算法的型基本步骤如下：

a)初始化蜜蜂种群。设置种群参数，蜜蜂总数 $N$ ，迭代次数 $i t e r { = } 1$ ，最大迭代次数maxCycle，蜜源停留最大限制搜索次数Limit；产生满足约束条件的 $N$ 个TMD-P的0-1矩阵作为初始蜂群;

b)计算种群中每个个体的适应度值，即RMS值；根据适应度值的大小将蜜蜂分为采蜜蜂和观察蜂，适应度值较大的 N/2个个体为采蜜蜂，其余为观察蜂，初始化标志向量，第 $i$ 个蜜蜂的标志向量 $\mathrm { \Delta } t r i a l ( i ) { = } 1$

c)选择较优的 $N / 2$ 个个体进行邻域搜索，新的个体的适应度值优于当前个体则进行替换，否则更新标志向量 trial $( i ) =$ $t r i a l ( i ) \substack { + 1 }$

d)计算观察蜂选择概率向量 $P$ ，利用轮盘赌策略从观察蜂中选择 $N / 4$ 个蜜蜂进行邻域搜索；

e)判断所有蜜蜂的标志向量是否大于Limit。如果第i个蜜蜂的标志向量大于Limit，则舍弃当前解，在解空间随机产生新解，更新标志向量 ${ \mathrm { \Delta } t r i a l { ( i ) } } { = } 1$ ；否则，直接转至步骤 f);

f)记录所有蜜蜂找到的最优解并更新全局最优解；iter=iter+1;

g)判断iter是否大于最大迭代次数maxCycle，如果是则转至步骤h)，否则，转至步骤 b);

h)输出全局最优的解为所要求的TMD-P关系矩阵。  
人工蜂群算法的基本流程如图2所示。

![](images/749d4d778ebf2227479185f97f60497386a449870cddaa260b3587b079540653.jpg)  
图3指控结构适应性调整过程图

# 5 仿真结果及分析

![](images/9772bd797be8c60070a41a9165eb4cb29e07be01acc71d1ad7707815c3d24500.jpg)  
图2算法流程图

# 5.1仿真案例

以文献[17]中提到的联合作战想定为案例，验证人工蜂群算法在兵力组织结构调整中的性能。整个仿真在Windows7系统环境下，用MATLAB2014a进行仿真分析。初始的任务—平台分配关系以及战术决策实体—平台分配关系如表1、2所示。关键参数设置，指控负载系数 $\omega _ { { c 2 } }$ 取1,协作负载系数 $\omega _ { \mathrm { r c } }$ 取2;平台控制权发生转移的最大数目取10。

表1初始的任务一平台关系表  

<html><body><table><tr><td>任务</td><td>分配的平台</td><td>任务</td><td>分配的平台</td></tr><tr><td>T1</td><td>P2,P6,P7,P16</td><td>T10</td><td>P6,P10</td></tr><tr><td>T2</td><td>P1,P2,P15,P19</td><td>T11</td><td>P7,P10,P14</td></tr><tr><td>T3</td><td>P11,P12,P13</td><td>T12</td><td>P4,P7,P12</td></tr><tr><td>T4</td><td>P</td><td>T13</td><td>P8,P11,P16</td></tr><tr><td>T5</td><td>Ps,P14</td><td>T14</td><td>P3,P9,P16</td></tr><tr><td>T6</td><td>P5,P9,P18</td><td>T15</td><td>P5,P13,P17,P20</td></tr><tr><td>T7</td><td>P10,P11,P12,P13,P20</td><td>T16</td><td>P4,P8,P18,P19</td></tr><tr><td>T8</td><td>P3,P5,P9,P18</td><td>T17</td><td>P10,P15</td></tr><tr><td>T9</td><td>P6,P8</td><td>T18</td><td>P4,P17</td></tr></table></body></html>

# 4指控结构适应性调整过程

表2初始的战术决策实体一平台关系表  

<html><body><table><tr><td>战术决策实体</td><td>所属平台</td></tr><tr><td>TDM1</td><td>P1,P10,P11,P14,P15</td></tr><tr><td>TDM2</td><td>P2,P6,P8,P16,P19</td></tr><tr><td>TDM3</td><td>P7,P12,P13,P20</td></tr><tr><td>TDM4</td><td>P3,P4,P5,P9,P17,P18</td></tr></table></body></html>

以上内容对指控结构适应性调整问题中的模型构建和算法求解进行了研究，指控结构适应性调整过程如图3所示。任务执行过程中，发生突发状况后，首先判断事件类型，根据不同类型建立相应的调整模型，然后利用人工蜂群算法进行求解，最后得到调整以后的任务计划。

由表2可以得到如下的初始战术决策实体与平台实体的指控关系矩阵，作为不确定情况发生前的关系矩阵,如表3所示。

表3不确定情况发生前的关系矩阵  

<html><body><table><tr><td></td><td>P1</td><td>P2</td><td>P</td><td>P4</td><td>P5</td><td>P6</td><td>P7</td><td>P8</td><td>P9</td><td>P10</td><td>P11</td><td>P12</td><td>P13</td><td>P14</td><td>P15</td><td>P16</td><td>P17</td><td>P18</td><td>P19</td><td>P20</td></tr><tr><td>TDM1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>TDM2</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td></tr><tr><td>TDM3</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>TDM4</td><td>0</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td></tr></table></body></html>

# 5.2仿真实验

1）行动计划改变

造成行动计划发生改变的因素有任务的完成、任务取消，增加任务，平台增加和损毁，这五种情况随机产生。行动计划发生改变之后，采用人工蜂群算法对第一个优化问题进行求解。以20次实验仿真中的某次实验为例，行动计划改变随机出现的是平台实体 ${ \bf P } _ { 2 }$ 和 ${ \bf P } _ { 3 }$ 损毁后，平台损毁后的TDM-P关系矩阵，如表4所示，作为本次仿真调整前的关系矩 $M _ { \mathrm { 1 } } ^ { \mathrm { T D M - P } }$ 。

通过人工蜂群算法调整之后的关系矩阵为 $M _ { 2 } ^ { \mathrm { T D M - P } }$ ，调整后平台 $\mathbf { P } _ { 7 }$ 的控制权发生转移，由 $\mathrm { T D M } _ { 3 }$ 调整为 $\mathrm { T D M } _ { 4 }$ 进行指控，调整后的关系由表5所示。

本情形下的经过20次实验仿真，仿真结果如表6所示，显示出了调整前后的均方根。

表4调整前的TDM-P关系  

<html><body><table><tr><td></td><td>P1</td><td>P4</td><td>P5</td><td>P6</td><td>P7</td><td>P8</td><td>P9</td><td>P10</td><td>P11</td><td>P12</td><td>P13</td><td>P14</td><td>P15</td><td>P16</td><td>P17</td><td>P18</td><td>P19</td><td>P20</td></tr><tr><td>TDM1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>TDM2</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td></tr><tr><td>TDM3</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>TDM4</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td></tr></table></body></html>

表5调整后的TDM-P关系  

<html><body><table><tr><td></td><td>P1</td><td>P4</td><td>P5</td><td>P6</td><td>P7</td><td>P8</td><td>P9</td><td>P10</td><td>P11</td><td>P12</td><td>P13</td><td>P14</td><td>P15</td><td>P16</td><td>P17</td><td>P18</td><td>P19</td><td>P20</td></tr><tr><td>TDM1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>TDM2</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td></tr><tr><td>TDM3</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>TDM4</td><td>0</td><td>1</td><td>1</td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td></tr></table></body></html>

表6情形1下的性能测度值  

<html><body><table><tr><td>仿真序号</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>调整前</td><td>15.23</td><td>23.23</td><td>27.78</td><td>25.30</td><td>20.29</td><td>30.42</td><td>31.17</td><td>26.49</td><td>36.81</td><td>29.85</td></tr><tr><td>调整后</td><td>5.06</td><td>22.57</td><td>26.75</td><td>24.57</td><td>19.61</td><td>29.96</td><td>29.17</td><td>25.31</td><td>34.82</td><td>28.09</td></tr><tr><td>仿真序号</td><td>11</td><td>12</td><td>13</td><td>14</td><td>15</td><td>16</td><td>17</td><td>18</td><td>19</td><td>20</td></tr><tr><td>调整前</td><td>44.10</td><td>28.62</td><td>31.76</td><td>32.20</td><td>28.86</td><td>35.00</td><td>25.18</td><td>31.30</td><td>26.23</td><td>23.76</td></tr><tr><td>调整后</td><td>42.80</td><td>37.22</td><td>31.44</td><td>31.32</td><td>26.12</td><td>31.92</td><td>23.08</td><td>28.96</td><td>24.27</td><td>22.24</td></tr></table></body></html>

贪心搜索算法(greedy searchalgorithm,GSA)也能较好地用于解决该问题[18]，实验中使用GSA算法和ABC 算法进行对比，对比结果如图4和5所示。

![](images/6e9f7dfa36dfedfad4cbfd7c2e4f94c0c7cf40b51603edbf927adda1b2616d4a.jpg)  
图4性能对比图

![](images/b33a63b45eece58a1c98c6c1990f14e5037197a5e5d9c9d382ac7c8898e0719b.jpg)  
图5时间对比图

从性能测度图上可以看出，使用人工蜂群算法对兵力组织进行调整，可以降低行动计划发生后的RMS值，提高兵力组织结构的性能。

2）决策实体失效

情形2中的情况更为复杂，在情形1的基础上，增加战术决策实体失效的情况。失效的决策实体通过随机选择产生。

在决策实体失效的第20次仿真中，遭遇行动计划发生改变随机增加了一个平台实体和决策实体 $\mathrm { T D M } _ { \mathrm { 1 } }$ 失效后的关系如表7所示。新增加平台实体 $ { \mathbf { P } } _ { 2 1 }$

TDMi失效后的关系如表8所示。

通过人工蜂群算法调整之后的关系矩阵为 $M _ { \mathrm { \Omega _ { 2 } } } ^ { \mathrm { T D M - P } }$ ，平台${ \bf P } _ { 1 1 }$ 的控制权发生转移，由 $\mathrm { T D M } _ { 2 }$ 调整为 $\mathrm { T D M } _ { 3 }$ 指控， $\mathrm { T D M _ { l } }$ 失效后，原平台实体接替指挥后的关系如表9所示。

情形2条件下的20次仿真结果和与GSA算法的对比结果如表10所示。

表7平台新增后的 TDM-P关系  

<html><body><table><tr><td></td><td>P1</td><td>P</td><td>P3</td><td>P4</td><td>P5</td><td>P6</td><td>P7</td><td>P8</td><td>P9 P10</td><td>P11</td><td>P12</td><td>P13</td><td>P14</td><td>P15</td><td>P16</td><td>P17</td><td>P18</td><td>P19</td><td>P20</td><td>P21</td></tr><tr><td>TDM1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0 1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>TDM2</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0 1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td></tr><tr><td>TDM3</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0 1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td></tr><tr><td>TDM4</td><td>0</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0 0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

表8TDMi失效后的TDM-P关系  

<html><body><table><tr><td></td><td>P1</td><td>P</td><td>P</td><td>P4</td><td>P5</td><td>P6</td><td>P7</td><td>P8</td><td>P9</td><td>P10</td><td>P11</td><td>P12</td><td>P13</td><td>P14</td><td>P15</td><td>P16</td><td>P17</td><td>P18</td><td>P19</td><td>P20</td></tr><tr><td>TDM2</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0 0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td></tr><tr><td>TDM3</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td></tr><tr><td>TDM4</td><td>0</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

表9 $\mathrm { T D M _ { l } }$ 失效经调整后的TDM-P关系  

<html><body><table><tr><td></td><td>P1</td><td>P2</td><td>P</td><td>P4</td><td>P5</td><td>P6</td><td>P7</td><td>P8</td><td>P9</td><td>P10</td><td>P11</td><td>P12</td><td>P13</td><td>P14</td><td>P15</td><td>P16</td><td>P17</td><td>P18</td><td>P19</td><td>P20</td><td>P21</td></tr><tr><td>TDM2</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td></tr><tr><td>TDM3</td><td>0</td><td>0</td><td>0</td><td>o</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td></tr><tr><td>TDM4</td><td>0</td><td>0</td><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

表10情形2下的性能测度值  

<html><body><table><tr><td>仿真序号</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>调整前</td><td>37.62</td><td>32.69</td><td>31.43</td><td>32.09</td><td>35.97</td><td>31.31</td><td>28.34</td><td>30.82</td><td>39.86</td><td>29.77</td></tr><tr><td>调整后</td><td>32.82</td><td>27.10</td><td>28.46</td><td>27.79</td><td>30.61</td><td>25.36</td><td>25.07</td><td>26.56</td><td>37.52</td><td>29.52</td></tr><tr><td>仿真序号</td><td>11</td><td>12</td><td>13</td><td>14</td><td>15</td><td>16</td><td>17</td><td>18</td><td>19</td><td>20</td></tr><tr><td>调整前</td><td>32.08</td><td>31.00</td><td>41.08</td><td>35.55</td><td>38.02</td><td>34.45</td><td>32.88</td><td>35.21</td><td>33.97</td><td>31.87</td></tr><tr><td>调整后</td><td>30.72</td><td>27.01</td><td>33.92</td><td>28.21</td><td>31.31</td><td>26.26</td><td>29.84</td><td>31.73</td><td>32.41</td><td>26.43</td></tr></table></body></html>

如图6、7所示，从20次的仿真效果图来看，人工蜂群算法也适用于在情形更加复杂的情况2中，负载均方值降低明显，调整后的组织性能有效提高。

![](images/01acc63747e7760ca5077893383e23d4af501dd60c0a6a3ed33fd68e901917ee.jpg)  
图6性能对比图

![](images/6b7737c57ca813f8470694fa430bcdc625416aed85c608770ac2abe1d3728886.jpg)  
图7时间对比图

# 5.3参数分析

在以上实验中，关键参数设置为，指控负载系数 $\omega _ { C 2 }$ 取1,协作负载系数 $\omega _ { \mathrm { r c } }$ 取2，协作负载系数 $\omega _ { \mathrm { r c } }$ 与指控负载系数@c的比值为2,接下来分析关键参数的权重变化对方法性能的影响。

协作负载系数 $\omega _ { \mathrm { { r c } } }$ 与指控负载系数 $\omega _ { c 2 }$ 的比值，从0.25增大至3，分析参数的变化在两种情形下对ABC调整算法性能的影响。

![](images/71ae652c177b7354db8597a0c7036c2e0781b09713a10d1bef8096de555a8c3b.jpg)  
图8行动计划改变

![](images/fc32fb4a9c834e5f3775c8583b17af1cea07a0ec4b5642f72d9cd948360d26a1.jpg)  
图9决策实体失效

由图8和9两个性能分析图可以看出，随着协作负载系数取值的增大，RMS值上升趋势明显，调整前后RMS的差值变大，即降低幅度变大。这是由于随着协作负载系数的变大，协作负载占总负载的权重增大，通过调整减少了组织内战术决策实体的协作，使得RMS值降低幅度增大。

# 5.4仿真分析

由仿真的结果，本文可以看出，在第一个实验当中，采用ABC算法和GSA算法都能降低战术决策实体的负载均方值RMS,GSA算法的结果稍好于ABC算法，但运行时间上，ABC算法效率更高，算法花费的时间约为GSA算法的三分之一。

第二个仿真中，ABC 算法和GSA算法的运行时间差别不大，ABC算法在大多数仿真里，所花费的时间都小于GSA算法；在性能上，采用 ABC 算法能够更好的减小负载均方值，提高指控结构的性能。

# 6 结束语

本文研究了兵力组织指挥控制结构的调整问题，基于人工蜂群算法的提出了指控结构适应性调整方法，分别在两种情形下对算法进行仿真验证，并和贪心算法进行对比，证明

了人工蜂群算法用在兵力组织调整中的有效性。

# 奓丐乂：

[1]孙昱，姚佩阳，张杰勇.C2 组织信息结构效能测度及综合评估[J]. 系统工程与电子技术,2015,37(6):1313-1318.   
[2]张杰勇，姚佩阳.C2 组织决策实体配置问题建模与求解方法[J]．系 统工程与电子技,2012,34(4):737-742.   
[3]修保新，张维明，刘忠，等.C2 组织结构的适应性设计方法[J]．系 统工程与电子技术,2007,29(7):1102-1108.   
[4]Perdu DM,Levis AH. Adaptation as a Morphing proces: a methodology for the design and evaluation of adaptive command and control teams [J]. Computational& Mathematical Organization Theory,1998,4(1):5-41.   
[5]Levchuk G M, Levchuk Y N,Meirina C,et al.Normative design of organizations part Il:modeling congruent,robust,and adaptive organizations [J].IEEE Trans on Systems,Man,and Cybernetics,2004, 34 (3): 337-50.   
[6]牟亮，张维明，修保新，等．基于滚动时域的C2 组织决策层结构动 态适应性优化[J]．国防科技大学学报,2011,33(1):125-131.   
[7]牟亮．不确定使命环境下C2组织结构动态适应性优化方法研究[D]. 长沙：国防科技大学,2011.   
[8]Karaboga D.An idea based on honey bee swarm for numerical optimization[R].[S.1.]:EngineeringFaculty,ErciyesUniversity,2005   
[9]Karaboga D,Akay B.Artificial bee colony algorithm on training artificial neural networks[C//Proc of the 15th Signal Processingand Communications Applications.2007: 1-4.   
[10]KarabogaD,AkayB.Acomparative studyof Artificial Bee Colony algorithm [J].Applied Mathematicsand Computation,2009,214（1): 108-132.   
[11] Ozturk C,Karaboga D, Gorkemli B.Artificial bee colony algorithm for dynamic deployment of wireless sensor networks [J]. Turkish Journal of Electrical Engineering and Computer Sciences,2012,20 (2): 255-262.   
[12] Karaboga D,Basturk B.On the performance of artificial bee colony (ABC)algorithm[J].Applied Soft Computing,2008,8(1): 687-697.   
[13]Rao RS,Narasimham S,Ramalingaraju M. Optimizationof distribution network configuration for loss reduction using artificial bee colony algorithm[J].International Journalof Electrical PowerandEnergy Systems Engineering,2008,1(2):709-715   
[14]卓涛，詹颖．改进人工蜂群算法的云计算资源调度模型[J].微电子 学与计算机,2014,31(7):147-150.   
[15]魏红凯．人工蜂群算法及其应用研究[D].北京：北京工业大学, 2012.   
[16]霍凤财，杜颖，刘洋．人工蜂群算法及其应用[J].吉林大学学报: 信息科学版,2016(4): 468-476.   
[17] Yu F,Tu F,Pattipati K R. Novel congruent organizational design methodology using group technology and a nested genetic algorithm [J]. IEEE Trans on Systems,Man,and Cybernetics,2006,36(1): 5-18.   
[18]孙昱，姚佩阳，李明辉，等．兵力组织指挥控制结构适应性调整方法 [J]．系统工程与电子技术,2016,38(9):2086-2092.