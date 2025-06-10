# 动态视角下的城市道路交通网络失效评价模型“

袁鹏程1，林徐勋²

(1．上海理工大学 管理学院，上海 200093;2．常州大学 商学院，江苏 常州 213164)

摘要：利用可靠性相关理论，在对交通网络状态变化规律分析的基础上，给出了了城市道路交通单元及交通网络的‘失效—非失效’态的表达方法；分析了路段单元及交通网络的状态从观察起始点 $t _ { 0 }$ 到首次演变到‘失效态’的时间分布规律，并以此为基础推导了城市道路单元及交通网络的失效概率、平均失效时长、失效率以及条件失效时长等失效评价模型，给出了模型标定的方法。以国内某城市核心城区5条道路单元组成的路网为实例，对首次失效时间进行了分布拟合及检验，对模型进行了标定，并将模型计算结果与实际观察结果进行了对比。结果表明，利用对数正态分布来拟合首次失效时间较为理想，而且模型的计算结果与实际观察结果也非常接近，表明模型具有良好的实用性。

关键词：道路单元；交通网络；失效态；失效概率中图分类号：TP393 doi: 10.3969/j.issn.1001-3695.2017.08.0718

# Urban traffic network failure model under dynamic perspective

Yuan Pengchengl†,Lin Xuxun² (BusinussShool,Universityofnghaiforcience&echnologyhnghaio3,hina;usinessShool,Cgzhou University,Changzhou Jiangsu 213164, China)

Abstract:Basedonthereliabilitytheory,theexpressionofthe'failure-nonfailure'stateoftheurbanroad traffcunitadthe traficnetworkis givenafter thechangelawoftheir states isanalyzed;thetimedistributionofthelinkunitandthetraffic network is analyzed from the observed starting point $t _ { 0 }$ to the "first failure state".Based on these, the failure probability,average failuretime,filurerateandconditionallengthoffiluretimeoftheurbanroadunitandtrafficnetworkarededuced,themethod of modelcalibration isalso given inthis paper.Aroad trafic networkthatcomposedoffiveroadunits inacore cityofChina is takenbyanexample,thefirstfailuretimeoftheroadunitsandthe trafic networkarefittdandchecked,the modelcalculation results are alsocompared with the actual observationresults.Theresultsshow thatitis beter touse logarithmic normal distributiontofitthefirstfailure time,andthecalculationresultsofthe modelareveryclosetotheactualobservationresults, which shows that the model has good practicability.

Key Words: road unit; trafc network; failure state; failure probability

# 0 引言

随着城市交通的不断发展，城市交通网络规模越来越大。这种迅速增长的交通网络导致对路网准确而又实时的描述变得越来越困难。当面对这种复杂的道路状况和时变性更快的交通状况时，需要一种有效的工具来描述这种复杂性和随机性，城市交通系统可靠性研究便在这个背景下应运而生[]。‘失效’的概念来源于可靠性理论。可靠性理论中将一个使用中的元件在一个特定时间段内不失效（正常工作）的概率定义为这个元件的可靠度[2;3]。但是，交通系统可靠性的研究从刚开始并没有引用这个概念，而是使用了更为一般的可靠度概念一一‘在规定条件下完成某种功能的概率'，这也使得交通系统可靠度的研究从刚开始就带有静态的基本特征。

到目前为止，对交通网络静态可靠性评价的研究已经积累了很多，研究人员从各个角度出发提出了能够反映交通网络静态特征的评价模型与方法。这其中主要包括网络的连通可靠度评价[4-6]，网络的行程时间可靠度评价[7\~II]，网络的通行能力可靠度[12-14]评价以及其他可靠度如行为可靠度[15\~17]及潜在可靠度[18]等方面的评价。这些方面代表性的工作主要包括Mine 和Kawai率先提出的交通网络连通可靠度的概念[19],Chen等人进一步扩展了这个评价模型，并提出的通行能力可靠度的概念[20].以及Asakura等提出的行程时间可靠度的概念。交通网络可靠度评价指标建立起来后，接下来的研究便是如何利用这些评价指标对交通网络可靠度进行评价。这方面的研究主要沿着解析[21]和仿真[13·22]两种方法展开。利用解析方法对交通网络可靠度进行推算的学者将交通网络随机性产生的原因归咎于交通供给和需求的随机性。解析研究首先对交通网络系统的供需的概率分布进行标定，然后根据网络上路段之间的相互连接关系、流量与阻抗关系及交通网络的均衡特征，推算出总的网络行程时间分布，进而计算出交通网络的可靠度。而模拟的方法则主要是利用交通流模拟器模型产生网络流量，然后利用蒙特卡罗模拟方法对网络可靠度评价参数的随机概率分布进行模拟标定，进而计算出交通网络的可靠度。

