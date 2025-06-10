# 基于MAC-LSTM的问题分类研究\*

余本功ab，许庆堂ä，张培行‘

(合肥工业大学 a.管理学院;b.过程优化与智能决策教育部重点实验室，合肥 230009)

摘要：问题分类是问答系统问题分析研究的基础组成部分，其精度直接影响自然语言理解效果的好坏。针对问句文本通常较短、语义信息与词语共现信息不足等问题，提出一种多层级注意力卷积长短时记忆模型（multi-level attentionconvolution LSTM neural network，MAC-LSTM）的问题分类方法。相比基于词嵌入的深度学习模型，该方法使用疑问词注意力机制对问句中的疑问词特征重点关注。同时，使用注意力机制结合卷积神经网络与长短时记忆模型各自文本建模的优势，既能够并行方式提取词汇级特征，又能够学习更高级别的长距离依赖特征。实验表明，该方法较传统的机器学习方法和普通的卷积神经网络、长短时记忆模型有明显的效果提升。

关键词：问答系统；问题分类；注意力机制；疑问词注意力机制；卷积神经网络；长短时记忆模型中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2018.05.0452

# Question classification based on MAC-LSTM

Yu Bengonga, b, Xu Qingtanga, Zhang Peihanga (a.SchoolofManagement,b.KeyLaboratoryofProcess Optimization&InteligentDecision-makingofMinistryofEducation, HefeiUniversity of Technology,Hefei 230o09,China)

Abstract: Questionclassificationisthebasicpartoftheresearchonquestionansweringsystem.Itsacuracydirectlyaffects te quality of natural languageunderstanding.Most of thequestion classification methodsare based on supervised learning algorithms whichrequireword embeddinganddoes notconsiderthe interogative features.However,questiontextisusualy shortandthe informationofsemantic informationand word co-occurrence are not enough.Toaddresstheabove problems,this paper proposes a multi-evel atention convolution LSTM neural network (MAC-LSTM) forquestion clasification.This approachuses theinterrogative wordattention mechanismto focus onthe interrogativefeatures inthe heterogeneous question contexts.At thesame time,usingtheattention mechanismcombined with theadvantagesofconvolutional neural networkand long-short memory model recurent neural network (LSTM).MAC-LSTM is able to capture both local features ofphrases as well as globaland temporal sentence semantics.Experiments show that，our approachachieves beter performance than traditional machinelearingmethod,ordinaryconvolutionalneuralnetwork,andtraditionalLSTMonquestionclasification tasks without the need of prior knowledge.

Key words:questionanswering;questionclasification;ttentionmechansm; interrogativeattentionmehansm;convolutional neural networks; LSTM

# 0 引言

问答系统(question and answering,QA)是信息检索领域的热门研究领域之一，能够为用户提出的自然语言问题提供一个简明、准确的答案，较好地满足了用户快速、精准地获取信息的需求[1]。问答系统的处理流程主要包括四步，即问题分类、语义理解、文本检索、答案抽取[2]。其中，问题分类通过确定问题的目标答案类型，可以为后续信息检索和答案抽取提供语义限制和约束，缩小候选答案的查找范围。例如，“最有名的徽菜馆在哪里？”是一个关于地点的问题，后续答案抽取时只需要匹配候选答案中的地点类型实体即可，准确有效地提升了问答精度[3]。与此同时，问题分类还可以为问答模式的选择策略提供依据。例如，“正宗徽菜的特点是什么？”是一个描述类问题，生成答案的时候应该侧重于对实体特征的描述与介绍，提供给用户最想获取的答案知识[4]。

与一般的文本分类不同，问题分类的语料具有以下特征：a）问句中的疑问词与问题类别有很强的相关性，加入疑问词特征可以使分类结果更准确；b）问句文本通常较短、特征共现信息不足，且具有口语化、歧义性特征。现有的问题分类方法主要是基于规则的方法和基于机器学习的方法。这些方法都没有考虑问题文本语料的特殊性，所以在语义层次上会面临数据特征稀疏和语义敏感问题，且抽取疑问词特征困难。

针对以上问题，本文将深度学习模型与注意力机制相结合，提出一种多层次注意力卷积长短时记忆模型。该方法使用疑问词注意力机制重点关注问句中的疑问词特征，强化了模型的疑问词特征抽取能力。同时，在卷积层与LSTM层之间加入注意力机制，使模型既能够并行方式提取词汇级特征，又能够学习更高级别的长距离依赖特征。

