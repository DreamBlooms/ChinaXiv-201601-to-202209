# 建筑物防雷系统中分支导体在雷电流作用下的温升计算

![](images/05bc2befa5c5d600e94498b14aff47f3fece3f82350118ce02de5e8d3fedb0ce.jpg)

王杰男1987年生，硕士研究生，主要研究方向为过电压保护与防雷。

王　杰盛财旺²童 达杨雷} 王俊杰\~ 杨文宝（1.国家电网冀北电力有限公司检修分公司北京1024882.全球能源互联网研究院北京102211）

摘要：为对建筑物防雷系统中分支导体在雷电流作用下的温升进行估算，提出了两种计算导体温升的数学模型。该模型用于估算在假设电流密度均匀分布在导体横截面内以及考虑到暂态趋肤效应下电流密度非均匀分布两种情况下圆柱导体的温升。根据以上两种数学模型，分别估算出了分支导体3在不同雷电流幅值作用下的温升：幅值为 $1 0 0 \mathrm { k A }$ 时，其温升分别为 $2 . 2 5 ^ { \circ } \mathrm { C }$ 和 $2 . 7 5 ^ { \circ } \mathrm { C }$ ；当幅值为150kA时，其温升分别为$5 . 1 \mathrm { { ^ { c } } }$ 和 $6 . 1 8 \mathrm { { ^ \circ C } }$ ；当幅值为 $2 0 0 \mathrm { k A }$ 时，其温升分别为 $9 . 1 9 \mathrm { { ^ circ C } }$ 和 $1 1 ^ { \circ } \mathrm { C }$ 。本文还验证了该数学模型的研究结果。分析表明：文献中给出的测量数据与该模型计算得出的数据基本一致；防雷系统中各分支导体的温升确实会受到暂态趋肤效应的影响；该部分引起的导体额外温度上升很小可以忽略不计。

关键词：防雷系统雷电流分支导体温升电流密度 暂态趋肤效应中图分类号：TM863

![](images/3ab89b41afcd6fbfaa77b55afa22053a9e04521b1148f79d730485c918ac025f.jpg)

盛财旺男1986年生，博士，主要研究方向为雷电过电压防护。

# Calculation of the Temperature Rise of Conducting Branches in a Lightning Protection System of a Building Subjected to Lightning Current Impulses

Wang Jie'Sheng Caiwang²Tong $D a ^ { 1 }$ Yang Lei'Wang Junjie'Yang Wenbao （1. Ji Bei Electric Power Maintenance Company of State Grid Beijing102488 China 2.Global Energy Interconnection Research InstituteBeijing102211 China）

Abstract: In order to estimate the temperature rise of conducting branches in a lightning protection system of a building under lightning current, two mathematical models for the temperature rise of conductors were proposed. The models used to estimate the temperature rise in cylindrical conductors assumed both a uniform and non-uniform current density distribution by taking into account the transient skin effect. According to the two models,the temperature rise of the third conducting branch subjected to three different amplitude lightning currents was worked out. When the amplitude of lighting currents is 100kA,150kA and 200kA,respectively,the temperature rise of the conductor calculated based on the first model is 2.25, 5.1 and 9.19 degree centigrade, respectively, and the temperature rise under the second model is 2.75,6.18 and 11 degree centigrade, respectively. In addition, verification of the mathematical results were studied. The measured results in the literature are consistent with the results from the mathematical models.It is convincingly shown that conducting branches can be influenced by the transient skin effect.The additional temperature rise however,caused by the transient skin effect, is minimal, and can be neglected.

Keywords:Lightning protection system,lightning current, temperature rise, conducting branches,current density,transient skin effect

# 1 引言

