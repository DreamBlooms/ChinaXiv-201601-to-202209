# BioTrHMM:基于迁移学习的生物医学命名实体识别算法

高冰涛，张 阳，刘斌(西北农林科技大学 信息工程学院，陕西 杨凌 712100)

摘要：传统的生物医学命名实体识别方法需要大量目标领域的标注数据，但是标注数据代价高昂。为了降低生物医学文本中命名实体识别对目标领域标注数据的需求，将生物医学文本中的命名实体识别问题化为基于迁移学习的隐马尔可夫模型问题。对要进行命名实体识别的目标领域数据集无须进行大量数据标注，通过迁移学习的方法实现对目标领域的识别分类。以相关领域数据为辅助数据集，利用数据引力的方法评估辅助数据集的样本在目标领域学习中的贡献程度，在辅助数据集和目标领域数据集上计算权值进行迁移学习。基于权值学习模型，构建基于迁移学习的隐马尔可夫模型算法 BioTrHMM。在GENIA语料库的数据集上的实验表明，BioTrHMM算法比传统的隐马尔可夫模型算法具有更好的性能；仅需要少量的目标领域标注数据，即可具有较好的命名实体识别性能。

关键词：迁移学习；隐马尔可夫模型；命名实体识别；文本挖掘 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.07.0702

BioTrHMM: named entity recognition algorithm based on transfer learning in biomedical texts

Gao Bingtao, Zhang Yang†, Liu Bin (College ofInformation Engineering,NorthwestA&F University,Yangling,ShaanXi712100,China)

Abstract: Traditional methodsof biomedical named entityrecognition（NER）require alarge amountof labeled data in the targetdomain,butthecostoftaggingdata is expensive.Inorder toreduce therequirementoflabeleddata intargetdomain for NER,theproblemofNER in biomedical textsis transformed intoahidden Markovmodelbased on transferlearning.The data sets n the target domain forNER do not ned alarge amountoflbeleddata tolearn a model forthe task bytransferlearning. Withthe helpoflabeleddatainsourcedatasetsacross adifferentbutrelateddomai,andusethe methodofdatagravitationto evaluate thecontributionofsamples in theauxiliarydata setsabout learninga modelforthetarget domain.Andcalculate the weightsof thedatafromthe source domainandthedata fromthe target domain.And then constructthe hiden Markov model algorithm(BioTrHMM)basedonthetransfer learming.The experimentresultson GENIAcorpusshowtheBioTrHMMalgorithm has beter performancethanthe traditional algorithmofhiden Markov model,onlyusessmallamountoflabeleddata intarget domain.

Key Words: Transfer learning; Hidden Markov Model; Named Entity Recognition; Text mining

# 0 引言

传统的生物医学命名实体识别方法往往需要使用大量标注数据集构建模型，从而保证模型的分类预测性能。但是在现实情况中，通常本文感兴趣的领域中可获得的已标注数据很少，缺乏足够大的训练集训练强壮的模型，并且人工标注的代价高昂。迁移学习可以从相关领域数据集中学习知识，辅助学习目标领域的知识，协助解决目标领域的学习问题。利用相关领域的数据，可以大大减少对目标领域已标注数据的需求量，节约标注数据的高昂成本。

本文利用基于实例的迁移学习方法对辅助数据集进行知识迁移，协助解决目标领域的学习问题。为了降低对目标领域已标注数据的需求，算法需要处理如下问题：a）如何在目标领域标注数据较少的情况下得到性能较好的预测模型；b）如何实现跨领域知识迁移，从而辅助目标任务进行学习。本文算法利用数据引力方法评估辅助数据集中样本对目标学习问题的贡献程度，进而对辅助数据集中样本赋予权值，提出了基于样本的迁移学习方法。本文通过修改隐马尔可夫模型的学习算法和分类方法，提出基于权值的隐马尔可夫模型--BioTrHMM算法。

隐马尔可夫模型（HMM)在传统的生物医学命名实体识别中应用非常广泛。比如基于单词相似度平滑技术的HMM命名实体识别分类器[I]、PowerBioNE 生物命名实体识别系统[2]、Zhang 等人[3.4]也指出HMM在生物医学领域中进行命名实体识别的有效性等。这些方法为了获得良好的预测性能，需要大量已标注的样本作为训练数据集来构建预测模型。

