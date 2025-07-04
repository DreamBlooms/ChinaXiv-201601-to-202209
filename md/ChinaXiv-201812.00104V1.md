# 基于混合互信息算法的文本情感分析

王义，戴月明

(江南大学 物联网工程学院，江苏 无锡 214122)

摘要：针对互信息（mutual information，MI）特征选择方法存在的正负相关性的现象以及未考虑特征项在不同类别内词频的问题，提出了一种混合互信息特征选择算法（hybrid mutual information,HMI)。该算法引入逆文档频率系数和类间词频信息系数，使得整个文档中的词频信息以及每个类之间的词频信息得以有效利用；引入正负相关性系数，区分正相关性和负相关性，并进行有效的利用。通过实验对比表明，混合互信息算法可以有效地提高特征选择的质量，进而提高文本情感分析的效果。

关键词：互信息；特征选择；正负相关性；词频信息；情感分析中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2018.08.0537

# Text sentiment analysis based on hybrid mutual information algorithm

Wang Yi, Dai Yueming (School of Internet of Things Engineering,Jiangnan University,Wuxi Jiangsu 214122, China)

Abstract: Aiming at the phenomenon of positive and negativecorrelation in the feature selection methodof mutual information (MI)and theproblem of not considering the word frequencyofthe feature items in different categories,a hybrid mutual information feature selection algorithm (HMI) is proposed.By introducing the inverse document frequency coefcientand the inter-classword frequency informationcoeficient,the algorithmcan effectively utilizethe word frequency information in the whole document and the word frequency information between each class.The positive and negative correlationcoeffcient is introduced todistinguish positivecorrelation and negativecorrelation and to make efective use.The experimental resultsshowthat the hybrid mutual information algorithmcan effctively improve the quality of feature selection and then improve the effect of text emotional analysis.

Key words: mutual information;featureselection;positiveand negativecorelation; word frequencyinformation;sentimen classification

# 0 引言

随着科技的不断发展，互联网的普及越来越高，对于数据分析的需求也日益增长，一些关于商品以及服务的评论越来越多。因此，从这些评论以及评价中对其观点进行情感分析成为了当下热门研究方向[1。文本情感分析是分析文本的情感倾向，并在文本中挖掘作者的观点、态度等有效信息[2],因此文本情感分析也被称为文本观点挖掘。目前，基于情感词典以及基于机器学习是文本情感分析的两种主要方法，而基于机器学习的方法是当前情感分类的主流方法[3]。在文本情感分析中，文本数据一般被表示为空间向量模型（VSM)[4]，借助此模型，可以将文本数据转换成为结构化数据，以便计算机能够对其进行处理。在一般的数据集中，特征项通常会达到上万个特征，稍大的数据集，甚至会达到上百万个特征，因此如何在降低特征空间的维度的同时，提高文本情感分类的效果，就成为文本情感分析中的关键问题[5]。特征选择自然也就成为文本情感分析中的一个重要部分。

