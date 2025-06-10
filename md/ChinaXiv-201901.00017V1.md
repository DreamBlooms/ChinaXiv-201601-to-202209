# 基于核函数的软件定义网络DDoS实时安全系统

刘敏，滕华，何先波(西华师范大学 计算机学院，四川 南充 637009)

摘要：针对软件定义网络中DDoS攻击的检测准确率与延迟较长的问题，提出了一种基于核函数的软件定义网络DDoS 实时安全系统。首先，每个周期提取软件定义网络的报文头信息，并组织成矩阵形式；其次，采用马氏距离分析相邻特征向量的显著变化，设计了两个核函数综合评估攻击行为的流量；最终，采用谱聚类技术与协方差统计信息自动地定位攻击者。基于真实软件定义网络进行了实验，结果显示该安全系统实现了较高的检测准确率，并且实现了理想的处理时间。

关键词：软件定义网络；网络安全；拒绝服务攻击；核函数；谱聚类技术中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2018.09.0659

Real time DDoS security system of software definition networks based on kernel functions

Liu Min, Teng Hua,He Xianbo (Computer Academy, China West Normal University,Nanchong Sichuan 637Oo9,China)

Abstract: Aiming at the problems oflog detection accuracy and long delayof DDoS(Distributed Denial-of-Service)attacks inthe software definition networks,This paper proposed areal time DDoS security systemof software definition networks basedonkerelfunctions.Firstlyitabstractedthepacketheaderfieldsofsoftwaredefinitionnetworksperiodly,ndformed the abstracted informationas matrices；then,itadopted the Mahalanobis distance to analyze thesignificantchangeof continuous featurevectors,and itdesigned two kernel functions to evaluate thebehavior flowsof atacks；lastly，the atackersare identifiedbythe spectral clustering techniqueand thecovariancestatistical information.Experimentalesults based onthereal software definition networks show that the proposed security system realizes a good detection accuracy, and performs a reasonable processing time.

Key words: software definition network; network security; denial-of-service attack; kernelfunction;spectral clustering

# 0 引言

DDoS(distributeddenialofservice)攻击是当前互联网中最为常见的攻击行为[I。DDoS的实现简单，并且实现的成本低，因此在各种类型的网络中DDoS均为一个重要的威胁[2]。软件定义网络(software defined networking，SDN)实现了网络控制与数据分离的思想，支持高度的开放性与可编程性，但是安全问题限制了SDN 在诸多场景下的大规模部署与应用。SDN的安全机制主要可分为六种类型[3]：a)SDN安全控制器；b)可组合的安全模块库；c)控制器的DoS、DDoS攻击防御系统；d)流规则的合法性与一致性检测；e)北向接口的安全性；f)应用程序的安全性。其中DDoS攻击直接导致网络瘫痪，对 SDN 的危害极大[4]。

文献[5]利用GHSOM技术，设计了基于对象特征的DDoS攻击检测方法。该方法结合SDN网络及攻击特点，提出基于目的地址的检测七元组，并以此作为判断目标地址是否受到DDoS攻击的检测元素。文献[6]提出了一种在SDN环境下基于KNN 算法的模块化DDoS攻击检测方法，该方法选取SDN网络的五个关键流量特征，采用优化的KNN算法对选取的流量特征进行流量异常检测。文献[7]提出了一种控制器的DDoS检测系统，该系统首先将端口的流事件分类，使用序贯概率比检验(sequential probability ratio test,SPRT)检测流量是否为异常。文献[8]对几类SDN的DDoS安全系统进行了分析，基于流量的统计分析方法一般检测效果较好，但是计算效率较低；而基于SDN报文头特征的分析方法计算效率较高，但是检测的准确率较低。

DDoS攻击可能导致整个网络瘫痪，所以需要在初期就能识别出DDoS流量，以防止DDoS造成更大的破坏[9]。为了在保证DDoS安全系统检测准确率的前提下保持较快的处理速度，设计了一种基于核函数的软件定义网络DDoS实时安全系统。DDoS攻击的出现往往伴随着流量模式的剧烈变化，所以本系统将消息流特征的明显变化作为一个潜在的DDoS攻击。目前主流的DDoS安全系统主要检测出DDoS攻击的流量，无法定位攻击源，而本系统能够检测出DDoS攻击行为，并且识别出攻击者。本系统属于无监督方法，利用观察的消息流量类型与数据量，并不需要额外的信息。

# 1 问题模型

# 1.1软件定义网络的OpenFlow 模型

控制器管理所有的路由决策，通过OpenFlow交换机的flow 表完成每个报文的转发。图1所示是OpenFlowversion1.3 协议[10]的报文头。

<html><body><table><tr><td>Ingress port</td><td>Ether src</td><td>Ether</td><td>VLAN</td><td>VLANy</td><td>IP_SRC</td><td>IP_dest</td><td>propcal</td><td>Src port</td><td>Dest port</td></tr></table></body></html>

![](images/86c2ffa1999624c3c20a84139ca9376efa9c7b8f8c6ac58ae5e9949e6a48f42e.jpg)  
图2所示是OpenFlow报文的处理流程。

# 1.2软件定义网络的DDoS攻击模型

每隔一个周期对控制报文进行一次采样，表示为 $_ { t = i \Delta t }$ 将该时段的样本组成一个特征向量。 $\Delta t$ 表示一个观察时段，监控该时段交换机收到的控制报文。在 $\Delta t$ 的结束，将IP_SRC用户的流量表示为 $d$ 维的向量 $\mathbf { v } _ { r }$ ，其中 $d$ 为各种流量类型的数量。向量 $\textbf { v }$ 的元素为整型，元素对应了第 $i$ 时间帧$( ( i - 1 ) \Delta \mathsf { < } t \mathsf { < } i \Delta )$ 内每种消息类型的出现次数。

