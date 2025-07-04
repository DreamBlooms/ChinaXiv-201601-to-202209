# 全极化GNSS-R陆面参数延迟多普勒图模型

吴学睿 1,2,3，金双根1,2,31．中国科学院上海天文台，上海市 200030;2．上海市空间导航与定位技术重点实验室，上海市 200030;3．中国科学院行星科学重点实验室，上海市200030

Theoretical DDM Modeling of GNSS-R Fully Polarization Land Surface Geophysical Parameters WU Xuerui1,2,3, JIN Shuanggen1,2,3

1.Shanghai Astronomical Observatory, Chinese Academy of Sciences, Shanghai 2Oo030, China Key Laboratory of space navigation and position technology, Shanghai 2Ooo30,China

3． Key Laboratory of Planetary Sciences， Chinese Academy of Sciences, Shanghai 2Ooo30, China

Abstract: GNSS-R is a new promising remote sensing technique,which utilizes the reflected signals of GNSS constelltion to remotely sense the ocean or land surface.At present,most of the existing research are based on the experimental observations,few theoretical studies have been carried out.This paper has developed a fully polarization GNSs-R delay Doppler map for land geophysical parameters study.This theoretical model was based on the ocean surface GPS scattering model,after the modifications,it has been used for the land surface.As for thecalculations of land geophysical parameters (bare soil and vegetation),random surface scattering model and thefirst order radiation transfer equation model were used.Effects of bare soil and vegetation parameters on the delay Doppler maps were simulated.In order to usethe polarization information for backward inversion,our developed theoretical model has theabilityoffuly polarizations calculations,i.e.RR,LR,HR and VR pol.This theoretical modelis a mechanism toolforthe data explanation of spaceborne mision,experimental campaign design,data simulations and the backward inversion algorithm development.

Keywords: GNSS-R; delay-doppler map; bare soil; vegetation; polarization

Foundation support: Natural Science Foundation of China (NSFC)(Grant No.41501384); the National Key R& D Program of China (Grant No.2017YB0502800 &2017YFB0502802);the academician workstation foundation In Chifeng (Grant No.cfxyys201710).

# 摘要：

目前，针对GNSS-R的研究多从观测角度出发，对其散射机理研究相对较少。本文针对GNSS-R（GNSS-Reflectometry）反射信号陆面参数的延迟多普勒图理论模型展开研究，对于陆面参数（裸土、植被）的双站散射特性的计算采用修改后的随机粗糙面散射模型和零阶/一阶辐射传输方程模型。通过该模型模拟分析了裸土、植被参数变化时，相应的延迟多普勒图的变化。同时为利用极化信息进行相应地物参数的后向反演，模型中增加全极化计算功能。全极化 $G N S S + R$ 陆面参数延迟多普勒图理论模型的研究有助于星载数据的解释、地表实验设计、数据仿真和后向反演算法的开发。

关键词：GNSS-R；延迟多普勒图；裸土；植被；极化  
中图分类号：P237  
基金项目：国家自然科学基金青年基金（41501384)；国家重点研发计划资助（2017YFB0502800，  
2017YFB0502802)；赤峰学院院士专家工作站项目（cfxyys201710）

1、引言

GNSS-R是利用导航卫星的反射信号对地物参数遥感的新兴对地观测方式，在国内外引起广泛关注[1.2]。由于海洋表面相对均一，极化特性不明显，因此GNSS-R 在海洋领域的研究相对较早，较成熟[4,5]。针对陆面，目前国内外研究主要依赖于地面试验手段，建立GNSS-R信号或GPS 多路径数据与地表参数间的相关性，以研究其应用的可行性或者建立区域性的定量反演算法。

早期的 SMEX02实验中首次包含机载 GPS-R土壤水分实验，接收机天线仍然指向天底，但增加了接收机天线增益，以期获得更好的 SNR 数据，该实验验证了GPS 反射信号和土壤介电常数以及土壤体积含水量之间的关系，利用GPS 数据获取的介电常数和Wang-Schmugge理论模型吻合较好，但是均较低于实测土壤水分数据[5]。

随后的 BAO 塔实验[6]，接收机天线包含多种天线类型：低增益半球 LHCP 天线；4个高增益（\~12dB）V、H、LHCP（Right Hand Circular Polarization）和 RHCP 天线；为了分析极化特性对反射信号反演的影响，采用一阶 SSA（Smal Slope Approximation）模型计算土壤散射特性，但是由于过于简单的模型假设造成BAO 塔实验中的实测数据无法验证相应的理论模型。

