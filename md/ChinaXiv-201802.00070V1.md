# 基于Morse势能函数谐振子模型的声传播研究

涂运冲1²谢军龙」王嘉冰¹王芸芸¹吴克启

(1.华中科技大学能源与动力工程学院，湖北武汉，4300742.广东美的制冷设备有限公司，广东顺德，528311)摘 要：对于复杂的体系，组成体系的各粒子间的相互作用决定其能量状态。对于不同势场，描述粒子运动规律的 Schrodinger方程是不同的微分方程。本文在原来的 Hamilton 谐振子数学模型基础上，通过引入 Morse 势能函数代替原来的简谐振子势模型，研究了一维气体分子链中声传播的问题。从能量的概念出发，将声传播问题转换成求解谐振子的波函数以及能量本征值的问题，建立配分函数与热力学量之间的关系，以Morse势能函数的振子模型构造的声传播模型求取声压及声能量。通过比较，经典方法与量子谐振子模型计算的一维声压吻合。

关键词：气动声学；Morse势能函数；Schrodinger方程中图分类号：04220413.1 文献标识码：A

# Sound Propagation Research on the Oscillator Model of Morse Potential Energy Function

TU Yun-Chong12 XIE Jun-Long1 WANG Jia-Bing WANG Yun-Yun' WU Ke-Qi1 (1. SchoolofEnergyand Power Engineering,Huazhong UniversityofScience andTechnologyWuhan43074，China; 2.GuangDong Midea Electric Appliances Co., Ltd， Shunde 528311， China)

Abstract:For a complex system,the reciprocal function ofthe particles constituting the system decides its energy state.Schrodinger equation which describes the particles moving rule willvary in diferent potential field. In this paper,based on the mathematic model in Hamilton harmonic oscilator researched before, Morse potential energy function which replace the harmonic oscilator potential model is introduced to study sound propagation in the one-dimensional gas molecule chain.From the standpoint of energy,the problem about sound propagation is converted into the problem ofthe harmonic wavelet function and the energy Eigen values.The relationship between the partition function and the thermodynamics quantity is built and sound propagation model based on oscilator model of Morse potential energy functions is used to get sound pressre and sound energy.Finally the one-dimensional sound pressure results got by quantum oscillator model agre well with classical approach results.

Keywords: aeroacoustics; Morse potential energy function; Schrodinger equation

# 0引言

已有气动声学理论研究基本上是在牛顿体系下展开研究的，虽在工程应用上获得巨大成功，但它们从建立之初就有其不足之处，令其发展缓慢，近几十年甚或停滞不前、难以改善。人们不仅要在目前的手段开展气动噪声研究，而且还要考虑在未来的计算条件下开展气动声学问题的研究。目前无论是工程应用还是理论研究，要求气动声学理论能提供声波运动及声流相互作用规律，以及在理论上提供了更为清晰的物理图象。

李政道提到[1]：“20 世纪的文明是微观的，…我认为 21 世纪微观和宏观应结合成一体。…目前微观和宏观的冲突己经非常尖锐，靠一个不能解决另一个，把它们联系起来会有一些突破，这个突破会影响科学的未来。”如有一个公共的力学体系能将气动声学的微观和宏观研究联系起来，为气动声学研究找出一种新途径，Hamilton 力学就有这样优点。Hamilton 力学就具有这样优点。如有一个公共的力学体系能将气动声学的微观和宏观研究联系起来，为气动声学研究找出一种新途径，Hamilton力学就有这样优点。从某种意义上讲，哈密顿体系是更本质和更重要的，一切保守体系都可以在哈密顿体系下统一表示。

