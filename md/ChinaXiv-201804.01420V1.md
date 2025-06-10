# 支持差分隐私保护及离群点消除的并行K-means算法

樊一康，刘建伟

(北京航空航天大学 电子信息工程学院，北京 100191)

摘要：针对大数据环境下聚类分析的隐私保护问题，基于MapReduce计算框架，提出了一种并行化的支持差分隐私保护和离群点消除的K-means 算法。算法并行地计算数据集中各点间的欧氏距离矩阵与最近邻超球半径以导出离群点的判定阈值，并在此基础上完成差分隐私保护下的初始聚类中心选取和并行聚类过程。理论分析证明整个算法满足ε-差分隐私保护，实验结果说明该算法在隐私保护的有效性，聚类结果的可用性以及执行效率等方面取得了很好的平衡，相比于同类算法有较优的表现。

关键词：K-均值聚类；离群点消除；差分隐私；MapReduce 中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2017.12.0825

# Parallel K-means algorithm with differential privacy preservation and outlier pruning

Fan Yikang, Liu Jianwei† (School of Electronic Information Engineering,Beihang University,Beijing lOo191,China)

Abstract: Aimingatthe problemofprivacyprotectionofclustering analysis inbigdata environment,basedonthe MapReduce computing framework,thispaperproposedaparallelK-meansalgorithmthatsupports diferential privacyprotectionandoutlier elimination.The algorithmparalellycalculates theEuclidean distance matrixand nearest neighborhypersphereradius between points ndatasettoderivethedecision thresholdofoutliers,andthencompletes theinitialclustercenterselectionand paralel clustering processunderdifferential privacyprotection.Thetheoreticalaalysis proves that theproposedalgorithmsatisfiesε- differential privacy,andtheexperimentalresultsshowthat,compared withotheralgorithms,ouralgorithmperformsbeterand hasagood balance between the validityof privacy protection,the availabilityof clustering result and the efciencyof implementation.

Key Words:K-means clustering; outlier pruning; differential privacy; MapReduce

# 0 引言

随着数据挖掘在各行各业越来越广泛的应用，挖掘引起的个人隐私泄露的问题也越来越受到重视。如何在保护个人隐私的同时为挖掘保持数据的可用性逐渐成为数据挖掘和信息安全领域的一个重要的研究方向。

早期典型的数据隐私保护模型是基于等价类（equivalencegroup）的 $k$ -anonymity[1]及其一系列扩展模型，它们的核心思想都是将一个记录隐藏在一组记录之中[2]，保证任一记录与至少$k { - } 1$ 个记录是不可区分的。但是这些模型总是需要针对新出现的攻击类型而作出相应的完善，例如针对“一致性”攻击而相继被提出的l-diversity[3]、 $( \alpha , k )$ -anonymity[4]、M-invariance[5],针对“最小性”攻击而被提出的 $\mathrm { ~ m ~ }$ -confidentiality[6]。导致这一局面的根本原因是基于等价类的隐私保护依赖于对攻击者所掌握的背景知识的限定，而只要攻击者从限定之外的背景知识出发来攻击，模型往往就无能为力。除了需要被动地针对新型攻击而发展变种的缺陷外，这些模型也未能提供一个严格的量化方法来度量其隐私保护水平，这也影响了它们的鲁棒性。

在这样的背景下，Dwork提出了差分隐私（differentialprivacy，DP）[7]的概念。差分隐私保护通过添加噪声的方式可使得处理数据集的某个算法的输出对数据集中某条记录的变化甚至存在与否不敏感。因此，个人的一条记录被包含在某个提供差分隐私保护的数据集中而带来的隐私泄露风险可以被控制在一个可接受的范围内，即便是在攻击者拥有最大背景知识(即攻击者已知除目标记录外的所有记录的信息)的情况下。同时，差分隐私定义了严格的攻击者模型并提供了可证明的量化的评估方法来度量隐私泄露风险。而基于差分隐私保护的算法在输出上需要添加的噪声独立于数据集的规模，且少量的噪声即可达到较高的隐私保护水平并保持挖掘结果的可用性。正因为差分隐私在上述几个方面有着良好的表现，其迅速被业界接纳并在近年来成为隐私保护领域的研究热点。

目前基于差分隐私的数据挖掘研究工作在关联规则挖掘上的积累较多，而在聚类分析上的积累则相对较少。K-means 算法是公认的应用最广泛的聚类算法之一，对于如何在其聚类分析的准确性与隐私保护的有效性间取得平衡，以及对其执行效率的优化上，国内外学者都做了一些积累与贡献。文献[8]给出了一种提供差分隐私保护的K-means 算法，文献[9]从隐私保护预算分配的角度对文献[8]中的工作进行了完善，文献[10]基于MapReduce 计算框架[11]将文献[9]完善的算法并行化，但它们均没有考虑算法面对噪声及离群点的鲁棒性。文献[12]提出了OEDPK-means 算法，其考虑了离群点对K-means 算法的消极影响并引入了一种检测离群点并消除的方法，但该方法的时间复杂度为 $O ( N ^ { 2 } )$ ， $N$ 为数据集中的记录数，其对算法执行效率的影响在对大数据集进行聚类分析时尤为明显，此外，OEDP算法对初始聚类中心的选取策略计算复杂高且在某些数据分布的情况下会发生劣化而导致更慢的收敛速度。文献[13]提出了另一种基于差分隐私保护的IDPK-means 算法，其考虑了初始聚类中心的选择对算法的影响，但其对初始聚类中心的选择仅是简单的分段取平均值，并没有排除可能的离群点带来的消极影响。另外，OEDPk-means 算法和IDPk-means 算法都是串行结构，而并行化的算法结构对大规模数据集上的聚类需求是很有意义的。

基于此，本文提出了一种支持差分隐私保护及离群点消除的并行K-means 聚类方法（因其关注 Parallelization 与 Pruning以及Privacy，可简称为 TriplePK-means 聚类方法)，其基于MapReduce计算框架并行地计算数据集中各点间的欧氏距离矩阵与最近邻超球半径以导出离群点的判定阈值，并在此基础上完成差分隐私保护下的初始聚类中心选取和并行聚类过程。本文给出了算法的差分隐私性证明与实验分析，相比于同类算法，本文算法在隐私保护的有效性，聚类结果的可用性以及聚类效率和扩展性等方面取得了较好的平衡。

# 1 相关概念

# 1.1差分隐私的定义及性质

差分隐私[7,4]模型提供了严格且可证明的隐私保护定义以及对泄露风险的量化评估方法。因其对隐私的保护不依赖于对攻击者所拥有的背景知识的限定，从而可应对任意背景知识下的攻击行为。其主要方式是在数据集中或者在算法输出上添加随机噪声来实现隐私保护，同时保持原有数据及所含信息的可用性。具体地，差分隐私模型的一些定义和性质如下所述：