迁移学习[5]作为一种解决跨领域知识学习问题的学习方法,在命名实体识别和软件故障预测等领域[6\~10]都有很好的应用。特别是基于实例的迁移学习方法[1l\~14],如nearest neighbour(NN)filter和transfernaiveBayes(TNB)等，通过度量样本对构建模型的贡献大小给样本分配不同的权重，辅助数据样本与目标数据越相似，则对构建分类分析模型起到的作用越大，所以赋予的权值越大[15]。本文采用文献[12]中的数据引力模型来评估辅助数据集中样本数据与目标数据集中样本数据的相似性，计算数据集中每个样本的权值。

本文算法仅需要少量目标领域标注数据，对已有相关但不同标注数据的辅助数据集进行迁移学习，基于辅助数据集和目标领域标注数据集构建预测模型，识别目标领域数据集中的命名实体。本文在GENIA语料库上针对不同角度进行了多组实验，实验结果表明本文提出的BioTrHMM算法在大大减少人工标注样本开销的情况下，比传统的HMM算法具有更好的预测性能。

# 1 问题定义

对于生物医学文本命名实体识别中需要大量的已标注样本，而人力标注开销大的问题，本文针对目标数据集 $D _ { _ t }$ ，以相关但不同领域的数据集 $D _ { s }$ 为辅助数据集，将其转换为迁移学习场景下的 HMM问题。给定训练数据集 $D _ { \iota }$ ， $D _ { \iota } = D _ { \iota } \cup D _ { \iota }$ 。在目标数据集上， $V = ( \nu _ { _ 1 } , \nu _ { _ 2 } , . . . , \nu _ { _ m } )$ 为观测序列， $I = ( i _ { _ 1 } , i _ { _ 2 } , . . . , i _ { _ m } )$ 为 $V$ 对应的词性状态序列。本文的目标是通过对 $D _ { \iota }$ 中的样本赋予权值，完成对 $D _ { s }$ 的知识迁移，得到 $D _ { \iota } \backslash = ( s a m p l e , w )$ ,其中，sample为样本， $w$ 为样本对应的权值。在 $D _ { _ l } ^ { ^ { \prime } }$ 上构建一个 HMM 模型 $f$ ，使得对于给定 $\boldsymbol { V }$ ， $V \in D _ { t - t e s t }$ ， $D _ { _ { t - t e s t } }$ 为与 $D _ { _ t }$ 同分布的目标测试集，有

$$
f ( V ) \to I
$$

即对于给定的观测序列 $\boldsymbol { V }$ ，通过模型 $f ( V )$ 对序列的词性状态进行识别分类，得到该序列所对应的词性状态序列 $I$ ，输出词性状态为实体类型的观测样本，完成命名实体识别。

# 2 BioTrHMM算法

本文提出基于迁移学习的隐马尔可夫模型BioTrHMM算法，在使用较少的目标领域数据的情况下，基于目标数据集和辅助数据集构建模型，对目标数据集进行预测，依然具有较好的性能。本文通过评估辅助数据集中样本对目标学习问题的贡献程度，利用数据引力的方法对样本赋予权值，进行知识迁移，通过修改隐马尔可夫模型的学习算法，得到迁移学习场景下的隐马尔可夫模型。本文的技术路线可分为4个主要步骤：数据集的构建、知识的迁移学习、模型的学习以及预测与评估，如图1所示。其中，图1中的第2部分和第3部分构成本文的BioTrHMM算法，将在下文进行介绍。

# 2.1基于实例的数据迁移

![](images/7f8b8528de13671a4c8831c830201b5e2bb1eb0c0b7d2d064884366be5ee7314.jpg)  
图1BioTrHMM算法模块关系

为了给数据样本赋予权值，本文以辅助数据样本与目标数据样本之间的相似度评估辅助数据集对目标学习问题的贡献程度。

# 2.1.1计算相似度

根据 $D _ { _ t }$ 中的词性和结构信息，计算 $D _ { s }$ 中的样本与 $D _ { \iota }$ 中样本的相似度。本文分别使用单词相似性和编辑距离对 $D _ { s }$ 中的样本数据和 $D _ { \iota }$ 中的样本数据的相似度进行计算。

定义1单词相似性（Similarity）是指两个不同的单词字符串中最大相同字符串的长度。

公式定义如下：

$$
\sin i l a r i t y = \frac { l } { \operatorname* { m a x } l }
$$

其中： $l$ 表示两个单词最大相同字符串长度， $\operatorname* { m a x } l$ 表示两个单词中长单词的字符串长度。

