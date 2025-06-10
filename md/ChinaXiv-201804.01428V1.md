# 云制造环境下面向多目标优化的虚拟资源调度研究

夏世洪，石宇强，吴双，陈柏志(西南科技大学 制造科学与工程学院，四川 绵阳 621010)

摘要：为解决云制造环境下虚拟资源调度存在的算法求解效率不高、模型建立缺乏考虑任务间关系约束和任务间及子任务间的物流时间及成本因素等不足，构建了兼顾交货期时间最小化、服务成本最低化、服务质量最优化为目标的多目标虚拟资源调度模型；采用一种基于项目阶段的双链编码方式进行编码，并提出自适应交叉与变异概率公式，以避免交叉、变异概率始终不变导致算法效率下降与过早收敛的问题；在此基础上利用基于项目阶段的多种交叉变异策略相结合的改进遗传算法进行求解，保证了算法的全局与局部搜索性能。实例结果表明，相比于传统的模型与算法，该模型适用性更强，改进的遗传算法在求解效率、准确度与稳定性方面均有较大提高。

关键词：云制造；虚拟资源调度；多目标；改进的遗传算法 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.12.0819

# Research on virtual resources scheduling for multi-objective optimization in cloud manufacturing environment

Xia Shihong, Shi Yuqiang†,Wu Shuang, Chen Baizhi (SchoolofManufacturingScience&Engineering,Southwest UniversityofScience&Technology,MianyangSichuan 61010, China)

Abstract:In virtual resources schedulingofcloud manufacturing，algorithms wereoften ineficient;relationalconstraints betweentasks,aswellaslogisticstime andcostbetweentasksandsub-tasks,werenotfullyconsideredwhile modeling.Inrder to solvetese problems,this paperconstructeda multi-objective virtualresources scheduling model with thegoalof minimizing thedeliverytime,minimizingtheservicecostandoptimizingthequalityofservice.Weusedadouble-strandedcoding method based on project stage,and proposedanadaptivecrossoverand mutationprobabilityformula,soastoavoidthe loweffciency or premature convergence of algorithm caused bythe invariance of crossver and mutation probability.On this basis,to guarantethe global and local search algorithm performance,we used an improved genetic algorithm combined with multiple crosover and mutation strategies based on project phase.The example shows that our model is more applicable than the traditionalones,and theimproved geneticalgorithm hasconsiderable improvementin eficiency,accuracyandstability. Kev words: cloud manufacturing: virtual resources scheduling: multi-obiective: improved genetic algorithm

# 0 引言

云制造是基于云计算的思想[I]，融合大数据、先进制造技术、语义Web、物联网技术等新兴技术发展而来的一种为制造全生命周期过程提供高效低耗、按需使用以及跨地域制造的制造新模式[2]。作为云制造重点研究之一的资源调度问题，其针对的是分布于不同地域间的任务调度，调度范围广且约束更为复杂；此外，云制造环境下包含巨量的制造资源与制造服务，其调度涉及制造全生命周期不同粒度的制造任务和制造资源[3].因此，相比于传统调度问题，云制造模式下的调度问题更加复杂且不易控制，属于大规模调度问题。

目前，云制造环境下虚拟资源调度问题的研究大致可分为以下方法：a)面向虚拟资源的搜索与匹配方法[4-6]，该类方法能较好地解决制造任务与制造资源间的匹配问题，但缺少对制造服务时间、资源利用率及负载均衡度等方面的考虑[7；b)基于调度模型的方法[8-10]，该类方法考虑了实际调度因素并建立了实际的调度模型，但是存在求解效率不高、搜索速度相对较慢的问题，对于大规模求解问题具有局限性；c面向多目标优化的方法[II-12]，该类方法综合考虑了用户多目标的调度需求，能够求解出较优的调度结果，但是大多对模型进行了简化处理，很少考虑任务之间的约束关系，对任务间的物流传输成本、传输时间进行简化或者不予考虑。

