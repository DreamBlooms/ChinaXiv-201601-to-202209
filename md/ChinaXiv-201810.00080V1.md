# 基于用户偏好优化模型的推荐算法研究

邱宁佳aʰ，何壮‘，王 鹏a，李岩芳ä(长春理工大学a.计算机科学技术学院;b.计算机与信息技术研究所，长春130022)

摘要：传统的个性化推荐算法普遍存在数据稀疏性问题，影响了推荐的准确度。Slope one算法具有简单、高效等特点，但该算法只是根据用户一项目评分矩阵进行数据分析，对所有用户采用一致性的权重进行计算，忽视了用户对项目类型的喜好程度。针对上述问题进行了研究，提出LR-Slope one 算法。首先根据用户一项目评分矩阵和项目类型信息构建用户对项目类型的偏好矩阵；然后利用线性回归模型计算用户对每个类型的权重，采用随机梯度下降算法优化权重；最后结合 Slope one 算法预测评分，填充评分矩阵，提高推荐的质量。实验结果表明，所提算法提高了推荐的精度，有效缓解了稀疏性问题。

关键词：推荐算法；Slope one；用户偏好；评分预测 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.07.0433

# Recommendation algorithm based on user preference optimization model

Qiu Ningjiaa, b, He Zhuanga,Wang Penga, Li Yanfanga (a.SchoolofComputerScience&Technology,b.InstituteofComputer&InformationTechnology,ChangchunUniversityof Science& Technology,Changchun 130022,China)

Abstract:Traditional personalized recommendation algorithm generall sufers from the problem of data sparseness，which affects theaccuracyofrecommendation.The Slopeone algorithm is simpleand eficient,butthe algorithm isonly basedon theuser-projectscore matrixtoanalyzethedata,ignoringthetypecharacteristicsofthe projectand theuser'spreferencefor the typeoftheproject.Inorder to solve theabove problems,the LR-Slopeone algorithm is proposed.Firstly,theuser's preference matrix isconstructed based on user project score matrix and project type information.Secondly,theweight of each type is calculated by linear regression modelandoptimized byrandom gradient descending algorithm.Finally,thescoreis predictedcombined by Slopeone，and thescoring matrixis filled,which improves the qualityof recommendation. Experimental results show that the proposed algorithm improves theaccuracyof recommendation and aleviates data sparseness effectively.

Key words: recommendation algorithm; Slope one; user preferences; score prediction

# 0 引言

随着互联网的普及和电子商务的快速发展，用户和产品数量呈指数级增长，在众多的商品中，想要快速而准确地找到用户想要的商品或者期待的物品时，关键字搜索的结果只能获得简单的需求，无法满足用户的个性化需求，此时个性化推荐系统应运而生。推荐系统的核心便是推荐算法，主要通过计算用户或项目之间相似度，将用户感兴趣的内容或相似度较高的其他内容推荐给最终用户[1]。由于项目评分数据稀少，导致预测不准确的情况，数据稀疏性问题一直是影响推荐质量的重要原因之一[2]。

针对数据稀疏性，许多学者提出基于降维技术的稀疏性问题解决方法，如主成分分析[3]/奇异值分解[4.5]、 $\mathrm { N M F } ^ { [ 6 . 7 ] }$ 。杜茂康等人[8]首先对用户已经评论过的数据进行聚类，然后结合Slopeone 算法来对未评分项目进行预测填充；张俊等人[9提出引入专家信任度的概念对用户未评分项目进行评分预测填充；郭娣等人[10]利用流行度降维的混合推荐方法对对数据矩阵进行精简；赵长伟等人[1提出了一种混合显式属性与隐式属性的矩阵分解算法，使用显式属性的相关性对因子矩阵进行约束，能够抑制稀疏数据矩阵分解中过拟合的问题,提高推荐精度；潘骏驰等人[12]引入用户可信度的概念,提出一种改进的奇异值分解算法，算法同时考虑了用户的信任信息、被信任信息以及各自的隐性反馈，有效提高了推荐准确度；李倩等人[13]提出基于谱聚类与多因子融合的协同过滤推荐算法，将FCM聚类融入到谱聚类算法的关键步骤，从而对相似度进行改进，提升了推荐性能；于阳等人[14]提出了一种基于熵优化近邻选择的协同过滤推荐算法，使用巴氏系数计算项目间相似性,并以此为权重加权计算用户间相似性，引入熵描述用户评分分布特性来衡量邻居用户的推荐贡献能力，最后利用双重准则共同计算推荐权重，并构建近邻集合，提升推荐准确度；周洋等人[15]提出一种基于栈式降噪自编码器的协同过滤算法，一定程度上解决了评分矩阵稀疏与项目之间没有共同用户评分就不能计算相似性的问题；刘林静等人[16提出一种基于用户相似性的加权Slope one 算法，首先筛选出活跃用户，据项目间相似性填充评分矩阵，有效地缓解了数据稀疏性问题。

上述方法在一定程度上缓解了数据稀疏性的问题，但是存在算法的计算复杂度较高，在数据量庞大和更新的速率比较快的情况下，不能有效地解决实时推荐的问题。Slopeone 算法是Lemire 等人[17]提出的一种协同过滤推荐算法，该算法具有简单、高效、推荐精确，在实时推荐上具有优势等优点。但是冷启动和数据稀疏等问题制约了其发展。

针对Slopeone 算法没有考虑项目本身类型特征，仅仅使用用户的评分作为推荐数据基础依据等问题，本文通过用户对类型的喜爱程度构建用户一类型偏好矩阵获得用户对类型的权重，对每个用户评分采用优化后的权值进行调整，使预测评分更精确，补全用户一评分矩阵，从而缓解数据稀疏性问题。

# 1 改进的Slope one个性化推荐算法

# 1.1问题描述

传统的协同过滤推荐算法一般流程主要分为四个部分：

a)构建用户一项目评分矩阵 $R _ { \mathfrak { m } * n }$ 。用户对项目的历史评分数据在很大程度上反映了用户对项目的喜爱程度，是协同过滤算法的基础数据依据，通常用用户一项目这种评分矩阵来表示。

b)获得用户或项目的相似邻居。依据评分矩阵 $R _ { \mathfrak { m } * n }$ ，通过不同的算法计算用户对其他用户或者项目对其他项目之间的相似度，选择最靠前的 $K$ 个用户或者项目组成近邻集合。

c)预测项目的评分。当前用户对目标项目的评分需要依据和它近邻集合的项目评分来计算它的预测评分。

