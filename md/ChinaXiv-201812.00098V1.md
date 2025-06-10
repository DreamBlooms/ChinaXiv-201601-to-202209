# 基于雾计算和强化学习的交通灯智能协同控制研究

安萌萌，樊秀梅，蔡含宇(西安理工大学自动化与信息工程学院，西安 710048)

摘要：智能交通系统(ITS)的目标是从根本上解决道路安全、车辆拥挤、环境污染等对城市造成的影响，交叉路口是道路和车辆的交汇处，也是交通拥堵现象最严重的地方。针对路口交通拥堵现象，结合雾计算和强化学习理论，提出了一种FRTL(fog reinforcement traffclight)交通灯控制模型，该模型根据实时的交通流信息进行交通灯智能协同控制。雾节点将收集到的实时交通流信息上传到雾服务器，雾服务器在雾平台实现信息共享，雾平台结合处理后的共享数据和Q学习制定交通灯控制算法。算法利用检测到的实时交通数据计算出合适的交通灯配时方案，最终应用到交通灯上。仿真结果表明，与传统的分时段控制方式和主干道控制方式(ATL)相比，FRTL控制方法提高了路口的吞吐量，减少了车辆平均等待时间，达到了合理调控红绿灯时间、缓解交通拥堵的目标。

关键词：十字路口；交通灯；雾计算；强化学习；Q学习中图分类号：TP273.1 doi:10.19734/j.issn.1001-3695.2018.08.0543

# Research on intelligent coordinated control of traffic light based on fog computing and reinforcement learning

An Mengmeng, Fan Xiumei†, Cai Hanyu (Dept.of Automation & Information Engineering,Xi'an University of Technology,Xi'an 710048,China)

