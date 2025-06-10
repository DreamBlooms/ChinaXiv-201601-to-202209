# 具有回程约束的多无人机基站的带宽功率与轨迹优化

黄颖茜，崔 苗，张广驰(广东工业大学 信息工程学院，广州 510006)

摘要：无人机支持灵活部署和高速率传输，有望成为新一代无线网络的重要组成部分。考虑一个多无人机组网的无线通信系统，多个无人机搭载的空中基站为覆盖区域内的多组用户提供服务。在网络中，由于频谱资源受限，基站的回程链路与用户的数据链路共享相同的频谱。为了合理利用频谱资源并提高用户的通信性能，以达到所有地面用户的最小平均速率最大化的目的，联合优化回程链路和数据链路的带宽、功率以及无人机基站的飞行轨迹。这种联合优化受限于无人机的移动性、频谱带宽以及传输功率。联合优化涉及的问题是非凸的并且难以得到最优解，因此提出一种高效算法获取高性能的次优解。仿真结果表明，所提出的联合优化算法实现的最小用户速率明显高于基准方案。

关键词：多无人机；回程节点；带宽；功率；轨迹；优化 中图分类号：TP919.72 doi: 10.19734/j.issn.1001-3695.2020.02.0059

# Bandwidth, power and trajectory optimization for multiple UAV base stations with backhaul constraint

Huang Yingqian, Cui Miao†, Zhang Guangchi (Guangdong University of Technology,School of Information Engineering,Guangzhou 510oo6,China)

Abstract: Unmanned aerial vehicles (UAVs)are envisioned to becomean important part of thenew generation wireles networks,due totheiradvantagesofflexibledeploymentand high-speed transmision.Awirelesscommunicationnetwork with multiple UAVbase stationsand multiple users hasbeenconsidered.Inthe network,duetothe limited spectrumresource, the backhaulinks of the UAV base stations andthe data linksof theusers share the same spectrum.Inorder to use the spectrumresource eficiently and improve the communication performance of the users,the bandwidth and power of the backhaulanddata links aswellas theflightrajectoryofthe UAVbase stations have beenjointlyoptimizedto maximize the minimumaveragerateofallusers.This jointoptimizationissubjecttothe UAVs'mobility,thetotalspectrumbandwidthand thetotaltransmit power.Theivolved jointoptimizationproblem isnon-convex,andthus itisdifficulttofinditsoptimal solution.Anefficient algorithm has been proposed toobtainahigh-qualitysuboptimal solutionof it.Simulationresults show thatthe minimum userrateachieved bythe proposed jointoptimizationalgorithm is significantlyhigher than thatof the benchmark schemes.

Key words:multi-uav; backhaul node; bandwidth; power; trajectory; optimization

# 0 引言

无人机经过数十年的飞速发展，由于其具有机动性能高，易于部署，价格低廉等优点已广泛应用于军事，交通，农业，物流等领域，给人们的生活带来了便捷。随着第五代(5G)无线通信的兴起，无人机在不同应用场景中辅助无线网络进行通信的作用，有助于提高5G网络的通信性能。因为与将通信节点固定在地面上的地面无线网络相比，无人机可以灵活地设计飞行轨迹，通过建立视距链路来提高与通信对方的通信质量，也可增加其通信覆盖范围[1\~3]。在无人机辅助的通信网络中，无人机可用作空中基站或中继站，尤其适用于交通拥堵或自然灾害等紧急情况[4.5]。经过多年研究，无人机辅助的通信仍然面临一些关键技术难题，其潜在优势未得到充分利用。例如，文献[6,7]考虑将无人机用作固定的无人机基站，文献[8]提出了一种节能无人机中继方案，文献[9,10]提出通过优化无人机的部署位置进行远距离通信节能策略，此外，无人机还可与地面的车辆进行协同通信，收集及掌握网络的全局信息或者作为中继转发信息，从而保证网络的连通性，改善信息传输性能[1]。然而，这些工作并未考虑无人机的高机动性能。实际上，在无人机通信网络中，根据网络动态共同优化通信资源和无人机轨迹可以极大提高无线通信性能，这是一个非常具有前景的研究方向。

受此启发，许多研究者开展了基于无人机通信网络的联合轨迹优化和资源分配方案的研究。文献[12]考虑了具有单个无人机的无线网络，联合优化了无人机的用户调度和轨迹，以达到最大化所有用户的最小吞吐量的效果。文献[13\~15]研究了在不同情况下无人机安全通信中的联合功率分配和轨迹优化，文献[4]和[5]研究了无人机中继系统中的联合资源分配和无人机轨迹优化。上述工作考虑了每个数据链路的固定带宽，可以根据信道和系统动态自适应地调整每个数据链路的带宽来进一步提高其性能。在文献[16]中，研究了联合优化无人机的部署位置，无人机的带宽和波束宽度；文献[17]已经研究了与设备到设备通信网络共存的无人机部署位置，无人机和基站的功率和带宽的联合优化；文献[18]已经研究了多跳无人机中继系统的联合带宽，功率和轨迹优化，其中端到端速率达到最大化。前面的工作主要集中在连接无人机和用户的接入链路的带宽上，而忽略了连接无人机和核心网络的回程链路[19]。实际上，当回程链路的带宽受到限制时，回程链路可能会限制无人机网络的整体性能，因此网络中的通信优化应考虑回程链路约束，在文献[20]中，由多跳无人机中继形成的无人机基站回程的速率最大化，文献[21]已经研究了具有回程约束的静态多无人机基站网络的部署和用户关联的联合优化。随着无人机任务的日趋多样化，单个无人机模式已不能满足其飞行任务的日常需要，因此还需要考虑多个无人机的无线通信网络。文献[22]考虑到了多无人机无线网络，它假设系统具有充足的回程链路带宽，优化无人机的用户调度、功率和轨迹来实现最大化所有用户的最小速率。文献[4]和[6]都是研究多无人机的多跳网络，前者只优化功率轨迹，且未考虑回程问题，后者虽然考虑了回程问题，但是无人机是静正不动的。据了解，既有回程约束又是多无人机通信同时优化带宽，功率和轨迹的问题尚未得到研究。

如图1所示，本文考虑一种提高具有回程约束的多无人机网络的通信性能，在该网络中，用户被分为多组，每个无人机分别服务一组用户。由于频谱稀缺，网络的回程与用户的数据链路共享相同的频谱。回程链路限制了所有用户的数据速率之和，即所有用户的数据速率总和不能超过回传速率。本文通过共同优化回程链路和数据链路的带宽、功率和无人机的轨迹，最大限度地提高所有用户的最低速率。尽管所提出的问题是非凸的并且难以求得最优解，但本文提出了一种高效的算法来找到次优解。仿真结果表明，所提算法的速率性能明显优于几种基准算法，说明了多无人机网络有必要进行联合带宽、功率和轨迹优化。

