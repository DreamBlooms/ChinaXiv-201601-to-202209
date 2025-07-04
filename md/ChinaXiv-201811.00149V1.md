# 基于叠层循环神经网络的语义关系分类模型

郝志峰1,²，陈培辉1，蔡瑞初」，温雯'，王丽娟1(1．广东工业大学 计算机学院，广州 510006;2．佛山科学技术学院 数学与大数据学院，广东 佛山 528000)

摘要：基于循环神经网络结合句法结构的方法被广泛运用于关系分类，利用神经网络对输入的编码信息自动获取特征并实现关系分类；然而，目前已有的方法主要是基于单一特定句法结构的模型，而特定句法结构的模型不能够迁移到其他句法结构类型上。针对该问题，提出一种融合多句法结构的叠层循环神经网络模型。该叠层循环神经网络分为两层进行网络构建，首先在序列层进行实体预训练，通过Bi-LSTM-CRF融合Atention 机制，提高模型对文本序列上实体信息的关注度，从而获取更加准确的实体特征信息，促进关系层阶段更好地分类；其次在关系层，将Bi-Tree-LSTM嵌套在序列层之上，并将序列层的隐状态与实体特征信息传入关系层，利用共享参数对三种不同的句法结构进行加权学习，通过端到端的模型训练并实现语义关系分类。实验结果表明，该模型在SemEval-2010 Task8语料库上的 marco-F1值达到了 $8 5 . 9 \%$ ，并进一步地提升了模型的鲁棒性。

关键词：叠层循环神经网络；多句法结构；Bi-Tree-LSTM；注意力机制；关系分类中图分类号：TP183 doi:10.19734/j.issn.1001-3695.2018.06.0461

# Sematic relation classification model via hierarchical recurrent neural network

Hao Zhifeng1,², Chen Peihui1, Cai Ruichul,Wen Wen1,Wang Lijuan1 (1.FacultyofComputer,Guandong,UniversityofTechnology,Guangzhou51o6,China;2.ScholofMathematics&Big Data,Foshan University,Foshan Guangdong 5280o0,China)

Abstract:The method based on recurent neural network combined with syntactic structure is widely used in relation clasification,andtheneuralnetworkisused toautomaticallacquirefeaturesandralizerelationclasification.Howeve,the existing methods aremainly basedonasingle specific syntactic structure model,and the modelofaspecific syntactic structure canotbetransfered toother typesofsyntacticstructures.Aimingat this problem,aherarchicalrecurrentneuralnetworkmodel with multi-syntacticstructure is proposed.The hierarchicalrecurrent neural network is divided intotwo layers for network construction.Firstlyentity pre-training isperformed inthesequence layer.TheBi-LSTM-CRFfusionAtention mechanismis usedtoimprove the model'satentiontotheentity informationonthe textsequence,therebyobtaining more acurate.The more accurateentityfeature informationpromotes betterclassification intherelationlayer stage.Secondly,intherelationlayer,the Bi-Tree-LSTMis nested above the sequence layer,andthe hidenstate and entity feature informationof thesequence layer is passed into therelationlayer,thenthre diferentsyntaxstructuresareweighted learedusing theshared parametersandclasify the semantic relation finally. The experimental results show that the model has a marco-Fl value of $8 5 . 9 \%$ on the SemEval-2010 Task8 corpus,and further improves the robustness of the model.

Key Words: H-RNN; multi-syntactic structure; Bi-Tree-LSTM; attention; relation classification

# 0 引言

为了应对互联网产生的海量的非结构化文本数据，通常将其转换为结构化的数据，从而帮助人们更快速地获取其中重要的信息。关系分类1作为其中使用最广泛的技术之一，越来越多的受到了研究界的关注。而关系分类主要涉及到文本序列和句法依赖两类重要的信息，如何引入结构化知识，将两者进行更好的融合，去提高分类效果，是本文的研究重点。

近年来，随着深度学习的高速发展，关系分类的做法正在由传统的基于构造特征工程[2-4]和构造核函数[5-7]的方法，逐渐过渡到直接使用深层神经网络对输入的编码信息进行学习并实现分类。其中，代表性的工作包括基于循环神经网络(recurrent/recursiveneuralnetwork）和 卷 积 神 经 网络(convolutionalneural network)的方法，而基于RNN的模型在结构上更适应文本问题，它能够直接地表示语言结构，如文本序列和句法依赖树结构。

在关系分类过程中，主要包括两阶段的任务，分别是命名实体识别和语义关系分类，对应的主流方法分别是基于序列标注[8-10]的方法和基于句法结构[11-13]的方法。在进行第二阶段的任务时，目前主要基于单一特定的句法结构，这类模型存在一定的局限性，只能够处理特定的句法结构，不能够很好地迁移到其他句法结构上。比如，对于序列“Athiefwho triedto stealthe truckbroke the ignitionwith screwdriver."，其最短路径结构(SDP)包含了实体对“thief”“ignition”以及实体对之间的谓语成分“broke"；对于同样的序列，其子树结构(SubTree)不仅包含了SDP，同时包含了其他成分信息如定语“A”，修饰成分“withscrewdriver”等。因此，SDP的网络模型对于SubTree 结构会存在信息丢失的问题，模型上不能够直接进行迁移。

因此，本文提出一种融合多句法结构的叠层循环神经网络模型。a)在序列层进行实体预训练，利用Bi-LSTM-CRF融合attention机制提高模型对实体信息的关注度，更加准确地获取实体标签信息；b)在关系层，利用Bi-Tree-LSTM接收序列层输出和依赖标签的融合特征作为新的输入，对三种不同的句法结构进行加权学习，利用后向传播对共享参数进行更新，最终通过softmax分类器输出语义关系类别。考虑到两阶段任务之间的交互是密切的，通过构造端到端的模型，能够互相促进和提升完整模型的效果。

