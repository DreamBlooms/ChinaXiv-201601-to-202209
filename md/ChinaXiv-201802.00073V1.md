# 多点聚焦下腔式吸热器水动力特性的研究

郝芸」陈开拓1²王跃社¹王启志¹1.西安交通大学动力工程多相流国家重点实验室，西安，7100492．西安航天动力研究院,西安，710100

摘要：塔式太阳能热发电系统中，由于镜场辐射投射到吸热器受热面上同一目标点（即单点聚焦），造成受热面局部区域高度集中，呈现出时间和空间分布的不均匀现象，导致系统工质流量分配及水循环安全特性恶化。为此，在前面研究的基础上，笔者研究了多点聚焦方式下，腔式吸热器热负荷分布和受热管组内工质流量分配、热偏差及流动特性，为塔式太阳能腔式吸热器安全运行及其水动力特性优化控制提供参考。

关键词：多点聚焦；腔式吸热器；热负荷；水动力特性中图分类号：TK124文献标识码：A 文章编号：

# Study on Hydrodynamic Characteristics of Tower Solar Cavity Receiver under the Multi-target Focus Type

HAO Yun'CHEN Kai-TUO12 WANG Yue-ShelWANG Qi-Zhil

1. State KeyLaboratoryofMultiphase Flow inPower Engineering, Xi'an Jiaotong University, Xi'an,71049,China

2.Xi'an Aerospace Propulsion Institute,Xi'an,7101oo,China

Abstract:For the characteristics of one-target focus type of the heliostats in the tower solar power system,the distribution of the heat flux of the solar cavity receiver is non-uniform and concentrated on the certain heat panels of the cavity receiver,which causes the deterioration of the flow rate distribution,thermal deviation and the flowreliability,and also affects the stability and security of the whole system.Thus,based on the study under one-target focus type ofthe heliostats,the flowrate distribution,thermal deviation and the flowreliability under the multi-target focus type of the heliostats field is developed to provide general guidance for the security operating andthe optimal control strategy of the hydrodynamic characteristics of the solar power tower system.

Keywords: multi-target focus; cavity receiver; heat panel; hydrodynamic characteristics

# 0前言

塔式太阳能定日镜场的聚焦作用使得投射到腔式吸热器的热负荷呈现出时间和空间分布的不均匀现象。前期笔者研究发现，单点聚焦下，蒸发受热面管内工质流量分配及热偏差特性随热负荷的增大在光斑附近会有所恶化；而过热受热面内工质流量分配及热偏差特性与热负荷分布也不同步，这会造成热负荷集中区域受热管高温烧蚀。常规锅炉中通常采用加装节流孔圈等方法，调节受热面各管的流量，以减小锅炉水冷壁热偏差，防止发生局部超温和爆管[1]。但由于塔式太阳能定日镜无法实时跟踪太阳踪迹，热流密度集中区域在空间和时间上不断变化，常规锅炉的流量调节方法在塔式太阳能吸热器中难以得到有效应用。因此，学者们提出了多点聚焦镜场控制策略[2,3]，即对定日镜场进行分区控制，太阳辐射投射到吸热器受热面的不同目标点[4]，以使受热面的热负荷分布更加均匀。

基于腔式吸热器受热面热负荷分布，结合吸热器内辐射-对流的能量传递过程，建立受热管内汽液两相或单相工质流动换热计算模型，建立非均匀热负荷分布条件下腔式吸热器水动力的非线性数学模型，求解得出多点聚焦方式下腔式吸热器受热管组内工质的流量分配、热偏差及流动可靠性。

# 1模型建立

# 1.1 基本假设

为了简化计算，假设： $\textcircled{1}$ 只考虑各受热管之间热负荷分布的不均匀性； $\textcircled{2}$ 各个受热管在轴向上热负荷分布均匀； $\textcircled{3}$ 受热管在周向上只有半面受热，背阴面采用保温材料隔热，可视为绝热，

# 1.2传热模型

腔式吸热器总辐射量为工质吸热量、对流散热和辐射散热三项之和。

腔式工质吸热量：

$$
\mathcal { Q } _ { a b s } = \alpha _ { 0 } \mathcal { A } \Delta t _ { m }
$$