Abstract:Thegoal of the Intelligent Transportation System(ITS）isto fundamentallysolve theimpactof road safety, vehicle congestion,and environmentalpolltiononcities.Andtheintersection serves as the intersectionofurbanroads and vehicles,ofcourse,has become the most prominent problemof trafic problemsand contradictions.Forintersection traffic congestion phenomenon, this paper combines fog computing and reinforcement learning theory,and proposes aFRTL(Fog ReinforcementTrafic Light)trafficlightcontrol model.The model performs intellgentcoordinatedcontroloftraffic lights basedonreal-time traffc flow information.Thefog node uploads thecollctedreal-time trafficflow informationto the fog server,and the fogserverrealizes informationsharing onthe fog platform,andthe fog platform combines the processed shared dataandQlearning toformulateatrafic lightcontrolalgorithm.Thealgorithmuses the detectedreal-time trafic datato calculate a suitable traffc light timing scheme,which is finally apliedtothe traffic light.The simulationresults show that compared with thetraditional time-phasecontrol methodand the main road control method (ATL）,the FRTL control method improves thethroughputof intersections,reduces theaverage waitingtimeofvehicles,andachieves thegoal of properly regulating trafic lights and alleviating traffic congestion.

Key words: intersection; traffic lights; fog computing; reinforcement learning; Q-learning

# 0 引言

智能交通系统（intelligent transportation system，ITS）目标是通过人、车、路的密切配合，缓解交通堵塞、降低交通事故发生率、减轻环境污染，而交通灯可以保证整个路网车辆通行的有序和顺畅。但是，由于道路上的行驶车流量每年都在大幅增长，传统的交通灯控制方式已不能根据路口的实时车流量达到动态调整交通灯的目的，导致路口拥堵。因此，构建自适应交通控制系统，提高十字路口的通行能力和服务质量是目前智慧交通领域一个重要的关键问题。

为了支持更多车辆顺利行驶、实现更好的通信效率，解决传统车载网络在延迟、位置感知以及实时响应方面的局限性，本文在集成雾计算[I]和VANET[2]的雾平台上进行研究，认为车联网中的车辆是智能车辆，具备一定的计算和通信能力，部署在网络边缘的雾节点（比如可以布局在已有的路边设施或十字路口交通灯上）可以实时有效地收集、存储、处理、上传和交互交通数据。把收集的数据通过雾服务器分析和计算，然后结合强化学习[3]中Q学习[4]制定的交通灯控制算法，得到相位的绿灯时间，达到根据实时交通流动态调控红绿灯时间的目的。

# 1 相关研究

目前，交通灯常用的控制方式主要有定时控制[51、感应控制[6、自适应控制[7这三种类型。随着车辆的增多，传统的交通灯控制方式（定时控制和感应控制）不能根据实时交通流调整交通灯，已经不能满足当前的交通需求，而自适应控制方法的灵活性、可用性和最优性，可以有效地缓解交通拥堵，所以采用自适应控制方法调控城市交通灯已成为一种主流方案。

目前，国外已经实施的自适应控制交通系统主要有

RHODES(美国)、SCOOT(英国)、SCATS(澳大利亚)等系统方案。RHODES系统在没有考虑其他交通流造成的延误的前提下，该系统可以根据交通流的随机变化特征通过预测模型提前获取交通流的必要状态信息[8]。SCOOT系统采用的方法是小步长渐进寻优，根据交通流量适量调整配时参数，可以在短期内适应交通流量的变化[9]。但是SCOOT系统需要对绿信比（Split，交通灯一个周期时间内可用于车辆行驶的比例时间)进行调整，不能及时响应每个周期的交通需求。SCATS系统采用分层控制的方法，主要根据车辆饱和度与综合量分别优化信号周期、相位差以及绿信比。SCATS系统的不足之处是配时方案有限、缺乏灵活性[10]。

整个交通路网是一个大空间、复杂的非线性系统，而强 化学习在非线性系统中具备良好的学习性能，所以近年来其 在交通灯控制中得到了一定应用。

文献[11]介绍了一种基于强化学习的多智能体系统的交通信号调度方案，以5个十字路口为研究对象，研究目标是最小化十字路口的车辆排队延迟时间。研究结果表明，结合强化学习的交通信号调度方案降低了排队延迟。文献[12]把交通自适应控制看做马尔可夫游戏问题，每个路口的交通信号灯都和相邻路口的交通信号灯相互协调，可以提高绿灯时间利用率。但是该方案不能及时得到交通流信息，数据传送延迟高，不能实时调控交通灯。文献[13]针对主干道提出的ATL交通灯调节方案虽然能缓解主干道路的交通拥堵，但是它弱化了非主干道路交通流对主干道路交通流的影响。

基于上述分析，考虑到十字路口的车辆数目是随机变化的，所以需要实时获取交通流信息，动态调整交通信号灯。雾计算具有低延迟、实时响应的优点，可以实时收集交通流信息；与动态环境交互信息、具备自主学习能力、自适应性强是强化学习的三大特点。因此本文针对多路口提出基于雾计算和强化学习的智能交通灯协同控制研究，根据实时交通状态信息来调整交通信号灯，达到缓解交通拥堵的目标。

# 2 相关技术研究背景

本研究中用到了雾计算和强化学习，简单分析介绍如下。

# 2.1雾计算

与云计算不同的是，雾计算是一种分布式计算，它把云计算的计算模式扩展到网络边缘[14]，其特点如下：a）低延时、位置感知；b）地理分布广泛、移动性强；c）包含大量节点以及传感器网络；d）可以实时交互信息、在线分析并与云相互作用。

近几年基于雾计算的热点研究内容主要有智慧城市、智能管理能源和工业无线传感器网络等。

雾计算的这些特性在智慧城市的一些案例研究中得到了充分的体现。例如，智能农业[15]作为智慧城市的一部分，雾计算通过智能传感器节点监控植物生长和气候条件，在农作物种植方面发挥着重要作用。此外，水资源管理[16]、温室气体控制和零售自动化是雾计算在智慧城市中广泛应用的一些案例。

平衡各个领域之间的能源消耗对是非常重要的。通过雾计算平台对建筑物和各种操作领域进行智能管理能源[17]，例如家庭或微电网。通过监视和计量每个设备的功耗来进行智能管理能源，例如家庭功耗；通过有效控制设备来管理能耗，例如智能照明、电动车充电器[18]。

大规模工业应用通常与机器人、固定装置、机床、工件和化学反应等有关，即工业 $4 . 0 ^ { [ 1 9 ] }$ 。具有工业无线传感器网络（industrial wireless sensor networks,IWSN）的智能工厂在工厂自动化、生产以及制造方面发挥着非常重要的作用。把雾计算应用到IWSN中，通过自适应操作平台（adaptiveoperationsplatform,AOP）来提高故障模型的有效性[20]。AOP是通过具有资源的雾基础设施、端到端服务来提供资产管理、生产和制造功能的。

# 2.2强化学习

强化学习是一种试错性学习，与监督学习不同的是，它不会告诉agent如何产生正确动作，而是由环境反馈的奖励信号来评价agent产生动作的好坏[21]。图1是强化学习的框架图。

![](images/3c549a26e38e1d05d97caca93872dca84f9343359a7c0b45defdc65f51c31bcf.jpg)  
图1强化学习框架  
Fig.1Reinforcement learning framework

强化学习的核心思想是根据从环境中感知到的不确定信息来学习最优策略，以后始终按照该策略对某一环境执行动作，通过改变环境的状态获取环境反馈的奖励信号，然后通过这个奖励信号来强化某一环境状态下和最佳动作之间的映射关系[22]。

在Q学习算法中，把在某个环境状态下执行完某个动作得到的奖励用Q值表示，把这些Q值存放到一个表格中，称之为Q表(表1)。强化学习系统通过不断地学习优化该表，间接获得最优策略。

表1Q表Table1Qtable  

<html><body><table><tr><td>状态\行为</td><td>a1</td><td>a2</td><td></td><td>an</td></tr><tr><td>S1</td><td>Qij</td><td>Qij+1</td><td>：</td><td>Qi.j+n</td></tr><tr><td>S2</td><td>Qi+1.j</td><td>Qi+1.j+1</td><td>：</td><td>Qi+1.j+n</td></tr><tr><td></td><td>：</td><td></td><td>：</td><td>：</td></tr><tr><td>Sm</td><td>Qi+m.j</td><td>Qi+m.j+1</td><td></td><td>Qi+m.j+n</td></tr></table></body></html>

其中， $i = 1 , 2 , 3 , . . . , m$ ； $j = 1 , 2 , 3 , . . . , n$

强化学习系统要从探索环境的过程中获取有价值的经验来更新Q表，让Q值朝着最优的方向更新。更新规则见式(1)。

$\begin{array} { r } { \mathcal { Q } _ { t + 1 } \left( s _ { t } , a _ { t } \right) = \mathcal { Q } _ { t } \left( s _ { t } , a _ { t } \right) + \alpha _ { t } \left[ r _ { t } + \gamma \operatorname* { m a x } \mathcal { Q } _ { t + 1 } \left( s _ { t + 1 } , a _ { t + 1 } \right) - \mathcal { Q } _ { t } \left( s _ { t } , a _ { t } \right) \right] } \end{array}$ (1)其中： $s _ { t } \cdot \ a _ { t } \cdot \ r _ { t }$ 分别表示在时刻t下的环境状态、行为选择以及回报奖励。 $\alpha$ 是学习速率， $\alpha \in [ 0 , 1 ]$ 。当 $\alpha$ 等于0时，学习系统停止学习；当 $\alpha$ 接近1时，学习系统学习速度太快，容易造成不成熟收敛。 $\gamma$ 是折扣因子， $\gamma \in \left[ 0 , 1 \right]$ 。 $\gamma$ 越接近1,学习系统越注重长期收益；而 $\gamma$ 越趋向于0，系统就会越注重当前利益。

# 3 基于雾计算平台的交通灯管理系统

本研究中的雾平台集成了雾计算和VANET，把雾计算模式扩展到传统的车辆网络中，以实现更好更快的信息共享和通信效率，并在延迟、位置感知以及实时响应方面解决了传统车载网络中的局限性。

本文将雾平台架构设计为三部分，如图2所示。

a)数据生成层。本研究假定车联网中的所有车辆都是智能设备并且有能力收集有用的交通信息，所以把车联网作为数据生成层。由于智能车辆具有实时的计算、传递、通信和存储能力，所以在车联网中把智能车辆作为关键的数据生成器。智能车辆本身在进行实时决策时可以处理一些数据，而其他的数据将会被共享并上传到雾节点；车辆检测器也会把检测的车辆数目上传至雾节点。

b)雾层。雾节点部署在交叉路口的交通信号灯旁边，这些雾节点可以收集智能车辆和车辆检测器发送的数据，并把这些数据处理后上传给雾服务器。雾节点作为雾服务器和智能车辆之间的中间设备，不仅仅只是中继或者广播机构，它们还具有一定的计算能力，可以通过处理、存储数据并在雾层作出决定，从而降低延迟时间。

c)云层。由于雾服务器的存储容量有限，那么当雾层的数据量太多时，雾服务器就会把之前存储的数据上传到云服务器。云服务器会根据存储的数据进行计算分析，从整体角度作出最佳决策。最典型的例子就是监控、管理、控制道路交通基础设施，实现最佳的城市交通控制。

![](images/ce9dc8be55ba40d1c5b66a0edd81400be93c56229acdde9beaa00b3ff440747a.jpg)  
图2雾平台架构

在车联网环境下，雾平台收集、共享信息的具体机制大体分为四个步骤：

a)车辆和车辆检测器会把交通流信息发送至雾节点。当车辆驶入雾节点的通信范围内，它就可以和雾节点每10s进行一次通信（因为频繁地通信存在通信风暴的危险，并且极有可能丢失数据；考虑到行人通过十字路口的速度相对于车辆比较慢，所以设置为10s通信一次）。

