# 多孔介质中不互溶气液两相驱替前缘的界面条件彭小龙 朱苏阳 梁保升 王超文 邓鹏等

Peng, Xiaolong, Zhu,Su ‘yang, Liang Baosheng, Wang Chaowen, Deng,Peng (State Key laboratory of Oil and Gas Reservoir Geology and Exploration, Southwest Petroleum University, Chengdu)

摘要：气-液两相驱替在油气藏开发中广泛存在。传统的渗流理论认为压力和达西速度在非连续界面处是连续的，我们在以往的研究对其进行了证伪。本文在前期不可压缩流体的基础上，以气-水两相驱替为例，研究了多孔介质中移动的气-水突变界面处的压力和渗流速度的连接条件。研究结果表明，在气-水两相驱替界面处：（1）总体压连续，但流体压力可以不连续；（2）总体流速的分布可以不连续，但满足特定的函数关系；（3）流体各相渗流速度不连续。

Abstract: Gas-liquid two-phase displacement are widely observed in oil and gas reservoir. The traditional seepage theory holds that the phase pressures and Darcy velocities must be continuous at the jump interface, and we have falsified them in previous studies.In this paper,the jump interface condition of two-phase seepage is extended from incompressible fluids to compressible.Taking gas-water two-phase displacement as an example, the new connection conditions of phase pressures and Darcy velocities at the gas-water displacement front in porous media were built.The results show that at the flood front,the global pressure is continuous,but not the fluid pressure are.(2)The total Darcy velocitycan be discontinuous with a specific functional relationship;(3)The phase Darcy velocity of each phase of the fluid is discontinuous.

# 1.介绍

气-液两相驱替在油气藏开发中广泛存在，例如：边底水类型气藏、含水层型地下储气库库气库、CO2地下埋存、注气驱油、注气驱油、带气顶油藏开发、天然气排水成藏、动态法测试气-水两相渗透率等储多问题。气-液两相驱替的连接条件是建立渗流数学模型，跟踪界面移动，计算驱替作用下产量。根据渗流文献，在驱替前缘界面处流体各相压力和渗流速度连续。即：

$$
\begin{array} { l } { { \nu _ { w } ^ { - } = \nu _ { w } ^ { + } , \nu _ { g } ^ { - } = \nu _ { g } ^ { + } } } \\ { { \qquad \quad p _ { g } ^ { - } = p _ { g } ^ { + } , p _ { w } ^ { - } = p _ { w } ^ { + } } } \\ { { \qquad p _ { c } ^ { - } = p _ { c } ^ { + } } } \end{array}
$$

根据质量守恒方程，单位时间内微元内流体变化流入微元的流量流出微元的流量。对于移动界面，体积为0，没有源汇项，则有，流入微元的流量流出微元的流量=0。Hassanizadeh,S.M.,&Gray，W.G.(1989)用物质守恒方程对其进行了证明。针对界面两侧区域毛管力不同的情况，作者在文献中对传统的界面条件进行质疑，然后根据物质守恒方程和两相渗流公式推导了新的界面条件以及跨突变界面的渗流公式[1,2]。气-液两相驱替界面具有三个特征：（1）驱替界面随时间不断移动；（2）驱替界面一般是突变界面，流体分布可能不连续；（3）气体压缩性高，驱替过程需要考虑压缩性。所以本文将在前期不可压缩流体两相突变界面条件的研究基础上，考虑流体的压缩性，研究多孔介质中不互溶气-液两相驱替前缘的界面条件。

# 2质疑对传统突变界面条件主要论点

（1）驱替前缘界面的界面条件需要建立的侧面两侧不同流体质点的压力连续条件和流体速度的连接条件（如图)；体积为0的界面微元流入量流出量所指对象是在界面上同一质点说明两者描述的不是同一物理过程;

![](images/6bcdab76056e92c6a95171d3189c34cf8f5d8302647350dfed23a927d8632b36.jpg)  
图1界面条件与界面上质点守恒方程所指对象

（2）以一维为例，假如包括界面的薄层状微元厚度为 ${ \mathfrak { b } } \to 0$ ，流入微元的流速记为 $\nu _ { \ell } ^ { - }$ ，流出微元的流速记为 $\boldsymbol { \nu } _ { \ell } ^ { + } \left( \ell = o , w \right)$ ，两者的数量关系即为连接条件，应满足根据质量守恒方程(2)，根据该方程并不能得出 $\nu _ { o } ^ { - } = \nu _ { o } ^ { + }$ ；而传统的渗流力学针对界面条件所用的质量守恒方程表达为(3），方程(2)与（3)的区别实质上已经替换了质量守恒方程。Hassanizadeh,S.M.,&Gray试图证明由（2）可以得到（3），但我们发现证明过程有误。

