# 融合协同过滤的XGBoost推荐算法

齐德法‘，徐连诚’，朱振方²

(1.山东师范大学 信息科学与工程学院，济南 250358;2.山东交通学院 信息科学与电气工程学院，济南 250357)

摘要：在推荐系统中，针对用户的冷启动问题，提出一种融合协同过滤的XGBo0st推荐算法。根据基于用户相似度的协同过滤推荐算法进行粗粒度召回，得到部分用户的召回集，使用 XGB00st 算法对召回集中的项目进行预测。对于存在冷启动问题的用户，直接使用XGB00st算法对候选集中的项目进行预测。该算法采用CCIR2018个性化推荐评测的在线评测数据集，并将推荐结果投放到知乎提供的线上平台进行评测。评测结果表明，该算法可以地解决用户的冷启动问题，具有很高的执行效率，准确度高，在线上评测中取得显著的推荐效果，并获得三等奖。

关键词：协同过滤；冷启动；XGBoost；推荐系统 中图分类号：TP301.6 doi:10.19734/j.issn.1001-3695.2018.10.0808

# XGBoost recommendation algorithm with collaborative filtering

Qi Defal, Xu Liancheng1,†, Zhu Zhenfang² (1.School ofInformationScience&Engineering，ShandongNormalUniversity,Jinan250358,China;2.Schoolof Information Science&Electrical Engineering,Shandong Jiaotong University,Jinan 25o357,China)

Abstract:In therecommendation system,this paper proposed an XGBoost recommendationalgorithm to integrate collborative filteringbasedon thecold-start problem of users.Firstly,ituses coarse graintorecallacording to the collborative filtering recommendation algorithm basedonuser similarity,and get arecall setof some users.Then using XGBoost algorithm to predict the items in therecallset.Secondly,forusers with cold-start problems,itcan directlyuse XGBoost algorithm to predictthe items in thecandidate set.Finall,the algorithmuses theonlineevaluation data setof CCIR2018 personalized recommendation evaluation,and puts the recommendation results on the online platform provided by Zhihu for evaluation.The evaluation results show that the algorithm inthis papercan solve thecold-start problemof users with highefficiencyandacuracy.Ithasachievedremarkablerecommendationeffectintheonlineevaluationplatform and gets the third prize.

Key words:collaborative filtering; cold-start; XGBoost; recommender system

# 0 引言

