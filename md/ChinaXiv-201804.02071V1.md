# 融合协同过滤的线性回归推荐算法

庞海龙，赵辉，李万龙，马莹，崔岩(长春工业大学 计算机科学与工程学院，长春 130012)

摘要：针对传统协同过滤算法中存在数据稀疏问题，提出融合协同过滤的线性回归推荐算法。根据用户对项目的评分以及用户和项目自身特征，构建用户间和项目间相似矩阵。基于相似矩阵，选出用户和项目最近邻集合，分别通过基于用户和基于项目的协同过滤算法来预测用户已评分项目的评分，将预测评分与真实评分的差值作为特征，组合在一起生成新的训练数据。把新的训练数据作为线性回归模型的输入，根据训练好的模型预测未知评分，采用Top-N算法产生推荐列表。在MovieLens数据集上进行实验。实验结果表明，新算法的推荐准确性较传统协同过滤算法有显著提高。

关键词：线性回归；协同过滤；相似性；推荐算法 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.11.0732

# Linear regression recommendation algorithm with collaborative filtering

Pang Hailong, Zhao Hui†,Li Wanlong, Ma Ying, Cui Yan (CollegeofComputer Science&Engineering,Changchun UniversityofTechnology,Changchun l300l2,China)

Abstract:Thispaperproposedalinearregresionalgorithmto integratecollaborativefilteringbasedonthedatasparseinfluence ofthe traditionalcollaborative filteringalgorithm.Firstly,itbuiltsimilaritymatrixbetweentheuserandtheprojectbasedon the user'sratingoftheproject,as wellastheuserandtheproject'sowncharacteristics.Secondly,basedonthesmilaritymatrix, it selectedtheuserand project nearest neighborset.Itpredictedthe score that the users had gradedrespectivelybythe wayof collaborative filtering algorithms basedonthe userandthe project.Andit would take the diference between predicted scores andtheealscoresas featurestogenerate new trainingdataandregardthenewtrainingdataas theinputofthelinearregresion model.Finalyaccording tothetraining model,itcould predict teunknownsore,andusedtheTop-Nalgorithmtoeerate therecommended list.Itconductedthe experimenton the MovieLensdataset.The experimentalresult showsthatthe proposed accuracy of the new algorithm improves compared with the traditional collaborative filtering algorithm.

Key words: linear regression; collaborative filtering; similarity; recommendation algorithm

# 0 引言

