# 基于活动区域的移动无线传感器网络路由协议

冉涌1，李芳²

(1．重庆三峡职业学院，机械与电子工程系，重庆 404155;2.重庆大学，计算机学院，重庆 400044)

摘要：为了解决移动无线传感器网络中能量效率问题，提出了一种基于活动区域的移动无线传感器网络（WSN）路由协议。本方法使用源和sink节点相对位置来形成路由的活动区域，网络中的移动节点使用睡眠唤醒模式来节约能源。移动向量信息（如当前位置，方向和速度）以及节点的剩余能量，用于选择能够提供最大连接保留时间的邻居，移动向量信息也被用来唤醒活动区域中的移动节点。实验表明，与其他路由协议进行比较，该方法在分组传输过程具有更高的可靠性。

关键词：能量效率；活动区域；无线传感器网络；路由协议；移动性向量中图分类号：TP393.04 doi:10.3969/j.issn.1001-3695.2018.05.0323

Mobile wireless sensor network routing protocol based on active region

Ran Yong1,Li Fang² (1.Dept.ofMechanical&Electrical Engineering,ChongqingThree Gorges Vocational Collge,Chongqing404155,China;2. School of Computer Science,Chongqing University,Chongqing 4Ooo44,China)

Abstract: Inorder tosolve the problem of energy eficiency inmobile wirelessensor networks,this paperproposes a mobile wirelesssensor network(WSN)routing protocolbasedonactiveregion.This methoduses therelativepositionsof the source andthe Sink node to form theactive region for routing.The mobile node in the network uses useaslep-wakeup pattern to conserve energy.The motion vector information,suchas current position,directionand speedandtheremaining energyof the node areused to selectthe neighbors thatcan providethe maximumconnection retention time.The motion vectorinformation is also usedto wakeupthe mobilenode intheactivearea.Experiments showthatcompared with otherrouting protocols,this method has higher reliability in packet transmission process.

Key words: energy efficiency; active region; wireless sensor network; routing protocol; mobility vector

# 0 引言

随着无线传感器网技术的发展[I]，移动无线传感器网络（mobilewirelesssensornetworks，MWSN）以低功耗、低成本的优势得到越来越多关注，其应用领域越来越广泛，如健康监测，跟踪车辆或监测特定区域等领域[2]。随着移动性的增加，节点必须不断适应频繁的拓扑变化，从而导致每个节点的能耗增加[3.4]。移动无线传感器网络中的能量效率对于确定节点的寿命以及节点本身的寿命至关重要。

为了解决节点能耗增加的问题，节点需要通过进入睡眠模式来避免不必要的运行时间，除非需要被激活[5]。确定何时将传感器节点置于睡眠状态可能是有个难点，因为处于睡眠状态的节点无法接收任何通信;另一方面，始终保持一个节点，即使它没有感应或通信，也会导致不必要的能量消耗。在网络协议栈设计方面，引入移动性具有挑战性[6]。

常规路由协议使用路由表将数据路由到目标[7]，由于动态拓扑，MWSN的情况下，路由表的频繁更新是不可避免的。网络需要频繁地执行路由发现，同时优化能耗、时间和带宽，动态拓扑也会导致频繁的链路中断，从而影响正在进行的通信。

