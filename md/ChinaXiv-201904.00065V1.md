# 基于稠密连接记忆神经网络的文本推理

潘永华，闭应洲，潘怀奇，郑思霞(广西师范学院 计算机与信息工程学院，南宁 530001)

摘要：由于传统的端到端记忆神经网络模型特征表示能力不足，无法很好地表示各个记忆之间的联系，导致其在数据集 bAbI中的位置推理和路径查找问题正确率不高。针对此问题，提出了一种结合稠密连接和多层感知机的记忆神经网络。该模型利用稠密连接与全连接层获取关系特征，增强了模型的特征表示能力。利用bAbI数据集对模型进行推理正确率的评估，实验结果表明，与传统的记忆神经网络以及端到端记忆神经网络相比，该模型能有效提升文本推理的正确率。

关键词：记忆神经网络；稠密连接；文本推理；多层感知机；特征表示中图分类号：TP389.1 doi: 10.19734/j.issn.1001-3695.2018.10.0794

Text reasoning base on densely connective memorynetworks

Pan Yonghua,Bi Yingzhou†,Pan Huaiqi, Zheng Sixia (SchoolofComputer&Information Engineering,Guangxi Teachers Education University,Nanning53ooo1,China)

Abstract:Because the traditional end-to-end memory networks model had insufficient featurerepresentation ability,it couldnot wellrepresentedtherelationshipbetweeneachmemory,whichleds to thelowacuracyoflocationreasoningand path finding in the bAbI dataset.This paper proposedanew memory networks combining densityconnectivity and mult-layer perceptron tosolve this problem.This model used densityconnectivityand fullconnected layertocapture relationship features,which enhanced thecapabilityoffeature representation.The proposed model evaluatedthe accuracyof textreasoning using bAbI dataset.The experimental results show that the model can efectively improve the reasoning accuracy compare with traditional memory network and the existing end-to-end memory network.

Key words: memory networks; density connectivity; text reasoning; multi-layer perceptron; feature representation

# 0 引言

随着如 Siri、Cortana、QQ 小冰等聊天机器人的出现，聊天机器人正越来越广泛地应用于日常生活中。这类聊天机器人不仅需要能够回答用户使用自然语言提出的单个问题，还需要对已有的自然语言文本进行推理，然后回答用户的问题。因此，文本推理受到越来越多的研究人员关注。

深度学习 (deeplearning，DL)[1]已经成为当前机器学习领域中最有潜力的发展方向。使用神经网络模型去解决自然语言处理中的问题逐渐成为主流，并在文本分类[2]、文本蕴涵[3]等方面取得了很多成果。然而传统的神经网络无法很好的解决文本推理问题，这是由于在文本推理时需要记忆文本中的上下文并通过上下文推理得到答案，而传统的神经网络无法很好地解决这类长时记忆问题，所以人们开始通过基于记忆模型的神经网络模型去解决文本推理问题，其中最具代表性的模型之一是记忆神经网络(memorynetworks,MemNN)[4]，并由此衍生出端到端记忆神经网络 (end-to-endmemory networks,MemN2N) [5]。

但是MemN2N也有许多不足，这些不足造成了MemN2N无法很好地解决bAbI数据集[6中的位置推理和路径查找问题。本文认为这是由于MemN2N模型特征表示能力的不足，无法很好地表示各个记忆之间的联系，导致端到端记忆神经网络在文本推理数据集bAbI中记忆间关系极为重要的位置推理和路径查找问题正确率不高。

为解决MemN2N的问题，本文提出了稠密连接记忆神经网络(densely connective memorynetwork,DenMemN2N)。其主要贡献包括：a)使用稠密连接加强各跳间的信息流，使模型能够使用前面几跳的信息；b)使用门控机制过滤稠密连接得到的信息流，只保留有效信息；c使用多层感知机获取关系特征，增强了模型在对象关系上的特征表示能力。

实验结果表明，本文方法相比于MemNNs、MemN2N和GMemN2N的回答问题的正确率有很大提升。

# 1 相关工作

# 1.1 记忆神经网络

Chopra 等人提出了MemNNs，并将其用于文本推理上。MemNNs主要由记忆m、输入组件、泛化组件、输出组件和回复组件组成。MemNNs文本推理的模型结构如图1所示。考虑一个文本问答的场景，提供一段事实（即几个句子)，针对这段事实进行提问。下面将通过这个场景对MemNNs进行讲解。