随着互联网技术的飞速发展，各类信息瞬间暴增，导致严重的“信息过载”问题[1。一方面，从用户的角度来看，从海量的数据中获取自己感兴趣的信息变的越来越困难；另一方面，从服务提供商的角度来看，用户能够提供的有效信息少之又少，为他们提供个性化的需求变得愈加困难。推荐系统{2作为一种信息过滤技术，在解决上述问题中起到了举足轻重的作用。它根据用户偏好向用户推荐其可能感兴趣的项目(如音乐、电影、图书等)。

目前推荐系统应用最广泛的技术之一是协同过滤算法[3.4],其主要分为基于用户的协同过滤算法和基于项目的协同过滤算法。基于用户的协同过滤算法给用户推荐与其兴趣相似的其他用户感兴趣的项目；基于项目的协同过滤算法给用户推荐与其之前感兴趣的项目相似的项目[5]。这两种传统协同过滤算法都是先根据用户对项目的评分计算用户或项目之间的相似性，然后找出用户或项目的最近邻集合，最后根据Top-N算法产生推荐列表进行推荐。然而随着推荐系统中用户和项目的数量不断扩增，传统协同过滤算法面临着扩展性、数据稀疏等问题。其中，数据扩展性指随着数据量的增加，无法及时计算出相似用户或项目，导致推荐延误；数据稀疏性指用户一般只对很少的项目进行评分，数据量越大，评分信息显得越少，相似性计算不够准确，导致推荐准确度降低。

为了解决上述问题，文献[6\~8]通过矩阵分解降低维数，减少存储空间，降低计算复杂度,以解决数据扩展性问题。但是分解算法不仅丢失原始评分信息，而且还容易产生过拟合的现象。文献[9\~11]采用聚类技术，对用户或项目进行聚类，缩小相似性范围填充评分值，一定程度上缓解了数据稀疏性问题；但是忽略了用户兴趣的差异性，推荐精度难以保证。文献[16]通过统计用户或物品的评分频次建立线性回归模型，进而利用该模型对未知评分直接根据历史评分频次进行预测。本文提出一种融合协同过滤的线性回归推荐算法(linearregression recommendationalgorithmwith collaborative filtering，LRCF)。首先，将用户历史评分以及用户和项目自身特征融入到相似性计算中，根据相似性矩阵选出最近邻集合；其次，基于协同过滤算法预测用户已评分项目的评分，通过预测评分与真实评分的差值建立线性回归模型；最后，根据该模型预测未知评分，从整体上提高用户预测评分的准确性。

# 1 相关工作

# 1.1协同过滤算法

协同过滤算法的中心思想是在整个空间寻找用户或项目的前 $k$ 个最近邻，核心是计算相似性。相似性计算的常用方法有余弦相似性[12]、修正的余弦相似性[13]、皮尔逊相关系数[14]等。以基于项目的协同过滤算法为例，分别介绍三种相似性的计算公式、预测评分公式以及top-N算法推荐。

余弦相似性计算公式为

$$
s i m ( i , j ) = \frac { \sum _ { u \in U _ { i , j } } R _ { u , i } \bullet R _ { u , j } } { \sqrt { \sum _ { u \in U _ { i , j } } R _ { u , i } ^ { 2 } } \sqrt { \sum _ { u \in U _ { i , j } } R _ { u , j } ^ { 2 } } }
$$

其中： $i , j$ 分别表示整个项目空间的两个项目； $U _ { i , j }$ 表示对项目$i , j$ 评分过的用户集合； $\pmb { R } _ { u , i }$ 表示用户 $\boldsymbol { u }$ 对项目 $i$ 的评分； $\pmb { R } _ { u , j }$ 表示用户 $u$ 对项目 $j$ 的评分。

修正的余弦相似性计算公式为

$$
s i m ( i , j ) = \frac { \sum _ { { \boldsymbol { u } } \in { \cal U } _ { i , j } } ( R _ { { \boldsymbol { u } } , i } - \overline { { R _ { \boldsymbol { u } } } } ) ( R _ { { \boldsymbol { u } } , j } - \overline { { R _ { \boldsymbol { u } } } } ) } { \sqrt { \sum _ { { \boldsymbol { u } } \in U _ { i , j } } ( R _ { { \boldsymbol { u } } , i } - \overline { { R _ { \boldsymbol { u } } } } ) ^ { 2 } } \sqrt { \sum _ { { \boldsymbol { u } } \in U _ { i , j } } ( R _ { { \boldsymbol { u } } , j } - \overline { { R _ { \boldsymbol { u } } } } ) ^ { 2 } } }
$$

其中： $\overline { { R _ { u } } }$ 表示用户 $\mathbf { \Omega } _ { u }$ 对已评分项目的平均评分。

皮尔逊相关系数计算公式为

$$
s i m ( i , j ) = \frac { \sum _ { { \boldsymbol { u } } \in U _ { i , j } } ( R _ { { \boldsymbol { u } } , i } - \overline { { R _ { i } } } ) ( R _ { { \boldsymbol { u } } , j } - \overline { { R _ { j } } } ) } { \sqrt { \sum _ { { \boldsymbol { u } } \in U _ { i , j } } ( R _ { { \boldsymbol { u } } , i } - \overline { { R _ { i } } } ) ^ { 2 } } \sqrt { \sum _ { { \boldsymbol { u } } \in U _ { i , j } } ( R _ { { \boldsymbol { u } } , j } - \overline { { R _ { j } } } ) ^ { 2 } } }
$$

其中： $U _ { i , j }$ 表示对项目 $i$ 和 $j$ 共同评分过的所有用户集合； $\overline { { R _ { i } } }$ 表示对项目 $i$ 的平均评分； $\overline { { R _ { j } } }$ 表示对项目 $j$ 的平均评分。

预测评分公式为

$$
p _ { u , i } = \overline { { R } } _ { i } + \frac { \sum _ { i _ { k } \in I _ { n } } ( R _ { u , i _ { k } } - \overline { { R _ { i _ { k } } } } ) s i m ( i , i _ { k } ) } { \sum _ { i _ { k } \in I _ { n } } \vert s i m ( i , i _ { k } ) \vert }
$$

在所有项目中寻找与目标项目 $i$ 相似性最高的前 $k$ 个项目构成项目 $i$ 的最近邻 $I _ { n } = \{ i _ { 1 } , i _ { 2 } , . . . , i _ { k } \}$ 。在最近邻 $I _ { n }$ 确定以后，预测用户 $\boldsymbol { u }$ 对未评分项目 $i$ 的评分，如式(4)所示。

根据式(4)计算出所有未对项目i评分的用户的预测评分，记为一个集合 $c$ ，对集合 $c$ 按降序的方式排序，最后把排序靠前的 $N$ 个项目推荐给用户。

# 1.2 线性回归算法

线性回归[15,16]是根据给定的一系列特征，对给定特征和实际值之间的组合关系进行分析，并通过线性组合的方式来拟合真实值。模型表示形式如式（5）所示。

$$
h _ { \theta } ( x ) = \sum _ { i = 1 } ^ { m } \theta _ { i } x _ { i } = \theta ^ { T } x
$$

其中: $\mathbf { \nabla } _ { m }$ 表示特征个数； $h _ { \theta } ( x )$ 表示预测值； $\theta ^ { T }$ 表示参数向量;$x$ 表示特征向量。预测值与真实值之间存在一定的误差，这个误差服从高斯分布，最终误差损失函数表示形式如下：

$$
J ( \theta ) = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { m } ( h _ { \theta } ( x ^ { ( i ) } ) - y ^ { ( i ) } ) ^ { 2 }
$$

其中： $\boldsymbol { J } ( \boldsymbol { \theta } )$ 表示误差平方和； $\boldsymbol y ^ { ( i ) }$ 表示真实值。利用梯度下降法优化求解 $\boldsymbol { J } ( \boldsymbol { \theta } )$ ，求 $\boldsymbol { J } ( \boldsymbol { \theta } )$ 对参数 $\theta$ 的偏导，然后利用式(7)迭代更新参数 $\theta$ ,直到达到最大迭代次数，求得参数 $\theta$ 。

$$
\theta _ { j + 1 } ^ { ( i ) } = \theta _ { j } ^ { ( i ) } - \alpha \sum _ { i = 1 } ^ { m } ( h _ { \theta } ( x ^ { ( i ) } ) - y ^ { ( i ) } ) x _ { j } ^ { ( i ) }
$$

其中： $\theta _ { j } ^ { ( i ) }$ 表示特征向量 $\boldsymbol { x } ^ { ( i ) }$ 的第 $j$ 个参数； $\alpha$ 表示学习率； $\boldsymbol { x } _ { j } ^ { ( i ) }$   
表示特征向量 $\boldsymbol { x } ^ { ( i ) }$ 的第 $j$ 个值。

# 2 融合协同过滤的线性回归推荐算法构建

# 2.1问题定义

为了更好地描述本文提出的算法，现对用户集合、项目集合、用户特征矩阵、项目特征矩阵以及用户一项目评分矩阵进行符号化定义。

定义1 $\pmb { U }$ 表示用户集合，形式如下：

$$
U = \{ u _ { 1 } , u _ { 2 } , . . . , u _ { m } \}
$$

其中： $u _ { m }$ 表示第 $m$ 个用户。

定义2 $\boldsymbol { \mathsf { I } }$ 表示项目集合，形式如下：

$$
I = \{ i _ { 1 } , i _ { 2 } , . . . , i _ { n } \}
$$

其中： $i _ { n }$ 表示第 $n$ 个项目。

定义3UFeature表示用户特征矩阵，形式如下：  

<html><body><table><tr><td>用户</td><td>fi</td><td>f</td><td>f</td><td>·</td><td>fp</td></tr><tr><td>u1</td><td>uf1.1</td><td>uf1.2</td><td>uf13</td><td>：</td><td>uf1.p</td></tr><tr><td>u2</td><td>uf2,1</td><td>uf2.2</td><td>uf2.3</td><td>：</td><td>uf2.p</td></tr><tr><td></td><td>：</td><td>：</td><td>：</td><td></td><td>：</td></tr><tr><td>Um</td><td>ufm,1</td><td>ufm,2</td><td>ufm.3</td><td>…</td><td>ufm.p</td></tr></table></body></html>

其中： $u f _ { m , P }$ 表示用户 $u _ { m }$ 的第 $p$ 个特征。

定义4IFeature表示项目特征矩阵，形式如下：  

<html><body><table><tr><td>项目</td><td>fi</td><td>f</td><td>f</td><td></td><td>fp</td></tr><tr><td>i</td><td>if1,1</td><td>if1,2</td><td>if1.3</td><td>：</td><td>if.q</td></tr><tr><td>i</td><td>if2.1</td><td>if2.2</td><td>if2.3</td><td></td><td>if2.q</td></tr><tr><td></td><td>：</td><td>：</td><td>：</td><td></td><td></td></tr><tr><td>in</td><td>ifn.1</td><td>ifn.2</td><td>ifn.3</td><td></td><td>ifnq</td></tr></table></body></html>

其中：ifn,q表示项目 $i _ { n }$ 的第 $q$ 个特征。

定义5 $R$ 表示用户-项目评分矩阵，形式如下：  

<html><body><table><tr><td>用户</td><td>i</td><td>i2</td><td>i</td><td></td><td>in</td></tr><tr><td>u1</td><td>R11</td><td>R1.2</td><td>R1.3</td><td>：</td><td>R1n</td></tr><tr><td>u2</td><td>R2,1</td><td>R2.2</td><td>R2,3</td><td>：</td><td>R2,n</td></tr><tr><td></td><td></td><td>：</td><td>：</td><td></td><td></td></tr><tr><td>Um</td><td>Rm,1</td><td>Rm.2</td><td>Rm,3</td><td></td><td>Rm.n</td></tr></table></body></html>

其中： $R _ { m , n }$ 表示用户 $u _ { m }$ 对项目 $i _ { n }$ 的评分值。

# 2.2算法构建

算法构建分为生成训练数据集和产生推荐列表两个阶段。

阶段1：生成训练数据集，流程如图1所示。输入、输出、算法步骤如下：

输入：预处理后的用户特征矩阵UFeature，预处理后的项目特征矩阵IFeature，用户一项目评分矩阵 $\pmb { R }$ ，用户集合 $\boldsymbol { \mathbf { \mathit { v } } }$ ，项目集合 $\boldsymbol { { \cal I } }$ ，最近邻数 $\pmb { k }$ 。

输出：训练数据。

算法步骤：

a)在 $\pmb { R }$ 中找出用户 $\boldsymbol { u }$ 已评分的项目集合$I _ { u } = \{ i \vert i \in I , R _ { u , i } \neq \emptyset \}$ 和对项目 $i$ 评分过的用户集合$U _ { i } = \{ u \vert u \in U , R _ { u , i } \neq \emptyset \}$ 。

b)根据 $I _ { \ u { u } } \setminus U _ { \ u { i } }$ 分别生成两两项目对集合$i p a i r s = \{ < i _ { a } , i _ { b } > | i _ { a } , i _ { b } \in I _ { u } \}$ 和用户对集合$u p a i r s = \{ < u _ { a } , u _ { b } > \mid u _ { a } , u _ { b } \in U _ { i } \} \ \mathrm { ~ . ~ }$