特征选择的主要目的就是为了通过去除噪声[6，选择出高质量，具有代表性的词汇，从而提高分类的准确率。目前，常见的特征选择方法包括：卡方统计量（Chi-square statistic，CHI）、文档频数（document frequency，DF）、信息增益(information gain，IG）、互信息（mutual information，MI)

等。在这些特征选择算法中，互信息以其时间复杂度低,易于理解以及使用便捷等优点，成为了一种重要的特征选择方法[7]。但是，传统互信息算法因为其没考虑词频因素，导致选取的特征词的质量较低[8]；另外，在计算特征项的互信息值时，忽略了呈负相关性的特征项，导致负相关性的特征值会明显削弱总体的特征值，从而降低了互信息算法的精确性。

综上所述，针对互信息算法在特征选择时的不足，本文引入了逆文档频率系数，类间频率系数以及正负相关性系数，提出一种混合互信息（hybridmutual information，HMI）特征选择方法。通过理论分析以及实验证明，该算法能有效地利用词频信息以及正负相关性信息提高特征选择的质量，从而提高情感分类的精确度。

# 1 互信息特征选择方法

互信息（MI）是一种基于统计学的算法，一般用来度量两个统计量之间的相互关联程度[9。而在文本情感分析中，互信息算法一般被用来计算文本中的特征项与各个类别之间的关联程度。当特征项与该类别的关联程度越大时，该特征项与该类的互信息值就越大，则说明该特征项对于该类就越具有代表性[9]。记 $t _ { k }$ 为特征项的集合， $k { = } 1 , 2 , . . . , m$ ： $c _ { j }$ 为训练集类别的集合， $j { = } 1 , 2 , . . . , r$ ；则 $t _ { k }$ 与 $c _ { j }$ 之间的互信息值的计算公式如下：

$$
M I ( t _ { k } , c _ { j } ) = \log \frac { p ( t _ { k } , c _ { j } ) } { p ( t _ { k } ) p ( c _ { j } ) } = \log \frac { p ( t _ { k } | c _ { j } ) } { p ( t _ { k } ) }
$$

其中 $: p ( t _ { k } , c _ { j } )$ 表示训练集中既包含特征 $t _ { k }$ 又属于类别的文本 $c _ { j }$ 概率， $p ( t _ { k } )$ 表示在整个文本训练集中包含特征 $t _ { k }$ 的文本概率,$p ( c _ { j } )$ 表示文本属于训练集中类别 $\mathbf { c _ { j } }$ 的文本概率, $p ( t _ { k } \vert c _ { j } )$ 表示类别 $c _ { j }$ 中，包含特征 $t _ { k }$ 的文本概率。对于多个类别的训练集，特征项 $t _ { k }$ 与训练集中各个类别的互信息计算公式如下所示：

$$
M I ( t _ { k } ) = \sum _ { j = 1 } ^ { r } p ( c _ { j } ) \log \frac { p ( t _ { k } , c _ { j } ) } { p ( t _ { k } ) p ( c _ { j } ) } =
$$

$$
\sum _ { j = 1 } ^ { r } p ( c _ { j } ) \log \frac { p ( t _ { k } | c _ { j } ) } { p ( t _ { k } ) }
$$

当特征选择时， $M I ( t _ { k } )$ 的互信息值按照从大到小排序，根据维度的选取需求，选取其中较大的前 $n$ 项值所对应的特征项进行文本的向量的表示。

互信息算法计算的是包含特征项 $t _ { k }$ 的文本数量与训练集中每个类别 $c _ { j }$ 中文本数量的之比，最重要的特征就是考虑了不同特征项和这一类别的同现频率，有效地利用了文本的类别信息[10]。但是互信息方法也存在着一些明显的不足之处，例如在式（2）中，各个特征项在不同类别之间的频数的差异并没有体现出来，也没有考虑包含特征项文本训练集频数之间的联系。在文本情感分析中，特征项与各个类别之间的相关性分为正相关性和负相关性，正相关的特征项在文本情感分类中起主要的作用[I]，但负相关特征对于最终的文本情感分类结果也有着重要的作用。从式（2）中可以看出，正负相关性的互信息值相互抵消了，从而忽略了负相关性的作用。

# 2 混合互信息特征选择方法

# 2.1类间词频信息系数

通过以上分析，在传统的互信息特征选择方法中，只考虑了类内特征项的频率[12]，但是特征项的词频数在文本情感分析中的作用不仅仅体现在类内，它也在类和类之间起着非常重要的作用。如果一个特征项对于某一类的代表能力越强，那么该特征项应当集中在某一类中，也就是在这一类中该特征项的词频应当较大，相反在其他类中应当尽量少的出现。假定特征项 $t _ { k }$ 为类别 $c _ { j }$ 的特征项，那么在特征项 $\mathfrak { t } _ { \mathrm { k } }$ 在类别 $c _ { j }$ 中应尽可能多的出现，而在其他类别 $c _ { q } ( q { \neq } j )$ 中应尽可能的少出现。那么在理论推导中，对于类别代表能力较强的特征项，在不同类别之间的标准差应当尽可能大。基于以上考虑，本文在式（2）的基础之上，引入类间词频信息系数 $\scriptstyle a$ ，则 $\scriptstyle a$ 的定义形式所示为

$$
\alpha = \sqrt { \frac { 1 } { m } \sum _ { j = 1 } ^ { m } \biggl [ t f _ { j } ( t _ { k } ) - \frac { 1 } { m } \sum _ { i = 1 } ^ { m } t f _ { i } ( t _ { k } ) \biggr ] ^ { 2 } }
$$

其中 $: t f _ { j } ( t _ { k } )$ 表示为特征 $t _ { k }$ 在类别 $j$ 中出现的频数， $\mathbf { \nabla } m$ 表示为类别的总数。那么，式（2）则可以写成

$$
M I ( t _ { k } ) = \alpha \times \sum _ { j = 1 } ^ { r } p ( c _ { j } ) \log \frac { p ( t _ { k } \mid c _ { j } ) } { p ( t _ { k } ) }
$$

式（4）中，在互信息方法中引入类间词频信息系数 $\scriptstyle a$ 系数 $\alpha$ 统计了特征项在每一类间的词频的标准差，使得特征项的词频信息在不同类别中得以体现，提高了互信息特征选择方法的效率。因此，该式进一步提高了文本情感分类的效果。

# 2.2逆文档频率系数

上文通过引入类间词频信息系数 $\scriptstyle a$ ，了解到当一个特征项集中出现在某一类的文本中时，则它对文本类别的代表能力就越强。在传统的互信息方法中，还忽略了出现特征项的文档频率，例如"他”“你”“是”这样的词在很多文本中都有可 $\overset { \cdot } { \mathbf { a } }$ 能会出现，然而这类词对于文本的区别能力并不高[13]。因此，如果一个特征项出现在大多数的文本中，那么意味着这个特征项对于文本类别的区分能力就越弱。基于以上所述，为了对此类特征项进行区分，增加特征项的区分力，引入逆文档系数 $\beta$ ，来调节这类问题。 $\beta$ 的定义形式如下所示：

$$
\beta { = } \ln \frac { \mathrm { ~ N ~ } } { f ( t _ { k } ) + 0 . 0 1 }
$$

那么，可以将式（4）写成

$$
M I ( t _ { k } ) = \alpha \times \sum _ { j = 1 } ^ { r } \beta \times p ( c _ { j } ) \log \frac { p ( t _ { k } \mid c _ { j } ) } { p ( t _ { k } ) }
$$

其中， $N$ 代表训练集中的文档总数， $f ( t _ { k } )$ 代表包含特征项 $t _ { k }$ 的文本数量，分母后加上小数0.01确保分母不为0，以保证系数的有效性。在式（5）中，由于 $N { \geq } f ( t _ { k } )$ 恒成立，当存在更多包含特征项 $t _ { k }$ 的文本时，也就是 $f ( t _ { k } )$ 越大时， $f ( t _ { k } )$ 越接近 $N$ 系数 $\beta$ 越接近0，那么，逆文档系数 $\beta$ 值对于该特征项的MI值的影响就越小。通过引入逆文档频率系数，降低了一些常用词作为特征项对于最后分类结果的影响，提高了特征选择的效率。

# 2.3 正负相关性系数

由式（1）可以看出，在计算特征项 $t _ { k }$ 和类别 $c _ { j }$ 的互信息值时，当 $p ( t _ { k } \vert c _ { j } )$ 大于 $p ( t _ { k } )$ ，此时 $M I ( t _ { k } ) { > } 0$ ，这表明特征项$t _ { k }$ 和类别 $c _ { j }$ 是正相关的。说明当 $p ( t _ { k } \vert c _ { j } )$ 的值越大，而 $p ( t _ { k } )$ 的值越小时，特征项 $t _ { k }$ 所能代表类别 $c _ { j }$ 的能力就越强。而当$p ( t _ { k } \vert c _ { j } )$ 小于 $p ( t _ { k } )$ ，此时 $M I ( t _ { k } ) { < } 0$ ，这表明特征项 $t _ { k }$ 和类别 $c _ { j }$ 之间是负相关的。说明当 $p ( t _ { k } \vert c _ { j } )$ 的值越小，而 $p ( t _ { k } )$ 的值越大时，特征项 $t _ { k }$ 与类别 $c _ { j }$ 之间的信息量就越少，特征项 $t _ { k }$ 代表类别 $c _ { j }$ 的能力就越低。从式（2）中可以看出，当计算类别集合的MI值时，特征项与类别为负相关性的部分值会削弱该特征项最终的MI值。在文本情感分类中，正相关性特征有利于提高最终的准确率，而负相关性特征有利于提高最终的查全率[14]，因此负相关性特征的作用也不能忽视[15]。针对这一现象，本文引入正负相关性系数 $\boldsymbol { \gamma }$ 来调节互信息方法中出现的正负相关性问题。

那么，在类别 $c _ { j }$ $( j { = } 1 , 2 , . . . , r )$ ）中，首先定义：

$$
\overline { { f ( t _ { k } ) } } = \frac { 1 } { m } \sum _ { j = 1 } ^ { m } f _ { j } ( t _ { k } )
$$

其中： $\overline { { f ( t _ { k } ) } }$ 表示每个类别中含有的特征项 $t _ { k }$ 的平均文本数，$f _ { j } ( t _ { k } )$ 代表类别 $c _ { j }$ 中包含特征项 $t _ { k }$ 的文本数量。

当 $p ( t _ { k } | c _ { j } )$ 大于 $p ( t _ { k } )$ 时， $\gamma$ 的定义形式如下所示：

$$
\gamma = \omega \times \frac { f _ { j } ( t _ { k } ) - \overline { { f ( t _ { k } ) } } } { \overline { { f ( t _ { k } ) } } }
$$

当 $p ( t _ { k } | c _ { j } )$ 大于 $p ( t _ { k } )$ 时， $\gamma$ 的定义形式如下所示：

$$
\gamma = ( 1 - \omega ) \times \frac { f _ { j } ( t _ { k } ) - \overline { { f ( t _ { k } ) } } } { \overline { { f ( t _ { k } ) } } }
$$

其中： $\boldsymbol { \omega }$ 为调节因子， $\omega$ 的理论取值范围为 $0 . 1 { \sim } 0 . 9$ ，用来调节正负相关特征项的影响力，使得特征项无论是正相关还是负相关，都充分发挥其对于最终情感分类的作用。另外，在Y中，当特征项与类别呈现负相关时， $p ( t _ { k } \vert c _ { j } )$ 的值越大，而$p ( t _ { k } )$ 的值越小时，说明特征项在该类中出现的次数较少，因此，系数 $\gamma$ 中的 $( f _ { j } ( t _ { k } ) - \overline { { f ( t _ { k } ) } }$ 很好地应对了这一情况，进而有效利用了与类别项呈负相关性的特征项。 $( f _ { j } ( t _ { k } ) - \overline { { f ( t _ { k } ) } } ) / \overline { { f ( t _ { k } ) } }$ 也相应表示了特征项文本集合的偏离程度，对于提高最终的特性选择效率有了一定的提高。

综上所述，混合互信息（HMI）的定义形式如下所示：

$$
\mathrm { H } M I ( t _ { k } ) = \alpha \times \sum _ { j = 1 } ^ { r } \beta \times \gamma \times p ( c _ { j } ) \log \frac { p ( t _ { k } | c _ { j } ) } { p ( t _ { k } ) }
$$

HMI算法的伪代码如下：

1. for each document $\mathrm { d } _ { j } \in \mathrm { D }$ do  
2. for each word $\mathfrak { t } _ { k } \in \mathrm { d j }$ do  
3. IF word $\in { \bf C } _ { j }$ then  
4. （204号 $^ { \mathrm { t } _ { c } + + }$ //所求特征项在类别Cj中出现的频数  
5. end if  
6. end for  
7. end for  
8. for each category $\mathbf { C } _ { j } \in \mathbf { C }$ do  
9. $\mathbf { C } _ { k } { + } +$ //数据集类别总数  
10.end for  
11.for each document $\mathrm { d } _ { j \in \mathrm { D } }$ do  
12. if word in $\mathrm { C } _ { j }$ then  
13. （204号 $\mathrm { d } _ { k } { + + }$ //类别 $\mathrm { C } _ { j }$ 中包含所求特征项的文本数量  
14. end if  
15.end for  
16.for each document dj $\in \mathrm { C j }$ do  
17. $\mathbf { D } _ { j } + +$ /类别Cj中文本的数量  
18.end for  
19.for each document $\mathrm { d } _ { j \in \mathrm { D } }$ do  
20. if word $\ u \in \mathrm { d } _ { j }$ then  
21. （204号 ${ \mathrm { c o u n t } } + +$ //含所求特征项的文本数量  
22. end if  
23.end for  
24.for each document $\mathrm { d } _ { j \in \mathrm { D } }$ do  
25. $^ { \mathrm { N + + } }$ /文本总数  
26.end for  
27. $\scriptstyle { \alpha = }$ sqrt (square $\mathrm { ( t } _ { c } \mathrm { - } \big ( \mathrm { s u m ~ } ( \mathrm { t } _ { k } ) / \mathrm { C } _ { k } ) \big ) / \mathrm { C } _ { k } \big )$ （2  
28. $\beta$ =log [N/ (count+0.01)]  
29. if $( \mathrm { d } _ { k } / \mathrm { D } _ { j } ) > = \left( \mathrm { c o u n t } / \mathrm { N } \right)$ then  
30. （20 $\gamma { = } { \omega } ^ { \ast } [ ( \mathrm { d } _ { k } { \mathrm { - c o u n t } } / \mathrm { C } _ { k } ) / \left( \mathrm { c o u n t } / \mathrm { C } _ { k } \right) ]$ （204号  
31. else  
32. $\gamma { = } ~ ( \mathrm { 1 - \infty } ) ^ { \ast } [ ( \mathrm { d } _ { k } { \mathrm { - c o u n t / C } } _ { k } ) / \mathrm { \left( c o u n t / C _ { k } \right) } ]$   
33.end if  
34. HMI $( \mathrm { t _ { k } } , \mathrm { C _ { j } } ) = \mathrm { M I ^ { * } } \alpha ^ { * } \beta ^ { * } \gamma$

# 3 实验结果及分析

# 3.1实验语料集

本文实验分别采用来自于谭松波的酒店管理评论语料集以及美的空调评论语料集来进行实验，两者语料集分别有4000 条评论数据，分为正向评论和负向评论两类，其中正向（pos）评论2000条，负向（neg）评论2000条。为验证算法的有效性，文本采用交叉实验的方式，将语料库的数据取其中的 $8 0 \%$ 作为训练集，用于训练，其余 $20 \%$ 作为测试集，用于检验分类器的效果，进行实验分析。表1展示了本文所用语料集中训练集的相应实例，表2展示了本文所用语料集中测试集的相应实例。

# 表1训练集语料实例

<html><body><table><tr><td>Table1 trainingset corpusexamples</td></tr><tr><td>训练集语料实例：</td></tr><tr><td>S1：设备很简单服务意识很差餐厅的设施就跟街边的小滩一样，卫生条 件很不好。</td></tr><tr><td>S2：房间很小，装修太差，电线全部裸露在外面，脏，不是一般的脏。 S3：位置不错，在市中心，周围吃饭等很方便，房间一如既往的干净。</td></tr><tr><td>表2测试集语料实例 Table2Test set corpus examples</td></tr><tr><td>测试集语料实例：</td></tr><tr><td>S4:地点和位置很好，晚上比较安静，设施较全。对于一般的自助游来 说比较合适。</td></tr><tr><td>S5：酒店还可以，早餐也不错，值得推荐，若价格能再低点就更好了。</td></tr><tr><td>S6：房间装修陈旧，下水管堵塞，晚上折腾了2个多小时，还是没有修 好。</td></tr></table></body></html>

# 3.2 实验评价标准

在文本情感分析中，比较常用的评价标准有查准率(precision)，也叫做准确率，和查全率（recall)，也叫做召回率，以及综合了准确率和查全率的评价标准 $F _ { 1 }$ 值。本文采用以上三种评价标准来对实验结果进行评价。文本情感分类的判断情况主要分为以下四种情况，如表3所示。

Table 3 Judgment of text emotion classification   

<html><body><table><tr><td></td><td>正向样例</td><td>负向样例</td></tr><tr><td>预测结果为正向样例</td><td>TP</td><td>FP</td></tr><tr><td>预测结果为负向样例</td><td>FN</td><td>TN</td></tr></table></body></html>

表4列出了表2中测试集语料实例的实际结果和预测结果实验对比。

表3文本情感分类判断  
表4测试集语料实例实验对比  
Table 4 Test set sample data   

<html><body><table><tr><td>测试集语料实例</td><td>实际结果</td><td>预测结果</td></tr><tr><td>S4</td><td>正向</td><td>正向</td></tr><tr><td>S5</td><td>正向</td><td>负向</td></tr><tr><td>S6</td><td>负向</td><td>正向</td></tr><tr><td>S7</td><td>负向</td><td>负向</td></tr></table></body></html>

其中，TP指的是预测为正向样例，实际也为正向样例的文本数，如表4中语料实例S4所示；FP指的是预测为正向样例，实际为负向样例的文本数，如表4中语料实例S6所示；FN指的是预测为负向样例，实际为正向样例的文本数，如表 4中语料实例S5所示；TN指的是预测为负向样例，实际也为负向样例的文本数，如表4中语料实例S7所示。

那么，关于准确率和召回率的定义形式为

$$
P r e c i s i o n = \frac { T P } { T P + F P }
$$

$$
{ \mathrm { R e } } c a l l = { \frac { T P } { T P + F N } }
$$

$F _ { 1 }$ 值则将准确率和召回率综合起来进行评价，其定义形式如下：

$$
F 1 = \frac { 2 \times P r e c i s i o n \times \mathrm { R e } c a l l } { P r e c i s i o n + \mathrm { R e } c a l l }
$$

# 3.3实验步骤

a）对数据集进行预处理，对语料集进行标注，将正向语料和负向语料合并为一个文档，进行分词处理，本文采用的

是较为常用的jieba中文分词工具。针对表1训练集语料实例分词后结果如表5所示。

表5Jieba分词处理后结果

Table 5 Results after Jieba participle processing

分词处理后结果：

S1:设备很简单服务意识很差餐厅的设施就跟街边的小滩一样，卫生条件很 不好。

S2:房间很小，装修太差，电线全部裸露在外面，脏，不是一般的脏。

S3:位置不错，在市中心，周围吃饭等很方便，房间一如既往 的 干净。

b)对文本中的停用词，标点符号等对文本情感分类无关的因素进去去除。针对表1训练集语料实例分词后结果如下表6所示。

Table 6 results after discontinuation of words

# 去停用词后结果：

S1：设备 很 简单服务 意识 很差 餐厅设施 街边小滩卫生条件很不好

S2：房间很小装修太差电线全部 裸露外面脏不是一般 脏S3：位置不错 市中心周围吃饭 很方便房间一如既往干净

c）分别采用互信息（MI）、混合互信息（HMI)、卡方统计量（CHI）三种特征选择方法进行特征选择。

