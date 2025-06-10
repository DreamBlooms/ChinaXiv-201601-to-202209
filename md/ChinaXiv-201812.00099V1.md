# 超网络的全终端可靠性分析

张科1.2.3，赵海兴1.2.3†，冶忠林 2.3.4，朱宇1,2.3(1.青海师范大学 计算机学院，西宁 810016;2.青海省藏文信息处理与机器翻译重点实验室，西宁 810008；3．藏文信息处理教育部重点实验室，西宁 810008;4．陕西师范大学 计算机科学学院，西安 710062)

摘要：网络的可靠性是复杂网络研究的一个重要领域，能有效刻画某些复杂系统的超网络属于复杂网络的研究范畴。基于超网络的拓扑结构——超图，提出了超网络在边失效下的全终端可靠度的定义，并给出了计算可靠度的两种基本方法，即状态枚举法和因式分解法，依据因式分解法对一些具有特殊结构的超网络进行化简。作为超网络可靠性的应用，研究了连通生成子网络的数目；在与普通复杂网络的对比中可以得知，超网络的可靠性研究不能其用转换后的普通复杂网络可靠性作替代研究。该研究是对超网络可靠性研究的初步探索，这方面有着广阔的研究空间和应用前景。

关键词：可靠度；全终端；超网络；因式分解；超图 中图分类号：TP393.02 doi:10.19734/j.issn.1001-3695.2018.08.0542

# Analysis forall-terminal reliabilityofhypernetworks

