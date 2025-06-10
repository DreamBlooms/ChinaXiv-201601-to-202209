# 二次栅格扫描与锚节点递减栅格扫描的定位算法

宋海声1，周浩，沈 伟¹，朱长驹²，吴佳欣(1．西北师范大学 物理与电子工程学院，兰州 730070;2.南京航空航天大学 电子信息工程学院，南京 211106;3东南大学 微电子学院，南京 210096)

摘要：为了提高无线传感器网络的定位精度，在Grid-Scan 算法的基础上作进一步的改进。首先利用二次栅格扫描确定初始定位点，并产生缩小的定位区域；在该缩小区域内，将邻居锚节点与初始定位点间的距离转换为理论信号强度值，再对比邻居锚节点实际接收未知节点的信号强度，对邻居锚节点进行有条件递减，得到递减锚节点栅格扫描法则，最终确定未知节点的估计位置。通过仿真实验的对比，改良后的定位算法在一定程度上提高了定位精度。

关键词：无线传感器网络；Grid-Scan算法；二次栅格扫描；信号强度；递减 中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2018.09.0748

Two grid scan and anchor node descending raster scan location algorithm

Song Haishengl, Zhou Hao], Shen Weil, Zhu Changju²,Wu Jiaxin³ (1.Collegeofhysics&ElectronicEngineering,NorthwestNormal UniversityLanzhou73070,China;2.Collegeof Electronic InformationEngineering,NanjingUniversityfAeronautics&Astronautics,Nanjing21o6,China;3.chool ofIntegrated Circuits,Southeast University,Nanjing 210096,China)

Abstract: Inorder to improve the positioning acuracyof wireless sensor networks,so make further improvements on the basisof Grid-Scanalgorithm.Firstly,thesecondrasterscandetermines the initial locationpointand generates thereduced locationarea.Inthereducedarea,byconvertingthe distance betweentheneighboringanchornodeandthe initial location pointto the theoreticalsignal strengthvalueand comparingthe signal strengthofthe neighboringanchor with thatof the unknown node,and the neighboring anchor node is conditional.Reducing the grid scanruleof the descending anchor node and determining the position estimationofthe unknown node.The simulationresults show thatthe localization algorithm improves the positioning accuracy to a certain extent.

Key words: wireless sensor networks; Grid-Scan algorithm; second raster scan; signal strength; descending

# 0 引言

无线传感器网络(wireless sensornetwork，WSN)的许多应用和协议都基于节点位置信息，因此，节点定位技术是WSN的核心支撑技术之一[I]。定位指根据网络中部分位置已知的节点(锚节点)来确定其余节点(未知节点)的位置[2]。根据在定位过程中是否需要测量节点之间的实际距离，当前的定位算法可分为基于测距的定位算法和无须测距的定位算法[3]

基于测距的定位算法通过未知节点与邻近信标节点间的通信具体计算两者之间的距离或者方位，并基于此实现节点自身定位[4]。经典算法有基于接收信号强度(receivedsignalstrengthindication，RSSI）测距定位、基于信号传播时间(timeofarrival，TOA）测距定位、基于信号到达时间差(timedifferenceofarrival，TDOA)测距定位等[5,6]。该类算法对于未知节点与邻近信标节点间的距离或者角度进行精确的计算，往往具有较高的定位精度，但定位过程中对于节点能量消耗较大，对网络的硬件设备要求较高，大幅增加了网络的计算量和通信成本[7,8]。针对基于测距的定位算法的不足，许多无须测距的定位算法相继被提出，较为典型的无须测距算法有近似三角形内点测试法（approximatepoint-in-triangulation，APIT）、质心算法和DV-Hop 算法等[9,10]。测距无关的定位算法利用节点之间的邻近关系和连通性实现定位，成本低且定位精度可以满足大多数应用，性价比较高，因此，被广泛采用。其中，Grid-Scan算法是在APIT算法中提出的一种典型的无须测距的定位算法，将目标点所在区域划分为若干正方形网格，从中选择最合适的网格求其质心点作为未知节点的估计位置。国内外学者也对无须测距的定位算法做了大量改进工作[II]。文献[12]利用未知节点与两跳范围内的锚节点的连通性约束信息，引入远节点对网格二次扫描，有效提高了定位精度。本文通过二次栅格扫描法优化了初始估计位置，对实际信号接收强度和理论信号强度进行对比，得到锚节点递减法则，并利用锚节点递减扫描法缩减了定位区域，在一定程度上减少了定位误差。

# 1 Grid-Scan 算法描述

Grid-Scan算法是在APIT算法中提出的一种典型的无须测距的定位算法[13]。Grid-Scan 算法分为三个步骤[14];

a)网络部署，待定位的未知节点搜索其通信范围内所有锚节点，并记录被搜索到的锚节点的ID和坐标信息，这些被搜索到的锚节点称为邻居锚节点。

b)将未知节点O所有邻居锚节点的通信圆交集以其外接矩形代替，得到外接估计矩形 ER (estimative rectangle)。如

