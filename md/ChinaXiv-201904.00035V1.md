# 基于印象空间的互联网广告效果评价

宋永强1²，王红1,2，王露潼¹，胡晓红1(1.山东师范大学 信息科学与工程学院，济南 250358;2.山东省分布式计算软件新技术重点实验室，济南 250014)

摘要：互联网广告效果评价是网络营销的核心问题，但是评价方法存在信息源单一、无差别假、全局假设等问题，对互联网广告效果评价提出了巨大挑战。寻找一种全新的衡量互联网广告效果的评价指标成为亟待解决的任务。首先，创新地提出印象空间概念，作为更有效的网页广告效果评价指标，以解决信息源单一问题；其次，分析用户类型、行为方式、行为过程等特征对互联网广告效果评价标准的影响，消除用户无差异假设所造成的评价偏差；再次，引入网页的局部性特征，分析页面布局、广告与页面内容相关性等因素对互联网广告效果的影响，以消除全局性假设；最后，构建基于多模态特征的印象空间模型来预测互联网广告效果。实验结果表明，提出的印象空间对互联网广告质量评价的准确率显著提升，达到 $9 2 . 4 \%$ 。而且印象空间模型的预测结果不仅更加准确科学，而且具有明显的可解释性。

关键词：印象空间；用户行为；兴趣区域；互联网广告效果中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2018.10.0824

Evaluation of Internet advertising effect based on impression space

Song Yongqiang1,2, Wang Hongl.2†, Wang Lutong1, Hu Xiaohong1 (1.College of Information Science&Engineering，Shandong Normal UniversityJinan 250358,China;2.Shandong Provincial Key Laboratory for Distributed Computer Software Novel Technology,Jinan 250014,China)

Abstract: Internet advertising efectivenessevaluation is the core isue ofonline marketing.At present,the evaluation criteriaof Internet advertising effectiveness are diferent.However,the evaluation methods have problems such as single source ofiformation,nodiference infalseood,andglobalassumptions,whichposesgreat challnges totheealuatioof Internetadvertising effectiveness.Findinganewevaluation index tomeasure theeffectivenessofInternetadvertisinghas become an urgent task.This paperfirst proposes theconcept ofimpresion space innovatively as amore effctive evaluation indexof webpage advertising efects tosolve the single problemofinformationsource.Secondly,this paperanalyzes the impact of user types，behaviors，behavioral processs andother characteristics on the evaluation criteria of Internet advertising effectivenessand eliminatestheevaluationbiascaused bytheuser's indiference hypothesis.Thirdly,this paper introduces the localcharacteristicsof web pages,and analyzes the influence offactors such as page layout,advertisement and pagecontent relevanceon Internet advertising effects to eliminate global assumptions.Finally, tis paperconstructsan impression space model based on multimodalfeatures to predict theefectiveness of Internet advertising.The experimental results show that the accuracy rate of the impresion space proposed by this paper is significantly improved to $9 2 . 4 \%$ Moreover,the prediction results of the impression space modelare not only more accurate and scientific,but also have obvious interpretability.

Keywords:impression space; the behavior of the user; the area of interest

# 0 引言

互联网广告作为互联网的产物，是一种通过网络服务传播的营销信息。它凭借强烈的交互性、传播的广泛性和灵活的时效性等特点，成为现代广告媒介的重要组成部分。最新研究数据表明，新媒体技术时代的互联网广告已经渗入到现代社会生活的各个方面。投放互联网广告的目标是提高广告主的投资回报率，提高浏览者的用户体验，以及实现产业链的多方共赢。实现此目标的核心是如何更加精准地投放广告。而解决该核心问题的关键是准确地评价广告效果。目前存在的信息源单一、无差别假、全局假设设等问题，对互联网广

告效果评价提出了巨大挑战。

a)现阶段互联网广告效果评价指标单一，多以点击率、转换率为指标。点击率指标最大的缺点是忽略了那些用户可能注意到，但是并没有点击的广告。而转化率则是将用户对网页的浏览和对广告的浏览混为一谈。

b)目前的互联网广告效果评价忽略了用户的差异性，仅仅考虑用户的主动行为。事实上不同的用户类型、不同的思维方式以及不同的浏览习惯等用户差异对互联网广告效果具有重要的影响。

c目前的互联网广告效果评价具有全局假设，即是在整个网页范围内整体评价广告效果，而不考虑广告布局、广告与页面内容的相关性等细粒度差异对广告效果的影响。

本文认为，网页广告效果是由多种因素共同决定的，除了与广告本身有关，还与用户类型、用户的心理学特征、页面布局、浏览轨迹等多种因素相关。因此，本文提出了以印象空间作为网络广告效果的评价标准，并实现了基于印象空间的互联网广告效果评价方法。本文的主要贡献如下：

a)针对信息源单一问题，创新地提出印象空间概念，作为更有效的网页广告效果评价指标。

b)针对用户无差异假设，分析用户类型、行为方式、行为过程等特征对互联网广告效果评价标准的影响，消除用户无差异假设所造成的评价偏差。

c)针对全局性假设，引入网页的局部性特征，分析页面布局、广告与页面内容相关性等因素对互联网广告效果的影响。

d)在上述基础上构建基于多模态特征的印象空间模型，预测互联网广告效果。预测结果不仅更加准确科学，而且具有明显的可解释性。

# 1 相关工作

互联网广告与传统的四大传播媒体广告相比，具有覆盖面广、交互性强、成本低廉等诸多优点，在网络营销体系中具有举足轻重的地位。因此，互联网广告研究受到越来越多的关注。

目前，点击率作为互联网广告效果的评价标准，得到了较多关注，主要有基于位置的级联点击模型（location-basedclickmodel,LCM)[1]、垂直感知点击模型(vertical-awareclickmodelVCM)[2]、基于时间的点击模型(temporalclick model,TCM)[3]以及基于数学模型的点击模型。LCM 验证了用户的浏览顺序与搜索结果的位置顺序是一致的;VCM验证了不同的垂直搜索结果对用户的注视行为有很大影响，可以准确反映用户注视行径;TCM描述了用户的非顺序性点击行为，指出用户的浏览可能是非顺序的。在以数学为基础建立的点击模型中，Shan 等人[4]利用全耦合交互张量的因式分解预估点击率。Wang等人[5]利用局部马尔可夫链(PartiallyobservableMarkovPOM)模型预估点击序列，并通过数学公式一定程度上证明了模型的准确率，由于上述研究只关注于用户的主动行为，忽略了用户在浏览过程中的无意识行为，因此，研究结果难以完全反馈用户的真实意图，对互联网广告效果的评价出现偏差。

