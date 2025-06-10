# 一种结合主题模型的推荐算法

曹占伟，胡晓鹏

(西南交通大学 信息科学与技术学院，成都 611756)

摘要：针对传统协同过滤推荐算法存在的冷启动、数据稀疏以及相似度度量的准确性问题，基于LDA主题模型对文本隐式主题挖掘的有效性和KL散度在主题分布相似性度量的准确性，提出了结合LDA主题模型的矩阵分解推荐算法。首先，利用改进的LDA算法输出项目-主题分布，并用困惑度作为主题数设置的修正函数；然后分别基于余弦相似度和KL散度计算得到项目相似度矩阵，将得到的相似度矩阵结合原评分训练集输出预评分，再将预评分填充到训练集；最后将训练集输入ALS 矩阵分解算法得到推荐结果。通过MovieLens数据集的实验结果表明，该算法在不同隐式参数设定下均能得到比ALS推荐算法以及更小的预测误差，并且最优预测误差小于传统推荐算法。该实验说明了通过集成LDA主题模型的ALS算法效果要优于其他推荐算法。

关键词：推荐算法；矩阵分解；隐式狄利克雷分布；KL散度；主题模型 中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2017.12.0811

# Recommendation algorithm combining theme model

Cao Zhanwei, Hu Xiaopeng (1.SchoolofInformationScience&Technology,Southwest Jiaotong University,Chengdu Sichuan611756,China)

Abstract:Inordertosolvetheproblemofcold startanddata sparsityfor traditional collaborative filteringrecommendation algorithm,and theaccuracyofsimilaritymeasurement,this paper proposedamatrix decompositionrecommendationalgorithm based on theLDAtheme model.Firstly,ituses the improvedLDAalgorithmtooutput theproject-topic distribution,sing the perplexityas themodifiedfunctionofthesubjectnumber; Secondly,itcalculatethesimilaritymatrixof teprojectbasedonthe cosine similarity andthe KL divergence,combineing theobtained similarity matrix with the original scoring training seto output the prescore,andthenflsthepreliminaryscore tothetraining set.Finally,itinput thetrainingsettoALSmatrix decomposition algorithm to get the recommended results.The experimental results ofthe MovieLens data set show that the proposedalgorithmcangetasmaler MAEvalues thanthe taditionalALSalgorithmunderdiferent implicit parametersettings and it greaterthantraditionalrecommdationalgorithm.Theexperiment showsthattheresultsoftheALSalgorithmarebeter than other algorithms by integrating the LDA theme model.

Key words:recommendationalgorithm; matrix decomposition; Latent Dirichlet distribution (LDA);KLdivergence;theme model

# 0 引言

随着互联网的飞速发展，各大电商网站的数据呈现井喷式的增长，为满足用户在海量信息中进行有效选择的需求，推荐系统应运而生，而推荐算法1又是推荐系统的精髓。

