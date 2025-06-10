# GEO卫星的VLBI快速高精度定位观测

李 婷1,²，童锋贤1,3，郑为民1,3,4.5，张娟1,3  
（1.中国科学院上海天文台，上海 200030；2.中国科学院大学，北京100049；3.中国科学院射电天  
文重点实验室，江苏 南京 210008；4.国家基础学科公共科学数据中心，北京100190；5.上海市导航定位重点实验室，上海200030）

摘要：卫星对地观测及导航定位的快速发展对地球同步轨道(Geostationary Earth Orbit,GEO)卫星的定轨精度有了米级甚至更高的需求。本文研究利用甚长基线干涉（VeryLong BaselineInterferometry，VLBI）时延数据进行GEO卫星快速定位的方法。首先对 VLBI时延进行理论精度分析，然后利用中国VLBI网进行GEO卫星观测试验及数据相关处理，最后利用短时VLBI时延数据完成对 GEO卫星的定位计算。针对时延中存在与测站和基线相关的异常值问题，本文提出了相应的检测校正方法。数据经校正后重新处理，得VLBI残余时延测量精度约0.16ns，等效于约0.58米的卫星横向位置误差。本文的研究可用于GEO卫星的快速高精度定位及轨道快速恢复。

关键词：差分VLBI；GEO卫星；精度分析；时延校正；快速高精度定位中图分类号:P161.5 文献标识码：A 文章编号：xXXX-XXXX-(2021)x-XXXX-XX

# 0 引言

地球同步轨道（Geostationary Earth Orbit，GEO）卫星轨道高约 36000 公里，绕地公转周期与地球自转周期一致，一定范围内相对地面点静止，在大地测量、导航定位和灾害监测等方面发挥重要作用。由于GEO卫星运动中受各种摄动力影响，特别是其太阳能翼板受到的太阳光压摄动大，使卫星的实际轨道发生漂移，偏离平衡点[]。为减少轨道误差对用户定位精度的影响，需尽快获取卫星准确位置信息，因此研究GEO卫星机动后的位置快速测量方法具有重要意义。

