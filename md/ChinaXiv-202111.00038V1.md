# MSAS系统中国区域航空服务性能分析

邵搏，张键\*，熊帅

（中国电子科技集团公司第二十研究所，西安，710068）

摘要：本文在介绍了国际星基增强系统（SBAS）的发展现状的基础上，梳理分析了日本MSAS系统的发展历程与当前服务能力。分析发现，MSAS的服务区域能够对我国东部地区形成覆盖。文中，对 MSAS电文类型和民航用户定位保护级计算方法阐述后，通过实际飞行试验对其在我国东部区域的实际服务性能进行了评估。评估结果表明，在我国东部地区，MSAS 增强定位精度优于LPV-250指标要求（水平 $1 6 \mathrm { m }$ ，垂直 $2 0 \mathrm { m }$ )；NPA可用性、连续性均达到 $100 \%$ ；用户保护级水平满足完好性指标要求。MSAS在我国东部地区有效的增强定位与完好性保障能力，可使地区相关用户依据自身需要使用该服务；同时，MSAS 基于其本土有限的监测站就实现了服务区域的扩展，也为我国BDSBAS 服务范围的扩展和服务性能的提升提供参考。

关键词：MSAS、服务性能、飞行试验、NPA、LPV-250中图分类号：TN961 文献标志码：A

# Performance analysis of

# China regional aviation service of MSAS

SHAO Bo, ZHANG Jian\*, XIONG Shuai (The 20th Research institute of CETC, Xi'an 710068, China)

Abstract: Based on the introduction of the development of the international SBAS,this paper analyzed the development and service performance of MSAS. It is found that the service area of MSAS can cover the eastern region of China. After describing the MSAS message type and the calculation method of civil aviation user positioning and protection level, the actual service performance in the eastern region of China is evaluated through the actual flight test. The evaluation results show that in eastern China,the positioning accuracy of MSAS is better than that of LPV-250 （16m horizontally and $2 0 \mathrm { m }$ vertically); NPA availability and continuity reach $100 \%$ The user protection level meets the integrity requirements. MSAS effectively the positioning and integrity support capability in eastern China, so that relevant users in the region can use the service according to their own needs; At the same time,MSAS has realized the expansion of service area based on its limited local monitoring stations, which also provides a reference for the expansion of BDSBAS service area and the improvement of service performance in China.

Keywords:MSAS, Service performance, Flight test, NPA,LPV-250

收稿期:

基金项目：陕西省重点研发计划项目（项目编号2021ZDLGY08-01)；陕西省创新能力支撑计划项目（2021TD-03)；陕西省自然科学基础研究计划项目（项目编号2021JM-609)；中国电子科技集团有限公司产业发展资金项目（项目编号20201121）

作者简介：邵搏，男，高级工程师，研究方向：星基增强系统技术研究。  
E-mail:night_boris83 $@$ 163.com  
通讯作者：张键，男，工程师，研究方向：GNSS 高精度定位及SBAS 性能评估的研究。E-mail:jianzhang_1993 $@$ 163.com

# 1概述

卫星导航系统（GNSS）克服了传统仪表着陆系统（ILS）的不足，实现了全天候、全球范围的高精度连续导航功能。由于使用GNSS 的定位结果受到多种外部因素的影响，导致定位结果有时并不能真实的反映出飞机当前的真实位置，使得飞机在被引导的过程中会出现完好性风险[1]。

为了满足航空等高生命安全用户对精度和完好性的需要，出现了以GNSS为增强对象的星基增强系统（SBAS)。SBAS 通过一定数量的地面监测站对导航卫星进行连续跟踪观测，由主控站对观测数据进行处理后生成相应的差分改正数和完好性参数，并编排成增强电文后通过地球同步卫星（GEO）向服务范围内的用户播发[2]。用户使用增强电文中的差分改正数提升定位精度，利用完好性参数实现服务性能的完好性保证。

目前，正式运行的 SBAS 有美国的广域增强系统（WAAS）[2-4]、欧洲地球同步卫星导航增强服务系统（EGNOS）[5-6]、日本的探路者卫星增强系统（MSAS）[7-8]、印度的 GPS辅助型静地轨道增强导航系统（GAGAN）[9-10]；处于试运行阶段的 SBAS 有中国的北斗星基增强系统（BDSBAS）[1I-13]、俄罗斯的差分改正监测系统（SDCM）[14-15]、非洲及印度洋星基增强系统（A-SBAS）[16-17]；处于建设阶段的 SBAS 有韩国增强卫星系统（KASS）[18]、澳大利亚/新西兰的南部定位增强网（SouthPAN）[19]。国际各国 SBAS 的分布如图1所示。

