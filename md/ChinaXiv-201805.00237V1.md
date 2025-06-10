# 加权有向网络中心节点识别的分解算法研究

刘臣，李丹丹，韩林，安咏雪(上海理工大学管理学院，上海 200093)

摘要：目前复杂网络节点重要性识别算法主要集中在无权、无向网络上，不能全面地描述真实世界复杂网络的情况。例如，大部分中心性度量方法仅仅考虑单一指标，忽略了节点出度与入度的差异，且忽视了权重的重要性。基于有向加权复杂网络，综合考虑节点出度与入度的差异，以及权值在真实网络中的实际重要性，提出了一种基于出度、入度和权值的中心节点识别算法——cW-壳分解算法。为了验证该算法的有效性，利用W-SIR传播模型在真实复杂网络上进行病毒传播仿真实验，结果表明，cW-壳分解方法能够有效地对节点进行分级排序，识别出具有高扩散能力的节点。

关键词：交叉度；c-壳；k-壳；节点重要性；传播动力学 中图分类号：TP301.5 doi: 10.3969/j.issn.1001-3695.2017.06.0648

# Decomposition algorithms of center node in directed-weighted network

Liu Chen, Li Dandan, Han Lin, An Yongxue (Business School,University ofShanghai for Science&Technology,Shanghai 2Oo093,China)

Abstract:The existing evaluation methods for node importance in complex network mainly focus on un-directed and unweighed networks,andcan'tdescribe thereal-world network completely.For example,mostcentrality measures onlyconsider asingle indicator,ignoringthedierencebetweenout-egreeandin-degreeoftheode,andnglectingtheimportanceofweight. Based on the directed-weighted complex network，this paper proposes a center node recognition algorithm，cw-shel decomposition method,whichisbasedonout-degre,in-degreeand weight,considering thediference betweenout-degreeand in-degreeofthe node,andthe practical importanceof weight inreal network.Inordertoverifytheeffectivenessof the new index,the weighted-susceptible-infectious-recovered modelisusedtosimulate spreading processonreal-worldnetworks.The results showthathecw-shelldecompositionmethodcanranktheodesefficiently,andidentifythnodes withigherdifusion ability.

Key Words: cross degree; c-shell; k-shell; node importance; transmission dynamics

# 0 引言

