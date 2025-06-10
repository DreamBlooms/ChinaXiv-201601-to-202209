# 基于综合信任的社会化混合推荐算法

杨丰瑞1,²，吴晓浩1，万程峰1

(1.重庆邮电大学 通信新技术应用研究中心，重庆 400065;2.重庆重邮信科(集团)股份有限公司，重庆 401121)

摘要：推荐系统是处理信息过载问题的重要手段。现有的基于信任网络推荐算法没有充分挖掘用户信任关系信息，影响推荐效果。提出了综合评估信任（CETrust）的模型，该模型综合考虑了用户间的直接信任和间接信任等因素。结合推荐项目的特征属性信息，集成到概率矩阵的因式分解模型中推荐。实验表明，新提出的推荐算法(H-CETrust)推荐精度高于现有推荐算法的推荐精度。

关键词：推荐系统；信任网络；信任评估；项目特征；概率矩阵 中图分类号：TP39 doi:10.3969/j.issn.1001-3695.2018.03.0372

# Social hybrid recommendation algorithm combined with comprehensive trust

Yang Fengrui1,2, Wu Xiaohaol,Wan Chengfengl (1.ResearchCenterofNewTelecommunicationTechnologyApplications,Chongqing UniversityofPosts &Telecommunications, Chongqing 4065,China;2.Chongqing Chongyou Information Technology(Group)Co.Ltd,Chongqing 40111,China)

Abstract:Therecommendationsystem is animportant method todeal with theproblemofinformation overload.The existing trust networkrecommendationalgorithmdoesnot fully mine theusertrustrelationshipinformationandaffects the recommendationeect.Thispaperproposesamodelcalled CETrust,whichtakes intoaccount thedirecttrustand indirecttrust among usersand integrates the atribute informationof therecommended project into the factorizationofprobabilitymatrix. Experiments showthattherecommendation accuracyof the newly proposedrecommendation algorithm(H-CETrust)is higher than that of the current recommendation algorithm.

Key Words: recommendation system;trust network; trust assessment; project characteristics; probability matrix

# 0 引言

在大数据时代，数据呈爆炸式增长，用户需要耗费长时间才能找到有效的信息，推荐系统是解决信息过载的重要手段，协同过滤算法具有高效性和便捷性，因而在推荐系统中应用十分广泛。协同过滤算法是找到与目标用户兴趣相似的用户，利用这些用户对物品的评分推测目标用户对物品的感兴趣程度。其推荐准确率受限于数据稀疏性问题和冷启动问题[1]。

随着社交网络的发展，研究人员将信任关系引入到推荐系统中，利用用户之间的社会关系来提供推荐。可以完善协同过滤推荐算法面临的数据稀疏和冷启动问题。Ma等人[2.3]利用矩阵分解技术整合用户之间的信任关系来提高推荐效果。

本文的贡献是：研究将全面的信任评估机制引入到协同过滤推荐算法中。该算法通过构建信任传输模型来完善用户间的信任关系，结合概率矩阵分解模型进行推荐，同时引入推荐项目的特征属性优化推荐结果。最后，把测试数据应用到推荐系统上，分析推荐算法的推荐精度。

# 1 相关工作

