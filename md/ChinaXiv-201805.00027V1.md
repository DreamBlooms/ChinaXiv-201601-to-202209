# 基于上下行对偶的CRN下行功率分配和波束赋形算法

季中恒，季新生，黄开枝(国家数字交换系统工程技术研究中心，郑州 450002)

摘要：认知无线网络（CRN）在underlay工作模式下的多用户下行功率分配和波束赋形问题研究中存在通用的 SDR算法计算复杂度高，实用性受限以及优化问题中忽视主网络（PN）对认知用户（SU）的干扰等问题。针对这些问题，首先在CRN网络模型中增添PN对 SU的干扰，生成优化问题；而后基于上行和下行的对偶特性，采用虚拟功率，将优化问题进行形式变换，成为上行功率分配和波束赋形问题；得到能够简便、快速求解的迭代算法。分析了算法的收敛特性，得到了收敛条件；并进一步计算了算法的复杂度，结果表明优于SDR算法。数值仿真显示，算法收敛很快；而且表明主网络基站（PBS）发送功率的变化影响可行解区域；PBS 发送功率的增加会导致CRN下行功率增大，影响较显著。

关键词：认知无线网络；虚拟功率；迭代算法；复杂性；可行解区域 中图分类号：TN927 doi:10.3969/j.issn.1001-3695.2017.10.1011

# CRN downlink power allocation and beamforming algorithm based on duality of uplink-downlink

Ji Zhongheng, Ji Xinsheng, Huang Kaizhi (National Digital Switching Systems Engineering &Technological Research Center, Zhengzhou 45002,China)

Abstract: There are some problems on multi-user downlink power allocation and beamforming inacognitiveradio network (CRN)which works intheunderlay mode.Theyare the highcomplexityof theconventionalSDRalgorithm,the limited applicabilityand ignoringthe interferences ofthe primary network(PN) to the secondaryuser（SU）,etc.Aiming at these problems,thispaperfirstlyaddedthe termofinterferenceofthePNtotheSUtothe CRN modelandformulated theoptimization problem.Thenbasedonthedualityofuplink-downlink,itobtainedthesimpleandfastiterativealgorithmbyintroducing virtual power,transforming theoptimization problem into theproblem ofuplink power alocation and beamforming.And it analyzed theconvergenceofthealgorithm toobtaintheconvergentconditions.Italsoreckoned thealgorithmcomplexity.Theresult demonstrates that iterative algorithm is superiorto the SDR algorithm.Numerical simulationresultsshow that thealgorithm convergesfaster,and thatthevariationoftransmitingpoweroftheprimarybasestation(PBS)couldaffectthefeasibilityregion. Theyalso show thathe increasingoftransmitig powerofthePBScouldlead to thedownlink powerincreasing.The influences are notable.

Key Words: cognitive radio network; virtual power; iterative algorithm; complexity; feasibility region

# 0 引言

认知无线网络（cognitive radio network,CRN）技术能有效地利用无线频谱，认知无线网络用户，即次级用户（secondaryuser，SU）可以在不影响授权用户，即主用户（primaryuser,PU）的前提下，接入频谱。这样就形成了两个网络，一个是PU组成的主网络（primary network，PN)，另一个是 SU 组成的CRN，两个网络在无线频谱空间是叠加在一起的。

CRN有三种工作模式，分别是interweave，overlay和underlay。在interweave工作模式，CRN只能在PN不工作的频点上接入，而一旦PN要占用该频点，CRN必须退出；这样就有可能会使CRN进行多次的接入和退出，使其无法正常工作。在overlay工作模式，CRN需要获知PU的码本和消息知识，通过编码方法来消除对PN的干扰；但是这一条件，在多数场合下，并不能得到满足，因而CRN会影响PN的工作。在underlay工作模式，CRN通过信道条件来控制自身的发送参数，实现与PN 共享频谱。

工作于underlay 模式下的CRN 多用户功率分配和波束赋形问题是当前CRN研究的一个重点。当SU和PU的数目较少时，可采用迫零（zero forcing，ZF）算法，来实现CRN和PN的频谱共享[1,2]。但是当SU 和PU的数目增多时，ZF 算法就无法适用，需通过解有约束条件的最优化问题来实现CRN和PN的频谱共享[3.4]，优化目标是下行功率即CRN 基站（CBS）的发送功率最小，约束条件有以信干噪比（SINR）来度量的CRN的服务质量QoS（quality-of-service）、波束赋形矩阵及CBS对PU的总干扰等。研究中存在以下的问题：一是最优化问题求解的通用实现算法SDR（semi-definiterelaxation）有较高的计算复杂度[5]，实用性受限；二是在优化问题中忽略由PN产生的对SU 的干扰[6\~8]，这是缘于PN 的服务优先级高。但是当在满足PN 服务要求的前提下，如果不把PN所产生的对SU的干扰计入CRN的工作约束条件中，将使CRN的QoS条件不严格，导致优化结果在实际使用时产生较大的不确定性。三是虽然提出了非SDP算法，如文献[7]的迭代算法，但是没有给出明确的收敛性条件和复杂性分析。

针对以上的问题，本文对工作于underlay 模式的CRN 下行功率分配和波束赋形问题作进一步的研究，参照文献[11,12],建立CRN网络模型，在约束条件中增添PN对 SU的干扰项，得到优化问题；在文献[7,10]的基础上，基于上下行对偶原理，引入虚拟功率，将下行功率分配和波束赋形问题转换为上行虚拟功率分配和波束赋形问题，先得到上行虚拟功率和波束赋形向量，而后再由对应的变换得到下行功率，建立迭代关系，用迭代算法快速、简便地求解优化问题。并对算法的收敛特性和复杂性分别进行了分析，得到了收敛条件和复杂性度量值。

通过数值仿真，检验了迭代算法的收敛特性；分析了PN基站（PBS）的发送功率与可行解区域之间的关系；下行功率与PBS的发送功率之间的关系等。仿真结果显示，迭代算法收敛很快，通过几十次迭代后即可收敛；PBS发送功率的变化会影响可行解区域，功率增加，可行解区域减小；PBS的发送功率对下行功率有较明显的影响，尤其是变大时，下行功率的变化更加显著。

