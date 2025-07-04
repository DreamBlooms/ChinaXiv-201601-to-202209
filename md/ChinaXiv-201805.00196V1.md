# 基于信息能量同传的异构小蜂窝网络能效优化

樊自甫，李悦宁，胡敏，文陈陈(重庆邮电大学 下一代网络应用技术研究所，重庆 400065)

摘要：研究无线信息和能量协同传输(simultaneous wirelessinformationand power transfer，SWIPT)异构小蜂窝网络的能效优化问题。保证小蜂窝用户和宏用户通信质量、小蜂窝用户能量采集和小蜂窝基站传输功率等约束下，为实现小蜂窝系统下行能效的最大化，对小蜂窝基站发射功率和小蜂窝用户端功率分流系数进行联合优化。该问题属于非凸优化问题，通过变量替换对原问题作等价转换，然后采用基于拉格朗日乘子的次梯度算法求解。计算机仿真结果表明，该联合优化算法简单有效。

关键词：无线信息和能量协同传输；异构小蜂窝网络；能效；功率分流；凸优化 中图分类号：TN doi:10.3969/j.issn.1001-3695.2017.07.0662

# Energy efficiency optimization of heterogeneous small cellular networks with simultaneous wireless information and power transfer

Fan Zifu,Li Yuening,Hu Min, Wen Chenchen (InstituteforApplicationTechnologyoftheNextGenerationNetworks,Chongqing UniversityofPosts&Telecommunications, Chongqing 400065, China)

Abstract:Researchonenergy eficiencyoptimizationofsimultaneous wireless informationand power ransferin heterogeneous smallcellarnetworks.Iorder tomaximize theenergy eficiencyofthedownlinkcellularsystembyjointlydesigningtransmit beamforming vectorand receivepower splitingratio under both smallcellular users'communication qualityand the collected energy,andthetransmisionpowerofthesmallcellbasestationconstraints.Thepoblemelongstotheonconvexoptimization problem,andtheequivalentproblemis tansformedbythevariablesubstitution,andthenthesubgradientiterationalgorithm basedontheLagrange multiplierisusedtosolvetheproblem.Theresultsofcomputersimulationshowthatejointoptimization algorithm is simple and effective.

Key Words:simultaneous wireless informationand power transfer; heterogeneous smallcellular network;energy effciency; power splitting; convex optimization

# 0 引言

随着移动互联网和物联网的快速发展，通信网络能耗日益加剧，为解决移动终端能量受限问题，SWIPT受到了学术界和工业界等众多领域的广泛关注[I]。当前，SWIPT通常以电磁波辐射的方式实现，辐射性的电磁波不仅可以作为信息传输的载体进行无线信息传输，也可以作为能量传输的载体实现无线能量传输，且受外界条件的干扰较小[2]。

众所周知，在SWIPT系统中同一接收机不可能同时实现能量采集和信息接收，因此出现了信息接收机和能量接收机采用不同天线来分别接收信息和采集能量的分离结构，及通过时间切换（time-switching）和功率分流（power-spliting）的共用天线的共存接收机结构[3]。后者在尺寸上可以做得更小，因此本研究采用基于功率分流的共用天线接收机架构。在此架构下，接收端将收到的信号分成两个完全独立的流，分别用于能量采集和信息解码。

目前，对SWIPT的研究已有大量成果，从最初研究点到点的单天线系统，到现在对多天线系统的研究。但是，核心问题依然是信息解码和能量采集之间的平衡，且大多集中在对吞吐量、传输功率和终端能量采集的研究[4,5,6]，对SWIPT系统能效的研究较少。 $\mathrm { N g }$ 等[7]在点到点单天线OFDMSWIPT系统中研究了基于资源分配的能效问题，由于载波功率分配与功率分流系数相互耦合，作者采用Dinkelbach方法提出了一种有效的资源分配迭代算法。Sudha 等[8]研究了基于SWIPT的两层异构小蜂窝网络下行资源分配问题，同时考虑时间切换和功率分流两种方式，在保证宏用户通信质量的前提下，联合优化小蜂窝用户的吞吐量和能量采集率。在此基础上，Sheng 等[9]考虑多个小蜂窝附加在一个宏蜂窝上的两层多输入单输出（multiple-input single-output,MISO）异构模型，信息接收机和能量接收机分别通过信息信道和能量信道接收信息和采集能量。不同于文献[7\~9]，本文研究MISOSWIPT异构小蜂窝网络下行资源分配问题，在保证小蜂窝用户和宏用户通信质量、小蜂窝用户能量采集和小蜂窝基站传输功率等约束下，联合优化小蜂窝基站发射功率和小蜂窝用户端功率分流系数，以最大化小蜂窝系统下行能效。为使问题在数学上易于处理，首先通过变量替换对原问题做等价转换，然后采用基于拉格朗日乘子的次梯度算法求解。

# 1 系统模型

研究大规模多输入单输出小蜂窝同信道部署在传统宏蜂窝上的下行数据和能量传输，如图1所示。其中，实线表示理想信号，虚线表示干扰信号。小蜂窝基站配有 $N ( N > K )$ 根天线，小蜂窝区域内有 $K$ 个单天线小蜂窝用户和一个单天线宏用户，且用户端天线都是无源的。假设将小蜂窝基站到小蜂窝用户间的下行信道考虑为Rician 衰落模型，且工作在时分双工（timedivision duplex,TDD）模式下。