在MemNNs中输入组件(组件I)负责将输入转换成内部特征表示，将转换过程定义为 $I ( x )$ ，其中 $x$ 表示MemNNs的输入。在文本推理中， $x$ 可以是一段事实，也可以是问题。泛化组件(组件G)主要负责更新记忆 $\scriptstyle { \mathrm { ~ m ~ } } \circ { \mathrm { ~ m ~ } }$ 是由i索引的一个对象数组， $\mathbf { m } _ { i }$ 表示第i个记忆。在文献[6]中直接将 $I ( x )$ 作为

记忆：

$$
\mathbf { m } _ { \mathrm { H } ( x ) } = \mathrm { I } ( x )
$$

其中： $\mathrm { H } ( x )$ 为选择函数，即组件G仅更新索引为 $\mathrm { H } ( x )$ 的记忆，而不修改记忆 $\mathrm { ~ m ~ }$ 的其他部分。在文本推理问题中，式(1)的 $x$ 通常为已有的事实； $\mathrm { H } ( x )$ 通常是文本出现的位置。

输出组件(组件O)负责读取记忆并进行推理，如计算哪些相关记忆能得到好的回复。回复组件(组件R)则将组件O的输出作为输入，最后生成可以阅读答案。在文本问答场景下，组件O发现相关的记忆，然后 $\mathrm { ~ \tt ~ R ~ }$ 生成答案。

$$
o = \mathbf { O } ( I ( x ) , m )
$$

$$
\scriptstyle a = \mathbf { R } ( o )
$$

其中：此时0含有所有与答案有关的记忆的特征内表示； $\mathbf { \Psi } _ { a }$ 表示预测答案。

![](images/8193056171cbc120347a5478185febb15d8558972249922fbed480e2351636b1.jpg)  
图1基于MemNNs 的文本推理模型

MemN2N克服了MemNNs无法进行端到端训练的缺点，在数据中进行端到端的学习，学习的目标函数是可微分的函数。受MemN2N结构的启发，研究者们提出了许多端到端模型。Kumar等人[7针对MemN2N只有静态记忆的缺点，提出了一种使用循环神经网络(recurrent neural network，RNN)动态更新记忆的动态记忆神经网络(dynamicmemorynetworks,DMN)。Xiong 等人[8]则对DMN的门控循环单元网络(gated recurrentunit,GRU)[9]进行了改进，提升了计算效率，并且还将提出的模型拓展到了视觉问答（visionquestionanswering,VQA)。门控端到端记忆神经网络(gatedend-to-endmemorynetworks，GMemN2N)改进了原MemN2N中记忆输入的更新方式，让记忆都要经过门控 $\mathrm { T } ^ { [ 1 0 ] }$ 。因此GMemN2N的门控机制能够动态地决定记忆如何以及何时跳过推理过程对记忆网络层的输入进行筛选。本文提出的DenMemN2N也使用GMemN2N的门控机制筛选记忆。

# 1.2增加有效特征

在关于如何获取更多的有效特征的研究中，Srivastava等人[1]提出了Highway networks，使用门控方式获取有效特征，解决了网络深度加深、梯度信息回流受阻造成网络训练困难的问题。Huang等人[12]提出了通过稠密连接，使用前面所有层的输出作为当前层的输入，以此强化层与层之间的信息流。

# 1.3关系特征获取

对如何获取两个对象间的关系特征方面，Santoro 等人[13]提出了关系网络(relationnetwork，RN)，并将其用于关系推理上。RN仅由两个简单的多层感知机（multi-layer perceptron,MLP）组成，其中一个MLP 结构 $g _ { \theta } ( x )$ 对实体之间的关系进行导出，另一个MLP结构 $f _ { \phi } ( x )$ 使用 $g _ { \theta } ( x )$ 获取的实体关系进行推理。由此可看出MLP能获取对象间的关系特征。

# 2 稠密记忆神经网络

# 2.1问题描述与定义

在文本推理问题中，通常会有一段事实 $\mathrm { \Delta X }$ ，一个基于这段事实的问题 $q$ 以及答案 $\mathbf { \Omega } _ { a }$ 。在本文使用的推理数据中，为了方便评估结果，本文的 $\mathbf { \Omega } _ { a }$ 是一个单词。设 $x _ { i }$ 是一个句子，则事实X由一个序列 $x _ { 1 } , x _ { 2 } , x _ { 3 } , \cdots , x _ { n }$ 共 $n$ 个句子组成。设 $w _ { i }$ 代表句子的第 $i$ 个单词，句子的长度是 $\mathbf { \nabla } _ { m }$ 。设语料中词汇量的大小为 $\boldsymbol { V } _ { \circ }$ 设 $f$ 是一个参数为 $\theta$ 的模型，本文期望在数据集中的$\mathbf { \Omega } _ { a }$ 与预测得到的 $\mathbf { \Phi } _ { a }$ 一致。设数据集中的第 $i$ 个事实 $X _ { i }$ 对应的问题是 $q _ { i }$ ，正确答案是 $a _ { i }$ ，则文本推理可以转换成关于 $f$ 的参数 $\theta$ 的参数优化问题，其形式化表达如下：

