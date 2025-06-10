# 融合项目偏差与用户偏好的推荐算法

程磊，高茂庭

(上海海事大学 信息工程学院，上海 201306)

摘要：针对协同过滤推荐中由于项目和用户间关联因素的相互影响而存在项目偏差和用户偏好的问题，提出一种融合项目偏差与用户偏好的推荐算法。先进行聚类处理，包括LDA主题建模生成项目簇和K-means 聚类生成用户簇；再依次根据项目簇和用户簇的约束生成项目偏差分，同时以用户项目评分及项目类型为基础，经过概率转移得到用户偏好分；最后以项目簇内已有评分的均值为基础，对项目偏差分和用户偏好分进行线性加权生成预测评分。对比实验表明，新算法能够根据不同的近邻得到合理的推荐，提高推荐的准确度。

关键词：协同过滤；主题建模；聚类；项目偏差；用户偏好 中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2018.05.0298

# Recommendation algorithm combining item deviation and user preference

Cheng Lei, Gao Maoting (College of Information Engineering,Shanghai Maritime University,Shanghai 2Ol306,China)

Abstract:Aimingatthe problem that there existsitem deviationanduser preferences in collaborative filtering recommendation forthe interaction between factors related in itemsandusers,thispaper proposed arecommendation algorithm integrated item deviationanduser preference.Firstly itclustered to generate item clusters onLDA topics modeling andto getuser clustersbyusing K-means; then it generated item deviation score onthe constraints of item cluster and user cluster,andobtained userpreferencescore withprobabilitytransferonuser-itemscoreanditem type.Finaly it weightedthe itemdeviation score and user preference score linearly to formthe prediction score based on the existing scoring average in the item cluster. Comparison experiments show that the new algorithm could obtain reasonable recommendation based on different neighbors and improve recommendation accuracy.

Key words: collaborative filtering; topic modeling; clustering; item deviation; user preference

# 0 引言

