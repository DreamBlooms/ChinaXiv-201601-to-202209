彩色印刷

编号：2016-0094

# 液氧煤油发动机尾焰冲击导流槽三维数值模拟

蔡红华，聂万胜，苏凌宇，侯志勇（装备学院航天装备系，北京101416)

摘要：为了研究液氧煤油发动机尾焰冲击导流槽的流场规律，采用CFD软件计算了液氧煤油发动机尾焰对无导流装置、有锲形导流装置和有圆锥体导流装置三种不同导流槽的冲击流场进行了三维数值模拟，对比分析了冲击不同导流槽的尾焰燃气流动。结果表明：液氧煤油发动机尾焰燃气垂直冲击无导流装置的导流槽，沿着导流槽侧面流动和向上反射的燃气会对导流槽底面正上方环境产生高温影响；锲形导流装置能够避免沿着导流槽侧面流动和向上反射的燃气对导流槽底面正上方环境的高温影响；圆锥体导流装置能够避免向上反射的燃气对导流槽底面正上方环境的高温影响，在避免燃气沿着导流槽侧面流动方面仍有改进余地；相对尾焰燃气冲击无导流装置的导流槽，锲形导流装置和圆锥体导流装置表面最大压力分别增大了10.31%和 $3 3 . 8 1 \%$ ，锲形导流装置和圆锥体导流装置受尾焰燃气冲击的最高温度分别降低了 $4 . 0 4 \%$ 和 $8 . 9 5 \%$

关键词：液氧煤油发动机；尾焰；冲击；导流槽；数值模拟中图分类号：V430 文献标识码：A 文章编号：

# Three-dimensional Numerical Simulation of LOX/Kerosene Engine Exhaust Plume Impinging on the Diversion Trough

CAI Hong-Hua, NIE Wan-Sheng, SU Ling-Yu, HOU Zhi-Yong (Department of Aerospace Equipment, The Academy of Equipment, Beijing 101416, China )

Abstract: Aimed at studying the flow characteristics ofLOX/kerosene engine exhaust plume impinging on the diversion trough,three-dimension flow fields of LOX/kerosene engine exhaust plume impinging on three diversion troughs of without deflector，with a wedge deflector，with a conical deflector were calculated with the CFD software,and flow fields of plume impinging on different diversion troughs were compared and analyzed.It is found that,after LOX/kerosene engine exhaust plume vertically impacting on the diversion trough without deflector,plume which flows along the side surface of the diversion through and plume reflected upward would bring high temperature efect on the environment directly above the diversion trough.The wedge deflector would avoid the high temperature effect of plume on the environment directlyabove the diversion trough,while the conical deflector only could avoid the high temperature effect of plume reflected upward, tere was stillroom for improving avoiding plume flowing along the side surface of the diversion trough. Compared with the plume impact on the diversion trough without deflector，the maximum pressure of the wedge deflector and the conical deflector respectively increase $1 0 . 3 1 \%$ and $3 3 . 8 1 \%$ ， the plume impact maximum temperature of the wedge deflector and the conical deflector respectively decrease $4 . 0 4 \%$ and $8 . 9 5 \%$

Key words:LOX/kerosene engine; Exhaust plume; Impinging; Deflector; Mathematical simulation

# 0 引言

液氧煤油发动机因为具有推力大、无毒、无污染等特点已经成为液体火箭发动机的发展方向。由于火箭在发射过程中喷射出高速、高温的尾焰燃气，在发射初始阶段和试验平台试车过程中发动机距离地面平台较近，尾焰燃气的热冲击和动力冲击效应不仅可能引起发射装置的振动响应和飞行器飞行的初始扰动，甚至会威胁地面平台上其他设备[1-

2]，因此有必要就尾焰燃气对发射平台的冲击效应进行研究[3]。在航天器设计过程中，通常通过计算研究火箭发动机尾焰对喷管出口下游临近结构冲击的热影响[4-5]。火箭发射场和发动机实验台采用在平台下面建设导流槽的方法引导尾焰流向，以减缓尾焰对平台和装置设施的冲击效应，为降低导流槽的冲击烧蚀效应、提高导流槽的安全性和使用寿命，科研工作者不断研究不同形状的导流装置。