假设第 $\boldsymbol { r }$ 个用户在观察时段内发出 $P _ { r }$ 个消息，每个消息的计数器表示为 $\mathbf { v } _ { r } ^ { p }$ $\therefore p { = } 1 , . . . , P _ { r }$ ，因此观察时段内的总采样信息可表示为 $\mathbf { v } _ { r } = \sum _ { p = 1 } ^ { P _ { r } } \mathbf { v } _ { r } ^ { p }$ ， $\mathbf { v } _ { r }$ 表示第 $\boldsymbol { r }$ 个用户发送的计数器矩阵,如图3所示。

![](images/aa36137c06d66912a37ff758a9ae68c94b3039f59931bcd7c2cc58adef625fee.jpg)  
Fig.2Processing flow of openflow message   
图3第 $\boldsymbol { r }$ 个用户的计数器矩阵 Fig.3Counter matrix of rth user

假设 $\textbf { x }$ 为状态向量，表示一个 $^ d$ 维的计数向量，定义为在一个观察时段内 $| U |$ 个用户的协同活动次数。服务器端所有用户的计数器向量之和定义为服务器状态向量，计算式为$\mathbf { x } = \sum _ { r = 1 } ^ { | U | } \mathbf { v } _ { r }$ ，如图4所示。

图2OpenFlow 报文的处理流程  
图5增加时间戳的用户消息向量

![](images/c207fc224fd4edbf51a9c9be4558661021c2ca68ea650c2ac4be392b5ea96cf0.jpg)  
图4服务器状态向量的示意图Fig.4Diagram of server states vector  
Fig.5Time-stamped user message vector diagram of serv

假设 $\mathbf { \lambda } _ { \pmb { x } _ { i } }$ 与 $x _ { j } \epsilon R ^ { d }$ 分别表示第i、 $j$ 个观察时段的服务器状态向量，本文采用这些特征向量(服务器状态向量)监控软件定义网络的流量变化。假设 $\mathbf { M }$ 为一个 $d { \times } d$ 的正定矩阵， $D _ { \mathrm { M } } ( x _ { i } ,$ $\mathbf { \sigma } _ { x j } )$ 为特征向量 $\mathbf { x } _ { i }$ 与 $\mathbf { X } _ { j }$ 之间的距离， $\mathbf { M }$ 表示尺度矩阵。$f ( \mathbf { M } | \mathbf { x } _ { n } { : } \mathbf { x } _ { n - k - 1 } )$ 为一个关于 $\mathbf { M }$ 的函数，定义为 ${ \bf x } _ { n - k - 1 }$ 到 ${ \bf x } _ { n }$ 之间(时间长度为 $k )$ 窗口的特征向量记录。

上述特征向量不包含时间戳信息，假设第 $\boldsymbol { r }$ 个用户、消息 $P _ { r }$ 的时间戳序列为 $t _ { r } ^ { 1 } , . . . , t _ { r } ^ { P _ { r } }$ ，通过对消息指示向量增加增广向量引入时间戳信息，具体方法为： ${ \left( { { \bf { W } } _ { r } ^ { p } } \right) ^ { \mathrm { { T } } } } = { \left( { \left( { { \bf { V } } _ { r } ^ { p } } \right) ^ { \mathrm { { T } } } } , t _ { r } ^ { p } \right) }$ 。 $\mathbf { W } _ { r } ^ { p }$ 表示带时间戳的消息指示向量， $\mathbf { W } _ { r } ^ { p } \in \mathbf { R } ^ { d + 1 }$ 与向量 $\mathbf { v } _ { r } ^ { p }$ 的关系如图5所示。

$$
\mathbf { w } _ { r } ^ { p } = \left| \begin{array} { l l } { \mathbf { v } _ { r } ^ { p } } \\ { t _ { r } ^ { p } } \end{array} \right|
$$

可将任意用户 $u _ { r }$ 表征为一个时间的序列，定义为一个矩阵： $\mathbf { V } _ { r } = [ \mathbf { v } _ { r } ^ { 1 } | \mathbf { v } _ { r } ^ { 2 } | . . . | \mathbf { v } _ { r } ^ { P } ]$ 或者 $\mathbf { W } _ { r } = [ \mathbf { w } _ { r } ^ { 1 } | \mathbf { w } _ { r } ^ { 2 } | \ldots | \mathbf { w } _ { r } ^ { P _ { r } } ]$ 。采用核函数计算两个用户 $( u _ { q } , ~ u _ { r } )$ 的相似性，将相似性表示为 $K ( u _ { q } , \ u _ { r } )$ 。$\kappa \big ( \mathbf { w } _ { r } ^ { P r } , \mathbf { w } _ { r } ^ { P q } \big )$ 定义为相同时段内两个用户之间的相似性，其中$\mathbf { w } _ { r } ^ { P r }$ 表示第 $\boldsymbol { r }$ 个用户的第 $p _ { r } ^ { t h }$ 个消息， $\mathbf { w } _ { r } ^ { P q }$ 表示第 $\boldsymbol { q }$ 个用户的第 $p _ { q } ^ { t h }$ 个消息。最终可计算出某个观察时段内 $\vert U \vert \times \vert U \vert ($ 所有用户)的核矩阵 $\mathbf { K }$ 。

# 2 基于自适应距离的异常监控

在一个平稳过程中消息的特征应当具有高度的统计相似性，而非稳态过程的两个特征集之间的距离较大。因此检测消息特征距离的显著变化点，对采样时间的流量进行分析，检测出潜在的DDoS攻击行为。

# 2.1 马氏距离

假设 $\mathbf { M } \mathbf { \epsilon } \mathbf { S } _ { + }$ 为一个 $d { \times } d$ 的对称半正定矩阵，那么 $\mathbf { x } _ { i }$ 与 $\mathbf { x } _ { j }$ 之间的马氏距离 ${ \bf D } _ { M }$ 计算为