上述研究中缺乏对实际因素的考虑，建立的调度模型忽略任务间关系约束与任务间及子任务间的物流时间、成本因素，且存在算法求解效率较低等不足，无法适应云制造平台的实际运作。因此，本文针对以上不足，构建了兼顾交货期时间最小化、服务成本最低化、服务质量最优化为目标的多目标虚拟资源调度模型；采用一种基于项目阶段的双链编码方式，并提出了自适应的交叉与变异概率公式[13-15]，在此基础上利用基于项目阶段的多种交叉变异策略相结合的改进遗传算法进行求解，最后以实例验证了该模型的适用性及该算法的有效性。

# 1 问题分析

云制造平台上的制造项目可分解成由多个任务组成的任务集，每个制造任务可分解为由若干子任务组成的子任务集。制造任务间存在关系约束，子任务之间存在时序约束。按照制造要求，子任务可随机选择特定的候选资源进行制造服务。同一时间同一制造资源只能执行一项制造任务。由于制造资源在不同地理位置的企业上提供制造服务，因此子任务的制造时间、成本、质量，物流时间、成本会随着所选的制造服务的不同而变化。调度的最终目标是确定子任务所选的候选资源，以及其在候选资源上的加工时间节点以及相应的加工顺序，以使得制造项目的总调度时间、总调度成本、总调度质量均达到最优化。

以制造项目G为例，用户向云制造平台发出制造申请，云制造平台将制造项目G进行封装并发布，设置包括最迟交货期时间 $T _ { \mathrm { m a x } }$ 、最高服务成本 $C _ { \mathrm { m a x } }$ 和最低服务质量 $Q _ { \mathrm { m i n } }$ 等制造要求。然后，根据相关制造要求，将制造项目G分解为 $n$ 个制造任务，制造任务具有不同的阶段划分，每个制造任务可向下分解为 $m _ { i }$ 个子任务。如图1所示。

1,子任务 $F _ { i j }$ 在制造资源k上加工 ijk= 0,子任务 $\cdot F _ { i j }$ 不在制造资源k上加工

# 2.1模型参数定义

$n$ ：制造任务数  
$m _ { i }$ :制造任务 $F _ { i }$ 的子任务数  
$l _ { i j }$ :制造子任务 $F _ { i j }$ 可选制造服务数  
$\mathbf { \xi } _ { l }$ ：可选制造服务集合  
$T$ ：总调度时间  
$c$ :总调度成本  
Q:总调度质量  
Tmax :制造项目所允许的最迟交货时间  
$C _ { \mathrm { m a x } }$ :制造项目所规定的最大成本  
$Q _ { \mathrm { m i n } }$ ：为制造项目所规定的最低服务质量  
$t _ { i j k }$ ：子任务 $F _ { _ { i j } }$ 在候选资源 $k$ 上的制造时间  
tjk:子任务Fij在候选资源k上的物流时间  
$c _ { i j k }$ ：子任务 $F _ { _ { i j } }$ 在候选资源 $k$ 上的制造成本  
Cijk :子任务Fi在候选资源k上的物流成本  
$q _ { i j k }$ ：子任务 $F _ { _ { i j } }$ 在候选资源 $k$ 上的加工满意度  
$e _ { i j k }$ ：制造服务每次评价得分值  
$s$ ：历史评价次数  
$t _ { e , i j }$ ：子任务 $F _ { i j }$ 的加工结束时间  
$t _ { e , i j } ^ { ' }$ ：子任务 $F _ { _ { i j } }$ 的物流时间  
$t _ { s , i j }$ ：子任务 $F _ { _ { i j } }$ 的开始时间  
$h _ { i }$ ：任务 $F _ { i }$ 的紧前任务集合  
h:h中的第u个任务  
miu:任务hiu的最后一个子任务

![](images/a8ed0c6c09c0523f4aad0220f9d6e34dbfd27d453737dbf105a6c8e3b9e2c1b5.jpg)  
图1任务分解层次关系

# 2.2 目标函数

构建总调度时间最小化、总调度成本最低化、总调度质量最优化的目标函数，其中总调度时间包括制造项目的加工时间及物流传输时间两部分，总调度成本包括制造项目的加工成本及物流传输成本两部分，总调度质量主要依照用户的满意度来体现，及对子任务加工满意度之和。

$$
T = \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m _ { i } } \sum _ { k = 1 } ^ { l _ { i j } } x _ { i j k } \times ( t _ { i j k } + \dot { t _ { i j k } } )
$$

