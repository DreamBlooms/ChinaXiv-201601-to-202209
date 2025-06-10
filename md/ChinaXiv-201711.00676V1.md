编号：2016-0199

# 基于水平衡的PEM燃料电池大电流运行优化控制

何晓波1,² 詹志刚1² 张洪凯²帅露」 隋邦杰3,4 徐立²

（1．武汉理工大学，材料复合新技术国家重点实验室，武汉4300702.武汉理工大学，能源与动力工程学院，武汉4300633．武汉理工大学，汽车工程学院，武汉4300704．加拿大维多利亚大学，机械系集成能源系统实验室，加拿大，B.C.省，维多利亚市)

摘 要：质子交换膜燃料电池(PEMFC)水管理是影响其性能的主要因素之一。本文针对大电流运行的PEM燃料电池，提出了一种基于MEA水平衡的温度控制方法。在一定的操作压力和过量系数下，得到了基于无净电拖的PEM 电池水平衡温度，并通过三维模拟对无净电拖水平衡温度进行修正，获得了基于电池最优性能的操作温度；电池实际的操作温度控制，可以以无净电拖水平衡温度线为基础，加上一个修正量，使电池在性能良好区域运行。这种电池操作温度的控制算法简单，对电池的设计与操作优化具有参考意义。

关键词：质子交换膜燃料电池；膜电极；水平衡；优化；温度控制中图分类号：TK91 文献标识码：A

# The Optimal Control of PEM Fuel Cell Operating at Large Current Density

# Based on WaterBalance

HE Xiao-Bo 1.² ZHAN Zhi-Gang1,² ZHANG Hong-Kai ² SHUAI Lu1SUI P.C.3,4 XU Li² (1.StateKeyLaboratoryofAdvancedTechnologyforMaterialsSynthesisandProcessing,WuhanUniversityofTechnologyWuhan

430070,China

2.School of Power and Energy Engineering,Wuhan University of Technology, Wuhan 43O070,China

3.School ofAutomotive Engineering,Wuhan University of Technology, Wuhan 430070, China

4.InstituteforIntegratedEnergySystemsandDepartmentofMechanicalEnginering,UniversityofVictoria,VictoriaBCCaada)

Abstract: The water management of Proton Exchange Membrane Fuel Cell (PEMFC) is one of the key factors affecting its performance. In this paper,a temperature control method based on MEA water balance was put forward for PEMFC operated at large current density. For a determined operating pressure and stoichiometry, the water balance temperature of PEMFC was acquired based on no net drag,and was modified through the three dimensional simulation,by which atemperature was obtained based on the optimal operating performance of the fuel cellThe actual temperature control ofPEMFC can be carred out according to the water-balance temperature without net drag modified with an amount,which helps fuel cels run in an area with high performance. The algorithm of this temperature control is simple, it may be will helpful for the optimal design and operation of PEMFC.

Key words: PEM fuel cel; Membrane electrode; Water balance; Optimization; Temperature control

# 0引言

质子交换膜燃料电池(Proton ExchangeMembraneFuelCell,PEMFC)是一种通过电极反应直接将储存在 $\mathrm { H } _ { 2 }$ 中的化学能转化成电能的装置。它因具有能量转换效率高、噪音低、无污染、启动迅速、比功率大等优点而备受各国青睐。为了满足狭窄空间及复杂工况的车用需求，PEMFC电性能、功率密度与耐久性不断提升，成本持续下降。

2013年11月，英国 Intelligent Energy 宣布实现了迄今最高的汽车燃料电池功率密度，其体积功率密度和质量功率密度分别达到了 $3 . 7 \mathrm { k W / L }$ 和$2 . 5 \mathrm { k W / k g ^ { [ 1 ] } }$ 。日本丰田汽车公司 2014 年推出了MIRAI燃料电池汽车，其电堆质量功率密度和体积功率达到 $3 . 1 \mathrm { k W / L }$ 和 $2 . 0 \mathrm { k W / k g } ^ { [ 2 ] }$ 。电池堆在大功率下运行，一般需要增加背压，以提高反应气体浓度；

