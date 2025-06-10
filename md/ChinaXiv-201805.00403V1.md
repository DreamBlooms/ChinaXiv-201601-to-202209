# 基于差异路径权重的二部图网络推荐算法

高长元ab，段文彬a，张树臣a,b

(哈尔滨理工大学a.经济与管理学院,b.高新技术产业发展研究中心，哈尔滨150040)

摘要：针对二部图网络结构推荐算法中资源分配不合理的现象，同时为了丰富推荐结果多样性和促进冷门物品的推荐，提出了一种利用差异路径权重改变资源传递的二部图网络结构算法。利用用户相似性构造路径权重改变第一阶段资源传递规则，使资源较多地流向与目标用户相似的用户节点。通过物品属性相似的构造路径权重，使第二阶段资源更多地流向与目标用户已购物品具有相似属性的物品。实验结果表明，本算法相对于其他流行网络结构算法提高了推荐的综合性能，并且更好地解决推荐中的相关问题。

关键词：二部图网络结构；差异路径权重；推荐算法；用户相似性；物品属性中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.09.0905

# Recommendation algorithm for bipartite graph network structure based on differential path weight

Gao Changyuana,b,Duan Wenbina, Zhang Shuchena, b (a.CollegeofEconomic&Management,.High-techIndustrialDevelopmentResearchCenter,HarbinUniversityofScience &Technology,Harbin 150040,China)

Abstract:This paperisaimedat theunreasonableallocationofresource intherecommendationalgorithmofbipartitenetwork, andin orderto enrichthediversityofrecommended resultsand promote therecommendation ofunpopular items.This paper proposes the algorithmforbipartite graph network structure,whichuses differential path weight tochangeresource delivery.It changes the first stageofresource transfer rulesbyusersimilarity to construct path weights and maketheresources flow more towardstheusernodessimilartothetargetusers.Throughtheconsiderationofconstructingpathweightofthearticlesatributes similarity,the second stageresources aremorelikelytoflowtotheobjectswhichhavesimilaratributes withthetargetusers' purchased products.Experimental results show that the proposedalgorithm improves the combination property of recommendation,and better solves therelated problems inrecommendation,whichoutperforms other popular network structure algorithms.

Key Words: bipartitenetworkstructure;diferentialpath weight;recommendationalgorithm;usersimilarity;articlesatribte

# 0 引言