b)雾节点之间相互通信。各个路口的雾节点不仅会把智能车辆和车辆检测器发送过来的交通信息上传至该区域的雾服务器，还会进行统计并分享给相邻路口的雾节点，通过交通灯控制机制（第4部分介绍）给出各个路口的交通灯红绿灯时间，进而协调本路口与相邻路口之间的交通流。

c)雾节点上传到雾服务器的交通信息就会成为历史信息，雾服务器会依据这些历史交通信息来预测交通流，以达到提高路网畅行的目的。

d)因为雾服务器的存储容量有限，所以它会把暂时不用的数据上传到云服务器。云服务器可以根据雾服务器上传的各个局部路网的交通信息进行全局优化，实现协调整个路网交通流的目的。图3是基于雾平台的交通灯管理控制系统示意图（黑色箭头表示车辆行驶方向，闪电形状的箭头表示云端、车辆、雾节点、雾服务器之间的通信链路）。

![](images/7b7bd302bca224673dbab71b0c64749e09b6bf9cd24f74b88029d674820ebd41.jpg)  
Fig.3Traffic light management system based on fog platform   
图3基于雾平台的交通灯管理系统

综上所述，把雾计算应用在交通信号灯控制中主要有三大好处：a）可以降低车辆应用与交通灯的响应时间；b）在把数据上传到雾服务器之前雾节点可以预处理收集的数据，减少数据量，可以加快通信速度；c）部分数据可以存放到雾服务器，从而减轻云服务器的存储负担。