主流推荐算法主要包括协同过滤推荐算法、基于内容的推荐、关联规则以及混合推荐方法。其中，协同过滤推荐算法[2]由于具有可利用用户行为数据和基于群体智慧的优势，在当前电商系统中应用最广泛。Zhengzheng等人[3]提出了一种奇异值分解（singular value decomposition,SVD）的协同过滤算法，该法对高阶评分矩阵进行降维，缓解了数据稀疏的问题，但是由于计算复杂度过高以及存在冷启动问题，在商业领域运用并不广泛。Rahul等[4提出利用K-Means算法对用户进行聚类以减小邻居搜索空间,该法考虑到了用户对项目属性的偏好，推荐效果优于传统推荐算法，但是依然存在冷启动问题。Maryam 等人[5]针对用户兴趣的动态性，提出了PIDFAR（potential interestdiscovery method based on fuzzy association rules）方法。该算法结合LDA（latentdirichletallocation），通过模糊关联规则挖掘出兴趣-时间模型，再根据关联规则和主题分布计算项目相似度。该算法在准确率上优于传统推荐算法并缓解了冷启动问题，但

对数据稀疏问题未能深入讨论。

Zhou等人[在NetFlix大赛中首次提出了基于交替最小二乘法（alternating least squares，ALS)的矩阵分解协同过滤算法。该方法在多用户、多项目以及稀疏数据的情况下优于经典的协同过滤算法，并在大赛中取得优异成绩，但是该法并未过多考虑新用户或新项目动态加入的因素，依然存在冷启动问题。

针对上述不足，本文提出了基于主题模型的ALS矩阵分解算法LDA-IT-ALS（LDAinserttoALS）。该方法运用LDA主题模型[7将项目属性映射成输入文档，通过LDA算法输出项目之间的主题分布，进而得到相似度矩阵，然后通过此矩阵与原评分矩阵进行联合操作得到预评分，再将预评分填充到源矩阵中，最后通过ALS算法得到推荐结果。ALS算法缓解了数据稀疏问题，本文算法在此基础上结合主题模型进行数据填充缓解了冷启动问题，并进一步缓解了数据稀疏问题，通过多次实验证明了本文方法能得到更低的预测误差。

# 1 ALS矩阵分解算法与LDA主题模型

# 1.1 ALS算法

协同过滤算法中用户对物品的评分可以表示成一个评分矩阵 $\operatorname { R } ( \operatorname { m } ^ { * } \mathrm { n } )$ ，其中元素 $\mathrm { R _ { i j } }$ 表示索引号为i( $0 { < } \mathrm { i } { < } { = } \mathrm { m }$ ）的用户对索引号为j( $( 0 { < j } { < } = \mathtt { n }$ ）的物品的评分，如表1所示。

在推荐系统中用户对项目的评分往往低于 $5 \% ^ { [ 8 ] }$ ，例如MovieLens数据集的稀疏度是 $4 . 5 \%$ ，Netflix是 $1 . 2 \%$ ，Bibsonomy是 $0 . 3 5 \%$ ，Delicious 是 $0 . 0 4 6 \%$ 。因此表1所示的评分矩阵中的大多数元素往往为空。本文称这些空值为缺失值（MissingValue)。推荐系统中往往需要得到某用户对所有物品的评分，假设 ${ \bf R } _ { 2 2 }$ 为缺失值，则就需要通过某些方法预测 $\mathbf { U } _ { 2 }$ 对$\mathrm { I } _ { 2 }$ 的评分，即“矩阵补全（填充)”。

ALS矩阵补全即通过交替最小二乘法[来填补评分矩阵。ALS 算法的核心基于以下假设：评分矩阵R是近似低秩的，也就是说一个 $\mathbf { m ^ { * } n }$ 的评分矩阵R可以用两个小稠密矩阵 $\mathrm { X } ( \mathrm { m } ^ { * } \mathrm { k } )$ （204号和 $\mathrm { Y } ( \mathrm { n } ^ { * } \mathrm { k } )$ 的乘积来近似表示，如表2和表3所示，其中 ${ \mathrm { R } } { \approx } \mathrm { X Y ^ { \mathrm { T } } }$ $k { < } { < } \mathrm { m }$ 、n， $\mathbf { k }$ 为隐式因子。

表1用户原评分矩阵  

<html><body><table><tr><td></td><td>I</td><td></td><td>I</td><td>…</td><td>I</td></tr><tr><td>U1</td><td>R11</td><td>R12</td><td>R13</td><td></td><td>R1n</td></tr><tr><td>U</td><td>R21</td><td>R22</td><td>R23</td><td></td><td>R2n</td></tr><tr><td>U</td><td>R31</td><td>R32</td><td>R33</td><td></td><td>R3n</td></tr><tr><td>…</td><td></td><td>…</td><td>…</td><td>：</td><td></td></tr><tr><td>Um</td><td>Rm1</td><td>Rm2</td><td>Rm3</td><td>…</td><td>Rmn</td></tr></table></body></html>

表2稠密矩阵X  

<html><body><table><tr><td>F1</td><td>F2</td><td>F3</td><td>…</td><td>Fk</td></tr><tr><td>U1</td><td>X11</td><td>X12</td><td>X13</td><td>： X1k</td></tr><tr><td>U2</td><td>X21</td><td>X22</td><td>X23</td><td>X2k</td></tr><tr><td>U3</td><td>X31</td><td>X32</td><td>X33 ：</td><td>X3k</td></tr><tr><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td></tr><tr><td>Um</td><td>Xm1</td><td>Xm2</td><td>Xm3</td><td>… Xmk</td></tr></table></body></html>

表3稠密矩阵Y   

<html><body><table><tr><td></td><td>F1</td><td>F2</td><td>F3</td><td>：</td><td>Fk</td></tr><tr><td>1</td><td>Y11</td><td>Y12</td><td>Y13</td><td>：</td><td>Y1k</td></tr><tr><td></td><td>Y21</td><td>Y22</td><td>Y23</td><td>：</td><td>Y2k</td></tr><tr><td>I</td><td>Y31</td><td>Y32</td><td>Y33</td><td>：</td><td>Y3k</td></tr><tr><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td></tr><tr><td>I</td><td>Yn1</td><td>Yn2</td><td>Yn3</td><td>：</td><td>Ynk</td></tr></table></body></html>

ALS矩阵分解的目的是将User和Item映射到一个维度为k( $k { < } { < } \mathrm { m }$ 、n）的隐式空间，这样User对Item的评分就可以通过隐式空间矩阵建模。ALS算法求解矩阵X和Y方法如算法1。

算法1 ALS 矩阵分解算法

a）定义损失函数 $C = \sum _ { ( i , j ) \in R } \left[ \left( r _ { i , j } - x _ { i } ^ { T } y _ { j } \right) ^ { 2 } + \lambda \left( \left. x _ { i } \right. ^ { 2 } + \left. y _ { j } \right. ^ { 2 } \right) \right] ,$ 其中 $\mathbf { r } _ { \mathrm { i , j } }$ 代表初始评分矩阵中用户i对项目j的评分， $\mathbf { X } \mathrm { i }$ 为X0 $\mathbf { \chi } _ { \mathrm { m } ^ { * } \mathbf { k } } ^ { }$ ）的第i行的一个列向量， $\mathrm { \ y _ { j } }$ 为 $\mathrm { \Delta Y }$ （ $\mathbf { \hat { \Pi } } _ { \mathbf { n } ^ { * } \mathbf { k } }$ ）的第 $\mathrm { j }$ 行的一个列向量， $\lambda$ 为正则化参数;

b）随机生成一个X(0),一般可以取0值或者全局均值;c）固定 $\mathrm { X } ( 0 )$ 即将 $\mathrm { X } ( 0 )$ 当作常量，求解Y(O)；此时的损失函数为 $C = \sum _ { ( i , j ) \in R } \left[ \left( r _ { i , j } - \left( x _ { i } ^ { ( 0 ) } \right) ^ { T } y _ { j } \right) ^ { 2 } + \lambda \left( \left. x _ { i } ^ { ( 0 ) } \right. ^ { 2 } + \left. y _ { j } \right. ^ { 2 } \right) \right]$

d）由于C中只有 $\mathrm { \Delta V _ { j } }$ 一个未知变量，因此C的最优化问题转换为最小二乘问题，即用最小二乘法求解 $\mathrm { Y _ { j } }$ 的最优解。固定$\{ \mathbf { \Sigma } ( \mathbf { j } { = } 1 , 2 , { \ldots } { \ldots } , \mathbf { n } )$ ，则C的导数

$$
\begin{array} { l } { \displaystyle \frac { \partial C } { \partial y _ { j } } = \frac { \partial } { \partial y _ { j } } \Bigg [ \displaystyle \sum _ { i = 1 } ^ { m } \Bigg [ \left( r _ { i , j } - \left( x _ { i } ^ { ( 0 ) } \right) ^ { T } y _ { j } \right) ^ { 2 } + \lambda \left( \left\| x _ { i } ^ { ( 0 ) } \right\| ^ { 2 } + \left\| y _ { j } \right\| ^ { 2 } \right) \Bigg ] \Bigg ] = } \\ { \displaystyle \sum _ { i = 1 } ^ { m } \Bigg [ 2 \bigg ( r _ { i , j } - \left( x _ { i } ^ { ( 0 ) } \right) ^ { T } y _ { j } \bigg ) \left( - x _ { i } ^ { ( 0 ) } \right) + 2 \lambda y _ { j } \Bigg ] } \\ { \displaystyle = 2 \sum _ { i = 1 } ^ { m } \Bigg [ \left( \left( x _ { i } ^ { ( 0 ) } \right) ^ { T } x _ { i } ^ { ( 0 ) } + \lambda \right) y _ { j } - r _ { i , j } y _ { i } ^ { ( 0 ) } \Bigg ] } \end{array}
$$

e $\frac { \partial C } { \partial \nu _ { j } } = 0$ C=0，可得 （204号 $\sum _ { i = 1 } ^ { m } \biggl [ \biggl ( \left( x _ { i } ^ { ( 0 ) } \right) ^ { T } x _ { i } ^ { ( 0 ) } + \lambda \biggr ) y _ { j } \biggr ] = \sum _ { i = 1 } ^ { m } r _ { i , j } x _ { i } ^ { ( 0 ) }$ $\Big ( X X ^ { T } + \lambda E \Big ) y _ { j } = X r _ { j } ^ { T } ~ \mathrm { ~ c ~ }$ （20

f）令 $\mathbf { M } _ { 1 } = X X ^ { T } + \lambda E , M _ { 2 } = X r _ { j } ^ { T }$ ，可得 $\begin{array} { r } { \boldsymbol { y } _ { j } = \boldsymbol { M } _ { 1 } ^ { - 1 } \boldsymbol { M } _ { 2 } } \end{array}$ ：g)按照步骤c)\~f))依次计算 $\mathbf { y } _ { 1 } , \mathbf { y } _ { 2 } , \mathbf { y } _ { 3 } , . . . , \mathbf { y } _ { \mathrm { n } } ,$ 从而得到 ${ \mathrm { Y } ( 0 ) }$

h）固定Y(0)，来求解 $\mathrm { X } ( 1 )$ 。求解方法同步骤 g)，得到$\Big ( Y Y ^ { T } + \lambda E \Big ) x _ { i } = Y r _ { i } ^ { T }$

令 $\mathbf { M } _ { 1 } = Y Y ^ { T } + \lambda E , M _ { 2 } = Y r _ { i } ^ { T }$ 得 $\boldsymbol { x } _ { i } = \boldsymbol { M } _ { 1 } ^ { - 1 } \boldsymbol { M } _ { 2 }$ 。

i）依照步骤h)依次计算 $\mathrm { x } _ { 1 } , \mathrm { x } _ { 2 } , \mathrm { x } _ { 3 } , . . . , \mathrm { x } _ { \mathrm { m } } .$ 从而得到 $\mathrm { X } ( 1 )$ U

