# 基于能效的异构蜂窝网络微基站部署研究\*

赵拓¹，杨 洁²，曹雪虹1,2

(1．南京邮电大学 通信与信息工程学院，南京 210003;2.南京工程学院 通信工程学院，南京 211167)

摘要：针对齐次泊松点过程下异构蜂窝网络的能量效率进行了研究。首先，利用齐次泊松点过程对异构蜂窝网络进行建模;然后在瑞利信道环境下给出了系统的覆盖率和可达速率的表达式，并且推导了能量效率的闭合形式的表达式；最后，通过凸优化算法对微基站密度进行优化，使网络能量效率达到最大。仿真结果表明，微基站的密度对系统能量效率有显著的影响，通过合理的设置微基站密度能有效提高系统的能量效率。

关键词：异构蜂窝网络；齐次泊松点过程；能量效率；覆盖率；可达速率 中图分类号：TN929.5 doi:10.3969/j.issn.1001-3695.2017.07.0678

# Energy-efficient micro-base station deployment in heterogeneous cellular network

Zhao Tuol, Yang Jie², Cao Xuehong1-2 (1.DeptofCommunication&InformationEngineering,anjingUniversitofPosts&Telecommunications,Nanjing0003, China; 2.SchoolofCommunication Engineering,Nanjing InstituteofTechnology,Nanjing 211167,China)

Abstract:This paper shows theresearch on the energy eficiengyofheterogenous cellularnetworks in homogenous Poison point processFirstlymodelingthe heterogenous cellular networks byusing homogenous Poison process.Secondly,deriving theexpressionofsystem'scoverage probabiltyandachievableratainRayleighchannelsituations,andthen deducingas wel as theexpressonofenergy eficiency'sclosedform.Finalyoptimizingthedensityofmicro-base stationviaconvex-optimum method in order to maximize networks’energy eficiency.The simulation resultsshow that micro-base station's density has significant effects onsystem'senergy eficiency.Itsessence is through reasonableseting of micro-base station'sdesityto available help improve its efficiency.

KeyWords:heterogeneous cellularnetworks;homogeneous Poisson point proces; energyeficiency;coverage probability; achievable rata

# 0 引言

近十几年来，移动数据流量的爆炸式增长给传统蜂窝网络带来了许多的挑战。为了满足急剧增长的业务流量需求，可以通过部署大量的基站来解决问题，但这样会带来大量的能量消耗，不符合绿色通信的要求[1]。由此异构蜂窝网络的概念被提出并得到了人们广泛的关注[2]。异构蜂窝网络由具有不同发射功率和覆盖范围的基站节点组成。异构蜂窝网络内除了常规的宏基站部署，还在宏蜂窝内部署了多种不同的低功率基站，如家庭基站和Pico基站等。其中宏基站发射功率很大，用来提供网络基本的覆盖。Pico基站主要部署在通信的热点区域，作为宏基站的补充，主要用来改善小区边缘用户的信号质量和提高热点区域的容量。

