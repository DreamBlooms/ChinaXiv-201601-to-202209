# 基于布尔函数的网络可达性验证方法

张立群，林海涛，沈钊(海军工程大学 电子工程学院，武汉 430000)

摘要：针对 SDN 网络中由于不同应用的转发路径交叠等导致的数据平面配置问题，提出一种基于布尔函数的网络可达性验证方法。首先，将网络拓扑抽象为端口拓扑并计算端口邻接矩阵；之后，生成网络的路径空间和各端口的转发函数并计算每条路径的路径函数；最后通过判断路径函数的可满足性来确定路径的可达性。通过仿真实验，对网络拓扑和流规则规模等因素对算法验证效率的影响进行研究，并将所提方法与APV和DASDA进行性能比较。实验结果表明，所提方法能够有效检测 SDN 网络中的流规则配置问题。随着网络中环路的增加和流规则规模的增长，验证网络所需的时间开销逐渐增加。其中，网络拓扑对路径生成时间影响较大，而转发函数的生成时间则主要受流规则规模的影响。所提方法的验证时间相较于APV和DASDA分别平均缩短约 $5 3 . 7 6 \%$ 和 $2 7 . 7 4 \%$ 。

关键词：软件定义网络；规则配置；可达性验证；布尔函数 中图分类号：TP393.08 doi: 10.19734/j.issn.1001-3695.2022.01.0049

Network reachability verification method based on Boolean functions

Zhang Liqun, Lin Haitao, Shen Zhao† (College ofElectronics Engineering,Naval University of Engineering,Wuhan 43ooo0,China)

Abstract: Aiming atthe data planeconfiguration problemcaused byoverlappng forwarding pathsof diferent applications in SDN network,thispaper proposesaBoolean function-based network reachabilityverification method.First,itabstracts thenetwork topology intoporttopologyandcalculates theportadjacencymatrix;then generates thepath spaceofthenetwork andthe forwarding functionofeachport,andcalculates thepath functionofeachpath;finaly,itjudges theaccesibilityof path fromthesatisfiabilityofpath function.Through simulation experiments,this paper studies theinfluenceoffactors such as network topologyand flowrulescaleonthealgorithmverification efficiency,andtheperformance ofthe proposedmethod is compared with APVand DASDA.Experimental results show that the proposed methodcan effectivelydetect flow rule configuration problems inSDNnetworks.Aste numberofloops inthe network increasesandthe sizeof the flowrules grows, thetimeverheadrequiredtoverify thenetwork graduallincreases.Among them,thenetworktopologyhasagreatinfluence on the path generationtime,and the generation timeofthe forwarding function ismainlyaffected bythescaleofthe flow rule. Compared with APV and DASDA,the time to verify is shortened by an average of about $5 3 . 7 6 \%$ and $2 7 . 7 4 \%$ respectively.

Key words: software defined network;rule configuration; reachability verification; Boolean functions

# 0 引言

为了适应新的网络需求，传统网络体系架构经过几十年的发展增加了大量的网络协议，这使得整个网络变得臃肿不堪[1]。为重新定义网络架构，斯坦福大学在2006年的CleanSlate项目中提出了软件定义网络[2](SoftwareDefinedNetwork，SDN)。SDN 的基本理念是构建一个网络操作系统，使得仅在控制器软件上进行网络编程就能管控所有网络流量。相较于传统网络架构，SDN架构具有较好的扩展性、强大的灵活性和快速响应性等特点，被广泛应用于物联网和5G 开发等大规模网络应用[3,4]。

但SDN也还存在着一些问题，可能导致严重的网络安全事故[5]。首先，部署在控制器中的多个应用对同一转发平面进行操作，使得不同应用的转发路径相互交叠，可能出现多应用的不当依赖。这种不当依赖使得真实的转发平面与管理员预期不符，出现转发环路、非法可达路径以及数据阻塞等网络问题，影响网络的安全和转发性能[6]，如图1(a)所示。其次，在主流的南向协议OpenFlow中定义了基于传输层安全性协议(Transport Layer Security，TLS)的 OpenFlow 通道,用于实现控制器对交换机的管理。但由于TLS协议的复杂性管理员一般使用明文对交换机进行配置管理[7]。这使得在SDN 中发生中间人攻击的概率要大于传统网络[8]。攻击者会利用OpenFlow协议实现欺骗拦截，阻止正常的流量传输，或者在交换机中添加新的流规则，控制数据包转发，使网络平面脱离管理员控制[9]，如图1(b)所示。目前，SDN中缺乏有效的网络验证机制，难以应对这些控制平面的配置错误和网络攻击[10]。为此，对网络可达性验证的研究具有重要的应用价值。

# 1 相关工作

文献[11]提出一种NetPlumber工具，NetPlumber基于头空间分析[12](Header Space Analysis，HSA)创建并维护流规则之间的依赖关系图，该图将流规则使用管道连接，两流规则的匹配域交集作为管道的过滤器，以增量的方式动态检查状态的合法性变化。文献[13]提出的NetV同样是基于HAS的网络分析工具。与NetPlumber相比，NetV使用二元决策图解决了通配符表达式在多次并集和差分操作后的爆炸问题，减少了使用不同通配符筛选器执行相同行为规则的冗余。