本文研究的意义在于，提出了一种融合多句法结构的网络模型，并且对两个任务构造叠层的端到端网络，能够更好的适应不同的句法结构，提高了关系分类的精度和稳定性。针对不同层次的网络，其贡献在于：a）在序列层的实体预训练阶段，考虑了输入与输出间的相关性，结合word-levelattention机制能够有效提升模型对文本序列上实体信息的关注度，这对于关系分类起到了促进作用；b）在关系层时，将多种句法结构进行融合，使得模型能够在同一个框架中处理不同的句法结构进行有效的分类，提升了模型的鲁棒性；同时，验证了不同的句法结构对于关系分类的贡献度。

# 1 研究现状

关系分类本质上是一个分类问题，通常的做法是先识别出一个句子中存在的实体对，然后利用分类器决定哪些成分是真正需要的关系。早期的关系分类问题通过借助知识库[14来解决，由于构建知识库的代价成本过大，因此将研究方向转向了机器学习。当前的研究可以分为如下三类：

a)基于特征的方法。通过抽取大量语言学特征，包括语义和语法，将其进行组合形成特征向量集，利用分类器（如最大熵模型和SVM）进行分类[2-4]。该方法在处理特定领域时效果较好，但在特征集的选择和设计上依赖于专家知识，需要花费的时间成本较大。

