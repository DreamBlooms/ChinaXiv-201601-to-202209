# 复合方腔顶盖驱动双扩散混合对流格子Boltzmann 模拟

陆威王婷婷 徐洪涛 陈建杨茉(上海理工大学能源与动力工程学院，上海 200093)

摘要为本文基于热质耦合的 Lattice Bhatnagar-Gross-Krook(CLBGK）模型，通过引入浓度分布函数，利用格子Boltzmann 方法对顶盖驱动的复合方腔内的双扩散混合对流现象进行了研究，复合方腔由多孔介质区域和自由空间组成。分析了路易斯数 $L e { = } 2 . 0$ ，浮升力比 ${ N = } 1 . 0$ ，格拉晓夫数 $G r { = } 1 0 ^ { 4 }$ 和普朗特数 ${ P r } { = } 0 . 7$ 时，孔隙率 $\mathit { \Omega } ^ { \prime } \varepsilon = 0 . 6 / 0 . 7 / 0 . 8 )$ 、方腔中多孔介质层位置及理查德森数 $R i ( 1 0 ^ { - 3 } \leqslant R i \leqslant 1 0 ^ { 3 } )$ 对内部混合对流及热质扩散的影响。给出了方腔内温度、浓度和流线分布，以及高温高浓度壁面的平均努塞尔数 $N u _ { \mathrm { a v } }$ 和平均舍伍德数 $S h _ { \mathrm { a v } }$ 。研究结果表明：多孔介质层对顶盖驱动方腔内热质双扩散影响显著，且方腔左壁壁面平均努塞尔数 $N u _ { \mathrm { a v } }$ 与平均舍伍德数 $S h _ { \mathrm { a v } }$ ，在位置 $D _ { 1 } { \sim } D _ { 3 }$ 之间随多孔介质层的右移而增大，在位置 $D _ { 3 }$ 上随 $R i ( 1 0 ^ { - 3 } \leqslant R i \leqslant 1 0 ^ { 3 } )$ 的增大而减小。

关键词复合方腔；顶盖驱动；双扩散；格子Boltzmann 模拟中图分类号：TK124 文献标识码：A 文章编号:0253-231X(2017)03-0640-08

# Lattice Boltzmann Simulation of Double Diffusive Mixed Convection in a Lid-Driven Composite Enclosure

LU WeiWANG Ting-TingXU Hong-TaoCHEN JianYANG Mo SchoolofEnergyandPower Enginering,UniversityofShanghaifor Scienceand Technology，Shanghai 20093,China

Abstract Based on the coupled lattice Bhatnagar-Gross-Krook (CLBGK) model, this article adopts latice Boltzmann method and introduces concentration distribution function to investigate the double difusive mixed convection in a lid-driven composite enclosure,which is composed of the space filled with porous medium and free space of pure fluid. At Le=2.0, $N { = } 1 . 0$ ， $G r { = } 1 0 ^ { 4 }$ ， $P r$ =0.7, the influence of porosity ( $\varepsilon = 0 . 6 / 0 . 7 / 0 . 8 )$ ，porous medium layer locations $D _ { x }$ and Richardson number $R i ( 1 0 ^ { - 3 } \leqslant$ $R i \leqslant 1 0 ^ { 3 }$ ) on the double diffusive heat and mass transfer is performed. Results are presented in terms of isotherms, isoconcentrations, streamlines and the average Nusselt and Sherwood numbers along the left high temperature and concentration wall. Results show that the porosity and locations of porous medium have a significant influence on the doublediffusiveheat and mass in the lid-driven enclosure. The average Nusselt and Sherwood numbers along the left wall increase with the moving right of porous medium layer from $D _ { 1 }$ to $D _ { 3 }$ and decrease with the increasing of $R i$ from $1 0 ^ { - 3 }$ to $1 0 ^ { 3 }$ ： Key wordscomposite enclosure; lid-driven; double diffusion; lattice boltzmann simulation

# 0引言

多孔介质与纯流体空间组合成的复合区域中的热质双扩散现象是自然界和工农业生产中普遍存在的一种现象，如室内有机挥发性化合物（VOCs）的扩散问题、土壤中的污染传播问题、农业生产中的干燥问题，化工食品加工中的脱水及晶体生长问题等。因此，对复合区域内的热质双扩散现象的研究具有十分重要的意义。