$a _ { \theta }$ -对流换热系数 $\mathrm { { / W { \cdot m } ^ { - 2 } { \cdot K } ^ { - 1 } } }$

$A$ 一 一对流换热面积 $/ \mathrm { m } ^ { 2 }$

$\varDelta t _ { m }$ —换热面积上的平均换热温差/K。

临界压力以下的单相水或水蒸气对流换热系数为[5]:

$$
\alpha _ { 0 } = 0 . 0 2 3 \frac { \lambda } { d _ { n } } R e ^ { 0 . 8 } P r ^ { 0 . 4 }
$$

2 管内工质的导热系数/ $\mathrm { { W } { \cdot } m ^ { - 1 } { \cdot } K ^ { - 1 } }$ $P r$ 普朗特数;  
$R e$ （2号 雷诺数，按循环流速计算；$d _ { n }$ 当量直径。

汽液两相蒸发段工质的对流换热系数采用饱和沸腾计算公式确定[6]:

$$
\alpha _ { 0 } = \alpha \sqrt { 1 + 1 . 0 2 7 \times 1 0 ^ { - 9 } ( { \frac { \dot { \rho ^ { \prime } } \omega _ { h } r } { q _ { n } } } ) ^ { \frac { 3 } { 2 } } ( { \frac { 0 . 7 \alpha _ { c h } } { \alpha } } ) ^ { 2 } }
$$

$$
\alpha = \sqrt { \alpha _ { d l } ^ { 2 } + ( 0 . 7 \alpha _ { c h } ) ^ { 2 } }
$$

$$
\alpha _ { d l } = 0 . 0 2 3 \frac { \lambda } { d _ { n } } R e ^ { 0 . 8 } P r ^ { 0 . 4 } ( \frac { \mu _ { n b } } { \mu _ { g z } } ) ^ { 0 . 1 1 }
$$

$$
\alpha _ { c h } = 3 . 1 6 ( \frac { p ^ { 0 . 1 4 } } { 0 . 7 2 2 } + 0 . 0 1 9 p ^ { 2 } ) q _ { n } ^ { 0 . 7 }
$$

$$
\omega _ { h } = \omega _ { 0 } [ 1 + x ( \frac { \rho ^ { ' } } { \rho ^ { ' } } - 1 ) ]
$$

$\lambda$ ——管内工质的导热系数/ $\mathrm { { W } { \cdot } m ^ { - 1 } { \cdot } K ^ { - 1 } }$ $P r$ —普朗特数;$R e$ ——雷诺数，按循环流速计算;$d _ { n }$ （2 当量直径。$a _ { d l }$ 1 单向流体强制对流换热系数$/ \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 } { \cdot } \mathrm { K } ^ { - 1 }$ $ { a _ { c h } }$ 池沸腾换热系数 $/ \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 } { \cdot } \mathrm { K } ^ { - 1 }$

$\omega _ { h }$ （20 管内汽水混合物流速/ $\mathbf { m } { \cdot } \mathbf { s } ^ { - 1 }$ $r$ 汽化潜热 $/ \mathrm { k J } \cdot \mathrm { k g } ^ { - 1 }$ ；$q _ { n }$ -内壁热负荷 $/ \mathrm { W } \cdot \mathrm { m } ^ { - 2 }$ ;$p$ （2 -压力/MPa;$\mu _ { n b }$ （2号 按内壁温度计算的粘性系数/Pa·s;$\mu _ { g z }$ 2 -按工质温度计算的粘性系数/Pa·s;$\omega _ { o }$ 循环流速/ $\mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ ：$x$ 1 管内工质干度；$\rho ^ { \prime }$ ， $\rho$ ”饱和水和饱和蒸汽的密度 $/ \mathrm { k g } \cdot \mathrm { m } ^ { - 3 }$ 。以上计算公式中的物性参数按照工质平均温度确定。

由于吸热器开口较小此，受热管外壁面对流散热根据大空间自然对流换热公式计算[]。单个受热管的辐射散热可由大空间内的小物体辐射散热计算得出。

# 1.3水动力模型