b)基于核的方法。该方法通过计算两个对象在高维稀疏空间上的内积以获取结构化特征。Zelenko等人[5]通过设计树核函数进行浅层的句法分析以获取结构共性；Culotta等人[6扩展了Zelenko的工作，将树核函数扩展到了依存关系树上，并结合了语法分析信息;Bunescu等人[7将句法最短路径与核函数进行融合，探索在不同句法结构上的分类效果；Zhang等人[15利用卷积树核探索句法特征在关系分类上的作用；Zhou等人[1在文献[15]的基础上添加了文本内容信息。该类方法在核函数的选择上需要技巧性，大数据量时训练速度慢；同时分类性能依赖于NLP工具，而文本预处理的错误结果会影响分类器性能。

c)基于神经网络的方法。该方法的优势在于对输入的编码信息进行自我学习，无须手动构建特征，同时丰富的编码信息克服了传统方法的稀疏问题。在RNN结合句法结构的方法上，Socher等人[17基于递归矩阵-矢量的方式获取语句在组成角度上的语义；Xu等人[1,18]和Liu等人[19]证明了句法最短路径对于神经网络模型获取语义关系是有帮助的；Li等人[20]讨论了不同的句法树结构在神经网络模型中的分类效果；Miwa 等人[21]提出了Bi-Tree-LSTM，并同时考虑了不同句法结构类型及其孩子节点的数量关系；Zhou等人[12]直接在Bi-LSTM上嵌套了一层attention，增强了编码后的权重信息；Xiao 等人[22]将长句子进行切割，并用两层的RNN网络结合attention对不同层的信息进行编码；Zhang 等人[23]提出RNN结合CNN的改进方法，将CNN接在双向LSTM上，对经过attention 的权重卷积后进行全连接输入分类器。而随着增强学习和对抗网络的提出，也有一些相关的研究成果，Feng等人[24]提出了一种利用增强学习处理噪声数据的关系分类方法，Liu 等人[25]提出了一种关系分类的对抗训练框架。

相比较其他两类传统方法，基于神经网络的方法优势在于网络能自主学习获取特征，无须人工定义特征，且分类效果目前达到最优。相对于CNN，基于RNN网络的模型，能够更好的处理文本序列和句法结构。但当前结合句法结构进行关系分类的模型，存在句法结构单一的问题，无法将特定句法结构的模型迁移到其他不同的句法结构上。因此，本文提出了一种融合多句法结构的叠层循环神经网络模型，分别利用Bi-LSTM-CRF(融合Attention机制)和Bi-Tree-LSTM对文本序列和多种不同的句法结构进行学习，通过共享参数进行端到端的训练，最终输出语义关系类别。

# 2 基于H-RNN的关系分类框架

本文的关系分类框架主要包括四部分，分别是输入序列、实体预训练、多句法融合的结构和输出语义关系。框架主体部分在于序列层和关系层上，基于双向循环神经网络来表示文本序列与句法结构，并将关系层嵌套于序列层之上，构成端到端的模型，模型框架如图1所示。更具体的是，在序列层，输入的文本序列经过Bi-LSTM 进行编码，通过word-level的Attention获取每个字在句子中的权重，最后利用CRF对其进行双向解码；在关系层，将依赖标签与序列层的输出进行拼接，作为此阶段的输入，经过Bi-Tree-LSTM对多种句法结构进行加权学习，获取实体对的候选关系，最后通过softmax分类器获取最终的语义关系。

![](images/8739319377efc0036de201441c5ec538aff8452d767705b3977987658efabf36.jpg)  
图1基于H-RNN 的关系分类框架

# 2.1框架的基本阐述

本文提出的模型框架主要由三部分构成，分别是输入序列的词向量表示、序列层的实体预训练、关系层的多句法融合结构。

词向量包含维度为 $\boldsymbol { d } _ { \scriptscriptstyle w }$ 、 $\boldsymbol { d } _ { p }$ 、 $\boldsymbol { d } _ { d }$ 的字 $\boldsymbol { v } _ { \scriptscriptstyle w }$ 、词性标签 $\boldsymbol { v } _ { { p } }$ 、句法标签 $\boldsymbol { v } _ { d }$ ，均为经过预训练的embedding。

在序列层部分，本文采用标准的Bi-LSTM对序列进行编码[26]。在 $t$ 时刻，LSTM包含了一个输入门 $i _ { \iota }$ 、一个忘记门 $f _ { t }$ 、一个输出门 $o _ { t }$ 、一个记忆单元 $\boldsymbol { c } _ { t }$ 以及一个隐状态 $h _ { t - 1 }$ ，其计算公式如下：

$$
\begin{array} { r l } & { \boldsymbol { i } _ { t } = \sigma ( \boldsymbol { W } ^ { ( i ) } \boldsymbol { x } _ { t } + \boldsymbol { U } ^ { ( i ) } \boldsymbol { h } _ { t - 1 } + \boldsymbol { b } ^ { ( i ) } ) } \\ & { \boldsymbol { f } _ { t } = ( \boldsymbol { W } ^ { ( f ) } \boldsymbol { x } _ { t } + \boldsymbol { U } ^ { ( f ) } \boldsymbol { h } _ { t - 1 } + \boldsymbol { b } ^ { ( f ) } ) } \\ & { \boldsymbol { o } _ { t } = \sigma ( \boldsymbol { W } ^ { ( o ) } \boldsymbol { x } _ { t } + \boldsymbol { U } ^ { ( o ) } \boldsymbol { h } _ { t - 1 } + \boldsymbol { b } ^ { ( o ) } ) } \\ & { \boldsymbol { u } _ { t } = \operatorname { t a n h } ( \boldsymbol { W } ^ { ( u ) } \boldsymbol { x } _ { t } + \boldsymbol { U } ^ { ( u ) } \boldsymbol { h } _ { t - 1 } + \boldsymbol { b } ^ { ( u ) } ) } \\ & { \boldsymbol { c } _ { t } = \boldsymbol { i } _ { t } \odot \boldsymbol { u } _ { t } + \boldsymbol { f } _ { t } \odot \boldsymbol { c } _ { t - 1 } } \\ & { \boldsymbol { h } _ { t } = \boldsymbol { o } _ { t } \odot \operatorname { t a n h } \big ( \boldsymbol { c } _ { t } \big ) } \end{array}
$$

其中: $\sigma$ 是逐元素的sigmoid函数， $\odot$ 是逐元素的积， $\boldsymbol { \mathcal { W } }$ 和 $\boldsymbol { \upsilon }$ 是权重矩阵， $b$ 是偏置向量。

对于一个包含 $\mathfrak { n }$ 个字的序列 $\left( x _ { 1 } , x _ { 2 } , \cdots , x _ { n } \right)$ ，每个字都用d维的特征向量来表示。在t时刻，对于当前的第 $\mathrm { ~  ~ t ~ }$ 个字，LSTM接收当前的输入向量为 $\boldsymbol { x } _ { t } = \left[ \boldsymbol { v } _ { w } , \boldsymbol { v } _ { p } \right]$ ，前一刻的隐状态 $h _ { t - 1 }$ 和细胞状态 $c _ { t - 1 }$ ，并返回当前的隐状态 $h _ { \iota }$ 。由于在这里使用的是Bi-LSTM,因此对于每个字在前向和后向均获得了一个隐状态，分别是 $\overrightarrow { h _ { t } }$ 和 $\overleftarrow { h _ { t } }$ ，经过拼接得到 $s _ { t } = \left[ \overline { { h _ { t } } } , \overline { { h _ { t } } } \right]$ ，作为传入关系层的输入之一。

在序列层的解码阶段，采用标准的CRF模型对来自Attention 的输出向量进行解码，标记模式为BILOU[27]，其中每个实体标签包含了实体类型和实体位置信息。如图2所示，B-PER和L-PER表示 SidneyYates是一个PER实体类型以及相应的位置。最终得到的实体标签向量 $\boldsymbol { v } _ { e }$ 将作为关系层的输入之一。

关于模型在序列层的Attention部分以及关系层将会在下文分开具体阐述。

![](images/88cd3b4f155d5d58d3b18b006e26485523dba4ed180812da3ce8da3bd07d2e48.jpg)  
Fig.1H-RNN based relation classification framework   
图2基于叠层循环神经网络的关系分类模型(当模型选择 SDP结构时)

Fig.2Semantic relation classfication model via hierarchical recurrent neural network(when model choose SDP)

# 2.2Word-level Attention

序列层不仅蕴涵了句子上的实体信息，同时包含了实体的上下文信息以及部分非相关信息。为了使模型能够更好的预测实体间的关系，需要让模型在这一层上更多的聚焦于序列上最关键的信息，也就是实体与谓语动作这两类主体信息。

因此，模型在序列层部分引入了一种字级别(word-level)的attention机制。Attention机制使得模型能够沿着文本序列逐字地处理Bi-LSTM所产生的隐藏向量 $s _ { \scriptscriptstyle t }$ ，从而获取到相应的权重分配，产生它们的加权表示 $\boldsymbol { r }$ ，如式(2)所示。

$$
\begin{array} { l } { { \displaystyle z _ { t } = \mathrm { t a n h } ( W ^ { ( w ) } h _ { t } ) } } \\ { { \displaystyle \alpha _ { t } = \frac { \exp \left( V _ { z } ^ { \top } z _ { t } \right) } { \sum _ { j = 1 } ^ { T } \exp \left( V _ { z } ^ { \top } z _ { j } \right) } } } \\ { { \displaystyle r = \sum _ { t = 1 } ^ { T } a _ { t } h _ { t } } } \end{array}
$$

其中： $\boldsymbol { W } ^ { ( w ) }$ 是权重矩阵， $\boldsymbol { v } _ { z }$ 是权重向量， $\boldsymbol { v } _ { z } ^ { \mathrm { T } }$ 是该权重向量的转

置。

# 2.3 关系层

关系层表示句法依赖树上一对实体对之间的候选关系，如图1的右部分所示。已有的实践证明，不同的句法结构对于关系分类有不同程度的效益，但目前的模型基本都是基于特定句法结构下的研究。因此，本文提出将三种不同的句法结构进行加权融为一体，让网络学习在不同的句法结构下对关系进行分类。

首先，明确 SDP、SubTree、FullTree 结构的定义：

a)SDP,最短路径是指最近公共节点和两个实体目标词之间的核心依赖路径；

b)SubTree,子树是包含了最短路径以及最近公共节点下的子树的句法结构;

c)FullTree,全树指完整的句法依赖树，能够捕获到完整句子的上下文信息。

本文采用Bi-Tree-LSTM获取实体对之间的候选关系，该网络结构不仅能够充分学习底部叶子节点及其孩子节点的信息，同时还能够将顶部的根节点信息传递到底部叶子节点，这对于网络充分学习句法结构上的信息是有益的。Miwa等[21]的模型通过将句法结构定义为两种类型，并通过一个映射函数来处理两种类型的句法结构树。基于此，本文提出一种改进的Bi-Tree-LSTM，通过共享权重融合三种句法结构信息，并能够计算不同结构下节点的孩子节点数量。

$$
\begin{array} { r l } & { \dot { t } _ { i } = \sigma \left( \mathcal { H } ^ { ( i ) } x _ { i } + \underset { n \neq ( i ) , n } { \sum \sum } p , U _ { i } ^ { ( i ) } h _ { n } + b ^ { ( i ) } \right) } \\ & { f _ { i } = \sigma \left( \mathcal { H } ^ { ( i ^ { * } ) } x _ { i } + \underset { n \neq ( i ) , n } { \sum \sum } p , U _ { i } ^ { ( i ^ { * } ) } h _ { n } + b ^ { ( i ^ { * } ) } \right) } \\ & { o _ { r } \sigma = \sigma \left( \mathcal { H } ^ { ( i ^ { * } ) } x _ { i } + \underset { n \neq ( i ) , n } { \sum \sum } p , U _ { i } ^ { ( i ^ { * } ) } h _ { n } + b ^ { ( i ^ { * } ) } \right) } \\ & { u _ { i } = \operatorname* { t a n h } \left( \mathcal { H } ^ { ( i ^ { * } ) } x _ { i } + \underset { n \neq ( i ) , n } { \sum \sum } p , U _ { i } ^ { ( i ^ { * } ) } h _ { n } + b ^ { ( i ^ { * } ) } \right) } \\ & { c _ { i } = i , \ Q u _ { i } + f \odot c _ { i - i } } \\ & { \dot { t } _ { i } = \sigma , \ Q \operatorname* { t a n h } \left( c _ { i } \right) } \end{array}
$$

其中： $\sum _ { n \in C ( t ) } \sum _ { s \in T } p _ { s } U _ { s } ^ { ( o ) } h _ { m }$ 表示对句法结构进行线性加权的学习，当模型学习到不同的句法结构时，需要计算该字 $x _ { t }$ 在相应的句法结构下的孩子节点数量， $s \in T$ 表示结构 $s$ 为所有树结构 $T$ 下的一种。本文定义两种节点类型，一种是SDP路径上的节点，另一种是SubTree和FullTree上除了最短路径之外的其他所有节点。

由于实体识别与语义关系分类是联合任务，通过将关系层嵌套在序列层之上，将文本序列获取的有效信息传递到关系层上，进行端到端的训练，能够有效的提升完整模型的训练效果。关系层上的LSTM单元在第t个字接收的输入为 $\mathscr { x } _ { t } = \left[ S _ { t } , V _ { t } ^ { ( e ) } , V _ { t } ^ { ( d ) } \right]$ (即图2右部分中的Co-Embedding)，分别为该字在序列层的隐状态向量 $\pmb { s } _ { t }$ 、实体预训练获得的实体标签 $\boldsymbol { \nu } _ { t } ^ { ( e ) }$ 、该字的依赖标签$\boldsymbol { V } _ { t } ^ { ( d ) }$ 。

在完整模型的解码阶段，基于组合的思想对每个检测到的实体的最后一个字进行组合以获取最终的候选关系，即在BILOU 模式下标记为L和U标签的字。在图1示例中，对Yates(L-PER)和Chicago(U-LOC)标记一个候选关系。对于每一个输入的句子，关系层经过Bi-Tree-LSTM获取候选关系 $\boldsymbol { d } _ { p }$ ，经过包含tanh函数的隐含层，最终通过softmax层预测关系标签。

关系层使用的是Bi-Tree-LSTM，因此候选关系$d _ { p } = \left[ h _ { r o o t } ^ { \uparrow } , h _ { e 1 } ^ { \downarrow } , h _ { e 2 } ^ { \downarrow } \right]$ ，其中，“ $h _ { r o o t } ^ { \uparrow }$ ”代表自底向上方向的顶部单元的隐含层状态向量（即，谓语成分)，“ $h _ { e 1 } ^ { \downarrow }$ ， $h _ { e 2 } ^ { \downarrow }$ ”代表自顶向下方向在两个底部叶子节点的隐含层状态向量（即，实体节点)。在最终的关系预测阶段，模型通过两层的神经网络预测最终的候选关系，分别是一个隐含层 $h _ { p } ^ { ( d ) }$ 和 softmax 层，公式如下：

