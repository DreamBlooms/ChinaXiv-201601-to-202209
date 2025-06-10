# 维语网页中n-gram模型结合类不平衡SVM的不良文本过滤方法

如先姑力·阿布都热西提1，亚森·艾则孜1，郭文强²(1．新疆警察学院 信息安全工程系，乌鲁木齐 830013;2.新疆财经大学 计算机科学与工程学院，乌鲁木齐 830013)

摘要：随着新疆地区网络的建设发展，产生了大量维吾尔语网页。为了构建健康网络环境，提出了一种结合n-gram统计模型和类不平衡支持向量机(SVM)分类器的维语文本过滤方法。首先，将网页文本进行预处理操作，通过n-gram统计模型来初步提取词干；然后，对词干进行语义分析，将具有相似含义的词干聚合为一类，以此降低词干维度；最后，在传统SVM中引入一个控制超平面之间距离的参数，构建一种类不平衡 SVM，使其能够很好地分类具有非线性不可分和不平衡性的维吾尔语文本。实验结果表明，该方法能够准确分类出不良文本，且具有较短的分类时间。

关键词：维吾尔语网页；不良文本过滤；n-gram词干提取；类不平衡SVM 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.07.0410

# Reactionary text filtering method based on $n$ -gram and class-unbalanced SVM for uyghur webpages

Ruxianguli· Abudurexiti1, Yasen Aizezil†, Guo Wenqiang² (1.Dept.of InformationSecurityEngineering XinjiangPoliceColege,Urumqi83013,China;2.SchoolofComputerScience & Engineering Xinjiang University of Finance & Economic, Urumqi 83oo13, China)

Abstract:Along with theconstructionanddevelopmentof thenetworkin Xinjiang,alarge numberof Uyghurwebpages have been produced. In order to construct a healthy network environment,this paper proposed a Uyghur text filtering method combining n-gramstatisticalmodelandclass-unbalancedsupportvectormachne(SVM)classifier.Firstly,itpreprocssedthe webpage text,andextractedthesteminitiallybytheN-gramstatisticalmodel.Then,itcarriedoutthesemanticanalysisofthe stems,andaggregated thestems with similar meanings intooneclass,therebyreducing the stem dimension.Finall,it introduced a parameter thatcontrolsthe distance between hyperplanes inthetraditional SVM，andconstructeda class-unbalanced SVMto classify Uyghur texts with nonlinear indivisibilityand imbalance.The experimentalresultsshow that the method can accurately classify bad texts and has a shorter classfication time.

Key words: Uyghur webpage; reactionary text filtering; n-gram stem extraction; class-unbalanced SVM

# 0 引言

由于互联网的迅速发展和普及，产生了大量不同类型的短文本，例如网页论坛、推文、新闻提要、书籍、电影概要等。对短文本进行分类对于网络信息过滤非常重要[1]，将分类为存在毒品、色情等不健康文本进行过滤能够净化网络环境，有助于维护社会稳定。短文本通常是非结构化的，并采用简短对话的形式，由多个短句组成。由于短文本具有稀疏特征向量和类别不平衡性，因此不能使用传统分类技术来对其进行高准确性分类[2.3]。不平衡数据集是指其中不同类别的样本数量不均。一个包含很多样本的类被称为“多数类”，相反，包含很少样本的类被称为“少数类”。在对不平衡数据集进行分类时，分类器往往对多数类达到较高准确性，但对少数类的准确率较低[4]。

近些年，随着新疆经济和教育的发展，产生了很多维吾尔语网站。对维语网站中的不良文本信息进行过滤对新疆的稳定和健康发展具有重要意义。目前，对于维吾尔语文本的分类和过滤方法研究较少，主要为新疆大学。例如，文献[5]通过使用纯粹的统计学方法，仅依赖于单词的N-gram 来进行分类。文献[6]中应用了一种监督方法，使用最大熵分类器将文档分类为已知类别，以及使用一种无监督学习方法，将未标记文档进行分组，其特征向量由原始单词和其N-gram 组成。文献[7]中使用了一种K最近邻（KNN）分类器，并结合了三种不同的距离度量（余弦，欧氏和Jaccard)。文献[8]提出使用 $\chi ^ { 2 }$ 方法进行特征提取，并采用了支持向量机（supportvectormachine，SVM)作为分类器。使用 $\chi ^ { 2 }$ 统计来选择特征，如果特征和类是独立的，则 $\chi ^ { 2 }$ 的值为零。这种方法具有较高的特征维数空间，因为文档空间矢量是稀疏的，很少有特征是不相关的。