随着深度学习架构成熟，Qu等人[通过在嵌入层和全连接层之间引入点击层，提出基于乘积的神经网络(product-based neuralnetwork，PNN)模型。为了更好地解决特征组合问题，Shan等人[7提出可以自动组合特征的深度交叉模型，上述方法也可总结为架构深度网络自动学习数据特征增强数据表达能力，尽管深度网络架构可以有效的利用结构化神经网络模型，适应广告数据集中复杂的非线性映射关系，但它忽略了用户在点击预测的实际反馈。这使得研究者不得不寻找点击率以外的指标，更加准确地评价互联网广告效果。

于是，出现了一系列先进的互联网广告效果评价方法。赵慧芳等人[8利用熵权双基点法来评估互联网广告效果，有效解决信息偏差问题。邓文峰等人[9将率与点击率相结合，通过有效到达率表示受众比率进而评价互联网广告效果。吕鸿江等人[10]利用用户浏览方式研究互联网广告效果，陈磊等人[1分析用户与广告交互行为，总结了与热门词相关联的广告效果。虽然这些研究各有侧重，但是难以定义一个综合性的指标来评价互联网广告的实际效果。之后，胡晓红等人[12]提出了使用记忆度和兴趣度来衡量互联网广告效果，但是，研究过程忽略了不同的用户在接受、存储、转换、提取和使用广告时采用的方式存在差异。Wedel等人[13]在研究中曾指出，个体的差异性会对产品产生不同的印象。Dreze等人[14]亦指出了点击率对互联网广告衡量的弊端，他认为用户浏览广告的路径因个人经验而不同。遗憾的是，Dreze只是通过传统实验进行说明，缺少专业设备支撑的深入分析。第二种差异性是网页布局特点对用户加工信息产生的不同反馈。Wang等人[15]通过局部顺序点击模型(partially sequentialclickmodel，PSCM)得到了不同用户常用的浏览方式，但是，研究缺少考虑不同区域的网页广告产生的反馈信息差异以及用户个体间的差异。

在用户浏览行为研究中，多数研究人员将眼动追踪数据为基线，认为接近人眼浏览的数据为真实结果。眼动追踪数据可以确定用户关注的兴趣点及浏览轨迹，真实地反映用户的兴趣区域和兴趣活动，探索用户的无意识行为。但是，从目前已经查到的文献来看，眼动研究多集中在自然图像处理方面，在网页方面研究涉及较少。Renshaw等人[16]通过眼动实验研究图形设计，Shen 等人[17研究了网页广告的显著性（webpage saliency)，但是得到的AUC仅达到0.7206。随着眼动追踪技术的发展，眼动实验可以摆脱繁重的机械设备，使得研究内容不局限于理论方面。Xu等人[18]利用眼动数据处理视频问题，文献[19，20]融合眼动追踪数据和鼠标数据，预测用户对搜索结果满意度。因此，本文通过眼动实验获取眼动数据来研究用户的眼动轨迹，分析用户的心理活动等隐式信息，发现不同类型用户的浏览模式，获取用户隐士行为，寻找用户兴趣区域，提出更加客观准确的网络广告效果评价指标，为实现互联网广告的精准投放提供依据。

# 2 印象空间

提出以印象空间作为互联网广告效果评价指标。社会心理学家指出印象的形成过程是主体对客体特征的判断，印象受认知主体和客体对主体信息反馈等共同影响（由词向量表达印象空间 $\ c =$ （主体信息，客体反馈信息）)。

心理学研究表明，印象的形成可能受认知风格、情绪和客体反馈信息等影响，认知风格可划分独立和依存，用户情绪状态划分为心境和激情，客体反馈信息可划分为完全反馈，可能反馈，失败反馈。定义印象空间由2（风格） $\times 2$ （情绪状态） $\times 3$ （客体反馈信息）表达，如表1所示。

表1印象空间划分  
Table 1Impression space division   

<html><body><table><tr><td>风格</td><td>情绪状态</td><td>反馈信息</td><td>印象空间</td></tr><tr><td rowspan="5">独立</td><td rowspan="2">心境</td><td>完全反馈</td><td>存在印象</td></tr><tr><td>可能反馈</td><td>模糊印象</td></tr><tr><td></td><td>失败反馈</td><td>缺失印象</td></tr><tr><td rowspan="2">激情</td><td>完全反馈</td><td>存在印象</td></tr><tr><td>可能反馈</td><td>存在印象</td></tr><tr><td rowspan="5">依存</td><td></td><td>失败反馈</td><td>缺失印象</td></tr><tr><td></td><td>完全反馈</td><td>存在印象</td></tr><tr><td>心境</td><td>可能反馈</td><td>缺失印象</td></tr><tr><td></td><td>失败反馈</td><td>缺失印象</td></tr><tr><td></td><td>完全反馈</td><td>存在印象</td></tr><tr><td rowspan="2"></td><td>激情</td><td>可能反馈</td><td>模糊印象</td></tr><tr><td></td><td>失败反馈</td><td>缺失印象</td></tr></table></body></html>

# 3 用户类型划分

为了消除无差别假设，本文划分用户类型，分析不同用户对互联网广告效果评价的影响。

# 3.1用户组合属性

属性组合方式多种多样（如性格、行为习惯)，利用数理统计学中常见的分布组合用户属性。以正态分布为例，探究属性列的分布情况。对于 $\forall A _ { j } \in$ 属性集合 $A$ ，其中 $j \in ( 1 , m )$ ，任取属性集合 $A _ { j } = ( a _ { j 1 } , a _ { j 2 } , a _ { j 3 } , . . . . . . , a _ { j N } )$ 中 $\mathfrak { n }$ 个属性使得属性均值和方差分别为

$$
\mu = \frac { \displaystyle \sum _ { i = 1 } ^ { n } a _ { j i } } { \displaystyle \sum _ { i = 1 } ^ { n } 1 }
$$

$$
\sigma ^ { 2 } = \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( a _ { j i } - 1 ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { n } 1 }
$$

若对任意一个属性集合 $A _ { j } = ( a _ { j 1 } , a _ { j 2 } , a _ { j 3 } , . . . . . . , a _ { j N } )$ 满足独立同分布且满足 $E ( A _ { j } ) = \mu _ { n }$ ， $D ( A _ { j } ) = \sigma _ { N } { } ^ { 2 }$ 给定分布函数 $F$ 定义为

$$
F ( A _ { j } ) = P \{ \frac { \sum - N \mu } { \sqrt { N } \sigma } < a _ { j i } \}
$$

满足

$$
\operatorname* { l i m } _ { \infty } F ( A _ { j } ) = \operatorname* { l i m } _ { \infty } \{ \frac { \sum a _ { j i } - N \mu } { \sqrt { N } \sigma } < a _ { j i } \} = \frac { 1 } { \sqrt { 2 } \pi } \int e ^ { \frac { - t ^ { 2 } } { 2 } }
$$

满足分布的中心极限定理，其中 $\mu _ { \scriptscriptstyle N }$ ， $\sigma _ { N } { } ^ { 2 }$ 分别为整体属性的均值和方差。中心极限定理表明，当本文属性数据达到一定条件时的时候随机变量 $A _ { j } = \frac { \displaystyle \sum { a _ { j i } - N \mu } } { \displaystyle \sqrt { N } \mu }$ ∑a-Nu近似服从正态分布。若属性 $A _ { j }$ 满足中心极限定理，则 $A _ { j }$ 的分布可以用 $f _ { j } ( a _ { j i } )$ 描述即属性 $A _ { j }$ 的概率密度函数。

$$
f _ { j } ( a _ { j i } ) = \frac { 1 } { \sqrt { 2 \pi \sigma } } \exp [ - \frac { ( a _ { j i } - \mu ) ^ { 2 } } { 2 \sigma ^ { 2 } } ]
$$

满足正态分布的概率密度函数，可划分到正态分布的组合属性中，其他概率密度函数如表2所示，如果对于任意属性列满足概率密度函数分布情况（概率分布的未知量可能不同，但分布规律一致)，则将其划分为一个组合属性。

表2不同分布的概率密度函数  
Table 2Probability density functions with different distributions   

<html><body><table><tr><td>名称</td><td>概率密度函数</td></tr><tr><td>二项分布</td><td>fj(n)=CN p"qN-n</td></tr><tr><td>泊松分布</td><td>n! f(n)=are-a</td></tr><tr><td>指数分布</td><td>f(n)=e-rg</td></tr><tr><td>均匀分布</td><td>1 fj(n)=- max(aji)-min(aji)</td></tr></table></body></html>

# 3.2基于属性组合的用户类型划分

用户类型划分有两种方式，第一种由属性 $w _ { m }$ 直接决定，如图1所示。

第二种由单属性和组合属性共同决定，第一层贡献度 $w _ { l m }$ 称为单属性贡献度，第二层贡献度 $w _ { l t }$ 称为组合属性权重，如图2所示。

定义1属性子集。对于样本集合 $D = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . . . . , x _ { n } \}$ 存在每一个样本的属性集合 $A = \{ A _ { 1 } , A _ { 2 } , A _ { 3 } , . . . . . . , A _ { m } \}$ ，给定$G = \{ G _ { 1 } , G _ { 2 } , G _ { 3 } , . . . . . . , G _ { T } \}$ 是 $A$ 的 $T$ 个子集的集合。

![](images/6fffc2b0d96f9fec0a989fcc4def159b56a443cfeb9c17472294710dab01ab0a.jpg)  
图1用户类型划分图Fig.1User type partition

![](images/d9dd6ad5c7417127032f312c150cd5351f10b778291a42f03512795b1657e237.jpg)  
）基于属性组合的用户类型划分 Fig.2User type partition based on attribute combination

定义2属性权重。对于 $\forall G _ { t 1 } , G _ { t 2 } \in G _ { T }$ ，其中 $G _ { t 1 } \neq \emptyset$ ，$G _ { t 1 } \cap G _ { t 2 } = \emptyset$ 假定样本集合 $D$ 可以划分到 $k$ 个簇$C = \{ c _ { 1 } , c _ { 2 } , . . . . . . , c _ { k } \}$ ,则单属性权重 $W = [ w _ { l t } ] _ { k \times m }$ ，表示为第 $l$ 个簇中的第 $\mathbf { \chi } _ { t }$ 个属性的权重。组合属性权重 $V = [ \nu _ { l j } ] _ { k \times 6 }$ ，表示为第 $l$ 簇中的第 $j$ 个组合属性的权重。

对于单属性权重 $w _ { l j }$ 和组合属性权重 $w _ { l t }$ 分别满足：

$$
\sum _ { j \in G _ { i } } w _ { l j } = 1
$$

$$
\sum _ { t = 1 } ^ { T } w _ { l t } = 1
$$

$\forall l \in \{ 1 , 2 , 3 , . . . . . . , k \} a n d \forall t \in \{ 1 , 2 , 3 , . . . . . . , T \}$ ，使 $w _ { l j } \mathrm { ~ , ~ } w _ { l t }$ 满给定约束条件:

$$
\begin{array} { r } { \underset { w _ { i j } } { \mathop { \operatorname* { m i n } } } \displaystyle \sum _ { l = 1 } ^ { k } ( \sum _ { j = 1 } ^ { m } w _ { l j } \log w _ { l j } ) } \\ { \underset { w _ { i t } } { \mathop { \operatorname* { m i n } } } \displaystyle \sum _ { l = 1 } ^ { k } ( \sum _ { t = 1 } ^ { T } w _ { l t } \log w _ { l t } ) } \end{array}
$$

最优化目标函数 $P ( U , Z , w _ { l j } , w _ { l t } )$ ：

$$
P ( U , Z , w _ { l j } , w _ { l t } ) =
$$$$
\begin{array} { c } { { r ( { \boldsymbol { \omega } } , { \boldsymbol { \omega } } , { \boldsymbol { w } } _ { l j } , { \boldsymbol { w } } _ { l t } ) = } } \\ { { \displaystyle \sum _ { l = 1 } ^ { k } [ \sum _ { i = 1 } ^ { n } \sum _ { t = 1 } ^ { T } \sum _ { j \in G _ { i } } U _ { i l } \nu _ { l j } w _ { l t } d ( { x } _ { i j } , { z } _ { i j } ) ] + \alpha \sum _ { j = 1 } ^ { m } \nu _ { l j } \log { w _ { { \boldsymbol { \nu } } _ { i } } } + \beta \sum _ { t = 1 } ^ { T } w _ { l t } ] } } \end{array}
$$

