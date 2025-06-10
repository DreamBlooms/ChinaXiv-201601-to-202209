# 受限玻尔兹曼机与加权SlopeOne的混合推荐算法研究

沈学利，赫辰皓，孟祥福(辽宁工程技术大学 电子与信息工程学院，辽宁 葫芦岛 125105)

摘要：针对传统协同过滤算法所面临的稀疏性及预测准确度不高的问题，提出一种基于受限玻尔兹曼机与加权Slope One的混合推荐算法。首先通过受限玻尔兹曼机对评分矩阵的初步填充，缓解数据的稀疏性问题；然后通过一种混合项目相似度计算方法，引入项目属性信息；最后通过加权 Slope One 算法的二次预测，提升推荐效果。在MovieLens100K数据集上的实验表明，两种算法的结合提高了推荐的准确度。

关键词：受限玻尔兹曼机；加权SlopeOne；修正余弦相似度；jaccard 相似度 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.08.0619

# Research on hybrid recommendation algorithm of restricted Boltzmann machine and weighted Slope One

ShenXueli,He Chenhao,MengXiangfu (Schoolof Electronic &InformationEngineering,Liaoning Technical University,HuludaoLiaoning1251o5,China)

Abstract:Aiming atthe sparseness andlow predictionaccuracyof traditional colaborative filtering algorithms,this paper proposed a hybrid recommendation algorithmbased on restricted Boltzmann machine and weighted Slope One.Firstly, it use the preliminary fillingof thescoring matrix bythe restricted Boltzmann machine toallviate the sparseness problemof thedata.Then,it introduced theprojectatribute informationthroughahybrid projectsimilaritycalculation method.Finally it adoptedthe second prediction by the weighted Slope One algorithm to improve the recommended effct.Experiments on the MovieLenslOoK dataset showthat thecombinationof the twoalgorithms increases theaccuracyofthe recommendation. Key Words: restricted Boltzmann machine; weighted slope one; adjusted cosine similarity; jaccard similarity

# 0 引言

随着互联网技术与应用的飞速发展，人类开始步入大数据时代，面对越来越繁杂的数据量，如何筛选数据成为了网络服务提供商以及互联网用户的共同难题。个性化推荐系统便是一种主要的数据筛选的途径。如今应用最广泛的个性化推荐方式为协同过滤算法[1]，而将两种协同过滤算法相结合的混合推荐算法如今成为协同过滤算法的一个重要的研究方向[2]。

协同过滤算法存在着数据稀疏性的问题。即在实际应用中，由于用户仅为少数的项目打分，用户一项目评分矩阵往往十分稀疏，导致算法的推荐准确度不高。将两种算法相结合的混合推荐算法可以很好地缓解这一问题。SlopeOne 算法是一种常见的基于用户的协同过滤算法，该算法具有简洁高效等特点，能充分考虑到评分矩阵中用户间与项目间的联系，在数据稠密时可取得较其他传统协同过滤算法更好的推荐结果[2]。但在数据稀疏时推荐效果不理想。针对此问题，研究者提出了使用奇异值分解（SVD）等方法[3-6]，对评分矩阵中缺失值进行填充，再通过 SlopeOne 算法进行预测。随着神经网络模型在协同过滤中的应用，神经网络模型较传统协同过滤算法，能更好地拟合数据，深层挖掘数据间的关系。受限玻尔兹曼机（RBM）是一种成功应用在推荐系统中的神经网络模型。实验证明，RBM模型取得了优于SVD等模型的推荐效果[7]。因此本文将采用受限玻尔兹曼机对评分矩阵加以填充。另外，研究者将相似度关系引入到 Slope One 算法中[8.9]，提出加权 Slope One 算法，有效解决了冷启动问题,并提高了预测准确度。

综上，本文将对以上两种模型加以结合及改进，提出一种基于项目的实值受限玻尔兹曼机与加权SlopeOne的混合推荐算法（item-based real value RBM&wighted Slope One,IR-RBM-WSO)。

# 1 受限玻尔兹曼机研究现状

