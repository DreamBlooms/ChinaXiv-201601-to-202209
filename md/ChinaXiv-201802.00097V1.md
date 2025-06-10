# 冷热油交替输送热力快速计算研究

韩东旭，王鹏，邵倩倩，宇波

(中国石油大学机械与储运工程学院，城市油气输配技术北京市重点实验室，北京 102249)

摘要：本文将基于贴体坐标的非稳态导热POD 低阶模型应用于冷热油交替输送热力快速计算中，并且详细介绍了POD 低阶模型的实施方案。在低阶模型的求解过程中针对管道热力影响区域内各部分导热系数相差达到300倍左右，文中采用更符合基函数空间导数物理意义的离散格式代替传统的中心差分格式来对其进行离散。在本文的算例中 POD 低阶模型平均计算误差不超过 $0 . 3 5 ^ { \circ } \mathrm { C }$ ，计算速度为传统的有限容积法的260 倍左右。

关键词： 冷热油交替输送；POD低阶模型；贴体坐标；快速计算

中图分类号：

文献标识码：A

# Fast Calculation of the Thermal Process during Hot and Cold Oil Alternating Transportation

HAN Dong-Xu WANG PengSHAO Qian-Qian YU Bo (National Engineering Laboratory forPipeline Safety,Beijing KeyLaboratoryof Urban Oiland Gas Distribution Technology, China University of Petroleum,Beijing,102249, China)

Abstract: A proper orthogonal decomposition (POD) Galerkin reduced order model based on body-fitted coordinate is applied to the fast calculation of the thermal process during cold and hot oil alternating transportation,and the implementation process is given in detail. Considering the uneven distributed heat conductivity coeffcient in the thermodynamically involved region of the pipeline (the ratio of heat conductivitycoefficients is as large as 300 around),a discretization scheme better fiting the physical meaning of the derivative of the basic function space is employed,instead of the traditional used central diference scheme.Trough all thecases devised,theaveraged computation error by POD reduced order model is below $0 . 3 5 ^ { \circ } \mathrm { C }$ ，while the speed can reach 26O times of the traditional finite volume method.

Keywords: Cold and hotoil alternating transportation; POD reduced order model; Body-fitted coordinate;Fast calculation

# 0前言

冷热油交替输送属国际前沿原油输送技术，即对两种或多种原油根据其物性尤其是粘温关系的不同采用不同的温度进行输送，在保证安全输送的前提下减少加热量达到节能的目的。但是这就会使整条管线始终处于热力不稳定状态，为了保证安全输送需要对其热力规律进行深入研究。

