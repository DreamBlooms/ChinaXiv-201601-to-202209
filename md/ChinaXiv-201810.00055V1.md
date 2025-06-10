# 引入隐式反馈的多维度推荐算法

刘美博，满君丰，彭成，刘鸣(湖南工业大学 计算机学院，湖南 株洲 412000)

摘要：现有的推荐算法大多是应用显示反馈信息来推荐。针对显示反馈信息作出的推荐在准确率和数据稀疏性处理上还存在缺陷的问题，引入了隐式反馈信息，设计和实现了一种引入隐式反馈的多维度推荐算法(iMCF)。该算法涵盖用户、项目和隐式反馈三个维度的信息。对于前两个维度的信息，通过云模型相似度建模；而隐式反馈维度的信息，主要是结合概率矩阵分解模型进行处理。之后再把这三个维度得出的预测评分根据权值进行平衡，得出最终预测评分并作出推荐。实验数据表明，该算法在召回率和准确率上的表现相对于其他算法有了较为明显的提升，且适合大数据环境。

关键词：推荐算法；隐式反馈；多维度；云模型；MapReduce 中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2018.04.0376

# Multidimensional recommendation algorithm with implicit feedback introduced

Liu Meibo, Man Junfeng, Peng Cheng, Liu Ming (College ofComputer & Communication Hunan University of Technology,Zhuzhou Hunan 412000,Chian)

Abstract:The existing recommendation algorithms are mostlyappliedto display feedback information to recommend.There are still defects in the accracyofrecommendation and data sparse processing for recommendations made by displaying fedback information.Implicitfedback informationwas introduced,andamulti-dimensionalrecommendationalgorithm (iMCF）that introduces implicit fedback was designed and implemented.The algorithm covered three dimensions of user, project,andimplicitfedback.Forthefirsttwodimensionsofinformation,itismodeledbythesimilarityofthecloudmodel. Theinformationofthe implicit feedback dimension was mainlydealt with bycombining theprobabilistic matrix decomposition model.Afterwards,the prediction scoresobtained from these threedimensions were balanced according to the weights,and obtainedthe finalprediction score andmade recommendation.The experimentaldata shows thatthealgorithm's performance in terms ofrecallrateandaccuracy has been significantly improvedcompared tootheralgorithms,and issuitable forbigdata environments.

Key words:recommendation algorithm; implicit feedback; multidimensional; cloud model; MapReduce

# 0 引言

网络的迅速普及和通信方式的多样给人们带来了极大的便利，同时也造成了信息量的急剧增加。信息的增多也带来了越来越多的垃圾信息，如何从大量信息中筛选出人们需要的信息就需要用到推荐系统。而现今的推荐系统大多利用的是人们的显式反馈信息[1\~4]，如对电影的评分、对商品的评分等。但人们的隐式反馈信息也不可忽略，如用户的浏览记录、购买记录、对相关电影的新闻的关注度等，这些隐式反馈信息获取容易，且信息量较大。因此，结合隐式反馈信息来进行推荐已成为研

究热点。

现有的推荐算法中，主流应用的推荐算法就是协同过滤推荐算法，主要可分为基于近邻的协同过滤推荐和基于矩阵分解模型的协同过滤。基于近邻的协同过滤推荐算法主要是通过计算相似度找出最近邻居，再通过最近邻居进行目标用户对目标项目的评分预测，最后作出推荐[5.6]。基于模型的协同过滤现今应用最广泛的就是矩阵分解[7,8]，矩阵分解能够有效地缓解数据稀疏问题，扩展性问题也得到了一定改善，但矩阵分解降维容易造成数据失真，这会导致推荐误差较大、准确率下降。

针对上述问题，通过学习前人的研究成果，本文提出一种引入隐式反馈的多维度推荐算法。该算法是基于Hadoop分布式平台来实现的，并且该算法选取了用户、项目和隐式反馈三个维度的数据展开研究。主要贡献如下：

a)充分利用了用户、项目、隐式反馈三个维度的数据，解决了数据稀疏和单一维度数据量稀少造成的推荐质量不高的问题。

b)有效结合了相似度模型和矩阵分解模型，使得显示反馈数据和隐式反馈数据都得到合理的应用。

c)给出了三个维度的MapReduce实现方法，提高了该算法的运算效率和可扩展性。

# 1 相关研究

# 1.1概率矩阵分解模型

概率矩阵分解（PMF）是指在矩阵分解的基础上添加了概率分布7]。假设有M部电影，N个用户和评分值为 $1 { \sim } \mathrm { K }$ 的评分矩阵。令 ${ \bf R } _ { \mathrm { i j } }$ 表示用户i对电影j的评分， ${ \mathrm { U } } \in { \mathrm { R } } _ { { \mathrm { D } } \times { \mathrm { N } } }$ 和 $\mathrm { V } \in \mathbf { R } _ { \mathrm { D } \times \mathrm { M } }$ 是用户和电影的隐式特征矩阵，列向量Ui和 $\mathrm { \Delta V _ { j } }$ 分别表示特定用户和特定电影的隐式特征向量。本文采用高斯观测噪声来设计概率线性模型，如图1所示。

![](images/35baa79430e5ae442e2ea1cec3eeceacda857df231554415dfa303fb4c9b9082.jpg)  
图1概率线性模型

将观察到的评级定义为条件分布，如式（1）所示。

$$
p ( R | U , V , \sigma ^ { 2 } ) = \prod _ { i = 1 } ^ { N } \prod _ { j = 1 } ^ { M } [ N ( R _ { i j } | U _ { i } ^ { T } V _ { j } , \sigma ^ { 2 } ) ] ^ { I _ { i j } }
$$

其中： $N ( x | \mu , \sigma ^ { 2 } )$ 是指具有均值 $\mu$ 和方差 $\sigma ^ { 2 }$ 的高斯分布的概率密度函数； $\mathrm { I _ { i j } }$ 是一个指示函数，当用户i对电影j进行了评分时为1，否则为0。并且还为每一个隐式特征向量添加了一个均值为0的球面高斯先验[1,11]，如式（2）所示。

$$
p ( U | \sigma _ { U } ^ { 2 } ) = \prod _ { i = 1 } ^ { N } N ( U _ { i } | 0 , \sigma _ { U } ^ { 2 } I )
$$

$$
p ( V \mid \sigma _ { V } ^ { 2 } ) = \prod _ { i = 1 } ^ { M } N ( V _ { i } \mid 0 , \sigma _ { V } ^ { 2 } I )
$$