![](images/a358b12d336a45cfd2431ac2622f4a54d7b6eb83d45ba56a664290c441db55df.jpg)  
图1基于功率分流接收机的多用户MISOSWIPT系统模型

基站发射的复基带信号 $x$ 表示为

$$
\pmb { x } = \sum _ { k = 1 } ^ { K } \nu _ { k } s _ { k }
$$

其中: $\boldsymbol { \nu } _ { \boldsymbol { k } }$ 表示小蜂窝基站对小蜂窝用户 $k$ 的发射波束成形矢量，$s _ { k }$ 表示对应的数据符号。假设小蜂窝基站和小蜂窝用户之间的信道为平坦衰落信道，表示为 $\pmb { h }$ 。在理想情况下， $s _ { k }$ 表示独立同分布的圆周对称复高斯随机变量，满足 $\pmb { S } _ { k } \sim \pmb { C } \pmb { N } \left( 0 , 1 \right)$ 。因此，功率分流前，小蜂窝用户 $k$ 收到的信号为

$$
y _ { k } = h _ { k } ^ { H } x + m _ { k } + n _ { k } , k = 1 , 2 , . . . , K
$$

其中: $m _ { k } \sim \pmb { C N } \left( 0 , \mathbf { \mathfrak { s } } _ { \mathbf { k } } ^ { 2 } \right)$ 为宏基站对小蜂窝用户 $k$ 的干扰信号，$n _ { k } \sim \bf C N _ { \mathrm { \ell } } ( 0 , 0 _ { k } ^ { 2 } )$ 为接收端天线噪声。接收端使用功率分流器将接

收信号功率的 $\rho ( 0 < \rho < 1 )$ 部分用于信息解码， $\rho$ 为功率分流系数，剩余部分用于能量采集。因此，小蜂窝用户 $k$ 用于信息解码的信号可表示为

$$
y _ { k } ^ { I D } = \sqrt { \rho _ { k } } \Bigg ( h _ { k } ^ { H } \sum _ { j = 1 } ^ { K } \nu _ { j } s _ { j } + m _ { k } + n _ { k } \Bigg ) + z _ { k } , \forall k
$$

其中： $z _ { k } \sim C N \left( 0 , \delta _ { \mathrm { k } } ^ { 2 } \right)$ 是信息解码引入的额外噪声。信息解码部分的信号干扰和噪声比（signal to interference-plus-noise ratio,SINR）为

$$
\mathrm { S I N R } _ { k } = \frac { \rho _ { k } \left\| h _ { k } ^ { H } \nu _ { k } \right\| ^ { 2 } } { \sum _ { j \neq k } \rho _ { k } \left\| h _ { k } ^ { H } \nu _ { j } \right\| ^ { 2 } + \rho _ { k } \varepsilon _ { k } ^ { 2 } + \rho _ { k } \sigma _ { k } ^ { 2 } + \delta _ { k } ^ { 2 } }
$$

小蜂窝用户 $k$ 用于能量采集的信号可表示为

$$
y _ { k } ^ { E H } = \sqrt { 1 - \rho _ { k } } ( h _ { k } ^ { H } \sum _ { j = 1 } ^ { K } \nu _ { j } s _ { j } + m _ { k } + n _ { k } ) , \forall k
$$

值得注意的是，能量采集过程引入的噪声具有不可控、能量小等特点，可忽略不计[10]。那么，小蜂窝用户 $k$ 采集到的能量可表示为

$$
E _ { k } = \zeta _ { k } ( 1 - \rho _ { k } ) ( \sum _ { j = 1 } ^ { K } \left\| h _ { k } ^ { H } \nu _ { j } \right\| ^ { 2 } + \varepsilon _ { k } ^ { 2 } + \sigma _ { k } ^ { 2 } ) ~
$$

其中： $\zeta _ { k } \in ( 0 \mathrm { ~ 1 ) }$ 表示小蜂窝用户将接收到的射频信号转换成直流信号的转换效率。

# 2 优化问题建模

本研究旨在最大化下行MISOSWIPT异构小蜂窝系统的能效，这里将能效定义为小蜂窝系统下行和速率与小蜂窝基站总能耗的比值[II]，即系统消耗单位能量所传送的比特数。由式（4)可得小蜂窝用户 $k$ 的速率：

$$
R _ { k } \mathbf { \Theta } ^ { \otimes } \mathbf { { W } } \log ( 1 + \mathrm { { S I N R } } _ { k } ) , \forall _ { k }
$$

因此，可得小蜂窝系统的下行和速率：

$$
R \Subset C _ { k = 1 } ^ { K } R _ { k }
$$

另外，将小蜂窝基站总能耗定义为由发射能耗和静态能耗两部分组成，发射能耗表示基站发射基带信号消耗的能量，静态能耗为基站发射信号过程中各器件所消耗的能量。因此，将系统总能耗定义如下