崔秀国[在其博士论文中从理论上深入研究了这一输油方案，姚峰2在大量数值模拟的基础上为中石油西部管道公司制定了一整套输送工艺，宇波等[3]通过数值模拟进一步研究了冷热油交替输送管道的

1

热力规律及其停输再启动问题。在上述数值研究中，存在一个普遍问题即计算速度较慢。在对热油管道的优化设计和风险评估中往往需要对大量的不同工况进行计算，这就会耗费大量的时间，甚至使得计算不能完成或者丧失了计算结果的时效性，所以必须寻求快速的计算方法。POD低阶模型作为一种快速计算方法被广泛应用于各工程领域中[4-9]。

在输油管道的热力规律计算方面文献[10]首次将POD低阶模型引入到了热油管道的计算中，采用基于非结构化网格的低阶模型，快速计算了埋地热油管道的冷热油交替输送和原油投产；文献[11]采用基于贴体坐标的稳态导热POD低阶模型，通过贴

体坐标的计算平面建立起不同的埋深和管径的管道横截面的关系，通过一次取样即可快速测不同管径和埋深的管道横截面稳态温度场。

但文献[10]和[11]均未考虑埋地管道的结蜡层、钢管壁和防腐层，由于其导热系数相差巨大，严重影响POD低阶模型的计算精度。文献[10]不能对不同埋深和管径的热油管道统一快速计算，文献[11]仅仅考虑了管道横截面的稳态温度场。

针对以上问题，本研究采用基于贴体坐标非稳态导热POD低阶模型，采用特殊格式离散基函数的空间导数，成功快速计算了不同埋深和管径的热油管道在冷热油交替输送时的热力规律。

# 1冷热油交替输送物理模型

图1所示为埋地冷热油交替输送管道示意图，冷油和热油交替从热站流入管道，油流与结蜡层内侧对流换热，结蜡层、管壁、防腐层以及土壤以热传导的形式换热，并经地面与大气换热。图2为埋地热油管道的热力影响区。

![](images/8432037b8e5072ea3cbbfb7f3d9a8553d2e898969f0335162623a6b95f9fa299.jpg)  
图1埋地冷热油交替输送管道示意图

![](images/7fbbd93e6874d18dec13e6a4ab10b80dd114bf0cf09c257f44e3b12dbb9c4cdf.jpg)  
Fig.1 Sketch of buried pipeline for cold and hot oil alternating transportation   
图2管道横截面示意图  
Fig.2 Schematic diagram of computational domain

为了方便计算，在冷热油交替输送油温沿程分布的计算过程中，做出以下假设：（1）管内原油温度在某一截面上是均匀的；（2）管道周围的土壤为各向同性的均匀介质；（3）忽略土壤区域轴向温降，将三维非稳态导热问题简化为二维非稳态导热问题；（4）管内结蜡层厚度在管道周向和轴向均不发生变化；（5）管道的热力影响区为 $1 0 \mathrm { m }$ ，即图2中$\mathrm { L } { = } 1 0 \mathrm { m }$ ， $\scriptstyle \mathrm { H = 1 0 m }$ 。

结蜡层、钢管壁、防腐层、土壤的传热控制方程：

$$
\rho _ { k } C _ { k } \frac { \partial T } { \partial \tau } = \frac { \partial } { \partial x } ( \lambda _ { k } \frac { \partial T } { \partial x } ) + \frac { \partial } { \partial y } ( \lambda _ { k } \frac { \partial T } { \partial y } ) k = 1 , 2 , 3 , 4
$$

油流控制方程连续性方程：

$$
\frac { \partial } { \partial \tau } ( \rho A ) + \frac { \partial } { \partial z } ( \rho V A ) = 0
$$

油流的换热方程：

$$
C _ { P } { \frac { d \vartheta } { d \tau } } - { \frac { \vartheta } { \rho } } \beta { \frac { d p } { d \tau } } - { \frac { f V ^ { 3 } } { 2 D } } = - { \frac { 4 q } { \rho D } }
$$

油流与结蜡层之间的匹配条件：

$$
- \lambda _ { 1 } \frac { \hat { \alpha } T } { \hat { \alpha _ { n } } \hat { \vert } _ { w } } \bigg \vert _ { w } = h _ { _ f } \left( \mathcal { S } - T _ { _ w } \right)
$$

其中 $T _ { _ w }$ 表示结蜡层和油流接触面的温度， $\mathcal { A }$ 表示热油温度， $h _ { f }$ 是管内油温对结蜡层的强制对流换热， $h _ { f }$ 为管内油温的函数。

管道热影响区域边界条件：

当 $x = 0$ ， $- ( H _ { o } - R _ { 1 } + \delta _ { 1 } ) \le y \le 0$ 时， $\lambda _ { \iota } \frac { \partial T } { \partial x } = 0$ ；当（204号 $x = 0$ （ $, - H \le y \le - ( H _ { o } + R _ { 1 } - \delta _ { 1 } )$ 时， $\lambda _ { k } \frac { \partial T } { \partial x } = 0$ ；当y=0时， $\lambda _ { 4 } \frac { \partial T } { \partial x } = h _ { _ a } ( T _ { _ a } - T _ { _ { g r o u n d } } )$ ；当 $\left| x \right| = L$ 时，T=0；当y=-H时T=T。

其中， $h _ { a }$ 为大气对土壤的换热系数，其值由实际测量确定； $T _ { c }$ 为土壤恒温层温度其值由实际情况确定； $T _ { a }$ 为大气温度，在本文中采用式（5）来计算

$$
T _ { a } = 5 \sin ( \frac { \pi } { 1 2 } t _ { 1 } ) + a t _ { 2 } + b
$$

式（5）中， $t _ { 1 }$ 单位为小时， $5 \sin ( \frac { \pi } { 1 2 } t _ { 1 } )$ 为一天内气温变化； $t _ { 2 }$ 单位为天， $a t _ { 2 } + b$ 为气温随日期的变化。

# 2直接数值模拟

在冷热油交替输送的热力计算中，主要需要求解方程（1）和（3)，下面对这两个方程的直接数值求解做简要介绍。

