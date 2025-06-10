# 文本分类中一种特征选择方法研究\*

赵婧，邵雄凯，刘建舟，王春枝(湖北工业大学 计算机学院，武汉 430068)

摘要：针对文本分类中传统特征选择方法卡方统计量和信息增益的不足进行了分析，得出文本分类中的特征选择关键在于选择出集中分布于某类文档并在该类文档中均匀分布且频繁出现的特征词。因此，综合考虑特征词的文档频、词频以及特征词的类间集中度、类内分散度，提出一种基于类内类间文档频和词频统计的特征选择评估函数，并利用该特征选择评估函数在训练集每个类别中选取一定比例的特征词组成该类别的特征词库，而训练集的特征词库则为各类别特征词库的并集。通过基于 SVM的中文文本分类实验表明，该方法与传统的卡方统计量和信息增益相比，在一定程度上提高了文本分类的效果。

关键词：文本分类；特征选择；分散度；集中度；频度 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.01.0078

# Study on feature selection method in text classification

Zhao Jing, Shao Xiongkai, Liu Jianzhou, Wang Chunzhi (School ofComputer Science Hubei University of Technology,Wuhan 430o68,China

Abstract: The traditional feature selection methodofchi-squaretestand information gain in textclasificationhasitsinherent defect.This paperanalyzed thekeyoffeature selection intext clasification being toselect feature words distributed evenlyand frequently in each typeof documents.This should consider notonlythe document frequencyand term frequencyof feature words,but alsote inter classconcentration degreeand the intra class scatter degreeoffeature words.It proposedafeature selectionevaluationfunctionthatisbasedondocumentfrequencyofwithin-classandbetween-classandterm frequencystatistics. Thefeature selection evaluation function could selecta certain proportionof thefeature words ineach categoryofthe training setto form thecorrsponding classof the feature word library.Theentire feature word libraryofthe training set could be composed byeach ofsuch classes as aresult.Itcarriedout the experiment of Chinese textclasificationbased on SVM.The experimentalresultsshowthattheproposedmethodimproves theeffctivenessoftextclasificationtoacertain extent,compared with the traditional chi-square test and information gain.

Key words: text classification; feature selection; distribution; concentration; frequency

# 0 引言

文本挖掘技术作为组织和处理海量文本数据的有效技术，近几年备受关注。文本分类作为文本挖掘中的关键技术之一，其目的是在预定义的分类体系下，根据文本的特征（内容或属性），将给定的文本与一个或多个类别相关联的过程[1]。基于机器学习的文本自动分类的整体思路大致为文本预处理；特征降维；建立文本表示模型；使用分类算法分类；分类模型评估。

特征降维作为文本分类中的重要步骤，其目的在于提高分类精度和分类效率[2]。文本通过预处理后变成由词项表示，即为原始特征空间。该原始特征空间具有高维性和稀疏性的特点，所存在的问题是：a)分类时间开销大；b)过多的特征可能会导致“维数灾难”[3]。特征降维，即将特征空间从高维降低到低维层次，从而提高分类的准确率，降低分类的时间成本。

特征降维包括特征选择（featureselection）和特征抽取（featureextraction）[3]。特征选择，即从原始特征数据集中选择出一部分具有代表性的特征。特征选择后得到的是原始特征数据集的一个子集。特征抽取，即利用原始特征空间中包含的所有信息来获得新的转换空间，从而将高维模式映射到低维模式[4]。其中，传统的特征选择方法有文档频率（documentfrequency，DF）、互信息（mutual information，MI）、信息增益（information gain，IG）、卡方统计量（chi-square test，CHI)