# 4基于强化学习中Q学习算法的交通灯控制机制

本文采用强化学习中的Q学习算法用于交通灯控制，并制定了交通灯控制算法，该算法在FRTL交通灯控制模型（该部分在5.1节介绍）中的交通灯控制模块中实现。算法中把交通流量作为状态，绿灯时间作为动作。该算法大致分为以下几个步骤：

a）初始化Q表为任意值;b）把检测到的当前交通状态作为初始状态s;c）根据Q值经验，在状态s下选择一个绿灯时间（动作）a;d）执行这个动作，更新交通状态，并观测奖励r;e）根据更新规则更新Q表；f）把新的交通状态 $s _ { t + 1 }$ 赋给状态 $s _ { t }$ ：g）重复步骤c）至步骤f)，直到Q值收敛。

本文是在只考虑直行车流量（东西方向、南北方向）的基础上进行研究的。如图4所示，一共有4个路口，每个路□都表示一个Agent，即Agent1，Agent2，Agent3，Agent4。路口之间的协调控制可以看做是一个马尔可夫决策过程，用${ \bf M } { = } ( { \bf S } , { \bf A } , { \bf R } )$ 表示，S代表路口的交通状态，A代表交通控制行为(绿灯时间)，R代表执行完交通控制行为得到的回报奖励。

![](images/946cc929c86b5f45262139d1f7f9fbc91bc5b3d90d3bd7b0108641bfb972838a.jpg)  
Fig.2Architecture of fog platform   
图4四路口交通控制示意图  
Fig.4Schematic diagram of traffic control at four intersections

a）交通状态。在路口等待通行的车辆数加上新到达的车辆数作为交通状态。每个Agent都会收到雾节点传过来的实时交通信息，发送过来的交通信息包括当前等候在路口的车辆数量和新到达的车辆数量。新到达的车辆数目由雾服务器给出，通过计算相邻路口当前时刻的前3次车辆数目平均值得到。本文用stopVehicle1、stopVehicle2、stopVehicle3、stopVehicle4分别表示等候在路口1(Agent1)、路口2(Agent2)、路口3(Agent3)、路口4(Agent4)的车辆数目，本文用newVehicle1，newVehicle2，newVehicle3，newVehicle4分别表示路口1、路口2、路口3、路口4新到达的车辆。交通状态用 $S = ( s t o p V e h i c l e , n e w V e h i c l e )$ 来表示。比如，对于Agent1 有$S 1 = ( 1 0 , 6 )$ ，表示路口1当前有10辆车在等红绿灯，有6辆车是新到达的车辆。

b）交通控制行为。交通灯控制行为一共有三种，即

