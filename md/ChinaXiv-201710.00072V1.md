# 不同孔隙率圆形微针肋热沉流动及传热特性

杨宇辰　夏国栋　陈 卓　马丹丹(北京工业大学环境与能源工程学院，传热强化与过程节能教育部重点实验室，北京100124)

摘要本文利用CFD数值模拟软件对当量直径为 $2 0 0 ~ { \mu \mathrm { m } }$ 的不同孔隙率的叉排圆形微针肋热沉的流动和传热特性进行了数值模拟。模拟结果表明，随着雷诺数的增加，针肋尾部出现不同形态的涡。不同孔隙率的通道中，由于后排针肋的影响，针肋尾迹区的涡的形态、大小出现不同。对不同孔隙率的微针肋热沉，热流密度的变化对热沉的努塞尔数 $N u$ 的影响不同,孔隙率较小时热流密度对热沉的努塞尔数 $N u$ 影响不大，孔隙率较大时热流密度升高，热沉的努塞尔数 $N u$ 升高。

关键词数值模拟；微针肋；传热特性；流型分析中图分类号：TK124 文献标识码：A 文章编号:0253-231X(2017)08-1714-05

# Flow and Heat Transfer Characteristics Across Circular Shaped Micro Pin-fin Heat Sinks With Different Porosity

YANG Yu-Chen XIA Guo-Dong CHEN Zhuo MA Dan-Dan (The Education MinistryKeyLaboratoryofEnhanced Heat TransferandEnergy Conservation，ColegeofEnvironmentand Energy Engineering,Beijing University of Technology，Beijing 10ol24,China)

Abstract In this paper,by utilizing CFD,numerical simulations and analyses were used to research the flow and heat transfer characteristic in diffrent porosity staggered circular shaped micro pin-fin heat sinks whose hydraulic diameter is $2 0 0 ~ { \mu \mathrm { m } }$ .The results indicate that,with the increase of Reynolds number，vortexes with different structures are found in the pin fins wake zone. Under diferent porosity，the size and shape of vortexes are different due to the infuence of pin-fins at downstream. The influence on Nusselt number of the heat sinks caused by the change of heat flux is diferent under different porosity. There is barely influence on Nusselt number under smaller porosity when heat flux changes,while under larger porosity, the Nusselt number increases with the increase of heat flux.

Key wordsnumerical simulation; micro pin-fn; heat transfer characteristic; flow distribution analysis

# 0引言