近年来，由于高层建筑物的大量兴建，雷击事故不断增加。一旦建筑物遭受到直接雷击，强大的雷电流将沿着防雷系统中各导体分支传输，在防雷系统中产生雷电暂态过程。由于电流流过导体时会产生热效应，导体自身的温度就会升高。当防雷系统中分支导体温度过高且导体横截面积较小时，其机械强度就会降低，最终会导致高层建筑物坍塌并造成人员伤亡。为了避免这种情况的发生，有必要评估建筑物在遭受直接雷击时防雷系统中各分支导体的温升，从而更合理地确定导体的横截面积[1]。然而，目前国内外对防雷系统中分支导体的温升情况研究较少[2-4]，国外只针对建筑物上的避雷针在遭受雷击时的温升进行了研究，并已取得了一些成果[5]。针对上述情况，本文提出了两种计算导体温升的数学模型。首先，对建筑物防雷系统进行暂态计算，求出各分支导体的电流以及比能；其次，假设雷电流均匀分布在各分支导体中，根据热平衡条件推导出各分支导体的温升计算公式；再次，在考虑暂态趋肤效应的情况下，通过热传导方程，求出导体的电流密度分布并计算出导体的热损耗，从而估算出导体的温升；最后，将这两种方法计算得出的结果与文献[6]中测量的结果进行对比，从而验证这两种数学模型的有效性。

# 2 防雷系统中暂态电流分布及能量计算

本文选取呼家楼新街危改二号楼来进行雷电暂态计算。该建筑物是钢筋混凝土结构建筑，长$3 5 . 6 \mathrm { m }$ ，宽 $1 9 . 1 \mathrm { m }$ ，高 $5 6 . 5 \mathrm { m }$ 。根据国家标准（GB50057一94）把它定义为第三类建筑物。雷电流波形选取 $1 0 / 3 5 0 \mu \mathrm { s }$ 标准波形，其双指数形式如下[7]

$$
I ( t ) = A I _ { \mathrm { m a x } } \left[ \exp ( - a t ) - \exp ( - b t ) \right]
$$

式中， $A = 1 . 0 2 5$ $I _ { \mathrm { m a x } }$ 为雷电流幅值； $a { = } 2 . 0 5 \times 1 0 ^ { - 3 } { \mu \mathrm { s } } ^ { - 1 }$   
$b = 0 . 5 6 4 \mu \mathrm { s } ^ { - 1 }$ 。

该建筑的防雷系统钢筋结构图如图1所示。其底层接地钢筋的接地电阻为 $5 \Omega$ 。每隔两层绑扎一道均压带。整幢建筑物由多根钢筋相互连接，构成其笼式防雷系统[]。

![](images/9e233f2f0a8255bba73b42269712a503a8e8a00b188557bd437ffd8b66ee8429.jpg)  
图1建筑物防雷系统结构图

根据图1所示的结构图，计算出各分支导体的电气参数即电容和阻抗参数[8]。然后，运用EMTP-RV 软件搭建电路模型进行暂态分析计算[9。由于该防雷系统中导体分支数较多，本文选取上图所示电流分布较大的三段分支导体来进行暂态计算。当注入雷电流幅值为 $1 0 0 \mathrm { k A }$ 时，流过三段分支导体的暂态电流如图2所示。

![](images/2777c9fb8b812752b9201cfede8c92a4bab3caf5bc04cf680f7ac79b3ba21490.jpg)  
Fig.1The diagram of lightning protection system   
图2防雷系统中三段分支导体暂态电流波形 Fig.2The transient current waveform of the three conducting branches in lightning protection system

在载流导体的机械完整性方面，导体的比能是一个决定性因素并与其热现象有关[10]。根据三段分支导体的暂态电流，就可以求出各分支导体的比能，其计算公式如下[]：

$$
w ( t ) = \int _ { 0 } ^ { t } I ^ { 2 } ( t ) \mathrm { d } t
$$

根据式（2）可绘制出导体的比能波形，如图3所示。

![](images/44d2b58a7c6726f40a668d25663240cc8169dfc3bd830b82a0158999d49cace6.jpg)  
图3三段分支导体比能波形

# 3 导体温升计算数学模型

通过研究得出：导体的温升是由导体横截面的电流密度分布情况决定的[12-14]。本文提出两种计算导体温升的数学模型。第一种是：假设电流均匀分布在导体横截面中，根据热平衡条件推导出导体的温升计算公式[15]；第二种是：对于非均匀分布的电流密度，就要考虑导体的暂态趋肤效应。

# 3.1假设电流均匀分布在导体横截面中估计其温升

为了进行导体温升计算，选取一根半径为 $\boldsymbol { r }$ 的有限长圆柱型导体作为分析的对象，如图4所示。

![](images/b4a0d75a3ac9c13e638afc59ca8c2ab29a4922e1a1da94848427fd3f86bc6d84.jpg)  
Fig.3The specific energy waveform of the three conducting branches   
图4半径为 $\boldsymbol { r }$ 的分支导体坐标示意图 Fig.4Section of the conducting branch with radius $r$ in cylindrical coordinates

假设电流均为分布在横截面中，其面积为 $s$ 中 $S = \pi r ^ { 2 } .$ )。根据热平衡条件，可以推导出沿着 $z$ 轴在位置 $z$ 和 ${ \boldsymbol { z } } + \mathrm { d } { \boldsymbol { z } }$ 这段基本体积元内的温升方程。该导体在体积元（ $\mathrm { d } \nu = \pi r ^ { 2 } \mathrm { d } z$ ）内的热平衡条件可表示为[16-17]