通过取对数得出用户特征向量和电影特征向量的后验分布，如式（3）所示。

$$
\begin{array} { l } { { { \ln p ( U , V \mid R , \sigma ^ { 2 } , \sigma _ { V } ^ { 2 } , \sigma _ { U } ^ { 2 } ) = - { \displaystyle { \frac { 1 } { 2 \sigma ^ { 2 } } } } \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { M } I _ { i j } ( R _ { i j } - U _ { i } ^ { T } V _ { j } ) ^ { 2 } } } } \\ { { - { \displaystyle { \frac { 1 } { 2 \sigma ^ { 2 } } } } \sum _ { i = 1 } ^ { N } U _ { i } ^ { T } U _ { i } - { \displaystyle { \frac { 1 } { 2 \sigma _ { V } ^ { 2 } } } } \sum _ { j = 1 } ^ { M } V _ { j } ^ { T } V _ { j } - { \displaystyle { \frac { 1 } { 2 } } } ( ( \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { M } I _ { i j } ) { \ln \sigma ^ { 2 } } + } } \\ { { N D { \ln \sigma _ { U } ^ { 2 } } + M D { \ln \sigma _ { V } ^ { 2 } } ) + C } } \end{array}
$$

其中：C代表常数。在固定超参数的（即观测噪声方差和先验方差）的情况下，最大化式（3）所示的对数后验概率相当于用二次正则化项最小化公式（4）所示的目标函数。

$$
\begin{array} { l } { { \displaystyle { \cal E } = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { M } I _ { i j } ( R _ { i j } - U _ { i } ^ { T } V _ { j } ) ^ { 2 } + \frac { \lambda _ { U } } { 2 } \sum _ { i = 1 } ^ { N } \lVert U _ { i } \rVert _ { { \boldsymbol F } r o } ^ { 2 } } } \\ { { \displaystyle ~ + \frac { \lambda _ { V } } { 2 } \sum _ { j = 1 } ^ { N } \lVert V _ { j } \rVert _ { { \boldsymbol F } r o } ^ { 2 } } } \end{array}
$$

λ=o²/o²,λ=σ²/σ²;²为Frobenius范数,再优化学习式(4)中的U和 $\mathrm { \Delta V }$ 特征矩阵。

# 1.2相似度计算

协同过滤推荐算法其基本思想是“物以类聚，人以群分”依据相似性而产生推荐[8.9]。

要想运用协同过滤推荐算法，其数据必须是一个矩阵形式，如表1所示。其中U是用户，I是项目， $\mathrm { R } _ { \mathrm { m n } }$ 表示用户集中的用户 $\mathbf { m }$ 对项目集中的项目 $\mathfrak { n }$ 的评分。

表1用户一项目评分  

<html><body><table><tr><td></td><td>I</td><td></td><td></td><td>I</td><td>：</td><td>I</td></tr><tr><td>U1</td><td>R1,1</td><td>R1,2</td><td>：</td><td>R1,a</td><td></td><td>R1.n</td></tr><tr><td>U2</td><td>R2,1</td><td>R2,2</td><td>：</td><td>R2.a</td><td></td><td>R2.n</td></tr><tr><td>：</td><td>：</td><td>：</td><td>…</td><td>…</td><td></td><td>：</td></tr><tr><td>Ua</td><td>Ra,1</td><td>Ra,2</td><td>：</td><td>Raa</td><td>：</td><td>Ran</td></tr><tr><td>…</td><td>：</td><td>…</td><td>：</td><td>：</td><td></td><td>…</td></tr><tr><td>Um</td><td>Rm,1</td><td>Rm,2</td><td>：</td><td>Rm.a</td><td>…</td><td>Rm.n</td></tr></table></body></html>

该算法的核心就是寻找最近邻居。要想找到邻居必需计算相似性，本文的度量相似性方法采用云模型相似性度量方法，具体如下。

云模型相似性：先根据评分矩阵统计得出用户或项目的评分频度向量 $\mathbf { U _ { i } } { = } ( \mathbf { u } _ { 1 } , \mathbf { u } _ { 2 } , \mathbf { u } _ { 3 } , \mathbf { u } _ { 4 } , \mathbf { u } _ { 5 } )$ （1≤i≤m），再通过逆向云算法计算特征向量如下：

$$
E { \hat { x } } = { \overline { { X } } } = { \frac { 1 } { N } } \sum _ { i = 1 } ^ { N } x _ { i } \ { \hat { H } } e = { \sqrt { \frac { \pi } { 2 } } } \times { \frac { 1 } { N } } \sum _ { \mathrm { i = 1 } } ^ { N } | \ x _ { i } - E { \hat { x } } | \ { \hat { E } } n = { \sqrt { S ^ { 2 } - { \frac { 1 } { 3 } } H { \hat { e } } ^ { 2 } } }
$$

特征向量 $\mathbf { V _ { i } } mathrm { = \ ( E x _ { i } , E n _ { i } , E e _ { i } ) \ , \ \mathbf { V _ { j } } = \ ( E x _ { j } , E n _ { j } , E e _ { j } ) }$ 。

$$
s i m ( i , j ) = \cos ( V _ { \mathrm { i } } , V _ { j } ) = \frac { V _ { \mathrm { i } } \cdot V _ { j } } { \parallel V _ { \mathrm { i } } \parallel \cdot \parallel V _ { j } \parallel }
$$

通过上述方法计算出相似用户后，在根据式（6）计算来产生推荐。

$$
R _ { i , d } = \overline { { { R } } } _ { i } + \frac { \sum _ { j \in N E S I } s i m ( i , j ) ^ { * } ( R _ { j , d } - \overline { { { R } } } _ { j } ) } { \sum _ { j \in N E S I } \lvert s i m ( i , j ) \rvert }
$$

其中：NESI表示邻居集； $\overline { { R } } _ { i }$ 表示项目i的平均评分； $\overline { { R } } _ { j }$ 表示邻居项目的平均评分。

# 2 引入隐式反馈的多维度推荐算法

本文主要选取了项目、用户和隐式反馈三个维度数据来综合得出最终预测结果，下面给出具体推荐示意图。如图2所示，引入隐式反馈的多维度推荐算法主要由建立用户一项目评分矩阵、基于用户云模型协同过滤建模、基于项目云模型协同过滤建模、概率矩阵分解建模以及综合推荐等模块组成。建立用户一项目评分矩阵主要是通过对稀疏矩阵进行填充来初步解决数据稀疏问题。之后再通过三个维度的建模来求得个这三个维度的预测评分，并通过权值分配得出三个维度的综合评分，再依据评分来进行推荐。