随着信息科技的迅猛发展，复杂网络渗入人类生活的方方面面。无论是病毒的传播，还是观点谣言的扩散，“谁是网络中最重要的节点？如何有效扩散信息？”，成为学者们关注的热点。Goel等人[通过对七个在线平台数据的观察收集，发现大部分的级联是小而且浅的，并且可以通过一些相似的树结构进行描述。提出即使存在一些大的级联，也是得益于媒体效应，例如粉丝们对喜欢的歌手或者产品的热切关注。所以作者建议，为了扩大网络传播范围，网络营销者和相关研究人员应该降低分享成本，摸清楚人群中的中心节点群，把注意力放在加强重要节点的传播潜力上。

如何识别重要节点，已有大量的研究，例如，用于无向网络中节点重要性排序的几个常用指标有度值、介数、k-壳值等，用于有向网络中节点重要性排序的两个经典算法一一HITS 算法和PageRank 算法都是来自WWW上的网页排序[2\~5]。

Newman等人[6通过对电子邮件网络的研究结果表明，去掉网络中度最大的节点后，网络会变得非常脆弱。度指标计算简单，时间复杂度低，适合大型网络。然而，度指标只反映了节点局部特征，没有对邻接节点的连接状况进行描述。Freeman[7用介数定义了节点的重要性，即经过某个节点的最短路径的数目，它刻画了节点i对于网络中节点对之间沿着最短路径传输信息的控制能力。然而，介数因需要计算最短路径而导致算法的时间复杂度较高，不适用于大型复杂网络。Kitsak等人[8提出节点在网络中的位置是影响其重要性的主要因素，在单个传播源的情况下，最具影响力的节点并非是那些度最大或者介数最大的节点，而是k-壳值最大的节点。k-壳指标时间复杂度低，适用于大型网络，而且比度、介数指标更能准确识别在疾病传播中最有影响力的节点。然而， $\mathbf { k } .$ -壳分解方法不适用树状网络、BA网络，因为该类网络的所有节点ks值相等，从而导致 ks 指标无法度量其节点的重要性。Bryan 等[9提出的PageRank算法是用于搜索引擎中网页排序的经典算法，可用于有向网络。PageRank 算法的基本思想是，WWW上一个页面的重要性取决于指向它的其他页面的数量和质量。然而，当网络中存在孤立节点或社团时，会出现排序不唯一的问题。Kleinberg[10]于1998 年提出 HITS 算法，其基本思想是，每个网页的重要性有两种刻画指标一一权威性和枢纽型。HITS算法在学界应用较为广泛，由于它需要的迭代次数更少，收敛速度更快，减少了时间复杂度。然而HITS不能识别非正常目的的网页引用，导致计算结果与实际有偏差。

周立欣等人[11]在 $\mathbf { k } .$ -壳分解方法的基础上提出适用于有向网络的c-壳分解方法，证明了该方法具有较好的区分度，能够识别有向网络中的重要节点。然而，c-壳分解方法无法直接应用于加权网络。

大多数的中心性方法，包括 $\mathbf { k }$ -壳分解法，都是在无权网络的情形下设计的。然而，真实的网络是加权的，而且他们的权重描述了基础系统的性能属性。例如，在经济贸易网络中，权重表示着一些测量属性，如贸易流，资金流等。在一个加权网络，节点至少可以通过两个属性进行描述，度和权重。然而权重是网络链接的属性，因此一个节点的权重可以通过计算通过该节点的所有链接的权重之和来定义[12]。在一个网络中即存在高度低权重的节点，也存在低度高权重的节点。在以往的研究中有两种主要的方法，一种办法是完全忽视权重。另一种是只考虑权重超过任意选择的阈值的链而过滤掉剩余的部分。这种方法的缺点是需要选择一个适当的权重临界值。这样的话可能会删除低权重而度高的节点（低于阈值)。另外，通过忽略低于阈值的链接，会使得网络中的一些节点断开链接而变得越来越稀疏[12]。

针对上述问题，本文提出了一种基于出度、入度和权重的节点重要性评价指标，交叉度(cw)指标，并提出了一种通用的方法对加权有向网络进行cw-壳分解。对美国航空网和青少年健康网络的仿真结果表明：该指标能有效的度量节点的重要性。本文的结构安排如下：首先介绍了基于壳数分解的中心节点识别算法，并提出了cw-壳分解方法。然后，利用W-SIR传播模型在真实复杂网络上模拟病毒传播仿真实验，验证方法的有效性。最后提出结论。

# 1 加权有向网络中心节点识别算法

# 1.1基于壳数的中心节点识别算法

# 1.1.1k-壳分解算法

Kitsak等人[8]于2010年首次提出了节点在网络中的位置是影响其重要性的主要因素，在单个传播源的情况下，基于SIR和SIS模型以及实际网络数据证明了，最具影响力的节点并非是那些度最大或者介数最大的节点，而是k-壳值最大的节点。然而，k-核很小的节点中也存在对网络的传播动力学产生巨大影响的节点，然而传统的k-核分解方法无法对这部分节点的传播能力进行度量[13]。此外，k-壳分解方法不适用树状网络、BA网络，因为该类网络的所有节点ks值相等，无法衡量节点的重要性。

$\mathbf { k }$ -壳分解方法通过递归地移除网络中所有度值小于等于K的节点，揭示网络的壳结构性质和网络的层次性质[13]。

设网络 $\scriptstyle { \mathrm { G = } } ( \mathrm { E } , \mathrm { V } )$ 是由V个节点和E条连边组成的网络。k-壳定义：由集合推导出的子网络 $_ \mathrm { H = ( C , E / C ) }$ ,满足C中任意节点V，其度值均大于k的最大子网络被称为 $\mathbf { k }$ -核，其中属于k-核但不属于 $( \mathbf { k } { + } 1 )$ -核的那部分节点称为 $\mathbf { k }$ 壳，简称ks。

# 1.1.2基于交叉度的c-壳分解算法

该方法是把有向网络转变为无向网络，再进行经典的 $\mathbf { k }$ 壳分解。在有向网络重要节点的识别过程中，度指标将节点的入度和出度简单相加，无法有效区分两者的差异[12]。节点交叉度（crossdegree）的物理意义是一个节点的邻接点之间的连线穿过该节点的次数。节点的交叉度用 $k ^ { \mathrm { c } }$ 表示：

$$
k ^ { c } = \left( k ^ { i n } + 1 \right) ^ { \lambda } \left( k ^ { o u t } + 1 \right) ^ { 1 - \lambda } - 1
$$

$\lambda$ 的不同取值影响节点的交叉度值，从而区分节点的出度与入度的重要性。式(1)中，作者在网络中额外增加一个节点，并且将它与已有的所有节点双向链接，于是得到 $\mathbf { n } { + } 1$ 的网络，这样就能够度量出度或入度为零的节点重要性，因此这个新的网络是强连通网络。

基于图1，对网络进行c-壳分解，对交叉度指标进行论证。c-壳分解法是把有向网络转变为无向网络，再进行经典的k-壳分解。该方法适合 $\mathbf { k }$ -壳分解方法的分级过程。但是，是基于交叉度的替代度量。计算结果如表1所示。

![](images/dec725c42f125b768feac5e95a9723dfddfcf712afed160ad8fd4e004cbd9790.jpg)  
图1有向网络图

表1c-壳分解结果  

<html><body><table><tr><td>c-壳</td><td>k值</td><td>节点</td></tr><tr><td>1-壳</td><td>k=0.4142</td><td>9,10,11,13,14,15,16,17</td></tr><tr><td>2-壳</td><td>k=1.0000</td><td>8</td></tr><tr><td>3-壳</td><td>k=1.4494</td><td>2,3,4,6,7</td></tr><tr><td>4-壳</td><td>kc=1.6458</td><td>1</td></tr><tr><td>5-壳</td><td>k=2.4641</td><td>12</td></tr></table></body></html>

由于最小k-核节点的ks值相同，而且根据 $\mathbf { k }$ 核分解原理，度为1以及大部分介数为0的节点属于最小 $\mathbf { k }$ -核节点，因此仅仅依靠节点自身k-核、度或介数信息不能很好的区分这类节点的传播能力[13]。根据表1，可以得出交叉度指标可以用于识别最小k-核节点中对网络传播重要的节点，且具有更高的区分度能够识别出有向网络中的重要节点。

周立欣[I等人通过在SIR 模型上进行仿真实验，研究交叉度值与度值都相同的节点在网络中的平均传播范围 $\mathbf { M } ( \mathbf { k } ^ { \mathrm { { c } } } , \mathbf { k } )$ 从而对比分析c-壳分解方法与度方法在准确识别重要节点方面的差异。结果表明 ${ \bf k } ^ { \mathrm { c } }$ 值越大的节点在网络中的平均传播范围$\mathbf { M } ( \mathbf { k } ^ { \mathrm { { c } } } , \mathbf { k } )$ 就越大。 ${ \bf k } ^ { \mathrm { c } }$ 值相近的节点，其传播能力相近，且 $\mathbf { M } ( \mathbf { k } ^ { \mathrm { { c } } } ,$ （204k)的取值与节点的度值关联很小。度值相同的节点，其传播能力却存在明显的差异，且表明了网络中存在度值很大而传播能力有限的节点。同理，证明了 $\mathrm { c } -$ 壳分解算法比介数中心性方法更能准确的衡量节点的传播能力和重要性程度。

但是，c-壳分解方法无法直接用于加权网络。因此本文提出交叉点权的概念。

# 1.2cw-壳分解算法

# 1.2.1交叉点权

这个方法考虑了节点的出度和入度，以及与邻接节点连边的权重因素。而一个节点的权重可以表示为经过该节点的所有链接的权重之和，因此为每个节点分配交叉点权。一个节点i的交叉点权被定义为：

$$
c w _ { i } = \left( \sum _ { j \in N } w _ { i j } + 1 \right) ^ { \lambda } \left( \sum _ { j \in N } w _ { j i } + 1 \right) ^ { 1 - \lambda } - 1
$$

其中:N 为节点i的邻节点集合， $\sum _ { j \in N } w _ { i j }$ 是所有以节点i为起点的连边的权重之和, $\sum _ { j \in N } w _ { j i }$ 是所有以节点i为终点的连边的权重之和.参数 $\lambda$ 的意义同上文，是为了区分出度与入度的重要性。本文，仅讨论 $\lambda = 1 / 2$ 的情况，这样就认为入度和出度同样重要。因此,

$$
c w _ { i } = \sqrt { \left( \sum _ { j \in N } w _ { i j } + 1 \right) \left( \sum _ { j \in N } w _ { j i } + 1 \right) } - 1
$$

在不加权的网络中，即 $\mathrm { \Delta \ w _ { i j } = 1 }$ ，一个节点的交叉点权等同于交叉度，这样可以使用 $\mathsf { c } \cdot$ 壳方法继续同一网络的分层。

# 1.2.2基于交叉点权的cW-壳分解算法实现过程

cw-壳分解法是把加权有向网络转变为无权无向网络，再进行经典的 $\mathbf { k }$ -壳分解。该方法适合k-壳分解方法的分级过程，但是，是基于交叉点权的替代度量。cw-壳分解算法通过递归地移除网络中所有cW 值小于或等于 $c w _ { \mathrm { m i n } }$ （网络中最小的cW值）的节点，从而将网络划分为若干层，每一层壳的节点的cw值相等。具体的算法实现过程如下：

a)根据式(3)，计算网络中所有节点的cW值;b)依次移除网络中所有cW值小于或等于 $c w _ { \mathrm { m i n } }$ 的节点，并移除节点与其邻接点的连边。此时剩下的网络中可能有出现一些新的 $c w$ 值小于或等于 $c w _ { \mathrm { m i n } }$ 的节点，再把这些节点与其邻接点的连边移除。重复此操作直至网络中不再有 $c w$ 值小于或等于 $c w _ { \mathrm { m i n } }$ 的节点为止。被移除的节点的集合，称为网络的cw-壳。余下的节点的集合称为网络的cw-核;

c)继续剥壳操作，重复a)b)，直至网络中所有节点都被移除。节点的cW值越大，表明节点与接近cw-壳分解的最内层，影响力越大。通过cw-壳分解算法能够确定所有节点在网络中所处的层级，并给出节点的重要性排序，识别网络的中心节点。