$$
\left\{ \begin{array} { l l } { \displaystyle { \frac { \hat { O } } { \partial t } } { \big ( } \phi S _ { \ell } { \big ) } + { \frac { \hat { O } } { \partial x } } { \big ( } \nu _ { \ell } { \big ) } = 0 } & { { \big ( } \ell = o , w { \big ) } } \\ { \displaystyle \nu _ { \ell } = - K \lambda _ { \ell } { \frac { d p _ { \ell } } { d x } } } & { \left( \ell = o , w \right) } \end{array} \right.
$$

$$
\left\{ \begin{array} { l l } { \nu _ { \ell } ^ { - } = \nu _ { \ell } ^ { + } } \\ { p _ { \ell } ^ { - } = p _ { \ell } ^ { + } } \end{array} \right. \qquad ( \ell = o , w )
$$

![](images/f9bb4801edfa9aa26ce14177a11dbed0a5283788021018ba1ffa590c02324293.jpg)  
图2包括驱替界面的江薄层状微元示意图

（3）Buckley-Leveret 模型的解析的解明确地显示渗流速度在前缘突变，与公式(2)明显区别；DeNeef,M.J.,&Molenaar,J.(1997)公式（1）显示流体各相压力和毛管力不能同时满足，为此提出改进的界面条件，他们认为润相流体压力连续，但非润湿相压力可以不连续。

（4）对于移动界面而言，公式(1)所示的传统的界面条件与Rankine-Hugoniot 条件矛盾；Rankine-Hugoniot条件可由质量守恒方程严格推导。以公式(2)为例，其Rankine-Hugoniot条件为：

$$
u _ { s } = \frac { \nu _ { w } ^ { - } - \nu _ { w } ^ { + } } { \phi \big ( S _ { w } ^ { - } - S _ { w } ^ { + } \big ) } = \frac { \nu _ { o } ^ { - } - \nu _ { o } ^ { + } } { \phi \big ( S _ { o } ^ { - } - S _ { o } ^ { + } \big ) }
$$

（5）因为按照公式(1)所示的传统的界面条件，以及两相流达西公式，突变界面处传导率应该为界面两侧的调和平均值，它不能正确反映真实的渗流过程，所以被单点上游权（SPU）和其它高阶上游权方法取代。调研文件我们发现虽然(1)表示的界面条件广泛见诸文献，但并没有得到真正应用。

$$
\nu _ { \ell } ^ { \Gamma } = \frac { 2 T _ { \ell } ^ { - } T _ { \ell } ^ { + } } { T _ { \ell } ^ { - } + T _ { \ell } ^ { + } } \left( p _ { \ell } ^ { - } - p _ { \ell } ^ { + } \right) , T _ { \ell } ^ { - } = \frac { K ^ { - } k _ { r \ell } ^ { - } } { \mu _ { \ell } ^ { - } } \frac { 1 } { \Delta x ^ { - } } , T _ { \ell } ^ { + } = \frac { K ^ { + } k _ { r \ell } ^ { + } } { \mu _ { \ell } ^ { + } } \frac { 1 } { \Delta x ^ { + } } \quad \left( \ell = w , g \right) \ : .
$$

（6）一些学者能通过否定流体饱和度不可能呈间断分布，从而解释突主界面处压力和流速必须连续。我们的观点认为：首先从微观而言，流体分布界面可以不连续，宏观是微观的统计，所以在宏观上流体的饱和度能呈突变分布；其次，从工业计算角度，突变界面区域对于整体的渗流阻力很小，压力降主要发生于突变界面两侧，即使流体分布以连续分布的方式突变，通过转换为不连续分布，可得到相近的结果，而且可大幅度减小计算量。

![](images/af9381ee58b58f74cace7efd2235cd93d2e92ed0b99bb2e2ab527c1a5e5fff25.jpg)  
图3将流体处突变但连续分布界面简化为不连续界面示意图（左：真实界面附近流体分布；右：简化后的不连续界面）

# 3不互溶气-水两相渗流方程

以不互溶的气-水两相为例根据气藏渗流力学，有气-水两相渗流的质量守恒方程：

$$
\left\{ \begin{array} { l } { \displaystyle \phi \frac { \hat { \sigma } } { \hat { \sigma } t } \big ( \rho _ { g } S _ { g } \big ) + \nabla \cdot \big ( \rho _ { g } \nu _ { g } \big ) = 0 } \\ { \displaystyle } \\ { \phi \frac { \hat { \sigma } } { \hat { \sigma } t } \big ( \rho _ { w } S _ { w } \big ) + \nabla \cdot \big ( \rho _ { w } \nu _ { w } \big ) = 0 } \\ { \displaystyle } \\ { S _ { w } + S _ { g } = 1 } \\ { \displaystyle } \\ { p _ { c } = p _ { g } - p _ { w } } \end{array} \right.
$$

引入地层体积系统 $B _ { g } = { \frac { V _ { g } } { V _ { g s c } } }$ 以 及 $B _ { _ w } = \frac { V _ { _ w } } { V _ { _ { w s c } } }$ 上述方程组可转换为：

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { \hat { \sigma } } { \hat { \sigma } t } \Bigg ( \frac { \phi S _ { g } } { B _ { g } } \Bigg ) + \nabla \cdot \Bigg ( \frac { \nu _ { g } } { B _ { g } } \Bigg ) = 0 } \\ { \displaystyle \frac { \hat { \sigma } } { \hat { \sigma } t } \Bigg ( \frac { \phi S _ { w } } { B _ { w } } \Bigg ) + \nabla \cdot \Bigg ( \frac { \nu _ { w } } { B _ { w } } \Bigg ) = 0 } \\ { \displaystyle S _ { w } + S _ { g } = 1 } \\ { \displaystyle p _ { c } = p _ { s } - p _ { w } } \end{array} \right.
$$

$B _ { g }$ 表示地层体积系数，无因次； $Z$ 表示气体偏差因子，无因次； $S _ { w }$ 表示含水饱和度； $\nu$ 表示达西流速m/day。 $\theta$ 表示 $\mathbf { x }$ 的水平夹角。流体在气藏中附合达西定律，所以有：

$$
\nu _ { \ell } = - \frac { K k _ { r \ell } } { \mu _ { \ell } } \big ( \nabla p _ { \ell } - \rho _ { \ell } g \sin \theta \big ) \quad \big ( \ell = w , g \big )
$$

# 4气-水两相驱替前缘的界面条件

# 4.1驱替前缘处总体流速的连接条件

以一维坐标为例，方程（7）改写为

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { \hat { \sigma } } { \hat { \sigma } t } \Bigg ( \frac { \phi S _ { g } } { B _ { g } } \Bigg ) + \frac { \hat { \sigma } } { \hat { \sigma } x } \Bigg ( \frac { \nu _ { g } } { B _ { g } } \Bigg ) = 0 \qquad } & { ( a ) } \\ { \displaystyle \frac { \hat { \sigma } } { \hat { \sigma } t } \Bigg ( \frac { \phi S _ { w } } { B _ { w } } \Bigg ) + \frac { \hat { \sigma } } { \hat { \sigma } x } \Bigg ( \frac { \nu _ { w } } { B _ { w } } \Bigg ) = 0 \qquad } & { ( b ) } \end{array} \right.
$$

考查驱替前缘附近 $\left[ x _ { a } , x _ { b } \right]$ 区域，用 $r _ { \Gamma }$ 表示气-水的驱动前缘界面，随时间移动， $x _ { a }  x _ { \Gamma } ^ { - } , x _ { b }  x _ { \Gamma } ^ { + }$ ；取 $\varepsilon _ { a } , \varepsilon _ { b } , \varepsilon _ { a } > 0 , \varepsilon _ { b } > 0$ 且 $\varepsilon _ { a } < < r _ { \Gamma } - r _ { \Gamma } ^ { - } , \varepsilon _ { b } < < r _ { \Gamma } ^ { + } - r _ { \Gamma }$ 其中 $r _ { \mathrm { r } } ^ { - } = r _ { \mathrm { r } } - \varepsilon _ { a } , r _ { \mathrm { r } } ^ { + } = r + \varepsilon _ { b }$ ，即有：

$$
\left[ r _ { \Gamma } - \varepsilon _ { a } , r _ { \Gamma } + \varepsilon _ { b } \right] \subset \left[ r _ { a } , r _ { b } \right]
$$

驱替过程中，在极短的时间可认为 $\textcircled{1}$ 驱替前缘界面以形态保持不变的方式移动； $\textcircled{2}$ 当孔隙度连续分布，可认为在此区间孔隙度为常数。

对方程公式（9）－（a）两端在 $\big [ r _ { a } , r _ { b } \big ]$ 范围内积分有：

$$
\begin{array} { r l } & { \displaystyle \int _ { x _ { a } } ^ { x _ { b } } \frac { \hat { \mathcal { O } } } { \hat { \mathcal { O } } t } \Bigg [ \frac { \phi S _ { g } } { B _ { g } } \Bigg ] d r + \int _ { x _ { a } } ^ { x _ { b } } \frac { \hat { \mathcal { O } } } { \hat { \mathcal { O } } x } \Bigg [ \frac { \nu _ { g } } { B _ { g } } \Bigg ] d x = 0 ~ ( } \\ & { \displaystyle \frac { \hat { \mathcal { O } } } { \hat { \mathcal { O } } t } \int _ { x _ { a } } ^ { x _ { b } } \Bigg ( \phi \frac { S _ { g } } { B _ { g } } \Bigg ) d x + \frac { \hat { \mathcal { O } } } { \hat { \mathcal { O } } t } \int _ { x _ { r } } ^ { x _ { r } } \Bigg ( \phi \frac { S _ { g } } { B _ { g } } \Bigg ) d x + \frac { \hat { \mathcal { O } } } { \hat { \mathcal { O } } t } \int _ { x _ { r } } ^ { x _ { r } + } \Bigg ( \phi \frac { S _ { g } } { B _ { g } } \Bigg ) d x + \frac { \hat { \mathcal { O } } } { \hat { \mathcal { O } } t } \int _ { x _ { r } } ^ { x _ { b } } \Bigg ( \phi \frac { S _ { g } } { B _ { g } } \Bigg ) d x + \Bigg [ \frac { \nu _ { g } } { B _ { g } } \Bigg ] _ { x = x _ { a } } ^ { x = x _ { b } } = 0 } \end{array}
$$

$$
\left( \phi \frac { S _ { g } ^ { a } } { B _ { g } ^ { a } } \right) \frac { \hat { \sigma } } { \hat { \sigma } t } \left( x _ { \Gamma } ^ { - } - x _ { a } \right) + \left( \phi \frac { S _ { g } ^ { a } } { B _ { g } ^ { a } } \right) \frac { \hat { \sigma } \mathcal { E } _ { a } } { \hat { \sigma } t } + \left( \phi \frac { S _ { g } ^ { b } } { B _ { g } ^ { b } } \right) \frac { \hat { \sigma } \mathcal { E } _ { b } } { \hat { \sigma } t } + \left( \phi \frac { S _ { g } } { B _ { g } } \right) \frac { \hat { \sigma } } { \hat { \sigma } t } \left( x _ { b } - x _ { \Gamma } ^ { + } \right) + \left[ \frac { \nu _ { g } } { B _ { g } } \right] _ { x = x _ { a } } ^ { \nu = x _ { b } } = 0
$$

令 $\boldsymbol { \varepsilon } _ { a }$ 和 $\boldsymbol { \varepsilon } _ { b }$ 为常数于是有：

$$
\Bigg ( \frac { S _ { g } ^ { a } } { B _ { g } ^ { a } } \Bigg ) \Bigg [ \phi \frac { \partial x _ { \Gamma } ^ { - } } { \partial t } \Bigg ] - \Bigg ( \frac { S _ { g } ^ { b } } { B _ { g } ^ { a } } \Bigg ) \Bigg [ \phi \frac { \partial x _ { \Gamma } ^ { + } } { \partial t } \Bigg ] + \Bigg [ \frac { \nu _ { g } } { B _ { g } } \Bigg ] _ { x = x _ { a } } ^ { x = x _ { b } } = 0
$$

即： $\phi \frac { \partial x _ { \Gamma } } { \partial t } = \frac { \displaystyle \frac { \nu _ { g } ^ { a } } { B _ { g } ^ { a } } - \frac { \nu _ { g } ^ { b } } { B _ { g } ^ { a } } } { \displaystyle \frac { S _ { g } ^ { a } } { B _ { g } ^ { a } } - \frac { S _ { g } ^ { b } } { B _ { g } ^ { a } } }$

等式（15）正是一维气-水两相驱替前缘界面的Rankine-Hugoniot 条件，渗流方程的，同理由（9）-（b）可得：

$$
\begin{array} { r } { \phi \frac { \partial r _ { \mathrm { r } } } { \partial t } = \frac { \left( \frac { \nu _ { \mathrm { w } } ^ { a } } { B _ { \mathrm { w } } ^ { a } } - \frac { \nu _ { \mathrm { w } } ^ { b } } { B _ { \mathrm { w } } ^ { b } } \right) } { \left( \frac { S _ { \mathrm { w } } ^ { a } } { B _ { \mathrm { w } } ^ { a } } - \frac { S _ { \mathrm { w } } ^ { b } } { B _ { \mathrm { w } } ^ { b } } \right) } } \end{array}
$$

合并（15）和（16）可得在驱替前缘有如下等式：

$$
\frac { \frac { \nu _ { g } ^ { a } } { B _ { g } ^ { a } } - \frac { \nu _ { g } ^ { b } } { B _ { g } ^ { a } } } { \frac { S _ { g } ^ { a } } { B _ { g } ^ { a } } - \frac { S _ { g } ^ { b } } { B _ { g } ^ { a } } } = \frac { \nu _ { w } ^ { a } } { B _ { w } ^ { a } } - \frac { \nu _ { w } ^ { b } } { B _ { w } ^ { b } }
$$

如果采用径向坐标系统仍然可以得到等式（15）～（17)

![](images/4404a9f8da615676d432718080c1dcc1e37a25ed02b05aff03c28d622d283802.jpg)  
图4边底水径向驱替示意图

$$
\tilde { \nu } _ { _ { \ell } } = \frac { \nu _ { _ { \ell } } } { B _ { \ell } } = - \frac { K k _ { r \ell } } { B _ { \ell } \mu _ { \ell } } \big ( \nabla p _ { \ell } - \rho _ { \ell } g \sin \theta \big ) \quad \big ( \ell = w , g \big )
$$

定义： $\tilde { \lambda } _ { \ell } = \frac { k _ { r \ell } } { \mu _ { \ell } B _ { \ell } } , \tilde { \nu } _ { t } = \tilde { \nu } _ { w } + \tilde { \nu } _ { g } , f _ { \ell } = \frac { \tilde { \nu } _ { \ell } } { \tilde { \nu } _ { t } } , \big ( \ell = w , g \big )$

可得： $\tilde { \nu } _ { t } = - K \tilde { \lambda } _ { t } \left[ \frac { d p _ { g } } { d x } - \tilde { f } _ { w } \frac { d p _ { c } } { d x } + \overline { { \gamma } } _ { \theta } \right]$

于是有： $\left\{ \begin{array} { l } { { \tilde { \nu } _ { _ w } = \tilde { f } _ { _ w } \tilde { \nu } _ { _ t } + G P _ { _ c } } } \\ { { \tilde { \nu } _ { _ g } = \tilde { f } _ { _ w } \tilde { \nu } _ { _ t } - G P _ { _ c } } } \end{array} \right.$

其中： $\overline { { \gamma } } _ { \theta } = \left( \tilde { f } _ { w } \rho _ { w } g + \tilde { f } _ { g } \rho _ { g } g \right) \sin \theta , \Delta \gamma _ { \theta } = \left( \rho _ { w } - \rho _ { g } \right) g \sin \theta , G P _ { c } = K \lambda _ { w } \tilde { f } _ { g } \left( \frac { d p _ { c } } { d x } + \Delta \gamma _ { \theta } \right) ,$ 将（21）入代（17）可得到：

$$
\nu _ { t } ^ { a } = \eta \nu _ { t } ^ { b } + \beta
$$

其中:

$$
\eta = \frac { \left( \frac { \tilde { f } _ { \kappa } ^ { \beta } } { S _ { _ \kappa } ^ { \beta } } - \frac { \tilde { f } _ { \kappa } ^ { \beta } } { S _ { _ \kappa } ^ { \beta } } - \frac { \tilde { f } _ { \kappa } ^ { \beta } } { \overline { { B _ { \kappa } ^ { \beta } } } S _ { _ \kappa } ^ { \alpha } - S _ { _ \kappa } ^ { \beta } } \right) } { \eta = \frac { \left( \frac { B _ { \kappa } ^ { \alpha } } { S _ { _ \kappa } ^ { \alpha } } - \frac { B _ { \kappa } ^ { \beta } } { S _ { _ \kappa } ^ { \beta } } - \frac { \tilde { B } _ { \kappa } ^ { \beta } } { B _ { \kappa } ^ { \beta } } S _ { _ \kappa } ^ { \alpha } - S _ { _ \kappa } ^ { \beta } \right) } { \left( \frac { \tilde { f } _ { \kappa } ^ { \alpha } } { S _ { _ \kappa } ^ { \alpha } - \frac { B _ { \kappa } ^ { \beta } } { B _ { \kappa } ^ { \beta } } S _ { _ \kappa } ^ { \beta } } - \frac { \tilde { C } _ { \kappa } ^ { \beta } } { S _ { _ \kappa } ^ { \beta } } S _ { _ \kappa } ^ { \alpha } - \frac { \tilde { B } _ { \kappa } ^ { \beta } } { S _ { _ \kappa } ^ { \beta } } S _ { _ \kappa } ^ { \alpha } \right) } } \beta = \frac { G P _ { c } ^ { \beta } } { B _ { _ \kappa } ^ { \alpha } - \frac { B _ { \kappa } ^ { \beta } } { B _ { \kappa } ^ { \beta } } S _ { _ \kappa } ^ { \beta } } + \frac { G P _ { c } ^ { \beta } } { S _ { _ \kappa } ^ { \alpha } - \frac { B _ { \kappa } ^ { \alpha } } { B _ { \kappa } ^ { \beta } } S _ { _ \kappa } ^ { \beta } } - \frac { G P _ { c } ^ { \beta } } { B _ { _ \kappa } ^ { \beta } } S _ { _ \kappa } ^ { \alpha } - S _ { _ \kappa } ^ { \beta }  { \frac { B _ { \kappa } ^ { \alpha } } { B _ { \kappa } ^ { \beta } } S _ { _ \kappa } ^ { \beta } S _ { _ \kappa } ^ { \beta } }  .
$$

说明在驱替前缘两侧，总体渗流速度不相等。对比不可压缩流体可知在驱替前缘两侧有总体速度相等，说明不可压缩流体和可压缩流体具有不同的界面连续条件，前者也可以看作是后者的特例。

# 4.2驱替前缘界面处总体压力的连接条件

定义总体压力： $\Phi = p _ { g } + \int _ { S _ { w } } ^ { 1 } \tilde { f } _ { w } \frac { d p _ { c } } { d \xi } d \xi$ ，总体压力对 $\mathbf { x }$ 求导数有：

$$
\frac { d \Phi } { d x } = \frac { d \Phi } { p _ { g } } \frac { d p _ { g } } { d x } + \frac { d \Phi } { d S _ { w } } \frac { d S _ { w } } { d x } = \frac { d p _ { g } } { d x } + \left( \frac { d } { d \Phi _ { g } } \int _ { S _ { w } } ^ { 1 } \tilde { f } _ { w } \frac { d p _ { c } } { d \xi } d \xi \right) \frac { d \Phi _ { g } } { d x } - \tilde { f } _ { w } \frac { d p _ { c } } { d x }
$$

定义 $\omega = \left( \frac { d } { d \Phi _ { g } } \int _ { S _ { w } } ^ { 1 } \tilde { f } _ { w } \frac { d p _ { c } } { d \xi } d \xi \right)$ 且根据 ded～p曲线变化非常平缓，所以可近似采用：

$$
\omega \approx \frac { d } { d p _ { g } } \int _ { S _ { w } } ^ { 1 } \tilde { f } _ { w } \frac { d p _ { c } } { d \xi } d \xi
$$

由（21）可得： $\frac { d \Phi } { d x } \big ( 1 - \omega \big ) = \frac { d p _ { g } } { d x } - \widetilde { f } _ { w } \frac { d p _ { c } } { d x }$

将（26）代入（20）有：

$$
\widetilde { \nu } _ { t } = - K \widetilde { \lambda } _ { t } \Bigg [ \big ( 1 - \omega \big ) \frac { d \Phi } { d x } + \overline { { \gamma } } _ { \theta } \Bigg ]
$$

由（27）整理得到如下方程：

$$
- \frac { d \Phi } { d x } = \frac { \widetilde { \nu } _ { t } } { \left( 1 - \omega \right) K \widetilde { \lambda } _ { t } } + \frac { \overline { { \gamma } } _ { \theta } } { \left( 1 - \omega \right) }
$$

对（28）在 $\big [ x _ { a } , x _ { b } \big ]$ 范围内求积分：

$$
\begin{array} { l } { \displaystyle - \int _ { x _ { a } } ^ { x _ { b } } \frac { d \Phi } { d x } = \int _ { x _ { a } } ^ { x _ { b } } \Biggl [ \frac { \tilde { \nu } _ { t } } { \left( 1 - \omega \right) K \tilde { \lambda } _ { t } } + \frac { \overline { { \gamma _ { \theta } } } } { \left( 1 - \omega \right) } \Biggr ] d x } \\ { \displaystyle \Phi _ { a } - \Phi _ { b } = \int _ { x _ { a } } ^ { x _ { \mathrm { r } } } \Biggl [ \frac { \tilde { \nu } _ { t } } { \left( 1 - \omega \right) K \tilde { \lambda } _ { t } } + \frac { \overline { { \gamma _ { \theta } } } } { \left( 1 - \omega \right) } \Biggr ] d x + \int _ { x _ { \mathrm { r } } } ^ { x _ { b } } \Biggl [ \frac { \tilde { \nu } _ { t } } { \left( 1 - \omega \right) K \tilde { \lambda } _ { t } } + \frac { \overline { { \gamma _ { \theta } } } } { \left( 1 - \omega \right) } \Biggr ] d x } \\ { \displaystyle \Phi _ { a } - \Phi _ { b } = \frac { \tilde { \nu } _ { t } ^ { a } \left( x _ { \mathrm { r } } - x _ { a } \right) } { \left( 1 - \omega ^ { a } \right) K ^ { a } \tilde { \lambda } ^ { a } } + \frac { \overline { { \gamma _ { \theta } ^ { a } \left( x _ { \mathrm { r } } - x _ { a } \right) } } } { \left( 1 - \omega ^ { a } \right) } + \frac { \tilde { \nu } _ { t } ^ { b } \left( x _ { b } - x _ { \mathrm { r } } \right) } { \left( 1 - \omega \right) K ^ { b } \tilde { \lambda } _ { t } ^ { b } } + \frac { \overline { { \gamma _ { \theta } ^ { b } \left( x _ { b } - x _ { \mathrm { r } } \right) } } } { \left( 1 - \omega ^ { b } \right) } } \end{array}
$$

由（30）或（31)，当 $x _ { a }  x _ { \Gamma } , x _ { b }  x _ { \Gamma }$ 有：

$$
\Phi _ { a } = \Phi _ { b }
$$

说明在驱替前缘界面处，有总体压力连续。

# 4.3驱替前缘界面的压力的连接条件

将（30)，（32）整合得到新的界面条件：