求解方程（1）主要目的在于求解任一管道横截面处管道热力影响区域内的温度场，根据对称性为了减少计算量只计算图2所示区域的一半。本文中采用基于贴体坐标的FVM计算热力影响区域内的温度场，当求解区域转换到了计算平面后，控制方程相应的转换到了计算平面中：控制方程公式（1）转换成公式（6)

$$
J \frac { \partial ( \rho _ { k } c _ { k } T ) } { \partial \tau } = \frac { \partial } { \partial \xi } [ \frac { \lambda _ { k } } { J } ( \alpha T _ { \xi } - \beta T _ { \eta } ) ] +
$$

$$
\frac { \partial } { \partial \eta } [ \frac { \lambda _ { \scriptscriptstyle k } } { J } ( \gamma T _ { \eta } - \beta T _ { \xi } ) ] + J S \qquad k = 1 , 2 , 3 , 4
$$

在FVM计算过程中，采用的贴体网格的总网格数目为3761，不同物性界面的导热系数采用调和平均进行插值，采用Gauss-Seidel迭代，迭代收敛标准为相邻两个迭代层的对应控制点最大误差小于 ${ 1 0 } ^ { - 9 }$ 。

利用原油与周围环境热量平衡关系实现管内油流传热与管外土壤传热的耦合，采用特征线法求解方程（2）并获得不同时间沿程油温分布。

# 3采用POD低阶模型快速计算

冷热油交替输送的热力规律计算，其计算量主要集中在管道横截面上温度场的计算即方程（6）的求解，该部分的计算消耗时间占据整个计算时间的$9 9 . 5 \%$ 以上。为此本文提出采用基于贴体网格的POD低阶模型来快速求解该方程，从而实现对不同埋深与管径的冷热油交替输送热力规律的快速计算。

由POD定义可知，稳态时计算平面上的温度场可写成一组基函数和对应的谱系数的线性叠加的形式，其中M表示所有基函数的个数。

$$
T ( \xi , \eta ) = \sum _ { k = 1 } ^ { M } a _ { k } \phi _ { k } \left( \xi , \eta \right)
$$

基于方程(6)，残差R可以定义为,

$$
R = J \frac { \hat { \sigma } ( \rho c _ { p } T ) } { \hat { \sigma } \tau } - \frac { \hat { \sigma } } { \hat { \sigma } \xi } [ \frac { \lambda } { J } ( \alpha T _ { \xi } - \beta T _ { \eta } ) ] -
$$

$$
\frac { \partial } { \partial \eta } [ \frac { \lambda } { J } ( \gamma T _ { \eta } - \beta T _ { \xi } ) ] - J S
$$

将方程(8)向基函数的空间投影，经过一系列推导可得（详见文献[12]），

$$
\begin{array} { l } { { \displaystyle 0 = \sum _ { k = 1 } ^ { M } \frac { d a _ { _ k } } { d \tau } \cdot H \tau _ { _ { i k } } + \sum _ { k = 1 } ^ { M } a _ { _ k } \cdot H n _ { _ { i k } } + \sum _ { k = 1 } ^ { M } a _ { _ k } \cdot H \nu _ { _ { i k } } + } } \\ { { \displaystyle \oint \sqrt { \alpha } q ^ { _ \xi } \phi _ { i } d \xi + \sqrt { \gamma } q ^ { _ { \eta } } \phi _ { i } d \eta + F _ { i } } } \end{array}
$$