$$
\operatorname* { m a x } _ { \theta } ( \sum _ { i } \mathrm { e q u a l } ( f ( X _ { i } , q _ { i } ; \theta ) , a _ { i } ) )
$$

其中：equal函数判断模型 $f$ 预测的答案与正确答案是否一致，若一致返回1，不一致返回0。

# 2.2稠密记忆神经网络

如图2所示，稠密记忆神经网络由输入编码模块I、稠密记忆模块DM和输出模块O三个主要部分组成。本文将在下面给出各个模块的细节。

# 2.2.1输入编码模块

输入编码模块与MemNNs中的组件I功能类似，主要将模型输入的文本转换成内部特征表示。而在具体实现中，本文使用输入编码模块将每一个句子转换成一个向量表示。它将输入序列的句子 $x _ { i }$ 的每个单词转换成一个向量并求和，用求和得到的向量作为当前句子的向量表示。本文提出的模型将输入的句子中的单词使用独热表示(one-hot representation)进行表示，并使用词嵌入矩阵将单词转换成词向量。设句子$x$ 中的 $w _ { i }$ 的独热表示为 $b _ { i }$ ，则输入编码模块的形式化表达可表示为

$$
\begin{array} { c } { { e _ { i } = b _ { i } A } } \\ { { } } \\ { { \nu = \sum _ { i } e _ { i } } } \end{array}
$$

其中：式(5)的 $\mathbf { \mathcal { A } }$ 是一个可训练的矩阵，本文称之为嵌入矩阵(embedding matrix)； $\boldsymbol { e } _ { i }$ 是 $w _ { i }$ 的词向量。式(6)将句子 $x$ 中的每个单词的词向量求和得到了句子 $x$ 的向量表示 $ { \boldsymbol \nu }$ ，即句子 $\textbf { x }$ 的句向量。

![](images/b896736225e8142f25825114fd72b380b68c9701e45a75db355e8bf5fb57d138.jpg)  
Fig.1Text reasoning base on memnns   
图2稠密记忆网络架构  
Fig.2Densely connective memory networks architecture

2.2.2稠密记忆模块

稠密记忆模块将MemNNs结构的组件G和O的功能进行了结合，其主要负责对记忆的加工与推理，是实现DenMemN2N推理能力的关键。其结构如图3所示。

本文更新记忆的方式与MemNNs类似，都是将句子的向量表示作为记忆。其中事实 $X$ 与问题 $q$ 的嵌入矩阵都为 $A$ ，但事实 $X$ 还使用另一个嵌入矩阵 $c$ 获取 $X$ 中句子的向量表示。其中设 $q$ 的向量化表示为 $u _ { 0 }$ 。 $m _ { i }$ 和 $c _ { i }$ 分别表示 $x _ { i }$ 使用嵌入矩阵 A与嵌入矩阵C向量化的结果， $m _ { i }$ 称为输入记忆， $c _ { i }$ 称为输出记忆。设输入记忆 $M _ { i n p u t }$ 为 $\{ M _ { i n p u t } | m _ { 1 } , m _ { 2 } , . . . , m _ { m s } \}$ ，设输出记忆 $M _ { o u t p u t }$ 为 $\{ M _ { o u t p u t } | c _ { 1 } , c _ { 2 } , . . . , c _ { m s } \}$ ， $m s$ 表示记忆量(memory size)的大小。

![](images/558a10642ed2dd28919bb598f49a5e354e14819a38dc3b58cd3d63474d944ec8.jpg)  
图3稠密记忆模块  
Fig.3Densely memory module

在获取记忆后，DenMemN2N通过注意力机制，计算问题与各个记忆的相似度，即求两个向量的内积。其计算过程如下：

$$
p _ { i } = \mathrm { s o f t m a x } ( ( u _ { 0 } ) ^ { T } m _ { i } )
$$

$$
p _ { i } = ( u _ { 0 } ) ^ { T } m _ { i }
$$

