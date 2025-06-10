# 无线网络干扰最小化问题的一种缩边贪心算法

杜磊'，付喜梅²，杨文瀚

(1．华南师范大学 计算机学院，广州 510631;2．韶关学院 数学与统计学院，广东 韶关 512005)

摘要：无线传感器网络的最大干扰最小化问题可以被描述为已知平面上n个点的位置及发射半径的阈值，要求设置发射半径使得任意点被其他点发射范围覆盖的最大数量达到最小。为了有效求解该问题，提出了一种新的贪心算法——缩边算法。不同于已有算法的构图方式，该算法是通过采取缩边的方式，构造网络通信拓扑图，并结合了操作系统中批量处理的思想对贪心算法进行了加速，缩短了算法的运行时间。通过实验验证，该算法相比于已有算法在随机产生的算例上能产生更优的解。

关键词：无线传感网络；贪心算法；干扰最小化；批量处理；连通图；缩边策略 中图分类号：TP301 doi:10.19734/j.issn.1001-3695.2018.10.0804

# Edge shrinking greedy algorithm for minimizing interference in wireless networks

Du Lei1, Fu Ximei², Yang Wenhan1 (1.SchoolofComputer,outhChinaNormal University,Guangzhou510631,China;2.SchoolofMathematics&Statistics, Shaoguan University,Shaoguan Guangdong 512005,China)

Abstract:The problem of minimizing the maximum interference in wirelesssensor networks can be described as follows: given npoints with their positions onthe plane and thresholds oftransmisionranges,for each point,the maximum number of other points whose transmission ranges cover this point is minimized.To effectively solve this problem,this paper proposeda new greedy algorithm caled edge shrinking algorithm.The algorithm constructs a desirable network communicationtopologybyshrinking edges,which is different from existing algorithms andisacceleratedbyincorporating theidea of batch processing in operating system to shorten its running time.Theresult shows thatthis algorithm can produce better solutions than existing algorithms.

Key words:wireless sensor network；greedyalgorithm;interference minimization;batch procesing;connected graph; shrinking strategy

# 0 引言

无线传感器网络（wirelesssensornetwork,WSN）是由大量的静止或移动的传感器以自组织和多跳的方式构成的无线网络，以协作地感知、采集、处理和传输网络覆盖地理区域内被感知对象的信息，并最终把信息发送给网络的所有者。无线传感器网络具有的众多类型的传感器，可探测包括地震、电磁、温度、湿度、噪声、光强度、压力、土壤成分、移动物体的大小、速度和方向等周边环境中多种多样的现象[1,2]。

无线传感器网络一般部署在人们不方便直接控制的地方！而且传感器节点一般使用的是电池，很难重新充电或者更换电池，因此能源成为制约无线网络服务时限的关键因素之一[3]。节省节点能源的一种方法是减少附近节点同时传输信号所产生的干扰。

目前减少干扰的方法有频率分配多路技术、时间分配多路技术和拓扑控制三种。前面两种方法虽然都可以有效地减少干扰，但是要求较高的技术和成本，而拓扑控制是通过给每个节点分配一个合理的发射半径并形成一个连通的拓扑，并且减小半径的某个目标函数使网络的最大干扰最小。因此，在无线传感器网络中，拓扑控制成为了减少干扰的重要方法之一[4]，也是近年来的一个研究热点。

在平面上计算无线传感器网络的最大干扰最小化并保持网络的连通已经被证明是NP难度的[5]，因此要在多项式时间内找到精确的解是困难的。文献中求解该问题的算法并不多，典型的有如下几种：2008 年，Halldorsson 提出的结合了计算几何和ε-网络理论的近似算法[6]，其最大干扰是 $\varDelta ^ { 0 . 5 }$ ，其中4是发射半径相同的网络中节点最大度。同年又有学者证明了任何能够产生连通图的传输半径函数都可以修改为具有以下特点的半径函数.其产生的拓扑结构干扰基本不变，且所有传感器节点的发射半径小于 $R _ { m i n }$ ， $R _ { m i n }$ 为保持网络强连通的最小可能半径[7]。2009年，又有人提出基于每个节点与最近邻居关系的最近邻算法[8]。2010，Aslanyan 等人提出了一种基于部分成员集合覆盖的近似算法[9]。2014年，有人基于Prim 算法提出了一种时间复杂度为 $O ( n ^ { 2 } )$ 的最佳邻算法[10]。之后又有人尝试在最佳邻算加入了后悔机制[11,12]，在适当增加时间的前提下，一定程度上提高了算法的精确度。

本文考虑了用拓扑控制方法来减少平面中无线传感器网络中最大干扰的最小值，提出了一种不同于已有算法构图方式的新的贪心算法，并在大量的随机算例上验证其有效性。

# 1 问题模型以及相关算法

针对无线通信中减少干扰的问题现已提出多个不同的模型[13]。其中有一种是以发送者为中心的模型，在此模型中干扰指的是边的干扰。另一种以接收者为中心的模型中，干扰指的是点的干扰，任意一点 $\nu$ 的干扰定义为传输范围可覆盖$\nu$ 的其他节点的数量。以发送者为中心的模型只考虑了发送者但实际干扰发生在接受者上，模型不能反映真实的情况。在本文中采用以接收者为中心的模型，通过拓扑控制来设计以接受者为中心模型的无线传感器网络中干扰最小化问题的有效算法。

本文中将使用图论的知识来描述问题模型，因此需要了解一些相关的概念。由于将无线传感器网络建模为图，所以本文中的“图”和“网络”是通用的。关于图的相关概念可以参看相关文献[14]。下面给出相关的概念，然后给出形式化的定义并介绍最小干扰化模型。