首先，假设在一个推荐系统中，包含 $\mathrm { ~ m ~ }$ 个用户以及n个项目，用户对项目的评分为 $1 { \sim } \mathbf { k }$ 间的整数，由此可建立一个用户一项目评分矩阵 $\mathbf { R } _ { \mathrm { m ^ { * } n } }$ 。在项目属性信息中，包含s个项目分类属性。比如，在MovieLens数据集中就提供有电影的18 种分类信息。每一个项目属于其中一种或多种，是否属于某种分类分别用1与0表示。由此可建立项目一属性矩阵 $\mathrm { I _ { n ^ { * } s } }$ 。下文将基于此例对算法进行说明。

受限玻尔兹曼机（RBM）是一种具有两层结构的神经网络模型：可见层表示评分数据，隐层作为特征提取器提取数据间特征[10]。特点为层内无连接，层间全连接。2007 年，Salakhutdinov等人[7首次将受限玻尔兹曼机应用于推荐系统中，针对推荐系统中的1\~k的整数评分范围，将原始RBM模型中可见单元从二值变量改变为一个含有k个二值单元的softmax单元。此模型中每个评分均需要 $\mathbf { k }$ 个单元来表示，使模型参数过于复杂，训练时间较长。2013年，Georgiev 等人[1提出一种同时基于用户与项目的 RBM 模型，并将评分数值直接应用在可见层。该模型降低了算法的复杂度，但可解释性较差。2015年，何洁月等人[12]在实值RBM基础上将社交信息引入到模型中，缓解了RBM的数据稀疏性问题，提高了推荐的效果；但引入的社交信息适用范围较小，并且社交信息的稀疏性问题使推荐效果不够理想。2017年，霍淑华[13]提出一种基于项目的 RBM 模型，取得了优于基于用户RBM模型的推荐效果。

本文将在利用实值的RBM模型基础上，以项目的角度建立受限玻尔兹曼机模型，提出一种基于项目的实值受限玻尔兹曼机模型（IR_RBM)，并在相似度计算过程中引入在推荐系统中更加普遍存在的项目属性信息来对预测结果加以改进。

# 2 本文算法

本文提出一种采用实值形式的基于项目受限玻尔兹曼机模型（item-basedrealvalueRBM，IR_RBM)，结构如图1所示。对每一个项目均建立一个IR-RBM模型，每个模型的可见层中，包含 $\mathrm { ~ m ~ }$ 个数值单元，用于表示每一个用户对此项目的打分。可见层节点数值为 $0 { \sim } \mathbf { k }$ 之间的整数，其中0表示此用户未对该项目打分，已有评分用实值表示。

![](images/4e2b12112f3062a9b52a4caed9c2a81238c20ca2d3f671a3ea7f874d28483988.jpg)  
图1 IR-RBM模型Fig.1 IR-RBMmodel

由于直接使用实值表示评分，在原RBM能量模型基础上加入一个二次方项，此模型的能量计算公式为

$$
\begin{array} { l } { { \displaystyle \mathrm { E } ( \nu , h | \theta ) = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { \mathrm { m } } { \nu _ { i } } ^ { 2 } - \sum _ { i = 1 } ^ { m } { \sum _ { j = 1 } ^ { n } { W _ { i j } } h _ { j } \nu _ { i } } ^ { - } } } \\ { { \displaystyle \sum _ { i = 1 } ^ { n } { \nu _ { i } } c _ { i } - \sum _ { j = 1 } ^ { m } { h _ { j } } b _ { j } } } \end{array}
$$

其中：bj为第j个隐节点的偏置，初始值为 $0 ^ { [ 1 4 ] }$ ；ai为第i个可见单元的偏置； $\mathrm { W _ { i j } }$ 为第i个可见单元与第 $\mathrm { j }$ 个隐单元之间的连接权重。初始化为满足正态分布N（0.0.01）的随机数。

根据能量公式，则当评分数据输入模型后，第j个隐单元的激活概率为

$$
\mathsf { p } ( h _ { j } = 1 | \nu , \theta ) = \sigma ( b _ { j } + \sum _ { i } \nu _ { i } W _ { i j } )
$$

