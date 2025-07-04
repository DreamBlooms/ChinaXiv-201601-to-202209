# 地表冻融状态对延迟多普勒波形和多路径数据影响分析

吴学睿1,2.3，夏俊明4,5，白伟华4,5,6，张兴刚

1.中国科学院上海天文台，上海 200030；2．上海市空间导航与定位技术重点实验室，上海200030；3．中国科学院行星科学重点实验室，上海 200030；4.中国科学院国家空间科学中心空间环境探测研究室，北京 100190；5．北京市天基空间环境探测重点实验室，北京100190；6.中国科学院大学天文学院，北京100190；7．中国科学院国家授时中心，陕西 西安710600

# Theoretical Analysis of Soil Freeze/Thaw Process on DDM Waveform and Multipath

WUXuerui1,2.3， XIAJunming4.5, BAI Weihua4,5.6, Zhang Xinggang7

1. Shanghai Astronomical Observatory, Chinese Academy of Sciences, Shanghai 20oo30, China; 2. Key Laboratory of space navigation and position technology, Shanghai 2Ooo30,China; 3.Key Laboratory of Planetary Sciences， Chinese Academy of Sciences, Shanghai 2Ooo30, China; 4. National Space Science Center, Chinese Academy of Sciences, Beijing 100190, China; 5. Beijing Key Laboratory of Space Environment Exploration, Beijing 100190,China; 6. School of Astronomy and Space Science, University of Chinese Academy of Sciences, Beijing, 100190,China; 7. National Time Service Center,Chinese Academy of Sciences,Xi'an,710600, China

Abstract:In order to extend the applications GNSS-R/IR (GNSS-Reflectometry /Interferometric Reflectometry ） remote sensing technique to soil freeze/thaw process detection, soil(frozen/thawn) mixing permitivity models are employed to calculate the soil permittivity. Bistatic full-polarizationcoherentscattering model and random roughness surface scattering model are used to calculate the coherent and non-coherent scatering, which result in the variations of GPS multipath observables and DDM (Delay Doppler Map）waveforms,respectively.When the soil freeze/thaw process occurs,theoretical simulations indicate that soil freeze/thaw process induce the abrupt permitivity changes and affect the obvious variations of GNSS-R/IR signals.In this way, theoreticalfundamentals for soil freeze/thaw process detections are presented.

Key words:GNSS-R/IR,soil freeze/thaw process,Delay Doppler Map, multipath, bistatic, full polarization

Foundation support: Natural Science Foundation of China (NSFC) (Grant No. 41501384); the National Key R & D Program of China (Grant No.2017YB0502800 &2017YFB0502802)； the academician workstation foundation In Chifeng (Grant No.cfxyys201710)

# 摘要:

GNSS-R/IR(GNSS-Reflectometry/Interferometric Reflectometry)遥感是利用导航卫星反射信号或直射信号与反射信号的相干信号对地观测的新兴遥感方式，在国内外引起广泛关注。为将 GNSS-R/IR 技术的应用领域拓展到地表冻融状态的监测上，本文利用冻融土混合介质介电常数模型计算土壤介电常数，采用双站全极化相干反射率模型和随机粗糙面散射模型，分别计算了经冻融土反射的GPS 相干反射量的镜像反射率，以及GPS 非相干反射分量的漫散射特性；并模拟分析了冻融转换时，GPS多路径信息（GNSS-IR）以及包含漫散射信号的延迟多普勒图（GNSS-R）的变化特征。理论研究表明冻融转换过程中，地表介电常数的变化导致GPS 多路径信息和延迟多普勒图的明显变化。本文从散射机理上揭示了利用GNSS-R和GNSS-IR 遥感进行地表冻融特性监测的理论依据。

关键词：GNSS-R/IR，冻融地表，延迟多普勒图，多路径，双站全极化中图分类号：P237 文献标识码： 文章编号：

基金项目：国家自然科学基金青年基金（41501384)；国家重点研发计划（2017YFB0502800，2017YFB0502802)；赤峰学院院士专家工作站项目（cfxyys201710）

季节性冻土和永久性冻土约占地球陆地总面积的 $3 5 \%$ ，主要分布在高纬度和高海拔地区。陆地表层土壤冻融状态转换随季节每年重复发生，与人类生活环境密切相关，由于土壤中水的相态变化，这一过程强烈地影响着地表辐射能量的转换过程和地表径流的强度，是地表能量平衡和水分平衡的重要影响因素,也是气候变化的灵敏指示器,因此有效监测地表冻融状态的时空分布及其相关物理参数是冰冻圈、地学、水文学等研究领域的重要课题。