近年来，国内外有关火箭发动机尾焰冲击导流

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

装置的数值研究不断深入，马艳丽等人[3]针对固体火箭发动机尾焰对发射平台冲击进行了数值研究。Mayer等人[开发程序，计算研究了基于液体火箭发动机尾焰冲击的传热特性。SeijiTsutsumi 等人[7]针对固体火箭发射初始阶段冲击流场开展仿真计算，研究了尾焰冲击不同形状导流装置的噪音特性。Michael等人[8-9]开发固体火箭发动机冲击流场仿真计算程序，通过建立水平试验台，采用实验方法对开发的计算程序进行验证。Jeffrey等人[10]采用CFD软件开展火箭尾焰冲击有圆锥体导流装置导流槽的流场特性仿真研究。Daniel C．Allgood 等人[11]针对战神系列火箭发射阶段，对氢氧发动机尾焰冲击导流槽效应进行了CFD仿真计算。BruceT.Vu等人[12]采用CFD计算研究了航天飞机主发动机和固体燃料助推器尾焰对有锲形导流装置导流槽的冲击流场。

本文提出了一种液氧煤油发动机尾焰冲击导流槽流场计算方法，首先计算发动机内流场，然后以计算获得喷管喉部截面参数作为入口边界条件计算尾焰冲击流场，该方法充分考虑了燃烧室内燃烧和复燃反应对尾焰冲击的影响。基于该方法采用CFD软件针对液氧煤油发动机尾焰冲击效应进行三维数值计算，研究了尾焰冲击不同结构形状导流装置的流场特性和流动规律。

# 1物理模型和计算方法

# 1.1 物理模型

本文以液氧煤油发动机为研究对象，推进剂总流量为 $3 9 0 \mathrm { k g / s }$ ，液氧/煤油混合比为2.4，为富燃燃烧工作状态。研究的导流槽及导流装置结构如图1所示。图1（a）为无导流装置的简单导流槽，由底面、侧面和坡面组成。发动机喷管出口直径为 $D$ 导流槽结构尺寸为侧面高度 $\scriptstyle a = 7 . 6 4 D$ （发动机喷管出口与导流槽底面距离)，底面横向宽度 $scriptstyle b = 6 . 3 7 D$ 坡面长度 $c { = } 1 2 . 7 4 D$ ，底面纵向宽度 $\scriptstyle d = 6 . 3 7 D$ 。图1（b）为图1（a）基础上在导流槽底面建设锲形导流装置，图1（c）为图1（a）基础上在导流槽底面建设圆锥体导流装置，锲形和圆锥体曲面设计参考文献[13]。

![](images/a177743f989b7dd278e5098d26b845816103611c093058cd930b79b21c296b27.jpg)  
图1导流装置和导流槽结构  
Fig.1 Structure size of diversion troughs and deflectors

# 1.2化学反应机理

文献[14]对比分析了液态煤油/气氢/气氧和气态煤油/气氢/气氧发动机内部流场计算结果，结果表明两种计算方法都可以获得正确流场计算结果。本文考虑复燃对尾焰冲击效应的影响，采用简化的单步总包反应

$$
\mathrm { C } _ { 1 2 } \mathrm { H } _ { 2 3 } + 1 7 . 7 5 \mathrm { O } _ { 2 }  1 2 \mathrm { C O } _ { 2 } + 1 1 . 5 \mathrm { H } _ { 2 } \mathrm { O } ( 1 )
$$

将实际煤油燃烧过程简化为煤油的替代燃料 $\mathrm { C } _ { 1 2 } \mathrm { H } _ { 2 3 }$ 单步氧化生成完全反应产物 $_ \mathrm { H } _ { 2 } \mathrm { O }$ 和 $\mathrm { C O } _ { 2 }$ ，数值计算中涉及到的物质有煤油蒸气、氧气、二氧化碳和水蒸气四种气体。采用单步总包化学反应计算得到的温度相比实际温度会偏高，但是计算效率却非常高，并且本文的研究目的在于对比分析不同导流槽的降温性能，采用单步总包化学反应可以得到正确的结论。