# 1.2.3实例

为了突出未加权方法的缺陷，假设网络加权，基于图1，假设 $\mathrm { W } _ { 1 , 1 0 } { = } 2 . 5$ ， $\mathrm { W } _ { 5 , 1 2 } { = } 3 . 5$ ， $\mathrm { W } _ { 1 , 6 } { = } 0 . 5$ ， $\mathrm { W } _ { 3 , 7 } { = } 0 . 5$ ， $\mathrm { W } _ { 1 2 , 1 7 } { = } 2$ ， $\mathrm { W } _ { 4 , 3 } { = } 2$ 其余均为1。依据cw-壳分解方法对图1网络进行分解。结果如表2所示。

表2cw-壳分解结果  

<html><body><table><tr><td>cw-壳</td><td>cw值</td><td>节点</td></tr><tr><td>1-壳</td><td>cw=0.4142</td><td>8,9,11,13,14,15,16,17</td></tr><tr><td>2-壳</td><td>cw=0.5811</td><td>6,7</td></tr><tr><td>3-壳</td><td>cw=0.7321</td><td>17</td></tr><tr><td>4-壳</td><td>cw=0.8708</td><td>10</td></tr><tr><td>5-壳</td><td>cw=1.1213</td><td>1,2,3,4,5,12</td></tr></table></body></html>

