# 基于Renyi熵的Openflow信道链路泛洪攻击主动防御方法

蔡佳晔，张红旗，宋佳良(信息工程大学，郑州 450001)

摘要：针对新型链路泛洪攻击，提出一种基于Renyi熵的Openflow信道链路泛洪攻击主动防御方法。运用 Renyi熵分析攻击者在构建Openflow 信道Linkmap 过程中产生的ICMP 超时报文数量变化。一旦出现攻击前兆由流量监控服务器向控制器发出攻击预警，控制器启动交换机-控制器连接迁移机制，将交换机迁移至新的控制器下并使用新的Openflow 信道与之通信。实验证明，主动防御方法能有效避免控制器与交换机之间通信链路受到链路泛洪攻击的影响，确保控制器和交换机能持续交互提供网络服务，增强了SDN网络的健壮性。

关键词：链路泛洪攻击；Openflow信道；Renyi熵；主动防御中图分类号：TP393 doi: xxxxxx

Active defense method of Openflow channel link flooding attack based on Renyi entropy

Cai Jiaye, Zhang Hongqi Song Jialiang (Information Engineering University,Zhengzhou 45oo01,China)

Abstract:Fordefendingthenew link flooding attack,this paper proposedanactive defense methodofOpenflowchannellink floodingbasedon Renyi entropy.Analyzing the changes in the numberofICMP timeout messages produced byan attcke in the construction ofthe Openflowchannel Linkmap from Renyi entropy.Once atacks precursor wasdetected,flow monitoring serversendsanattack warningtothecontrollr,thencontrollerstartswitch-controllrconnectionmigrationmechanism,migrate theswitch toanew controlerand communicate with the new Openflow channel.Experimental results show thatthe active defense methodcan efectivelyavoid the impactoflinkflooding attck betweencontrolerandswitch and ensure thatcontroller and switch can provide continuous network services and enhance the robustness of SDN network.

ey words: link-flooding attack; Openflow channel; Renyi entropy; active defense

# 0 引言

近年来，一种名为链路泛洪攻击(link-flooding attack，LFA)的新型DDoS攻击引起学术界的广泛关注。不同于传统DDoS攻击以消耗目标服务器资源为目的，链路泛洪攻击旨在泛洪特定网络链路，阻止用户访问某个重要网络服务，间接破坏依赖这些链路的网络服务。链路泛洪攻击的实施策略相比普通DDoS攻击更加复杂，隐蔽性更高，其使用合法流量对目标链路实施攻击，使得网络防御机制无法进行有效应对。目前主流的链路泛洪攻击分为crossfire[1]和coremelt[2]，其中crossfire 因其不依赖于bots所处位置信息，所以在攻击发起前可以灵活指定不同的链路集合以达到避免引起警报的目的，相比于coremelt攻击更具威胁性。

攻击者发动链路泛洪攻击前需要收集目标服务器周围的链路信息，通常攻击者使用网络诊断工具（如traceroute）来进行这项工作，收集到的信息的集合被称为链路图（linkmap)。攻击者依据链路图筛选目标链路，一般筛选的目标链路流量密度较大，数据传输稳定，是用户访问网络服务的主干链路。攻击者选定目标链路后，将组织大量僵尸主机向目标链路发送低速合法数据流以消耗其带宽，导致链路丢包率和RTT值大幅上升，实现对目标链路的阻塞。链路泛洪攻击步骤如图1所示。

![](images/0b4bc5b01eae5d48e913c4775bfad409cc0081062938c191846cf677879af458.jpg)  
图1链路泛洪攻击实施步骤

SDN网络是一种新型网络架构，其显著特点是数据转发功能与控制功能分离，逻辑集中控制，实现对网络流量的灵活控制。Openflow作为一种开源协议目前已成为SDN的标准，SDN网络架构分为应用层，控制层与基础设施层，其中控制层是核心，通过Openflow信道向基础设施层的交换机下发流表转发规则，可见Openflow信道是控制层实现对全网有效控制的基础。Openflow信道是基于TCP的6633端口建立的，其可靠性有底层传输协议保证，同样会受到链路泛洪攻击的威胁。一旦攻击者对Openflow信道实施链路泛洪攻击，控制层面将无法及时有效地回应来自数据转发层的流表请求，也无法实时掌握全网动态，导致控制层面失去逻辑集中控制功能，达到间接破坏 SDN网络的目的。因此防范针对Openflow信道的链路泛洪攻击具有重要意义。

