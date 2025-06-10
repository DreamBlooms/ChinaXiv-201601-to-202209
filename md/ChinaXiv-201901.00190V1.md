# 基于最近邻距离权重的ML-KNN算法\*

陆凯，徐华+

(江南大学 物联网工程学院，江苏 无锡 214122)

摘要：在大数据环境下，K近邻多标签算法（ML-KNN）高时间复杂度的问题显的尤为突出；此外，ML-KNN也没有考虑k个近邻对最终分类结果的影响。针对上述问题进行研究，首先将训练集进行聚类，再为测试集找到一个距离其最近的训练数据簇作为新的训练数据集；然后计算最近邻样本的距离权重，并用该权重描述最近邻和其他近邻对预测结果的影响；最后使用新的目标函数为待测样本分类。通过在图片、Web页面文本数据等数据集上的实验表明，所提算法得到了更好的分类结果，并且大大降低了时间复杂度。

关键词：多标签分类；ML-KNN；聚类；最近邻；距离权重 中图分类号：TP301.6 doi:10.19734/j.issn.1001-3695.2018.09.0738

ML-KNN algorithm based on nearest neighbor distance weight

Lu Kai, Xu Hua+ (School of Internetof Things Engineering,Jiangnan University,WuxiJiangsu 214122,China)

Abstract: Inordertoeficientlyapply multi-labelK-nearestneighbor(ML-KNN)inbigdataset,thispaper firstconducted clustering algorithmto separate thetrainingdataset into several parts,from which founda nearest cluster asnew training set for test dataset; and then calculated nearest neighbor distance weight,by which the effect of $\mathbf { k }$ neighbors was described. Finally,anunseen sample could be clasified bythis new method.Numberical simulationresults indiferent datesets show that a better classfication result is obtained,and the time complexity of the algorithm is also improved.

Key words: multi-label classification; ML-KNN; cluster; nearest neighbor; distance weight

# 0 引言

互联网的发展直接造成数据规模和数据信息量的飞速增长，这就导致了传统的单标签分类已经无法适应当下的分类需求，因此多标签分类逐渐成为数据分类的重点话题。在传统的单标签分类1中，每一个训练样本都只对应着一个标签！其中 $\mathbf { \xi } _ { l }$ 来自于一个有限的、互斥的标签集合L。假设$D = \{ ( m _ { 1 } , l _ { 1 } ) , ( m _ { 2 } , l _ { 2 } ) , . . . , ( m _ { n } , l _ { n } ) \}$ ，其中 $m$ 表示输入的数据，1表示 $m$ 从属的单标签。如果标签的数量为2，则称为二分类，而如果标签数量大于2，则称为多标签分类。多标签(multi-label)分类2和多类别(multi-class)分类3是完全不同的两个概念。多类别分类是在两个以上的类中预测出属于样本的一个类，所以其本质还是单标签分类。

一般来说，多标签分类方法主要可以分为问题转换法、算法适应法和集成方法[4.5]三类。问题转换法是将一个多标签分类问题转换为一个或者多个单标签分类问题，其中应用最为广泛方法的则是将每一个标签的预测都看做是一个独立的二分类任务，即：对于每一个不同的标签 $\lambda \in L$ 都给出一个二分类器 $h _ { \lambda }$ ： $X  \{ \lnot \lambda , \lambda \}$ ；然后将原始数据集转换为 $| L |$ 个数据集 $D _ { \lambda }$ ，其中 $\lambda$ 表示原始数据包含该标签，而 $- x$ 则表示原始数据不包含该标签，这种方法被称为二分关联(BR)算法[67]。算法适应法是将一些传统的分类器扩展为一个可以直接处理多标签分类问题的多标签分类器，多标签K近邻算法（ML-KNN）就是该方法比较典型例子。集成方法则是将多个一种或多种多标签基分类器向融合以达到更好的分类效果近年来涌现出不少有关ML-KNN算法的研究，并都取得了不错的成果。文献[8]通过在ML-KNN算法中引入辅助标签的方式提出了一种分层的ML-KNN方法，引入辅助标签的目的就是弥补了ML-KNN算法没有考虑标签之间具有相关性的缺陷，从而改善了算法的最终结果；在文献[9]中，首先使用原型选择算法（PS）来减少训练数据的数量，并且在这个删减过的数据集上，根据标签之间的关联程度来得到一个标签的排序，通过这种方法可以将很多不相关的原型丢弃；文献[10]则是先利用线性判别式分析（LDA）提取出数据的特征，再降低整个数据矩阵的维度，从而训练得到一个分类器和标签之间的相关性，最后可获得到分类结果；在文献[11]中，首先计算出标签集合中每对标签间的条件概率，然后对于即将被预测的标签，将其与已经预测的标签间的条件概率进行排序，求出最大值，最后将最大值与对应标签值相乘同时结合最大化后验概率来构造多标签分类模型。从以上的几种研究情况来看，现在大部分研究都集中于多标签的标签相关性上，如文献[12]也是一个利用标签相关性来提升ML-KNN算法的研究方式。标签相关性确实是提升了算法的运行结果，但是当数据量很大时，也是存在标签量很大的情况，这必然会造成更大的时间消耗。另外，说到大数据自然会想到Hadoop、Spark 等分布式技术，文献[13]就是结合Spark的优越性和ML-KNN算法的特性提出了基于Spark框架下的多标签最近邻算法。而在实际的生产生活中，Spark 需要的分布式环境的成本也是不可忽视的。在本文所提的算法中，利用聚类算法的同时引入最近邻距离权重就能达到降低算法时间复杂度和提升算法性能的双重目的。

