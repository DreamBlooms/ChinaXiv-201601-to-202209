# 大型射电望远镜面形精度测量方法研究综述

汪 赞¹²，孔德庆²，陈志平1(1.杭州电子科技大学机械工程学院，浙江 杭州310018；2.中国科学院国家天文台，北京

100012)

摘要：射电望远镜是天文观测与深空探测的重要设备，当前正朝着大口径、高频段方向发展。大型射电望远镜的面形精度是影响接收性能的关键指标。为了厘清各种大型射电望远镜面形精度测量方法的特点，将大型射电望远镜面形精度测量方法分为了四类：经典测量法、激光测量法、摄影测量法和微波全息法；详细阐述了各种面形精度测量方法的原理及应用，并对比分析了各自的优劣势；最后对大型射电望远镜面形精度测量方法的发展趋势进行了论述和展望，为不断探索和创新望远镜面形精度测量方法提供了启发。

关键词：大型射电望远镜；面形精度；测量方法中图分类号：P111.4 文献标识码：A 文章编号：

# 0引言

面形精度是射电望远镜的关键指标，决定了天线效率和最短可观测波长。观测波长λ天线效率 $\eta$ 与面形精度 $\delta$ 之间存在关系 $\eta { = } \mathrm { e x p } [ { - } ( 4 \pi \delta / \lambda ) ^ { 2 } ] ^ { [ 1 ] }$ ，性能优异的射电望远镜面形精度通常须小于最短可观测波长的 $1 / 1 5 \sim 1 / 2 0 ^ { [ 2 ] }$ ，而测量精度要达到面形精度的 $1 / 3 \sim 1 / 5 ^ { [ 3 ] }$ 。可见，射电望远镜的观测波长越短、天线效率指标越高，对面形测量提出的要求就越高。

随着射电望远镜口径不断增大、工作频段不断提高，面形测量方法也在不断发展以满足日新月异的射电天文与深空探测需求。英国的Lovell $7 6 \mathrm { m } ^ { [ 4 ] }$ 、澳大利亚的Parkes $6 4 ~ \mathrm { m } ^ { [ 5 ] }$ 、德国的Effelsberg $\boldsymbol { 1 0 0 } \mathrm { m } ^ { [ 6 ] }$ 以及西班牙和法国共建的 MRT $3 0 ~ \mathrm { m } ^ { [ 2 ] }$ 等射电望远镜的面形测量最初均采用经纬仪带尺法或其改进方法；日本的Nobeyama $4 5 \mathrm { m } ^ { [ 7 ] }$ 毫米波射电望远镜的面形测量开始使用先进的全站仪；美国的GBT $1 0 0 \mathrm { m } ^ { \left[ 8 \right] }$ 、Arecibo $3 0 5 \mathrm { m } ^ { [ 9 - 1 0 ] }$ 以及中国的Miyun $5 0 \mathrm { m } ^ { [ 1 1 ] }$ 、Tianma $6 5 \mathrm { m } ^ { [ 1 2 ] }$ 、FAST $5 0 0 \mathrm { m } ^ { [ 1 3 ] }$ 等射电望远镜的面形测量与调整逐渐采用更为先进的激光测量、摄影测量或微波全息等技术。

综观面形测量方法的发展历程，可将口径不小于 $2 5 \mathrm { ~ m ~ }$ 的大型射电望远镜的面形测量方法分为四类：经典测量法、激光测量法、摄影测量法和微波全息法。本文通过对这四类方法的原理及应用进行总结与分析，以期为不断探索和创新望远镜面形测量方法提供一些启发。

# 1大型射电望远镜面形测量方法研究现状

# 1.1 经典测量法

经典测量法主要包括经纬仪带尺法、经纬仪系统测量法、全站仪测量法、距离交会测量

法等等。经典测量法是国内外大型射电望远镜的反射面在初装时通常所采用的方法。

# 1.1.1经纬仪带尺法

其测量原理如图1，利用金属带标尺在反射面上钻孔并放置靶标，然后用放置在反射面顶点上的经纬仪测量各个靶标的角度，据此来计算靶标对应点的空间坐标同理想抛物面的偏差[14]。经逐点测量，归算后就可得到反射面面形的均方根差。对于大型射电望远镜，需测靶标有数百甚至上千，一次完整测量通常历时长达 $8 \sim 1 0 \mathrm { h }$ ，测量工作十分艰辛。

![](images/cefcabf04e67af948bc819643c59685c31ffe5079d7e22068080df8483589753.jpg)  
图1经纬仪带尺法