目前对GEO卫星视向位置测量主要依靠测距技术，包括伪距和载波相位测量、转发式测距测量和激光测距等。高精度测距需卫星转发测距信号，为主动式测量，定轨精度百米量级[2。制约测距定轨精度的因素与GEO卫星特点有关：卫星轨道高，地面跟踪站构网范围相对较小，导致观测网几何结构略差；相对静止特性使得星站间动力学和几何约束变弱，造成钟差和测站偏差等系统误差解算困难；为维持同步轨道，卫星需频繁轨控，但星上发动机推力不易建模，造成后续轨道恢复和预测困难[2]-[4]

对GEO卫星轨道平面位置测量可采用光学成像或射电干涉等被动式测量方法，这些方法优点为仅需接收卫星下行信息，不占用星上资源。拥有独立本振的甚长基线干涉（Very Long BaselineInterferometry，VLBI）技术是一种射电干涉测量技术，因其具有超高测角分辨率和灵敏度，已被广泛应用于深空探测器跟踪测量[5]。VLBI对确定卫星横向（垂直于卫星轨道径向平面）位置具有高灵敏度，可提供观测目标角位置的几何约束。差分VLBI技术通过快速交替观测目标探测器和邻近致密射电源，利用信号差分可有效减少介质时延、仪器时延、测站钟差等测量误差，测角精度优于毫角秒[6]-[7]

联合使用 VLBI技术与测距技术可进一步提高GEO 卫星的三维位置解算精度。1984年 TadashiShiomi采用差分VLBI技术与无线电测距对GEO卫星进行联合定轨试验得到卫星轨道精度约100米[8]。近年来国内学者也开展了对GEO卫星的仿真试验和实测研究。2003 年舒逢春利用双差单向测距（Delta Diferential One-way Ranging，△DOR）和双差单向测速两种差分 VLBI技术，开展我国首次GEO 卫星的VLBI实测试验，获得卫星信号干涉条纹，未进行实际卫星定位定轨计算。试验△DOR总误差约41cm，理论上相当于用 $2 0 0 0 \mathrm { k m }$ 基线观测地球同步轨道目标时 $\mathrm { 8 m }$ 的位置误差[9]。2006年杜兰进行数值仿真试验表明，在测距观测中增加VLBI辅助观测数据，理论上有望将GEO卫星轨道精度提高至米级[3]，未开展实测试验。2011年黄勇利用C 波段转发式测距数据和 VLBI时延数据进行综合定轨试验，定轨后时延数据残差均方根值约3.6ns，时延率约0.4ps/s，相当于轨道横向位置误差约 $1 0 \mathrm { m } ^ { \left[ 1 0 \right] }$ 。2017 年弓剑军利用宽带 VLBI系统与轨道跟踪和转移测定系统观测GEO 卫星，得到约0.14ns 的时延形式误差，同一时间段重复定轨结果的中误差在米量级[11]，为结果的内符合精度评估。前述试验结果均未与观测目标事后精轨比较，准确度暂无法衡量。

鉴于卫星轨控后轨道恢复时间长、偏差大，且对GEO卫星定轨精度的要求越来越高，因此，研究 GEO 卫星位置的快速高精度测量技术，具有重要现实意义。我们组织中国VLBI网（ChineseVLBI network，CVN）所属4个台站观测GEO卫星，并利用VLBI短时观测的时延测量数据对GEO卫星进行定位计算。CVN由天马（Tm）、北京（Bj）、昆明（Km）、乌鲁木齐（Ur）4观测站和位于上海的数据处理中心组成，含6条观测基线。本文首先从理论上对GEO卫星VLBI时延观测精度进行分析，然后利用约4小时的 S 波段VLBI时延数据进行卫星定位计算。同时文中详细描述了VLBI时延结果中的异常值检测和校正方法，并利用校正后的VLBI时延数据和新开发的后处理程序重新进行GEO卫星定位计算，通过定位结果验证时延跳变的校正效果。将计算结果与国际全球导航卫星系统服务组织（Intermational Global Navigation Satelite Systems Service，IGS）提供的事后精轨数据进行比较，可作为定位结果的外符合准确度估计。

# 1 卫星差分VLBI观测原理与精度分析

# 1.1 卫星差分VLBI观测原理

VLBI 观测量为时延和时延率，即两个地面天线接收同一信号的时间延迟和时间延迟变化率，包括群时延（率）和相时延（率）。差分VLBI技术即选取目标探测器附近位置精确已知的致密射电源作为参考源，交替观测参考源及目标探测器。一般要求两者角距小于 $1 0 ^ { \circ }$ [12]，观测频率越高，可用的角距范围越大。通过两信号差分，可有效减少时延测量误差。差分VLBI几何关系示意图如图1所示。图中1、2 为两观测台站， $\vec { B }$ 为两台站组成的基线矢量，为台站观测射电源方向矢量， $\overrightarrow { r _ { 1 } }$ 、 $\overrightarrow { r _ { 2 } }$ 为台站观测卫星方向矢量， $\tau$ 为射电源观测时延。

![](images/5fc236d93de48ca9141c1be077c309b507b4ddd022df3a9037d9b49946591b11.jpg)  
图1差分VLBI原理示意图   
Fig.1 Schematic Diagram of Differential VLBI Principle

测量时，按照"参考源-目标卫星-参考源"的顺序观测，在 $t _ { 1 }$ ， $t _ { 2 }$ ， $t _ { 3 }$ 时刻对应的VLBI时延值分别为 $\tau ^ { q } ( t _ { 1 } )$ ， $\tau ^ { s } ( t _ { 2 } )$ ， $\tau ^ { q } ( t _ { 3 } )$ ，上标 $q$ 表示参考源观测， $s$ 表示卫星观测。通过插值可得到 $t _ { 2 }$ 时刻参考源观测量 $\tau ^ { q } ( t _ { 2 } )$ 。在 $t _ { 2 }$ 时刻，有如下关系

$$
\tau ^ { q } ( t _ { 2 } ) = \tau _ { g } ^ { q } ( t _ { 2 } ) + \tau _ { e r r } ^ { q } ( t _ { 2 } )
$$

$$
\tau ^ { s } ( t _ { 2 } ) = \tau _ { g } ^ { s } ( t _ { 2 } ) + \tau _ { e r r } ^ { s } ( t _ { 2 } )
$$

其中， $\tau _ { \mathrm { g } }$ 为几何时延，可以由台站坐标、观测源坐标和地球定向参数等先验值计算得到。 $\tau _ { \mathrm { e r r } }$ 为观测中的系统误差和随机误差项之和，包括介质时延、钟差、仪器时延和观测噪声等。差分VLBI时延观测值为

$$
\Delta \tau = \tau ^ { s } ( t _ { 2 } ) - \tau ^ { q } ( t _ { 2 } ) = \tau _ { g } ^ { s } ( t _ { 2 } ) - \tau _ { g } ^ { q } ( t _ { 2 } ) + \varepsilon _ { \tau }
$$

$$
\varepsilon _ { \tau } = \tau _ { e r r } ^ { s } ( t _ { 2 } ) - \tau _ { e r r } ^ { q } ( t _ { 2 } )
$$

因 $\tau _ { e r r } ^ { s } ( t _ { 2 } ) \backprime \tau _ { e r r } ^ { q } ( t _ { 2 } )$ 为同一时刻观测误差值，可认为钟差和仪器时延等近似相等，又因观测间隔时间短且参考源和目标探测器角距近，所以介质时延相差小。因此，差分得到的 $ { \varepsilon } _ { \tau }$ 为极小误差项，消除了VLBI观测中无法被精确建模的共同误差源影响，得到卫星的实际VLBI时延值 $\tau ^ { s } ( t _ { 2 } )$

$$
\tau ^ { s } ( t _ { 2 } ) \approx \tau ^ { q } ( t _ { 2 } ) + \Delta \tau
$$

$\tau ^ { s } ( t _ { 2 } )$ 包括的卫星的位置信息，可用于定位。

# 1.2 时延精度与卫星位置误差分析

为评估卫星位置解算精度，需对VLBI测量精度进行理论分析。VLBI时延测量误差主要包括射电源源位置、台站位置、地球自转参数和介质等带来的系统性误差，以及观测源噪声、氢原子钟不稳定度、介质扰动和仪器相位抖动等带来的随机误差[13]。

射电源源位置误差VLBI观测时从国际天球参考架优先选择位置精度高的点源，因此系统误差中的源位置时延误差是一个与源本身位置精度和投影基线长有关的极小量。估算公式为[13]

$$
\varepsilon _ { \Delta \tau } = \frac { B _ { p } } { c } \varepsilon _ { \vartheta }
$$

$B _ { p }$ 为基线在天空平面投影的长度， $\scriptstyle \varepsilon _ { \vartheta }$ 为河外源位置误差， $\boldsymbol { c }$ 为光速。大部分源的位置精度在0.5-2.0nrad，对投影长度 $3 0 0 0 \mathrm { k m }$ 的基线，射电源位置误差0.75nrad时，由射电源位置误差带来的时延误差约为0.0075ns。

台站位置误差 台站位置时延误差可用基线在天球面的投影误差表示，与射电源和卫星夹角有关，表示为[13]

$$
\varepsilon _ { \Delta \tau } = \frac 1 c ( \Delta \theta ) \ \varepsilon _ { B L }
$$

$\Delta \theta$ 为射电源和卫星夹角， $\varepsilon _ { B L }$ 为基线投影误差，假定射电源和卫星夹角0.2rad，基线投影误差0.02米，则由台站位置误差带来的时延误差约为0.0067ns。

地球定向参数误差地球定向参数对时延的影响主要由模型计算时坐标系转换时引入，取决于UT1和极移参数的精度，与卫星和参考源间夹角成比例，关系为[13]

$$
\varepsilon _ { \Delta \tau } = \frac 1 c ( \Delta \theta ) \varepsilon _ { U T P M }
$$

εuTPM为地球定向参数UT1和极移的误差，为一极小值，假定射电源和卫星夹角 $0 . 2 \mathrm { r a d }$ ，球定向参数为0.02米，则由其产生的时延误差约为0.0067ns。

中性大气系统误差 该误差与台站天顶方向的干湿对流层误差及台站观测目标高度角有关，近似关系如下[13]

$$
\varepsilon _ { \Delta \tau } = \frac { \rho _ { z } } { c } \left. \frac { 1 } { s i n \gamma _ { s } + 0 . 0 1 5 } - \frac { 1 } { s i n \gamma _ { q } + 0 . 0 1 5 } \right.
$$

Ys、 $\gamma _ { q }$ 分别为台站观测卫星和射电源的高度角， $\rho _ { z }$ 为天顶方向的干湿对流层误差。假设卫星高度角 ${ 4 0 } ^ { \circ }$ ，射电源高度角 $3 9 ^ { \circ }$ ，天顶方向的干对流层误差为 $0 . 0 0 2 \mathrm { m }$ ，天顶方向的湿对流层误差为$0 . 0 0 5 \mathrm { m }$ ，两个台站干湿对流层影响产生的时延误差约为0.0075ns。

电离层系统误差电离层系统性误差对时延误差的影响较复杂，可由Klobuchar模型简略计算，若观测台站周围布设有双频GPS 接收机可获得更准确的台站天空电离层信息。VLBI观测电离层时延误差影响的典型值为 $0 . 0 2 \mathrm { n s }$ 。

卫星热噪声误差 GEO 卫星热噪声与卫星信号信噪比、观测通道带宽和积分时间等有关，近似

关系为[13]

$$
\varepsilon _ { \Delta \tau } = \frac { \sqrt { 1 2 } } { 2 \pi \Delta f _ { B W _ { q } } S N R _ { s } }
$$

$\Delta f _ { B W _ { q } }$ 为卫星观测带宽， $S N R _ { s }$ 为卫星信号信噪比。GEO卫星数传信号通常为带宽10MHz 的单通道观测，假定卫星信噪比1000，则卫星热噪声带来的时延误差约0.0551ns。

台站钟不稳定度误差 氢原子钟不稳定性带来的误差具体可用目标交替观测间隔内的台站钟频率稳定性表示，公式为[13]

$$
\varepsilon _ { \Delta \tau } = T _ { s - q } \varepsilon _ { \Delta f / f }
$$

$T _ { s - q }$ 为射电源和卫星交替观测时间， $\varepsilon _ { \Delta f / f }$ 为站钟的稳定性，若探测器和河外源观测时间间隔为600s，钟频率稳定度为 $1 0 ^ { - 1 4 }$ ，则其时延影响为0.0060ns。

仪器相位抖动误差仪器相位抖动产生的时延误差与信号总带宽近似成反比，关系为[13]

$$
\varepsilon _ { \Delta \tau } = \sqrt { 2 } \sqrt { 2 } \frac { \varepsilon _ { \varphi } } { 3 6 0 } \frac { 1 } { f _ { \mathrm { B W } _ { s } } }
$$

$\varepsilon _ { \varphi }$ 为仪器相位误差， $f _ { \mathrm { B W } _ { s } }$ 为总观测带宽。假设仪器相位抖动为 $0 . 2 ^ { \circ }$ ，总观测带宽为 $4 0 \mathrm { { M H z } }$ ，则时延误差为0.0278ns。

介质扰动误差对流层和电离层的随机性误差与各自观测方向的扰动不确定性及卫星和参考源间夹角有关，该项不能通过差分运算消除，表示如下[13]

$$
\varepsilon _ { \Delta \tau } = \frac { 1 } { c } ( \frac { \Delta \theta } { 0 . 1 7 4 5 } ) \rho _ { f l u c t }
$$

（204 $\rho _ { f l u c t }$ 为 $1 0 ^ { \circ }$ 分离角的对流层或电离层波动不确定性，若对流层和电离层波动不确定性均为$0 . 0 1 \mathrm { m }$ ，则两者对时延影响均为0.0191ns。

上述各误差项的统计结果见图2，图中红色项为系统误差，蓝色项为随机误差，黑色项为所有误差项平方和的平方根值（Root Sum Square，RSS），RSS 总误差约0.0720ns。

![](images/961b7d042428ad9073bf909d138bf9084de4a4dea17ffea1f4dede31493e3cf3.jpg)  
图2时延误差估计Fig.2 Estimation of Delay Error

差分VLBI时延测量误差 $\varepsilon _ { \Delta \tau }$ 与卫星垂直于径向轨道的平面位置误差 $\delta _ { \varepsilon }$ 之间满足[2]

$$
\varepsilon _ { \Delta \tau } = \frac { \delta _ { \varepsilon } } { c } \cdot \frac { B } { L }
$$

式中 $B$ 为基线在天空平面投影的长， $L$ 近似认为是测站到卫星距离。对于GEO卫星， $L$ 约为36000km，若投影基线长 $3 0 0 0 \mathrm { k m }$ ，差分VLBI时延测量精度在0.0720ns 时，轨道横向位置精度约

0.26米的。

为了对定位结果的可靠性进行直观评估，可将试验结果与IGS提供的事后精轨数据进行比较。不同机构提供的GEO 精轨结果本身存在一定差异。目前，德国地球科学研究中心（GeoForschungsZentrum，GFZ）和武汉大学（WuhanUniversity，WHU）两家机构可公开提供观测日滞后时间约十几天的 GEO 卫星精轨。两机构提供的观测日北斗导航C03星精轨比较结果如图3所示。图中横坐标表示观测日时刻，纵坐标表示两机构精轨坐标差值。蓝橙绿黑散点分别为X、Y、Z坐标分量差和三维坐标差，均方根值依次为 $1 . 0 9 \mathrm { m }$ ， $ { 0 . 6 4 \mathrm { m } }$ ，$0 . 1 7 \mathrm { m }$ 和 $1 . 2 7 \mathrm { m }$ ，三维坐标差最大值约为 $1 . 4 5 \mathrm { m }$ （2说明不同机构提供的精轨数据本身包含米量级的偏差。

![](images/051d6471717597e980a725db2aacad05b80f523b59cf0a698476a001f32c5906.jpg)  
图3GFZ和WHU的GEO卫星精轨比较 Fig.3 Comparison of Precise GEO Satellite Orbit between GFZ and WHU

# 2 实测数据处理与分析

# 2.1 观测设置

我们在UTC时间 2018年1月13日组织了一次约4小时的GEO卫星差分VLBI观测，信标频率在2.217GHz，具体观测参数设置见表1。

表1观测参数设置Tab.1 Setting of Observation Parameters  

<html><body><table><tr><td>code</td><td>b8113a</td></tr><tr><td>observation period</td><td>3:30~7:30</td></tr><tr><td>quasar targets</td><td>1741-038，1908-201，2008-159 2134+00，2227-088，3C454.3</td></tr><tr><td>satellite target</td><td>Beidou C03</td></tr><tr><td>stations</td><td>Beijing（Bj），Kunming（Km） Tianma（Tm），Urumqi（Ur)</td></tr><tr><td>beacon frequency</td><td>S(2.217GHz)</td></tr><tr><td>channels</td><td>8</td></tr><tr><td>bandwidth</td><td>4MHz</td></tr><tr><td>sampling rate</td><td>8MS/sec</td></tr><tr><td>quantization bits</td><td>2bit</td></tr><tr><td>data recording format</td><td>Mark5B</td></tr></table></body></html>