平面中的无线传感器网络可以描述为节点的集合，在集合中的每个点 $i$ 都有一个二维坐标 $( x ( i ) , \ y ( i ) )$ ，并且满足其半径函数 $r ( i ) \in [ 0 , R ( i ) ]$ ，其中 $R ( i )$ 是该节点的半径阈值。因此，对于传输半径函数 $\boldsymbol { r }$ 所导出的所有节点的传输关系可以建模为一个图 $G _ { r } { = } { < } V , E _ { r } { > }$ 。对于 $\boldsymbol { V }$ 中的任意两点 $\boldsymbol { u }$ 和 $\nu$ ，边 $( u , \nu )$ 存在当且仅当 $r ( u )$ 和 $r ( \nu )$ 不小于 $\mathbf { \Omega } _ { u }$ 和 $\mathbf { \sigma } _ { \nu }$ 的欧氏距离 $\boldsymbol { d } ( u , \nu )$ ，即$r ( u ) { \geq } d ( u , \nu )$ 且 $r ( \nu ) { \geq } d ( u , \nu )$ 。本文为了方便起见，将 $G _ { r } { = } { < } V , E _ { r } { > }$ 叫做传输半径函数的导出图，并作出以下定义。

定义1对 $V$ 中任意的两点 $u , \nu \in V$ ，经由传输半径函数 $\boldsymbol { r }$ 导出的任意点之间的传输关系记为图 $G _ { r } { = } { < } V , E _ { r } { > }$ ，边 $( u , \nu ) \in$ $E _ { r }$ 存在当且仅当 $u$ 和 $\mathbf { \sigma } _ { \nu }$ 的传输半径 $r ( u )$ 和 $r ( \nu )$ 不小于它们之间的欧氏距离 $d ( u , \nu )$ ，即 $r ( u ) { \geq } d ( u , \nu )$ 且 $r ( \nu ) { \geq } d ( u , \nu )$ 。因此，$G _ { r } { = } { < } V , E _ { r } { > }$ 称为传输半径函数 $\boldsymbol { r }$ 的导出图。

定义2导出图 $G _ { r } { = } { < } V$ ， $E _ { r } >$ 中任一点 $\nu$ 的干扰度定义为$I _ { r } ( \nu )$ ，表示发射半径能覆盖到节点 $\nu$ 的图中其点的个数，即

$$
I _ { r } ( \nu ) { = } { \big | } \{ u \in { V } \backslash \{ \nu \} { \big | } r ( u ) \geq d ( u , \nu ) \} { \big | }
$$

定义3导出图 $G _ { r } { = } { < } V , E _ { r } { > }$ 的干扰度 $I _ { r }$ 定义为图中所有点干扰度的最大值，即

$$
I _ { r } = \operatorname* { m a x } \{ I _ { r } ( \nu ) | \nu \in V \}
$$

根据定义2和3，图1中点 $\mathbf { \sigma } _ { \nu }$ 的干扰是3，导出图的干扰也是3。

![](images/0c9fe89e48ffdb66964792a8eae552d60c2af49f3901449c37518963baf37eed.jpg)  
图1最大干扰示意图  
Fig.1Example diagram of maximum interference

# 1.1干扰最小化模型

考虑到连通的最基本的要求，可以有下面的问题模型

最小干扰化问题（MIP）：给定平面中的一个节点集 $V$ $V$ 中的任意一点 $i$ 的坐标可表示为 $( x ( i ) , \ y ( i ) )$ 。对 $V$ 中的任意一点 $i$ 都有一个满足以下条件的传输半径阈值函数 $R ( i ) \in [ 0 , 1 ]$ 且导出图 $G _ { R } { = } { < } V , E _ { R } { > }$ 连通。因此需要确定一个传输半径 $\boldsymbol { r }$ 满足导出图 $G _ { r } { = } { < } V , E _ { r } { > }$ 是连通的且干扰最小的。

从上文的定义可知，对任意一个传输半径 $\boldsymbol { r }$ 都满足导出图 $G _ { r }$ 是导出图 $G _ { R }$ 的子图。而且，如果重新选择使节点 $\nu$ 到它在图 $G _ { r }$ 中距离最远的邻居的距离作为节点 $\mathbf { \sigma } _ { \nu }$ 的传输半径，最终的得到的导出图和导出图 $G _ { r }$ 有相同的干扰。因此，可以仅从节点 $\nu$ 与其在导出图 $G _ { R }$ 中可到达的邻居节点的不同距离中来选择 $\nu$ 的传输半径。通过这样的选择方式，节点 $\nu$ 的传输半径即导出图 $G _ { r }$ 中 $\nu$ 与可到达的距离最远的邻居的距离

MIP已经被证明是NP难度的，即使对于寻找所有节点都在一条直线上这种特殊的MIP的一个最优实例也是很困难的，尽管难度还没有被证明出来。对于二维网络的特殊情况，如网格网络，这个问题的难度也是NP难度的。MIP难度源于其组合结构，以至于从许多直观的特性，如最小度、最近的邻居、最好的邻居等特点，都不能产生令人满意的解。因此可以考虑设计贪心算法来解决这个问题。

# 1.2干扰最小化问题的典型算法

目前已有不少学者研究了干扰最小化问题，并提出了解决该问题的相关算法，本文主要介绍了介绍如下几种算法。

# 1.2.1最近邻算法(NNA)

