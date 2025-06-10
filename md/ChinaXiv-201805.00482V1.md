# 基于文本分析的故障序列模式挖掘算法\*

常文兵，苑星龙，周晟瀚，李磊(北京航空航天大学 可靠性与系统工程学院，北京 100191)

摘要：针对结构化程度差、表达形式各异的文本数据，提出了一种基于文本信息的故障序列模式挖掘算法，用以发掘故障之间的时序关系。为从文本记录的故障信息中挖掘故障规律，首先将文本信息向量化，对故障文本信息进行相似度衡量，将表达相同意义的故障归为一类。在此基础上根据故障特性，提出最大窗口阈值、最小共现度阈值的概念，构建故障序列模式挖掘算法框架。最后对某型飞机文本故障信息进行序列模式挖掘，找出了正确的故障序列关系。实例验证了所提算法是正确有效的。

关键词：序列模型；数据挖掘；文本相似度；飞机故障；文本挖掘中图分类号： $\mathrm { V } 2 6 7 + . 3$ doi:10.3969/j.issn.1001-3695.2018.02.0142

# Failures sequence pattern mining algorithm based on text analysis

Chang Wenbing, Yuan Xinglong, Zhou Shenghan†,LiLei (SchoolofReliability&SystemEngineering,Beihang University,Beijingl0o191,China)

Abstract:For textual data with poor structured degree anddiferent expression forms,a failuressequence pattrn mining algorithmbasedontext informationis proposedtoexplorethetimesequencerelationshipbetweenfailures.Inordertominethe failuresrules fromthetext,firstlyquantifythetextinformation,measurethesimilarityofthefailuresinformation,ndclasify thefailures that expressthe same meaning intooneclass.Onthis basis,we propose theconceptofmaximum windowthreshold and minimum concurrence threshold basedon failurescharacteristics,and build amining algorithm framework forfailures sequencepattrn.Finallyextractsequentialfailurespattns fromacertainaireraft,andfindoutthecorrectfaliuressequence relationship.The example shows that the proposed algorithm is correct and effective.

'ey words: sequence pattern; data mining; text similarity; aircraft failure; text mining

# 0 引言

飞机作为大型的复杂装备系统，服役周期长，飞行环境复杂恶劣，导致飞机的故障发生频繁，原因复杂。在长期的维修保障过程中积累了大量的故障文本信息，对故障分析和维修决策具有重大意义，有待进行更深层次的挖掘。目前，还没有针对文本信息应用序列模式挖掘识别故障之间的时间关系的研究。