值得注意的是近年来，随着复杂性科学的研究进展，利用复杂网络的思想对城市交通网络可靠性演化（绝大多数文献中称为‘级联失效'）进行模拟仿真的研究也越来越多。如吴建军等结合交通流分配理论较早建立了反映城市交通系统的级联失效模型[23\~26]。Sun等人[25]在此基础上提出来抵御级交通网络级联失效的鲁棒分配模型。王正武等人[27]基于双层交通网络的思想，提出了一个交通网络的级联失效模型，并将之用来评价交通网络节点重要度，还构建了城市道路交通网络级联失效的灾害蔓延动力学模型[28]。王芳等人[29]利用流量-容量模型对交通网络上的级联失效过程进行了模拟分析。陈小兰[30]通过模拟仿真，找到了对交通网络级联失效破坏程度最小和最大时各因素的组合方案。尹洪英等人[31]也通过仿真分析了不同网络拓扑结构、不同路段移除方式及不同耦合强度对于交通网络级联失效的影响规律。徐小洋[32]则利用复杂网络理论思想，将城市道路交通网络表示成具有特殊统计特征的复杂网络，借鉴复杂网络上传染病传播的 SIS（susceptible-infected-susceptible）机制，提出了基于SIS 的交通拥堵传播仿真模型。在此基础上，以北京市道路交通网络为例，利用所建立的仿真模型，对路网进行随机/蓄意攻击（随机或者故意断开某些节点的连接)，对比攻击前后网络主要参数的变化情况，从而对节点的重要性作出评价。复杂网络的思想对于解决大规模（至少几万以上节点）具有显著参数统计特征的交通网络具有一定意义，但是当网络规模较小，网络拓扑结构非常清晰时（例如当只有几十条道路组成的小规模路网）这种思想和研究方法是不适用的，因为网络的参数已经不再具有统计意义上的相关特征。而在实际交通工程的实践中，通常本文需要对局部的有限规模的交通网络的失效规律和特征进行分析和应用。不仅如此，虽然‘级联失效’本身是一个动态的概念，但是当前的研究更关注于由于某个节点或边‘失效’后由此引发的其他节点或边的失效蔓延状态，因此它还不是一个真正意义上的‘动态'，还不能够刻画具体时刻交通网络所处的失效状态。因此，不同于徐小洋等利用复杂网络思想以及仿真分析的研究方法，本文从一般交通网络出发，利用随机过程相关理论，研究交通网络失效的动态特征，推导交通网络道路单元失效的时变规律，建立城市交通网络单元的失效解析模型。

# 1 模型构建

# 1.1交通网络的失效状态

路段是组成交通网络的基本单元，在交通网络系统中，每一条道路都发挥着不同的功能，组成网络系统的所有路段之间共同作用、相互协调，保障了交通流量的集散，发挥了交通网络系统的‘集疏运’功能。当交通网络系统中的部分路段单元由于内外作用而不能发挥其应有的功能时，就可以认为路段单元失效了。

考虑一个由 $n$ 条路段单元组成的交通网络系统，假设每条路段单元交通流状态的集合为 $M$ 。在 $\mathbf { \Phi } _ { t }$ 时刻，如果路段$i ( i = 1 , 2 , \cdots n )$ 的状态为 $J \left( J \in M \right)$ 时，便认为此路段单元丧失了应有的功能，则定义 $\mathbf { \Phi } _ { t }$ 时刻此路段单元的状态为失效状态。记 $\mathbf { \Phi } _ { t }$ 时刻路段单元 $\mathbf { \chi } _ { i }$ 的状态为 $S _ { i } \left( t \right)$ ，则有