$$
D _ { M } ( \mathbf { x } _ { i } , \mathbf { x } _ { j } ) { = } ( \mathbf { x } _ { i } { - } \mathbf { x } _ { j } ) ^ { \mathrm { T } } \mathbf { M } ( \mathbf { x } _ { i } { - } \mathbf { x } _ { j } )
$$

全秩样本协方差矩阵的逆 $\pmb { \Sigma }$ 是马氏距离的一种特殊情况，如果特征集服从标准的高斯分布，可得 $\scriptstyle \mathbf { M } = \sum = \mathbf { I } _ { \mathit { c } }$ ，对称半正定矩阵可分解为 $\mathbf { M } { = } \mathbf { A } \tau \mathbf { A }$ ，因此 $\mathbf { A }$ 为一个 $e \times d$ 的投影矩阵，并且 $e { \leqslant } d$ 。可获得以下的关系式：

$$
\begin{array} { r l } & { D _ { \mathrm { M } } ( \mathbf { x } _ { i } , \mathbf { x } _ { j } ) = ( \mathbf { x } _ { i } , \mathbf { x } _ { j } ) ^ { \mathrm { T } } \mathbf { M } ( \mathbf { x } _ { i } , \mathbf { x } _ { j } ) } \\ & { = ( \mathbf { x } _ { i } , \mathbf { x } _ { j } ) ^ { \mathrm { T } } \mathbf { A } ^ { \mathrm { T } } \mathbf { A } ( \mathbf { x } _ { i } , \mathbf { x } _ { j } ) = \left( \mathbf { A } ( \mathbf { x } _ { i } , \mathbf { x } _ { j } ) \right) ^ { \mathrm { T } } \mathbf { A } ( \mathbf { x } _ { i } - \mathbf { x } _ { j } ) } \\ & { = \left\| \mathbf { a } _ { i } - \mathbf { a } _ { j } \right\| _ { 2 } ^ { 2 } = D _ { E } ( \mathbf { a } _ { i } , \mathbf { a } _ { j } ) = D _ { \mathrm { A } } ( \mathbf { x } _ { i } , \mathbf { x } _ { j } ) } \end{array}
$$

其中： $\mathbf { a } _ { i = \mathbf { A } \mathbf { X } { i } }$ 为投影向量； $\mathbf { D } _ { E }$ 为欧氏距离。式(2)说明特征空间中马氏距离等价于投影空间的欧氏距离。

# 2.2基于距离的网络流量模型

通过观察滑动窗口的距离之和实现对网络流量的监控，该距离称为流量的移动距离，将滑动窗口之和与阈值 $\epsilon$ 比较，决定是否为异常流量。一个大小为 $k$ 的窗口移动距离可定义为一个关于对称正定矩阵 $( \mathbf { M } \in \mathbf { S } _ { + + } )$ 的函数，如式（3）所示。

$$
f \left( \mathbf { M } \mid \mathbf { x } _ { n } : \mathbf { x } _ { n - k - 1 } \right) = \sum _ { j = n - k - 1 } ^ { n - 1 } \left( \mathbf { x } _ { n } - \mathbf { x } _ { j } \right) ^ { \mathrm { T } } \mathbf { M } ( \mathbf { x } _ { n } - \mathbf { x } _ { j } )
$$

如果使用马氏距离计算的移动距离高于阈值 $\epsilon$ ，即$f ( \mathbf { M } _ { n - 1 } | \mathbf { x } _ { n } { : } \mathbf { x } _ { n - k - 1 } ) { > } \epsilon _ { t h }$ ，那么触发一个警告。每个周期更新一次马氏距离，定义为

$$
\operatorname* { m i n } _ { \mathbf { M } \in \mathbf { S } _ { + + } } f ( \mathbf { M } | \mathbf { x } _ { n } : \mathbf { x } _ { n - k - 1 } ) + \lambda D _ { I d } ( \mathbf { M } , \mathbf { M } _ { n - 1 } ) + \beta D _ { I d } ( \mathbf { M } , \mathbf { I } )
$$

其中：第2、3项为正则化函数，该函数基于对数行列式散数实现(LogDet)[11]。LogDet函数可估计两个矩阵之间的距离,定义为：

$$
D _ { I d } ( \mathbf { M } , \mathbf { M } _ { t - 1 } ) = t r ( \mathbf { M } \mathbf { M } _ { t - 1 } ^ { - 1 } ) - \log \operatorname* { d e t } ( \mathbf { M } \mathbf { M } _ { t - 1 } ^ { - 1 } ) - d
$$

其中： $t r ( . )$ 为矩阵的迹函数。

计算式(4)的导数，可获得最优的马氏矩阵 $( \mathbf { M } ^ { * } )$

$$
\begin{array} { l } { { \displaystyle { \bf M } ^ { * } = \left( \frac { \lambda } { \lambda + \beta } { \bf M } _ { n - 1 } ^ { - 1 } + \frac { \beta } { \lambda + \beta } { \bf I } \right. } } \\ { { \displaystyle \left. + \frac { 1 } { \lambda + \beta } \sum _ { j = n - k - 1 } ^ { n - 1 } \left( { \bf x } _ { n } - { \bf x } _ { j } \right) \left( { \bf x } _ { n } - { \bf x } _ { j } \right) ^ { \top } \right) ^ { - 1 } } } \end{array}
$$

每个周期重复更新该马氏矩阵。算法1所示是流量改变的检测算法。

算法1自适应移动距离的流量改变检测算法

1初始化 ${ \bf { M } } _ { 0 }$   
2初始化参数 $k , \lambda , \beta , \alpha$   
3while(新流量){  
4 观察窗口(大小为 $k )$ 内的流量，计算计数器向量；  
5 i $f ( \mathbf { M } _ { n - 1 } | \mathbf { x } n ; \mathbf { x } _ { n - k - 1 } ) > \epsilon \ \{$ （204号  
6 发出警告;  
7 允许恶意用户检查程序；  
8 }  
9 评估 $\mathbf { M } ^ { * }$   
10 $\mathbf { M } _ { n - 1 } { = } \mathbf { M } ^ { * }$ ·  
11}

