# 基于关键词相似度的短文本分类方法研究

张振豪1，过弋1,2.3′，韩美琪1，王吉祥1

(1.华东理工大学 信息科学与工程学院，上海 200237;2.石河子大学 信息科学与技术学院，新疆 石河子 832003;3.大数据流通与交易技术国家工程实验室——商业智能与可视化技术研究中心，上海 200436)

摘要：在传统的文本分类中，文本向量空间矩阵存在“维数灾难”和极度稀疏等问题，而提取与类别最相关的关键词作为文本分类的特征有助于解决以上两个问题。针对以上结论进行研究，提出了一种基于关键词相似度的短文本分类框架。该框架首先通过大量语料训练得到 word2vec词向量模型；然后通过 TextRank获得每一类文本的关键词，在关键词集合中进行去重操作作为特征集合。对于任意特征，通过词向量模型计算短文本中每个词与该特征的相似度，选择最大相似度作为该特征的权重。最后选择K近邻(KNN)和支持向量机SVM作为分类器训练算法。实验基于中文新闻标题数据集，与传统的短文本分类方法相比，分类效果平均提升约 $6 \%$ ，从而验证了该框架的有效性。

关键词：词向量；特征选择；短文本分类；特征权重 中图分类号：TP391.1 doi: 10.19734/j.issn.1001-3695.2018.04.0440

# Research on short text classification based on keyword similarity

Zhang Zhenhao', Guo ${ \mathrm { Y i ^ { 1 , 2 , 3 \dagger } } }$ ,Han Meiqi',Wang Jixiang1 (1.SchoolofnformationScience&Engineering,EastChina UniversityofScience&Technologyhanghai2O37,Cin;2. Schoolof InformationScience&Technology，Shihezi UniversityXinjiang832003，China；3.Business Inteligence& Visualization Research Center，National Engineering Laboratory forBig Data Distribution& Exchange Technologies, Shanghai 200436, China)

Abstract: Inorder tocope with the problemof data sparsityand“curse of dimensionality”in textclassification,this paper proposes a shorttextclasification framework bytaking keyword as featrues and assigning keyword similarityas feature weight.First,ittraineda word2vec model withlargecorpusdata,thengot keywordsofeachcategorytextbytextrank.And it selected unique keywords fromthe keywordscollctionasfeatures.Foreach feature,itcalculatedthesimilarityof word in the short text by word2vec model,andasignedthe maximum similarityasthe weightofthe feature.Finally,itchose KNN and SVMas clasifier.Experiments on dataset of Chinese news headlines demonstrate that the accuracyoutperforms other usual methods by $6 \%$ ：

Key words: word embedding; feature selecting; short text classification; feature weighting

# 0 引言

近几年，由于互联网的快速发展，人们也越来越依赖于从网络中获取信息。如何快速准确地获取自己想要的信息成为当前一个重点研究课题。而文本数据量的飞速增长，混乱分布极大影响了信息获取的效率与结果，其中还包含大量诸如微博、新闻标题、商品评论等短文本。因此对短文本进行分类也吸引了越来越多的研究。

在传统的文本分类中，一般采用文本向量空间模型方法[I]但是该方法对于短文本具有特征稀疏、语义特征不明显等特点。目前对于该问题，主要有两种方法：a)利用搜索引擎对短文本进行扩展[2]，将短文本扩展为一般文本进行分类；b)利用大量知识库、语料库作为背景知识[3]，发现词语之间的语义关系。以上两种方法均能提升段文本分类的性能。但是仍然存在着计算耗时、无法处理新词等问题。

针对特征稀疏、语义特征不明显等问题，文献[4]利用LDA主题一词分布矩阵的主题向量改进方法降低特征维度进行短文本分类。文献[5]融合词语类别特征和语义进行短文本分类，虽然效果相比传统方法有所提升，但是两者均采用LDA主题模型。该模型属于无监督学习，速度较慢，且依赖主题数量的选择，需要不断优化。文献[6]提出了提取文档关键词作为文本特征的方法，也取得了较好的分类结果。虽然文档关键词考虑了文本语义信息，但是文档关键词会随着文档数量的增加而增加，导致文本向量空间矩阵维度较大，计算耗时。本文结合不同方法的特点，采用TextRank提取类别关键词，作为新的短文本特征，使得文本向量空间的特征集合不再是长度达数千的词汇表而是短小有限的关键词集合。再通过word2vec模型计算词语之间的语义相似度作为特征权值，保留了短文本的一定语义信息，在此基础上训练分类器进行短文本分类。

