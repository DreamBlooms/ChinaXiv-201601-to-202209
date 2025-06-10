# 动态环境下改进人工势场法的仓储机器人自主导航系统研究

罗强la,1b，王海宝la,b，崔小劲la，徐洪泽²(1.重庆三峡学院 a.机械工程学院;b.重庆市轻合金材料与加工工程技术研究中心，重庆404100;2.北京交通大学电子信息工程学院，北京 100044)

摘要：为了解决仓储机器人在全动态环境中的自主导航问题，在分析自主导航技术基础上建立了机器人和动态障碍物的数学模型，搭建了以2维激光雷达为主的环境感知平台，提出了一种改进的人工势场法。在传统的人工势场法中同时引入相对速度和相对加速度因素得到改进的人工势场模型，实现机器人在全动态环境中的自主移动。设计了无障碍物和多动态障碍物两种移动环境，经仿真验证，应用改进的人工势场法进行路径规划，能高效地避开动态障碍物、跟踪动态目标，且运动路径光滑。

关键词：动态环境；自主导航；人工势场；路径规划；激光雷达 中图分类号：TP242 doi:10.3969/j.issn.1001-3695.2018.09.0640

Research on autonomous navigation system of warehousing mobile robot based on improved artificial potential field method in dynamic environment

Luo Qiangla,1b, Wang Haibaola,1b, Cui Xiaojingla, Xu Hongze² (1. a.School of Mechanical Engineeing,b.Chongqing Engineering Technology Research Center for Light Alloy & Processing，Chongqing Three Gorges University，Chongqing 404100,China；2.School of Electronic& Information Engineering,Beijing Jiaotong University,Beijing 10oo44, China)

Abstract: In order to solve the problems of warehousing mobile robots autonomous navigation in fulldynamic environment, this paperestablished a mathematical model of robotsand dynamicobstacles，designedaplatform of environmental awarenesbasedon2-dimensional lidar,and proposedan improvedartificial potential fieldmethod.It introduced the relativespeedandrelativeaccelerationtothetraditionalartificial potentialfield method，thendesignedthematlab simulationinfulldynamic environment.Itisverifiedthat theimprovedartificialpotential field method is used toplanpath, which can eectively avoid the dynamic obstacles,track the dynamic target,and the movement path is smooth.

Key words: dynamic environment; autonomous navigation; artificial potential field; path planning; laser radar

# 0 引言