文献[14]提出一种高效的流规则冲突检测方法。通过对全网规则的匹配域进行编码，实现对流规则的压缩，进而对全网规则冲突的检测。但由于对规则进行压缩，使得可能在检测过程中出现虚报。文献[15]提出了一种基于原子谓词验证(AtomicPredicatesVerifier，APV)的方法，该方法通过将访问控制列表(Access ControlLists，ACL)和转发表(ForwardInformationdataBase，FIB)构造成端口谓词，并计算谓词集合的原子谓词集。然后使用整数集合来表示各个转发谓词，构建转发图验证网络可达性。但当其网络数目较多时，需要计算大量的原子谓词。并且当原子谓词集合进行更新时，表示端口谓词的整数集合也需要进行调整，验证效率较低。文献[16]提出了一种轻量级的包转发验证方案(LightweightPacketForwardingVerification，LPV)，通过对交换机出口和入口的随机采样，比对采样包中的相关信息判断网络中的异常转发。但由于需要不断采样和上传，增加了转发延迟和通信开销。文献[17]提出一种基于形式化验证的冲突检测解决方案

DASDA。DASDA通过底层配置和转发平面快照验证SDN拓扑中所有网络设备的行为。交换机中的流规则被抽象为流规则决策图(Flow entries Decision Diagram，FeDD)，FeDD中的路径节点代表数据包的各个匹配字段，路径终点记录着数据包在网络中的所有动作。当交换机数目较少时，算法检测速度相对较快。文献[18]提出一种方法来验证请求的路径集合会不会发生配置错误。但该方法只对路径集合进行了分析，并没有结合具体的流规则。

针对上述研究存在的虚假预警、验证效率低以及通信开销增加等问题，本文提出一种基于布尔函数的网络可达性验证(Reachability Verification Based on Boolean Functions,RVBBF)方法，RVBBF使用控制器中已有的网络拓扑和流规则信息，无须与转发平面进行频繁通信，减小了通信开销；并且该方法使用布尔函数对未压缩的流规则匹配域进行描述，结合物理路径对数据平面中的可达性和转发环路进行检测，消除了虚假预警，提高了验证效率，增强了SDN的安全性。

![](images/b59635396d93458bbb430adcd2fc720fe154bdc667808b244cccebcaafb6368d.jpg)  
Fig.1Network scenes

图1网络场景

# 2 网络模型

对于每一个数据包，其都有着确定的源IP地址，记作 $I P _ { s }$ 和目的IP地址，记作 $I P _ { D }$ 。在 $\scriptstyle { \mathrm { I P v 4 } }$ 网络中，网络地址由32位比特序列表示，本文将数据包抽象为一个64 位的比特序列(该方法同样可拓展应用于IPv6)，其中前32位表示 $I P _ { s }$ ，后32位表示 $I P _ { D }$ 。整个数据包空间 $\Omega$ 可以表示为

$$
\Omega = \{ ( a _ { 0 } , \cdots , a _ { 6 3 } ) | a _ { i } \in \{ 0 , 1 \} \}
$$

当数据包到达交换机时，会将数据包的包头信息与流规则进行匹配，并根据规则定义的动作处理数据包。流规则一般包含匹配域、动作域、优先级以及计数器等字段。为简化问题，使得仅通过布尔运算就能判断数据包与流规则的匹配关系以及求解流规则所能匹配的数据包集合，作出如下定义，定义1流规则格式定义如式(2)所示。

$$
R \mathrel { \mathop : } < s w , p r i , M , a c t i o n >
$$

其中， $s w$ 记录规则所在的交换机； $p r i$ 表示规则的优先级，其取值为 $[ 0 , 6 5 5 3 5 ]$ 内的整数，数值越大则优先级越高；匹配域$M = ( N e t _ { s } , N e t _ { D } )$ ， $N e t _ { s }$ 和 $N e t _ { D }$ 分别表示规则匹配的源地址网络和目的地址网络，两者皆为前缀匹配字段；action为动作域，表示交换机对数据包的操作。当该数据包到达 $s w$ 时，将按照

所匹配规则的action进行操作。

定义2交换机对数据包的操作包含转发和丢弃两种，对动作域action使用式(3)描述。

$$
a c t i o n = f w d ( E t h )
$$

对于转发动作，使用本地端口 $E t h$ 描述，表示将数据包从对应端口转发；对于丢弃动作，可认为交换机将数据包从特殊的端口 $E t h _ { d }$ 转发，即 $a c t i o n = f w d ( E t h _ { d } )$ 。

定义3对于任意流规则 $R$ ，其可匹配的数据包空间为$\Omega _ { R }$ ，则一定存在一个64元的布尔函数 $B$ ，使得