$$
\mathrm { d } Q = ( Q _ { 1 } + Q _ { 2 } ) - ( Q _ { 3 } + Q _ { 4 } )
$$

式中， $\boldsymbol { Q } _ { 1 }$ 为在 $\mathrm { d } t$ 时间内穿过横截面积 $S$ 流入位置$z$ 处的热量； $\boldsymbol { Q } _ { 2 }$ 为体积是 $\mathrm { d } \nu$ 这段导体在 $\mathrm { d } t$ 时间内自身产生的热量； $\mathcal { Q } _ { 3 }$ 为在 $\mathrm { d } t$ 时间内穿过横截面积 $s$ 流出位置 ${ \boldsymbol { z } } + \mathrm { d } { \boldsymbol { z } }$ 处的热量； $Q _ { 4 }$ 为体积是 $\mathrm { d } \nu$ 这段导体在dt时间内通过外表面散发出的热量； $\mathrm { d } Q$ 为体积是 $\mathrm { d } \nu$ 这段导体在 $\mathrm { d } t$ 时间内剩余的热量。它们的关系式如下

$$
Q _ { \mathrm { 1 } } = - \lambda S \mathrm { d } t { \frac { \mathrm { d } T } { \mathrm { d } z } }
$$

$$
Q _ { 2 } = J ^ { 2 } \rho S \mathrm { d } t \mathrm { d } z
$$

$$
Q = - \lambda S \mathrm { d } T \left( \frac { \mathrm { d } T } { \mathrm { d } z } + \frac { \mathrm { d } T } { \mathrm { d } z } \mathrm { d } z \right)
$$

$$
\mathcal { Q } _ { 4 } = 2 \pi k _ { \mathrm { h c } } r \mathrm { d } z \mathrm { d } t ( T - T _ { 0 } )
$$

式中， $\lambda$ 为导体的热导率， $\boldsymbol { \mathrm { W / m \cdot \mathrm { { C } } } }$ ； $J$ 为电流密度，$\mathbf { A } / \mathbf { m } \mathbf { m } ^ { 2 }$ ， $T$ 为温度， $\mathrm { { ^ \circ C } }$ ； $\rho$ 为导体电阻率， $\Omega \cdot _ { \mathrm { m } }$ ， $k _ { \mathrm { { h c } } }$ 为热转换系数， $\mathrm { w / m } ^ { 2 } { \cdot } \mathrm { \bar { c } }$ 。

由于雷击建筑物是一个暂态过程并且流过建筑物中各分支导体的电流持续时间很短，因此导体散发到环境中的热量可以忽略不计。上式中 $k _ { \mathrm { h c } } = 0$ 且$( \mathrm { d } t / \mathrm { d } z ) = 0$ ，则根据式（3）～式（7）可以得出

$$
\mathrm { d } Q = J ^ { 2 } \rho S \mathrm { d } t \mathrm { d } z
$$

同时，在体积 $\mathrm { d } \nu$ 内导体剩余的热量可以通过下式求得

$$
\mathrm { d } Q = S c \mathrm { d } z { \frac { \mathrm { d } T } { \mathrm { d } z } } \mathrm { d } t
$$

从式（8）和式（9）可以得出导体温升的微分方程

$$
{ \frac { \mathrm { d } T } { \mathrm { d } z } } = J ^ { 2 } { \frac { \rho } { c } }
$$

一般来说，式（10）中 $\rho$ 和 $\mathbf { \Psi } _ { c }$ 不适合脱离温度

