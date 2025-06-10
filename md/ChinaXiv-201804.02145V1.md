# 基于虚拟移动的IPv6主动防御方案

孔亚洲，张连成，王振兴(数学工程与先进计算国家重点实验室，郑州 450002)

摘要：现有通过地址跳变对 IPv6节点进行防护的技术依赖时间同步或事件同步，利用IPv6 的良好移动特性和多转交地址注册机制，提出一种基于虚拟移动的IPv6主动防御方案。通过为 IPv6节点分配动态变化的转交地址，使其呈现出在网络内不断移动的特征，降低攻击者对其实施攻击概率的同时，能够保证通信的持续。理论分析和实验测试表明，方案具有良好的抗攻击能力且较小的系统开销。

关键词：IPv6；虚拟移动；主动防御；方案 中图分类号：TP393.08 doi:10.3969/j.issn.1001-3695.2018.01.0045

# Proactive defense scheme of IPv6 based on virtual mobile

Kong Yazhou, Zhang Liancheng,Wang Zhenxing (State Key Laboratory ofMathematical Engineering&Advanced Computing,Zhengzhou 450o02,China)

Abstract:The existing technologies for protecting IPv6 nodes byaddress hopping relyon time synchronization or event synchronization,utilizing the good mobilityfeatureof IPv6and multiple care-of address registration mechanisms,this paper proposeda proactive defense scheme ofIPv6based on virtual mobile.Byasigning adynamically changing care-ofaddress to an IPv6 node,the IPv6 node presentedthecontinuouslymoving feature in the network,reduced the atack probabilityof an attacker,andensuredthecontinuityofcommunications.Theoreticalanalysisand experimentaltestsshowthattheschemehas good anti-attack ability and less system overhead.

Keywords:IPv6;virtual mobile;proactive defense; scheme

# 0 引言

2016年11月7日，互联网架构委员会（InternetArchitectureBoard，IAB）发表声明称，建议互联网工程任务组（InternetEngineeringTaskForce，IETF）等标准开发组织及合作伙伴放弃在新协议标准中兼容IPv4，用行动支持并实施IPv6在全球范围内的部署[1]。2017年11月26日，中共中央办公厅、国务院办公厅印发了《推进互联网协议第六版（IPv6）规模部署行动计划》[2]（简称“计划")，“计划”要求不仅要实现移动互联网全面支持IPv6，还要强化网络安全保障。

随着IPv6部署的广泛深入，越来越多的网络服务正逐步迁移到IPv6网络，包括Web服务器、邮件服务器、域名服务器等。由于IPv6拥有128位地址空间，使得每个节点均能分配一个全球可路由单播地址，且可保持永久不变。因此，在IPv6网络环境中，提供网络服务的重要节点更易遭受来自攻击者的攻击[3]，其中最常见且难以防护的攻击包括拒绝服务（denialofservice,DoS）攻击、分布式拒绝服务（distributeddenialof service,DDoS）攻击等。

针对网络的确定性和静态性带来的网络易攻难守等挑战，美国提出一种“改变游戏规则”的积极主动的网络防御思想，即移动目标防御（moving target defense，MTD）[4]，通过动态、持续的变化以显著增加攻击者的攻击难度，降低其攻击成功率。利用这一防御思想，研究人员已经在网络层设计并开发出了多种具体的防御机制。动态网络地址转换（dynamicnetworkaddresstranslation,DyNAT)[5]是一种在数据包被路由转发之前，动态变化其地址与端口信息来抵抗嗅探攻击的技术，该技术依赖集中网关的安全性，存在通信失败的可能；网络地址随机化（network address space randomization，NASR）[6]是一种通过修改网络内动态主机配置协议（dynamic host configuration protocol,DHCP）服务器来动态更改IP地址变化频率来抵抗蠕虫攻击的技术，该技术部署成本较高，且只能实现局域网（localareanetwork，LAN）内的地址随机化；端口跳变（porthopping）是一种通过动态变化TCP/UDP 端口号来抵抗DoS/DDoS攻击的技术；Lee等人[7提出一种通过在服务器和用户之间共享私钥进行 TCP/UDP端口跳变的技术，该技术能够有效阻止攻击者对服务器进行攻击，但是其依赖严格时间同步，无法适用于网络延时较大的网络中；Badishi等人[8提出一种基于端口的配给信道机制，利用伪随机函数使不同信道在不同时刻使用不同的端口通信，这一机制的安全性依赖于ACK报文，若ACK报文被截获，攻击者即可对目标节点实施攻击；石乐义等人[提出服务跳变（service hopping）和端跳变（end hopping）的概念，通过伪随机跳变图来动态地变化通信双方或一方的IP地址、端□、时隙、加密算法、通信协议等信息，以增加攻击难度与成本；Jafarian 等人[10]提出一种 OF-RHM（OpenFlow random hostmutation)技术，利用OpenFlow快速变换主机虚拟IP,OpenFlow实现虚拟IP与真实IP的转换，从而增加攻击难度。由于OF-RHM部署困难，Al-Shaer等人[1l]提出一种RHM（randomhostmutation)技术，利用低频变换和高频变换来给主机分配虚拟IP。为提高变化机制安全性，Jafarian等人[2]提出一种STAM（spatio-temporaladdressmutation）机制来实现动态变化主机与IP 地址的绑定关系，每个主机对应一个瞬时IP，且每个瞬时IP只能在指定时间间隔内与另一特定主机通信。MT6D（movingtargetIPv6defense）[13]是一种在IPv6 网络环境下MTD的具体实现方法，通信双方以EUI-64接口标志符（interfaceidentifier，IID）、共享密钥及系统时间为参数，经过哈希计算后生成新的IID，增加了攻击成本与复杂度；刘慧生等人[14]提出一种利用IPv6多穴特性使主机地址在多个地址域内动态变化的技术MHH-PD6，增加了攻击者流量监听及DoS攻击的难度。

综上所述，现有的可有效阻止或降低IPv6节点遭受DoS攻击的技术（以MT6D和MHH-PD6为例）主要存在以下不足之处：a)MT6D 在通信地址动态改变的过程中存在地址冲突的可能，从而造成丢包或会话中断现象；b)MT6D依赖严格时间同步，无法适应网络延迟较大或网络拥塞的网络环境；c)MHH-PD6依赖跳变服务器的安全性，跳变服务器存在被DoS攻击的可能;d)MHH-PD6 需要所在网络接入多条链路，适用范围受限。