$$
\begin{array} { r l } & { { \boldsymbol { h } } _ { { \boldsymbol { p } } } ^ { ( d ) } = \operatorname { t a n h } \left( { \boldsymbol { W } } ^ { ( d _ { h } ) } { \boldsymbol { d } } _ { \boldsymbol { p } } + { \boldsymbol { b } } ^ { ( d _ { h } ) } \right) } \\ & { \boldsymbol { P } = \operatorname { s o f t m a x } \left( { \boldsymbol { W } } ^ { ( d _ { y } ) } { \boldsymbol { d } } _ { \boldsymbol { p } } + { \boldsymbol { b } } ^ { ( d _ { y } ) } \right) } \end{array}
$$

# 2.4模型训练

对于模型的训练过程和参数设置问题。在序列层上，采用标准的线性链CRF，基于BILOU模式对训练集进行实体预训练，将得到的标签作为关系层的输入之一。在关系层上，本文将softmax作为分类器，置于关系层的隐含层之上，接收来自隐含层的句子表示 $h _ { p } ^ { ( d ) }$ 并产生该句子的语义关系概率分布 $P$ (如式(4)所示)，其训练目标是最小化介于句子的预测关系与实际语义关系之间的交叉熵，即：

$$
l o s s = - \sum _ { k = 1 } ^ { n } \sum _ { i = 1 } ^ { C } y _ { k i } l o g \left( \dot { y _ { k i } } \right) + \frac { \lambda } { 2 } \big \| \theta \big \| ^ { 2 }
$$