# 1.1.1差分隐私

设有两个数据集 $D$ 和 $\boldsymbol { D }$ ，二者的属性结构相同，记二者的对称差为 $D \Delta D ^ { \prime }$ ，记对称差中的记录数量为 $\left| D \Delta D ^ { \prime } \right|$ 。称$\left| D \Delta D ^ { \prime } \right| = 1$ 时的 $D$ 和 $D ^ { \prime }$ 为邻近数据集（AdjacentDataset）。

设 $\kappa$ 为邻近数据集 $D$ 和 $D ^ { \prime }$ 上的一个随机算法，记 $\kappa$ 所有可能的输出的集合为 $R a n g e ( \mathcal { K } )$ ，记事件 $X$ 发生的概率为

$P _ { r } [ X ]$ ，则对 $R a n g e ( K )$ 的任一子集 $s$ ，若 $\kappa$ 满足

$$
P _ { r } [ \mathcal { K } ( D ) \in S ] \le \exp ( \varepsilon ) \times P _ { r } [ \mathcal { K } ( D ^ { \prime } ) \in S ]
$$

则称算法 $\kappa$ 满足 $\varepsilon .$ 差分隐私保护。称 $\mathbf { \Psi } _ { \varepsilon }$ 为隐私保护预算，它限制了数据集中某一记录的变化对算法输出的影响，越小的$\varepsilon$ 意味着越严格的隐私保护。一般 $\varepsilon$ 的取值范围是(0.01,0.1)或在某些情况下为 $( \ln 2 , \ln 3 )$ ，[14]。

$L _ { \mathrm { 1 } }$ 敏感度

设函数 $f : D \to R ^ { d }$ ,其将数据集 $D$ 映射到 $d$ 维实数空间中的一个向量，对于任意的邻近数据集 $D$ 和 $\boldsymbol { D }$ ，令

$$
\Delta f { = } \operatorname* { m a x } _ { D , D ^ { \prime } } \| f ( D ) { - } f ( D ^ { \prime } ) \| _ { 1 }
$$

则称 $\Delta f$ 为函数 $f$ 的 $L _ { \mathrm { 1 } }$ 敏感度[7,14]，其中 $\| f ( D ) - f ( D ^ { \prime } ) \| _ { 1 }$ （20是 $f ( D )$ 与 $f ( D ^ { \prime } )$ 间的 $_ { 1 - }$ 阶范数距离。注意 $L _ { \mathrm { 1 } }$ 敏感度独立于数据集而仅由函数本身决定，它是影响所需加入的随机噪声量的关键参数。

# Laplace机制

差分隐私保护的噪声实现机制主要有指数机制和 Laplace机制[15]两种，相比于指数机制，Laplace机制对数值型数据的保护更为适合，因此多用于构造支持差分隐私保护的聚类算法。记位置参数为0、尺度参数为 $b$ 的 Laplace分布为 $L a p ( b )$ ，则其概率密度函数为

$$
p ( x | b ) = \frac { 1 } { 2 b } \exp ( - \frac { | x | } { b } )
$$

对于函数 $f : D \to R ^ { d }$ ，其 $L _ { 1 }$ 敏感度为 $\Delta f$ ，若随机算法 $\kappa$ 有

$$
K ( D ) = f ( D ) + ( L a p _ { 1 } ( \Delta f / \varepsilon ) , L a p _ { 2 } ( \Delta f / \varepsilon ) , . . . , L a p _ { d } ( \Delta f / \varepsilon ) )
$$

则算法 $\kappa$ 满足 $\varepsilon$ 差分隐私保护，其中 $L a p _ { i } ( \Delta f \mid \varepsilon ) , i \in [ 1 , d ]$ 之间是相互独立的。由 $p ( x | b )$ 及 $b = \Delta f \mid \varepsilon$ 可知，越小的 $\boldsymbol { \varepsilon }$ 需要引入的噪声就越大。

# 1.1.2序列组合性

设有 $\mathbf { \Omega } _ { n }$ 个随机算法 $\kappa _ { 1 } , \kappa _ { 2 } , . . . , \kappa _ { n }$ ,其隐私保护预算分别为ε,ε,,εn，则对于某一数据集D，由这n个随机算法序列组合成的算法 ${ \ K } ( { \ K } _ { 1 } ( D ) , { \ K } _ { 2 } ( D ) , . . . , { \ K } _ { n } ( D ) )$ 满足 $( \sum _ { i = 1 } ^ { n } \varepsilon _ { i } )$ 差分隐私保护，此即差分隐私的序列组合性[16]。

# 1.1.3并行组合性

设有 $n$ 个随机算法 $K _ { 1 } , K _ { 2 } , . . . , K _ { n }$ ,其隐私保护预算分别为$\varepsilon _ { 1 } , \varepsilon _ { 2 } , . . . , \varepsilon _ { n }$ ，则对 $n$ 个交集为空集的数据集 $D _ { 1 } , D _ { 2 } , . . . , D _ { n }$ ，由着 $n$ 个随机算法并行组合成的算法 ${ \ K } ( K _ { 1 } ( D _ { 1 } ) , K _ { 2 } ( D _ { 2 } ) , . . . , K _ { n } ( D _ { n } ) )$ 满足$( \operatorname* { m a x } _ { i } \varepsilon _ { i } )$ -差分隐私保护，此即差分隐私的并行组合性[16]。

# 1.2 $\boldsymbol { \mathsf { k } }$ -means聚类算法与离群点

对一个 $\mathbb { R } ^ { T }$ 上的数据集 $\mathcal { X } { = } \{ x _ { 1 } , x _ { 2 } , { \ldots } , x _ { N } \}$ ，其包含 $N$ 个具有$T$ 维属性值的数据点，聚类算法可将其划分为 $\boldsymbol { K }$ 个簇：$\mathcal { P } = \{ P _ { 1 } , P _ { 2 } , . . . , P _ { K } \}$ 并满足 $\bigcup _ { i = 1 } ^ { K } P _ { i } = \mathcal { X } , P _ { i } \bigcap P _ { j } = \phi ( 1 \leq i \neq j \leq K )$ ，簇内的点或称向量之间高度相似而簇间的相异。k-means 算法被公认是应用最广泛的聚类算法之一，其首先选择 $K$ 个初始中心点，然后将数据集中的点按平方欧氏距离分配到最近的中心点从而形成 $K$ 个簇并调整各中心点到各簇的平均值，算法重复这一分配调整的过程直至满足收敛判据或者迭代次数达到上限。k-means 算法的一个重要优势是时间及空间复杂度均与 $\mathbf { \Omega } _ { N , T , K }$ 呈线性相关（一般地， $T \ll N , K \ll N \ \backslash$ 。但因为 $\mathbf { k }$ -means 算法以平方欧氏距离度量相似度，所以其对数据噪声及离群点十分敏感，少数的离群点就能对其所属簇的中心造成很大的影响，在降低聚类准确性的同时也可能致使 $\mathbf { k }$ -means算法迭代次数增加而降低算法的运行效率。为回避离群点带来的消极影响，可以选择鲁棒性更好的距离函数如City-block $( \mathcal { L } _ { 1 } )$ [17]，但更直接的处理方法是离群点修剪。有关离群点的一些定义及概念如下述。