推荐系统作为一种是帮助用户快速选择有效信息的重要工具，正在被越来越多的电子商务和社交网站用来改善用户体验。推荐算法主要包括基于协同过滤的算法、基于内容的算法和基于标签的算法[I。作为常用的推荐算法，协同过滤主要依据用户一项目评分信息进行评分预测，存在一些不足使算法准确度难以提高，一方面，由于受项目间关联因素的相互影响，实际存在项目偏差问题；另一方面，却缺少考虑不同用户对各项目类型的偏好因素。

为此，Shi等人[2提出一种基于新型概率主题模型，在相似度计算时引入两个项目之间相异性的惩罚项，减少不相关的项目对于准确度的影响。Qiao等人[3提出一种结合用户属性和项目内容的推荐算法，利用LDA(latentDirichletallocation)模型分别对用户属性和项目内容进行主题分析，挖掘出用户对项目的偏好。Zhao 等人[4]提出一种基于特征转移和概率矩阵分解的推荐算法，将信任矩阵集成到评分矩阵中，用户的评分只受到自身属性以及信任的人影响，从而过滤掉无关用户。Zhou等人[5]提出一种评估协同过滤的LDA模型，通过给主题模型添加用户评分信息来进行协同过滤，并利用用户对于项目的偏好给出合理的推荐。原福永[等人提出一种基于项目的协同过滤算法，将项目分类和K近邻引入到SlopeOne 算法，从而过滤掉不相关的项目。刘慧婷等人[7提出一种基于用户偏好的矩阵分解算法，通过用户项目评分矩阵和矩阵分解得到的项目属性矩阵计算用户的偏好，提高了预测的准确度。

这些研究一定程度上考虑了项目偏差或用户偏好因素对预测的影响，取到了较好的成效，基于此，提出一种融合项目偏差和用户偏好的推荐算法（item deviation and user preferencecombinationfiltering，IUCF)，通过对项目和用户分别进行聚类处理，利用最近邻协同过滤和概率转移挖掘项目偏差和用户偏好，并将两者融入用户对项目的预测评分中完成推荐。

# 1 相关研究

# 1.1基于用户的协同过滤算法

基于用户的协同过滤算法分为以下几步：a)根据用户-项目评分矩阵计算用户之间的相似度；b)根据相似度选取近邻用户；c)根据近邻用户给出预测分数。相似度的计算采用皮尔逊相关系数[8]：

$$
S i m ( a , b ) = \frac { \displaystyle \sum _ { n \in I _ { a b } } { ( r _ { a n } - \overline { { r _ { a } } } ) ( r _ { b n } - \overline { { r _ { b } } } ) } } { \displaystyle \sqrt { \sum _ { n \in I _ { a b } } { ( r _ { a n } - \overline { { r _ { a } } } ) ^ { 2 } } } \sqrt { \sum _ { n \in I _ { a b } } { ( r _ { b n } - \overline { { r _ { b } } } ) ^ { 2 } } } }
$$

其中: $I _ { a b }$ 表示用户 $a$ 与用户 $b$ 共同评分过的项目集合， $r _ { a n }$ 和 $r _ { b n }$ 分别表示用户 $a$ 和用户 $b$ 对项目 $n$ 的实际评分， $\overline { { r } } _ { a }$ 和 $\overline { { r _ { b } } }$ 分别表示用户 $a$ 和用户 $b$ 所有评分的平均值。

# 1.2LDA主题模型

LDA主题模型首先使用Dirichlet概率分布来设置文档的潜在概率，然后使用抽样算法来估计文档-主题概率分布和主题-词汇概率分布。抽样算法采取Gibbs 采样[10]：

$$
p ( z _ { i } = k \big | \vec { z } _ { - i } , \vec { w } ) \propto \frac { n _ { m , - i } ^ { ( k ) } + \alpha _ { k } } { \displaystyle \sum _ { k = 1 } ^ { K } ( n _ { m , - i } ^ { ( k ) } + \alpha _ { k } ) } \cdot \frac { n _ { k , - i } ^ { ( t ) } + \beta _ { t } } { \displaystyle \sum _ { t = 1 } ^ { V } ( n _ { k , - i } ^ { ( t ) } + \beta _ { t } ) }
$$

其中: $p ( z _ { i } = k \mid \vec { z } _ { - , i } , \vec { w } )$ 表示排除第 $i$ 个词汇，根据文档集 $\vec { w }$ 中其它词汇序列的主题分布来计算第 $i$ 个词汇属于第 $k$ 个主题的概率，其中 $z _ { i }$ 表示语料库中的第 $i$ 个词汇对应的主题； $n _ { m , - i } ^ { ( k ) }$ 表示排除第 $i$ 个词汇，第 $m$ 篇文档中主题 $k$ 的词汇次数； $n _ { k , - i } ^ { ( t ) }$ 表示排除第 $i$ 个词汇，第 $k$ 个主题中词汇 $t$ 的次数； $\alpha _ { k }$ 和 $\beta _ { t }$ 分别表示文档-主题分布和主题-词汇分布的Dirichlet先验参数。

# 1.3问题描述与分析

在进行评分预测过程中，由于受项目间关联因素的相互影响，实际存在项目偏差问题，例如动作题材电影的评分计算时，除同一题材电影的评分外，许多无关题材的评分也参与了计算，导致预测评分偏离了实际；同样，在近邻选取时，往往是在整个用户集里找寻，并未充分考虑用户的内在属性，无法准确体现不同用户对不同类型项目所存在的一些偏好，例如：不同年龄段人群间爱好存在一定的差异，表面上打分相近用户，实际上可能有较大差距。同时，用户的偏好也影响用户对项目的评分，例如：当电影同时存在用户喜欢的动作题材和不喜欢的恐怖题材，用户对电影的打分就会受到其个人偏好的影响。需要准确挖掘项目偏差和用户偏好，以对最终预测评分进行纠偏。

针对项目偏差挖掘，文献[6]分别从用户和项目的角度对项目偏差进行过滤，最后再进行混合加权，但是这种方式计算量比较大。文献[11]使用用户间信任度与相似度的线性加权作为最近邻的选取依据，但其在计算时依然未考虑项目的内在属性。针对用户偏好挖掘，文献[7]通过矩阵分解算法挖掘出用户的偏好，但矩阵分解算法可解释差。文献[12]简单使用包括某类型的项目评分的均值表示类型的评分，导致用户偏好区分度不高。

为此，在IUCF算法中，充分考虑项目和用户的内在属性，通过对项目类型和用户属性进行聚类，使得项目偏差更加准确可靠。通过统计项目类型被标记次数的比例，再结合用户评分矩阵，使得出现频率高的类型获得较高的打分，从而使得到的用户偏好可靠。

# 2 融合项目偏差与用户偏好的推荐算法

IUCF算法中融入两部分内容：基于项目簇和用户簇生成项目偏差分和基于项目类型生成用户偏好分，并以目标用户所在项目簇的已有评分均值为基础，对两部分线性加权生成最终预测评分，算法模型如图1所示。

![](images/1d63dca58cd8e62fdb386d98c8a10f8d375615d1fc8d539cdcb9a5f038ec171b.jpg)  
图1IUCF算法模型

# 2.1聚类处理

为准确地体现项目偏差，需要在项目偏差中同时考虑项目类型和用户属性；同时为准确地挖掘用户偏好，在计算用户偏好时考虑用户对不同项目类型的喜好程度。为此，通过对项目类型和用户属性的聚类，生成项目簇和用户簇，计算项目偏差和用户偏好，从而提高推荐的准确度。

# 2.1.1LDA主题建模生成项目簇

LDA主题建模是一种文档主题生成模型，能够识别语料库中潜在的主题信息。在模型中，每一篇文档看作是由许多主题所构成，而每一个主题又由许多词汇所构成。将所有的项目类型作为文档，将类型作为词汇，找寻每个词汇所在的主题。设 $I$ 为项目集合， $I = \{ I _ { 1 } , I _ { 2 } , \cdots , I _ { n } \}$ ，其中， $I _ { n }$ 表示第 $n$ 个项目。定义项目类型 $I _ { n } = ( i _ { 1 } , i _ { 2 } , \cdots , i _ { m } )$ ，其中， $i _ { m }$ 表示项目 $I _ { n }$ 的第 $m$ 个类型，例如，当 $I _ { n } =$ (Action,Drama, $\mathrm { W a r }$ ）时，表示项目 $I _ { n }$ 的类型为Action、Drama和War。

将项目集合进行LDA主题建模，使用Gibss采样法，得到项目-类型主题分布 $\hat { z }$ 和主题-类型概率矩阵 $D _ { t \times m }$ ，其中主题数目需要根据LDA聚类后算法的准确度确定。

在 $\hat { z }$ 中，每个项目 $I _ { n }$ 的类型 $i _ { m }$ 都有一个主题标号，形式如$I _ { n } = ( i _ { 1 } : z _ { 1 } , i _ { 2 } : z _ { 2 } , \cdots , i _ { m } : z _ { t } )$ ，其中， $i _ { m } : z _ { t }$ 表示 $i _ { m }$ 对应的主题标号为 $z _ { t }$ ，例如，Action:3表示类型Action属于主题3。

根据 $\hat { Z }$ 建立项目-主题隶属矩阵 $\hat { I } _ { n \times t }$ ，当项目的类型 $i _ { m }$ 属于主题 $t$ 时， $\hat { i } _ { n t } = 1$ ，否则， $\hat { i } _ { n t } { = } 0$ ，如式（3）所示。

$$
\hat { I } _ { n \times t } = \left[ \begin{array} { l l l } { \hat { i } _ { 1 1 } } & { \cdots } & { \hat { i } _ { 1 t } } \\ { \vdots } & & { \vdots } \\ { \hat { i } _ { n 1 } } & { \cdots } & { \hat { i } _ { n t } } \end{array} \right]
$$

由项目一主题隶属矩阵的任意一行可以得到项目主题簇，记为 $\mathbf { C N } _ { n }$ ；由项目一主题隶属矩阵的任意一列，可以得到主题项目簇，记为 $\mathbf { C T } _ { t }$ 。如式（4）（5）所示。

$$
\mathbf { C N } _ { n } = \{ i \vert \hat { i } _ { n i } = 1 , i \in [ 1 , t ] \}
$$

$$
\begin{array} { r } { \mathbf { C T } _ { t } = \{ j \vert \hat { i } _ { j t } = 1 , j \in [ 1 , n ] \} } \end{array}
$$

其中： $\mathrm { C N } _ { n }$ 表示项目 $n$ 所属的主题集合， $\mathbf { C T } _ { t }$ 表示主题 $t$ 包含的项目集合， $i$ 表示主题号， $j$ 表示项目号。

对于目标项目 $n$ ，先找到其对应的 $\mathbf { C N } _ { n }$ ，然后找到每个主题所对应的 $C T _ { t }$ ，最后将所有的 $\mathbf { C T } _ { t }$ 进行并集运算得到目标项目 $n$ 所在的项目簇 $C _ { n }$ ，如式（6）所示。

$$
C _ { n } = \bigcup _ { t \in \mathrm { C N } _ { n } } \mathbf { C T } _ { t }
$$

# 2.1.2K-means聚类生成用户簇

在当前的网络环境下，可以准确获取用户属性，用户属性包括用户的性别，年龄和职业。定义用户集合为$\boldsymbol { Q } = \{ Q _ { 1 } , Q _ { 2 } , \cdots , Q _ { i } \}$ ，用户属性为 $\boldsymbol { Q } _ { i } = ( q _ { 1 } , q _ { 2 , \cdots , q _ { k } } )$ ，其中， $Q _ { i }$ 表示第 $i$ 个用户， $q _ { k }$ 表示用户 $i$ 的第 $k$ 个基本属性，例如，当 $Q _ { i } =$ （男，23，teacher）时，表示用户 $Q _ { i }$ 的性别为男，年龄为23，职业为teacher。

为了进行K-means聚类，需要对用户的基本信息进行预处理，采用数字编码[1-9]的方式对用户的基本信息进行预处理。针对性别，将男女分别编码为1和2；针对年龄，根据文献[13]所提出的5组划分方式，将用户年龄划分为少儿组（0\~19岁），青年组（20-39岁)，壮年组（40\~59岁)，实年组（60\~79岁）和老年组（ $\geq 8 0$ 岁)，并依次编码为1,2,3,4,5。针对职业，文献[14]将二八定理用于信息评估，定理指出：任何一组东西，最重要的东西只占大约 $20 \%$ ，其余的只占 $8 0 \%$ 。同理，统计所有用户的职业种类及每种职业的用户数量，根据每种职业的用户数量对职业进行降序排名，对排在前 $20 \%$ 的职业给予单独编码，剩余的职业归为一类。例如，统计MovieLens中用户的职业情况，根据统计，一共21个职业，取用户数量前4的职业进行单独编码，剩余的职业归为一类，所以用户的职业编码依次为1,2.3,4,5。经过数字编码后，用户属性表示为数字编码，例如， $Q _ { i } =$ （男，23，teacher）表示为 $Q _ { i } = ( 1 , 1 , 5 )$ 。