d)生成 $T o p - N$ 推荐列表。把目标用户对不同项目的预测评分值，选取靠前的 $N$ 个项目，组成推荐列表，作为最终的结果推荐给目标用户。

用户一项目评分矩阵如表1所示。

表1用户—项目评分矩阵  

<html><body><table><tr><td>User</td><td>1</td><td>J</td><td>K</td><td>M</td></tr><tr><td>A</td><td>3</td><td>4</td><td>-</td><td>5</td></tr><tr><td>B</td><td></td><td>-</td><td></td><td>4</td></tr><tr><td>C</td><td>4</td><td></td><td></td><td>5</td></tr></table></body></html>

表中 ${ } _ { A , B , C }$ 表示用户， $I , J , K , M$ 代表项目；评分值为 $\{ 0 { - } 5 \}$ ，

‘-’代表没有评分，5代表最高分。可以看出这个评分矩阵是一个稀疏矩阵，根据这个稀疏矩阵进行预测评分来进行推荐，显然推荐的精准性不高。

# 1.2Slope one 推荐算法

Slope one 算法是基于Item-Based 的协同过滤推荐算法，基本思想是利用用户的历史评分数据和偏好的平均值来预测用户对新物品的偏好值，其原理是两个物品的偏好值之间存在某种线性关系，可以由物品 $\mathbf { x }$ 的偏好值估算出用户对新物品的偏好值，从而计算两两物品之间的平均偏好值成为计算关键。

Slope one 算法主要步骤如下：

a)计算同时被评分的两两物品之间的评分差的均值，记为 物品间的评分偏差。

$$
P _ { ( i j ) } = \frac { \displaystyle \sum _ { u \in N _ { i } \cap N _ { j } } \left( r _ { u i } - r _ { u j } \right) } { \displaystyle \left| N _ { i } \cap N _ { j } \right| }
$$

其中： $r _ { u i }$ 是用户 $\mathrm { ~ u ~ }$ 对物品i的评分； $r _ { u j }$ 是用户 $\mathrm { ~ u ~ }$ 对物品j的评分； $N _ { i }$ 是对物品i评过分的用户；而 $N _ { i } \cap N _ { j }$ 是对物品i和物品j都评过分的用户； $\left| N _ { i } \cap N _ { j } \right|$ 是对物品i和j都评过分的用户集合。

b)根据物品间的评分偏差和用户的历史评分，预测用户对未评分的物品的评分。

$$
P _ { ( u j ) } = \frac { \displaystyle \sum _ { i \in N u } \big | N _ { i } \bigcap N _ { j } \big | \big ( r _ { u i } - p _ { ( i j ) } \big ) } { \displaystyle \sum _ { i \in N u } \big | N _ { i } \bigcap N _ { j } \big | }
$$

其中： $\boldsymbol { N _ { u } }$ 是用户 $\mathbf { u }$ 评过分的项目集合。

c)将预测后的评分进行排序，取前 $\mathrm { ~  ~ N ~ }$ 个项目推荐给目标用户

# 1.3用户类型偏好矩阵的构建