针对现有研究技术的不足之处，本文提出一种基于虚拟移动的IPv6抗DoS攻击方案，利用IPv6的良好移动特性支持，提出虚拟移动思想，即为受保护IPv6节点分配动态变化的转交地址（care-ofaddress，CoA)，使攻击者无法准确辨识目标节点是否发生真实移动及其位置，从而无法对其实施DoS攻击。此外，由于移动IPv6（mobileIPv6，MIPv6）允许IPv6节点能够在移动（即改变其CoA）的同时保持当前连接，因此该方案不依赖时钟同步或事件同步机制，能够适应较复杂的网络环境且保持通信的持续不断。

# 1 ADVM方案

本文提出的虚拟移动（virtualmobile，VM）包含两方面含义：一是IPv6节点未发生真实移动，而是利用IPv6对移动的良好支持，使其对外呈现出移动的表征；二是IPv6节点发生真实移动，使其对外呈现出移动位置动态变化的特点，无法辨识其移动的真伪。接下来，本章将对ADVM方案的基本结构、工作流程进行详细描述。

# 1.1 ADVM结构组成

定义1IPv6 虚拟移动节点（virtual mobile node for IPv6,

VMN)。受ADVM方案保护的IPv6节点。

定义2转交地址集（setofcare-ofaddresses）。VMN用于呈现虚拟移动特征的地址集合， $C = \{ c o a _ { 1 } , c o a _ { 2 } , . . . , c o a _ { n } \} , n \in \mathbb { Z }$ 。

定义3IPv6 虚拟移动代理（virtual mobile agent for $\mathrm { I P v } 6$ VMA）。与VMN处于不同子网的IPv6节点，$A = \{ \nu m a _ { 1 } , \nu m a _ { 2 } , . . . , \nu m a _ { n } \} , n \in \mathbb { Z }$ ，为VMN转发通信数据包。

定义4 通信对端（corresponding node，CN)。与VMN进行通信的对端节点， $N = \{ c n _ { 1 } , c n _ { 2 } , . . . , c n _ { l } \} , l \in \mathbb { Z }$ 。

ADVM的基本结构如图1所示。

![](images/9da73e8b4fa5d2cfaa0454b4a638d65bfa4116bf17f33bb1885a9c7c154c37bf.jpg)  
图1ADVM基本结构

ADVM方案基本思想是：在于CN进行通信过程中，VMN从集合 $A$ 中随机选取一个子集$A _ { s u b s e t } = \{ \nu m a _ { i } , \nu m a _ { i + 1 } , . . . , \nu m a _ { j } \} , i , j \geq 1 ,$ 且i, $j \in \mathbb { Z }$ ，其对应的转交地址子集为 $C _ { s u b s e t } = \{ c o a _ { i } , c o a _ { i + 1 } , . . . , c o a _ { j } \} , i , j \geq 1 ,$ 且i, $j \in \mathbb { Z }$ ，VMN将通信对端 分为若干个组$G = \left\{ \left( \overbrace { c n _ { _ k } , c n _ { _ { k + 1 } } , . . . , c n _ { m } } ^ { { m - k + 1 } } \right) . . . \left( \overbrace { c n _ { _ u } , c n _ { _ { u + 1 } } , . . . , c n _ { _ \nu } } ^ { { \nu - u + 1 } } \right) \right\} , c n \in N$ ，每个组中的成员与数量均是随机的，VMN将转交地址子集按照RFC$5 6 4 8 ^ { [ 1 5 ] }$ 中定义的多转交地址注册（multiple care-of addressesregistration）过程随机通知给通信对端组，从而达到有效保护VMN免受DoS攻击的目的。

# 1.2ADVM 基本流程

ADVM方案的基本流程如图2所示。其中Alice为 $\scriptstyle { \mathrm { I P v 6 } }$ 虚拟移动节点VMN， $B o b = \left\{ B o b _ { i } \vert 1 \leq i \leq n \right\}$ $n \in \mathbb { Z }$ 为通信对端集合，$A = \Big \{ A _ { j } , 1 \leq j \leq m \Big \} ,$ $m \in \mathbb { Z }$ 为IPv6 虚拟移动代理集合VMA。接下来对其工作过程进行详细阐述。

![](images/2518a171d53ab1583f0d44640de9a7ebb11b7c16a41b7f1e0182f30bccf5d086.jpg)  
图2ADVM基本流程

1)Alice向VMA发起虚拟移动注册