等[5]。Yang等人[的研究结果表明，卡方统计量（CHI）和信息增益（IG）的分类效果相对较好，其结论对之后的研究具有重要的参考价值。本文主要针对CHI和IG特征选择方法进行研究和分析，并提出了一种综合考虑特征词的文档频、词频以及特征词的类间集中度、类内分散度的特征选择方法、基于类内类间文档频和词频统计（document frequencyof within-class andbetween-class and term frequency statistics，DFCTFS）的特征选择方法。

# 1 相关工作

# 1.1CHI特征选择方法

CHI以特征词t与类别 $\mathrm { C _ { i } }$ 相互独立为前提，计算这两个变量之间的值（即偏差程度）。如果计算得到的值越大（即偏差较大），则特征词 $\mathrm { \Omega _ { t } }$ 与类别 $\mathrm { C _ { i } }$ 越相关[。CHI 评估函数的公式如下：

$$
\chi ^ { 2 } ( t , c _ { i } ) = \frac { N \times ( A \times D - B \times C ) ^ { 2 } } { ( A + C ) \times ( B + D ) \times ( A + B ) \times ( C + D ) }
$$

其中：N、A、B、C、D参数的意义如表1所示。

表1CHI评估函数中各项参数的意义  

<html><body><table><tr><td colspan="3">属于类别Ci 不属于类别Ci</td><td>总数</td></tr><tr><td>包含特征词t的文本数</td><td>A</td><td>B</td><td>A+B</td></tr><tr><td>不包含特征词t的文本数</td><td>C</td><td>D</td><td>C+D</td></tr><tr><td>总数</td><td>A+C</td><td>B+D</td><td>N=A+B+C+D</td></tr></table></body></html>

式（1）计算得到的是特征词t对于一个类别的CHI值。对于训练集为多个类别，特征词t对于整个训练集的CHI值，即为计算该特征词t在训练集中各类别的CHI值，取计算所得CHI值的平均值或者最大值作为结果，可用式（2）和（3）分别进行表示。

$$
\chi _ { a \nu g } ^ { 2 } \left( t \right) = \sum _ { i = 1 } ^ { M } P ( C _ { i } ) \chi ^ { 2 } ( t , C _ { i } )
$$

$$
\chi _ { \operatorname* { m a x } } ^ { 2 } ( t , C _ { i } ) = \operatorname* { m a x } _ { i = 1 } ^ { M } \{ \chi ^ { 2 } ( t , C _ { i } ) \}
$$

其中：M为类别数。

但是传统的CHI方法存在着不足：a）未考虑特征词在各类别中的词频分布，只考虑了特征词的文档频，导致CHI可能会选择文档频率高但词频低的特征词[8]，例如类别 $\mathrm { C _ { i } }$ 的多数文档中都含有特征词t，即特征词t在类别 $\mathrm { C _ { i } }$ 的文档频率高，但特征词t在其每篇文档中只出现一次，即特征词t在类别 $\mathrm { C _ { i } }$ 的词频很低，该特征词t并不适合代表类别 $\mathrm { C _ { i } }$ ，但使用CHI特征选择方法可能会选择该特征词t；b）不属于该类别的特征词的干扰，因为式（1）中的因子 $( A \times D - B \times C ) ^ { 2 }$ 的存在，导致当 $\mathrm { B C } \rangle \rangle \mathrm { A D }$ 时，即特征词t不属于该类别 $\mathrm { C _ { i } }$ 时，其CHI值也会较高，可能被选择为代表Ci类的特征词[9]。

# 1.2IG特征选择方法

IG用于文本的特征选择时，衡量的是某个词的出现与否对判断一个文本是否属于该类别所提供的信息量，信息量的多少由熵来衡量。

IG 即为不考虑任何特征时文档的熵和考虑该特征后文档的熵的差值[。该差值表示信息不确定性的减少程度。信息不确定性减少程度越大，相应的信息增益越大；该词项提供的信息越多，该词项越重要。

因此，在进行特征选择时，通常按照IG值降序排列，选取一定比例的词作为特征词。IG评估函数的公式如下：

$$
\begin{array} { l } { { \displaystyle I G ( t ) = - \sum _ { i = 1 } ^ { M } P ( C _ { i } ) \log P ( C _ { i } ) + P ( t ) \sum _ { i = 1 } ^ { M } P ( C _ { i } \mid t ) \log P ( C _ { i } \mid t ) + } } \\ { { \displaystyle P ( \bar { t } ) \sum _ { i = 1 } ^ { M } P ( C _ { i } \mid \bar { t } ) \log P ( C _ { i } \mid \bar { t } ) } } \end{array}
$$

其中： $\mathtt { M }$ 表示类别数； $P ( C _ { i } )$ 表示属于类 $\mathrm { C _ { i } }$ 的文本在文本集中出现的概率，即

$$
P ( C _ { i } ) = \frac { \sqrt { 1 2 } \mp 2 \Im } { \Im \Im \Im } \Re \Re \Re \Re \Re  { \Re \Re \Re }
$$

$P ( t )$ 表示文本集中包含特征词t的文本的概率，即

$$
P ( t ) = \frac { \overleftrightarrow { \mathrm { U } } _ { 1 } \overleftrightarrow { \mathrm { H } } _ { 2 } } { \overleftrightarrow { \mathrm { X } } \overleftrightarrow { \mathrm { H } } _ { 2 } } t \overleftrightarrow { \mathrm { H } } ^ { \prime } \times \overleftrightarrow { \mathrm { X } } _ { 3 } \times \frac { 3 } { 3 } \times \frac { 3 } { 3 } \times \frac { 3 } { 3 } \times \frac { 3 } { 3 } \times \frac { 3 } { 3 } \times ( \frac { 3 } { 3 } \times \frac { 3 } { 3 } ) .
$$

$P ( C _ { i } \left| t \right)$ 表示文本包含特征词t时属于类 $\mathrm { C _ { i } }$ 的条件概率，即$\left. P ( C _ { i } \mid \bar { t } ) \right.$ 表示文本不包含特征词t时属于类 $\mathrm { C _ { i } }$ 的条件概率，即

但是传统的IG方法存在着不足：a）未考虑特征词在各类别中的词频分布，只考虑了特征词的文档频，导致IG可能会选择文档频率高但词频低的特征词；b)考虑了特征词t在类别 $\mathrm { C _ { i } }$ 中未出现时对于分类的贡献，但该类别未出现的特征词对特征选择也存在着干扰[10]；c）只能作全局的特征选择（指训练集中所有类别都使用相同的特征集合），而无法作本地的特征选择（指训练集中每个类别都有自己的特征集合）[1]。

# 2 DFCTFS特征选择方法

# 2.1DFCTFS 特征选择评估函数

综合分析CHI和IG的不足，可以得出文本分类中特征选择的关键在于选择出集中分布于某类文档并在该类文档中均匀分布且频繁出现的特征词。因此，本文综合考虑特征词的文档频、词频以及特征词的类间集中度、类内分散度，提出一种基于类内类间文档频和词频统计（DFCTFS）的特征选择方法。

# 2.1.1特征词的类间集中度、类内分散度

能够代表某一类别的特征词应是集中分布在该类别中（即类间集中度高)，并且在该类别中均匀分布(即类内分散度大)。综合考虑这两个因素，本文提出：

$$
\alpha { = } \frac { \mathrm { D F ( t _ { k } , C _ { i } ) } } { \mathrm { D F ( t _ { k } ) } } { \bullet } \frac { \mathrm { D F ( t _ { k } , C _ { i } ) } } { \mathrm { D F ( t , C _ { i } ) } }
$$

其中： $\mathrm { D F } \left( \mathrm { t } _ { \mathrm { k } } , \mathrm { C } _ { \mathrm { i } } \right)$ 表示特征词 $\mathrm { t _ { k } }$ 在类别 $\mathrm { C _ { i } }$ 中出现的文本数；DF(tk)表示特征词 $\mathfrak { t } _ { \mathrm { k } }$ 在训练集所有类别中出现的文本数总和；DF $\left( \mathrm { { t } , \mathrm { { C _ { i } } } } \right)$ 表示类别 $\mathrm { C _ { i } }$ 中所有特征词出现的文本数的总和。

其基本思想是：构造一个特征词、类别的二维矩阵。假设该二维矩阵为4\*3的矩阵，如表2所示。矩阵中的元素代表特征词 $\mathrm { \Delta t _ { k } }$ 在 $\mathrm { C _ { i } }$ 类别出现的文本数DF $\left( \mathrm { { t } _ { \mathrm { { k } } } , \mathrm { { C } _ { \mathrm { { i } } } } } \right)$ 。将特征词 $\mathrm { t _ { k } }$ 所在行的各个DF $\left( \mathrm { { t } _ { \mathrm { { k } } } , \mathrm { { C } _ { \mathrm { { i } } } } } \right)$ 相加即为DF $\left( \mathrm { t _ { k } } \right)$ ，表示特征词 $\mathrm { t _ { k } }$ 在训练集所有类别中出现的文本数总和；对特征词 $\mathrm { t _ { k } }$ 所在行使用 $\frac { \mathrm { D F ( t _ { k } , C _ { i } ) } } { \mathrm { D F ( t _ { k } ) } }$ 即为计算特征词 $\mathrm { t _ { k } }$ 在 $\mathrm { C _ { i } }$ 类的类间集中度。将第 $\mathrm { C _ { i } }$ 列的各个DF $\left( \ t _ { \mathrm { { t } _ { \mathrm { k } } , \tilde { \mathbf { \Lambda } } } } \right)$ 相加即为 $\mathrm { D F } \left( \mathrm { t } , \mathrm { C } _ { \mathrm { i } } \right)$ ，表示类别 $\mathrm { C _ { i } }$ 中所有特征词出现的文本数的总和；对特征词 $\mathrm { t _ { k } }$ 所在列使用 DF(C，即为计算特征词 $\mathrm { t _ { k } }$ 在 $\mathrm { C _ { i } }$ 类的类内分散度。

表2特征词、类别的二维矩阵  

<html><body><table><tr><td></td><td>C1</td><td>C2</td><td>C</td></tr><tr><td>t1</td><td>0</td><td>1</td><td>3</td></tr><tr><td>t2</td><td>3</td><td>0</td><td>0</td></tr><tr><td>t</td><td>1</td><td>1</td><td>1</td></tr><tr><td>t4</td><td>0</td><td>2</td><td>0</td></tr></table></body></html>

# 2.1.2词频

能够代表某一类别的特征词应是频繁出现在该类别中（即词频较高），同时考虑对词频进行归一化处理，避免类别中的文档数对词频产生影响。因此，本文提出：

$$
\beta = \frac { \mathrm { T F ( t _ { k } , C _ { i } ) / n u m D o c s _ { i } } } { \displaystyle \sum _ { i = 1 } ^ { M } [ \mathrm { T F ( t _ { k } , C _ { i } ) / n u m D o c s _ { i } } ] }
$$

其中： $\mathrm { T F } \left( \mathrm { t } _ { \mathrm { k } } , \mathrm { C } _ { \mathrm { i } } \right)$ 表示特征词 $\mathrm { t _ { k } }$ 在类别 $\mathrm { C _ { i } }$ 中出现的次数；  
numDocsi表示类别 $\mathrm { C _ { i } }$ 的文本数； $\mathtt { M }$ 表示类别数。

# 2.1.3DFCTFS评估函数

因此，综合考虑特征词的文档频、词频以及特征词的类间集中度、类内分散度，提出DFCTFS特征选择的评估函数，公式为

$$
\begin{array} { r l } & { D F C T F S ( t _ { k } , C _ { i } ) = \alpha \bullet \beta = } \\ & { \frac { \mathrm { D F ( t _ { k } , C _ { i } ) } } { \mathrm { D F ( t _ { k } ) } } \bullet \frac { \mathrm { D F ( t _ { k } , C _ { i } ) } } { \mathrm { D F ( t , C _ { i } ) } } \bullet \frac { \mathrm { T F ( t _ { k } , C _ { i } ) / n u m D o c s _ { i } } } { \displaystyle \sum _ { i = 1 } ^ { M } [ \mathrm { T F ( t _ { k } , C _ { i } ) / n u m D o c s _ { i } } ] } } \end{array}
$$

其中：DFCTFS $\left( \mathrm { { t } _ { \mathrm { { k } } } , \mathrm { { C } _ { \mathrm { { i } } } } } \right)$ 表示特征词 $\mathrm { t _ { k } }$ 在类别 $\mathrm { C _ { i } }$ 中的DFCTFS值；DF $\left( \mathrm { { t } _ { \mathrm { { k } } } , \mathrm { { C } _ { \mathrm { { i } } } } } \right)$ 表示特征词 $\mathrm { t _ { k } }$ 在类别 $\mathrm { C _ { i } }$ 中出现的文本数；DF $\left( \mathrm { t } _ { \mathrm { k } } \right)$ 表示特征词 $\mathrm { t _ { k } }$ 在训练集所有类别中出现的文本数总和；DF $\left( \mathrm { { t } , \mathrm { { C } _ { \mathrm { { i } } } } } \right)$ 表示类别 $\mathrm { C _ { i } }$ 中所有特征词出现的文本数的总和； $\mathrm { T F } \left( \mathrm { t } _ { \mathrm { k } } , \mathrm { C } _ { \mathrm { i } } \right)$ 表示特征词 $\mathrm { t _ { k } }$ 在类别 $\mathrm { C _ { i } }$ 中出现的次数；numDocsi表示类别 $\mathrm { C _ { i } }$ 的文本数；M表示类别数。

# 2.2 DFCTFS特征选择的实现思路

训练文本集通过预处理和特征选择后形成特征词库。CHI特征选择方法是依据CHI评估函数，得到每个特征词在训练集各个类别的CHI值，使用特征词在所有类别中的CHI值的平均值或者最大值作为该特征词在整个训练集中的CHI值，将所有特征词按CHI值降序排列，选取一定比例的特征词作为整个训练集的特征词库。IG特征选择方法是依据IG评估函数，得到每个特征词在整个训练集中的IG值，将所有特征词按IG值降序排列，选取一定比例的特征词作为整个训练集的特征词库。

本文提出的DFCTFS特征选择方法是依据本文提出的DFCTFS评估函数，从训练集各类别选择一定比例的特征词，将所获得的特征词取并集后形成最终的特征词库。

利用DFCTFS 特征选择算法进行中文文本分类的算法步骤如图1所示。

![](images/c509200566a2ab544b00729f4f92aecd249336e57de002623bf1d0e3cc0da550.jpg)  
图1中文文本分类整体流程

a）文本预处理。首先将训练集和测试集中的文本做好类别标志；其次将训练集和测试集中的文本进行分词，去停用词。文本经过预处理后变成由词项表示，即为原始特征空间。

b)特征选择。将训练集经过预处理后的原始特征空间使用DFCTFS特征选择方法得到特征词库。主要实现思路如下：

(a)构造一个特征词、类别的二维矩阵，其中行代表特征词，列代表类别，矩阵中的元素为DFCTFS值。获取训练集中原始的所有特征词，编号为 $\mathrm { t } _ { 0 } { \sim } \mathrm { t } _ { \mathrm { N } } .$ 0

针对训练集中的各个类别，统计特征词 $\mathrm { t _ { k } }$ 0 $\mathrm { ? k { = } 1 \mathrm { . ~ . ~ . ~ } N }$ ，N:词项总个数）在第 $\mathrm { C _ { i } }$ （ $\mathrm { i = 1 \ldots \cdot M }$ ，M：类别数）类别中出现的文本数DF $\left( \ t _ { \mathrm { t } _ { \mathrm { k } } , \mathrm { C _ { \mathrm { i } } } } \right)$ 和次数TF $\cdot \left( \ t _ { \mathrm { { t } _ { \mathrm { k } } , \tilde { C } _ { \mathrm { i } } } } \right)$ 。根据 $\mathrm { { t } _ { \mathrm { k } } , \ C _ { \mathrm { i } } }$ 定位到二维矩阵相应位置，利用DFCTFS评估函数，计算 $\mathrm { C _ { i } }$ 类别的特征词 $\mathrm { \Delta t _ { k } }$ 的DFCTFS值，从而构造出 $\mathrm { N * M }$ 的二维矩阵。

(b)依据各类别中每个特征词的DFCTFS值，对每个类别中的特征词进行降序排列。

(c)依据文献[12]所述，对于高维的特征词空间一般选择$2 \% \sim 5 \%$ 的特征词集合作为分类依据。根据此规则，首先获得训练集中总类别数（用M表示）以及训练集中特征词的总个数，取特征词总个数的 $2 \% \sim 5 \%$ （用numWords表示），则各类别中选择的特征词个数num为numWords除以 $\mathtt { M }$ 0

(d)各类别中都依据上一步所得num值，选取该类别中降序排列后的前num个特征词组成该类别的特征词库。

(e)得到训练集的特征词库，即为各类别所得特征词库的并集。并集，即保证特征词库中词的唯一性。

c）建立文本表示模型。其中向量空间模型使用最为广泛[13],主要实现思路是，根据特征词库，计算训练集中每篇文本对应的特征词的权重。最常使用的权重计算方法是TF-IDF（词频-逆文档频率），即将训练集向量化后形成一个二维矩阵，每一行代表一篇文本，每一列代表特征词库中的一个特征词。测试集作同样操作。

d）使用分类算法分类。对训练集使用分类算法进行分类器训练，得到分类模型。

e）分类器性能评估。利用训练得到的分类模型，对测试集进行分类，利用准确率、召回率、F1值，实现对分类器的性能评价。

# 3 实验与分析

本文的实验在进行文本分词时使用的是中国科学院计算技术研究所研发的ICTCLAS 汉语分词系统[14]。分词后的去停用词，使用的是哈工大停用词表[15]。

# 3.1 语料库

实验中使用的语料库是复旦大学计算机信息与技术系国际数据库中心自然语言处理小组整理的中文语料库[16]。选用其中的体育、历史、太空、政治、环境、经济、艺术、计算机，共8 个类别。其中各类别文本的选取情况如表3所示。

表3语料库中训练集和测试集的选取情况  

<html><body><table><tr><td></td><td>体育</td><td>历史</td><td>太空</td><td>政治</td><td>环境</td><td>经济</td><td>艺术</td><td>计算机</td></tr><tr><td>训练集</td><td>400</td><td>400</td><td>400</td><td>400</td><td>400</td><td>400</td><td>400</td><td>400</td></tr><tr><td>测试集</td><td>65</td><td>65</td><td>65</td><td>65</td><td>65</td><td>65</td><td>65</td><td>65</td></tr></table></body></html>

# 3.2 分类器

实验中使用SVM分类算法实现中文文本分类，SVM将基于台湾大学林智仁教授等开发的LIBSVM工具箱的Java版本。因为建立文本表示模型时使用的是向量空间模型，其本身是一个大且稀疏的矩阵，线性可分，不需要再对其进行高维映射，所以使用 SVM中的线性核函数[17]。使用线性核函数需要寻找最优参数C（惩罚因子）[18]。本文使用的是传统的网格搜索方法，在一定范围内，对训练集采用交叉验证的方法，找出交叉验证准确率最高的C值，作为SVM模型中的惩罚因子C的取值。

# 3.3评价标准

实验中将采用召回率、准确率、F1值在单个类别上进行评价。采用宏召回率、宏准确率、宏F1值在整体上进行评价。召回率衡量的是分类器的完备性，准确率衡量的是分类器的正确性，F1值是调节召回率和准确率的一个平衡点。召回率R、准确率P、F1值、宏召回率MacroR、宏准确率MacroP、宏F1值MacroF1的公式如下：

$$
R = { \frac { A } { A + C } }
$$

$$
P = { \frac { A } { A + B } }
$$

$$
F 1 = \frac { 2 P R } { P + R }
$$

$$
\boldsymbol { M a c r o R } = \frac { \displaystyle \sum _ { i = 1 } ^ { M } R _ { i } } { \displaystyle M }
$$

$$
 M a c r o P = \frac { \displaystyle \sum _ { i = 1 } ^ { M } P _ { i } } { M }
$$

$$
\ M a c r o F 1 = \frac { \displaystyle \sum _ { i = 1 } ^ { M } F 1 _ { i } } { M }
$$

其中：M为类别数；A、B、C、D参数的意义如表4所示。

表4召回率、准确率公式中的参数意义  

<html><body><table><tr><td></td><td>属于该类</td><td>不属于该类</td></tr><tr><td>判定为属于该类的</td><td>A</td><td>B</td></tr><tr><td>判定为不属于该类的</td><td>C</td><td>D</td></tr></table></body></html>

# 3.4实验结果及分析

表 $5 { \sim } 7$ 以及相应的图 $2 { \sim } 4$ 是分别选择原始特征词集合的$2 \%$ 、 $3 \%$ 、 $4 \%$ ， $5 \%$ 作为特征向量空间维数在宏召回率、宏准确率、宏 F1值上的实验结果。通过在不同维度上对分类器性能进行整体评价，验证本文提出的DFCTFS特征选择方法的有效性。通过实验对比，传统的CHI和IG特征选择方法的分类宏召回率、宏准确率、宏F1值在不同维度上呈现出上下波动的趋势，而本文提出的DFCTFS特征选择方法在不同维度上的分类效果相较于CHI和IG而言，都有一定程度的提高，并且特征向量空间维数不同，提升的幅度不同。在本文的实验中，选择原始特征词集合的 $5 \%$ 作为特征向量空间维数，提升的幅度最大。

分析DFCTFS特征选择方法优于传统的CHI和IG的原因，是因为DFCTFS特征选择评估函数是基于类内类间文档频和词频统计的，特征选择出的特征词是集中分布于某类文档并在该类文档中均匀分布且频繁出现的。同时，DFCTFS特征选择方法做的是本地特征选择，相较于全局特征选择方法而言，特征选择出的特征词在具体类别中更具有代表性。

表5CHI、IG和DFCTFS在不同维度的宏召回率的比较  

<html><body><table><tr><td></td><td>2%</td><td>3%</td><td>4%</td><td>5%</td></tr><tr><td>CHIR</td><td>0.9288</td><td>0.925</td><td>0.9326</td><td>0.925</td></tr><tr><td>IGR</td><td>0.9134</td><td>0.9326</td><td>0.925</td><td>0.9307</td></tr><tr><td>DFCTFS R</td><td>0.9307</td><td>0.9384</td><td>0.9403</td><td>0.9461</td></tr></table></body></html>

![](images/fed5f1b73eb8feca1840bf9f32dbbba6731f94fd5ac4696f6faa323eaedcc548.jpg)  
图2CHI、IG 和DFCTFS 在不同维度的宏召回率的比较

表6CHI、IG和DFCTFS在不同维度的宏准确率的比较  

<html><body><table><tr><td></td><td>2%</td><td>3%</td><td>4%</td><td>5%</td></tr><tr><td>CHI P</td><td>0.931</td><td>0.927</td><td>0.9343</td><td>0.9259</td></tr><tr><td>IG P</td><td>0.9143</td><td>0.9339</td><td>0.9271</td><td>0.9334</td></tr><tr><td>DFCTFSP</td><td>0.9321</td><td>0.9402</td><td>0.9416</td><td>0.947</td></tr></table></body></html>

![](images/7e985553a1eaaaf90071f4c1aba7e60751ce9217e4dc8da6f6dc9eb336119707.jpg)  
图3CHI、IG 和 DFCTFS 在不同维度的宏准确率的比较表7CHI、IG 和DFCTFS 在不同维度的宏F1值的比较

<html><body><table><tr><td></td><td>2%</td><td>3%</td><td>4%</td><td>5%</td></tr><tr><td>CHI F1</td><td>0.9293</td><td>0.9252</td><td>0.9327</td><td>0.9248</td></tr><tr><td>IG F1</td><td>0.9132</td><td>0.9326</td><td>0.9251</td><td>0.931</td></tr><tr><td>DFCTFS F1</td><td>0.9309</td><td>0.9385</td><td>0.9402</td><td>0.946</td></tr></table></body></html>

![](images/4210d56764fb7cb47fd91af8d7072834568dbb6eabe0279e15f6dadf713c37c9.jpg)  
图4CHI、IG和DFCTFS在不同维度的宏F1值的比较

以下实验结果是通过对具体类别分类效果的评价，进一步验证本文提出的DFCTFS特征选择方法的有效性。实验选择原始特征词集合的 $5 \%$ 作为特征向量空间维数。通过对表 $8 \sim 1 0$ 及相应的图 $5 { \sim } 7$ 分析，可以得出本文提出的DFCTFS特征选择，在所选的8个类别的分类效果的整体趋势上好于传统的CHI和IG。通过对表11及相应的图8分析，可以得出本文提出的DFCTFS特征选择方法，在分类的宏召回率上与CHI、IG相比分别提高了 $2 . 1 1 \% . 1 . 5 4 \%$ ，在宏准确率上分别提高了 $2 . 1 1 \% . 1 . 3 6 \%$ 在宏F1值上分别提高了 $2 . 1 2 \%$ 、 $1 . 5 \%$ 。因此，可以得出，本文提出的DFCTFS特征选择方法与传统的CHI和IG相比，文本分类效果有一定程度的提高，说明了DFCTFS特征选择方法的有效性。

表8CHI、IG和DFCTFS在各类别上分类召回率的比较  

<html><body><table><tr><td></td><td>CHI R</td><td>IG R</td><td>DFCTFSR</td></tr><tr><td>体育</td><td>0.9384</td><td>0.9538</td><td>0.9538</td></tr><tr><td>历史</td><td>0.8461</td><td>0.8923</td><td>0.8923</td></tr><tr><td>太空</td><td>0.923</td><td>0.923</td><td>0.9384</td></tr><tr><td>政治</td><td>0.8769</td><td>0.8615</td><td>0.923</td></tr><tr><td>环境</td><td>0.9846</td><td>0.9692</td><td>0.9846</td></tr><tr><td>经济</td><td>0.9846</td><td>0.9846</td><td>1</td></tr><tr><td>艺术</td><td>0.9538</td><td>0.9538</td><td>0.9538</td></tr><tr><td>计算机</td><td>0.8923</td><td>0.9076</td><td>0.923</td></tr></table></body></html>

![](images/f18369425faadfcb23b04cb90a93a079048e82cd1189e1f834b5cb56222d8dfb.jpg)  
图5CHI、IG 和DFCTFS 在分类召回率的比较

表9CHI、IG和DFCTFS在各类别上分类准确率的比较  

<html><body><table><tr><td></td><td>CHI P</td><td>IG P</td><td>DFCTFSP</td></tr><tr><td>体育</td><td>0.9242</td><td>0.9393</td><td>0.9538</td></tr><tr><td>历史</td><td>0.8593</td><td>0.8529</td><td>0.9206</td></tr><tr><td>太空</td><td>0.8823</td><td>0.8695</td><td>0.9104</td></tr><tr><td>政治</td><td>0.9661</td><td>1</td><td>1</td></tr><tr><td>环境</td><td>0.9696</td><td>0.9692</td><td>0.9696</td></tr><tr><td>经济</td><td>0.9014</td><td>0.9142</td><td>0.9154</td></tr><tr><td>艺术</td><td>0.9841</td><td>1</td><td>0.9687</td></tr><tr><td>计算机</td><td>0.9206</td><td>0.9218</td><td>0.9375</td></tr></table></body></html>

![](images/5399b7b54587c2d55d5a1636701b104f68d33dcbe53d9af8681044f3aab60006.jpg)  
图6CHI、IG 和DFCTFS 在分类准确率的比较

表10CHI、IG 和DFCTFS 在各类别上分类F1值的比较  

<html><body><table><tr><td>CHI F1</td><td>IG F1</td><td>DFCTFSF1</td></tr><tr><td>体育</td><td>0.9312 0.9465</td><td>0.9538</td></tr><tr><td>历史</td><td>0.8527</td><td>0.8721 0.9062</td></tr><tr><td>太空</td><td>0.9022 0.8955</td><td>0.9242</td></tr><tr><td>政治</td><td>0.9193 0.9256</td><td>0.96</td></tr><tr><td>环境</td><td>0.977 0.9692</td><td>0.977</td></tr><tr><td>经济</td><td>0.9411 0.9481</td><td>0.9558</td></tr><tr><td>艺术</td><td>0.9687 0.9763</td><td>0.9612</td></tr><tr><td>计算机</td><td>0.9062</td><td>0.9147 0.9302</td></tr></table></body></html>

![](images/b88f437b71b6ea7d9d167906b70a2baa6a338d1be0b797e733230f0cbeb80c94.jpg)  
图7CHI、IG和DFCTFS在分类F1值的比较

表11CHI、IG 和DFCTFS 在整体分类效果上的比较  

<html><body><table><tr><td></td><td>宏R</td><td>宏P</td><td>宏F1</td></tr><tr><td>CHI</td><td>0.925</td><td>0.9259</td><td>0.9248</td></tr><tr><td>IG</td><td>0.9307</td><td>0.9334</td><td>0.931</td></tr><tr><td>DFCTFS</td><td>0.9461</td><td>0.947</td><td>0.946</td></tr></table></body></html>

![](images/224689cb73ce10ec3d85a5cf3751109ea95e8f9b7eee4bb3bea9fec92849c859.jpg)  
图8CHI、IG 和DFCTFS 在整体分类效果上的比较

# 4 结束语

本文分析了传统特征选择效果较好的CHI和IG特征选择方法存在的不足，即未考虑特征词在各类别中的词频分布；类别负相关特征词的干扰；以及IG只能做全局的特征选择，而无法做本地的特征选择。并由此得出，文本分类中的特征选择关键在于选择出集中分布于某类文档并在该类文档中均匀分布且频繁出现的特征词。因此，综合考虑特征词的文档频、词频以及特征词的类间集中度、类内分散度，提出一种基于类内类间文档频和词频统计（DFCTFS）的特征选择方法。

通过基于SVM的中文文本分类实验验证，DFCTFS特征选择与CHI、IG特征选择方法相比，在一定程度上提高了中文文本分类的效果。但是由于中文文本分类系统涉及文本预处理，特征降维，建立文本表示模型中的特征词权重的计算，分类算法决策等多个环节，最终的分类效果是由以上所述环节共同作用的结果。因此，仅改进特征选择的方法，只能在一定程度上提高分类的效果。

# 参考文献：

[1]宗成庆．统计自然语言处理(第2版)[M].北京：清华大学出版社, 2013:416-430.(Zong Chengqing. Statistical natural language processing (2nd ed)[M].Beijing:Tsinghua University Press,2013:416-430.)   
[2]戚孝铭，施亮．基于模拟退火及蜂群算法的优化特征选择算法[J].计 算机工程与设计，2013,34(8):2917-2921.(Qi Xiaoming,Shi Liang Improved feature selection algorithm based on simulated annealing algorithm and artificial bee colony algorithm[J]. Computer Engineering and Design,2013,34(8):2917-2921.)   
[3]廖一星．文本分类及其特征降维研究[D].杭州：浙江大学,2012.(Liao Yixing. Text classification and its feature reduction research [D]. Hangzhou: ZhejiangUniversity,2012.)   
[4]Maji P, Garai P. Simultaneous feature selection and extraction using feature significance [J].Fundamenta Informaticae,2015,136 (4):405-431.

[5]Lu Yonghe,Liang Minghui,Ye Zeyuan,et al.Improved particle swarm optimization algorithm and itsapplcation in text teature selection [J]. Applied Soft Computing,2015,35: 629-636.

[6]Yang Y,Pedersen J O.A comparative study on feature selection in text categorization[Cl// Proc of the 14th International Conference on Machine Learning. San Francisco: Morgan Kaufmann,1997: 412-420.   
[7]Uysal A K, Gunal S.A novel probabilistic feature selection method for text classification [J].Knowledge-Based Systems,2012,36:226-235   
[8]姚海英．中文文本分类中卡方统计特征选择方法和TF-IDF权重计算方 法的研究 [D].长春：吉林大学,2016.(Yao Haiying.Research on chisquare statistic feature selection method and TF-IDF feature weighting method for Chinese text classification [D].Changchun:Jilin University, 2016.）   
[9] 叶敏，汤世平，牛振东．一种基于多特征因子改进的中文文本分类算法 [J].中文信息学报,2017,31(4):132-137.(Ye Min,Tang Shiping,Niu Zhendong. An improved Chinese text clasification algorithm based on multiple feature factors [J].Journal ofChinese Information Processing,2017, 31 (4): 132-137.)   
[10]董微，刘学，倪宏．基于信息增益的自适应特征选择方法[J].计算机 工程与设计,2014,35(8):2856-2859.(Dong Wei,Liu Xue,Ni Hong. Adaptive feature selection method based on information gain [J]. Computer Engineering and Design,2014,35 (8): 2856-2859.)   
[11]任永功，杨荣杰，尹明飞，等．基于信息增益的文本特征选择方法[J] 计算机科学,2012,39 (11):127-130.(Ren Yonggong,Yang Rongjie,Yin Mingfei,et al. Information gain based text feature selection method [J]. Computer Science,2012,39 (11): 127-130.)   
[12]王小青．中文文本分类特征选择方法研究[D].重庆：西南大学,2010. (Wang Xiaoqing.Study on the selection method of Chinese text clasification features [D]. Chongqing:Southwest University,2010.）   
[13]郭正斌，张仰森，蒋玉茹．一种面向文本分类的特征向量优化方法[J] 计算机应用研究,2017,34(8):2299-2302.(Guo Zhengbin,Zhang Yangsen, Jiang Yuru.Feature vector optimization method for text classification [J]. Application Research of Computers,2017,34(8): 2299-2302.）   
[14]中国科学院计算技术研究所.ICTCLAS2013[EB/OL].(2013-06-04) [2017-03-24]. htp://ictclas. nlpir.org/. (InstituteofComputing Technology Chinese Academy of Sciences.ICTCLAS2013 [EB/OL]. (2013-06-04) 24p:/   
[15]哈尔滨工业大学．哈工大停用词表扩展[EB/OL].(2008-05-30)[2017- 04-11. htp://ownload.csdn.net/download/qq361277534/475580. (Harbin Institute of Technology.The expansion ofthe stop words in Harbin Institute ofTechnology [EB/OL]. (2008-05-30)[2017-04-11]. htp://download.csdn. net/download/qq361277534/475580.)   
[16]复旦大学计算机信息与技术系国际数据库中心自然语言处理小组．复 旦大学中文文本分类语料库[EB/OL].(2011-04-21）[2017-03-24]. http://www.nlpir.org/?action-viewnews-itemid-103.(Fudan University computer information and technology department international database

center natural language processing group.Fudan University Chinese text classification corpus [EB/OL]. (2011-04-21） [2017-03-24]. http://www. nlpir.org/?action-viewnews-itemid-103.)

[17]刘佳.基于SVM的Web中文文本分类系统研究与实现[D].西安：西安电子科技大学，2014.(Liu Jia.Research and implementation of

categorization system for Chinese Web text based on SVM[D].Xian:Xidian University,2014.) [18] Zhang Yin,Dai Miaolin,Ju Zhimin.Preliminary discussion regarding SVM kernel function selection in the twofold rock slope prediction model [J]. Journal of Computing in Civil Engineering,2016,30 (3): 04015031.