Zhang $\mathrm { K e } ^ { 1 , 2 , 3 }$ , Zhao Haixing1,2.3†, Ye Zhonglin2,3,4, Zhu $\mathrm { Y u } ^ { 1 , 2 , 3 }$ （204号 (1.SchoolofComputer，Qinghai Normal University,Xining810o08,China;2.Tbetan InformationProcessng&Machine Translation Key Laboratoryof Qinghai Province， Xining 810o08,China;3.Key Laboratory of Tibetan Information Processing of MinistryofEducation,Xining 810o08,China;4.SchoolofComputer Science,Shaanxi Normal University Xi'an 710062, China)

Abstract:The networkreliabilityisanimportant fieldofthecomplex network research.Hypernetworks whichcandescribe somecomplex systems effectivelybelong tothe scopeof thecomplex network research.Based on the topological structures of hypernetworks-hypergraphs,this paperpresents thedefinitionoftheal-terminalreliabilityofhypernetworks with edge failure,and proposes two basic methods forcalculating thereliability,namely state enumerationandthe factorization method.According to the factorization method,some hypernetworks with special structures can besimplified.As an applicationof the hypernetwork reliability，the numberof connectedspanning sub-networks is studied.Compared with ordinarycomplex networks,wecanconclude thatthereliabilityof hypernetworkscan’tbereplaced bythereliabilityof ordinarycomplex networks that transform from coresponding hypernetworks.This research is a preliminary explorationof the hypernetwork reliability, which has broad research spaces and application prospects.

Keywords:reliability;all-terminal; hypernetwork; factorization;hypergraph

# 0 引言

现实世界中的各种各样的复杂系统往往抽象成网络模型进行研究，网络的拓扑结构是普通图。特别是近二十年来，网络科学得到了长足的发展，而相应系统的可靠性是研究的一个重要的方向[。例如，由于故障、自然灾害或蓄意破坏等会使电力网络的功能降低，甚至会出现大面积停电的事故；又如，通信网络的一个小的局部中断，最终可能会使整个地区的通信服务受到影响。类似问题的解决有赖于网络可靠性的研究与发展。

其中，在评估网络系统的连通性可靠性方面，是将网络实现连通的概率作为其可靠性的度量。网络可靠性的模型有三种：点失效、边失效以及点和边都失效[2]。网络可靠性研究的两个方面是可靠性的分析和设计[2]。抽象后的网络图有无向和有向之分，而对其研究又有多种不同的模型，包括2-终端、

$K$ -终端和全终端，每一种模型又分为有源和无源[3]。研究方法主要有：a)经典的解析方法，如状态枚举法、因式分解法、容斥原理法等;b）近似、仿真的方法，如定界法、蒙特卡罗法、智能算法等;c）与网络结构相关的和特定要求下的其他方法，着眼点不同的丰富的研究结果充实了网络可靠性的研究内容。

随着网络科学的进一步发展，研究人员发现有些网络的顶点有多样化的特点，有些网络的顶点之间的关系也不局限于顶点对之间有无链路的简单关系，有些网络的结构表现出多层、有嵌套的特征[4]。为了解决研究网络的过程中遇到的类似种种新的问题，超网络的概念被提了出来，从而拓宽并丰富了复杂网络的研究范围。一般来说，超网络分为两类，即基于图的超网络和基于超图的超网络。对于前者，其可靠性已经有一些研究结果[5]；后者是本文的研究对象，它是指用超图来建模的复杂网络。这些网络如果用图进行建模的话就会出现顶点间不同质或丢失网络信息等问题，所以用超图来对这些网络进行建模是更有效的方法。例如，科研合作网的超图描述能更全面的反映出研究者之间的合作关系[；食物竞争网络的超图描述能清楚的反映出种群之间的食物竞争关系[7]。

近十年来，超网络引起了越来越多的研究者的注意。对超网络的研究主要集中在模型的建立[6.8.9]、拓扑指标研究[10,1]和应用[12]等方面[4]。在应用方面，由于超网络模型的一条链路可以包含两个或两个以上的顶点，结合超图的理论，用超图对复杂网络进行建模比普通图具有显著的优势。一方面，由于图是超图的特殊类型，所以能用普通复杂网络建模的复杂系统都能用超网络建模；另一方面，超网络能够准确的刻画复杂系统中更多元化的连接关系，进而探索网络科学中没有发现的规律[4]。由上述超网络的发展历程可知，它隶属于复杂网络的研究范畴。网络可靠性作为具有重大理论意义和应用价值的研究热点，在普通复杂网络中有很多相关的研究成果。随着越来越多的复杂系统用超网络来描述，超网络可靠性研究的需求日益显现出来。如在快递超网络[13]中，少量物流公司的负载过重会极大地降低该超网络的流通效率。但这一研究领域在超网络背景下，到目前为止，国内外几乎没有人涉足。与超网络可靠性相关的研究结果也较少。1987年，陈廷槐等人[14]将超图的连通性用于容错多总线系统的设计中；1997年，曹其国等人[151从超图的视角设计通信网络中可靠性高的多总线结构；最近，马秀娟等人[13]分析了快递超网络和电子元件超网络的相继故障。

本文主要是对超网络的可靠性作初步地探讨，首先给出了超网络的全终端可靠度的定义，并提出了两种计算可靠度的基本方法。依据可靠度的计算方法，对具有特殊结构的超网络的可靠度计算进行了化简；借助超网络的可靠度，可以分析其连通生成子超图的数目及其与可靠度的关系。最后，利用可靠度对普通图和超图进行了比较研究，发现了可靠度不同于普通图可靠度的超图。也列出了一些可以进一步研究的问题。

# 1 超图的基本概念和相关术语

本文研究超网络的可靠性。这里的超网络是用有限的无向连通超图进行建模的，即超网络的研究对象与超图的顶点是对应的，并且超图的边与超网络的链路具有相同的连接方式。在后文中对超网络和超图不作区分。具有 $n$ 个顶点和 $m$ 条超边（简称边）的有限的无向连通超图记为 $H ( V , \varepsilon )$ ，其顶点的集合为 $V = \{ \nu _ { 1 } , ~ \nu _ { 2 } , ~ \cdots , ~ \nu _ { n } \}$ 以及边的集合为$\varepsilon = \{ E _ { 1 } , E _ { 2 } , \cdots , E _ { m } \}$ 。本文仅考虑超图的点都不失效而边失效的情形，边之间是否失效是相互独立的，并且设其第 $i$ 条边 $E _ { i }$ 失效的概率为 $p _ { i }$ 。本文采用全终端可靠度作为相应的超网络的可靠性的度量，它是普通复杂网络中全终端可靠度的推广。与图相关的定义和术语可以参考文献[16]，与网络的全终端可靠度相关的定义和术语可以参考文献[2]。下面仅对超图的相关概念和术语作简要的介绍，没有介绍到的可以参考文献[17]。

超图 $H$ 是一个二元组 $( V , \varepsilon )$ ，其中 $\boldsymbol { V }$ 是 $H$ 的顶点的集合， $\boldsymbol { \varepsilon }$ 是$V$ 的非空子集的集合。集合 $\varepsilon$ 的一个元素是 $H$ 的一条超边或简称为 $H$ 的一条边。下文中研究的超图不含孤立点，孤立点是指不包含在任何超边中的点。 $H$ 的一个顶点 $\nu$ 的度记为$d _ { H } ( \nu )$ 或 $d ( \nu )$ ，表示 $H$ 中含顶点 $\nu$ 的边的个数。在边集合$\varepsilon = \{ E _ { 1 } , E _ { 2 } , \cdots , E _ { m } \}$ 中，对于任意的 $i , j ( 1 \leq i , j \leq m )$ ，如果由 $E _ { i } \subseteq E _ { j }$ 可得 $i = j$ ，则称 $H$ 为简单超图。在超图中，如果存在一条边包含某两个顶点，则称这两个顶点是相邻的；如果两条边的交集非空，则称这两条边是相邻的。对于任意的 $i , j ( 1 \le i , j \le m )$ ，如果 $\big | E _ { i } \cap E _ { j } \big | \leq 1$ ，则称超图 $H$ 是线性的。如果$| E _ { i } | = r ( r = 1 , ~ 2 , ~ \cdots , ~ m )$ ，则称 $H$ 是一个 $r$ -一致超图。由此可知,一个简单的2-一致超图就是一个普通图，反之亦然。

对于 $u , \nu \in V$ ， $H$ 的满足 $\nu _ { i }$ 5 $\nu _ { _ { i + 1 } } \in E _ { i }$ ， $( i = 0 , 1 , 2 , \cdots , i - 1 )$ 的一个点边交错的序列 $( u = \nu _ { 0 } , E _ { 1 } , \nu _ { 1 } , E _ { 2 } , \nu _ { 2 } , \cdots , \nu _ { k } = \nu )$ 称为 $( u , \nu )$ 途径，其中 $k$ 为该途径的长度。 $( u , \nu )$ 途径的最短长度记为$d ( u , \nu )$ ，表示 $u , \nu$ 之间的距离。

如果超图 $H$ 的任意两个顶点之间存在一条途径，则称其为连通的，否则它就是不连通的。如果一个超图 $H$ 是不连通的，则它的连通分支的个数记为 $\omega ( H )$ 。超图 $H$ 的边连通度记为 $\lambda ( H )$ ，表示使得 $H$ 不连通所要删去的最少的边数。这个定义是图中相应定义的推广。

树是图论中的重要的研究对象，图的生成树个数与对应网络的边可靠度有着密切的联系[18]。把树的定义推广到超图中称之为超树（简称树)。与树的定义相比，超树的定义要复杂得多，并且不同的定义之间不是等价的[19.20]。本文所采用的超树的定义是任意删去一条边都导致自身不连通的超图。超图 $H$ 的生成超树是指 $H$ 的生成子超图，它同时又是超树。

与树在图中的地位一样，超树是超图中的具有基础性意义的结构，在超网络的边失效可靠性研究中扮演着重要的角色。

下面的结论刻画了紧超树的结构[21]。由树和超树的定义可知，这个结论适用于树。

设 $H$ 是一个具有 $n$ 个顶点的连通超图。如果 $H$ 是紧超树，则有 $\sum _ { i = 1 } ^ { m } ( \mid E _ { i } \mid - 1 ) = n - 1$ 。

换一个角度来看这个结论。如果 $H$ 是紧超树，意味着从$H$ 中任意删去一条边 $\boldsymbol { \varepsilon }$ 后， $H$ 的子超图 $H - E$ 的分支数恰好为边 $E$ 中所含的点的个数即 $\vert E \vert$ 。用数学符号语言表述为如果$H$ 是紧超树，则 $\forall E \in \mathcal { E } ( H )$ ，有 $\omega ( H - E ) = \mid E \mid$ 。

对于 $r$ -一致超图，文献[22]给出了一个相关的结论。设 $H$ 是一个具有 $n$ 个顶点的 $r$ -一致超图。如果 $H$ 是连通的，则有m(H)≥n-1 。当且仅当从 $H$ 中任意删去一条边 $\boldsymbol { \varepsilon }$ 所得的r-1°子超图恰好有 $r$ 个分支时等号成立。

这个结论给出了连通的 $r$ -一致超图的边数的下界，并且指出边数取得下界时的 $r$ -一致超图为紧的 $r$ -一致超树。

# 2 超网络的可靠性及基本计算方法

即使是在网络科学经历了近二十年发展的今天，计算网络的可靠度仍然是一件极具挑战性的事情。诸如交通网、电信网、社会网络和电力系统，这些网络对自身的可靠性有着更高的要求，计算它们的可靠度时由于复杂度高也更加困难。近年来由于在组合学中的合理性和在应用上的有效性，越来越多的研究者在尝试用超图对一些复杂系统进行建模。随着超图设计理论的进一步发展，超图的可靠性研究和应用将受到越来越多的关注。然而，对超网络可靠性的研究仍然是一个极少有人涉足的领域。

在研究网络可靠性的多种不同的模型中，全终端可靠度作为一种常用的可靠性度量受到了很多的关注。像电力网、交通网、计算机网络等，全终端可靠度是更为重要的一种网络的可靠性的度量[23]。本文的研究对象是有限的无向超图的全终端可靠度，即在边失效下该超图保持连通的概率。

设 $H ( V , \ \varepsilon )$ 是一个有限的无向超图，其顶点集为

$V = \{ \nu _ { 1 } , ~ \nu _ { 2 } , ~ \cdots , ~ \nu _ { n } \}$ ，边集为 $\varepsilon = \{ E _ { 1 } , E _ { 2 } , \cdots , E _ { m } \}$ 。因为仅仅考虑边不可靠的情形，所以每一条边只有失效和不失效两种状态。将边集的状态向量定义为 $X = ( x _ { 1 } , x _ { 2 } , x _ { 3 } , \cdots , x _ { m } )$ ，其中相应边的状态的指示变量 $x _ { 1 } , x _ { 2 } , x _ { 3 } , \cdots , x _ { m }$ 都是二进制布尔变量：

$$
\boldsymbol { x } _ { i } = \left\{ \begin{array} { l l } { 1 , \mathrm { ~ } \Dot { \mathcal { U } } \Dot { \mathcal { K } } E _ { i } \underset { \mathcal { X } } { \mathcal { K } } \Dot { \mathcal { K } } \Dot { \mathcal { X } } \Dot { \mathcal { X } } } \\ { 0 , \mathrm { ~ } \Dot { \mathcal { U } } \Dot { \mathcal { K } } E _ { i } \underset { \mathcal { X } } { \mathcal { K } } \Dot { \mathcal { X } } \Dot { \mathcal { X } } } \end{array} ; \ i = 1 , \ 2 , 3 , \cdots , m \mathrm { ~ . ~ } \right.
$$

由此，在假设指示变量都是随机变量的前提下，所有的无向超图 $H$ 的生成子超图就会组成一个随机系统 $\mathcal { H }$ 。易知$| \mathcal { H } | = 2 ^ { m }$ 。 $H$ 的连通的生成子超图的个数记为 $\varsigma ( H )$ (简记为$\varsigma$ ）。

本文假设 $m$ 个随机变量 $x _ { 1 } , x _ { 2 } , x _ { 3 } , \cdots , x _ { m }$ 是相互独立的，它们的概率分布如下：

$$
P _ { i } = \left\{ { \begin{array} { l } { 1 - p _ { i } , x _ { i } = 1 } \\ { p _ { i } \quad , x _ { i } = 0 } \end{array} } ; i = 1 , 2 , 3 , \cdots , m . \right.
$$

# 2.1状态枚举法

关于计算超网络 $H$ 的可靠度，由假设，可以把状态枚举法的计算方法总结为如下定理的形式。

定理1有限的无向超图 $H$ 的全终端可靠度为

$$
R ( H ) = \sum _ { k = 1 } ^ { \zeta } \prod _ { i = 1 } ^ { m } P _ { i }
$$

式（3）的右边是关于 $p _ { i }$ 和 $1 - p _ { i }$ 的 $m$ 次齐次多项式，其中 $i = 1 , \ 2 , \ 3 , \ \cdots , \ m$ ，共有 $\varsigma$ 项，并且这个多项式的每一项只含有 $p _ { i }$ 或者 $1 - p _ { i }$ 。称其为超图 $H$ 的标准可靠多项式。

枚举法是计算超网络可靠度的最直观的方法。用于计算普通网络可靠度的枚举法是它的特殊情形。考虑如图1所示的具有4条链路的超网络，为了用枚举法计算其可靠度，需要考察16个边集的子集合。其中，有8个对应着该网络的连通生成子网络。

![](images/b2b471e4e7f9c3d94464bb6f578ca76cdefd4bd19d20698a7b66bcbcd3ece3b7.jpg)  
图1具有5个顶点4条边的简单3-一致超图  
Fig.1A3-uniformhypergraph with5 vertices and 4edges 其全终端可靠度为:

$$
\begin{array} { l } { { R ( p _ { 1 } , p _ { 2 } , p _ { 3 } , p _ { 4 } ) = ( 1 - p _ { 1 } ) p _ { 2 } p _ { 3 } ( 1 - p _ { 4 } ) + } } \\ { { \ \qquad p _ { 1 } ( 1 - p _ { 2 } ) p _ { 3 } ( 1 - p _ { 4 } ) + } } \\ { { \ \qquad p _ { 1 } p _ { 2 } ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) + } } \\ { { \ \qquad ( 1 - p _ { 1 } ) ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) p _ { 4 } + } } \\ { { \ \qquad ( 1 - p _ { 1 } ) ( 1 - p _ { 2 } ) ( p _ { 3 } ) ( 1 - p _ { 4 } ) + } } \\ { { \ \qquad ( 1 - p _ { 1 } ) p _ { 2 } ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) + } } \\ { { \ \qquad p _ { 1 } ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) + } } \\ { { \ \qquad ( 1 - p _ { 1 } ) ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) } } \\ { { \ \qquad ( 1 - p _ { 1 } ) ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) . } } \end{array}
$$

