# 基于延迟函数次梯度启发式道路交通补偿策略

刘艳锐，姚笛，李金培(上海交通大学 安泰经济与管理学院，上海 200030)

摘要：拥挤收费被认为是解决交通拥挤的有效方法，解决道路交通拥堵的主要想法是，对于有些容易造成拥堵的道路进行收费，而对于其他未充分利用的道路进行适当补偿，对此提出一种基于延迟函数的次梯度启发式道路交通补偿策略。首先，给出道路集的收费/补贴的非线性规划模型，主要是基于Beckmann最小化目标函数实现，然后利用库恩-希尔斯条件和拉格朗日乘子建立模型的条件约束；其次，基于启发式算法建立道路交通的定价补偿策略，利用边际成本建立延迟函数分析模型，然后基于次梯度法进行模型的优化；最后，通过在真实道路网络上的仿真实验，显示所提算法在旅行时间、交通流量、收敛性等指标上均具有较好的性能，验证了算法的有效性。

关键词：延迟函数；次梯度；启发式；道路交通；补偿策略中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.07.0704

# Subgradient heuristic method for road trafc compensation based on delay function

Liu Yanrui, Yao Di, Li Jinpei (AntaiCollege ofEconomics&Management,Shanghai Jiaotong University,Shanghai200030)

Abstract:This paper considers thecongestionpricing tobethe effective way to solve thetrafficcongestion,the main idea of roadtraficcongestionis tochargeforsomeeasytocauseroadcongestion,andappropriatecompensationforotherunderutilized roads,and here presents a subgradient heuristic trafc delay compensationstrategybasedon function.Firstly,here use a nonlinearprogramming model intheroad tol/subsidies,beckmann is the main realization basedonminimizingtheobjective function,anduses theKuhnhils-Lagrangemultipliermodeltoconstructtheconstraintcondition;Secondly,thealgorithmuses the pricing compensation strategytoestablish theroad trafic modelbasedonheuristic algorithm,andalsouses the marginal cost modeltoestablishthedelayfunctionanalysis model.Finaly,thesimulation experiments onrealroad networksshowthat theproposedalgorithmhasbeterperformanceintermsoftaveltime,traficflow,convergenceandsoon,andtheefctiveess of the proposed algorithm is verified.

Key Words: delay function; subgradient; heuristic; road traffic; compensation strategy

# 0 引言

交通堵塞会对经济社会造成巨大损失，2016年美国市区的拥堵费为1010亿美元[I\~2]。最近的一项研究表明，澳大利亚首都城市2015年度的拥塞成本估计约17.5亿美元的，而年度的拥塞成本是12.8亿，该值得到了大幅增加。因此，研究交通拥塞解决问题，具有非常重要的研究价值[3]。

利用供求关系分析，当需求大于供给时就会发生阻塞。因此，可以通过增加供给或降低需求来解决拥塞问题[4]。在供给侧，可建造更多的道路实现交通的分流。在需求方面，可利用经济文献中提出的拥挤定价策略进行设计，实现供给和需求过程的平衡。例如，文献[5]提出了一个随时间变化的定价方案，包括在同一路线上的通行费和补贴。文献[6]讨论了一种再分配方案，可实现从理想路线收集的流量转移到不太理想的路线上。文献[7]研究了帕累托改进的交通定价的多用户存在问题。在限制帕累托改善条件的情况下，如果存在显著的间隙，交通定价问题总是存在一个解决方案。文献[8]研究了利用奖励措施，引导通行者选择拥堵程度较弱的路段。文献[9]研究基于纯粹补贴（没有任何收费）机制的交通引导策略，其目的是减少城市网络中的拥塞。

上述方法思路都是针对一些高度拥挤的道路，旨在重新分配流量负载均匀分布在整个网络包括不拥挤的道路。此类方法类似于一种专家策略，并未定义问题的梳理模型进行分析，优化效果不理想。为此，本文在给出交通定价补偿数学规划模型基础上，实现道路交通补偿的优化。

# 1 数学模型

# 1.1问题描述

给定一组具有上限容量的道路，需进行收费或者补贴，即交通定价方案。该问题本质上是一个容量限制交通分配问题(CTAP)。考虑 $G \big ( N , A \big )$ 是一个交通网络图，其具有 $N$ 个节点，$A$ 是连接 $R \subset N \times N$ 上源节点和目的节点的道路。道路集的收费/补贴可表示为 ${ \overline { { A } } } \subset A$ 。CTAP 可归结为如下非线性规划问题：

$$
m i n \ z { \big ( } x { \big ) } = \sum _ { a \in A } \int _ { 0 } ^ { x _ { a } } t _ { a } { \big ( } x { \big ) } d x
$$

s.t.