$$
C = \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m _ { i } } \sum _ { k = 1 } ^ { l _ { i j } } x _ { i j k } \times ( c _ { i j k } + c _ { i j k } ^ { ' } )
$$

$$
Q = \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m _ { i } } \sum _ { k = 1 } ^ { l _ { i j } } x _ { i j k } \times q _ { i j k }
$$

$$
q _ { i j k } = \sum _ { k = 1 } ^ { s } e _ { i j k } \mathrm { ~ / ~ } s
$$

# 2 多目标调度优化模型

# 2.3 约束条件

调度过程中的约束条件如下：

S.t.

制造项目可分解为 $n$ 个制造任务 $F _ { i } ( i = 1 , 2 , \cdots , \mathrm { n } )$ ，制造任务 $F _ { i }$ 可分解为 $m _ { i }$ 个子任务 $F _ { i j } ( j = 1 , 2 , \cdots , \mathfrak { m } _ { i } )$ ，子任务 $F _ { _ { i j } }$ 有 $l _ { i j }$ 个可选制造服务 $( l _ { i j } \in l )$ 。决策变量：

$$
\begin{array} { c } { T _ { \mathrm { m a x } } \geq T } \\ { C _ { \mathrm { m a x } } \geq C } \end{array}
$$

$$
Q _ { \mathrm { m i n } } \leq Q
$$

$$
t _ { e , i j } + t _ { e , i j } ^ { ' } \le t _ { s , i ( j + 1 ) }
$$

$$
\operatorname* { m a x } _ { h _ { i u } \in h _ { i } } \left\{ t _ { e , h _ { i u } m _ { i u } } + t _ { e , h _ { i u } m _ { i u } } ^ { ' } \right\} \leq t _ { s , i 1 }
$$

$$
\sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m _ { i } } \sum _ { k = 1 } ^ { l _ { i j } } x _ { i j k } \leq 1 \
$$

式(5)表示制造项目交货期约束，式(6)表示制造项目成本约束，式(7)表示制造项目质量约束，式(8)表示制造子任务时序约束，即子任务的开始时间不能早于其紧前子任务的结束时间与物流时间之和，式(9)表示制造任务的关系约束，即制造任务的开始时间不能早于所有紧前任务最后一个子任务的结束时间与物流时间之和的最大值，式(10)表示制造任务资源约束，即一个制造资源同一时刻只允许加工一个制造任务。

# 3 改进的遗传算法设计

# 3.1改进的遗传算法流程

改进的遗传算法流程如图2所示。首先初始化制造项目及算法的参数，然后对项目进行阶段分解，分别对服务选择链和子任务顺序链进行编码并初始化种群。在此基础上解码并计算适应度值，如果满足终止条件，则算法结束，否则进行遗传操作。遗传操作中选择策略包括随机一致性选择与精英保留相结合的策略；交叉概率与变异概率通过自适应生成，根据自适应交叉与变异概率进行基于项目阶段的交叉操作与变异操作。遗传操作后产生新一代种群，此时，计算适配值，判断是否满足终止条件。

![](images/839a5be8ba286bb84754fc16ffadff771fedbdb2f3a26d28c273c5ad8b033d0c.jpg)  
图2改进的遗传算法流程

# 3.2 编码

根据调度模型的特点，本文采用基于项目阶段的双链编码[16]方式进行编码：第一条编码表示子任务 $F _ { _ { i j } }$ 所对应的子任务顺序链。第二条编码表示子任务 $F _ { i j }$ 所对应的服务选择链。针对子任务顺序链，首先，依据阶段顺序进行排序，然后按照阶段顺序对阶段内的子任务顺序进行随机编码，每个编码位对应相应的任务号；针对服务选择链，在子任务顺序链编码确定的情况下，对相应子任务随机选择其候选服务进行编码，每个编码位对应该子任务候选服务序号。整条编码中任务号出现的次数与子任务数相等，同时，服务选择链与子任务顺序链的长度相等，基于项目阶段的双链编码结构如表1所示。

表1基于项目阶段的双链编码结构  

<html><body><table><tr><td>项目阶段 1 2 3 4</td></tr></table></body></html>

# 3.3自适应交叉概率与变异概率

针对传统遗传算法在整个求解过程中交叉概率与变异概率始终不变导致算法效率下降与过早收敛的问题，本文设计了自适应的交叉与变异概率公式。

# 3.3.1自适应交叉概率

在算法迭代初期，进化代数较小，种群中个体差异较大，通过增加交叉概率可以使算法快速收敛，增强算法的性能；而在迭代后期，进化代数接近最大遗传代数，种群中个体趋于一致，个体间距离较小，通过减小交叉率可以避免破坏优良基因结构，从而使算法可以快速收敛。自适应交叉率公式如下：

$$
P _ { c ( t ) } = \Big ( F _ { e } ^ { 2 } + F _ { c } ^ { 2 } \Big ) ^ { \frac { 1 } { 2 } } \times ( 1 - \frac { D _ { a \nu g } } { D _ { \mathrm { m a x } } } ) \times ( 1 - \frac { t } { T } )
$$

$$
F _ { e } = ( F _ { \operatorname* { m a x } } - F _ { a \nu g } ) / ( F _ { \operatorname* { m a x } } - F _ { \operatorname* { m i n } } )
$$

$$
F _ { _ c } = ( F _ { \operatorname* { m a x } } - F _ { _ { ( x ) } } ) / ( F _ { \operatorname* { m a x } } - F _ { \operatorname* { m i n } } )
$$

其中：Pe()表示第t代的交叉概率，t表示遗传代数，Fmax、Fmin分别表示最大适应度值和最小适应度值， $F _ { \alpha \nu g }$ 表示平均适应度值， $F _ { ( x ) }$ 表示两父代交叉个体中较大的适应度值， $D _ { a \nu g }$ 表示种群间的平均欧式距离， $D _ { \mathrm { m a x } }$ 表示种群间最大的欧氏距离。

# 3.3.2自适应变异概率

对于适应度较高的个体应赋予较小的变异概率，使其优良基因不会因变异而受到破坏；而对于适应度较低的个体应增大其变异概率从而增大种群的搜索能力。在迭代初期，群体多样性较大，因而需要较小的变异率以使算法快速收敛，而在迭代后期，群体趋于一致，种群中个体间的个体差异较小，因此需要增大其变异率，以免算法限于局部最优。自适应变异率公式如下：

$$
P _ { _ { m ( t ) } } = \frac { F _ { _ m } } { 1 + F _ { e } } \times \frac { D _ { _ { a \nu g } } } { D _ { _ { \mathrm { m a x } } } } \times \frac { \arctan ( t ^ { \frac { 1 } { 2 } } ) } { \pi }
$$

$$
F _ { m } = ( F _ { \operatorname* { m a x } } - F _ { \ O _ { ( x ) } } ) / ( F _ { \operatorname* { m a x } } - F _ { \operatorname* { m i n } } )
$$

其中： $P _ { m ( t ) }$ 表示第 $\mathbf { \Phi } _ { t }$ 代的变异概率， $\mathbf { \chi } _ { t }$ 表示遗传进化代数， $F _ { \left( x \right) }$ 表示个体的适应度值，Davg表示种群间的平均欧式距离，Dmax表示种群间最大的欧氏距离。

# 3.4适应度函数与选择策略

# 3.4.1适应度函数

云制造模式下的多目标优化调度模型的目标函数为交货期，成本和质量。三个目标间存在相互矛盾关系且有着不同的量纲，

需要对各目标进行归一化处理。首先，对各目标函数进行无量纲化处理，然后采用优先权值设置法将多目标转换为单目标。转换公式如下：

$$
F = \omega _ { 1 } T _ { n o r m } + \omega _ { 2 } C _ { n o r m } + \omega _ { 3 } Q _ { n o r m }
$$

$$
\omega _ { 1 } + \omega _ { 2 } + \omega _ { 3 } = 1
$$

$$
T _ { n o r m } = \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m _ { i } } \frac { T _ { i j } - T _ { \operatorname* { m i n } } } { T _ { \operatorname* { m a x } } - T _ { \operatorname* { m i n } } }
$$

$$
C _ { n o r m } = \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m _ { i } } \frac { C _ { i j } - C _ { \operatorname* { m i n } } } { C _ { \operatorname* { m a x } } - C _ { \operatorname* { m i n } } }
$$

$$
Q _ { n o r m } = \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { m _ { i } } \frac { Q _ { \operatorname* { m a x } } - Q _ { i j } } { Q _ { \operatorname* { m a x } } - Q _ { \operatorname* { m i n } } }
$$

其中： $F$ 表示归一化后的适应度函数值， $\omega _ { 1 }$ 、 $\omega _ { 2 }$ 、 $\omega _ { 3 }$ 分别表示三个目标函数的权值， $T _ { n o r m } \setminus \ C _ { n o r m } \setminus \ Q _ { n o r m }$ 分别表示归一化处理后的总调度时间、总调度成本与总调度质量，Ti、Ci、Qij分别表示子任务 $F _ { _ { i j } }$ 的加工或物流时间、加工或物流成本、加工质量， $T _ { \mathrm { m a x } }$ ， $T _ { \mathrm { m i n } }$ ， $C _ { \mathrm { m a x } }$ ， $C _ { \mathrm { m i n } }$ ， $Q _ { \mathrm { m a x } }$ ， $Q _ { \mathrm { m i n } }$ 分别表示个体中子任务最大加工或物流时间、最小加工或物流时间、最高加工或物流成本、最低加工或物流成本、最高加工质量以及最低加工质量。

# 3.4.2选择策略

本文使用结合随机一致性选择和精英保留策略[16]的选择策略，其基本流程如下：a）根据种群中个体的适应度函数，计算个体的选择概率与累积概率;b）每选择一个个体，产生0到步长间的初始随机数（步长为种群规模的倒数)，并加上步长的倍数产生随机数进行选择；c）重复进行 $N I N D \times G G A P$ 次步骤b)，得到数量为$N I N D \times G G A P$ 个个体的下一代种群,其中 NIND 为种群规模，GGAP为代沟；d）将当代种群NIND按适应度值从大到小进行排序，并将排序后的种群均分为 $p$ 个子种群;e）将 $p$ 个子种群中适应度最大的个体代替下一代种群中适应度值最小的 $p$ 个个体，生成新种群。