首先，虚拟移动节点Alice从VMA的集合 $A$ 及其转交地址集合 $C$ 中随机选取一个非空子集构成集合$S = \left\{ \left. A _ { i } , C o A _ { i } \right. \big | A _ { i } \in A , C o A _ { i } \in C , 1 \le i \le n \right\} , n \in \mathbb { Z }$ ，并向集合中的每个VMA发送身份注册报文 $R e g _ { \scriptscriptstyle V M N }$ ，虚拟移动代理验证Alice的身份后，向其回复身份确认报文 $A c k _ { \scriptscriptstyle V M A }$ 。至此，集合 $s$ 中的每个VMA将作为Alice的通信中转节点，负责Alice与通信对端之间通信数据的转发，该注册过程经过随机变化的时间间隔 $\tau$ 就会执行一次，使Alice呈现出在IPv6子网间不断移动的假象，增加攻击成本及复杂度。该过程可表示为：

a）Alice: select(S）。  
b）A $\operatorname { l i c e }  S : R e g _ { { } _ { V M N } } ( H o A _ { { } _ { A l i c e } } , I D _ { { } _ { A l i c e } } )$ 。c） $s \to$ Alice : $A c k _ { \scriptscriptstyle V M A } ( C o A _ { s } , I D _ { s } )$ 。  
2)多转交地址注册

在该过程中，Alice先从通信对端的集合 $B o b$ 中选取个非空真子集 $\mathscr { Q } _ { 1 } , \mathscr { Q } _ { 2 } , . . . , \mathscr { Q } _ { z }$ ，且 $B o b { = } Q _ { 1 } \cup Q _ { 2 } \cup \ldots \cup Q _ { z }$ ，$\forall i \neq j , Q _ { i } \cap Q _ { j } = \emptyset$ ；然后 Alice 从集合 $s$ 的非空子集中选取个子集，并将这些集合中的转交地址以绑定更新（bindingupdate，BU）报文的方式通知所有通信对端，这些BU报文增加了绑定标志符选项（binding identification number，BID)；之后每个集合中的通信对端回复绑定确认（bindingacknowlegement，BA）消息。该过程可表示为：

a）Alice:sele $\cdot c t ( Q _ { 1 } , Q _ { 2 } , . . . , Q _ { z } )$ 。b） $\mathrm { A l i c e } \to Q _ { i } : B U ( B I D _ { i } , H o A _ { A l i c e } , C o A _ { S } ) \ _ { \mathcal { C } }$ c） $Q _ { i } \to \mathrm { A l i c e } : B A ( H o A _ { A l i c e } , C o A _ { s } )$ 。3）返回可路由过程

RFC6275中描述了路由优化过程，即移动节点和通信对端之间可以直接发送通信数据。返回可路由过程（returnroutabilityprocedure，RRP）是为验证移动节点既可以通过它的本地地址到达，也可以通过它的转交地址到达，从而防止绑定更新欺骗和DoS攻击。在ADVM方案中，RRP过程如图3所示。

![](images/eda9a2ee6d0fb7d90b24d5c5809f52800e25a5ecb4bcea7e9f2dae5c8d093236.jpg)  
图3ADVM中RRP 的处理

a）Alice向VMA发送RRP启动信号，随后VMA向Bob发送HoTI（home test init）和 CoTI（care-of testInit）消息。其中，HoTI先经过隧道发送给HA，然后由HA发送给Bob，CoTI则由VMA直接发送给 $\mathbf { B o b }$ 。该过程可表示为：

(a) Alice $ \mathbf { S } \colon$ start(b) $\mathrm { S } \to \mathrm { H A } \to \mathrm { B o b } \colon H o T I \ , \mathrm { S } \to \mathrm { B o b } \colon C o T I$ b）Bob收到HoTI和CoTI消息后，生成本地地址令牌tokenl，转交地址令牌token2，然后Bob将tokenl置于HoT消息中经由HA发送给VMA，将token2置于CoT消息中直接发送给VMA。该过程可表示为：(c) $\mathbf { B o b } \colon g e n e r a t e ( t o k e n 1 , t o k e n 2 )$ (d) $\mathbf { B o b } \to \mathbf { H A } \to \mathbf { S } : H o T ( t o k e n 1 )$ ， $\mathbf { B o b }  \mathbf { S } : C o T ( t o k e n 2 )$ c)VMA收到后将tokenl和token2发给Alice，随后Alice生成一个Kbm并发给VMA，VMA向Bob发送由Kbm加密的绑定更新消息，Bob收到该消息后对 $K b m$ 进行认证。如果认证通过，则根据BU消息更新绑定缓存并回复绑定确认消息；否则，不做任何操作。该过程可表示为：

(e $\begin{array} { r } { \jmath \mathrm { S }  \mathrm { A l i c e } \colon p a c k e t ( t o k e n 1 , t o k e n 2 , I D _ { s } ) } \end{array}$ 。  
(f) Alice : generate(Kbm,tokenl,token2） 。  
(g) Alice $ \mathbb { S }$ S: packet(Kbm,IDlice）。（ $\mathrm { h } ) \mathbf { S }  \mathbf { B } \mathrm { o } \mathbf { b } \colon B U _ { \phantom { } _ { K b m } }$ 。  
(i)Bob:Verify(Kbm),if true,  
update and BA,else,do nothing 。1 ${ \mathrm { j } } ) \mathbf { S }  \mathbf { A l i c e } : e n d$ 。

经过上述过程，即使所在网络环境需要执行返回可路由过程，ADVM依然可以实现对VMN的有效防护。

4)通信传输过程

通信对端的绑定缓存（BindingCache）结构如图4所示，