式(7)和(8)是获取相似度 $p _ { i }$ 的两种方式。式(7)中的softmax函数为 $\operatorname { s o f t m a x } ( \alpha _ { i } ) = e ^ { \alpha _ { i } } / \sum _ { j } e ^ { \alpha _ { j } }$ 。在训练过程中，如果训练方式为非线性起始(non-linear start,non-ls)，则通过式(7)获取 $p _ { i }$ ；若使用线性起始(linearstart,ls)方式，则在训练过程中前 $\mathbf { \Psi } _ { e }$ 代通过式(8)获取 $p _ { i }$ ,其中 $\mathbf { \Psi } _ { e }$ 是一个超参。然后将 $p _ { i }$ 与 $c _ { i }$ 的每个元素相乘求和得到o。

$$
o = \sum _ { i } p _ { i } c _ { i }
$$

式(9)是实现注意力机制的关键步骤。DenMemN2N使用注意力机制寻找与问题相关度较高的输入记忆 $m _ { i }$ ,越相关 $p _ { i }$ 越高，则 $p _ { i }$ 对应的输出记忆 $c _ { i }$ 的信息就能更多地保留在 $\mid o \mid$ 中，即认为输入的句子与问题相似度越高越有可能与答案相关。

但是若只根据式(9)获取输出，在面对有多个支持事实的问题时，可能无法得到更好的结果。通过表1的例子来说明其问题。如果仅通过计算问题与已有事实相似度，在表1中第1句的相似度是最高的，因为都存在单词“milk”。但是要得出正确答案，无法只根据第1句话来得到答案，还需要知道“Mary”最后去到哪里。因此DenMemN2N还通过多跳机制进行相关项之间的推理。如图3所示，即将第1跳得到的输出作为第2跳的输入。这种多跳机制实现了自然语言的多级计算，也就是需要将上下文关联的信息在计算中联系起来。让下一跳再通过求相似度的方式找到与上一跳有关的记忆，实质上就是一个联想回忆的过程，使其实现递进式的推理。如表1例子中在第1跳的输出中第一句的特征相对较多，以此作为第2跳的输入。在进行相似度计算时，由于第1跳的输出含有“Mary”相关的信息，所以会使同样含有“Mary”的第4句权重最高，并可以根据第4句获得正确答案。但是现实场景中并非所有推理都是递进式推理，还有通过对象间关系的推理。

Table 1Example of text reasoning   

<html><body><table><tr><td>分类</td><td>句子</td><td>与答案是否相关</td></tr><tr><td rowspan="4">已有事实</td><td>1 Mary got the milk there.</td><td>√</td></tr><tr><td>2 John moved to the bedroom.</td><td></td></tr><tr><td>3 Sandra went back to the kitchen.</td><td></td></tr><tr><td>4 Mary travelled to the hallway.</td><td>√</td></tr><tr><td>问题与答案</td><td>5 Where is the milk? hallway 14</td><td></td></tr></table></body></html>

考虑如表2中的位置推理问题。答案需要两个事实，并且需要获得形状之间的关系才能获得正确答案。为解决这一问题，本文使用稠密连接增强各跳间的信息流，然后通过门机制筛选出各跳输入和输出中有意义的特征，使模型能更全面地考虑各跳中找到的相关事实，最后将这些相关事实输入到多层感知机中获取关系特征。就如表2所示，当第1句与第2句对物体间的关系进行描述，本文就需要结合两句话的信息，在DenMemN2N中，本文使用稠密连接结构增强不同跳中找到的信息并使用门控机制加以过滤，使其过滤一些无用的信息(如例子中的颜色信息)。在获得各跳有效信息后，本文还需要通过这些有效信息获取各个物体（例子中的"triangle""rectangle""square"）间的关系特征，最后根据问题与关系特征获取答案。设第 $\mathbf { k }$ 跳的门控为 $G ^ { k }$ ，且 $k \geq 2$ 。则第$k$ 跳的计算流程可表示为

$$
p _ { i } ^ { k } = \mathrm { s o f t m a x } ( ( u _ { i } ^ { k } ) ^ { T } m _ { i } )
$$

$$
O ^ { k } = \sum _ { i } p _ { i } ^ { k } c _ { i }
$$

$$
G ^ { k } \left( [ u ^ { 1 } , u ^ { 2 } , . . . , u ^ { k } ] \right) = \sigma ( W _ { T } ^ { k } [ u ^ { 1 } , u ^ { 2 } , . . . , u ^ { k } ] + b _ { T } ^ { k } )
$$