# 1 CRN网络模型及优化问题

# 1.1 网络模型

网络模型如图1所示，由1个CBS和多个SU组成CRN，1个PBS和多个PU组成PN。CBS和PBS共享频谱。实际网络中PBS的数目不止1个，但其他PBS对SU的干扰远没有与CBS共享频谱的PBS的干扰效应显著，因此对分析结果几乎无影响，可以略去。PU 的数目为 $\mathbf { \Omega } _ { L }$ ，SU的数目为 $K$ ，CBS 的发送天线数目为 $N _ { t }$ ，PBS为单天线发送，PU和 SU均是单天线接收。

CBS与 $\operatorname { s u } _ { k }$ 之间的信道向量 $\boldsymbol { h } _ { \boldsymbol { k } } = ( h _ { \boldsymbol { k } , 1 } , h _ { \boldsymbol { k } , 2 } , . . . , h _ { \boldsymbol { k } , N _ { t } } ) ^ { H }$ ，发送的功率为 $p ^ { = } ( p _ { 1 } , p _ { 2 } , . . . , p _ { K } ) ^ { T }$ ，波束赋形矩阵 $\boldsymbol { U } ^ { = } ( U _ { 1 } , U _ { 2 } , . . . , U _ { K } )$ ，其中： $\boldsymbol { u } _ { k } = ( u _ { k , 1 } , u _ { k , 2 } , . . . , u _ { k , N _ { t } } ) ^ { H }$ 。

PBS与 $\operatorname { S U } _ { k }$ 之间的信道向量 $h _ { { } _ { p k } }$ （维数为1)，发送的功率

为Pp°

![](images/f41bfbe3df0bc2e69d79033704bf25f30ce1c4d9f21962e13c6233c46fc84628.jpg)  
图1 CRN网络模型

$\operatorname { s u } _ { k }$ 的接收信号 $y _ { k } ( t )$ ：

$$
y _ { k } ( t ) = \sqrt { p _ { k } } \ h _ { k } ^ { H } \ u _ { k } \ s _ { k } ( t ) + \sum _ { i = 1 , i \neq k } ^ { K } \sqrt { p _ { i } } h _ { k } ^ { H } u _ { i } s _ { i } ( t ) +
$$

$$
\sqrt { p _ { p } } \ h _ { p k } \ s _ { p } ( t ) + z _ { k } ( t )
$$