![](images/9cd88a9a5b1d76d88fcd9ff58a3cb661a63d0a1ab240a03a53b83d3d7cff1150.jpg)  
图1具有回程约束的多无人机无线网络  
Fig.1A multi-UAV wireless network with the backhaul constraint

# 1 系统模型

如图1所示，考虑一个多无人机基站辅助的无线通信网络系统，其中 $J { > } 1$ 的无人机为地面 $K > 1$ 个地面用户提供服务，用户和无人机集合分别表示为 $\Re$ 和 $\mathcal { I }$ ，其中（204号 ${ \mathfrak { R } } \triangleq \left\{ 1 , . . . , K \right\}$ ， ${ \mathcal { I } } \triangleq \{ 1 , \cdots , J \}$ ，不同的无人机服务不同的用户，如第 $j$ 个无人机服务的用户为 $K _ { j } , K _ { j } \in \Re$ ，而无人机与回程节点之间的链路则称为无线回程链路。本文主要研究无人机到地面用户的下行链路通信，并且该研究可以直接扩展到上行链路通信的场景。应用笛卡尔坐标系来表示位置关系，则回程链路节点及用户 $k , k \in \Re$ 的位置分别固定在 $\left[ \pmb { w } _ { \mathrm { B H } } ^ { T } , 0 \right] ^ { T }$ 及$\left[ \pmb { w } _ { k } ^ { T } , 0 \right] ^ { T }$ ，它们的水平位置分别为： $\pmb { w } _ { \mathrm { B H } } = \left[ x _ { 0 } , y _ { 0 } \right] ^ { T } \in \mathbb { R } ^ { 2 \times 1 }$ ，$\pmb { w } _ { k } = \left[ x _ { k } , \mathbf { y } _ { k } \right] ^ { T } \in \mathbb { R } ^ { 2 \times 1 }$ ，此处 $T$ 表示转置。假设无人机 $j$ 在高度为$H$ (以米为单位)的高空飞行，其坐标在 $t , 0 \leq t \leq T$ 时刻表示为 $\left[ \mathbf { s } _ { k } ^ { T } ( t ) , 0 \right] ^ { T }$ ，其中， $\pmb { s } _ { j } = \left[ x _ { j } ( t ) , y _ { j } ( t ) \right] ^ { T } \in \mathbb { R } ^ { 2 \times 1 }$ 为第 $j , j \in \mathcal { I }$ 个无人机在时隙 $\textit { t }$ 的水平位置， $T$ (以秒为单位)表示无人机的飞行周期。为了便于部署，要求无人机在飞行周期结束时返回其初始起飞位置，且无人机的轨迹也受到最大速度 $V _ { \mathrm { m a x } }$ 限制和避免碰撞的限制，所以，第 $j$ 个无人机的飞行轨迹有如下约束，

$$
s _ { j } \left( 0 \right) = s _ { j } \left( T \right) ,
$$

$$
\left\| \dot { s } _ { j } ( t ) \right\| \le { V } _ { \operatorname* { m a x } } , 0 \le t \le T ,
$$

$$
\begin{array} { r } { \left\| s _ { j } ( t ) - s _ { m } ( t ) \right\| \geq d _ { \operatorname* { m i n } } , 0 \leq t \leq T . } \end{array}
$$

由于无人机的轨迹在时间 $t$ 上是连续的，涉及无数个变量，想要完成优化是极其困难的，因此，为了促进轨迹的优化，本文通过将飞行时间 $T$ 划分成等长的 $N$ 个时隙，并把序列 $\{ \mathbf { s } _ { j , n } , 0 \leq n \leq N , \forall j \}$ 当做一个近似的轨迹，其中，$\boldsymbol { s } _ { j , n } = \left[ x _ { j , n } , y _ { j , n } \right] ^ { T }$ 为第 $j$ 个无人机在第 $n$ 个时隙的水平位置。当时隙数量 $N$ 足够大时，每个时隙的长度可以小到忽略不计，这样，无人机基站在每个时隙 ${ \varepsilon } _ { t } = T / N$ 可以认为是静态的。因此，第 $j$ 个无人机的移动性约束，即式(1)(2)和(3)变化如下，

$$
{ \bf { S } } _ { j , 0 } = { \bf { S } } _ { j , N } ,
$$

$$
\begin{array} { r } { \big \| \pmb { s } _ { j , n + 1 } - \pmb { s } _ { j , n } \big \| ^ { 2 } \leq L _ { \operatorname* { m i n } } ^ { 2 } , j \in J , n = 0 , . . . , N - 1 , } \end{array}
$$

$$
\begin{array} { r } { \left\| \pmb { \mathscr { s } } _ { j , n } - \pmb { \mathscr { s } } _ { m , n } \right\| ^ { 2 } \geq d _ { \frac { \operatorname* { m } } { \operatorname* { m i n } } } ^ { 2 } , \forall j , n , j \neq m , } \end{array}
$$

其中 $L _ { \operatorname* { m a x } } \triangleq V _ { \operatorname* { m a x } } \varepsilon _ { t }$ 是无人机在每个时隙内可以飞行的最大距离。因此，第 $j$ 个无人机在第 $n$ 时隙到用户 $k$ 及基站之间的距离分别为，

$$
d _ { j , n , k } = \sqrt { H ^ { 2 } + \left\| s _ { j , n } - w _ { k } \right\| ^ { 2 } } , k \in K _ { j } , \forall j , n ,
$$

$$
d _ { j , n , \mathrm { B H } } = \sqrt { H ^ { 2 } + \left\| \boldsymbol { s } _ { j , n } - \boldsymbol { w } _ { \mathrm { B H } } \right\| ^ { 2 } } , \forall j , n ,
$$