本文的主要贡献如下:

a）本文提出了一种基于类别关键词的文本特征选择方法，类别关键词个数远小于文档的总词数，能够较好地解决维度过高等问题。b）在特征表示中本文将词语之间的相似度作为特征的权重，弥补了“词袋”模型中未考虑语义的缺点。c）基于以上两点本文提出了一种新的短文本分类框架，通过对真实数据集的实验表明该框架相比传统分类方法效果有一定提升。

# 1 相关工作与流程

设短文本集合 $D { = } \{ d _ { I } , d _ { 2 } , d _ { 3 } , . . . , d _ { n } \}$ ，短文本类别标签$Y { = } \{ y _ { I } , y _ { 2 } , y _ { 3 } { \ldots } y _ { n } \}$ ，特征集 $W { = } \{ w _ { I } , w _ { 2 } , w _ { 3 } , { \ldots } , w _ { m } \}$ 。本文的主要目的是通过基于关键词相似度利用 $W$ 将 $\textbf {  { D } }$ 转换成向量空间矩阵$X = \{ \pmb { x } _ { I } , \pmb { x } _ { 2 } , \pmb { x } _ { 3 } , . . . , \pmb { x } _ { n } \} ^ { T } , \pmb { x } _ { \mathrm { i } } ( 1 \le i \le n )$ 均为 $m$ 维向量,再训练得到分类器，能够使得将 $\textbf {  { D } }$ 中的元素尽可能分类得到正确的类别。具体流程如图1所示。

![](images/1dec432ce34efd60fd122b3c2eea4b99b96787e610533d670f7c4cb9988dea30.jpg)  
图1基于关键词相似度的短文本分类流程  
Fig.1Short text classification process based on keyword similarity

# 2 特征选择及特征表示

在本章中主要介绍基于基于TextRank的短文本特征选择以及基于word2vec的特征表示。

# 2.1基于TextRank 的短文本特征选择

传统的短文本特征的基本思想是对文本集合中的每一个特征计算某种统计度量值，并且设定一个阈值。若该度量值小于阈值，将该特征过滤；否则认为该特征为有效特征。比较典型的方法有文档频率、信息增益、互信息等。此类方法存在无法处理新文本的缺陷，即若文本中的特征均不存在有效特征集合中，该文本将无法有效表示。

针对以上问题，本文提出提取类别关键词作为文本特征。目前主流的关键词提取方法以无监督方法为主，其中涉及统计方法、图模型方法以及语义方法。以词频一逆文档频率（termfrequency-inverse document frequency,TF-IDF）[7]为基础，衍生了很多有效的关键词抽取算法，但是TF-IDF仅仅考虑词频，没有考虑到语义和词与词之间的关系，而且无法对单一文档进行关键词提取,并不适合进行类别的关键词提取。