$s _ { j } ( t )$ （ $j = 1 , 2 , . . . , K$ ）CBS发送给 SU $j$ 的信号，$E \Big ( \big | s _ { j } ( t ) \big | ^ { 2 } \Big ) = 1$ ； $s _ { p } ( t )$ 是 PBS 的发送信号， $E { \left( \left| { \boldsymbol { s } } _ { p } ( t ) \right| ^ { 2 } \right) } = 1$ ； $z _ { k } ( t )$ 是加性高斯白噪声，z(t)～N(0,σ²）。

CBS对 $\mathrm { P U } _ { l } \ ( \ l = 1 , 2 , . . . , L \ )$ 的干扰信号为 $\sum _ { i = 1 } ^ { K } \sqrt { p _ { i } } h _ { K + l } ^ { H } U _ { i } s _ { i } ( t )$ 。$\operatorname { s u } _ { k }$ 的 SINR为

$$
S I N R _ { k } = \frac { p _ { k } \left\| h _ { k } ^ { H } u _ { k } \right\| ^ { 2 } } { \displaystyle \sum _ { i = 1 , i \neq k } ^ { K } p _ { i } \left\| h _ { k } ^ { H } u _ { i } \right\| ^ { 2 } + p _ { p } \left\| h _ { p k } \right\| ^ { 2 } + \sigma _ { k } ^ { 2 } } =
$$

$$
\frac { p _ { k } \boldsymbol { u } _ { k } ^ { H } \boldsymbol { h } _ { k } \boldsymbol { h } _ { k } ^ { H } \boldsymbol { u } _ { k } } { \displaystyle { \sum _ { i = 1 , i \neq k } ^ { K } p _ { i } \boldsymbol { u } _ { i } ^ { H } \boldsymbol { h } _ { k } \boldsymbol { h } _ { k } ^ { H } \boldsymbol { u } _ { i } + p _ { p } \boldsymbol { h } _ { p k } \boldsymbol { h } _ { p k } ^ { H } + \sigma _ { k } ^ { 2 } } }
$$

因为 $h _ { { } _ { p k } }$ 的维数为1，所以 $\left\| h _ { _ { p k } } \right\| ^ { 2 } = h _ { _ { p k } } ^ { _ H } h _ { _ { p k } } = h _ { _ { p k } } h _ { _ { p k } } ^ { _ H } \circ \left\| . \right\|$ 是Euclidean 范数。

在实际应用中，很难得到信道的瞬时特性，一般是使用期望值。因此可设： $\operatorname { s u } _ { k }$ 与 CBS 之间的信道相关矩阵 $R _ { k } =$ $E ( h _ { _ k } h _ { _ k } ^ { \scriptscriptstyle H } )$ ， $\operatorname { s u } _ { k }$ 与 PBS之间的信道相关矩阵 $R _ { { _ { p k } } } = E ( h _ { { _ { p k } } } h _ { { _ { p k } } } ^ { \scriptscriptstyle { H } } )$ ，用 $R _ { k }$ 和 $\boldsymbol { R } _ { \scriptscriptstyle p k }$ 分别替换 $h _ { k } h _ { k } ^ { H }$ 和 $h _ { { _ { p k } } } h _ { { _ { p k } } } ^ { \scriptscriptstyle { H } }$ 可得：

$$
S I N R _ { k } = \frac { p _ { k } \boldsymbol { u } _ { k } ^ { H } { \boldsymbol { R _ { k } } } \boldsymbol { u _ { k } } } { \displaystyle \sum _ { i = 1 , i \neq k } ^ { K } p _ { i } \boldsymbol { u } _ { i } ^ { H } \boldsymbol { R _ { k } } \boldsymbol { u _ { i } } + p _ { p } \boldsymbol { R _ { p k } } + \sigma _ { k } ^ { 2 } }
$$

由CBS对 $\mathrm { ~ U ~ } _ { l } \left( \mathrm { ~ \right. ~ } l = 1 , 2 , . . . , L$ )的干扰信号 $\sum _ { i = 1 } ^ { K } \sqrt { p _ { i } } h _ { K + l } ^ { H } u _ { i } s _ { i } ( t )$ ，可得：

$$
I _ { l } = \sum _ { i = 1 } ^ { K } p _ { i } \left\| h _ { K + l } ^ { H } U _ { i } \right\| ^ { 2 } = \sum _ { i = 1 } ^ { K } p _ { i } U _ { i } ^ { H } h _ { K + l } h _ { K + l } ^ { H } u _ { i }
$$

可设： $\mathrm { P U } _ { l }$ 与CBS之间的信道相关矩阵 $R _ { { { \kappa } _ { + l } } } = E ( h _ { { { \kappa } _ { + l } } } h _ { { { \kappa } _ { + l } } } ^ { H } )$ ，用 ${ \cal R } _ { { \scriptscriptstyle K + l } }$ 替换 $h _ { { { \scriptscriptstyle K + l } } } h _ { { { \scriptscriptstyle K + l } } } ^ { H }$ 可得：

$$
{ { I } _ { l } } = \sum _ { i = 1 } ^ { K } { { { p } _ { i } } } { { u } _ { i } ^ { H } } { { R } _ { { { \kappa } _ { + l } } } } { { u } _ { i } } \circ
$$

关于CRN模型的两点说明：

1） $R _ { k }$ 有以下的特性：

(1） $R _ { k }$ 是 Hermitian 矩阵； $k = 1 , 2 , . . . , K + L$   
由 $R _ { k } ^ { } = E ( h _ { k } ^ { } h _ { k } ^ { \scriptscriptstyle H } )$ 可得： $\begin{array} { r } { { \cal { R } } _ { k } ^ { H } = E ( h _ { k } h _ { k } ^ { H } ) ^ { H } = E ( h _ { k } h _ { k } ^ { H } ) = { \cal { R } } _ { k } } \end{array}$ 。

(2） $R _ { k } { \succeq } O$ ，即 $R _ { k }$ 是正定/半正定的， $k = 1 , 2 , . . . , K + L$ 。因为： ${ { x } _ { k } ^ { H } } { { R } _ { k } } { { x } _ { k } } = { { x } _ { k } ^ { H } } E ( { { h } _ { k } } { { h } _ { k } ^ { H } } ) { { x } _ { k } } = E ( { { x } _ { k } ^ { H } } { { h } _ { k } } { { h } _ { k } ^ { H } } { { x } _ { k } } ) = E \Big ( \Big \| { { x } _ { k } ^ { H } } { { h } _ { k } } \Big \| ^ { 2 } \Big )$ ≥0。

2）与文献[9]将PN干扰用一随机数值表示不同，CRN 模型引入PBS 干扰，能够更加准确地描述 $S I N R _ { k }$ ，并且PBS 与SU 之间的信道的时变特性使干扰项 $p _ { p } R _ { p k }$ 对 $S I N R _ { k }$ 的影响显著;进一步影响 $p _ { k } \cdot u _ { k }$ 和 $I _ { \iota }$ 等，使优化问题的结果更符合实际。

# 1.2优化问题

下行功率分配和波束赋形的优化问题如下：

P1:

$$
\operatorname* { m i n } _ { U , p _ { 1 } , \dots , p _ { K } } \sum _ { k = 1 } ^ { K } p _ { k }
$$

s.t. $S I N R _ { k } = \frac { p _ { k } u _ { k } ^ { H } R _ { k } u _ { k } } { \displaystyle { \sum _ { i = 1 , i \neq k } ^ { K } p _ { i } u _ { i } ^ { H } R _ { k } u _ { i } + p _ { p } R _ { p k } + \sigma _ { k } ^ { 2 } } } \geq \gamma _ { k } \ ; k = 1 , 2 , . . . , K$   
$p _ { k } \ge 0 \ ; \left\| u _ { \boldsymbol { k } } \right\| = 1 ; p _ { p } \ge 0$   
$I _ { l } = \sum _ { i = 1 } ^ { K } p _ { i } U _ { i } ^ { H } R _ { K + l } U _ { i } \leq \frac { 1 } { \gamma _ { K + l } } ; l = 1 , 2 , . . . , L$   
Y和 $\frac { 1 } { \gamma _ { _ { K + l } } }$ 分别是 $S I N R _ { k }$ 和 $I _ { \iota }$ 的门限

问题P1的形式转换成为P2。

P2:

$$
\displaystyle \operatorname* { m i n } _ { U , p _ { 1 } , \ldots , p _ { K } } \sum _ { k = 1 } ^ { K } p _ { k }
$$

s.t. $S I N R _ { k } = \frac { p _ { k } u _ { k } ^ { H } R _ { k } u _ { k } } { \displaystyle { \sum _ { i = 1 , i \neq k } ^ { K } p _ { i } u _ { i } ^ { H } R _ { k } u _ { i } + p _ { p } R _ { p k } + \sigma _ { k } ^ { 2 } } } \geq \gamma _ { k } \ ; k = 1 , 2 , . . . , K$   
$p _ { k } \ge 0 \ ; \left\| u _ { { k } } \right\| = 1 ; p _ { p } \ge 0$   
$\frac { 1 } { I _ { \iota } } = \frac { 1 } { \displaystyle \sum _ { i = 1 } ^ { K } p _ { i } u _ { i } ^ { H } R _ { \scriptscriptstyle K + l } u _ { i } } \ge \gamma _ { \scriptscriptstyle K + l } ; l = 1 , 2 , . . . , L$

引入松弛变量 $p _ { K + l } \leq 1 \ ( \ l = 1 , 2 , . . . , L \ )$ )，作为虚拟的PU下行功率，可得问题P3。

P3:

$$
\operatorname* { m i n } _ { U , p _ { 1 } , \dots , p _ { K } } \sum _ { k = 1 } ^ { K } p _ { k }
$$

$$
S I N R _ { k } = \frac { p _ { k } u _ { k } ^ { H } R _ { k } u _ { k } } { \displaystyle { \sum _ { i = 1 , i \neq k } ^ { K } p _ { i } u _ { i } ^ { H } R _ { k } u _ { i } + p _ { p } R _ { p k } + \sigma _ { k } ^ { 2 } } } \geq \gamma _ { k } \ ; k = 1 , 2 , . . . , K
$$

$$
S I N R _ { K + l } = \frac { p _ { K + l } } { \displaystyle \sum _ { i = 1 } ^ { K } p _ { i } u _ { i } ^ { H } R _ { K + l } u _ { i } } \geq \gamma _ { K + l } \ ; l = 1 , 2 , . . . , L
$$

$$
p _ { k } \ge 0 \ ; \left\| u _ { k } \right\| = 1 ; p _ { { \scriptscriptstyle K } + l } \ge 0 \ ; p _ { { \scriptscriptstyle K } + l } \le 1 ; p _ { p } \ge 0
$$

$S I N R _ { K + l }$ 是 $\mathrm { P U } _ { l }$ 的虚拟 $S I N R \circ$ 由 $p _ { K + l }$ 的特性可知，问题 P2和 P3 有相同的结果。因为当 $p _ { K + l } = 1$ 时，P3 即为 P2。为确保$p _ { K + l } = 1$ ，在算法中增加 $\big | p _ { K + l } - 1 \big |$ 的收敛性判据。

# 1.3基于上行和下行对偶的问题转换

根据上行和下行的对偶特性[0]，依据文献[7]采用上行虚拟功率，下行问题P3可转换为虚拟上行问题P4。

P4:

$$
\operatorname* { m i n } _ { U , q _ { 1 } , . . . , q _ { K + L } } \ \sum _ { k = 1 } ^ { K } \gamma _ { k } ( p _ { p } R _ { p k } + \sigma _ { k } ^ { 2 } ) q _ { k } - \sum _ { l = 1 } ^ { L } p _ { K + l } q _ { K + l }
$$

s.t.

$$
S I N R _ { k } ^ { U } = \frac { q _ { k } U _ { k } ^ { H } R _ { k } u _ { k } } { u _ { k } ^ { H } \left( \sum _ { i = 1 , i \ne k } ^ { K + L } q _ { i } \gamma _ { i } R _ { i } + I \right) u _ { k } } \textbar { _ { k } } 1 ; \quad k = 1 , 2 , . . . , K
$$

$$
q _ { k } \ge 0 ; \left\| u _ { k } \right\| = 1 ; p _ { { { \scriptscriptstyle K } } + l } \ge 0 ; p _ { { { \scriptscriptstyle K } } + l } \le 1 ; q _ { { { \scriptscriptstyle K } } + l } \ge 0 ; p _ { p } \ge 0 ; l = 1 , 2 , . . . , L
$$

$q _ { 1 } , . . . , q _ { K }$ 和 $q _ { K + 1 } , . . . , q _ { K + L }$ 是分别对应于 $K$ 个SU和 $L$ 个PU的虚拟上行功率。

不同于文献[7]的是，由于考虑了PN 对 SU 的影响，其中的 $\eta _ { \scriptscriptstyle 1 }$ 变为

$$
\eta = [ \gamma _ { 1 } ( p _ { p } R _ { p 1 } + \sigma _ { 1 } ^ { 2 } ) , . . . , \gamma _ { k } ( p _ { p } R _ { p k } + \sigma _ { k } ^ { 2 } ) ] ^ { T } , k = 1 , 2 , . . . , K \mathrm { ~ o ~ }
$$

有关优化问题P4的两点说明：

a)P4 和P3有相同的优化波束赋形向量 $u _ { k } ^ { \mathrm { ~ ( ~ } _ { k } = 1 , 2 , \ldots , K ^ { \mathrm { ~ ) ~ } } }$ ，通过P4可以较简便地得到uk。

b)P3 的 $p _ { k }$ $\left( \begin{array} { l } { k = 1 , 2 , . . . , K } \end{array} \right)$ 和 $p _ { K + l }$ （ $l = 1 , 2 , . . . , L ^ { \mathrm { ~ ) ~ } }$ 由如下的关系式得到：