# 2.3移动距离的阈值

根据实验分析，移动距离之和的分布可近似为卡方分布。然后从高斯分布获得马氏距离，因此可得： $\scriptstyle { \mu = \mathbf { x } _ { n } }$ ， ${ \boldsymbol { \Sigma } } { = } \mathbf { M } ^ { - 1 }$ 。假设 $\textbf { y }$ 是当前滑动窗口的观察集合，如果 $\textbf { y }$ 是一个服从高斯分布的 $d$ 维随机向量，其平均向量为 $\mu$ ，协方差矩阵为 $\pmb { \Sigma }$ ，将 $\scriptstyle \mathbf { z } = ( \mathbf { y } - \mathbf { x } _ { n } ) \tau \mathbf { M } ( \mathbf { y } - \mathbf { x } _ { n } ) = ( \mathbf { y } - { \boldsymbol { \mu } } ) \tau { \boldsymbol { \Sigma } } ^ { - 1 } ( \mathbf { y } - { \boldsymbol { \mu } } )$ 转换为自由度为 $d$ 的卡方分布。

假设 $z _ { i }$ 表示 $k$ 个独立同分布的随机变量， $z _ { i }$ 服从卡方分布，如 $\begin{array} { r } { z _ { 1 } \sim \chi _ { \alpha , d _ { 1 } } ^ { 2 } , z _ { 2 } \sim \chi _ { \alpha , d _ { 2 } } ^ { 2 } , . . . , z _ { k } \sim \chi _ { \alpha , d _ { k } } ^ { 2 } } \end{array}$ 。根据独立卡方分布的变量属性，随机变量之和服从卡方分布，其自由度为 $d _ { 1 } { + } d _ { 2 } { + } . . . { + } d _ { k } ,$ 具体可表示为

$$
Z = z _ { 1 } + z _ { 2 } + . . . + z _ { k } , \ Z \sim \chi _ { \alpha , d _ { 1 } + d _ { 2 } + . . . + d _ { k } } ^ { 2 }
$$

最终，异常流量检测模型的阈值为 $\mathcal { E } _ { t h } = \chi _ { \alpha , k ^ { * } d } ^ { 2 }$ ，其中 $\alpha$ 表示收到异常流量的概率。将正常流量情况下，移动距离平均值的评分表示为Z，Z值达到阈值 $\varepsilon _ { t h }$ 的概率为 $a , a$ 值根据应用场景可设为 $\alpha \epsilon \{ 0 . 1 , 0 . 0 5 , 0 . 0 2 , 0 . 0 1 \}$ 。

异常流量检测模型的阈值计算式为

$$
\varepsilon _ { t h } = c k { \left( \frac { d } { 2 } \right) } ^ { 2 }
$$

其中： $k$ 为时间窗口长度； $d$ 为向量维度； $\boldsymbol { c }$ 为一个常量。因为每个周期地观察中均会更新观察量之间的马氏距离，所以本系统是一个自适应的智能安全系统。

# 3 判断恶意用户

如果一个异常流量为一个DDoS攻击，那么需要识别恶意用户的集合，从而防止造成分布式攻击。观察周期内每个用户的历史行为表示为一个时间序列，如图3所示。使用相似性函数处理时间序列，将行为相似的用户分类为同一个组。提出了两种攻击判别方法：a)基于全局的时间序列对齐核，计算消息序列特征之间的距离；b)在观察周期结尾提取的用户消息数量向量。

# 3.1 时间序列对齐核

本文考虑 $k$ 长度窗口内的带时间戳消息，将消息表示为时间序列格式，即 $( n { - } k { - } 1 ) { , } { \ldots } , ( n { - } 1 )$ 。每个用户的序列包含不同数量的消息事件，每个事件发生的时间点不同。本文的目标是基于核方法计算用户消息之间的相似性，首先需要将消息队列进行对齐处理，不同长度消息之间的相似性较低，因此同类型消息的相似性较高，不同类型消息的相似性较低。

假设一对用户 $( u _ { q } , u _ { r } )$ 的带时间戳消息序列为 $( \mathbf { W } _ { q } , \mathbf { W } _ { r } )$ ，假设 $\mathbf { W } _ { q } = \left[ \mathbf { W } _ { q } ^ { 1 } \mid \mathbf { W } _ { q } ^ { 2 } \mid \mathbf { W } _ { q } ^ { 3 } \right]$ 与 $\mathbf { W } _ { r } = \left[ \mathbf { w } _ { r } ^ { 1 } \left| \mathbf { w } _ { r } ^ { 2 } \right. \right]$ 分别具有3个与2个消息事件。图6所示是 ${ \mathbf W } _ { q }$ 与 $\mathbf { W } _ { r }$ 所有可能的对齐情况，该案例共有5个对齐情况，如下所示：

$$
\begin{array} { r l } { } & { { } \bigtriangleup \big ( \mathbf { w } _ { q } ^ { 1 } , \mathbf { w } _ { r } ^ { 1 } \big ) , \big ( \mathbf { w } _ { q } ^ { 1 } , \mathbf { w } _ { r } ^ { 2 } \big ) , \big ( \mathbf { w } _ { q } ^ { 2 } , \mathbf { w } _ { r } ^ { 2 } \big ) , \big ( \mathbf { w } _ { q } ^ { 3 } , \mathbf { w } _ { r } ^ { 2 } \big ) } \end{array}
$$

$$
\begin{array} { r l } { } & { { } \bigtriangleup \big ( \mathbf { w } _ { q } ^ { 1 } , \mathbf { w } _ { r } ^ { 1 } \big ) , \big ( \mathbf { w } _ { q } ^ { 2 } , \mathbf { w } _ { r } ^ { 2 } \big ) , \big ( \mathbf { w } _ { q } ^ { 3 } , \mathbf { w } _ { r } ^ { 2 } \big ) } \end{array}
$$