j）循环交替执行步骤a)\~i),直到损失函数C的值收敛或者达到设定的迭代次数，这样就得到了最优解对应的矩阵X，Y。

由算法1得到的矩阵X和Y即可用来近似求解稠密的评分矩阵 $\mathbf { R } { : } = \mathbf { X } \mathbf { Y } ^ { T }$ ， $\mathbf { R ^ { \prime } }$ 中相较于R多出的评分项即为预评分项，

可据此对用户做推荐。

# 1.2LDA主题模型

# 1.2.1主题模型概念

主题模型（TopicModel）是用来在大量文档中提取抽象主题的一种统计模型，它可以根据不同文档中出现相同或者不同词汇的条件概率确定文档的隐主题以及词汇的主题归属。由于同一个主题可能会包含多个词汇，因此文档的比较不再是简单的词汇统计，而是文档中主题出现的概率分布。某个主题中包含的词汇是语义相对相似或者相同的，因此主题可以表示为整个文档集词汇表中词汇的多元分布函数。词汇对应的系数越大，那么词汇的语义越接近主题的语义；反之，和主题的关系越小。归纳起来，文档就是不同主题对词汇集不同词汇分布的分布。

由于TF-IDF方法对文本主题分析的局限性，先后出现了潜在语义分析模型（latent semantic analysis，LSA）、pLSA模型以及马尔科夫模型等，但多存在计算复杂度高、针对多文档的过拟合以及扩展性不好等问题，但它们的出现为潜在狄利克雷分布LDA主题模型的出现奠定了基础[10]。