# 1 相关介绍

# 1.1多标签分类

多标签分类问题可以用数学语言描述为：

给定一个d维样本空间 $m$ ，有限的标签集合 $\boldsymbol { L } = \{ l _ { 1 } , l _ { 2 } , . . . , l _ { q } \}$ 那么训练集则可以表示为${ \cal D } = \{ ( m _ { 1 } , L _ { 1 } ) , ( m _ { 2 } , L _ { 2 } ) , . . . , ( m _ { n } , L _ { n } ) \} ( m _ { i } \in R ^ { d } , L _ { i } \subseteq L )$ ，需要计算出一个多标签分类器 $h \colon D \times L \to R$ 。

# 1.2ML-KNN 算法简述

ML-KNN[I4]是基于传统的KNN算法和最大后验概率法则的懒惰型多标签学习算法，它的主要思想是一个样本的标签集合可以由该样本的近邻来决定。给定一个待测样本 $x$ ，假设它的标签集合为 $L ( x )$ ，ML-KNN算法首先在训练数据集中找出 $x$ 的 $\mathbf { k }$ 个近邻，再统计这些近邻中属于每一个标签的数量，记为 $j$ 。然后根据最大后验概率准则来确定测试样本的标签集合，且每一个 $l _ { i } \in { L }$ 的后验概率计算如下：

$$
P ( l _ { i } \in L ( x ) \vert E _ { j } ^ { l _ { i } } ) = P ( l _ { i } \in L ( x ) ) P ( E _ { j } ^ { l _ { i } } \vert l _ { i } \in L ( x ) )
$$

最后，对于每一个 $l _ { i } \in L$ 是否在 $x$ 的标签集合中，ML-KNN算法使用如下规则：