由于K-means聚类是一种无监督学习方法，具体的聚类个数需要根据所有类簇的误差平方和(sumof squares errors,SSE)来确定，采用肘方法[15],该方法选择簇内误差平方和关于簇数曲线的拐点作为聚类数。经过K-means聚类后得到用户 $a$ 所在的用户簇 $U _ { a }$ ，如式（7）所示。

$$
U _ { a } = \{ u _ { j } | u _ { j } \in Q , j \in [ 1 , i ] \}
$$

其中： $u _ { j }$ 表示用户簇中的第 $j$ 个用户， $\boldsymbol { \mathcal { Q } }$ 表示用户集合。

# 2.2计算项目偏差分

采用目标项目被打分时的偏离项目均值的程度来衡量项目偏差，为了准确地表达项目偏差分，主要通过项目簇和用户簇对项目和用户进行过滤，计算每个项目与其所在项目簇已有评分的均值的差值。其计算过程如下：

a）在项目簇内计算增强的评分相似度。

在项目簇 $C _ { n }$ 内，根据用户-项目评分矩阵计算用户之间的增强评分相似度 $\hat { S } i m ( a , b )$ ，如式（8）所示。

$$
\hat { S } i m ( a , b ) = \frac { { \displaystyle \sum _ { n \in I _ { a b } } } ( r _ { a n } - \overline { { r } } _ { a } ^ { n } ) ( r _ { b n } - \overline { { r } } _ { b } ^ { n } ) } { \sqrt { { \displaystyle \sum _ { n \in I _ { a b } } } ( r _ { a n } - \overline { { r } } _ { a } ^ { n } ) ^ { 2 } } \sqrt { { \displaystyle \sum _ { n \in I _ { a b } } } ( r _ { b n } - \overline { { r } } _ { b } ^ { n } ) ^ { 2 } } }
$$