![](images/fc329ef147949835ca7cdf5e7785f148857924297e11602b584200ac0d278a63.jpg)  
图4绑定缓存结构

当Bob与Alice进行通信时，首先，按照BID的值从绑定缓存中随机一条表项，与表项对应的CoA进行通信。在通信过程中采用“先选取，后删除”策略，即通信时Bob先选取下一刻将使用的CoA，当通信切换到新的CoA之后，再将之前的缓存表项删除。VMA收到消息后，对数据包进行排序操作后，将这些数据包转发给Alice。然后，Alice根据数据包中的标记进行重组，至此，Alice的数据接收过程结束。之后，Alice将回复数据包按此逆过程进行传输，直至Bob完成接收过程，至此，整个通信传输过程结束。

# 1.3虚拟位置漂移算法

虚拟位置漂移算法（virtuallocation driftalgorithm，VLDA）是对虚拟移动代理进行随机选取、对通信对端进行随机分组的过程，遇到以下三种情况将会执行该算法：a）每隔时间间隔 $\tau$ 就会执行一次；b）虚拟移动代理有更新或删除变化；c）通信对端的集合有变化。

算法1 VLDA 算法  

<html><body><table><tr><td>Algorithm VLDA 输入：VMA，CN. 输出：S，Bob.</td></tr><tr><td>1.Start</td></tr><tr><td>2．S=Select(VMA)；//从VMA中选取一个非空子集</td></tr><tr><td>3．CNR=Calcu(CN)；//将CN分成若干个非空真子集</td></tr><tr><td>4．//从CN中随机选取若干个真子集且满足以下条件</td></tr><tr><td>CN=BobUBob,，当i≠j时,BobiBob=Ω</td></tr><tr><td>5.Bob=SelectFrom(CNR);</td></tr><tr><td>6.End</td></tr></table></body></html>

该算法为ADVM方案提供了两方面的安全性，一是虚拟移动代理集合的随机性，使攻击者对虚拟移动节点的追踪更加困难，提高了攻击难度；二是通信对端的分组随机性，使攻击者对通信流量的分析更加复杂，提高了攻击成本。

# 2 ADVM方案分析

# 2.1 ADVM安全性分析

本节主要从以下两个方面对ADVM的安全性进行分析：a)攻击者扫描速率与ADVM安全性之间的关系；b）攻击者数量与ADVM安全性之间的关系。

1）攻击者扫描速率与ADVM安全性之间的关系

假设防御者在 $t$ 时刻选用的VMA的数量一共有 $\eta$ 个， $\chi ( t )$ 是攻击者在t时刻无法确定的VMA的数量，假设攻击者对VMA的扫描是独立泊松过程，攻击者所用扫描时间为 $T _ { s c a n }$ ，那么攻击者对每个VMA的平均扫描速率为 YT，每个 VMA的变化时间间隔是独立的，且服从指数分布（平均 $T _ { s u c c e s s } = \gamma _ { \xi } )$ 假设防御者选取VMA的时间是随机变化的，那么 $\chi$ 可建模为一个连续时间的齐次马尔科夫链，其转移到状态 $s$ 的转移速率矩阵可表示为

$$
\mathbf { Q } = \left[ \begin{array} { c c c c } { - q _ { 0 0 } } & { q _ { 0 1 } } & { \hdots } & { q _ { 0 \eta } } \\ { q _ { 1 0 } } & { - q _ { 1 1 } } & { \hdots } & { q _ { 1 \eta } } \\ { \vdots } & { \vdots } & & { \vdots } \\ { q _ { \eta 0 } } & { q _ { \eta 1 } } & { \hdots } & { - q _ { \eta \eta } } \end{array} \right] ,
$$

$$
q _ { s , s - 1 } = \zeta \ , 1 \leq s \leq \eta \ q _ { s , \eta } = \xi , 0 \leq s \leq \eta - 1
$$

攻击者的平均扫描速率 $\zeta = \mathop { V } _ { T _ { s c a n } }$ ，代表攻击者锁定VMA的速度。

$\chi$ 的稳态分布 $\pi$ 满足平衡方程 $\pi \mathbf { \dot { Q } } = 0 \mathbf { \dot { \eta } }$ ，其中转移速率矩阵 $\mathbf { Q } = [ q _ { i , j } ]$ ，且 $\begin{array} { r } { q _ { i , j } = - \sum _ { j \neq i } q _ { i , j } } \end{array}$ 。令 $\varphi = \frac { \zeta } { \xi } = \frac { T _ { s u c c e s s } } { T _ { s c a n } }$ ，且$\gamma = \frac { \zeta } { \zeta + \xi } = \frac { \varphi } { \varphi + 1 }$ ， 求解平衡方程得