c)对于ipairs 中的每一对 $< i _ { a } , i _ { b } >$ 在IFeature 中找出 $i _ { \phantom { a } a }$ 和 $i _ { _ { b } }$ 对应的行，利用式(2)计算相似性 $s i m ( i _ { a } , i _ { b } )$ ;同样的方式利用式(3)计算upairs 中每一对 $< u _ { a } , u _ { b } >$ 的相似性 $s i m ( u _ { a } , u _ { b } )$ 。

d)循环执行a)b)c),得到每个用户和每个项目的相似性，分别构建用户相似性矩阵 $u s i m ( m , m )$ 和项目相似性矩阵 $i s i m ( n , n )$ 。

e)在 $\pmb { R }$ 上计算每一个用户在 $u s i m$ 的相似性，取相似性最高的前k个用户构成用户最近邻集合N"={{u,u,,uk}|u∈usim}并保存；同理，计算每一个项目在 $i s i m$ 的相似性，取相似性最高的前k个项目构成项目最近邻集合N={i,i,,k}i∈isim}并保存。

f)遍历 $\pmb { R }$ ，选择项目 $i$ 对应的最近邻集合 $N _ { i }$ ，根据式(4)计算用户 $u$ 对项目 $i$ 的预测评分 $\boldsymbol { p } _ { \ u , i } ^ { i }$ ，将 $p _ { \ u , i } ^ { i }$ 与 $R _ { u , i }$ 的差值记为 $x _ { 1 } ^ { i }$ ；同理，选择用户 $u$ 对应的最近邻集合 $\boldsymbol { N } _ { u }$ ，类比式(4)计算用户 $\mathrm { ~  ~ u ~ }$ 对项目i预测评分 $\boldsymbol { p ^ { u } } _ { u , i }$ ，将 $\boldsymbol { p ^ { u } } _ { u , i }$ 与 $R _ { u , i }$ 的差值记为 $x _ { 2 } ^ { u }$ ；最后将$x _ { 1 } ^ { i }$ 、 $x _ { 2 } ^ { u } \quad \cdot$ $R _ { u , i }$ 组成特征，构造新的数据集$d a t a = \{ \{ x _ { 2 } ^ { u } , x _ { 1 } ^ { i } , R _ { u , i } \} \vert i \in I , u \in U , R _ { u , i } \in R \}$ 并保存。