GPS-IR 方法不需要研制专门接收机，直接采用地球物理或者地球测绘类接收机，即利用其多路径信息（直射信号和反射信号的相干信号）对地物参数进行遥感监测[7]。采用电磁单次散射前向模型验证近地表土壤水分和 SNR 相关量的变化关系[8]，研究表明地表5cm 以上区域的土壤水分变化会影响有效反射计高度、相位和幅度，浅层（<1-cm 深）的土壤水分变化对其影响最大，土壤质地类型的影响可以忽略，相位是土壤水分变化反演的最有效度量标准[9]。

IPT方法是利用测得的直射信号和反射信号的相干能量反演地形、植被覆盖区土壤水分和植被高度参数[10]，该种方法中接收到的能量信号中，凹槽位置、振幅以及个数与地物参数有关[11,12]，实际应用中利用其信息进行反演：地形反演精度是 $R M S E = 2 7 c m$ ；植被覆盖区土壤水分的精度为 $2 \% \sim 5 \%$ ；植被高度的反演精度为 $R M S E = 3 ^ { \sim } 5 c m$ 。

GNSS-R 的研究目的是实现星载观测,美国NASA的8星星座“飓风全球导航卫星系统”CYGNSS（Cyclone Global Navigation Satelite System）已经于2016年12月12 日成功发射，CYGNSS 星座发射的主要目的是利用GPS 直射信号和反射信号测量热带风暴和飓风期间海洋表面风场信息，同时CYGNSS 也为陆面参数及冰雪圈研究提供了重要契机[13]，其成功发射标志着 GNSS-R 星载计划走向业务化，CYGNSS 的接收机为 DMR（Delay Mapping Receiver），每个观测平台中包含一个 DDMI（Delay Doppler MappingInstrument）接收仪，接收机获得的是海面或陆面参数的 DDM 波形，而 DDM 波形是GNSS-R 技术反演地球物理参数的基本观测量，其仿真软件是开展GNSS-R 基本理论研究和项目工程参数设计的重要工具。

针对星载观测的仿真软件如 CYGNSS E2ES 软件[14](Brien et al.,2017)，P2EPS 仿真软件[15](Park et al.,2017)，GREEPS 仿真软件[16](Bai etal.,2016)均针对海洋表面参数建立。目前针对对陆地表面的 DDM 仿真系统较少。

本文目的是发展建立针对不同地物参数（裸土、植被）的全极化GNSS 反射信号模型。GNSS 直射信号经地表反射后，被专门的机载/星载GNSS-R接收机所接收，形成一种双站/多站雷达的工作模式。现有的地物参数微波散射模型，多是针对单站雷达的后向散射模型或者是针对辐射计的被动微波反射率模型[17]。因此针对GNSS-R遥感，需要对现有常规微波散射模型进行修改，使得模型具备双站散射计算能力[18]。

与传统单站雷达或者辐射计不同，导航卫星发射的为圆极化信号（如GPS卫星发射的为RHCP)，该信号经地表反射后，极性发生改变。由于电磁波的极化特性受目标物介电常数、物理特性、几何形状和取向等因素影响，对GNSS-R极化特性的研究有利于探测目标参数提取，因此本文发展建立了全极化散射模型。

在上述发展建立的双站全极化模型的基础上，发展建立了针对典型陆面参数（土壤水分、植被）的全极化DDM仿真模型。

文章中第二部分对发展建立的全极化GNSS-R反射信号陆面参数延迟多普勒图模型的具体理论和研究方法进行介绍，包括双站全极化散射模型和陆面GNSS 反射信号模型，即拓展的Z-V模型以及相应的工作流程；第三部分则给出了相应的模拟结果，包括裸土、植被相关参数变化时，相应的各种极化双站雷达散射截面的变化关系以及对应的延迟多普勒图的变化关系。第四部分对结果进行讨论，第五部分为总结。

# 2、理论及方法

本部分对全极化GNSS-R散射信号陆面参数物理模型的理论基础和工作流程进行介绍。包括计算裸土、植被覆盖地表的双站全极化散射模型，计算相应地物参数的GNSS-R 散射信号延迟多普勒图模型以及该理论模型的总体工作流程。

# 2.1双站全极化散射模型

