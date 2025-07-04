# 社会网络环境下基于信任传递的推荐模型研究

陈文俊，倪静(上海理工大学 管理学院，上海 200093)

摘要：现有基于信任的推荐算法中没有充分挖掘用户间的信任关系，且缺乏合理的信任关系传递规则，极大地影响了推荐算法的可靠性和准确性。针对上述问题，通过用户评分数据与用户的社会关系建立信任传递模型，提出一种基于信任传递的推荐算法。该算法首先利用评分数据计算信任传递模型中用户的隐式直接信任关系，其次通过求解有序加权平均算子融合多条信任传递链的间接信任关系，最后将计算出的用户信任度与相似度融合为综合相似度进行预测推荐。实验结果证实了所提算法可有效提升系统的推荐质量。

关键词：推荐算法；社会网络；信任传递；有序加权平均算子中图分类号：TP301.6 doi: 10.19734/j.issn.1001-3695.2018.11.0812

Research on recommendation model based on trust transitivity in social network environment

Chen Wenjun, Ni Jing† (Business School,University of Shanghai for Science&Technology,Shanghai 20o093,China)

Abstract: Thecurrent trust-based recommendation algorithms did notfully exploit the trustrelationship betweenusers and it lackedreasonable trust transitivityrules,which greatlyafected thereliabilityandaccuracyof therecommendation algorithm.Aiming at theabove problems,this paper combied userratingdata with the user's social relationshipto builda trusttransitivitymodel,andproposesarecommendationalgorithmbasedontrustransitivity.Firstly,thealgorithmuses the scoredatatocalculatetheimplicitdirecttrustrelationshipoftheusers inthetrustransitivitymodel.Secondly,theindirect trustrelationshipofmultiple trusttransitivitychains issolvedbysolvingtheordered weightedaverage operator.Finally,it converge theuser's trustand similarity intocomprehensive similarity for predictiverecommendation.Theexperimental results show that the proposed algorithm can effectively improve the recommendation quality of the system.

Key words: recommendation algorithm; social network; trust transitivity; ordered weighted average operator

# 0 引言

