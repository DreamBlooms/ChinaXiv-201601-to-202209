# 基于双向LSTM和GBDT的中医文本关系抽取模型

罗计根，杜建强，聂斌，熊旺平，刘蕾，贺佳(江西中医药大学 计算机学院，南昌 330004)

摘要：为解决采用 Softmax作为长短期记忆网络分类器导致实体关系识别模型泛化能力不足，不能较好适用中医实体关系抽取等问题，提出一种融合梯度提升树的双向长短期记忆网络的关系识别算法(BILSTM-GBDT)。先采用word2vec 对中医文本进行向量化表示，再利用基于注意力机制的双向长短期记忆网络提取高阶特征，最后采用集成分类模型梯度提升树作为特征分类器，提高关系识别效果。在中医等多个关系语料库上的实验结果表明，该模型与传统SVM方法、GBDT方法及其深度学习方法相比，均有更高的精确率、召回率和F值。

关键词：关系抽取；LSTM；梯度提升树；注意力机制；中医文本 中图分类号：TP doi: 10.3969/j.issn.1001-3695.2018.07.0420

# TCM text relationship extraction model based on bidirectional LSTM and GBDT

Luo Jigen1,Du Jianqiang†,Nie Bin, Xiong Wangping,Liu Lei, He Jia (School ofComputer Jiangxi UniversityofTraditional Chinese Medicine,Nanchang33oo04,Chinc

Abstract: Inorder to solvethe problem thattheuseofSoftmax asalong-short-term memory network clasifierleads to the lack of generalizationabilityoftheentityrelationshiprecognition model,itis notsuitablefortheextractionof TCM entity relationships.Thispaperproposeda bidirectionallong short-term memory(BILSTM)relational identificationalgorithm (BILSTM-GBDT)that incorporatesa gradient bostingdecision tree(GBDT).Firstly,The Chinese medicine textvectoris trainedby word2vec,thenthehigh-order features are extractedbythe BidirectionalLong Short-Term Memory network based ontheattentionmechaism.Finall,theintegratedclassificationmodelgradientlifting treeisusedasthefeatureclasifierto improve the relationshiprecognitioneffect.Experimental results onmultiple relationalcorporasuch as Chinese medicine show thatthe model has higheraccuracy,recallandF value than traditional SVMmethod,GBDT method and deep learming method. Key Words: relationship extraction; LSTM; GBDT; attention mechanism; Chinese medicine text

# 0 引言

中医诊断知识是中华民族千百年遗留下的瑰宝，对中医临床具有很强的指导作用。随着中医诊断数据的不断增加，语句表达形式上具有一定的灵活性，实体关系也随之变得复杂。中医实体关系识别[1,2]是中医领域信息抽取[3]的一部分，是指在给定实体对和非结构文本情况下，识别两者之间存在的语义关系。

例如下面这个句子包含方剂、中药、症状、舌像、脉象、证型等多类实体：补天大造丸由牛膝、当归、小茴香等多味中药组成，其主治为咳逆喘息少气，咯痰色白有沫，血色暗淡，潮热，自汗，盗汗，声嘶或失音，面浮肢肿，心慌，唇紫，肢冷，形寒，口舌生糜。苔黄而剥，舌质光淡，脉微细而数的肺痨阴阳两虚证。对于上面句子中，在关系抽取任务中，需要准确的识别出实体"补天大造丸"和实体“牛膝”、“当归"和"小茴香"之间的语义关系，其大类关系为"方药”，小类关系为"组成”，实体"补天大造丸"与实体"肺痨阴阳两虚证"是"治疗"关系，实体"肺痨阴阳两虚证"与实体"脉微细而数"是"脉象”，也就是脉微细而数是痨阴阳两虚证的脉象，此外还有证型和症状，证型和舌像的关系。整个句子的关系表现形式如图1所示。

# 1 相关工作

关系抽取对于信息检索、篇章理解、知识图谱构建等研究都具有及其重要的研究意义。目前较流行的关系抽取方法有：基于特征工程的抽取方法、基于核函数的抽取方法和基于深度

学习的抽取方法[4]。

在基于特征工程的抽取方法中，主要是利用词汇特征、句法特征和语义特征[5]。虽然基于特征工程的关系抽取方法在一定程度上取得了不错的效果，但是由于句子的表达形式越来越复杂，特征提取越来越困难，导致基于特征的关系抽取效果很难提升。基于核函数[的关系抽取方法不同于特征工程，它主要考虑的是句子本身的结构信息，不需要建立高维的数据特征向量。它使用句法结构树作为输入对象，通过核函数比较语料之间的结构相似性进行关系分类。但是由于句子隐形特征中存在人们无法识别的噪声，且语义相同存在不同的表达形式，句子的长短表达能力不一样导致基于核函数的关系抽取也存在一定的弊端。

![](images/b70a446d95e43d646a077c55ec51d2d4df1ef767ab575225f9696e25dcf852f9.jpg)  
图1例句关系

随着深度学习的不断发展，以其自动提取特征的优势被更多的应用在关系抽取任务中[7,8]。 $\mathrm { v } _ { \mathrm { u } }$ 等人[9]提出将深度循环神经网络（deep recurrentneural networks，DRNN）应用于关系抽取任务中，通过解析树的方式将句子分成两个部分，而后将其输入到多层循环神经网络中去。Zeng等人[10]提出一种融合位置信息的卷积神经网络（convolutional neuralnetworks，CNN）的关系抽取算法，为有效缓解长距离依赖问题，该算法考虑N-gram特征，但是由于CNN中的滤波器选择不能太大，导致不能完全长距离依赖的问题。LSTM是由Hochreiter等人[1]提出的一种 RNN改进模型，它设置了三种门限结构，通过记忆和遗忘等操作解决RNN和CNN存在的长距离依赖问题，目前也越来越多的应用在关系抽取任务上，Miwa等人[I2]利用LSTM引入SPTree中进行关系抽取。但是，以上模型都采用了Softmax作为分类器，导致实体关系识别模型泛化能力不足[13]，不能较好适应中医实体关系分类的问题。

为解决上述问题，本文提出一种融合梯度提升树(gradientboostingdecision tree，GBDT)算法[14]的双向长短期记忆网络（bidirectional long short-term memory，BILSTM）模型。其中在使用BILSTM进行特征提取的同时，加入Attention机制抓取关键字词对句子理解7，解决该模型容易被无关词干扰的问题。特征提取后采用GBDT对关系分类训练预测，由于GBDT的基础模型具有低方差高偏差等优势，使得集成模型更具稳定性，可以在一定程度上解决采用Softmax作为长短期记忆网络分类器导致泛化能力不足的问题。

# 2 融合GBDT的BILSTM关系抽取

融合GBDT的BILSTM关系抽取模型，采用BILSTM模型获取前后两个方向的深层隐含特征，同时有效解决传统深度学习方法中长距离依赖的问题。同时在利用BILSTM提取特征时加入Attention机制考虑关键字词对特征的影响，从而获取更多的上下文信息；然后采用GBDT算法对提取的特征进行分类处理，得到最终的关系类别。该模型如图2所示，其主要包括两个部分：

a）加入Attention 机制的BILSTM特征提取。将训练语料库的词向量输入到BILSTM模型中，采用Attention机制计算注意力概率，对BILSTM模型输入的关键字词重要性分析，根据注意力概率获取BILSTM模型的输出特征。

b）基于GBDT的关系分类。将BILSTM模型得到的特征输入到GBDT算法中，不断迭代构建决策树，利用上次模型的负梯度改进模型，在残差减少的梯度方向上建立新的决策树。

![](images/ac3ac584f4a8d4f29aa2601216937e0253bc6cf4f381ac2d6c312f10a285a517.jpg)  
图2融合GBDT的BILSTM关系抽取模型

# 2.1基于注意力机制的BILSTM特征提取

由于LSTM不能直接处理文本数据，需先利用Google 的开源工具Word2vec 将文本转换成字向量。假设输入的句子为（204 $s$ ，所包含的字集合为 $W ( w _ { 1 } , w _ { 2 } , w _ { 3 } , . . . , w _ { m } )$ ， $\mathbf { \Sigma } _ { m }$ 为句子长度，其中第 $\mathbf { \Phi } _ { t }$ 个字的字向量为： $w _ { t } ^ { * } \in R ^ { d }$ ，上式中 $d$ 为词向量的维度，则输入文本表示为

$$
S = \left[ { w _ { 1 } } ^ { * } , { w _ { 2 } } ^ { * } , . . . , { w _ { m } } ^ { * } \right] \in R ^ { T \times d }
$$

LSTM神经网络是一种特殊的RNN，其思想是用LSTM单元去替代RNN中隐含层的神经单元。LSTM单元是由输入门（Inputgate），输出门（Output gate）和遗忘门（Forget gate）三个门组成，由于LSTM的特殊结构，让LSTM神经网络可以在一定程度上解决长距离依赖问题。

在 $t$ 时刻，LSTM各单元组成部分的更新情况如下所示。

$$
f _ { t } = \sigma ( W _ { t } \cdot [ h _ { t - 1 } , x _ { t } ] + b _ { f } )
$$

$$
i _ { t } = \sigma ( W _ { f } \cdot [ h _ { t - 1 } , x _ { t } ] + b _ { i } )
$$

$$
\tilde { c } _ { t } = \mathrm { t a n h } ( W _ { c } \cdot [ h _ { t - 1 } , x _ { t } ] + b _ { c } )
$$

$$
c _ { t } = f _ { t } \circ c _ { t - 1 } + i _ { t } \circ \tilde { c } _ { t }
$$

$$
o _ { t } = \sigma ( W _ { o } \cdot [ h _ { t - 1 } , x _ { t } ] + b _ { o } )
$$

$$
h _ { t } = o _ { t } \circ \operatorname { t a n h } ( c _ { t } )
$$

其中: $\sigma$ 表示 sigmoid 激活函数，。是元素乘， $x _ { t }$ 为 $t$ 时刻LSTM的输入向量， $h _ { { _ t } }$ 代表了隐含状态， $W _ { f } \ , W _ { i } \ , W _ { c } \ ,$ $W _ { o }$ 分别代表了遗忘门，输入门，记忆单元，输出门的权值矩阵。𝑏f，bi，$b _ { c } , b _ { o }$ 分别代表了遗忘门，输入门，记忆单元，输出门的偏置。fr，i，c,，o,表示遗忘门，输入门，记忆单元状态和输出门。

为充分利用上下文信息，挖掘更多的隐含特征，有效解决关系抽取问题，本文设计双向LSTM神经网络，该方法是由两个相反方向的LSTM神经网络组成，其模型结构如图1中BILSTMlayer部分所示，其中 $\vec { h } _ { t }$ 是前向LSTM神经网络在 $t$ 时刻的输出， $\ddot { h } _ { { t } }$ 是后向LSTM单元在时刻 $\mathbf { \Phi } _ { t }$ 的输出，所以时刻t的输出为前向后向的拼接，即h=[h,h]。

由于每个字词对句子所属类别的贡献能力不同，利用Attention机制[15的思想对句子进行更深的特征提取，提高关系分类精确率。例如在句子"现代研究：许氏报告用通脉四逆汤加味治疗少阴格阳证16例，全部治愈"中，普通的BILSTM神经网络对句子中的每一个词都是同等对待的，引入Attention机制后，模型通过注意力权值分配，重点关注"治疗"这个关键词。图2中Attentionlayer所示为在BISLTM模型后接入Attention机制的结构示意图。经过Attention层得到的全局输出向量为H，则相关计算如下：

$$
\begin{array} { r } { u _ { t } = \operatorname { t a n h } ( w _ { \mathrm { w } } h _ { t } + b _ { \mathrm { w } } ) } \\ { a _ { t } = s o f t m a x ( u _ { t } ^ { T } , u _ { \mathrm { w } } ) } \end{array}
$$

$$
H = \sum _ { t } a _ { t } h _ { t }
$$

其中: $u _ { \iota }$ 是 $h _ { { _ t } }$ 的隐藏单元， $\boldsymbol { u } _ { \scriptscriptstyle w }$ 为句子的上下文向量， $a _ { \scriptscriptstyle t }$ 为注意力向量， $h _ { { _ t } }$ 为 BILSTM 的输出向量，也即 $h _ { t } = [ \vec { h } _ { t } , \ddot { h } _ { t } ]$ ， $w _ { \mathrm { w } } \ , \ b _ { { } _ { w } }$ 为注意力权重值和偏置，随机初始化并在训练中不断学习。

# 2.2基于GBDT的关系分类

关系抽取可以看成是多分类问题，奠雨洁等人[16提出将GBDT用于微博立场检测当中，通过对语料库手动提取特征，完成文本分类。段大高等人[17提出一种基于GBDT的虚假消息检测方法，通过提出评论中文本内容、用户属性，信息传播和时间等特征，利用GBDT实现分类。GBDT是一种集成学习器，采用Boosting的思想，构造 $N$ 个弱学习器，经过多次迭代形成最终强学习器。它采用的弱学习器为CART回归树，每一次迭代都是为了减少上一个模型的残差，并在残差减少的梯度上训练建立新的模型。

由 Attention 机制的 BILSTM 模型得到的特征和原始类别标签形成 GBDT 训练集数据$T = \{ ( x _ { 1 } , y _ { 1 } ) , ( x _ { 2 } , y _ { 2 } ) , ( x _ { 3 } , y _ { 3 } ) , . . . , ( x _ { n } , y _ { n } ) \}$ ，其中 $x _ { i }$ 为语料库中第 $i$ （20个句子在模型提取的特征向量。 $y _ { i }$ 的取值为关系类别。假设GBDT损失函数为 $L ( y , f )$ ，则其表达式为

$$
L ( y , f ) = \sum _ { i = 1 } ^ { m } L ( y _ { i } , f ( x _ { i } ) )
$$

第 $t$ 轮的第 $i$ 个样本的损失函数的负梯度表示为

$$
r _ { t i } = - \Bigg [ \frac { \hat { \sigma } L ( y _ { i } , f ( x _ { i } ) ) } { \hat { \sigma } f ( x _ { i } ) } \Bigg ] _ { f ( x ) = f _ { t - 1 } ( x ) }
$$

利用 $x _ { i } , r _ { t j } )$ 可以拟合一颗CART回归树，得到了第 $\mathbf { \Phi } _ { t }$ 棵决策树，其对应的叶节点区域。其中 $J$ 为叶子节点的个数。

针对每一个叶子节点里的样本，求出使损失函数最小，也就是拟合叶子节点最好的输出值 $c _ { t j }$ 如下：

$$
c _ { t j } = \underbrace { \underset { c } { \arg \operatorname* { m i n } } } _ { c } \sum _ { x _ { i } \in R _ { J } } L ( y _ { k } , f _ { t - 1 } ( x _ { i } ) + c )
$$

得到本轮的决策树拟合函数为：

$$
\begin{array} { r } { h _ { _ t } ( x ) = \sum _ { c _ { t j } } ^ { J } I ( x \in R _ { _ { t j } } ) } \end{array}
$$

本轮的最终强学习模型的表达式如下：

$$
f _ { t } ( x ) = f _ { t - 1 } ( x ) + \overset { J } { \mathop { \sum } } c _ { t j } I ( x \in R _ { t j } )
$$

# 2.3融合GBDT的BILSTM关系抽取模型

在实现实体关系抽取时，利用基于Attention 机制的BILSTM抽取文本特征向量，得到特征组合 $\nu$ ，之后采用梯度提升树对特征组合进行分类训练和预测，得到最终每个句子的关系类别。BILSTM-GBDT的优点在于可以在一定程度上解决传统深度学习方法在处理关系抽取时出现的泛化能力不强的问题，同时提高关系抽取的精确率。

BILSTM-GBDT的具体算法流程如下：

a)利用word2vec 对训练集样本进行Embedding操作，则每个输入句子的向量矩阵为； $\boldsymbol { S } \mathrm { = } \boldsymbol { \left[ w _ { 1 } ^ { * } , w _ { 2 } ^ { * } , w _ { 3 } ^ { * } , . . . , w _ { m } ^ { * } \right] }$

b)将 $\boldsymbol { S } \mathrm { = } \big [ w _ { 1 } ^ { * } , w _ { 2 } ^ { * } , w _ { 3 } ^ { * } , . . . , w _ { m } ^ { * } \big ]$ 矩阵输入到 BILSTM 模型中，计算 $\mathbf { \Phi } _ { t }$ 时刻的正向输出 $\vec { h _ { t } }$ ，逆向输出为 $\mathbf { \Sigma } _ { h _ { t } } ^ {  }$ ，BILSTM层的输出特征为h =[h,h];

c)初始化Attention层中各节点的注意力权值，通过式（9）得到注意力概率 $a _ { { } _ { t } }$ ，由式（10）计算得到最终输出特征 $H$ ；

d)利用 Attention 层输出 $H = \{ h _ { 1 } , h _ { 2 } , h _ { 3 } , . . . , h _ { _ n } \}$ 和类别标签$Y = \{ y _ { 1 } , y _ { 2 } , y _ { 3 } , . . . , y _ { m } \}$ 构建梯度提升树。此时假设GBDT损失函数为 $L ( y , f ) = \sum _ { i = 1 } ^ { m } L ( y _ { i } , f ( x _ { i } ) ) $