其中： $\overline { { r } } _ { a } ^ { n }$ 和 $\overline { r } _ { b } ^ { n }$ 分别表示 $r _ { a n }$ 和 $r _ { b n }$ 各自项目对应的 $C _ { n }$ 中的已有评分的均值。

b）在用户簇内求出目标用户的最近邻。

生成目标用户与其他用户的增强相似度，在用户簇 $U _ { a }$ 内，选取与目标用户 $a$ 相关系数最高的前 $k$ 个用户组成目标用户的最近邻 $\hat { N } ( a ) _ { k }$ ，如式（9）所示。

$$
\hat { N } ( a ) _ { k } = \{ b _ { j } \vert b _ { j } \in D e s c ( \hat { S } i m ( a , b _ { j } ) , b _ { j } \in U _ { a } ) , j \in [ 1 , k ] \}
$$

其中： $b _ { j }$ 为与用户 $\mathbf { \Delta } _ { a }$ 相关系数从高到低的第 $j$ 个用户，$D e s c ( \hat { S } i m ( a , b _ { j } ) , b _ { j } \in U _ { a } )$ 为在用户簇 $U _ { a }$ 内与用户 $a$ 的相似度由高到低的排序序列。

c）采用加权平均偏差生成项目偏差分。

在得到目标用户的最近邻后，采用加权平均偏差作为用户簇内用户 $a$ 对目标项目 $n$ 的项目偏差分，如式（10)：

$$
\mathrm { I D } _ { a n } = \frac { \underset { b \in \hat { N } ( a ) _ { k } } { \sum } \hat { S } i m ( a , b ) ( r _ { b n } - \overline { { r } } _ { b } ^ { n } ) } { \underset { b \in \hat { N } ( a ) _ { k } } { \sum } \hat { S } i m ( a , b ) }
$$

其中： $\mathrm { I D } _ { a n }$ 为用户簇内用户 $a$ 对目标项目 $n$ 的项目偏差分。

# 2.3 计算用户偏好分

项目偏差分是基于相似度生成的，但由于其受限于共同评分项，当共同评分项很少甚至不存在时，项目偏差分就失去了调节意义，因此，考虑计算用户偏好分，它反映了用户对不同项目的偏好程度。算法先从项目类型偏好分出发，挖掘用户的类型喜好，再计算主题偏好分，最后计算用户偏好分。其计算过程如下：

a)由用户类型偏好分生成用户类型喜好。

用户类型喜好是基于用户类型偏好分的，用户类型偏好分表示不同类型在用户评分总和中所占的分值，即不同类型对总分所起的贡献比例，如式（11）所示。