测试结果表明，无人机和地面节点之间的通信由视距链路控制[231，本文应用自由空间的传播模型来近似估算无人机与所有地面用户之间以及无人机与回程链路节点之间的信道。因此，在第 $n$ 个时隙处，第 $j$ 个无人机和第 $k$ 个用户之间的信道功率增益可以写为

$$
\varphi _ { j , n , k } = \frac { \beta _ { 0 } } { d _ { j , n , k } ^ { 2 } } = \frac { \beta _ { 0 } } { H ^ { 2 } + \left\| \mathbf { s } _ { j , n } - \mathbf { w } _ { k } \right\| ^ { 2 } } , k \in K _ { j } , \forall j , n ,
$$

其中， $\beta _ { 0 }$ 表示当参考距离 $d _ { 0 } = 1 { \mathrm { m } }$ 时无线信道的信道功率增益。同理，在第 $n$ 个时隙处，第 $j$ 个无人机和回程链路节点之间的信道功率增益为，

$$
\varphi _ { j , n , \mathrm { B H } } = \frac { \beta _ { 0 } } { d _ { j , n , \mathrm { B H } } ^ { 2 } } = \frac { \beta _ { 0 } } { H ^ { 2 } + \left\| \mathbf { s } _ { j , n } - \boldsymbol { w } _ { \mathrm { B H } } \right\| ^ { 2 } } , \forall j , n ,
$$

假设由于频谱稀缺，在考虑的无人机基站网络中没有用于回程链路的专用频谱。因此，带内回程方案被应用在网络中，该方案使用户的回程链路和数据链路共享相同的频谱，带宽为赫兹 $\left( \mathrm { H z } \right)$ 。为了避免干扰，不同的链路分配有正交频谱。用 $x _ { j , n , 0 }$ 和 $x _ { j , n , k }$ 分别表示第 $j$ 个无人机及第 $k$ 个用户在第 $\mathfrak { n }$ 个时隙的回程链路和数据链路的带宽分配部分，它们应该满足以下带宽约束，

$$
\sum _ { k = 0 } ^ { K _ { j } } \boldsymbol { x } _ { j , n , k } \le 1 , \forall j , n ,
$$

$$
0 \leq x _ { j , n , k } \leq 1 , k \in \{ 0 \} \cup K _ { j } , \forall j , n .
$$

假设在第 $n$ 个时隙，回程链路节点向第 $j$ 个无人机发射功率为 $p _ { j , n , 0 }$ ，并且第 $j$ 个无人机以功率 $p _ { j , n , k }$ 向地面第 $k$ 个用户发送信号，并且 $p _ { j , n , 0 }$ 及 $p _ { j , n , k }$ 受到如下总功率约束和非负约束，

$$
\sum _ { k = 0 } ^ { K _ { j } } p _ { j , n , k } \leq P _ { \operatorname* { m a x } } , \forall j , n ,
$$

$$
p _ { j , n , k } \geq 0 , k \in \{ 0 \} \cup K _ { j } , \forall j , n .
$$

其中， $P _ { \mathrm { m a x } }$ 表示回程链路节点和无人机的最大总功率。因此，用户 $k$ 在时隙 $n$ 处可实现的数据速率(比特/秒/赫兹)可以表示为

$$
R _ { j , n , k } = x _ { j , n , k } \log _ { 2 } ( 1 + \frac { p _ { j , n , k } \varphi _ { j , n , k } } { x _ { j , n , k } B N _ { 0 } } ) = x _ { j , n , k } \log _ { 2 } ( 1 + \frac { p _ { j , n , k } \zeta _ { 0 } } { x _ { j , n , k } \lambda _ { j , n , k } } )
$$

其中， $ { \mathcal { N } } _ { 0 }$ 表示接收器处加性高斯白噪声的功率谱密度，

$\zeta _ { 0 } = \beta _ { 0 } / ( B N _ { 0 } )$ ， $\lambda _ { j , n , k } = H ^ { 2 } + \left\| \mathbf { s } _ { j , n } - \pmb { w } _ { k } \right\| ^ { 2 }$ 。假设回程链路节点以恒定功率向第 $j$ 个无人机发射信号，并在第 $n$ 个时隙表示回程链路可实现的数据速率为

$$
R _ { j , n , \mathrm { B H } } = x _ { j , n , 0 } \log _ { 2 } ( 1 + \frac { p _ { j , n , 0 } \varphi _ { j , n , \mathrm { B H } } } { x _ { j , n , 0 } B N _ { 0 } } ) = x _ { j , n , 0 } \log _ { 2 } ( 1 + \frac { p _ { j , n , 0 } \zeta _ { 0 } } { x _ { j , n , 0 } \lambda _ { j , n , \mathrm { B H } } } )
$$

其中， $\lambda _ { j , n , \mathrm { B H } } = H ^ { 2 } + \left\| { \pmb { s } } _ { j , n } - { \pmb { w } } _ { \mathrm { B H } } \right\| ^ { 2 }$ 。由于无人机基站只能将通过核心网接收的数据(经过回程链路节点)传输给用户，因此所有用户的总速率应不大于任何时隙的回程链路速率，这称为回程速率约束，

$$
R _ { j , n , \mathrm { B H } } \geq \sum _ { k = 1 } ^ { K _ { j } } R _ { j , n , k } , \forall j , n .
$$

# 2 带宽、功率与飞行轨迹的联合优化

# 2.1 优化问题

为了提高用户的数据速率并保证用户间的公平性，本文的目标是最大化所有用户的最小平均速率，即 $\displaystyle \operatorname* { m i n } _ { k \in \Re } \frac { 1 } { N } \sum _ { n = 1 } ^ { N } R _ { j , n , k }$ 通过共同优化回程链路和所有数据链路的带宽$\mathbf { X } \triangleq \left\{ x _ { j , n , k } , k \in \{ 0 \} \cup K _ { j } , \forall j , n \right\}$ 和功率 $\mathbf { P } \triangleq \{ p _ { j , n , k } , k \in \{ 0 \} \cup K _ { j } , \forall j , n \}$ ，以及无人机的飞行的轨迹 $\mathbf { S } \triangleq \{ \mathbf { s } _ { j , n } , \forall j , n \}$ ，受限于式(4)(5)和(6)无人机的移动性约束，式(11)(12)中的带宽约束，式(13)(14)中的发射功率约束，式(17)中的回程速率约束，通过引入一个松弛变量 $\varsigma$ 来表示所有用户允许的最小平均速率，将该问题表示为

$$
\operatorname* { m a x } _ { \zeta , \mathbf { X } , \mathbf { P } , \mathbf { S } } { \zeta }
$$

$$
s . t . \frac { 1 } { N } \sum _ { n = 1 } ^ { N } R _ { j , n , k } \geq \varsigma , k \in K _ { j } , \forall j ,
$$

由于存在变量 $\mathbf { X }$ ， $\mathbf { P }$ 和 $\mathbf { s }$ ，不等式(17)的左侧和右侧都是非凹约束，所以，问题(P1)是非凸问题，难以得到最优解。为此，本文提出了一种算法来优化该算法，如下所示。

# 2.2联合优化算法

在本节中，基于交替优化方法，提出了一种解决问题(P1)的有效算法。首先，所提出的算法将所有优化变量划分为两个模块，其中第一个模块包括带宽部分变量 $\mathbf { X }$ 和发射功率变量P，第二个模块包括无人机轨迹变量S。接下来，通过这种变量划分，问题(P1)可以分为两个子问题，分别表示为子问题1和子问题2。前一个子问题在固定变量 $\mathbf { X }$ 和 $\mathbf { P }$ 下优化变量S，而后一个子问题在固定变量S下优化变量 $\mathbf { X }$ 和 $\mathbf { P }$ 。拟议的算法解决了子问题1和2交替迭代，直到问题的目标值(P1)收敛为止。在下文中，将分别提出解决子问题1和2的方法。而后，将给出总体算法。

# 2.2.1固定无人机轨迹，优化带宽和发射功率

首先处理子问题1，该子问题优化了具有固定轨迹的无人机网络的带宽和发射功率分配。问题可以表述为

$$
\operatorname* { m a x } _ { \zeta , \mathbf { X } , \mathbf { P } } \varsigma
$$

$$
s . t . \frac { 1 } { N } { \sum _ { n = 1 } ^ { N } } x _ { j , n , k } \log _ { 2 } ( 1 + \frac { p _ { j , n , k } f _ { j , n , k } } { x _ { j , n , k } } ) \ge \varsigma . k \in \cal K _ { j } , \forall j ,
$$

$$
x _ { j , n , 0 } \log _ { 2 } ( 1 + \frac { p _ { j , n , 0 } f _ { j , n , \mathrm { B H } } } { x _ { j , n , 0 } } ) \geq \sum _ { k = 1 } ^ { K _ { j } } x _ { j , n , k } \log _ { 2 } ( 1 + \frac { p _ { j , n , k } f _ { j , n , k } } { x _ { j , n , k } } ) , \forall j , n
$$

其中， $f _ { j , n , k } = \zeta _ { 0 } \big / \lambda _ { j , n , k }$ ， $f _ { j , n , \mathrm { B H } } = \zeta _ { 0 } / \lambda _ { j , n , \mathrm { B H } }$ 。在问题(P2)中，由于约束式(23)的右侧相对于变量 $x _ { j , n , k }$ 和 $p _ { j , n , k }$ 是凹的，因此问题(P2)是非凸的，无法通过标准的优化技术来解决。为了解决问题(P2)，将引入松弛变量 $\mathbf { a } \triangleq \{ a _ { j , n , k } , \forall j , n , k \}$ ，并提出以下问题。

$$
s . t . \frac { 1 } { N } \sum _ { n = 1 } ^ { N } a _ { j , n , k } \geq \varsigma , k \in K _ { j } , \forall j ,
$$

$$
x _ { j , n , 0 } \log _ { 2 } ( 1 + \frac { p _ { j , n , 0 } f _ { j , n , \mathrm { B H } } } { x _ { j , n , 0 } } ) \geq \sum _ { k = 1 } ^ { K _ { j } } a _ { j , n , k } , \forall j , n
$$

$$
a _ { j , n , k } \leq x _ { j , n , k } \log _ { 2 } ( 1 + \frac { p _ { j , n , k } f _ { j , n , k } } { x _ { j , n , k } } ) , \forall j , n , k
$$

证明问题(P3)和问题(P2)在 $\mathbf { X }$ 和 $\mathbf { P }$ 具有相同的最优解，因为存在使约束式(28)中的等式成立的最优解。

证明假设存在 $x _ { m , i , l }$ 和 $p _ { m , i , l }$ 是(P3)有最优解，其中，$m \in \mathcal { I }$ ， $i \in N$ ， $l \in \Re$ ，使得约束式(28)满足严格的不等式，可以找到 $\tilde { x } _ { m , i , l }$ 和 $\tilde { p } _ { m , i , l }$ ， $\tilde { x } _ { m , i , l } \leq x _ { m , i , l }$ ， $\tilde { p } _ { m , i , l } \leq p _ { m , i , l }$ 使约束式(28)的等式恒成立，由于 $\tilde { x } _ { m , i , l }$ 和 $\tilde { p } _ { m , i , l }$ 不会降低问题(P3)的目标值，因此它们也是解决问题(P3)的最佳方法。此外，当等式在约束式(28)中成立时，问题(P3)和(P2)的 $\mathbf { X }$ 和 $\mathbf { P }$ 的可行区域相同，因此它们在 $\mathbf { X }$ 和 $\mathbf { P }$ 上具有相同的最优解。因此，可以通过 $\mathbf { X }$ 和 $\mathbf { P }$ 的值来解决问题(P3)，也就解决了问题(P2)。由于问题(P3)的目标函数，约束式(26)(29)是线性约束，并且约束式(27)的左端和约束式(28)的右端相对于 $\mathbf { X }$ 和 $\mathbf { P }$ 是凹的，所以问题(P3)是凸优化问题，通过使用内点法来解决[24]。

# 2.2.2固定带宽和发射功率，优化无人机轨迹

本节将处理子问题2，该子问题通过固定的带宽和发射功率分配来优化无人机的轨迹。问题可以表述为，

$$
s . t . \frac { 1 } { N } \sum _ { n = 1 } ^ { N } x _ { j , n , k } \log _ { 2 } ( 1 + \frac { g _ { j , n , k } } { H ^ { 2 } + \left\| { \pmb s } _ { j , n } - { \pmb w } _ { k } \right\| ^ { 2 } } ) \geq \varsigma . k \in K _ { j } , \forall j ,
$$

$$
\begin{array} { r l } { \displaystyle x _ { j , n , 0 } \log _ { 2 } ( 1 + \frac { g _ { j , n , 0 } } { H ^ { 2 } + \left\| s _ { j , n } - w _ { \mathrm { B H } } \right\| ^ { 2 } } ) \geq } & { } \\ { \displaystyle \sum _ { k = 1 } ^ { K _ { j } } x _ { j , n , k } \log _ { 2 } ( 1 + \frac { g _ { j , n , k } } { H ^ { 2 } + \left\| s _ { j , n } - w _ { k } \right\| ^ { 2 } } ) , \forall j , n } & { } \end{array}
$$

其中， $g _ { j , n , k } = p _ { j , n , k } \zeta _ { 0 } \big / x _ { j , n , k }$ ， $g _ { j , n , 0 } = p _ { j , n , 0 } \zeta _ { 0 } \big / x _ { j , n , 0 }$ 。在(P4)中，约束式(32)分别来自式(17)，注意到式(31)和(32)是非凸约束，所以(P4)问题是非凸问题，难以得到最优解，提出了一种次优的方法，方法如下，

首先，将松弛变量 $\boldsymbol { \mathsf { b } } \triangleq \{ b _ { j , n , k } , \forall j , n , k \}$ 引入问题(P4)，并提出以下问题：

$$
\operatorname* { m a x } _ { \zeta , \mathbf { S } , \mathbf { b } } \varsigma
$$

$$
\begin{array} { r } { s . t . \frac { 1 } { N } \sum _ { n = 1 } ^ { N } b _ { j , n , k } \geq \varsigma , k \in K _ { j } , \forall j , } \end{array}
$$

$$
x _ { j , n , 0 } \log _ { 2 } ( 1 + \frac { g _ { j , n , 0 } } { H ^ { 2 } + \left\| { \boldsymbol { s } } _ { j , n } - { \boldsymbol { w } } _ { \mathrm { B H } } \right\| ^ { 2 } } ) \geq \sum _ { k = 1 } ^ { K _ { j } } b _ { j , n , k } , \forall j , n ,
$$

$$
b _ { j , n , k } \leq x _ { j , n , k } \log _ { 2 } ( 1 + \frac { g _ { j , n , k } } { H ^ { 2 } + \left\| { { \bf s } _ { j , n } } - { { \bf w } _ { k } } \right\| ^ { 2 } } ) , \forall j , n , k
$$

与问题(P3)和问题(P2)在 $\mathbf { X }$ 和 $\mathbf { P }$ 上具有相同的最优解相似，可以证明存在问题(P5)的最优解，使得约束式(37)满足不等式相等，因此 问题(P5)和问题(P4)在S上具有相同的解决方案。所以，可以通过解决问题(P5)来获得S的解决方案。但是，问题(P5)仍然难以解决，因为式(36)的左侧和式(38)的右侧相对于 $s _ { j , n }$ 是非凹的。

接下来，通过迭代的连续凸优化技术来近似解决问题(P5)。具体而言，在每次迭代过程中，逐次凸优化技术采用一个初始点，并通过使用初始点在问题(P5)的凸可行域内最大化问题(P5)的目标函数来获得问题(P5)的近似解。当前迭代中获得的近似解将用作下一次迭代中的初始值，当问题(P5)的目标值收敛时，迭代过程停止。

详细过程如下，假设 $\mathbf { S } ^ { ( r ) } \triangleq \left\{ s _ { j , n } ^ { ( r ) } , \forall j , n \right\}$ 是在第 $\boldsymbol { r }$ 次迭代获得第 $j$ 个无人机轨迹的解， $r \geq 0$ 。在第 $r + 1$ 次迭代中，将$S ^ { ( r ) }$ 作为初始点，并找到以下近似解。值得注意的是，尽管式(36)的左侧和式(37)的右侧相对于 ${ \pmb s } _ { j , n }$ 是非凹的，但它们分别相对于 ${ \left\| { { s _ { j , n } } - { w _ { \mathrm { { B H } } } } } \right\| ^ { 2 } }$ 和 $\left\| s _ { j , n } - w _ { k } \right\| ^ { 2 }$ 是凸的。因此，把$\left\| \boldsymbol { s } _ { j , n } ^ { ( r ) } - \boldsymbol { w } _ { \mathrm { B H } } \right\| ^ { 2 }$ 的一阶泰勒展开式作为式(36)的左侧的下界 $R _ { j , n , \mathrm { B H } } ^ { l b , ( r ) }$ ，同理，式(37)右侧的下界 $R _ { j , n , k } ^ { l b , ( r ) }$ 表示 $\left\| \pmb { S } _ { j , n } ^ { ( r ) } - \pmb { w } _ { k } \right\| ^ { 2 }$ 的一阶泰勒展开式，如下所示，

$$
\begin{array} { c } { { x _ { j , n , 0 } \log _ { 2 } ( 1 + \frac { g _ { j , n , 0 } } { H ^ { 2 } + \left\| { \pmb S } _ { j , n } - { \pmb w } _ { \mathrm { B H } } \right\| ^ { 2 } } ) \geq } } \\ { { - \eta _ { j , n , \mathrm { B H } } ^ { ( r ) } ( \left\| { \pmb s } _ { j , n } - { \pmb w } _ { \mathrm { B H } } \right\| ^ { 2 } - \left\| { \pmb s } _ { j , n } ^ { ( r ) } - { \pmb w } _ { \mathrm { B H } } \right\| ^ { 2 } ) + \phi _ { j , n , \mathrm { B H } } ^ { ( r ) } \triangleq R _ { j , n , \mathrm { B H } } ^ { l b , ( r ) } } } \end{array}
$$

$$
x _ { j , n , k } \log _ { 2 } ( 1 + \frac { g _ { j , n , k } } { H ^ { 2 } + \left\| s _ { j , n } - w _ { k } \right\| ^ { 2 } } ) \geq
$$

$$
- \eta _ { j , n , k } ^ { ( r ) } ( \| \pmb { s } _ { j , n } - \pmb { w } _ { k } \| ^ { 2 } - \| \pmb { s } _ { j , n } ^ { ( r ) } - \pmb { w } _ { k } \| ^ { 2 } ) + \phi _ { j , n , k } ^ { ( r ) } \triangleq R _ { j , n , k } ^ { l b , ( r ) }
$$

其中,

$$
\lambda _ { j , n , \mathrm { B H } } ^ { ( r ) } = H ^ { 2 } + \left\| \pmb { S } _ { j , n } ^ { ( r ) } - \pmb { w } _ { \mathrm { B H } } \right\| ^ { 2 } ,
$$

$$
\lambda _ { j , n , k } ^ { ( r ) } = H ^ { 2 } + \left\| \pmb { S } _ { j , n } ^ { ( r ) } - \pmb { w } _ { k } \right\| ^ { 2 } ,
$$

$$
\eta _ { j , n , \mathrm { B H } } ^ { ( r ) } = \frac { x _ { j , n , 0 } g _ { j , n , 0 } \log _ { 2 } ( e ) } { \lambda _ { j , n , \mathrm { B H } } ^ { ( r ) } ( \lambda _ { j , n , \mathrm { B H } } ^ { ( r ) } + g _ { j , n , 0 } ) }
$$

$$
\eta _ { j , n , k } ^ { ( r ) } = \frac { x _ { j , n , k } g _ { j , n , k } \log _ { 2 } ( e ) } { \lambda _ { j , n , k } ^ { ( r ) } ( \lambda _ { j , n , k } ^ { ( r ) } + g _ { j , n , k } ) }
$$

$$
\phi _ { j , n , \mathrm { B H } } ^ { ( r ) } = x _ { j , n , 0 } \log _ { 2 } ( 1 + \frac { g _ { j , n , 0 } } { \lambda _ { j , n , \mathrm { B H } } ^ { ( r ) } } )
$$

$$
\phi _ { j , n , k } ^ { ( r ) } = x _ { j , n , k } \log _ { 2 } ( 1 + \frac { g _ { j , n , k } } { \lambda _ { j , n , k } ^ { ( r ) } } )
$$

通过分别用 $R _ { j , n , \mathrm { B H } } ^ { l b , ( r ) }$ （204 和 $R _ { j , n , k } ^ { l b , ( r ) }$ （ 代替式(36)的左侧和式(37)的右侧，得出问题(P5)的近似问题如下，

$$
\operatorname* { m a x } _ { \zeta , \mathrm { S , b } } \varsigma
$$

$$
s . t . \frac { 1 } { N } \sum _ { n = 1 } ^ { N } b _ { j , n , k } \geq \varsigma , k \in K _ { j } , \forall j ,
$$

$$
R _ { j , n , \mathrm { B H } } ^ { l b , ( r ) } \geq \sum _ { k = 1 } ^ { K _ { j } } b _ { j , n , k } , \forall j , n ,
$$

$$
b _ { j , n , k } \leq R _ { j , n , k } ^ { l b , ( r ) } , \forall j , n , k ,
$$

由于约束式(42)的左侧和约束式(43)的右侧相对于变量$s _ { j , n }$ 是凹的，而其他约束是线性的，因此问题(P6)的可行区域为凸集，此外，问题(P6)的目标函数是线性的，因此问题(P6)是凸优化问题，并采用内点法获得最优解[23]。

由于 $b _ { j , n , k } \leq R _ { j , n , k } ^ { l b , ( r ) } , \forall j , n , k$ ，和 $R _ { j , n , k } ^ { l b , ( r ) }$ 是式(36)的左侧和式(37)的右侧的下界，因此约束式(42)和(43)分别代表约束式(36)和(37)，因此，通过解决问题(P6)获得的最优解是问题(P5)的可行解，此外，由于在第( $\cdot \mathbf { \sigma } _ { r + 1 }$ ）次迭代中，得出的解 $\boldsymbol { S } ^ { ( r + 1 ) }$ 是问题(P6)的最优解，且初始点 $S ^ { ( r ) }$ 在可行范围内，因此，问题(P6)的目标值 $S ^ { ( r + 1 ) }$ 不小于问题(P5)的目标值 $S ^ { ( r ) }$ 。所以，可得出结论，问题 (P5)的目标值在迭代过程中不会减小。

# 2.2.3总体算法

算法1为总结提出的算法,其中 $f ( \mathbf { X } , \mathbf { P } , \mathbf { S } )$ 表示问题(P1)的目标值有解，为 $\mathbf { X }$ ， $\mathbf { P }$ 和S， $\eta > 0$ 及 $\tau > 0$ 表示收敛精度的阈值。首先，如前一个小节分析，通过执行算法1的步驟$\mathbf { c } ) { \sim } \mathbf { h } )$ 获得有解的问题(P1)的目标值在迭代过程中不会减少；其次，由于目标值上届是有限的，因此可以保证算法1收敛；最后，算法1的计算复杂度为 ${ \mathcal O } [ N _ { \mathrm { i t e } } N ^ { 3 . 5 } ]$ ，其中 $N _ { \mathrm { i t e } }$ 表示其迭代次数。