$$
y _ { x } ( l _ { i } ) = \left\{ { 1 , P ( l _ { i } \in L ( x ) \vert E _ { j } ^ { l _ { i } } ) \geq 0 . 5 } \right.
$$

其中： $E _ { j } ^ { l _ { i } }$ 表示 $x$ 的 $\mathbf { k }$ 个近邻中有 $\mathrm { j }$ 个样本属于标签 $l _ { i }$ 的事件；如果 $y _ { x } ( l _ { i } ) = 1$ 则表示 $l _ { i }$ 在 $x$ 的真实标签集合中，如果 $y _ { x } ( l _ { i } ) = 0$ 则表示 $l _ { i }$ 不在 $x$ 的真实标签集合中。

# 2 改进算法

对于数据集中的每一个样本，它的k个近邻的标签集合理论上应该跟它自身的标签集合有一定程度上的相似，这种相似度会随着近邻到样本距离的改变而改变，并且距离大，相似度越小。而ML-KNN算法的计算过程中并没有将这种关系考虑进去，针对这一缺陷，本文同时考虑了待测样本的 $\mathbf { k }$ 个近邻和最近邻的影响，并利用权重来衡量这种影响。因此根据式(1)可得到一个新的分类函数：

$$
P ( l _ { i } \in L ( x ) | E _ { j } ^ { l _ { i } } ) = w ^ { * } N N _ { x } ( l _ { i } ) +
$$

$$
( 1 - w ) ^ { * } P ( l _ { i } \in L ( x ) ) P ( E _ { j } ^ { l _ { i } } \mid l _ { i } \in L ( x ) )
$$

其中： $w$ 表示由 $x$ 的最近邻到 $x$ 的距离所转换而来的权重，也是 $x$ 的最近邻在本文改进算法中的权重； $1 - w$ 则表示 $x$ 的 $\mathbf { k }$ 个近邻的权重； ${ N N } _ { x } ( l _ { i } )$ 表示 $x$ 的最近邻样本是否含有 $l _ { i }$ 标签，取值只能是0或者1。

由式(3)可知，本文算法的关键是如何确定权重 $w$ ，将距离转换为权重主要有反函数、减函数、高斯函数三种方法。对于一个距离 $^ d$ ，反函数最为简单，将距离加上一个常量之后取倒数，即 $w = \frac { 1 } { d + c }$ ，加入常量 $\mid c \mid$ 的目的是为了避免当距离接近0时而导致反函数为无穷大，因此反函数的缺点也比较明显，它会赋予近邻项很大的权重，而随着 $\boldsymbol { \mathscr { d } }$ 的增大 $w$ 则会以一个极快的速度递减；减函数跟反函数类似，也是引入了一个常量 $\mid c \mid$ ，若 $d \leq c$ ，则 $w = c - d$ ，否则 $w = 0$ ，虽然该函数克服了近邻分配权重过大的问题，但是 $w$ 一定会慢慢递减到0；高斯函数则是利用式(4)将距离转换成权重：

$$
w = a ^ { * } e ^ { \frac { d ^ { 2 } } { 2 c ^ { 2 } } }
$$

其中： $\boldsymbol { a }$ 和 $\mid c \mid$ 是常数； $\textit { d }$ 表示的距离都是欧氏距离。高斯函数克服了近邻项分配权重过大的潜在问题，并且权重会随着

距离的增加而减少，与减函数不同的是这里的权重始终不会跌至0，所以本文将采用高斯函数的方法将距离转换为权重。本文改进算法的详细步骤如下：

算法1：改进ML-KNN算法的详细步骤

输入：训练数据，测试数据。

输出：分类结果。

1利用 $\mathbf { k }$ -means聚类算法将训练数据分为r个聚类中心，记为 $R _ { 1 } , R _ { 2 } , . . . , R _ { r }$ ;

2利用 $\mathbf { k }$ -means聚类算法将测试数据分为t个聚类中心，记为 $T _ { 1 } , T _ { 2 } , . . . , T _ { r }$ ;

3当 $i \in \{ 1 , 2 , . . . , t \}$ 时：

4 计算 $T _ { i }$ 到 $R _ { j }$ 的欧式距离，记为 $D ( T _ { i } , R _ { j } )$ ， $\mathbf { j } { = } 1 , 2 , . . . , \mathrm { r }$

5 根据第4步获取距离 $T _ { i }$ 最近的 $R _ { j }$ ，$R _ { j } = { \mathrm { m i n } } \{ D ( T _ { i } , R _ { j } ) \} , \mathbf { j = } 1 , 2 , . . . , \mathrm { r } ;$

将 $T _ { i }$ 对应的簇作为新的测试数据集，记为 $N e w Y$ ：

7将第5步得到的 $R _ { j }$ 对应的簇作为新的训练数据，记为NewX；

8 对于每一个 $\boldsymbol { x _ { u } } \in N e w X$ ，计算每一个 $l _ { i } \in L$ 的先验概率：

$$
P ( l _ { i } \in L ( x _ { u } ) ) = ( s + \textstyle \sum _ { u = 1 } ^ { m } y _ { x _ { u } } ( l _ { i } ) ) / ( s ^ { * } 2 + m )
$$

$$
P ( l _ { i } \notin L ( x _ { u } ) ) = 1 - P ( l _ { i } \in L ( x _ { u } ) )
$$

获取 $x _ { u }$ 的 $\mathbf { k }$ 个近邻 $N _ { x _ { u } }$ 、最近邻 $N N _ { x _ { u } }$ 以及最近邻距离 $x _ { u }$ 的距离 $d$ ，并使用式(4)将其转换为 $w$

10 计算 $l _ { i } \in L$ 的后验概率：

令 $p \in \{ 0 , 1 , . . . , k \}$ （20

$$
P ( E _ { p } ^ { l _ { i } } \left| l _ { i } \in L ( x _ { u } ) \right. ) = ( s + c [ p ] ) / \left( ( s ^ { * } \big | N _ { x _ { u } } \big | + 1 ) + \sum _ { q = 0 } ^ { k } c [ q ] \right)
$$

$$
P ( E _ { p } ^ { l _ { i } } \mid l _ { i } \not \in L ( x _ { u } ) ) = ( s + c ^ { * } [ p ] ) / \left( ( s ^ { * } \left| N _ { x _ { u } } \right| + 1 ) + \sum _ { q = 0 } ^ { k } c [ q ] \right)
$$

11利用式(3)计算每一个 $z _ { \nu } \in N e w Y$ 拥有 $l _ { i }$ 的后验概率，得到最终预测结果

根据算法1，本文先是使用 $\mathrm { ~ K ~ }$ -means分别将训练数据和测试数据聚类[15]，再为每一个测试数据簇选择一个距离它最近的训练数据簇，这样一方面减少了数据的规模，从而减少了ML-KNN算法的计算量，最后达到降低算法时间复杂度的目的；另一方面距离测试数据最近的训练簇中的数据相较于其他训练数据和测试数据具有一定程度上相似度，从而也提高了多标签算法的各种评价指标。然后再使用本文改进ML-KNN算法对数据分类。

# 3 实验结果与分析

为了方便比较算法的性能，将本文提出的改进算法称为DML-KNN，文献[16]中提出的改进算法称为IML-KNN，并分别在MATLAB上实现。MATLAB是一个功能强大且使用的算法仿真工具。

# 3.1评价指标

a)Hammingloss。计算一个样本标签对被错误分类的次数，比如一个本该属于样本的标签没有被预测到，或者一个不属于样本的标签被预测到了。