其中： $\sigma$ 为激活函数， $\sigma ( x ) = 1 / 1 + \exp ( - x )$ 。

当隐单元的状态确定时，第i个可见单元的值为

$$
\nu _ { i } = c _ { i } + \sum _ { i } h _ { j } W _ { i j }
$$

参数的更新方式使用对比散度方法，参数更新准则为

$$
\begin{array} { r l } & { \Delta \mathsf { W } _ { \mathrm { i j } } = \lambda ( \left. \nu _ { i } h _ { j } \right. _ { d a t a } - \left. \nu _ { i } h _ { j } \right. _ { r e c o n } ) } \\ & { \Delta \mathsf { a } _ { i } = \lambda ( \left. \nu _ { i } \right. _ { d a t a } - \left. \nu _ { i } \right. _ { r e c o n } ) } \\ & { \Delta \mathsf { b } _ { i } = \lambda ( \left. h _ { j } \right. _ { d a t a } - \left. h _ { j } \right. _ { r e c o n } ) } \end{array}
$$

其中： $\lambda$ 为学习率。本文实验通过Adam方法来更新学习率，以加快模型收敛速率。 $\lambda$ 初始值设置为 $0 . 0 0 1 ^ { [ 1 5 ] }$ 。 $\left. \bullet \right. _ { r e c o n }$ 为一次重构后模型定义的分布。建立IR-RBM模型的伪代码见算法1。算法1基于IR-RBM模型的算法的伪代码IR-RBM算法伪代码输入：评分矩阵 $\mathbf { R } _ { \mathrm { m ^ { * } n } } .$ 0输出：利用IR-RBM模型填充后的评分矩阵。建立IR-RBM模型1 for $\mathbf { t } = 1$ :iteration DO://iteration为IR-RBM迭代次数，此处取iteration为202 for $\mathrm { i } = 1 : \mathrm { m D O }$ 3可见单元状态已知，利用式（2）更新隐单元状态4 隐单元状态已知，利用式（3）更新可见单元的值5利用式（4）更新参数6 end for7end for8 for each ${ \bf R } _ { \mathrm { i j } } = 0$ in $\mathbf { R } _ { \mathrm { m ^ { * } n } }$ DO:9利用训练好的IR-RBM为预测 ${ \bf R } _ { \mathrm { i j } }$ 的分数10 end for

# 2.1相似度算法

本文提出的复合相似度计算方法，首先通过修正余弦相似度方法计算填充后的评分矩阵中项目间相似度，虽然此方法可以较好地挖掘评分矩阵中的项目间相似关系，但其忽略了项目本身属性之间的相似关系，在实际应用中，用户往往会对同一种类型的项目有着相似的喜好程度，并给出相似的打分；其次基于此种情况，本文提出一种融合信息熵的Jaccard相似度[18]计算方法，挖掘项目属性间的相似关系，通过信息熵对不同的项目属性赋予不同的权重，再采用jaccard算法计算项目间的属性相似度；最后将项目评分相似度及项目属性相似度作为项目最终相似度，将其作为SlopeOne 算法的权值。

# 2.1.1修正余弦相似度算法

修正余弦相似度是在余弦相似度的基础上，加入去中心化思想，通过减去平均值来修正不同用户的评分尺度问题。基于项目的修正余弦相似度计算公式如式（5）所示。其中：$R _ { i , c }$ 表示用户 $\mathrm { ~  ~ c ~ }$ 对项目i的评分； $\overline { { R _ { i } } }$ 、 $\overline { { R _ { j } } }$ 表示所有用户对项 $R _ { i , c }$ 表示用户c对项目i的评分， $\overline { { R _ { i } } }$ 、 $\overline { { R _ { j } } }$ 表示所有用户对项目i和j打分的平均值。

$$
{ \sin } _ { \mathrm { A c } } ( \mathrm { i , j } ) { = } \frac { \sum _ { { u \in \mathrm { U } _ { \mathrm { i } } } } ( R _ { u , i } - \overline { { R _ { i } } } ) ( R _ { u , j } - \overline { { R _ { j } } } ) } { \sqrt { \sum _ { { u \in \mathrm { U } _ { i } } } ( R _ { u , i } - \overline { { R _ { i } } } ) ^ { 2 } } \sqrt { \sum _ { { u \in U } _ { j } } ( R _ { u , j } - \overline { { R _ { j } } } ) ^ { 2 } } }
$$