算法1功率、带宽与飞行轨迹的联合优化算法a)初始化：设置初始带宽，功率和轨迹分别为 $\mathbf { X } ^ { ( 0 ) }$ ， $\mathbf { P } ^ { ( 0 ) }$ 和 $\mathbf { S } ^ { ( 0 ) }$ ，$\varsigma ^ { ( 0 ) } = f ( \mathbf { X } ^ { ( 0 ) } , \mathbf { P } ^ { ( 0 ) } , \mathbf { S } ^ { ( 0 ) } )$ ，令 $l = 0$ ：

b) $\scriptstyle { l = l + 1 }$ ：

c)给定无人机轨迹 $\mathbf { S } ^ { ( l - 1 ) }$ ，通过问题(P3)解得带宽 $\mathbf { X } ^ { ( l ) }$ 和功率 $\mathbf { P } ^ { ( l ) }$ 。

d)给定固定的带宽 $\mathbf { X } ^ { ( l ) }$ 和发射功率 $\mathbf { P } ^ { ( l ) }$ ，在以下迭代过程中获得轨迹值 $\mathbf { S } ^ { ( l ) }$ ： $\mathbf { S } ^ { ( 0 ) } = \mathbf { S } ^ { ( l - 1 ) }$ ， $r = 0$ ，则 $\xi ^ { ( 0 ) } = f ( \mathbf { X } ^ { ( l ) } , \mathbf { P } ^ { ( l ) } , \mathbf { S } ^ { ( 0 ) } )$ ：  
e) $r = r + 1$ .  
$\mathsf { f } )$ 将 $\mathbf { S } ^ { ( r - 1 ) }$ 作为初始值，解决问题(P6)，并得到最优解 $\mathbf { S } ^ { ( r ) }$ ;g)计算 $\xi ^ { ( 0 ) } = f ( \mathbf { X } ^ { ( l ) } , \mathbf { P } ^ { ( l ) } , \mathbf { S } ^ { ( r ) } )$ ：  
h)如果 $\frac { \big | \xi ^ { ( r ) } - \xi ^ { ( r - 1 ) } \big | } { \big | \xi ^ { ( r - 1 ) } \big | } < \eta$ ，则令 $\mathbf { S } ^ { ( l ) } = \mathbf { S } ^ { ( r ) }$ ，否则重复步驟e)\~h)；i)计算 $\varsigma ^ { ( l ) } = f ( \mathbf { X } ^ { ( l ) } , \mathbf { P } ^ { ( l ) } , \mathbf { S } ^ { ( l ) } )$ ：  
j)如果 $\frac { \left| \varsigma ^ { ( l ) } - \varsigma ^ { ( l - 1 ) } \right| } { \left| \varsigma ^ { ( l - 1 ) } \right| } < \tau$ ，跳出循环；否则重复步驟 ${ \mathfrak { b } } ) { \sim } { \dot { \mathsf { J } } }$ ）。

