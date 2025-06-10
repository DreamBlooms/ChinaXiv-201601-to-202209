# 社交网络中基于网络结构支撑模型的谣言传播研究

王路帮1，李守伟²

(1．浙江万里学院，浙江 宁波 315100;2．山东师范大学，济南 250014)

摘要：社交网络中节点及其之间的关系构成一种网络结构，这种结构形成了节点之间的支持和被支持关系。结合结构支撑理论，探究节点网络结构支持力的一些性质，提出了社交网络结构中的全网支持力和被支持力的总量一致性，并进一步提出计算节点支持力的方法。谣言作为特殊信息，在支持力不同节点之间的传播特性有所不同，借鉴随机游走模型中的 PageRank 计算方法，对不同节点支持力的谣言传播以及传播后的辟谣状况进行了仿真模拟，结果表明支持力不同的节点对于谣言传播和辟谣影响明显。

关键词：社交网络；网络结构；结构支撑；PageRank；谣言传播中图分类号：N949 doi:10.3969/j.issn.1001-3695.2018.04.0229

# Rumor spreading based on network structural supportiveness model in social network

Wang Lubang1,Li Shouwei² (1.Zhejiang Wanli University,Ningbo Zhejiang 3151oo,China;2.Shandong Normal University,Jinan250014,China)