$$
p _ { a i } = \frac { s _ { a i } } { \displaystyle \sum _ { i = 1 } ^ { m } s _ { a i } } \sum _ { j = 1 } ^ { n } r _ { a j }
$$

其中： $p _ { a i }$ 表示用户 $a$ 对类型 $i$ 偏好分， $s _ { a i }$ 表示用户 $a$ 对类型 $i$ 的评论次数， $r _ { a j }$ 表示用户 $a$ 对项目 $j$ 的评分， $m$ 表示类型数，（204号 $n$ 表示项目数。 $s _ { a i }$ 是用户-类型评次矩阵 $S _ { a \times m }$ 的每一项， $S _ { a { \times } m }$ （204号通过用户一项目隶属矩阵 $\hat { R } _ { a \times n }$ 和项目-类型隶属矩阵 $\hat { I } _ { n \times m }$ 的对应项相乘得到。在 $\hat { R } _ { a \times n }$ 中，当用户 $a$ 存在对 $I _ { n }$ 的评分时， $\hat { r } _ { a n } = 1$ ，否则 $\hat { r } _ { a n } = 0$ 。同理，在 $\hat { I } _ { n \times m }$ 中，当 $\hat { I } _ { n \times m }$ 中存在属于类型 $m$ 的类型时， $\hat { i } _ { n m } = 1$ ，否则 $\hat { i } _ { n m } = 0$ 。如式（12)：

$$
S _ { a \times m } = \hat { R } _ { a \times n } \times \hat { I } _ { n \times m }
$$

用户的类型喜好存在喜欢和不喜欢， $\textbf { z }$ -score标准化反映了数值与均值的差异程度，其结果的正负刚好用来反映用户对不同类型的喜好，因此对用户的类型偏好分进行 $\textbf { z }$ -score归一化，如式（13）所示。

$$
\hat { p } _ { a i } = \frac { p _ { a i } - \mu _ { a } } { \sigma _ { a } }
$$

其中： $\hat { p } _ { a i } ^ { \phantom { \dagger } }$ 表示用户 $\boldsymbol { a }$ 对类型 $i$ 的喜好， ${  { \mu } } _ { a }$ 表示用户 $a$ 的所有类型偏好分的均值， $\sigma _ { a }$ 表示用户 $a$ 的所有类型偏好分的标准差。

b)依次计算主题偏好分和用户偏好分。

先计算用户对主题的偏好分，主题偏好分反映了用户对于主题的偏好程度，它是用户-类型喜好矩阵 $\hat { P } _ { a \times m }$ 和类型-主题概率矩阵 $D _ { m \times t }$ 对应项相乘得到，计算形式同式（12)，其中 $\hat { P } _ { a \times m }$ 由 $\hat { p } _ { a i }$ 组成， $D _ { m \times t }$ 是 $D _ { t \times m }$ 的转置矩阵；再将同一项目主题簇$\mathbf { C N } _ { n }$ 中的用户主题偏好分累加；最后采用平均法生成用户 $a$ 对项目 $n$ 的偏好分 $\mathrm { U P } _ { a n }$ 。如式（14）所示。

$$
\mathrm { U P } _ { a n } = \frac { \displaystyle \sum _ { t \in \mathrm { C N } _ { n } } ( \sum _ { i = 1 } ^ { m } \hat { p } _ { a i } d _ { i t } ) } { N _ { n } }
$$

其中： $d _ { i t }$ 表示 $D _ { m \times t }$ 中类型 $m$ 对应的主题 $t$ 的概率， $N _ { n }$ 表示项目 $n$ 所属 $\mathbf { C N } _ { n }$ 中的主题个数。

# 2.4生成最终预测评分

目标项目的预测评分是以目标项目所在的项目簇的已有评分的均值为基础，添加项目偏差分和用户偏好分而生成的。通过权重系数 $\lambda$ 对两种预测分进行调节，从而得到用户 $a$ 对项目$n$ 的最终预测评分 $T _ { a n }$ ，如式（15）所示。

$$
T _ { a n } = \overline { { { r } } } _ { a } ^ { n } + \lambda \mathrm { I D } _ { a n } + ( 1 - \lambda ) \mathrm { U P } _ { a n }
$$

其中： $\overline { { r } } _ { a } ^ { n }$ 表示用户 $a$ 所预测项目 $n$ 的项目簇 $C _ { n }$ 中的已有评分的均值。最终的预测评分受到权重系数 $\lambda$ 的影响，当 $\scriptstyle \lambda = 0$ 时，预测评分只受到用户偏好分的调节，当 $\lambda { = } 1$ 时，预测评分只受

到项目偏差分的调节，具体的?值需要根据实验给出。

# 2.5IUCF的算法描述

算法融合项目类型与用户属性的推荐算法 (IUCF)输入：用户-项目评分矩阵 $\boldsymbol { R } _ { a \times n }$ ，项目集合 $I$ ，用户集合 $\boldsymbol { Q }$ ，权重系数 $\lambda$ 。