对于裸土散射特性的计算分为两部分：假设地表足够光滑，可以用光滑表面的反射率模型对地表的散射特性进行描述。对于非相干部分的计算，采用随机粗糙面散射模型[19]。

$$
\scriptstyle { \mathcal { O } } _ { q p } ^ { 0 } = { \mathcal { O } } _ { q p } ^ { k } + { \mathcal { O } } _ { q p } ^ { k c } + { \mathcal { O } } _ { q p } ^ { c }
$$

式中， $\sigma ^ { \mathrm { { o } } }$ 表示双站雷达散射截面；下标 ${ \mathfrak { p } } , \ { \mathfrak { q } }$ 分别代表发射和接收的极化状态。该模型整体上分为基尔霍夫项 $\sigma _ { q p } ^ { k }$ ，基尔霍夫项的补偿项 $\mathcal { S } _ { q p } ^ { \mathrm { c } }$ 和两者的交叉项 $\sigma _ { \varphi } ^ { k c }$ 三项之和（公式1）。

对于植被散射特性的计算采用迭代算法求解辐射传输方程[17]：假定向上和向下传输的能量强度矩阵分别为 $1 ^ { + }$ ，十，可以通过辐射传输方程的一阶微分形式表示，如公式2-3

$$
\frac { d } { d z } I ^ { + } \left( z \right) = - k _ { e s } I ^ { + } \left( z \right) + F ^ { + } \left( z \right)
$$

$$
\frac { d } { d z } I ^ { - } \left( z \right) = k _ { e s } I ^ { - } \left( z \right) - F ^ { - } \left( z \right)
$$

式中

$$
\begin{array} { l } { { k _ { e s } = k _ { e } / \cos \theta _ { s } = k _ { e } / \mu _ { s } } } \\ { { \ } } \\ { { \mu _ { s } = \cos \theta _ { s } , \mu = \cos \theta } } \\ { { \ } } \\ { { I ^ { + } ( z ) = I ( z , \mu _ { s } , \phi _ { s } ) } } \\ { { \ } } \\ { { \Gamma ( z ) = I ( z , - \mu _ { s } , \phi _ { s } ) } } \end{array}
$$

式中对角矩阵 $k _ { s } , k _ { e }$ 分别为体散射系数矩阵和消光系数矩阵； $k _ { s s } = k _ { s } / \cos \theta _ { s }$ ， $P ( \mu _ { s } , \mu , \phi _ { s } - \phi )$ 为散射相位矩阵；辐射传输方程解的一阶积分方程形式如下：

$$
\begin{array} { l } { { \displaystyle I ^ { + } \left( z \right) = I ^ { + } \left( - d \right) e ^ { - k _ { e s } \left( z + d \right) } + \int _ { - d } ^ { z } F ^ { + } \left( z \right) e ^ { - k _ { e s } \left( z - { \bar { z } } ^ { * } \right) } d { \bar { z } } } } \\ { { \displaystyle I ^ { - } \left( z \right) = I ^ { - } \left( 0 \right) e ^ { k _ { e s } z } + \int _ { z } ^ { 0 } F ^ { - } \left( \dot { z } \right) e ^ { k _ { e s } \left( z - { \bar { z } } ^ { * } \right) } d { \bar { z } } } } \end{array}
$$

式中 $F ^ { \pm }$ 为向上向下传输的能量强度的函数。

$$
\begin{array} { c } { { F ^ { \pm } \left( z \right) { = } \displaystyle \frac { k _ { s s } } { { 4 } \pi } { \int _ { 0 } ^ { 2 \pi } { \int _ { 0 } ^ { 1 } { P \left( { \pm } { \mu _ { s } , \mu , \phi _ { s } - \phi } \right) I ^ { + } d \mu d \phi } } } } } \\ { { { + } \displaystyle \frac { k _ { s s } } { { 4 } \pi } { \int _ { 0 } ^ { 2 \pi } { \int _ { 0 } ^ { 1 } { P \left( { \pm } { \mu _ { s } , - \mu , \phi _ { s } - \phi } \right) I ^ { - } d \mu d \phi } } } } } \end{array}
$$

针对植被的辐射传输方程模型[20,21]，假定入射强度为 $I _ { i } \big ( \theta _ { i } , \varphi _ { i } \big )$ ，散射强度为 $I _ { s } \big ( \theta _ { s } , \varphi _ { s } \big )$ ，其中 $\theta _ { i } , \varphi _ { i }$ 分别是入射的天顶角和方位角， $\theta _ { s } , \varphi _ { s }$ 为散射的天顶角和方位角。