阶段2：产生推荐列表，流程如图2所示。输入、输出、算法步骤如下。

输入：训练数据，目标用户 $\mathbf { \Omega } _ { u }$ 。

输出：目标用户 $\boldsymbol { u }$ 的推荐列表。

算法步骤：

a)将训练数据的前两列作为线性回归模型的输入参数

$X = \{ x _ { 1 } , x _ { 2 } \}$ ，最后一列作为样本标签 $Y = \{ y _ { u , i } \}$ 。

b)根据式(5)(6)建立线性回归模型，利用梯度下降法优化求解下边损失函数 $J ( \theta ) \ , J ( \theta ) = \frac { 1 } { 2 } \mathrm { { \sum _ { \it { j = 1 } } ^ { \mathrm { 2 } } } } ( \theta ^ { T } x _ { j } - y _ { u , i } ) ^ { 2 } \ \mathrm { { \sigma } } _ { \mathrm { { } } }$

c)求损失函数 $\boldsymbol { J } ( \boldsymbol { \theta } )$ 对参数 $\theta$ 的偏导，然后利用式(7)迭代更新参数 $\theta$ ，直到达到最大迭代次数，将求得的参数 $\theta$ ，带入式(5)，得到LRCF模型。

d)根据LRCF预测目标用户 $\boldsymbol { u }$ 对未评分项目的评分，使用top- $. \mathrm { \Delta N }$ 算法生成推荐列表。