# 1 相关工作

早期的问答系统面向特定领域，强调特定的领域知识，所以问题分类规则需要拥有相关背景的专家制定。比如Biswas等人[5]针对医疗数据抽取固定的语法模式，然后利用语法模式来判定问题类别。这种手动设计的特征规则需要大量人力，并且只适用于特定的数据集，可迁移性差。而基于机器学习的问题分类方法具有较强的适用性，这种分类方法的研究主要把精力放在机器学习模型的选择和特征提取上面，即如何在较短的问题文本上面抽取特征、提取出浅层的语义信息。比如Li等人[6]利用双语（英语汉语）、句子长度、句子音节数等信息作为支持向量机模型的扩展特征，对英文句子进行分类并取得了优良效果。考虑到问句中疑问词的重要性，Hu等人[提出了疑问语义单元的概念，并结合HOWNET对其进行语义扩展，在开放式问题分类实验中达到了较高的分类精确度。但是基于机器学习的问题分类算法面临着数据特征稀疏的问题，不能很好地抽取文本中蕴含的语义信息，分类器的效果仍然有待提升。

当前，深度学习在自然语言处理等领域取得了优秀表现，也有许多学者利用深度学习技术[8来解决问答系统问题分类任务。Li等人[9将卷积神经网络应用于知识库问答系统问题分类，并扩展了答案文本、答案类型、答案路径等特征来学习问题的分类规则。对于同样的问题，Feng等人[10]使用共享卷积神经网络来训练问题答案对，并在此基础上进行了语义相似度计算。这些方法使用了卷积神经网络来解决问题分类任务，能够较好地捕捉从数据本身到高层语义的复杂映射，具有远超于传统机器学习模型的表达能力。但是这些方法的参数复杂且没有考虑文本语料的时序特征。针对这一问题，有一些学者开始使用长短时记忆模型来处理问句这种序列数据。长短时记忆模型是一种特殊的循环神经网络改进结构，能够解决原模型梯度消失和长距离依赖的问题[11]。Wang 等人[12]基于多层长短时记忆网络模型训练问答对的联合特征向量，把问答匹配问题转换为分类或排序问题。此外，考虑到卷积神经网络和长短时记忆模型各自对文本建模的优点，Zhou等人[13]将两种模型相结合提出了一种新颖的组合模型（C-LSTM)，并指出卷积神经网络和长短时记忆模型提供了互补的信息，该模型在情感分类和问题分类两个任务中都取得了优良的表现。

注意力机制的原理是仿照人脑的注意力思维，通过自动加权的方式对整体信息进行局部重点关注，帮助深度学习模型取得显著的精度提升[14,15]。2014 年，Bahdanau 等人[16]使用基于注意力机制的循环神经网络来解决机器翻译任务，开启了注意力机制在自然语言处理领域的应用。Zhou等人[17]提出了双语长短时记忆模型的层次注意力机制来解决跨语言情感分析任务，使用单词级注意力模式可以知道每个句子中的哪个词是具有决定性的，而句子级注意力模式学习哪些句子对于确定整体文档的情绪更为重要。另外，考虑到卷积神经网络在短文本分类场景中的优良效果，有学者探究了注意力机制与卷积神经网络的结合[18]。其中，文献[19]通过注意力机制的方法将用户和产品信息与文本语义信息结合，提出了一个层次化卷积神经网络。该方法能够在一定程度减少模型参数，并使得文本中语义信息更加丰富。

以上研究成果促使人们从问题分类领域引用注意力机制来衡量特征的重要性，结合相关模型可以实现特征的有效提取。本文提出的多层级注意力卷积长短时记忆模型利用卷积神经网络对疑问词注意力矩阵提取局部特征，并结合注意力矩阵筛选对问题分类最相关的特征映射输入给双向长短时记忆模型。此外，在问答领域的问题分类任务中，疑问词是具有重要影响的特征。为了有效提取疑问词特征，本文提出了一种基于疑问词的注意力机制，通过构造疑问词注意力矩阵强化模型对疑问词特征的重点关注。这样MAC-LSTM同时拥有长短时记忆模型捕获全局上下文和卷积神经网络捕获问句局部特征的优势，并拥有了对疑问词等重点特征的抽取能力。

# 2 基于MAC-LSTM的问题分类

本文提出的MAC-LSTM模型通过两个层次的注意力机制学习问题文本的疑问词特征，有效提高问题分类的准确度。首先，在模型输入层引入疑问词注意力机制，通过疑问词典构建疑问词注意力矩阵，强化问句表示中的疑问词语义信息，并将疑问词注意力矩阵输入卷积层提取局部特征；其次，模型使用注意力矩阵来筛选对问题分类最有用的卷积特征，输送给双向长短时记忆模型层进行高层次时序特征抽取；最后，将融合后的特征向量加入到Softmax分类器中完成问题分类任务。模型结构如图1所示。

# 2.1基于疑问词注意力机制的输入表示

与普通文本分类不同，问句的类型判别更加依赖于疑问词这一分类特征。这是由于问题文本较短、语义信息和词语共现信息不足，所以问句中的疑问词对问题分类的结果影响较大。而深度学习模型一般使用的词向量并没有对疑问词信息进行重点关注。针对该问题，本文提出了一种基于疑问词的注意力机制，通过构建疑问词典，将词向量与疑问词对角关注矩阵组合，使模型有能力确定哪一部分句子对疑问词最有影响力。具体方法为：收集汉语问句中的疑问词建立疑问词典，如“谁""哪里”“多少”等都属于疑问词；然后对问句分词后查找疑问词典，找到问句中的疑问词 $e$ ；随后以词为单位训练词向量 $W _ { n }$ ；最后引入对角关注矩阵 $A ^ { r }$ 来表征句子中普通词语 $w _ { i } \in W _ { n }$ 与疑问词 $e$ 之间的语境相关性和连接强度。其元素 $A _ { i } ^ { r }$ 的计算公式如下：

$$
A _ { i } ^ { r } = f \left( e , w _ { i } \right) \cdot \beta
$$

其中：疑问词 $e$ 通过本文构造的疑问词典，扫描问句分词序列得到；函数 $f$ 为词向量的内积运算； $\beta$ 为参数向量，并且在训练过程期间通过反向传播被新。同时对于每一个对角关注矩阵元素 $A _ { i } ^ { r }$ ，定义：

$$
\mathfrak { a } _ { i } ^ { r } = \frac { \exp \bigl ( A _ { i } ^ { r } \bigr ) } { \sum _ { j = 1 } ^ { n } \exp \bigl ( A _ { j } ^ { r } \bigr ) }
$$

来表示第 $i$ 个普通词 $w _ { i }$ 与疑问词 $e$ 之间的相对重要程度，并在此基础上构造基于注意力机制的疑问词向量：

$$
\mathbf { X } _ { i } = \mathbf { \boldsymbol { q } } _ { i } ^ { r } \cdot \mathbf { \boldsymbol { w } } _ { i }
$$

模型输入表示层的最终结果是基于注意力机制的疑问词向量排列矩阵：

$$
{ \mathbf X } = \left[ { \mathbf x } _ { 1 } , { \mathbf x } _ { 2 } , \cdots , { \mathbf x } _ { n } \right]
$$

其中：矩阵维度为 $R ^ { l \times n }$ ，1为词向量的维度， $\mathfrak { n }$ 是问句长度;逗号代表行矢量级连接。图2描述了基于注意力机制的疑问词向量表示矩阵构造的详细过程。

![](images/c952d64cec5f31d63820287d708fbea392835b2c0e7a5a5ffe4051230f42191c.jpg)  
图1基于MAC-LSTM的问题分类模型

![](images/734a1286433cf1fe83ca1525d1c8e431ecd4e07dbf16a70b48cf5351f97f7c05.jpg)  
Fig.1Question classification model based on MAC-LSTM   
Fig.2Interrogative word embedding attention matrix

# 2.2通过卷积运算进行特征抽取

卷积神经网络能够通过卷积运算从原始数据中抽取局部特征。本文使用 $d$ 个相同大小的一维滤波器在疑问词向量序列上滑动，以提取不同位置的文本特征，得到疑问词语义依存关系特征映射。一维滤波器表示为 $m \in R ^ { l \times k }$ ，其中 $k$ 为滤波器的宽度。此时，句子中的第 $i$ 个词语对应的窗口矩阵 $w _ { i }$ 由 $k$ 个一维向量组成：

$$
\mathbf { W } _ { i } = [ x _ { i } , x _ { i + 1 } , \cdots , x _ { i + k - 1 } ]
$$

其中：逗号代表行矢量级连接。卷积滤波器 $m$ 与每个位置处的窗口矩阵(k-gram)卷积运算生成特征映射 $\mathbf { c } \in \mathbf { R } ^ { n - k + 1 }$ ，这里特征映射每个元素 $\mathrm { ~ c ~ } _ { j }$ 的计算公式定义如下：

$$
\mathbf { c } _ { j } = f \big ( \mathbf { W } _ { i } ^ { * } m + b \big )
$$

其中： $^ *$ 为元素乘法； $\textit { b }$ 为偏差项。相关研究表明ReLU具有单侧抑制性和相对宽阔的兴奋边界，并通过引入网络稀疏性从而获得更快的特征学习速率[20]。本文非线性激活函数 $f$ 选择ReLU，公式如式(7)所示。

$$
f ( x ) = m a x ( 0 , x )
$$

为保留原文数据的时序性特征，对于d个具有相同长度的特征映射 $\mathbf { \Psi } _ { c }$ ，将其转置重排为对应与每个窗口矩阵 $\mathbf { W } _ { i }$ 的特征表示：

$$
\mathbf { E } = \left[ c _ { 1 } ; c _ { 2 } ; \cdots ; c _ { d } \right]
$$

其中：分号表示列向量的连接； $c _ { i }$ 是使用第 $i$ 个滤波器生成的特征向量。 ${ \bf E } \in { \bf R } ^ { ( d ) \times ( n - k + 1 ) }$ 的每列 $E _ { j }$ 是原问题文本位置 $j$ 处窗口向量的新特征表示形式。

# 2.3基于注意力机制的时序特征抽取

对于问题分类任务，问题的分类规则依赖于前向和后向的上下文信息，因此本文将卷积层提取的窗口映射输入给双向长短时记忆模型进一步提取文本时序特征。双向长短时记忆模型层结构如图3所示。

![](images/7973077a4aa94bacdb26c24417e3d36492f9e5a0cc8cbcb598d84f6f7993f2bc.jpg)  
图2疑问词向量注意力矩阵构建  
图3双向长短时记忆模型结构  
Fig.3Bidirectional LSTM

图3中，方框表示长短时记忆单元： $\vec { h }$ 为前向长短时记忆模型在 $\mathbf { \Phi } _ { t }$ 时刻的输出： $\ddot { h }$ 为后向长短时记忆模型在 $\mathbf { \Psi } _ { t }$ 时刻的输出。通过串接操作将前向序列和后向序列的输出进行合并，即可得到文本的上下文语义表示。

为了让整体模型在句子层面有能力自动识别句子中对问题分类最相关的部分，本文提出了一种基于注意力机制的连接模式来连接卷积层与长短时记忆模型。具体做法为：对卷积特征构造加权注意力矩阵 $G _ { i }$ 来比较卷积特征的重要性。通过不同的权值大小反映语义重要性的大小，对更重要的句子部分进行重点关注，同时减少了特征提取过程中的信息丢失和信息冗余。

注意力矩阵计算方式如下：

$$
A _ { i } ^ { c } = t a n h \bigl ( { \cal U } \cdot { \cal E } _ { j } + b \bigr )
$$

其中： $U$ 是神经网络学习的加权参数矩阵； $b$ 表示注意力机制的线性偏差。 $A _ { i } ^ { c }$ 为 $\mathrm { E } _ { j }$ 对问题分类的重要程度函数，进一步对其归一化处理：

$$
a _ { i } ^ { c } = \frac { \exp \bigl ( A _ { i } ^ { c } \bigr ) } { \sum _ { i = 1 } ^ { m } \exp \bigl ( A _ { i } ^ { c } \bigr ) }
$$

最后，将这个注意力矩阵与卷积层的输出 $\mathrm { ~ E } _ { j }$ 相乘，把向量$G _ { i }$ 表示对分类结果重要的部分并作为双向长短时记忆模型的输入。

$$
\mathbf { G } _ { i } = \boldsymbol { a } _ { i } ^ { c } \cdot \boldsymbol { E } _ { j }
$$

经过双向长短时记忆模型的时序语义建模，最后将隐藏层的输出向量作为Softmax分类器的输入，从全局角度对特征进行分析，进而完成问题模型的分类任务。

# 3 实验与分析

为了验证本文模型的有效性，解决问题分类任务，本文将在不同的中文短文本数据集上进行对比实验。实验环境为如表1所示。

为进行对比实验，本文采用与 Zhou 等人[13]相同的词向量训练配置，使用word2vec 的 skip-gram 训练模式，上下文窗口大小设置为5，词向量维度大小设为100，得到原始短文本的输入表示即词组映射矩阵。

表1实验环境及配置  

<html><body><table><tr><td>实验环境</td><td>环境配置</td></tr><tr><td>操作系统</td><td>Windows10企业版</td></tr><tr><td>CPU</td><td>Inter Corei5-6500 3.2GHz</td></tr><tr><td>GPU</td><td>NVIDIAGeForceGTX1070</td></tr><tr><td>内存</td><td>16G</td></tr><tr><td>编程语言</td><td>Java</td></tr><tr><td>分词工具</td><td>ICTCLAS2016</td></tr><tr><td>深度学习框架</td><td>DeepLearning4J</td></tr></table></body></html>

此外，问题分类体系的构建是问题分类的前提[2I]。对于英文问题分类，各机构往往对TRECQA标准数据集采用UIUC分类体系，将问题分为ABBR、DESC、ENTY、HUM、LOC和NUM六大类。而中文问题分类没有统一的分类体系，被大多数学者采用的是哈尔滨工业大学信息检索和社会计算中心所提出的分类体系，它根据汉语的特点提出包括描述类（DES）、人物类（HUM）、地点类（LOC）、数字类（NUM）、时间类（TIME）、实体类（OBJ）六个大类，每个大类及其实例如表2所示。

# 3.1数据集的选择与处理

本文选用的数据集分为三个部分：百度实验室数据集6205条数据①，CCF国际自然语言处理与中文计算会议2016(NLPCC

2016）QA评测的问题集共9604 条数据②，NLPCC2017QA评测的问题集共9518条数据，共有25327条数据。其中NLPCCQA 提供的公开数据集格式清晰、质量高，但数据集中只有问题与答案对，所以本文对该数据进行了人工标注工作。在本任务中，每个问题都由3人独立标注，对于有异议的数据存储数据库最后协商标注。同时，为排除数据集里偶然误差的干扰，本文将各数据集大致按照 $20 \%$ 的比例随机划分训练集与测试集

表2分类体系  
Table 2 Category system   

<html><body><table><tr><td>大类</td><td>代表例子</td></tr><tr><td>描述类（DES)</td><td>万达广场主要经营的是什么生意？</td></tr><tr><td>人物类（HUM)</td><td>《机械设计基础》这本书的作者是谁？</td></tr><tr><td>地点类（LOC)</td><td>安德烈是哪个国家的人呢？</td></tr><tr><td>数字类（NUM)</td><td>合肥地铁一号线总投资额是多少？</td></tr><tr><td>时间类（TIME）</td><td>华严寺何时建造的？</td></tr><tr><td>实体类（OBJ)</td><td>中国第二大民族是什么族？</td></tr></table></body></html>