输出：目标项目的预测评分 $T _ { a n }$ 0

a)先对 $I$ 进行LDA主题建模得到项目-类型主题分布 $\hat { z }$ 和主题-类型概率矩阵 $D _ { t \times m }$ ，再根据 $\hat { Z }$ 建立项目-主题隶属矩阵 $\hat { I } _ { n \times t }$ ，随后由 $\hat { I } _ { n \times t }$ 生成项目主题簇 $\mathbf { C N } _ { n }$ 和主题项目簇 $\mathbf { C T } _ { t }$ ，最后由 $\mathbf { C N } _ { n }$ 和 $\mathbf { C T } _ { t }$ 生成项目簇 $C _ { n }$ 。

b)先对 $\boldsymbol { Q }$ 中的每个用户 $Q _ { i }$ 的基本信息进行数字编码，再对编码后的$\boldsymbol { Q }$ 进行 $\mathbf { k }$ -means 聚类，最后生成用户簇 $U _ { a }$ 。

c)先在 $C _ { n }$ 内根据 $R$ 使用皮尔逊相关系数计算用户间的增强评分相似度 $\hat { S } i m ( a , b )$ ，再在 $U _ { a }$ 内根据 $\hat { S } i m ( a , b )$ 由高到低生成目标用户的最近邻$\hat { N } ( a ) _ { k }$ ，最后采取加权平均偏差法生成项目偏差分 $\mathrm { I D } _ { a n }$ 。

d)先对用户-项目隶属矩阵 $\hat { R } _ { a \times n }$ 和项目-类型隶属矩阵 $\hat { I } _ { n \times m }$ 进行矩阵相乘得到用户-类型评次矩阵 $S _ { a \times m }$ ，再由 $S _ { a \times m }$ 和 $R _ { a \times n }$ 的对应项生成用户类型偏好分 $p _ { a i }$ ，最后对 $p _ { a i }$ 进行 $z$ -score 标准化得到用户类型喜好 $\hat { p } _ { a i } ^ { \phantom { \dagger } }$

e)先由 $\hat { p } _ { a i }$ 建立用户-类型喜好矩阵 $\hat { P } _ { a \times m }$ ，将 $D _ { t \times m }$ 转置生成类型-主题概率矩阵 $D _ { m \times t }$ ，再根据 $\hat { P } _ { a \times m }$ 和 $D _ { m \times t }$ 对应项相乘生成用户主题偏好分，再累加同一 $\mathrm { C N } _ { n }$ 中的用户主题偏好分，最后采用平均法生成用户偏好分UPan °

f)以目标用户所属 $C _ { n }$ 的已有评分的均值 $\overline { { r } } _ { a } ^ { n }$ 为基础，通过权重系数λ对 $\mathbf { I D } _ { a n }$ 和 $\mathrm { U P } _ { a n }$ 进行调节，最终生成 $T _ { a n }$

# 2.6IUCF的时间复杂度分析

设项目数为 $n$ ,项目类型数为 $m$ ，主题数为 $t$ ，Gibbs 迭代次数为 $g$ ，用户数为 $a$ ，用户的基本信息数为 $q$ ， $\mathbf { k }$ -means聚类个数为 $s$ ， $\mathbf { k }$ -means迭代次数 $d$ ，最近邻个数为 $k$ 。在用户数和项目数保持一定的情况下，算法分为离线部分和在线部分。

离线部分：步骤a)：LDA主题建模生成项目簇的时间复杂度为 $O ( g n m t )$ ，步骤 b)：k-means 聚类生成用户簇的时间复杂度为 $O ( d a q s )$ ，步骤c)：在项目簇内计算增强的评分相似度的时间杂度为 $O ( a ^ { 2 } n )$ ，步骤d)：由用户类型偏好分生成用户类型喜好的时间复杂度为 $O ( a n m )$ 。

在线部分：步骤c)：在用户簇内求出目标用户的最近邻和采用加权平均偏差生成项目偏差分的时间复杂度为$O ( a \log _ { 2 } { a } + k a )$ ，步骤d)：由主题偏好分生成用户偏好分的时间复杂度为 $O ( a m t )$ ，步骤e)：生成最终评分的时间复杂度为$O ( 1 )$ 。

综上，离线部分包含ac和bd两个独立的分支，而LDA主题建模的时间复杂度远大于 $\mathbf { k }$ -means，所以时间复杂度为

$O ( g n m t + a ^ { 2 } n )$ ，在线部分时间复杂度为 $O ( a \log _ { 2 } a + a m t )$ 。

# 3 实验结果与分析

# 3.1实验数据集和实验环境

实验数据集采用美国明尼苏达大学的GroupLens小组开发并维护的MovieLens100K数据集，包含943个用户对1682部电影的10万多条评分，以及电影类型和用户属性等内容。将数据集的 $80 \%$ 作为训练集，剩余的 $20 \%$ 作为测试集，采用五折交叉验证的方式进行实验。

