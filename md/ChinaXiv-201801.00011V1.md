黑白印刷

# 流量分配不均下三股流板翅式换热器数值研究

李俊¹，蒋彦龙²，王瑜³，孟二林¹，李翠敏1(1.苏州科技大学 环境科学与工程学院，苏州，215009；2.南京航空航天大学 航空宇航学院，南京，210016；3 南京工业大学 城市建设学院，南京，210009)

摘要：建立了流量分配不均下多股流板翅式换热器通用传热数学模型，并通过 FLUENT 仿真和自主编程相结合的方式实现了板翅式换热器数值计算。以机载交叉式三股流板翅式换热器为例，通过与文献试验数据对比论证了数值方法的合理性，分析了变流体比热容、流体入口温度和流体流动阻力条件下流量分配不均对多股流板翅式换热器传热性能的影响。

关键词：三股流板翅式换热器；流量分配不均；数值模拟

中图分类号：V241.0 文献标志码：A

# Numerical Study of Three-stream Plate-Fin Heat Exchanger under the Condition of Flow Ununiform Distribution

LI Jun1, JIANG Yan-Long², WANG $\mathrm { Y u } ^ { 3 }$ ,MENG Er-Lin1,LI Cui-Min1 (1.SchoolofEnviromentalScienceandEnginering,SuzhouUniversityofSienceandTechology,Suzhou,250,Cin; 2. College of Aerospace Engineering,Nanjing UniversityofAeronauticsandAstronautics,Nanjing,210o16,China; 3. College of Urban Construction,Nanjing Tech University, Nanjing,210009, China)

Abstract: The mathematical model of multi-stream plate-fin heat exchanger (MPFHE) under the condition of flow ununiform distribution was established，and numerical calculation of MPFHE was achieved by the integration ofFLUENT and independent programming.For the airborne three-stream plate-fin heat exchanger with cross type,the rationality of numerical method was testified compared with the test data from reference,and the heat transfer performance of MPFHE under the influence offlow maldistribution was analyzed under diffrent specific heat capacity, inlet temperature and flow resistance.

Key words: three-stream plate-fin heat exchanger; flow ununiformity; numerical simulation.

# 0引言

多股流板翅式换热器通过冷热流体资源整合，具有系统集成度高、便于管理、节约投资成本、占地面积小等优点，在航空领域有着广泛应用前景。在板翅式换热器设计时，通常假定流体流量均匀分配，实际上，由于封头和导流片结构影响，流量均匀分配仅是理想工况，尤其当换热器传热单元数较大时，这种影响将更严重。流量分配不均不容忽视，国内外学者对此展开研究。