修正余弦相似度的取值为[-1,1]。考虑到本文将会使用此相似度作为权值使用，故需将其映射到[0,1]区间内。映射公式如式（6）所示。

$$
s i m _ { h } ( i , j ) = \frac { 1 + s i m _ { A C } ( i , j ) } { 2 }
$$

2.1.2融合信息熵的改进Jaccard相似度算法

Jaccard相似度是一种用来描述两个集合间相似度的一  
种方法，适用于高度离散维度特征向量的计算[16]。计算公式$J ( A , B ) = \frac { \left| A \cap B \right| } { \left| A \cup B \right| }$ AUB，其中A、B为两个n维向量，所有维度的  
取值为1或0，用来表示是否包含该属性。式中分子表示AB  
中所有取值相同的维度个数，分母表示AB并集的维度个数。

若直接将其应用到推荐系统中会出现相似度衡量不准确的问题。针对单一维度来说，设 $\mathbf { a } _ { \mathrm { i } }$ ， $\mathbf { b } _ { \mathrm { i } }$ 分别为A、B中第i个维度的取值，则在此维度 $A \cap B$ 成立包含有两种情况：ai、bi同时为1，或者ai、bi同时为O。即Jaccard认为ai、bi同时为0是一种相似的情形，但考虑到推荐系统中ai、bi取值的实际意义为：项目A与B均不属于i类型，这并不能作为两者相似的依据。并且在实际的数据集中，一个项目只会属于多种分类属性中的少数几个，即ai、bi同时为0的情况会大量存在。比如，假设用6种属性来划分项目，其中项目A仅属于属性1，属性向量为{1,0.0.0.0,0}，项目B仅属于属性2，属性向量为{0,1,0.0.0.0}，通过jaccard系数计算得出的相似度为 $6 6 . 7 \%$ ，但从实际意义考虑，两者分属不同的类型，可认为相似度为0。

针对此问题，本文将对Jaccard相似度算法进行修改，对于单一维度，一共存在四种可能情况，分别为：

p：ai、bi同时为1；q：ai为1且bi为0;

r：ai为0且bi为1；s：ai、bi同时为0。

为了使相似度计算更符合实际情况，本算法只将 $\mathrm { ~ \bf ~ P ~ }$ 归为相似情况，则A与B的相似度表示为

$$
s i m _ { j } = \frac { | p | } { | p | + | { \bf q } | + | { \bf r } | + | { \bf s } | }
$$

其中：表示符合此种情况维度的个数。

另外，Jaccard相似度计算中，每种属性的贡献度是等价的，忽略了不同属性对项目区分的差异性。比如，若大多数（或很少）的项目属性中都包含属性i，那么属性i对项目的区分度就会很低，应相对降低此属性的权值。针对此问题，本文将引入信息熵来对不同的属性加以区分，信息熵可以用来量化一个系统的混乱程度，对于0,1的二元值情况来说，0与1的单元个数差值越大，表示变量的不确定性越小，熵值越小，熵值越低；反之，差值越小，系统越稳定，熵值越大。对用户一属性矩阵的每一列，计算其1值出现的概率，通过信息熵计算公式（8）计算此项目的信息熵权值。

$$
\begin{array} { r } { H ( \alpha _ { i } ) = - p ( \alpha _ { i } ) \times \log _ { 2 } p ( \alpha _ { i } ) - ( 1 - p ( \alpha _ { i } ) ) \times \log _ { 2 } ( 1 - p ( \alpha _ { i } ) ) } \end{array}
$$

其中：p $\mathbf { \left( a _ { i } \right) }$ 为 $\mathbf { a } _ { \mathrm { i } }$ 值为1的概率。之后，通过信息熵的权值来计算两个项目间的相似度。

综上，本文提出的结合信息熵的改进Jaccard 相似度计算公式为