针对链路泛洪攻击的防御技术，学者们做了如下研究。文献[3]提出LinkScope 技术，采用端到端逐跳技术捕获异常链路性能下降来检测链路泛洪攻击;文献[4]使用修改后的路由器，可将低速攻击流从合法流量中检测出来，并保护合法流量;文献[5]使用SDN流量工程，临时增加目标链路的逻辑带宽，迫使攻击者增加攻击成本，从而使得攻击隐蔽性减弱;文献[6]提出软件定义蜜罐技术，引诱traceroute数据包进入蜜网，这样攻击者收集的是通往蜜网的链路，保护真正的网络服务链路不被攻击者探测到;文献[7]提出一种名为LFADefender的链路泛洪攻击防御架构，该系统利用SDN网络全局视图，流回溯功能以及网络虚拟化的弹性部署特性检测和缓解链路泛洪攻击。

以上研究大部分为攻击发生后采取的检测和缓解措施，在防御态势上处于被动一方。本文借鉴移动目标防御思想（movingtargetdefense,MTD)，采取主动防御姿态，提出一种针对Openflow信道链路泛洪攻击的防御方法。首先，在Openflow交换机北向接口处部署流量监控服务器，每隔固定时间段抓取Openflow信道中的数据包，统计ICMP 超时报文的数量;其次,运用Renyi 熵分析攻击者在构建Openflow 信道Linkmap过程中产生的ICMP超时报文数量变化，以此判断是否出现攻击前兆。最后，一旦出现攻击前兆由流量监控服务器向控制器发出攻击预警，控制器启动交换机-控制器连接迁移机制，将交换机迁移至新的控制器下并使用新的Openflow信道与之通信。

# 1 Traceroute

Traceroute是Linux系统用于路由探测的程序，通过ICMP“超时”和“端口不可达”两种消息配合记录通向目标主机路径的路由。具体原理如图2所示。

![](images/b3cbd1d2931dba68f62ca85864b377bc5a34869a6778fa5b6d2e2f1882ba7127.jpg)  
图2Traceroute 程序原理

Traceroute程序利用增加数据包存活时间(TTL)值实现路由探测功能，每当数据包经过一个路由器，TTL值就会减1。当

TTL值减为0时，路由器便丢弃数据包并向发送者传递ICMPTimeExceeded报文。Traceroute 程序一般首次发送TTL值为1的3个数据包，之后发送3个TTL值为2的数据包，依此类推。当traceroute 程序收到ICMPPortUnreachable 消息时，表明发送的数据包已到达目的主机，因为程序发送的数据包目标端口值一般选择应用程序都不会使用的号码(30000 以上)。

综上所述，某个用户使用traceroute程序进行路由探测的过程中会产生大量的ICMPTimeExceeded消息报文，其报文格式如下

![](images/a168aac597cf7a56f5706d57ca172543a1955a3b98d8dc1e7129647203698127.jpg)  
图3ICMPTimeExceeded 报文格式

ICMPTimeExceeded报文有两种，本文主机讨论ICMP报文是在TTL值为0时产生的，因此其代码字段为0。当代码字段为1时，为“组装报文超时”的ICMP报文。

# 2 Renyi熵

信息熵用于刻画随机变量的不确定性，熵值越高，变量随机性越大，熵值越低，变量随机性越小，确定度越高。信息熵在各个领域都有大量应用，如香农熵和Tsallis熵，但针对小流量的度量，Renyi熵相比香农熵更能增大两个分布之间的差异[8]。Renyi熵定义如下：

$$
H _ { \mathbf { \Gamma } _ { a } } ( x ) = \frac { 1 } { 1 - \alpha } \log _ { 2 } ( \sum _ { i = 1 } ^ { n } p _ { i } ^ { \alpha } )
$$

满足 $\mathfrak { p } _ { i } \in \left\{ p _ { 1 } , p _ { 2 } \ldots \mathfrak { p } _ { n } \right\}$ ，pi 是随机变量 $x _ { i }$ 的概率分布。 $\alpha \ge 0 , \alpha \ne 1$ 。

当 $\scriptstyle { \alpha = 0 }$ 时得最大值

$$
\operatorname* { m a x } ( H _ { \alpha } ( x ) ) = \log _ { 2 } ( n )
$$

当 $\alpha \to 1$ 时，Renyi 熵收敛于香农熵，证明如下：