贪心算法的基本思路是从问题的某一个初始解出发一步一步地进行，根据某个优化测度，每一步都要确保能获得局部最优解。在干扰最小化问题中，可直观地认为节点的传输半径越小则网络中的干扰越小。最近邻算法正是基于这样的直观特性，并且结合了最小生成树的思想，通过调整两个相邻最近的节点的传输半径来连通当前网络中不连通的两个连通分量。重复这个步骤，直至整个网络连通。

# 1.2.2 最佳邻算法(BNA)

最近邻算法在一般网络中的效果尚可，但是在特殊网络（指数链网络）中效果很差。针对最近邻算法的不足，文献[10]提出了改进的最近邻算法一一最佳邻算法。最佳邻算法的主要思想是：通过调整当前连通网络最大干扰增幅最小的节点对的传输半径来连通两个不连通的部分。重复上述步骤，直至整个网络连通。

最佳邻算法与最近邻算法的时间复杂度相当。但是大量的实验结果表明，最佳邻算法不仅能消除最近邻算法在特殊网络上的弊端，在普通网络上的效果也优于最近邻算法。

# 1.2.3后悔贪心算法(RGA)

Sun[12]在2017年提出了后悔贪心算法，其主要步骤遵循贪心算法的工作流程，并在贪心算法的每个迭代步尝试采用后悔策略。在贪心算法的每个迭代步中，如果当前网络的最大干扰发生了改变，即当前导出图的最大干扰增加后，将针对此时具有最大干扰的节点用后悔策略调整某些节点的已由贪心算法确定的传输半径来试图降低它的干扰，使得当前最大干扰减少。

# 1.2.4旋转贪心算法(CGA)

基于基本贪心算法 $G$ 的旋转贪心算法的主要思想是在贪心算法 $G$ 求得的可行解中选择一定比例的元素作为部分解。每次将部分解的第一个元素移除，通过贪心算法 $G$ 重新加入元素，更新部分解。重复这一步骤，直至迭代结束。最后利用贪心算法 $G$ 得到一个完整的解。

# 1.2.5基于部分成员集合覆盖算法(SCA)

Kuhn等人在2005提出了最小成员集合覆盖问题，并将其用于解决蜂窝网络中的干扰问题。在文献[9]中，Aslanyan等人在2010 年将最小成员集合覆盖问题推广到最小部分成员集合覆盖，将其用于求解无线网络干扰最小化问题，并从理论上证明了干扰的上限 $O ( o p t ^ { 2 } { \times } l n ^ { 2 } n )$ 和近似比 $O ( o p t ^ { \times } l n ^ { 2 } n )$

部分成员集合覆盖定义如下：给定一个 $n$ 元素集合 $S { = } S _ { 1 }$ $\cup S _ { 2 }$ 以及 $s$ 子集的集合 $C { = } \{ C _ { 1 } , C _ { 2 } , . . . C _ { k } \}$ ,其中 $S _ { 1 } \cap S _ { 2 } { = } \phi , | S _ { 1 } | { = } n _ { 1 }$ $\lvert S _ { 2 } \rvert = n _ { 2 }$ ，求集合 $C ^ { \prime } { \subset } C$ 且满足以下两个条件：

$C ^ { \prime }$ 覆盖 $S _ { 1 }$ 中的所有元素，可表示为 $\mathbf { S } _ { 1 } \mathbf { \Psi } S _ { 1 } \subseteq \cup _ { C _ { i } \in C ^ { : } } C _ { i }$ 。

C'使 S2中的元素被覆盖的最大次数最小，即 maxM(u,C")最小。其中 $S _ { 2 }$ 中的元素 $\boldsymbol { u }$ 被集合 $c$ 覆盖的次数定义为元素 $u$ 的成员值 $M ( u , C )$ ，可表示为 $M { = } ( u , C ^ { \prime } ) { = } | C _ { i } \in C ^ { \prime } { : } u \in C _ { i } | _ { \circ }$

然后将该问题构建成一个整数规划问题，利用线性规划松弛技术解决，因此可以将 $C$ 看做是问题的一个解，对于每一个 $C _ { j } \in C$ ，分配一个 $x _ { j } \in \{ 0 , 1 \}$ ，即 $x _ { j } { = } 1 \Leftrightarrow C _ { j } \in C$ 。

Minimize （204 $z$

to

$$
\begin{array} { r l } { \sum _ { u _ { i } \in C _ { j } } x _ { j } \geq 1 \quad } & { u _ { i } \in S _ { 1 } } \\ { \quad } & { \quad } \\ { \sum _ { u _ { i } \in C _ { j } } x _ { j } \leq z \quad } & { u _ { i } \in S _ { 2 } } \\ { \quad } & { x _ { j } \in \{ 0 , 1 \} \quad \quad C _ { j } \in C } \end{array}
$$

具体步骤如下：

a)初始化图 $G { = } { < } V$ $\therefore \angle 1 , \angle 0 > , E _ { 0 } =$ ， $\scriptstyle { l = 0 }$ 。$\mathsf { b } ) l { = } l { + } 1$ ，找到问题中对应的 $S _ { 1 }$ 、 $S _ { 2 }$ 、 $C$ ，并用线性规划求 $C ^ { \prime }$ （204c)调整 $C ^ { \prime }$ 中边上的半径， $E _ { l ^ { = } E _ { l - 1 } \cup C ^ { \prime } }$ ，更新图 $G _ { l } { = } { < } V , E _ { l } { > }$ 。d)重复步骤b)和c)，直至图连通为止。

# 2 缩边贪心算法(SEA)

# 2.1基本思想

