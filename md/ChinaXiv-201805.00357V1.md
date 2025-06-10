# 基于软件定义网络的域内路由保护方案研究

张举，耿海军(山西大学 软件学院，太原 030013)

摘要：软件定义网络（SDN）是一种将控制平面和转发平面分离的新型网络体系结构。由于其灵活性和可控性得到了业界的青睐。然而，目前 SDN采用最优路径转发报文，很难应对网络中频繁出现的节点或者链路故障。因此，为了提高 SDN网络的可用性，提出了一种基于软件定义网络的域内路由保护方案（intra-domain routing protection schemebased on software defined network，RPBSDN）。该方案可以为网络中的每个源-目的对计算出多个备份下一跳，利用节点加入到最短路径树的偏序关系来保证转发路径没有路由环路。实验结果表明，该方案不仅具有较小的计算复杂度，而且大大提高了网络的可用性。

关键词：软件定义网络；开放最短路径优先；备份下一跳；偏序关系 中图分类号：TP309.7 doi:10.3969/j.issn.1001-3695.2017.10.0951

# Research on intra-domain routing protection scheme based on software defined network

Zhang Ju, Geng Haijun (School ofSoftware Engineering Shanxi University,Taiyuan O3oo3,China)

Abstract: Software defined network (SDN)isanovel network architecture separating controlplane and forwarding plane.SDN has beenfavoredbytheindustrybecauseofitsflexibilityandcontrollbility.However,SDNusuallyemploys thebestpaths to forwardpackets,which isdificult todealwith thenodeorlinkfailures inthe network.Inorder toimprovetheavailabilityof SDN network,this paper proposed an intra-domain routing protection scheme based on SDN (RPBSDN).The scheme could calculate multiple backup nexthops foreach source-destination,and guaranteed loop-freeness ofthe induced forwardngpath bytheunderlying partial orderof the nodes.Theexperimental results showthatthe scheme notonlyhassmallcomputational complexity, but also greatly improve the availability of the network.

Key Words: software defined network; open shortest path first; backup next hop; partial order

# 0 引言

当前互联网的应用越来越普及，规模也随之增大，各种端系统的应用软件层出不穷，社会对互联网的依赖也越来越深，互联网已经深深的融入大众的日常生活中。但这些端系统的应用都依托于下面的网络层，是在IP之上的应用，因此IP层的路由设计是非常重要的。特别是某些实时性[1,2]的应用，如VoIP、股票行情交易软件和在线游戏等，它们对网络的可用性有更严格的要求。

目前，域内的路由都采用动态路由，比较典型的是OSPF协议。OSPF协议是要在源节点和目的节点间找出代价最小的一条路径，以此作为两节点间的路由。但当发生网络故障时，由于改变了域内统一的网络拓扑，需要花费时间完成收敛，并重新计算出路由，这个过程往往需要几秒甚至更多时间，而这对某些实时性要求高的应用来说，是不能满足性能需要的[3],甚至会造成重大损失。因此，如何在网络出现故障时对路由进行保护，防止网络服务出现中断，成为一个有现实意义的科学问题。

针对网络层的路由保护，学术界提出了一些方案。ECMP（equalcostmultiple paths）方案是一种通过管理员调整链路的代价，使得源节点和目的节点间出现多条代价相等的最短路径，以此来达到备份保护路径的目的，但有研究证明是NP-Hard问题[4]。LFA（loop freealternates），即无环可选下一跳机制，是基于IETF 提出的一种快速重路由方案，对应文档为RFC5286,由于简单，比较容易布署，该方案已经实现了一定程度的商业化。但其保护程度有限，有研究表明该方案的保护率约为 $50 \%$ 。多路由配置方案（multiple routing configurations，MRC）[5]则直接在路由设备中通过增加冗余路由进行路由保护，该方案可处理单节点路由故障，而不需要知道网络状态变化的原因。Not-Via非逐跳转发方式则用了两种地址，当分组遇到链路故障时，就将其按照Not-Via地址进行封装，绕开节点链路，到达预定节点后，再解封装，并按照IP网络的规则进行转发。这种方案计算量较大，也不利于实际部署。