$$
S _ { i } \left( t \right) = \left\{ \begin{array} { l l } { 1 } & { t ^ { \mathrm { H } } \Sigma \backslash | i | \Sigma \backslash \ \forall \Sigma \backslash \Sigma \cup K ; K \in M \quad K \neq J } \\ { 0 } & { t ^ { \mathrm { H } } \Sigma \backslash | i | \Sigma \backslash \ \forall \Sigma \backslash \Sigma \cup J ; J \in M } \end{array} \right.
$$

显然 $S _ { i } \left( t \right)$ 是一个随机变量，当 $S _ { i } \left( t \right) = 1$ ，表示路段 $i$ 处于非失效状态；否则，当 $S _ { i } \left( t \right) = 0$ 时，表示路段 $i$ 处于失效状态。同时， $\mathbf { \Phi } _ { t }$ 时刻交通网络的状态可记为$S ( t ) = \bigl \{ S _ { 1 } ( t ) , S _ { 2 } ( t ) , \cdots , S _ { i } ( t ) , \cdots , S _ { n } ( t ) \bigr \}$ ， $S ( t )$ 称为 $\mathbf { \Phi } _ { t }$ 时刻交通网络的一个状态变量，它表明 $\mathbf { \chi } _ { t }$ 时刻网络中哪条道路正常运行，哪条道路已经处于失效状态了。

以上提出的‘路段单元交通流状态’的概念，是对道路交通流运行特征的进行描述的一个基本概念，也是进行道路失效定义的基础概念。在交通工程中常常将交通流的运行状态分为‘畅通、拥挤、堵塞’等。实际上，交通流的状态是一个连续的概念，因此对交通状态的划分方法及状态种类的数量也不是唯一的。无论哪种对交通状态的划分方法都具有其合理性，本文不纠结于讨论各种交通状态的划分方法的优劣比较，仅以交通单元系统的多状态性特征为基础，来说明对交通单元失效状态的定义。同时本文也不纠结于何种状态可以称为单元的‘失效’状态，‘失效’状态根据管理者对系统本身的预期来定义，例如，在路段单元处于空闲、畅通、繁忙、拥挤、堵塞和阻断的六种状态中，可以认为只有当路段处于‘阻断’状态时才认为此时路段失效，但也可以认为当路段在‘拥挤’及其更坏的状态时，如将‘拥挤、堵塞和阻断’状态统称为‘失效’状态。对单元状态失效的具体定义完全取决于实际中的需要以及管理者的预期。

# 1.2路段单元段的失效函数

现实中，交通网络系统各单元的交通状态总是不断变化的，例如路段单元的状态总是随着时间在‘畅通一拥挤一堵塞’三个状态之间变化，如果将堵塞作为路段单元的'失效态'的话，路段单元实际上是在‘非失效’与‘失效’两种状态之间变化。记初始时刻 $t _ { 0 }$ 的路段单元 $i$ 的状态为 $S _ { i } \left( t _ { 0 } \right)$ ，经过一段时间$T$ 后路段单元 $i$ 的状态首次变为‘失效态'，称时间 $T$ 为路段单元 $i$ 的首次失效时长。显然，路段单元 $i$ 的首次失效时长 $T$ 是一个连续随机变量。令 $T$ 的概率密度函数为 $f _ { i } \left( t \right)$ ，则 $T$ 的分布函数为 $F _ { i } \left( t \right)$ 。

$$
F _ { i } \left( t \right) = P \left( 0 \leq T \leq t \right) = \int _ { t _ { 0 } } ^ { t _ { 0 } + t } f _ { i } \left( u \right) d u , t > 0
$$

fi(t）表示的是路段单元i在to+t时刻处于‘非失效'态的概率， $F _ { i } \left( t \right)$ 表示路段单元 $i$ 在 $\left[ t _ { 0 } , t _ { 0 } + t \right]$ 时间段内会处于‘失效态’的概率，成为路段单元 $i$ 的失效函数。若定义（204号 $R _ { i } \left( t \right) = 1 - F _ { i } \left( t \right)$ ，则 $R _ { i } \left( t \right) = P \left( T > t \right)$ ，表示路段单元 $\mathbf { \chi } _ { i }$ 在[t,?to+t]时间段内都处于‘非失效态’的概率。根据路段单元的失效时间的概率密度函数可以计算得到路段单元 $i$ 的失效时间的期望值E(T)。

$$
E { \big ( } T _ { i } { \big ) } = \int _ { t _ { 0 } } ^ { \infty } t f _ { i } { \big ( } t { \big ) } d t = \int _ { t _ { 0 } } ^ { \infty } t F _ { i } ^ { ^ { \prime } } ( t ) d t
$$

若路段单元 $i$ 在 $t _ { 0 } + t$ 时刻还处于‘非失效态’，则在(to+t,to+t+△t]内到达‘失效态’的概率可计算为：

$$
P \big ( t < T _ { i } \le t + \Delta t \vert T _ { i } > t _ { 0 } + t \big ) =
$$

$$
\frac { P \big ( t < T _ { i } \le t + \Delta t \big ) } { P \big ( T _ { i } > t \big ) } = \frac { F _ { i } \big ( t + \Delta t \big ) - F _ { i } \big ( t \big ) } { R _ { i } \big ( t \big ) }
$$

上式两边同除以 $\Delta t$ ，并令 $\Delta t \to 0$ ，取极限，则可得

$$
z _ { i } ( t ) = \operatorname* { l i m } _ { \Delta t  0 } \frac { F _ { i } ( t + \Delta t ) - F _ { i } ( t ) } { \Delta t } \cdot \frac { 1 } { R _ { i } ( t ) } = \frac { f _ { i } ( t ) } { R _ { i } ( t ) } \cdot \
$$

称 $z _ { i } \left( t \right)$ 为路段单元 $i$ 的失效率函数。当路段单元 $\mathbf { \chi } _ { i }$ 在（204号 $t _ { 0 } + t$ 时刻处于‘非失效’态，在经过 $x$ 时间后该路段单元仍未到达过‘失效态’，且仍保持‘非失效’态的概率记为$R _ { i } \big ( x | t _ { 0 } + t \big )$ ，则有

$$
R _ { i } \left( x | t _ { 0 } + t \right) = P \left( T _ { i } > x + t | T _ { i } > t \right) = \frac { P \left( T _ { i } > x + t \right) } { P \left( T _ { i } > t \right) } = \frac { R _ { i } \left( x + t \right) } { R _ { i } \left( t \right) }
$$

称 $R _ { i } \big ( x | t _ { 0 } + t \big )$ 为 $t _ { 0 } + t$ 时刻路段单元 $\mathbf { \chi } _ { i }$ 的条件可靠度函数。根据路段单元的条件可靠度函数容易计算出路段单元 $\mathbf { \chi } _ { i }$ 的‘平均剩余失效时间'（路段单元 $i$ 在）的期望值，也称为路段单元$i$ 的平均剩余失效时间，记为 $E \big ( T _ { i } ^ { r } \big )$ 。

$$
E { \left( T _ { i } ^ { r } \right) } = \int _ { t _ { 0 } } ^ { \infty } { x f _ { i } \left( x | t _ { 0 } + t \right) d x } = - \int _ { t _ { 0 } } ^ { \infty } { x R _ { i } ^ { { ' } } \big ( x | t _ { 0 } + t \big ) d x }
$$

# 1.3交通网络失效函数

考虑一个由 $\mathbf { \Omega } _ { n }$ 条路段单元组成的交通网络 $N$ ，假设每条路段单元 $i$ 都有‘失效态’与‘非失效态’两种状态,则根据排列组合，此交通网络共有 $2 ^ { n }$ 种状态。在这 $2 ^ { n }$ 种状态中，若其中 $m ( 1 \leq m < 2 ^ { n } )$ 种状态发生时都可认为此交通网络丧失了道路‘疏散’功能，即‘失效’了。记初始时刻 $t _ { 0 }$ 的交通网络 $N$ 的状态为 $S ( t _ { 0 } ) = \left\{ S _ { 1 } ( t _ { 0 } ) , S _ { 2 } ( t _ { 0 } ) , \cdots S _ { i } ( t _ { 0 } ) , \cdots , S _ { n } ( t _ { 0 } ) \right\}$ ,经过一段时间$T$ 后交通网络 $N$ 的状态首次变为‘失效态'，称时间 $T$ 为交通网络 $N$ 的首次失效时长，同理可得交通网络 $N$ 的失效函数$F \left( t \right)$ 。

$$
F \bigl ( t \bigr ) = P \bigl ( 0 \leq T \leq t \bigr ) = \int _ { t _ { 0 } } ^ { t _ { 0 } + t } f \bigl ( u \bigr ) d u , t > 0
$$

f(t)表示交通网络N 在 to+t时刻处于‘非失效’态的概率， $F \left( t \right)$ 表示交通网络 $N$ 在 $\left[ t _ { 0 } , t _ { 0 } + t \right]$ 时间段内会处于‘失效态’的概率，称为交通网络 $\mathbf { \Omega } _ { N }$ 的失效函数。若定义$R \bigl ( t \bigr ) = 1 - F \bigl ( t \bigr )$ ，则 $R { \big ( } t { \big ) } = P { \big ( } T > t { \big ) }$ ，表示交通网络 $N$ 在[t,t +t]时间段内都处于‘非失效态’的概率。同理，根据交通网络 $N$ 的失效时间的概率密度函数 $f \left( t \right)$ 可以计算得到交通网络 $N$ 的失效时间的期望值 $E \big ( T \big )$ 、失效率函数 $z ( t )$ 、条件失效函数及平均剩余失效时间 E(T)。

$$
E { \big ( } T { \big ) } = \int _ { t _ { 0 } } ^ { \infty } t f { \big ( } t { \big ) } d t = \int _ { t _ { 0 } } ^ { \infty } t F ^ { \prime } { \big ( } t { \big ) } d t
$$

$$
R { \big ( } x | t _ { 0 } + t { \big ) } = P { \big ( } T > x + t | T > t { \big ) } = { \frac { R { \big ( } x + t { \big ) } } { R { \big ( } t { \big ) } } }
$$

$$
z \big ( t \big ) = \operatorname* { l i m } _ { \Delta t  0 } \frac { F \big ( t + \Delta t \big ) - F \big ( t \big ) } { \Delta t } \cdot \frac { 1 } { R \big ( t \big ) } = \frac { f \big ( t \big ) } { R \big ( t \big ) }
$$

$$
E { \Big ( } T ^ { r } { \Big ) } = \int _ { t _ { 0 } } ^ { \infty } x f _ { i } { \big ( } x | t _ { 0 } + t { \big ) } d x = - \int _ { t _ { 0 } } ^ { \infty } x R _ { i } ^ { { \big ( } x | t _ { 0 } + t { \big ) } d x }
$$

$F ( t ) \setminus E ( T ) \setminus z ( t )$ 以及 $E ( T ^ { r } )$ 是表征交通网络从观测时刻（204号 $t _ { 0 }$ 直至首次到达‘失效态’的重要参数，在交通工程中，特别是在智能交通工程中，可以利用以往的交通流（交通状态）观测数据对路网即将进入‘失效态’进行预判；若当前时刻路网已经处于‘失效态’时，又可以利用以上模型对路网消散时长进行预判。从而为驾驶员的路径选择进行决策依据。

# 2 参数标定过程

以上交通网络失效评价模型涉及到的核心变量便是路段单元 $i$ 及交通网络 $N$ 的首次失效时间 $T$ 的概率分布，因此主要是对随机变量 $T$ 的概率分布函数进行参数估计及分布假设检验。这里主要应用 $\chi ^ { 2 }$ 检验法对 $T$ 的分布进行检验。检验过程如下：

假设随机变量 $T$ 服从参数为 $\theta _ { 1 }$ $\theta _ { 2 } , \cdots \theta _ { r }$ 的分布函数$F \left( t , \theta _ { 1 } , \theta _ { 2 } , \cdots , \theta _ { r } \right)$ ， $\theta _ { \mathrm { { l } } } ,$ $\theta _ { 2 } , \cdots \theta _ { r }$ 为未知参数。 $T _ { \mathrm { r } } ,$ $T _ { 2 } , \cdots \cdot T _ { n }$ 为观测到的一个样本。

a)将随机变量 $T$ 的取值范围分成 $k$ 个连续且不相交的等 分小区间，记为A, $A _ { 2 } { , } { \cdots } A _ { k }$ ，如可取为 $\left( a _ { 0 } , a _ { 1 } \right] , \left( a _ { 1 } , a _ { 2 } \right] , \cdots , \left( a _ { k - 1 } , a _ { k } \right] \circ$ （20

b)把落入第 $\mathbf { \chi } _ { i }$ 个小区间的样本值的个数记作 $f _ { i }$ 称为组频数,则所有组频数之和 $\sum _ { i = 1 } ^ { k } f _ { i } = n$ 。

c)利用样本 $T _ { 1 } , \ T _ { 2 } , \cdots \cdot T _ { n }$ ，求得未知参数 $\theta _ { 1 } , ~ \theta _ { 2 } , \cdots \cdot \theta _ { r }$ 的极大似然估计值。θ $, \quad \hat { \theta } _ { 2 } , \cdots \cdot \hat { \theta } _ { r }$ 。

d)在分布函数 $F \left( t , \theta _ { 1 } , \theta _ { 2 } , \cdots , \theta _ { r } \right)$ 冲，用 $\hat { \theta } _ { \scriptscriptstyle 1 }$ $\mathbf { \Omega } _ { 1 } , \ \hat { \theta } _ { 2 } , \substack { \ldots \ldots \hat { \theta } _ { r } }$ 来代替$\theta _ { \scriptscriptstyle 1 }$ ， $\theta _ { 2 } , \cdots \theta _ { r }$ ，即得到一个不含未知参数的分布函数$F ( t , \hat { \theta } _ { 1 } , \hat { \theta } _ { 2 } , \cdots , \hat { \theta } _ { r } )$ 。

e)利用分布函数 $F ( t , \hat { \theta } _ { 1 } , \hat { \theta } _ { 2 } , \cdots , \hat { \theta } _ { r } )$ 求 $\hat { p } _ { i } \left( i = 1 , 2 , \cdots , k \right)$ 。  
f)计算 $\chi ^ { 2 }$ 统计量的值 $\chi ^ { 2 } = \sum _ { i = 1 } ^ { k } f _ { i } ^ { 2 } / n \hat { p } _ { i } - n$ 。