国际射电天文研究所的MRT $3 0 \mathrm { m }$ 的反射面单块面板制造精度达 $0 . 0 3 \ : \mathrm { m m } ^ { [ 1 5 ] }$ ，用改进的经纬仪带尺法对反射面面形精度进行了测量，结果为 $0 . 1 2 \mathrm { m m } ^ { [ 1 6 ] }$ 。20 世纪70年代初，德国建成了当时世界上口径最大的可跟踪射电望远镜Effelsberg $1 0 0 \mathrm { ~ m ~ }$ ，其反射面面形测量最初也是采用的经纬仪带尺法， $\Phi 8 0 \mathrm { m }$ 内测得的面形精度优于 $1 \mathrm { m m } ^ { [ 1 7 ] }$ 。

# 1.1.2经纬仪系统测量法

经纬仪系统测量法基于多台高精度电子经纬仪，结合各种附件与软件系统，根据空间前方交会原理解算空间点坐标。图2为某大型天线面形测量系统布设。该天线面积约 $6 0 0 \mathrm { m } ^ { 2 }$ 均分为2个区，四台T3000A经纬仪施测。测量前先标定四台经纬仪的空间相对位置及姿态，系统定向完成后，1和2组合测1区，3和4组合测2区。根据测得的 $a _ { i }$ 、 $\beta _ { i }$ ，经数据处理可分别获得点 $\scriptstyle P _ { 1 }$ 与 $P _ { 2 }$ 的三维坐标。经该法调整后的反射面，其面形精度可优于 $0 . 5 \mathrm { m m } ^ { [ 1 8 ] }$ 。

![](images/19d2226376f771702c7f9a1956c928ecef36c8c4dccb4707a2aa76944253c90b.jpg)  
Fig.1Sketch of Theodolite Tape Method   
图2经纬仪测量系统布设[18]

中国电科54所在研制我国第一个多波束天线时，构建了由T3000A和T2000S 电子经纬仪、基准尺、数据传输电缆以及便携式计算机等组成的经纬仪测量系统，将天线面形精度控制在 $0 . 6 7 \mathrm { m m }$ 左右[19]。信息工程大学开发了经纬仪系统测量软件MetroIn，并基于该软件对大尺寸天线罩安装过程中的测量数据进行实时处理与分析来指导现场安装[20]。文献[21]采用该法对 $\varPhi 2 5 \mathrm { m }$ 天线反射面进行了重力变形测量，得到表面RMS 为 $0 . 5 \mathrm { m m }$ 。

# 1.1.3全站仪测量法

