# 多孔介质突变界面处两相可压缩流体界面连接条件

# Interface Connection Conditions Of Two-Phase Compressible Fluid At ImmovableJump Interface In Porous Media彭小龙 邓鹏 朱苏阳 王超文 吴昊强

Peng, Xiaolong, Deng,Peng， Zhu,Su ‘yang, Wang Chaowen, Wu Haoqiang (State Key laboratory of Oil and Gas Reservoir Geology and Exploration, Southwest Petroleum University, Chengdu)

摘要：多孔介质间突变界面在油气藏开发中广泛存在。传统的渗流理论认为压力和达西速度在非连续界面处是连续的，我们在以往的研究对其进行了证伪。多孔介质物性突变界面为固定界面，本文在前期不可压缩流体的基础上，以气-水两相为例，考虑流体的压缩性，建立了这类突变界面处流体压力和渗流速度的连接条件。研究结果表明，在多孔介质固定的物性突变界面：（1）总体压力必然连续，但各相流体压力可以不连续；（2）总渗流速度相等，但各相流体的渗流速度可以不连续；（3）固定突变界面与移动突变界面的连接条件不同，不能用Rankine-Hugoniot条件描述；（4）根据突变界面的连接条件以及两相达西公式根据界面两端压力以及流体分布可计算出跨物性突变界面的各相流体的流速，跨物性的突变界面的流量应取上游值。

Jump interface in porous media exists widely in oil and gas reservoirs during development. The traditional seepage theory holds that the pressure and Darcy velocity are continuous at the discontinuous interface,and we have falsified them in previous studies.In this paper,taking gas-water phase as an example and considering the compressibity ofthe fluids,the connection conditions of phase pressures and Darcy velocitiesatthe immovable jumpinterface are established.The results show that:(1)the total pressure is always continuous,but the phase pressure of each phase canbe discontinuous;(2)The total Darcy velocityat the both sides are equal,but the phase Darcyvelocity probably discontinuous;(3)The connection conditions of fixed jump interfacedo notcomfort to Rankine - Hugoniot conditions, which are different from mobile jump interface,i.e.flood front which

Key words: Abrupt interface; Connect condition; Global pressure; Two-phase seepage   
Financed by: National Natural Science Foundation of China (Grant No.51474179);National Oil and Gas Major Project   
2016ZX05053; 2016ZX05066; 2016ZX05015)

大家在写论文时写上下面四个项目作为支助国家油气重大专项2016ZX05015；国家油气重大专项2016ZX05066  
国家油气重大专项2016ZX05053

# 1.前言

突变界面在油气藏中广泛存在，例如储层的层间差异、原始的油气水界面、生产过程中注水或注气前缘、化学驱油前缘、边底水锥进界面、基岩与裂缝系统的国连接界面、井筒与储层的连接面、压裂缝与储层的交界面，相关的多相渗流问题在数学上称为Neumann 问题。两相渗流突变界面处的连接条件是渗流数学模型的重要组成，是时空行流体界面跟踪(示踪剂)、计算油气井产量、描述跨类型或跨尺度多孔介质流体渗流规律、相渗测试、构建油藏数值模型等多相渗流领域的基础理论问题。根据渗流文献，在多孔介质突变界面处流体各相压力和渗流速度连续。即：

$$
\begin{array} { c } { { \nu _ { w } ^ { - } = \nu _ { w } ^ { + } , \nu _ { g } ^ { - } = \nu _ { g } ^ { + } } } \\ { { { } } } \\ { { p _ { g } ^ { - } = p _ { g } ^ { + } , p _ { w } ^ { - } = p _ { w } ^ { + } } } \\ { { { } } } \\ { { p _ { c } ^ { - } = p _ { c } ^ { + } } } \end{array}
$$

根据质量守恒方程，单位时间内微元内流体变化流入微元的流量流出微元的流量。对于移动界面，体积为0，没有源汇项，则有，流入微元的流量流出微元的流量=0。Hassanizadeh,S.M.,&Gray,W.G.(1989)用物质守恒方程对其进行了证明。针对界面两侧区域毛管力不同的情况，作者在文献中对传统的界面条件进行质疑，然后根据物质守恒方程和两相渗流公式推导了新的界面条件以及跨突变界面的渗流公式[1,2]。气-液两相驱替界面具有三个特征：（1）多孔介质物性突变界面不随时间不断移动；（2）在多孔介质的突变界面处流体分布可能不连续；（3）气体压缩性高，驱替过程需要考虑压缩性。所以本文将在前期不可压缩流体两相突变界面条件的研究基础上，考虑流体的压缩性，以气-水两相为例，研究多孔介质突变界面处，气-液两相压力和渗流速度的连接条件。

# 2传统突变界面条件面对的挑战[1]

（1）突变界面的连接条件针对界面两侧不同的质点，建立的是不同质点压力的连接条件和不同渗流速度的连接条件（如图1），该条件所描述的并非突变界面上同一流体质点的流速和压力。传统的渗流理论认为界面体积为0，根据质量守恒方程得出流入突变界面的流量等于流出突变界面的流量这一结论虽然是正确的，但它描述的并非界面的条件。如图1所示，以一维为例，假如包括界面的薄层状微元厚度为 ${ \mathfrak { b } } \to 0$ ，流入微元的流速记为 $\nu _ { \ell } ^ { - }$ ，流出微元的流速记为 $\boldsymbol { \nu } _ { \ell } ^ { + } \left( \ell = o , w \right)$ ，两者的数量关系即为渗流速的连接条件，应满足根据质量守恒方程(2)，根据该方程并不能得出 $\nu _ { o } ^ { - } = \nu _ { o } ^ { + }$ ；而传统的渗流力学针对界面条件所用的质量守恒方程表达为(3)。Hassanizadeh,S.M.,&Gray 试图证明由（2）可以得到（3），但我们发现证明过程有误。