而单独考虑。对此，能够通过下式精确地表示出商p/c与温度之间的关系[18]

$$
\frac { \rho } { c } = \frac { \rho _ { \mathrm { 0 } } } { c _ { \mathrm { 0 } } } \left( 1 + \theta \Delta T \right) = \frac { 1 } { \gamma _ { \mathrm { 0 } } c _ { \mathrm { 0 } } } ( 1 + \theta \Delta T )
$$

根据式（10）和式（11)，可以得出导体的温升计算公式为

$$
\Delta T = \frac { 1 } { \theta } \left\{ \exp \left[ \frac { \theta w ( t ) } { c _ { 0 } \gamma _ { 0 } S ^ { 2 } } \right] - 1 \right\}
$$

式中， $\theta$ 为导体的温度系数； $c _ { 0 }$ 为导体的比热； $\gamma _ { 0 }$ 为导体的电导率。本文选取铁材料作为研究对象，则 $\theta = 6 . 5 1 \times 1 0 ^ { - 3 } ~ \mathrm { ~ \normalfont ~ C ~ } ^ { - 1 }$ ， $c _ { 0 } = 3 . 4 5 \times 1 0 ^ { 6 } \mathrm { W \cdot s / m ^ { 3 } \cdot \ s }$ ， $\gamma _ { 0 } =$ （204号 $1 . 0 ^ { 3 } \times 1 0 ^ { 7 } \Omega ^ { - 1 } \mathrm { m } ^ { - 1 }$ 。

# 3.2考虑导体在暂态趋肤效应情况下电流密度非均匀分布的温升计算

本文通过对导体电流密度进行数值积分，计算出导体的损耗。在该损耗的基础上，实现了在考虑暂态趋肤效应情况下对导体温升的估计。为了推导出各分支导体电流密度分布 $J ( \boldsymbol { x } , t )$ ，选取半径为 $\boldsymbol { r }$ 的圆柱型导体分支进行分析计算，该导体分支结构如图4所示。基于麦克斯韦方程组，在不考虑位移电流的作用下，导体电流密度可以通过贝塞尔微分方程来表示[18-20]。

$$
{ \frac { \partial ^ { 2 } J ( x , t ) } { { \partial x } ^ { 2 } } } + { \frac { 1 } { x } } { \frac { \partial J ( x , t ) } { \partial x } } = \gamma \mu { \frac { \partial J ( x , t ) } { \partial t } }
$$

根据文献[12]，该微分方程的解是通过拉普拉斯变换并且利用杜哈梅积分法求得的。首先，运用该方法得出适合于幅值为 $\boldsymbol { I } _ { \mathrm { r e } }$ 的矩形脉冲电流的贝塞尔微分方程的解。然后，通过拉普拉斯反变换将求得的杜哈梅积分转换到时域中，最终求得时域响应的解。

对于矩形脉冲来说，式（13）应用拉普拉斯变换可得到

$$
{ \frac { \partial ^ { 2 } J _ { \mathrm { r e } } \left( x , s \right) } { \partial ( \mathrm { i } k x ) ^ { 2 } } } + { \frac { 1 } { \mathrm { i } k x } } { \frac { \partial J _ { \mathrm { r e } } \left( x , s \right) } { \partial ( \mathrm { i } k x ) } } + J _ { \mathrm { r e } } \left( x , s \right) = 0
$$

式中， $k = \sqrt { \gamma \mu s }$ ; $\mu$ 为导体的磁导率， $\mathrm { V } { \cdot } _ { \mathrm { s / A } { \cdot } \mathrm { m } }$ ；i为虚数单位。

方程（14）的解可以通过以下形式来进行表示

$$
J _ { \mathrm { r e } } \left( x , s \right) = A ( s ) J _ { \scriptscriptstyle 0 } ( \mathrm { i } k x ) + B ( s ) N _ { \scriptscriptstyle 0 } ( \mathrm { i } k x )
$$

式中， $J _ { 0 } ( x )$ 为第一类0阶贝塞尔函数； $N _ { 0 } ( x )$ 为第二类0阶贝塞尔函数；积分常数 $A ( s )$ 和 $B ( s )$ 是由边界条件决定的[18]

由于 $N _ { 0 } ( x )$ 在 $x = 0$ 的时候是发散的，从物理意义上考虑，当 $x = 0$ 时，积分常数 $B ( s ) = 0$ 。因此，式（15）可化简为[18]