![](images/4642d9b4850b461022c2939312930772a509538c8e218755a3602a4f41efdb96.jpg)  
图1国际各国SBAS分布示意图Fig1SBAS distributions

由图1可见，在我国周边正式提供服务的 SBAS 系统主要是日本的 MSAS 和印度的GAGAN。虽然GAGAN 系统已于 2015年4月实现了一类垂直引导进近（APV-I）服务[9-10],但2019年后，系统状态未见更新报道。MSAS却在不断的对系统进行更新升级，持续提升

服务性能。

MSAS 由日本民航局(JCAB)负责建设[2，第一阶段 MSAS 空间段由日本自主设计的 2颗MTSATGEO卫星构成，MTSAT-1R（PRN129）位于 $1 4 0 ^ { \circ } \mathrm { E }$ 和MTSAT-2（PRN137）位于$1 4 5 ^ { \circ } \mathrm { E }$ 。由于技术原因，MTSAT-1R未能正式运行，日本为了保留 PRN129 的使用权力，通过MTSAT-2同时使用PRN129和PRN137播发服务信号。地面段包括6个地面监测站（GMS）分别位于福冈、札幌、东京、那霸、神户和常陆太田，2个主控站（MCS）分别位于神户和常陆太田，主控站兼具注入功能，神户主控站负责向PRN129注入信息，常陆太田主控站负责向PRN137注入信息。MSAS第一阶段于2007年9月开始运行，提供非精密进近（NPA）服务，已经在日本51个机场公布了非精密进近飞行程序，并在25架区域运输飞机安装了MSAS 设备[7]。

随着日本准天顶卫星系统（QZSS）的发展，MSAS第二阶段将与QZSS 进行一体化建设，利用QZSS 系统提供MSAS 服务[8]。第二阶段MSAS 空间段由1颗QZS-3GEO 卫星构成，位于 $1 2 7 ^ { \circ } \mathrm { E }$ 使用 PRN129 和137播发增强电文[20]。地面段包括13个GMS 分别位于札幌、仙台、常陆太田、小松、神户、广岛、福冈、系满、种子岛、奄美大岛、石垣岛、宫古岛、父岛，2个MCS分别位于常陆太田和所泽，1个测试评估中心位于所泽，3个注入站分别位于常陆太田、种子岛和宫古岛[21]。

自2020 年4月起，MSAS 服务信息的播发通道由MTSAT-2卫星调整至QZSS 的QZS-3（GEO）卫星，由QZS-3同时使用PRN129和137播发服务信息。目前，JCAB正在开展决断高度250英尺垂直导航信标性能（LPV-250）服务能力的验证工作和决断高度200英尺垂直导航信标性能（LPV-200）服务能力的论证工作；MSAS 有望在 2023 年实现垂直导航信标性能（LPV）全阶段服务能力，将服务于全日本的83个机场（不包含2个军用机场）[22]。

# 2MSAS单频增强电文

MSAS对GPS进行增强，其播发的增强电文类型如表1所示：

表1MSAS 增强电文类型Table1MSAS Augmentation Message Types  

<html><body><table><tr><td>Type</td><td>Contents</td><td>Type</td><td>Contents</td></tr><tr><td>1</td><td>PRN Mask assignments</td><td>17</td><td>GEO satellite almanacs</td></tr><tr><td>2 to4</td><td>Fast corrections</td><td>18</td><td>Ionospheric grid point masks</td></tr><tr><td>6</td><td>Integrity information</td><td>25</td><td>Long term satellite error corrections</td></tr><tr><td>7</td><td>Fast correction degradation factor</td><td>26</td><td>Ionospheric delay corrections</td></tr><tr><td>9</td><td>GEO navigation message</td><td>28</td><td>Clock-Ephemeris Covariance Matrix Message</td></tr><tr><td>10</td><td>Degradation Parameters</td><td>63</td><td>Null Message</td></tr></table></body></html>

# 2.1误差修正

MSAS 增强电文类型 2-4播发快变改正数PRC（Pseudo RangeCorrection）和用户差分距离误差索引（UDREI)，用户仅可使用UDREI<14的卫星进行定位解算，以保证完好性要求。用户可直接对观测伪距修正如下：