同时电流密度往往也较高，可能高达 $1 . 0 { - } 2 . 0 \mathrm { A } / \mathrm { c m } ^ { 2 }$ 。因此生成水较多，如果合理利用生成水,可以简化加湿系统，因此增加操作压力、阴极无加湿、大电流密度运行的燃料电池电堆成为发展趋势[3.4]。

燃料电池应用于车辆动力系统时，控制策略是决定其能否高效、持久、稳定运行的关键因素之一，而优化的控制策略取决于对电池堆运行状态的有效识别，其中膜电极(MEA)含水状态的准确辨识非常重要[5]，然而又极其困难。

Yuan[]、Jang[7]、丁靖[8]等通过模拟和实验的方法，探索了电池最优运行性能时的工作温度、气体加湿度、运行压力、流场结构等参数；Kanani[9]、Damour [10]等分别提出了基于 Response SurfaceMethodology和Flatness-basedApproach的控制模型，以调节电池运行操作条件。 $\mathrm { { H u } } ^ { [ 1 1 ] }$ 、Cheng[12]等利用基于模型的方法以调节、控制燃料电池膜电极水淹状态(阳极purge方式)和运行温度，并将其应用到实际的巴士燃料电池系统中。但模型的准确性、特别是膜电极水淹模型的可靠性，将影响电池是否可以高效稳定运行。

Shaul[13]认为阴阳极气体无加湿而依赖生成水润湿质子交换膜,操作电池是可能的，并提出了相应的准则条件；Janssen[14]等实验研究了操作条件对净电拖系数的影响，认为净电拖系数受电流密度等参数的影响很小，在阴极不加湿、阳极加湿的条件下，该值几乎为常数，并且电化学反应生产的水几乎全部被阴极反应气体带走。基于此，Berming[15,16]探索了阴阳极进口气体不加湿、出口气体刚好达到饱和的理想状态水平衡问题，提出利用阴、阳极出口气体露点温度对燃料电池运行参数进行控制的方法，但他们自己发现这样的控制方式可以使膜电极达到水平衡，却不能获得最优的电池性能，且气体过量系数受到严格约束。

鉴于此，针对PEM电池大电流运行、阴极不加湿、阴阳极加背压运行工况，本文建立电池内部水平衡零维模型，获得不同背压条件及过量系数下无净电拖的水平衡温度；然后考虑了净电拖系数较小的情况，得出净电拖系数修正的水平衡点温度；最后通过三维模拟，考虑电拖、液态水因素的影响，以电池性能最优为目标，对水平衡温度进行修正，获取相应工况下的最佳操作条件。

# 1电池水传输零维模型

图1是PEM电池水传输过程。

![](images/53f067f5f888b7f1566a2e6a4d955d23602c23cd9f6db1b98b17fb35bf4b8ba6.jpg)  
图1PEM电池水传输过程

Fig.1The process of watertransport inPEMFuel Cell:(a)water transport in the Fuel Cell,(b)water transport in membrane.

在稳态的情况下，电池阴阳极进、出流道的水及反应生成的水有如下关系：

$$
q _ { w - c a t } ^ { i n } + q _ { w - a n } ^ { i n } + q _ { w - p r o d } = q _ { w - c a t } ^ { o u t } + q _ { w - a n } ^ { o u t }
$$

阴极进口水量：

$$
q _ { w - c a t } ^ { i n } = d _ { a i r } \cdot q _ { a i r } ^ { i n }
$$

$$
d _ { a i r } = 0 . 6 2 2 \frac { p _ { \nu } ( T _ { h u m } ) } { p _ { b } - p _ { \nu } ( T _ { h u m } ) } \ , q _ { a i r } ^ { i n } = \frac { S _ { c } } { x _ { o _ { 2 } } } \frac { i } { 4 F } M _ { a i r } \nonumber
$$

阳极进口水量：

$$
q _ { w - a n } ^ { i n } \ = d _ { H _ { 2 } } \cdot q _ { H _ { 2 } } ^ { i n }
$$