随着互联网的飞速发展，信息资源呈现几何级数增长，丰富的网络信息给用户带来极大的便捷，使用户能够通过网络获取更多的知识信息。但数据规模的爆炸式增长[1却产生了信息过载的问题，用户在大量的信息中很难获取到真正需要的数据信息。传统搜索引擎的出现解决了大数据时代初期信息过载的问题，但随着互联网的进一步发展，传统的搜索引擎已无法满足用户的特殊需求，因此个性化推荐系统应运而生，并成为了解决信息过载问题的有效方法[2]。个性化推荐系统能够根据用户个人喜好自动进行信息推荐，减少信息的冗余，简化用户的操作，从而带来更好的用户体验。

个性化推荐算法多种多样，传统的推荐算法主要有基于内容的推荐、协同过滤推荐[3]、混合推荐三种方式。基于内容的推荐是根据用户的历史交互记录，挖掘出与目标用户喜欢项目的相似项目。协同过滤是根据用户对项目的评分计算用户或项目之间的相似度，找出用户或项目的最近邻集合，最后产生推荐列表并进行推荐[4]。混合推荐是将多种推荐算法按照一定的规则组合在一起，然后进行预测，最终将结果

推荐给目标用户。

协同过滤是经典的推荐算法，其对推荐对象没有特殊要求，能够处理复杂的对象信息，可解释性强，简单易实现，因此协同过滤推荐算法被广泛应用。在实际应用场景中，协同过滤存在冷启动问题。冷启动问题是指在推荐系统中，缺少用户历史行为数据，系统无法得到用户的个人偏好，最终导致系统推荐效果较差。例如，当系统不存在或者存在少量的用户历史交互记录时，将无法得到目标用户的相似用户。同理，对于新项目也存在相同的冷启动问题。冷启动是协同过滤推荐算法中被广泛关注的问题，冷启动问题的存在严重影响了推荐系统的推荐质量[5]。

针对冷启动问题，陈克寒等人[提出一种基于两阶段聚类的推荐算法GCCR，将图摘要方法和基于内容相似度的算法结合，实现基于用户兴趣的主题推荐；于洪等人7提出了用户时间权重信息概念，将时间权重信息应用到推荐系统中，可以判断该用户是积极用户还是消极用户，以及用户对新项目的偏爱程度，该算法在准确度和新颖度都有较好的效果；Pereira等人[8]将用户人口统计信息引入到推荐算法，形成混合协同过滤推荐算法，可以很好地解决冷启动问题；

Shambour等人[9在传统的基于用户的协同过滤推荐算法中，融入了项目评分信任度的思想，同时槟弃了传统的相似度计算方法，该算法既能缓解数据稀疏性问题，又能很好地解决冷启动问题。

本文算法旨在解决推荐系统中的冷启动问题，同时提高算法的执行效率，减少推荐过程所消耗的时间，提高模型的准确率，改善用户体验。为了减少模型的计算量，本算法首先使用基于用户的协同过滤推荐算法进行项目的召回，对于活跃用户，可以得到用户的召回集。召回集的项目数量远远少于候选集的项目数量，使用XGBoost算法在召回集上进行回归预测，降低了模型的计算量，提高了预测效率。对于历史交互记录稀疏或者缺失的用户，此类用户对应的召回项目较少，甚至没有召回项目。对于该类用户，使用XGBoost算法直接在全部候选集中进行预测，虽然原始候选集的数据量较多，但此类用户在推荐系统中所占的比例很低，因此消耗的时间较少。通过本文算法可以有效地缓解用户的冷启动问题，同时又可以减少模型计算所消耗的时间，提高算法的执行效率。通过CCIR2018清华大学与知乎联合举办的个性化推荐评测的在线评测，本文算法取得了显著的推荐效果。

# 1 相关工作

# 1.1协同过滤

协同过滤[0]是经典的推荐算法，其在工业界得到了广泛应用。协同过滤主要分为基于用户的协同过滤、基于项目的协同过滤和基于模型的协同过滤。基于用户的协同过滤是根据用户的历史行为，挖掘出与目标用户相似的用户，然后向目标用户推荐其相似用户所喜好的项目；基于项目的协同过滤是根据项目的相似性，向用户推荐其喜欢项目的相似项目；基于模型的协同过滤首先根据训练集数据，采用概率统计模型或者机器学习方法建立模型（如潜在语义模型、贝叶斯模型、决策树模型、图模型等)，进而通过模型预测目标用户的偏好[11]。

定义包含 $m$ 个用户的集合 $U = \{ u _ { 1 } , u _ { 2 } , \cdots , u _ { m } \}$ ，包含 $n$ 个项目的集合 $I = \{ i _ { 1 } , i _ { 2 } , \cdots , i _ { n } \}$ ，用户对项目的历史交互记录矩阵 $s$ 可以表示为

$$
S _ { m \times n } = \bigl \{ s _ { 1 1 } , s _ { 1 2 } , \cdots , s _ { 1 n } , \cdots s _ { m 1 } , s _ { m 2 } , \cdots , s _ { m n } \bigr \}
$$

基于用户的协同过滤和基于项目的协同过滤，都是基于相似度进行计算，根据用户对项目的历史交互记录矩阵 $s$ ，可以得到相似用户或者相似项目，最后得到推荐列表。本文相似度计算公式使用Ochiai系数[12]，该系数源于生物学中两个地区共同物种分布区域的相似度计算方法，是余弦相似度[13]的一种形式。

Ochiai系数计算公式为

$$
\mathcal { L } ( \phi ) = { \sum _ { i } l } \big ( \hat { y } _ { i } , y _ { i } \big ) + { \sum _ { k } \Omega } \big ( f _ { k } \big )
$$

$$
w h e r e \Omega ( f ) = \gamma T + \frac { 1 } { 2 } \lambda \omega ^ { 2 }
$$

其中： $\hat { y } _ { i }$ 为预测值； $y _ { i }$ 为真实值； $\mathbf { \xi } _ { l }$ 为损失函数； $\Omega ( f _ { k } )$ 为正则项； $f _ { k }$ 为一棵决策树。XGBoost算法还使用了二阶泰勒展开，假设第 $t$ 次的损失函数为

$$
\mathcal { L } ^ { \left( t \right) } = \sum _ { i = 1 } ^ { n } l \big ( y _ { i } , \hat { y } _ { i } ^ { \left( t - 1 \right) } + f _ { t } \left( x _ { i } \right) \big ) + \Omega \big ( f _ { t } \big )
$$

对 $\mathcal { L } ^ { \prime \prime }$ 做二阶泰勒展开

$$
\mathcal { L } ^ { \left( t \right) } \simeq \sum _ { i = 1 } ^ { n } \biggl [ l \bigl ( y _ { i } , \hat { y } ^ { \left( t - 1 \right) } \bigr ) + g _ { i } f _ { t } \left( x _ { i } \right) + \frac { 1 } { 2 } h _ { i } f _ { t } ^ { 2 } \left( x _ { i } \right) \biggr ] + \Omega \bigl ( f _ { t } \bigr )
$$

$$
\begin{array} { r l r } { w h e r e } & { { } } & { g _ { i } = \hat { \sigma } _ { \hat { y } ^ { ( t - 1 ) } } l \left( y _ { i } , \hat { y } ^ { ( t - 1 ) } \right) } \end{array}
$$

$$
h _ { i } = \hat { \sigma } _ { \hat { y } ^ { ( t - 1 ) } } ^ { 2 } l \big ( y _ { i } , \hat { y } ^ { ( t - 1 ) } \big )
$$

其中： $g _ { i }$ 为一阶导数； $h _ { i }$ 为二阶导数。通过二阶泰勒展开，可以加快模型收敛速度，得到全局最优解。

XGBoost有原始XGBoost库和scikit-learn库的两种实现方式，为用户提供了多种参数，通过调节不同的参数，得到最优模型。XGBoost库中的基学习器不仅可以使用CART，也可以使用线性分类器。其效率很高，在Kaggle等比赛中取得了很好的成绩，在工业界也得到了广泛的使用。

# 1.2 XGBoost

$$
K = \frac { \left| A \cap B \right| } { \sqrt { \left| A \right| \times \left| B \right| } }
$$

# 2 融合协同过滤的XGBoost推荐算法的模型构建

其中： $A$ 和 $B$ 表示集合； $| A |$ 和 $\left| B \right|$ 分别表示集合 $A$ 和 $B$ 中的元素个数。

XGBoost[14]是由陈天奇博士提出的Gradient Boosting[15]算法，是GradientBoosting 的一种高效系统实现，其对GBDT[16进行了优化改进，能够并行计算、近似建树、对稀疏数据进行有效处理，对CPU和内存的使用进行了优化，使其在机器学习领域展现了很好的效果。

本模型使用协同过滤和XGBoost相融合的算法进行内容推荐。首先通过协同过滤得到用户的召回集；然后使用XGBoost模型对召回集中的项目进行预测，若不满足推荐数量，则继续使用XGBoost对候选集进行预测；最终产生推荐列表。模型构建主要分为三个阶段：首先是基于协同过滤的内容召回；其次是XGBoost模型训练；最后是产生推荐列表。算法流程如图1所示。

首先，XGBoost在GBDT的基础上，通过在目标函数中加入正则化项，减小模型的复杂度，避免过拟合。其目标函数为

![](images/651f7577d5b5f1a12329f2667df07dd2578e41569cfff66d0e880c74e246cff0.jpg)  
图1算法流程  
Fig.1Flow of algorithm

阶段1：基于协同过滤的内容召回。  
输入：用户历史交互记录。  
输出：部分用户的召回集。

算法步骤：

a)在训练集中提取每个用户点击的项目。

b）根据用户点击项目，计算用户之间的相似度。其相似度 $s$ 计算公式为

$$
S = \frac { n \big ( I _ { u _ { a } } \cap I _ { u _ { b } } \big ) } { \sqrt { n \big ( I _ { u _ { a } } \big ) \times n \big ( I _ { u _ { b } } \big ) } }
$$

其中： $I _ { u _ { \alpha } }$ 表示第 $\mathbf { \Delta } _ { a }$ 个用户的历史交互项目； $I _ { u _ { b } }$ 表示第 $b$ 个用户的历史交互项目； $n$ 表示项目的数量。

c）根据用户相似度，得到每个用户最相似的用户，然后将最相似用户已点击而该用户未点击的项目作为召回集，但因存在冷启动问题，该召回集仅为部分用户的召回集。

阶段2：XGBoost模型训练。输入：用户的历史交互记录，用户的特征数据，项目的特征数据。输出：XGBoost 模型。算法步骤：a)提取用户历史交互数据，将存在点击记录的项目视为1，不存在点击记录的项目视为0。b）对数据进行均衡化，使已点击项目和未点击项目的比例为1:1。c）提取用户的特征，并对特征进行预处理。对于文本型特征，将其转换为one-hot编码。对于时间戳型特征，截取前三位数字。对于数字型特征，需要进行离散化处理。d）使用XGBoost 进行模型训练，并对参数进行调整，得到最终模型。阶段3：产生推荐列表。输入：部分用户的召回集，原始候选集，XGBoost模型。输出：推荐列表。算法步骤：a）使用 XGBoost 模型对部分用户的召回集进行预测，将预测值大于阈值的项目作为推荐结果。b)若推荐结果小于10条，则使用XGBoost在原始候选集中进行预测，并将预测值大于阈值的项目作为推荐结果。c）对于存在冷启动问题的用户，则将此类用户在原始候选集中进行预测，并得到推荐结果。d)将所有推荐结果进行去重处理，对于历史交互记录已存在项目，不再向用户进行推荐。e）为每个用户提取推荐结果中的前10条作为推荐列表，将结果投放到线上环境进行推荐。