![](images/177c151d897cf31a429a2faeec1abbe85bb3552e214c8e9adfdf1bd49aba779f.jpg)  
图4射电源和卫星天球位置及轨迹 Fig.4 Position and Trajectory of Radio Sources and Satellites in Celestial Reference System

CVN的4台站参与观测，最长基线为东西向的乌鲁木齐-天马基线（Ur-Tm），长度约 $3 2 4 9 \mathrm { k m }$ 最短基线为北京-天马基线（Bj-Tm），长度约1114km。由于GEO卫星轨道高度较河外射电源低，且相对射电源每小时沿天赤道方向移动15度左右，导致不同测站观测卫星和邻近参考源的视差角不同，且大小随时间变化。为提高观测精度，从国际天球参考架中选择6颗邻近C03卫星的致密射电源作为参考源，射电源和卫星天球位置及轨迹如图4所示。

# 2.2 数据处理

利用 CVN 软件相关处理机 scorr 进行原始观测数据的相关处理后，经校正可得到观测时延[14]。相关处理时利用预先计算的模型时延对两台站接收的两路信号进行补偿，得到残余时延[15]。射电源模型时延为远场模型，卫星模型时延为近场模型，卫星模型时延根据卫星的预报轨道获得。均由上海

天文台VLBI中心计算。

