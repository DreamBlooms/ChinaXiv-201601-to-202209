# 基于BLSTM网络的医学时间短语识别

张顺利1，王应军‘，姬东鸿²

(1．河南科技学院 信息工程学院，河南 新乡 453003;2.武汉大学 国家网络安全学院，武汉 430205)

摘要：从医学文本中识别时间短语是临床医学自然语言处理的关键技术之一。传统基于规则和机器学习的方法，需要设计复杂规则和提取特征，而且大多数系统采用串行方法会导致错误的传播。提出基于双向长短时记忆网络(BLSTM）的神经网络架构，在识别时间表示式的同时判别它们的类型：首先使用卷积神经网络（CNN）学习得到单词的字符级别向量和大规模生物医学背景语料上训练得到的词向量进行组合作为 BLSTM 的输入，然后使用BLSTM网络学习单词的上下文语义表示，最后使用条件随机场（CRF）对BLSTM输出的序列进行标签优化。实验基于 SemEval-2016任务12，结果表明没有添加任何特征的神经网络学习方法比该任务中官方提供的最高分的F1值提高了 $3 \%$ 。

关键词：时间短语；病历文本；LSTM 中图分类号：TP391 doi: 10.19734/j.issn.1001-3695.2018.09.0742

Temporal phrases extraction in clinical text based on bidirectional long-short term memory model

Zhang Shunli', Wang Yingjun', Ji Donghong2 (1.Schoolof Information Engineering,Henan Instituteof Science&Technology,Xinxiang Henan453003,China;2. National Network Security College,Wuhan University,Wuhan 430205,China)

Abstract: Recognizing time phrases fromclinical textisafundamentaltask for manyapplications inclinical NLP.Previous work mainly adopted rule-based methods or machine learning approaches,which greatly depend on patern designing or feature enginering,and the pipeline method used by most systems may lead to error propagation.This paper proposed a novel neural network based on bidirectional long-shortterm memory (BLSTM)to identifying clinical timeexpressions and thetypeofthemsimultaneously.First,itcombinedcharacter-levelword embedingtrainedbyconvolutionalneuralnetwork (CNN) with word embedding trained from large-scale biomedical corpus together as input to BLSTM,then utilized BLSTM to modelcontext informationof each word,finally employedconditionalrandom field(CRF)tooptimize theoutputof BLSTM.This paper evaluated the model on the Semeval-20l6 Task 12; it receives the bestF1 value without requiring any handcrafted features orrules.Compared withthe state-of-the-art systems in this task,the proposed model improves theF1 scores by $3 \%$ ：

Key words: time expressions; clinical text; LSTM

病历文本中时间信息的抽取是近期生物医学研究的热点问题，这些信息可以用来帮助医务工作人员及科研工作者更好地认识疾病的发展模式，理解和认识动态的医学现象，是进行临床路径研究和智能决策支持系统开发的基础[I\~3]。病历文本是医务人员对患者进行医疗活动过程的记录，由于医务人员工作的快节奏及专业性特点，病历文本中的时间信息存在着书写格式不统一、表述不规范以及和医学事件相互联系的特点，这些特点给时间短语的识别带来了很大的困难，阻碍了时间信息的后续利用，所以自动识别病历文本中的时间短语信息成为重要的研究课题，得到了越来越多的关注。

在英文病历文本中抽取时间信息，目前影响比较大的是系列ClinicalTempEval共享任务，该任务已经在Semeval会议上举行了三次测评任务，分别为Semeval2015Task6[4]、Semeval2016Task12[5]和Semeval2017Task12[6]。该任务主要是从医院病历相关文本中抽取时间相关的信息，可以分为医学时间短语抽取，医学事件抽取、医学时间和事件关系抽取三个任务。医学时间短语识别是医学时间信息抽取任务中的第一步，也是最为关键的一步，它所识别的时间短语是医学时间和事件关系识别的基础，是整个任务的核心。

# 0 相关工作

从相关文献来看，目前时间短语的识别方法主要采用基于规则的方法和机器学习的方法。基于规则的识别方法认为，自然语言中基本的时间短语都有着清晰的结构和明显的特征通过设计完备的规则可以覆盖大部分的时间信息。在通用领域，Strotgen等人[7]采用基于正则表达式的模式设计了HeidTime系统来抽取时间表达式，然后再使用语言学的规则对表示式进行标准化转换，在TempEval-2的测评上取得了最高的F1值。Chang等人[8设计的SUTIME系统支持英文文本中四种时间类型的识别：时间（time）、持续的时间段（duration）、时间间隔（interval）和时间集合（set），现已经集成到斯坦福自然语言处理包中。Zhong 等人[9提出了一个叫做SynTime的方法来抽取时间表达式，在这个方法在推特数据集上的识别效果超过了现有的最好方法。由于病历文本中医学时间短语的多样性和不确定性，采用通用领域的基于规则的方法需要花费巨大的工作量，例如MayoTime[l0]在

2012i2b2的医学信息识别任务中设计了300多个规则完成了医学时间短语的抽取工作。

目前多数研究者采用机器学习中的线性统计模型来完成医学时间短语的抽取任务。在Semeval-2016的任务12中，大部分小组采用此类方法完成了时间短语的抽取任务。UTHealth组[1采用隐性马尔可夫（HMM）和支持向量机（SVM）相结合的序列标注器进行时间短语的识别，取得了最高的F1值。LIMSI组[12]和GUIR 组[13]使用基于条件随机场（CRF）的序列标注算法抽取时间短语。ULISBOA 组[14]使用基于支持向量机的序列标注器。以上这些小组无一例外地都使用了大量的句法、词法和领域知识作为特征，其中UTHealth组还使用了基于规则的系统SUTIME[8]的识别结果作为特征。特征工程的构建需要花费大量的时间和精力，而且，在构建特征的过程中难免引入的一些不准确的特征，也会影响最终的识别效果。

近年来，循环神经网络的变体一一基于双向长短时记忆单元的神经网络（BLSTM）由于能更好地学习到自然语言中的上下文语义特征，得到了广泛地应用。Huang 等人[15]抽取单词的拼写特征作为BLSTM 网络的输入，然后将BLSTM网络的输出序列使用CRF模型的进行了输出优化，在CONLL2003的组块识别任务上取得了 $8 8 . 8 3 \%$ 的F1值。实验表明BLSTM模型可以有效得建模句子的上下文语义表示，CRF可以对输出的标签优化，获得一个全局最优的标记序列。Ma 等人[16使用CNN模型学习单词的字符级别向量表示，并组合词向量一起作为BLSTM-CRF模型的输入，在未使用任何人工特征的情况下在词性标注和通用命名实体识别任务上取得了不错的成绩，实验不仅验证了BLSTM-CRF在序列标注问题上的有效性，还说明了CNN模型可以有效地学习到单词的拼写特征。李丽双等人[I7]使用CNN-BLSTM-CRF模型在BiocreativeIIGM和JNLPBA语料上进行生物医学命名实体识别，取得了目前最好的成绩。在使用深度神经网络进行医学时间短语识别的研究中，Fries[18]在SemEval-2016任务12的测评任务中使用了一个简单的双向循环神经网络(vanilla版本)进行医学时间短语的抽取，Chikka[19]使用卷积神经网络架构进行时间短语的抽取，识别效果比基于规则的方法和统计模型识别方法差。

从医学时间短语抽取流程的整体框架来看，大多数系统都是采用串行方法，即先识别出时间短语，再识别其类别，这种方法在一定程度上会造成错误的传播。Lee等人[1I提出在识别时间表达式的同时识别其类型的方法，该方法一定程度上可以避免错误的传播。针对病历文本中时间表达的多样性、关联性和不确定性，作者提出了一个三层的基于双向长短时记忆单元的神经网络系统进行时间短语识别：a)使用CNN训练得到的字符级别向量和大规模生物医学背景语料上训练得到的词向量进行组合作为网络的第一层词向量输入层；b)第二层使用BLSTM网络学习单词的上下文语义表示；c）第三层使用CRF对BLSTM网络输出的序列进行标签输出优化。在Semeval-2016的任务12中语料上的实验结果表明，在未使用任何人工特征的情况下，该模型达到了目前的最好效果。

# 1 模型及算法描述

病历文本中的时间短语抽取任务可以看成序列标注任务，参考先前的成功案例，在识别时间表达式的同时判别出时间的类型。采用BIO方式进行结果标注。例如用"B-Timex-Date"来表示一个单词是Date类型的时间表达式的开头，用“I-Timex-Time”方式来表示一个单词是Time 类型的时间表达式的非开头部分。

图1为本文提出的基于长短时记忆单元的神经网络架构其共分为三层来实现：第一层为词向量表示层，第二层为双向长短期记忆层（BLSTM)，第三层为标签输出层。首先将句子分离成一个单词序列，通过查询词向量表将输入的单词转换为相应的词向量序列，然后和使用卷积神经网络(CNN)训练出的单词的字符级别表示向量相拼接，拼接后的词向量用作双向长短时记忆层的输入，经过该层计算后输出带有单词上下文语义的向量表示，最后在标签输入层使用最大条件随机场（CRF）对输出的标签进行整体优化。

![](images/1b97e1c0ee0634000e1c231e678469dbbb782a5c8833a48fe241ebbd59ee7266.jpg)  
图1基于长短时记忆单元的神经网络架构 Fig.1Neural network architecture based on BLSTM

# 1.1 词向量表示层

词向量表示层的输入为单词，输出为该单词的向量表示。本研究中所使用的单词的向量表示由两部分向量拼接而成，一部分是由单词查询一个词向量表得到，另一部分是使用CNN网络计算的单词的字符级别表示向量。词向量表可以使用word2vector[20]在大规模的非标注数据集上自已训练，也可以使用领域内提供的公开向量集，这种公共数据集在大规模的语料上通过非监督学习而得到，具有很好的泛化效果。

Ma 等人[16]的研究表明，卷积神经网络可以通过卷积层能够很好地描述单词的局部特征，池化层可以进一步提取出单词局部特征中最具有代表性的部分。因此，本文提出使用CNN抽取病历文本中单词的字符级别特征（前缀、后缀以及拼写)，再通过字符级别特征与词向量相结合的方法来提高模型的性能。本文使用的CNN 模块与Ma 和Hovy不同之处在于：本文在初始字符向量时，对字符的大小写、标点符号对应了不同的字符向量。

本文使用的CNN的结构如图2所示。对于一个长度为 $\mathfrak { n }$ 的单词 $\mathbf { w } { = } \{ \mathbf { a } _ { 1 } , \mathbf { a } _ { 2 } , \cdots \mathbf { a } _ { \mathfrak { n } } \}$ ， ${ \bf a } _ { \mathrm { i } }$ 为单词中的第i个字符，定义 $e m b ( a _ { i } )$ 为该字符的字符向量，假设卷积神经网络的窗口大小C为1，则字符 $\mathbf { a } _ { \mathrm { i } }$ 最终的向量表示为前后各一个字符和自身字符的向量的连接，记为 $r _ { a _ { i } } = \left[ e m b ( a _ { i - 1 } ) , e m b ( a _ { i } ) , e m b ( a _ { i + 1 } ) \right]$ 卷积操作使用一个固定大小的卷积核在单词的字符向量矩阵上进行卷积来提取出局部特征，最后使用最大池化操作获取整个单词的字符级别的特征向量表示。

# 1.2双向长短期记忆层

双向长短时记忆（BLSTM）网络是一种特殊的循环神经网络（RNN）模型，它克服了传统RNN模型由于序列过长而产生的梯度消失问题[21,22]，已经被成功地运用到应用于实体识别、文本分类和机器翻译多个自然语言处理任务中。双向长短时记忆网络在结构上和双向RNN相似，唯一不同之处是它使用LSTM单元[23]替代了双向RNN网络上的隐藏单元。LSTM单元使用输入门、记忆单元、遗忘门、输出门来控制上下文信息被记忆或者被遗忘。其结构可以形式化地表示为

$$
\begin{array} { r l } & { f _ { t } = \sigma ( w _ { f } \cdot [ \mathrm { h } _ { t - 1 } \oplus \mathrm { x } _ { t } ] + \mathrm { b } _ { f } ) } \\ & { \mathrm { i } _ { t } = \sigma ( w _ { i } \cdot [ \mathrm { h } _ { t - 1 } \oplus \mathrm { x } _ { t } ] + \mathrm { b } _ { i } ) } \\ & { \tilde { c } _ { t } = \mathrm { t a n h } ( w _ { c } \cdot [ \mathrm { h } _ { t - 1 } \oplus \mathrm { x } _ { t } ] + \mathrm { b } _ { c } ) } \\ & { c _ { t } = f _ { t } \times c _ { t - 1 } + i _ { t } \times \tilde { c } _ { t } } \\ & { o _ { t } = \sigma ( w _ { o } \cdot [ \mathrm { h } _ { t - 1 } \oplus \mathrm { x } _ { t } ] + \mathrm { b } _ { o } ) } \\ & { h _ { t } = o _ { t } \times \mathrm { t a n h } ( c _ { t } ) } \end{array}
$$

其中： $\sigma$ 是激活函数 sigmod； ${ \mathrm { i } } _ { t } , f _ { t } , o _ { t } , c _ { t }$ 分别表示在t时刻的输入门、忘记门、输出门和记忆门； $w _ { i } , w _ { f } , w _ { c }$ 代表权重矩阵;$b _ { i } , b _ { f } , b _ { c }$ 为偏置向量。对于一个输入的向量序列$\{ x _ { 1 } , x _ { 2 } , \cdots x _ { n } \} , t \in { 1 \cdots n }$ ，每一个LSTM单元的输入为 $\{ x _ { t } , h _ { t - 1 } , c _ { t - 1 } \}$ ，输出为 $\{ h _ { t } , c _ { t } \} _ { \mathrm { ~ o ~ } } \dot { 1 } _ { t }$ 决定哪些新的信息被存放在当前的记忆单元$c _ { t }$ 中， $f _ { t }$ 决定哪些信息在当前的单元中将被丢弃掉， $o _ { t }$ 决定哪些信息将被输出到当前的 $h _ { t }$ 中。

![](images/104abd55345db9ec012aef00b3082e86d7ea3fed0f5e4a3f4d4eb4fdc7f102b2.jpg)  
图2卷积神经网络的结构  
Fig.2Structure of convolutional neural network

为了能够有效利用单词的上下文信息，本文采用如图1所示的BLSTM结构。BLSTM网络对每个输入句子分别采用从左到右地顺序（forward）和从右到左地顺序（backward）计算，每一个句子中的第 $\mathrm { ~  ~ { ~ t ~ } ~ }$ 个单词经过计算后得到两种不同的隐藏层向量表示： ${ h ^ { ( l ) } } _ { t }$ 和 ${ h ^ { ( r ) } } _ { t }$ ，双向长短时记忆层的输出由这两个向量的拼接计算得到，其公式如式（2）所示。

$$
\smash { \ddot { h } _ { t } = \operatorname { t a n h } ( W _ { h } \cdot ( h ^ { ( l ) } { } _ { t } \oplus h ^ { ( r ) } { } _ { t } ) + b _ { h } ) }
$$

# 1.3标签输出层

条件随机场(CRF)，是由Lafferty 等人[24]于2001年提出的无向概率图模型。CRF通过考虑相邻标签的关系获得一个全局最优的标记序列，近几年在许多序列标注任务中都有很好的表现。本文使用CRF算法对BLSTM层的输出结果进行优化，获得全局最优的标签输出。

对于一个句子：

$$
\boldsymbol { x } = \{ x _ { 1 } , x _ { 2 } , \cdots x _ { n } \}
$$

定义P为其在BLSTM层计算后输出的评分结果。 $\mathrm { ~ \bf ~ P ~ }$ 为 $\mathbf { n } \times \mathbf { k }$ 的矩阵， $\mathbf { k }$ 为输出的标签种类个数，定义 $P _ { i , j }$ 为句子中第i个单词输出第 $\mathrm { j }$ 个标签的概率。对于一个预测序列 $y = \{ y _ { 1 } , y _ { 2 } , \cdots y _ { n } \}$ ，它的评分可以定义为

$$
S ( x , y ) = \sum _ { i = 0 } ^ { n } A _ { y _ { i } , y _ { i + 1 } } + \sum _ { i = 1 } ^ { n } P _ { i , y _ { i } }
$$

其中：A是转移矩阵； $A _ { i , j }$ 代表由标签i转移到标签j这里使用softmax函数定义产生序列 $\mathbf { y }$ 的概率。

$$
\mathsf { p } ( \mathsf { y } | X ) = \frac { e ^ { S ( x , y ) } } { \sum _ { \tilde { \mathsf { y } } \in Y _ { X } } e ^ { S ( x , \tilde { \mathsf { y } } ) } }
$$

训练数据的似然函数为

$$
\log \left( \mathrm { p } ( \mathbf { y } | X ) \right) { = } \mathbf { S } ( \mathbf { x } , \mathbf { y } ) { - } \log \left( \sum _ { \tilde { \mathbf { y } } \in Y _ { X } } e ^ { S ( x , \tilde { \mathbf { y } } ) } \right)
$$

$Y _ { \chi }$ 表示对应一个句子X所有可能的标记序列。通过上面的公式得到一个有效合理的输出序列。预测时，由公式输出整体概率最大的一组序列：

$$
\mathbf { y } ^ { * } = \mathrm { a r g m a x } ( \mathbf { S } ( \mathbf { x } , \tilde { \mathbf { y } } ) )
$$

# 1.4训练参数

训练过程中，采用随机梯度下降模型AdaGrad[25],学习率选取为0.03，正则化参数为 $1 0 ^ { - 8 }$ 。为了减轻模型的过度拟合，在BLSTM层的输入/输出部分增加了Dropout,其值定为0.5。参数根据开发集的结果上进行了调整。本文选取可公共使用的200 维的Pubmed[26]向量集作为单词的初始向量查询表，此向量集从大量的生物医学文献和摘要中训练而成。向量集选取的实验依据将在3.2.1节中给出。其他向量定义为200维。CNN的窗口定为1，输出向量长度定为20。

# 2 实验

# 2.1数据集与评测方法

文中采用Semeval-2016任务12提供的梅奥医学中心标注的癌症病人的病理报告和临床记录语料(THYME 语料)[27]进行了各项实验。数据集分为训练集、开发集和测试集三部分。其中训练集中含有293篇临床记录文档，开发集和测试数据集分别含有147篇和152篇文档，它们分别包含3833、3078、1952个时间表达式。

在实验中使用和该任务一致的评测方法，在下面的表中P代表准确率(precession),R代表召回率(recall)，F1代表F1值（F1-measure）。

# 2.2实验结果

# 2.2.1词向量的表示

词向量的表示对序列标注任务的结果有着很大的影响，文中选取以下三类词向量进行了对比实验：a)随机初始化长度为100维、200维、300维的词向量进行实验；b）采用word2vec工具，对任务提供的THYME语料进行训练得到的100 维、200 维、300 维的词向量；c）由Pyysalo[26]从大规模生物医学语料中训练出来的200 维的Pubmed词向量集。实验结果如表1所示，第三类向量取得了最好的泛化结果。

表1词向量的选取对识别性能的影响  
Table 1Results with different choices of word embedding   

<html><body><table><tr><td>词向量表示</td><td>P</td><td>R</td><td>F1</td></tr><tr><td>随机初始100维</td><td>81.75</td><td>78.31</td><td>79.99</td></tr><tr><td>随机初始200 维</td><td>82.35</td><td>78.68</td><td>80.47</td></tr><tr><td>随机初始300维</td><td>82.36</td><td>78.43</td><td>80.35</td></tr><tr><td>THYME语料训练100维</td><td>81.93</td><td>78.84</td><td>80.36</td></tr><tr><td>THYME语料训练200维</td><td>82.22</td><td>79.84</td><td>81.01</td></tr><tr><td>THYME 语料训练300 维</td><td>82.41</td><td>79.75</td><td>81.06</td></tr><tr><td>Pubmed200 维向量</td><td>83.72</td><td>80.03</td><td>81.83</td></tr></table></body></html>

# 2.2.2神经网络架构分层实验

对神经网络结构进行分层测试，对比实验的结果来分析各个模块在模型中起到的作用。实验结果如表2所示“-CRF”表示模型去掉CRF层，标签结果采用softmax 进行输出。“-pretrain”表示模型不使用训练好的Pubmed向量集作为初始向量，而是采用随机方法初始词向量；“-CNN”表示模型去掉CNN层，从Pubmed向量集中读取的向量直接作为词向量的表示；“CNN-BLSTM-CRF”为本文实验最终所选用的神经网络模型。

# 表2模型的分层测试

Table 2Ablation test performance evaluation   

<html><body><table><tr><td>模型</td><td>P</td><td>R</td><td>F1</td></tr><tr><td>-CNN</td><td>80.54</td><td>79.82</td><td>80.18</td></tr><tr><td>-pretrain</td><td>82.35</td><td>78.68</td><td>80.47</td></tr><tr><td>-CRF</td><td>79.86</td><td>78.34</td><td>79.09</td></tr><tr><td>CNN-BLSTM-CRF</td><td>83.72</td><td>80.03</td><td>81.83</td></tr></table></body></html>

# 2.2.3 Dropout 设置

Dropout可以防止神经网络模型的过度拟合。文中采用不同的Dropout数值，在数据集上进行了测试，结果如表3所示。

Table 3Results with different dropout values   

<html><body><table><tr><td>Dropout</td><td>P</td><td>R</td><td>F1</td></tr><tr><td>-</td><td>82.51</td><td>79.38</td><td>80.91</td></tr><tr><td>-0.1</td><td>82.82</td><td>79.63</td><td>81.19</td></tr><tr><td>-0.3</td><td>83.29</td><td>79.92</td><td>81.57</td></tr><tr><td>-0.5</td><td>83.72</td><td>80.03</td><td>81.83</td></tr><tr><td>-0.8</td><td>83.16</td><td>79.92</td><td>81.51</td></tr></table></body></html>

# 2.3与现有其他工作的对比

经过上述三组实验，文中选取维度为200的Pubmed向量，Dropout为0.5进行实验，并将实验结果与其他优秀学者的实验结果相比较，比较结果如表4所示。

表3不同Dropout 对模型性能的影响  
表4和其他学者的工作比较  
Table 4Performance comparison with previous research   

<html><body><table><tr><td>团队</td><td>P</td><td>R</td><td>F1</td></tr><tr><td>CDE-IITH(Chikka,2016)*</td><td>0.614</td><td>0.560</td><td>0.586</td></tr><tr><td>Brundlefly (Fries,2016)*</td><td>68.60</td><td>41.50</td><td>51.70</td></tr><tr><td>UFPRSheffield(Tissot et al.,2015)</td><td>0.311</td><td>79.50</td><td>44.70</td></tr><tr><td>UTHealth (Lee et al.,2016)</td><td>83.60</td><td>75.70</td><td>79.50</td></tr><tr><td>LIMSI-1 (Grouin and Moriceau, 2016)</td><td>84.00</td><td>51.00</td><td>63.50</td></tr><tr><td>CNN-BLSTM-CRF(文中模型)</td><td>83.72</td><td>80.03</td><td>81.83</td></tr></table></body></html>

Lee等人[I]使用隐性马尔可夫（HMM）与支持向量机（SVM)相结合的序列标注器，结合大量的特征工程（词形、词性、词干和相关字典等）进行时间短语的识别，在Semeval-2016的评比中取得了最好的F1（79.5）值。Grouin等人[12]使用条件随机场（CRF）和基于规则的系统（HeidelTime）相结合的方法取得了Semeval-2016任务评比中准确率第一名，但是F1 值却非常不理想。Tissot 等人[28]设计一个基于规则的医学时间识别系统，在Semeval-2015的测评中取得了最好的成绩。在使用神经网络的方法中，Fries[18]使用在两个医学语料上训练得到的词向量输入双向循环神经网络(vanilla版本)进行医学时间短语的抽取，准确率和F1值均很低。Chikka[19]使用卷积神经网络架构进行了时间短语的抽取实验，结果低于其用SVM获得的识别效果。

