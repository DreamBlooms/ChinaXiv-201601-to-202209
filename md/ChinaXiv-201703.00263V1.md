# 高能电子辐照下介质-导体相间结构深层充电特性研究

郑汉生1,²，杨涛¹，韩建伟1²，张振龙1,²，刘继奎³(1.中国科学院国家空间科学中心，北京100190；2.中国科学院大学，北京100049;3．北京控制工程研究所，北京100190)

摘要：介质-导体相间结构是航天器部件的常见结构。为研究影响此种结构深层充电特性的内在因素，设计了不同构型的实验样品，利用 Sr90放射源模拟空间高能电子环境对样品进行了深层充电辐照实验，测量了充电电位的差异。并借助深层充电三维仿真软件计算了此种结构在不同几何构型情况下的深层充电电位、电场分布。实验和仿真结果表明，介质最高表面电位以及介质内部最大电场均与介质宽度和高度呈正相关。其它条件不变时，介质越宽，或越高于导体表面，发生放电的风险就越高。在介质与导体侧面存在微小缝隙情况下，介质内最大电场显著增强，易发生内部击穿。而在介质与导体之间的真空间隙内，电场很容易超过击穿阈值，在一定的触发条件下放电风险很大。航天工程应用中为降低此种结构深层充放电的风险，在满足绝缘性能及其他要求的前提下应尽量减小介质的宽度，降低介质与导体间高度差，并确保介质与导体侧面接触良好。

关键词：高能电子；介质深层充电；实验；三维仿真中图分类号：V520.6，V416.5 文献标志码： 文章编号：

# Charging Characteristics of Dielectric-conductor Adjacent Structure under Energetic Electron Irradiation

ZHENG Han-sheng1,2，YANG Taol，HAN Jian-wei1, ZHANG Zhen-long1,LIU Ji-kui3 (1.National Space Science Center, Chinese Academy of Sciences,Beijing 1Oo19o, China; 2.University of Chinese Academy of Sciences,Beijing 1Ooo49,China; 3.Beijing Institute of Control Engineering,Beijing 1OO190, China)

Abstract:Dielectric-conductor adjacent structure commonly exists in spacecraft. To investigate the charging characteristics of the structure, different samples are designed and irradiated by $\operatorname { S r - } 9 0 \beta$ source to simulate the energetic-electron environment in space and sample charging potentials are measured during experiment. By using 3-D simulation tool of deep dielectric charging,diferent structures are modeled and charging potential and electric field are calculated numerically. Experimental results and simulation analysis show that the maximum dielectric surface potential and built-in electric field of the structure are positively associated with the width and height(relative to conductor surface)of dielectric.Wider or higher 收稿日期：年-月-日；修回日期：   
基金项目:国防基础科研计划(B1320133032)

dielectric willbe subjected to greater discharging risk.Especially when there is a narrow gap between dielectric and conductor,the electric field inside dielectric will enhance dramatically and may result in internal break-down. The electric field of the gap region can easily exceed the vacuum break-down threshold value.To mitigate the internal charging hazards of such structures in space engineering applications,the width and height of dielectric should be minimized as far as possible and the gap between dielectric and conductor must be avoided.

Key words: energetic electron; deep dielectric charging; experiment; three-dimensional simulation

空间辐射环境中高能电子穿透性强，易沉积在航天器外围的绝缘介质深处或穿透航天器屏蔽层沉积在内部的介质中以及孤立导体表面，导致电荷持续积累而形成深层充电（或称为内部充电）效应，由此引发的空间静电放电是主要的空间环境危害之一[1-3]。尤其是在电子环境恶劣的地球外辐射带区域，常出现规律性或偶发性的高能电子暴，能量为几百keV 至几MeV 的电子其通量会在数天内增大2\~3个数量级[4.5]，深层充电的危害性更加凸显，从而严重威胁着地球同步轨道（GEO）卫星、中高轨道(MEO)以及高椭圆轨道(HEO)卫星的在轨安全可靠运行[6-8]。

