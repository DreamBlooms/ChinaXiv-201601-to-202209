# 一种嵌入项目疲劳和多样偏好的聚合推荐算法

阙正昊，邓明通，刘学军，李斌(南京工业大学 计算机科学与技术学院，南京 211816)

摘要：为了解决推荐列表偏向于热门项目，多样性差的问题，提出了ARIFDP 算法（aggregation recommendationalgorithm for embedding item fatigue and diversity preference）。首先通过对用户历史反馈数据分析用户的多样性偏好，得出用户的多样倾向度，进而构造了与评价次数负相关的项目疲劳函数，最终将矩阵分解与项目疲劳函数相聚合，并加入多样倾向度调节项目疲劳函数所占权重，增加了冷门项目被推荐的概率。实验结果表明，ARIFDP 算法能在保证准确率的前提下有效提高推荐结果的多样性。

关键词：主题模型；矩阵分解；多样倾向度；项目疲劳函数；推荐多样性 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.04.0279

Aggregation recommendation algorithm for embedding item fatigue and diversity preference

Que Zhenghao, Deng Mingtong,Liu Xuejun, Li Bin (College ofComputer Science&Technology,Nanjing Tech University,Nanjing 211816,China)

Abstract:In order to solve the problem that therecommendation list is biased towards popular projectsand with poor diversity,this paper proposes the ARIFDP(An Aggregation Recommendation Algorithm for Embedding Item Fatigue and DiversityPreference)algorithm.First,theuser'sdiversity preferencesareanalyzedbyusingthe historicalfedbackdataof the user toderive theuser.Thedegreeof diversification;and thenconstructingaproject fatigue functionnegativelyrelated tothe numberof evaluations;eventuallythematrix decompositionandthe projectfatigue functionare aggregated,and theiclusion of various propensitydegrees adjusts the weightofthe fatigue functionoftheproject,and increases the probabilityof the proposed project.Experimental resultsshow that the ARIFDP algorithm can efectively improve the diversity of recommendation results on the premise of ensuring accuracy.

Key words: topic model; matrix factorization; diversity tendency; item fatigue function; recommendation diversity

# 0 引言

近年来，推荐系统已经成为电子商务网站或资料库网站中帮助其推广业务以及帮助用户寻找项目的必备工具。作为一个有效的解决信息过载问题的工具，推荐系统能够从巨大的项目池中给用户推荐符合其偏好的项目集合。

目前已有的推荐系统多注重准确性，如何提高多样性越来越成为推荐任务中的关键问题[I]。例如，当用户在电影资料库网站IMDB(http://www.imdb.com/title/tt3612032/)中搜索电影《致命弯道》后，所有关于《致命弯道》系列的电影都会被推荐，如图1所示。从准确性的角度，推荐列表是令人满意的，因为目标用户喜欢《致命弯道》。然而，由于推荐结果缺乏多样性，不利于拓宽用户的视野，从而让用户感到厌烦。事实上，拓宽用户的视野已经成为推荐系统的重要特性之一错误!未找到引用源。一个能够开拓用户视野的系统可以获得一个双赢的结果：用户可以找到更多的有趣的项目，网站经营者可以增加他们的销售额，提高用户满意度。本文通过对用户的历史反馈信息分析得出用户的多样倾向度，将用户的历史反馈信息和项目的主题分布使用矩阵分解得到用户对项目的初始偏好得分，进而通过项目疲劳函数调整偏好得分，并加入多样倾向度调节项目疲劳函数所占比重，从而向用户推荐既具有多样性，同时也不失准确性的一组推荐列表。

# 1 相关工作

推荐系统的主要目标是向用户推荐一组满足其要求的个性化列表，根据用户的历史行为数据做出推荐，文献错误！未找到引用源。针对用户的购买或点击行为，提出了三种折扣方法：面向用户的折扣，面向项目的折扣和面向时间的折扣，该方法能够很好的与现有的矩阵分解模型相结合，提高了推荐的准确性。文献错误！未找到引用源。认为需要同时收集其正反馈和负反馈数据，提出了将用户反馈作为分类变量，并且将它和用户，项目以三元组的方式建模，采用了三阶张量分解技术和更高阶的折叠式方法产生推荐。文献错误！未找到引用源。提出了一种基于一组不同属性（包括认知努力，用户模型，测量尺度和域相关性)，在推荐系统中使用显式和隐式用户反馈的分类框架，提高了推荐系统的性能。上述的推荐方法虽然一定程度上提高了推荐准确性，但是都存在一定的不足之处，即忽略了推荐的多样性。

![](images/874f1ca67154202e6cadee35a6b028aa4b75ce72a962b0fd203d5a61d471f17c.jpg)  
图1IMDB网站中关于《致命弯道》的推荐列表