$$
h l o s s ( h ) = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } \frac { 1 } { Q } \big | h ( x _ { i } ) \Delta Y _ { i } \big |
$$

其中： $\varrho$ 是标签数量； $h ( x _ { i } )$ 表示分类结果； $h ( x _ { i } ) \Delta Y _ { i }$ 表示样本真实标签集合与分类结果的对称差。

b)Coverage。评估为了涵盖所有可能的样本标签需要平均给出的标签列表。

$$
\mathrm { c o v } ( f ) = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } \operatorname* { m a x } _ { y \in Y _ { i } } r a n k _ { f } ( x _ { i } , y ) - 1
$$

c)One-error。评估排在前面的标签不在样本真实标签中的次数。

$$
o n e - e r r o r ( f ) = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } H ( x _ { i } )
$$

若排在首位的标签在样本真实标签中，则 $H ( x _ { i } ) = 1$ ，否则$H ( x _ { i } ) = 0$ 。

d)Rankingloss。评估被反向排序的标签对的平均分。

$$
r l o s s ( f ) = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } \frac { 1 } { \left| Y _ { i } \right| \left| \overline { { Y _ { i } } } \right| }
$$

其中： $\overline { { Y _ { i } } }$ 是 $Y _ { i }$ 在总标签集合上的补集。

e)Averageprecision。该指标的含义与One-error相反，它评估的是排在前面的标签在样本真实标签中的次数。

$$
a \nu g p ( f ) = \frac { 1 } { m } \sum _ { i = 1 } ^ { m } \frac { \displaystyle \sum _ { y \in Y _ { i } } \displaystyle \frac { \displaystyle \left| \left\{ y ^ { \cdot } \mid r a n k _ { f } ( x _ { i } , y ^ { \cdot } ) \leq r a n k _ { f } ( x _ { i } , y ^ { \cdot } ) , y ^ { \cdot } \in Y _ { i } \right\} \right| } { r a n k _ { f } ( x _ { i } , y ) } } { \displaystyle \left| Y \right| }
$$

以上五个评价中，前四个越小越好，最后一个越大越好。

# 3.2 数据集

表1中记录的是选取于keel的四个数据集的详细信息，它们分别为电子邮件信息数据集enron、图片数据集 scene、酵母细胞信息数据集Yeast和包含Web页面文本数据的数据集delicious。其中标签基数表示一个样本平均具有几个标签，标签密度是由标签基数除以标签总数。

表1实验数据信息  

<html><body><table><tr><td>名称</td><td>enron</td><td>scene</td><td>Yeast</td><td>delicious</td></tr><tr><td>样本数</td><td>1702</td><td>2407</td><td>2417</td><td>16105</td></tr><tr><td>标签数</td><td>53</td><td>6</td><td>14</td><td>983</td></tr><tr><td>标签基数</td><td>3.3784</td><td>1.074</td><td>4.237</td><td>19.02</td></tr><tr><td>标签密度</td><td>0.064</td><td>0.179</td><td>0.303</td><td>0.019</td></tr><tr><td>训练数</td><td>1532</td><td>1927</td><td>2177</td><td>14495</td></tr><tr><td>测试数</td><td>170</td><td>480</td><td>240</td><td>1600</td></tr></table></body></html>