# 2.2因式分解定理

一般来说，使用因式分解定理来计算普通网络的可靠度最早是由Moskowitz[24]和Mine[25]提出的。目前，有很多研究者利用因式分解定理来计算普通网络的可靠度[26.27]。下面将计算普通网络的可靠度的因式分解定理推广到超网络。在超网络中，进行收缩或删除的边可以是超边，从而扩大了其在复杂网络可靠度研究中的应用范围。下面给出了计算超网络可靠度时的因式分解定理，并证明了其正确性。

定理2超网络 $H$ 中的某条超链路 $E _ { i }$ 只有失效和不失效两种状态。对应着这两种状态超网络 $H$ 的状态可以分为两类，其全终端可靠度可表示为

$$
R ( H ) = ( 1 - p _ { i } ) R ( H _ { E _ { i } } ) + p _ { i } R ( H - E _ { i } )
$$

其中， $H _ { E _ { i } }$ 和 $H - E _ { i }$ 分别表示为在 $H$ 中收缩和删去边 $E _ { i }$ 后所得到的超网络。

证明 $H$ 的所有生成子超图中， $E _ { i }$ 作为其一条边的连通生成子超图所占的概率为 $( 1 - p _ { i } ) R ( H _ { E _ { i } } )$ ， $E _ { i }$ 不是其一条边的连通生成子超图所占的概率为 $p _ { i } R ( H - E _ { i } )$ 。从而 $H$ 的连通生成子超图的概率为 $R ( H ) = ( 1 - p _ { i } ) R ( H _ { E _ { i } } ) + p _ { i } R ( H - E _ { i } )$ 。