e)第 $t$ 轮的第 $i$ 个样本的损失函数的负梯度表示为：$\mathbf \Sigma _ { t j } = - \Bigg [ \frac { \hat { \sigma } L ( y _ { i } , f ( x _ { i } ) ) } { \hat { \sigma } f ( x _ { i } ) } \Bigg ] _ { f ( x ) = f _ { t - 1 } ( x ) }$ f)拟合叶子节点输出值 $c _ { t j }$ 如下：$c _ { t j } = a r g m i n \sum _ { c } L ( y _ { k } , f _ { t - 1 } ( x _ { i } ) + c )$ （204号

g)决策树拟合函数为 $h _ { t } ( x ) = \sum _ { j = 1 } ^ { J } c _ { t j } I ( x \in R _ { t j } )$ ，经过 $\mathbf { \Sigma } _ { m }$ 次迭代形成的集成学习模型为 $f _ { t } ( x ) = f _ { t - 1 } ( x ) + \sum _ { j = 1 } ^ { J } c _ { t j } I ( x \in R _ { t j } )$ 0

h)通过模型迭代训练得到最终关系类别。

# 3 实验

# 3.1实验设置

为验证本文提出的BILSTM-GBDT实体关系抽取算法的有效性，使用整理后的中医关系语料库（TCMRECoupus）对模型进行验证。中医关系语料库的来源包含了中医古籍文本、教学书籍、中医科研论文，在构建中医关系语料库时，先从标注文档中抽取出所需实体对，然后对文档进行断句处理，最后形成的语料库一共为26855个句子，包含11个类别。另外为验证本文提出改进算法的性能，本文除了使用中医关系语料库，还在SemEval-2010和ACL2007关系语料库上进行了对比实验。三组语料库详细情况如表1所示。