编辑距离（editdistance）是指对于两个字符串，由一个转换成另一个所需的最少编辑操作次数。许可的编辑操作包括将一个字符替换成另一个字符，插入一个字符，删除一个字符。假设字符串 $\mid c \mid$ 和 $d$ 的长度分别为 $y$ 和 $e$ ，则字符串 $\scriptstyle { \begin{array} { l } { c } \end{array} }$ 和 $d$ 的编辑距离 $E D ( e , y )$ 的计算公式[18]为

$$
\begin{array} { r l } & { E D ( 0 , 0 ) = 0 } \\ & { E D ( 0 , y ) = E D ( y , 0 ) = y } \\ & { E D ( e , y ) = } \\ & { \left\{ \begin{array} { l l } { E D ( e - 1 , y - 1 ) \quad \quad \quad c _ { \epsilon } = d , } \\ { \quad 1 + \operatorname* { m i n } ( E D ( e - 1 , y ) , \quad \quad c _ { \epsilon } \neq d _ { * } } \\ { \quad E D ( e , y - 1 ) , \quad \quad } \\ { E D ( e - 1 , y - 1 ) ) \quad \quad } \end{array} \right. } \end{array}
$$

# 2.1.2计算权值

因为命名实体数据的词性类别属于NN（noun，singularor mass：名词，单数；物资名词(不可数名词)）[16]，所以计算$D _ { s }$ 中的词性为 NN 的样本数据与 $D _ { \iota }$ 中实体类型样本数据和词性为NN的样本数据的相似性。设Similarity,或者EditDistan $c e _ { _ p }$ 为 $D _ { s }$ 中样本与 $D _ { _ t }$ 中第 $p$ 个实体类型样本或词性为NN的样本的相似度，则对于目标样本的权值 $W$ 可由式（4）或式（5）计算得到。其中， $m _ { \scriptscriptstyle 1 }$ 和 $m _ { _ 2 }$ 分别为两物体的质量 $\mathcal { K }$ 为常数。

$$
\begin{array} { l } { { { \cal W } _ { _ { p } } = G { \frac { m _ { _ { 1 } } m _ { _ { 2 } } } { r ^ { 2 } } } = G { \frac { K m _ { _ { 1 } } m _ { _ { 2 } } S i m i l a r i t y _ { _ { p } } } { ( 2 - S i m i l a r i t y _ { _ { p } } ) ^ { 2 } } } } } \\  { \propto { \displaystyle { \frac { S i m i l a r i t y _ { _ { p } } } { ( 2 - S i m i l a r i t y _ { _ { p } } ) ^ { 2 } } } } } \end{array}
$$

$$
\begin{array} { l } { { \displaystyle { W _ { _ { p } } = G \frac { m _ { _ { 1 } } m _ { _ { 2 } } } { r ^ { 2 } } = G \frac { K m _ { _ { 1 } } m _ { _ { 2 } } } { ( 1 + E d i t D i s \tan c e _ { _ { p } } ) ^ { 2 } } } } } \\ { { \displaystyle { \propto \frac { 1 } { ( 1 + E d i t D i s \tan c e _ { _ { p } } ) ^ { 2 } } } } } \end{array}
$$

$D _ { s }$ 中每个词性为NN的数据的最终权值为

$$
W = \operatorname * { m a x } ( W _ { p } ) \qquad p = 1 , 2 , \Lambda \ , m
$$

其中： $m$ 为 $D _ { \ t { t } }$ 中实体类型样本数与词性为NN 的样本数之和。

通过上述方法对 $D _ { \iota }$ 中样本赋予权值，得到 $D _ { _ l } ^ { \ \cdot }$ ，并用以构建模型。

# 2.2 BioTrHMM的学习算法

本文使用的基本模型是隐马尔可夫模型，模型参数包括：状态转换概率矩阵 $A$ 、观测概率矩阵 $B$ 和初始状态概率向量 $\pi$ U其中 $A = [ a _ { i j } ] _ { n \times n }$ ,其中 $a _ { _ { i j } }$ 表示在时刻 $t$ 处于状态 $q _ { i }$ 的条件下在时刻 t+1 转移到状态qj的概率P(i=qjl𝑖i=q)，i=1,..,n;$j = 1 , 2 , . . . , n$ 。其中， $Q = \{ q _ { \mathrm { _ 1 } } , q _ { \mathrm { _ 2 } } , \Lambda , q _ { \mathrm { _ n } } \}$ 是所有可能的状态的集合，$n$ 为所有可能的状态数。本文对隐马尔可夫模型的参数 $A$ 和 $\pi$ 进行了修改。传统的模型参数学习方法是使用转换状态的次数计算得到状态转换概率，本文是在迁移学习场景下进行模型参数的学习，故本文中参数 $A$ 的计算方式如下：

$$
a _ { _ i j } = \frac { w _ { _ { i j } } } { w _ { _ { i } } } = \frac { w _ { _ { i j } } } { \displaystyle \sum _ { j = 1 } ^ { n } w _ { _ { i j } } } \ i = 1 , 2 , . . . , n
$$

其中： $\boldsymbol { w } _ { i j }$ 表示状态 $i$ 转移到状态 $j$ 的权值， $w _ { i }$ 表示状态 $i$ 发生转移的权值之和。

$B = [ b _ { _ j } ( k ) ] _ { _ { n \times m } }$ ,其中 $b _ { j } ( k )$ 表示在时刻 $t$ 处于状态 $q _ { j }$ 的条件下生产观测值 $\nu _ { _ k }$ 的概率 $P ( o _ { \mathrm { \Lambda } _ { t } } = \nu _ { \mathrm { \Lambda } _ { k } } \vert i _ { \mathrm { \Lambda } _ { t } } = q _ { \mathrm { \Lambda } _ { j } } )$ ，其中 $k = 1 , 2 , . . . , m$ ·，$j = 1 , 2 , . . . , n \mathrm { ~ . ~ }$

$$
b _ { j } ( k ) = \frac { N _ { _ { j k } } } { N _ { _ { j } } }
$$

其中： ${ N _ { j k } }$ 表示状态 $j$ 的时候观测到 $\nu _ { k }$ 的次数， $N _ { _ j }$ 表示状态$j$ 的时候可能观测到的所以观测值的次数总和。

$\pi = ( \pi _ { i } ) \ , \pi _ { i }$ 是时刻 $t = 1$ 处于状态 $q _ { i }$ 的概率 $P ( i _ { 1 } = q _ { i } )$ ,其中

$$
\pi _ { i } = \frac { w _ { i } } { \displaystyle \sum _ { i = 1 } ^ { n } w _ { i } } ~ i = 1 , 2 , . . . , n
$$

其中， $w _ { i }$ 表示初始状态为 $i$ 的权值。

在 $D _ { _ L } ^ { \phantom { \dagger } }$ 上通过统计的方式学习得到 $\mathbf { \boldsymbol { A } } \cdot \mathbf { \boldsymbol { B } }$ 、 $\pi$ 三个参数，得到模型 $f$ 。

# 2.3 BioTrHMM的分类算法

在 $D _ { _ l } ^ { \ \cdot }$ 上学习得到模型 $f$ 后，本文进一步对维特比算法[13]进行了修改，并使用修改后的维特比算法进行分类分析。本文在 $D _ { _ l } ^ { ^ { \dagger } }$ 上通过样本的权值，计算得到基于权值的状态转换矩阵代替原维特比算法中使用状态出现次数计算状态转换矩阵。在给定模型 $f$ 的情况下，维特比算法可以有效地得到观测序列对应的状态序列，即得到给定观测文本序列对应的词性序列，通过观察对比得到的词性序列，本文可以得到命名实体类型的观测文本，达到命名实体识别的目的。下面给出本文中的预测算法：

在这里定义两个变量 $\delta$ 和 $\psi$ ，定义在时刻 $t$ 状态为 $i$ 的所有单个路径 $( i _ { 1 } , i _ { 2 } , . . . , i _ { t } )$ 中概率最大值为

$$
\begin{array} { r l } & { \delta _ { t } ( i ) = \underset { i _ { 1 } , \dots , i _ { t - 1 } } { \operatorname* { m a x } } P ( i _ { t } = i , i _ { t - 1 } , . . . , i _ { 1 } , \nu _ { t } , . . . , \nu _ { 1 } \Big | \lambda ) } \\ & { \quad \quad = \underset { 1 \leq j \leq N } { \operatorname* { m a x } } [ \delta _ { t } ( j ) a _ { j i } ] b _ { i } ( \nu _ { t + 1 } ) } \\ & { \quad \quad \quad i = 1 , 2 , . . . , N ; t = 1 , 2 , . . . , T - 1 } \end{array}
$$

定义在时刻 $t$ 状态为 $i$ 的所有单个路径 $( i _ { _ 1 } , i _ { _ 2 } , . . . , i _ { _ { t - 1 } } , i _ { _ t } )$ 中概率最大的路径的第 $t \mathrm { - } 1$ 个节点为

$$
\psi _ { \prime } ( i ) = \arg \operatorname* { m a x } _ { \substack { 1 \le j \le N } } [ \delta _ { \scriptscriptstyle { t - 1 } } ( j ) a _ { \scriptscriptstyle { j i } } ] , i = 1 , 2 , . . . , N
$$

具体预测如下:

a）初始化。

$$
\delta _ { \scriptscriptstyle 1 } ( i ) = \pi _ { i } b _ { \scriptscriptstyle i } ( \nu _ { \scriptscriptstyle 1 } ) = \frac { w _ { \scriptscriptstyle i } } { \sum _ { i = 1 } ^ { n } w _ { \scriptscriptstyle i } } b _ { \scriptscriptstyle i } ( \nu _ { \scriptscriptstyle 1 } ) ,
$$

$$
i = 1 , 2 , . . . , n ; \psi _ { 1 } ( i ) = 0 , i = 1 , 2 , . . . , n
$$

首先对与给定观测序列，在时刻 $t { = } 1$ 时计算得到状态为 $i$ 的所有单个路径 $( i _ { \scriptscriptstyle 1 } )$ 中概率最大的路径。由于时刻 $t { = } 1$ 没有前一时刻，所以y(i)=0.,i=1,2..,n。

b）递推。对，t=2....T

$$
\begin{array} { l } { \displaystyle \delta _ { \mathfrak { r } } ( i ) = \underset { 1 \leq j \leq n } { \operatorname* { m a x } } [ \delta _ { \mathfrak { r } - 1 } ( j ) a _ { j i } ] b _ { i } ( \nu _ { \mathfrak { r } } ) } \\ { = \underset { 1 \leq j \leq n } { \operatorname* { m a x } } [ \delta _ { \mathfrak { r } - 1 } ( j ) \frac { w _ { j i } } { \displaystyle \sum _ { i = 1 } ^ { n } w _ { j i } } ] b _ { i } ( \nu _ { \mathfrak { r } } ) , i = 1 , 2 , . . . , n } \end{array}
$$

$$
\begin{array} { r l } & { \psi _ { \prime } ( i ) = \arg \underset { 1 \leq j \leq n } { \operatorname* { m a x } } [ \delta _ { t - 1 } ( j ) a _ { j i } ] } \\ & { = \arg \underset { 1 \leq j \leq n } { \operatorname* { m a x } } [ \delta _ { t - 1 } ( j ) \frac { w _ { j i } } { \displaystyle \sum _ { i = 1 } ^ { n } w _ { j i } } ] , i = 1 , 2 , . . . , n } \end{array}
$$

对时刻 $t = 2 , 3 , . . . , T$ 依次计算得到出现的状态路径中概率最

大的路径，并得到概率最大路径的第t-1个节点。

c）终止。

$$
\begin{array} { l } { P ^ { * } = \underset { { 1 \leq i \leq N } } { \operatorname* { m a x } } \delta _ { { \scriptscriptstyle T } } ( i ) } \\ { i _ { { \scriptscriptstyle T } } ^ { * } = \arg \underset { { 1 \leq i \leq N } } { \operatorname* { m a x } } [ \delta _ { { \scriptscriptstyle T } } ( i ) ] } \end{array}
$$

当时刻 $t = T$ 时，可以计算得到最后一个时刻概率最大路径对应的节点和概率最大路径中前一时刻对应的节点。

d）最优路径回溯，对t=T-1,T-...1

$$
i _ { t } ^ { * } = \psi _ { t + 1 } ( i _ { t + 1 } ^ { * } )
$$

由时刻 $t = T$ 依次回溯到 $t = 1$ 时刻，就可以得到观测序列对应的概率最大路径，即最优路径。最终求得的最优路径，也就是词所对应的词性状态，根据得到的状态序列，输出命名实体类型对应的观测样本，完成命名实体识别。

表1GENIAV3.02 语料库中实体标签分布  

<html><body><table><tr><td>Protein/%</td><td>DNA/%</td><td>RNA/%</td><td>Cell type</td><td>Cell line</td><td>No-entity</td></tr><tr><td></td><td></td><td></td><td>1%</td><td>1%</td><td>1%</td></tr><tr><td>10.45</td><td>3.95</td><td>0.40</td><td>4.00</td><td>1.90</td><td>79.30</td></tr></table></body></html>

表2辅助集中实体标签分布  

<html><body><table><tr><td>DNA/%</td><td>RNA/%</td><td>Cell type/%</td><td>Cell line/%</td><td>No-entity/%</td></tr><tr><td>3.95</td><td>0.40</td><td>4.00</td><td>1.90</td><td>89.75</td></tr></table></body></html>

# 3 实验及结果分析

为了验证BioTrHMM算法的性能，本文在GENIAv3.02语料库上进行了实验。

# 3.1实验设置

为了验证本文的算法对生物医学命名实体识别的预测性能，选取传统的HMM 算法与本文提出的基于迁移学习的BioTrHMM算法进行比较。目前，最常用的生物医学标注语料库是GENIAv3.02语料库，该语料库包含了来自MEDLINE的2000个摘要标注文本（约360000个单词)，并且包含36个词性类别，其中包含5个生物医学实体类型。本文使用了GENIA$\mathbf { v } 3 . 0 2$ 语料库（http://www.nactem.ac.uk/genia/genia-corpus）的数据进行了实验。本文识别的是蛋白质命名实体，采用了精确率、召回率和 $F$ 值[17]作为评价指标。GENIA $\mathbf { v } 3 . 0 2$ 语料库中实体标签分布说明如表1所示。