以前针对异构蜂窝网络的建模主要采用基于六边形网格的模型，这种网格格模型的最主要的特征是宏基站都规则的分布在六边形小区的中心，而微基站则规则的部署在六边形小区的边缘上。然而这种模型虽然直观明了，但是网格与实际基站部署差别太大，并且在数学上不易分析干扰特性。为了克服六边形网格模型的不足，JeffreyG.Andrews率先提出采用泊松点过程(PoissonPointProcess,PPP)[3]对蜂窝网络的基站进行建模，PPP模型不仅能够体现网络节点的随机分布特性，而且大大简化了蜂窝网络性能的分析，因此得到了人们广泛的关注。鉴于PPP模型的优点，本文在PPP模型的基础上，综合考虑了基站偏置和频谱复用方式来对异构蜂窝网络进行分析。用目前文献中针对提高能量效率的方法大致有无线资源管理、基站休眠、基站的部署策略等。文献[4]通过研究用户速率的下界，将非凸的最优化问题转换为一个凸的优化问题。然后提出了两步式算法对功率和信道进行合理的分配来最小化系统的功率消耗。文献[5]通过把微基站用户切换到宏基站会不会减少功率消耗作为判断微基站休眠的准则，通过微基站的休眠策略来减少系统的功率消耗。文献[6]利用了随机几何理论研究了异构蜂窝网络下的最优基站密度，以最大程度减少系统的能量消耗。文献[7]推导了不同休眠模式下的成功概率和能效表达式，尤其研究了随机休眠策略和动态休眠策略对系统功率消耗的影响。文献[8]根据信道状态信息和电路功率消耗来对小小区的功率和回程链路的带宽做分配，使系统的能量效率最大。文献[9]通过联合部分频率复用和基站休眠来减少异构蜂窝网络的能量消耗。文中首先推导了用户在不同基站层的覆盖率，接着通过优化部分频率复用因子和两种基站活跃概率比来使覆盖率最大，这样功率最小化问题可以通过分析最优的部分频率复用因子和基站活跃概率比来解决。文献[10]通过引入一个偏移因子扩展小区的范围来提升系统的能量效率。文献[11]通过用户的关联策略和功率控制来最优化系统上行链路的能量效率,并提出一个迭代算法来解决。文献[12]通过对无线资源、功率和基站的休眠联合设计来最小化异构蜂窝网络的功率消耗。但是上述研究都没有考虑微基站密度对系统能量效率的影响。

上述研究和本文最相关的是[6],但是它只涉及对系统的能量消耗的优化，但是本文是直接对系统的能量效率进行优化。本文推导了系统的能量效率的表达式，通过凸优化方法实现了能量效率的最优化。实验仿真的结果验证了理论分析的正确性。

# 1 异构蜂窝网络模型

考虑如图1所示的两层异构蜂窝网络场景：

![](images/ee140cdfe1ecc089bac07fb234570642f422f06c027a22bee355a1c6afabee46.jpg)  
图1两层异构蜂窝网络示意图

本文考虑的是由宏基站和微基站(Pico基站)构成的两层异构蜂窝网络，微基站以泊松点分布的方式部署在宏小区范围内，不同层基站的传输功率、密度和支持的数据速率都不同。本文假设第i层的基站是服从密度为λi的齐次泊松点过程 $( { \mathrm { H P P P } } ) \Phi _ { i }$ $\operatorname { i = } 1 , 2$ 。基站分布图如图2所示。为了便于分析，本文假设层与层之间是完全独立的。每层的发射功率为 $P _ { i }$ ，同一层上的所有基站发射功率相同，基站的信干噪比（Signalto Interference plusNoise Ratio,SINR）门限为 $\beta _ { i }$ ,并且每层的路径损耗因子假设是$\mathfrak { a }$ 。用户的分布同样也是服从密度为 $\lambda _ { u }$ 的齐次泊松点过程 $\Phi _ { u }$ ，并且用户的分布和基站的分布是相互独立的。

由统计学知识[13]14]可知，对于随机分布的异构网络基站，所有用户都具有相同的统计特性。所以，不失一般性，本文以位于原点的典型用户作为讨论对象并分析其性能。考虑全频率复用的情况。假设位于r处的基站和位于原点的典型用户之间的信道衰落损耗为 $h _ { { } _ { r } }$ 。若假设是瑞利信道，则 $h _ { { } _ { r } }$ 为独立同分布的指数分布。路径损耗函数为 $\operatorname { L } ( \operatorname { r } ) = \Vert r \Vert ^ { - \alpha }$ ， $\alpha > 2$ 。所以位于原点处的典型用户接收到第 $\mathbf { k }$ 层位于 $r _ { k }$ 处的基站的信号功率为$\begin{array} { r } { P _ { k } h _ { r _ { k } } \ : \Pi r _ { k } \ : \Pi ^ { \alpha } } \end{array}$ 。如果这个用户连接到该基站，则该用户的信干噪比（SINR）为：

$$
\operatorname { S I N R } \left( r _ { k } \right) = \frac { P _ { k } h _ { r _ { k } } \left\| r _ { k } \right\| ^ { - \alpha } } { I + \sigma ^ { 2 } }
$$