文献[2论述了在Hamilton 系统下，以谐振子势能模型结合群论建立数学模型讨论了一维气体分子链中声传播的问题。

对于复杂的体系，组成体系的各粒子间的相互作用决定其能量状态。各相互作用以及处理中中心场使用近似方法，使得复杂体系的Schrodinger方程中有可能出现高次非谐振子势、极化等效势、环形非球振子势、势等高次正幂与逆幂势函数以及它们的叠加等不同的势场。对于不同势场，描述粒子运动规律的Schrodinger方程是不同的微分方程，但只有少数势场的Schrodinger方程才能得到其特征值的解析解，多数量子体系的Hamilton算数比较复杂，Schrodinger方程不能严格求解[3]。

任何体系在平衡位置附近的小振动，例如分子振动、晶格振动、原子核表面振动以及辐射场的振动等往往都可以分解成若干彼此独立的一维简谐振动[3]。简谐振动往往还作为复杂运动的初步近似[4]。

对于双原子分子谐振而言，应用上述简谐振子模型可以较好地近似描述双原子分子在低能量时的谐振行为。但是在实际上，由于双原子分子振动并不是简谐振动，振动能级也并不均匀，在常温下双原子分子几乎处于低能级上，这时双原子分子势能曲线与简谐振子的势能曲线在低能级振动时相近[5]。

本文在原来的 Hamilton 谐振子数学模型基础上，通过引入Morse 势能函数代替原来的简谐振子势模型，研究了一维气体分子链中声传播的问题。从能量的概念出发，将声传播问题转换成求解谐振子的波函数以及能量本征值的问题[]。本文与文献[2]的不同在于：分子间只与相邻的分子相互作用，取Morse势能函数，数值求解分子控制方程时用四阶辛算法，同时比较了经典方法与量子谐振子模型计算的一维声压。

# 1模型建立的理论基础

本文选取一维体系进行研究，空气成分中占绝大部分的是氮气和氧气，他们都是双原子分子[7]。分子间互作用原理详见文献[2]。

可证明长波极限下，一维分子链的振动可化为连续体弹性波。一维分子链的运动方程为：

$$
\begin{array} { l } { { \displaystyle m \beta _ { n } ^ { \mathrm { a c } } = \beta ( \mu _ { n + 1 } + \mu _ { n - 1 } - 2 \mu _ { n } ) } } \\ { { \displaystyle ~ = \beta a ^ { 2 } \left( \frac { \mu _ { n + 1 } - \mu _ { n } } { a } - \frac { \mu _ { n } - \mu _ { n - 1 } } { a } \right) } } \\ { { \displaystyle a } } \end{array}
$$

在长波极限下，位移可以看作连续变化的，即：

$$
m \beta \frac { \Re } { n } = \beta a ^ { 2 } \mu _ { x x }
$$

而弹性波方程为：

$$
\displaystyle \mathbf { \beta } ^ { \mathbf { \ 8 } } = \nu ^ { 2 } \mu _ { x x }
$$

对比得波速为：

$$
\nu = \sqrt { \frac { \beta } { m } } a
$$

设试探解为：

$$
u _ { n } = A e ^ { - i \left( \omega t - n a q \right) }
$$

式中 $A$ 为振幅， $\omega$ 为圆频率， $q$ 为波矢，与波长$\lambda$ 的关系为： $\scriptstyle q = 2 \pi / \lambda , n a q$ 为第 $\mathfrak { n }$ 个分子振动的位相，将（2）代入（1)，容易求得 $\omega$ 与 $q$ 的关系为：

$$
{ \omega } ^ { 2 } = \frac { 2 \beta } { m } { \left( 1 - \cos q a \right) }
$$

由式（6）不难看出，当 $n a - m a = l \lambda$ ，即第 $\mathfrak { n }$ 和第$\mathbf { m }$ 个分子的位移相等，所以式（6）所描述的原子围绕平衡位置运动是以行波的形式在气体中传播的，是气体介质中分子子的一种集体运动形式。

由色散关系可得到波的相速度和群速度为：

相速度：

$$
\nu _ { _ { p } } = { \frac { \omega } { q } } = a { \left( { \frac { \beta } { m } } \right) } ^ { \gamma _ { 2 } } { \frac { \sin { \frac { q a } { 2 } } } { \frac { q a } { 2 } } }
$$