依据 $\mathbf { k }$ -壳分解方法，节点10 将被放置在网络的边缘，即$\mathrm { k } _ { \mathrm { s } } { = } 1$ ，即使它是强连接到核心节点中的一个。在真实网络这种强连接链路，表示该特定节点是更为重要的[8]。但这不是能通过k-壳分解方法所计算出的层状结构能够进行描绘的。因此通过cw-壳分解方法计算出 $c w _ { 1 0 } = 0 . 8 7 0 8$ ， $c w _ { 1 1 } = 0 . 4 1 4 2$ ，节点10的重要性就高于节点11的重要性，这样就突出了其实际重要性。

# 2 cw-壳分解算法的有效性分析

本节介绍了cw-壳算法在真实复杂网络中的应用。首先，在Koblenz网站获得数据集，进行数据描述。然后，使用cw-壳算法进行网络分解，得到网络cw-壳结构，确定网络节点的中心程度。最后，利用W-SIR 模型模拟病毒传播仿真实验，检验中心程度不同的节点在网络中的传播范围和重要性程度，从而验证cw-壳分解算法的有效性。

# 2.1 数据集

通过Koblenz 网站获得如下数据集，如表3所示。

a）Adolescenthealth：这是1994年的一个有关青少年友谊关系的调查。节点表示学生，有向边表示学生甲选择学生乙作为朋友。权重表示两者的亲密程度，值越大，关系越密切。节点之间没有连边，表示无往来。