$$
u _ { t } ^ { k + 1 } = [ \rho ^ { 1 } , \rho ^ { 2 } , . . . , o ^ { k } ] \odot G ^ { k } ( [ u ^ { 1 } , u ^ { 2 } , . . . , u ^ { k } ] ) +
$$

$$
\left[ u ^ { 1 } , u ^ { 2 } , . . . , u ^ { k } \right] \odot \left( 1 - G ^ { k } \left( \left[ u ^ { 1 } , u ^ { 2 } , . . . , u ^ { k } \right] \right) \right)
$$

$$
u ^ { k + 1 } = \mathbf b \mathbf n ^ { k } ( u _ { t } ^ { k + 1 } )
$$

其中：式(10)和(11)表示获得第 $k$ 跳的输出 $o ^ { k }$ 的流程。式(12)中的 $G ^ { k }$ 是一个门函数， $u ^ { 1 } , u ^ { 2 } , . . . , u ^ { k }$ 和 $o ^ { 1 } , o ^ { 2 } , . . . , o ^ { k }$ 分别表示第1跳至第 $\mathbf { k }$ 跳的记忆层的输入和输出， $\odot$ 表示向量元素对应相乘， $\sigma$ 表示 Sigmoid 函数。 $[ u ^ { 1 } , u ^ { 2 } , . . . , u ^ { k } ]$ 则表示第1跳\~第k跳输入的串联， $[ o ^ { 1 } , o ^ { 2 } , . . . , o ^ { k } ]$ 表示第1跳至第 $k$ 跳输出的串联。 $W _ { T } ^ { k }$ 是可以训练的变量，其维度与模型的跳数有关，设句向量的维度是 $l _ { e }$ ，则 $W _ { T } ^ { k } \in R ^ { k l _ { e } \times k l _ { e } }$ 。由于使用了稠密连接，下一跳的输入会得到所有跳的特征，然后所有跳的特征会作为门函数 $G ^ { k }$ 的输入并训练参数 $W _ { T } ^ { k }$ ，其目的是通过该跳前面所有跳的记录去训练 $G ^ { k }$ ，使得 $G ^ { k }$ 能够对 $[ u ^ { 1 } , u ^ { 2 } , \ldots , u ^ { k } ]$ 和 $[ o ^ { 1 } , o ^ { 2 } , . . . , o ^ { k } ]$ 中的信息进行筛选。式(13)使用Highwaynetwork的结构对前 $k$ 跳的输入与输出信息进行过滤，最终输出向量 $u _ { t } ^ { k + 1 }$ 。式(12)与(13)构建了一个使用门 $G ^ { k }$ 的稠密连接，增强了跳与跳之间的信息流使得到的 $\boldsymbol { u } _ { t } ^ { k + 1 }$ 不仅包含当前跳的信息，也包含前面几跳的有效信息。

表1文本推理例子  
表2位置推理例子  
Table 2Example of positional reasoning   

<html><body><table><tr><td></td><td>句子</td><td>与答案是否相关</td></tr><tr><td rowspan="2">事实</td><td>1 The triangle is above the pink rectangle.</td><td>√</td></tr><tr><td>2 The blue square is to the left of the triangle.</td><td>√</td></tr><tr><td>问题与</td><td>3 Is the pink rectangle to the right of the blue</td><td></td></tr><tr><td>答案</td><td>square?yes12</td><td></td></tr></table></body></html>

式(14)的 $\mathbf { b } \mathbf { n } ^ { k }$ 表示第 $k$ 跳的批标准化层(batchnormalization,bn)层[14]。第2跳的bn层没有激活函数，而第3跳的bn层激活函数为Sigmoid函数。最后将bn层的输出作为下一跳的输入。 $\mathbf { b } \mathbf { n } ^ { k }$ 的作用主要是获取 $\boldsymbol { u } _ { t } ^ { k + 1 }$ 中的关系特征，$u _ { t } ^ { k + 1 }$ 中不仅包含当前跳的信息，也包含前几跳的信息，因此$\mathbf { b } \mathbf { n } ^ { k }$ 能够同时获取跳与跳之间的关系特征与当前跳的关系特征，最终获得输出 $u ^ { k + 1 }$ ，并将 $u ^ { k + 1 }$ 作为下一跳的输入。

如图3所示，第1跳的流程中没有设置bn层，这是因为第1跳前没有前置的层，无须使用稠密连接加强各跳之间的信息流，所以也不需要使用bn层获取各跳以及记忆间的关系特征。

稠密记忆模块通过稠密连接增强各跳间记忆的信息流，增加了各跳所找到的关键信息在推理中的作用。并且还使用MLP获取关系特征，因此该模块增强了模型的特征表示能力。2.2.3输出模块