$$
J _ { \mathrm { r e } } ( x , s ) = A ( s ) J _ { \scriptscriptstyle 0 } ( \mathrm { i } k x )
$$

为了求出积分常数 $A ( s )$ ，需运用下面的关系式[19-20]

$$
\frac { \mathrm { d } J _ { \mathrm { r e } } ( x , t ) } { \mathrm { d } x } = \gamma \mu \frac { \mathrm { d } H ( x , t ) } { \mathrm { d } t }
$$

对式（17）进行拉普拉斯变换可得

$$
\frac { \mathrm { d } J _ { \mathrm { r e } } ( x , t ) } { \mathrm { d } x } = \gamma \mu s H ( x , t )
$$

根据安培环路定理，导体在 $x = r$ 处的磁场强度为

$$
H ( r , s ) = { \frac { I ( s ) } { 2 \pi r } }
$$

其中， $I ( s ) = I _ { \mathrm { r e } } / s$ 。

根据式（16)、式（18）和式（19）可求出积分常数

$$
A ( s ) = { \frac { \mathrm { i } k I _ { \mathrm { r e } } } { 2 \pi r J _ { 1 } ( \mathrm { i } k r ) } }
$$

将式（20）代入式（16）可得到方程（14）的 解为

$$
J _ { \mathrm { r e } } \left( x , s \right) { = } \frac { \mathrm { i } k I _ { \mathrm { r e } } J _ { \mathrm { 0 } } ( \mathrm { i } k x ) } { 2 \pi r s J _ { \mathrm { 1 } } ( \mathrm { i } k r ) }
$$

式中， $J _ { 1 } ( x )$ 表示第一类1阶贝塞尔函数。

为了求出时间函数 $J _ { \mathrm { r e } } ( x , t )$ ，需对式（21）进行拉普拉斯反变换。根据海维赛展开定理将式 (21)写成

$$
\frac { N ( s ) } { M ( s ) } = \frac { \mathrm { i } k I _ { \mathrm { { e } } } J _ { \mathrm { { 0 } } } ( \mathrm { i } k x ) } { 2 \pi r s J _ { \mathrm { { 1 } } } ( \mathrm { i } k r ) }
$$

则可以有

$$
J _ { _ { \mathrm { R } } } ( x , t ) = \sum _ { n = 1 } ^ { \infty } \frac { N ( p _ { n } ) } { M ^ { \prime } ( p _ { n } ) } \mathrm { e x p } ( p _ { n } t )
$$

式中， $p _ { n }$ 表示 $M ( s ) = 0$ 第 $n$ 个根。

根据式（21）～式（23)，最终可求得时间函数 $J _ { \mathrm { r e } } ( x , t )$ 为

$$
J _ { \mathrm { r e } } \left( x , t \right) = \frac { I _ { \mathrm { r e } } } { \pi r ^ { 2 } } \left\{ 1 + \sum _ { 0 } ^ { \infty } \frac { J _ { 0 } \Big [ \left( x / { r } \right) z _ { n } \Big ] } { J _ { 0 } \left( z _ { n } \right) } \times \exp \left( - \frac { z _ { n } ^ { 2 } } { \gamma \mu r ^ { 2 } } t \right) \right\}
$$

式中， $z _ { n }$ 表示贝塞尔函数 $J _ { 1 } ( z ) = 0$ 第 $n$ 个根。

利用式（24）和杜哈梅积分法，可以得到方程式（13）在时域上的解[21-22]

$$
J ( x , t ) = J _ { \mathrm { r e } } ( x , t ) I ( 0 ) + \int _ { 0 } ^ { t } J _ { \mathrm { r e } } ( x , \tau ) { \frac { \mathrm { d } } { \mathrm { d } t } } I ( t - \tau ) \mathrm { d } \tau
$$

由于图2中所求出的电流为离散的数据，因此需要对上式积分进行离散化处理。取 $t = n \Delta t$ ，且 $0 <$ $\tau \leqslant t$ ， $J ( x , 0 ) = 0$ ，则式（26）数值形式可表示为