其中: $y _ { k i }$ 表示句子 $k$ 属于类别 $i$ 的概率， $y _ { k i } ^ { ' }$ 表示句子 $k$ 预测为类别 $i$ 的概率， $\lambda$ 是L2正则化项， $\theta$ 是它的参数，本文只对权重$W$ 和 $U$ 进行正则化。

同时为了防止过拟合，设置了训练提前结束，具体是设定一个数值 $\scriptstyle 1 = 1 0 0$ ，交叉熵在 $\mathfrak { n }$ 次迭代没有达到之前的最好值就可以提前结束训练。为了保证网络训练过程的一致性，对长度不等的句子进行填充。模型训练过程详细的参数设置在3.2节中阐述。

# 3 实验结果与讨论

实验旨在证明：a)融合Word-level的Attention机制能够有效提升模型对于文本序列上实体信息的关注度，对完整模型的分类效果起到促进作用；b)多种句法结构的加权学习能提升模型的鲁棒性，保证模型能够处理不同的句法结构。下面，首先介绍实验数据与评价指标，实验设置，然后分别测试实验和结果分析，最后与其他方法进行对比。

# 3.1实验数据与评价指标

实验采用Semeval-2010Task8[1]作为实验数据集，该数据集是评判关系分类任务的经典数据集，共包含8000条训练样

本和2717条测试样本，关系类别包括9种语义关系以及Other关系（即实体对之间不存在关系)，具体语义关系-样本分布如表1所示。

Table 1Semantic relation-sample distribution of SemEval 2O1o Task8   

<html><body><table><tr><td>关系类型</td><td>训练集</td><td>测试集</td></tr><tr><td>Other</td><td>1410</td><td>454</td></tr><tr><td>Cause-Effect</td><td>1003</td><td>328</td></tr><tr><td>Component-Whole</td><td>941</td><td>312</td></tr><tr><td>Entity-Destination</td><td>845</td><td>292</td></tr><tr><td>Entity-Origin</td><td>716</td><td>258</td></tr><tr><td>Product-Producer</td><td>71</td><td>231</td></tr><tr><td>Member-Collection</td><td>690</td><td>233</td></tr><tr><td>Message-Topic</td><td>634</td><td>261</td></tr><tr><td>Content-Container</td><td>540</td><td>192</td></tr><tr><td>Instrument-Agency</td><td>504</td><td>156</td></tr><tr><td>合计</td><td>8000</td><td>2717</td></tr></table></body></html>

实验采用marco-F1作为评价指标，该计算依赖于正确率(precision)和召回率(recall)，计算公式如下：

$$
P r e c i s i o n = \frac { T r u e \ P o s i t i \nu e + T r u e \ N e g a t i \nu e } { P o s i t i \nu e + N e g a t i \nu e }
$$

$$
F 1 = \frac { 2 ^ { * } p r e c i s i o n ^ { * } r e c a l l } { p r e c i s i o n + r e c a l l }
$$

