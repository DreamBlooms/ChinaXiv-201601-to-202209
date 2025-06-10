# 高速铁路移动通信下基于IMT-A的时变信道建模

廖勇1,²，樊卓宸³，沈轩帆1，胡异1，姚海梅1，张楠1(1.重庆大学飞行器测控与通信教育部重点实验室，重庆 400044;2.西安电子科技大学 综合业务网理论及关键技术国家重点实验室，西安 710071;3．北京大学信息工程学院，广东 深圳 518055)

摘要：信道建模及其仿真方法是高速铁路移动通信系统设计的难点，同时已有的面向高速移动下IMT-A时变信道建模的研究仍存在不足。针对上述挑战，提出了一种高铁移动下具有时变参数的基于IMT-A信道的建模方法。首先，针对 IMT-A的城市宏小区场景，设计了一个马尔可夫过程来模拟时变簇的数量变化，接着推导出随时间变化的信道参数的表达式，其中包括簇的延迟、功率、离开角和到达角，并得到了信道冲激响应；其次，分析了信道的时变空时域互相关函数、时变自相关函数以及平稳间隔；最后，对所提信道模型的统计性质进行了仿真，验证了该模型具有时变性以及高速铁路信道具有的非平稳性，并且证明了所提信道模型可用来模拟高速铁路信道的可行性。

关键词：高速移动；信道建模；时变参数；马尔可夫过程；非平稳性 中图分类号：TN918 doi:10.3969/j.issn.1001-3695.2017.08.0887

# Time-varying IMT-A channel modeling for high-speed train mobile communication scenario

Liao Yong1,², Fan Zhuochen³, Shen Yuanfan1, $\mathrm { \ H u \ Y i ^ { 1 } }$ , Yao Haimei1, Zhang Nanl (1.KeyLaboratoryofAerocraftT&CandCommunicationofMinistryofEducation,ChongqingUniversityChongqing400044, China;2.StateKeyLboratoryotegatedervicsNetworksidianUnversityXi1,ia;3hooloflectoc &Computer Engineering,Peking University Shenzhen Graduate School,Shenzhen Guangdong518055,China)

Abstract: Channelmodelinganditssimulation methodis thedificult pointofhigh-speed train mobilecommunicationsystem design.Athe same time,there are stillsome researches on IMT-Atime-varyingchannel modelingforhigh-sped train mobile communication.Aiming at theabove challenges,this paper presents a modeling method basedon IMT-A channel with highspeed train mobile with time-varying parameters.First,for theurban macro-cel (UMA)sceneofIMT-A,we designa Markov processto simulate the numberof time-varying clusters,and then derive the expression ofthe channel parameters with time, including thedelaypower,Angleandreachangle,and get thechannelimpulseresponse(CIR).Secondly,thetime-varying space-timecross-correlation function(CCF),time-varyingautocorrelation function(ACF)andstationaryintervalofchanneare analyzed.Finalythestatistical propertiesofteproposedchannelmodelaresimulated,whichproves thenon-statioarityof the modelandthenon-stationarityofthehigh-spedtrainchannel,and proves thattheproposedchannelmodelcanbeusedto simulate the feasibility of high-speed train channel.

KeyWords:high-speed train mobile communication;channel modeling; time-varying parameters;Markov process nonstationarity

# 0 引言

媒体通信需求。众所周知，信道是通信系统的基础，它的模型及仿真方法对于特定场景下通信系统的设计具有重要作用。当前面向高铁场景的标准化信道模型主要有IMT-advanced(IMT-A)1和WINNERII信道模型，它们均假设信道满足广义稳定(wide-sense stationary,WSS)并且忽略了其非平稳性。文献[2]中

近年来，随着高速铁路的发展，乘客对高质量、高速率的数据和多媒体通信提出了更高的需求。然而，现有的无线通信技术还无法满足运行速度在 $3 0 0 ~ \mathrm { k m / h }$ 以上列车的高质量的多信道测量的结果表明，标准信道模型明显比实际测量的高速铁路信道具有更长的平稳间隔（定义为信道满足WSS条件的最大持续时间)，而WSS假设仅对实际无线信道中的短时间间隔有效。综上所述，采用常规平稳信道来建模高速铁路信道的方法已经受到日益严峻的挑战。

目前，国内外针对高铁移动通信场景下的信道建模已做了大量研究，特别是针对非几何随机模型(non-geometricalstochasticmodel,NGSM)。文献[3]提出了一种基于高铁无线通信的有限状态马尔可夫链的NGSM，使用马尔可夫链来表征移动簇(movingclusters,MC)的生灭性质。所提模型能够利用马尔可夫链在不同的接收信噪比区间跟踪信道状态的变化，从而捕获高铁无线信道随时间变化的特性。但是，该模型的非平稳的统计性质很难通过推导得出。此外，文献[4]提出了基于NGSM的非平稳车对车信道。基于在高架桥和狭窄通道场景下的高铁信道测量数据，文献[5]提出了一种有限状态的马尔可夫信道，结果表明，莱斯分布能很好地表征小尺度衰落在两种高铁场景下的测量幅度，并且NGSM可有效地捕捉在高铁信道中快衰落的动态本质。但是在现有NGSM的研究方法中，目前尚没有面向IMT-A时变信道的建模，因此，为了健全和完善高速铁路无线信道建模理论，研究这类符合高速铁路移动通信情形下的信道建模方法具有一定的应用参考价值。

为此，本文提出了一种高铁移动通信NGSM场景下具有时变参数的基于IMT-A的信道建模方法，其中时变参数包括簇的数量、功率和延迟，以及离开角(angleofdeparture,AoD)和到达角(anglesofarrival,AoA)。首先本文理论分析了所提模型重要的统计特性，包括局部空间互相关函数(cross-correlationfunction,CCF)、局部时间自相关函数(auto-correlation function,ACF)和平稳间隔。其次，通过MATLAB仿真验证了该信道模型具有非平稳性，从而证明了理论分析和推导的正确性。