对垂直并联受热管组，各受热管均在上、下集箱之间所形成的压差下工作，并联管屏回路示意图见图1。

![](images/2bfe40d541feb7e97a2db2b1fd9b1048878d5e3b6a471b2f953c69675b79d3e0.jpg)  
图1并联管屏回路示意图  
Fig.1 Parallel tube circuit schematic diagram

单相过冷水及汽液两相流的管组，忽略集箱效应对受热管进出口压差的影响，得到：

$$
\begin{array} { r l } & { f _ { i } = \left( \Delta p _ { { _ { m c , i } } } + \Delta p _ { { _ { j b , i } } } + \Delta p _ { { _ { z w , i } } } + \Delta p _ { { _ { j s , i } } } \right) - } \\ & { \quad \quad ( \Delta p _ { { _ { m c , i + 1 } } } + \Delta p _ { { _ { j b , i + 1 } } } + \Delta p _ { { _ { z w , i + 1 } } } + \Delta p _ { { _ { j s , i + 1 } } } ) } \end{array}
$$

单相过热蒸汽的管组，忽略受热管内工质流动的加速压降，可得：

$$
\begin{array} { r l } & { f _ { i } = [ \Delta p _ { m c , i } + \Delta p _ { _ { j b , i } } + \Delta p _ { _ { z w , i } } - \left( \Delta p _ { _ { f , i } } - \Delta p _ { _ { h , i } } \right) ] - } \\ & { \quad [ \Delta p _ { _ { m c , i + 1 } } + \Delta p _ { _ { j b , i + 1 } } + \Delta p _ { _ { z w , i + 1 } } - \left( \Delta p _ { _ { f , i + 1 } } - \Delta p _ { _ { h , i + 1 } } \right) ] } \end{array}
$$

对 $\scriptstyle i = 1 , 2 , \ldots , \ n - 1$ ，可以得到 $^ { n - 1 }$ 个非线性方程[55]，同时考虑质量守恒定律，有：