# 3.3 实验结果及分析

基于3.2节中的四个数据集和3.1节中的五个评价指标，分别进行本文算法的性能评估。由算法1可知，本文算法具有以下几个关键参数：最近邻数k、高斯函数中的两个可调参数 $^ { a , c }$ 、训练数据聚类簇数r、测试数据聚类簇数t。对于ML-KNN算法，最近邻数k应当避免过小或者过大，因为过小时，近邻中包含的信息也会越少；而过大时，虽然近邻中包含的信息量大了，但是这会很大程度上增加算法的计算量。结果多次实验，本文将k的值定为20。表2\~5分别是当 $^ { a , c }$ 不同时，三种算法在四个数据集上的实验结果。

表2三种算法在数据集enron上的实验结果  
Table 2Results of three algorithms on enron   

<html><body><table><tr><td colspan="3"></td><td>a=5 c=1/2</td><td>a=7 c=1/3</td><td>a=10 c=1/2</td></tr><tr><td>指标</td><td>ML-KNN</td><td>IML-KNN</td><td></td><td>DML-KNN</td><td></td></tr><tr><td>hloss</td><td>0.0507</td><td>0.0502</td><td>0.0453</td><td>0.0453</td><td>0.0461</td></tr><tr><td>rloss</td><td>0.1002</td><td>0.0896</td><td>0.0616</td><td>0.0595</td><td>0.0581</td></tr><tr><td>one-error</td><td>0.3</td><td>0.288</td><td>0.1534</td><td>0.1503</td><td>0.1534</td></tr><tr><td>coverage</td><td>14.365</td><td>13.306</td><td>10.057</td><td>9.8392</td><td>9.8032</td></tr><tr><td>avgprec</td><td>0.638</td><td>0.647</td><td>0.7421</td><td>0.7439</td><td>0.7514</td></tr><tr><td>Time(s)</td><td>20.781</td><td>20.53</td><td>18.976</td><td>18.895</td><td>19.153</td></tr></table></body></html>

Table 1 Experimental datainformation   

<html><body><table><tr><td colspan="3"></td><td>a=5 c=1/2</td><td>a=8 c=1/3</td><td>a=10 c=1/5</td></tr><tr><td>指标</td><td>ML-KNN</td><td>IML-KNN</td><td></td><td>DML-KNN</td><td></td></tr><tr><td>hloss</td><td>0.01851</td><td>0.018468</td><td>0.0143</td><td>0.016</td><td>0.0133</td></tr><tr><td>rloss</td><td>0.12416</td><td>0.11953</td><td>0.1063</td><td>0.115</td><td>0.0887</td></tr><tr><td>one-error</td><td>0.39006</td><td>0.38199</td><td>0.275</td><td>0.259</td><td>0.2164</td></tr><tr><td>coverage</td><td>578.954</td><td>556.0199</td><td>378.1</td><td>472.45</td><td>346.48</td></tr><tr><td>avgprec</td><td>0.32995</td><td>0.34044</td><td>0.4982</td><td>0.4195</td><td>0.5007</td></tr><tr><td>Time(s)</td><td>899.5247</td><td>916.6451</td><td>343.14</td><td>462.93</td><td>343.81</td></tr></table></body></html>

表3三种算法在数据集 scene 上的实验结果 Table 3Results of three algorithms on scene   

<html><body><table><tr><td colspan="3"></td><td>a=5</td><td>a=6 c=1/2</td><td>a=8 c=1/5</td></tr><tr><td>指标</td><td>ML-KNN</td><td>IML-KNN</td><td>c=1/3</td><td>DML-KNN</td><td></td></tr><tr><td>hloss</td><td>0.0906</td><td>0.083681</td><td>0.0697</td><td>0.0723</td><td>0.0696</td></tr><tr><td>rloss</td><td>0.0723</td><td>0.069687</td><td>0.0667</td><td>0.0692</td><td>0.0657</td></tr><tr><td>one-error</td><td>0.2291</td><td>0.22292</td><td>0.1861</td><td>0.1973</td><td>0.1815</td></tr><tr><td>coverage</td><td>0.4542</td><td>0.43958</td><td>0.40688</td><td>0.4294</td><td>0.4012</td></tr><tr><td>avgprec</td><td>0.867</td><td>0.87111</td><td>0.88854</td><td>0.8819</td><td>0.891</td></tr><tr><td>Time(s)</td><td>14.53</td><td>14.3504</td><td>6.1741</td><td>5.9862</td><td>6.065</td></tr></table></body></html>

