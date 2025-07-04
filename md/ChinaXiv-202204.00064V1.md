# 多中心半开放式送取需求可拆分的车辆路径研究

张颖钰，吴立云

(河南理工大学 工商管理学院，河南 焦作 454003)

摘要：针对多中心半开放式送取需求可拆分的车辆路径问题，构建了以车辆配送距离最短为目标的多中心半开放式送取需求可拆分的数学模型。设计大变异邻域遗传算法进行求解，采用二维染色体编码及顺序交叉策略，同时运用大变异策略和邻域搜索策略提高算法全局和局部的寻优能力，通过算例对比验证了所提模型与算法的有效性。算例实验表明，大变异邻域遗传算法在求解多中心物流配送车辆路径问题上，求解质量较优、求解效率较高、求解结果较为稳定。同时还验证了联合配送下多中心半开放式送取需求可拆分的配送模式优于独立配送下单中心送取需求可拆分的配送模式。研究成果不仅拓展了车辆路径问题，还可为相关快递物流企业配送优化提供决策参考。

关键词：车辆路径问题；多中心；送取需求可拆分；大变异遗传算法 中图分类号：TP18;F252 doi:10.19734/j.issn.1001-3695.2022.01.0014

Multi-depot half open vehicle routing problem with split deliveries and pickups

Zhang Yingyu, Wu Liyun+ (SchoolofBusiness Administration,Henan Polytechnic University,Jiaozuo Henan 454oo3,China)

Abstract:Tosolve theproblemofmulti-depothalf-openvehiclerouting problem with splitdeliveriesand pickups,this article constructs a multi-depot half-open vehicle routing problem with split deliveries and pickups mathematical model with the shortest vehicle delivery distance as the goal.The solving processmainlyuse genetic algorithmbased on big mutation and variable neighborhood search,whichadopt two-dimensional chromosome coding and sequential crossover strategy,thebig mutation strategyandneighborhood search strategy improve the global and localoptimization capabilitiesofalgorithm.The numerical examplesverifytheeffectivenessof themodelandthe algorithm.Numerical examples show that thealgorithm have benefits insolutionqualityeficiencyforsolving thmulti-centerlogisticsdistributionvehicle routing problem,andthe result is relatively stable.Meanwhile,the multi-depot half-open vehicle routing problem with split deliveriesand pickups is superior to the vehicle routing problem with split deliveriesand pickups.The research results not only expand the vehicle routing problem,butalsoprovidedecision-makingreferences forthe distributionoptimizationofrelatedlogistics enterprises.

Key words: vehicle routing problem; multi-depot; split deliveries and pickups; genetic algorithm based on big mutation

# 0 引言

近年来电商联盟快速发展，环保政策相应落实，促使国家逆向物流发展迅速。车辆路径问题(VehicleRoutingProblem.VRP)逐渐演化成联合配送下多中心带回程的运输问题，其中包括多中心开放式车辆路径问题(Multi-DepotOpenVRP,MDOVRP)[1]、多中心半开放式车辆路径问题(Multi-DepotHalf OpenVRP,MDHOVRP)[2]以及多中心闭合式车辆路径问题。随着客户点由单一的配送需求演变为送取双需求，还包括同时送取货问 题(VRPwith Simultaneous Delivery andPickup，VRPSDP)[3]和送取需求可拆分的车辆路径问题(VRPwith SplitDeliveriesandPickups,SVRPPD)[4]等众多的拓展问题。本文研究的联合配送下多中心半开放式送取需求可拆分的车辆 路 径 问 题(Multi-Depot Half Open VRP with SplitDeliveriesandPickups,MDHOSVRPPD)是综合了SVRPPD、MDHOVRP及联合配送特点的车辆路径问题。MDHOSVRPPD问题更加准确的描述了现实物流配送的复杂情况。如在一个多配送中心联合配送快递的区域内，配送车辆不仅要配送快递，还要进行快递的揽件操作，当客户点需求全部满足后，配送车辆可采用就近原则返回任意配送中心，共享配送网络。半开放式的配送中心及合理的拆分末端客户点的送取需求，有助于提高车辆载重利用率，降低物流、运输企业的配送成本。目前，针对该问题的研究涉及较少。但其包含的SVRPPD、MDHOVRP等问题仍是当前的研究热点。

关于SVRPPD、MDHOVRP国内外学者都对其模型和求解方法进行了广泛和深入的研究。Mitra[5]首次深入分析了SVRPPD问题，并构造了NH、SM两种启发式算法对其求解。Archetti等人[对客户点需求是否拆分作出了详细的科学论证，实验证明当客户点的总平均需求大于车辆容量一半但小于车辆容量的四分之三，并且需求方差相对较小时，拆分可以获得最大的收益。拆分带来的收益主要体现在车辆配送路径的减少，跟客户点的位置无关。Tang等人7在解决现实中第三方物流案例中，采用了送取需求可拆分的车辆路径模型，并加入了时间窗的限制，运用构造型启发式算法-竞争决策算法对模型求解。Nagy等人[8]采用禁忌搜索算法对SVRPPD 进行求解，并与文献[7]的算法进行了对比，表明禁忌搜索算法在求解精度和效率上均更优。对于MDHOVRP的研究，Cordeau等人[9]设计了一种禁忌搜索算法，并加入了一组惩罚函数对MDHOVRP问题求解；Ting等人[I0]将模拟退火算法与蚁群算法相结合对MDHOVRP 问题进行求解。辜勇等人[11]研究了带时间窗的多中心半开放式车辆路径问题，并设计了一种三段式求解方法，第一阶段先用K-mediods方法将多配送中心转换为单配送中心路径，第二阶段用GA-ACO算法进行求解，第三阶段运用节约算法将单配送中心拆分成多配送中心；范厚明等人[12]根据蚁群算法，改进信息素更新方式从而提高寻优能力，对MDHOVRP问题进行求解；王勇等人[13]将遗传算法与粒子群算法结合求解MDHOVRP问题。范厚明等人[14]首次研究多中心联盟配送与同时送取货结合的车辆问题(Multi-Depot VRP with Simultaneous DeterministicDelivery and Stochastic Pickup based on Joint Distribution,MDVRPSDDSPJD)，根据问题特征，设计了变邻域文化基因算法求解该问题。

综上所述，现有文献主要集中在对SVRPPD、MDHOVRP分开的研究，将SVRPPD与MDHOVRP结合考虑的文献涉及较少。在现实复杂的物流配送网络中，仅靠解决以上单一问题是不全面的，而需要综合考虑车辆共享、各配送中心之间联合配送以及对客户点送取需求合理拆分的情况，才能更好的优化现实物流配送路径。

MDHOSVRPPD问题是现实物流配送模式发展演变而来，具有多中心、半开放式以及客户点送取需求可拆分等特点。在运行至客户点时，车辆负载减少或增加，导致负载波动，必须对车辆每个线路进行可行性检查，进一步增加了算法的求解难度。为了更好地求解MDHOSVRPPD问题，提升求解效率和解的质量，本文设计了一种针对MDHOSVRPPD特点的大变异邻域遗传算法，采用二维染色体编码，不仅实现了对客户点送取需求的拆分，而且提高了求解效率，并引入顺序交叉算子，加强种群之间的交流旨在通过该算法以获得较高质量的满意解。

# 1 MDHOSVRPPD 的提出

MDHOSVRPPD问题是对传统VRP问题的扩展。由以下VRP问题扩展而来：

# 1)带回程车辆路径问题

带回程车辆路径问题(VRPwith Backhauls,VRPB)[15]是在配送车辆只能进行后尾装载(Rear-Loaded)的状态下产生的。配送车辆负载货物从配送中心出发，先服务具有送货需求的客户点，再服务具有取货需求的客户点，最后车辆回到配送中心。VRPB的示意图见图1(a)。

2)混合装载带回程车辆路径问题

