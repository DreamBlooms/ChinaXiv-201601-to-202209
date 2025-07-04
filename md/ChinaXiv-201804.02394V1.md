# 基于分段的移动对象轨迹简化算法

张甜，杨智应

(上海海事大学 信息工程学院，上海 201306)

摘要：GPS 的高采样率使轨迹的数据规模巨大，在实际应用中难以处理，需要依赖轨迹简化算法对原始数据进行压缩。针对此问题，提出了一种新的基于速度分段的轨迹简化算法，即STS算法，在保留速度特征的同时保留了给定轨迹的时空特征。STS 算法将速度值分组成若干间隔，将轨迹分割成速度保留段，计算各轨迹段的SED阈值，通过在每个子轨迹段上应用TD-TR算法导出简化的轨迹。通过真实的数据集进行广泛实验，验证所提出的算法比ATS 算法具有更好的性能。

关键词：移动对象；轮廓系数；TD-TR算法；CART决策树；轨迹简化 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.02.0090

# Segmentation-based trajectory simplification algorithm

Zhang Tianl, Yang Zhiying² (Schoolof Information Engineering,Shanghai Maritime University,Shanghai2Ol3o6,China)

Abstract:The high samplingrateofGPSmakesthedata setof the trajectory huge,whichis diffcult to handle in practical applications.Itneeds toelyon trajectorysimplificationalgorithmtocompresstheoriginaldata.Aimingat tis problem,anew simplificationalgorithbasednspeedsegmentationwasproposed,amelySTSalgorithm,whichpreservedthespatioteoral characteristics whilepreserving the velocitycharacteristicsofagiventrajectory.TheSTSalgorithmdividedthevelocityvalues into several intervalsand divides the trajectory into velocity-preserving segments.ItcalculatedtheSEDthresholdof each trajectorysegment and derives a simplified trajectory by applying the TD-TR algorithmon each sub-trajectory segment. Extensive experiments withreal datasets demonstrate thatthe proposedalgorithmhas beterperformance than ATSalgorithms. Key Words: moving object; silhouete coefficient; TD-TR algorithm; CART; trajectory simplification

# 0 引言

近年来，全球范围内销售的GPS设备数量大幅增长。研究市场格局的信息技术公司Canalys在报告中称，2006年至2007年期间GPS 装置的销售数量增长了 $1 1 6 \%$ 。以 GPS 为基础的移动设备所构建的基于位置的服务和应用代表着迅速扩大的消费者市场。2009年，预估有2700万台配备GPS的智能手机在全球各地销售，仅在消费市场上就将全球GPS用户群带到至少6800 万人[2]。这些设备有能力产生、存储和传输轨迹数据。轨迹被定义为由位置（纬度，经度）和时间信息组成的三元组数据流。

目前基于位置的应用程序在使用轨迹数据时主要存在三个问题。首先，大量的轨迹数据的存储可能会快速地淹没可用的数据存储空间。例如，如果轨迹点数据以每10s的时间间隔被收集，那么1GB 的存储容量仅能存储约4000 个轨迹点[3。因此，如何有效地存储和查询GPS 轨迹是一个值得研究的领域

6]。其次，通过蜂窝或卫星网络发送大量轨迹数据的成本非常高，一般每兆字节在5\~7美元[7]。因此，假设追踪4,000 辆车的轨迹，一天的成本约为 $5 0 0 0 { \sim } 7 0 0 0$ 美元，每年约为180000\~2,500000 美元。最后，随着轨迹数据的规模增大，从数据中检测有效的特征信息将变得更加困难。缩减轨迹数据的规模有可能加速轨迹模式的挖掘[8]。

# 1 相关工作

# 1.1轨迹简化算法的研究现状