$$
P \circledast P _ { c } + \sum _ { k = 1 } ^ { K } \left\| \nu _ { k } \right\| ^ { 2 }
$$

其中： $p _ { c }$ 表示静态能耗，第二项表示信号发射能耗。那么，问题建模如下：

$$
\begin{array} { r l } & { \quad \displaystyle \sum _ { \lbrace \nu _ { k } , \rho _ { k } \rbrace } ^ { \mathrm { m a x } } \sum _ { k = 1 } ^ { K } R _ { k } \Biggl \langle ( P _ { c } + \sum _ { k = 1 } ^ { K } \| r _ { k } \| ^ { 2 } ) \Biggr . } \\ & { \quad  \ s { t } _ { k } \cdot \int _ { \mathbb { R } ^ { I } } \| r _ { k } \| ^ { 2 } \leq P _ { I o t a l } } \\ & { \quad c _ { 1 } \cdot S = \| r _ { k } \| _ { k } \geq r _ { I } , \forall k } \\ & { \quad c _ { 2 } : \operatorname { S m R } _ { k } \geq \gamma _ { k } , \forall k } \\ & { \quad c _ { 3 } : E _ { k } \geq \epsilon _ { k } , \forall k } \\ & { \quad c _ { 4 } : \sum _ { k = 1 } ^ { K } \| g _ { k } ^ { H } \nu _ { k } \| ^ { 2 } \leq \eta } \\ & { \quad c _ { 5 } : 0 \leq \rho _ { k } \leq 1 , \forall k } \end{array}
$$

其中： $C _ { 1 }$ 表示小蜂窝基站发射功率约束， $C _ { 2 }$ 、 $C _ { 4 }$ 分别表示小蜂窝用户和宏用户的通信质量约束， $C _ { 3 }$ 、 $C _ { 5 }$ 分别表示小蜂窝用

户能量采集和功率分流系数约束， ${ \pmb g } _ { k } ^ { H }$ 表示小蜂窝基站到宏用户的信道增益。由分析可知，上述问题属于非凸非线性分式规划[12]，难以直接求解。

# 3 问题转换与求解

考虑到异构小蜂窝网络采用低功耗的发射节点，且信号在传输过程中会发生显著衰减，这给移动终端的能量采集造成了很大困难。因此，在保证移动终端正常通信的前提下，基站应尽可能地降低算法开销，从而保证移动端采集到更多的能量。那么，本研究采用迫零波束成形技术[13]（zero-forcingbeamforming,ZFBF）对发射信号进行处理，在消除用户间干扰的同时，ZFBF可以简化发射机的设计。

与此同时，本小节通过数学构造法对原问题作等价转换，使其在数学处理上得到简化。

命题1令 $H _ { k } \ @ [ h _ { 1 } , . . . , h _ { k - 1 } , h _ { k + 1 } , . . . , h _ { K } ]$ ， $U _ { k }$ 为 $\boldsymbol { H } _ { \boldsymbol { k } } ^ { H }$ 零空间的 正交基，再令 $\Omega _ { V E } ^ { q } @ U _ { k } U _ { k } ^ { H } { h _ { k } ^ { } / } P U _ { k } U _ { k } ^ { H } { h _ { k } ^ { } P }$ ， $f _ { k } \Subset P h _ { k } ^ { H } \sqrt [ \mathscr { V } _ { k } P ^ { 2 }$ ， $\nu _ { k } = \sqrt { p _ { k } } \% , \forall k$ 。则问题式（10）可转换为

$$
\begin{array} { r l } & { \frac { \rho _ { k } } { k _ { 2 } } \mathrm { W i g } _ { k \_ + } ( 1 + \frac { \rho _ { k } p _ { k } f _ { k } } { \rho _ { k } \varepsilon _ { k } ^ { 2 } + \rho _ { k } } \varepsilon _ { k } ^ { 2 } \frac { 1 } { \rho _ { k } ^ { 2 } } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \times \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \times \quad \quad } \\ &  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad  \end{array}
$$

显然，在目标函数中优化变量 $p _ { k }$ ， $\rho _ { k }$ 相互耦合，且是两式相除的形式。因此，问题（11）仍属于非凸优化问题，首先使用分式规划将目标函数转换为减的形式，然后采用基于拉格朗日乘子的次梯度算法将问题（11）转换为无约束优化问题。

引理1假设 $f ( x )$ 、 $g ( x )$ 是连续可微函数，且 $g ( x ) > 0$ ，约束集 $S$ 是紧凑型函数，那么

$$
\begin{array} { r l } {  { \operatorname* { m a x } _ { x } \ f ( x ) / g ( x ) } ~ } & { { } } \\ { \ s . t . \ c _ { i } ( x ) \leq 0 , \forall i = 1 , . . . , I } & { { } } \\ { \ h _ { j } ( x ) = 0 , \forall j = 1 , . . . , J } \end{array}
$$

可通过求解问题式（13）取得最优解，即

$$
F ( \lambda ) = \operatorname* { m a x } _ { x \in S } \left\{ f ( x ) - \lambda g ( x ) \right\}
$$

下面的工作是找到最优的 $\lambda ^ { * }$ ，使得 $F ( \lambda ) { = } 0$ ，从而得到问题式（12）的最优解，即

$$
{ x ^ { * } } = \arg \operatorname* { m a x } _ { x \in S } { \left\{ { f ( x ) - \lambda } ^ { * } g ( x ) \right\} }
$$

现对问题式（11）的约束条件 $C _ { 2 }$ 和 $C _ { 3 }$ 作如下处理，令

$$
l _ { 1 } ( \rho _ { k } ) \circledast \gamma _ { k } ( \rho _ { k } \sigma _ { k } ^ { 2 } + \delta _ { k } ^ { 2 } ) \Big / \rho _ { k } f _ { k }
$$

$$
l _ { 2 } ( \rho _ { k } ) \circledast \left( \frac { e _ { k } } { \zeta _ { k } \left( 1 - \rho _ { k } \right) } - \sigma _ { k } ^ { 2 } \right) \bigg / f _ { k }
$$

则问题式（11）等价于

$$
\begin{array} { r l } & { \quad \displaystyle \sum _ { k = 0 } ^ { \bar { K } } w \log ( 1 + \frac { \rho _ { k } p _ { k } f _ { k } } { \rho _ { k } \varepsilon _ { k } ^ { 2 } + \rho _ { k } \sigma _ { k } ^ { 2 } } + \frac { 2 } { k } ) } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \kappa : \quad \frac { \bar { K } } { k = 1 } \rho _ { k } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \times } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \times } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ &  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \end{array}
$$