$$
P R _ { c o r r e c t e d } ( t ) = P R _ { m e a s u r e d } ( t ) + P R C \big ( t _ { o f } \big ) + R R C \big ( t _ { o f } \big ) \times \big ( t - t _ { o f } \big )
$$

上式中，t为伪距观测时刻； $t _ { o f }$ 为最近的PRC 接收时刻； $P R _ { c o r r e c t e d } ( t )$ 为经 PRC 修正后的载波相位平滑伪距； $P R _ { m e a s u r e d } ( t )$ 为修正前的载波相位平滑伪距； $P R C \big ( t _ { o f } \big )$ 为接收的快变改正数； $R R C \big ( t _ { o f } \big )$ 为 $t _ { o f }$ 时刻用户计算的测距速率改正数（Range-Rate Corrections）。

MSAS 利用电文类型 25 播发慢变改正数，慢变改正数为被增强GPS 卫星的轨道位置（ECEF坐标系)改正数和钟差改正数。用户可直接在广播星历解算得到的GPS卫星位置与钟差上进行修正，如下：

$$
[ X \quad Y \quad Z ] _ { c o r r e c t e d } ^ { T } = [ X \quad Y \quad Z ] _ { L 1 C / A } ^ { T } + [ \delta X \quad \delta Y \quad \delta Z ] _ { M S A S } ^ { T }
$$

上式中,[XYz]corrected为ECEF坐标系下经修正后的卫星轨道位置; $[ \boldsymbol { X } \quad \boldsymbol { Y } \quad \boldsymbol { Z } ] _ { L 1 } ^ { T }$ 为GPSL1 导航电文解算得到的ECEF 坐标系下卫星轨道位置； $\begin{array} { r l } { [ \delta X } & { { } \delta Y \quad \delta Z ] _ { M S A S } ^ { T } } \end{array}$ 为MSAS播发的单频慢变轨道改正数。用户星钟误差修正如下：

$$
( \Delta t _ { s v } ) _ { c o r r e c t e d } = ( \Delta t _ { s v } ) _ { L 1 } + \delta a _ { M S A S } - T G D _ { L 1 } + D C B _ { p 1 c 1 }
$$

上式中， $( \Delta t _ { s v } ) _ { c o r r e c t e d }$ 为经修正后的GPS 卫星钟差； $( \Delta t _ { s v } ) _ { L 1 }$ 为 GPS L1导航电文解算得到的卫星钟差； $\delta a _ { M S A S }$ 为 MSAS单频慢变钟差改正数； $T G D _ { L 1 }$ 为 GPS L1导航电文中的 TGD参数； $D C B _ { p 1 c 1 }$ 为 GPS 伪距硬件延迟偏差。

MSAS 通过电文类型18播发电离层格网掩码，电文类型26播发格网电离层垂直改正数和格网电离层垂直误差因子（GIVEI)，用户通过站星位置计算电离层穿刺点（IPP）后，在穿刺点周围搜索电离层格网点（IGP)后内插为用户视线方向电离层延迟。MSAS播发的 IGP分布如图2所示。

![](images/ef3a065a981d9debd78ea1431f10d746d36d9ab26f8ab7ec2927c60748db7638.jpg)  
图2MSAS电离层格网点分布图  
Fig 2MSAS IGP distribution map

# 2.2定位及保护级解算

在修正过轨道/钟差和电离层误差后，使用加权最小二乘法进行定位解算。观测方程几何矩 $G$ 阵的第i行如下：

$$
G _ { i } = [ - c o s E l _ { i } s i n A z _ { i } \quad - c o s E l _ { i } c o s A z _ { i } \quad - s i n E l _ { i } \quad 1 ]
$$

上式中， $E l _ { i }$ 为第i颗卫星的高度角； $A z _ { i }$ 为第 $\mathrm { ~ i ~ }$ 颗卫星的方位角。则用户加权最小二乘解如下：

$$
\hat { x } = ( G ^ { T } \cdot W \cdot G ) ^ { - 1 } \cdot G ^ { T } \cdot W \cdot y
$$

上式中， $\hat { x }$ 为用户的位置和钟差估计值； $y$ 为经修正后的伪距残差值；W为权矩阵，如下：

$$
W = \left[ \begin{array} { l l l l } { w _ { 1 } } & { 0 } & { \cdots } & { 0 } \\ { 0 } & { w _ { 2 } } & { \cdots } & { 0 } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { 0 } & { 0 } & { \cdots } & { w _ { N } } \end{array} \right] , w _ { i } = 1 / \sigma _ { i } ^ { 2 }
$$