构建用户特征矩阵UFeature，  
项目特征矩阵IFeature,  
用户—项目评分矩阵R  
?  
生成用户相似矩阵usim，  
项目相似矩阵isim  
√  
遍历R，分别基于用户、项目协同过滤算法  
预测用户 $\boldsymbol { u }$ 对项目的评分 ${ p ^ { u } } _ { u , i }$ ， $p _ { u , i } ^ { i }$ ，将 $p ^ { \boldsymbol { \mu } } { } _ { u , i }$ （204号  
与 $\cdot _ { \boldsymbol { R _ { u , \cdot } } }$ 差值、 $p _ { ~ u , i } ^ { i }$ 与 $R _ { u . }$ i差值、 $R _ { u , i }$ 作为新特征  
组合在一起形成新数据集data,  
即 $d a t a = \{ x _ { 2 } ^ { u } , x _ { 1 } ^ { i } , R _ { u , i } \}$

![](images/4db8d48df43a12ba5b33dea1dee42b40f9dcf8d691f617bd1e8455cdf48151b6.jpg)  
图1生成训练数据流程  
图2产生推荐列表流程

# 3 实验分析

# 3.1实验数据

本文采用的实验数据是由GroupLens提供的MovieLens100k数据集[17]。该数据集提供了用户特征数据集、电影特征数据集、用户评分数据集等。其中，用户特征数据集包含943条记录，每一条记录了用户id、年龄、性别、职业、邮编，如表1所示；电影特征数据集包含1682条记录，每一条记录了电影id、电影名、上映日期，IMDb上的网址，类别，如表2所示；评分数据集包含100000条评分记录，记录了943个用户对1682部电影的评分，每个用户至少对20部电影进行了评分，评分区间是1\~5，数值大小代表用户对电影的喜爱程度。评分数据集的稀疏度是 $1 - 1 0 0 0 0 0 / 9 4 3 ^ { * } 1 6 8 2 = 0 . 9 3 6 9 5$ 。实验数据集的各项基本特征如表3所示。实验中将数据集按照一定比例划分为训练集和测试集，其中 $80 \%$ 作为训练集， $20 \%$ 作为测试集。