其中：TruePositive $^ +$ TrueNegative表示输出的判断正确的关系个数;Positive $^ +$ Negative表示输出的所有的关系个数;TruePositive表示在输出判断正确的关系中，属于Positive类别中的关系个数，Positive表示所有关系中正确类别的关系个数。

# 3.2实验设置

词向量采用由Glove2vec对英文维基百科预训练的词向量进行初始化，维度为20o；采用StanfordDependencyParser对句子进行句法依赖解析。模型的激活函数选用tanh 函数，隐含层节点数为200，采用softmax作为本文的分类器，对权重W和$U$ 采取L2正则化。为防止过拟合，在训练过程中分别对序列层和关系层引入dropout策略，dropout 值取0.3。另外，采用批量的Adam和梯度剪裁用于模型训练更新权重参数，批量大小取1，训练轮数取100。对于其他参数，均采用随机初始化处理。

# 3.3 实验结果与分析

本文实验以文献[21]中的结果为基准，该方法在未添加额外的先验知识WordNet时，能够达到的分类效果为 $84 . 4 \%$ 。

# 3.3.1序列层的改进

本文在第一组实验中，基于文献[21的方法，通过改进该模型的序列层，分别是使用了不同的解码方式以及添加word-level的Attention机制，得到实验结果如表2所示。

由实验结果可知，将解码方式改进为CRF并添加Attention机制，提高了基准模型最终的分类效果。其原因在于，在原先的基准模型的序列层上，实体预训练的解码方式是基于单向的贪心解码，通过将其替换成CRF，能够捕获双向的上下文信息，从而学习到更充分的信息。另一方面，尽管替换为CRF解码方式，但模型的分类效果并没有显著提升，分析原因可能是对于实体信息的学习不够充分。通过添加word-level的attention 机制提高了模型的分类效果，其原因在于提高了模型对于文本序列上实体信息的关注度，让模型更好的学习到实体信息。该实验说明，使用CRF和attention机制能够有效提升模型在实体预训练的效果。

表1SemEval2010 Task8 语义关系-样本分布  
表2改进序列层的实验结果(未添加额外的先验知识)  

<html><body><table><tr><td colspan="2">prior knowledge)</td></tr><tr><td>方法</td><td>Marco-F1(%)</td></tr><tr><td>Baseline(SDP)</td><td>84.4</td></tr><tr><td>+CRF</td><td>84.5</td></tr><tr><td>+CRF,+ATTENTION</td><td>84.9</td></tr></table></body></html>

# 3.3.2融合多句法结构

在第二组实验中,保持文献[2进行实体预训练的序列层不变，通过将基准模型的依赖层替换成融合多句法结构的关系层，实验结果如表3所示。

表3融合多句法结构的实验结果（添加了额外的先验知识，

WordNet)

Table 2Experimental results of improved sequence layer(without extra   
Table 3Experimental results of multi-syntactic structure(with extra prior   

<html><body><table><tr><td colspan="2">knowledge,WordNet)</td></tr><tr><td>Baseline</td><td>多句法结构</td></tr><tr><td>SDP</td><td>85.1 85.3</td></tr><tr><td>SubTree</td><td>83.9 84.0</td></tr><tr><td>FullTree</td><td>82.9 83.0</td></tr></table></body></html>

基准模型的句法结构采用映射函数来选择使用何种句法结构，而本文的模型通过融合多种句法结构为一体，其目的在于提升模型的鲁棒性，使得模型能够直接处理不同的句法结构。由实验结果可知，本文提出的融合多句法结构的模型，对于不同的句法结构都有着稳定可靠的表现，其结果较基准模型有所提升，具备良好的鲁棒性。

进一步地，由第一组实验已知，通过使用CRF解码并添加Attention机制的方式，能够提升序列层的实体训练效果，这对于模型进一步分类起到了促进作用。因此，通过将两组实验进行结合，即将改进的序列层与多句法融合的结构叠层嵌套，对完整模型进行端到端的训练，实验结果如表4所示。

在第三组实验中，本文提出的 H-RNN 模型要优于添加了额外先验知识的基准模型和基于序列的模型。其原因可能是：a）实体识别与关系分类是互相关联的任务，序列层的改进，提升了实体预训练的效果，对于训练端到端的完整模型起到了促进作用，从而提升了分类效果；b）文本序列和句法结构都蕴含了不同的信息成分，基于序列的模型在信息量上过于单一，通过将结构化的信息引入到文本序列上，能够丰富模型的分类能力；c）同时，进一步证明了，SDP在序列的关系分类问题上优于SubTree 和FulITree。因为SDP在结构上要更直观简洁，其他两种结构部分多余的节点信息会引入一些冗余，可能会导致训练过程对重要信息的学习造成干扰。

表4改进的序列层 $^ +$ 融合多句法结构的实验结果（添加了额外的先验知识，WordNet）

<html><body><table><tr><td></td><td>多句法结构</td></tr><tr><td>SDP</td><td>85.9</td></tr><tr><td>SubTree</td><td>84.7</td></tr><tr><td>FullTree</td><td>83.6</td></tr><tr><td>SDP(baseline)</td><td>85.1</td></tr><tr><td>SPSeq</td><td>84.4</td></tr><tr><td>SPXu</td><td>84.7</td></tr></table></body></html>

表5H-RNN与其他方法进行对比

Table 4Experimental results of improved sequence layer& multisyntactic structure(with extra prior knowledge,WordNet)   
Table 5 Comparison between H-RNN with other methods   

<html><body><table><tr><td>模型</td><td>添加的特征</td><td>Marco-F1/%</td></tr><tr><td rowspan="4">SVM</td><td>POS,WordNet,prefixesandother</td><td rowspan="4">82.2</td></tr><tr><td>morphological features,dependency parse, Levin classes,PropBank,FanmeNet,</td></tr><tr><td></td></tr><tr><td>NomLex-Plus, Google n-gram, paraphrases,</td></tr><tr><td>CNN</td><td>TextRunner position features,words around nominals, WordNet</td><td>82.7</td></tr><tr><td>SDP-LSTM</td><td>POS embeddings,WordNet embeddings, grammar relation embeddings</td><td>83.7</td></tr><tr><td>BLSTM</td><td>POS,NER,WordNet, position features, dependency feature,relative-dependency feature</td><td>84.3</td></tr><tr><td>ATT-BLSTM</td><td>Without any other features,only use word vector(50 dim & 100 dim) and position indicators</td><td>84.0</td></tr><tr><td>2ATT-BLSTM- BLTM</td><td>position features,WordNet,NER</td><td>84.3</td></tr><tr><td>BLSTM- BTLSTM(SDP)</td><td>POS,dependency feature,WordNet</td><td>85.1</td></tr><tr><td>H-RNN(SDP)</td><td>POS,dependency feature,WordNet</td><td>85.9</td></tr></table></body></html>

# 3.4 与其他方法对比

本文选取了当前在关系分类中最好的一些方法与本文进行横向对比，分别是：

a)SVM[28]。利用大量人工定义和工具抽取的特征，使用SVM进行训练和分类。