随着微电子技术的快速发展，微流动系统在高热流密度微型器件及设备的散热中得到越来越广泛的应用。作为微流动系统的重要组成部分，微通道热沉因具有较好的强化传热效果，得到了国内外学者的广泛关注和研究，并发展出强化传热效果更好的微针肋热沉。Kosar 等[1-4]首先开展了微针肋热沉流动换热方面的工作，对微针肋热沉的摩擦系数的计算进行了研究，提出了适用于微针肋热沉的摩擦系数关联式。随后，用模拟和实验的方法，对不同形状、不同布置方式的微针肋热沉的传热与压降进行了研究，指出通过合理地设计微针肋热沉，可以在保持优越传热性能的基础上有效减小流动阻力，进而降低泵功消耗。周明正等[5]和夏国栋等[6分别对流体横掠水滴形微针肋热沉和菱形、长菱形微针肋热沉进行了实验研究，研究表明，在相同布置方式下，相对于圆形和菱形针肋，水滴形和长菱形针肋在设计上避免了尾涡滞留区的形成，具有较好的传热效果。由于在微电子设备的实际应用中，器件的发热量会随工作条件的变化而变化，对热沉的散热效果产生影响，因此一些研究人员也开始研究热流密度变化对热沉换热性能的影响。Guan 等[7-8]对不同热流密度下圆形针肋尾部旋涡的变化，以及热沉中边界层厚度的变化进行了研究，发现热流密度升高会使针肋尾迹区拉长，边界层减薄，壁面效应减弱，使热沉对流换热能力增强。

当前，对微针肋热沉的研究多集中在传热和压降特性方面，对不同排布方式下多圆柱绕流的对比研究还较少；同时，热流密度变化对不同排布方式的微针肋热沉的影响也不明确。因此，本文用数值模拟的方法，在不同热流密度下，对当量直径为200$\mu \mathrm { m }$ ，孔隙率为 $\varepsilon { = } 0 . 7 4 3$ 和 $\varepsilon { = } 0 . 8 3 6$ 的两种微针肋热沉中针肋扰流流场和传热特性进行了研究。

# 1数值模拟

# 1.1物理模型

考虑到两种微针肋热沉模型为对称结构，因此选取模型的一半作为模拟单元，模拟基本单元如图1所示，针肋正面结构如图2所示。针肋排布方式如表1所示。根据不同的针肋排布方式，两个圆形微针肋热沉的孔隙率分别为 $\varepsilon = 0 . 7 4 3$ 和 $\varepsilon = 0 . 8 3 6$ ，将两个微针肋热沉分别命名为SCP-0.743和SCP-0.836(其中S 代表叉排布置，C代表圆形，P代表针肋，数字代表孔隙率)。固体基板高 $H _ { 1 } { = } 0 . 1 5 ~ \mathrm { m m }$ ，加热面长$L { = } 1 0 \ \mathrm { m m }$ ，宽 $W { = } 1 . 7 6 ~ \mathrm { m m }$ ，针肋高 $H _ { 2 } { = } 2 0 0 ~ \mu \mathrm { m }$ ，前后各有 $3 \mathrm { m m }$ 的稳流区，不进行加热。

![](images/11ef482be4448243331047235c0a86dc3e1b6e70942d65fb4699366b1cc4f6bc.jpg)  
图1基本计算单元Fig.1 Basic computing elements

# 1.2控制方程

为简化计算，本文对模型做出如下假设：三维、稳态、无内热源层流流动和传热过程；工质黏度随温度变化按分段线性变化；忽略辐射和热损失作用。由假设可知，流体的连续性方程、动量方程和能量方程可简化为：

$$
\frac { \partial ( \rho u _ { i } ) } { \partial x _ { i } } = 0
$$

$$
\frac { \partial ( \rho _ { \mathrm { f } } u _ { i } u _ { j } ) } { \partial x _ { i } } = - \frac { \partial ( P ) } { \partial x _ { j } } + \frac { \partial } { \partial x _ { i } } \left[ \mu _ { \mathrm { f } } \left( \frac { \partial u _ { j } } { \partial x _ { i } } + \frac { \partial u _ { i } } { \partial x _ { j } } \right) \right]
$$

$$
\frac { \partial ( \rho _ { \mathrm { f } } u _ { i } c _ { p , \mathrm { f } } T ) } { \partial x _ { i } } { = } \frac { \partial } { \partial x _ { i } } \left( \lambda _ { \mathrm { f } } \frac { \partial T } { \partial x _ { i } } \right) +
$$

固体区域能量方程为：

$$
\mu _ { \mathrm { f } } \left[ 2 \left( { \frac { \partial u _ { i } } { \partial x _ { i } } } \right) ^ { 2 } + \left( { \frac { \partial u _ { j } } { \partial x _ { i } } } + { \frac { \partial u _ { i } } { \partial x _ { j } } } \right) ^ { 2 } \right]
$$

$$
{ \frac { \partial } { \partial x _ { i } } } \left( \lambda _ { \mathrm { s } } { \frac { \partial T } { \partial x _ { i } } } \right) = 0
$$

其中， $\rho _ { \mathrm { f } }$ 为流体密度, $c _ { p , \mathrm { f } }$ 为流体比热容， $\lambda _ { \mathrm { f } }$ 为流体导热系数， $\mu _ { \mathrm { f } }$ 流体运动黏度， $\lambda _ { \mathrm { s } }$ 为固体导热系数。

# 1.3边界条件

假设流体与固体接触面没有速度滑移。边界条件设置为：

入口：

$$
x = 0 , \quad u = u _ { \mathrm { i n } } , \quad v = 0 , \quad w = 0 , \quad T = T _ { \mathrm { i n } }
$$

出口：

![](images/0ad8525d3c980c65ef607dde30abd7e5433e326a023e17cb82981401a85cfe4e.jpg)  
图2微针肋热沉正面示意图 Fig.2 Diagram of the micro-pin fin heat sink

$$
x = L , \quad P = 0
$$

对称边界：

$$
\scriptstyle { \frac { \partial u } { \partial y } } = { \frac { \partial v } { \partial y } } = { \frac { \partial w } { \partial y } } = { \frac { \partial u } { \partial y } }
$$

底面加热面加以恒定热流：

$$
- \lambda _ { \mathrm { s } } \frac { \partial T } { \partial z } = q
$$

$$
u = u _ { \mathrm { i n } } , \quad v = 0 , \quad w = 0 , \quad \frac { \partial T } { \partial \overrightarrow { n } } = 0
$$

其他壁面均为绝热边界。

# 2模拟结果与讨论

# 表1针肋间距尺寸

Table 1 Dimension of pin fin spacing   

<html><body><table><tr><td>模型</td><td>ST/mm</td><td>SL/mm</td><td>SD/mm</td></tr><tr><td>SCP-0.743</td><td>0.44</td><td>0.28</td><td>0.36</td></tr><tr><td>SCP-0.836</td><td>0.44</td><td>0.44</td><td>0.49</td></tr></table></body></html>

# 2.1传热特性

$N u$ 数是表示对流换热强度的无量纲数，可由式(10)得出：

$$
N u = \frac { h d } { \lambda _ { \mathrm { f } } }
$$

其中， $h$ 为对流换热系数，W/ $( \mathrm { m } ^ { 2 } \cdot \mathrm { K } )$ ， $d$ 为当量直径，m。

由于在实际应用中，微型器件和设备的工作环境、条件和状态会发生变化，使得散热器的热负荷发生变化，因此本文研究了不同热流密度下微针肋热沉 $N u$ 数的变化情况。图3所示为SCP-0.743在底面热流密度分别为 $q { = } 4 { \times } 1 0 ^ { 5 } \ \mathrm { W / m ^ { 2 } }$ $8 { \times } 1 0 ^ { 5 } \ \mathrm { W / m ^ { 2 } }$ $1 . 2 { \times } 1 0 ^ { 6 } ~ \mathrm { W / m ^ { 2 } }$ 时， $N u$ 数与 $R e$ 数变化关系的曲线图。由图3中可以看出，相同热流密度下，随着 $R e$ 数的增大，Nu数也逐渐增大；相同Re数下，热流密度的升高，对 $N u$ 数影响不大。图4所示为 SCP-0.836 在底面热流密度分别为 $\scriptstyle q = 4 \times 1 0 ^ { 5 }$ $\mathrm { W / m ^ { 2 } }$ ， $\scriptstyle q = 8 \times 1 0 ^ { 5 }$ $\mathrm { W / m ^ { 2 } }$ ， $1 . 2 { \times } 1 0 ^ { 6 } ~ \mathrm { ~ W } / \mathrm { m } ^ { 2 }$ 时， $N u$ 数与 $R e$ 数变化关系的曲线图。从图4中可以看出，在相同 $R e$ 数下，随着热流密度升高，Nu数有较为明显的上升。由此可见，在相同 $R e$ 数下，对不同空隙率的微针肋热沉，热流密度对热沉 $N u$ 数的影响有较大区别。由于流体流型对热沉的传热特性有很大影响，因此，本文将研究不同孔隙率的微针肋热沉中流体流型随热流密度的变化，来分析流型可能对换热产生的影响。

![](images/4b3b96975ff8725a68d28a3d4c0c5f5173d21d1033f4f0d15b28fff4c7978902.jpg)  
图3SCP-0.743在不同热流密度下 $N u$ 数与 $R e$ 数关系Fig.3Variation of $N u$ with $R e$ in SCP-0.743

![](images/188ccf59f0900611bbe07dd3199cbac2952f29be5e3ba64e943ca2fa64b13777.jpg)  
图4SCP-0.836在不同热流密度下 $N u$ 数与 $R e$ 数关系Fig.4 Variation of $N u$ with $R e$ in SCP-0.836

# 2.2 流动特性

为方便观察通道中流体的流线图随 $R e$ 数和热流密度 $q$ 升高而变化的趋势，本文将通道沿流动方向，在入口、中段和出口处分别截取了相同长度的观察区域。图5为入口雷诺数 $R e _ { \mathrm { i n } } { = } 6 0$ ，热流密度$q { = } 4 { \times } 1 0 ^ { 5 } \mathrm { W / m ^ { 2 } }$ 时，热沉通道中流体的流线图。可以看出，在 $R e _ { \mathrm { i n } } { = } 6 0$ ，时，针肋尾部出现一对较小的旋涡。由于 SCP-0.743中后排针肋距前排针肋较 SCP-0.836的近，因此，针肋尾部的尾涡区范围较小。在针肋区出口处，由于SCP-0.743的通道最大流速（1.03$\mathrm { m } / \mathrm { s } )$ 比 SCP-0.836 的最大流速 $( 0 . 9 4 ~ \mathrm { m / s } )$ 大，SCP-0.743最后一排针肋的尾涡区明显长于SCP-0.836。