对于图1所示的超网络，下面用因式分解的方法计算它的可靠度。选择 $E _ { 4 }$ 进行收缩和分解，如图2所示。得到的全终端可靠度与用状态枚举法得到的结果一致。

![](images/8e46294fe729fe666c038ede5f0da95ce9375b13178b63512cd9cf432011c93b.jpg)  
图2因式定理应用于一个简单3-一致超图  
Fig.2The factoring theoremapplied to a simple 3-uniform hypergraph

$$
\begin{array} { r l } { R ( P _ { 1 } , P _ { 2 } , P _ { 3 } , P _ { 4 } ) = ( 1 - p _ { 1 } ) R ( E _ { 1 } ) + p _ { 2 } R ( R - E _ { 1 } ) } \\ & { = ( 1 - p _ { 2 } ) \Big \{ ( 1 - p _ { 1 } ) p _ { 1 } p _ { 2 } + p _ { 1 } ( 1 - p _ { 2 } ) p _ { 3 } + } \\ & { \quad p _ { 1 } p _ { 2 } ( 1 - p _ { 3 } ) + ( 1 - p _ { 1 } ) ( 1 - p _ { 2 } ) p _ { 4 } + } \\ & { \quad ( 1 - p _ { 1 } ) p _ { 1 } ( 1 - p _ { 3 } ) - ( 1 - p _ { 1 } ) ( 1 - p _ { 2 } ) p _ { 3 } + } \\ & { \quad ( 1 - p _ { 1 } ) ( 1 - p _ { 2 } ) ( 1 - p _ { 1 } ) \Big \} + } \\ & { \quad ( 1 - p _ { 1 } ) ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) } \\ & { \quad p _ { 4 } ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) + p _ { 4 } \langle 1 - p _ { 2 } \rangle } \\ & { = ( 1 - p _ { 2 } ) p _ { 2 } \langle 1 - p _ { 3 } \rangle + p _ { 4 } \langle 1 - p _ { 2 } \rangle \langle 1 - p _ { 3 } \rangle + } \\ & { \quad p _ { 1 } p _ { 2 } ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) + ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) p _ { 4 } + } \\ & { \quad ( 1 - p _ { 1 } ) ( 1 - p _ { 2 } ) p _ { 3 } ( 1 - p _ { 4 } ) + } \\ & { \quad ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) + } \\ & { \quad p _ { 1 } ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) + } \\ & { \quad ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) - } \\ & { \quad p _ { 2 } ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) - } \\ & { \quad ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) - } \\ & { \quad ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) - } \\ & { \quad ( 1 - p _ { 2 } ) ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) } \\ & { \quad ( 1 - p _ { 3 } ) ( 1 - p _ { 4 } ) ( 1 - p _ { 4 } ) } \\ & { \quad ( 1 - p _ { 2 } ) ( 1 - p _ { 2 } ) ( 1 - p _ { 3 } ) } \end{array}
$$