在国外,Ranganayakulu[',2采用有限元方法研究了两股流交叉式换热器流体流动方向热传导、入口温度和流量分配不均对换热器换热性能的影响。Lalotl3通过电加热实验研究了流量分配不均对换热器换热性能的影响，研究发现：由于流体流量分配不均匀，交叉式换热器换热性能损失高达 $2 5 \%$ 。Mishra4采用有限差分法通过阶梯型、指数型、正弦型分配模型研究了交叉式两股流换热器流量分配不均且动态变化时对换热器换热特性的影响。Yuan[5]基于四种流量分配模型研究了三股流换热器流量分配不均匀特性与换热性能之间的关系，通过流体温度场和效率对比认为流量分配不均可能会提升换热器性能。

国内西安交通大学传热与强化课题组针对封头和导流片结构引起的流量分配不均问题进行了研究。文键采用CFD 软件数值模拟了工业用基本型封头、顺排孔板和错排孔板封头的流量分配不均匀特性，证明封头结构改善可有效降低最大流速比和不均匀参数，之后通过实验与数值模拟结果作了对比分析[7]，同时采用相同实验研究方法对两相流在不同封头结构型式下流量分配特性作了研究[]，证明两相流体在换热器内流量分布比单相流更加复杂且不均匀。焦安军[对基本型封头结构进行了二次封头改进，实验研究了一次封头和二次封头进出口管径选取对流量分配不均匀性的影响，得出结论：当一次封头进出口管径比与二次封头进出口管径比相等时流量分配将更加均匀。另外，焦安军[10,11]还对导流片的结构参数和导流角度对导流性能和换热性能进行了深入研究。张哲[12采用CFD 软件数值模拟对比分析了基本型封头和二次封头改进型封头结构的流量分配特性，证明改进后的封头结构流体流动均匀性得到明显改善，流体分配均匀度和最大与最小流速比均得到减小，之后张哲[13,14]通过实验对上述结论进行了验证。

目前国内外关于流量分配不均对多股流换热器传热性能的影响研究较少，尽管与两股流换热器相比存在共通之处，但是多股流换热器流体间流动方式多样且温度耦合，流量分配不均必然导致传热特性具有新的表现形式。本文拟基于FLUENT仿真模拟获得特定结构多股流换热器流量分配模型，采用自主编制的多股流板翅式换热器计算程序，实例分析流量分配不均对换热器传热性能的影响。

# 1MPFHE数值计算方法

# 1.1数学模型

对于多股流板翅式换热器(如图1)，为建模方便，假设：通道内流体沿高度方向温度相等；翅片和隔板厚度方向温度相等；翅片与隔板接触良好；隔板温度等于翅片根部温度；忽略同一通道流体横向导热；忽略翅片和隔板横向导热。

![](images/ec362a1ff1852f11131318300b46ff1238a2b52eed12ea397f14dae2329d3060.jpg)  
图1板翅式换热器结构示意图

Fig.1 Structure of plate-fin heat exchanger

基于上述假设，分别建立翅片、隔板、以及流体能量守恒方程，对于单相流体：

$$
\begin{array} { r l } & { ( F c _ { p } ) _ { f u i d , i } G _ { i } ( n ) H _ { i } ( 1 - f \delta ) _ { i } \frac { \mathrm { d } T _ { i } ( l ) } { \mathrm { d } l } = } \\ & { \alpha _ { i } ( 1 - f \delta ) _ { i } \big [ t _ { i } ( 0 ) + t _ { i } ( H _ { i } ) - 2 T _ { i } ( l ) \big ] + } \\ & { \left[ \lambda ( f \delta ) _ { i } \frac { \mathrm { d } t _ { i } ( H _ { i } ) } { \mathrm { d } x _ { i } } - \lambda ( f \delta ) _ { i } \frac { \mathrm { d } t _ { i } ( 0 ) } { \mathrm { d } x _ { i } } \right] } \end{array}
$$

上式中， $F$ 表示流体间的相对流动方向( $F$ 等于1或-1)； $l$ 、 $n$ 分别表示沿流体流动方向、流动横向笛卡尔坐标 $\mathrm { { ( m ) } }$ ；下标 $i$ 表示通道编号，$\scriptstyle i = 1 , 2 , \dotsc \dotsc \mathrm { N }$ ； $G$ 表示质量流速( $\mathrm { \ k g / ( m } ^ { 2 } \cdot \mathrm { s ) } \$ )，流体在不同通道间的质量流速分布通过FLUENT 仿真模拟获得； $c _ { p }$ 表示流体定压比热容 $( \mathrm { J } / ( \mathrm { k g } { \cdot } \mathrm { K } ) )$ ； $H$ 表示翅片高度 $\mathrm { { ( m ) } }$ ; $f$ 表示单位长度翅片个数 $( \mathbf { m } ^ { - 1 } )$ ）； $\delta$ 表示翅片厚度 $\mathrm { { ( m ) } }$ ； $T$ 表示流体温度(K)； $\mathbf { \chi } _ { t }$ 表示翅片温度(K)； $\lambda$ 表示翅片导热系数 $\left( { \mathrm { W / ( m } } { \cdot } { \mathrm { K } } \right) )$ ； $\alpha$ 表示对流表面换热系数 $( { \mathrm { W } } / ( { \mathrm { m } } ^ { 2 } { \cdot } { \mathrm { K } } ) )$ 。

另外，式(1)中的第一项表示流体沿流动方向能量增量，第二项表示流体与上、下隔板之间的热流量，第三项表示翅片上下根部热流差，其值等于流体与翅片之间的热流量。

对于隔板建立能量守恒方程：

$$
\begin{array} { r l } & { - \lambda ( f \delta ) _ { f i n , i } \frac { \mathrm { d } t _ { f i n , i } ( H _ { i } ) } { \mathrm { d } x } + \lambda ( f \delta ) _ { f i n , i + 1 } \frac { \mathrm { d } t _ { f i n , i + 1 } ( 0 ) } { \mathrm { d } x } + } \\ & { \alpha _ { i } ( 1 - f \delta ) _ { f i n , i } \Big [ T _ { i } ( l ) - t _ { f i n , i } ( H _ { i } ) \Big ] + } \\ & { \alpha _ { i + 1 } ( 1 - f \delta ) _ { f i n , i + 1 } \Big [ T _ { i + 1 } ( l ) - t _ { f i n , i + 1 } ( 0 ) \Big ] = 0 } \end{array}
$$

上式中， $x$ 表示沿翅片高度方向笛卡尔坐标$\mathrm { { ( m ) } }$ 。下标 $i$ 表示隔板编号， $\scriptstyle i = 0 , 1 , 2 , \dotsc \dotsc \mathrm { N }$ ，且第一、三项分别表示第 $i$ 通道翅片、流体与隔板上端面之间的热流量，第二、四项分别表示第 $( i { + } 1 )$ 通道翅片、流体与隔板下端面之间的热流量。根据假设，换热器上下隔板绝热，上隔板 $( i = N )$ 绝热时，第二、四项为0，下隔板 $( i = 0 )$ 绝热时，第一、三项为0。

另外根据假设，隔板上下端面温度相等，即：

$$
t _ { i } ( H _ { i } ) = t _ { i + 1 } ( 0 ) \quad i = 1 , 2 . . . . . . , N - 1
$$

对于翅片建立能量守恒方程：

$$
\lambda \delta _ { i } { \frac { \mathrm { d } ^ { 2 } t _ { i } ( x ) } { \mathrm { d } x ^ { 2 } } } + 2 \alpha _ { i } \big [ T _ { i } ( l ) - t _ { i } ( x ) \big ] = 0
$$

令 $P _ { i } = \sqrt { 2 \alpha _ { i } / ( \lambda \delta _ { i } ) }$ ，上式的一般解可表示为：

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { t _ { i } ( x ) = T _ { i } ( l ) + A _ { i } \sinh ( P _ { i } x _ { i } ) + B _ { i } \cosh ( P _ { i } x _ { i } ) } \\ { \displaystyle { \frac { \mathrm { d } t _ { i } ( x ) } { \mathrm { d } x _ { i } } } = P _ { i } [ A _ { i } \cosh ( P _ { i } x _ { i } ) + B _ { i } \sinh ( P _ { i } x _ { i } ) ] } \end{array} \right. } \end{array}
$$

上式 $A _ { i }$ 、 $B _ { i }$ 表示翅片定解参数，将式(5)代入式 $( 1 \sim 3 )$ ，经整理后式(1)、(2)和(3)构成关于流体温度 $T _ { i } ( l )$ 、 $A _ { i }$ 和 $B _ { i }$ 共计3N 方程。

# 1.2数值离散方法

将换热器划分为如图2所示的 $\mathbb { W } \times \mathbb { L }$ 个子单元换热器，对于式(1)中 $T _ { i } ( l )$ 的一阶导数项，通过一阶中心差分离散如下：

$$
\cfrac { d T _ { i } ( l ) } { d l } = \cfrac { T _ { o u t } ( i , j , k ) - T _ { i n } ( i , j , k ) } { \Delta l }
$$

![](images/0928baf6604d2259acb0726bb098e37a274d72ba357061d7bc7845985f92a2ae.jpg)  
图2换热器网格划分示意图  
Fig.2 Subdivision of heat exchanger

对于流体与隔板、翅片的对流换热定性温度，取子单元换热器流体进出口温度的算术平均值，如下：

$$
T _ { i } ( l ) = \frac { T _ { o u t } ( i , j , k ) + T _ { i n } ( i , j , k ) } { 2 }
$$

# 1.3翅片数据库

为了实现多股流板翅式换热器精确数值计算，合理的数值计算方法是关键，但是翅片的对流表面换热系数计算也是比较重要的影响因素。翅片结构的传热特性常用 $j$ 因子表征。针对下文的锯齿形翅片，选用Weiting拟合公式[15]：

$$
\left\{ \begin{array} { l l } { \mathrm { R e } \leq 1 0 0 0 ; ~ j = 0 . 4 8 3 ( \displaystyle \frac { a } { d _ { e } } ) ^ { - 0 . 1 6 2 } ( \displaystyle \frac { s _ { f i n } - \delta _ { f i n } } { H _ { f i n } - \delta _ { f i n } } ) ^ { - 0 . 1 8 4 } \mathrm { R e } ^ { - 0 . 5 3 6 } } \\ { \mathrm { R e } \geq 2 0 0 0 ; ~ j = 0 . 2 4 2 ( \displaystyle \frac { a } { d _ { e } } ) ^ { - 0 . 3 2 2 } ( \displaystyle \frac { \delta _ { f i n } } { d _ { e } } ) ^ { 0 . 0 8 9 } \mathrm { R e } ^ { - 0 . 3 6 8 } } \end{array} \right.
$$

上式 $a$ 表示锯齿形翅片不间断流动长度 $( \mathfrak { m } ) ; d _ { e }$ 表示当量直径 $\mathrm { ( m ) }$ ; $s _ { f i n }$ 表示翅片间距 $\mathrm { { ( m ) } }$ ; $H _ { \mathfrak { f i n } }$ 表示翅片高度 $\mathrm { { ( m ) } }$ ； $\delta _ { f i n }$ 表示翅片厚度 $\mathrm { { ( m ) } }$ ；Re表示雷诺数。式(8)中关于过渡区的 $j$ 因子通过 $j { \mathrm { - R e } }$ 曲线的交点确定，实际Re小于交点处 $\mathtt { R e }$ ，采用层流区公式计算，反之，采用湍流区公式。

# 1.4流量分配模型建立方法

板翅式换热器结构复杂(如图3所示)，入口结构主要分为封头和导流片两部分，采用CFD同时考虑两者对换热器流量分配的影响，网格数量大，因此在研究换热器封头和导流片流量分配特性时需简化模型。假定：流体物性参数为常数，且忽略温度场对速度场的影响；封头和导流片的流量分配特性单独分析；分析封头结构对流量分配特性影响时，芯体和导流片采用同等阻力特性的多孔介质材料替代，模拟不同流量下封头背压。基于上述假设，采用FLUENT可分别获得特定结构形式换热器封头、导流片的流量分配规律。之后，参照流体入口质量流量可构建换热器流量分配模型，具体实施方法如下：

图3板翅式换热器FLUENT仿真模型  
![](images/d3f542804f5bbc92ed900fef5a0dbf6de4ffab9b989d860876af7864ebf4ac4c.jpg)  
Fig.3FLUENT models of plate-fin heat exchanger

(1)基于平均质量流量，仿真计算单通道流体的流量分配和流动阻力特性，此时流体的速度场在通道内呈二维分布，采用加权方式可将二维速度场简化为单通道一维流量分配模型。本文将通道沿流体流动方向划分为进口、中间、出口三个区域，同时将通道沿流体流动方向垂直的横向截面划分为W个子单元，那么对于任一子单元 $k$ 的质量流量占单通道总质量流量的比重可表示为：

$$
\psi _ { k } = \frac { G _ { _ k } } { G _ { _ { c h a n n e l } } } = w _ { _ { i n } } \frac { G _ { _ { k , i n } } } { G _ { _ { c h a n n e l } } } + w _ { _ { m i d l e } } \frac { G _ { _ { k , m i d d l e } } } { G _ { _ { c h a n n e l } } } + w _ { _ { o u t } } \frac { G _ { _ { k , o u t } } } { G _ { _ { c h a n n e l } } }
$$

上式， $G _ { k }$ 表示第 $\mathbf { k }$ 个子单元的平均质量流量，$G _ { c h a n n e l }$ 表示单通道质量流量， $G _ { k , i n }$ 、 $G _ { k , o u t }$ 、 $G _ { k , m i d d l e }$ 分别表示进口、出口、中间区域第 $k$ 个子单元的质量流量， $w _ { i n }$ 、 $w _ { m i d d l e }$ 和 ${ { \ w } _ { o u t } }$ 分别表示进口、出口、中间区域流量分配权重，具体取值需依据仿真结果、导流结构以及流体间的流动方式定性确定。对于下文的算例，考虑到中间为主流区域，进口区域冷热流体温差较大，换热较为充分，因此三个区域流量分配所占的权重w依次取值0.3、0.6、0.1。

(2)根据单通道流体流动阻力特性，将封头模型中通道设置为多孔介质并调整其阻力参数，保证封头模型通道阻力特性与单通道相当，由此获得不同通道的流量分配特性。

(3)将各通道流量乘以 $\psi _ { \boldsymbol { k } }$ 可获得某一流体的二维流量分配模型 $( i , G _ { k } )$ 。

# 1.5数值计算流程

基于上述分析，将交叉式多股流板翅式换热器划分为 $\mathrm { w } \times \mathrm { L }$ 个子单元换热器(如图1、2中虚线所示)，流量分配不均下多股流板翅式换热器的数值计算方法(如图4)可表述为：1)根据换热器封头和导流结构形式采用FLUENT 获得各股流体的二维流量分配模型(1.4节所述)；2)假定流体流量在子单元换热器内均匀分配，以一个子单元换热器作为研究对象，已知流体进口温度及其对应的入口流量，确定流体物性参数，根据公式(8)计算对流表面换热系数$\alpha$ ，之后根据1.1和1.2节所述方法建立各通道流体出口温度 $T _ { o u t } ( i , j , k )$ 的线性方程组并求解；3)通过逐行或逐列扫描依次循环可获得流体温度场分布，其中每次计算子单元换热器时， $\alpha$ 需根据实际流量重新计算一次。