$$
I _ { s } \left( \theta _ { s } , \varphi _ { s } \right) = \frac { 1 } { r ^ { 2 } } L _ { m } \left( \theta _ { s } , \varphi _ { s } ; \theta _ { i } , \varphi _ { i } ; \theta _ { k } , \varphi _ { k } \right) I _ { i } \left( \theta _ { i } , \varphi _ { i } \right)
$$

入射能量被单散射体散射后，散射能量强度与入射能量强度之间可以通过修改的缪勒矩阵 $\mathrm { L } _ { \mathrm { m } }$ 联系（公式11)。 $\left( \theta _ { \boldsymbol { k } } , \varphi _ { \boldsymbol { k } } \right)$ 为单散射体朝向，r为散射强度与散射体之间的距离， $L _ { m }$ 为散射体的电场散射矩阵，由散射振幅S定义。

$$
\sigma _ { r t } \left( \psi _ { r } , \chi _ { r } , \psi _ { t } , \chi _ { t } \right) = 4 \pi \tilde { Y } _ { m } ^ { r } M Y _ { m } ^ { t }
$$

对于各种极化散射截面的计算采用极化合成的方法[22]（公式12)，式中 $\boldsymbol { Y } _ { m } ^ { \ t }$ 和 $\boldsymbol { Y } _ { m _ { m _ { } } } ^ { \ r }$ 分别为发射机和接收机的归一化斯托克斯矢量，通过对其中椭倾角和椭率角的变换，可以得到任意极化的雷达双站散射截面。

# 2.2全极化GNSS-R散射信号模型

早期的 Z-V 模型是应用海洋表面的相关函数和相关功率模型[23]，本质上是双站雷达的积分形式，是由收发分置的散射问题近似派生出来的，该模型最初是用来研究海洋表面风场，由基尔霍夫光学模型出发。本文发展建立的理论模型将其拓展用于裸土、植被延迟多普勒图仿真分析。重点对其积分区域、观测几何以及观测目标散射模型进行修改[24]。该模型可以描述在不同时间延迟和多普勒频移下GPS 反射信号的能量

$$
Y _ { s } \left( \hat { \tau } , \hat { f } \right) = \frac { T _ { \scriptscriptstyle { I } } ^ { 2 } P _ { \scriptscriptstyle { T } } \lambda ^ { 2 } } { \left( 4 \pi \right) ^ { 3 } } \iint \frac { G _ { \scriptscriptstyle { T } } \sigma ^ { 0 } G _ { _ { R } } } { R _ { \scriptscriptstyle { R } } ^ { 2 } R _ { \scriptscriptstyle { T } } ^ { 2 } } \Lambda ^ { 2 } \left( \hat { \tau } - \tau \right) \sin c ^ { 2 } \left( \hat { f } - f \right) d A
$$

式中 $Y _ { s }$ ：接收到的 GPS 反射信号能量，是时间延迟 $\hat { \tau }$ 和频率f的函数； $P _ { \scriptscriptstyle T }$ ：为 GPS 卫星发射的能量;（204 $G _ { \scriptscriptstyle T }$ ：发射机天线增益； $G _ { \scriptscriptstyle R }$ ：接收机天线增益； $R _ { R }$ ：接收机到地面反射点的距离； $R _ { T }$ ：发射机到地表镜像反射点的位置； $\lambda$ ：电磁波波长； $T _ { \scriptscriptstyle I }$ ：信号处理时采用的相干积分时间； $\sigma ^ { 0 }$ ：无维，双站雷达散射截面； $\Lambda \big ( \hat { \tau } - \tau \big )$ ：GPS 相关函数（三角函数）， $\hat { \tau } , \tau$ 分别为复制信号和入射信号延迟； $\mathrm { s i n } c ^ { 2 } \big ( \hat { f } - f \big )$ ：多普勒滤波函数， $\hat { \boldsymbol f } , \boldsymbol f$ 分别为复制信号和入射信号的频率；A:有效散射面积，接近闪烁区；dA:A 区域内的积分面积。

# 2.3理论方法流程图