$$
\begin{array} { r l } { } & { { } \bigtriangleup \big ( \mathbf { w } _ { q } ^ { 1 } , \mathbf { w } _ { r } ^ { 1 } \big ) , \big ( \mathbf { w } _ { q } ^ { 2 } , \mathbf { w } _ { r } ^ { 1 } \big ) , \big ( \mathbf { w } _ { q } ^ { 2 } , \mathbf { w } _ { r } ^ { 2 } \big ) , \big ( \mathbf { w } _ { q } ^ { 3 } , \mathbf { w } _ { r } ^ { 2 } \big ) } \end{array}
$$

$$
\begin{array} { r l r } {  { ( 4 ) \big ( \mathbf { w } _ { q } ^ { 1 } , \mathbf { w } _ { r } ^ { 1 } \big ) , \big ( \mathbf { w } _ { q } ^ { 2 } , \mathbf { w } _ { r } ^ { 1 } \big ) , \big ( \mathbf { w } _ { q } ^ { 3 } , \mathbf { w } _ { r } ^ { 2 } \big ) } } \end{array}
$$

$$
\begin{array} { r l } { } & { { } \bigodot \big ( \mathbf { w } _ { q } ^ { 1 } , \mathbf { w } _ { r } ^ { 1 } \big ) , \big ( \mathbf { w } _ { q } ^ { 2 } , \mathbf { w } _ { r } ^ { 1 } \big ) , \big ( \mathbf { w } _ { q } ^ { 3 } , \mathbf { w } _ { r } ^ { 1 } \big ) , \big ( \mathbf { w } _ { q } ^ { 3 } , \mathbf { w } _ { r } ^ { 2 } \big ) } \end{array}
$$

文献[12]提出了一种全局对齐核，使用动态规划计算两个序列的相似性，本文基于文献[12]的算法实现，唯一的修改是引入马氏距离。

![](images/7423f0f7e5bedffed1db1aaa237f5b437c4116a7d20b605cfdaaf366700ae7c9.jpg)  
图6 $\mathbf { W } _ { q }$ 与 $\mathbf { W } _ { r }$ 的所有对齐情况Fig.6All aligned cases of $\mathbf { W } _ { q }$ and ${ \bf W } _ { r }$

3.1.1全局序列对齐核

给定两个用户 $\left( u _ { q } , \ u _ { r } \right)$ 的两个消息序列 $\mathbf { W } _ { q } = [ \mathbf { w } _ { q } ^ { 1 } \mid \mathbf { w } _ { q } ^ { 1 } \mid \ldots \mid \mathbf { w } _ { q } ^ { P _ { q } } ]$ 与 $\mathbf { W } _ { r } = [ \mathbf { w } _ { r } ^ { 1 } | \mathbf { w } _ { r } ^ { 1 } | \ldots | \mathbf { w } _ { r } ^ { P } ]$ ，假设其状态空间为 $\Omega$ ，设计一个二维数组 $T _ { P q , P r }$ 保存二维序列，其中 ${ \cal T } _ { P q , 0 } { = } 0 ( p _ { q } { = } 1 , . . . , P _ { q } )$ ， $T _ { 0 }$ $\scriptstyle P r = 0 ( p _ { r } = 1 , \ldots , P _ { r } )$ ， $\scriptstyle T _ { 0 , 0 = 0 }$ 。假设存在一个函数可度量用户 $u _ { q }$ 与$u _ { r }$ 之间消息事件的相似性，设为 $\kappa \big ( \mathbf { w } _ { q } ^ { p _ { q } } , \mathbf { w } _ { q } ^ { p _ { r } } \big )$ 。因此可通过递归方法计算出 $T _ { P q , P r }$

$$
T _ { p _ { q } , p _ { r } } = \left( T _ { p _ { q } , p _ { r } - 1 } + T _ { p _ { q } - 1 , p _ { r } - 1 } + T _ { p _ { q } - 1 , p _ { r } } \right) \kappa \left( \mathbf { w } _ { q } ^ { p _ { q } } , \mathbf { w } _ { r } ^ { p _ { r } } \right)
$$

最终可获得两个用户 $( u _ { q } , ~ u _ { r } )$ 之间相似性未正则化的结果，如式(10)所示。

$$
K _ { u n n o r m e d } ( u _ { q } , u _ { r } ) = T _ { P _ { q } , P _ { r } }
$$

获得每对用户的核矩阵之后，为了解决尺度不统一的问题，对 $| U | \times | U |$ 核矩阵进行单位对角正则化处理，其中 $| U |$ 表示系统中活动用户的数量。单位对角正则化的方法如式（11）所示。

$$
K ( u _ { q } , u _ { r } ) = \frac { K _ { u n n o r m e d } ( u _ { q } , u _ { r } ) } { \sqrt { K _ { u n n o r m e d } ( u _ { q } , u _ { q } ) } \sqrt { K _ { u n n o r m e d } ( u _ { r } , u _ { r } ) } } \cdot q
$$

$$
K ( u _ { q } , u _ { r } )  [ 0 , 1 ]
$$

将上述核矩阵称为时间序列核。

3.1.2核函数

一个窗口内的每个用户可表征为带时间戳的消息序列，用户消息序列包括了不同的长度与不同的消息类型。

假设两个带时间戳的向量为 $\left( \mathbf { W } _ { q } ^ { p _ { q } } \right) ^ { \mathrm { T } } = \left( \left( \mathbf { V } _ { q } ^ { p _ { q } } \right) ^ { \mathrm { T } } , t _ { q } ^ { p _ { q } } \right)$ 与$\left( \mathbf { w } _ { r } ^ { p _ { r } } \right) ^ { \mathrm { T } } = \left( \left( \mathbf { v } _ { r } ^ { p _ { r } } \right) ^ { \mathrm { T } } , t _ { r } ^ { p _ { r } } \right)$ ，两个向量的核函数定义为