![](images/7a3bde137941b785aab2eb8a521782e28a91cea426bdff3d2d597ea89666e052.jpg)  
图4多股流板翅式换热器数值计算流程  
Fig.4 Calculation process of multi-stream plate-fin heat exchanger

# 2 算例分析

以文献[16]中机载三股流换热器为例，芯体长度 $4 0 0 \mathrm { m m }$ ，宽度 $1 3 0 \mathrm { m m }$ ，隔板厚度 $0 . 8 \mathrm { m m }$ ，通道排列方式(ABACABAC…)A。流体(空气)A 作为冷流体沿宽度方向流动，流体(空气)B 和流体(空气)C 作为热流体沿长度方向顺流流动。三股流体翅片均为锯齿形，不间断长度均为 $3 \ \mathrm { m m }$ ，换热器结构参数如表1所示。

表1三股流板翅式换热器结构参数  
Table 1 Structure parameters of three-stream plate-fin heat   

<html><body><table><tr><td colspan="4">exchanger</td></tr><tr><td></td><td>流体A</td><td>流体B</td><td>流体C</td></tr><tr><td>流道数</td><td>27</td><td>13</td><td>13</td></tr><tr><td>翅高/mm</td><td>4.5</td><td>2.0</td><td>2.0</td></tr><tr><td>节距/mm</td><td>2.0</td><td>1.4</td><td>1.4</td></tr><tr><td>翅厚/mm</td><td>0.15</td><td>0.15</td><td>0.15</td></tr></table></body></html>