$$
d _ { { \scriptscriptstyle H _ { 2 } } } = 8 . 9 3 6 \frac { p _ { \nu } ( T _ { h u m } ) } { p _ { b } - p _ { \nu } ( T _ { h u m } ) } \ , q _ { { \scriptscriptstyle H _ { 2 } } } ^ { i n } = S _ { a } \frac i { 2 F } M _ { { \scriptscriptstyle H _ { 2 } } }
$$

阴极出口水量：

$$
q _ { w - c a t } ^ { o u t } = ( \frac { S _ { c } } { x _ { o _ { 2 } } } - 1 ) M _ { H _ { 2 } O } \frac { i } { 4 F } \frac { p _ { \nu } ( T _ { c e l l } ) } { p _ { b } - p _ { \nu } ( T _ { c e l l } ) }
$$

阳极出口水量：

$$
q _ { w - a n } ^ { o u t } = ( S _ { H _ { 2 } } - 1 ) M _ { H _ { 2 } O } \frac { i } { 2 F } \frac { p _ { \nu } ( T _ { c e l l } ) } { p _ { b } - p _ { \nu } ( T _ { c e l l } ) }
$$

生成水：

$$
q _ { { \bf \psi } _ { w - p r o d } } = \frac { i } { 2 F } M _ { { \bf \psi } _ { H _ { 2 } o } }
$$

设水从阳极流向阴极为正，则膜中水的净电拖量：

$$
q _ { w - m e m } = r _ { d } \frac { i } { F } M _ { H _ { 2 } o } = q _ { E O D } - q _ { b a c k } - q _ { p r e s s }
$$

由此既保持阴阳极水平衡，又使得膜获得润湿。其中, $q _ { w - c a t } ^ { i n }$ 为阴极进口水量； $\boldsymbol { q } _ { \scriptscriptstyle { w - a n } } ^ { \scriptscriptstyle { i n } }$ 为阳极进口水量； $q _ { w - p r o d }$ 为阴极 MEA 生成水量； $q _ { w - c a t } ^ { o u t }$ 为阴极出口水量； $\boldsymbol { q } _ { w - a n } ^ { o u t }$ 为阳极出口水量； $q _ { w - m e m }$ 为膜中水的净通量； $q _ { b a c k }$ 为浓差反扩散量； $q _ { \scriptscriptstyle E O D }$ 为电渗拖拽量; $q _ { \mathit { p r e s s } }$ 为压差扩散量； $r _ { d }$ 为净电拖系数; $d _ { a i r }$ 为空气的含湿量； $d _ { { \scriptscriptstyle H _ { _ { 2 } } } }$ 为空气的含湿量； $p _ { _ { \nu } } ( T _ { h u m } )$ 为加湿温度为 $T _ { h u m }$ 时，进口的水蒸气分压，kPa;$p _ { \nu } ( T _ { c e l l } )$ 为电池温度为 $T _ { c e l l }$ 时，出口的水蒸气分压;$p _ { b }$ 为操作压力； $S _ { c }$ 为阴极空气过量系数； $S _ { a }$ 为阳极氢气的过量系数； $\boldsymbol { M } _ { { H _ { 2 ^ { o } } } }$ 为水的摩尔质量，18$\mathbf { k g } / \mathrm { k m o l }$ ； $M _ { a i r }$ 为空气的摩尔质量， $2 8 . 8 \ \mathrm { k g / k m o l }$ ：$\boldsymbol { M } _ { H _ { 2 } }$ 为氢气的摩尔质量， $2 ~ \mathrm { k g / k m o l }$ ; $\boldsymbol { x } _ { o _ { 2 } }$ 为氧气在空气中占的体积分数，一般取1/5； $i$ 为电流密度，$\mathrm { A } / \mathrm { c m } ^ { 2 }$ ; $F$ 为法拉第常数 $9 6 4 8 7 \mathrm { ( C / m o l ) } .$ 0

# 2 阴极无加湿MEA水平衡