$$
\left\{ \begin{array} { l l } { \boldsymbol { \nu } _ { t } ^ { a } = \eta \boldsymbol { \nu } _ { t } ^ { b } + \boldsymbol { \beta } } \\ { \Phi _ { a } = \Phi _ { b } } \end{array} \right.
$$

根据（33）揭示的总体渗流速度和总压力在驱替前缘界面的连接关系，结合达西公式（21）可以计算出气和水的渗流速度在界面处的连接条件；根据 $p _ { c } = p _ { g } - p _ { w }$ 以及总体压力定义，可计算气和水压力的在界面处的连接条件：

$$
\begin{array} { l } { { \displaystyle \left( \left( \nu _ { w } ^ { a } - G P _ { c } ^ { a } \right) f _ { w } ^ { b } = f _ { w } ^ { b } \eta \left( \nu _ { w } ^ { b } - G P _ { c } ^ { b } \right) + f _ { w } ^ { b } f _ { w } ^ { a } \beta \right. } } \\ { { \displaystyle \left( \nu _ { g } ^ { a } + G P _ { c } ^ { a } \right) f _ { g } ^ { b } = f _ { g } ^ { b } \eta \left( \nu _ { g } ^ { b } + G P _ { c } ^ { b } \right) + f _ { g } ^ { b } f _ { g } ^ { a } \beta } } \\ { { \displaystyle \left. \int _ { g } ^ { a } + \int _ { s _ { w } } ^ { 1 } \tilde { f } _ { w } ^ { a } \frac { d p _ { c } ^ { a } \left( \xi \right) } { d \xi } d \xi = p _ { g } ^ { b } + \int _ { s _ { w } } ^ { 1 } \tilde { f } _ { w } ^ { b } \frac { d p _ { c } ^ { b } \left( \xi \right) } { d \xi } d \xi \right. } } \\ { { \displaystyle \left. p _ { w } ^ { a } + p _ { c } ^ { a } + \int _ { s _ { w } } ^ { 1 } \tilde { f } _ { w } ^ { a } \frac { d p _ { c } ^ { a } \left( \xi \right) } { d \xi } d \xi = p _ { w } ^ { b } + p _ { c } ^ { a } + \int _ { s _ { w } } ^ { 1 } \tilde { f } _ { w } ^ { b } \frac { d p _ { c } ^ { b } \left( \xi \right) } { d \xi } d \xi \right. } } \end{array}
$$

# 4.4驱替前缘两侧气-水两相流量计算

联立（22）和（31）可解出驱替前缘两侧的总的渗流速度 $\nu _ { t } ^ { a }$ ， $\nu _ { t } ^ { b }$ 。

$$
\nu _ { t } ^ { a } = \frac { \left( \Phi _ { a } - \Phi _ { b } \right) } { \frac { \left( x _ { \mathrm { r } } - x _ { a } \right) } { \left( 1 - \omega ^ { a } \right) K ^ { a } \tilde { \lambda } ^ { a } } + \frac { \left( x _ { b } - x _ { \mathrm { r } } \right) } { \eta \left( 1 - \omega ^ { b } \right) K ^ { b } \tilde { \lambda } _ { t } ^ { b } } } + \frac { \frac { x _ { b } - x _ { \mathrm { r } } } { 1 - \omega ^ { b } } \left( \frac { \beta } { \eta K ^ { b } \tilde { \lambda } _ { t } ^ { b } } + \bar { \gamma } _ { \theta } ^ { b } \right) - \frac { \bar { \gamma } _ { \theta } ^ { a } \left( x _ { \mathrm { r } } - x _ { a } \right) } { \left( 1 - \omega ^ { a } \right) } } { \left( x _ { \mathrm { r } } - x _ { a } \right) }  { \frac { \left( x _ { \mathrm { r } } - x _ { a } \right) } { \left( 1 - \omega ^ { a } \right) K ^ { a } \tilde { \lambda } ^ { a } } + \frac { \left( x _ { b } - x _ { \mathrm { r } } \right) } { \eta \left( 1 - \omega ^ { b } \right) K ^ { b } \tilde { \lambda } _ { t } ^ { b } } }
$$

$$
\nu _ { t } ^ { b } = \frac { \Phi _ { a } - \Phi _ { b } } { \frac { \eta \left( x _ { \Gamma } - x _ { a } \right) } { \left( 1 - \omega ^ { a } \right) K ^ { a } \tilde { \lambda } ^ { a } } + \frac { \left( x _ { b } - x _ { \Gamma } \right) } { \left( 1 - \omega ^ { b } \right) K ^ { b } \tilde { \lambda } _ { t } ^ { b } } } - \frac { \frac { \left( x _ { \Gamma } - x _ { a } \right) } { \left( 1 - \omega ^ { a } \right) } \left( \frac { \beta } { K ^ { a } \tilde { \lambda } ^ { a } } + \overline { { \gamma } } _ { \theta } ^ { a } \right) + \frac { \overline { { \gamma } } _ { \theta } ^ { b } \left( x _ { b } - x _ { \Gamma } \right) } { \left( 1 - \omega ^ { b } \right) } } { \frac { \eta \left( x _ { \Gamma } - x _ { a } \right) } { \left( 1 - \omega ^ { a } \right) K ^ { a } \tilde { \lambda } ^ { a } } + \frac { \left( x _ { b } - x _ { \Gamma } \right) } { \left( 1 - \omega ^ { b } \right) K ^ { b } \tilde { \lambda } _ { t } ^ { b } } }
$$

将（35）代入（21）可以分别计算出 $\nu _ { { } _ { w } } ^ { a }$ ， $\nu _ { g } ^ { a }$

$$
\begin{array} { r } { \left\{ \tilde { \nu } _ { w } ^ { a } = \tilde { f } _ { w } ^ { a } \tilde { \nu } _ { t } ^ { a } + \cfrac { d p _ { c } ^ { a } \left( S _ { w } ^ { a } \right) } { d S _ { w } ^ { a } } \cfrac { \hat { \sigma } S _ { w } ^ { a } } { \hat { \sigma } x } + \left( \rho _ { w } ^ { a } - \rho _ { g } ^ { a } \right) g \sin \theta \right. } \\ { \left. \left[ \tilde { \nu } _ { g } ^ { a } = \tilde { f } _ { w } ^ { a } \tilde { \nu } _ { t } ^ { a } - \cfrac { d p _ { c } ^ { a } \left( S _ { w } ^ { a } \right) } { d S _ { w } ^ { a } } \cfrac { \hat { \sigma } S _ { w } ^ { a } } { \hat { \sigma } x } + \left( \rho _ { w } ^ { a } - \rho _ { g } ^ { a } \right) g \sin \theta \right. \right. } \end{array}
$$

将（36）代入（22）可以得到 $\nu _ { { } _ { w } } ^ { b } , \quad \nu _ { g } ^ { b }$

$$
\begin{array} { r } { \left\{ \tilde { \nu } _ { w } ^ { \mathrm { b } } = \tilde { f } _ { w } ^ { b } \tilde { \nu } _ { t } ^ { b } + \frac { d p _ { c } ^ { a } \left( S _ { w } ^ { a } \right) } { d S _ { w } ^ { a } } \frac { \hat { \sigma } S _ { w } ^ { a } } { \hat { \sigma } x } + \left( \rho _ { w } ^ { a } - \rho _ { g } ^ { a } \right) g \sin \theta \right. } \\ { \left. \left[ \tilde { \nu } _ { g } ^ { b } = \tilde { f } _ { g } ^ { b } \tilde { \nu } _ { t } ^ { b } - \frac { d p _ { c } ^ { b } \left( S _ { w } ^ { b } \right) } { d S _ { w } ^ { b } } \frac { \hat { \sigma } S _ { w } ^ { b } } { \hat { \sigma } x } + \left( \rho _ { w } ^ { b } - \rho _ { g } ^ { b } \right) g \sin \theta \right. \right. } \end{array}
$$

# 5讨论

（1）本文研究结果显示在驱替前缘界面处，流体压力和渗流速度可以不连续；流体渗流速度不连续是因为渗流速度记录的是流量除以渗流横截面积，即使流体分子的真实速度在界面处连续，但渗流速度可以不同；当流体在界面处连续分布，流体压力场在界面处应连续，但在微观上，突变界面所处区域的，两相体很容易在孔喉位置发生截断；

（2）对于突变界面处流体是否能够不连续分布，学术界还有争议，一些学者根据传统的界面条件认为流体不可能连续分布。我们认为，抛开争议，从等效计算的角度，流体即使在突变区连续分布，但分布范围很狭窄，渗流阻力占比极低，采用本文提出的能够反映跨间断界面渗流规律的界面连接条件，可避免采用高密网格采样条件下，得到满足计算结果。

（3）大多数情况下，分相流系数随压力变化较小，可忽略（ $\scriptstyle { \omega = 0 } )$ )，

（4）驱替形成的移动界面与多孔介质物性突变产生的界面相比较，流体渗流速度和压力在界面的连接条件特征不同，即移动的突变界面的连接条件与静止的突变界面的连接条件不同，需要注意应用条件，例如，本文所建立的界面条件不适合描述跨尺度，跨类型介质的流量的计算;

（5）本文以气-水两相为例，没有考虑溶解性，如果考虑溶解性，因物质守恒方程的变化，突变界面条件也随之变化；本文只考虑了一维情况，对于多维界面条件更为复杂；

# 参考文献

[1] Xialong Peng YL,Baosheng Liang, Zhimin Du. Interface ConditionForThe Darcy VelocityAtThe Water-OilFlood Front In The Porous Medium [J]. Plos One, 2017, 12(5): E0177187.

[2]Peng X,MoF,LiangB,EtAl.Critical InvestigationOfInterface ConditionsForFluidPressures,CapilaryPressure, And Velocities At Jump Interface In Porous Media [J]. Journal Of Porous Media,2019, 22(6): [3]Bear, J. (1972). Dynamics of fluids in porous media. Courier Corporation. [4]Brenner, K.,Cances,C.,& Hilhorst,D.(2013).Finite volume approximation for an immiscible two-phase flow in porous media with discontinuous capillary pressure. Computational Geosciences,17(3), 573-597. [5]De Neef, M. J.,& Molenar, J. (1997). Analysis of DNAPL infiltration in a medium with a low-permeable lens. Computational Geosciences,1(2), 191-214. [6]Hassanizadeh,S.M.,& Gray, W. G. (1989). Boundary and interface conditions in porous media. Water Resources Research,25(7), 1705-1715. [7]Huber,R.,& Helmig,R.(200). Node-centered finite volume discretizations for the numerical simulation of multiphase flow in heterogeneous porous media. Computational Geosciences, 4(2),141-164. [8]Liu,P.L.F,Cheng,A.H.D,Ligget,J.A.,&Lee,J.H. (981).Boundary integral equationsolutions tomoving interface between two fluids in porous media. Water Resources Research,17(5),1445-1452. [9]Mozolevski,1.，& Schuh,L.(2013). Numerical simulationof two-phase immiscible incompresible flows in heterogeneous porous media with capillry barriers. Journal of Computational and Applied Mathematics,242,12-27. [10]Ohlberger, M., & Schweizer, B. (2007). Modeling of interfaces in unsaturated porous media. [11]Szymkiewicz,A. (2012). Modeling water flow in unsaturated porous media: accounting for nonlinear permeability and material heterogeneity. Springer Science & Business Media.Page 41, [12]Valdes-Parada,F.J.,&Espinosa-Paredes,G. (2Oo5).Darcy'sLaw for Immiscible Two-Phase Flow: A Theoretical Development. Journal of Porous Media, 8(6).