# 2.1热流体流量分配模型

对于算例所述三股流板翅式换热器(如图3)，冷流体A通过扩张管和渐缩管流入和流出换热器，可认为冷流体A在通道内流量均匀分配；热流体B和C 所在通道布置有封头和导流结构，流体在通道内和通道间流量分配不均匀。

对于热流体B，当总质量流量为 $3 3 0 \mathrm { k g / h }$ 时，采用上文1.3节所述方法获得流量分配模型如图 5所示，具体FLUENT仿真过程属常规方法，本文限于篇幅不具体展开分析。热流体C总质量流量为$3 3 0 \mathrm { k g / h }$ 时，其流量分配模型与流体B轴向对称。

![](images/642c7d6077e38e7dc05facc167ba55d70bbede3d2289883ddc3e7eb4325058d4.jpg)  
图5热流体B流量分配模型Fig.5Flow distribution model of hot fluid B

# 2.2数值方法试验验证

文献[16]在热动力试验台上对三股流板翅式换热器数值方法进行了试验验证，认为流量分配不均对数值计算的精度影响较大。本节引入流量分配不均匀模型后，在流体A变流量下，对比热流体B、C 出口平均温度的数值计算与试验数据，如图6所示；流量分配均匀和不均匀模型下，热流体B和C出口温度相对计算误差，如图7所示。