目前对于多样性的研究主要分为两个方面：总体多样性（aggregatediversity）和个体多样性（individualdiversity）。文献错误！未找到引用源。利用异构信息网络中的元路径相似性度量计算得到项目间的相关性，从而关联流行项目和利基项目，提高了推荐的总体多样性。文献错误！未找到引用源。为了提高推荐的个体多样性，提出了使用张量分解揭示包括社区、用户和社会标签的多模式数据中潜在主题的框架。文献错误！未找到引用源。提出了一种面向多样性的热传导算法，与面向准确度的能量扩散方法结合，调节精确度与多样性的平衡。文献错误！未找到引用源。结合了传统协同过滤和概率主题建模的优点，为用户和项目提供了可解释的潜在结构，增加了推荐的多样性。文献错误！未找到引用源。为了发现新颖项目，提出了通过项目的共现性将用户和项目之间的关系转换为项目和项目之间的关系的UC-BCF模型。上述学者对于多样性的研究都集中在项目集合上，而没有考虑到用户自身对于多样性的偏好程度。

本文提出了嵌入项目疲劳和多样偏好的聚合推荐算法，主要致力于向目标用户推荐符合其多样性偏好程度的个性化列表。本文的主要工作如下：a）通过对用户历史反馈信息分析用户对于多样性的偏好程度，提出了多样倾向度的概念，并通过聚类分析计算出用户的多样倾向度。b）为了增加冷门项目被推荐的权重，通过分析项目的被浏览信息，构造了受长尾分布约束的项目疲劳函数。c）提出了对用户历史反馈信息和项目主题信息使用矩阵分解与项目疲劳函数相聚合的ARIFDP算法，并加入多样倾向度调节项目疲劳函数所占权重。

d）在真实数据集上对本文提出的方法进行了实验，结果证实ARIFDP能够获得较好的结果。

# 2 问题描述和LDA主题模型

# 2.1问题描述

本文按如下方式考虑推荐问题：给定项目的描述信息以及目标用户的历史反馈信息，向目标用户推荐符合其多样性偏好程度的项目集合。

# 2.2LDA主题模型

LDA 模型错误！未找到引用源。由 D.M.Blei在 2003 年提出，是一种非监督机器学习技术，可以用来识别大规模文档集(documentcollection)或语料库(corpus)中潜藏的主题信息。其模型图如图2所示。

![](images/a2ad9fd9c76e4316fa276a1702e9d8cfef150a053e0e17a78bd18cd680b39f04.jpg)  
图2LDA模型图

当给定一个有M篇文档的文档集合D，共包含K个主题z，N 个单词 $\mathrm { ~ \bf ~ w ~ }$ 。其中 $\alpha$ 与 $\beta$ 是服从狄力克雷分布的语料级别的参数， $\alpha$ 是 $p ( \theta )$ 的向量参数，用于生成一个主题 $\theta$ 向量，$\beta$ 是各个主题对应的单词概率分布矩阵 $p ( w | z )$ 。则文本的生成过程可描述如下：

a)对每个文档 $d \in D$ ,从狄利克雷分布 $D i r ( \alpha )$ 中取样生成  
文档 $d$ 的主题分布 $\theta$ ·b)从主题的多项式分布 $\theta$ 中取样生成文档 $d$ 第 $n$ 个单词的  
主题 $z _ { n }$ ；c)从狄利克雷分布 $D i r ( \beta )$ 中取样生成主题 $z _ { n }$ 的词分布  
$\varphi _ { z _ { n } }$ ；d)从词的多项式分布 $\varphi _ { z _ { n } }$ 中采样最终生成词 $w _ { n }$ 。M个文档集合 $\mathrm { ~ D ~ }$ 用LDA生成的概率为

$$
\prod _ { m = 1 } ^ { M } \int p ( \theta _ { m } | \alpha ) \Biggl ( \prod _ { n = 1 } ^ { N _ { m } } p ( z _ { n } | \theta _ { m } ) p ( \varphi _ { z _ { n } } | \beta ) p ( w _ { n } \left| \theta _ { z _ { n } } \right. ) \Biggr ) d \theta _ { m }
$$

上述表达式中含有两个隐含变量，即文档-主题分布 $\theta$ 和主题-词分布，它们均可由Gibbs sampling 方法获得。

# 3 嵌入项目疲劳和多样偏好的聚合推荐算法

# 3.1 用户多样性偏好

定义1多样倾向度。设项目集合中所有项目经过聚类后的类簇数为K，用户反馈信息中项目的子类数目为L，则用户的多样倾向度为α=L/K。