算法框图如图2所示。

![](images/72cc77ae7640855fc553ab91bc3467d2f07afa3d2046310ba048f95fc5d3e3a0.jpg)  
图2算法过程框图  
Fig.2Diagram of the proposed algorithm

# 3 仿真结果

本章将提供计算机仿真结果，验证与以下基准方案相比，本文提出的联合带宽、功率和轨迹优化算法的性能。

a)具有固定带宽和功率分配的轨迹优化：通过设置$x _ { j , n , 0 } = 1 / ( 2 J )$ ， $x _ { j , n , k } = x _ { j , n , 0 } / ( 2 \bf K )$ 和 $p _ { j , n , 0 } = p _ { \operatorname* { m a x } } / J$ ， $p _ { j , n , k } = p _ { \operatorname* { m a x } } / K$ 来固定不同数据链路的带宽和分配给不同无人机及用户的功率，并使用算法1的步骤4-8来优化无人机轨迹。

b)具有固定带宽方案的功率和轨迹优化：通过设置$x _ { j , n , 0 } = 1 / ( 2 J )$ 和 $x _ { j , n , k } = x _ { j , n , 0 } / ( 2 \bf { K } )$ 来固定不同数据链路的带宽，并使用类似于算法1的交替优化算法来优化发射功率和无人机的轨迹。