g)给定显著性水平 $\mathbf { { a } = 0 . 0 5 }$ ，若 $\begin{array} { r } { \chi ^ { 2 } < \chi _ { \alpha } ^ { 2 } \left( k - r - 1 \right) } \end{array}$ ，则可以得到随机变量 $T$ 的概率分布函数 $F ( t , \hat { \theta } _ { 1 } , \hat { \theta } _ { 2 } , \cdots , \hat { \theta } _ { r } )$ ；否则令分布函数 $F \left( t , \theta _ { 1 } , \theta _ { 2 } , \cdots , \theta _ { r } \right)$ 为其他形式，返回 $^ { b ) }$ 直至检验合格，得到所需要的分布函数。

# 3 算例及模型检验

# 3.1数据来源

采用国内某城市核心城区5条单向道路单元组成的路网（图1)，数据采用埋设在道路上的专用线圈检测器采集获得，线圈检测器通过检测感应到的车辆来获得车速、流量及时间占有率等参数，统计间隔为 $3 ~ \mathrm { m i n }$ ，也就是说在道路的某一个断面，线圈采集设备每三分钟便将此时间段内经过此断面的交通流参数（包括车流量、平均车辆速度、平均时间占有率、平均车头时距）进行统计并上传到数据库，共获取此路网连续两个月（60d）的交通流数据。5条道路单元段的交通流数据描述性统计如表1所示。