# 1.2.2LDA算法描述

Blei 等人[7在2003年提出的潜在狄利克雷分布（LDA）是一种无监督的生成模型。该方法认为每篇文档的生成方式如下：先从主题集合中以一定的概率抽取主题，然后再从这个主题对应的词汇集合中以一定的概率抽取当前词汇，循环执行，直到生成整篇文档。

一个词汇的生成概率如式（1）所示。

$$
p ( { \mathrm { w o r d } } | { \mathrm { d o c } } ) = \sum _ { \mathrm { } t o p i c } p ( { \mathrm { w o r d } } | { \mathrm { t o p i c } } ) \times p ( { \mathrm { t o p i c } } | { \mathrm { d o c } } )
$$

LDA模型的生成过程如图1所示，其中K为主题个数，M为总文档数， $\mathrm { { N m } }$ 是第 $\mathrm { ~ m ~ }$ 个文档的词汇总数，β是每个Topic下词的多项分布的Dirichlet先验超参数， $\mathfrak { a }$ 是每个文档下 Topic的多项分布的Dirichlet先验超参数， $Z _ { \mathrm { m , n } }$ 是第 $\mathrm { ~ m ~ }$ 个文档中第n个词汇所属主题， $\mathbf { w } _ { \mathrm { m , n } }$ 是第 $\mathbf { m }$ 篇文档中的第 $\mathfrak { n }$ 个词汇，两个隐变量 $\theta _ { \mathrm { ~ m ~ } }$ 和 $\Phi _ { \textup { k } }$ 分别表示第 $\mathrm { ~ m ~ }$ 篇文档下的Topic 分布和第k个Topic下word的分布，前者是 $\mathbf { k }$ 维(k为Topic 总数)向量，后者是 $\mathbf { v }$ 维向量，其中 $\mathbf { v }$ 为所有文档集中不重复词汇的总数。

图1所示的文档生成过程主要分解为两个物理过程：

a） $\overrightarrow { \alpha }  \overrightarrow { \theta _ { m } }  z _ { m , n }$ ，表示在生成第 $\mathbf { m }$ 篇文档的时候，先从M个doc-Topic 分布函数中抽取分布函数 $\overrightarrow { \theta _ { m } }$ ，然后从多个Topic中抽取一个编号为 $z _ { m , n }$ 的 Topic 作为第 $\mathfrak { n }$ 个词的主题;

b） ${ \overrightarrow { \beta } }  { \overrightarrow { \varphi _ { k } } }  w _ { m , n } \mid k = z _ { m , n }$ ，表示在K个 Topic-word 分布函数中选择编号为 ${ \bf k } = z _ { m , n }$ 的分布，然后在分布中随机选择word作为第 $\mathbf { m }$ 篇文档的第 $\mathfrak { n }$ 个词 $\mathbf { w } _ { \mathrm { m , n } }$

在给定超参数α和β的情况下，LDA的联合共轭分布如式（2）所示，其中 $\overrightarrow { n _ { k } } = ( \mathbf { n } _ { \mathrm { k } } ^ { ( 1 ) } \cdots \mathbf { n } _ { \mathrm { k } } ^ { ( \mathrm { V } ) } )$ ， $ { \mathbf { n } } _ {  { \mathbf { k } } } ^ { ( t ) }$ 表示第 $\mathrm { ~ m ~ }$ 篇文档中第k个主题产生词汇的个数， $\mathbf { k }$ 下标为文档编号。 $\overrightarrow { n _ { m } } = ( \mathbf { n } _ { m } ^ { ( 1 ) } \cdots \mathbf { n } _ { m } ^ { ( \mathrm { K } ) } ) ,$ $ { \mathbf { n } } _ { m } ^ { ( t ) }$ 表示第 $\mathrm { ~ m ~ }$ 篇文档中第k个主题产生的词汇的个数，k下标为Topic 编号。

$$
p ( \overrightarrow { \mathbf { w } } , \overrightarrow { \mathbf { z } } | \overrightarrow { \alpha } , \overrightarrow { \beta } ) = p ( \overrightarrow { \mathbf { w } } \mid \overrightarrow { \mathbf { z } } , \overrightarrow { \beta } ) p ( \overrightarrow { \mathbf { z } } \mid \overrightarrow { \alpha } )
$$

$$
= \prod _ { k = 1 } ^ { K } \frac { \Delta ( \overrightarrow { n _ { k } } + \overrightarrow { \beta } ) } { \Delta \overrightarrow { \beta } } \prod _ { m = 1 } ^ { M } \frac { \Delta ( \overrightarrow { n _ { m } } + \overrightarrow { \alpha } ) } { \Delta \overrightarrow { \alpha } }
$$

以上是LDA定义的文档生成过程，而实际情况是LDA生成过程的逆过程。已知文档集，需要对联合分布 $p ( \vec { \mathrm { w } } , \vec { \mathrm { z } } )$ 进行采样。采样的方法包括变分-EM算法、Gibbs抽样法和最大似然估计法。本文采用Gibbs 抽样法采样主题分布，有关细节可查看文献[11]。

![](images/d27a6a392a9255ba16478af3ad2420c1325cad2f25d8b4a33a71eaacb1f7109f.jpg)  
图1LDA 图模型

# 2 本文改进算法

ALS 矩阵分解推荐算法虽然优于基于邻域的协同过滤算法，但是依然存在数据稀疏以及冷启动问题，这些问题对实际推荐准确率有很大影响。本文提出了一种结合LDA 主题模型的ALS 算法，即LDA-IT-ALS算法。该算法利用LDA模型对项目信息进行建模，将项目文件中的每一行（单个项目的描述信息）转换为主题的分布，不仅对文档进行了降维而且挖掘出了不同词可能包含的相同或相近的主题信息。在这些信息的基础上进行的项目相似度的计算更符合人的常规思维方式。主题分布信息经过本文方法处理后变成项目相似度矩阵，然后结合原评分矩阵产生预评分填充到原评分矩阵中形成新的输入集输入ALS 算法。

# 2.1算法过程描述

本文所用到的数据集为美国GroupLens提供的MovieLens数据集[12]。算法主要包括项目文件处理及主题分布的计算、项目相似度矩阵求解、预评分求解及填充、ALS矩阵分解及推荐。

# 2.1.1文件处理及主体分部计算

本步骤用到了u.Item文件以及u.genre 文件。文件u.Item每行描述一部电影，不同的描述项（电影属性)以单竖线分割：第1项为索引号，第2项为电影名、第3项为上映日期，第4项为空，第5项为网址信息，第6\~24项为以位图描述的电影类型（如果某部电影属于某个类型，则对应的位图为1，否则为0)。文件u.genre 描述电影类型及索引号，每行描述一个电影类型，共19 行。