实验环境为IntelCorei5处理器和8G内存，Windows7x64操作系统，算法使用Python3.5语言实现。

# 3.2 实验度量标准

准确性采用平均绝对误差（MeanAbsoluteError,MAE）作为度量标准，它可以直观反映推荐质量的高低，MAE越小，证明推荐准确度越好，如式（16）所示。

$$
\mathrm { M A E } = { \frac { \displaystyle \sum _ { n = 1 } ^ { N } \left| T _ { a n } - r _ { a n } \right| } { \left| \mathrm { N } \right| } }
$$

其中： $T _ { a n }$ 表示用户 $a$ 对项目 $n$ 的预测评分， $r _ { a n }$ 表示用户 $a$ 对项目 $n$ 的实际评分， $\mathrm { ~ N ~ }$ 表示预测的项目数。

# 3.3算法相关参数确定实验

算法中需要确定的参数包括K-means聚类个数、LDA聚类主题数目和权重系数λ。

# 3.3.1K-means聚类个数的确定

为了确定合适的 $\mathbf { k }$ -means聚类数，采用肘部方法，依次选取聚类的个数为2、3、4、5、6、7、8，分别计算SSE，结果如图2所示。

![](images/2b63b010255812ce77a5e849c3a58331de756c17be1182f2b0930942ad2aef35.jpg)  
图2不同聚类个数下的MAE值变化

图2中，随着聚类数目的增加，SSE的值依次下降。从图中可以看出，当聚类个数从2到3时，SSE的值下降了大约300，而聚类个数从3开始，SSE的值下降速度明显小于300，同时3所对应的点也刚好为肘方法的拐点，因此，当聚类个数为3时，聚类效果最好。

# 3.3.2LDA聚类主题数目的确定

为了确定合适的LDA聚类的主题数目，设置 $\lambda { = } 1$ ，即仅通过项目偏差分的算法去确定最佳主题数目，固定近邻数目为10、30、50，采用Gibbs抽样方法，依次选取主题数目为12、

13、14、15、16、17、18 进行实验，同时根据文献[16]的实践进行参数设置， $\alpha { = } 5 0 / T$ ， $\beta = 0 . 0 1$ ，如图3所示。

![](images/653d7989e406cafeabba18b3cd2fbebcc83d1acd979558028ae86ac25e5db1f4.jpg)  
图3不同主题数下的MAE值变化

图3中，在近邻数目为10、30、50的时候，当主题数目为15时，算法MAE最小，表明不管在何种近邻数目下，设置主题数目为15，更加有利于保证算法的推荐效果。因此，在算法中主题数目的最佳值为15。

# 3.3.3权重系数的确定

为了确定最佳的权重系数?，分别设置近邻数目为10、30和50，通过调节权重系数λ，计算IUCF算法在不同λ值下的MAE，如图4所示。

![](images/d50d4e66141ed9620d4de4fd8bd7b912448692b83d7256c59901f44255afbd66.jpg)  
图4不同权重系数下的MAE值变化

从图4可以看出，对于近邻数目为10、30、50，当 $\lambda { = } 0 . 6$ 时，IUCF算法的MAE最小，算法的推荐质量最佳。因此，实验中权重系数λ值取为0.6。

# 3.4算法对比实验

为了充分比较UCF 算法与其它算法在推荐准确度上的差别，分别选择4种算法作为对比算法进行实验，包括传统的于用户的协同过滤算法（UCF）和基于项目的协同过滤推荐算法(ICF)，文献[4]所提出的基于特征转移和概率矩阵分解的推荐算法（FTMF)，文献[11]所提出的采用信任网络增强的协同过滤算法（ECFATN)，实验结果如图5所示。

图5中，相较于传统的UCF和ICF，IUCF在MAE上明显下降，表明本文算法确实提高了传统协同过滤算法的准确度。对比ECFATN，在不同近邻数目下本文算法MAE更低，表明本文算法更优，但是对比FTMF，当近邻数目增加到30以后，IUCF的MAE要高于FTMF，这可能是由于项目偏差分中过多的近邻数目反而降低了算法的准确度，但是在近邻数目少于30时，IUCF的MAE要低于FTMF，表明本文算法在近邻数目较低时，提高了算法的准确度。

![](images/891ae1d5f8edad9dab5589a5a41fc0a6f21df8e43a37f236813aa67ef0aace49.jpg)  
图5不同算法下的MAE 值变化

为了验证IUCF算法与其他算法在时间效率上的差别，分别选择UCF和ICF进行对比实验，分别对20、40、60名用户产生推荐，不同算法的运行时间对比如表1所示。

表1算法运行时间对比表  