本文中 $D _ { \ t { t } }$ 是含有蛋白质命名实体标签和其他词性标签的目标集， $D _ { s }$ 是把蛋白质命名实体标签处理为NN类型的辅助集，辅助集中标签分布如表2所示。

本文中设置了三个参数 $\alpha$ $\chi ~ , ~ \beta ~ , ~ \gamma$ 。其中 $\alpha | D _ { t } |$ 表示目标集的大小； $\beta | D _ { s } |$ 表示辅助集的大小； $\gamma$ 表示所用数据集所占GENIA语料库的比例，当使用全部GENIAv3.02语料库时，$\gamma$ 值为1。本文通过对每组实验进行十折交叉验证的方法，确保结果的有效性。

# 3.2实验结果

为了验证BioTrHMM算法的性能，本文分别从不同角度进

行了实验。实验如下：

# 3.2.1针对 $\alpha$ 的实验

本文针对不同的 $\alpha$ 取值分别对BioTrHMM和HMM进行了实验，实验结果如图2所示，实验结果表明同样大小的 $D _ { \iota }$ 下，通过对 $D _ { s }$ 中知识的迁移学习，BioTrHMM算法的识别性能显著优于HMM的识别性能。

![](images/459c3d5cc4ad2686bfac7cb61939991fc06d0c6b64905729b743cc854acb85dc.jpg)  
图2针对 $\alpha$ 的实验