其中分母的第一项 $I$ 为其他干扰基站对目标用户的总干扰， $\sigma ^ { 2 }$ 为恒定的加性噪声功率。通常，在典型的异构蜂窝网络中，主要的干扰源为小区间的干扰，它一般会比加性噪声大很多，所以通常认为加性噪声对异构蜂窝网络的性能没有太大的影响，因此本文一般忽略噪声项。文献[15]已经证明了这个假设的合理性。本文假设用户采用基于SINR的接入方式，即如果第 $k$ 层的基站能提供大于 $\beta _ { k }$ 的SINR,那么用户就接入到第k层。因为此时可能会出现一个用户会接入多层的情况，为了便于分析本文假设 $\beta _ { \iota } { > } 1$ 这样在整个网络中某个时刻至多只有一个基站可以提供大于 $\beta _ { k }$ 的 SINR，也就是说此时一个用户至多只能接入到一个基站。

![](images/40eaf13fc8c1d3a19f2cf10b879ac09630ae67c10349dd3bf6ea93e5f663701d.jpg)  
宏基站密度为0.1，微基站密度为0.5的基站分布图  
图2两层异构蜂窝网络的基站分布

# 2 异构蜂窝网络性能分析

# 2.1覆盖率分析

覆盖率在无线通信中是一个重要的服务质量指标，它通常由用户接收 SINR 的互补累计积分函数(Complementarycumulativedistributionfunction,CCDF)来表示，也就是SINR大于某一门限值的概率。数学上用户的覆盖率可以定义为

$$
P _ { C } = \Pi \{ S I N R > \beta \}
$$

本文假设基站采用开放接入模式，即目标用户可以接入任意层基站。在本文的系统模型中，这样的假设意味着用户会选择接入提供最大SINR的基站。根据文献[15]的推论1,在干扰受限的二层异构蜂窝网络中（忽略噪声)，覆盖率可以表示为

$$
P _ { c } = { \frac { \pi } { C ( \alpha ) } } { \frac { \sum _ { k = 1 } ^ { k = 2 } \lambda _ { k } P _ { T k } ^ { 2 / \alpha } \beta _ { k } ^ { - 2 / \alpha } } { \sum _ { k = 1 } ^ { k = 2 } \lambda _ { k } { P _ { T k } } ^ { 2 / \alpha } } }
$$

其中： $P _ { \mathit { T k } }$ 为第 $k$ 层基站的发射功率， $\mathbf { C ( \boldsymbol { \alpha } ) } = \frac { 2 \pi ^ { 2 } } { \arcsin \left( \displaystyle \frac { 2 \pi } { \alpha } \right) }$

从式（3）可以看出，覆盖率和基站的密度，发射功率，信干比门限都有关系。但是三者相比，基站的密度密度更起决定性的作用。因为 $\frac { 2 } { \alpha } \langle 1 , \alpha \rangle 2$ 。如果每层的信干噪比门限值相同,即 $\beta _ { k } = \beta$ ，则覆盖率可以表示为

$$
P _ { c } = \frac { \pi } { C ( \alpha ) \beta ^ { - 2 / \alpha } }
$$

可以看出，此时覆盖率与基站的密度、发射功率还有网络的层数都无关。因此增加基站密度和功率将不会对覆盖率有影响。这是因为用户接收到的有用信号的功率和干扰信号的功率变化趋势大致相同，所以信干噪比大概保持不变。又因为用户是基于信干噪比和信干噪比门限来选择接入基站的，所以导致了覆盖率基本不变。

根据文献[15]中的推论2,用户连接到第 $\mathbf { k }$ 层基站的概率可以表示为：

$$
A _ { k } = \frac { \lambda _ { k } P _ { T k } ^ { 2 / \alpha } \beta _ { k } ^ { - 2 / \alpha } } { \sum _ { k = 1 } ^ { k = 2 } \lambda _ { k } P _ { T k } ^ { 2 / \alpha } \beta _ { k } ^ { - 2 / \alpha } }
$$

观察式（5）可以发现,用户更倾向于接入密度高的，功率大的，信干比阈值小的那一层。与上面覆盖率的分析类似，对于接入概率来说，基站密度相比基站发射功率和信干比门限来说更起决定性作用。