另外，对于不平衡数据集的分类，传统SVM并不能得到很好的结果。为此，一些学者对其进行了改进，例如，文献[9]对SVM中多数和少数类使用不同的损失函数（即使用L2范数的平方而不是 $\mathrm { L } _ { 1 }$ 范数)，来惩罚少数数据样本的错误分类。文献[10]试图通过向少数类样本的支持向量中引入校正因子来校正分类器学习的偏移，以减少SVM模型的偏差。文献[11]中提出模糊支持向量机（FSVM）作为学习工具。这些技术需要微调用户定义的参数，具有高度复杂性。文献[12]中采用了少类样本合成过采样技术（SMOTE)，是一种较新的非均衡数据集学习办法，通过对少数类样本的人工合成来提高其比例，以平衡样本之间的差异。但是，SMOTE需要对许多用户定义的参数进行微调，获得一组合适参数较为困难。文献[13]中提出了一种称为MINSVM的改进型SVM方法，其通过删减一部分多数类样本，并为少数类样本提供更大的权重，使它们比多数类更受关注，致使产生的超平面应尽可能地接近多数类别。然而，其删减样本的操作一定程度上必然会影响学习效果。

为此，本文结合了n-gram统计模型和类不平衡SVM分类器，提出了一个新的框架来分类网页中的短维吾尔语文本。实验结果表明了提出方法能够有效的分类不良文本，为网页不良信息过滤提供了良好基础。

# 1 提出的文本过滤框架

维吾尔语是以阿拉伯字母为基础的文字，具有高度的黏着性。维吾尔字母共有32个，字母的形式具有多样性，通常包含4 种表现形式，致使其形态变化较为复杂。维吾尔语单词由词干和词缀组成，在同一词干前后添加不同的词缀可以表示不同的词义[14]。由于这些特征，给维吾尔语文本信息处理造成一定的困难，如特征维数大[15]。

所提出的框架由文本处理和分类器两部分组成。图1显示了该方法的工作流程。首先，将数字文本保存在UTF-8 格式的文本文件中。然后进行文本处理，将原始文本转换为特征向量表示。最后，采用提出的改进型SVM分类器（CUB-SVM)，训练该分类器以建立一个分类模型，用于分类测试样本。

本文方法的其主要创新点为：a)考虑到维吾尔语的特性，本文采用了N-gram 统计模型进行词干提取，同时采用了一种语义相似性方法来进一步归类词干，减少文本的特征数量和稀疏性;b)为了提高对不平衡数据的分类精度，本文在传统SVM基础上开发了一种改进型SVM。

# 2 文本预处理与向量表示

通过应用传统技术来分类短文本会产生大量和稀疏的特征向量，从而导致分类器的性能较差。在这项研究中，本文提出一种基于词干的特征约简方法，在文本转换为特征向量之前，应用多个预处理步骤来减少特征向量的稀疏性。这种方法可以分五个阶段来描述，如图2所示。

![](images/b01ca32784e106f5678d02c9c78ff79491bf2028bbe91d616bd0e610a291f181.jpg)  
图1所提出方法的流程图  
图2文本处理与向量表示流程图