表1用户特征示例  

<html><body><table><tr><td>用户id</td><td>1</td><td>2</td></tr><tr><td>年龄</td><td>24</td><td>53</td></tr><tr><td>性别</td><td>M</td><td>F</td></tr><tr><td>职业</td><td>technician</td><td>other</td></tr><tr><td>邮编</td><td>85711</td><td>94043</td></tr></table></body></html>

表2项目属性示例  

<html><body><table><tr><td>电影id</td><td>1</td></tr><tr><td>电影名</td><td>Toy Story</td></tr><tr><td>上映日期</td><td>01-Jan-1995</td></tr><tr><td rowspan="2">IMDb上的网址</td><td>http://us.imdb.com/M/title-</td></tr><tr><td>exact?Toy%20Story%20(1995)</td></tr><tr><td>类别</td><td>Animation|Children's|Comedy</td></tr></table></body></html>

表3实验数据统计信息  

<html><body><table><tr><td>用户数目(个)</td><td>943</td></tr><tr><td>项目数目(个)</td><td>1682</td></tr><tr><td>评分记录数(条)</td><td>100000</td></tr><tr><td>用户最大评分数(条)</td><td>685</td></tr><tr><td>用户最小评分数(条)</td><td>20</td></tr><tr><td>用户平均评分(分)</td><td>3.52986</td></tr><tr><td>稀疏度(%)</td><td>93.695%</td></tr></table></body></html>

# 3.2度量标准

本实验采用目前最常用的一种推荐质量度量标准，即均方根误差(root mean square error，RMSE)。RMSE 的值越小，推荐质量越好。RMSE定义如下：

$$
R M S E = \sqrt { \frac { \displaystyle \sum _ { u , i \in R _ { T e s t } } \left( R _ { u , i } - p _ { u , i } \right) ^ { 2 } } { N } }
$$

其中： $\mathrm { ~ N ~ }$ 表示测试集评分数据个数； $R _ { t e s t }$ 测试集评分数据集合；$R _ { u , i }$ 用户 $\boldsymbol { u }$ 对项目 $i$ 的真实打分； $p _ { u , i }$ 用户 $\mathrm { ~  ~ u ~ }$ 对项目i的预测打分。

# 3.3 实验结果及分析

考虑各个参数对本文算法的影响，本节先通过部分实验找到最优参数的设定，在最优参数确定的基础上对本文算法和传统协同过滤算法进行比较。本实验的用户相似性度量方法是皮尔逊相关系数，项目相似性度量方法是修正的余弦相似性和皮尔逊相关系数。

# 1）最近邻数分析

考察用户和项目最近邻数对本文算法(LRCF)推荐精度的影响。将最近邻数在5\~305 间变动，固定学习率 $\scriptstyle { \alpha = 0 . 0 1 }$ 。如图2所示，随着用户最近邻数k值的增加，LRCF的RMSE值减小，推荐准确率上升，用户最近邻数 $\mathbf { k }$ 取275时，LRCF的RMSE值达到最小，随后再增加 $\mathbf { k }$ 值，LRCF的RMSE值不在发生变化，推荐准确率保持不变；如图3所示，k值在5\~25间，LRCF的RMSE的值一直在减小，k值在25\~55间，RMSE的值一直在增大，随后再增加 $\mathbf { k }$ 值，LRCF的RMSE的值一直在减小，推荐准确率上升，项目最近邻数 $\mathbf { k }$ 取275时，LRCF的RMSE值达到最小，随后再增加 $\mathbf { k }$ 值，LRCF的RMSE值不在发生变化，推荐准确率保持不变。

# 2）学习率 $\alpha$ 分析

考察不同学习率 $\alpha$ 对本文算法的影响。将学习率 $\alpha$ 在0.001\~1间变动。如图4 所示，学习率 $\scriptstyle \alpha = 0 . 1$ 时，本文算法的RMSE 值到达最小，随后再增加 $\alpha$ 值，本文算法的RMSE 值不在发生变化。

因此，针对于LRCF分别设置用户最近邻 $k { = } 2 7 5$ 、项目最近邻 $k { = } 2 7 5$ 、学习率 $\scriptstyle \alpha = 0 . 1$ 进行后续实验。