# 3 实验结果与分析

# 3.1实验数据与评测

本实验采用的数据集是CCIR2018个性化推荐评测的在线评测数据集，该数据集来自知乎移动端的信息流推荐数据。该数据集包括用户信息、内容信息、用户与内容的历史交互信息。其中用户信息包括注册时间、性别、访问频率、关注、提问次数、回答次数、终端设备、所在地等相关信息，内容信息包括内容对应的问题id、是否匿名、否被推荐、媒体信息、赞同次数、评论次数、收藏次数等相关信息，用户与内容的历史交互包括内容展示的时间、用户点击的时间、用户搜索的时间等信息。知乎每天给出10000个用户的历史交互信息数据以及相关用户、内容的信息数据，同时给出候选集，在候选集中为每个用户分别选择10条内容作为推荐结果从第二天凌晨开始将该结果投放到知乎线上环境进行评测。

# 3.2数据预处理

在数据集中，不同维度的特征具有不同的量纲，在特征选择中，需要对数据进行无量纲化处理。通过将不同维度的特征全部转换为数字表示的特征，特征之间才能够进行计算，最终得到目标函数。

在评测数据集中，特征类型有多种形式，不同类型的特征，数据处理方式不同，主要分为时间戳类型特征、文本类型特征、数字类型特征。在XGBoost模型训练时，需要对特征数据进行预处理。其处理方式如表1和2所示。