$$
\begin{array} { l } { { \displaystyle \sum _ { l = 1 } ^ { k } U _ { i l } = 1 , U _ { i l } \in \{ 0 , 1 \} , 1 \le i \le n } } \\ { { \displaystyle \sum _ { l = 1 } ^ { k } w _ { l i } = 1 , w _ { l i } \in \{ 0 , 1 \} , 1 \le t \le T } } \\ { { \displaystyle \sum _ { j \in G _ { i } } \nu _ { l j } = 1 , \nu _ { l j } \in ( 0 , 1 ) , 1 \le t \le k } } \end{array}
$$

其中： $U$ 是一个参数为 $U _ { i l }$ 的 $n \times k$ 的矩阵。当 $U _ { i l } = 1$ 表示对于第 $i$ 的用户属于第 $l$ 类簇； $\boldsymbol { Z } = \{ Z _ { 1 } , Z _ { 2 } , Z _ { 3 } , . . . . . . , Z _ { k } \}$ 是一个 $k$ 维向量，表示 $k$ 的聚类中心。 $d ( x _ { i j } , z _ { l j } )$ 表示考虑第 $j$ 的属性，用户与第$l$ 的聚类中心的距离。

对于参数 $\nu _ { l j }$ 求解：

$$
\nu _ { l j } = \frac { \displaystyle { \exp \{ - \sum _ { i = 1 } ^ { n } U _ { i l } w _ { l t } d ( x _ { i j } , z _ { l j } ) \} } } { \displaystyle { \sum _ { h \in G _ { t } } \exp \{ - \sum _ { i = 1 } ^ { n } U _ { i l } w _ { l t } d ( x _ { i h } , z _ { l h } ) \} } }
$$

