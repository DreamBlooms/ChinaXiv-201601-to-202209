# 基于NS-BML模型的记忆密度在交通信号灯控制系统中的研究

李兴华，霍艳凤，靳聪聪，宋波，李春华(山东科技大学 矿业与安全工程学院，山东 青岛 266590)

摘要：交通信号灯管理与控制直接影响着交通网络中的运行效率。NS-BML模型广泛应用于交通信号灯控制系统仿真，针对目前NS-BML模型中只考虑现在瞬时密度而忽略历史密度的问题，提出记忆密度策略，从长时记忆密度策略和短时记忆密度策略两个角度来分析该策略对曼哈顿式网络的影响，通过对时间离散化，求解短时记忆密度的最优比例因子。仿真结果表明，通过采用所提出的短时记忆密度策略可以有效提高系统的运行效率，同时保证计算机处理的速度，交通网络的平均速度和到达率分别同比增长 $8 . 5 1 \%$ 和 $9 . 2 8 \%$ ，说明了所提出策略的有效性。

关键词：元胞自动机；交通信号灯管理与控制；记忆密度；NS模型；BML模型中图分类号：TP391.9 doi: 10.3969/j.issn.1001-3695.2018.05.0257

Memory density was studied in traffic signal control system based on NS-BML model.

LiXinghua,Huo Yanfeng†, Jin Congcong, Song Bo,Li Chunhua (College of Mining & Safety Engineering Shandong Universityof Science & Technology,Qingdao; 266590, China)

Abstract:Traffic signal management and control directly affect theefficiencyof traffic network.The NS-BML model is widelyused in the simulationoftraffic signalcontrol system.For the problemofthecurent NS-BML modelonlyconsidered the present instantaneous density but neglected the historydensitythe memorydensitystrategywas proposed.This strategy was analyzed the influenceof the proposed strategy to the eficiencyof Manhatan network from two perspectives,the long memory densitystrategyand the short memorydensity strategy.Using time-discretization obtained theoptimal proportion factorof the short-term memorydensity.The simulationresults show thatthe efficiencyof the system can be improved efectively byusing the short memory density strategy proposed inthis paper.Atthe same time,the eficiencyof computer processing is guaranteed. The average speed and the rate of arrival of the system are increased by $8 . 5 1 \%$ and $9 . 2 8 \%$ （204 respectively, indicating the effectiveness of the proposed strategy.

Key Words: Celular automata; Management and control of traffic signals; Memory density; NS model;BML model

# 0 引言