针对本文研究工况，阴极气体无加湿，则qc-in =0。根据 Janssen 等的研究结论，经过电拖、反扩散以及压力扩散引起的穿过膜的总体水通量，也即净电拖量，和生产水量比较小许多[14]，因此利用阴极气体带走生产水、使其出口达到饱和状态而保障膜电极中没有多余水的存在是可能的[13]。但另一方面，这种水平衡使膜容易偏干，电池性能并非最佳[15]；电池性能达到最佳时，MEA 阴极侧往往存在少量液态水，使膜的润湿状态最好[]。阴极侧液态水由生成水和净电拖水中的部分凝结而成，随后在毛细压力驱动下排出到流道，因此阴极出口处气体为过饱和态。

# 2.1无净电拖的MEA水平衡

假设电池阴阳极间净电拖量为0，即阴阳极之间没有水传输；生成水与阴极出口水量差值为 $\Delta q$ ，则：

$$
\begin{array} { l } { { \Delta q = q _ { w - p r o d } - q _ { w - c a t } ^ { o u t } } } \\ { { \displaystyle ~ = \frac { i } { 2 { \cal F } } M _ { H _ { 2 } o } - ( \frac { S _ { c } } { x _ { o _ { 2 } } } - 1 ) M _ { H _ { 2 } O } \frac { i } { 4 { \cal F } } \frac { p _ { \nu } ( T _ { c e l l } ) } { p _ { b } - p _ { \nu } ( T _ { c e l l } ) } } } \end{array}
$$

根据Clausius-Clapeyron方程，水蒸气饱和分压与温度的关系为[17].

$$
\log _ { 1 0 } p _ { s a t } = 2 6 . 2 0 9 3 6 8 - { \frac { 2 9 6 0 . 9 6 } { T } } - 5 . 1 6 4 9 \log _ { 1 0 } T 
$$

其中, $p _ { s a t }$ 为温度 $T$ 对应的饱和水蒸汽的压力。

图2、3是阴极过量系数为2.5，操作压力分别为 $2 0 0 \mathrm { { k P a } }$ 和 $1 0 0 \mathrm { { k P a } }$ 时， $\Delta q$ 随温度、电流密度的变化关系。从图中可以看出：对同一操作压力， $\Delta q$ 随着温度升高而减小至0，之后为负值，且其绝对值随电流密度的增加而增加。 $\Delta q { = } 0$ ，即生成水量全部被阴极干气体带走，并在出口处达到饱和，该点称作MEA水平衡点，其对应的温度为水平衡温度。压力为 $1 0 0 \mathrm { { k P a } }$ 时，其平衡点的温度为 $5 4 . 3 ^ { \circ } \mathrm { C }$ ；压力为$2 0 0 \mathrm { { k P a } }$ 时，其平衡点的温度为 $6 9 . 5 9 ^ { \circ } \mathrm { C }$ ；压力为$3 0 0 \mathrm { { k P a } }$ 时，平衡温度为 $7 9 . 3 3 ^ { \circ } \mathrm { C }$ 。值得注意的是，平衡点的温度值与电流密度无关，只与压力和过量系数有关。在操作温度小于平衡点温度时，△q均为正值，说明生成水除了被饱和空气带走后，MEA中还有多余的水以液态水形式存在，且随着电流密度的升高而增大；当操作温度大于平衡点温度时， $\Delta q$ 为负值，说明生成水被全部带走后，还需要额外的水来补充，会导致MEA失水，在实际电池运行时，额外的水主要来自加湿水和阳极电拖水，且随着电流密度的升高而所需的额外水也增加。

图4是过量系数 $S _ { c } { = } 2 . 5$ ，温度为 $7 0 ^ { \circ } \mathrm { C }$ 时， $\Delta q$ 随电流密度、操作压力的变化关系。从图中可以看出，$\Delta q$ 随着压力升高而增加，说明升高压力留在MEA中的剩余水变多，气体携水能力下降；当压力为$2 0 0 \mathrm { { k P a } }$ 时， $\Delta q$ 几乎为零，且与电流密度无关，这与图2压力为 $2 0 0 \mathrm { { k P a } }$ 时，平衡点温度为 $6 9 . 5 9 ^ { \circ } \mathrm { C }$ 的结论一致。

![](images/6d529dd6b6509f0fb9aef19ea1a785ffdc4d1259502c327b4aa21dde68038d09.jpg)  
图2 $p _ { b } { = } 2 0 0 \mathrm { k P a }$ ， $\Delta q$ 随操作温度的变化，平衡点温度 值 $6 9 . 5 9 ^ { \circ } \mathrm { C }$