本步骤又可分为两个子过程，处理流程如图2所示。

![](images/c5320522e2a13358f9e32d469cbf10c582203e738c276cdf4dbd984bf2397a62.jpg)  
图2项目文件处理

1）电影描述文件预处理

u.Item文件不能直接作为主题分布计算模块的输入文件。需要将u.Item的位图信息转换为电影类型信息，提取电影名称及上映日期，并过滤掉干扰信息。经过处理后的文件为u.word，文件中每一行表示一部电影的文本信息，例如电影Toy Story 的信息为（Toy Story Janl995Animation Children's Comedy）。

# 2）主题分布计算

将u.word转换成主题分布文件，用到了LDA算法。由于Blei 提出LDA 算法的初衷是利用隐式主题对文本进行分类，源码在读文件模块读入对象是以一个项目对应一个文件的形式存在，而步骤1）中得到的u.word文件约1600行文本，其中一行代表一部电影。为满足后续实验要求以及避免大量文件读取时造成频繁的磁盘读操作而降低效率，本文对BIei的读模块进行了改进，将逐文件处理变为了逐行处理。

在完成读模块的改写后，需要对u.word进行联合分布的采样以及主题分布的输出，具体过程参考1.2.2节。为提高主题分布对电影的区分效果，本文引入了困惑度[13]，表示对不同物品间的区分能力,困惑度越小其区分效果越好。困惑度由式（3）所示，其中W为语料集， $\mathrm { w } _ { \mathrm { m } }$ 为语料中的单词， $\mathrm { { N } _ { \mathrm { { m } } } }$ 为单词数量。

$$
p e r p l e x i t y ( W ) = \exp \left\{ - \frac { \displaystyle \sum _ { m } \ln p \big ( w _ { m } \big ) } { \displaystyle \sum _ { m } N _ { m } } \right\}
$$

在不同的主题数前提下得到多个具有不同困惑度的主题分布，设置最小困惑度对应主题数进行再一次LDA算法，得到的主题分布矩阵如图3所示，其中 $\mathsf { p i j } ( 1 { \leq } \mathrm { i } { \leq } \mathsf { m } , 1 { \leq } \mathrm { j } { \leq } \mathsf { n } )$ 为第i个项目的第j个主题的条件概率。

$$
\left( { \begin{array} { l l l l } { p _ { 1 1 } } & { p _ { 1 2 } \cdots } & { p _ { 1 n } } \\ { p _ { 2 1 } } & { p _ { 2 2 } \cdots } & { p _ { 2 3 } } \\ { \vdots } & { \vdots } & { \vdots } \\ { p _ { m 1 } } & { p _ { m 2 } \cdots } & { p _ { m n } } \end{array} } \right)
$$

