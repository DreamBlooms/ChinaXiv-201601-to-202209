# 约束多目标进化算法研究进展

朱亚文，周红标，李杨，徐浩渊(淮阴工学院 自动化学院，江苏 淮安 223003)

摘要：约束多目标进化算法(constrained multi-objectiveevolutionary algorithms，CMOEAs)能够同时处理多个相互冲突的目标函数和约束条件，引导种群逼向可行域的最优解，受到了研究者的广泛重视。首先介绍了约束多目标优化问题(constrained multi-objective optimization problems，CMOPs)的相关定义和多目标进化算法(multi-objectiveevolutionary algorithms，MOEAs)的三种分类；其次，系统地分析了当前CMOEAs 中约束处理机制，凝练出当前主要的四种约束处理方法；然后，从基于支配、基于指标、基于分解三个方面对CMOEAs 的研究进展进行了详细综述；最后，指明了CMOEAs存在的挑战和未来研究方向。

关键词：约束多目标优化问题；约束多目标进化算法；基于支配；基于指标；基于分解 中图分类号：TP18 doi:10.19734/j.issn.1001-3695.2022.01.0041

Research progress of constrained mult-iobjective evolutionary algorithms

Zhu Yawen, Zhou Hongbiao†,Li Yang, Xu Haoyuan (FacultyofAutomation,Huaiyin Instituteof Technology,Jiangsu Huai’an 223o03,China)

Abstract: Constrained multi-objective evolutionary algorithms (CMOEAs)can deal with multiple conflicting objective functionsandconstraints simultaneouslyand guide thepopulationtowards theoptimal solutionin thefeasible domain,which has received extensiveatention fromresearchers.This paper firstly introduces therelevantdefinitions ofconstrained multiobjectiveoptimization problems (CMOPs)and three clasifications of multi-objective evolutionary algorithms (MOEAs); secondly,itsystematicallyanalyzes thecurentconstraint proceing mechaisms inCMOEAsandcondenses thecurnt four main constraint procesing methods;Then,the research progressofCMOEAs is reviewed in detail fromthree aspects: dominance-based,index-based,andecompositio-based;fiallthechalengesandfutureresearchirectionsofCOEAs are pointed out.

Key words: CMOPs; CMOEAs; domination-based; indicator-based; decomposition-based

# 0 引言