# 3.5 交叉变异策略

交叉操作与变异操作均是在基于项目阶段的基础上进行，即首先随机选择一个或多个需要进行交叉或变异的项目阶段，再对选中阶段执行交叉操作或变异操作。交叉策略分为服务选择链交叉和子任务顺序链交叉。本文采用基于项目阶段的部分匹配交叉与一致交叉联合使用的策略进行服务选择链的交叉操作，采用基于项目阶段的线性次序交叉与改进优先操作交叉[17]相结合的策略进行子任务顺序链的交叉操作。

变异策略分为服务选择链的变异与子任务顺序链变异，对于服务选择链，采用基于项目阶段的基本位变异策略进行变异操作；而对于子任务顺序链，采用基于项目阶段的逆转变异策略进行变异操作。

# 4 算法实现

算法实现步骤如下：

a）初始化参数，种群个体数量为1000，最大遗传代数为  
100，代沟0.9，交货期权重、成本权重、质量权重分别为0.45、  
0.4和0.15;b）将各目标进行归一化处理得到适应度函数 $F i t N$ ，计算  
种群中个体的适应度函数值；c）采用随机一致性选择策略进行选择操作，并且采用精英  
保留策略保存父代中优秀个体；d)进行交叉变异操作，根据自适应交叉变异概率公式确定  
交叉概率与变异概率，按照交叉概率 $P _ { c ( t ) }$ 采用基于项目阶段的  
多种交叉联合使用的策略随机对个体进行交叉操作，按照变异  
概率 $P _ { m ( t ) }$ 采用基于项目阶段的变异策略对个体进行变异操作；e）根据适应度值排序选择最优个体，若满足收敛条件，结  
束返回最优解，否则退回步骤a);f）对最优个体进行解码，转换为调度结果。

