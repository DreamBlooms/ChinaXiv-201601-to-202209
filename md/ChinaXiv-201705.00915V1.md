# 非定常流动的隐式间断 Galerkin方法研究

周莉刘玺王占学(西北工业大学动力与能源学院，西安 710072)

摘要为了增加间断 Galerkin(Discontinuous Galerkin,DG）方法在非定常流动中的求解效率，本文开展了非定常流动的隐式DG方法研究。隐式DG方法的构造采用二阶向后差分格式（BDF2）进行时间项离散，非线性代数系统的求解基于 Newton 迭代法，采用块对称 Gauss-Seidel(SGS）迭代法对线性方程组进行了求解。基于所发展的非定常流动的隐式DG 方法，分别对等熵圆柱扰流和卡门涡街（ $R e { = } 1 0 0$ )现象进行了数值模拟。研究结果表明，所发展的隐式DG方法能够达到设计精度，能够在高出显式方法两个数量级的时间步长上保持稳定，具有高的求解效率，且计算结果与显式方法和相关文献均吻合较好。

关键词间断Galerkin方法；隐式方法；非定常流动；求解效率中图分类号：V211.3 文献标识码：A 文章编号：:0253-231X(2017)04-0733-07

# Investigation on Implicit Discontinuous Galerkin Method in Unsteady Flow

ZHOU Li LIU XiWANG Zhan-Xue (School of Power and Energy, Northwest Polytechhic University，Xi'an 710072, China)

AbstractAn implicit discontinuous Galerkmethod (DG) was investigated in order to increase the solving efficiency of unsteady fow.ASecond-order backward diference formulation (BDF2) was applied for the time-discretization. The Newton-Raphson method and block symmetric Gaus-Seidel (SGS) iteration were consideredtoSlve non-linear equations and linear equations respectively. The isentropic flow around the cylnder and the Karmann vortex street phenomenon were simulated to verify the validity of theimplicit DG method developed in the paper. The results show that the calculation accuracy ofthe implicit DG method can match designed accuracy. The solution using the implicit DG method keeps stable even the time step adopted is more than 100 times of that it has in the explicit method, with the favorable solving efficiency achieved,and the corresponding results are in good agreement with the explicit method and related references.

Key wordsdiscontinuous Galerkin method (DG)； implicit method; unsteady flow； solving efficiency

# 0引言

高精度CFD方法是空间高于二阶精度的方程离散方法，相比于低阶方法，由于具有在较低的计算成本上得到更高计算精度的潜在特性而受到了关注[1]。目前发展了一系列的高精度CFD方法，例如高阶有限体积、DG方法、谱方法、谱差分/谱体积、通量重构等。其中DG方法具有高阶精度、易于构造、插值模板小、灵活处理间断问题和易于实现并行计算等特点，自从上世纪 80 年代末 Shu 等[2] 提出 DG方法求解守恒律问题的基本理论以来便得到了大量研究[3-5]。

DG方法结合了有限元方法(FEM)和有限体积方法(FVM)的特点。在单元采用与FEM相似的多项式逼近策略，通过增加基函数个数以提高计算精度；不同点在于其在每个单元上的多项式分布是完全独立的，且网格单元界面上允许间断产生。单元之间的信息传递采用了FVM中Riemann求解器计算界面通量的方法，保持了格式的迎风特性；且在超声速流场中限制器的构造完全继承于FVM。

近年来，国内外学者针对于DG方法的构造进行了大量的研究。张来平[]对于高精度DG/FV 混合算法进行了研究，其在DG框架下采用重构思想通过扩大插值模板在存储量基本不变的前提下到达更高阶精度。于剑、Jiang 等[7,8]基于四边形网格分别研究了层流流动DG方法的构造和非定常流动的隐式求解方法。郝海兵[9]基于Gauss-Seidel迭代研究了无黏流动的隐式DG 方法。Wang[10] 详细阐述了非定常无黏流动的隐式DG方法及 $p$ 型多重网格方法的构造。Persson[11]针对隐式 DG 方法中病态线性方程组的预处理方法和迭代方法进行了详细研究。Patrick[14]采用解析方法推导了无黏流动隐式DG 方法Jacobi矩阵的计算。谭勤学[12]对雷诺时均N-S方程(RANS)采用DG方法离散，通过数值模拟研究了燃气轮机空气系统中的流动和传热问题，研究表明DG方法的结果更接近于实验值。此外，DG方法在压气机等部件的内部流动研究中也得到了相应的应用[13,14]。

研究者们采用DG方法进行流场计算时广泛采用了显式Runge-Kutta方法对时间项进行离散，通过时间推进方法得到收敛的流场结果。虽然此方法简单且易于构造，但是由于数值稳定性严重限制了时间步长使得流场求解效率异常低下。例如，采用2阶精度的DG方法进行流场求解时保证绝大部分算例稳定的 $C F L { \approx } 0 . 1 5$ ，在更高阶精度下这一限制将会更加严苛[15]。因此提升流场求解效率是DG方法进行工程应用研究亟待解决的关键问题之一

在流动仿真中提升求解效率的主要方案有隐式计算方法、并行计算和多重网格筹其中隐式方法理论上不受时间步长的限制，具有无条件稳定特性，可显著提升流场求解效率。因此，本文开展非定常层流流动的隐式DG方法研究，基于所发展的隐式DG方法，分别对等熵圆柱扰流和卡门涡街( $R e = 1 0 0 ^ { \circ } ,$ 现象进行了数值模拟，以验证本文所发展的非定常层流流动的隐式DG方法的求解精度及稳定性。

# 1DG方法与FVM对比

# 1.1 间断 Galerkin 方法

ht t p:

非定常可压缩N-S方程为：

$$
\frac { \partial \pmb { u } } { \partial t } + \nabla \cdot \pmb { F } _ { \mathrm { i n v } } ( \pmb { u } ) = \nabla \cdot \pmb { F } _ { \mathrm { v i s } } ( \pmb { u } , \nabla \pmb { u } )
$$

其中， $\boldsymbol { u }$ 为守恒变量， $F _ { \mathrm { i n v } }$ 和 ${ \cal F } _ { \mathrm { v i s } }$ 分别为黏性通量项和无黏通量项。其中黏性通量项的本构关系满足Stokes假设，热流量满足Fourier定律。为了采用DG方法进行方程离散，引入辅助变量 $s$

$$
\mathbf { \nabla } _ { s } = \nabla \mathbf { u }
$$

首先，将求解区域进行单元剖分，在每个单元上将守恒变量 $\textbf { \em u }$ 和辅助变量 $s$ 采用多项式逼近：

$$
q = \sum _ { i = 1 } ^ { N p } q _ { i } ( t ) \varphi _ { i } ( { \pmb x } )
$$

其中 $\pmb { q } = [ \pmb { u } ; \pmb { s } ] ^ { \mathrm { T } }$ ， $\varphi _ { i }$ 和 $q _ { i }$ 分别表示第 $\mathbf { \chi } _ { i }$ 个基函数和其系数, $N _ { \mathrm { p } }$ 为每个单元上的自由度总数。基函数的选取可采用多种形式，例如Lagrange基函数和任何一种标准正交基函数。

其次，将式(3)代入式(1)，(2)中，基于加权余量法 (变分原理)使余量 $\scriptstyle { R _ { \mathrm { h } } }$ 正交于基函数空间，即基函数与余量方程在每个控制体上的积分为零：

$$
\left\{ \begin{array} { l l } { \displaystyle \mathrm { i } : R _ { \mathrm { h } } = \frac { \partial { \boldsymbol { u } } _ { \mathrm { h } } } { \partial t } + \nabla \cdot \mathbf { { F } } _ { \mathrm { i n v } } ( { \boldsymbol { \boldsymbol { u } } } _ { \mathrm { h } } ) - \nabla \cdot \mathbf { { F } } _ { \mathrm { v i s } } ( \boldsymbol { \boldsymbol { u } } _ { \mathrm { h } } , \nabla { \boldsymbol { u } } _ { \mathrm { h } } ) } & \\ { \displaystyle \mathrm { i i } : \int _ { D ^ { k } } \varphi _ { i } \cdot R _ { \mathrm { h } } \mathrm { d } V = 0 \quad 1 \leqslant i \leqslant N p } \end{array} \right.
$$

将其展开便得到了DG方法的半离散方程：

$$
\begin{array} { r l }   { ( \int _ { D _ { k } \ll \mathcal { A } } \boldsymbol { \mathcal { S } } \boldsymbol { \mathcal { S } } \boldsymbol { \mathcal { S } } = \oint _ { \partial D _ { k } } \boldsymbol { u } ^ { * } \varphi \boldsymbol { n } \mathrm { d } s - \int _ { D _ { k } } \boldsymbol { u } \cdot \nabla \varphi \boldsymbol { \mathrm { i } } \mathrm { d } \mathcal { Q } \boldsymbol { \mathrm { i } } } \\ & { \lesssim \underset { \mathrm { i } \neq \mathcal { \bar { H } } } { \sum _ { \partial \bar { t } \backslash \bar { t } } } \iint _ { D _ { k } } ^ { \infty } \varphi _ { i } \boldsymbol { u } _ { h } \mathrm { d } \varOmega = \int _ { D _ { k } } ( F _ { \mathrm { i n v } } - F _ { \mathrm { v i s } } ) \cdot \nabla \varphi _ { i } \mathrm { d } \varOmega - } \\ & { \lesssim \Vert \int _ { \partial D _ { k } } \varphi _ { i } [ ( F _ { \mathrm { i n v } } - F _ { \mathrm { v i s } } ) \cdot \boldsymbol { n } ] ^ { * } \mathrm { d } s } \end{array}
$$

其中 $\boldsymbol { u } ^ { * }$ 和 $[ ( \pmb { F } _ { \mathrm { i n v } } - \pmb { F } _ { \mathrm { v i s } } ) \cdot \pmb { n } ] ^ { * }$ 为数值通量， $\scriptstyle { n }$ 为界面外法向向量。本文中无黏项通量和黏性项通量分别采用Lax-Friedrich格式和BR1格式。

最后，将式(5)时间项和空间项分离，简化得到最终离散形式为：

$$
M { \frac { \mathrm { d } u } { \mathrm { d } t } } = R ( u )
$$

# 1.20有限体积方法

FVM方法的解在单元上采用常数近似，根据数据存储点与网格节点位置关系通常有单元顶点法和单元中心法两种。控制体 $k$ 中解的分布为：

$$
{ \overline { { \mathbf { u } } } } ^ { k } = { \frac { 1 } { V ^ { k } } } \int _ { D ^ { k } } { \mathbf { u } } \mathrm { d } V
$$

式中 $\smash { V ^ { k } }$ 为控制体 $D ^ { k }$ 的体积 (面积)。

同样，首先将其带入余量方程(4)中的 $\mathbf { \chi } _ { i }$ 式，并在单元上积分：

$$
\int _ { D ^ { k } } \frac { \partial \overline { { \boldsymbol { \mathbf { u } } } } } { \partial t } + \nabla \cdot ( F _ { \mathrm { i n v } } ( \overline { { \boldsymbol { \mathbf { u } } } } ) - F _ { \mathrm { v i s } } ( \overline { { \boldsymbol { \mathbf { u } } } } , \nabla \overline { { \boldsymbol { \mathbf { u } } } } ) ) \mathrm { d } V = 0
$$

其次，利用Gauss定理将散度的体(面)积分变为界面上的面(线)积分：

$$
\frac { \mathrm { d } \overline { { \boldsymbol { u } } } _ { k } } { \mathrm { d } t } + \frac { 1 } { V ^ { k } } \cdot \int _ { \partial D ^ { k } } \left( \boldsymbol { F } _ { \mathrm { { i n v } } } ^ { * } ( \overline { { \boldsymbol { u } } } ) - \boldsymbol { F } _ { \mathrm { { v i s } } } ^ { * } ( \overline { { \boldsymbol { u } } } , \nabla \overline { { \boldsymbol { u } } } ) \right) \cdot \boldsymbol { n } \mathrm { d } s = 0
$$

式（9）则为FVM的最终离散格式。提高空间逼近精度的关键在于重构守恒变量在单元上的分布，格式的精度将由重构界面通量的精度决定。

相比于DG方法的离散过程，FVM在离散时相当于DG方法中守恒变量 $\varphi = 1$ 时的情形。因此，在离散方法上FVM可以认为是DG方法在基函数为1时的特例。

# 2非定常隐式DG 方法构造

显式DG方法在计算式(6）右端残量项时采用当前已知时间层上的守恒变量值 $\pmb { R } ( \pmb { u } ^ { n } )$ 。而隐式DG方法是指残量项基于待求时间层 $n + 1$ 时刻的守恒变量值：

$$
M { \frac { \mathrm { d } u } { \mathrm { d } t } } = R ( u ^ { n + 1 } )
$$

显式方法和隐式方法的本质差异在于右端残量项的计算是基于哪一时间层上守恒变量值的，两者与时间项离散格式无关，因此任何一种显式方法的时间离散格式均可用来构造隐式方法。本文将以时间项二阶向后差分格式(BDF2)为例进行非定常隐式DG方法构建，待求方程为： 用学

$$
\frac { M } { \Delta t } \left( \frac { 3 } { 2 } { \boldsymbol u } _ { \mathrm { h } } ^ { n + 1 } - 2 { \boldsymbol u } _ { \mathrm { h } } ^ { n } + \frac { 1 } { 2 } { \boldsymbol u } _ { \mathrm { h } } ^ { n - 1 } \right) = \underbrace { { \boldsymbol R } (  { \boldsymbol u } _ { \mathrm { h } } ^ { \mathrm { M P } } ) } _ { \times \mathrm { a s s } } + \frac { 1 } { 2 } \sum _ { i , j = 1 } ^ { \infty } a _ { i j } ^ { j } \dots a _ { i j } ^ { j } ,
$$

非定常隐式方法构建的关键是确保式(11）精确成立，其所有的工作均是在调和计算效率/存储量同式(11)精确成立之间的矛盾。由于式(11)经离散后为一大型非线性代数系统，为了对其进行求解本文采用Newton迭代法。首先构造残量方程：

$$
R _ { \mathrm { e } } ( { \mathbf { \mathbf { \mathbf { u } } } } _ { \mathrm { h } } ^ { n + 1 } ) = \frac { M } { \Delta t } \left( \frac { 3 } { 2 } { \mathbf { \mathbf { \mathbf { u } } } } _ { \mathrm { h } } ^ { n + 1 } - 2 { \mathbf { \mathbf { \mathbf { u } } } } _ { \mathrm { h } } ^ { n } + \frac { 1 } { 2 } { \mathbf { \mathbf { \mathbf { u } } } } _ { \mathrm { h } } ^ { n - 1 } \right)
$$

$$
- \pmb { R } ( \pmb { u } _ { \mathrm { h } } ^ { n + 1 } ) = 0
$$

基于Newton迭代的线性化处理结果为：

$$
\frac { \mathrm d R _ { \mathrm { e } } } { \mathrm d u _ { \mathrm { h } } } ( u _ { \mathrm { h } } ^ { n + 1 , j } - u _ { \mathrm { h } } ^ { n + 1 , j - 1 } ) = - R _ { \mathrm { e } } ( u _ { \mathrm { h } } ^ { n + 1 , j - 1 } )
$$

式中 $j = 1 , 2 , \cdots , \delta ,$ $\delta$ 为迭代总次数， ${ \pmb u } _ { \mathrm { h } } ^ { n + 1 , j }$ 为第$j$ 次迭代的待求时间层 $n { + } 1$ 上的守恒变量值。将式(12)带入式（13）中，可得到迭代过程为：

$$
\{ \begin{array} { l l } { \displaystyle \mathfrak { i } : u _ { \mathrm { h } } ^ { n + 1 , 0 } = u _ { \mathrm { h } } ^ { n } } \\ { \displaystyle \mathrm { i i } : ( \frac { 3 } { 2 } \frac { M } { \Delta t } - \frac { \mathrm { d } R } { \mathrm { d } u _ { \mathrm { h } } } ) ( u _ { \mathrm { h } } ^ { n + 1 , j } - u _ { \mathrm { h } } ^ { n + 1 , j - 1 } ) = } \\ { \displaystyle \quad - ( \frac { M } { \Delta t } ( \frac { 3 } { 2 } u _ { \mathrm { h } } ^ { n + 1 , j - 1 } - 2 u _ { \mathrm { h } } ^ { n } + \frac { 1 } { 2 } u _ { \mathrm { h } } ^ { n - 1 } ) -  } \\ {   R ( u _ { \mathrm { h } } ^ { n + 1 , j - 1 } ) ) } \\ { \displaystyle \mathrm { i i i } : u _ { \mathrm { h } } ^ { n + 1 } = u _ { \mathrm { h } } ^ { n + 1 , \delta } } \end{array} 
$$

首先，Jacobi矩阵 $\mathrm { d } R / \mathrm { d } u _ { \mathrm { h } }$ 的计算对于黏性流动若采用解析方法通常是困难的，因此本文采用数值方法进行近似计算：

$$
\frac { \mathrm { d } R } { \mathrm { d } u } \lvert { u } _ { \mathrm { h } } = { u } _ { \mathrm { h } } ^ { n } = \frac { R ( u _ { \mathrm { h } } ^ { n } + \varepsilon ) - R ( u _ { \mathrm { h } } ^ { n } ) } { \varepsilon }
$$

其中 $\varepsilon$ 为一小量，例如可采用 $\varepsilon \approx | | \boldsymbol { u } | | \times 1 0 ^ { - 8 }$

其次，对于迭代过程（14）中ii式的求解。对其进行整理可写为：

$$
A \left( \boldsymbol { \mathfrak { u } } _ { \mathrm { h } } ^ { n + 1 , j } - \boldsymbol { \mathfrak { u } } _ { \mathrm { h } } ^ { n + 1 , j - 1 } \right) = B
$$

$$
A = \frac { 3 } { 2 } \frac { M } { \Delta t } - \frac { d R } { d u _ { \mathrm { h } } } ,
$$

$$
\begin{array} { c } { { \displaystyle B = - \biggl [ \frac { M } { \hbar \otimes \Delta t } \left( \frac { 3 } { 2 } { \pmb u } _ { \mathrm { h } } ^ { n + 1 , j - 1 } - 2 { \pmb u } _ { \mathrm { h } } ^ { n } + \frac { 1 } { 2 } { \pmb u } _ { \mathrm { h } } ^ { n - 1 } \right) - } } \\ { { \displaystyle \Upsilon ( { \pmb u } _ { \mathrm { h } } ^ { n } ) } } \end{array}
$$

”式(16)为大型线性方程组，待求值为网格单元上所有自由度上守恒变量的值。然而其系数矩阵A通常具有很大的条件数，造成了方程(16)严重病态，这为方程组的直接求解带来了困难。因此，在CFD中的隐式方法广泛采用对系数矩阵先预处理再进行迭代求解的策略，例如块对角预处理、Gauss-Seidual预处理、LU分解等[13]。本文采用块Gauss-Seidual迭代完成对方程 $( \mathfrak { N } )$ 的求解的，求解过程均是以每个单元上所有自由度的守恒变量值构成的矩阵为元素进行的。其迭代过程为：

$$
\Big \{ \bigotimes _ { ( L + D ) \Delta u ^ { n + 1 , j } = B - U \cdot \Delta u ^ { n + 1 , j - 1 } \ j = 1 , 3 , 5 \cdot \cdot \cdot } ^ { A \times \bigotimes \cdot \bigotimes \cdot \bigcirc }
$$

式中， $\mathbf { \Delta } _ { L , D , U }$ 分别为下三角阵、对角阵和上三角阵。 $\Delta { \boldsymbol u } ^ { n + 1 , j } = { \boldsymbol u } _ { \mathrm { h } } ^ { n + 1 , j } - { \boldsymbol u } _ { \mathrm { h } } ^ { n + 1 , j - 1 }$ 。在进行第奇次和第偶次迭代时分别采用向下扫描和向上扫描依次求解；每次只需要对每个单元的系数矩阵进行求逆运算，显著降低了条件数和计算量。

至此便完成了对非线性代数系统式(11)的求解过程。对于非定常流动，时间推进的每一个时间步上式（11）的计算准确度均与流场精度密切相关；另一方面，由于对式（11)的计算采用了迭代求解策略，总是存在误差使得其不可能精确成立。因此，对于非定常流动的迭代收敛判据是在保证较少的迭代次数与式(11)计算准确度之间做出的折中：

$$
\left\| \frac { M } { \Delta t } \bigg ( \frac { 3 } { 2 } \boldsymbol { u } _ { \mathrm { h } } ^ { n + 1 } - 2 \boldsymbol { u } _ { \mathrm { h } } ^ { n } + \frac { 1 } { 2 } \boldsymbol { u } _ { \mathrm { h } } ^ { n - 1 } \bigg ) - R ( \boldsymbol { u } _ { \mathrm { h } } ^ { n + 1 } ) \right\| < \xi \left\| \boldsymbol { u } \right\|
$$

本文中 $\xi = 1 0 ^ { - 4 }$ [9]。

需要指出的是：1)非定常流动中时间步长 $\Delta t$ 必须在所有网格上保持一致；2)式(18)为隐式非定常流动判断Newton迭代收敛的唯一判据，因此在计算过程中可以采用与隐式定常流动中一致的加速方案，例如Jacobi矩阵延迟更新、线性方程组（16）有限步迭代等。3）隐式DG方法虽然能够显著提升时间步长，但是在每个时间步上通常需要数倍于显式方法的计算量与存储量，尤其是在高阶精度和大网格量的情形下。所以，想要彻底改变隐式方法的计算效率寻求更好的计算策略至关重要。

圆为远场边界条件、内部圆为无穿透（反射）边界条件。图2为网格量为3000的网格上2阶精度$\left( p _ { 1 } \right)$ 时显式方法与非定常隐式方法的残差收敛历史图，如图所示，隐式方法的计算效率显著高于显式方法。图3表示圆柱表面压力系数分布，如图所示，圆柱上下壁面高度重合且左右对称分布符合无黏圆柱扰流特点，另外其与Bassi[16] 的计算结果高度吻合也证明了计算的准确性。图4和图5分别表示4阶精度时马赫数 $\boldsymbol { { M a } }$ 和密度分布等值线图，其值分别为 $M a _ { i } = 0 . 0 3 6 \times ( i - 1 ) , i = 1 , \cdot \cdot \cdot , 2 6 ; \rho _ { i } =$ $0 . 0 2 \times { \left( i - 1 \right) } + 0 . 9 4 , i = 1 , 2 , \cdots , 2 3 ,$ 0

# 3数值结果

基于本文构造的非定常隐式DG方法的计算方案，对无黏圆柱扰流和卡门涡街现象（ $R e { = } 4 0 )$ 进行了数值模拟研究。前者旨在证明本文计算方案的正确性，后者通过非定常的卡门涡街现象以验证非定常隐式DG方法的计算效率和计算精度。

# 3.1无黏圆柱扰流

亚音速无黏圆柱扰流无流动损失、几何上中心对称的特点使得流场结构理论上高度对称弯曲的壁面利于研究高精度CFD 方法对凡何精度的依赖性。因此在网格量分别为74、5283000的三套网格上进行了2阶精度 $\left( p _ { 1 } \right)$ 至4解精度 $\left( p _ { 3 } \right)$ 的无黏圆柱扰流流场计算。

![](images/c271451c082f1d1a040cedf92fe8e55737fe3a6a097de47f86e2072cffc5cccd.jpg)  
图1网格示意图 $( 7 4 , \ p _ { 3 } )$ （202 Fig.1 Grids of isentropic flow around cylinder $( 7 4 , p _ { 3 } )$ （20

圆柱扰流来流条件为 $M a = 0 . 3 8$ ， $p _ { \infty } = 1 0 1 3 2 5$ Pa $T _ { \infty } ~ = ~ 2 7 3 \mathrm { ~ K ~ }$ ；高阶壁面的构造基于圆弧逼近；网格量为74的计算域示意图如图1所示；外部

![](images/a6c817455ae13e5fa05f5e376aebcf6b81fe9d76aab53c98168a0c0d7330d03b.jpg)

![](images/1e074297c97d3300fc157cce315c5f13ad3e74098ca80639967f485fd42ded86.jpg)  
Fig. 2 .Energy residual convergence history (3000, $p _ { 1 }$ ）  
图3上、下表面压力系数分布图 Fig.3 Pressure coefficient distribution around cylinder

表1为2阶精度至4阶精度时不同网格量上得到的熵误差。如表所示，在3阶和4阶精度时流场的真实精度均达到了设计值；但2阶精度时真实计算精度低于设计精度，这是由于在2阶精度时单元的等参变换与仿射变换相同，使得边界单元采用了直边界而造成的。这表明了高阶壁面近似对高精度CFD 方法至关重要；另外，本文构建的隐式DG 方法实际精度能够达到设计精度。

![](images/a0c1944b68c7d8fc4b3e69ed310c7aaadaa245af3dd9167b534444ce4e30988d.jpg)  
图4Ma分布云图(3000，p3) Fig.4 $\mathit { M a }$ contour around cylinder(3000,:

![](images/7408698b316310e5b547052ce2df687c7674bd2b22fb3fa2e2788473c157c05a.jpg)  
图5密度分布云图（3000, $p _ { 3 }$ ）  
Fig.5 Density contour around cylinder (3000,p3)

Table 1 Accuracy verification using implicit DG

表1基于非定常隐式DG方法的精度验证  

<html><body><table><tr><td rowspan="2">Element number</td><td colspan="2">p1</td><td colspan="2">P2</td><td colspan="2">p3</td></tr><tr><td>Error</td><td>Order</td><td>Error</td><td>Order</td><td>Error</td><td>Order</td></tr><tr><td>74</td><td>1.4×10-2</td><td>1</td><td>4.1×10-3</td><td>1</td><td>1.1×10-3</td><td>1</td></tr><tr><td>528</td><td>3.8×10-3</td><td>1.33</td><td>1.0×10-4</td><td>3.75</td><td>3.2×10-6</td><td>5.87</td></tr><tr><td>3000</td><td>7.1×10-4</td><td>1.49</td><td>3.1×10-6</td><td>4.06</td><td>1.0×10-8</td><td>5.90</td></tr></table></body></html>

# 3.2卡门涡街

卡门涡街现象数值模拟的计算域如图6所示，其网格量为6368，圆柱壁面分布40个网格点，同样地对其边界单元进行数值积分时采用圆弧逼近边界边的曲边三角形进行计算。自由来流参数为 $p _ { \infty } = { }$ $1 0 1 3 2 5 \ \mathrm { P a }$ ， $T _ { \infty } = 2 7 3 \mathrm { ~ K ~ }$ ， $M a = 0 . 3$ ，以圆柱直径和远场边界参数定义的雷诺数 $R e { = } 1 0 0$ ；圆柱壁面为等温 $( T _ { \mathrm { w a l l } } = 2 7 3 \ \mathrm { K } )$ ）无滑移边界条件。本文对其进行了2阶精度 $\left( p _ { 1 } \right)$ 至4阶精度 $\left( p _ { 3 } \right)$ 的计算。所有精度下的流场初始化参数均为同一个收敛的2阶定常流动。

![](images/9e6921538e663ea129cc65b3b5f42b82a86e3b18dba70b2ac6fb437362369d9d.jpg)  
图6网格示意图  
Fig.6 Grids of Karmann vortex street phenomenon

表2为不同精度下隐式DG方法的时间步长与经测试得到保持稳定的显式方法时间步长对比。如表所示，隐式DG方法的时间步长通常比显式方法高出两个数量级，这表明本文发展的隐式DG方法能够在远大于显式方法的时间步长下保持稳定。

表2隐式方法和显式方法时间步长  

<html><body><table><tr><td>Table Time step suited for explicit and implicit DG</td><td></td><td>p2</td><td>p3</td></tr><tr><td>Space accuracy</td><td>P1 2.0×10-5</td><td>1.0×10-5</td><td>7.0×10-6</td></tr><tr><td>Time step(explicit) Time step(implicit)</td><td>2.0×10-3</td><td>1.0×10-3</td><td>5.0×10-4</td></tr></table></body></html>

图7为4阶精度下某一时刻的涡量云图，图中涡量值的分布为 $\mathcal { Q } _ { i } = 1 0 \times ( i - 1 ) - 1 0 0 , j = 1 , \cdots , 2 1 .$ 图8和图9分别为从同一初始流场开始计算，显式方法和隐式方法得到的 $t = 0 . 2$ 时刻壁面摩擦阻力与压力系数系数分布。如图所示，隐式方法的计算结果与显式方法几乎重合，这表明了隐式方法的正确性。图10和图11分别表示升力系数和阻力系数随迭代步数的变化图，当非定常特性保持稳定后，随着涡的脱落升力系数和阻力系数均呈现周期性变化规律。当两者变化保持周期性时，提取一个周期的峰值差得到如表3所示的物理参数。在4阶精度 $\left( p _ { 3 } \right)$ 下与Collis[17]的结果进行对比发现，升力系数 $C _ { \mathrm { { L } } }$ 和阻力系数 $C _ { \mathrm { D } }$ 的峰值误差分别为 $1 . 8 \%$ 和 $6 . 0 \%$ ，表征非定常的无量纲参数斯特劳哈尔数 $S t$ 的误差为 $1 . 1 \%$ 5这表明本文构造的非定常隐式DG方法的精度能够达到预期值。

![](images/4e78f24c8cfeea4a4226b0675d0a5ddc14e64fd2da7f7daf6d481314f15df8da.jpg)  
图7涡量云图(p3)Fig.7Vortex contour $\left( p _ { 3 } \right)$

图8 $t = 0 . 2$ 时刻摩擦阻力系数分布 Fig.8 Skin friction coefficient distribution at $t = 0 . 2$ S   
![](images/99f4e1c5326525943a1aabde92e3adca39f9d50a93aac1716a9a81465a21ce6f.jpg)  
'ig.11 Drag coefficient changing with iteration steps

![](images/bf522b2d949e9f9c17966c28f1dcbddcc7d78baa5e66b24ac14666ad98da255b.jpg)  
图9 $t = 0 . 2$ 时刻压力系数分布 Fig.9 Pressure coefficient distribution at $t = 0 . 2$ S

![](images/f4a83307c9c29ebffd9efa08cc127f54364354c69133021a007af5c110d90962.jpg)  
图10升力系数随迭代步数变化图

![](images/e9531ab1b4c534fe19cbcea9821a991938f814c45947399baaeaa7700ffb762c.jpg)  
Fig.10 Lift coefficient changing with iteration steps   
图11阻力系数随迭代步数变化图

etp.

表3不同精度下物理参数值  
Table 3 Physic parameter at different accuracy   

<html><body><table><tr><td></td><td>CD</td><td>CL</td><td>St</td></tr><tr><td>P1</td><td>1.3334</td><td>0.5991</td><td>0.1659</td></tr><tr><td>p2</td><td>1.4432</td><td>0.7238</td><td>0.1672</td></tr><tr><td>p3</td><td>1.4366</td><td>0.7380</td><td>0.1668</td></tr><tr><td>Collis[24]</td><td>1.4107</td><td>0.6960</td><td>0.165</td></tr></table></body></html>

# 4结论

本文针对非定常层流流动的隐式DG方法的构造进行研究，主要结论如下：

1）相比于显式方法，基于本文构造的非定常流动的隐式DG方法对定常流动也具有较高的求解效率，且实际精度均能达到设计值。另外，高阶壁面近似对高精度CFD方法至关重要。

2)非定常流动的隐式DG方法能够在大于显式方法两个数量级的时间步长上保持稳定，表明了隐式DG方法在求解非定常问题时具有达到较高求解效率的潜力。

3)本文构造的非定常流动的隐式DG方法与显式方法及相关文献比较均有较高的吻合度，表明了构造方法的正确性。

# 参考文献

[1]Wang Z J,FidKowsk K,Abgrall R,et al.High-Order CFD Methods:Current Status and Perspective [J]. International Journal for Numerical Methods in Fluids,2013, 72:811-845   
[2] Shu Chiwang.A Brief Survey on Discontinuous Galerkin Methods in Computational Fluid Dynamics [J].Advance in Mechanics,2013,43(6):541-554   
[3]Kroll N.ADIGMA-A European Project on the Development of Adaptive Higher-Order Variational Methods for Aerospace Applications [C]//47th AIAA Aerosapce Sciences Meeting,Orlando,Florida,2009   
[4]孙强，吕宏强，伍贻兆，等.基于高阶物面近似的自适应间断 有限元方法欧拉方程数值模拟[J].空气动力学学报2015 33(4):446-453 电子 SUN Qiang,LV Hongqing,WU Yizhao,etal.yAdaptive Discontinuous Galerkin Method to Solve Eler Equations Based on High-order Approximative Bumdary [J]. Acta Aerodynamica Sinic,2015,33(4): 446453   
[5] Ren Xiaodong,Gu Chunwei. Application of a Discontinuous Galerkin Method on the Compressible Flow in the Transonic Axial Compressor [J].Applied Thermal Engineering,2016,93:707-717   
[6]张来平,贺立新，刘伟，等.基于非结构/混合网格的高阶精 度格式研究进展[J].力学进展，2013，43(2)：202-236 ZHANG Laiping,HE Lixin,LIU Wei,et al.Reviews of High-order Methods on Unstructured and Hybrid Grid [J]. Advances in Mechanics,2013,43(2):202-23   
[7]于剑,阎超.Navier-Stokes 方程间断Galerkin方法研究 力学学报,2010,42(5):962-970 YU Jian,YAN Chao.Study on Discontinuous Galerkin Method for Navier-Stokes Equations [J]. Chinese Journal of Theoretical and Applied Mechanics, 2014,42(5): 962- 970   
[8] Jiang Zhenhua,Yan Chao,Yu Jian.High-Order Implicit Discontinuous Galerkin Schemes for Unsteady Compressible Navier-Stokes Equations [J].Chinese Journal of Aeronautics,2014,27(6):1384-1389   
[9] 郝海兵,张强,杨永.基于LU-SGS 迭代的 DGM 隐式方法 研究[J].西北工业大学学报,2014,32(3)：347-350 HAO Haibing,ZHANG Qiang，YANG Yong,et al． An Implicit Scheme of Discontinuous Galerkin Method Based on LU-SGS Iteration Method [J]. Journal of Northwestern Polytechnical University, 2014,32(3):246-350   
[10] Wang L,Mavriplis D J.Implicit Solution of the Unsteady Euler Equations for High-Order Accurate Discontinuous Galerkin Discretizations [J]. Journal of Computational Physics,2007,225:1994-2015   
[11] Persson P, Peraire J.Newton-GMRES precondition for Discontinuous Galerkin Discontinuous of the NavierStokes Equations [J].SIAM J Sci Comput,2007,30(6): 2709-27   
[12]谭勤学,林立,吴康,等.间断伽辽金方法在燃机空气系统的 用[J].工程热物理学报，2015,36(6)：1-6 TAN Qinxue,LIN Li,WU Kang,et al. Discontinuous Galerkin Method and Application for Gas Turbine's Secondary Air System [J]. Journal of Engineering Thermophysics,2015,36(6):1-6   
[13] Hao Zengrong,Gu Chunwei,Yin Song. Thermoelastic Simulations Based on Discontinuous Galerkin Methods: Formulation and Application in Gas Turbines [J].International Journal of Turbo& Jet-Engines,2015,33(2):1989- 1992   
[14] Hao Zengrong,Gu Chunwei,Ren Xiaodong. The Application of Discontinuous Galerkin Methods in Conjugate Heat Transfer Simulations of Gas Turbines [J]. Energies, 2014, 7: 7857-7877   
[15] Dolejsi V Feistauer M. Discontinuous Galerkin Method Analysis and Application to Compressible Flow [M]. Berlin: Springer, 2016: 423-424   
[16] Bassi F,Rebay S.High Order Accurate Discontinuous Finite Element Solution of 2D Euler Equations [J].Journal of Computational Physics,1997,138:251-285   
[17]Collis S S.Discontinuous Galerkin Method of Turbulence Simulation [R].Center for Turbulence Research Proceeding of the Summer Program,2002,155-167