Luo 等人[8提出了WSN的最小化能量消耗方法，并最大化一维队列网络的网络寿命，其中传感器的位置是预先确定的且不可更改的，其目标是通过考虑它们到汇的距离和剩余能量的差异来优化网络能效。Kumar等人9在研究了无线传感器网络基于位置的路由协议的基础上，提出了一个系统而全面的基于位置的路由协议分类法，主要用于传感器网络。文献[10\~12]中提出了使用电晕机制来支持移动性的低功耗和有损网络（RPL）的路由协议。由于该方法重复使用相同的控制消息并保持与标准规范的向后兼容性，因此该方法只需很少的附加组件。标准RPL在为移动WSN提供QoS保证方面非常有限。

本文提出了一种基于区域的移动无线传感器网络

（MWSN）路由协议，为了移动数据路由，在源和宿周围会生成一个活动区域，只有活动区域中的节点参与路由选择，其余节点遵循睡眠唤醒模式。数据路由以这样的方式完成，即参与路由的节点保持靠近连接源和sink节点的欧式距离。本文方法使用节点睡眠唤醒模式来节约能源，活动区域中的节点参与路由选择，保证数据包传输的可靠性。

# 1 本文提出的路由协议

对于传感器网络的 $M$ 个移动节，每个移动节点在区域 $A$ 内以速度 $\nu _ { i }$ （角度 $\theta _ { i }$ ）随机移动，基站放置在位置 $\left( { x } _ { b } , { y } _ { b } \right)$ ，所有节点遵循睡眠唤醒模式来提高能源效率。假设这些移动节点可以使用GPS或类似的技术确定他们的位置，并且可以自由导航。

睡眠唤醒模式已被用于降低能耗，每个节点休眠 $T$ 时间，且在 $\Delta T$ 被唤醒，其中 $\Delta T \ll T$ 。源 $N _ { s }$ 和基站 $B S$ 之间的通信通过创建圆角矩形区域R来建立。本文所提出的方法基于使用移动性向量信息计算的接触时间来选择最优节点来转发数据分组。邻居选择协议如下所示，协议有两个阶段，信令阶段和数据传输阶段。

# 1.1信令阶段

当节点有数据要传输时，则从信令阶段开始，信令阶段的目标是在源和基站之间形成一个活动区域，其中所有的传感器节点都处于唤醒状态。在此阶段，节点使用源和目标位置的信息来创建连接源和目标的虚拟区域，该区域如图1所示的体育场区域，其中半径 $\boldsymbol { r ^ { \prime } }$ 的圆圈通过中心切成两半，然后两端用一个边长为的矩形分开。

![](images/4ca68e837b1eeb221e88b5489845f60da60b7e7329d3b25da4bea2d0e741de28.jpg)  
图1源通过移动中继到Sink节点示意图

区域形成的面积为 $\hat { A } = \pi r ^ { \prime 2 } + 2 r ^ { \prime } a$ ，根据节点相对于设定区域的位置将节点划分为区外和区域内。区域 $\hat { A }$ 中的节点被分类为区域内，如果一个节点 $x \in A : x \notin { \hat { A } }$ ，则被分类为一个区域外节点，节点的分类如图1所示。源和基站位于圆形区域的中心。最初，每个节点都作为一个区域外节点开始，所有分类为区域外的节点都遵循睡眠唤醒模式，在清醒时，这些节点发出参与请求 $P _ { r e q }$ 消息。

如果任何被分类为区域内的节点接收到 $P _ { r e q }$ 消息，则在小于 $\Delta t$ 的随机等待时间之后发送参与回复 $P _ { r e q }$ 消息，包含在 $P _ { r e q }$ 消息中的源和目的地信息由节点用来决定其是否属于区域 $\hat { A }$ ，节点保持其无线状态，直到它移动到区域 $\hat { A }$ 之外。

# 1.2数据传输阶段

数据通信阶段在信号阶段之后开始，在数据通信期间，只有活动节点参与。信令阶段用于唤醒区域R中的所有节点，这些节点在通信阶段转发数据。每个数据分组头包含用于保存源节点和 Sink 节点位置的 $S _ { p o s }$ 和 $D _ { p o s }$ 字段，移动节点使用此字段动态重新计算活动区域。如果一个节点有数据要传输，需要找到一个邻居进行通信，发送方节点向所有邻居广播数据请求分组数据 $d a t a _ { r e q }$ ，所有收到数据包的活动节点在一小段时间 $\rho _ { t }$ 后回复给发送者， $\rho _ { t }$ 值与每个邻居的优先级值成反比。

优先级是由节点保持在发送 $d a t a _ { r e q }$ 分组的邻居节点传输范围内以及其相对于目的地位置的位置多长时间来决定的，$d a t a _ { r e q }$ 消息的邻居将避免自己发送回复消息，随后数据被发送到选定的移动节点，数据可以发送到最多 $\hat { t }$ 时间单位。这个过程在有数据要发送的每个节点上重复。之后将描述用于计算两个节点保持在传输范围（接触时间 $\hat { t }$ ）内的时间。

接触时间计算：两个移动节点 $n _ { \mathrm { { \scriptscriptstyle 1 } } }$ 和 $n _ { 2 }$ 的接触时间是两个节点保持在传输范围 $\boldsymbol { r }$ 内的时间。设 $\overrightarrow { X _ { \scriptscriptstyle 1 } }$ 为节点 $n _ { \mathrm { { 1 } } }$ 在时间 $\mathbf { \Phi } _ { t }$ 的位置向量， $\overrightarrow { X } _ { 1 } ( t )$ 是节点 $n _ { \mathrm { { 1 } } }$ 的位置矢量， $\overrightarrow { X _ { 2 } }$ 为节点 $n _ { 2 }$ 在时间 $\mathbf { \Phi } _ { t }$ 的位置向量， $\widehat { X _ { 2 } } ( t )$ 是节点 $n _ { 2 }$ 的位置矢量。两个移动节点以速度 $\nu _ { 1 }$ ，$\nu _ { 2 }$ 移动的情况如图2所示。

![](images/c61315cdd9feb9f782716c7308d93a2d1da989749041cfa89f9d7e955e4599f9.jpg)  
图1两个移动节点移动情景

假设 $t _ { 0 }$ 时刻是计算 $\mathbf { \Phi } _ { t }$ 值时的值， $\left| \overrightarrow { X _ { \scriptscriptstyle 1 } } ( t _ { 0 } ) - \overrightarrow { X _ { \scriptscriptstyle 2 } } ( t _ { 0 } ) \right|$ 是最初节点之间的距离，并且这将小于节点的传输范围 $\boldsymbol { r }$ 。假设 $t ^ { \prime }$ 是节点超出通信范围的时间，则有

$$
\left| \overrightarrow { X _ { 1 } } ( t ^ { \prime } ) - \overrightarrow { X _ { 2 } } ( t ^ { \prime } ) \right|
$$

$$
t ^ { \prime } { = } \operatorname* { m i n } t \ | | \overrightarrow { X _ { 1 } } ( t ) - \overrightarrow { X _ { 2 } } ( t ) | > r
$$

则对于移动节点 $n _ { \mathrm { { } _ { l } } }$ 和 $n _ { 2 }$ 的接触时间 $\hat { t }$ 表示为 $t ^ { \prime } – t _ { 0 }$ ，因此，两个节点的相对速度为 $\overrightarrow { \nu _ { r } } = \overrightarrow { \nu _ { 1 } } - \overrightarrow { \nu _ { 2 } }$ ，沿 $x$ 和 $y$ 方向的速度为

$$
\left\{ \begin{array} { l l } { { \nu _ { r } \left( x \right) = \nu _ { 1 } \cos \theta _ { 1 } - \nu _ { 2 } \cos \theta _ { 2 } } } \\ { { \nu _ { r } \left( y \right) = \nu _ { 1 } \sin \theta _ { 1 } - \nu _ { 2 } \sin \theta _ { 2 } } } \end{array} \right.
$$

其中 $\nu _ { 1 } = \left| \nu _ { 1 } \right|$ ， $\nu _ { { } _ { 2 } } = \left| \nu _ { { } _ { 2 } } \right|$ 。此后，可以使用该公式获得幅度和相对速度。幅度可表示为

$$
\sqrt { \nu _ { r } ^ { 2 } \left( x \right) + \nu _ { r } ^ { 2 } \left( y \right) }
$$

相对速度的方向可以表示为：

$$
\tan ^ { - 1 } \left( \frac { \nu _ { \mathrm { 1 } } \sin \theta _ { \mathrm { 1 } } - \nu _ { \mathrm { 2 } } \sin \theta _ { \mathrm { 2 } } } { \cos \theta _ { \mathrm { 1 } } - \nu _ { \mathrm { 2 } } \cos \theta _ { \mathrm { 2 } } } \right) = \tan ^ { - 1 } \left( \frac { \nu _ { r } \left( y \right) } { \nu _ { r } \left( x \right) } \right)
$$

最初，节点 $n _ { \mathrm { { \scriptscriptstyle 1 } } }$ 和 $n _ { 2 }$ 在时间 $t _ { 0 }$ 处的距离为 $d _ { 0 }$ ，则有

$$
d _ { 0 } = \left| \overrightarrow { X _ { 1 } } ( t _ { 0 } ) - \overrightarrow { X _ { 2 } } ( t _ { 0 } ) \right|
$$

其中： $d _ { 0 } < r$ ，时间 $t ^ { \prime }$ 由式(2)给出，因此，接触时间可表示为

$$
\left( t ^ { \prime } - t _ { 0 } \right) = \left( \frac { r - d _ { 0 } } { \sqrt { \nu _ { r } ^ { 2 } \left( x \right) + \nu _ { r } ^ { 2 } \left( y \right) } } \right)
$$

如果 $\left( x _ { 1 } , y _ { 1 } \right)$ 是节点 $n _ { \mathrm { { } _ { 1 } } }$ 在时间 $t _ { 0 }$ 处的坐标， $\left( x _ { 1 } , y _ { 1 } \right)$ 是节点 $n _ { 2 }$ 在时间 $t _ { 0 }$ 处的坐标，则在时间 $t _ { 0 }$ ，节点 $n _ { \mathrm { { } _ { 1 } } }$ 和 $n _ { 2 }$ 之间的欧式距离$d _ { 0 }$ 由等式(8)得到。

$$
d _ { 0 } = \sqrt { \left( x _ { 1 } - x _ { 2 } \right) ^ { 2 } + \left( y _ { 1 } - y _ { 2 } \right) ^ { 2 } }
$$

接触时间将是节点超出范围 $\boldsymbol { r }$ 所需的时间。节点 $n _ { \mathrm { { } _ { 1 } } }$ 和 $n _ { 2 }$ 的距离是 $d _ { 0 }$ ，相对速度使其分开 $r - d _ { 0 }$ 。则接触时间为 $r - d _ { 0 } / | \nu _ { r } |$ ，$\left| \nu _ { r } \right|$ 表示相对速度的大小。最终接触时间可由式(9)得到。

$$
\hat { t } = \frac { r - \sqrt { \left( x _ { 1 } - x _ { 2 } \right) ^ { 2 } + \left( y _ { 1 } - y _ { 2 } \right) ^ { 2 } } } { \sqrt { \left( \nu _ { 1 } \cos \theta _ { 1 } - \nu _ { 2 } \cos \theta _ { 2 } \right) ^ { 2 } + \left( \nu _ { 1 } \sin \theta _ { 1 } - \nu _ { 2 } \sin \theta _ { 2 } \right) ^ { 2 } } }
$$

下面给出了该方法的算法，算法分为三部分。算法1检查节点是否有数据要传输。

procedure START(node) if node has data then Call CALCULATE NEXT HOP(node) else if node $\neq$ source && node $\neq$ destination then call SETTIMER(node,Check area) end if end if end procedure

#

如果没有要传输的数据，则节点将在睡眠区域之外进入休眠状态，如果目标位于发送节点的范围内，它将直接将数据转发到目标，否则，发送方根据最高 $\hat { t }$ 值选择一个节点来转发数据。算法2过程中是算法1中使用的CALCULATENEXTHOP(node)函数。

procedure CALCULATE NEXTHOP(node) max $\mathbf { \tau } = \mathbf { \tau }$ NEGATIVE_VALUE for all i do Calculate $\begin{array} { r l } { \widehat { t } } & { = \mathrm { C O N T A C T \_ T } \mathrm { C A L C } ( \mathrm { n o d e } , i ) , } \end{array}$ （204号 where $i$ is neighbor(node) if max <fthen $\operatorname* { m a x } = \mathbf { \Gamma } _ { \hat { t } } \ \mathbf { \Gamma }$ end if end for   
if d(node,destination) $\prec \mathrm { { r } }$ )then

node $$ contact_time $\mathbf { \tau } = \mathbf { \tau }$ CONTACT_T_CALC(node,destination); node $$ nexthop $\mathbf { \tau } = \mathbf { \tau }$ destination else node $$ contact_time $\ O =$ max node-→nexthop $\ O =$ hop

# end if

# end procedure

接触时间计算在算法3中给出，算法3使用式(9)计算接触时间 $\hat { t }$ ，移动Ad-hoc 网络采用类似的方法来预测接触时间。一旦移动节点移出活动区域，就会进入睡眠唤醒状态，以保持能源效率。

$$
\mathbf { i f } d ( n _ { 1 } , n _ { 2 } ) < d ( n _ { 1 } , d e s t ) \& \& d ( n _ { 2 } , d e s t ) <
$$

$$
a = \nu _ { { 1 } } \cos \theta _ { { 1 } } - \nu _ { { 2 } } \cos \theta _ { { 2 } } , b = \nu _ { { 1 } } \sin \theta _ { { 1 } } - \nu _ { { 2 } } \sin \theta _ { { 2 } }
$$

$$
c = x _ { 1 } - x _ { 2 } , c = y _ { 1 } - y _ { 2 } , { \hat { t } } = \left( { \frac { r - { \sqrt { c ^ { 2 } + d ^ { 2 } } } } { { \sqrt { a ^ { 2 } + b ^ { 2 } } } } } \right)
$$

# end if

# end procedure

本协议中使用的算法不会保留与邻近其他节点相关的任何数据。源节点和目标节点的位置是唯一保存在其内存中的数据。因此，该协议中使用的算法具有恒定的空间复杂度，对于参与数据传输的每个节点，需要完成接触时间计算。在最坏的情况下，一个节点可以有 $n$ 个节点在其附近，其中 $n$ 是节点的总数。为了计算数据传输的下一跳邻居节点，还需要 $O ( n )$ 时间复杂度。邻居计算发生在每个特定的时间间隔之后，因此，该协议中使用的算法具有线性时间复杂度O(n)+O(n)=2×O(n)=O(n)。

# 2 实验结果与分析

为了验证和分析本文提出移动无线传感器网络路由协议的性能，在Intelcore i7， $2 . 6 9 \ : \mathrm { G H z }$ 和4GBRAMWin10系统上的OMNeT $^ { + + }$ 框架下实现仿真，无线网络传感器仿真参数如表1所示。

表1仿真实验参数  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>区域大小</td><td>200m*200m</td></tr><tr><td>节点总数</td><td>55</td></tr><tr><td>数据包大小</td><td>128byte</td></tr><tr><td>sink节点</td><td>(0，0)</td></tr><tr><td>初始能量</td><td>0.1J</td></tr></table></body></html>

<html><body><table><tr><td>Eelec</td><td>50 nJ/bit</td></tr><tr><td>Efs</td><td>20 pJ/bit/m²</td></tr><tr><td>εmp</td><td>0.013 pJ/bit/m4</td></tr></table></body></html>

为了体现本文算法的优越性，将本文算法与其他算法进行比较，目前文献中有较少协议可以通过移动中继支持WSN 中的节能路由，本文选择了基于接收方机会转发协议（ROF）和贪婪周边无状态路由转发算法（GPSR）与本文方法进行比较。由于复杂度较低，因此不需要全局表（均使用本地拓扑信息来选择通信的直接邻居)。

