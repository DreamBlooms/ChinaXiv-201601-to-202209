# 线性菲涅尔太阳能系统光学性能研究与优化

邱羽，何雅玲\*，程泽东

（西安交通大学能源与动力工程学院，热流科学与工程教育部重点实验室，陕西，西安，710049）

摘要：为研究与优化线性菲涅尔太阳能系统的光学性能，本文采用蒙特卡罗光线追迹法（MCRT）自编程建立了整个系统的三维光学模型。基于此，分析了不同反射镜型式、瞄准位置、形面误差以及地理位置等对系统光学性能的影响规律，优化了反射镜几何参数与瞄准位置。结果表明，不同镜面型式下系统性能均存在最优值，此时圆柱面与抛物面镜光学性能几乎一样。对于吸热管热流分布，可通过优化设计反射镜瞄准线来提高热流分布均匀性，一定的形面误差也会改善其均匀性。在地理上，该系统在北纬 $2 0 ^ { \circ } { \sim } 5 0 ^ { \circ }$ 的范围内年均光学效率在 $5 2 \% { \sim } 3 7 \%$ 之间，可在我国大部分地区应用。

关键词：太阳能；线性菲涅尔；复合抛物面二级反射器；蒙特卡罗光线追迹；光学性能

中图分类号：TK124 文献标识码：A

# Optical Performance Investigation and Optimization of a

# LinearFresnel Reflector Solar Collector

QIU Yu HE Ya-Ling CHENG Ze-Dong

KeyLaboratoryofThermo-FluidScienceandEngineringofMinistryofEducation,ScholofEnergyandPowerEnginering,

Xi'an Jiaotong University, Xi'an, Shaanxi,71oo49,China)

Abstract: A 3D Monte Carlo ray tracing model was developed in FORTRAN for a linear Fresnel reflector solar collector in order to investigate and optimize its optical performance. The performance of three typical mirors,the effects of the mirror aim lines, slope error,and location, etc.were investigated. The results show that the optimal radius and focal length could be found for the cylindrical and parabolic mirors,respectively.The optimized cylindrical mirror could achieve the same performance as that of the optimized parabolic mirror. The uniformity of the concentrated solar flux on the absorber tube could be improved by designing the aim lines and using the mirror with a certain slope error.In addition, the LFR system whose yearly mean optical efficiency ranges between $52 \%$ and $3 7 \%$ from $\mathrm { N } 2 0 ^ { \circ }$ to $\mathrm { N } 5 0 ^ { \circ }$ could be applied in most area of China.

Keywords: Solar energy; Linear Fresnel reflector; Compound Parabolic Collctor (CPC); Monte Carlo ray tracing(MCRT); Optical performance

# 0引言