c)给定圆形轨迹联合优化带宽和功率[22]：用以下方法设置初始轨迹，并根据2.2.1节内容联合优化带宽功率。

在以上方案中，使用以下方法生成圆形轨迹来作为无人机的初始轨迹。轨迹的圆心和半径分别由 $c _ { t , j } = \left[ x _ { t , j } , \mathbf { y } _ { t , j } \right] ^ { T }$ 和 $r _ { t , j }$ 表示，其中无人机的速度取恒定值 $\boldsymbol { V }$ ， $0 < V \leq V _ { \operatorname* { m a x } }$ 。对于给定的任意时间 $T$ ，都有 $2 \pi r _ { t , j } = V T$ 。为了更好地平衡用户的速率.首先将第 $j$ 个无人机所服务的用户的几何中心确定为（204号 $c _ { g , j } = \sum _ { k = 1 } ^ { K _ { j } } { w _ { k } / K _ { j } }$ ，把 $c _ { g , j }$ 作为第 $j$ 个无人机所能覆盖的用户的最小圆圆心，半径用 $r _ { f , j }$ 表示，它等于 $c _ { g , j }$ 与第 $j$ 个无人机所服务的用户之间的最大距离，即 $r _ { f , j } = \operatorname* { m a x } _ { k \in K _ { j } } \left\| w _ { k } - c _ { g , j } \right\|$ 。但是由于受到无人机最大速度限制，则 $2 \pi r _ { f , j } \leq V _ { \mathrm { m a x } } T$ ，所以满足条件的最大半径应为