那么，问题式（17）的拉格朗日对偶函数为

$$
\begin{array} { l } { { { \cal L } ( p _ { k } , \rho _ { k } , \alpha , \beta , \nu ) = \displaystyle \sum _ { k = 1 } ^ { K } W \log ( 1 + \frac { \rho _ { k } p _ { k } f _ { k } } { \rho _ { k } \varepsilon _ { k } ^ { 2 } + \rho _ { k } \sigma _ { k } ^ { 2 } + \delta _ { k } ^ { 2 } } ) } } \\ { { \quad \quad \quad - \lambda _ { k } ( p _ { c } + \displaystyle \sum _ { k = 1 } ^ { K } p _ { k } ) - \alpha _ { k } ( \displaystyle \sum _ { k = 1 } ^ { K } p _ { k } - p _ { \mathrm { t o t a l } } ) } } \\ { { \quad \quad \quad - \displaystyle \sum _ { k = 1 } ^ { K } \beta _ { k } \operatorname { m a x } ( l _ { 1 } ( \rho _ { k } ) , l _ { 2 } ( \rho _ { k } ) ) - p _ { k } ) } } \\ { { \quad \quad \quad - \nu _ { k } ( \displaystyle \sum _ { k = 1 } ^ { K } \left| \varrho _ { k } ^ { H } \right| ^ { 2 } p _ { k } - \eta ) } } \end{array}
$$

其中 $\lambda _ { k }$ 表示问题式（13）的最优解， $\alpha _ { k }$ 、 $\beta _ { k }$ 、 $\upsilon _ { k }$ 表示各约束条件对应的拉格朗日乘子。因此，与问题式（11）等价的无约束优化问题可定义为

$$
\operatorname* { m i n } _ { \alpha , \beta , \upsilon > 0 \{ p _ { k } , \rho _ { k } \} } { L ( p _ { k } , \rho _ { k } , \alpha , \beta , \upsilon ) }
$$

一旦给定 $\alpha _ { k }$ 、 $\beta _ { k }$ 、 $\upsilon _ { k }$ 的值，最优的 $p _ { k } ^ { * }$ 和 $\rho _ { k } ^ { * }$ 可以通过KKT（Karush-Kuhn-Tucker）条件求解。

a)固定 $\rho _ { \ast }$ ，讨论 $p _ { k }$ 。

$$
\begin{array} { r } { \frac { \partial L ( p _ { k } , \rho _ { k } , \alpha , \beta , \upsilon ) } { \partial p _ { k } } = \frac { W f _ { k } \rho _ { k } } { \rho _ { k } \varepsilon _ { k } ^ { 2 } + \rho _ { k } \sigma _ { k } ^ { 2 } + \delta _ { k } ^ { 2 } + p _ { k } \rho _ { k } f _ { k } } } \\ { - \lambda _ { k } - \alpha _ { k } + \beta _ { k } - \upsilon _ { k } \left| g _ { k } ^ { H } \right| ^ { 2 } } \end{array}
$$

令 $\hat { \sigma } L ( p _ { k } , \rho _ { k } , \alpha , \beta , \upsilon ) / \hat { \sigma } p _ { k } { = } 0$ ,则 $p _ { k }$ 的闭式表达式为

$$
p _ { k } = \frac { w } { \lambda _ { k } + \alpha _ { k } - \beta _ { k } + \upsilon _ { k } \left| g _ { k } ^ { H } \right| ^ { 2 } } - \frac { ( \varepsilon _ { k } ^ { 2 } + \sigma _ { k } ^ { 2 } ) } { f _ { k } } - \frac { \delta _ { k } ^ { 2 } } { \rho _ { k } f _ { k } }
$$