Fig. 2 The water difference $\Delta q$ versus operating temperature under the operating pressure of $2 0 0 \mathrm { { k P a } }$ . The water-balance temperature is $6 9 . 5 9 ^ { \circ } \mathrm { C }$ ：

![](images/40259c1c966bb8d718f5482d6413e9e65301ca273bb9d019a24745f0c79f955b.jpg)  
图3 $p _ { b } { = } 1 0 0 \mathrm { k P a }$ ， $\Delta q$ 随操作温度的变化，平衡点 温度值 $5 4 . 3 ^ { \circ } \mathrm { C }$ Fig. 3 The water difference $\Delta q$ versus operating temperature under the operating pressure of $1 0 0 \mathrm { { k P a } }$ .Thewater-balance temperature is $5 4 . 3 ^ { \circ } \mathrm { C }$ ：

![](images/aa69f5e38c0a23c162e94e07174290cc42fe51a7fd62d8c4cbde4a75da99a798.jpg)

目前常用的燃料电池阴极气体过量系数 ${ \cal S } _ { c } = 2$ 、2.5、3，而操作压力 $p _ { b }$ 则多在 $1 0 0 { \sim } 3 0 0 \mathrm { k P a }$ 之间。这些操作参数下对应的MEA水平衡温度变化规律，如下图所示：

![](images/936ed48a1001f210fef79ee52c2246486310e7dc7d654750d209a1165d61fc20.jpg)  
图4 $\scriptstyle T _ { \mathrm { c e l l } } = 7 0 ^ { \circ } \mathrm { C }$ ， $\Delta q$ 随电流密度的变化 Fig. 4 The water difference $\Delta q$ versus current density under the operating temperature of $7 0 ^ { \circ } \mathrm { C }$   
图5不同操作压力及过量系数下的水平衡温度 Fig.5 The water-balance temperature under different operating pressure and cathode stoichiometry

从图5中可知，随着操作压力的升高，水平衡温度升高；随着阴极过量系数的增加，水平衡温度降低。这说明对于一定的操作压力，增加过量系数后，不需要提高温度便可以使气体容纳水气能力提升，而当过量系数一定时，增加操作压力，会使气体容纳水气能力减弱。

通过上述方程能较为简单的获得一定操作条件下的平衡温度，算法简单。但在平衡温度线上运行，膜偏干，电池性能并非最佳[15]。

# 2.2考虑净电拖的MEA水平衡

在阴极无加湿、阳极加湿的条件下，净电拖量很小 $( 0 < r _ { d } \le 0 . 1 ) ^ { [ 1 4 ] }$ ，即从阳极电拖过来的水，大多数又通过反扩散回到了阳极；对于本文考虑的15微米厚的nafion膜，更是如此，这是图5作为露点温度法(也即平衡点温度)控制电池水平衡的理论依据。然而，如前所述，平衡点温度控制会使得膜偏干[15]；为使膜润湿最佳，电池达到最优性能，膜电极中应该有适量的液态水，因此需对图5中的平衡温度进行修正。为此考虑少量净电拖水和凝结水对电池总体水平衡的影响。

为考虑净电拖对水平衡的影响，设 $q _ { w - m e m }$ 为净电拖水，净电拖水加上生成水被阴极出口气体带走，则方程(10)变成：

$$
q _ { _ { w - p r o d } } + q _ { _ { w - m e m } } = q _ { _ { w - c a t } } ^ { _ { o u t } } + \Delta q
$$

![](images/f478905d57f9f8328a3c8a8483efa8f8a4ed8a215b1ae46aa7270712d7a5d1be.jpg)  
图6 $S _ { c } { = } 2 . 5$ ， $p _ { b } { = } 3 0 0 \mathrm { k P a }$ ， $\Delta q$ 随净电拖的变化，平衡点温度值 $7 9 . 3 3 ^ { \circ } \mathrm { C } / 8 1 . 3 6 ^ { \circ } \mathrm { C } / 8 3 . 2 ^ { \circ } \mathrm { C }$