随着网络应用的发展，网络上的数据资源每天都在爆炸式增长，导致用户需求与大量复杂数据资源之间存在严重矛盾。为了解决这些矛盾，个性化推荐系统被设计产生并应用于从用户的大量信息中提取有用信息[1]。基于社会网络的协同过滤是推荐系统中具有重要意义的一种方法，具有简单性和合理性等优点，成为推荐系统中一个重要的研究方向[2]。其中，将社会网络中用户间信任关系应用到推荐方法中成为近年来研究的热门方向，主要有矩阵分解和链路预测方法。矩阵分解技术如Ma等人[3]提出的SoRec方法是将信任网络结构和用户对项目的评分信息融入概率矩阵因子模型。Salakhutdinov等人[4]从概率的角度描述了矩阵分解问题，提出概率矩阵分解模型PMF。彭鹏等人[5]提出一种结合用户兴趣和信任的矩阵分解方法，挖掘用户潜在的标签关系并将其与评分信息进行矩阵分解。陈婷等人[在此之上结合全局与局部信任与基记忆的协同过滤思想融入矩阵分解模型。基于链路预测的方法如Massa等人[7]从用户的直接反馈中构建了一个信任模型，提出一种利用信任数据进行推荐的算法。O'Donovan等人[8]分别从用户和项目两方面建立信任计算模型，从不同的角度提高推荐精度。在此基础上，Zhang 等人[9]通过将用户节点划分不同区域来计算不同用户之间的信任值。然而这些方法都忽略了社会网络中用户间信任传递的影响。王占和杨丰瑞等人[10,11]考虑了用户间的信任传递作用，引入用户间接信任并以此构建信任网络，获得了较其他算法更优的推荐性能。但是目前的研究并没有一种合理的信任传递规则，在计算方面都只是简单的取最值或求平均值，缺乏真实性和合理性，最终影响推荐结果的可信性和准确性。

针对以上出现的问题，本文提出一种基于社会网络信任传递的推荐算法，通过求解有序加权平均(OWA)算子[12]构建信任传递模型，以此挖掘深层信任关系并为信任的传递提供合理的计算方法。算法最终的目的是引入变量融合用户相似度与信任度信息，将综合相似度作为推荐依据实现算法改进，以期提高推荐质量。

# 1 相关研究

# 1.1信任传递模型

信任传递是指主体A借鉴主体B对主体C的感知信任，形成A与C之间间接的信任关系，描述的是信任在多个主体之间传递的过程[13]。根据构建模型的方法可以将信任传递模型分为数学模型和社会网络模型。信任传递数学模型主要应用概率论、模糊数学等方法构建信任传递模型，如Sun等人[14]针对网络安全问题，构建了基于概率论的信任传递模型来抵御恶意节点，提高网络整体的安全性。田博[15]应用D-S 证据理论提出一种B2C电子商务中的推荐信任评价模型。然而数学模型存在不直观，不能真实反映传递关系的问题。社会网络模型逐渐成为信任传递模型的研究趋势，Kim 等人[16]认为信任能够缓解在线社会网络信任传播中的信息过载问题，提出了最小一最大复合和加权复合相结合的信任度计算方法，并通过实验分析验证了该方法的有效性。Walter等人[17]构建了信任传递社会网络模型应用于推荐系统的研究，模型中主体通过与其他主体之间的信任关系传递关于某事物的信任信息，但是这种方法只是单纯利用信任关系进行推荐，无法有效融入目前的推荐系统中。

总之，目前信任传递的研究具备了一定的理论基础，但是传统的信任传递研究方法由于不能深入刻画人的主观特性，以及计算方法缺乏合理性与真实性无法更好的应用于社会网络的研究及其应用领域。

# 1.2有序加权平均算子

1988 年，Yager 提出了 OWA(ordered weighted averageoperator)算子。自引入以来，它已被应用于许多领域，如神经网络、数据基系统、模糊逻辑控制器和组决策[18]。在不确定的情况下，可以使用OWA算子来实现预期的效用。其目的为集结决策中最大算子与最小算子的方法，其特点为将数据信息进行从大到小排序，然后根据顺序进行排列。其定义如下：

定理1设 $F { \mathrel { : } } R ^ { n } \to R ,$ 若 $F \left( a _ { 1 } , \cdots , a _ { n } \right) = \sum _ { j = 1 } ^ { n } w _ { j } b _ { j }$ ，其中：$w = \left( w _ { 1 } , w _ { 2 } , \cdots , w _ { n } \right) ^ { T }$ 是与 $F$ 相关联的加权向量， $w _ { j } \epsilon [ 0 , 1 ]$ ， $\sum _ { j = 1 } ^ { n } w _ { j } = 1$ $b _ { j }$ 是一组数据 $a _ { j } \epsilon ( i \epsilon N )$ 中第 $j$ 个最大元素，则称函数 $F$ 是 $n$ 维有序加权平均算子。

其中函数 $F$ 需满足以下条件： $F ( \mathbf { x } )$ 必须满足 $F ( 0 ) = 0$ $F ( 1 ) = 1$ ，且 $F ( \mathbf { x } )$ 为单调增函数[19]。这种方法有助于本文计算多信任链下的信任传递，而不是传统的直接根据某一条信任链的信任度决定。

# 2 推荐系统信任传递模型构建流程

为解决信任传递模型研究中出现的问题，本章提出一种综合考虑数学模型和社会网络模型的信任传递模型。首先将参与信任传递的主体和主体间信任传递关系抽象为节点和边；然后根分别建立直接信任度模型和间接信任度模型，其中间接信任度模型包括两部分，分别是单信任链上信任度的计算方式和多信任链上综合信任度的复合计算方式，综合信任度的复合计算是模型的核心部分。其流程如图1所示。

![](images/37a59f93c6eeee205e10e764b9861e652925a04cf4998f5c133619460ad41596.jpg)  
图1信任传递模型构建流程  
Fig.1Trust transitivity model construction flow graph

# 2.1直接信任度计算模型

由于直接表示用户信任度关系的方式带有强烈主观性且大部分网站推荐系统中用户原始数据稀缺，所以关于用户直接信任度的研究都是从用户的评分数据中隐式获取。本文借鉴李熠晨等人[20]的思路，并改进其直接信任度计算方法。对于有过共同评分的用户，即认定其进行过交互，使用用户间的预测误差和用户评分数两部分来计算用户间的直接信任度。改进后的计算方法包括三个步骤，以用户 $^ { u , \nu }$ 为例

首先，根据用户 $\mathbf { \Lambda } _ { \nu }$ 对项目 $i$ 的评分值预测用户 $\mathbf { \Omega } _ { u }$ 的对项目 $i$ 的评分，公式如下：

$$
p _ { u , i } ^ { \nu } = r \overline { { ( u ) } } + \frac { s i m _ { u , \nu } \times \left( r _ { \nu , i } - r \overline { { ( \nu ) } } \right) } { s i m _ { u , \nu } }
$$

其中： $p _ { u , i } ^ { \nu }$ 表示是根据用户 $\mathbf { \sigma } _ { \nu }$ 在项目 $i$ 上的评分计算出对用户$u$ 对项目 $i$ 的预测评分； $s i m _ { u , \nu }$ 为用户 $u , \nu$ 之间的相似度; $r \overline { { ( u ) } }$ 为用户 $u$ 对项目的平均评分； $r \overline { { ( \nu ) } }$ 为 $\nu$ 对项目的平均评分； $r _ { \nu , i }$ 为 $\boldsymbol { \nu }$ 对项目 $i$ 的实际评分。化简后可得

$$
p _ { u , i } ^ { \nu } = r \overline { { ( u ) } } + \left( r _ { \nu , i } - \mathrm { r } \overline { { ( \nu ) } } \right)
$$

其次，由于接下来要计算同一个用户预测评分与实际评分的差值，但是不同数据源计算出的差值存在大于1的情况导致最后计算出的信任度存在负值，这不符合信任概念的定义，也不符合算法的通用性准则，所以本文将预测评分与实际评分的差值利用反正切标准化再计算均方误差。

$$
x _ { i } = \arctan ( \mid p _ { u , i } ^ { \nu } - r _ { u , i } \mid ) \times \frac { 2 } { \pi }
$$

$$
\ M S E _ { u , \nu } = { \frac { \sum _ { i = 1 } ^ { I _ { u , \nu } } \left( x _ { i } \right) ^ { 2 } } { \mid I _ { u , \nu } \mid } }
$$

其中： $x _ { i }$ 为经过反正切标准化的数值； $r _ { u , i }$ 为用户 $\mathbf { \Omega } _ { u }$ 的实际评分； $I _ { u , \nu }$ 为用户 $^ { u , \nu }$ 共同评价过的项目。将正确率记为 $c o r r e c t _ { u , \nu }$ ，则

$$
c o r r e c t _ { u , \nu } = 1 - M S E _ { u , \nu }
$$

最后，为了避免两用户间共同评论的项目过于稀少影响最终结果，先计算用户 $u , \nu$ 的Jaccard系数。Jaccard系数定义为用户 $u$ 与 $\nu$ 交集与并集大小的比值。将正确率与Jaccard系数相乘得出用户 $\boldsymbol { u }$ 对 $\boldsymbol { \nu }$ 的直接信任度 $D t r u s t .$ 0

$$
J a c c a r d _ { u , \nu } = \frac { \left| I _ { u , \nu } \right| } { \left| I _ { u } \right| + \left| I _ { \nu } \right| - \left| I _ { u , \nu } \right| }
$$

$$
D t r u s t _ { u , \nu } = c o r r e c t _ { u , \nu } \times J a c c a r d _ { u , \nu }
$$

# 2.2间接信任度计算模型

为了缓解推荐算法的数据稀疏性，为目标用户匹配更多的邻居用户，需要利用社会网络信任的传递性质，将更多没有直接关联的用户联系起来。其中信任传递计算方法在信任传递模型中起重要作用，并且信任在社会网络中从一个节点到另一个节点的传递时，通常通过以下两种方式。

# 2.2.1单信任链传递

单信任链传递是信任从网络一个节点传递到没有直接关联的另一节点时，只能通过固有的仅有的一条链路才能到达。

例如图2中用户 $\mathbf { \Omega } _ { u }$ 到用户 $\nu$ 存在唯一的信任传递链，其中实线表示用户直接信任关系，虚线表示用户间接信任关系。

![](images/756968af2a4f4155a4ff15310646f10518e004364036a33e83aedb1818af56e6.jpg)  
图2单信任链传递图

根据六度空间理论，可以认定信任从用户 $\boldsymbol { u }$ 到用户 $\nu$ 传递长度不会超过6，设信任链长度阈值为 $H$ ，其中 $H { \leq } 6$ 。首先给出Einstein算子如下：

$$
E _ { x , y } = \frac { x y } { 2 - ( x + y - x y ) } \forall x , y \in [ 0 , 1 ]
$$

$$
T _ { x , y } = \frac { E ( 2 x , 2 y ) } { 2 } = \frac { x y } { x y + ( 1 - x ) ( 1 - y ) } \forall x , y \in [ 0 , 0 . 5 ]
$$

基于式(9)可以扩展到不大于 $H$ 个的信任传递数的单信任传递链，计算公式为

$$
T _ { u , \nu } = \frac { \prod _ { i = 1 } ^ { n } t _ { i } } { \prod _ { i = 1 } ^ { n } t _ { i } + \prod _ { i = 1 } ^ { n } ( 1 - t _ { i } ) } i = 1 , \cdots , H
$$

其中： $T _ { u , \nu }$ 为用户 $\mathbf { \Phi } _ { u , \nu }$ 之间一条信任链下的间接信任度； $t _ { i }$ 表示从用户 $\boldsymbol { u }$ 开始到用户 $\mathbf { \sigma } _ { \nu }$ 结束的一条信任传递链上的第 $i$ 个信任度。

# 2.2.2多信任链传递

多信任链传递是信任从网络一个节点传递到没有直接关联的另一个节点时，通过多条不同的信任链都能到达，其中单信任链传递可认为是多信任链传递的一种特例。多信任链传递如图3所示。

![](images/f7999d3d1caa8c3d385855532d68ac27f830321e8a295c7535af67531e723343.jpg)  
Fig.2Single trust transitivity chain graph   
图3多信任链传递图  
Fig.3Multiple trust transitivity chain graph

对于用户 $u$ 到用户 $\boldsymbol { \nu }$ 存在多链路信任传递时，可以分别计算不同信任链 S1、 $S 2$ 、、 $S ( \mathrm { n - l } )$ 、 $S \mathrm { n }$ 作为单信任链时的间接信任度。其中，在不同的传递链中，每条传递链得到两用户的间接信任度不会全部相同。

一个用户受到不同信任传递的链路越多，用户得到的信任就越客观，因此，为了克服单条链路信任的主观性，就需要考虑每条传递链的作用。又因为信任在社会网络中传递具有弱传递性，信任链的长度越长，这条信任链计算出的信任影响就越小。在此首先将多信任链下每条信任链按从长到短排序，通过求解OWA算子为每条信任链赋予不同的权重，真实反映社会网络中信任传递的性质和规律。根据OWA算子的定理，给出信任链权重的计算公式：

$$
F ( x ) = x ^ { 2 }
$$

$$
w _ { j } = F { \Biggl ( } { \frac { j } { n } } { \Biggr ) } - F { \Biggl ( } { \frac { j - 1 } { n } } { \Biggr ) } , j = 1 , \cdots , n
$$

其中： $w _ { j }$ 为将信任链排序后第 $j$ 条信任传递链的权重值。最后根据求解的权重融合多信任链上的信任值并计算间接信任Itrust，计算公式如下：

$$
I t r u s t _ { u , \nu } = \sum _ { j = 1 } ^ { n } T _ { u , \nu } ^ { j } w _ { j } j = 1 , \cdots , n
$$

# 3基于有序加权平均多链路信任传递的推荐算法构建流程

在本章中将给出本文推荐算法的具体流程。该推荐算法一共分五个步骤:

a)读入数据。

