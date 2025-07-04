# 楔形超高层建筑风效应的大涡模拟研究

# 余远林 杨易 谢壮宁

(华南理工大学亚热带建筑科学国家重点实验室，广州510641)

【摘要】风荷载往往是超高层建筑结构安全性和舒适性的控制性荷载。本文通过大涡模拟技术并结合作者建议的一种新的湍流入口生成方法(NSRFG方法),对四种不同锥度的楔形建筑模型进行了风效应的数值模拟对比研究,以比较不同锥度对结构风荷载和风振响应的影响,及检验本文数值模拟方法的适用性。数值模拟结果表明，虽然不同锥度的建筑模型平均风压和脉动风压分布规律相似，但在结构响应方面,结构横风向峰值基底弯矩响应随模型锥度增大显著减少,表明采用适当锥度的体形可以有效地减小结构横风向气动荷载。本文数值模拟结果和风洞试验结果整体规律相符,表明结合改进的入流湍流生成技术的大涡模拟具有一定的精度，可以给超高层建筑气动外形优化研究提供有价值的参考。

(关键词】超高层建筑;气动优化大涡模拟风荷载结构响应【中图分类号】TU355； $\mathrm { T U } 3 1 2 ^ { + } 1$ 【文献标识码】A【DOI】10.16670/j.cnki.cn11 -5823/tu.2017.01.16【文章编号】1674-7461(2017)01-0091-06

# 1前言

随着社会经济的发展,国内近年来已出现了越来越多的超高层建筑。由于高层建筑结构具有柔度大、质量轻、自振频率以及阻尼较低的特点，结构的风效应逐步成为控制高层建筑安全性、舒适性和经济性的最重要的因素之一。超高层建筑结构属风敏感性结构，对风荷载所造成的扰动十分敏感，在强风作用下容易受到损坏。强风作用下超高层建筑结构的风荷载是结构安全性和舒适性的控制荷载，因此对风荷载的研究和分析已成为超高层建筑结构设计和体型优化的重要环节。

建筑外形是决定作用于结构上气动荷载的关键因素，通过合理改变建筑物的外形，对建筑外形进行优化设计，可以显著改变作用于建筑结构的风荷载和风致响应。通过传统的增强结构的强度与刚度已经很难满足现今结构设计者对于抗风设计的要求，于是合理地优化作用于超高层建筑结构上的风荷载已成为结构风工程的一个重要研究方向，如台北的101大厦及阿联首迪拜大厦的外形都进行了抗风优化研究。

随着计算风工程在国内外的发展，数值模拟方法已经成为结构风工程的主要研究方法之一，大涡模拟（LargeEddySimulation,LES）在建筑风效应的模拟中得到越来越广泛的应用。随着数值模拟技术和计算机性能的提升，近年来研究人员尝试将大涡模拟运用到工程实践中。例如,李秋胜等人[1-]采用LES分析了高层建筑的空气动力学效应，Dag-new,A.等人[3]和Daniels,S.J.等人[4]运用LES对高层建筑的风荷载进行了评估。

目前，采用LES数值模拟方法对超高层建筑的气动外形进行参数优化研究还较少，分析可能原因，由于超高层建筑风荷载效应对气动外形变化较敏感，这需要数值模拟具有很高的精度和分辨率，而通常数值风洞技术还很难做到和物理风洞类比。

本文旨在运用计算流体动力学（Computationalfluiddynamics，CFD)数值模拟技术，结合作者建议的一类新的入流湍流生成技术，对不同楔形外形的超高层建筑模型进行大涡模拟研究，以评估不同锥度楔形外形建筑模型的气动荷载和风致响应影响规律，并探讨采用新的入流湍流生成方法的LES数值模拟技术研究超高层建筑气动外形优化的可行性。

# 2数值模拟概况

# 2.1算例模型与结构动力特性