其中 $H n _ { i k } = ( \frac { \hat { \sigma } \phi _ { i } } { \hat { \sigma } \xi } , \lambda \sqrt { \alpha } \frac { \hat { \sigma } \phi _ { k } } { \hat { \sigma } n ^ { \xi } } ) + ( \frac { \hat { \sigma } \phi _ { i } } { \hat { \sigma } \eta } , \lambda \sqrt { \alpha } \frac { \hat { \sigma } \phi _ { k } } { \hat { \sigma } n ^ { \eta } } ) ,$

$$
F _ { _ i } = - ( S , \Theta _ { _ i } ) , \Theta _ { _ i } = \phi _ { _ i } \cdot J
$$

将初始条件和边界条件引入到方程(9)中可求解得到谱系数，详见文献[12]。

由于管道热力影响区域中，结蜡层、钢管壁、防腐层和土壤层的导热系数（本文中分别取0.15$\mathrm { w / ( m ^ { \circ } C ) } \mathrm { . ~ } 5 0 \mathrm { ( w / m ^ { \circ } C ) } \mathrm { . ~ } 0 . 1 5 \mathrm { ( w / m ^ { \circ } C ) }$ 和 $0 . 8 5 \ : ( \mathrm { w / m ^ { \circ } C ) }$ ）相差巨大，尤其是钢管壁同结蜡层和防腐层的导热系数相差300倍左右。在这种情况下，采用传统的中心差分格式来对其进行离散已经不能满足精度要求，本文采用与基函数空间导数物理意义相适应的如下离散格式，

$$
( \phi _ { \xi } ) _ { P } = \frac { \phi _ { P } + B _ { _ { E } } / B _ { _ { P } } \phi _ { _ { E } } } { 1 + B _ { _ { E } } / B _ { _ { P 1 } } } - \frac { \phi _ { P } + B _ { _ W } / B _ { _ P } \phi _ { _ { W } } } { 1 + B _ { _ W } / B _ { _ { P 1 } } }
$$

$$
( \phi _ { \eta } ) _ { P } = \frac { \phi _ { P } + B _ { \scriptscriptstyle N } / B _ { \scriptscriptstyle P 2 } \phi _ { \scriptscriptstyle N } } { 1 + B _ { \scriptscriptstyle N } / B _ { \scriptscriptstyle P 2 } } - \frac { \phi _ { P } + B _ { s } / B _ { \scriptscriptstyle P 2 } \phi _ { s } } { 1 + B _ { s } / B _ { \scriptscriptstyle P 2 } }
$$

$$
B _ { _ N } = \frac { \lambda \alpha } { J \sqrt { \gamma } } \Bigg | _ { _ N } , B _ { _ S } = \frac { \lambda \alpha } { J \sqrt { \gamma } } \Bigg | _ { _ S } , B _ { _ W } = \frac { \lambda \alpha } { J \sqrt { \alpha } } \Bigg | _ { _ W } ,
$$

$$
B _ { _ { E } } = \frac { \lambda \alpha } { J \sqrt { \alpha } } \Bigg \vert _ { _ { E } } , B _ { _ { P 1 } } = \frac { \lambda \alpha } { J \sqrt { \alpha } } \Bigg \vert _ { _ { P } } , B _ { _ { P 2 } } = \frac { \lambda \alpha } { J \sqrt { \gamma } } \Bigg \vert _ { _ { P } }
$$

该离散格式根据调和平均推导得到，可更好地保证能量守恒，因此采用该格式离散基函数空间导数的低阶模型具有较高的精度(详见文献[12])。

# 4 算例分析

在冷热油交替输送管道的设计，以及运营方案的优化中需要对大量的工况进行热力数值模拟，直接数值模拟通常耗费时间较多，下面就以一个实际问题为例介绍采用POD低阶模型是如何快速求解这一类问题的。