b）USairport：这是2010年的美国机场运作网络。节点表示机场，有向边表示飞机由机场A飞向机场B，权重表示该方向飞行的次数。

表3复杂网络数据集  

<html><body><table><tr><td>网络</td><td>网络类型</td><td>NN</td><td>NE</td><td>K</td><td>C</td><td>d</td></tr><tr><td>Adolescent health</td><td>D+</td><td>2539</td><td>12969</td><td>10.216</td><td>14.20%</td><td>10</td></tr><tr><td>US airport</td><td>D+</td><td>1,574</td><td>28,236</td><td>35.878</td><td>38.40%</td><td>8</td></tr></table></body></html>

表3中，给出了网络的一些详细的统计性质。 $\mathrm { D } +$ 表示该网络是加权有向网络， $\mathrm { N _ { N } }$ 是节点总数， $\mathrm { N } _ { \mathrm { E } }$ 边数， $\mathbf { k }$ 网络的平均度，C网络平均聚类系数，d直径。

# 2.2W-SIR模型

近年来，SIR模型被用于网络研究，用来探索疾病传播，经济危机蔓延，以及信息和谣言传播等[14-18]。由于感兴趣的是加权网络，所以把有关权重的概念引入到SIR模型,如公式4。这个模型最初是为了模拟经济危机的传播[19]，它假设节点i以概率Pij感染节点j，且每个链路感染的概率不同，公式：

$$
p _ { i j } \propto m \cdot w _ { i j } / \nVdash
$$

其中: $w _ { i j }$ 是以节点i为起点，以节点j为终点的所有链的总权重。是以节点j为终点的所有链的总权重。比率 $w _ { i j } / \$ %被用来作为节点j被节点i感染可能性的一个因素。 $\mathbf { m }$ 是可以扩大的自由参数，例如危机的严重性，一种病毒是如何传染的，一个谣言的重要性等。这个模型称为加权SIR 模型(W-SIR)。