![](images/f851dfafd9d1635c9debec5e6af1ed8259c865b2866f3a6553f5539672e8c0ab.jpg)  
图1 路网示意图

# 3.2道路单元及交通网络的‘失效态

Kerner[33]提出的三相交通流状态受到理论界的广泛认同，后续的研究则在此基础上进一步将三相交通流状态扩展到四相（自由流、谐动流、同步流、阻塞流）和五相（自由流、畅行流、通行能力状态、同步流状态及阻塞状态）状态。考虑到本文数据类型的特征，在这里采用蔡燕飞等利用流量-速度-时间占有率数据提出的五相交通状态来对交通流状态进行识别和划分[34]，具体过程参见文献[35，37]。这里定义当路段单元处于同步流状态及阻塞流状态时，路段单元为‘失效态'，则可获得如图2所示的各路段‘失效态’与‘非失效态’。

表1路段交通流数据描述统计  

<html><body><table><tr><td>参数类型</td><td>最大值</td><td>最小值</td><td>均值</td><td>方差</td></tr><tr><td>流量(辆)</td><td>86</td><td>1</td><td>36.83</td><td>21.59</td></tr><tr><td>平均速度(km/h)</td><td>75</td><td>13</td><td>48.46</td><td>6.00</td></tr><tr><td>平均时间占有率(%)</td><td>72.43</td><td>0.09</td><td>7.29</td><td>5.69</td></tr><tr><td>流量(辆)</td><td>77</td><td>1</td><td>30.59</td><td>16.80</td></tr><tr><td>平均速度(km/h)</td><td>67</td><td>11</td><td>34.29</td><td>5.72</td></tr><tr><td>平均时间占有率(%)</td><td>47.8</td><td>0.11</td><td>7.12</td><td>5.09</td></tr><tr><td>流量(辆)</td><td>122</td><td>1</td><td>38.49</td><td>20.03</td></tr><tr><td>平均速度(km/h)</td><td>61</td><td>11</td><td>38.37</td><td>5.78</td></tr><tr><td>平均时间占有率(%)</td><td>37.86</td><td>0.07</td><td>5.12</td><td>4.03</td></tr><tr><td>流量(辆)</td><td>86</td><td>1</td><td>25.08</td><td>19.84</td></tr><tr><td>平均速度(km/h)</td><td>84</td><td>10</td><td>38.76</td><td>9.31</td></tr><tr><td>平均时间占有率(%)</td><td>43.29</td><td>0.06</td><td>3.09</td><td>2.94</td></tr><tr><td>流量(辆)</td><td>54</td><td>1</td><td>21.85</td><td>11.53</td></tr><tr><td>平均速度(km/h)</td><td>69</td><td>3</td><td>40.23</td><td>9.06</td></tr><tr><td>平均时间占有率(%)</td><td>100</td><td>0.13</td><td>9.50</td><td>8.09</td></tr></table></body></html>

根据失效的基本定义，若交通网络不能发挥原有的‘疏散"功能，则可认为其发生了‘失效'。基于此，可以看出当图1所示的交通网络出现如表2所示（0表示‘失效态'，1表示‘非失效态'）的路段单元状态组合时，交通网络不再是联通的，因此便可认为此网络发生了失效。

![](images/fbd7933cebef77aaed63ddce5269471d5da48e374639268d401c9de0a7f60686.jpg)  
图2各路段单元的‘失效态’与‘非失效态

表2交通网络的失效态  

<html><body><table><tr><td></td><td>Link1</td><td>Link2</td><td>Link3</td><td>Link4</td><td>Link5</td><td>交通网络</td></tr><tr><td>状态1</td><td>0</td><td>0</td><td></td><td></td><td></td><td>0</td></tr><tr><td>状态2</td><td>-</td><td></td><td>---</td><td>0</td><td>0</td><td>0</td></tr><tr><td>状态3</td><td>0</td><td>0</td><td></td><td>0</td><td>0</td><td></td></tr><tr><td>状态4</td><td></td><td></td><td>0</td><td></td><td></td><td>0</td></tr><tr><td>状态5</td><td>0</td><td>0</td><td>0</td><td></td><td></td><td>0</td></tr><tr><td>状态6</td><td></td><td></td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>状态7</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

根据以上路段单元的失效态以及对交通网络失效态的定义便可得到交通网络的‘失效态随时间变化过程，如图3所示

# 3.3参数标定

以0：00和为起始观察时刻 $t _ { 0 }$ 对各路段单元段及交通网络的首次失效时长 $T$ 进行观察（注意，若路段单元或者网络在某一天未到达过失效态，则记 $T = 1 4 4 0$ ，也就是一天的分钟数)，观察结果如图4所示。