设 $\pmb { p } _ { 1 } = ( p _ { 1 } , p _ { 2 } , . . . , p _ { K } ) ^ { T }$ 是 $\boldsymbol { K }$ 个 SU 的下行功率向量;P=(PK+1, P+2,Pκ+z)是L个PU的虚拟下行功率向量,有

$$
p _ { 1 } = ( D - G _ { 1 } ) ^ { - 1 } \eta
$$

$$
p _ { 2 } = G _ { 2 } p _ { 1 }
$$

其中： $[ \boldsymbol { D } ] _ { k , k } = \boldsymbol { u } _ { k } ^ { H } \boldsymbol { R } _ { k } \boldsymbol { u } _ { k }$ ； $[ G _ { 2 } ] _ { l , j } = \gamma _ { { } _ { K + l } } u _ { j } ^ { H } R _ { { } _ { K + l } } u _ { j }$ (12)

$$
\begin{array} { r } { [ G _ { 1 } ] _ { i , j } = \left\{ \begin{array} { l l } { 0 , \quad } & { i = j ; } \\ { \gamma _ { i } U _ { j } ^ { H } R _ { i } u _ { j } , i \ne j } \end{array} \right. } \end{array}
$$

$$
\eta = [ \gamma _ { 1 } ( p _ { p } R _ { p 1 } + \sigma _ { 1 } ^ { 2 } ) , . . . , \gamma _ { k } ( p _ { p } R _ { p k } + \sigma _ { k } ^ { 2 } ) ] ^ { T }
$$

$$
l = 1 , 2 , . . . , L , k , i , j = 1 , 2 , . . . , K _ { \mathrm { ~ \scriptsize ~ c ~ } }
$$

# 2 迭代算法

# 2.1算法思路

由 P4 可知，当 $q _ { k }$ 固定时，波束赋形向量 $u _ { \boldsymbol { k } }$ 的值应当使$S I N R _ { k } ^ { U }$ 尽可能的大；而当 $u _ { \boldsymbol { k } }$ 固定时， $q _ { k }$ 将在尽量小的情形下满足 $S I N R _ { k } ^ { U } \geq 1$ 的要求。 $S I N R _ { k } ^ { U }$ 的最低要求是等于1，因此可得到$u _ { \boldsymbol { k } }$ 和 $q _ { k } ^ { \mathrm { ~ ( ~ } } k = 1 , 2 , . . . , K ^ { \mathrm { ~ ) ~ } }$ 的迭代算式。而 $q _ { K + l }$ 是因 $p _ { K + l }$ 所生成,所以只需 $p _ { K + l } q _ { K + l }$ 即可生成迭代算式。

# 2.2算法流程

迭代算法如下：

a）初始化q(0)=1，n=1,2...,K+Lb）迭代次数 $t = 1 , 2 , \dots$ ，作以下的迭代步骤，直到按要求收敛：

（a）波束赋形因子更新：

$$
\mu _ { k } ( t ) = \operatorname* { m a x } _ { \| u _ { k } ( t ) \| = 1 } \frac { q _ { k } ( t - 1 ) U _ { k } ^ { H } ( t ) R _ { k } u _ { k } ( t ) } { U _ { k } ^ { H } ( t ) \left( \sum _ { i = 1 , i \neq k } ^ { K + L } q _ { i } ( t - 1 ) \gamma _ { i } R _ { i } + I \right) U _ { k } ( t ) } ; k = 1 , 2 , . . . , K
$$

对于上式求解，由文献[10,14]可知： $\mu _ { k } ( t )$ 和 $u _ { k } ( t )$ 是矩阵双 $\mathbb { \displaystyle \left\{ { \mathfrak { q } } _ { k } ( t - 1 ) { \mathfrak { R } } _ { k } , \left( \sum _ { i = 1 , i \neq k } ^ { K + L } { \mathfrak { q } } _ { i } ( t - 1 ) \gamma _ { i } { \mathfrak { R } } _ { i } + I \right) \right\} } $ 的最大广义特征值和对应的单位特征向量。

（b）SU的虚拟上行功率分配更新：

$$
q _ { k } ( t ) = \frac { q _ { k } ( t - 1 ) } { \mu _ { k } ( t ) } \ ; k = 1 , 2 , . . . , K
$$

（c）转换为下行功率分配：

$$
\begin{array} { c } { { p _ { 1 } ( t ) = ( D ( t ) - G _ { 1 } ( t ) ) ^ { - 1 } \eta } } \\ { { p _ { 2 } ( t ) = G _ { 2 } ( t ) p _ { 1 } ( t ) } } \end{array}
$$

其中：

$$
\left[ \widehat { \cal D } ( t ) \right] _ { k , k } = u _ { k } ^ { { \cal H } } ( t ) { \cal R } _ { k } u _ { k } ( t ) ; \left[ \widehat { \cal G } _ { 2 } ( t ) \right] _ { l , j } = \gamma _ { K + l } u _ { j } ^ { { \cal H } } ( t ) { \cal R } _ { K + l } u _ { j } ( t ) ;
$$

$$
\begin{array} { r } { [ G _ { 1 } ( t ) ] _ { i , j } = \left\{ \begin{array} { l l } { 0 , \quad } & { i = j ; } \\ { \gamma _ { i } U _ { j } ^ { H } ( t ) R _ { i } U _ { j } ( t ) , } & { i \ne j } \end{array} \right. } \end{array}
$$

$$
l = 1 , 2 , . . . , L , k , i , j = 1 , 2 , . . . , K
$$

（d）PU的虚拟上行功率分配更新：

$$
q _ { { \scriptscriptstyle K + l } } ( t ) = \left\{ p _ { { \scriptscriptstyle K + l } } ( t ) q _ { { \scriptscriptstyle K + l } } ( t - 1 ) \ \begin{array} { l } { { i f \operatorname* { m i n } \big \{ p _ { 1 } , . . . , p _ { \scriptscriptstyle K } \big \} \geq 0 } } \\ { { q _ { { \scriptscriptstyle K + l } } ( t - 1 ) } } \end{array} \right.
$$

c）收敛性检测。

$$
\begin{array} { r } { \left| q _ { k } ( t ) - q _ { k } ( t - 1 ) \right| \le \delta ; \left| p _ { K + l } ( t ) - 1 \right| \le \delta } \end{array}
$$

$k = 1 , 2 , . . . , K + L , l = 1 , 2 , . . . , L , \delta$ 是一预先定义的收敛判决门限。  
若满足收敛条件,到d);否则,转到 $\mathbf { b } _ { , } ^ { \setminus }$ L。

d)当经过 $N$ 次迭代后，满足收敛条件时，可得问题最优值为：

（a）最优功率分配： $p _ { 1 } ( N ) , p _ { 2 } ( N ) , . . . , p _ { \scriptscriptstyle K } ( N )$ ：(b）对应的波束赋形向量u(N),u(N),,uk(N)。

# 2.3算法收敛特性分析

定理算法收敛需要满足条件 $\operatorname* { l i m } _ { t \to \infty } \ \mu _ { k } ( t ) \to 1$ ; $k = 1 , 2 , . . . , K$ 和1 $\operatorname* { i m } _ { \substack {  \infty } } p _ { \scriptscriptstyle K + l } ( t )  1$ ； $l = 1 , . . . , L$ 。

$q _ { k } ( t ) = \frac { q _ { k } ( t - 1 ) } { \mu _ { k } ( t ) } \left( \begin{array} { c } { k = 1 , 2 , . . . , K } \end{array} \right)$ 可知：

$$
\operatorname* { l i m } _ { t \to \infty } \mu _ { k } ( t ) \to 1 \Rightarrow \operatorname* { l i m } _ { t \to \infty } \frac { q _ { k } ( t - 1 ) } { q _ { k } ( t ) } \to 1
$$

$\mu _ { k } ( t )$ 是实时的 $S I N R _ { k } ^ { U }$ ,迭代过程中的收敛过程如下:$\mu _ { k } ( t ) = \operatorname* { m a x } _ { \| u _ { k } ( t ) \| = 1 } \frac { q _ { k } ( t - 1 ) U _ { k } ^ { H } ( t ) R _ { k } u _ { k } ( t ) } { U _ { k } ^ { H } ( t ) \left( \sum _ { i = 1 , i \neq k } ^ { K + L } q _ { i } ( t - 1 ) \gamma _ { i } R _ { i } + I \right) u _ { k } ( t ) }$ 可知：$\mu _ { k }$ 是 $q _ { k }$ 的单调递增函数；是 $q _ { i } ( i \neq k , i = 1 , 2 , . . . , K + L )$ 的单

调递减函数。由 $R _ { k }$ 的性质，可知 $\mu _ { k } ( t ) > 0$ 。在迭代的第 $t$ 步，$\mu _ { k } ( t )$ 的取值有两种情形，分别是

a） $\mu _ { k } ( t ) { \geq } 1$ $q _ { k } ( t ) = \frac { q _ { k } ( t - 1 ) } { \mu _ { k } ( t ) }$ （204号 $k = 1 , 2 , . . . , K$ ，可知：

$$
\begin{array} { r } { q _ { k } ( t ) \le q _ { k } ( t - 1 ) \ ; k = 1 , 2 , . . . , K \circ } \end{array}
$$

对于 $q _ { \scriptscriptstyle K + l } ( t ) : l = 1 , . . . , L$ ，由迭代关系：

$$
q _ { { \scriptscriptstyle K + l } } ( t ) = \left\{ p _ { { \scriptscriptstyle K + l } } ( t ) q _ { { \scriptscriptstyle K + l } } ( t - 1 ) \begin{array} { l } { i f \operatorname* { m i n } \big \{ p _ { 1 } , . . . , p _ { \scriptscriptstyle K } \big \} \geq 0 } \\ { q _ { { \scriptscriptstyle K + l } } ( t - 1 ) \qquad o t h e r w i s e } \end{array} \right.
$$

可知： $q _ { \kappa + l } ( t ) \leq q _ { \kappa + l } ( t - 1 )$ 或 $q _ { \kappa + l } ( t ) > q _ { \kappa + l } ( t - 1 )$

第 $t + 1$ 步时， $\mu _ { k } ( t + 1 )$ 有如下的两种情形：(a) $\mu _ { k } ( t + 1 ) \leq$ （20 $\mu _ { k } ( t )$ ，可得 $q _ { k } ( t )$ 减小； $( \mathsf { b } ) \mu _ { k } ( t + 1 ) > \mu _ { k } ( t )$ ，可得 $q _ { k } ( t )$ 仍是减小。

情形（a）的 $\mu _ { k }$ 将由于 $q _ { k }$ 的减小趋于1;（b）的 $\mu _ { k }$ 将由于$q _ { k }$ 的减小在迭代若干次后改变不等号而成为情形（a)，否则，当 $q _ { k } \to 0$ 时，有 $\mu _ { k } \to 0$ ，与a）的前提条件矛盾。

b） $0 < \mu _ { \boldsymbol { k } } ( t ) < 1$

可知 $q _ { k } ( t ) > q _ { k } ( t - 1 ) \ ; \quad k = 1 , 2 , . . . , K \ .$

第 $t + 1$ 步时， $\mu _ { k } ( t + 1 )$ 有如下的两种情形：a) $\mu _ { k } ( t + 1 ) \geq$ $\mu _ { k } ( t )$ ，可得 $q _ { k } ( t )$ 是增加的；b） $\mu _ { k } ( t + 1 ) < \mu _ { k } ( t )$ ，可得 $q _ { k } ( t )$ 仍是增加的。

在迭代过程中，情形（a）的 $\mu _ { k }$ 将由 $q _ { k }$ 的增加趋于1；(b)的 $\mu _ { k }$ 将由于 $q _ { k }$ 的增加在迭代若干次后改变不等号而成为（a)，否则，当 $q _ { k } \to \infty$ 时，有 $\mu _ { k } \to \infty$ ，与 $\boldsymbol { \mathbf { b } }$ ）的前提条件矛盾。