值得注意的是， $\lambda _ { k }$ 为最优能效区间内的值，后面将给出具体过程。由分析可知，问题式（17）关于 $p _ { k }$ 的二阶偏导数小于零，即 $\hat { \sigma } ^ { 2 } L ( p _ { k } , \rho _ { k } , \alpha , \beta , \upsilon ) \big / \hat { \sigma } ^ { 2 } p _ { k } < 0$ ，那么，式（21）所得 $p _ { k }$ 为问题式（17）的最优功率分配方案。然后采用次梯度迭代的方式更新拉格朗日乘子[14]

$$
\begin{array} { r l } & { \alpha _ { k } ^ { ( t + 1 ) } = \alpha _ { k } ^ { ( t ) } - \nabla _ { \alpha } ^ { ( t + 1 ) } \times ( \underset { k = 1 } { K } ^ { K } p _ { k } - p _ { \mathrm { t o t a l } } ) } \\ & { \beta _ { k } ^ { ( t + 1 ) } = \beta _ { k } ^ { ( t ) } - \nabla _ { \beta } ^ { ( t + 1 ) } \times ( \operatorname* { m a x } ( l _ { 1 } ( \rho _ { k } ) , l _ { 2 } ( \rho _ { k } ) ) - p _ { k } ) } \\ & { \upsilon _ { k } ^ { ( t + 1 ) } = \upsilon _ { k } ^ { ( t ) } - \nabla _ { \upsilon } ^ { ( t + 1 ) } \times ( \underset { k = 1 } { K } ^ { K } \left| { g } _ { k } ^ { H } \right| ^ { 2 } p _ { k } - \eta ) } \end{array}
$$

其中： $\nabla _ { \alpha } ^ { ( t + 1 ) }$ 、 $\nabla _ { \beta } ^ { ( t + 1 ) }$ 、 $\nabla _ { \upsilon } ^ { ( t + 1 ) }$ 表示对偶变量在迭代更新时所使用的步长，为保证乘子的收敛，步长取值必须为正。因此可将其取 $1 / t$ ，其中 $t$ 为迭代次数。为增加次梯度迭代的收敛速度，步长的设置可以采用不同的方式，例如等步长和变步长等。另外，对偶变量更新的收敛条件可根据复杂度和性能需求进行设置。

b)代入 $\boldsymbol { p } _ { k } ^ { * }$ ，讨论 $\rho _ { \ast }$ 。

将得到的最优 $p _ { k } ^ { * }$ 代入（18)，采用同样的方法可得关于 $\rho _ { \ast }$ 的表达式，此时会得到多个 $\rho _ { \ast }$ 的值，在满足 $0 \leq \rho _ { \ast } \leq 1$ 的情况下，取使问题式（18）最大的 $\rho _ { \ast }$ 。

c)求取最优能效 $\lambda ^ { * }$ 。