定义2项目主题分布错误未找到明用源。。对于每个项目 $\boldsymbol { \nu } _ { \boldsymbol { j } }$ ，用LDA主题模型获取项目描述信息的主题分布，亦即项目主题分布，记为 $\theta _ { \nu }$ 。

通过对用户历史反馈信息研究发现，大部分用户的历史反馈信息中都存在很多不同种类的项目，项目的种类数越多则说明用户越偏好于多样性。本文通过K均值聚类算法对项目聚类，K均值聚类算法是一种基于形心的技术，需要计算不同类型的项目相异度。对于项目特征，可以通过项目的描述信息或项目的属性信息获取，本文通过LDA主题模型提取每个项目描述信息的主题分布向量，通过欧几里得距离计算每两个向量 $\mathbf { \Phi } _ { a }$ 和向量 $b$ 之间的相异度 $\boldsymbol { d i s t } ( \boldsymbol { a } , \boldsymbol { b } )$ 为

$$
d i s t ( a , b ) = \sqrt { \left( a _ { 1 } - b _ { 1 } \right) ^ { 2 } + \left( a _ { 2 } - b _ { 2 } \right) ^ { 2 } + \ldots + \left( a _ { n } - b _ { n } \right) ^ { 2 } }
$$

其中： $n$ 为主题向量的维数。在设定类簇个数 $\mathrm { ~ \bf ~ K ~ }$ 并完成聚类后，本文通过平均轮廓系数错误!未找到引用源。进行有效性分析，对象 $\mathbf { \sigma } _ { o }$ 的轮廓系数 $s ( o )$ 为

$$
s ( o ) = \frac { b ( o ) - a ( o ) } { \operatorname* { m a x } \left\{ a ( o ) , b ( o ) \right\} }
$$

在 $\mathrm { K } ^ { - }$ 均值聚类中， $s ( o )$ 的值在0和1之间， $a ( o )$ 表示 $\mathbf { \sigma } _ { o }$ 与$\mathbf { \Sigma } _ { o }$ 所属的簇的其他对象之间的平均距离，其值反映 $\mathbf { \Sigma } _ { o }$ 所属的簇的紧凑性，该值越小，簇越紧凑； $b ( o )$ 表示 $o$ 与不属于 $\mathbf { \Sigma } _ { o }$ 的所有簇的最小平均距离，其值捕获 $\mathbf { \sigma } _ { o }$ 与其他簇的分离程度，该值越大， $\mathbf { \Sigma } _ { o }$ 与其他簇越分离。为了度量聚类的质量，求所有项目的轮廓系数的平均值：

$$
{ \overline { { s ( o ) } } } = { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } s ( o )
$$

其中： $\boldsymbol { n }$ 为项目总数。平均轮廓系数的值越大，聚类质量越好。对于所有可能的类簇个数 $K$ ，求取平均轮廓系数的最大值，此时的 $K$ 即为最佳的聚类簇数。

使用K-均值聚类算法得到所有项目的 $K$ 个类簇后（离群点除外)，将用户的历史反馈记录中的项目逐一与聚类完成后的 $K$ 个簇进行比对后可以得到 $L$ 个子类（ $\scriptstyle L < = K )$ ， $L$ 即为用户历史反馈记录中项目的子类数量。则用户的多样倾向度通过定义1即可求得。

算法1多样倾向度取值算法

输入：项目集合中所有项目描述信息的数据集 $S _ { 1 }$ ，用户历史反馈数据中项目ID 的数据集S。  
输出：多样倾向度 $\omega$ 。

# begin

a） for each $i \in S _ { 1 }$   
b）采用LDA 计算项目描述信息的主题分布向量 $\theta$   
c）end for  
d）分别计算每两个向量之间的相异度 $d i s t ( a , b )$   
e）从 $S _ { \mathrm { 1 } }$ 中任意选择K个对象作为初始簇中心  
f）repeat  
g）根据簇中对象的均值，将每个对象分配到最相似的簇  
h）更新簇均值，until各个簇均值不再发生变化  
i）变换K的数值，重复步骤5\~8，分别求其平均轮廓系数，取最大平均  
轮廓系数对应的K值作为 $S _ { 1 }$ 聚类后项目的类簇数K  
j） for each j∈S2  
k）将 $\mathrm { \bf { j } }$ 与K个簇进行比对  
1）end for  
m）计算得到 $S _ { 2 }$ 中共有L个子类  
n) $\omega \gets L / K$   
o）return $\omega$ （204号  
end

# 3.2多样性推荐方法