经过预处理的数据息应包括用户信息、项目信息和用户对项目的评分信息。

b)计算用户间相似度。

相似度 $s i m _ { u , \nu }$ 计算方法以Person相似度计算方法为例，其公式为

$$
s i m _ { u , \nu } = \frac { \sum _ { i \in I _ { u , \nu } } \big ( r _ { u , i } - r \overline { { ( u ) } } \big ) \big ( r _ { \nu , i } - r \overline { { ( \nu ) } } \big ) } { \sqrt { \sum _ { i \in I _ { u , \nu } } \big ( r _ { u , i } - r \overline { { ( u ) } } \big ) ^ { 2 } } \sqrt { \sum _ { i \in I _ { u , \nu } } \big ( r _ { \nu , i } - r \overline { { ( \nu ) } } \big ) ^ { 2 } } }
$$

其中: $I _ { u , \nu }$ 表示用户 $\boldsymbol { u }$ 与 $\nu$ 共同评价过的项目集合； $r _ { u , i }$ 与 $r _ { \nu , i }$ 分别表示用户 $\boldsymbol { u }$ 与 $\nu$ 对项目 $i$ 的实际评分； $r \overline { { ( u ) } }$ 为用户 $\mathbf { \Omega } _ { u }$ 对项目的平均评分； $r \overline { { ( \nu ) } }$ 为 $\nu$ 对项目的平均评分。