![](images/8cf80bab85238267532ebc8e3849827798ed103984628dde3cc311871ee4a470.jpg)  
图5 $R e _ { \mathrm { i n } } = 6 0$ ， $q = 4 \times 1 0 ^ { 5 } \ \mathrm { W / m ^ { 2 } }$ 时，通道中流体的流线图 Fig.5 Flow field in different heat sinks at

随着 $R e$ 数逐渐增大，针肋对流体的扰动加剧，出现不同形态的涡。如图6所示，可以观察到对称涡、单个涡、S型涡等。不同空隙率下，相同观察区域内的涡的形态也不同。

如图6(a)、(b)，当 $R e _ { \mathrm { i n } } { = } 1 0 0$ 时，在 SCP-0.743中可以观察到少量单个涡、S型涡的存在。而在SCP-0.836中只有对称涡存在。随着 $R e$ 数的增大，如图6(c)、(d)，当 $R e _ { \mathrm { i n } } { = } 1 6 0$ 时，SCP-0.743中出现单个涡、S型涡的范围增加。相同Re数下，SCP-0.836也开始出现单个涡、S型涡。如图6(e)、(f)，当 $R e _ { \mathrm { i n } } { = } 2 0 0$ 时，两种热沉中可以更加明显观察到不同形态的涡。出现这一现象的原因是，对于SCP-0.743，由于孔隙率较小，针肋排布较密，最大速度较大，扰动更加剧烈，相对于SCP-0.836，较小的 $R e$ 数下绕流针肋产生的扰动已不能被黏性力抑制，使对称的涡演变为单个涡、S型涡。随着Re数的增大，通道中最大速度的增加使流体的扰动加剧，能够更多的观察到针肋尾迹区的涡由对称涡变为单个涡或S型涡。