$$
\left\{ \begin{array} { l l } { \sum _ { \ d _ { p } } f _ { \ d _ { p } , \ d _ { r } } = q _ { \ d _ { r } } } \\ { r \in R \to { \mathrm { L a g r a n g e ~ m u l t i p l i e r } } ( w _ { \ d _ { r } } ) } \end{array} \right.
$$

$$
f _ { p , r } \geq 0 p \in P _ { r } , r \in R
$$

$$
\displaystyle x _ { _ a } = \sum _ { r } \sum _ { p } f _ { _ p , r } \delta _ { _ { a , p } } ^ { r } ~ a \in A , p \in P _ { _ r } , r \in R \left( 4 \right)
$$

$$
\left\{ \begin{array} { l l } { x _ { a } \leq C _ { a } } \\ { a \in \overline { { A } } \to \mathrm { L a g r a n g e ~ m u l t i p l i e r } ( \beta _ { a } ) } \end{array} \right.
$$

其中: $z$ 是Beckmann最小化目标函数； $x _ { _ a }$ 是道路 $a$ 上的交通流量； $q _ { r }$ 是与OD对 $r \in R$ 相对应的运输需求； $f _ { p , r }$ 是与OD 对相连接路径 $p$ 上的交通流量； $P _ { _ { r } }$ 是与OD对相连接的所有路径集合； $\delta _ { a , p } ^ { r }$ 是道路路径的隶属度，如果 $a \in p$ 则 $\delta _ { a , p } ^ { r } = 1$ ，否则 $\mathcal { S } _ { a , p } ^ { r } = 0$ ·$C _ { a }$ 是路径 $a$ 的交通容量。

# 1.2库恩-希尔斯条件和拉格朗日乘子

实践证明，CTAP在线性约束条件下是严格凸问题，呈现独特的道路流量全局最优解。考虑 $w _ { r }$ 和 $\beta _ { _ a }$ 分别作为运输需求和容量限制的拉格朗日乘子。则可构建如下库恩-希尔斯条件（KKT）条件：

$$
f _ { _ { p , r } } \left( u _ { _ { p , r } } + \sum _ { a \in A } \delta _ { a , p } ^ { r } \beta _ { a } - w _ { _ r } \right) = 0
$$

$$
\beta _ { _ a } \left( C _ { _ a } - x _ { _ a } \right) = 0
$$

$$
u _ { _ { p , r } } + \sum _ { a \in A } \delta _ { a , p } ^ { r } \beta _ { a } - w _ { _ r } \geq 0
$$

$$
C _ { a } - x _ { a } \ge 0 , f _ { p , r } \ge 0 , \beta _ { a } \ge 0
$$

$$
\sum _ { p } f _ { p , r } = q _ { r }
$$

其中： $u _ { _ { p , r } } = \sum _ { a \in A } \delta _ { a , p } ^ { r } t _ { a }$ 是在连接OD对 $p$ 路径上的总的运输时间，有关参数取值设定如下： $p \in P _ { r }$ ， $r \in R ^ { \prime } , { \it \Delta \phi } _ { a \in \overline { { A } } }$ 。定义 $\hat { u } _ { { } _ { p , r } }$ 为相应路径的运输时间为

$$
\hat { u } _ { p , r } = \sum _ { a \in A } \delta _ { a , p } ^ { r } \left( t _ { a } + \beta _ { a } \right)
$$

将式（11）代入式（6）（8）可得

$$
f _ { p , r } ( \hat { u } _ { p , r } - w _ { r } ) = 0
$$

$$
\hat { u } _ { { } _ { p , r } } - w _ { { } _ { r } } \ge 0
$$

利用式 $( 1 2 ) \sim ( 1 3 )$ 可以证明， $w _ { r }$ 是与OD 对相连接的最短路径传输时间；因此，如果一个路径需要一定的交通量$f _ { _ { p , r } } > 0$ ，这肯定是最短的路径。根据式 $( 7 ) \sim ( 9 )$ ，如果容量约束是饱和的，即 $\ x _ { _ a } = C _ { _ a }$ ，那么相应的拉格朗日乘子为非零，即 $\beta _ { _ a } > 0$ ；否则 $\beta _ { _ a } = 0$ 。式(11)中有两项有助于增加传输时间：正常或巡航传输时间 $t _ { _ a }$ 和 beta 项 $\beta _ { _ a } \circ \beta _ { _ a }$ 可以解释为收费/补贴价值或防止道路的运输延迟出现过饱。

在文献中，beta 项也可解释为在过饱和的道路排队堆积造成等待时间。如图所示，代表通行费或补贴价值的beta项是正数，而补贴应该是负值。接下来，将提出一种策略防止出现任何的负面循环。

# 1.3行程时间加强

首先假设只有收费和没有补贴。在制定收费标准后，会把模型扩大到补贴。考虑延迟函数 $t _ { \phantom { } _ { a } } = t _ { \phantom { } _ { a } } ^ { \phantom { } 0 } \bigl ( + f \bigl ( x _ { \phantom { } _ { a } } \bigr ) \bigr )$ ，其中 $t _ { _ a } ^ { \scriptscriptstyle 0 }$ 是行人在道路 $a$ 上的自由行走时间， $f \left( x _ { _ a } \right) \geq 0$ 是非递减的，函数 $x _ { _ a }$ 的凸函数满足 $f \left( x _ { _ a } \right) = 0 \big | x _ { _ a } = 0$ 。可以直观地认为，只要是空的或不拥挤的道路，行程时间是自由流的时间，即x\~0=>𝑡≈t;随着交通量的构建，行程时间 $t _ { _ a }$ 也相应增加，肯定比自由流时间高。根据式（11)，饱和路段的行程时间 $\hat { t } _ { _ a }$ 可表示为

$$
\hat { t } _ { { } _ { a } } = \big ( t _ { { } _ { a } } ^ { 0 } + b _ { { } _ { a } } \big ) \big ( 1 + f \big ( x _ { { } _ { a } } \big ) \big )
$$

$$
\beta _ { _ a } = \hat { t } _ { _ a } - t _ { _ a } = b _ { _ a } \big ( 1 + f \big ( x _ { _ a } \big ) \big )
$$

其中: $b _ { _ a }$ 是式（14）中自由流时间的附加惩罚。换言之， $b _ { _ a }$ 是在$x _ { _ a } = 0$ 时的 beta值。注意，前面已经证明，行程时间中的附加惩罚项与各自容量限制的拉格朗日值相同，见式(11)中的 $\beta _ { _ a }$ 口因此，在CTAP的行程时间利用增强的行程时间进行更换，即（20 $t _ { _ a } \gets \hat { t } _ { _ a }$ ，同时容量限制也下降了。如果已经知道 beta( $b e t a ( \beta _ { a } ) ~ )$ （20的全局最优值（CTAP中)，只需要基于任何已知的算法或软件，利用膨胀的行程时间解决TAP问题即可。