群速度：

$$
\nu _ { g } = { \frac { d \omega } { d q } } = a { \left( { \frac { \beta } { m } } \right) } ^ { \gamma _ { 2 } } \cos { \frac { 1 } { 2 } } q a
$$

由此可以看到，由于分子的不连续性，波的相速度不再是常数。但当 $q {  } 0$ 时， $\nu _ { p } = a \Bigg ( \frac { \beta } { m } \Bigg ) ^ { \smash { \not \zeta _ { 2 } } }$ 为一常数。这是因为当波长很大时，一个波长范围含若干分子，相邻分子的位相差很小，分子的不连续效应很小，波接近于连续媒质中的弹性波。

# 2 计算模型

文献[1]论述了在Hamilton 系统下，以谐振子势能模型结合群论建立数学模型讨论了一维气体分子链中声传播的问题。本文基于文献[]基础上，程序编译思想如下图1所示。

基于群论及谐振子模型的声传播方法步骤为：

1、先将声波传播问题转换成求解 Schrodinger方程，确定波函数及能量本征值（能级)。这里用谐振子的Schrodinger方程，后续研究可以再考虑复杂体系叠加势的含时 Schrodinger方程;

2、求解分子正则运动方程，解久期方程，得振动频率及振幅；

3、通过声能与声压的关系获得声场有关量。

振动 传播子 配分函数 气体的热力学量

# 3分子Morse势能函数谐振子配分函数

对于双原子分子谐振而言，应用简谐振子模型可以较好地近似描述双原子分子在低能量时的谐振行为．但是在实际上，由于双原子分子振动并不是简谐振动，振动能级也并不均匀，在常温下双原子分子几乎处于低能级上，这时双原子分子势能曲线与简谐振子的势能曲线在低能级振动时才相近。图 2表示谐振子、Morse势能函数振势能曲线，图3表示谐振子、Morse势振子分子间作用。

这里用Morse 势能函数方法，它可以更好地接近双原子分子谐振的实际情况.下面对此加以讨论，引入双原子分子势能函数

$$
V \left( r \right) = D _ { e } \left[ 1 - \exp \left( - a \left( r - r _ { e } \right) \right) \right] ^ { 2 }
$$

式中：

$D _ { e }$ —一分子从势能曲线最低点到孤立原子 $( r  \infty )$ 时的能量; $r _ { e }$ —一双原子的平衡核间的距离; $a$ 与分子有关的参量。

当 $( r - r _ { e } )$ 很小时略去其高阶项，就可以利用势能函数级数展开式求解Schrodinger方程。这里，需要确定能量零点，可分别取势能曲线最低点或者分子振动基态为能量零点作为能量零点。

对势能函数 $V ( r )$ 平衡点做Taylor级数展开为

$$
V \left( r \right) = V \left( r _ { e } \right) + \left( \frac { d V } { d r } \right) _ { r = r _ { e } } \left( r - r _ { e } \right)
$$

$$
+ \frac { 1 } { 2 ! } \Bigg ( \frac { d ^ { 2 } V } { d r ^ { 2 } } \Bigg ) _ { r = r _ { e } } \left( r - r _ { e } \right) ^ { 2 }
$$

$$
+ \frac { 1 } { 3 ! } \left( \frac { d ^ { 3 } V } { d r ^ { 3 } } \right) _ { r = r _ { e } } \left( r - r _ { e } \right) ^ { 3 } + { \bf K }
$$

如果取势能曲线最低点作为能量零点，可以得到它的振动能级及其相应的配分函数分别为：