<html><body><table><tr><td>用户数</td><td>UCF ICF</td><td></td><td>IUCF</td></tr><tr><td>20</td><td>3.79</td><td>4.15</td><td>4.03</td></tr><tr><td>40</td><td>6.12</td><td>7.82</td><td>6.92</td></tr><tr><td>60</td><td>10.87</td><td>12.54</td><td>11.32</td></tr></table></body></html>

从表1中可以看出，IUCF算法在时间效率上要明显优于传统的基于项目的协同过滤推荐算法，但是与基于用户的协同过滤推荐算法相比，IUCF算法的运行时间较长，这是因为基于项目的协同过滤相似度的计算要在线完成，而基于用户的协同过滤的相似度计算可以离线完成。

综上，IUCF算法在推荐准确度和时间效率上得到了一定的改善。

# 4 结束语

准确衡量项目偏差与用户偏好对于推荐质量有较大影响，通过限定计算范围，排除不相关的项目和用户，有效地缓解协同过滤推荐中项目和用户间关联因素的相互影响导致的准确度不高的问题，取得了较好的效果。

下一步可以采用自然语言处理技术，从用户的评论中提取情感词，进而挖掘项目偏差与用户偏好，进一步提高推荐系统的准确度，同时使推荐结果更具有说服力。

# 参考文献：

[1]Chen Wei,Hsu W,Lee ML.A unified framework for recommendations based on quaternary semantic analysis [C]//Proc of the 34th international ACM SIGIR conference on Research and development in Information Retrieval.New York:ACMPress,2011:1023-1032.   
[2]Shi Min,Liu Jianxun,Zhou Dong,et al.A probabilistic topic model for mashup tag recommendation [C]// Proc of IEEE International Conference on Web Services.2016: 444-451.   
[3]Qiao Zhi,Zhang Peng,He Jing,et al. Combining geographical information of users and content of items for accurate rating prediction [C]//Proc of the 23rd International Conference on World Wide Web.New York: ACM Press, 2014: 361-362.   
[4]ZhaoZhilin，WangChangdong，WanYuanyu，etal.FTMF: recommendation in social network with feature transfer and probabilistic matrix factorization [C]// Proc of International Joint Conference on Neural Networks.2016:847-854.   
[5]Zhou Xiuze,Wu Shunxiang. Rating LDA model for collaborative filtering [J]. Knowledge-Based Systems,2016,110:135-143.   
[6]原福永，温志慧，梁顺攀，等．融合项目分类的加权 Slope One算法[J]. 小型微型计算机系统，2017，38(09):2090-2095.(Yuan Fuyong，Wen Zhihui,Liang Shunpan,et al.Integrating Item Category Into Weighted Slope One Algorithm [J].Journal of Chinese Mini-Micro Computer Systems,2017,38 (09): 2090-2095.)   
[7] 刘慧婷，陈艳，肖慧慧．基于用户偏好的矩阵分解推荐算法[J].计算 机应用，2015,35(S2):118-121.(Liu Huiting,Chen Yan, Xiao Huihui. Matrix factorization recommendation algorithm based on users’preference [J]. Journal of Computer Applications,2015,35 (S2):118-121.)   
[8]HerlockerJL,KonstanJA,BorchersA,etal.Analgorithmic framework forperforming collaborative filtering[C]// Proc of International ACM SIGIR Conference on Research and Development in Information Retrieval. NewYork:ACMPress,1999:230-237.   
[9]BleiDM,NgAY,JordanMI.LatentDirichlet allocation[J]. Journal of Machine Learning Research,2003,3 (3): 993-1022.   
[10] Casella G, George EI.Explaining the Gibbs sampler[J]. The American Statistician,1992,46 (3): 167-174   
[11]李熠晨，陈莉，石晨晨，等．采用信任网络增强的协同过滤算法[J]. 计算机应用研究，2018,35(01):116-120.(Li Yichen,ChenLi，Shi Chenchen,et al.Enhanced collaborative filtering adopting trust network [J]. Application Research of Computers,2018,35 (01): 116-120. )   
[2]何明，孙望，肖润，等．一种融合聚类与用户兴趣偏好的协同过滤推荐 算法[J].计算机科学,2017,44(S2):391-396.(He Ming，Sun Wang, Xiao Run，et al.Collaborative filtering recommendation algorithm combining clustering and user preferences [J].Computer Science,2017, 44 (S2): 391-396. )   
[13]罗淳．关于人口年龄组的重新划分及其蕴意[J].人口研究，2017，41 (05):16-25.(Luo Chun.Re-partitioning population age group and its implications [J].Population Research,2017,41 (05): 16-25.)   
[14] Wood JC,Wood M C. Joseph M. Juran: Critical evaluations in business and management [M].[S.1.] $\because$ Psychology Press,2005.   
[15] Bholowalia P,Kumar A. EBK-means: A clustering technique based on elbow method and k-means in WSN[J]. International Journal of Computer Applications,2014,105(9).   
[16]Griffiths TL,SteyversM.Finding scientific topics[J].Proceedingsof the National academy of Sciences,2004,101 (suppl1): 5228-5235.