# 3.2对比实验设置

本文提出的MAC-LSTM模型通过多层级注意力机制将卷积神经网络与长短时记忆模型相结合，针对问题分类任务对疑问词特征重点关注。为验证模型的有效性，本文设置多种模型方法在两种数据集上进行对比实验，

a)SVM。基于Li等人[提出的使用线性核函数的SVM 模型，采用词袋模型进行文本表示，并运用TF-IDF 算法对单词进行权重计算，是效果较好的传统分类模型。

b)CNN。由 $\mathrm { K i m ^ { [ 8 ] } }$ 提出的基础卷积神经网络模型，由卷积层、池化层以及全连接层组成。

c)LSTM。文献[10]提出的一种双向长短时记忆模型，适合于处理和预测时间序列中间隔和延迟相对较长的文本序列。

d)C-LSTM。Zhou等人[13]将卷积神经网络与长短时记忆模型相结合，由卷积层提出特征后输入给长短时记忆模型，采用了新颖的向量重排模式。

e）MCA-LSTM。本文提出的模型，在C-LSTM的基础上增加了基于注意力机制的疑问词矩阵输入和连接层注意力矩阵，能够自适应的识别句子中最重要的部分。

# 3.3 实验结果与分析

通过与不同模型对比来验证MAC-LSTM模型在短文本分类中的适用性和优越性，本文在不同数据集进行了对比实验。实验结果如表3所示。