随着物流运输技术的进步，配送车辆不仅可以后尾装载，还可以进行侧面装载(Side-Loaded)。因此，对送取顺序不会加以限制，产生混合装载带回程的车辆路径问题(VRPwithBackhaul andMixedLoad,VRPBM)[l6]。VRPBM的示意图见图1(b)。

VRPB与VRPBM问题都是解决单一配送中心、客户点具有单一配送需求的车辆路径问题。随着时代的发展解决现有物流运输问题具有一定的局限性。

# 3)同时送取货车辆路径问题

同时送取货车辆路径问题(VRPwithSimultaneousDeliveryand Pickup,VRPSDP)[17,18]是指客户同时具有送货、取货两种需求，且车辆对其只能服务一次，VRPSDP问题是对VRPBM问题的扩展。VRPSDP的示意图见图1(c)。

4)送取需求可拆分车辆路径问题

在实际应用中，部分客户点需求量较大，如果仍要求每个客户点仅由一辆车提供服务，不仅造成车辆空载严重，还增加了车辆使用数量，使派遣成本增加。Dror和Trudeau[19]首次提出了送货需求可拆分的车辆路径问题(SplitDeliveryVRP,SDVRP)，合理拆分使得客户点被配送车辆服务一次的限制取消了。这样不仅提高了车辆的利用率，还可以节省运输距离和服务的车辆数目。后来研究学者开始探讨对客户点具有送货、取货双重需求拆分的车辆路径问题(VRPwith Split

Deliveries andPickups,SVRPPD)。SDVRP 问题可以看做是SVRPPD问题中送取需求其中一个为0时的特例。而SVRPPD 问题可以看成是对 SDVRP与VRPSDP的扩展,SVRPPD的示意图见图1(d)。

5)多中心闭合式送取需求可拆分的车辆路径问题

随着现代物流业的发展，逐渐演变为在某一区域内有多个配送中心，来自不同配送中心的车辆完成所有客户点的送取货任务后返回原配送中心，称为多中心闭合式送取需求可拆分车辆路径问题(Multi-Depot VRPwith Split Deliveries andPickups,MDSVRPPD)。MDSVRPPD 问题是对SVRPPD问题的扩展，MDSVRPPD 的示意图见图1(e)。

6)多中心半开放式送取需求可拆分的车辆路径问题

MDHOSVRPPD问题中配送中心具有半开放式的特点。开放式、闭合式及半开放式三者是由配送中心对车辆始末停靠位置进行区别的。开放式的配送中心允许车辆在行驶路径中自由停靠，车辆最终不一定要返回配送中心；闭合式的配送中心要求车辆的始末位置是配送中心且必须一致；半开放式的配送中心要求车辆完成任务后可就近返回任意配送中心，车辆可以共享配送网络。因此MDHOSVRPPD问题是进一步降低配送成本的演变，也是MDSVRPPD问题的拓展。MDHOSVRPPD的示意图见图1(f)。

关于MDHOSVRPPD问题的最优解理论，文献[20]已证明多中心半开放式下的车辆运输，仅影响车辆在配送中心的首末停靠位置，而配送车辆对客户点送取货的行驶路径不受影响。因此由Dror和Trudeau提出的需求拆分最优解相关理论，也适用于本文研究的MDHOSVRPPD问题。

![](images/b3673257e5ba4ffd813c15694d8f24c475e1be723d1fe71cb3ff629ca39db546.jpg)  
图1MDHOSVRPPD 提出过程  
Fig.1Presentation process of MDHOSVRPPD

# 2 MDHOSVRPPD的数学模型

# 2.1问题描述

MDHOSVRPPD问题可以描述如下：给定多个配送中心、客户点，各个配送中心之间可联合配送，客户点同时具有送货需求与取货需求且单个客户点的总需求可能超过车辆载重。同一类型的车辆以负载状态从配送中心出发，携带客户点所需要的货物，对客户点执行先送货、后取货服务，服务时不允许超过车辆最大载重，车辆返回时选择距离近的配送中心。

单个客户点的需求可以由多辆车服务来满足。目标是找到一组满足所有客户点需求的车辆路线，并使配送距离最小化。

基于以上分析，本文将构建车辆运输距离最小化的车辆路径模型，并满足以下模型假设：

a)配送中心、客户点位置已知；

b)每个客户点的送取需求量已知；

c)所有车辆起止点均为配送中心，车辆装载能力相同且  
运输过程中实际装载量不得超过车辆载重；d)各客户点的送取总需求允许超过车辆载重，客户点可  
以接受多次服务；e)车辆对客户点的服务无顺序要求；f)车辆对客户点的服务无时间要求。

# 2.2数学模型

以距离最小化为优化目标，建立的MDHOSVRPPD数学模型如下：

$$
\operatorname* { m i n } { z } = \sum _ { i \in V } \sum _ { j \in V } \sum _ { k \in K } x _ { i j k } C _ { i j }
$$

