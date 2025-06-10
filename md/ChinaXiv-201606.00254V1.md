# 以拥塞控制为导向的WMSN多路径路由协议研究

付常雷

(中国科学院文献情报中心，北京1000190)（通信邮箱：fuchl@mail.las.ac.cn）

摘要：多媒体无线传感器网络所具有数据量大、能耗高等特性易导致网络拥塞，通过构建多路径,节点级拥塞检测与流量调度机制，实现拥塞节点调控和拥塞缓解，从而提出了带有拥塞控制机制的多路径路由协议。给出了实际的报文封装、协议时序交互，并做了TinyOS下代码实现，灌装在实际节点中，在北京市昌平区前葡沟村现代农业示范基地实测环境下运行正常。理论仿真也验证了所提机制可提高多媒体数据传输能量高效性，延长网络生存时间。

关键字：无线传感器网络；多媒体数据；多路径；路由协议；拥塞控制中图法分类号：TN915.04文献标识码：A

# Research on Congestion Control Oriented Multipath Routing

# Protocol for WMSN

FU ChangLei

(National ScienceLibrary,BeijinglOoi9o,China)

（fuchl@ mail.las.ac.cn)

【ABSTRACT】Wireless Multimedia Sensor Networks(WMSN) have the characteristics of large data transmission rates,high energy consumption，which nodes are more likely to get into congestion trouble.By multipath constructing,congestion detecting and load balance mechanism,a congestion control oriented multipath protocol was proposed to achieve the goal of node control and congestion relief.The actual message structure and packets interaction were presented.Also the nesC code in TinyOS was compiled and downloaded to actual IRIS nodes. The system tests running the code have a good performance at Modern agricultural demonstration base in QianLinGou Village,Changping District， Beijing. Simulation results show that this scheme achieves good performance in energy efficiency and increases network life in multimedia data transmission.

【KEY WORDs】 WSN; Multimedia data; Multipath; Routing Protocol; Congestion Control

# 1引言

无线传感器网络(Wireless Sensor Networks，WSN)以传输温度、湿度、二氧化氮含量等离散数据为主，此类数据具有单次传输数据量小，传输频率低，传输持续时间短等特点。随着软硬件发展以及对传感网的更高需求，以传输音频、视频、图像为主的多媒体无线传感器网络(Wireless Multimedia Sensor Networks，WMSN)应运而生。无线传感器网络具有能量有限、无线链路受环境影响较大等特点，而多媒体无线网络在此基础上又增加了数据量大、数据实时性要求较高等特性，因此WMSN中对路由协议的健壮性和拥塞控制机制的设计提出更高要求。

# 2相关研究

无线传感器网络中多路径路由机制可有效解决网络中大数据量并发传输的问题。文献[]在提出多路径缠绕模型，试图降低多路径构建过程能量消耗。文献[2提出不相关多路径构建机制，减少路由发现次数，增强路由的稳定性。文献提出多路径流量分析模型，通过流量分流策略提高网络吞吐量及健壮性。多路径路由机制相比单路径模型可有效提高网络负载能力和网络路由健壮性。

WMSN 网络作为传统传感器网络的拓展，除具有WSN所具有的特点外，其大数据流量短时间内竞争信道，导致报文冲突加剧，缓冲区堆积加速，而更易产生网络拥塞[4]。拥塞控制机制分为拥塞检测，拥塞告知，拥塞缓解三个主要阶段[5]。高效拥塞检测机制是快速预测和发现网络拥塞的首要前提，检测方式有缓冲区占用率、信道负载、拥塞度、数据逼真度等。节点通过拥塞检测机制检测网络拥塞，将拥塞信息告知邻居节点、数据源节点或基站。文献提出CODA拥塞控制方案，使用能量高效的拥塞检测机制，通过背压反馈机制和转发速率调整有效缓解网络拥塞；文献提出区分数据类型使用不同路径传输，而通过调整采样周期方式实现拥塞缓解在很大程度上对数据精确性性上造成损失。图像网内压缩算法MCIC[8通过多节点协同压缩实现图像高质量压缩，但限制于传感网节点计算能力和能量有限性，大量数据计算无法保证节点及网络良好生命周期。目前已进行的拥塞机制研究中多针对传统传感器网络特点，而具有独自特性的WMSN网络中面对持续或突发的大数据流量，依赖单一路径和节点速率调整的拥塞控制机制无法保证良好网络服务。

# 3带有拥塞控制机制的多路径路由协议

针对多媒体无线传感器网络大数据流量、持续密集数据传输等特点提出采用按需路由策略，构建带有拥塞控制机制的多路径路由 DMRC(Disjoint Multipath Routing& Congestioncontrol)协议。多路径传输保证多媒体网络的带宽需求，节点局部检测拥塞，通过本地拥塞缓解策略并利用多路径实现流量调度，缓解节点和链路级网络拥塞。

# 3.1多路径路由构建

# 3.1.1多路径路由发现

图像数据源节点采集图像后触发路由发现，源节点向整个网络中洪泛路由请求报文REQ，报文结构如图1(a)所示：

![](images/bd5e94858d407002a7aa8e864c4e19afaefc7a14a501afd667ac4a486c3171fc.jpg)  
图1不同路由报文结构

中间节点接收REQ报文，检查此ID序列的REQ报文是否已经处理过，若首次接收（伪码1至5行）或重复接收相同ID报文但其 HopCount不大于当前记录中HopCount（伪码7至10 行)，则记录或更新 ID 对应HopCount，报文ParentID[HopCount]字段记录当前节点，转发REQ报文（伪码4至11行)；否则丢弃报文（伪码第12行)。报文处理伪码描述如下：