$$
K \big ( \mathbf { w } _ { q } ^ { p _ { q } } , \mathbf { w } _ { r } ^ { p _ { r } } \big ) { = } \exp \left( { - \gamma D _ { M } \left( \mathbf { v } _ { q } ^ { p _ { q } } , \mathbf { v } _ { r } ^ { p _ { r } } \right) - \rho \big | t _ { q } ^ { p _ { q } } - t _ { r } ^ { p _ { r } } \big | } \right)
$$

$$
D _ { M } \left( \mathbf { v } _ { q } ^ { p _ { q } } , \mathbf { v } _ { r } ^ { p _ { r } } \right) = \left( \mathbf { v } _ { q } ^ { p _ { q } } , \mathbf { v } _ { r } ^ { p _ { r } } \right) ^ { \mathrm { T } } \mathbf { M } \left( \mathbf { v } _ { q } ^ { p _ { q } } , \mathbf { v } _ { r } ^ { p _ { r } } \right)
$$

其中： $\mathbf { M }$ 为式(6)的马氏矩阵。如果 $\mathbf { V } _ { q } ^ { p _ { q } } = \mathbf { V } _ { r } ^ { p _ { r } }$ 并且 $t _ { q } ^ { p _ { q } } = t _ { r } ^ { p _ { r } }$ ，可得 $\kappa \big ( \mathbf { w } _ { q } ^ { p _ { q } } , \mathbf { w } _ { r } ^ { p _ { r } } \big ) { = } 1$ 。系数y与 $\rho$ 分别为消息距离与时间距离的权重，本文假设两者相等 $\scriptstyle \gamma = \rho = 1$ 。

# 3.2用户距离核

基于马氏距离计算用户之间的相似性核矩阵，如果马氏距离越接近0，那么两个用户的相似性越高，反之则相似性越低，马氏距离核可视为一种高斯核的特殊情况。基于用户的消息计数向量 $\mathbf { v } _ { q } , \mathbf { v } _ { r } \in \mathbb { R } ^ { d }$ ，比较两个用户 $u _ { q }$ 与 $u _ { r }$ 的相似性：

$$
K ( u _ { q } , u _ { r } ) = \exp \left( - \big ( \mathbf { v } _ { q } - \mathbf { v } _ { r } \big ) ^ { \mathrm { T } } \mathbf { M } \big ( \mathbf { v } _ { q } - \mathbf { v } _ { r } \big ) \right)
$$

将式(13)的核简称为距离核，如果 $\scriptstyle \mathbf { v } _ { q } = \mathbf { v } _ { r }$ ，那么 $K ( u _ { q } ,$ （20$u _ { r } ) { = } 1$ ，该特征向量并未包含消息的时间戳信息，仅仅评价了该窗口内用户的消息特征。

# 3.3谱聚类算法

式(11)(13)两式中计算了用户之间相似性的核矩阵 $\mathbf { K }$ ，矩阵K可表示为一个全连接的加权邻接图，图中顶点表示用户，边表示相似性。邻接矩阵应当可分为恶意用户与合法用户两个子图。使用拉普拉斯谱聚类算法将邻接图分类，该方法可将相似的节点分为同一类，同时保证不相似节点彼此远离[13]。

将第 $q$ 个活动用户核矩阵的元素之和定义为该用户的度，那么一个给定窗口中第 $q$ 个活动用户的度定义为

$$
d g _ { q } = \sum _ { r = 1 } ^ { | U | } \mathbf { K } _ { q , r }
$$

其中： $\mathbf { K } _ { q , r } = \mathbf { K } \big ( u _ { q } , u _ { r } \big )$ 。

度矩阵 $\mathbf { D }$ 为对角矩阵，其对角元素为“度”： $\boldsymbol { d g } _ { 1 }$ $d g _ { 2 } , . . . , d g _ { | U | }$ 。拉普拉斯矩阵 $\mathbf { L }$ 的评估方法如式（15）定义：

# $\scriptstyle \mathbf { L = D - K }$

其中： $\mathbf { K }$ 是 $| U | \times | U |$ 的核矩阵， ${ \bf K } ( u _ { q } , u _ { r } )$ 的计算方法为式(11)或者式(13)。

算法2所示是谱聚类算法的伪代码。

算法2拉普拉斯谱聚类算法输入：给定 $\mathsf { R } ^ { | \boldsymbol { U } | \times | \boldsymbol { U } | }$ 中的 $\pmb { \kappa }$ 矩阵。输出：矩阵D与L的评估结果。

1计算广义特征问题 $\scriptstyle \mathsf { L } \psi = \Lambda \mathsf { D } \psi$ 的前两个特征向量 $\psi _ { 1 }$ 与 $\psi _ { 2 }$ ，其中 $\wedge$ 表示特征值 $\lambda _ { 1 } , . . . , \ \lambda _ { | \upsilon | }$ 的对角矩阵。  
2将 $\psi _ { 1 }$ 与 $\psi _ { 2 }$ 两个特征向量组成矩阵 $\Psi \in \mathsf { R } ^ { | U | ^ { \times } 2 }$ 。将 $\pmb { \psi }$ 的各行作为映射空间内的新特征向量。

3采用2-means聚类算法对特征向量进行处理，获得分类的向量。

# 3.4恶意用户类的自动识别

大多数恶意用户均会表现出重复且相关的行为，而合法用户则一般表现出不重复且多样化的行为。4.3节将合法用户与恶意用户进行了分类，下一个任务则是识别恶意用户的攻击类型。

因为恶意用户的消息序列向量的重复性高、多样性低，所以计算类内用户消息序列向量的协方差矩阵。如果协方差矩阵越小，那么该类为恶意用户的可能性越大。算法3所示是恶意用户的选择算法。