本文第一部分是故障文本相似度衡量，由于文本记录的特性，相同信息的表达形式千差万别，通过文本相似度衡量把相同意思的文本划归为一类。首先要对故障本文进行预处理，使用语言模型进行自然语言处理是建立在词的基础上的，由于中文与英文的区别需要先对故障文本进行分词，才能做进一步的处理。吴熠潇[1介绍了什么是中文分词，中文分词的国内研究现状和当前的研究热点，介绍了统计语言模型,以及如何利用简化的语言模型进行中文分词。本文将采用jieba分词算法来进行分词处理。在分完词的基础上，要把文本信息用数学语言表达出来才能进行下一步的相似度衡量。郑文超等人[2提出了一种中文分词算法，用来将中文文本分割成独立的词语。再对处理后的语料使用word2vec工具集，应用深度神经网络算法，转换为对应的词向量。张志昌等人[3提出一种中文词汇蕴涵关系识别方法，利用词向量技术,设计各种基于词向量的分类特征，训练得到可用于名词词汇蕴涵关系分类的支持向量机分类模型.周练[4研究了word2vec 模型的原理及应用，分析了词向量的特点。唐明等人[5]提出了一种基于word2Vec模型的文档向量表示，利用TF-IDF算法计算每篇文档中词的权重，并结合word2vec词向量生成文档向量。现有的研究大都集中在词汇特征和句法特征的提取上，而忽略了词语之间的语义关系，Zhang等人[为了获得语义特征，提出了一种基于word2vec 和SVMperf的情感分类方法。殷耀明[提出了基于关系向量模型的句子相似度计算，考虑句子结构和语义信息，更能体现句子的结构和语义信息。为了解决机器翻译依赖问题，同时仍然利用资源丰富的语言中的数据，Tian等人[8提出联合学习低资源语义的语义文本相似性任务和资源丰富语义的语义文本相似性任务，该任务仅依赖于多语言词语嵌入。本文第二部分是构建序列模式挖掘算法，也是本文核心部分。序列模式挖掘是数据挖掘的一个重要领域，苗雪连[描述了间隙约束序列挖掘的分类及研究现状,给出了间隙约束的序列模式挖掘在实际生活中的发展趋势并认为在未来的研究领域中,具有间隙约束的序列模式挖掘仍是一个重要的研究方向。

基于模式增长的序列模式挖掘（FreeSpan）的初步研究，Krishna[10]提出了一种更有效的方法，称为PSP，用于高效挖掘顺序模式。Le等人[1研究了频繁闭合和发生器序列的开采任务，因为与频繁序列集合相比，频繁闭合和发生器序列的基数通常远低于频繁序列的基数。针对数据集的增多，约束频繁模式树的构建存在一定的缺陷，约束频繁模式树很难应用于海量数据集，Yan等人[12使用MapReduce 编程模型提出了一种被称为PACFP的约束频繁模式的并行挖掘算法。武优西等人[13]采用模式匹配技术，在一遍扫描序列数据库的情况下，建立其所有超模式的不完整网树森林，并对这些超模式的支持率进行有效地计算，进而挖掘出所有频繁模式，有效地提高了序列模式挖掘速度。Mooney[14]专注于数据挖掘的子领域序列模式挖掘，研究迄今为止提出的方法和算法。Aloysius[15]提出了一种使用PrefixSpan 算法挖掘用户购买模式的方法，并根据采购模式的顺序将产品放置在货架上。Wright[16使用顺序模式挖掘来自动推断药物之间的时间关系，可视化这些关系，并生成规则以预测可能为患者开具的下一个药物。

由于本文挖掘数据是文本信息，故障序列模式的挖掘算法较传统序列模式挖掘算法发生了很大变化。首先是对文本数据的结构化处理，对不同描述的同一类故障归类，找出相似项目集；之后根据研究对象的特点在故障序列模式挖掘过程中定义最大事件窗口阈值和最小共现度阈值，在此基础上构建了故障序列模式挖掘的算法框架。

# 1 研究方法

针对故障文本进行挖掘的序列模式为重复有间隙型序列模式，其中间隙是指两个事件之间不是必须紧挨。因为不一定连续两次故障之间才存在因果关系，所以考虑一定间隔内按次序发生的故障序列更符合实际。以图1所示序列模式为例，假设最大间隙为2，则对于序列 $\mathrm { A }  \mathrm { B }$ ，用元素的位置表示来代表序列关系，则 $\mathrm { S } _ { \mathrm { l } }$ 中， $1  3$ ， $2  3$ ， $6  7$ ， $6  8$ 满足条件，记录4次， $\mathbf { S } _ { 2 }$ 中 $1  2$ 满足条件，记录1次，两条序列中共记录5次。如果两事件满足一定事件间隔要求，则两事件序列模式的支持度加一。

$$
{ \begin{array} { r l } { S _ { 1 } = \left[ { \begin{array} { c c c c c c c } { A } \end{array} } \right] } & { { \bigtriangleup } } & { { \bigtriangledowns } } & { { \bigtriangleup } } & { { \bigtriangleup } } & { { \bigtriangleup } } & { { \bigtriangleup } } \\ { \mathrm { p o s i t i o n ~ 1 } } & { 2 } & { 3 } & { 4 } & { 5 } & { 6 } & { 7 } & { 8 } \end{array} }
$$

$$
S _ { 2 } = \underbrace { \left. \pmb { A } \right. } _ { 1 } \begin{array} { c c c } { \pmb { \langle B \rangle } } & { \pmb { \bigtriangledown } } & { \pmb { \bigtriangledown } } \\ { 2 } & { 3 } & { 4 } \end{array}
$$

图1重复有间隙型序列模式示例

# 1.1相关概念与定义

下面定义了概念与符号，便于对后面步骤进行准确描述：

在故障序列模式挖掘过程中定义最小相似度阈值、最小频繁度阈值、最大事件窗口阈值、最小支持度阈值和最小共现度阈值。其中最小相似度阈值指文本信息划归为同一类的最低要求，划归成的类称为相似事件集；最小频繁度阈值指相似事件集中最小事件个数，对于低于最小频繁度阈值的事件集，认为这类故障极少发生，不做考虑，达到最小频繁度阈值的事件集称为频繁事件集；最大事件窗口阈值避免了挖掘出来的故障序列模式中事件之间相隔过多，事件之间关联度很小，对预防性维修指导性不够的情况；最小支持度阈值指频繁事件集之间关联程度最低要求；最小共现度阈值避免了挖掘出来的故障序列模式只在小部分产品中频繁发生，不具有普遍性的情况。

a)事件。事件记做 $\boldsymbol { e } _ { i }$ ，满足， $e _ { i } \in p$ 其中 $p$ 为是事件集合。每个事件有一个事件时间标识，表示事件的顺序。

b)事件序列。序列记做 $e _ { i } \to e _ { j }$ ，其中 $e _ { i } , e _ { j }$ 表示事件 $i$ 与 $j _ { \circ }$ 一个序列中的事件有时间先后关系， $e _ { i }$ 出现在 $e _ { j }$ 之前。

c)事件窗口。事件窗口记做 $w i n _ { i j }$ ，表示事件序列 $e _ { i } \to e _ { j }$ 之间间隔的事件数目。

d)事件相似度。事件相似度记作 $X _ { i j }$ ，表示事件 $i$ 与 $j$ 之间相似的程度。

e)相似事件集。相似事件集记做 $S E S _ { k } = [ e _ { 1 } ^ { k } , e _ { 2 } ^ { k } , \ldots , e _ { n } ^ { k } ]$ ，其中 $e _ { i } ^ { k }$ 表示相似事件集 $S E S _ { k }$ 中的 $i$ 事件，集合中任意两个事件均满足最小相似度阈值min_sim。相似事件集中的所有事件被认定为同一类事件。

f)相似事件集频繁度。事件频繁度记做 $f r e q ( k )$ ，是指相似事件集 $S E S _ { k }$ 中事件的个数。

g)频繁事件集。当相似事件集 $S E S _ { k }$ 中事件的个数 $f r e q ( k )$ 大于或等于min_freq时，相似事件集 $S E S _ { k }$ 被认定为频繁事件集，记作 $F E S _ { k } = [ e _ { 1 } ^ { k } , e _ { 2 } ^ { k } , \ldots , e _ { n } ^ { k } ]$ 。其中 min_freq 表示最小频繁度阈值。

h)序列支持度。若存在事件序列 $e _ { i } ^ { p } \to e _ { j } ^ { q }$ ， $e _ { i } ^ { p } , \ e _ { j } ^ { q }$ 分别表示$i$ 和 $j$ 事件，分别属于频繁事件集 $F E S _ { p }$ 、 $F E S _ { q }$ ，且 $w i n _ { i j }$ 小于或等于最大事件窗口阈值max_win，则认定序列模式 $p  q$ 的支持度加一，序列模式支持度记作 $s u p ( p \to q )$ ，具体计算过程如后所示。

i)序列的共现度。一个序列 $p  q$ 的共现度是指该序列出现在不同产品的个数，序列 $p  q$ 共现度可以表示为 $o c c ( p \to q )$ 。

j)序列模式（sequential pattern）。序列 $p  q$ 是一个序列模式，当且仅当满足以下三个约束条件： ${ \mathrm { a } } ) p$ ， $q$ 都是满足min_freq的FES；b)sup( $\displaystyle { \dot { p } }  q { \dot { \overline { { \mathbf { \Lambda } } } } }$ ）≥min_sup；c $) o c c ( p \to q ) ,$ ）≥min_occ。其中 min_sup 指最小支持度阈值，min_occ 指最小共现度阈值