$$
s i m _ { j } ( i , j ) = \frac { \sum _ { a _ { n } \in p } H ( \alpha _ { n } ) } { \sum _ { a _ { m } \in p , q , r , s } H ( \alpha _ { m } ) }
$$

2.1.3项目综合相似度算法

本文采用两种相似度平均值作为项目间相似度。计算公式如（10）所示.

$$
\mathrm { s i m } _ { \mathrm { i t e m } } ( i , j ) = \frac { s i m _ { h } ( i , j ) + s i m _ { j } ( i , j ) } { 2 }
$$

算法2项目综合相似度伪代码

输入：填充后的评分矩阵 $\mathbf { R } _ { \mathrm { m ^ { * } n } }$ 项目属性矩阵 $\mathbf { I } _ { \mathrm { n ^ { * } s } }$ 。项目集为V，用户集为 $\mathbf { M }$ ，属性集为P.

输出：项目相似度矩阵 $\mathbf { S } _ { \mathbf { n } ^ { * } \mathbf { n } }$ 。

Begin  
1 for each i in PDO:  
2 在I中统计pi中0与1出现概率  
3利用式（8）计算pi信息熵  
4 end for  
5 for each i,j in V( $\mathsf { i ! = j }$ DO:  
6 在R中取列向量Ri、 ${ \bf R } _ { \mathrm { j } }$   
7利用式（6）计算 $\mathrm { { s i m } _ { \mathrm { h } } }$ （ $( \mathrm { R } _ { \mathrm { i } } , \mathrm { R } _ { \mathrm { j } } )$ ）  
8 在P中，取行向量 $\mathrm { \sf P _ { i } }$ 、 $\mathbf { P _ { j } }$   
9利用式（7）计算 $\mathrm { { s i m } _ { h } }$ （pi,Pj)  
10 利用式（10）计算 simitem（i,j)  
11 在矩阵 S中，更新 $\mathrm { \Delta S _ { i j } = S _ { j i } = }$ simitem (i.j)  
12 end for

# 2.2 加权 Slope One 算法

本文使用加权SlopeOne 算法来计算最终的预测结果。SlopeOne 算法是一种基于线性回归思想的推荐算法，由偏差计算公式和预测公式组成。基于项目的偏差计算公式如下：

$$
\mathrm { d e v _ { i j } } = \frac { \sum _ { { \boldsymbol { u } } \in S _ { i j } } ( { \boldsymbol { r } } _ { { \boldsymbol { u } } i } - { \boldsymbol { r } } _ { { \boldsymbol { u } } j } ) } { \left| S _ { i j } \right| }
$$

其中： ${ \mathrm { \ R } } _ { \mathrm { u i } }$ 表示用户i对项目 $\mathbf { u }$ 的评分； $\mathrm { S _ { i j } }$ 表示同时为该项目打分的用户i与 $\mathrm { ~ j ~ }$ 的集合。由于本文使用的为填充完整的评分矩阵，所以 $\mathrm { S _ { i j } }$ 在这里等于用户集 $\mathbf { M }$ 。

融入项目相似度 $\mathrm { s i m } _ { \mathrm { i t e m } } ( i , j )$ 的 Slope One 预测公式如式（12）所示。

$$
p r e ( u , i ) = \frac { \sum _ { \substack { j \in \mathrm { S } ( \mathrm { u } ) } } ( r _ { u j } + d e \nu _ { i j } ) \times s i m _ { i t e m } ( i , j ) } { \sum _ { \substack { j \in \mathrm { S } ( \mathrm { u } ) } } s i m _ { i t e m } ( i , j ) }
$$

其中：S(u)表示通过项目相似度选出的相似度最大的 $\mathbf { N }$ 个项目集合。

算法3Slope One 预测伪代码

输入：评分矩阵 $\mathbf { R } _ { \mathrm { m ^ { * } n } } .$ 项目相似度矩阵 $S _ { \mathrm { n ^ { * } n } } .$ 用户集 $\mathbf { M }$ 定义的最大近邻个数 $\mathbf { k }$ ，需评分项 ${ \mathrm { \sf R } } _ { \mathrm { u i } }$ 。

输出：预测评分pre(u.i)。