通过对辅助集的学习，BioTrHMM学到了更多对目标任务有贡献的知识，使得学习得到的模型更加健壮。BioTrHMM与HMM有相同的目标集，但是BioTrHMM通过使用现有分布不同的辅助集在不增加人工标注成本的情况下，大大提升了算法的性能。

# 3.2.2针对 $\beta / \alpha$ 的实验

本文为了研究 $D _ { \iota }$ 大小对算法性能的影响，在训练集大小相同情况下，针对不同 $\beta / \alpha$ 进行了实验。本文把 $D _ { _ L }$ 中 $\beta$ 和 $\alpha$ 的数据集大小比例设定为2：1、3：1、4：1和5:1。表3是 $\gamma = 1$ 时的实验结果对比。

尽管随着 $D _ { \ t { t } }$ 数量的减少BioTrHMM算法的性能有所降低，但是仍然与传统的隐马尔可夫模型的预测效果相当。

表3BioTrHMM与HMM实验结果对比  

<html><body><table><tr><td rowspan="2">方法</td><td rowspan="2">β/a</td><td rowspan="2">精确 率</td><td rowspan="2">召回</td><td rowspan="2">F值</td></tr><tr><td>率</td></tr><tr><td>HMM</td><td></td><td>0.6355</td><td>0.5399</td><td>0.5797</td></tr><tr><td rowspan="4">BioTrHMM(Similarity)</td><td>2:1</td><td>0.8955</td><td>0.5201</td><td>0.6519</td></tr><tr><td>3:1</td><td>0.8695</td><td>0.4974</td><td>0.6226</td></tr><tr><td>4:1</td><td>0.8684</td><td>0.4701</td><td>0.6009</td></tr><tr><td>5:1</td><td>0.8822</td><td>0.4578</td><td>0.5848</td></tr><tr><td>BioTrHMM</td><td>2:1</td><td>0.8761</td><td>0.5363</td><td>0.6541</td></tr><tr><td>(EditDistance)</td><td>3:1</td><td>0.8704</td><td>0.4980</td><td>0.6233</td></tr><tr><td></td><td>4:1</td><td>0.8677</td><td>0.4723</td><td>0.6026</td></tr><tr><td></td><td>5:1</td><td>0.8697</td><td>0.4453</td><td>0.5811</td></tr></table></body></html>