缩边贪心算法（简称缩边算法，以下均使用简称）主要思想是从最大传输半径 $R$ 的导出连通图 $G _ { R } \mathrm { = } \mathrm { < } V , E _ { R } \mathrm { > }$ 开始，通过逐步缩小图中各点的传输半径，找到干扰较小的连通子图$G _ { r } { = } { < } V , E _ { r } { > } ,$ 。算法开始时通过将所有节点的传输半径初始化到最大的阈值，即 $r ( i ) { = } R [ i ]$ ， $i \in V$ ，即初始化的导出图是连通的，在确保导出图是连通的前提下算法按照缩边策略去减小各节点的发射半径，直至所有节点的传输半径都不能再减小为止。而已有算法都是通过初始化图中各节点发射半径为0开始，然后一步一步地按照算法中的策略扩大某些节点的发射半径使得这些点加入到当前导出图的连通分图中，即通过“加边”的方式将这些节点连通到当前的连通图中，与之相比，缩边算法又可以看做是不断地对当前导出连通图通过"减边”的方式以达到降低干扰的目的。

由于最终所得的导出图必须是连通的，所以选点缩边要遵循的首要条件是不能破坏导出图的连通性。根据这条件选择缩边的节点，直观上所选的点应是出度大且最大干扰点应在其覆盖圆的最外围。出度大意味着该点的连通性能可能较好，缩小其发射半径对导出图的连通性影响不大；而最大干扰点在其覆盖圆最外围的点则意味着小幅度的缩小点的发射半径即可消除对最大干扰点的干扰，最小程度地降低了对导出图连通性的影响。然而“出度大”和“最大干扰点处在其外围”这两点如果仅仅单一考虑一个都会出现极端的情况，会极大地影响当前导出图的连通性。为了避免出现这些极端情况，下面综合考虑这两点来选取缩边的节点。为此作出如下定义：

设 $u$ 为当前最大干扰点，令 $N ( u )$ 为对 $\boldsymbol { u }$ 产生干扰的节点集合，即 $N ( u ) { = } \{ \nu { \in } V | r _ { \nu } { \geq } d ( u , \nu ) \}$ ,令 $l ( u , \nu )$ 为 $u$ 在 $\nu$ 中按与 $\boldsymbol { \nu }$ 距离从近到远的排序号，其中 $\nu \in N ( u )$ ，则选择缩边的点为

$$
\nu ^ { \prime } { = } \arg \operatorname* { m a x } _ { \nu \in N ( u ) } l ( u , \nu )
$$

缩边点的发射半径由 $\boldsymbol { r } _ { \nu }$ 缩小为 $d ( u , \nu ^ { \prime } ) _ { - \xi }$ ，其中 $\boldsymbol { \varepsilon }$ 为任意小的正实数。

![](images/b7c37151ce7e63e5cdc91ec4fa7e890f94f799676ffaa9a7affbb290d471b089.jpg)  
图2缩边点选取实例  
Fig.2Example of selecting shrinking point

图2中直观展示了按式(3)选取缩边点的合理性，假设 $u$ 点为当前最大干扰点且最大干扰为3（为了方便理解，将所有在传输半径以内的点都放在同一直线上），点A、B、 $C$ 分别为干扰 $\boldsymbol { u }$ 的三个节点，可看出 $B$ 的出度最大，而 $u$ 处于 $C$ 的发射范围的最外围，当缩小节点 $B$ 或节点 $C$ 的发射半径都会使得缩边的节点仅与一个节点相连，均会破坏导出的连通性。根据式(3)选取的点为 $A$ ，缩小点 $A$ 的发射半径能保持导出图的连通性。而如果选择点 $B$ 或者 $C$ 都会极大地破坏导出图的连通性。

# 2.2算法描述

在本节中将对缩边算法进行描述分析，并根据各种算法在相同实例上的执行结果来比较不同算法产生的解的质量。算法1给出缩边算法的伪代码。

算法1缩边算法

Input:已知节点集 $V = \{ 1 , 2 , \ldots , n \}$ 在平面上的坐标，对于每个点i$\in \boldsymbol { V }$ 的最大传输半径阈值函数 $R _ { i } \ \in [ \Theta , 1 ]$ ,满足图 $G _ { R } = { \left( V , E _ { R } \right) }$ 是连通的。  
Output：图的传输半径向量 $\boldsymbol { r } = ( r _ { 1 } , r _ { 2 } , \ldots , r _ { n } )$ ，使得图 $G _ { r } = \left( V , E _ { r } \right)$ （204号连通且干扰较小。  
Begin  
1. $r _ { \mathrm { i } } { = } \mathsf { R } _ { \mathrm { i } }$ ， $\mathbf { i } \in \{ 1 , 2 , \ldots , \mathsf { n } \}$   
2.do $u \gets$ 当前最大干扰度点  
3. $\mathsf { v _ { i } } \in \mathsf { V } , \mathsf { N } ( \mathsf { u } ) \gets \{ \mathsf { v } \in \mathsf { V } | \mathsf { r } _ { \mathsf { v } } \geq \mathsf { d } ( \mathsf { u } , \mathsf { v } ) \}$   
4.While $N ( u ) \neq \emptyset$   
$\nu ^ { \prime } { = } \underset { \nu \in N \left( u \right) } { \arg \operatorname* { m a x } } l ( u , \nu )$   
5.if对 $\nu ^ { \prime }$ 缩边后图仍连通then  
6．do更新 $\boldsymbol { r } _ { v }$   
7.else  
8. $\mathsf { N } ( \mathsf { u } ) {  } \mathsf { N } ( \mathsf { u } ) \backslash \{ \mathsf { v } ^ { \prime } \}$   
9.end if  
10．end while  
11．while $u$ 的干扰减小  
12．end while  
end  
下述定理给出了缩边算法的正确性及时间复杂度的结论。