Table 1 Feature processing of user data   
表2内容数据特征处理  

<html><body><table><tr><td>特征名称</td><td>特征样例</td><td>处理方式</td><td>结果样例</td></tr><tr><td>注册时间</td><td>1540475871</td><td>截取前3位</td><td>154</td></tr><tr><td>性别</td><td>男、女</td><td>one-hot</td><td>01、10</td></tr><tr><td>访问频率</td><td>daily、weekly</td><td>one-hot</td><td>001、010</td></tr><tr><td>关注用户数</td><td>238、25</td><td>等频划分</td><td>3、1</td></tr><tr><td>关注话题数</td><td>128、36</td><td>等频划分</td><td>4、1</td></tr><tr><td>被评论数</td><td>63、655</td><td>等频划分</td><td>1、10</td></tr><tr><td>被点赞数</td><td>48、190</td><td>等频划分</td><td>1、4</td></tr><tr><td>注册类型</td><td>other</td><td>one-hot</td><td>00010000</td></tr><tr><td>注册平台</td><td>android</td><td>one-hot</td><td>00000100</td></tr><tr><td>是否用PC</td><td>0、1</td><td>不处理</td><td>0、1</td></tr><tr><td>设备model</td><td>Mi8</td><td>one-hot</td><td>00000100</td></tr><tr><td>用户平台</td><td>Xiaomi</td><td>one-hot</td><td>00100000</td></tr><tr><td>用户所在省</td><td>北京</td><td>one-hot</td><td>00001000</td></tr><tr><td>用户所在市</td><td>北京</td><td>one-hot</td><td>00100000</td></tr></table></body></html>