本模型的输出模块功能主要是将稠密记忆模块的输出作为输入然后输出预测答案 $\mathbf { \Psi } _ { a }$ 。输出模块获取答案的公式为

$$
\hat { p } = \operatorname { s o f x m a x } ( W _ { o } o _ { D M } + b _ { o } )
$$

其中： $W _ { o }$ 是可以训练的矩阵； $o _ { D M }$ 则是稠密记忆模块的输出。如果预测答案 $\hat { a }$ 仅为一个单词，则 $\hat { p }$ 表示每个单词作为答案的概率分布。

# 2.3模型训练

假设问题 $q _ { i }$ 的答案为 $\mathbf { \Psi } _ { a }$ ，则输出目标向量的元素值表示为

$$
p _ { i } = { \left\{ \begin{array} { l l } { 1 } & { j = a } \\ { 0 } & { j \neq a } \end{array} \right. }
$$

使用交叉熵作为DenMemN2N的损失函数，如式(17)所示。

$$
L { = } { \mathrm { - } } \sum _ { i = 1 } ^ { N } p _ { i } \log ( p _ { i } )
$$

本文训练的优化方式选用随机梯度下降法。为提升模型的准确率和泛化能力，还进行了如下改进：

a)在输入编码模块使用文献[4]提出的位置编码(positionencoding)和时序编码，并随机选择时序编码中的 $10 \%$ 加入噪声。

b)对梯度进行裁剪，若梯度张量的L2范数大于40，则L2 标准化使用40进行标准化，防止梯度爆炸。

c)在预测模块的全连接层以及关系导出的全连接层后加入了dropout层，防止过拟合。

d)在更新记忆时，本文使用相邻权重捆绑(adjacentweighttyping)，即第1跳输入记忆嵌入矩阵为 $A _ { 0 }$ ，输出记忆嵌入矩阵为 $C _ { 1 }$ ，则第k跳的输入记忆嵌入矩阵为 $A _ { k } = C _ { k - 1 }$ ，输出记忆矩阵为 $C _ { k }$ 。

# 3 实验与分析

# 3.1数据集与数据预处理

本实验使用的数据集为bAbI数据集(使用的bAbI数据集版本为1.2)。表1和2均为bAbI数据集中的某个任务，有一组事实X、问题 $q$ 以及答案 $\mathbf { \Omega } _ { a }$ ，其中事实X为一组句子。X和 $q$ 使用词袋模型表示， $a$ 使用大小为的独热向量表示。并且数据集中还标注了与答案有关的事实。本文提出的DenMemN2N不使用除答案外的任何监督信息。本文中仅使用bAbI的 $1 0 \mathrm { ~ k ~ }$ 数据集进行实验，即每个任务中有10000个问题。

# 3.2超参设置

首先将bAbI数据集中训练集的 $10 \%$ 作为验证集，用于超参的调优。学习率 $\eta$ 初始值为0.01，并且每25代减少一半，即变为 $\eta / 2$ ，直到第100代才停止降低 $\eta$ 的值。训练集分批的大小(batchsize)为32，所有的权重和偏置值使用截断正态分布进行随机初始化。其中，用于权重初始化的正态分布期望为0，标准差为0.1；用于偏置初始化的值正态分布期望值为0.5，标准差为1。模型在训练中只考虑距离问题最近的50个句子，将其作为模型的输入数据，所有模型的跳数均为3。在本文的实验中，本文的词向量维度大小为20。

为了避免单次训练的误差，本文将每个任务执行30次，并选择30次测试中得到的最高正确率作为最终的正确率。由于本文使用的是bAbI数据集的1.2版本，所以本文用新的数据集重新训练了MemN2N。

# 3.3实验结果

模型的训练采用单一训练的方式，即将bAbI数据集中每个任务单独进行训练。bAbI数据集中各个任务的正确率如表3所示。

本文将DenMemN2N的实验结果与文献[4]的MemNNs强监督(strongly supervised，SS)版本以及文献[5]的MemNNs弱监督(weakly supervised heuristic,WSH)版本进行了对比。MemNNs的强监督版本即知道X中哪些事实与问题相关，并将这些信息用于训练之中；MemNNs的弱监督版本则不使用除答案外的任何监督信息进行训练。同时还将实验结果与MemN2N和GMemN2N进行了对比。MemN2N以及GMemN2N训练过程中仅使用答案作为监督信息。