# 3.2.3针对γ的实验

为了进一步探讨算法的有效性，本文还分别在不同大小的数据集上进行了实验。本文分别在 $\gamma = 0 . 8$ 和 $\gamma = 0 . 6$ 是进行了实验，实验结果如表4和5所示。实验结果表明，标注的目标数据集的规模对传统的HMM算法的性能具有较大的影响。尽管数据集规模有所减小，但是BioTrHMM算法依然具有良好的预测分类性能。同时，BioTrHMM算法在保证分类分析性能的前提下，有效的降低了对标注目标数据的需求量，减少了人工标注数据的开销。

综上实验结果表明本文提出的BioTrHMM算法通过对跨领域知识的迁移，可以在生物医学蛋白质命名实体标注数据较少的情况下，可以达到较好的分类分析效果。此外，以上实验结果表明相似度度量方法的不同对本文提出的BioTrHMM 算法几乎没用影响。使用不同的相似度度量方法，BioTrHMM算法都可以实现比传统隐马尔可夫模型更好的预测效果。由于HMM与BioTrHMM算法实验使用的训练集和测试集的大小都相同，而BioTrHMM算法算法中训练集是由两部分组成，故在BioTrHMM算法实验中目标集的大小远远小于传统隐马尔可夫模型算法实验中训练集的大小。因此实验结果表明与传统隐马尔可夫模型相比，BioTrHMM算法仅使用其1/3，甚至更少的标注目标集，就可以达到良好的分类分析效果。