深层充电效应的研究对象主要是航天常用的高电阻率介质材料。对于未接地的孤立导体，原则上应该彻底避免。卫星上的电缆护套、电路板以及各种绝缘支撑件、固定件等存在大块介质的结构，是发生深层充电的高风险部位。目前，针对平板介质等简单构型开展的深层充电模拟实验和仿真计算的研究很多[9-1]，但针对卫星上具代表性的较复杂构型开展的深层充电规律研究相对较少[12,13]。实际上，在轨发生的充放电效应是一复杂的物理过程，不仅与介质材料自身的性能参数相关，还与充电部位的具体结构、接地条件及其周围布局有关，简单地等效为一维平板模型在很多情况下并不恰当。因此，通过实验和仿真的手段研究具有较高深层充电风险的典型卫星部件结构的充电特性和规律，对航天工程应用中深层充电防护设计具有重要意义。

介质-导体相间结构是指介质与导体侧面相邻紧贴的结构，导体为介质提供了侧面接地条件。此结构常见于卫星太阳帆板驱动机构(SADA)的导电环装置。太阳帆板与卫星主体间通过 SADA 导电环的金属滑环和电刷完成功率及信号传输，不同的金属滑环间用绝缘介质隔离[14]。由于 SADA 安装于卫星主体与外空间的交接处，高能电子很可能穿透SADA壳体而使导电滑环间的绝缘介质遭受严重的深层充电效应，一旦介质充电引发对导电滑环的放电，放电脉冲将可能影响到太阳帆板的跟踪控制以及卫星的可靠供电。本文利用 Sr90放射源模拟外辐射带的高能电子环境，设计了不同构型的介质-导体相间结构实验样品，对其进行了深层充电辐照实验，并借助自主开发的内部充电三维仿真软件，计算了不同介质宽度和高度以及介质与导体存在间隙情况下的充电电位、电场分布，分析了影响介质-导体相间结构深层充电特性的各种内在因素。

# 1实验和仿真方案

# 1. 1 实验装置

中科院空间中心的航天器充放电模拟装置(SCADS)是用于航天介质材料充放电特性研究以及卫星部件和单机设备的充放电风险评估的专用实验装置[15]，如图1所示。装置主要由真空室及真空泵组、电子辐照源、温控样品台、屏蔽及传动系统和参数测量系统组成，其核心部分是两套不同的电子辐照源，包括一台 STAIB EK-100-FL 型电子枪以及由七枚出厂总活度达 $3 5 0 \mathrm { { m C i } }$ 的 $^ { 9 0 } \mathrm { S r ^ { 9 0 } Y }$ 放射源组成的面阵。电子枪能提供 ${ 5 { \sim } 1 0 0 \mathrm { k e V } }$ 能量范围内束流密度连续可调的单能电子束，而 $^ { 9 0 } \mathrm { S r ^ { - } } ^ { 9 0 } \mathrm { Y }$ 放射源通过β衰变所发射的电子具有连续能谱 $\mathrm { ( E _ { m a x } { = } } 2 . 2 8 \mathrm { M e V ) }$ 且通量可控制在pA量级上下，与外辐射带中的深层充电高能电子能谱和通量有着较好的匹配，是较理想的深层充电模拟源。为模拟不同恶劣程度的高能电子环境，可通过调节放射源和实验样品之间的距离来控制电子通量的大小。辐照实验期间，参数测量系统可对实验样品的表面电位、接地电流、放电电流脉冲和电场脉冲以及放电图像等充放电参数进行自动监测记录。

![](images/ae03cfd0c2691688db50e9ab1e58409921390bd7a4e8dccdd40c3cdf7d7b7c46.jpg)  
图1航天器充放电模拟装置  
Fig.1Spacecraft Charging and Discharging Simulator

# 1.2 实验样品

为对比研究介质-导体相间结构中介质的宽度和高度(介质与导体表面高度差)对其深层充电效应的影响，设计了#1、#2 两种实验样品，其结构如图2 所示（侧视图）。样品尺寸均为$9 8 \mathrm { m m } { \times } 6 0 \mathrm { m m } { \times } 8 \mathrm { m m }$ ，介质材料为聚酰亚胺，导体材料为铜。 $2 \mathrm { m m }$ 厚的铜条嵌入不同深度( $\mathrm { \tilde { 6 } m m }$ 和 $\mathrm { 4 m m } )$ 的绝缘凹槽中，#1样品铜条以及铜条间的介质宽度均为 $1 0 \mathrm { m m }$ ，#2 样品的铜条以及铜条间的介质宽度均为 $5 \mathrm { m m }$ 。