随着互联网的快速发展，社会和企业信息化的逐步成熟，越来越多的数据通过多种终端产生并服务于人们的生活之中。海量的数据随之而来引发了“信息过载”问题[11，致使能满足用户需求的推荐系统迅速发展。推荐算法是推荐系统中极为重要的一个模块，主要负责选择符合用户兴趣的信息或者物品并推荐给用户，目前主流的推荐算法有协同过滤推荐算法（collaborative filtering recommendation algorithms, CFRA）、基于内容的推荐算法(content-based recommendation algorithms,

CBRA)[2]、基于知识的推荐算法(knowledge-basedrecommendationalgorithms,KBRA)[3]、基于二部图网络结构推荐算法(bipartite network structure recommendation algorithms,BNSRA)[4]。其中二部图网络结构推荐算法由于推荐物品多样性较好且不受物品种类的限制，越来越受到研究推荐的学者欢迎。

目前CFRA的研究较为系统并且众多电子商务平台也使用该算法，但是部分学者经过大量实验证实了BNSRA在推荐效率和精准度上较优于传统的CFRA[4]。BNSRA将系统中存在的用户和物品虚拟化为二部图网络中的点，系统中的购买关系形成了网络中点之间的连线。目前越来越多研究推荐的学者尝试对BNSRA进行优化研究，随着扩散动力学与热传导的引入，BNSRA主要转向了基于物质扩散的BNSRA（materialdiffusionbipartite network,MDBN）[6]和基于热传导的BNSRA(heatconductionbipartite network,HCBN)[7]两大改进方向。并且不同的学者也主要从改进初始资源分配[8]、降低流行性、满足用户个性化[9]、消除冗余属性、考虑物品内容[10]、基于社团划分[I]、考虑时间效应[12]以及组合算法[13]等八个角度去优化提高BNSRA性能，并且丰富算法推荐物品种类以及弥补冷门物品推荐上的不足。

目前传统的推荐算法通常倾向于将比较流行的物品推荐给用户，然而并没有顾及到用户需求多样化。因此，丰富推荐物品种类的多样性以及增加对冷门物品的推荐，对于推荐系统向更多用户服务才更有实际意义。基于此，本文利用用户相似性构建二部图网络结构资源传递路径权重，改变传统资源均等传递情况提高推荐的精准度。同时，为了提高推荐结果多样性和对冷门物品的推荐，本文通过对物品间属性海明距离计算，改变资源从用户向物品传递的规则，增加推荐物品种类。通过实验验证了本文算法在推荐结果精准度以及算法的综合性能都得到提升。

# 1 基于二部图网络结构推荐算法

二部图网络结构推荐算法认为，用户已购买的物品具有向用户推荐其他物品的能力，这种能力是物品依据被选择的情况赋予一定的资源量，通过用户-物品网络向其他物品进行传递。假设目标用户 $\boldsymbol { u } _ { \alpha }$ 购买了系统中的部分物品，则开始时赋予 $\boldsymbol { u } _ { \alpha }$ 每个已购物品的资源量为1。假设一个系统中存在 $m$ 种物品和 $n$ 位用户，设 $O = \{ o _ { 1 } , o _ { 2 } , o _ { 3 } , . . . , o _ { m } \}$ 代表系统中的 $m$ 种物品，$U = \{ u _ { 1 } , u _ { 2 } , u _ { 3 } , . . . , u _ { n } \}$ 代表系统中的 $n$ 位用户。则整个系统中的物品和用户可以构成一个 $m$ 行 $n$ 列的关系矩阵 $a _ { \alpha i }$ ，其中$i = \{ 1 , 2 , 3 , . . . , m \}$ ， $\alpha = \{ 1 , 2 , 3 , . . . , n \}$ 。关系矩阵 $a _ { \alpha i }$ 的取值如下所示：

$$
a _ { \alpha i } = \left\{ \begin{array} { l l } { { 1 , { u _ { \alpha } } \mathrm { j } \underline { { { \# } } } \mathrm { j } \mp \mathrm { k } \mathrm { i } \mp \mathrm { \overrightarrow { { R H } } } \mathrm { \Gamma } } _ { { \mathrm { H H } } { \bf { 0 } } _ { i } } ^ { \ast } } \\ { { 0 , { u _ { \alpha } } \mathrm { \neq } \mathrm { i } \underline { { { \# } } } \mathrm { j } \pm \mathrm { \overrightarrow { { R H } } } \mathrm { \Gamma } } _ { { \mathrm { H H } } { \bf { 0 } } _ { i } } ^ { \ast } } \end{array} \right.
$$

当 $a _ { \alpha i } = 1$ 时，用户 $\textstyle u _ { \alpha }$ 和物品 $o _ { i }$ 之间形成一条连线，同时物品 $o _ { i }$ 被赋予了一个单位的资源量；若未被选择，则初始资源量为零。二部图网络结构资源传递过程如图1所示。

美 國

初始资源从物品层经过物品与用户的选择关系平均分配到用户层。经过第一阶段的资源变动，用户 $u _ { \iota }$ 获得的资源量为

$$
f ( u _ { l } ) = \sum _ { i = 1 } ^ { m } { \frac { a _ { l i } } { k ( o _ { i } ) } }
$$

其中: $k ( o _ { i } )$ 为物品节点 $o _ { i }$ 的度，即物品 $o _ { i }$ 被选择的数量。第二阶段资源会由用户层的每个用户节点经过选择关系流向物品层，则物品节点 $o _ { j }$ 的资源量为

$$
f ( o _ { j } ) = \sum _ { l = 1 } ^ { n } \frac { a _ { l j } f ( u _ { l } ) } { k ( u _ { l } ) } = \sum _ { i = 1 } ^ { m } \sum _ { l = 1 } ^ { n } \frac { a _ { l j } } { k ( u _ { l } ) } \frac { a _ { l i } } { k ( o _ { i } ) } = \sum _ { i = 1 } ^ { m } w _ { i j }
$$

其中: $k ( u _ { l } )$ 为用户节点 $u _ { \iota }$ 的度，即用户购买物品数。 $w _ { i j }$ 表示物品$o _ { i }$ 对 $o _ { j }$ 推荐的资源贡献量。针对具体的目标客户，将物品按照新资源量由大到小排序，取排序中前 $\boldsymbol { L }$ 个物品作为推荐系统中推荐给目标用户的推荐结果。

# 2 改进的二部图网络结构推荐算法

# 2.1引入用户相似性构建路径权重

二部图网络结构推荐算法第一阶段中资源通过物品度均等分配，没有考虑到不同用户间的兴趣差异，若购买同一物品的用户间评分不同，则用户对于该物品的喜好也存在差异。文献[16,17]通过聚类区分用户兴趣差异，改变资源传递规则提高了算法的精确度。在资源传递第一阶段中，物品资源量更应该传递到和目标用户喜好类型和程度较为相似的用户点。因此，本文借助Jaccard系数，通过对系统中用户评分差均值 $a \nu e r a g e ( \alpha , \beta )$ 的计算获取用户间差异函数 $D ( \alpha , \beta )$ 。Jaccard相似性系数可定义为

$$
s i m ^ { \prime } ( \alpha , \beta ) = \frac { \mid I _ { \alpha } \cap I _ { \beta } \mid } { \mid I _ { \alpha } \cup I _ { \beta } \mid }
$$

$I _ { \alpha }$ 和 $I _ { \beta }$ 表示用户 $u _ { \alpha } \ , u _ { \beta }$ 对于其已购物品中具有实际评分的项目数量，当Jaccard相似性系数越大时，则认为 $u _ { \alpha } \ , \ u _ { \beta }$ 共同评分的项目数量较多，他们兴趣一致的可能性较大即相似性较大。对 $\boldsymbol { u } _ { \alpha }$ 、 $\boldsymbol { u } _ { \beta }$ 间共同评分项目的分值进行做差$D _ { \alpha \beta } = \{ d _ { 1 } , d _ { 2 } , \cdot \cdot \cdot , d _ { i } , \cdot \cdot \cdot , d _ { \scriptscriptstyle N } \}$ ，其中 $d _ { i }$ 为 $u _ { \alpha } \mathrm { ~ , ~ } u _ { \beta }$ 在第 $i$ 种物品的评分数$r _ { \alpha i }$ 、 $r _ { \beta i }$ 差的绝对值，即 $d _ { i } = \mid r _ { \alpha i } - r _ { \beta i } \mid$ ， $\mathbf { \Omega } _ { N }$ 表示 $\textstyle u _ { \alpha }$ 、 $\boldsymbol { u } _ { \beta }$ 共同评分的个数。则用户间评分差值的均值为

$$
a \nu e r a g e ( \alpha , \beta ) = \frac { \displaystyle \sum _ { i \in I _ { \alpha } \cap I _ { \beta } } d _ { i } } { N }
$$

为了能起到调节Jaccard相似性系数的作用，使其能达到用户间评分差距大时系数降低，用户评分差距小时系数升高的效果。对不同用户评分差均值进行归一化处理，并且去除评分纲量影响，得到用户间差异函数为

$$
D ( \alpha , \beta ) = 1 - \frac { a \nu e r a g e ( \alpha , \beta ) } { r _ { \mathrm { m a x } } - r _ { \mathrm { m i n } } }
$$

$r _ { \mathrm { m a x } }$ 为两用户间已购买的所有物品中最大的评分数值， $r _ { \mathrm { m i n } }$ 为最小的数值。通过对 $D ( \alpha , \beta )$ 计算，就可以借助Jaccard系数构造出用户相似性函数 $s i m ( \alpha , \beta )$ ：

$$
s i m ( \alpha , \beta ) = \frac { \mid I _ { \alpha } \cap I _ { \beta } \mid } { \mid I _ { \alpha } \cup I _ { \beta } \mid } D ( \alpha , \beta )
$$

利用 $s i m ( \alpha , \beta )$ 构造第一阶段路径权重 $S _ { \alpha \beta i }$ ，从而使得和目标用户相似性比较高的用户节点能够获得更多的资源值。其计算公式如下：

$$
S _ { \alpha \beta i } = \frac { a _ { \alpha i } s i m ( \alpha , \beta ) } { \displaystyle \sum _ { l = 1 } ^ { n } a _ { l i } s i m ( \alpha , l ) }
$$

$S _ { \alpha \beta i }$ 表示用户 $\boldsymbol { u } _ { \beta }$ 和目标用户 $\textstyle u _ { \alpha }$ 的相似度占所有选择了商品 $o _ { i }$ 的用户与目标用户 $\boldsymbol { u } _ { \alpha }$ 的相似度之和的比例。 $S _ { \alpha \beta i }$ 的结果在[0,1]内， $S _ { \alpha \beta i }$ 较大时，表示在所有已经购买 $o _ { i }$ 的用户群体中，目标用户 $\boldsymbol { u } _ { \alpha }$ 与用户 $\boldsymbol { u } _ { \beta }$ 比其他用户与 $\boldsymbol { u } _ { \alpha }$ 较为相似，则物品 $o _ { i }$ 上的初始资源就会较多的传递到 $\boldsymbol { u } _ { \beta }$ 。

若在系统中，以 $u _ { 4 }$ 作为目标用户，则物品 $o _ { I }$ 在改进路径权重后的第一阶段资源传递变化如图2所示。

![](images/e0a65c007719a76561b73490827c2939c7740a44434c67138e3f9881a740eebe.jpg)  
图2第一阶段资源传递变化

# 2.2引入物品相似性构建路径权重

用户选取物品时可能物品的某些属性致使用户购买，不同物品间虽然种类不同，但会有一部分相似属性，利用这些属性可以扩展推荐物品的种类以及极个别冷门物品。因此，物品属性相似性研究对推荐系统改进具有一定的实际意义。一些学者通过物品标签作为二部图扩展，提高推荐性能[18]。如果进行物品相似性计算，不同属性权重不同，如果人为设定权重值，会导致数据不平滑的现象。本文利用格雷编码表示不同的属性值，通过计算海明距离区分不同物品间差异，避免了人为属性权重设定，通过算法的自学习性自动的分析不同属性的作用大小。

对于物品属性，首先对每个属性确定其分类个数 $N$ ，确定该属性的编码位数 $n = 1 b N$ ，对于一个物品的不同属性值进行格雷编码并且连接成格雷编码串 $B _ { { } _ { N o m } }$ ，对两物品间的 $B _ { { } _ { N o m } }$ 进行海明距离差异比较得出不同物品的属性差异量 $D _ { H M } ( i , j )$ 。

$$
D _ { H M } ( i , j ) = D _ { H M } ( B _ { N o m i } , B _ { N o m j } )
$$

其中： $D _ { H M } ( i , j )$ 表示物品 $o _ { i }$ 和 $o _ { j }$ 的海明距离差异量，假设物品 $o _ { i }$ 属性串为 $B _ { \mathit { N o m i } } = ( 0 1 0 1 0 0 0 0 0 0 )$ ，物品 $o _ { j }$ 的属性串为$B _ { { N o m j } } = ( 1 1 0 0 0 1 0 1 0 0 )$ ，则 $D _ { \scriptscriptstyle H M } ( i , j ) = 4$ 。为了能起到与 $D ( \alpha , \beta )$ 同等的效果，对不同物品属性的海明距离值进行归一化处理，并且去除差异纲量影响，得到物品属性差异函数 $D ( i , j )$ 如下：

$$
D ( i , j ) = 1 - \frac { D _ { H M } ( i , j ) } { D _ { H M \operatorname* { m a x } } }
$$

其中： $D _ { H M \operatorname* { m a x } }$ 为物品 $o _ { i }$ 与 $o _ { j }$ 属性的海明距离的最大值。物品属性差异函数能够将描述物品特征的属性尽可能考虑到物品相似度计算中，有助于丰富推荐物品的种类。将物品属性差异函数$D ( i , j )$ 引入到Jaccard 相似性系数中，就可以得到物品相似度函数 $s i m ( i , j )$ 为

$$
s i m ( i , j ) = \frac { \lvert T _ { i } \cap T _ { j } \rvert } { \lvert T _ { i } \cup T _ { j } \rvert } D ( i , j )
$$

其中： $T _ { i }$ 和 $T _ { j }$ 分别表示物品 $o _ { i }$ 和 $o _ { j }$ 的特征属性数。通过 $s i m ( i , j )$

构造资源从用户到物品传递路径的权重 $Q _ { \beta i j }$ ，从而使得和目标用户已选择的物品相似性比较高的物品节点能够获得更多的资源值。 $Q _ { \beta i j }$ 表示物品 $o _ { j }$ 和目标用户 $\boldsymbol { u } _ { \alpha }$ 已选择的物品 $o _ { i }$ 的相似度占用户 $\boldsymbol { u } _ { \beta }$ 所有选择的物品 $o _ { t }$ 与物品 $o _ { i }$ 相似度的比例，其计算公式如下：

$$
Q _ { \beta i j } = \frac { s i m ( i , j ) } { \displaystyle \sum _ { t = 1 } ^ { m } a _ { \beta t } s i m ( i , t ) }
$$

若在系统中，以 $u _ { 4 }$ 作为目标用户，针对用户 $u _ { 4 }$ 已选择物品$O 3$ 时，则改进路径权重后的第二阶段资源传递变化如图3所示。

![](images/405d25258a61c3bcc386583f0bb0e2c6d1a74986ec33d379423dd1f3258a8afb.jpg)  
图3第二阶段资源传递变化

假设选定用户 $\boldsymbol { u } _ { \alpha }$ 为目标用户为其推荐物品，其已购买物品$o _ { i }$ 初始资源量定为1，则传递到用户 $\boldsymbol { u } _ { \beta }$ 的资源量为

$$
f ( u _ { \beta } ) = \sum _ { i = 1 } ^ { m } S _ { \alpha \beta i } a _ { \beta i }
$$

随后资源由用户 $\boldsymbol { u } _ { \beta }$ 传递到物品 $o _ { j }$ 后，物品 $o _ { j }$ 的资源量为

$$
f ( o _ { j } ) = \sum _ { \beta = 1 } ^ { n } Q _ { \beta i j } a _ { \beta j } f ( u _ { \beta } )
$$

对于目标用户所选择的物品初始资源量经过两轮资源传递后，就可以得到每个物品节点新的资源量，选取物品的 $f ( o _ { j } )$ 值进行由大到小顺序排列并将前 $\boldsymbol { L }$ 个物品推荐给用户。

# 3 算法详细步骤

利用上述不同的差异路径权重改进的BNSRA具体步骤如下：

输入：用户评分矩阵 $W$ ，物品属性表 $P$ ，目标用户 $\boldsymbol { u } _ { \alpha }$ 。输出：用户 $\boldsymbol { u } _ { \alpha }$ 推荐列表。a)通过用户评分矩阵建立用户与物品的二部图网络 $G$ ，并计算用户的度 $e$ 。b）在网络 $G$ 中通过式（3）可以得到不同的用户Jaccard系数，并计算用户评分差均值 $a \nu e$ 。c）根据ave和Jaccard系数，通过式（7）计算第一阶段路径权重 $s$ d）将 $P$ 中数据进行二进制转换，并进行与或运算得到物品建属性差异量 $D _ { H M }$ ，及最大差异量 $D _ { H M \operatorname* { m a x } }$ 。e）通过表 $P$ 获取两物品间的属性并交数量，利用式（11)计算出第二阶段路径权重 $\scriptstyle Q$ 中f）通过式（13）计算出传递后物品节点的资源量。g）将物品资源量按照由大到小排列，去除已购物品，取前$L$ 个最为推荐列表，算法结束。

本文算法的时间复杂度分析：假定系统中有n个用户，m种物品，在过程a）中可离线求出用户的度，其时间复杂度为$O ( n )$ ；在过程b）中由于Jaccard 系数和用户评分差均值可以离线计算，所以第一阶段路径权重复杂度为 $O ( m )$ 也可通过离线计算。过程d）中直接离线通过数据处理即可，随后在进行第二阶段路径权重计算时复杂度为 $O ( m ^ { 2 } )$ ，但是也可以离线运算。最后通过两阶段资源传递计算物品节点新的资源量时的时间复杂度为 $O ( n \cdot m )$ ,所以本文算法在计算过程中时间复杂度为 $O ( n \cdot m )$ ，$\mathbf { n }$ 为用户数， $\mathbf { m }$ 为物品数。

# 4 实验数据及评价指标

# 4.1实验数据

本文的实验数据选取GroupLens 研究组的MovieLens 数据集中943位用户对1682部电影的10万条评价信息，EachMovie数据集中72916位用户对1628部电影的评价信息以及Netflix数据集中480189位用户的17770部电影的评分数据进行实验。

# 4.2评价指标

a）海明距离（Hammingdistance，H）可以作为检测系统推荐物品种类多样性的一个重要指标。 $\textbf { \em L }$ 表示推荐列表长度， $Q _ { \alpha \beta }$ 表示 $\boldsymbol { u } _ { \alpha }$ 和 $\boldsymbol { u } _ { \beta }$ 推荐结果中相同物品个数，对于整个系统推荐物品种类多样性可表示为

$$
S { = } \frac { 1 } { m ( m - 1 ) } \sum _ { \alpha \neq \beta } ( 1 { - } \frac { Q _ { \alpha \beta } } { L } )
$$

$s$ 越大表明系统推荐物品的种类较多。

b）流行性（Popularity， $< \mathbf { k } >$ ）能反映出系统对于相对冷门物品推荐的情况。推荐系统的流行性可利用推荐物品度的均值$< \mathbf { k } >$ 表示，如果 $< \mathbf { k } >$ 较高，则说明推荐物品中的流行物品较多。物品度的平均值 ${ \bf < k > }$ 可以表示为

$$
\langle k \rangle = { \frac { 1 } { n L } } \sum _ { \beta = 1 } ^ { n } \sum _ { j = 1 } ^ { L } k ( o _ { j } )
$$

其中 $n$ 表示用户的数量。

c）准确率（precision，P）为推荐结果中目标用户已购买物品占比。 $\mathrm { ~ \bf ~ P ~ }$ 的结果越大表示算法的准确率越高。P的计算公式如下：

$$
P = \frac { f r a c t p t p f p } { h f i l l ( 1 ) }
$$

其中：fractptpfp是指已推荐的物品中用户已购物品的数量，hfill(l)是指推荐物品数量。

d）召回率（recall，R）为推荐结果中目标用户已购买物品的个数与目标用户购买物品总数的比值，R的结果越大表示算法的召回率越高。R的计算公式如下：

$$
R = \frac { f r a c t p t p f n } { h f i l l ( 2 ) }
$$

其中：fractptpfn指的是推荐列表中用户已经选择的物品数量，hfil(2)是指用户所有选择的物品数量的总和。

e）综合评价指标（F-measure）衡量推荐系统的综合表现的

指标，常用 $\mathrm { ~ \bf ~ P ~ }$ 和 $\mathtt { R }$ 的加权调和平均值表示，其公式为

$$
F 1 = \frac { 2 ^ { * } P ^ { * } R } { P + R }
$$

F1常作为衡量算法推荐能力的标准，F1值越大表明算法推荐效果越佳。

# 5 实验结果及分析

实验参照基准算法如下：本文算法基于差异路径权重（differentialpathweight，DPW）二部图网络推荐算法，协同过滤推荐算法（collaborative filtering，CF)，基于网络推理的算法（network-based inference，NBI）[4]，异质热传导（heterogeneousheat conduction，HHC）二分网络推荐算法[14]，热传导和物质扩散结合的混合推荐算法（hybrid methodof heat conduction andmass diffusion，HHM）[15]。

首先，在算法的推荐结果多样性能力上，如图4所示，CF、HHC、HHM和DPW推荐结果多样性上较传统网络结构算法有了明显改善。当实验数据量较少时，DPW算法的推荐结果多样性能力与HHC较为相似，当推荐列表长度增大时，DPW 算法的多样性推荐能力较好。随着实验数据量的增多DPW算法在推荐结果多样性上表现较好。可见随着推荐系统中展示物品数量增多以及物品总数增多，DPW算法能展示出更多种类的物品。

![](images/1b2afddb4e230e0042f1c01da0761a1c863695cfc0878a4b5a75ab39ee140496.jpg)  
图4平均海明距离值对比结果

在推荐冷门物品的能力上如图5所示，HHC、HHM 和DPW 算法相比传统的CF 和 NBI算法对冷门物品的推荐效果上有显著的改善。其中DPW和HHC 算法在推荐产品数量极少时，推荐冷门物品能力较好。随着推荐物品数量以及系统中物品总数增多，三种较优的算法的推荐冷门物品能力逐渐增强。当推荐物品数多于22时，DPW算法在多个数据集中推荐冷门物品能力表现较好。所以当推荐物品数量较多时，DPW算法更有可能推荐更多的冷门物品。

![](images/106d343519eaca5a90ba312bd961b8640110b23f3ac7ee07651ede40f97fdd23.jpg)  
图5流行性值对比结果

在算法准确程度和推荐性能方面，由于本算法针对物品中的资源量进行入手，在结果表示上不是以用户评分数展现，所以不能与其他算法进行MAE指的比较。因此，本文重点参考了算法的P、R、F1值进行算法性能的衡量。由实验结果可以看出DPW算法的P和R随着实验的推荐列表长度增加准确程度呈现渐好地趋势，在数据量较少的Movielens数据集中，DPW的性能与 HHC 算法效果较为相似，随着实验数据量的增多DPW 推荐性能逐渐增强，具体结果如图6、7所示。

![](images/6fdc87e1adc9d2da8fd258076389430afdeb0252e520dc179bfc3f63866d101f.jpg)  
图6Precision 值对比结果

![](images/d0f92577d9df429acd2f3eec039a21ee5d9c8ad3720680f860302dd70c81cbbd.jpg)  
图7Recall值对比结果

算法综合性能上，DPW算法在推荐系统物品总量低时表现不稳定，并且性能略差于HHC算法。随着系统中物品总数增多以及推荐物品的增多，算法的性能逐渐转好，并且在多物品阶段的性能较HHC和HHM算法都有所提高，具体结果如图8所示。

![](images/ea7fc47bab2177d5ffac9391333641b6deb811ca98f043da917fe25729cebebc.jpg)  
图8综合评价指标F1值对比结果

对于DPW算法在推荐物品数量较少时，没有达到更优的表现，对Movielens数据集查询发现，此数据库流行物品较多，当推荐物品数量较少时，推荐冷门数量较少。但是在多个数据集的整体效果上，DPW算法在推荐结果的多样性和准确性上，较目前流行的网络结构算法和协同过滤算法有了进步。

# 6 结束语

针对二部图网络结构推荐算法中资源均等分配和传统推荐算法中推荐物品流行性及推荐物品多样性较弱的情况，本文提出一种基于差异路径权重的二部图网络结构推荐算法。实验分析中发现，通过用户相似度的引入，可使推荐结果改变，同时借助物品属性的相似性使推荐算法的推荐结果流行性降低，推荐质量进一步改进。实验结果表明，当系统推荐物品数量较多时，本文算法推荐物品种类较丰富且优于其他几种流行算法，同时本文算法也能作用在实验数据较为稀疏的情境中。本文算法综合性能与几类主流网络推荐算法相比有所提高。同时本文算法通过降低推荐物品的流行性实现对冷门物品的推荐，使得本文算法能作用于个性化推荐系统中。在未来的研究中，针对不同的应用场景本文算法需要进行改变，同时在处理更多量的数据时，算法的工作效率也有待提高。

# 参考文献：

[1]赵宏晨，翟丽丽，张树臣．基于灰色关联度聚类与标签重叠因子结合的 协同过滤推荐方法研究[J].计算机工程与科学,2016,38(1):171-176.   
[2]Pazzani M J,Bilsus D. Content-Based Recommendation Systems [C]// Adaptive Web.Springer-Verlag,2007: 325-341.   
[3]Trewin S.Knowledge-based recommender systems [J].Encyclopedia of library and information science,200o,69 (32):180-186.   
[4] Zhou T,Ren J,Medo M. Bipartite network projection and personal recommendation [J].Physical Review E,2007,76 (4): 046115.   
[5]Zanker M, Jessenitschnig M. Case-studies on exploiting explicit customer requirements in recommender systems [J]. User Modeling and UserAdapted Interaction,2009,19 (1):133-166.   
[6]Zhang YC,Blattner M,Yu Y K.Heat conduction process on community networks as a recommendation model[J].Physical review letters,2007, 99 (15): 154301.   
[7]Zhou Y,Lu L,Liu W,et al. The power of ground user in recommender systems [J].PLoS ONE,2013,8(8): e70094.   
[8]Zhou T, Jiang LL,SuRQ,etal.Effect of initial configuration on networkbased recommendation [J].EPL(Euro physics Leters),20o8,81(5): 58004.   
[9]孙玉华，曾庆铎．二阶段网络系统的全局 DEA 模型[J].统计与决策， 2014, (11): 43-46.   
[10]张新猛，蒋盛益，张倩生．基于用户偏好加权的混合网络推荐算法[J]. 山东大学学报：理学版,2015,50(9):29-35.   
[11]熊湘云．基于二分网络的多维度推荐技术研究[D].江苏：苏州大学, 2013: 29-33.   
[12] KorenY.Collaborativefilteringwithtemporaldynamics[J]. Communications of the ACM,2010,53 (4): 89-97.   
[13]王茜，段双艳．一种改进的基于二部图网络结构的推荐算法[J].计算 机应用研究,2013,30(3):771-774.   
[14]胡吉明，林鑫．基于用户一资源一词汇三部图的社会化推荐算法设计 与实现[J]．情报理论与实践,2016,39(3):130-134.   
[15] Zhou T, Kuscsik Z,Liu JG,et al. Solving the apparent diversity-accuracy dilemma ofrecommender systems [J]. Proceedings ofthe National Academy of Sciences,2010,107 (10): 4511-4515.

[16]葛志鹏，严广乐，张国亮．基于蚁群聚类的二部图网络推荐算法[J].信息技术,2016,(3):57-61.

[17]王桐远．基于二分K均值聚类的二部图网络推荐算法[J].经营管理

者,2015 (25): 3.[18]肖扬，王道平，杨岑．基于三部图网络结构的知识推荐算法[J].计算机应用研究,2015,32(2):386-390.