表1三种语料库信息  

<html><body><table><tr><td colspan="2">TCM RECoupus</td><td colspan="2">SemEval-2010</td><td colspan="2">ACL2007</td></tr><tr><td>关系</td><td>数量</td><td>关系</td><td>数量</td><td>关系</td><td>数量</td></tr><tr><td>方药</td><td>3850</td><td>其他</td><td>1864</td><td>制造使用</td><td>1440</td></tr><tr><td>药症</td><td>2982</td><td>因果</td><td>1331</td><td>类属</td><td>1776</td></tr><tr><td>药证</td><td>1839</td><td>整体与部分</td><td>1253</td><td>转喻</td><td>470</td></tr><tr><td>方证</td><td>3642</td><td>实体与目标</td><td>1137</td><td>组织从属</td><td>2460</td></tr><tr><td>方症</td><td>2869</td><td>实体与来源</td><td>974</td><td>局部整体</td><td>981</td></tr><tr><td>方病</td><td>1683</td><td>生产者产品</td><td>948</td><td>人物</td><td>3116</td></tr><tr><td>病症</td><td>2258</td><td>会员与组织</td><td>923</td><td>地理位置</td><td>2157</td></tr><tr><td>证症</td><td>2754</td><td>实体与主题</td><td>895</td><td>，</td><td>-</td></tr><tr><td>药症</td><td>2115</td><td>内容与包含</td><td>732</td><td></td><td>-</td></tr><tr><td>舌证</td><td>2863</td><td>工具使用者</td><td>660</td><td></td><td></td></tr><tr><td>脉证</td><td>2651</td><td></td><td></td><td></td><td></td></tr></table></body></html>