Table1Experimental environment and configuration   
表3不同模型准确率对比  
Table 3Comparison of evaluation scores   

<html><body><table><tr><td>模型</td><td>Bidu</td></tr><tr><td>SVM</td><td>76.69%</td></tr><tr><td>CNN</td><td>89.14%</td></tr><tr><td>LSTM</td><td>90.82%</td></tr><tr><td>C-LSTM</td><td>92.65%</td></tr><tr><td>MAC-LSTM</td><td>94.31%</td></tr></table></body></html>

从表3来看，由于不同数据集各大类数据的数量分布不同，各模型精确度有不同程度的波动，但并不影响各模型对比参照。本文画出直方图直观的展示几类模型在不同数据集上的精度对比，MAC-LSTM在三个数据集上都表现出较好的优势。

![](images/99be21d6e7d19cba8b029097584298c5a9f5bf1e1c75832b2127e325cfb58711.jpg)  
图4模型三个数据集上的精度对比Fig.4Comparison of different database

图4展示了本文的模型结果优于高度人工设计特征的传统模型SVM，人工设计特征需要大量的人力劳动，不能很好地推广其他数据集和任务。本文提出的 MAC-LSTM 模型具有自动学习语义句子表示的能力，不需要任何人工抽取特征具有更好的可扩展性；将单个卷积神经网络和长短时记忆模型的结果与相比，卷积神经网络在NLPCC 数据集精确度更高，表明在文本较短且数据量充足的情况下卷积运算更能有效抽取文本特征;将C-LSTM与本文提出的MAC-LSTM与单一的卷积神经网络和长短时记忆模型相比，分类效果更好，说明模型的结合在抽取文本局部特征的同时，可对序列特征进一步深度挖掘，更有利于对问题的理解；对比本文的MAC-LSTM模型与C-LSTM方法可以看出，本文提出的多层级注意力机制能使模型在训练过程高度关注分类的目标的特征信息，从而更好地识别疑问词相关特征，验证了注意力机制在问题分类任务中的有效性。