# 2.2最小可达速率分析

在异构蜂窝网络中，假设是等资源分配的，即所有基站为其服务的用户分配了相同的带宽资源。根据香农公式，当目标用户连接到第 $\mathbf { k }$ 层基站时，其最小可达速率可以表示为

$$
R _ { k } = \operatorname { E } \left[ { \frac { B } { N _ { k } } } l o g _ { 2 } \left( 1 + { \boldsymbol { \beta } } _ { k } \right) \right]
$$

其中：B表示系统的带宽， $\mathrm { N _ { k } }$ 表示第 $\mathbf { k }$ 层平均每个基站服务的用户数。为了便于处理，假设 $\mathrm { N _ { k } }$ 和 $\beta _ { \mathrm { ~ k ~ } }$ 是相互独立的，这并不影响结果的准确性[16],所以 $\mathtt { R } _ { \mathrm { k } }$ 可表示为

$$
R _ { k } = \frac { B } { \operatorname { E } [ N _ { k 1 } } l o g _ { 2 } \big ( 1 + \beta _ { k } \big )
$$

根据文献[16,17],服务基站的平均负载为：

$$
\operatorname { E } \left[ N _ { k } \right] = 1 + 1 . 2 8 { \frac { \lambda _ { u } A _ { k } } { \lambda _ { k } } }
$$

由此能得出系统中总的最低可达速率为

$$
R _ { t o t a l } = \sum _ { k = 1 } ^ { k = 2 } P _ { C k } \lambda _ { u } R _ { k }
$$

其中 $P _ { C k }$ 表示第 $\mathrm { ~ k ~ }$ 层的覆盖率。

# 2.3 能效分析

通常，基站的功率消耗主要由两部分组成：静态功耗和动态功耗。静态功耗主要由功率放大器、制冷器、信号处理、天线、备用电池等组成。动态功耗主要由基站的发射功率产生。

一般静态功耗和动态功耗是相互独立的，因此，一个基站的总功率消耗可以表示为

$$
P _ { \mathrm { { } } k } = P _ { \mathrm { { } } _ { s t a t i c \_ k } } + w _ { \mathrm { { } } k } P _ { \mathrm { { } } T k }
$$

其中: $P _ { s t a t i c \_ k }$ 为第 $\mathrm { ~ k ~ }$ 层基站的静态功耗， $w _ { k }$ 为发射功率相关的尺度因子， $P _ { T k }$ 为基站的发射功率。

系统的能效一般定义为系统单位时间内的总吞吐量和总的功率消耗的比值。所以本文中系统能效可以表示为

$$
\eta _ { E E } = \frac { R _ { t o t a l } } { P _ { t o t a l } }
$$

其中： $P _ { t o t a l }$ 是网络中所有基站的功率消耗的总和，它和基站的功率还有密度有关。因此，根据覆盖率和吞吐量的表达式，系统能量效率可以表示为

$$
\eta _ { E E } = \frac { R _ { t o t a l } } { P _ { t o t a l } } = \frac { \sum _ { k = 1 } ^ { k = 2 } P _ { C } \lambda _ { u } R _ { k } } { \sum _ { k = 1 } ^ { k = 2 } \lambda _ { k } P _ { k } }
$$

其中， $P _ { \kappa } = P _ { s t a t i c \_ k } + w _ { k } P _ { T k }$ ，因为 $w _ { k }$ 与服务基站的负载量呈线性关系，所以为了简单起见，假设 $w _ { k } = \operatorname { E } \left[ N _ { k } \right]$ 。

经过一系列代数的化简，能得到能量效率的表达式为

$$
\begin{array} { r } { \eta _ { \varepsilon E } = \frac { B \pi } { C ( \alpha ) } \frac { \sum _ { k = 1 } ^ { k = 2 } { \overbrace { ( \sum _ { k = 1 } ^ { k - 2 } \lambda _ { k } P _ { \pi } ^ { 2 \mu } C \lambda _ { \ast } } ^ { [ \lambda _ { k } P _ { \pi } ^ { 2 \mu } ( { D } + ( \beta _ { k } ) ) ] / \lambda _ { \ast } } }  } {  \sum _ { k = 1 } ^ { k = 2 } \overbrace { \lambda _ { k } P _ { \pi } ^ { 2 \mu } ( { D } - ( \lambda _ { \ast } ) ) ( 1 + 1 . 2 8 A _ { k } \lambda _ { k } / \lambda _ { k } ) } ^ { [ \lambda _ { k } P _ { \pi } ^ { 2 \mu } ( { D } + ( \lambda _ { \ast } ) ) ] } }  } \\ {  \sum _ { k = 1 } ^ { k = 2 } \lambda _ { k } [ P _ { \pi M i _ { 2 } } + P _ { \pi } + 1 . 2 8 \frac { P _ { \pi } P _ { \pi } ^ { 2 } \beta _ { k } ^ { - 2 } } { [ \lambda _ { \ast } P _ { \pi } ^ { 2 } \beta _ { k } ^ { - 2 } ] }   } \\ {   \sum _ { k = 1 } ^ { k = 2 } \overbrace { \lambda _ { \ast } P _ { \pi } ^ { 2 } \beta _ { k } ^ { - 1 } } ^ { [ \lambda _ { \ast } P _ { \pi } ^ { 2 } ( { D } + ( \lambda _ { \ast } ) ) ] } ^ { [ \lambda _ { \ast } P _ { \pi } ^ { 2 } ( { D } + ( \lambda _ { \ast } ) ) ] / \lambda _ { \ast } } ] } \end{array}
$$

# 3 能量效率优化求解

在异构蜂窝网络中，一般宏基站的密度都是是固定的，所以本部分只考虑对微基站的密度的优化。不难证明优化问题式（13）的目标函数是一个凹函数，为了便于利用凸优化算法进行求解，把式（13）进行取反。这样优化问题式（14）就变成了一个凸优化问题。因为最优化问题式（14）的目标函数的一阶导数是非线性的，所以令导函数为零的方式不能得出最优解。本文采用黄金分割法来求目标函数的最小值。

$$
\begin{array} { r } { \operatorname* { m i n } _ { \lambda _ { i } \ge } \frac { - B \pi } { C ( \alpha ) } \frac { \sum _ { k = 1 } ^ { k = 2 } \frac { \big [ \lambda _ { k } P _ { \pi } ^ { 2 \alpha } / o g 2 \big ( 1 + \beta _ { k } \big ) \big ] / \lambda _ { u } } { \left( \sum _ { k = 1 } ^ { k = 2 } \lambda _ { k } P _ { \pi k } ^ { 2 \alpha } / \lambda _ { u } \right) \left( 1 + 1 . 2 8 A _ { k } \lambda _ { u } / \lambda _ { k } \right) } } { \sum _ { k = 1 } ^ { k = 2 } \frac { \sqrt { \left( \sum _ { k = 1 } ^ { k } \lambda _ { k } P _ { \pi k } ^ { 2 \alpha } / \lambda _ { u } \right) } } { \lambda _ { u } } } } \\ { \sum _ { k = 1 } ^ { k = 2 } \frac { \lambda _ { k } } { \lambda _ { u } } \left[ P _ { s u l t _ { 1 } } + P _ { \pi k } + 1 . 2 8 \frac { P _ { \pi } P _ { \pi } ^ { 2 } \beta _ { k } ^ { - \frac { 2 } { \alpha } } } { \sum _ { k = 1 } ^ { k = 2 } \frac { \lambda _ { k } P _ { \pi } ^ { 2 } \beta _ { k } ^ { - \frac { 2 } { \alpha } } } { \lambda _ { u } } } \right] } \end{array}
$$

$$
s . \ t 0 < \lambda _ { 2 } < \lambda _ { 2 M A X }
$$

算法描述如下：

算法输入为微基站的密度范围，算法输出为最佳的微基站密度和能效相反数的最小值。

给定初始区间 $[ m , n ]$ 以及精度 $\varepsilon > 0$

步骤1.令 $x _ { 2 } = m + 0 . 6 1 8 ( n { - } m ) , f _ { 2 } = f ( x _ { 2 } ) .$ 转到步骤2；

步骤2.令 $\mathrm { x } _ { 1 } \mathrm { = m } \mathrm { + } 0 . 3 8 2 ( \mathrm { n } \mathrm { - m } ) , \mathrm { f } _ { 1 } \mathrm { = f } ( \mathrm { x } _ { 1 } )$ ，转到步骤3；

步骤3.如果 $\vert n - m \vert \leqslant \varepsilon$ ，则 $x ^ { * } { = } ( m { + } n ) / 2$ 并且停止迭代。如果|m $n | > \mathfrak { \varepsilon }$ ，则转到步骤 $^ { 4 }$

步骤4.如果 $f _ { I } < f _ { 2 }$ 则 $n { = } x _ { 2 } { , } x _ { 2 } { = } x _ { I } { , } f _ { 2 } { = } f _ { I } { , }$ 转到步骤2;

如果 $f _ { I } = f _ { 2 }$ 则 $\scriptstyle { m = x _ { I } , n = x _ { 2 } } ,$ 转到步骤1;

如果 $f _ { I } > f _ { 2 }$ 则 $\scriptstyle { m = x _ { I } , x _ { I } = x _ { 2 } , f _ { I } = f _ { 2 } } ,$ 转到步骤5；

步骤5.令 $x _ { 2 } = a + 0 . 6 1 8 ( n { - } m ) , f _ { 2 } = f ( x _ { 2 } ) .$ 转到步骤3。

只需将初始区间设为 $\left[ 0 , \lambda _ { _ { 2 M A X } } \right]$ ， $\mathrm { f \left( x \right) }$ 设为 $- \eta _ { _ { E E } }$ 然后就可以根据算法求得最优的微基站密度 $\boldsymbol { \lambda } _ { 2 } ^ { * }$ ，把 $\boldsymbol { \lambda } _ { 2 } ^ { * }$ 公式（13）就能得到能量效率的最大值。

$$
\eta _ { E E } ^ { * } = D ^ { * } \frac { L 1 ^ { * } w _ { 1 } + L 2 ^ { * } w _ { 2 } } { \left( L 1 + L 2 \right) ^ { * } \left[ \left( 1 + \frac { 1 . 2 8 A _ { 1 } \lambda _ { u } } { \lambda _ { 1 } } \right) + \left( 1 + \frac { 1 . 2 8 A _ { 2 } \lambda _ { u } } { \lambda _ { 2 } ^ { * } } \right) \right. }
$$

其中

$$
L 1 = \lambda _ { 1 } P _ { T 1 } ^ { \frac { 2 } { \alpha } } / \lambda _ { u } , { \lambda _ { 2 } ^ { * } } P _ { T 2 } ^ { \frac { 2 } { \alpha } } / \lambda _ { u } = L 2 , w _ { k } = l o g 2 \bigl ( 1 + \beta _ { k } \bigr ) ,
$$

$$
\mathbf { D } = \frac { B \pi } { C ( \alpha ) } , \ P _ { 1 } = \frac { \lambda _ { 1 } } { \lambda _ { u } } \left( P _ { s t a t i c _ { 1 } } + P _ { T 1 } + 1 . 2 8 \frac { P _ { T 1 } P _ { T 1 } ^ { \frac { 2 } { \alpha } } \beta _ { 1 } ^ { - \frac { 2 } { \alpha } } } { L 1 ^ { * } \beta _ { 1 } ^ { - \frac { 2 } { \alpha } } + L 2 ^ { * } \beta _ { 2 } ^ { - \frac { 2 } { \alpha } } } \right) ,
$$

$$
P _ { 2 } = \frac { \lambda _ { 2 } ^ { * } } { \lambda _ { u } } ( P _ { s t a t i c _ { 2 } } + P _ { T 1 } + 1 . 2 8 \frac { P _ { T 2 } P _ { T 2 } ^ { \frac 2 \alpha } \beta _ { 1 } ^ { - \frac 2 \alpha } } { L 1 ^ { * } \beta _ { 1 } ^ { - \frac 2 \alpha } + L 2 ^ { * } \beta _ { 2 } ^ { - \frac 2 \alpha } } )
$$

# 4 仿真分析

本部分通过 MATLAB 蒙特卡洛仿真对上述理论结果进行仿真，仿真结果是通过在正方形区域内5000次随机撒点得到的。如果没有特别说明，仿真参数如表1所示。

表1两层异构网络系统级仿真参数  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>系统区域</td><td>160000平方米的正方形区域</td></tr><tr><td>系统带宽</td><td>10 MHz</td></tr><tr><td>宏基站密度</td><td>入=0.001m²</td></tr><tr><td>用户密度</td><td>入u=0.1m-²</td></tr><tr><td>路径损耗指数</td><td>α=4</td></tr><tr><td>信干比门限</td><td>β2=0dB</td></tr><tr><td>宏基站静态功率</td><td>1000W</td></tr><tr><td>宏基站发射功率</td><td>40W</td></tr><tr><td>微基站静态功率</td><td>50W</td></tr><tr><td>微基站发射功率</td><td>1W</td></tr><tr><td>微基站密度最大值</td><td>0.35m²</td></tr></table></body></html>

图4给出了不同宏基站门限下的覆盖率曲线图。在这里微基站的密度为宏基站的2倍。从理论结果曲线和仿真曲线可以看出二者大致拟合，所以这就证明了式（8）的正确性。另外可以看出，随着宏基站门限值的逐渐增加，覆盖率逐渐减小。这是因为本文中，用户是采用基于实时SINR的方式选择接入基站的，所以随着宏基站SINR门限值的逐渐增加，用户接入宏基站的可能性就会越下，所以就导致了覆盖率的递减。

![](images/d7f0be5eaca7343cc0f43642636ccb1beae1949f822698b83c99568889aa4fd7.jpg)  
图4覆盖率和宏基站门限的关系

图5给出了覆盖率和微基站密度之间的关系。这里本文假设宏基站的门限值 $\beta _ { \mathrm { 1 } } = 2 d B$ 。从图中可以看出，随着微基站的密度的增大，覆盖率也逐渐增大，但是最终覆盖率变化会趋于平缓收敛到一个值。这表明，当微基站密度足够大之后，继续增加微基站密度不会使系统覆盖率继续增加。这是因为当微基站密度很小的时候，随着微基站密度的增加，边缘用户会得到有效的服务，所以此时覆盖率会逐渐增加。但是当微基站的密度增加到一定值以后，用户接收到有用信号强度增加的同时受到的干扰也会越严重，有用信号和干扰信号相互均衡，所以此时覆盖性能不会继续增加而是收敛为一个固定的值。

![](images/4950bb5bc1feb3ce171c65498544f39bb27bd26a5789b360cf45d6e39e809481.jpg)  
图5覆盖率和微基站密度的关系

图6给出了微基站密度和能效的关系曲线图，此时假设用户密度为一个定值。从中可以看出，随着微基站的密度逐渐的增大，系统的能量效率先增大后减小。增大的原因是随着微基站密度的增加，宏基站的部分用户会由微基站提供服务，由于微基站的功率较小，所以此时系统能效会提升。但由于此时用户密度为某一定值，所以当微基站密度大于某一给定的值后，由于微基站的持续增多，系统的功率消耗也会持续增加，所以此时会造成能量效率的下降。并且从图中可以看出提高宏基站的信干噪比门限也会是系统能效得到提高，这是因为宏基站的信干比门限提高后，用户会更倾向于接入微基站，所以导致能效增加。

![](images/656a33e3db8ec05e23f07166b1b915ffb648fe29c9e99d83b7b0b1cd9cb4adbc.jpg)  
图6微基站密度和能效的关系

图7给出了在不同的用户密度下， $\beta _ { 1 } = \beta _ { 2 } = 0 d B$ 时最优微基站密度对应的能效和非最优微基站密度对应能效对比。最上方的曲线是，最优微基站密度下对应的系统能效，下面两个曲线分是普通微微基站密度下的系统能效。从图可以很明显的看出，在不同的用户密度情况下，通过合理的调整微基站密度可以使系统能效显著的提高。

![](images/4f3ca543abe40bab04c61d0dc469b4ed41a133c4306b34e4894fe37e4b934606.jpg)  
图7不同微基站密度下系统能效的比较

# 5 结束语

本文利用随机几何的理论研究了异构蜂窝网络中微基站的部署对系统能量效率的影响。首先给出了干扰受限情况下覆盖率的表达式，然后基于此推导出系统的最小可达容量，并构建出系统能效的数学模型。对于能效的数学模型，本文利用凸优化的手段进行优化，求得给定配置条件下的最优微基站部署。仿真结果显示，最优微基站密度是存在的，在这种微基站密度配置下的能量效率要高于普通微基站密度下的能量效率。本文的研究可为微基站的实际部署提供了一些理论指导。

# 参考文献：

[1]Coskun C C,Ayanoglu E.A greedy algorithm for energy-efficient base

station deployment in heterogeneousnetworks [C]//Procof IEEE International Conference on Communications.2015:7-12.   
[2]Andrews JG,Buzzi S,Wan C,et al. What will5G be?[J]. IEEE Journal on Selected Areas in Communications,2014,32 (6): 1065-1082.   
[3]Andrews JG, Bacceli F, Ganti R K.A tractable approach to coverage and rate in cellular networks [J].IEEE Trans on Communications,2011,59 (11): 3122-3134.   
[4]Sun X,Wang S.Resource Allocation Scheme for Energy Saving in Heterogeneous Networks[J].IEEE Trans on Wireless Communications, 2015,14 (8): 4407-4416.   
[5] 邱畅啸，冷甦鹏，叶宇．基于能效的异构无线网络联合切换调度和资源 分配算法[J].计算机应用,2015,35(6):1505-1508.   
[6] Cao D, Zhou S,Niu Z. Optimal combination of base station densities for energy-efficient two-tier heterogeneous cellular networks [J]. IEEE Trans on Wireless Communications,2013,12(9): 4350-4362.   
[7]Yong S S,Quek TQ S, Kountouris M,et al. Energy eficient heterogeneous celular networks [J]. IEEE Journal on Selected Areas in Communications, 2013,31 (5): 840-850.   
[8]Liu H, Zhang H, Cheng J,et al. Energy eficient power allocation and backhaul design in heterogeneous small cell networks [C]// Proc of IEEE International Conference on Communications.2016: 1-5.   
[9] Cao D, Zhou S,Niu Z. Improving the energy eficiency of two-tier heterogeneous cellular networks through partial spectrum reuse [J]. IEEE Trans on Wireless Communications,2013,12 (8): 4129-4141.   
[10] Zhang Yuhao,Cui Zhiyan, Cui QImei,et al.Energy efficiency analysis of heterogeneous cellular networks with extra cell range expansion [J]. IEEE Access,2017, PP (99).   
[11] Wang M,Gao H,Lv T.Energy-efficient user association and power control in the heterogeneous network[J]. IEEE Access,2017,PP(99).   
[12] Ghazzai H,Farooq M J,Alsharoa A,et al.Green networking in cellular hetnets: a unified radio resource management framework with base station on//off switching[J].IEEE Trans、on Vehicular Technology,2016,PP(99).   
[13] Bacceli F,Blaszczyszyn B.Stochastic geometry and wireless networks,par II: applications [M].[S.1] $\because$ Now Publishers Inc.2009:1-312   
[14]Haenggi M. Stochastic geometry for wireless networks [M].[S.1.]: Cambridge University Press,2012.   
[15] Dhillon H S,Ganti RK,Baccelli F,et al.Modeling and analysis of $\mathbf { k }$ -tier downlink heterogeneous cellular networks [J]. IEEE Journal on Selected Areas in Communications,2011,30(3): 550-560.   
[16] Singh S,Dhillon H S,Andrews JG. Ofloading in heterogeneous networks: modeling，analysis,and design insights[J].IEEE Transon Wireless Communications,2013,12 (5): 2484-2497.   
[17] Dhillon H S,Andrews JG.Downlink rate distribution in heterogeneous cellular networks under generalized cell selection [J]. IEEE Wireless Communications Letters,2014,3(1): 42-45.