![](images/8d1dfd09b94023ee86996ff48f55c1d7511a6cd878d2ea00a3d8550d9be2cd99.jpg)  
图6热流体B和C数值计算结果与试验数据对比

![](images/0355a4be89bd5017372bf68d2c4f3708d88df0502e930acb39695fa24b55f02c.jpg)  
Fig.6 Comparison between calculation results and experimental   
图7不同流量分配模型下热流体B和C相对计算误差Fig.7 Calculationuncertainty for fluidB and C under differentflow distribution model

从图6、7可看出，尽管引入的流量分配不均匀模型为简化模型，数值计算精度仍得到了有效提高。另外从图中可以看出，冷流体A质量流量越低，流量分配不均匀模型对数值计算的修正效果越明显，当冷流体A质量流量为 $8 0 0 \mathrm { k g / h }$ 时，流体C误差修正 $3 . 9 \%$ ；冷流体A热容流越高，流量分配不均匀对热流体换热性能的影响越小。

# 2.3流量分配不均对换热性能影响

对于上述三股流换热器，假定流体A为冷流体，入口质量流量和温度分别为 $1 4 0 0 \mathrm { k g / h }$ 、 $3 0 ^ { \circ } \mathrm { C }$ ，流体B、C为热流体，入口质量流量均为 $3 3 0 \mathrm { k g / h }$ ，入口温度分别为30、90、 $1 3 0 \mathrm { ~ } ^ { \circ } \mathrm { C }$ 。