$$
\sigma _ { i } ^ { 2 } = \sigma _ { i , f l t } ^ { 2 } + \sigma _ { i , U I R E } ^ { 2 } + \sigma _ { i , a i r } ^ { 2 } + \sigma _ { i , t r o p o } ^ { 2 }
$$

上式中， $\sigma _ { i , f l t } ^ { 2 }$ ，のiUIRE， $\sigma _ { i , a i r } ^ { 2 }$ ， $\sigma _ { i , t r o p o } ^ { 2 }$ 可由 MSAS 播发的UDREI、GIVEI 和空域、时域降效参数等参数计算得到。

投影矩阵S如下：

$$
S = ( G ^ { T } \cdot W \cdot G ) ^ { - 1 } \cdot G ^ { T } \cdot W = \left[ \begin{array} { c c c c } { S _ { e a s t , 1 } } & { S _ { e a s t , 2 } } & { \cdots } & { S _ { e a s t , N } } \\ { S _ { n o r t h , 1 } } & { S _ { n o r t h , 2 } } & { \cdots } & { S _ { n o r t h , N } } \\ { S _ { U , 1 } } & { S _ { U , 2 } } & { \cdots } & { S _ { U , N } } \\ { S _ { t , 1 } } & { S _ { t , 2 } } & { \cdots } & { S _ { t , N } } \end{array} \right]
$$

则有下式：

$$
\begin{array} { r } { d _ { m a j o r } = \sqrt { \frac { d _ { e a s t } ^ { 2 } + d _ { n o r t h } ^ { 2 } } { 2 } + \sqrt { \left( \frac { d _ { e a s t } ^ { 2 } - d _ { n o r t h } ^ { 2 } } { 2 } \right) ^ { 2 } + d _ { E N } ^ { 2 } } } } \end{array}
$$

$$
\begin{array} { r } { d _ { e a s t } ^ { 2 } = \sum _ { i = 1 } ^ { N } s _ { e a s t , i } ^ { 2 } \sigma _ { i } ^ { 2 } , d _ { n o r t h } ^ { 2 } = \sum _ { i = 1 } ^ { N } s _ { n o r t h , i } ^ { 2 } \sigma _ { i } ^ { 2 } , d _ { E N } ^ { 2 } = \sum _ { i = 1 } ^ { N } s _ { e a s t , i } s _ { n o r t h , i } \sigma _ { i } ^ { 2 } \circ 1 \qquad \mathrm { ~ a s \ } \qquad \rho \geqslant \rho \ \geqslant \rho \ \gamma . } \end{array}
$$

$$
d _ { U } = \sqrt { \sum _ { i = 1 } ^ { N } s _ { U , i } ^ { 2 } \sigma _ { i } ^ { 2 } }
$$

计算得到 $d _ { m a j o r }$ 和 $d _ { U }$ 后，保护级可由下式得到：