表4 $\gamma = 0 . 8$ 实验结果对比  

<html><body><table><tr><td>方法 HMM</td><td>β/a</td><td>精确率</td><td>召回率</td><td>F值</td></tr><tr><td rowspan="5">BioTrHMM (Similarity)</td><td></td><td>0.5591</td><td>0.4561</td><td>0.5024</td></tr><tr><td>2:1</td><td>0.8909</td><td>0.4298</td><td>0.5799</td></tr><tr><td>3:1</td><td>0.9508</td><td>0.3919</td><td>0.5550</td></tr><tr><td>4:1</td><td>0.9828</td><td>0.3851</td><td>0.5534</td></tr><tr><td>5:1</td><td>0.9837</td><td>0.3846</td><td>0.5530</td></tr><tr><td rowspan="4">BioTrHMM (EditDistance)</td><td>2:1</td><td>0.8909</td><td>0.4298</td><td>0.5799</td></tr><tr><td>3:1</td><td>0.9677</td><td>0.4054</td><td>0.5714</td></tr><tr><td>4:1</td><td>0.9661</td><td>0.3851</td><td>0.5507</td></tr><tr><td>5:1</td><td>0.9716</td><td>0.3829</td><td>0.5493</td></tr></table></body></html>

表5 $\gamma = 0 . 6$ 实验结果对比  

<html><body><table><tr><td>方法 HMM</td><td>β/a</td><td>精确率</td><td>召回率</td><td>F值</td></tr><tr><td rowspan="5">BioTrHMM (Similarity)</td><td></td><td>0.5205</td><td>0.4524</td><td>0.4841</td></tr><tr><td>2:1</td><td>0.8780</td><td>0.4286</td><td>0.5760</td></tr><tr><td>3:1</td><td>0.9712</td><td>0.4052</td><td>0.5731</td></tr><tr><td>4:1</td><td>0.9778</td><td>0.3793</td><td>0.5466</td></tr><tr><td>5:1</td><td>0.9837</td><td>0.3707</td><td>0.5385</td></tr><tr><td rowspan="4">BioTrHMM (EditDistance)</td><td>2:1</td><td>0.8810</td><td>0.4405</td><td>0.5873</td></tr><tr><td>3:1</td><td>0.9796</td><td>0.4138</td><td>0.5818</td></tr><tr><td>4:1</td><td>0.9565</td><td>0.3793</td><td>0.5432</td></tr><tr><td>5:1</td><td>0.9773</td><td>0.3707</td><td>0.5375</td></tr></table></body></html>

# 4 结束语