最早的基于距离的轨迹压缩算法是Douglas 和Peucker 提出的 Douglas-Peucker 算法（简称DP 算法）[9]，其递归地选择垂直距离大于给定阈值的点，直到所有保留点满足条件。后来Meratnia和Rolf提出了TD-TR算法[3，是一种自顶向下的时间比算法，它通过用SED 代替垂直距离来充分考虑时空特征。TD-TR算法的基本思想是：给定轨迹 $T$ 和参数 $\varepsilon$ ，通过重复添加 $T$ 中的点得到一个新的轨迹 $T ^ { \prime }$ ，直到 $T ^ { \prime }$ 的时间-同步欧氏距离（SED）小于 $\varepsilon$ 。该算法最初使用轨迹的第一个和最后一个点来近似原始轨迹。然后，重复选择引起最大SED误差的点，并使用该点来更准确地近似原始轨迹的过程。当最大SED误差小于 $\varepsilon$ 时，该过程停止。

Wu 等人提出了OpeningWindow Time-Ratio 算法[1o]，使用SED 代替垂直距离来考虑时间特征。2013年，Long 等人[提出了基于方向的轨迹简化算法，通过给定的角度阈值来简化轨迹，使求出的简化轨迹最大角度值不大于给定的角度阈值。在文献[11]的基础上，文献[12]提出了简化轨迹的数量在不大于给定值的情况下，使得简化轨迹与原始轨迹方向阈值最小的简化算法。Deng等人[13基于文[11]提出了基于方向的实时简化算法。称这类轨迹简化算法为基于方向的轨迹简化算法(DPTS)。

在最近的研究中，Lin等人[14考虑轨迹的速度特征，提出了速度保留的ATS算法。ATS算法首先使用肘方法确定k值将速度值聚类分段表示，将原始轨迹分解成速度保留子轨迹。然后根据基于最小长度原理（MDL）的阈值决策模型，从而得出不同子轨迹的空间误差阈值。最后使用Douglas-Peuker算法用于导出简化轨迹。ATS算法在将速度值聚类过程中使用EIbow方法需要人为判断，无法直接得到K-means聚类所需k值，对分段后的轨迹使用Douglas-Peucker算法推导出简化轨迹。本文对其进行改进，使用轮廓系数法计算 $\mathbf { k }$ 值实现批量化聚类，并在简化过程中加入时间维度，使用TD-TR算法推导出简化轨迹，进一步考虑了轨迹的时空特性，减小SED误差。

# 1.2定义与记号

定义1轨迹点。定义 $p$ 为轨迹点，表示为一个三元组，即 $p = \left( x , y , t \right)$ ，组内对应属性分别代表该点的经度、纬度、时间。

定义2原始轨迹。原始轨迹 $T$ 为若干有序轨迹点的集合。$T = { \big ( } p _ { 1 } , p _ { 2 } , . . . , p _ { n } { \big ) } { \big ( } i \in { \big [ } 1 , n { \big ] } { \big ) }$ ，其中 $p _ { i } = \left( x _ { i } , y _ { i } , t _ { i } \right)$ 且$t _ { 1 } < t _ { 2 } < . . . < t _ { i } < t _ { n }$ 9

原始轨迹 $T$ 中轨迹点的个数用 $| T |$ 表示，则 $T$ 中轨迹段的个数为 $\left| T \right| { - } 1$ 或 $n - 1$ 。

定义3简化轨迹。原始轨迹 $T$ 经过算法删除若干轨迹点（除首尾点），简化轨迹 $T _ { s i m }$ 是简化后有序轨迹点的集合。定义 为 $T _ { s i m } = \left( p _ { s _ { 1 } } , p _ { s _ { 2 } } , p _ { s _ { 3 } } , . . . , p _ { s _ { m } } \right)$ $\left( 1 \leq s _ { 1 } < s _ { 2 } < s _ { m } \leq r \right.$ 且 $m \leq n$ ）

简化轨迹 $T _ { s i m }$ 中轨迹点的个数用 $\left| T _ { s i m } \right|$ 表示，则 $T _ { s i m }$ 中轨迹段的个数为 $\left| T _ { s i m } \right| { - } 1$ 或 $m - 1$ 。

定义4轨迹段。原始轨迹 $T$ 或简化轨迹 $T _ { s i m }$ 中，对轨迹点 $p _ { i }$ 和 $p _ { j } \left( 1 \leq i \leq j \leq n \right)$ 的连线，用 ${ p _ { i } p _ { j } }$ 表示。如果（20 $j - i = 1$ ，则认为 $p _ { i }$ 和 ${ { p } _ { j } }$ 是相邻的，相邻两点之间所连的线段称为轨迹 $T$ 或轨迹 $T _ { s i m }$ 中的轨迹段。

定义5轨迹段的长度、平均速度。原始轨迹 $T$ 或简化轨迹 $T _ { s i m }$ 中，对轨迹点 $p _ { i }$ 和 $p _ { j } \left( 1 \leq i < j \leq n \right)$ ，若 $p _ { i }$ 和 ${ { p } _ { j } }$ 相邻，则轨迹段的长度用 $d \Big ( \overline { { p _ { i } p _ { j } } } \Big )$ 表示，相应轨迹段的平均速度用 $\nu \bigg ( \overline { { p _ { i } p _ { j } } } \bigg )$ 表示。

$$
\nu \Big ( \overline { { p _ { i } p _ { j } } } \Big ) = \frac { d \Big ( \overline { { p _ { i } p _ { j } } } \Big ) } { p _ { j } . t _ { j } - p _ { i } . t _ { i } }
$$

# 1.3基于分段的轨迹简化问题定义

速度保留轨迹简化问题定义如下。给定原始轨迹 $T$ 和如表1所示的速度-误差表，其包含速度间隔和SED 误差阈值的集合，推导出简化轨迹 $T _ { s i m } = \left( p _ { s _ { 1 } } , p _ { s _ { 2 } } , p _ { s _ { 3 } } , . . . , p _ { s _ { m } } \right)$ ，其满足以下要求：a）对于 $T _ { s i m }$ 中的轨迹段，原始轨迹点与其相对应的简化后轨迹之间的时间-同步欧式距离小于ε，其中ε为v(PiPj)所在速度间隔中相应的 SED 误差阈值。b） $\left| T _ { s i m } \right|$ 最小化。

表1速度-误差表  

<html><body><table><tr><td>速度值</td><td>误差阈值</td></tr><tr><td>V1-V2</td><td></td></tr><tr><td>V2-V3</td><td>ε2</td></tr><tr><td>V3-V4</td><td></td></tr></table></body></html>

速度一误差表是该问题的输入之一，它表示在不同的速度下应采用不同的SED误差阈值。简化的轨迹可以理解为通过使用尽可能少的点来保持位置和速度特征。

# 2 基于分段的轨迹简化算法

# 2.1STS算法的框架描述

在本节中，提出了基于分段的轨迹简化算法（STS）。简而言之，STS算法首先从原始轨迹的观察中导出速度误差表，然后使用该表导出简化的轨迹。STS算法的框架如图1所示。首先，从速度值的分布中找出代表性的速度间隔。然后，基于这些代表性的速度间隔，通过它们将整个轨迹划分成若干子轨迹，每个子轨迹具有与其他子轨迹具有显著不同的速度值。根据速度-误差表和子轨迹的平均速度来确定合适的阈值。最后，通过TD-TR算法推导出简化的子轨迹，通过连接简化后子轨迹从而获得简化轨迹。STS算法的细节将在以下部分进行描述。

![](images/ac4b32993cd57f9d3d1d23ca51893e6000919c0e21cfd6f965f7e74bba084831.jpg)  
图1 STS算法框架

# 2.2导出代表速度区间

本节介绍了构造速度-误差表时，设置速度间隔的方法。为了确定这些速度间隔的分割方法，本文将聚类方法应用于轨迹数据集的速度特征，从而将速度值划分为若干组。使用K-means对速度值进行聚类以获得具有代表性的速度间隔，其中k值是数据所分类数，应由用户给出，但从数据集属性的先验知识无法判断k的合适值。因此，本文使用了轮廓系数方法[15]来确定k 的取值。轮廓系数旨在将某个对象与自己的簇的相似程度和与其他簇的相似程度进行比较。轮廓系数最高的簇的数量表示簇的数量的最佳选择。轮廓系数结合了凝聚度和分离度，其计算步骤如下：

a)对于第i个对象，计算它到所属簇中所有其他对象的平均距离，即i向量到同一簇内其他点不相似程度的平均值，记average(i）（体现凝聚度)

b)对于第i个对象和不包含该对象的任意簇，计算该对象到给定簇中所有对象的平均距离，即i向量到其他簇的平均不相似程度的最小值，记为 $\mathrm { m i n } ( i )$ （体现分离度）。

c)第i个对象的轮廓系数计算公式为

$$
S \left( i \right) = \frac { \operatorname* { m i n } \left( i \right) - a \nu e r a g e \left( i \right) } { \operatorname* { m a x } \left\{ a \nu e r a g e \left( i \right) , \operatorname* { m i n } \left( i \right) \right\} }
$$

由此可得，轮廓系数取值为[-1,1]，其值越大表示聚类效果越好，当计算结果接近0时，表明样本i在两个簇的边界上。当计算结果为负时，表明 $a \nu e r a g e ( i ) > \operatorname* { m i n } ( i )$ ，样本i被分配到错误的簇中，更应该被分配到其他簇中。

如图2所示，示例中为了求得13个点的最佳聚类 $\mathbf { k }$ 值，将k 值取为2、3、4、5、8并分别计算其轮廓系数，当 $\scriptstyle \mathbf { k } = 3$ 时计算出轮廓系数为0.722，此时轮廓系数最大，根据轮廓系数法原理，其值越大表示聚类效果越好，所以示例中将k值取3为最佳聚类k值。

![](images/d2a9f903c4ae7869c5a08dc39b5f69a0f5a3bae6e5c62c1f1a68fcb2b32fd279.jpg)  
图2计算轮廓系数求 $\mathrm { ~ k ~ }$ 值示例

# 2.3 分割原始轨迹

本节描述了如何将原始轨迹划分成若干子轨迹的方法，使得子轨迹之间的速度值具有显着差异。为了达到这个目的，使用CART决策树方法[1判断轨迹是否应分为两部分及如何分割。为了在本文问题中利用CART决策树方法的Gini 系数分类法，原始轨迹 $T { = } \big ( p _ { 1 } , p _ { 2 } { , } { , \underline { { . . . , p _ { n } } } } \big )$ 被转换为（204 $T ^ { \nu } = \left( L _ { 1 } , L _ { 2 } , . . . , L _ { { n - 1 } } \right)$ ，其中 $L _ { \mathrm { { } } _ { i } }$ 为轨迹点速度值在速度分类区间中的所属类，即速度标签。速度 $\nu \big ( p _ { i } , p _ { i + 1 } \big )$ 均包含在此中。例如，给定 $\nu \big ( p _ { 2 } , p _ { 3 } \big ) = 2 8$ 及表2中的速度值分类区间， $L _ { _ 2 }$ 的值可以被推导出为1。Gini系数定义为$G i n i \big ( T ^ { \nu } \big ) = 1 - \sum _ { i = 1 } ^ { k } \Biggl ( \frac { N \big ( { \cal L } _ { i } \big ) } { k } \Biggr ) ^ { 2 }$ ，其中 $k$ 为速度标签 $T ^ { \nu }$ 的总大小， $N ( \cdot )$ 为 $T ^ { \nu }$ 中 $L _ { \mathrm { { } } _ { i } }$ 相等时出现的数量总和， $\frac { N \left( L _ { i } \right) } { k }$ 示各类速度标签在 $T ^ { \nu }$ 中出现的频率。例如,$T = \left( p _ { 1 } , p _ { 2 } , . . . , p _ { 1 3 } \right)$ ，假设其转换后的结果 $T ^ { \nu }$ 为 $\begin{array} { r } { T ^ { \nu } = \left( L _ { 1 } , L _ { 2 } , . . . , L _ { 1 2 } \right) } \end{array}$ $= \left( 0 , 0 , 1 , 0 , 0 , 0 , 1 , 1 , 2 , 2 , 2 , 2 \right)$ 。原始轨迹点数为13，所以转换后速度标签数为12， $k = 1 2$ ， $L _ { 1 } = L _ { 2 } = L _ { 4 } = L _ { 5 } = L _ { 6 } = 0$ ，所以$N ( 0 ) { = } 5$ ， $L _ { _ 3 } = L _ { _ 7 } = L _ { _ 8 } = 1$ ，所以 $N { \big ( } 1 { \big ) } = 3$ ，（204号 $L _ { \mathrm { 9 } } = L _ { \mathrm { 1 0 } } = L _ { \mathrm { 1 1 } } = L _ { \mathrm { 1 2 } } = 2$ ，所以 $N { \left( 2 \right) } = 4$ 。数据 $L _ { _ i }$ 计算所得的Gini系数越大，代表 $L _ { \mathrm { { } } _ { i } }$ 在整体数据集合中的差异性越大。因此，在本文的设置中，所需的子轨迹是基尼系数小的轨迹。划分原始轨迹的方法在算法1中列出。

# 算法1分割原始轨迹（tr_partition算法）

输入：原始轨迹 $T$ ，分割阈值 $G i n i _ { \operatorname* { m i n } }$ 输出： ${ { S } _ { T } } = \left\{ { { T } _ { 1 , m } } , { { T } _ { m , \mathrm { { o } } } } , . . . , { { T } _ { p , n } } \right\}$ 1: $S _ { T } = \emptyset$ 2 $T ^ { \nu } = \left\{ { { L _ { 1 } } , { L _ { 2 } } , . . . , { L _ { n - 1 } } } \right\}$ 3: if Gini(T.)≤Ginimin then

4: return{T}   
5: end   
$\begin{array} { r } { \mathbf { \Sigma } _ { 6 : } \ i = \arg \operatorname* { m i n } _ { \mathbf { \Sigma } _ { 0 < i < n } } \Big ( G i n i _ { s p l i t } \left( T _ { 1 , i , n - 1 } ^ { \nu } \right) \Big ) ; } \end{array}$ （204号   
$\begin{array} { r l } & { \mathrm { \ l } S _ { T } = \mathrm { S } _ { T } \cup t r _ { - } p a r t i t i o n { \left( T _ { \mathrm { 0 } , i } , G i n i _ { \mathrm { m i n } } \right) } } \\ { \mathrm { \ l } ? } & { \cup t r _ { - } p a r t i t i o n { \left( T _ { i , n } , G i n i _ { \mathrm { m i n } } \right) } ; } \end{array}$   
8: return $S _ { T }$

表2速度分类  

<html><body><table><tr><td>类</td><td>速度（km/h）</td></tr><tr><td>0</td><td>0-25</td></tr><tr><td>1</td><td>25-47</td></tr><tr><td>2</td><td>47-88</td></tr><tr><td>3</td><td>>88</td></tr></table></body></html>

a)使用最小 $G i n i _ { s p l i t }$ 将 $T ^ { \nu }$ 分割成两个轨迹段$\begin{array} { r } { T _ { 1 , i } ^ { \nu } = \left( L _ { 1 } , L _ { 2 } , . . . , L _ { i } \right) \mathcal { K } T _ { i + 1 , n - 1 } ^ { \nu } = \ \left( L _ { i + 1 } , L _ { i + 2 } , . . . , L _ { n - 1 } \right) , } \end{array}$ $G i n i _ { s p l i t }$ 的定义如下：$G i n i _ { s p l i t } \left( T _ { 1 , i , n - 1 } ^ { \nu } \right) { = } \frac { N _ { 1 } } { N } G i n i { \left( T _ { 1 , i } ^ { \nu } \right) } + \frac { N _ { 2 } } { N } G i n i { \left( T _ { i + 1 , n - 1 } ^ { \nu } \right) }$ 其中 $N$ ，$N _ { 1 } , N _ { 2 }$ 是 $T ^ { \nu }$ 、 $T _ { 1 , i } ^ { \nu }$ 和 $T _ { i + 1 , n - 1 } ^ { \nu }$ 的大小，且 $N _ { 1 } + N _ { 2 } = N$ 。b)对于 $T _ { 1 , i } ^ { \nu }$ 和 $T _ { i + 1 , n - 1 } ^ { \nu }$ ，计算它们的基尼系数 $G i n i { \left( T _ { 1 , i } ^ { \nu } \right) }$ 及$G i n i \Big ( T _ { i + 1 , n - 1 } ^ { \nu } \Big )$ 。对于每一个子轨迹，如果其基尼系数大于给定的阈值 $G i n i _ { \mathrm { m i n } }$ ，递归地进行操作 a)。