本文通过将语料库按照每种关系的7:3方式划分模型的训练集和测试集。在BILSTM参数设置见表2所示，其中Dropout、学习率和优化器等参数通过多组实验对比得出。

表2LSTM神经网络参数设置  

<html><body><table><tr><td>超参数</td><td>调参值</td></tr><tr><td>learning rate</td><td>0.001</td></tr><tr><td>dropout</td><td>0.5</td></tr><tr><td>gradient clipping</td><td>5.0</td></tr><tr><td>embedding-dim</td><td>300</td></tr><tr><td>optimizer</td><td>Adam</td></tr><tr><td>batch-size</td><td>64</td></tr><tr><td>hidden-dim</td><td>300</td></tr><tr><td>epoch</td><td>30</td></tr></table></body></html>

为体现本文提出的模型优势，采用准确率(P）、召回率（R）、F值作为模型评价准则。

# 3.2实验结果

利用中医实体关系语料库的训练集数据进行模型训练，用测试集数据进行BILSTM-GBDT模型评测，得到11类关系的精确率、召回率和 $F$ 值如表3所示。

表3BILSTM-GBDT模型实验结果   

<html><body><table><tr><td>关系类别</td><td>P(%)</td><td>R(%)</td><td>F(%)</td></tr><tr><td>方药</td><td>93.25</td><td>92.53</td><td>92.88</td></tr><tr><td>药症</td><td>86.53</td><td>85.21</td><td>85.86</td></tr><tr><td>药证</td><td>85.12</td><td>86.74</td><td>85.92</td></tr><tr><td>方证</td><td>92.41</td><td>93.85</td><td>93.12</td></tr><tr><td>方症</td><td>83.96</td><td>81.23</td><td>82.57</td></tr><tr><td>方病</td><td>81.29</td><td>82.56</td><td>81.92</td></tr><tr><td>病症</td><td>88.20</td><td>87.06</td><td>87.62</td></tr><tr><td>证症</td><td>91.22</td><td>89.38</td><td>90.29</td></tr><tr><td>药症</td><td>84.23</td><td>82.71</td><td>83.46</td></tr><tr><td>舌证</td><td>90.36</td><td>89.27</td><td>89.81</td></tr><tr><td>脉证</td><td>91.28</td><td>92.06</td><td>91.67</td></tr><tr><td>所有</td><td>87.98</td><td>87.51</td><td>87.74</td></tr></table></body></html>

由表3可知，对于自定义的11种中医关系，其中方药、方证、证症、脉证四类关系的精确率、召回率和F值达到 $90 \%$ 以上。这是因为中医在这四类关系上表达，形式简单，实体形式固定，语料占比相对其他关系较大，所以效果明显优于其他类关系的实验效果。

为验证本文提出改进算法的性能，同时引入四种目前流行的关系抽取算法，分别为支持向量机（SVM）、梯度提升树（GBDT）、深度学习方法BILSTM、融入注意力机制的BILSTM模型（BILSTM-ATT)，这两类深度学习关系抽取模型都是在提取特征后采用Softmax进行关系分类。对比实验结果如表4和