本文选取4个不同外形的建筑模型进行计算，模型高度均为 $9 1 0 \mathrm { m m }$ ,模型底边宽度为 $1 0 0 \mathrm { m m }$ ,缩尺比取为 $1 : 6 0 0$ ,相当于实际建筑高度 $5 4 6 \mathrm { m }$ ，建筑高宽比9.1。4个模型中包含1个正方形等截面模型（模型1），3个锥度(模型底部截面边长与顶部截面边长差值与模型高度的比值）分别为 $2 . 2 \%$ ，$4 . 4 \%$ ， $6 . 6 \%$ 的楔形建筑模型(模型2，模型3，模型4)各模型形状和尺寸如图1所示。为方便叙述，锥度用 $\boldsymbol { \xi }$ 表示并定义：

$$
\xi = \frac { D _ { 1 } - D _ { 2 } } { H }
$$

2式中， $D _ { 1 }$ 和 $D _ { 2 }$ 分别为模型底部和顶部截面边长； $\mathcal { H }$ 为模型高度;

![](images/e97f6e262c8020914df1e18aa96df371e03df0f886c94321550cf040a7c2ffee.jpg)  
图1模式形状和尺寸 $\mathbf { \dot { m } } \mathbf { m } )$

建筑模型动力计算所采用的前两阶自振周期均为10.2s（自振频率 $0 . 0 9 8 ~ \mathrm { H z }$ )，假定振型沿高度方向线性分布，阻尼比取为 $3 . 5 \%$ ，基本风压参照深圳地区，选取重现期100年、50年和10年的基本风压分别为 $0 . 9 0 \mathrm { { k P a } } \ , 0 . 7 5 \mathrm { { k P a } }$ 和 $0 . 4 5 \mathrm { k P a }$ 。

# 2.2 湍流入口的生成

入口湍流的模拟一直以来是大涡模拟的关键问题之一，其意义等同于物理风洞试验中需首先准确模拟边界层风场特性，因此有许多专门研究针对入口湍流的准确模拟、以及入口湍流影响等进行深入探讨。本文采用作者建议的一种湍流入口生成方法—NSRFG方法[5]生成大涡模拟的湍流入口,其表达式如下式所示：

$$
u \left( x , t \right) ~ = ~ \sum _ { n = 1 } ^ { N } p _ { n } \mathrm { s i n } { \left( \mathrm { \bf ~ k } _ { n } \cdot \tilde { x } + 2 \pi f _ { n } t + \varphi _ { n } \right) }
$$

$u = \{ u , v , w ^  \} , \stackrel { \sim } { x } = \frac { x } { L _ { n } } , x = \{ x , y , z ^  \} ; ~ \mathbf { p } _ { n } ~ =$ $\sqrt { 2 \mathrm { S } ( f _ { n } ) \Delta f } ; \mathrm { ~ S ~ } = \mathrm { ~ } \{ s _ { u } , s _ { v } , s _ { w } \}$ 为三个方向上的风速谱（卡曼谱),N为功率谱离散数目,fn= 2n-1为带宽, $\varphi _ { n } - U ( - \pi , \pi )$ ,另外参数 $L _ { \mathfrak { n } }$ 取值由下式得到：

$$
L _ { _ n } \ = \frac { U _ { _ { a v } } } { \gamma C f _ { n } }
$$

$\gamma = \binom { 3 . 7 \beta ^ { - 0 . 3 } , \beta < 6 . 0 } { 2 . 1 , \beta \geqslant 6 . 0 }$ ， $\beta = { \mathrm { C D } } / { \mathrm { L u } } , { \mathrm { C } }$ 为衰减系数；Lu为 $\mu$ 方向湍流积分尺度； $\mathrm { D } = 0 . 5 \sim$ $1 . 0 \mathrm { h } , \mathrm { h }$ 为建筑高度；Uav为平均风速。

通过编程将NSRFG方法写成UDF用户自定义程序并与商用软件包ANSYSFLUENT链接进行计算。