$$
r _ { \mathrm { m a x } } = \frac { V _ { \mathrm { m a x } } T } { 2 \pi }
$$

综上，初始圆形轨迹的半径为 $r _ { t , j } = \operatorname* { m i n } ( r _ { \operatorname* { m a x } } , r _ { f , j } )$ ，令$\alpha _ { n } \triangleq 2 \pi { \frac { ( n - 1 ) } { N - 1 } } , \forall n \ , \quad \mathbf { S } _ { j , n , 0 } = \left\{ \mathbf { s } _ { j , n , 0 } , \forall j , n \right\}$ 。根据圆心 $c _ { t , j }$ 和半径 $r _ { t , j }$ ，在第 $n$ 个时隙，第 $j$ 个无人机的初始轨迹为

$$
\begin{array} { r l } & { \mathbf { s } _ { j , n , 0 } = \left[ x _ { t , j } + r _ { t , j } \cos \alpha _ { n } , y _ { t , j } + r _ { t , j } \sin \alpha _ { n } \right] ^ { T } , } \\ & { n = 1 , . . . , N . } \end{array}
$$

对于多无人机 $j \geq 2$ ，无人机之间的距离大于或等于 $d _ { \operatorname* { m i n } }$ ，则式(47)中获得的轨迹对于原始问题 (P1)是可行的，可通过放缩 $r _ { f , j }$ 的大小来获得可行得初始轨迹。

在仿真中，设置地面用户随机位于大小为 $2 \times 2 { \bf { k m } } ^ { 2 }$ 的区域中，有 $K = 6$ 个用户，无人机有 $J { = } 2$ 个，其中用户1\~3由无人机1服务，用户4\~6由无人机2服务，为了比较不同方案的差异，以下结果是根据用户的位置随机获得的。两个无人机的飞行高度和最大速度均分别表示为 $H = 1 0 0 \mathrm { m }$ 和$V _ { \mathrm { m a x } } = 5 0 \mathrm { m / s }$ ，网络频谱的总带宽设置为 $B { = } 1 0  { \mathrm { M H z } }$ ，无人机和回程链路节点的最大总发射功率 $P _ { \mathrm { m a x } } = 2 \mathrm { W }$ 和 $P _ { \mathrm { b , m a x } } = 2 \mathrm { W }$ ，其他参数设置为 $d _ { \mathrm { m i n } } = 5 0 \mathrm { m }$ ， $\beta _ { 0 } = - 6 0 \Im \mathrm { B }$ ， $N _ { \mathrm { 0 } } = - 1 6 9 \mathrm { \mathcal { U } B m / H z }$ ，$\scriptstyle \tau = 1 0 ^ { - 4 }$ ， $\eta = 1 0 ^ { - 4 }$ 。

图3显示了当无人机基站的时间 $T = 1 2 0 \mathrm { s }$ 时方案(a)和方案(c)的轨迹图，其中‘☆’表示无人机1服务的用户，‘O’表示无人机2服务户，‘十’代表回程节点。可以看出，当回程节点以最大功率分别发送给两个无人机时，每个无人机都尽量沿着所服务的用户飞行，但因为受到回程链路的限制，两个无人机无法完全达到用户的顶端。其中，无人机1从用户3附近出发，以用户3，1，2，3的顺序飞行，更靠近用户1、3，距离用户2较远，用户2的速率相对小很多。无人机2在3个用户之间是呈直线飞行的，但距离用户4、5较远，两个无人机的轨迹与初始圆轨迹相比，服务的范围更小。图4为本文提出的方案和方案(c)的轨迹图，可以看出当带宽和功率也得到优化时，在相同的时间内，无人机飞行轨迹的范围明显扩大，可飞行至用户顶端或者近用户端提高用户速率，例如，无人机1经过用户3的顶端，并在1，3用户之间停留一段时间，飞行轨迹与图3相比距离用户2更近；无人机2从起始点以用户5，6，4，5的顺序以近似的直线飞行，虽然不能达到用户端(回程链路限制)，但是转折点与图3相比距离用户4和5更近。两个无人机的轨迹相较方案(c)的圆形轨迹，与回程节点呈直线连接的用户是以直线轨迹飞行的，所以耗时更短，服务用户的目的更直接，因而速率会更大。由此，整个系统达到了最大化所有用户速率的效果。

![](images/5bee5596b2cb801bd48feeb2e1ea415a48777e20df74cc315ab9cd4e4cc31f46.jpg)  
图3具有固定带宽和功率分配的轨迹优化与给定圆形轨迹联合优化带宽和功率轨迹图

图5和6是由提出的算法中回程链路节点分配给两个无人机对应的发射功率以及带宽部分与时间的关系，其参数与图4的参数相同。可以看出，图5中，基站到两个无人机的发射功率可以达到最大值或者为0，基站要给其中一个无人机提供当其中分配到其中一个无人机的功率为最大值时，另外一个无人机的功率则为0，且最大或最小取值会延长一段时间，因为在这段时隙中其中一个无人机与基站的信道条件最好，所以分配更多的功率给它，但是在每个时隙，分配的发射功率总和等于最大功率，而图6中，带宽的占比可能为0，但却不能达到最大值1，这是因为无人机1和2之间带宽采用正交频分的方式，从而避免无人机之间的干扰。

![](images/305fd2a2a09c0dd20a069e8aa83032b66a2b468009f93629ff4b48e530c6d0fc.jpg)  
图4联合优化与给定圆形轨迹联合优化带宽和功率轨迹图 Fig.4Trajectories obtained by the proposed joint optimization scheme and the bandwidth and power optimization with a given circular trajectory scheme

![](images/f66af37416c599a4b974247ab24b508ca1c601bda72694529e7b6deda62f1b12.jpg)  
图5基站到无人机的传输功率随时间变化图像

![](images/04df3b18f4560818692a2c3750e4fa458309c7a4736da893ca48c13b297f87ba.jpg)  
Fig.3Trajectories obtained by the trajectory optimization with fixed bandwidth and power allocation scheme and the bandwidth and power optimization with a given circular trajectory scheme   
Fig.5Transmit power versus time of base station to the uavs   
图6基站到无人机的带宽占比随时间变化图像  
Fig.6Bandwidth portion versus time of base station to the uavs