算法3恶意用户类的选择算法  
输入：分类后的向量C。  
输出：类 $C _ { 1 }$ 与 $C _ { 2 }$ 的类型。  
1计算类 $\boldsymbol { C } _ { 1 }$ 与 $C _ { 2 }$ 内投影消息向量的协方差矩阵；2if（协方差矩阵 $\therefore \angle C = 9$ ）{  
3 该类为恶意用户；  
$^  4 \}$ else{  
5 计算协方差矩阵的特征值；  
6 特征值最高的类为恶意用户。  
7}

算法4所示是DDoS智能安全系统的总体伪代码。

算法4DDoS智能安全系统的总体伪代码提取OpenFlow报文头的信息按照2.2节建立向量模型与矩阵模型

if（时间序列对齐核）{

设置权重参数 $\gamma$ 与 $\rho$ 计算核矩阵 $\pmb { \kappa }$ ，即 $\forall \left( { { u } _ { q } } , { { u } _ { r } } \right) \in U \times U$ ，可得 $\pmb { \mathsf { K } } _ { q , r } { = } K ( u _ { q } , \ u _ { r } )$ 0对 $\kappa _ { u n n o r m e d }$ 进行对角正则化处理，获得 $\pmb { \kappa } _ { \circ }$ }if（用户距离核）{计算核矩阵 $\pmb { \kappa }$ ，即 $\bigtriangledown \left( \boldsymbol { u } _ { q } , \boldsymbol { u } _ { r } \right) \in \boldsymbol { U } \times \boldsymbol { U }$ ，可得 $\aleph _ { q , r } { = } K ( u _ { q } , \ u _ { r } )$ 。}采用拉普拉斯谱聚类算法(算法2)将 $\pmb { \kappa }$ 分类，获得结果c。采用算法3检测C的恶意用户。

# 4 实验结果与分析

# 4.1实验环境与实验方法

实验环境为PC机：IntelCorei7-4770处理器， $3 . 4 \ : \mathrm { G H z }$ 主频，8GB内存。操作系统为LinuxUbuntu14.04，交换机系统为 Mininet Version 2.2.26，OpenFlow version1.3。在实验室搭建了实际的软件定义网络，如图7所示。该网络由三个控制器组成，每个控制器包含一个POX 控制层、64个主机与8个OpenFlow 交换机。每个OpenFlow 连接8个主机，组成一个子网。POX是一个快速的轻量级 SDN控制层，并且支持各种平台，因此实验中采用了POX控制层。

采用MiniEdit工具建立仿真网络，采用OpenVirtual交换机(OVS)作为网络交换机，OVS中已经实现了各种主流的网络接口与网络协议。采用 Scapy工具产生实际的 flooding攻击，合法流量中包含随机的数据流。基于Python语言编程生成网络流量，使用Python的“randrange”函数生成随机的源IP地址，合法流量的目标IP地址范围为10.0.0.1\~10.0.0.64，运行两个python 脚本，一个负责生成攻击流量，另一个负责生成合法流量。

![](images/723374184ba87c4d222742c9b52a592a047a2680831a761b73be62019bc2a0fc.jpg)  
Fig.7Software defined network constructed in the experiment

4.1.1DDoS安全系统的性能评估指标

采样精度、召回率与F-score三个指标评估DDoS安全系统的性能，分别定义为

精度 $\mathbf { \Sigma } = \mathbf { \Sigma }$ 正确检测的攻击/所有检测的攻击召回率 $\mathbf { \sigma } = \mathbf { \sigma }$ 正确检测的攻击/样本的总数量

F-score $\mathbf { \sigma } = \mathbf { \sigma }$ 精度\*召回率 $^ { * } 2 ,$ （精度 $^ +$ 召回率)

4.1.2测试例

为了测试本系统对DDoS攻击安全性，考虑了两个实验测试例。第一个测试例为单目标攻击实验：在一个主机上运行三种不同流量比例的DDoS攻击，三种攻击流量比例分别为 $10 \%$ 、 $20 \%$ 、 $30 \%$ ；第二个测试例为子网目标攻击的实验：在一个子网中运行三种不同比例的DDoS攻击，三种攻击流量比例分别为 $10 \%$ 、 $20 \%$ 、 $30 \%$ 。

# 4.1.3仿真参数设置

表1所示是实验中的参数设置。因为实验中共有64个主机，所以本系统的窗口大小设为80。根据预处理实验的结果，本实验环境下 $k { = } 5$ 、 $\lambda { = } 1$ 、 $\scriptstyle { \beta = 4 }$ 、 $c { = } 1$ 获得了较好的检测性能。

表1测试例的参数设置  
Table1 Parameters of test cases   

<html><body><table><tr><td>参数</td><td>取值</td></tr><tr><td>报文类型</td><td>UDP</td></tr><tr><td>窗口大小</td><td>80</td></tr><tr><td>目标端口</td><td>80</td></tr><tr><td>源端口</td><td>2</td></tr><tr><td>合法流量间隔</td><td>0.1秒</td></tr><tr><td>攻击流量间隔</td><td>0.025秒</td></tr><tr><td>报文总量</td><td>6500</td></tr><tr><td>数据内容</td><td>随机生成</td></tr><tr><td>k</td><td>5</td></tr><tr><td></td><td>1</td></tr><tr><td>B</td><td>4</td></tr><tr><td>C</td><td>1</td></tr></table></body></html>

# 4.2实验结果与性能分析

4.2.1单目标攻击实验的结果

因为本系统采样周期对检测精度存在一定的影响，所以本文考虑了三个采样周期，分别为1s、3s、5s。将本算法与KNNDD[6]、VNDD[7]两个同类型DDoS 检测系统进行横向比较，综合地评估本系统的性能。每组实验独立地运行30次，将30次实验的结果作为最终的统计结果。