$$
\left\{ \begin{array} { l l } { \displaystyle E _ { i } = \left( n + \frac { 1 } { 2 } \right) h \nu _ { e } - \left( n + \frac { 1 } { 2 } \right) ^ { 2 } x _ { e } h \nu _ { e } } \\ { \displaystyle q _ { \nu } = \sum _ { n } \exp \left\{ - \left[ \left( n + \frac { 1 } { 2 } \right) - \left( n + \frac { 1 } { 2 } \right) ^ { 2 } x _ { e } \right] \frac { h \nu _ { e } } { k T } \right\} } \end{array} \right.
$$

式中 $\nu _ { e } = \frac { a } { \pi } \sqrt { \frac { D _ { e } } { 2 \mu } } , x _ { e } = \frac { h \nu _ { e } } { 4 D _ { e } }$ 称为非简谐常量，可由光谱数据求得。

如果取分子振动基态为能量零点，则振动能级与相应的配分函数可写成如式（12）所示。

$$
\left\{ \begin{array} { l } { \displaystyle E _ { i } ^ { \prime } = \Big [ n - n \big ( n + 1 \big ) x _ { e } \Big ] h \nu _ { e } } \\ { \displaystyle q _ { \nu } ^ { \prime } = \sum _ { n } \exp \left\{ - \Big [ n - n \big ( n + 1 \big ) x _ { e } \Big ] \frac { h \nu _ { e } } { k T } \right\} } \end{array} \right.
$$

由于双原子Morse势能函数中的 $D _ { e }$ 是双原子从平衡位置离解成2个相距无限远的原子所需的能量，因此振动能级 $E _ { \nu }$ 最大为 $D _ { e }$ ，与此相应的求和的分子数 $n$ 应取为上限 $n _ { \mathrm { m a x } }$ ，它由式（13）确定，即

$$
D _ { e } = \left[ \left( n _ { \operatorname* { m a x } } + \frac { 1 } { 2 } \right) - \left( n _ { \operatorname* { m a x } } + \frac { 1 } { 2 } \right) ^ { 2 } x _ { e } \right] h \nu _ { e }
$$

$$
\xrightarrow { \nVDash _ { \mathbb { X } _ { e } = \frac { h \nu _ { e } } { 4 D _ { e } } \nmid \mathbb { C } \lambda \sqrt { \mathbb { H } _ { \Psi } ^ { \mathbb { H } } } } } \ n _ { \operatorname* { m a x } } = \frac { 1 } { 2 x _ { e } } - \frac { 1 } { 2 }
$$

故上述不同能量零点的配分函数表达式分为

$$
\left\{ \begin{array} { l } { { \displaystyle { q _ { \nu } = \sum _ { n = 0 } ^ { \frac { 1 } { 2 x _ { e } - 2 } } \exp \left\{ - \left[ \left( n + \frac { 1 } { 2 } \right) - \left( n + \frac { 1 } { 2 } \right) ^ { 2 } x _ { e } \right] \frac { \theta _ { \nu e } } { T } \right\} } } } \\ { { \displaystyle { \frac { 1 } { 2 x _ { e } - 2 } \sum _ { n = 0 } ^ { \frac { 1 } { 2 x _ { e } - 2 } } \exp \left\{ - \left[ n - n ( n + 1 ) x _ { e } \right] \frac { \theta _ { \nu e } } { T } \right\} } } } \end{array} \right.
$$

式中： $\theta _ { \nu e }$ 双原子分子振动特征温度，它等于

![](images/5d162b6ba47355dbd2fb614aff6d6c9a88b34d2bd76b14c7b734d5ddca88530a.jpg)

![](images/51167b45bc083d08cc51dbce5d0df9552da745953fa750dbf7a2a4b5bd663304.jpg)  
图2谐振子、Morse势能函数振势能曲线 Fig.2 Vibrational potential energy curve of harmonic oscillator and Morse potential energy function   
图3谐振子、Morse势振子分子间作用  
Fig.3 Interaction of harmonic oscillator and Morse potential vibrator of molecule

# 4能级与宏观量的联系

如果已知气体的自由能函数 $F ( T , V )$ ， $V$ 为体积，就可以根据：

$$
p = - ( \frac { \hat { \partial } \boldsymbol { F } } { \hat { \partial } \boldsymbol { V } } ) _ { \boldsymbol { T } }
$$

写出气体的状态方程。自由能函数可以一般地写成:

$$
F = - k T \ln Z
$$

$Z$ 为配分函数：

$$
{ \cal Z } = \sum _ { i } e ^ { - E _ { i } } { \bf \mathit { \Sigma } } ^ { }
$$

连加式是对所有分子的能级 $E _ { i }$ 相加。

能级 $E _ { i }$ 除包括分子处于格点时的平衡气体的能量 $U ( V )$ 外，还有各波的振动能： $\sum _ { j } ( n _ { j } + \frac { 1 } { 2 } ) \hbar \omega _ { j } , j$

标志各不同波， $n _ { j }$ 为相应的量子数。配分函数 $Z$ 包括系统的所有量子态，因此应分别对每个 $n _ { { } _ { j } } = 0$ ，1,2，…相加，从而得到：

$$
\begin{array} { c } { { Z = e ^ { - U _ { k T } } \displaystyle \prod _ { j } e ^ { - \frac { 1 } { 2 } ( h \omega _ { j } { \Bigg / } _ { k T } ) } \left[ \displaystyle \sum _ { n j = 0 } ^ { \infty } e ^ { - n h \omega _ { j } } \right] } } \\ { { = e ^ { - U _ { k T } } \displaystyle \left[ \frac { 1 } { 1 - e ^ { - h \omega _ { j } } { \Bigg / } _ { k T } } \right] } } \end{array}
$$

代入自由能公式（9）得到：

$$
F = U + k T { \sum _ { j } } \Biggl [ { \frac { 1 } { 2 } } { \frac { h \omega _ { j } } { k T } } + \ln ( 1 - e ^ { - h \omega _ { j } } / \ker ) \Biggr ]
$$

当体系体积改变时，波频率也将改变，所以上式除 $U$ 以外，各频率 $\omega _ { j }$ 也是宏观参量 $V$ 的函数。根据（12)对 $V$ 求微商，得到：

$$
p = - \frac { d U } { d V } - \sum _ { j } \Biggl ( \frac { 1 } { 2 } h + \frac { h } { e ^ { \displaystyle h \omega _ { j } } { / } _ { K T - 1 } } \Biggr ) \frac { d } { d V }
$$

上式包含了各振动频率对的 $V$ 依赖关系，因此具有很复杂的性质。格律乃森针对这种情形，提出一个有用的近似。如把上式写成：

$$
p = - \frac { d U } { d V } - \sum _ { j } \left( \frac { 1 } { 2 } h + \frac { h } { e ^ { h \omega _ { j } } / \mathit { K T - 1 } } \right) \frac { d \ln \omega _ { j } } { d V }
$$

其中式（22）括号内是平均振动能。

式(22)中表征频率随体积变化的 $\frac { d \ln \omega _ { j } } { d \ln V }$ 是一个无量纲的量，假设它近似对所有振动相同，这样式(22)就简化为下列近似状态方程：

$$
p = - { \frac { d U } { d V } } + \gamma { \frac { \overline { { E } } } { V } }
$$

其中 $\overline { { E } }$ 表示气体的平均振动能：

$$
\gamma = - { \frac { d \ln \omega } { d \ln V } }
$$

γ为常数。一般 $\omega$ 随增 $V$ 加而减小， $\gamma$ 具有正的数值。

# 5声传播模拟及分析

空气中 $1 5 ^ { \circ } \mathrm { C }$ 时声速为 $3 4 0 \mathrm { ~ m / s ~ }$ ，假设各个振子振前都处于基态， $n _ { i } = 0$ 。这里，由于同核双原子分子 $N _ { 2 }$ 、 $O _ { 2 }$ 属于 $D _ { \infty h }$ 群，计算时以 $D _ { \infty h }$ 群操作。简便起见，选取点震源为 $\xi = \sin ( 0 . 0 0 2 \pi t )$ ，则所考察的系统的总能量为：

$$
E = \sum _ { i } ^ { N } h \omega _ { i } ( n _ { i } + \frac { 1 } { 2 } ) = \frac { N } { 2 } h \omega
$$

从能量表达式看出，各个振子的波数或频率可以不一致，故一系列谐振子的组合相当于波包。

模拟过程中把波动过程看成是一种能量的流动。即声波对谐振子做功，体系就会发热膨胀。图4为谐振子模型模拟声波传播过程中，声压与密度变化关系图。图5表示的是用二阶有限差分法（FDTD）模拟的经典声传播过程中，声压随波程（时间与速度的乘积，波速为常量）变化示意图。通过比较，新模型声压随波程变化的趋势和经典声传播的趋势十分吻合。这说明本文数值计算有效。

![](images/12410d0ef214d37d7d6aba9f08f7ad75384b1456a37abf84e7dc393d6c957b13.jpg)  
图4声压与密度随波程变化比较图

![](images/8608e358171cb0622620f83495889adefa36d7ddf560f8c95c62ea68e59c6d3e.jpg)  
Fig.4Comparison chart between sound pressure and density   
图5一维二阶FDTD经典声传播声压示意图

Fig.5 Diagram of one-dimensional second order FDTD classic sound propagation sound pressure

6结论

本文基于用Morse势能函数的振子模型及群论方法对声在空气中传播建立了一个新的哈密顿数学模型。分析并讨论分子状态下，分子能级与配分函数的关联，并通过配分函数与热力学量之间的关系，以Morse 势能函数的振子模型构造的声传播模型求取声压及声能量。通过比较，经典方法与量子谐振子模型计算的一维声压吻合。

此外，新模型只考虑了声波传播问题，将问题转换成求解谐振子的波函数以及能量本征值的问题，除了离散关系和本征值方程的代数操作，它既不需要完整求解传播模型,也没有任何迭代计算。通过与有限差分法（FDTD）模拟结果的比较，新模型的数值计算有效。

# 参考文献

[1]高执棣，郭国霖．统计热力学导论[M].北京：北京大学 出版社，2004 GAO Zhidu,GUO Guolin. Introduction to Statistical Thermodynamics [M]. Beijing: Peking University Press, 2004   
[2]涂运冲，谢军龙，薛永飞，王嘉冰，吴克启．基于群论 及谐振子模型的声传播方法的研究[J].工程热物理学 报,2013,34(3): 450\~453 TU Yunchong, XIE Junlong, XUE Yongfei, WANG Jiabing,WU Keqi. Study of Group Theory and Harmonic Oscillator Model for Sound Propagation [J]. Journal of Engineering Thermophysics,2013,34(3): 450\~453   
[3]Zhou G D, Duan L Y. Bases of Structural Chemistry, (2rd edition)[M].Peking University Press,1995:26-39   
[4] Zeng JY.Quantum Mechanics,volume I(3rd edition) [M].Beijing: Science Press .2000.7:52-65   
[5]黄雪芬，薛永飞，涂运冲，吴克启．基于路径积分的声 传播微观特性的研究[J]．工程热物理学报．2012, 33(4):603-606 HUANG Xuefen，XUE Yongfei, TU Yunchong, WU Keqi. Study on the Microscopic Properties of Sound Propagation Based on the Path Integral [J].Journal of Engineering Thermophysics,2012,33(4):603-606   
[6]Wang, Z.J. High-order spectral volume method for benchmark aeroacoustic problems [C]. 41st Aerospace SciencesMeetingand Exhibit 6-9 January,Reno Nevada AIAA-2003-0880,2003   
[7]Shen J,Sha W,Huang Z X,Chen MS,Wu XL,High-oder Symplectic FDTD Scheme for Solving Time-dependent Schrodinger Equation[J]，Acta Physica Sinica，2012, 61(19): 190202-1\~190202-7