通过以上对比分析可以看出，本文的神经网络模型在未使用任何人工特征的情况下，取得了目前最好的成绩。

# 2.4错误分析

对实验的结果进行分析，主要发现有如下两类错误：

a)时间短语中的介词经常没有被识别出来，例如标准答案中的时间短语“for the past twentyyears”，本文识别的短语为“the past twenty years”，漏掉了介词“for”。在训练语料中，一些介词时间短语的标注标准中有的包含介词，有的不包含介词，这会影响最终的识别效果。

b）样本的数量会影响神经网络系统的识别效果，例如Time类型的短语在训练数据中所占的比例很少，识别的正确率也相应地非常低。在神经网络的训练过程中，如何解决由于样本的不平衡而引起的结果偏差，也是本文要解决的一个

问题。

# 3 结束语

本文提出了一个基于深度神经网络架构的病历时间短语抽取模型，模型使用卷积神经网络有效地表示了单词的词形特征，通过BLSTM网络序列上下文语义信息，并使用CRF算法对标签输出结果进行了优化，在没有使用任何人工特征和医学领域背景知识的情况下性能优于目前最好的系统。模型还可以用来解决一些类似的序列标注问题，如进行医学事件的抽取。将来，可以通过多任务的联合学习，使系统获得更好地泛化能力。譬如，本文可以训练一个同时识别时间和事件信息的联合神经网络模型来获得更好地效果。