TextRank[8算法基于词汇的共现链，以图模型的方法提取文档关键词，该方法效果较好，也能够实现对单一文档的关键词提取。在TextRank算法中，首先构建候选关键词图$\scriptstyle { G = ( V , E , W ) }$ ，其中节点集 $V = \{ \nu _ { I , } \nu _ { 2 , } \nu _ { 3 , } . . . , \nu _ { n } \}$ ，由文档中的候选关键词组成，一般为词性为名词、形容词、动词的非停用词。$W { = } \{ w _ { i j } | 1 { \le } i { \le } n \land 1 { \le } j { \le } n \}$ 为图的权重集合， $E { = } \{ ( \nu _ { i } , \nu _ { j } ) \mid \nu _ { i } { \in } V$ $\bigwedge { } _ { V } \in { \cal V } \bigwedge { w } _ { i j } \in { \cal W } \bigwedge { w } _ { i j } \ne 0 \}$ 为各个节点之间的非空有限集合。两个节点之间存在边仅当它们对应的词汇在长度为 $K$ 的窗口中共现， $K$ 表示窗口大小，即最多共现 $K$ 个单词。由 $\mathbf { G }$ 可以得到对应的相似度矩阵 $S _ { n \times n }$ ，如式(1)所示。

$$
S _ { n \times n } = { \left( \begin{array} { l l l } { w _ { 1 1 } } & { \cdots } & { w _ { 1 n } } \\ { \vdots } & { \ddots } & { \vdots } \\ { w _ { n 1 } } & { \cdots } & { w _ { n n } } \end{array} \right) }
$$

由 $G$ 和 $S _ { n \times n }$ ，通过式(2)迭代计算各节点的权重。

$$
W S ( \nu _ { i } ) = ( 1 - d ) + d \times \sum _ { \nu _ { j } \in I n ( \nu _ { i } ) } \frac { w _ { j i } } { \displaystyle \sum _ { \nu _ { k } \in O u t ( \nu _ { j } ) } w _ { j k } } W S ( \nu _ { j } )
$$

其中： $W S ( \nu _ { i } )$ 为节点vi的权重值； $d$ 是阻尼系数，一般设置为0.85，表示任意一节点跳转到其他任意节点的概率； $I n ( \nu i )$ 表示指向节点 $\nu _ { i }$ 的所有节点的集合； $O u t ( \nu _ { i } )$ 表示 $\nu _ { i }$ 指向的所有节点的集合。一般当迭代20\~30次，迭代阈值设置为 $0 . 0 0 0 1$ 。计算结束之后，根据节点的权重降序排列。在此基础上，本文根据每类文本的背景知识语料提取类别关键词，如对于体育类背景知识语料，提取的关键词依次为{“比赛”，“球队”，“球员”....}等、对于财经类背景知识语料、提取的关键词依次为{“中国”，“公司”，“市场”...}等。

# 2.2基于word2vec 的特征权重

在确定文本特征之后，需要对每一个样本的所有特征分配一定的权重。分配权重的好坏将极大影响分类效果。比较传统的权值分类方法有二分类（该特征在文本出现即为1，未出现即为0)、词频(tf)、逆文档频率(idf)、TF-IDF等。文献[9]通过文档中不包含的词计算存在的词的特征权重，在其他条件相同的情况下，较之前的TF-IDF，信息熵等方法分类效果有明显的提升。文献[10]针对朴素贝叶斯分类器，通过从训练数据深度计算特征加权频率一定程度提高了分类效果。然而大多数有关特征权重的研究还是仅仅考虑特征频率等“词袋"层面的联系，未考虑到特征与文本之间的语义关系。为此，本文将词与词之间的相似度作为特征权值，在文本转换为向量的过程中保留了一定语义内容。

为了准确计算词语之间的相似度，本文选择word2vec[II]模型。Word2vec 模型自提出以来就得到了广泛应用，文献[12]利用word2vec模型用于观点分类，效果比词袋模型出色。文献[13]借助word2vec模型所包含的语义信息提取中文评论的情感特征，在情感分析方面取得了不错的效果。Word2vec模型其本质是一种具有隐含层的神经网络，输入输出均为词汇表，通过学习词与上下文之间的关系，待神经网络收敛之后，从输入层到隐含层的向量代表词汇表中每个词的向量。Word2vec包含两种训练模型 CBOW(continueous bag-of-words)和 Skip-Gram。相对来说CBOW更适用于较大的语料数据。因此本文采用CBOW训练模型得到的词向量模型表示短文本中的词汇。

![](images/ab0049322e65f95881f3c20311370f5cd344e9f9d61f01ade4c8c4aee14a19bb.jpg)  
图2 CBOW模型Fig.2 CBOW model

在CBOW训练模型中，它将词的上下文作为输入，而该词作为输出，如图2所示。输入层为第 $i$ 个词的前后 $\mathbf { \nabla } _ { m }$ 个词，输出层为第 $i$ 个词 $w _ { i }$ ，输入输出层向量均为one-hotencoding，即维度数等于词汇数量。核心思想即根据上下文预测当前词语的概率。在训练结束以后，可以得到所有词的词向量。令第 $i$ 个词的词向量为 $s _ { i }$ ，第 $j$ 个词的词向量为 $s _ { j }$ ，则可以根据余弦相似度计算得到两个词之间的相似度，如式(3)所示。

$$
s i m ( s _ { i } , s _ { j } ) = \frac { s _ { i } \bullet s _ { j } } { \left| s _ { i } \right| \left| s _ { j } \right| }
$$

# 3 基于关键词相似度的短文本分类方法

本章将介绍基于关键词相似度的短文本分类方法的具体框架以及相关细节。各符号定义如表1所示。