两条管线pipe1 和 pipe2，为两条已经达到热力平衡的稳态运行输油管线，两条管线埋深、管径甚至钢管壁厚都有很大的差异，各项运行参数见表1。根据工程实际的要求，需将其中一条改为冷热油交替输送工艺，由于输送方案较多，计算量较大所以采用基于贴体坐标低阶模型来快速计算不同方案的热力规律，下文详细介绍了其实施步骤。

表1管线基本参数Table1Pipeline parameters  

<html><body><table><tr><td>管线</td><td>站间距</td><td>埋深</td><td>管径</td><td>壁厚</td><td>进站温度</td></tr><tr><td>pipe 1</td><td>108</td><td>1.3</td><td>0.711</td><td>0.010</td><td>50</td></tr><tr><td>pipe 2</td><td>108</td><td>0.9</td><td>0.457</td><td>0.006</td><td>30</td></tr></table></body></html>

为了说明低阶模型的精度和计算速度，选取众多方案中具有代表性的两个来对低阶模型进行测试：方案1更改pipe1为 $3 0 ^ { \circ } \mathrm { C }$ 和 $6 0 ^ { \circ } \mathrm { C }$ 交替输送，10小时交替一次，流速为 $1 \mathrm { m / s }$ ，在夏季进行更改，即式(5)中 $b { = } 2 0 , \mathsf { a } { = } \ 0 . 4$ ；方案2更改pipe2为 $2 0 ^ { \circ } \mathrm { C }$ 和$5 0 ^ { \circ } \mathrm { C }$ 交替输送，20小时交替一次，流速为 $2 \mathrm { m / s }$ ，在冬季更改，即式(5)中 $\mathsf { b } { = } { - } 2 0 , \mathsf { a } { = } { - } 0 . 4$ 。

首先进行取样。低阶模型的主要目的是计算冷热油交替输送时管道横截面的温度场，所以取样目的是为了获得管道横截面的温度场信息，各参数的取样值见表2和表3，取样时各样本从初场一直计算到稳态，时间步长为1200s，在初始阶段温度场变化剧烈时加大取样密度而在温度场变化缓慢的后期则应减小取样密度。由于取样只是针对一个管道的横截面进行数值计算而不是对一条管道的所有截面进行计算，所以取样付出的时间代价较小。

其次求取基函数。在获得样本矩阵之后采用快照法计算基函数,前8组基函数包含了基函数总能量的 $9 9 . 9 6 \%$ 。由于几何参数变化的影响，导致基函数中一些较重要的局部信息存在于后面能量贡献较低的基函数中，所以在POD低阶模型计算中，为了准确计算管道横界面的温度场，采用了前26个基函数来对其进行预测。

最后，将低阶模型应用于前述的两个测试方案中。采用FVM和POD低阶模型分别对这两种方案进行计算，二者采用的时间步长都是1200s，计算网格采用第2节所述网格，FVM的迭代方法和收敛标准也如前所述。

图3给出了方案1和方案2的新工艺在初期运行时，具有代表性的时刻原油沿程温度分布图。方案1需要30个小时才能将原来管中的油置换完全，而此时管内进口原油已经发生了两次交替；方案2只需15个小时就可以将整个管道内的原油置换完毕。无论是对于方案1还是方案2,POD低阶模型都表现出了较高的精度

通常情况下，我们最关心的是管道内原油的进站温度，为此图4分别给出了pipe1和pipe2在30天内进站温度随时间变化的曲线。从图中可以看出方案1和方案2中进站油温周期性变化，周期分别为10h和 $2 0 \mathrm { h }$ ，与出站油温的周期性变化一致。

表2冷热油交替输送管线横截面取样 Table2 Samples on the cross section of the pipeline   
表3冷热油交替输送取样表  