Begin

1S中取列向量 $S _ { \mathrm { u } }$ ，从中选取 $\mathbf { k }$ 个相似度最大近邻项目，组成近邻项目集合 S(u)

2 for each u in S(u) DO:

3 for each j in $\mathbf { M } ( \mathrm { j ! = i } )$ DO:   
4 利用式（1\~11）求devij   
5 end for   
6利用式（1\~12）求pre(u,i)   
7 end for

# 3 实验结果及分析

# 3.1数据集及评价指标

本节将通过实验来证明本文所提出算法的精确度，以及模型参数对实验结果的影响。实验采用MovieLens100K数据集中的用户一项目评分信息以及项目一属性信息来进行实验验证。其中，用户一项目评分信息存放在u.data文件中，包含943名用户对1682个电影的十万条评分数据；项目一属性信息存放在u.item文件中，包含1682个电影的属性信息，实验将提取其中的18个电影类别信息作为项目一属性矩阵。在用户一项目评分中，抽取 $20 \%$ 的评分数据作为测试数据集。

实验使用平均绝对误差（MAE）及均方根误差（RMSE）作为评价指标。

MAE定义如式（13）所示。

$$
\ M A E { = } \frac { \sum _ { i j } \left| R _ { i j } - R _ { i j } \right| } { N }
$$

RMSE 定义如式（14）所示。

$$
R M S E = \sqrt { \frac { \sum _ { i j } \left| R _ { i j } - R _ { i j } \right| ^ { 2 } } { N } }
$$

# 3.2实验过程与结果分析

3.2.1IR_RBM模型中隐单元数量实验本实验将建立IR-RBM模型对测试集进行预测，以探究

IR_RBM中隐单元数量对矩阵填充效果的影响，并确定一个最佳隐单元数量。在IR-RBM模型中，使用训练次数iteration $\scriptstyle 1 = 8 0$ ，实验结果如图2所示。

![](images/cfd97b123106226e527a9eb17f3d9c4bb10538c2247391062ec7a8d0b0922740.jpg)  
图2不同隐单元数量下IR-RBM模型的MAE值Fig.2MAE value of IR-RBM model with differentnumber ofhidden units

从图中可知，随着隐单元数目的增加，IR-RBM模型的MAE值呈现出先降后增的趋势，在隐单元数量取值100时，取得最优推荐效果。在隐单元数目大于100时推荐效果下降，是因为作为特征提取功能的隐单元数目过大而产生了过拟合现象。故本文实验中IR-RBM模型中的隐单元个数将固定为100。

# 3.2.2IR-RBM模型训练集训练次数实验

本实验将探究IR-RBM 模型中，iteration 参数对矩阵填充效果的影响，并确定一个最佳的iteration数值。实验结果如图3所示。图中横坐标为训练集在IR-RBM中的训练次数，纵坐标为评价指标MAE值。从图中可以发现，在iteraiton值大于20时，模型趋于收敛，在80处取得最佳推荐效果。

![](images/da99ceacc6f6f995b62523c03a2eee5f6bc9f63f326018a6653244bebdf03577.jpg)  
图3不同训练次数下IR-RBM模型的MAE值

本实验将建立在本文所提出的IR-RBM-WSO算法，研究最近邻居数目K对推荐准确度的影响。实验结果如图4所示。

由图可见，模型的推荐效果随着近邻数目的增加呈现出先降低而后稳定的趋势。由于模型的推荐准确率在近邻数$\mathbf { k } { > } 8 0$ 时已趋于稳定，所以本文将采用 $\scriptstyle \mathbf { k } = 8 0$ 作为实验参数。

# 3.2.4本文相关算法对比实验

本实验将建立在训练次数iteration $\scriptstyle 1 = 8 0$ 、近邻个数 $\scriptstyle \mathbf { k } = 8 0$ 的情况下，对本文所提出的IR-RBM-WSO算法效果与其组成算法进行对比，并选取了以下四组模型进行对比，分别测试其MAE、RMAE值：

a)Slope One 算法。

b)基于本文相似度的加权SlopeOne算法（WSO）。