表1短文本分类中各符号的定义  
Table 1Definition of symbols   

<html><body><table><tr><td>符号</td><td>定义</td></tr><tr><td>P={p1.,p2,..,pk}</td><td>不同类别的背景知识语料</td></tr><tr><td>D={d1,d2,...dn}</td><td>短文本集合</td></tr><tr><td>C</td><td>短文本类别集合</td></tr><tr><td>di={q1,q2,..gm}</td><td>文本i的词汇集合</td></tr></table></body></html>

<html><body><table><tr><td>K={k1,k2,..,.k]</td><td>所有类别的关键词集合</td></tr><tr><td>kj</td><td>类别j的关键词集合</td></tr><tr><td>Y</td><td>短文本的标签集合</td></tr><tr><td>Dic</td><td>文本特征集合</td></tr><tr><td>Vi={w1,W2,.., Wq}</td><td>文本i表示的特征向量</td></tr><tr><td>sim(a,b)</td><td>向量a与向量b的相似度</td></tr><tr><td>Model</td><td>词向量模型</td></tr></table></body></html>

# 3.1短文本特征选择

基于TextRank，本文依据算法1获得短文本的文本特征。算法1基于关键词的短文本特征选择输入：不同类别的文本语料 $P$ ，关键词个数 $n$ 。输出：类别关键词集合Dic。$\textcircled{1}$ for $p _ { i }$ in $P$ ：$\textcircled{2}$ $p _ { i } { = }$ Textpre-process $. ( p _ { i } )$ \*对背景知识语料做文本预处理\*/$\textcircled{3}$ ki=TextRank $\scriptstyle ( p _ { i } , \mathrm { t o p k } = n _ { * }$ /\*TextRank降序排列关键词，选取第 $i$ 类语料的前 $n$ 个关键词\*/$\textcircled{4}$ end for$\textcircled{5}$ for $k _ { i }$ in $K$ ：$\textcircled{6}$ for eachword in $k _ { i }$ ：$\textcircled{7}$ （204号 if word appears only once:$\textcircled{8}$ Dic.append(word)/\*对各类别关键词集合去重，保在一个类别关键词集合中出现的词\*$\textcircled{9}$ end for$\textcircled{10}$ end for

# 3.2短文本特征向量表示

在进行文本分类之前，都需要将文本转换成特征向量以便能够使用分类器进行训练和学习。本文的特征向量表示方法如算法2所示。

算法2短文本集合特征向量表示

输入：文本特征集合 $D i c$ ，词向量模型Model，短文本集合 $D$ 。

输出：短文本集合特征向量 $ { \boldsymbol { V } } _ { \circ }$

$\textcircled{1}$ for $d _ { i }$ in $D$ ：  
$\textcircled{2}$ for each $w$ in $D i c { : } / { ^ { * } D i c }$ 中元素个数即为特征个数\*/  
$\textcircled{3}$ $\mathrm { \ m a x \_ s i m = } { } - 1$   
$\textcircled{4}$ for $q _ { j }$ in $d _ { i }$ ：  
$\textcircled{5}$ $\mathrm { s } { = } \mathrm { s i m } ( \mathrm { M o d e l } ( q _ { j } ) , \mathrm { M o d e l } ( w ) ) / { } ^ { * }$ 通过词向量将词转  
换成向量进行相似度计算\*/  
$\textcircled{6}$ $\mathrm { i f ( s > m a x \_ s i m ) m a x \_ s i m = s }$   
$\textcircled{7}$ end for  
$\textcircled{8}$ $w _ { j } { = } \mathrm { m a x } \_ { \mathrm { s i m } / { * } }$ 文本 $i$ 的第 $j$ 个特征权重\*/  
$\textcircled{9}$ end for  
$\textcircled{10}$ end for

# 3.3 短文本分类

通过以上方法就能够得到短文本集合的特征向量矩阵$X = \{ \pmb { x } _ { I } , \pmb { x } _ { 2 } , \pmb { x } _ { 3 } , . . . , \pmb { x } _ { n } \} ^ { T }$ ， $n$ 为短文本数据集大小； $\pmb { x } \mathrm { i } ( 1 \leq i \leq n )$ 为 $\mathbf { \nabla } _ { m }$ 维向量； $m$ 为特征集大小。结合标签集合 $Y$ 可以使用分类算法如KNN、SVM等进行实验，验证以上特征选择和特征权重计算方法的优劣。

# 4 实验与结果

为了验证基于关键词相似度的短文本分类方法的有效性，本文利用近两年的新浪热点新闻数据进行实验。首先介绍数据集以及对比的算法；最后在数据集上进行10折交叉验证该方法的有效性。

# 4.1数据集与实验设置

本文以近两年的热点新闻为实验数据，采集了包括体育、社会、娱乐、财经、科技、国际、军事七大类的新闻标题以及正文。标题用于短文本分类，正文用于作为背景知识进行关键词提取。同时为了数据均匀分布，各类新闻标题数据数量均为2000条，如表2所示。而word2vec 模型则由额外语料（百度百科 $2 0 \textup { G }$ 、新闻语料 $1 2 \mathrm { ~ G ~ }$ 、小说 $9 0 \mathrm { ~ G ~ }$ ）数据训练而得。对于分类算法的设置中，SVM 核函数采用径向基函数(radial basisfunction，RBF)。RBF在线性不可分的情况下效果优于线性核且计算耗时少于多项式核。通过实验比较，KNN选择近邻数N为15较合适。

表2新闻标题数据集  
Table 2Data set of news headline   

<html><body><table><tr><td>Category</td><td>Number of news headlines</td></tr><tr><td>Technology</td><td>2000</td></tr><tr><td>Sports</td><td>2000</td></tr><tr><td>Society</td><td>2000</td></tr><tr><td>Entertainment</td><td>2000</td></tr><tr><td>Military</td><td>2000</td></tr><tr><td>International</td><td>2000</td></tr><tr><td>Finance</td><td>2000</td></tr></table></body></html>

# 4.2实验设计

为验证本文提出的方法的有效性，首先在相同的分类算法上，验证不同的关键词个数对分类效果的影响；然后选择较合适的关键词个数作为实验参数，与以下两个实验做对比。

a)TF-IDF对数据进行常规预处理（去除标点符号、去除停用词等)后，计算短文本的TF-IDF特征向量。最后使用KNN和SVM进行训练和验证。