![](images/d19e60e9f83c87d1bc4e680df3c082546ba7a0f013e70995be398277c202da68.jpg)  
图2#1和#2实验样品结构示意图

与介质侧面紧贴的导体(非孤立导体)为介质内的沉积电荷提供了泄放通道。若因导体与介质接触不良导致两者间存在微小缝隙，将对电荷的泄放产生不利影响。为研究此情况下的深层充电效应，设计了#3 样品，样品尺寸为 $4 0 \mathrm { m m } { \times } 4 0 \mathrm { m m } { \times } 8 \mathrm { m m }$ ，介质材料为聚四氟乙烯，导体材料为铜，其结构如图3所示。铜条厚 $2 \mathrm { m m }$ ，介质与铜条表面高度差为 $4 \mathrm { m m }$ ，其中一个铜条侧面与介质间存在 $0 . 1 \mathrm { m m }$ 的间隙。

![](images/c86eb5ff6245ae88d1f786283c186d1b7903a273791d73c397b8b13699fb9169.jpg)  
Fig.2Schematic diagram of sample #1 and #2   
图3#3实验样品结构示意图  
Fig.3Schematic diagram of sample #3

考虑到工程应用中 SADA导电环的金属滑环所加电压与介质充电电压相比可以忽略，实验样品的铜条均作接地处理。实验时，样品前表面(有凹槽的一面)接受电子辐照，推出放射源至样品正前方，调节源距使样品中心位置的电子通量为 $5 \mathrm { p A } / \mathrm { c m } ^ { 2 }$ 。实验期间，真空度维持在 $1 0 ^ { - 4 } { \sim } 1 0 ^ { - 5 } \mathrm { P a }$ ，温度保持室温。对样品两处对称位置的表面电位进行非接触式感应测量，比较充电电位的差异。

# 1.3仿真软件及建模

通过模拟实验可获得充电表面电位、放电电流脉冲及电场脉冲等充放电关键参数，但对于实验对象内部的剂量沉积以及电场和电位分布细节缺乏有效的测量手段。而借助计算机仿真则可弥补模拟实验的不足，能灵活地选择输入能谱参数，通过计算得出剂量沉积分布，给出充电电位、内部电场随时间和空间的变化情况。

SIC3D 是空间中心自主研发的可对具有复杂三维结构的卫星部件进行几何建模和仿真计算的深层充电三维仿真软件[16,17]，其基本框架如图4所示。软件的深层充电计算涉及两个基本物理过程，即空间辐射电子在介质材料内的输运以及介质材料内建电场的演化。相应地，SIC3D具有两个主要模块：基于Geant4 的电子输运蒙卡模拟模块，用于计算高能电子在材料内的运动轨迹和能量沉积；基于有限元分析(FEA)的电场演化计算模块，通过求解包含 RIC 模型的电荷连续性方程和泊松方程来计算介质材料内建电场的演化。

![](images/dc5bef40da4adf24e21073ca016be28435b73ea46073f8a87f927e033124117c.jpg)  
图4SIC3D基本框架图  
Fig.4FrameworkofSIC3D

利用 SIC3D对介质-导体相间结构进行了几何建模和充电仿真计算。如图5所示，建立了4种不同的三维模型，包含了不同的介质宽度、高度以及介质与导体间存在微小间隙的情况。4 种模型的介质材料均为聚酰亚胺(PI)，导体为 $2 \mathrm { m m }$ 厚的铜条。模型a中与铜条相邻的介质宽 $1 0 \mathrm { m m }$ ，高 $2 \mathrm { m m }$ 模型b的介质宽 $1 0 \mathrm { m m }$ ，高 $4 \mathrm { m m }$ ；模型c的介质宽 $\cdot$ ，高 $2 \mathrm { m m }$ ；模型d与a的介质宽度及高度相同，但铜条与介质间存在 $0 . 1 \mathrm { m m }$ 间隙。计算中采用的介质材料参数见表1，铜条被设定为零电位。为便于与模拟实验取得的定性结果进行对照，仿真的电子源采用 $\mathsf { S r } 9 0$ 放射源的能谱，从模型上方入射，电子通量与实验保持一致 $( 5 \mathrm { p A } / \mathrm { c m } ^ { 2 } )$ 。