$$
\operatorname* { l i m } _ { \alpha \to 1 } H _ { _ x } ( \alpha ) = \operatorname* { l i m } _ { \alpha \to 1 } { \frac { 1 } { 1 - \alpha } } \log _ { 2 } ( \sum _ { i = 1 } ^ { n } p _ { i } ^ { \alpha } ) = \operatorname* { l i m } _ { \alpha \to 1 } { \frac { \sum _ { i = 1 } ^ { n } p _ { i } ^ { \alpha } \ln p _ { i } } { \displaystyle \sum _ { i = 1 } ^ { n } p _ { i } ^ { \alpha } \ln 2 } }
$$

由于 $\sum _ { i = 1 } ^ { n } p _ { i } ^ { \alpha } = 1$ ,所以有

$$
\operatorname* { l i m } _ { \alpha  1 } H _ { _ x } ( \alpha ) = - \sum _ { i = 1 } ^ { n } p _ { _ i } ^ { \alpha } \bullet \log _ { _ 2 } p _ { _ i }
$$

当 $\alpha \to 0$ 时，有

$$
\frac { \hat { \sigma } H _ { \alpha } ( x ) } { \hat { \sigma } \alpha } \leq 0
$$

表明 $H _ { \alpha } ( x )$ 是一个随 $a$ 增大而减小的递减函数。

# 3 链路泛洪攻击主动防护原理

链路泛洪攻击防护原理如图4所示。

![](images/9ad36985eac9e3fb896ac2ee60674ef6bfee0072cf0381bbbfeb4ee3b2d03f2f.jpg)  
图4链路泛洪攻击防护原理

Openflowv1.4.0版本的协议支持交换机与多个控制器相连以便于两者之间连接关系的调整。因此图中交换机与两个控制器相连，控制器A为master控制器，用Openflow信道1与之相连，控制器B为slave 控制器，用Openflow 信道2与之相连。正常情况下交换机主要通过信道1与master控制器进行通信，当master控制器A收到链路泛洪预警信息时，启动交换机迁移机制，将控制器B变为master控制器并使用信道2进行通信。由于攻击者并不知道交换机与控制器之间的通信信道发生变化，仍然对信道1进行攻击，显然攻击未能达到预期效果，控制器与交换机之间的通信没有受到影响。当攻击者发现攻击无效后，必须再次发送探测数据包进行链路图的绘制工作及定位目标链路，无疑增加攻击者的难度和成本。

攻击者在发动针对Openflow 信道的DDoS攻击前，要进行链路图的收集工作。通常使用traceroute程序发送数据包进行路由探测，如前文所述在探测链路的过程中会产生大量的ICMPTimeExceeded消息，造成一段时间内ICMP包分布发生变化，基于traceroute 程序这一特性，且ICMP包在实际网络中属于小流量行为，本文使用Renyi 熵来描述Openflow 信道中ICMP包的分布情况。

在流量监控服务器部署抓包程序，每隔固定的时间段监控自网络搭建以来的数据包数量Mi作为监控数据，以ICMPTimeExceeded报文为统计对象统计其数量mi并作为统计数据。将监控数据Mi，统计数据mi以二元数组的形式存储在以时间增序的缓存队列里，如图所示为滑动时间窗口[9]，属于滑动时间窗口内的数据将作为主动防御算法的输入。主动防御算法循环提取缓存队列中的监控数据和统计数据，并计算Renyi熵，当判断熵值出现异常后向master控制器和slave 控制器发出链路泛洪预警信息。

本文提出的交换机与控制器的连接关系变化过程如下图6所示。假设在迁移过程中控制器A不再发送和迁移无关的新信息给交换机处理。

![](images/b38bb767a265d4ff7e3aad1755ba39bc70ef16e2a4e53416e2431c1a3df954d2.jpg)  
图5滑动时间窗□

![](images/04b08220933412f2db1e4dcf3ba4b3421be90cea481d80d0342aa149fdc8af60.jpg)  
图6交换机-控制器连接迁移流程

a）控制器A向交换机发送添加流表项的指令，并将一条虚假的流表项添加进交换机中。b)为了确保交换机安装该虚假流表项，控制器向交换机发送 barrier-request 消息。c）交换机安装虚假流表项后向控制器发送barrier-reply 消息回应控制器发送的barrier-request 消息。d）控制器B向交换机发送role-request 消息，申请将自己对交换机的身份从slave 转变为equal。e）交换机向控制器B发送role-reply消息告知其身份转变已完成。能够接收交换机发送的异步消息（asynchronousmessage)，为迁移做好准备。f）控制器A向交换机发送flow-mod 消息，指示交换机将之前安装的虚假流表项删除。g）交换机同时向控制器A和控制器B发送flow-removed消息。h）控制器B收到 flow-removed 消息后发送role-request 消息给交换机请求将自己的角色转变为master。i）交换机向控制器B发送role-reply消息，通知控制器B身份转变已完成。同时根据Openflow协议，控制器A的角色自动设置成slave。