传统的协同过滤推荐算法往往只是考虑了用户对项目的评分，本文认为项目的类型也一定程度影响用户的喜好，通过加入对项目类型因素作为参考，能够获得更好的预测精度。考虑用户对不同类型电影的喜好程度不同，通过对用户所评价过的类型数量、项目数量进行统计，获得用户对每个类型的偏好评分 $P H Z$ 和项目的平均评分 $P J F$ ，构建用户一类”偏好矩阵，作为后续模型的数据基础。其公式如下：

$$
P H Z = \frac { \displaystyle \sum _ { i \in I _ { u , x } } Z _ { u , i } } { n u m { \left( I _ { u , x } \right) } }
$$

$$
\scriptstyle P J F = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } Z _ { u , i } } { n } }
$$

其中： $I _ { u , x }$ 表示用户 $\boldsymbol { u }$ 所评价过的项目含有 $x$ 个类型的集合；$Z _ { u , i }$ 表示用户 $\mathbf { \Omega } _ { u }$ 对项目 $i$ 的真实历史评分； $n u m \big ( I _ { u , x } \big )$ 表示 $I _ { u , x }$ 集合中元素的个数； $n$ 表示用户看过的电影的个数。通常把矩阵中没有评分的项目设为0，即

$Y _ { i , j } = \binom { r _ { i , j } } { 0 }$ ，用户对项目有评分用户讨项目没有评分

表2用户—项目评分矩阵S  

<html><body><table><tr><td>用户</td><td>1</td><td>1</td><td>1</td></tr><tr><td>U</td><td>3</td><td>4</td><td>4</td></tr><tr><td>U</td><td>0</td><td>2</td><td>0</td></tr><tr><td>U</td><td>4</td><td>0</td><td>3</td></tr></table></body></html>

在类型矩阵中，如果项目中的类型，存在于矩阵中，就设为1，反之为0，即

$$
P _ { j , x } = \{ { \stackrel { \mathrm { 1 , \overleftrightarrow { j } } } { \mathrm { 0 , \overleftrightarrow { j } } } } \operatorname { E j } { \widehat { \underset { \mathrm { 1 } } { \right. } } } { \overleftrightarrow { \underset { \mathrm { E } } { \right. } } } { \stackrel { \mathrm { 2 } } { \underbrace { \ast } } } { \stackrel { \mathrm { 2 } } { \underset { \mathrm { 1 } } { \left. } } } { \underset { \mathrm { 2 } } { \left. } }
$$

表3项目类型信息矩阵 $C$   

<html><body><table><tr><td>项目</td><td>类型Ta</td><td>类型Tb</td><td>类型T</td><td>类型Td</td></tr><tr><td>1</td><td>1</td><td>1</td><td>1</td><td>0</td></tr><tr><td>1</td><td>0</td><td>1</td><td>1</td><td>1</td></tr><tr><td>1</td><td>1</td><td>1</td><td>0</td><td>0</td></tr></table></body></html>

用户一类型偏好矩阵 $T$ 构建的具体步骤如下：

a)根据式(5)，将用户一项目评分矩阵 $s$ 中未评分的项目设为0，如表2所示。b)根据式(6)，对项目类型信息进行统计，获得项目类型信息矩阵 $c$ ，如表3所示。c)根据式(3)和 (4)，得到用户对每个类型的偏好评分PHZ 和用户评过分项目的平均评分PJF，构建用户用户一类型偏好矩阵 $T$ ，如表4所示。

表4用户-类型偏好矩阵 $T$   

<html><body><table><tr><td>用户</td><td>类型Ta</td><td>类型Tb</td><td>类型Te</td><td>类型Td</td><td>评分</td></tr><tr><td>U</td><td>3.5</td><td>3.67</td><td>3.5</td><td>4</td><td>3.67</td></tr><tr><td>U</td><td>0</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>U3</td><td>3.5</td><td>3.5</td><td>4</td><td>0</td><td>3.5</td></tr></table></body></html>

# 1.4预测评分改进方案

Slope one 算法具有简单、高效、推荐精确等优点，但数据稀疏性等问题依然存在。由于Slope one 算法在计算时仅仅使用用户的项目评分与目标项目之间的平均评分偏差，没有考虑用户对项目类型的喜好，所以在预测目标项目评分的过程中，极有可能将目标项目不相关的项目纳入项目集合中进行计算，从而使得计算结果偏差较大，导致推荐精度不高。因此本文提出了LR-Slopeone 算法，充分考虑了用户对项目类型的喜好程度，构建用户一类型偏好矩阵，使用类型的偏好值作为后续模型操作的参数，利用线性回归模型获得类型权重，使用随机梯度下降对权值进行优化。改进后的偏差 $L R d e \nu _ { i , j }$ 公式如下：