GNSS-R 反射信号地物参数理论模型工作框架如图1所示，其中裸土和植被的双站雷达散射截面分别通过随机粗糙面散射模型和一阶辐射传输方程模型计算得到，由GPS卫星及相应的GNSS-R接收机的位置和速度信息计算得到卫星几何模型中所需参数，最后由全极化GNSS 散射信号模型计算得到相应地物参数的延迟多普勒图。

![](images/05dd0ab674bde2fc69603491155e122334d05cc5bb5b7df27539c429ef8cf627.jpg)

Fig.1 Flowchart of the fully polarimetric $G N S S + R$ delay Doppler map model for land geophysical parameters

# 3 模拟结果

在以下模拟中GPS 载波频率采用 L1波段，积分时间为O.001s。GPS 卫星（tx）和相应GNSS-R 接收机(rx)位置矢量(_pos 单位 $| \mathsf { k m } \rangle$ 和速度矢量(_vel单位 $m / s )$ 信息如下：${ \begin{array} { r c l } { { \mathrm { t x } } _ { - } { \mathrm { P o S } } } & { = } & { \left[ - 1 1 1 7 9 \ - 1 3 1 6 0 \ 2 0 3 4 2 \right] } \\ & & \\ { { \mathrm { t x } } _ { - } { \mathrm { v e l } } } & { = } & { \left[ 2 5 2 3 \ - 3 6 1 1 6 3 \right] ; } \\ & & \\ & & { } \\ { { \mathrm { r x } } _ { - } { \mathrm { P o S } } } & { = } & { \left[ - 4 0 7 0 \ - 3 5 8 3 \ 4 5 2 8 \right] ; } \\ & & \\ & & { } \\ { { \mathrm { r x } } _ { - } { \mathrm { v e l } } } & { = } & { \left[ - 4 7 3 8 \ - 1 7 9 6 \ - 5 6 5 5 \right] ; } \end{array} }$ ：

# 3.1裸土、植被DDM波形

地表模型输入参数（地表和植被）如表1所示。通过输入不同的植被和土壤参数可以获取其对双站雷达散射截面和最终的DDM 波形的定量影响结果。

![](images/fefd7bb472acc5dc8d0a8884a0c45c0fef964f2a3379d78f798773b0a0d1b2a8.jpg)  
图1.全极化 $G N S S + R$ 陆面参数延迟多普勒图理论模型工作流程图

表1.GNSS-RDDM地表模型输入参数。树冠层高度为11.00米，冠层密度为0.2棵树 $/ \mathfrak { m } ^ { 2 }$ 。Tab.1 Model inputs for GNSS-R DDM simulator. Canopy height is $1 1 . 0 0 \mathrm { m }$ ,canopy density is 0.2 trees/m  

<html><body><table><tr><td colspan="5">树冠层</td></tr><tr><td></td><td>树干</td><td>枝条</td><td>叶子</td><td>针状叶</td></tr><tr><td>介电常数 (/）</td><td>16.4+7.3j</td><td>16+7.3j</td><td>19+6j</td><td>27-12.43j</td></tr><tr><td>重力含水量（g/cm）</td><td>0.6</td><td>0.6</td><td>0.8</td><td>0.8</td></tr><tr><td>干物质密度（g/cm）</td><td>0.4</td><td>1.0</td><td>0.976</td><td>0.1</td></tr><tr><td>长度 (cm)</td><td>1600</td><td>200</td><td>0.02</td><td>1.7</td></tr><tr><td>半径 (cm)</td><td>20.08</td><td>2.0</td><td>4.0</td><td>0.1</td></tr><tr><td>密度(散射体/m)</td><td>0.2</td><td>3.4</td><td>85000</td><td>85000</td></tr><tr><td>地表层</td><td></td><td></td><td></td><td></td></tr><tr><td>介电常数（/)</td><td>6.3+1.6j</td><td></td><td></td><td></td></tr><tr><td>均方根高度(cm)</td><td>0.45</td><td></td><td></td><td></td></tr><tr><td>相关长度 (cm)</td><td>18.75</td><td></td><td></td><td></td></tr></table></body></html>

由三角函数∧和多普勒滤波函数 $S$ 分别确定的环形区和多普勒等值区如图2所示。

Fig.2 Illustration for time delay and Doppler shift.

以表1中相应参数作为模型的输入，在图2所示的时间延迟和多普勒频移下，植被的全极化双站散射截面示意图如图3所示。图3分别给出了不同极化（RR、LR、VR和 HR）的双站雷达散射截面图。从双站雷达散射截面图可以看出，在中心区域，即镜像散射点附近双站雷达散射面截较强，而在漫散射区域，相应的雷达散射特性较弱。相同时延和多普勒频处，不同极化的散射波形差异较大，因为在不同极化时，地物参数的散射特性差异较大。

![](images/b4ed168206a788b134bfd801e6a1222fe6f01acaa94079108687da218c3da11d.jpg)  
图2．时间延迟和多普勒频移示意图  
图3植被RR、LR、VR和HR极化双站雷达散射截面图

Fig.3 Vegetation bistatic radar cross section for RR、LR、VR and HR po

当模型中去掉树冠层，只保留地表层，即裸露地表的双站雷达散射截面的计算采用随机粗糙面散射模型计算得到。图4中给出植被和裸土全极化双站雷达散射截面差别示意图，不同极化的双站雷达散射截面差别较大。由于各散射点对应的观测几何的差异，图4中在各种极化的不同观测几何下，相应的双站雷达散射截面差不同，由于植被的衰减，植被双站雷达散射截面小于裸土的双站雷达散射截面，具体衰减程度与相应的观测角度有关。

![](images/f4ff38baf0656d96751801b7f1eda78d983f2e255d1b45ba7df6091d0e200579.jpg)  
图4.植被覆盖与裸土全极化双站雷达散射截面差别图

Fig.4 Bistatic radar cross section difference map for vegetation and bare so

图5 则是在不同极化时，对应的植被和裸土延迟多普勒散射信号能量差示意图。不同极化下，散射信号能量差别较大。因此可以有效利用极化信息进行地表和植被相关参数的监测和反演。由于地物参数的散射特性受观测几何（即散射的天顶角和方位角）影响较大，因此散射信号能量差在不同观测几何下呈现不同特性。

![](images/e2f095a84a5a33434651164a2ee90a1e0c7358f56849d355a17b0dd6ef8c0a1a.jpg)

针对裸土，该理论模型可以模拟分析地表土壤水分、地表粗糙度变化对延迟多普勒图的影响；针对植被，该理论模型可以模拟分析植被生长状况、生物量变化、植被含水量以及地表参数变化对延迟多图普勒图的影响。

# 4、讨论

目前的微波散射模型，多是针对辐射计的发射率模型或者是针对单站雷达的后向散射模型。GNSS-R遥感中 GNSS 导航卫星群和相应的反射信号接收机之间构成典型的双站雷达工作模式，因此计算时需要采用双站雷达模型，即模型需要可以计算任意散射方向（散射天顶角和方位角）的散射模型。本文计算裸土用的高级积分方程模型和计算植被的辐射传输方程模型均为双站雷达散射模型，在进行模型验证时，将该模型的角度（散射天顶角和方位角）修改为后向单站雷达的角度，得到的模型计算结果与未经修改的模型计算结果相同，以此表明各种角度（散射天顶角和方位角）的双站散射计算能力的正确性。

为降低电离层对 GNSS 卫星信号的影响，导航卫星群作为发射源发射右旋圆极化的信号，因此需要双站散射模型可以计算包含圆极化的全极化的计算功能，通过极化合成公式可知，归一化斯托克斯矢量中椭倾角和椭率角决定着不同极化方式，针对全极化的计算功能，将极化合成公式中的椭倾角和椭率角修改为线极化的角度，将发展建立的模型计算结果与原有未经修改的线极化模型的计算结果进行比较，以此验证全极化模型计算的正确性。

本文发展建立的全极化DDM 仿真模型是在原有海洋表面DDM 仿真模型的基础上发展建立的，模型验证时将双站雷达散射截面用相应的土壤水分或植被的双站雷达散射截面来替代，模拟结果的正确性验证时，需要验证原有海洋表面 DDM 仿真模型的双站雷达散射截面接口设置是否合理，因此将海洋表面的双站雷达散射截面作为接口处输入值，计算得到结果与原有模型结果相同，以此验证模型的正确性。

作为对地观测新方式，GNSS-R遥感的发展在国内外引起广泛关注。 $G N S S + R$ 是指除了利用导航卫星的反射信号以外，还可以利用其他数字通讯卫星的反射信号对地物参数进行遥感。GNSS-R遥感的一个特点就是不断变化的观测几何，而且其工作波段只有L波段。利用其反射计的思想，采用数字通信卫星的反射信号为例对海面粗糙度进行研究实验上验证了其应用的可行性[25,26]。由于数字通信卫星工作在微波频段，所以从理论上进行土壤水分监测和植被特性研究是可行的。但有必要对其散射机制进行研究，明确机理，并展开相应的实验。

本文发展建立的双站全极化散射模型频率覆盖范围为0.5-10GHz,观测入射天顶角大于 $1 0 ^ { \circ }$ ，在针对相应的导航卫星或者其他数字通讯卫星的三角函数和多普勒滤波函数的修改基础上，该模型可以拓展到$G N S S + R$ 的应用。本文中散射特性的研究为 $G N S S + R$ 相关接收机设计、数据仿真和定量反演算法的开发可以提供关键的机理工具，而给出的陆面参数（裸土、植被、冻融地表)的延迟多普勒图仿真分析模型为 $G N S S + R$ 的发展提供了一定的理论基础。