# 3 超网络可靠度的化简

对于具有 $m$ 条超链路的超网络 $H$ ，用2.2小节所述的因式分解定理计算其可靠度的复杂度为 $O ( 2 ^ { m } )$ 。由因式分解方法的计算原理，如果一个超网络的超链路数少一条，则计算其可靠度的复杂度降为原来的一半。所以计算超网络的可靠度时，对该超网络进行关于可靠度的等价化简具有重要的意义。现实世界的很多超网络都具有串联、并联以及具有1度顶点等结构特点，使这种等价的化简具有可操作性。

# 3.1具有1度顶点的超网络的可靠度的等价化简

定理3设 $E _ { 0 }$ 为超网络 $H$ 的一条具有1度顶点的超链路，且 $E _ { 0 }$ 失效的概率为 $p _ { \mathrm { 0 } }$ ，则 $H$ 的可靠度为

$$
R ( H ) = ( 1 - p _ { \mathrm { 0 } } ) R ( H _ { E _ { \mathrm { 0 } } } )
$$

证明 由因式分解定理， $R ( H ) = ( 1 - p _ { 0 } ) R ( H _ { E _ { 0 } } ) + p _ { 0 } R ( H - E _ { 0 } )$ 。因为超链路 $E _ { 0 }$ 中具有1度顶点，所以子超网络 $H - E _ { \mathrm { 0 } }$ 是不连通的，即 $R ( H - E _ { 0 } ) = 0$ 。命题得证。

图3中，给出了利用因式分解定理计算一个具有1度点的超网络的可靠度的实例。由此也可以看出，利用因式分解

定理计算超网络的可靠度时计算的时间复杂度依赖于选边的顺序。

![](images/7089d0da9854a129d57e5f01c086381c4d738f3552a7f876e2fd6cce7fe7b612.jpg)  
图3将因式分解定理应用于一个具有1度点的超网络 Fig.3The factoring theorem applied to a hypernetwork with at least one vertex of degree 1

# 3.2串联超网络和并联超网络

很多大规模的超网络都可以最终分解成一些基础超网络，或者这些网络是在某个基础超网络上建立的，下面研究两类基础超网络，即串联超网络和并联超网络。

# 3.2.1串联超网络

在普通复杂网络中，串联网络的拓扑结构是图论中的一条路。超网络中的串联形式表现出复杂多样的特点，它们都表现为任何一条边失效都会导致该串联网络不连通,即串联超网络的可靠度为

$$
R ( H _ { s } ) = \prod _ { i = 1 } ^ { m } ( 1 - p _ { i } ) = ( 1 - p _ { 1 } ) ( 1 - p _ { 2 } ) \cdots ( 1 - p _ { m } )
$$

如果所有的链路都具有相同的失效的概率 $p$ ，则

$$
R ( H _ { s } ) = \prod _ { i = 1 } ^ { m } ( 1 - p ) = ( 1 - p ) ^ { m }
$$

图4中所示的是具有5个顶点2条（超）链路的所有串联超网络，它们的可靠度均为 $( 1 - p _ { 1 } ) ( 1 - p _ { 2 } )$ 。

![](images/01a51911f0b5b5884b835a3d1c51cc8a39a5e7169c800bbf5ede2270c797e2a0.jpg)  
图4具有5个顶点2条链路的所有串联超网络 Fig.4All series hypernetworks with 5 vertices and2 edges 3.2.2并联超网络

并联超网络的特点在于只有所有的超链路都失效了它才会失效。其可靠度为1减去所有链路失效的概率的乘积，即

$$
R ( H _ { p } ) = 1 - \prod _ { i = 1 } ^ { m } p _ { i } = 1 - p _ { 1 } p _ { 2 } \cdots p _ { m }
$$

如果所有的链路都具有相同的失效的概率 $p$ ，则

$$
R ( H _ { p } ) = 1 - p ^ { m }
$$