# 4 主动防御算法

本文通过研究攻击者使用的链路探测程序traceroute 的原理，分析运行过程中出现的特征与链路泛洪攻击的关联，提出了一种针对 Openflow 信道链路泛洪攻击的主动防御算法，提高的SDN的稳定性和健壮性。图7给出算法的流程。

![](images/9772a689ed60366fdc9057c32e89633179ad1ab6b5bba2cb47eb65f4c3821cd8.jpg)  
图7算法流程

a）循环读取时间窗口内的监控数据和统计数据b）计算ICMPTime Exceeded 报文的Renyi熵，若熵值高于预警阈值ε，则返回上一步，若低于预警阈值ε，则进行下一步。c）启动计数器count，其值加1。d）判断计数器count值是否大于告警阈值δ，若不大于阀值δ则判定为正常主机的链路连通性测试，并返回步骤a)。若大于阈值8，则认定为僵尸主机的链路探测行为，输出链路泛洪预警信息，并进行下一步。

e）启动交换机迁移机制。

在实际 SDN中部分主机为测试端到端的连通性会发送ICMP报文，也同样可能会造成ICMPTimeExceeded消息报文数量突变，为了降低算法误报率，避免因交换机频繁迁移导致的网络性能下降，设立一个告警阈值δ。当Renyi熵值低于预警阈值ε的次数超过8时，认定为正常主机的链路连通性测试，当次数高于阈值8，认定为僵尸主机链路探测行为。阈值和δ 需经实验确定。

在算法复杂度方面，设待检测的数据样本总数为N，算法中两个循环的关系并不是嵌套关系，而是互斥关系，因此可得算法复杂度为O(N)。

算法：主动防御算法

(1)do readData//循环读取时间窗口内的监控数据和统计数据(2） $H \mathcal { \partial } \mathbf { \partial } = \mathbf { \partial }$ calculate(ICMP）//计算ICMPTime Exceeded报文的 Renyi熵Hd(3)while Hok $\varepsilon$ //若熵值低于预警阈值，重新读取数据(4) count $^ { t + }$ //低于预警阈值ε，count+1(6)ifcount>δ（7） then alarm(）//僵尸主机的链路探测行为，输出预警(8) then启动交换机迁移机制(9)elsecontinue//正常主机的链路连通性测试(10) End

# 5 仿真实验

实验拓扑本文实验环境基于Mininet仿真平台，使用Openflowv1.4版本协议，控制器使用Floodlight版本，交换机为OpenvSwitch和刷写了OpenWRT开源系统,并能支持Openflowv1.4版本的路由器。搭建的网络拓扑如图8所示

![](images/d421b6b5fb90ae5dc2b24edeadcc2e795471e39a8e8a1cc83f12c0988c46c65b.jpg)  
图8实验拓扑图

实验拓扑中Openflow交换机个数为20，控制器个数为10，路由器个数为80。网络初始状态下控制器C1至C5为 master控制器，C6至C10为slave控制器。路由器用于模拟真实网络中的Openflow 信道，其中R1至 R40 模拟Openflow 信道1，R41至R80 模拟Openflow 信道2。流量监控服务器部署在Openflow交换机北向接口处，每个交换机和3台终端相连。

# 6 实验结果分析

实验首先模拟僵尸主机的不同链路探测强度，将探测强度分为三个等级，一级探测强度模拟僵尸主机使用traceroute 程序发送TTL值依次为1至10 的数据包。二级探测强度模拟僵尸主机使用traceroute 程序发送TTL值依次为1至20的数据包。三级探测强度模拟僵尸主机使用traceroute 程序发送TTL值依次为1至30的数据包。用于模拟Openflow信道的路由器为40台，因此三级强度已接近完成链路探测总量的 $7 5 \%$ 。图9\~11为三个探测强度下ICMPTime Exceeded 报文的Renyi 熵和香农熵的变化曲线。