表1用户数据特征处理  
Table 2Feature processing of content data   

<html><body><table><tr><td>特征名称</td><td>特征样例</td><td>处理方式</td><td>结果样例</td></tr><tr><td>是否匿名</td><td>0、1</td><td>不处理</td><td>0、1</td></tr><tr><td>优质答案</td><td>0、1</td><td>不处理</td><td>0、1</td></tr><tr><td>是否推荐</td><td>0、1</td><td>不处理</td><td>0、1</td></tr><tr><td>创建时间</td><td>1540475871</td><td>截取前4位</td><td>1540</td></tr><tr><td>是否有图</td><td>0、1</td><td>不处理</td><td>0、1</td></tr><tr><td>感谢次数</td><td>63、655</td><td>等频划分</td><td>1、10</td></tr><tr><td>赞同次数</td><td>48、190</td><td>等频划分</td><td>1、4</td></tr><tr><td>搜藏次数</td><td>43、152</td><td>等频划分</td><td>1、4</td></tr><tr><td>反对次数</td><td>3、42</td><td>等频划分</td><td>1、5</td></tr><tr><td>举报次数</td><td>0、5</td><td>不处理</td><td>0、5</td></tr></table></body></html>

# 3.3评价指标

在推荐过程中，若推荐数量过少，将会导致推荐结果的偶然性，使其不具有说服力；若推荐数量过多，由于每个用户浏览的时间不同，展示的项目数量不同，为浏览时间较短的用户进行推荐的项目无法全部展示，其结果将会产生误差。因此在评测中，根据用户平均浏览数量，选择10条项目作为推荐结果。

在线评测的评价标准计算公式如下：

$$
\mathrm { s c o r e } = { \frac { N _ { c l i c k } } { N _ { o n l i n e } } }
$$

其中： $N _ { c l i c k }$ 是用户点击量； $N _ { o n l i n e }$ 是当天10000名用户的在线数量。同时在12d的推荐结果中选出最高的8d得分，然后计算平均分。

# 3.4 实验结果与分析

# 1）XGBoost参数调整

XGBoost模型的构造十分简单，但若提高模型的效果，则需要进行参数的调整。XGBoost模型为用户提供了多类参数，并且提供了便捷的CV函数供用户进行调参。在模型训练过程中，将用户的历史交互数据进行分割， $80 \%$ 作为训练集， $20 \%$ 作为测试集。然后使用CV函数得到最优参数。参

数如表3所示。

2）基于用户的协同过滤方法分析

在数据集中，用户浏览的每条内容都对应着多个话题类型，不同的浏览内容对应的话题可能相同，也可能不同。因此，在计算用户相似度时，既可以根据浏览的内容进行相似度的计算，又可以根据浏览内容所属的话题进行相似度计算。本实验分别使用基于内容的用户相似度和基于话题的用户相似度进行内容召回，然后使用相同的XGBoost模型进行计算，最后在知乎线上环境进行评测，其测试结果如表4所示。

Table 3Xgboost model parameters   

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>learning_rate</td><td>0.1</td></tr><tr><td>n_estimators</td><td>500</td></tr><tr><td>max_depth</td><td>11</td></tr><tr><td>min_child_weight</td><td>1</td></tr><tr><td>gamma</td><td>0</td></tr><tr><td>subsample</td><td>1</td></tr><tr><td>colsample_bytree</td><td>0.8</td></tr><tr><td>nthread</td><td>4</td></tr><tr><td>scale_pos_weight</td><td>1</td></tr><tr><td>seed</td><td>27</td></tr><tr><td>objective</td><td>binary:logistic</td></tr><tr><td>num_round</td><td>200</td></tr></table></body></html>