定义流体在流量分配均匀和不均匀时热负荷相对差值为：

$$
U _ { i } = \frac { q _ { i , u n e v e n } - q _ { i , e v e n } } { q _ { i , e v e n } }
$$

上式， $i$ 表示流体种类， $q _ { i , u n e \nu e n }$ 和 $q _ { i , e \nu e n }$ 分别表示流量分配不均匀和均匀时流体热负荷。

现分别从变流体比热容、变流体入口温度、变流体流阻三个角度，分析其对换热器传热性能的影响。

# 1)变流体比热容

改变流体B比热容，计算热流体B、C不同热容比条件下各股流体热负荷相对差值如图8所示。从图中可以看出，随着流体B比热容增加，流量分配不均匀导致流体B换热量增加、流体C换热量降低，流量分配不均匀对热容流较低的流体影响较大，$U _ { _ B }$ 绝对值最大达到 $5 \%$ ；冷流体作为唯一冷流体，其换热量代表了换热器总换热量，流量分配不均匀导致 $U _ { _ A } \leq 0$ ，当热流体B 比热容足够大时 $U _ { _ A }$ 趋于0。

![](images/c405df2582e6ff979cd7abc598f80f427dfd59dc3588c1ff052e491078ada427.jpg)  
图8热流体不同热容比条件下各股流体热负荷相对差值Fig.8Relativedifferenceofheatloadineachfluidunderdifferent heat capacity ratio of hot fluid

改变冷流体A的比热容，热流体B、C比热容相同，冷热流体不同热容比条件下各股流体热负荷相对差值如图9所示。从图中可看出，冷流体A热容流越小，热流体 $U _ { _ B }$ 和 $U _ { c }$ 的绝对值越大，流量分配不均匀导致入口靠近冷流体A进口侧的流体B换热量升高 $7 . 5 \%$ ，相对地流体C换热量降低 $4 . 2 \%$ 换热器总体换热性能略有下降；随着冷流体A热容流增大，流量分配不均匀对各股流体的换热性能影响逐渐降低。这是由于：冷流体A热容流越小，在流动过程中其温升越快，流体B大流量区域靠近冷流体A进口侧，必然获得更多冷量，当流体A热容流增加时，流体A温度梯度减小，流体B和C均能得到有效换热，流量分配不均匀对换热性能的影响也就越小。

