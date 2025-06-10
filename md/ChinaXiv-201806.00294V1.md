# 三频段太阳射电望远镜与空间天气

耿立红‘，谭程明‘，敦金平²，章宏，贾彦辉²，颜毅华‘， 陈志军¹，马素丽1.5，刘东浩¹，杜静‘，苏仓¹

1.中国科学院太阳活动重点实验室(国家天文台),北京，100101;2.中国气象局空间天气重点开放实验室，国家空间天气监测预警中心，北京，100081；3.中国电子科技集团第十六研究所，合肥，安徽,230043;4.中国电子科技集团第五十四研究所,石家庄，河北,05081;5.中国石油大学，青岛，山东，266580)

摘要：基于地基望远镜，对太阳射电辐射流量进行长期监测是空间天气预报的一个重要手段，用来预报太阳活动引发的地球上的各种扰动。明安图和塔什库尔干两台新的三频段（10.7cm，6.6cm 和 $3 . 3 \mathsf { c m }$ ）太阳射电望远镜将服务于我国的空间天气监测和预报，介绍了系统结构和设计特性、双噪声源定标方法。系统稳定性优于 $1 \%$ （10小时），灵敏度优于1s.f.u。展示了明安图太阳射电望远镜 2017年试观测初步结果。

关键词：太阳射电辐射流量；望远镜； $\mathrm { F } _ { 1 0 . 7 }$ 指数；定标；空间天气中图分类号：P162.11 文献标识码：A 文章编号：1672-7673 (2018)

基于地基望远镜，对太阳射电辐射流量进行长期监测是空间天气预报的一个重要手段，可预报太阳活动发生后在地球上产生的各种扰动。两台新建成的三频段太阳射电望远镜—一明安图三频段太阳射电望远镜（Mingantu three bands Solar Telescope,，MST)和塔什库尔干三频段太阳射电望远镜（Tashkurghan three bands SolarTelescope，TST），将对太阳射电辐射流量长期监测发挥重要作用。高稳定性、高灵敏度、大动态范围以及可调时间分辨率设计，使这两台望远镜兼具太阳射电爆发观测和辐射流量监测的功能。

# 1.太阳射电流量辐射与空间天气

太阳活动等自然现象导致日地空间状态发生的变化被称为"空间天气”，太阳活动是空间天气的主要驱动源。剧烈的空间天气变化可能造成空间天气灾害。越来越多的事实表明，一次空间天气灾害能在通信、导航、航空、航天、勘探及能源等各种技术层面同时产生系统的冲击，导致巨大的影响[Il。许多问题亟待研究和总体规划，如建设空间天气观测系统、应对空间天气灾害、评估恶劣空间天气事件影响、可靠预报和减轻空间天气影响等。

空间天气灾害监测需从太阳一行星际一磁层空间一电离层和中高层大气这一空间天气事件因果链上进行[2]。太阳活动预报是空间天气预报中最重要的方面，主要包括太阳耀斑、日冕物质抛射、质子事件、太阳射电流量和高速太阳风等。某一波长处总的太阳射电辐射流量反映了日冕中某一层次的太阳活动水平。太阳射电辐射流量与黑子相对数、耀斑爆发、X射线爆发以及高能电子质子事件均有一定的关系，以 $2 8 4 0 \mathrm { M H z }$ （波长 $1 0 . 7 \mathrm { c m } \rangle$ 最为显著。 $1 0 . 7 \mathrm { c m }$ 太阳射电流量（ $\cdot \mathrm { F } _ { 1 0 . 7 }$ ）单位为"太阳射电辐射流量单位”（sfu），宁静太阳射电辐射流量约在50-500。自20世纪60年代 $\mathrm { F } _ { 1 0 . 7 }$ 一直被作为太阳活动指数，是太阳活动预报的主要参数。

对宁静太阳射电辐射的研究，结合光学资料，可以建立更精确的太阳大气（色球和日冕）模型。太阳缓变射电流量密度与黑子和谱斑面积有很好的统计关系。太阳缓变射电源的高度和尺寸通常随着波长的增加而增加，流量密度也随波长而变化。观测发现，缓变射电的频谱峰值出现于 $5 { - } 2 0 \mathrm { c m }$ 频段，具体位置随太阳活动性的增强（如黑子磁场的增强）而变化。在多种波长对太阳缓变射电辐射作同步观测，可监测活动区上空不同层次的太阳大气的物理状态（如电子密度、电子温度等）。通常，太阳爆发与太阳黑子的大量出现分不开。FI0.7与太阳黑子数有较好的线性关系。太阳风暴发生在太阳射电流量较高的时段，太阳风暴爆发之前的1-2天，太阳射电流量会突然增加，射电能谱特性也会发生明显变化。

太阳紫外辐射影响地球高层大气密度，而高层大气密度变化对航天器产生电力效应，影响卫星轨道。即，大气层曳力与太阳紫外辐射通量密切相关，目前大多数曳力模式以 $\mathrm { F } _ { 1 0 . 7 }$ 代表太阳紫外辐射通量。地球高层大气也有十分明显的11年周期的长期变化特征，对长期飞行的航天器轨道和寿命产生严重影响[3]。

总之，太阳射电流量是最有用的太阳活动和太阳紫外辐射爆发的指示器，表征着太阳活动的总体水平。