$\begin{array} { r } { \pi _ { i } = \{ \begin{array} { l l } { \gamma ^ { \eta } , \quad \quad \quad \quad , i = 0 } \\ { \gamma ^ { \eta - i + 1 } (   \begin{array} { l } { V } \\ { \gamma } \end{array} | ) \ , 0 < i \leq \eta } \end{array}  , } \end{array}$ 因此，

$\chi$ 的期望记为

$$
\begin{array} { l } { { \displaystyle E \chi = \sum _ { i = 0 } ^ { \eta } i \pi _ { i } } } \\ { ~ } \\ { { \displaystyle ~ = \eta - \frac { \gamma \left( 1 - \gamma ^ { \eta } \right) } { 1 - \gamma } } } \\ { { \displaystyle ~ = \eta - \varphi \left( 1 - \left( \frac { \varphi } { \varphi + 1 } \right) ^ { \eta } \right) } } \end{array}
$$

由上可得:

结论1 $E \chi$ 与 $\varphi$ 成反比，即使攻击者采用较高的扫描速率，也只能获取较少的VMA的信息，增加了攻击者的攻击难度和复杂度。

2）攻击者数量与ADVM安全性之间的关系首先，给出涉及到的符号及其说明，如表1所示。

表1符号说明  

<html><body><table><tr><td>符号</td><td>含义</td></tr><tr><td>N</td><td>所有通信对端的数目</td></tr><tr><td>Na</td><td>所有假冒通信对端的攻击者数目</td></tr><tr><td>Nb</td><td>所有合法通信对端数目</td></tr><tr><td></td><td>跳变时间间隔</td></tr><tr><td>NCoA</td><td>跳变间隔内VMA数目</td></tr><tr><td>Nc&</td><td>使用注册地址CoA的通信对端数目</td></tr><tr><td>PCoA</td><td>注册地址CoA不被扫描发现的概率</td></tr><tr><td>Nba</td><td>与攻击者处于同组的通信对端数目</td></tr><tr><td>Nba'</td><td>与攻击者不处于同组的通信对端数目</td></tr><tr><td>Pe</td><td>通信对端通信成功的概率</td></tr></table></body></html>

由表可知， $N = N _ { a } + N _ { b }$ ，与攻击者不处于同组的通信对端的数目为

$$
N _ { b a } \mathrm { , } = \sum _ { k = 1 } ^ { N _ { C o A } } p _ { C o A _ { k } } N _ { c _ { k } }
$$

假设通信对端的数目按照CoA的数目均匀分布，那么$N _ { c _ { k } } = \frac { N } { N _ { { c o A } } } , k \ge 1$ ，使用注册地址 $C o A _ { k }$ 的通信对端不被锁定的概率为

$$
p _ { C o A _ { k } } = \frac { \binom { N - N _ { a } } { N _ { c _ { k } } } } { \binom { N } { N _ { c _ { k } } } }
$$

其中： $\binom { N - N _ { a } } { N _ { c _ { k } } }$ 是 ${ { N } - { N _ { a } } }$ 中大小为 $N _ { { { \boldsymbol { c } } _ { k } } }$ 的真子集的个数；$\binom { N } { N _ { c _ { k } } }$ 是 $N$ 的大小为 $N _ { c _ { k } }$ 的真子集的个数。因此，

$$
E \left( N _ { b a } , \right) = \sum _ { k = 1 } ^ { N _ { c o t } } \frac { \left( N - N _ { a } \right) } { \left( N _ { c _ { k } } \right) } N _ { c _ { k } }
$$

假设通信对端均匀分布于各个真子集，因此，

$$
E \left( { N } _ { b a } , \mathbf { \lambda } \right) = \frac { \left( \begin{array} { c } { { N - N _ { a } } } \\ { { N _ { c _ { k } } } } \end{array} \right) } { \left( \begin{array} { c } { { N } } \\ { { N } } \\ { { N _ { c _ { k } } } } \end{array} \right) } \times N
$$

根据斯特林公式， $n ! \approx \left( { \frac { n } { e } } \right) ^ { n } { \sqrt { 2 \pi n } }$ ，假设 $N _ { a } \ll N$ ，那么：

$$
E { \left( N _ { b a } , \right) } = N \times { \left( \frac { N - N _ { a } } { N } \right) } ^ { N _ { c k } } = N \times { \left( 1 - \frac { N _ { a } } { N } \right) } ^ { N / C o A _ { k } }
$$

那么，通信对端通过VMA成功进行数据传输的概率为

$$
p _ { e } = \frac { N } { N _ { b } } \bigg ( 1 - \frac { N _ { a } } { N } \bigg ) ^ { N / C o A _ { k } }
$$

由上可得：

结论2攻击者数量的增加并不能显著降低通信对端的通信效率，增加了攻击复杂度，提升了网络安全性。

# 2.2 ADVM性能分析

由1.2节可知，与正常IPv6 通信相比，VMA的选取和数据转发有可能带来一定的时延。接下来，本节将对ADVM对通信性能的影响进行分析。

1）正常情况下，IPv6通信时延

首先，对正常情况下IPv6节点间的通信时延进行分析。当通信发起者为固定节点时，通信时延主要是路径传输时延，记为 $T _ { p a t h }$ ，当通信发起者为移动节点时，通信时延主要包括移动节点完成链路切换的时延 $T _ { h a n d o \nu e r }$ ，当移动节点移动到新的外地链路时，要执行地址自动配置，此阶段所耗时间记为 $T _ { c o n f i g }$ ；之后，移动节点要与通信对端完成路由优化过程，所用时间记为（204号 $T _ { o p t i m a l }$ ；最后，通信对端与移动节点进行通信时的路径传输时延为 $T _ { p a t h }$ 。因此，正常情况下，IPv6通信时延可记为

$$
T _ { n o r m a l } = \left\{ \begin{array} { c } { T _ { { p a t h } } , } \\ { \big ( \ddagger \ddagger { \boxdot { 4 } } \ne \mathcal { Y } _ { \mathfrak { h } } \boxplus \overleftrightarrow { \frac { \lambda ^ { * } } { \lambda \mathfrak { k } } } \ H _ { \mathfrak { h } } ^ { \Bigl ( \frac { - 1 } { \lambda \mathfrak { k } } \frac { - 1 } { \mathfrak { k } } \frac { - 1 } { \mathfrak { k } } \Bigr ) } } \\ { T _ { { p a t h } } + T _ { { h a n d o v e r } } + T _ { { c o n f i g } } + T _ { { o p t i m a l } } } \\ { \big ( \dddot { \mathfrak { K } } \dddot { \mathfrak { k } } \dddot { \mathfrak { k } } \ne \mathcal { Y } _ { \mathfrak { h } } \dd { \mathfrak { k } } \hat { \mathfrak { k } } \hat { \mathfrak { k } } \big ) \xrightarrow { + 1 } \mathinner { \operatorname { I m } } \mathclose | } \end{array} \right.
$$

2）ADVM通信时延

在ADVM方案中，若VMN是固定节点，那么ADVM的通信时延主要包括VMN每隔时间 $\tau$ 执行一次算法的时间，记为 $T _ { a l g }$ 。ADVM向选取的VMA发起注册的时间 $T _ { r e g }$ ，VMA返回确认信息的时间 $T _ { a c k }$ 。VMN向通信对端发起多转交地址注册的过程中，所需时间包括绑定更新时间和绑定确认时间，分别记为 $T _ { B U }$ 和 $T _ { _ { B A } }$ 。路径传输时延包括通信对端到VMA的时间和VMA到VMN的时间，分别记为 $T _ { { \scriptscriptstyle C N } \to V M A }$ 和 $T _ { \mathit { V M A }  \mathit { V M N } }$ 。若VMN是移动节点，除去上述过程的时延外，还包括VMN完成链路切换的时延 $T _ { h a n d o v e r }$ 和VMN移动到外地链路后，完成地址自动配置所花费的时延 $T _ { c o n f i g }$ 。因此，ADVM方案的通信时延可记为

$$
T _ { A D V M } = \{ \begin{array} { l l } { T _ { a i g } + T _ { r e g } + T _ { a c k } + T _ { B U } + } & \\ { T _ { B A } + T _ { C N  V M A } + T _ { V M A  V M N } } & \\ { \qquad ( \frac { \lambda r } { \perp } \nabla { \mathrm { M N } } \frac { \mathcal { V } _ { y } } { \mathcal { V } _ { y } \mathcal { V } _ { z } } ) [ \Xi ] \frac { \hat { x } - \hat { x } } { \mathcal { V } _ { z } } + \frac { \mathrm { i } + } { 2 } \frac { \mathrm { k } } { \mathcal { V } _ { z } } ) } & \\ { T _ { a i g } + T _ { r e g } + T _ { a c k } + T _ { B U } + } & \\ { T _ { B A } + T _ { C N  V M A } + T _ { V M A  V M N } + T _ { h a n d o w r r } + T _ { c o n f i g } } & \\ { \qquad ( \frac { \lambda r } { \perp } \nabla { \mathrm { M N } } \mathcal { V } ) [ \tilde { \mathcal { H } } _ { y } ^ { z } \tilde { \mathcal { V } } _ { z } ] \frac { \hat { x } - \hat { x } } { \mathcal { V } _ { z } } ) + \frac { \mathrm { i } + } { 2 } \frac { \mathrm { k } } { \mathcal { V } _ { z } } ) } & \end{array} 
$$

其中，由于ADVM中涉及的绑定更新与确认，数据传输过程与正常情况下的时延并无区别，因此，

$$
\begin{array} { l } { { T _ { o p t i m a l } = T _ { _ { B U } } + T _ { _ { B A } } \mathrm { ~ , ~ } } } \\ { { \nonumber } } \\ { { T _ { p a t h } = T _ { _ { C N  V M A } } = T _ { _ { V M A  V M N } } } } \end{array}
$$

因此，ADVM的通信时延可简化为

$$
T _ { A D V M } = \{ \begin{array} { l l } { T _ { a l g } + T _ { r e g } + T _ { a c k } } \\ { + T _ { o p t i m a l } + 2 T _ { p a r b } } \\ { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\  T _ { a l p V M } = \{ \begin{array} { l l } { \frac { \mathrm { i } \mathrm { i } \mathrm { \cdot } } { \mathrm { i } \mathrm { E } } \mathrm { \cdot } \mathrm { e } ^ { \mathrm { i } \mathrm { i } \mathrm { E } } \mathrm { i } } \\ { T _ { a l g } + T _ { r e g } + T _ { a c k } } \\ { + T _ { o p t i m a l } + 2 T _ { p a r b } + T _ { h a m d o v e r } + T _ { c o n f i g } } \\ { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \end{array}  \end{array}
$$

因此，与正常通信相比，ADVM方案的额外开销可记为

$$
T _ { e x t r a } = \left\{ \begin{array} { l l } { T _ { a l g } + T _ { r e g } + T _ { a c k } + T _ { o p t i m a l } + T _ { p a t h } } \\ { \quad ( \frac { \mathrm { x t } } { \mathrm { | f | } } \mathrm { V M N } \not { \mathrm { \dot { \mathcal { H } } | } } \frac { t \mathrm { \dot { \mathcal { H } } } } { \mathrm { | f | } } \frac { \mathrm { t \dot { \mathcal { H } } } } { \mathrm { | f | } } \frac { \mathrm { t \ddot { \mathcal { H } } } } { \mathrm { | f | } } ) } \\ { T _ { a l g } + T _ { r e g } + T _ { a c k } + T _ { p a t h } } \\ { \quad ( \frac { \mathrm { x t } } { \mathrm { | f | } } \mathrm { V M N } \not { \mathrm { \dot { \mathcal { H } } } } \frac { t \mathrm { \dot { \mathcal { H } } } } { \mathrm { | f | } } \frac { \mathrm { t \ddot { \mathcal { H } } } } { \mathrm { | f | } } ) } \end{array} \right.
$$

由此可知，当VMN为固定节点时，即VMN并未发生真实移动时，为虚拟其移动的情景，额外开销主要是执行算法的开销，进行虚拟注册的时间开销及数据传输开销；当VMN为移动节点时，即VMN发生真实移动，但虚拟其移动至其他子网的情景，额外开销主要是执行算法的开销，进行虚拟注册的时间开销及数据传输开销，但无需进行一次路由优化的时间开销。

# 3 实验测试与分析

利用移动IPv6的开源实现UMIP，在Ubuntu17.04操作系统上实现了ADVM方案，通过接入CERNET2搭建了如图5所示的验证环境。

![](images/5e8c11f507bd364f0cd7bee4658e315e83a8a03ac1227031cdc9b7e3f9167af0.jpg)  
图5实验测试拓扑

其中，Ai和A2为虚拟移动代理，Bob1和Bob2为通信对端，Alice为虚拟移动节点，Attacker为攻击者。参数配置如表2所示。

表2参数配置  

<html><body><table><tr><td>节点</td><td>IPv6地址</td><td>操作系统</td></tr><tr><td>A1</td><td>2001:da8:2017:ad12</td><td>Ubuntu 17.04</td></tr><tr><td>A2</td><td>2001:da8:2018:cd49</td><td>Ubuntu 17.04</td></tr><tr><td>Bob1</td><td>2001:da8:2019::38e1</td><td>Windows 8</td></tr><tr><td>Bob2</td><td>2001:da8:2020:af09</td><td>Ubuntu 17.04</td></tr><tr><td>Alice</td><td>2001:da8:2021:ac22</td><td>Ubuntu 17.04</td></tr><tr><td>Attacker</td><td>2001:da8:2022:ff03</td><td>Windows 8</td></tr></table></body></html>

# 3.1ADVM开销测试

为测试ADVM方案的开销，主要从以下两种场景对其开销进行测试：a）Alice为固定节点；b）Alice为移动节点。

针对第一种场景，依据虚拟位置漂移算法，Alice选取A1和A2的IPv6地址为CoA，并分别向Bob1和Bob2进行多转交地址注册，通过在Alice与Bob1和Bob2之间传输不同大小的文件来测试ADVM的开销，其测试结果如图6所示。

![](images/0acb02357a5780ed3418a5062c28cb7a00dfd61458f73907bbb65dec748581bd.jpg)  
图6 Alice 为固定节点时的开销

由图6可知，与正常通信相比，传输同样大小的文件，ADVM方案的开销并未显著增加，且传输过程中未出现数据包乱序问题，Alice能完整恢复出所传输的文件。

针对第二种场景，令Alice发生真实移动至子网$2 0 0 1 { \cdot } \mathrm { d a } 8 { \cdot } 2 0 2 3 { \cdot } { : } / 4 8$ ，并按照场景一中的方法对ADVM方案的开销进行测试，其测试结果如图7所示。

![](images/713f8e6eb73a1b9254bf85485417d0bbcb676768636f2dd83b23a8e4d72c352c.jpg)  
图7Alice为移动节点时的开销

由图7可知，当Alice发生真实移动时，ADVM方案的开销相比第一种场景有所增加，这是因为Alice 执行了移动IPv6过程，但与正常通信相比，其开销并未显著增加。

由上可知，测试结果与3.2节的分析结论一致，说明了ADVM方案的额外开销并未影响节点间的正常通信。

# 3.2ADVM抗流量分析能力测试

为验证ADVM的抗攻击能力，假设攻击者Attacker具备截获Bob1和Bob2发出的数据包的能力，攻击者分别对ADVM启用前后，Bob1和Bob2在 $5 ~ \mathrm { m i n }$ 通信时间内的数据包的地址分布情况的统计分析结果如图8所示。

由图8可知，ADVM启用之前，攻击者Attacker从截获到的流量可分析出Alice与Bob1和Bob2之间保持密切通信的关系；ADVM启用之后，攻击者Attacker从截获到的流量中分析出的是Bob1和Bob2与Ai和A2之间的通信关系较为密切，而与Alice之间的通信关系并不密切，提高了攻击难度。

![](images/b66658c9a2d9906e770f293d562d0d2644570e235027a92e19fae933b64d8044.jpg)  
图8 ADVM启用前后流量分析图

# 3.3抗DoS攻击能力测试

假设攻击者经过流量分析发现，Ai和 $\mathbf { A } _ { 2 }$ 是与Bob1和Bob2通信的关键节点，若能对其实施DoS攻击，那么Alice与Bob1和Bob2之间的通信必然受到攻击，然而在实际网络中，Ai和A2是的数量和节点都是随机变化的，为进一步测试ADVM的抗DoS攻击能力，在实验网络中逐步增加虚拟移动代理的部署，并进行相应测试，其测试结果如图9所示。

![](images/38575cf1a1642d695d662065422c5545010fbdb0662e88ae1537f16bf9c44565.jpg)  
图9不同个数攻击者DoS攻击成功率与VMA之间的关系

由图9可知，随着网络中虚拟移动代理个数的增加，攻击者成功实施DoS攻击的概率越低，但是攻击者个数的增加并没有显著增加DoS攻击成功率，与3.1节的分析结果一致。

# 3.4对比测试

文献[16]中提出一种基于佯动的移动IPv6位置隐私保护方案FBLPC，通过位于与移动节点不同链路的节点配合，形成MN移动至外地的“佯动”情形。虽然该方案可以保护移动节点的位置，但是其安全性取决于FRN，存在单点失效问题。

接下来，本文将从系统性能和方案安全性两个方面对这ADVM方案和FBLPC方案进行对比测试。首先，在传输相同大小文件（分别为1MB、2MB、3MB、4MB）时系统开销测试结果如图10所示。

由图10可知，传输相同大小的文件时，ADVM的开销略比FBLPC大，但仍然处于毫秒级。

700 600 FBLPC-固定 ■FBLPC-移动 500 (su) ■ADVM-固定 400 ADVM-移动 200 100 0

然后，分别在实验网络中部署1、3、5个攻击者，攻击者发起10次DoS攻击，对两种方案的抗DoS攻击能力进行了对比测试，其测试结果如图11所示。

![](images/9befdfe51b9090e702925a7e27ebd8c5df8962bf86a54850d562db309120812e.jpg)  
图10ADVM与FBLPC方案开销对比  
图11 ADVM与FBLPC抗DoS攻击能力对比

由图11可知，ADVM比FBLPC方案的抗DoS攻击能力更强，综合来看，ADVM方案以较小的额外开销，换来了更好的网络防护能力。

# 4 结束语

利用IPv6对移动特性的良好支持与多转交地址注册机制，本文提出一种基于虚拟移动的IPv6主动防御方案，通过为受保护IPv6节点随机分配多个动态变化的转交地址，使攻击者无法准确辨识目标节点是否发生真实移动及其位置，从而无法对其实施DoS攻击等。与已有方案相比，ADVM方案既能保证主动防御过程中的通信持续不间断，又能以较小的系统开销换取防护能力的较大提升。与移动IPv6相比，移动IPv4的主要不同之处在于：a)移动节点可以直接向通信对端发送数据，而通信对端必须经过家乡代理向移动节点发送数据；b)移动IPv4中没有返回路由可达过程；c)IPv4中需要使用IP-in-IP隧道进行数据传输。由于IPv6与IPv4将长期共存，虽然移动IPv4有别于移动IPv6的不同之处会增加系统开销，部分模块功能无法应用于移动IPv4中，但是虚拟移动思想仍然适用于IPv4网络环境。因此，本文下一步的主要工作是将该方案的各个功能模块进行细化，使虚拟移动方案在IPv6/IPv4共存环境中能够选择最优的虚拟移动策略，从而以较小的系统开销实现对共存环境下目标节点的有效防护。

# 参考文献：

[1]https://www.iab.org/2016/11/07/iab-statement-on-ipv6/[EB/OL].[2016- 11-07].   
[2]http:/politics.people. com.cn/n1/2017/1127/c1001-29668295．html [EB/OL].[2017-11-27].   
[3]http:/tech．sina．com.cn/i/2012-02-16/08086731105．shtml [EB/OL]. [2012-02-16].   
[4] 蔡桂林，王宝生，王天佐，等．移动目标防御技术研究进展[J].计算 机研究与发展,2016,53(5):968-987.   
[5]Kewley D,Fink R,Lowry J,et al. Dynamic approaches to thwart adversary intelligence gathering [C]//Proc of IEEE DARPA Information Survivability Conference& Exposition II.Piscataway,NJ:IEEE Press,2001:176-185.   
[6]Antonatos S,Akritidis P,Markatos E P,et al.Defending against hitlist worms using network address space randomization [J]. Computer Networks, 2007,51(12): 3471-3490.   
[7]Lee HCJ,ThingVLL.Port hopping for resilient networks [C]//Proc of the 60th Vehicular Technology Conference.Piscataway,NJ: IEEE Press, 2004:3291-3295.   
[8]Badishi G,HerzberG A,Keidar I. Keeping denial-of-service attackers in the dark [C]//Proc of Distributed Computing.Berlin: Springer, 2005:18-32.   
[9]石乐义，贾春福，吕述望．基于端信息跳变的主动网络防护研究[J]. 通信学报,2008,29(2):106-110   
[10] Jafarian JH,Al-Shaer E,Duan Qi.OpenFlow random host mutation: Transparent moving target defense using software defined networking [C]/ Proc of the 1st Workshop on Hot Topics in Software Defined Networks.New York:ACMPress,2012:127-132.   
[11] Al-shaer E,Duan Qi,Jafarian JH. Random host mutation for moving target defense [C]//Proc of Security and Privacy in Communication Networks. Berlin: Springer,2013: 310-327.   
[12] Jafarian JHH,Al-Shaer E,Duan Qi. Spatio-temporal address mutation for proactive cyber agility against sophisticated attackers [C]//Proc of the lst ACMWorkshop on Moving Target Defense.New York:ACMPress,2014: 69-78.   
[13] Dunlop M, Groat S, Urbanski W,et al. MT6D: a moving target IPv6 defense [C]//Proc ofMILCOM 2011.Piscataway,NJ: IEEE Press,2011: 1321-1326.   
[14] 刘慧生，王振兴，郭毅．一种基于多穴跳变的 IPv6 主动防御模型[J]. 电子与信息学报,2012,34(7):1715-1720   
[15] RFC 5648,Multiple care-ofaddresses registration [S].   
[16] 刘慧生，王振兴，张连成．基于佯动的移动IPv6位置隐私保护方案[J]. 计算机研究与发展,2012,49(Suppl.):74-81.