# 2 基于启发式的定价补偿策略

# 2.1启发式beta 值更新算法

式（14)\~(15）的主要功能是解除过饱和道路的延时功能，直到交通量稳定在容量水平内。延迟函数中的初始beta 值（204号 $( \ b e t a ( \beta _ { a } )$ )是迭代更新的，主要挑战是收敛性和用户平衡性。容量限制和交通分配之间存在很强的相关性，拥挤收费的一般理论是以边际成本为基础定价策略。则行程时间可表示为

$$
\hat { t } _ { a } \left( x _ { a } \right) = t _ { a } \left( x _ { a } \right) + x _ { a } \cdot \hat { \mathcal { O } } t _ { a } \left( x _ { a } \right) / \hat { \mathcal { O } } x _ { a }
$$

其中: $\hat { t } _ { { } _ { a } } ( x _ { { } _ { a } } )$ 是那些已经穿越公路的额外的上下班人员的边际成本或旅行时间。 $\partial t _ { a } \left( x _ { _ a } \right) / \partial x _ { _ a }$ 是道路 $x _ { _ a }$ 上的每个司机所经历的额外旅行时间。通过边际成本在网络上实现系统最优流量，并拓展未充分利用的公路。因此，利用 $\boldsymbol { x } _ { a } \cdot \hat { \boldsymbol { \alpha } } t _ { a } \left( \boldsymbol { x } _ { a } \right) / \hat { \boldsymbol { \alpha } } \boldsymbol { x } _ { a }$ 作为一个模板来更新初始测试如下：

$$
\hat { t } _ { _ { a C } } ^ { ( i ) } = \Big ( t _ { _ a } ^ { ^ 0 } + b _ { _ a } ^ { ( i ) } \Big ) \Big ( 1 + f \big ( C _ { _ a } \big ) \Big )
$$

$$
\nabla b _ { a } ^ { ( i ) } = \left( x _ { a } ^ { ( i ) } - C _ { a } \right) \frac { \hat { t } _ { a } ^ { ( i ) } - \hat { t } _ { a C } ^ { ( i ) } } { C _ { a } }
$$

$$
b _ { a } ^ { ( i + 1 ) } = b _ { a } ^ { ( i ) } + \nabla b _ { a } ^ { ( i ) }
$$

其中:上标 $i$ 和 $a$ 表示当前迭代和各自（过）饱和的道路； $\hat { t } _ { _ { a C } } ^ { ( i ) }$ 表示膨胀延迟函数在容量为 $\ x _ { _ a } = C _ { _ a }$ 时的旅行时间； $b _ { a } ^ { ( i ) }$ 是免费行程时间附加惩罚。 $\nabla b _ { a } ^ { ( i ) }$ 是在当前迭代中初始 beta 的计算速度。

式（18）中，满足边际成本原则，即利用 $\boldsymbol { x } _ { a } \cdot \partial t _ { a } \left( \boldsymbol { x } _ { a } \right) / \partial \boldsymbol { x } _ { a }$ 更新速度值。 $x$ 可由额外的交通流量 $\left( \boldsymbol { x } _ { a } ^ { ( i ) } - \boldsymbol { C } _ { a } \right)$ 进行替换，延迟函数斜率 $\left( d t / d x \right)$ 可由膨胀的旅行时间的斜率减去容量值归一化步长值获得，即 $\Big ( \hat { t } _ { { a } } ^ { ( i ) } - \hat { t } _ { { a C } } ^ { ( i ) } \Big ) \Big / C _ { { a } }$ 。图1(a)中，给出式（17）\~(19)膨胀延迟函数的三次迭代图形化表示形式。在第一次迭代时，没有初始 beta 值 ${ \mathrm i n i t i a l - b e t a ( b } _ { a } )$ ，即 $b _ { _ a } ^ { ( 1 ) } = 0$ ，容量控制在$\boldsymbol { x } _ { a } ^ { ( 1 ) } > C _ { a }$ ，速度值 $\nabla b _ { a } ^ { \scriptscriptstyle ( 1 ) } > 0$ 是计算机图形显示，其提升下一次迭代的延迟函数，即 $b _ { a } ^ { ( 2 ) } = 0 + \nabla b _ { a } ^ { ( 1 ) }$ 。在第二次迭代中，即使它是膨胀旅行时间 $\nabla b _ { a } ^ { ( 1 ) }$ ，交通量仍高于通行能力，即 $x _ { _ a } ^ { ( 2 ) } > C _ { _ a }$ 。因此，速度值 $b _ { a } ^ { ( 2 ) } > 0$ 用来计算第三次迭代值： $b _ { a } ^ { ( 3 ) } = b _ { a } ^ { ( 2 ) } + \nabla b _ { a } ^ { ( 2 ) }$ 。执行第三次迭代，容量保持不变，即 $x _ { _ a } ^ { ( 3 ) } = C _ { _ a }$ 。算法有三个关键组件：$b e t a ( \beta _ { a } )$ ，initial $- b e t a { \left( b _ { _ { a } } \right) }$ 和速度 $\nabla b _ { _ a }$ ，如图1所示。

![](images/f5d74823062f18e1e2a1da6625573c64b15dc0f545791bec6b9a13341f55e1b9.jpg)  
图1所提道路延迟函数表示方法

在给出这种渐进的方法中，如果一个（以上）饱和路发现是不饱和的，在中间的迭代位置，其相应的惩罚是无效的。见图1(b)，即 $p _ { a } ^ { ( i + 1 ) } = 0 \big | x _ { a } ^ { ( i ) } < C _ { a }$ 。上述 $i n i t i a l - b e t a ( b _ { \circ } )$ 计算过程,可用两条规则加以总结：

$$
b _ { a } ^ { ( i + 1 ) } = \left\{ \begin{array} { l l } { b _ { a } ^ { ( i ) } + \nabla b _ { a } ^ { ( i ) } , x _ { a } ^ { ( i ) } \geq C _ { a } } \\ { 0 , x _ { a } ^ { ( i ) } < C _ { a } } \end{array} \right.
$$

上面设定符合在产能分配问题的KKT稳定点条件，据前所述，beta项可解释为在过饱和的道路排队堆积造成等待时间，因此对于非饱和路段的beta值最终设定为0。

# 2.2定价补偿策略

现在可以把定价补贴包括在模型中。如前所述，一个负循环可能破坏整个定价过程。为了避免这种情况，确保道路的旅行时间始终保持为正常值。为此，首先取消所有收费/补助道路的免费通行时间，然后将初始beta初始化到相应的自由流旅行时间。实际上，没有任何变化，延迟函数保持不变：

$$
\begin{array} { c } { { { \displaystyle { \left\{ b _ { a } ^ { \left( 0 \right) } = t _ { a } ^ { \left( \right) } \right.}  } } }  \\ { { { \left. t _ { a } ^ { \left( \right) } = 0 \right.}  } } \end{array}
$$

具体如图1（c）所示，在迭代计算的最后一步，根据获得的beta值，获得在A或B上的延迟函数。beta值减去自由流时间 $\beta _ { a } - t _ { a } ^ { 0 }$ ，可以产生正值(延迟函数A)或负值(延迟函数B)，分别代表通行费或补贴。此外，补贴的绝对价值不能超过自由流通时间。换句话说，没有哪条路会出现负数的旅行时间；因此，不会出现负循环。

给定最后一次迭代（迭代 $\mathbf { \Omega } _ { n }$ ）输出，收费/补贴值（ $- t _ { a } ^ { 0 } \leq s _ { a } \leq + \infty$ ）可计算如下：

$$
s _ { { \scriptscriptstyle a } } = \bar { t } _ { { \scriptscriptstyle a } } ^ { \prime } { } ^ { \bar { B } } - t _ { { \scriptscriptstyle a } } ^ { \mathrm { 0 } } \Big ( 1 + f \big ( \overline { { C } } _ { \alpha } \big ) \Big )
$$

# 2.3算法流程

图2给出收费/补贴的定价方案流程图。

![](images/6df3ca706a0aab7624492d87c737aa8983c2f796945a31ff367d08e305056227.jpg)  
图2收费/补贴的定价方案流程图

如果旅行需求高于网络的容量，问题就变得不可行。可引入一个通过道路高行程时间与所有区域相连的虚拟节点。该算法可以很容易地集成到一个传统的TAP 解决方案中，如弗兰克-沃尔夫方法。鉴于initial-beta值的逐渐积累，收敛准则可定义为低于步数值的一个普通值的，具体形式为

$$
\operatorname* { m a x } _ { a } \big | \nabla b _ { a } ^ { ( i ) } \big / \widehat t _ { a } \big | \leq \varepsilon
$$

计算结果表明： $\varepsilon = 1 \%$ 就足以获得可靠的结果。因此，该算法不终止，除非这两个标准的相对差距和相对速度值得到满足。迭代求解容量约束的拉格朗日乘子值的尝试，事实上相当于解决了原来CTAP部分的对偶变换。结果表明，部分对偶梯度问题导致交通量向量过大，次梯度法被认为是一个有效的求解算法。

# 2.4收敛性讨论

上述算法本质上是一种次梯度方法，可基于交通量过大的情况，迭代地更新了对偶值。子梯度法的一个关键组成部分是步长，它被均匀地应用于所有道路，并且可能在迭代过程中变化。为了保证收敛，步长值必须符合一组规则。相反，本文提出了一个直观的步长选择机制（类似于边际成本)，排斥每一条道路和迭代。上述方法的最优性条件和收敛性方面，本文方法的新颖之处是将拉格朗日值转换为通行费/补贴值。为此，当CTAP终止时，自由流时间先清零；利用最终的旅行时间和原始的旅行时间函数的区别，指定收费/补贴值。

根据式（18）和（20）可知，当 $\boldsymbol { x } _ { a } ^ { ( i ) } \geq C _ { a }$ 时，$\nabla b _ { a } ^ { ( i ) } = \left( x _ { a } ^ { ( i ) } - C _ { a } \right) \frac { \hat { t } _ { a } ^ { ( i ) } - \hat { t } _ { a C } ^ { ( i ) } } { C _ { a } }$ 中的 $\left( \boldsymbol { x } _ { a } ^ { ( i ) } - \boldsymbol { C } _ { a } \right)$ 项为正值, 项为负值，亦即 $\nabla b _ { a } ^ { ( i ) }$ 取值为负值，满足梯度优化中的扶梯度条件。因此，算法收敛。

# 3 实验分析

# 3.1实验设置

该方法利用macro进行编码，这是一种交通规划软件Emme3的专用编程语言的，其中无容量限制TAP过程采用弗兰克-沃尔夫算法求解。使用一台具有 $3 . 6 0 ~ \mathrm { G H z }$ 的CPU和16GBRAM的台式PC机；其次，使用现实生活中的一个大型的道路网络例子对算法性能进校验证，该道路网络案例，来自上海市，如图3所示。

该案例由154个区、943个节点和3075条定向道路组成，每小时的车辆通行需求量为56219辆。该城市是由两个河流一分为二，河流位置位于城市的中间。根据流量调查和实地观察，交通局在提出了理想的交通分配，以避免在上午高峰时段发生重大交通堵塞。图4中， $_ { 1 \sim 1 1 }$ 标号为河流上的桥梁。

在本研究中，收费/补贴的局部和目标流量值是已知的，可由外部给定。为此在表1中，给出包括过境交通量在内的过境点的特征量取值，其中 $t _ { _ a } ^ { \scriptscriptstyle 0 }$ 为自由流旅行时间， $\bar { C } _ { a }$ 道路的物理容量， $C _ { a }$ 交通量上限。

![](images/f1502adadb522e46c864723cb6cc1c9894081f2870a39ea3e51fe419d3866aa1.jpg)  
图3道路网络案例

表1输入和输出值设定  

<html><body><table><tr><td>道路ID</td><td>方向ID</td><td>t</td><td>C</td><td>C</td><td>交通流量</td><td>X</td><td>x/C</td><td></td><td>S</td><td>通行费/补贴</td></tr><tr><td>1</td><td>1-1</td><td>0.77</td><td>2500</td><td>1800</td><td>828.93</td><td>1796.92</td><td>99.83</td><td>2.66</td><td>1.86</td><td>0.52</td></tr><tr><td></td><td>1-2</td><td>0.77</td><td>2500</td><td>1800</td><td>183.76</td><td>185</td><td>10.28</td><td>0.03</td><td>-0.74</td><td>-0.21</td></tr><tr><td>2</td><td>2-1</td><td>0.84</td><td>750</td><td>750</td><td>722.32</td><td>727.05</td><td>96.94</td><td>0.03</td><td>-0.92</td><td>-0.26</td></tr><tr><td></td><td>2-2</td><td>0.84</td><td>750</td><td>750</td><td>762.35</td><td>750.24</td><td>100.03</td><td>7.08</td><td>6.11</td><td>1.7</td></tr><tr><td>3</td><td>3-1</td><td>0.25</td><td>2500</td><td>1800</td><td>600.48</td><td>348.27</td><td>19.35</td><td>0.01</td><td>-0.24</td><td>-0.07</td></tr><tr><td></td><td>3-2</td><td>0.25</td><td>2500</td><td>1800</td><td>2759.71</td><td>1801.39</td><td>100.08</td><td>8.63</td><td>8.37</td><td>2.33</td></tr><tr><td>4</td><td>4-1</td><td>0.35</td><td>2500</td><td>1800</td><td>1205.92</td><td>1800.78</td><td>100.04</td><td>7.2</td><td>6.84</td><td>1.9</td></tr><tr><td></td><td>4-2</td><td>0.35</td><td>2500</td><td>1800</td><td>84.03</td><td>108.25</td><td>6.01</td><td>0.01</td><td>-0.33</td><td>-0.09</td></tr><tr><td>5</td><td>5-1</td><td>0.44</td><td>1750</td><td>1750</td><td>1641.31</td><td>1749.8</td><td>99.99</td><td>9.52</td><td>9.02</td><td>2.51</td></tr><tr><td></td><td>5-2</td><td>0.44</td><td>1750</td><td>1750</td><td>469.82</td><td>403.75</td><td>23.07</td><td>0.02</td><td>-0.42</td><td>-0.12</td></tr><tr><td>6</td><td>6-1</td><td>0.23</td><td>2625</td><td>1800</td><td>2446.11</td><td>1802.87</td><td>100.16</td><td>12.18</td><td>11.95</td><td>3.32</td></tr><tr><td></td><td>6-2</td><td>0.23</td><td>1750</td><td>1750</td><td>785.81</td><td>592.48</td><td>33.86</td><td>0.01</td><td>-0.22</td><td>-0.06</td></tr><tr><td>7</td><td>7-1</td><td>0.16</td><td>2500</td><td>1800</td><td>2313.34</td><td>1796.73</td><td>99.82</td><td>12.85</td><td>12.68</td><td>3.53</td></tr><tr><td></td><td>7-2</td><td>0.16</td><td>2500</td><td>1800</td><td>656.64</td><td>389.2</td><td>21.62</td><td>0.01</td><td>-0.15</td><td>-0.04</td></tr><tr><td>8</td><td>8-1</td><td>0.23</td><td>1750</td><td>1750</td><td>2035.5</td><td>1751.26</td><td>100.07</td><td>11.73</td><td>11.47</td><td>3.19</td></tr><tr><td></td><td>8-2</td><td>0.23</td><td>2625</td><td>1800</td><td>783</td><td>752.7</td><td>41.82</td><td>0.01</td><td>-0.22</td><td>-0.06</td></tr><tr><td>9</td><td>9-1</td><td>0.57</td><td>2625</td><td>1800</td><td>1683.56</td><td>1795.59</td><td>99.76</td><td>12.75</td><td>12.16</td><td>3.38</td></tr><tr><td></td><td>9-2</td><td>0.47</td><td>2625</td><td>1800</td><td>903.52</td><td>824.2</td><td>45.79</td><td>0.02</td><td>-0.45</td><td>-0.12</td></tr><tr><td>10</td><td>10-1</td><td>0.30</td><td>2550</td><td>1800</td><td>1547.86</td><td>1092.88</td><td>60.72</td><td>0.01</td><td>-0.29</td><td>-0.08</td></tr><tr><td></td><td>10-2</td><td>0.27</td><td>3750</td><td>1800</td><td>3261.11</td><td>1802.74</td><td>100.15</td><td>15.13</td><td>14.86</td><td>4.13</td></tr><tr><td>11</td><td>11-1</td><td>0.59</td><td>2500</td><td>1800</td><td>189.06</td><td>629.38</td><td>34.97</td><td>0.02</td><td>-0.57</td><td>-0.16</td></tr><tr><td></td><td>11-2</td><td>0.59</td><td>2500</td><td>1800</td><td>289.45</td><td>1505.82</td><td>83.66</td><td>0.02</td><td>-0.58</td><td>-0.16</td></tr></table></body></html>

# 3.2结果分析

该算法迭代运行237次，直到相对间隙和相对步长值分别下降到0.0001和0.01以下。计算时间仅为15秒。计算结果包括交通量、膨胀旅行时间以及通行费/补贴值也如表2所示。为满足交通量的限制，如 $x _ { _ a } / C _ { _ a }$ 列所示的轻微违规行为小于 $1 \%$ ，这可以归因于ITT是一种启发式算法，存在一定的越限情况。图5显示了关于道路1,2和3的连续迭代的交通量和膨胀旅行时间的变化。

图5所示结果显示，结果表明，这种变化在早期迭代中是不稳定的，其会导致交通量变化和旅行时间变化不恒定，但随着迭代过程会逐步收敛，并最终稳定下来。这表明，算法对于示例道路网络的控制起到了预期效果。

如果设定旅游需求预计达到 $5 \%$ ，则意味着可达到59029.94人次。 $5 \%$ 的增长可以被视为一年或两年一次的城市交通增长，这样就可以获得一些在收费、补贴金额的年变化上的启示。下面给出预计需求的比较结果，具体如表2实验数据所示。

![](images/6a011d8f6cdac66840b95c234a09da28de1164d349298c70f910c4ccf00e9d77.jpg)  
图5前三个桥连续迭代计算结果

表2预计需求的比较结果  

<html><body><table><tr><td rowspan="2">道路</td><td rowspan="2">方向 交通量</td><td rowspan="2"></td><td colspan="4">现有道路网络与需求</td><td colspan="4">现有的道路网络及需求预测</td></tr><tr><td>现有交通量</td><td>通行费-补</td><td>交通量容量占</td><td>收费/补</td><td>现有交通量</td><td>通行费-补</td><td>交通量容量占</td><td>收费/补</td></tr><tr><td rowspan="2">ID</td><td>ID</td><td>容量</td><td>容量</td><td>贴</td><td>比/%</td><td>贴/元</td><td>容量</td><td>贴</td><td>比/%</td><td>贴/元</td></tr><tr><td>1-1</td><td>1800</td><td>828.93</td><td>1796.92</td><td>99.83</td><td>0.52</td><td>884.15</td><td>1897.14</td><td>105.4</td><td>1.65</td></tr><tr><td rowspan="2">1</td><td>1-2</td><td>1800</td><td>183.76</td><td>185</td><td>10.28</td><td>-0.21</td><td>171.15</td><td>198.69</td><td>11.04</td><td>-0.2</td></tr><tr><td>2-1</td><td>750</td><td>722.32</td><td>727.05</td><td>96.94</td><td>-0.26</td><td>693.08</td><td>753.73</td><td>100.5</td><td>-0.22</td></tr><tr><td rowspan="2">2</td><td>2-2</td><td>750</td><td>762.35</td><td>750.24</td><td>100.03</td><td>1.7</td><td>738.28</td><td>785.66</td><td>104.75</td><td>3.09</td></tr><tr><td>3-1</td><td>1800</td><td>600.48</td><td>348.27</td><td>19.35</td><td>-0.07</td><td>712.76</td><td>362.41</td><td>20.13</td><td>-0.06</td></tr><tr><td rowspan="2">3</td><td>3-2</td><td>1800</td><td>2759.71</td><td>1801.39</td><td>100.08</td><td>2.33</td><td>2894.1</td><td>1872.34</td><td>104.02</td><td>3.55</td></tr><tr><td>4-1</td><td>1800</td><td>1205.92</td><td>1800.78</td><td>100.04</td><td>1.9</td><td>1344.33</td><td>1870.29</td><td>103.91</td><td>3.08</td></tr><tr><td rowspan="2">4</td><td>4-2</td><td>1800</td><td>84.03</td><td>108.25</td><td>6.01</td><td>-0.09</td><td>52.04</td><td>115.48</td><td>6.42</td><td>-0.09</td></tr><tr><td>5-1</td><td>1750</td><td>1641.31</td><td>1749.8</td><td>99.99</td><td>2.51</td><td>1583.63</td><td>1817.77</td><td>103.87</td><td>3.95</td></tr><tr><td rowspan="2">5</td><td>5-2</td><td>1750</td><td>469.82</td><td>403.75</td><td>23.07</td><td>-0.12</td><td>407.18</td><td>421.54</td><td>24.09</td><td>-0.11</td></tr><tr><td>6-1</td><td>1800</td><td>2446.11</td><td>1802.87</td><td>100.16</td><td>3.32</td><td>2656.02</td><td>1832.61</td><td>101.81</td><td>4.47</td></tr><tr><td rowspan="2">6</td><td>6-2</td><td>1750</td><td>785.81</td><td>592.48</td><td>33.86</td><td>-0.06</td><td>937.85</td><td>586.84</td><td>33.53</td><td>-0.06</td></tr><tr><td>7-1</td><td>1800</td><td>2313.34</td><td>1796.73</td><td>99.82</td><td>3.53</td><td>2449.24</td><td>1849.18</td><td>102.73</td><td>4.69</td></tr><tr><td rowspan="2">7</td><td>7-2</td><td>1800</td><td>656.64</td><td>389.2</td><td>21.62</td><td>-0.04</td><td>636.55</td><td>408.02</td><td>22.67</td><td>-0.04</td></tr><tr><td>8-1</td><td>1750</td><td>2035.5</td><td>1751.26</td><td>100.07</td><td>3.19</td><td>2104.15</td><td>1784.64</td><td>101.98</td><td>4.71</td></tr><tr><td rowspan="2">8</td><td>8-2</td><td>1800</td><td>783</td><td>752.7</td><td>41.82</td><td>-0.06</td><td>826.34</td><td>773.17</td><td>42.95</td><td>-0.06</td></tr><tr><td>9-1</td><td>1800</td><td>1683.56</td><td>1795.59</td><td>99.76</td><td>3.38</td><td>1610.9</td><td>1841.02</td><td>102.28</td><td>4.5</td></tr><tr><td rowspan="2">9</td><td>9-2</td><td>1800</td><td>903.52</td><td>824.2</td><td>45.79</td><td>-0.12</td><td>754.71</td><td>888.55</td><td>49.36</td><td>-0.12</td></tr><tr><td>10-1</td><td>1800</td><td>1547.86</td><td>1092.88</td><td>60.72</td><td>-0.08</td><td>1678.71</td><td>1110.07</td><td>61.67</td><td>-0.08</td></tr><tr><td rowspan="2">10</td><td>10-2</td><td>1800</td><td>3261.11</td><td>1802.74</td><td>100.15</td><td>4.13</td><td>3444.08</td><td>1876.04</td><td>104.22</td><td>5.02</td></tr><tr><td>11-1</td><td>1800</td><td>189.06</td><td>629.38</td><td>34.97</td><td>-0.16</td><td>228.85</td><td>728</td><td>40.44</td><td>-0.15</td></tr><tr><td>11</td><td>11-2</td><td>1800</td><td>289.45</td><td>1505.82</td><td>83.66</td><td>-0.16</td><td>306.38</td><td>1835.87</td><td>101.99</td><td>-0.16</td></tr><tr><td></td><td>Sum</td><td></td><td>26153.6</td><td>24407.3</td><td></td><td></td><td>27114.5</td><td>25609.1</td><td></td><td></td></tr><tr><td></td><td>Min</td><td></td><td></td><td></td><td></td><td>-0.26</td><td></td><td></td><td></td><td>-0.22</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>4.13</td><td></td><td></td><td></td><td>5.02</td></tr><tr><td></td><td>Max</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

如表2所示，通过收费/补贴公路的总交通流量从24407.3增加到25609.1，相当于 $4 . 9 \%$ 的增长。补贴和通行费的数额也出现了适度的变化，这是对最终结果稳定的一种支持。

选取图3中，桥梁1、5、10、11四个路段进行beta值收敛性验证，其中，路段5位于市中心，其交通处于饱和状态，桥梁1、10、11路段处于郊区，交通处于非饱和状态，beta 值收敛实验结果见图6所示。

![](images/543836451f543a9207108d2bcc7a7b1d525cae6a28c6b687a18473c0d0815527.jpg)  
图6beta 值收敛性验证

根据图6可知，选取的桥梁1、5、10、11四个路段均随着迭代过程收敛，且桥梁1、10、11三个路段的beta值收敛到0值附近，而桥梁5的beta值收敛到非0值。这与前面表述相一致。

# 4 结束语

本文提出一种基于延迟函数的次梯度启发式道路交通补偿策略，是基于Beckmann最小化目标函数实现，然后利用库恩-希尔斯条件和拉格朗日乘子建立模型的条件约束，并基于启发式算法建立道路交通的定价补偿策略，利用边际成本建立延迟函数分析模型，然后基于次梯度法进行模型的优化。实验结果表明，所提算法可有效实现对交通量和旅行时间的优化，通过收费/补贴公路的总交通流量从24407.3增加到25609.1，增长$4 . 9 \%$ ，提高了通行率，并且对beta值的收敛性进行了理论和实验分析。下一步，主要是对算法的实际应用进行研究。

# 参考文献：

[1]杨帆，杨琦，张珺，等．公共交通定价与最优政府补偿模型[J].交通 运输工程学报,2010,10(2):110-115.   
[2]Castro L, Stanojevic R,Gorinsky S. Using Tuangou to Reduce IP Transit Costs[J].IEEE//ACMTrans onNetworking,2014,22(5):1415-1428.   
[3]Andreas R,Magnus F, Konrad Z,et al.Freight transportation planning considering carbon emissions and in-transit holding costs:a capacitated multi-commodity network flow model[J].EURO Journal on Transportation and Logistics,2016,5 (2): 123-160.   
[4]Michael G,Ahmed E G. Driving transit retention to renaissance: trends in Montreal commute public transport mode share and factors by age group and birth cohort[J].Public Transport,2013,5(3): 219-241.   
[5]Michael G,Ahmed E G. Transit to eternal youth: lifecycle and generational trends in Greater Montreal public transport mode share [J]. Transportation, 2014, 41 (1): 1-19.   
[6]MahyarA,Rezaeestakhruie H,Poorzahedy H.Multi-objective cordon price design to control long run adverse traffic efects in large urban areas [J]. NETNOMICS: Economic Research and Electronic Networking, 2015,16 (1): 1-12.   
[7]Alessandro V, Giuseppe G,Daniele R.A smartphone based DSS platform for assessing transit service attributes [J].Public Transport,2016,8(2): 315- 340.   
[8]Bagherian M,Mesbah M,Ferreira L.Using delay functions to evaluate transit priority at signals [J]. Public Transport,2015,7(1): 61-75.   
[9]Qin Feifei, Zhang Xiaoning,Eoin P.The welfare effects of nationalization in a mixed duopoly public transport market [J]. Operational Research,2017, 17 (2): 593-618.   
[10] Eric JG.Coordinated pricing for cars and transit in cities with hypercongestion [J]. Economics of Transportation,2015,4(1): 64-81.   
[11] Leonardo JB,Sergio R J. Integrating congestion pricing,transit subsidies and mode choice [J]. Transportation Research Part A: Policy and Practice, 2012,46 (6): 890-900.   
[12] Zhao Xueyu, Yang Jiaqi. Research on the bi-level programming model for ticket fare pricing of urban rail transit based on particle swarm optimization algorithm[J].Procedia: Social and Behavioral Sciences,2013,96(6): 633- 642.   
[13] Kaushik D,Massimo F.Estimating welfare changes from efficient pricing in public bus transit in India [J].Transport Policy,2011,18 (1): 23-31.   
[14] Bagloee S A,Heshmati M,Tavana M,et al.A logit-based model for measuring the effects of transportation infrastructure on land value [J]. Transp Plan Tech,2017,40(2):143-166.   
[15] Xiao F,Zhang H. Pareto-improving toll and subsidy scheme on transportationnetworks[J]. European Journal ofTransportand Infrastructure Research,2014,14(1): 46-65.