![](images/aa8f33e03f5df2f1728d3be176280485b342d961060a591a47b42b215e59fd2c.jpg)  
图3交通网络的‘失效态’与‘非失效态'

![](images/517b1f9a334240bdef02eb1408c9455a5480524e2e744a1b49ea59e7d2622a6b.jpg)  
图4路段单元及交通网络的首次失效时长

利用第3节给出的模型参数标定方法，在原假设 $H _ { 0 }$ ：路段单元及交通网络首次失效时长均服从参数为 $\mu$ ，方差为 $\sigma ^ { 2 }$ 的对数正态分布下，对路段单元及交通网络首次失效时长进行概率分布函数的拟合检验，结果如表3所示。

表3路段单元及交通网络的首次失效时长概率分布拟合  

<html><body><table><tr><td></td><td>Link1</td><td>Link2</td><td>Link3</td><td>Link4</td><td>Link5</td><td>交通网络</td></tr><tr><td>从</td><td>6.11</td><td>5.90</td><td>6.07</td><td>-----</td><td>5.98</td><td>6.30</td></tr><tr><td></td><td>0.015</td><td>0.55</td><td>0.027</td><td>-----</td><td>0.01</td><td>0.14</td></tr><tr><td>x²值</td><td>4.04</td><td>6.0</td><td>5.32</td><td>-----</td><td>3.60</td><td>1.52</td></tr><tr><td>p</td><td>0.13</td><td>0.54</td><td>0.07</td><td>-----</td><td>0.16</td><td>0.67</td></tr><tr><td>接受Ho？</td><td>是</td><td>是</td><td>是</td><td>-----</td><td>是</td><td>是</td></tr></table></body></html>

注意，由于观察结果显示路段4的失效时长只存在2天变化，故不对路段4进行失效时长的分布拟合。

从表3可以看出，除路段4因其基本未发生过时效而不进行首次失效时长的分布拟合外，其余路段单元以及交通网络的失效时长都用对数正态分布进行了拟合，并且从拟合结果科研看出，路段2和交通网络的拟合结果都非常好（ $p$ 值分别达到了 $54 \%$ ， $63 \%$ )，路段1、5的拟合效果稍差，但是可以看出 $p$ （204值均大于0.05，也就是说在 $5 \%$ 的显著性水平下，仍然可以接受路段1、5的失效时长服从对数正态分布的假设。当失效时间 $T$ 服从参数为 $\hat { \mu }$ ， $\hat { \tau }$ 的对数正态分布时，可写出失效时间的概率密度函数为

$$
f \left( t \right) = \left\{ \begin{array} { c c } { \displaystyle { \frac { 1 } { \sqrt { 2 \pi \hat { \tau } } } e ^ { - \left( \ln { t } - \hat { \mu } / 2 \hat { \tau } ^ { 2 } \right) } } } & { t > 0 } \\ { 0 } & { \mathrm { \gtrapprox \hat { \mu } \hat { t } \hat { \ t } \hat { \ t } } } \end{array} \right.
$$

根据分布函数与概率密度函数之间的关系可得

$$
F \bigl ( t \bigr ) = P \bigl ( 0 \leq T \leq t \bigr ) = \int _ { t _ { 0 } } ^ { t _ { 0 } + t } f \bigl ( u \bigr ) d u = 1 - \Phi \mathopen { } \mathclose \bgroup \left( \frac { \hat { \mu } - \ln t } { \hat { \tau } } \aftergroup \egroup \right) , t > 0
$$

再根据式（9）～（11）可得

$$
E \big ( T \big ) = \int _ { t _ { 0 } } ^ { \infty } t f \big ( t \big ) d t = e ^ { \hat { \mu } + \hat { \tau } ^ { 2 } / 2 }
$$

$$
R { \big ( } x { \big | } t _ { 0 } + t { \big ) } = { \frac { R { \big ( } x + t { \big ) } } { R { \big ( } t { \big ) } } } = { \frac { \Phi { \Bigg ( } { \frac { { \hat { \mu } } - \ln { \big ( } x + t { \big ) } } { { \hat { \tau } } } } { \Bigg ) } } { \Phi { \Bigg ( } { \frac { { \hat { \mu } } - \ln t } { { \hat { \tau } } } } { \Bigg ) } } }
$$

$$
z { \big ( } t { \big ) } = { \frac { f { \big ( } t { \big ) } } { R { \big ( } t { \big ) } } } = \left( \phi { \left( { \frac { { \hat { \mu } } - \ln t } { { \hat { \tau } } } } \right) } / \tau t \right) / \Phi { \left( { \frac { { \hat { \mu } } - \ln t } { { \hat { \tau } } } } \right) }
$$

# 3.4结果比对

表3给出了观察起始点 $t _ { \mathrm { 0 ? } } = 0 { : } 0 0$ 时各道路单元及交通网络首次失效时长的概率密度函数，若给定一个时长 $\mathbf { \chi } _ { t }$ ，便可根据式（14）--式（17）求得各路段单元及交通网络的在时间段[t,?to+t]内的失效（非失效）概率、失效时间的期望值、条件可靠度及平均剩余失效时间，同时也可以得到失效率函数。令 $t = 4 5 0 \ m m i n$ ，则依据模型所求得的各路段单元及交通网络的失效概率、失效时间的期望值 $E ( T )$ 、条件可靠度 $R \big ( x | \mathfrak { X } _ { 0 } + t \big )$ 等参数，各路段的及网络的失效概率随时间变化如图5所示。

![](images/bfbb06274f516d6280a5a69dd96fa1f5a5f7c14ce1c78d50f3916ce62b9cdfd2.jpg)  
图5各路段单元及交通网络的失效概率随时间变化曲线

为了对模型计算结果精准度进行检验，取各道路单元及交通网络的状态变化（‘失效一非失效'）数据，分别计算对应时间段内各道路单元及交通网络的失效频率、平均失效时长、条件可靠频率、平均剩余失效时长,计算过程具体为：失效频率 $. =$ 观察到的失效次数/观察次数；平均失效时长 $\underline { { \underline { { \mathbf { \Pi } } } } } = \underline { { \underline { { \mathbf { \Pi } } } } }$ 观察到的失效时长/观察次数条件可靠频率 $= t _ { 0 } + t$ 时刻观察到未失效，但在$\begin{array} { r } { \left[ \boldsymbol { t } _ { 0 } + \boldsymbol { t } , \boldsymbol { t } _ { 0 } + \boldsymbol { t } + \boldsymbol { x } \right] } \end{array}$ 时间段内观察到失效的次数/观察次数；平均剩余失效时长 $\scriptstyle : =$ 在 $\left[ { { t } _ { 0 } } + t , \ { { t } _ { 0 } } + t + x \right]$ 时间段内观察到失效态的失效时长/观察次数。对模型计算结果与观察结果进行比对，结果如表4所示。

从表4中可以看出，用模型估计得到的失效概率与观察得到的失效频率以及非常接近，说明模型具有较高的精确度以及良好的实用性。

表4结果比较（ $\mathbf { \xi } _ { t } = 4 5 0 \operatorname* { m i n } , x = 3 0 \operatorname* { m i n } \mathbf { \xi } )$ （204  