对于参数 $w _ { l j }$ 求解：

$$
w _ { l j } = \frac { \displaystyle \exp \{ - \sum _ { i = 1 } ^ { n } U _ { i l } \sum _ { j \in G _ { t } } \nu _ { l j } d ( x _ { i j } , z _ { l j } ) \} } { \displaystyle \sum _ { h \in G _ { t } } \exp \{ - \sum _ { i = 1 } ^ { n } U _ { i l } \sum _ { j \in G _ { t } } \nu _ { l j } d ( x _ { i h } , z _ { l h } ) \} }
$$

算法1基于属性组合的用户类型划分

Input: the number of clusters $\textbf { k }$ Output:optimal values $\mathsf { v }$ ， $\mathsf { w } , \mathsf { u } , \mathsf { z }$ Randomly choose k cluster centers，setallinitialweightsin $\pmb { \nu }$ and $\boldsymbol { \mathsf { W } }$ to equal values.

repeat   
update $\pmb { \ v }$ by(1)   
update W by（2)   
until the objective function $\mathsf { P } ( \boldsymbol { \mathsf { v } } , \boldsymbol { \mathsf { w } } )$ obtains its local   
minimum value

# 4 用户行为

利用频繁序列算法和路径合并算法，研究不同用户行为方式对互联网广告效果的影响。

# 4.1点击行为

通过Apriori算法寻找用户点击行为关联规则。已知Apriori算法先验定律（如果一个集合是频繁项集，则其所有子集都是频繁项集)，合并部分挖掘结果便于观测点击模式下的关联规则。利用关联规则研究用户点击偏好。关联规则中的基本概念为支持度和置信度。

定义3支持度。事务的一个频繁项集或者规则在所有事物中出现的频率，确定规则可以用于给定数据集的频繁程度，支持度通常用来删除那些无意义的规则，关联规则的支持度定义为 $s u p p o r t _ { A \Rightarrow B } = P ( A \cup B )$ 。

定义4置信度。一个事件Y在包含一事件X的事务中出现的频繁程度，置信度度量是通过规则进行推理可靠，关联规则 $\mathrm { A } { \Rightarrow } \mathrm { B }$ 的置信度为 $c o n f i d e n c e _ { A \Rightarrow B } = P ( B \mid A )$ 。

定义5频繁项集。

在关联规则挖掘中，满足一定最小置信度以及支持度的集合称为频繁集。

# 4.2浏览行为

通过路经合并算法寻找用户浏览偏好，以浏览模式分解思想（例如任意用户浏览模式路径为 $_ { 1  2  3 }$ ，其浏览模式可分解为 $1 {  } 2$ 和 $2 {  } 3$ 两种浏览模式的子路径）为基础。通过该思想挖掘出用户子路径，并合并子路经结合得用户浏览模式。

定义6用户浏览矩阵 $S _ { \mathcal { o } }$ 以前文提及的搜索引起的网页页面布局格式（共有10个URL，及右侧区域与AD区域）建立 $1 2 \times 1 2$ 的矩阵，关于矩阵中元素值 $S _ { i j }$ 其值的含义为页面访问次数（其中 $S _ { 1 2 }$ 值为4表示 $1 {  } 2$ 共出现在所有的浏览模式中共出现4次，矩阵元素值为4)。

$$
S = { \left[ \begin{array} { l l l } { s _ { 1 1 } } & { \dots } & { s _ { R 1 } } \\ { \dots } & { \dots } & { \dots } \\ { s _ { 1 R } } & { \dots } & { s _ { R R } } \end{array} \right] } _ { 1 2 \times 1 2 }
$$

定义7多频子路经。已知用户浏览矩阵 $S$ ，对用户浏览矩阵中计算矩阵的每一行的和记为 $S _ { i }$ ，其中$i \in \{ 1 , 2 , 3 , 4 , 5 , 6 , 7 , 8 , 9 , 1 0 , A D , R \}$ ，对于用户浏览矩阵 $s$ 进行处理，得到矩阵 $\Delta S$ ，对于矩阵 $\Delta S$ ，其元素值 $\Delta S _ { i j }$ 为 $\Delta S _ { i j } = S _ { i j } / S _ { i }$ 。规定一个阈值 $s$ ，若矩阵元素值 $\Delta S _ { i j } \ge S _ { i }$ ，则规定 $i  j$ 为多频子路径。

定义8路径合并。若 $m {  } n$ ， $n {  } l$ 分别为多频子路经，则路径合并为 $m {  } n {  } l$ ，其中对于 $\mathbf { \nabla } _ { m }$ ， $n$ ， $l$ 可以为单个页面布局的浏览位置也可以为其他的多频子路经。