表1仿真采用的材料参数  
Table1Parameters ofPI for simulation   

<html><body><table><tr><td>材料</td><td>p/(g·cm-³)</td><td></td><td>00/(Ω1.m1)</td><td>kp/(Ω¹·m1.rad△s△)</td><td>△</td></tr><tr><td>PI</td><td>1.42</td><td>3.45</td><td>1.0x10-15</td><td>2.0×10-13</td><td>0.6</td></tr></table></body></html>

![](images/ded880dace03ce4b88fd2655ffe07ab7e32500c3243e9cc8f120bcdca1246ddf.jpg)  
图5四种不同结构的仿真建模  
Fig.5Four different structures modeled in SIC3D

# 2实验和仿真结果及分析

# 2.1介质宽度和高度对深层充电特性的影响

在 Sr90放射源辐照下，#1、#2样品各自两处测量位置的电位变化趋势如图6所示。约 2000 分钟后，样品的表面电位均趋于平衡。#1样品位置1的平衡电位约为-14000V，位置2的平衡电位约为-16500V；#2样品位置1的平衡电位约为-13000V，位置2的平衡电位约为-15000V。

#1样品两个测量位置的表面电位均高于#2样品对应位置的表面电位，这说明介质与导体高度差相同时，宽介质比窄介质的充电电位更高。而两种样品测量位置2的电位均高于位置1的电位，说明了介质与导体高度差增加时，充电电位升高。

![](images/eb5e6f1a30da0800fa8a25b0f9d9473fe9a9d2b5cf9dc743637367a397d0ccc6.jpg)  
图6样品表面电位随时间的变化

利用 SIC3D对a、b、c三种模型计算得到的介质充电电位及内部电场三维分布如图7及图8所示。从图中可见，充电电位及电场在不同介质宽度和高度情况下的分布规律类似。介质表面最高负电位均出现在距离铜条(接地点)最远端。若介质两侧均有接地导体相邻，那么最大负电位点应位于介质中心位置。介质内部最大电场均出现在介质侧面与接地铜条的交界处，这与正面、背面及双面接地情况下平板介质的深层充电计算结果类似[10]。

![](images/b17d7ac6a7509e0131e791006db456030a851b1636c6cd72493d8912d1ad5950.jpg)  
Fig.6Evolution of surface potential of two samples   
图7a、b、c三种模型的电位分布

![](images/1610a78b3769ed7c68694dce68c6972817fb71c2f723b58a300174ab0d14f431.jpg)  
Fig.7Distribution of potential in model a,b and c

![](images/c2533aa12ca90c40046a7b106d0f500dd73429337c6faefd023f1bfe517d4f01.jpg)  
图8a、b、c三种模型的电场分布  
Fig.8Distribution of electric field in model a,b and c   
图9介质最高电位及最大电场随介质宽度和高度的变化  
Fig.9Variation of maximum surface voltage and electric field of dielectric with its width and height

图9为通过SIC3D仿真得到的介质最高表面电位及内部最大电场随介质宽度和高度的变化。介质是否会发生内部击穿放电取决于内部最大电场是否超过材料的介电强度。从最大电场随介质宽度和高度的变化情况可见，介质宽度或高度增加时，深层充电导致的介质内建电场会增强。介质宽度增加导致最大电场增强与介质接受电子辐照的面积增大有关。假设电子入射通量为 $J _ { \mathrm { I } }$ ，介质受照面积为 S，接地面积为 $s _ { \mathrm { o } }$ ，接地面附近介质内建电场为 $E$ ，电导率为 $\sigma$ ，则介质达到充电平衡时，由电荷守恒定律及欧姆定律可得 $\oint _ { S _ { I } } { J _ { I } \cdot \mathrm { d } S } = \oint _ { S _ { o } } { \boldsymbol { \sigma } E \cdot \mathrm { d } S }$ 。在其它条件不变时，增加介质的宽度会增大介质暴露的受照面积 $S _ { \mathrm { I } }$ ，从而导致介质接地面附近产生更强的局部电场，增加介质发生内部击穿的风险。