c）计算用户间信任度。

利用上述建立的信任传递模型计算出用户间的信任度。

d)融合用户相似度与信任度。

根据用户相似度与信任度的关系，通过设置推荐权重 $\theta$ ，自适应地平衡相似关系和信任关系，可以提高识别邻居的能力，避免相似度过小而信任度却较大的问题。融合规则如下：

$$
W _ { u , \nu } = \left\{ \begin{array} { c c } { \theta s i m _ { u , \nu } + ( 1 - \theta ) T r u s t _ { u , \nu } 3 i m _ { u , \nu } > 0 } \\ { s i m _ { u , \nu } \qquad } & { s i m _ { u , \nu } \leq 0 } \\ { T r u s t _ { u , \nu } } & { s i m _ { u , \nu } = \emptyset } \end{array} \right.
$$

其中： $W _ { u , \nu }$ 为融合后的综合相似度； $s i m _ { u , \nu }$ 为用户间的相似度;$T r u s t _ { u , \nu }$ 为用户间的信任度。当两用户相似度不存在时，采用Trust为综合相似度；当两用户相似度小于0时，采用 $s i m$ 为综合相似度。

e)预测评分并推荐。

使用融合后的综合相似度作为寻找最近邻居的依据并进行评分预测。采用的预测评分公式如下：