# 1 基于IMT-A的信道建模

在高速移动的环境下，可观察到的MC或移动端(MobileStation,MS)的快速移动，这样的移动变化可能会违背前面所提到的WSS假设。在这种情况下提出具有时变参数的基于IMT-A信道建模，几何示意图如图1所示，其信道冲激响应(channelimpulserespond,CIR)可以表示为

$$
h ( t , \tau ) = \sum _ { p = 1 } ^ { P ( t ) } h _ { p } ( t ) \delta \big ( \tau - \tau _ { p } \left( t \right) \big )
$$

其中:

$$
\begin{array} { c } { h _ { p } ( t ) = \sqrt { W _ { p } ( t ) / Q } \times } \\ { \sum _ { q = 1 } ^ { Q } \mathrm { e } ^ { \mathrm { j } \delta _ { T } k \sin ( \alpha _ { p q } ^ { T } ( t ) ) + \mathrm { j } \delta _ { R } k \sin ( \alpha _ { p q } ^ { R } ( t ) ) } \times \mathrm { e } ^ { \mathrm { j } k \left\| \vec { v } _ { M S } \right\| \cos ( \alpha _ { p q } ^ { R } ( t ) - \alpha _ { M S } ) t } \mathrm { e } ^ { \mathrm { j } \Theta _ { p q } } } \end{array}
$$

由于 MS 和/或 MC 的移动，信道模型参数P(t)，τ,(t)，W(t)，α𝑇q(t)和αpq(t)需要使用适当的时变函数来表示。其中$\alpha _ { p q } ^ { T } ( t _ { 0 } )$ ， $\alpha _ { p q } ^ { R } ( t _ { 0 } )$ ， $\Delta \alpha _ { p q } ^ { T } ( t )$ 和 $\Delta \alpha _ { p q } ^ { R } ( t )$ 分别表示初始 AoD，初始AoA，AoD偏移和AoA偏移。下标 $p , \ q$ 分别表示宽带信道中的 $P$ 条路径中的一条和 $\varrho$ 条子路径中的一条。此时的AoD 和第一单射/簇 $S _ { 1 }$ 有关，AoA 来自最后的单射/簇 $S _ { P }$ 。此外， $\alpha _ { L O S } ^ { T }$ 和 $\alpha _ { L O S } ^ { R }$ 分别是基站(Base Station,BS)和 MS 的视距(Line of Sight,LoS)分量。本文假设BS 是固定的，而簇 $S _ { \mathrm { 1 } }$ ，以 $\alpha _ { \scriptscriptstyle 1 }$ 的方向和速度 $\nu _ { 1 }$ 运动。当本文考虑对于每个路径发生多次散射时，簇 $S _ { P }$ 表示具有移动方向αp和速度vp的最后一次反射。对于MS，αms是具有速度 $\nu _ { \ / { M S } }$ 的移动方向。 MC $S _ { \mathrm { 1 } }$ ，MC $S _ { P }$ 和 MS 的移动分别使用向量 $\vec { \nu } _ { 1 }$ ， $\vec { \nu } _ { { p } }$ 和 $\vec { \nu } _ { M S }$ 表示在图中。此外，假设BS 和 MC$S _ { 1 }$ 之间的初始距离 $D _ { B S } ^ { T } \left( t _ { 0 } \right)$ 以及MS和MC $S _ { P }$ 之间的初始距离$D _ { M S } ^ { R } \left( t _ { 0 } \right)$ 是已知的。BS 和 MS 之间的 LoS 分量的初始距离为DLos(to)。信道参数及定义通过表1给出。

![](images/0b14dccbb2ab7d5ce512a3b6724894f4656a45c50dcd4b2ea8ce5abea89c4118.jpg)  
图1基于IMT-A信道建模的时变参数示意图

基于MC $S _ { \mathrm { { \Phi } _ { \mathrm { { l } } } } }$ ，MC $S _ { P }$ 和 MS 的移动方向，BS，MC 和 MS之间的距离将随着时间 $\mathbf { \chi } _ { t } ^ { }$ 变化。通过考虑相对速度 MC $S _ { \mathrm { 1 } }$ 和MC $S _ { P }$ 的概念，本文可以假定MS 只相对于MC $S _ { P }$ 的运动。从信道测量获得距离 $D _ { B S } ^ { T } \left( t _ { 0 } \right)$ 、 $D _ { M S } ^ { R } \left( t _ { 0 } \right)$ 和 $D _ { L O S } ( t _ { 0 } )$ 后，则时间 $\mathbf { \Phi } _ { t }$ 处的时变距离可以表示为式(3)、(4)和(5)。图1中信道参数的定义如表1所示。

表1图1中信道参数的定义  