近年来，线性菲涅尔反射式太阳能热发电技术得到了快速发展，多套发电系统已相继投入运行。线性菲涅尔系统的光学性能是衡量系统性能的关键参数，它直接影响系统的光热转化过程及后续发电过程的性能，相关基础研究获得了广泛关注。Haberle[1等研究了世界上第一个线性菲涅尔示范系统Solarmundo的光学性能，得到了垂直入射时吸热管上的辐射热流分布和典型工况下系统的光热效率。杜春旭等[2]探讨了减少镜场阴影和遮挡损失的方法，得到了东西向布置系统无阴影无遮挡损失时的镜场设计方法。Abbas 等3]对比分析了使用圆柱面与抛物面反射镜的线性菲涅尔系统在平面吸热器上的光斑分布情况。Grena 等[4提出了一种具有双翼二级反射器的线性菲涅尔系统，并研究了其光学性能与热流分布特性。目前，针对线性菲涅尔系统光学性能的预测及关键参数对其影响方面的研究还比较少，相关参数的影响机理也还不明确。

为研究与优化线性菲涅尔系统的光学性能，本文推导了其反射镜跟踪方程及光线追迹方程，采用蒙特卡罗光线追迹法(Monte Carlo ray tracing,MCRT)[5-7建立了系统动态光学模型，并基于此进行了一系列分析与优化研究。

# 1物理模型

本文所研究的线性菲涅尔系统如图1所示，主要由线性菲涅尔反射镜场（LinearFresnelReflector,

LFR）、复合抛物面二级反射镜(CompoundParabolicCollector,CPC)、具有选择性吸收涂层的吸热管以及玻璃板等组成。系统主要参数参见表1。其中，反射镜场由水平布置的几何参数相同的条状反射镜构成，每组反射镜通过独立跟踪太阳位置，从而将阳光反射到固定的CPC腔体内。反射镜场东西对称布置，将东侧反射镜由西至东依次标记为M1-M25,西侧反射镜由东至西依次标记为M26-M50。复合抛物面二级反射镜的型线左右对称，由渐开线AB和抛物线 BC 组成，如图1所示，型线通式见式 $( 1 ) ^ { [ 8 ] }$ 。

$$
\left\{ \begin{array} { l l } { y = r _ { 1 } \sin \theta _ { \mathrm { o } } - \rho \cos \theta _ { \mathrm { o } } } \\ { z = - r _ { 1 } \cos \theta _ { \mathrm { o } } - \rho \sin \theta _ { \mathrm { o } } } \end{array} \right.
$$

式中：

$$
: \rho = r _ { 1 } \big ( \theta _ { \circ } + \beta \big ) , \operatorname { a r c c o s } ( r _ { 1 } / r _ { 2 } ) \le \theta _ { \circ } \le \pi / 2 + \theta _ { \mathrm { m a x } }
$$

$$
\mathrm { B C } : \rho = \frac { r _ { \mathrm { 1 } } \left[ \theta _ { \mathrm {  o } } + \theta _ { \operatorname* { m a x } } + \pi / 2 + 2 \beta - \cos ( \theta _ { \mathrm { o } } - \theta _ { \operatorname* { m a x } } ) \right] } { 1 + \sin ( \theta _ { \mathrm { o } } - \theta _ { \operatorname* { m a x } } ) }
$$

$$
\pi / 2 + \theta _ { \mathrm { { m a x } } } < \theta _ { \mathrm { { o } } } \leq \theta _ { \mathrm { { o m a x } } }
$$

其中 $\beta = \sqrt { ( r _ { 2 } / r _ { 1 } ) ^ { 2 } - 1 } - \operatorname { a r c c o s } ( r _ { 1 } / r _ { 2 } )$

图1线性菲涅尔系统示意图  
![](images/50ff64e643ad5c6033909a9cd63782c02976682ce81a2c5950b79ed884b3eb95.jpg)  
Fig.1 Sketch of linear Fresnel reflector solar collector

# 2跟踪方程与蒙特卡罗光线追迹过程

# 2.1反射镜跟踪方程

为研究系统光学性能，需先确定每组反射镜在任意时刻的跟踪角 $\theta _ { \mathrm { { m } } }$ 。为此，建立系统右手直角坐标系，包括入射系 $X _ { \mathrm { i } } Y _ { \mathrm { i } } Z _ { \mathrm { i } }$ 、镜面系 $X _ { \mathrm { m } } Y _ { \mathrm { m } } Z _ { \mathrm { m } }$ 、地面系$X _ { \mathrm { g } } Y _ { \mathrm { g } } Z _ { \mathrm { g } }$ 和吸热器系 $X _ { \mathrm { r } } Y _ { \mathrm { r } } Z _ { \mathrm { r } }$ ，如图1所示。 $\theta _ { \mathrm { { m } } }$ 定义为反射镜绕 $X _ { \mathrm { m } }$ 旋转后 $Y _ { \mathrm { m } }$ 正向与 $Y _ { \mathrm { g } }$ 正向间的夹角，且当 $X _ { \mathrm { m } }$ 逆时针旋转时为正。 $\theta _ { \mathrm { { m } } }$ 可由镜面中心反射光线的瞄准线 $( x _ { \mathrm { g } } , y _ { \mathrm { a i m } } , z _ { \mathrm { a i m } } )$ 确定，如图1。当 $\pi { \le } A { \le } 3 \pi / 2$ ，随机跟踪误差 $R _ { \mathrm { t e } }$ 服从 $N ( 0 , \sigma _ { \mathrm { t e } } ^ { 2 } .$ )分布时，由式(2)可得西边反射镜的跟踪角 $\theta _ { \mathrm { { m } } }$ 。同理可得其他情况下的跟踪角。

$$
\theta _ { \mathrm { { m } } } = \left( \varphi _ { _ 2 } - \varphi _ { 1 } \right) / 2 + R _ { \mathrm { { t e } } }
$$

$$
\varphi _ { \mathrm { { i } } } = \tan ^ { - 1 } \left( { \frac { \tan \alpha } { \sin \left| A - \pi \right| } } \right) , \varphi _ { \mathrm { { 2 } } } = \tan ^ { - 1 } \left| { \frac { z _ { \mathrm { { a i m } } } } { y _ { \mathrm { { a i m } } } - y _ { \mathrm { { m } } } } } \right|
$$

式中， $\varphi _ { 1 } , \varphi _ { 2 }$ 如图1所示， $\sigma _ { \mathrm { t e } }$ 为跟踪误差的标准差，

$y _ { \mathrm { { m } } }$ 为反射镜轴线在 $X _ { \mathrm { g } } Y _ { \mathrm { g } } Z _ { \mathrm { g } }$ 中的 $y$ 坐标值， $\boldsymbol { a }$ 与 $A$ 分别为太阳高度角和方位角，可由当地纬度 $\varphi$ 、太阳时 $t _ { \mathrm { s } }$ 及日序数 $N _ { \mathrm { d a y } }$ 求得[9]。

表1系统结构参数及光学参数[][4]Table 1 Geometric and optical parameters.  

<html><body><table><tr><td>项目</td><td>值</td><td>项目</td><td>值</td></tr><tr><td>镜子数nm</td><td>50</td><td>0omax / rad</td><td>3.36</td></tr><tr><td>镜宽Wm／m</td><td>0.5</td><td>玻璃板宽/m</td><td>0.832</td></tr><tr><td>镜长Lm／m</td><td>100</td><td>玻璃板厚/m</td><td>0.003</td></tr><tr><td>镜轴距dm/m</td><td>0.598</td><td>玻璃板高Hglass/m</td><td>9.805</td></tr><tr><td>管高Ht/m</td><td>10</td><td>镜反射率pi</td><td>0.92</td></tr><tr><td>管半径r/m</td><td>0.10</td><td>玻璃板透射率t</td><td>0.95,</td></tr><tr><td>r2/m</td><td>0.186</td><td>玻璃折射率</td><td>1.577</td></tr><tr><td>r3/m</td><td>0.466</td><td>CPC 反射率p2</td><td>0.95</td></tr><tr><td>0max/°</td><td>60°</td><td>吸热管吸收率αt</td><td>0.94</td></tr></table></body></html>

# 2.2蒙特卡罗光线追迹过程

# 2.2.1随机光子初始化

在蒙特卡罗光线追迹过程中将各反射镜面设定为随机光子发射面，并假设太阳辐射在镜面上均匀分布，则入射光线在镜面系中与反射镜的交点可表示为 $\pmb { P } _ { \mathrm { m } }$ ，如式(4)。考虑阳光的不平行夹角$\delta { = } 9 . 3 0 \mathrm { m r a d }$ ，则在 $X _ { \mathrm { i } } Y _ { \mathrm { i } } Z _ { \mathrm { i } }$ 系中的入射向量可表示为$I _ { \mathrm { i } }$ ，如式(4)。

$$
\begin{array} { r } { P _ { \mathrm { m } } = \left[ \begin{array} { c } { - L _ { \mathrm { m } } \cdot \xi _ { 1 } } \\ { W _ { \mathrm { m } } ( \xi _ { 2 } - 0 . 5 ) } \\ { f _ { \mathrm { m } } ( Y _ { \mathrm { m } } ) } \end{array} \right] , I _ { \mathrm { i } } = \left[ \begin{array} { c } { \delta _ { \mathrm { s o l } } \cos \theta _ { \mathrm { s o l } } } \\ { \delta _ { \mathrm { s o l } } \sin \theta _ { \mathrm { s o l } } } \\ { \sqrt { 1 - \delta _ { \mathrm { s o l } } ^ { 2 } } } \end{array} \right] } \end{array}
$$

$$
\delta _ { \mathrm { s o l } } \mathrm { = s i n \mathrm { ^ { - 1 } } } \sqrt { \xi _ { 3 } \sin ^ { 2 } ( \delta / 2 ) } \ , \ \theta _ { \mathrm { s o l } } \mathrm { = } 2 \pi \xi _ { 4 }
$$

式中， $f _ { \mathrm { m } } ( \boldsymbol { y } )$ 为 $Y _ { \mathrm { m } } Z _ { \mathrm { m } }$ 平面中的反射镜截面型线方程，本文中所有 $\xi$ 均服从 $U [ 0 , 1 ]$ 分布。

那么，某面反射镜上的每个光子所携带的能量可表示为：

$$
W _ { \mathrm { p } } = D N I \cdot L _ { \mathrm { m } } W _ { \mathrm { m } } \eta _ { \mathrm { c o s } } \cdot n _ { \mathrm { p } }
$$

式中， $\eta _ { \mathrm { c o s } }$ 为反射镜余弦效率， $n _ { \mathrm { p } }$ 为反射镜上所追迹的光子数， $D N I$ 为太阳直接辐射强度[9]。

# 2.2.2光子在反射镜或CPC上的反射

以图1中光子在反射镜上的反射过程为例来说明针对反射过程的模拟。先通过坐标变换将 $I _ { \mathrm { i } }$ 转换为 $X _ { \mathrm { g } } Y _ { \mathrm { g } } Z _ { \mathrm { g } }$ 系下的 $I _ { \mathrm { { g } } }$ 和 $X _ { \mathrm { m } } Y _ { \mathrm { m } } Z _ { \mathrm { m } }$ 系下的 $\boldsymbol { I _ { \mathrm { m } } }$ 。接着产生一个随机数 $\xi$ 来判断光子是否发生反射，若 $\xi$ 小于$\rho _ { 1 }$ 则发生反射，那么由式(7)可求得 $X _ { \mathrm { m } } Y _ { \mathrm { m } } Z _ { \mathrm { m } }$ 下的反射向量 $\pmb { R } _ { \mathrm { m } }$ 。最后再将 $\pmb { R } _ { \mathrm { m } }$ 转换为地面系下的 $R _ { \mathrm { g } }$ 。

$$
R _ { \mathrm { n } } = 2 \big ( I _ { \mathrm { m } } \cdot N _ { \mathrm { m } } \big ) N _ { \mathrm { m } } \cdot I _ { \mathrm { m } }
$$

$$
N _ { \mathrm { m } } = \left[ \begin{array} { c c c } { 1 } & { 0 } & { 0 } \\ { 0 } & { \cos k _ { \mathrm { m } } } & { - \sin k _ { \mathrm { m } } } \\ { 0 } & { \sin k _ { \mathrm { m } } } & { \cos k _ { \mathrm { m } } } \end{array} \right] \left[ \begin{array} { l } { \rho _ { \mathrm { m } } \cos \varphi _ { \mathrm { m } } } \\ { \rho _ { \mathrm { m } } \sin \varphi _ { \mathrm { m } } } \\ { \sqrt { 1 - { \rho _ { \mathrm { m } } } ^ { 2 } } } \end{array} \right]
$$

式中， $N _ { \mathrm { m } }$ 为 $\pmb { P } _ { \mathrm { m } }$ 处的单位法向量， $\rho _ { \mathrm { m } }$ 和 $\varphi _ { \mathrm { m } }$ 为形面误差 $\sigma _ { \mathrm { s e } }$ 引起的镜面法线径向与切向偏角[10]， $k _ { \mathrm { m } }$ 为$\pmb { P } _ { \mathrm { m } }$ 处镜面型线斜率。可采用与上述类似的方法计算CPC上的反射过程。

# 2.2.3阴影与遮挡

当入射光线被相邻反射镜挡住，光线将不能到达镜面，从而在镜面上形成阴影。下面以图1中的阴影过程为例，给出判断光线是否被挡住的方法。首先，将a镜系下的入射光线与a镜的交点 $P _ { \mathrm { { a } } }$ 转化为b镜系下的 $P _ { \mathrm { a b } }$ ，如式(9)。然后，将该点的 $I _ { \mathrm { { g } } }$ 转换为b系下的 $\boldsymbol { I _ { \mathrm { b } } }$ ，式(10)。由 $P _ { \mathrm { a b } }$ 和 $\boldsymbol { I _ { \mathrm { b } } }$ 可得 $\boldsymbol { \mathbf { b } }$ 系下的入射光线方程。接着联立光线方程与b镜在b系中的曲面方程即可求得光线与b镜的交点 $\pmb { P } _ { \mathbf { b } }$ 。若 $\pmb { P } _ { \mathrm { b } }$ 在b镜上，则该条光线被挡住。用与上述相似的方法可判断入射光线是否被吸热器挡住，同时也可判断反射光线是否被相邻反射镜遮挡。

$$
\begin{array} { r l } & { P _ { \mathrm { a b } } = \left[ \begin{array} { c c } { 1 } & { 0 } \\ { 0 } & { \cos \theta _ { \mathrm { m } } ( \mathbf { b } ) \sin \theta _ { \mathrm { m } } ( \mathbf { b } ) } \\ { 0 } & { \sin \theta _ { \mathrm { m } } ( \mathbf { b } ) \cos \theta _ { \mathrm { m } } ( \mathbf { b } ) } \end{array} \right] \times } \\ & { \left\{ \left[ \begin{array} { c c } { 1 } & { 0 } \\ { 0 \cos \theta _ { \mathrm { m } } ( \mathbf { a } ) - \sin \theta _ { \mathrm { m } } ( \mathbf { a } ) } \\ { 0 \sin \theta _ { \mathrm { m } } ( \mathbf { a } ) } & { \cos \theta _ { \mathrm { m } } ( \mathbf { a } ) } \end{array} \right] P _ { \mathrm { a } } + \left[ \begin{array} { c c } { 0 } & { 0 } \\ { y _ { \mathrm { m } } ( \mathbf { a } ) - y _ { \mathrm { m } } ( \mathbf { b } ) } \\ { 0 } & { 0 } \end{array} \right] \right\} } \end{array}
$$

$$
\begin{array} { r } { I _ { \mathrm { b } } = \left[ \begin{array} { c c c } { 1 } & { 0 } & { 0 } \\ { 0 } & { \cos \theta _ { \mathrm { m } } ( \mathrm { b } ) } & { \sin \theta _ { \mathrm { m } } ( \mathrm { b } ) } \\ { 0 } & { - \sin \theta _ { \mathrm { m } } ( \mathrm { b } ) } & { \cos \theta _ { \mathrm { m } } ( \mathrm { b } ) } \end{array} \right] I _ { \mathrm { g } } } \end{array}
$$

# 2.2.4光子在玻璃板中的折射

若反射光子没有被遮挡，则接着求解光子与玻璃板的交点。先将反射光线与镜面交点 $\pmb { P } _ { \mathrm { m } }$ 变换为地面系下的 $P _ { \mathrm { g } }$ ，如式(11)，结合 $R _ { \mathrm { g } }$ 即可得地面系中的反射光线方程。

然后联立反射光线方程与玻璃板下表面在$X _ { \mathrm { g } } Y _ { \mathrm { g } } Z _ { \mathrm { g } }$ 系中的方程 $z = H _ { \mathrm { g l a s s } }$ 即可求得二者交点。接着用一个 $\xi$ 来判断光子是否折射，若 $\xi < \tau$ 则发生折射。若发生折射，则玻璃中的折射向量 $\pmb { R } _ { \mathrm { t } }$ 可由式(12)计算。接着可求得折射光线与玻璃板上表面的交点，而透射前后光子向量不变仍为 $R _ { \mathrm { g } }$ 。

$$
\begin{array} { r l } & { P _ { \mathrm { g } } = \left[ \begin{array} { c c c } { 1 } & { 0 } & { 0 } \\ { 0 } & { \cos \theta _ { \mathrm { m } } } & { - \sin \theta _ { \mathrm { m } } } \\ { 0 } & { \sin \theta _ { \mathrm { m } } } & { \cos \theta _ { \mathrm { m } } } \end{array} \right] P _ { \mathrm { m } } + \left[ \begin{array} { c c } { 0 } \\ { y _ { \mathrm { m } } } \\ { 0 } \end{array} \right] } \\ & { R _ { \mathrm { t } } = n _ { \mathrm { i } } \cdot n _ { \mathrm { t } } R _ { \mathrm { g } } + \left\{ n _ { \mathrm { i } } \cdot n _ { \mathrm { t } } R _ { \mathrm { g } } \cdot N _ { \mathrm { w } } - \right. } \\ & { \left. \sqrt { 1 - \left( n _ { \mathrm { i } } \cdot n _ { \mathrm { t } } \right) ^ { 2 } \left[ 1 - \left( R _ { \mathrm { g } } \cdot N _ { \mathrm { w } } \right) ^ { 2 } \right] } \right\} N _ { \mathrm { w } } } \end{array}
$$

式中， $N _ { \mathrm { w } }$ 为玻璃板法向量。

# 2.2.5光子在吸热管上的吸收与统计

当光子透过玻璃板后或经CPC反射后击中吸热管时，产生一个 $\xi$ 来判断光子是否被吸收，若<$a _ { \mathrm { t } }$ 则光子被吸收。接着将吸热管所吸收的光子统计在划分在管子上的 $N _ { \mathrm { c } }$ 个周向网格内。

# 2.2.6定义光学性能评价参数

经光线追击并统计光子在吸热管上的分布，可得到吸热管上的非均匀热流分布和系统光学效率等性能参数。为对系统光学性能进行评价，定义了吸热管周向热流不均匀性的系数 $\sigma _ { q } ^ { [ 1 1 ] }$ 、吸热管轴向热流的局部聚光比 LCR、系统瞬时光学效率 niop[4]、日均光学效率 $\eta _ { \mathrm { d o p t } }$ 和年均光学效率 $\eta _ { \mathrm { y o p t } } ^ { \left[ 9 \right] }$ ：

$$
\sigma _ { _ q } = \frac { \sum _ { k = 1 } ^ { N _ { \mathrm { c } } } \bigl | q _ { k } - q _ { \mathrm { a v e } } \bigr | } { N _ { \mathrm { c } } \cdot q _ { \mathrm { a v e } } } , \ q _ { \mathrm { a v e } } = \frac { \sum _ { k = 1 } ^ { N _ { \mathrm { c } } } q _ { k } } { N _ { \mathrm { c } } }
$$

$$
L C R = q _ { k } \mathrm { ~ / ~ } D N I
$$

$$
\eta _ { \mathrm { i o p t } } = Q _ { i j } / ( D N I _ { i j } \cdot L _ { \mathrm { m } } W _ { \mathrm { m } } n _ { \mathrm { m } } )
$$

$$
\eta _ { \mathrm { d o p t } } = \int _ { i = 7 . 5 } ^ { 1 6 . 5 } \sum _ { i = 8 } ^ { 1 6 } Q _ { i j } ~ / \int _ { i = 7 . 5 } ^ { 1 6 . 5 } \sum _ { i = 8 } ^ { 1 6 } ( D M _ { i j } \cdot L _ { \mathrm { m } } W _ { \mathrm { m } } n _ { \mathrm { m } } ) ~
$$

$$
\eta _ { \mathrm { y o p t } } = \frac { \sum _ { j = 1 } ^ { 3 6 5 } \int _ { i = 7 . 5 } ^ { 1 6 . 5 } \mathcal { Q } _ { i j } } { \sum _ { j = 1 } ^ { 3 6 5 } \int _ { i = 7 . 5 } ^ { 1 6 . 5 } ( D M _ { i j } \cdot L _ { \mathrm { m } } W _ { \mathrm { m } } n _ { \mathrm { m } } ) }
$$

式中， $q _ { k }$ 为吸热管周向第 $k$ 个网格的局部热流密度，$Q _ { i j }$ 和 $D N I _ { i j }$ 分别为第 $j$ 天 $i$ 时刻吸热管吸收涂层吸收的热量与直接辐射强度。

# 3模型准确性验证

本文采用Fortran编程，利用上述方法建立了系统三维光学模型。为验证方法与模型的准确性，采用与Chemisana等[12]类似的方式，与TracePro[13]软件和 SolTrace 软件[14]的模拟结果进行了比对。TracePro是一款应用广泛的商业软件，SolTrace是NREL开发的一款太阳能模拟软件，二者均可分析光学系统的瞬态性能。本文分别用二者验证无形面误差的复杂几何光学模型和形面误差模型。即先与TracePro对比研究了 $\scriptstyle \alpha = 9 0 ^ { \circ }$ 、反射镜为平面镜、东西侧反射镜所对应瞄准线分别为 $( x _ { \mathrm { g } } , - 0 . 1 5 , 1 0 )$ 和$( x _ { \mathrm { g } } , 0 . 1 5 , 1 0 )$ 时的吸热管所吸收辐射的 $L C R$ 分布，再在相同参数下与SolTrace 对比了 $\sigma _ { \mathrm { s e } } { = } 2 . 5$ mrad时玻璃板下表面入射辐射的 $L C R$ 分布，对比结果见图2。由图2可见，两种情况下的 $L C R$ 曲线均吻合得很好，验证了本文方法与模型的准确性。

![](images/fec3a3076629ea3213ebf6320bd13f5cb583d3aefe6fafdfa945b5ed9fc306fd.jpg)  
图2MCRT与TracePro及SolTrace 模拟结果对比 Fig.2 Comparisons of the results between MCRT and softwares (TracePro and SolTrace)

# 4结果与讨论

# 4.13种典型反射镜性能对比与优化

反射镜是系统聚光元件，其造价占系统成本一半以上，其几何参数直接影响系统性能。为研究反射镜几何参数对系统性能的影响，探讨降低系统成本的途径，本节将对使用平面镜、圆柱面镜和抛物面镜的系统进行对比研究。本文假设反射镜与CPC具有相同的形面误差 $\sigma _ { \mathrm { s e } }$ 。本节中瞄准线均为$( x _ { \mathrm { g } } , 0 , 1 0 )$ ， $\sigma _ { \mathrm { s e } } { = } 2 . 5$ mrad， $D N I { = } 1 0 0 0 \ \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 }$ 。

为对比3种反射镜的性能，首先对圆柱面镜半径 $( r )$ 和抛物面镜焦距 $( f )$ 进行了优化。图3为优化结果，其中系统位置在北回归线上，优化目标函数为$\eta _ { \mathrm { d o p t } }$ ，计算时间为夏至日 $7 { : } 3 0 { \sim } 1 6 { : } 3 0$ 。由图可见 $\eta _ { \mathrm { d o p t } }$ 先随 $r$ 或f迅速增大至最大值(即当 $r { = } 2 7 . 5 \mathrm { m }$ 或 $f { = } 1 4 \mathrm { m }$ 时)，然后逐渐减小，最终趋近于平面镜日均效率$5 2 . 5 2 \%$ 。分析可知，在 $r { = } 2 5 . 5 { \sim } 3 2 \mathrm { m }$ 或 $\mathrm { \ f = 1 2 . 7 { \sim } 1 5 . 7 m }$ 内，两种反射镜各自 $\eta _ { \mathrm { d o p t } }$ 变化不超过 $0 . 1 \%$ ，说明系统在该范围内对 $\boldsymbol { r }$ 或 $f$ 的变化不敏感，这将为系统的设计与制造带来便利。

图4给出了使用优化后的3种反射镜的系统吸热管上的热流分布，其中 $\scriptstyle \alpha = 9 0 ^ { \circ }$ 。可见优化后的抛物面镜与圆柱面镜的光学性能非常接近，以致二者在吸热管上的 $L C R$ 曲线几乎重合， $\eta _ { \mathrm { i o p t } }$ 相差也小于$0 . 1 \%$ 且比平面镜大 $9 . 8 \%$ 。经分析验证，其他瞄准方式下的模拟结果也有相同的特点。该结论证明了在LFR系统中使用优化后的圆柱面镜可以达到与抛物面镜相同的性能。由于圆柱面镜的加工相对容易，成本较低，因此可有效降低系统成本。后文研究中均使用圆柱面镜。

![](images/062ab6c5650069079cebd406fa7c4c43366a29d589f31c104d670bf5f6630c1f.jpg)  
图3抛物面焦距 $( f )$ 与圆柱面半径 $( r )$ 优化结果 Fig.3 Optimization results of $f$ and $r$

![](images/1e855bd3f04718451f18f2015d7bc4a1335f3715172607fdca98aea6c60ecf3b.jpg)  
图43种反射镜系统吸热管热流分布图

Fig.4 Comparison of the concentrated solar flux distributions on the absorber of systems with three typical mirrors

# 4.2反射镜瞄准线对光学性能的影响

由于在图4的瞄准方案下，圆柱面镜系统的最大 $L C R$ 为平面镜的2倍以上，这将增大吸收涂层失效的可能性。本节将在保证较高的光学效率的情况下，通过设计瞄准方案来实现更均匀的热流分布，其中 $\sigma _ { \mathrm { s e } }$ 为 $2 . 5 \mathrm { m r a d }$ ， $z _ { \mathrm { a i m } } { = } 9 . 8 0 5 ~ \mathrm { m }$ 。

首先，采用4.1节所述方法对表2所示的5种不同瞄准方案(西侧与东侧反射镜的瞄准线关于 $x _ { \mathrm { g } } z _ { \mathrm { g } }$ 面对称)下的反射镜半径进行了优化，结果见表2。

图5与图6是优化后的5种方案的光学性能对比结果。由图5可见，在保证较高的光学效率的前提下，可通过分散瞄准线来降低 $L C R$ 。对比还表明，方案4与5均具有较高的 $\eta _ { \mathrm { i o p t } } \left( 6 5 . 9 0 \% , \ 6 7 . 5 \% \right)$ 和较低的 $\sigma _ { q }$ 0 $3 6 . 5 0 \%$ ， $5 7 . 3 4 \%$ )。由图6可见，方案4最大 $L C R$ 比方案1降低了 $3 6 \%$ ，而吸热管上半部分获得了 $3 5 \%$ 的能量；方案5最大 $L C R$ 比方案1降低了$22 \%$ ，而吸热管上半部分获得了 $20 \%$ 的能量。为避免吸热管局部超温，同时保证较高的效率，LFR系统可在吸热管低温段采用方案5，高温段采用方案

4。后文的研究则以方案4为例进行。

表25种反射镜瞄准方案Table 2Five aim modes of the mirror  

<html><body><table><tr><td rowspan="2">方 案</td><td colspan="4">yaim/m</td><td rowspan="2">/m rm</td></tr><tr><td>M1~ M5</td><td>M6~ M10</td><td>M11~ M15</td><td>M16~ M21~ M20 M25</td></tr><tr><td>1 2</td><td></td><td></td><td>0.00 -0.05</td><td></td><td>27.5 27.5</td></tr><tr><td>3</td><td></td><td></td><td>0.006~ -0.15</td><td></td><td>32.5</td></tr><tr><td>4</td><td>0.15</td><td>0.10</td><td>-0.20</td><td>0.10 -0.15</td><td>29.0</td></tr><tr><td>5</td><td>0.11~ 0.15</td><td>0.11~ 0.15</td><td>0.09~ 0.05</td><td>-0.01~ 0.00 -0.05</td><td>28.5</td></tr></table></body></html>

![](images/022e2c43ca3a6ab72c75d38595fbb36910f583449bf917d354c09305c8b234a5.jpg)  
图55种方案效率与均匀性对比图

![](images/4a89fde0c27d126a7520f5de9eae993620e505d0e520b8812b0c9b43f0ecee43.jpg)  
Fig.5 Comparisons of the instantaneous efficiency and non-uniformity index data under five aim modes   
图65种方案吸热管热流分布对比图  
Fig.6 Comparison of the concentrated solar flux distributions on the absorber of five aim modes   
图 $9 \eta _ { \mathrm { d o p t } }$ 与 $\eta _ { \mathrm { y o p t } }$ 随纬度的变化规律  
Fig.9 The variations of $\eta _ { \mathrm { d o p t } }$ and $\eta _ { \mathrm { y o p t } }$ with latitude $\varphi$

# 4.3形面误差对光学性能的影响

图7与图8为不同形面误差 $\sigma _ { \mathrm { s e } }$ 下的系统瞬时光学性能对比结果，其中 $\scriptstyle \alpha = 9 0 ^ { \circ }$ 。由图7可见，随着 $\sigma _ { \mathrm { s e } }$ 的增大 $( 0 { \sim } 3 . 5 \ \mathrm { m r a d } )$ ， $\sigma _ { q }$ 逐渐减小，管壁热流均匀性提高，同时 $\eta _ { \mathrm { i o p t } }$ 也逐渐降低但降低幅度较小 $( 3 . 9 \% )$ 。结合图8可知，最大 $L C R$ 相对降低了 $20 \%$ 。可见使用具有一定 $\sigma _ { \mathrm { s e } }$ 的反射镜可以以较小的效率损失换来热流均匀性的较大提高。后文中 $\sigma _ { \mathrm { s e } }$ 均为 $2 . 5 \mathrm { m r a d }$ 。

![](images/79bfa6bd728e0651eaf81b1f114cf6015ce73d909512ce9c6c2d2ef4b3386723.jpg)  
图7形面误差对瞬时效率和热流均匀性的影响 Fig.7 Effects of slope error on instantaneous efficiency and non-uniformity index

![](images/f889cdcf62d2f9b7a8199b0b63c2f97b53fd625ad7a10e2109808252dedc7f88.jpg)  
图8形面误差对吸热管热流分布的影响  
Fig.8 Effect of slope error on the concentrated solar flux distributions on the absorber

# 4.4不同纬度的光学效率

图9为系统在不同纬度下的日均效率 $\eta _ { \mathrm { d o p t } }$ 与年均效率 $\eta _ { \mathrm { y o p t } }$ 的对比结果。

65 60 55 50   
% 4540353025 b   
/dopu p nyopt 4 nyopt d e a. 10,54.9 13,4521 f 2015 bc d 15,51.71 ni 45, 49.59 gh 25,49.88 50,37.39 10 e 30, 47.69 5 0 40 80 120160 200240280 320360 日序数 $N _ { \mathbf { d a y } }$

由图9可见 $\eta _ { \mathrm { d o p t } }$ 随日序数 $N _ { \mathrm { d a y } }$ 和纬度 $\varphi$ 的变化情况，系统在不同 $\varphi$ 时的 $\eta _ { \mathrm { d o p t } }$ 曲线均随日序呈钟形曲线变化，在北半球北回归线以南的系统的 $\eta _ { \mathrm { d o p t } }$ 曲线均存在两个峰值，而北回归线以北的系统均只有一个峰值且在夏至日。同时，随着φ的增大，nyopt逐渐减小。在 ${ \bf N } 2 0 ^ { \circ } { \sim } { \bf N } 5 0 ^ { \circ }$ 的范围内，该线性菲涅尔系统的 $\eta _ { \mathrm { y o p t } }$ 变化范围为 $5 2 \% { \sim } 3 7 \%$ 。可见该系统具有较高的光学效率，可在我国大部分地区应用。

5结论为研究与优化线性菲涅尔系统的光学性能，本  
文采用蒙特卡罗光线追迹法，建立了系统三维光学  
模型，运用FORTRAN编程实现了该算法，并基于  
此进行了一系列分析与优化研究。具体结论如下：(1)经过优化的圆柱面镜可以达到与抛物面镜  
几乎一样的光学性能，以致二者在吸热管上的辐射  
分布曲线几乎重合。该结论可为在LFR系统中用相  
对廉价的圆柱面镜替代抛物面镜提供依据，有望降  
低系统成本。(2)可通过优化反射镜瞄准线，牺牲少量效率来  
提高吸热管热流均匀性，对此本文给出了两种设计  
方案。同时可见，圆柱面反射镜半径存在一个稳定  
的高效率区间，在该区间内效率对半径的变化不敏  
感，该结论可减小系统设计和优化的难度。(3)吸热管热流均匀性随镜面形面误差 $\sigma _ { \mathrm { s e } }$ 的增  
大而提高，选用具有一定 $\sigma _ { \mathrm { s e } }$ 的反射镜既可提高热流  
均匀性又可降低制造成本。(4)在北纬 $2 0 ^ { \circ } { \sim } 5 0 ^ { \circ }$ 的范围内，该系统具有较高  
的年效率 $( 5 2 \% { \sim } 3 7 \% )$ ，可在在我国大部分地区应用。

# 参考文献

[1]Häberle A，Zahler C,Lerchenmüller H,et al． The Solarmundo line focussing Fresnel collector. Optical and thermal performance and cost calculations[C]. Proceedings of the 2002 SolarPACES International Symposium. 2002.   
[2]杜春旭,王普,马重芳,等.线性菲涅耳聚光系统无遮挡镜 场布置的光学几何方法[J]光学学 报，2010,11:3276--3282. DU Chunxu,WANG Pu,MA Chongfang,et al. Optical Geometric Method for LFR Mirror Field Arrangement Without Shading and B locking[J]. Acta Optica Sinica, 2010,11:3276-3282.   
[3]Abbas R,Montes MJ,Piera M,et al.Solar radiation concentration features in Linear Fresnel Reflector arrays[J] Energy Conversion and Management， 2012， 54(1): 133-144.   
[4]Grena R, Tarquini P. Solar linear Fresnel collector using molten nitrates as heat transfer fluid[J]. Energy, 2011, 36(2): 1048-1056.   
[5] He Y L, Xiao J,Cheng Z D, et al. A MCRT and FVM coupled simulation method for energy conversion process in parabolic trough solar collector[J]. Renewable Energy, 2011,36(3): 976-985.   
[6] Qiu Y, He Y L, Cheng Z D, et al. Study on optical and thermal performance of a linear Fresnel solar reflector using molten salt as HTF with MCRT and FVM methods[J].Applied Energy,2015,146: 162-173.   
[7]Cheng Z D,He Y L,Xiao J,et al. Three-dimensional numerical study of heat transfer characteristics in the receiver tube of parabolic trough solar collctor[J]. International Communications in Heat and Mass Transfer, 2010,37(7): 782-787.   
[8] Oommen R, Jayaraman S. Development and performance analysis of compound parabolic solar concentrators with reducedgaplosses-oversizedreflector[J].Energy Conversion and Management,2001, 42(11): 1379-1399.   
[9] He Y L, Cui F Q, Cheng Z D,et al. Numerical simulation of solar radiation transmission process for the solar tower power plant: From the heliostat field to the pressurized volumetric receiver[J].Applied Thermal Enginering, 2013,61(2): 583-595.   
[10] Shuai Y, Xia XL, Tan HP. Radiation performance of dish solar concentrator/cavity receiver systems[J]. Solar Energy, 2008,82(1): 13-21.   
[11] Cheng Z D,He Y L,Cui F Q,et al. Comparative and sensitive analysis for parabolic trough solar collectors with a detailed MCRT ray-tracing optical model[J]. Applied Energy, 2014,115: 559-572.   
[12] Chemisana D，Barrau J，Rosell JI,et al.Optical performance of solar reflective concentrators: A simple method for optical assessment[J]. Renewable Energy, 2013, 57: 120-129.   
[13] TracePro user's manual release 5.O.Lambda Research Corporation, 2009   
[14] Wendelin T,Dobos A，Lewandowski A. SolTrace:a ray-tracing code for complex optical systems[R]. Denver West Parkway Golden， Colorado: National Renewable Energy Laboratory,2013: 1-14