传统的协同过滤方法能够解决一定的稀疏性问题，但是当有新项目加入到系统中时，没有足够的用户对其产生过反馈信息，此时如果利用传统的协同过滤方法就很难得到理想的推荐效果。受文献错误!未找到引用源。错误!未找到引用源。的启发，将项目的主题模型融入矩阵分解中计算出用户对项目的初始偏好得分，同时聚合项目疲劳函数，调整偏好得分，一方面可以缓解冷启动问题，另一方面也可以增加推荐结果的多样性。

为了改善矩阵分解的推荐效果，增加冷门项目的信息，本文用LDA主题模型学习项目描述信息的主题分布 $\theta _ { \nu }$ ，不采用随机的方式初始化项目的隐含特征矩阵，而是用 $\theta _ { \nu }$ 初始化项目的隐含特征矩阵 $\boldsymbol { V }$ ，通过模型学习得到的项目的隐含特征 $\boldsymbol { V }$ 如下：

$$
\nu _ { _ j } = \varepsilon _ { \nu j } + \theta _ { \nu j }
$$

其中： $\boldsymbol { \varepsilon }$ 表示项目的特征分布与LDA学习得出的主题分布的偏差值，项目的特征分布是接近于LDA学习出的主题分布，但也存在偏差。LDA使用的是内容信息获取项目的主题分布，在LDA与矩阵分解的融合中加入用户的评分信息，调整用户和项目的特征分布，则目标函数如下：

$$
\begin{array} { l } { { \displaystyle f \left( U , V \right) = \sum _ { ( i , j ) \in I } \left( r _ { i j } - { u _ { i } ^ { T } } \nu _ { j } \right) ^ { 2 } + } } \\ { { \displaystyle \lambda _ { u } \sum _ { i } \left\| u _ { i } \right\| ^ { 2 } + \lambda _ { \nu } \sum _ { j } \left\| \left( \nu _ { j } - \theta _ { \nu j } \right) \right\| ^ { 2 } } } \end{array}
$$

对于每一个用户 $i$ 和项目 $j$ 的对 $( i , j ) ~ , ~ r _ { i j }$ 表示用户 $i$ 对项目 $j$ 的评分。 $r _ { i j } \in R$ ， $\scriptstyle { \mathcal { R } }$ 为评分矩阵。 $\lambda _ { u }$ 和 $\lambda _ { \nu }$ 是正则项系数,通过使用交替最小二乘法求解可以得到 $u _ { i }$ 和 $\boldsymbol { \nu } _ { { } _ { j } }$ 相应的更新公式：

$$
u _ { i } = \left( \boldsymbol { W } ^ { T } + \lambda _ { u } \boldsymbol { E } \right) ^ { - 1 } V R _ { i }
$$

$$
\nu _ { j } = \left( U U ^ { T } + \lambda _ { \nu } E \right) ^ { - 1 } \left( U R _ { j } + \lambda _ { \nu } \theta _ { \nu j } \right)
$$

其中： $E$ 是单位矩阵； $R _ { i }$ 是 $R$ 矩阵中第 $i$ 行向量的转置； $R _ { j }$ 是$R$ 矩阵中第 $j$ 行向量的转置。通过迭代更新 $u _ { i }$ 和 $\boldsymbol { \nu } _ { { } _ { j } }$ 可以得到用户隐含特征 $\boldsymbol { U } ^ { * }$ 和项目隐含特征 $\boldsymbol { V } ^ { * }$ ，则用户 $i$ 对项目 $j$ 的偏好得分 $r _ { i j } ^ { * }$ 计算公式如下：

$$
r _ { i j } ^ { * } = \left( u _ { i } ^ { * } \right) ^ { T } \nu _ { j } ^ { * }
$$

对电子商务网站的销售记录研究发现，项目的销量呈长尾分布，项目的被评价次数也同样呈长尾分布错误!未找到引用源。，当用户被多次推荐相同的项目会产生项目疲劳[14]。为了进一步增加冷门项目被推荐的概率，本文将矩阵分解计算得出的初始偏好得分与项目疲劳函数相聚合，提高冷门项目的推荐权重。因此将式(9)改写为

$$
{ r _ { i j } ^ { * } } = \left( { u _ { i } ^ { * } } \right) ^ { T } { \nu _ { j } } ^ { * } + \omega { \cdot } \mu \eta ( x )
$$

其中： $\eta ( \boldsymbol { x } )$ 为项目疲劳函数，其具体构造方法将在下一节详细介绍； $\omega$ 为多样倾向度，用来调节项目疲劳函数所占比重；系数 $\mu$ 用来调节 $\eta ( \boldsymbol { x } )$ 的值域范围，其值为评分范围的最大值。

将对应的偏好得分降序排序，选取top $. N$ 作为最终推荐列表。