图3主题分布矩阵

# 2.1.2项目相似度矩阵求解

在主题分布矩阵基础上进行项目相似度矩阵求解，主要过程为两两之间计算相似度。

1）相似度选择

常见的相似度的度量方式有余弦相似度、Jaccard、欧式距离等，最为常用的为余弦相似度。本文对余弦相似度和文献[14]提到的KL散度进行对比。

余弦相似度是通过计算两个向量的夹角余弦值来评估它们的相似度，计算公式如式（4）所示，其中 $\mathbf { A } _ { \mathrm { i } }$ 代表向量A的在维度i上的值，Bi代表向量B的在维度i上的值， $\mathfrak { n }$ 为维度。

KL 散度又叫相对熵或者互熵、交叉熵，用于度量两个随机变量的距离，计算公式如式（5）所示，其中 $\mathfrak { p } ( \mathbf { x } )$ 和 ${ \bf q } ( { \bf x } )$ 是关于变量X取值的概率分布函数。由于KL散度是两个概率分布 $\mathrm { ~ \bf ~ P ~ }$ 和Q的非对称性的度量，一般采用 $\mathrm { ( D ( p | | q ) { \mathrel { + } } D ( q | | p ) ) } / 2$ 度量两个分布间的距离。在此需要将距离转换为相似度，并且归一化。用常用的sigmoid函数进行转换，公式如式（6）所示，其中D为 $\mathrm { ( D ( p | | q ) { \mathrel { + } } D ( q | | p ) ) } / 2$ 0

$$
\cos \theta = \frac { \sum _ { 1 } ^ { n } ( A _ { i } \times B _ { i } ) } { \sqrt { \sum _ { 1 } ^ { n } A _ { i } ^ { 2 } } \times \sqrt { \sum _ { 1 } ^ { n } B _ { i } ^ { 2 } } }
$$

$$
\operatorname { D } ( p \| q ) = \sum _ { 1 } ^ { n } p ( x ) \log { \frac { p ( x ) } { q ( x ) } }
$$

$$
S ( \mathbf { x } ) = \frac { 1 } { 1 + e ^ { - D } }
$$

# 2）相似度后处理

将图3中的主题分布矩阵分别根据1）中的两种方式逐行两两计算相似度，得到相似度矩阵。为方便后续流程，生成的相似度矩阵实际上以三元组形式存在，形如（item1，item2，sim)。

后续求解预评分根据邻居项目已存在的评分来估计空白处的评分，因此相似度矩阵需要以固定阈值过滤掉相似度小的项。本文按照文献[16]的方法取阈值为0.9，得到的相似度矩阵后续称为高相似度矩阵。

# 2.1.3预评分求解及填充

结合原评分矩阵以及高相似度矩阵预测某些缺失评分项，原评分矩阵文件为u.data，其评分是以三元组形式存在，形如（user，item，rate)，本文主要根据当前项目和邻居项目间的相似性集合和用户对项目结合的评分预测缺失项，主要过程如算法2。

算法2 预评分求解

a)定义preMarkMap，其数据结构为Map<Integer,Map<Integer,Double>>b)定义markMap存储评分数据，其数据结构为Map<Integer,Map<Integer,Double>>c)逐行遍历原评分文件，User 和 ItemMap 保存在markMap  
中，形如 $[ ( \mathbf { u } _ { 1 } , [ ( \mathbf { i } _ { 1 } , \mathbf { v } _ { 1 1 } ) , ( \mathbf { i } _ { 2 } , \mathbf { v } _ { 1 2 } ) ] ) , ( \mathbf { u } _ { 2 } , [ ( \mathbf { i } _ { 1 } , \mathbf { v } _ { 2 1 } ) , ( \mathbf { i } _ { 2 } , \mathbf { v } _ { 2 2 } ) ] ) . . . ]$ d)定义ItemSimMap，数据结构为Map<Integer,Map<Integer,Double>>e)逐行遍历相似度矩阵，Iteml 和Item2List 保存于  
ItemSimMap 中，形如 $[ ( \mathrm { i } _ { 1 } , [ ( \mathrm { i } _ { 2 } , \mathrm { v } _ { 1 2 } ) , ( \mathrm { i } _ { 3 } , \mathrm { v } _ { 1 3 } ) ] ) , ( \mathrm { i } _ { 2 } , [ ( \mathrm { i } _ { 3 } , \mathrm { v } _ { 2 3 } ) , ( \mathrm { i } _ { 4 } , \mathrm { v } _ { 2 4 } ) ] ) \ldots ]$ f)遍历 markMap，获取当前User 的 ItemMap，遍历每个

ItemSimMap，如果ItemMap中不包含当前Item值，那么当前User对当前Item的预评分可通过如下方式求解：