图1所示，ER的四条边分别平行于 $\textbf { x }$ 轴和y轴。ER的大小由式(1)确定。

![](images/edc0dacd27dd89406419aaae7c1142b491bc5fc6b35bfb27161044e2a69c2931.jpg)  
图1 Grid-Scan 原理

$$
( l _ { x } , l _ { y } ) = [ \operatorname* { m a x } { ( x _ { i } - r ) } , \operatorname* { m a x } { ( y _ { i } - r ) } ] \times [ \operatorname* { m i n } { ( x _ { i } - r ) } , \operatorname* { m i n } { ( y _ { i } - r ) } ]
$$

$( l x , l y )$ 为未知节点所属的ER大小， $i$ 为锚节点下标， $( x _ { i }$ $y _ { i } )$ 为锚节点的位置坐标， $\boldsymbol { r }$ 为锚节点的通信半径。

c)划分栅格并计算未知节点的坐标。设栅格的边长为 $l ,$ ER的长为 $L { \times } l$ ，宽为 $W { \times } l$ ，则ER可表示为 $\boldsymbol { L } \times \boldsymbol { W }$ 个栅格的集合 $G$ ，如式（2）所示。

$$
\pmb { G } = \{ G _ { 1 } , G _ { 2 } , \cdots G _ { m } \} \ , m = L { \times } W
$$

将网络中所有栅格的初始值赋为0， $C _ { m }$ 为栅格的中心，若ER内栅格 $G _ { m }$ 和 $C _ { m }$ 均位于 $\mathrm { ~ N ~ }$ 个邻居锚节点的通信范围内，则将栅格 $G _ { m }$ 赋值为 $N _ { \mathfrak { c } }$ ，ER内赋值最大的所有栅格组成的区域对应为一个未知节点的估计区域 $E _ { j }$ ，如图1(b)所示赋值最大的栅格组成的区域即为估计区域 $E _ { j }$ ，最后，计算该估计区域 $E _ { j }$ 的质心位置，实现对未知节点的定位。

# 2 二次栅格扫描与锚节点递减扫描法

# 2.1算法原理

本文通过对Grid-Scan定位算法的研究发现，在随机产生的网络拓扑中，未知节点的实际位置可能位于以估计位置到邻居锚节点的距离为半径的圆内，对栅格二次扫描后获得新的初始估计位置，对邻居锚节点有条件递减，完成算法的改进。

# 2.2二次栅格扫描法

首先由邻居锚节点的位置信息可以得到未知节点的初始位置估计，然后利用最近锚节点坐标信息与初始位置估计的坐标信息得到未知节点更小更精确的位置估计区域，二次扫描网格获得未知节点新的初始估计位置。二次栅格扫描算法具体分为3个阶段：

# 2.2.1初始位置估计

设未知节点的邻居锚节点个数为 $N$ ，将监测区域栅格化后，采用传统的Grid-Scan算法完成该未知节点的ER区域内的栅格已被赋值，得到 $E _ { j }$ 区域所有被赋值为 $N$ 的栅格Grid,从而产生未知节点的初始位置估计坐标 $( x t _ { 0 } , \ y t _ { 0 } )$ 。

# 2.2.2判断可再定位性

二次栅格扫描算法仅利用最近锚节点，存在不可定位的情况出现，故需要判定未知节点能否二次定位。