现实世界的优化问题除了具有多个相互冲突的目标函数之外，还存在各种约束条件[1]。例如：在污水处理多目标优化中，能耗和罚款是常见的两个目标函数，出水氨氮、出水总磷等水质指标的达标排放限定值以及待优化控制变量的上下限常作为不等式约束条件[2]。此外，在车间作业调度[3]、交通路线优化[4、金融投资[5等领域也存在这类带有等式或不等式约束条件的多目标优化问题，它们统称为约束多目标优化问题(constrained multi-objectiveoptimization problems,CMOPs)[67]。对于CMOPs的研究，主要解决以下两个问题：一是如何寻找到一组收敛性好、分布均匀且覆盖完整的近似Pareto解集；二是如何处理约束条件，使得种群更加容易地逼向可行域中的最优解。但是，由于实际工程问题的非线性、高阶性以及不确定性[8]，传统算法难以逼近真实Pareto前沿。此外，由于约束条件的存在，搜索空间中可行区域的结构变得更加复杂，传统优化算法难以有效发现潜在的可行域[9]。

多目标进化算法(multi-objective evolutionaryalgorithms,MOEAs)一次运行能够获取一组待解决MOPs的Pareto最优解，受到研究者广泛重视。根据所采用选择策略的不同，MOEAs大体可以划分为三类：1）基于支配的框架，即采用Pareto支配关系推动种群向真实Pareto前沿进化，典型代表有 NSGA-I[10]、SPEA2[11]、MOPSO[12,13]；2）基于指标的框架，即采用超体积(hypervolume,HV)等性能指标评价解的收敛性和多样性，典型代表有IBEA[14]、SIBEA[15]、HypE[16];3）基于分解的框架，即采用协作的方式将一个MOP分解成一系列的单目标优化子问题[17]，典型代表有C-MOGA[18]、MOGLS[19]、MOEA/D[20]。

上述MOEAs及其变体的开发均是用于解决无约束优化问题。考虑到实际问题一般都带有约束条件，自然想到将约束处理技术集成到MOEAs中，从而形成约束多目标进化算法(constrained multi-objective evolutionary algorithms,CMOEAs)。目前，常用的约束处理技术有惩罚函数法[21]、约束和目标分离法[22]、多目标优化法[23]、混合法[24]等。这些处理技术与MOEAs的有机融合，不仅可以平衡算法的可行性、收敛性和分布性，而且可以显著提升算法的搜索效率。然而，这些方法也存在一些缺陷。例如：惩罚函数法的惩罚参数设置十分困难[25]，约束和目标分离法需要人为设定不同的ε值；多目标优化法的计算量随约束条件数目的增多而呈现指数式增大，混合法在如何集成不同处理机制时缺乏有效理论指导。近几年，研究者陆续提出了基于模糊规则的惩罚函数处理机制[26]无约束搜索和约束搜索动态融合机制[27]、基于双协作档案的约束处理机制[28]等，极大地提升了算法寻找可行域最优解的能力。可见，约束处理技术对CMOPs的高效解决具有至关重要的影响。因此，对CMOEAs领域的研究成果进行整理和分析，并总结现存的问题，展望未来的挑战，是一件非常重

要也是十分必要的研究工作。

本文首先介绍了CMOPs的定义和MOEAs的分类；其次分析了常用的四种约束处理机制的优缺点；然后从基于支配、基于指标、基于分解三个方面对CMOEAs的研究进展进行了详细综述；最后指明了CMOEAs存在的难题和未来研究方向。

# 1 相关工作

# 1.1CMOPs 数学描述

不失一般性，以最小化问题为例，CMOPs可定义为如下形式：

$$
\begin{array} { c } { \operatorname* { m i n } f ( \mathbf { x } ) = \{ f _ { 1 } ( \mathbf { x } ) , f _ { 2 } ( \mathbf { x } ) , . . . , f _ { m } ( \mathbf { x } ) \} } \\ { \quad s . t . \quad \left\{ \begin{array} { l l } { \mathbf { x } = ( x _ { 1 } , x _ { 2 } , . . . , x _ { n } ) \in \Omega \subset \Omega } \\ { g _ { i } ( \mathbf { x } ) \leq 0 , i = 1 , 2 , . . . , r } \\ { h _ { i } ( \mathbf { x } ) = 0 , i = r + 1 , . . . , q } \end{array} \right. } \end{array}
$$

其中， $\Omega \subset R ^ { n }$ 是决策空间， $f _ { 1 } ( \mathbf { x } ) , f _ { 2 } ( \mathbf { x } ) , . . . , f _ { m } ( \mathbf { x } )$ 是实值函数， $m$ 是目标维数， $g _ { i } ( \mathbf { x } )$ 为 $\boldsymbol { r }$ 个不等式约束， $h _ { i } ( \mathbf { x } )$ 为 $q  – r$ 个等式约束。

在处理时，通常将式(1)的等式约束转换为式(2)所示的不等式约束：

$$
h _ { i } ( { \bf x } ) ^ { \prime } \equiv \delta - \vert h _ { i } ( { \bf x } ) \vert \ge 0
$$

其中， $\delta { > } 0$ 称为不等式约束的容忍参数。

个体 $\textbf { x }$ 的整体约束违反程度可以由下式计算得出：

$$
\nu ( \mathbf { x } ) = \sum _ { i = 1 } ^ { m } G _ { i } ( \mathbf { x } )
$$

# 1.2 CMOPs相关定义

定义1可行解。当且仅当 $g _ { i } ( \mathrm { x } ) { \le } 0 ( i { \in } \{ 1 , . . . , r \} )$ ，$h _ { i } ( \mathbf { x } ) { = } 0 ( i { \in } \{ r { + } 1 , . . . , q \} )$ ，称 $\mathbf { x }$ 为 CMOPs 的可行解。

定义2不可行解。不能同时满足 $g _ { i } ( \mathrm { x } ) { \leq } 0 ( i { \in } \{ 1 , . . . , r \} )$ $h _ { i } ( \mathbf { x } ) { = } 0 ( i { \in } \{ r { + } 1 , . . . , q \} )$ 的解 $\mathbf { x }$ ，称其为不可行解。

定义3可行域。由所有可行解组成的集合称为CMOPs的可行域 $\Omega$ ，如图1所示。

定义4不可行域。由所有不可行解组成的集合称为CMOPs的不可行域。

![](images/9b0f793003e00cef0baf2ca8ece3131226dc425ceaa43675bf4b6b42ccb527e9.jpg)  
图1CMOPs的可行域Fig.1Feasible domains for cmops

# 1.3 MOEAs分类

# 1）基于支配的MOEAs

基于支配的MOEAs通过Pareto支配关系将种群划分成若干个层次，依层顺序选出最优解以保证种群的收敛性。在同一层中，首选拥挤度值小的解遗传到下一代，以保证种群的分布性。图2是NSGA-II非支配排序示意图。在图2中，分类子集 $F _ { 1 }$ 和 $F _ { 2 }$ 中的所有个体均进入了新群体 $\boldsymbol { P } _ { t + 1 }$ ，但分类子集 $F _ { 3 }$ 中只有一部分个体可以进入新群体 $P _ { t + 1 }$ 。

# 2）基于指标的MOEAs

基于指标的MOEAs采用性能评估指标来评价解的质量，以便度量个体在种群中的收敛和分布性。图3为 $I _ { \varepsilon ^ { + } }$ 指标示意图。

以最小化为例， $I _ { \varepsilon ^ { + } }$ 指标可表示为

$$
\begin{array} { r l } & { I _ { \varepsilon ^ { + } } ( A , B ) = \operatorname* { m i n } _ { \varepsilon } \{ \forall \mathbf { x } ^ { 2 } \in B \exists \mathbf { x } ^ { \mathrm { l } } \in A \colon } \\ & { f _ { i } ( \mathbf { x } ^ { \mathrm { l } } ) - \varepsilon \leq f _ { i } ( \mathbf { x } ^ { 2 } ) \mathrm { ~ f o r ~ } i \in \{ 1 , . . . , n \} \} } \end{array}
$$

其中，A、B为种群中的两个解集， $f _ { i } ( i { = } 1 , 2 , . . . , n )$ 为目标函数。

![](images/24e58635bf125ce60eb2a4be29991aea2f1cd1248f1528e7b458c04d8ee53f46.jpg)  
图2NSGA-II非支配排序示意图

![](images/9a89e1e13147f365e6ed25db5febe85ee9217bb872b1a73b51495030f443a53c.jpg)  
Fig.2NSGA-II non-dominated sequencing schematic   
图3Iε+-指标

在图3中，A、B分别为只包含一个个体的两个解集。在图3(a)中，A集合中的个体和B集合中的个体是互不支配的，此时 $I _ { \varepsilon + } ( B , A ) > 0$ ， $I _ { \varepsilon + } ( A , B ) { > } 0$ ；在图3(b)中，集合B中的个体支配集合 $A$ 中的个体，此时 $\scriptstyle I _ { \varepsilon + } ( B , A ) < 0$ ， $I _ { \varepsilon + } ( A , B ) { > } 0$ 。

# 3）基于分解的MOEAs

2002年，Murata等人首先提出了基于分解的MOEAs即细胞多目标遗传算法(cellular multi-objective genetic algorithmC-MOGA)[29]。C-MOGA 使用权重和(weighted sum,WS)作为聚合函数进行问题分解，其生成的后代只与当前个体比较。2007年，张青富等人提出了MOEA/D算法，其通过聚合函数将一个多目标优化问题分解为多个单目标优化子问题，并且利用一种相互协作的方式同时优化这些子问题。与C-MOGA相比，MOEA/D除了使用WS聚合函数外，还研究了切比雪夫(Tchebycheff，TCH)和基于惩罚边界交叉的(penalty-basedboundaryintersection,PBI)聚合函数。此外，还引入邻域的概念以提高种群进化效率。图4为TCH分解方法示意图。

![](images/a4b73837d2cda5c212ccaaaddc0eebd15098466b663e0b3f7265bb0e60b7cf8c.jpg)  
Fig.3 $\mathrm { I } \varepsilon + -$ indicator   
图4切比雪夫方法Fig.4Tchebycheff approach

# 2 约束处理机制

经过近二十年的发展，CMOEAs已形成多种成熟的约束处理机制。下面介绍四种常用的约束处理机制。

# 1）惩罚函数方法

惩罚函数方法是指对种群中违反约束条件的个体按约束违反程度进行惩罚，以减小其被选择的概率，如式(5)和(6)所示。

$$
G _ { i } ( \mathbf { x } ) = \left\{ \begin{array} { l l } { \operatorname* { m a x } \{ 0 , g _ { i } ( \mathbf { x } ) \} } & { 1 \leq i \leq r } \\ { \left| h _ { i } ( \mathbf { x } ) \right| } & { r + 1 \leq i \leq q } \end{array} \right.
$$

$$
G ( \mathbf { x } ) = \sum _ { i = 1 } ^ { m } G _ { i } ( \mathbf { x } )
$$

其中， $G _ { i } ( \mathbf { x } )$ 为个体 $\textbf { x }$ 到第 $i$ 个约束条件的距离， $G ( \mathbf { x } )$ 为个体$\textbf { x }$ 到可行域的距离，反映了个体 $\textbf { x }$ 违反约束条件的程度。

由于其原理简单性、应用方便，惩罚函数法是CMOEAs领域最流行的约束处理方法。目前，已形成了死亡惩罚[30]、静态惩罚、动态惩罚[31]、自适应惩罚[32]等多种类型的惩罚函数。

在死亡惩罚方法中，当某个解违反任何约束时，都视该个体为不可行解，将拒绝该个体参与算法进化。在静态惩罚方法中，惩罚因子在进化过程中保持不变。在动态惩罚方法中，惩罚因子通常会随进化代数变化。通常，在进化前期使用较小的惩罚因子，以便扩大搜索区域，提高种群的多样性；在进化后期使用较大的惩罚因子，以便在可行域集中搜索，提高种群的收敛性。自适应惩罚方法一般需要从进化过程中获取约束违反信息，并利用这些反馈信息来自适应地调整惩罚因子。

惩罚函数法是带参数的约束处理方法，参数过大或过小都会影响算法的性能，并且参数调整过程极其费时费力[33]。因此，惩罚函数法的主要难题是如何设计自适应策略以快速高效确定合适的惩罚因子。

# 2）约束和目标分离方法

约束和目标分离方法是将目标值与约束违反程度分开来处理。Deb等人[34]提出了在替换过程中进行个体比较时要遵循的三个可行性准则，用来保持可行解与不可行解间的平衡。准则内容如下：1）如果两个个体均可行，则根据目标函数值评估它们的优劣；2）如果一个个体可行，另一个不可行，则选择可行个体；3）如果两个个体均不可行，则选择约束违反程度较低的个体。

可行性准则不仅操作简单，并且无须设置参数，因此更易于找到可行解。但是，可行性准则过于强调可行解，而忽略了不可行解中可能携带的有用信息，容易使算法陷入局部最优。

除了可行性准则外，其他代表性方法还有约束支配原则(constraint dominance principle,CDP)[34]、随机 排序法[35](stochastic ranking,SR)和 $\boldsymbol { \varepsilon }$ 约束处理法[36]。

在CDP方法中，制定了以下准则来评价解 $\textbf { x }$ 和 $\textbf { y }$ 的优越性，以便进行替换操作：1）如果 $\textbf { x }$ 可行，而 $\textbf { y }$ 不可行，则不用 $\textbf { y }$ 替换 $\mathbf { x }$ ；2）如果解 $\textbf { x }$ 不可行，而解 $y$ 可行，则用y替换 $\mathbf { x } ; ~ 3 \$ ）如果解 $\textbf { x }$ 和 $\textbf { y }$ 均不可行，则用约束违规度小的解替换大的解；4）解 $\textbf { x }$ 和 $\textbf { y }$ 均可行，则用某性能度量值好的解替换差的解。

在 SR方法中，通过设置概率参数 $p { \it _ { f } }$ 来决定算法根据哪个指标(目标函数值、约束违反程度)来评价任意两个解的优劣。SR方法在搜索过程中有效取得了约束违反程度和适应度值之间平衡，不仅最大程度利用了可行解提供的有用信息，而且挖掘出了不可行解携带的潜在信息，有力推动算法逼近可行域中的最优值。SR的伪代码见算法1。

算法1随机排序

开始

For $\scriptstyle { i = 1 }$ to $N$

For $\scriptstyle { j = 1 }$ to $_ { P - 1 }$

$u =$ random(0,1)；// $u$ 为(0,1)生成随机概率系数If 约束违反值为or随机概率系数 $u <$ 设定的 $P _ { f }$ 值If第 $j$ 个元素适应度值 $>$ 第 $j { + } 1$ 个元素适应度值交换第 $j$ 元素与第 $j { + } 1$ 个元素的顺序；

Else

If第 $j$ 个元素约束违反度 $>$ 第 $j { + } 1$ 个元素约束违反度交换第 $j$ 元素与第 $j { + } 1$ 个元素的顺序；

# End For

$\pmb { \mathrm { I } } \pmb { \mathrm { f } }$ 元素不发生交换

退出For 循环；

End For

# 结束

在 $\boldsymbol { \varepsilon }$ 约束处理方法中，使用分段函数来控制 $\boldsymbol { \varepsilon }$ 值。根据总约束违反度将个体划分到不同的区域，并采用不同的评价标准，具体公式如下：

$$
\varepsilon ( 0 ) = \nu ( \mathbf { x } _ { \theta } )
$$

$$
\varepsilon ( t ) = \left\{ \begin{array} { c c } { \displaystyle \varepsilon ( 0 ) \Biggl ( 1 - \frac { t } { T _ { c } } \Biggr ) ^ { c p } } & { 0 < t < T _ { c } } \\ { 0 } & { t \geq T _ { c } } \end{array} \right.
$$

其中， $\mathbf { \chi } _ { t }$ 为当前代数， $T _ { c }$ 为控制代数， $c p$ 控制 $\boldsymbol { \varepsilon }$ 减小的速率，$\nu ( \mathbf { x } \theta )$ 为种群中第 $\theta$ 个体违反约束条件的程度。

根据 $( f ( \mathbf { x } ) , \nu ( \mathbf { x } ) )$ 集合上的顺序关系定义 $\mathbf { \sigma } _ { \varepsilon }$ 级别比较。设$f ( \mathbf { x } _ { 1 } ) , f ( \mathbf { x } _ { 2 } )$ 和 $\nu ( \mathbf { x } _ { 1 } )$ 、 $\nu ( \mathbf { x } _ { 2 } )$ 分别为解 $\mathbf { x } _ { 1 }$ 和 ${ \bf x } _ { 2 }$ 的目标值和约束违反程度。对于任何满足 $\varepsilon { \geq } 0$ 的情况， $\boldsymbol { \varepsilon }$ 级别比较 $\prec _ { \varepsilon }$ 定义如下：

$$
\begin{array} { r } { ( f ( \mathbf { x } _ { 1 } ) , \nu ( \mathbf { x } _ { 1 } ) ) \prec _ { \varepsilon } \left( f ( \mathbf { x } _ { 2 } ) , \nu ( \mathbf { x } _ { 2 } ) \right) } \\ { \Updownarrow } \end{array}
$$

$$
\left\{ \begin{array} { l l } { f ( \mathbf { x } _ { 1 } ) \prec f ( \mathbf { x } _ { 2 } ) , \mathrm { i f } \nu ( \mathbf { x } _ { 1 } ) \le \nu ( \mathbf { x } _ { 2 } ) } \\ { f ( \mathbf { x } _ { 1 } ) \prec f ( \mathbf { x } _ { 2 } ) , \mathrm { i f } \nu ( \mathbf { x } _ { 1 } ) = \nu ( \mathbf { x } _ { 2 } ) } \\ { \nu ( \mathbf { x } _ { 1 } ) < \nu ( \mathbf { x } _ { 2 } ) , \mathrm { o t h e r w i s e } } \end{array} \right.
$$

# 3）多目标优化法

多目标优化方法核心思想是将约束条件转换为目标函数，从而将CMOPs转换为MOPs。通常有两种方式，第一种是将约束优化问题转换为两目标优化问题，其形式为min$F ( \mathbf { x } ) { = } ( f ( \mathbf { x } ) , G ( \mathbf { x } ) )$ ，其中 $f ( \mathbf { x } )$ 为原问题的目标函数， $G ( \mathbf { x } )$ 为解违反 $( r { + } q )$ 个约束条件的总程度。第二种是将约束优化问题转换为有 $( r { + } q { + } 1 )$ 个目标的多目标优化问题。尽管多目标优化法在处理CMOPs时表现出良好的收敛性，但是算法的计算复杂度也成倍增大。

# 4)混合方法

混合方法通常采用以下三种操作范式：1）多机制策略，即运用两种或两种以上的约束处理机制；2）多阶段策略，即将搜索过程分为多个阶段，在不同阶段运用不同的约束处理机制；3）协同进化策略，即多机制之间相互协作，能够有效解决复杂约束优化问题。

# 3 CMOEAs分类研究

根据选择机制的不同，这里分别从基于支配、基于指标、基于分解三个大类对CMOEAs进行阐述。

# 3.1基于支配的CMOEAs

首先介绍惩罚函数法在基于支配的CMOEAs中的应用情况。周等人[37]提出一种基于Pareto支配和分解的混合多目标骨干粒子群优化算法(HBBMOPSO)。该方法采用自适应惩罚函数法构建了包括能耗、罚款在内的约束多目标函数。为了提高Pareto最优解集的收敛性和多样性，该方法利用分解策略选取个体引导者，利用Pareto 支配和拥挤距离法维护外部档案。Azzouz等人[38]提出动态非支配排序遗传算法(dynamic nondominated sorting genetic algorithm II，DNSGA-

II)用来处理目标函数、约束条件或问题参数随时间变化的动态约束问题。该方法利用当前种群中可行解的比例自适应地调节惩罚项来处理动态约束。实验结果表明DNSGA-II在大多数测试问题中收敛性和多样性均优于原始算法。

除了有参的惩罚函数法，还有一些无参数的惩罚函数法。Jadaan 等人[39]提出一种将非支配排名遗传算法(nondominated ranked genetic algorithm，NRGA)与无参数惩罚函数法相结合的约束多目标进化算(PP-NRGA)。该方法运用无参数的惩罚系数 $r _ { g }$ ，不需要问题的先验知识，并在适应度函数中引入秩使算法更容易逼近全局Pareto前沿。实验结果表明PP-NRGA能在保持多样性的同时提高收敛速度。Ning 等人[40]提出一种新颖的约束非支配排序(constrained non-dosorting，CNS)的约束处理方法。该方法利用约束违反程度和Pareto等级将种群中的每个个体都被分配一个受约束的非支配等级，可取得可行性和最优性之间的平衡。为了有效解决CMOPs，将CNS嵌入到MOEA/DM2M当中形成非常具有竞争力的cMOEA/H算法。

由于惩罚参数设置困难，带有惩罚函数法约束处理机制的CMOEAs性能难以得到保证。因此，研究者更加关注约束和目标分离方法中可行性准则方法。

Zhang等人[41]为处理最优测试资源分配问题(optimaltestingresource allocationproblems,OTRAPs)的约束，提出一种基于 NSGA-II 的约束处理方法(NSGA-II testing resourceallocation，NSGA-II-TRA)。该方法利用启发式算法修复导致约束违反的元素值，采用基于z-score的欧式距离来评估个体之间的差异。根据敏感性分析结果，NSGA-II-TRA具有良好的稳健性。Jiao等人[42]提出了一种带有可行解引导策略的改进NSGA-II算法。该方法利用个体的违反约束值和真实目标函数值来修改个体的目标函数值，利用当前种群反馈的可行解比值来保持算法平衡，利用不可行解在可行个体的指导下确定可行方向，能够从可行空间和不可行空间两方向搜索Pareto最优解。实验结果表明该算法在收敛性和多样性方面表现出优越性。Fan 等人[43]提出了一种基于支配的新型聚类方法，采用不可行的解处理CMOPs，并利用差分进化的交叉算子以便快速收敛到Pareto前沿。

在约束和目标分离方法中，Ray等人[44]提出一种基于非支配的CMOEAs。通过使用非支配性来处理约束和目标，消除了惩罚函数法中存在的缩放和聚合问题。该算法将约束与目标分开单独处理，在目标域和约束域中使用Pareto排序概念。实验结果表明该算法在获得一组Pareto最优解的同时能够保持其多样性。Elarbi等人[45]提出基于孤立解的约束NSGA-I 算 法(constrained non-dominated sorting geneticalgorithm-III,ISC-NSGA-II)，通过选择与孤立子区域(即权重向量或参考点)相关的不可行解来提高算法的多样性和收敛性。Yang 等人[46]提出一种基于支配和 $\boldsymbol { \varepsilon }$ 约束处理切换机制的多目标差分进化算法(MODE-CHS)来解决CMOPs中可行性、收敛性和分布性的平衡问题。该算法通过引入 $\boldsymbol { \varepsilon }$ 约束技术在获得可行解的同时最大程度地加速种群收敛。实验结果表明MODE-CHS在解决CMOPs方面非常具有竞争力。Cuate等人[47]提出了一种基于NSGA-II和Pareto 追踪器(Pareto tracerPT)相结合的两阶段混合进化算法(ε-NSGA-II/PT)以解决等式CMOPs。PT策略能够沿着Pareto前沿追踪最优解以及处理约束条件。实验结果表明 $\varepsilon$ -NSGA-II/PT比现有的方法具有更强的优越性。

在多目标优化法中，Isaacs 等人[48]提出一种基于改进的NSGA-II 约束 处 理方法(constraint handling evolutionaryalgorithm,CHEA)。该方法将具有 $k$ 个目标的原始约束优化问题转换为具有 $k { + } 1$ 个目标的无约束优化问题，并通过自定义的参数 $\scriptstyle a$ 控制要保留在群体中的不可行解的数量，利用不可行空间搜索最优解，增加了解的多样性。实验结果表明，CHEA可以快速地搜索到可行域最优解集。

在混合方法的应用中，Deb 等人[49]提出了一种双目标进化算法与惩罚函数法相结合的CMOPs处理方法。该方法将违反约束的最小化作为附加目标，并与双目标进化优化策略相结合，利用获取的Pareto前沿估计问题的惩罚参数R，利用经典的局部搜索方法求解惩罚函数，促进算法收敛。实验结果表明带有惩罚函数法约束处理机制的进化算法可以快速、准确地找到约束问题的最优解。Venkatraman 等人[50]提出了一个基于遗传算法的两阶段框架以解决CMOPs。在第一阶段，将约束优化问题作为无约束问题处理，找到可行的解；在第二阶段，将优化目标函数和约束条件视为一个双目标优化问题。实验结果证明该算法与问题无关，具有较高的鲁棒性。Woldesenbet等人[51]提出了一种基于自适应惩罚函数和距离度量的混合约束处理技术。该方法原理简单、无调整参数，显示出了更好的处理结果。

实际工程中的问题大都具有动态特性，即目标函数、决策参数和约束条件均随时间发生变化。对于这类动态CMOPs,Azzouz等人[52]结合自适应惩罚函数和可行性驱动策略，提出了一种基于 NSGA-II 的 CMOEAs 算法(dynamic constrainedmulti-objective evolutionary algorithm,DC-MOEA).在DC-MOEA中，可行性驱动策略能够根据环境变化引导搜索向新的可行解方向收敛。基于支配的CMOEAs的研究总结见表1。

还有一些研究是利用CMOEAs解决实际工程的问题。Ji等人[53]通过将约束违反转换为目标函数方式，形成了改进的NSGA-II算法，并用其解决连续泊位分配问题(continuousberthallocationproblem,BAPC)。Gadhvi等人[54]利用带有约束处理机制的NSGA-II、SPEA2和PESA-II等算法处理车辆被动悬架系统的约束多目标优化问题。

Sorkhabi[55]提出一种基于NSGA-II的新型约束处理方法其采用惩罚函数和约束编程(constraint handlingvia constraintprogramming，CHCP)来平衡局部和全局探索，提高了优化效率，解决了多目标风约束电场布局优化问题。Abul'Wafa等人[56提出了一种多目标受控制精英NSGA-II算法，以便处理多目标经济/环境调度问题。Bora 等人[57]使用约束NSGA-II和强化学习来解决多目标风电调度问题。Song等人[58]采用约束转向规则设计了一种改进的NSGA-II算法，并用其解决多目标土地分配空间优化问题。Rathnayake[59.60]等人利用二元锦标赛约束处理技术改善NSGA-II处理约束问题的能力，并将算法用于下水道系统多目标控制当中。实验结果显示该约束处理机制比其他约束处理技术的处理效果更好。周等人[61]提出一种基于约束多目标骨干粒子群的污水处理过程智能优化控制方法。表2列出了基于支配的CMOEAs在工程中的应用研究。

# 3.2 基于指标的CMOEAs

相比基于支配的CMOEAs，基于指标的CMOEAs的研究较少，主要成果如下：

Garcia 等人[62]提出一种基于指标的MOEAs。该方法利用参考集引导种群搜索，利用IGD值推动种群收敛，最终达到利用性能指标获取约束边界可行解的目的。

在约束和目标分离法中，Scimemi等人[62]提出一种基于超体积指标的约束处理方法，该方法将单目标优化问题的SR方法扩展到多目标优化问题，实验结果表明所提出方法的适用性。

在混合方法中，Said等人[64]提出了基于指标的协同进化迁移算 法(indicator-based co-evolutionary migration basedalgorithm，IB-CEMBA)，以解决带约束的双层多目标优化问题。双层优化问题包括上级(领导者)和下级(跟随者)，下级(跟随者)优化问题作为上级(领导者)优化问题的约束出现。IB-CEMBA采用基于指标的方法来衡量下级发送给上级的解是否具有最佳指标贡献度。Guo等人[65]提出一种基于指标的IBEA与可满足性模理论(satisfiability modulo theories,SMT)

相结合的混合MOEAs(satisfiability modulo theories indicator-basedevolutionaryalgorithm,SMTIBEA)，用于解决现实软件产品线配置优化问题。Antonio 等人[66提出了一种基于超体积指标的新的合作协同进化 MOEA(indicator-based multi-objective evolutionaryalgorithm,IBMOEA)以解决 CMOPs。

Tab.1 Research summary of dominance-based cmoeas   
表2基于支配的CMOEAs在工程应用的研究总结  

<html><body><table><tr><td>研究方法</td><td>文献</td><td>特点</td><td>测试集</td></tr><tr><td rowspan="5">惩罚函数</td><td></td><td>[37]利用自适应惩罚法构建约束多目标函数。</td><td>BSM1基准仿真平台</td></tr><tr><td></td><td>[38]利用种群中可行解的比例自适应地调节惩罚项来处理动态约束。</td><td>DCTP1-8</td></tr><tr><td></td><td>[39]利用无参数惩罚函数法rg。</td><td>CTP1-5</td></tr><tr><td></td><td>[40]使利用约束违反程度和 Pareto 等级筛选候选解。</td><td>CF1-10</td></tr><tr><td></td><td>[41]利用启发式算法修复交叉和变异操作导致约束违反的元素值。</td><td>4个并行模块化软件系统</td></tr><tr><td rowspan="9">约束和目标</td><td></td><td>[42]利用不可行解在可行解的引导下确定可行方向。</td><td>BNH、SRN、TNK、CONSTR、 OSY、Welded、Beam、CTP1-8</td></tr><tr><td>[43]</td><td>利用不可行解设计基于差分进化的交叉算子，</td><td>CONSTR、TNK、SRN、OSY、</td></tr><tr><td></td><td>利用平方搜索更新可行非支配解。</td><td>CTP1-2、FON、POL、SCH、KUR</td></tr><tr><td>[44]</td><td>利用传统惩罚函数方法的缩放和聚合处理约束条件，</td><td>双目标桁架设计、四杆桁架设计、</td></tr><tr><td></td><td>设计有效匹配策略来改进弱解。</td><td>振动平台设计、五目标水资源规划</td></tr><tr><td></td><td>[45]利用约束违反值和不同子区域的小生境数目综合比较不可行解。</td><td>C1-DTLZ1、C1-DTLZ3、C2-DTLZ2、 凸C2-DTLZ2、C3-DTLZ1、C3-DTLZ4</td></tr><tr><td>[46]</td><td>设计约束处理切换机制：如果种群中没有可行解，</td><td>LIRCMOPs1-12、CFs1-7、CTPs1-8</td></tr><tr><td></td><td>则利用改进的ε约束处理实现进化；否则，算法不考虑约束条件。</td><td></td></tr><tr><td></td><td>[47]利用ε约束：总体约束违反小于&的解x被视为可行解。</td><td>CZDT1-3、CZDT4、CZDT6、D&D、</td></tr><tr><td></td><td></td><td>[52]设计可行性驱动策略，能够根据环境变化引导搜索向新的可行解方向收敛。</td><td>Eql-ZDT1、Eq2-ZDT1、Eql-Quad、Eq2-Quad DCT1-8</td></tr><tr><td></td><td></td><td>多目标优化[48]将k目标约束优化问题转换为k+1目标的无约束优化问题。</td><td>CTP2-8</td></tr><tr><td></td><td></td><td>[49]双目标进化方法与惩罚函数法相结合。</td><td>TP3、TP4、TP5、TP6、TP8、Weld</td></tr><tr><td></td><td>[50]</td><td>第一阶段，约束优化问题转为无约束问题处;</td><td></td></tr><tr><td>混合</td><td></td><td>第二阶段，将优化目标函数和约束条件视为一个双目标优化问题。</td><td>G 1-11</td></tr><tr><td></td><td></td><td>[51]自适应惩罚函数和距离度量的混合约束处理技术。</td><td>BNH、SRN、OSY、TNK、CTP1-8、 CONSTR、焊接梁优化</td></tr></table></body></html>

表1基于支配的CMOEAs的研究总结  
[ab.2Research summary of dominance-based CMOEAs in   

<html><body><table><tr><td colspan="3">engineering applications</td></tr><tr><td>算法名称</td><td>特点</td><td>工程应用</td></tr><tr><td>MNSGA-II[53]</td><td>约束转换为目标函数</td><td>连续泊位分配</td></tr><tr><td>NSGA-II、SPEA2、 PESA-II [54]</td><td>综合比较三个算法</td><td>车辆悬架系统优化</td></tr><tr><td>改进NSGA-II [55]</td><td>综合惩罚函数和约束规划</td><td>电场布局约束优化</td></tr><tr><td>CE-NSGA-II [56]</td><td>两阶段策略</td><td>经济/环境调度</td></tr><tr><td>NSGA-RL [57]</td><td>引入强化学习</td><td>风电调度优化</td></tr><tr><td>knowledge-informed</td><td>不可行解转换为可行解</td><td>土地分配空间优化</td></tr><tr><td>NSGA-II [58] 改进 NSGA-II [59,60]</td><td>二元锦标赛约束处理</td><td>下水道系统控制</td></tr><tr><td>CBBMOPSO[61]</td><td></td><td></td></tr><tr><td></td><td>可行性原则</td><td>污水处理过程优化</td></tr></table></body></html>

有些成果是结合多种优化算法来处理约束优化问题。BenMansour等人[67]提出基于蚁群优化算法和邻域方法(局部搜索)互补的组合算法(indicator weighted based local searchwithantcolonyoptimization,IWBLS/ACO)来处理多目标多维背包问题。该方法采用蚁群优化创建初始解，采用局部搜索方法核ε指标实现空间搜索，能在探索和开发之间取得更好的折中。Mansour等人[68提出了一种基于指标的蚁群优化算法用于解决多目标背包约束问题。

为了防止种群在处理CMOPs时容易陷入局部最优，Yuan 等人[69]提出一种基于自定义的指标的约束处理技术(indicator-based constrained multi-objective algorithm,ICMA)。该方法首先引入距离度量来衡量目标空间中解之间的拥挤程度，引导种群充分探索不同区域，然后利用该度量和整体约束违反程度设计可行解和不可行解的评估指标，有效引导种群探索有潜力区域，防止陷入局部最优。实验结果表明ICMA优于其他CMOEAs。Liu 等人[70]开发了一个基于指标的CMOEA框架，该框架可以方便地集成基于指标的CMOEAs(HypE、IBEA和ISDE)和三个约束处理技术(可行性准则、SR、 $\varepsilon$ -约束方法)。实验结果表明基于指标的CMOEAs在处理CMOPs时具有较强竞争力。Wang等人[71]基于SATIBEA提出了改进的SATIBEA $^ +$ 方法，该方法通过为每个特征引入二进制变量并将约束映射到公式，可以将特征选择问题映射为SAT问题。以最小化无效约束的数量定义为搜索过程的目标，在搜索过程中通过将无效配置替换为有效配置或"更好"的配置(约束违规较少)来减少特征违规的数量并增加有效配置的百分比。实验结果表明，SATIBEA $\cdot ^ { + }$ 优于SATIBEA。

Shi 等人[72]提出了一种基于指标的并行投资组合方法(indicator-basedevolutionaryalgorithmparallel portfolioapproach,IBEAPORT)，该方法通过将SAT求解以不同方式合并到IBEA中来组成三种算法变体(SATIBEAv1、SATIBEAv2和SATIBEAv3)，并利用并行化技术执行这些变体。实验结果表明，IBEAPORT利用了不同算法的探索能力，并能在有限时间预算内提高最优性。基于指标的CMOEAs的研究总结见表3。

Tab.3Research summary of indicator-based CMOEAs   

<html><body><table><tr><td>研究方法文献</td><td></td><td>特点</td><td>测试集</td></tr><tr><td>惩罚函数[62]</td><td></td><td>将二次惩罚集成到基于Tchebycheff的目标函数中，用于确 定待优化问题的Pareto前沿的形状和位置。</td><td>CZDT1-6、Eql-ZDT1、Eq2-ZDT2、Eq1-Quad、 Eq2-Quad、Eq-DTLZ1</td></tr><tr><td rowspan="4">约束和目 标分离</td><td>[63] 解的优劣。</td><td>将随机排序方法扩展到多目标优化，使用超体积指标比较</td><td>结构案例约束多目标问题</td></tr><tr><td>[69]</td><td>计算解之间的拥挤距离，与整体约束违反程度一起，设计DAS-CMOP、MW、C-DTLZ、DC-DTLZ、DOC、Eq1-DTLZ、 可行解与不可行解的评估指标。</td><td>FCP1-5</td></tr><tr><td>[70]</td><td>设计通用算法框架，能够集成HypE、IBEA和ISDE 与三 个约束处理技术(可行性准则、SR、ε-约束方法)。</td><td>CTP1-8、BNH、CONSTR、DBD、OSY、SRD、SRN、TNK、 WBD、C1-DTLZ1-2、C1-DTLZ4</td></tr><tr><td>[71]</td><td>为每个特征引入基于二进制变量约束映射公式，有效减少</td><td>Web Portal、eCos、FreeBSD、Linux X86</td></tr><tr><td rowspan="7">混合</td><td></td><td>违反约束的无效解。 [64]利用两个子群体多线程并行工作方式。</td><td>双层生产分配规划问题模型、双层特征构建问题的机器学习案例</td></tr><tr><td></td><td>第一阶段，约束优化问题转为无约束问题；</td><td></td></tr><tr><td></td><td>[65]第二阶段，将优化目标函数和约束条件视为一个双目标优 化问题。</td><td>ECOS、FIASCO、LINUXFREEBSD、UCLINUX</td></tr><tr><td></td><td>[66] 设计基于超体积指标的选择机制。 蚁群优化和局部搜索相结合，考虑目标空间不同方向上的</td><td>DTLZ1-7</td></tr><tr><td>[67]</td><td>约束演化。</td><td>MOMKP</td></tr><tr><td></td><td>[68]使用二元指标搜索原理加强最优解的搜索效率。</td><td>MOKP</td></tr><tr><td></td><td>[72]以不同方式将 SAT求解合并到 IBEA 中。</td><td>ECOS、FIASCO、FREEBSD、LINUX、LINUXUC</td></tr></table></body></html>

在工程应用方面，Li等人[73]为了平衡网状AC/VSC-MTDC系统的经济性和安全性，先是提出了一种校正安全约束多目标潮流模型，然后开发了一种基于指标的并行双准则进化 算 法(parallel bi-criterion evolution indicator basedevolutionaryalgorithm，PBCE-IBEA)。实验结果表明PBCE-IBEA能够有效地实现网状AC/VSC-MTDC系统的经济性和安全性之间的权衡。Tangpattanakul 等人[74]提出一种基于指标的多目标局部搜索方法(indicator-based multi-objective localsearch,IBMOLS)用于解决与地球观测卫星选择和调度相关的CMOPs。表4列出了基于指标的CMOEAs在工程问题中的应用研究。

表3基于指标的CMOEAs的研究总结  
表4基于指标的CMOEAs在工程应用的研究总结  
Tab.4Research summary of index-based CMOEAs in engineering   

<html><body><table><tr><td colspan="3">applications</td></tr><tr><td>算法名称</td><td>特点</td><td>工程应用</td></tr><tr><td></td><td>通过并行计算提升寻找Pareto最优 BCE-IBEA[73]解的效率，利用综合决策技术自动</td><td>网状AC/VSC- MTDC系统优化</td></tr><tr><td></td><td>确定最优解。</td><td>地球观测卫星选</td></tr><tr><td>IBMOLS[74]</td><td>利用超体积指标来评判解的优劣。</td><td>择和调度</td></tr></table></body></html>

# 3.3基于分解的CMOEAs

本小节主要以MOEA/D为例，介绍基于分解的CMOEAs的研究现状。

有些方法在处理CMOPs的过程中利用可行解或不可行解。Miyakawa 等人[75]提出一种带有定向交配和存档的约束MOEA/D 的算法(constrained MOEA/D with directed matingandarchive，CMOEA/D-DMA)。该方法采用定向交配机制选择有用的不可行解，其具有比可行解更好的标量函数值作为父项，并将它们保存在档案中。通过连续mCDTLZ 和多目标离散背包问题进行测试，结果表明该算法有更高的搜索性能。Elarbi等人[7提出了一种基于隔离解的约束MOEA/D方法(isolated solution-based constrained MOEA/D,ISC-MOEA/D),利用不可行解处理具有各种复杂特征的超多目标优化问题(constrained many-objective optimization problems,CMaOPs)。先通过基于隔离解决方案的更新程序IS处理具有复杂特征的CMaOPs，然后选择与隔绝子区域相关的以及具有较小约束违反值的不可行解决方案。实验结果表明，ISC-MOEA/D有更好的竞争力。

在约束和目标分离的方法中，Fan 等人[77提出一种基于角度的约束优势原则(angle-basedconstraineddominanceprinciple,ACDP)的MOEA/D(MOEA/D-ACDP)。ACDP利用两个解之间的角度信息和可行解的比例来调整优势关系，从而同时保持种群良好的收敛性、多样性和可行性。Asafuddoula等人[78提出一种基于MOEA/D自适应约束处理方法。该方法包含一个约束违反阈值自适应设置机制，当不可行解的约束违反值小于该阈值时，此不可行解将与可行解等同。Fan等人[79]在MOEA/D的框架中应用了改进的 $\boldsymbol { \varepsilon }$ 约束处理机制。实验结果表明，所提出的 $\boldsymbol { \varepsilon }$ 约束处理机制在收敛性和多样性方面都非常有效。Martinez等人[80]提出了一种基于 $\boldsymbol { \varepsilon }$ 约束处理方法的新型选择机制，通过MOEA/D邻域信息以获得使可行区域内目标函数最小化的解。实验结果显示所提新型 $\boldsymbol { \varepsilon }$ 约束处理方法能够在可行解生成和向Pareto最优前沿加速收敛之间取得最佳平衡。

此外，约束条件可能导致算法陷入两种停滞状态：1）由于CMOPs的可行区域一般是由不相连的可行子区域组成，算法在搜索时容易陷入可行子区域中，而子区域中可能没有全局Pareto最优解；2）一个约束违反函数可能包含许多非零极小点，它会使搜索陷入一个不可行的区域。为了解决这两个问题，Zhu等人[8I]基于MOEA/D设计了一种检测和逃避策略(detect-and-escape,DAE)，以帮助约束处理方法摆脱不可行区域和局部最优Pareto前沿，其约束处理机制流程如图5所示。

在基于多目标优化的约束处理方法中，Zapotecas-Martinez等人[82]提出了一种基于MOEA/D的多目标约束处理方法。该方法构建了一个以标量函数和约束违反度作为目标函数的双目标问题，通过标量函数来选择最佳解，提升了使用不可行解来逼近CMOPs的Pareto前沿的可能性，能在收敛性、多样性和可行性之间保持平衡。Peng 等人[83]同样也提出一种基于MOEA/D的多目标约束处理方法。该方法将约束违反度转换为一个目标函数，利用分布在不可行区域的一部分权重来选择不可行的非支配个体，这些权重随着进化进程动态变化，从而寻找具有更好目标值和较小约束的不可行非支配个体，以提高种群的收敛性和多样性。Wang 等人[84]基于MOEA/D提出一种权向量调整策略，以实现对约束条件的多目标处理。

![](images/f2d4e30d4451d802cc1d6e57083ea65e6a689ed39415720741c0a18d4d9dca4f.jpg)  
图5CHT-DAE框架流程  
Fig.5CHT-DAE framework process

还有一些文献 $\boldsymbol { \varepsilon }$ 约束针对MOEA/D中常用的分解方法可能会导致多样性的丧失或对PF的形状敏感的问题，Cai等人[85]提出了一种网格约束分解方法(constraineddecomposition with grids,CDG)，名为 CDG-MOEA。其中，CDG可看做 $\boldsymbol { \varepsilon }$ 约束方法的扩展，它具有反映解之间邻域结构信息的固有特性。在CDG中，选择一个目标函数进行优化，而其他所有目标函数通过设置上限和下限将其转换为约束。该方法在收敛性和多样性方面都优于比较算法，且对Pareto前沿的形状具有鲁棒性。之后，基于之前在CDG方面的工作,Cai等人[86]提出一种基于动态网格分解约束框架(dynamicconstrained decompositionwith grids,DCDG)的多目标模因算法(DCDG multi-objective memetic algorithm,DCDG-MOMA),用于种群规模动态变化的组合CMOPs。此外，DCDG可以动态增加网格的数量以获得更多的非支配解，提高了解多样性。经实验对比该算法明显优于其他算法。Cai等人提出这两种方法的不同之处如表5所示。

在使用混合方法求解CMOPs 中，Chen 等人[87]提出一种基于分解的具有ε-约束框架的 MOEA(decomposition-basedMOEAwith the $\varepsilon$ -constraint,DMOEA-εC)。该方法将 $\varepsilon \cdot$ -约束纳入分解策略，选择一个目标作为主要目标，将其他目标转换为约束，并采用可行性准则优化子问题。经实验对比该算法明显优于其他算法，并且在解决0-1背包问题方面也显示出明显的优势。Liu 等人[87提出一种具有边界搜索和归档功能的 MOEA/D 进化算法用于处理CMOPs。基于分解的CMOEAs研究总结见表6。

表5CDG-MOEA与DCDG-MOMA对比  
Tab.5Comparison of CDG-MOEA and DCDG-MOMA   

<html><body><table><tr><td>CDG-MOEA</td><td>DCDG-MOMA</td></tr><tr><td>仅维护种群P</td><td>需维护种群P和LS的解集PS</td></tr><tr><td>使用字典排序来获得前N个解</td><td>选择至少一个排名第一的解</td></tr><tr><td>固定的种群规模</td><td>动态的种群规模</td></tr><tr><td>固定的划分参数K</td><td>动态增加的划分参数K</td></tr></table></body></html>

表6基于分解的CMOEAs研究总结  
Tab.6Decomposition-based research summary of cmoeas   

<html><body><table><tr><td>研究方法</td><td>文献</td><td>特点</td><td>测试集</td></tr><tr><td rowspan="10">分离</td><td>[75]</td><td>利用定向交配策略选择比可行解具有更好目标值的不可行 解作为父代解。</td><td>mCDTLZ、mk-KP 背包问题</td></tr><tr><td></td><td>[76]利用隔绝子区域内具有较小约束违反值的不可行解。</td><td>C1-DTLZ1、C1-DTLZ3、C2-DTLZ2、Convex C2-DTLZ2、C3-</td></tr><tr><td></td><td>[77]利用解之间的角度信息和可行解的比例比较解的优劣。</td><td>DTLZ1、C3-DTLZ4 LIR-CMOP1-14、工字梁双目标约束优化</td></tr><tr><td></td><td>[78]设计自适应约束处理方法，自适应地确定约束违反阈值。</td><td>SRN、OSY、CTP6、Toysub、TNK、CTP2-8</td></tr><tr><td></td><td>[79]利用当前种群中的可行解的比例动态调整ε级别。</td><td>CMOP1-CMOP9</td></tr><tr><td>约束和目标 [80]</td><td>利用 MOEA/D邻域相关信息设计基于ε约束方法的新型选</td><td>CMOP1-10</td></tr><tr><td></td><td>择机制。</td><td>LIRCMOPCF1-14、CTP 1-8、CF1-10、C1-DTLZ1、</td></tr><tr><td>[81]</td><td>利用可行解比例和整体约束违反程度设计逃逸策略，引导 搜索摆脱停滞状态。</td><td>C1-DTLZ3、C3-DTLZ1、C3-DTLZ4、DC1-DTLZ1、 DC1-DTLZ3、DC2-DTLZ1、DC2-DTLZ3、DC3-DTLZ1、 DC3-DTLZ3、LIRCMOP1-12、DOC1-DOC9</td></tr><tr><td>[85]</td><td>选择一个目标函数进行优化，通过设置上限和下限将其他 目标函数转换为约束条件。</td><td>UF1-10、GLT1-6</td></tr><tr><td></td><td>[86]使用动态网格来保持多样性，支持协同单目标局部搜索。</td><td>多目标旅行商、多目标二次分配、多目标电容弧路由</td></tr><tr><td>[82]</td><td>构建以标量函数和约束违反度作为目标函数的双目标问 题。</td><td>CF1-10</td></tr><tr><td rowspan="2"></td><td>多目标优化[83]</td><td>将约束违反度转换为目标函数，利用分布在不可行域的部 分权重来选择不可行的Pareto 解。</td><td>CTP1-8</td></tr><tr><td>[84]</td><td>将约束优化问题转换为双目标优化问题，引入重启策略帮 助种群跳出不可行区域的局部最优。</td><td>CEC2006、CEC2010、CEC2017</td></tr><tr><td rowspan="2">混合</td><td>[87]</td><td>综合分解策略与ε-约束法分解为一系列标量约束优化子问</td><td>ZDT1-3、ZDT4、ZDT6、DTLZ1-4、DTLZ6、UF1-10、</td></tr><tr><td></td><td>题并采用可行性准则协同优化子问题。 [88] 将约束优化问题划分为多个子问题，以协作方式处理约束。</td><td>LZ1、LZ3、LZ4、LZ7、LZ9、WFG1-9、MOKPs CTP1-8、CF1-10</td></tr></table></body></html>

在工程应用方面，Zhu等人[89]利用带有惩罚函数约束处理机制的MOEA/D处理风火电系统的经济排放调度问题。Biswas 等人[90]利用带有可行解优越性(superiorityof feasiblesolutions,SF)约束处理机制的MOEA/D处理电力系统的约束多目标最优潮流问题。Zhou等人[91]利用带有可行性准则约束处理机制的MOEA/D处理污水处理过程的约束多目标优化控制问题。Li等人[92]利用改进MOEA/D来解决MEMS布局优化问题。Hu等人[93]提出了一种基于MOEA/D和约束规划的MOEAs用于解决具有时间窗口的多目标团队定向越野问题(multi-objective TOPTW,MOTOPTW)。Li等人[94]考虑提出一种问题结构和客观特征引导的 MOEA/D(problem-specificheuristics MOEA/D,PH-MOEAD)以解决混合流水调度批次流问题。表7列出了基于分解的CMOEAs在工程问题中的应用研究。

表7基于分解的CMOEAs在工程应用的研究总结

Tab.7Research summary of decomposition-based CMOEAs in   

<html><body><table><tr><td colspan="3">engineering applications</td></tr><tr><td>算法名称</td><td>特点</td><td>工程应用</td></tr><tr><td>MOEA/D+EED[89]随机变量在内-</td><td>机会约束规划方法解决包括</td><td>风火电系统经济排 放调度</td></tr><tr><td>MOEA/D-SF [90]</td><td>-的约束 可行解优越性约束处理机制</td><td>电力系统最优潮流</td></tr><tr><td>AMOEA/D [91]</td><td>可行性准则约束处理机制处污水处理过程约束</td><td>约束多目标优化</td></tr><tr><td></td><td>理出水水质约束条件 动态分配计算资源给更有希</td><td>多目标优化控制</td></tr><tr><td>cMOEA/D [92]</td><td>望的子问题</td><td>MEMS布局优化</td></tr><tr><td>CPMOEA/D[93]</td><td>集成分解方法处理约束组合团队多目标定向优 优化问题</td><td>化</td></tr><tr><td>PH-MOEAD [94]</td><td>考虑子批次排列的变异启发混合流水车间批次 式算法提高开发能力</td><td>流调度</td></tr></table></body></html>

# 4 结束语

本文主要从基于支配、基于指标、基于分解三个角度分别对CMOEAs的研究成果进行了总结，并详细分析了惩罚函数法、约束和目标分离法、多目标优化法、混合法等四种典型的约束处理机制在算法中的具体运用。纵观这十几年的研究发展趋势，CMOEAs的理论愈加丰富，约束处理效果愈加突出，工程应用领域持续拓展，但是仍然存在一些亟待解决的难题：

# 1）复杂约束条件的处理

为了寻找可行解，常将等式约束条件转换为不等式约束条件来处理，但对于非线性、离散等具有复杂等式约束条件的约束优化问题，进化算法很难找到可行解。在离散约束优化中，最优解容易陷入可行域的局部最优。因此，如何合理利用复杂约束条件寻找可行解，防止算法陷入局部最优仍然是一个开放性难题。进一步的研究，可以考虑综合运用现有的约束处理技术，设计混合约束处理机制，以应对复杂的搜索环境；也可以将种群划分多个子群，利用子群之间的协同演化，实现不同进化阶段的约束处理。

# 2）约束与目标间的不平衡

在解决CMOPs时，过于注重约束条件可能会遗漏Pareto最优解，过于注重目标函数可能会使种群偏离可行域。例如：在污水处理多目标优化问题中，如果特别强调水质参数必须全部达标排放，那么处理所需的电力消耗带来的成本将十分高昂；如果只追求能耗最低，那么出水水质参数约束得不到基本保证，则会对水环境造成重大危害。因此，根据工程问题特点，兼顾约束条件与目标函数之间的平衡就显得极其重要。进一步的研究，可以考虑根据决策者的偏好获取感兴趣的Pareto 前沿，或决策出违反约束条件但却是急需的解。

# 3）许多目标问题

现实生活中的问题常常需要考虑诸多因素。当目标维数大于3时，随着目标维数增多，传统的Pareto支配关系对区分个体优劣的能力降低，导致收敛速度的下降，无法很好地收敛到Pareto前沿面。因此，针对约束许多目标优化问题，设计一个具有选择压力与约束处理同步的进化机制也是一个极具挑战性的难题。进一步的研究，可以考虑分阶段处理收敛性和多样性，比如在第一阶段采用弱支配关系促进种群收敛，在第二阶段采用强支配关系提升种群多样性，在提供强大选择压力的同时，考虑采用双档案策略处理约束条件。

# 4）测试函数

现实问题复杂多变，现有的用于CMOEAs性能验证的约束测试函数集已不能满足实际工程需求，因此设计出能反映实际工程问题特征的基准测试函数是非常有必要的。进一步的研究，可以考虑设计具有可控参数的测试函数生成器。

综上所述，约束多目标进化算法在处理CMOPs时仍面临着诸多的挑战。随着科学技术和智能进化算法的发展，CMOEAs的约束处理效果和优化性能仍有可挖掘的空间。现在大部分成果主要是针对原始算法进行性能改善，新的算法理论及约束处理技术仍有待进一步深入研究；现实问题通常是动态的约束优化问题，常与时间或环境相互影响，迭代后产生的最优解也会随时间或环境的变化而动态变化，因此针对动态约束多目标优化问题仍需从算法框架、参数控制、处理机制等方面进行研究；设计满足探索和开发需求的自适应学习机制，或与时下先进的机器学习理论(如深度学习、迁移学习、强化学习)等相结合，设计知识驱动型约束多目标进化算法以提高种群自组织学习能力也是值得关注的研究方向。

# 参考文献：

[1]Qu B Y,Suganthan P N.Constrained multi-objective optimization algorithm with an ensemble of constraint handling methods [J]. Engineering Optimization,2011,43(4): 403-416.   
[2]Zhou Hongbiao,Qiao Junfei. Multi-objective optimal control for wastewater treatment process using adaptive MOEA/D [J]，Applied Intelligence,2019,49 (3): 1098-1126.   
[3]Khalilpourazari S,Pasandideh S H R.Multi-objective optimization of multi-item EOQ model with partial backordering and defective batches and stochastic constraints usingMOWCA and MOGWO[J].Operational Research,2020,20 (3): 1729-1761.   
[4] Zhu Siying，Zhu Feng.Multi-objective bike-way network design problem with space-time accessibility constraint [J].Transportation, 2020,47(5):2479-2503.   
[5]El-Abbasy M S,Elazouni A,Zayed T.Finance-based scheduling multiobjective optimization:benchmarking of evolutionary algorithms [J]. Automation in Construction,2020,120:Article ID 103392.   
[6]Michalewicz Z, Schoenauer M. Evolutionary algorithms for constrained parameter optimization problems [J]. Evolutionary Computation,1996, 4(1): 1-32.   
[7]Coello CA C.Theoretical and numerical constraint-handling techniques used with evolutionary algorithms:a survey of the state of the art [J]. Computer Methods in Applied Mechanics and Engineering,20o2,191 (11-12):1245-1287.   
[8]陈志旺，白锌，杨七，等．区间多目标优化中决策空间约束、支配及 同序解筛选策略[J]．自动化学报,2015,41(12):2115-2124.(Chen Zhiwang,Bai Xin,Yang Qi,et al. Decision space constraint,domination and same order solution selection strategy in interval multi-objective algorithm [J].IEEE Trans on Evolutionary Computation,2015,20 (3): 475-480.   
[10] Deb K,Pratap A,Agarwal S,etal.A fast and elitist multi-objective geneticalgorithm:NSGA-II[J].IEEE Transon Evolutionary Computation,2002,6 (2): 182-197.   
[11] Zitzler E,Laumanns M,Thiele L. SPEA2: improving the strength pareto evolutionary algorithm [J/OL]. Technical Report Gloriastrasse,2001, 103.(2001-07-13)[2022-03-31].doi: 10.3929/ETHZ-A-004284029.   
[12] Coello CA C,Lechuga MS.MOPSO: a proposal for multiple objective particle swarm optimization [J].IEEE Service Center,2002,2: 1051- 1056.   
[13] Qiao Junfei, Zhou Hongbiao,Yang Cuili.Bare-bones multi-objective particle swarm optimization based on parallel cell balanceable fitness estimation [J].IEEE Access,2018,6 (6): 32493-32506.   
[14] Zitzler E,Kinzli S.Indicator-based selection in multi-objective search [J].Lecture Notes in Computer Science,2004,3242: 832-842.   
[15] Brockhoff D, Zitzler E. Improving hypervolume-based multi-objective evolutionary algorithms by using objective reduction methods [Cl/ Proc ofIEEE Congress on Evolutionary Computation.IEEE,2007: 2086-2093.   
[16] Bader J, Zitzler E.HypE: analgorithm for fast hypervolume-based manyobjective optimization [J].Evolutionary Computation,2011,19 (1): 45- 76.   
[17] Qiao Junfei,Zhou Hongbiao,Yang Cuili，Yang Shengxiang.A decomposition-based multi-objective evolutionary algorithm with anglebased adaptivepenalty[J].Applied Soft Computing,2019,74():190- 205.   
[18] Murata T,Gen M. Cellular genetic algorithm for multi-objective optimization [C]/ Proc of the 4th Asian Fuzzy System Symposium. 2002: 538-542.   
[19] Ishibuchi H, Murata T.Amulti-objective genetic local search algorithm and its application to flowshop scheduling [J]. IEEE Trans on Systems, Man,and Cybernetics,Part C:Applications and Reviews,1998,28 (3): 392-403.   
[20] Li Hui, Zhang Qingfu. Multi-objective optimization problems with complicated pareto sets,MOEA/D and NSGA-II[J]. IEEE Trans on Evolutionary Computation, 2008,13 (2): 284-302.   
[21] Homaifar A, Qi C X, Lai S H. Constrained optimization via genetic algorithms [J]. Simulation,1994,62 (4): 242-253.   
[22] Jain H,Deb K.An evolutionary many-objective optimization algorithm using reference-point based nondominated sorting approach,part II: handling constraints and extending to an adaptive approach [J]. IEEE Trans on Evolutionary Computation,2013,18 (4): 602-622.   
[23] Cai Zixing，Wang Yong.A multi-objective optimization-based evolutionary algorithm for constrained optimization [J].IEEE Trans on Evolutionary Computation,2006,10 (6): 658-675.   
[24] Wang Yong,Cai Zixing,Zhou Yuren,et al.An adaptive tradeoff model forconstrained evolutionary optimization[J]. IEEE Transon Evolutionary Computation,2008,12 (1):80-92.   
[25]尚荣华，焦李成，马文萍．免疫克隆多目标优化算法求解约束优化 问题[J]．软件学报，2008(11):2943-2956.(Shang Ronghua, Jiao Licheng，Ma Wenping. Immune clonal multi-objective optimization algorithm for solving constrained optimization problems [J].Journal of Software,2008 (11): 2943-2956.)   
[26] SahaC,Das S,Pal K,etal. Afuzzy rule-based penalty function approach for constrained evolutionary optimization [J].IEEE Trans on Cybernetics, 2U14,4U(1∠). ∠yJJ-∠9UJ.   
[27] Yang Yongkuan,Liu Jianchang，Tan Shubin.A constrained multiobjective evolutionary algorithm based on decomposition and dynamic constraint-handling mechanism [J].Applied Soft Computing,2020,89: Article ID 106104.   
[28] Li Ke,Chen Renzhi,Fu Guangtao,et al. Two-archive evolutionary algorithm for constrained multi-objective optimization [J]. IEEE Trans on Evolutionary Computation,2018,23 (2):303-315.   
[29] Murata T,Gen M. Cellular genetic algorithm for multi-objective optimization [Cl/ Proc of the 4th Asian Fuzzy System Symposium. 2002: 538-542.   
[30] Bäck T, Hoffmeister F, Schwefel HP. Asurvey of evolution strategies [C/OL]/Proc of the 4th International Conference on Genetic Algorithms. 1994.(1994) [2022-03-31].https://www. researchgate. net/publication/2611416   
[31] Joines JA,Houck CR. On the use of non-stationary penalty functions to solve nonlinear constrained optimization problems with GA's [C]/ Proc of the lst IEEE Conference on Evolutionary Computation.IEEE World Congress on Computational Inteligence.1994: 579-584.   
[32] Coit D W, Smith A E, Tate D M. Adaptive penalty methods for genetic optimization of constrained combinatorial problems [J].INFORMS Journal on Computing,1996,8 (2): 173-182.   
[33]刘三阳，靳安钊．求解约束优化问题的协同进化教与学优化算法 [J]．自动化学报,2018,44(09): 1690-1697.(Liu Sanyang,Jin Anzhao. Co-evolutionary teaching and learning optimization algorithms for solving constrained optimization problems [J].Acta Automatica Sinica, 2018,44(09): 1690-1697.)   
[34] Deb K.An eficient constraint handling method for genetic algorithms [J]. Computer Methods in Applied Mechanics and Engineering,2000, 186 (2-4): 311-338.   
[35] Runarsson TP, Yao X. Stochastic ranking for constrained evolutionary optimization [J].IEEE Trans on Evolutionary Computation,2oo0,4 (3): 284-294.   
[36] Takahama T,Sakai S.Constrained optimization byε constrained particle swarmoptimizer withε-levelcontrolJ].Springer BerlinHeidelberg, 2005,29: 1019-1029.   
[37]周红标，乔俊飞．混合多目标骨干粒子群优化算法在污水处理过程 优化控制中的应用[J].化工学报，2017,68(9):3511-3521.(Zhou Hongbiao,Qiao Junfei.Application of hybrid multi-objective backbone particle swarm optimization algorithm in optimal control of wastewater treatment process[J]. Journal of Chemical Industry and Engineering, 2017,68 (9): 3511-3521.)   
[38] Azzouz R,Bechikh S,Ben Said L.Multi-objective optimization with dynamic constraints and objectives: new challenges for evolutionary algorithms [C]//Proc of Annual Conference on Genetic and Evolutionary Computation.2015: 615-622.   
[39] Jadaan OAL,Rajamani L,Rao C R.Non-dominated ranked genetic algorithm for solving constrained multi-objective optimization problems [J]. Journal of Theoretical & Applied Information Technology,2009,5 (5): 60-67.   
[40] Ning Weikang,Guo Baolong,Yan Yunyi,et al. Constrained multiobjective optimization using constrained non-dominated sorting combied with an improved hybrid multi-objective evolutionary algorithm[J].Engineering Optimization,2017,49 (10): 1645-1664.   
[41] Zhang Guofu, Su Zhaopin,Li Miqing,et al. Constraint handling in NSGA-II for solving optimal testing resource allocation problems [J]. IEEE Trans on Reliability,2017,66(4):1193-1212.   
[42.1 Jiao Licheng Inn Inaniian Shang Ronghua et al A modified nhiective

[43]Fan Lei,Liu Xiyang.An enhanced domination based evolutionary algorithm for multi-objective problems [Cl/ Proc of the 9th Intermational Conference on Computational Inteligence and Security. 2013: 95-99.   
[44] Ray T, Tai K, Seow K C.Multi-objective design optimization by an evolutionaryalgorithm[J].Engineering Optimization,20o1,33(4):399- 424.   
[45] Elarbi M,Bechikh S,Said L B.On the importance of isolated infeasible solutions in the many-objective constrained NSGA-II[J]. KnowledgeBased Systems,2021,227: Article ID 104335.   
[46] Yang Yongkuan,Liu Jianchang,Tan Shubin,et al.A multi-objective diferential evolution algorithm based on domination and constrainthandling switching [J].Information Sciences,2021,579:796-813.   
[47] Cuate O,Ponsich A,Uribe L,et al.A new hybrid evolutionary algorithm for the treatment of equality constrained MOPs [J]. Mathematics, 2020, 8 (1): 7.   
[48] Isaacs A,Ray T, Smith W.Blessings of maintaining infeasible solutions for constrained multi-objective optimization problems [C]//Proc of IEEE Congress on Evolutionary Computation.IEEE,2008: 2780-2787.   
[49] Deb K,Datta R.A fast and accurate solution of constrained optimization problems using a hybrid bi-objective and penalty function approach [C]// Proc of IEEE Congress on Evolutionary Computation.IEEE,2010:1-8.   
[50] Venkatraman S,Yen G G.A generic framework for constrained optimization using genetic algorithms [J]. IEEE Trans on Evolutionary Computation,2005,9 (4): 424-435.   
[51] Woldesenbet YG,Yen G G,Tessema B G.Constraint handling in multiobjective evolutionary optimization [J].IEEE Trans on Evolutionary Computation,2009,13 (3): 514-525.   
[52] Azzouz R,Bechikh S,Said LB,et al. Handling time-varying constraints and objectives in dynamic evolutionary multi-objective optimization [J]. Swarm and Evolutionary Computation,2018,39:222-248.   
[53] Ji B,Yuan X, Yuan Y. Modified NSGA-I for solving continuous berth allocation problem: using multi-objective constraint-handling strategy [J].IEEE Trans on Cybernetics,2017,47(9): 2885-2895.   
[54] Gadhvi B,Savsani V,Patel V.Multi-objective optimization of vehicle passive suspension system using NSGA-II, SPEA2 and PESA-II [J]. Procedia Technology,2016,23:361-368.   
[55] Sorkhabi SY D,Romero DA,Beck JC,et al. Constrained multiobjective wind farm layout optimization: novel constraint handling approach based on constraint programming [J]. Renewable Energy,2018, 126: 341-353.   
[56] Abul'Wafa A R. Optimization of economic/emission load dispatch for hybrid generating systems using controlled elitist NSGA-II[J]. Electric Power Systems Research,2013,105: 142-151.   
[57] Bora T C,Mariani V C,dos Santos Coelho L.Multi-objective optimizationoftheenvironmental-economicdispatchwith reinforcement learning based on non-dominated sorting genetic algorithm[J].Applied Thermal Engineering,2019,146: 688-700.   
[58] Song M, Chen D.An improved knowledge-informed NSGA-II for multiobjective land allocation (MOLA)[J]. Geo-spatial Information Science, 2018,21 (4): 273-287.   
[59] Rathnayake U.Review of binary tournament constraint handling technique in NSGA I for optimal control of combined sewer systems [J]. Journal of Information and Optimization Sciences,2016,37(1): 37-49.   
[60] Rathnayake U S,Tanyimboh T T.Optimal control of combined sewer systems using SWMM 5.0[J]. Transactions on the Built Environment,   
[61]周红标．基于约束多目标骨干粒子群的污水处理过程优化控制[J]. 电子测量与仪器学报，2017,31(9):1488-1498.(Zhou Hongbiao. Optimal control of wastewater treatment process based on constrained multi-objective backbone particle swarm [J]. Journal of Electronic Measurement and Instrument,2017,31 (9):1488-1498.)   
[62] GarciaJLL,Monroy R,HernandezVA S,et al. COARSE-EMOA: An indicator-based evolutionary algorithm for solving equality constrained multi-objective optimization problems [J]. Swarm and Evolutionary Computation,2021,67: Article ID 100983.   
[63] Scimemi G F,Rizzo S.An hypervolume based constraint handling technique for multi-objective optimization problems [C/OL]/Proc of the 20th Congr.Ital.Assoc.Theor. Appl.Mech,2011.(2011) [2022-03-31] http://hdl. handle. net/10447/77182   
[64] Said R,Bechikh S,Louati A,etal.Solving combinatorial multi-objective bi-level optimization problems using multiple populations and migration schemes [J]. IEEE Access,2020,8: 141674-141695.   
[65] Guo Jianmei,Liang Jiahui,Shi Kai,et al. SMTIBEA:a hybrid multiobjective optimization algorithm for configuring large constrained software product lines [J]. Software & Systems Modeling,2019,18 (2): 1447-1466.   
[66] Antonio L M, Coello CA C.Indicator-based cooperative coevolution for multi-objectiveoptimization[C]//Procof IEEE Congresson Evolutionary Computation (CEC).IEEE,2016: 991-998.   
[67] BenMansour I,Alaya I,Tagina M. Indicator weighted based multiobjective approach using self-adaptive neighborhood operator[J]. Procedia Computer Science,2021,192: 338-347.   
[68] MansourIB,Alaya I. Indicator based ant colony optimization for multiobjective knapsack problem[J].Procedia Computer Science,2015,60: 448-457.   
[69] Yuan Jiawei,Liu Hailin,OngY S,et al.Indicator-based evolutionary algorithm for solving constrained multi-objective optimization problems [J]. IEEE Trans on Evolutionary Computation, 2021: 1.   
[70] LiuZhizhong，Wang Yong，WangBingchuan． Indicator-based constrained multi-objective evolutionary algorithms [J]. IEEE Trans on Systems,Man,and Cybermetics: Systems,2019,51(9): 5414-5426.   
[71] Wang Yibo，Hotz L. Optimal feature selection via evolutionary algorithms and constraint solving [Cl// Proc of 18th International Configuration Workshop.2016: 97.   
[72] Shi Kai, Yu Huiqun, Guo Jianmei, et al. Aparalel portfolio approachto configuration optimization for large software product lines [J]. Software: Practice and Experience,2018,48 (9): 1588-1606.   
[73] Li Yahui, Li Yang. Security-constrained multi-objective optimal power flow for a hybrid AC/VSC-MTDC system with lasso-based contingency filtering [J]. IEEE Access,2019,8: 6801-6811.   
[74] Tangpattanakul P,Jozefowiez N,Lopez P.A multi-objective local search heuristic for scheduling earth observations taken by an agile satellite [J]. European Journal of Operational Research,2015,245 (2): 542-554.   
[75] Miyakawa M, Sato H, Sato Y. Directed mating in decomposition-based MOEA for constrained many-objective optimization [C]// Proc of Genetic and Evolutionary Computation Conference. 2018: 721-78.   
[76] Elarbi M,Bechikh S,Said L B.On the importance of isolated solutions in constrained decomposition-based many-objective optimization [Cl/ Proc of Genetic and Evolutionary Computation Conference.2O17: 561- 568.   
[77] Fan Zhun，Fang Yi,Li Wenji,et al.MOEA/D with angle-based constrained dominance principle for constrained multi-objective optimization problems [Jl.Applied Soft Computing.2019.74: 621-633.   
[78] Asafuddoula M,Ray T,Sarker R,et al. An adaptive constraint handling approach embedded MOEA/D [C]// Proc of IEEE Congresson Evolutionary Computation.IEEE,2012:1-8.   
[79] Fan Zhun,Li Hui,Wei Caimin,et al.An improved epsilon constraint handling method embedded inMOEA/D for constrained multi-objective optimization problems [C]// Proc of IEEE Symposium Series on Computational Intelligence (SSCI) .IEEE,2016:1-8.   
[80] Martinez S Z,Coello CA C.A multi-objective evolutionary algorithm based on decomposition for constrained multi-objective optimization [C]//Proc ofIEEE Congress on Evolutionary Computation(CEC).IEEE, 2014: 429-436.   
[81] Zhu Qingling,Zhang Qingfu,Lin Qiuzhen.Aconstrained multi-objective evolutionary algorithm with detect-and-escape strategy [J].IEEE Trans on Evolutionary Computation,2020,24 (5): 938-947.   
[82] Zapotecas-Martinez S,Ponsich A.Constraint handling within MOEA/D through an additional scalarizing function [C]// Proc of Genetic and Evolutionary Computation Conference.2020:595-602.   
[83] Peng Chaoda,Liu Hailin.A decomposition-based constraint-handling technique for constrained multi-objective optimization [C]// Proc of IEEE/WIC/ACM International Conference on Web Intelligence Workshops.ACM,2016:129-134.   
[84] Wang Bingchuan,Li Hanxiong,Zhang Qingfu,et al.Decompositionbased multi-objective optimization for constrained evolutionary optimization [J].IEEE Trans on Systems,Man,and Cybernetics: Systems, 2018,51(1): 574-587.   
[85] Cai Xinye,Mei Zhiwei,Fan Zhun,et al.A constrained decomposition approach with grids for evolutionary multi-objective optimization [J]. IEEE Trans on Evolutionary Computation,2017,22 (4): 564-577.   
[86] Cai Xinye,Xia Chao,Zhang Qingfu,et al.The collaborative local search basedondynamic-constrained decompositionwith gridsfor combinatorial multi-objective optimization [J].IEEE Transon Cybernetics,2019,51 (5):2639-2650.   
[87] Chen Jie,Li Juan,Bin Xin.DMOEA-εC:Decomposition-based multiobjective evolutionary algorithm with the ε-constraint framework [J]. IEEE Trans.Evolutionary Computation.2017,21(5): 714-730.   
[88] Liu Hailin,Peng Chaoda,Gu Fangqing,et al.A constrained multiobjective evolutionary algorithm based on boundary search and archive [J].International Journal of Pattern Recognition and Artificial Intelligence,2016,30 (01):Article ID 1659002.   
[89] Zhu Yongsheng，Wang Jie,Qu Boyang.Multi-objective economic emission dispatch considering wind power using evolutionary algorithm based on decomposition [J]. International Journal of Electrical Power & Energy Systems,2014,63:434-445.   
[90] Biswas PP, SuganthanPN,MallipeddiR,et al.Multi-objective optimal power flow solutions using a constraint handling technique of evolutionary algorithms [J]. Soft Computing,2020,24 (4): 2999-3023.   
[91] Zhou Hongbiao，Qiao Junfei．Multi-objective optimal control for wastewater treatment process using adaptive MOEA/D [J]，Applied Intelligence,2019,49 (3):1098-1126.   
[92] Li Wenji,Fan Zhun,Cai Xinye,et al.Design optimization of MEMS using constrained multi-objective evolutionary algorithm [C]// Proc of Companion Publication of the Annual Conference on Genetic and Evolutionary Computation.2014:1175-1180.   
[93] Hu Wanzhe,Fathi M,Pardalos P M.A multi-objective evolutionary algorithm based on decomposition and constraint programming for the multi-objective team orienteering problem with time windows [J]. Applied Soft Computing,2018,73:383-393.   
[94]Li Junqing,Tao Xinrui,Jia Baoxian,et al.Effcient multi-objective algorithm for the lot-streaming hybrid flowshop with variable sub-lots [J].Swarm and Evolutionary Computation,2020,52:Article ID 100600.