介质高度对最大电场的影响与介质不同深度的剂量率分布有关。图10所示为通过蒙卡计算得到的模型a中 $\scriptstyle \mathbf { y = } 0$ 平面介质区域的剂量率分布，由图可见，介质右半部分由于 $2 \mathrm { m m }$ 厚铜条的屏蔽，电子未能穿透进入其中。而左半部分，从介质表面沿着垂直向下的方向，电子沉积导致的剂量率呈减小趋势。受限于入射电子在介质材料中的最大射程，在距介质表面约 $4 \mathrm { m m }$ 以下，剂量率几乎为零。$\sigma = \sigma _ { \mathrm { d a r k } } + \sigma _ { _ { R I C } } = \sigma _ { \mathrm { d a r k } } + \mathbf { k } _ { \mathrm { p } } ( \frac { \mathrm { d } D } { \mathrm { d t } } ) ^ { \Delta }$ 的材料参数计算可知，聚酰亚胺的辐射诱导电导率比暗电导率大一个数量级。因此，当介质与导体表面高度差大于电子最大射程时，由于接地面附近介质电导率大幅降低，由欧姆定律 $J = { \boldsymbol { \sigma } } E$ 可知，介质内部最大电场将显著增强。

![](images/4f90afab4cc3daa888469a8a7ea405545605c6a211fd811d1c693c2976515943.jpg)  
图10a模型中 $\scriptstyle \mathbf { y = } 0$ 平面的剂量率分布

从充电电位的仿真结果来看，与最大电场的变化规律类似，一定条件下介质表面电位同样与介质宽度和高度呈正相关。电位是电场在空间的积分，介质表面电位取决于介质内部场强以及与接地点的距离。仿真所建立的a、b、c三种模型中，与另两种相比，模型b的介质内部电场更强，且介质上表面边沿与接地点的距离更远，因此其表面电位也更高。介质表面电位的高低不仅是其内部电场大小的间接体现，更直接的影响是，介质表面与附近其它部件表面间的电位差影响着两者间发生放电的风险。若相邻表面的电位差导致它们之间的电场超过击穿阈值，两者间将发生放电。因此，在介质-导体相间结构中，为降低介质发生内部击穿放电以及介质与附近部件表面间的放电风险，在满足其他要求的前提下，应尽量减小介质的宽度，降低介质与导体表面的高度差。

# 2.2介质与导体间隙对深层充电特性的影响

利用 $\mathsf { s r } 9 0$ 放射源对#3实验样品持续辐照24h以上达到充电平衡，辐照期间未监测到放电脉冲。图11所示为样品两处测量位置的电位变化情况，位置1和2的表面电位可见明显差异。位置1的介质与铜条接触良好，其表面平衡电位约为- $6 1 0 0 \mathrm { V }$ ；而位置2的介质其侧面与铜条间存在 $0 . 1 \mathrm { m m }$ 的间隙，表面电位相对高出 $32 . 8 \%$ ，达到 ${ \bf \nabla } \cdot { \bf 8 1 0 0 V }$ 。

![](images/bc014f1820d1143697bdad7c95607221831045ea65ac3848c4bf4ac66ab9c3ba.jpg)  
Fig.10Dose rate distribution of $\scriptstyle { \mathbf { y } = 0 }$ plane in model a   
图11#3样品表面电位随时间的变化

对模型d的三维充电仿真计算结果如图12所示。由电位分布图可见，有间隙时介质最高表面电位达-19000V，比模型a的介质最高电位-9146V高一个数量级。而通过比较模型a 和模型d的电场计算结果，发现两种结构的介质最大电场及其分布细节所呈现的差异性更为显著。无间隙时，最大电场为 $7 . 4 { \times } 1 0 ^ { 4 } \mathrm { V / c m }$ ，位于与铜条侧面相接处的介质内；有间隙时，整个结构的最大电场位于介质与导体侧面之间真空间隙区域的上部，达 $\cdot$ ，而介质内部的最大电场位于间隙底部的铜条边沿附近，约为 $\cdot$ ，这都超过了NASA-HDBK-4002A手册中给出的可能发生真空间隙放电以及介质击穿放电的阈值电场判据[18]，特别是间隙区域内的电场强度更是高出击穿阈值电场一个数量级。