$$
J ( x , \Delta t ) = \frac { \Delta \tau } { 2 } \left\{ \sum _ { m = 1 } ^ { M } D _ { 1 } J _ { \mathrm { r e } } \left[ x , ( m - 1 ) \Delta \tau \right] + \sum _ { m = 1 } ^ { M } D _ { 2 } J _ { \mathrm { r e } } \left( x , m \Delta \tau \right) \right\}
$$

$$
\begin{array} { l } { \displaystyle J \Big [ x , ( n + 1 ) \Delta t \Big ] = J ( x , n \Delta t ) + } \\ { \displaystyle \quad \quad \frac { \Delta \tau } { 2 } \sum _ { m = 1 } ^ { M } { D _ { 1 } J _ { \mathrm { r e } } \Big [ x , ( m - 1 ) \Delta \tau + n \Delta t \Big ] } + } \\ { \displaystyle \quad \quad \frac { \Delta \tau } { 2 } \sum _ { m = 1 } ^ { M } { D _ { 2 } J _ { \mathrm { r e } } } ( x , m \Delta \tau + n \Delta t ) } \\ { \displaystyle n = 1 , 2 , 3 \cdots N } \end{array}
$$

式（26）和式（27）中，

$$
D _ { 1 } = \frac { I ( \Delta t - m \Delta \tau ) - I [ \Delta t - ( m + 1 ) \Delta \tau ] } { \Delta \tau }
$$

$$
D _ { 2 } = \frac { I [ \Delta t - ( m - 1 ) \Delta \tau ) ] - I [ \Delta t - m \Delta \tau ] } { \Delta \tau }
$$

根据式（26）～式（29)，运用Matlab软件编写程序求出电流密度的离散数据。因此，导体分支的热损耗 $P$ 就可以通过下式求出[23-24]。

$$
P = \frac { 1 } { \gamma } \sum _ { i = 1 } ^ { n _ { 1 } } \sum _ { j = 1 } ^ { n _ { 2 } } 2 \pi i \Delta x [ J ( i \Delta x , j \Delta t ) ] ^ { 2 } \Delta t \Delta x
$$

式中， ${ \mathbf { \zeta } } n _ { 1 }$ 、 $n _ { 2 }$ 分别表示半径为 $\boldsymbol { r }$ 的导体径向离散数和时间离散数。

因此，导体分支通过热损耗产生的高于导体表面环境温度的温升

$$
\Delta T = \frac { P } { \pi r ^ { 2 } c }
$$

# 4导体温升模型计算结果与分析

由于上述图2和图3已知三段分支导体电流和比能的大小，下面就可以根据式（12）计算出导体的温升△T，如图5所示。

![](images/404054a694187c77bd7f8d93155225f06334d9a5dc510af7c90a4514bd7273de.jpg)  
图5电流均匀分布在导体横截面中时三段分支导体的温升 Fig.5Estimation of the temperature rise assuming a uniform current density distribution over the cross-section of the conductors

由图5可以看出三段分支导体的温升在起始阶段增长迅速，随着时间的增加导体的温升增长缓慢，当时间超过 $6 0 0 \mu \mathrm { s }$ 后，导体1和导体2的温升基本不变，这说明载流导体产生的能量主要集中在$6 0 0 \mu \mathrm { s }$ 以内；而对于导体3来说，温升变化主要在$7 0 0 \mu \mathrm { s }$ 以内。

在考虑导体暂态趋肤效应的情况下，根据式(24)、式（26）～式（29）可以求出三段导体在不同时间下的径向电流密度分布，如图6所示。

由图6可以看出，在雷电暂态过程开始的时间段里，电流密度 $J ( x , \ t )$ 主要集中在导体表面并且不断增加。当流过导体的电流达到最大值之后，电流密度随着时间的增加而不断减小，直到保持在某一数值不变。该图阐述了暂态趋肤效应对导体电流分布的影响。

为了更加合理地确定建筑物防雷系统分支导体横截面积的大小，本文选取防雷系统中电流最大的导体分支一一导体3进行分析，求出在注入不同幅值雷电流情况下导体横截面积与温升的关系，如图7所示。