![](images/403ebd91eb09a7126b1fd71dd4e10e42c48d84554a394c4baafbed3223c889e0.jpg)  
图2推荐示意图

# 2.1未评分项的预测填充

数据稀疏问题是传统推荐算法普遍存在的问题，会导致相似度计算困难、推荐准确度偏低。本文通过采用云模型相似度来对评分矩阵进行评分预测填充，再利用填充好的评分矩阵进行目标用户对目标项目的评分计算。其有效解决了数据稀疏问题。具体如算法1所示。

算法1未评分项的预测填充 输入：评分矩阵 $\mathbb { R } _ { \mathrm { m } \times \mathrm { n } }$ 。

输出：预测用户 $\mathrm { ~  ~ u ~ }$ 对未评分项目 $\dot { \mathbf { i } } _ { \mathrm { a } }$ 的评分。

a)根据评分矩阵 $\mathbb { R } _ { \mathrm { m } \times \mathrm { n } }$ ，统计出项目的评分频度向量${ \bf { I } } _ { \bf { u } } \mathrm { = }$ (ii,i2,i3,i4,is)（1≤i≤m），再通过逆向云算法计算特征向量 $\mathbf { V _ { i } } \mathbf { = }$ 0 $\mathbf { \check { E } x _ { i } } , \mathbf { E n _ { i } } , \mathbf { E e _ { i } } ,$ ）（1≤i≤m）；

b)根据式（5）计算 $\dot { \mathbf { i } } _ { \mathrm { a } }$ 与其他项目的云相似性：

$$
\operatorname { s i m } ( i _ { a } , j ) = \cos ( V _ { i _ { a } } , V _ { j } ) = { \frac { V _ { i _ { a } } \cdot V _ { j } } { \parallel V _ { i _ { a } } \parallel \cdot \parallel V _ { j } \parallel } }
$$

c）将第二步的相似度值进行大到小排序，得出前若干项目作为邻居集 ${ \mathrm { N E S I } } { = } \{ \mathrm { i } _ { 1 } , \mathrm { i } _ { 2 } , . . . , \mathrm { i } _ { \mathrm { x } } \}$

d）得出邻居集NESI后，再根据式（6）计算用户 $\mathrm { ~  ~ u ~ }$ 对未评分项目ia的评分：

$$
R _ { \mathrm { u } , i _ { a } } = \overline { { { R } } } _ { u } + \frac { \sum _ { j \in N E S I } s i m ( i _ { a } , j ) ^ { * } ( R _ { j , d } - \overline { { { R } } } _ { j } ) } { \sum _ { j \in N E S I } \lvert s i m ( i _ { a } , j ) \rvert }
$$

# 2.2三个维度的预测评分计算

基于用户云模型相似度计算第一维度的预测评分：在上面矩阵填充的基础上，根据式(5)计算用户间的相似度 $\mathrm { { S i m } ( U _ { i } , \ U _ { x } ) }$ ，再使用式（6）求得预测评分，将目标用户Ui对目标项目 $\mathrm { I j }$ 的预测评分记为 $\mathrm { U R } _ { \mathrm { i , j } }$ ，其中目标用户的邻居集为S（Ui）。

$$
U R _ { i , j } = \overline { { { R } } } _ { i } + \frac { \sum _ { U x \in S ( U i ) } S i m ( U i , U x ) ^ { * } ( R _ { x , j } - \overline { { { R } } } _ { x } ) } { \sum _ { U x \in S ( U i ) } \lvert s i m ( U i , U x ) \rvert }
$$

基于项目云模型相似度计算第二维度的预测评分：在上面矩阵填充的基础上，根据式(5)计算项目间的相似度 $\mathrm { { S i m } ( I _ { i } , I _ { y } ) }$ 再使用式（6）求得预测评分，将目标用户 $\mathrm { U } _ { \mathrm { i } }$ 对目标项目 $\mathrm { I j }$ 的预测评分记为 $\mathrm { I R } _ { \mathrm { i , j } }$ ，其中目标项目的邻居集为S $\mathrm { { ( I _ { i } ) } }$ 。

$$
I R _ { i , j } = \overline { { { R } } } _ { i } + \frac { \sum _ { { I y \in S ( I i ) } } S i m ( I i , I y ) ^ { * } ( R _ { i , y } - \overline { { { R } } } _ { y } ) } { \sum _ { { I y \in S ( I i ) } } \lvert s i m ( I i , I y ) \rvert }
$$

为了对隐式反馈数据实验的开展，本文选取了从知名影评网豆瓣爬取的数据进行实验，选取了符合条件的4万多个用户的数据集，每个人收藏的电影超过25部，交互数据超过30次。具体实例如表2、3所示。

表2用户收藏信息示例  

<html><body><table><tr><td colspan="2">ID 收藏的电影</td></tr><tr><td>173952145</td><td>降临，速度与激情，机械公敌，全民超人，</td></tr><tr><td>209456781</td><td>独立日，当幸福来敲门，变脸，空中监狱，</td></tr><tr><td>198746028</td><td>荒岛余生，变相怪杰，训练日，木乃伊，</td></tr><tr><td>表3用户交互数据示例</td><td></td></tr><tr><td>电影 简介</td><td>点击IMDB链接 评论 分享</td></tr><tr><td>速度与激情 2</td><td>5 3 2</td></tr><tr><td>空中监狱 0</td><td>0 5 3</td></tr><tr><td>荒岛余生 1</td><td>3 7 4</td></tr></table></body></html>

针对该数据，借鉴了文献[10]和文献[11]中的相关做法，在此基础上进行了改进。具体方法如下：

$\textcircled{1}$ 计算用户对电影的隐式兴趣程度向量。设定用户为 $\mathrm { ~ u ~ }$ ，用户对电影的兴趣信息列表 $\mathbf { S } ( \mathbf { u } )$ ，用户的交互活动矩阵 $\mathbf { A } ( \mathbf { u } )$ 5用户收藏的感兴趣电影列表L（u）， $\mathrm { ~ S ~ } ( \mathrm { ~ u ~ } ) = \{ \mathrm { s } _ { 1 } , \mathrm { s } _ { 1 } , . . . , \mathrm { s } _ { \mathrm { n } } \}$ ，A(u)$= \{ \mathrm { a _ { u } } 1 , \mathrm { a _ { u } } 2 , . . . , \mathrm { a _ { u n } } \} .$ 0