c)基于项目的受限玻尔兹曼机模型（I-RBM)。

d)利用 SVD 进行矩阵填充，并采用本文加权Slope One算法进行二次预测的算法（SVD-WSO）。

实验结果如图5、6所示。

![](images/e9c44b8d63ea3e01a11785814ae46c56e0bbdf3a2f8108752df1f0943486c1b5.jpg)  
图4不同近邻个数下IR-RBM-WSO 算法的MAE值Fig.4MAE value of IR-RBM-WSO algorithm under differentneighbors

0.90.85WAA 0.8 m0.750.7 10.65SVD-WSO IR-RBM-WSO对比算法

![](images/00363dd3d3a4b1684419026da241f04087e759a36378aae9ff59b6c323527329.jpg)  
Fig.3MAE value ofIR-RBMmodel under different iteratior 3.2.3最近邻居数目k对推荐效果的影响   
图5相关算法对比实验MAE图  
Fig.5Related algorithm comparison experimentMAE diagram   
图6相关算法对比实验RMSE图  
Fig.6Related algorithm comparison experiment RMSE diagram

分析两图中数据可得以下结论：加权SlopeOne算法在推荐准确度上优于原始SlopeOne 算法，MAE与RMSE 值分别较后者提升了 $4 . 8 \%$ 与 $8 . 3 \%$ ，说明本文相似度的引入在一定程度上缓解了SlopeOne 算法的数据稀疏性问题，推荐效果得到了一定的提升；IR-RBM-WSO模型的推荐效果优于其组成算法I-RBM与WSO算法，MAE值分别提升了 $7 . 4 9 \%$ 与$1 0 . 7 1 \%$ ，RMSE值分别提升了 $8 . 7 5 \%$ 与 $12 . 6 3 \%$ ，说明将两种算法相结合，很好地弥补了各自的缺陷，提高了预测准确度；IR-RBM-WSO较SVD-WSO，MAE与RMSE值分别提升了$3 . 8 9 \%$ 与 $4 . 1 9 \%$ ，说明本文所提出的IR-RBM模型对矩阵填充的效果较SVD有所提高。

# 3.2.53.2.5本文算法与已有算法对比实验

为了进一步验证本文算法的性能，将本实验与文献[11]所提出的UI-RBM模型以及文献[17]所提出的基于用户与项目，并引入属性信息层的IC-CRBMF模型进行对比，进一步验证本文方案的性能。实验结果如图7所示。

![](images/b22718d1f15531cb8331a61927dcf0b7b42f3b66b69ee055807ae51665a26ae0.jpg)  
图7与其他算法对比实验MAE 图

实验表明，在本数据集上，IR-RBM-WSO模型的推荐效果优于IC-CRBMF模型，最佳MAE值提升了 $3 . 8 \%$ ; UI-RBM模型收敛速度较慢，在对比图中未达到最优效果，推荐效果弱于本文算法，在iteration $\scriptstyle 1 = 5 0 0$ 时，MAE值收敛在0.690,仅比本文算法低0.002，但由于其需训练次数较高，并且其模型同时对用户及项目建模，模型较复杂，所以本文算法的训练时间远小于该算法。

# 4 结束语

本文提出一种混合推荐算法，将受限玻尔兹曼机与加权SlopeOne有机结合在一起。通过受限玻尔兹曼机对矩阵缺失值的填充，缓解了矩阵稀疏度问题；通过SlopeOne 算法进行二次预测，提升了模型的推荐效果。另外，通过一种复合相似度计算方法，挖掘项目属性相似度，并将其与评分相似度相结合，更好地反映了项目间的相似关系。通过对比实验证明，本文提出的混合推荐算法得到了较好的推荐效果。但是本算法并不能很好地解决冷启动问题，在此方面的改进将是下一步的工作方向，另外，将对深度学习模型进行实验[18,19]，以进一步提升推荐效果。

# 参考文献：