$$
\{ \begin{array} { c } { B ( \omega ) = T r u e , \forall \omega \in \Omega _ { R } } \\ { \xi \in \Omega _ { R } , \forall \xi \in \{ \xi | B ( \xi ) = T r u e \} } \end{array} 
$$

称 $B$ 为流规则 $R$ 的匹配函数，形式如下：

$$
B { = } \nu _ { 0 } \wedge \nu _ { 1 } \wedge { \cdots } \wedge \nu _ { 6 3 }
$$

对于匹配函数存在下列性质：

性质1对于数据包 $a _ { 6 }$ 和匹配函数 $B$ ，若 $B ( \omega _ { \mathrm { b } } ) = T r u e$ ，则 $a _ { 6 }$ 匹配流规则；否则数据包与该流规则不匹配。

性质2　若 $B$ 为某一流规则的匹配函数，则 $B ( \omega ) = T r u e$ 的解空间，即为该规则所有可匹配的数据包。

性质3存在两个特殊的匹配函数 $B _ { T }$ 和 $B _ { F }$ ，分别有

$$
B _ { r } ( \omega ) = T r u e , \forall \omega \in \Omega
$$

$$
B _ { F } ( \omega ) = F a l s e , \forall \omega \in \Omega
$$

值得注意的是，并非所有匹配函数都具有全部的64个比特变量。例如，存在流规则 $R$ ，其匹配域 $M = ( 1 9 2 . 1 6 8 . 0 . 0 / 1 6 , 1 0 . 0 . 0 . 0 / 8 )$ ，则 $B _ { R }$ 如下所示，

$$
B _ { R } = \nu _ { 0 } \wedge \nu _ { 1 } \wedge \neg \nu _ { 2 } \wedge \neg \nu _ { 3 } \wedge \neg \nu _ { 4 } \wedge \neg \nu _ { 5 } \wedge \neg \nu _ { 6 } \wedge \neg \nu _ { 7 } \wedge
$$

$$
\nu _ { 8 } \wedge \neg \nu _ { 9 } \wedge \nu _ { 1 0 } \wedge \neg \nu _ { 1 1 } \wedge \nu _ { 1 2 } \wedge \neg \nu _ { 1 3 } \wedge \neg \nu _ { 1 4 } \wedge \neg \nu _ { 1 5 } \wedge
$$

$$
\neg \nu _ { 3 2 } \wedge \neg \nu _ { 3 3 } \wedge \neg \nu _ { 3 4 } \wedge \neg \nu _ { 3 5 } \wedge \nu _ { 3 6 } \wedge \neg \nu _ { 3 7 } \wedge \nu _ { 3 8 } \wedge \neg \nu _ { 3 9 }
$$

在 $B _ { R }$ 中只包含24个比特变量，这是由于 $N e t _ { s }$ 和 $N e t _ { D }$ 的网络前缀分别为16和8。对于 $N e t _ { s }$ 来说，需要从 $\nu _ { 0 }$ 到 $\nu _ { 1 5 }$ 的16个比特变量即可表示；同理对于 $N e t _ { D }$ 则只需从 $\nu _ { 3 2 }$ 到 $\nu _ { 3 9 }$ 的8个比特变量。

本文使用二元决策图[19](Binary Decision Diagram,BDD)来对布尔函数进行表示。BDD是用于表示布尔函数的有向无环图，可以极大的减小验证布尔函数满足性需要的时间开销，其结构如图2所示。

![](images/f3b97809dd1aa72e6744b5cb204b0641dcedf4a0507327f27ad91d22f678f74d.jpg)  
图2 函数 $B = \nu _ { 0 } \nu _ { 1 } \nu _ { 2 } \lnot \nu _ { 3 }$ 的BDDFig. 2 The BDD of $B = \nu _ { 0 } \nu _ { 1 } \nu _ { 2 } \lnot \nu _ { 3 }$

# 3 基于布尔函数的网络可达性验证

为解决SDN网络中缺乏可达性验证机制的问题，基于上一节的网络模型提出一种基于布尔函数的网络可达性验证方法。RVBBF的工作流程包括四部分：抽象端口拓扑、计算转发函数、生成路径空间和路径验证，其流程结构如图3所示。

RVBBF对流规则和数据包的匹配关系用布尔函数进行描述，并使用路径搜索算法对转发平面的拓扑结构进行搜索生成路径空间，将网络可达性问题转换为布尔可满足性问题(BooleanSatisfiabilityProblem，SAT)，使得仅通过简单的逻辑运算就能够验证网络端到端的可达性。为提高验证效率，RVBBF对生成路径空间和计算转发函数两阶段做并行处理，使二者同时进行；并且使用BDD 结构表示方法中的布尔函数，有效缩短路径验证时间。

下面将对RVBBF的各阶段工作进行详细描述。

![](images/90ced0f518586641ee7129c68a4836d30d124333c6bf36d8fc8268366b138400.jpg)  
图3工作流程结构

# 3.1抽象端口拓扑

对网络的物理拓扑进行抽象，可得网络的端口拓扑，如图4所示。在端口拓扑中，节点表示设备端口，分为交换机节点和主机节点；边则表示端口之间的连接关系，实线为外部连接，即端口位于不同交换机且存在物理链路；虚线为内部连接，即端口位于同一交换机。

![](images/8c6f2daa17c15743abfd7788e83757b9425a3755224e6c9cf763f72f05ac9b62.jpg)  
Fig.3The method flow structure   
图4端口拓扑抽象  
Fig.4Port abstraction

为方便后续研究，将 $< s w , e t h >$ 映射为全局端口 $P$ ，映射规则记为 $D$ 。例如在上述拓扑中有，

$$
\begin{array} { r l } & { D [ < \mathrm { S w } 1 , \mathrm { E t h } . 0 > ]  \mathrm { P } _ { 1 } } \\ & { D [ < \mathrm { S w } 1 , \mathrm { E t h } . 1 > ]  \mathrm { P } _ { 0 } } \\ & { \qquad \vdots } \end{array}
$$

由 $D$ 和各端口的连接关系，可得网络拓扑的邻接矩阵 $\scriptstyle { E }$ ，其中 $e _ { i j } \in \{ - 1 , 0 , 1 \}$ 表示端口 $\mathbf { P } _ { i }$ 和 $\mathbf { P } _ { j }$ 的连接关系。若 $e _ { i j } = - 1$ ，表示两节点为内部连接；若 $e _ { i j } = 0$ ，表示两节点无连接；若 $e _ { i j } = 1$ ，则表示两节点为外部连接。上述拓扑的邻接矩阵如下所示：

$$
E = \left[ \begin{array} { c c c c c c c c c c c c c c c } { 0 } & { - 1 } & { - 1 } & { 1 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } \\ { - 1 } & { 0 } & { - 1 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 1 } & { 0 } \\ { - 1 } & { - 1 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 1 } & { 0 } & { 0 } \\ { \vdots } & { \vdots } & { \vdots } & & & & & { \ddots } & & & & & { \vdots } \\ { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 1 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } & { 0 } \end{array} \right]
$$

# 3.2计算转发函数

匹配函数 $B$ 可以求得流规则所匹配的数据包，但在交换机内部存在大量的流规则，并且优先级和转发端口各异，难以用其表征交换机的转发动作。为此类比匹配函数，对转发函数进行如下定义：

定义4对于任意的交换机端口 $P$ ，通过其转发的数据包空间为 $\Omega _ { { P } }$ ，则一定存在一个64元的布尔函数 $F _ { P }$ ，使得

$$
\{ \begin{array} { c } { F _ { P } ( \omega ) = T r u e , \forall \omega \in \Omega _ { P } } \\ { \xi \in \Omega _ { P } , \forall \xi \in \{ \xi | F _ { P } ( \xi ) = T r u e \} } \end{array} 
$$

称布尔函数 $F _ { P }$ 为端口 $P$ 的转发函数。

根据流规则集合和 $D$ 可计算任意端口的转发函数 $F _ { P }$ ，其

步骤如下：

首先，通过算法1，对获取的流规则进行预处理，计算其匹配函数，并将端口映射为全局端口，得到使用匹配函数表示的流规则 $< s w , p r i , B , P >$ 。

算法1流规则预处理  
输入： <sw,pri,M,action $>$ ， $D$ 。  
输出： $< s w , p r i , B , P >$ 。  
1 $M ^ { \prime } \gets \mathrm { t r a n } ( M )$   
2 $B  B _ { T }$ ;  
3 for $i \gets 1$ to $\mathrm { l e n } ( M )$ do  
4 switch( $M ^ { \prime } [ i ] )$ （20  
5 case 0:  
6 $B \gets B \land \nu _ { i }$ :  
7 case 1:  
8 $B \gets B \land \neg \nu _ { i }$   
9 case \* :  
10 Skip;  
11 end switch  
12 end for  
13 $E t h  \mathrm { g e t \_ E t h } ( \mathrm { a c t i o n } )$   
14 $P \gets D [ < s w , E t h > ]$   
15 return $< s w , p r i , B , P >$   
在算法1中，函数tranO将 $M$ 转换为三元序列

$M ^ { \prime }$ ，

$$
M ^ { \prime } \in \{ ( m _ { 0 } , \cdots , m _ { 6 3 } ) | m _ { i } \in \{ 0 , 1 , ^ { * } \} \}
$$

其中， $( m _ { 0 } , \cdots , m _ { 3 1 } )$ 表示 $N e t _ { s }$ ， $( m _ { 3 2 } , \cdots m _ { 6 3 } )$ 表示 $N e t _ { D }$ ， $*$ 为通配符。若 $M ^ { \prime }$ 的第 $i$ 位为1或0，取位变量 $\nu _ { i }$ 或 $\neg \nu _ { i }$ ；若第 $i$ 位为 $*$ ，则跳过位变量 $\nu _ { i }$ 。所有位变量的析取即为该流规则的匹配函数。get_EthO则根据action 获取本地转发端口 $E t h$ ，之后根据$D$ 将 $< s w , E t h >$ 映射为 $P$ 。

数据包在交换机内进行规则匹配时，是按照优先级进行的，数值越大，优先级越高。为实现对同一交换机中高优先级的流规则优先处理，将规则以 $( s w , p r i )$ 为关键字进行排序，其中 $s w$ 为主关键字，进行升序排列， $p r i$ 为次关键字，进行降序排列。可得到有序的流规则列表，如下所示，

$$
\begin{array} { c } { { < s w _ { 1 } , p r i _ { 1 } , B _ { 1 } , P _ { 1 } > } } \\ { { \vdots } } \\ { { < s w _ { j } , p r i _ { j } , B _ { j } , P _ { j } > } } \\ { { \vdots } } \\ { { \ddots } } \\ { { \langle s w _ { n } , p r i _ { n } , B _ { m } , P _ { m } > } } \end{array}
$$

其中，对于相同 $s w$ 的规则,若 $j < k$ ，有 $p r i _ { j } \geq p r i _ { k }$ 0

最后通过算法2，根据有序的规则列表和端口集合，计算各个端口的转发函数。

算法2计算转发函数

输入：有序的流规则列表，端口集合 $\{ 1 , 2 , \cdots , \ n \}$ 。  
输出：转发函数集合 $\{ F _ { 1 } , \cdots , F _ { n } \}$ 。  
1for $j \gets 1$ to $n$ do  
2 $F _ { j } \gets B _ { F }$ ：  
3 end for  
4 （204号 $f d \gets B _ { F }$ ;  
5 $s \gets s w _ { 1 }$ ;  
6 $i \gets 1$ ;  
7 while $i \leq m$ do  
8 if $s w _ { i } = s$ then  
9 $\begin{array} { r l } & { F _ { P _ { i } } \gets F _ { P _ { i } } \lor ( B _ { i } \land \neg f d ) } \\ & { f d \gets f d \lor B _ { i } } \\ & { i \gets i + 1 } \end{array}$   
10  
11  
12 else  
13 $f d \gets B _ { F }$   
14 $s \gets s w _ { i }$   
15 $i \gets i$ （20  
16 end if  
17 end while  
18 return $\{ F _ { 1 } , F _ { 2 } , \cdots , F _ { n } \}$

# 3.3 生成路径空间

按照真实网络中的转发模式，数据包一般是从交换机的某一端口 $\mathbf { P } _ { \mathrm { M } }$ 进入，通过内部连接到转发端口 $\mathbf { P } _ { \mathrm { N } }$ ，然后从 $\mathbf { P } _ { \mathrm { N } }$ 通过外部连接转发至另一交换机的端口 $\mathbf { P } _ { \mathrm { X } }$ 进入交换机，不断重复，如图5所示。为此，根据邻接矩阵 $E$ 和起始端口 $P$ ，可生成 $P$ 的路径空间 $S e t _ { P }$ 。

![](images/f16b3673fca7a45bf0f22c34f40021a434bd2be97cceddb901c3b79c7d70472d.jpg)  
图5数据包转发示意图  
Fig.5Schematic diagramof packet forwarding

路径空间中的基本元素是物理可达路径path，并具有以下特点：a)path以某一主机节点作为起始节点，通过外部连接与交换机节点相连，而后通过内部连接与同一交换机的节点相连，交替进行；b)当访问到已访问过交换机的节点时，path结束；c)当访问到已访问过的节点时，path结束；d)当访问到主机节点时，path 结束。