# 2.4计算SED误差阈值

本节讨论如何为每个速度间隔选择SED误差阈值 $\varepsilon$ 。在此步骤之后，可以建立速度-误差表。由于这些子轨迹具有相似的速度标签，所以观察这些子轨迹可以帮助每个代表速度间隔决定适当的 SED 误差阈值。SED(Synchronized Euclidean Distance)即同步欧式距离，如图3所示，SED距离为 $P _ { i }$ 与 $P _ { i }$ 之间的欧氏距离，其中 $P _ { i } ^ { \phantom { \dagger } }$ 坐标位置的具体计算公式如下。

$$
\begin{array} { c } { \Delta e = t _ { e } - t _ { s } } \\ { \Delta i = t _ { i } - t _ { s } } \end{array}
$$

![](images/5620b44ee0d6377836d41bbdaab801ce8827a3d4aba32c29237ffe202524d08b.jpg)  
图3 SED 距离的定义

简化后较低的误差和较小的轨迹规模通常是互相制约的，因此难以同时实现。为了在这两个因素之间取得良好的平衡，定义了一个Balance 值，表示每一次迭代循环的SED 误差比分与轨迹规模比分之间的和，Balance值越低表示更好的拟合简化。因此，我们可以获得不同速度变化范围内子轨迹的优化 $\varepsilon$ 。在开始迭代时初始的子轨迹表示为 $T = \left( p _ { 1 } , p _ { n } \right)$ 。简化子轨迹的 Balance 值定义如下：