社交网络迅速发展，研究者对用户间的信任度的计算提出了各自算法。如Golbeck 提出了TidalTrust 算法[4]，该算法在信任网络中执行改进的广度优先搜索算法来计算预测评级，通过大多偏好目标用户的信任路线来搜索所有相关用户的评级，但是这种方法难以计算非相邻用户之间的信任值。Jamali等人[5]提出了基于信任的个性化推荐算法SociaIMF，该算法通过将矩阵分解与信任传播机制相结合来推荐。他们的实验结果表明SocialMF算法具有很高的推荐精度。信任传播机制已经成为基于信任的社交网络中的重要手段。Li等人[提出一种基于信任传播和奇异值分解的社会推荐方法。该实验结果表明有效并高效提高了推荐质量。郭磊等人[7提出了一种敏感的强化信任关系的社会推荐算法，这种强化可以进一步提高推荐算法的精度。秦继伟等人[提出了一种融合了用户信任和情感偏好的协同过滤推荐算法。使用不同的通用评级资源值，该算法利用用户之间的相似性评分或信任值来弥补推荐方法的缺点。邹本友等人[提出了一种个性化的推荐方法，将张量分解和用户关系集成在一个社交网络环境中。该算法采用不同的推荐主题，选择不同朋友的信任度，可以应用于更新速度更快的个性化推荐场景。胡云等人[10]提出结合评分和信任度关系的推荐算法，利用朋友间的信任矩阵对用户间的特征向量进行修正，解决用户特征向量精准构建和信任传递问题。实验结果表明较传统的社会化网络推荐算法在性能上有明显提高。胡惠成等人[1提出一种融合隐式信任关系的推荐算法，解决了显式数据稀疏性问题，有效提高了推荐结果的准确度。Zhang等人[12]提出了一种融合信任关系和时间序列的个性化推荐算法，该算法综合考虑了用户与时间因素之间的信任关系，从而保证了推荐的及时性。在类似的研究中，李慧等人[13]提出了一种整合了各种上下文信息的社交网络推荐算法。该算法基于使用用户的地理位置和时间信息，深入挖掘用户间潜在的社会关系，有效解决了推荐精度问题。

上述社会化推荐算法虽然取得了不错的推荐效果，大多是从用户的角度出发，忽略了项目间的关联关系。此外，使用直接信任关系时忽略间接信任关系，导致缺乏信任信息和

无法解决冷启动问题。本文提出一种综合评估信任（comprehensive evaluation trust,CETrust）的推荐模式。该模型基于综合考虑了概率矩阵分解模型、直接和间接信任关系、融合项目关联属性等因素，提出一种混合推荐算法（hybridrecommendation algorithm based on comprehensive evaluationtrustanditem，H-CETrust）。在Epinions数据集上的实验结果表明，本文提出的推荐算法较传统的协同过滤算法具有更好的推荐精度。

# 2 信任机制

# 2.1信任网络

本文使用信任网络来表达用户之间的信任关系和社交网络系统推荐的环境。信任网络可以分为两值信任网络和通用信任网络。图1给出了一个双值信任网络图。图中有向边表示信任关系，信任度为1。图2显示了一个通用的信任网络图。在该图中节点表示用户，并且有向边表示用户之间的信任关系。

![](images/b102b98dc50f6f634ba757db4c5f5bbd08f2c046dc0735fd5c9b8c05a51f1204.jpg)  
图1双值信任网络图

信任网络可以定义为一个图结构。 $G { = } { < } U , T U { > }$ ，其中： $U =$ $\{ u _ { I } , \ u _ { 2 } , \ \dots , \ u _ { n } \}$ 代表一组用户； $T U = \{ \textit { \textbf { ( u , \nu ) , u } } \in U , \ \nu \in T u \}$ 表示 $G$ 中的一组关系。 $G$ 中的每个节点对应于 $u ^ { \scriptscriptstyle * }$ $\boldsymbol { \mathscr { k } } \in { \cal I } , { \cal 2 }$ ，，$n$ ）表示的用户， $G$ 中的每个边对应于信任关系。 $t _ { u \nu }$ 表示用户 $\mathbf { \Omega } _ { u }$ 对用户 $\mathbf { v }$ 的直接信任度， $t _ { u \nu } \in [ 0 , 1 ]$ ，较大的值表示信任度较高。另外，用户 $\mathrm { ~  ~ u ~ }$ 直接信任的用户集合表示为 $T u = \{ \nu \in U$ ， $t _ { u \nu } \in$ $[ 0 , I ] ; , \ I = \{ i _ { I } , \ i _ { 2 } , \ \dots , \ i _ { m } \}$ 是一组项目， $R _ { u i }$ 代表用户 $u$ 对项目 $i$ 的分数。在推荐任务中，给定用户 $u \in U$ 和项目 $i \in I$ ，未知分数 $\hat { \textmd R } _ { u i }$ 是用户 $u$ 对项目 $i$ 的预测评分。

![](images/f61f60e0da35a69aed3ae321ed5631ef189aa5ef92e2b5195cb336e5cfb4c910.jpg)  
图2通用信任网络图

# 2.2信任传播计算

在基于信任的社交网络中，通过选择目标用户与邻居之间的信任关系（0,1）内的实数来衡量信任度。在基于信任的推荐模型中，用户之间的信任关系是指直接信任，而在推荐过程中间接信任关系的影响没有得到体现。如图3所示，其中用户 $u$ 对用户 $\nu$ 的直接信任值为0.7，用户 $\mathbf { \Lambda } _ { \nu }$ 对用户 $w$ 的直接信任值为0.5。根据信任的传递性，可以通过计算获得用户 $u$ 对间接邻居用户 $w$ 的间接信任值 $t _ { u w }$ 。计算信任传播的常用方法如下：

$$
\mathbf { t } _ { u w } = t _ { u \nu } \cdot t _ { \nu w }
$$

$$
\mathbf { t } _ { u w } = \mathbf { m i n } ( t _ { u \nu } , t _ { v w } )
$$

$$
{ \bf t } _ { \mathrm { u w } } = \mathrm { m a x } ( t _ { u \nu } + t _ { \nu w } - 1 , 0 )
$$

$$
\mathbf { I } _ { u w } = \{ \operatorname* { m i n } ( t _ { u \nu } , t _ { v w } ) \ ~ , ~ \operatorname* { m a x } ( t _ { u \nu } , t _ { v w } ) = 1
$$

式 $( 1 ) \sim ( 4 )$ 分别计算 $t _ { u w }$ 得 $0 . 4 2 、 ~ 0 . 6 、 ~ 0 . 3 、 ~ 0 _ { \circ }$ ，各种信任传播方法计算的间接信任度可能不同。

![](images/1fb7677971aebf5cf5d6013f73a3872885cda6d7261da392a9764aa56f7ae080.jpg)  
图3信任度传播计算图

# 3 H-CETrust推荐算法

全球信息很难在现有的个性化推荐算法中计算。推荐准确度、实时性能和冷启动问题继续存在。本文使用社交网络中的信任关系来全面考虑用户与用户项目评分之间的信任值。应用矩阵分解来分解用户之间的信任关系网络，并进一步研究隐藏在信任关系背后的用户特征。介绍了基于信任关系的新推荐机制，有效提高用户信任模型的可扩展性。融合推荐项目的关联性，优化CETrust模型。Epinions公开数据集上的实验结果表明，本文提出的H-CETrust推荐算法保证了复杂社交网络中推荐的准确性，具有很强的可扩展性。

# 3.1CETrust模型的基本概念

购买商品时，用户主要受用户对商品的需求程度以及用户信任的朋友的程度两个因素的影响。在现有的社交网络中，相邻用户之间的直接信任（显示的信任）关系容易获得，直接用户通信的机会很少。不能直接获取非相邻用户间的信任关系（隐式信任关系)，但这种间接信任关系可以提高推荐算法的精度，有助于解决冷启动问题。间接信任可以从现有的信任关系和信任传递机制中获得。

Ma等人[2.3]提出的RSTE模型，考虑直接用户信任关系，但不考虑间接用户信任关系。本文改进RSTE 模型，并基于对用户之间直接信任关系的综合分析，使用信任传输机制来确定间接用户信任关系。该机制可以通过计算间接信任关系来识别现有用户所信任的其他用户。考虑用户偏好的相似性，计算用户间的相似度，综合考虑用户间的信任关系。

# 3.2CETrust模型中的信任计算

在社交网络中，间接信任能通过计算获得。傅敏[14]提出递归计算，通过分析信任的传输和聚合特征来计算信任值。

$$
\mathbf { t } _ { a , u } = \frac { \displaystyle \sum _ { \nu \in V ^ { T } } t _ { a , u } . t _ { \nu , u } } { \displaystyle \sum _ { \nu \in V ^ { T } } t _ { a , \nu } }
$$

其中： $\textit { a , } u$ 和 $\mathbf { \Lambda } _ { \nu }$ 表示用户； $\mathbf { \Delta } t _ { a , \mathrm { ~ } u }$ 表示目标用户 $a$ 与用户 $\mathbf { \Phi } _ { u }$ 之间的信任值； $\nu$ 是从 $\boldsymbol { a }$ 到 $u$ 的最短路径上的节点；而 $V ^ { T }$ 是一组用户，这些用户应该位于从 $a$ 到 $u$ 的最短路径上，并且他们的信任值应该大于指定的阈值。用户 $a$ 与 $\boldsymbol { u }$ 之间的相似度可以通过计算Pearson相关系数来获得。

$$
\sin ( a , u ) = \frac { \displaystyle \sum _ { i \in I _ { u , a } } ( R _ { a , i } - \overline { { R } } _ { a } ) ( R _ { u , i } - \overline { { R } } _ { u } ) } { \sqrt { \displaystyle \sum _ { i \in I _ { u , a } } ( R _ { a , i } - \overline { { R } } _ { a } ) ^ { 2 } } \sqrt { \displaystyle \sum _ { i \in I _ { u , a } } ( R _ { u , i } - \overline { { R } } _ { u } ) ^ { 2 } } }
$$

其中：sim $( a , ~ u )$ 表示用户 $\mathbf { \Delta } _ { a }$ 和 $u$ 之间的相似度。在获得用户a与 $\mathrm { ~  ~ u ~ }$ 之间的信任值和相似度之后，使用加权平均来组合这两个特征。具有高相似度和信任值的推荐邻居增加了信任。新的信任值 ${ T _ { a u } } ^ { , }$ 用户 $\mathbf { \Delta } _ { a }$ 与 $\mathbf { \Omega } _ { u }$ 之间的关系可以通过计算式（7）来获得。

$$
\textrm { T } _ { a u } ^ { ' } = \frac { 2 \sin ( a , u ) \cdot t _ { a , u } } { s i m ( a , u ) + t _ { a , u } }
$$

# 3.3CETrust概率图模型

图4显示了CETrust 概率图模型。CETrust使用概率预测评分，首先，执行综合信任评估算法获取一个新的信任矩阵 $T ^ { \prime }$ ，如图4的右边框所示。与矩阵 $T$ 不同，矩阵 $T$ 不仅包括直接信任关系，还包括间接信任关系。通过矩阵模型将所有信任关系整合到推荐算法中，使用梯度下降法来优化目标函数。T（u)是用户 $u$ 信任的一组用户， $\mid T \left( u \right) \mid$ 是用户 $\boldsymbol { u }$ 所信任的用户数量。这里， $U \in { \cal R } ^ { d \times N }$ 和 $V \in R ^ { d \times M }$ 是用户和项目的 $d$ 维潜在特征矩阵。如果用户和项目的特征矩阵符合零均值的球形高斯先验分布，则该项目的用户偏好程度是可用概率表示。在这种情况下，组合潜在特征矩阵 $U$ 和 $V$ 的后验概率分布是

$$
\begin{array} { r l } & { \mathrm { p } ( U , V \big \vert R , T ^ { \prime } , \sigma _ { R } ^ { 2 } , \sigma _ { U } ^ { 2 } , \sigma _ { V } ^ { 2 } ) } \\ & { = \displaystyle \prod _ { u = 1 } ^ { N } \prod _ { i = 1 } ^ { M } \Biggl [ N ( R _ { u i } \Biggl \vert g ( \sum _ { k \in T ( u ) } T _ { u } ^ { \prime } U _ { k } ^ { T } V _ { i } ) , \sigma _ { R } ^ { 2 } ) \Biggr ] ^ { I _ { u } ^ { R } } } \\ & { \times \displaystyle \prod _ { u = 1 } ^ { N } N ( U _ { u } \vert 0 , \sigma _ { U } ^ { 2 } I ) \times \prod _ { i = 1 } ^ { M } N ( V _ { i } \vert 0 , \sigma _ { v } ^ { 2 } I ) } \end{array}
$$

其中： $N ( x | \mu , \sigma ^ { 2 } )$ 是密度函数，表示 $x$ 满足均值 $\mu$ 和方差 $\sigma ^ { 2 }$ 的高斯分布；函数 $g ( x ) = 1 / \left( 1 + \exp ( - x ) \right)$ 表示逻辑功能。

逻辑函数用于确保 $\sum _ { \mathbf { k } \in T ( u ) } T _ { u k } ^ { ' } U _ { k } ^ { T } V _ { i }$ 的值在[0,1]内。 $I _ { u i } ^ { R }$ 是一个（204指示函数，如果用户 $u$ 对项目 $i$ 进行评分，则为1，否则为0。$T _ { u k } ^ { ' }$ 表示用户 $u$ 对用户 $k$ 的信任值，可以用（5）式获得。

![](images/2c9855202cd32f82575799a4c8a1c8e8049688914f22c5042613c2bf89174a46.jpg)  
图4CETrust 概率图模型

# 3.4 优化CETrust模型

CETrust 模型推荐方法更加精确从用户的角度推荐，没有考虑推荐项目的关联特性。而推荐项目之间的联系也是用户决策的重要因素，为了把项目之间的内容特性考虑进去，在CETrust方法的基础上对算法进行扩展。

假设 $X _ { i } = \{ F I , F 2 , \ldots F { _ { j \ldots F } } { _ { n } } \}$ 表示项目的特征属性集合。用一些关键字或标签来描述项目内容，其中 $F _ { j }$ 表示 $X _ { i }$ 的第 $j$ 个特征。如果 $F _ { j }$ 值等于1，则表示 $X _ { i }$ 具有该特征，否则表示 $X _ { i }$ 不具备该特征。因此，所有项目都可以形成关于项目关键字的二维矩阵，如表1所示。

表1项目一特征矩阵  

<html><body><table><tr><td></td><td>特征F1</td><td>特征F2</td><td></td><td>特征Fn</td></tr><tr><td>项目x1</td><td>1</td><td>0</td><td></td><td>0</td></tr><tr><td>项目x2</td><td>0</td><td>1</td><td>0</td><td>0</td></tr><tr><td>…</td><td>…</td><td>：</td><td></td><td>…</td></tr><tr><td>项目xn</td><td>0</td><td>0</td><td>…</td><td>1</td></tr></table></body></html>

项目间的关联度通过式（9）计算得到。

$$
\mathbf { C } _ { x _ { \mathrm { i } } , x _ { \mathrm { k } } } = \sum _ { j = 1 } ^ { k } ( F _ { x _ { \mathrm { i } } , j } \times F _ { x _ { \mathrm { k } } , j } ) / k
$$

其中： $\mathrm { F _ { x i , j } }$ 表示项目 $\mathbf { X } \mathrm { i }$ 的第 $\mathrm { j }$ 个特征属性，若有这个特性，那么$\mathrm { F _ { x ^ { i } , j } = 1 }$ ，否则就为0。 $\mathbf { C } _ { \mathrm { x } ^ { \mathrm { i } } , \mathrm { x k } }$ 的大小代表了两个项目的关联强度。其中, ${ \bf C } _ { \mathrm { x ^ { i } , x ^ { k } } } \in [ 0 , 1 ]$ ${ \mathrm { C } } { = } \{ \mathrm { C } _ { \mathrm { X } ^ { \mathrm { i } } , \mathrm { X } ^ { \mathrm { k } } } \}$ 表示一个 $\langle \mathbf { M } \times \mathbf { M } \rangle$ 项目关联矩阵。将特征矩阵C分解可以得到低维潜在特征关系矩阵。推荐项目V矩阵分解后的低维特征向量 $\mathrm { { V } _ { i \setminus \partial } \ \mathrm { { V } _ { j \cdot } } }$ 。项目间的关联关系矩阵C的后验概率分布可以表示为

$$
\mathrm { P } ( C \big | V , \sigma _ { c } ^ { 2 } ) = \prod _ { \mathrm { i = 1 } } ^ { M } \prod _ { j = 1 } ^ { M } N \Big [ C _ { \mathrm { X } _ { \mathrm { i } } , X _ { \mathrm { j } } } \big | g ( V _ { i } ^ { T } V _ { j } ) , \sigma _ { c } ^ { 2 } \Big ] ^ { I _ { i j } ^ { C } }
$$

其中： $I _ { i j } ^ { C }$ 指数函数表示推荐项目 $X _ { i }$ 和 $X _ { j }$ 的特征关联关系，如果 $C _ { x ^ { i } , x ^ { j } }$ 不等于0,指数函数的值为1，否则为0。为了优化CETrust模型，提高推荐精度，利用共享的潜在特征空间将推荐项目进行特征关联、用户间的社会信任和评分信息结合在一起，进一步提高推荐的精度。所用的概率模型如图5所示。

![](images/bb1c16b481849d11f07b5b8bdc4df1dfec90a8d291471fe86ce4fcd26bf4f67c.jpg)  
图5H-CETrust 概率模型

$U , V$ 的对数联合后验概率进一步表示为

$$
\begin{array} { l } { { \displaystyle \operatorname* { l i p } _ { p ^ { \prime } \in \mathcal { N } _ { k ^ { \prime } } } | R _ { k ^ { \prime } } , C _ { \sigma _ { k ^ { \prime } } } \sigma _ { \nu , \sigma _ { k ^ { \prime } } } ^ { 2 } \sigma _ { \nu ^ { \prime } } ^ { 2 } } } \\ { { \displaystyle = - \frac { 1 } { 2 \sigma _ { k ^ { \prime } \sigma _ { k ^ { \prime } } } ^ { 2 } } \sum _ { i = 1 } ^ { M } \frac { I _ { k ^ { \prime } } } { i \sigma _ { k \sigma _ { k ^ { \prime } } } } E _ { i } ( R _ { k \sigma } - g _ { i } \sum _ { k ^ { \prime } \sigma _ { k } } T _ { \alpha } ^ { \prime } V _ { k ^ { \prime } } ^ { \prime } V _ { k ^ { \prime } } ^ { \prime } ) ^ { 2 } } } \\ { { \displaystyle - \frac { 1 } { 2 \sigma _ { \mathrm { c } ^ { \prime } } ^ { 2 } } \frac { \underset { k ^ { \prime } } { \sum } } { i \sigma _ { k \sigma _ { k } } ^ { 2 } } E _ { i } ^ { \prime } ( C _ { _ { \lambda _ { k } \sigma _ { k ^ { \prime } } } } - g _ { i } \langle Y _ { k ^ { \prime } } ^ { \prime } V _ { k } \rangle ) ^ { 2 } } } \\ { { \displaystyle - \frac { 1 } { 2 \sigma _ { \sigma _ { k ^ { \prime } } } ^ { 2 } } \sum _ { i = 1 } ^ { M } U _ { \alpha } ^ { \prime } - \frac { 1 } { 2 \sigma _ { \sigma _ { k ^ { \prime } } } ^ { 2 } } \frac { \underset { k ^ { \prime } } { \sum } } { i \sigma _ { k \sigma _ { k } } ^ { 2 } } V _ { i } ^ { \prime } } } \\  { \displaystyle - \frac { 1 } { 2 } ( \sum _ { i = 1 } ^ { M } \frac { I _ { k ^ { \prime } } ^ { \prime } } { i \sigma _ { k ^ { \prime } } ^ { 2 } } ) { \ln \sigma _ { k } ^ { 2 } } \frac { - 1 } { 2 } \frac { \underset { k ^ { \prime } } { \sum } } { i \sigma _ { k \sigma _ { k } } ^ { 2 } } { \ln ( 1 - i \mathrm { d } \sigma _ { k ^ { \prime } } ^ { 2 } ) + 1 } \sigma _ { \mathrm { c } ^ { \prime } } ^ { 2 } } \\ { { \displaystyle - \frac { 1 } { 2 } ( N \times d \mathrm { s } \ln \sigma _ { \nu } ^ { 2 } + M \mathrm { s } \mathscr { A } \mathrm { s } \mathscr { A } \sigma _ { \nu } ^ { 2 } ) + L } } \end{array}
$$

其中： $L$ 是不依赖于任何参数的常数； $d$ 是潜在特征矩阵的对应维度。最大化式（11）后的后验概率等于最小化的以下带正则项的误差平方和函数：

$$
\begin{array} { l } { { \displaystyle { \mathbb E } ( R , T , C , U , V ) } \ ~ } \\ { { \displaystyle = \frac 1 2 \sum _ { u = 1 } ^ { N } \sum _ { i = 1 } ^ { M } I _ { u i } ^ { R } ( R _ { u i } - g ( \sum _ { k \in T ( u ) } T _ { u k } ^ { ' } U _ { k } ^ { T } V _ { i } ) ) } ^ { 2 } }  \\ { { \displaystyle ~ + \frac { \lambda _ { C } } { 2 } \sum _ { i = 1 } ^ { M } \sum _ { j = 1 } ^ { M } I _ { x , { \scriptstyle i } j } ^ { C } ( C - g ( V _ { i } ^ { T } V _ { j } ) ) ^ { 2 } } } \\ { { \displaystyle ~ + \frac { \lambda _ { \mathrm { U } } } { 2 } \| U \| _ { F } ^ { 2 } + \frac { \lambda _ { V } } { 2 } \| V \| _ { F } ^ { 2 } } } \end{array}
$$

其中：

$$
\lambda _ { c } = \frac { \sigma _ { \mathrm { { R } } } ^ { 2 } } { \sigma _ { c } ^ { 2 } } , \lambda _ { \mathrm { U } } = \frac { \sigma _ { R } ^ { 2 } } { \sigma _ { U } ^ { 2 } } , \lambda _ { \scriptscriptstyle V } = \frac { \sigma _ { \mathrm { { R } } } ^ { 2 } } { \sigma _ { V } ^ { 2 } } , \left\| \cdot \right\| _ { \mathrm { F } } ^ { 2 }
$$

是对应矩阵的 $F$ 范数，范数表示矩阵中所有元素的二次和。  
为减少算法的复杂度，令 ${ \boldsymbol { \lambda } } { \boldsymbol { \mathbf { u } } } { = } { \boldsymbol { \lambda } }$ V。

此外， $\| \mathbf { U } \| _ { F } ^ { 2 } = \Sigma _ { u = 1 } ^ { N } { U _ { \phantom { } u } ^ { T } U _ { \phantom { } u } } , \| V \| _ { F } ^ { 2 } = \Sigma _ { i = 1 } ^ { M } V _ { i } ^ { T } V _ { i }$ 式(12)给出的目标函数的局部最小值可以通过在U和 $\mathrm { \Delta V }$ 中通过梯度下降方法来求得。

$$
\begin{array} { l } { { \displaystyle \frac { \hat { \sigma } \mathrm { E } } { \partial U } = \sum _ { i = 1 } ^ { M } { \cal I } _ { u i } ^ { R } \mathrm { \bf g } ^ { \cdot } ( \sum _ { k \in T ( u ) } T _ { u k } ^ { \prime } U _ { k } ^ { T } V _ { i } ) } \ ~ } \\ { { \displaystyle ~ \times ( g ( \sum _ { k \in T ( u ) } T _ { u k } ^ { \prime } U _ { k } ^ { T } V _ { i } ) - R _ { u i } ) } \ ~ } \\ { { \displaystyle ~ \times \sum _ { k \in T ( u ) } T _ { u k } ^ { \prime } V _ { i } + \lambda _ { U } U _ { u } } } \end{array}
$$

$$
\begin{array} { r l } & { \frac { \widehat { \alpha } \mathrm { E } } { \widehat { \sigma } V } = \displaystyle \sum _ { \mathrm { u } = 1 } ^ { N } I _ { u \mathrm { f } } ^ { R } \mathrm { g } ^ { \cdot } ( \sum _ { k \in T ( u ) } T _ { u k } ^ { \cdot } U _ { k } ^ { T } V _ { i } ) } \\ & { \times ( g ( \displaystyle \sum _ { k \in T ( u ) } T _ { u k } ^ { 1 } U _ { k } ^ { T } V _ { i } ) - R _ { u i } ) \times \displaystyle \sum _ { k \in T ( u ) } T _ { u k } ^ { \cdot } U _ { k } ^ { T } } \\ & { + \lambda _ { c } \displaystyle \sum _ { i = 1 } ^ { M } I _ { x , r _ { i } } ^ { c } g ^ { \cdot } ( V _ { i } ^ { T } V _ { j } ) \times ( g ( V _ { i } ^ { T } V _ { j } ) - C ) \times V _ { j } } \\ & { + \lambda _ { v } V _ { i } } \end{array}
$$

其中： $\begin{array} { r } { \mathbf { g ^ { ' } ( x ) } = \exp ( \mathrm { x } ) / ( 1 + \exp ( - \mathrm { x } ) ) ^ { 2 } } \end{array}$ 是逻辑回归函数 $g \left( x \right)$ 的导数，式(13)和(14)用于获取变量 $L$ 的偏导数。

# 4 实验结果和分析

# 4.1数据集与评价指标

本文使用Epinions[15]作为实验数据集。数据集是测试案例推荐算法的常用手段。Epinions.com 是一个着名的评论网站，成立于1999 年。用户可以在本网站上提交有关产品或电影的评论和意见。本网站的每个成员都维护一个代表用户之间信任关系的信任列表。信任关系的价值为1表示信任，0表示不信任。最初的信任值不需要计算。Epinions网站收集的数据包括对83509个不同项目的51670个用户的评分。

平均绝对误差（meanabsoluteerror,MAE）和均方根误差（rootmean squarederror,RMSE）衡量用户估计特定项目评分的准确性，定义如下：

$$
\begin{array} { r l } & { \mathrm { M A E } { = } \displaystyle \frac { 1 } { \mathrm { N } } \sum _ { i = 1 } ^ { N } \left. R _ { u i } - \hat { R } _ { u i } \right. } \\ & { \mathrm { R M S E } { = } \sqrt \displaystyle \frac { 1 } { \mathrm { N } } ( \sum _ { i = 1 } ^ { N } ( R _ { u i } - \hat { R } _ { u i } ) ^ { 2 } ) } \end{array}
$$

其中： $R _ { u i }$ 表示用户 $\boldsymbol { u }$ 对项目 $i$ 的真实评分； $\hat { \textmd R } _ { u i }$ 表示用户 $\boldsymbol { u }$ 对项目 $i$ 的预测评分； $N$ 表示测试样品的数量。MAE与RMSE值越小，估计准确度越高,推荐效果越好。

# 4.2实验参数影响

本节的实验主要评估参数 $\lambda c$ 和维数 $d$ 对H-CETrust算法的影响。该算法随机分割 Epinions 数据集，其中 $80 \%$ 用于训练集，其余 $20 \%$ 包含测试集。在推荐系统中，c的值为0，表示仅依靠用户的信任关系进行推荐；当无穷大时，表示仅依赖用户偏好的项目的关联关系实施推荐。显然只有联合项目关联关系和用户的综合信任关系才能使推荐效果达到最佳。

首先选择参数值，本实验设置参数 $\lambda u { = } \lambda \nu { = } 0 . I$ ，使算法获得改进的结果并确定进行实验的最佳值。并计算RMSE 和MAE的值。本文使用潜在特征矩阵维数 $d = 2 0$ 来确定参数的 $\lambda c$ 值。实验数据结果如表2所示。

表2实验数据结果（ $d { = } 2 0 .$ ）  

<html><body><table><tr><td colspan="3">测试集比</td><td colspan="6">xc</td></tr><tr><td rowspan="4"></td><td>例%</td><td>0.1</td><td>0.5</td><td>1</td><td>5</td><td>10</td><td>20</td><td>50</td></tr><tr><td>20</td><td>1.16</td><td>1.15</td><td>1.14</td><td>1.13</td><td>1.13</td><td>1.10</td><td>1.16</td></tr><tr><td>50</td><td>1.05</td><td>1.04</td><td>1.03</td><td>1.03</td><td>1.02</td><td>1.01</td><td>1.03</td></tr><tr><td>80</td><td>0.97</td><td>0.96</td><td>0.95</td><td>0.94</td><td>0.93</td><td>0.93</td><td>0.94</td></tr><tr><td rowspan="3">RMSE</td><td>20</td><td>0.95</td><td>0.94</td><td>0.92</td><td>0.91</td><td>0.90</td><td>0.88</td><td>0.89</td></tr><tr><td>50</td><td>0.85</td><td>0.84</td><td>0.82</td><td>0.81</td><td>0.79</td><td>0.76</td><td>0.80</td></tr><tr><td>80</td><td>0.78</td><td>0.76</td><td>0.75</td><td>0.74</td><td>0.74</td><td>0.73</td><td>0.75</td></tr></table></body></html>

由表2的数据可以看出，λc的值对推荐效果有着重要的影响，表面综合考虑用户信任关系和项目关联关系可以提高推荐性能。当λc的值取20时，MAE和RMSE的值相对较低，算法的推荐性能最好。实验数据结果如表3所示。

表3实验数据结果（ $\scriptstyle \lambda \ c = 2 0$ ）  

<html><body><table><tr><td rowspan="2"></td><td rowspan="2">测试集比例%</td><td colspan="3">d</td></tr><tr><td>2</td><td>5</td><td>10</td></tr><tr><td rowspan="3">MAE</td><td>20</td><td>1.15</td><td>1.13</td><td>1.10</td></tr><tr><td>50</td><td>1.04</td><td>1.03</td><td>1.02</td></tr><tr><td>80</td><td>0.96</td><td>0.94</td><td>0.91</td></tr><tr><td rowspan="3">RMSE</td><td>20</td><td>0.82</td><td>0.81</td><td>0.78</td></tr><tr><td>50</td><td>0.72</td><td>0.71</td><td>0.66</td></tr><tr><td>80</td><td>0.65</td><td>0.64</td><td>0.60</td></tr></table></body></html>

由表3可以看出，维数越高推荐效果更好，在2、5、10这三个维度下进行实验，维度为10的效果更好。这是由于用户特征和项目特征矩阵越大则对应分类越细，算法的推荐性能越好。因此最终将参数入c设定为20，维度d取值为10进行对比实验，比较算法性能。

# 4.3算法性能对比实验

为了评估H-CETrust推荐算法的性能，本文使用RMSE 和MAE作为度量标准，并比较以下算法：

下仅使用用户项目评分矩阵来查找建议。

b)PMF[17]是一种基本的概率矩阵分解算法。该算法使用用户项目评级矩阵信息来预测未知评级，并且不考虑用户信任关系。

a）NMF[1使用非负矩阵分解方法在没有其他信息的情况

c)RSTE是基于评级和用户之间信任关系的推荐算法;该算法由Ma等人提出[2]。它将评分信息和用户信任关系整合到基本概率矩阵分解算法中，但不考虑信任传输。

d）TrustSeqMF是基于时间信息和信任关系的推荐算法;该算法由Zhang 等人[12]提出。

H-CETrust是本文中的推荐算法。使用改进RSTE模型，此方法考虑项目与信任传输之间的相似性，是一种基于模型的社交网络推荐方法，采用矩阵分解技术。全面考虑了以下因素：用户之间的直接和间接信任、信任传播和用户相似度、项目间的关联关系。实验选取测试集比重分别为 $20 \%$ 、 $50 \%$ 和 $80 \%$ 。实验室数据结果如表4所示.

表4实验数据结果  

<html><body><table><tr><td rowspan="2">方法</td><td colspan="3">MAE</td><td colspan="3">RMSE</td></tr><tr><td>80%</td><td>50%</td><td>20%</td><td>80%</td><td>50%</td><td>20%</td></tr><tr><td>NMF</td><td>0.832</td><td>0.852</td><td>0.979</td><td>0.632</td><td>0.655</td><td>0.732</td></tr><tr><td>PMF</td><td>0.807</td><td>0.832</td><td>0.933</td><td>0.616</td><td>0.635</td><td>0.702</td></tr><tr><td>RSTE</td><td>0.854</td><td>0.865</td><td>0.942</td><td>0.636</td><td>0.668</td><td>0.743</td></tr><tr><td>TrustMF</td><td>0.807</td><td>0.830</td><td>0.920</td><td>0.615</td><td>0.634</td><td>0.711</td></tr><tr><td>H-CETrust</td><td>0.805</td><td>0.827</td><td>0.902</td><td>0.615</td><td>0.633</td><td>0.696</td></tr></table></body></html>

![](images/2eee2b4c5c4cb72f20a1983834e0d88aafd6ef09cca156e6ee6c68e86cf0e965.jpg)  
图6各算法的MAE值比较

![](images/110196313d7354fdaf61acd22f6c9a4c91c22c1c77dac1b0f2e2f3307becc21e.jpg)  
图7各算法的RMSE 值比较

通过实验结果表明H-CETrust推荐算法由于分别从用户和项目的角度出发，考虑了用户的信任关系和项目间的关联关系。各算法的MAE值比较如图6所示。各算法的RMSE值比较如图7所示。从图6和7中可以直观地看出，在RMSE模型基础上改进后，推荐效果明显提升，本文提出的推荐算法在MAE 和RMSE作为评估指标下要优于实验中的其他推荐算法。

# 5 结束语

本文旨在为推荐系统建立适当的信任模型。为了实现这一目标，本研究调查了所有现有基于信任的协同过滤类型的方法和推荐模型。确定了这些方法和模型的优点和缺点。综合考虑这些因素后，提出了一种新的推荐模式。该方法使用概率矩阵分解模型，直接信任和间接信任，信任传输机制以及用户之间的相似性，同时结合项目关联信息实行推荐。实际数据集的实验结果表明，本文提出的推荐算法较现有基于信任推荐方法更可行。同时解决了新用户和项目的冷启动问题。这项研究的局限性是由于社交网络中的隐私问题，收集的可用信息较少。不信任信息在许多社交网络中提供，因此，未来的研究应探索如何将信任和不信任信息整合到推荐模型中，并进一步研究信任和不信任信息的传播机制和影响。

# 参考文献：

[1]Massa P,AvesaniP.Trust-aware recommender systems [C]//Proceedings of ACMConference on Recommender Systems.New York:ACMPress,2007: 17-24.   
[2]Ma Hao,King I,Lyu M R.Learning to recommend with social trust ensemble [C]//Proc of the 32nd International ACM SIGIR Conference on Research and Development in Information Retrieval.New York:ACMPress, 2009:203-210.   
[3]Ma Hao,Zhou Dengyong,Liu Chao,et al.Recommender systems with social regularization [C//Proc of the 4th ACM International Conference on Web Search and Data mining.New York: ACMPress,2011: 287-296.   
[4]Golbeck JA. Computing and applying trust in web-based social networks [D].[S.l.]:Universityof Maryland College Park,2005.   
[5]Jamali M,Ester M.A matrix factorization technique with trust propagation for recommendation in social networks [C]// Proc of the 4th ACM Conference on Recommender Systems.New York:ACM Press,2010:135- 142.   
[6]Li Weijiang,Qi Jing,Yu Zhengtao,et al.A social recommendation method based on trust propagation and singular value decomposition [J]. Journal of Intelligent & Fuzzy Systems,2017,32(1): 807-816.   
[7]郭磊，马军，陈竹敏．一种信任关系强度敏感的社会化推荐算法[J]. 计算机研究与发展,2013,50(9):1805-1813.(Guo Lei,Ma Jun,Chen Zhumin.A social recommendation algorithm with intensity of trust relationship [J].Journal of Computer Research and Development,2013,50 (9): 1805-1813. )   
[8] 秦继伟，郑庆华，田锋，等．一种融合信任和用户情感偏好的协同过滤 算法[J].软件学报,2013,24(2):61-72.(Qin Jiwei,Zheng Qinghua,Tian Feng,et al.A collaborative filtering algorithm with fusion trust and user emotional preferences [J]. Journal of Software,2013,2013,24 (2): 61-72.)   
[9] 邹本友，李翠平，谭力文，等．基于用户信任和张量分解的社会网络推 荐[J].软件学报,2014,25(12):2852-2864.(Zou Benyou,LiCuiping,Tan Liwen,et al. Social network recommendation based on user trust and tensor decomposition [J].Chinese Journal of Software,2014,25(12):2852-2864.)   
[10]胡云，李慧，施珺.结合评分和信任关系的社会化推荐算法[J].计算 机应用，2017,37(3):791-795.(Hu Yun，LI Hui，Shi Ye.Social recommendation algorithm based on scoring and trust relationship [J]. Journal of Computer Applications,2017,37(3): 791-795.)   
[11]胡惠成，陈平华．一种融合隐式信任关系的推荐算法[J].广东工业大 学学报，2017，34(3):43-48.(Hu Huicheng，Chen Pinghua.A recommendation algorithm based on implicit trust relationship[J]. Journal of Guangdong UnversityofTechnology2017,34 (3):4-48.)   
[12] Zhang Zhijun,Liu Hong.Social recommendation model combining trust propagation and sequential behaviors [J].Applied Intelligence,2015,43 (3): 695-706.   
[13]李慧，马小平，胡云，等．融合上下文信息的社会网络推荐系统[J]. 智能系统学报,2015,10(2):293-300.(LiHui,Ma Xiaoping,Hu Yun,et al. Social network recommendationsystem integrating context information[J]. Journal of Inteligent Systems,2015,10 (2): 293-300.)   
[14]傅敏．基于信任和不信任的协同过滤推荐模型研究[D].秦皇岛：燕山 大学,2012.(Fu Min A research on trust and distrust-based collaborative filtering recommendation model [D]. Qinhuangdao:Yanshan University, 2012.)   
[15]Ma Hao,Yang Haixuan,Lyu MR,et al.SoRec:social recommendation using probabilistic matrix factorization [C]// Proc of the 17th ACM Conference on Information and Knowledge Management. New York: ACM Press,2008:931-940.   
[16] Lee D D,Seung H S.Learning the parts of objects by nonnegative matrix factorization [J]. Nature,1999,401 (6755): 788-791.   
[17]Koren Y，BellR，Volinsky C.Matrix factorization techniqusfor recommender systems [J]. IEEE Computer, 2009,42(8):30-37.