求出所有邻居锚节点到该未知节点的信号强度，设未知节点接收到所有邻居锚节点的信号强度为RSS，而RSS中的最大信号强度 $R S S _ { \mathrm { u } }$ 对应的锚节点即为最近锚节点。由式(3)计算初始位置估计到最近锚节点的距离dist。

$$
d i s t = \sqrt { ( x t _ { 0 } - x _ { \mathrm { i s t } } ) ^ { 2 } + ( y t _ { 0 } - y _ { \mathrm { i s t } } ) ^ { 2 } }
$$

（204 $( x _ { i s t } , \ y _ { i s t } )$ 为最近锚节点坐标，将dist代入式(4)可得初始位置到最近锚节点的理论信号强度 $R S S _ { \mathrm { e } }$ 。

$$
R S S _ { \mathrm { e } } = P _ { \mathrm { T } } - P _ { \mathrm { L } } ( d _ { 0 } ) - 1 0 \eta 1 0 { \bf g } _ { 1 0 } ( \frac { d i s t } { d _ { 0 } } )
$$

其中： $P _ { \mathrm { T } }$ 为发送信号功率； $P _ { \mathrm { L } } ( d _ { 0 } )$ 为参考距离 $d _ { 0 }$ 的路径损耗功率； $\eta$ 为路径损耗指数； $R S S _ { \mathrm { u } }$ 为未知节点从最近锚节点接收到的实际信号强度。

以最近锚节点圆心、以最近邻居锚节点与 $( x t _ { 0 } , \ y t _ { 0 } )$ 间的距离为半径进行扫描，将该半径通过式(4)计算成一个信号强度值。当最近邻居锚节点接收到未知节点的信号强度值大于由最近邻居锚节点与初始位置估计点的信号强度值时，则说明该未知节点处于以最近锚节点为圆心、以最近邻居锚节点与 $( x t _ { 0 } , \ y t _ { 0 } )$ 间的距离为半径的通信圆内，满足这一条件称该未知节点是可二次定位的，此时，进行二次栅格扫描后，可缩小定位区域，即：当 $R S S _ { \mathrm { u } } { > } R S S _ { \mathrm { e } }$ 时，判定未知节点存在可再定位性；反之，当最近邻居锚节点接收到未知节点的信号强度值小于由最近邻居锚节点与初始位置估计点的信号强度值时，则说明该未知节点处于以最近锚节点为圆心、以最近邻居锚节点与初始位置估计点间的距离为半径的通信圆外，即，当 $R S S _ { \mathrm { u } } { \le } R S S _ { \mathrm { e } }$ 时，判定未知节点不可二次定位。

# 2.2.3定位区域缩小

对可二次定位的未知节点进行二次栅格扫描。计算 $E _ { j }$ 区域内所有栅格的 $C _ { m }$ 到最近锚节点的距离 $D$ ，如式（5）所示。

$$
\pmb { { \cal D } } = \{ d _ { 1 } , d _ { 2 } , \cdots , d _ { m } \}
$$

当 $\_ d _ { m } > d i s t$ 时， $d _ { m }$ 对应在 $\it { G r i d }$ 内的值不变；当 $d _ { m } < d i s t$ 时， $d _ { m }$ 对应在Grid内的栅格值为 $N { + } 1$ ，赋值为 $N { + } 1$ 的栅格集合为Gridmap；由Gridmap产生一个新的估计区域 $E N _ { j }$ 计算 $E N _ { j }$ 的质心位置得到优化过后的初始估计位置。

![](images/30522cc8cb3181a6da93bc4dc9facab049c9467d2e419c9b3a8a2c62d29dac3b.jpg)  
Fig.1 Grid-Scan schematic diagram   
图2二次栅格扫描法  
Fig.2Two grid scanning method

如图2所示，设未知节点有三个邻居锚节点 $\mathbf { A } _ { 1 }$ 、 $\mathbf { A } _ { 2 }$ ，A3相交区域为 $E _ { j }$ ， $\mathbf { A } _ { 1 }$ 为最近锚节点，在 $E _ { j }$ 区域内得到未知节点的初始位置估计，得到 $E _ { j }$ 区域内栅格赋值为3的Grid，以初始位置到Ai的距离dist为半径对 $E _ { j }$ 区域进行栅格扫描得到估计区域 $E N _ { j }$ ， $E N _ { j }$ 区域内栅格值在Grid 基础上加1，得到ENj区域所有被赋值为4的栅格集合Gridmap，计算二次定位坐标。