定理1该算法在 $O ( n ^ { 3 } { \times } d )$ 时间内产生一个传输半径函数$\boldsymbol { r }$ 且导出图 $G _ { r } { = } { < } V , E _ { r } { > }$ 是连通的。

证明首先证明算法的时间复杂度。该算法第一步首先要找到当前网络中最大干扰节点 $u$ ，需要时间 $O ( n )$ ；接着第二步要找出所有出度中含有 $u$ 的节点需要时间 $O ( n )$ ；最后为了保证图的连通性，在每次缩小节点的传输半径之后需要判断新的导出子图是否连通需要时间 $O ( n )$ 。又因为该算法需要重复上述直至再也找不到可以缩小的节点为止，一般这个重复次数 $d$ 会远小于 $n$ ，所以该算法的时间复杂度为 $O ( n ^ { 3 } { \times } d )$ 。

其次证明导出图的连通性，该算法初始化图时，就确保了图是连通的，并且每一步选择缩小传输半径的节点都必须以不能破坏图的连通性为首要条件，因此所选择的点不影响图的连通性，所以该算法产生的导出图 $G _ { r } { = } { < } V , E _ { r } { > }$ 是连通的。证毕。

# 2.3算例分析

例1对于上述文中所提到的一维指数链网络的实例，考虑在一维指数链网络 $n { = } 6$ 的实例上用缩边算法的执行情况。初始化图时，所有的节点都连接到了与自己相距最远的节点，如图3(a)所示，其中每个点的弧线表示该节点的传输半径最远能影响到的节点。

![](images/fd55617ac0da0fafe49e51842cae9f577b7231810a87772b957eea7080147b55.jpg)  
(a)在6个点的一维指数链网络,缩边算法初始化各点半径

(a) In one-dimensional exponential chain network with six points,edge reduction algorithm initializes derived graphs generated by radius of (b) Derived graphs after performing iteration step of algorithm

![](images/adc257f7fae764b973e8def3d1c5666414b3bb64d46ca1900d4d90c108286b5f.jpg)  
产生的导出图

![](images/c2466e4a18310c51be008171e88be1933022c6d234751a49947f5885114ec23a.jpg)  
(b)执行一次算法迭代步后的导出图  
Fig.3Example of shrinking algorithm in one-dimensional chain

(c）在6个点的一维指数链网络，缩边算法的最终结果导出图 (c) In one-dimensional exponential chain network with six points,final result of edge reductionalgorithmisderived

此时图中6个节点的干扰度都为5，均为最大干扰点。最大干扰节点不止一个时，按顺序先队编号小的点先进行缩边，选取的需要减少干扰的节点为 $\nu _ { 1 }$ ，则缩边节点v'= argmaxl(vi,v)=v。依此类推，接下来需要减少干扰的节点分别为 $\nu _ { 2 }$ 、 $\nu _ { 3 }$ 、 $\nu _ { 4 }$ 对应的缩边节点分别为 $\nu _ { 6 }$ 、 $\nu _ { 6 }$ 和 $\nu _ { 1 }$ ，完成这些缩边操作之后，各节点传输半径如图3(b)所示。经过上述一系列缩边之后，节点 $\nu _ { 1 }$ 和节点 $\nu _ { 6 }$ 都缩小了传输半径，使得当前图的最大干扰为4。

重复上述步骤，直至不存在可以缩边的节点为止，最终结果示意图如图3(c)所示。图3(c)中， $\nu _ { 1 }$ 、 $\nu _ { 2 }$ 、 $\nu _ { 4 }$ 、 $\nu { } _ { 5 }$ 和 $\nu _ { 6 }$ 的传输半径都仅仅覆盖到了与自身相邻最近的两个节点（除端节点外），而节点 $\mathbf { \sigma } _ { \nu 3 }$ 的传输半径则覆盖到了与自身相邻最远的一个节点即 $\mathbf { \Psi } _ { \nu 6 }$ 。从示意图中可直观地观察到导出图是连通的，且最大干扰度为2，平均干扰度为1.83。

例2考虑在二维空间随机产生了 $\scriptstyle n = 1 0$ 个点的算例上用缩边算法的执行情况并与已有的算法作了对比分析。算例中10个点 $\nu _ { 1 , \nu _ { 2 } , \ldots , \nu _ { 1 0 } }$ 在平面上的位置如图4所示，对应每个点的坐标分别为(1.11，0.17)(1.64，1.84)(1.92，1.72)(0.46，0.79)(1.94，0.81)(0.29，1.84)(0.24，1.30)(0.60，1.00)(1.56，0.37)(1.54，2.26)。

![](images/5d89391e35799ae8eb1e5e51be6d36b208a7139b752198c45ab0e41efa11d815.jpg)  
图4节点在平面上的位置Fig.4Position of points on plane

已知上述平面坐标的节点集 $V = \{ 1 , 2 , . . . , 1 0 \}$ ，算例的最大传输半径阈值函数，满足图 $G _ { R } \mathrm { = } ( V , E _ { R } )$ 是连通的。缩边算法执行时进行初始化，即将每个节点的传输半径设置为所能连接到最远的节点。初始化示意图如图5所示，图中箭头表示该节点所能到达最远的节点。

![](images/5e813a010988c9ddd7b705a324a498d5eea625d42890ec460524744b5f93c8ce.jpg)  
图3缩边算法在一维指数链实例  
图5各节点传输半径初始化

![](images/3fce8fb32e39f4cfc4fe88005e598c80b4fda0a6a147241dea675fcf002c3a0c.jpg)  
Fig.5Initialize transmission ranges of points   
图6最终各点传输半径  
Fig.6Final transmission ranges of points

缩边算法每个迭代步中节点传输半径变化如下：

a)r(1)=0.91-→0.89b)r(8)=0.91→0.89c)r(10)=0.66-→0.43d)r(7)=0.55-→0.54$\mathrm { e } ) r ( 8 ) { = } 0 . 8 9 { \longrightarrow } 0 . 2 5$ $\mathrm { f ) } r ( 6 ) { = } 0 . 8 9 { \longrightarrow } 0 . 5 4$