![](images/98545ebf17dda460fb02480fb243d07fb3c72d3a8ce247a084bddab054e6671f.jpg)  
(a）导体分支1

![](images/a9198fb28399aa57d89c47cead4c027a7367d1b88e02746c5e08dab3b30df543.jpg)  
图6三段分支导体在不同时间下的电流密度分布Fig.6Current density distribution in the three conductingbranches for the sequential times

由图7可以看出，随着导体横截面积的不断增大，导体的温升逐渐减小；当导体的横截面积在$5 0 \mathrm { m m } ^ { 2 }$ 以内时，随着导体横截面积的减小，温升受雷电流幅值的影响越来越大。由于导体的温升直接影响它的机械强度，只有各分支导体的机械强度较大时，整幢建筑物才比较坚固。由此得出，建筑物防雷系统中各分支导体横截面积越大越好，但是从经济的角度考虑，导体横截面积则越小越好，这样才可以节省费用。综合以上因素，本文选取导体的横截面积为 $7 8 \mathrm { m m } ^ { 2 }$ 。

![](images/0b567c09ba3e5fa2abe7c4c7056aebac0346e80f5a19fd0243f6d609c7714daa.jpg)  
图7注入不同幅值雷电流导体3横截面积与温升关系 Fig.7Temperature rise of the third conductor for different cross-section ( $1 5 \sim 1 0 0 \mathrm { m m } ^ { 2 }$ ）energized fordifferent amplitude lightning currents

为了验证本文提出的导体温升计算方法的正确性，将计算得出的结果与文献[6]中的测量结果进行对比，见下表。

表横截面积为 $7 8 \mathrm { m m } ^ { 2 }$ 的三段分支导体计算结果与测量结果  
ab. Measure and calculated results for three $7 8 \mathrm { m m } ^ { 2 }$ conducting branches   

<html><body><table><tr><td>导体分支编号</td><td></td><td>1</td><td></td><td></td><td>2</td><td></td><td></td><td>3</td><td></td></tr><tr><td>雷电流幅值Im/kA</td><td>100</td><td>150</td><td>200</td><td>100</td><td>150</td><td>200</td><td>100</td><td>150</td><td>200</td></tr><tr><td>分支电流幅值Im/kA</td><td>29.824</td><td>44.736</td><td>59.649</td><td>32.262</td><td>48.393</td><td>64.524</td><td>38.176</td><td>57.264</td><td>76.352</td></tr><tr><td>比能 w/(A²·s)</td><td>127 267</td><td>286 351</td><td>509 069</td><td>246 607</td><td>554 866</td><td>986 428</td><td>488932</td><td>1 100 100</td><td>1 955 730</td></tr><tr><td>热损耗P/(W·s/m)</td><td>189.0</td><td>425.2</td><td>756.0</td><td>337.7</td><td>759.7</td><td>1350.6</td><td>744.2</td><td>1 674.5</td><td>2 976.8</td></tr><tr><td>温升△T/℃，公式（12)</td><td>0.58</td><td>1.31</td><td>2.34</td><td>1.13</td><td>2.55</td><td>4.57</td><td>2.25</td><td>5.10</td><td>9.19</td></tr><tr><td>温升△T/C，公式（31)</td><td>0.70</td><td>1.57</td><td>2.79</td><td>1.25</td><td>2.80</td><td>4.98</td><td>2.75</td><td>6.18</td><td>11.0</td></tr><tr><td>△T/C，测量值[6]</td><td>0.6</td><td>1.3</td><td>2.3</td><td>1.1</td><td>2.6</td><td>4.6</td><td>2.1</td><td>5.0</td><td>9.1</td></tr></table></body></html>

由上表可以得出：三段分支导体的温升测量结果与用式（12）和式（31）计算出来的结果非常接近。从而验证了本文提出的导体温升算法的有效性。基于以上研究，得出暂态趋肤效应对导体温升的影响很小，可以忽略不计。因此，导体的温升就可以直接运用由电流密度均匀分布情况下的数学模型得出的式（12）计算求出。

# 5 结论

当建筑物遭受直击雷时，就会在防雷系统中的各圆柱型导体产生热效应。本文提出了两种便于计算圆柱型导体分支温升的数学模型表达式，这两种表达式是通过考虑导体电流密度均匀分布和非均匀分布两种情况推导出来的。虽然各分支导体受到趋肤效应的影响，由上述计算的结果可以看出该部分对导体温升的影响很小可以忽略不计。考虑到导体的加热和机械强度标准，需要为建筑物防雷系统合理地选择导体的材料和横截面积。通过以上两种数学模型求出的结果与文献中测量的结果基本一致，这就充分验证了这两种数学模型的有效性。