$$
s _ { 1 } = \{ { \begin{array} { l l } { 1 } & { s _ { i } \in L ( u ) } \\ { 0 } & { s _ { i } \not \in L ( u ) } \end{array} } , 1 \leq i \leq n
$$

其中： $\mathrm { a } _ { \mathrm { u s } }$ （ $1 { \mathrm { < } } = \mathbf { s } { \mathrm { < } } = \mathbf { n } .$ 是 $\mathbf { k }$ 维向量，其中每一个数据为交互类型出现的次数。具体交互类型如下：

a)用户是否查看电影具体剧情简介；  
b）用户是否点击IMDB链接;  
c）用户是否评论和回复他人评论；  
d）用户是否分享该电影。

针对这四种交互类型，本文设定权重系数 $\scriptstyle \mathtt { a } = ( 1 , 4 , 6 , 1 0 )$ ，再通过式（10）合并交互数据。

$$
\begin{array} { c c } { { 1 } } & { { a _ { u , s , i } \geq t h r e s h o l d } } \\ { { p _ { u , s , i } \ S _ { a _ { u , s , i } } \{ _ { t h r e s h o l d } } }  & { { a _ { u , s , i } < t h r e s h o l d } } \\ { { \displaystyle ( 1 \leq i \leq k , 1 \leq s \leq n ) , i _ { u , s } = \frac { 1 } { \alpha ^ { ' } } \sum _ { j = 1 } ^ { k } \alpha _ { j } p _ { u , s , j } } } \end{array}
$$

其中：threshold为交互次数的三四分位数。然后可得到用户对电影的隐式兴趣程度向量 ${ \mathrm { ~ I ~ } } \left( { \bf u } \right) = \{ { \mathrm { i } } _ { 1 } , { \mathrm { i } } _ { 2 } , . . . { \mathrm { i } } _ { \mathrm { n } } \}$ 。

$\textcircled{2}$ 计算用户的兴趣程度评分及评分向量。通过式（11）得出兴趣程度评分。

$$
r _ { u , s } = ( w + ( 1 - w ) i _ { u , s } ) s _ { u , s }
$$

其中： $\mathrm { r } _ { \mathrm { u , s } }$ 为用户对电影的最终兴趣评分； $\mathbf { w }$ 为权重参数，取值为0,85，得出评分向量 ${ \textsc { R } } ( { \mathbf { u } } ) = \{ { \mathbf { r } } _ { 1 } , { \mathbf { r } } _ { 2 } , . . . { \mathbf { r } } _ { \mathrm { { n } } } \}$ 。

$\textcircled{3}$ 计算评分矩阵R中某一预测评分。通过式（12）得出预测评分。

$$
\begin{array} { l } { { \displaystyle F R _ { u i } = \sum _ { k = 1 } ^ { K } U _ { u k } V _ { k i } = U _ { u } V _ { i } ^ { T } , } } \\ { { \displaystyle u \in ( 1 , . . . , N ) , i \in ( 1 , . . . , M ) , k \in ( 1 , . . . , K ) } } \end{array}
$$

其中：U为用户特征矩阵； $\mathrm { \Delta V }$ 为电影特征矩阵；K为特征数。而对于未知元素本文使用AMAN方法[12,13]设为0，然后再经过PMF模型进行训练得出最终推荐结果。具体示意图如图3所示。

![](images/75c6529ee8aea73c185e6f39722c1dc1e71eec5125b632a87d3bd997209c59c0.jpg)  
图3基于隐式反馈的电影推荐示意图

# 2.3 最终预测评分

接收以上得出的三个预测评分，动态确定三个评分的权值分配，借鉴文献[17]的方法引入近邻群和信任子群，并按式（13)和（14）得出相关对象集合。

$$
S ( U _ { a } ) = \{ U _ { x } | S i m ^ { \prime } ( U _ { a } , U _ { x } ) > \mu , a \neq x \}
$$

$$
S ( I _ { j } ) = \{ I _ { x } \mid S i m ^ { \prime } ( I _ { j } , I _ { y } ) > \nu , j \neq y \}
$$

近邻群大小 $\lvert \mathrm { S ( U a ) } \rvert { = } \mathrm { m }$ . $\lvert \mathrm { S ( I _ { j } ) } \rvert { = } \mathrm { n }$

$$
\begin{array} { l } { { S ^ { \prime } ( U _ { a } ) = \{ U _ { x } \mid S i m ^ { \prime } ( U _ { a } , U _ { x } ) > \mu \& } }  \\ { { \mid I _ { U _ { a } } \cap I _ { U _ { x } } \mid > \varepsilon , a \neq x \} } } \end{array}
$$

$$
S ^ { \prime } ( I _ { j } ) = \{ I _ { y } | S i m ^ { \prime } ( I _ { j } , I _ { y } ) > \nu \mathcal { E }
$$

$$
\vert U _ { I _ { j } } \cap U _ { I _ { y } } \vert > \delta , j \neq y \}
$$

信任子群大小 ${ | \mathrm { S ^ { \prime } ( U a ) } | } \mathrm { = m ^ { \prime } }$ . $\lvert \mathrm { S ^ { \prime } ( I j ) } \rvert { = } \mathrm { n ^ { \prime } }$ ；其中 $\mu$ ，v，ε，δ为阈值。

$$
S ^ { \ " } ( U _ { a } ) = \{ U _ { x } \mid S i m ^ { \prime } ( U _ { a } , U _ { x } ) > \mu \& R _ { x , j } \neq 0 , a \neq x \}
$$

$$
S ^ { \ " } ( I _ { j } ) = \{ I _ { \boldsymbol { x } } \mid S i m ^ { \prime } ( I _ { j } , I _ { y } ) > \nu \& R _ { a , y } \neq 0 , j \neq y \}
$$

相关对象集合大小 $| \mathrm { S " ( U a ) } | { \mathrm { = m " , } } | \mathrm { S " ( I _ { j } ) } | { \mathrm { = n " } }$ 。其中 ${ \mu } , \textbf { v }$ 为阈值。

设a、b分别为用户维度和项目维度的权值，则1-a-b为隐式反馈维度的权重。

$$
a = \frac { \phi \times M } { \phi \times M + \mathcal { S } \times N + q } ; b = \frac { \mathcal { S } \times N } { \phi \times M + \mathcal { S } \times N + q } ;
$$

$$
1 - a - b = { \frac { q } { \phi \times M + \vartheta \times N + q } }
$$

$\phi$ 、 $\boldsymbol { \mathscr { s } }$ 是调和参数,q为Ua打过分的项目集大小。 $. \mathbf { M } , \mathbf { N }$ 取值如下：

$$
1 . ( m " + n " ) > 0 , M = m " , N = n " ;
$$

$$
2 . ( m ^ { \prime } + n ^ { \prime } ) > 0 , M = m ^ { \prime } , N = n ^ { \prime } ;
$$

$$
\begin{array} { l c r } { { 3 . ( m + n ) > 0 , M = m , N = n ; } } \\ { { 4 . M = N = 0 ; } } \end{array}
$$

然后根据式（20）计算目标用户对未评分项目的综合预测评分，算出综合预测评分后，再把评分值进行排序，根据TOP-N 算法[18]作出推荐。

$$
P R _ { i , j } = a \times U R _ { i , j } + b \times I R _ { i , j } + ( 1 - a - b ) ~ F R _ { i , j }
$$

# 2.4引入隐式反馈的多维度推荐算法实现

该算法主要可分为以下几个步骤进行具体实现：根据填充后的评分矩阵计算基于用户和基于项目维度的预测评分；根据隐式反馈计算基于隐式反馈维度的预测评分；动态确定权值分配，计算最终的综合预测评分；根据项目最终预测评分高低为目标用户作出推荐。具体如算法2所示。

算法2引入隐式反馈的多维度推荐算法

输入：已填充的评分矩阵 $\mathbf { R } _ { \mathrm { m } \times \mathrm { n } }$ ，阈值 ${ \mu } , { \mathrm { ~ v } } , { \mathrm { ~ \varepsilon } } , { \mathrm { ~ \delta } }$ ，调和参数 $\phi$ 、 $\boldsymbol { \mathscr { s } }$ ，隐式数据的项目特征矩阵Q，用户特征矩阵P，正则因子 $\lambda$ 值列表 $( \lambda _ { 0 } , ~ \lambda _ { 1 } . . . \lambda _ { \mathrm { a } } )$ ，特征数L。

输出：为目标用户 $\mathrm { U _ { a } }$ 推荐的前 $\mathbf { k }$ 个项目编号。

1．根据式（13）（14)求得用户和项目的近邻群 $\mathrm { \Delta S ( U _ { a } ) }$ $\mathbf { \Lambda } = \{ \mathbf { U } _ { 1 } , \dots \$ ， $| \mathrm { U _ { s } } \}$ 和 $\mathrm { ~ S ~ } \left( \mathrm { { I _ { j } } } \right) \ = \{ \mathrm { { I } _ { 1 } , . . . , \mathrm { { I } _ { t } } \} }$

2． 求出目标用户 $\mathrm { U _ { a } }$ 的已评分项目集合 $\mathrm { { I _ { U a } } = \{ I _ { l } , \ . . . , I _ { q } \} }$

3． for j from 1 to n do

4. If $\mathrm { U _ { a } }$ did not rate $\mathrm { ~ I ~ } _ { \mathrm { j } }$ then

5. for i from 1 to s do

6. if $\mathrm { U } _ { \mathrm { i } }$ rated $\mathrm { I j }$ then

7. Under1 $+ { = } \mathrm { U S i m ( U a , U _ { i } ) }$

9. end for

10.If $\mathrm { U n d e r l } = = 0$ then $\mathrm { U R _ { a , j } = U A v g ( U _ { i } ) }$

11．Else $\mathrm { U R _ { a , j } = U A v g ( U _ { i } ) + O n 1 / U n d e }$ rl；

12．fori from 1 to t do

13.if $\mathrm { U } _ { \mathrm { i } }$ rated $\mathrm { I j }$ then

14.Under2 $\underline { { \ u } } + = \mathrm { { I S i m } ( \mathrm { { I j } , \mathrm { { I i } ) } } }$

$$
\mathrm { O n 2 + = I S i m ( I _ { j } , I _ { i } ) \ ^ { * } \left( R _ { a , i } – I A v g ( I _ { i } ) \right) } ;
$$

16. end for

17．IfUnder $2 = = 0$ then $\mathrm { I R _ { a , j } = \mathrm { I A v g ( I _ { j } ) } }$

18．Else $\mathrm { I R _ { a , j } = I A v g ( I _ { j } ) ^ { + } }$ On2/Under2;

19.for $\lambda$ in $( \lambda _ { 0 } , \lambda _ { 1 } . . . \lambda _ { \mathrm { a } } )$ do

20.for $\mathbf { x }$ in $^ { ( 0 , \mathrm { n } ) }$ do

21． $[ \mathrm { Q u _ { x l } , . . . , Q u _ { x L } } ] {  } \mathrm { s e a r c h ( i _ { x } , \boldsymbol { \lambda } , \boldsymbol { Q } ) }$

22． $\mathrm { R } _ { \mathrm { L } \times \mathrm { L } } {  } ( \lambda { \times } \mathrm { n } { \times } \mathrm { I } { + } \mathrm { Q } \mathrm { u } ^ { \mathrm { T } } \mathrm { Q } \mathrm { u } ) ^ { - 1 }$

23.for $\mathbf { x }$ in (0,L) do

$\mathrm { P u x }  \sum _ { z = 0 } ^ { n } ( \sum _ { y = 0 } ^ { L - 1 } R _ { x y } \mathcal { Q } u _ { y z } ) \times r _ { z }$ （204号24. end for25. [Pixl,..,PixL]←Search(ux,λ,P)26. $\mathrm { R } _ { \mathrm { L } \times \mathrm { L } } {  } ( \lambda { \times } \mathrm { n } { \times } \mathrm { I } { + } \mathrm { P i } ^ { \mathrm { T } } \mathrm { P i } ) ^ { - 1 }$ 27. for $\mathbf { x }$ in (0,L) do  
$\mathrm { Q i x } {  } \sum _ { z = 0 } ^ { n } ( \sum _ { y = 0 } ^ { L - 1 } R _ { x y } P i _ { y z } ) { \times } r _ { z }$ （204号28. end for29. end for30. end for31. $\mathrm { F R _ { a , j } = P _ { u } Q _ { i } ^ { \mathrm { T } } }$ 32. calcWeight(a,b,1-a-b);33. $\mathrm { P R _ { a , j } = a ^ { * } U R _ { a , j } + b ^ { * } I R _ { a , j } + ( 1 - a - b ) ^ { * } F R _ { a , j } }$ 34. Store $\mathrm { ( P , P R _ { a , j } ) }$ ：35. end for36. store(P);37. Return Top(k);

该算法第5\~11行通过用户相似度计算用户维度的预测评分，第12\~18行通过项目相似度计算项目维度的预测评分，第19\~33行通过概率矩阵分解计算隐式反馈维度预测评分，之后通过动态权值分配求得三个维度的权值，再通过计算得出最终综合预测评分，并把该评分降序排列，选出前k个推荐给目标用户Uao

# 2.5推荐过程的 MapReduce 实现

为了方便并行化处理，必须对相关步骤进行mapreduce 实现。具体如下：

1)对前两个馈维度的处理$\textcircled{1}$ 评分矩阵的MapReduce

Map 阶段：接收输入的<key,value>键值对，其中基于项目这一维度key为项目的ID，value为用户的ID与评分值；基于用户这一维度key为用户的ID，value为项目的ID与评分值。然后进行切分工作，将原始数据切分成若干记录，检查数据是否合理。Shuffle 排序聚集和分发都以key 值为依据，然后再将合理的数据发送至管道，进入reduce阶段。

Reduce阶段：接收Map阶段的数据，根据key值进行合并，得到评分矩阵。

$\textcircled{2}$ 相似度计算的MapReduce

Map阶段：接收评分矩阵后，对每个评分数据进行提取，基于项目这一维度以项目对！ $( \mathbf { i } _ { \mathrm { x } , \mathbf { i } _ { \mathrm { y } } } )$ 作为key值，项目对应的评分对！ $\mathrm { \langle S _ { x } , S _ { y } }$ ）作为value 值输出。基于用户这一维度以用户对（20 $( \mathrm { u } _ { \mathrm { x } } , \mathrm { u } _ { \mathrm { y } } )$ 作为key值，用户对应的评分对（ $\mathrm { \Delta S _ { x } , S _ { y } ) }$ ）作为value值输出

Reduce阶段：接收Map阶段的数据，根据式（5）计算项目间的相似度和计用户间的相似度；将结果保存输出。

$\textcircled{3}$ 预测评分的MapReduce

Map 阶段：根据相似度的值，首先基于项目这一维度得出每个项目相似度最高的N个项目定义为邻居，以项目为key值、项目邻居为value值输出。然后基于用户这一维度得出每个用户相似度最高的N个项目定义为邻居，以用户为key值、用户邻居为value 值输出。

Reduce阶段：接收Map阶段的数据，根据式（7）和（8）计算出两个维度目标用户对未评分项目的预测评分。

2)对隐式反馈维度的处理$\textcircled{1}$ 用户特征矩阵更新的MapReduce 处理Map方法：输入：（行号line_key,（电影号i,用户号u,对应评分r））。输出：（用户号u,（电影号i,对应评分r））。1.根据行号将（行号line_key,（电影号i,用户号u,对应评  
分r））映射为用户号u2.if行号line_key小于总行数M:3．输出（用户号u,（电影号i,对应评分r））Reduce方法：输入：（用户号u,（电影号i,对应评分r）对列表） $\mathcal { , \lambda }$ 列表,  
特征数k,项目特征矩阵Q输出：（（用户号 $\mathbf { u } _ { \pm }$ 正则因子 $\lambda$ ）,用户特征矩阵P)1.for $\lambda$ in $\lambda$ 列表&&xin $\left( 0 , \mathrm { ~ \ n \right) ~ }$ do2.Search $( \mathrm { i _ { x } } , \lambda , Q )$ 得出对应电影特征向量 $[ \mathrm { Q u _ { x 1 } } , \cdots , \mathrm { Q u _ { x k } } ]$ 3. 计算 $( \lambda \mathrm { { x n } \mathrm { { x I } \mathrm { { + Q u } ^ { \mathrm { { T } } } Q u ) ^ { - 1 } } } }$ 得出评分值 $\scriptstyle \mathbf { R } _ { \mathbf { k } \times \mathbf { k } }$ 4. for $\mathbf { x }$ in (0,k) do5. 计算 $\sum _ { x = 0 } ^ { n } ( \sum _ { y = 0 } ^ { k - 1 } R _ { x y } Q u _ { y z } ) \times r _ { x }$ 得出 $\mathrm { P _ { u x } }$ （206.输出更新后的用户特征矩阵U  
$\textcircled{2}$ 项目特征矩阵更新的MapReduce 处理  
Map 方法：  
输入：（列号column_key(电影号i,用户号 ${ \mathrm {  ~ u ~ } } ,$ 对应评分r))。输出：（电影号i(用户号 $\mathrm { ~  ~ u ~ }$ ，对应评分r))。