基于ROF协议不需要在源和目的地之间建立全局路由。ROF选择相对于发送方的邻居节点来争夺转发权限。ROF协议优化了转发优先级计算，设计了基于双通道的转发权争用机制，处理数据冲突和转发延迟。GPSR使用关于网络拓扑中的发送者的直接邻居的信息来做出决定。在GPSR中，当数据包到达贪婪转发区域时是不可能的，该算法通过绕该区域的周边进行路由而恢复。对于具有移动节点的动态拓扑结构，GPSR可以快速找到正确的新路线。

仿真假设单个源-目标对。随机点移动模型用于确定节点位置，分析是通过改变源节点的数量，数据速率和节点速度来完成的，数据包大小设置为128 Byte。

图3显示了本文提出的协议，ROF和GPSR的分组传递率（packet deliver ratio,PDR)，节点以 $0 . 5 ~ \mathrm { m / s }$ 的速度移动，发送者速率从 $1 0 \mathrm { p p s }$ 变化到 $2 0 0 ~ \mathrm { p p s }$ 。结果表明，与其他协议相比，本文方法产生更好的PDR，可以看出GPSR具有最小的PDR。

为了进一步分析和验证协议，节点速度是变化的，速度从$0 . 5 ~ \mathrm { m / s }$ 到 $1 0 ~ \mathrm { m / s }$ 不等，以 $2 0 ~ \mathrm { p p s }$ 的速率发送数据包,计算每种方法的PDR，结果显示在图4中。从图4中可以得到，本文提出协议在性能上表现的更好。