$\mathbf { a } = \left\{ { \begin{array} { l } { 1 } \\ { 2 } \\ { 1 } \end{array} } \right.$ 绿灯时间保持不变（204号 增加绿灯时间[3减少绿灯时间

当路口拥堵时，并且绿灯时间已达到最大绿灯时间（120s)，此时交通控制行为是1（即绿灯时间保持不变)；当绿灯时间不能让等候在路口的全部车辆通过，并且绿灯时间没有达到120s，此时就要增加绿灯时间；当等候的全部车辆都能通过路口时，而且绿灯时间还有剩余，此时就要减少绿灯时间。那么，每个agent都有三个行为选择，比如对于agent1有 $_ { \mathrm { A 1 = } ( 1 , 2 , 3 ) }$ 。

c）回报奖励。在交通信号灯控制中，agent根据不同的交通状况做出交通控制行为，执行这个行为并回报给 agent一个奖励。对于Agenti（其中 $i = 1 , 2 , 3 , 4 )$ ，主要有五种交通状态：有 $S _ { i } = s t o p V e h i c l e , n e w V e h i c l e$ ，(a) $( s t o p V e h i c l e , 0 )  ( s t o p V e h i c l e - 1 0 , 0 )$ ，表示等候在路口的车辆中有小于等于10辆车通过了路口，路口没有新到达的车辆。(b) $( s t o p V e h i c l e , 0 )  ( s t o p V e h i c l e - 1 1 , 0 )$ ，表示等候在路口的车辆中有大于等于11辆车通过了路口，路口没有新到达的车辆。(c) $( 0 , 0 )  ( 0 , n e w V e h i c l e + 5 )$ ，表示路口没有等待通行的车辆，但是有小于等于5辆新到达的车辆通过了路口。(d) $( 0 , 0 )  ( 0 , n e w V e h i c l e + 6 )$ ，表示路口没有等候的车辆，但是有大于等于6辆新到达的车辆通过了路口。(e) $( s t o p V e h i c l e , n e w V e h i c l e )  ( s t o p V e h i c l e - 1 1 , n e w V e h i c l e + 6 )$ 表示等候在路口的车辆中有大于等于11辆车通过了路口，并且有大于等于6辆新到达的车通过了路口。

回报奖励取决于当前交通状态到下一时刻交通状态的转换，这样进行计算：

# 5 FRTL交通灯控制模型

# 5.1模型设计

时延低、有位置感知能力是雾计算的优点，与环境交互信息、自适应强是强化学习的优点。所以，本文在雾计算平台上，结合强化学习，提出FRTL交通灯控制模型，如图5所示。

a)交通信息采集模块。该模块的功能是收集交通流信息，交通流信息主要来自智能车辆和车辆检测器。采集的交通信息包括当前等候在路口的车辆数目、车辆在雾节点范围内的行驶速度、当前交通灯的状态等，并且采集模块把采集的交通信息传送给雾服务器模块。

b)雾节点。处理信息采集模块传送过来的交通信息是在雾节点中进行的，通过分析和处理收集的交通信息，交通灯控制模块把处理后的数据应用到Q学习制定的交通灯控制算法中，计算得到每个相位的合理绿灯时间。而且雾节点会把接收到的交通信息进行汇总，作为统计交通信息上传给雾服务器。

c)雾服务器。雾服务器通过分析、计算雾节点上传的统计交通信息来进行局部交通控制。雾服务器在进行局部协调交通流时，不仅考虑实时交通流量，还会考虑历史交通信息来预测交通流。本文第四部分的交通灯控制机制中的新到达的车辆就是雾服务器根据历史交通信息计算得到的。

d)云服务器。云服务器通过大数据分析雾服务器上传的数据来挖掘交通信息，进行全局交通控制。云服务器还可以根据大量的交通信息为智能车辆提供其他服务，比如导航服务，以帮助控制交通流量。

![](images/e9fa419c3bd69c46cbb6200dde321e384be37d96f2d4d5d447c968bc38c89495.jpg)  
图5FRTL交通灯控制模型  
Fig.5FRTL traffic light control model

# 5.2交通流评估参数

交通灯在交通流管理中起着至关重要的作用，合理分配交通信号时间可以保证车辆尽可能快速地通过路口，减少路□滞留车辆。本文用到的交通流评估参数有路口车辆吞吐量、口十寸陕的而、迫路论怕反。