![](images/e88e701197c96ce1bccefff3c08fb27e04da152ba58864f1780ae4c7aad54d65.jpg)  
图5不同向量维度的表现  
Fig.5Comparison of different embedding dimensions

本文在C-LSTM研究的基础上提出了疑问词注意力机制，通过构建疑问词向量强化模型对问句疑问词特征的抽取效果。疑问词向量的特征表示效果与词向量的维度有很大关系，本文使用不同维度的词向量构造疑问词向量进行实验，验证疑问词注意力机制的有效性和稳定性。实验结果如图5所示。从图中可以看出，当向量维度大小变化时，模型准确率在开始时会增加；当维度大小超过50之后变得稳定。本文最终选择100作为向量维度，在兼顾到计算简单的情况下能得到相对好的实验结果。

# 4 结束语

本文从问题分类的角度出发，分析了传统方法的不足之处以及深度学习在本领域相关的应用，同时结合了注意力机制对深度学习模型进行改进，本文提出了一种多层次注意力深度学习模型。首先应用注意力机制加强了模型对疑问词的特征的关注度；然后将卷积神经网络与长短时记忆模型通过注意力连接模式有效结合，同时发挥两类模型对问题分类的优势。MAC-LSTM模型能够通过卷积运算学习疑问词向量的短语级特征，然后将特征表示输送到长短时记忆模型中以增强捕捉文本时序依赖特征的能力。本文使用 MAC-LSTM 模型对问题类型分类任务进行了评估实验，取得了满意的结果。当前问题分类任务面临着缺少语料的问题，除了继续搜集和标注新的数据这个思路之外，如何利用大量未标记的语料进行半监督学习也是一条可行的方向。此外，问题分类是问答系统的基础研究之一，问题分类结果的好坏会影响问答系统答案抽取与回答生成策略地选择，所以答案抽取与问题分类相结合方面的研究也将是下一步研究的重点。