介质与导体的间隙导致充电电位与电场急剧增强是由于介质内部沉积电荷的泄放通道发生变化。介质与导体侧面接触良好时，介质内电荷主要通过导体侧面泄放，泄放面积大且距离近。当两者因接触不良而产生微小间隙时，电荷只能绕道间隙底部导体与介质的接触点(即导体底面边沿)泄放，此位置由于铜条的屏蔽其下方的介质没有受到电子辐照，只有暗电导率参与电荷的泄放，因而导致局部电场显著增强。而介质与导体之间的真空间隙区域内，由于间隙两边电位相差悬殊且间隙尺度非常小，间隙中就可能形成超过击穿阈值的强电场，在一定触发条件下(例如介质材料真空出气)发生放电的风险很高。因此，在工程应用中，介质与导体相邻紧贴时，确保两者侧面间具有良好的电接触十分重要。

![](images/b6723a19ad9b1a1bee22d5542438f7c55f8c2089b1ccdf6ee4771f09daf56969.jpg)  
Fig.11Evolution of surface potential of sample #3   
图12结构d的电位及电场分布  
Fig.12Distribution of potential and electric field in structure d

# 3总结

本文利用航天器充放电模拟装置的 $\mathsf { s r } 9 0$ 放射源，对不同构型的介质-导体相间结构实验样品进行了深层充电辐照实验，并借助深层充电三维仿真软件 SIC3D 计算了不同几何构型的介质-导体相间结构模型充电至平衡时的电位及电场分布。实验和仿真结果表明，在连续谱高能电子的辐照下，与导体相邻的绝缘介质最大表面电位以及介质内部最大电场均与介质宽度和高度呈正相关。其它条件不变时，介质越宽，或者越高于导体表面，发生相邻部件间放电以及介质内部击穿放电的风险越高。尤其是当介质与导体侧面之间由于接触不良而产生微小间隙时，由于电荷泄放通道改变，导致介质内部最大电场显著增强，场强增大一个数量级。而间隙内的狭小真空区域，在间隙尺度很小时电场很可能超过击穿阈值而使介质-导体间发生放电。对于航天器中的介质-导体相间结构（例如SADA 导电环)，在满足导体间绝缘性能以及其他要求的前提下，应尽量减小介质的宽度以及介质与导体间的高度差，并确保介质与导体侧面电接触良好，杜绝缝隙的产生。

# 参考文献：

[1]Frederickson A R. Upsets related to spacecraft charging[J]. Nuclear Science, IEEE Transactions on, 1996, 43(2): 426-441   
[2] Griseri V. Behavior of dielectrics in a charging space environment and related anomalies in Flight[J]. IEEE Transactions on Dielectrics and Electrical Insulation,2OO9,16(3): 689-695   
[3]全荣辉．航天器介质深层充放电特征及其影响[D]．博士学位论文．北京：中国科学院研究生院, 2009   
[4] 濮祖荫，余彬，谢伦，等．磁层高能电子暴[J]．中国科学A辑,2000,30(增刊):127-130 Pu Zuyin，Yu Bin， Xie Lun, et al. Magnetosphere energetic electron storm[J]. SCIENCE IN CHINA (Series A), 2000,30(Suppl): 127-130   
[5] 闫小娟，陈东，黄建国，等．诱发卫星深层充电的高能电子环境模式研究[J]．航天器环境工程, 2008,25 (2): 120-124 Yan Xiaojuan， Chen Dong， Huang Jianguo, et al. A space energetic electron environment model for spacecraft deep dielectric charging evaluation[J]. Spacecraft Environment Engineering, 2OO8, 25 (2): 120-124   
[6]Han Jianwei, Huang Jianguo,Liu Zhenxing,et al. Correlation of double star anomalies with space environment[J]. Journal of spacecraft and rockets, 2005,42(6): 1061-1065   
[7]黄建国，韩建伟，航天器内部充电效应及典型事例分析[J]．物理学报,2010,59(4):2907-2913 Huang Jianguo, Han Jianwei. Analysis of a typical internal charging induced spacecraft anomaly[J]. ACTA PHYSICA SINICA,2010, 59(4): 2907-2913   
[8] Ecofet R. Overview of in-orbit radiation induced spacecraft anomalies[J]. Nuclear Science,IEEE Transactions on,2013, 60(3): 1791-1815   
[9] Jun I, Garrett HB,Kin W,et al. Review of an internal charging code,NUMIT[J]. IEEE Trans. Nucl. Sci., 2008, 36(5): 2467-2472   
[10] 黄建国，陈东．卫星介质深层充电的计算机模拟研究[J]．地球物理学报,2004,47(3):392-397 Huang Jianguo，Chen Dong.A study of deep dielectric charging on satelites by computer simulation[J]. Chinese Journal of Geophysics,2004, 47(3): 392-397   
[11]唐小金，易忠，张超，等．星用FR-4 电路板内建电场分析计算研究[J]．装备环境工程,2009,