这种严格的要求导致并联超网络的形式单一。它的任何一条平行的链路都要包含网络中的所有的顶点。图5给出了具有5个顶点2条链路的两个超网络，其中超网络图5（a)是并联的，超网络（b）不是并联的。

![](images/2c4040070829cf8dded139ed15785cd1a630309aa18e6eac056a311d5c6cc83c.jpg)  
图5具有5个顶点2条链路的两个超网络。  
Fig.5Two hypernetworks with5 vertices and 2 edges.

# 4超图的可靠度与其连通生成子超图的数目之间的关系

假设超网络中的每一条链路都具有相同的失效概率 $p$ 并且每条边是否失效是相互独立的，则2节中提到的可靠度的标准形式就是一个关于 $p$ 和 $1 - p$ 的 $m$ 次齐次多项式，表示为如下形式

$$
R ( H , p ) = \sum _ { i = 0 } ^ { m } s _ { i } ( H ) ( 1 - p ) ^ { i } p ^ { m - i } .
$$

其中： $s _ { i } ( H )$ 为 $H$ 中具有 $i$ 条边的连通生成子超图的个数。

为了更准确的描述由可靠度反映出的相应的超网络 $H$ 具有的某些性质，也为了更深入地理解超网络 $H$ 的可靠多项式，接下来进一步假设超网络 $H$ 的拓扑结构是 $\boldsymbol { r }$ -一致超图。得到的结论可以推广到一般的情形的。

由超图的生成超树的定义，超网络中的树结构是指具有极小链路数的生成子网络。其中具有最小链路数的生成子网络称为主生成子网络，相应的拓扑结构为主生成超树。例如，图1所示的超网络中有4个生成子网络，组成的集合为${ \cal S T } = \{ \{ E _ { 1 } , E _ { 4 } \} , \{ E _ { 2 } , E _ { 4 } \} , \{ E _ { 3 } , E _ { 4 } \} , \{ E _ { 1 } , E _ { 2 } , E _ { 3 } \} \}$ 。其中共有 3个主生成子网络，组成的集合为$S T _ { M } = \{ \{ E _ { 1 } , E _ { 4 } \} , \{ E _ { 2 } , E _ { 4 } \} , \{ E _ { 3 } , E _ { 4 } \} \}$ 。由上述超网络 $H$ 的可靠多项式，当超边失效的概率很大，即趋近于1时，超网络 $H$ 的主生成子网络数目对该网络的可靠性起到决定性的作用。

设超网络 $H$ 的拓扑结构是连通的超图，且具有 $n$ 个顶点和 $m$ 条链路。

依据可靠多项式，关于多项式的系数，可以得到以下主要结论：

$$
\begin{array} { c } { { s _ { 0 } ( H ) = s _ { 1 } ( H ) = s _ { 2 } ( H ) = \cdots = s _ { \left\lceil \frac { n - 1 } { r _ { - 1 } } \right\rceil - 1 } ( H ) = 0 \ , } } \\ { { \displaystyle s _ { \left\lceil \frac { n - 1 } { r _ { - 1 } } \right\rceil } ( H ) = \left| S T _ { M } \right| \ , } } \\ { { \displaystyle \sum _ { i = \left\lceil \frac { n - 1 } { r _ { - 1 } } \right\rceil } ^ { m } s _ { i } ( H ) = \varsigma ( H ) \ . } } \end{array}
$$

2）设 $H _ { 1 }$ 和 $\boldsymbol { H } _ { 2 }$ 是两个具有相同顶点数和边数的 $r$ -一致 超图。若 $\lambda ( H _ { 1 } ) > \lambda ( H _ { 2 } )$ ，或同时满足 $\lambda ( H _ { 1 } ) = \lambda ( H _ { 2 } )$ 和

$$
\begin{array} { r } { s _ { \left[ \frac { n - 1 } { r - 1 } \right] } ( H _ { 1 } ) > s _ { \left[ \frac { n - 1 } { r - 1 } \right] } ( H _ { 2 } ) _ { , } } \end{array}
$$

则存在 $p _ { 0 } < 1$ 使得对所有 $p _ { 0 } < p < 1$ ，有$R ( H _ { 1 } , p ) > R ( H _ { 2 } , p ) _ { \circ }$ （204

# 5 可靠性意义下的超图与普通图的比较

假设所研究的图或超图中的所有顶点都是可靠的，所有的（超）边都是不可靠的，（超）边失效的概率均为 $p$ 并且是否失效是相互独立的。

从可靠性的角度，可以看出图与超图结构上的区别。下面用两个实例加以说明。

例证1找不到一个普通图，使之与图1中的超图具有

相同的可靠度。

证明由假设，图1中的超图的可靠度是关于 $p$ 的多项式

$$
R ( p ) = 3 ( 1 - p ) ^ { 2 } p ^ { 2 } + 4 ( 1 - p ) ^ { 3 } p + ( 1 - p ) ^ { 4 } \ \cdot
$$

如果存在一个图G，其可靠度也为 $R ( p )$ ，则 $\mathrm { n } ( G ) \leq 5$ 。否则连通的图G至少有5条边。

当 $\mathfrak { n } ( G ) = 5$ 时，具有4条边的连通的图G的结构是确定的，即为具有5个点的树，不同构的结构有3种，它们的可靠度均为 $\left( 1 - p \right) ^ { 4 }$ ，不等于 $R ( p )$ 。