b)Sum-CBOW由于短文本词数较少，获得的TF-IDF 特征向量维度高且极其稀疏，且词向量本身具有较好的语义特征，文献[14]提出了将短文本中所有词的词向量累加作为短文本的特征向量的方法，即特征维度为词向量的维度而不是类别关键词的数目。该方法的文本向量空间维度低、分类速度快，效果也相对较好。该方法在本文中简称Sum-CBOW。

最后为验证语义性对分类效果的提升，在特征集保持不变的情况下，特征权重由词频代替，对比实验结果。在此过程中，本文提出的方法为Key-CBOW。

# 4.3实验评估

本次实验评估分别有以下四个指标：

a)分类准确率Precision。  
类别 $c _ { i }$ 的分类准确率 $p _ { i }$ ，如式(4)所示。

b)分类召回率Recall。

类别ci的分类召回率ri，如式(5)所示。

c)F1分数。

类别ci的F1分数f1i，如式(6)所示。

$$
f 1 _ { i } = \frac { 2 \times p _ { i } \times r _ { i } } { p _ { i } + r _ { i } }
$$

d）宏平均F1分数。

它是所有类别的F1分数的算术平均值，如式(7)所示。

$$
F 1 _ { { m a c r o } } = { \frac { 1 } { k } } { \sum } _ { i = 1 } ^ { k } f 1 _ { i }
$$

# 4.4实验结果及分析

图3验证了类别关键词个数对短文本分类效果的影响，验证指标为F1-macro。关键词个数取 $N { = } \{ \ 2 0 , 4 0 , 6 0 , 8 0 , 1 0 0 , 1 2 0 ,$ （204号140,160}。总体上，SVM算法要优于KNN算法，原因在于特征为类别关键词，类别间可分性比较好；而KNN比较适合基于样本相似度的方法，KNN并不依赖于特征的可区分度。当关键词个数较少时，效果均不是很理想，随着关键词个数的增加，文本特征集扩大，分类效果提升。当关键词个数达到一定值之后达到稳定，F1-macro值不再提高。为避免过拟合以及欠拟合等问题，本文后续实验中的关键词个数均设置为100。