$$
{ L R d e } \nu _ { i , j } = \frac { { \displaystyle \sum _ { i \in { R _ { j , i } } } } \left( \frac { { \vec { \omega } } ^ { j } r _ { u , j } } { n u m \left( { \vec { \omega } } ^ { j } \right) } - \frac { { \vec { \omega } } ^ { i } r _ { u , i } } { n u m \left( { \vec { \omega } } ^ { i } \right) } \right) } { n u m \left( R _ { j , i } \right) }
$$

其中： $L R d e \nu _ { i , j }$ 表示项目 $j$ 与 $i$ 之间的偏差； $R _ { j . i }$ 表示对项目 $i$ 与（204 $j$ 都评过分的用户集合； $r _ { u , i }$ 和 $r _ { u , j }$ 分别表示用户 $\boldsymbol { u }$ 对项目 $i \setminus j$ （204号的评分； $I _ { { \bf \Pi } _ { j } }$ 表示与目标项目 $j$ 同时被评分的项目集合； $\vec { \omega } ^ { i } \cdot \vec { \omega } ^ { j }$ 分别是项目 $i \setminus j$ 的项目权重；num（)表示集合中元素的个数。通过对每个项目评分分别考虑项目类型的偏好影响，结合Slopeone 算法，预测项目评分，补全用户一评分矩阵，使预测结果更为准确，并且缓解评分数据稀疏性问题。改进后的预测评分$G u _ { j }$ 公式如下：

$$
G u _ { j } = \frac { \displaystyle \sum _ { i \in I _ { j } } \left( L R d e \nu _ { j , i } + r _ { u , i } \right) } { n u m \left( I _ { j } \right) }
$$

具体描述如算法1所示。

算法1 LR-Slope one 算法

输入：用户-项目评分数据集S，权重 $\vec { \omega }$ ，偏好矩阵 $T$ ，样本数  
目 $n$ ， $F$ 为 $j$ 评过分的其他项目集合。  
输出：目标项目的预测评分Guj。for each Sif $j \neq \emptyset \cup j \in j \cap S$ return 用户集 $R$ （204号if $F \neq \varnothing \cup F \in F \bigcap R$ return 项目集1end forfor each T通过公式（8）获得权重 $\vec { \omega }$ （204号for $\mathrm { i } { = } 1$ to $n$ （204号根据算法2，对权重 $\vec { \omega }$ 进行优化end forend forfor each S计算 $n u m \big ( \vec { \omega } ^ { j } \big ) , n u m \big ( \vec { \omega } ^ { i } \big )$ 根据式（7）得到项目之间的偏差 LRdevi,jend for输出式（8）得到预测的项目评分 $G u _ { j }$

# 2 融合用户兴趣偏好的推荐优化算法

# 2.1 偏好模型优化

本文利用用户一类型矩阵构建偏好模型。该模型的一般形式为 $y = \vec { \omega } x$ ，其中 $\vec { \omega } = \left( \omega _ { 0 } , \omega _ { 1 } , \omega _ { 2 } . . . \omega _ { n } \right) ^ { T }$ ， $\mathbf { \Psi } _ { X } = \left( x _ { 0 } , x _ { 1 } , x _ { 2 } . . . x _ { n } \right) ^ { T }$ 口给定参数 $\vec { \omega }$ ，就能得到样本的预测值。预测值与样本的实际评分值存在偏差 $H ( \vec { \omega } )$ ：

$$
H \left( \vec { \omega } \right) = \sum _ { i = 1 } ^ { n } \left( \stackrel { \wedge } { y ^ { ( i ) } } - y ^ { ( i ) } \right) ^ { 2 }
$$

其中： $y ^ { ( i ) }$ 为实际评分值； $\hat { \boldsymbol y ^ { ( i ) } }$ 为样本的预测值。本文使用梯度下降方法来度量偏好模型的优劣。优化方法如下：首先计算偏差的梯度 $\nabla H ( \vec { \omega } )$ ；然后沿着梯度方向更新学习率 $\alpha$ ；最后多次迭代执行上述操作，直至达到设定的损失函数收敛阈值 $A$ 时：目标函数 $H ( \vec { \omega } )$ 取最小， $\vec { \omega }$ 的取值即为最优权值 $\omega ^ { * }$ ，再把 $\omega ^ { * }$ 带回到模型中，替换 $\vec { \omega }$ ，得到最终的模型。根据每个项目类型的权值分量，获得目标项目的类型评分。具体的算法描述如算法2所示。

算法2偏好模型优化算法

输入：参数集 $x$ ，评分集 $y$ ,数据集S，偏好矩阵 $T$ ，样本数目 $\mathbf { \Omega } _ { n }$ ，样本的类型个数 $\mathbf { \Omega } _ { m }$ ，损失函数收敛阈值 $A$ 。