由 $q _ { \scriptscriptstyle K + l } ( t ) = \left\{ p _ { \scriptscriptstyle K + l } ( t ) q _ { \scriptscriptstyle K + l } ( t - 1 ) \quad i f \operatorname* { m i n } \left\{ p _ { 1 } , . . . , p _ { \scriptscriptstyle K } \right\} \geq 0 \right.$ 当 $p _ { K + l } > 1$ 时，表明 PU 所受到的干扰增大，需要减小 $p _ { k } : \mathbf { \sigma } _ { p _ { k } }$ （202的减小致使 $p _ { K + l }$ 也减小。当 $0 < p _ { \scriptscriptstyle K + l } < 1$ 时，表明 PU 所受到的干扰减小，应当增加p来得到较高的 SINRk；由此，相应的Pk+l也增加。

当 $\operatorname* { l i m } _ { t \to \infty } \ p _ { K + l } ( t ) \to 1$ 时， $\operatorname* { l i m } _ { t \to \infty } \left| q _ { K + l } ( t - 1 ) - q _ { K + l } ( t ) \right| \to 0$ ；$l = 1 , 2 , . . . , L$ 。所以，算法收敛。证明完成。

# 2.4算法复杂度分析

以乘和加作为基本运算单位，算法单次迭代过程的各步骤的计算复杂度[13]如下：

a $\left( q _ { k } ( t - 1 ) R _ { k } , \left( \sum _ { i = 1 , i \neq k } ^ { K + L } q _ { i } ( t - 1 ) \gamma _ { i } R _ { i } + I \right) \right)$ 的最大广义特征值和对应的特征向量求解。根据文献[14]的乘幂法算法，其中运算量最大的是 $N _ { t } \mathrm { ~ x ~ } N _ { t }$ 矩阵求逆，因此运算复杂度是 $O ( N _ { t } ^ { 3 } )$ 。当$k = 1 , 2 , . . . , K$ 时，运算复杂度是 $O ( K N _ { t } ^ { 3 } )$ 。

$q _ { k } ( t ) = \frac { q _ { k } ( t - 1 ) } { \mu _ { k } ( t ) }$ $k = 1 , 2 , . . . , K$ ，共作 $K$ 次运算。

c) $[ \boldsymbol { D } ( t ) ] _ { k , k } = \boldsymbol { u } _ { k } ^ { H } ( t ) \boldsymbol { R } _ { k } \boldsymbol { u } _ { k } ( t )$ ，共作 $2 \ K N _ { t } ^ { 2 } { + } 2 \ K N _ { t } { - } _ { K }$ 次运算。