# 1.2文本相似度衡量模型

由于自然语言的特性，不同个体对同一件事情的描述可能有所差别，完全相同的文本信息很少，进而难以找出故障序列模式。先对故障文本描述进行相似度的衡量，以更好的完成序列模式的挖掘。

# 1.2.1文本预处理

使用语言模型进行自然语言处理是建立在词的基础上的而对于中文，词之间没有明确的分界符。因此需要先对故障文本进行分词，才能做进一步的自然语言处理。分词结果中存在一些区分度不高的介词，连词，标点符号等，为了更好地衡量文本相似度，需要进行去停用词的处理，经过分词的结果进行去停用词的处理。

# 1.2.2文本向量化

词的分布式表示是指一个稠密的低维的实数向量。例如$[ 0 . 7 9 2 , - 0 . 1 7 7 , - 0 . 1 0 7 , 0 . 1 0 9 , - 0 . 5 4 2 , . . . ] { \circ }$ 。利用Doc2Vec 模型将每一个分完词的句子被映射成一个独立的向量，Doc2Vec 模型能表示词和词之间的语义关系，考虑了词的先后顺序，能够很好地将文本向量化。本文使用的Doc2Vec训练模型如下：

model $\mathbf { \Sigma } = \mathbf { \Sigma }$ Doc2Vec(sentences, size, window,min_count, workers,min_alpha)