最终结果示意图见图6。为了清晰起见，这里仅标记出了经过一系列缩小传输半径后各个节点传输半径内所最远能到达的节点。从图中各节点的传输半径可知，导出图是连通的，最大干扰点是有多个分别是 $\nu _ { 1 }$ 、 $\nu _ { 2 }$ 、V3、 $\nu _ { 4 }$ 、V5、V7、V8、v9，其干扰值均为2。

在该算例中前文提到的“加边”算法在这个算例中都得出了相同的结果，其中最大干扰为3，如图7所示。

![](images/5f8410b63ba4dbb75e8e19020328157b503a067f6b150473dd136e4faacc8d81.jpg)  
图7加边”算法最终结果

将图6与7对比可看出，图6中唯一的区别在于缩边算法中设置 $r ( 8 ) { = } 0 . 2 5$ ，而“加边”算法中设置 $r ( 8 ) { = } 0 . 4 7$ ，从而导致最终最大干扰值不同。因此在这个实例上缩边算法所得的解比“加边”算法得到的解更优。

# 2.4实验结果

实验环境如表1所示。

表1实验环境说明  
Table 1Experimental environment description   
表2各个算法所得解的平均目标值  

<html><body><table><tr><td>Type</td><td>Specific information</td></tr><tr><td>OS</td><td>Microsoft Windows 7Pro version 64bit</td></tr><tr><td>CPU</td><td>Intel(R) Core(TM) i5-2410M CPU @2.30GHz</td></tr><tr><td>Memory</td><td>6GB</td></tr><tr><td>Disk</td><td>HHD 512GB</td></tr><tr><td>IDE</td><td>Codeblocks13.12</td></tr></table></body></html>

在这一部分，通过比较缩边算法与其他算法在相同例子上的执行结果来对比不同算法之间产生的解的效果。

![](images/fd965a326deb1ecdb32703b11dc1234fe089be32f2243fae57630bb208f68bf3.jpg)  
Fig.7Result of adding edge algorithm

每个例子产生规则如下： $n$ 代表实例中点的个数， $R$ 是每个点的传输半径的阈值（一般为1)， $d$ 是到处图 $G _ { R } \mathrm { = } ( V , E _ { R } )$ 的平均点度，可表示导出图中边的稠密度。对于每个给定的点对 $( n , d )$ ，在 $w { \times } w$ 的方形区域内随机产生 $n$ 个点，容易知道$d$ 满足 $d { = } n \pi R ^ { 2 } / \nu ^ { 2 }$ 。对每个实例，比较每个算法产生的导出图的干扰度。随机产生100个实例并用这100个实例的干扰度的平均值作为点对 $( n , d )$ 的最终干扰。根据下列的图8、表 2可以直观地看出各算法的解的效果，以及运行时间的对比。如表2所示，其中算例 $( n , \ d )$ 中 $n$ 和 $d$ 分别代表相应例子的节点数和平均点度

Table 2Average result of algorithms   

<html><body><table><tr><td>(n,d)</td><td>NNA</td><td>BNA</td><td>RGA</td><td>CGA</td><td>SCA</td><td>SEA</td></tr><tr><td>(100,6)</td><td>5.01</td><td>4.62</td><td>4.40</td><td>4.41</td><td>4.74</td><td>4.02</td></tr><tr><td>(100,9)</td><td>5.37</td><td>4.56</td><td>4.33</td><td>4.25</td><td>5.13</td><td>4.01</td></tr><tr><td>(100,15)</td><td>5.29</td><td>4.57</td><td>4.16</td><td>4.08</td><td>5.08</td><td>3.95</td></tr><tr><td>(100,21)</td><td>5.08</td><td>4.47</td><td>4.09</td><td>3.98</td><td>4.88</td><td>3.81</td></tr><tr><td>(200,8)</td><td>5.57</td><td>4.79</td><td>4.55</td><td>4.39</td><td>5.20</td><td>4.06</td></tr><tr><td>(200,12)</td><td>5.43</td><td>4.66</td><td>4.43</td><td>4.35</td><td>5.13</td><td>4.03</td></tr><tr><td>(200,16)</td><td>5.50</td><td>4.68</td><td>4.33</td><td>4.20</td><td>5.20</td><td>4.03</td></tr><tr><td>(200,20)</td><td>5.57</td><td>4.70</td><td>4.36</td><td>4.25</td><td>5.25</td><td>4.10</td></tr></table></body></html>

(a) $n { = } 1 0 0$ 时，不同的平均度 $d$ ，其中纵坐标为对数刻度(a)When $\mathtt { n } = 1 0 0$ ,theaverage degreeDis different,in which ordinatesare logarithmic

![](images/1ffb49b965c924b2204f19e101960d4c951aefa2cc340076a1ff5270e74cde75.jpg)  
图8各算法在不同随机图上平均运行时间  
Fig.8Average running time of algorithms in random graphs

从表2可以看出，缩边算法的解的效果明显优于其他算法，但是在图8中可以直观地看出缩边算法的运行时间比其他算法长很多，并且随着点对 $( n , d )$ 的增长，运行时间呈指数增长，这说明单纯的缩边算法适用性并不太强。为此本文结合了增强贪心算法的策略，对缩边算法进行加速。