输出：项目类型权重 $\vec { \omega }$ 。  
while $T \neq \emptyset$ 偏好模型 $y = \vec { \omega } x$ for $\mathrm { i } { = } 1$ to n do:根据公式（9）得到 $H ( \vec { \omega } )$ for i=1 to A更新@=@-a\*VHif $\boldsymbol { H } ( \vec { \omega } ) = \boldsymbol { A }$ return $\vec { \omega }$ （204号end forend for  
end while  
输出项目类型权重 $\vec { \omega }$

# 2.2改进的推荐算法

数据稀疏性一直是推荐算法面临的问题，补全评分项目的缺失作为解决问题的方法之一，对最终的预测结果影响重大。本文结合用户对类型的喜好程度构建用户一类型偏好矩阵，应用线性回归模型，得到类型的权重，优化权值参数，结合LR-Slopeone 算法，对稀疏矩阵进行填充，利用填充后的数据集进行有效的推荐。由于对用户每个评分都加入类型偏好的考虑，推荐结果更加符合用户的喜好，更贴近用户自身的想法，使推荐质量更高。推荐算法整体解决方案如下：

a)首先遍历用户一项目评分数据集 $s$ ，得到类型集 $c$ 。b)根据类型集 $c$ ，统计用户对每个类型的观看次数 $_ { C S }$ 和该类型的总评分 $P F$ 。c)根据 $_ C S$ 和 $P F$ ，应用式（3）和（4）得到用户对每个项目类型的偏好评分 $P H Z$ 和用户所看过电影的平均分 $P J F$ 。d)通过数据集 $s$ 、PHZ 和 $P J F$ ，组成用户一类型偏好矩阵 $T$ 当做测试集。e)对矩阵 $T$ 根据偏好模型，使用算法2对模型进行优化，得到用户对每个类型的权重 $\vec { \omega }$ 。f)把目标项目的权重 $\vec { \omega }$ 带入算法1中，最终得到目标项目的预测评分 $G u _ { j }$ ，补全用户一项目评分矩阵S。

g)根据预测评分值，为目标用户生成推荐列表。

推荐算法整体流程如图1所示。

![](images/cb666025a58309007cdc8c0863db1ac59f7fa64b7e4d83ae15addb8c01beea0f.jpg)  
图1推荐算法整体流程

# 3 实验分析

# 3.1实验数据

本文实验的操作系统为Windows10，实验中的所有程序使用Python实现。采用MovieLens数据集作为实验的测试数据集[18]。它包含了9125部电影的100 004 评级和1296个标签应用，评分范围为 $1 { \sim } 5$ 分，分数越高说明用户对电影的喜爱程度越深。本文将所有的电影按流派划分到romance、musical、western、horror等19个类别当中，数据集的稀疏度为 $9 3 . 7 \%$ 。实验将随机选取全部数据集中 $80 \%$ 作为训练集对模型进行训练， $20 \%$ 作为测试集，对评分预测的精度，推荐的准确率进行交叉验证。

# 3.2 实验评测标准

本文使用平均绝对误差MAE以及准确率来衡量算法预测评分的准确性，并且验证了迭代的收敛性。MAE是推荐算法业界认可度高的评估推荐系统质量的方法，MAE的值越小，算法的预测精度越高；反之，则预测精度越差。MAE的公式如下：

$$
\ M A E = { \frac { \displaystyle \sum _ { i = 1 } ^ { C } \lvert P _ { i } - Q _ { i } \rvert } { C } }
$$

其中： $P _ { i }$ 表示项目 $i$ 的预测评分； $Q _ { i }$ 表示项目 $i$ 的真实评分； $c$   
表示测试集中用户对项目的评分个数。

准确率指标（precision）即判断推荐的项目列表中，目标用户已经为其打分的项目所占的比例，比例越高，推荐的质量越好。公式如下：

$$
p r e c i s i o n { = } \frac { \displaystyle \sum _ { u \in U } \mid R _ { u } \cap T _ { u } \mid } { \displaystyle \sum _ { u \in U } \mid R _ { u } \mid }
$$

其中： $R _ { u }$ 为用户 $\boldsymbol { u }$ 推荐 $R$ 个物品； $T _ { \phantom { } _ { u } }$ 为用户喜欢的物品集合。

# 3.3 实验结果与分析

实验1偏好优化模型实验。本文根据MovieLens数据集，分别统计用户观看次数、电影类型和用户所看电影的平均评分用来构建用户一类型偏好矩阵，如表5所示。

表5用户-类型偏好矩阵  

<html><body><table><tr><td rowspan="2">用户</td><td colspan="7">电影类型</td><td rowspan="2">评分</td></tr><tr><td>action</td><td>adventure</td><td>animation</td><td></td><td>thriller</td><td>war</td><td>drama</td></tr><tr><td>1</td><td>2.8</td><td>2.166</td><td>2.8</td><td></td><td>2.833</td><td>2</td><td>2.571</td><td>2.559</td></tr><tr><td>2</td><td>3.315</td><td>3.7</td><td>3.6666666</td><td></td><td>3.333</td><td>3.8</td><td>3.615</td><td>3.693</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>671</td><td>4</td><td>4.086</td><td>4.25</td><td></td><td>4.052</td><td>3.857</td><td>3.778</td><td>4.031</td></tr></table></body></html>