![](images/427b00032faf7b6424998eeefc0cc9752629cbdd1a1fb0764189efaf61fbd2ab.jpg)  
图2用户最近邻数k对于均方根误差的影响

![](images/2d0bd17e8b1bc15438194200813a1068dddfe6cb416c2f4381a7c3a1a412bf31.jpg)  
图3项目最近邻数k对于均方根误差的影响

# 3）与传统协同过滤算法比较

将本文算法与userCF、itemCF作比较。如图5所示，本文提出的融合协同过滤的线性回归推荐算法具有最小的RMSE，由此可知本文提出的推荐算法准确性较传统协同过滤算法有显著提高。

![](images/710c59e60c0aa3dabd0b16d09c2a101fd9f05e3226aca4b282dac92b43b1f08f.jpg)  
图4学习率α对于均方根误差的影响

![](images/aba0f32c5a6585891bb4779e2b064edf42e9cbd7155cd50947ae91ee450ae4c7.jpg)  
图5不同算法对于均方根误差的影响

# 4 结束语

本文提出融合协同过滤的线性回归推荐算法，通过用户一项目评分矩阵以及用户特征和项目属性构建相似矩阵，准确计算用户和项目的最近邻集合，有效克服了因数据稀疏导致推荐精度不高的问题。同时，将传统协同过滤算法的预测已知评分与真实评分的差值作为特征，组合产生新的数据用于线性回归模型的训练，从整体上提高系统预测评分的准确性。下一步的工作将对新加入的用户特征和项目属性进行分析，以及如何发现并解决在训练过程中产生模型过拟合问题进行研究。

# 参考文献：

[1]Gouws RH,Tarp S.Information overload and data overload in lexicography [J].International Journal of Lexicography,2o17: ecw030.   
[2]Bouzid M,BonnefoyD,Lhuillier N,et al. Recommender system:US, WO//2010//005942[P].2010.   
[3]Patil V A,Ragha L. Comparing performance of collaborative filtering algorithms [Cl// Proc of International Conference on Communication, Information & Computing Technology. 2012: 1-6.   
[4]Al-Shamri M Y H. Power coefficient as a similarity measure for memorybased collaborative recommender systems [J]. Expert Systems with Applications,2014,41 (13): 5680-5688.   
[5]项亮．推荐系统实践[M].北京：人民邮电出版社,2012.   
[6] Ocepek U,Rugelj J，Bosnic Z. Improving matrix factorization recommendations for examples in cold start [J]. Expert Systems with Applications,2015,42 (19): 6784-6794.   
[7]Vozalis MG,Margaritis KG.Applying SVD on item-based filtering [C]// Proc of International Conference on Intelligent Systems Design and Applications.[S.1.]: IEEE Computer Society,2005: 464-469.   
[8]Vozalis M G, Margaritis K G. Using SVD and demographic data for the enhancement of generalized collaborative filtering [J]. Information Sciences, 2007,177 (15):3017-3037.   
[9]Gong S.A collaborative filtering recommendation algorithm based on user clustering and item clustering [J]. Journal ofSoftware,2010,5(7): 745-752.   
[10] Li W,He W.An improved collaborative filtering approach based on user ranking and item clustering[M]// Internet and Distributed Computing Systems. 2013: 134-144.   
[11] Zhang J,Lin Y,LinM,etal.Anefectivecollaborative filteringalgorithm based on user preference clustering [J]. Applied Intelligence,2O16,45 (2): 230-240.   
[12]Pirlo G,Impedovo D.Cosine similarity for analysis and verification of static signatures [J].Iet Biometrics,2013,2(4): 151-158.   
[13] He X,Luo Y.Mutual information based similarity measure for collaborative filtering[C]/ Proc of IEEE International Conference on Progress in Informatics and Computing. 2010: 1117-1121.   
[14]Alshamri MY H, Alashwal N H. Fuzzy-weighted similarity measures for memory-based collaborative recommender systems [J].Journal of Intelligent Learning Systems & Applications,2014,6(1): 1-10.   
[15]陈震，谢峰，冯喜伟，等．基于线性回归的推荐方法及系统， CN103942298A [P]. 2014.   
[16]王兆国，谢峰，关毅，等．一种基于线性回归的新型推荐方法[J]．智 能计算机与应用,2017,7(4):1-5.   
[17] GroupLens [EB/OL]. htp://www. grouplens. org/.