# 5 兴趣区域

提出以注视时效和页面布局划分兴趣区域，消除全局假设对互联网广告效果的影响。

# 5.1 页面布局特点

页面布局特点通常由10个URL（主体内容)，以及广告区域部分与右侧部分构成，如图3所示。（L1、L2和L3分别表示广告出现在主体内容上方、下方及右侧合称AD区域)

用户在浏览网页时会因为视觉的特性，自身浏览习惯等形成了某种固有的浏览行为习惯，在实际操作中难以获取更多用户的浏览信息特点，若在后续的工作中对整个网页的信息研究，不仅工序繁琐，更会消耗大量工作时间，致使科研人员寻找有价值信息足够多、范围足够小的兴趣区域。

![](images/438a68e8b6ceaa4bba8b428ed981308bfcb28cb8ff7fb9894034c24480f3b285.jpg)  
图3页面布局图Fig.3Page layout

# 5.2基于注视时效的兴趣区域

定义9任意区域 $i$ 注视时间 $T _ { i }$ 为

$$
T _ { i } = \frac { F t i m e _ { i } + D t i m e _ { i } } { F c o u n t _ { i } }
$$

其中：Ftime为注视时间，Dtime为回看时间，Fcount为注视次数(fixationcount)。则在任意区域 $i$ 注视时效公式为

$$
\psi = \frac { T _ { i } } { \sum T _ { i } }
$$

利用注视时效和页面布局划分兴趣区域，保留广告区域AD 和右侧区域R作为2个单独区域进行研究；依据注视时效计算结果，取10个URL区域的平均注视时效，以此为基线，将10个URL区域内注视时效大于基线的作为兴趣区域，小于基线的作为非兴趣区域。

# 6 数据收集

本文提出印象空间概念，但现阶段缺少眼动追踪数据与用户印象空间相关的数据集，故首先进行大规模的数据收集活动。

# 6.1实验对象

通过招募方式随机选取本学校各个专业的本科生（年龄18\~21岁）自愿参加实验。所有实验人员无眼疾等疾病情况，符合眼动实验要求。

# 6.2实验器材

眼动实验仪器选用德国普升科技有限公司研发的眼动仪器Version2.4，其采样频率为 $1 2 0 ~ \mathrm { H z }$ 。记录和分析过程用其自带的IViewX、Experiment Center 和BeGaze，实验数据处理和分析选用Spyder及Java。

# 6.3实验材料

本文实验材料需要收集用户主体信息及用户浏览信息。

用户主体信息数据收集采取目前研究中采用较多的镶嵌图形测验（EFT)进行认知划分，利用美国著名心理学家Witk等人提出心理学情况状态测试表进行情绪状态划分。

用户浏览信息使用网页材料。选取了不同类型的物品，如奢侈品、门票、家居电器等，覆盖范围广。模拟用户日常生活中选择的心态，每种类型有两种不同品牌。搜索引擎选择百度，因为它既是全球最大的中文搜索引擎，并且与大多数中文搜索引擎排版基本相同。为保证实验效果更加真实，让被试尽可能像往常一样自由浏览，如点击和滚动屏幕。并且为了较好的控制实验变量，保证被试看到的某一类型的SERP是一样的，将从搜索引擎上爬下来，并只保留所要研究位置的商业推广在浏览结束后检查被试者记忆力情况，用以描述客体信息反馈情况。实验过程中，通过眼动仪器记录被试的眼动信息，通过网页中嵌入的JavaScript代码获取用户的点击信息。

# 6.4实验程序

a)收集用户主体信息。测验要求被试者在较复杂的图形中找到并描绘出隐藏在其中的一个指定的简单图形，该测验一共25道题目，题型由易到难程度递增。

b)收集用户浏览信息。网页浏览开始前，先进行眼动仪器的标准校正，当被试达标则开始正式实验。用户根据屏幕中的提示了解接下来需要进行的商品类型，如屏幕提示产品类型是手机，这意味着用户将要以一位手机购买者的心态浏览某手机品牌的SERP。浏览过程与日常浏览网页一样。当遇到感兴趣的地方，用户可以点击该条目。为防止用户疲劳，每位用户最多随机展示6条SERP，用户可以根据自身状态随时停止实验进程，并在实验结束后收集用户记忆情况。

c印象空间信息。通过用户风格测试题目及浏览时的情绪状态以及网页对用户的反馈信息三部分知识划定印象空间。

# 7 印象空间分析

点击率一度作为互联网广告的评价的黄金指标，但营销商为了获得更高的经济效益，进行大量广告投递导致互联网广告质量下降，使得网民缺乏兴趣点击广告。网民对互联网网页平均不到 $1 \%$ 的点击情况，使得点击率难以真实反映出互联网广告的效果，最新数据表明，网络广告平均点击率已从 $30 \%$ 降低到 $0 . 5 \%$ 以下。对于品牌广告来说，广告的成功不仅取决于是否点击或者阅读广告后是否购买该商品，而更多地应该表现为用户是否对该商品形成固有的印象，形成品牌效应，创造独特良好的品牌或产品形象，提升较长时期内的离线转换率。

# 7.1印象空间模型特征

以印象空间作为类标签，将实验收集到的数据作为模型特征。表3展示影响用户产生印象空间的特征。

表3眼动特征  
Table 3Eye movement characteristics   

<html><body><table><tr><td>特征集</td><td>特征</td></tr><tr><td>鼠标信息</td><td>点击信息</td></tr><tr><td>眼动信息</td><td>结束时间，点击次数，浏览位置等</td></tr><tr><td>广告体眼动特征</td><td>注意持续时间，注视次数等</td></tr><tr><td>广告自身特征</td><td>广告覆盖率，广告位置等</td></tr><tr><td>用户特征</td><td>年龄，性别等</td></tr></table></body></html>

关于本文类标签印象空间，印象空间的量化方法如下所示：

定义9认知风格 $\ L _ { \cdot } =$ 独立1，依存0；

情绪 $\mathbf { \bar { \rho } } = \mathbf { \bar { \rho } }$ 心境1，应激0;  
反馈信息 $\ v { x } =$ 完全反馈2；部分反馈1；失败反馈0；则标签印象空间的向量表达式为  
存在印象[(1,1,0);(0,1,2);(1,0,2);(1,0,1)；(0,0,2)]模糊印象[(1,1,1);(0,0,1)]  
缺失印象[(1,1,0);(1,0,0);(0,1,1);(0,1,0);(0,0,0)]