通过基于深度优先搜索(DepthFirst Search,DFS)的算法3,可由拓扑的邻接矩阵和起始节点，生成路径空间 $S e t _ { P }$ 。

算法3生成路径空间

输入：邻接矩阵 $E$ ，起始节点 $P$ 。  
输出：路径空间 $S e t _ { P } = \{ p a t h _ { 1 } , \cdots p a t h _ { k } \}$ 。  
1 （204号 $n o w { = } P$ : $S e t _ { P } \gets \emptyset$ :  
2 （20 $p a t h \gets [ n o w ]$ ;  
3 while True do  
4 while True do  
5 if find_next(now） then  
6 $n o w \mathrm { {  } f i n d \_ n e x t { ( n o w ) } } \ ;$   
7 else  
8 break;  
9 end if  
10 path.append(now)  
11 if now or（now.Sw is visited） then  
12 break;  
13 end if  
14 end while  
15 $S e t _ { P } \gets S e t _ { P } \bigcup \{ p a t h \}$   
16 while continue_back do  
17 path.popO  
18 if $l e n ( p a t h ) = 0$ then  
19 break;  
20 end if  
21 $n o w \gets p a t h [ - 1 ]$   
22 end while  
23 if find_over( then  
24 break  
25 end if  
26 end while  
27 return $S e t _ { P }$ （204  
中，函数 find nextO可以返回当前正在访问节占nowi

尚未访问的下一跳节点；当mow的所有可达节点都被访问过后，continue_backO返回 $T r u e$ ，路径回溯；若 $n o w { = } P$ 且 $n o w$ 的所有可达节点都已访问，则所有路径都已经找到，函数check_overO返回为True，算法结束并返回路径空间 $S e t _ { P }$ 。

# 3.4路径验证

$S e t _ { P }$ 中的path只是物理可达并不一定逻辑可达，即交换机不一定存在相应的流规则来转发数据包。通过算法4，对所有的物理可达路径进行验证，在这个过程中，可以检测路径包含的环路以及可达性。

算法4路径可达性验证

输入：路径空间 $S e t _ { P }$ ，转发函数集 $\{ F _ { 1 } , \cdots , F _ { n } \}$ 。  
输出：循环路径空间 $\dot { C } i r$ 、可达路径空间 $R e a$ 。  
1for path in $S e t _ { P }$ do  
2 $B _ { p t }  B _ { T } \mathrm { ~ ; ~ }$ （204号  
3 for $P$ in path do  
4 if $P$ is Output then  
5 $B _ { p t }  B _ { p t } \land F _ { P } \ ;$   
6 end if  
7 end for  
8 if SAT（ $B _ { p t }$ ）then  
9 ifpath.tail in path-path.tail then  
10 $C i r \gets C i r \mathsf { U } \{ p a t h \} \ ;$   
11 else  
12 $R e a \gets R e a \bigcup \{ p a t h \} \ ;$   
13 end if  
14 end if  
15 end for  
16 return $C i r$ ，Rea

算法4通过遍历路径空间，对路径中输出端口的转发函数 $F$ 进行合取得到路径函数 $B _ { p t }$ ，然后对 $B _ { p t }$ 进行 SAT 验证。若存在可满足的解，则存在数据包能够同时通过路径上所有的转发端口，其解空间就是可通过该路径的数据包集合，路径存在逻辑通路。之后再对路径属性进行判断，若路径的终端节点在路径中重复出现，则表明该路径是循环路径，否则为单向可达路径。若解不存在，说明不存在数据包可以通过该条路径上所有转发端口，即路径逻辑不可达。

# 4 实验分析

# 4.1实验条件

本文实验计算机的配置如下：IntelCorei7-9750HCPU$2 . 6 \mathrm { G H z }$ 处理器，16GB内存，Win10操作系统。在VisualStudioCode 平台上基于Python 语言对该方法进行实现。在性能分

析实验中不同规模的流规则集合为通过使用Classbench工具随机生成。

# 4.2 实验结果与分析

4.2.1有效性分析

为验证RVBBF的有效性，对引言中所提的网络场景进行分析验证，其端口拓扑(省略内部连接)及映射关系如图6所示。以H1(在两图中均为节点9)为起始节点生成路径空间，两场景的路径空间如表1所示(加粗路径表示逻辑可达)。

![](images/7b5ef512062f50e4f3a55478c4a745f20cc52db2e6f15f3ded31ba8b12fb19d0.jpg)  
Fig.6Port representation of the example scene

表1不同场景的路径空间  
Tab.1Path space for different scenes   

<html><body><table><tr><td>Scene Number</td><td>Path space</td></tr><tr><td rowspan="5">Scene 1</td><td>[9,0,1,10]</td></tr><tr><td>[9,0,3,4,5,6,7,2]</td></tr><tr><td>[9,0,3,4,5,6,8,11]</td></tr><tr><td>[9,0,2,7,6,5,4,3]</td></tr><tr><td>[9,0,2,7,8,11]</td></tr><tr><td rowspan="4">Scene 2</td><td>[9,0,4]</td></tr><tr><td>[9,0,1,10]</td></tr><tr><td>[9,0,2,7,8,11]</td></tr><tr><td>[9,0,3,5,6,12]</td></tr></table></body></html>

结合转发函数对表1路径进行验证，发现场景1中存在一条转发环路[9,0,3,4,5,6,7,2]和一条非法可达路径[9,0,1,10];在场景2中则只有一条数据通路[9.0,4]，其中节点4为$< S w 0 , E t h _ { d } >$ ，表明Sw1可能受到攻击或规则设置错误，造成数据阻塞。结果表明，RVBBF能够有效检测网络中由于应用的不当依赖和网络攻击导致的流规则冲突。

# 4.2.2性能分析

为验证RVBBF的性能，本小节通过改变网络拓扑和流规则数目等参数，对算法各部分验证效率进行分析。为提高准确性，本节数据均为多次实验取平均值。

1）网络拓扑对生成路径空间的影响

在实验中设置5台交换机，分别组成线形、环形和网状3种典型的基本网络拓扑，如图7所示。通过改变不同拓扑下的终端主机数量，研究网络拓扑对路径空间生成时间的影响，实验结果如图8。各个拓扑的路径空间(由于终端主机地位对等，任取其一作为起始节点)大小如表2所示。

![](images/86636131463db023aff62aa8061450a172e40cdc81a13fccace8642def5a311b.jpg)  
图6示例场景的端口示意  
图7实验拓扑结构  
Fig.7Experimental topology

由表2和图8可以看出，在相同拓扑下，随着主机数量的增多，路径数量和生成时间也逐渐增加，且不同拓扑之间的差距逐渐增大。网状拓扑的路径空间生成时间要明显高于线形拓扑和环形拓扑。这是由于在网状拓扑中具有较多可达环路，增加相同数目的主机使得增加的物理可达路径会更多，在生成路径空间时需要消耗较多的时间。在相同交换机数目的情况下，环形拓扑和网状拓扑的路径生成时间平均约为线形拓扑的3.02倍和10.83倍。

表2不同拓扑中的路径数量  
Tab.2Number of paths in different topologies   

<html><body><table><tr><td>Number of hosts</td><td>Linear</td><td>Ring</td><td>Mesh</td></tr><tr><td>10</td><td>9</td><td>19</td><td>102</td></tr><tr><td>20</td><td>19</td><td>37</td><td>171</td></tr><tr><td>30</td><td>29</td><td>55</td><td>232</td></tr><tr><td>40</td><td>39</td><td>73</td><td>301</td></tr><tr><td>50</td><td>49</td><td>91</td><td>362</td></tr><tr><td>60</td><td>59</td><td>109</td><td>431</td></tr><tr><td>70</td><td>69</td><td>127</td><td>492</td></tr><tr><td>80</td><td>79</td><td>145</td><td>561</td></tr><tr><td>90</td><td>89</td><td>163</td><td>622</td></tr><tr><td>100</td><td>99</td><td>181</td><td>691</td></tr></table></body></html>

![](images/3cca571cf69dba04f929416ba46bc0fe0c679f74c90fc30fe60882615087f0c8.jpg)  
图8主机数量对路径空间生成时间的影响

随机生成不同数量的流规则集合，研究流规则规模对转发函数生成的影响，结果如图9所示。

![](images/d60250a710fe50c2e27b06b541e92e2cfd987309bcbad0e1b98e5e590c536b93.jpg)  
图9流规则规模对转发函数生成时间的影响  
Fig.9Influence of flow rule size on forwarding function generation tim

由图9可以看出，三种拓扑的转发函数生成时间在相同规则规模下几乎相等，且随着规模的增加而增加。这是由于该阶段需要对预处理后流规则的匹配函数进行析取、合取和求反等操作。每一条规则进行的操作相似。为此，端口函数的生成时间会随着流规则的规模逐渐增加，且基本成线形关系。

# 3）流规则数目对路径验证的影响

为避免路径空间大小对路径验证时间的影响，实验设置具有68台终端的线形拓扑、37台终端的环形拓扑和4台终端的网状拓扑，其路径空间中都包含67条路径。实验结果如图10所示。

由图10可看出，总体上来说网状拓扑的路径验证时间最长，其次是环形拓扑，线形拓扑的路径验证时间最短。这是因为网状拓扑中的路径相对较长，生成路径函数时需要对更多的转发函数进行析取操作，为此验证时间更长。而且由于使用了BDD对布尔函数进行存储，极大缩短了对路径的验证时间。在上述实验中，路径验证时间均不超过 $2 0 \mathrm { m s }$ 。

![](images/cc5ddb7d725eccdf4c9bf41439b1314505d7a1c84cec9012217f53a2581c0a9e.jpg)  
图10流规则规模对路径验证时间的影响

本小节将对 RVBBF 与文献[15]提出的 APV 和文献[17]提出的DASDA进行性能比较。实验在如图11所示的复杂拓扑下进行，通过改变流规则的集合规模，分析其验证效率，实验结果如图12所示。

![](images/c2f26245acc2af08ba5593e7d64f237f7adb21f3148f1511c47e53dad2a596b5.jpg)  
Fig.10Influence of flow rule size on path verification time 4.2.3与APV算法的性能比较   
图11复杂拓扑

![](images/f5d7d658423c09b1b31bccc1b28933013c2bef17efaed3faaab7445d303bba44.jpg)  
Fig.8Influence of the number of hosts on the path generation time 2）流规则规模对转发函数生成的影响   
Fig.11Complex topology   
图12与APV 和DASDA 的性能比较  
Fig.12Performance comparison with APV and DASDA

由图11可以发现，三种算法的检测时间都随着流规则规模的增加而增加，但RVBBF在验证效率上要优于APV和DASDA，验证时间分别平均缩短约 $5 3 . 7 6 \%$ 和 $2 7 . 7 4 \%$ 。这是由于随着流规则数目的增加，尤其是当流规则集合包含的网段较多时，APV中的原子谓词数量会显著增加，DASDA则会因此导致FeDD过于庞大，使得在对其进行维护和查询时需要更多的时间。并且在APV中，新谓词的出现可能会对当前的原子谓词集合造成影响，导致其需要重新计算原子谓词集合，增加了验证的时间消耗。相对于APV，DASDA没有复杂的原子谓词计算过程，检测效率相对较高。而RVBBF则只需计算交换机各端口的转发函数，再据此对路径空间中的路径进行验证即可。同时由于使用BDD对布尔函数进行表示，大大提高了RVBBF的路径验证验证效率。

# 5 结束语

针对SDN网络中由于不同应用的转发路径交叠等导致的数据平面配置问题，本文提出了一种基于布尔函数的网络可达性验证方法。该方法根据流规则生成转发函数，结合路径生成算法产生的路径空间可实现SDN数据转发平面的可达性验证。实验结果表明，RVBBF能够有效验证网络可达性。并且相比较APV，其验证效率有明显提高。

在当今网络中，转发平面中的配置错误非常普遍。新技术也带来了新的安全挑战。在经典的 SDN 南向接口协议OpenFlow中，定义的动作中存在能够修改数据包IP地址的SET动作，该动作可以对数据包的包头信息进行修改，使得网络管理员方便、灵活地实现数据牵引、路由重定向等功能。但如果对SET动作使用不当，则会造成防火墙失效，引发严重的网络安全事故[20]。因此下一步将就如何快速高效的检测由SET动作导致的转发平面威胁展开研究，进一步提高网络安全。

# 参考文献：

[1] 杨泽卫，李呈．重构网络:SDN 架构与实现[M]．北京：电子工业出 版社，2017:1-16.(YANG Z W,LI C.Refactoring networks:SDN architecture and implementation [M].Beijing:Publishing House of Electronics Industry,2017:1-16.)   
[2]GREENBERG A,HJALMTYSSONG,MALTZDA,et al.A clean slate 4D approach to network control and management [J].ACM SIGCOMM Computer Communication Review,2005,35 (5): 41-54.   
[3]MAITY I，MONDAL A，MISRA S,et al. Tensor-based rule-space management system in SDN [J].IEEE Systems Journal,2018,13(4): 3921-8.   
[4]Barakabitze AA,Ahmad A,Mijumbi R,et al. 5G network slicing using SDN and NFV:A survey of taxonomy,architectures and future challenges [J].Computer Networks,2020,167:106984.   
[5]刘艺，雷程，张红旗，等．基于MapReduce 的OpenFlow 网络属性验 证技术[J].计算机研究与发展,2016,53(11):2500-11.(LIUY,LEI C,ZHANG HQ,et al.MapReduce-based network property verification technique for OpenFlow network [J].Journal of Computer Research and Development,2016,53 (11): 2500-11.)   
[6]王军.SDN下的策略冲突检测研究[D]．成都：电子科技大学,2020. (WANG J.Research on Strategy Conflict Detection under SDN [D]. Chengdu:University of Electronic Science and Technology of China, 2020.)   
[7]BENTON K,CAMP LJ, SMALL C.OpenFlow vulnerability assessment [C]// Proceedings of the second ACM SIGCOMM workshop on Ht topics in software defined networking,HongKong,Aug16,2013.New York:ACM,2013:151-152.   
[8]董仕．软件定义网络安全问题研究综述[J].计算机科学,2021,48 (03):295-306.(DONG S.Survey on Software Defined Networks Security [J].Computer Science,2021,48 (03): 295-306.)   
[9]郭中孚，张兴明，赵博，等．软件定义网络数据平面安全综述[J]. 网络与信息安全学报,2018,4(11):1-12.(GUO ZF, ZHANG X M, ZHAO B,et al. Survey of software-defined networking data plane security [J].Chinese Journal of Network and Information Security,2018, 4 (11): 1-12.)   
[10]陈浩宇，邹德清，金海．面向 SDN/NFV 环境的网络功能策略验证 [J].网络与信息安全学报,2021,7(03):59-71.(CHENHY,ZHOU Q D,JIN H,et al. Verification on policies for network functions in SDN/NFV-based environment [J]. Chinese Journal of Network and Information Security,2021,7(03): 59-71.)   
[11] KAZEMIAN P, CHANG M, ZENG H, et al. Real time network policy checking using header space analysis [C]// Proceedings of the 10th USENIXSymposiumonNetworkedSystemsDesignand Implementation,Ilinois,Apr 2-3,2013.New York: ACM Press,2013: 99-111.   
[12] KAZEMIAN P, VARGHESE G, MCKEOWN N. Header space analysis: Static checking for networks [C]// Proceedings of the 9th USENIX Symposium on Networked Systems Design and Implementation, Illinois, Apr 25-27,2012.New York:ACMPress,2012:113-126.   
[13] Fang Y,Lu Y.Real-Time Verification of Network Properties Based on Header Space [J].IEEE Access,2020,8:36789-36806.   
[14]郝巍，伊鹏，江逸茗．一种快速的 SDN规则冲突检测机制[J]．计算 机工程,2019,45 (02): 139-43.(HAO W,YIP,JIANGY M.AFast SDN Rule Conflict Detection Mechanism [J].Computer Engineering,2019, 45 (02): 139-43.)   
[15] YANG H, LAM S S J IA T O N. Real-time verification of network properties using atomic predicates [J].IEEE/ACM Transactions on Networking,2015,24 (2): 887-900.   
[16]王首一，李琦，张云．轻量级的软件定义网络数据包转发验证[J]. 计算机学报,2019,42(01): 176-89.(WANG SY,LIQ,ZHANGY.LPV: Lightweight packet forwarding verification in SDN [J]. Chinese Journal of Computers,2019,42 (01): 176-89.)   
[17] Saied W, Souayeh NB YB,Saadaoui A,et al. Deep and automated SDN data plane analysis [C]// 2o19 International Conference on Software, Telecommunications and Computer Networks,Split, Sept 19.2019. IEEE,2019: 1-6.   
[18] BurdonovI, Kossachev A, Yevtushenko N,et al.Preventive Model-based Verification and Repairing for SDN Requests [J]. arXiv preprint arXiv: 1906.03101,2019.   
[19] Bryant R E.Graph-based algorithms for boolean function manipulation [J].Computers,IEEE Transactions on,1986,100(8): 677-691.   
[20] Saadaoui A, Souayeh NB YB,Bouhoula A.Automated and Optimized Formal Approach to Verify SDN Access-Control Misconfigurations [C]// International Conference on Testbeds and Research Infrastructures, Shanghai, December 1-3,2018.Cham: Springer Press 2018: 96-112.