d）采用词袋模型（BOW）对特征项进行表示，并使用空间向量模型（VSM）将文本数据转换为结构化数据。

e）由于支持向量机（supportvectormachine,SVM）分类器具有结构较为简单，全局最优等优点，已逐渐成为文本情感分析中的主流分类器。因此，本文实验采用了支持向量机分类器对数据进行训练以及测试，并对三种特征选择方法实验结果进行分析对比。

具体的实验流程如图1所示。

![](images/5cb4ced6271f1887a5ecf213ce9886bd2c807d6e7035591e01659397e5d00b19.jpg)  
图1实验流程图  
Fig.1Flow chart of experiment

# 3.4结果及分析

本文实验中分别采用卡方统计量（CHI）、互信息（MI)以及本文提出的混合互信息（HMI）这三种不同的特征选择方法对数据集进行特征选择并进行对比实验。实验中，特征项表示方法采用BOW词袋模型，分别计算在2000、3000、4000、5000、6000、7000、8000和9000维度下的准确率（precision）、召回率（recall）以及 $F _ { 1 }$ 值。另外，由于正相关特征项起主要作用，对式（8）中的调节因子 $\boldsymbol { \mathbf { \rho } } _ { \infty }$ 分别取0.5、0.6、0.7、0.8以及0.9，通过多次对比实验，最终发现@取0.8时，实验效果最佳。表7\~9分别为酒店管理评论在不同维度下准确率、召回率以及 $F _ { 1 }$ 值的数据对比表格。