因此还需研究不同热流密度下流体在通道中流动时流型的变化。本文用数值模拟的方法，研究了相同$R e$ 数时，三种不同热流密度下通道内流体流型的变化情况。图7为SCP-0.743在 $R e _ { \mathrm { i n } } { = } 2 0 0$ 时，不同热流密度下流型的变化情况。对比图 $\mathrm { 7 ( a ) } \mathrm { \sim ( c ) }$ 可以看出，随着加热面热流密度的升高，针肋尾部涡发展的速率发生变化。以出口段为例，可以观察到随着热流密度的升高，尽管流体黏度减小，流体绕流针肋时黏滞力减弱，使壁面效应减弱，可以加强换热，但由于前后排针肋间距较小，对流体形成挤压，使涡的出现相对滞后，流体扰动的剧烈程度下降，削弱了换热能力。两因素的共同作用，使热流密度对 $N u$ 数的影响相对较小。图8为SCP-0.836在 $R e _ { \mathrm { i n } } { = } 2 0 0$ 时，不同热流密度下流型的变化情况。同样以出口段为例，可以观察到随着热流密度上升，流体温度上升，黏度下降，流体绕流针肋时黏滞力减小，使流体绕流针肋时涡生成的速率加快，意味着流体扰动的加强，增强了流体混合，加强了对流换热，因此 $N u$ 数随热流密度升高而有相对明显的升高。

![](images/70c33719a0538f9a156d10ce3ea5c7b0084641b8bfa9292185683cfc6e946cc0.jpg)  
图6不同Re数下流形的变化情况：Fig.6 Flow field under different Re number:

$R e _ { \mathrm { i n } } { = } 1 0 0$ ， $7 \ \mathrm { m m } { \leqslant } L { \leqslant } 8 . 9 6 \ \mathrm { m m }$ ,(a) SCP-0.743,(b) SCP-0.836;  
$R e _ { \mathrm { i n } } { = } 1 6 0$ $3 . 6 4 ~ \mathrm { m m } { \leqslant } L { \leqslant } 5 . 6 ~ \mathrm { m m }$ ,(c) SCP-0.743,(d) SCP-0.836;  
$R e _ { \mathrm { i n } } { = } 2 0 0 , 3 . 0 8 \ \mathrm { m m } { \leqslant } L { \leqslant } 5 . 0 4 \ \mathrm { m m }$ (e) $\mathrm { S C P - } 0 . 7 4 3$ ，(f) SCP-0.836;