$$
\left\{ \begin{array} { c } { { f _ { i } = 0 , i = 1 , 2 , \cdots , n - 1 } } \\ { { } } \\ { { \displaystyle \sum _ { i = 1 } ^ { n } m _ { i } = m } } \end{array} \right.
$$

式中：

（204号 $p _ { i j }$ 、 $p _ { i c }$ 第 $i$ 根管进、出口压力/Pa;$p _ { i n }$ 1 分配集箱进口压力/Pa;$p _ { o u t }$ 汇集集箱出口压力/Pa;$\varDelta p _ { f , i }$ 分配集箱入口到进口压增/Pa;$\varDelta p _ { h , i }$ ——汇集集箱出口到第 $i$ 根管出口压增/Pa;$\varDelta p _ { m c , i }$ 1 第 $i$ 根管摩擦阻力/Pa;$A p _ { j b , i }$ —第i根管局部阻力/Pa;$\varDelta p _ { z w , i }$ 第 $i$ 根管重位阻力/Pa;$m _ { i }$ 2 第i根管内工质质量流量 $\mathrm { / k g { \cdot } s ^ { - 1 } }$ ：$m$ 并联管组工质总质量流量 $\mathrm { / k g { \cdot } s ^ { - 1 } }$ 。

# 1.4流动可靠性[5]

水循环可靠性校验时，认为不发生停滞的条件是：

$$
\Delta p _ { \scriptscriptstyle 0 } / \Delta p _ { \scriptscriptstyle t z } \geq 1 . 0 5
$$

$\varDelta p _ { 0 }$ 一 回路的工作点压差 $/ \mathrm { P a }$ $\varDelta p _ { t z }$ -受热管的停滞压差/Pa。水循环不发生倒流的条件：

$$
\Delta p _ { 0 } \big / \Delta p _ { d l } ^ { m a x } \ge 1 . 0 5
$$

$\Delta p _ { d l } ^ { m a x }$ （201 受热弱管最大倒流压差/Pa;

# 2 热负荷分布

热负荷以Schwarzbolz.P.[5]等提出了HFCAL分析计算模型为依据而计算的。图2给出了镜场聚焦有效偏差系数相同，受热面平均热负荷为$1 0 0 \mathrm { k W } { \cdot } \mathrm { m } ^ { - 2 }$ 时，定日镜场的单点及多点聚焦方式下受热面热负荷分布。从图中可以看出，多点聚焦可使各个聚焦光斑中心区域的热负荷大为降低，避免了热负荷过度集中。

![](images/6c8a68efaf3332dfd109395272e090730ab6f65d4366b0ebdbe57bccc5385895.jpg)  
图2受热面热负荷分布

# 3结果与讨论

# 3.1流量分配特性

多点聚焦使得受热面热负荷分布趋于均匀，工质的流量分配得到改善，一定程度上避免了热负荷集中区域因冷却不足发生事故。

图3给出了系统压力 $5 \mathrm { { M P a } }$ ，平均热负荷分别为 $1 0 0 \mathrm { k W } { \cdot } \mathrm { m } ^ { - 2 }$ 和 $4 0 0 \mathrm { k W } { \cdot } \mathrm { m } ^ { - 2 }$ 时，不同聚焦方式下蒸发受热面的流量不均匀系数。

![](images/b2bcea301171c895f746cca5e4190470368439886003f4cbf5894dc560631a88.jpg)  
Fig.2HeatFluxofHeat Surfaces

(a) $1 0 0 \mathrm { k W } { \cdot } \mathrm { m } ^ { - 2 }$ 时流量不均匀系数分布情况 (a)Flow Non-uniformity Coefficient Distribution for $1 0 0 \mathrm { k W } { \cdot } \mathrm { m } ^ { - 2 }$

![](images/0b56969e7fdbdaec26e4d4a9eab41a3c11be2ee1ac7053480b3d5f04a824888b.jpg)  
图3蒸发受热面流量分配情况

Fig.3FlowRateDistribution ofEvaporationPanels

从图3(a)可以看出，当受热面平均热负荷较小时，无论是单点或多点镜场聚焦方式，受热管内工质流量分配特性较好；但是当受热面平均热负荷较大时，如图3(b)所示，多点聚焦可缓解受热面热负荷过度集中和流量分配不匹配问题。

图4分别给出了不同聚焦方式下，腔式吸热器过热受热面各管流量不均匀系数分布特性。

![](images/21eecd3d122997690abef6f7461c13ba4efbe9db67791856235f9063c44cf7aa.jpg)  
图4过热面各管流量分配特性

从图中可以看出，多点聚焦使得聚焦光斑中心区域的流量分配更加均匀。

# 3.2热偏差特性

工程中通常用受热管焓增与平均工况管焓增的比值，即热偏差系数来反映受热管的偏差特性。

图5给出了系统压力5MPa，平均热负荷为$4 0 0 \mathrm { k W } { \cdot } \mathrm { m } ^ { - 2 }$ 时，不同聚焦方式下蒸发受热面各受热管的热偏差系数。

![](images/a3b5ebedb60dcbc32e851a038bae1ed15bb0456067a1ee9ce9ce97a1bcf9e4e2.jpg)  
图5蒸发受热面工质热偏差

Fig.5 Thermal Deviation of Evaporation Panels

从图可以看出，多点聚焦的蒸发受热面各管内工质的焓增与平均工况管焓增比值为1，热偏差特性得到改善。

图6为三种聚焦方式下，过热受热面各管内工质热偏差系数的分布情况。

![](images/1fcfa9045ccff8e03d34fa1692305089a5ad5ee91c0194eabb5bacc244863656.jpg)  
Fig.4 Flow Rate Distribution of Superheated Sections   
图6过热面工质热偏差

Fig.6 Thermal Deviation of Superheated Sections

从图中可以看出，多点聚焦可有效缓解热负荷过度集中造成的受热管内工质热偏差，避免受热管发生超温，提高了系统运行安全性。

# 3.3流动可靠性

因蒸发受热面内的介质为单相过冷水或汽液两相流，离光斑中心较远的外围区域热负荷较小的受热管可能会发生循环停滞或倒流。

图7为系统压力 $5 \mathrm { { M P a } }$ ，不同聚焦方式下蒸发受热面各管工作压差与受热管停滞压差的比值情况，其中虚线为 $\varDelta p o / \varDelta p _ { t z } = I . 0 5$ 。

![](images/66aa52f05178f076fdaa8b57db4320e6de83c76a4aed4e43c97ae34447d511e5.jpg)  
图7受热管进出口压差与停滞压差比值

Fig.7 The Ratio of Inlet/Outlet and Stagnation Pressure

Differences

从图可以看出，多点聚焦增大了循环停滞区受热管的热负荷，使发生循环停滞的受热管数目减少。

图8给出了系统压力和受热管几何尺寸一定时，三种不同聚焦方式下受热面各管的最大流压差情况。多点聚焦降低了受热管的最大倒流压差，避免工质循环发生倒流。

![](images/35a727509ce1ff7d48a0aedb3d44c1ba7f1e5110819719ee982e8d29cb3e3635.jpg)  
图8受热管最大倒流压差  
Fig.8MaximumPressureDifferences ofBackflow

# 4结论

面的水循环安全特性，对汽水系统的安全运行具有重要意义。

# 参考文献

[1]喻兰兰，周克毅，汤妍．锅炉水冷壁节流孔板结构对结 垢的影响及其优化．《动力工程学报》2012年11期， 第32卷：830-835 YU Lanlan, ZHOU Keyi, TANG Yan. Influence of Strutural Parmeters on Fouling of Throttle Orificein Boiler Water Walls. Journal of chinese socity of power engineering,2012.11(32): 830-835   
[2] Riaz M, Gurr T. Solar Flux Density Distributions on Central Tower Receivers[J]. Solar Energy,1977,19 (2): 185-194.   
[3] 辛秋霞，卞新高，杨缝缝．塔式太阳能热发电系统镜场 调度方法的研究[J]．太阳能学报，2010年3月第31卷： 317-322. XIN Qiuxia, BIAN Xingao, YANG Fengfeng. Research on Dispatching Heliostats in Solar Power Tower Plant. Acta Energiae Solaris Sinica.2010.3(31):317-322.   
[4] 余琴.基于光学效率与热效应的塔式太阳能定日镜场布 置及优化研究[D]．西安：西安交通大学，2011. YU Qin. Investigation on Layout and Optimization of HeliostatField in Solar Tower PowerPlantsBased on Optical Efficiency and Thermal Effect.Xi'an: xi'an jiaotong university,2011   
[5] 车的福，庄正宁，李军，王栋．锅炉[M]．西安：西安 交通大学出版社，2004. CHE Defu, ZHUANG Zhengning, LI Jun, WANG Dong. “Boiler[M]".Xi'an: Xi'an Jiaotong University press, 2004.   
[6] 徐济．沸腾传热和汽液两相流[M]．北京：原子能出 版社，2001 XU Jiyun.“Boiling Heat Transfer and Vapor Liquid Two Phase Flow [M]". Beijing: atomic energy press, 2001   
[7] 杨世铭，陶文钰．传热学（第三版）[M]．北京：高等 教育出版社，1998. YANG Shiming, TAO Wenquan. “Heat Transfer Theory (third edition) [M]".Beijing: higher education press,1998   
[8] 杨冬，陈听宽，李会雄等．锅炉过热器与再热器流量分 配的非线性数学模型及壁温计算方法[J]．中国电机工 程学报，20015(21):39-43. YANG Dong, CHEN Tingkuan LI Huixiong et al. Nonlinear Mathematical Model for Flow Rate Distribution in the Parallar Tubes of Boiler Superheater/Reheater and the Calculation Method of Tube Surface Temperature.Proceedings of the CSEE.2001 (5): 39-43.   
[9] Schwarzbolz P,Schmitz,M.,Pitz-Paal,R.Visual HFCAL -ASoftware for Layout and Optimization of Heliostat Fields[C]. Berlin,2009.

本文分析了多点聚焦热负荷分布形式下腔式吸热器受热面热负荷分布特征，能够有效地改善腔式吸热器系统的流量分配特性、热偏差特性蒸发受热

# 附页：

作者通讯地址：西安交通大学动力工程国家重点实验室，手机：18991945780，电子信箱：haoyun@stu. xjtu. edu. cn。