# 7.2有效性验证

为了进一步验证本文提出的印象空间的有效性，进行了一次数据采集与标注工作，实验具体内容为：准备网页材料，主要通过爬虫手段保存下多张网页；收集多人次的网页浏览信息、广告点击信息；使用卡方检验方法进行验证。卡方检验是一种用于检测预测值与实际值之间偏离程度的常见假设检验方法，卡方检验数值越大，表示预测值与实际值之间的偏离程度越大，所使用的预测方法越不符合；相反，卡方检验值越小，预测值与实际值之间的偏离程度越小，所使用的预测方法越好。本文将专家量表标注看成实际值，将印象空间存留能力和点击情况分别看成卡方检验中的预测值。

以印象空间和专家量表标注为例，卡方检验具体步骤如下：

a 提出原假设：H0印象空间能力和专家量表标注之间不存在偏差， $\mathrm { S i g { = } 0 . 0 5 }$ 。

b计算理论数：

$$
T _ { R C } = \frac { n _ { R } \times n _ { C } } { n }
$$

c计算 $\chi ^ { 2 }$ 值：

$$
\chi ^ { 2 } = 0 . 5 7 9
$$

d查值 $\chi ^ { 2 }$ 表：

$$
\chi ^ { 2 } { = } 0 . 5 7 9 < \chi _ { s i g = 0 . 5 ^ { 2 } } = 3 . 8 4
$$

按照 $\mathrm { S i g { = } 0 . 0 5 }$ 标准，不能拒绝H0，因此可以认为两种方法无差别。所以印象空间可作为实验数据标签。

# 7.3印象空间模型构建

针对印象空间模型本文提出两种结构堆叠方法：第一种方法基于用户类型及用户偏好的信息如图4所示。

![](images/c187d3faceba15c8ec5a661d8bab67767d7359b5c5898e0b3d68af8db3c81965.jpg)  
图4印象空间模型  
Fig.4Impression space model

算法2印象空间模型构建算法