<html><body><table><tr><td></td><td colspan="2">Link1</td><td colspan="2">Link2</td><td colspan="2">Link3</td><td colspan="2">Link4</td><td colspan="2">Link5</td><td colspan="2">交通网络</td></tr><tr><td>失效概率/失效频率</td><td>0.48</td><td>0.50</td><td>0.64</td><td>0.6</td><td>0.92</td><td>0.90</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0.09</td><td>0.10</td></tr><tr><td>E(T)/平均失效时长</td><td>450.38</td><td>448.75</td><td>424.64</td><td>409.20</td><td>432.83</td><td>433.25</td><td>1448</td><td>1407.90</td><td>395.46</td><td>397.55</td><td>544.62</td><td>549.20</td></tr><tr><td>R(xto+t)/条件可靠频率</td><td>0.00002</td><td>0</td><td>0.87</td><td>0.8</td><td>0.0008</td><td>0</td><td>1</td><td>1</td><td>0</td><td></td><td>0.89</td><td>0.9</td></tr></table></body></html>

# 4 结束语

本文利用可靠性及概率统计相关理论，从动态视角提出了能够反映城市道路交通流时变特质的道路单元及交通网络失效评价模型。首先从道路单元路段出发，给出了道路单元路段的状态表示方法，然后根据路段单元状态与其功能之间的关系，将路段单元状态转换为路段单元的‘失效一非失效'二态表示。以此为基础，根据网络中路段之间的关系，给出了交通网络‘失效—非失效’的识别方法；分析了以观察点 $t _ { 0 }$ 为起始点时的道路单元及交通网络首次到达失效态的时间概率分布规律，给出了对假想分布的未知参数进行估计及对假想分布进行假设检验的方法。提出了以失效概率、失效期望时间 $E \big ( T \big )$ 、条件可靠度函数 $R _ { i } \left( x | \mathcal { I } _ { 0 } + t \right)$ 以及失效率为主要评价参数的交通网络失效评价模型。最后本文以一个实际路网为例，对模型进行了标定，并对模型的评价结果进行了验证。结果显示：a)无论对于道路单元路段还是交通网络，其失效时间的概率分布用对数正态分布来拟合都可以通过显著性水平 $\alpha = 0 . 0 5$ 的假设检验，这也表明用对数正态分布对首次失效时间进行拟合是一个较为可靠的选择；b)将标定好的模型评价结果与实际观察结果进行了比对，结果显示两者之间非常接近，这表明模型具有较高的精度。

笔者认为本文所提的失效评价模型给道路运行状况的评价提供了一个全新的视角，也可以为交通规划师、交通工程师进行决策提供理论依据。当前工程上对于一条道路运行状况的评价常用的指标大多是运行速度、拥堵时长等静态的确定性指标，连通可靠性/行程时间可靠性等作为一个静态的非确定性参数的应用具有一定的进步，但是它仍旧不能很好的刻画交通网络状态时变动态的特质。本文失效评价模型的提出可以反映出交通网络状态的时变特质，例如图5所示，可以看出随着时间变化交通网络失效概率的变化规律，在实践中可以根据这个规律，对道路交通流进行必要的管理，获得相关的数据后进一步评价管理措施的效果（例如采取某交通措施收，失效函数的倾斜程度变缓，那么可以认为此管制措施是有效的)。另外本文虽然给出的是失效评价模型，但是事实上利用同样的原理，本文可以还可以用来评价交通网络失效态的消散过程，这个评价指标实际上是非常有意义的。

尽管如此，本文的理论及实用性还有待进一步深入，例如，本文所给出的失效评价模型都是以一次失效为基础的，但事实上根据经验或者从图2、3可以看出，实际交通网络都是在‘失效态’与‘非失效态’之间不断变化的，因此如果能对模型进行进一步深入研究，提出能够刻画这种不断变化状态的交通网络失效评价模型将是非常有意义的。此外，本文由于受到数据采集条件方面的制约，只能采集到两三个月的连续交通流数据，相对来说样本还是比较小，例如在对首次失效时长进行分布拟合过程中，样本只有60个，这样有可能增加的模型参数估计的偏误。在以后更加深入的研究中需要采集到更多区域交通网络的样本数据，以对本文所提模型的有效性进行检验

# 参考文献：