W-SIR的建模过程如下。首先，将所有的节点定义为易感染者S。接着，选择一个节点i，并且被假定为被感染者I。这个节点会在第一时间里以概率 Pij感染其相邻节点。这将导致所有被感染的节点由状态S转换为I，而发起这个过程的节点转换为R状态，并不能再感染其他节点或被感染。不断重复上述步骤，并且所有被感染的节点都试图感染它的邻接S节点。这个过程一直持续到网络中没有可以被感染的节点或者所有的节点都已被感染为止。

# 2.3仿真分析

对于给定的m值，对每个单独的节点，在W-SIR 模型上进行100次实验，每一个节点的感染能力都是这100次实验实现的平均值。然后根据cw-壳分解方法得到的壳结构，分析每层壳的传染能力。

# 2.3.1cW-壳分解方法的精确度

首先，分别依据节点的度，介数和cw-壳分解方法分解网络，得到该网络的壳结构，并根据节点距核心的距离为得到壳排序。然后，计算每层壳的所有节点平均感染范围，估计壳的传播潜力。如图2所示。

图2中，通过cW-壳的分解方法获得的中心节点能够引发感染的暴发，且距离核心越近，感染能力越强。意味着cw-壳分解方法能够定位具有较高平均扩散能力节点，并把它放置在离核心近的位置。

为了进一步给出量化比较，可以通过计算不精确函数 $\varepsilon ( p )$ 来衡量这些指标对节点重要性的识别准确度[20]，公式如下：

$$
\varepsilon _ { \scriptscriptstyle c w } ( p ) \equiv 1 - M c w / M _ { \scriptscriptstyle e f f }
$$

$$
\varepsilon _ { k } ( p ) \equiv 1 - M _ { k } \mathrm { \Gamma } / M _ { e f f }
$$

$$
\varepsilon _ { \scriptscriptstyle C B } ( p ) \equiv 1 - M _ { \scriptscriptstyle C B } / M _ { \scriptscriptstyle e f f }
$$

显然，当 $\varepsilon ( p )$ 越小时，说明该指标的精确度越高，传播能力越强，能够更加有效地识别出网络中的中心节点。

![](images/97b5f0989b78ca99a1379828e3e8dc03031b870ab04369f10a2e9375cc4b0551.jpg)  
图2网络Adolescent health $( \mathrm { m } { = } 5 )$ ,USairport $( \mathrm { m } { = } 1 )$ 每层壳距核心距离与该层壳所有节点平均感染能力的关系比较

图3表明，随着选取比例 $p$ 的不断增加，各个指标的准确性不断增加。对于网络USairport $\mathrm { { ( m { = } 1 ) } }$ ，当 $p$ 小于 $1 . 5 \%$ 时，$\varepsilon _ { c w } ( p ) < \varepsilon _ { k } ( p ) < \varepsilon _ { C B } ( p )$ ，即cw-壳分解方法的误差均小于度指标和介数指标，表明cw-壳分解方法比度指标和介数指标更加的准确。对于网络Adolescenthealth $( \mathrm { m } { = } 4 )$ ，总有，$\varepsilon _ { k } ( p ) < \varepsilon _ { c w } ( p ) < \varepsilon _ { C B } ( p )$ ，即cw-壳分解方法的误差小于介数指标，表明cw-壳分解方法比介数指标更加的准确。相比于另外两种方法，基于介数识别最有效传播者的方法最不准确。由仿真结果可以得出，cw-壳分解方法更能够合理有效地对节点进行分级排序，把具有高扩散能力的节点放置在离核心近的位置。

# 2.3.2每层壳的同质性

为了验证cw-壳分解方法的准确性，文中测试了每层壳的同质性，即同一层壳的所有节点应具有相似的感染能力。为了做到这一点，在给定的 $\mathrm { ~ m ~ }$ 值下，依据cw值对网络分层，层数用r表示，总的节点数用n表示。则此次验证就可以看做：在因素 $\mathbf { r } -$ 壳的不同水平下，每层壳的感染能力是否有显著性差异的单因素方差分析。即判断网络分层结构对节点感染能力是否有显著差异。数据如表4所示。