当 $\mathrm { n } ( G ) = 4$ 时，具有4条边的连通的图 $\mathbf { G }$ 的不同构的结构只有两种，如图5中所示的 $G _ { \mathrm { 1 } }$ 和 $G _ { 2 }$ 。而

$$
R ( \mathbf { G } _ { 1 } , p ) = 4 ( 1 - p ) ^ { 3 } p + ( 1 - p ) ^ { 4 } ,
$$

$$
R ( { \bf G } _ { 2 } , p ) = 3 { ( 1 - p ) } ^ { 3 } p + { ( 1 - p ) } ^ { 4 }
$$

均不等于 $R ( p )$ 。

当 $\mathbf { n } ( G ) = 3$ 时，具有4条边的连通的图 $\mathbf { G }$ 的不同构的结构有3种，如图5中所示的 $G _ { 3 }$ 、 $G _ { 4 }$ 和 $G _ { 5 }$ 。它们可靠度分别为

$$
\begin{array} { c } { { R ( \mathrm { \bf G } _ { 3 } , p ) = 5 ( 1 - p ) ^ { 2 } p ^ { 2 } + 4 ( 1 - p ) ^ { 3 } p + ( 1 - p ) ^ { 4 } , } } \\ { { { } } } \\ { { R ( \mathrm { \bf G } _ { 4 } , p ) = 3 ( 1 - p ) ^ { 2 } p ^ { 2 } + 3 ( 1 - p ) ^ { 3 } p + ( 1 - p ) ^ { 4 } , } } \\ { { { } } } \\ { { R ( \mathrm { \bf G } _ { 5 } , p ) = 4 ( 1 - p ) ^ { 2 } p ^ { 2 } + 4 ( 1 - p ) ^ { 3 } p + ( 1 - p ) ^ { 4 } . } } \end{array}
$$

以上三式均不等于 $R ( p )$ 。

当 $\operatorname { n } ( G ) = 2$ 时，具有4条边的连通的图 $\mathbf { G }$ 的结构是唯一确定的，即为具有4条边的平行网络，如图5中的 $G _ { 6 }$ ，其可靠度为

$$
R ( G _ { 6 } , p ) = 4 ( 1 - p ) p ^ { 3 } + 6 ( 1 - p ) ^ { 2 } p ^ { 2 } + 4 ( 1 - p ) ^ { 3 } p + ( 1 - p ) ^ { 4 }
$$

不等于 $R ( p )$ 。

![](images/d227d7feb527c20d6a03144e5fca9da13a52e6b154208b74f7ad9fb0815d08b1.jpg)  
图6具有4条边的点数分别为4,3,2的图Fig.6Graphs with 4 edges of order 4,3,2.  
Fig.7All 3-uniform linear hypertrees with 4 edges

例证2已知具有4条边的不同构的树结构有3种，而仅仅是在线性3-一致超图中具有树结构的不同构的超图就有

7种。如图6所示。

![](images/3cbff5e47e44c95cee1f5064bfa710a786737c7ab0792ece7512859cb072bdf1.jpg)  
图7具有4条边的3-一致线性超树

这两个事实表明普通图与超图之间的形成边的细微差别会导致对应结构间的根本性差别。在超图中，顶点间连边方式的多元性使得超图的结构本身更为复杂多样。对于复杂网络的可靠性，将超图模型转换为普通图模型进行的替代研究是不完全等价的。所以针对超图和超网络本身的新的理论和方法的研究是重要的。

# 6 结束语

随着现实世界网络的日益复杂化，超网络成为了探索网络科学的强有力工具。在网络可靠性研究方面，超网络可靠性研究是其重要的组成部分。本文提出并研究了超网络的全终端可靠性。给出了计算在边失效下超网络全终端可靠性的两种基本计算方法：状态枚举法、因式分解法，进而讨论了一些具有特殊结构的超网络的化简。接着研究了超网络可靠性在计算连通生成子超图数目方面的应用。最后从可靠性角度，对普通网络模型和超网络模型进行了比较分析，超网络适合于更广泛意义上的网络建模。

在超网络可靠性方面有很多问题有待进一步探索，归纳为下面三个大的方向：

a）不同可靠性模型定义下的各类可靠性计算方法研究。即使是经历了半个多世纪发展的普通复杂网络的可靠性计算，对于更一般的规模较大的网络的可靠性分析仍然困难重重，超网络可靠性计算有着更宽广的空间。

b）一定条件下超网络可靠性的设计。由于超网络模型具有多元的特点，其可靠性设计将更具有挑战性。

c）可靠性视角下，超网络自身特性的研究。跳出普通复杂网络的思维模式，对超网络本身规律进行探索，能使人们全方位地认识真实的网络世界。

# 参考文献：