随着物流行业的快速发展，对货物的仓储、分拣和运输都需要大量的人力物力参与，在当前人口红利逐渐消失的形势下，机器人的参与成为了人们探讨的重点，无人仓库、无人分拣、无人派送等先进技术应运而生，而仓储机器人就是无人仓库中最重要的角色[1。仓储机器人在无人参与的情况下自主完成货物的识别、装卸和运输，可24小时持续工作，在很大程度上节约劳动力成本，提高工作效率，如亚马逊公司在全美的仓库中运用仓储机器人，每年节约成本将近10亿美元。

仓储机器人关键技术成为了国内外研究机构研究的重点，自主导航是仓储机器人研究中最核心技术，其包括对环境的感知、机器人自身定位和路径规划几大部分。对环境的感知主要融合一系列传感器信息来实现，如超声波、红外线、激光雷达、图像等；机器人的定位可由GPS、惯性（速度、位移计等）、Wi-Fi、LBS基站、环境磁场定位技术来实现[2l;路径规划是自主导航技术中最重要的部分，是解决仓储机器人在复杂、动态环境中如何搜寻出一条到达目标货架的最优或近似最优、无碰撞路径的问题[3]。

路径规划需要机器人对环境的感知和自身定位信息，在采用一定的规划算法来实现。近40年国内外对路径规划进行了广泛研究，并取得了一定的成果。目前，常用的路径规划算法有人工势场法、向量法、栅格法、蚁群算法、模糊神经网络、遗传算法、模型预测法、A\*算法[4.5]等，这些算法都各有千秋，并适用于不同的应用场所中。其中人工势场法是由Khatib 提出的一种虚拟力场法[6]，其将机器人在环境中的运动虚拟为一种在人工受力场的运动，目标对机器人产生引力，障碍物产生斥力，引力和斥力的合力控制机器人的运动。该算法因其数学分析简单、计算量小、路径光滑等优点被广泛应用在实时避障和路径规划领域。

在过去针对人工势场法的研究中，大量的研究致力于如何改进人工势场法[78]以解决该算法存在的局部最小值点和目标不可达问题，虽取得显著的成效，但大多数都是应用于静态环境中，即目标和障碍物都处于静止不动状态。然而，在无人仓储应用环境中，仓储机器人所处的环境是复杂的、动态变化的。首先，目标可能是运动的，如Fetch和Freight仓储机器人，Fetch负责将商品从货架上拿下来，Freight负责将商品运送打包，Fetch机器人作为目标就是动态变化的，Freight则需要动态跟随目标。其次，障碍物也有动态和静态的，在无人仓库中的货架、物品、墙壁、工作台等都属于静态障碍物，但同时运行的其他仓储机器人和工作人员就变成了动态障碍物。

针对全动态环境下的路径规划问题，国内外学者也开展了相关研究，文献[9]提出一种改进的路径规划算法，基于动态障碍物设计了一种新的避障规则，有效实现避障和跟踪目标，但采用相同距离的规划步长，即只考虑规划方向而未考虑规划驱动力的变化，且规划路径不光滑，存在大的转角变化。文献[10,11]提出了一种改进的人工势场法，在引力势场函数中引入相对速度和相对加速度，有效解决动态目标的跟踪问题；在斥力势场函数中引入相对速度因素，来绕开动态障碍物，但存在动态避障效率不高、规划路径长的问题。

本文重点对仓储机器人自主导航技术中的环境感知和路径规划问题。首先采用2维激光雷达构建仓储机器人环境感知系统，实时检测机器人周围的障碍物姿态；然后在传统人工势场法基础上引入相对位置、相对速度以及相对加速度，改进势场函数，从而解决仓储机器人在全动态环境中自主导航问题。

# 1 移动环境模型建立

# 1.1仓储机器人数学模型

本文选用的仓储机器人模型如图1所示，后轮为2轮差速驱动轮，前轮为2个起支撑作用的万向轮。此种机器人系统为典型的非完整约束是非完整系统[12]，机器人的姿态可描述为 $\bar { X } ^ { r } = [ x ^ { r } , y ^ { r } , \theta ^ { r } ] ^ { r } \subset R ^ { 3 }$ 0

![](images/3d752475f4e1c7963aa21c4837c04d7322f12a5ea97d7e8d8ecb9ce1a23ce3eb.jpg)  
图1仓储机器人模型  
Fig.1Warehousing robot model

其数学模型为

$$
\left\{ \begin{array} { l } { \dot { x } ^ { r } = \nu ^ { r } \cos \theta ^ { r } } \\ { \dot { y } ^ { r } = \nu ^ { r } \sin \theta ^ { r } } \\ { \dot { \theta } ^ { r } = \omega ^ { r } } \end{array} \right.
$$

其中： $( x ^ { r } , y ^ { r } )$ 为机器人的位置坐标， $\theta ^ { r }$ 为机器人的位姿角，$\boldsymbol { \nu } ^ { r }$ 为机器人的瞬时线速度， $\omega ^ { r }$ 为机器人转动角速度。机器人系统的输入为 $U ^ { r } = [ \nu ^ { r } , \omega ^ { r } ] \in U _ { n h } ^ { r } \subset R ^ { 2 }$ ，输入范围为$U _ { n h } ^ { r } = [ \nu _ { \operatorname* { m i n } } ^ { r } , \nu _ { \operatorname* { m a x } } ^ { r } ] \times [ \omega _ { \operatorname* { m i n } } ^ { r } , \omega _ { \operatorname* { m a x } } ^ { r } ]$ 。在实际应用中，机器人的姿态是动态变化的，即机器人下一时刻的姿态为当前姿态加上单位时间内的变化量，可以用欧拉近似法来描述机器人的姿态变化关系。

$$
\bar { X } _ { n + 1 } ^ { r } = \bar { X } _ { n } ^ { r } + \Delta f ^ { \ r } ( \nu _ { n } ^ { r } , \omega _ { n } ^ { r } )
$$

其中： $\Delta$ 为机器人规划间隔时间， $f ^ { r } ( \nu _ { n } ^ { r } , \omega _ { n } ^ { r } )$ 是关于机器人运动线速度 $\boldsymbol { \nu } ^ { r }$ 和角速度 $\omega ^ { r }$ 的函数，其数学关系为

$$
f ^ { r } ( \nu _ { n } , \omega _ { n } ) = { \left[ \begin{array} { l } { \nu _ { n } ^ { r } \cos \theta _ { n } ^ { r } } \\ { \nu _ { n } ^ { r } \sin \theta _ { n } ^ { r } } \\ { \omega _ { n } ^ { r } } \end{array} \right] }
$$

当机器人为变加速度运动时，机器人的速度关系为

$$
\nu _ { n + 1 } ^ { r } = \nu _ { n } ^ { r } + \Delta \bullet a _ { n } ^ { r }
$$

本文中所有表达式中用上标 $\boldsymbol { r }$ 表示与机器人相关，上标$\mid o \mid$ 表示与障碍物相关，上标 $g$ 则表示与目标相关。

# 1.2动态障碍物数学模型

在无人仓储环境中，动态障碍物可为行走的人、其他仓储机器人、移动的货架等，其运动状态可以为匀速、变速的直线运动或者曲线运动，且可在几种运动模型中随机切换[12]。障碍物的姿态可用 $\bar { X } ^ { o } = [ x ^ { o } , y ^ { o } , \theta ^ { o } ] ^ { _ T } \subset R ^ { 3 }$ 来表示，在实际应用中同样可采用欧拉近似法得到障碍物的姿态变化方程：

$$
\bar { X } _ { n + 1 } ^ { o } = \bar { X } _ { n } ^ { o } + \Delta \bullet f ^ { o } ( q _ { n + 1 } ^ { o } , w _ { n } ^ { o } , \theta _ { n } ^ { o } )
$$

其中： $q _ { n + 1 } ^ { o } \in ( l i n e , a r c )$ ，代表了下一时刻机器人的运动状态是直线运动或是曲线运动。如果 $q _ { n + 1 } ^ { o } = l i n e$ 则为直线运动，此时 $w _ { n } ^ { o }$ 为线速度；若 $q _ { n + 1 } ^ { o } = a r c$ 则为曲线运动，此时 $w _ { n } ^ { o }$ 为角速度。不同运动状态下 $f ^ { o } ( q _ { n + 1 } ^ { o } , w _ { n } ^ { o } , \theta _ { n } ^ { o } )$ 也存在一定的差异。

直线运动状态时，

$$
f ^ { o } ( l i n e , w _ { n } ^ { o } , \theta _ { n } ^ { o } ) = \left[ \begin{array} { l } { w _ { n } ^ { o } } \\ { \gamma w _ { n } ^ { o } } \\ { 0 } \end{array} \right]
$$

其中：／为直线运动的斜率，可由 $\gamma = \tan \theta _ { n } ^ { o }$ 求的。

曲线运动状态时，

$$
f ^ { o } ( a r c , w _ { n } ^ { o } , \theta _ { n } ^ { o } ) = { \left[ \begin{array} { l } { r w _ { n } ^ { o } \cos \theta _ { n } ^ { o } } \\ { r w _ { n } ^ { o } \sin \theta _ { n } ^ { o } } \\ { w _ { n } ^ { o } } \end{array} \right] }
$$

其中： $\boldsymbol { r }$ 为曲线运动时圆弧半径，在随机运动环境中， $\boldsymbol { r }$ 也是可以动态变化的。同时， $w ^ { o }$ 也可动态变化，则$w _ { n + 1 } ^ { o } = w _ { n } ^ { o } + \Delta \bullet a _ { n } ^ { o }$ 。

# 1.3条件假设

仓储机器人的自主导航系统包括硬件平台和软件平台，功能上实现机器人自身定位、外界环境感知和路径规划算法。本文重点研究仓储机器人对外界环境的感知和全动态环境下的路径规划问题，为了简化分析，可作如下假设：

机器人的位置 $p ^ { r }$ 、速度 $\boldsymbol { \nu } ^ { r }$ 和加速度 $\boldsymbol { a } ^ { r }$ 都实时可知，且仓储机器人外形可视为半径为 $R$ 的圆形。

目标的位置 $p ^ { g }$ 、速度 $\nu ^ { g }$ 和加速度 $a ^ { g }$ 都可实时检测到，且目标的速度满足 $\big | \nu ^ { g } \big | \big \vert \nu _ { \mathrm { m a x } } ^ { r } \big \vert$ 。

障碍物的位置 $p ^ { o }$ 、速度 $\nu ^ { o }$ 和加速度 $a ^ { o }$ 都可实时获得，其外形可视为为半径为 $R _ { i } ^ { o }$ 的圆形。

假设目标和障碍物都为匀加速运动，达到最大运行速度后为匀速运动。

# 2 激光雷达构建环境感知平台

# 2.1激光雷达工作原理

激光雷达是传统雷达和激光技术相结合的产物，它利用激光载波先向目标发射探测信号，然后将其接收到的同波信号与发射信号相比较，从而获得目标的位置（距离、方位和高度）、运动状态（速度、姿态）等信息，实现对目标的探测、跟踪和识别。

利用2维激光雷达实现仓储机器人自主导航的工作原理：将激光雷达固定在机器人上，实时扫描周围环境，得到周围障碍物的实时距离和方位，则可构建与机器人为中心、以雷达扫描半径为最大区域的环境地图，多次测量可辨别出障碍物的运动姿态，进而为机器人的路径规划提供基础。

# 2.2激光雷达数据的获取

本文选用RPLIDAR系列激光雷达，测量距离为0.15\~8米，扫描角度范围为 $0 ^ { \circ }$ ${ \sim } 3 6 0 ^ { \circ }$ ，测距分辨率最大为 $0 . 5 ~ \mathrm { m m }$ 角度分标率为 $0 . 4 5 ^ { \circ }$ ，扫描频率为10 赫兹，即1S扫描10周。其数据采集模型如图2所示，经扫描可确定障碍物相对于激光雷达的距离 $\rho _ { i j }$ ，由激光光束号可确定方位，从而得到以激光雷达为中心坐标系的极坐标数据点 $( \rho _ { i j } , \phi _ { i j } )$ ，其中$\phi _ { i j } = ( j - 1 ) * 0 . 4 5 ^ { \circ }$ $j = 1 \sim 8 0 1$ 。

![](images/de0edc427b1ba869ccf6157271a4772412b253241db445d16a7be7cf95208416.jpg)  
图2激光雷达模型 Fig.2Lidar model

当激光雷达与机器人几何中心重合时，激光雷达的位置坐标可以机器人位置坐标来表示，若机器人的位置坐标为$( x ^ { r } , y ^ { r } )$ 时，那障碍物的位置坐标则为

$$
( x ^ { o } , y ^ { o } ) ^ { T } = { \left[ \begin{array} { l } { x ^ { r } } \\ { y ^ { r } } \end{array} \right] } + { \left[ \begin{array} { l } { \rho _ { i j } \cos \phi _ { i j } } \\ { \rho _ { i j } \sin \phi _ { i j } } \end{array} \right] }
$$

其中： $j$ 表示同一周期内的激光束号， $i$ 表示采样时间序列。

采样的激光雷达数据中不可避免地存在噪声点，这样会降低障碍物或目标检测的精度，在实际设计中需要对原始数据进行滤波处理。文献[13]提出一种自适应曲率滤波算法，以激光雷达在第 $i$ 时刻第 $j$ 个扫描线所测量的距离 $\rho _ { i j }$ 为中心，建立 $3 { \times } 3$ 的数据分析窗口，分析9个数据在时间和空间上的最大相关性，可有效地减少噪声，又能够保持数据边界点、保留离群点。文献[14]中提出了基于高程信息平坦度的均值滤波算法，即先将激光雷达的强度信息转换为灰度图像，然后对各像素进行均值滤波处理。激光雷达数据常见的滤波算法还有基于数学形态学的滤波算法、基于坡度的滤波算法、基于TIN的LIDAR点云过滤算法、基于伪扫描线的滤波算法等，相关算法研究较多且容易实现，此处不再赘述。

由实时获取的障碍物位置坐标可判断障碍物为静止或动态运动状态，且可计算出障碍物的瞬时速度和加速度等，为后续的路径规划提供数据支持。在无人仓储系统中，由于动态但障碍物多为其他仓储机器人，仓储机器人自身具有定位功能，也可构建无线网络系统，利用无线网络实时分享自身的姿态和位置，从而可构建全局路径规划环境，在无线网络中的多机器人协同工作将会在后续研究中涉及。

# 3 路径规划算法研究

# 3.1传统人工势场法

传统的人工势场法只考虑机器人与目标、障碍物的距离因数，目标对机器人产生的引力势场与两者距离成正比例关系，离目标越远产生的引力势场越大，反之则越小，从而牵引机器人向目标逼近；障碍物对机器人产生的斥力势场与两者距离成反比例关系，离障碍物越近产生的斥力越大，反之则越小，以达到避障的效果[15]。其数学函数关系如式(9)(10)所示。

$$
U _ { a t t } ( p ) = { \frac { 1 } { 2 } } k \parallel p ^ { r } - p ^ { g } \parallel ^ { 2 }
$$

$$
U _ { r e p } ( X ) = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { 2 } m ( \frac { 1 } { \rho } - \frac { 1 } { \rho _ { 0 } } ) ^ { 2 } , \qquad } & { \rho < \rho _ { 0 } } \\ { 0 , \qquad } & { \rho \geq \rho _ { 0 } } \end{array} \right.
$$

其中： $k , m$ 分别为引力和斥力势场增益系数， $\| p ^ { r } - p ^ { g } \|$ 为机器人相对于目标的距离， $\rho { = } { } { \left| \left| \begin{array} { l l } { p ^ { r } - p ^ { o } } \end{array} \right| \right|} $ 为机器人与障碍物的距离， $\rho _ { 0 }$ 为障碍物斥力势场对机器人产生影响的距离界限，当$\rho > \rho _ { 0 }$ 时机器人受斥力作用，反之则不受。

引力和斥力分别有相应势场函数的负梯度求得，分别为

$$
F _ { a t t } ( p ) = - g r a d [ U _ { a t t } ( p ) ] = - k \parallel P ^ { r } - P ^ { g } \parallel
$$

其方向为由机器人指向目标。

$$
F _ { r e p } ( { p } ) = - g r a d [ U _ { r e p } ( { p } ) ] = \left\{ \begin{array} { l l } { { m ( \displaystyle \frac { 1 } { \rho } - \displaystyle \frac { 1 } { \rho _ { 0 } } ) \displaystyle \frac { 1 } { \rho ^ { 2 } } , ~ \rho < \rho _ { 0 } ~ } } & { { } } \\ { { 0 , ~ } } & { { \rho \ge \rho _ { 0 } } } \end{array} \right.
$$

其方向为由障碍物指向机器人。当由多个障碍物时，$F _ { r e p \triangle } = \sum _ { i = 1 } ^ { n } F _ { r e p i }$ ，最后斥力和引力的合力 $F _ { t o t a l } = F _ { a t t } + F _ { r e p \ e s }$ 为机器人提供下一步路径规划方向和力。

传统人工势场法适用于静态环境的路径规划，而对于全动态的仓储应用环境，目标和障碍物都存于随机运动，运动形式和姿态都实时变化，将无法满足规划要求。

# 3.2改进人工势场法

# 3.2.1改进的引力势场函数和引力

当目标为运动状态的取件机器人时，不仅对仓储机器人的位置作出要求，还需要其与目标保持相同的速度和相同的运动趋势，即机器人与目标的相对速度和相对加速度为零。传统的引力势场函数是无法满足要求的，需要进一步改进。

为了解决仓储机器人的速度和加速度需和目标保持相同运动趋势的问题，特将机器人与目标点的相对速度和相对加速度因素引入到传统引力势场函数中[15:16]，如式(13)所示。

$$
\begin{array} { c } { { U _ { a t t } ( p , \nu , a ) { = } \displaystyle \frac { 1 } { 2 } k _ { p } \parallel p ^ { r } - p ^ { s } \parallel ^ { 2 } { + } \displaystyle \frac { 1 } { 2 } k _ { \nu } \parallel \nu ^ { r } - \nu ^ { g } \parallel ^ { 2 } + } } \\ { { \displaystyle \frac { 1 } { 2 } k _ { a } \parallel a ^ { r } - a ^ { g } \parallel ^ { 2 } } } \end{array}
$$

其中： $\boldsymbol { k } _ { p }$ 、 $k _ { \nu }$ 和 $k _ { a }$ 都为正因常数因子， $p ^ { r }$ 、 $p ^ { g }$ 、 $\nu ^ { r }$ 、 $\nu ^ { g }$ 、$a ^ { r }$ 和 $a ^ { g }$ 分别为机器人和目标的位置、速度和加速度。$\| p ^ { r } - p ^ { g } \|$ 为机器人与目标之间的几何距离， $\left\| \nu ^ { r } - \nu ^ { g } \right\|$ 为机器人与目标之间的相对速度大小， $\left\| a ^ { r } - a ^ { g } \right\|$ 为机器人与目标之间的相对加速度大小。

由式(13)可见，当且仅当机器人与目标的相对位置、相对速度和相对加速度三项都为零时，引力势场函数才为零，否则将会持续为仓储机器人提供引力作用。

其引力函数可由引力势场函数的负梯度求的，其推导如式(14)所示。

$$
\begin{array} { c } { { F _ { a t t } ( p , \nu , a ) = - g r a d [ U _ { a t t } ( p , \nu , a ) ] = - g r a d _ { p } [ U _ { a t t } ( p , \nu , a ) ] } } \\ { { - g r a d _ { \nu } [ U _ { a t t } ( p , \nu , a ) ] - g r a d _ { a } [ U _ { a t t } ( p , \nu , a ) ] } } \end{array}
$$

令

$$
\begin{array} { l } { { \displaystyle F _ { a t t x } ( p ) = - g r a d _ { _ P } [ U _ { a t t } ( p , \nu , a ) ] = - \frac { \displaystyle \hat { \sigma } U _ { a t t } ( p , \nu , a ) } { \displaystyle \hat { \sigma } p } } } \\ { { \displaystyle ~ = - k _ { p } \parallel p ^ { r } - p ^ { s } \parallel } } \end{array}
$$

其方向为由机器人指向目标点。

同理，令

$$
\begin{array} { l } { { \displaystyle F _ { a t t \nu } ( \nu ) = - g r a d _ { \nu } [ U _ { a t t } ( x , \nu , a ) ] = - \frac { \hat { \sigma } U _ { a t t } ( x , \nu , a ) } { \hat { \sigma } \nu } } } \\ { { \displaystyle \qquad = - k _ { \nu } \parallel \nu ^ { r } - \nu ^ { g } \parallel } } \end{array}
$$

其方向为由目标点速度向量与机器人速度向量之差向量$\vec { \nu } ^ { g } - \vec { \nu } ^ { r }$ 的方向。

$$
\begin{array} { l } { { \displaystyle F _ { a t t a } ( a ) = - g r a d _ { a } [ U _ { a t t } ( x , \nu , a ) ] = - \frac { \displaystyle \hat { \partial } U _ { a t t } ( x , \nu , a ) } { \displaystyle \hat { \partial } a } } } \\ { { \displaystyle \quad = - k _ { a } \left. a ^ { r } - a ^ { s } \right. } } \end{array}
$$

其方向为由目标点加速度向量与机器人加速度向量之差向量 $\vec { a } ^ { g } - \vec { a } ^ { r }$ 的方向。

则机器人受到的引力为

$$
F _ { a t t } \left( x , \nu , a \right) = F _ { a t t x } \left( x \right) + F _ { a t t \nu } \left( \nu \right) + F _ { a t t a } \left( a \right)
$$

引力计算过程及各向量的关系如图3所示。

![](images/9eff457f05030abdd77d963c9a05d23c8287f173f2c2ebc76076df18126d9283.jpg)  
图3计算引力过程

3.2.2改进的斥力势场函数和斥力

在全动态环境中，障碍物也处于运动状态，与改进的引力势场函数类似，在斥力势场函数中同样引入相对速度和相对加速度因素[17]，如式(19)所示。

$$
U _ { r e p } ( p , \nu , a ) = \left\{ \begin{array} { c } { \displaystyle { \frac { 1 } { 2 } } { m _ { p } } ( \frac { 1 } { \rho } - \frac { 1 } { \rho _ { 0 } } ) ^ { 2 } + { m _ { \nu } } \left\| { \nu } ^ { r } - { \nu } ^ { o } \right\| \cos \alpha } \\ { \displaystyle { + m _ { a } } \left\| { a } ^ { r } - { a } ^ { o } \right\| \cos \beta , } \\ { \displaystyle { \rho < = \rho _ { 0 } \& { \& } \alpha \alpha \alpha \in ( - \frac { \pi } { 2 } , \frac { \pi } { 2 } ) } } \\ { \displaystyle { 0 } \qquad \quad , \rho > \rho _ { 0 } \left\| \alpha \not \in ( - \frac { \pi } { 2 } , \frac { \pi } { 2 } ) \right. } \end{array} \right.
$$

应

$$
U _ { r e p p } = \frac { 1 } { 2 } m _ { p } ( \frac { 1 } { \rho } - \frac { 1 } { \rho _ { 0 } } ) ^ { 2 }
$$

$$
U _ { r e p \nu } = m _ { \nu } \parallel \nu ^ { r } - \nu ^ { o } \parallel \cos \alpha
$$

$$
U _ { r e p \nu } = m _ { a } \left\| a ^ { r } - a ^ { o } \right\| \cos \beta
$$

其中： $m _ { p }$ 、 $m _ { v }$ 和 $m _ { a }$ 都为正因常数因子， $\scriptstyle { \nu ^ { o } }$ 和 $a ^ { o }$ 分别为障碍物的速度和加速度。 $\| \nu ^ { r } - \nu ^ { o } \|$ 为机器人与障碍物之间的相对速度大小， $\left\| a ^ { r } - a ^ { o } \right\|$ 为机器人与障碍物之间的相对加速度大小。$\alpha$ 、 $\beta$ 分别为机器人相对于障碍物的相对速度矢量和相对加速矢量与相对位置矢量的夹角，可看出改进后的斥力势场函数引入了相对速度和相对加速度在机器人与障碍物连线上的分量，各斥力势场关系如图4所示。

![](images/e4534bc3a794b1c002822b6a61cbe1e479c21187e519e21020052bbc1d8070b8.jpg)  
Fig.3Attraction force calculation process   
图4改进的斥力势场向量关系  
Fig.4Relation of improved repulsive potential field vectors

为了便于分析引入的相对速度分量与相对位置的关系，可将坐标系进行一定平移和旋转处理，先将坐标原点移到障碍物中心点，再将 $X$ 轴旋转到障碍物相对于机器人的速度方向，建立新的直角坐标系。在此坐标系中，机器人的位置坐标可记为 $( x _ { o r } , y _ { o r } )$ ，引入齐次变换矩阵，可得到机器人在新旧坐标中的变换关系如式(23)所示。

$$
M = { \left[ \begin{array} { l } { 1 \ 0 \ - x ^ { o } } \\ { 0 \ 1 \ - y ^ { o } } \\ { 0 \ 0 1 } \end{array} \right] } { \left[ \begin{array} { l l l } { \cos \psi \ - \sin \psi \ 0 } \\ { \sin \psi } & { \ \cos \psi \ 0 } \\ { 0 } & { \ 0 } & { 1 } \end{array} \right] }
$$

其中 $\psi$ 为障碍物相对于机器人速度方向与原坐标系的夹角。

在转换后的坐标系中，可求得

$$
\cos \alpha = \frac { x _ { o r } } { \sqrt { x _ { o r } ^ { 2 } + y _ { o r } ^ { 2 } } }
$$

由式(21)(24)可推导出

$$
\begin{array} { c } { { F _ { r e p p 2 } = - \nabla p U _ { r e p \nu } = - \nabla p ( m _ { \nu } \parallel \nu ^ { r } - \nu ^ { o } \parallel \cos \alpha ) } } \\ { { = - m _ { \nu } \displaystyle \frac { \parallel \nu ^ { r } - \nu ^ { o } \parallel } { \sqrt { x _ { o r } ^ { 2 } + y _ { o r } ^ { 2 } } } \sin \alpha ( \sin \alpha , - \cos \alpha ) } } \\ { { = - m _ { \nu } \displaystyle \frac { \parallel \nu ^ { r } - \nu ^ { o } \parallel } { \rho } \sin \alpha ( \sin \alpha , - \cos \alpha ) } } \end{array}
$$

$\mid F _ { r e p p 2 } \mid = - m _ { \nu } \frac { \parallel \nu ^ { r } - \nu ^ { o } \parallel } { \rho } \mid \sin \alpha \mid$ |sinα|，即为机器人与障碍物的相对速度在两者连线垂线上的分量。

同理，可由式(22)求得

$$
\begin{array} { l } { { F _ { r e p p 3 } = - \nabla p U _ { r e p \nu } = - \nabla p ( m _ { a } \parallel a ^ { r } - a ^ { o } \parallel \cos \beta ) } } \\ { { \ } } \\ { { \ } } \\ { { \displaystyle \ = - m _ { a } \frac { \parallel a ^ { r } - a ^ { o } \parallel } { \sqrt { { \chi _ { o r } } ^ { 2 } + { \ y _ { o r } } ^ { 2 } } } \sin \beta ( \sin \beta , - \cos \beta ) } } \\ { { \ } } \\ { { \displaystyle \ = - m _ { a } \frac { \parallel a ^ { r } - a ^ { o } \parallel } { \rho } \sin \beta ( \sin \beta , - \cos \beta ) } } \end{array}
$$

$\mid F _ { r e p p 3 } \mid = - m _ { a } \frac { \parallel a ^ { r } - a ^ { o } \parallel } { \rho } \mid \sin \beta \mid$ ,即为机器人与障碍物的相对加

速度在两者连线垂线上的分量。

由式(20)可求得

$$
\begin{array} { l } { { \displaystyle F _ { r e p p 1 } = - \nabla p U _ { r e p p } = - \nabla p [ \frac { 1 } { 2 } m _ { p } ( \frac { 1 } { \rho } - \frac { 1 } { \rho _ { 0 } } ) ^ { 2 } ] } } \\ { { \displaystyle \ } } \\ { { \displaystyle \ = m _ { p } ( \frac { 1 } { \rho } - \frac { 1 } { \rho _ { 0 } } ) \frac { 1 } { \rho ^ { 2 } } } } \end{array}
$$

可以求的势场函数关于速度和加速度的负梯度函数，如式(28)(29)所示。

$$
\begin{array} { r l } & { \boldsymbol { F } _ { r e p \nu } = - \nabla \nu ( \boldsymbol { U } _ { r e p p } + \boldsymbol { U } _ { r e p \nu } + \boldsymbol { U } _ { r e p a } ) } \\ & { \qquad = - \nabla \nu \boldsymbol { U } _ { r e p \nu } = - \nabla \nu ( m _ { \nu } \parallel \nu ^ { r } - \nu ^ { o } \parallel \cos \alpha ) } \\ & { \qquad = - m _ { \nu } \cos \alpha } \end{array}
$$

$$
\begin{array} { r l } & { \boldsymbol { F } _ { r e p a } = - \boldsymbol { \nabla } a ( \boldsymbol { U } _ { r e p p } + \boldsymbol { U } _ { r e p \nu } + \boldsymbol { U } _ { r e p a } ) } \\ & { \qquad = - \boldsymbol { \nabla } a \boldsymbol { U } _ { r e p a } = - \boldsymbol { \nabla } a ( m _ { a } \parallel a ^ { r } - a ^ { o } \parallel \cos \beta ) } \\ & { \qquad = - m _ { a } \cos \beta } \end{array}
$$

由式(25)\~(29)可得到斥力函数为

$$
F _ { r e p } = \left\{ \begin{array} { l l } { \displaystyle { F _ { r e p p 1 } + F _ { r e p p 2 } + F _ { r e p p 3 } + F _ { r e p v } + F _ { r e p a } } , } \\ { \displaystyle { \rho < \rho _ { 0 } \& \& \alpha \alpha \in ( - \frac { \pi } { 2 } , \frac { \pi } { 2 } ) } } \\ { \displaystyle { 0 , \quad \quad \rho > \rho _ { 0 } \| \alpha \notin ( - \frac { \pi } { 2 } , \frac { \pi } { 2 } ) } } \end{array} \right.
$$

图5展示了斥力函数计算过程和各函数关系。

由图5可见，改进后的斥力函数在传统斥力函数的位置斥力作用基础上，额外增加了 $F _ { r e p \nu }$ 和 $F _ { r e p a }$ 两个斥力，加大了障碍物排斥作用，同时，在垂直于位置斥力方向上，额外增加了 $F _ { r e p 2 }$ 和 $F _ { r e p 3 }$ 两个力，为机器人提供绕行障碍物的能力。

最后由 $F _ { r e p }$ 和 $F _ { a t t }$ 的合力为机器人提供下一步规划方向和力。

$$
a _ { n } ^ { r } = \frac { F _ { t o t a l } } { m }
$$

$$
\nu _ { n + 1 } ^ { r } = \left\{ { \begin{array} { l l } { \nu _ { n } ^ { r } + a _ { n } ^ { r } \bullet \Delta , } & { \left| \nu _ { n } ^ { r } \right| < \nu _ { \operatorname* { m a x } } ^ { r } } \\ { \nu _ { \operatorname* { m a x } } ^ { r } } & { , } \end{array} } \right.
$$

![](images/d84cd77a1d102835b519d28a4ff3285097fa965b20baffe244d3a37ecb528806.jpg)  
图5斥力函数计算过程

# 4 仿真及结果分析

为了验证改进的人工势场法在仓储机器人路径规划中的可行性，通过MATLABR2016a分别在无障碍情况下的目标跟踪和有障碍物情况下的目标跟踪进行了仿真实验。

# 4.1算法描述

为了解决仓储机器人在动态环境下的路径规划，本文重点将机器人与目标点、障碍物的相对速度和相对加速度引入势场函数中，从而得到了改进的引力和斥力函数。算法的开展首先需要获取机器人自身、目标和障碍物的位置、速度和加速度信息；其次，计算出目标对机器人的引力作用；再次，判读机器人是否处于障碍物斥力作用范围，如果在则计算出相应的斥力值，否则，斥力作用为零；最后，计算机器人受到的合力，以计算机器人在下一步的加速度和速度，最终实现跟踪目标运动。具体流程如图6所示。

![](images/938e0ac9abcb99e7523322b3c2e1dbe207b075621114ac8fa5b2c041a86d4ad4.jpg)  
Fig.5Repulsion function calculation process   
Fig.6Flow diagram of improved artificial potential field algorithm

# 4.2无障碍情况下的目标跟踪

首先可在无障碍物情况下根据改进的引力函数对目标进行跟踪实验，从而调节引力函数中的相关参数，选择合适的数值，仿真参数如表1所示。

表1无障碍物情况下的仿真参数  
Table1 Simulation parameters without obstacles   

<html><body><table><tr><td>仿真参数名称及符号</td><td>值/(单位)</td></tr><tr><td>仿真环境面积s</td><td>30 × 30/ (m2)</td></tr><tr><td>目标初始位置p</td><td>(5,27)/(m)</td></tr><tr><td>目标初始速度v</td><td>(0.3,-0.3)/(m/s)</td></tr><tr><td>目标初始加速度a</td><td>(0.2,-0.4)/(m/s²)</td></tr><tr><td>机器人初始位置p</td><td>(3,15)/(m)</td></tr><tr><td>机器人初始速度v"</td><td>(0,0)/(m/s)</td></tr><tr><td>机器人初始加速度a"</td><td>(0,0)/(m/s²)</td></tr><tr><td>机器人质量m</td><td>10/(Kg)</td></tr><tr><td>规划时间△</td><td>0.3/(s)</td></tr><tr><td>最大移动速度Vmax</td><td>3/(m/s)</td></tr></table></body></html>

在相同环境下经过多次实验，调整 $k _ { x }$ 、 $k _ { \nu }$ 和 $k _ { a }$ 三个参数，可以获得不同的跟踪效果，有的能够达到快的响应时间，但存在过大的振荡，增大跟踪路程开销，如图7所示；有的追踪过程平稳，但响应缓慢，需要长的跟踪时间，如图8所示。

![](images/d8d52dca10b3d7145c2433393d7299c7b2f522a40c32a3da739047a7956af9dc.jpg)  
图7 $k _ { p } = 2 , k _ { \nu } = 3 , k _ { a } = 3$ 时路径规划

![](images/92c9527b02aabcb0aeef4498bf82e75021cfce4189831a736fbdab00727f2dd0.jpg)  
图6改进人工势场法路径规划流程  
Fig.7Path planning at $k _ { p } = 2 , k _ { \nu } = 3 , k _ { a } = 3$   
图8 $k _ { p } = 4 , k _ { \nu } = 2 , k _ { a } = 1$ 时路径规划 Fig.8Path planning at $k _ { p } = 4 , k _ { \nu } = 2 , k _ { a } = 1$

可见在追踪目标的时响应速度、稳定性和精确性存在一定的矛盾，在参数选择时，需要折中考虑，当 $k _ { x } = 4$ 、 $k _ { \nu } = 5$ 和$k _ { a } = 2$ 时，跟踪效果最为理想，在 $T = 6 s$ 时，机器人就跟踪上目标，并和目标保持相同的运动状态，路径规划如图9所示。

# 4.3有障碍物情况下的目标跟踪

在动态目标环境的基础上，随机设定3个动态障碍物来验证仓储机器人具备在动态环境中避障和目标跟踪的能力，具体仿真参数如表2所示。

表2有障碍物情况下仿真参数  
Table 2 Simulation parameters with obstacle conditions   

<html><body><table><tr><td>仿真参数名称及符号</td><td>值/(单位)</td></tr><tr><td>目标初始位置p</td><td>(5,27)/(m)</td></tr><tr><td>目标初始速度v</td><td>(0.4,-0.4)/(m/s)</td></tr><tr><td>目标初始加速度a</td><td>(0.4,-0.2)/(m/s²)</td></tr><tr><td>机器人初始速度v"</td><td>(0.0)/(m/s)</td></tr><tr><td>机器人初始加速度a"</td><td>(0,0)/(m/s²)</td></tr><tr><td>障碍物1初始位置p</td><td>(0.5,15)/(m)</td></tr><tr><td>障碍物1初始速度v</td><td>(2.5,-2)/(m/s)</td></tr><tr><td>障碍物1初始加速度a</td><td>(-0.1,0.15)/(m/s²)</td></tr><tr><td>障碍物2初始位置p</td><td>(13,21)/(m)</td></tr><tr><td>障碍物2初始速度v</td><td>(-3,-1)/(m/s)</td></tr><tr><td>障碍物2初始加速度a</td><td>(0.6,0.05)/(m/s²)</td></tr><tr><td>障碍物3初始位置p</td><td>(8.5,14)/(m)</td></tr><tr><td>障碍物3初始速度v</td><td>(1,2)/(m/s)</td></tr><tr><td>障碍物3初始加速度a</td><td>(-0.2,-0.2)/(m/s²)</td></tr><tr><td>机器人质量m</td><td>10/(Kg)</td></tr><tr><td>规划时间△</td><td>0.3/(s)</td></tr><tr><td>最大移动速度Vmax</td><td>5/(m/s)</td></tr><tr><td>引力正比例系数(kp,kvka)</td><td>(2,5,1)</td></tr><tr><td>斥力正比例系数(mp,mv,ma)</td><td>(4,4,3)</td></tr></table></body></html>

仓储机器人在引力和斥力共同作用，避开障碍物跟踪目标，具体过程如图10\~16所示。

30机器人轨迹 目标移动方向障碍物1轨迹 CX800025 障碍物2轨迹障碍物3轨迹o 目标轨迹 障碍物2移动方向20 T=2.4s机器人位置000□□□□□障碍物1移动方向 T=2.1s机器人位置1500000 障碍物3移动方向10 VYA 人移动方5 器00 2 4 6 8 10 12 14X轴

![](images/9ddc04aebe343a1a2f2e8979119028a00c8d8928abb33ed6f2259b8926364970.jpg)  
图9 $k _ { p } = 2 , k _ { \nu } = 5 , k _ { a } = 1$ 时路径规划 Fig.9Path planning at $k _ { p } = 2 , k _ { \nu } = 5 , k _ { a } = 1$   
图11 $\mathrm { T } { = } 2 . 4 \mathrm { s }$ 时仿真结果  
Fig.11Path planning at $\mathrm { T } { = } 2 . 4 \mathrm { s }$   
图12 $\mathrm { T } { = } 3 . 3 \mathrm { s }$ 时仿真结果

30目标移动方向机器人轨迹障碍物1轨迹 C08800000025 障碍物2轨迹 T=3.3s机器人位置\*0 障碍物3轨迹 障碍物2移动方向目标轨迹20 □□□□□□□□□□障碍物1移动方向 V15 00000 障碍物3移动方向8010人移动方向AA5 Y器00 2 4 6 8 10 12 14X轴

![](images/8faa7d8668c6855ef82314b7a34437987640e981d7ed890e20f913d1f3b1bf57.jpg)  
图10 $\mathrm { T } { = } 1 . 8 \mathrm { s }$ 仿真结果  
Fig.1OThe path planning at $\mathrm { T } { = } 1 . 8 \mathrm { s }$   
Fig.12Path planning at $\mathrm { T } { = } 3 . 3 \mathrm { s }$   
图13 $\mathrm { T } { = } 3 . 9 \mathrm { s }$ 仿真结果   
Fig.13Path planning at $\mathrm { T } { = } 3 . 9 \mathrm { s }$   
图14 $\mathrm { T } { = } 6 \mathrm { s }$ 仿真结果 Fig.14Path planning at $\mathrm { T } { = } 6 \mathrm { s }$

30X 机轨迹 C00000OOO25 □ 障碍物2轨迹T=3.9s机器人位置0 障碍物3轨迹 T=3.6s机器人位置20 □□□□□□  
轴15  
Y0000080000105 L00 2 4 6 8 10 12 14X轴

30 轨达 T=6s机器人位置 25 □ 障碍物2轨迹 0000000000900o0 米 障碍物3轨迹 AAA41 20 。 目标轨迹 文 □□06□□ V 轴15 10 5 F 0 0 5 10 15 X轴

![](images/6fd483e7d6ac4cceaa898d8d1c1c4e77a6774d88acd61cb24ab71ac558195976.jpg)  
图15 $\mathrm { T } { = } 6 . 6 \mathrm { s }$ 仿真结果

![](images/9640564d7bb3516c85216af5f44676132c4572dbde6a0d59392d93e8b12da735.jpg)  
Fig.15Path planning at $\mathrm { T } { = } 6 . 6 \mathrm { s }$   
图16 $\mathrm { T } { = } 1 3 \mathrm { s }$ 时仿真结果 Fig.16Path planning at $\mathrm { T } { = } 1 3 \mathrm { s }$

可见，机器人在 $\mathrm { \ t = } 1 . 8 \mathrm { s }$ 时进入障碍物1的作用范围，在$\mathrm { t } { = } 2 . 1 \mathrm { s }$ 时避开了障碍物1继续跟踪目标；机器人在 $\mathrm { t } { = } 3 . 3 \mathrm { s }$ 时进入障碍物2的作用范围，在 $\mathrm { t } { = } 3 . 9 \mathrm { s }$ 时避开了障碍物2；在$\scriptstyle { \mathrm { t } } = 6 { \mathrm { s } }$ 时机器人遇到障碍物3， $\scriptstyle { \mathfrak { t } } = 6 . 6 5$ 时机器人避开障碍物3，继续跟踪目标；在 $\mathrm { \ t } { = } 1 3 \mathrm { s }$ 时机器人与目标处于相同位置，且保持相同的速度和加速度继续运动。仿真结果验证了改进后的人工势场法能很好的解决仓储机器人在全动态环境下的路径规划问题，且跟踪效率高，路径光滑

# 4.4与其他算法比较

为了进一步验证本算法的优越性，采用文献[16]的仿真环境进行仿真实验，结果如图17(b)所示。

图17(a)为文献[16]的仿真结果，(b)为本算法的仿真结果，由图可见在 $\mathrm { \ t = } 1 0 \ \mathrm { s }$ 时已经实现与目标同步运动，且运动轨迹圆滑，所以，本算法在动态障碍物避障和动态目标追踪上更具优势。

# 5 结束语

本文首先分析了仓储机器人自主导航的工作原理，给出了机器人和障碍物的数学模型，搭建了基于2维激光雷达的环境感知平台，提出了一种改进的人工势场法，使得仓储机器人具备在全动态环境中自主导航的能力。将机器人相对于目标、障碍物的位置、速度和加速度引入到传统势场函数中，经仿真验证，仓储机器人不仅能有效避开动态障碍物，还能精确地跟踪目标机器人，为下一步应用到现实无人仓储环境中奠定了坚实基础。

![](images/79e35d4a8533d02cad2baa2ef107772712d3ba75aac255a497bc0421ccb942ee.jpg)  
  
Fig.17Result compared with other method

# 参考文献：

[1]沈博闻，于宁波，刘景泰．仓储物流机器人集群的智能调度和路径 规划[J].智能系统学报，2014，9(6):659-664.(Shen Bowen，Yu Ningbo,Liu Jingtai. Intelligent scheduling and path planning of Warehouse mobile robots [J].CAAI Transactions on Intelligent Systems, 2014,9(6):659-664.)   
[2]达兴鹏，曹其新，王雯珊．移动机器人里程计系统误差及激光雷达 安装误差在线标定[J].机器人,2017,39(2):205-213.(Da Xingpeng, Cao Qixin,Wang Wenshan.On-line calibration for odometry systematic errors and laser rangefinder installation errors of a mobile robot [J]. Robot,2017,39(2):205-213.)   
[3]朱大奇，颜明重．移动机器人路径规划技术综述[J].控制与决策， 2010,25(7): 961-967.(Zhu Daqi，Yan Mingchong.Surveyon technology of mobile robot path planning [J].Control and Decision, 2010,25(7):961-967.)   
[4]高民东，张雅妮，朱凌云．应用于机器人路径规划的双向时效 $\mathbf { A } ^ { * }$ 算 法[J/OL].计算机应用研究,2019，36(4).http://www.arocmag.com/ article/02-2019-04-018.html.(Gao Mindong,Zhang Yani,Zhu Lingyun. Bidirectional time-efficient $\mathbf { A } ^ { * }$ algorithm for robot path planning [J/OL]. Application Research of Computers,2019,36(4). http://www.arocmag. com/article/02-2019-04-018.html.)   
[5]张杰，刘耕阳，关永．一种水下群机器人路径规划算法的形式化研

究[J/OL].计算机应用研究，2019,36(3).http://www.arocmag.com/

article/O2-2019-03-063.html.(Zhang Jie,Liu Gengyang,Guan Yong. Formal research for path planning of underwater swarm robots [J/OL]. Application Research of Computers,2019,36(3). http://www.arocmag. com/article/02-2019-03-063.html.)   
[6]Khatib O.Real-time obstacle avoidance for manipulators and mobile robots [J]. International Journal of Robotics Research,1986,5(1): 90-98.   
[7]胡小平，李泽玉．一种改进的势场法路径规划算法 [J].机械科学与 技术,2017,36(1O):1-9. (Hu Xiaoping,Li Zeyu. An improved potential field method for robot path planning [J].Mechanical Science and Technology for Aerospace Engineering,2017,36(10):1-9.)   
[8]徐飞．基于改进人工势场法的机器人避障及路径规划研究[J].计算 机科学，2016,43(12):293-296.(Xu Fei.Research on robot obstacle avoidance and path planning based on improved artificial potential field method [J].Computer Science,2016,43(12):293-296.)   
[9] 鄢文浩，贺赛先，沈婷婷．基于随机运动障碍避障规则的机器人路 径规划[J]．电光与控制,2017,24(5):73-76.(Yan Wenhao,He Saixian, Shen Tingting.Path planning of robots based on rules for avoiding random moving obstacle [J].Electronics Optics & Control,2017,24(5): 73-76.)   
[10]翟红生，王佳欣．基于人工势场的机器人动态路径规划新方法[J]. 重庆邮电大学学报:自然科学版,2015,27(6):814-818.(Zhai Hongsheng,Wang Jiaxin.Dynamic path planning research for mobile robot based on artificial potential field [J]. Journal of Chongqing University of Posts and Telecommunications:Natural Science Edition, 2015,27(6): 814-818.)

[11]韩永，刘国栋．动态环境下基于人工势场的移动机器人运动规划

[J].机器人，2006,28(1):45-49.(Han Yong，Liu Guodong.Mobile robot motion planning based on potential field in dynamic environment [J].Rob0t,2006,28(1):45-49.)   
[12]Nick M,ChiangHT,KendraL,et al.Hybrid dynamic moving obstacle avoidance using a stochastic reachable set-based potential field [J]. IEEE Trans onRobotics,2017,33(5):1124-1138   
[13]李捷，袁夏，赵春霞，等．基于2维激光雷达的小型地面移动机器人 自主回收方法[J].机器人，2017,39(5):688-696.(LiJie,Yuan Xia, Zhao Chunxia,et al.Automatic withdrawal method based on 2Dlaser radar for small ground mobile robot[J].Robot,2017,39(5): 688-696.)   
[14]赖旭东，万幼川．基于平坦度的激光雷达强度图像的滤波算法[J]. 中国激光,2005,32(10):1325-1329.(Lai Xudong,Wan Youchuang.A kind of filter algorithms for lidar intensity image based on evenness terrain [J].Chinese Journal ofLasers,2005,32(10):1325-1329.)   
[15] Kim Jiwoong,Chung Woojin.Localization of a mobile robot using a laser range finder in a glass-walled environment [J].IEE Trans on Industrial Electronics,2016,63(6):3616-3627.   
[16]殷路，尹怡欣．基于动态人工势场法的路径规划仿真研究[J]．系统 仿真学报，2009,21(11):3325-3328.(Yin Lu,Yin Yixin.Simulation research on path planning based on dynamic artificial potential field [J]. Journal of system simulation,2009,21(11):3325-3328.)   
[17]朱毅，张涛，程农，等．动态环境下基于子目标的移动机器人路径规 划方法[J]．系统仿真学报,2010,22(1):254-257.(Zhu Yi,Zhang Tao, Cheng Nong,et al. Sub-goal based path planning mehod for mobile robot under dynamic environment [J]. Journal of System Simulation, 2010,22(1):254-257.)