将以上两步得到的最优功率分配 $\boldsymbol { p } _ { k } ^ { * }$ 和最优功率分流系数$\rho _ { k } ^ { * }$ 代入式（23)。由分析可知， $F ^ { ' } ( \lambda ) < 0$ ，因此 $F ( \lambda )$ 是关于 $\lambda$ 的单调递减函数，且 $F ( 0 ) > 0$ 。如果在最优能效区间内存在一点使得 $F ( \lambda ) < 0$ ,那么函数 $F ( \lambda )$ 在最优能效区间内必存在一点使得 $F ( \lambda ) = 0$ 。因此，可采用二分法求解最优能效值。

$$
F ( \lambda ) = \sum _ { k = 1 } ^ { K } W \log ( 1 + \frac { \rho _ { k } ^ { * } p _ { k } ^ { * } f _ { k } } { \rho _ { k } ^ { * } \varepsilon _ { k } ^ { 2 } + \rho _ { k } ^ { * } \sigma _ { k } ^ { 2 } + \delta _ { k } ^ { 2 } } ) - \lambda ( P _ { c } + \mathcal { S } \sum _ { k = 1 } ^ { K } p _ { k } ^ { * } )
$$

使用二分法的目的是通过迭代求取函数的零点，其基本原理如表1所示。另外，二分法的关键点在于区间端点值的确定，这里通过放缩法获得最优能效区间的上界。假设所有小蜂窝基站在相同的信道条件下以满足约束条件的最大功率发射，即$f _ { 1 } = f _ { 2 } = . . . = f _ { k } = f$ ，那么最优能效区间的上界如式(24)所示。因此，最优能效 $\lambda ^ { * }$ 的取值范围为 $\lambda ^ { * } \in ( 0 , A )$ 。

$$
\begin{array} { r l } & { \qquad \quad \frac { \hat { k } } { k } R _ { k } } \\ & { = } \\ & { \qquad \frac { \hat { k } } { k \frac { 2 } { 3 } \hat { r } _ { k } ^ { 2 } + \hat { r } _ { k } ^ { 2 } } } \\ & { \qquad \frac { \mathrm { l n g } ( 1 + \frac { \hat { \rho } _ { k } h _ { k } f _ { 1 } } { \rho _ { 1 } \hat { r } _ { k } ^ { 2 } } + \hat { \sigma } _ { 1 } ^ { 2 } + \mathrm { l n g } ( 1 + \frac { \hat { \rho } _ { k } \hat { \rho } _ { 2 } f _ { 2 } } { \rho _ { 2 } \hat { \sigma } _ { 2 } ^ { 2 } + \hat { \sigma } _ { 2 } ^ { 2 } + \hat { \sigma } _ { 2 } ^ { 2 } } ) ^ { 2 } + \cdots + \mathrm { l n g } ( 1 + \frac { \hat { \rho } _ { k } h _ { k } f _ { k } } { \rho _ { k } \hat { r } _ { k } ^ { 2 } + \hat { \sigma } _ { k } \hat { \sigma } _ { k } ^ { 2 } + \hat { \sigma } _ { k } ^ { 2 } } ) ^ { 2 } } { \rho _ { 1 } + \rho _ { 2 } + \rho _ { 2 } + \hat { \sigma } _ { 2 } ^ { 2 } + \hat { \sigma } _ { 2 } ^ { 2 } + \hat { \sigma } _ { 2 } ^ { 2 } } } \\ &  \qquad \frac { \hat { \rho } _ { k } ( 1 ^ { 2 } + \hat { \sigma } ^ { 2 } ) ^ { 2 } + \hat { \sigma } ^ { 2 } } { \rho _ { 1 } + \rho _ { 1 } ^ { 2 } + \hat { \sigma } ^ { 2 } + \hat { \sigma } ^ { 2 } + \hat { \sigma } ^ { 2 } + \hat { \sigma } ^ { 2 } + \hat { \sigma } ^ { 2 } + \hat { \rho } _ { k } ( \hat { \sigma } ^ { 2 } + \hat { \sigma } ^ { 2 } ) ^ { 2 } + \hat { \sigma } ^ { 2 } } \\ &  \qquad \frac { \hat { \rho } _ { k } ( 1 ^ { 2 } + \hat { \sigma } ^ { 2 } ) ^ { 2 } + \hat { \sigma } ^ { 2 } } { \rho _ { 1 } + \rho _ { 1 } + \rho _ { 1 } + \rho _ { 1 } + \rho _ { 1 } } \frac { \hat { \rho } _ { k } f _ { 1 } } { R _ { k } ^ { 2 } + \hat { \sigma } ^ { 2 } + \hat { \sigma } ^ { 2 } + \hat { \sigma } ^ { 2 } } \end{array}
$$

算法1和2分别给出了二分法和联合优化算法的伪代码。外层循环通过二分法更新第次迭代过程中的，逐步找到最优，即最优系统总能效。内层循环通过对偶分解和次梯度迭代对进行更新，找出最优功率分配策略，然后将其代入原问题可得最优功率分流系数。

算法1二分法迭代流程  
输入：区间[0,A]，精确度 $\boldsymbol { \vartheta }$ ：  
输出：零点 $\lambda ^ { * }$ ：  
验证 $f ( 0 ) f ( A ) < 0$   
求区间 $\left( 0 , A \right)$ 的中点 $\lambda ^ { * }$ ：  
计算 $f ( \lambda ^ { * } )$ ：  
如果 $f ( \lambda ^ { * } ) = 0$ ，那么 $\lambda ^ { * }$ 就是函数的零点；  
如果 $f ( 0 ) f ( \lambda ^ { * } ) < 0$ ，则令 $\boldsymbol { A } = \boldsymbol { \lambda } ^ { * }$ ：  
如果 $f ( \lambda ^ { * } ) f ( A ) < 0$ ，则令 $0 = \lambda ^ { * }$ ：  
判断：如果 $\left| 0 - A \right| < \lambda ^ { * }$ ，则得到零点近似值0或 $( A )$ ；否则，重复步骤 3)～6)算法2联合优化算法  
输入： $g _ { k } ^ { H }$ ， $\varepsilon _ { k } ^ { 2 }$ ， $\delta _ { k } ^ { 2 }$ ， $\sigma _ { k } ^ { 2 }$ ， $\rho _ { k }$ ， $f _ { k }$ ，功率收敛门限 $r _ { p }$ ，能效收敛门限 $r _ { \lambda }$ ：  
输出：最优功率分配 $\boldsymbol { p } _ { k } ^ { * }$ ，最优功率分流系数 $\rho _ { k } ^ { * }$ ，最优能效 $\boldsymbol { \lambda } _ { k } ^ { * }$ ：  
初始化： $\scriptstyle t = 0 , \alpha _ { k } ( 0 ) = 0 , \beta _ { k } ( 0 ) = 0 , \upsilon _ { k } ( 0 ) = 0$ ：  
根据（22）更新拉格朗日乘子；  
根据（21）更新 $p _ { k }$ ：  
判断：如果 $\left| p _ { k } ( t + 1 ) - p _ { k } ( t ) \right| > r _ { p }$ ，则令 $t = t + 1$ ，返回到第2）步；否则，将得到的最优功率分配 $p _ { k } ^ { * }$ 代入（18)，并求出最优的功率分流系数 $\rho _ { k } ^ { * }$   
将 $p _ { k } ^ { * }$ 和 $\rho _ { k } ^ { * }$ 代入（23）然后采用二分法求解最优能效值λ\*；  
判断：如果 $\left| \lambda _ { k } ( t + 1 ) - \lambda _ { k } ( t ) \right| > r _ { \lambda }$ ，则令 $t = t + 1$ ，并返回到第3）步；否则，输出最优能效值 ${ \boldsymbol { \lambda } } _ { k } ^ { * }$ ，算法结束。