Abstract:The purposeis to explore the nodes supportivenessproperties insocial network basedon the network structural supportiveness model (NSsM），and therumor propagation characteristicsunder the different modessupportivenes. Combined withthestructuralsupportheory,this paperprobedintosomepropertiesof thenetworkstructure.Afteritdscribed the definitionofsupportivenessput forward theconclusionthatte total network supportivenessandRe-supportivenessare equal in MSSN,thenitproved thisconclusionbyusing formula.WiththereferenceofthePageRank calculation method inthe random walk model,itimplementedananalogue simulationabout therumorsspreadingofdifferent nodes supportiveness,as well as therumorrefuting situation.The resultsshow that diferent nodes supportiveness has diferent propagation characteristics and different supportiveness of node has significant impact on the rumor infection and recovery.

Key words: social network; network structure; structural supportiveness; PageRank; rumor spreading

# 0 引言

人在社交网络上的行为是现实行为的某种映射，而网络因为其自身的快速传播特性导致某些行为在网络上会产生巨大的负面作用，如谣言传播。研究社交网络的文献很多，WATTS和STROGATZ通过随机重连将规则网络变化为小世界网络，计算表明社交网络具有一定的小世界特征[1]。BARABASI和ALBERT发现了某些网络的无标度特性，少数节点具有大量的连接而大量节点连接很少的特性，将这种度分布符合幂律分布的网络定义为无标度网络[2]。现实中的社交网络和基于互联网的虚拟社交网络一般都有这种无标度特征。研究社交网络的拓扑结构是深入分析社交网络特性和规律的有效方法，大量的学者研究社交网络的拓扑结构问题，包括度分布、聚类系数、群聚系数、顶点度、相关系数等网络属性[3\~6]。文献 $[ 7 \sim 9 ]$ 从节点度以及与之相关的节点影响力的角度进行社交网络的相关研究。文献[7]根据社交网络中节点出度和入度的不同情况研究信息传播的效果。文献[8]说明了在线社交网络中信息节点度一般都具有负的相关性。文献[9]通过利用社交网络中节点影响力来进行社交网络的社团划分，通过研究基于社团划分的信息分级隐私保护策略，以提升信息的可用性，增强核心节点的保护。这些基于社交网络结构的研究方法，能够从底层深刻刻画各种信息传播的底层架构，为基于其上的信息传播演化规律提供研究基础。

社交网络的信息(各种舆论)会从一些所谓自媒体的个体中产生而上传到社交圈，之后会在社交网络的好友圈不断传播、演绎。在研究网络信息传播的文献中，有类问题值得进一步探讨。在信息传播过程中，到底是因为节点自身的信息优势（诸如个人魅力，或者拥有信息解释的权威），还是节点所处于网络结构的重要位置。基于此，部分学者从网络结构的角度来分析信息传播的规律性。文献[10]提出了随机游走模型PageRank。PageRank根据其所在网络特点和分析目标的不同，也产生了一些变种，如判断节点间距离的RWRS以及结合话题主题的随机游走模型等[11,12]。在以网络结构为角度的相关研究中，超图作为工具也被利用在舆情的传播扩散研究中。现实中的个体存在于多个密切联系的社会关系网络中，个体的信息传播受制于各种不同社会关系网络，而利用基于超图的超网络实现对这种多类型网络结构的刻画，并在此基础上引入流行病学传播模型实现舆情的传播研究，揭示超网络中舆情传播的规律和态势[13]。

谣言作为特殊信息，其传播的特性和控制的方法都与普通的信息有所不同。文献[14,15]利用社交网络中的聚类系数来研究谣言传播的一些规律。文献［14］在经典谣言传播模型的基础上，研究了具有幂律度分布和可变聚类系数的无标度网络上的谣言传播行为。结果表明，聚类系数越高的网络，越有利于抑制谣言的传播。文献[15]中将复杂网络的聚类系数作为参量进行社交网络谣言传播的仿真研究，通过仿真研究发现，谣言的传播能力与影响范围会随着初始传播节点的度的增大而增大，但会随着网络聚类系数的增加而得到抑制。文献[16]构建了两阶段的A-SC1C2IR模型并得出模型的动态方程。仿真结果表明，权威信息过早干预能够有效控制微博谣言的传播。文献[17]对于信息在虚拟社区和博客中的传播规律进行分析，博客传播的环境有社交网络的某种特性，可以把博客网络看做是基于每个博主节点的社交网络。文献[18]在借鉴传染病动力学模型的基础上，引入用户行为分析和接触节点，提出基于用户行为分析的SCIR模型，分析微博社交网络中节点之间的关联和演化。在考虑网络结构影响谣言传播中，文献[19]基于社团结构和K-shel1节点法构造影响力判别值来分析单感染源的传播问题。考虑到K-shell分解法存在着得到大量相同ks值，对该方法作出改进，提出基于节点所处不同社团结构的ks值区分法，定义一种新的节点影响力判别值（Nc值），以此识别ks值相同的节点的不同影响力。通过单感染源的 SIR 模型进行仿真，发现Nc值较高的节点不仅最终节点的影响范围较大，传播速度也快于其他节点[19]。文献[20]提出了一种网络结构支撑模型，用于刻画社交网络中节点的重要性。这种模型很好地量化解释了网络结构中成员的影响程度。本文探讨基于网络结构支撑理论的社交网络节点关系，结合文献[10,20]中的基本观点，进一步探究节点支持力的一些重要特性，并结合社交网络中谣言传播基本规律的基础上，探讨不同支持力节点谣言传播的一些特性。相关研究工作为研究谣言、管理谣言以及控制谣言传播提供一定的参考借鉴。

# 1 网络结构支撑模型

# 1.1节点影响度

节点影响度反映了网络 $G = ( V , E )$ 中节点 $u , \nu \in V$ 在整个图中的相对重要性指标。定义抽象函数 $\lambda _ { G } ( \nu )$ 表达节点 $\nu \in V$ 的影响度。

定义1节点影响度函数 $\lambda _ { \scriptscriptstyle G } ( \nu )$ 定义为从节点 $\nu \in V$ 指向实数 $R$ 的函数。文献[10]中利用PageRank 实现度量 $\lambda _ { \scriptscriptstyle G } ( \nu )$ 的赋值。在文献[21]中，利用节点重要性打分函数，用PageRank和 TwitterRank 实现节点 $\nu$ 的 $\lambda _ { \scriptscriptstyle G } ( \nu )$ 函数赋值。

这里不妨利用文献[10]的方法来刻画节点u的影响度函数$\lambda _ { \scriptscriptstyle G } ( \nu )$ 为 $\lambda _ { \scriptscriptstyle P R } ( u )$ ：

$$
\lambda _ { \mathit { P R } } ( u ) = \frac { 1 - \varepsilon } { \left| V \right| } + \varepsilon \sum _ { \nu \in M ( u ) } \frac { \lambda _ { \mathit { P R } } ( \nu ) } { d ( \nu ) }
$$

PageRank利用概率转移的思想，节点 $\nu$ 的PageRank取值均分，转移给其所指向的节点。一个节点 $u$ 的PageRank取值$\lambda ( u )$ 取决于其受到的转移量之和。 $M ( u )$ 表示指向节点 $u$ 的节点集合， $d ( \nu )$ 表示节点 $\nu$ 的出度。 $\lambda _ { \scriptscriptstyle P R } ( u )$ 的数值度量了节点 $u$ 在网络 $G = ( V , E )$ 中的影响力大小，一般来说，影响度值大的节点其受访的概率就会大些。

# 1.2个体支持力函数

利用文献[20]的方法，对依赖度、支持力和K支持力进行定义说明。

定义2 依赖度。对于图 $G = ( V , E )$ ， $u , \nu \in G \land u \neq \nu$ ，定义 $u$ 对 $\nu$ 的依赖度函数$\omega ( \nu  u ) = \frac { | \lambda _ { G } ( u ) - \lambda _ { G - \nu } ( u ) | } { \lambda _ { G } ( u ) }$ 依赖度函数 $\omega ( \nu  u )$ 表明在原图 $G$ 中，除去节点 $\nu \in V$ 前后， $u$ 的节点度量函数$\lambda _ { \scriptscriptstyle G } ( u )$ 发生变化的相对情况。也可以理解为原图中节点 $\nu$ 对节点 $u$ 的支撑程度。除去节点 $\nu$ 后，度量函数 $\lambda _ { \scriptscriptstyle G } ( u )$ 相对变化越大，这种支撑越明显。

依赖度可以理解为衡量节点间亲疏关系的一种度量标准，$u$ 对 $\nu$ 的依赖度越大，或者 $\nu$ 对节点 $u$ 支持力度大，说明 $\nu$ 与$u$ 之间的关系越亲近；反之，就表明两者关系越疏远。对于两个节点 $\nu$ 和 $u$ ， $u$ 对 $\nu$ 的依赖可以理解为 $\nu$ 对 $u$ 的支持，一个节点被其他节点依赖的程度，可以理解为这个节点的“给力”程度。

在依赖关系 $G = ( V , E )$ 中，对于 $\nu \in V$ ，的最近邻集合，表示为 $N N ( \nu )$ ， $N N ( \nu )$ 可以表示为

$$
\left\{ u \in V { \left| { \neg \exists u ^ { \prime } \in V , s t , \omega ( u ^ { \prime } \to \nu ) > \omega ( u \to \nu ) } \right. } \right\}
$$

从定义可知， $N N ( \nu )$ 表示为对节点一支持力最大的所有点的集合。

$\nu \in V$ 的反向最近邻，表示为 $R N N ( \nu )$ ， $R N N ( \nu )$ 可以定义为：RNN $( \nu ) = \{ u | \nu \in N N ( u ) \}$

从定义可知， $R N N ( \nu )$ 表示为可以以节点一为近邻的所有节点集合。

定义3 支持力。在图 $G = \left( V , E \right)$ 中， $u \in V$ 的支持力表示为

$\operatorname* { s u p } { p ( u ) } = \sum _ { \nu \in R N N ( u ) } \frac { 1 } { \left| N N ( \nu ) \right| }$ 对支持力的进一步扩展，有 $k$ 支持力的概念。

定义4 $k$ 支持力。在图 $G = \left( V , E _ { \omega } \right)$ 中，节点的 $k$ （204  
支持力表示为： $\mathit { S U P P } _ { k } ( u ) = \sum _ { \nu \in \mathit { R k N N } ( u ) } \frac { k } { \left| k N N ( \nu ) \right| }$ 节点的支持力 $S U P P _ { k } ( u )$ ，所代表的是节点 $u$ 的社交能量,  
$S U P P _ { k } ( u )$ 越大的节点在社交网络中产生的影响一般越大。

# 1.3支持力计算

考虑到社交网络中节点支持力的计算问题，需要通过查找节点 $u$ 的 $R k N N ( u )$ ，给问题解决带来一定的困难。本节通过定义被支持力，之后证明一个定理，并在基于定理的基础上实现节点支持力的一种计算方法。

定义5 $k$ 被支持力。在图 $G = \left( V , E \right)$ 中，节点 $u \in V$ 的$k$ 被支持力表示为： $R S U P P _ { k } ( u ) = \sum _ { \nu \in k N N ( u ) } \frac { k } { \left| k N N ( \nu ) \right| } \circ$

在社交网络中 $R S U P P _ { k } ( u )$ 表示节点 $u \in V$ 的被影响程度，通常 $R S U P P _ { k } ( u )$ 越大，说明节点 $u$ 在社交网络中被其他节点影响的时机越多，越有可能被其他节点的信息（或消息）所影响。

定理1在图 （20 $G = \left( V , E \right)$ 中，

$$
\sum _ { u \in V } R S U P P _ { k } ( u ) \mathop { { \sum } } _ { \nu \in V } S U P P _ { k } ( \nu ) \mathop { { \circ } } _ { \circ }
$$

定理的意思是说社交网络图 $G = \left( V , E _ { \omega } \right)$ 中，所有节点被支持的总和量和所有节点支持其他点的总和量相同。

# 证明

$\begin{array} { r l } { \displaystyle \sum _ { u \in V } S U P P _ { k } ( u ) \quad = \quad } & { \displaystyle \sum _ { u \in V } \left( \displaystyle \sum _ { v \in R \land N ( u ) } \frac { k } { \left| k N N ( v ) \right| } \right) \quad = } \\ { \displaystyle \sum _ { u \in V } \displaystyle \sum _ { v \in R \land N ( u ) } \frac { k } { \left| k N N ( v ) \right| } \quad \quad - \quad } & { \displaystyle \sum _ { u \in V } S S U P P _ { k } ( u ) \quad \quad - } \\ { \displaystyle \sum _ { u \in V } \left( \displaystyle \sum _ { v \in R \land N ( u ) } \frac { k } { \left| k N N ( v ) \right| } \right) = \displaystyle \sum _ { u \in V } \displaystyle \sum _ { v \in R \land N ( u ) } \frac { k } { \left| k N N ( v ) \right| } } \end{array}$ 从 $N N ( \nu )$ 和 $R N N ( \nu )$ 的定义$\begin{array} { r } { N N ( \nu ) = } \end{array}$ $\left\{ u \in V { \left| { \neg \exists u ^ { \prime } \in V , s t , \omega ( u ^ { \prime } \to \nu ) > \omega ( u \to \nu ) } \right. } \right\}$ 以及RNN $( \nu ) = \{ u | \nu \in N N ( u ) \}$ 可得：

$\forall \nu i \in V$ ，假如 $\nu _ { k } \in M N ( \nu i )$ ，那么一定有$\nu i \in R M N ( \nu k )$ 。也就是 $V$ 中任意两个节点的近邻关系是对应的。同理 $K M N ( \nu )$ 和 $K R N N ( \nu )$ 也具有同样的性质。

有此可得

$\sum _ { u \in V } \sum _ { \nu \in R k N N ( u ) } \frac { k } { \left| k N N ( \nu ) \right| } =$   
$\sum _ { u \in V } \sum _ { \nu \in k N N ( u ) } \frac { k } { \left| k N N ( \nu ) \right| }$   
也就是 $\sum _ { u \in V } R S U P P _ { k } ( u ) _ { = } \sum _ { \nu \in V } S U P P _ { k } ( \nu )$ 。定理得证。

根据定理1，计算支持力 $S U P P _ { k } ( u )$ 可以通过计算$R S U P P _ { k } ( u )$ 来实现，这样的好处是，只需用在 $V$ 中计算每个点的邻居NN $( \nu )$ 对其的支持情况，而不需要计算每个点的逆邻居RNN $( \nu )$ 。考虑到节点的数量一般需要计算机来实

现 $R S U P P _ { k } ( u )$ 的计算。

# 2 基于支持力的谣言传播仿真分析

# 2.1谣言传播状态和基本过程

谣言传播是社交网络信息传播的一种特殊情况。因为谣言自身敏感性，其传播的速度一般会快于普通的信息，当辟谣信息公布后，谣言的影响力又会得到一定程度消弱和消灭。在研究谣言传播的文献中，很多借鉴Kermack和McKendrick(1927)提出的经典的 SIR 传染病模型。一般用S（susceptible）、I（infective）、R（recovered）代表三种传播状态，这三种状态的转换关系如图1所示。

![](images/dafb275cbf3881981f1110138fe5703d2fc2a440ef08876ecf08129f61ef3b60.jpg)  
图1经典的传染模型SIR状态变化

而实际上，谣言传播的特性和传染病有很大不同，如从感染节点I到免疫节点R的转变方面。传染病只需用个体自身的免疫力，随时间变化个体就会按概率实现转换。但谣言的传播节点的转换一般需要免疫信息（如权威辟谣信息）的干预才可以实现转变。当然，在S到I的转换过程中，两者也有很大区别，比如传染病中两者的转换是根据空间接触性，但在谣言传播中是根据节点之间的关联性。结合实际情况，确定社交网络谣言传播的基本转换规则。

节点V在健康状态、传播状态和免疫状态之间的转移不仅依赖于节点自身的状态，还与它的邻居节点的状态相关。定义以下传播规则：

a）如果一个健康节点S与一个传播节点I接触，则健康节点会以概率 $p _ { 1 }$ 转换为传播节点 $I$ 。b)传播节点I遇到免疫节点 $R$ 会以概率 ${ { p } _ { 2 } }$ 转换为免疫节点。c）谣言来自于外部，并注入到某个点 $\mathrm { v _ { j } }$ ，使得$\mathrm { V _ { j } } ( S ) \mathrm { \to V _ { j } } ( I )$ ，或者说，没有外部的注入，封闭的社交网络没有所谓的谣言。同样，辟谣信息也来自于外部注入。