# 1.3控制方程与求解模型

采用多组分化学反应的守恒型三维N-S方程作为模型的流动、物质与能量交换以及燃烧控制方程，其通用形式为

$$
\frac { \partial U } { \partial t } + \frac { \partial ( F - F _ { \mathrm { v } } ) } { \partial x } + \frac { \partial ( G - G _ { \mathrm { v } } ) } { \partial y } + \frac { \partial ( H - H _ { \mathrm { v } } ) } { \partial z } = J
$$

式中 $U$ 为守恒变量向量， $t$ 为时间变量， $F$ ， $G$ ， $H$ 为对流项向量， $F _ { \mathrm { v } }$ ， $G _ { \mathrm { v } }$ ， $H _ { \mathrm { v } }$ 为粘性项向量， $J$ 为源项向量。上式分别为质量方程、 $x$ ，

$y$ ， $z$ 方向动量方程、能量方程和各组分方程。

描述火箭发动机燃烧流动过程的N-S方程是非线性强相互耦合的偏微分方程组，目前压力隐式算

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

子分裂算法（PressureImplicit with SplittingofOperators，PISO）已成功应用于计算火箭发动机燃烧流动过程[15]。应用有限体积法离散尾焰流场控制方程，以realizable $k { - } \varepsilon$ 双方程模型和有限速率/涡耗散模型求解流场N-S控制方程进行计算，使用Arrhenius公式计算化学源项。

# 1.4计算网格与边界条件

基于发展较为成熟的网格处理软件对网格进行处理，由于发动机喷注器面板上喷嘴分布具有1/3对称特性，为提高计算效率，采用结构化网格的方法处理本文中发动机内部流场三维计算区域，生成网格及边界条件如图2所示；由于尾焰冲击导流槽及导流装置流场具有1/4对称特性，为提高计算效率，选取1/4对称流场作为尾焰冲击流场的计算区域，生成网格及边界条件如图3所示。经过网格独立性验证，最终选择97万网格方案和111万网格方案分别进行发动机内流场和尾焰冲击流场计算。

![](images/a243b95ec40eb49fda920c5c072a399e13e33016a07c30274536fd6c6ad99bf7.jpg)  
图2发动机内部流场计算三维网格及边界条件

Fig.2Three dimensional mesh and boundaries of engine internal flow field

发动机内部流场计算边界条件具体定义为：massflowinlet边界为 $1 . 1 7 8 \mathrm { k g / s }$ ，氧/煤油混合比为2.4；wall边界为壁面无滑移；pressure outlet边界为温度 $3 0 0 ~ \mathrm { K }$ ，压力 $1 0 1 3 2 5 \ \mathrm { P a }$ 。尾焰冲击流场计算边界条件具体定义为：massflowinlet边界通过发动机内部流场计算确定；pressurefar field 边界为温度$3 0 0 \mathrm { K }$ ，压力 $1 0 1 3 2 5 \mathrm { P a }$ ；wall边界为壁面无滑移。

![](images/8c84f5a8af40ab11866183059484f9661f43b0619ff3ab68fccee33ece886864.jpg)  
图3尾焰冲击流场计算三维网格及边界条件

# 2 计算结果与分析

# 2.1 模型验证