随着世界经济的飞速跨越式发展，交通拥堵日益严重，交通信号灯可以缓解交通冲突所带来的交通拥堵。Ewin 等人[1]认为交通建设的里程发展速度跟不上世界经济需求的增长速度，人们对于交通的需求日益增多。Parmar等人[2认为车辆的交通堵塞对经济、生产力和污染的三条生命线造成了不利的影响。Feng等人[3认为城市的快速扩张和高速发展，导致了几乎每天都出现严重的交通拥堵。Fei等人[4认为交通拥堵会增加交通事故的可能性。Surya等人[5观察表明，随着车辆交通的发展，城市城市迫切需要交通拥堵的缓解，在一个十字路口，一个固定的持续时间的交通信号灯可以有效提高交通的运行效率，缓

解交通冲突所带来的交通拥堵。

交通拥堵研究的方法有很多。Le等鼓励人们使用公共汽车服务来减轻城市环境和交通的压力。Cao等人[7提出了一种基于信息要素的交通管理框架，以减少交通拥堵。Li等人[8将增强学习技术纳入可变限速控制策略，以减少高速公路瓶颈的系统旅行时间。Porat等人[9将网络的思想融入到缓解交通拥堵的策略中，建立拥堵缓解机制，通过该机制获得每个节点的最优参数配置。

元胞自动机是研究交通的有效方法之一，在动态研究方面具有比较好的效果。Wolfram[10将元胞自动机这一理论方法引入到科学问题研究中，后来该方法的184号模型逐步演化为NS模型，引起了交通领域的广泛关注。胡清梅等人[1认为元胞自动机能够对一系列密度条件下的复杂交通流仿真，具有很好的仿真近似性。Chai等人[12]提出了一种改进的元胞自动机(CA)模型来估计交通冲突的出现和严重程度，研究结果表明CA方法能够有效刻画现实的交通拥堵情况。安旭等[13]建立了基于NS 模型针对交织区的元胞自动机模型，研究发现流量较高并且交织比不大时，设置隔离带将减少系统拥堵及各流向车辆的行程时间。Belz等人[14]介绍了一种新的元胞自动机模型，考虑了出行行为因素的影响，从而精确地评估环形路网的性能。Liu等人[15提出了一种基于短链分组的元胞自动机模型，研究了在交通信号控制下的短链交叉路口的交通流特征。Gaurav 等人[17]提出并验证一种改进的元胞自动机模型，考虑了横向位置偏好，可根据领导者和追随者车辆的速度和减速特性动态地计算安全前和后隙，取得良好效果。张凤琴等人[16以节点作为元胞自动机的元胞，构建城市交通网络流量元胞自动机预测模型，并证实了该模型对于城市的交通管理能力有一定的提升作用。

NS 模型和BML模型的融合是元胞自动机进行交通研究的有效方法。Wu 等人[8基于NS模型，并考虑了采用不同驱动规则的驱动因素，提出了一种基于双车道公路交通流的元胞自动机混合模型。Zhang等人[19]研究了在周期边界条件下的 NS交通模型中流动-密度图中最大速度v(max)和随机概率p的两种重要参数的机制。Linesch等人[20]基于BML模型研究了网络交通流的自组织特征。

交通信号灯在NS-BML融合模型中的研究越来越受到人们的重视。人们进行动态交通配时时，多数情况使用的是某一时刻的交通量而忽略了对历史交通量的考量。Lu等人[2I]介绍了一种新型的二维元胞自动机，这些模型中的许多都显示了急剧的阶段转换、自组织的特性。 $\mathrm { H u }$ 等人[22]提出了一种改进的BML模型(EBML)，有效地模拟了基于量子粒子群优化算法的时间调度优化算法，从而优化了交通信号灯的时序安排。Kuang等人[23]从慢速启动的效果出发，基于 BML 模型，利用平均场理论得到了最大速度的理论值。Sun等人[24基于BML模型研究了不同交通灯周期对交通流的影响。Qian等人[25]通过采用汽车跟踪规则，应用BML模型研究独立运行交通信号灯对交通性能的影响，但并未涉及动态交通配时的内容。Jiang、敖大成等人[26:27]基于 NS-BML 融合模型研究了曼哈顿式网络的系统稳定性，但是其对于交通信号灯的考量仅是某一时刻的数据，而没有从历史的角度分析，历史交通量对于动态交通配时的影响，这是本文所有研究的内容，进行初步探求该处的研究空白。

综上所述，人们在进行动态交通配时时，多数情况使用的是现在瞬时时刻的交通量而忽略了对历史交通量的考量。本文基于NS-BML融合模型，将历史交通量引入到元胞自动机中，提出记忆密度策略，同时考量储存历史交通量数据所占用的空间，从长时记忆密度策略和短时记忆密度策略两个角度来分析所提出策略对曼哈顿式网络的影响，并通过对时间进行离散化，计算最优配比，从而提高系统效率，弥补目前研究所存在的缺陷。

# 1模型

# 1.1曼哈顿式网络搭建

本文所采用的数据为青岛滨海花园东南角交通信号灯信息，均采用单信号灯控制，考虑计算机仿真的效率，选取路段数目为 $N \times N = 1 8 \times 1 8$ 的方形曼哈顿式网络，设置网络的车辆密度为0.2，将车辆作为元胞进行交通仿真，任意相邻的交叉路口由两条路段连接，两条路的通行方向相反，对路段长度进行整数离散化，元胞长度设置为 $6 \mathrm { m }$ ，以贴近汽车的实际长度；青岛滨海花园周围4段路总长为1600米，取每段路400米，同时为了道路的取整性，则每段路取元胞的数量为67个，合计402米，如图1所示。

![](images/d61e623d924a8819fe2578da79fdbb4a8ff9d10ea1761044fb575e1939ffec4d.jpg)  
图1 $1 8 \times 1 8$ 曼哈顿式网络

# 1.2交通信号灯设置与参数

a）每个交叉路口处均设有交通信号灯，采用单向控制。入向道路为绿灯时，该道路的车辆可以直行、左转、右转和掉头，其他道路不可通行，即十字交叉路口只有一条路的交通信号灯是绿灯，其他三条路的交通信号灯均为红灯。

b）交通信号灯周期为 $\mathrm { T } { = } 8 1 { \times } 2 { = } 1 6 2 \mathrm { s }$ 。数据81s是从百度地图中对交通信号灯拍摄的图像中获得，乘以2而不是乘以4是因为在现实的交通信号管控中通常均采用对向控制，相向行驶的交通信号灯具有相同的信号，即同绿同红。

c）交叉路口占据一个元胞的位置。  
d）不设置黄色交通信号。  
e）交通信号灯顺时针进行转换。

# 1.3自适应交通信号灯策略

1）动态时间分配

所有交叉路口的交通信号周期设为 $T$ ，交通信号灯顺时针进行转换，绿灯由两部分组成：静态时间 $T _ { \mathrm { s t a t i c } }$ 和动态时间（204号 $T _ { \mathrm { d y n a m i c } }$ ，静态绿灯时间是最小的绿灯时间，对所有的驶入路段一致。动态绿灯时间与道路车辆密度呈正比：

$$
T _ { d y n a m i c , i } = \frac { \rho _ { i } ^ { \alpha } } { \displaystyle \sum _ { i = 1 } ^ { m } \rho _ { i } ^ { \alpha } } \times \left( T - m T _ { s t a t i c } \right)
$$

其中: $m$ 是交叉路口驶入车辆路段的数量， $\rho _ { i }$ 是交叉路口驶入路段 $i$ 的瞬时车辆密度，在 $t = 0 , T , 2 T , \cdots$ 时刻进行更新， $\alpha$ 是

可调参数，反映各路段密度的权重。[26-27]

# 2）余数时间分配

由于元胞自动机参数设置需要保证数据的整数性，针对该部分的问题本文采用蒙特卡罗仿真的方法将余数逐一随机分配到每条道路上。

# 3）无密度时间分配

如果在一个周期结束的瞬时时刻，与交通信号灯相连的路段上均无驶入车辆，则继续使用上次的交通配时方案。

# 1.4车辆行驶规则

车辆的位置不同，车的行驶规则也不同，首先进行车辆类别划分。目前对于双车道的NS-BML模型，头车和尾车的定义没有明确的说明，本文给出NS-BML模型中车辆的分类，定义如下：

定义1将在一条道路中距离行驶方向前方交通信号最近的一辆车定义为头车，且该车不在交通信号灯位置。将在一条道路中距离行驶方向前方交通信号最远的一辆车定义为尾车，且该车不在交通信号灯位置。将占据交通信号灯位置的车辆路□车。除头车和路口车以外的其他车辆称为非头车。

a）车辆起点和目的地随机产生，当车辆到达目的地时，重  
新随机赋予新的目的地。b）车辆的路径选择。车辆在进行路径选择时，总是选择几  
何最短路行驶；多条最短路时，出行者根据先进的出行者信息  
系统（ATIS）提供的平均速度值，选择平均速度最大的一条。c)车辆只能靠右行驶。车辆不得在非交通信号灯位置掉头。d）在每个交叉路口，遵守“绿灯行，红灯停”的规则，在  
十字路口时，按照交通信号灯控制，车辆可以经过十字路口进  
行直行、左转、右转和掉头。e）车辆在道路上按照NS模型行驶，车辆遵守以下更新规  
则：(a)加速： $\nu _ { n }  \operatorname* { m i n } ( \nu _ { \operatorname* { m a x } } , \nu _ { n } + 1 )$ 。取速度最大值 $\nu _ { \mathrm { m a x } }$ 为

3cell/s 。

(b)减速： $\nu _ { n }  \operatorname* { m i n } ( d _ { n } , \nu _ { n } )$ 。 $d _ { n }$ 是表达车间距，$d n = d n _ { 1 } + d n _ { 2 } + d n _ { 3 }$ ， $d n _ { 1 }$ 表示车辆距离交叉口或者同车道紧前车辆的空元胞数， $d n _ { 2 }$ 表示路口元胞数是否被占据，取值为1表示被占据，取值为0表示未被占据， $d n _ { 3 }$ 表示下一路段中尾车距离其背向交通信号灯的元胞数。

(c)随机慢化：以一定的随机概率 $\mathsf { p }$ ， $\nu _ { n }  \operatorname* { m i n } ( \nu _ { n } - 1 , 0 )$ 。取随机慢化概率为0.1。(d)位置更新: $x _ { n } \to x _ { n } + \nu _ { n }$ 。f）非头车车辆行驶控制， $d n _ { 2 } = d n _ { 3 } = 0$ ，则 $d n { = } d n _ { 1 }$ 。g）头车车辆行驶控制。(a)当交通信号灯为红灯时，对于头车车辆， $d n _ { 2 } = d n _ { 3 } = 0$ 则 $d n { = } d n _ { 1 }$ 。

(b)当交通信号灯为绿灯时，如果行使方向交叉口没有被占用并且行使的最短路方向的车道最后一个单元格没有被车辆占据， $d n _ { 2 } = 1$ ， $d n _ { 3 }$ 为实际下一路段中尾车距离其背向交通信号灯的元胞数，则 $d n = d n _ { 1 } + d n _ { 2 } + d n _ { 3 }$ 。

(c)当交通信号灯为绿灯时，如果行使方向交叉口被占用或者行使的最短路方向的车道最后一个单元格被车辆占据，则对于头车车辆， $d n _ { 2 } = d n _ { 3 } = 0$ ，则 $d n { = } d n _ { 1 }$ 。

h)路口车辆行驶控制，路口车在下一秒优先按照理想车道进行直行、左转、右转和掉头，不需要考虑交通信号灯的方向。

i）防止跃出目的地控制。车辆在城市道路中限定最大速度为 3cell/s，则采用轨迹的方法来进行判定其是否越过目的地。控制过程：判定车辆距离目的地欧式几何距离，如果其平方和大于9，则说明没有可能越过目的地，如超过9，则检测车辆行驶的轨迹中是否含有目的地，如何含有目的地则将车辆更新至目的地的位置，并给到达目的地的车辆分配新的目的地。

# 2 问题及策略

# 2.1问题阐述

目前所查到的文献中NS-BML模型中进行动态交通配时，采用的是现在瞬时车道密度，而没有考虑历史车道流量的影响。

本文截取青岛市市政府南门区域进行说明，采用百度地图测量路段长度，四个路段的总长度为 $1 . 6 \mathrm { k m }$ ，平均段路的长度为 $0 . 4 \mathrm { k m }$ ，如图2所示。其中D为滨海花园东南角，从C到D距离为 $4 7 1 \mathrm { ~ m ~ }$ ，交通信号灯在该方向的绿灯时长为81s，限速为$6 0  { \mathrm { k m } } /  { \mathrm { h } }$ ，如图3所示。按照限制速度行驶 $4 7 1 \mathrm { m }$ 需要28.26s;考虑实际过程中车辆的行驶速度，假定实际速度为 $4 0 ~ \mathrm { k m / h }$ ，通过 $4 7 1 \mathrm { ~ m ~ }$ 需要 $4 2 . 3 9 \mathrm { ~ s ~ }$ 。无论是28.26s还是 $4 2 . 3 9 \mathrm { ~ s ~ }$ ，该时间与该相位的时间81s差距较大，意味着，该相位绿灯时间内不仅仅可以通过该条路段的车辆，还通过了很多非与该路口直接相连路段上的车辆。

![](images/422b626413cbf2b4e60d5dd009f26da934184f85891faf1b588e37ed6d956b07.jpg)  
图2青岛市市政府南门区域

![](images/f6143db2ad90393a869c40589d63abfefe26d510dbf031a63e21282fc45e52a8.jpg)  
图3D区域交通信号灯

从而说明：时间的路口交通信号灯控制的车辆数不仅仅与路段相连的路段车辆相关，还与未来驶入该路段的车辆相关。若从与当前路段相连的其他路段分析入手，则难以考量各路段流入该路段的车辆数目，但是，车辆总会通过该路段，只是时间维度上问题，于是本文从历史交通量的角度来完善这一不足，提出了记忆密度策略。

与现有文献中不同之处在于：本文不仅考虑了现在瞬时密度的影响，而且考虑了历史密度对交通控制系统的影响，本文将在NS-BML 模型中同时考虑现在密度和历史密度来确定自适应信号灯动态时间的策略称之为记忆密度策略。

# 2.2长时记忆密度策略

考虑过往的一切周期节点密度的影响，提出长时记忆密度策略。首先本文对文献[26]中关于动态时间的公式进行改善，对路段的瞬时密度 $\rho _ { i }$ 进行重新定义，改善成记忆密度，其计算公式为

$$
\rho _ { i , t } = { \sum _ { k = 1 } ^ { t } } \Biggl ( \eta _ { i , k } \frac { x _ { i , k } } { L _ { i } { * } S } \Biggr )
$$

$$
\sum _ { \mathrm { k } = 1 } ^ { t } \eta _ { i , k } = 1 , \eta _ { i , k } \ge 0
$$

$$
\eta _ { i , k } = 1 / t , ~ \eta _ { i , k } \geq 0 , ~ k = 1 , 2 , 3 , . . . , t ; i = 1 , 2 , . . . , m
$$

$$
T _ { \mathrm { d y n a m i c } , i , t } = \frac { \rho _ { i , t } ^ { \alpha } } { \displaystyle \sum _ { i = 1 } ^ { m } \rho _ { i , t } ^ { \alpha } } \times \left( T - m T _ { \mathrm { s t a t i c } } \right)
$$

$$
T _ { i , t } = T _ { \mathit { d y n a m i c , i , t } } + T _ { \mathit { s t a t i c } }
$$

其中： $\rho _ { i , t }$ 表示第i条道路在t时间段内的记忆密度，单位为辆/m; $\eta _ { i , k }$ 表示第i时间段整数离散化后各个周期节点瞬时密度所占的比重，无量纲单位，为了简化公式，将公式2中的比重系数 $\eta _ { i , k }$ 统一为固定值，即令其值均相等； $L _ { \phantom { } _ { i } }$ 表示第i条路的元胞数目，单位为cell；S表示平均车长，单位为 $\mathrm { { m } / \mathrm { { c e l l } } }$ ； $x _ { i , k }$ 表示第i条道路在第 $\mathbf { k }$ 个周期节点的瞬时车辆数，单位为辆，$k = 1 , 2 , 3 , . . . , t ; i = 1 , 2 , . . . , m$ ； $T _ { d y n a m i c , i , t }$ 表示第i个路段在t时刻的动态绿灯时间，单位为 $\mathrm { ~ \bf ~ s ~ }$ ； $T _ { i , t }$ 表示第i个路段在t时刻的绿灯时间，单位为s； $T _ { \mathrm { s t a t i c } }$ 表示静态绿灯时间，单位为s； $m$ 表示与交通信号灯连接的路段数量； $T$ 表示交通信号灯周期时间，单位为s； $\alpha$ 是可调参数，反映各路段密度的权重。

# 2.3短时记忆密度策略

长时记忆策略需要占用较多的内存，为减少内存提高运行效率，提出短时记忆密度策略，其为一种间隔周期待定比重系数的策略，只采用过去一个瞬时时刻密度与现在瞬时时刻密度的数据进行加权处理。

在固定交通信号灯总周期时间的情况下，因调整每个相位绿信比是在每个周期结束之后进行，采用的策略是提取周期时间节点前后两次的瞬时密度数值。其公式表示为

$$
\rho _ { i , t } = \eta _ { 1 } \frac { x _ { i , t - T } } { L _ { i } ^ { * } S } + \eta _ { 2 } \frac { x _ { i , t } } { L _ { i } ^ { * } S }
$$

$$
\eta _ { 1 } + \eta _ { 2 } { = } 1
$$

其中： $\rho _ { i , t }$ 表示第i条道路在t时间段内的记忆密度，单位为辆$/ \mathrm { m }$ ； $\eta _ { \mathrm { 1 } }$ 和 $\eta _ { 2 }$ 分别表示间隔周期的周期节点的密度值的权重，无量纲单位； $L _ { \mathrm { { } } i }$ 表示第i条路的长度，单位为cell；S表示平均车长，单位为m/cell; $T$ 表示交通信号灯周期时间，单位为 s； $x _ { i , t }$ 表示第i条道路在第t个周期节点的瞬时车辆数，单位为辆，$t = t$ or $t - T$ 。首先将比重系数根据长时记忆策略的方法，统一设置为均值0.5，之后采用遍历算法求解最优比例。

将现有文献中策略与本文所采取的策略进行原理对比，结果如表1所示。

表1策略对比结果表  

<html><body><table><tr><td></td><td>现在瞬时策略</td><td>长时记忆策略</td><td>短时记忆策略</td></tr><tr><td rowspan="2">共同点</td><td></td><td>采用的瞬时密度；</td><td></td></tr><tr><td></td><td>属于自适应控制范畴</td><td></td></tr><tr><td rowspan="2">不同点</td><td></td><td>现在瞬时密度，与 现在瞬时密度+全现在瞬时密度+部</td><td></td></tr><tr><td>历史密度无关</td><td>部历史瞬时密度</td><td>分历史瞬时密度</td></tr></table></body></html>

# 3 仿真实验

# 3.1参数设置

采用MATLAB2016a软件进行编程，结合矩阵更新的思想，将整个网络中分为四个矩阵层，控制绘图矩阵层A、控制车辆矩阵层B、控制交通信号灯矩阵层C和控制路网矩阵层D，其属性设置如表2所示。

表2矩阵层属性设置   

<html><body><table><tr><td colspan="2">显示矩阵- A</td></tr><tr><td>序号</td><td>属性</td></tr><tr><td>1</td><td>包含车辆信息的路网矩阵，将B、C和D三个矩阵融合在一起形成的路 网矩阵，用于图像显示，矩阵的大小为((L+2)×N+2)2。</td></tr><tr><td colspan="2">车辆信息控制矩阵——B</td></tr><tr><td>序号</td><td></td></tr><tr><td>1</td><td>车辆序号</td></tr><tr><td>2,3</td><td>车辆位置横、纵坐标（简称坐标)</td></tr><tr><td>4,5</td><td>目的地坐标</td></tr><tr><td>6</td><td>车辆类别，头车值为1，否则值为0</td></tr><tr><td>7</td><td>d 车辆距离同车道紧邻前方车辆或者交通信号灯的距离，即</td></tr><tr><td>8，9</td><td>车辆的运动方向。 （0.1）表示东；（0,-1）表示西； （-1.0）表示北</td></tr><tr><td>10</td><td>车辆行驶速度</td></tr><tr><td>11，12</td><td>车辆紧前交通信号灯坐标</td></tr><tr><td>13，14</td><td>车辆目的地紧后交通信号灯坐标</td></tr><tr><td>15</td><td>表示下一路段中尾车距离其背向交通信号灯的元胞数，在车辆运行规则 中的d</td></tr><tr><td>16，17</td><td>目的地紧前交通信号灯坐标</td></tr><tr><td>18,19</td><td>经过当前红绿灯之后在下一路段的运动方向</td></tr><tr><td>20</td><td>车辆安全距离，防止越出目的地</td></tr><tr><td>21</td><td>车辆是否为路口车，路口车值为1，否则值为0</td></tr><tr><td colspan="2">交通信号灯控制矩阵- -C</td></tr><tr><td>序号</td><td></td></tr><tr><td>1</td><td>交通信号灯序号</td></tr><tr><td>2,3</td><td>交通信号灯位置坐标</td></tr><tr><td>4</td><td>西向绿灯时长</td></tr><tr><td>5</td><td>东向绿灯时长</td></tr><tr><td>6</td><td>北向绿灯时长</td></tr></table></body></html>

<html><body><table><tr><td>7</td><td>南向绿灯时长</td></tr><tr><td>8，9</td><td>交通信号灯此时的通行方向</td></tr><tr><td>10</td><td>交通信号灯相连车辆向西行驶的车辆数</td></tr><tr><td>11</td><td>向东行驶的车辆数</td></tr><tr><td>12</td><td>向南行驶的车辆数</td></tr><tr><td>13</td><td>向北行驶的车辆数</td></tr><tr><td colspan="2">路网矩阵—-D</td></tr><tr><td>序号</td><td>属性</td></tr><tr><td>1</td><td>路网属性层，无车辆信息，包含交通信号灯和路网信息，用于初始化路 网，矩阵的大小为(L+2)×N+2)2。</td></tr><tr><td colspan="2">表3 输入参数含义</td></tr><tr><td>序号</td><td>含义</td><td>取值</td></tr><tr><td>1</td><td>L</td><td>路长</td></tr><tr><td>2</td><td>T</td><td>交通信号灯周期时间</td></tr><tr><td>3</td><td>Ts</td><td>交通信号灯静态时间</td></tr><tr><td>4</td><td>N</td><td>曼哈顿网络每条边的路段数目</td></tr><tr><td>5</td><td>Vmax</td><td>最大行驶速度</td></tr></table></body></html>

<html><body><table><tr><td>6</td><td>P</td><td>随机慢化概率</td><td>0.1</td></tr><tr><td>7</td><td>p</td><td>路网中车的密度</td><td>0.2</td></tr><tr><td rowspan="2">8</td><td></td><td>绘制矩阵A时，交通信号灯对</td><td rowspan="2">10</td></tr><tr><td>light_value</td><td>应的数值，只要与其它value</td></tr><tr><td>9</td><td>car_value</td><td>值不同，可任意取值</td><td></td></tr><tr><td>10</td><td>load_value</td><td>车对应的数值 路对应的数值</td><td>1</td></tr><tr><td>11</td><td>noload_value</td><td>非路网部分对应的数值</td><td>-1 0</td></tr><tr><td></td><td></td><td></td><td>初始值设</td></tr><tr><td>12</td><td>t</td><td>循环计数</td><td>为0</td></tr><tr><td>13</td><td>TT</td><td>需要进行仿真的次数。</td><td>1000</td></tr></table></body></html>

输入参数为L、T、Ts、N、Vmax、p、ρ、light_value、car_value、load_value、noload_value、t、TT，其含义及参数设置如表3所示，利用网络的平均速度、密度矩阵分布和到达率来描述系统的运行效率。模型的基本仿真流程如图4所示。

![](images/c5413c439cd5a6bcde5f36b75a8f637715f38afdcb379c37073787f5217554a2.jpg)  
图4仿真程序运行图

# 3.2程序改善

采用记忆密度策略之后，需要建立矩阵E对历史的密度值进行储存，不同策略具有不同的矩阵维度。可以分为三种情况，一种是现有文献中所采用的现在密度策略，不需要建立矩阵。第二种采用长时记忆密度策略，需要建立矩阵，采用的是历史所有周期节点的密度值和现在的密度值，矩阵的维度随着时间t而不断增大，其维度为（（ $_ { \mathrm { N + 1 } }$ ）^2，4t）。第三种是采用短时记忆密度策略，需要建立矩阵，采用的是历史周期节点的密度值和当前的密度值，截取的周期数目一定，不断更新，矩阵的维度不随着时间t变化，其维度为（（ $_ { \mathrm { N + 1 } }$ ）^2，8）。根据本文提出的记忆密度策略对流程改善，流程图如图5所示。

![](images/b2deb4185ac97d3b56fdb6e1091835cc271584e367f9b711a3dc16dcd62e725c.jpg)  
图5记忆密度策略流程图

# 4 结果分析

# 4.1策略对比

通过对现有文献中的策略（现在瞬时策略）、长时记忆密度策略、短时记忆密度策略分别进行仿真实验，从平均速度和路网密度分布、到达率三个角度进行结果分析对比，对比结果如图6、7和表4所示。

图6表明，短时记忆密度策略与现在瞬时策略速度变化趋势相似，而与长时记忆密度差异较大；而且长时记忆密度策略波动性大，平稳性差。

从表4可以看出，按照速度大小进行排序，长时记忆密度策略速度 $V _ { 2 } <$ 现在瞬时策略速度 $V _ { 1 } <$ 短时记忆密度策略速度$V _ { 3 }$ ，同现在瞬时策略速度相比，长时、短时记忆密度策略同比增长 $. 0 . 1 6 \%$ 和 $8 . 5 1 \%$ ，说明了短时记忆密度策略能够有效提升系统的运行效率，但是长时记忆密度策略有可能会降低系统的运行效率。按照到达率进行排序，长时记忆密度策略到达率<现在瞬时策略到达率 $<$ 短时记忆密度策略到达率，同现在瞬时策略速度相比，长时、短时记忆密度策略同比增长 $- 1 . 3 6 \%$ 和$9 . 2 8 \%$ 。

![](images/1aabb89f255d3d66df0059b6d79c108691d0790d55a574b307aa938e3326e127.jpg)  
图6速度对比图

表4平均值与到达率  

<html><body><table><tr><td rowspan="2">序号</td><td rowspan="2">策略</td><td colspan="2">速度平均值/ 速度同比增长</td><td rowspan="2">到达率/104</td><td rowspan="2">到达率同比增 长比例</td></tr><tr><td>(cell/s)</td><td>比例</td></tr><tr><td>1</td><td>现在瞬时策略</td><td>0.5123</td><td></td><td>2.3338</td><td></td></tr><tr><td>2</td><td>长时记忆密度</td><td>0.5115</td><td>-0.16%</td><td>2.3021</td><td>-1.36%</td></tr><tr><td></td><td>策略 短时记忆密度</td><td></td><td></td><td></td><td></td></tr><tr><td>3</td><td>策略</td><td>0.5559</td><td>8.51%</td><td>2.5503</td><td>9.28%</td></tr></table></body></html>

![](images/e24a975cad46e5aa17e8d11e79bdbde5acd8f52cfe5b8e2d78656362b00a0a6f.jpg)  
(b）长时记忆密度策略

![](images/4cfd92197697a71213bc7eae4aab7ee91c6897b115eaeb16d10d3d76a9bc6413.jpg)  
(c)短时记忆密度策略

图7(a)和(b)对比可知，现在瞬时密度策略速度分布与长时记忆密度策略差别较大，现在瞬时策略中高密度区域分布在网络的中心，而长时记忆密度策略中高密度区域分布在网络的四周；图7(a)和(c)对比可知：现在瞬时策略速度分布与短时记忆密度策略相似，但是其密度却比短时记忆密度策略大。

原因分析：之所以产生长时记忆密度策略 $<$ 现在瞬时策略<短时记忆密度策略的现象，主要在于，现在瞬时密度在交通信号灯控制中占据较为重要的位置，但是长时记忆密度将历史各个时间上瞬时密度进行等同处理，导致系统的效率和稳定性下降；而短时记忆密度策略兼具了历史数据、现在数据和计算机的处理效率，其效果最佳，但是最优比例因子是否均为0.5，需要根据下一节的内容进行研究判断。

结论：a）采用时间记忆密度策略不一定能够提高系统的效率，这与历史密度所占的比重相关；短时记忆密度无论是在计算机处理效率方面还是路网运行效率方面均具有一定优势;b)采用比例因子均为0.5时，短时记忆密度网络的运行效率比现在瞬时策略在平均速度和到达率分别同比增长 $8 . 5 1 \%$ 和 $9 . 2 8 \%$ ，说明了本文所提出策略的有效性。

# 4.2 最优比例

本节探讨在参数设定之后，权重 $\eta _ { \mathrm { 1 } }$ 和 $\eta _ { 2 }$ 的最优取值。本文通过遍历算寻求最优配比。取其间隔为0.05，进行仿真实验，采用路网的平均速度作为评价指标，仿真结果如图8所示。

![](images/46fb81147d30016ee05ace953693e91b0e5732db969997b24190786098c8dbd6.jpg)  
图7密度对比图  
图8最优比例仿真结果

由图8可知,a）最优比例是在 $\eta _ { 1 } = 0 . 3 5$ 和 $\eta _ { 2 } = 0 . 6 5$ 处取得，其效果要优于 $\eta _ { 1 } = 0 . 5$ 和 $\eta _ { _ 2 } { = } 0 . 5$ ，同比增长幅度为 $1 . 8 8 \%$ ；b)

只采用历史密度不采用现在瞬时密度效果更差，平均速度降低幅度为 $8 8 . 0 2 \%$ ，而只采用现在瞬时密度，其效果依然不佳。

# 5 结束语

随着中国经济的迅猛发展，人们对于交通的需求越来越大，交通拥堵也日益严重，交通信号灯的研究与使用可以缓解交通拥堵。本文主要研究了现有NS-BML模型中只考虑现在瞬时密度而忽略历史密度的问题，提出记忆密度策略，从长时记忆密度策略和短时记忆密度策略两个角度来分析所提出策略对曼哈顿式网络的影响，选择青岛市市政府南门区域对模型进行数据标定，通过采用短时记忆密度策略，平均速度和到达率同比增长 $8 . 5 1 \%$ 和 $9 . 2 8 \%$ ；通过遍历算求得最优配比为 $\eta _ { \mathrm { 1 } } = 0 . 3 5$ 和$\eta _ { 2 } = 0 . 6 5$ ，速度同比增长为 $1 . 8 8 \%$ ，说明了本文所提出策略的有效性。本文的研究对实际交通信号控制系统动态交通分配具有一定的借鉴意义。

当然，本文还存在可继续研究的空间，例如在短时记忆密度策略中，研究考虑多个历史周期节点的瞬时密度，其为多变量权重求解问题，试采用启发式算法寻求最优解，这是笔者下一步研究的方向。

# 参考文献：

[1]Ewing R,Tian Guang,Lyons T.Does compact development increase or reduce traffic congestion?[J].Cities,2018,72 (2): 94-101.   
[2]Parmar R S,Trivedi B,Stevanovic A.A model with traffic routers, dynamically managing signal phases to address traffic congestion in real time [J].Journal of Transportation Technologies,2018,O8 (1): 75-90.   
[3]Feng Xuesong,Saito Mitsuru,Liu Yi.Improve urban passenger transport management by rationally forecasting traffic congestion probability [J]. International Journal of Production Research,2O16,54(12):1-10.   
[4]Fei Wenpeng，Song Guohua,Zang Jinrui et al.Framework model for time-variant propagation speed and congestion boundary by incident on expressways [J].IETIntelligent Transport Systems,2017,11(1):10-17.   
[5]Surya S,Rakesh N. Traffic congestion prediction and intelligent signalling based on Markov decision process and reinforcement learning [C]//Proc of International Conference on Cognition and Recognition.2O18,1: 317-331   
[6]Linh TP,Trinh T A.Encouraging public transport use to reduce traffic congestion and air pollutant: a case study of Ho Chi Minh City, vietnam [J]. Procedia Engineering,2016,142: 235-242.   
[7]Cao Zhiguang,Jiang Siwei, Zhang Jie,et al.A Unified framework for vehicle rerouting and traffic light control to reduce traffic congestion [J]. IEEETrans on Intelligent Transportation Systems，2O17,18(7): 1958-1973.

[8]Li Zhibin,Liu Pan,Xu Chengcheng,et al.Reinforcement learning-based variable speed limit control strategy to reduce trafic congestion at freway recurrent bottlenecks [J]. IEEE Trans on Intelligent Transportation Systems, 2017,PP (99): 1-14.

[9] Porat H. Method and a system for controlling traffic congestion in a network [P]. US,20140016472,2014.   
[10] Wolfram S.Theory and applications of celular automata: including selected papers 1983-1986 [J].IEEE Trans on Computers,1986,43(12): 1346-1357.   
[11]胡清梅，方卫宁，郭北苑，等．行人运动建模技术综述[J].计算机应 用研究,2009,26 (2): 444-447.(Hu Qingmei,Fang Weining,Guo Beiyuan, et al. Review on pedestrian simulation model[J]. Application Research of Computers,2009,26 (02): 444-447.)   
[12] Chai C,Diew W Y. Comparison of Two simulation approaches to safety assessment: cellular automata and SSAM [J].Journal of Transportation Engineering,2015,141(6): 05015002.   
[13]安旭，赵靖，马晓旦，等．基于元胞自动机模型的交织区车道分配问题 分析[J/OL].计算机应用研究,2019,36(6):1-7[2018-05-03].http://kns. cnki. net/kcms/detail/51.1196.TP.20180408.1050.046.html.(An xu, Zhao Jing,Ma Xiaodan,et al.Analysis of lane allocation problem in weaving area based on cellular automaton model[J]. Application Research of Computers，2019，36(6):1-7[2018-05-03]. htp://kns.cnki. net/kcms/detail/51.1196.TP.20180408.1050.046. html.）   
[14] Belz N P,Aultman-Hall L,Montague J. Influence of priority taking and abstaining at single-lane roundaboutsusing cellularautomata[J]. Transportation Research Part C Emerging Technologies，2O16,69: 134-149.   
[15]Liu Yingdong,Niu Hui-min,Wang Jianqiang. Celular Automata Model of Short-link Grouped Intersections [J]. Journal of Highway & Transportation Research & Development,,2015,32(02):140-146+153.   
[16] Gaurav,Pandey,Ramachandra,et al.Modeling vehicular interactions for heterogeneous traffic flow using cellular automata with position preference [J].Journal of Modern Transportation,2017,25 (3): 163-177.   
[17]张凤琴，王梦非，管桦，等．城市交通网元胞自动机全局流量预测方法 [J]．计算机应用研究，2017，34（1):42-45.(ZhangFengqin，Wang Mengfei,Guan Hua,et al.Prediction method of global transportation network flow withcelllar automata [J].Application Research of Computers,2017,34(1): 42-45.)   
[18] Wu Kefei, Kong Linghang,Lu Muren. The study of a cellular automaton NS and WWH mixed model for traffc flow on a two-lane roadway [J]. ActaPhysica Sinica,2006,55(12):6275-6280.   
[19] Zhang Bo,Zhao Huiying.Parameter Correlation Analysis and Research on Single-Lane Celular Automaton NS Model [J].Journal of Kunming University of Science & Technology,2016,41 (04): 45-51.   
[20] Linesch Nicholas J.,D'Souza Raissa M.Periodic states,local effects and coexistence in the BML traffic jam model [J].Physica A Statistical Mechanics & Its Applications,2012,387 (24): 6170-6176.   
[21] Daniel Lawrence Lu. Generalization of elementary cellular automata to a higher dimension family including the BML trafc model [J].Physics, 2015. 1 (4): 1-8.   
[22] Hu Wenbin,Wang Huan,Qiu Zhenyu,et al.A quantum particle swarm optimization driven urban trafic light scheduling model [J].Neural Computing & Applications,2016: 1-11.   
[23] Kuang Hua, Zhang Guoxin,Li Xingli,et al.Effect of slow-to-start in the extended BML model with four-directional traffic [J].Physics Letters A, 2014,378 (21): 1455-1460.   
[24] Sun Duo,Wang Bing Hong.Effects of traffic lights period and application of mean-field theory in two dimension traffic flow [J].Journal of Jilin University,2009,39:80-82.   
[25] Qian Xinjing,Xu Yanbing,Gu Guoqing.Green wave model for two dimensional cellular automaton traffic flow and traffc lights effects [J]. Journal of University of Shanghai Forence & Technology，2OO0(03): 207-211.   
[26] Jiang Rui,Chen Jinyong，Ding Zhongjun,et al.Network operation reliability in a Manhattan-like urban system with adaptive trafic lights [J]. Transportation Research Part C Emerging Technologies，2016，69: 527-547.   
[27]敖大成．曼哈顿型城市道路网络：路径选择和自适应交通灯的影响 [D].合肥：中国科学技术大学,2014.(Ao Dacheng.The effect of routing andadaptive traffic light strategy ina Manhattan-like urban system [D]. HeFei: University of Science and Technology of China,2014.)