![](images/a2ab9b51bab2f7d317854ddbda12a7f792f06fe0b084bf9e793c729894b03560.jpg)  
图9冷热流体不同热容比条件下流体热负荷相对差值 Fig.9Relative difference ofheatload in each fluid under different heat capacity ratio of hot and cold fluid

# 2)变流体入口温度

改变热流体C入口温度，其变化范围为$7 0 { \sim } 1 3 0 ^ { \circ } \mathrm { C }$ ，计算热流体C不同温度条件下各股流体热负荷相对差值如图10所示。从图中可以看出，当$( T _ { i n , C } - T _ { i n , A } ) / ( T _ { i n , B } - T _ { i n , A } ) < 1$ 时，热流体B入口温度比C高，且因为流体C大流量区域在冷流体A出□侧，流体C温度越低，其换热量受流量分配不均匀影响较大，换热量最高可降低 $4 . 8 \%$ ；随流体C温度升高，冷热流体温差越大，换热越充分，流量分配不均匀对换热性能的影响减小。

![](images/d1a4e3a1bdb287c7ff86870800607a758693e4f052db8793a687afa44382bf49.jpg)  
图10热流体C不同温度条件下各股流体热负荷相对差值Fig.lORelativedifferenceofheatloadineachfluid underdifferent inlet temperature of hot fluid C

# 3)变流体流动阻力

改变热流体在通道内压降获得不同的流量分配模型，计算热流体不同流量分配模型条件下各股流体热负荷相对差值如图11所示。

![](images/f16290f2565c5ea15c2f79bdba2fdc6717d21e4f0ad69b81629876c8e0f2296b.jpg)  
图11封头不同背压下各股流体热负荷相对差值Fig.11Relative differenceofheatload in eachfluid underdifferent backpressure of the shell cover

从图11可以看出，当通道压降较低时 $U _ { \mathbf { \Omega } _ { A } } \setminus U _ { B }$ 和 $U _ { c }$ 均小于0，意味着各股流体换热性能均降低;当通道压降增大时，流体在各个通道内流量分配趋于均匀，各股流体换热性能均得到提升；当通道压降趋于无穷大时，认为同一流体不同通道内流量分配均匀，但是导流片结构导致了通道内流体流动横向流量分配不均匀，因此靠近冷流体进口侧的热流体B换热量增加，相反地热流体C换热量降低，由此可看出导流片结构和布置方式会影响热流体间能量分配比例。

# 4小结

本文采用CFD和自主编程相结合的方式，构建了流量分配不均下多股流板翅式换热器数值计算方法，通过与试验数据对比论证了数值方法的合理性，最后实例分析了变流体比热容、变流体入口温度、变流体流阻对换热器传热性能的影响，所得结论如下：

(1)通过与试验数据对比，证明引入文中所述的流量分配不均匀模型可有效提高数值计算精度，尤其当冷流体质量流量越低时流量分配不均匀模型的修正效果越明显。

(2)以三股流换热器实例，在相同的流量分配模式下，改变热流体热容流比，流量分配不均匀对热容流较小流体影响大，换热量最高可降低 $5 \%$ ；改变冷热流体热容流比，流量分配不均匀导致热流体能量分离明显，入口封头靠近冷流体入口侧的热流体换热量可升高 $7 . 5 \%$ ，相对地另一股热流体换热量降低 $4 . 2 \%$ ，冷流体的热容流越低，影响效果越明显;改变热流体入口温度，两股热流体中温度较低者，其换热量受流量分配不均影响较大，换热量最高可降低 $4 . 8 \%$ ；改变通道流动阻力，在不同流量分配方式下，通道流动阻力越小，通道间流量分配越不均匀。

# 参考文献

[1]Ranganayakulu C， Seetharamu K N. the Combined Effects ofLongitudinal HeatConductionFlow Nonuniformity and TemperatureNonuniformityin Crossflow Plate-fin Heat Exchangers [J]. International Communication in Heat and Mass Transfer, 1999,26(4): 669-678   
[2] Ranganayakulu C,Seetharamu KN, Sreevatsan K V. the Effects of Inlet Fluid Flow Nonuniformity on Thermal Performance and Pressure Drops in Crossflow Plate-fin

Compact Heat Exchangers [J]. International Journal of