$$
\left\{ \begin{array} { l l } { \displaystyle \int _ { x ^ { - } } ^ { x _ { \Gamma } } \displaystyle \frac { \widehat { \mathcal { O } } } { \partial t } \big ( \phi ^ { - } S _ { \ell } ^ { - } \big ) + \int _ { x _ { \Gamma } } ^ { x ^ { + } } \displaystyle \frac { \widehat { \mathcal { O } } } { \widehat { \mathcal { O } } t } \big ( \phi ^ { + } S _ { \ell } ^ { + } \big ) + \Big ( A ^ { - } \nu _ { \ell } ^ { - } - A ^ { + } \nu _ { \ell } ^ { + } \Big ) = 0 \quad } & { \big ( \ell = o , w \big ) } \\ { \displaystyle \nu _ { \ell } ^ { - } = - K ^ { - } \lambda _ { \ell } ^ { - } \displaystyle \frac { d p _ { \ell } ^ { - } } { d x } , \nu _ { \ell } ^ { + } = - K ^ { + } \lambda _ { \ell } ^ { + } \displaystyle \frac { d p _ { \ell } ^ { + } } { d x } \quad } & { \big ( \ell = o , w \big ) } \end{array} \right.
$$

$$
\left\{ \begin{array} { l l } { \boldsymbol { \nu } _ { \ell } ^ { - } = \boldsymbol { \nu } _ { \ell } ^ { + } } \\ { \boldsymbol { p } _ { \ell } ^ { - } = \boldsymbol { p } _ { \ell } ^ { + } } \end{array} \right. \qquad \left( \ell = o , w \right)
$$

![](images/2d55885e05cbe0e97824129cf95cac71b18d019ce0ac7fd90eaa49261c588f34.jpg)  
图1界面条件与界面上质点守恒方程所指对象

![](images/2c00c491c24a03b35a399ad94335a135f9f8ca7c5a0931d7a531b2b8dbf8bb2b.jpg)  
图2包括驱替界面的江薄层状微元示意图

（2）研究一维水驱油的 Buckley-Leveret方程的解析解显示渗流速度在前缘界面处不连续分布，这与传统的界面条件（如公式(1)）明显矛盾。此外De Neef,M.J.,& Molenaar,J.(1997)针对突变界面两侧毛管力曲线不相同，对传统的界面条件提出了改进，他们认为润相流体压力连续，但非润湿相压力可以不连续;

(3）调研文件我们发现虽然(1)表示的界面条件广泛见诸文献，但并没有得到真正应用，因为公式(1)所示的传统的界面条件，以及两相流达西公式，突变界面处传导率应该为界面两侧的调和平均值，它不能正确反映真实的渗流过程，所以被单点上游权（SPU）和其它高阶上游权方法取代。

$$
\nu _ { \ell } ^ { \Gamma } = \frac { 2 T _ { \ell } ^ { - } T _ { \ell } ^ { + } } { T _ { \ell } ^ { - } + T _ { \ell } ^ { + } } \Big ( p _ { \ell } ^ { - } - p _ { \ell } ^ { + } \Big ) , \qquad \big ( \ell = w , g \big )
$$

其中： $T _ { \ell } ^ { - } = \frac { K ^ { - } k _ { r \ell } ^ { - } } { \mu _ { \ell } ^ { - } } \frac { 1 } { \Delta x ^ { - } } , T _ { \ell } ^ { + } = \frac { K ^ { + } k _ { r \ell } ^ { + } } { \mu _ { \ell } ^ { + } } \frac { 1 } { \Delta x ^ { + } }$

（4）从计算角度，即使在突变界面处，流体分布虽然突变但仍然连续的情况下，由于突变区分布厚度薄，将突变区简化为不连续界面，可实现在获得相近计算结果的前提下，大幅度减小计算量。

![](images/cb02b86d463c4e6c664e4f19f8e13a9c1c229fdefeb62aed1fa46a8b7bdb7129.jpg)  
图3将流体处突变但连续分布界面简化为不连续界面示意图（左：真实界面附近流体分布；右：简化后的不连续界面）

# 3.考虑突变界面的两相可压缩流体Darcy公式

# 3.1质量守恒方程

假设油气藏存在突变界面，界面位置不随时间变化，界面两侧储层的孔隙度，渗透率，流体压力，流体饱和度，孔隙度，岩石压缩性不同。整个油藏被突变界面Γ分割为两个子区域， $\Omega _ { a }$ 和 $\Omega _ { \mathrm { { b } } }$ (图 2)。每个子区域质量守恒方程满足微分方程：

$$
\left\{ \begin{array} { l } { \displaystyle \frac { \hat { \sigma } } { \partial t } \big ( \phi \rho _ { g } S _ { g } \big ) = - \nabla \cdot \big ( \rho _ { g } \nu _ { g } \big ) } \\ { \displaystyle \frac { \hat { \sigma } } { \partial t } \big ( \phi \rho _ { w } S _ { w } \big ) = - \nabla \cdot \big ( \rho _ { w } \nu _ { w } \big ) } \end{array} \right.
$$

式中下标 $\ell$ 为流体类型标记，可选气相和水相； $\phi$ 表示孔隙度； $\rho _ { \ell }$ 流体 $\ell$ 的密度 $\mathrm { { , K g / m ^ { 3 } } }$ ； $\nu$ 表示渗流速度，$m / d$ ；t表示时间,d。 $S _ { \ell }$ 表示流体饱和度。两种流体的饱和度有如下关系：

$$
S _ { \scriptscriptstyle { w } } + S _ { \scriptscriptstyle { g } } = 1
$$

引入地层体积系数的定义公式：

$$
B _ { g } = \frac { \rho _ { g s c } } { \rho _ { g } } , B _ { w } = \frac { \rho _ { w } } { \rho _ { w s c } }
$$

其中 $B _ { g }$ 表示气体在地层条件下的体积与地面气体休积的比值，亦可表示气体在地面的密度 $\rho _ { g s c }$ （单位 $\mathrm { k g / m ^ { 3 } }$ ）与地层密度 $\rho _ { g }$ （单位 $\mathrm { k g / m ^ { 3 } }$ ）的比值； $B _ { \mathrm { w } }$ 表示水在地层条件下的体积与地面条件也的体积，亦可表示水在地面的密度（20 $\rho _ { \it { w s c } }$ （单位 $\mathrm { k g / m } ^ { 3 }$ ）与地下密 $\rho _ { { } _ { w } }$ （单位 $\mathrm { k g / m } ^ { 3 }$ ）的比值。方程组（5）改写为：

$$
\left\{ \begin{array} { c } { \displaystyle \frac { \partial } { \partial t } \left( \phi \frac { S _ { g } } { B _ { g } } \right) = - \nabla \cdot \left( \frac { \nu _ { g } } { B _ { g } } \right) } \\ { \displaystyle \frac { \partial } { \partial t } \left( \phi \frac { S _ { w } } { B _ { w } } \right) = - \nabla \cdot \left( \frac { \nu _ { w } } { B _ { w } } \right) } \end{array} \right.
$$

将上述方程组左端关于时间的导数项展开，并引入岩石压缩系数 $c _ { \phi }$ （单位 $\mathrm { { M P a } ^ { - 1 } }$ ），气体压缩系数 $c _ { g }$ （单位 $\mathrm { { M P a } ^ { - 1 } }$ ）以及水压缩系数 $c _ { _ w }$ （单位 $\mathrm { { M P a } ^ { - 1 } }$ ），方程组改写为：

$$
\left\{ \begin{array} { l } { \displaystyle { \frac { \phi } { B _ { g } } \frac { \hat { \alpha } S _ { g } } { \hat { \alpha } t } + \frac { \phi S _ { g } } { B _ { g } } \big ( c _ { \phi } + c _ { g } \big ) \frac { \hat { \alpha } p } { \hat { \alpha } t } = - \frac { d } { d x } \bigg ( \frac { \nu _ { g } } { B _ { g } } \bigg ) } } \\ { \displaystyle { \frac { \phi } { B _ { w } } \frac { \hat { \alpha } S _ { w } } { \hat { \alpha } t } + \frac { \phi S _ { w } } { B _ { w } } \big ( c _ { \phi } + c _ { w } \big ) \frac { \hat { \alpha } p } { \hat { \alpha } t } = - \frac { d } { d x } \bigg ( \frac { \nu _ { w } } { B _ { w } } \bigg ) } } \end{array} \right.
$$

# 3.2储层物性突变界面处的渗流速度的连接条件

将程组（9）中气相方程和水相方程分别除以饱和度导数项的系数，然后相加得到两相整体流动方程

$$
\phi S _ { w } \left( c _ { \phi } + c _ { w } \right) \frac { \hat { \sigma } p _ { w } } { \hat { \sigma } t } + \phi S _ { g } \left( c _ { \phi } + c _ { g } \right) \frac { \hat { \sigma } p _ { g } } { \hat { \sigma } t } = - B _ { g } \frac { d } { d x } \left( \frac { \nu _ { g } } { B _ { g } } \right) - B _ { w } \frac { d } { d x } \left( \frac { \nu _ { w } } { B _ { w } } \right)
$$

式中气、水两相流体的渗流满足两相达西公式：

或

$$
\begin{array} { l l } { { \nu _ { \ell } = - K \lambda _ { \ell } \displaystyle \left( \frac { d p _ { \ell } } { d x } { - \rho _ { \ell } g \sin \alpha } \right) } } & { { \qquad \displaystyle \left( \ell = w , g \right) } } \\ { { \displaystyle \frac { d p _ { \ell } } { d x } = \rho _ { \ell } g \sin \alpha { - } \frac { \nu _ { \ell } } { K \lambda _ { \ell } } } } & { { \qquad \displaystyle \left( \ell = w , g \right) } } \end{array}
$$

$\lambda$ 表示流度， $\lambda _ { \ell } = \frac { k _ { r \ell } } { \mu _ { \ell } }$ ， $k _ { r \ell }$ 为流体 $\ell$ 的相对渗透率， $\mu _ { \ell }$ 表示流体 $\ell$ 的粘度， $\mathrm { \ m P a . s }$ ； $p _ { \ell }$ 为流体 $\ell$ 的压力，MPa;对方程（10）两侧在 $[ x _ { a } , x _ { b } ]$ 区域关于 $\mathbf { x }$ 做积分有：

$$
\int _ { x _ { a } } ^ { x _ { b } } \left( \phi S _ { w } \left( c _ { \phi } + c _ { w } \right) \frac { \hat { Q } p _ { w } } { \hat { Q } t } + \phi S _ { g } \left( c _ { \phi } + c _ { g } \right) \frac { \hat { Q } p _ { g } } { \hat { Q } t } \right) d x = \int _ { x _ { a } } ^ { x _ { b } } \left( - B _ { g } \frac { d } { d x } \left( \frac { \nu _ { g } } { B _ { g } } \right) - B _ { w } \frac { d } { d x } \left( \frac { \nu _ { w } } { B _ { w } } \right) \right) d x
$$

$[ x _ { a } , x _ { b } ]$ 区域包括突变界面，所以方程（13）左端（记为LHS）有：

$$
\begin{array} { l } { { \displaystyle L H S = \left( x _ { \mathrm { r } } - x _ { a } \right) \phi ^ { a } \Biggl ( S _ { w } ^ { a } \left( c _ { \phi } ^ { a } + c _ { w } ^ { a } \right) \frac { \hat { \mathcal { O } } p _ { w } ^ { a } } { \hat { \mathcal { O } } t } + S _ { g } ^ { a } \left( c _ { \phi } ^ { a } + c _ { g } ^ { a } \right) \frac { \hat { \mathcal { O } } p _ { g } ^ { a } } { \hat { \mathcal { O } } t } \Biggr ) } } \\ { { \displaystyle + \left( x _ { b } - x _ { \mathrm { r } } \right) \phi ^ { b } \Biggl ( S _ { w } ^ { b } \left( c _ { \phi } ^ { b } + c _ { w } ^ { b } \right) \frac { \hat { \mathcal { O } } p _ { w } ^ { b } } { \hat { \mathcal { O } } t } + S _ { g } ^ { b } \left( c _ { \phi } ^ { b } + c _ { g } ^ { b } \right) \frac { \hat { \mathcal { O } } p _ { g } ^ { b } } { \hat { \mathcal { O } } t } \Biggr ) } } \end{array}
$$

又因为有：

$$
B _ { g } \frac { d } { d x } \Bigg ( \frac { \nu _ { g } } { B _ { g } } \Bigg ) = \nu _ { g } + \nu _ { g } c _ { g } \frac { d p _ { g } } { d x } = \nu _ { g } + \nu _ { g } c _ { g } \Bigg ( \rho _ { g } g \sin \alpha - \frac { \nu _ { g } } { K \lambda _ { g } } \Bigg )
$$

$$
B _ { w } \frac { d } { d x } \Bigg ( \frac { \nu _ { w } } { B _ { w } } \Bigg ) = \nu _ { g } + \nu _ { w } c _ { w } \frac { d p _ { w } } { d x } = \nu _ { g } + \nu _ { w } c _ { w } \Bigg ( \rho _ { w } g \sin \alpha - \frac { \nu _ { w } } { K \lambda _ { w } } \Bigg )
$$

将（15）（18）代入方程（13）右端（记为RHS）各项，于是：

$$
\int _ { x _ { a } } ^ { x _ { b } } \left( - \frac { d \left( \nu _ { g } + \nu _ { w } \right) } { d x } \right) d x + \int _ { x _ { a } } ^ { x _ { b } } \left( - \nu _ { g } \cdot c _ { g } \left( \rho _ { g } g \sin \alpha - \frac { \nu _ { g } } { K \lambda _ { g } } \right) - \nu _ { w } \cdot c _ { w } \left( \rho _ { w } g \sin \alpha - \frac { \nu _ { w } } { K \lambda _ { w } } \right) \right) d x
$$

上式积分项内所有参数都是真实世界中数量有限的物理量，所以有积分后有：

$$
R H S = \nu _ { t } ^ { a } - \nu _ { t } ^ { b } + \left( x _ { a } - x _ { \Gamma } \right) \left[ \nu _ { g } ^ { a } c _ { g } ^ { a } \left( \rho _ { g } ^ { a } g \sin \alpha - \frac { \nu _ { g } ^ { a } } { K ^ { a } \lambda _ { g } ^ { a } } \right) + \nu _ { w } ^ { a } c _ { w } ^ { a } \left( \rho _ { w } ^ { a } g \sin \alpha - \frac { \nu _ { w } ^ { a } } { K ^ { a } \lambda _ { w } ^ { a } } \right) \right] ,
$$

$$
+ \big ( x _ { \Gamma } - x _ { b } \big ) \Bigg [ \nu _ { g } ^ { b } c _ { g } ^ { b } \Bigg ( \rho _ { g } ^ { b } g \sin \alpha - \frac { \nu _ { g } ^ { b } } { K ^ { b } \lambda _ { g } ^ { b } } \Bigg ) + \nu _ { w } ^ { b } c _ { w } ^ { b } \Bigg ( \rho _ { w } ^ { b } g \sin \alpha - \frac { \nu _ { w } ^ { b } } { K ^ { b } \lambda _ { w } ^ { b } } \Bigg ) \Bigg ]
$$

由（14）和（18）得到如下方程：

$$
\begin{array} { r l } & { \Big ( x _ { \Gamma } - x _ { a } \Big ) \phi ^ { n } \Bigg ( S _ { \nu } ^ { n } \Big ( c _ { \phi } ^ { n } + c _ { \nu } ^ { n } \Big ) \frac { \hat { \Omega } P _ { \kappa } ^ { n } } { \hat { \Omega } t } + S _ { \nu } ^ { n } \Big ( c _ { \phi } ^ { n } + c _ { \nu } ^ { n } \Big ) \frac { \hat { \Omega } P _ { \kappa } ^ { n } } { \hat { \Omega } t } \Bigg ) } \\ & { \qquad + \Big ( x _ { b } - x _ { \Gamma } \Big ) \phi ^ { n } \Bigg ( S _ { \nu } ^ { n } \Big ( c _ { \phi } ^ { n } + c _ { \nu } ^ { n } \Big ) \frac { \hat { \Omega } P _ { \nu } ^ { n } } { \hat { \Omega } t } + S _ { \nu } ^ { n } \Big ( c _ { \phi } ^ { n } + c _ { \nu } ^ { n } \Big ) \frac { \hat { \Omega } P _ { \xi } ^ { n } } { \hat { \Omega } t } \Bigg ) } \\ & { = \nu _ { \eta } ^ { n } - \nu _ { \nu } ^ { b } + \Big ( x _ { a } - x _ { \Gamma } \Big ) \Bigg [ \nu _ { \delta } ^ { n } c _ { \delta } ^ { n } \Bigg ( \rho _ { \varepsilon } ^ { n } g \sin \alpha - \frac { V _ { \nu } ^ { n } } { K ^ { n } \hat { \mathcal { A } } _ { \kappa } } \Bigg ) + \nu _ { n } ^ { n } c _ { \kappa } ^ { n } \Bigg ( \rho _ { n } ^ { n } g \sin \alpha - \frac { V _ { \nu } ^ { n } } { K ^ { n } \hat { \mathcal { A } } _ { \kappa } ^ { n } } \Bigg ) \Bigg ] } \\ & { \qquad + \Big ( x _ { \Gamma } - x _ { \nu } \Big ) \Bigg [ \nu _ { \delta } ^ { n } c _ { \delta } ^ { n } \Bigg ( \rho _ { \varepsilon } ^ { n } g \sin \alpha - \frac { \nu _ { \delta } ^ { n } } { K ^ { n } \hat { \mathcal { A } } _ { \kappa } } \Bigg ) + \nu _ { n } ^ { n } c _ { \nu } ^ { n } \Bigg ( \rho _ { \nu } ^ { n } g \sin \alpha - \frac { \nu _ { \nu } ^ { n } } { K ^ { n } \hat { \mathcal { A } } _ { \kappa } } \Bigg ) \Bigg ] } \end{array}
$$

又因为 $x _ { a }  x _ { \Gamma } , x _ { b }  x _ { \Gamma }$ ，所以有

$$
\nu _ { t } ^ { a } = \nu _ { t } ^ { b }
$$

上式说明，在固定的突变界面处，气和水的总的渗流速度的分布连续。

# 3.3储层物性突变界面处的压力的连接条件

由气、水两相的达西公式（11）得到：

$$
\nu _ { _ { t } } = \nu _ { o } + \nu _ { _ { g } } = - K \lambda _ { { t } } \left[ \frac { d p _ { _ { g } } } { d x } - f _ { { w } } \frac { d p _ { _ { c } } } { d x } - \Big ( f _ { _ { g } } \rho _ { _ { g } } g + f _ { { w } } \rho _ { _ { w } } g \Big ) \sin \alpha \right]
$$

定义总体压力（total pressure）

$$
\Phi = p _ { g } + \int _ { S _ { w } } ^ { 1 } f _ { w } \frac { d p _ { c } } { d x } d S _ { w }
$$

$$
\frac { d p _ { g } } { d x } = \frac { d \Phi } { d x } - \frac { \hat { \sigma } \int _ { s _ { w } } ^ { 1 } f _ { w } \frac { d p _ { c } } { d x } d S _ { \nu } } { \hat { \sigma } \Phi } \frac { \hat { \sigma } \Phi } { \hat { \sigma } x } - \frac { \hat { \sigma } \int _ { s _ { w } } ^ { 1 } f _ { w } \frac { d p _ { c } } { d x } d S _ { \nu } } { \hat { \sigma } S _ { w } } \frac { \hat { \sigma } S _ { w } } { \hat { \sigma } x }
$$

定义 $\omega$ ，因为气体粘度随压力变化平缓，工程上可采用如下公式近似

$$
\omega = \frac { \partial \int _ { S _ { w } } ^ { 1 } f _ { w } \frac { d p _ { c } } { d x } d S _ { w } } { \partial \Phi } \approx \frac { \partial \int _ { S _ { w } } ^ { 1 } f _ { w } \frac { d p _ { c } } { d x } d S _ { w } } { \partial p _ { g } }
$$

将（24）代入（22）可以得到：

$$
\frac { d p _ { g } } { d x } = \frac { d \Phi } { d x } \big ( 1 - \omega \big ) + f _ { w } \frac { d p _ { c } } { d x }
$$

将其代入（21）总体流速表达式得到：

$$
\nu _ { _ { t } } = - K \lambda _ { _ { t } } { \left[ { \left( 1 - \omega \right) \frac { d \Phi } { d x } - \overline { { { \gamma } } } _ { \alpha } } \right] }
$$

整理得到：

$$
\frac { d \Phi } { d x } = \frac { \nu _ { t } } { - K \lambda _ { t } \left( 1 - \omega \right) } + \frac { \overline { { \gamma } } _ { \alpha } } { 1 - \omega }
$$

两端分别对 $\mathbf { x }$ 做积分有：

$$
\int _ { x _ { a } } ^ { x _ { b } } \frac { d \Phi } { d x } d x = \int _ { x _ { a } } ^ { x _ { b } } \frac { \nu _ { t } } { - K \lambda _ { t } \left( 1 - \omega \right) } d x + \int _ { x _ { a } } ^ { x _ { b } } \frac { \overline { { \gamma } } _ { \alpha } } { 1 - \omega } d x
$$

积分后可得：

$$
\Phi _ { b } - \Phi _ { a } = - \nu _ { t } \left[ \frac { x _ { \Gamma } - x _ { a } } { K ^ { a } \lambda _ { t } ^ { a } \left( 1 - \omega ^ { a } \right) } + \frac { x _ { b } - x _ { \Gamma } } { K ^ { b } \lambda _ { t } ^ { b } \left( 1 - \omega ^ { b } \right) } \right] + \frac { \left( x _ { \Gamma } - x _ { a } \right) \overline { { \gamma } } _ { \alpha } ^ { a } } { 1 - \omega ^ { a } } + \frac { \left( x _ { b } - x _ { \Gamma } \right) \overline { { \gamma } } _ { \alpha } ^ { b } } { 1 - \omega ^ { b } }
$$

因为 $x _ { a }  x _ { \Gamma }$ 以及 $x _ { b }  x _ { \Gamma }$ 可以得到：

$$
\Phi _ { a } = \Phi _ { b }
$$

上式说明在突变界面处有总体压力连续。

# 3.4物性突变界面处的流体压力和渗流速度的连接条件

根据（20）（30）可得到多孔介质在固定的突变界面处流体压力和渗流速度的连接条件：

$$
\left\{ \begin{array} { l } { \displaystyle f _ { w } ^ { b } \left( \nu _ { * } ^ { a } - G P C ^ { a } \right) = f _ { w } ^ { a } \left( \nu _ { * } ^ { b } - G P C ^ { b } \right) } \\ { \displaystyle f _ { g } ^ { b } \left( \nu _ { * } ^ { a } - G P C ^ { a } \right) = f _ { g } ^ { a } \left( \nu _ { * } ^ { b } + G P C ^ { b } \right) } \\ { \displaystyle p _ { g } ^ { a } + \int _ { S _ { w } ^ { a } } ^ { 1 } f _ { w } ^ { a } \left( \xi \right) \frac { d p _ { c } ^ { a } \left( \xi \right) } { d \xi } d \xi = p _ { g } ^ { b } + \int _ { S _ { x } ^ { b } } ^ { 1 } f _ { w } ^ { b } \left( \xi \right) \frac { d p _ { c } ^ { b } \left( \xi \right) } { d \xi } d \xi } \\ { \displaystyle p _ { w } ^ { a } - \int _ { S _ { w } ^ { * } } ^ { 1 } f _ { g } ^ { a } \left( \xi \right) \frac { d p _ { c } ^ { a } \left( \xi \right) } { d \xi } d \xi = p _ { w } ^ { b } - \int _ { S _ { w } ^ { b } } ^ { 1 } f _ { g } ^ { b } \left( \xi \right) \frac { d p _ { c } ^ { b } \left( \xi \right) } { d \xi } d \xi } \end{array} \right.
$$

$$
G P _ { c } ^ { a } = K ^ { a } \frac { \lambda _ { g } ^ { a } \lambda _ { w } ^ { a } } { \lambda _ { t } ^ { a } } \Bigg [ \Delta \rho _ { \mathrm { w } } ^ { a } g \sin \alpha + \frac { d p _ { c } ^ { a } } { d x } \Bigg ] , G P _ { c } ^ { b } = K ^ { b } \frac { \lambda _ { g } ^ { b } \lambda _ { w } ^ { b } } { \lambda _ { t } ^ { a } } \Bigg [ \Delta \rho _ { \mathrm { w } } ^ { b } g \sin \alpha + \frac { d p _ { c } ^ { b } } { d x } \Bigg ]
$$

根据（31）可知，在物性突变界面处流体压力和渗流速度可以不连续分布。

# 4跨突变界面的流量计算

根据（29）可得：

$$
\nu _ { t } = \frac { \Phi _ { a } - \Phi _ { b } + \frac { \left( x _ { \Gamma } - x _ { a } \right) \overline { { \gamma } } _ { \alpha } ^ { a } } { 1 - \omega ^ { a } } + \frac { \left( x _ { b } - x _ { \Gamma } \right) \overline { { \gamma } } _ { \alpha } ^ { b } } { 1 - \omega ^ { b } } } { \left[ \frac { x _ { \Gamma } - x _ { a } } { K ^ { a } \lambda _ { t } ^ { a } \left( 1 - \omega ^ { a } \right) } + \frac { x _ { b } - x _ { \Gamma } } { K ^ { b } \lambda _ { t } ^ { b } \left( 1 - \omega ^ { b } \right) } \right] }
$$

将（32）代入（21）可以分别计算出 $\nu _ { _ { w } } ^ { a } , \quad \nu _ { _ { g } } ^ { a }$

$$
\left\{ \begin{array} { l } { { \displaystyle { \nu } _ { w } ^ { a } = f _ { w } ^ { a } { \nu } _ { t } ^ { a } + \frac { d p _ { c } ^ { a } \left( S _ { w } ^ { a } \right) } { d S _ { w } ^ { a } } \frac { \hat { \sigma } S _ { w } ^ { a } } { \hat { \sigma } x } + \left( \rho _ { w } ^ { a } - \rho _ { g } ^ { a } \right) g \sin \alpha } } \\ { ~ } \\ { { \displaystyle { \nu } _ { g } ^ { a } = f _ { g } ^ { a } { \nu } _ { t } ^ { a } - \frac { d p _ { c } ^ { a } \left( S _ { w } ^ { a } \right) } { d S _ { w } ^ { a } } \frac { \hat { \sigma } S _ { w } ^ { a } } { \hat { \sigma } x } - \left( \rho _ { w } ^ { a } - \rho _ { g } ^ { a } \right) g \sin \alpha } } \end{array} \right.
$$

以及 $\nu _ { { } _ { w } } ^ { b } , \quad \nu _ { g } ^ { b }$

$$
\left\{ \begin{array} { l } { { \displaystyle { \nu } _ { w } ^ { b } = f _ { w } ^ { b } { \nu } _ { t } ^ { b } + \frac { d p _ { c } ^ { b } \left( S _ { w } ^ { b } \right) } { d S _ { w } ^ { b } } \frac { \hat { \sigma } S _ { w } ^ { b } } { \hat { \sigma } x } + \left( \rho _ { w } ^ { b } - \rho _ { g } ^ { b } \right) g \sin \alpha } } \\ { ~ } \\ { { \displaystyle { \nu } _ { g } ^ { b } = f _ { g } ^ { b } { \nu } _ { t } ^ { b } - \frac { d p _ { c } ^ { b } \left( S _ { w } ^ { b } \right) } { d S _ { w } ^ { a } } \frac { \hat { \sigma } S _ { w } ^ { b } } { \hat { \sigma } x } - \left( \rho _ { w } ^ { b } - \rho _ { g } ^ { b } \right) g \sin \alpha } } \end{array} \right.
$$

跨物性的突变界面的流量应取上游值，即： $\textcircled{1}$ 当流体由 $x _ { a }$ 流向 $x _ { b }$ ，通过突变界面的流速为 $\nu _ { w } ^ { a }$ ， $\nu _ { g } ^ { a }$ ; $\textcircled{2}$ 当流体由 $x _ { b }$ 流向 $x _ { a }$ ，通过突变界面的流速为 $ { \boldsymbol \nu } _ {  { \boldsymbol w } } ^ { b }$ ， $\nu _ { g } ^ { b }$ 。

# 5讨论

（1）多孔介质物性突变界面是一种固定界面，界面处流体压力和渗流速度的连接条件可表述为：总体流速相等，总流速相等，但流体压力和渗流速度可以不连续。流体渗流速度不连续是因为渗流速度记录的是流量除以渗流横截面积，即使流体分子的真实速度在界面处连续，但渗流速度可以不同；微观上当流体在界面处连续分布，流体压力场在界面处应连续，但在突变界面所处，两相流体很容易在孔喉位置发生截断，从而形成压力场的不连续分布；

（2）对于突变界面处流体是否能够不连续分布，学术界还有争议，一些学者根据传统的界面条件认为流体不可能连续分布。我们认为，抛开争议，从等效计算的角度，流体即使在突变区连续分布，但分布范围很狭窄，渗流阻力占比极低，采用本文提出的能够反映跨间断界面渗流规律的界面连接条件，可避免采用高密网格采样条件下，得到满足计算结果;

（3）大多数情况下，分相流系数随压力变化较小，可忽略（ $\scriptstyle { \omega = 0 }$ ）；

（4）多孔介质物性突变产生的界面与驱替形成的移动界面与相比较，流体渗流速度和压力在界面的连接条件特征不同，即静止的突变界面的连接条件与移动的突变界面的连接条件不同，需要注意应用条件。例如，本文所建立的界面条件不适合描述跨尺度，跨类型介质的流量的计算；

（5）本文以气-水两相为例，没有考虑溶解性，如果考虑溶解性，因物质守恒方程的变化，突变界面条件也随之变化；本文只考虑了一维情况，对于多维界面条件更为复杂。

# References

Aziz, K.and Settari, A.:Petroleum Reservoir Simulation. Applied Science Publishers,New York. (1979)   
Blunt,M.J.and Rubin,B.: Implicit flux limiting schemes for petroleum reservoir simulation.Journal ofComputational   
Physics 102(1),194-210(1992)   
Brenner,K.,Cances,C.,&Hilhorst,D. (2O13).Finite volume approximation foranimmiscible two-phase flowin porous   
media with discontinuous capilary pressure.Computational Geosciences,17(3),573-597.（使用了传统的连接条件）   
3.S.N.Antoncev,On the solvability of boundary value problems for degenerate two-phase porous flow equations,   
Dinamika Splo"sno°1 Sredy Vyp. 10 (1972),28-53, (Russian). Antoncey,Chavent 4.G.Chavent,Anew formulationof diphasic incompresible flows in porous media,Applications ofMethods ofFunctional Analysis to Problems in Mechanics,Lecture Notes inMathematics 503,P. GermainandB.Nayroles,eds.,Springer-Verlag, Berlin,New York,1976,pp.258-270.（应用了 global pressure 的概念）   
G. Chavent andJ. Jaffre_,Mathematical Models and Finite Elements for Reservoir Simulation," North-Holland, Amsterdam,1978．（应用了 global pressure 的概念）   
Arbogast,T. (1992).The existence of weak solutions to single porosityand simple dual-porosity models of two-phase incompressible flow.Nonlinear Analysis: Theory,Methods & Applications,19(11),1009-1031.（引用了global) Chen, Z. (2ool). Degenerate two-phase incompresible flow: I. existence,uniquenessand regularity ofa weak solution. Journal of Differential Equations,171(2),203-232.（引用了 global 的概念）   
Crichlow, H.B.: Modern Reservoir Engineering: A Simulation Approach,Englewood Clifs (Prentice-Hal),New Jersey.( 1977)   
Dicks,M.E.:Higher Order Godunov Black-Oil Simulations for Compressible Flow in Porous Media.PhD Thesis, University of Reading (1993)   
Guinot V.:Godunov-type Schemes/An Introduction for Engineers,1st Edition. Imprinted by Elsevier.(2003)   
Heller J.P.:The Interpretation of Model Experiments For the DisplacementofFluids Through Porous Media.American Institute of Chemical Engineers Journal,Vol.9, pp.452-459(1963)   
Liu,X.-D.,Osher,S.,and Chan,T.: Weighted essentiallynon-osilatoryschemes.JouralofComputational Physics115, 200-212(1994)   
Malison,B.T.,Gerrtsen,M.G.,Jessen,K.,andOr,F.M.:igh-orderupwindschemes for two-phase,multicomponent flow. SPE Journal 10(3),297-311 (2005)   
Parterson L.,Hornof V.,and Neale G.,A Consolidated Porous MediumFor the Visualization of Unstable Displacements. Powder Technology. vol.33,pp265-268(1982)   
Paterson L.,Hornof V.,Neale, G.:Visualization of a Surfactant Flood of an Oil-Saturated Porous Medium.SPE   
Journal.24(3),325-327(1984),SPE11598-PA   
Rohan Panchadhara,Laurent White and Dimitar Trenev.:Toward Application of Higher Order Finite Volume Schemes to Porous Media Flow.SPE163612-MS(2013)   
Sadok Laminea, Michael G.Edwards.:Higher ordercell-ased multidimensional upwind schemes forflow in porous media on unstructured grids.Computer Methods in Applied Mechanics and Engineering.Volume 259,103-122(2013)   
Thiele,M.R.and Edwards,M.G.Physicallybased higher order godunovschemes for compositional simulation.Paper SPE 66403,presented at the SPE Reservoir Simulation Symposium, Houston,TX,11-14 February(2001)   
TODD,M.R.etal.:Methods for Increased Accuracy in Numerical Reservoir Simulators.SPE3616-PA.(1972).   
Yann Brenier,Jérome Jafre.: UpstreamDifferencingFor Multiphase Flow In Reservoir Simulation.SIAMJ.Numer.Anal., 28(3),685-696(1991)

附录1：

$$
\begin{array} { r l } & { v _ { x } = - K \lambda _ { x } \Bigg \{ \frac { \partial \beta \alpha _ { _ { _ { 2 } } } } { \partial x } - \rho _ { x } \varepsilon \} \Bigg | } \\ & { v _ { x } = - K \lambda _ { x } ^ { 2 } \left( \frac { \partial \beta \alpha _ { _ { _ { 2 } } } } { \partial x } - \rho _ { x } \varepsilon \right) \Bigg | } \\ & { v _ { x } = - K \lambda _ { x } ^ { 2 } \left( \frac { \partial \beta \alpha _ { _ { _ { 2 } } } } { \partial x } - \rho _ { x } \varepsilon \right) ^ { 2 } } \\ & { \quad - ( \lambda _ { x } ^ { 2 } - \lambda _ { x } ^ { 2 } ) \Bigg \{ \frac { \partial \beta \alpha _ { _ { _ { 2 } } } } { \partial x } - \rho _ { x } \varepsilon \} \Bigg | } \\ & { v _ { x } = - K \lambda _ { x } ^ { 2 } \left( \frac { \partial \beta \alpha _ { _ { _ { 2 } } } } { \partial x } - \rho _ { x } \varepsilon \right) \Bigg \{ - \lambda _ { x } \varepsilon _ { x } \varepsilon _ { x } \sin \alpha = - \lambda _ { x } ^ { 2 } \left( \lambda _ { x } ^ { 2 } - \rho _ { x } \varepsilon \right) \frac { \partial \beta \alpha _ { _ { _ { 2 } } } } { \partial x } \Bigg | = - K \lambda _ { x } ^ { 2 } \left( \frac { \partial \beta \alpha _ { _ { _ { 2 } } } } { \partial x } - \rho _ { x } \varepsilon _ { x } \sin \alpha \right) \Bigg | - K ^ { 2 } } \\ & { \quad + \lambda _ { x } ^ { 2 } \left( \frac { \partial \beta \alpha _ { _ { _ { 2 } } } } { \partial x } - \rho _ { x } \varepsilon \right) \sin \alpha = - \lambda _ { x } ^ { 2 } \frac { \partial \beta \alpha _ { _ { _ { 2 } } } } { \partial x } \Bigg \{ \frac { \partial \beta \alpha _ { _ { _ { 2 } } } } { \partial x } \left( \frac { \partial \beta \alpha _ { _ { _ { 2 } } } } { \partial x } - \rho _ { x } \varepsilon _ { x } \right) \frac { \partial \beta \alpha _ { _ { 2 } } } { \partial x } \Bigg | } \\ & { \quad - ( \lambda _ { x } ^ { 2 } - \lambda _ { x } ^ { 2 } ) \Bigg \{ \frac { \partial \beta \alpha _ { _ { 2 } } } { \partial x } - \rho _ { x } \varepsilon _ { x } \sin \alpha = - \lambda _ { x } ^ { 2 } \left( \lambda _ { x } ^ { 2 } - \rho _ { x } \varepsilon _ { x } \sin \alpha + \frac { \partial \beta \alpha _ { _ { 2 } } } { \partial x } \right) } \\ &  \quad - ( \lambda _ { x } ^ { 2 } - \lambda _ { x } ^ { 2 } ) \Bigg \} \\ &  \quad - ( \lambda _ { x } ^ { 2 } - \lambda _ { x } ^   \end{array}
$$

fv， =vg+GPc νw = fwv, +GP vg=fwv，-GPc