a）车辆吞吐量。通过十字路口的车辆数。这个指标通常用于衡量道路的平顺程度及其交通流量。吞吐量越大，表示路口越顺畅。b）车辆等候时间。车辆在十字路口等待通行的时间。车辆等候时间越高表示车辆通过路口的速度越低，路口就越拥堵[23]。c）车辆饱和度。车辆饱和度= 最大通行能力，它是衡量道 最大交通量路服务水平的一个重要性能指标。根据车辆饱和度值把道路服务水平分为四个等级。(a) $0 \leq$ 车辆饱和度 $< 0 . 6$ ，就表示道路通畅，服务水平好；(b) $0 . 6 \leq$ 车辆饱和度 $< 0 . 8$ ，就表示道路稍微拥堵，服务水平较高；(c) $0 . 8 \leq$ 车辆饱和度 $^ { < 1 }$ ，就表示明道路拥堵，服务水平较差；(d)饱和度 $\geq 1 . 0$ ，就表示道路出现严重拥堵，服务水平极差。

# 6 实验仿真

PTV-VISSIM是一种微观的、基于时间间隔以及驾驶行为的交通仿真建模工具，它可以分析各种交通条件下（比如交通信号、公交站点等）城市路网交通的运行状况，能有效评价交通方案[24]。VISSIM不仅可以生成在线的交通运行状况，还可以离线统计各种数据，比如行程时间、排队长度等[25]。所以，本研究采用VISSIM进行实验仿真。

本文把VISSIM离线输出的统计数据（例如车辆排队长度、十字路口吞吐量）作为MATLAB的输入，进行实验仿真。在VISSIM中设置交通规则为右行交通、仿真时间 $3 6 0 0 \mathrm { s }$ ，仿真精度是10个时间步长、每个进口道的饱和车流量是2000veh/h、绿灯最大时间为90s、十字路口之间的距离是 $5 0 0 \mathrm { ~ m ~ }$ 。设置强化学习系统的学习速率 $\alpha$ 为0.6、折扣因子／为0.5。为了验证FRTL交通灯控制模型的有效性，本文用交通灯分时段控制方式和ATL控制方式[13]作对比。

每隔5个时间步（每个时间步长是10s）对交通流量做一次计算，运行了360个时间步长（3600s）后，得到协调路口的交通流吞吐量（以路口1为例)。从图6可以看到，与分时段控制方式和ATL控制方式相比，在FRTL交通灯控制方式下每秒通过十字路口的车辆数目多。

![](images/1a74a14cf3aa980b1f5d19ce3b360c6f59c8022141e6618a5f403f04a7e942be.jpg)  
图6路口吞吐量示意图

每个时间步都会获得路口的车辆等候时间，运行360个时间步长以后，得到各个路口的车辆总等候时间，根据总等候时间来计算每个路口的车辆平均总等候时间。图7是每个路口的车辆平均总等候时间示意图。从图中可以得到，FRTL交通灯控制方式下的车辆平均总等候时间分别比分时段控制方式和ATL控制方式平均低6.4s、3.1s。

![](images/ec85e5926c464af466f6784ab8d9301c6dfcbcafe1a3b3ed1efa477699c84e52.jpg)  
Fig.6Schematic diagram of intersection throughput

图8是分时段控制方式、ATL控制方式和FRTL控制方式这三种控制方式下的车辆饱和度示意图，图中的两条黑色粗实线表示车辆饱和度分界值。可以从图中看到,分时段控制方式在路口车辆数目小于等于800辆时，道路交通顺畅，是一级服务水平；ATL控制方式在路口车辆数目小于等于1000辆时是一级服务水平；而本文提出的FRTL控制方式在路口车辆数目达到1100辆时还可以保持道路交通顺畅。通过比较可以得到，FRTL控制方式下的车辆饱和度小，能保持道路畅通，提供较好的道路服务水平。

本文把采集的西安市咸宁西路与兴庆路的十字路口一个小时的交通流信息（包括等待红绿灯的车辆数目以及红绿灯时间）分别应用到FRTL、ATL交通灯控制方式中，仿真结果如图9所示。现阶段西安市咸宁西路与兴庆路十字路口的交通灯绿灯时间是45s、73s往复循环，即使路口没有等候车辆，也要执行这么长时间的绿灯时间，造成绿灯时间浪费。在不考虑车辆启动延迟的情况下，实际测得一辆车通过路口的平均时间是2s。从图9中可以看到，当路口有10辆等待车辆时，FRTL控制方式给出20s绿灯时间让车辆通过路口；ATL控制方式给出15s的绿灯时间，从而会导致路口有滞留车辆，这是由于ATL控制方式的实时性低导致的。绿灯时间最大不能超过最大绿灯时间（ $1 2 0 \mathrm { ~ s ~ } )$ ，当路口车辆等待数目达到60辆车时，FRTL控制方式下达到最大路灯时间；而ATL控制方式在车辆数目达到70辆车时才达到最大绿灯时间。