图8所示是三个安全系统的单目标攻击实验的结果。从图中可看出，本系统1s采样周期的精度、召回率与F-score均低于KNNDD、VNDD两个系统，而本系统3s与5s采样周期的性能则具有明显的优势。

![](images/f1da42d15697ad2c052de0cba2360443ab54678ab18248f25e5bf167d45e1537.jpg)  
图7实验搭建的软件定义网络  
图8三个安全系统的单目标攻击实验的结果Fig.8Result of single target attack of three security systems4.2.2子网目标攻击实验的结果

本文考虑了三个采样周期，分别为1s、3s、5s。将本算法与KNNDD[6]、VNDD[7]两个同类型DDoS检测系统进行横向比较，综合地评估本系统的性能。每组实验独立地运行30次，将30次实验的结果作为最终的统计结果。

图9所示是三个安全系统的子网目标攻击实验的结果。从图中可看出，本系统1s采样周期的精度、召回率与F-score均低于KNNDD、VNDD 两个系统，本系统3s采样周期的性能与KNNDD 算法接近，而系统5s采样周期的性能表现

出明显的优势。

![](images/668aeb7bd50a7fc1111df0ff725da97be582021682f149f03635b35e2899c07a.jpg)  
图9三个安全系统的子网目标攻击实验的结果

根据算法4的处理流程，本系统主要有三个模块组成，分别为计算距离核、计算时间序列对齐核、谱聚类处理。实验中分别统计了三个模块的平均处理时间，如图10所示。从图中可看出，三个不同的采样周期下，本系统的处理时间较为稳定，总时间约为 $3 . 5 \mathrm { ~ s ~ }$ ，满足实时检测的要求。

![](images/89f6ac8cc83cb650e5d8406aa3c03d1580d7d9e2c167d7657a7173a3a049cb21.jpg)  
Fig.9Result of sub-network target attack of three security systems 4.2.3安全系统的计算效率   
图10三个模块的平均处理时间  
Fig.10Average processing time of three models

# 5 结束语

DDoS攻击的出现往往伴随着流量模式的剧烈变化，本系统将消息流特征的明显变化作为一个潜在的DDoS攻击。本系统能够检测出DDoS攻击行为并识别出攻击者。本系统属于无监督方法，利用观察的消息流量类型与数据量，并不需要额外的信息。基于真实软件定义网络进行了实验，结果显示该安全系统实现了较高的检测准确率，并且实现了理想的处理时间。未来将考虑在实际大规模软件定义网络中进行实验，评估本系统的有效性与性能。

# 参考文献：

[1]Saied A,Overill R E,Radzik T.Detection of known and unknown DDoS attacks using artificial neural networks [J]. Neurocomputing, 2016,172 (C):385-393.   
[2]KoliasC,Kambourakis G, Stavrou A,et al.DDoS in the IoT:mirai and other botnets [J].Computer,2017,50(7):80-84.

[3]王蒙蒙，刘建伟，陈杰，等．软件定义网络：安全模型、机制及研究进展[J].软件学报，2016,27(4):969-992.(Wang Mengmeng,LiuJianwei, Chen Jie,et al. Software defined networking:security model,threats and mechanism [J]. Journal of Software，2O16,27 (4):969-992.)

[4] 王秀磊，陈鸣，邢长友，等．一种防御DDoS攻击的软件定义安全网 络机制[J]．软件学报,2016,27(12):3104-3119.(Wang Xiulei,Chen Ming,Xing Changyou,et al. Software defined security networking mechanism against DDoS attacks [J].Journal of Software,2016,27 (12):3104-3119.)   
[5] 姚琳元，董平，张宏科．基于对象特征的软件定义网络分布式拒绝 服务攻击检测方法[J].电子与信息学报,2017,39(2):381-388.(Yao Linyuan,Dong Ping，Zhang Hongke.Distributed denial of service attack detection based on object character in software defined network [J].Journal of Electronics & Information Technology,2O17,39 (2): 381-388.)   
[6]肖甫，马俊青，黄洵松，等.SDN 环境下基于KNN的 DDoS攻击检 测方法[J]．南京邮电大学学报：自然科学版,2015,35(1):84-88. (Xiao Fu,Ma Junqing,Huang Xunsong,et al.DDoS attack detection based on KNN in software defined networks [J]. Journal of Nanjing University of Posts and Telecommunications ：Natural Science,2015, 35 (1): 84-88.)   
[7]Dong P,Du X, Zhang H,et al.A detection method for a novel DDoS attack against SDN controllers by vast new low-traffic flows [C]/ Proc of IEEE International Conference on Communications.2016:1-6. VNDD   
[8]Kalkan K,Gur G, Alagoz F. Defense mechanisms against DDoS attacks in SDN environment [J]. IEEE Communications Magazine,2017,55 (9): 175-179.   
[9] 杨君刚，王新桐，刘故箐．基于流量和 IP 熵特性的 DDoS 攻击检测 方法[J].计算机应用研究,2016,33(4):1145-1149.(Yang Jungang， Wang Xintong,Liu Guqing. DDoS attack detection method based on network traffic and IP entropy [J].Application Research of Computers, 2016,33 (4): 1145-1149.)   
[10] Sulak V, Helebrandt P,Kotuliak I. Performance analysis of OpenFlow forwarders based on routing granularity in OpenFlow 1.O and $1 . 3 \ [ \mathrm { C } ] / I$ （20 Proc of Open Innovations Association. 2017: 236-241.   
[11] Davis JV,Kulis B,Jain P,et al. Information-theoretic metric learning [C]// Proc of International Conference on Machine Learning.2007: 209-216.   
[12] Cuturi M,Vert J,Birkenes O,et al.A kernel for time series based on global alignments [C]// Proc of IEEE International Conference on Acoustics, Speech and Signal Processing. 2006: II-413-II-416.   
[13] Luxburg U V.A tutorial on spectral clustering [J]. Statistics& Computing,2007,17 (4): 395-416.