# 参考文献：

[1]Dang H T,Kelly D,Lin J. Overview of the TREC 2007 question answering track [C]//Proc of the 16th Text Retrieval Conference.2007:115-123.   
[2]Le-Hong P,Phan XH,Nguyen TD.Using dependency analysis to improve question classification [C]//Proc of Knowledge and Systems Engineering. 2015:653-665.   
[3]Hernault H, Prendinger H,Duverle DA,et al.HILDA: a discourse parser using support vector machine classification [J].Dialogue & Discourse,2010, 1(3).   
[4]Li Xin,Roth D.Learning question classifiers[J].Proc.COLING-2002,2002, 12 (24): 556-562.   
[5]Biswas P, Sharan A,Kumar R.Question classification using syntactic and rule based approach [C]//Proc of International Conference on Advances in Computing,Communications and Informatics.2014:1033-1038.   
[6]Li Kuan,Xiong Zhongyang,Zhang Yufang,et al. The spoken//written language classification of english sentences with bilingual information [M]// Natural Language Processing and Chinese Computing. Berlin: Springer, 2013:370-377.   
[7]Hu Yue,Liu Bo,Zhang Shouwei.Chinese question classify model based on interrogative semantic unit [C]// Proc of International Symposium on Computer Architecture.2013,92:14-19.   
[8]Kim Y.Convolutional neural networks for sentence classification [J].arXiv