# 5、结论

GNSS-R工作模式本质上为双站雷达，接收机接收到的数据为延迟多普勒图。本文发展建立了全极化GNSS-R 陆面参数延迟多普勒图理论模型。该理论模型基于海洋表面的GNSS 散射信号模型，针对陆面的裸土、植被应用展开。相应地物参数双站雷达散射截面的计算分别采用修改后的随机粗糙面散射模型、零阶/一阶辐射传输方程模型。利用极化合成的方法使得微波散射模型可以计算各种极化的散射特性。当地表有无植被覆盖以及地表参数变化时，会导致各种极化下的雷达散射截面差异和延迟多普勒图的变化。该理论还可以用来计算土壤水分、植被生长状况，生物量或者含水量变化时，延迟多普勒图的变化情况。该延迟多普勒图理论模型可以计算各种极化下，相应地物参数的延迟多普勒图的变化，有利于利用极化信息来提取相应地物参数的有效信息。基于微波散射机理的延迟多普勒模型的理论研究工作有助于星载 GNSS-R 观测数据的解释和分析，并有利于后向反演算法的开发，其研究结果也为 $G N S S + R$ 陆面遥感的发展奠定一定的理论基础。

# 参考文献

[1].Zavorotny V U,Gleason S,Cardelach E,et al.Tutorial on Remote Sensing Using GNSS Bistatic Radarof Opportunity[J]. IEEE transaction on Geoscience and Remote Sensing, 2016,4(2):8-45.