学者们对复合方腔内的传热与热质双扩散现象进行了广泛研究。如流体为达西流或非达西流时，多孔介质层的物性参数（如：孔隙率、渗透率、多孔介质层的厚度等)，无量纲特性参数 (如：浮升力比 $N$ 、瑞丽数Ra、路易斯数Le、格拉晓夫数 $G r$ 等)对复合方腔内的自然对流与热质扩散影响的研究[1-6]。也研究了复合方腔内多孔介质层与纯流体空间交界面上的应力跳跃系数对方腔内自然对流与热质扩散的影响[7,8]。对比研究了二维与三维复合方腔模型内自然对流和热质扩散现象[9-11]等。以上对自然对流现象的研究工作均基于表征体元(RepresentativeElementaryVolume,REV）尺度，采用有限体积或者有限元等传统方法进行的。

与传统的模拟方法不同，被称为介观方法的格子Boltzmann方法因其计算效率较高、编程容易、边界条件处理简单等优点，被广泛应用于微尺度流动与换热、多孔介质、晶体生长等一些传统方法难以胜任的领域。如张国庆等[12]采用格子Boltzmann 方法在孔隙尺度下对放有多孔介质块的通道内的流动进行了模拟，研究了不同多孔介质模型及雷诺数Re对复合通道内流动的影响。Kang等[13-16]采用格子Boltzmann方法搭建LB模型，对孔隙尺度下多孔介质输运过程中的多组分反应及溶质溶解过程进行了研究等。

由于多孔介质复杂物理边界的无规则性，学者的研究工作主要集中在REV尺度自然对流的研究上，对孔隙尺度下双扩散混合对流的研究较少。因此，本文利用格子Boltzmann方法，研究孔隙尺度下复合方腔内多孔介质孔隙率 $\varepsilon$ 分别为0.6，0.7和0.8时，不同位置多孔介质对顶盖驱动的复合方腔内的混合对流与热质扩散的影响，为孔隙尺度下多孔介质内的热质交换的进一步研究提供一定参考。

速度水平向右移动。方腔内多孔介质层宽为 $D$ ，且$D / L { = } 1 / 4$ 。通过改变多孔介质层与左侧壁面间的距离 $D _ { \mathrm { x } }$ ，在多孔介质层孔隙率 $\varepsilon$ 分别为0.6，0.7和0.8时，探讨顶盖驱动的复合方腔内部双扩散混合对流特性。

采用Wang等[17,18]提出的四参数生成法（Quar-tet StructureGeneration Set，QSGS）构造孔隙尺度多孔介质层，四参数分别为生长核分布率 $P _ { \mathrm { c } }$ ，方向生长率 $P _ { \mathrm { g } }$ ，相交互生长率 $P _ { i }$ 和固相相含率 $P _ { \mathrm { { v } } }$ ，本文构造的多孔介质平均孔隙率 $\varepsilon { = } 0 . 6 / 0 . 7 / 0 . 8 .$ ，平均固体颗粒直径 $D _ { \mathrm { d } } { = } 1 8 . 0$ ，平均颗粒直径 $D _ { \mathrm { d } } = 6 / S _ { \mathrm { v } }$ ， $S _ { \mathrm { v } }$ 为多孔介质固体颗粒的比表面积， $S _ { \mathrm { v } } = M / A$ ， $M$ 和$A$ 分别为二维多孔介质固体颗粒的边界总周长和面积[19]，所构造的多孔介质层如图2所示。

![](images/195577a2a8a8d3ce8a7a7c0af902b2b9108b3fd78ce845a8713ebede16a8a1a8.jpg)  
图2多孔介质层模型 Fig.2 Models of Porous Medium layer

![](images/f4e0527d339c898075c506d19afa6346235a69304a52f852e6f0b141576a07ed.jpg)  
图1物理模型Fig.1 PhysicalModel

通过改变多孔介质层与左侧壁面的距离，研究多孔介质层位置对复合方腔内热质双扩散的影响，方腔网格尺寸为 $8 0 0 \times 4 0 0$ ，多孔介质层网格尺寸为$8 0 0 \times 1 0 0$ ，所选5组模型中多孔介质层与高温高浓度边界间间隔的网格步长如表1所示，因本文多孔介质固体颗粒边界为绝热不可渗透边界，为避免多孔介质层对高温高浓度与低温低浓度边界的有效换热面积的影响，在模型 $D _ { 1 }$ 与 $D _ { 5 }$ 中多孔介质层与左右壁面间留有5个步长的间隙。

# 1 物理与数学模型

本文研究的物理模型如图1所示。复合方腔长宽比 ${ H } / { L } \mathrm { { = } } 2 . 0$ ，方腔左壁为高温高浓度边界，右壁为低温低浓度边界，上下壁面与多孔介质固体颗粒边界均为绝热不可渗透边界，顶盖以 $U { = } 1 . 0$ 的恒定晓夫数 $G r$ ，普朗特数 $P r$ ，理查德森数 $R i$ ，路易斯数 $L e$ 及浮升力比 $N$ 定义如下

表1多孔介质层在方腔中的位置  
Table 1 Locations of Porous Medium Layer in Cavity   

<html><body><table><tr><td>Dx</td><td>D1</td><td>D2</td><td>D3</td><td>D4</td><td>D5</td></tr><tr><td>步长/lu</td><td>5</td><td>100</td><td>150</td><td>200</td><td>295</td></tr></table></body></html>

模型涉及的无量纲特征参数：雷诺数 $R e$ ，格拉

$$
R e = \frac { u _ { i } t } { v } , G r = \frac { g \beta _ { \mathrm { T } } ( T _ { \mathrm { h } } - T _ { \mathrm { c } } ) L _ { c } ^ { 3 } } { v ^ { 2 } } , P r = \frac { v } { \alpha }
$$

$$
R i = \frac { \mathrm { G r } } { R e ^ { 2 } } , L e = \frac { \alpha } { \beta } , N = \frac { \beta _ { \mathrm { C } } ( C _ { \mathrm { h } } - C _ { \mathrm { c } } ) } { \beta _ { T } ( T _ { \mathrm { h } } - T _ { \mathrm { c } } ) }
$$

本文模拟时普朗特数 $P r$ 取定值0.7，格拉晓夫数 $G r$ 取 $1 . 0 \times 1 0 ^ { 4 }$ ，路易斯数 $L e { = } 2 . 0$ ，浮升力比$N { = } 1 . 0$ 。复合方腔边界条件设定如下

左壁： $U = V = 0 . 0 , \theta = S = 1 . 0$

右壁： $U = V = 0 . 0 , \theta = S = 0 . 0$

顶板： $U = 1 . 0 , V = 0 . 0 , \partial \theta / \partial Y = \partial S / \partial Y = 0 . 0$

底板： $U = V = 0 . 0 , \partial \theta / \partial Y = \partial S / \partial Y = 0 . 0$

多孔介质固体边界： $\partial \theta / \partial n = \partial S / \partial n = 0 . 0$ ， $\scriptstyle { n }$ 表示固体边界表面的外法向。

# 2热质耦合双扩散 Boltzmann 模型

本文在Guo 等[20]提出的CLBGK 模型的基础上引入了浓度分布函数，构造用于模拟方腔内双扩散混合对流的热质耦合的LBGK模型，其密度分布函数的演化方程为

$$
\begin{array} { r l r } {  { f _ { i } ( { \pmb x } + { \pmb e } _ { i } \delta _ { t } , t + \delta _ { t } ) - f _ { i } ( { \pmb x } , t ) = } } \\ & { - ( f _ { i } ( { \pmb x } , t ) - f _ { i } ^ { \mathrm { e q } } ( { \pmb x } , t ) ) / \tau _ { f } + \delta _ { t } { \pmb F } _ { i } } \end{array}
$$

式中， $\boldsymbol { e } _ { i }$ 为离散速度，速度场、温度场及浓度场时离散速度模型均采用D2Q9 模型[21]，无量纲松弛时间 $\tau _ { \mathrm { f } }$ 与运动黏度 $\mathbf { \sigma } _ { v }$ 满足关系 $\upsilon = c _ { \mathrm { s } } ^ { 2 } ( \tau _ { \mathrm { f } } - 1 / 2 ) \delta _ { \mathrm { t } }$ 。平衡态密度分布函数 $f _ { i } ^ { \mathrm { e q } } \left( \pmb { x } , t \right)$ 表达式为

$$
f _ { i } ^ { \mathrm { e q } } \left( { \pmb x } , t \right) = \left\{ \begin{array} { c c } { \rho _ { 0 } - 5 P / 3 c ^ { 2 } + \rho _ { 0 } s _ { i } ( { \pmb u } ) } & { i = 0 } \\ { P / 3 c ^ { 2 } + \rho _ { 0 } s _ { i } ( { \pmb u } ) } & { i = 1 , 2 , 3 , 4 } \\ { P / 1 2 c ^ { 2 } + \rho _ { 0 } s _ { i } ( { \pmb u } ) } & { i = 5 , 6 , 7 , 8 } \end{array} \right.
$$

$$
s _ { i } ( u ) = \omega _ { i } [ 3 e _ { i } u / c + 4 . 5 ( e _ { i } u ) ^ { 2 } / c ^ { 2 } - 1 . 5 u ^ { 2 } / c ^ { 2 } ]
$$

式中，权系数 $\omega _ { 0 } = 4 / 9$ ， $\omega _ { 1 - 4 } = 1 / 9$ ， $\omega _ { 5 - 8 } = 1 / 3 6$ 。演化方程中外力项 $\pmb { F } _ { i }$ 表达式为

$$
\begin{array} { c } { { { \pmb F } _ { i } = \left( 1 - 1 / 2 \tau _ { \mathrm { f } } \right) \omega _ { i } [ 3 \left( c e _ { i } - { \pmb u } \right) / c ^ { 2 } } } \\ { { + \left. 9 \left( { { \pmb e } _ { i } \cdot \pmb u } \right) { \pmb e } _ { i } / c ^ { 2 } \right] \cdot { \pmb F } } } \end{array}
$$

假设方腔内流体为不可压牛顿流体，忽略黏性耗散，为便于处理由于温差和浓度差而引起的浮升力项，采用 Boussinessq 假设[22]，浮升力 ${ \textbf { } } ^ { F } = { }$ ${ \pmb g } \beta _ { \mathrm { T } } ( T - T _ { 0 } ) + { \pmb g } \beta _ { \mathrm { C } } ( C - C _ { 0 } )$ ， $g$ 为重力加速度，热膨胀系数 $\beta _ { \mathrm { T } } ~ = ~ - \left( \partial \rho / \partial T \right) / \rho _ { 0 }$ ，质膨胀系数 $\beta _ { \mathrm { C } } =$ $- \left( \partial \rho / \partial C \right) / \rho _ { 0 }$ 。流场宏观速度与压力定义为

$$
\pmb { u } = \sum _ { i = 1 } ^ { 8 } c e _ { i } f _ { i } , \quad P = \frac { 5 } { 3 } c ^ { 2 } \left[ \sum _ { i = 1 } ^ { 8 } f _ { i } + s _ { 0 } ( \pmb { u } ) \right]
$$

温度分布函数与浓度分布函数的演化方程为

$$
\begin{array} { r l r } {  { g _ { i } ( { \pmb x } + { \pmb e } _ { i } \delta _ { \mathrm { t } } , t + \delta _ { \mathrm { t } } ) - g _ { i } ( { \pmb x } , t ) = } } \\ & { } & { - ( g _ { i } ( { \pmb x } , t ) - g _ { i } ^ { \mathrm { e q } } ( { \pmb x } , t ) ) / \tau _ { \mathrm { t } } } \end{array}
$$

$$
\begin{array} { r l r } & { } & { h _ { i } ( { \pmb x } + { \pmb e } _ { i } \delta _ { t } , t + \delta _ { \mathrm { t } } ) - h _ { i } \left( { \pmb x } , t \right) = } \\ & { } & { - \left( h _ { i } \left( { \pmb x } , t \right) - h _ { i } ^ { \mathrm { e q } } \left( { \pmb x } , t \right) \right) / \tau _ { \mathrm { c } } \quad } \end{array}
$$

式中，无量纲松弛时间 $\tau _ { \mathrm { t } } , \tau _ { \mathrm { c } }$ 与热扩散系数 $\alpha$ 、质扩散系数 $\beta$ 满足关系

$$
\alpha = \frac { 1 } { 2 } \left( \tau _ { \mathrm { t } } - \frac { 1 } { 2 } \right) c ^ { 2 } \delta _ { \mathrm { t } } , \beta = \frac { 1 } { 2 } \left( \tau _ { \mathrm { c } } - \frac { 1 } { 2 } \right) c ^ { 2 } \delta _ { \mathrm { t } }
$$

温度与浓度的平衡态分布函数定义为

$$
\begin{array} { c } { { g _ { i } ^ { \mathrm { e q } } \left( { \bf x } , t \right) = \omega _ { i } T \left[ 1 + \displaystyle \frac { 3 e _ { i } \cdot u } { c } + \right. } } \\ { { \left. 4 . 5 \displaystyle \frac { \left( e _ { i } \cdot u \right) ^ { 2 } } { c ^ { 2 } } - 1 . 5 \displaystyle \frac { u ^ { 2 } } { c ^ { 2 } } \right] } } \end{array}
$$

$$
h _ { i } ^ { \mathrm { e q } } \left( \mathbf { x } , t \right) = \omega _ { i } C \left[ 1 - 3 \boldsymbol { e } _ { i } \cdot \boldsymbol { \mathbf { u } } / c \right]
$$

宏观温度与宏观浓度定义为

$$
T = \sum _ { i = 1 } ^ { 8 } g _ { i } , \quad C = \sum _ { i = 1 } ^ { 8 } h _ { i }
$$

高温高浓度壁面平均努塞尔数 $N u _ { \mathrm { a v } }$ 与平均舍伍德数 $S h _ { \mathrm { a v } }$ 计算式为

$$
\begin{array} { l } { { \displaystyle N u _ { \mathrm { a v } } = - \frac { 1 } { H } \int _ { 0 } ^ { H } \left( \frac { \partial \theta } { \partial X } \right) _ { X = 0 } \mathrm { d } Y } } \\ { { \displaystyle S h _ { \mathrm { a v } } = - \frac { 1 } { H } \int _ { 0 } ^ { H } \left( \frac { \partial C } { \partial X } \right) _ { X = 0 } \mathrm { d } Y } } \end{array}
$$

方腔四周壁面边界处理采用Guo等[23]提出的具有二阶精度的非平衡外推格式，多孔介质固体颗粒边界采用反弹格式[24]，流场初始密度 $\rho _ { 0 } = 1 . 0$ 。

# 3程序验证

本文多孔介质固体颗粒边界为绝热不可渗透边界，与方腔内纯流体空间双扩散的区别仅在于边界的不同。为对程序进行验证，本文采用热质耦合的LBGK模型模拟了二维方腔内纯流体空间的双扩散混合对流，计算了路易斯数 $L e { = } 1 . 0$ ，浮升力比$N { = } 1 . 0$ ，格拉晓夫数 $G r { = } 1 0 ^ { 4 }$ 时方腔内浓度、温度分布图，高温高浓度壁面的平均努塞尔数 $N u _ { \mathrm { a v } }$ 及平均舍伍德数 $S h _ { \mathrm { a v } }$ 的值，并与参考文献[25]所得结论进行了对比。等温线、流线及等浓度线分布对比如图3所示，高温高浓度壁面平均努塞尔数 $N u _ { \mathrm { a v } }$ 及平均舍伍德数 $S h _ { \mathrm { a v } }$ 的对比结果如图4所示。从图4中可以看出本文结论与参考文献[25]采用有限体积法模拟计算所得结论吻合较好，验证了本文采用的模型程序的准确性。

![](images/7ebc43dc67388c085166fda5fa9abde874c99039eccdf2d2ef252d0cfbedfaf5.jpg)  
Fig.3 Comparison contours of isotherm,streamline and isoconcentration between this article (up）and Ref.[25] (down)

![](images/2975d814bc774e45c9a08c6b5de12676c12765e529ab7ca117f169fbf9e228a0.jpg)  
图4左壁壁面 $N u _ { \mathrm { a v } }$ (上)和 $S h _ { \mathrm { a v } }$ (下)随 $R i$ 的变化对比图$( L e { = } 1 . 0 , N { = } 1 . 0 )$ 门  
Fig.4 Comparison diagrams of $N u _ { \mathrm { a v } } ( \mathrm { u p } )$ and $S h _ { \mathrm { a v } }$ (down） atthe left wall changes with $R i ( L e { = } 1 . 0$ ， ${ N = } 1 . 0$ ）

# 4计算结果与分析

# 4.1不同结构参数下方腔内热质扩散分布特性

图5(a)所示为孔隙率 $\varepsilon { = } 0 . 6 / 0 . 7 / 0 . 8$ ，不同多孔介质层位置下，方腔内热质扩散及流线分布图。从图5(a）中的流线分布可以看出，自由空间靠近顶盖位置形成明显的涡流，多孔介质层阻力较大，流体不易穿透。随着多孔介质层位置右移，左侧自由空间内流体的自然对流强度因浮升力作用逐渐增强，顶盖驱动引起的局部涡流强度左侧部分逐渐增大，在多孔介质层右移至位置 $D _ { 2 }$ 时，涡流区域相应演变为上下两个；而方腔右侧部分涡流逐渐减小，在多孔介质层右移至位置 $D _ { 3 }$ 时中部出现涡流，由于右侧自由空间内流体对流换热强度随多孔介质层的右移逐渐减弱，右侧涡流逐渐消失。

图5(b)所示为孔隙率分别为0.7和0.8, $D _ { 3 }$ 位置温度、浓度及流线分布图。对比图5(a)、(b)中的流线分布可以发现，孔隙率 $\varepsilon { = } 0 . 7$ 和 $\varepsilon { = } 0 . 8$ ，多孔介质层处于位置 $D _ { 3 }$ 时，方腔内流线分布与 $\varepsilon { = } 0 . 6$ （图5(a))时相似。且随着孔隙率 $\boldsymbol { \varepsilon }$ 的增大，多孔介质层内渗流强度因流动阻力的减小而增强，孔隙率 $\varepsilon { = } 0 . 6$ 时位置 $D _ { 3 }$ 中左侧中部出现的涡流与位置 $D _ { 5 }$ 中右侧中部出现的涡流强度随孔隙率的增大而逐渐增强，且因渗流强度的增强，与另一侧流体呈逐渐融合趋势。

从图5(a）中的温度与浓度分布云图可以看出，多孔介质层对复合方腔内的温度与浓度分布影响显著，由于流动阻力的存在，多孔介质层内对流强度比自由空间弱很多，很大程度上限制了方腔内的热质交换，使得复合方腔内，仅在左侧高温高浓度与右侧低温低浓度壁面附近存在较为明显的温度梯度，而在方腔中部温度与浓度分布较为均匀。且当多孔介质层靠近高温高浓度壁面位置(位置 $D _ { 1 } , D _ { 2 } )$ 时,左壁壁面附近由于对流强度较弱，传热传质主要以扩散为主，混合对流速度场对温度与浓度分布的影响较小，壁面上下温度与浓度梯度近似呈均匀分布；随着多孔介质层的右移，方腔左侧混合对流强度逐渐增强，对传热传质的影响逐渐占据主导地位，使得左壁壁面顶板附近局部温度与浓度分布趋于均匀。对比图5(a)、(b)可以发现，当多孔介质层位置不变时，方腔内混合对流强度因孔隙率的增大而增强，多孔介质层对方腔内温度与浓度分布的影响逐渐减弱。

![](images/8b0e089f10388a61f511863b29756f2a8c0b50c4238fe13b6d726ce607a6aee7.jpg)  
图5(a）多孔介质位置 $D _ { x }$ 不同时方腔内温度(上)、浓度(下)与流线分布图（ $\overset { \cdot } { \varepsilon } = 0 . 6$ ）

![](images/fe4a5a370ef656199779fdce8045fc051727c66b7ec8db978d6944e182b895d9.jpg)  
g.5(a)Contours of isotherm(up)and isoconcentration(down)and streamline in cavity with diferent locations $D _ { x } ( \varepsilon = 0 . 6 \$   
图5(b） $D _ { 3 }$ 位置下孔隙率 $\varepsilon { = } 0 . 7$ 和 $\varepsilon { = } 0 . 8$ 时方腔内温度 (左)、浓度 (右)与流线分布图 ）Contours of isotherm(left) and isoconcentration(right)and streamline in cavity with location $D _ { 3 }$ at $_ { ; \varepsilon = 0 . 7 }$ and $\varepsilon { = } 0 . 8$ （20

# 4.2不同结构参数下高温高浓度壁面热质交换特性

图6所示为不同孔隙率时，顶盖驱动方腔内多孔介质层不同位置对左侧高温高浓度壁面平均努塞尔数 $N u _ { \mathrm { a v } }$ 和平均舍伍德数 $S h _ { \mathrm { a v } }$ 的影响曲线图。从图中可以看出，在位置 $D _ { 1 } { \sim } D _ { 3 }$ 之间，当多孔介质层孔隙率 $\mathbf { \varepsilon } _ { \varepsilon }$ 不变时，随着多孔介质层的右移，方腔左侧自由空间内混合对流强度逐渐增强，强化了左壁壁面的热质交换效率，使得方腔左壁壁面 $N u _ { \mathrm { a v } }$ 和$S h _ { \mathrm { a v } }$ 随多孔介质层的右移而增大，且孔隙率 $\varepsilon$ 越小，增幅越明显。在位置 $D _ { 3 } { \sim } D _ { 5 }$ 之间，多孔介质层的存在对方腔左侧混合对流强度的影响减弱，使得多孔介质层的位置 $D _ { x }$ 及孔隙率 $\varepsilon$ 对 $N u _ { \mathrm { a v } }$ 和 $S h _ { \mathrm { a v } }$ 的影响不明显。仅当处于位置 $D _ { 1 }$ 时，多孔介质层内的渗流强度因孔隙率 $\boldsymbol { \varepsilon }$ 的增大而增强，强化了方腔内的热质交换，使得左壁壁面 $N u _ { \mathrm { a v } }$ 和 $S h _ { \mathrm { a v } }$ 显著增大。

# 4.3理查德森数 $\mathbf { \nabla } R i$ 的影响

理查德森数 $R i$ 是衡量混合对流中强制对流与自然对流相对强弱的关键因素，为探究 $R i$ 对复合方腔壁面对流传热传质特性的影响，本文对不同

$R i ( 1 0 ^ { - 3 } ~ \leqslant R i \leqslant 1 0 ^ { 3 } )$ 下，多孔介质层处于位置 $D _ { 3 }$ 时，复合方腔内的对流传热传质进行了模拟。如图7所示为孔隙率 $\varepsilon { = } 0 . 6$ 不同 $R i$ 下方腔内的流线分布图。

从图中可以看出， $R i$ 对复合方腔内流场分布的影响显著，当方腔内为自然对流（ $( R i < 1 0 ^ { - 1 } )$ 时，复合方腔内流线分布较为复杂，受顶板影响，多孔介质层左右两侧顶板附近均存在顺时针方向涡流，而在右侧中部局部出现逆时针方向涡流；当流体处于混合对流流态 $( 1 0 ^ { - 1 } \leqslant R i \leqslant 1 0 )$ 时，局部涡流处于顶板附近，逆时针方向涡流消失；当流体处于强制对流流态 $( R i > 1 0 )$ 时，方腔两侧流线分布，两侧涡流中心分别处于方腔两侧中部且涡流占据整个自由空间。显然，随着 $R i$ 的增大，多孔介质层内渗流强度明显减弱，流体在多孔介质层两侧分别形成涡流，在这很大程度上限制了方腔左右两侧流体间的热质交换，从而影响壁面对流传热传质效率。如图8所示，不同孔隙率下方腔左壁壁面 $N u _ { \mathrm { a v } }$ 和 $S h _ { \mathrm { a v } }$ 随 $R i$ 变化曲线图能直观反映这一点。方腔左壁壁面 $N u _ { \mathrm { a v } }$ 和$S h _ { \mathrm { a v } }$ 随 $R i$ 的增大逐渐减小。

![](images/ceac92bf7cf65bddc15575dad41ea75778c62311878f9823c78809983237c027.jpg)  
图6不同孔隙率下 $N u _ { \mathrm { a v } }$ (a)和 $S h _ { \mathrm { a v } }$ (b）随多孔介质层位置变化关系图Fig.6 $N u _ { \mathrm { a v } }$ (a)and $S h _ { \mathrm { a v } }$ (b)of the left wall changes with porous medium layer locations at different porosity

![](images/04390703fd9dd3a471512a2aa00e84eb821a89e9fa5f44a0675ca056c4cc2231.jpg)  
图7 $D _ { 3 }$ 位置不同 $R i ( 1 0 ^ { - 3 } \leqslant R i \leqslant 1 0 ^ { 3 } )$ 下复合方腔内流线分布 $\scriptstyle ( \varepsilon = 0 . 6 )$

![](images/704eb525550820e7ec026c58a315f418d6a34fed7d9cc8acf4ef7fe137549796.jpg)  
图8位置 $D _ { 3 }$ 下左壁壁面 ${ N u } _ { \mathrm { a v } } ( \mathrm { a } )$ 和 $S h _ { \mathrm { a v } } ( \mathrm { b } )$ 随理查德森数$R i$ 变化关系图Fig.8 $N u _ { \mathrm { a v } }$ (a)and $S h _ { \mathrm { a v } } ( \mathrm { b } )$ of the left wall changes withRichardson number $R i$ at different porosity

3)不同位置下，孔隙率对高温高浓度壁面 $N u _ { \mathrm { a v } }$ 和 $S h _ { \mathrm { a v } }$ 影响不具统一规律性。4）当多孔介质层处于位置 $D _ { 3 }$ 时，高温高浓度壁面 $N u _ { \mathrm { a v } }$ 和 $S h _ { \mathrm { a v } }$ 随 $R i$ 的增大而减小。

# 参考文献

[1]Goyeau B,Gobin D.Heat Transfer by Thermosolutal Natural Convection in a Vertical Composite Fluid-porous Cavity [J]. International Communications in Heat and Mass Transfer,1999, 26(8):1115-1126   
[2] Mharzi M, Daguenet M,Daoudi S.Thermosolutal Natural Convection in a Vertically Layered Fluid-Porous Medium Heated From the Side [J]. Energy Conversion and Management,2000,41(10):1065-1090   
[3] Bennacer R, Beji H, Mohamad A A. Double Diffusive Convection in a Vertical Enclosure Inserted With two Saturated Porous Layers Confining a Fluid Layer [J]. International Journal of Thermal Sciences,2003,42(2):141-151   
[4] Gobin D,Goyeau B,Neculae A. Convective Heat and Solute Transfer in Partially Porous Cavities [J].International Journal of Heat and Mass Transfer, 2005,48(10):1898- 1908   
[5] Akbal S,Baytas F. Effects of Non-uniform Porosity on Double Diffusive Natural Convection in a Porous Cavity With Partially Permeable Wall [J].International Journal of Thermal Sciences, 2008,47(7): 875-885   
[6] Baytas A C,Baytas A F,Ingham D B,et al.Double Diffusive Natural Convection in an Enclosure Filled With a Step Type Porous Layer: Non-Darcy Flow [J]. International Journal of Thermal Sciences,2009,48(4):665-673   
[7] Chen B,Wang L,Liu F,et al. Effect of Mesoscopic Structure of Interface on Heat and Mass Transfer in a Partially Porous Cavity [C]//ASME 2009 Second International Conference on Micro/Nanoscale Heat and Mass Transfer.American Society of Mechanical Engineers, 2009:699-705   
[8] Liu F,Chen B M.Natural Convection ina Cavity Partially Filled with a Vertical Porous Medium [C]//Advanced Materials Research.2011,321:15-18   
[9] Hadidi N,Ould-Amer Y,Bennacer R.Bi-layered and Inclined Porous Collector: Optimum Heat and Mass Transfer[J].Energy,2013,51:422-430   
10] Hadidi N,Bennacer R,Ould-amer Y.Two-Dimensional Thermosolutal Natural Convective Heat and Mass Transfer in a Bi-layered and Inclined Porous Enclosure [J]. Energy,2015,93(2):2582-2592   
11] Hadidi N,Bennacer R. Three-dimensional Double Diffusive Natural Convection Across a Cubical Enclosure Partially Filled by Vertical Porous Layer [J].International Journal of Thermal Sciences, 2016,101(10):143-157   
12] 张国庆，陈宝明，刘智，刘芳．格子Boltzmann 方法对多孔 介质复合通道内流动的研究，节能,2014,5(380)：10-13 ZHANG Guoqing, CHEN Baoming, LIU Fang. The Researching of Flow in Porous Medium Composite Channel Using Lattice Boltzmann Method,Energy Conservation, 2014, 5(380): 10-13   
'13] Kang Q, Zhang D,Chen S,et al. Lattice Boltzmann Simulation of Chemical Dissolution in Porous Media [J].Phys

# 5结论

本文采用 Boltzmann 方法在孔隙尺度下，对路易斯数 $L e { = } 2 . 0$ ，格拉晓夫数 $G r { = } 1 0 ^ { 4 }$ ，浮升力比$N { = } 1 . 0$ ，普朗特数 ${ P r } { = } 0 . 7$ 时，多孔介质层与纯流体空间组成的复合方腔内顶盖驱动的双扩散混合对流现象进行了数值模拟，分析讨论了多孔介质层孔隙率、不同位置及 $R i$ 对方腔内热质双扩散特性的影响，得到结论如下：

1）多孔介质层的存在对方腔内顶盖驱动下的双扩散特性影响显著，且孔隙率越小，多孔介质层越靠近高温高浓度壁面，影响越明显。

2）当多孔介质层孔隙率 $\varepsilon$ 不变时，在位置$D _ { 1 } { \sim } D _ { 3 }$ 之间，方腔高温高浓度壁面 $N u _ { \mathrm { a v } }$ 和 $S h _ { \mathrm { a v } }$ 随多孔介质层的右移而增大，在位置 $D _ { 3 } { \sim } D _ { 5 }$ 之间，多孔介质层位置对高温高浓度壁面 $N u _ { \mathrm { a v } }$ 和 $S h _ { \mathrm { a v } }$ 影响不显著。

ical Review E,2002,65(3):036318 [14] Kang Q，Lichtner P C,Zhang D.Lattice Boltzmann Porescale Model for Multicomponent Reactive Transport in Porous Media [J].Journal of Geophysical Research: Solid Earth,2006,111(B5):5203 [15]Kang Q,Lichtner P C,Zhang D.An Improved Lattice Boltzmann Model for Multicomponent Reactive Transport in Porous Media at the Pore Scale [J].Water Resources Research,2007,43(12):W12S14 [16]Kang Q，Wang M,Mukherjee P,and Lichtner P C. Mesoscopic Modeling of Multi-Physiochemical Transport in Porous Media [J].Advances Mechanical Engineering,   
2010,2:142879 [17]WangM,Wang J,Pan N,and Chen S,Mesoscopic Predictions of the Effective Thermal Conductivity of Microscale Random Porous Media.Physical Review E.20o7: 75:   
036702 [18]Wang M,Pan N.Predictions of Effective Physical Properties of Complex Multiphase Materials [J].Materials Science and Engineering:R:Reports,2008,63(1):1-30 [19]Bird R B.Transport Phenomena [J].Applied Mechanics Reviews,2002,55(1):R1-R4.   
[20]Guo Z,Shi B,Zheng C.A Coupled Lattice BGK Model for the Boussinesq Equations [J].International Journal for Numerical Methods in Fluids,2002,39(4):325-342   
[21]Qian YH, Dhumieres D,Lallemand P,Lattice BGK Models for Navier-Stokes Equations [J],Europhysics Letters, 1992,17(6): 479-484   
[22]Sheikholeslami M,Gorji-Bandpy MGanji D D.Investigation of Nanofluid Flow and Heat Transfer in Presence of Magnetic Field Using KKL Model[J].Arabian Journal for Science and Engineering,2014,39(6):5007-5016   
[23] Guo Z L, Zheng C G,ShiB C. Non-equilibrium Extrapolation Method for Velocity and Boundary Conditions in the Lattice Boltzmann Method [J].Chinese Physics,2002, 11(4):0366-0374   
[24] Chen S,Martinez D,Mei R.On Boundary Conditions in Lattice Boltzmann Methods [J].Physics of Fluids (1994- present),1996,8(9):2527-2536   
[25] Teamah M A,El-Maghlany WM.Numerical Simulation of Double-diffusive Mixed Convective Flow in Rectangular Enclosure With Insulated Moving Lid [J].International Journal of Thermal Sciences,2010,49(9):1625-1638