Fig. 6 The water difference $\Delta q$ versus net drag coefficient under the operating pressure of $3 0 0 \mathrm { { k P a } }$ and cathode stoichiometry of 2.5.The water-balance temperature is $7 9 . 3 3 ^ { \circ } \mathrm { C } / 8 1 . 3 6 ^ { \circ } \mathrm { C } / 8 3 . 2 ^ { \circ } \mathrm { C } \circ$ （20

根据Janssen 等[14]的研究，净电拖系数分别取0.05和0.1，图6为 $\Delta q$ 随净电拖系数的变化。由于净电拖为正值，即水被质子从阳极带到阴极，因此

要让这部分多余的水随同生成水一起被阴极气体带走，需要更高的温度，即净电拖系数为0.05和0.1时的水平衡温度分别为 $8 1 . 3 6 ^ { \circ } \mathrm { C }$ 和 $8 3 . 2 ^ { \circ } \mathrm { C }$

# 2.3基于最优性能的MEA水平衡

前述考虑净电拖为正值、基于露点的MEA水平衡温度控制，更容易导致质子交换膜偏干，润湿没有到达最佳状态，因此电池性能不是最优。为此，本文针对所研究的问题，利用流体动力学软件Fluent进行三维模拟，获得电池性能最优时的操作温度。模拟的主要结构参数及操作条件如下表，因篇幅所限，热质传输方程、电化学方程及具体的物性参数、电化学参数见。

表1主要的结构参数及操作条件  
Table1 The main geometric parameters and operating conditions   

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>流道长度；宽度；深度/(mm)</td><td>50；1.0；0.4</td></tr><tr><td>极板厚度/(mm)</td><td>0.1</td></tr><tr><td>膜厚度；CL 厚度；GDL 厚度/(mm)</td><td>0.015；0.01；0.2</td></tr><tr><td>阴极气体过量系数Sc</td><td>2.5</td></tr><tr><td>阳极气体过量系数Sa</td><td>1.5</td></tr><tr><td>操作压力(绝对压力)Pb/(kPa)</td><td>100~300</td></tr><tr><td>电池温度Tcel/(C)</td><td>50~90</td></tr><tr><td>阴极进口气体相对湿度Rhc/(%)</td><td>0</td></tr><tr><td>阳极进口气体相对湿度Rha/(%)</td><td>100</td></tr><tr><td>电流密度i(A/cm)</td><td>1.0~2.0</td></tr></table></body></html>

图7和图8显示了模拟获得的最优性能温度(左侧虚线)，其过量系数为2.5，操作背压分别为 $1 0 0 \mathrm { { k P a } }$ 和 $3 0 0 \mathrm { { k P a } }$ 。图7中电池平衡温度为 $5 4 . 3 ^ { \circ } \mathrm { C }$ ，不受电流密度的影响，电池在此温度下运行时生成水刚好被阴极气体带走且在出口保持饱和状态，但实际最佳运行温度大约在 $4 7 . 7 ^ { \circ } \mathrm { C }$ 左右(电流密度变化此温度稍有不同)，此时MEA阴极侧有少量液态水生成，但膜的润湿良好，考虑氧气传输和膜导电性，电池性能最佳，尽管此时阴极出口气体是过饱和的。低于此温度运行，MEA会产生较严重的水淹；高于此温度运行，膜的润湿逐渐变干。图8中MEA水平衡分区类似，只是电池最佳性能温度和水平衡温度非常接近，也即在较高背压下运行时，阴极气体携带水的能力降低，电池温度稍微低于平衡温度就可以使得膜得到较好的润湿，这与图4规律也是相符的。

![](images/5bd07204f4b370a5ad69987d8edaf27cb03d2ee73f1acb6999eb09bee217a543.jpg)  
图 $7 \ : S _ { c } { = } 2 . 5$ ， $p _ { b } { = } 1 0 0 \mathrm { k P a }$ ，基于模拟的电池性能分区 Fig.7 Different operating areas of fuel cell performance under the pressure of $1 0 0 \mathrm { { k P a } }$ and cathode stoichiometryof2.5 based on simulation.