# 5 实例验证

以汽车零部件生产项目为例验证本文模型的适用性及算法的有效性。汽车车门生产项目包括设计、制造、检测、组装等生产阶段，设计阶段（阶段1）包含3个任务 $\left\{ F _ { 1 } , F _ { 2 } , F _ { 3 } \right\}$ ，生产阶段（阶段2）包含6个任务 $\left\{ F _ { 4 } , F _ { 5 } , F _ { 6 } , F _ { 7 } , F _ { 8 } , F _ { 9 } \right\}$ ，检测阶段（阶段3）包含4个任务 $\left\{ { { F } _ { 1 0 } } , { { F } _ { 1 1 } } , { { F } _ { 1 2 } } , { { F } _ { 1 3 } } \right\}$ ，组装阶段（阶段4）包含1个任务 $\left\{ F _ { 1 4 } \right\}$ ，每个任务均包含2个子任务，任务间的关系约束如图3所示，服务所属企业如表2所示，企业间物流时间及成本如表3所示，候选资源在资源调度中数据如表4所示：

![](images/9dbfa7a0b65b4ed116c42430d4d270f42fd310b577d4be89a42c38ed58c360aa.jpg)  
图3任务间关系约束

表2服务所属企业  

<html><body><table><tr><td>企业</td><td>服务号</td></tr><tr><td>E1</td><td>1,5</td></tr><tr><td>E2</td><td>3</td></tr><tr><td>E3</td><td>2.8</td></tr><tr><td>E4</td><td>4,9</td></tr><tr><td>E5</td><td>6,7</td></tr></table></body></html>