全站仪测量法在大型天线变形测量中应用广泛，相较于经纬仪系统测量法，它仅用一台全站仪即可实现所有的一般测量功能，成本较低。此外，它还具有构建系统快、测量时间短、操作简单等优点。其测量原理如图3所示，通过测量水平角 $\scriptstyle a$ 、垂直角 $\beta$ 和斜距 $s$ 来计算天线抛物面上待测点 $P$ 的三维坐标（ $\scriptstyle  \displaystyle  ( = s \cos \beta  $ sina, $\scriptstyle y = s \cos \beta$ cosa, $\scriptstyle z = s \sin \beta$ ）

![](images/fc2e948e73d48bc0b38621617967f0bb7cf44d06d1501b51acdb9d50c0853ad3.jpg)  
Fig.2Sketch of Theodolite Measurement System   
图3全站仪测量法原理  
Fig.3Sketch of Total Station Measurement Method

日本的 $4 5 \mathrm { ~ m ~ }$ Nobeyama毫米波射电望远镜在安装调整的过程中，通过全站仪可将天线面形精度控制在 $0 . 2 \ \mathrm { m m }$ 左右[7]。美国于20 世纪60年代建成的当时世界上口径最大的固定式射电望远镜 Arecibo 首次安装测量也是采用的全站仪，控制网的绝对精度达 $1 \ \mathrm { m m } ^ { [ 3 ] }$ 。21世纪初，美国国家射电天文台又在格林班克建成了 $1 0 0 \mathrm { ~ m ~ }$ 口径的可跟踪射电望远镜GBT，初装时用全站仪结合经纬仪进行测量，得到天线面形精度约 $1 . 1 \mathrm { m m } ^ { [ 8 ] }$ 。

# 1.1.4距离交会测量法

经纬仪系统、全站仪均是基于角度交会测量，而距离交会测量法是基于距离交会测量。因为角度误差对最终结果的影响随着测量距离的增大而增大，而距离误差则不然，故距离交会测量法的精度一般略高。该法原理如图4，抛物面上待测点不在测距点1、2、3所构成的平面上。以点1为坐标原点；1、2连线为 $x$ 轴；经过点1，由点1、2、3所构成的平面的法线为 $z$ 轴。首先进行系统标定，然后列出观测方程，测量 $n$ （ $( n > 6 )$ 个点共有 $4 n$ 个观测方程，而未知数为 $3 n { + } 6$ ，最后可按最小二乘法进行求解。

![](images/17a21b8192fd3f7cb5c40bc312854ef62245695db1e5948cb407d19fcd6cf541.jpg)  
图4GBT距离交会测量系统[22]  
Fig.4 GBT's Reflector Surface Measurement System

美国国家射电天文台曾用三台测距仪对GBT的主动反射面进行了距离交会测量，面形测量结果的绝对精度优于 $1 \ \mathrm { m m } ^ { [ 3 ] }$ ；而后为了掌握天线俯仰转动时的变形情况，工程人员又在天线基础地面上安装了12台特制的测距仪，如图4所示，使测距精度达到了 $0 . 0 5 \mathrm { \ m m }$ 并将面形精度控制在了 $0 . 3 \mathrm { m m }$ 以内[23]。

# 1.2激光测量法

经典测量法施测费时费力，且测量结果好坏与测量人员的操作水平及其工作时的情绪状态有很大关系。激光测量法以及后面的摄影测量法、微波全息法均无需人眼瞄准，基本消除了面形测量中人的因素对测量效果的影响，且在测量速度上较经典测量法有了很大提高。

# 1.2.1激光跟踪测量法

激光跟踪仪的测量原理和全站仪一样，但在测距方式、跟踪方式及结构设计等方面有所不同。激光跟踪测量系统由激光跟踪仪和便携式计算机两大部分组成。一台激光跟踪仪包含五大部件：角度测量部件、距离测量部件、跟踪控制部件、控制部件和支撑部件。激光跟踪测量系统的测量精度高、速度快，且不易受人为因素影响。

中国科学技术大学采用美国自动精密工程公司的LTS-3000 激光跟踪仪测量系统对某天线进行测量，在测量范围内，其重复测量精度可达 $5 \ \mu \mathrm { m / m }$ ；采用绝对坐标测量时，其重复测量精度在 $1 0 \ \mu \mathrm { m / m }$ 左右[24]。信息工程大学对徕卡激光跟踪仪的底层控制软件 EmScon 进行二次开发，解决了目标测量点自动快速精确定位问题，并通过模拟实验验证了其精度和测量效率[25]。20 世纪70年代，美国的 $3 0 5 \mathrm { ~ m ~ }$ Arecibo 望远镜的面形测量曾尝试采用激光跟踪测量法，但由于当时技术条件的限制，测量单个靶标位置坐标及其误差所需时间约 $6 0 ~ \mathrm { s }$ ，测得的靶标位置精度从 $0 . 8 \mathrm { m m }$ 到 $2 . 7 \mathrm { m m }$ 不等[9]。

# 1.2.2激光扫描测量法

激光扫描测量法的本质也是测距，按测距原理的不同，可分为非相干式和相干式。前者基于测量激光的飞行时间，后者基于测量激光的相位差。由于光速极快，非相干式测距在中小距离情况下的测距分辨率较低，而相干式测距的测量精度则较高。激光扫描测量法与激光跟踪测量法的不同在于前者不需要靶标作为合作目标，属于非接触式测量。

目前国外已开发了Focus S350、IMAGER5010C、RIEGLVZ400 等多款激光扫描测量产品。文献[26]用RIEGLVZ400 测量某桥梁挠度变化，当被扫桥底最远处与仪器相距在 $4 0 0 \mathrm { m }$ 以内时，测量精度可达 $1 \mathrm { c m }$ 。文献[27]研究了如何将三维激光扫描技术应用到古建筑变形监测与分析。文献[28]就三维激光扫描仪技术的现状和发展、扫描仪原理、误差来源以及点云数据的配准进行了研究，提出利用同名点进行点云数据的配准并进行间接平差，可以获得满足精度的配准坐标。文献[29]尝试利用RieglVZ400对Tianma $6 5 \mathrm { ~ m ~ }$ 射电望远镜的反射面背架进行测量，在 $3 0 \mathrm { m }$ 范围内的测量效果较好。尽管运用激光扫描仪测量大型天线面形的实践目前较少，但从已开发的激光扫描测量产品的性能（如表1）来看，其在天线测量方面极具应用潜质。

表1激光扫描测量产品  
Table1 Laser Scanning Products   

<html><body><table><tr><td>生产厂家</td><td>产品型号</td><td>扫描距离</td><td>测距测角精度</td><td>特点</td></tr><tr><td rowspan="3">FARO</td><td rowspan="3">Focus S350</td><td>Min:0.6 m</td><td>1mm</td><td>视场范围：360x300°</td></tr><tr><td></td><td>水平：19"</td><td>扫描速率：97.6万/秒</td></tr><tr><td>Max:350 m</td><td>垂直：19"</td><td>工作温度：+5℃至+40℃</td></tr><tr><td rowspan="3">Z+F</td><td rowspan="3">IMAGER 5010C</td><td>Min:0.3 m</td><td>0.1 mm</td><td>视场范围：360x320°</td></tr><tr><td>Max:187 m</td><td>水平：1.44"</td><td>扫描速率：101.6万点/秒</td></tr><tr><td></td><td>垂直：0.72"</td><td>工作温度：-10℃至+45℃</td></tr><tr><td rowspan="3">Leica</td><td rowspan="3">ScanStation P50</td><td>Min:0.4 m</td><td>3mm</td><td>视场范围：360x290</td></tr><tr><td></td><td>水平：8"</td><td>扫描速率：100万点/秒</td></tr><tr><td>Max:>1km</td><td>垂直：8"</td><td>工作温度：-20℃至+50℃</td></tr><tr><td rowspan="3">Riegl</td><td rowspan="3">VZ-6000</td><td></td><td>15 mm</td><td>视场范围：360x60</td></tr><tr><td>Min:5m</td><td>水平：1.8"</td><td>扫描速率：30万点/秒</td></tr><tr><td>Max:6km</td><td>垂直：1.8"</td><td>工作温度：0°至+40</td></tr></table></body></html>

# 1.3摄影测量法

摄影测量法是大型建筑物或设备变形测量的通用方法。用摄影测量法对大型射电望远镜反射面进行测量时，首先，需要使用一台或两台工业相机在不同位置进行拍摄，得到天线反射面的两张或多张图像，这些图像称为立体像对[30]；然后，用图像处理技术获取图像中天线反射面的像平面信息；最后，利用像平面信息，通过直接线性变换法、空间后方交会-前方交会方法、相对定向-绝对定向方法和光束法平差等坐标变换方法，确定图像中各点对应在物方空间坐标系中的绝对位置，以恢复天线反射面的三维信息。图5为基于近景摄影测量的天线反射面变形检测中的空间坐标转换关系，即摄影获得的天线反射面图像（图中最大矩形框）与天线反射面实际变形表面（图中曲线部分）之间的相互关系。

美国首先将摄影测量技术应用于天线测量。在Arecibo望远镜的升级测量过程中，用摄影测量法共进行了三次测量，首次测量效果并不理想，得到的天线面形精度为 $1 5 \mathrm { m m }$ ，较预估值 $3 . 2 \mathrm { m m }$ 有很大差距[31]。后采用CRC1工业相机进行摄像，最终坐标测量面形精度能够达到 $0 . 2 5 \ : \mathrm { m m } ^ { [ 3 2 ] }$ 。国内，王勇等人用摄影测量法对毫米波以及亚毫米波天线面形进行测量，根据测量结果调整后的天线面形精度分别达到了 $0 . 0 8 3 \mathrm { m m }$ 和 $0 . 0 0 5 5 \mathrm { m m } ^ { [ 3 3 ] }$ 。马开锋研究了

![](images/96cde56f784b9c1cb5ebfaafde3076bb6af537bf68987f6e1a8af157f4dfe634.jpg)  
图5天线反射面变形摄影测量中各空间坐标系关系

4 高低温环境下天线形面变形的近景摄影测量与数据处理技术[34]。李宗春等人提出用仿真数  
5 据验证摄影测量精度的整体思路，以摄影距离、摄站环数、摄站间隔和所加像点误差四个参  
6 数为输入量，以点位误差为输出量，寻求Tianma $6 5 \mathrm { m }$ 天线摄影测量的最优布设方案[35]。文  
7 献[11]采用摄影测量法对密云 $5 0 \mathrm { ~ m ~ }$ 天线在俯仰角分别为 $7 ^ { \circ }$ 和 $3 0 ^ { \circ }$ 时的反射面面形进行了  
8 测量和调整，调整后的面形精度均在 $2 \mathrm { m m }$ 以内。

# 1.4微波全息法

10 微波全息法属于系统性测量，可消除天线系统其他方面误差，量程大，精度高，测速较  
11 快，自动化程度高。该法测量天线面形精度的原理如图6，对于理想抛物面，在焦点上的发  
12 射源发出的信号，经抛物面反射到达口径平面，其经历的光程相等 $( F P 1 + P 1 T 1 = F P 2 + P 2 T 2 )$ 。  
13 然而，实际天线反射面并不是理想的抛物面，其理想表面上各点的切线与实际变形表面上对  
14 应点的切线间存在一个小的法向误差 $\varepsilon$ 。只要测出发射源发出的信号到达口径面上各个点时  
15 的相位或相位差，就可以通过运算解求天线面与理想抛物面之间的微小差别。

![](images/16eb251daa4993ea2a159f0c5a5f1c839bf94aca00f5d03041f6bd0480c3ae74.jpg)  
Fig.5Sketch of Antenna Reflector Surface Measurement Using Photogrammetry   
图6微波全息法的几何原理  
Fig.6Sketch of Microwave Holography

22

研究表明可用间接方式测量口径面上的相位值，其所依据的物理事实是抛物面天线的口径场和远场存在二维傅里叶变换关系[36]。知道复数平面内天线远场的幅度和相位，就可理论推导出口径场的幅度和相位；反之，亦然。远场辐射 $T$ 与微小表面形变 $\varepsilon$ 的数学关系[13]:

$$
\varepsilon ( x , y ) = \frac { \lambda } { 4 \pi } \sqrt { 1 + \frac { x ^ { 2 } + y ^ { 2 } } { 4 { F } ^ { 2 } } } P h a s e \left\{ { e ^ { j 2 k F } F ^ { - 1 } \left[ T ( u , \nu ) \right] } \right\}
$$

其中， $\boldsymbol { F } ^ { 1 } [ \cdots ]$ 指二维逆傅里叶变换。

微波全息法的理论测量精度可以通过互相关后的信噪比来评估[13]:

$$
\varepsilon _ { \alpha } = \frac { N \lambda } { 2 \pi S N R ( O ) }
$$

（式2）

1其中， $N$ 为天线网格扫描的点数的平方根； $S N R ( O )$ 为被测天线和参考天线同时指向信号时的互相关输出信噪比。

获取相位差的方法有相位相关法和相位恢复法，前者所需数据为远场幅值和相位分布，测量时参考天线需始终对准信号源；后者所需数据仅为远场幅值，无参考天线，口径场的相位分布根据远场幅度特性通过辐射模型迭代出来。面形测量结果好坏受相位恢复算法的影响，较为常用的相位恢复算法是Misell算法[37]。该算法在MRT $3 0 \mathrm { m }$ 反射面面形测量中表现优异，测量结果精度达到 $0 . 0 2 \mathrm { m m } ^ { [ 3 8 ] }$ 。仿真分析表明，Misell算法恢复的面形精度也基本能满足我国新疆奇台在建的 $1 1 0 \mathrm { m }$ 口径射电望远镜的面形测量需要[39]。

微波全息法在20世纪60年代被提出，但直至1977年才由 Scott等人将其应用于天线面形测量，当时对 $5 \mathrm { k m }$ 射电天文干涉阵列天线进行测量，面形精度达到了 $0 . 1 \mathrm { m m } ^ { [ 4 0 ] }$ 。Nishibori等人用该法对UDSC $6 4 \mathrm { m }$ 口径的射电望远镜反射面进行了测量与调整，获得了 $0 . 5 4 \mathrm { m m }$ 的面形精度[41]。国内，王锦清等人用相位相关全息法对余山 $2 5 \mathrm { m }$ 口径的射电望远镜主反射面进行了测量，调整面板后的面形精度达到 $0 . 5 2 ~ \mathrm { m m } ^ { [ 4 2 ] }$ ；而后又用该法对天马 $6 5 \mathrm { ~ m ~ }$ 射电望远镜的主动面进行测量与调整，将面形RMS 从 $0 . 5 8 \mathrm { m m }$ 提升至 $0 . 2 8 \mathrm { m m } ^ { [ 1 1 ] }$ 。

# 2大型天线面形测量方法优劣对比与发展趋势分析

# 2.1不同面形测量方法优缺点的比较

总结四类面形测量方法的可测范围、精度、测速与其他特点见表2。经典测量法在反射面初装时较为可用，但在后期面板调整和维护时若继续采用此类方法则存在明显不足。激光测量、摄影测量与微波全息技术部分或完全克服了经典测量法的测量范围小、精度低、测速慢、需靶标等缺点；其中，激光扫描法因测速最快、可实现全俯仰角度的测量，微波全息法因属于系统性测量（可修正副面的精度）且量程最大，均有着光明的应用前景。

表2大型天线面形测量方法对比  
Table 2The Four Kinds of Reflector Surface Measurement Methods of Large Antenna   

<html><body><table><tr><td colspan="2">测量方法</td><td>量程/m</td><td>精度/mm</td><td>测速</td><td>特点</td></tr><tr><td rowspan="4">经典 测量法</td><td>经纬仪带尺法</td><td><30</td><td>0.1~0.3</td><td>很慢</td><td>需靶标；一般只能在天线正对天顶</td></tr><tr><td>经纬仪系统测量法</td><td><50</td><td>0.02~0.5</td><td>慢</td><td>需靶标；任意仰角</td></tr><tr><td>全站仪测量法</td><td><200</td><td>0.2~1.0</td><td>慢</td><td>需靶标；任意仰角； 设备简单易操作</td></tr><tr><td>距离交会测量法</td><td><500</td><td>0.05～1.0</td><td>慢</td><td>需靶标；任意仰角</td></tr><tr><td rowspan="2">激光 测量法</td><td>激光跟踪测量法</td><td><70</td><td>5～10×10D</td><td>较慢</td><td>需靶标；任意仰角</td></tr><tr><td>激光扫描测量法</td><td><500</td><td>8～10x10D</td><td>快</td><td>无需靶标；任意仰角；昂贵</td></tr><tr><td></td><td>摄影测量法</td><td><300</td><td>10～12x10 D</td><td>较快</td><td>需靶标；任意仰角; 对光线有要求</td></tr><tr><td></td><td>微波全息法</td><td>任意口径</td><td>0.05~0.5</td><td>较快</td><td>无需靶标；任意仰角； 系统性测量；不能用于初装</td></tr></table></body></html>

# 2.2发展趋势分析

激光扫描、摄影测量和微波全息法是大型天线面形测量方法的主要发展方向，但同时这些法也存在一些问题需要解决：激光扫描法在大型天线面形测量中的可行性尚需实验验证;摄影测量法的摄距通常在 $1 0 0 \mathrm { m }$ 以内，因此大口径天线的人工拍摄工作及后续的相片拼接处理复杂，同时为获得足够高的精度需设置尽可能多的靶标，增加了测量准备期的工作量；微波全息法通常采用同步卫星作为投射信号源，因此天线俯仰角度会受到限制，同时其分辨率还受到信号源强度和参考天线口径大小的影响；此外，这些方法均会到光线、风、温度、沙尘等环境因素的影响。未来面形测量方法必将朝着实时或准实时、高精度、自动化且不易受环境影响的方向发展。摄影测量法可借助无人机携带工业相机的方式消除拍摄工作的困难；微波全息法可利用特定射电源的宽带信号实现全俯仰测量，弥补利用同步卫星窄带信号测量时的不足；激光测量法通过与微波全息法结合，可综合两种方法的优点，进一步提高天线面形测量精度。

# Surface Measuring Methods of Large Antenna: A Review

Wang Zan[1,2], Kong Deqing[2],Chen Zhiping[1] (1. Hangzhou Dianzi University, Hangzhou 31Oo18, China; 2. National Astronomical Observatories, Chinese Academy of Sciences, Beijing 1Oo012, China)

Abstract: Radio telescope is an important equipment for astronomical observation and deep space exploration. Nowadays,as the caliber becomes larger and the observing frequency is getting higher, it is crucial to improve reflector surface accuracy to ensure the receiving performance. In this paper, in order to clarify the characteristics of different reflector surface measuring methods of large antenna,the reflector surface measuring methods of large radio telescope are divided into four groups: classical way, laser way, photogrammetric way and microwave holography way. First, principles and applications of different surface measuring methods are illustrated. Then, the advantages and disadvantages of each method are compared and analyzed. Finally， the development trend of reflector surface measuring methods of large radio telescope is discussed. This paper should provide some inspiration for the exploration and innovation of surface measuring methods of large antenna.

Key words: Large radio telescope; reflector surface accuracy; measuring method

# 参考文献

[1] Ruze J. Antenna tolerance theory-a review[J]. Proceedings of the IEEE,1966,54(4):633-640.   
[2] Greve A. Reflector surface measurements of the IRAM $3 0 \mathrm { m }$ radio telescope[J]. International Journal of Infrared and Millimeter Waves,1986,7(1):121-135.   
[3] 李宗春，李广云．天线几何量测量理论及其应用[M].测绘出版社,2009.   
[4]Morison I. 50 years of the Lovel telescope[J]. Astronomy & Geophysics, 2007, 48(5):23-25.   
[5]Minnett H. The construction of the Parkes 21O-ft radio telescope[J]. International Journal on Media Management,1994,7(1):16-23.   
[6]Wielebinski R, Junkes N, Grahl B H. The Effelsberg $1 0 0 \mathrm { m }$ radio telescope: construction and forty years of radio astronomy[J]. Journal of Astronomical History and Heritage,2011, 14(1):3-21.   
[7]Morimoto M. Results from Nobeyama Radio Observatory (NRO)—a progress report[J]. Astrophysics and Space Science, 1986,118(2):63-65.   
[8]Hall R,Goldman M A,Parker D H,et al. Measurement program for the Green Bank Telescope[J]. Proceedings of SPIE - The International Society for Optical Engineering,1998, 335(7):265-276.   
[9]Lalonde L M. The upgraded Arecibo Observatory[J]. Science,1974,186(4160):213-218.   
[10] Goldsmith PF. The second Arecibo upgrade[J]. IEEE Potentials,1996,15(3):38-43.

1 [11] 许文学．大型天线测量方法研究及应用[D]．解放军信息工程大学,2006.   
2 [12] 王锦清，左秀婷,Kesteven M，等. $\mathrm { T M } 6 5 \mathrm { m }$ 射电望远镜面形微波全息测量[J]．中国科学:   
3 物理学 力学 天文学,2017,47(09):92-102.   
4 Wang J, Zuo X, Kesteven M, et al. TM $6 5 \mathrm { m }$ radio telescope microwave holography[J].   
5 Scientia Sinica: Physica, Mechanica and Astronomica, 2O17, 47(O9):92-102.   
6 [13] 周荣伟，朱丽春，胡金文，等．FAST 单元面板面型检测算法研究[J]．天文研究与技术,   
7 2012, 9(01):14-20.   
8 Zhou R, Zhu L, Hu J,at al. Study of a measurement algorithm for the surface of a single   
9 panel of the reflector of the FAST[J]. Astronomical Research and Technology，2012,   
10 9(01):14-20.   
11 [14] Imbriale WA．深空网大天线技术[M]．清华大学出版社,2006.   
12 [15] Greve A, Morris D,Johansson L E B,et al. Precision of radio reflector surfaces adjusted from   
13 theodolite-tape measurements[J]. Microwaves Antennas and Propagation IEE Proceedings,   
14 1994, 141(1):23-29.   
15 [16] Baars JW M, Greve A, Hein H, et al. Design parameters and measured performance of the   
16 IRAM 30m millimeter radio telescope[J]. Proceedings of the IEEE,1994, 82(5):687-696.   
17 [17] Godwin M P, Schoessow E P, Grahl B H. Improvement of the Effelsberg $1 0 0 \mathrm { m }$ telescope   
18 based on holographic reflector surface measurement[J]. Astronomy and Astrophysics,1986,   
19 167(2):390-394.   
20 [18]李宗春,李广云，汤廷松，等．电子经纬仪交会测量系统在大型天线精密安装测量中的   
21 应用[J]．海洋测绘,2005,25(1):26-30.   
22 Li Z,Li G, Tang T, et al. Electronic multi-theodolite measuring system applied in the   
23 precision installation of a large antenna[J]. Hydrographic Surveying and Charting, 2005,   
24 25(1):26-30.   
25 [19]金超，芦志辉，李广云，等．工业测量系统在多波束天线安装检测中的应用[J]．解放军   
26 测绘学院学报,1998,15(3):17-21.   
27 Jin C,Lu Z, Li G, et al. Application of electronic theodolite industrial measuring system in   
28 the large multi-wave antenna adjustment[J]. Journal of Geomatics Science and Technology,   
29 1998, 15(3):17-21.   
30 [20] 王瑞鹏，李东敏，李广云，等．MetroIn 在大尺寸天线罩安装测量中的应用[J]．测绘工程,   
31 2014, 23(11):43-45.   
32 Wang R, Li D, Li G, et al. Application of MetroIn system to the measurement of large-scale   
33 radome installation[J]. Engineering of Surveying and Mapping, 2014, 23(11):43-45.   
34 [21]徐忠阳．小型非接触式测量系统及其在天线自重变形测量中的应用[D]．解放军测绘学   
35 院,1990.   
36 [22] Prestage R M, Constantikes K T, Balser D S,et al. The GBT precision telescope control   
37 system[J]. Ground-Based Telescopes, 2004, 548(9):1029-1040.   
38 [23] Payne J. Pointing and surface control of GBT[J]. GBT Memos,1990, 36(1):1-6.   
39 [24]胡静．基于激光跟踪仪的大型天线面形测量辅助系统设计[D]．中国科学技术大学,   
40 2013.   
41 [25]王罗刚，王同合，范百兴，等．一种大型天线自动化变形测量新方法[J]．测绘科学,2017,   
42 42(02):130-134.   
43 Wang L, Wang T, Fan B, et al. A new automatic deformation measurement method of large   
44 antenna[J]. Science of Surveying and Mapping, 2017, 42(02):130-134.   
2 与地球动力学,2017,37(6):609-613.   
3 Xu J,Guo X,Liao H,et al. The test on bridge deflection deformation monitoring by   
4 terrestrial laser scanning[J]. Journal of Geodesy and Geodynamics,2O17, 37(6):609-613.   
5 [27]田鹏艳．基于三维激光扫描技术的变形测量关键技术研究[D]．山东理工大学,2018.   
6 [28]朱文武．基于标靶控制的三维激光扫描点云数据配准研究[D]．中国地质大学(北京),   
7 2012.   
8 [29]李干．大型天线安装测量与面型数据处理若干问题研究[D]．解放军信息工程大学,   
9 2012.   
10 [30] 冯文灏．近景摄影测量[M]．武汉大学出版社,2002.   
11 [31] Edmundson K, Baker L. Photogrammetric measurement of the Arecibo primary reflector   
12 surface[C]. Albuquerque,NM: 17th Annual Coordinate Measurement Systems Committee   
13 Conference, 2001.   
14 [32] Goldsmith P. Resetting the Arecibo primary reflector surface[J]. The Arecibo Observatory   
15 Newsletter, 2001, 3(2):1-4.   
16 [33]王勇，黄桂平，杨天克，等．毫米波天线形面精度摄影测量技术及实践[J]．微波学报,   
17 2017, 33(S1):317-319.   
18 Wang Y, Huang G, Yang T, et al. High precision photography measurement technology and   
19 practice in millimeter wave / submillimeter wave[J]. Journal of Microwaves,2017,   
20 33(S1):317-319.   
21 [34]马开锋．高低温环境卫星天线形面变形的近景摄影测量与数据处理[D].中国矿业大学   
22 (北京),2016.   
23 [35]李宗春，李广云，冯其强,等．上海天文台 $\phi 6 5 \mathrm { ~ m ~ }$ 射电望远镜精密安装测量[J].测绘通   
24 报,2012(S1):126-130.   
25 Li Z,Li G, Feng Q,et al. Precision installation of the $6 5 \mathrm { m }$ radio telescope of Shanghai   
26 Observatory[J]. Bulltin of Surveying and Mapping, 2012(S1):126-130.   
27 [36] Rahmat S Y. Surface diagnosis of large reflector antennas using microwave holographic   
28 metrology: an iterative approach[J]. Radio Science,1984,19(05):1205-1217.   
29 [37] Misell L D.A method for the solution of the phase problem in electron microscopy[J].   
30 Journal of Physics D: Applied Physics, 1973, 6(1):6-9.   
31 [38] Morris D, Bremer M, Butin G, et al. Surface adjustment of the IRAM 30 m radio telescope[J].   
32 IET Microwaves Antennas & Propagation, 2009, 3(1):99-108.   
33 [39]王志桥．相位恢复全息法天线面形测量技术研究[D]．新疆大学,2017.   
34 [40] Scott F, Ryle M. A rapid method for measuring the figure of a radio telescope reflector[J].   
35 Monthly Notices of the Royal Astronomical Society, 1977, 178(4):539-545.   
36 [41] Nishibori T, Hirabayashi H, Kobayashi H, et al. Surface error measurements of large reflector   
37 antennas by phase retrieval holography—an application of extrapolation algorithm[J].   
38 Electronics and Communications in Japan, 2010,79(4):104-114.   
39 [42]王锦清，余宏．全息法测量天线面表面精度[J]．中国科学院上海天文台年刊,   
40 2007(28):109-118.   
41 Wang J,Yu H. The measurement of the precision of antenna's surface with holograph[J].   
42 Annalsof Shanghai Astronomical Observatory， ChineseAcademy of Sciences,   
43 2007(28):109-118.