[1]Duan M.Collaborative filtering recommendation algorithm [J]. International Journal of Security & Its Applications,2015,9(7): 99-108.   
[2]宋瑞平．混合推荐算法的研究[D].兰州：兰州大学，2014.(Song Ruiping.Research of hybrid recommendation algorithm [D].Lanzhou: Lanzhou University,2014)   
[3]Yehuda K,Robert B,Chris V. Matrix factorization techniques for recommender systems [J].IEEE Computer Society，2009,42 (42): 30-37.   
[4]Jing Huijuan,Liang Anchun,Lin Shoude,et al.A transfer probabilistic collective factorization model to handle sparse data in collaborative filtering [C]//Proc of IEEE International Conference on Data Mining. 2015:250-259.   
[5]向小东，邱梓咸．基于SlopeOne算法改进评分矩阵填充的协同过滤 算法研究[J].计算机应用研究，2019,36(5)：1-5.(Xiang Xiaodong, QiuZixiang.Research on collaborative filtering algorithm based on slope one algorithm to improve score matrix filling [J].Application Research of Computers,2019 (5): 1-5)   
[6]杜倩．基于聚类的加权 Slope One 推荐技术研究[D]．北京：北京工 业大学，2Ol6.(Du Qian.Reasearch on the weighted Slope One recommendation technology based on clustering [D]. Beijing: Beijing University of Technology,2016.)   
[7]Salakhutdinov R,Mnih A,Hinton G. Restricted Boltzmann machines for collaborative filtering [C]//Proc of the 24th International Conference Maching Learning.2007: 791-798.   
[8] Song Shiyu，Wu Kejia. A creative personalized recommendation algorithm-user-based Slope One algorithm [C]//Proc of International Conference on Systems and Informatics.Yantai: IEEE Press. 2012: 2203-2207.   
[9]郁思思．融合相似度和机器学习的加权 Slope One 算法研究[D]．秦 皇岛：燕山大学,2O15.(Xun Sisi. integrating similarity and machine learning into weighted Slope One algorithm [D]. Qinhuangdao: Yanshan University,2015)   
[10]罗恒．基于协同过滤视角的受限玻尔兹曼机研究[D].上海：上海 交通大学，2O11.(Luo Heng.Restricted Boltzmann machines:a collborative filtering [D]. Shanghai: Shanghai Jiao Tong University, 2011.)   
[11] Georgiev K,Nakov P.A non-IID framework for collaborative filtering withrestricted Boltzmann machines[Cl/Proc of International Conference on Machine Learning.2013: 1148-1156.   
[12]何洁月，马贝．利用社交关系的实值条件受限玻尔兹曼机协同过滤 推荐算[J].计算机学报,2016,39(1):183-195.(He Jieyue,Ma Bei. Based on real-valued conditional restricted Boltzmann machine and social network for collaborative filtering [J].Chinese Journal of Computers2016,39 (1):183-195.)   
[13]霍淑华．基于协同过滤的评分预测推荐算法研究[D].北京：北京 工业大学，2015.(Huo Shuhua.Research on colaborative filtering based rating prediction algorithm [D]. Beijing: Beijing University of Technology, 2015.)   
[14] Hinton G E.A practical guide to training restricted Boltzmann machine [R].Montreal: Department of Computer Science,University of Toronto, 2010.   
[15] Kingma D,Ba J.Adam:a method for stochastic optimization [J]. Computer Science,2014.   
[16]王斌．融合项目属性相似度和评分相似度的协同过滤推荐算法[D]. 秦皇岛：燕山大学，2O17．（WangBin．Collaborative filtering recommendation algorithm for converting project atribute similarity and score similarity [D]. Qinhuangdao: Yanshan University,2017.)   
[17] Liu Xiaomei, Ouyang Yuanxin, Rong Wenge,et al. Item category aware conditional restricted Boltzmann machine based recommendation [M]//Neural Information Processing. 2015: 609-616.   
[18] Du Yongping,Yao Changqing,Huo Shuhua, et al. A new item-based deep network structure using a restricted Boltzmann machine for collaborative filtering[J]．信息与电子工程前沿(英文）,2017,18(5): 658-666.   
[19] Betru B T,Onana C A,Batchakui B.Deep learning methods on recommender system:a survey of state-of-the-art [J]. International Journal of Computer Applications,2017,162 (10): 17-22.