# 参考文献：

[1]Hao Tianyong,Pan Xiaoyi,Gu Zhiying,et al.A pattern learning-based method for temporal expression extraction and normalization from multi-lingual heterogeneous clinical texts [J].Bmc Medical Informatics & Decision Making,2018,18 (Suppl 1): 22.   
[2] Moharasar G,Tu B H.A semi-supervised approach for temporal information extraction from clinical text [C]// Proc of IEEE Rivf InternationalConferenceonComputing&Communication Technologies,Research,Innovation,and Vision for the Future.2016: 7-12.   
[3]Liu Zengjian，Tang Buzhou,Wang Xiaolong，et al. CMedTEX:a rule-based temporal expression extraction and normalization system for chinese clinical notes [Cl./Proc of AMIA Annual Symposium Proceedings. 2017: 818.   
[4]Bethard S,Derczynski L,Savova G,et al. SemEval-2015 task 6: clinical tempeval [C]// Proc of the 9th International Workshop on Semantic Evaluation.2015: 806-814.   
[5]Bethard S,SavovaG,Chen Weite,et al. Semeval-2016 task 12: clinical tempeval [C]// Proc of the 10th International Workshop on Semantic Evaluation. 2016:1052-1062.   
[6]Bethard S,Savova G,Palmer M,et al. SemEval-2017 task 12: clinical tempeval [C]// Proc of the 11th International Workshop on Semantic Evaluation. 2017: 565-572.   
[7]Strotgen J, Gertz M. HeidelTime: high quality rule-based extraction and normalization of temporal expressions [C]// Proc of International Workshop on Semantic Evaluation.2010:321-324.   
[8]Chang A X,Manning C D. SUTIME:a library for recognizing and normalizing time expressions [J]. Lrec,2012,9(1): 3735-3740.   
[9]Zhong Xiaoshi, Sun Aixin,Cambria E.Time expressions analysis and recognition using syntactic token types and general heuristic rules [C]// Proc of the 55th Annual Meeting of the Association for Computational Linguistics.Vancouver Canada: ACL,2017: 420-429.   
[10] Sohn S,Wagholikar KB,Li Dingcheng,et al. Comprehensive temporal information detection from clinical text: medical events,time,and tlink identification [J].Journal of the American Medical Informatics Association Jamia,2013,20 (5): 836-842.   
[11] Lee HJ,Xu Hua,Wang Jingqi,et al.UTHealth at SemEval-2016 task 12:an end-to-end system for temporal information extraction from clinical notes [Cl// Proc of the lOth International Workshopon Semantic Evaluation.2016:1292-1297.   
[12] Grouin C,Moriceau V. LIMSI at SemEval-2016 task 12:machine learning and temporal information to identify clinical events and time expressions [C]// Proc of the 10th International Workshop on Semantic Evaluation.2016:1225-1230.   
[13] Cohan A,Meurer K,Goharian N.GUIR at SemEval-2016 task 12: temporal information processing for clinical narratives [C]//Proc of the 10th International Workshop on Semantic Evaluation.2016:1248-1255.   
[14]Barros M,Lamurias A,Figueiro G,et al.ULISBOAat SemEval-2016 task12:extraction of temporal expressions,clinical events and relations using ibent [C]//Proc of the 1Oth International Workshop on Semantic Evaluation.2016.   
[15]Huang Zhiheng,Xu Wei,Yu Kai.Bidirectional lstm-crf models for sequence tagging [J].Computer Science,2015.   
[16] Ma Xuezhe,Hovy E.End-to-end sequence labeling via bidirectional lstm-cnns-crf [C]//Proc of the 54th Annual Meeting of the Association for Computational Linguistics.Berlin:Association for Computational Linguistics.2016:1064-1067.   
[17]李丽双，郭元凯．基于CNN-BLSTM-CRF模型的生物医学命名实体 识别[J].中文信息学报，2018,32(1):117-122.(LiLishuang,Guo Yuankai. Biomedical name entity recognition with cnn-blstm-crf [J]. Journal of Chinese Information Processing,2018,32(1):117-112.)   
[18] Fries J.Brundlefly at SemEval-2O16 task 12:Recurrent neural networks vs.joint inference for clinical temporal information extraction [C]// Proc of the 1Oth International Workshop on Semantic Evaluation.2016: 1274-1279.   
[19] Chikka V R.CDE-IIITH at SemEval-2016 task 12:extraction of temporal information from clinical documents using machine learning techniques [C]//Proc of the 1Oth International Workshop on Semantic Evaluation.2016:1237-1240.   
[20] Mikolov T,SutskeverI,Chen Kai,et al.Distributed representations of Words and phrases and their compositionality [J].Advances in Neural Information Processing Systems,2013,26:3111-3119.   
[21]Bengio Y, Simard P,Frasconi P.Learning long-term dependencies with gradient descent is difficult [J].IEEE Trans on Neural Networks,1994, 5 (2): 157-166.   
[22] Hochreiter S.The vanishing gradient problem during learning recurrent neural nets and problem solutions [J]. International Journal of Uncertainty, Fuzziness and Knowledge-Based Systems,1998,6 (2): 107-116.   
[23] Graves A,Schmidhuber J.Framewise phoneme classification with bidirectional lstm and other neural network architectures [J].Neural Networks,2005,18(5):602-610.   
[24]Lafferty，John D，McCallum，et al.Conditional random fields: probabilistic models for segmenting and labeling sequence data [M// Departmental Papers (CIS).2001: 282-289.   
[25] Duchi J,Hazan E,Singer Y.Adaptive subgradient methods for online learning and stochastic optimization [J].Journal of Machine Learning Research,2011,12(7): 257-269.   
[26]Pyysalo S,Ginter F,Moen H,et al.Distributional semantics resources for biomedical text processing[C]//Proc of LBM.2013:39-44.   
[27] 4Th SW,Bethard S,Finan S,et al.Temporal annotation in the clinical domain [J].Trans of the Association for Computational Linguistics, 2014,2 (1): 143-154.   
[28] Tissot H,Gorrell G,Roberts A,et al.UFPRSheffield: contrasting rule-based and support vector machine approaches to time expression identification in clinical tempeval [C]// Proc of the 9th International Workshop on Semantic Evaluation.2015:835-839.