IFREQ[ID].Received $\scriptstyle = =$ FALSE THEN

2 REQ[ID].Received $\ c = ^ { \prime }$ TRUE;   
3 REQ[ID].HopCount $\ c =$ HopCount;//报文中跳数信息   
4 ParentID[HopCount] $\vDash$ TOS_NODE_ID;//当前节点号   
5 SendMsg (ID);   
6 ELSE THEN   
7 IF HopCount $\scriptstyle < =$ REQ[ID].HopCount THEN   
8 REQ[ID].HopCount $\ c =$ HopCount;   
9 ParentID[HopCount] $\vDash$ TOS_NODE_ID;   
10 SendMsg(ID);   
11 ELSE THEN   
12 DropMsg(ID);   
13 END   
14 END

# 3.2路由选择

目标节点Sink 最终会获取多条路由请求信息，从中选择最大不相交的多条路径[9]。本文采取的策略是将最先到达目标节点的路由定义为最小时延路径。当节点收到REQ时，目标节点记录整个路径信息，并沿此路径返回REP 报文，报文结构如图1(b)所示。在接收首个REQ报文后，目标节点仍会接收多个相同ID的REQ报文，通过处理一定时间段内的REQ报文获取更多的路由信息，此时选择与之前已经回复REP 的路由最大不相交且跳数最小的路由作为新路径。对满足条件的路由，目标节点通过选定路径回复REP报文。基站节点回复多个REP报文，源节点可获知多条可用路径。