preprint arXiv:1408.5882,2014.

[9]Li Dong,WeiFuru,Zhou Ming,et al.Question answering over freebase with multi-column convolutional neural networks [C]//Proc of Meeting of the Association for Computational Linguistics and the,International Joint Conference on Natural Language Processing.2015: 260-269.   
[10] Feng Minwei,Xiang Bing,Glass MR,et al.Applying deep learning to answer selection: a study and an open task [J].Astrophysics Data System, 2015:813-820.   
[11]Ruder S,GhaffariP,BreslinJG.Ahierarchical model of reviews for aspectbased sentiment analysis [C]//Proc of Conference on Empirical Methods in Natural Language Processing.2016: 999-1005.   
[12]Wang Ding,Nyberg E.A long short-term memory model for answer sentence selection in question answering [C]// Proc of Meeting of the Association for Computational Linguistics and the,International Joint Conference on Natural Language Processing.2015:707-712.   
[13] Zhou Chunting,Sun Chonglin,Liu Zhiyan,et al.AC-LSTM neural network for text classification [J].arXiv preprint arXiv:1511.O8630,2015.   
[14] Yin Wenpeng，Schütze H,Xiang Bing，et al.Abcnn:attention-based convolutional neural network for modeling sentence pairs [J].arXiv preprint arXiv:1512.05193,2015.   
[15] Mnih V,Heess N,Graves A,et al. Recurrent models of visual attention [J]. Astrophysics Data System,2014,3:2204-2212.   
[16] Bahdanau D,Cho K,Bengio Y. Neural machine translation by jointly learning to align and translate[J].arXiv preprint arXiv:1409.O473,2014.   
[17] Zhou Xinjie,Wan Xiaojun,Xiao Jianguo.Attention-based LSTM network for cross-Lingual sentiment classification [Cl// Proc of Conference on Empirical Methods in Natural Language Processing.2016: 247-256.   
[18] Yang Zichao,Yang Diyi,Dyer C,et al.Hierarchical attention networks for document classification $[ \mathrm { C } ] / \AA$ Proc of Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies.2017:1480-1489.   
[19] Chen Huimin，Sun Maosong，Tu Cunchao,et al.Neural sentiment classification with user and product attention [C]//Proc of Conference on Empirical Methods in Natural Language Processing.2016:1650-1659.   
[20] Nair V,Hinton G E.Rectified linear units improve restricted boltzmann machines [C]// Proc of International Conference on International Conference on Machine Learning.201o: 807-814.   
[21] Hao Tianyong,Xie Wenxiu,Wu Qingyao,et al.Leveraging question target word features through semantic relation expansion for answer type classification [J]. Knowledge-Based Systems,2017.