表4基于内容和基于话题的用户相似度对比

表3XGBoost模型参数  
Table 4Content-based and topic-based user similarity comparison   

<html><body><table><tr><td>相似度</td><td>阈值</td><td>得分</td><td>平均分</td></tr><tr><td>基于话题的用户相似度</td><td>0.3</td><td>1.78 1.757</td><td>1.7685</td></tr><tr><td>基于内容的用户相似度</td><td>0.1</td><td>1.827 1.916</td><td>1.8715</td></tr></table></body></html>

在实验过程中，基于话题的用户相似度计算的召回率更高，因此设置阈值为0.3，可以为大部分用户进行内容召回；基于内容的用户相似度计算的召回率较低，较小的阈值才可以为大部分用户进行内容的召回。使用同样的XGBoost模型进行预测，将预测结果推荐给用户。由结果显示，基于话题的用户相似度可以提高召回率，但同时会导致准确率降低。因此，基于内容的用户相似度在评测中得分更高，点击率也更高。

# 3）执行效率对比分析

在数据集中，若仅仅使用XGBoost算法，则需要在全部候选集中进行预测。当使用协同过滤进行粗粒度召回时，则可以减少模型的计算量。本实验通过使用XGBoost算法和融合协同过滤的XGBoost算法进行对比，当最大树深和迭代次数分别为5、50和11、200时，模型准确率最高。实验结果如图2所示。

由图2的评测结果显示，在全部候选集中进行预测，将会消耗大量的时间，融合协同过滤的XGBoost算法，由于协同过滤的召回，减少了模型的计算量，提高了模型的执行效率。

# 4）模型效果对比分析

由式（2）可知，基于话题的用户相似度与基于内容的用户相似度相比，后者具有更好的推荐效果。使用式（1）（2)得到的结论，然后使用协同过滤、XGBoost算法、协同过滤与XGBoost相融合的三种算法分别进行内容推荐，其在线上的评测结果如图3所示。