现在对联合优化算法的计算复杂度作出简要分析。内层循环采用次梯度对拉格朗日乘子进行更新，其复杂度与功率收敛门限 $r _ { p }$ 的设置有关，为 $O ( N ^ { 2 } )$ ；外层循环采用简单的二分法寻找最优能效值，其计算复杂度也与能效收敛门限 $r _ { \lambda }$ 的设置有关，为 $\log _ { 2 } ( A / r _ { \lambda } )$ ，即算法复杂度为 $O ( \log _ { 2 } N )$ 。因此，算法的总体复杂度为 $O ( N ^ { 2 } \log _ { 2 } N )$ 。随着收敛门限的降低，其算法复杂度增加较快，因此选择适当的收敛门限使计算复杂度和精确度符合实际要求变得非常最要。

# 4 算法仿真

本节将对所提联合优化算法进行仿真，通过与文献[16]所用的拉格朗日松弛（LagrangeRelaxation,LR）方法对比，来验证算法的有效性。部分仿真参数如下：小蜂窝用户数 $K = 4$ ，在不作特别说明的情况下，小蜂窝基站天线数 $N _ { t } = K = 4$ ，小蜂窝基站总的发射功率 $P _ { t o t a l } = 3 0 \mathrm { d B m }$ 。现假设小蜂窝基站到小蜂窝用户每 $ { 5 \mathrm { m } }$ 的信号衰减为 $4 0 \mathrm { d B m }$ ，小蜂窝系统下行带宽$W = 1 5 \mathrm { \mathbf { k H z } }$ ，且所有用户的参数集相同，即 $\mathscr { E } _ { k } ^ { 2 } = \mathscr { E } ^ { 2 } = - 3 0 \mathrm { d } \mathrm { B m }$ $\delta _ { k } ^ { 2 } = \delta ^ { 2 } = - 5 0 \mathrm { d } \mathrm { B m } , \quad \sigma _ { k } ^ { 2 } = \sigma ^ { 2 } = - 7 0 \mathrm { d } \mathrm { B m } , \quad \gamma _ { k } = \gamma , \quad e _ { k } = e ,$ $\zeta _ { k } = \zeta = 0 . 6 5$ 。因为异构蜂窝网络采用低功耗节点传输信号，传播距离短，视距（line-of-sight,LOS）信号占主导地位，因此，信道采用Rician衰落模型[15]

$$
h _ { k } = \sqrt { \frac { K _ { R } } { 1 + K _ { R } } } h _ { k } ^ { L O S } + \sqrt { \frac { K _ { R } } { 1 + K _ { R } } } h _ { k } ^ { N L O S }
$$

其中: $h _ { k } ^ { L O S } \in \pounds ^ { N _ { t } \times 1 }$ 表示视距衰落部分， $\pmb { h } _ { k } ^ { N L O S } \in \pounds ^ { N _ { t } \times 1 }$ 为非视距衰落部分，且服从均值为0，方差为 $- 4 0 \mathrm { d B }$ 的Rayleigh 分布，$K _ { \scriptscriptstyle R } = 5 \mathrm { d B }$ 表示Rician 因子。另外，视距衰落部分采用远场一致的线性天线阵列模型

$$
{ \pmb h } _ { k } ^ { L O S } = 1 0 ^ { - 2 } [ 1 e ^ { j \theta _ { k } } ~ e ^ { j 2 \theta _ { k } } { \kappa _ { \kappa } } ~ e ^ { j ( N _ { t } - 1 ) \theta _ { k } } ] ^ { T }
$$

其中： $\theta _ { \boldsymbol { k } } = - 2 \pi d \sin ( \phi _ { \boldsymbol { k } } ) / \mu$ ， $d$ 表示天线之间的间隔， $\mu$ 为载波波长， $\phi _ { k }$ 表示小蜂窝基站到小蜂窝用户的方向角。现假设$\begin{array} { r } { l = \mu / 2 , \left\{ \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 } , \phi _ { 4 } \right\} = \left\{ - 3 0 ^ { \circ } , - 6 0 ^ { \circ } , 6 0 ^ { \circ } , 3 0 ^ { \circ } \right\} } \end{array}$ 。下面分别讨论算法迭代次数，基站天线数和基站总发射功率和系统能效之间的关系。

图2反映了所提算法的收敛性能。由图可知，在保证较高系统能效的同时，所提算法收敛速度较快。

图3反映了小蜂窝基站天线数与系统平均能效之间的关系。如图所示，随着基站天线数的增加，系统平均能效呈现出先增后减的趋势。这是因为随着基站天线数的增加，基站静态功耗$p _ { c }$ 急剧增加，当天线数 $N _ { t } = 1 0$ 时，系统平均能效达到最大值。