# 3 缩边算法的加速

# 3.1加速策略

增强型贪心算法的策略有很多，如迭代贪心算法已应用于置换流水车间调度问题，Xiong等人将随机贪心算法应用于 MLST问题[15,16]。这两类贪心算法易于实现，但在MIP 问题中随机化容易破坏图的连通性。最近Carmine等人提出了旋转贪心算法，易于实现且已成功用于增强一些典型问题的贪心算法[17]。本文的第二章对旋转贪心算法进行了解释，并实验部分进行相关了的实验对比。

本文考虑了结合批量处理的增强策略，对缩边算法进行了改进。批量处理增强策略就是多个步骤同时运行，与计算机上批量处理的基本思想相似，这种策略可以减少算法的运行时间，使算法的适用性更广。

对于影响缩边算法运行时间的因素主要分为四个部分：a)找到当前最大干扰点；b)找出所有出度中含有当前最大干扰点的节点；c)缩边并判断图的连通性；d)循环上述步骤，直至不存在可缩边的节点。

关于a)，由于当前连通图的最大干扰节点在经过一次缩边策略之后，会有全局性的改变，所以每次搜索都需要遍历全图。关于b)，可以采取加入索引的方式，但是索引需要用到矩阵存储，空间复杂度会增加 $O ( n ^ { 2 } )$ ，并且在每次对节点进行缩边之后需要对矩阵进行修改，难以对该部分进行优化。因此将对c)和d)进行优化，尽可能减少图的连通性的判断次数，并加快图的最大干扰收敛的速度。

从上述算法描述中可以知道判断图的连通性是在缩小一个节点的传输半径之后进行。通过大量实验发现，最大干扰度点不仅仅只有一个，即需要减少干扰度的节点可以存在多个，但是在缩边算法中只能依次去对这些同样具有当前最大干扰度点去进行缩边策略，因此每进行一次缩边策略就需要判断一次图的连通性，这样就会导致运行时间过长。对此本文考虑是否可以将计算机批量处理的思想结合到缩边算法中，通过所有具有当前最大干扰度点一次性的进行缩边策略之后再进行判断导出图的连通性。具体算法描述如算法2伪代码。

算法2：批量缩边算法

Input:已知节点集 $V = \{ 1 , 2 , \ldots , n \}$ 在平面上的坐标，对于每个点i$\in \boldsymbol { V }$ 的最大传输半径阈值函数 $R _ { i } \ \in [ \Theta , 1 ]$ ,满足图 $G _ { R } = \left( V , E _ { R } \right)$ 是连通的。  
Output:图的传输半径向量 $\boldsymbol { r } = ( r _ { 1 } , r _ { 2 } , \ldots , r _ { n } )$ ，使得图 $G _ { r } = \left( V , E _ { r } \right)$ （204连通且干扰较小。  
Begin  
1 $\mathsf { r } _ { \mathrm { i } } { = } \mathsf { R } _ { \mathrm { i } }$ ，i∈1,2...n, $\mathsf { V } _ { \mathtt { I } _ { - } \mathtt { m a x } } = \Phi$   
2 do I_max←当前导出图最大干扰  
3 for each $\boldsymbol { v } \in \boldsymbol { V }$ Do  
4 if （204 $\scriptstyle { \cal T } _ { v } = { \cal T } _ { - } m a x$ then  
5 do $\mathsf { V } _ { \mathtt { I } _ { - } \mathtt { m a x } }  \mathsf { V } _ { \mathtt { I } _ { - } \mathtt { m a x } } \cup \mathsf { v }$   
6 end if  
7 end for  
8 if $V _ { \perp m a x }$ 中的点都进行缩边操作后图仍连通then  
9 do 更新各个缩边点的半径  
10 else  
11对 $u \in V _ { I _ { - } m a x }$ 采取未改进的缩边算法  
12 end if  
13while I_max减小  
14.end while  
end

# 3.2加速后的实验结果

为了说明算法的改进是有效的，本文对批量缩边算法进行了对比实验，实验数据如表3和图9所示。其中算例(n，$d )$ 中 $n$ 和 $d$ 分别代表相应例子的节点数和平均点度。

根据上述图表可以看出，虽然批量缩边算法的解的效果与原缩边算法的效果对比略逊一筹，但是相差并不大，还是优于其他算法。反观批量缩边算法的运行时间，批量的加速策略虽不能将缩边算法的时间复杂度从 $O ( n ^ { 3 } )$ 降低一个数量级到 $O ( n ^ { 2 } )$ ，但是其实际运行时间却远远低于原缩边算法的运行时间。

表3各算法所得解的平均目标值  
Table3Average result of algorithms   

<html><body><table><tr><td>(n,d)</td><td>NNA</td><td>BNA</td><td>RGA</td><td>CGA</td><td>SCA</td><td>SEA</td><td>P-SEA</td></tr><tr><td>(100,6)</td><td>5.15</td><td>4.56</td><td>4.39</td><td>4.36</td><td>4.80</td><td>4.08</td><td>3.89</td></tr><tr><td>(100,9)</td><td>5.21</td><td>4.60</td><td>4.39</td><td>4.27</td><td>5.08</td><td>4.06</td><td>4.08</td></tr><tr><td>(100,15)</td><td>5.19</td><td>4.57</td><td>4.25</td><td>4.11</td><td>5.06</td><td>3.83</td><td>4.09</td></tr><tr><td>(100,21)</td><td>5.15</td><td>4.31</td><td>4.11</td><td>4.01</td><td>4.88</td><td>3.89</td><td>3.94</td></tr><tr><td>(200,8)</td><td>5.58</td><td>4.94</td><td>4.76</td><td>4.80</td><td>5.22</td><td>4.11</td><td>4.20</td></tr><tr><td>(200,12)</td><td>5.53</td><td>4.68</td><td>4.38</td><td>4.36</td><td>5.17</td><td>4.03</td><td>4.09</td></tr><tr><td>(200,16)</td><td>5.53</td><td>4.67</td><td>4.35</td><td>4.30</td><td>5.21</td><td>3.98</td><td>4.14</td></tr><tr><td>(200,20)</td><td>5.62</td><td>4.71</td><td>4.39</td><td>4.22</td><td>5.25</td><td>4.00</td><td>4.15</td></tr></table></body></html>