![](images/96901a9eab66d2d8427764e6fc9d1ec8703a213533e55cf7aca1cb781c194b74.jpg)  
图8 $S _ { c } { = } 2 . 5$ ， $p _ { b } { = } 3 0 0 \mathrm { k P a }$ ，基于模拟的电池性能分区 Fig.8Different operating areas of fuel cell performance under the pressure of $3 0 0 \mathrm { { k P a } }$ and cathode stoichiometry of 2.5 based on simulation.

BerningT.等提出以平衡点温度作为电堆运行温度的控制方法[14-16],不管是否考虑净电拖，膜都是偏干的。本文基于现有传质传递及电化学模型，寻找最优性能工况，但考虑如下因素：(1)目前的模型并非完美，因此得到的结果与实际可能有偏差；(2)电堆内部温度等物理量空间分布不均，严格要求以某一点温度值作为控制值实用意义不大； (3)电堆及膜电极材料和结构变化，则最优性能线也会偏移；(4)控制系统本身的误差，因此本文提出了保持电堆性能良好的工况运行区域，而非以计算获得的最优性

能线作为控制工况。

图9是阴极气体过量系数为2.5时，模拟修正的电池性能最优温度和无净电拖的水平衡点温度，由图可知：电池最优性能的操作温度低于水平衡温度。由此得到燃料电池操作的温度范围，在性能最优温度线之下运行，电池将发生水淹；在该线及水平衡点温度线之间运行，电池性能良好；在平衡温度线之上运行电池则偏干。实际电池操作温度控制，可以以无净电拖温度平衡线为基础，加上一个修正量，使电池在性能良好区域运行，这种控制算法简单。