$$
p _ { u , i } = r \overline { { ( u ) } } + \frac { \sum _ { \nu \in S } W _ { u , \nu } \left( r _ { \nu , i } - r \overline { { ( \nu ) } } \right) } { \sum _ { \nu \in S } W _ { u , \nu } }
$$

其中： $s$ 为目标用户的邻居集合； $W _ { u , \nu }$ 为融合后的综合相似度；$p _ { u , i }$ 为目标用户 $\boldsymbol { u }$ 对项目 $i$ 的预测评分。将得到的预测分值，从大到小排列，选择其中最大的 $\mathrm { ~ N ~ }$ 个项目，作为Top-N的项目推荐使用。

# 4 实验验证及分析

# 4.1实验数据

本文使用的是著名的 $\mathrm { m l - l m }$ 的数据集，该数据集合来自6040个用户对3952部电影的100多万条评分数据，采用1\~5 整数评分制。实验评估前，首先进行降噪处理，最终保留965个用户的50多万条评分数据，将这组数据分别以训练集占比 $20 \%$ 、 $50 \%$ 、 $80 \%$ 进行实验，然后利用训练集中的预测来对测试集进行验证。

# 4.2实验评价标准

本次实验的评价指标采用平均绝对误差(MAE），其为最常用来评估算法准确度的指标。该指标是根据训练集的数据预测用户对项目的评分来与测试集中的真实评分相比，计算出绝对值差的平均。平均不会出现正负相抵消的情况，所以平均绝对误差能更好地反映预测值误差的实际情况。

$$
M A E = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \lvert p _ { u , i } - r _ { u , i } \rvert
$$

其中： $p _ { u , i }$ 为用户 $\mathbf { \Omega } _ { u }$ 对项目 $i$ 的预测评分， $r _ { u , i }$ 为用户 $\mathbf { \Omega } _ { u }$ 对 $i$ 的实际评分。MAE值越小，推荐的效果越好。

# 4.3实验结果

4.3.1融合信任度与相似度时权重 $\pmb \theta$ 值的确定

影响实验结果MAE值大小的因素有三个，即 $\theta$ 值的大小、邻居集合的大小以及测试集占实验比的多少。所以本文采取控制变量法，共进行六次实验。首先保持邻居数量为20不变而改变 $\theta$ 值与测试集所占比例，确定一个效果最好的 $\theta$ 值。实验结果如图4所示。

![](images/3eba2efd77ac0b603b45efad6b182eab3489ca8a376533101ba5839aafc9b294.jpg)  
图4参数 $\theta$ 对 $M A E$ 值的影响  
Fig.4Parameter $\theta$ influences value of MAE

从图4可以看出，当测试集占比从 $20 \% { \sim } 8 0 \%$ 时，MAE值随着 $\theta$ 值的变化趋势几乎一致，并且在 $\theta$ 取0.1时取得最小值，这说明该算法实用性强。而且随着实验中测试集占比的增大，MAE值也随着增大，这说明用于训练的数据越多，推荐效果越精确。

然后本文保持测试集占比为 $20 \%$ 不变而改变邻居用户的数量和 $\theta$ 值，实验结果如图5所示。

从图5中可以看出，当邻居用户从4个增加到12个时，MAE值随着 $\theta$ 值的变化趋势几乎一致，并且在 $\theta$ 取0.1时取得最小值。而且随着实验中邻居用户的增加，MAE值随着减小，这说明用当用户的邻居数量越多，可用于参与计算的数据越多，推荐效果越精确。综上，当 $\theta$ 取0.1时MAE值最小，推荐效果最好。

# 4.3.2实验结果分析

本实验对传统协同过滤算法、无信任传递方法、简单计算信任传递方法以及本文方法进行比较，四种方法均采用邻居用户4\~28，增量为4，计算MAE值结果如图6所示。

![](images/04c00ac0e75f8f1693309137835178f0aa598050763b6f7d831a1f7494bf8ac4.jpg)  
图5参数 $\theta$ 对 $M A E$ 值的影响

![](images/60558281ff8fc74b89674acfe53a643cd4bf5a32f23c2fa3f35ae2fd5aaa23bd.jpg)  
Fig.5Parameter $\theta$ influences value of MAE   
图6四种方法MAE值对比  
Fig.6MAE value comparison graph of four methods

实验分析：从图6中可以看出，当邻居用户从4增长到28时，四种方法的MAE值都逐渐下降；邻居用户增长到20之后四种方法都开始收敛，这与实验数据有关。在引入信任之后，协同过滤算法得到明显提升，本文引入信任，并考虑了深层次信任传递问题，所以本文提出的方法优于传统协同过滤算法和无信任以及简单计算信任传递的方法

# 5 结束语

本文旨在解决基于信任协同过滤算法中数据稀疏性以及基于社会网络关系的推荐算法中信任传递规则计算不合理等问题。通过建立信任传递模型，挖掘深层次的用户信任关系并结合协同过滤算法，更合理地为用户匹配邻居用户进行推荐。经过实验验证，本文提出的方法有效提高了推荐精度，证明了该方法的合理有效性，为基于信任的推荐算法研究提供了新思路。当然，基于信任的推荐算法仍有继续研究和探索的空间，以后的工作还要研究随着时间的改变用户兴趣和信任的变化以及将不信任关系引入推荐模型，以期更好地改善推荐效果。

# 参考文献：

[1]Li Wenjuan，Cao Jian，Wu Jiyi，et al.A collaborative filtering recommendation method based on discrete quantum-inspired shuffled frog leaping algorithms in social networks [J].Future Generation Computer Systems,2018,88(11):262-270.   
[2]Lim SL.Social networks and collaborative filtering for large-scale requirements elicitation[J]. IEEE Trans on Software Engineering,2012, 38 (3): 707-735.   
[3]Ma Hao，Yang Haixuan,Lyu M R，et al. SoRec: social recom-mendation using probabilistic matrix factorization [C]// Proc of the 17th ACM conference on Information and knowledge management. NewYork:ACMPress,2008:931-940.   
[4]Salakhutdinov B R,Mnih A.Probabilistic matrix factor-ization [C]// Proc of the 2Oth International Conference on Neural Information Processing Systems.2015:1257-1264.   
[5] 彭鹏，米传民，肖琳．基于用户信任和兴趣的概率矩阵分解推荐方 法[J].计算机系统应用,2017,26 (9):1-9.(Hu Peng,Mi Chuanmin, Xiao Lin.Recommended algorithm based on user trust and interest with probability matrix factorization [J].Computer Systems and Applications, 2017,26 (9): 1-9.)   
[6] 陈婷，朱青，周梦溪，等．社交网络环境下基于信任的推荐算法 [J]. 软件学报,2017,28(3):721-731.(Chen Ting,Zhu Qing,Zhou Mengxi, et al.Trust-based recommendation algorithm in social network [J]. Journal of Software,2017,28 (3): 721-731.)   
[7]Massa P,Bhattacharjee B.Using trust in recommender systems:an experimental analysis [C]//Proc of International Conference on Trust Management.Berlin: Springer,2004:221-235.   
[8]O'Donovan J,Smyth B.Trust in recommender system-s [C]// Proc of the 1Oth International Conference on Intelligent User Interfaces.New York: ACM Press,2005:167-174.   
[9]Zhang Peiyun,Kong Yang,Zhou Mengchu.A domain partition-based trust model for unreliable clouds [J].IEEE Trans on Information Forensics & Security,2018,13 (9):1-1.   
[10]王占，林岩.基于信任与用户兴趣变化的协同过滤方法研究[J].情 报学报,2017,36(2):197-205.(Wang Zhan,Lin Yan.Research on collaborative filtering method based on trust and the change of user’s interest [J]. Journal of the China Society for Scientific and Technical Information,2017,36(2):197-205.)   
[11]杨丰瑞，吴晓浩，万程峰．基于综合信任的社会化混合推荐算法 [J/OL].计算机应用研究,2019,36(12).(2018-10-18)[2018-11-01]. http://www.arocmag.com/article/02-2019-12-004.html (Yang Fengrui, Wu Xiaohao,Wan Chengfeng.Socialhybrid recommendation algorithm comb-ined with comprehensive trust [J/OL].Application Re-search of Computers,2019,36(12）.(2018-10-18)[2018-11-01]. htp://www. arocmag.com/article/02-2019-12-004. html.)   
[12] Yager R R.On ordered weighted averaging aggregation operators in multicriteria decisionmaking [J].IEEE Trans on Systems Man & Cybernetics,1988,18:183-190.   
[13]胡祥培，尹进.信任传递模型研究综述[J].东南大学学报：哲学社 会科学版,2013,15(4):46-51.(Hu Xiangpei, Yin Jin.A review of research on trust transitivity model[J].Journal of Southeast University: Philosophy and Social Science,2013,15 (4): 46-51.)   
[14] Sun YL,Yu Wei,Han Zhu,et al.Information theoretic framework of trust modeling and evaluation for ad hoc networks [J]. IEEE Journal on Selected Areas in Communications,2006,24 (2): 305-317.   
[15]田博，覃正.B2C 电子商务中基于D-S 证据融合理论的推荐信任评 价模型[J].管理科学,2008,21(5):98-104.(Tian Bo,Qin Zheng. Recommended trust evaluation model in business-to-consumer E-commerce based on D-S evidence fusion theory [J].Journal of Management Science,2008,21(5): 98-104.）   
[16]Kim YA,SongH S.Strategies for predicting local trust based on trust propagation in social networks [J].Know ledge-Based Systems.2011, 24 (8): 1360-1371   
[17] Walter F E,Battiston S,Schweitzer F.A model of a trust-based recommendation system on a social network [J].Autonomous Agents and Multi-Agent Systems,2008,16 (1): 57-74.   
[18] Ameri F,Zoej MJV,Mokhtarzade M.Multi-criteria,graph-based road centerline vectorization using ordered weighted averaging operators [J]. Photogrammetric Engineering and Remote Sensing，2016,82 (2): 107-120.   
[19] Wu Jian,Chiclana F. Non-dominance and attitudinal pri-oritisation methods for intuitionistic and interval-valu-ed intuitionistic fuzzy preference relations [J].Expert Systems with Applications,2012,39: 13409-13416.   
[20]李熠晨，陈莉，石晨晨，等．采用信任网络增强的协同过滤算法[J]. 计算机应用研究，2018,35(1):116-120.(Li Yichen,Chen Li,Shi Chenchen,et al. Enhanced collaborative filtering adopting trust network [J].Application Research of Computers,2018,35(1):116-120.）