相关处理时傅里叶点数设为1024，卫星频域512个数据点的互相关功率相位谱结果如图5所示。6 个子图分别为北京-昆明基线（Bj-Km）、北京-乌鲁木齐基线（Bj-Ur）、北京-天马基线（Bj-Tm）、昆明-乌鲁木齐基线（Km-Ur）、昆明-天马基线（Km-Tm）和乌鲁木齐-天马基线（Ur-Tm）结果。图中横坐标为频率，单位kHz；纵坐标蓝色为幅度谱，单位dB，橙色为相位谱，单位为度（°）。从相关处理结果可以看出，6条基线均获得较好的干涉条纹。

Bj-Km Bj-Ur Bj-Tm 10 180 150 10 180 150 10 150 180   
(ap)apriidte 0 109030300 () aseyd (ap)hphiidre 0 296030 (gp)pnendu 0 12063003000 () aseyd -30 -10 -10 -60 -10 -90 -90 -120 -120 -120 -150 -150 -150 -20 -180 -20 -180 -20 -180 0 2000 4000 0 2000 4000 0 2000 4000 frequency（kHz) frequency（kHz) frequency（kHz) Km-Ur Km-Tm Ur-Tm 180 180 180 10 150 10 150 10 150   
(ap)aprtidae 0 296030° (gpepnidu 0 296030 apne 0 2090630 () aseyd 0 0 -30 -30 -30 -10 -60 -10 -60 -10 -60 -90 -90 -90 -120 -120 -120 -150 -150 -150 -20 -180 -20 -180 -20 -180 0 2000 4000 0 2000 4000 0 2000 4000 frequency (kHz) frequency （kHz) frequency（kHz)

