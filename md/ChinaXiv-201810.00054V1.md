# 基于信息熵和用户行为一致性的协同过滤分组推荐

苏梦珂，杨煜普

(上海交通大学自动化系 系统控制与信息处理教育部重点实验室，上海 200240)

摘要：在仅以输入评分矩阵作为唯一算法输入的协同过滤推荐算法研究中，针对数据的质量不同带来的差异性对推荐结果的影响这一问题，包括对数据质量方面的重视与关注、如何刻画质量差异性以及如何针对不同质量数据的用户组别进行分组推荐建模等问题，提出针对数据质量的刻画，综合考虑用户行为一致性和用户信息熵两个指标对数据质量进行评价并对用户进行分组。对于不同组别的用户在分析其历史行为的基础上可以进行更精准的推荐建模。实验结果表明，数据质量的差异性确实对推荐精度的提升有着重要的影响，同时论证了对用户进行分组推荐的必要性。实验结果同时表明，运用用户行为一致性和用户信息熵两个指标的综合刻画带来的精度提升效果最为显著。

关键词：信息熵；噪声刻画；数据质量差异性；用户行为一致性；协同过滤中图分类号：TP311 doi:10.3969/j.issn.1001-3695.2018.05.039

# Collaborative filtering group recommendation based on information entropy and user behavior consistency

Su Mengke, Yang Yupu (KeyLaboratoryofSystemControl&InformationProcessing,MinistryofEducationofChina,Dept.ofAutomation,anghai Jiao Tong University, Shanghai 200240, China)

Abstract:For the scoring matrix as theunique algorithm inputofthecollaborative filteringrecommendation algorithm,the diferences inthequalityofthedatahave greatimpactontherecommendationresults,includingarousing theatentiontodata quality,how tocharacterizequality diferences,andhow to groupusers andrecommendon the basis of user groups with diferentqualitydata.This paper proposes a descriptionofdata quality，comprehensively considers the "user behavior consistency"and "userinformation entropy"to evaluate the data quality.Usersof diferent groups can perform moreaccurate recommendationresultsbasedonanalyzingtheir historical behavior.The experimentalresults show thatthediferenceindata qualitydoes haveanimportantimpactonthe improvementofrecommendationaccuracy,andatthesame time demonstratethe necesity of group recommendation.The experimental results also show thatthe accuracy of the combination of the two aspects of "user behavior consistency" and "user information entropy" is the most significant.

Key words: information entropy;noise description;dataqualitydiference; userbehaviorconsistency;collaborative filtering

# 0 引言

互联网技术的快速发展加速了网络资源的急剧膨胀，每天都有大量的信息充斥在网络中，这种膨胀的信息过载问题使得用户通过传统的检索模式去寻找自己感兴趣的信息的代价越来越高，同时用户也很难对爆炸式增长的信息进行有效的处理和利用。推荐系统作为当下社会解决信息过载问题的一项重要技术，已经被广泛地应用在各大平台如亚马逊电子商务平台和一些社交网站平台。其中基于协同过滤1的推荐算法自出现以来就得到了广泛的研究和应用，主要由于其实现的简单性和易扩展性。经典的基于用户的协同过滤算法2主要是为每个用户找到一个相似度高的用户集合，利用两个用户之间存在共同评分项目计算用户之间的相似性。而基于模型[3.4的协同过滤推荐算法是利用评分数据对用户评分规律进行数学建模,其中矩阵分解模型[5把用户和项目映射到共同的低维隐含空间，并尝试通过用户和项目在隐空间的向量积解释评分，后来随着Netflix大赛的发展，矩阵分解及其改进模型因突出表现脱颖而出。

基于模型的协同过滤算法的优点在于可以提高推荐的准确性，算法的关键在于利用训练数据集离线学习一个预测模型，而算法和数据是影响这个模型准确性的两个相当重要的因素。推荐算法是基于数据集提供的数据质量不存在差异，基于不同用户的行为数据都准确地代表了用户的真实喜好，继而在建模时对所有用户进行同等看待不加分类。但是在现实应用中的推荐系统如电子商务平台会存在一些恶意用户给出参考价值很小的用户反馈，而有些用户的反馈会十分有利于对他们进行推荐。即不同用户的行为数据在质量方面存在差异性，有些用户的行为前后比较一致，反馈比较稳定，利用这些数据不仅降低建模难度，并可以给这些用户提供更精准的结果，而有些用户的行为前后反差较大，对模型来说这些数据较难利用且结果也不够准确。所以数据的质量和数量极大地影响了推荐结果的准确性[6]，即数据中的噪声问题，而数据中的噪声问题却一直以来没有得到广泛的关注。推荐系统的噪声一般可以分为两类：a)为了某种目的，为了提高商业利益或者恶意扰乱而出现的蓄意噪声[7]；b)用户打分太过随意，并没有真实的表达自己的想法的自然噪声[8]。