<html><body><table><tr><td>参数</td><td>定义</td></tr><tr><td>Ds(t)</td><td>BS 和 MC S之间的距离</td></tr><tr><td>Ds(1)</td><td>MS 和MC Sp之间的距离</td></tr><tr><td>DLos(t)</td><td>BS 和 MS之间LoS分量的距离</td></tr><tr><td>aTq(t），α(t）</td><td>与第p个簇/路径内的第q个子路径相关的</td></tr><tr><td></td><td>AoD 和AoA</td></tr><tr><td></td><td>LoSAoD 和LoSAoA</td></tr><tr><td>△apa(t），</td><td>AoD 偏移和AoA偏移</td></tr><tr><td>△ap(t)</td><td></td></tr><tr><td>V，v和vs</td><td>MCS，MCSp和MS的速度矢量</td></tr><tr><td>v，α</td><td>MCA的速度和MS的移动方向</td></tr><tr><td>Vp，αp</td><td>MCZ 的速度和MS 的移动方向</td></tr><tr><td>VMs’ ams</td><td>MS 的速度和MS 的移动方向</td></tr></table></body></html>

$$
\begin{array} { c } { { D _ { B S } ^ { T } \left( t \right) = } } \\ { { \sqrt { \left( D _ { B S } ^ { T } \left( t _ { 0 } \right) \right) ^ { 2 } + \left( \nu _ { 1 } t \right) ^ { 2 } - 2 \cdot D _ { B S } ^ { T } \left( t _ { 0 } \right) \cdot \nu _ { 1 } t \cdot \cos ( \pi + \alpha _ { p q } ^ { T } \left( t _ { 0 } \right) ) - \alpha _ { A } ) } } } \end{array}
$$

$$
D _ { M S } ^ { R } ( t ) =
$$

$$
\sqrt { \left( D _ { M S } ^ { R } ( t _ { 0 } ) \right) ^ { 2 } + \left( \nu t \right) ^ { 2 } - 2 \cdot D _ { M S } ^ { R } \left( t _ { 0 } \right) \cdot \nu t \cdot \cos ( \alpha _ { p q } ^ { R } ( t _ { 0 } ) - \alpha _ { \nu } ) }
$$

$$
D _ { L O S } ( t ) =
$$

$$
\sqrt { D _ { L O S } ^ { 2 } ( t _ { 0 } ) + ( \nu _ { M S } t ) ^ { 2 } - 2 \cdot D _ { L O S } ( t _ { 0 } ) \cdot \nu _ { M S } t \cdot \cos ( \alpha _ { M S } - \alpha _ { L O S } ^ { R } ) }
$$

为了推导出所需求解的时变角参数，本文设置四个辅助角，即图中的 $\beta _ { p q } ^ { T } ( t ) \ , \phi \ , \beta _ { p q } ^ { R } ( t )$ 和 $\theta$ 。应当注意，在图中，仅展示出了LoS 路径和第 $p$ 个散射传播路径。作为示例，簇 $S _ { \mathrm { 1 } }$ 和簇$S _ { P }$ 分别对应于第 $p$ 个散射路径的第一和最后的跳动簇。如果MC $S _ { 1 }$ 和/或 $\mathrm { M C } S _ { { P } }$ 是平稳的，则 MC $S _ { 1 }$ 的速度 $\nu _ { 1 }$ 或MC $S _ { P }$ 的速度 $\nu _ { { } _ { P } }$ 可以被设置为零。这不会影响该基于IMT-A 的信道建模中的时变信道参数的生成过程。

基于上述描述，可以通过以下步骤获得基于IMT-A信道建模中的信道参数的实现，如图2所示：

![](images/1e8241bc22e891ee5b73bdb19765d0e03ba86cb8944fd795ff955841461d7edf.jpg)  
图2基于IMT-A信道建模的信道参数实现流程图

# 2 时变信道参数分析

# 2.1 时变簇的生成

在高速铁路移动通信场境下，随着MS的移动，MS和BS之间的传播环境将改变。此外，还有一些移动散射体在环境内的移动也会对传播环境造成影响。因此，在行驶过程中，一些路径会消失，同时一些新的路径会出现。文献[6]提出了生灭过程的移动簇的建模方法。在时变情况下，簇只考虑在特定时间段上存在。随着时间的推移，新的簇出现即出生，并且保持一定的时间即存活，然后最终消失即死亡。应当注意的是，时变簇是指本文假设此高铁信道是一个多径信道，但与传统信道不同的是，这个多径信道的径数 $P$ 会随着时间变化，并且其状态转移连续，这就符合马尔可夫过程的连续状态转移的行为。所以，基于簇生成和重组的过程， $M C ( \varepsilon _ { M C } )$ 的移动以及在 $t _ { k - 1 }$ 和$t _ { k }$ 时刻的时间间隔中 $M C ( \varepsilon _ { M C } )$ 的移动引起的信道波动可以表

示为

$$
{ { \varepsilon } _ { \scriptscriptstyle R } } = { { \varepsilon } _ { \scriptscriptstyle M C } } + { { \varepsilon } _ { \scriptscriptstyle M S } }
$$

其中:

$$
\varepsilon _ { M C } = \int _ { t _ { k - 1 } } ^ { t _ { k } } R _ { M C } \big ( \big \| \vec { \nu } _ { 1 } \big \| + \big \| \vec { \nu } _ { P } \big \| \big ) \mathrm { d } t
$$

$$
\mathcal { E } _ { M S } = \int _ { t _ { k - 1 } } ^ { t _ { k } } \big ( \big \| \vec { \nu } _ { M S } \big \| \big ) \mathrm { d } t
$$

其中: $R _ { \scriptscriptstyle M C }$ 是移动簇所占的百分比。由于时间间隔较短暂，每个时间间隔 $t _ { k } - t _ { k - 1 }$ 可以被假设为匀速运动[7]。这使得(7)和(8)得到进一步简化

$$
\varepsilon _ { M C } = \big ( t _ { k } - t _ { k - 1 } \big ) R _ { M C } \big ( \nu _ { 1 } + \nu _ { P } \big )
$$

$$
\varepsilon _ { _ { M S } } = \big ( t _ { k } - t _ { k - 1 } \big ) \nu _ { _ { M S } }
$$

在任何 $t _ { k }$ 时刻可以通过在 $t _ { k - 1 }$ 时刻区分在先前CIR 中已经存在的新生成的簇和存活的簇。通过簇的生成速率 $\rho _ { 1 }$ 和新路径的复合速率 $\rho _ { { } _ { 2 } }$ 来描述这个马尔可夫过程。CIR实现中的簇的总数的期望也被定义为初始数，可表示为

$$
\operatorname { E } \left\{ P { \big ( } t { \big ) } \right\} = P { \big ( } t _ { 0 } { \big ) } = { \frac { \rho _ { 1 } } { \rho _ { 2 } } }
$$

观察这个CIR的时间序列，每个簇从 $t _ { k - 1 }$ 时刻的一个CIR到 $t _ { k }$ 时刻的随后的CIR保持概率为

$$
R ( \varepsilon _ { R } ) = \mathbf { e } ^ { - \rho _ { 1 } \rho _ { 2 } }
$$

因此，通过马尔可夫过程产生的多个新簇的期望为

$$
{ \displaystyle { \cal E } \left\{ P _ { n e w } \right\} } = \frac { \rho _ { 1 } } { \rho _ { 2 } } \Big ( 1 - { \sf e } ^ { - \rho _ { 1 } \rho _ { 2 } } \Big )
$$

经过演化后，两个簇之间的相关性通过 $\varepsilon _ { \scriptscriptstyle R }$ 量化。若 $\varepsilon _ { \scriptscriptstyle R }$ 的值较高，则会导致 $t _ { k - 1 }$ 时刻的祖先簇的属性与其在 $t _ { k }$ 时刻的继承簇之间的相关性降低。在NLoS 的城市宏小区(Urban Macro-cell,UMA)场景下，从原始IMT-A信道模型获取的初始簇数$P \big ( t _ { 0 } \big ) = 1 8$ ，并且簇的每次改变只考虑在相邻状态的值之间改变。基于上述情况，本文进行马尔可夫生灭过程的MATLAB仿真，仿真数据为： $\rho _ { 1 } = 0 . 6 / \mathrm { m } \ , \ \rho _ { 2 } = 0 . 0 3 / \mathrm { m } \ , \ \nu _ { _ { M S } } = 6 0 \mathrm { m } / \mathrm { s } \ , \ \nu _ { _ { 1 } } = 1 5 \mathrm { m } / \mathrm { s }$ （204号 $\nu _ { { P } } = 5 \mathrm { m } / \mathrm { s } \ , \ R _ { { M C } } = 0 . 3$ 。仿真得到的时变簇的数量 $P ( t )$ 如图3所示。

![](images/734676a14e63e5a2cfe01d2deec08e9f643928041960ce29511f20eccdbbab7a.jpg)  
图3时变簇的数量分布

从图3中可以看出，簇的初始值为18，簇的数量会随着时间而发生改变，并且一共有16、17、18、19、20这5种情况的数值。

# 2.2时变延迟

随着 MC（包括MC $S _ { \imath }$ 和MC $S _ { P }$ ）和 MS 的移动，第 $p$ 个簇的传播距离将是时变的。时变延迟 $\tau _ { p } \left( t \right)$ 的计算如下：

$$
\begin{array} { c } { { \tau _ { _ { p } } \left( t \right) = \left( \Delta D _ { _ { B S } } ^ { ^ T } + \Delta D _ { _ { M S } } ^ { ^ R } \right) / c + \tau _ { _ { p } } ^ { ~ \prime } \left( t \right) = } } \\ { { \left( D _ { _ { B S } } ^ { ^ T } \left( t \right) - D _ { _ { B S } } ^ { ^ T } \left( t _ { 0 } \right) \right) / c + \left( D _ { _ { M S } } ^ { ^ R } \left( t \right) - D _ { _ { M S } } ^ { ^ R } \left( t _ { 0 } \right) \right) / c + \tau _ { _ p } ^ { ~ \prime } \left( t \right) } } \end{array}
$$

其中： $\mathbf { \Psi } _ { c }$ 是空气中的光速， $\left( \Delta D _ { B S } ^ { T } + \Delta D _ { M S } ^ { R } \right)$ 是由 MS 和MC 的移动引起的传播距离的改变。 $\Delta D _ { B S } ^ { T } = D _ { B S } ^ { T } \left( t \right) - D _ { B S } ^ { T } \left( t _ { 0 } \right)$ 是 BS和MC$S _ { 1 }$ 之间的距离差， $\Delta D _ { M S } ^ { R } = D _ { M S } ^ { R } \left( t \right) - D _ { M S } ^ { R } \left( t _ { 0 } \right)$ 是MC $S _ { P }$ 和MS之间的距离差， $\tau _ { p } ^ { \prime } ( t )$ 是MC $S _ { \imath }$ 和MC $S _ { P }$ 之间的虚拟链路[8]的延迟，可以通过在 $t = t _ { k }$ 时刻使用一阶滤波算法计算得到[9]

$$
{ \tau _ { p } } ^ { \prime } \left( t _ { k } \right) = e ^ { \left( \left( t _ { k - 1 } - t _ { k } \right) / \kappa \right) } { \tau _ { p } } ^ { \prime } \left( t _ { k - 1 } \right) + \left( 1 - e ^ { \left( \left( t _ { k - 1 } - t _ { k } \right) / \kappa \right) } \right) \Gamma
$$

其中 $\Gamma$ 服从 $U \big ( { D _ { L O S } } \mathrm { ~ / ~ } c , \tau _ { \mathrm { m a x } } \big )$ 分布， $\kappa$ 是取决于虚拟链路和场景的相干性的参数， $\tau _ { \operatorname* { m a x } }$ 是最大延迟并且可以从文献[1]获得，例如， $\tau _ { \mathrm { m a x } } = 1 8 8 5 \mathrm { n s }$ 。

值得注意的是， $\tau _ { p } ^ { \prime } \left( t _ { 0 } \right)$ 可以计算为

$$
{ \tau _ { \dag } } ^ { \prime } \left( t _ { 0 } \right) = \tau _ { p } \left( t _ { 0 } \right) - \left( D _ { B S } ^ { T } \left( t _ { 0 } \right) + \Delta D _ { M S } ^ { R } \left( t _ { 0 } \right) \right) / c
$$

其中初始延迟 $\tau _ { _ { p } } \big ( t _ { 0 } \big )$ 从指数延迟分布中随机抽取，如在原始IMT-A 信道模型中解释的给定情形[8]。将式 $( 3 ) { \sim } ( 5 )$ 代入式(14),获得在不同瞬时时间 $t$ 的第 $p$ 个簇的时变延迟即 $\tau _ { p } \big ( t \big )$ 。然后通过减去最小延迟来对延迟进行归一化并按照降序排序。其中，归一化延迟将用于时变信道系数生成(见式(1))，但不用于簇的生成。

# 2.3 簇的时变功率

在时间 $t _ { 0 }$ 的第 $n$ 个簇的随机平均功率表示为 $W _ { p } \left( t _ { 0 } \right)$ ，它可以从原始IMT-A信道模型给出的参数产生[I]。因此，基于上面对时变延迟的计算，那么在时间 $\mathbf { \Psi } _ { t }$ 的第 $p$ 个簇的随机平均功率可以表示为

$$
W _ { p } ^ { \prime } \left( t \right) = \mathrm { e } ^ { \frac { \left( 1 - r _ { D S } \right) \left( \tau _ { p } \left( t \right) \right) } { r _ { D S } \cdot \sigma _ { D S } } } \times 1 0 ^ { - \frac { \xi _ { p } } { 1 0 } }
$$

其中： $r _ { D S }$ 是延迟分布比例因子， $\sigma _ { D S }$ 是延迟扩展， $\boldsymbol { \xi } _ { n }$ 是每簇阴影项（以dB为单位)，它们都可以从文献[1]中的表A1-7中获得。令所有簇功率的总功率等于1，簇的时变功率 $W _ { p } \left( t \right)$ 可以表示如下：

$$
W _ { p } \left( t \right) = W _ { p } ^ { \prime } \left( t \right) / \sum _ { p = 1 } ^ { P \left( t \right) } W _ { p } ^ { \prime } \left( t \right)
$$

# 2.4时变AoD

时变 AoD 的时变函数 $\alpha _ { p q } ^ { T } ( t )$ 可表示为

a）如果

$$
- \pi \le \alpha _ { p q } ^ { T } ( t _ { 0 } ) < 0 , - \pi \le \alpha _ { _ A } \le \alpha _ { p q } ^ { T } ( t _ { 0 } ) \cup \alpha _ { p q } ^ { T } ( t _ { 0 } ) + \pi \le \alpha _ { _ A } < \pi
$$

那么

$$
\alpha _ { p q } ^ { T } ( t ) = \alpha _ { p q } ^ { T } ( t _ { 0 } ) - \beta _ { p q } ^ { T } ( t )
$$

如果 $- \pi \le \alpha _ { p q } ^ { T } ( t _ { 0 } ) < 0 \ , \alpha _ { p q } ^ { T } ( t _ { 0 } ) \le \alpha _ { A } \le \alpha _ { p q } ^ { T } ( t _ { 0 } ) + \pi$ ，那么

$$
\alpha _ { p q } ^ { T } ( t ) = \alpha _ { p q } ^ { T } ( t _ { 0 } ) + \beta _ { p q } ^ { T } ( t )
$$

b）如果

$0 \leq \alpha _ { p q } ^ { T } ( t _ { 0 } ) < \pi , - \pi \leq \alpha _ { _ A } \leq \alpha _ { p q } ^ { T } ( t _ { 0 } ) \cup \alpha _ { p q } ^ { T } ( t _ { 0 } ) + \pi \leq \alpha _ { _ A } < \pi \ ,$ 那么

$$
\boldsymbol { \alpha } _ { p q } ^ { T } ( t ) = \boldsymbol { \alpha } _ { p q } ^ { T } ( t _ { 0 } ) + \boldsymbol { \beta } _ { p q } ^ { T } \left( t \right)
$$

如果 $0 \leq \alpha _ { p q } ^ { T } ( t _ { 0 } ) < \pi \ , \alpha _ { p q } ^ { T } ( t _ { 0 } ) \leq \alpha _ { A } \leq \alpha _ { p q } ^ { T } ( t _ { 0 } ) + \pi$ ，那么

$$
\alpha _ { p q } ^ { T } ( t ) = \alpha _ { p q } ^ { T } ( t _ { 0 } ) - \beta _ { p q } ^ { T } ( t )
$$

其中:

$$
\begin{array} { r l r } & { } & { \beta _ { p q } ^ { T } \left( t \right) = } \\ & { } & { \mathrm { a r c c o s } \frac { D _ { B S } ^ { T } \left( t _ { 0 } \right) + \nu _ { 1 } t \cos \left( \alpha _ { p q } ^ { T } \left( t _ { 0 } \right) - \alpha _ { A } \right) } { \sqrt { \left( D _ { B S } ^ { T } \left( t _ { 0 } \right) \right) ^ { 2 } + \left( \nu _ { 1 } t \right) ^ { 2 } + 2 D _ { B S } ^ { T } \left( t _ { 0 } \right) \nu _ { 1 } t \cos \left( \alpha _ { p q } ^ { T } \left( t _ { 0 } \right) - \alpha _ { A } \right) } } } \end{array}
$$

# 2.5时变AoA

a）如果

$- \pi \le \alpha _ { p q } ^ { R } ( t _ { 0 } ) < 0 , - \pi \le \alpha _ { \nu } \le \alpha _ { p q } ^ { R } ( t _ { 0 } ) \cup \pi + \alpha _ { p q } ^ { R } ( t _ { 0 } ) \le \alpha _ { \nu } < \pi ,$ 那么

$$
\alpha _ { p q } ^ { R } ( t ) = \alpha _ { \nu } - \beta _ { p q } ^ { R } \left( t \right) \pm \pi
$$

如果 $- \pi \le \alpha _ { p q } ^ { R } ( t _ { 0 } ) < 0 \ , \alpha _ { p q } ^ { R } ( t _ { 0 } ) \le \alpha _ { \nu } < \pi + \alpha _ { p q } ^ { R } ( t _ { 0 } )$ ，那么

$$
\alpha _ { p q } ^ { R } ( t ) = \alpha _ { \nu } + \beta _ { p q } ^ { R } \left( t \right) \pm \pi
$$

b）如果

$$
\begin{array} { r } { 0 \leq \alpha _ { p q } ^ { R } \left( t _ { 0 } \right) < \pi \mathrm { , } - \pi \leq \alpha _ { \nu } \leq \alpha _ { p q } ^ { R } \left( t _ { 0 } \right) \cup \pi + \alpha _ { p q } ^ { R } \left( t _ { 0 } \right) \leq \alpha _ { \nu } < \pi \mathrm { , } } \end{array}
$$

那么

$$
\alpha _ { p q } ^ { R } ( t ) = \alpha _ { \nu } + \beta _ { p q } ^ { R } \left( t \right) \pm \pi
$$

如果 $\begin{array} { r } { 0 \leq \alpha _ { p q } ^ { R } ( t _ { 0 } ) < \pi \ , \alpha _ { p q } ^ { R } ( t _ { 0 } ) - \pi \leq \alpha _ { \nu } < \alpha _ { p q } ^ { R } ( t _ { 0 } ) } \end{array}$ ，那么

$$
\alpha _ { p q } ^ { R } ( t ) = \alpha _ { \nu } - \beta _ { p q } ^ { R } \left( t \right) \pm \pi
$$

其中

$$
\begin{array} { r l r } & { } & { \beta _ { p q } ^ { R } \left( t \right) = } \\ & { } & { \mathrm { a r c c o s } \frac { \nu t - D _ { M S } ^ { R } \left( t _ { 0 } \right) \cos \left( \alpha _ { \nu } - \alpha _ { p q } ^ { R } \left( t _ { 0 } \right) \right) } { \sqrt { \left( D _ { M S } ^ { R } \left( t _ { 0 } \right) \right) ^ { 2 } + \left( \nu t \right) ^ { 2 } - 2 D _ { M S } ^ { R } \left( t _ { 0 } \right) \nu t \cos \left( \alpha _ { \nu } - \alpha _ { p q } ^ { R } \left( t _ { 0 } \right) \right) } } } \end{array}
$$

应当注意，式 $( 2 4 ) { \sim } ( 2 7 )$ 中的“ $\pm \pi$ ”是校正器，以确保结果在范围[-π,π)。

# 3 统计性质

# 3.1时变空时域互相关函数

对于所提出的基于IMT-A信道建模系统，空间时变CCF不仅取决于 BS 处的天线间隔 $\Delta \delta _ { _ T }$ 和 MS 处的天线间隔 $\Delta \delta _ { _ R }$ ，还取决于时间 $\scriptstyle t _ { \circ }$ 因此，该信道建模的空间CCF被称为局部空间CCF，表示为[7]

$$
R _ { h } \left( t , \Delta \delta _ { { \scriptscriptstyle T } } , \Delta \delta _ { { \scriptscriptstyle R } } \right) =
$$

$$
\left( 1 / Q \right) \sum _ { q = 1 } ^ { Q } E \left\{ W _ { p } \left( t \right) e ^ { j k \Delta \delta _ { T } \sin \left( \alpha _ { p q } ^ { T } \left( t \right) \right) } e ^ { j k \Delta \delta _ { R } \sin \left( \alpha _ { p q } ^ { R } \left( t \right) \right) } \right\}
$$

# 3.2 时变自相关函数

考虑到马尔可夫生灭过程，簇从 $t - \Delta t$ 到 $t$ 存活的概率表示为 $R ^ { \prime } = e ^ { - \rho _ { 2 } \left( \nu _ { _ { M S } } \Delta t + R _ { _ { M C } } \left( \nu _ { 1 } + \nu _ { P } \right) \Delta t \right) }$ 。因此，第 $p$ 个簇的非平稳信道模型的局部时间ACF可以表示为

$$
r _ { n } \left( t , \Delta t \right) = E \left\{ h _ { _ { p } } \left( t \right) h _ { _ { p } } ^ { ^ { * } } \left( t \right) \right\} =
$$

$$
R ^ { \prime } \times \left( 1 / Q \right) \sum _ { q = 1 } ^ { Q } E \big \{ W _ { p } \left( t \right) X \left( t , \Delta t \right) Y \left( t , \Delta t \right) Z \left( t , \Delta t \right) \big \}
$$

其中:

$$
X \left( t , \Delta t \right) = \mathrm { e } ^ { \mathrm { j } k \delta _ { R } \sin \left( \alpha _ { p q } ^ { R } \left( t \right) \right) - \sin \left( \alpha _ { p q } ^ { R } \left( t + \Delta t \right) \right) }
$$

$$
Y \left( t , \Delta t \right) = { \mathrm e } ^ { \mathrm { j } k \delta _ { T } \sin \left( \alpha _ { p q } ^ { T } \left( t \right) \right) - \sin \left( \alpha _ { p q } ^ { T } \left( t + \Delta t \right) \right) }
$$

$$
Z \left( t , \Delta t \right) = \mathrm { e } ^ { - \mathrm { j } k \nu \cos \left( \alpha _ { p q } ^ { R } \left( t \right) - \alpha _ { \nu } \right) \left( t \right) } \times \mathrm { e } ^ { \mathrm { j } k \nu \cos \left( \alpha _ { p q } ^ { R } \left( t + \Delta t \right) - \alpha _ { \nu } \right) \left( t + \Delta t \right) }
$$

# 3.3 平稳间隔

可以使用平均功率延迟分布(APDP)计算平稳间隔，表示为

$$
\bar { W } _ { h } \left( t , \Delta t \right) = \frac { \sum _ { k } ^ { k + N - 1 } \left| h \left( t _ { k } , \tau \right) \right| ^ { 2 } } { N }
$$

其中 $l ^ { \prime }$ 是相关系数的给定阈值，具体值将在后面的仿真中给出。

其中： $\begin{array} { r } { h \big ( t _ { k } , \tau \big ) = \sum _ { p = 1 } ^ { P } h _ { p } \big ( t _ { k } \big ) \delta \big ( \tau - \tau _ { p } \big ) } \end{array}$ ， $N$ 是要平均的功率延迟分布的数量， $t _ { k }$ 是第 $k$ 个下降的时间。两个APDP之间的相关系数可以计算为

$$
l \left( t _ { k } , \Delta t \right) = \frac { \int \overline { { W } } _ { h } \left( t _ { k } , \tau \right) \overline { { W } } _ { h } \left( t _ { k } + \Delta t , \tau \right) d \tau } { \operatorname* { m a x } \left\{ \int \overline { { W } } _ { h } \left( t _ { k } , \tau \right) ^ { 2 } d \tau , \int \overline { { W } } _ { h } \left( t _ { k } + \Delta t , \tau \right) ^ { 2 } d \tau \right\} }
$$

然后将平稳间隔计算为

# 4.1时变空时域互相关函数

![](images/a38bfb5a81792ba001f716d5596876d7d20aafd46c0bc8c4f97e2534a3f86bae.jpg)  
图4所提出的基于IMT-A信道建模的三维局部空间CCF绝对值

# 4 仿真分析

接下来对所提出的高铁移动通信场景下的基于IMT-A信道建模的统计性质进行MATLAB仿真分析。

在这里，本文使用NLoS的UMA场景和主要仿真参数如下： $\alpha _ { p q } ^ { T } ( t _ { 0 } ) =$ random, $D _ { B S } ^ { T } \left( t _ { 0 } \right) = 1 0 0$ ， $\alpha _ { 1 } ^ { \phantom { + } } = 1 5 ^ { \circ }$ ， $\nu _ { \mathrm { { } _ { 1 } } } = 3 0 \mathrm { { m } / \mathrm { { s } } }$ ， $\alpha _ { p q } ^ { R } ( t _ { 0 } )$ $\ O =$ random， $D _ { M S } ^ { R } \left( t _ { 0 } \right) = 1 5 0 \mathrm { m }$ ， $\nu { = } 2 0 \mathrm { m / s }$ ， $\alpha _ { _ \nu } { = } 1 2 0 ^ { \circ }$ 0

$$
T _ { h } \left( t _ { k } \right) = \operatorname* { m a x } \left\{ \Delta t \ : \vert _ { l \left( t _ { k } , \Delta t \right) \geq l ^ { \prime } } \right\}
$$

图4展示了所提出的基于IMT-A信道建模的三维(3D)局部空间CCF的绝对值。从图4可以看出，随着MS处的天线间距$\Delta \delta _ { _ R }$ 的逐渐增大，局部空间互相关函数CCF呈现下降趋势，并且是伴随着有一定周期性波动的下降形式，波动的幅度也随着MS 处的天线间隔的增大而明显减小，最后趋近于平缓。这是由于该高速移动下的信道的非平稳特性引起的。

图5表示从图4截取的5个不同瞬时即 $\scriptstyle t = 0 \mathrm { s }$ 、 $_ { t = 1 \mathrm { s } }$ 、 $t { = } 2 \mathrm { s }$ ，$\scriptstyle { t = 3 \mathrm { s } }$ 、 $\scriptstyle t = 4 \mathrm { s }$ 的局部空间互相关函数的绝对值。

![](images/f18ab3db4b4693e4656ac69382c18c93cc6d0f1cf108019f658655d6a7c94944.jpg)  
图5不同瞬时的局部空间CCF的绝对值

从图中可以看出，虽然局部空间CCF是随着MS处的天线间距的增大而下降，但是在不同的时刻，波动的幅度并不相同。总的来看，CCF峰值整体是平缓略有增加的趋势，并且时间越长幅度越小，最后波动趋向于平缓。以上正是由于非平稳性引起的。结合图4和5的分析，表明该高速移动下基于IMT-A的信道模型有很明显的非平稳性。

# 4.2时变自相关函数

继续使用NLoS的UMA场景进行仿真，以下参数用于仿真局部时间自相关函数ACF: $\alpha _ { p q } ^ { T } ( t _ { 0 } ) =$ random, $D _ { B S } ^ { T } \left( t _ { 0 } \right) = 1 0 0$ $\alpha _ { _ 1 } = 1 5 ^ { \circ } , \quad \nu _ { _ 1 } = 3 0 \mathrm { m } / \mathrm { s } , \quad \alpha _ { _ { p q } } ^ { R } ( t _ { 0 } ) = \mathrm { r a n d o m } , \quad D _ { _ { M S } } ^ { R } \left( t _ { 0 } \right) = 7 0 \mathrm { m } , \quad \alpha _ { _ { \nu } } = - 1 5 ^ { \circ } ,$ $1 4 0 ^ { \circ } , \quad _ { \nu _ { _ P } } = 5 \mathrm { m / s } , \quad \alpha _ { _ { M S } } = 1 2 0 ^ { \circ } , \quad _ { \nu _ { _ { M S } } } = 2 0 \mathrm { m / s } \circ$ （204号

图6表示NLoSUMA场景的基于IMT-A信道建模的3D局部时间自相关函数的绝对值。类似于局部空间互相关函数，由于时变AoD和AoA，局部时间自相关函数的绝对值随时间t变化。随着时间差的逐渐增大，局部时间自相关函数ACF呈现下降趋势，并且有一定周期性波动的下降形式，波动的幅度也随着时间差的增大而明显减小，最后趋近于平缓。

图7表示从图6截取的6个不同瞬时即 $\scriptstyle t = 0 \mathrm { s }$ 、 $t { = } 1 \mathrm { s }$ 、 $t { = } 2 \mathrm { s }$ ，$\scriptstyle { t = 3 \mathrm { s } }$ 、 $\scriptstyle t = 4 \mathrm { s }$ 和 $\scriptstyle t = 5 \mathrm { s }$ 的局部时间自相关函数ACF的绝对值。本文可以看出，局部时间自相关函数是随着时间差的增大而下降，并且在不同的时刻，波动的幅度并不相同。并且有随着时间的增大，波动有变大的趋势。在时间差为0.25s时，不同的时刻的ACF基本都急剧下降了 $80 \%$ 以上。随着时间差的增大，波动趋向于平缓。从图6和7同样证实了该高速移动下基于IMT-A信道模型的非平稳性，仿真结果再次匹配了分析结果。

![](images/feec106d09dbc92ea6cfef3e7c37ac5c3bdb2ae18cc7ed437f0edfb0d5df3c35.jpg)  
图6基于IMT-A信道建模的三维局部时间ACF绝对值

![](images/371fa9803a9643f94a13ee9e8fc523b537bc28983477ebbad197dd878f8916ef.jpg)  
图7不同瞬时的局部时间ACF的绝对值

# 4.3 平稳间隔

图8显示了该基于IMT-A信道建模中速度为 $\scriptstyle \nu = 9 0 \mathrm { m / s }$ 和速度为 $\scriptstyle \nu = 2 0 \mathrm { m / s }$ 时的平稳间隔的经验补充累积分布函数(CCDF)[10]的结果图，其他的仿真参数为： $f _ { c } { = } 9 3 0 \mathrm { M H z }$ ， $l ^ { \prime } = 0 . 8$ 。对于该信道建模， $D _ { B S } ^ { T } \left( t _ { 0 } \right) = 1 0 0$ ， $\nu _ { \mathrm { { } _ { 1 } } } = 0 \mathrm { { m } / \mathrm { { s } } }$ ， $D _ { M S } ^ { R } \left( t _ { 0 } \right) = 7 0 \mathrm { m }$ ， $\alpha _ { _ \nu } { = } 0 ^ { \circ }$ 。

![](images/6520b8d33c14e20e3569199c38f9f493a76f0dcddd6d1740b302b6ae62e4ee32.jpg)  
图8速度分别为 $\scriptstyle \nu = 9 0 \mathrm { m } / \mathrm { s }$ 和 $\scriptstyle \nu = 2 0 \mathrm { m } / \mathrm { s }$ 的CCDF

从图8可得，速度为 $\scriptstyle \nu = 9 0 { \mathrm { m / s } }$ 时，本文所提出的信道建模的平稳间隔的CCDF概率如下：当概率为0.8时对应的时间间隔为 $0 . 0 0 9 \mathrm { s }$ ，以及概率为0.6时对应的时间间隔为0.02s；速度为 $\scriptstyle \nu = 2 0 \mathrm { m } / \mathrm { s }$ 时，其平稳间隔的CCDF 的情况是：当概率为0.8时对应的时间间隔为0.018s，以及概率为0.6时对应的时间间隔为0.06s。通过以上两者数据的对比可以看出，速度越大时，相关性越小，从而证明了所提出的基于IMT-A的信道建模方法的可行性，符合客观实际情况。

# 5 结束语

本文提出了一种高速铁路移动通信场景下基于IMT-A 信道的建模方法，使用马尔可夫过程建模时变簇的生灭过程，并基于此信道模型，推导和分析了其重要的统计特性，即局部空间CCF和局部时间ACF及平稳间隔。对该信道建模中的CCF、ACF和平稳间隔的MATLAB进行了仿真，发现其具有非平稳特性，验证了本文所提信道建模方法的可行性。

# 参考文献：

[1]ITU-R M.2135-1. Guidelines for evaluation of radio interface technologies for IMT-Advanced [EB/OL].2009. http://ccsa. org. cn.   
[2]Yang J,Ai B,Guan K,et al. Quasi-stationarity regions analysis for channel in composite high-speed railway scenario [C]//Proc of IEEE International Symposium on Antennas and Propagation.2016:1699-1700.   
[3]Lin S,Kong L,He L,et al.Finite-state Markov modeling for high-speed railway fading channels [J]. IEEE Antennas & Wireless Propagation Letters, 2015,14: 954-957.   
[4] Matolak D W. V2V communication channels: state of knowledge,new results,and what's next [M]// Communication Technologies for Vehicles. Berlin: Springer, 2013:1-21.   
[5] Xuan L,Chao S,Ai B,et al.Finite-state Markov modeling of fading channels:a field measurement in high-speed railways [Cl// Proc of IEEE//CIC International Conference on Communications in China. 2013: 577-582.   
[6]Molisch AF,Tufvesson F.Propagation channel models for next-generation wireless communications systems [J].IEICE Trans on Communications, 2014,E97.B (10): 2022-2034.   
[7]Wu S,Wang CX,Haas H,et al.ANon-Stationary Wideband Channel Model for Massive MIMO Communication Systems [J]. IEEE Trans on Wireless Communications,2015,14 (3): 1434-1446.   
[8] Molisch A F,Karttnen A,Hur S,et al. Spatially consistent pathloss modeling for millimeter-wave channels in urban environments [C]// Proc of European Conference on Antennas and Propagation.2016:1-5.   
[9]Wu S,Wang C X,Aggoune E HM,et al.A non-stationary 3-D wideband twin-cluster model for 5G massive MIMO channels [J].IEEE Journal on Selected Areas in Communications,2014,32 (6):1207-1218.   
[10] Guan K,Ai B,Fricke A,et al. Excess propagation loss modeling of semiclosed obstacles for inteligent transportation system [J].IEEE Trans on Intelligent Transportation Systems,2016,17(8):2171-2181.