![](images/059f2d84d3e1c25501f8adff8c0b5b7ba903a813947154ac92005003d49d0841.jpg)  
图3基于关键词个数的F1-macro 值对比  
Fig.3Comparison of F1-macro based on number of keywords

对比实验结果如表3所示。根据表3的结果可以看到，Sum-CBOW的分类效果相对较差，将短文本的词向量直接叠加作为该文本的特征向量，虽然能够一定程度保留该短文本的语义信息，但削弱了类别特征的区分度。传统的TF-IDF在本次实验中效果较好，但是存在召回率和准确率偏差略大、特征多、维度稀疏、计算耗时等问题。而本文方法选取类别关键词作为特征以及将短文本与特征的最大相似度作为特征权重，能够有效挖掘出短文本与不同类别的核心语义关联，在转换为特征向量的过程中保留语义。因此对于测试数据集，虽然部分指标未达到最大值，但是本文方法在准确率和召回率保持平衡的同时，将平均准确率和平均召回率都提升了约 $6 \%$ 。图4为三个实验对于数据集各类别分类F1值的直观对比，证明了本文提出的基于关键词相似度的短文本分类方法能够有效提高分类效果。

表3不同算法的分类效果表现比较  

<html><body><table><tr><td colspan="4">TF-IDF</td><td colspan="3">Sum-CBOW</td><td colspan="4">Key-CBOW</td></tr><tr><td>Category</td><td>P</td><td>R</td><td>F1</td><td>P</td><td>R</td><td>F1</td><td>P</td><td>R</td><td></td><td>F1</td></tr><tr><td>Technology</td><td>0.77</td><td>0.74</td><td>0.76</td><td>0.58</td><td>0.75</td><td>0.66</td><td></td><td>0.74</td><td>0.73</td><td>0.73</td></tr><tr><td>Sports</td><td>0.92</td><td>0.88</td><td>0.90</td><td>0.91</td><td>0.87</td><td>0.89</td><td></td><td>0.94</td><td>0.95</td><td>0.95</td></tr><tr><td>Society</td><td>0.57</td><td>0.71</td><td>0.64</td><td>0.80</td><td>0.51</td><td></td><td>0.63</td><td>0.75</td><td>0.71</td><td>0.73</td></tr><tr><td>Entertainment</td><td>0.70</td><td>0.90</td><td>0.79</td><td>0.68</td><td>0.91</td><td></td><td>0.78</td><td>0.89</td><td>0.90</td><td>0.90</td></tr><tr><td>Military</td><td>0.80</td><td>0.87</td><td>0.83</td><td>0.79</td><td>0.81</td><td></td><td>0.80</td><td>0.83</td><td>0.86</td><td>0.85</td></tr><tr><td>International</td><td>0.75</td><td>0.63</td><td>0.69</td><td>0.68</td><td>0.91</td><td>0.78</td><td></td><td>0.73</td><td>0.77</td><td>0.75</td></tr><tr><td>Finance</td><td>0.88</td><td>0.55</td><td>0.68</td><td>0.82</td><td>0.52</td><td>0.64</td><td></td><td>0.76</td><td>0.74</td><td>0.75</td></tr><tr><td>Average</td><td>0.77</td><td>0.75</td><td>0.75</td><td>0.75</td><td></td><td>0.75</td><td>0.74</td><td>0.81</td><td>0.81</td><td>0.81</td></tr></table></body></html>

![](images/064efbe1cff01168d8e91690028629c61cfba092b84bd48ed66d57e14a6d6752.jpg)  
图4不同算法的类别F1值对比  
Fig.4Comparison ofF1 values of category of different algorithms

针对验证语义关系对分类能力的影响，本文设计了第三个实验Key-Frequency。在此实验中，对于短文本特征向量$\scriptstyle x = \{ w _ { I , } w _ { 2 } , \dotsc , w _ { m } \}$ ( $m$ 为特征集个数)，特征权重不再是短文本与该特征的相似度，而是该特征在短文本中的频次，KNN为该实验的分类算法。实验结果的F1值如表4所示。TF-IDF分类效果明显比该方法出色，说明在缺失了语义相似度和特征较少的情况下，以词频为特征权重无法处理大部分且不在特征集合中的词，从而验证了本文提出的将语义相似度作为特征权重的方法能够有效提升分类效果。

Table 3Comparison of classification effects on different algorithms   
表4语义相似度对分类F1值的影响  
Table 4Influence of semantic similarity on F1 value   