![](images/f5819333c25599a07868cb328c93aa8c3f14de5050f1d63d5ba991dd2af3a65e.jpg)  
图3分组传递率与速率关系

![](images/a5cb7256540ae48830793a727acccd02118053320142a3f357a46fd8b2c33b27.jpg)  
图4分组传递率与速度的关系

本文协议的效率在改变速度的同时比较彼此接触范围内的节点数量来评估。实验时间300s，多次迭代的平均值用于分析，结果如图5所示。可以得出，参与整个数据通信的节点数量与ROF相比较少，这是因为所提出的协议选择具有最大接触时间的邻居节点。另外，随着速度的增加，接触的移动节点的数量也增加，这是由于高度动态的拓扑结构造成的。

![](images/162030f92d307e24e0116f65a8d085e90610fb96639e90f97e4aa0b9c99557a3.jpg)  
图5数据通信节点的数量与速度的关系

图6给出了计算每个节点的平均接触时间，并且与ROF协议进行比较。可以得出由于邻居选择算法优选地选择邻居，所以本文所提协议的平均接触时间是最高的。

![](images/5d5c6086277c5cd5f21cbe382e62064fff250ff40961bbade85348ea0e08e172.jpg)  
图6平均接触时间与速度的关系

# 3 结束语

本文提出了一种基于区域的无线传感器网络移动中继节点的路由协议。所提协议通过遵循更好的睡眠唤醒节点来支持拓扑控制，该静态节点的睡眠唤醒方法保证了整个网络的能量效率，没有增加时间同步开销。通过与RoF和GPSR协议的对比实验可以得出本文协议在分组传递率上性能更优，且参与节点数更少。目前的方法侧重于单个源与静态接收器进行通信的，未来工作将协议应用于将多个源与移动接收器的通信。