[1]邹志云，毛保华，龚全州．城市道路网络失效(堵塞）相关性分析[J]. 交通运输系统工程与信息,2009,9(2):110-114.   
[2]马文·劳沙德．系统可靠性理论：模型、统计方法及应用[M].2版．北 京：国防工业出版社,2010.   
[3]Kamm L.Reliability and maintenance [J].Social Science Electronic Publishing,2017,81(4): 147-147.   
[4]月当悔 佰快尘[J]T国认 道科学,2016,37(1): 132-137.   
[5]马洪伟，周溪召．随机交通网络渐近连通可靠性分析[J].运筹与管理, 2015, (3): 45-50.   
[6]Sun H,Wu J,Wang W,et al.Reliability-based trafic network design with advanced traveler information systems [J]. Information Sciences,2014,87: 121-130.   
[7]Sumalee A,Watling D,Nakayama S. Reliable network design problem: case with uncertain demand and total travel time reliability[J]. Transportation Research Record Journal of the Transportation Research Board,2006,1964 (1): 81-90.   
[8]Bhat CR,Sardesai R.The impact of stop-making and travel time reliability oncommute mode choice [J]. Transportation Research Part B Methodological,2006,40 (9):709-70.   
[9]Clark S,Watling D.Modelling network travel time reliability under stochastic demand[J]. Transportation Research PartB Methodological, 2005, 39 (2): 119-140.   
[10] Liu HX,Recker W,ChenA.Travel Time Reliability[M].[S.1.] $\vdots$ Springer, 2004.   
[11]林徐勋，袁鹏程，霍良安．基于概率密度演化理论的动态行程时间可靠 性计算模型研究[J]．管理工程学报,2017,31(3):141-148   
[12]LiuHX, YunPU.Road Network Capacity Reliability Based on Link Travel Time Reliability[J]. Journal of Southwest Jiaotong University,2oo4,39 (5): 573-576.   
[13] Chen A, Yang H, Hong K L,et al. Capacity reliability ofaroad network: an assessment methodology and numerical results [J]. Transportation Research Part B Methodological,2002,36 (3): 225-25.   
[14]郭长波，张宁．快速路出口通行能力的可靠性仿真研究[J]．系统仿真 学报,2003,15 (11): 1595-1599.   
[15]郭洪洋，韩雪松，刘澜，etal.驾驶员交通安全行为可靠性风险度量研 究[J].中国安全科学学报,2013,23(6):103-109.   
[16]郭孜政，张殿业，金键，et al．机车双司机驾驶行为可靠性研究[J]．中 国安全科学学报,2007,17(2):162-168.   
[17] Tan Z, Yang H, GuoR.Pareto efficiencyofreliability-based traffic equilibria and risk-taking behavior of travelers [J]. Transportation Research Part B Methodological,2014, 66 (8): 16-31.   
[18] Uno N,Iida Y,Kawaratani S,etal.An analysis of potential of providing information on traffic accident to enhance travel time reliability [C]//Proc of the 1 st International Symposium on Transportation Network Reliability. 2003.   
[19]袁鹏程，韩印，马万达．基于行程时间可靠性的随机交通网络均衡模型 [J]．上海理工大学学报,2008,30(4):352-356.   
[20] Chen A, Kasikitwiwat P, Yang C.Alternate capacity reliability measures for transportation networks [J]. Journal of Advanced Transportation, 2013,47 (1): 79-104.   
[21]Palma A D,Picard N. Route choice decision under travel time uncertainty [J].Transportation Research PartAPolicy&Practice,20o5,39(4):295-324.   
[22] Hong KL,Luo XW,Siu B WY.Degradable transport network: Travel time budget of travelers with heterogeneous risk aversion [J].Transportation Research PartB Methodological,2006,40(9): 792-806.   
[23]WuJJ,Sun HJ,Gao ZY.Cascading failures on weighted urban traffic equilibrium networks [J].PhysicaA Statistical Mechanics & Its Applications, 2007,386 (1): 407-413.   
[24] Zheng JF,Gao ZY, Zhao X M.Modeling cascading failures in congested complex networks [J].Physica A Statistical Mechanics $\&$ Its Applications, 2007,385 (2): 700-706.   
[25] Sun HJ, Zhao H,Wu JJ.A robust matching model of capacity to defense cascading failure on complex networks [J].PhysicaA Statistical Mechanics & Its Applications,2008,387 (25): 6431-6435.   
[26]吴建军．城市交通网络拓扑结构复杂性研究[D].北京：北京交通大学, 2008.   
[27]王正武，况爱武，王贺杰．考虑级联失效的交通网络节点重要度测算 [J]．公路交通科技,2012,29(5):96-101.   
[28]王正武，彭烁，黄中祥城市道路交通网络级联失效的灾害蔓延动力学 模型[J].安全与环境学报,2014,14(3):1-4   
[29]王芳．基于级联失效的均衡路网脆弱性研究[D].成都：西南交通大学, 2013.   
[30]陈小兰．城市交通复杂网络级联失效影响源辨识[D].长沙：长沙理工 大学,2013.   
[31]尹洪英，权小锋．交通运输网络级联失效影响规律及影响范围[J]．系 统管理学报,2013,22(6):869-875.   
[32]徐小洋．面向节点重要性评价的城市道路交通网络失效模型研究[D]. 北京：北方工业大学,2017.   
[33] Kerner,Boris S,Rehborn,et al.Recognition and tracking of spatialtemporal congested traffic patterns on freeways [J].Transportation Research Part C,2004,12(5):369-400.   
[34]蔡燕飞.基于交通相特征的交通系统状态识别[D].广州：华南理工大 学,2011.   
[35]袁鹏程，隽志才．区域交通网络行程时间估计的半 Markov 链模型[J]. 系统管理学报,2014,23(5):690-697.