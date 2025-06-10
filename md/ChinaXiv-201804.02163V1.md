# 基于语义关系约束和词语关系信息的句向量研究

夏小强，邵堃

(合肥工业大学计算机与信息学院,合肥 230009)

摘要：针对现有的句向量学习方法不能很好的学习关系知识信息、表示复杂的语义关系，提出了基于PV-DM 模型和关系信息模型的关系信息句向量模型（RISV），该模型是将PV-DM模型作为句向量训练基本模型，然后为其添加关系信息知识约束条件，使改进后模型能够学习到文本中词语之间的关系，并将关系约束模型（RCM）模型作为预训练模型，使其进一步整合语义关系约束信息，最后在文档分类和短文本语义相似度两个任务中验证了RISV模型的有效性。实验结果表明，采用RISV模型学习的句向量能够更好地表示文本。

关键词：句向量；RISV模型；PV-DM模型；关系信息；预训练 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2018.01.0029

# Sentence vector based on semantic relationship constraints and word relationship information

Xia Xiaoqiang, Shao Kun (School ofComputer&Information,Hefei UniversityofTechnology,Hefei230oo9,China)

Abstract:In viewof the factthattheexisting sentence vectorlearning method cannot wellearn therelational knowledge informationand expressthecomplicated semantic relation,this paper proposedarelational information sentence vectormodel (RISV)basedonthePV-DMmodeland therelational informationmodel.This modelused thePV-DMmodelasthe basic model ofsentence vectortraining,and thenaddedthe knowledgeconstraintofrelational informationtomake theimproved modelcan learn therelationship betweenthewords inthetextand uses theRCMmodelas Pre-training model to further integrate the informationofthesemanticrelationshipconstraints,andfiallyvalidatesthevalidityoftheRISVmodelintwotasks:document classificationand short text semantic similarity.The experimentalresults show that sentence vectors learned byRISVmodel can better represent the text.

Key Words: sentence vector; RISV Model; PV-DM Model; Relationship information; Pre-training

# 0 引言