# 参考文献：

[1]许红艳，郭红．无线传感器网络节点故障诊断算法研究[J].西南师范 大学学报：自然科学版,2016,41(9):126-133.(Xu Hongyan,Guo Hong. On fault diagnosis algorithm in wireless sensor network nodes [J]. Journal ofSouthwest China Normal University:Natural Science Edition,2O16,41 (9): 126-133.)

[2]常捷，张灵．随机分布的无线传感器网络中移动 sink 的路径规划[J]. 计算机科学,2017,44(2): 147-151.(Chang Jie,Zhang Ling.Optimal path planning for mobile sink in random distributed wireless sensor networks [J].Computer Science,2017,44(2): 147-151.)   
[3]Al-Jemeli M,Hussin F A.An energy efficient cross-layer network operation model for IEEE 802．15.4-based mobile wireless sensor networks [J].IEEE Sensors Journal,2015,15 (2): 684-692.   
[4]Velmani R,Kaarthick B.An efficient cluster-tree based data collection scheme for large mobile wireless sensor networks [J].IEEE Sensors Journal,2015,15(4):2377-2390.   
[5]Boubekri A,Ajib W,Boukadoum M. EAM: Energy Aware Mobility over wireless sensor networks [C]//Proc of the 3Oth Canadian Conference on Electrical and Computer Engineering.[S.1.] : IEEE Press,2O17: 1-6.   
[6]Sreejith V, Suriyadeepan R,Anupama KR,et al.DS-MMAC:dynamic schedule based MAC for mobile wireless sensor network [C]//Proc of the 31st Annual ACM Symposium on Applied Computing.New York:ACM Press,2016: 738-741.   
[7]赵悦，孟博，陈雷，等．基于能量感知的无线传感器网络路由协议[J]. 计算机工程与设计,2016,37(1):16-20.(Zhao Yue,Meng Bo,Chen Lei, et al.Routing protocol in wireless sensor networks based on energy aware [J].computer Engineering and Design,2016,37(1):16-20.)   
[8]Luo J,Hu J,Wu D,et al. Opportunistic routing algorithm for relay node selection in wireless sensor networks [J].IEEE Trans on Industrial Informatics,2015,11(1):112-121.   
[9]Kumar A,Shwe HY,Wong KJ,et al.Location-Based RoutingProtocols for Wireless Sensor Networks:A Survey [J].Wireless Sensor Network, 2017,9(1): 25-72.   
[10]Pantazis N A,Nikolidakis SA,Vergados D D.Energy-efficient routing protocols in wireless sensor networks:A survey [J].IEEE Communications Surveys& Tutorials,2013,15(2):551-591.   
[11] Gaddour O,Koubaa A,Rangarajan R,et al.Co-RPL:RPL routing for mobile low power wireless sensor networks using Corona mechanism [C]// Proc of the 9th IEEE International Symposium on Industrial Embedded Systems.2014:200-209.   
[12]王凯彬，程良伦．一种无线传感器网络冗余节点状态调度方法[J].计 算机应用研究.2018,35(4):1227-1230.(Wang Kaibin,Cheng Lianglun. Wireless sensor network redundancy sensor node state schedule method [J]. Journal of Application Research of Computers,2018,35 (4):1227-1230.)