s.t.

$$
\sum _ { i \in L \cup B } y _ { i j } - \sum _ { i \in L \cup B } y _ { j i } = D _ { j } ; j \in L \cup B
$$

$$
\sum _ { i \in L \mathrm { U } B } z _ { j i } - \sum _ { i \in L \mathrm { U } B } z _ { i j } = P _ { j } ; j \in L \mathrm { U } B
$$

$$
\sum _ { i \in V } y _ { i 0 } = 0 ; \sum _ { j \in V } z _ { 0 j } = 0
$$

$$
\sum _ { i \in L \mathsf { U } B } \sum _ { j \in L \mathsf { U } B } x _ { i j k } - \sum _ { i \in L \mathsf { U } B } \sum _ { j \in L \mathsf { U } B } x _ { j i k } = 0 ; k \in K
$$

$$
\sum _ { i \in M } \sum _ { j \in L \mathsf { U } B } x _ { i j k } = \sum _ { i \in L \mathsf { U } B } \sum _ { j \in M } x _ { i j k } = 1 ; k \in K
$$

$$
y _ { i j } + z _ { i j } \le Q \sum _ { k \in K } x _ { i j k } ; i , j \in V
$$

$$
x _ { i j k } \geq 0 , y _ { i j } \geq 0 , z _ { i j } \geq 0 , x _ { i j k } \in Z ^ { + }
$$

目标函数式(1)为距离最小化；式(2)-(3)保证所有客户点的需求都被满足；式(4)确保车辆离开配送中心时车上只有待配送的货物，当车辆返回配送中心时，车上只有收取的货物；式(5)表示车辆服务客户点的次数等于离开客户点的次数，车辆不能在客户点进行停靠；式(6)表示车辆从任意配送中心出发且仅离开一次，并最终返回任意配送中心；式(7)保证车辆实际装载不超过车辆载重；式(8)为变量的取值约束。

模型中各符号含义见表1所列。

# 3 大变异邻域遗传算法

MDHOSVRPPD是NP难问题，其送取需求可拆分的特点，增加了求解难度。对于送取需求可拆分的车辆路径问题的求解，大多数学者采用构造型启发式算法[4,6,8.9]，本文对于MDHOSVRPPD的求解采用现代启发式算法，现代启发式算法对于解决大规模的VRP类问题能够在合理的时间内得出近似最优解。将大变异遗传算法(Genetic Algorithmbased onbig Mutation，GAM)和 邻域算法[21](Variable NeighborhoodSearch,VNS)结合求解MDHOSVRPPD问题，前者具有出色的全局搜索能力，后者有较强的局部搜索能力，因此本文设计了大变异邻域遗传算法(Genetic algorithm based on bigMutation and Variable Neighborhood Search,GAMVNS)。

# 3.1编码与解码

本文采用两段式实数编码，将真实客户点在原位置的基础上分成两个虚拟客户点，虚拟客户点只具有送货任务或者取货任务。编码第一段为送货任务随机全排列，第二段为对应的取货任务随机全排列，所有任务储存在 $p o p _ { - } P n u m$ 中，记录任务的服务顺序如图2。

# 表1符号说明表

Tab.1Symbol description table   

<html><body><table><tr><td>类别</td><td>符号</td><td colspan="2">说明</td></tr><tr><td rowspan="7">数据</td><td>M</td><td colspan="2">配送中心合集M∈{1,2,L，m}</td></tr><tr><td>L</td><td>具有送货需求的虚拟客户点合集 L∈{m+1,m+2.L,m+n}</td></tr><tr><td>B</td><td>具有取货需求的虚拟客户点合集</td></tr><tr><td></td><td>B∈{m+n+1,m+n+2,L,m+2n}</td></tr><tr><td>V</td><td>配送中心和客户点合集V=MULUB</td></tr><tr><td>k</td><td>车辆的标号(车辆型号统一)k∈{1,2,L,K}</td></tr><tr><td>K Q</td><td>使用车辆的总数</td></tr><tr><td rowspan="4">需求 定量</td><td></td><td>车辆的最大装载能力</td></tr><tr><td>D</td><td>从配送中心运输到客户点j的总需求量； j∈L</td></tr><tr><td>P</td><td>在客户点j取货并运回配送中心的总需求量；</td></tr><tr><td>Cii</td><td>j∈B 路径中任意点i到点j的距离；i,j∈V</td></tr><tr><td rowspan="4">决策 变量</td><td>Xijk</td><td colspan="2">车辆k从点i行驶至点j的次数；i,j∈V</td></tr><tr><td></td><td>经过客户点i，j后，车辆上剩余的待送货物</td><td></td></tr><tr><td>yi</td><td></td><td>量；i,j∈LUB 经过客户点i，j后，车辆上需运回配送中心的</td></tr><tr><td>Zi</td><td colspan="2">货物量；i,j∈LUB</td></tr><tr><td colspan="2"></td><td>pop_Pnum 送货任务</td><td></td></tr><tr><td colspan="2"></td><td>3 5 2 1</td><td>4</td><td>取货任务 3 5 2</td></tr></table></body></html>

图2编码示意图  
Fig.2Coding diagram

解码过程中，车辆对客户点服务执行先送后装原则。解码分为两阶段，第一阶段从左到右将客户点的任务划分给车辆，按照贪婪原则，车辆满足送货任务后尽可能多的取货，并进行车辆约束检验，直到车辆没有待配送货物且待运回货物满载时，车辆退出路径分配阶段，等待返回配送中心，派出新车对剩余任务进行服务；第二阶段根据每辆车服务首尾客户点到配送中心的距离最短原则，确定每辆车的始末配送中心。

举例对图2进行求解，假设车辆 $k _ { 1 }$ 满足客户点4的全部任务，访问客户点3时满足送货任务和一部分取货任务，访问客户点5时满足部分送货任务和全部取货任务，此时车辆$k _ { 1 }$ 没有待配送货物且已满载，则退出路径分配。派出车辆 $k _ { 2 }$ 对剩余任务服务， $k _ { 2 }$ 先服务客户点5的送货任务和客户点3的取货任务，再去服务客户点2和客户点1，假设 $k _ { 2 }$ 满足客户点1、2的任务，则 $k _ { \mathrm { 1 } }$ 的分配过程和 $k _ { \mathrm { 1 } }$ 、 $k _ { 2 }$ 的最后路径如图3所示,最后依据车辆服务首尾客户点到配送中心距离最小来确定车辆的始末配送中心，6、7为配送中心。