词向量是一种将词表示为连续向量的技术，是自然语言处理中的一个重要研究课题。自2013年Mikolov 等人[1提出了word2vec 模型，词向量在POS Tagging[2]、句法依存分析[3]、机器翻译[4以及情感分析等领域取得了丰硕的成果。在大部分的任务中，学习词向量只是工作的第一步，比如说情感分析，需要用学习到的词向量有效的表示文档，这部分是研究工作的另一个难点。

国内外学者在基于词向量的基础上作出了许多重大贡献。唐明等人[5]在word2vec 模型的基础上，结合TF-IDF 算法用来表示文档向量。何天翔等人[利用大量语料库以及同义词集合构建情感词网，对短文本特征稀疏、信息量不足等问题，提出了结合情感词网的中文短文本情感倾向分析。苗祥等人[将特征代表词的同义特征词所对应的情感词加入到该特征代表词的情感词集中,有效提高了特征代表词的情感分析的准确性。QLiu 等在15 年提出SWE 模型[8]，该模型在 skip-gram 基础上组合表示成不等式约束的词语间的关系（同义，上下位等）。Xu等人[9则基于Skip-gram 模型，提出融合关系知识和分类知识的训练框架 RC-NET。2016年Nguyen 等人[10]尝试在 Skip-gram模型基础上加入词汇对比信息共同训练，提出了DLCE 模型，使得训练得到的词向量能有效识别同义词和反义词。除了基于词向量的工作，Le 等人[1I]在word2vec 模型的基础上添加了paragraphid，提出了doc2vec 模型，通过该模型可以直接有效的学习文本句向量。

句向量常见学习方法有求单一文本词向量的平均值[12]，利用 TF-IDF 算法加权后求平均值，对词向量进行聚类[13]，以及使用doc2vec 模型等。这些方法在一般的学习任务中可以得到不错的结果，但却没有考虑到文本之间语义信息关系和词汇信息，近些年，Liu等人先后提出了SWE模型[8以及DLCE模型[10],这些模型尝试在word2vec 模型基础上，以不同的方式融合不同的结构化信息，取得一定的效果。如DLCE 模型在同义反义识别任务上表现优异，但在词向量的语义相似性和语义相关性评估任务中，在不同数据集上表现差异较大（SIMLEX999，MEN3000，WS353），模型稳定性不足，SWE模型在词向量的语义相似性和语义相关性评估任务上有提升，但在同义反义识别任务上却表现不佳。本文在此基础上，借鉴了SWE 模型添加词语关系信息和RCM模型[14]中关系约束的思想提出了本文的关系信息句向量模型（RISV）训练模型，与SWE 模型相比，本文提出的RISV模型在PV-DM引入了关系信息，并用关系约束（RCM）模型作为预训练模型，所以能够一定程度的表达复杂的语义关系。最后，在文档分类和短文本语义相似度这两个任务中对模型进行了验证。

# 1 学习句向量

# 1.1 RWE模型

知识图谱中的知识，一般表示为三元组(h,r,t)的形式，其中r表示t关联的多种不同的关系,例如样本(vegetable,_hyponymy,tomato)。在提取三元组数据后，需要对词语的关系建立表示。例如对于三元组(h,r,t)，若三元组是事实信息，则有 $\scriptstyle \mathrm { h + r } \ \approx { \mathrm { t } }$ ，即$\scriptstyle \mathrm { h + r }$ 对应向量应与t更相近，该模型称为关系信息模型。模型的输入层是目标词t的对应的三元组集合 $( \mathrm { h , r , t } )$ ，投影层做了恒等投影，输出层是在语料中预测目标词。

在CBOW语言模型训练中，加入短语关系等信息，使得学习获得的词向量能够很好地表示丰富的语义关系。在此基础上可以得到关系信息词向量模型（relationalinformationwordembedding）。目标函数如下：

$$
L _ { r i w e } = \sum _ { i = 1 } ^ { C } ( \log \mathrm { p } ( w _ { i } \mid w _ { i - c } ^ { i + c } ) + \gamma \sum _ { \gamma \in R _ { w _ { i } } } \log p ( w _ { i } \mid h + r ) )
$$

其中：函数前半部分是CBOW模型目标函数，后半部分是关系信息模型目标函数， $\gamma$ 是调权参数，C是训练语料库的大小。$p ( w _ { i } \mid h + r )$ 表示已知目标词与词 $\mathbf { h }$ 之间存在关系r，预测目标词为 $\mathbf { W } _ { i }$ 的概率，具体计算公式如下：

$$
p ( w _ { i } \mid h + r ) = \frac { \exp ( { e _ { h + r } } ^ { T } \theta _ { w _ { i } } ) } { \sum _ { j = 1 } ^ { V } \exp ( { e _ { h + r } } ^ { T } \theta _ { w _ { i } } ) }
$$

其中： $\mathbf { e } _ { h + r }$ 表示向量 $\mathbf { e } _ { h }$ 和 $ { \mathbf { e } } _ { r }$ 的线性加和，即 $\mathbf { e } _ { h + r } = \mathbf { e } _ { h } + e _ { r }$ ，$\theta _ { \mathrm { w } _ { i } }$ 表示词 $\mathbf { W } _ { i }$ 的分类参数。

# 1.2 RISV模型

文本中词语之间具有很多复杂的语义关系，例如上下位关系，在“猫坐在桌子上的垫子里”这个文本中，“猫”是“坐在”的上位词，“桌子”是“坐在”的下位词，这里“坐在”的下位词除了“桌子”外，还有有“垫子”等，具有相同上位词的“桌子”和“垫子”，从某种意义上来说应该是相似或者相关的，但Word2vec 模型只是利用大规模语料库中的词语进行训练，所得的词向量只能学习到文本上下文信息，却无法学习到这种词语间的关系，所以其他复杂的语义关系也很难充分表达。

关系信息词向量模型（RWE）主要是基于CBOW模型来学习词向量，对于一些任务来说，仍需要将训练好的词向量转换为句向量，所以本文中将关系信息模型引入到PV-DM模型，得到关系信息句向量模型（relationalInformation sentencevector,RISV），RISV模型目标函数如下：$L _ { r i s v } = \sum _ { i = 1 } ^ { c } ( \sum _ { d \in D } \log \mathrm { p } ( w _ { i } \left| C o n t ( w _ { i - c } ^ { i + c } , d ) \right) + \gamma \sum _ { \gamma \in R _ { w _ { i } } } \log p ( w _ { i } \left| h + r ) \right)$ (3）其中：d表示 paragraphid 向量，D表示 paragraph id 向量空间。cont $( w _ { i - c } ^ { i + c } , d )$ 表示词 wi 的上下文以及 paragraph id 向量。

使用 Negative Sampling对RISV目标函数进行优化，则对于样本（u,wi)来说，如果 $\mathrm { ~  ~ u ~ }$ 的目标词满足条件E视为正样本，通过负采样的其他词成为负样本。则指示函数为

$$
\delta ( w _ { i } \mid u ) = \ S _ { 0 , w _ { i } \not = E } ^ { 1 , w _ { i } = E }
$$

对于RISV目标函数的求解可以分为前半部分和后半部分，则前半部分函数为

$$
L _ { \mathrm { f r o n t } } = \sum _ { d \in D } \sum _ { i = 1 } ^ { C } \log \mathfrak { p } ( w _ { i } \mid C o n t e x t ( w _ { i - c } ^ { i + c } , d ) )
$$

使用随机梯度下降算法对其进行求解可得

$$
\theta _ { u } = \theta _ { u } + \eta ( \delta ( w _ { i } \left| u \right. ) - \sigma ( \boldsymbol { X } _ { w } ^ { T } \boldsymbol { \theta } _ { u } ) ) \boldsymbol { X } _ { w }
$$

$$
V ( w ) = V ( w ) + \eta \sum _ { j = 2 } ^ { l ^ { w } } ( \delta ( w _ { i } \left| u \right. ) - \sigma ( X _ { w } ^ { T } \theta _ { u } ) ) \theta _ { u }
$$

其中： $X _ { \scriptscriptstyle w }$ 表示词向量的和或者由词向量连接成，$\sigma ( x ) = \exp \{ x \} / ( 1 + \exp \{ x \} )$ ， $\eta$ 为调权参数， $\mathrm { V } ( \mathrm { w } )$ 为句向量。 $\mathrm { L } _ { f r o n t }$ 函数中（4）式中条件E为是否为目标词。

后半部分函数为

$$
L _ { \mathrm { r e a r } } = \sum _ { i = 1 } ^ { C } \sum _ { \gamma \in R _ { w _ { i } } } \log p ( w _ { i } \mid h + r )
$$

同理，采用随机梯度下降算法进行求解可得：

$$
\begin{array} { l } { { \displaystyle \theta _ { \mathrm { u } } = \theta _ { \mathrm { u } } + \alpha ( \delta ( w _ { i } | u ) - \sigma ( e _ { h + r } ^ { T } \theta _ { \mathrm { u } } ) ) e _ { h + r } } } \\ { ~ } \\ { { \displaystyle { { \bf e } _ { h } = { \bf e } _ { h } + \alpha \sum _ { u \in U } ( \delta ( w _ { i } | u ) - \sigma ( e _ { h + r } ^ { T } \theta _ { u } ) ) \theta _ { u } } } } \\ { { \displaystyle { { \bf e } _ { r } = { \bf e } _ { r } + \alpha \sum _ { u \in U } ( \delta ( w _ { i } | u ) - \sigma ( e _ { h + r } ^ { T } \theta _ { u } ) ) \theta _ { u } } } } \end{array}
$$

其中：U 表示关系信息集， $\alpha$ 表示调权参数， $\mathrm { \Delta L _ { r e a r } }$ 函数中式（4）中条件E为是否满足关系信息集。则 $\boldsymbol { e } _ { h + r }$ 更新可以由公式 $\mathbf { e } _ { h + r } = \mathbf { e } _ { h } + e _ { r }$ 完成。

RISV模型是在dco2vec模型训练中，引入了关系信息知识作为监督，共享词向量，从目标函数来看，PV-DM模型与关系信息模型线性组合，二者都对句向量更新有着一定影响，调权参数平衡二者关系，最终使用随机梯度下降算法不断优化参数，得到最优解。

与RWE模型相比，本文提出的RISV模型可以直接训练出句向量，省略了词向量到句向量转换的过程。另外，RISV模型添加了paragraphid 信息，被用来记忆当前文本或文章主题中漏掉的信息，因此造成信息损失较小，在情感分析等任务中相对于RWE等模型来说更具优势。

# 1.3预训练

在深度学习中，模型预训练起着重要作用[15]。例如，在YuM[14]的工作中使用了CBOW模型等进行预训练，取得了很好的效果。受YuM等工作的启发，本文使用RCM模型进行预训练。

主要思想为假设Rw为单词 $\mathbf { w }$ 在关系集R中的唯一表示。目标是最大化关系语料库 $\mathrm { ~  ~ N ~ }$ 中全部单词关系的和：

$$
{ \frac { 1 } { N } } \sum _ { i = 1 } ^ { N } \sum _ { w \in R _ { w _ { i } } } \log p ( w | w _ { i } )
$$

其中 $p ( w \vert w _ { i } ) { = } \mathrm {{ e x p } } ( X _ { _ { w _ { i } } } ^ { T } V _ { _ w } ) / \sum _ { _ { w } } { \mathrm { e x p } } ( X _ { _ { w _ { i } } } ^ { T } V _ { _ w } )$ ,x,V分别表示输入与输出的词向量。这个模型被称为RCM模型。通过RCM模型的预训练，然后将预训练词向量作为RISV模型的输入，某些参数作为RISV模型的初始值。在本文中，RCM模型可以理解为一种特殊的先验分布带来的正则化，有别于L1与 L2正则化，这种正则化项和 semi-superviesed 以及 earlystopping 的原理比较类似。最终的实验效果是给RISV模型关系信息的一种补充，为模型增加了关系约束知识。

# 2 实验与结果分析

实验数据文本语料来自维基百科，爬取数据后，对数据进行去除超链接和中间数据，将数字用数字单词代替等预处理。预处理后总共有一亿个左右单词，然后筛选出出现超过五次的单词，组成包含202363个单词的语料库。训练RCM模型使用“词汇’版本的PPDB（没有短语）语料库，然后筛选出在文本语料库出现的关系对，然后删除重复的关系对，例如，如果 ${ \ < } \mathrm { X } , \mathrm { Y } { > }$ 包含在PPDB中，则删除 ${ \bf < Y , X > }$ 关系对。三元组语料来自Freebase，用于关系信息模型的训练。具体信息如表1所示。

表1实验数据表格  

<html><body><table><tr><td>数据</td><td>来源</td><td>词库</td><td>测试集</td></tr><tr><td>文本语料</td><td>维基百科</td><td>202363</td><td></td></tr><tr><td>PPDB 语料</td><td>PPDB</td><td>57829</td><td>1583</td></tr><tr><td>三元组</td><td>Freebase</td><td>69023</td><td>1657</td></tr></table></body></html>

实验数据部分示例如表2所示。

表2实验数据部分实例  

<html><body><table><tr><td>数据</td><td>示例</td></tr><tr><td rowspan="5">文本语料</td><td>Anarchism is a political philosophy that advocates self-</td></tr><tr><td>governed societies based on voluntary institutions.These</td></tr><tr><td>are often described as stateless societies,although several</td></tr><tr><td>authors have defined them more specifically as institutions</td></tr><tr><td>based on non-hierarchical free associations.</td></tr><tr><td rowspan="4">PPDB 语料</td><td><planning,plans>,<monitoring,monitor>,</td></tr><tr><td><seemed,suggested>,<pyramidal,pyramid></td></tr><tr><td><The Trail Blazer,is-a,TVEpisode>,</td></tr><tr><td><The Trail Blazers,Country of origin,United States of</td></tr><tr><td rowspan="3">三元组</td><td>America>,</td></tr><tr><td><Playing Guitar,is-a,Book>,</td></tr><tr><td><Playing Hardball,is-a,TVEpisode></td></tr></table></body></html>

# 2.1文档分类任务

# 2.1.1实验数据

测试语料库来自Reuters Corpus,Volume I(RCV1)[16]，该语料库有806791个手动分类好的新闻，共有三个大的分类目录，包括主题，工业和地区。本文主要针对主题这个目录的分类，该目录包括四个主题，分类为C，E，G和M，其中C表示公司或工业类，E表示经济类，G表示政府类以及M表示市场类。经过简略的处理后详细信息如表3所示。

表3文档分类测试语料库信息  

<html><body><table><tr><td>类别</td><td>训练集</td><td>测试集</td></tr><tr><td>C</td><td>6000</td><td>1000</td></tr><tr><td>E</td><td>1000</td><td>500</td></tr><tr><td>G</td><td>3000</td><td>1000</td></tr><tr><td>M</td><td>3000</td><td>1000</td></tr></table></body></html>

# 2.1.2实验说明

文档分类任务主要是对语料库中的文档进行分类，由表3可知，实验数据总共分为四类，分别为C，E，G和M，语料库总体分为两个部分，分别为训练集以及测试集，训练集用于模型训练，测试集测试实验分类结果，另外，在训练中，会在训练集中分出部分作为作为验证集。具体实验过程如图1所示。

由图1可知，文档分类任务分为学习句向量和文档分类两个阶段，学习句向量阶段核心是RISV模型训练，RISV模型是在doc2vec模型训练中，加入关系信息作为监督信息，二者共享词向量，实际训练中，调权参数／为0.12时，实验表现最佳。在文档分类任务中，首先，RCV1语料库中的文档会在第一阶段训练出句向量，然后，学习到的句向量和相应的类别会组成类似<data,label>形式的数据对做为SVM分类器的输入，最后在测试集对模型进行验证，验证方法为给定一组数据 $_ { < \mathrm { X } , \mathrm { y } > }$ ，如果SVM分类器预测类别 $\mathbf { y } ^ { \prime }$ 与y相同判定分类正确，反之，判定失败，完成所有测试后，汇总计算预测准确率。

![](images/296bc200d301044b54b13c350121f75f0236e53f023ec2452d1c4ab5112fd8b5.jpg)  
图1文档分类任务流程图

# 2.1.3实验结果

常见的文档分类方法有基于word2vec模型的平均以及tf_idf等，基于doc2vec 模型以及使用RWE模型训练词向量进而通过平均以及tf_idf等。本文在RCV1语料库上进行测试，测试标准为准确率，分类模型为SVM，验证方式使用五分交叉验证。测试结果如表4所示。

表4实验结果  

<html><body><table><tr><td rowspan="2">模型</td><td colspan="5">准确率 (%)</td></tr><tr><td>C</td><td>E</td><td>G</td><td>M</td><td>全部</td></tr><tr><td>Word2vec+平均</td><td>67.56</td><td>69.23</td><td>71.25</td><td>65.32</td><td>68.21</td></tr><tr><td>Word2vec+tf_idf</td><td>69.26</td><td>69.56</td><td>70.24</td><td>68.67</td><td>69.41</td></tr><tr><td>Doc2vec</td><td>70.35</td><td>70.67</td><td>69.25</td><td>71.26</td><td>70.34</td></tr><tr><td>RWE+平均</td><td>71.25</td><td>72.34</td><td>71.21</td><td>72.39</td><td>71.72</td></tr><tr><td>RWE+tf_idf</td><td>70.35</td><td>72.53</td><td>72.36</td><td>72.25</td><td>71.77</td></tr></table></body></html>

<html><body><table><tr><td>RISV</td><td>72.1273.21 72.21</td><td></td><td></td><td>72.9472.54</td></tr><tr><td>RISV+预训练</td><td>72.26 73.29</td><td>72.34</td><td>72.97</td><td>72.63</td></tr></table></body></html>

从表3中可以看出，本文提出的RISV模型在C，E和M类别中分类效果比word2vec以及RWE等方法效果要好。在所有类别汇总的分类中效果也也很明显。另外，在RISV模型中使用预训练，从实验数据中可以看出，有一定的提升效果。

# 2.2短文本语义相似度任务

# 2.2.1实验数据

短文本语义相似度任务使用微软语料库[17]，该语料库常被用来做短文本语义相似度的验证[18-20]。总共有5801个短文本对，每个短文对都用二进制形式来判断语义是否相等。语义相等的短文本对有3900个，不相等的短文本对有1901个，用其中4076个进行训练，1725个进行测试。

# 2.2.2实验说明

短文本语义相似度任务是计算两个文本的语义相似度。例如，“只有英特尔公司的股息收益率较低"和“只有英特尔 $0 . 3 \%$ 的收益率较低”语义是相似的，“去年12月，他预计增长 $5. 3 \%$ 至近1,540亿美元”和“去年12月，他预测增长率为 $5 \%$ ”语义是不相似的。实验数据使用微软语料库，其数据形式为给定两个短文本，并给出两个文本语义是否相似的判定结果，结果使用二进制表示，1表示两个短文本语义相似，0表示两个短文本语义不相似。利用微软语料库，短文本语义相似度任务转换为了二分类问题，具体实验过程如图2所示。

![](images/ed0f85fcf8770691388eb65917d53ba3290840edcb835b2624689292c3e512df.jpg)  
图2短文本语义相似度任务示意

由图2可知，在短文语义相似度任务中，首先，微软语料库中的文档会被表示为句向量，然后，学习到的句向量会被添加标签0和1，1表示语义相似，0表示语义不相似。最后使用测试集测试实验结果，测试方法为给定一组数据<string,label>，如果SVC分类器预测相似度p_label与label相同判定相似，反之，判定不相似，完成所有测试后，计算预测相似准确率。

# 2.2.3实验结果

实验使用的评估标准是准确率以及p(precision)，r(recall)以及Fi值，分类器使用RBF核的SVC模型，因为特征空间不一定是线性的，验证方式使用五分交叉验证。

表5短文本相似度实验结果  

<html><body><table><tr><td>模型</td><td>准确率</td><td>p</td><td>r</td><td>F1</td></tr><tr><td>Word2vec+平均</td><td>0.6991</td><td>0.7123</td><td>0.8425</td><td>0.7719</td></tr></table></body></html>

<html><body><table><tr><td>Word2vec+tf_idf</td><td>0.7012</td><td>0.7621</td><td>0.8521</td><td>0.8046</td></tr><tr><td>Doc2vec</td><td>0.6929</td><td>0.7235</td><td>0.9137</td><td>0.8076</td></tr><tr><td>RWE+平均</td><td>0.7102</td><td>0.7426</td><td>0.8969</td><td>0.8125</td></tr><tr><td>RWE+tf_idf</td><td>0.7201</td><td>0.7716</td><td>0.9123</td><td>0.8361</td></tr><tr><td>RISV</td><td>0.7312</td><td>0.7821</td><td>0.9237</td><td>0.847</td></tr><tr><td>RISV+预训练</td><td>0.7319</td><td>0.7826</td><td>0.9314</td><td>0.8505</td></tr></table></body></html>

从表5中可以看出，RISV模型在准确率以及 $p , r { \cal F } _ { 1 }$ 值上表现比word2vec以及RWE 等方法好。在预训练后，实验表现能够得到进一步的提升。

# 2.3 总结

本文主要从两个任务验证RISV模型学习句向量的有效性，任务分别为文档分类和短文本语义相似度任务。在文档分类任务中，实验结果如表6所示，对6个模型学习到的句向量使用SVM分类器进行分类，包括对RISV进行RCM预训练处理。实验结果表明RISV模型能够在文档分类任务中取得了很好的表现。在短文本语义相似度任务中，实验结果如表4所示，RISV模型也有很好的表现，并且在两个任务中，使用关系约束模型（RCM）预训练，使初始词向量具有一定关系约束信息，并在RISV模型中有一定的体现，从而对实验结果起到帮助。

# 3 结束语

本文在RWE模型的基础上提出了RISV模型，与RWE模型相比，RISV模型添加了文档向量，能够记忆段落信息，减少传统从词向量到句向量转换损失的信息，在一个文档训练过程中，paragraphid保持不变，相当于在预测单词概率时，使用了整个文本的语义。另外，RISV模型能够直接学习得到句向量，不需要转换。但相对于RWE 模型以及一些基于word2vec 模型的算法相比，本文提出的RISV模型增加了算法复杂度，在训练中对数据处理也比较繁琐。因此，下一步需要对模型进行改进，优化算法复杂度。

# 参考文献：

[1]Mikolov T, SutskeverI, Chen K,et al.Distributed representations of words and phrases and their compositionality [Cl// Proc of International Conference on Neural Information Processing Systems.[S.1.] :Curran Associates Inc.,2013:3111-3119.   
[2]Zheng X, Chen H,Xu T.Deep learning for Chinese word segmentation and POS tagging[C]//Proc of Conference on Empirical Methods in Natural Language Processing. 2013: 647-657.   
[3] Zhang M,Zhang Y,Che W,et al. Chinese Parsing Exploiting Characters [C]//ACL.2013: 125-134.   
[4]Devlin J,Zbib R,Huang Z,et al.Fast and robust neural network joint models for statistical machine translation [C]//Proc of Meeting of the Association for Computational Linguistics.2014:1370-1380.   
[5]唐明，朱磊，邹显春．基于Word2Vec 的一种文档向量表示[J].计算机 [小 计算机应用研究,2015,32(10):2905-2909.   
[7] 苗祥，刘业政，孙春华．领域同义特征词的统计规律及其在情感分析上 的应用研究[J].计算机应用研究,2014,31(11):3333-3336.   
[8]Liu Quan,Jiang Hui, Wei S,et al. Learning semantic word embeddings based on ordinal knowledge constraints [C]// Proc of the 53th Annual Meeting ofthe Association for Computational Linguistics.2015:1501-1511.   
[9]Xu C,Bai Y,Bian J,et al. RC-NET: a general framework for incorporating knowledge into word representations [C]//Proc of ACM International Conference on Conference on Information and Knowledge Management New York: ACM Press,2014: 1219-1228.   
[10]Nguyen KA, Walde SSI,VuNT. Integrating distributional lexical contrast into word embeddings for antonym-synonym distinction [C]//Proc of the 54th Annual Meeting of the Association for Computational Linguistics. 2016: 454-459.   
[11] Le Q V,Mikolov T.Distributed representations of sentences and documents [C]//Proc of the 31st International Conference on Machine Learning.2014.   
[12] Xing C,Wang D,Zhang X,et al.Document classification with distributions of word vectors [Cl// Proc of Asia-Pacific Conference on Signal and Information Processing Association. 2014: 1-5.   
[13] Han K K, Kim H, Cho S. Bag-of-concepts: comprehending document representation through clustering words in distributed representation [EB/OL].http://dm.snu.sc.kr//static//docs//TR//SNUDM-TR-2015-05.pdf.   
[14] Yu M,Dredze M. Improving Lexical Embeddings with Semantic Knowledge [Cl// Proc of Meeting of the Association for Computational Linguistics. 2014: 545-550.   
[15] Erhan D, Bengio Y,Courville A,et al. Whydoes unsupervised pre-training help deep learning?[J]. Journal ofMachine Learning Research,2010,11 (3): 625-660.   
[16] LewisDD,Yang Y,Rose TG,et al.RCV1: a new benchmark collection for text categorization research[J]. Journal of Machine Learning Research, 2004,5 (2): 361-397.   
[17] Quirk C,Brockett C,Dolan W B.Monolingual machine translation for paraphrase generation [C]// Proc of Conference on Empirical Methods in Natural Language Processing. 2004: 142-149.   
[18] Annesi P, Croce D,Basili R. Semantic compositionality in tree kernels [C]/ Proc of the 23rd ACM International Conference on Conference on Information and Knowledge Management. 2014: 1029-1038.   
[19] Fernando S,Stevenson M.A semantic similarity approach to paraphrase detection [C]// Proc of Annual Research Collquium on Computational Linguistics. 2008.   
[20] Hu B,Lu Z,Li H,et al.Convolutional neural network architectures for matching natural language sentences [Cl//Proc of International Conference on Neural Information Processing Systems. Cambridge: MIT Press,2014: 2042-2050.