图3所示。表4五种关系模型实验对比  

<html><body><table><tr><td colspan="4">TCM RECoupus (%)</td><td colspan="3">SemEval-2010</td><td colspan="3">ACL2007</td></tr><tr><td>方法</td><td>P</td><td>R</td><td>F</td><td>P</td><td>R</td><td>F</td><td>P</td><td>R</td><td>F</td></tr><tr><td>GBDT</td><td>79.21</td><td>78.63</td><td>78.92</td><td>79.53</td><td>81.21</td><td>80.36</td><td>78.33</td><td>79.61</td><td>78.96</td></tr><tr><td>SVM</td><td>75.63</td><td>78.57</td><td>77.07</td><td>78.92</td><td>79.34</td><td>79.13</td><td>77.63</td><td>76.97</td><td>77.29</td></tr><tr><td>BILSTM</td><td>83.78</td><td>82.35</td><td>83.06</td><td>81.66</td><td>82.62</td><td>82.14</td><td>82.35</td><td>82.74</td><td>82.54</td></tr><tr><td>BILSTM- ATT</td><td>85.82</td><td>85.44</td><td>85.63</td><td>84.09</td><td>83.25</td><td>83.67</td><td>84.67</td><td>84.14</td><td>84.40</td></tr><tr><td>BILSTM- GBDT</td><td>87.98</td><td>87.51</td><td>87.74</td><td>86.13</td><td>85.52</td><td>85.82</td><td>85.85</td><td>86.28</td><td>86.06</td></tr></table></body></html>