由表3可知，本文提出的DenMemN2N模型在任务17、任务18以及任务19上都取得了比MemN2N以及GMemN2N更好的效果。任务17与任务19的结果比GMemN2N分别提升了 $2 5 . 8 \%$ 与 $2 . 5 \%$ ，比MemN2N分别提升了 $2 5 . 4 \%$ 和 $1 8 . 5 \%$ ，比MemNNs的SS版本分别提升了 $2 2 . 6 \%$ 和 $30 . 9 \%$ 。该实验结果表明，本文方法很好地解决了MemNNs和MemN2N无法解决的任务17和任务19，克服了传统端到端记忆神经网络的缺点。

本实验也同时对比了Non-LS与LS两种获取相似度的方法在MemN2N、GMemN2N和DenMemN2N模型上的差别。通过表3的结果可以看出，这两种方法对pathfinding任务和basic induction任务有着很大的影响。在使用LS时，模型获取了更多的线性特征，因此可以在basicinduction任务中获得更佳的结果。但是在使用LS时，无法获取更多的非线性特征，因此无法在pathfinding上获得更好的结果。而本文提出的DenMemN2N模型在positional reasoning 任务中，使用Non-LS的效果要优于LS。笔者猜测这是因为对象间关系大多是非线性特征，所以使用Non-LS时获取了更多的非线性特征，取得了更好的效果。但无论使用哪种方法，本文提出的模型效果在此任务上都要优于MemN2N和GMemN2N。

但是本文提出的模型也有明显的缺陷，任务16的正确率都远低于GMemN2N以及MemN2N。其原因是LS对任务16的影响极大，但DenMemN2N的BN层的非线性激活函数极大的降低了LS的作用。

# 4 结束语

本文提出了一种使用稠密连接以及门控机制的记忆神经网络一一稠密连接记忆神经网络。实验结果表明，本文提出的基于稠密连接、门控机制以及多层感知机的稠密记忆神经网络模型能够有效地解决传统的端到端记忆神经网络模型的特征表示能力不足的问题，更加充分地获取记忆间的关系特征表示，在文本推理问题上得到了更好的结果。但是新模型仍然存在一些可以改进的地方，如网络结构中超参过多、模型存在过拟合问题以及过参数化问题。因此，在保留现有模型的框架下，构建一个结构更简单、参数更少的模型将会是

今后研究的重点。

表3bAbI10k 数据集训练结果Table3Result of bAbI1Ok dataset  

<html><body><table><tr><td rowspan="2">任务</td><td colspan="2">MemNNs</td><td colspan="2">MemN2N</td><td colspan="2">GMemN2N</td><td colspan="2">DenMemN2N</td></tr><tr><td>SS</td><td>WSH</td><td>Non-LS</td><td>LS</td><td>Non-LS</td><td>LS</td><td>Non-LS</td><td>LS</td></tr><tr><td>1:1 supporting fact</td><td>100.0</td><td>99.9</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td></tr><tr><td>2:2 supporting fact</td><td>100.0</td><td>60.4</td><td>99.7</td><td>99.7</td><td>100.0</td><td>99.9</td><td>99.2</td><td>100.0</td></tr><tr><td>3:3 supporting fact</td><td>100.0</td><td>20.5</td><td>90.7</td><td>92.7</td><td>95.5</td><td>95.0</td><td>95.1</td><td>93.7</td></tr><tr><td>4:2 argument relation</td><td>100.0</td><td>63.4</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td></tr><tr><td>5:3 argument relation</td><td>99.8</td><td>78.9</td><td>99.4</td><td>99.4</td><td>99.8</td><td>100.0</td><td>99.9</td><td>99.7</td></tr><tr><td>6:yes/no questions</td><td>100.0</td><td>50.1</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td></tr><tr><td>7:counting</td><td>96.9</td><td>64.9</td><td>96.3</td><td>97.1</td><td>97.3</td><td>98.2</td><td>97.4</td><td>97.7</td></tr><tr><td>8:lists/sets</td><td>99.0</td><td>57.3</td><td>99.1</td><td>99.2</td><td>98.6</td><td>99.7</td><td>99.1</td><td>99.0</td></tr><tr><td>9:simple negation</td><td>100.0</td><td>63.6</td><td>99.0</td><td>99.2</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td></tr><tr><td>10:indefinite knowledge</td><td>100.0</td><td>24.0</td><td>96.9</td><td>97.6</td><td>100.0</td><td>99.8</td><td>100.0</td><td>100.0</td></tr><tr><td>11:basic coreference</td><td>100.0</td><td>74.7</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>89.2</td><td>100.0</td></tr><tr><td>12:conjunction</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td></tr><tr><td>13:compound coreference</td><td>100.0</td><td>87.7</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td></tr><tr><td>14:time reasoning</td><td>100.0</td><td>91.3</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>99.9</td><td>100.0</td></tr><tr><td>15:basic deduction</td><td>100.0</td><td>31.2</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td></tr><tr><td>16:basic induction</td><td>100.0</td><td>49.1</td><td>58.6</td><td>100.0</td><td>61.9</td><td>100.0</td><td>46.8</td><td>49.9</td></tr><tr><td>17:positional reasoning</td><td>75.4</td><td>48.9</td><td>72.6</td><td>56.3</td><td>70.6</td><td>72.2</td><td>98.0</td><td>86.6</td></tr><tr><td>18:size reasoning</td><td>97.9</td><td>54.2</td><td>95.3</td><td>93.3</td><td>97.6</td><td>91.5</td><td>99.1</td><td>98.6</td></tr><tr><td>19:path finding</td><td>68.1</td><td>0.0</td><td>80.5</td><td>33.5</td><td>95.8</td><td>69.0</td><td>99.0</td><td>68.5</td></tr><tr><td>20:agent's motivation</td><td>100.0</td><td>95.6</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td><td>100.0</td></tr></table></body></html>

