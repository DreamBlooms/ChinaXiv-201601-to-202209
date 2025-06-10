# 基于项目模糊相似度的协同过滤推荐算法

王森，陈莉，张洁(西北大学 信息科学与技术学院，西安 710127)

摘要：针对传统协同过滤算法中评分和标签存在的模糊性问题进行了研究，利用梯形模糊数描述评分与满意度的映射关系，在考虑评分稀疏性的基础上构建了一种新的梯形模糊评分模型以判断基于模糊评分的相似度，分析标签与项目的隶属度，构建模糊项目标签矩阵以衡量基于标签隶属度的相似度，最终采用改进的评分预测策略进行评分估计。在MovieLens 数据集上的实验结果显示，所提算法在抑制项目冷启动、缓解模糊性和稀疏性问题的同时，提高了预测精度，表明了该算法的有效性。

关键词：协同过滤；模糊相似度；梯形模糊评分模型；模糊项目标签矩阵 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2020.04.0056

Collaborative filtering recommendation algorithm based on item fuzzy similarity

Wang Sen, Chen $\operatorname { L i } ^ { \dagger }$ , Zhang Jie (SchoolofInformationScience&Technology,Northwest University,Xi'an71o127,China)

Abstract:In viewofthe problemoffuzzness ofratingand tagin traditionalcollaborative filteringalgorithms,a trapezoidal fuzzy number was used to describe the mapping relationship between rating and satisfaction.The algorithm considered the impact ofsparsenessofthe rating,constructed anew trapezoidalfuzzy rating modeltodetermine thesimilaritybasedon fuzzy rating,analyzedthe degreeof membership betweenthe tagandthe item,ndconstructedafuzzyitem-tag matrix to measure thesimilaritybasedonthedegreeoftag membership.Finaly,the improved scoring prediction strategy wasusedtoestimate the score.The experimentalresults on the MovieLens dataset show that the proposed algorithm improves the prediction accuracy while suppressing thecold startof the project,alleviating the problems offuziness and sparseness,which ndicate the effectiveness of the proposed algorithm.

Key words: collaborative filtering; fuzzy similarity; trapezoidal fuzzy rating model; fuzzy item-tag matrix

# 0 引言

伴随着信息技术的蓬勃发展，机构和个人用户产生的数据量急剧增加，导致WEB用户难以高效获取有价值的信息[1]。推荐系统因其可以主动预测用户需求，为用户推荐数据的特点，已成为缓解信息过载问题最常用的方法之一。

协同过滤(collaborative filtering,CF)是目前应用最广泛的推荐技术，其借助“物以类聚、人以群分”的思想，认为用户对项目的偏好可以根据邻域的其余用户对项目的评价进行推测，或者根据用户对目标项目邻域的评价进行推测[2]。但是，由于互联网数据的急剧增加和用户习惯的缺陷，协同过滤算法依然面临着稀疏性、冷启动等问题。

学者们针对以上问题展开了研究，例如，Wei等人[3]将时间感知协同过滤模型timeSVD $^ { + + }$ 与深度学习架构 SDAE相结合，利用SDAE提取项目内容特征，使用timeSVD $^ { + + }$ 模型预测评分以解决项目冷启动问题。Hu等人[4]提出了一种相似度增强机制，通过中间用户和项目发掘潜在的相似性关系，并从相似邻居中提取更多数据以减少稀疏性问题。但是此类研究大多未考虑协同过滤的模糊性问题[5\~7]，影响了推荐质量，

模糊性问题是指协同过滤算法的输入通常具有模糊性。例如在电影评分系统中，用户需要从给定评分集合中选择某评分以表达自己对项目的满意度，但是有限的评分不能充分表达用户的偏好差异，往往只能选择一个接近自己喜好程度的评分，这就意味着相同评分并不代表用户的偏好完全一致。另外，由于时间、心情和环境等因素的影响，相同的满意度也可能表现为不同的评分。这种评分-满意度关系的不确定性被称为评分模糊性。此外，推荐系统中还存在项目标签隶属度不确定等模糊性问题。

针对该问题，学者们提出了模糊协同过滤算法，使用模糊理论更恰当地表达协同过滤算法输入数据蕴涵的信息，提升预测精度。Tsai等人[8采用模糊集度量两个业务之间的相似度，以预测两家企业吸引同一用户的可能性。该算法的准确率高于对比算法 $3 3 \%$ ，体现了算法的优势。但是其所构建的评论网络仅仅是基于同一个用户对两家企业发表评论的二进制变量，未考虑评论的方差，有进一步改进预测模型的必要。VashisthP等人[9]使用区间2型模糊集创建用户模型，以捕捉不同用户行为的模糊性，基于此提出了模糊特征混合方法(fuzzy feature combination hybridzation method,FFCHM),改善了数据稀疏性问题，但是该方法的时间复杂度过高，可扩展性低。WasidM等人[0针对基于内存的协同过滤的可扩展性问题，提出了一种基于用户模糊特征的推荐系统，他们认为大多数用户特征在本质上是模糊的，使用模糊集可以更精确地描述用户特征。该算法相比于传统协同过滤算法在MAE、覆盖率、准确性和效率等指标上都有提升。Kant等人[1]使用局部模糊距离和全局模糊距离衡量用户和项目相似度以提升预测精度。实验结果表明该算法的覆盖率较高、MAE值较低，但是在稀疏数据集中的表现不佳。ZhangX等人[12]使用三角模糊数描述用户对项目的综合评价，根据三角形面积和中点衡量三角模糊数相似度以确定用户相似度，提升了相似度计算的准确率。然而三角模糊数中隶属度的最大值只对应一个点，灵活性逊于梯形模糊数，导致可扩展性较低。吴毅涛等人[13]借鉴年龄模糊模型将满意度映射到原始评分上，引入梯形模糊相似度计算策略衡量用户相似度以提升推荐效果。他们使用数学方式证明了模糊相似度是余弦相似度在模糊域上的扩展，实验结果表明该算法的预测精度优于基于三角模糊数的协同过滤算法。但是该算法的模型是固定的，无法随着数据集和用户的改变而自动调整。2017年，吴毅涛等人[14]在文献[13]的基础上，根据评分的分布情况自动生成个性化梯形模糊评分模型，基于模糊相似度和模糊评分实施评分预测以改进推荐质量，实验结果表明该算法的预测误差较低。但是该算法的模型未考虑评分数据的稀疏性问题，致使部分低频率评分对应的梯形模糊数误差较大。

综上所述，模糊协同过滤算法可降低输入数据的模糊性，  
提高相似度计算的准确率，提升推荐质量。但是，目前大多  
数模糊协同过滤算法依然存在以下几个方面的问题。a）只模糊化协同过滤的部分过程，缺少对数据预处理、  
相似性计算和评分预测等全过程实施模糊化的算法。b)模糊数的相似度计算只考虑常规距离和重心距离，误  
差仍然较大。c）忽略数据稀疏性对模糊化准确率的影响。

针对以上不足，本文改进稀疏数据导致的评分数据统计噪声的问题，将评分转换成梯形模糊数，使用新的梯形模糊相似度计算策略判断基于模糊评分的项目相似性(itemsimilarity basedonfuzzyrating,FRIS)，利用模糊隶属度将标签与项目的关系由{0,1}扩展为[0,1]，并以此判断基于标签隶属度的项目相似度(item similarity based on tags membership,TMIS)，然后融合以上两种相似度形成项目相似度，使用一种新的模糊评分预测策略进行评分估计，最终用于推荐。在MovieLens100K和1M数据集上进行实验，结果表明本文算法可在一定程度上改善模糊性和稀疏性带来的不利影响，抑制项目冷启动问题。

# 1 相关工作

# 1.1模糊集合与模糊数

经典集合论中元素i与集合U的关系只能是属于或者不属于，且满足式(1)，其中 $\oplus$ 表示异或关系。

$$
[ ( i \in U ) \oplus ( i \notin U ) ] = 1
$$

然而现实世界中的概念大多不是非此即彼的。例如交通工具的时速，有人认为 $6 0 \mathrm { k m / h }$ 的速度快，另一部分人认为慢。

针对以上问题，L.A.Zadeh教授[15]提出了模糊理论，使用数学工具描述客观世界的模糊现象，利用隶属度函数将二值逻辑改进为连续值逻辑。

模糊集合是模糊理论的数据表现形式，若给定论域U，集合 $A$ 有式(2)所示的映射关系，则称 $A$ 是模糊集合。

$$
\mu _ { _ A } { : } U \to [ 0 , 1 ] , \ \mathfrak { u } \mapsto \mu _ { _ A } ( u )
$$

$\mu _ { _ A }$ 是 $\mathbf { \Psi } _ { A }$ 的隶属度函数， $\mu _ { _ A } ( u )$ 的范围是[0,1]。若将模糊集合的隶属度 $\mu _ { _ A } ( u ) \in [ 0 , 1 ]$ 变为 $\mu _ { _ A } ( u ) \in \{ 0 , 1 \}$ ，则模糊集合退化为经典集合。

模糊数是满足特定要求的模糊集合，可以更精确地表现协同过滤的映射关系，同时也方便数学处理，模糊数的相关概念如定义1和2所示。

定义1假设 $A \in F ( R )$ ，对于 $\forall \lambda \in \left( 0 , 1 \right]$ ，称 $A _ { \lambda } = \left\{ u \in U \vert \mu _ { _ A } ( u ) \geq \lambda \right\}$ 为 $A$ 的 $\lambda$ 截集， $\lambda$ 为置信度，其中 $A \in F ( R )$ 表明 $\mathrm { \bf A }$ 是实数集R上的模糊集。

定义2假设 $A \in F ( R )$ ， $\exists { x } \in R$ 使得 $\mu _ { _ A } ( x ) { = } 1$ ，且 $\forall \lambda \in ( 0 , 1 ]$ ，$A _ { \lambda }$ 是闭区间，则称 $A$ 是模糊数。

# 1.2梯形隶属度函数

隶属度函数决定了对象与模糊集合之间的隶属度，可用来描述模糊集合，目前常用的隶属度函数有三角形、梯形、高斯型和钟型等函数。

三角形与高斯型隶属度函数的趋势类似，隶属度先升高再降低，区别在于高斯型的曲线可以更精确的描述模糊概念。这两种函数适用于描述某一明确定义的附近范围，在明确定义处，隶属度最大。但由于以上两种函数只允许一点处的隶属度为最大值，故不符合用户评分的习惯。

梯形与钟型隶属度函数的趋势类似，隶属度先升高再保持最后降低，但是由于钟型隶属度函数构建模型的时间消耗过大，故可行性较低。梯形隶属度函数因为容易操作、计算简单且比较贴合大多数模糊概念的特点，应用场景最为广泛。并且，梯形隶属度函数可以通过调整参数退化成三角隶属度函数以扩大适用范围，可扩展性强。所以，本文拟使用梯形隶属度函数改进满意度与评分的映射关系，以提升推荐效果。梯形模糊隶属度函数如图1所示，定义如式(3)所示。

$$
\begin{array} { r } { T r a p ( x ; a , b , c , d ) = \left\{ \begin{array} { l l } { 0 , x \leq a } \\ { \displaystyle { \frac { x - a } { b - a } } , a \leq x \leq b } \\ { 1 , b \leq x \leq c } \\ { \displaystyle { \frac { d - x } { d - c } } , c \leq x \leq d } \\ { 0 , d \leq x } \end{array} \right. } \end{array}
$$

![](images/aa4798776c5f7485d1adbe19b92fd9419f6ffe45a7be8bb171994629a15fa37c.jpg)  
图1梯形隶属度函数  
Fig.1Trapezoid membership function

# 1.3梯形模糊数的运算

使用梯形隶属度函数的模糊数被称为梯形模糊数。梯形模糊数可以使用梯形四个顶点的横坐标和最大隶属度进行描述。具体定义如式(4)所示。

$$
\pmb { A } _ { i } = \left( a _ { i , 1 } ^ { ^ A } , a _ { i , 2 } ^ { ^ A } , a _ { i , 3 } ^ { ^ A } , a _ { i , 4 } ^ { ^ A } ; W _ { i } \right)
$$

上式中 $a _ { i , j } ^ { \ A }$ 表示梯形模糊数 $A _ { i }$ 的 $\mathrm { ~ j ~ }$ 个顶点的横坐标值，$\boldsymbol { W } _ { i }$ 表示该梯形模糊评分的最大隶属度。

假设有两个梯形模糊数 $A _ { i }$ 和 $\boldsymbol { A } _ { k }$ ，则它们的加、减、乘、除运算如式(5)(6)(7)和(8)所示。

$$
A _ { i } ^ { + } A _ { k } ^ { - } \binom { a _ { i , 1 } ^ { A } + a _ { k , 1 } ^ { A } , a _ { i , 2 } ^ { A } + a _ { k , 2 } ^ { A } , a _ { i , 3 } ^ { A } + a _ { k , 3 } ^ { A } , } { a _ { i , 4 } ^ { A } + a _ { k , 4 } ^ { A } ; W _ { \mathrm { i } } + W _ { k } }
$$

$$
A _ { i } ^ { - } A _ { k } ^ { - } { = } \left( \begin{array} { l } { { a _ { i , 1 } ^ { 4 } { - } a _ { { i , 1 } } ^ { ^ A } , a _ { { i , 2 } } ^ { ^ A } { - } a _ { { i , 2 } } ^ { ^ A } , a _ { { i , 3 } } ^ { ^ A } { - } a _ { { k , 3 } } ^ { ^ A } , } } \\ { { a _ { i , 4 } ^ { ^ A } { - } a _ { { k , 4 } } ^ { ^ A } ; W _ { \mathrm { i } } { - } W _ { k } } } \end{array} \right)
$$

$$
{ A _ { i } } ^ { * } t = \left( { a _ { i , 1 } ^ { ^ A } } ^ { * } t , { a _ { i , 2 } ^ { ^ A } } ^ { * } t , { a _ { i , 3 } ^ { ^ A } } ^ { * } t , { a _ { i , 4 } ^ { ^ A } } ^ { * } t ; { W _ { \mathrm { ~ i ~ } } } ^ { * } t \right)
$$

$$
A _ { i } ^ { ~ / ~ t = } \big ( a _ { i , 1 } ^ { ~ A } / t , a _ { i , 2 } ^ { ~ A } / t , a _ { i , 3 } ^ { ~ A } / t , a _ { i , 4 } ^ { ~ A } / t ; W _ { \mathrm { i } } / t \big )
$$

本文将结合以上公式，改进现有协同过滤系统的评分预测策略，利用邻域的梯形模糊评分预测目标评分。

# 1.4信息量

香农在信息论中通过事件发生的不确定性度量事件包含的信息量，即事件发生的可能性与其包含的信息量成反比。信息量计算如式(9)所示。

$$
H ^ { ' = - } p ^ { i } * \log _ { 2 } p ^ { i }
$$

其中， $\boldsymbol { H } ^ { i }$ 表示事件i的信息量， $p ^ { i }$ 表示事件i发生的概率。

本文拟通过评分出现的概率计算评分信息量，以此作为权重调整不同项目对用户相似性的贡献度，以提升相似度计算的准确率。

# 2 基于项目模糊相似度的协同过滤推荐算法

传统的项目协同过滤算法忽略了输入数据的模糊性，致使推荐精度较低。已有的模糊协同过滤算法常采用经典的模糊相似度计算策略，导致相似度计算误差较大，且多是从用户角度出发，忽略了项目标签表达的信息，使得推荐效果欠佳。所以，基于项目的模糊协同过滤算法仍需进一步研究。

针对以上问题，本文对协同过滤算法的全过程进行模糊化，构建梯形模糊评分模型和模糊项目标签矩阵，提出一种新的模糊相似度计算策略以提升推荐质量。

# 2.1一种新的梯形模糊评分模型

满意度是判断用户相似度的关键因素。因此，如何更好地描述用户对项目的满意度是协同过滤算法的关键问题之一。针对此问题，本节改进稀疏数据集的评分统计方法，以满意度作为论域，利用梯形隶属度函数将满意度映射到评分中，以使用梯形模糊评分代替原始评分进行相似度计算。

目前的评分系统多为5评分或10评分系统，本节以5评分系统为例，介绍新的梯形模糊评分模型。

梯形模糊评分模型如图2所示，横坐标为满意度，纵坐标为隶属度，范围是[0,1]，纵坐标的值越大，表示满意度对应梯形模糊数的隶属度越大。因为任意满意度都可使用评分进行描述，故在该模型中，任意满意度对应的评分隶属度之和都为1。

![](images/0cbd5d5bc141f0799eb087d4baa72694de31c04b4d4ea2cac1d58d5322d3e20c.jpg)  
图2新的梯形模糊评分模型  
Fig.2New trapezoidal fuzzy scoring model

图2中 $A _ { i }$ 是用户A的第i种梯形模糊评分，i为原始评分， $\mathbf { i } \in \{ 1 , 2 , 3 , 4 , 5 \}$ 。 $A _ { i }$ 对应的满意度置信区间由 $f _ { \ A } ^ { i - 1 }$ 、 $\smash { d _ { \ A } ^ { \ i } }$ 、 $f _ { _ A } ^ { ^ i }$ 三部分 $( \mathrm { i } \in \{ 2 , 3 , 4 \}$ 或者其中两部分 ${ \mathrm { ( i } } \in \{ 1 , 5 \} { \mathrm { ) } }$ 组成。 $\smash { d _ { s } ^ { \prime } }$ 表示 $A _ { i }$ 对应满意度的确定域，在 $\boldsymbol { d } _ { \ A } ^ { \prime }$ 范围内，满意度只映射到一个梯形模糊评分中。 $\boldsymbol { f } _ { \ A } ^ { i - 1 }$ 和 $f _ { \ A } ^ { i }$ 表示 $A _ { i }$ 对应满意度的模糊域，在该范围内，任意满意度都映射到两个相邻的梯形模糊评分中。

根据模糊统计法，用户A的第i种评分出现的概率决定$A _ { i }$ 对应满意度置信区间的大小 $\boldsymbol { r } _ { A } ^ { i }$ ，评分i出现的概率越大说明用户越喜欢使用该评分评价项目，则评分i对应的满意度置信区间越大。 $r _ { A } ^ { i }$ 的定义如式(10)所示。

$$
r _ { A } ^ { i } { = } \frac { n ( { _ { r _ { A } } } { = } i ) } { n ( { _ { r _ { A } } } ) }
$$

其中， $n { \big ( } r _ { A } = i { \big ) }$ 表示用户 $\mathrm { \bf A }$ 的评分中i出现的次数， $n ( \boldsymbol { r } _ { A } )$ 表示用户A的总评分数。

由于数据过度稀疏，故会出现用户未曾使用过某种评分的现象，导致该评分对应的满意度置信区间长度为0。为了避免以上问题，本文使用 $n e w { \big ( } r _ { A } = i { \big ) }$ 和 $n e w ( r _ { A } )$ 改进 $n { \big ( } r _ { A } = i { \big ) }$ 和$n \big ( r _ { A } \big )$ ，以改善数据稀疏性造成的统计误差，具体定义如式(11)和(12)所示。

$$
n e w \big ( r _ { A } = i \big ) = \left\{ \begin{array} { l l } { n ( { r _ { A } } ) ^ { * } t , i f ( n ( { r _ { A } } = i ) < n ( { r _ { A } } ) ^ { * } t ) } \\ { n ( { r _ { A } } = i ) , i f ( n ( { r _ { A } } = i ) \geq n ( { r _ { A } } ) ^ { * } t ) } \end{array} \right.
$$

$$
n e w \big ( r _ { \scriptscriptstyle A } \big ) = \sum _ { i = 1 } ^ { 5 } n e w ( r _ { \scriptscriptstyle A } = i )
$$

式(11)中 $n e w { \big ( } r _ { A } = i { \big ) }$ 表示改进后A用户评分i的出现次数，通过赋值可变参数 $\mathrm { ~  ~ { ~ t ~ } ~ }$ 可以调整评分出现次数的最小值，进而调整评分i对应满意度的最小置信区间长度。式(12)中 $n e w ( r _ { A } )$ 表示改进后用户A的总评分数。

通过以上改进， $r _ { A } ^ { i }$ 的定义如式(13)所示。 $r _ { A } ^ { i }$ 表示用户A的评分i对应的满意度置信区间长度，故 $\textstyle \sum _ { i = 1 } ^ { 5 } r _ { A } ^ { i } = 1$ 。

$$
r _ { \scriptscriptstyle A } ^ { \scriptscriptstyle i } = \frac { n e w ( } { r _ { \scriptscriptstyle A } } = i )  { n e w ( } r _ { \scriptscriptstyle A } )
$$

$r _ { A } ^ { i }$ 表示的满意度置信区间由模糊域和确定域组成，相关定义如式(14)和(15)所示。

$$
\pmb { f } _ { \ A } ^ { i } = 2 * p * \operatorname* { m i n } ( \pmb { r } _ { \ A } ^ { i } , \pmb { r } _ { \ A } ^ { i + 1 } )
$$

$$
\begin{array} { r l } & { \boldsymbol { d } _ { \mathrm { \lambda } } ^ { i } = \left\{ \begin{array} { l } { r _ { \mathrm { \lambda } } ^ { i } - 0 . 5 * f _ { \mathrm { \lambda } } ^ { i } - 0 . 5 * f _ { \mathrm { \lambda } _ { A } } ^ { i - 1 } , i \in \left\{ 2 , 3 , 4 \right\} } \\ { r _ { \mathrm { \lambda } } ^ { i } - 0 . 5 * f _ { \mathrm { \lambda } _ { A } } ^ { i } , i = 1 } \\ { r _ { \mathrm { \lambda } } ^ { i } - 0 . 5 * f _ { \mathrm { \lambda } _ { A } } ^ { i - 1 } , i = 5 } \end{array} \right. } \end{array}
$$

$f _ { _ A } ^ { ^ { \prime } }$ 表示模糊域，位于两个评分对应满意度的交界处，由$\boldsymbol { r } _ { A } ^ { i }$ 和 $\boldsymbol { r } _ { A } ^ { i + 1 }$ 中的最小数与描述模糊程度的参数 $\mathsf { p }$ 确定。从图2可知 $f _ { \mathrm { ~ } _ { A } } ^ { i } \geq 0$ 且 $f _ { \ A } ^ { i } \leq \operatorname* { m i n } ( r _ { A } ^ { i } , r _ { A } ^ { i + 1 } )$ ，所以 $p \in \left[ 0 , 0 . 5 \right]$ 。 $\smash { d _ { \ A } ^ { \ i } }$ 表示确定域，长度由 $r _ { A } ^ { i }$ 与模糊域共同决定，该模型中每种评分对应一个确定域。综上所述，5评分系统的梯形模糊评分模型由4个模糊域、5个确定域构成，若将确定域的长度缩小为一点，则梯形模糊评分模型退化为三角模糊评分模型。

本模型中所有梯形模糊数的1和4顶点的纵坐标值都为0，顶点2、3的纵坐标值都为1，故本模型的梯形模糊数定义如式(16)所示。

$$
A _ { i } = ( a _ { i , 1 } ^ { A } , a _ { i , 2 } ^ { A } , a _ { i , 3 } ^ { A } , a _ { i , 4 } ^ { A } , 1 )
$$

$$
A _ { i } = \left\{ \begin{array} { l l } { \displaystyle ( 0 , 0 , r _ { \lambda } ^ { i } - 0 . 5 ^ { * } f _ { \lambda } ^ { i } , r _ { \lambda } ^ { i } + 0 . 5 ^ { * } f _ { \lambda , 1 } ^ { i } ) , i = 1 } \\ { \displaystyle \left( \frac { i - 1 } { j - 1 } r _ { \lambda } ^ { j } - 0 . 5 ^ { * } f _ { \lambda } ^ { ( i - 1 ) } , \frac { j - 1 } { j - 1 } r _ { \lambda } ^ { j } + 0 . 5 ^ { * } f _ { \lambda } ^ { ( i - 1 ) } , \right) , } \\ { \displaystyle \left( \sum _ { j = 1 } ^ { i } r _ { \lambda } ^ { j } - 0 . 5 ^ { * } f _ { \lambda } ^ { i } , \sum _ { j = 1 } ^ { i } r _ { \lambda } ^ { j } + 0 . 5 ^ { * } f _ { \lambda , 1 } ^ { i } , \right) } \\ { \displaystyle \left( \sum _ { j = 1 } ^ { i } r _ { \lambda } ^ { j } - 0 . 5 ^ { * } f _ { \lambda } ^ { 4 } , \sum _ { j = 1 } ^ { i } r _ { \lambda } ^ { j } + 0 . 5 ^ { * } f _ { \lambda } ^ { 4 } , 1 , 1 , 1 \right) , i = 5 } \end{array} \right.
$$

式(16)中 $a _ { ( i , j ) } ^ { A }$ 表示用户A的评分i第 $\mathrm { ~ j ~ }$ 个顶点的横坐标值，1表示该梯形模糊评分的最大隶属度为1。

结合模糊域与确定域的定义， $A _ { i }$ 的定义如式(17)所示。

# 2.2梯形模糊相似度

协同过滤算法常用的余弦相似度等计算策略不适用于模糊评分的相似度计算，故本小节以梯形模糊相似度为基础，结合评分信息改进梯形模糊评分模型的相似度计算策略[16]。

设两个梯形模糊评分为 $A _ { i }$ 和 $B _ { j }$ ，根据 Ahmad S 的定义，它们的相似度计算如式(18)(19)和(20)所示。

式(18)中，四个因子分别表示几何距离、重心距离、戴斯相似性系数(dice similaritycoefficient，DSC)、豪斯多夫距离(hausdorffdistance,HD)。其中，几何距离度量了两个梯形的横向距离，重心距离度量了梯形重心的横向与纵向距离，且由于重心纵坐标与梯形上下底的长度差距有关，故重心距离也反映了梯形模糊评分中模糊域和确定域的差别，DSC通常根据两个集合的重复比例判断它们的相似性，在式(18)中，AhmadS将DSC引入梯形模糊评分，利用梯形顶点的横坐标判断梯形的相似性，HD将顶点横坐标视为点集以判断梯形模糊评分的最大不匹配程度。

$\textbf { \textit { W } } _ { A _ { i } }$ 和 $\boldsymbol { W } _ { B _ { \ell } }$ 表示梯形模糊评分 $A _ { i }$ 和 $B _ { j }$ 的最大隶属度，本文中设定 $W _ { A _ { i } } { = } W _ { B _ { j } } { = } 1$ 。 $X _ { A }$ 和 $X _ { \ B , \ }$ 分别表示梯形模糊评分 $A _ { i }$ 和$B _ { j }$ 重心的横坐标值。

$$
\begin{array} { c } { { S 1 \Big ( A _ { \prime } B _ { j } \Big ) = \left( 1 - \displaystyle \frac 1 { 4 } \displaystyle \frac { \xi } { k - 1 } \Big | a _ { i , k } ^ { A } - b _ { j , k } ^ { B } \Big | \right) * \left( 1 - \Big | X _ { A _ { i } } - X _ { B _ { j } } \Big | \right) ^ { B \big ( S _ { i , s } , S _ { B _ { i } } \big ) } \times } } \\ { { \left( \displaystyle \frac { 2 W _ { A _ { i } } W _ { B _ { j } } \Big [ \big ( a _ { i , 1 } ^ { A } + a _ { i , 2 } ^ { A } \big ) \big ( b _ { j , 1 } ^ { B _ { 1 } } + b _ { j , 2 } ^ { B _ { 2 } } \big ) + \big ( a _ { i , 3 } ^ { A _ { 3 } } + a _ { i , 4 } ^ { A _ { 3 } } \big ) \big ( b _ { j , 3 } ^ { B _ { 3 } } + b _ { j , 4 } ^ { B _ { 3 } } \big ) \Big ] } { W _ { A } + W _ { B } } \right) \times } } \\ { { \left( \displaystyle \frac 1 { 1 + \Big [ \operatorname* { m a x } \big \{ \Big | a _ { i , 1 } ^ { A } - b _ { j , 1 } ^ { B } \Big | , \Big | a _ { i , 2 } ^ { A } - b _ { j , 2 } ^ { B _ { 2 } } \Big | , \Big | a _ { i , 3 } ^ { A } - b _ { j , 3 } ^ { B _ { 3 } } \big | , \Big | a _ { i , 4 } ^ { A } - b _ { j , 4 } ^ { B _ { 4 } } \Big | \big \} + \Big | W _ { A _ { i } } - W _ { B _ { j } } \Big | \Big ] } \right) } } \end{array}
$$

$$
W _ { \scriptscriptstyle A } = \left( W _ { \scriptscriptstyle A _ { i } } ^ { \mathrm { ~ ~ } ^ { 2 } } \right) \left[ \left( a _ { \scriptscriptstyle i , 1 } ^ { \scriptscriptstyle A } + a _ { \scriptscriptstyle i , 2 } ^ { \scriptscriptstyle A } \right) ^ { 2 } + \left( a _ { \scriptscriptstyle i , 3 } ^ { \scriptscriptstyle A } + a _ { \scriptscriptstyle i , 4 } ^ { \scriptscriptstyle A } \right) ^ { 2 } \right]
$$

$$
W _ { \scriptscriptstyle B } = \left( W _ { \scriptscriptstyle B j } { } ^ { 2 } \right) \left[ \left( b _ { j , 1 } ^ { B } + b _ { j , 2 } ^ { B } \right) ^ { 2 } + \left( \left( b _ { j , 3 } ^ { B } + b _ { j , 4 } ^ { B } \right) ^ { 2 } \right) \right]
$$

为了使上述相似度计算更适用于协同过滤算法的需求以提高预测准确率，本节引入信息量作为权重加入相似度计算中，梯形模糊评分信息量的定义如式(21)所示。

$$
H _ { A } ^ { i } = - r _ { A } ^ { i } { } ^ { * } l o g _ { 2 } r _ { A } ^ { i }
$$

对信息量做归一化处理后，将信息量作为权重改进 $A _ { i }$ 和$B _ { j }$ 的相似度计算，具体公式如式(22)所示。

$$
s ( A _ { i } , B _ { j } ) = S 1 ( A _ { i } , B _ { j } ) ^ { * } H _ { A } ^ { i } { } ^ { * } H _ { B } ^ { j }
$$

综上所述，项目I和J的相似度如式(23)所示。

上式中 $\mathrm { s i m } _ { - } 1 _ { i , j }$ 表示项目i和j的相似度，U表示对项目i和j共同评分的用户集合， $n ( U )$ 表示U的数量，若两个项目未被任何用户同时评分，则认为两个项目的相似度为 $0 , R _ { x , i }$ 表示用户X对项目i的梯形模糊评分， $s \big ( { R _ { x } } , { R _ { x , j } } \big )$ 表示两个梯形模糊评分的相似度。

$$
\begin{array} { r } { \operatorname* { s i m } _ { - } 1 _ { _ { i , j } } = \left\{ \begin{array} { l l } { \sum _ { \boldsymbol { x } \in U } S \big ( { R _ { { \boldsymbol { x } } , i } } , { R _ { { \boldsymbol { x } } , j } } \big ) } \\ { \qquad n ( U ) } \\ { 0 , n ( U ) = 0 } \end{array} , n ( U ) \ne 0 \right. } \end{array}
$$

# 2.3模糊项目标签矩阵

标签作为用户和项目自身携带的数据，可以体现用户、项目的特征，提供标签维度的相似度，缓解评分稀疏性问题。除此之外，标签不受历史数据的制约，可以抑制冷启动问题。所以，引入标签改进协同过滤算法的相似度计算成为学者们研究的热点。但是，传统协同过滤算法认为标签与项目的关系只是属于和不属于，忽略了标签与项目所属关系的模糊性问题，导致预测精度较差。针对以上问题，本节利用模糊隶属度将标签属于项目的隶属度由{0,1}扩展为[0,1]，以此提升推荐质量。

推荐系统中项目包含多个标签。例如，一款手机可能包含品牌、价格、颜色和处理器型号等标签。通过这些标签反映的项目类别和特征，用户可以更高效地筛选数据。大多数推荐系统为了保证标签的专业性，会提供标签集合供项目选择，故项目与标签的关系可以使用项目标签矩阵来表示。

假设拥有k个标签的标签集合为 $T = \left\{ \mathbf { t } _ { 1 } , \mathbf { t } _ { 2 } ^ { \phantom { \dagger } } \cdots \mathbf { \theta } ^ { \dagger } \right\}$ ，其中 $\mathbf { t } _ { \mathrm { i } }$ 表示第i个标签，拥有 $\mathfrak { n }$ 个项目的项目集合为 $I = \{ I _ { 1 } , I _ { 2 } ^ { \phantom { . . . . . } } I _ { \textrm { \em n } } \}$ ，其中 $I _ { \textit { j } }$ 表示第j个项目，则项目标签矩阵可以被表示为 $\mathbf { n } ^ { * } \mathbf { k }$ 阶的矩阵 $\boldsymbol { M } _ { \scriptscriptstyle n , k }$ 。表1展示了包含6个项目和5个标签的项目标签矩阵，其中 $m _ { i , j } = 1$ 表示第 $\mathrm { j }$ 个标签属于第i个项目， $m _ { i , j } = 0$ 表示不属于。

表1项目标签矩阵  
Tab.1Item label matrix   
表2模糊项目标签矩阵  

<html><body><table><tr><td>mi.j</td><td>t</td><td>t</td><td>t</td><td>t4</td><td>t5</td></tr><tr><td></td><td>1</td><td>0</td><td>1</td><td>1</td><td>0</td></tr><tr><td>I</td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td></tr><tr><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td></tr><tr><td>I4</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>1</td><td>1</td><td>1</td><td>1</td><td>0</td><td>1</td></tr><tr><td>1</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

项目上传者和用户在分配标签时，需要根据项目内容判断标签是否属于项目，但是如何判断项目内容和标签的所属关系是一个难点。例如是否包含武打场面的电影就是功夫片，包含多少科幻元素的电影可以被定义为科幻片。所以，项目标签的隶属度存在模糊性问题，即标签与项目之间的隶属关系不应该只是属于和不属于的非此即彼关系，而应区分不同标签属于项目的程度。

项目上传者或用户对标签的使用阈值越低，则其操作的项目拥有的标签数量 $N u m _ { i }$ 越多，因而 $N u m _ { i }$ 与标签属于项目的隶属度 $N P _ { i , j }$ 成反比。同样的，从标签角度出发，标签出现次数 $C o u n t _ { i }$ 与 $N P _ { i , j }$ 也成反比。此外，从信息量的角度来看，利用标签计算相似度时，由于标签包含信息量的不同，故不同标签对相似度的贡献存在差异，当标签在所有项目中出现次数越多，则表示该标签包含的信息量越少，在计算基于标签的项目相似度时应该弱化该标签的影响权重。综上所述，本章算法将 $N u m _ { i }$ 与 $C o u n t _ { i }$ 融合在 $N P _ { i , j }$ 中。隶属度函数的定义如式(24)所示。

$$
{ N P } _ { i , j } \mathrm { { = } } \left\{ \overline { { N u { m _ { i } } ^ { * } C o u n t _ { i } } } ^ { , } { P } _ { i , j } \mathrm { { \neq } 0 } \right.
$$

以表1所示的项目标签矩阵为例，通过式(24)计算项目标签隶属度 $N P _ { i , j }$ 得到的模糊项目标签矩阵如表2所示。

Tab.2Fuzzy item label matrix   

<html><body><table><tr><td>NPi.</td><td>t</td><td>t</td><td>t</td><td>t4</td><td>t5</td></tr><tr><td>1</td><td>0.111</td><td>0</td><td>0.167</td><td>0.333</td><td>0</td></tr><tr><td>I</td><td>0</td><td>0.125</td><td>0</td><td>0</td><td>0.167</td></tr><tr><td>I</td><td>0</td><td>0.125</td><td>0</td><td>0</td><td>0.167</td></tr><tr><td>I4</td><td>0.333</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>I</td><td>0.083</td><td>0.063</td><td>0.125</td><td>0</td><td>0.083</td></tr><tr><td>1</td><td>0</td><td>0.25</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

为了方便后续处理，将 $N P _ { i , j }$ 按照式(25)进行归一化，其中$M A X \left( N P \right)$ 表示NP中最大的数值。

$$
N P _ { i , j } { = } \frac { N P _ { i , j } } { M A X \left( N P \right) }
$$

# 2.4标签隶属度的相似度

构建模糊项目标签矩阵后，将每个项目的标签隶属度视作 $\mathfrak { n }$ 维向量，通过余弦相似度计算项目相似度，计算公式如式(26)所示。

$$
{ \sin } _ { - } 2 _ { _ { A , B } } { = } \frac { \displaystyle \sum _ { t \in { T _ { A } } \cap { T _ { B } } } N P _ { { A } , t } { * } N P _ { { B } , t } } { \displaystyle \sqrt { \sum _ { t \in { T _ { A } } } \left( N P _ { { A } , t } \right) ^ { 2 } } * \sqrt { \sum _ { t \in { T _ { B } } } \left( N P _ { { B } , t } \right) ^ { 2 } } }
$$

# 2.5项目相似度计算

将基于标签隶属度的相似度 $s i m _ { - } 2 _ { { \scriptscriptstyle i , j } }$ 和基于模糊评分的相似度 $\mathrm { s i m } _ { - } 1 _ { i , j }$ 加权融合成项目相似度 $s i m \_ i t e m _ { { \scriptscriptstyle i } , j }$ ，具体的定义如式(27)所示。 $\lambda$ 表示融合系数， $\lambda \in \left[ 0 , 1 \right]$ 0

$$
s i m \_ i t e m _ { \scriptscriptstyle i , j } = \ r { i \ r { e m } } _ { \scriptscriptstyle - } \ r { i \ r { s i m \_ } } \ r { s i m \_ } \ r { 1 } _ { \scriptscriptstyle i , j } \ r { s i \ r { s i m \_ } } \ r { 2 } _ { \scriptscriptstyle i , j }
$$

# 2.6模糊评分预测策略

传统协同过滤的评分预测策略只适用于原始评分，本小节改进该策略以适用于梯形模糊评分模型，具体步骤如下：

a)利用模糊相似度预测用户A对项目i的模糊评分。具体方法如式(28)所示。

$$
P _ { _ { A , i } } = \frac { \underset { j \in N _ { i } } { \sum _ { j \in N _ { i } } } s i m \_ i t e m _ { _ { i , j } } { * _ { A } } _ { j } } { \underset { j \in N _ { i } } { \sum _ { j \in N _ { i } } } \Bigl | s i m \_ i t e m _ { _ { i , j } } \Bigr | }
$$

其中， ${ N } _ { i }$ 表示项目i的邻域集合， $A _ { j }$ 表示用户A对项目j的梯形模糊评分数， $\boldsymbol { P } _ { \lambda , i }$ 表示预测的梯形模糊评分数。

# b）寻找最相似的模糊评分

在经典协同过滤中，评分通常用整数表示，故需要将预测的评分四舍五入为整数。例如预测评分4.3将四舍五入为评分4，在此处四舍五入的本质是为小数评分寻找最相似的整数评分。本文使用梯形模糊相似度求 $P _ { \ A , i }$ 与用户各梯形模糊评分的相似度，为 $\tilde { P } _ { A , i }$ 寻找最相似的梯形模糊评分。

c）去模糊化

将相似度最大的梯形模糊评分 $\scriptstyle A _ { k }$ 对应的原始评分 $\mathbf { k }$ 赋值给预测的梯形模糊评分。

$$
P _ { _ { A , i } } { } _ { = } k , i f S _ { _ k } { } = \operatorname* { m a x } \left( S _ { ^ { , } } S _ { ^ { , } } S _ { ^ { , } } S _ { ^ { , } } S _ { ^ { , } } S _ { ^ { , } } S _ { ^ { , } } \right)
$$

# 2.7算法描述

本文提出了一种基于项目模糊相似度的协同过滤推荐算法，利用项目标签隶属度和梯形模糊评分确定项目的相似度，并完成推荐。

算法的具体描述如下所示。

输入：用户项目评分矩阵R、项目标签矩阵M、目标用户 $\mu$ 、目标项目j、邻居数量 $k _ { i }$   
输出：目标用户对目标项目的预测评分。  
根据式(11)和(12)计算 $n e w { \bigl ( } r _ { \mathrm { \scriptscriptstyle A } } { = } i { \bigr ) }$ 和 $n e w ( r _ { A } )$ #  
a）设置参数t和p构建梯形模糊评分模型；  
b）根据式(23)计算基于模糊评分的相似度；  
c）使用式(24)构建模糊项目标签矩阵；  
d）利用式(26)计算基于标签隶属度的相似度;  
e）设置参数入；  
f）根据式(27)计算项目相似度；  
g）利用式(28)预测模糊评分；  
h）使用式(29)对模糊评分去模糊化。

# 3 实验结果及分析

本节首先介绍实验使用的数据集，然后给出评价指标，说明对比算法和实验环境，最后分析了实验结果。

# 3.1实验数据集

这里采用GroupLens收集的MovieLens100K和1M数据集，该数据集是验证推荐算法使用最广泛的数据集之一。数据集的相关信息如表3所示。

表3实验数据集  
Tab.3Datasets used in experiments   

<html><body><table><tr><td>数据集</td><td>用户数</td><td>项目数</td><td>评分数</td><td>稀疏度</td></tr><tr><td>100K</td><td>943</td><td>1682</td><td>100000</td><td>93.7%</td></tr><tr><td>1M</td><td>6040</td><td>3952</td><td>1000000</td><td>95.81%</td></tr></table></body></html>

# 3.2评价指标

本文采用推荐系统中常用的评价指标平均绝对误差(meanabsoluteerror，MAE)判断算法的有效性，MAE表示预测评分与真实评分差异的平均值，MAE越大表明预测误差越大，反之表明预测精度越高，具体定义如式(30)所示。

$$
\mathit { M A E } { = } \frac { \displaystyle \sum _ { u , i \in T } \left| P _ { u , i } - R _ { u , i } \right| } { \displaystyle | T | }
$$

T表示测试集，T表示测试集的数量， $\boldsymbol { P } _ { u , i }$ 表示用户 $\boldsymbol { u }$ 对项目 $i$ 的预测评分值， $\scriptstyle R _ { u , i }$ 表示用户 $\boldsymbol { u }$ 对项目 $i$ 的真实评分值。MAE值越小，推荐结果的精度越高。

# 3.3对比实验

为了验证本文算法IFSCF的有效性，对比算法有文献[13]提出的基于用户模糊相似度的协同过滤算法FUBCF-1、文献[14]提出的改进的基于用户模糊相似度的协同过滤算法FUBCF-2、文献[11]提出的模糊协同过滤算法FCF、文献[17]提出的基于模糊偏差值权重的协同过滤算法FPCF、文献[18]提出的基于模糊权重的协同过滤算法CORFR。

# 3.4实验环境

Inter(R) Core(TM) i5-9300 CPU @2.40GHz,8.0GB 内存,512GB SSD，Windows10 64 位操作系统，MatlabR2016a。

# 3.5 实验结果及分析

为了更清晰地表达各参数对本算法性能的影响，本节首先使用基于模糊评分的项目相似度FRIS作为项目相似度，分析参数t和p对IFSCF(FRIS)算法的影响，然后调整参数入，将基于模糊评分的项目相似度与基于标签隶属度的项目相似度加权融合，最终比较IFSCF算法和对比算法在不同数据集和稀疏度中的性能差异，分析本文算法的特点。

最小满意度置信区间参数t决定了评分对应满意度的最小区间长度，在5评分系统的推荐系统中， $\mathfrak { t } \in [ 0 , 0 . 2 ]$ 。为了验证参数t对预测精度的影响，控制IFSCF(FRIS)算法的其他变量固定，设步长为0.02进行实验，实验结果如图3所示。

![](images/7395c2e28ffac8685acb60b4accab76987cdf0862fd2a29ea94d827569ea2654.jpg)  
图3参数t对MAE值的影响

由图可知，在100K数据集中，随着t的增大，MAE值先急速下降再缓慢回升，当 $\mathfrak { t } \in ( 0 . 0 6 , 0 . 1 4 )$ 时MAE值稳定于0.7左右，当 $\scriptstyle \mathrm { t = } 0 . 1$ 时，MAE值最小， $_ { \mathrm { t > 0 . 1 4 } }$ 时，MAE值逐渐变大。在1M数据集中，MAE值的趋势与100K数据集类似，MAE值在 $\scriptstyle \mathrm { t = 0 } . 1 2$ 处到达最小，当 ${ \mathrm { t } } { > } 0 . 1 6$ 时出现回升现象。

MAE值出现以上趋势的原因是评分数据过于稀疏导致评分出现概率与事实差异较大，改进前的 $r _ { A } ^ { i }$ 无法较精确地描述最小满意度置信区间长度，因此t较小时MAE值较大。当$0 . 0 6 { < } \mathrm { t } { < } 0 . 1 6$ 时，改进后的 $r _ { A } ^ { i }$ 接近真实评分对应的满意度置信区间长度，MAE值来到最小处。当t逐渐趋近于0.2时，评分之间失去了差异性，引起MAE值上升。通过以上实验和分析，固定t的取值为0.1。

模糊域参数p表示模糊程度，决定了满意度置信区间中模糊域的占比， $\mathfrak { p } \in [ 0 , 0 . 5 ]$ 。若 $\scriptstyle \mathbf { p = } 0$ 则表示未使用模糊域，故模糊评分退化为原始评分，若 $\mathtt { p } { = } 0 . 5$ 则表示满意度全是模糊域，没有确定域。为了验证 $\mathfrak { p }$ 对实验结果的影响，在控制其他变量固定的情况下，设步长为0.05对IFSCF(FRIS)算法进行实验，实验结果如图4所示。

![](images/2495eba95533e9c846dd6d5e4875ceb8cbc654d5d6febd1edc8fa1793535e42e.jpg)  
Fig.3Effect of parameter ton MAE  
图4参数p对MAE值的影响Fig.4Effect of parameter p on MAE

观察实验结果可知，在100K数据集中，随着p的增大，MAE值先变小再增大，当 $\scriptstyle { \mathtt { p } } = 0 . 1 5$ 时，MAE值最小。在1M数据集中，MAE的趋势与100K数据集类似，MAE值在$\scriptstyle \mathtt { p } = 0 . 2$ 处到达最小值。

当p过小或过大时，评分预测的效果都不理想，这是因为当模糊域过大或者过小时，都无法较好地描述梯形模糊评分对应的满意度置信区间。由MAE值的最低点可知，模糊域的范围略小于确定域时效果最好。通过对比 $\mathtt { p } { = } 0 . 5$ 和 $\scriptstyle \mathbf { p = } 0$ 可知，全是模糊域的满意度比全是确定域的满意度推荐质量更佳，表明了引入模糊理论构建模糊域的有效性。通过以上实验和分析，后续的实验固定p的取值为0.15。

融合参数λ是基于模糊评分的相似度sim_1和基于标签的相似度sim_2的融合权重。为了验证参数λ对IFSCF算法性能的影响，控制近邻项目数量不变，设步长为0.1进行实验，实验结果如图5所示。

![](images/cad5c38a526e3d6caf98f8382b377f37905d85c2b0c0f69ac7bac93acf402cca.jpg)  
图5参数 $\lambda$ 对MAE值的影响

由图可知，在100K数据集中，当 $\lambda \in \left[ 0 , 0 . 2 \right]$ 时，随着 $\lambda$ 的增大，预测误差稳步下降并在 $\scriptstyle \lambda = 0 . 2$ 处到达最低点，MAE值略低于0.7。当 $\lambda \in [ 0 . 2 , 1 ]$ 时，随着 $\lambda$ 的增大，预测误差逐渐上升。数据集为1M时，MAE的趋势与前者类似，当 $\scriptstyle \lambda = 0 . 3$ 时MAE值低于 $0 . 6 8$ 。 $\scriptstyle \lambda = 0$ 和 $\scriptstyle \lambda = 1$ 处的数据显示基于标签的相似度计算的评分预测精度略逊于基于模糊评分的相似度计算，这是由于前者主要负责改善项目冷启动，提高算法在稀疏数据中的效果，而后者负责提升预测精度和推荐多样性。通过以上分析，λ的值取为0.2。

以邻居数量为变量，取步长为5，比较IFSCF算法与对比算法的预测精度，实验结果如表4和5所示，N表示近邻数量。

Tab.4MAE with different neighbors(ML-100K)   

<html><body><table><tr><td>N</td><td>FUBCF_1</td><td>FUBCF_2</td><td>FCF</td><td>FPCF</td><td>CORFR</td><td>IFSCF_FRIS</td><td>IFSCF</td></tr><tr><td>5</td><td>0.779</td><td>0.758</td><td>0.815</td><td>0.802</td><td>0.797</td><td>0.746</td><td>0.745</td></tr><tr><td>10</td><td>0.770</td><td>0.734</td><td>0.788</td><td>0.781</td><td>0.774</td><td>0.725</td><td>0.718</td></tr><tr><td>15</td><td>0.754</td><td>0.731</td><td>0.775</td><td>0.771</td><td>0.751</td><td>0.715</td><td>0.709</td></tr><tr><td>20</td><td>0.744</td><td>0.727</td><td>0.768</td><td>0.762</td><td>0.731</td><td>0.711</td><td>0.706</td></tr><tr><td>25</td><td>0.740</td><td>0.726</td><td>0.762</td><td>0.756</td><td>0.728</td><td>0.709</td><td>0.704</td></tr><tr><td>30</td><td>0.742</td><td>0.726</td><td>0.760</td><td>0.753</td><td>0.722</td><td>0.706</td><td>0.702</td></tr><tr><td>35</td><td>0.739</td><td>0.725</td><td>0.757</td><td>0.752</td><td>0.721</td><td>0.704</td><td>0.701</td></tr><tr><td>40</td><td>0.738</td><td>0.725</td><td>0.752</td><td>0.750</td><td>0.718</td><td>0.703</td><td>0.700</td></tr><tr><td>45</td><td>0.737</td><td>0.726</td><td>0.752</td><td>0.749</td><td>0.717</td><td>0.703</td><td>0.700</td></tr><tr><td>50</td><td>0.737</td><td>0.729</td><td>0.75</td><td>0.749</td><td>0.715</td><td>0.702</td><td>0.699</td></tr></table></body></html>

表51M数据集中各算法MAE值的比较

表4100K数据集中各算法MAE值的比较  
Tab.5MAE with different neighbors(ML-1M)   

<html><body><table><tr><td>N</td><td>FUBCF_1</td><td>FUBCF_2</td><td>FCF</td><td>FPCF</td><td>CORFR</td><td>IFSCF_FRIS</td><td>IFSCF</td></tr><tr><td>5</td><td>0.765</td><td>0.740</td><td>0.801</td><td>0.783</td><td>0.803</td><td>0.731</td><td>0.745</td></tr><tr><td>10</td><td>0.758</td><td>0.721</td><td>0.772</td><td>0.763</td><td>0.775</td><td>0.706</td><td>0.709</td></tr><tr><td>15</td><td>0.739</td><td>0.714</td><td>0.760</td><td>0.755</td><td>0.741</td><td>0.699</td><td>0.701</td></tr><tr><td>20</td><td>0.733</td><td>0.711</td><td>0.748</td><td>0.751</td><td>0.725</td><td>0.695</td><td>0.693</td></tr><tr><td>25</td><td>0.730</td><td>0.709</td><td>0.745</td><td>0.745</td><td>0.721</td><td>0.691</td><td>0.690</td></tr><tr><td>30</td><td>0.728</td><td>0.705</td><td>0.745</td><td>0.740</td><td>0.719</td><td>0.689</td><td>0.686</td></tr><tr><td>35</td><td>0.725</td><td>0.705</td><td>0.741</td><td>0.736</td><td>0.716</td><td>0.687</td><td>0.683</td></tr><tr><td>40</td><td>0.721</td><td>0.703</td><td>0.742</td><td>0.733</td><td>0.712</td><td>0.686</td><td>0.682</td></tr><tr><td>45</td><td>0.720</td><td>0.702</td><td>0.741</td><td>0.732</td><td>0.711</td><td>0.685</td><td>0.682</td></tr><tr><td>50</td><td>0.719</td><td>0.702</td><td>0.740</td><td>0.731</td><td>0.711</td><td>0.685</td><td>0.681</td></tr></table></body></html>

由表可知，在100K数据集中，任意邻域数量下IFSCF算法的精度皆高于对比算法，在1M数据集中，当邻域数量较小时，IFSCF 算法的误差大于FUBCF-2和IFSCF(FRIS)算法，但当邻域数量扩大后，IFSCF算法的误差逐渐变为最小。

IFSCF算法引入了标签模糊隶属度，理论上可以更好地应对评分稀疏性问题。为了验证以上推测，本实验使用100K数据集，在保证用户数和项目数不变的前提下，逐步减少数据集中的评分数量，将数据集的稀疏度从0.937逐渐提升到0.99，比较IFSCF算法与对比算法在不同稀疏度中的表现。实验结果如图6所示。

![](images/aaf2ad271d5b83600fda70bc5b9eed0d9aeba2dbb7cf0523fcfad8b443d52faa.jpg)  
Fig.5Effect of parameter  on MAE   
图6不同稀疏度下各算法MAE的比较  
Fig.6MAE with different sparsity

从实验结果可知，随着稀疏度的增大，可使用的数据逐渐减少，各算法的MAE值都不同程度地增大，并且在稀疏度大于 $9 7 \%$ 后增速变快。其中，IFSCF算法的MAE值增幅较小，预测精度最高，可在稀疏数据中较好地完成推荐。

# 4 结束语

本文引入模糊理论改善了评分-满意度和项目-标签的模糊性问题，提出了一种基于项目模糊相似度的协同过滤推荐算法，利用梯形模糊数描述评分与满意度的映射关系，改进模糊相似度计算策略以提升相似度计算的精度，使用隶属度函数判断标签与项目的所属程度，根据项目标签隶属度向量计算基于标签的相似度，改进评分预测策略以进行模糊评分估计，对基于项目的协同过滤算法全过程实施了模糊处理。实验结果表明，该算法可在一定程度上缓解模糊性问题并可改善评分数据稀疏性带来的不利影响。

# 参考文献：

[1]魏甜甜，陈莉，范婷婷，等．结合项目流行度加权的协同过滤推荐算 法[J].计算机应用研究,2020,37(3):676-679.(Wei Tiantian,ChenLi, Fan Tingting,et al.Collaborative filtering recommendation algorithm based on item popularity weighting [J].Application Research of Computers,2020,37(3):676-679.)   
[2]Ekstrand M D.Collaborative filtering recommender systems [J].Acm Transactions on Information Systems,2007,22(1):5-53.   
[3]Wei Jian,He Jianhua, Chen Kai,et al.Collaborative filtering and deep learning based recommendation system for cold start items [J].Expert Systems With Applications,2017,69 (69):29-39.   
[4]Hu Yan,Shi Weisong,Li Hong,et al. Mitigating data sparsity using similarity reinforcement-enhanced collaborative filtering [J].Acm Transactions on Internet Technology,2017,17 (3):1-20.   
[5]Yera R,Martinez L.Fuzzy tools in recommender systems: a survey [J]. International Journal of Computational Intelligence Systems,2017,10 (1): 776-803.   
[6]Kant S,Mahara T,Jain VK,et al.Fuzzy logic based similarity measure for multimedia contents recommendation [J].Multimedia Tools and Applications,2019,78(4):4107-4130.   
[7]Berkani L.Social-Based collaborative recommendation:bees swarm optimization based clustering approach [C]//International Conference on Model and Data Engineering. Springer,Cham,2019:156-171.   
[8]Tsai C H.A fuzzy-based personalized recommender system for local businesses [C]//Proceedings of the 27th ACM Conference on Hypertext and Social Media.ACM,2016:297-302.   
[9]Vashisth P,Khurana P,Bedi P.A fuzzy hybrid recommender system [J]. Journal of Intelligent& Fuzzy Systems,2017,32 (06):3945-3960.   
[10] Wasid M,Kant V.A particle swarm approach to collaborative filtering based recommender systems through fuzzy features [J].Procedia Computer Science,2015,54 (06): 440-448.   
[11]Kant V,Bharadwaj KK.Enhancing recommendation quality of contentbased filtering through collaborative predictions and fuzzy similarity measures [J].Procedia engineering,2012,38 (3):939-944.   
[12] Zhang Xixiang,Ma Weimin,Chen Liping.New similarity of triangular fuzzy number and its application [J].The Scientific World Journal,2014, 2014 (1): 1-7.   
[13]吴毅涛，张兴明，王兴茂，等．基于用户模糊相似度的协同过滤算法 [J]．通信学报，2016,37(1):198-206.(Wu Yitao,Zhang Xingming, Wang Xingmao,et al.User fuzzy similarity-based collaborative filtering recommendation algorithm[J].Journal on Communications.2016,37(1): 198-206.)   
[14]Wu Yitao,Zhang Xingming,Hong Yyu,et al.Collaborative filtering recommendation algorithm based on user fuzzy similarity [J].Intelligent Data Analysis,2017,21 (2):311-327.   
[15]L.A. Zadeh.Fuzzy Sets[J].Information & Control,1965,8(3):338-353.   
[16] Ahmad SA S,Mohamad D,Sulaiman NH,et al.A distance and set theoretic-based similarity measure for generalized trapezoidal fuzzy numbers [C]//AIP Conference Proceedings.AIP Publishing LLC,2018, 1974 (1): 02-43.   
[17]Al-Shamri MYH,Al-Ashwal NH.Fuzzy-weighted similarity measures for memory-based collaborative recommender systems [J].Journal of Intellgent Learning Systems and Applications,2014,6 (O1):1-10.   
[18]Lee S.Collaborative filtering using fuzzy rank-based similarity measures [C]// 2018 International Conference on Control,Artificial Intelligence, Robotics& Optimization(ICCAIRO) .IEEE,2018:84-89.