[1]吴俊，段东立，赵娟，等．网络系统可靠性研究现状与展望[J]．复 杂系统与复杂性科学,2011,8(2):77-86.(Wu Jun,DuanDongli,Zhao Juan,et al.Status and prospects on network reliability [J].Complex Systems and Complexity Science,2011,8(2):77-86.)   
[2]李晓明．网络可靠性综合的现状及其展望[J].计算机学报，1990,13 (9）:699-7O5.(Li Xiaoming.Current status and trends in the synthesis of reliable networks [J]. Chinese Jaurnal of Camputers,199o,13（9）: 699-705.)   
[3]Beichelt F.Reliability preserving network transformation applications and problems [J]. International Journal of Reliability Quality & Safety Engineering,2008,14(5): 189-199.   
[4] 索琪，郭进利．基于超图的超网络:结构及演化机制[J]．系统工程理 论与实践,2017,37(3):720-734.(Suo Qi,Guo Jinli. The structure and dynamics of hypernetworks [J].Systems Engineering-Theory& Practice,2017,37(3): 720-734.）   
[5]艾毅.超网络可靠性研究[D].成都：西南交通大学，2013.(Ai Yi. Super-network reliability research [D]. Chengdu: Southwest Jiaotong University,2013.)   
[6]胡枫，赵海兴，何佳倍，等．基于超图结构的科研合作网络演化模型 [J]．物理学报，2013,62(19):198901.(Hu Feng，Zhao Haixing，He Jiabei,et al.Anevolving model for hypergraph-structure-based scientific collaboration networks [J].Acta Phys.Sin．,2013,62(19): 198901.)   
[7]Estrada E,Rodriguez-Veläzquez JA. Subgraph centrality and clustering in complex hyper-networks [J].Physica A,2006,364: 581-594.   
[8]刘胜久，李天瑞，洪西进，等.超网络模型构建及特性分析[J].计算 机科学与探索,2017,11(2):194-211. (Liu Shengjiu,Li Tianrui,Hong Shijin,et al.Hypernetwork model and its properties [J].Journal of Frontiers of Computer Science and Technology, 2017,11(2):194-211.)   
[9]索琪，郭进利.超网络中的舆情传播模型及仿真研究[J].计算机应 用研究,2017,34(9):2629-2632.(Suo Qi,Guo Jinli.Spreading model and simulation analysis of Internet public opinion in hypernetworks [J]. Application Research of computers,2017,34(9):2629-2632.)   
[10] Sun L,Wu J,Cai H. The Wiener index of r-uniform hypergraphs [J]. Bulletin of the Malaysian Mathematical Sciences Society,2016,40(3): 1-21.   
[11]胡枫，李发旭，赵海兴．超网络的无标度特性研究[J]．中国科学： 物理学力学 天文学,2017,47(6):060501.(Hu Feng,Li Faxu,Zhao Haixing.The research on scale-free characteristics of hypernetworks[J]. Sci. Sin. $\because$ Phys.Mech.Astron.,2017,47(6):060501)   
[12] Zhang H, Song L,Han Z,Y Zhang.Hypergraph theory in wireless communication networks [M].Cham:Springer,2017.   
[13]马秀娟，赵海兴，胡枫．基于超图的超网络相继故障分析[J].物理 学报,2016,65(8):088901． (Ma Xiujuan，Zhao Haixing，Hu Feng. Cascading failure analysis in hyper-network based on the hypergraph [J].Acta Phys.Sin.,2016,65(8):088901)   
[14]陈廷槐，康泰，姚荣．超图的连通性及容错多总线系统的设计[J]. 中国科学：数学 物理学 天文学 技术科学,1987，17（12）：79-89. (Chen Tinghuai, Kang Tai,Yao Rong.The connectivity of hypergraph and the design of fault-tolerant multibus systems [J]. Sci. Sin. $\because$ Maths. Phys.Astron.Sc1 1echnol.,198/,1/（12）:/9-89.)   
[15]曹其国，孙雨耕．可靠通信网多总线结构的超图设计法[J].电子学 报，1997,25(10):88-90.(Cao Qiguo,Sun Yugeng. The hypergraph design method of multibus structures of reliable communication networks [J].Acta Electronica Sinica,1997,25(10): 88-90.)   
[16] Bondy JA,Murty U SR.Graph Theory [M]. New York: Springer, 2008.   
[17] BergeC.Hypergraphs:combinatoricsoffinitesets[M]. [S.l.]:North-Holland,1989.   
[18]李晓明，黄振杰．图中树的数目：计算及其在网络可靠性中的作用 [M].哈尔滨：哈尔滨工业大学出版社，1999.(Li Xiaoming，Huang Zhenjie.On the number of spanning trees of graphs and applications of networks [M].Harbin:Harbin Institute of Technology Press,1999.)   
[19] Nieminen J,Peltola M.Hypertrees [J].Applied Mathematics Letters, 1999,12: 35-38.   
[20] Katona G Y, Szab6 PG N.Bounds on the number of edges in hypertrees [J].Discrete Mathematics,2016,339(7):1884-1891.   
[21]许小满，孙雨耕，杨山，等．超图理论及其应用[J]．电子学报，1994, 22(8): 65-72.(Xu Xiaoman,Sun Yugeng,Yang Shan. Hypergraph theiry with applications [J].Acta Electronica Sinica,1994,22(8): 65-72.)   
[22] Gu Xiaofeng，Lai Hongjian．Realizing degree sequenceswith k-edge-connected uniform hypergraphs [J].Discrete Mathematics.2013, 313:1394-1400.   
[23] Jain S P,Gopal K.An eficient algorithm for computing global reliability of a network [J].IEEE Trans on Reliability，1988,37(5): 488-492.   
[24] Moskowitz F.The analysis of redundancy networks [J].IEEE Trans on Communications and Electronic,1958,39: 627-632.   
[25]Mine H.Reliability of physical systems [J].IEEE Trans on Circuit Theory,1958,CT6:138-151.   
[26] Satyanarayana A,Chang MK.Network reliability and factoring theory [J].Networks,1983,20:107-120.   
[27] Page L B,Perry JE. Combining vertex decompositions with factoring in an all terminal network reliability algorithm [J].Microelectronics Reliability,1990,30(2):249-262.