LCcaC\`{ruCEC·cE文本 Eco cELccE..Gil.deEcELuyCCECECE分词 CELEcE.kwEEEECoCEcEC无用词过滤CE. EoWLELEC  
N-gram词干提取 cl.κい²ckcckyedoRoot1: (Root8-Root10)Root2:(Root5)语义分组 Root3: (Root6 - Ro0t10)Root5:(Root2)RootR:(Root15-Root30-TextO:F1F2F3. ...FFClassText1:120....023C1Text2.:0.11.....001 C2  
文本特征向量表示 Text3:2.3......020 C2Text4:111 .101 C2TextN:401 .201 C2

1）词语分割首先，使用斯坦福分词器[16对原始文本进行分词，将介词和代词从原词中分离出来，并分隔任何标点符号。

# 2）无用词过滤

文本无用词过滤过程包括删除停止词、代词、数字、标点和其他非维吾尔语符号。这些部分只会增加特征向量的大小，对区分文本没有帮助。

# 3）词干提取

维吾尔语是一种以词干为主的语言，这意味着几乎每一个词都是其自身的根源，或者源于三个字母或四个字母的根。从同一根派生的词具有相似的含义，因此可以根据它们的根分组。因此，词干可以被认为是一个特征，从而减少特征向量的长度。

采用更适合维吾尔语环境的统计方法来提取词干。所采用的统计方法为 $\mathbf { n }$ -gram 统计模型[17]。在字母层上进行单词切分，即将连续 $N$ 个字母作为一个 gram 单元。 $\mathfrak { n }$ -gram 模型中，对于文本中一个不良字母 $l _ { i }$ ，设定其出现的概率与前面 $N { - } 1$ 个字母的出现情况相关。因此，字母序列 $L = l _ { 1 } l _ { 2 } l _ { 3 } , . . . , l _ { N }$ 出现的概率为：

$$
P ( L ) = P ( l _ { 1 } l _ { 2 } l _ { 3 } , . . . , l _ { N } ) = \prod _ { i = 1 } ^ { N } P ( l _ { i } \mid l _ { i - N + 1 } , . . . , l _ { i - 1 } )
$$

N-gram模型中 $N$ 的设定需要结合具体的语言环境，对于维吾尔语，由于其每个单词都由多个字母结合而成，为此较小的 $N$ 不能有效地代表单词属性，而 $N$ 较大如等于3或4时，则具有较强的代表性。

本文利用n-gram统计模型提取词干过程中，为了降低单词维度和冗余度，首先根据维吾尔语词典，删除了单词中最常见的词缀。然后，计算两个词语的相似度[18]，以此来提取词干。

为了展示 $\mathfrak { n }$ -gram 统计模型提取词语的过程，列举了一个$\Nu { = } 2$ 时的例子，即计算两个词 $\yen 123,456$ （教育）和 $\ r _ { s } \approx s t 0$ (教育的）的相似度。

$1 . \mu  3 ^ { \ell \downarrow } \mu \Rightarrow \mu  \mu  3$ .。（首先将词分解为 $\Nu { = } 2$ 字母组合单元）

2.去除常用词缀的两字母组合 $\Rightarrow \forall \cdots \pmb { \mathscr { s } } _ { \pmb { \mathscr { s } } } ,$ .L。

$$
3 . \because 1 4 6 \Rightarrow \forall 6 5 < 4 6 < 4 0
$$

4.去除常用词缀的两字母组合 $\Rightarrow \forall \cdots \leq s _ { 1 } \leq 1 , L _ { 0 }$ ：

那么，这两个单词的相似性为： $S { = } \frac { 2 C } { A + B } { = } \frac { 2 { \times } 3 } { 4 { + } 3 } { = } 0 . 8 5 7 1$ 。其中， $A$ 表示第一个单词中所包含的且第二个单词中不存在的字母组合的数量；同样， $B$ 第二个单词中所包含的且第一个单词中不存在的字母组合的数量； $c$ 表示两个词中都包含的相同字母组合的数量。若两个单词的相似性大于设定的阈值，则将这两个词合并为一个词干。

# 4）词义分组

词干有助于将单词与属于同一词干的单词进行分组，但是一些具有相似含义的单词不共享相同的词干。因此本文使用语义方法按以下方式对具有相似含义的词干进行分组。

首先，将来自数据集的每个词干作为查询词，根据同义词词典返回包含该词干的同义词。然后，从文本源中提取同义词并存储在包含词干和其同义词的列表中。最后，将列表中的词干一起比较。如果一个词干与另一个词干共享一个同义词，则这些词干被认为具有相似的含义并被分组在一起。如果一个词干与已在组中的词干共享同义词，则新的词干将添加到现有组中。该过程仅执行一次迭代，这意味着所得到的组不会再聚合在一起。

图3展示了语义分组阶段的过程。到这个阶段结束时，具有相似含义的词干被分组在一起，并且可以被认为是一个特征。

![](images/33e35ba73eda89764fd04c0e6d0a07b9e2f7f8508c5c317ee16898e080c12598.jpg)  
图3词义分组示例

5）特征向量构建

在这个阶段，根据获得的词干特征，为数据集中的每个文本构建特征向量，并且整个数据集可以以表格形式呈现。

# 3 提出的改进型SVM文本分类器

# 3.1传统 SVM分类器

SVM分类器是一种基于统计学的机器学习方法，其基本思想就是通过一个非线性映射，将数据映射到高维特征空间，然后执行线性回归。

设定输入一个数据集 $G = \left\{ ( x _ { i } , y _ { i } ) \right\} _ { i = 1 } ^ { n }$ ， $x \in R ^ { n }$ 为输入特征向量， $y$ 为期望输出值。对于二分类问题，SVM的映射函数表示为：

$$
y = w \phi ( x ) + b
$$

其中： $\phi ( x )$ 表示将数据映射到高维空间，参数 $w$ 和 $b$ 的值是通过最小化下式来近似获得：

$$
R _ { S V M } \left( c \right) = \left( c / n \right) \sum _ { i = 1 } ^ { n } L _ { \varepsilon } \left[ y _ { i } , w \phi ( x _ { i } ) + b \right] + \left\| w \right\| ^ { 2 } \big / 2
$$

为了方便计算，引入两个松弛变量 $\xi _ { i } ^ { + }$ 和 $\xi _ { i } ^ { - }$ ，那么就变成通过最小化下式来估计参数值：

$$
R _ { S V M } ( w , \xi _ { i } ^ { + } ) = c \sum _ { i = 1 } ^ { n } ( \xi _ { i } ^ { + } + \xi _ { i } ^ { - } ) + \left\| w \right\| ^ { 2 } / 2
$$

其中：满足以下条件：

$$
w \phi ( x _ { i } ) + b _ { i } - y _ { i } \leq \varepsilon + \xi _ { i } ^ { + }
$$

$$
y _ { i } - w \phi ( x _ { i } ) - b _ { i } \leq \varepsilon + \xi _ { i } ^ { - }
$$

# 3.2改进的类不平衡 SVM(CUB-SVM)

在这项工作中，为了使SVM能够很好地处理具有非线性不可分和不平衡性的维吾尔语文本，本文扩展了传统SVM分类器，形成类不平衡SVM(CUB-SVM)。

除了将内核集成到SVM之外，本文引入了一个新的参数$\boldsymbol { \tau } _ { \mathrm { i } }$ 。它将多数数据样本与分离超平面之间的距离最小化，并将少数数据样本与分离超平面之间的距离最大化，如图4所示。CUB-SVM的目标公式为

$$
\operatorname* { m i n } _ { \boldsymbol { w } } \left\{ \begin{array} { l } { \displaystyle \frac { 1 } { 2 } | | \mathbf { \nabla } \boldsymbol { w } | | ^ { 2 } + C ^ { + } \sum _ { \{ i | \boldsymbol { y } _ { i } = + 1 \} } ^ { N _ { 1 } } \xi _ { i } ^ { + } + C ^ { - } \sum _ { \{ i | \boldsymbol { y } _ { i } = - 1 \} } ^ { N _ { 2 } } \xi _ { i } ^ { - } } \\ { \displaystyle \qquad + D ^ { + } \sum _ { \{ i | \boldsymbol { y } _ { i } = + 1 \} } ^ { N _ { 1 } } \tau _ { i } ^ { + } - D ^ { - } \sum _ { \{ i | \boldsymbol { y } _ { i } = - 1 \} } ^ { N _ { 2 } } \tau _ { i } ^ { - } } \end{array} \right\}
$$

满足：

$$
w ^ { T } \phi ( x _ { i } ) + b \geq \tau _ { i } ^ { + } - \xi _ { i } ^ { + } f o r x _ { i } { : } y _ { i } = + 1
$$

$$
w ^ { T } \phi ( x _ { i } ) + b \leq - \tau _ { i } ^ { - } - \xi _ { i } ^ { - } f o r x _ { i } { : } y _ { i } = - 1
$$

$$
\tau _ { i } ^ { + } , \xi _ { i } ^ { + } , \tau _ { i } ^ { - } , \xi _ { i } ^ { - } \geq 0 f o r \forall x _ { i }
$$

其中：下标 $" + "$ 代表多数类别，“-”代表少数类别，并且C+,C,D,D-为比例参数。

那么，该问题的拉格朗日方程为

$$
\begin{array} { l } { { \displaystyle { \mathcal { L } } _ { p } = \frac { 1 } { 2 } \| { \mathbf \Lambda } _ { w } \| ^ { 2 } + C ^ { + } \sum _ { i = 1 } ^ { N _ { 1 } } \xi _ { i } ^ { + * } + C ^ { - } \sum _ { ( i ) = - 1 } ^ { N _ { 2 } } \xi _ { i } ^ { - * } + D ^ { + } \sum _ { ( i ) = + 1 } ^ { N _ { 1 } } \tau _ { i } ^ { + * } } } \\ { { \displaystyle ~ - D ^ { - } \sum _ { ( i ) _ { 1 } = - 1 } ^ { N _ { 2 } } \tau _ { i } ^ { - } - \sum _ { ( i ) = + 1 } ^ { N _ { 1 } } \lambda _ { 2 } [ w ^ { T } \phi ( { x } _ { i } ) + b - \tau _ { i } ^ { + } + \xi _ { i } ^ { + } ] + } } \\ { { \displaystyle ~ \sum _ { ( i ) _ { i } = - 1 } ^ { N _ { 2 } } \mu _ { [ i } \mathbf { \Lambda } ^ { \prime } \phi ( { x } _ { i } ) + b + \tau _ { i } ^ { - } + \xi _ { i } ^ { - } ] - \sum _ { ( i ) _ { i } = + 1 } ^ { N _ { 1 } } \alpha _ { i } \xi _ { i } ^ { + * } - } } \\ { { \displaystyle ~ \sum _ { ( i ) _ { i } = - 1 } ^ { N _ { 2 } } \beta _ { i } \xi _ { i } ^ { - } - \sum _ { ( i ) _ { i } = + 1 } ^ { N _ { 1 } } \gamma _ { i } ^ { \prime \prime } _ { i } ^ { + } - \sum _ { ( i ) _ { i } = - 1 } ^ { N _ { 2 } } \delta _ { i } \tau _ { i } ^ { - } } } \end{array}
$$

其中： $\lambda _ { i } , \mu _ { i } , \alpha _ { i } , \beta _ { i } , \gamma _ { i } , \delta _ { i }$ 为拉格朗日乘子。通过找到 KKT 条件并代入拉格朗日函数，本文可以得到一个双重问题，表示为。

$$
\begin{array} { r }  \underset { \lambda , \mu } { \operatorname* { m a x } } \left\{ \begin{array} { l }  \underset { \{ i \} _ { i } = + 1 \} { \overset { N _ { 1 } } { \sum } } \underset { \{ j \} _ { j } = - 1 } { \overset { N _ { 2 } } { \sum } } \lambda _ { i } \mu _ { j } \phi ( x _ { i } ) \phi ( x _ { j } ) } \\  - \frac { 1 } { 2 } \underset  \{ i \} _ { i } = + 1 \} { \overset { N _ { 1 } } { \sum } } \underset { \{ j \} _ { j } = + 1 \} { \overset { N _ { 1 } } { \sum } } \lambda _ { i } \lambda _ { j } \phi ( x _ { i } ) \phi ( x _ { j } ) \Biggr \} } \\ { - \frac { 1 } { 2 } \underset { \{ i \} _ { i } = - 1 \} { \overset { N _ { 2 } } { \sum } } \underset { \{ j \} _ { j } = - 1 } { \overset { N _ { 2 } } { \sum } } \mu _ { i } \mu _ { j } \phi ( x _ { i } ) \phi ( x _ { j } ) \Biggr \} } \end{array} \right. } \end{array}
$$

满足：

$$
\begin{array} { c } { { \displaystyle \sum _ { \{ i | v _ { i } = + 1 \} } ^ { N _ { 1 } } \lambda _ { i } - \sum _ { \{ i | v _ { i } = - 1 \} } ^ { N _ { 2 } } \mu _ { i } = 0 } } \\ { { 0 \le \lambda _ { i } \le C ^ { + } } } \\ { { \mu _ { i } \ge D ^ { - } } } \end{array}
$$

使用 $K ( x _ { i } , x _ { j } ) = \phi ( x _ { i } ) \phi ( x _ { j } )$ ，那么CUB-SVM可以表示为

$$
\operatorname* { m a x } _ { \lambda , \mu } \left\{ \begin{array} { l }  { \displaystyle \sum _ { \{ i \} _ { \nu } = + 1 \} ^ { N _ { 1 } } \sum _ { i \neq j } ^ { N _ { 2 } } \lambda _ { i } \mu _ { j } K ( x _ { i } , x _ { j } ) } } \\ { { } } \\   \displaystyle - \frac { 1 } { 2 } \sum _ { \{ i \} _ { \nu } = + 1 \} ^ { N _ { 1 } } \sum _ { \{ j \} _ { j } = + 1 \} ^ { N _ { 1 } } \lambda _ { i } \lambda _ { j } K ( x _ { i } , x _ { j } ) } } \\ { { } } \\   \displaystyle - \frac { 1 } { 2 } \sum _ { \{ i \} _ { \nu } = - 1 \} ^ { N _ { 2 } } \sum _ { \{ j \} _ { j } = - 1 \} ^ { N _ { 2 } } \mu _ { i } \mu _ { j } K ( x _ { i } , x _ { j } ) } } \end{array} \right\}
$$

满足

$$
\sum _ { \{ i | y _ { i } = + 1 \} } ^ { N _ { 1 } } \lambda _ { i } - \sum _ { \{ i | y _ { i } = - 1 \} } ^ { N _ { 2 } } \mu _ { i } = 0
$$

$$
0 \leq \lambda _ { i } \leq C ^ { + }
$$

$$
\mu _ { i } \geq D ^ { - }
$$

在解决 $\lambda _ { i } , \mu _ { i }$ 的这个问题后，本文可以找到分离超平面，其中：

$$
w = \sum _ { \{ i | y _ { i } = + 1 \} } ^ { N _ { 1 } } \lambda _ { i } \phi ( x _ { i } ) - \sum _ { \{ i | y _ { i } = - 1 \} } ^ { N _ { 2 } } \mu _ { i } \phi ( x _ { i } )
$$

并且，分类器的公式变为

$$
f ( x ) = s i g n ( \sum _ { \{ i | { v _ { i } = + 1 } \} } ^ { N _ { 1 } } \lambda _ { i } K ( x , x _ { i } ) - \sum _ { \{ i | { v _ { i } = - 1 } \} } ^ { N _ { 2 } } \mu _ { i } K ( x , x _ { i } ) + b )
$$

![](images/6777cc31bd9aa35a84d7af6332041f35e58d4eee29674ecddc1064b493530648.jpg)  
图4CUB-SVM超平面和余量

# 4 实验及分析

# 4.1实验设置

为了测试网页文本中的各种不良主题，从各种维吾尔文网站论坛上收集了500 篇文本，分为4大类：(1)毒品类的文本，数量为143篇；(2)色情类的文本，数量为78篇；(3)赌博类的文本，数量为107篇；(4)正常文本，数量为172篇。这些文本及其类别具有不平衡性，文本集的字符长度统计如表1所示。

表1文本数据集的属性  

<html><body><table><tr><td></td><td>最小值</td><td>最大值</td><td>均值</td><td>标准差</td></tr><tr><td>字符数</td><td>91</td><td>2030</td><td>834</td><td>484</td></tr><tr><td>单词数</td><td>25</td><td>460</td><td>195</td><td>113</td></tr></table></body></html>

另外，在具有Intel酷睿 $\mathrm { I 5 } ~ 5 2 5 0 @ 2 . 7 \mathrm { G H z } \mathrm { \bf C }$ PU，24GB内存和Windows764位PC机上，通过使用MATLABR2013b和CVX2.1工具箱实现本文方法。

# 4.2性能指标

对数据集进行五重交叉验证。为了测量分类器的性能，使用了三个度量标准，其中设定TP表示正确分类的阳性样本，

FP表示错误分类的阳性样本，TN表示正确分类的阴性样本，FN表示错误分类的阴性样本。

a)准确性度量(Accuracy)，用于评估分类器正确分类的性能，表示如下。

$$
A c c u r a c y = { \frac { T P + T N } { T P + T N + F P + F N } }
$$

$\mathbf { b } ) F$ -measure度量，用于评估分类器的整体性能。其中，$F$ -measure 由精确性(Precision)和召回率(Recall)计算而来，分别表示如下：

$$
P r e c i s i o n = \frac { T P } { T P + F P }
$$

$$
R e c a l l = \frac { T N } { T N + F N }
$$

$$
F \ – M e a s u r e = 2 \times ( \frac { P r e c i s i o n \times R e c a l l } { P r e c i s i o n + R e c a l l } )
$$

c)AUC面积。感受性曲线(ROC)是以真阳性率和假阳性率为坐标的曲线，曲线与X 坐标轴之间的面积则为AUC面积，取值为0.5到1之间，用来反映分类器的效果。其值越大说明分类效果越好。

# 4.3 分类结果分析

首先，本文分析了预处理阶段的效果。在传统文本处理方法中，直接将词语作为特征而不进行过滤和词干化。对于本文采用的维吾尔语文本数据集，传统方法会产生长度为6204的特征向量。而本文方法经过词干提取和语义分组后，所获得特征向量长度为1163，缩小了近5.3倍。

为了评估本文CUB-SVM的性能，将其与标准SVM、文献[13]提出的 MINSVM 和文献[12]提出的 SMOTE-SVM 进行比较，以突出不同改进型分类方法之间的区别。表2给出了各种方法在数据集上的性能平均值。图3给出了各种方法的ROC曲线。

表2各分类器的平均分类结果  

<html><body><table><tr><td>分类器</td><td>准确性(%)精度(%)召回率(%)F-度量AUC 面积</td></tr><tr><td>本文CUB-SVM 0.92</td><td>0.87 0.89 0.88 0.94</td></tr><tr><td></td><td></td></tr><tr><td>SVM 0.83</td><td>0.73 0.80 0.76 0.83</td></tr><tr><td>MINSVM 0.87 0.81</td><td>0.85 0.83 0.87 0.89 0.84 0.86 0.85 0.91</td></tr></table></body></html>

![](images/156df687f84f3807572714236a5d9a8186637ee14bb86bc75d1913852741814a.jpg)  
图3各种分类方法的ROC曲线

可以看出，本文CUB-SVM分类器优于传统SVM和一些改进 SVM分类器，其中 $F .$ -measure 比传统SVM提高了 $16 \%$ 。这是因为，本文方法中的预处理过程可以有效降低数据维度，且提出的CUB-SVM能够很好地对不平衡短文本进行分类。

对于SMOTE和MINSVM方法，数据重采样技术并不能提高 SVM分类器的性能，这是因为其通过改变数据的分布可能导致更多的异常值来降低SVM的性能。另外，具有不同成本函数的SVM确实提高了分类器的精确性，但是这种改进是以降低召回率为代价的，这导致较低的F-measure值和整体准确度。

另外，表3给出了各种分类器的分类时间，其中为了公平比较，维吾尔语文本数据的预处理中，都采用了本文提出的过滤和词干提取步骤。可以看出，SMOTE-SVM具有最高的运行时间，因为它需要对数据执行过采样，这非常耗时且导致产生更多的数据。MINSVM具有最低的处理时间，因为它随机删除部分数据样本，这导致数据集更小，因此处理时间更短。本文CUB-SVM分类器的处理时间比标准SVM分类器稍长，但并没有明显增加开销。

表3各种分类器的分类时间  

<html><body><table><tr><td>分类器</td><td>本文CUB-SVM</td><td>SVM</td><td>MINSVM</td><td>SMOTE-SVM</td></tr><tr><td>分类时间(s)</td><td>21</td><td>16</td><td>43</td><td>58</td></tr></table></body></html>

# 4.4统计分析

统计分析用于测试分类器之间准确度差异的显著性。给定两个分类器，统计测试分类器是否具有相同的期望错误率。为了进行统计分析，本文采用了 $\mathrm { ~  ~ K ~ }$ 折交叉验证实验。

K 折交叉验证中，从原始数据集中获得K个训练/测试集合对。分类器在训练集 $t r a i n _ { i }$ 上训练并在测试集 $t e s t _ { i }$ 上测试。训练和测试集上分类器的误差率分别表示为pi,p²，i=1,2,..,K。

如果分类器具有相同的错误率，则它们应该具有相同的均值，即它们的平均值的差值应该等于0。对于K交叉验证测试，第 $i$ 个错误率的差异为 $p _ { i } = p _ { i } ^ { 1 } - p _ { i } ^ { 2 }$ ，为此可得到一个包含K点的 $p _ { i }$ 分布。假设 $p _ { i } ^ { 1 }$ 和 $p _ { i } ^ { 2 }$ 都是正态分布的，那么它们的差异 $p _ { i }$ 也是正态分布的。

假设 $H _ { 0 }$ 为这种分布具有正常的零均值。

$$
H _ { 0 } ; \mu = 0 , \qquad H _ { 1 } ; \mu \ne 0
$$

$$
L e t : S = \frac { \sum _ { i = 1 } ^ { K } p _ { i } } { K } , S ^ { 2 } = \frac { \sum _ { i = 1 } ^ { K } ( p _ { i } - m ) ^ { 2 } } { K - 1 }
$$

在 $\scriptstyle \mu = 0$ 的零假设下，有一个符合 $\mathbf { t } -$ 分布的自由度为 $\scriptstyle { K - 1 }$ 的统计量： $\frac { \sqrt { K } . m } { S } \sim t _ { k - 1 }$ （20

如果该值在范围 $( - t _ { \alpha / 2 , K - 1 } , - t _ { \alpha / 2 , K - 1 } )$ 之外，则测试拒绝在显著性水平 $\alpha$ 上的假设。当 $\alpha = 0 . 1$ 时，置信水平为 $90 \%$ ，范围为（-2.132，2.132)。

测试的错误率以及整体错误率的统计分析结果如表4所示。由于数据集具有不平衡性，有些类别的样本数量较少。统计结果可以看出，所有测试均拒绝少数类别的假设。对于多数类别来说，假设在两个数据集上被拒绝并在其他三个数据集上被接受，这意味着两个数据集中的错误率在其他分类器上存在差异，但在其他三个数据集上没有差异。至于整体错误率，所有数据都接受假设，这意味着整体错误率没有差异。总之，本文CUB-SVM分类器在少数类别上具有较好的准确性，同时不会牺牲整体的准确性，这说明了本文分类器能够很好地处理不平衡数据。

表4分类器成对统计分析的分数  

<html><body><table><tr><td>分类器对</td><td>多数类分数</td><td>少数类分数</td><td>总体分数</td></tr><tr><td rowspan="2">CUB-SVMvs.SVM</td><td>0.561</td><td>-2.953</td><td>-1.452</td></tr><tr><td>accepted</td><td>accepted</td><td>accepted</td></tr><tr><td rowspan="2">CUB-SVMvs.SMOTE-SVM</td><td>1.742</td><td>-4.765</td><td>-0.503</td></tr><tr><td>rejected</td><td>accepted</td><td>accepted</td></tr><tr><td rowspan="2">CUB-SVMvs.MINSVM</td><td>0.405</td><td>-2.526</td><td>-1.416</td></tr><tr><td>rejected</td><td>accepted</td><td>accepted</td></tr></table></body></html>

# 5 结束语

本文提出了一种用于维吾尔语网站文本过滤的方法，采用了不良的文本预处理和词干提取步骤来降低文本特征维度，并将本文向量化表示。为了更好的对类不平衡文本进行分类，提出了一种改进型的SVM分类器(CUB-SVM)，以此实现维吾尔语文本的高精度分类，从而对不良文本进行过滤。实验结果表明，提出的方法能够准确分类出不良类的网页文本，能够应用于维吾尔语网页的管理和净化。

# 参考文献：

[1]余本功，张连彬．基于CP-CNN 的中文短文本分类研究[J].计算机应 用研究,2018,35(4):1001-1004.(Yu Bengong,Zhang Lianbin.Chinese short text classification based on CP-CNN [J].Application Research of Computers,2018,35(4): 1001-1004.) [2] 黄发良，冯时，王大玲，等．基于多特征融合的微博主题情感挖掘[J]. 计算机学报，2017,40 (4):872-888.(Huang Faliang,Fneg Shi,Wang Daling，et al. Mining topic sentiment in microblogging based on multi-feature fusion [J]. Chinese Journal of Computers,2O17,40 (4):   
872-888.) [3]顾晓清，蒋亦樟，王士同．用于不平衡数据分类的0阶TSK型模糊系统 [J].自动化学报,2017,43(10):1773-1787.(Gu Xiaoqing,Jiang Yizhang, Wang Shitong. Zero-order TSK-type fuzzy system for imbalanced data classification [J].Acta Automatica Sinica,2017,43 (10): 1773-1787.) [4]Bhowan U,Mark Johnston,Zhang Mengjie，et al.Evolving diverse ensembles using genetic programming for classification with unbalanced data [J].IEEE Trans on Evolutionary Computation,2013,17(3): 368-386. [5] 买买提依明·哈斯木，吾守尔·斯拉木，维尼拉·木沙江，等．基于N元模 型的维吾尔语文本分类技术研究[J].计算机应用研究，2015，32（7):   
1986-1988.(MaimaitiyimingHasimu,WushouerSilamu,Weinila Mushajiang Nuermaimaiti Youluwasi,et al. Research N-gram based

Uyghur text classification technique [J].Application Research of Computers,2015,32(7):1986-1988.)

[6]吐尔地·托合提，艾克白尔·帕塔尔，艾斯卡尔·艾木都拉．语义词特征提取及其在维吾尔文文本分类中的应用[J]．中文信息学报，2014，28(6):14O-144.(Turdi Tohti,Akbar Pattar,AskarHamdulla.Semantics-basedfeature extraction and its application in uyghur text classification [J].Journal of Chinese Information Processing,2014,28 (6):140-144.)

[7]吐尔地·托合提，艾海麦提江·阿布来提，米也塞·艾尼玩，等．一种结合GAAC和K-means的维吾尔文文本聚类算法[J].计算机工程与科学，2013,35(7): 149-155.(Turdi Tohti,Ahmatjan Ablat,Muyassar Aniwar,etal.Combined algorithm of GAAC and K-means for Uyghur text clustering[J].Computer Engineering and Science,2013,35(7): 149-155.)

[8]李响，吐尔根·依布拉音，卡哈尔江·阿比的热西提，等．基于主动学习 的SVM维吾尔语情感分析研究[J].新疆大学学报：自然科学版，2015， 32 (4): 447-452.(LI Xiang,Tuergen Yibulayin,Kahaerjiang Abiderexiti,et al. Emotion analysis of active learning based on SVM in Uyghur language [J].Journal of Xinjiang University (Natural Science Edition),2O15,32 (4): 447-452. )

[9]Pal M,MatherPM.Support vector machines for classification in remote sensing [J].International Journal of Remote Sensing，2O15,26 (5): 1007-1011.

[10] Yuan Yubo,Fan Weiguo,Pu Dongmei. Spline function smooth support vectormachine for classification [J].Journal of Industrial &Management Optimization,2017,3(3):529-542.

[11] Ma Hongyan,Wang Liling,Shen Bo.A new fuzzy support vector machines for class imbalance learning [C]// Proc of International Conference on Electrical and Control Engineering．Piscataway，NJ: IEEE，2011: 3781-3784.

[12] Chawla NV,Bowyer K W,HallLO,et al.SMOTE:synthetic minority over-sampling technique [J]. Journal of Artificial Intelligence Research, 2002,16(1): 321-357.

[13] Ajeeb N,Nayal A，Awad M.Minority SVM for linearly separable imbalanced datasets [C]//Proc of International Joint Conference on Neural Networks. $\because$ Piscataway,NJ:IEEE,2014:1-5.

[14]阿不都萨拉木·达吾提，于斯音·于苏普，艾斯卡尔·艾木都拉．类别区 分词与情感词典相结合的维吾尔文句子情感分类[J].清华大学学报： 自然科学版,2017,57(2):197-201.(Abdusalam Dawut,Hussein Yusuf, Askar Handulla. Emotion recognition from Uyghur sentences based on combinations of class discrimination words and a sentiment dictionary [J] Journal of Tsinghua University: Science and Technology，2O17,57 (2): 197-201. )

[15]韩军兵，哈力旦·阿布都热依木，古力努尔·艾尔肯，等．改进信息增 益的维吾尔文特征选择方法[J].计算机工程与应用，2017，53 (23): 34-38.(Han Junbing,Halidan· Abudureyimu,Gulnur Arken，et al. Improved information gain algorithm based on Uyghur feature selection [J]. Computer Engineering and Applications,2017,53 (23): 34-38.)

[16] Sun Rong,Zhou Wen,Liu Zongtian.Using language rules to improve the performance of word segmentation [Cl// Proc of International Congress on Image and Signal Processing.Piscataway,NJ:IEEE,2O14:1665-1669.

[17]于洁.基于Spark和DN-gram 模型的定义抽取研究[J].北京信息科技大学学报：自然科学版，2017，32(4):64-68.(Yu Jie.Researchondefinition extraction based on Spark and DN-gram model[J]. Journal ofBeijing Information Science & Technology University,2017,32 (4):

# 64-68.)

[18]董洋溢，李伟华，于会．基于混合余弦相似度的中文文本层次关系挖掘 [J].计算机应用研究,2017,34(5):1406-1409.(Dong Yangyi,LiWeihua, Yu Hui.Hierarchical relation mining of Chinese text based on mixed cosine similarity [J].Application Research of Computers,2017,34(5): 1406-1409.)