表4三种算法在数据集Yeast上的实验结果

Table 4Results of three algorithms on Yeast   

<html><body><table><tr><td colspan="3"></td><td rowspan="2">a=5 c=1/2</td><td rowspan="2">a=7 c=1/4</td><td rowspan="2">a=10 c=1/6</td></tr><tr><td></td><td></td><td></td></tr><tr><td>指标</td><td>ML-KNN</td><td>IML-KNN</td><td></td><td>DML-KNN</td><td></td></tr><tr><td>hloss</td><td>0.20119</td><td>0.20179</td><td>0.24084</td><td>0.2022</td><td>0.2012</td></tr><tr><td>rloss</td><td>0.17932</td><td>0.17843</td><td>0.19358</td><td>0.1857</td><td>0.1755</td></tr><tr><td>one-error</td><td>0.24167</td><td>0.2333</td><td>0.26088</td><td>0.2419</td><td>0.21385</td></tr><tr><td>coverage</td><td>6.4333</td><td>6.425</td><td>6.577</td><td>6.5398</td><td>6.4809</td></tr><tr><td>avgprec</td><td>0.75232</td><td>0.75351</td><td>0.73327</td><td>0.7464</td><td>0.76022</td></tr><tr><td>Time(s)</td><td>5.435</td><td>5.4848</td><td>4.083</td><td>4.1248</td><td>4.0908</td></tr></table></body></html>

表5三种算法在数据集delicious上的实验结果

由上面的四个表格可知，在数据集enron上，当$\mathrm { a } { = } 1 0 { , } \mathrm { c } { = } 1 / 2$ 时本文算法效果最好；在数据集scene上，当$\mathrm { a } { = } 8 , \mathrm { c } { = } 1 / 5$ 时本文算法效果最好；在数据集Yeast上，当$\mathrm { a } { = } 1 0 , \mathrm { c } { = } 1 / 6$ 时本文算法效果最好；在数据集delicious上，当$\mathrm { a } { = } 1 0 { , } \mathrm { c } { = } 1 / 5$ 时本文算法效果最好；同时也不难看出，本文算法在时间复杂度上也具有不小的优势，尤其在数据集delicious上，当数据量大幅度增加时，本文算法在五大性能指标和时间复杂度上都有大幅度的改进。进一步地，由算法1可知，不同的聚类簇数对本文算法也有至关重要的影响，因为它直接决定了测试数据对应的训练集，从而最终影响到预测结果。当a、c确定时，表6\~9反映了当聚类簇数不同时，本文算法在四个数据集上的性能。

Table 5Results of three algorithms on delicious   
表6数据集enron上不同聚类簇数的影响  
Table 6Effect of different r,t on enron   

<html><body><table><tr><td></td><td>r=2，t=2</td><td>r=3，t=2</td><td>r=3，t=3</td></tr><tr><td>hloss</td><td>0.046087</td><td>0.052775</td><td>0.055204</td></tr><tr><td>rloss</td><td>0.058146</td><td>0.10065</td><td>0.058409</td></tr><tr><td>one-error</td><td>0.15337</td><td>0.29707</td><td>0.27053</td></tr><tr><td>coverage</td><td>9.8032</td><td>12.7693</td><td>9.9893</td></tr><tr><td>avgprec</td><td>0.75137</td><td>0.6572</td><td>0.71208</td></tr><tr><td>Time(s)</td><td>19.1834</td><td>17.421</td><td>17.2456</td></tr></table></body></html>

表7数据集 scene上不同聚类簇数的影响  

<html><body><table><tr><td></td><td>r=2，t=2</td><td>r=3，t=3</td><td>r=4，t=3</td></tr><tr><td>hloss</td><td>0.069413</td><td>0.072451</td><td>0.11154</td></tr><tr><td>rloss</td><td>0.065248</td><td>0.069544</td><td>0.096498</td></tr><tr><td>one-error</td><td>0.18011</td><td>0.19142</td><td>0.31161</td></tr><tr><td>coverage</td><td>0.39939</td><td>0.43201</td><td>0.56425</td></tr><tr><td>avgprec</td><td>0.89178</td><td>0.88367</td><td>0.82217</td></tr><tr><td>Time(s)</td><td>6.0315</td><td>4.4674</td><td>4.0325</td></tr></table></body></html>