vgaune1mmm 11 NNA0.11 BNAslt 女5女 RGA0.01 &CGA1H 10 -SEA0.0018 12 16 20 P-SEAd(b) $\scriptstyle \mathtt { n } = 2 0 0$ 时,不同的平均度d,其中纵坐标为对数刻度When ${ \bf n } = 2 0 0$ ,average degree D is different,inwhich ordinatelogarithmic

![](images/41f33d1abbd9cb5b109473fa300b092d510a48b87cde9a5b604a27f7ac13de5f.jpg)  
(a) $\scriptstyle \mathtt { n = 1 0 0 }$ 时,不同的平均度d,其中纵坐标为对数刻度  
图9各算法在不同随机图上平均运行时间  
Fig.9Algorithms of average running time in random graphs

# 4 结束语

在以接收者为中心的干扰模型下，针对无线传感器网络中基于拓扑控制技术的干扰最小化问题，本文提出了一种缩边贪心算法。该算法采用了已有算法不一样的构图方式，通过在每个节点的传输半径为最大的阈值的导出图上采取缩边的方式进行构图在大多数随机产生的算例上能产生更优解。针对其运行时间过长这一缺陷，本文将批量处理策略加入到缩边算法中，大大缩短了其运行时间，相较于其他算法使得其能在几乎相同的时间内获得更优的结果。

# 参考文献：

[1]孙利民，李建中，陈渝．无线传感器网络[M]．北京：清华大学出版 社,2005:3-23.(Sun Li-ming,Li Jian-zhong,Chen Yu.Wireless sensor networks [M].Beijing:Tsinghua University Press,20o5:3-23.)   
[2]Bilo D,Proietti G. On the complexity of minimizing interference in ad-hoc and sensor networks [J].Theoretical Computer Science,2008, 402 (1): 43-55.   
[3]Akyildiz IF,Su Weilian,Sankarasubramaniam Y,et al.Wireless sensor networks:a survey[J].Computer Networks,2002,38 (4):393-422.   
[4]Lou Tiancheng,Tan Haisheng,Wang Yuexuan,et al.Minimizing averageinterferencethroughtopologycontrol [C]//Procof International Symposium on Algorithms and Experiments for Sensor Systems,Wireless Networks and Distributed Robotics.Berlin :Springer, 2011,7111: 115-129.   
[5]Buchin K.Minimizing the maximum interference is hard [J].arXiv: 0802.2134v2,2008.   
[6]Von Rickenbach P,Schmid S,Wattenhofer R，et al.A robust interference model for wireless ad-hoc networks [C]//Proc of the 19th IEEE International Parallel and Distributed Processing Symposium. Piscataway,NJ:IEEE Press,2005,13 (4):239-246.   
[7]Benkert M，Gudmundsson J，Haverkort H,et al.Constructing minimum-interference networks [J]. Computational Geometry, 2008 40 (3): 179-194   
[8]Von Rickenbach P,Wattenhofer R,Zollinger A.Algorithmic models of interference in wireless ad hoc and sensor networks [J].IEEE/ACM Trans on Networking,2009,17(1): 172-185.   
[9]Halldorsson MM,Tokuyama T.Minimizing interference of a wireless ad-hoc network in a plane [J]. Theoretical Computer Science,2o08,402 (1): 29-4   
[10] Zhang Xiaoke,Chen Weidong.An effective algorithm for interference minimization in wireless sensor networks [C]// Proc of International Conference on Intelligent Computing.[S.l.]:Springer International Publishing,2014 572-581   
[11] .Hassin R,Levin A.A better-than-greedy approximation algorithm for the minimum set cover problem[J].SIAM Journal on Computer, 2005, 35 (1): 189-200.   
[12]孙佩歆．无线传感器网络中干扰最小化问题的后悔贪心算法[J]. 计算机工程与科学,2017,39(12):2217-2223.(Sun Peixin.A regret greedy algorithm for the interference minimization problem in wireless sensor networks [J].Computer Engineering and Science Computer Engineering and Science,2017,39 (12): 2217-2223.)   
[13] Shetty D P,Lakshmi M P. Algorithms for minimizing the receiver interference in a wireless sensor network [C]//Proc ofIEEE Distributed Computing,VLSI,Electrical Circuits and Robotics .2016: 113-118.   
[14] West D B.Introduction to graph theory [M].Upper Saddle River, NJ :Prentice-Hall,1996   
[15]Karabulut K.A hybrid iterated greedy algorithm for total tardiness minimization in permutation flowshops [J].Computers & Industrial Engineering,2016,98:300-307.   
[16] Xiong Yupei,Golden B,Wasil E.Improved heuristics for the minimum label spanning tree problem [J]. IEEE Transon Evolutionary Computation,2006,10(6): 700-703.   
[17] Cerrone C,Cerulli R,Golden B.Carousel greedy: a generalized greedy algorithm with applicationsin optimization [J].Computers& Operations Research,2017,85:97-112.