依据单因素方差分析的数学模型，计算组内离差平方和QE和组间离差平方和QA[21]。

选择检验统计量F值：

$$
F = \frac { \overline { { Q } } _ { A } } { \overline { { Q } } _ { E } } = \frac { ( Q _ { A } / \left( r - 1 \right) ) } { ( Q _ { E } / \left( n - r \right) ) } = \frac { \sum _ { i = 1 } ^ { r } n _ { i } \left( \overline { { M } } _ { i } - \overline { { M } } \right) ^ { 2 } } { \sum _ { i = 1 } ^ { r } \sum _ { j = 1 } ^ { n _ { i } } \left( \overline { { M } } _ { i j } - \overline { { M } } \right) ^ { 2 } }
$$

在检验假设成立条件下，对于给定的显著性水平α，可以通过F临界表中查到Fα(r-1,n-r)的值。

表5、6为方差分析表：对 $\mathrm { ~ a ~ } { = } 0 . 0 5$ ，从显著性概率看， $\scriptstyle \mathbf { P < } 0 . 0 5$ 说明几组数据之间有显著差异。即，使用cw-壳分解方法得到的壳结构，可以有效的对网络进行分层排序，得到同质性强的壳结构。此外，还可以通过配对比较，计算每层壳两两之间的差异性，可以进一步验证每层壳的同质性。总之，使用cw-壳方法可以有效的对网络进行分解。对于给定的cw-壳值，处于同一cw层的节点具有相似的感染能力，且最有效的传播者位于cw-壳分解的最内层，具有最大的cw值。

# 3 结束语

![](images/1cbe11502343345b84a10c81f36f4940426a22e9c769d0250283c15eb22565af.jpg)  
图3cw-壳分解方法与度指标、介数指标不精确函数对比

本文提出了一种通用的旨在识别加权有向网络中心节点的方法，cw-壳分解方法。该方法综合考虑了节点出度与入度的差异，以及权值在真实网络中的实际重要性，对美国航空网和青少年健康网络的仿真研究表明，采用cw指标可以有效地对网络节点进行重要性排序，得到同质性强的壳结构，能够识别出具有高扩散能力的节点。在用cw 指标与度指标和介数指标相较时，由于度指标和介数指标均不考虑边的方向和权值要素，所以比较的结果并不理想。另外，本文仅讨论 $\lambda = 1 / 2$ 的情况，即默认出度和入度同等重要，但是对于不同的网络，出度和入度的影响力是不同的。因此需要根据特定的网络，进一步讨论的取值。

<html><body><table><tr><td>表4</td><td>网络分壳结果</td></tr><tr><td>感染能力M壳</td><td>每层壳每个节点的M值</td></tr><tr><td>1-壳</td><td>M11M12 M13</td></tr><tr><td>2-壳</td><td>M21 M22 M23..</td></tr><tr><td>3-壳</td><td>M31M32M33.</td></tr><tr><td></td><td></td></tr><tr><td>r-壳</td><td>Mr1 Mr2 Mr3.</td></tr></table></body></html>

为了检验网络分层结构对节点感染能力是否有显著差异，本文选择统计软件 SPSS 进行One-wayANOVA分析，即单因素方差分析（ $\mathrm { ~ a ~ } { = } 0 . 0 5$ )。

运行结果如表5、6所示。

表5网络Adolescenthealth $( \mathrm { m } { = } 4 )$ 每层壳感染能力的方差分析表  