图7为通过不同方案获得的所有用户的最小速率与无人机飞行时间的关系。可以看出，所有方案的最小用户速率都是随着时间的增大而增大的；此外还可看出，所提的算法的速率明显高于其他三种方案的最小用户速率，这是因为在(a)(b)和(c)方案中，(a)和(b)方案的两个无人机为各自服务的用户分配相同的带宽，而(c)方案则优先给定了初始轨迹。显然，(c)方案可获得更大的自由度，因此它的速率相较于(a)和(b)方案更大，而(a)和(b)方案相比，(b)方案仅实现了很小的最小用户速率增益，这表明功率分配仅在带宽分配固定时才能实现边际增益。

![](images/cd8d22fe786131ca9f029db1b44f3c8285bf5fdc0881f5fc0b701b2be890390e.jpg)  
图7不同方案下的所有用户的最小速率图  
Fig.7Minimum rate of all users under different schemes

# 4 结束语

本文研究了联合带宽，发射功率和轨迹优化同时具有有限回程约束的多无人机网络。本文提出了一种有效的算法，通过联合优化所有用户的回程链路和数据链路的带宽，发射功率及无人机的轨迹，可以最大化所有用户的最小速率。仿真结果表明，与其他基准方案相比，基于交替优化的算法可以实现更高的最低用户速率的性能。

# 参考文献：

[1]Huang Yuwei,Xu Jie,Qiu Ling,et al.Cognitive UAV communication via joint trajectory and power control [C]//2018 IEEE 19th International Workshop on Signal Processing Advances in Wireless Communications (SPAWC),Kalamata,2018:1-5.   
[2]Wang Zhe,Duan Lingjie,Zhang Rui.Adaptive deployment for UAV aidedcommunication networks[J].IEEE Transon Wireless Communication,2019,18 (9): 4531-4543.   
[3]Mei Weidong，Wu Qingqing，Zhang Rui. Cellular-connected UAV: uplink association,power control and interference coordination [C]// Globecom IEEE Global Communications Conference.IEEE,2018:206- 212.   
[4] Zhang Guangchi，Yan Haiqiang，Zeng Yong，et al. Trajectory optimization and power allocation for Multi-hop UAV relaying communications [J].IEEE Access,2018,6:48566-48576.   
[5] Zeng Yong,Zhang Rui,Lim T J. Throughput maximization for UAVenabled mobile relaying systems [J].IEEE Trans on Communications, 2016,64 (12): 4983-4996.   
[6]Li Peiming，and Xu Jie.Placement optimization for UAV-enabled wirelessnetworkswithMulti-hopbackhauls[J].Journalof Communications and Information Networks 2018:64-73.   
[7]Mozaffari M, Saad W,Bennis M,et al.Unmanned aerial vehicle with underlaid device-to-device communications:performance and tradeoffs [J].IEEE Trans on Wireless Communications,2016,15(6):3949-3963.   
[8]Li Kai,Ni Wei,Wang Xin,et al. Energy-efficient cooperative relaying for unmanned aerial vehicles [J]. IEEE Trans on Mobile Computing, 2016,15(6):1377-1386.   
[9]王巍，赵继军，彭力，等．基于UAV 的移动物联网远距离通信节能 策略研究[J]．电子学报,2018,46(12):2914-2922.(WangWei,Zhao Jijun,Peng Li,et al.Research on the energy saving strategy for long distance communication of mobile internet of things based on UAVs [J]. Acta Electronica Sinica,2018,46 (12):2914-2922.)   
[10]王巍，赵继军，彭力，等．移动物联网非完整约束中继的协同任务规 划[J].电子学报,2019,47(6):1251-1259.(Wang Wei,Zhao Jijun, Peng Li,et al. Cooperative task planning of ground relay with nonholonomic constraints in mobile internet of things based on UAVs [J]. Acta Electronica Sinica,2019,47 (6): 1251-1259.)   
[11]范茜莹，黄传河，朱钧宇，等．无人机辅助车联网环境下干扰感知的 节点接入机制[J].通信学报,2019,40(6):90-101.(Fan Qianying, Huang Chuanhe, Zhu Junyu,et al. Interference-aware node access scheme in UAV-aided VANET[J]. Journal on Communications,2019,40 (6): 90-101.)   
[12] Wu Qingqing,Zeng Yong and Zhang Rui.Joint trajectory and communication design for UAV-Enabled multiple access [C]// Globecom 2017-2017 IEEEGlobal Communications Conference,Singapore,2017: 1-6.   
[13] Zhang Guangchi,Wu Qingqing,Cui Miao,et al.Securing UAV communications via trajectory optimization [C]// Globecom 2017-2017 IEEE Global Communications Conference,Singapore,2017: 1-6.   
[14] Zhang Guangchi，Wu Qingqing，Cui Miao,et al. Securing UAV communications via joint trajectory and power control [J]. IEEE Trans on Wireless Communications,2019,18 (2):1376-1389.   
[15] Cui Miao, Zhang Guangchi, Wu Qingqing,et al. Robust Trajectory and Transmit Power Design for Secure UAV Communications [J].IEEE Trans on Vehicular Technology,2018,67 (9): 9042-9046.   
[16] Yang Zhaohui,Pan Cunhua,Shikh-Bahaei M,et al. Joint altitude, beamwidth,location,and bandwidth optimization for UAV-enabled communications [J].IEEE Communications Letters,2018,22 (8):1716- 1719.   
[17] Huang Wenhuan,Yang Zhaohui,Pan Cunhua,et al. Joint power,altitude, location and bandwidth optimization for UAV with underlaid D2D communications [J].IEEE Wireless Communications Letrs,2019,8 (2): 524-527.   
[18] Fan Jingyao,Cui Miao,Zhang Guangchi,et al. Throughput improvement for multi-hop UAV relaying [J]. IEEE Access,2019,7(1):147732- 147742.   
[19] Fotouhi A,Qiang Haoran,Ding Ming,et al. Survey on UAVcelular communications:practical aspects, standardization advancements, regulation,and security challenges [J]. IEEE Communications Surveys & Tutorials,2019,21(4): 3417-3442.   
[20] Almohamad A,Hasna M O,Khattab T,et al.Maximizing dense network flow through wireless multihop backhauling using UAVs [Cl// 2018 International ConferenceonInformationandCommunication Technology Convergence (ICTC),IEEE,2018: 526-531,   
[21] Qiu Chen,Wei Zhiqing,Feng Zhiyong,et al. Joint resource allocation, placement and user association of multiple UAV-mounted base stations with in-band wireless backhaul [J]. IEEE Wireless Communications Letters,2019,8 (6): 1575-1578.   
[22] Wu Qingqing，Zeng Yong，and Zhang Rui. Joint trajectory and communication design for multi-UAV enabled wireless networks [J]. IEEE Trans on WirelessCommunications,2018,17 (3): 2109-2121.   
[23] Lin Xingqin,Yajnanarayana V,Muruganathan SD,et al. The sky is not the limit: LTE for unmanned aerial vehicles [J].IEEE Communications Magazine,2018,56 (4): 204-210.   
[24] Boyd S and Vandenberghe L.Convex Optimization [M]. Cambridge University Press, 2004.