表3企业间物流时间及成本（上、下三角分别表示时间、成本)  

<html><body><table><tr><td>企业</td><td>E1</td><td>E2</td><td>E3</td><td>E4</td><td>E5</td></tr><tr><td>E1</td><td>0</td><td>10</td><td>9</td><td>7</td><td>8</td></tr><tr><td>E2</td><td>28</td><td>0</td><td>11</td><td>6</td><td>8</td></tr><tr><td>E3</td><td>24</td><td>27</td><td>0</td><td>3</td><td>5</td></tr><tr><td>E4</td><td>21</td><td>13</td><td>9</td><td>0</td><td>12</td></tr><tr><td>E5</td><td>18</td><td>18</td><td>12</td><td>26</td><td>0</td></tr></table></body></html>

表4候选资源在资源调度中的部分数据  

<html><body><table><tr><td colspan="6">任务子任务紧前任务子任务数可选服务加工时间(h)加工成本(元)加工质量(满意度)</td></tr><tr><td rowspan="3">1 2 1</td><td>1</td><td rowspan="3">2</td><td>1,2,3 21,26,22</td><td>33,27,32</td><td>117,83,108</td></tr><tr><td></td><td>1,2,5 30,22,26</td><td>23,32,27</td><td>67,108,87</td></tr><tr><td></td><td>2,3,4 22,22,26</td><td>32,31,27</td><td>111,107,85</td></tr><tr><td rowspan="2">2</td><td>2</td><td rowspan="2">2</td><td>1,3,9</td><td>21,27,23</td><td>34,26,31</td><td>120,80,106</td></tr><tr><td></td><td>2,5,7</td><td>29,25,25</td><td>24,28,29</td><td>71,90,93</td></tr><tr><td rowspan="2">3</td><td>1 2</td><td>2</td><td>1,5,9</td><td>29,28,21</td><td>24,25,33</td><td>69,76,116</td></tr><tr><td>1</td><td></td><td>3,4,8</td><td>29,22,22</td><td></td><td></td></tr><tr><td rowspan="2">4</td><td>2</td><td>1 2</td><td>1,4,6</td><td></td><td>24,31,32</td><td>72,106,112</td></tr><tr><td></td><td></td><td></td><td>26,22,30</td><td>27,32,24</td><td>86,108,68</td></tr><tr><td rowspan="2">5</td><td>1</td><td>2 2</td><td>2,7,8</td><td>27,24,22</td><td>26,29,33</td><td>80,96,114</td></tr><tr><td>2</td><td></td><td>3,4</td><td>24,27</td><td>29,26</td><td>95,78</td></tr></table></body></html>