(a)通过当前 Item 获取其 value1Map 形如[(i2,v12),(i3,V13)...](b)通过当前User 获取其 value2Map 形如 $[ ( \dot { \bf i } _ { 1 } , { \bf v } _ { 1 1 } ) , ( \dot { \bf i } _ { 2 } , { \bf v } _ { 1 2 } ) . . . ]$ (c)设置局部变量sum和n(d)遍历valuelMap，获取当前ItemTmp，当前值为value1Tmp.遍历value2Map 查找键为ItemTmp 的项，值为value2Tmp.将(value1Tmp\*value2Tmp+value1Tmp/value2Tmp)/2叠加到sum，n自增1(e)将当前User，ItemTmp， $\mathrm { { s u m } / n }$ 的值写入preMarkMapg）循环执行步骤e）f)，最后输出preMarkMap。算法2简要的描述了预评分求解过程，将输出的预评分填充到原评分文件即可作为ALS矩阵分解算法的训练集。

# 2.1.4矩阵分解及推荐

在得到训练集的前提下，利用1.1节的算法进行求解并推荐。在1.1节提到了隐式参数，本算法将平均绝对误差MAE[15]值作为隐式参数的修正目标函数：MAE越小证明推荐预测效果越好。MAE 定义如式(7)，其中 $\mathfrak { p } \mathrm { i }$ 为预测评分， $\mathbf { q } _ { \mathrm { i } }$ 为真实评分，N 为测试集评分数。

$$
\ M A E = { \frac { \displaystyle \sum _ { i = 1 } ^ { N } \left| p _ { i } - q _ { i } \right| } { N } }
$$

通过修正MAE得到的最优模型即可对用户进行推荐，比如对用户 $\mathbf { U } _ { 1 }$ 的预测矩阵如表3所示，那么就可以根据预测集合优先推荐I和 $\mathrm { I } _ { 6 }$ 给用户 $\mathbf { U } _ { 1 }$ 。

表3用户预测评分矩阵  

<html><body><table><tr><td></td><td>I</td><td></td><td>I</td><td></td><td>16</td></tr><tr><td>U1</td><td>3.3</td><td>3.5</td><td>4.6</td><td></td><td>5.7</td></tr></table></body></html>

# 3 实验对比及结果分析

本实验使用的数据集来自美国GroupLens 研究小组提供的MovieLens数据集。数据集中包括943个用户描述文件，1682个电影信息描述文件，10万个评分记录。本文从数据集中抽取$80 \%$ 作为训练集，利用LDAIT-ALS算法进行推荐， $20 \%$ 的测试集检测算法的效果。使用5折交叉平均实验结果减少误差，采用MAE作为评价标准，实验方法如第2节所示。本文算法由JAVA 实现，实验平台为Windows7-64 位双核,IDE 为Eclipse。

# 3.1与ALS 算法对比实验

# 3.1.1LDA主题数设置

为了能保证LDA算法的处理效果，首先需要对主题数的设置进行调整，以困惑度作为主题数的修正参数。

首先将主题数设置在5\~50，步长为5，困惑度与主题数的关系如图3所示，topNum代表主题数，perplexity代表困惑度，发现在topNum为5-10之间perplexity 最小。然后设置 topNum

在1-10，步长为1，困惑度与主题数的关系如图4所示。困惑度在topNum为6的时候最小，因此本文后续实验主题数固定为6。

![](images/4d5fc7841a10b2a252bb9d2acf73d201ecb0627e27e2abd5ae722db880441fc8.jpg)  
图3困惑度与主题数(步长为5)

![](images/d05c12573eb7fdc8bdafee22f7e6e085de35bcb04de8fd3f9b749403950116ed.jpg)  
图4困惑度与主题数(步长为1)

# 3.1.2与ALS算法对比

为验证本文算法的有效性，在不同隐式参数设置下将ALS算法和本文算法进行对比。另外，还将本文算法中处理项目相似度的方式进行纵向对比。

首先设定隐式参数从5\~40，步长为5，对比结果如图5所示。发现在5\~10的MAE值最小，然后设定隐式参数从5\~10，步长为1进行对比。结果如图6所示，在MAE为3的时候三种算法均能达到最小误差，并且本文算法的MAE 值小于ALS算法的MAE值。

![](images/4d089fbc91c6b7edcb950caa0ad9e5c7f5e14eddcb4df11ddc9dbbcf95ffb39e.jpg)  
图5隐因子step $^ { - 5 }$ 时算法对比

![](images/48a2028d269bb368ee7fd3cbb1f01a5b934933f6fd5bb2f090aece8f038fd9b5.jpg)  
图6隐因子 step $_ { \mathrm { = } 1 }$ 时算法对比  
图7推荐算法对比

# 3.2其他推荐算法比较

为了进一步证明本文算法的有效性，择取文献[17]提出的算法以及基于用户和基于物品的协同过滤算法进行比较。由于后三种算法采用的是邻居用户或者邻近项目的调参方式，不同于本文，所以采取最优值进行比较。为保证实验结果的有效性，采用统一数据集，统一实验平台以及统一评价标准MAE，将各个算法调参后的最优值作为最后统计结果。调参方法分别参考本文3.1节以及文献[17]，最后得到的结果如图7所示。