<html><body><table><tr><td>编 号</td><td>油温 /℃</td><td>油管换热系数 /W/(m².C)</td><td>空气温度 /℃</td><td>大气换热系数 /W/(m².C)</td><td>初 场</td><td>几何 形状</td></tr><tr><td>1</td><td>20</td><td>25</td><td>-5</td><td>10</td><td>空气温度为0℃，恒温</td><td></td></tr><tr><td>2</td><td>40</td><td>55</td><td>0</td><td>25</td><td>层温度为5℃的稳态温</td><td>Geo1,见表3</td></tr><tr><td>3</td><td>60</td><td>90</td><td>15</td><td>25</td><td>度场</td><td></td></tr><tr><td>4</td><td>20</td><td>25</td><td>-15</td><td>10</td><td>空气温度为0℃，恒温</td><td>Geo2,见表3</td></tr><tr><td>5</td><td>40</td><td>55</td><td>0</td><td>10</td><td>层温度为-5℃的稳态温</td><td></td></tr><tr><td>6</td><td>60</td><td>90</td><td>5</td><td>25</td><td>度场</td><td></td></tr><tr><td>7</td><td>20</td><td>25</td><td>15</td><td>25</td><td>空气温度为10℃，恒温</td><td></td></tr><tr><td>8</td><td>40</td><td>55</td><td>0</td><td>25</td><td>层温度为-5℃的稳态温</td><td>Geo3,见表3</td></tr><tr><td>9</td><td>60</td><td>90</td><td>-15</td><td>25</td><td>度场</td><td></td></tr></table></body></html>

Table 3 Samples for alternating transportation of cold and hot oi   

<html><body><table><tr><td></td><td>埋深 (m)</td><td>管径(m)</td><td>壁厚 (m)</td><td>结蜡层 (m)</td><td>防腐层 (m)</td></tr><tr><td>Geo1</td><td>1.5</td><td>0.8</td><td>0.007</td><td></td><td></td></tr><tr><td>Geo2</td><td>1</td><td>0.5</td><td>0.012</td><td>0.022</td><td>0.004</td></tr><tr><td>Geo3</td><td>1.3</td><td>0.6</td><td>0.09</td><td></td><td></td></tr></table></body></html>

![](images/1b17f08e186e8e3b91926f5aac9584667a643764cb366000da53a51efb29e3de.jpg)  
图3投产油温沿程分布图 Fig.3 Oil temperature distribution along pipeline during the commissioning process

![](images/6a5e1bd154a00c3ffadcd067ebc1016f49d602871312f2d6e5db797caead5c8b.jpg)  
图4进站温度随时间变化图  
Fig.4 Temperature at the inlet of the station

从图4中可以看出POD计算结果与FVM计算结果吻合良好，两种方案POD计算最大误差不超过$0 . 9 \mathrm { { ^ circ C } }$ ，平均误差分别为 $0 . 3 5 \mathrm { ^ \circ C }$ 和 $0 . 3 0 ^ { \circ } \mathrm { C }$ ，这个误差水平在输油行业是完全可以接受的。