其中 sentences：句子库；size：特征向量维度；window:要预测的词和文档中用来预测的上下文词之间的最大距离；alpha：初始学习速率；min_count：忽略总频数小于此的所有的词；workers：用来训练模型的电脑线程数量。

# 1.2.3相似度计算

对于已经向量化的文本，我们利用余弦相似度进行文本之间相似度计算，余弦相似度通过测量两个向量的夹角的余弦值来度量它们之间的相似性。计算公式如下：

$$
\begin{array} { r } { s i m i l a r i t y = \frac { \sum _ { i = 1 } ^ { n } ( A _ { i } \times B _ { i } ) } { \sqrt { \sum _ { i = 1 } ^ { n } ( A _ { i } ) ^ { 2 } } \times \sqrt { \sum _ { i = 1 } ^ { n } ( B _ { i } ) ^ { 2 } } } } \end{array}
$$

其中： $A _ { i }$ 和 $B _ { i }$ 分别代表向量 $A$ 和 $B$ 的各分量。由相似度衡量的特性，可知相似度矩阵是对角线上均为1的对称矩阵。

# 1.3算法流程

本算法设计流程如下主要包括建立故障文本相似度衡量模型和设计故障序列挖掘算法两部分。在故障文本相似度衡量之前，首先要对故障文本信息进行相关处理。在此基础上进行故障序列模式挖掘，最后通过实例验证该算法算法。设计流程如图2所示。

# 2 算法构建

算法主要包括两部分，一是在文本相似度衡量基础上进行频繁事件集的挖掘，二是在频繁事件集基础上进行故障序列模式挖掘。

# 2.1频繁事件集挖掘

# 2.1.1算法描述

a)通过故障文本相似度衡量模型得到如表1所示的相似

度矩阵。

![](images/af5377b21526d3b1bdc0786a64f22c9e37658b6de2623cff1a7520f18ad9ca91.jpg)  
图2本文算法设计流程

表1文本相似度矩阵  

<html><body><table><tr><td>事件</td><td>1</td><td>2</td><td>：</td><td>n</td></tr><tr><td>1</td><td>1</td><td>X12</td><td>…</td><td>X1n</td></tr><tr><td>2</td><td>X21</td><td>1</td><td></td><td>X2n</td></tr><tr><td>…</td><td></td><td></td><td>…</td><td></td></tr><tr><td>n</td><td>Xn1</td><td>Xn2</td><td>…</td><td>1</td></tr></table></body></html>

其中 $X _ { i j }$ 表示事件 $i$ 与事件 $j$ 的相似度，显然当 $i { = } j$ 时 $X _ { i j } { = } 1$ 。b)找出相似事件集，给定最小相似度阈值min_sim及式(2)，