根据本文创建的调度模型，结合改进的遗传算法，采用MATLAB编程进行运算，初始化参数设置如下：种群个体数目为1000，最大遗传进化代数为100，代沟0.9，交货期权重为0.45，成本权重为0.4，质量权重为0.15。得到调度的甘特图与多目标函数变化曲线如图4与图5所示，为验证本模型的适用性，结合上述实例，对比未考虑任务间关系约束和任务间与子任务间物流时间及成本的传统模型，结果如表5所示。

![](images/9df36c1e431c4fd1b4e037346693c355da50fac9f2df3f7a06129275846cc841.jpg)  
图4调度甘特图

由图4可以得到子任务所选择的最佳制造服务与子任务的加工顺序及相应的加工时刻。由图5可以看出，调度的最小服务时间为252h，最低服务成本为1095元，最高服务质量为2639。由表5中本文模型与传统模型运行结果对比可以看出，本文模型求解的最小服务时间与最低服务成本分别为252h和1095元，均高于传统模型的234h与746元，而最高服务质量为2639，相对优于传统模型的2326。这是由于传统模型未考虑任务间关系约束和任务间与子任务间的物流时间与成本因素，而本文模型综合考虑这些因素，虽在求解出的时间及成本上略高于传统模型，但是本文模型更加贴近于实际生产情况，能够更好的适应云制造平台真实调度情况。

![](images/5faf16cc11790e36c5a2401ae33be1f29895c302b24d4ae2b09c6627178e37bf.jpg)  
图5多目标函数变化曲线

表5模型结果对比  

<html><body><table><tr><td></td><td>最小服务时间（h)</td><td>最低服务成本（元)</td><td>最高服务质量</td></tr><tr><td>本文模型</td><td>252</td><td>1095</td><td>2639</td></tr><tr><td>传统模型</td><td>234</td><td>746</td><td>2326</td></tr></table></body></html>

为验证算法的性能，本文针对上述实例，将所提出的改进的遗传算法和传统的遗传算法进行性能对比分析，结果如表6及图6所示。衡量算法性能与准确度的评价目标分别为求出最优解遗传代数均值与最优解均值，由表6比较可得，分别运行50 次的情况下，改进GA算法与传统GA算法求出最优解遗传代数均值分别为25代与47代，改进GA算法性能相对于传统GA算法提高将近一倍，最优解均值分别为18.1475与18.2577，说明改进的GA算法准确度与稳定性相对于传统GA算法均有大幅度提升，改进的GA 算法能够较快地寻找出全局最优解18.1474，准确度明显高于传统GA算法，而传统GA算法只能找到局部最优解18.1475，得到的最优解不稳定且质量较差。

表6运算结果对比  

<html><body><table><tr><td colspan="5">运行次数 最优解 最优解均值 求出最优解遗传代数均值</td></tr><tr><td>改进GA</td><td>50</td><td>18.1474</td><td>18.1475</td><td>25</td></tr><tr><td>传统GA</td><td>50</td><td>18.1475</td><td>18.2577</td><td>47</td></tr></table></body></html>

根据图6可得，随着遗传进化代数的增加，传统的遗传算法与改进的遗传算法都收敛且趋于稳定，由于改进的遗传算法采用了自适应的交叉概率与变异概率，并结合基于项目阶段的多种交叉变异相结合的策略，使得该算法在迭代初期交叉概率增大，继而快速收敛并使优良结果累积，在20代左右找到接于最优解的次优解18.25，此时种群中解的均值为19，趋向于最优解并且个体间具有较高的适应度，而在迭代后期，变异概率增大，使得算法搜索空间增大从而跳出局部最优并在27代左右找到全局最优解18.1474；相对而言，传统的遗传算法采用单一的交叉变异策略，并且交叉概率与变异概率在整个迭代过程中保持一层不变，因此在迭代初期收敛较慢，在54代左右才找到局部最优解18.19，并且种群中解的均值相对保持较高且个体间适应度较低，而在迭代后期不能够通过有效的变异增大搜索空间从而导致不能找到全局最优解而陷于局部最优。

![](images/3879629b2a3320971116fd84c0a86eceaf8f6b796a4ff50e8c3a1f3bf7c0465b.jpg)  
图6归一化目标函数变化曲线

# 6 结束语