Table7Effect of different r,t on scene   
Table 8Effect ofdifferent r,ton Yeast   

<html><body><table><tr><td></td><td>r=2，t=2</td><td>r=3，t=2</td><td>r=3，t=3</td></tr><tr><td>hloss</td><td>0.20412</td><td>0.21709</td><td>0.21794</td></tr><tr><td>rloss</td><td>0.17922</td><td>0.19141</td><td>0.18643</td></tr><tr><td>one-error</td><td>0.20681</td><td>0.26982</td><td>0.25124</td></tr><tr><td>coverage</td><td>6.5013</td><td>6.6214</td><td>6.6703</td></tr><tr><td>avgprec</td><td>0.75848</td><td>0.7398</td><td>0.74164</td></tr><tr><td>Time(s)</td><td>4.1438</td><td>2.2736</td><td>2.926</td></tr></table></body></html>

表9数据集delicious上不同聚类簇数的影响

表8数据集Yeast上不同聚类簇数的影响  
Table9Effect of different r,ton delicious   

<html><body><table><tr><td></td><td>r=11，t=4</td><td>r=13，t=3</td><td>r=14，t=4</td></tr><tr><td>hloss</td><td>0.014148</td><td>0.015778</td><td>0.013979</td></tr><tr><td>rloss</td><td>0.10453</td><td>0.13485</td><td>0.10342</td></tr><tr><td>one-error</td><td>0.28109</td><td>0.32058</td><td>0.31589</td></tr><tr><td>coverage</td><td>378.5584</td><td>451.5746</td><td>373.349</td></tr><tr><td>avgprec</td><td>0.49485</td><td>0.41648</td><td>0.47827</td></tr><tr><td>Time(s)</td><td>416.7709</td><td>419.4521</td><td>422.1061</td></tr></table></body></html>

由表6\~9可知，在数据集enron、scene、Yeast上， $\scriptstyle \mathbf { r } = 2$ ，$\scriptstyle { \mathrm { t } = } 2$ 时算法效果最好；在数据集delicious上，当 $\scriptstyle \mathbf { r } = 1 1$ ， $\scriptstyle { \mathrm { t } = 4 }$ 时算法效果最好。与此同时，r、t的取值需要适当，若r太小，则起不到降低时间复杂度的效果，但当r太大时，虽然时间可能会减少，但是也可能会大幅降低算法的精度；对于t来说，它决定了算法的循环次数，即决定了算法的计算量，所以t的取值不宜太大。图1\~6直观地体现了本文算法的优越性。其中coverage 和时间会因为数量规模的不同而出现较大的差异，所以本文在这两者的比较上利用百分比的方式。

![](images/193e45ee723a5b1fd97e46d93f3a8713d109440381af69a6e839635375799566.jpg)  
图1三种算法的 hloss 对比  
Fig. 1 Hloss comparison of three algorithms

0.2   
0.18 0.16 一 0.14 0.12 三 0.01 0.06 I I 0.04 0.02 0 enron scene Yeast delici ous 数据集 ■ML-KNN ■IML-KNN ■DML-KNN   
oi-ni 0.45   
0.4   
0.35   
0.3 lmm   
0.25   
0.2   
0.15   
0.1   
0.05 0 数据集 ■ML-KNN ■IML-KNN ■DML-KNN

![](images/a5b5b96a2cd88d5815dfc15a3cb87c81b6c4983aed58574cb233b57883c6c1b1.jpg)  
Fig.3 One-error comparison of three algorithms   
图4三种算法的coverage 对比

![](images/dd177b7fd89d1825d467ff8376f5e3fe65b91be341048f5a35438c4c12bba8c1.jpg)  
图3三种算法的one-error 对比  
Fig.4 Coverage comparison of three algorithms   
图5三种算法的avgprec 对比

![](images/7bf12f2ad4c8a8f03517df3134b83caf6ee436660ab4c3cc131160ddc0ef6698.jpg)  
图2三种算法的rloss 对比  
Fig. 2 Rloss comparison of three algorithms   
Fig. 5 Avgprec comparison of three algorithms   
图6三种算法的时间对比  
Fig. 6 Time comparison of three algorithms

# 4 结束语