85 山d 80   
75   
70   
中医语料库 SemEval-2010 ACL2007 ■GBDT ■SVM ■BILSTM   
■BILSTM-ATT ■BILSTM-GBDT

结合表4和图3的实验结果，在中医关系语料库上集成算法GBDT在精确率、召回率和 $F$ 值上都超过SVM，可见集成学习算法相对传统机器学习算法增强了模型抗干扰能力，增强了模型的泛化能力。但综合来看，BILSTM比GBDT算法在 $F$ 值高出 $4 . 1 4 \%$ ，说明BILSTM自动提取的句子深层特征有利用关系分类，可以得到更好的实验结果。BILSTM-ATT在BILSTM的基础上增加了注意力机制，由实验结果可以看出，BILSTM-ATT模型的 $F$ 值相比BILSTM高出了 $2 . 1 7 \%$ ，正是加入了注意力机制的原因，它为每个输入的字向量提供权值，句子最终的特征通过此权重加权之后的整合，可以减少句子中噪声词的影响。BILSTM-GBDT是在引入注意力机制的情况下，采用GBDT作为模型的分类器，在F值上相对BILSTM-ATT提高了 $2 . 1 1 \%$ 。

五种算法在SemEval-2010语料库上的实验结果见表4和图3。由实验结果数据可知，集成算法GBDT在精确率、召回率和 $F$ 值上依旧超过了SVM，可见GBDT集成算法在关系分类上的优势。BILSTM-GBDT在三个评价指标相对其他算法都最高的，在 $F$ 值测评上高出BILSTM-ATT 模型 $2 . 2 5 \%$ 。