[2].JIN Shuanggen,Cardellach E,andXIEFeiqin.GNSSRemote Sensing:Theory, MethodsandApplications[M].New York, London: Springer, 2014.

[3]GleasonST,HodgartS,Yiping S,etal. Detectionand processingofbi-staticall reflected GPS signals from low Earth orbit for ocean remote sensing[J].IEEE transaction on Geoscience and Remote Sensing,2OO5,43(6):1229- 1241.

[4].M.Martin-Neira,S.D'Addio,C.Buck,etal.ThePARISoceanaltimeterin-orbitdemonstrator[J].IEEEtransaction on Geoscience and Remote Sensing,2011, 49(6): 2209-2237.

[5] KatzbergSJ,Torres O,GrantMS,etal. Utilizing calibratedGPSreflectedsignals toestimatesoilreflectivityand dielectric constant: Results from SMEX02[J]. Remote Sensing of Environment, 2006,100(1):17-28.

[6] Zavorotny VU,Voronovich A G. Bistatic GPS signal reflections at various polarizations from rough land surface with moisture content[Cl// Geoscience and Remote Sensing Symposium,2000.Proceedings.IGARSS 2000.IEEE 2000 International. IEEE, 2000:2852-2854 vol.7.

[7] Larson K M. GPS interferometric reflectometry: applications to surface soil moisture,snow depth，and vegetation water content in the western United States:GPS interferometric reflectometry[J].Wiley

Interdisciplinary Reviews Water,2016.

[8] ZavorotnyVU,Larson KM,BraunJJ,etal.A Physical Model for GPS Multipath Caused by Land Reflections: Toward Bare Soil Moisture Retrievals[J].IEEE Journal of Selected Topics in Applied Earth Observations &Remote Sensing,2011, 3(1):100-110.

[9] Chew C，Small E E，Larson K M.An algorithm for soil moisture estimation using GPS-interferometric reflectometry for bare and vegetated soil[M]. Springer-Verlag New York,Inc. 2016.   
[10]Rodriguez-Alvarez N,Camps A,Vall-Llossera M,et al.Land Geophysical Parameters Retrieval Using the Interference Pattern GNSs-R Technique[J]. IEEE Transactions on Geoscience & Remote Sensing,2010,49(1):71-84. [11] Rodriguez-Alvarez N,Bosch-Lluis X，Camps A,et al. Soil Moisture Retrieval Using GNSS-R Techniques: Experimental Results Over a Bare Soil Field[J].IEEE Transactions on Geoscience & Remote Sensing，2009, 47(11):3616-3624.   
[12]Rodriguez-AlvarezN,MonerisA,Bosch-LuisX,etal.SoilmoistureandvegetationheightretrievalusingGNR techniques[C]//Geoscience and Remote Sensing Symposium,2009 IEEE International,igarssIEEE,2010:Il-69- I1-872.   
[13] Ruf C S,Gleason S,Jelenak Z,et al.The CYGNSS nanosatelite constellation hurricane mission [C],IEEE International Geoscience and Remote Sensing Symposium, Munich, Germany, 2012,214-216.   
[14] O'BrienA,JohnsonJT.Comparing the cygnss simulator forward scattering model with TDS-1 andcygnss onOrbit DDMS[C]// IGARSS 2017 - 2017 IEEE International Geoscience and Remote Sensing Symposium. IEEE, 2017:2657-2658.   
[15] Park H,Camps A,Pascual D,etal.AGeneric Level1 Simulatorfor Spaceborne GN-RMissionsandApplication to GEROS-ISS Ocean Reflectometry[J].IEEE Journal of Selected Topics in Applied Earth Observations & Remote Sensing,2017, PP(99):1-15.   
[16] BaiW,XiaJ,ZhaoD,etal.GREEPS:AnGNSS-REnd-to-End Performance Simulator[C]//GeoscienceandRemote Sensing Symposium. IEEE, 2016:4831-4834.   
[17].Tsang L., Kong J.A., Shin R.T. Theory of microwave remote sensing [M]. NASA.1985.   
[18].Wu,X.R.,and S.G.Jin.GNSs-Reflectometry: Forest canopies polarization scattering propertiesand modeling [J], Advance in Space Research.2014, 54(5):863-870.   
[19].Chen,K.S.,T.D.Wu,L.Tsang,etal.Emisionofrough surfaces calculatedbythe integral equation method with comparison to three-dimensional moment method simulations[J].IEE Transactions on Geoscience and Remote Sensing, 2003,41(1): 90-101.   
[20].UlabyFT, Sarabandi K,McDonald K,etal.Michiganmicrowave canopy scatering model[J],International

Journal of Remote Sensing,1990,11:1223-1253.

[21].Liang P,PierceLE,and Moghaddam M.Radiative transfer modelfor microwave bistaticscatering fromforest canopies[J].IEEE Transaction on Geoscience and Remote Sensing, 2005,43: 2470-2483.

[22].UlabyFT,and Elachi C.Radar polarimetryfor geoscience applications[M].Norwood,MA,USA: Artech House Publishers,1990.

[23].Zavorotny V U and Voronovich A G.Scattering of GPS signals from the ocean with wind remote sensing application. IEEE Transactions on Geoscience and Remote Sensing.20oo,38 (2): 951-964.

[24].Wu X R and Jin S G.Simulations and analysis of BeiDou Navigation Satelite System (BDS)-Relectometry DelayDoppler Maps for vegetation[C]. Proceeding of China Satelite Navigation Conference,2014,1:87-95.

[25].Torres Oand Lawrence R.Retrieval of Reflected Direct Broadcast Satelite (DBS) Signals for Earth Science Applications[C]. IEEE International Geoscience and Remote Sensing Symposium,2008,V240-V243.

[26]. Shah R,Garrison JLand Grant M S.Demonstration of bistatic radar for ocean remote sensing using communication satelite signals [J].IEEE transaction on Geoscience and Remote Sensing Lettrs,2012,9(4): 619- 623.

第一作者简介：吴学睿（1981-)，女，博士，副研究，研究方向为GNSS-R遥感原理及应用Email:xrwu@shao.ac.cn

Firstauthor:WU Xuerui(1981-),female，Ph.D,AssociateProfessor,majorin GNSS-Rremote sensing fundamentals   
and applications   
注：图2，图5请彩印