1.根据列号将(列号column_key,(电影号i,用户号u,对应评分r))映射为电影号u

2.if 行号line_key小于总列数N：

3.输出（电影号i，（用户号 ${ \mathrm {  ~ u ~ } } ,$ 对应评分r））

Reduce方法：

输入：（电影号i，（用户号 ${ \mathrm {  ~ u ~ } } ,$ 对应评分r）对列表），入列表，特征数 $\mathbf { k , } \textcircled{ 1 }$ 得出的用户特征矩阵 $\mathrm { ~ \bf ~ P ~ }$ 。

输出：（（电影号i,正则因子 $\lambda$ ）,项目特征矩阵Q）。

1.for $\lambda$ in $\lambda$ 列表&& $\mathbf { x }$ in $( 0 , \mathrm { ~ \ n ~ } )$ do  
2. Search $\mathrm { ( u _ { x } } \ , \lambda , \mathrm { U ) }$ 得出对应用户特征向量 $[ \mathrm { P i _ { x 1 } , \cdots , \mathrm { P i _ { x k } } } ]$   
3. 计算 $( \lambda { \times } \mathrm { n } { \times } \mathrm { I } \mathrm { + } \mathrm { P i } ^ { \mathrm { T } } \mathrm { P i } ) ^ { - 1 }$ 得出评分值 $\scriptstyle { \mathrm { \mathrm { R } } } _ { \mathrm { k } \times \mathrm { k } }$   
4. for $\mathbf { x }$ in (0,k) do  
5. 计算 $\sum _ { x = 0 } ^ { n } ( \sum _ { y = 0 } ^ { k - 1 } R _ { x y } P i _ { y z } ) \times r _ { x }$ 得出 $\mathrm { Q } _ { \mathrm { i x } }$ （204号