本文针对传统生物医学文本的命名实体识别方法需要大量的标注目标样本，但是现实中标注样本困难的问题，提出了基于迁移学习的隐马尔可夫算法BioTrHMM。算法通过计算辅助集数据集和目标数据集集中样本数据的相似度，根据数据对目标任务贡献的大小，赋予辅助集数据集中样本数据权值，实现基于实例的迁移学习。本文通过对HMM学习算法进行改进，在加权数据集中学习HMM的模型参数，建立迁移学习条件下的预测模型。实验结果表明，BioTrHMM在使用较少目标领域已标注数据的情况下，具有更好的预测性能。本文提出的方法不仅可以用于生物医学文本的命名实体识别中，同时可以推广到文本挖掘的命名实体识别当中。

在部分本文仅对HMM算法进行了改进，很多研究表明条件随机场在命名实体识别中比HMM 具有更好的识别性能[1920]。基于此研究成果和研究现状，未来工作考虑将在条件随机场基础上对命名实体识别进行迁移学习，从而提升对命名实体的识别性能。

# 参考文献：

[1]Horn H, Schoof E M,Kim J,et al, KinomeXplorer: an integrated platform for kinome biology studies [J].Nature Methods,2014,11(6),603-604.   
[2]Srinivasagan K G,Suganthi S,Jeyashenbagavalli N.NER for Hindi language using association rules [C]// Proc of International Conference on Data Mining and Intelligent Computing. 2014.   
[3]Gayen V, Sarkar K.An HMM based named entity recognition system for Indian languages: The JU System at ICON [R].Published in ArXiv, 2013.   
[4]Armold A,Nallapati R,Cohen W W, et al.Exploiting feature hierarchy for transfer learning in named entity recognition [C]/ Proc of the 46th Annual Meeting of the Association for Computational Linguistics.20o8,245-253.   
[5]Pan Jialin, Yang Qiang.A survey on transfer learning[J],IEEE Trans on Knowledge and Data Englineeging,2010,22 (10): 1345-1359.   
[6]Liu Jie,Yu Kai,Zhang Yi,et al, Training conditional random fieldusing transfer learning for gesture recognition [C]// Proc of IEEE International Conference on Data Mining.2010.   
[7]Magimai-Doss M,Rasipuram,Aradilla G,et al. Grapheme-based automatic speech recognition using KL-HMM[C]// Proc of InterSpeech. 2011.   
[8]Cui Xiaodong, Huang Jing, Chien JT.Multi-view and multi-objective semisupervised learning for HMM-based automatic speech recognition [J]. IEEE Trans on Audio,Speech,and Language Processing,2012,20(7):1923-1935.   
[9]Hu Hao, Zheng Wenchen, Yang Qiang,Cross-domain activity recognition via transfer learning[J].Pervasive and Mobile Computing,2011,7(3): 344- 358.   
[10] Cook D,Feuz K D,Narayanan C,et al,Transfer learning for activity recognition: asurvey[J]. Knowledge ofInformation System.2010,36: 537- 556.   
[11] Pan Jialin,Toh Zhiqiang et al. Transfer joint embedding for cross-domain named entity recognition [J].ACM Trans on Informaition Systems,2013,31 (2): Article 7.   
[12] Ma Ying,Luo Guangchun,Zeng Xue,et al,Transfer learning for crosscompany software defect prediction [J]. Information and Software Technology,2012,54: 248-256.   
[13] Rabiner L, Juang B,An introduction to hidden Markov models [J]. IEEE ASSPMagazine,1986.   
[14]庄福振，罗平，何清，等，迁移学习研究进展[J].软件学报,2015,26 (1): 26-39.].   
[15] Bui Q C,Katrenko S,Sloot P MA.A hybrid approach to extract proteinprotein interactions [J].Bioinformatics,2011,27(2):259-265.   
[16]Huang Yuanhua,Xu Bosen, Zhou Xueya,et al. Systematic characterization and prediction of post-translational modification cross-talk[J],Molecular & Cellular Proteomics,2015,14(3):761-770.   
[17]张阳，李建良，胡正国.NewsGrouper：一个自动抽取重要新闻的软件 工具，计算机工程,2002,28(4):83-84.   
[18] Teixeira,J, Sarmento L,Oliveira E.A bootstrapping approach for training a NER with conditional random fields [C]// Portuguese Conference on Artificial Intelligence.Berlin: Springer, 2011.   
[19]Konkol M,Konop'ik M.CRF-based Czech named entity recognizer and consolidation of Czech NER research [J].Berlin:Springer-Verlag,2013: 153-160.