在 20 s时模拟僵尸主机对Openflow 信道1依次实施一、二、三级强度的链路探测，图9显示一级探测强度下检测到两次ICMPtimeexceeded报文的熵值偏离正常值的情况并在27s处回归正常水平。其中香农熵值偏离程度最小；随着阶数 $\mathfrak { a }$ 的增大，Renyi 熵值偏离程度逐渐增大，在 $\scriptstyle { \mathsf { a } } = 1 0$ 时偏离程度最大，达到0.2068。图10显示二级探测强度下检测到4次熵值偏离正常值的情况并在32s处回归正常情况，阶数 $\scriptstyle { \mathsf { a } } = 1 0$ 的Renyi熵偏离最大，达到0.2490。图11显示检测到8次熵值偏离情况，阶数 $\scriptstyle { \mathfrak { a } } = 1 0$ 的Renyi熵偏离幅度最大，达到0.3898，熵值在$4 0 \mathrm { ~ s ~ }$ 处才回归正常水平。

![](images/b63c21e89b72f0d2c366891ec71e1fedaf349edbc42e0ee7938adc1f0721cfd2.jpg)  
图9一级探测强度熵值

![](images/26baa99d193be7bbbe9833f2a6c1304380a2b0ad45f3ae72105bb58b4c06f851.jpg)  
图10二级探测强度熵值

![](images/2caeb26b85b2d50323e90743b61ca5efc6e6f5d70dd9896d5c903223492af0f2.jpg)  
图11三级探测强度熵值

综上所述，随着探测强度的增大，熵值偏离的幅度也不断加大，这是因为探测过程中生成的ICMPTimeExceeded报文数量占总流量的比重不断升高，但ICMP报文在实际网络中是小流量行为，增加比例较小，香农熵变化幅度有限，无法及时对ICMP流量的变化作出反映，检测灵敏度较低。而Renyi熵无论在哪种探测强度下，都能"放大"流量特征的变化，检测灵敏度高。表1\~3为不同探测强度下香农熵和Renyi熵的具体值。通过对比，Renyi熵在阶数 $\scriptstyle { \mathfrak { a } } = 1 0$ 时检测灵敏度最高，正常平均熵值为1.6439，所以将阈值ε设为1.6439。当检测到熵值偏离8次时，攻击者已完成约 $7 5 \%$ 的探测量，因此本文将阈值δ设为8，避免因小流量变化导致频繁启动交换机迁移，降低整个SDN 网络的性能。

表1一级探测强度各阶数Renyi 熵  

<html><body><table><tr><td>阶数</td><td>正常平均熵值</td><td>最低熵值</td><td>拐点差</td></tr><tr><td>香农熵</td><td>1.7851</td><td>1.7809</td><td>0.0042</td></tr><tr><td>α-2</td><td>1.7384</td><td>1.6894</td><td>0.0490</td></tr><tr><td>α=6</td><td>1.6968</td><td>1.5921</td><td>0.1047</td></tr><tr><td>α=10</td><td>1.6439</td><td>1.4371</td><td>0.2068</td></tr></table></body></html>

表2二级探测强度各阶数Renyi 熵  

<html><body><table><tr><td>阶数</td><td>正常平均熵值</td><td>最低熵值</td><td>拐点差</td></tr><tr><td>香农熵</td><td>1.7851</td><td>1.7249</td><td>0.0602</td></tr><tr><td>α=2</td><td>1.7384</td><td>1.6461</td><td>0.0923</td></tr><tr><td>α-6</td><td>1.6968</td><td>1.4846</td><td>0.2122</td></tr><tr><td>α=10</td><td>1.6439</td><td>1.3949</td><td>0.2490</td></tr></table></body></html>

表3三级探测强度各阶数Renyi 熵   

<html><body><table><tr><td>阶数</td><td>正常平均熵值</td><td>最低熵值</td><td>拐点差</td></tr><tr><td>香农熵</td><td>1.7851</td><td>1.7031</td><td>0.0820</td></tr><tr><td>α=2</td><td>1.7384</td><td>1.6157</td><td>0.1227</td></tr><tr><td>α=6</td><td>1.6968</td><td>1.3629</td><td>0.3339</td></tr><tr><td>α=10</td><td>1.6439</td><td>1.2541</td><td>0.3898</td></tr></table></body></html>

在确定算法阈值后进行算法防护效果测试，Openflowv1.4协议中规定当一个Openflow 交换机与 master 控制器的通信中断时会进入 STANDALONE 状态，进入该状态的Openflow 交换机会转变成传统二层交换机建立MAC表进行数据包转发工作。