<html><body><table><tr><td>Category</td><td>Key-Frequency</td><td>TF-IDF</td></tr><tr><td>Technology</td><td>0.31</td><td>0.76</td></tr><tr><td>Sports</td><td>0.40</td><td>0.90</td></tr><tr><td>Society</td><td>0.44</td><td>0.64</td></tr><tr><td>Entertainment</td><td>0.33</td><td>0.79</td></tr><tr><td>Military</td><td>0.55</td><td>0.83</td></tr><tr><td>International</td><td>0.10</td><td>0.69</td></tr><tr><td>Finance</td><td>0.31</td><td>0.68</td></tr></table></body></html>

# 5 结束语

鉴于短文本分类中高度稀疏、缺少语义特征等问题，本文提出了一种基于关键词相似度的短文本分类框架。该框架综合考虑类别词汇以及语义信息，通过选择有限的类别关键词作为特征集合以及将词与特征之间的相似度作为特征权重，既解决了文本特征维度过高的问题，又保留了短文本的语义，提高了文本的区分度。本文通过基于词频和基于语义的对比实验，验证了该框架的有效性。

接下来的工作主要是分析不同类别短文本分类效果差异较大的现象，以及考虑相应的优化方法。对于用语义相似度表示特征权重的方法，可以考虑对比语义相似度的不同计算方法，验证本文方法的可行性。

# 参考文献：

[1]Salton G,Wong A,Yang C S.A vector space model for automatic indexing [M].New York:ACMPress,1974.   
[2]Sun Aixin. Short text classification using very few words [C]// Proc of the 35th International ACM SIGIR Conference on Research and Development in Information Retrieval.New York: ACMPress,2012:1145-1146.   
[3]Chen Mengen,Jin Xiaoming, Shen Dou.Proceedings of the twenty-second international joint conference on artificial intelligence short text classification improved by learning multi-granularity topics [J]. Journal of Shanxi Institute of Economic Management, 2012:152-157.   
[4]杨萌萌，黄浩，程露红，等．基于LDA 主题模型的短文本分类[J].计 算机工程与设计，2016,37(12):3371-3377.(Yang Mengmeng,Huang Hao,Cheng Luhong,et al. Short text classification based on LDA topic model[J].Computer Engineering and Design,2016,37(12): 3371-3377.)   
[5]马慧芳，周汝南，吉余岗，等．融合词语类别特征和语义的短文本分类 方法[J].计算机工程与科学,2017,39(2):399-404.(Ma Huifang,Zhou Runan,Ji Yugang,et al.A short text classification method combining lexical category features and semantics [J]. Computer Engineering & Science,2017,39 (2): 399-404.)   
[6]Onan A,Korukoglu S,Bulut H. Ensemble of keyword extraction methods and classifiers in text classification [J]. Expert Systems with Applications, 2016,57 (C): 232-247.   
[7]Salton G, Buckley C.Term-weighting approaches in automatic text retrieval [M].Oxford:Pergamon Press,Inc,1988.   
[8]Mihalcea R.TextRank: bringing order into texts [J].Empirical Methods on Natural Language Processing,20o4: 404-411.   
[9]Sabbah T, Selamat A,Selamat MH,et al.Modified frequency-based term weighting schemes for text classification [J].Applied Soft Computing, 2017,58:193-206.   
[10] Jiang Liangxiao,Li Chaoqun,Wang Shasha,et al. Deep feature weighting for naive Bayes and its application to text classification [J].Engineering Applications of Artificial Intelligence,2016,52 (C): 26-39.   
[11]Mikolov T,Sutskever I,Chen Kai,et al.Distributed representations of words and phrases and their compositionality [J].2013,26:3111-3119.   
[12] Enriquez F, Troyano JA,L6pez-Solaz T.An approach to the use of word embeddings in an opinion classification task [J].Expert Systems with Applications,2016,66:1-6.   
[13] Zhang Dongwen,Xu Hua, Su Zengcai,et al. Chinese comments sentiment classification based on word2vec and SVM perf [J].Expert Systems with Applications,2015,42(4):1857-1863.   
[14]江大鹏．基于词向量的短文本分类方法研究[D].杭州：浙江大学, 2015.(Jiang Dapeng,Research on short text classification based on word distributed representation [D]. Hangzhou: Zhejiang University,2015.)