可以看出，在后续操作时只对 $p o p _ { - } P n u m$ 信息的第一段进行迭代操作，操作完成后依据配送车辆的载重约束重新为每辆车分配客户点，得到每个车辆的运行路径，再对车辆的首尾客户点进行解码操作就可以获得最终路径。只要 $p o p _ { - } P n u m$ 第一阶段正确，则后面由它产生的最终路径也一定是正确的，即pop_Pnum的第一阶段编码决定了后续编码。通过此编码方式，不仅实现对客户点需求的拆分，而且使得后续扰动操作总能产生可行解，提高了算法效率。

# 3.2适应度函数

适应度函数通常由目标函数式(1)确定，由于构建距离最小化的目标函数，则染色体 $s$ 的适应度函数 $f _ { s }$ 如下：

$$
f _ { s } = \frac { 1 } { G _ { s } }
$$

$G _ { s }$ 为染色体 $s$ 的目标函数值。

# 3.3 选择交叉操作

本文选择操作采用轮盘赌与精英保留策略相结合的方式。轮盘赌是个体以一定概率被选中，概率大小根据个体的适应度函数值大小确定，个体适应度函数值高的被

pop_Pnum

选中的概率则大，反之则小。精英保留策略是适应度函数值最高的父代代替适应度函数值最低的子代。采取这两种策略有助于加强所有个体间基因充分交流以及快速形成稳定的下一代。

![](images/d43b6c42e8e717f75c8c020c49fb63fc4bd9080b0753a027ec5813ffa1d7a50c.jpg)  
Fig.3Decoding diagram

交叉操作则是采用顺序交叉算子。对个体pop_1顺序交叉时，从种群中随机选取pop_2个体，分别随机选取pop_1、pop_2中四个基因 $g _ { 1 1 }$ 、 $g _ { 1 2 }$ 、 $g _ { 2 1 }$ 和 $g _ { 2 2 }$ ， $p o p _ { - } 1$ 中的 $g _ { 1 1 }$ 、 $g _ { 1 2 }$ 之间的基因作为newpop_1个体的第一段，消除 $p o p _ { - } 2$ 中 $g _ { 1 1 } \setminus g _ { 1 2 }$ 之间的客户点，保持剩下客户点位置不变，作为newpop_1的第二段，此时newpop_1个体生产完毕，newpop_2同理。如图4所示。

![](images/f0ab26d2a05cbe3ab0213b7e79dfafdf5fcda72306c92b177e9862fafed95e5c.jpg)  
Fig.4Sequence crossing diagram

# 3.4大变异操作

传统遗传算法容易“早熟”，为了让种群摆脱“早熟”，采取大变异策略弥补这一缺陷。大变异策略具体为[22]：首先设定一个合适的变异率搜索，并记录每一代种群的最高适应度 $f _ { \mathrm { m a x } }$ 和平均适应度 $f _ { a \nu g }$ ，当满足：

$$
\alpha \times f _ { \mathrm { m a x } } < f _ { a \nu g }
$$

表示该代种群具有高度“集中”的表现，随后以普通变异率大5倍以上的概率对该代种群进行一次变异操作。其中，$0 . 5 < \alpha < 1$ ， $\alpha$ 为密集因子，表示种群的集中程度。

变异操作采用了三种邻域结构，分别是插入、交换、2-opt，来增强算法的局部搜索。设置邻域结构的最优解次数Se和最大搜索次数 $M a x \_ S e$ ，当个体进行第一个邻域操作时，在$\mathit { s e }$ 次最优解不变，进入下一个邻域操作，或当个体循环次数达到 $M a x \_ S e$ 时，进入下一个邻域操作。直至循环到最后一个邻域操作，搜索终止输出最优解。

a)插入规则如图5(a)，将个体中的客户点3移动到客户点6后产生新的个体。

b)交换规则如图5(b)，将个体中的客户点3与客户点6进行交换产生新的个体。

c)2-opt规则如图5(c)，将个体中客户点3与客户点6之间的客户逆序排列，客户点3保持不变，客户点5、2、6逆序排列，从而产生新的个体。

![](images/7eaf63d406bfb1f605835e13ac3d1081b206b31c9d2924cb4cd4beb08bc173cc.jpg)  
图3解码示意图  
图5邻域搜索示意图  
Fig.5Neighborhood search diagram

使用三种策略产生新个体，能大大提高个体的适应度，进而提升GAMVNS算法的局部搜索能力，提高算法运算效率。算法流程图如图6。

![](images/c41cad935203ccf3742633512cbd0b2ccb81ba465b6c239ee62d6cdfdc16ae2a.jpg)  
图4顺序交叉示意图  
图6算法流程图  
Fig.6Algorithm flow chart

# 4 实验与结果分析

本文依次选取 MDVRP 算例、MDHOSVRPPD 算例与

SVRPPD算例验证本文算法的有效性。其中SVRPPD算例不仅证明了本文算法的有效性，而且证明了联合配送下多中心半开放送取需求可拆分的配送模式优于单中心下送取需求可拆分的配送模式。为了测试GAMVNS算法的性能，对算例进行大量实验验证。本文在MATLAB2016B中编程，并使用Inter?CoreTMi5-1035G1CPU2.19GHz计算机系统在Windows10上执行，该系统具有16GB内存。实验基本参数设置见表2， $n$ 、 $N$ 、 $\boldsymbol { \mathscr { G } }$ 、 $P c$ 、 $P m$ 、 $\mathit { s e }$ 、 $M a x _ { - } S e$ 分别为客户规模、种群规模、最大迭代次数、交叉概率、变异概率、最优解次数、最大邻域搜索次数。

Tab.2Parameter setting   

<html><body><table><tr><td>n</td><td>N</td><td>G</td><td>Pc</td><td>Pm</td><td>Se</td><td>Max_Se</td></tr><tr><td>0<n≤50</td><td>100</td><td>50~500</td><td>0.8</td><td>0.08</td><td>50~100</td><td>70~100</td></tr><tr><td>50<n≤75</td><td>300</td><td>500~700</td><td>0.8</td><td>0.08</td><td>50~100</td><td>70~100</td></tr><tr><td>75<n≤100</td><td>500</td><td>700~1000</td><td>0.8</td><td>0.07</td><td>50~100</td><td>70~100</td></tr></table></body></html>