b)CNN[13]。将句子作为序列数据处理，并利用卷积神经网络学习句子级别的特征；同时，利用一个特殊的位置向量来表示序列上的每一个字。通过将句子级别特征和词法特征拼接在

一起，输入分类器 softmax 中进行预测。

c)SDP-LSTM[I1]。将最短路径的形式与网络进行结合，同时通过四个通道融合了不同的异构信息。

d)BLSTM[29]。采用NLP工具和词法资源衍生出的众多特征与双向LSTM网络学习句子级别的特征。

e)Att-BLSTM[12]。提出了一种将注意力融合进双向循环神经网络的网络结构，提高了分类器对关键信息的注意力。

f)2ATT-BLSTM-BLSTM[22]。提出了一种融合注意力机制的叠层的双向循环神经网络模型。

g)BLSTM-BTLSTM[21]。提出了一种将实体识别与关系分类拼接在一起的端到端的神经网络模型，其中实体识别用Bi-LSTM来表示，关系分类用Bi-Tree-LSTM来表示。

如表5所示，相对于其他模型，在更少的额外的特征信息的情况下，H-RNN的结果达到了目前最优效果。

# 4 结束语

本文针对现有基于特定句法结构的关系分类模型无法迁移到其他句法结构上的问题，提出了一种融合多句法结构的叠层循环神经网络模型。该模型通过利用Bi-LSTM-CRF（融合attention）和Bi-Tree-LSTM来表示文本序列和句法结构，将实体预训练和关系分类融合到端到端的框架中利用共享参数进行训练，在实体预训练阶段融合attention机制提升对实体的关注度，同时对多种句法结构进行加权学习。

在Semeval-2010Task8数据集上实验证明，1)多句法结构的网络模型能够对不同句法结构的关系进行有效分类，具备一定的鲁棒性。同时，进一步证明了 SDP 结构(相对于其他结构)对于关系分类是最有效的。2)通过构造端到端的模型，在实体预训练阶段利用attention机制提升模型对实体的关注度，利用共享参数的学习方式，有效提升了模型的分类精度。

# 参考文献：