在构建偏好模型后，统计所有用户对每个类型的偏好权重，利用线性回归模型，采用梯度下降方法进行权值参数优化，迭代求得最优的权值。通过大量实验验证，损失函数收敛阈值设定为 $0 . 0 0 0 1$ ，学习率 $\alpha$ 设定为0.001时，通过多次迭代，能够得到比较合理的优化效果，最终得到优化后的权值如表6所示。

表6权值优化结果  

<html><body><table><tr><td>参数</td><td>优化后的权值</td><td>参数</td><td>优化后的权值</td></tr><tr><td>@</td><td>0.012</td><td>Q11</td><td>0.014</td></tr><tr><td></td><td>0.021</td><td>@12</td><td>0.006</td></tr><tr><td></td><td>0.106</td><td>@13</td><td>0.051</td></tr><tr><td>@4</td><td>0.014</td><td>@14</td><td>0.004</td></tr><tr><td>05</td><td>0.002</td><td>@15</td><td>0.225</td></tr><tr><td>@6</td><td>0.207</td><td>@16</td><td>0.005</td></tr><tr><td></td><td>0.006</td><td>@17</td><td>0.018</td></tr><tr><td>@8</td><td>0.001</td><td>Q18</td><td>0.107</td></tr><tr><td></td><td>0.015</td><td>@19</td><td>0.168</td></tr><tr><td>@10</td><td>0.018</td><td></td><td></td></tr></table></body></html>

根据表6把训练好的优化权值带回线性回归模型，计算用户一类型偏好矩阵的预测评分，对比每个用户的原始评分数据和模型优化后的预测评分数据，结果如图2所示。

![](images/4ed8135729a31c32a62e06f519fb9899e09a789baa8c7644fbc5de694b9d46e9.jpg)  
图2模型优化对比

从图2中可以看出，训练好的偏好优化模型的预测评分和原始用户的评分数据曲线贴近程度较高，有较好的拟合效果，并且随着用户数量的变化，训练模型得到的预测评分较好地反映了原始用户的评分趋势，为下一步使用本文提出的LR-Slopeone 算法对用户做推荐时提供可靠的依据。

实验2改进的预测评分算法验证。由于推荐算法是根据预测评分信息来补全用户一评分矩阵的，所以预测评分的好坏对推荐的质量有着直接的影响。本实验根据已知用户一类型偏好矩阵，随机选取六部电影进行评分预测。首先统计电影的类型为Action、Adventure、Drama、Sci-Fi、Thriller，其优化后的权重分别是 $\omega _ { \scriptscriptstyle 1 }$ 、 $\omega _ { 2 }$ 、 $\omega _ { \mathrm { s } }$ 、 $\omega _ { 1 6 }$ 、 $\omega _ { 1 7 }$ 。把权重带入到本文提出的 LR-Slope one 算法中，得到的预测评分和原始 Slope one 算法得到的预测评分与用户真实的评分对比，结果如表7所示。

表7预测评分对比  

<html><body><table><tr><td>电影ID</td><td>原始 Slope one 算法</td><td>LR-Slope one 算法</td><td>真实评分</td></tr><tr><td>31</td><td>2.5</td><td>2.124</td><td>2</td></tr><tr><td>1129</td><td>3.5</td><td>3.128</td><td>3</td></tr><tr><td>1263</td><td>3</td><td>4.121</td><td>4</td></tr><tr><td>1339</td><td>4.5</td><td>4.963</td><td>5</td></tr><tr><td>1343</td><td>4.5</td><td>3.981</td><td>4</td></tr><tr><td>1953</td><td>3.5</td><td>3.688</td><td>3</td></tr></table></body></html>

由表7可以看出，本文提出的LR-Slope one 算法的预测评

分比原始的 Slopeone 算法的预测评分对用户给出真实的电影评分更加接近，说明结合用户类型偏好信息的预测评分更加准确。

为了进一步验证预测评分算法的合理性，采用全部用户做实验验证，取不同数量集下原始Slopeone 算法与本文提出的LR-Slopeone 算法预测评分的MAE 效果对比，结果如图3所示。

![](images/7c8ed6831d1b14dd6309680af964a63def9fcdb7c2ceaa54cdbf9357644b789c.jpg)  
图3MAE对比