根据表4和图3中五种算法在ACL2007语料库上的实验结果可知，集成算法GBDT相对SVM来说，在三个评测标准上仍有很大的优势。BILSTM-GBDT 相对其他两种以 Softmax作为分类器的模型来说具有很大的优势，在F值评测上，BILSTM-GBDT达到 $8 6 . 0 6 \%$ ，高出BILSTM-ATT模型 $1 . 6 6 \%$ 。为探究梯度提升树构建棵数 $m$ 值和模型效果的问题，本文在三个关系语料库上做了相关实验，实验结果如图4所示，图中决策树的数目呈10的倍数递增，共计10次。

![](images/f2905d66cedf9590b7bad4d2bc118143c8ee8f3a2e3ab6fc9d470f353b72da63.jpg)  
图4模型效果随 $\mathbf { \Sigma } _ { m }$ 值变化

由图4可知，初始时随着决策树数目 $\mathbf { \Sigma } _ { m }$ 的值增加，BILSTM-GBDT模型在三个语料库上的F值均呈现上升的趋势，当梯度提升树构建到60棵的时候，此时模型效果达到最优，之后三个语料库上的F值基本趋于稳定，甚至会出现一定程度上的下降。

综上所述，BILSTM-GBDT利用融合注意力机制的双向长短期记忆网络充分提取句子特征，使用集成学习GBDT作为分类器，在一定程度上解决了传统以Softmax用作分类器带来的模型泛化能力不强的问题，使实验结果更加稳定。相比来说，SVM算法实验效果最差，使用GBDT这种集成学习算法使得模型更加稳定，泛化能力得到加强。但是由于人工提取的特征使GBDT跟BILSTM-GBDT的实验结果还是有一定差距。BILSTM-GBDT先利用融合注意力机制的BILSTM模型提取高阶特征，然后利用集成学习GBDT迭代形成多棵决策树，增强了模型泛化能力，当梯度提升树构建到60棵的时候模型的效果趋于稳定。在三个语料库上的实验效果表明，BILSTM-GBDT较BILSTM-ATT有明显的优势，在三个语料库上的综合表现 $F$ 值分别提高了 $2 . 1 1 \%$ 、 $2 . 2 5 \%$ 、 $1 . 6 6 \%$ ，实验结果验证了该方法在解决以Softmax作为分类器带来的泛化能力不强问题上的有效性。

# 4 结束语

本文针对关系抽取任务上采用Softmax作为长短期记忆网络分类器导致模型泛化能力不足，不能较好适应中医实体关系分类的问题，提出了一种融合梯度提升树算法的双向长短期记忆模型，充分在利用双向LSTM自动提取特征的优势，并结合Attention机制抓取关键字词对句子理解，解决模型容易被无关词干扰的问题，最后利用GBDT低方差高偏差的优势，增强模型的鲁棒性和泛化性。通过对中医关系语料库和其他两个公开领域语料库实验的比较，证明本文提出的改进模型在准确率、召回率和F值上均有明显提高，是一种适合于中医特定领域的关系抽取模型。但是改进算法仍有不足之处，只能抽取预先定义好的关系，在接下来的工作中，将进一步研究对于新关系的抽取，以及如何将其扩展到其他领域中。

# 参考文献：