可见光和热红外遥感受天气条件限制，微波遥感却可以全天时全天候的观测。主/被动微波遥感（雷达/辐射计）是地表冻融状态监测的有效手段之一，星载观测将空前提高地表冻融监测的空间分辨率，但其时间分辨率 (每3天全球重复覆盖）与实际监测的科学需求之间存在一定的差距。

近年来，利用导航卫星的反射信号(GNSS-R)或直射信号和反射信号的相干信号(GNSS-IR)进行陆面参数遥感研究成为一种新兴的对地观测方式，GNSS-R/IR显著的低成本、小功耗、轻体积以及高时空分辨率等诸多优点可以成为现有地面站点观测和机载/星载遥感监测的有效有益补充[1,2]。

GNSS-R的工作模式分为散射计模式和高度计模式，针对GNSS-R 散射计模式，需要研制专门GNSS反射信号接收机对陆面参数进行遥感监测，在该种接收机的基础上利用其相关功率值遥感地物参数。目前陆地表面研究领域涉及土壤水分、植被含水量和生物量以及积雪厚度研究。

GNSS-IR遥感不需要研制专门的接收机，可以直接使用地球测绘或者地球物理的接收机对地表土壤水分、植被参数、积雪厚度和潮位变化进行遥感监测[3-6]。其空间分辨率约为1km：介于传统站点式传感器（ $< 1 \mathsf { m } ^ { 2 }$ ）和星载观测（ $> 1 0 0 \mathsf { k m } ^ { 2 }$ ）之间。利用从多路径观测数据中的有效反射计高度，幅度和相位信息可以提取相关地物参数。美国PBOH2O 研究团队将上述环境遥感产品每隔12 小时公布一次[7]，其土壤水分反演结果已被用做SMAP（SoilMoistureActivePassive）卫星的校验中[8]。

目前利用GNSS-R/IR进行地表冻融状态监测的研究相对较少，但利用GNSS-R/IR对地表冻融状态监测存在着可行性[9],是一种新兴的监测手段。研究者已经利用相关理论和IGS (International GNSSService）站点数据分析中进行了一些探索性研究[10,11]。本文详细阐述了利用GNSS-R/IR遥感方式进行地表冻融监测的理论机理。

针对星载观测，GNSS卫星群和专门的 GNSS-R反射信号接收机之间形成一种双站雷达的工作模式，接收机得到的DDM波形是用于反演地球物理参数的基本观测量。开发建立相应的仿真软件是开展卫星观测、数据仿真、实验设计，内插外推数据和反演等工作的重要关键机理工具[12,13]。目前，国内外的研究团队重点针对海况参数展开仿真分析，已经发展建立CYGNSS E2ES (cyclone global navigationsatellite systems mission end to end simulator(E2ES)）软件[14]，P2EPS（the PAU/PARISend-to-end performance simulator）仿真软件[15]和 GREEPS（an GNSS-R end-to-end performance simulator）仿真软件[16], SAVERS (a simulator of GNSSreflections from bare and vegetatedSoils）仿真软件则针对陆面土壤和植被特性研究而建立[17]。近期，研究人员在此Z-V 模型基础上[18]，发展建立了地表冻融转换DDM仿真分析模型[19]。

大多数的前向GPS多路径模型关注码调制，对于反射能量、相位和延迟采用任意值，或者基于给定几何计算反射延迟，亦或根据经验值定义反射能量。基于物理模型的前向GPS多路径模型，最早的是Zavorotny等人的模型[20]，该模型完全考虑了测绘接收机和天线的直射信号和反射信号的极化特性，采用分层的办法计算反射信号，并利用小波扰模型计算反射率，将介电常数转换为反射系数，最后把反射系数和指定的天线辐射样图耦合得到 SNRmpi(multipath Signal Noise Ratio）干涉图。基于Zavorotny等人的物理模型，Nievinski和 Larson 给出了一个全极化的前向 GPS多路径模型[2I]，该模型考虑了GPS广播信号的右旋和左旋圆极化信息、天线朝向、地表响应、伪码测距和噪声能量。本文在此模型基础上，发展建立了地表冻融状态转换模型。

本文将已有的DDM仿真分析模型和前向GPS多路径模型拓展到适宜进行地表冻融状态监测的理论模型，并以此模型为工具，模拟分析了地表冻融状态转换对DDM波形和多路径数据的影响，从散射机理上揭示了利用GNSS-R/IR遥感进行地表冻融特性监测的理论依据，为后续利用GNSS-R/IR方法进行地表冻融监测提供理论依据。

# 1．地表冻融转换时的电磁散射特性变化

物质的复介电常数是其固有属性，实部反应了不同介质表面发生的波的折射和反射现象；虚部则表示入射电磁波在介质中的衰减（吸收和转化）程度。本部分利用混合介电常数模型模拟分析了地表冻融转换时，介电常数以及其对应的各种极化条件下的反射信号的相干和非相干部分的散射特性变化情况。

# 1.1冻融转换导致介电常数差异

基于电磁波传输理论，冻结土壤可看做是由空气、固体颗粒、自由水、束缚水和冰五种物质组成的介电混合体，其复介电常数理论上受入射电磁波的频率、温度、土攘含水量等因素影响。最终介电常数可看做是各组分介电常数之和，如公式1所示。

$$
\varepsilon _ { m } ^ { \alpha } = \sum _ { i } V _ { i } \varepsilon _ { i } ^ { \alpha }
$$

其中， $\alpha$ 是形状常数因子， $\mathrm { \Delta V _ { i } }$ 是第i个组分的体积百分含量。本文土壤介电常数的实部和虚部可通过普遍采用的半经验模型Dobson 介电常数模型计算得到[22-24]。图1给出利用该模型模拟的不同土壤水分含量下，GPSL1载波频率，土壤介电常数实部和虚部随土壤温度的变化情况。从中可以看出当土壤从冻结状态转换到融化状态过程中，在各种土壤水分含量下，介电常数的实部和虚部均变化明显，在土壤温度大于 $0 ^ { \circ } \mathsf C$ 时，土壤水分含量对介电常数影响(实部，虚部）明显，在土壤温度小于0℃时，由于冰的存在，土壤水分对实部有影响但不明显，对于虚部的影响完全可以忽略。

![](images/eea912df719a6da3757d9174e55759345ed9fda33dd0bf300e81b540c5d03429.jpg)  
图1GPSL1载波频率时，在不同土壤水分含量下，介电常数实部（a）和虚部（b）随土壤温度的变化情况  
Fig.1 Dielectric constants (real part (a)and imaginary part (b)) versus soil temperature of GPS L1 carrier frequency at different soil moisture.

对于不同的GPS 载波频率，土壤的介电常数如表1所示，由表1可知在冻融转换时，GPS 载波频率（均为低频L波段）对介电常数的影响可以忽略，因此在后续模拟分析中只采用L1载波频率时的介电常数开展分析。

# 表1GPSL1，L2 和L5 载波频率下冻 $( - 1 \ ^ { \circ } \mathsf { C } )$ 融 $( 1 ~ ^ { \circ } \mathsf C )$ ）土壤的介电常数

Tab.1 Dielectric constants of GPS L1,L2 and L5 frequency band as soil change from frozen $( - 1 ~ ^ { \circ } C )$ to thawn state $( 1 \ ^ { \circ } \mathsf C )$ 0   

<html><body><table><tr><td></td><td colspan="2">L1 载波频率</td><td colspan="2">L2 载波频率</td><td colspan="2">L5 载波频率</td></tr><tr><td>Ts(℃)</td><td>实部</td><td>虚部</td><td>实部</td><td>虚部</td><td>实部</td><td>虚部</td></tr><tr><td>-1</td><td>8.66769</td><td>1.03403</td><td>8.70793</td><td>1.16876</td><td>8.71293</td><td>1.19762</td></tr><tr><td>+1</td><td>21.10970</td><td>3.54415</td><td>21.27701</td><td>3.49827</td><td>21.29776</td><td>3.51016</td></tr></table></body></html>

# 1.2冻融转换时圆极化反射率变化情况

在考虑相位的情况下，利用极化合成的方法 $\sigma _ { _ { R R } } = \sigma _ { _ { L L } } = \left( \frac { \left( \left| \boldsymbol { r _ { \nu } } \right| ^ { 2 } + \left| \boldsymbol { r _ { h } } \right| ^ { 2 } \right) } { 4 } - \frac { 1 } { 2 } \operatorname { R e } \left( \boldsymbol { r _ { \nu } } r _ { h } ^ { * } \right) \right)$ 计算得到RR和LR 极化下的反射率[25,26]

$$
\sigma _ { { \scriptscriptstyle R L } } = \sigma _ { { \scriptscriptstyle L R } } = \left( \frac { \left( \left| r _ { \nu } \right| ^ { 2 } + \left| r _ { h } \right| ^ { 2 } \right) } { 4 } + \frac { 1 } { 2 } { \mathrm { R e } } \left( r _ { \nu } r _ { h } ^ { * } \right) \right)
$$

$\sigma$ 为镜像双站雷达散射截面，下角标R、L分别代表 RHCP（RightHand Circular

Polarization） 和 LHCP（Left hand circularpolarization）极化状态。r为镜像反射系数，下标 $\mathbf { v }$ 和h分别代表垂直极化和水平极化。

![](images/6e81381f6f8870fc5c8fd74ff8d3d3bc77ce596df568407da681651e1ba81b0c.jpg)  
图2.地表冻 $( - 1 ^ { \circ } \mathsf { C } )$ 融 $\left( 1 ^ { \circ } \mathsf { C } \right)$ 时，圆线(VR/HR）（a）/圆（RR/LR）(b)极化BRCS变化

Fig.2 Circular-linearly(VR/HR)(a) and circularly (RR/LR)(b)BRCS as soil change from frozen to thawn state

图2给出了当土壤温度分别为 $\cdot 1 ^ { \circ } \mathsf { C }$ （冻结）和 $1 ^ { \circ } \mathsf { C }$ （融化）时，圆极化和圆线极化在同极化和交叉极化下的BRCS（BistaticRadarCrossSection）变化情况。由图可知，在布鲁斯诺角附近，VR极化存在BRCS最低点，VR 极化在小仰角，即 $1 ^ { \circ } \mathsf { C }$ 布鲁斯诺角之前， $- 1 ^ { \circ } \mathsf { C }$ 的BRCS高于 $1 ^ { \circ } \mathsf { C }$ ，而在 $\cdot 1 ^ { \circ } \mathsf { C }$ 布鲁斯诺角之后， $1 ^ { \circ } \mathsf { C }$ 时的BRCS高于- $\cdot 1 ^ { \circ } \mathsf { C }$ 的BRCS;在图2中给出的仰角范围内， $- 1 ^ { \circ } \mathsf { C }$ 时的BRCS高于 $1 ^ { \circ } \mathsf { C }$ 的BRCS（两条BRCS交叉线之间），在BRCS交叉线之后和第二个布鲁斯诺角之前， $1 ^ { \circ } \mathsf { C }$ 的BRCS高于 $\cdot 1 ^ { \circ } \mathsf { C }$ ：RR极化随着仰角的增加，BRCS增加， $1 ^ { \circ } \mathsf { C }$ 的 BRCS 高于 ${ \boldsymbol { \cdot } } 1 ^ { \circ } { \boldsymbol { \mathrm { C } } }$ 的 BRCS；LR 极化的BRCS随着仰角增加而降低， $- 1 ^ { \circ } \mathsf { C }$ 的BRCS高于 $1 ^ { \circ } \mathsf { C }$ 的BRCS。

# 1.3冻融转换时BRCS变化

实际地表为随机粗糙表面，入射的导航卫星信号经地表散射后，散射能量中的非相干部分不可忽视。而常用的随机粗糙地表的面散射模型有KA（KirchhoffApproach）模型、SPM（Small Perturbation Method）模型、IEM (Integrated Equation Model)模型以及AIEM(Advanced Integrated Equation Model)模型。AIEM模型是在IEM模型的基础上的改进模型，形式更为复杂，但是模型的精度得到了提高，AIEM模型的基本形式可以概括为三项之和：基尔霍夫项 $\boldsymbol { \sigma } _ { r t } ^ { k }$ ，基尔霍夫补偿项 $\boldsymbol { \sigma } _ { r t } ^ { c }$ 和二者的交叉项 $\sigma _ { r t } ^ { k c }$ ，如公式4所示。公式中 $\boldsymbol { \sigma } ^ { 0 }$ 为双站雷达散射截面， $\mathsf { q }$ /p分别为接收和发射时的极化状态[27]。

$$
\sigma { \it _ { q p } } ^ { \circ } = \sigma { \it _ { q p } } ^ { k } + \sigma { \it _ { q p } } ^ { k c } + \sigma { \it _ { q p } } ^ { c }
$$

图3是利用极化合成方法计算得到的地表冻融转换时各种极化BRCS的变化情况。在地表从冻结到融化转换的过程中，BRCS在各种极化和角度时，变化差异明显，即观测几何中的天顶角和方位角以及观测的各种极化都会导致冻融转换时BRCS 的变化。如何从角度和极化信息中有效提取冻融转换敏感参数是后续研究重点内容之一。

![](images/7e2e8018e8f2a86a592df69dc625eda9330212f18f11ce500b1f1b243d7d2bc7.jpg)  
图3.冻 $( - 1 ^ { \circ } \mathsf { C } )$ 融 $( 1 ^ { \circ } \mathsf { C } )$ 转换时各种极化（线极化、圆极化）下BRCS变化差异

Fig.3 BRCS differences as the soil temperature changes from frozen state $( - 1 ^ { \circ } \mathsf { C } )$ to thawn state $( 1 ^ { \circ } \mathrm { C } )$ at linear polarization (VV、HH and VH) and circular polarization(RR and RL)

# 2.冻融转化时GNSS-R/IR接收机信号变化

# 2.1多路径信息变化

当地物参数，如积雪厚度、植被含水量、土壤水分变化时，会引起地球测绘或者地球物理的 GPS 接收机的多路径信息的变化(SNR、相位和伪距）。因此，可以利用直射信号和反射信号的相干多路径数据对地物参数进行反演。

Nievinski和Larson发展建立了可以同时考虑GPS信号极化、天线和地表响应的全极化前向GPS 多路径模型[21]。

$$
\mathbf { P } _ { \mathrm { d } } = P _ { d } ^ { R } G _ { d } ^ { R } W _ { d } ^ { 2 }
$$

$$
\mathbf { P } _ { r } = P _ { d } ^ { R } \left| X S W _ { r } \right| ^ { 2 }
$$

$\mathrm { ~ \bf ~ P ~ }$ 代表电场能量， $\mathbf { G }$ 代表天线增益，W代表 Woodward 模糊函数，下标 $d$ 和 $\mathrm { ~ \bf ~ r ~ }$ 分别代表直射和反射分量， $\mathrm { \Delta } \mathrm { X }$ 是地表和天线耦合系数。

$$
{ \mathbf { X } ^ { \mathrm { R } } } { = } { \mathbf { R } ^ { \mathrm { s } } } \sqrt { G _ { r } ^ { R } } \exp \left( i \Phi _ { r } ^ { R } \right)
$$

$$
{ \bf X } ^ { L } { = } { \bf R } ^ { X } \sqrt { G _ { r } ^ { L } } \exp \Bigl ( i \Phi _ { r } ^ { L } \Bigr )
$$

脚标 $R$ 和 $L$ 分别为 RHCP 和 LHCP极化. $\Phi$ 为干涉相位. ${ \bf R } ^ { \mathrm { s } }$ 和 ${ \tt R } ^ { \tt X }$ 分别为同极化和交叉极化发射系数，是H极化和V极化的线性组合。

图4给出了当地表冻融转换时，天线高度为 $2 . 0 \mathrm { ~ m ~ }$ ，载波频率为GPSL1时，采用TRM29659.00天线模型，模拟分析在上半部分为空气，下半部分为冻融土壤的多径反射情况下，多路径信息 (SNR，相位和伪距)的变化情况，以及其引起的相应的有效反射计高度的变化。从图4可以看出，当土壤温度发生冻结一融化转换时，会引起多路径幅度增加，以及有效反射计高度的增加。而这种冻融转换引起的多路径信息的变化，可以用于地表冻融转换监测。文章[28]中给出了实测GPS(AB33)和SNOTEL(ID958)站点分析结果，并探讨了相应影响因素及局限性。

![](images/fe291171578633059f73f6df7862b67605ab1bb11840027bf98b283330be9d56.jpg)  
图4.土壤温度（ $- 0 . 5 ^ { \circ } \mathrm { C } \mathrm { - } 0 . 5 ^ { \circ } \mathrm { C }$ ）对GPS多路径信息（SNR、相位和伪距）影响。图右侧列图采用LombScargle谱分析方法展示了相应结果  
Figure 4. Soil temperature effects on GPS multipath observations (GPS SNR,carrier phase,and code pseudorange).Lomb-Scargle spectrogram analysis is presented in the right panel. Soil temperature with $- 0 . 5 ^ { \circ } \mathrm { C }$ is shown in blue, $0 . 5 ^ { \circ } \mathrm { C }$ in pink.

# 2.2冻融转化时DDM波形变化：

式9），针对BRCS采用2.3部分的随机粗糙面模型，建立了适用于冻融土壤的DDM模型，并模拟分析了冻融转换前后，DDM波形的差异。

当地表发生冻融转换时，介电常数的变化会导致BRCS的变化，进而引起DDM波形的变化。本文在 Z-V 模型的基础上[18]（公

$$
\begin{array} { c } { { \displaystyle { \left| Y _ { r t } \left( \tau , f \right) \right| ^ { 2 } = \frac { \lambda ^ { 2 } } { \left( 4 \pi \right) ^ { 3 } } P _ { r } T _ { i } ^ { 2 } { \displaystyle \iint } \frac { G _ { T } \left( \theta _ { i } , \phi _ { i } \right) G _ { R } \left( \theta _ { s } , \phi _ { s } \right) } { R _ { R } ^ { 2 } R _ { T } ^ { 2 } } } } } \\ { { \displaystyle { \times \sigma _ { r t } ^ { 0 } \left( \theta _ { i } , \phi _ { i } ; \theta _ { s } , \phi _ { s } ; \Theta \right) \Lambda ^ { 2 } \left( \delta \tau \right) S ^ { 2 } \left( \delta f \right) d A } } } \end{array}
$$

Z-V 模型本质上为双站雷达的积分形式。 $P _ { T }$ 为 GNSS 卫星发射能量，其波长为λ，天线增益及散射点到发射机/接收机之间的距离分别用G和 $\mathtt { R }$ 表示，下标 $\mathrm { \Delta T }$ 和R分别代表发射机和接收机， $\sigma ^ { \circ }$ 则是积分区域A内的冻融地表的双站雷达散射截面，三角函数和 Sinc 函数分别用 $\Lambda$ 和 S表示，二者平方的积是双站雷达的模糊度函数。

当地表发生冻融转换时，DDM波形的变化如图5所示 (注：未进行归一化处理)，从中可以看出当冻融转换时，不同极化状态的DDM马蹄状波形存在着明显的差异。极化信息是进行冻融监测的重要指标信息，不同极化时，DDM 波形的最大值和最小值如表2所示。

表2.线极化和圆极化时BRCS的最大值和最小值  
Tab.2 Maximum and minimum BRCS differences at linear and circular polarizations   

<html><body><table><tr><td>Pol</td><td rowspan="3">VV</td><td rowspan="3">HH</td><td rowspan="3">VH</td><td rowspan="3">RR</td><td rowspan="3">RL</td></tr><tr><td>DDM differences</td><td></td></tr><tr><td>Max</td><td>7.28e-18</td></tr><tr><td></td><td>8.85e-18</td><td></td><td>0</td><td>0</td><td>0</td></tr><tr><td>Min</td><td>-1.54e-17</td><td>-1.40e-17</td><td>-4.57e-18</td><td>-8.40e-17</td><td>-9.93e-18</td></tr></table></body></html>

![](images/1f3fe286fe2e33301b8f51924061f17ed05c378ca373f03740f2e669d8a8eb0f.jpg)  
图5.地表冻融转换时下线各种极化的DDM波形差异

Fig.5 The DDM diffrences at linear (HH, VVand HV)and circular (RR and RL) polarization, when the bare soil changes from frozen sate and thawn state.

# 3讨论

依据。

本文从仿真模型角度分析了利用GNSS-R/IR技术进行地表冻融监测的理论

本文采用的冻融土介电常数模型为经过实际验证的较为经典的模型，理论模拟的结果与文章中的模拟完全一致[22-24]；各种极化的相干和非相干部分的双站散射特性，在模型验证时，采用的方法是将模型中椭倾角和椭率角修改为线极化角度，与原有模型进行比较，结果一致，因此本文用圆极化/圆线极化模拟分析冻融转换时BRCS差别；另外冻融GPS 多路径模型和DDM 波形的验证方法可参考文章[26,19]。

极化是电磁波重要特性，地表反射信号的极化信息携带地表重要信息，极化比是土壤水分反演和植被状态研究的重要信息参数[29.30]，地表冻融过程中，不同极化的反射信号的双站散射特性和DDM波形信息的差异性表明极化/极化比信息在地表冻融状态的监测领域具有重要前景。

GNSS-R/IR本质上是双站雷达，由于电磁波散射的空间异质性，在各个散射天顶角和方位角下，包含地物的不同信息，有效利用不同角度（天顶角和方位角）信息是提高地物监测时后向反演的重点和难点问题

${ \mathrm { G N S S } } { \mathrm { + R } }$ 遥感是指除了可以利用GNSS导航卫星群的反射信号进行遥感监测外，亦可以利用通讯卫星或数字广播卫星的反射信号遥感地物参数[31.32]，本文模拟分析时重点考虑GPSL1载波频率下的散射特性、多路径以及DDM差异，但同时本文所提及模型，同样为利用其他数字通讯卫星开展地表冻融监测提供了基本理论模型和依据。

土壤水分、积雪和植被都是复杂寒区冻融地表的重要地表参数，直接影响着相应多路径和DDM波形的变化，本文中给出了裸土情况下，地表冻融状态对 GNSS-R/IR 接收机信号的影响，复杂寒区地表的积雪、植被覆盖等是后续模型中发展的重点。

# 4结论

GNSS-R和 GNSS-IR是介于微波遥感和卫星导航技术的新兴多元交叉对地观测技术，近年来在国内外引起了广泛关注。本文将该种遥感方式的应用领域从现有的土壤水分、植被和积雪厚度研究拓展到地表冻融状态监测上。理论研究表明当地表发生冻融转换时，土壤介电常数存在较大差别，进而导致了各种极化下反射信号的相干分量和非相干分量在冻融前后变化差异明显。其中，多极化相干分量变化，为利用GNSS多径信号开展地表冻融监测的GNSS-IR 技术提供了理论依据；非相干分量极化状态的变化，为利用漫散射信号的DDM波形开展地表冻融监测的 GNSS-R 技术提供了理论依据。

参考文献   
1. Zavorotny V U, Gleason S, Cardellach E,et al. Tutorial on Remote Sensing Using GNSS Bistatic Radar of Opportunity[J]. IEEE Geoscience & Remote Sensing Magazine,2015, 2(4):8- 45.   
2.Cardellach E,Fabra F, Nogués-Correig O,et al. GNSS-R ground-based and airborne campaigns for ocean, land, ice,and snow techniques: Application to the GOLD-RTR data sets[J]. Radio Science, 2016, 46(6):1-16.   
3.Larson, K. M. GPS interferometric reflectometry: applications to surface soil moisture, snow depth,and vegetation water content in the western united states: GPS interferometric reflectometry. Wiley Interdisciplinary Reviews Water[J].2016.   
4. Chew C. Soil Moisture Remote Sensing using GPS-Interferometric Reflectometry[D]., Gradworks, 2015.   
5．汉牟田，张波，杨东凯,等．利用 GNSS 干涉信号振荡幅度反演土壤湿度[J]．测绘学报, 2016,45(11):1293-1300. HAN Mutian, ZHANG Bo, YANG Dongkai, et al. Soil moisture retrieval utilizing GNSS interference signal amplitude[J].Acta Geodaetica et Cartographica Sinica,2016,45(11):1293-1300.   
6．张双成，南阳，李振宇,等.GNSS-MR 技术用于潮位变化监测分析[J]．测绘学报,2016, 45(9):1042-1049. ZHANG Shuangcheng，NAN Yang,LI Zhenyu, et al.Analysis of tide variationmonitoredbyGNSS-MR[J].ActaGeodaeticaetCartographica Sinica,2016,45(9):1042-1049   
7. Chew C C, Small E E, Larson K M, et al. Effects of Near-Surface Soil Moisture on GPS SNR Data:Development of a Retrieval Algorithm for Soil Moisture[J]. IEEE Transactions on Geoscience & Remote Sensing, 2013, 52(1):537-543.Jackson T, Colliander A, Kimbal J, et al. Science data calibration and validation plan—SMAP[J]. 2016,1,6   
8. WU Xuerui, JIN Shuanggen. Method and device for monitoring freeze-thaw state of earth surface.China,201410326132.3[P].2016-07-05(吴学睿，金双根.一种地表冻融状态的监测 方法及装置:中国，201410326132.3[P].2016-07-05)   
9.Wu, X., & Jin, S. Can we monitor the bare soil freeze-thaw process using gnss-r?: a simulation study. Spie,[J], 2014, 9246(01).   
10. Wu X, Chang L, Jin S, et al. Initial results for near surface soil freeze-thaw process detection using GPS-Interferometric Reflectometry[C]// Geoscience and Remote Sensing Symposium. IEEE,2016:1989-1992.   
11. Fung, A. K. Microwave scattering and emisson models and their applications. (1994).Artech House.   
12. Shi, J. C., Yang, D., Du, J.Y., et al. Progresses on microwave remote sensing of land surface parameters. Sci China Earth Sci[J],2012.55(7),1052-1078.   
13.Brien A. O.and Johnson T. J. Comparing the CYGNSS simulator forward scattering model with TDS-1 and CYGNSS on-orbit DDMS[C]// Geoscience and Remote Sensing Symposium. IEEE,2017,2657-2658   
14. Park H, Camps A,Pascual D,et al. A generic level 1 simulator for spaceborne GNSS-R Missions and application to Geros-ISS ocean reflectometry. IEEE Journal of Selected Topics In Applied Earth Observations and Remote Sensing.[J]. 2017.10(10):4645-4659   
15.Bai W H, Xia J M, Zhao D Y et al. GREEPS: an GNSS-R end-to-end performance simulator[C]// Geoscience and Remote Sensing Symposium. IEEE,2016,4831-4834   
16.Pierdicca, N., Guerriero,L., Giusto,R., et al.A. SAVERS: A Simulator of GNSS Reflections from Bare and Vegetated Soils. IEEE Trans. Geosci. Remote Sens.[J] 2014, 52, 6542-6554.   
17. Zavorotny, V.U. and A.G. Voronovich, Scattering of GPS signals from the ocean with wind remote sensing application. IEEE Transactions on Geoscience and Remote Sensing.[J]. 2000. 38(2): 951-964.   
18. Wu, X., Chang,L., Jin, S. A fullpolarization GNSS-R Delay-Doppler-Map (DDM) simulation for bare soil freeze/thaw process detection.remote sensing.[J].remote sensing, 2018,under review.   
19. Zavorotny, V. U., Larson, K. M., Braun, J. J., et al. A physical model for GPS multipath caused by land reflections: toward bare soil moisture retrievals. IEEE Journal of Selected Topics in Applied Earth Observations & Remote Sensing.[J].2010,3(1),100-110..   
20. Nievinski, F. G.，& Larson, K. M. Forward modeling of GPS multipath for near-surface reflectometry and positioning applications. GPS Solutions.[J].2013,18(2), 309-322..   
21. Dobson, M. C., Ulaby, F. T., Halikainen, M. T., et al. Microwave dielectric behavior of wet soil-part i: dielectric mixing models. IEEE Transactions on Geoscience and Remote Sensing.[J].1985, GE-23(1):35-46.   
22. Halikainen, M. T., Ulaby, F. T., Dobson, M. C.， et al. Microwave dielectric behavior of wet soil-part 1: empirical models and experimental observations. IEEE Transactions on Geoscience and Remote Sensing.[J].1985, GE-23(1):25-34.   
23. Zhang, L., Shi, J., Zhang, Z., et al. The estimation of dielectric constant of frozen soil-water mixture at microwave bands[C]// Geoscience and Remote Sensing Symposium. IEEE,2003, 4:2903-2905.   
24. Fung A K. Microwave Scatering and Emission Models and Their Applications[M]. Artech House,2009.   
25. Ulaby,F.T.and C.Elachi, Radar polarimetry for geoscience applications.Norwood, MA,Artech House, Inc., 1990.   
26. Chen, K. S., Wu, T. D., Tsang,L., et al. Emission of rough surfaces calculated by the integral equation method with comparison to three-dimensional moment method simulations.IEEE Transactions on Geoscience & Remote Sensing.[J]. 2003,41(1),90-101..   
27. Wu,X., Jin,S.,& Chang,L. Monitoring bare soil freeze-thaw process using gps-interferometric reflectometry: simulation and validation. Remote Sensing.[J].2017,10(1), 14.   
28. Zavorotny, V. U., & Voronovich,A. G. Bistatic GPS signal reflections at various polarizations from rough land surface with moisture content[Cl// Geoscience and Remote Sensing Symposium. IEEE,2000,7,.2852-2854.   
29. Zavorotny, V., Masters, D., Gasiewski, A., et al. Seasonal polarimetric measurements of soil moisture using tower-based GPS bistatic radar[C]// Geoscience and Remote Sensing Symposium. IEEE,2003,2, 781-783.   
30.Wu， X. R.， and S.G. Jin， GNSS-Reflectometry: Forest canopies polarization scattering properties and modeling, Adv. Space Res.[J].2014,54(5), 863-870.   
31. Torres, O., & Lawrence, R. Retrieval of Reflected Direct Broadcast Satellite (DBS) Signals for Earth Science Applications[C]// Geoscience and Remote Sensing Symposium. IEEE,2008, 5, 240 - 243.

32. Shah, R., Garrison, J.L.,& Grant, M. S.Demonstration of bistatic radar for ocean remote sensing using communication satelite signals. IEEE Geoscience & Remote Sensing Letters.[J].2012, 9(4), 619-623.

收稿日期：2018-01-22  
修回日期：2018-10-30

第一作者简介：吴学睿(1981-)，女，博士，副研究员，研究方向为GNSS-R遥感原理及应用First author: WU Xuerui (1981-)， female,Ph.D,associate professor, major in GNSS-Rremote sensing fundamentals and applications

E-mail: xrwu@shao.ac.cn 通讯作者：吴学睿 Corresponding author: WU Xuerui E-mail:xrwu@shao.ac.cn