# 参考文献

[1] 中国机械工业联合会主编．中华人民共和国国家 标准GB50057—2010 建筑物防雷设计规范[S]．北 京：中国计划出版社，2010.   
[2] 雷成华，刘刚，李钦豪．BP神经网络模型用于 单芯电缆导体温度的动态计算[J]．高电压技术, 2011,37(1): 184-189. Lei Chenghua,Liu Gang,Li Qinhao.Dynamic calculation of conductor temperature of singlecable using BP neural network[J]. High Voltage Engineering, 2011, 37(1): 184-189.   
[3]李亚西，张慧媛，范霄汉，等．高温超导电缆 在故障状态下的温升计算[J]．超导技术，2013, 41(9): 37-42. Li Yaxi, Zhang Huiyuan, Fan Xiaohan, et al. Temperature rise calculation of high temperature superconducting cable under fault conditions[J]. Super Conductivity, 2013,41(9): 37-42.   
[4] 王羽，李晓萍，罗思敏，等．垂直型直流接地极暂 态温升计算与试验[J]．中国电机工程学报，2013, 33(1): 1-7. Wang Yu, Li Xiaoping,Luo Simin,et al. Test and computation for vertical ground electrode's transient temperature rise[J]. Proceedings of CSEE,2013, 33(1): 1-7.   
[5] Rakov V A, Uman M A. Lightning physics and effects[M]. Cambridge University Press,2003.   
[6] Paisios M P, Karagiannopoulos C G, Bourkas P D. Estimation of the temperature rise in cylindrical conductors subjected to heavy $1 0 / 3 5 0 \mu \mathrm { s }$ lightning current impulses[J]. Electric Power Systems Research,2008,78(1): 80-87.   
[7] 张小青．建筑物内电子设备的防雷保护[M].北京： 电子工业出版社，2000.   
[8] Zhang Xiaoqing. A circuit approach to the calculation of lightning transients in cage-like multiconductor systems[J]. International Journal of Electrical Engineering Education, 2010,47(2): 213-222.   
[9] 曹玉胜，陈允平．图形化电磁暂态仿真软件 EMTP-RV及其应用[J]．高电压技术，2007, 33(7): 154-158. Cao Yusheng, Chen Yunping. Application of EMTPRV graphic software of electromagnetic transient simulation[J]. High Voltage Engineering,2007, 33(7): 154-158.   
[10]Horvarth T. Computation of lightning protection[M]. Research Studies Press, 1991.   
[11]Heidler F. Calculation of lightning current parameters[J]. IEEE Transactions Power Delivery, 1999,14(2): 399-404.   
[12]Miller K W. Diffusion of electric current into rods, tubes and flat surfaces[J].AIEE Trans.1947,66(1): 1496-1502.   
[13]Valese L M.Diffusion of pulsed current in conductors[J]. Journal of Applied Physics,1954, 25(2): 225-228.   
[14]Rusck S. The losses in linear systems energized by exponential impulses[J]. American Society of Engineers and Architects Research,1961,10(6): 45- 49.   
[15]Polykrati A D, Paisios M P, Karagiannopoulos C G, et al. Model for temperature estimation of electric couplings suffering heavy lightning currents[J]. IET Proceedings Generation Transmission and Distribution,2004,151(1): 90-94.   
[16]包科达．热物理学基础[M]．北京：高等教育出版 社，2004.   
[17]Cengel Y A. Introduction to thermodynamics and heat transfer[M]. Mc Graw-Hill,1997.   
[18]Bowman F. Introduction to bessel functions[M]. Dover Publications,1958.   
[19]Kreyszig E. Advanced engineering mathematics[M]. 8th Edition,John Wiley &Sons,Incorporated,1999.   
[20]Kupfmuller K. Einfuhrung in die theoretische elektrotechnik,auflage[J]. Springer-Verlag,1984, 11(2): 153-162.   
[21]Greenwood A. Electrical transients in power systems[M]. Wiley-Interscience,1971.   
[22］李竹英．杜哈梅尔积分的全解析算法[J]．华中理 工大学学报，1994，22(4)：30-35.