从图3中可以看出，原始Slope one 算法的误差在 $0 . 7 3 \mathrm { \sim } 0 . 8 2$ 间，本文提出的LR-Slope one 算法的误差在0.63\~0.72间，最高时误差降低了11个百分点，并且随着用户评分数据的增多，预测评分的 MAE 值更小。这是由于本文提出的LR-Slope one算法对每个评分都结合了用户类型偏好信息的分析，充分考虑了用户对每个类型的喜好程度，用户越多，结合类型偏好信息的预测评分效果越好，精准度越高。

实验3推荐效果验证。由于在实际应用中，用户的目的是想获得自己喜欢的电影推荐而不是仅仅知道对电影的评分状况，为了验证本文算法的推荐准确率，本文统计用户已经评过分的电影和评分较高的前10部电影的占比情况，计算不同的用户数量集下推荐的准确率，与原始的Slopeone 算法进行对比，结果如图4所示。

![](images/739b1c0d1c662108a448f32159f3ec2202d2f368bcd4bf35c67b9d37a950ae2c.jpg)  
图4准确率precision 对比

由图4可以看出，本文算法较原始Slopeone 算法的准确率最低提高了 $8 . 2 2 \%$ ，最高提高了 $1 3 . 9 2 \%$ ，说明本文提出的LR-Slopeone 准确率更高，推荐效果更好。由上述实验可知，本文提出的LR-Slopeone 算法的预测评分误差更小，推荐的准确率更高，可以显著地提高推荐系统的推荐质量。

实验4多数据集验证。为了验证本文提出的LR-Slope one算法在不同数据集上的效果，实验分别对 ml-100k.zip、ml-1m.zip、 $\mathrm { m l - l 0 m . z i p }$ 、 $\mathrm { m l } { - } 2 0 \mathrm { m }$ .zip 这四个不同的数据包应用本文提出的算法和原始Slopeone算法进行比较，实验结果如表8所示。

表8多种数据集MAE对比  

<html><body><table><tr><td>数据集</td><td>原始 Slope one 算法</td><td>LR-Slope one 算法</td></tr><tr><td>ml-100k</td><td>0.748</td><td>0.638</td></tr><tr><td>ml-1m</td><td>0.776</td><td>0.625</td></tr><tr><td>ml-10m</td><td>0.815</td><td>0.616</td></tr><tr><td>ml-20m</td><td>0.873</td><td>0.609</td></tr></table></body></html>

由表8可以看出，随着数据集的增大，数据越来越稀疏，原始Slopeone 算法的误差越来越大，而本文提出的算法依然有较好的准确率。这是由于尽管随着数据集的变大、用户的数量增加、电影数目变大、评分数据变多、用户对相同电影打分数据变少等情况，但是电影的类型数目没有变化，用户对类型的喜好程度还是实际存在的，结合本文优化后偏好模型，在不同大小的数据集上预测精度都要高于原始的 Slope one 算法，所以本文提出的LR-Slope one 算法实用性更强。

# 4 结束语

针对推荐算法数据稀疏性问题，采用Slopeone 推荐算法。但由于该算法没有考虑用户对电影类型的喜好，采用了一致性权重计算，导致个性化推荐的准确度低。本文通过构建用户一类型偏好矩阵，结合线性回归模型，对类型权重进行优化并在后期评分预测时，充分考虑了用户对不同电影的喜好程度，对每个用户采用不同的类型权重进行计算。通过对偏好优化模型进行验证，能够获得较好的拟合效果，并且对算法的预测评分与真实评分作比对，LR-Slopeone 算法预测评分误差更小，更贴近真实评分。在最后的推荐效果上，本文算法也明显提升了推荐质量。通过上述实验结果表明，本文提出的LR-Slope one算法在推荐结果上要优于原始的Slope one 推荐算法，并且预测评分准确度高，有效地提高了推荐质量并缓解数据稀疏性。

# 参考文献：

[1]冷亚军，陆青，梁昌勇．基于结构相似性的协同过滤推荐算法[J]．小 型微型计算机系统，2015,36(10):2266-2269.(Leng Yajun,Lu Qing, Liang Changyong.Collaborative filtering recommendationalgorithm based on structure similarity[J].Journal of Chinese Computer Systems,2015,36 (10): 2266-2269.)

[2]Liu Limin,Zhang Pengxiang,Lin Le,et al.Research of data sparsity based on collaborative filtering algorithm [J].Applied Mechanics & Materials, 2013,462-463 (2013): 856-860.

[3]陈健美，孙亚军．基于用户近邻的N 维张量分解推荐算法[J].计算机 工程,2017,43(11):193-197.(Chen Jianmei,Sun Yajun.N dimensional tensor decomposition recommendation algorithm based on user ’ s neighbors [J]. Computer Engineering,2017,43 (11): 193-197.)

[4]王建芳，张朋飞，刘永利．基于改进带偏置概率矩阵分解算法的研究[J]．计算机应用研究，2017,34(5):1397-1400.(Wang Jianfang,Zhang

Pengfei,Liu Yongli.Research on improved bias probabilistic matrix factorization [J].Application Research of Computers,2017,34 (5): 1397-1400.)