6.输出更新后的项目特征矩阵Q

通过 $\textcircled{1} \textcircled{2}$ ，分别计算出了用户特征矩阵P和项目特征矩阵Q。再通过式（12）可计算某一预测评分，并通过式（21）计算均方根误差RMSE[19]。

$$
R M S E = \sqrt { \frac { 1 } { \mid R \mid } \sum _ { ( u , i ) \in R } { ( F R _ { u i } - r _ { u i } ) ^ { 2 } } }
$$

其中：R为评分集； $\mathrm { F R } _ { \mathrm { u i } }$ 为预测评分； ${ \mathrm { \bf { r } } _ { \mathrm { { u i } } } }$ 为评分集中的评分，且RMSE与推荐准确度成反向关系。

$\textcircled{3}$ 均方根误差（RMSE）计算的MapReduce处理

Map 方法：

输入：（行号line_key，（电影号i,用户号 ${ \mathrm {  ~ u ~ } } _ { ; \mathrm { \scriptsize { \mathrm {  ~ u ~ } } } }$ 对应评分r）），入列表，特征数 $^ { \mathbf { k } , \textcircled{ 1 } }$ 得出的用户特征矩阵P $\textcircled{2}$ 得出的电影特征矩阵Q。

输出：（ $\mathrm { \ ? { \lambda } , E S \mathrm { \ ' } }$ 。  
1.for $\lambda$ in $\lambda$ 列表do  
2. Search $\mathbf { \Sigma } ( \mathrm { u _ { \ell } } , \lambda , \mathrm { P } )$ 得出每一用户特征向量 $[ \mathrm { u } _ { 1 } , \cdots , \mathrm { u } _ { \mathrm { k } } ]$ 3. Search $( \mathrm { i } , \lambda , 0 )$ 得出每一电影特征向量[i,,ik]4. 计算 $\sum _ { x = 1 } ^ { k } u _ { x } \dot { l } _ { x }$ 并设其为 $\mathbf { r } _ { \mathrm { a } }$   
5. 计算 $( \mathrm { r } _ { \mathrm { a } } - \mathrm { r } ) ^ { 2 }$ 并设其为ES  
6. 输出（ $\mathrm { \hat { \lambda } } \mathrm { , E S }$ ）  
Reduce方法：  
输入： （ $\mathrm { \hat { \lambda } } \mathrm { , E S }$ 列表）。  
输出：RMSE。  
计算 $\sqrt { ( \sum _ { x = 1 } ^ { n } E S _ { x } ) / n }$ 得出RMSE  
1.输出RMSE  
通过 $\textcircled{1} \textcircled{2} \textcircled{3}$ 的迭代执行，直到RMSE不再减小，取最小直和特征矩阵，计算出预测评分。通过上述所有算法，再

$\lambda$ 据3.4所示作出推荐。

# 3 实验及分析

# 3.1实验环境与数据度量标准

本文用七台普通的PC 机搭建Hadoop 组成集群，命名为master、slave1\~slave6。以豆瓣网站爬取的数据为例，如表4所示。

表4数据集描述  

<html><body><table><tr><td>数据集</td><td>用户数</td><td>项目数</td><td>选择行为</td></tr><tr><td>训练集</td><td>33 213</td><td>84 633</td><td>5 095 277</td></tr><tr><td>测试集</td><td>8156</td><td>23 982</td><td>151 972</td></tr></table></body></html>

对数据划分为训练级与测试集，比例大概为4:1。采用Rank值反映召回率(查全率)和Top-k命中率反映准确率(precision)，命中率、召回率与推荐质量都成正向关系，如式（22）所示。Rank值表示实际选择的电影在推荐列表中所占百分比位置，实际选择电影在首位，Rank值为 $0 \%$ ，在最后，Rank值为 $100 \%$ 。命中率指推荐给用户的 $\mathbf { k }$ 部电影，用户实际选择的电影所占的比例。推荐情况示例如表5所示。

<html><body><table><tr><td></td><td>推荐</td><td>未推荐</td></tr><tr><td>喜欢</td><td>A</td><td>B</td></tr><tr><td>不喜欢</td><td>C</td><td>D</td></tr></table></body></html>

召回率 $= \boldsymbol { A } / \left( \boldsymbol { A } + \boldsymbol { C } \right)$ ，准确率 $= \boldsymbol { A } / \left( \boldsymbol { A } + \boldsymbol { B } \right)$

并采用加速比表示处理海量数据时集群节点数对性能方面的影响。加速比定义： $K { = } { \mathrm { T } } _ { 1 } / { \mathrm { T } } _ { 1 } .$ 其中：T1表示单节点运行耗费的时长； $\mathrm { T n }$ 表示 $\mathfrak { n }$ 个节点运行耗费的时长。

# 3.2加速性能测试实验

该实验目的主要是针对不同的TaskTracker节点，测试该算法在Hadoop平台下时效性方面是否显著提升。进行该实验前必须先确定正则因子入值与RMSE值，具体取值如表6所示。

表6不同值对应的RMSE值  

<html><body><table><tr><td></td><td>0.01</td><td>0.03</td><td>0.05</td><td>0.06</td><td>0.07</td><td>0.08</td></tr><tr><td>RMSE</td><td>0.979</td><td>0.942</td><td>0.923</td><td>0.920</td><td>0.921</td><td>0.923</td></tr></table></body></html>

从表中可以看到，当 $\lambda$ 值为0.06时得到的RMSE值最小，所以对 $\lambda$ 的取值为0.06。得到 $\lambda$ 后，再进行加速比实验，分别选取全部数据集和一部分小数据集进行实验，具体结果如图4所示。

![](images/90f27c6b6a98952ac23658433271173fea4ed917cd5d771145fc65e2ed2837ee.jpg)  
图4加速比实验图

从图4可看出，当集群节点数从1加到3时，加速比几乎呈线性增长，节点3以后增速下降。说明节点增加确实能提高效率，但是理论上增加一个节点提升1倍效率，在实际上很难达到。而对比两个数据集可以发现，数据集越大，加速效果越明显。

# 3.3与其他推荐算法的对比实验

下面主要把本文算法(iMCF)与基于隐式反馈的矩阵分解算法(iMF)、基于用户的协同过滤算法(UBCF)、基于项目的协同过滤算法(IBCF)算法进行实验比较，得到各个阶段的数据。首先选取不同的K值（推荐队列的长度）进行实验，得出对应的准确率，具体结果如图5所示。然后比较这三种算法在相同情况下的Rank值，具体结果如图6所示。

通过图5、6的比较可以看出，当K值逐渐增大时，这三种算法的准确率逐渐下降，召回率在逐步增加。不同K值时iMCF算法都能得到最大的准确率和召回率，并且iMCF算法对于准确率和召回率的提升比较明显。这说明iMCF算法比其他两个算法的推荐质量更佳，准确度更好。

# 4 结束语

针对越来越庞大的网络资源和以往推荐算法的不足，本文提出了一种引入隐式反馈的多维度推荐算法(iMCF)。该算法充分利用了Hadoop集群的优势，有效结合了云模型，引入了隐式反馈数据，并且通过动态确定权重，使得目标用户对目标项目的预测评分更加精确。实验数据表明，该算法能适应大数据环境，并由于利用了云模型和三个维度数据，数据稀疏性问题也得到了合理的解决，推荐质量也上升了一个档次。而随着时间的变化，人们的兴趣也会发生改变，如何来衡量变化对推荐质量的影响，是笔者下个阶段的研究重点。

![](images/13a57fd0e2629e1bce848b6f4f1150231ec97543c41763b5700def94296aaa5c.jpg)  
图5不同K值下其他算法与iMCF 算法的Precision 比较

![](images/c280dd7b232204df129ea979626f917ea43f645e0d1a84b56e3ccd3466239277.jpg)  
图6不同K值下其他算法与iMCF算法的Rank比较

# 参考文献：

[1]Liu Xin，Aberer K.SoCo:a social network aided context-aware recommender system[C]//Proc of International Conference on World Wide Web.[S.1.]:ACMPress,2013:781-802. [2]Sun Guangfu,Wu Le,Liu Qi,et al.Recommendations based on collaborative filtering by exploiting sequential behaviors [J]. Journal of Software,2014,24(11):2721-2733. [3]Zhang Jia,Lin Yaojin,Lin Menglei,et al.An effective collaborative filtering algorithm based on user preference clustering[J].Applied Inteligence,2016,   
45 (2): 230-240. [4] 于洪，李俊华．一种解决新项目冷启动问题的推荐算法[J].软件学报,   
2015,26(6):1395-1408.(Yu Hong,Li Junhua.A recommended algorithm for solving cold start problems ofnew projects [J].Journal of Software,2015,   
26 (6): 1395-1408.)

[5]荣辉桂，火生旭，胡春华，等．基于用户相似度的协同过滤推荐算法 [J]．通信学报，2014,35(2):16-24.(Rong Huigui,Huo Shengxv,Hu Chunhua,et al. Collaborative filtering recommendation algorithm based on user similarity[J]. Journal of Communications,2014,35 (2):16-24. )

[6]Li Chenyang, He Kejing. CBMR: an optimized MapReduce for item-based collaborative filtering recommendation algorithm with empirical analysis [J] Concurrency and Computation: Practice and Experience,2017,29(10): 129. 138.   
[7]Ba Qilong,Li Xiaoyong,Bai Zhongying. Clustering collaborative filtering recommendation system based on SVD algorithm [C]// Proc of IEEE International Conference on Software Engineering and Service Science. [S. 1.]: IEEE Press,2013: 963-967.   
[8]Hernando A,Bobadilla J,Ortega F.Anon negative matrix factorization for collaborative filteringrecommender systems based ona Bayesian probabilistic model[J]. Knowledge-Based Systems,2016,97(9): 188-202.   
[9]Yazdanfar N,Thomo A.Link recommender:collaborative-filtering for recommending URLs to twitter users [J].Procedia Computer Science,2013, 19 (4): 412-419.   
[10]Park Y,Park S,JungW,etal.Reversed CF:a fastcollaborative filtering algorithm using a K-nearest neighbor graph [J]. Expert Systems with Applications,2015,42 (8): 4022-4028.   
[11]印鉴，王智圣，李琪，等．基于大规模隐式反馈的个性化推荐[J].软 件学报,2014,25 (9):1953-1966.(Yin Jian,Wang Zhisheng,Li Qi,et al. Personalized recommendation based on large-scale implicit feedback [J]. Jourmal of Software,2014,25 (9): 1953-1966. )   
[12]王智圣，李琪，汪静，等．基于隐式用户反馈数据流的实时个性化推荐 [J].计算机学报,2016,39(1):52-64.(Wang Zhisheng,LiQi,Wang Jing, et al.Real-time personalized recommendation based on implicit user feedback data stream [J]. Journal of Computer,2016,39(1): 52-64.）   
[13] Yuan Ting, Cheng Jian, Zhang Xi,et al. A weighted one class collaborative filtering with content topic features [C]// Proc of International Conference on Multimedia Modeling. Berlin: Springer,2013: 417-427.   
[14]LiGai,Zhang Zhiqiang,Wang Liyang,et al.One-class collaborative filtering based on rating prediction and ranking prediction [J]. Knowledge Based Systems,2017,124(8): 46-54.   
[15]黄创光，印鉴，汪静，等．不确定近邻的协调过滤推荐算法[J].计算 机学报,2010,33(8):1369-1377. (Huang Chuang guang,Yin Jian,Wang Jing,et al. Coordinated filtering recommendation algorithm for uncertain neighbors [J].Journal of Computer,2010,33(8): 1369-1377.)   
[16] Kumar NP,Fan Zhenzhen.Hybrid user-item based collaborative filtering [J]. Procedia Computer Science,2015,60 (1): 1453-1461.   
[17]陆艺，曹健．面向隐式反馈的推荐系统研究现状与趋势[J].计算机科 学,2016,43 (4): 7-15. (Lu Yi, Caojian. Research status and trends of recommender system for implicit feedback[J]. Computer Science,2016,43 (4): 7-15. )   
[18]燕彩蓉，张青龙，赵雪，等．基于广义高斯分布的贝叶斯概率矩阵分解

方法[J].计算机研究与发展,2016,52(12):2793-2800.(Yan Cairong, Zhang Qinlong,Zhao Xue,et al. Bayesian probability matrix decomposition method based on generalized Gaussian distribution [J].Journal of Computer Research and Development,2016,52 (12):2793-2800)

[19]Bauer J,Nanopoulos A.Recommender systems based on quantitative implicit customer feedback [J].Decision Support Systems,2014,68(6): 77- 88.