表7不同维度下准确率对比结果[able 7 comparison of accuracy in different dimensions  

<html><body><table><tr><td>特征维数</td><td>MI</td><td>HMI</td><td>CHI</td></tr><tr><td>2000</td><td>0.58</td><td>0.83</td><td>0.66</td></tr><tr><td>3000</td><td>0.61</td><td>0.83</td><td>0.71</td></tr><tr><td>4000</td><td>0.65</td><td>0.84</td><td>0.72</td></tr><tr><td>5000</td><td>0.70</td><td>0.83</td><td>0.74</td></tr><tr><td>6000</td><td>0.74</td><td>0.84</td><td>0.73</td></tr><tr><td>7000</td><td>0.79</td><td>0.85</td><td>0.74</td></tr><tr><td>8000</td><td>0.81</td><td>0.86</td><td>0.75</td></tr><tr><td>9000</td><td>0.81</td><td>0.86</td><td>0.75</td></tr></table></body></html>

表6去停用词后结果  
表9不同维度下F1值对比结果  

<html><body><table><tr><td>特征维数</td><td>MI</td><td>HMI</td><td>CHI</td></tr><tr><td>2000</td><td>0.59</td><td>0.90</td><td>0.78</td></tr><tr><td>3000</td><td>0.63</td><td>0.90</td><td>0.80</td></tr><tr><td>4000</td><td>0.68</td><td>0.89</td><td>0.77</td></tr><tr><td>5000</td><td>0.71</td><td>0.90</td><td>0.79</td></tr><tr><td>6000</td><td>0.77</td><td>0.88</td><td>0.79</td></tr><tr><td>7000</td><td>0.80</td><td>0.88</td><td>0.80</td></tr><tr><td>8000</td><td>0.81</td><td>0.89</td><td>0.80</td></tr><tr><td>9000</td><td>0.81</td><td>0.90</td><td>0.81</td></tr></table></body></html>

Table 8 comparison of recall rates in different dimensions   
Table 9 comparison of F1 values in different dimensions   

<html><body><table><tr><td>特征维数</td><td>MI</td><td>HMI</td><td>CHI</td></tr><tr><td>2000</td><td>0.59</td><td>0.87</td><td>0.72</td></tr><tr><td>3000</td><td>0.63</td><td>0.87</td><td>0.75</td></tr><tr><td>4000</td><td>0.67</td><td>0.86</td><td>0.74</td></tr><tr><td>5000</td><td>0.70</td><td>0.86</td><td>0.76</td></tr><tr><td>6000</td><td>0.76</td><td>0.87</td><td>0.76</td></tr><tr><td>7000</td><td>0.80</td><td>0.86</td><td>0.77</td></tr><tr><td>8000</td><td>0.81</td><td>0.87</td><td>0.77</td></tr><tr><td>9000</td><td>0.81</td><td>0.87</td><td>0.78</td></tr></table></body></html>

由表7\~9可以看出，混合互信息（HMI）算法在酒店管理评论数据集中，无论是在准确率、召回率，还是在 $F _ { 1 }$ 值上，这三个指标均明显优于另外两种特征选择方法。其中，由表7可以看出，准确率较MI算法提高了 $5 \%$ ，较CHI算法提高了 $1 1 \%$ ；由表8可以看出，召回率较MI算法提高了 $9 \%$ ，较CHI算法提高了 $9 \%$ ；由表9可以看出， $F _ { 1 }$ 值较MI算法提高了 $6 \%$ ，较CHI算法提高了 $9 \%$ 。可以看出，HMI特征选择算法对于文本情感分类效果具有显著的提高。

表10\~12分别为美的空调评论在不同维度下准确率、召回率以及F1值的数据对比表格。

表8不同维度下召回率对比结果  
表10不同维度下准确率对比结果  
Table1O comparison of accuracy in different dimensions   

<html><body><table><tr><td>特征维数</td><td>MI</td><td>HMI</td><td>CHI</td></tr><tr><td>2000</td><td>0.55</td><td>0.69</td><td>0.56</td></tr><tr><td>3000</td><td>0.58</td><td>0.73</td><td>0.56</td></tr><tr><td>4000</td><td>0.64</td><td>0.75</td><td>0.61</td></tr><tr><td>5000</td><td>0.69</td><td>0.80</td><td>0.62</td></tr><tr><td>6000</td><td>0.71</td><td>0.83</td><td>0.64</td></tr><tr><td>7000</td><td>0.73</td><td>0.83</td><td>0.67</td></tr><tr><td>8000</td><td>0.71</td><td>0.84</td><td>0.71</td></tr><tr><td>9000</td><td>0.71</td><td>0.83</td><td>0.72</td></tr></table></body></html>

Table 11 comparison of recall rates in different dimensions   
表12不同维度下准确率对比结果  

<html><body><table><tr><td>特征维数</td><td>MI</td><td>HMI</td><td>CHI</td></tr><tr><td>2000</td><td>0.67</td><td>0.82</td><td>0.78</td></tr><tr><td>3000</td><td>0.69</td><td>0.85</td><td>0.80</td></tr><tr><td>4000</td><td>0.77</td><td>0.89</td><td>0.81</td></tr><tr><td>5000</td><td>0.79</td><td>0.90</td><td>0.83</td></tr><tr><td>6000</td><td>0.78</td><td>0.91</td><td>0.83</td></tr><tr><td>7000</td><td>0.78</td><td>0.91</td><td>0.85</td></tr><tr><td>8000</td><td>0.76</td><td>0.90</td><td>0.85</td></tr><tr><td>9000</td><td>0.78</td><td>0.90</td><td>0.84</td></tr></table></body></html>

表11不同维度下召回率对比结果  
Table 12 comparison of accuracy in different dimensions   

<html><body><table><tr><td>特征维数</td><td>MI</td><td>HMI</td><td>CHI</td></tr><tr><td>2000</td><td>0.60</td><td>0.79</td><td>0.69</td></tr><tr><td>3000</td><td>0.68</td><td>0.79</td><td>0.69</td></tr><tr><td>4000</td><td>0.73</td><td>0.80</td><td>0.70</td></tr><tr><td>5000</td><td>0.74</td><td>0.83</td><td>0.69</td></tr><tr><td>6000</td><td>0.74</td><td>0.80</td><td>0.70</td></tr><tr><td>7000</td><td>0.74</td><td>0.82</td><td>0.73</td></tr><tr><td>8000</td><td>0.73</td><td>0.82</td><td>0.72</td></tr><tr><td>9000</td><td>0.75</td><td>0.83</td><td>0.74</td></tr></table></body></html>

由表10\~12可以看出，混合互信息（HMI）算法在美的空调评论中，无论是在准确率、召回率，还是在 $F _ { 1 }$ 值上，这三个指标均也同样明显优于另外两种特征选择方法。其中，由表10可以看出，准确率较MI算法提高了 $12 \%$ ，较CHI算法提高了 $1 1 \%$ ；由表11可以看出：召回率较MI算法提高了 $12 \%$ ，较CHI算法提高了 $6 \%$ ；由表12可以看出， $F _ { 1 }$ 值较MI算法提高了 $8 \%$ ，较CHI算法提高了 $9 \%$ 。综上可以看出，HMI 特征选择算法对于两种数据集的文本情感分类效果均具有显著的提高。

为了对不同特征维度下文本情感分类的准确率、召回率以及 $F _ { 1 }$ 值的变化情况有一个更加直观的认知，如图2\~4所示，采用折线图来展现在酒店管理评论数据集中，不同维度下三个值的变化情况。

![](images/69985ea28a2df187d51005642ee827fa88604a73c1d2a72c61855d4369c0d154.jpg)  
图2不同特征选择维度下准确率折线图

从图2\~4可以看出，MI和CHI算法效果在维度在7000时开始趋于稳定，而HMI算法自始至终都保持在一定的范围，且HMI算法整体的分类效果均优于另外两个算法。

![](images/2d3358d67128c3af0c955a3a6ffa4dbeed759401026a17054406bd210c174345.jpg)  
图3不同特征选择维度下召回率折线图

![](images/14a5da9ea30c460206c2f26b6aaa1e3a279a31726caf508631feaa8feb2b5419.jpg)  
Fig.3Broken line diagram of recall rate under different feature selection dimensions   
图4不同特征选择维度下F1值折线图 Fig.4Fl-value line diagram under different feature selection dimensions

如图5\~7所示，采用折线图来展现在美的空调评论数据集中不同维度下三个值的变化情况。

从图5\~7可以看出，三种算法的准确率以及召回率都呈现上升的趋势，但明显HMI算法的整体效果要优于另外两种算法。另外，HMI算法的 $F _ { 1 }$ 值在维度上具有较好的稳定性。

![](images/eef7b32756be07f15d7a5e387edf3e10332db9ce957540b109362463eba4102d.jpg)  
Fig.2Broken line diagram of accuracy under different featur selection dimensions   
图5不同特征选择维度下准确率折线图 Fig.5Broken line diagram of accuracy under different feature selection dimensions

![](images/8461ab0775f35878772d0a33d91b278acc76ec58480f3833a5a8b025424ec150.jpg)  
图6不同特征选择维度下召回率折线图

![](images/f97a48606a6e37a3bd471c19c63c497183ca2ed1030ffecc7b2b1e04d9dd4ca1.jpg)  
Fig.6Broken line diagram of recall rate under different feature selection dimensions   
图7不同特征选择维度下F1值折线图 Fig.7Fl-value line diagram under different feature selection dimensions

综上所述，混合互信息算法在准确率、召回率以及 $F _ { 1 }$ 值都明显高于MI和CHI方法，并且在特征维度的选择上具有较强的稳定性。因此可以得出，混合互信息（HMI）特征选择算法可以有效地提高特征选择的质量，进而提高文本情感分类的效果。

# 4 结束语

本文在分析互信息的特征选择方法存在的正负相关性现象以及忽略词频信息的问题基础之上，提出了一种混合互信息特征选择算法(HMI)。该算法通过引入逆文档频率，类间词频以及正负相关性指标，有效地使得词频信息在MI方法中得以有效地利用，并且很好地利用了正负相关性在该算法中不可忽视的作用。通过实验结果可以得出，混合互信息（HMI）方法明显优于其他特征选择方法，并在文本情感分类中取得了不错的效果。

# 参考文献：

[1]Cherry C,Mohammad S.Binary classifiers and latent sequence models for emotion detection in suicide notes [J].Journal of Biomedical Informatics Insights,2012,5(S1):147-154.   
[2]Atiyeh M, Hossein MM.Robust feature selection from microarray data

Based on cooperative game theory and qualitative mutual information

[J]. Advances in Bioinformatics,2016,2016 (1): 1-16. [3] 李平，戴月明，王艳．基于混合卡方统计量与逻辑回归的文本情感 分析[J].计算机工程,2017,43(12):192-196.(Li Ping,DaiYueming, Wang Yan. Text emotion analysis based on mixed chi-square statistics and logical regression [J].Computer Engineering，2017,43(12): 192-196.) [4] Tang Jian, Zhou Shuigeng. A new approach for feature selection from microarray data based on information [J].IEEE/ACM Transon Computational Biology and Bioinformatics. 2016.13(6): 1004-1015. [5]Bidi N,Elberichi Z. Feature selection for text classification using genetic algorithms [C]/Proc of the 8th International Conference on Modelling,Identification and Control. Piscataway,NJ:IEEE Press,2016: 806-807. [6]朱颢东，陈宁，李红婵．优化的互信息特征选择方法[J].计算机工 程与应用,2010,46(26):122-124.(Zhu Yidong,Chen Ning,Li Hongchen. Optimized mutual information feature selection method [J].Computer Engineering and Application,2010,46 (26): 122-124.) [7] 陶永才，赵国桦，石磊，等．一种改进的 MapReduce 互信息文本特 征选择机制[J]．小型微型计算机系统，2018，39(3)：433-438.(Tao Yongcai, Zhao Guohua, Shi Lei,et al. Improved MapReduce mutual information text feature selection mechanism [J]. Minicomputer System, 2018,39(3):433-438.) [8]Li Kewen,Yu Mingxiao,Liu Lu,et al.Feature selection method based on weighted mutual information for imbalanced Data [J]. International Journal of Software Engineering and Knowledge Engineering,2018, 28(8): 1177-1194. [9] Coelho F, Braga AP, Verleysen M.A mutual information estimator for continuous and discrete variables applied to feature selection and classification problems [J]. International Journal of Computational Intelligence Systems,2016,9(4): 726-733. [10]刘海峰，陈琦，张以皓．一种基于互信息的改进文本特征选择[J]. 计算机工程与应用,2012,48(25):1-4.(Liu Haifeng,Chen Qi,Zhang Yihao.An improved text feature selection based on mutual information [J]. Computer Engineering and Application,2012,48 (25): 1-4.) [11]林少波，杨丹，徐玲．基于类别相关的新文本特征提取方法[J].计 算机应用研究,2012,29(5):1680-1683.(Lin Shaobo,Yang Dan,Xu Ling.A new text feature extraction method based on category correlation [J]．ComputerApplication Research，2012，29(5): 1680-1683. ) [12] Calvo B,Larrariaga P,Lozano JA.Feature subset selection from positive and unlabeled example [J]. Patten Recognition Letters,2009, 30(11): 1027-1036. [13] Lin Yaojin,Hu Qinghua,Liu Jinghua,et al. Streaming feature selection for multilabel learning based on fuzzy mutual information [J]. IEEE Trans on Fuzzy Systems,2017,25(6): 1491-1507. [14] Bostani H, Sheikhan M. Hybrid of binary gravitational search algorithm and mutual information for feature selection in intrusion detection systems [J]. Soft Computing,2017,21(9): 2307-2324. [15]辛竹，周亚建．文本分类中互信息特征选择方法的研究与算法改进 [J]．计算机应用，2013，33(S2):116-118.(Xin Zhu,Zhou Yajian. Research and improvement of mutual information feature selection method in text classification [J].Computer applications,2O13,33 (S2): 116-118. ) [16]