![](images/aa99f7629b113d9171948424e7dccc6c2d1c347c41adeb263fd6b4d749e7670f.jpg)  
图8车辆饱和度示意图

![](images/171158342085ef36db4393f29f53e8191a46d2c4924814e90c8c8673e238b07b.jpg)  
ig.7Schematic diagram of the average waiting time of vehicles   
Fig.8Schematic diagram of vehicle saturation   
图9交通灯绿灯时间示意图(南北方向）  
Fig.9Schematic diagram of traffic light green light time(north-sout direction)

把西安市咸宁西路与兴庆路的十字路口一个小时的交通流信息分别应用到三种交通灯控制方式中，得到路口的滞留车辆数。如图10所示，当等待车辆大于60辆时，FRTL交通灯控制方式下才会有滞留车辆；ATL交通灯控制方式由于实时性较低，每次都会有几辆滞留车辆；由于分时段控制方式下绿灯时间是固定的，所以当等待车辆为30辆时就会有滞留车辆。

![](images/bf5c14a4c3a3dbcd6f0f16e6291b23c66e481b3b389dd50adb1689e97e24213a.jpg)  
图7车辆平均总等候时间示意图  
图10十字路口滞留车辆数示意图（东西方向）  
Fig.1OSchematic diagram of the number of vehicles stranded at the intersection (east-west direction)

# 7 结束语

雾计算具有低延时、实时交互信息的特点，强化学习系统通过自身学习的经验，可以根据雾平台收集的实时交通信息调控交通灯，具有较强的自适应性。所以本文结合雾计算和强化学习，提出了FRTL交通灯控制模型，以达到降低车辆等候时间、避免绿灯时间的浪费和缓解交通拥堵的目的。在该模型中，雾节点把收集的实时交通流信息上传到雾服务器，多个雾服务器会把信息共享到雾平台，交通灯控制模块结合处理后的共享数据和Q学习制定交通灯控制算法计算出红绿灯时间。

与分时段交通灯控制方式和ATL控制方式不同，本文提出的FRTL交通灯控制模型考虑了相邻路口的情况，车辆、交通信号灯以及道路基础设施通过雾平台共享实时交通信息，交通灯控制模块的交通灯控制机制可以根据实时交通信息制定相应的交通信号灯配时方案。从分析的仿真结果可以得出：FRTL控制方式能够有效缓解交通拥堵、提高道路服务水平。

本文提出的交通灯控制方式是在道路通行顺畅没有交通事故发生的前提下进行的。目前研究的是在局部路网中且只有直行车辆，但是现实中存在拐弯车辆且存在发生交通事故的可能性，所以在后续的研究中，将会考虑拐弯车辆和处理交通事故的故障模型，通过局部路网最优做到全局路网交通最优，缓解整个路网的交通拥堵，提高道路利用率。

# 参考文献：

[1]方巍．从云计算到雾计算的范式转变[J]．南京信息工程大学学报, 2016,8(5): 404-414.(Fang Wei. Paradigm shift from cloud computing to fog computing [J].(Journal of Nanjing University of Information Science & Technology,2016,8(5): 404-414.)   
[2]Oulhaci T,Omar M,Harzine F,et al.Secure and distributed certification system architecture for safety message authentication in VANET[J]. Telecommunication Systems,2017,64(4): 679-694.   
[3]Prabuchandran K J,Hemanth K A N,Bhatnagar S.Multi-agent sreinforcement learning for traficsignal control [C]//Procof International IEEE Conference on Intelligent Transportation Systems. Piscataway,NJ:IEEE Press,2014:2529-2534.   
[4]Khamis M A,Gomaa W. Adaptive multi-objective reinforcement learning with hybrid exploration for trafic signal control based on cooperative multi-agent framework [J].Engineering Applications of Artificial Intelligence,2014,29(3):134-151.   
[5]Tu Xianku.The research of intelligent timing control system for urban traffic signal light [C]//Proc of International Conference on Consumer Electronics，Communications and Networks.Piscataway,NJ:IEEE Press,2011: 5425-5428.   
[6]林晓辉．基于全感应控制的交叉口信号控制方法与模型[J].现代 交通技术,2015,12(1): 44-46.(Lin Xiaohui.Intersection signal control method and model based on full induction control [J].Modern Transportation Technology,2015,12(1): 44-46.)   
[7]Li Nan,Zhao Guangzhou.Adaptive signal control for urban traffic network gridlock [C]//Proc of International Conference on Control. Piscataway,NJ:IEEE Press,2O16:1-6.   
[8]Zhao Yi,Tian Zong.An Overview of the Usage of adaptive signal control system in the United States of America [J].Applied Mechanics & Materials,2012,178-181:2591-2598.   
[9]王海忠，于泉，顾九春，等.城市交通信号控制系统研究(二)[J].交 通科技,2OO4(6): 94-9/.(Wang Haizhong,Yu Quan,Gu Jiuchun,et al. Research on urban traffic signal control system(2）[J].Transport Technology Journal,2004(6): 94-97.）   
[10] Pascale A,Lam H T,Nair R. Characterization of network trafic processes under adaptive trafc control systems[J]. Transportation Research Part C,2015,59(3): 340-357.   
[11] Arel I,Liu Chengxi, Urbanik T,et al.Reinforcement learning-based multi-agent system for network trafic signal control[J]. Intellient Transport Systems Iet,2010,4(2): 128-135.   
[12] El-Tantawy S,Abdulhai B,Abdelgawad H.Multiagent reinforcement learning for integrated network of adaptive traffic signal controllers (MARLIN-ATSC): methodologyand large-scaleapplicationon downtown toronto [J]．IEEE Trans on Intelligent Transportation Systems,2013,14(3): 1140-1150.   
[13] Younes M B，Boukerche A.Intelligent traffic light controlling algorithms using vehicular networks [J].IEEE Trans on Vehicular Technology,2016,65(8): 5887-5899.   
[14] Alrawais A,Alhothaily A,Hu Chunqiang,et al. Fog computing for the Internet of things:security and privacy issues [J]. IEEE Internet Computing,2017,21 (2): 34-42.   
[15] Perera C,Jayaraman P P,Zaslavsky A,et al.Sensor discovery and configuration framework for the Internet of Things paradigm [C]// Internet of Things.Piscataway,NJ: IEEE Press,2013: 94-99.   
[16] Perera C, Zaslavsky A, Georgakopoulos D,et al. Sensing as a service model for smart cities supported by Internet of Things [J].European Trans on Telecommunications,2014,25(1): 81-93.   
[17] Vatanparvar K, Faruque M A A. Energy management as a service over fog computing platform [C]//Proc of the 6th ACM/IEEE International Conference on Cyber-Physical Systems.New YorkACM Press 2015: 248-249.   
[18] Faruque M A A，Dalloro L，Zhou Siyuan，et al. Managing residential-level EV charging using network-as-automation platform (NAP）technology[C]/ProcofElectricVehicleConference. Piscataway,NJ: IEEE Press,2012: 1-6.   
[19] Sasajima H, Ishikuma T, Hayashi H. Future IIOT in process automation Latest trends of standardization in industrial automation,IEC//TC65 [C]// Society of Instrument and Control Engineers of Japan.2015: 963-967.   
[20] Gazis V,Leonardi A,Mathioudakis K,et al.Components of fog computing in an industrial internet of things context [Cl//Proc of IEEE International Conference on Sensing,Communication,and Networking. Piscataway,NJ: IEEE Press,2015:1-6.   
[21]高阳，陈世福，陆鑫．强化学习研究综述[J]．自动化学报，2004，30 (1): 86-1Oo.(Gao Yang,Chen Shifu,Lu Xin.A review of reinforcement learning research [J].ACTA Automatica Sinica,2004,30(1): 86-100.)   
[22] Sutton R S,Barto A G. Reinforcement learning: an introduction [J]. IEEE Trans on Neural Networks,1998,9(5): 195-220.   
[23]Yit Kwong Chin,Lai Kuan Le,BolongN,etal.ExploringQ-Leaing Optimization in Traffic Signal Timing Plan Management[C]//Proc of International Conference on Computational Intelligence.Piscataway,NJ: IEEE Press,2011: 269-274.   
[24]郑晓鸿.VISSIM 仿真技术在交通领域中的应用[J].中小企业管理与 科技,2017(7):147-148.(Zheng Xiaohong.Application of VISSIM simulation technology in the field of transportation [J].Management & Technology of SME,2017(7): 147-148.)   
551钩凇信六习十姓扣动在と行油察运动过程建描住吉

[D].南京：南京理工大学，2017.(Bao Yiting.Modeling and simulation of motion process of right-round motor vehicleand pedestrian conflict at signalized intersection [D]. Nanjing:Nanjing University of Technology,2017.)