由于在实际应用中散热器的热负荷会发生变化，

![](images/8e6a59bd000bd8f99004236688aa9f02cc4a27072a65d97f14dc03a54019c3aa.jpg)  
图7SCP-0.743热沉中流型随热流密度变化情况： Fig.7Variationof flow field withheat fluxin SCP-0.743

![](images/7958bce0e88b428e375fd68516b1be106933809a3a20531081519f9ff429037c.jpg)  
图8SCP-0.836热沉中流型随热流密度变化情况： Fig.8 Variation of flow field with heat flux in SCP-0.836

# 3结论

本文借助CFD模拟软件，用数值模拟的方法对当量直径为 $2 0 0 ~ { \mu \mathrm { m } }$ 、孔隙率为 $\varepsilon = 0 . 7 4 3$ 和 $\varepsilon = 0 . 8 3 6$ 的两个微针肋热沉的传热和流动特性进行了研究。通过分析模拟结果得出了以下结论：

1）不同孔隙率下，热流密度对热沉对流换热性能的影响不同。孔隙率较大时，随着热流密度上升，热沉的 $N u$ 数有较为明显的上升；孔隙率较小时，热流密度对热沉 $N u$ 数几乎没有影响。

2) $R e _ { \mathrm { i n } } { = } 6 0$ 时，针肋的尾部可以形成一对对称的涡。当 $R e$ 数继续上升，流体绕流产生的扰动已不能被黏性力抑制，在针肋尾部出现对称涡、单个涡、S型涡等不同形态的涡。随着 $R e$ 数继续增大，单个涡、S型涡出现的更多。孔隙率小的微针肋热沉中更容易出现不同形态的涡。

3)不同孔隙率下，热流密度对流型的影响有区别。孔隙率为0.743时，热流密度升高会使针肋尾部的涡滞后形成，流体扰动减弱，抵消了部分流体黏度降低、壁面效应降低带来的强化传热效果。孔隙率为0.836时，随着热流密度升高，针肋尾部的涡加速形成，加强了通道内流体的混合和扰动，带来相对较为明显的强化传热效果，Nu数有所提升。

# 参考文献

[1]Kosar A,Mishra C,Peles Y.Laminar Flow Across a Bank ofLow Aspect Ratio Micro Pin Fins [J].Journal of Fluids Engineering,2005,127(3):419-431   
[2]Kosar A，Peles Y.Thermal-hydraulic Performance of MEMS-based Pin Fin Heat Sink [J].Heat Transfer, 2006, 128:121-131   
[3] Kosar A，Peles Y.Micro Scale Pin Fin Heat SinkParametric Performance Evaluation Study[J].IEEE Transaction on Components and Packaging Technologies, 2007,30(4): 855-865/69   
[4] Izci T,Koz M,Kosar A.The Effect of Micro Pin-Fin Shape on Thermal and Hydraulic Performance of Micro Pin-Fin Heat Sinks [J].Heat Transfer Engineering,2015, 36(17): 1447-1457   
[5]周明正,夏国栋,柴磊,等.流体横掠水滴形微针肋热沉流动 和传热特性[J].航空动力学报，2012,27(12)：2681-2686 Zhou Mingzheng,Xia Guodong,Chai Lei,et al. Flow and Heat Transfer Characteristics of Drop-shaped Micro Pinfin Heat Sinkswith Cross Flow[J],Journal of Aerospace power,2012,27(12):2681-2686   
[6]夏国栋,崔珍珍,翟玉玲,等.长菱形微针肋热沉的流动与换 热特性[J].中国石油大学学报,2014,38(2)：130-134 Xia Guodong，Cui Zhenzhen,Zhai Yuling,et al．Flow and Heat Transfer Characteristics for Long-diamond Shaped Micro Pin Fin [J],Journal of China University of Petroleum,2014,38(2):130-134   
[7]Guan Ning,Luan Tao,Liu Zhigang,et al.Vortex Distribution and Mixed Convection of Liquid Flow Across Micro-cylinders in a Rectangular Channel [J].Heat Mass Transfer,2016,52:657-670   
[8]Guan Ning,Luan Tao,Jiang Guilin,et al．Influence of Heating Load on Heat Transfer Characteristics in Micropin-fin Arrays [J].Heat Mass Transfer,2016,52:393-405