[1]Iris H, Su Nam K, Zornitsa K,et al. Semeval-2010 task 8:multi-way classification of semantic relations between pairs of nominals [C]//Proc of the 5th International Workshop on Semantic Evaluation，SemEval'10. Stroudsburg,PA:ACL Press,2010:33-38.   
[2]Kambhatla N.Combining lexical,syntactic,and semantic features with maximum entropy models for extracting relations [C]//Proc of the 42nd ACL on Interactive poster and demonstration sessions. Stroudsburg,PA: ACL Press,2004 :No.22.   
[3]Zhou GuoDong,Su Jian,Zhang Jie,et al.Exploring Various knowledge in relation extraction [C]//Proc of the 43rd annual meeting on association for computational linguistics. Stroudsburg,PA :ACL Press,20o5:427-434.   
[4]Zhang Zhu.Weakly-supervised relation classification for information extraction [C]// Proc of the 13th ACM international conference on Information and knowledge management.New York:ACM Press,2004: 581-588.   
[5]Zelenko D,Aone C,Richardella A. Kermel methods for relation extraction [J]. Journal of machine learning research,2003,3 (Feb): 1083-1106.   
[6]Culotta A,Sorensen J. Dependency tree kernels for relation extraction [C]/ Proc of the 42nd Annual Meeting on Association for Computational Linguistics.Stroudsburg,PA $\because$ ACL Press,2004: No. 423.   
[7]Bunescu R C, Mooney R J.A shortest path dependency kernel for relation extraction [Cl//Proc of Conference on Human Language Technology and Empirical Methods in Natural Language Processing.Stroudsburg,PA: ACL Press,2005: 724-731.   
[8]Katiyar A,Cardie C.Nested named entity recognition revisited [C]// Proc of the 16th Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies. Stroudsburg PA: ACL Press,2018: 861-871.   
[9]Wang Qi,Xia Yuhang,Zhou Yangming,et al. Incorporating dictionaries into deep neural networks for the Chinese clinical named entity recognition [J]. arXiv,2018,preprint arXiv: 1804. 05017.   
[10] Zheng Suncong,Wang Feng,Bao Hongyun,et al. Joint extraction of entities and relations based on a novel tagging scheme[C]// Proc of the 55th Annual Meeting ofthe Association for Computational Linguistics. Stroudsburg, PA: ACL Press,2017: 1227-1236.   
[11] Yan Xu,Mou Lili,Li Ge,etal.Classifying relationsvialongshort term memory networks along shortest dependency paths [C]// Proc of the 20th ConferenceonEmpiricalMethodsinNaturalLanguage Processing. Stroudsburg, PA : ACL Press,2015: 1785-1794.   
[12] Zhou Peng,Wei Shi,Tian Jun,et al.Attention-based bidirectional long short-term memory networks for relation classification [C]//Proc ofthe 54th Annual Meeting of the Association for Computational Linguistics. Stroudsburg,PA : ACL Press,2016: 207-212.   
[13] Zeng Daojian,Liu Kang,Lai Siwei,et al.Relation classification via convolutional deep neural network [C]// Proc of the 25th International Conference on Computational Linguistics. Stroudsburg, PA $\because$ ACL Press, 2014: 2335-2344.   
[14] Aone C,Ramos-Santacruz M. REES:a large-scale relation and event extraction system [C]// Proc of the 6th conference on Applied natural language processing. Stroudsburg, PA $\because$ ACL Press,2000 : 76-83.   
[15] Zhang Min,Zhang Jie,Su Jian.Exploring syntactic features for relation extraction using aconvolution tree kernel[C]/ Proc of Main Conference on Human Language Technology, Conference of the North American Chapter of the Association of Computational Linguistics.Stroudsburg,PA: ACL Press, 2006: 288-295.   
[16] Zhou Guodong,Zhang Min,Ji Donghong,et al. Tree kernel-based relation extraction with context-sensitive structured parse tree information[C]/ Proc of the Joint Conference on EMNLP-CoNLL. Stroudsburg,PA $\because$ ACL Press, 2007: 728-736.   
[17] SocherR, Huval B,Manning C D,et al. Semantic compositionality through recursive matrix-vector spaces [Cl//Proc of Joint Conference on EMNLPCoNLL. Stroudsburg,PA : ACL Press,2012: 1201-1211.   
[18] Xu Kun，Feng Yansong,Huang Songfang，et al. Semantic relation classification via convolutional neural networks with simple negative sampling[J].arXiv,2015,preprint arXiv: 1506.07650.   
[19] Liu Yang,Wei Furu,Li Sujian,et al.A dependency-based neural network for relation classification [J].arXiv,2015,preprint arXiv: 1507.04646.   
[20] Li Jiwei,Thang Luong,Dan Jurafsky,et al.When are tree structures necessary for deep learning of representations?[C]// Proc of Conference on EMNLP. Stroudsburg,PA : ACL Press, 2015: 2304-2314.   
[21] Miwa M,Bansal M.End-to-endrelation extractionusing stms onsequnces and tree structures [C]//Proc of the 54th Annual Meeting of the Association for Computational Linguistics.Stroudsburg, PA $\because$ ACL Press, 2016: 1105- 1116.   
[22] Xiao Minguang,Liu Cong. Semantic relation classification via hierarchical recurrent neural network with attntion [C]//Proc of the 26th International Conference on Computational Linguistics. Stroudsburg,PA $\because$ ACL Press, 2016: 1254-1263.   
[23] Zhang Xiaobin, Chen Fucai, Huang Ruiyang. A Combination of RNN and CNN for attention-based relation classification [J]. Procedia Computer Science,2018,131: 911-917.   
[24] Feng Jun,Huang Minlie, Zhao Li,etal. Reinforcement Learning for Relation Classification from Noisy Data [Cl// Proc of AAAI. Palo Alto, CA: AAAI Press, 2018.   
[25]Liu Wenpeng,Cao Yanan,Cao Cong,et al. Anadversarial training framework for relation classification [Cl//Proc of ICCS.Berlin: Springer Press, 2018: 194-205.   
[26] Graves A， Schmidhuber J. Framewise phoneme classification with bidirectional LSTM networks [C]//Proc of IJCNN on IEEE.Piscataway, NJ: IEEE Press,2005,4: 2047-2052.   
[27] Ratinov L,Roth D.Design challenges and misconceptions in named entity recognition [C]// Proc of the 13th Conference on Computational Natural Language Learning. Stroudsburg, PA: ACL Press,2009: 147-155.   
[28]Rink B,Harabagiu S.Utd: Clasifyingsemantic relationsbycombining lexical and semantic resources [C]// Proc of the 5th International Workshop on Semantic Evaluation. Stroudsburg,PA: ACL Press,2010: 256-259.   
[29] Zhang Shu,Zheng Dequan,Hu Xinchen,et al.Bidirectional long short-term memory networks for relation classification [C]//Proc of te 29th Pacific Asia Conference on Language, Information and Computation. Stroudsburg, PA : ACL Press, 2015: 73-78.