# 3.3受长尾分布约束的项目疲劳函数

定义3长尾分布错误！未找到引用源。。令 $S ( x )$ 为任意一个分布的累积分布函数，互补函数为 $S ^ { c } \left( x \right) = 1 - S \left( x \right)$ 。如果满足对任意$\gamma > 0$ ，当 $t \to \infty$ 时，有 $e ^ { \gamma t } S ^ { c } \left( x \right) \to \infty$ ，则称 $s ( x )$ 对应的分布为长尾分布。

为了满足定义3中描述的长尾分布的条件，文献错误！未找到引用源。提出了由 $n$ 个底为 $\mathbf { \Psi } _ { e }$ 的指数函数线性组合描述长尾分布函数：

$$
P ( x ) = \sum _ { j = 1 } ^ { n } p _ { j } e ^ { - \lambda _ { j } x } + C
$$

数据集中项目的被评价次数符合长尾分布，将数据点记为$( x _ { i } , y _ { i } ) \ ( i = 1 , . . . , h )$ ，其中， $x _ { i }$ 为项目被评分次数的排名， $y _ { i }$ 为项目被评分的次数， $\mathbf { \Phi } _ { h }$ 为项目总数， $F ( x )$ 表示 $P ( x )$ 与数据(x,y)的平方差：

$$
F ( x ) = \sum _ { i = 1 } ^ { h } \omega _ { i } \Biggl ( \sum _ { j = 1 } ^ { n } p _ { j } e ^ { - \lambda _ { j } x _ { i } } + C - y _ { i } \Biggr ) ^ { 2 }
$$

其中： $\omega _ { i } > 0$ 为点的权系数，可通过求 $n$ 阶非线性方程组得到使 $F ( x )$ 最小的参数 $p _ { j } , \lambda _ { j } > 0 \ \left( j = 1 , . . . , n \right)$ ，进而求得满足长尾分布描述的 $P ( x )$ 。文献错误!未找到引用源。进一步通过对韦伯分布的拟合效果分析得出当 $n = 2$ 时，对长尾分布的描述效果最优，也即 $P ( x ) = p _ { 1 } e ^ { - \lambda _ { 1 } x } + p _ { 2 } e ^ { - \lambda _ { 2 } x } + C$ 。