# 参考文献：

[1]Lecun Y,Bengio Y,Hinton G.Deep learning [J].Nature,2O15,521 (7553): 436-444.   
[2]余本功，张连彬．基于CP-CNN的中文短文本分类研究[J].计算机 应用研究，2018,35(4):1001-1004.(Yu Bengong，Zhang Lianbin. Chinese short text classification based on CP-CNN [J].Application Research of Computes,2018,36(5):1001-1004.)   
[3]谭咏梅，刘姝雯，吕学强．基于CNN与双向LSTM的中文文本蕴涵 识别方法 [J]．中文信息学报,2018,32(7):11-19.(Tan Yonmei,Liu Shuwen，Lyu Xueqiang.CNN and BiLSTM based Chinese textual entailment recognition [J].Journal of Chinses Information Processin, 2018,32 (7):11-19.)   
[4]Weston J,Chopra S,Bordes A.Memory networks [C]// Proc of the 2nd International Conference on Learning Representations.2014.   
[5]Sukhbaatar S,Weston J, Fergus R. End-to-end memory networks [C]/ Proc of the 29th Conference on Neural Information Processing Systems. Montreal:Curran Associates Inc,2015:2440-2448.   
[6]Weston J,Bordes A,Chopra S,et al.Towards ai-complete question answering:a set of prerequisite toy tasks [C]// Proc of the 4th International Conference on Learning Representations.2016.   
[7]Kumar A,Irsoy O,Ondruska P,et al.Ask me anything:dynamic memory networks for natural language processing[C]// Proc of the 33rd International Conference on Machine Learning.New York:PMLR, 2016:1378-1387.   
[8]Xiong Caiming,Merity S,Socher R.Dynamic memory networks for visual and textual question answering [C]// Proc of the 33rd International Conference on Machine Learning.New York:PMLR, 2016:2397-2406.   
[9]Cho K,MerrienboerB,Gulcehre C,et al.Learning phrase representations using RNN encoder-decoder for Statistical machine translation [C]// Proc of Conference on Empirical Methods in Natural Language Processing.Doha: Association for Computational Linguistics, 2014:1724-1734.   
[10]Liu Fei, Perez J.Gated end-to-end memory networks [C]// Proc of the 15th Conference on European Chapter of the Association for Computational Linguistics:volume 1，Long Papers. Valencia: Association for Computational Linguistics,2017:1-10.   
[11] SrivastavaRK,GreffK,Schmidhuber J.Training very deep networks [C]//Proc of the 29th Neural Information Processing Systems.Montreal: Curran Associates Inc,2015:2377-2385.   
[12] Huang Gao,Liu Zhuang,Van Der Maaten L,et al.Densely connected convolutional networks [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition．Honolulu: IEEE Press，2017: 2261-2269.   
[13] Santoro A,Raposo D,Barrett D G,et al.A simple neural network module for relational reasoning [C]// Proc of the 3lst Conference on Neural Information Processing Systems.Long Beach: Curran Associates Inc,2017: 4967-4976.   
[14]Ioffe S,Szegedy C.Batch normalization:accelerating deep network training by reducing internal covariate shift [Cl// Proc of the 32nd International Conference on Machine Learning.Lille:PMLR,2015: 448-456.