# 2.3递减锚节点扫描法

将初始算法估计位置作为初始质心位置的递减锚节点扫描法记为NGrid-Scan算法，二次栅格扫描法估计位置作为初始质心位置的递减锚节点扫描法记为TNGrid-Scan算法。

在实际情况下，首先将监测区域进行栅格化，设未知节点邻居锚节点为AN，通过初始算法或者二次栅格扫描法，得到ER内赋值最大栅格，设为C，如式（6）所示。

$$
\pmb { C } = \left[ \begin{array} { c } { \vdots } \\ { C _ { h } } \\ { \vdots } \\ { } \end{array} \right]
$$

其中：h 为赋值最大的栅格下标。设 $C _ { h }$ 的质心坐标为 $( x _ { C h } , \mathrm { y } _ { C h } )$ 由 $C$ 得到的质心坐标为 $( x _ { f } , y _ { f } )$ ，栅格边长为1，锚节点矩阵为$_ { A N }$ ，如式（7）所示。

$$
A N = \left[ \begin{array} { c } { \vdots } \\ { \mathbf { N } _ { i } } \\ { \vdots } \\ { \vdots } \end{array} \right]
$$

计算得到邻居锚节点 $A N$ 与 $( x f , y f )$ 间的距离 $N F$ ，如式(8）所示。

$$
N F = \left[ \begin{array} { c } { \vdots } \\ { N C _ { i } } \\ { \vdots } \end{array} \right]
$$

将 $N C _ { i }$ 代入公式(3.1)得到邻居锚节点 $N _ { i }$ 接收到坐标 $( x f , y f )$ 的理论信号强度值RSSN，如式（9）所示。

$$
R S S N = \left[ \begin{array} { c } { \vdots } \\ { R S S N _ { i } } \\ { \vdots } \end{array} \right]
$$

在实际情况下，在通过BP神经网络校正的网络中，邻居锚节点 $N _ { i }$ 接收到未知节点 $U _ { j }$ 的信号强度为 $R S S _ { j i }$ ，满足$R S S N _ { i } { > } R S S _ { j i }$ 时，舍去该锚节点，当栅格 $C _ { h }$ 与锚节点之间距离代入公式(3.1)得到理论信号强度 $R S S G _ { h j }$ ，当 $R S S G _ { h j } { > } R S S N _ { i }$ 将栅格 $C _ { h }$ 的值继续赋值一次，并产生替代节点，再由替代节点进行下一次锚节点递减扫描，从而得到锚节点递减扫描赋值后的栅格 $G r i p$ ，如式（10）所示。

$$
G r i p = \left[ { \begin{array} { c } { \vdots } \\ { C _ { h } } \\ { \vdots } \end{array} } \right]
$$

其中：Grip中的元素来自于 $C$ 中的元素，且Grip中的元素数量小于或等于 $C$ 中的元素数量，如图3所示，赋值为7的栅格为邻居锚节点递减扫描所得到的最大赋值栅格。对最大赋值网格求其质心，该质心即为算法最终的定位点。

![](images/fbdf8b0cd7e804326e4f11afea595c938b078370ecd4a7e8bffe709c677c5d37.jpg)  
图3邻居锚节点递减扫描法  
Fig.3Neighbor anchor node diminishing scanning method

# 3 仿真实验

# 3.1实验设计

本文实验在MATLAB平台上进行，设节点个数为Node,并在 $1 0 0 { \times } 1 0 0 \mathrm { m }$ 监测区域内产生随机的拓扑场景，节点通信半径为 $\boldsymbol { r }$ ，栅格边长为l，节点发送信号功率 $P _ { T } { = } 0$ dB，参考距离 $d o { = } 1 \mathrm { ~ m }$ ，参考距离 $d o$ 的路径损耗功率 $P _ { L } ( d o ) { = } 5 5 ~ \mathrm { d B }$ ，路径损耗指数 $\scriptstyle \eta = 4$ 。将文中二次栅格扫描与锚节点迭递减栅格扫描的定位算法简记为TNGrid-Scan，同时分别将初始网格扫描算法、二次栅格扫描算法、锚节点递减栅格扫描定位算法简记为 Grid-Scan、TGrid-Scan、NGrid-Scan，将文献[12]中的算法简记为SGrid-Scan，将文献[15]中的算法简记为VGrid-Scan。将以上算法在归一化的平均相对定位误差上进行对比。其中，VGrid-Scan 算法依然采用文献[15]中锚节点通信半径的设定方法，设置为节点通信半径的0.7倍。

采用式(11)计算网络中未知节点归一化的平均相对定位误差。

$$
e r o r r _ { \mathrm { l o c a l } } = \frac { 1 } { r \cdot k \cdot n _ { \mathrm { u } } } { \sum _ { i = 1 } ^ { n _ { \mathrm { u } } } } \sqrt { ( x _ { \mathrm { e s } } - x _ { \mathrm { t } } ) ^ { 2 } + ( y _ { \mathrm { e s } } - y _ { \mathrm { t } } ) ^ { 2 } }
$$

其中： $( x _ { e s } , y _ { e s } )$ 表示未知节点的定位坐标； $( x _ { t } , y _ { t } )$ 表示未知节点的实际坐标； $\boldsymbol { r }$ 表示网络中节点的通信半径； $n _ { u }$ 表示网络中可定位未知节点的个数； $k$ 表示随机产生节点网络的次数，即归一化次数。实验中，归一化次数 $k { = } 1 0 0$ ，即产生100次的随机节点部署。其中：本文实验设 $k { = } 1 0 0$ ，即产生100个随机网络拓扑， $n _ { r }$ 为可定位的节点个数。

为了使改进算法的仿真误差更具对比性，将每次产生的随机网络拓扑场景分别提供给以上六种算法进行仿真，确保算法在相同环境下进行定位误差的计算，增加实验数据对比的可靠性。

# 3.2通信半径对算法定位误差的影响

通过式(1)可以发现，节点的通信半径可以影响未知节点的外接矩形的大小，进而影响邻居锚节点个数。设节点个数Node ${ \tt \left. \sum \right.} 0 0 $ ，锚节点个数为40，栅格边长 $l { = } 2 \mathrm { m }$ 。仿真结果如图4所示。

![](images/34e6f36d3882eb350ebdff44017d5874f2655239deb25d9ebc662d823891fbdd.jpg)  
图4通信半径对算法定位误差的影响 Fig.4Influence of communication radius on location error of algorithm

如图4所示，通信半径越大，以上算法的定位误差越低，并且锚节点递减算法对定位精度的提升明显优于其他算法，误差更低。TNGrid-Scan算法的定位误差较NGrid-Scan算法平均减小了 $0 . 6 1 4 \%$ ；TNGrid-Scan 算法的定位误差较TGrid-Scan 算法平均减小了 $6 . 8 6 3 \%$ ；TNGrid-Scan 算法的定位误差较VGrid-Scan 算法平均减小了 $7 . 7 \%$ ； TNGrid-Scan 算法的定位误差较Grid-Scan 算法平均减小了 $10 . 9 5 \%$ ：TNGrid-Scan 算法的定位误差较 SGrid-Scan 算法平均减小了$5 . 1 7 \%$ 。

# 3.3锚节点个数对算法定位误差的影响

锚节点密度影响邻居锚节点个数，邻居锚节点个数可以影响估计区域 $E _ { j }$ 的大小。设节点个数 $N o d e { = } 2 0 0$ ，节点通信半径 $\scriptstyle { r = 2 0 \mathrm { m } }$ ，栅格边长 $l { = } 2 \mathrm { m }$ 。仿真结果如图5所示。

![](images/fb46059b73e65fb7e5bb73ea446468f9729e6bd3a1759df62f9b90f27e4b93f4.jpg)  
图5锚节点个数对算法定位误差的影响 Fig.5Influence of number of anchor nodes on location error ol algorithm

如图5所示，以上算法的定位误差均随锚节点个数增加而逐步减小。TNGrid-Scan算法的定位误差较NGrid-Scan算法平均减小了 $0 . 6 3 4 \%$ ；TNGrid-Scan算法的定位误差较TGrid-Scan算法平均减小了 $5 . 6 2 \%$ ；TNGrid-Scan算法的定位误差较VGrid-Scan 算法平均减小了 $6 . 3 6 \%$ ；TNGrid-Scan算法的定位误差较Grid-Scan 算法平均减小了 $9 . 6 3 \%$ ·TNGrid-Scan算法的定位误差较SGrid-Scan算法平均减小了$5 . 0 3 \%$ 。

# 3.4节点个数对算法定位误差的影响

节点总数是衡量网络密集度的一个重要参数，因此仿真了节点总数对六种算法定位性能的影响。设节点通信半径$r { = } 2 0 \mathrm { m }$ ，锚节点个数为 $0 . 2 N$ ，栅格边长 $l { = } 2 \mathrm { m }$ 。仿真结果如图6所示。

![](images/f9ae984926b4309645404f03b1b57f18692f979c10525049b0a6c03caf09534f.jpg)  
图6节点个数对算法定位误差的影响  
Fig.6Influence of number of nodes on location error of algorithm

如图6所示，随着节点个数的增多，网络密集度随之变大，以上算法的定位误差均随之减小。TNGrid-Scan 算法的定位误差较NGrid-Scan 算法平均减小了 $0 . 7 1 \%$ ; TNGrid-Scan算法的定位误差较TGrid-Scan 算法平均减小了 $5 . 2 7 \%$ ·TNGrid-Scan算法的定位误差较VGrid-Scan算法平均减小了$6 . 1 4 \%$ ；TNGrid-Scan 算法的定位误差较Grid-Scan 算法平均减小了 $9 . 3 2 \%$ ；TNGrid-Scan 算法的定位误差较 SGrid-Scan算法平均减小了 $3 . 9 1 \%$ 。

# 3.5栅格边长对算法定位误差的影响

由Grid-Scan算法的定位原理可知，栅格的边长会对估计区域 $E _ { j }$ 边缘的栅格数量产生影响，从而影响 $E _ { j }$ 质心的位置。设节点个数 $N o d e { = } 2 0 0$ ，锚节点个数为40，节点的通信半径$r { = } 2 0 ~ \mathrm { m }$ 。仿真结果如图7所示。

![](images/322984d75c9872fc6c308152f35a266d4b255f388c1ec7664923326b40b6fb28.jpg)  
图7栅格边长对算法定位误差的影响  
Fig.7Influence of grid edge length on location error of algorithm

如图7所示，栅格边长越小，六种算法的定位误差越低，且TNGrid-Scan算法的定位误差较NGrid-Scan算法平均减小了 $0 . 9 4 \%$ ；TNGrid-Scan 算法的定位误差较TGrid-Scan算法平均减小了 $2 . 8 7 \%$ ；TNGrid-Scan算法的定位误差较VGrid-Scan 算法平均减小了 $5 . 5 0 \%$ ；TNGrid-Scan 算法的定位误差较Grid-Scan 算法平均减小了 $6 . 4 1 \%$ ；TNGrid-Scan算法的定位误差较SGrid-Scan 算法平均减小了 $3 . 8 9 \%$ 。随着栅格边长的增大，以上算法的定位误差就越接近，但TNGrid-Scan算法的定位精度要始终优于其他定位算法。

# 4 结束语

本文通过二次栅格扫描法对未知节点初始定位完成优化，然后对比理论信号强度值与实际信号接收强度，得到锚节点递减扫描法则，对邻居锚节点有条件递减，缩减了未知节点的定位区域，最终实现了二次栅格扫描与锚节点递减栅格扫描定位算法，有效地降低了定位误差。仿真结果表明，在变通信半径、变锚节点个数、变节点个数和变栅格边长的条件下，本文算法均有效降低了平均相对定位误差。

# 参考文献：

[1]任秀丽，任霞丽．无线传感网中节点的协同过滤定位算法[J/OL]. 计算机应用研究,2018,35(10).[2017-09-27].(Ren Xiuli,Ren Xiali. Cooperative filtering algorithm for node location in wireless sensor networks [J/OL].Application Research of Computers,2018,35（10). [2017-09-27].)   
[2]孙大洋，钱志鸿，韩梦飞，等．无线传感器网络中多边定位的聚类分 析改进算法[J]．电子学报,2014,42(8):1601-1607.(Sun Dayang. Qian Zhihong,Han Mengfei,et al.Improving multilateration algorithm by cluster analysis in WSN[J].Acta Electronica Sinica,2014,42(8): 1601-1607.)   
[3]钱志鸿，孙大洋，LEUNGV.无线网络定位综述[J].计算机学报, 2016,39 (6):1237-1256.(Qian Zhihong，Sun Dayang,LEUNG V.A survey on localization model in wireless networks[J].Chinese Journal of Computers,2016,39(6):1237-1256.)   
[4]Woojin K,Jaemann P,Jin K,et al.A multi-class classification approach fortarget localization in wireless sensor networks [J].Journal ofMechanical Science and Technology,2014,28(1):323-329.   
[5] 闫中江，龚红焱，沈中，等．基于网格扫描的WSN节点定位算法 [J]. 计算机工程,2011,37(21):68-71.(Yan Zhongjiang,Gong Hongyan, Shen Zhong,et al. WSN node localization algorithm based on grid scanning[J].Computer Engineering,2011,37(21):68-71.)   
[6]胡咏梅，张欢．一种改进的无线传感器网络质心定位算法[J].计算 机工程与科学,2012,34(2):45-49.(Hu Yongmei,Zhang Huan.An improved algorithm for the centroid localization of wireless sensor network[J].Computer Engineering& Science,2012,34(2):45-49.)   
[7]Victoria Y Z,Albert K W. Closed-form solution for joint localization and synchronization in Wireless Sensor Networks with and without beacon uncertainties [J].International Journal of Wireless Information Networks,2013,20(2):120-139.   
[8]Tian Y,Tang Z N,Yu Y. Received signal strength indicator-based adaptive localization algorithm for indoor wireless sensor networks [J]. International Journal of Wireless Information Networks,2013,22 (6): 1-7.   
[9]姚艳，禹继国，郭强．基于网格扫描的无线传感器网络定位算法 [J]. 计算机工程，2012,38(9):86-89.(Yao Yan,Yu Jiguo,Guo Qiang. Wireless sensor network localization algorithm based on grid scanning [J].Computer Engineering,2012,38 (9): 86-89.)   
[10]张会清，石晓伟，邓贵华，等．基于BP神经网络和泰勒级数的室内 定位算法研究[J]．电子学报，2012，40(9)：1876-1879.(Zhang Huiqing,Shi Xiaowei,Deng Guihua,et al.Research on indoor location technology based on back propagation neural network and taylor series [J].Acta Electronica Sinica,2012,40 (9):1876-1879.)   
[11]蒋锐，杨震．基于质心迭代估计的无线传感器网络节点定位算法 [J].物理学报,2016,65(3):1-8.(Jiang Rui,Yang Zhen.An improved centroid localization algorithm based on iterative computation for wireless sensor network[J].Acta Physica Sinica,2016,65 (3):1-8.)   
[12]彭爱平，郭晓松，蔡伟，等．基于二次栅格扫描的无线传感器网络定 位算法 [J].传感技术学报,2009,22(11):1651-1655.(Peng Aiping, Guo Xiaosong,Cai Wei,et al.A localization algorithm for Wireless Sensor Networks based on twice grid scan [J].Chinese Journal of Sensors and Actuators,2009,22(11):1651-1655.)   
[13] Sheu JP,Chen PC,HSUC S,et al.A distributed localization scheme for wireless sensor networks with improved Grid-Scan and vector-based refinement [J].IEEE Trans on Mobile Computing，2008,7(9): 1110-1123.   
[14]陆娴，彭勇．一种改进的 APIT定位算法[J].计算机工程与应用, 2015,51(3): 74-78.(Lu Xian,Peng Yong.Improved APITlocalization algorithm [J].Computer Engineering and Applications,2015,51(3): 74-78.)   
[15]李牧东，熊伟，梁青.Grid-Scan 算法定位精度和定位率的改进[J]. 计算机应用,2012,32(12):3521-3524.(Li Mudong,Xiong Wei,Liang Qing.Modified localization algorithm of APIT for WSN[J]. Journal of Computer Applications,2012,32(12):3521-3524.)