6(4): 33-38

TANG Xiaojin, YI Zhong, ZHANG Chao, et al. Study on computation of build-up electric field in

FR-4 circuit board for satelite[J]. Equipment Environmental Engineering,2OO9, 6(4): 33-38 [12] 张振龙，全荣辉，韩建伟，等．卫星部件内部充放电试验与仿真[J]．原子能科学技术，2010,44 (增刊): 538-544 ZHANG Zhenlong， QUN Ronghui， HAN Jianwei, et al. Internal charging-discharging test and simulation for satelite components[J]. Atomic Energy Science and Technology， 2010,44(Suppl): 538-544 [13] 易忠，王松，唐小金，等．不同温度下复杂介质结构内带电规律仿真分析[J]．物理学报，2015, 64(12): 125201-125201 YI Zhong，WANG Song，TANG Xiaojin，et al. Computer simulation on temperature-dependent internal charging of complex dielectric structure[J]. ACTA PHYSICA SINICA，2015，64(12): 125201-125201 [14] 李睿，刘继奎，徐跃民，等．太阳帆板驱动机构的表面充放电效应研究[J].空间科学学报，2014, 34(3): 360-366 LI Rui,LIU Jikui, XU Yuemin, et al. Study of surface charging and discharging effects on solar array drive assembly[J]. Chinese Journal of Space Science, 2O14, 34(3): 360-366 [15] Zhang Zhenlong, Quan Ronghui, Wang Yan, Han Jianwei. Ground testing and computer modeling of internal charging for complex structures[C]. The 12th Spacecraft Charging Technology Conference, Kitakyushu, Japan, May 14-18,2012 [16]孙建军，张振龙，梁伟，等．卫星电缆网内部充电效应仿真分析[J]．航天器环境工程,2014,31(2): 173-177 Sun Jianjun, Zhang Zhenlong,Liang Wei, etal. Simulation of internal charging for electric cables used in the satellite[J]. Spacecraft Environment Engineering, 2014, 31(2): 173-177 [17] Zhang Zhenlong, Zhu Lihua,Han Jianwei, Gong Ding.A three-dimensional tool for spacecraft internal charging[C]. AIAA Space and Astronautics Forum and Exposition 2O15,Pasadena,USA, August 29-02, 2015 [18] Michael G R. Mitigating In-Space Charging Effects -A Guideline[R]. NASA-HDBK-4002A, 2011

作者简介：  
郑汉生（1989—)，男，博士研究生，研究方向为空间环境效应；通信地址：北京市海淀区中关村南二条1号；电话：  
13161079232；E-mail: zhenghansheng12 $@$ mails.ucas.ac.cn  
作者导师：  
韩建伟（1970—），男，博士，研究员，主要从事空间环境效应研究；通信地址：北京市8701信箱（100190)；电话：  
(010）62582852；E-mail:hanjw@nssc.ac.cn