近来的相关研究只是单纯地把数据质量问题转换为部分去噪问题，如Chirita等人[9提出了一种识别恶意用户的评价指标，Bilge 等人[10]为了识别恶意用户和水军账号，采用K-均值聚类算法划分不同的用户组别，Cao等人[I]提从半监督(semi-shillingattackdetection，Semi-SAD)的角度出发，利用少量数据预训练一个贝叶斯分类器再自适应于所有数据得到最终的分类器。这些方法虽然使得噪声引起的推荐精度问题得到了解决，但是共同弊端在于需要训练复杂的模型，并且调参复杂，而噪声只是数据质量的一种体现。

刘江冬等人[16提出借鉴信息熵的概念，综合考虑用户信息熵和评分时效性过滤部分用户，从而提高推荐的准确性。于鹏华[17]从数据的角度综合考量数据的质量和数量问题，对评分数据进行分组，分析了数据的质量和数量差异对推荐结果的影响。张佳等人[18借鉴用户信息熵来表达用户的评分分布，并确定评分倾向性程度，在传统的基于用户的协同过滤算法中确定某一用户的最近邻时利用信息熵将某些明显倾向不同的用户剔除，提高了最后的推荐精度。高翠华等人[19]综合考虑信息熵和模糊聚类，利用信息熵衡量隶属度的不确定性，提出融合信息熵加权的模糊聚类协同过滤算法，在提高推荐精度的同时简化了算法的复杂度。Kluver等人[8提出可以用信息熵刻画用户的评分质量，Bellogin等人[12]通过分析用户历史行为提出一种新的评分质量评价。为了充分说明数据质量对推荐结果的影响，本文综合考虑信息熵和用户行为一致性来共同全面地刻画不同质量的数据，并提出基于不同质量和数量的数据子集的分组协同过滤推荐算法。本文提出综合考虑用户评分两种极端情况随意和集中来分析用户质量，将用户分为不同质量的数据子集并进行分组推荐，进一步实现了针对不同用户的个性化建模，并提高了推荐精度。

# 问题基本描述

# 1.1基本模型 BMF

矩阵分解模型的输入如表1所示。表1中显示的是 $\mathbf { m }$ 个用户对n个项目的所有的评分集合，其中如果用户 $\mathbf { u }$ 对某个项目i进行了观影评价，则 $r _ { u i }$ 表示相应的评分，一般的评分矩阵比较稀疏，用户未评论过的电影在矩阵内评分用0表示。如何利用已有的评分数据通过数学建模的方式将用户和项目潜在的评分规则公式化，并对未知评分进行预测是进行推荐的关键步骤。

表1评分矩阵  

<html><body><table><tr><td rowspan="2">用户</td><td colspan="4">项目</td></tr><tr><td>i</td><td>i</td><td>：</td><td>in</td></tr><tr><td>u1</td><td>r11</td><td>r12</td><td>…</td><td>Y1n</td></tr><tr><td>u2</td><td>r21</td><td>r22</td><td>：</td><td>r2n</td></tr><tr><td>：</td><td>…</td><td>：</td><td>：</td><td>…</td></tr><tr><td>Um</td><td>rml</td><td>rm2</td><td></td><td>Ymn</td></tr></table></body></html>

矩阵分解 BMF 模型是隐语义模型 (latent factor model)[13]的改进模型，因为其在推荐系统数据比赛Netflix比赛2009 年的杰出表现而成为最热门的推荐算法。矩阵分解模型BiasedMF(Biasedmatrixfactorization)算法通过寻找一个低维的隐含因子空间，把原始用户和项目映射到这一低维空间，项目i映射成向量 $q _ { i }$ ，向量分量表示项目i对这些基本因子的包含程度，用户 $\mathbf { u }$ 映射成向量 $p _ { u }$ ，向量分量是用户对该因子的偏好程度的表征。经过低维映射后，某用户 $\mathbf { u }$ 对某项目i的偏好程度可以用用户和物品向量的内积 ${ q _ { i } } ^ { T } p _ { u }$ 来表示。

基于矩阵分解的推荐算法以所示矩阵作为算法的输入，通过挖掘用户和项目的隐含潜在因子进行数学建模，并对用户未知的评分进行预测。本文选用BiasedMF(BMF)算法为基础，融合用户的信息熵和行为一致性提出了改进方案。BMF的基本算法如下：

$$
b _ { u i } = \mu + b _ { u } + b _ { i }
$$

$$
\hat { r } _ { u i } = b _ { u i } + q _ { i } ^ { T } p _ { u }
$$

$$
\operatorname* { m i n } _ { p _ { u } , q _ { i } } \sum _ { ( u , i ) \in R _ { n e w } } \Bigl [ ( \widehat { r } _ { u i } - r _ { u i } ) ^ { 2 } + \lambda ( \bigl \| q _ { i } \bigr \| ^ { 2 } + \bigl \| p _ { u } \bigr \| ^ { 2 } + { b _ { u } } ^ { 2 } + { b _ { i } } ^ { 2 } ) \Bigr ]
$$

式(1)表示评分的偏置项构成，其中 $\mu$ 表示整体平均值， $b _ { u }$ 表示用户偏置， $b _ { i }$ 表示项目偏置；式(2)表示预测评分由模型预测结果和偏置项构成。训练模型使得 $\hat { r } _ { u i }$ 无限接近于 $r _ { u i }$ ，即转换成式(3)所示的最优化问题，其中 $\lambda$ 表示正则化项，目的是为了提高模型的泛化能力。选择常用的随机梯度下降法寻找到最优的P和Q。模型训练好以后，就可以对用户未评分电影进行预测，并按照评分从高到低的集合进行推荐。

# 1.2噪声问题

大多相关学者的研究工作都是收集到原始的评分矩阵，根据某种策略将数据分为训练集和测试集，然后进行建模与测试。因为评分矩阵作为协同过滤算法的唯一输入，所以评分矩阵的质量差异性会在很大程度上影响算法的最终结果。如何刻画不同用户的评分质量，并对用户进行分组推荐是本文关心的问题。

为了分析评分质量的差异与推荐精度的关系，针对不同的用户存在不同程度的噪声数据的问题，本文针对数据中的噪声问题，综合考虑用户信息熵和用户历史行为来刻画用户的评分质量差异，并将用户分为不同的质量子集。根据文献[8]指出的可信度低的用户的评分存在过于集中，如评分一边倒或者只是针对某些特定的目标的问题，本文引入信息熵来刻画用户评分质量。信息熵可以表征随机变量的取值不确定性的情况，刻画一个随机变量的概率分布情况，随机变量的信息熵的值与其分布的混乱程度成正比。设某一变量的信息熵定义如式(4)所示。

$$
H ( Y ) = - \int f ( y ) l b f ( y ) d y
$$

由式(4)可知，信息熵与变量的概率分布密切相关，用户信息熵可以反映用户评分的丰富程度，如果用户信息熵过低，即可表示用户的评分过于集中。

但是如果只是过滤掉集中性过强的用户，那些打分丰富的用户的并不一定都是可靠的评分，所以不能单独以集中性来刻画用户的评分质量。根据Bellogin提出的基于用户历史行为数据引入用户行为一致性[2]来从另一个角度衡量用户的评分质量。用户行为一致性反映了用户的评分是否前后连贯，可根据这一指标将用户划分为行为一致性程度较高和较低的不同组别。综合考虑用户信息熵和用户行为一致性分析不同的数据质量对推荐结果的影响。

# 2 模型改进

# 2.1评分的质量刻画

# 2.1.1引入用户信息熵刻画用户评分质量

如何对评分矩阵的质量差异性进行刻画，如何将不同的用户分为不同的质量子集，本文从数据的噪声的角度来刻画数据的质量，并提出综合分析用户的信息熵和历史行为来分析用户评分的质量。根据式(4)的定义，假设 $\left\{ R _ { u } = r _ { 1 } , r _ { 2 , \cdots r _ { i . . . } } \right\}$ 表示用户 $\mathbf { u }$ 的所有评分信息。对用户 $\mathbf { u }$ ，定义用户评分取值的概率为该评级出现的次数与评分总次数的占比，即 $P _ { u g }$ 如式(5)所示，用户的信息熵定义为 $C _ { 1 } ( u )$ 如式(6)所示。

$$
P _ { u g } = \frac { \displaystyle \left[ \sum _ { r _ { i } \in R _ { u } } I ( r _ { i } = g ) \right] } { \displaystyle \left| R _ { u } \right| } ; g = 1 , 2 , 3 , 4 , 5
$$

$$
C _ { 1 } \big ( u \big ) = \sum _ { g = 1 } ^ { 5 } - P _ { u g } l b ( P _ { u g } )
$$

用户信息熵反映了用户评分偏水军特点的可能性。根据文中公式定义，用户信息熵偏低则表明用户偏水军的可能性越高。2.1.2 基于用户历史行为刻画用户评分质量

基于用户的历史评分行为，如图1表示两个用户对类似题材分布下的电影的评分集合，基于用户的评分高低反应用户的好恶，图1左的用户相对于爱情和伦理片更喜欢惊悚类的电影，而图1右的用户的行为数据比较分散，不易挖掘规律。长远看来有理由相信图1中的用户（左）评分相对于用户（右）比较稳定，因为用户（左）对于相似类型的电影评分也比较相似。

假设用户行为前后连贯表现在对同种类型或者相近类型地评分偏差较小，利用用户在相似物品空间的评分偏差来定义用户行为的稳定性。对任一用户有过评分行为的项目划分为不同的特征空间，假设 $R ( u , f )$ 表示用户对特定特征空间的物品的评分集合， $\bar { r } _ { u f }$ 表示用户在这一特征下的评分平均值， $R ( u , F )$ 表示用户$\mathbf { u }$ 的所有评分集合，则用户行为一致性 $C _ { 2 } ( u )$ 可以用用户在各种特征空间的评分下的偏差来表征，如式(8)所示。

$$
C _ { 2 f } ( u ) = \sqrt { \sum _ { i \in R ( u , f ) } ( r _ { u i } - \overline { { r } } _ { u f } ) ^ { 2 } }
$$

$$
C _ { 2 } ( u ) = - \sum _ { f \in F } C _ { 2 f } ( u ) \frac { \left\| R ( u , f ) \right\| } { \left\| R ( u , F ) \right\| }
$$

其中： $C _ { 2 f } ( u )$ 表示用户的某种特定评分方差； $C _ { 2 } ( u )$ 表示用户整体评分方差，实质为用户的特定评分方差的加权平均，其值与用户行为一致性成正比关系，用户行为前后行为一致，则这部分用户较容易建模。

![](images/85158e564866e76d6eacb5f637d799e08d1fe36f63ecff0a78d9ceeb88a81bb1.jpg)  
图1用户行为一致性

# 2.2用户分组并进行分组推荐

本文对所提的 $C _ { 1 } ( u )$ 和 $C _ { 2 } ( u )$ 采用顺序式用户分组，通过对用户的评分数据分析，每个用户得到相应的 $C _ { 1 } ( u )$ 和 $C _ { 2 } ( u )$ 。对于信息熵这个评价指标，由于信息熵是针对用户评分数据具有一边倒的特点而定义的，所以首先根据 $C _ { 1 } ( u )$ 将用户信息熵较低的用户采取直接过滤的方式，即在原始数据中保留评分质量良好的大部分数据；然后根据 $C _ { 2 } ( u )$ 的值将用户聚类为困难用户和容易用户，分析不同组别的质量差异性对推荐精度的影响。

# 3 实验与分析

# 3.1实验数据集

为了测试数据的质量差异性对最终推荐精度的影响，以及验证质量指标的有效性和分组推荐的必要性，利用著名的Movielens1M( $\mathrm { . m l - l m }$ ）电影评分公开真实数据集[14]对本文提出的算法进行实验评估。该数据集包括6000多用户的评分数据1000209条，每个用户评论的电影在20部以上，一共有3900部电影。其中评分值反映了用户对电影的喜爱程度，评分值越大代表用户对电影评价越高。该数据集属于数据量易处理里涵盖信息比较丰富的数据集，在用户的数据质量方面存在差异性，适合进行此次验证。

# 3.2评价指标

不同的评价指标适用于不同的研究环境。由于本文主要是针对数据质量差异性进行刻画，为了体现不同质量数据组对推荐精度的影响，并分析针对不同质量差异性造成的推荐精度的影响，本文采用评分预测中的均方根误差(RMSE)15指标作为此次实验的评估。RMSE是通过利用在训练集上得到的模型对未知评分进行预测后计算预测的用户评分和实际的用户评分之差来评估推荐精度。RMSE因其直观表征推荐的精度而被广泛采用。RMSE与推荐精度成反比，如式(9)和(10)所示。

$$
R M S E ( u ) = \sqrt { \sum _ { i = 1 } ^ { n } ( r _ { u i } - \hat { r } _ { u i } ) ^ { 2 } }
$$

$$
\sum _ { R M S E = \frac { u = 1 } { m } } ^ { m } R M S E ( u )
$$

# 3.3实验步骤

# 3.3.1刻画用户评分质量

对数据集中的用户作为基准，对于每一条用户的评分数据，计算相应的用户信息熵和用户行为一致性，得到信息熵 $C _ { 1 } ( u )$ 如图2、3所示，一致性 $C _ { 2 } ( u )$ 如图4、5所示。

![](images/974e2570e36c5a7891bce34c8a503603d9a7f2f067d98e9c07101decd596a5cf.jpg)  
图2用户信息熵(归一化之后)

![](images/18b18e5d8994d61e943b2f491ac0ae6622f4726741ca090e99780c3b27953fd5.jpg)  
图3用户信息熵数量统计

图2和3分别表示对6040个用户的信息熵的分布和数量统计，大部分的评分质量是可靠的。 $C _ { 1 } ( u )$ 取不同阈值，通过取阈值为 $C _ { 1 } ( u ) = \left. 0 . 1 , 0 . 2 , . . . 0 . 8 \right.$ ，发现取 $C _ { 1 } ( u ) = 0 . 5$ 时精度提升最大,之后随着 $C _ { 1 } ( u )$ 的增大，会使评分矩阵越来越稀疏，从而也影响推荐的精度。

![](images/2f4eef96d65b71cc51052fe2b28945140567a82df500634b3de473848e32da1a.jpg)  
图4用户行为一致性

![](images/d0958872234feb92bde7239e4a3149a3b883d36d3c26370064f8a0e0c2121c87.jpg)  
图5用户行为一致性数量统计

# 3.3.2用户分组推荐

首先对用户根据 $C _ { 1 } ( u )$ 的值，选取不同的阈值进行数据过滤。对于低于阈值的用户评分数据，采取直接删除这一部分用户的做法。实验表明 $C _ { 1 } ( u ) = 0 . 5$ 的情况下，精度提升最大。

在此基础上根据 $C _ { 2 } ( u )$ 的值将用户分为困难用户和容易用户（取 $C _ { 2 } ( u ) = - 8$ ），此时，困难用户组评分数量为509623，容易用户组的评分数量为490586，两组分别接近原始数据集的$5 0 \%$ ，以排除数据数量对推荐结果的影响。两组用户都采用5折交叉验证划分为数据集和训练集，分别表示为 ${ t r _ { e } }$ $\smash { \dot { e } \mathrm { ~ s ~ } t e _ { e \mathrm { ~ s ~ } } t r _ { d } }$ 、$\boldsymbol { t e _ { d } }$ 。其中 $s _ { 1 } = ( t r _ { d } , t e _ { d } )$ 表示对困难用户组建模推荐， $s _ { 4 } = ( t r _ { e } , t e _ { e } )$ 表示对容易用户组建模推荐， $s _ { 2 } = \left( t r _ { e } \cup t r _ { d } , t e _ { e } \cup t e _ { d } \right)$ 表示原始数据建模推荐（对比的基准）， $s _ { 3 }$ 表示对原始数据进行信息熵过滤之后的用户组进行建模推荐。图6表示不同质量分组的情况下的误差RMSE，其中横轴(1,2.3.4)分别表示 $( { \bf \it { s } } _ { 1 } , { \it { s } } _ { 2 } , { \it { s } } _ { 3 } , { \it { s } } _ { 4 } )$ 。

![](images/9bf2945b9c5c1dac4a62486a1f48c11fb1e63a98058622157c0c20f2cf1748c2.jpg)  
图6不同质量情况下的误差RMSE

# 3.3.3对比实验

本文提出的融合用户信息熵和用户行为一致性改进的基于模型的协同过滤算法(ABMF)对比基本的BMF算法，RMSE指标降低了 $1 . 1 \%$ 。文献[16]提出的UEITMF方法融合信息熵和时效性的改进，考虑了实时动态这一特性，但是相较原始方法精度提升不明显，而且增加了算法的复杂度。文献[17]只是从数据质量的角度考虑，单一地考虑了用户前后行为的变化，推荐精度也有一定提升。Entropy-based-CF[18]是在基于用户的协同过滤的基础上融合信息熵，算法的逻辑性和理解性较高。不同算法的RMSE对比如表2所示。

表2不同算法的RMSE 对比  

<html><body><table><tr><td>算法</td><td>BMF</td><td>ABMF</td><td>UEITMF[16]</td><td>文献[17]</td><td>Entropy-based-CF[18]</td></tr><tr><td>RMSE</td><td>0.861</td><td>0.852</td><td>0.859</td><td>0.855</td><td>0.865</td></tr></table></body></html>

# 3.4 实验结果分析

对比 $s _ { 2 }$ 和 $s _ { 3 }$ ，不考虑用户行为一致性，只对用户进行信息熵过滤，虽然取 $C _ { 1 } ( u ) = 0 . 5$ 的情况下，推荐的精度由0.8614降低到0.8594，效果微弱，但是这一质量指标的提出对于大数据情况下分析如电子商务系统中刷单的行为应该会具有明显的效果。

经过过滤质量极差的用户后，针对剩余的用户根据进行$C _ { 2 } ( u )$ 的值分组，如图6所示， $s _ { 1 }$ 表示在困难用户子集上建模，并在困难用户子集上测试； $s _ { 4 }$ 表示在容易用户子集上建模，并在容易用户子集上测试； $s _ { 3 }$ 相对于 $s _ { 2 }$ 推荐精度提升了 $0 . 2 \%$ ： $s _ { 4 }$ 相对于 $s _ { 2 }$ 推荐精度提升了 $1 . 1 \%$ ， $s _ { 4 }$ 相对 $s _ { 1 }$ 推荐指标变化了$3 . 2 \%$ 。推荐精度的变化说明进行分组推荐是十分必要的，并且$( s _ { 1 } , s _ { 2 } , s _ { 3 } , s _ { 4 } )$ 分别表示数据的质量从低到高，明显RMSE呈下降趋势，即推荐精度呈提高趋势。实验结果论证了本文提出的信息熵和用户行为一致性综合分析用户评分质量的指标是十分有效的，不同质量组的建模推荐精度存在着显著差异。

# 4 结束语

本文从一个新型的角度即数据质量出发，提出提高基于模型的推荐算法精度的研究，综合评分集中性和随意性，分别通过用户信息熵和行为稳定度来刻画用户评分的质量差异性，并提出基于不同数据质量把用户分为不同组别并进行分开建模的改进方法。实验结果充分表明了数据质量的差异性对推荐精度的提高有重要的影响，所以在当下大数据的发展环境下，数据的质量问题应该引起广泛关注。数据质量问题会随着数据规模的增大凸显，数据集越大数据质量差异性会更显著，如何利用信息熵和用户行为一致性这两个指标对大数据集进行更好的分析，并对用户进行合理分组是接下来的研究方向。本文针对用户实现了评分质量分组，如何针对不同项目设置合理的分类标准，从不同角度定义相应的质量指标对数据进行分类，也是未来考虑的方向。

参考文献：   
[1] Chu Wei,Park S T. Personalized recommendation on dynamic contents using predictive bilinear models [C]// Proc of the 18th International Conference on World Wide Web.New York: ACMPress,2009: 691-700.   
[2] 沈键，杨煜普．基于二阶段相似度学习的协同过滤推荐算法[J].计算 机应用研究,2013,30(3):715-719.(Shen Jian,Yang Yupu.Collaborative filtering recommendation algorithm based on two stages of similarity learning[J].Application Research of Computers,2013,30 (3): 715-719.)   
[3]吴金龙．Netflix Prize 中的协同过滤算法[D].北京：北京大学，2010. (Wu Jinlong.Collaborative filtering algorithm in the Netflix Prize [D]. Beijing: Beijing University2010.)   
[4]Robert B, Yehuda K, CHRIS V.Modeling relationships at multiple scales to improve accuracy of large recommender systems [C]// Proc of the 13th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. New York: ACM Press,2007: 95-104.   
[5]Koren Y，Bell R，Volinsky C.Matrix factorization techniques for recommender systems [J].Computer,2009,42(8):30-37.   
[6]孟祥武，刘树栋，张玉洁，等．社会化推荐系统研究[J].软件学报， 2015,26(6): 1356-1372. (Meng Xiangwu,Liu Shudong, Zhang Yujie,et al Research on social recommender systems [J].Journal of Software,2015, 26 (6): 1356-1372.)   
[7]Gunes I, Kaleli C,Bilge A,et a1.Shilling attacks against recommender systems: a comprehensive survey [J].Artificial Intelligence Review, 2014, 42 (4): 767-799.   
[8]KluverD,Nguyen T,Ekstrand M,et a1. How manybitspeating[C]/ Proc of the 6th ACM Conference on Recommender systems.Dublin, Ireland: ACM Press,2012: 99-106.   
[9]ChiritaPA,Nejdl W,ZamfirC.Preventingshillng attacksinonline recommender systems [C]// Proc of the 7th Annual ACM International Workshop on Web Information and Data Management. New York: ACM Press, 2005: 67-74.   
[10] Bilge A, ZdemiRZ,Polat H. A novel shilling attack detectionmethod [J]. Procedia Computer Science,2014,31: 165-174.   
[11]Cao Jie,Wu Zhiang,MaoBo,etal.Shiling attack detectionutlizing semi-supervised learning method for collaborative recommender system [J]. World Wide Web,2013,16 (5//6): 729-748.   
[12] Bellogin A,Said A,Pdevries A.The magic barrier of recommender systems no magic just ratings [Cl// Proc of User Modeling,Adaption,and Personalization.Aalborg,Denmark: SpringerInternational Publishing,2014 25-36.   
[13]Hofmann T.Latent semantic models for collaborative filtering [J].ACM Trans on Information Systems,2004,22 (1): 89-115   
[14]张学胜面向数据稀弦的协同讨滤推芳管注研空[l今肥：中国科学

技术大学，2O11.(Zhang Xuesheng.Research on collaborative filtering recommendation algorithm for data sparse [D]. Hefei: University of

Science and Technology of China,2011.)

[15] Pang Yanwei，Ma Zhao，Pan Jing，et al.Robust sparse tensor decomposition by probabilistic latent semantic analysis [C]//Proc of the 6th International Conference on Image and Graphics.Washington DC: IEEEComputerSociety,2011:893-896．刘江冬，梁刚，冯程，等．基于 信息熵和时效性的协同过滤推荐[J].计算机应用2016，36(9): 2531-2534.(Liu Jiangdong,Liang Gang,Feng Cheng,et al. Collaborative filtering recommendation based on information entropy and timeliness [J]. Journal of Computer Applications 2016,36 (9): 2531-2534.)

[16]于鹏华．数据数量与质量的推荐系统若干问题研究[D].杭州：浙江大 学,2016.(Yu Penghua. Research on several problems of recommendation system for data quantity and quality [D]. Hangzhou: Zhejiang University, 2016.)

[17]张佳，林耀进，林梦雷，等．基于信息熵的协同过滤算法[J]．山东大 学学报：工学版,2016,46(2): 43-50.(Zhang Jia,Lin Yaojin,Lin Menglei, et al.Collaborative filtering algorithm based on information entropy [J]. Journal of Shandong University: Engineering Edition，2O16,46 (2): 43-50.)

[18]高翠芳，黄珊维，沈莞蔷，等．基于信息熵加权的协同聚类改进算法 [J].计算机应用研究 2015，32(4):1016-1018.(Gao Cuifang，Huang Shanwei, Shen Wanqiang，et al. Improved algorithm for collaborative clustering based on information entropy weighting [J].Application Research of Computers,2015,32(4): 1016-1018.)