d） $\left[ G _ { 2 } ( t ) \right] _ { l , j } = \gamma _ { K + l } u _ { j } ^ { H } ( t ) { \cal R } _ { K + l } u _ { j } ( t )$ ，共作 $2 \ L K N _ { t } ^ { 2 } { + } 2 \ L K N _ { t }$ 次运算。

$\begin{array} { r } { [ G _ { 1 } ( t ) ] _ { i , j } = \left\{ \begin{array} { l l } { 0 , \quad } & { i = j ; } \\ { \gamma _ { i } U _ { j } ^ { H } ( t ) R _ { i } U _ { j } ( t ) , i \ne j } & { } \end{array} \right. } \end{array}$ ，，共作 2 K²N²+2 K²N,$- 2 \ K N _ { t } ^ { 2 } - 2 \ K N _ { t }$ 次运算。

f） $p _ { 1 } ( t ) = ( D ( t ) - G _ { 1 } ( t ) ) ^ { - 1 } \eta$ ，共作 $\boldsymbol { K } ^ { 3 + 2 } \boldsymbol { K } ^ { 2 }$ 次运算。

g） $p _ { 2 } ( t ) = G _ { 2 } ( t ) p _ { 1 } ( t )$ ，共作 $^ 2 L K$ 次运算。

h） $q _ { \scriptscriptstyle K + l } ( t ) = \left\{ p _ { \scriptscriptstyle K + l } ( t ) q _ { \scriptscriptstyle K + l } ( t - 1 ) \begin{array} { c } { { i f \operatorname* { m i n } \big \{ p _ { 1 } , . . . , p _ { \scriptscriptstyle K } \big \} \geq 0 } } \\ { { q _ { \scriptscriptstyle K + l } ( t - 1 ) \qquad \ o t h e r w i s e } } \end{array} \right.$ $L ^ { + } K$ 次运算。

i）收敛性检测，共做 ${ { 2 } _ { K } } ^ { + 4 } L$ 次运算。

因此，在一个迭代过程中，算法步骤 $\mathbf { b } ) { \sim } \mathrm { i } )$ 的运算次数是2$K ^ { 2 } N _ { t } ^ { 2 } + 2 \ L K N _ { t } ^ { 2 } + 2 \ K ^ { 2 } N _ { t } + 2 \ L K N _ { t } +$