200 156 ■max_depth=5 160 num_round=50 (rihniiirg 122 ■max_depth=11 120 num_round=200 80 51 39 40 0 XGBoost UserCF+XGBoost model

![](images/42d66fe8d1ba54a0ec851989c4af51d1a02011cd8c8b2c35c6d33f9b4f4384ab.jpg)  
Fig.2Comparison of execution efficiency   
图3模型融合结果对比  
Fig.3Comparison of model fusion results

模型融合结果对比如图3所示。由图3的评测结果显示，融合协同过滤的XGBoost推荐算法具有更高的点击率，能够提供更好的推荐效果。在实验过程中，由于协同过滤具有冷启动问题，部分用户的历史交互记录很少甚至没有，所以无法为这部分用户进行推荐。而对于XGBoost推荐算法，其需要对全部候选集进行计算，从而导致计算量的增加，耗时增多；同时候选集内容过多也会导致准确率的降低。融合协同过滤算法可以增加准确率，降低计算量，XGBoost算法可以解决协同过滤的冷启动问题，同时可以增加准确率，因此模型融合的效果比单个模型的效果更好。

# 5）评测结果对比分析

本次评测总共进行12次结果提交，选出8次评测最高分，计算出平均分作为最终结果。部分获奖选手的最终成绩如图4所示。

![](images/5e1da1afc1a57a87d143284faac5ba7fad26a7ee0a61541181444531bbdf9375.jpg)  
图2执行效率对比  
图4部分获奖用户评测得分  
Fig.4.Evaluation score of partial award-winning users

由图4的评测结果显示，与基于会话的推荐算法和基于Skip-gram推荐算法相比，融合协同过滤的XGBoost推荐算法具有较好的推荐效果；与基于项目嵌入的推荐算法相比，推荐效果略差一些。在线上评测环境中，不同选手分配的推荐用户群体不同，在评测得分上存在不确定因素，同时在12d 的评测中，模型或者参数的调整也会直接影响最终的评测得分。但是真实的线上评测环境能够直接反映模型的推荐效果，与使用离线数据集相比，其结果更具有参考价值。

# 4 结束语

本文主要针对推荐系统中用户的冷启动问题进行改进，将协同过滤算法和XGBoost算法进行融合，首先使用协同过滤方法进行内容的粗粒度召回，然后使用XGBoost算法进行精确召回。本算法解决了用户冷启动问题，提高了模型的执行效率，提升了模型的预测能力，能够为用户准确推荐项目。同时，本文也存在不足之处，在模型的训练过程中未使用用户历史交互的时间序列特征。因此，下一步的工作将在模型中加入用户历史交互的时间序列特征，使模型达到更优的推荐效果。

# 参考文献：

[1]Marz N,Warren J.Big data:principles and best practices of scalable realtime data systems [M]//Greenwich:Manning.2015.   
[2]Yang Bo,Lei Yu,Liu Jiming,et al. Social collaborative filtering by trust [J]. IEEE Trans on Pattern Analysis and Machine Intelligence, 2017,39 (8): 1633-1647.   
[3]Al-Shamri M Y H. Power coefficient as a similarity measure for memory-based collaborative recommender systems [J].Expert Systems with Applications,2014,41(13): 5680-5688.   
[4]庞海龙，赵辉，李万龙，等．融合协同过滤的线性回归推荐算法 [J/OL].计算机应用研究，2019(5):1-3.[2018-12-10].http:/www. arocmag.com/article/02-2019-05-004.html.(Pang Hailong,Zhao Hui, Li Wanlong,et al.Linear regression recommendation algorithm with collaborative filtering [J/OL].Application Research of Computers,2019 (5):1-3. [2018-12-10]. http://www.arocmag.com/article/02-2019-05- 004. html.)   
[5]Wang Zhiqiang,Liang Jiye,LiRu,et al.An approach to cold-start link prediction: establishing connections between non-topological and topological information [J]. IEEE Trans on Knowledge and Data Engineering,2016,28 (11): 2857-2870.   
[6] 陈克寒，韩盼盼，吴健.基于用户聚类的异构社交网络推荐算法 [J]. 计算机学报,2013,36 (2):349-359.(Chen Kehan,Han Panpan,Wu Jian. User clustering based social network recommendation [J].Chinese Journal of Computers,2013,36(2):349-359.)   
[7] 于洪，李俊华．一种解决新项目冷启动问题的推荐算法[J].软件学 报,2015,26 (6):1395-1408.(Yu Hong,Li Junhua.Algorithm to solve the cold-start problem in new item recommendations [J].Journal of Software,2015,26(6):1395-1408.)   
[8]Pereira AL V, Hruschka E R. Simultaneous co-clustering and learning to address the cold start problem in recommender systems [J]. Knowledge-Based Systems,2015,82:11-19.   
[9]Shambour Q,Lu Jie.An effective recommender system by unifying user and item trust information for B2B applications [J].Journal of Computer and System Sciences,2015,81(7): 1110-1126.   
[10] Kluver D,Ekstrand M D,Konstan JA.Rating-based collaborative filtering:algorithms and evaluation [M]// Social Information Access. Cham: Springer,2018: 344-390.   
[11] Park D H,Kim H K,Choi I Y,et al.A literature review and classification of recommender systems research [J]. Expert Systems with Applications,2012,39(11):10059-10072.   
[12] Torre E,Quaglio P,Denker M,et al.Synchronous spike patterns in macaque motor cortex during an instructed-delay reach-to-grasp task [J]. Journal of Neuroscience,2016,36 (32):8329-8340.   
[13] Pirlo G,Impedovo D.Cosine similarity for analysis and verification of static signatures [J].Iet Biometrics,2013,2(4): 151-158.   
[14] Chen Tianqi,Guestrin C.Xgboost: a scalable tree boosting system [C]// Proc of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.New York:ACM Press,2016: 785-794.   
[15]李航．统计学习方法[M]．北京：清华大学出版社，2012.(Li Hang. Statistical learning methods [M].Beijing: Tsinghua University,2012.）   
[16] Kleinberg J,Lakkaraju H, Leskovec J,et al.Human decisions and machine predictions [J].Nber Working Papers,2018,133(1): 237-293.