上述结果说明，大规模天线阵列并不一定能提升系统能效，天线选择是提升系统能效的关键性工作。

![](images/24287e99a3d55576f4427f1b412a9be29c89bae7a4843a5dee6fa5fc6c0d7ac1.jpg)  
图2迭代次数与系统能效

![](images/596298cee51f9a2bdc1b18cfa671681b189d8239f3264e7c9c792d915f12bc56.jpg)  
图3小蜂窝基站天线数与系统平均能效

![](images/4a0745a516d40e7f02680b3e51484216fbc9d9adadc500b6c251b68f650e9902.jpg)  
图4确定／下基站总发射功率与系统平均能效

![](images/ed4d0b702ff631d350f80dbf265c1f75ec4db31147053910e1e6a4c82dc4f796.jpg)  
图5确定 $e$ 下基站总发射功率与系统平均能效  
图4和5分别反映了在不同的QoS与能量采集门限要求

下，小蜂窝基站总发射功率与系统平均能效之间的关系。如图所示，系统平均能效随着总发射功率的增加而增加，当$p _ { \mathrm { t o t a l } } = 2 4 d B m$ 时，在给定的／和 $e$ 下，系统平均能效达到最大值，且随着总发射功率的增加保持不变。另外，较低的QoS 和能量采集要求能实现较大的系统能效。因此，系统能效与用户QoS和能量采集门限之间存在折中。

# 5 结束语

研究了MISOSWIPT异构小蜂窝网络的能效优化问题，在保证小蜂窝用户正常通行和能量采集的前提下，提出了一种低复杂度的多目标联合优化算法。通过与前面工作的对比凸显出：所提算法能有效提升系统能效，且算法复杂度较低，有利于移动终端进行能量采集，从而为解决移动设备能量受限问题提供了理论基础。未来将进一步研究大规模天线阵列中天线选择与系统能效的关系。

# 参考文献：

[1] Zhang R.,Maunder R.G.,L.Hanzo.Wireless information and power transfer:from scientific hypothesis to engineering practice [J].IEEE Communications Magazine,2015,53(8): 99-105.   
[2]宋要飞，徐位凯，王琳．基于功率分配器的大规模信息能量同传系统吞 吐率优化[J]．厦门大学学报：自然科学版,2017(02):271-277.   
[3]X.Lu,P. Wang,D.Niyato,etal. Wireless networks with rfenergy harvesting: a contemporary survey [J]. IEEE Communications Surveys & Tutorials, 2015,17(2): 757-789.   
[4]G.Pan,H.Lei, Y. Yuan,Z.Ding.Performance analysis and optimization for swipt wireless sensor networks [J].IEEE Transactions on Communications, 2017,65 (5): 2291-2302.   
[5]M.M. Zhao,Y.Cai,Q. Shi,et al.Robust transceiver design for miso interference channel with energy harvesting [J]. IEEE Trans on Signal Processing,2016,64(17): 4618-4633.   
[6]E.Boshkovska,R.Morsi,D.W.K.Ng.Power allocation and scheduling for SWIPT systems with non-linear energy harvesting model[C]// Proc of IEEE International Conference on Communications.2016:1-6.   
[7]Ng D W K, Schober R.Resource allocation for secure communication in systems with wireless information and power transfer[C]//Proc of IEEE Globecom Workshops.2013:1251-1257.   
[8]Lohani S,Hossain E,Bhargava VK. On Downlink resource allocation for swipt in small cels ina two-tier HetNet [J].IEEE Trans on Wireless Communications,2016,15 (11): 7709-7724.   
[9]Sheng M, Wang L,Wang X,et al. Energy efficient beamforming in MISO heterogeneous cellular networks with wireless information and power transfer [J].IEEE Journal on Selected Areas in Communications,2016,34 (4): 954-968.   
[10] Ng D W K,Schober R.Secure and green SWIPT in distributed antenna

networks with limited backhaul capacity [J].IEEE Trans on Wireless

Communications,2015,14(9):5082-5097.   
[11]HintonK,JalaliF.A survey of Internet energy efficiencymetrics [C]//Proc of the 5th International Conference on Smart Cities and Green ICT Systems. 2016: 1-9.   
[12] Dinkelbach W.On nonlinear fractional programming [J].Management Science,1967,13(7):492-498.   
[13] Larsson E G,Danev D,Olofsson M.Teaching the principles of massive MIMO:exploring reciprocity-based multiuser MIMO beamforming using acoustic waves [J].IEEE Signal Processing Magazine,2017,34(1): 40-47.   
[14] Valls V,Leith DJ.Dual subgradient methods using approximate multipliers [C]//Proc of the 53rd Annual Allerton Conference on Communication, Control,and Computing.2015:1016-1021.   
[15] Cai Y,Zhao M M, Shi Q,et al. Joint transceiver design algorithms for multiuser miso relay systems with energy harvesting [J].IEEE Trans on Communications,2016,64(10): 4147-4164.   
[16]Peng C,Shi Q,Xu W,et al.Energy efficiency optimization for multi-user MISO swipt systems [C]//Proc of IEEE China Summit and International Conference on Signal and Information Processing.2015: 772-776.