$$
K ^ { 3 + 2 } K ^ { 2 + 2 } L K ^ { + 5 } L ^ { + 3 } K \circ
$$

通常情况下， $K$ 和 $\mathbf { \Omega } _ { L }$ 的数量级相同， $K { > } { > } 1$ ，可以略去$K ^ { 2 } N _ { t } \setminus L K N _ { t } \setminus K ^ { 3 } \setminus K ^ { 2 } \setminus L K \setminus L$ 和 $K$ 等低阶项，并且 $L \approx K$ ，可得算法步骤b)\~i)的复杂度是 $O ( K ^ { 2 } N _ { t } ^ { 2 } )$ 。

由步骤a)的复杂度 $O ( K N _ { t } ^ { 3 } )$ 可得算法的复杂度是$O ( \operatorname* { m a x } ( K N _ { t } ^ { 3 } , K ^ { 2 } N _ { t } ^ { 2 } ) )$ 。而由文献[7]知，SDR 算法的复杂度是$O ( K ^ { 3 } N _ { t } ^ { 3 } )$ 。因此，迭代算法的复杂度要比SDR 算法低很多。

# 3 数值仿真及结果分析

数值仿真条件：SU用户数 $K ^ { = 5 }$ ，PU用户数 $L ^ { = 5 }$ ；CBS的发送天线数 $N _ { { t } } = 9$ ；PU 用户的干扰门限 $\frac { 1 } { \gamma _ { K + l } } = - 6 \$ dB，（ $l = 1 , 2 , . . . , L \$ )；SU的QoS约束 $\gamma _ { \scriptscriptstyle k } \mathrm { ~ ( ~ } k = 1 , 2 , . . . , K \mathrm { ~ ) ~ }$ 在区间[0.1,9.0]内取值；噪声功率 $\sigma _ { k } ^ { 2 } = . - 6$ dB， $\textbf { \textit { k } } = 1 , 2 , . . . , K ^ { \mathrm { ~ } } )$ ；信道是Rayleign衰落信道，对于每一次的信道计算结果，均作100次独立Monte-Carlo运算再取均值。PBS 的发送功率 $p _ { p } = 3 0 \mathrm { d B m }$ 。算法的收敛门限 $\delta ^ { = 1 0 ^ { - 6 } }$ 。以下图3中的The sum ofP1 即是目标值∑pk° $\sum _ { k = 1 } ^ { K } p _ { k }$

# 3.1迭代算法的收敛性

迭代算法的收敛门限和迭代次数如表1所示。

表1不同收敛门限下的迭代次数  

<html><body><table><tr><td>类别</td><td>组1</td><td>组2</td><td>组3</td><td>组4</td><td>组5</td><td>组6</td><td>组7</td></tr><tr><td>收敛门限δ</td><td>10-2</td><td>10-3</td><td>10-4</td><td>10-5</td><td>10-6</td><td>10-7</td><td>10-8</td></tr><tr><td>迭代次数N</td><td>9</td><td>14</td><td>19</td><td>34</td><td>36</td><td>58</td><td>61</td></tr></table></body></html>