<html><body><table><tr><td>方差来源</td><td>离差平方和</td><td>自由度</td><td>均方离差</td><td>F值</td><td>显著性</td></tr><tr><td>组间</td><td>14.053</td><td>9</td><td>1.561</td><td></td><td></td></tr><tr><td>组内</td><td>16.459</td><td>2529</td><td>0.007</td><td>239.935</td><td>0.000</td></tr><tr><td>总和</td><td>30.512</td><td>2538</td><td></td><td></td><td></td></tr><tr><td>表6</td><td>网络USairport (m=1)每层壳感染能力的方差分析表</td><td></td><td></td><td></td><td></td></tr><tr><td>方差来源</td><td>离差平方和</td><td>自由度</td><td>均方离差</td><td>F值</td><td>显著性</td></tr><tr><td>组间</td><td>9.825</td><td>6</td><td>1.638</td><td></td><td></td></tr><tr><td>组内</td><td>10.981</td><td>1567</td><td>0.007</td><td>233.677</td><td>0.000</td></tr><tr><td>总和</td><td>20.807</td><td>1573</td><td></td><td></td><td></td></tr></table></body></html>

# 参考文献：

[1]Goel S,Watts D J,Goldstein DG.The structure of online diffusion networks [C]//Proc of the 13th ACM Conference on Electronic Commerc.New York: ACMPress 2012:623-638.   
[2]刘建国，任卓明，郭强，等．复杂网络中节点重要性排序的研究进展 [J]．物理学报,2013,62(17):178901-178901.   
[3]李翔，刘宗华，汪秉宏．网络传播动力学[J].复杂系统与复杂性科学, 2010, 7 (Z1): 33-37.   
[4]Pei S,MuchnikL,JrAJ,etal. Searching for super spreaders of information in real-world social media.[J]. Scientific Reports,2014,4: 5547-5547.   
[5]任卓明，邵凤，刘建国，等．基于度与集聚系数的网络节点重要性度量 方法研究[J]．物理学报,2013(12):128901-128901.   
[6]Newman MEJ,Forrest S,Balthrop J.Email networks and the spread of computer viruses.[J].Physical Review E.2002,66 (3 Pt 2A): 035101.   
[7]Freeman L C.A set of measures of centrality based on betweenness.[J]. Sociometry,1977,40(1): 35-41.   
[8]Kitsak M, Gallos LK,Havlin S,etal. Identifying influential spreaders in complex networks [J]. Nature Physics,2010,6(11): 888-893.   
[9]Bryan K,Leise T.The \$25,Ooo,Ooo,Ooo Eigenvector: the linear algebra behind google [J]. Siam Review,2006,48 (3): 569-581.   
[10] Kleinberg JM.Authoritative sources in a hyperlinked environment [J] Journal of the ACM,1999,46 (5): 604-632.   
[11]周立欣，刘臣，霍良安，等.基于交叉度的有向加权网络中心节点识别 算法研究[J].计算机应用研究,2015,33(11):1-1.   
[12] GarasA,Schweitzer F,Havlin S.A k-shell decomposition method for weighted networks [J].New Journal of Physics,2012,14(8): 083030.   
[13]任卓明，刘建国，邵凤，等．复杂网络中最小k-核节点的传播能力分析 [J]．物理学报,2013(10):108902.   
[14]王长春，陈超，董志强．网络结构对谣言传播的影响[J]．系统仿真学 报,2013,25(1):127-131.   
[15] Moreno Y,Nekovee M,Pacheco AF.Dynamics of rumor spreading in complex networks [J].Physical ReviewE,2004,69 (6 Pt2): 066130.   
[16]葛新，赵海，张君．可变相关系数网络病毒传播仿真研究[J].系统仿 真学报,2012,24(8):1723-1727.   
[17]Borge-Holthoefer J,Moreno Y.Absence of influential spreaders in rumor dynamics [J].Physical Review E,2011,85 (2Pt2): 026116.   
[18] Klemm K, Serrano MA,Eguiluz VM,et al.A measure of individual role in collective dynamics [J]. Scientific Reports,2010,2(2): 292.   
[19] Garas A,Argyrakis P,Rozenblat C,et al.Worldwide spreading of economic crisis [J].New Journal ofPhysics,2010,12 (2):185-188.   
[20]汪小帆，李翔，陈关荣．网络科学导论[M].北京：高等教育出版社， 2012.   
[21]师义民，徐伟，秦超英，等.数理统计[M].3版．北京：科学出版社, 2009.