![](images/3e6c056643d03be83190623234a80ce0e75f7e4e1bae163a235ac1966f0c3e47.jpg)  
图9模拟修正的电池性能最优温度和水平衡点温度(阴极气体过量系数 $S _ { c } { = } 2 . 5$ ）  
Fig.9The optimal temperature of the simulated modify and the water balance temperature (The cathode gas stoichiometry $S _ { c } { = } 2 . 5$ ）

# 3结论

本文研究了PEMFC在大电流运行条件下电池水传输及平衡特征，提出了一种基于MEA水平衡的温度控制方法。因反应生成水可以利用，故采用阴极不加湿，阳极加湿(模拟循环加湿)、有背压。获得的主要结论如下：

(1)在确定的操作压力和过量系数下，基于无净电拖的 MEA电池存在一个平衡温度，它与电流密度无关，此时生产的水刚好被阴极出口空气带走，运行温度大于此平衡温度，MEA将处于失水状态；运行温度低于此平衡温度，MEA可能部分水淹。背压增加，该平衡温度随之增加；阴极气体过量系数增加，该平衡温度降低。

(2)基于无净电拖平衡温度算法简单，但以此控制电池的操作温度，将使得膜偏干。

(3)经过三维模拟对无净电拖平衡温度进行修正，获得了基于电池最优性能的操作温度；随着操作压力的增加，最优性能温度和无净电拖平衡温度逐渐接近。电池在最优温度线上运行，MEA部分水淹，但考虑到膜润湿和氧气传输的综合效果，电池具有最佳性能；在最优温度线以下运行，MEA会发生较严重水淹；在最优温度线和水平衡温度线之间运行，电池性能较好；在水平衡温度线之上运行，膜偏干，电池性能较差。

(4)实际电池操作温度控制，可以以无净电拖温度平衡线为基础，加上一个修正量，使电池在性能良好区域运行，这种控制算法简单。

本文利用模拟方法对水平衡温度进行修正，获得的电池最优性能操作温度，会因电池MEA结构及材料成份不同而有所变化，但上述变化规律，以及基于此对电池操作温度进行控制的方法，对电池的设计与操作优化具有参考意义。

# 参考文献

[1]蔡亚微,IntelligentEnergy宣布实现迄今最高的汽车燃料 电池功率密[EP/PL].[2016-9-15]. http://info.electric.hc360.com/2013/03/291114517509.shtml Cai Yawei, Intelligent Energy announced so far the highest vehicle fuel cellpower density [EP/PL].[2016-9-15]. http://info.electric.hc360.com/2013/03/291114517509.shtml

[2]YOSHIDA T,KOJIMA K. Toyota MIRAI Fuel Cell Vehicle and Progress Toward a Future Hydrogen Society[J]. Electrochemical Society Interface,2015,24(2):45-49.   
[3]Fofana D, Natarajan S K, Hamelin J, et al. Low platinum, high limiting current density of the PEMFC (proton exchange membrane fuel cell) based on multilayer cathode catalyst approach[J]. Energy, 2014,64(64):398-403.   
[4]Kotaka T,Aotani K, Tabuchi Y, et al. The analysis of mass transport phenomena in micro porous layer for high current densityoperationinPEMFCforautomobile application[C].11th International Conference on Fuel Cell Science,Engineering and Technology.2013.   
[5]Pei P, Li Y, Xu H, et al. A review on water fault diagnosis of PEMFC associated with the pressure drop[J]. Applied Energy,2016,173:366-385.   
[6] Yuan W, Tang Y, Pan M, et al. Model prediction of effects of operating parameters on proton exchange membrane fuel cell performance[J]. Renewable Energy， 2010, 35(3):656-666.   
[7]Jang JH, Chiu HC, Yan W M, et al. Effects of operating conditions on the performances of individual cell and stack of PEM fuel cell[J].Journal of Power Sources,2008, 180(1):476-483.   
[8]丁靖,曹涛锋,林鸿,等．质子交换膜燃料电池性能优化实 验研究[J]．工程热物理学报,2014,35(9):1826-1830. DING Jing, CAO Taofeng, LIN Hong,et al.Experimental optimization of the PEM fuel cell performance[J].Journal ofEngineering Thermophysics,2014,35(9):1826-1830.   
[9]Kanani H,Shams M,Hasheminasab M,et al.Model development and optimization of operating conditions to maximize PEMFC performance by response surface methodology[J].Energy Conversion&Management,2015, 93:9-22.   
[10]Damour C,Benne M,Grondin-Perez B,et al.A novel non-linear model-based control strategy to improve PEMFCwatermanagement-The flatness-based approach[J]. International Journal of Hydrogen Energy, 2015,40(5):2371-2376.   
[11]Hu Junming ，Xu Liangfei，Li Jianqiu,et al. Model-based estimation of liquid saturation in cathode gas diffusion layer and current density difference under proton exchange membrane fuel cell flooding[J].International Journal ofHydrogen Energy, 2015,40(41):14187-14201.   
[12] Cheng S,Fang C,Xu L,et al. Model-based temperature regulation of a PEM fuel cell system on a city bus[J]. InternationalJournalofHydrogenEnergy,2015, 40(39):13566-13575.   
[13] Shaul Stampfer. Operating Proton Exchange Membrane Fuel CellsWithoutExternalHumidification of the Reactant Gases[J]. Journal of the Electrochemical Society,1997, 144(8):2767-2772.   
[14]Janssen GJM,Overvelde ML J.Water transport in the proton-exchange-membrane fuel cel: measurements of the effective drag coefficient [J].Journal of Power Sources, 2001,101(1):117-125.   
[15]Berning T. The dew point temperature as a criterion for optimizing the operating conditions of proton exchange membrane fuel cells[J]. International Journal ofHydrogen Energy,2012,37(13):10265-10275.   
[16]Berning T,Kar S K.Low stoichiometry operation of a proton exchange membrane fuel cell employing the interdigitated flow field -A modeling study[J]. InternationalJournal of Hydrogen Energy， 2012, 37(10):8477-8489.   
[17]范宏昌．热学[M]．北京：科学出版社．2003:112-150. Fan Hongchang.Thermal physics[M].Beijing: Science Press.2003:112-150.

附页：

（1）作者信息：

<html><body><table><tr><td>姓名</td><td>何晓波</td></tr><tr><td>通讯 地址</td><td>武汉市洪山区武汉理工大学马房山 校区(西院) 邮编：430070</td></tr><tr><td>电话</td><td>13554629212</td></tr><tr><td>邮箱</td><td>1805097506@qq.com</td></tr></table></body></html>