由于项目被评价的次数呈长尾分布，为了增加对冷门项目的推荐，提高推荐的多样性，通过构造与评价次数负相关的项目疲劳函数来提高冷门项目的推荐权重，令函数g(x)=1/(1+e")将长尾分布的函数值P(x)映射到[0,1]，则项目疲劳函数 $\eta ( \boldsymbol { x } )$ 可表示如下：

$$
\eta ( x ) = 1 - \frac { 1 } { 1 + e ^ { - P ( x ) } }
$$

# 3.4ARIFDP 算法总体描述

推荐系统要以“用户的长期维系”为目标，如果只以当前大多数基于准确率为衡量标准的算法进行推荐，将严重影响推荐系统的长期性能，从而导致长尾项目无法得到推荐。本文ARIFDP推荐算法的主要步骤为：通过对用户历史反馈信息分析用户的多样倾向度；将主题模型融入矩阵分解计算出用户对项目的初始偏好得分；为了提高推荐多样性，将初始偏好得分与项目疲劳函数相聚合，并通过多样倾向度调节项目疲劳函数所占权重。ARIFDP算法的主要步骤表示如下：

算法2多样性推荐算法ARIFDP

输入：用户评分数据集 $D$ ，待推荐项目集合item。  
输出：每个用户的 top $\cdot N$ 推荐列表。  
begin  
1）for each i∈ Item  
2）通过项目的描述信息计算项目主题分 布 $\theta _ { \nu }$   
3）end for  
4）用 $\theta _ { \nu }$ 初始化项目隐含特征矩阵 $V$ ，并加入用户评分数据集 $D$ 调整用户和项目的特征分布，求解 $\boldsymbol { U } ^ { * }$ 和 $\boldsymbol { V } ^ { * }$   
5）计算用户对于项目的初始偏好得分ri\*←(u）v\*  
6）通过数据集D构造项目疲劳函数n(x)←1 $\eta ( x ) \gets 1 - \frac { 1 } { 1 + e ^ { - W ( x ) } }$   
7） ${ r _ { i j } ^ { * }   } { ( { u _ { i } ^ { * } } ) ^ { T } } { \nu _ { j } ^ { * } } + \omega { \cdot \mu } \eta ( x )$   
8）根据 $r _ { i j } ^ { * }$ 降序排序，选取Top-n 作为最终的推荐列表  
end

# 4 实验及结果分析

# 4.1实验数据集

本文实验数据采用了MovieLens 数据集，该数据集由美国明尼苏达州立大学GroupLens 研究小组提供，包括6040个用户对3952部电影的约100万条电影评分信息，每个用户至少评价了20部电影，且评分范围为1\~5，“1”表示“p00r”（不喜欢)，“5”表示“perfect”（非常喜欢）。本文从中选取了943个用户对1682部电影的大约100000次评分数据作为实验数据集，稀疏度为 $9 3 . 7 \%$ 。由于数据集中不包含电影的描述信息，但是此部分信息是本文中算法的重要组成部分，而MovieLens数据集中的u.item文件中包含了每部电影链接IMDbURL，因此通过Python 爬虫程序获取每部电影的Storyline（描述信息）。

在实验中，从数据集中随机抽取 $80 \%$ 作为训练集，其余的$20 \%$ 作为测试集。

# 4.2评价标准

# 4.2.1推荐准确性评测指标

本实验采用平均绝对偏差MAE(meanabsolute error)作为度量准确性的标准，它是一种统计精度度量方法，同时也是最常用的一种推荐质量度量方法，其通过计算预测评分与实际评分之间的偏差来衡量预测的准确性，MAE的值越小，表明推荐质量越高。

假设预测的用户评分集合为 $\{ p _ { 1 } , p _ { 2 } , \cdots , p _ { N } \}$ ，对应的实际用户评分集合为 $\{ q _ { 1 } , q _ { 2 } , \cdots , q _ { N } \}$ ， $\mathbf { N }$ 表示预测的次数，则 MAE 的计

算公式如下：

$$
\ M A E = { \frac { \displaystyle \sum _ { i = 1 } ^ { N } \lvert p _ { i } - q _ { i } \rvert } { N } }
$$

# 4.2.2推荐多样性评测指标

高准确性一直是目前大多数推荐系统的衡量标准，但是系统要以"用户的长期维系"为目标，因此提高推荐结果的多样性非常重要。对推荐结果的多样性评测主要包括两个方面：总体多样性和个体多样性。

对于总体多样性，本实验采用信息熵错误;未找到引用源·进行评测。信息熵是信息理论中用于度量信息量的一个概念，如果系统越是有序，那么信息熵越低，反之越高。如果推荐结果中所有的项目都能够出现，并且出现的次数相差不大，那么系统具有很好的挖掘长尾项目的能力，我们将不同推荐列表中项目的出现次数称为该项目在推荐结果中的流行度，信息熵的计算公式如下：

$$
H = - \sum _ { i = 1 } ^ { n } p ( i ) \log p ( i )
$$

其中: $p ( i )$ 等于项目 $i$ 的流行度除以所有项目流行度之和。信息熵越大，表明算法挖掘长尾项目的能力越好。

对于个体多样性，通过计算每个用户 $\boldsymbol { u }$ 的推荐结果 $\boldsymbol { R } ( \boldsymbol { u } )$ 中两两项目的不相似程度 $D ( R ( u ) )$ ，进而求得所有用户的推荐列表不相似程度的均值为

$$
D ( R ( u ) ) = 1 - \frac { \sum _ { i , j \in { \cal R } ( u ) , i \neq j } s i m ( i , j ) } { \frac { 1 } { 2 } | R ( u ) | ( | R ( u ) | - 1 ) }
$$

$$
D = { \frac { 1 } { | U | } } \sum _ { u \in U } D ( R ( u ) )
$$

# 4.3实验过程

# 4.3.1类簇个数的取值

K-均值聚类算法中，不同的 $K$ 值对聚类效果有着重要的影响，本实验采用平均轮廓系数来确定类簇的个数，数据集中共有1682部电影，通过分析数据集中电影的数据规模、类别特征以及已有的K均值算法对于MovieLens数据集的聚类效果，将K值范围设定在[2,50]之间。

由于K-均值聚类具有一定的随机性，并不是每次都收敛到全局最小，为了避免得到局部最优解，针对区间内每一个K值，重复执行 30次，计算每一次的 $\overline { { s ( o ) } }$ ，并取其平均值 AVG( ${ \overline { { s ( o ) } } } )$ 度量K值的聚类效果，由于篇幅有限，表1列出了部分AVG( $\overline { { s ( o ) } }$ )较大时聚类质量情况。

表1不同的类簇个数对聚类效果的影响  

<html><body><table><tr><td>簇数</td><td>AVG( s</td><td>簇数</td><td>AVG(</td></tr><tr><td>8</td><td>0.5714</td><td>13</td><td>0.6912</td></tr><tr><td>9</td><td>0.5893</td><td>14</td><td>0.6895</td></tr></table></body></html>

<html><body><table><tr><td>10</td><td>0.5167</td><td>15</td><td>0.6713</td></tr><tr><td>11</td><td>0.6058</td><td>16</td><td>0.6574</td></tr><tr><td>12</td><td>0.6719</td><td>17</td><td>0.6051</td></tr></table></body></html>

从表1中可以看出，类簇数为13时的平均轮廓系数最大，其值为0.6912，所以类簇数为13时聚类效果最好，在接下来的实验中，将类簇数设置为13进行实验。

# 4.3.2多样倾向度 $\omega$ 的分布

在ARIFDP算法中，多样倾向度 $\omega$ 起到了很重要的作用，用来平衡准确性和多样性的比重， $\omega$ 越大表明算法受项目疲劳函数的影响力越大。由4.3.1节可知， $\mathrm { K } { = } 1 3$ 时聚类效果最好，本实验分别计算了数据集在 $\mathrm { K } { = } 1 3$ 时30次聚类完成后各用户评分过的电影类别数，并计算了用户30次多样倾向度 $\omega$ 的平均值，得到用户的多样倾向度 $\omega$ 的分布情况，结果如表2所示。

表2不同的 $\omega$ 值所占的百分比  

<html><body><table><tr><td>ω值的范围</td><td>所占百分比</td></tr><tr><td>[0.0.1)</td><td>3.5%</td></tr><tr><td>[0.1,0.2)</td><td>9%</td></tr><tr><td>[0.2,0.3)</td><td>57%</td></tr><tr><td>[0.3,0.4)</td><td>15%</td></tr><tr><td>[0.4,0.5)</td><td>6.5%</td></tr><tr><td>[0.5,0.6)</td><td>4.5%</td></tr><tr><td>[0.6.0.7)</td><td>2%</td></tr><tr><td>[0.7,0.8)</td><td>1.5%</td></tr><tr><td>[0.8.0.9)</td><td>0.5%</td></tr><tr><td>[0.9,1]</td><td>0.5%</td></tr></table></body></html>

从表2中可以看出，大部分的用户的多样倾向度 $\omega$ 的值集中在[0.2.0.3)内，这说明了大部分用户对于推荐系统的多样性是有一定的要求，如果只以传统的基于准确性为标准的算法进行推荐是不能够满足要求的，这也说明了本文算法的有效性。

# 4.3.3多样性和准确性的对比实验

为了展示本文提出的ARIFDP算法的有效性和高效性，本文同以下两种方法进行了比较：

a)传统MF,该方法通过对用户的浏览行为进行矩阵分解来计算用户对于项目的偏好。

b)CTR 错误!未找到引用源。,该方法结合了传统协同过滤和概率主题建模的优点，为用户和项目提供了可解释的潜在结构，增加了推荐的多样性。

由于MovieLens数据集中用户对电影的评分范围为1\~5，因此设置式（10）中的参数 $\scriptstyle \mu = 5$ 。实验中分别比较了本文提出的ARIFDP 算法同其他两种算法在准确性，个体多样性以及总体多样性指标上的不同表现。以选择的推荐对象个数为横坐标，各评测指标为纵坐标，推荐对象个数从10开始，逐次增加，直至100，实验结果如图3\~5所示。

![](images/7469ad2acc5d8f96683cf8e61b625bfdbdf91407543740f745468adabb156e53.jpg)  
图3不同算法的准确性对比

从图3中可以看出，由于ARIFDP算法加入了项目疲劳函数，增加了推荐的多样性，其准确性与CTR模型相比略显不足，但是由于ARIFDP算法不仅利用了用户的评分信息，同时还加入了项目主题模型，而传统的MF模型仅利用了用户的评分信息，所以当推荐的项目逐渐增多的时候，准确率较传统的 MF模型稍高。因此，ARIFDP算法的准确性还是在可以接受的范围之内。

![](images/3d58fdc88f453116cb4587e04950825f067b84c8c5078a37c1226d93796450dc.jpg)  
图4不同算法的总体多样性对比

![](images/21c64d8a12b6be11e7ff1e8677f883725515e329f7f742cfb969ea74944003dd.jpg)  
图5不同算法的个体多样性对比

从图4和5中可以看出，由于本文提出的ARIFDP 算法加入了项目疲劳函数，增加了冷门项目的推荐权重，综合三种不同的推荐算法，包括总体多样性和个体多样性两个方面，ARIFDP算法均能够取得较好的效果。在总体多样性方面，ARIFDP能够在全局上推荐更多不同种类的项目，有利于保证推荐系统的长期性能；在个体多样性方面，ARIFDP能够为单个用户提供尽可能丰富的推荐列表，有利于拓宽用户的视野，提高用户的满意度。因此，本文提出的ARIFDP算法能够有效向目标用户推荐符合其多样性偏好程度的项目集合。

# 5 结束语

针对如何向目标用户推荐符合其多样性偏好程度的项目集合，本文提出了嵌入项目疲劳和多样偏好的聚合推荐算法ARIFDP，通过K-均值聚类算法对项目进行聚类，分析用户的多样性偏好程度，得出用户的多样倾向度；将矩阵分解与项目疲劳函数相聚合，同时加入多样倾向度调节项目疲劳函数所占权重，增加了冷门项目被推荐的概率。在真实数据集上的实验表明，ARIFDP能够得到准确率较好且多样性丰富的推荐列表。

用户的多样倾向度还和用户的属性信息相关联，比如性别、年龄、职业、受教育程度等。此外，用户的多样倾向度是动态变化的。如何设计一个能够有效结合用户行为信息和用户属性信息的模型来度量用户的多样倾向度将是我们下一步的研究方向。

# 参考文献：

[1]Cheng Peizhe,Wang Shuaiqiang,Ma Jun,et al. Learning to recommend accurate and diverse items [C]// Proc of the 26th International Conference on World Wide Web.International World Wide Web Conferences Steering Committee,2017:183-192.   
[2]Kawai K, Kitagawa H. Collaborative filtering with implicit feedbacks by discounting positive feedbacks [Cl// Proc of the 2nd IEEE International Conference on Multimedia Big Data.2016: 41-48.   
[3] Frolov E,Oseledets I.Fifty shades of ratings: how to benefit from a negative feedback in top-N recommendations tasks [C]//Proc of the 10th ACM Conference on Recommender Systems.New York: ACM Press, 2016: 91-98.   
[4]Jawaheer $\mathbf { G }$ Weller P,Kostkova P. Modeling user preferencesin recommender systems:a classification framework for explicit and implicit user feedback [J].ACM Trans on Interactive Intelligent Systems,2014,4 (2): 8.   
[5]Liu Yezheng,Wang Jinkun,Jiang Yuanchun,et al.Utilize item correlation to improve aggregate diversity for recommender systems [C]/ Proc of IEEE International Conference on Data Science in Cyberspace.2016: 412-417.   
[6]Koochi M R,Hussin A R C,Dahlan H M.Improving recommendation diversity using tensor decomposition and clustering approaches [Cl// Proc ofthe 4th World Congresson Information and Communication Technologies.2014: 240-245.   
[7] Zhou Tao，Kuscsik Z,Liu JianGuo，et al.Solving the apparent diversity-accuracy dilemma of recommender systems [J]. Proceedings of the National Academy of Sciences,2010,107 (10): 4511-4515.   
[8]Wang Chong,Blei D M. Colaborative topic modeling for recommending scientific articles [C]// Proc of the 17th ACM SIGKDD international conference on Knowledge discovery and data mining.New York:ACM Press,2011: 448-456.   
[9]Niemann K,Wolpers M.A new collaborative filtering approach for increasing the aggregate diversity of recommender systems [Cl// Proc of the 19th ACM SIGKDD International Conference on Knowledge Discovery and DataMining.New York:ACMPress,2013:955-963.   
[10] Blei D M,NgA Y, Jordan MI. Latent Dirichlet allocation [J]. Journal of Machine Learning Research,2003,3(1): 993-1022.   
[11] Steinberger J.Update summarization based on novel topic distribution [C]//Proc of ACM Symposium on Document Engineering.New York: ACMPress,2009:205-213.   
[12] Jain R,Koronios A. Innovation in the cluster validating techniques [J]. Fuzzy Optimization & Decision Making,2008,7(3):233-241.   
[13] Park YJ,Tuzhilin A.The long tail of recommender systems and how to leverage it [C]//Proc of ACM Conference on Recommender Systems.New York:ACMPress,2008:11-18.   
[14]印桂生，张亚楠，董红斌，等．一种由长尾分布约束的推荐方法[J]. 计算机研究与发展，2013，50(9):1814-1824.（Yin Guisheng，Zhang Yanan，Dong Hongbin，et al.A long tail distribution constrained recommendation method [J].Journal of Computer Research and Development,2013,50 (9):1814-1824.)   
[15] Sar Shalom O,Koenigstein N,Paquet U,et al.Beyond collaborative filtering:the list recommendation problem [C]// Proc of International Conferenceon World WideWeb.InternationalWorld Wide Web Conferences Steering Committee,2016: 63-72.   
[16] Zhang QianSheng, Jiang ShengYi.A note on information entropy measures for vague sets and its applications [J].Information Sciences,2O08,178 (21): 4184-4191.