$$
B a l a n c e \left( T _ { s i m } \right) = \frac { s e d \_ e r r o r _ { \varepsilon } } { s e d \_ e r r o r _ { \mathrm { m a x } } } + \frac { s i z e _ { \varepsilon } - 2 } { s i z e _ { \mathrm { m a x } } - 2 }
$$

$s e d \_ e r r o r _ { \mathrm { m a x } }$ 为最简轨迹，即 $\scriptstyle { T = \left( p _ { 1 } , p _ { n } \right) }$ 到原始轨迹中某一点的最大 SED 距离， $s i z e _ { \operatorname* { m a x } }$ 是原始轨迹的大小。sed_error是在简化过程中从未简化的原始轨迹中的某一点到已简化轨迹之间的最大SED距离，伴随着轨迹简化的进度将不断变化。size.是在简化过程中随之对应的简化轨迹的大小，同样随着轨迹简化不断变化。 $\varepsilon$ 的增加会增加error的值，但减少 size 的值，反之亦然。因此，最小化balance 值可以得到在size 和error之间达到最佳平衡的阈值 $\varepsilon$ 。

本文中计算SED误差阈值如算法2中所示。该算法的基本原理是找到简化轨迹和原始轨迹之间的最大偏差，即原始轨迹中的点和简化轨迹中的点之间最远SED距离，并将此值设置为最大 $\varepsilon$ ，并将该点添加到简化轨迹。因此，最大偏差缩小，简化轨迹的规模增大。然后，计算该简化轨迹的Balance值。当误差可以得到最小Balance 值时，则存储最小Balance 值和误差值。整个过程重复，直到简化轨迹 $T _ { s i m }$ 包含原始轨迹 $T$ 中的所有点。最后计算出导致最小Balance值的误差值 $\varepsilon$ 。算法2的时间复杂度为 $O { \big ( } \log n { \big ) }$ 。