Heat and Mass Transfer,1997,40(1): 27-38   
[3]Lalot S,Florent P, Lang S K, Bergles A E, et al. Flow Maldistribution in Heat Exchangers [J]. Applied Thermal Engineering, 1999,19(8): 847-863   
[4]Mishra M, Das P K, Sarangi S.Effect of Temperature and FlowNonuniformityonTransient Behaviourof Croslow Heat Exchanger [J]. International Journal of Heat and Mass Transfer,2008,51(9): 2583-2592   
[5]Yuan P. Effect of Inlet Flow Maldistribution on the Thermal Performance of a Three- fluid Crossflow Heat Exchange［J]. International Journal of Heat and Mass Transfer,2003,46(20) : 3777- 3787   
[6]WEN Jian, LI Yanzhong. Study of Flow Distribution and its Improvement on the Header of Plate-fin Heat exchanger[J].Cryogenics,2004,44(11): 82-831   
[7]文键.基于 PIV 技术的换热器内部场分布特性研究[D]. 西安:西安交通大学,2006 WEN Jian.the Investigation ofFlow Field Distribution in Plate-Fin Heat Exchangers Based on PIV Technology[D]. Xi'an :Xi'an Jiaotong University, 2006   
[8]文键,王斯民,厉彦忠.板翅式换热器二相流的分配特性 [J].化学工程,2010,38(12) :26-29 WEN Jian, WANG Simin, LI Yanzhong. Two-Phase Flow Distribution in Plate-fin Heat Exchanger [J].Chemical Engineering,2010,38(12):26-29   
[9]JIAO Anjun, ZHANG Rui, Jeong S. Experimental InvestigationofHeaderConfigurationonFlow Maldistribution in Plate-Fin Heat Exchanger[J].Applied Thermal Engineering, 2003,23(10):1235-1246   
[10] 焦安军,厉彦忠,张瑞等.板翅式换热器不同结构导流片 导流性能的研究[J].西安交通大学学报，2001, 35(11):1113-1117 JIAO Anjun, LI Yanzhong, ZHANG Rui, et al. Flow Distribution Performance of Different Distributor's Configuration in Plate-Fin Heat Exchanger[J].Jouranl of

Xi'an Jiaotong University, 2001,35(11):1113-1117 [11]焦安军,厉彦忠,张瑞等.板翅式换热器导流片结构参数 对其导流性的影响[J].化工学报,2003,54(2):153-158 JIAO Anjun,LI Yanzhong, ZHANG Rui, et al. Effects of Different Distributor Configuration Parameters on Fluid Flow Distribution in Plate-Fin Heat Exchanger[J].Journal ofChemical IndustryandEngineering，2003, 54(2):153-158

[12] ZHANG Zhe,TIAN Jinjin,GUO Yonggang,et al. CFD Simulation on Flow Distribution in Plate-Fin Heat Exchangers[J]. Advanced Materials Research, 2013, 665-657: 445-448

[13] ZHANG Zhe, Mehendale S, TIAN Jinjin， et al. Experimental Investigation of Distributor Configuration on Flow Maldistribution in Plate-Fin Heat Exchangers[J]. Applied Thermal Engineering,2015,85(22):111-123

[14] 张哲,田津津,郭永刚等.板翅式换热器封头对其流体分 配及换热的影响[J].化学工程,20013,41(9):40-44. ZHANG Zhe, TIAN Jinjin, GUO Yonggang, et al.Effects of Header Configurations on Flow Distribution and Heat Transfer in Plate-Fin Heat Exchangers[J].Chemical Engineering,2013, 41(9):40-44   
[15]Weiting A K.Empirical Correlations for Heat Transfer andFlow Friction Characteristicsof Rectangular Offset-Fin Plate-Fin Heat Exchangers[J].ASME Journal ofHeat Transfer,1975,97:488\~490   
[16]李俊,蒋彦龙,周年勇等.交叉式多股流板翅式换热器数 值研究[J].航空动力学报,2016,31(5):1087-1096 LI Jun， JIANG Yanlong， ZHOU Nianyong，et al. Numerical Study of Multi-Stream Plate-fin Heat Exchanger with Cross Type[J].Journal of Aerospace Power,2016,31(5):1087-1096