实验模拟攻击者对Openflow 信道1发动链路泛洪攻击的全过程。下图描绘了实验过程中处于STANDALONE状态的Openflow交换机的数量，在0\~30s模拟攻击者发送traceroute数据包进行链路图收集工作，30s时对Openflow信道1进行模拟链路泛洪攻击，可以看到当没有部署动态防御算法时，随着时间的推移变成STANDALONE状态的交换机数量急剧上升，在 $4 0 \mathrm { ~ s ~ }$ 时所有交换机均处于STANDALONE状态，此时表明master 控制器无法与交换机进行通信，SDN网络彻底瘫痪，Openflow交换机退化为传统二层交换机。

当部署了动态防御算法后，可以看到仅有2台交换机处于STANDALONE状态，原因是有的交换机还未完成迁移流程时与master控制器通信的链路就被阻断，尤其在交换机处理barrier消息时需要将之前控制器发送的消息处理完毕后才能回复barrierreply消息，无疑增加了迁移所用的时间，但整体防御效果符合理论预期。

![](images/31079e18899bb4e7edb774d788c4c9d9f328f64bf814f812e3a903bb99963055.jpg)  
图12防御效果

# 7 结束语

本文提出了一种基于Renyi熵的Openflow信道链路泛洪攻击主动防御方法，在Openflow交换机北向接口部署流量监控服务器，监控Openflow信道内ICMP超时报文数量，当报文数量出现异常时启动交换机迁移机制，交换机使用新Openflow信道与新master控制器进行通信。经实验证明主动防御方法能有效避免控制器与交换机之间通信链路受到链路泛洪攻击的影响,确保控制器和交换机能持续交互提供网络服务，增强了SDN的健壮性。今后的研究工作将继续围绕SDN控制层面的网络动态防御技术研究，提高SDN整体安全性。

# 参考文献：

[1]KangMS,Lee SB,GligorVD.The crossfire attack [C]// Security and Privacy.2013:127-141.   
[2]StuderA,Perrig A.The coremelt attack [C]// Lecture Notes in Computer Science,vol. 2009:37-52.   
[3]Xue L,Luo X,Chan EWW,et al. Towards detecting target link flooding attack [C]//Proc of USENIX Conference on Large Installation System Administration.[S.1.]:USENIX Association,2014.   
[4]Lee SB,Kang M S,Gligor VD.CoDef: collaborative defense against largescale link-flooding attacks [C]// Proc of ACM Conference on Emerging NETWORKING Experiments and Technologies.New York:ACM Press, 2013:417-428.   
[5]Kang M S,Gligor VD, Sekar V,et al. SPIFFY: inducing cost-detectability tradeoffs for persistent link-flooding attacks[C]//Proc of Network and Distributed System Security Symposium.2016.   
[6]Kim J,Shin S. Software-Defined HoneyNet: towards mitigating link flooding attacks $[ \mathrm { C } ] / \AA$ Proc of IEEE//IFIP International Conference on Dependable Systems and Networks Workshop.Washington DC:IEEE Computer Society,2017: 99-100.   
[7]刘世辉．基于 SDN 和 NFV 的链路洪泛攻击检测与防御 [D].武汉：武 汉大学,2017.   
[8]Zyczkowski K. Renyi extrapolation of Shannon entropy[J].Physics,2003, 10 (3): 297-310.   
[9]蔡佳晔，张红旗，高坤．基于 Sibson 距离的OpenFlow 网络 DDoS 攻击 检测方法研究[J]．计算机应用研究,2018,35(6).   
[10]张朝昆，崔勇，唐骂祎，等．软件定义网络(SDN)研究进展[J]．软件 学报,2015,26(1):62-81.   
[11]Wang Qian,Xiao F,Zhou M,et al.Linkbait: active link obfuscation to thwart link-flooding attacks [J].arXiv:1703.09521,2017.   
[12]Wang L,Li Q, Jiang Y,et al.Towardsmitigating link flooding atack via incremental SDN deployment [C]// Computers and Communication.2016: 397-402.   
[13]王鹏．防止链路型DDoS攻击的实现方法和系统：中国,CN105049441A [P]. 2015.   
[14]王利明，雷程，马多贺，等．一种基于转发路径自迁移的链路型 DDoS 防御方法及系统：中国,CN106961387A[P].2017.   
[15]陈宇，温欣玲，段哲民，等．一种大规模IP 网络多链路拥塞推理算法 [J]．软件学报,2017,28(7):1815-1834.