$$
\begin{array} { r } { \{ X _ { i j } \geq m i n \_ s i m , \ X _ { i j } = 1 } \\ { \{ X _ { i j } < m i n \_ s i m , \ X _ { i j } = 0 } \end{array}
$$

通过式（2）转换得到如表2所示的相似事件集矩阵。

表2转化后的相似度矩阵  

<html><body><table><tr><td>事件</td><td>1</td><td>2</td><td>：</td><td>n</td></tr><tr><td>1</td><td>1</td><td>0或1</td><td></td><td>0或1</td></tr><tr><td>2</td><td>0或1</td><td>1</td><td>…</td><td>0或1</td></tr><tr><td></td><td></td><td>…</td><td></td><td></td></tr><tr><td>n</td><td>0或1</td><td>0或1</td><td>…</td><td>1</td></tr></table></body></html>

显然矩阵中值为1代表两事件为相似事件，属于同一事件集合，值为0代表两事件不相似，从而找出相似事件集 $S E S _ { k }$ 。

c找出频繁项目集，下面计算相似事件集频繁度：

$$
\begin{array} { r } { f r e q _ { p } = \sum _ { j = 1 } ^ { n } X _ { i j } , i , p = 1 , 2 , \dots , n } \end{array}
$$

其中 $X _ { i j }$ 表示时间 $i$ 与事件 $j$ 的相似度, $X _ { i j } { = } 1$ 或 $0 , \ f r e q _ { p }$ 表示第$i$ 个事件所在相似事件集 $S E S _ { p }$ 的事件个数。

给定最小频繁度阈值min_freq,

$$
\begin{array} { r } { \left\{ f r e q _ { p } \geq m i n \_ f r e q , \mathcal { H } _ { k H } ^ { E B M } \not \exists H / \# \not \exists p \right. } \\ { \left. \left\{ f r e q _ { p } < m i n \_ f r e q , \right. \mathop { \pm } \beta _ { k } ^ { \not \perp } \not \equiv / 4 \not \emptyset p \right. } \end{array}
$$

根据式(4)得到若干频繁事件集 $F E S _ { k }$ 。

# 2.1.2算法流程

频繁事件集挖掘算法，流程如图3所示。

2.2.1算法描述

![](images/2bb767e9688bc6cd74eab9f2d41eb3fb2c7418c4f49d423c284747f15945e908.jpg)  
图3频繁事件集挖掘流程

a)对所有频繁事件集 $F E S _ { k }$ 中的事件按照飞机ID进行划分，划分结果如表3所示。

# 2.2 序列模式挖掘

![](images/3aae852473c4d71dd4eac650e45d08415c13f93eb0cac09772fcd50d8ddd961e.jpg)  
图4序列模式挖掘流程

表3频繁事件集  

<html><body><table><tr><td rowspan="2">FES</td><td colspan="3">ID</td></tr><tr><td>1</td><td>：</td><td>n</td></tr><tr><td>1</td><td>ea</td><td>：</td><td>er</td></tr><tr><td>2</td><td>e</td><td>：</td><td>es</td></tr><tr><td>：</td><td>：</td><td>：</td><td>：</td></tr><tr><td>m</td><td>em</td><td>：</td><td>em</td></tr></table></body></html>

其中 $e _ { i j } ^ { p }$ 表示发生在第 $i$ 架飞机上的第 $j$ 个故障事件，并且故障事件 $j$ 属于频繁事件集 $p$ 。

序列模式挖掘算法流程如图4所示。

b)对单架飞机进行故障序列模式挖掘，方法如下：

在第 $i$ 架飞机中，对于频繁事件集 $p$ 与频繁事件集 $q$ 中的故障序列， $p$ 中的故障事件为 $e _ { i a } ^ { p }$ ， $q$ 中的故障事件为 $e _ { i b } ^ { q }$ ，给定最大窗口事件max_win，

$$
i f \colon \ w i n _ { a \to b } \leq m a x \_ w i n , \ \left\{ \operatorname* { s u p } _ { 0 \csc ( p \to q ) } = \operatorname* { s u p } _ { 0 \csc ( p \to q ) } + 1 \right.
$$

其中 $w i n _ { a  b }$ 表示故障a、b之间间隔的故障事件数， $\mathsf { s u p } ( \boldsymbol { p }$ $ q \dot { . }$ 表示序列模式 $p \to q$ 的支持度， $\operatorname { o c c } ( p \to q )$ 表示序列模式 $p$ $\to q$ 的共现度。

利用该方法，算出序列模式 $| p \to q$ 在该架飞机上的的支持度和共现度。依次迭代，计算出所有频繁事件集之间序列模式的支持度和共现度。

c)迭代步骤b)，依次对每架飞机进行故障序列挖掘。将序列模式在不同飞机上的支持度、共现度累加。

d)检验各序列模式是否满足最小支持度阈值、最小共现度阈值。对于序列模式 $p  q$ ，若满足式(6)

$$
\left\{ \begin{array} { l l } { s u p ( p \to q ) \geq m i n \_ s u p } \\ { o c c ( p \to q ) \geq m i n \_ o c c } \end{array} \right.
$$

其中min_sup表示最小支持度阈值，min_occ表示最小共现度阈值，则认定序列模式 $| p \to q$ 成立。

# 2.2.2算法流程

# 3 实例验证

使用某型3架飞机共计20条故障情况文本信息作为实例对象，其中第1架飞机和第2架飞机分别有7条故障情况文本描述，第3台产品有6条故障情况文本描述，需要在其中找出故障序列模式。对应产品ID和故障序号在表4中列出。

表4故障文本描述  

<html><body><table><tr><td>ID FES</td><td>1</td><td>2</td><td>3</td></tr><tr><td rowspan="3">1</td><td></td><td>4 发滑油散热</td><td>3发滑油散</td></tr><tr><td>2 发滑油散热</td><td>器蜂窝结构渗</td><td>热器蜂窝结</td></tr><tr><td>器蜂窝孔渗油</td><td>油</td><td>构漏油</td></tr><tr><td rowspan="3">2</td><td>4 发滑油散热</td><td>起动发电机起</td><td>2 发滑油散</td></tr><tr><td>器蜂窝结构渗</td><td>动电流超差</td><td>热风门不工</td></tr><tr><td>油</td><td>3发滑油散热</td><td>作</td></tr><tr><td rowspan="2">3</td><td>3发滑油散热 器风门电机有</td><td>器蜂窝结构漏</td><td>4 发滑油散 热器蜂窝结</td></tr><tr><td>卡滞现象</td><td>油</td><td>构漏油</td></tr><tr><td rowspan="2">4</td><td>无线电高度表</td><td>2 发滑油散热</td><td>4发航前起</td></tr><tr><td>照明灯不亮</td><td>器蜂窝孔渗油</td><td>动电流差大</td></tr><tr><td rowspan="2">5</td><td>2 发滑油散热</td><td>无线电高度表</td><td>2 发滑油散</td></tr><tr><td>器风门不工作</td><td>指示器照明灯</td><td>热器蜂窝孔</td></tr><tr><td rowspan="3">6</td><td>右1组油量表</td><td>不亮 2 发滑油散热</td><td>渗油 3发滑油散</td></tr><tr><td>传感器多指 1000KG</td><td>风门不工作</td><td>热风门不能 自动关闭</td></tr><tr><td>3 发滑油散热 器蜂窝结构漏</td><td>3发散热器蜂 窝结构漏油</td><td></td></tr></table></body></html>

# 3.1文本预处理

故障文本示例如表5所示。

表5故障文本示例  

<html><body><table><tr><td>故障情况文本（共计20条）</td></tr><tr><td>2发滑油散热器蜂窝孔渗油</td></tr><tr><td>4发滑油散热器蜂窝结构渗油</td></tr><tr><td>3发滑油散热器风门电机有卡滞现象</td></tr><tr><td>无线电高度表照明灯不亮</td></tr></table></body></html>

对故障文本进行分词、去停用词，利用Python 语言中的jieba分词包进行处理，得到结果如表6所示。

表6预处理之后的文本  

<html><body><table><tr><td>故障情况文本</td></tr><tr><td>2//发滑油//散热器//蜂窝//孔//渗油</td></tr><tr><td>4//发滑油//散热器//蜂窝//结构//渗油</td></tr><tr><td>3//发滑油//散热器//风门//电机//有卡滞//现象</td></tr><tr><td>无线电//高度表//照明//灯不亮</td></tr></table></body></html>

# 3.2计算故障文本相似度

运用Doc2Vec模型进行文本表示，其中模型参数选择如下：model=Doc2Vec(sentences,size $\displaystyle { \cdot = I 0 } ,$ window $\scriptstyle \gamma = 3$ ,min_count $\scriptstyle \cdot = 3$ ，workers $\scriptstyle \cdot = 4 ,$ （204tin_alpha $_ { : = 0 . 0 0 2 }$ 一

使用余弦相似度来进行相似度的衡量，结果如下：

$$
\left[ { \begin{array} { c c c c c c c c } { 1 } & { 0 . 3 9 1 } & { 0 . 0 2 5 } & { \cdots } & { 0 } & { 1 } & { 0 . 0 0 8 } \\ { 0 . 3 9 1 } & { 1 } & { 0 . 0 2 8 } & { \cdots } & { 0 . 1 8 2 } & { 0 . 3 9 1 } & { 0 . 0 0 9 } \\ { 0 . 0 2 5 } & { 0 . 0 2 8 } & { 1 } & { \cdots } & { 0 } & { 0 . 0 2 5 } & { 0 . 1 0 8 } \\ { \vdots } & { \vdots } & { \vdots } & { \ddots } & { \vdots } & { \vdots } & { \vdots } \\ { 0 } & { 0 . 1 8 2 } & { 0 } & { \cdots } & { 1 } & { 0 } & { 0 } \\ { 1 } & { 0 . 3 9 1 } & { 0 . 0 2 5 } & { \cdots } & { 0 } & { 1 } & { 0 . 0 0 8 } \\ { 0 . 0 0 8 } & { 0 . 0 0 9 } & { 0 . 1 0 8 } & { \cdots } & { 0 } & { 0 . 0 0 8 } & { 1 } \end{array} } \right]
$$

# 3.3故障频繁项目集挖掘

设定最小相似度阈值 $m i n \_ s i m = 0 . 8$ ，将故障文本描述的相似度矩阵转化为0-1矩阵来方便频繁度的计算。维度为 $2 0 { \times } 2 0$ 的0-1矩阵如下：

$$
\left[ { \begin{array} { l l l l l l l } { 1 } & { 0 } & { 0 } & { \cdots } & { 0 } & { 1 } & { 0 } \\ { 0 } & { 1 } & { 0 } & { \cdots } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 1 } & { \cdots } & { 0 } & { 0 } & { 0 } \\ { \vdots } & { \vdots } & { \vdots } & { \ddots } & { \vdots } & { \vdots } & { \vdots } \\ { 0 } & { 0 } & { 0 } & { \cdots } & { 1 } & { 0 } & { 0 } \\ { 1 } & { 0 } & { 0 } & { \cdots } & { 0 } & { 1 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { \cdots } & { 0 } & { 0 } & { 1 } \end{array} } \right]
$$

各条故障文本描述的频繁度为：[3,3,1,2,3,1,4,3,1,4,3,2,3,1,4,3,6,1,3,1]。

设定最小频繁度阈值min_freq $= 3$ ，则利用伪代码程序计算可以得到频繁事件集文本序号为[1,2,5,7,8,10,11,13,15,16,17, 19]。

相似频繁项目集结果如表7所示。

表7频繁事件集  

<html><body><table><tr><td rowspan="2">序号</td><td colspan="3">飞机ID</td></tr><tr><td>1</td><td>2</td><td>3</td></tr><tr><td>1</td><td>1</td><td>11</td><td>19</td></tr><tr><td>2</td><td>2</td><td>8</td><td>17</td></tr><tr><td>5</td><td>5</td><td>13</td><td>16</td></tr></table></body></html>

<html><body><table><tr><td>7</td><td>7</td><td>10</td><td>[15,17]</td></tr><tr><td>8</td><td>2</td><td>8</td><td>17</td></tr><tr><td>10</td><td>7</td><td>10</td><td>[15,17]</td></tr><tr><td>11</td><td>1</td><td>11</td><td>19</td></tr><tr><td>13</td><td>5</td><td>13</td><td>16</td></tr><tr><td>15</td><td>7</td><td>10</td><td>[15,17]</td></tr><tr><td>16</td><td>5</td><td>13</td><td>16</td></tr><tr><td>17</td><td>[2,7]</td><td>[8,10]</td><td>[15,17]</td></tr><tr><td>19</td><td>1</td><td>11</td><td>19</td></tr></table></body></html>

# 3.4序列模式挖掘

设定最大事件窗口闽值max_win $^ { = 4 }$ ，最小支持度阈值min_sup $\scriptstyle 1 = 4$ ，产品最小共现度阈值min_occ ${ \mathrm { \Omega } } { = } 2$ ，利用伪代码程序计算可以得到挖掘出故障序列模式，结果如表8所示。

表8故障序列模式挖掘结果  

<html><body><table><tr><td>序列模式</td><td></td><td>前向故障</td><td>后向故障</td><td>sup</td><td>OCC</td></tr><tr><td rowspan="2">1</td><td>17→1</td><td></td><td>4发滑油散热器蜂窝2发滑油散热器蜂窝</td><td>4</td><td>2</td></tr><tr><td></td><td>结构漏油 4发滑油散热器蜂窝2发滑油散热器蜂窝</td><td>孔渗油</td><td></td><td></td></tr><tr><td>2</td><td>17→11</td><td>结构漏油</td><td>孔渗油</td><td>4</td><td>2</td></tr><tr><td rowspan="2">3</td><td>17→19</td><td>4发滑油散热器蜂窝2发滑油散热器蜂窝</td><td></td><td>4</td><td>2</td></tr><tr><td></td><td>结构漏油</td><td>孔渗油</td><td></td><td></td></tr></table></body></html>

可以得到，满足条件的序列模式为{"4发滑油散热器蜂窝结构漏油 $\cdot \to \ { \cdot } _ { 2 }$ 发滑油散热器蜂窝孔渗油"}，根据序列模式支持度和共现度的结果来看，在该算法框架下该序列模式共发生4次，在2架飞机上出现过。通过与文本数据验证，找出的该故障序列关系是客观存的。根据结果来看，在产品的维修保障过程中，如果有发动机的滑油散热器发生漏油或渗油等问题，各个发动机的滑油散热器都应该去做检查，做到防患于未然。

# 4 结束语

文本记录的故障信息，其表达形式各异，结构化程度差，现有的序列模式挖掘算法不能直接对文本数据进行挖掘。针对文本信息，本文提出了一种基于文本相似度衡量的故障序列模式挖掘算法，其与现有方法的区别如下：

a）由于文本信息的特殊性，相同信息的表达千差万别，本文提出的文本相似度衡量模型，可以有效的将相同意义的故障文本归为一类，将结构化程度差的文本数据整合归类，在此基础上进行序列模式挖掘。

b)本文针对文本数据提出了最小频繁度概念，针对序列模式挖掘提出了最大事件窗口、最小共现度两个概念，可以确保挖掘出的序列模式是普遍存在的。

实例验证表明，本文提出的算法是正确有效的，对于识别故障时间关系，进行故障预测和维修决策提供支持。

# 参考文献：

[1]吴熠潇．中文分词相关算法研究[J].科技经济导刊,2018(2):122-123.

(Wu Yixiao.Research on Chinese word segmentation algorithm [J]. Technology and Economic Guide,2018 (2): 122-123.)   
[2]郑文超，徐鹏．利用Word2vec 对中文词进行聚类的研究[J]．软件， 2013,34 (12):160-162.(Zheng Wenchao,Xu Peng.Research on Chinese word Clustering with word2vec [J]. Software,2013,34 (12): 160-162.)   
[3] 张志昌，周慧霞，姚东任，等．基于词向量的中文词汇蕴涵关系识别 [J]．计算机工程,2016,42(2):169-174.(Zhang Zhichang,Zhou Huixia, Yao Rendong,et al. Recognition of Chinese lexical entailment relation based on word vector[J]. Computer Engineering,2016,42 (2): 169-174.)   
[4]周练.Word2vec 的工作原理及应用探究[J].图书情报导刊,2015,25(2): 145-148.(Zhou Lian. Exploration of the working principle and application of word2vec [J].Sci-tech Information Development and Economy,2015,25 (2): 145-148.)   
[5]唐明，朱磊，邹显春．基于Word2Vec 的一种文档向量表示[J].计算机 科学，2016,43(6):214-217.(Tang Ming,Zhu Lei， Zou Xianchun. Document vector representation based on word2vec [J]. Computer Science, 2016, 43 (6): 214-217.)   
[6]Zhang Dongwen,Xu Hua,Su Zencai,et al. Chinese comments sentiment classification based on word2vec and SVM perf [J].Expert Systems with Applications,2015,42 (4): 1857-1863.   
[7]殷耀明，张东站．基于关系向量模型的句子相似度计算[J].计算机工 程与应用，2014，50(2):198-203.(Yin Yaoming，Zhang Dongzhan. Sentence similarity computing based on relation vector model[J]. Computer Engineering and Applications,2014,50 (2):198-203.)   
[8]Tian Junfeng,Lan Man,Wu Yuanbin,et al.An adversarial joint learning model for low-resource language semantic textual similarity [C]//Advances in Information Retrieval.2018: 89-101.   
[9]苗雪连．间隙约束序列模式挖掘的对比研究[J].网络安全技术与应用, 2017 (2): 66-67. (Miao Xuelian. Comparative study of sequential pattern mining with gap constraints [J].Network Security Technology and Application,2017 (2): 66-67.)   
[10]Krishna B.PrefixSpan:Mining Sequential Patterns by Prefix-Projected Patern [J].International Journal of Computer Science & Engieering Survey,2012,2(4): 111-122.   
[11] Le B,Hai D,Truong T,et al.FCloSM,FGenSM: two efficient algorithms for mining frequent closed and generator sequences using the local pruning strategy[J].Knowledge& Information Systems,2017,55 (3):1-37.   
[12] Yan Xiaowu, Zhang Jifu,Xun Yaling,et al.A paralel algorithm for mining constrained frequent patterns using MapReduce [J]. Soft Computing,2017, 21 (9): 2237-2249.   
[13]武优西，周坤，刘靖宇，等．周期性一般间隙约束的序列模式挖掘[J]. 计算机学报,2017,40(6):1338-1352.(Wu Youxi, Zhou Kun,Liu Jingyu, et al.Mining Sequential Pattern with Periodic General Gap Constraints [J]. Chinese Journal of Computers,2017,40(6):1338-1352.)   
[14] Mooney C，Roddick J. Sequential pattern mining:approaches and algorithms [J].ACM Computing Surveys,2013,45 (2):1-39.   
[15] Aloysius G,Binu D.An approach to products placement in supermarkets using PrefixSpan algorithm [J].Journal of King Saud University of Computer & Information Sciences,2013,25(1): 77-87.   
[16] Wright A,Wright T,Mccoy A,et al. The use of sequential pattern mining to predict next prescribed medications [J].Biomedical Informatics,2015,53 (C): 73.