针对传统的ML-KNN算法高时间复杂度的问题，本文先将训练数据和测试聚类以降低数据的规模，从而减少算法的计算量，最终达到降低时间复杂度的目的；同时本文还考虑了 $\mathbf { k }$ 个近邻会因为距离的不同而对预测结果产生不同的影响，并将这种影响利用最近邻距离权重衡量。结合聚类和最近邻距离权重，本文提出了一种改进的ML-KNN算法。实验结果也表明本文算法会取得更好的分类效果，并且在多标签评价指标上也优于原始算法。

# 参考文献：

[1]Liu Chunming,Cao Longbing.A coupled K-nearest neighbor algorithm for multi-label classification [C]// Advances in Knowledge Discovery and Data Mining.Berlin: Springer International Publishing,2015: 176-187.   
[2]Chen Zijie,Hao Zhifeng.Latent semantic KNN algorithm for multi-label learning[C]//Proc of International Conference on Machine Learning and Cybernetics.Berlin: Springer Berlin Heidelberg,2015: 278-284.   
[3]Zhou Ligang,Tam Kwoping,Fu Jita.Predicting the listing status of Chinese listed companies with multi-class classification models [J]. Information Sciences,2016,328(C): 222-236.   
[4]Mahdavi-Shahri A,Houshmand M,Yaghoobi M,et al.Applying an ensemble learning method for improving multi-label classification performance [C]//Proc of Signal Processing and Intelligent Systems. Berlin:Springer Berlin Heidelberg,2017:14-15.   
[5] 李玲，刘华文，马宗杰，等．基于特征选择的集成多标签分类算法 [J].计算机工程与科学,2013,35(10):137-143.(LiLin,Liu Huawen, Ma Zongjie,et al.An ensemble multi-label classification method using feature selection [J]. Computer Engineering & Science,2013,35 (10): 137-143.)   
[6] Tanaka E A,Macedo A A．A multi-label approach using binary relevance and decision trees applied to functional genomics [J].Journal of Biomedical Informatics,2015,54(C): 85-95.   
[7]Montanes E，Senge R，Barranquero J，et al.Dependent binary relevance models for multi-label classification [J].Pattern Recognition, 2014,4/ (3): 1494-1508.   
[8]Qi Hongwei, Zhou Yanquan,Guo Qi.A hierarchical ML-KNN method for complex emotion analysis on customer reviews [C]//Proc of International Conference on Mechatronics Engineering and Information Technology.2016:6.   
[9]Calvo-Zaragoza J,Valero-Mas JJ,Rico-Juan JR. Improving KNN multi-label classfication in Prototype selection scenarios using class proposals [J].Pattern Recognition,2015,48 (5):1608-1622.   
[10] Li Zhiqiang.An improved ML-KNN multi-label classification model based on feature dimensionality reduction [C]// Proc of International Conference on Computer, Mechatronics and Electronic Engineering. [S.l.]: Science and Engineering Research Center,2016: 4.   
[11]檀何凤，刘政怡．基于标签相关性的K近邻多标签分类方法[J].计 算机应用，2015,35(10):2761-2765.(Tan Hefeng，Liu Zhengyi. Multi-label K-nearest neighbor algorithm by exploiting label correlation [J].Journal of Computer Applications,2015,35 (10):2761-2765.)   
[12] Yang Xiaodan,Zhou Lihua,Wang Lizhen.An improved ML-KNN approach based on coupled similarity [C]// Proc of Asia-Pacific Web Conference.Berlin: Springer International Publishing,20l6:77-89.   
[13]王进，夏翠萍，欧阳卫华，等.Spark下的并行多标签最近邻算法[J]. 计算机工程与科学,2017,39 (2):227-235.(Wang Jin,XiaCuiping, OuYang Weihua,et al.Parallel multi-label K-nearest neighbor algorithm based on Spark [J].Computer Engineering & Science,2017, 39 (2):227-235.)   
[14] Zhang Minling,Zhou Zhihua.ML-KNN:a lazy learning approach to multi-label learning[J].Pattern Recognition,2007,40(7): 2038-2048.   
[15] Deng Zhenyun,Zhu Xiaoshu,Cheng Debo,et al.Efficient KNN classification algorithm for big data [J].Neurocomputing,2016,195 (C): 143-148.   
[16] ZengYong,Fu Haoming,Zhang Yuping,et al.An improved ML-KNN algorithm by fusing nearest neighbor classification [J].DEStech Transactions on Computer Science and Engineering,2016 (aics): 8196.