基于SIR三状态的谣言传播关系如图2所示。

SP[在与I状态节点相邻情况下]Ip2[在与R相邻情况下1R

# 2.2谣言传播仿真样本抽取和实验

# 2.2.1构造基本网络结构

在微博或twitter中，博主作为社交网络节点，节点之间基于"订阅一分发"模式传播信息，节点之间的关注和评论，对于信息影响力的放大没有明显的效果，所以本文选择"转发"作为微博或twitter节点之间关联确定。转发行为造成了信息的二次传播，体现了信息影响力的放大和"支撑"效果。

构造基本网络结构。基于社交网络的现实情况，构造双向无权属性图 $\mathbf { G } ( \mathsf { V } , \mathbf { A } , \mathbf { E } )$ ，其中 $\mathrm { \Delta V }$ 表示该图的节点集合$\mathsf { V } = \left\{ V _ { i } \big | i \in N \right\}$ ；而E为边 $\mathrm { E } =  \overline { { V _ { i } V _ { j } } } | i , j \in N \wedge i \neq j $ 的集合， $\overline { { V _ { i } V _ { j } } }$ 表示 $V _ { i }$ 和 $V _ { j }$ 有边相联系，或者说两者之间信息是通联的，当 $V _ { i }$ 与 $V _ { j }$ 两个节点之间有关注或被关注关系时，这两个节点之间就存在一条关联的有向边，分别用 $\vec { V _ { i } V _ { j } }$ 表达$V _ { j }$ 关注 $V _ { _ i }$ 节点，用 $V _ { i } ^ {  } { } _ { V _ { j } }$ 表达 $V _ { _ i }$ 关注 $V _ { j }$ 节点，用 $\overset  { V _ { i } V _ { j } }$ 表达$V _ { i }$ 和 $V _ { j }$ 互相关注。而A为图 $\mathbf { G }$ 中节点 $\mathrm { \Delta V }$ 的属性集合，定义属性集合为： $\mathbf { A } = \left\{ S , I , R \right\}$ 。其中：S为易感状态[susceptible];I为传播状态[infective]；R为免疫状态[recovered]。在信息传播中，S为信息接受易感个体，I为信息传播个体，R为对信息传播有免疫力的个体。

这样，图 $\mathbf { G } ( \mathsf { V } , \mathbf { A } , \mathbf { E } )$ 就是节点 $\mathrm { ~ V ~ }$ 带有S、I、R三种可能属性，并含有节点间有向边E的网络节点集合。

# 2.2.2仿真数据分析

1）众多节点形成的无标度网络特性

用上小节的办法，选取新浪微博10586个节点，在一个时间段内统计得出26836个转发，根据节点之间的关注和被关注关系确定节点之间的有向边关联。利用上面基础数据得到节点度的分布情况，节点直接的出度和入度没有区分的统计在一起，如图3所示。

![](images/50c9c47fc61fe17da06e5b9580a19f5aa5cdcf919a80f0b9cdff7332cf0de65c.jpg)  
图2社交网络谣言传播中节点状态转换关系  
图3案例节点度分布情况

利用文献[8]的随机游走模型计算节点的PageRank值，由此进一步按照1.3节的计算节点支持力的计算方法实现节点支持力的计算和统计分析，如图4所示。

![](images/57b1496c0c53a016b660867ca69bea3336b4bc93274fe89679c789a8315ef541.jpg)  
图4节点支持力分布情况对数图

从上面的数据分析可以看出，在新浪微博的客户关系中，节点度和支持力服从一定的幂率分布特性，大部分节点的度和支持力都很小，极少数节点的度和支持力的比较大。

# 2）最大支持力K个节点传播的特性

选择节点支持力最高的5个节点（这完全是实验研究的方便，不是一定要5个），注入谣言，这5个节点在时间步为0的时刻状态定格为I状态。之后与这5个节点相关联的节点（关注这5个节点的节点），按照模型中转换的概率 $p _ { 1 }$ 实现状态 S到I的转换，其转换过程如图5所示。

![](images/eb96264d419b3cf2d4785152b4e18619a030b4917152eeb8fd64372bd67e4a45.jpg)  
图5节点支持力不同的点注入谣言后的演化图

图中\*号代表支持力大的5个节点，而 $^ +$ 号代表支持力较小的节点。在系统中节点谣言全感知后，系统注入辟谣信息后，系统的演化会发生什么情况呢。选择支持力最高的10个节点，注入辟谣信息，这10个节点在时间步为0的时刻状态定格为R状态。之后和这10个节点相关联的节点（关注这10个节点的节点）按照模型中转换的概率 ${ { p } _ { 2 } }$ 实现状态I到R的转换，其转换的过程如图6所示。在图6中，\*号代表支持力大的5个节点，而 $^ +$ 号代表支持力较小的节点。仿真实验表明，支持力较大的节点明显更快地实现了对谣言信息的免疫控制一一免疫节

点的增加速度较快。

![](images/cbae18193be81a69ce33cf5aa38a5901bb1857b8b5b78b2b7000d529c429cc2b.jpg)  
图6节点支持力不同的点注入辟谣信息后的演化图

# 3 结束语

本文在社交网络结构支撑模型的基础上，在定义分析系统支持力和被支持力的概念的基础上，通过证明在整个系统内两者的等价性，由此实现系统不同节点支持力的计算。在面向样本社交网络群体的所有个体中，选择支持力相对较大和相对较小节点进行谣言传播和辟谣过程的仿真实验分析，数据说明支持力不同节点在传播谣言和辟谣的作用方面差距明显。后续的研究可以更深入地开展面向所有个体的传播差异性研究，这种支持力的差异性在分布上的特性以及由此产生的谣言传播影响差异性都值得深入研究。另外，在结构支撑模型基础上的谣言传播中的更多参量值得进一步深度分析，比如谣言各种状态的转换系数，以及SIR之外的可能有的更多中间状态值得进一步分析。相关的研究正在持续开展中。

# 参考文献：

[1]Watts D J, Strogatz S H. Collective dynamics of small-world networks [J]. Nature,1998,393 (6684): 440-442.   
[2]Barabasi AL,Albert R.Emergence of scaling in random networks [J]. Science,1999,286 (5439): 509-512.   
[3]Kumar R,Novak J,Tomkins A.Structure and evolution of online social networks [C]//Pcoc of the 12th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.2006.   
[4]Hu H,Wang X.Evolution of a large online social network [J].Physics Letters A,2009,373(12-13):1105-1110.   
[5]Mislove A,Marcon M,Gummadi KP,et al.Measurement and analysis of online social networks [C]//Pcoc of the 7th ACM SIGCOMMConference on Internet Measurement.2007.   
[6]Chun H,Kwak H,Eom YH,et al. Comparison of online social relations in terms of volume Vs.interaction: a case study of Cyworld [C]//Pcoc of the 8th ACM SIGCOMM Conference on Internet Measurement.2008.   
[7]张凌，罗曼曼，朱礼军．基于社交网络的信息扩散分析研究[J].数据

分析与知识发现,2018,14(2):46-57.(Zhang Ling,Luo Manman,Zhu Lijun.Analyzing information dissemination on social networks [J].Data Analysis and Knowledge Discovery,2018,14(2): 46-57.)

[8]Fu F, Chen X,Liu L,et al. Social dilemmas in an online social network: the structure and evolution of cooperation [J].Physics Letters A,2007, 371 (1-2): 58-64.

[9]陆 越，陈秀真，马进．融合社团划分的社交网络分级隐私保护算法[J]通信技术，2018，15(2):404-412.(Lu Yue,Chen Xiuzhen，Ma Jin.Hierarchical privacy protection algorithm for social network based oncommunity division [J].Communications Technology，2018，15 (2):404-412. )

[10] Page L,Brin S. Motwani R,et al. The PageRank citation ranking: bringing order to the Web,Technical Report SIDL-WP-1999-0120 [R].[S.1.]: Stanford University,1999.

[11] Fujiwara Y,Nakatsuji M, Onizuka M,et al.Fast and exact top-k search for random walk with restart [C]//Proc of the 38th Very Large Data Base. 2012.

[12] Zhou Guangyou,Liu Kang,Zhao Jun. Topical authority identification in community question answering [C]// Proc of the Chinese Conference on Pattern Recognition.2012.

[13]索琪，郭进利.超网络中的舆情传播模型及仿真研究[J].计算机应用研究,2017,34 (9): 2629-2632.(Suo Qi,Guo Jinli. Spreading model andsimulation analysis of Internet public opinion in hypernetworks [J].Application Research of Computers,2017,34(9): 2629-2632.)

[14]潘灶烽，汪小帆，李翔.可变聚类系数无标度网络上的谣言传播仿真研 究[J]．系统仿真学报，2006，18(8):2346-2348.(Pan Zaofeng Wang Xiaofan Li Xiang. Simulation investigation on rumor spreading on scale-free network with tunable clustering [J].Journal of System Simulation,2006,18(8): 2346-2348.)

[15]朱张祥，刘咏梅．在线社交网络谣言传播的仿真研究—一基于聚类系 数可变的无标度网络环境[J]．复杂系统与复杂性科学，2016,13(2):   
74-82.(Zhu Zhangxiang,Liu Yongmei. Simulation study of propagation of rumor in online social network based on scale-free network with tunable clustering [J]. Complex Systems and Complexity Science,2016,13 (2):   
74-82.) [16]宋之杰石蕊王建.权威信息发布对突发事件微博谣言传播的影响 研究[J].情报杂志,2016,35(12): 41-47.(Song Zhijie,Shi Rui,Wang Jian.Influence of authoritative information release on rumors microblog spreading in emergency events [J]. Journal of Intelligence,2016,35 (12):   
41-47. ) [17] Java A,Kolari P,Finin T,et al.Modeling the spread of influence on the blogosphere [Cl// Proc of the 15th International World Wide Web Conference.2006. [18]郑志蕴，郭芳，王振飞，等．基于行为分析的微博传播模型研究[J]. 计算机科学，2016,43（12):41-46.(Zheng Zhiyun,Guo Fang，Wang Zhenfei,et al. Study on microblog propagation model based on analysis of user behavior [J].Computer Science,2016,43(12): 41-46.) [19]朱晓霞，赵雪，刘萌萌．基于社团结构的节点的影响力分析[J].计算 机应用研究，2017,34(9):2582-2585.(Zu Xiaoxia,Zhao Xue,Liu Mengmeng. Analysis of influential node based on community structure [J]. Application Research of Computers,2017,34(9):2582-2585.) [20]韩 毅，许 进，方滨兴，等．社交网络的结构支撑理论．计算机学报,   
2014,37 (4): 905-914. (Han Yi,Xu Jin,Fang Binxing,et al. Structural supportiveness theory on social networks [J].Chinese Journal of Computers,2014,37 (4): 905-914.) [21] Weng Jianshu,Lim E P,Jiang Jing，et al.TwitterRank:finding topic-sensitive influential twitterers[C]//Procof the3rd ACM International Conference on Web Search and Data Mining.2010.