# 4.1MDVRP 算例验证

实验一为了验证本文算法的有效性，选取文献[23\~25]中的MDVRP 算例进行验证。该算例中包括30个客户点(编号为1-30)，3个配送中心(编号为31-33)，配送车辆的最大容量为10t及最大行驶距离为 $5 0 \mathrm { k m }$ ，所有客户点需求都在2t及以下。表3给出文献[23]的狼群算法(WPA)、文献[24]的竞争决策算法(CDA)以及文献[25]的禁忌搜索算法(TS)、量子遗传算法(QGA)与本文提出的GAMVNS算法运行10次的结果对比。表中KOS表示已知最优解，Best、Worst、Avg分别表示算法运行10次得到的最优解、最差解以及平均解，%Dev、CPU 为最优解偏差与算法平均运行时间。配送车辆行驶路径见表4。

由表3可以看出，本文算法求得最优解与已知最优解相同均是116.01，而求得的最差解及平均解均优于其他算法所求。从求解时间方面来看，本文算法运行10次的平均时间为7.84s，运行时间比其他算法有显著降低，有较强的优势。

表3实验一结果对比  
表4实验一最优解路径  

<html><body><table><tr><td rowspan="2">算例</td><td rowspan="2">KOS</td><td colspan="2">总距离</td><td colspan="2">总距离</td><td rowspan="2">CPU/s</td></tr><tr><td>Best</td><td></td><td>%Dev Worst %Dev</td><td>总距离 Avg %Dev</td></tr><tr><td>WPA[23]</td><td></td><td>122.42</td><td>5.53</td><td>1</td><td></td><td>1</td></tr><tr><td>CDA[24]</td><td></td><td>123.33</td><td>6.31</td><td></td><td>1 1</td><td>1</td></tr><tr><td>TS[25]</td><td>116.01 116.01</td><td></td><td>0</td><td>343.31195.93 187.34 61.49</td><td></td><td>243</td></tr><tr><td>QGA[25]</td><td></td><td>116.01</td><td>0</td><td>326.48 181.42176.37 52.03</td><td></td><td>216</td></tr><tr><td>GAMVNS</td><td></td><td>116.01</td><td>0</td><td>150.13 29.41 142.81 23.10</td><td></td><td>7.84</td></tr></table></body></html>

Tab.3Comparison of experiment l results   
Tab.4Experiment 1 optimal solution path   

<html><body><table><tr><td>算法</td><td>车辆行驶路线</td><td>总距离</td></tr><tr><td rowspan="3">GAMVNS</td><td>33-6-3-18-26-12-5-25-33</td><td></td></tr><tr><td>33-17-21-19-20-23-24-2-9-27-16-33 32-11-29-18-13-8-15-1-32</td><td>116.01</td></tr><tr><td>31-4-7-10-22-14-30-31</td><td></td></tr></table></body></html>

# 4.2MDHOSVRPPD 算例验证