使用本文模型计算文献[16给定工况下尾焰冲击流场，并将结果与之进行对比。不同压力比(NPR $\underline { { \underline { { \mathbf { \Pi } } } } } =$ 喷管总压/喷管出口处环境压力）工况下计算结果与实验测量结果对比如图4所示，左边是本文计算得到流场速度云图，右边是文献中纹影测量流场结果。喷管出口直径 $d = 2 . 5 4$ cm，喉部上游喷管收缩段的收缩比约为5，地面平板与喷管出口间距离 $\scriptstyle h = 2 d$ 。图4（a）是 $\mathrm { N P R } { = } 2 . 5$ 时流场对比图，流场中存在斜激波；图4（b）和图4（c）分别是$\mathrm { N P R } { = } 3 . 7$ 和 $\mathrm { N P R } { = } 5 . 0$ 时流场对比图，流场不再产生斜激波而产生了马赫盘现象，并且马赫盘的尺寸随着相互作用强度的增大而增大； $\mathrm { N P R } { = } 3 . 7$ 时，不同h/d工况下冲击平板表面压力分布实验对仿真对比如图5所示。计算得到流场结构、平板表面压力分布与实验测得流场结构吻合较好，证明了尾焰冲击流场计算模型的准确性。

![](images/57c4a973dd5148f458949a39b212231644f2716c9e4f7ba8fced529b8c6b63c9.jpg)  
Fig.3Three dimensional meshand boundariesof gasflow-guided channel and deflector   
图4不同压力比工况下流场对比  
Fig.4Flow field contoursofdifferentNPR

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

![](images/76ff90e540a69bafb2091c600f9adda36268ae7887c3731feaac736a88d425ba.jpg)  
Fig.5 Pressure distributions comparison between experiment and simulation on the plane surface $( \mathrm { N P R } { = } 3 . 7$ ）

# 2.2发动机内部流场计算结果与分析

首先，本文对液氧煤油发动机内部燃烧流场进行计算，获得温度和速度流场参数分布如图6所示，氧和煤油混合富燃蒸气在发动机内进行充分的化学反应生成二氧化碳和水，喷管喉部和扩张段流场参数具有轴对称特征。

![](images/59eb0be451e65fb552726ae375cccf5d15cd6a3ee1d205f542cadb8af0fc75aa.jpg)  
图5 冲击平板表面压力分布对比！ $\mathrm { ( N P R = } 3 . 7$   
图6发动机内部温度与速度分布

# 2.3尾焰冲击流场计算结果与分析

以发动机内部流场计算得到喷管喉部截面参数作为入口边界，采用单步总包化学反应描述复燃反应过程，计算获得了液氧煤油发动机尾焰冲击无导流装置、有锲形导流装置、有圆锥体导流装置三种导流槽的三维流场，图7（a）-图7（c）分别为尾焰冲击无导流装置导流槽的压力、温度和速度流场，尾焰燃气冲击导流槽底面之后主要沿着导流槽的坡面、导流槽侧面和由垂直冲击导致的向上反射三个方向流动，沿着导流槽侧面向上流动和向上反射的燃气都将对导流槽底面正上方环境产生高温影响。图8（a）-图8（c）分别为尾焰冲击有锲形导流装置导流槽的压力、温度和速度流场，尾焰燃气直接冲击锲形导流装置顶端之后主要沿着导流装置引导的坡面流动，避免了尾焰燃气对导流槽底面正上方环境的高温影响。图9（a）-图9（c）分别为尾焰冲击有圆锥体导流装置导流槽的压力、温度和速度流场，尾焰燃气直接冲击圆锥体导流装置顶端之后沿着导流装置引导方向流动，避免了垂直冲击导流槽底面而引起的燃气向上反射，但由于圆锥体导流装置引导一部分燃气沿着导流槽侧面流动，因此只是在一定程度上减缓了尾焰燃气对导流槽底面正上方环境的高温影响，还具有改进的余地。

![](images/a8fcccaafcab55d19414c390dbcf537d91fd31b14fa90f17ffc9eaa8c1a2d7de.jpg)  
Fig.6 Temperature and velocitycontours in engine   
图7无导流装置尾焰冲击流场  
Fig.7Impact flow field contours without deflector

# WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

![](images/8a2437fda72a59f01692e2ff58419d31e0b64f24de43d3d3bdbdeb53c2992872.jpg)

![](images/1479318460e12d56ac01e5b1e8fe3261270079061eece24cb66cb857bd08d98e.jpg)  
Fig.8 Impact flow field contours with the wedge deflector   
图9有圆锥体导流装置尾焰冲击流场

Fig.9Impact flow field contours with the conical deflector

图10（a）-图10（c）分别为导流槽底面、锲形导流装置表面和圆锥体导流装置表面上压力分布，锲形导流装置和圆锥体导流装置表面最大压力相对无导流装置的导流槽底面分别增大了 $1 0 . 3 1 \%$ 和 $3 . 8 1 \%$ ，这是因为：一是在导流槽底面上的导流装置导致发动机喷管出口与冲击表面之间距离缩短了；二是导流装置的形状导致最大受力面面积减小了，并且圆锥体导流装置的最大受力面面积相对锲形导流装置更小。

![](images/ee47096b4e8ab24e88cda6a2449d2e72772246dc58832f10cb0fb02f32d6eefd.jpg)  
图8有锲形导流装置尾焰冲击流场  
图10导流槽底面和导流装置表面压力分布  
Fig.10 Pressure contours of the bottom surface and the deflector   
图11轴线上参数分布  
Fig.11 Parameters distribution on the axis

WORD批量转PDF工具-未注册注册码购买联系QQ：3049816538

喷管喉部到冲击平面间中心轴线上参数分布如图11所示，图11（a）-图11（c）分别为压力、速度和温度分布，尾焰燃气冲击到导流槽和导流装置表面时速度骤降为0，导致压力和温度骤然升高；

由于导流装置能够很好的引导尾焰燃气流动，相对尾焰燃气冲击无导流装置的导流槽，锲形导流装置和圆锥体导流装置表面受尾焰燃气冲击的最高温度分别降低了 $4 . 0 4 \%$ 和 $8 . 9 5 \%$ 。

10.0M1 no deflector 3.0k 4.0k no deflectorT 2.5k conical defietor 7caldeflec  
6.0M wedge deflector2.5k  
2.0M 1 1 1.0k A ： noniealecthletor wedge deflector90 500.0 1.5k/ ·0.0- 0.0 1.0k0 2 4 6 8 10 12 14 2 4 10 12 14 0 2 4 6 8 10 12 14position /m position /m position /m(a)压力 (b)速度 (c）温度

3结论通过研究得到如下结论：

（1）液氧煤油发动机尾焰燃气垂直冲击无导流装置的导流槽之后同时沿着导流槽的坡面和侧面流动，沿着导流槽侧面流动和向上反射的燃气会对导流槽底面正上方环境产生高温影响。

（2）液氧煤油发动机尾焰燃气冲击有锲形导流装置的导流槽之后沿着导流装置和导流槽坡面流动，避免了沿着导流槽侧面流动和向上反射的燃气对导流槽底面正上方环境的高温影响。

（3）液氧煤油发动机尾焰燃气冲击有圆锥体导流装置的导流槽之后沿着导流装置、导流槽坡面和侧面流动，一定程度上减缓了燃气对导流槽底面正上方环境的高温影响，在避免燃气沿着导流槽侧面流动方面仍有改进余地。

（4）相对尾焰燃气冲击无导流装置的导流槽，由于导流装置导致发动机喷管出口与导流冲击表面之间距离缩短了、最大受力面面积减小了，锲形导流装置、圆锥体导流装置表面最大压力分别增大了 $1 0 . 3 1 \%$ 和 $3 3 . 8 1 \%$ ；由于导流装置能够很好的引导尾焰燃气流动，锲形导流装置、圆锥体导流装置受尾焰燃气冲击的最高温度分别降低了 $4 . 0 4 \%$ 和$8 . 9 5 \%$ 。

# 参考文献：

[1]聂万胜，杨军辉，何浩波，等．液体火箭发动机尾喷焰红 外辐射特性[J]．国防科技大学学报,2005,27(5):91-94. NIE Wansheng,YANG Junhui,HE Haobo,et al.The IR Radiation Characteristic of Exhaust Plume of the Liquid Rocket Engine[J]. Journal of National Universityof Defense Technology,2005,27(5): 91-94.(in Chinese)   
[2] 周帆，姜 毅，郝继光．火箭发动机尾焰流场注水降温 效果初探[J].推进技术,2012,33(2):249-252. ZHOU Fan，JIANG Yi,HAO Jiguang. Exploring on Cooling Effect of Water Injection on Rocket Motor Exhaust[J]. Journal of Propulsion Technology,2012,33(2): 249-252.(in Chinese)   
[3]马艳丽，姜毅，郝继光，等．固体发动机燃气射流对发射 平台冲击效应研究[J]．固体火箭技术,2010,33(4):373- 377. MA Yanli, JIANG Yi, HAO Jiguang,et al. Study on the Impact Effect of Solid Rocket Motor ExhaustPlume to the LaunchingPlatform[J].JournalofSolidRocket Technology,2010,33(4): 373-376.   
[4]E.Mayer, R. Prickett. Rocket Plume Impingement Heat Transfer on Plane Surfaces[J]. AIAA Journal, 1987, 24(4): 291-295.   
[5]David R Gonzalez,Paul Wallman,Matthew Sanford,et al. Characterizationof RocketPlumeFluid Dynamic Environment UsingNumerical&Experimental Approaches[J].AIAA Journal,2013,50(3): 527-539..   
[6] E.Mayer,R.Prickett.Rocket Plume Impingement Heat Transfer on Plane Surfaces[R].AIAA 86-1321,1986.   
[7] Seiji Tsutsumi, Susumu Kato,Kato Fukuda,etal.Effect of Deflector Shape on Acoustic Field of Launch Vehicle at Lift-off[C]//Orlando: $4 7 ^ { \mathrm { t h } }$ AIAA Aerospace Sciences Meeting Including The New HorizonsForum and Aerospace Exposition,2009,AIAA 2009-328.   
[8] Michael C Dawson, Freddie Douglas,Peter A.Orlin.ASRM Plume Deflector Analysis Program[C]// Nashville: 17th Aerospace Ground Testing Conference,1992，AIAA 92- 3978.   
[9]Freddie Douglas,Michael C Dawson,Peter A Orlin.ASRM Subscale Plume Deflector Testing[C]// Nashville:17th Aerospace Ground Testing Conference，1992,AIAA 92- 3919.   
[10]Jeffery A.Housman,Michael F.Barad, Cetin C.Kiris. Space-Time Accuracy Assessment of CFD Simulations for the Launch Environment[C]// Honolulu: 29th AIAA Applied Aerodynamics Conference,2011，AIAA 2011- 3650.   
[11] DANIE C A,VINEET A.Computational Plume Modeling of Conceptual ARES Vehicle Stage Tests[C]// Cincinnati: 43rd AIAA/ASME/SAE/ASEE Joint Propulsion Conference & Exhibit,2007,AIAA 2007-5708.   
[12]BRUCE T V，NILI B,OSHIN P，et al.Multiphase Modeling of Water Injection on Flame Deflector[C]//. San Diego:2lst AIAA Computational Fluid Dynamics Conference,2013,AIAA 2012-2592.   
[13]J.K.Prasad,R.C.Mehta,A.K. Sreekanth.Impingement of Supersonic Jets on An Axisymmetric Deflector[J].AIAA JOURNAL,1994,32(7):1535-1538.   
[14] T S Wang. Thermo-kinetics characteristics of kerosene combustion[C]// Denver: 34th AIAA Thermophysics conference,2000,AIAA 2000-2511,1-11.   
[15]聂万胜，丰松江．液体火箭发动机燃烧动力学模型与数 值计算[M]．北京：国防工业出版社，2011. NIE Wansheng,FENG Songjiang.Liquid Rocket Engine Combustion Kinetics Model and Numerical Calculation[M]. Beijing: National Defense Industry Press,20o5.(in Chinese)   
[16]Alvi F S,Iyer K G.Mean and Unsteady Flowfield Propertiesof Supersonic Impinging Jetswith Lift Plates[C]//Bellevue:5th AIAA/CEASAeroacoustics Conference,1999,AIAA 99-1829.   
附加：   
作者：蔡红华   
地址：北京市怀柔区八一路一号98号信箱   
邮编：101416   
手机号码：15300249295   
E-mail: honghuacai@aliyun.com