# 2．三频段太阳射电望远镜MST和TST

至今国际上依然有大量单天线的点频或多频太阳射电流量观测系统在运行，如加拿大 Otawa/penticton2800MHz系统，自1947年2月开始常规观测至今，日均太阳流量密度是国际公认的太阳活动指标，绝对精度优于 $5 \%$ ，数十年相对稳定性优于 $2 \%$ 。日本野边山天文台的1.0、2.0、3.75、9.4、17、35、80GHz共7个单频偏振计，是国际公认太阳射电流量谱标准点。美国空军全球太阳射电监测网（RSTN)，由4个站LEAR（无35GHz)、PALE、SGMR 和SVTO 组成24小时不间断观测，0.245、0.41、0.606、1.415、2.695、4.995、8.8、15.4、35GHz9个频点。瑞士伯尔尼大学应用物理研究所的系统在8个频点上进行观测，包括3.2、5.2、8.4、11.8、19.6、35.0、50.0和 $9 2 . 5 \mathrm { G H z }$ 。还有国家天文台 $2 8 4 0 \mathrm { M H z }$ 系统，自20世纪70年代开始常规观测。

但是，过去国内在空间天气预报方面 $\mathrm { F } _ { 1 0 . 7 }$ 指数更多依赖国外监测数据，获得信息时间滞后且信息量有限，每天只有一个时间点的数据。塔什库尔干三频段太阳射电望远镜，是中国气象局国家空间天气监测预警中心在全国范围内用于空间天气预报业务的地基太阳观测系统总体规划的一部分，由中国科学院国家天文台总体负责，以发展我国空间天气综合的无缝隙的探测业务。

综合考虑维护、气候和太阳观测条件，在塔什库尔干和国家天文台内蒙古明安图观测基地，各建设完成1台三频段2801MHz/4542MHz/9084MHz（波长 $1 0 . 7 \mathrm { c m } , 6 . 6 \mathrm { c m }$ 和 $3 . 3 \mathrm { c m } \dot { }$ ）太阳射电望远镜（TST，位置： $3 7 . 7 8 ^ { \circ } \mathrm { N }$ $7 5 . 2 3 ^ { \circ } \mathrm { E } , 3 0 9 1 \mathrm { m } \mathrm { H }$ ；MST，位置： $4 2 . 2 2 ^ { \circ } \mathrm { N }$ $1 1 5 . 2 4 ^ { \circ } \mathrm { E } , 1 3 5 6 \mathrm { m } \mathrm { H } )$ ，见图1。两台望远镜横贯中国东西，相距约5000千米，时差约2小时40分钟，能提供更长太阳观测时间覆盖。观测结果可以互相验证和补充，经定标后，将及时传送到中国气象局国家空间天气预警中心，为太阳活动预报和太阳风暴事件的实时警报提供及时可靠的第一手数据。