与文献[9中多路径协议中路由机制不同，中继节点接收REQ、REP获取路径信息后，保存相应路径信息，且仅保存此路径中当前节点的下一跳节点信息，而传输感知数据时不再携带全部的路由信息，提高数据报文利用率。各中间节点中保存的路由信息表格式如表1所示：

表1节点中的路由信息表  

<html><body><table><tr><td>SourceID</td><td>RouteID</td><td>NextHop</td><td>Status</td></tr><tr><td>5</td><td>1</td><td>6</td><td>1</td></tr><tr><td>5</td><td>2</td><td>8</td><td>1</td></tr></table></body></html>

# 3.3多路径路由维护

在链路状态不稳定的无线网络中，一条选用的路径可能由于节点死亡、链路拥塞而导致中断，而路由维护是路由健壮性的重要表征。当下游节点连续未回复回馈信息时，则判定此链路中断，向此路径上游发送ERR报文，报文结构如图1(c)，源节点接收到ERR报文后获知链路失效，从本地路由信息中标记此条路由链路失效。源节点得知此链路拥塞，查询本地路由信息表，选择备用路由进行数据传输。

# 3.4基于多路径的拥塞控制策略

对于数据量大、数据实时性要求较高的多媒体无线传感器网络而言，节点或链路发生拥塞不可避免[4，本文在所设计的多路径基础之上引入拥塞控制机制，数据源节点通过功率调整初步控制拥塞，而持续的网络拥塞则触发多路径拥塞缓解机制。

# 3.4.1拥塞检测与告知

在拥塞检测阶段，目前成熟的检测机制为：节点局部使用基于缓冲区占用率机制作为节点拥塞检测手段。定义缓冲区大小为B，定义 ${ \bf b } _ { \bf k }$ 为第 $\mathbf { k }$ 个时间间隔结束时其缓冲区的占用，定义 $\scriptstyle \Delta \mathsf { b } = ( \mathsf { b } _ { \mathrm { k } } - \mathsf { b } _ { \mathrm { k } - 1 } )$ ，若 $ { \mathbf { b } } _ { \mathrm { k } } + \Delta  { \mathbf { b } } >  { \mathbf { B } }$ ，则判定第 $( \mathbf { k } { + } 1 )$ 个间隔将发生拥塞。拥塞告知方式采用拥塞告知报文，报文结构与ERR报文相同结构。当节点通过上述机制测到拥塞后，从拥塞节点反向至数据源节点发送拥塞告知报文。

# 3.4.2拥塞缓解

在数据源节点的拥塞避免策略，本文采用渐加倍减策略。数据源节点从开始发送数据时渐加(Additive Increase)发送速率，网络中任何节点检测到拥塞会触发拥塞告知报文至源节点后，源节点则采用倍减(Multiplicative Decrease)策略成倍减小数据发送速率，从源头减小数据流入网络的流量，来实现初步的拥塞源头流量控制。

在突发性网络流量、节点偶然性触发拥塞告知情况下，源节点发送速率调整在一定程度上缓解拥塞，此操作不会导致网络拓扑变化，防止网络路由震荡变化。而对于持续性的、高速率数据流的多媒体数据传输，基于源节点的速率控制策略不能为其高速网络传输提供保障。基于多路径的流量分流策略，建立在已完成的多路径路由之上，当源节点采用初步的流量限制策略无法缓解持续网络拥塞时，采用多路径分流策略来解决拥塞。前文所构建多路径路由具有最大不相交特性，即不同路径之间尽量不存在重合节点或链路，分流策略为源节点选择其他路径进行数据传输，绕开网络中的拥塞区域，实现流量均衡与拥塞缓解，保证数据的持续传输。

![](images/5633c70de5c2fece13b3af7915d5f7f9ad264288961251676522e2e70c572193.jpg)  
图2基于多路径的拥塞控制策略处理流程

# 4仿真验证

本文利用OMNet $^ { + + }$ 对带有拥塞控制的多路径路由协议与其他路由协议进行对比分析，仿真参数设定如下：

表2网络仿真参数设定  

<html><body><table><tr><td>参数设置</td><td>参数值</td></tr><tr><td>部署区域范围（m）</td><td>100*100</td></tr><tr><td>普通节点数量（个)</td><td>256</td></tr><tr><td>图像节点数量（个）</td><td>4</td></tr><tr><td>通信距离(m)</td><td>15</td></tr><tr><td>最大传输跳数（TTL）</td><td>8</td></tr><tr><td>初始能量</td><td>1000</td></tr><tr><td>发送报文能耗</td><td>1</td></tr><tr><td>接收报文能耗</td><td>0.5</td></tr></table></body></html>

本文仿真对比分析无线传感器网络中的 SMR 多路径协议，以及MHC 协议[1以及本文提出的DMRC多路径协议，同时将DMRC 协议与网络层使用MHC协议传输层加入CODA拥塞控制机制[的MHCC协议进行对比。

![](images/2a49465483f689894e4fd12d62cd5cae387693aca17ca0bbb5cd42ab39b4f745.jpg)  
图3路由报文不同协议下的占有率

图4节点能量不同多路径路由协议下随时间变化

图3显示MHC协议在网络初始化过程中由于洪泛策略导致路由报文占有率明显高于另外两种协议，而 SMR 相对于DMRC 协议在网络初始过程中路由报文数量要更少，这得益于路由报文转发的严格策略；随着网络运行时间加长，DMRC 由于减少了再次洪泛路由请求机率，长时间运行后路由报文占有率趋于平稳。随着网络长时间运行，三种协议的路由报文占有率表现大致趋于相当。针对高数据量和高数据传输速率的多媒体无线传感器网络的环境下初始过程中路由报文需更多的额外支出以完成多路径构建。

图4对比DMRC协议与SMR协议，给出两种多路径路由协议下的平均节点能量随时间变化。网络初始阶段由于DMRC较为宽泛的路由报文转发策略，能耗方面高于SMR；而在网络持续运行过程中，SMR无限制的多路径传输导致链路能量耗尽，触发再次路由洪泛，DMRC通过拥塞控制策略缓解节点或链路级拥塞，减少了报文重发，均衡节点能量消耗，避免由于链路节点死亡导致的再次路由洪泛，延长整个网络生命周期。

![](images/65d83032a2e69e1e5f0172a8e5dee12b3c818bf2816a1e25304d4730cebad362.jpg)  
图5不同拥塞控制协议下报文传输成功率对比

图5对比DMRC 协议与MHCC协议，数据显示DMRC 在发包率不断增加的WMSN 网络中具有更好的报文传输成功率。

# 5结语

多媒体无线传感器网络具有数据量大、实时性要求高、易于发生网络拥塞的特性，本文提出多路径路由构建机制，并在此基础上实现网络拥塞控制。本文给出了报文封装、协议时序交互，并已完成了TinyOS下代码实现，灌装在实际节点中，在北京市昌平区前葡沟村现代农业示范基地实测环境下运行正常。仿真对比分析表明，带有拥塞控制的多路径机制在大数据量传输的多媒体无线传感器网络中具有更高的传输成功率，网络平均能耗平缓。下一阶段工作将对多路径模型进行深入对比，分析不同多路径路由机制所带来的网络性能差异。

# 参考文献

[1] Ganesan D, Govindan R, Shenker S,et al. Highly-resilient, energy-eficient multipath routing in wireless sensor networks[Cl//Proceedings of the 2OO1 ACM International Symposium on Mobile Ad Hoc Networking and Computing. Long Beach, CA, United states: Association for Computing Machinery, 2001: 251-254.   
[2] Mateen W,Raza S, Uzmi Z A, et al. Adaptive multi-path on-demand routing in mobile ad hoc networks[Cl// Proceedings of 8th IEEE International Symposium on Object-Oriented Real-Time Distributed Computing. Seatle, MA, United states: IEEE Computer Society,20O5: 237-244.   
[3] Chen C,Wu W,Li Z. Multipath routing modeling in ad hoc networks[C]// IEEE International Conference on Communications. Seoul, Republic of Korea: Institute of Electrical and Electronics Engineers Inc., 2005: 2974-2978.   
[4] Almalkawi IT, Guerrero Zapata M, Al-Karaki JN, et al. Wireless Multimedia Sensor Networks: Current Trends and Future Directions[J]. SENSORS.2010,10(7): 6662-6717.   
[5] 孙利民，李波，周新运．无线传感器网络的拥塞控制技术[J]．计算机研究与发展.2008,45(1): 63-72.   
[6] Wan C, Eisenman S B,Campbell A T.CODA: Congestion detection and avoidance in sensor networks[Cl//Proceedings of the First International Conference on Embedded Networked Sensor Systems.Los Angeles, CA, United states: Association for Computing Machinery,2003: 266-279.   
[7]Paek J, Govindan R. RCRT: Rate-controlled reliable transport for wireless sensor networks[C]/ Proceedings of the 5th ACM Conference on Embedded Networked Sensor Systems. Sydney, NSW,Australia: Association for Computing Machinery,2007: 305-319.   
[8] 罗武胜，鲁琴，杜列波．基于LBT的无线传感器网络多节点协同图像压缩算法[J]．传感技术 学报.2008(09):1600-1604.   
[9]Lee S J, Gerla M. Split multipath routing with maximally disjoint paths in Ad hoc networks[C]// IEEE International Conference on Communications.Helsinki,Finland: Institute of Electrical and Electronics Engineers Inc., 2001: 3201-3205.   
[10] Han K,Ko Y,Kim J.A novel gradient approach for efficient data dissemination in wireless sensor networks[Cl//IEEE Vehicular Technology Conference.Los Angeles, CA, United states: Institute of Electrical and Electronics Engineers Inc.,2004: 2979-2983.