# 1.2.1 $\boldsymbol { r } .$ .最近邻超球及其半径

对于 $\mathbb { R } ^ { T }$ 上的数据集 $\mathcal { X } { = } \{ x _ { 1 } , x _ { 2 } , { \ldots } , x _ { N } \}$ ,称任一数据点 $x _ { i }$ 与离其最近的 $\boldsymbol { r }$ 个数据点在 $T$ 维空间中构成的超球为 $x _ { i }$ 的 $\mathbf { \Psi } _ { r }$ 最近邻超球，这一概念的原型为文献[12]中的 $\mathbf { \Psi } _ { r }$ 最近邻区域（rnearest-neighbour area）。

希望点 $x _ { i }$ 的 $\scriptstyle { r - }$ 最近邻超球的大小可以反映出点 $x _ { i }$ 及其周围点的稀疏程度，因此取点 $x _ { i }$ 与其超球中的所有点的平均欧氏距离为超球的半径，记数据点 $x _ { i }$ 与其 $\mathbf { \Psi } _ { r } .$ .最近邻超球中的点$n _ { \scriptscriptstyle { l } } ( 1 \leq l \leq r )$ 间的欧氏距离为 $d i s t ( x _ { i } , n _ { l } )$ ，超球半径为

$$
r R a d i u s ( x _ { i } , \mathcal { X } ) = [ \sum _ { l = 1 } ^ { r } d i s t ( x _ { i } , n _ { l } ) ] / r
$$

# 1.2.2离群点及判定阈值

离群点[12]是指与其他点有明显不同的数据点，一般可分为全局离群点（globaloutlier）、情境离群点（contextualoutlier）、集体离群点（collectiveoutlier)，鉴于本文主要面对的是数值型数据的分析处理，不涉及具体情境或者群组，因此只考虑全局离群点，也即数据集中与其余点差别均很大的数据点。对于离群点的判定，由数据集中的稀有类由至多 $5 \%$ 的数据点组成[18]，估计数据集 $\chi$ 中离群点数目不超过 $N \times 0 . 0 5$ ，记为 $O _ { n u m }$ ，记离群点的 $\boldsymbol { r } .$ .最近邻超球半径的判定阈值为 $\tau$ ，取其值为数据集中$r .$ .最近邻超球半径最大的 $O _ { n u m }$ 个点的半径均值，从而认为 $r .$ 最近邻超球半径超过阈值 $\tau$ 的数据点为离群点。

# 2 算法设计与分析

本文提出的算法基于MapReduce 计算框架，并行地计算得到离群点的判定阈值，并在此基础上完成差分隐私保护下的初始聚类中心选取和并行聚类分析。其中离群点相关的处理可以提高K-means算法的准确度和运行效率，而差分隐私保护则关注在数据集中的一条记录改变时，算法聚类结果（各聚类质心位置及所含数据项的数目）的相应变化不会泄露隐私信息。具体来说，算法分为三个阶段：

首先是准备阶段。对于一个R上的数据集X={x,X.x}，由前文离群点的相关概念可知，离群点的相关计算依赖于 $\chi$ 中各数据点间的欧氏距离 $d i s t ( x _ { i } , x _ { j } ) ( 1 \leq i \neq j \leq N )$ ，用一个 $N \times N$ 的距离矩阵 $D i s t$ 来表示它。而在计算该距离矩阵前，需要对数据集进行归一化处理。因此首先需要计算数据集中 $T$ 个属性各自的最大值和最小值。然后完成数据的归一化以及按一定方式分拆与整理数据集中的所有数据以适配MapReduce下对各数据点间欧氏距离的并行计算，最终获得距离矩阵 Dist。

其次是过渡阶段，算法完成离群点判定阈值的计算以及初始聚类中心的选取。由上一阶段得到的距离矩阵 $D i s t$ ，并行地计算数据集中各数据点的 $\mathbf { \Psi } _ { r } .$ .最近邻超球半径 $r R a d i u s ( x _ { i } , \mathcal { X } )$ ，进而计算出离群点的判定阈值 $\tau$ 。此外，考虑到K-means 算法因其梯度下降的性质而对初始中心点的选择十分敏感[17]，盲目选择初始中心可能导致第三阶段的聚类算法迭代次数增多而影响效率，且过慢的收敛还会引入更多的噪声而影响聚类结果的可用性。因此算法利用距离矩阵 $D i s t$ 中的信息完成初始聚类中心的选取，核心策略是让这 $K$ 个初始聚类中心能尽可能地分别落在假设存在的 $K$ 个簇中，并在选取过程中剔除离群点。

算法在第三阶段完成数据的聚类分析及其中的差分隐私保护。由第二阶段得到的 $K$ 个初始聚类中心出发，将数据集 $\chi$ 中的数据点参考其与各聚类中心的距离大小就近划分成 $K$ 个簇，并计算各簇中数据点的数量及总和并添加相应量的Laplace 噪声，进而获得新一代的 $K$ 个聚类中心。算法重复这一过程，直至满足收敛判据或者迭代次数达到上限。最终算法输出最后一次迭代得到的聚类中心及所含数据点的数量。

# 2.1具体步骤

# 2.1.1计算最大值与最小值

设 $\mathbb { R } ^ { T }$ 上的数据集 $\mathcal { X } { = } \{ x _ { 1 } , x _ { 2 } , { \ldots } , x _ { N } \}$ 被均匀划分为 $M$ 个数据片，每个数据片中最多有 $\lceil N / M \rceil$ 个数据点，记第 $\mathbf { \psi } _ { m }$ 个数据片及其索引分别为 $S p l i t _ { { m } }$ 和 $S p l i t I n d e x _ { m }$ 。记由 $T$ 个属性域的理论最大值和理论最小值构成的数据点分别为 $A t t r _ { M A X }$ 和 $A t t r _ { M I N }$ ，记由数据集 $\chi$ 在 $T$ 个属性域上的最大值和最小值构成的数据点分别为 $x _ { _ { M A X } }$ 和 $x _ { _ { M I N } }$ ，记由数据片 $S p l i t _ { m }$ 在 $T$ 个属性域上的最大值和最小值构成的数据点分别为xm.max 和 xm.min 。