本文研究对象原型为 $5 0 0 \mathrm { m }$ 以上的超高层建筑，由于此高度已经超过了我国现行荷载规范的梯度风高度，故没有采用《建筑结构荷载规范（GB50009-2001）》的风场参数取值，而是依据英国工程科学数据库(ESDU)的方法定义了数值模拟入口的平均风剖面和湍流度剖面，如图2所示。

![](images/4d8ada4c4a846a27238e204c43f2486b6a51ce481f134f36090215d0ae1a6e2c.jpg)  
图2风剖面与湍流度分布(ESDU)

# 2.3 网格划分与参数设定

数值模拟在华南理工大学风洞实验室的数值风洞平台商用CFD软件包ANSYSFLUENT上进行。参照 $\mathrm { A I J } ^ { [ 6 ] }$ 和相关文献的规定，确定流域尺寸如图3a所示，堵塞率为 $0 . 8 \%$ ,满足小于 $3 \%$ 的要求。边界条件方面，模型表面和地面设置为无滑移壁面，流域左右壁面和顶面设置为对称面，流域入口为速度入口，出口采用压力出口，如图 $3 \mathrm { a }$ 所示。由于建筑模型较为规整，本次数值模拟采用结构网格进行计算。考虑到计算精度和计算资源的平衡，最小网格尺寸取为0.06D（D为模型底面宽度），网格拉伸比例为1.05。近墙壁 $\mathrm { ~ y ~ + ~ }$ 值约为 $3 0 \sim 7 5$ ,适用于壁面函数。不同模型网格划分方式一致，网格数量约为320万，网格划分情况如图3b所示（仅给出模型1的情况）。