[1]彤博辉，付琨，黄宇，等．基于多通道卷积神经网的实体关系抽取[J]. 计算机应用研究,2017,34(3):689-692.(Rong Bohui,Fu Kun,Huang Yu, et al.Relation extraction based on multi-channel convolutional neural network[J].Application Research of Computers,2017,34(3):689-692 [2]陈宇，郑德权，赵铁军．基于deep beliefnets的中文名实体关系抽取[J]. 软件学报,2012,23 (10): 2572-2585.(Chen Yu,Zheng Dequan,Zhao Tiejun. Chinese relation extraction based on deep belief nets [J].Journal of Software,   
2012,23 (10): 2572-2585) [3]郭喜跃，何婷婷．信息抽取研究综述[J].计算机科学,2015,42(2):14-   
17.(Guo Xiyue,He Tingting.Survey about research on information extraction [J].Computer Science,2015,42(2): 14-17.) [4]段利国，徐庆，李爱萍，等．实体词语义信息对中文实体关系抽取的作 用研究[J].计算机应用研究,2017,34(1):141-146.(DuanLiguoit,Xu Qing,Li Aiping,et al.Research on effect of entities semantic information on Chinese entity relation extraction [J]. Application Research of Computers,   
2017,34 (01): 141-146. ) [5]甘丽新，万常选，刘德喜，等．基于句法语义特征的中文实体关系抽取 [J]．计算机研究与发展，2016,53(2):284-302.(Gan Lixin，Wan Changxuan,Liu Dexi,et al. Chinese named entity relation extraction based on syntactic and semantic features [J]. Journal of Computer Research & Development,2016,53 (2): 284-302. ) [6]陈鹏，郭剑毅，余正涛，等．基于凸组合核函数的中文领域实体关系抽 取[J].中文信息学报,2013,27(5):144-148.(Chen Peng,Guo Jianyi,Yu Zhengtao,et al.Chinese field entity relation extraction based on convex combination kernel function [J]. Journal ofChinese Information Processing,

2013,27 (5): 144-148)

[7]Wang Yequan,Huang Minlie,Zhu Xiaoyan,et al.Attention-based LSTM for Aspect-level Sentiment Classification [C]// Proc of Conference on Empirical Methods in Natural Language Processing.2017: 606-615.   
[8]Chen Qian,Zhu Xiaodan,Ling Zhenhua,et al. Enhanced LSTM for natural language inference [C]// Proc of Meeting of the Association for Computational Linguistics.2017: 1657-1668.   
[9]Vu N T,Adel H,Gupta P,et al. Combining recurrent and convolutional neural networks for relation classification [EB/OL].(2016-05-24）. https://arxiv.org/abs/1605.07333.   
[10] Zeng Daojian,Liu Kang,Lai Siwei,et al.Relation classification via convolutional deep neural network [C]// Proc of the 25th International Conference on Computational Linguistics.2014: 2335-2344   
[11] Hochreiter S,Schmidhuber J.Long short-term memory [J].Neural Computation,1997,9(8): 1735-1780.   
[12] Miwa Makoto,Bansal Mohit.End-to-end relation extraction using LSTMs on sequences and tree structures [EB/OL].(2016-06-08).https://arxiv. org/abs/1601.00770.

[13]胡杰，李少波，于丽娅，等．基于卷积神经网络与随机森林算法的专利

文本分类模型[J].科学技术与工程，2018,18(6):268-272.(Hu Jie,Li Shaobo,Yu Liya,et al.Apatent classification model based on convolutional neural networks and rand forest [J]. Science Technology and Engineering,   
2018,18 (6): 268-272) [14] Jerome H. Friedman. greedy function approximation: a gradient boosting machine[J].Annals of Statistics,2001,29 (5): 1189-1232. [15]Baziotis C,Pelekis N,Doulkeridis C.DataStories at SemEval-2O17 task 4: deep LSTM with attention for message-level and topic-based sentiment analysis [C]//Proc of International Workshop on Semantic Evaluation.2017:   
747-754. [16]奠雨洁，金琴，吴慧敏．基于多文本特征融合的中文微博的立场检测 [J].计算机工程与应用,2017,53 (21):77-84.(Dian Yujie;Jin Qin;Wu Huimin. Stance detection in Chinese microblogs via fusing multiple text features [J].Computer Engineering and Applications,2017,53 (21): 77-84.) [17]段大高，盖新新，韩忠明，等．基于梯度提升决策树的微博虚假消息检 测[J].计算机应用,2018,38(2):410-414.(Duan Dagao,Gai Xinxin,Han Zhongming,Liu Bingxin.Micro-blog misinformation detection based on gradient boost decision tree [J].Journal of Computer Applications,2018,38 (2): 410-414.)