Master(主节点)指派 $M$ 个Map 任务与2个Reduce任务。需要注意的是，在经典形式中，Map任务会遍历数据片中的各键值对并在其上分别调用Map函数，而在这里采取相异的策略以便于处理数据，即将上述遍历过程放在Map函数之中（通过重载 mapper类的用户继承类中的run 方法来实现)，因此每个Map 任务只需调用一次Map 函数，在后续的一些步骤中也用到了同样的策略，不再一一说明。本文参考MapReduce 框架提出者在文献[11]中的表达形式，在Map 函数中用EmitIntermediateC函数表示输出中间键值对（这些中间键值对会由框架传递给Reduce任务)，在Reduce函数中用Emit(函数表示输出结果键值对（写入到每个Reduce任务的输出文件中)，在后续的各步骤中依然保持这样的表达形式。

具体地，计算最大值与最小值的Map函数及Reduce函数的伪代码如下所示：

map(Index SplitIndexm, DataSplit $S p l i t _ { { m } }$ ）

$\begin{array} { r } { x _ { m , \mathrm { m a x } } } \\ { A t t r _ { M I N } ; } \\ { x _ { m , \mathrm { m i n } } } \\ { A t t r _ { M A X } ; } \end{array}$ （204 for each xin Splitm: update $x _ { m , \operatorname* { m a x } }$ and $x _ { m , \mathrm { m i n } }$ ； EmitIntermediate("max”, $x _ { m , \mathrm { m a x } } .$ ） EmitIntermediate $( ^ { \ast } \mathrm { { m i n } ^ { \prime \prime } }$ ， $x _ { m , \mathrm { m i n } }$ ） reduce(String type,Iterator vectors) //type取值为"max"或"min” //vectors 是同 type 下各 $x _ { m , \operatorname* { m a x } }$ 或 $x _ { m , \mathrm { { m i n } } }$ 的集合 if(type.equals("max")) for each $x _ { m , \operatorname* { m a x } }$ in vectors: update $x _ { \ / { M A X } }$ ； $\mathrm { E m i t } ( ^ { \left. } \mathrm { m a x } ^ { \right. } , x _ { _ { M A X } } )$ ， else for each $x _ { m , \mathrm { m i n } }$ in vectors: update $x _ { _ { M I N } }$ ； Emit("min”, $x _ { _ { M I N } } .$ ）

2.1.2归一化及倒排索引

延用上一步中划分得到的 $M$ 个数据片。记数据集 $\chi$ 的 $T$   
个属性域的集合为 $A t t r i b u t e s = \{ A _ { 1 } , A _ { 2 } , . . . , A _ { T } \}$ ，记数据点 $x _ { i }$ 在属  
性域 $A _ { t } ( 1 \leq t \leq T )$ 上的分量为 $a _ { t , x _ { i } }$ ,记其归一化值为 $a _ { t , x _ { i } } ^ { \prime }$ ，将数据  
片 $S p l i t _ { { m } }$ 中的点 $x _ { i }$ 及其在属性域 $A _ { t }$ 上的归一化分量作为键值  
对 $< x _ { i } , a _ { t , x _ { i } } ^ { \prime } >$ 存放在一个关联数组中，记为 $H _ { t , m }$ ，同理记数据集  
$\chi$ 中所有点在属性域 $A _ { t }$ 上的相应关联数组为 $H _ { t }$ 。Master 指派  
$M$ 个 Map 任务与 $T$ 个 Reduce 任务。用 Map 函数将 $S p l i t _ { { \scriptscriptstyle m } }$ 中的  
数据在归一化的同时按各属性域拆分，用Reduce函数将属性  
域下各数据片的数据整合，二者伪代码如下所示：map(Index SplitIndex,DataSplit $S p l i t _ { { m } }$ ）for each $A _ { t }$ in Attributes:$H _ { t , m }$ =new ssociativeArray(;1/新建一个关联数组 $H _ { \iota , m }$ （204号for each xin Splitm:$H _ { { t , m } } [ x _ { i } ] = ( a _ { { t , x } _ { i } } - a _ { { t , x } _ { { M N } } } ) / ( a _ { { t , x } _ { { M A X } } } - a _ { { t , x } _ { { M N } } } ) ;$ （EmitIntermediate $( \mathbf { \nabla } _ { A _ { t } } , \mathbf { \nabla } H _ { t , m } )$ ，reduce(String $A _ { t }$ , Iterator arrays):$/ /$ arrays 是各数据片在属性 $A _ { t }$ 下 $H _ { t , m }$ 的集合$H _ { \iota } { = } \mathrm { n e w ~ s s o c i a t i v e A r r a y ( ) } ;$ （204号for each $H _ { t , m }$ in arrays:Merge( $\{ H _ { t } , H _ { t , m } \}$ ：$\mathrm { E m i t } ( A _ { t } , H _ { t } ) .$

2.1.3计算欧氏距离矩阵

如果 $T \leq M$ （此时往往有 $\left\lceil M / T \right\rceil \leq N$ )，为了达到更优的扩展性，可以对上一步获得的各属性域下的关联矩阵进行复制

及划分。具体地，记 $Q = \lceil M / T \rceil$ ，对于某个关联矩阵  
（204号 $H _ { t } = [ ( x _ { 1 } , a _ { t , x _ { 1 } } ^ { \prime } ) , ( x _ { 2 } , a _ { t , x _ { 2 } } ^ { \prime } ) , . . . , ( x _ { N } , a _ { t , x _ { N } } ^ { \prime } ) ]$ ，将其中的键值对均匀划分  
为 $\boldsymbol { \mathscr { Q } }$ 个部分，每部分至少包含 $\lfloor N / Q \rfloor$ 个键值对，从而由 $H _ { t }$ 派  
生出 $\boldsymbol { \mathscr { Q } }$ 个内容与 $\textstyle H _ { t }$ 一致但下标不同的关联矩阵  
（204号 $\{ H _ { t , 1 } , H _ { t , 2 } , . . . , H _ { t , Q } \}$ 。而对于其中某个 $H _ { t , q } ( 1 \leq q \leq Q )$ ，用它的属  
性域标号 $\mathbf { \Phi } _ { t }$ 与键值对序号 $q$ 的乘积 $t q$ 作为它的索引，Map 函数  
只计算该关联矩阵中第 $q$ 部分键值对涉及的点与其余点在属性  
域 $A _ { t }$ 下的距离分量。为了节省空间，对于Map 函数的输出，不  
同于传统中间键值对（intermediate key/value pair）的形式  
$< ( x _ { i } , x _ { j } )$ ,value $>$ ，采用“带”（stripe）的形式 $< x _ { i } , [ ( x _ { j } , \nu a l u e ) . . . ] >$   
来存放，即将点 $x _ { i }$ 与其余点在属性域 $A _ { t }$ 下的距离分量存放在一  
个关联数组 $D _ { \mathrm { t } , i }$ 中。以带的形式来组织数据相比于中间键值对  
可以节省约三分之一的空间，并且在利用MapReduce 框架中的  
Combiner 时也能有更高的合并效率。Reduce 函数将数据点 $x _ { i }$ （204  
在各属性域下与其余点的距离分量整合并计算得到其与其他点  
的欧氏距离最后存入关联数组 $D _ { i }$ 之中。如果 $T$ 与 $M$ 较为接近，  
则取 $\boldsymbol { \mathscr { Q } }$ 为1,即不再对 $H _ { t }$ 分段划分而作为一整段来处理。Master  
共指派 $T \times Q$ （其值可能略大于 $M$ ）个 map 任务和 $M$ 个 reduce  
任务。到此，即可获得距离矩阵 $D i s t$ ，其由 $M$ 份 Reduce任务  
输出的数据文件组成。Map 函数及reduce 函数的伪代码如下所  
示：map(Index tq , AssociativeArray $H _ { t , q }$ ）for each $x _ { i }$ in the $q _ { t h }$ segment of $H _ { t , q }$ ：Dt,i =new ssociativeArrayO;for each $x _ { j } ( j \neq i )$ in $H _ { t , q }$ ：$D _ { t , i } [ x _ { j } ] = ( a _ { t , x _ { i } } ^ { \prime } - a _ { t , x _ { j } } ^ { \prime } ) ^ { 2 } ;$ （204号EmitIntermediate $( \ v { x } _ { i } , \ v { D } _ { \mathrm { t } , i } )$ ，reduce(Point $x _ { i }$ , Iterator arrays):$/ /$ arrays 是点 $x _ { i }$ 在各属性域下 $D _ { \mathfrak { t } , i }$ 的集合$D _ { i } { \mathrm { = n e w ~ s s o c i a t i v e A r r a y ( ) } } ;$ for each $D _ { \mathfrak { t } , i }$ in arrays:AttributeSum( $\mathbf { \varepsilon } _ { D _ { i } }$ ， $D _ { \mathfrak { t } , i }$ ）//将各属性域下的距离平方求和AttributeSquareRoot $( D _ { i } ) ; / /$ 开方求欧氏距离${ \mathrm { E m i t } } ( x _ { i } , D _ { i } )$ ：  
2.1.4 计算判定阈值上一步得到的距离矩阵 $D i s t$ 由 $M$ 段数据文件组成，记第

$\mathbf { \Sigma } _ { m }$ 段数据文件及其索引分别为 Segmentm和 SegmentIndexm。对于某段数据文件 $S e g m e n t _ { m }$ ,Map 函数线性扫描其中各数据点与其余数据点的距离以获得最小的 $\boldsymbol { r }$ 个欧式距离，并由此计算出各点的 $r .$ 最近邻超球半径 $r R a d i u s ( x _ { i } , \mathcal { X } )$ ，同时 Map 函数线性扫描该段数据文件中各数据点的最近邻超球半径以获得最大的$O _ { n u m }$ 个值并作为一个集合 $S e t _ { m }$ 输出。Reduce 函数线性扫描所有其收到的集合并选取其中最大的 $O _ { n u m }$ 个值，取其均值作为判定阈值 $\tau$ 。Master 指派 $M$ 个 Map 任务和1个Reduce 任务。Map

及Reduce函数的伪代码如下所示： map(Index SegmentIndexm,DistSplit Segmentm): $S e t _ { m } ^ { \phantom { } = \phantom { } \mathrm { n e w } \mathrm { S e t ( ) } ; }$ //新建含 $O _ { n u m }$ 个0的集合 for each $x _ { i }$ in Segmentm :   
scan $D _ { i }$ to get the $\mathbf { r }$ smallest distance; calculate $r R a d i u s ( x _ { i } , \mathcal { X } )$ ·， if (it >minimum( $S e t _ { m }$ 》 replace the minimum with it; EmitIntermediate( $\cdot \ x , \ S e t _ { m } \ )$ ：   
reduce(Dataset $\chi$ , Iterator sets) $/ /$ sets 是各段数据的 $S e t _ { m }$ 的集合 Set $\ O =$ new Set(); //新建含 $O _ { n u m }$ 个0的集合   
for each $S e t _ { m }$ in sets: for each r in Setm : if (r >minimum(Set)) replace the minimum with r; T=mean(Set);//求集合中半径的均值   
（204号 $\operatorname { E m i t } ( \chi , \tau )$

# 2.1.5选取初始聚类中心

经过上一步不仅获得了离群点的判定阈值 $\tau$ ，也得到了各数据点的 $\mathbf { \Psi } _ { r }$ .最近邻超球半径 $r R a d i u s ( x _ { i } , \mathcal { X } )$ 。记 $K$ 个初始簇及聚类中心分别为 $\{ C _ { 1 } , C _ { 2 } , . . . , C _ { K } \}$ ， $\{ \mu _ { 1 } , \mu _ { 2 } , . . . , \mu _ { K } \}$ ，算法从数据集（204 $\chi$ 的 $N$ 个数据点中随机选取一个非离群点 $\mu _ { 1 } ^ { \prime }$ （204号(rRadius(μ',X)<T)，并根据距离矩阵 Dist 中的信息从其余数据点中拿出距离点 $\mu _ { 1 } ^ { \prime }$ 最近的 $\lfloor N / K \rfloor$ 个非离群点（遇到离群点则剔除）与点 $\mu _ { 1 } ^ { \prime }$ 组成初始簇 $C _ { 1 }$ ，接着算法从剩余的数据点中再次随机选取一个非离群点作为 $\mu _ { 2 } ^ { ' }$ 并同样拿出其周围的一部分点与其组成初始簇 $C _ { 2 }$ ，算法重复这一拿取的过程直至获得$K$ 个初始簇。然后计算各簇中数据点的总和，并向总和与簇中数据点数目（约 $\lfloor N / K \rfloor$ ）分别添加Laplace噪声，进而求各簇的均值点作为初始聚类中心。由Master（主节点）整合距离矩阵 $D i s t$ 并单独执行这一步算法。

# 2.1.6聚类分析及隐私保护

经过上一步得到了 $K$ 个初始聚类中心 $\{ \mu _ { 1 } , \mu _ { 2 } , . . . , \mu _ { K } \}$ 与不含离群点的数据集 $\chi ^ { \prime }$ ，仍划分其为 $M$ 个数据片，第 $\mathbf { \Sigma } _ { m }$ 个数据片及其索引仍记为 $S p l i t _ { { m } }$ 和 $S p l i t I n d e x _ { m }$ 。对某个数据片 $S p l i t _ { { m } }$ ，Map 函数计算其中数据点与各聚类中心的距离并就近关联片中数据点到相应的聚类中心，并以 $< \mu _ { { } _ { k } } , C _ { { } _ { k , m } } >$ 的形式发布各中心点与片中数据点（其集合记为 $C _ { k , m }$ ）的关联关系。Reduce 函数

则整合与各中心点关联的所有数据点为一簇并计算其数目与总  
和，记第 $k$ 个中心点的簇为 $C _ { k }$ ，簇中数据点数目及总和分别为  
$n u m _ { k }$ 和 $s u m _ { k }$ ，然后向 $n u m _ { k }$ 和 $s u m _ { k }$ 中添加相应量的 Laplace 噪  
声得到 $n u m _ { k } ^ { \prime }$ 和 $s u m _ { k } ^ { \prime }$ ，进而计算出簇 $C _ { k }$ 的均值点作为新一代  
的聚类中心 $\mu _ { k }$ 。Master 接收 Reduce 任务输出的新一代  
{μ,μ,μ}并结合其在上一轮的值计算是否满足收敛条件以  
及判断迭代次数是否达到上限，进而决定是进入下一轮迭代还  
是终止算法并给出聚类结果。Master 共指派 $M$ 个 Map 任务和  
$K$ 个Reduce 任务 $\mathsf { \Omega } _ { \circ } \mathbf { M } \mathbf { a } \mathsf { p }$ 函数及Reduce函数的伪代码如下所示：map(IndexSplitlndexm,DataSplit $S p l i t _ { { m } }$ ）for $\mathbf { k }$ from 1 to K:（20 $C _ { k , m } { = } \mathrm { n e w } \ \mathrm { S e t } ( ) ;$ //为中心点 $\mu _ { k }$ 建立一个空的集合for each xiin Splitm :find the nearest centre μk ;add $x _ { i }$ t0 $\mu _ { k }$ 's $C _ { \boldsymbol { k } , m }$ ：，for $\mathbf { k }$ from 1 to K:EmitIntermediate( $\cdot \mu _ { k } , \ C _ { k , m } )$ reduce(Point $\mu _ { k }$ , Iterator sets)// sets 是各段数据 $C _ { \boldsymbol { k } , m }$ 的集合for $\mathbf { k }$ from 1 to K:（20 $C _ { k } = \mathrm { n e w ~ S e t ( ) } ;$ //为中心点 $\mu _ { k }$ 建立一个空的集合for each $C _ { k , m }$ in sets:Merge $\big ( C _ { k } , \ r _ { k , m } \big )$ ：Calculate $n u m _ { k }$ and $s u m _ { k }$ of $C _ { k }$ ；Addlaplace noise and get numk'sumk';update $\mu _ { k }$ by $s u m _ { k } ^ { \prime } / n u m _ { k } ^ { \prime }$ ；（204号 $\mathrm { E m i t } ( \mu _ { k } , \mathbf \Sigma _ { n u m _ { k } ^ { ' } } ) ;$ （20

# 2.2 差分隐私分析

由上述，在聚类分析的每一次迭代过程中，数据集 $\chi$ 的 $M$ 个数据片上各有一个Map 任务，Map 任务的输出又被划分为$K$ 个部分并行地由对应的Reduce 任务完成数据的整合与新一代聚类中心的计算。因此每一次迭代得到的聚类结果是各Reduce任务输出的并行组合，设第 $\mathbf { \xi } _ { l }$ 次迭代各Reduce任务的输出都可以满足 $\varepsilon _ { \iota }$ -差分隐私保护，由前文所述的差分隐私的并行组合性，则第 $\mathbf { \xi } _ { l }$ 次迭代的输出可以满足 $\varepsilon _ { l }$ -差分隐私保护，而聚类分析的最终结果相当于多次迭代过程的序列组合的输出设总迭代次数为 $L$ ，由差分隐私的序列组合性，算法的最终输出满足 $( \sum _ { l = 1 } ^ { L } \varepsilon _ { l } ) \cdot$ 差分隐私保护。本文采用文献[9]的隐私保护预算分配策略，设总的预算为 $\mathbf { \sigma } _ { \varepsilon }$ ，则给予每一次迭代剩余隐私预算的一半，即取第 $\mathbf { \Phi } _ { l }$ 次迭代的隐私保护预算 $\varepsilon _ { l }$ 为 $\varepsilon / 2 ^ { l }$ ，如此不论算法做了多少次迭代，总有 $( \sum _ { l = 1 } ^ { L } \varepsilon _ { l } ) < \varepsilon$ 。需要注意的是，应将初始簇的选取及初始聚类中心的生成看做第一次迭代。

由第 $\mathbf { \Phi } _ { l }$ 次迭代的隐私保护预算 $\varepsilon _ { l }$ ，可以计算出聚类中心点$\mu _ { k }$ 的簇 $C _ { k }$ 中数据点数目 $n u m _ { k }$ 及总和 $s u m _ { k }$ 需要添加的Laplace噪声量的大小。首先分析num及 $s u m$ 的全局敏感度，考虑修改或者删去 $\mathbb { R } ^ { T }$ 上归一化的数据集 $\mathcal { X } { = } \{ x _ { 1 } , x _ { 2 } , { \ldots } , x _ { N } \}$ 中的一点，易知num的全局敏感度 $\Delta f _ { n u m } = 1$ ，而因为归一化，xi ∈[0,1]T，由此知 sum的全局敏感度△fsum =T，因此聚类结果（或称查询序列）的 $\Delta f = ( T + 1 )$ 。所以第 $l$ 次迭代 $n u m _ { k }$ 及 $s u m _ { k }$ 需要添加的 Laplace 噪声量应为 Lap((T+1)×2' |ε)

综上，本文算法可以达到 $\varepsilon \cdot$ 差分隐私保护。

# 3 实验分析

本文算法的隐私性已经在上文中得到证明，因此实验部分主要考察算法的运行效率及其聚类结果的可用性。实验环境由作为主节点的一台计算机和作为分节点的三台计算机组成。每台计算机的CPU为双核 $3 . 3 \mathrm { G H z }$ ，内存4GB，操作系统为Ubuntu并部署了Hadoop2.6.0，算法实现语言为Java。实验用数据集为UCIKnowledge Discovery Archive database 中的 Ecoli 数据集（记录数为336，属性数为8，中心数为8)，Wine数据集（记录数为178，属性数为13，中心数为3)，HTRU2数据集（记录数为17898，属性数为9，中心数为2)，这三个数据集都适用于分类与聚类算法以及离群点检测算法的检验。在检验算法之前首先对这些数据集进行一些合理的预处理如对记录点的去重和各点属性值的归一化（min-max标准化)。实验中与本文算法作对比的是OEDP $\mathbf { k }$ -means[12]，IDP $\mathbf { k }$ -means[13],DPk-means[9]等目前基于差分隐私保护的聚类算法。

# 3.1聚类结果可用性的评估

考虑到实验所用的各数据集都已给出了参考分类，本文采用 $F$ -measure 值来评估各算法聚类结果的可用性。 $F$ -measure综合了信息检索与挖掘中的准确率(precision)和召回率(recall)，相比于其他一些评估方法更为中肯。假设某数据集中的记录总数为 $N$ ，标准聚类结果为 $\mathcal { P } = \{ P _ { 1 } , P _ { 2 } , . . . , P _ { K } \}$ ，算法的实际聚类结果为 $\mathcal { P } ^ { \prime } = \{ P _ { 1 } ^ { \prime } , P _ { 2 } ^ { \prime } , . . . , P _ { K } ^ { \prime } \}  \ , \ | P _ { i } | \stackrel { \left. } { \right. } | P _ { i } ^ { \prime }$ 分别为 $P _ { i }$ 和 $P _ { i } ^ { ' }$ 中的记录数目， $\mid P _ { i } \cap P _ { i } ^ { \prime } \mid$ 为 $P _ { i }$ 和 $P _ { i } ^ { \prime }$ 交叉的记录数目，记第 $i ( 1 \leq i \leq K )$ 个聚类的准确率和召回率分别为 $P r e c _ { i }$ 和 $R e c _ { i }$ ，则：

$$
P r e c _ { i } = \frac { \mid P _ { i } \cap P _ { i } ^ { \prime } \mid } { \mid P _ { i } \mid } , R e c _ { i } = \frac { \mid P _ { i } \cap P _ { i } ^ { \prime } \mid } { \mid P _ { i } ^ { \prime } \mid }
$$

二者的加权调和平均（取准确率与召回率同样的权重）为

$$
F _ { i } = \frac { 2 \cdot P r e c _ { i } \cdot R e c _ { i } } { P r e c _ { i } + R e c _ { i } }
$$

然后对各 $F _ { i }$ 取加权平均即为算法聚类结果的可用性度量

$$
F – m e a s u r e = \sum _ { i = 1 } ^ { K } \frac { \lvert P _ { i } \rvert } { N } F _ { i }
$$

$F$ -measure的取值范围是[0,1],值越大则说明聚类结果的可用 性越高。

# 3.2算法参数选取

首先，对于隐私保护预算 $\boldsymbol { \varepsilon }$ ，一般在[0.05,1]中取值，因此线性地在该区间中取值来观察其对算法的可用性和执行效率的影响。

其次，对于聚类数 $K$ ，因为实验中用到的各数据集都已给出了参考分类，而本文主要关注的是 $\mathbf { k }$ -means算法中的离群点消除、初始中心点选取和对差分隐私的支持，因此取各数据集参考分类的数目为其聚类数K。

最后，在本文算法和OEDP $\mathbf { k }$ -means算法对离群点的处理过程中，都涉及 $r .$ .最近邻区域的概念并对参数 $\boldsymbol { r }$ 较为敏感。参考文献[19]中的方法以 $F$ -measure为目标函数对参数 $\boldsymbol { r }$ 进行调整并取最优，即对Ecoli数据集取其 $\boldsymbol { r }$ 为3，对Wine 数据集取其 $\boldsymbol { r }$ 为1，而对HTRU2 数据集取其 $\boldsymbol { r }$ 为7，并在后续的实验中将各数据集 $\boldsymbol { r }$ 值代入本文算法与OEDP $\mathbf { k }$ -means算法。

# 3.3可用性与运行效率对比及分析

首先，在Ecoli数据集和Wine 数据集上单机运行了本文算法，OEDP $\mathbf { k }$ -means 算法，IDPk-means 算法和 DP $\mathbf { k }$ -means算法。对每一次在[0.05,1]中线性取得的隐私保护预算 $\mathbf { \Psi } _ { \varepsilon }$ ，都重复执行上述四种算法5次，以取得各算法的 $F$ -measure值和执行所耗时间的平均值。考虑到IDP $\mathbf { k }$ -means算法并不包含对离群点的处理而DP $\mathbf { k }$ -means算法不包含任何附加的初始化策略，这里的执行耗时是在完成聚类初始化（如可能的离群点消除与初始聚类中心的选取）后各算法聚类过程所耗的时间。具体情况如下图1到图4所示。

![](images/831994c9cda5c806494a985a12cc87cc0b80811b8f616ecb0655e29405326709.jpg)  
图1Ecoli数据集上各算法的可用性

![](images/47a21f1db3f8718c78d66c6389b81c593e1ec9dc23a11eb3a9a0990bd5aad199.jpg)  
图2Ecoli数据集上各算法的执行效率

![](images/b09678a8191cb51d7e334c401c3cd6a45900ece96960bf59ef9d0830871a3fb2.jpg)  
图3Wine 数据集上各算法的可用性

![](images/b26266566629b2a327f406e2f7504f22eb8d3970d211e428a405a67c512bf540.jpg)  
图4Wine 数据集上各算法的执行效率

由图1到图4可知，对隐私保护预算 $\boldsymbol { \varepsilon }$ 的每一个值，本文提出的算法相比于其他算法都有着更高的F-measure 值和更少的聚类耗时；并且当 $\boldsymbol { \varepsilon }$ 变化时，本文算法耗时的波动相比其他算法较小；另外，F-measure值代表的聚类结果可用性随着 $\mathbf { \Sigma } _ { \varepsilon }$ 的增加隐私保护水平的降低而提高。

从算法设计的角度而言，相比于一般的DP $\mathbf { k }$ -means算法，本文算法在提供差分隐私保护的同时，对离群点和初始聚类中心的处理提升了聚类结果可用性；对于离群点的判定，本文主要利用的是数据点的最近邻超球半径，而OEDPk-means算法所用的最近邻密度实际上是最近邻超球半径的倒数，二者在导出判定阈值上没有本质区别，因此省去倒数计算的本文算法更为简洁，此外本文算法导出判定阈值的过程是并行化的；对于初始聚类中心的选取，IDPk-means算法中简单地将所有数据点均匀划分为 $K$ 部分并求其中心的方法对聚类的优化并不够好，OEDP $\mathbf { k }$ -means算法则是将所有数据点先按最近邻密度排序然后均匀划分为 $K$ 部分并求其中心，该方法虽优于IDP $\mathbf { k }$ -means但当 $K$ 个数据簇在高维空间对称分布且簇内密度均匀时得到的初始中心会趋于集中而发生劣化，而本文算法充分利用了计算离群点判定阈值时生成的距离矩阵，选取的初始聚类中心可以更接近实际的中心点，从而减少了聚类过程的迭代次数，也避免了过多噪声的引入，因此在实验中较OEDPk-means和IDPk-means算法表现更好。因此，依靠更合理的离群点处理和初始聚类中心选取策略，对于同等级的差分隐私保护，本文算法在聚类结果的可用性以及聚类效率等方面相比其他三种算法有更优的表现。

其次，考察在不同数据量下多节点并行处理对本文算法的加速情况。在HTRU2数据集上截取不同数量的记录集作为待处理数据集。对每一次截取所得数据集，单机运行本文算法，单机运行OEDP $\mathbf { k }$ -means算法，3个子节点运行本文算法各5次取运行时间的平均值。这里的运行时间包含算法中的聚类初始化过程（离群点消除与初始聚类中心选取）耗时。具体图5所示。

![](images/e53d16e67a879339e81aefd6bbc5b7386ab829d853042599d65643891a90989a.jpg)  
图5HTRU2数据集上各情况的执行效率

由图5可知，单机运行下本文算法的耗时较OEDPk-means算法更低，这主要是因为本文算法对离群点的判定更为简洁，且对初始聚类中心的选取策略更为合理。而3节点下的本文算法耗时相比单机时有显著下降，这说明MapReduce框架下的本文算法可以很好地通过多节点并行计算来提高聚类算法的执行效率。另外，图中三种情况的耗时基本和截取数据集中的记录数呈二次曲线，这主要是由于为完成离群点的判定，需要计算数据集中各记录点的欧氏距离矩阵，而该过程的计算复杂度下界关于数据集中的记录数是二次的。虽然在获得图5数据的过程中每一次运行都会计算一遍距离矩阵，但在实际中，同一数据集上的初始化过程计算一遍即可。

# 4 结束语

本文基于MapReduce计算框架提出了一种并行化的支持差分隐私保护和离群点消除的K-means聚类算法，给出了由数据集各点间的欧氏距离矩阵与最近邻超球半径导出离群点判定阈值的并行计算方案，以及在此基础上设计的满足差分隐私保护的初始聚类中心选取策略。理论分析与实验结果表明算法在隐私保护的有效性，聚类结果的可用性以及执行效率和可扩展性等方面取得了很好的平衡，相比于同类算法有较优的表现。在后续的研究中，计划尝试更多不同的隐私保护预算分配策略并探索本文算法的更多扩展和应用。

# 参考文献：

[1]Sweeney L.k-anonymity:a model for protecting privacy[J]. International Journal of Uncertainty,Fuzziness and Knowledge-Based Systems,2002,10 (05): 557-570.

[2]熊平，朱天清，王晓峰．差分隐私保护及其应用[J].计算机学报,2014, 37(1):101-122.   
[3]Machanavajjhala A,Kifer D, Gehrke J,et al.l-diversity: privacy beyond kanonymity[J].ACMTrans on Knowledge Discovery from Data,2007,1(1): 3-3.   
[4]WongRCW,Li Jiuyong,FuAWC,et al.(α,k) -anonymity: an enhanced k-anonymity model for privacy preserving data publishing [C]/ Proc of the 12th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.New York:ACMPress,2006:754-759.   
[5]Xiao Xiaokui, Tao Yufei.M-invariance: towards privacy preserving republication of dynamic datasets [C]//Proc of ACM SIGMOD international conference on Management of data.New York:ACMPress,2007: 689-700.   
[6] Wong R C W,FuA W C,Wang Ke,et al. Minimality atack in privacy preserving data publishing [C]//Proc of the 33rd International Conference on Very Large Data Bases.[S.l.]:VLDB Endowment, 2007: 543-554.   
[7]Dwork C.Differential privacy [C]// Proc of the 33rd International Colloquium on Automata,Languages and Programming.2oo6:1-12.   
[8]BlumA,Dwork C,McsherryF,et al.Practical privacy: the SuLQ framework [C]// Proc of the 24th ACM SIGMOD-SIGACT-SIGART Symposium on PrinciplesofDatabase Systems.New York:ACMPress,2005:128-138.   
[9]Dwork C.A firm foundation for private data analysis [J].Communications of the ACM,2011,54 (1): 86-95.   
[10]李洪成，吴晓平，陈燕.MapReduce 框架下支持差分隐私保护的Kmeans 聚类方法 [J].通信学报,2016,37(02):124-130.   
[11] Dean J,Ghemawat S.MapReduce: simplified data processing on large clusters [J].Communications of the ACM,2008,51(1):107-113.   
[12] Yu Qingying,Luo Yonglong,Chen Chuanming,et al. Outlier-eliminated Kmeans clustering algorithm based on differential privacy preservation [J]. Applied Intelligence,2016,45 (4): 1179-1191.   
[13]李杨，郝志峰，温雯，等．差分隐私保护K-means聚类方法研究[J].计 算机科学,2013,40(3):287-290.   
[14] Dwork C.Differential privacy in new settings [C]//Procs of the 21st Annual ACM-SIAM Symposium on Discrete Algorithms.Society for Industrial and Applied Mathematics,2010: 174-183.   
[15]Dwork C,Mcsherry F,Nissim K,et al.Calibrating noise to sensitivity in private data analysis [C]// Theory of Cryptography. Berlin: Springer,2006: 265-284.   
[16]Mcsherry F D.Privacy integrated queries:an extensible platform for privacy-preserving data analysis [C]//Proc of ACM SIGMOD International Conference on Management of data.New York:ACMPress,20o9:19-30.   
[17] Celebi M E,Kingravi HA,Vela PA.A comparative study of efficient initialization methods for the K-means clustering algorithm [J].Expert Systems with Applications,2013,40(1): 200-210.   
[18] Aggarwal C C.Outlier analysis [C]// Data Mining.[S.1.]:Springer International Publishing,2015:237-263.   
[19] Angiulli F,Fassetti F.Dolphin: an efficient algorithm for mining distancebased outliers in very large datasets [J].ACM Trans on Knowledge Discovery from Data,2009,3 (1): 4.