$$
H P L _ { S B A S } = \big \{ { K _ { H , N P A } } \cdot d _ { m a j o r }
$$

$$
V P L _ { S B A S } = K _ { V } \cdot d _ { U }
$$

上式中， $K _ { H , N P A } = 6 . 1 8 ~ , ~ K _ { H , P A } = 6 . 0 , ~ K _ { V } = 5 . 3 3 \circ$ （20

# 3MSAS服务范围分析

MSAS 的服务群体主要是具有高生命安全需求的民航用户，其服务性能正在从NPA 向LPV-250 逐渐过渡。根据国际民航组织标准与建议措施的规定，NPA服务和LPV-250服务的精度、完好性、连续性和可用性的指标要求如表2所示[24]。

表2NPA和LPV-250 服务性能要求Table 2NPA and LPV-25O service performance requirements  

<html><body><table><tr><td>Service</td><td>Accuracy HPE/VPE</td><td>Integrity risk</td><td>Integrity HAL/VAL</td><td>Alarm time</td><td>Continuity</td><td>Availability</td></tr><tr><td>NPA</td><td>220 米/--</td><td>1×107/小时</td><td>556米/--</td><td>10秒</td><td>1-10-4 ~1-10-8/小时</td><td>0.99~0.99999</td></tr><tr><td>LPV-250 (APV-I)</td><td>16 米/20米</td><td>2x107/进近</td><td>40米/50米</td><td>10秒</td><td>1-8×10/15 秒</td><td>0.99~0.99999</td></tr></table></body></html>

利用MSASPRN137在2020年9月18日的增强电文，以空间分辨率 $\cdot \overset { \circ } { \boldsymbol { 1 } ^ { \circ } } \times \boldsymbol { 1 } ^ { \circ }$ ，时间分辨率30s，绘制了MSAS的NPA服务范围和LPV-250 服务范围，如图3所示[25]。

![](images/402b559717352f6b276cf6066c3b48175f37fada7e4e907ce81227d386b1d692.jpg)  
图3MSASNPA（左）和LPV-250（右）服务覆盖范围 Fig 3MSAS NPA (left) and LPV-25O (right) service coverage Map

由图3（左）可见，MSAS的NPA 服务已经对日本全境实现了覆盖，与其现在对外宣布的服务能力相匹配。同时，也对我国东部区域形成了覆盖。由图3（右）所示结果，目前MSAS 的LPV-250 服务尚不具备正式服务的能力，与其正在进行LPV-250 服务验证的工作状态相符合，该服务依然可覆盖我国东部地区，但其可用性低于 $70 \%$ 。

# 4服务性能飞行验证

为了进一步分析MSAS在我国东部区域的航空服务性能，于2020年9月18日和9月25 日在辽宁省沈阳市法库县财湖机场进行了两次航空飞行试验，分别模拟民用航空飞机在进近阶段与航路阶段的飞行状态。

航空飞行试验使用小型通航飞机。试验中使用两台诺瓦泰接收机，通过后处理RTK 的方式获得飞机的真实轨迹，其中一台架设在机场附近作为基准站，另一台做为流动站安装在通航飞机上。同时，通航飞机上还安装了一台 Septentrio PolaRx5 接收机，与流动站共用航空天线，采集GPS 观测数据、GPS 导航电文以及MSAS 增强电文。

# 4.1进近阶段飞行试验

2020年9月18日进行的飞行试验持续约2小时15分钟，通航飞机在机场上方半径 $1 0 \mathrm { k m }$ 的空域内进行了多次起飞降落、五边飞行和大圆飞行，用来模拟民用航空飞机在进近阶段的飞行状态。进近阶段飞行试验的飞行轨迹如图4所示。

![](images/a8fcdcbcf392edcf1676a1bec9b6a76b952e447eb2322e87ab680301abd2b53e.jpg)  
图4进近阶段飞行测试飞机航迹图  
Fig 4A map of the aircraft's tracks for the near-stage flight test

# 4.1.1定位精度

以第2节所述方法进行MSAS增强定位解算，将增强结果与后处理RTK参考位置比较，对通航飞机在飞行试验过程中的水平、垂直误差分布与 $9 5 \%$ 分位数进行统计分析，如图5所示。

![](images/8b860dc389cfadd173090081030d4adb16dc5896add1da5300dcda2f9aba307c.jpg)  
图5进近阶段飞行测试MSAS单频增强定位水平（左）、垂直（右）误差直方统计图 Fig 5The MSAS HPE(left) and VPE(right) histogram for flight testing in the near stage

根据误差统计，进近阶段飞行试验中MSAS 的水平定位精度（ $9 5 \%$ ）为 $1 . 4 9 0 \mathrm { m }$ ，垂直定位精度（ $9 5 \%$ ）为 $2 . 0 4 2 \mathrm { m }$ ，满足表1中NPA 服务和LPV-250 服务的精度指标要求，表明MSAS所播发的慢变/快变改正数在我国东部空域依然具有用户定位增强作用。

# 4.1.2完好性

完好性要求保护级能够以一定的概率对定位误差实现包络，在服务层面一般使用完好性事件发生次数来描述[26]。针对 NPA 服务，完好性事件定义为水平定位误差（HPE）大于水平告警门限(HAL)且水平保护级（HPL）小于HAL 的情况。针对LPV-250 服务，完好性事件定义为（1）HPE 大于HAL且HPL小于HAL；或者（2）垂直定位误差（VPE）大于垂直告警门限(VAL)且垂直保护级（VPL）小于VAL 的情况。进近阶段飞行试验中定位误差、保护级和告警门限关系如图6所示。

![](images/bf564d7b8b7912dd909ace75572703fb3bb4bf26e58f85a9cf97d58452efa481.jpg)  
图6进近阶段飞行试验中定位误差、保护级和告警门限关系图（左：NPA，右：LPV-250） Fig 6PE,PL and AL diagram in the near-stage flight test (left: NPA, right: LPV-250)

由图6结果可见，在飞行试验时段内保护级能将相应的定位误差完全包络，完好性风险发生概率为0，满足表1中 NPA 服务和LPV-250服务的完好性风险指标要求，表明 MSAS所播发的完好性参数在我国东部空域内依然可为用户提供完好性保障。

# 4.1.3可用性

对于可用性分析，通常将保护级小于告警门限的时间概率视为系统服务的可用性[26]。针对 NPA 服务，当HPL小于HAL时认为服务可用。针对LPV-250 服务，当HPL小于HAL且VPL小于VAL时认为服务可用。

基于图6中的保护级和告警门限对比，进近阶段飞行试验中NPA服务可用性和LPV-250服务可用性的统计结果分别为 $100 . 0 0 0 \%$ 和 $0 . 0 0 0 \%$ 。NPA服务的可用性能够满足表1中NPA服务的可用性指标要求。由于MSAS服务目前主要针对NPA进行设计，导致完好性参数较为保守，保护级过大，能够对定位误差进行包络但却超过了LPV-250 服务的告警门限，试验开展时间为当日7时15分至9时30分，该时段内计算得到的保护级均大于告警门限，使得LPV-250服务可用性不满足指标要求，等于 $0 . 0 0 0 \%$ 。

# 4.1.4 连续性

对于连续性分析，通常使用15 秒滑动窗法（如图7所示）进行连续性统计[27]。对于某个特定时刻，如果系统服务在当前时刻可用，但在接下来的15秒中至少有1秒系统服务变为不可用，则认为出现一次连续性事件。连续性为一段时间内样本总数与连续性事件之差除以样本总数。进近阶段飞行试验中NPA服务连续性和LPV-250 服务连续性统计结果如表2所示。

![](images/10cdf5692085e4e4b78cbb64c2c153648ad2dd3e08b2bcde605ca035928e25f0.jpg)  
图715秒滑动窗法示意图  
Fig715 second sliding window diagram

SBASNPA服务等级连续性要求为 ${ \mathrm { 1 - 1 0 } } ^ { - 4 } { \sim } { \mathrm { 1 - 1 0 } } ^ { - 8 } / \$ 小时，则每小时发生连续性事件的概率为$1 0 ^ { - 4 } { \sim } 1 0 ^ { - 8 }$ ，

$$
( 1 0 ^ { - 4 } { \sim } 1 0 ^ { - 8 } ) / 3 6 0 0 s = ( 1 0 ^ { - 4 } { \sim } 1 0 ^ { - 8 } ) \times \frac { 1 } { 2 4 0 } / 1 5 s
$$

则连续性为 $( 1 - 4 . 1 7 \times 1 0 ^ { - 7 } { \sim } 1 - 4 . 1 7 \times 1 0 ^ { - 1 1 } ) / 1 5 s \circ$

基于进近阶段飞行试验中每个时刻保护级和告警门限的对应关系，NPA服务连续性和LPV-250服务连续性的统计结果分别为 $100 . 0 0 0 \%$ 和 $0 . 0 0 0 \%$ 。

从 NPA 连续性指标（ $\cdot 1 { - } 1 0 ^ { - 4 } { \sim } 1 { - } 1 0 ^ { - 8 } /$ 小时）和LPV-250 连续性指标（ $\phantom { + } 1 { - } 8 { \times } 1 0 ^ { - 6 } / 1 5$ 秒）中可以看到，要的到准确的连续性评估结果，NPA的最小样本时长应为 $1 0 ^ { 4 } { \sim } 1 0 ^ { 8 } \mathrm { h }$ ，而LPV-250的最小样本时长应为 $1 0 ^ { 6 } / 8 { \times } 1 5 \mathrm { s } \{ \approx  5 2 0 . 8 \mathrm { h }$ 。因此虽然上述飞行试验MSASNPA服务连续性达到 $1 0 0 . 0 0 0 \%$ ，但仍需进行长期试验以完全验证连续性的正确性。

# 4.1.5 小结

MSAS应用于进近阶段的飞行试验服务性能统计如表3所示。

# 表3进近阶段飞行试验MSAS服务性能统计结果

Table 3The performance statistics of MSAS service in the near-stage flight test   

<html><body><table><tr><td>HPE(95%)/m</td><td>VPE(95%)/m</td><td>NPA Availability /%</td><td>NPA Continuity / %</td></tr><tr><td>1.490</td><td>2.042</td><td>100</td><td>100</td></tr><tr><td>NPA Integrity event</td><td>LPV-250 Availability /%</td><td>LPV-250 Continuity /%</td><td>LPV-250 Integrity event</td></tr><tr><td>0</td><td>0.000</td><td>0.000</td><td>0</td></tr></table></body></html>

从上述统计分析结果可以看到，MSAS 在沈阳试验区域内，其播发的GPS卫星轨道/钟差改正数和电离层改正数依然能够实现用户定位精度的提升，使水平/垂直精度满足民航用户 NPA与LPV-250 服务等级要求；且其提供的UDREI、GIVEI、空域降效参数和时域降效参数等完好性信息能够保证计算的保护级将定位误差完全包络，避免完好性事件发生；MSAS的NPA服务在我国东部地区具有应用潜力。

# 4.2航路阶段飞行试验

9月25日飞行测试持续约3小时55分钟，测试主要为转场飞行，飞行从财湖机场起飞，先向西南方向飞约 $1 8 0 \mathrm { k m }$ ，再向东南方向飞约 $1 8 0 \mathrm { k m }$ 到达第二机场，在第二机场不降落，通过场地后原路返回，返回财湖机场后进行大圆飞行降落，以模拟民用航空飞机进航路阶段飞行状态。飞行测试轨迹如图8所示。

![](images/5701abf290208555d21535d760a9f4449794554423ab406f294cb8a32260747e.jpg)  
图8航路阶段飞行测试飞机航迹图  
Fig 8Flight test aircraft track map of the route stage

采用 MSAS进行单频增强定位解算，航路阶段飞机定位误差直方统计图、保护级及告警门限分别如图9和图10所示。

![](images/a1ab1f6f4595bee0c82e2cba2f9dee2238a875a47342fdd517344c7cb2a99545.jpg)  
图9航路阶段飞行测试MSAS单频增强定位水平、垂直误差直方统计图 ig 9The MSAS HPE(left) and VPE(right) histogram for flight testing in the route stag

![](images/7f48f8c5480b2dcaf94df49255c84d9d6216851434704ebe11c2c52aee718c59.jpg)  
图10航路阶段飞行试验中定位误差、保护级和告警门限关系图（左：NPA，右：LPV-250） Fig10PE,PL and AL diagram in the route stage flight test (left: NPA,right: LPV-250)

表4航路阶段飞行试验MSAS服务性能统计结果  
Table 4The performance statistics of MSAS service in the route stage flight test   

<html><body><table><tr><td>HPE(95%)/m</td><td>VPE(95 %)/m</td><td>NPA Availability /%</td><td>NPA Continuity / %</td></tr><tr><td>1.267</td><td>3.290</td><td>100.000</td><td>100.000</td></tr><tr><td>NPAIntegrity event</td><td>LPV-250 Availability /%</td><td>LPV-250 Continuity / %</td><td>LPV-250 Integrity event</td></tr><tr><td>0</td><td>4.964</td><td>0.000</td><td>0</td></tr></table></body></html>

从图9、图10和表4所示结果，航路阶段MSAS 的服务性能与进近阶段性能基本一致。航路阶段，MSAS 电文播发的快/慢变改正数、电离层改正数、UDREI、GIVEI、空域降效参数和时域降效参数等依然有效，可为民航用户提供定位增强与完好性保障，且满足NPA 服务指标要求，但不具备LPV-250 服务能力。

# 5总结

本文整体简要介绍了世界范围内 SBAS 系统的发展现状，阐述了日本 MSAS 系统的发展阶段、系统组成及当前应用情况，详细介绍了用户使用MSAS单频增强电文实现定位增强和保护级计算方法，并根据实际的飞行试验数据初步测试了MSAS 在我国东部空域的系

统服务能力。测试结果表明：

（1）MSAS 所提供的服务等级与其官方宣布一致，仅能为民航用户提供NPA服务，其LPV-250等级服务处于建设阶段；（2）MSAS NPA 服务能够覆盖我国东部地区，其增强定位精度、可用性、完好性和连续性均满足国际民航组织指标要求，可为我国东部区域民航用户提供NPA服务。

对 MSAS系统的发展历程的总结、测试方法、测试结果的测试经验将有助于我国BDSBAS系统的建设和发展，实现BDSBAS服务范围的扩展和服务性能的提升；同时MSAS在我国东部地区有效的增强定位与完好性保障能力，可使地区相关用户依据自身需要使用其服务。

# 参考文献

[1]邵搏．混合星座导航系统的用户差分距离误差完好性关键技术研究[D].北京：北京航空 航天大学.2012. SHAO Bo. Research on Integrity Key Technology of User Differential Range Error for Mixed Constellation [D]. BeiJing: Beihang University,2012(in Chinese).   
[2]邵搏，耿永超，丁群，吴显兵．国际星基增强系统综述[J]．现代导航，2017，8(3): 157-161. SHAO Bo, GENG Yongchao, DING Qun, et al. Summarize of International Satellite Based Augmentation System [J]. Modern Navigation, 2017(3):157-161(in Chinese).   
[3] JASON B. Wide Area Augmentation System (WAAS) update [R]. SBAS IWG 30, Changsha, China,2016.   
[4]Ken Alexander, Don Wilkerson, Jason Burns. Wide Area Augmentation System Update [C]. International Civil Aviation Organization Navigation Systems Panel Joint Working Groups fifth meeting,Montréal, 15-24 October 2019.   
[5]European Satellite Services Provider (ESSP). EGNOS performance and LPV implementation status [R]. SBAS IWG 3O, Changsha, China, 2016.   
[6] NATHALIE R. EGNOS programme status [R]. SBAS IWG 30, Changsha, China, 2016.   
[7] MASASHIG.MSAS status [R]. SBAS IWG 30, Changsha, China, 2016.   
[8] HIDETSUGU W. MSAS status and future plan [R]. SBAS IWG 35,Australia, 2019.   
[9] Airports Authority of India (AAI). GPS Aided GEO Augmented Navigation (GAGAN) [R]. SBAS IWG 30, Changsha, China, 2016.   
[10] Airports Authority of India (AAI)GPS Aided GEO Augmented Navigation (GAGAN) [R]. SBAS IWG 31, Senegal, 2016.   
[11]中国卫星导航系统管理办公室．北斗卫星导航系统应用服务体系（1.0版）[S].2019 年 12月.

China Satellite Navigation Office (CSNO). The Application Service Architecture of BeiDou

Navigation Satellite System (Version 1.O) [S]. 2019 Dec (in Chinese). [12] Civil Aviation Administration of China (CAAC). The new service provider ID and UTC standard ID for BDSBAS [R]. ICAO NSP 4th Meeting,Montreal, Canada, 2017. [13] LIU Cheng，GAO Weiguang， SHAO Bo,et al.Development of BeiDou satelite-based augmentation system [J]. Navigation, 2021, 68(2): 405-417. [14] CSNO. SDCM [OL]. http://www.beidou.gov.cn/zy/kpyd/201710/t20171023_4777.html [15]ESA. SDCM [OL]. https://gssc.esa.int/navipedia/index.php/SDCM [16] ASECNA. SBAS for Africa and Indian Ocean initiative [R]. Twenty-Second Meeting for the AFI Planning and Implementation Regional Group,Ghana, 2019. [17] ASECNA. Update on “SBAS for Africa and Indian Ocean”(A-SBAS) development [R]. ICAO NSP Sixth Meeting, virtual meeting, 2020. [18] EUNSUNG L. Korea SBAS program [R]. SBAS IWG 30, Changsha, China, 2016. [19] Jeffrey Bollrd， Simon Reynolds. Southern Positioning Augmentation Network Program Update [R]. ICAO NSP Sixth Meeting, virtual meeting, 2020. [20] U.S. government .L1 C/A PRN Code Assignments. https://www.gps.gov/technical/prn-codes/L1-CA-PRN-code-assignments-2020-Oct.pdf [OL] [21] NEC. https://www.nec.com/en/global/solutions/cns-atm/navigation/msas.html [OL]. [22] Kuniyuki Matsuda， Yuto Miyasaka. MSAS Status Update. International Civil Aviation Organization Navigation Systems Panel sixth meeting,2-13 November 2020. [23] RTCA DO-229E. Minimum Operational Performance Standards for Global Positioning System/Satellite-Based Augmentation System Airborne Equipment [S]. December 15, 2016. [24] ICAO. International Standards and Recommended Practices Annex 1O Aeronautical Telecommunications Volume I. July 2018. [25]张键，邵搏，熊帅,等．北斗星基增强系统单频服务区域可用性评估[J].导航定位与授时, 2021, 8(3):9. ZHANG Jian, SHAO Bo, Xiong Shuai, et al. Regional single frequency service availability evaluation of BDSBAS [J]. Navigation Positioning and Timing,2O21, 8(3):9 (in Chinese). [26] FAA. Wide Area Augmentation System (WAAS) Performance Analysis Report [R]. 2018. [27] ESSP. Service Provision Yearly Report (April 2017- March 2018) [R]. 2018.