以上研究方案中，或者复杂不易部署，或者需要管理员手动进行配置，也有容易部署但保护效果有限，但所有这些都是分布式的，每个节点要单独计算路由。SDN[可以为网络设计者提供了更大的灵活性，更加便于网络管理员配置网络。然而已有的 SDN 依然主要采用最短路径转发报文，当网络中有故障时，仍然需要重新收敛，计算新的路由表，在此期间报文可能会被丢弃。随着SDN技术的发展，该技术为解决网络中的故障提供了新的解决思路，相比于传统的网络体系结构，SDN在实现路由保护方面具有更强的优势[7-[9]，有很好的应用前景。欧盟的一项研究深入研究了SDN 网络中的故障恢复技术。作者在文献[10]中提出一种根据控制器调度的恢复方案，但是该方案具有较高的延迟。作者在文献[11]中提出，在OpenFlow 中增加FastFailover实现网络故障恢复。相关作者将SDN网络中的单故障恢复问题归结化一个整数规划模型[12]，从而利用启发式方法求出近似解。

因此本文所提算法在 SDN 中心节点实现，问题应用环境为域内的路由保护，开创性地将源和目的节点互换，通过一定的算法达到路由保护的目的，而 SDN中心节点与各数据平面内的通信及流表的生成则不在本文内研究。本文的方案只需要对已有的SDN协议做微小的调整就可以实现路由保护，并不会给控制节点带来额外的负担。其思路为在构造以目的为根的树的过程中对节点加入到该树的顺序进行编号，节点之间形成一个偏序关系，利用该偏序关系构造出源节点到目的节点的多条无环路径，从而保证报文转发的正确性。

# 1 域内 SDN 体系结构设计

在传统的网络体系结构中，网络中的路由设备被设计为控制和数据的统一，路由器既要运算并生成路由，还要实现高速转发。SDN的思想是将原来网络设备中的控制功能抽离出来，将它们集中到一个控制中心来实现，使数据面和控制面相分离，控制中心则集中于控制运算，而转发设备则专注于转发功能，向上(北向)提供可供开发的编程接口，而向下(南向）则将控制运算结果交给转发设备，形成一个三层体系结构，如图1所示。

基础设施层中的设备是通用转发设备，具体使用中的功能受控制层的控制，可以是传统的交换机、路由器、防火墙、流量监控系统等专用设备的功能。转发设备与控制层之间的通信接口使用Openflow，目前技术已比较成熟。

控制层是一个平台，维护着网络拓扑和一些状态信息等，并将网络控制功能向上提供API接口，向下则把控制下达给基础设施层中的通用设备。

应用层进行软件开发，调用控制层的API，实现网络的各种功能。

![](images/e1ac890fc08258193bdd7a38db28bbfa8bc24aac632495b666d43e1c6b64c23e.jpg)  
图1SDN体系结构

# 2 域内路由保护方案及算法

# 2.1算法描述

在已经得到域内全网拓扑图的基础上，以目标节点为根构造最短路径树，并对加入到树中的各节点按照加入次序由小到大编号，这样，每个节点可由自身节点开始，寻找编号比它本身编号小的邻居节点构造通往根的路径，而这样的路径可以不是唯一的。由于每个节点都采用这样的算法，就避免了路由环路的产生。

但由于是以目的节点为根构造的最短路径树，所以对某个节点来说，要得到所有n个目标节点的路由，就需要这样的n棵树。这对于单个节点来说是一个不小的负担，但对SDN的体系来说，却发挥了它的集中运算的优点。如此，就可以构造出到所有n个目的节点的多条路径，达到路由保护的目的。

# 2.2构造以目的节点为根的最短路径树

本文利用最短路径优先算法（shortestpath first，SPF）构造以v为根的最短路径树，此处节点v为目的节点。算法思路为：从根节点开始寻找距离最短的路径及相邻节点，并将其记入一个集合，称为入选路径集合。再以新入选的节点开始加入新的路径及节点，这个被扩充了的路径和节点集合称为备选路径集。从备选路径集中再寻找一个最短路径，并将其加入入选路径集合，接着再更新备选路径集。重复以上过程，直到所有节点全部加入到入选路径集中为止。

![](images/657d242623267485f8c6a18bf13d0fd4d45095f95f985f88dd9dbc0b59c0c935.jpg)  
图2网络拓扑结构

![](images/abcc2d997cfa5e8ae072b93d2920fa269a4317c18e1b7d089e0c9323e67f97d1.jpg)  
图3以节点v为根的最短路径树

![](images/a987a570238298b0e0e0ecc5fbca334c0bdf079b4665e8ef8e5f9d6bbb50c049.jpg)  
图4构造保护路径的例子

# 2.3构造保护路径

下面利用一个简单的例子来说明构造保护路径的基本思想。网络拓扑图如图2所示，包含6个节点和8条链路，其中链路中间的数字表示该链路的权值。根据3.2节中描述的算法可以构造出以节点v为根的最短路径树。如果在构造该树的过程中记录每个节点加入树的顺序，就可以得到图3。图3中的数字表示该节点加入到最短路径树的编号，按加入顺序从小到大编号。

当节点e收到目的地址为v的数据报时，就从目的地址为v 的最短路径树中查找下一跳转发地址，查找规则为节点编号比它自身编号小的相邻节点，此处应为d、b、a三个节点，如图4所示，虚线表示除最优路径外的保护路径。这样，就可以构造出去往目的节点的多条路径。按照编号从小到大的顺序分别为 $\cdot < _ { \mathrm { e , d , v } } >$ 、 $\mathbf { < e , b , v > }$ 、 $< _ { \mathrm { e , a , v } > }$ 。由于编号代表着该节点加入最短路径树的顺序，按照前面最短路径树的构造方法可知，这样的顺序也是一个代价从低到高的顺序，也就是路径优先级从高到低的顺序。

从实际拓扑图来看，节点e到节点v的路径除了$< \mathrm { e , d , v > < e , b , v > < e , a , v > }$ 三条外，还存在其他路径，比如通过节点c，如果可以这样，那么c执行同样的算法还可能会把分组再转发给节点e，这样就会造成路由环路。下面证明上述方法不会产生路由环路。

# 2.4无环路证明

定理当报文的目的地址为d时，节点c可以将该报文转发给它的任何一个邻居节点x，当且仅当节点c和节点 $\textbf { x }$ 满足sequencer $^ { \mathrm { ( d , x ) < } }$ sequence(d,c)，如果按照上述的条件转发报文，该报文的转发过程将不会出现环路。其中sequence $^ { \mathrm { ( d , x ) } }$ 表示在spt(d)中节点x加入到该树的顺序，sequence $( \mathrm { d } , \mathrm { d } ) { = } 1$ ，spt(d)表示

以节点d为根的最短路径树。

证明假设 ${ \mathfrak { p } } = ( \mathbf { u } _ { \mathrm { n } } , \mathbf { u } _ { \mathrm { n - 1 } } , \dots \mathbf { u } _ { \mathrm { 1 } } )$ 是报文的转发路径,应用上述规则将会得sequence $( \mathrm { d } , \mathrm { u _ { n } } ) >$ sequence( $\mathrm { \hat { \Omega } } _ { \mathrm { { d } , \mathrm { { u } } _ { \mathrm { { n } } } } }$ 1)>...>sequence $( \mathrm { d } , \mathrm { u } _ { 1 } )$ 。因此，可以得出这样的结论：任意两个相邻的节点存在一个严格的偏序关系，因此，该报文的转发过程将不会出现环路。

# 2.5 算法实现 (伪代码）

本节将详细描述算法RPBSDN的执行过程。第1\~4行将所有节点的访问标记属性设置为未访问，代价设置为无穷大，其中C(c,v）表示节点c到节点v的最小代价。第5\~7行将节点c的访问标记属性设置为已访问，代价设置为0，初始化seq 的数值。第8行将节点c加入到队列中。第10行选取一个节点出队列。第11行计算该节点加入到树中的序列，其中sequence(c,v）表示节点v加入到spt(c)中的序列。第13\~14 行更新节点v的访问标记和代价。第 $1 5 { \sim } 2 2$ 行更新节点v的邻居的属性。第24\~30行计算所有节点到节点c的下一跳集合，其中 bn(v,c)表示节点 $\mathbf { v }$ 到节点c的下一跳集合。

算法RPBSDN:

输入：网络拓扑结构 $\mathrm { G } = ( \mathrm { V } ; \mathrm { E } )$   
假设目的地址为c   
1 for $\mathbf { v } \in \mathbf { V }$ do   
2 $\mathrm { C } ( \mathrm { c } , \mathrm { v } ) \gets \infty ;$ （20   
3 v.visited $$ false;   
4 endfor   
5 c.visited $$ true;   
$6 \mathbf { C } ( \mathbf { c } , \mathbf { c } ) \gets 0 ;$   
7 seq←0   
8 Enqueue(Q; <c, 0 >);   
9 while Q is not empty do   
10 $< \mathbf { v } ,$ tc $> $ ExtractMin(Q);   
11 sequence $( { \bf c } , { \bf v } ) \gets { \bf s e q }$ ：   
12 seq++;   
13 v.visited $$ true;   
14 $\mathrm { C } ( \mathrm { c } , \mathrm { v } ) \gets \mathrm { t c } ;$ （20   
15 for each neighbor u of v do   
16 if u.visited $\ O =$ false then   
17 $\begin{array} { r } { \mathrm { n e w d i s t }  \mathrm { C } ( \mathrm { c } , \mathrm { v } ) + \mathrm { L } ( \mathrm { v } ; \mathrm { u } ) ; } \end{array}$ （204   
18 if newdist $< \mathrm { C } ( { \mathrm { c } , \mathrm { u } } )$ then   
19 Enqueue $( \mathrm { Q } ; < \mathrm { u } ,$ newdist $>$ ）   
20 endif   
21 endif   
22 endfor   
23 endwhile   
24 for （204 $\textbf { v } \in { \textbf { V } }$ do   
25 for each neighbor u of v do   
26 ifsequence(c,v)>sequence(c,u)   
27 bn(v,c)=bn(v,c) U {u}   
28 endif   
29 endfor   
30 ndfor

# 2.6 算法复杂度分析

算法RPBSDN主要包含三种优先级队列操作，分别是Enqueue、ExtractMin、Decrease-Key，本文用 $\mathrm { T _ { e } }$ 、 $\mathrm { T _ { x } }$ 和 ${ { \mathrm { T } } _ { \mathrm { k } } }$ 来表示三种操作所需要的时间，通过对这三种操作的调用来维护优先级队列Q。对于操作Enqueue 和ExtractMin，算法执行过程中最多调用V|次，而操作Decrease-Key 则最多调用|E|次。因此，该算法的复杂度为 $\mathrm { O ( | V | * T _ { e } + | V | * T _ { x } + | E | * T _ { k } ) } ,$ 。当使用斐波那契堆来实现优先级队列时， ${ \mathrm { T } } _ { \mathrm { e } } = \mathrm { O } ( 1 )$ ， $\mathrm { { T _ { x } } = \mathrm { { O } ( | g | V | ) } }$ ， ${ \mathrm { T } } _ { \mathrm { k } } = \mathrm O ( 1 )$ 。因此算法RPBSDN 的复杂度为 $\mathrm { O } ( | \mathrm { V } | ^ { \ast } \log ( | \mathrm { V } | ) + | \mathrm { E } | )$ 。

# 3 实验

本章对前面提出的算法RPBSDN进行实验模拟，先介绍实验方法，然后通过分析实验结果来说明算法性能。

# 3.1实验方法

1）实验拓扑

为了更真实全面的对算法进行评测，这里采用了多种拓扑结构。

（a）美国教育科研网Abilene[13]，这是美国教育科研网的真实拓扑结构，其中包括14条边和11个节点。

（b）使用了Rocketfuel项目[14]中公开的拓扑，本实验从中选取特征差别比较明显的五个拓扑来作为实验案例，这五个拓扑的节点数量和链路数量分别为Telstra（108，153）、Ebone（87，162）、Tiscali（161，328）、Exodus（79，147）、Abovenet（141，748）。

（c）利用开源软件Brite[15]来有目的的生成一些拓扑结构来丰富实验案例，有助于对算法进行较为全面的评测，此处生成的拓扑节点数量为20\~200。

# 2）实验评价指标

基于本文算法的目的，在此设计两个评价指标，分别是下一跳平均个数和计算效率。在实验中将RPBSDN和 SDN-SPF[9]进行比较。SDN-SPF采用 SDN方式实现了OSPF协议，并且采用最短路径转发报文。

3）实验中，利用一台PC机运行OpenDaylight控制器来获取网络拓扑结构和计算网络中的路由，另外一台PC 机运行Mininet 和OpenvSwitch，从而可以生成多种多样的拓扑结构。

# 3.2 下一跳平均个数

下一跳平均个数可以定义为总的下一跳个数 $\langle ( \mathbf { n } ^ { * } ( \mathbf { n } { - } 1 ) )$ ，其中n为拓扑中的节点个数。从该定义可以知道，下一跳平均个数越多，网络的可用性越高。

图5和6是利用Brite软件生成的拓扑。图5中拓扑的节点平均度为4，对节点数量进行了改变。图6中改变了拓扑的节点平均度，保持拓扑中的节点数量不变，均为200个。

![](images/832ead8418687235957b4599f031d544c6f53f6cd6f1a5eeb35ba26a4001e190.jpg)  
图5平均下一跳个数和拓扑大小的关系

![](images/a4fbc5ff513bbaa65ba0a1cc3270576da9b06255109abe520601ab4d689f2ff2.jpg)  
图6平均下一跳个数和节点平均度的关系

![](images/b3e885db508073397b61b86181e3e4bf8c9c408589a2b055fbde0d5bc72cb05d.jpg)  
图7不同算法在 Abilene 和Rocketfuel 中的平均下一跳

从图5、6可以看出，节点中路由的平均下一跳个数与其平均度相近，这主要是因为用Brite 软件生成的拓扑较规则，连通度较好。相比较OSPF-SPF算法来说，RPBSDN路由有更多的选择，达到了路由保护的目的。图7中的拓扑选取了美国教育科研网Abilene 和Rocketfuel项目中公开的几个拓扑。从图中可以看出，Abilene 的平均下一跳为1.4，数值最小；Abovenet的平均下一跳最大，为5.21，主要原因在于其网络拓扑的连通度不同。连通度越大，平均下一跳个数也越多，符合RPBSDN预期。

# 3.3计算效率

为了消除不确定因素的影响，计算效率用构造最短路径树的次数来模拟。从图8来看，在所有拓扑结构中OSPF-SPF和RPBSDN的计算效率都是一样的。这是因为在SDN中，控制器需要为所有节点计算路由表，如果将RPBSDN部署在SDN中，控制器需要执行|V|次RPBSDN 算法，所以复杂度为V|O(|VI$^ { * } \log ( | \mathrm { V } | ) + | \mathrm { E } | )$ ，同样OSPF-SPF也需要为网络中所有节点计算路由表，控制器需要执行V次 SPF算法，其复杂度同样为$| \mathrm { V } | \mathrm { O } ( | \mathrm { V } | ^ { \ast } \log ( | \mathrm { V } | ) + | \mathrm { E } | )$ 。所以，如果在SDN中实现OSPF-SPF和RPBSDN，其复杂度是一样的。

![](images/ec6255de3cbfdeea8166e208ca202f892231c20e8cd26daa166e839126779334.jpg)  
图8不同算法在Abilene 和Rocketfuel中的计算效率

# 4 结束语

因特网中，域内路由协议多采用OSPF，由于该协议使用了Dijkstra 提出的最短路径算法 SPF，所以针对某一目的地，下一跳只取最短路径。这样，当链路出现故障时，直到新的路由生成，网络通信处于不正常状态。RPBSDN可以针对某一目的地生成多条路由，增加了网络的可靠性，形成路由保护。

另外，鉴于SDN应用的快速发展，本文将算法放在SDN中心节点来实现，依靠 SDN中心的强大计算能力，能更加发挥RPBSDN的优点。但限于环境等因素，本文在实验中对SDN 环境的模拟还不够真实，这也是下一步要做的工作。

# 参考文献：

[1]李清.基于弱转发的互联网路由可用性和扩展性研究[D].北京：清华 大学,2013.   
[2]Zheng J,Xu H, Zhu X,et al.We've got you covered: failure recovery with backup tunnels in traffic engineering $[ \mathrm { C } ] / \hbar$ Proc of IEEE International

Conference on Network Protocols. 2016: 1-10. [3]耿海军．基于路由度量的域内多路径路由研究[D].北京：清华大学, 2015. [4]Sridharan A, Guerin R, Diot C.Achieving near-optimal traffic engineering solutions for current ospf//s-is networks [J]. IEEE//ACM Trans on Networking,2005,13 (2): 234-247. [5]Kvalbein A,Hansen AF, Cicic T,et al.Fast IP network recovery using multiple routing configurations [C]// Proc of IEEE International Conference on Computer Communications.2007: 1-11. [6]张朝昆，崔勇，唐骂祎，等．软件定义网络（SDN）研究进展[J].软件 学报,2015,26(1): 62-81. [7]Sharma S,Staessens D, Colle D,et al.Fast failure recovery for in-band OpenFlow networks [C]// Proc of the 9th International Conference on Design of Reliable Communication Networks.2013: 52-59. [8] Hartert R,Vissicchio S,Schaus P,et al.A declarative and expressive approach to control forwarding paths in carrier-grade Networks [J].ACM Sigcomm Computer Communication Review,2015,45 (5): 15-28. [9] Diego Kreutz, Ramos F M V,Verissimo P E,et al. Software-defined networking: a comprehensive survey[J]. Proceedings of the IEEE,2015, 103 (1): 14-76. [10] Sharma S,Staessens D,Colle D,et al. Enabling fast failure recovery in OpenFlow networks [C]//Proc of the 8th International Workshop on Design of Reliable Communication Networks.2011: 164-171. [11] Sharma S,Staessens D, Colle D,et al. OpenFlow: Meeting carrier-grade recovery requirements [J]. Computer Communications,2013,36 (6): 656- 665. [12] Hao F,Kodialam M,Lakshman T V. Optimizing restoration with segment routing [C]// Proc of the 35th Annual IEEE International Conference on Computer Communications.2016: 1-9. [13] Advanced networking for research and education.[EB/OL]. https://www. internet2. edu/products-services/advanced-networking. [14] Spring N,Mahajan R,Wetherall D,et al. Measuring ISP topologies with rocketfuel[J]. IEEE//ACM Trans on Networking,2004,12(1): 2-16. [15] htp://www. cs.bu.edu/brite [EB/OL].