为了更加形象的说明POD 低阶模型的计算精度，图5(a)和图5(b）分别给出了pipe1末端进站处在冷热油交替输送的第 5 天和 pipe2 末端进站处第30天时管道横截面温度场分布。

![](images/b1566ac39533ec081e7e15f5f2f320afcb5f0e9d35c2df32dac993b7a8598f70.jpg)  
图5进站处管道横截面温度分布图  
Fig.5 Temperature distribution on the cross section at the inlet

为了说明相比于直接数值模拟的FVM方法，POD低阶模型具有较高的速度优势，本文测算了在处理器为Inteli7CPU $@ 3 . 5 0 \mathrm { G H z }$ 的微型计算机上，两种方法计算所耗费的时间：对于方案1，FVM耗时3900s，采用POD耗时14.8s，POD计算速度为FVM263倍；对于方案2，FVM耗时2220s，采用POD耗时8.7s，POD计算速度为FVM255倍。需要注意的是，方案2的计算时间少于方案1，是由于方案2流速快，需要计算温度场的截面较少。假如工程中有200种方案（各参数不同取值的排列组合，通常这个数量较大）可供选择，如果采用FVM则大约需要耗费7天的计算时间，这在工程上是几乎不能承受的，而POD低阶模型则只需要 40分钟，这为工程上优化设计和运营都带来了极大的方便。

# 5结论

本文采用基于贴体坐标的非稳态导热POD低阶模型，基函数空间导数采用更符合其物理意义的格式离散，实现了对不同管径和埋深管道冷热油交替输送热力规律的快速计算。测试算例表明低阶模型具有较高的精度和健壮性，完全可以满足工程需求，且其计算速度在本文算例中为FVM方法的260倍左右。该快速计算方法的应用会大大加快工程中冷热油交替输送管道的优化设计、运营以及风险评估的速度。

参考文献   
[1] 崔秀国．冷热油交替输送管道非稳态水力热力耦合问题 分析及应用 [D].北京：中国石油大学(北京),2005   
CUI Xiuguo. Analysis and Application of Unsteady-State Hydraulic and Thermal Coupled Problems During Cold and Hot Oil Alternating Transportation [D]. Beijing: China University of Petroleum, 2005   
[2] 姚峰．西部原油管道冷热油交替输送方案研究 [D]．北 京：中国石油大学(北京),2006   
YAOFeng. Studyon Cold and Hot Oil Alternating Transportation Schemes for Western Crude Pipeline [D]. Beijing: China University of Petroleum,2006   
[3]宇波，徐诚，张劲军．冷热原油交替输送停输再启动研究 [J]．油气储运,2009,28(11):4-16   
YU Bo, XU Cheng, ZHANG Jinjun. Study on Restart of Crude Oils Batch Pipelined with Different Outlet Temperature[J]. Oil & gas storage and transportation, 2009,28: 4-16   
[4] Ravindran S S. Control of Flow Separation over a Forward Facing Step by Model Reduction [J]. Comput Method Appl M, 2002,191(41-42): 4599-4617   
[5] My-Ha D,Lim K M,Khoo B C,et al.Real Time Optimization Using Proper Orthogonal Decomposition: Free Surface Shape Prediction due to Underwater Bubble Dynamics [J]. Comput Fluids,2006,36(3): 499-512   
[6] Fogleman M, Lumley JL,Rempfer D, et al. Application of the Proper Orthogonal Decomposition to Datasets of Internal Combustion Engine Flows [J]. J Turbul, 2004, 5:1-18   
[7] Park H M,Lee WL. Feedback Control of Natural Convection [J].Comput Method Appl M,2001,191:1013-1028   
[8] DING Peng. Application of the Reduced Order Model in the on-line Control ofGlass Thickness and Solution of Heat Transfer Inverse Problems [D]. Xi'an: Xi'an Jiaotong University,2009 [9] 丁鹏，陶文钰．求解对流换热反问题的低阶模型[J].西安 交通大学学报，2009,43(3):14-16   
DING Peng，TAO Wenquan. Reduced Order Model Based Algorithm for Inverse Convection Heat Transfer Problem [J].J Xi'an Jiaotong Univ, 2009,43:14-16   
[10] HAN Dongxu,YU Bo, YU Guojun, et al. Study on a BFC-based POD-Galerkin ROM for the Steady-State Heat Transfer Problem[J].Int JHeat Mass Transf,2014,69:1-5   
[11] YU Bo, YU Guojun, CAO Zhizhu, et al. Fast Calculation of the Soil Temperature Field Around a Buried Oil Pipeline Using a Body-fitted Coordinates-Based POD-Galerkin Reduced-Order Model[J].Numer Heat TrA-Appl,2013,63:776-794   
[12] HAN Dongxu,YU Bo,ZHANG Xinyu. Study on a BFC-based POD-Galerkin Reduced-Order Model for the Unsteady-State Variable Property Heat Transfer Problem [J]. Numer Heat Tr B-Fund,Accepted.