6 本次数值模拟计算采用压力隐式分割算法(Pressure Implicit with Splitting of Operators,PISO）,空间离散采用中心差分格式，时间离散采用二阶隐式格式。亚格子模型采用壁面自适应局部涡粘模型（Wall-AdaptingLocalEddy-viscositymodel,WALE）。计算在华南理工大学风洞实验室的64核AMAX工作站进行，采用16核并行计算。时间步长选为0.002s,数值模拟计算总时间10s,并取后8s的数据作为分析数据。参考高度采用模型高度$0 . 9 5 \mathrm { m }$ ,在参考高度处的风速为 $1 1 \mathrm { m / s }$ 。参考高度处建筑模型雷诺数约为 $7 . 8 \times 1 0 ^ { 4 }$ O

![](images/05da4a4bc55226b862665847935858de4377aa6af53776b6595cd45a6b691419.jpg)  
图3计算流域尺寸与网格

# 3 结果分析

# 3.1 表面风压分布和流场分布

经计算，得到四个模型的表面平均风压系数和脉动风压系数分布，如图5所示。由图5可得，拥有不同锥度的模型平均风压系数和脉动风压系数大小差别不大，分布相似。随着锥度的增大，风压分布图形趋于拉长。值得注意的是，在模型背风面脉动风压系数分布方面，随着锥度的增大，图形辐射中心由两个化为一个，且有上移的趋势。具体风压系数分布情况见图5。

图6给出模型1在10s时刻湍流场示意图。由图6可见，来流风在建筑迎风两侧发生分离，并产生分流涡旋，在来流风的作用下交替向下游泄出，产生规则的漩涡脱落现象。模型的尾流流场出现有别于来流湍流的复杂特征湍流，呈现出典型的钝体分离流动特性。

# 3.2横风向基底气动弯矩和结构响应

强风作用下风荷载将成为影响结构安全的控制荷载，超高层建筑的横风向风致振动响应通常会超过顺风向响应而成为结构设计中要考虑的重点[7] 0

![](images/64063af7ebb159d349b6d10b65c0a7210aa24fa506ccdbad1ccf48aa7a730b9f.jpg)

![](images/05af50cad31f239bdcf30a8330edb3d49dc9ce455d65e40edd254c8668f39013.jpg)  
图5风压系数分布

![](images/a4ec903c46ed1edb54654be94073cc62885ed16aae9a71b2eb40573b8ad589dc.jpg)  
图6流场：10s时速度云图和流线(模型1)

当结构的振型沿高度线性分布时，基底弯矩和结构的1阶广义力成正比，因此基底弯矩是衡量结构整体气动性能的重要指标。为研究不同锥度 $\boldsymbol { \xi }$ 对模型基底弯矩的影响，在数值模拟过程中记录每一个时间步的横风向基底弯矩系数 $C _ { M x }$ ,其定义如式（4）所示：

$$
C _ { \mathrm { M x } } = { \frac { M _ { \mathrm { x } } } { { \displaystyle { \frac { 1 } { 2 } } \rho ^ { } { V _ { h } } ^ { 2 } D H ^ { 2 } } } }
$$

其中， $M x$ 为建筑模型的横风向基底弯矩， $\boldsymbol { V } _ { h }$ 为参考高度风速， $D$ 为建筑模型的宽度（此处取底部宽度）， $H$ 为建筑模型高度。

图6给出了不同锥度的模型横风向基底弯矩系数功率谱密度的对比。由图6可见，气动弯矩随模型截面的收缩而衰减，同时基底弯矩的主峰频率随锥度的增大而增大。此结果与文献[7」的风洞试验结果基本一致，进一步验证了本文数值模拟方法的适用性和准确性。

![](images/3e66b09530ce3ce4da888fa6776eec8580328eaa8a0e57b3cbba95edb3886ab4.jpg)  
图6不同锥度下模型横风向基底弯矩功率谱密度

随着的增大，基底弯矩的主峰频率也增大，使得建筑的基底气动弯矩的主能量分布向高频端移动，这可能会对结构带来不利的影响。图6中竖线对应的频率值分别为100年、10年重现期下原型结构1阶自振频率换算到模型的值，其换算关系为：

$$
f _ { m } = \frac { f _ { p } } { \lambda _ { f } } = \frac { f _ { p } \lambda _ { L } } { \lambda _ { V } }
$$

其中, $f _ { m }$ 和 $f _ { p }$ 为模型与原型频率； $\lambda _ { f } , \lambda _ { L } , \lambda _ { V }$ 分别为原型和模型的频率比、缩尺比和风速比。

根据结构动力学随机振动理论，由式(4)记录的基底弯矩时程和结构动力特性可计算得到考虑结构动力放大效应的横风向基底弯矩功率谱密度和标准差，计算公式如式(6）～（8)所示：

$$
S _ { M _ { D } } ( f ) \ = \mid \ H ( f ) \mid \ ^ { 2 } S _ { M } ( f )
$$

$$
\pmb { \sigma } _ { M _ { D } } = \int _ { \ 0 } ^ { \infty } S _ { M _ { D } } ( f ) d f \approx \sqrt { \pmb { \sigma } _ { M } ^ { 2 } + \pi f _ { 0 } S _ { M } ( f _ { 0 } ) / ( 4 \zeta ) }
$$

$$
| H ( f ) \ | ^ { 2 } \ = \ { \frac { 1 } { \{ [ \ : 1 \ - \ ( f - f _ { 0 } ) ^ { 2 } \ : ] ^ { 2 } \ + 4 \zeta _ { \cdot } ^ { 2 } \ ( f / f _ { 0 } ) ^ { 2 } \ : \} } }
$$

式中，| $H ( f ) \mid ^ { 2 }$ 为结构机械导纳函数; $f _ { 0 }$ 和 $\zeta$ 分别为结构1阶自振频率和阻尼比。式（7）中的$\sigma _ { M } ^ { 2 }$ 和 $\pi f _ { 0 } S _ { M } ( f _ { 0 } ) / ( 4 \zeta )$ 分别为弯矩响应的背景分量和共振分量。在得到基底弯矩标准差之后，模型的峰值基底弯矩响应由下式计算得到：

$$
M _ { \mathrm { m a x } } \ : = \ : \bar { M } \ : + \ : g \ : \cdot \ : \sigma _ { M _ { D } }
$$

式中， $M _ { \mathrm { m a x } }$ 为峰值基底弯矩响应; $\bar { M }$ 为基底弯矩响应平均值(横风向取为0)； $\boldsymbol { g }$ 为峰值因子，由下式可得：

$$
g _ { x } \ = \ \sqrt { 2 \ln ( \upsilon _ { x } T ) } + 0 . 5 7 7 / \sqrt { 2 \ln ( \upsilon _ { x } T ) }
$$

其中，T为统计时间,通常取600s; $\upsilon _ { x }$ 是单位时间内平均位移的水平交叉率数，由下式求得：

$$
{ \pmb { \nu } } _ { x } \ = \ \big [ \int _ { 0 } ^ { \infty } { \bf f } ^ { 2 } S _ { x 1 } \left( f \right) d n \big / \int _ { 0 } ^ { \infty } { S _ { x 1 } \left( f \right) d n } \big ] ^ { 1 / 2 }
$$

关于高层建筑结构峰值响应计算的具体方法详见文献「8。本文计算响应用的结构自振周期是根据已有工程和规范建议估计的，但实际的建筑结构周期会在这个基础上发生一定范围内变化。为全面考虑建筑外形对结构气动性能的影响必须分析该结构风致响应对周期变化的敏感性。图7给出了不同 $\boldsymbol { \xi }$ 值下模型峰值基底弯矩随周期比的变化曲线图。此处周期比的定义是实际建筑结构周期与本文假定的计算周期之比，周期比的变化范围为$0 . { \overset { } { \underset { } { \underbrace { - 6 } } } } \sim 1 . 4$ ,相当于结构的计算周期范围为 $6 . 1 2 \sim$ 28s,这一范围基本覆盖了《建筑结构荷载规范（GB50009-2001）》计算结构周期的经验公式范围，基本满足此类高度超高层建筑自振周期的要求。

![](images/0d1a35e7e4fd602a611fd95c396bf8d7130917882eebe34672e16be7071e4190.jpg)  
图7不同周期比下峰值基底弯矩

从图7可得，当周期比大于等于0.85时，峰值基底弯矩随着锥度 $\boldsymbol { \xi }$ 的值增大而减小，由此看来建筑模型的截面收缩可十分有效地降低结构峰值基底弯矩。当周期比小于0.7时， $\xi = 2 . 2 \%$ 和 $\xi =$ $4 . 4 \%$ 两种外形模型的峰值基底弯矩反而出现超过等截面模型的情况，可见变化规律与图6所示基底弯矩功率谱密度的变化规律一致，且在所关心的周期比变化范围内， $\xi = 6 . 6 \%$ 模型的峰值基底弯矩响应最小。此计算结果与文献[8]风洞试验结果变化规律整体相符，证明结合改进的入流湍流生成技术的大涡模拟具有相当的精度，可以给超高层建筑气动外形的优化研究提供有价值的参考，对不同外形的建筑模型风效应进行定性的比较和判断。

但不可否认的是，数值模拟结果与试验对比仍存在一定差距，可能与大涡模拟的滤波效应、数值模拟参数设置等因素有关，将在后续的工作中进行详细比较分析，以进一步提高数值模拟结果的精度。

# 4结论

本文采用CFD大涡模拟技术并采用作者建议的一种湍流生成方法—NSRFG方法对拥有不同锥度的楔形外形超高层建筑模型进行了风效应的研究，得出以下结论：

(1)不同模型的平均风压系数和脉动风压系数大小差别不大，分布规律相似；随着锥度的增大，风压分布图形趋于拉长。

(2)结构横风向峰值基底弯矩响应随模型锥度增大显著减少，这说明超高层建筑采用由下到上逐渐收缩的外形可以有效地减小结构横风向气动荷载。一定周期比范围内，锥度越大，横风向气动弯矩的削减效果越好。锥度分别为 $2 . 2 \%$ ， $4 . 4 \%$ ，$6 . 6 \%$ 的建筑模型在周期比为1的情况下，相对于等截面模型横风向基底弯矩响应减少了 $5 8 . 8 \%$ ，$8 4 . 5 \%$ 和 $8 6 . 2 \%$ 。同时锥度越大，建筑的游涡脱落频率也会相应增大，这有可能造成在结构自振频率高或者低风速情况下，锥度高的建筑风致响应比等截面还大的情况。此类建筑的外形优化还需和角区优化、避难层开透风槽等局部气动优化措施综合考虑。

(3)采用作者建议的新的LES入流湍流生成方法NSRFG方法，数值模拟结果与风洞试验客观上虽存在一定差距(可能与大涡模拟滤波效应和数值模拟参数设置有关），但仍具有相当的精度和分辨率，可以较为准确地预测模型漩涡脱落频率，给超高层建筑气动外形的优化研究提供有价值的参考，可以达到在初步设计阶段对不同外形的建筑模型风效应进行体型优选的目的。

# 参考文献

［1］李秋胜，刘顺.基于大涡模拟的平屋盖锥形涡数值模拟研究.湖南大学学报（自然科学版），2015，42（11）：72-79.  
[2］卢春玲，李秋胜,黄生洪,等.深圳平安国际金融大厦风致响应大涡模拟分析.建筑结构学报，2012，33(11):1-11.  
[3]Dagnew,A.,Bitsuamlak,G.T.Large eddy simulation forwind-induced response of tall buildings located in a citycenter.In:Proceedings of the 2O12 Engineering MechanicsInstitute and $1 1 ^ { \mathrm { t h } }$ ASCE Joint Specialty Conference onProbabilistic Mechanics and Structural Reliability.NotreDame，2012.surface and surface pressure fluctuations of a tall modelbuilding.Journal of Wind Engineering and Industrial Aer-odynamics，2013，120：19-28.  
[5］Yuanlin Yu,Yi Yang,Zhuangning Xie.An improved in-flow turbulence generator for LES evaluation of wind loadon high-rise buildings[C].Processing of the 8th interna-tional colloquium of buff bodies aerodynamics and appli-cation,Boston，2016.  
[6]Yoshihide Tominaga,Akashi Mochida,Ryuichiro Yoshie,HirotoKataoka,TsuyoshiNozu,MasaruYoshikawa,TaichiShirasawa.AIJ guidelines for practical applications of CFDto pedestrian wind environment around buildings.JournalofWind Engineering and Industrial Aerodynamics,2008.1749-1761.  
[7］谢壮宁，李佳.强风作用下楔形外形超高层建筑横风效应试验研究.建筑结构学报，2011，32（12）：118-126.  
［8］谢壮宁，方小丹,倪振华.超高层建筑的等效静风荷载：扩展的荷载响应相关方法［J].振动工程学报，2008，21(4):398-403.

# LES Research on Wind Effect on Tapered Super-tall Buildings

Yu Yuanlin,Yang Yi, Xie Zhuangning (State Key Laboratory of Subtropical Building Science， South China University of Technology, Guangzhou 510641，China）

OAbstract: Wind load was often the key load for the safety and comfort of super-tallbuilding structures. Large eddy simulation(LES)technique combined with a new inflow turbulence generator(NSRFG)was employed to study the wind effects on tapered building models with diferent tapers,which aimed to compare the effctof different taper on wind loads and wind-induced responses of the structure and validate the applicabilityof the numerical method of this paper.Numerical simulation showed thatthe distributions of the average and fluctuating pressure on building surfaces were similar,whilefor the wind-induced response,the peak base bending moment(BBM)of different models in across wind direction decreased remarkably with the increasing of the taper.Therefore,a building with botom-up graduall shrinking and an appropriated tapershape can efectively decrease the aerodynamic wind load in acros-wind direction.In adition,results from the numerical simulation werecoincided with that fromthe wind tunneltest inthe whole,which indicated thatLES technique combined with an appropriated inflow turbulence generator would havecertain accuracy and canprovide valuable reference to the aerodynamic shape optimization of super-tall buildings.

Key Words:High-rise Building；Aerodynamic Optimization； Large Eddy Simulations；Wind Loads； StructuralResponse