由表1中的各组数据可知，算法收敛很快。如当收敛门限为 $1 0 ^ { - 6 }$ 时，经过36次迭代即满足收敛条件。相对于SDR算法，迭代算法不仅降低了计算量，而且收敛速度快。

# 3.2PBS的发送功率与可行解区域的关系

可行解区域的度量指标是可解度百分比（feasibilitypercentage)，是指在一定数量的随机信道实现条件下，优化算法有可行解的信道实现所占百分比。它是算法对信道变化适应性的一种度量。取 ${ \gamma _ { _ { k } } } = \gamma$ （ $k = 1 , 2 , . . . , K$ )。图中的 gamma 即为Y。

![](images/a1bb1f93dae80ab85ac0a166fe126fe78e3aea464138a9cfa892ba21a2d65c9a.jpg)  
图2 $\gamma$ 与可解度百分比的关系

如图2所示，当PBS的发送功率变化时，可行解区域也发生变化。这是由于PBS 的发送功率 $\boldsymbol { p } _ { p }$ 的引入，影响了优化问题的信干噪比，进一步影响了CRN的干扰约束，使可行解区域缩小。如以图中的可解度百分比为0.6为例，当 $p _ { p } = 3 0 \mathrm { d B m }$ 时，相应的 $\gamma$ 约为4.0;而当 $p _ { p } { = } 2 7 \mathrm { d B m }$ 时，相应的 $\gamma$ 增加到约4.7;在无PBS时（ $p _ { p } { = } 0 )$ ， $\gamma$ 能到约 7.0。而对于存在 PBS 的情形（ $\cdot \ p _ { p } = 3 0 \ \mathrm { d B m }$ 和 $p _ { p } = 2 7 ~ \mathrm { d B m } )$ ，可解度百分比为0。这是因为要获得 $\gamma ^ { = 7 . 0 }$ 的信干噪比，下行功率必须增加，而下行功率增大导致CBS对PU的干扰增大，无法满足干扰约束条件，所以无可行解，可解度百分比为0。由此可见，PBS的功率对可行解区域的影响是很显著的。

# 3.3PBS的发送功率与下行功率的关系

如图3所示，当PBS的发送功率 $p _ { p }$ 增加时，CRN的下行功率增加。当 $p _ { p } \leq 3 0 \mathrm { d B m }$ 时，下行功率增加较平缓；当 $p _ { p }$ $> 3 0 \mathrm { d B m }$ 后，下行功率增加较快。这是因为当 $p _ { p }$ 逐渐增大时，PBS对SU的干扰也逐渐增加，CRN要保证SU的SINR，必须增加下行功率。这表明在CRN系统中，PBS的发送功率对SU的QoS有明显的影响。

![](images/4377623f52582854f9056d14172ca734a6e3e6d7836256395913d26ff0c5def0.jpg)  
图3 $\boldsymbol { p } _ { p }$ 与下行功率的关系

# 4 结束语

通过对工作于underlay 模式的CRN下行功率分配和波束赋形问题的研究，得到了PN干扰条件下的求解优化问题的简便、快速和实用的迭代算法。为CRN的组网提供了一种有效的工具，利于工程实现。针对PN 的干扰效应，进行了算法数值仿真，得到了PBS的发送功率变化对可行解区域和下行功率均有较明显的影响的实用结论。进一步表明PN的干扰在CRN网络模型中是不能忽略的，尤其是在CRN的网络构建工程中，更应当重视。

# 参考文献：

[1]Hamdi K,Hasna M O,GhrayebA.Priority-based zero-forcing in spectrum sharing cognitive systems [J].IEEE Communications Letters,2013,17(2): 313-316.   
[2]Kibria MG,Yuan Fang,Kojima F.Feedback bits allocation for interference minimization in cognitive radio communications [J].IEEE Wireless Communications Letters,2016,5(1):104-107.   
[3]Ma Shuai,Sun Dechun.Chance constrained robust beamforming in cognitive radio networks [J].IEEE Communications Letters,2013,17(1): 67-70.   
[4]Jeong Y,Quek T Q S,Shin H.Downlink beamforming optimization for cognitive underlay networks [C]//Proc ofISITA.2010:934-939   
[5]Huang Yongwei,Palomar D P. Rank-constrained separable semidefinite programming with applications to optimal beamforming[J]. IEEE Trans on Signal Processing,2010,58 (2): 664-678.   
[6]Le TA,Navaie K.Downlink beamforming in underlay cognitive cellular networks [J].IEEE Trans on Communications,2014,62(7): 2212-2223.   
[7]Pesavento M,Ciochina D,Gershman A B.Iterative dual downlink beamforming for cognitive radio networks [C]//Proc of the 5th International Conference on Cognitive Radio Oriented WirelessNetworks& Communications.2010:1-5.   
[8]Xu Yongjun，Zhao Xiaohui,Liang Y C.Robust power control and beamforming in cognitiveradionetworks:asurvey [J].IEEE Communications Surveys & Tutorials,2015,17(4):1834-1857.   
[9]Dhifallh O,Dahrouj H,Al-naffouri T.Decentralized. SINR balancing in cognitive radio networks [J].IEEE Trans on Vehicular Technology,2017,66 (4): 3491-3496.   
[10] Schubert M,Boche H. Solution of the multiuser downlink beamforming problem with individual SINR constraints [J].IEEE Trans on Vehicular Technology,2004,53 (1): 18-28.   
[11] Tong Xue,Dong Xiaodai, Shi Yi. Resource allocation strategy for multi-user cognitive radio systems: location-aware spectrum access [J].IEEE Trans on Vehicular Technology,2017,66 (1): 884-889.   
[12] Gaafar M,Amin O,Abediseid W.Underlay spectrum sharing techniques with in-band full-duplex systems using improper gaussian signaling [J]. IEEE Trans on Wireless Communications,2017,16(1):235-249.   
[13] Boyd S,Vandenberghe L.Convex optimization [M]，Cambridge: Cambridge University Press,2004   
[14]张贤达．矩阵分析与应用[M].北京：清华大学出版社,2004.