[5]孙玲芳，冯遵倡，SunLingfang，等．基于特征加权张量分解的标签推荐 算法研究[J].江苏科技大学学报：自然科学版，2015,29(6):574-579. (Sun Lingfang,Feng Zunchang, SunLingfang,et al. Tag recommendation algorithm based on feature weighting and tensor decomposition [J]. Journal of Jiangsu University of Science and Technology: Natural Science Edition, 2015,29 (6): 574-579. )

[6]Wang Xiwei, Zhang Jun,Lin Pengpeng,et al. Incorporating auxiliary information incollaborative filtering data update with privacy preservation [J].International Journal of Advanced Computer Science & Applications,   
2014,5 (4): 224-235. [7]Luo Xin, Zhou Mengchu,Xia Yunni,et al.An eficient non-negative matrix-factorization-basedapproachtocollaborativefilteringfor recommender systems [J]. IEEE Trans on Industrial Informatics,2014,10 (2): 1273-1284. [8] 杜茂康，刘苗，李韶华，等．基于邻近项目的 SlopeOne 协同过滤算法 [J]．重庆邮电大学学报：自然科学版，2014，26（3）．：421-426.(Du Maokang,Liu Miao,Li Shaohua,et al. Slope one collaborative filtering recommendation algorithm based on neighbor[J]. Journal of Chongqing University of Posts and Telecommunications: Natural Science Edition,   
2014,26 (3): 421-426. ) [9] 张俊，刘满，彭维平，等．融合兴趣和评分的协同过滤推荐算法[J]. 小型微型计算机系统,2017,38(2):357-362.(ZhangJun,Liu Man,Peng Weiping,et al. Collaborative filtering recommendation algorithm based on fusion interest and score [J].Journal of Chinese Computer Systems,2017,   
38 (2): 357-362. ) [10]郭娣，赵海燕，侯景德，等．基于相似性传播和流行度降维的混合推荐 方法[J].小型微型计算机系统,2015,36(4):707-712.(Guo Di,Zhao Haiyan,Hou Jingde，et al.Hybrid recommendation via similarity propagation and dimension reduction based on popularity [J]. Journal of Chinese Computer Systems,2015,36 (4): 707-712.) [11]赵长伟，彭勤科，张志勇．混合因子矩阵分解推荐算法[J]．西安交通 大学学报,2016,50 (12):87-91.(Zhao Changwei,Peng Qinke,Zhang Zhiyong.A matrix factorization algorithm with hybrid implicit and explicit atributesforrecommender systems[J].Journal of Xi'an Jiaotong University,2016,50 (12): 87-91.) [12]潘骏驰，张兴明，汪欣．融合用户可信度的改进奇异值分解推荐算法 [J].小型微型计算机系统,2016,37(10):2171-2176.(Pan Junchi,Zhang Xingming，WangXin.Improvedsingularvaluedecomposition recommender algorithm based on user reliability[J].Journal of Chinese Computer Systems,2016,37(10): 2171-2176.) [13]李倩，李诗瑾，徐桂琼．基于谱聚类与多因子融合的协同过滤推荐算法 [J]．计算机应用研究,2017,34(10):2905-2908.(Li Qian,Li Shijin,Xu Guiqiong.Collaborative filtering recommendation algorithm based on

spectral clustering and fusion of multiple factors [J].Application Research of Computers,2017,34(10): 2905-2908.)

[14]于阳，于洪涛，黄瑞阳．基于熵优化近邻选择的协同过滤推荐算法[J]. 计算机应用研究,2017,34(9):2618-2623.(Yu Yang,Yu Hongtao,Huang Ruiyang.Collaborative filtering recommendation algorithm based on entropy optimization nearest-neighbor selection [J].Application Research of Computers,2017,34(9): 2618-2623.)

[15]周洋，陈家琪．基于栈式降噪自编码器的协同过滤算法[J].计算机应 用研究,2017,34(8): 2336-2339.(Zhou Yang,Lu Jiaqi. Stacked denoising autoencoder for collaborative filtering algorithm [J].Application Research ofComputers,2017,34(8):2336-2339.)

[16] 刘林静，楼文高，冯国珍．基于用户相似性的加权 Slope One 算法 [J]. 计算机应用研究，2016,33(9):2708-2711.(Liu Linjing,Lou Wengao, Feng Guozhen. New weighted Slope One algorithm based on user similarity [J].Application Research of Computers,2016，33(9): 2708-2711. )   
[17] Lemire D,Maclachlan A.Slope One predictors for online rating-based collaborative filtering [J]. Computer Science,2007: 21-23.   
[18]Harper F M,Konstan JA.The MovieLens datasets [J].ACM Trans on Interactive Intelligent Systems,2016,5(4):1-19.