![](images/ebf63f286975febff17fcf8f54972dfb9336ad0ccef63e0d51e50124ba92ddc6.jpg)  
图1(左）明安图三频段太阳射电望远镜MST;(右)塔什库尔干三频段太阳射电望远镜TST 'ig.1(left)Mingantu Three Bands Solar Telescope-MST; (right) Tashkurghan Three Bands Solar Telescope-TST

TST 建在塔什库尔干县城中心附近的气象局内，电磁环境给其三频段太阳射电观测带来很大困难。随着国家"一带一路"战略的推进,塔什库尔干已成为"中巴经济走廊"在中国境内的重要节点，移动通信网络将发展很快，其东南、西南和西北方向又分别与巴基斯坦、阿富汗、塔吉克斯坦三国接壤，使TST电磁环境更加不容乐观，需考虑TST移址问题。国家天文台明安图观测基地则采用了多种无线电环境保护措施，离人口较为密集的明安图镇直线距离也在 20 千米以外，MST 电磁环境远好于TST。

明安图射电频谱日像仪(Mingantu Spectral Radioheliograph,MUSER)位于明安图观测基地，是基于综合孔径原理，新一代同时具有高时间、高空间和高频谱分辨率的太阳专用成像观测设备[4]，2016年7月通过验收，是国际上观测太阳活动的动力学性质、探测日冕大气、研究太阳物理的最新最有力武器之一。MUSER分为高、低频两个阵列，其中MUSER-II工作在2.0-15.0GHz波段，由60面2米抛物面天线组成3螺旋阵列，常规观测模式为全频段扫频（中频带宽400MHz）观测，时间分辨率为 $2 0 6 . 2 5 \mathrm { m s }$ ，而MST为1ms。在MUSER-II高空间分辨率成像观测耀斑爆发等现象时，同地点MST的3频点双极化同时观测，利于观测数据的互相检验，并将可能提供该时间段内对应3个频段的太阳大气3个层次上高时间分辨率的更精细的演变过程。

# 3．三频段太阳射电望远镜系统

# 3.1．系统组成和性能

MST和TST具有自动采集观测数据、分析处理、生成和传送符合气象业务规范要求的格式化数据产品，及系统标校和自检的功能，还具有较高可靠性、稳定性，能全天候长期连续运行，适应恶劣气候环境。系统组成框图见图2，并采用全球定位系统校时，UPS提供备用电源。采用 $3 \mathrm { m }$ 口径赤道式抛物面天线，效率优于 $40 \%$ 。宽带 $9 0 ^ { \circ }$ 合成器将 Eleven 馈源接收的线极化信号转换为左、右旋圆极化信号，工作频段为 2801MHz,4542MHz,9084MHz，时间分辨率1s、 $1 0 0 \mathrm { { m s } }$ 和1ms，瞬时动态范围大于30dB。三个频段半功率波束宽度分别为150'，92'和46'，覆盖了全日面，指向精度优于工作波长1/15，对日跟踪时，指向在计算机控制下每秒更新一次。

![](images/abb5f6bd4c8cc8389b3d8e80454ba589abffa10516208b6d7c6192b59d5c6c1e.jpg)  
图2太阳射电望远镜系统组成框图Fig.2 SystemBlockDiagramofMSTand TST

两个站址气候条件恶劣，为保障系统性能稳定和降低系统噪声，采用双路低噪声放大器，温度敏感的室外射频前端组件置于靠近馈源的高精度恒温箱内，这沿用了MUSER 模拟室外前端方法[5]，并采用低损耗同轴电缆进行射频信号传输，增益起伏小于 $1 \% / 1 0$ 小时。室外接收前端可工作在 ${ - 3 0 ^ { \circ } C { \sim } { + } 6 0 ^ { \circ } C }$ 环境下，温度控制范围 $1 0 ^ { \circ } \mathrm { C } \sim$ $4 0 ^ { \circ } \mathrm { C }$ ，可根据环境温度设定，经测试温控精度优于 $\pm 0 . 0 5 \mathrm { ^ \circ C }$ 。图3为恒温室外前端内部装配示意图和实物图。

![](images/f5cd8703ee1d202a39227e5d4dec6b0e328e5840df0d0165d52d29f8b3f0cadb.jpg)  
图3恒温室外前端内部装配示意图和实物图  
Fig.3 Configuration Diagram and Picture of Thermostatic RF Front End Box

单天线系统灵敏度公式：

$$
\Delta S _ { \mathrm { m i n } } = { \frac { 2 R _ { \mathrm { m i n } } k T s } { A \eta \sqrt { \tau \Delta f } } }
$$

其中， ${ \bf R } _ { \mathrm { m i n } }$ 为最小可用信噪比，一般 $R _ { m i n } { = } 5$ ；波尔兹曼常数 $k { = } I . 3 8 ~ { ^ { \ast } I O ^ { - 2 3 } J / K }$ ；接收天线几何面积 $A = \pi D ^ { 2 } / 4$ $D { = } 3 m$ ；积分时间 $\scriptstyle \tau = l O O m s$ ，积分带宽 $\scriptstyle { \mathcal { A } } = l O M H z$ ，天线效率 $\scriptstyle \eta = 0 . 4$ 。

$$
T _ { s } { \approx } \left( T _ { a } { + } T _ { s u n } \right) { \ { ^ { * } b } { + } T _ { O } { \ { ^ { * } } \left( I { - } b \right) } { + } T _ { r e c } }
$$

$T _ { a } \mathrm { + } T _ { s u n }$ ：天线噪声（指向冷空）和宁静太阳辐射功率； $b$ ：从天线输出端到接收机输入端之间的传输系数;取 $T _ { a } \approx I O O K$ ， $2 8 0 I M H z$ 处， $T _ { s u n } { \approx } 5 0 0 K$ ， $b { \approx } 0 . 5$ ， $\scriptstyle { T _ { O = 2 } 9 O K }$ ；采用的双路限幅低噪声放大器在工作频带内的噪声系数经测量 $< 2 . 5 d B$ 。接收机系统噪声系数 $< 3 . O d B$ ，接收机系统噪声温度 $T _ { r e c } < 2 9 0 K$ ， ${ \cal T } _ { s } { \approx } 7 3 5 { \cal K }$ ；从而得到系统灵敏度 $\varDelta S _ { m i n } \approx 0 . 3 6$ sfu。MAT和TST的相对灵敏度优于 $1 \%$ ，并具备探测几个 sfu 的小爆发的能力。

# 3.2. 用户友好界面

MAT和TST操作界面友好美观，方便易操作，见图4。主界面上显示系统结构，可以设置时间分辨率、选择数据存储磁盘，另可以通过上方按钮，进入系统设置和状态显示、天线控制和状态显示、实时功率显示等界面。界面简洁、一目了然，易于操作。自动观测模式下，系统自动按时启动和停止观测，并在停止后使天线处于收藏状态，同时可以查看系统状态和实时功率。天线控制界面可设置天线指向某一方向，可选择天线在赤经和赤纬两个轴向的转动方向和速度，也可使天线根据给定轨道自动跟踪目标。实时功率显示界面，放大和缩小两个轴向的显示尺度，并可任意选择显示3个频段，选择数据实时显示或当日数据回放显示。

![](images/6c3cc90e7eab692ea1f6cb62ce57b955b39637b32d07d7b3468336a15e19b7a9.jpg)  
图4太阳射电望远镜用户友好界面Fig.4UserFriendly InterfacesofMSTand TST  
图5MST和TST双噪声源定标的原理框图Fig.5 diagram of calibration ofMSTand TST

# 3.3. 定标

定标是确定接收机数值与信号强度的关系。只有经过定标，观测数据才有物理意义，才能与其它设备观测结果有可比性。射电太阳是一颗“变星”，太阳射电望远镜在各波段上的逐日定标是其观测流程中的重要一环[6]。太阳射电望远镜定标方法[7-10]有绝对定标、相对定标和非线性定标。相对定标较为常用，即利用已知标准源对原始数据进行定标。定标参数是频率、温度、考虑大气吸收时天顶距Z的函数。

. . TsunR 天线指向太阳右旋. . TsunL 天线指向太阳左旋TskyR 天线指向天空右旋TskyL天线指向天空左旋区 天线有效面 $\cdot _ { \mathrm { e R } } ( \mathbf { \boldsymbol { v } } )$ 左旋圆极化AeL(v)计算机TaRGR RsunRTaLGL Tr RskyRTn1 接收机Gr RsunL噪声源1 RskyL噪声源2 Tn2 Rn1 一Rn2 =GL、 $\mathbf { G } _ { \mathrm { R } }$ 包含了接收机前级低噪放至微波开关前的左、右旋增益特性Tr包含了微波开关至数字终端的接收系统增益特性

（1）绝对定标

对于一个方向瓣较宽的天线，点源的流量密度可以表示为

$$
S ( \nu ) = \frac { 8 \pi k _ { B } } { \eta D _ { o } K \lambda ^ { 2 } } \cdot \Delta T _ { A } \cdot e ^ { \tau _ { 0 } \sec z } = \frac { 8 \pi k _ { B } \cdot \Delta T _ { A } } { G \lambda ^ { 2 } }
$$

$S ( \nu )$ 是点源在频率 $\boldsymbol { \mathsf { v } }$ 处的流量； $k _ { B }$ 为玻尔兹曼常量； ${ \bf D } _ { 0 }$ 为天线方向性系数；K 为天线方向图改正因子； $\tau _ { O }$ （204号为大气吸收因子； $\textbf { z }$ 为天顶距，而 $e ^ { \tau { \cal O } s e c ( z ) }$ 是大气改正因子，通常可近似为1，天线增益 $G = \eta D _ { \theta }$ ， $\Delta T _ { A }$ 为天体（太阳）的天线温度增量。由于太阳的 $\Delta T _ { A }$ 每天都有所变化，因而稳定而又可靠的 $\Delta T _ { A }$ 的测量是绝对定标的先决条件[。要获得太阳的绝对流量密度，须通过实验测量得到天线增益及标准噪声源的值，然后由上述公式把天线温度增量转换成射电辐射流量。绝对定标使射电望远镜的观测结果不依赖于其它望远镜而成为一个独立系统。

（2）相对定标

MST和TST初始设计也采用了Tanaka等人70年代系统阐述的定标方法，即利用已知噪声温度的噪声源、匹配负载、天空背景，确定太阳净射电辐射流量值：

$$
{ \frac { R _ { s u n } - R _ { s k y } } { T _ { s u n } - T _ { s k y } } } = { \frac { R _ { n } - R _ { t } } { T _ { n } - T _ { t } } }
$$

从圆极化馈源输出的太阳左、右旋圆极化信号分别经过低噪声放大器，再接四选一微波开关的两个输入。微波开关的另外两个输入初始设计为超噪比为15dB 的噪声源和 $5 0 \mathrm { o h m }$ 的匹配负载。高的接收机系统后端噪声抬高了底噪，使微波开关切换到 $5 0 \mathrm { o h m }$ 负载时，终端读数反映等效到微波开关前的接收机系统噪声。采用具有不同超噪比的双噪声源进行定标解决这个问题，即用 $\mathbb { R } _ { \mathrm { n l } }$ 、 ${ \bf R } _ { \mathrm { n } 2 }$ 和 $\mathrm { T _ { n 1 } }$ 、 $\mathrm { T } _ { \mathrm { n } 2 }$ 代替 ${ \bf R } _ { \mathrm { n } }$ 、 $\mathbf { R } _ { \mathrm { t } }$ 和 $\mathrm { { T } _ { n } }$ 、 $\mathrm { T _ { t } }$ ，见图5。

由右旋宁静太阳和天空背景在终端的读数相减，得到扣除天空背景辐射后右旋宁静太阳射电辐射净流量：

$$
\begin{array} { r l } & { \mathrm { R } _ { \mathrm { s u r k } } ( \nu ) = ( \mathrm { T } _ { \mathrm { s u r k } } ( \nu ) \cdot G _ { \scriptscriptstyle R } ( \nu ) + T _ { r } ( \nu ) ) \cdot G _ { r } ( \nu ) = ( \mathrm { S } _ { \mathrm { s u r k } } ( \nu ) \cdot C _ { k } \cdot A _ { \scriptscriptstyle e R } ( \nu ) \cdot G _ { \scriptscriptstyle R } ( \nu ) + T _ { r } ( \nu ) ) \cdot G _ { r } ( \nu ) } \\ & { \mathrm { R } _ { \mathrm { s u r k } } ( \mathbf { v } ) = ( \mathrm { T } _ { \mathrm { s u p t } } ( \mathbf { v } ) \cdot \mathrm { G } _ { \scriptscriptstyle \mathrm { R } } ( \mathbf { v } ) + \mathrm { T } _ { \mathrm { r } } ( \mathbf { v } ) ) \cdot \mathrm { G } _ { \mathrm { r } } ( \mathbf { v } ) = ( \mathrm { S } _ { \mathrm { s u p t } } ( \mathbf { v } ) \cdot \mathrm { G } _ { \scriptscriptstyle \mathrm { k } } \cdot \mathrm { A } _ { \scriptscriptstyle { e R } } ( \mathbf { v } ) \cdot \mathrm { G } _ { \scriptscriptstyle \mathrm { R } } ( \mathbf { v } ) + \mathrm { T } _ { \mathrm { r } } ( \mathbf { v } ) ) \cdot \mathrm { G } _ { \mathrm { r } } ( \mathbf { v } ) } \\ & { \mathrm { R } _ { \mathrm { u l } } ( \mathbf { v } ) = ( \mathrm { T } _ { \mathrm { n l } } ( \mathbf { v } ) + \mathrm { T } _ { \mathrm { r } } ( \mathbf { v } ) ) \cdot \mathrm { G } _ { \mathrm { r } } ( \mathbf { v } ) } \\ & { \mathrm { R } _ { \mathrm { n 2 } } ( \mathbf { v } ) = ( \mathrm { T } _ { \mathrm { n 2 } } ( \mathbf { v } ) + \mathrm { T } _ { \mathrm { r } } ( \mathbf { v } ) ) \cdot \mathrm { G } _ { \mathrm { r } } ( \mathbf { v } ) } \end{array}
$$

由以上4式可得：

$( \mathrm { S } _ { \mathrm { s u p R } } ( \mathbf { v } ) - \mathrm { S } _ { \mathrm { s t y R } } ( \mathbf { v } ) ) \cdot \mathrm { C } _ { \mathrm { k } } \cdot \mathrm { A } _ { \mathrm { e R } } ( \mathbf { v } ) \cdot \mathrm { G } _ { \mathrm { R } } ( \mathbf { v } ) = ( \mathrm { R } _ { \mathrm { s u p R } } ( \mathbf { v } ) - \mathrm { R } _ { \mathrm { s t y R } } ( \mathbf { v } ) ) \cdot \frac { \mathrm { T } _ { \mathrm { n l } } ( \mathbf { v } ) - \mathrm { T } _ { \mathrm { n 2 } } ( \mathbf { v } ) } { \mathrm { R } _ { \mathrm { n l } } ( \mathbf { v } ) - \mathrm { R } _ { \mathrm { n 2 } } ( \mathbf { v } ) }$ 设 $\mathrm { C _ { \scriptscriptstyle R } } ( \mathrm { v } ) = \mathrm { C _ { \scriptscriptstyle k } } \mathrm {  \large ~ \cdot ~ } \mathrm { A _ { \mathrm { e R } } } ( \mathrm { v } ) \mathrm {  \large ~ \cdot ~ } \mathrm { G _ { \scriptscriptstyle R } } ( \mathrm { v } )$ ，（1）式成为：

$$
( \mathrm { S } _ { \mathrm { s u n R } } ( \mathbf { v } ) - \mathrm { S } _ { \mathrm { s u r R } } ( \mathbf { v } ) ) \cdot \mathrm { C } _ { \mathrm { R } } ( \mathbf { v } ) = ( \mathrm { R } _ { \mathrm { s u r R } } ( \mathbf { v } ) - \mathrm { R } _ { \mathrm { s i r R } } ( \mathbf { v } ) ) \cdot \frac { \mathrm { T } _ { \mathrm { n l } } ( \mathbf { v } ) - \mathrm { T } _ { \mathrm { n 2 } } ( \mathbf { v } ) } { \mathrm { R } _ { \mathrm { n l } } ( \mathbf { v } ) - \mathrm { R } _ { \mathrm { n 2 } } ( \mathbf { v } ) }
$$

同理，得到扣除天空背景辐射后的左旋太阳射电辐射净流量：

$$
( \mathrm { S } _ { \mathrm { s u n L } } ( \mathbf { v } ) - \mathrm { S } _ { \mathrm { s t y L } } ( \mathbf { v } ) ) \cdot \mathrm { C } _ { \mathrm { L } } ( \mathbf { v } ) = ( \mathrm { R } _ { \mathrm { s u n L } } ( \mathbf { v } ) - \mathrm { R } _ { \mathrm { s k y L } } ( \mathbf { v } ) ) \cdot \frac { \mathrm { T } _ { \mathrm { n l } } ( \mathbf { v } ) - \mathrm { T } _ { \mathrm { n 2 } } ( \mathbf { v } ) } { \mathrm { R } _ { \mathrm { n l } } ( \mathbf { v } ) - \mathrm { R } _ { \mathrm { n 2 } } ( \mathbf { v } ) }
$$

(2)、(3)式右端均为记录已知值。理想情况下，在观测宁静而没有黑子的太阳时，所得太阳辐射圆偏振应该为0，即全日面宁静太阳辐射具有无圆偏振特性。但对宁静太阳实际观测时，左、右旋圆极化输出读数是不等的。可利用宁静太阳无圆偏振特性校准望远镜偏振接收特性。实际宁静太阳左、右旋射电辐射流量均应为该频段1/2太阳总射电辐射 $ { \mathrm { S } } _ { \Theta } (  { \mathbf { \nu } } )$

$$
\mathrm { S _ { s u n R } ( \mathbf { v } ) - \mathrm { S _ { s k y R } ( \mathbf { v } ) = \mathrm { S _ { \mathrm { e R } } ( \mathbf { v } ) = \mathrm { S _ { \mathrm { e L } } ( \mathbf { v } ) = \mathrm { S _ { s u n L } ( \mathbf { v } ) - \mathrm { S _ { s k y L } ( \mathbf { v } ) = \mathrm { S _ { \mathrm { e } } ( \mathbf { v } ) / 2 } } } } } } }
$$

其中， $ { \mathbf { S } } _ { \Theta } (  { \mathbf { v } } )$ 采用观测当天国际标准太阳射电流量谱的值。一般情况下，并不能每日实时获得 $ { \mathbf { S } } _ { \Theta } (  { \mathbf { \nu } } )$ 标准值。将已知一段时间的 Se(ν)代入(2)、(3)式，可获得这段时间内 $\mathbf { C } _ { \mathrm { { R } } } ( { \boldsymbol { \nu } } )$ 和 $\mathbf { C } _ { \mathrm { { L } } } ( \nu )$ 的一个正态分布，取其平均值作为左、右旋圆极化通道的校准系数 ${ \bf C } ^ { * } { \bf \Psi } _ { \mathrm { R } } ( \bf { \Psi } )$ 和 $\mathbf { C } ^ { * } \mathbf { \mathrm { _ L } } ( \mathbf { \mathrm { \boldsymbol { v } } } )$

$$
\mathrm { S _ { \mathrm { s u n R } } ( \mathbf { v } ) - \mathrm { S _ { \mathrm { s k y R } } ( \mathbf { v } ) = \frac { R _ { \mathrm { s u n R } } ( \mathbf { v } ) - R _ { \mathrm { s k y R } } ( \mathbf { v } ) } { C _ { \mathrm { \mathrm { \mathrm { \textmu } } } } ^ { \ast } ( \mathbf { v } ) } \cdot \frac { \mathrm { T _ { n l } ( \mathbf { v } ) - T _ { n 2 } ( \mathbf { v } ) } } { R _ { n l } ( \mathbf { v } ) - R _ { n 2 } ( \mathbf { v } ) } } }
$$

$$
\mathrm { S _ { s u n L } ( \mathbf { v } ) - \mathrm { S _ { s k y L } ( \mathbf { v } ) = \frac { R _ { s u n L } ( \mathbf { v } ) - R _ { s k y L } ( \mathbf { v } ) } { C ^ { * } _ { L } ( \mathbf { v } ) } \cdot \frac { \partial T _ { n l } ( \mathbf { v } ) - T _ { n 2 } ( \mathbf { v } ) } { R _ { n l } ( \mathbf { v } ) - R _ { n 2 } ( \mathbf { v } ) } } }
$$

在接收机线性范围内，可对净太阳射电爆发流量左、右旋分量进行定标：

$$
\mathrm { S _ { b u r s t - R } ( \mathbf { v } ) - \mathrm { S _ { s k y R } ( \mathbf { v } ) \it = \frac { R _ { b u r s t - R } ( \mathbf { v } ) - \mathrm { R _ { s k y R } ( \mathbf { v } ) } } { \mathrm { C ^ { * } _ { R } ( \mathbf { v } ) } } \cdot \frac { \partial \mathrm { T _ { n l } ( \mathbf { v } ) - \mathrm { T _ { n 2 } ( \mathbf { v } ) } } } { \partial \mathrm { R _ { n l } ( \mathbf { v } ) - \mathrm { R _ { n 2 } ( \mathbf { v } ) } } } } }
$$

$$
\mathrm { S _ { b u r s t - L } ( \mathbf { v } ) - \mathrm { S _ { s k y L } ( \mathbf { v } ) = \frac { R _ { b u r s t - L } ( \mathbf { v } ) - R _ { s k y L } ( \mathbf { v } ) } { C ^ { \ast } _ { L } ( \mathbf { v } ) } \cdot \frac { T _ { n l } ( \mathbf { v } ) - T _ { n 2 } ( \mathbf { v } ) } { R _ { n l } ( \mathbf { v } ) - R _ { n 2 } ( \mathbf { v } ) } } }
$$

环境及大气参数变化会使定标系数产生短期起伏和周年变化。太阳活动峰年时每日定标精度会下降。MST和TST的3个频段跨越了厘米-分米范围，大气吸收影响对3个频段是不同的。定标要求接收机必须有很好的线性[7及稳定性。要得到精确可靠的定标系数，需较长时间的观测数据统计分析。

# 4．初步结果

2016年底，MST和TST开始试观测。图6及表1为2016年12月15日MST与石岛及日本野边山类似太阳射电望远镜观测太阳结果进行比对，MST系统稳定性优于 $1 \%$ （10小时）。太阳在爆发时，强烈的无线电信号导致观测结果标准偏差显著增大。即使在无黑子的宁静期，望远镜也会接收来自不同天体或天空背景的电磁信号。所以通过观测太阳得到系统的稳定性需要长期的监测数据分析。另外减少周围环境影响,是取得长期稳定性的一个重要保证。今后将对系统稳定性作长期测试，并进一步分析测试影响系统稳定性的因素。

![](images/0bfe31c1a75d3c998cd836ae3b161070b60aecfaf1d5ba20a1aa565aa913ca7d.jpg)  
图6MST（红色）与类似的太阳射电望远镜-石岛（蓝色）及日本NORP（黑色）观测比对Fig.6PreliminaryresultofMTon3-bandcomparedwiththoseofimilarsolarradiotelescopesinShidaondinNobeyama,Japan表1.（对应图6）MST、石岛和日本NORP三台太阳射电望远镜观测值的相对标准偏差值Table1(referred to Figure6）Relative Standard Deviation of MST, Shidao Telescope and NORP

<html><body><table><tr><td></td><td>中国-MST</td><td></td><td>中国-石岛</td><td></td><td>日本-NORP</td></tr><tr><td>相对标准偏差</td><td>0.51%</td><td>2801MHz</td><td>0.88%</td><td>2801MHz</td><td>0.75% 2000MHz</td></tr><tr><td>相对标准偏差</td><td>1.01%</td><td>4542MHz</td><td>1.65%</td><td>4542MHz</td><td>2.38% 3500MHz</td></tr><tr><td>相对标准偏差</td><td>1.95%</td><td>9084MHz</td><td>2.75%</td><td>9084MHz</td><td>2.42% 9400MHz</td></tr></table></body></html>

系统稳定性通常是指接收机的稳定性。Allan 检验1是测量稳定性的最终方法，但需要大量的测量时间。本文通过测量接收机长期工作的增益起伏和信噪比得到接收机的稳定性，见图7。表明接收机16个小时的增益起伏很小，信噪比大于20dB。可认为接收机稳定性优于 $1 \%$ 。

![](images/4d33580fa93d1faaa8a5507e88fbfb92a0e5d778635da45dcfe0d0f020b49c6a.jpg)  
图72016年11月30日，接收机系统连续16个小时的稳定性监测Fig.7 Stability monitoring of receiving system lasting 16 hours on Nov.30,2016  
图8MSTS频段2017年1-10月太阳射电流量（红点）与加拿大Penticton数据（未考虑日地距离变化，绿线）比对Fig.8 Solar flux data of MAT S-band in 2O1701-2O1710(red dot) compared with that of Penticton $2 8 0 0 \mathrm { M H z }$ Solar Flux (green line.

150 130 110 WWW 100 M

至10月31日，2017年MST共有效观测太阳148天。图8为MST流量值（红点）与加拿大2800 MHz Penticton（绿线）比对，MST数据是先将毫秒级数据积分到秒，用正午1点（有爆发时避开）左右旋和3个频段太阳观测值分别减去当天背景，并乘以对应的校正系数得到的。2017年3月初对MST天线、接收机及软件进一步调试，并实现观测自动化，调试前后系统状态有变化，这可能是图8中MAT和加拿大数据比对时1月和2月偏离较大的原因，系统状态随季节变化也会导致偏离[1],这也是今后系统定标必须考虑的。2017年9月太阳活动区AR2673引起一系列太阳爆发现象，北京时间 2017年9月6日晚 20:02，太阳爆发了有史以来最耀眼的 X9.3级耀斑。图9给出了MST在9月1日-12日期间的观测，图10为2017年9月6日MSTX频段观测结果的局部细节放大。

![](images/7b06265982909f8f59a5edb56a40e414b32d0cbf9a74356d564d7ff7717ba960.jpg)  
图920170901-20170912期间MST三频段右旋秒级观测太阳数据（横轴：世界时，纵轴：20170901为基础逐日加10dB)

![](images/254d55f30dc09397c6d0e6209340116bb3ca3600dffd73bd9ed56eac1413a850.jpg)  
ig9Tbatd(Udd   
图10左：MSTX频段局部放大图(20170906 UT0:48-1:12);右：MSTX频段局部放大图(20170906 UT8:30-10:30) ig.10left:MSTX-bandenlargeddrawing（20170906UTO:48-1:12);right:MSTX-bandenlargeddrawing（2017906UT8:30-10:3C

# 5．结论

两台三频段太阳射电望远镜已分别在国家天文台(内蒙古)明安图观测基地和新疆塔什库尔干建成。受电磁干扰困扰，TST正在考虑迁址。MST则已获得太阳流量数据，并观测到数次太阳爆发，表明高稳定性（优于 $1 \% / 1 0$ 小时）、高灵敏度（优于1s.f.u）、大动态范围（30dB）以及可调时间分辨率设计，使望远镜兼具太阳射电爆发观测和辐射流量监测功能，当然观测结果还有待进一步鉴别。本文中首次设计采用双噪声源定标方法。2017年底试观测基础上对MST再次进行了调试，系统运行更加稳定可靠，2018年有望获得更多有效观测数据，以便在系统校准方面深入开展工作，今后并将对影响稳定性的因素作进一步分析和测试。

致谢：感谢支持和参与系统调试工作的中国电子科技集团第16所的黄文生、刘文齐、孙婷婷，中国电子科技集团第54研究所的耿京朝、武占为、张明，也向提出很好建议并参与系统观测等工作的国家天文台明安图观测基地的所有同事表示感谢。

# 参考文献：

1．美国国家研究理事会恶劣空间天气事件对社会和经济影响委员会(工作组).恶劣空间天气事件[M].王劲松,张效信，译.北 京：气象出版社,2011   
2．王劲松,焦维新.空间天气灾害[M].北京:气象出版社,2008.   
3. 张效信,杜丹,郭建广.空间天气定量预报模式[M].北京:气象出版社,2016.   
4. 颜毅华,张坚,陈志军,等.关于太阳厘米-分米波段频谱日像仪研究进展[J].天文研究与技术一国家天文台台刊，2006, 3(2):91-98. Yan Yihua,Zhang Jian,Chen Zhijun,etal.Progresson Chinese solarradioheliograph incm-dm wavebands[J].Astronomical Research & Technology—Publications of National Astronomical Observatories of China,20o6,3(2):91-98.   
5. 耿立红,颜毅华,宋庆辉,等.明安图射电频谱日像仪高频阵模拟接收机研制[J].天文研究与技术,2016,13(2):160-169. Geng Lihong,YanYihua,Song Qinghui,et al.MUSER-IIanalogreceiver system designinganddeveloping[J].Astronomical Research & Technology,2016,13(2):160-169.   
6. 傅其骏,郑乐平,李小聪,等.厘米分米波段太阳射电的绝对定标与常规测量[J].天体物理学报，1982.2(3):191-200. Fu Qijun,ZhengLeping,LiXiaocong,et.al.Absolutecalibrationofsolaremissionincentimeterbandanddailycalibration[J]. Acta Astrophysica Sinica,1982,2(3):191-200.   
7. Tanaka H,CasteliJP,CovingtonAE,et.al.absolutecalibrationof solarradiofluxdensityinthe microwaveregion[J].Solar Physics,1973,29:243-262.   
8. YanYH,TanCM,XuL.et.al.Nonlinearcalibrationanddataprocessingofthesolarradioburst[J].ScienceinChinaSeriesA: Mathematics,2002,45 (s1):89-96.   
9. Tan CM,YanYH,TanBL,etal.Calibrationofthe solarradio spectrometer[J].Science inChinaSeries G:Physics,Mechanics and Astronomy,2009,52(11):1760 -1764.   
10. Tan CM,YanYH,TanBL,etal.Studyof calibrationof solarradio spectrometersand thequiet-sunradioemisson[J].The Astrophysical Journal, 2015,808:61(14PP).   
11.Allan D W. Statistics of atomic frequency standards[J].Proceedings of the IEEE,1966,54(2): 21-230.

# Two New 3-Bands Solar Radio Polarimeters and Spaceweather

Geng Lihongl, Tan Chenming1,Dun Jinping², Zhang Hong³, Jia Yanhui4, Yan Yihual, Chen Zhijun1, Ma Suli1,5,Liu Donghaol, Du Jing1, Su Cang1 (1.AKe Wete 54th ResearchInstituteofCETC,hijiazhuang,O5o8l,China;5.ChinaUniversityofPetroleum,Qingdao,26580Cina)

Abstract:Itisan important methodof space weather predictor to monitorthesolarfluxcontinuouslyinlong-termwith the ground-basedsolardiotelescopes.olarfluxisoneofthemostusefulobservableidexes forpredictingindsoftrbulenceocurredn thearth excitedbythsunactivitiesandsolarultravioletradiation.Itrepresentsthesolartotalactivitylevel,especiallythe $1 0 . 7 \mathrm { c m }$ solar flux,whichhaslongbenusedassolaractivityindexsince96Os.WithefancialsupportofMC(atioalSateliteMeteoloical Center）andNAOC(NationalAstronmicalObservatories),twonew3-bandsradiotelescopesusedtomonitorthesolarfluxonthee wavelengths( $1 0 . 7 \mathrm { c m }$ $6 . 6 \mathrm { c m }$ and $3 . 3 \mathrm { c m }$ Dhave been set up in 2016 December in Mingantu Observatory of NAOC in inner Mongolia province and in Tashkurghan in Xinjiang province.The two telescopes, named MST and TST separately,each consisting of a $3 { \cdot } \mathrm { m }$ size diameter parabolic antenna, $2 { \cdot } 1 0 ~ \mathrm { G H z }$ wide band two-polarization feed,a constant temperature front-end box,will give more time coverage to observe the sun with the distance between the two sites is about $5 0 0 0 \mathrm { k m }$ and 2.67 hours zone away. Constant temperature of the front-box helpstokeptesstemstabilityspeialliningantundTashurganthweaterhangesseverelyfromourtoourAfteralibated, datasetsofitsformatwillbeuploadedautomaticallyeveryaythroughtheintemettothedatareductioncenterofNSMC,usedaspace weather monitoringdata.Double noise sources methodsisfirstadopted insystemcalibration.Thesystem stabilityisbettr than $1 \%$ in over 10 hours,system sensitivity is better than 1 s.f.u.,with $\Delta \mathrm { f } { = } 1 0 \mathrm { M H z }$ and $\Delta { \sf t } = 0 . 1 \mathrm { s }$ . The electromagnetic environment of MAT is much better thanthatofTT.I7,asotesoepreliaysults.I18,oeiientdatacanexpcteddfurtrokwlle done in system calibration and system stability testing and analyzing.

Key words: solar radio flux; telescope; $\mathrm { F } _ { 1 0 . 7 }$ index; calibration; spaceweather