实验二MDHOSVRPPD问题的相关约束较多，有多个配送中心、多个客户点、客户点具有送取需求等特点。目前没有通用的算例集，本文选用标准算例库中的MDVRP算例P02(算例集来源 https://neo.lcc.uma.es/vrp/vrpinstances/multiple-depot-vrp-instances/)，并按MDHOSVRPPD问题的特点修改后来进行验证。P02算例包括50个客户点(编号为1-50)，4个配送中心(编号为51-54)，车辆容量为160。客户的送取需求由Nagy[26]提出的需求分离规则产生： $x _ { i }$ 、 $y _ { i }$ 为客户点的坐标， $d _ { i }$ 、 $p _ { i }$ 为客户点送货、取货需求， $q _ { i }$ 为客户点原始需求，$r _ { i } = \operatorname* { m i n } ( x _ { i } / y _ { i } , y _ { i } / x _ { i } )$ 计算每个客户比率，由 $d _ { i } = q _ { i } r _ { i }$ 和 $p _ { i } = q _ { i } ( 1 - r _ { i } )$ 计算得出各个客户点的送取需求，算例具体信息见表5。

# 表5实验二算例数据

表2参数设置  

<html><body><table><tr><td rowspan="2"></td><td colspan="4">Tab. 5 Experiment 2 example data</td></tr><tr><td>xi</td><td>yi</td><td>di</td><td>pi</td></tr><tr><td>编号</td><td>37</td><td>52</td><td>5</td><td>2</td></tr><tr><td>1 2</td><td>49</td><td>49</td><td>30</td><td>0</td></tr><tr><td>3</td><td>52</td><td>64</td><td>13</td><td>3</td></tr><tr><td></td><td>20</td><td>26</td><td>7</td><td>2</td></tr><tr><td>4</td><td></td><td></td><td></td><td>5</td></tr><tr><td>5</td><td>40</td><td>30 47</td><td>16 7</td><td>8</td></tr><tr><td>6</td><td>21 17</td><td>63</td><td>5</td><td>14</td></tr><tr><td>7 8</td><td>31</td><td>62</td><td>12</td><td>12</td></tr><tr><td>9</td><td>52</td><td>33</td><td>7</td><td>4</td></tr><tr><td>10</td><td>51</td><td>21</td><td>2</td><td>3</td></tr><tr><td>11</td><td>42</td><td>41</td><td>19</td><td>0</td></tr><tr><td>12</td><td>31</td><td>32</td><td>28</td><td>1</td></tr><tr><td>13</td><td>5</td><td>25</td><td>5</td><td>18</td></tr><tr><td>14</td><td>12</td><td>42</td><td>6</td><td>15</td></tr><tr><td>15</td><td>36</td><td>16</td><td>4</td><td>6</td></tr><tr><td>16</td><td>52</td><td>41</td><td>12</td><td>3</td></tr><tr><td>17</td><td>27</td><td>23</td><td>3</td><td>0</td></tr><tr><td>18</td><td>17</td><td>33</td><td>21</td><td>20</td></tr><tr><td>19</td><td>13</td><td>13</td><td>9</td><td>0</td></tr><tr><td>20</td><td>57</td><td>58</td><td>28</td><td>0</td></tr><tr><td>21</td><td>62</td><td>42</td><td>5</td><td>3</td></tr><tr><td>22</td><td>42</td><td>57</td><td>6</td><td>2</td></tr><tr><td>23</td><td>16</td><td>57</td><td>4</td><td>12</td></tr><tr><td>24</td><td>8</td><td>52</td><td>2</td><td>8</td></tr><tr><td>25</td><td>7</td><td>38</td><td>5</td><td>23</td></tr><tr><td>26</td><td>27</td><td>68</td><td>3</td><td>4</td></tr><tr><td>27</td><td>30</td><td>48</td><td>9</td><td>6</td></tr><tr><td>28</td><td>43</td><td>67</td><td>9</td><td>5</td></tr><tr><td>29</td><td>58</td><td>48</td><td>5</td><td>1</td></tr><tr><td>30</td><td>58</td><td>27</td><td>9</td><td>10</td></tr><tr><td>31</td><td>37</td><td>69</td><td>6</td><td>5</td></tr><tr><td>32</td><td>38</td><td>46</td><td>10</td><td>2</td></tr><tr><td>33</td><td>46</td><td>10</td><td>5</td><td>18</td></tr><tr><td>34</td><td>61</td><td>33</td><td>14</td><td>12</td></tr><tr><td>35</td><td>62</td><td>63</td><td>17</td><td>0</td></tr><tr><td>36</td><td>63</td><td>69</td><td>5</td><td>1</td></tr><tr><td>37</td><td>32</td><td>22</td><td>6</td><td>3</td></tr><tr><td>38</td><td>45</td><td>35</td><td>12</td><td>3</td></tr><tr><td>39</td><td>59</td><td>15</td><td>4</td><td>10</td></tr><tr><td>40</td><td>5</td><td>6</td><td>6</td><td>1</td></tr><tr><td>41</td><td>10</td><td>17</td><td>16</td><td>11</td></tr><tr><td>42</td><td>21</td><td>10</td><td>6</td><td>7</td></tr><tr><td>43</td><td>5</td><td>64</td><td>1</td><td>10</td></tr><tr><td>44</td><td>30</td><td>15</td><td>8</td><td>8</td></tr><tr><td>45</td><td>39</td><td>10</td><td>3</td><td>7</td></tr><tr><td>46</td><td>32</td><td>39</td><td>4</td><td>1</td></tr><tr><td>47</td><td></td><td></td><td></td><td>5</td></tr><tr><td>48</td><td>25</td><td>32</td><td>20</td><td>9</td></tr><tr><td>49</td><td>25</td><td>55</td><td>8</td><td>8</td></tr><tr><td></td><td>48</td><td>28</td><td>11</td><td></td></tr><tr><td>50</td><td>56</td><td>37</td><td>7</td><td>3</td></tr><tr><td>51</td><td>20</td><td>20</td><td>0</td><td>0</td></tr><tr><td>52</td><td>30</td><td>40</td><td>0</td><td>0</td></tr><tr><td>53 54</td><td>50 60</td><td>30 50</td><td>0 0</td><td>0 0</td></tr></table></body></html>

计算结果稳定。并与传统遗传算法(Genetic Algorithm,

GA)、传统蚁群算法(Ant Colony Optimization，ACO)、传统大变异遗传算法(Genetic Algorithm based on big Mutation,GAM)、传统变邻域搜索算法(VariableNeighborhood Search,VNS)作对比，结果见表6和表7，Best、Num为算法运行20次的最优解和车辆数，%Dev、 $C P U$ 为最优解偏差与算法平均运行时间。

由表6看出，传统遗传算法、大变异遗传算法、蚁群算法及变邻域搜索算法搜索策略单一，容易出现“早熟”现象，在求解质量上表现较差。本文提出的GAMVNS算法与四种算法相比，在配送总距离方面分别优化了 $56 \text{‰}$ 、 $6 . 8 8 \%$ 、$12 . 8 3 \%$ 、 $1 6 . 4 6 \%$ ，求解质量方面均优于传统算法。从求解时间上看，本文算法的平均时间为7.2s，计算时间比较理想。最优解偏差为 $0 . 8 \%$ ，能够有效的求解出最优解。表7为配送车辆行驶路径。由图7的最优路径的迭代图可以看出，本文的GAMVNS算法能够以较少的迭代次数快速地进行收敛，具有较强的寻优能力。

Tab.6Comparison of experiment 2 results   

<html><body><table><tr><td>算法</td><td>Best</td><td>Num</td><td>%Dev</td><td>CPU/s</td></tr><tr><td>GAMVNS</td><td>738.59</td><td>3</td><td>0.83</td><td>7.2</td></tr><tr><td>GA</td><td>833.41</td><td>3</td><td>1.47</td><td>11.7</td></tr><tr><td>ACO</td><td>860.21</td><td>3</td><td>1.52</td><td>12.1</td></tr><tr><td>GAM</td><td>780.44</td><td>3</td><td>0.87</td><td>8.3</td></tr><tr><td>VNS</td><td>789.45</td><td>3</td><td>0.91</td><td>11.3</td></tr></table></body></html>

表7实验二最优解路径

表6实验二结果对比  

<html><body><table><tr><td>算法</td><td>车辆行驶路线</td><td>总距离</td></tr><tr><td rowspan="3"></td><td>54-36-3-28-31-8-26-7-23-24-14-25-18-4-47-12- 46-27-1-32-22-48-6-14-25-13-51</td><td rowspan="3"></td></tr><tr><td>GAMVNS 54-29-21-50-9-49-5-38-16-34-30-10-39-33-45- 738.59</td></tr><tr><td>15-44-37-42-41-13-40-24-43-52</td></tr><tr><td></td><td>54-35-20-2-11-32-1-22-48-6-43-17-19-40-51</td></tr></table></body></html>

![](images/e88f711631ffdf321dbe36ca3933b9df6b45361483eb20e9e2109db346c8f92d.jpg)  
图7最短路径迭代图  
Fig.7Shortest path iteration graph

# 4.3 配送模式对比验证

实验三为验证联合配送模式下多中心半开放式送取需求可拆分配送模式优于独立配送模式下单中心送取需求可拆分配送模式(VRPwith SplitDeliveries and Pickups,SVRPPD),选取了MDVRP标准算例库中的P01、P02、P03、P04、P05、P06进行半开放式送取需求可拆分的多中心与单中心对比研究。多中心的配送中心坐标取算例中的数据，单中心的配送中心坐标见表8，客户点送取需求数据的处理按照实验二的标准执行。表9中Best、Worst、Avg分别为算法运行20次得到的最优解、最差解以及平均解。 $\% D e \nu$ 为最优解偏差，Num 为车辆数，CPU为算法运行20次的平均时间。结果见表8和表9。

由表9看出，联合配送模式与独立配送模式下，各算例求解结果中，最优解偏差最大为 $8 . 9 \%$ ，最小为 $0 . 5 \%$ ，求解时间均在8s内。可以看出，本文算法的优化结果求解速度较快，可以稳定的收敛到较优解。

对比联合配送模式下多中心半开放式送取需求可拆分的配送模式与独立配送模式下单中心送取需求可拆分的配送模式，可以看出，配送距离对应缩短为 $3 1 . 8 6 \%$ 、 $1 3 . 0 \%$ 、 $2 5 . 5 7 \%$ 、$9 . 8 9 \%$ 、 $2 7 . 9 5 \%$ 和 $6 . 5 5 \%$ 。从表9与图8可以得出，联合配送下多中心半开放式送取需求可拆分的配送模式，相对于独立配送下单中心送取需求可拆分模式，前者大幅度减少了车辆频繁往返配送中心产生的配送路径，进而降低车辆的配送成本。

Tab.7Experiment 2 optimal solution path   
表8实验三算例数据  

<html><body><table><tr><td colspan="2">算例数据</td><td colspan="2">MDHOSVRPPD</td><td colspan="2">SVRPPD</td></tr><tr><td>算例</td><td>客户数</td><td>车辆载重</td><td>配送中心数</td><td>配送中心数</td><td>配送中心坐标</td></tr><tr><td>P01</td><td>50</td><td>80</td><td>4</td><td>1</td><td>(20,20)</td></tr><tr><td>P02</td><td>50</td><td>160</td><td>4</td><td>1</td><td>(20,20)</td></tr><tr><td>P03</td><td>75</td><td>140</td><td>5</td><td>1</td><td>(40,40)</td></tr><tr><td>P04</td><td>100</td><td>100</td><td>2</td><td>1</td><td>(35,20)</td></tr><tr><td>P05</td><td>100</td><td>200</td><td>2</td><td>1</td><td>(15,35)</td></tr><tr><td>P06</td><td>100</td><td>100</td><td>3</td><td>1</td><td>(15,20)</td></tr></table></body></html>

# 5 结束语

本文针对联合配送下多中心半开放式送取需求可拆分的车辆路径问题进行了以下研究。(1)构建了总配送距离最短的多中心半开放式送取需求可拆分的车辆路径数学模型。(2)设计了大变异邻域遗传算法对其求解，大变异策略和邻域搜索策略摆脱了算法“早熟”问题以及提高了搜索效率，通过三组算例对模型和算法进行了验证分析。结果表明，本文建立的模型和算法能够有效地解决MDHOSVRPPD问题，且搜索稳定，具有较为明显的优势。

此外，MDHOSVRPPD适用于电商联盟，为了给电商企业提供更贴合现实的配送路径，不仅要考虑配送距离最小化，还要考虑客户满意度问题。因此，在时间窗约束下求解多中心半开放式送取需求可拆分的车辆路径问题是下一步的研究方向。

Tab.8Experiment three example data   
表9实验三结果对比  
Tab.9 Comparison of the results of the third experiment   

<html><body><table><tr><td colspan="7">MDHOSVRPPD</td><td colspan="5">SVRPPD</td></tr><tr><td>Best</td><td>Worst</td><td>Avg</td><td>%Dev</td><td>Num</td><td>CPU/s</td><td>Best</td><td>Worst</td><td>Avg</td><td>%Dev</td><td>Num</td><td>CPU/s</td></tr><tr><td>959.62</td><td>1122.08</td><td>987.99</td><td>2.9</td><td>6</td><td>7.2</td><td>1265.32</td><td>1573.06</td><td>1293.6</td><td>2.2</td><td>6</td><td>7.3</td></tr><tr><td>738.59</td><td>833.41</td><td>779.86</td><td>5.3</td><td>3</td><td>7.2</td><td>834.60</td><td>992.23</td><td>864.48</td><td>3.5</td><td>3</td><td>6.9</td></tr><tr><td>917.82</td><td>1143.7</td><td>1008.58</td><td>8.9</td><td>6</td><td>6.8</td><td>1152.52</td><td>1416.46</td><td>1208.07</td><td>4.6</td><td>6</td><td>7.1</td></tr><tr><td>1955.21</td><td>2016.45</td><td>1989.43</td><td>1.7</td><td>9</td><td>7.5</td><td>2148.69</td><td>2241.41</td><td>2183.12</td><td>1.6</td><td>9</td><td>7.1</td></tr><tr><td>1522.29</td><td>1642.5</td><td>1601.31</td><td>4.9</td><td>5</td><td>7.3</td><td>1947.81</td><td>2057.52</td><td>1974.55</td><td>1.4</td><td>5</td><td>6.8</td></tr><tr><td>1804.34</td><td>1837.48</td><td>1875.6</td><td>3.8</td><td>9</td><td>6.9</td><td>1922.45</td><td>1924.80</td><td>1923.63</td><td>0.5</td><td>9</td><td>7.2</td></tr></table></body></html>

![](images/f1601d3d15c8e430fa8a3b0fda258f25dab7bb0f5d943b64415339150437b6bf.jpg)  
图8MDHOSVRPPD 配送模式下最优路径图  
Fig.8Optimal path diagram under MDHOSVRPPD distribution mode

# 参考文献：

[1] 杨翔，范厚明，徐振林，等．模糊需求下多中心开放式车辆路径优化 [J]．计算机集成制造系统,2019,25(2):469-479.(Yang Xiang,Fan Houming,Xu Zhenlin,et al.Optimization of open multi-depot vehicle routing problem with fuzzy demand [J].Computer Integrated Manufacturing Systems,2019,25 (2): 469-479.)   
[2]刘冉，江志斌，耿娜，等．半开放式多车场车辆路径问题[J].上海 交通大学学报,2010,44(11):1539-1545.(Liu Ran,Jiang Zhibin,Geng Na,et al.The half open mult-depot vehicle routing problem[J]. Journal of Shanghai Jiaotong University,2010,44 (11):1539-1545.)   
[3]HornstraRP,Silva A,Bergen KJR,et al.The vehicle routing problem with simultaneous pickup and delivery and handling costs [J].Computers and OperationsResearch,2020,115(3):305-408.   
[4]Wang KF,Ye C M,Ning AB.Achieving better solutions for vehicle routing problem involving split deliveries and pickups using a competitive decision algorithm [J].Asia Pacific Journal of Operational Research,2015,32 (4):155-177.   
[5]Mitra S.An algorithm for the generalized vehicle routing problem with backhauling[J].Asia Pacific Journal of Operational Research,2005,22 (2): 153-169.   
[6]Archetti C,Savelsbergh M, Speranza MG.To split or not to split: That is the question [J]．Transportation Research Part E Logistics& Transportation Review,2008,44(1):114-123.   
[7]Tang G C,Ning AB,Wang KF,et al.A practical split vehicle routing problem with simultaneouspickup and delivery [C]//the 16th International Conference on Industrial Engineering and Engineering Management.New York:IEEE,2009:26-30.   
[8]Nagy G,Wassan NA, Speranza MG,et al. The vehicle routing problem with divisible deliveries and pickups [J].Transportation Science,2015,   
[9]Cordeau JF,Laporte G,Mercier A.A unified tabu search heuristic for vehicle routing problems with time windows [J].Journal of the Operational Research Society,2001,52 (8): 928-936.   
[10] Ting C J,Chen C H.Combination of multiple ant colony system and simulated annealing for the multi-depot vehicle-routing problem with time windows [J].Transportation Research Record Journal of the Transportation Research Board,2008,2089 (2089): 85-92.   
[11]辜勇，袁源乙，张列，等．带时间窗的多中心半开放式车辆路径问题 [J].中国机械工程,2020,31(14):1733-1740.(Gu Yong,Yuan Yuanyi, Zhang Lie,et al.Multi-depot half open vehicle routing problem with time windows [J].China Mechanical Engineering,2020,31(14): 1733-1740.)   
[12]范厚明，杨翔，李荡，等．基于生鲜品多中心联合配送的半开放式车 辆路径问题[J].计算机集成制造系统，2019,25(1):256-266.(Fan Houming,Yang Xiang,Li Dang,et al.Half-open multi-depot vehicle routing problem based on joint distribution mode of fresh food [J]. Computer Integrated Manufacturing Systems,2019,25 (1):256-266.)   
[13]王勇，任音吉，刘永，等．基于多中心车辆路径问题的收益分配优化 研究[J]．交通运输系统工程与信息,2018,18(3):210-217.(Wang Yong,Ren Yinji,Liu Yong,et al.Profit allocation optimization based on multi-center vehicle routing problem [J].Journal of Transportation Systems Engineering and Information Technology,2018,18 (3):210- 217.)   
[14]范厚明，刘鹏程，刘浩，等．多中心联合配送模式下集货需求随机的 VRPSDP问题 [J]．自动化学报，2021,47(07):1646-1660.(Fan Houming,Liu Pengcheng,Liu Hao,et al. The multi-depot vehicle routing problem with simultaneous deterministic delivery and stochastic pickup based on joint distribution [J].Acta Automatica Sinica,2021,47 (07): 1646-1660.)   
[15] Brandao J.A new tabu search algorithm for the vehicle routing problem with backhauls. European Journal Operational Research,20o6,173 (2): 540-555.   
[16] Wade A C, Salhi S.An investigation into a new class of vehicle routing problem with backhauls [J].Omega,2002,30 (6):479-487.   
[17]Lin Z, Jiuh-Biling S.Failure-specific cooperative recourse strategy for simultaneous pickup and delivery problem with stochastic demands [J]. European Journal of Operational Research,2018,271 (3):896-912.   
[18] Shi Y,Boudouh T,Grunder O,et al. Modeling and solving simultaneous delivery and pick-up problem with stochastic travel and service times in home health care [J].Expert Systems with Applications,2018,102(7): 218-233.   
[19] Dror M,Trudeau P. Savings by split delivery routing [J]. Transportation Science,1989,23 (2): 141-145.   
[20]范厚明，张轩，任晓雪，等．多中心开放且需求可拆分的VRPSDP问 题优化[J]．系统工程理论与实践，2021,41(06):1521-1534.(Fan Houming,Zhang Xuan,Ren Xiaoxue,et al.Optimization of multi-depot open split delivery vehicle routing problem with simultaneous delivery and pick-up[J]. Systems Engineering-Theory & Practice,2021,41 (06): 1521-1534.)   
[21]徐倩，熊俊，杨珍花，等．基于自适应大邻域搜索算法的外卖配送车 辆路径优化[J]．工业工程与管理,2021,26(03):115-122.(Xu Qian, Xiong Jun,Yang Zhenhua,et al.Route optimization of takeout delivery vehicles based on adapyive large neighborhood search algorithm [J]. Industrial Engineering and Management,2021,26 (03):115-122.)   
[22]张华庆，张喜．改进遗传算法在车辆路径问题中的应用[J]．交通信 息与安全,2012,30(5):81-86.(Zhang Huaqing,Zhang Xi.Application of improved genetic algorithm in vehicle routing problem[J].Journal of Transport Information and Safety,2012,30(5):81-86.)   
[23]叶勇，张惠珍．多配送中心车辆路径问题的狼群算法[J].计算机应 用研究,2017,34(09):2590-2593.(Ye Yong,ZhangHuizhen.Wolf pack algorithm for multi-depot vehicle routing problem [J].Application Research of Computers,2017,34 (09): 2590-2593.)   
[24]殷脂，叶春明．多配送中心物流配送车辆调度问题的分层算法模型 [J]．系统管理学报,2014,23(04):602-606.(Yin Zhi,Ye Chunming. Study on the hierarchical model for multi-depot logistic vehicle scheduling problem[J].Journal of Systems & Management,2014,23 (04):602-606.)   
[25]葛显龙，许茂增，王伟鑫．基于联合配送的城市物流配送路径优化 [J].控制与决策,2016,31(03):503-512.(Ge Xianlong,Xu Maozeng, Wang Weixin.Route optimization ofurban logistics in joint distribution [J]. Control and Decision,2016,31 (03): 503-512.)   
[26] Salhi S,Nagy G.A cluster insertion heuristic for single and multiple depot vehicle routing problems with backhauling[J].Journal of the Operational Research Society,1999,50 (10):1034-1042.