本文在云制造环境下虚拟资源调度问题现有研究存在对调度模型中忽略任务之间关系约束，对任务间及子任务间的物流传输成本、传输时间进行简化以及算法求解效率不高、搜索速度相对较慢等不足的情况下，构建了兼顾考虑分布于不同地理位置的制造资源约束、任务间的关系约束以及任务间及子任务间的物流时间、成本因素的多目标虚拟资源调度模型；采用基于项目阶段的双链编码方式进行编码，显著减少编码时的冗余子任务，结合自适应的交叉变异概率与基于项目阶段的多种交叉变异策略相结合的改进遗传算法进行求解。最后以实例验证了本文模型的适用性与本文算法的有效性。下一步工作将进一步研究云制造环境下的动态资源调度，针对动态调度的特点，建立相应的动态调度策略及模型算法，以期能适应复杂多变的云制造动态调度环境，提高动态调度效率与稳定性，更加贴近于实际情况。

# 参考文献：

[1]Xu Xun. From cloud computing to cloud manufacturing [J].Robotics and Computer Integrated Manufacturing,2012,28 (1): 75-86.   
[2]李伯虎，张霖，任磊，等.云制造典型特征、关键技术与应用[J].计算 机集成制造系统,2012,18(07):1345-1356.   
[3] 熊永华，王静，吴敏，等．面向多目标优化的云制造虚拟资源调度方法 [J]．计算机集成制造系统,2015,21(11):3079-3087.   
[4] 李慧芳，董训，宋长刚．制造云服务智能搜索与匹配方法[J].计算机 集成制造系统,2012,18(07):1485-1493.   
[5]Lartigau J,Nie L,Xu Xiaofei,et al. Scheduling methodology for production service in cloud manufacturing [C]/ Proc of International Joint Conference on Service Sciences.WashingtonDC: IEEE,2012: 34-39.   
[6]Tai Lijun,Hu Rufu, Chen Caowei,et al. Manufacturing resources and demand inteligent matching in cloud manufacturing environment [C]// Proc of the 2nd International Conference on Energy，Environment and Sustainable Development. Washington DC: IEEE,2012: 2101-2104.   
[7]周龙飞，张霖，刘永奎.云制造调度问题研究综述[J].计算机集成制 造系统,2017,23 (06): 1147-1166.   
[8] 张卫，潘晓弘，刘志，等．基于云模型蚁群优化的制造服务调度策略 [J].计算机集成制造系统,2012,18(01):201-207.   
[9] Laili Yuanjun, Zhang Lin, Tao Fei. Energy adaptive immune genetic algorithm for collaborative design task scheduling in cloud manufacturing system[C]//Procof IEEE International Conferenceon Industrial Engineering and Engineering Management.Washington,DC: IEEE,2011: 1912-1916.   
[10] Jian Chengfeng,Wang Yong.Batch task scheduling-oriented optimization modelling and simulation incloud manufacturing[J]. International Journal of Simulation Modelling,2014,13(1): 93-101.   
[11]部丽君，胡如夫，赵韩，等．面向云制造服务的制造资源多目标动态优 化调度[J].中国机械工程,2013,24(12):1616-1622.   
[12] Gen M,Zhang Wenqiang,Lin Lin,et al.Recent advance in hybrid evolutionary algorithms for multi-objective manufacturing scheduling [J]. Computers & Industrial Enginering,2017,112: 616-633.   
[13]杨从锐，钱谦，王锋，等.改进的自适应遗传算法在函数优化中的应用 [J/OL].(2017-03-31) [2017-11-20].htp://kns.cnki.net/kcms/detail/51. 1196. TP. 20170401. 1739.078. html.   
[14]王军强，郭银洲，崔福东，等．基于多样性增强的自适应遗传算法的开 放式车间调度优化[J].计算机集成制造系统,2014,20(10):2479-2493.   
[15]黄江波，付志红．基于自适应遗传算法函数优化与仿真[J].计算机仿 真,2011,28 (05): 237-240.   
[16]郑卫．云制造模式下的云资源服务优化调度研究[D].杭州：浙江大学, 2015.   
[17]赵诗奎．基于遗传算法的柔性资源调度优化方法研究[D].杭州：浙江 大学,2013.