0.755 0.74950.745 0.75 三0.740.30.7250.720.7150.71ULR-UserCF ULR-ItemCF （cosine） （KL散度）LDA-IT-ALS LDA-IT-ALS (算法类型

# 3.3 实验结果分析

通过实验证明，本文算法平均绝对误差在设定不同隐因子的情况下均小于ALS算法，同时也要优于文献[17的算法。通过图6可以发现ULR-ItemCF算法优于ItemCF算法和ALS算法，原因在于ULR-ItemCF算法也是利用了项目的描述信息，缓解了冷启动问题，这也进一步证明了项目描述信息在推荐算法中的重要性。同时，也可以发现本文算法LDA-IT-ALS的最小MAE值为0.7257，效果要好于ULR-ItemCF算法，原因在于本文算法采用的主题模型生成的预评分正好填充了ALS算法训练集所缺的评分项，缓解了数据稀疏性并且解决了冷启动问题。例如，若表1中 $\mathrm { I } _ { 3 }$ 是新上映电影，那么 $\mathrm { R } _ { 1 3 } { \sim } \mathrm { R } _ { \mathrm { m } 3 }$ 都为空值，如果将此时数据集作为训练集，推荐系统无法对用户进行个性化推荐，也即出现了冷启动问题。在利用本文方法预测空白值并填充后，再根据后续步骤即可进行正常推荐。另外，在实验中对项目相似度矩阵求解方法余弦相似度和KL散度进行对比，结果KL散度实验效果优于余弦相似度。原因是KL散度本身更适合计算两个概率分布之间的距离，而余弦相似度更适用于实际空间物理角度的计算。

# 4 结束语

本文提出的结合LDA主题模型的ALS推荐算法(LDA-IT-ALS）属于管道式[14]的集成算法。利用改进算法建模将项目描述信息处理成主题分布信息，然后融入到评分文件中，解决了冷启动问题并缓解了数据稀疏问题，使推荐准确度得到提高。再者，本文对LDA 原创作者的源码进行了改进以适应本实验的处理流程，避免了磁盘频繁读取的问题。另外，在项目相似度计算时引入了KL散度，提升了相似度度量准确率，减小了推荐误差，与传统推荐算法相比准确度有所提高。但是推荐算法依然面临许多问题，比如安全性、实时性问题。本文后续工作将着重于将LDA-IT-ALS算法并行化，实现其在线实时处理。

# 参考文献：

[1]Guo Yan,Wang Minxi,Li Xin.Application of an improved Apriori algorithm in a mobile e-commerce recommendation system [J].Industrial Management& Data Systems,2017,117(2).   
[2]Wei Jian,He Jianhua,Chen Kai,et al.Collaborative filtering and deep learning based recommendation system for cold start items [J].Expert Systems with Applications,2017, 69.   
[3]Xian Zhengzheng,Li Qiliang,Li Gai,et al.New collaborative filtering algorithms based on SVD $^ +$ and differential privacy[J].Mathematical Problems in Engineering,2017,2017.   
[4]Katarya R,Verma O P.An effective collaborative movie recommender system with cuckoo search [J].Egyptian Informatics Journal, 2016.   
[5]Najafabadi M K, Mahrin MN, Chuprat S,et al. Improving the accuracy of collaborative filtering recommendations using clustering and association rules mining on implicit data [J]. Computers in Human Behavior, 2017,67 (C): 113-128.   
[6]Zhou Y, Wilkinson D,Schreiber R,et al. Large-Scale Parallel Collaborative Filtering for the Netflix Prize [C]// Proc of International Conference Algorithmic Aspects in Information and Management.20o8:337-348.   
[7]Blei D M,Ng AY, Jordan MI. Latent dirichlet allocation [J].Journal of Machine Learning Research,2003,3: 993-1022.   
[8]Villegas N M, Sanchez C,Diaz-Cely J,et al. Characterizing context-aware recommender systems: a systematic literature review [J]. Knowledge-Based Systems,2017.   
[9]印鉴，王智圣，李琪，等．基于大规模隐式反馈的个性化推荐[J]．软 件学报,2014,25 (9):1953-1966.   
[10] Peritz M.Ein Bruchstick aus J'hudah Hajjug's arabischem Werke üiber die hebraischen Zeitworter mit schwachen Stammlauten [J]. Zeitschrift fuir die Alttestamentliche Wissenschaft,2009,13（1).   
[11] Chai Huimin,Lei Jiangnan,Fang Min.Estimating Bayesian networks parameters using EM and Gibbs sampling [J].Procedia Computer Science, 2017,111: 160-166.   
[12] MovieLens10oKDataset[DB/OL].https:/grouplens.org/datasets/

movielens/

[13] Zhao Weizhong,Chen JJ,Perkins R,et al.A novel procedure on next generation sequencing data analysis using text mining algorithm[J].BMC Bioinformatics,2016,17(1):301.

[14]项亮．推荐系统实践[M].北京：人民邮电出版社,2012.

[15] Zhao Weizhong,Chen JJ,PerkinsR,etal.Aheuristic approach to determine an appropriate number of topics in topic modeling[J].BMC Bioinformatics,

2015,16(13): S8

[16]Moreno MN,Segrera S,LopezVF,et al.Web mining based framework for solving usual problems in recommender systems:a case study for movies' recommendation [J].Neurocomputing,2016,176 (C): 72-80.

[17]高娜，杨明.嵌入LDA主题模型的协同过滤推荐算法[J].计算机科学，2016,43 (3):57-61,79.