Input: $\scriptstyle A = \{ ( \mathrm { t } ^ { 1 } , \mathrm { y } ^ { 1 } ) ( \mathrm { t } ^ { 2 } , \mathrm { y } ^ { 2 } ) . . . . . . . ( \mathrm { t } ^ { 3 } , \mathrm { y } ^ { 3 } ) \}$ ，NumberTrees，Rate. Output:Y.   
$A _ { k } =$ activationscreenl(A,k）//用户类型筛选   
$B _ { k } =$ activationscreenl $( A _ { k } )$ //用户偏好筛选   
Random forest rf A =new random forest()   
$r + \textsf { A }$ .build Forest(A，NumTrees，Rate ，depth) for all $t ^ { i }$ in A   
do   
return( $p _ { A } ^ { i }$ ， $y _ { A } ^ { i }$ ）   
end for   
Random forest rf $B _ { k }$ =new random forest()   
$\boldsymbol { \mathsf { r } } \boldsymbol { \mathsf { f } } \ B _ { k }$ build Forest( $B _ { k }$ ,NumTrees,Rate ,depth) for all $t ^ { i }$ in A do   
return( $p _ { B _ { k } } ^ { i } \mathrm { ~ , ~ } y _ { B _ { k } } ^ { i }$ ）   
end for   
for all $t ^ { i }$ in A do   
get max( $P _ { A } ^ { i } \ , \ P _ { B } ^ { i }$ ）   
第二种如图所5示   
算法3印象空间模型构造算法   
Input: $A { = } \{ ( \mathrm { t ^ { 1 } , y ^ { 1 } } ) ( \mathrm { t ^ { 2 } , y ^ { 2 } } ) . . . . . . . ( \mathrm { t ^ { 3 } , y ^ { 3 } } ) \}$ ,NumberTrees，Rate. Output:Y.   
$A _ { k } =$ activationscreenl(A,k)   
$B _ { k } =$ activationscreenl(Ak)   
classification model $\mathsf { K } ( ~ B _ { k }$ ）

![](images/698f86f4aa139f223d9218a7025e708b45a007bc7ed268107f4d560cdbbe7870.jpg)  
choose the optimal classification model

# 7.4实验结果

为了说明提出方法的有效性，本文进行三组实验。第一组实验选择最优用户类型数使不同用户群之间差异性较大并分析用户行为；第二组实验架构最优的印象空间模型；第三组实验对比实验结果展示。

# 7.4.1用户行为分析

利用Robert提出的组内平方和差决定最佳用户类型数量结果如图6所示，用户类型聚类结果如图7所示。结果表明考虑两类用户类型时为最佳聚类个数，各个类型间存在较大差异性信息，利于挖掘用户浏览、注意点等行为动态信息。

![](images/6bbee62f6b7d3469a5b5b59078934f53e5a4aca051017ab28fc6bf3c22a49527.jpg)  
Fig.5Impression space model   
图6聚类个数Gap

![](images/8362f2ea358324fa52a24674bb0679829cefb80734f6267a426bf4e575bc1f3b.jpg)  
图5印象空间模型  
Fig.6Number of clusters Gap   
图7用户类型划分Fig.7Divides user types

利用频繁序列挖掘不同用户类型下的点击偏好关联规则结果如表4所示。

# 表4用户点击偏好

Table 4User click preferences   

<html><body><table><tr><td>用户类型</td><td>用户点击偏好</td></tr><tr><td>1</td><td>1，2=3；3，4>6;</td></tr><tr><td rowspan="3"></td><td>1，2=R</td></tr><tr><td>3，6=>2；3，6=>1； 4，6=>3；4，6=>7；</td></tr><tr><td>3，5→7；2，4=3；</td></tr><tr><td>2</td><td>1，2=R</td></tr></table></body></html>

结果表明用户点击行为规律：两种用户类型的点击都为自上而下进行。两种用户类型的点击多为顺序性的，但也存在部分回访点击行为。两种用户的点击行为都为自上而下进行点击，当用户对前部分点击时可能表示用户已经引起用户兴趣，此时用户便会对后续部分进行点击；当引起用户兴趣时，用户还可能会来回点击从而充分了解信息。

通过路经挖掘算法得到不同用户类型的浏览模式序列如表5所示。

Table 5User browsing preferences   

<html><body><table><tr><td>类型</td><td>用户浏览偏好</td></tr><tr><td>1</td><td>AD→1→234→56; 1→AD-→2→3→4→→5; 1→AD-→R-→2→4→5→→6; R→1→2→1→3;</td></tr><tr><td></td><td>1→2R→34→5; 2→1→34→5-6→AD; 2→1→3→4→5→6→7→9→AD;</td></tr><tr><td>1→AD→R-→3-→4→5;</td><td>1→2-3→4-→5→6-→7→8-→9→10→AD; 1→2-→3→→4→→5→6;</td></tr><tr><td>2</td><td>2→1→3-→4→R;</td></tr></table></body></html>

结果表明用户浏览顺序基本满足垂直假设即自上而下逐步浏览。

利用注视时效计算方法可得用户在不同区域的注视时效如表6所示。

表5用户浏览偏好  
表6注视时效表  
Table6Fixation timetable   

<html><body><table><tr><td>类型</td><td>用户1 用户2</td></tr><tr><td>1</td><td>10.58% 11.07%</td></tr><tr><td>2</td><td>10.11% 10.27%</td></tr><tr><td>3 9.09%</td><td>10.86%</td></tr><tr><td>4</td><td>8.64% 9.03%</td></tr><tr><td>5 7.56%</td><td>6.69%</td></tr><tr><td>6 6.56%</td><td>6.17%</td></tr><tr><td>7 6.08%</td><td>6.17%</td></tr><tr><td>8 5.48%</td><td>5.31%</td></tr><tr><td>9 5.69%</td><td>5.31%</td></tr><tr><td>10 5.10%</td><td>5.87%</td></tr><tr><td>AD 11.47%</td><td>10.64%</td></tr><tr><td>R 13.63%</td><td>12.60%</td></tr></table></body></html>

利用注视时效和页面布局得到用户兴趣区域，如图8所示。

![](images/04f0ac7901bae19c0fc17f1a86f69591b761ce8b0b17f8fb74ff39fa3a3d4881.jpg)  
图8兴趣区域图

通过兴趣区域得用户浏览行为有如下特点：a)用户对网站的关注热点度呈现F形，关注热度由上至下、由左至右递减；b用户注视点的聚簇多集中在页面的前三分之二部分，而这部分往往是最早展示出来的地方；c用户对页面左侧的总体关注时间往往超过右侧区域。但这种分析是抽象化，需要进一步分析用户浏览行为。

# 7.4.2印象空间模型

以机器学习中经典的分类器作为基模型结合决策树分枝筛选架构印象空间模型，结果如图9所示

![](images/dfa9b4e68e16840fbe4516cf66668ae1f83de143c91b71b59eaa3b39765d8782.jpg)  
Fig.8Region of Interest   
图9基于决策树构造的印象空间模型

实验结果表明，选择随机森立作为基模型，架构的印象空间模型效果最优。究其原因，随机森林属性一种集成算法其核心是组合基分类器得到一个强分类器，且随机森林是由多棵决策树通过节点分裂筛选特征，在工作过程中具有一定的随机性，这种随机性表现在随机采样及特征随机选取，筛选策略的精准和随机森林的随机性结合达到最优实验效果。

进一步优化印象空间模型，验证不同的分类基模型通过多模型架构能否产生更好的效果，结果如图10所示。

![](images/0a0bf9bfdeff9645601ade88f37a5663f339ccaad93ca2f59e2d7cb470ed4305.jpg)  
Fig.9Impression Space Model Based on Decision Tree   
图10基于多模型构造的印象空间模型  
Fig.10Impression space model based on Multi-model

实验结果表明，每次选择最优分类模型会在一定程度上增加小幅度的实验效果，但是使用不同的模型训练不同的数据子集的训练时间是各个模型训练时间之和，这种选择多模型构建的印象空间模型增大了工作量，在分类准确率方面多模型构建的印象空间模型以随机森林得到的结果已达到一定意义上的最优。综合上述实验结果多模型构建的印象空间模型尽管分类准确率方面可带来一定的提高，但却大幅度增大了工作时间，而且在数据处理过程中占用较大资源，本文选择决策树分枝情况结合随机森林作为基模型构建印象空间模型。

# 7.4.3模型比较

目前互联网广告效果指标多以点击率与转化率作为评价指标。以点击率为互联网广告效果评价指标的点击模型主要有局部马尔可夫链模型(partially observable Markov，POM)模型、二项式(polynomial2，PLOY2)模型、因式分解机(factorizationmachine，FM)模型、域因式分解机(fieldfactorizationmachine，FFM)模型。选择同样数据集以印象空间为互联网广告效果指标的印象空间模型对比点击模型得到评价效果准确率和稳定性如表7所示。

表7模型对比  

<html><body><table><tr><td colspan="3">Table 7 Model comparison</td><td></td></tr><tr><td>模型</td><td>准确率</td><td>召回率的MAE</td><td>召回率的MSE</td></tr><tr><td>POM</td><td>0.872</td><td>0.031</td><td>0.049</td></tr><tr><td>PLOY2</td><td>0.866</td><td>0.042</td><td>0.053</td></tr><tr><td>FM</td><td>0.865</td><td>0.071</td><td>0.052</td></tr><tr><td>FFM</td><td>0.878</td><td>0.057</td><td>0.057</td></tr><tr><td>印象空间模型</td><td>0.924</td><td>0.028</td><td>0.048</td></tr></table></body></html>

分析结果可知：a)可能人们对于互联网广告越来越了解，这也促使点击行为难以反映用户真实意图，会出现无意识点击以及点击行为影响实验结果；b)可能存在大量的用户对互联网广告产生了不错的印象，却没有付诸实践行动。综上所述，点击率难以反映出真实的互联网效果，促使科研人员寻找其他指标衡量互联网广告效果。

# 8 结束语

本文旨在以印象空间作为互联网效果评测标准，研究分析不同的用户类型对于互联网信息的处理方式和偏好行为构建印象空间模型衡量互联网广告效果。

在用户类型划分过程中，为了最大化保留用户属性提出利用不同的概率分布规律划分组合属性，将数学思想与复杂的算法理论结合以解决实际问题；提出了注视时效和页面布局特点划定用户兴趣区域，在后续的工作中将通过attention模型结合用户行为方式重新划分网页界面；利用多因素多模态构建印象空间模型，可以行之有效的测评互联网广告效果，对于商业利益最大化，增强用户体验等有重要作用。

# 参考文献：

[1]Craswell N, Zoeter O, Taylor M,et al.An experimental comparison of click position-bias models [C]//Proc of the lst International Conference on Web SearchandData Mining.New York:ACMPress,20o8:87-94.   
[2]Wang Chao,Liu Yiqun,Zhang Meng,et al.Incorporating vertical results into search click models [C]/Proc of the 36th International ACM SIGIR Conference on Research and Development in Information Retrieval.New York:ACMPress,2013:503-512.   
[3]Xu Wanghong,Manavoglu E,Gantu-Paze E.Temporal click model for sponsored search [C]//Proc of the 3rd ACM International Conference on Web Search and Data Mining.New York:ACMPress,2010:211-220.   
[4]Shan Lili,Lin Lei, Sun Chengjie,etal.Predicting ad click-through rates via feature based fully coupled interaction tensor factorization [J]. Electronic Commerce Research Applications,2016,16 (C): 30-42.   
[5]Wang Chao,Liu Yiqun,Wang Meng,et al.Inferring search behaviors using partially observable Markov model [C]// Proc of the 3rd ACM International Conference on Web Search and Data Mining. New York: ACM Press,2010:211-220.   
[6]Qu Yanru,Cai Han,Ren Kan,et al.Product-based neural networks for user response prediction [Cl/Proc of IEEE International Conference on Data Mining. Piscataway,NJ: IEEE Press,2017: 1149-1154.   
[7]Shan Ying,Hoens T.Ryan,Jiao Jian,et al.Deep crossing:Web-scale modeling without manually crafted combinatorial features [C]//Proc of the 22nd ACM SIGGKDD International Conference on Knowledge Discovery and Data Ming.New York: ACM Press,2016: 255-262.   
[8]赵慧芳，张岩．熵权双基点法在网络广告效果评估中的应用[J].统 计与信息论坛，2006,21(4):84-86.(Zhao Huifang，Zhang Yan. Comparative research on two kinds of data mining technologies in forecasting the customer degree of satisfaction [J].Statistics and Information Form,2006,21(4): 84-86.)   
[9]邓文峰，周朝民．浅析网络广告效果评价方法[J].上海管理科学, 2005，27(4):13-15．(Deng Wenfeng，Zhou Chaomin．On the measurements of online advertisement effectiveness [J]. Shanghai Management Science,2005,27(4):13-15.)   
[10]吕鸿江，程明．基于消费者心理视角的网络广告效果评价[J].南京 农业大学学报:社会科学版,2006,6(4):46-50.(Lyu Hongming,Chen Ming.A study of online advertising effect appraisement from a custom psychology perspective [J]. Journal of Nanjing Agricultural University (Social Sciences Edition),2006,6(4):46-50.)   
[11]陈磊，刘亦群，茹立云，等.基于用户日志挖掘的所所引起广告分析 [J].中文信息学报,2008,22(6):92-97.(Chen Lei,Liu Yiqun,Ru Liyun,et al. Performance evaluation of online sponsored search based on user log analysis [J]. Journal of Chinese Information Processing, 2008,22(6): 92-97.)   
[12]胡晓红，王红，任衍具．基于眼动技术的互联网广告效果研究[J]. 计算机应用研究,2018,35(5):1345-1349.(Hu Xiaohong,Wang Hong, Ren Yanju,et al. Research on network advertisement effect based on eye movement technology [J].Application Research of Computers, 2008,35 (5): 1345-1349.)   
[13] Wedel M,Pieters R.Eye fixations on advertisements and memory for brands:a model and findings[J].Marketing Science,20oo,19(4): 297-312.   
[14] Dreze X,HussherrF X, Internet advertising: Is anybody watching?[J]. Journal of Interactive Marketing,2003,17(4): 8-23.   
[l5]WangC,Liu Y Q,Wang M,et al. Incorporating nonsequential behavior into click models [C]// Proc of the 38th International ACM SIGIR Conference Research and Development in Information Retrieval, New York: ACM Press,2015: 211-220.   
[16]RenshawJA,Finlay JE,TyfaD,et al.Understanding visual influence ingraph design through temporal and spatial eye movement characteristics [J]. Interacting with Computers,2004,16(3):557-578.   
[17] Shen Chengyao,Huang Xun,Zhao Qi.Predicting eye fixations on webpage with an ensemble of early featuresand high level representations from deep network [J]. IEEE Trans on Multimedia, 2015,17(1): 2084-2093.   
[18] Xu Ying,Xu Suting,Liu Xingtong,et al.Analysis on the validity of eye movement data during video viewing [C]//Proc of International Congress on image and Signal Processing, Biomedical Engineering and Informatics.2017.   
[19] Chen Ye,Liu Yiqun,Zhou Ke,et al. Does vertical bring more satisfaction:predicting search satisfaction in a heterogeneous environment [C]// Proc of the 24th ACM International Conference on Information and Knowledge Management. New York: ACM Press,2015: 1581-1590.   
[20] Liu Yiqun,Chen Ye,Tang Jinhui,et al.Different Users,Different Opinions:Predicting Search Satisfaction with Mouse Movement Information [C]//Proc of the 38th ACM SIGIR International Conference on Research and Development in Information Retrieval.New York: ACM Press,2015: 493-502.   
[21] Chen Xiaojun，Ye Yunming,Xu Xiaofei,et al.A feature group weighting method for subspace clustering of high dimensional data [J]. Pattern Recognition,2014,45(1): 434-446.   
[22] Clifton C,Ferreira F,Henderson JM,et al.Eye movements in reading and information processing: Keith Rayners4O year legacy[J]. Journal of Memory Language,2016,86:1-19.   
[23] Tibshirani R,Walther G,Hastie T,et al.Estimating the number of clusters in a data set via the graph statistic [J]. Journal of the Royal Statistical Society,2001,63(2): 411-423.   
[24] Deng Xinyang,Liu Qi,Deng Yong,et al. An improved method to construct basic probability assignment based on the confusion matrix for classification problem [J]． Information Sciences,2016,340: 250-261.   
[25] Chen Chen,Hou Chunyan，Xiao Jiakun,et al.Purchase Behavior Prediction in E-Commerce with Factorization Machines [J]. IEICE Trans on Information and Systems,2016,99 (1): 270-274.