对相关处理后时延数据进行拟合、钟差改正及介质改正等后处理的结果如图6所示，横坐标为观测时刻，纵坐标为6条基线的残余时延值，单位ns。6条基线残余时延拟后残差中误差分别为2.35ns，1.15ns， $0 . 3 9 \mathrm { n s }$ ，0.75ns，0.70ns，0.86ns，均值为1.03ns。图上显示部分时间段的残余时延结果存在缺值和跳变情况，与台站数据和数据处理中引入的误差有关。残余时延结果与模型时延的和为总时延数据，因VLBI对确定卫星径向位置不敏感，若仅利用总时延数据解算卫星位置，解算结果精度较差，因此可采用距离约束的方法。假定卫星的地心距等于由其预报轨道计算的地心距，则地心距约束的先验误差由预报轨道误差给定[1。将该等式与VLBI观测等式共同组成误差方程解算卫星位置，并与IGS 提供的精密轨道数据进行比较，三维坐标差结果如图7所示。两者坐标差小于35米，坐标均方根误差约16.76米。图7中部分时间段卫星定位结果存在跳变，与残余时延结果图中存在跳变的时间段较一致，对应时间段数据分别在两图中由蓝红绿色圈标出。

![](images/3b5113a80533dd11213549617807ed4ee3541db1153e9bf5db9d97fd2c0e2e0b.jpg)  
图56条基线互相关功率相位谱 Fig.5 Cross-correlation Power Phase Spectrum of 6 Baselines

![](images/fb519cb51ac07829187c47b44a4054c3fb77673a8e7bd5285abac2277dffe2ba.jpg)  
图66条基线残余时延Fig.6 Residual Delay of 6 Baselines  
图7卫星坐标差  
Fig.7 Satellite Coordinate Difference

# 2.3 残余时延改进方法

时延异常值将直接影响卫星最终定位结果。为提高卫星位置解算精度，需对VLBI残余时延数据异常值进行检测和校正，改正VLBI残余时延跳变问题。时延异常值产生原因主要分两类： $\textcircled{1}$ 与台站相关，如台站测量记录设备引入的误差或钟差修正残余部分； $\textcircled{2}$ 与基线相关，由数据处理误差引入。因残余时延数据为时间序列数据，异常检测时不能作为孤立的样本点处理，借助多项式拟合方法和基线理论时延闭合差为零的约束条件来检测两类异常值。将每条基线的残余时延拟合值残差作为异常值检测数据，偏离平均值一定倍数标准差的数据即为异常值。与台站和基线相关的异常值检测校正方法流程图分别见图8和图9，主要步骤包括 $\textcircled{1}$ 确定标记异常值； $\textcircled{2}$ 判断是否台站、基线相关； $\textcircled{3}$ 计算校正值并校正。

![](images/b5d5fd201dfa9812355a0b2491176c709cc7ca5afa1d41763b75dd5e6728ab16.jpg)  
图8台站异常值检测校正流程

![](images/4624ccf5bb7852a11699a6500b4d13df4573d7e419d0785b7de5c2c4b15fc99a.jpg)  
ig.8 Outlier Detection and Correction Flow of Stations   
图9基线异常值检测校正流程 .g.9 Outlier Detection and Correction Flow of Baseline:

首先检测台站相关异常值，试验中采用拟合值残差1倍标准差作为异常值检测阈值，若同一时间段与某一台站相关的所有基线均标记有异常值，则认为该时间段存在台站相关的数据异常。在确定为台站相关异常值后，对异常时间段的台站数据进行校正：在0到最大异常偏离值范围内，每隔一较小间隔如0.0lns 确定一改正值，计算改正值改正后所有基线的时延测量值与拟合值差值平方和，最终的改正值应使该平方和最小。

针对基线的数据处理引入的误差，误差检测与校正方法主要基于多基线理论时延闭合差为零的条件，4个台站6条基线共4种组合方式，如用 BK-KU-BU表示 Bj-Km、Km-Ur和Bj-Ur基线组合。计算不同基线组合的时延闭合差，求每个 scan 内每一时延闭合差的平均值（以下称 scan 闭合差均值）(设阈值为1.25ns，scan 闭合差均值超阈值处为需要校正的时间段，取 scan 闭合差均值绝对值的基线组合闭合差之平均值为校正值。正负号据 scan 闭合差均值正负和该基线在组合中位置判断，例如：在某一 scan 内，BK-KU-BU 和 BK-KT-BT基线组合同时被标记，则共同基线 BK（即 Bj-Km 基线）需要被校正，若该 scan内BK-KU-BU和BK-KT-BT基线组合闭合差均值都为正，则 BK基线需减去改正值，反之需加上改正值。台站记录数据缺失会导致基线数据空缺问题，受部分时间段数据空缺和不同基线组合闭合差差别较大等的影响，可能导致无法确定需校正的具体基线，可通过修改闭合差阈值的大小来综合判断。

校正前后的基线组合时延闭合差对比如图10所示，横坐标为观测时刻，纵坐标为基线组合的时延闭合差，单位ns。蓝色散点为校正前的时延闭合差，部分时间段闭合差结果较差，红色散点为经台站和基线异常值校正后的闭合差结果，校正后的结果更接近理论零值。校正前后的残余时延分别为图11中蓝色星号和绿色圆圈，从图中对比看出，残余时延值经过校正后变平滑。校正后的6条基线残余时延拟后残差中误差分别为0.56ns，0.53ns，0.31ns，0.66ns，0.50ns，0.70ns，均值为0.54ns。

![](images/9af86e7cdd3fc46de5ed1ae4f2ec437f1a9054d3ff60b6d11e8bc5627275e9d3.jpg)  
图10基线组合闭合差校正前后结果比较 Fig.10 Comparison of Baseline Combination Closure Error before and after Correction

![](images/decaca335ea7a75d8401ec5171defcbe8cd71dbdc60964e4b4bd168ec22de9fb.jpg)  
图11校正前后与重新处理后的6条基线残余时延对比 Fig.11 Comparison of Residual Delay of 6 Baselines before and after Correction and Reprocessing

# 2.4 结果分析

为进一步提高卫星定位精度，对数据重新处理后，残余时延数据变得更加平滑，见图11中的红色线。采用五阶多项式拟合VLBI残余时延数据，时延精度用拟后残差中误差表示。最终得到6条基线的时延拟后残差中误差分别为0.16ns，0.23ns，0.14ns，0.14ns，0.14ns，0.13ns，均值为0.16ns，等效于轨道横向位置误差约0.58米。

分别用校正后和重新处理的总时延数据对GEO卫星定位计算。定位结果与精轨坐标差的比较见图12。红色星号为校正前结果，绿色加号为校正后结果，蓝色圆圈为新处理程序的结果。经过基线和台站时延校正后，卫星定位精度有一定提高，尤其是对图6中标出的3处存在异常值的时间段。用新的后处理程序重新处理后的轨道定位结果与精轨比较的均方根误差约6.61米，3次处理结果的残余时延残差均值和卫星坐标均方根误差统计见表2。

![](images/5e04a137170f99d0cdb8d399ddc5cc465b8668b7574180efc92ab5a178574d96.jpg)  
图 12卫星坐标差对比

# 表2三次处理结果比较

Tab. 2 Comparison of Results   

<html><body><table><tr><td></td><td>before correction</td><td>after correction</td><td>reprocessing</td></tr><tr><td>mean of residual delay</td><td>1.03ns</td><td>0.54ns</td><td>0.16ns</td></tr><tr><td>RMS of coordinate difference</td><td>16.76m</td><td>14.59m</td><td>6.61m</td></tr></table></body></html>

试验结果表明，利用仅4小时的短时VLBI时延数据可以得到外符合精度米级的GEO卫星定位结果，有利于GEO卫星的快速轨道恢复。本次实测试验结果与历史实测结果对比见表3，对比说明，此次VLBI窄带观测时延测量精度较历史窄带观测结果有较大提高，且接近宽带观测的时延精度结果。并且本文首次计算了外符合精度结果，更好地评估定位结果的准确度。虽与精轨结果比仍有一定差异，但在GEO卫星轨控后可快速提供较高精度卫星位置信息，减少轨道误差影响，仍具有重要意义。

# 表3GE0卫星实测试验信息统计

Fig.12 Comparison of Satellite Coordinate Differences   
Tab.3 Information Statistics of GEO Satellites Observations   

<html><body><table><tr><td>year</td><td>VLBI observation mode</td><td>VLBI observation accuracy</td><td>estimated horizontal position accuracy</td><td>external coincidence accuracy</td></tr><tr><td>1984</td><td>17 hours, 4GHz</td><td>2ns</td><td>/</td><td>/</td></tr><tr><td>2003</td><td> 3 hours,2/8GHz,4M</td><td>△DOR 41cm</td><td>8m</td><td>/</td></tr><tr><td>2011</td><td>3 hours,2GHz,2M bandwidth</td><td>3.6ns</td><td>10m</td><td>/</td></tr></table></body></html>

<html><body><table><tr><td>2017</td><td>36 hours,4GHz,32M</td><td>0.14ns</td><td>0.42m</td><td>/</td></tr><tr><td>our article</td><td>4 hours,2GHz,M</td><td>0.16ns</td><td>0.58m</td><td>6.61m</td></tr></table></body></html>

# 3 结论

利用VLBI技术观测GEO卫星，可充分发挥VLBI对卫星横向位置约束精度高的特点，提高GEO 卫星的短时定位精度，有利于卫星机动后的轨道快速恢复。本文首先对VLBI时延进行理论精度分析，包括射电源源位置、台站位置、地球自转参数和介质等带来的系统性误差，和观测源噪声、氢原子钟不稳定度、介质扰动和仪器相位抖动等带来的随机误差。分析得差分VLBI时延理论测量精度为0.0720ns，换算为卫星平面位置误差约0.26米。

实测实验利用CVN的4个台站观测GEO卫星，得4小时的VLBI残余时延数据的拟后残差中误差均值为1.03ns。画图结果显示残余时延存在缺值和跳变的情况，影响了时延测量精度。因此本文提出了针对该情况的异常值检测校正方法，分别考虑与观测台站和观测基线相关的异常值校正。重新处理校正后的数据得残余时延拟后残差中误差均值为0.16ns。进而进行卫星定位计算进一步验证该时延异常值的校正效果，发现卫星定位结果与IGS提供的精轨结果差异由16.76米提高到6.61米，说明了校正方法的有效性。本文的研究可利用短时的VLBI观测数据进行GEO卫星的快速高精度定位，有望用于GEO卫星轨道的快速恢复。

在此基础上，未来还可利用VLBI时延观测数据和时延率数据预报短时间的VLBI时延值，并进行后续GEO卫星位置预报的相关研究。随VLBI全球观测系统的不断完善，将会有更多台站和更多基线组合可用于GEO 卫星的跟踪观测。另外可以通过设置专门的 DOR 信标或宽带信标等方式，进一步提高短时测量精度，提高GEO卫星轨道监测能力。

# 参考文献

[1]刘林.航天器轨道理论[M].第一版.北京:国防工业出版社,2000:211-221,414-451. LIUL.Orbit Theoryof Spacecraft[M].1sted.Beijing: National Defense Industry Pres,2000: 211-221,414-451.   
[2] 黄勇,胡小工,张秀忠,等.VLBI应用于GEO 导航卫星的测定轨[J].科学通报,2011(24):32-39. HUANG Y,HU X G, ZHANG X Z,et al. Improvement of orbit determination for geostationary satelites with VLBI tracking[J]. Science China Press,2011(24) :32-39.   
[3]杜兰,郑勇,李杰.VLBI在GEO卫星精密定轨中的应用[J].测绘科学技术学报,2006(4):38-40. DUL,ZHENG Y,LI J.VLBI-augmentedorbit determination for geostationary satelites[J]. Journal of Geomatics Science and Technology,2006(4): 38-40.   
[4]杨旭海,李志刚，冯初刚,等.GEO 卫星机动后的星历快速恢复方法[J].中国科学(G 辑:物理学 力学 天文学), 2008(12):1759-1765. YANG X H,LIZG,FENG C G, et al. Rapid recovery methodof ephemeris after maneuverof GEO satelite[J]. Scientia Sinica (Physica,Mechanica & Astronomica),2008(12):1759-1765.   
[5]李金岭,张津维,刘鹂,等.应用于深空探测的 VLBI技术[J].航天器工程,2012,21(2):62-67. LI JL,ZHANGJW,LIUL,et al.VLBI techniqueapplied in deep space exploration[J]. Spacecraft Enginering,021, 21(2): 62-67.   
[6] 童锋贤,郑为民,舒逢春.VLBI相位参考成像方法用于玉兔巡视器精确定位[J].科学通报,2014(34):30-37. TONGFX, ZHENG W M,SHUFC.Accurate relative positioning of Yutu lunar rover using VLBI phase-referencing mapping technology (in Chinese). Chin Sci Bull(Chin Ver),2014,59:3362-3369,doi: 10.1360/N972014-00578   
[7] 聂振华，张波，乔书波,等．深空探测器的 VLBI 逆相位参考定位[J].中国科学:物理学 力学 天文学，2017, 047(012):P.102-110. NIE ZH,ZHANG B,QIAO SB,et al. Positioning of spacecraft with VLBI inverse phase reference (in Chinese).Sci SinPhys Mech Astron,2017,47:129502,doi:10.1360/SSPMA2017-00050   
[8]SHIOMIT,KOZONO SIARIMOTO Y,et al. Precise orbit determinationof a geosynchronoussatelite by Delta VLBI method[J]. Journal of the Radio Research Laboratory,1984,31(133):111-132.   
[9] 舒逢春,张秀忠,郑为民.地球同步卫星的 VLBI观测[J].中国科学院上海天文台年刊,2003,000(001):105-111. SHU F C,ZHANG X Z, ZHENG W M. VLBI observations of geosynchronous satelites[J].Annals of Shanghai Astronomical Observatory Chinese Academy of Sciences,2003, O0o(O01): 105-111.   
[10]HUANGY,HUXG,ZHANGXZetal.Improvementoforbit determinationforgeostationarysateliteswith BItracking [J]. Chinese Science Bulletin,2011,56(26): 2765-2772.   
[11] GONGJJ,CAOF,YANG X,et al.The GEO satelite orbit experiment measured bycombinationofthe broadband VLBI & the orbit tracking of two way range[J]. Boletin Tecnico/Technical Bulletin,2017,55(8):39-47.   
[12] 钱志瀚,李金岭.甚长基线干涉测量技术在深空探测中的应用[M].第一版.北京:中国科学技术出版社,2010. QIAN Z H,LIJL. The Application of Very Long Baseline Interferometry in Deep Space Navigation[M]. Beijing: China Science and Technology Press,2010.   
[13]Delta-DOR—Technical CharacteristicsandPerformance InformationalReport CCSDS 500.1-G-2.GreenBook [R] Washington,D.C.: CCsDS,November 2019   
[14]郑为民,舒逢春,张冬.应用于深空跟踪测量的VLBI软件相关处理技术[J].宇航学报,2008,29(001):18-23. ZHENG W M,SHUFC,ZHANG D.Application of software correlator to deep space VLBI tracking[J]. Joumal of Astronautics,2008,29(001):18-23.   
[15]孙晓彤,童力,郑为民,等.基于多重网格的射电源条纹搜索算法研究[J].天文研究与技术,2021,18(1):52-59 SUN X T,TONG L, ZHENG W M, et al. Research on Radio Source Fringe Search Algorithm Based on Multi-Grid[J]. Astronomical Research & Technology,2021,18(1):52-59   
[16] 郭丽.基于VLBI跟踪观测的空间飞行器瞬时状态参量归算[D].北京：中国科学院研究生院（上海天文台）,2007. GUO L.Reduction of the instantaneous state vectors of spacecraft based on VLBI tracking data[D]. Beijing: Graduate School of Chinese Academy of Sciences (Shanghai Astronomical Observatory),2007.

# Fast high accuracy positioning of GEO satellite in VLBI observation

Li Ting12,Tong Fengxian13,Zheng Weimin1,34,5,Zhang Juan1,3 (1.Sangs;s 10049,Ca;ditrna;i BasicDisciplineseijg,ina;5angiKeyboatoracevigatioditionghqueang

Abstract: With the rapid development of satelites Earth observation， navigation and positioning，the orbit of Geostationary Earth Orbit (GEO) satelites requires an accuracy of meters level or even higher. In this paper，we study the method of GEO satellites fast positioning using Very Long Baseline Interferometry (VLBI) delay data. First of all, we analyze the theoretical accuracy of VLBI delay. After that we conduct the GEO satelite observation experiment and data correlation using Chinese VLBI Network. Finally,the positioning calculation of GEO satelite is completed by using short-time VLBI delay data.In order to solve the problem of outliers related to stations and baselines in VLBI delay, we also study the corresponding detection and correction methods. After correction and reprocessng, the measurement accuracy of VLBI residual delay is about 0.16ns,which is equivalent to the transverse position error of about 0.58 meters.The research in this paper can be used for fast and high-precision positioning and rapid orbit recovery of GEO satellites.

Key words: differential VLBI, GEO satelite,accuracy analysis,delay correction,fast high accuracy positioning