算法2计算SED误差阈值

输出：合适的误差阈值 $\varepsilon$ 1: ${ \cal T } ^ { \prime } { = } \left( p _ { 1 } , p _ { n } \right)$ 2: while $\big | T ^ { \prime } \big | \neq \big | T \big |$ d

3: 找到从 $T$ 到 $T ^ { \prime }$ 之间SED距离最远的点 $p _ { i }$ ，   
4: 将 ${ { p } _ { i } }$ 添加至 $T$   
5: $b a l a n c e = B a l a n c e ( T " ) ;$ （204号   
6: if balance <balancemin then   
7: $b a l a n c e _ { \operatorname* { m i n } } = b a l a n c e ;$ （204号   
8: $\varepsilon = e r r o r ( T ^ { \prime } ) ;$   
9: end   
10: end   
11: return ε;

# 2.5 导出简化轨迹

本节介绍在经过以上步骤，得出速度-误差表后，使用速度-误差表简化轨迹的方法。在通过速度值将轨迹划分为子轨迹之后，使用TD-TR 算法[3]进行简化轨迹。TD-TR 算法是对Douglas-Peucker 算法的改进，Douglas-Peucker 算法使用垂直欧氏距离(PED)计算点 $p _ { i }$ 与近似轨迹之间的误差距离，具有忽略时态数据的局限性，TD-TR算法通过使用同步欧氏距离(SED)克服了这个限制。从速度-误差表可以得到速度间隔和相应的SED误差阈值，根据每个子轨迹的速度间隔，可以从速度-误差表中获得相应的SED误差阈值，该误差阈值是用于简化该子轨迹的TD-TR算法中使用的参数。最后将简化好的子轨迹按照时间顺序全部连接，得到最终的简化轨迹 $T _ { s i m }$

TD-TR 算法的时间复杂度为 $O \big ( n ^ { 2 } \big )$ ，所以文中的 STS 算法的时间复杂度为 $O \big ( n ^ { 2 } \big )$

# 3 实验与结果

# 3.1实验配置及数据集

在本节中，进行了大量的实验。具体配置如下：处理器为Intel(R) CoreTM i5-6300HQ, $\mathrm { C P U } @ 2 . 3 0 \mathrm { G H z } 8$ GB RAM中实现;实验环境为Windows10操作系统和Anaconda3开发环境，Python3.6实现。实验数据从项目MicrosoftGeoLife 得到[17,18],MicrosoftGeoLife的位置数据是在两年多时间中（2007年4月到2009年8月）从178个人中获得的。数据集中包括各种运输方式，如骑自行车，步行和铁路。大约 $91 \%$ 的轨迹采样率为1-

5秒，大部分数据的收集发生在中国北京附近，少量在美国和欧洲。

表3数据集  

<html><body><table><tr><td>序号</td><td>名称</td><td>轨迹数量 （条）</td><td>轨迹点数目 （个）</td></tr><tr><td>1</td><td>微小数据集</td><td>865</td><td>10-300</td></tr><tr><td>2</td><td>小数据集</td><td>660</td><td>300-800</td></tr><tr><td>3</td><td>中数据集</td><td>515</td><td>800-1600</td></tr><tr><td>4</td><td>大数据集</td><td>822</td><td>1600-6400</td></tr><tr><td>5</td><td>超大数据集</td><td>201</td><td>> 6400</td></tr></table></body></html>

为了确定算法对于简化性能与轨迹长度之间的关系，将原始轨迹分为5类：微短轨迹，短轨迹，中等轨迹，长轨迹和超长轨迹。微短轨迹中每个轨迹有10-300个点。短轨迹中每个轨迹有300\~800个点。中等轨迹中每个轨迹有 $8 0 0 { \sim } 1 6 0 0$ 个点。长轨迹中每个轨迹有1600\~6400个点。超长轨迹中每个轨迹有6400多个点。通过这五类轨迹，如表3所示，将原始数据集也分为五类：微小数据集，小数据集，中数据集，大数据集和超大数据集。序列号为1\~5，对不同规模数据集下的压缩时间、简化率、SED误差、速度误差和空间误差进行测试。

首先对本文所提出的STS算法与ATS算法在压缩时间和简化率等方面进行了比较，说明了STS算法能够在简化率持平的情况下减少压缩时间。然后，对于STS 算法、ATS算法、Douglas-Peucker 算法（简称DP 算法）及TD-TR算法，比较了四个算法之间的平均SED误差、速度误差以及空间误差。

# 3.2度量指标及算法比较

3.2.1基于简化时间及简化率的评估

简化时间是指原始轨迹段进行简化过程的运行时间，是衡量轨迹简化效率的重要依据，在实际应用中，简化时间越短越好。图4描述了STS算法与ATS算法的实际执行时间，STS算法的平均压缩时间比ATS算法短，并且伴随着数据集的增大，差距愈加明显。

简化率（R）是反应轨迹数据大小变化的性能指标，其定义为 $R { = } 1 { - } \frac n m$ ，其中 $\mathrm { ~ m ~ }$ 代表原始轨迹的轨迹点数目，n代表简化后轨迹的轨迹点数目。图5对两种算法的简化率进行了对比，随着原始轨迹规模的增大，ATS与STS算法的平均简化率均会提高，两种算法的简化率总体相差不大。当原始轨迹较小时（800个点以下），STS的简化率比ATS 略高，但当轨迹较大时，STS算法的简化率略低于ATS算法。

![](images/c8b05fa1212702117533f37d887f91855848ea86aab9342e970f0830a821e06f.jpg)  
图4不同规模数据集下两种算法平均压缩时间的比较

![](images/024bc1c270c6407162d8e1ca03a8faa91c7422c12f9db713029be92c6615f6a4.jpg)  
图5不同规模数据集下两种算法平均简化率的比较

# 3.2.2基于误差度量的评估

SED 误差是指原始轨迹点 $p _ { i }$ 与简化后轨迹中的估计点$p _ { i }$ '之间的距离（即 SED 距离）， $p _ { i }$ '坐标位置的计算方式与2.4 节中相同。如图6所示，原始轨迹 $T = \left( p _ { 1 } , p _ { 2 } , . . . , p _ { 8 } \right)$ 及简化轨迹 $T _ { s i m } = \left( p _ { 1 } , p _ { 4 } , p _ { 6 } , p _ { 8 } \right)$ ， $p _ { 2 }$ 的估计点是 $p _ { 2 }$ '，则 $p _ { 2 }$ 的SED 误差是 ${ { p } _ { 2 } }$ 与 $p _ { 2 }$ '的距离。

![](images/3c7ad788c78d0371ee7af15993f9472c44a2bf4c7eb25436d34bd8a9cb9a3867.jpg)  
图6SED误差示例

空间误差与 SED 误差类似，只是 SED 误差中计算 $p _ { i }$ 与$p _ { i }$ '之间的SED距离，空间误差则计算其垂直欧氏距离。

给定原始轨迹点 $p _ { i } = \left( x _ { i } , y _ { i } , t _ { i } \right)$ 和 $p _ { i + 1 } = ( x _ { i + 1 } , y _ { i + 1 } , t _ { i + 1 } )$ $p _ { i }$ 的速度计算为 $\frac { d \big ( p _ { i } , p _ { i + 1 } \big ) } { t _ { i + 1 } - t _ { i } }$ 对于 $p _ { i }$ 和 $p _ { i + 1 }$ 的估计点 $p _ { i }$ '和（204号 ${ p _ { i + 1 } } ^ { \prime }$ ，类似地计算 $p _ { i }$ '处的速度。相对于 $p _ { i }$ 的速度误差被定义为原始轨迹点 $p _ { i }$ 的速度与简化后轨迹点 $p _ { i }$ '的速度差值。

SED误差、速度误差及空间误差是衡量轨迹简化算法性能的重要依据。图7\~9分别描述了STS、ATS、DP 和TD-TR四种算法在SED误差、速度误差、空间误差方面的比较。由图7可得，随着数据集的增大，四种算法的SED误差均会增大，本文所提出的STS 算法的SED误差增幅远远低于ATS和DP 算法，当数据集较小时STS的SED误差最小，但在数据集较大时TD-TR 算法的 SED 误差最小。

图8中四种算法的速度误差均会随着轨迹规模的增大而增大，在数据集较大时，DP与ATS算法的速度误差增幅较大，STS 与TD-TR 算法的速度误差大致相同，在大数据集中TDTR 算法速度误差更小，但在小数据集中 STS 优于TD-TR 算法。

由图9可以得到以下结论：STS算法的空间误差在小数据集中最小，但在大数据及中略高于TD-TR算法。

![](images/7a2faa465762456f8f9104f9e89df959843559926585434c75bc1d2aedf033e8.jpg)  
图7平均SED误差

![](images/13ef8f950cb78f092004698522591644ad4cca072f3e05aa82793411204bf642.jpg)  
图8平均速度误差

![](images/104c043a04a8d74389738b30168e864d925058264f74c0c088eee809a5e5c634.jpg)  
图9平均空间误差

# 4 结束语

本文研究移动对象原始轨迹的简化轨迹的简化问题。在ATS算法的基础上，提出了基于分段的轨迹简化算法STS算法。STS算法首先通过聚类方法从速度值的分布中导出代表性速度区间，通过其代表性速度值，将整个轨迹划分成若干子轨迹。然后分别计算各个子轨迹段的SED误差阈值。最后使用TD-TR算法导出简化轨迹。为了验证本文提出的算法的有效性，使用真实轨迹数据集进行大量的实验。实验表明，STS算法在压缩时间、简化率、平均SED误差、平均空间误差等方面优于ATS算法，总体来说，STS在微小数据集中的表现更好。在接下来的研究中，为了满足基于位置服务工具对移动对象数据分析处理的需求，将进一步与深度学习相结合，考虑如何对移动对象轨迹数据进行预测等一系列处理，研究预测模型，将简化前后轨迹放入预测模型做对比衡量。

# 参考文献：

[1]Canalys.Worldwide mobile navigation device market more than doubles [R]. [S.l.] :Canalys Research Release,2007.   
[2]Canalys.North America overtakes EMEA as largest satellite navigation market [R].[S.1.]:Canalys Research Release,2009.   
[3]Wilson B D,Mannucci AJ,Edwards C D.Subdaily northern hemisphere ionospheric maps using an extensive network of GPS receivers [J].Radio Science,2016,30 (3):639-648.   
[4]Lichman M, Smyth P.Modeling human location data with mixtures of kernel densities [C]// Proc of ACM SIGKDD International Conference on Knowledge Discoveryand Data Mining.New York:ACMPress,2014:35- 44.   
[5]Song Renchu,Sun Weiwei,Zheng Baihua,et al.PRESS:a novel framework of trajectory compression in road networks [J].Proceedings of the VLDB Endowment,2014,7(9): 661-672.   
[6]Sun Penghui, Xia Shixiong, Yuan Guan,et al.An overview of moving object trajectory compression algorithms[J].Mathematical Problemsin Engineering,2016,2016 (3):1-13.   
[7]Muckell J, Olsen PW,Hwang JH,et al.Compression of trajectory data: a comprehensive evaluation and new approach [J]. Geoinformatica,2014,18 (3): 435-460.   
[8]He Xinran,David Kempe. Stability of influence maximization [J].2015: 1256-1265.   
[9]Douglas D H, Peucker T K.Algorithms for the reduction of the number of points required to represent a digitized line or itscaricature [J]. Cartographica the International Journal for Geographic Information & Geovisualization,1973,10(2):112-122.   
[10] Meratnia N,By RAD.Spatiotemporal Compression Techniques for Moving Point Objects [C]//Proc of International Conference on Extending Database Technology. 2004: 765-782.   
[11] Cheng Long, Wong R C, Jagadish H V. Direction-preserving trajectory simplification [J].Proceedings of the VLDB Endowment,2013,6(10): 949- 960.   
[12] Cheng Long，Wong R C,Jagadish H V. Trajectory simplification:on minimizing the directionbased error [J].Proceedings of the VLDB Endowment,2014,8(1): 49-60.   
[13] Deng Ze,Han Wei,Wang Lizhe,et al.An efficient online directionpreserving compression approach for trajectory streaming data [J].Future Generation Computer Systems,2017,68:150-162.   
[14] Lin Chihyu,Hung C C,Lei P R.A velocity-preserving trajectory simplification approach [C]// Technologies and Applications of Artificial Intelligence.2017: 58-65.   
[15]朱连江，马炳先，赵学泉．基于轮廓系数的聚类有效性分析[J].计算 机应用，2010,30 (s2):139-141.(Zhu LianJiang，Ma Bingxian,Zhao Xuequan. Clustering validity analysis based on silhouette coefficient [J]. Journal of Computer Applications,2010,30 (s2):139-141.)   
[16]陈辉林，夏道勋．基于CART 决策树数据挖掘算法的应用研究[J].煤 炭技术，2011,30 (10):164-166.(Chen Huilin,Xia Daoxun.Applied research on data mining based on CART decision tree algorithm [J].Coal Technology,2011,30(10): 164-166.)   
[17] Zheng Yu,Li Quannan,Chen Yukun, et al. Understanding mobility based on GPS data [C]// Proc of International Conference on Ubiquitous Computing. New York:ACMPress,2008:312-321.   
[18] Zheng Yu, Zhang Lizhu,Xie Xing,et al.Mining interesting locations and travel sequences from GPS trajectories [C]// Proc of International Conference on World Wide Web.New York:ACMPress,2009:791-800.