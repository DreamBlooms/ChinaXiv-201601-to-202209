# 面向小样本关系抽取的自适应胶囊网络

张晓明la，窦全胜 $^ { 1 \mathrm { b } , 2 ^ { \dagger } }$ ，陈淑振1b，唐焕玲 1b,2(1.山东工商学院 a.信息与电子工程学院;b.计算机科学与技术学院，山东 烟台 26400;2.山东省高等学校未来智能计算协同创新中心，山东 烟台 264000)

摘要：小样本关系抽取任务是自然语言处理中的热点问题，旨在使用低成本的标注数据训练关系抽取模型。目前广泛使用的原型网络存在类原型表达不准确、不完整等问题。为了克服该问题，提出一种自适应胶囊网络(AdaptiveCapsule Network，ACNet)，ACNet 借助胶囊网络的归纳能力生成类原型，并在此基础上对动态路由过程进行评估，使其面对不同样本能自适应调整网络参数。同时，在ACNet中引入一种记忆迭代机制，帮助模型快速确定类表示。在小样本关系数据集FewRel上进行实验验证得出，ACNet 能够有效处理小样本关系抽取任务。

关键词：关系抽取；小样本；自适应；胶囊网络；动态路由 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2021.12.0702

Adaptive capsule network for few-shot relation extraction

Zhang Xiaomingla, Dou Quansheng1b.2†, Chen Shuzhen1b, Tang Huanling1b.2 (1.a.SchoolofInformation&ElectronicEnginering,b.SchoolofComputercience&TechnologyhandongTechology& BusinessUniversityYantaiShandong 2640o0,China;2.Shandong Future Inteligent ComputingCollborative Innovation Center, Yantai Shandong 264000, China)

Abstract:The few-shot relationshipextraction task isahot issue in natural language processing.It aims to train the relationship extraction model using low-cost label data.The widely used prototype network has some problems,such as inaccurate and incomplete expression of class prototypes.This paper proposed an Adaptive Capsule Network (ACNet) to solvethis problem.ACNet generatesaclass prototype with the inductivecapabilityof thecapsule network.On this basis,the dynamic routing processis evaluated so that itcan adjust network parameters adaptively to diferentsamples.At the same time,a memoryiteration mechanism is introduced in ACNet to help the model determine theclass representation quickly. Experiments onafew-shot relational datasetFewRel show that ACNet can handle few-shot relational extraction tasks.

Key words: relationship extraction; few-shot; adaption; capsule network; dynamic routing

# 0 引言

由自然语言构成的文本数据是当前大数据的重要组成部分，在文本中，如人名、地名等具有特殊意义的词汇被称为实体(Entity)，实体之间通常存在着某种关系，如语法关系、语义关系等．所谓实体关系抽取(Entity Relation Extraction)，就是指在实体识别的基础上，对实体之间存在的上述关系进行有效的识别和判断。实体关系抽取是正确理解文本语义的关键，也是文本挖掘和信息抽取的关键基础性任务，其效果对文本摘要、自动问答[1]、机器翻译[2]、语义网标注、知识图谱[3]等自然语言处理下游任务有着重要的影响，一直是自然语言处理(NaturalLanguage Processing,NLP)研究领域的重要研究内容和热点研究问题。

近年来，深度学习的兴起为关系抽取任务提供了新的解决方案，这方法多采用监督学习方式，其效果对样本数据存在较强依赖。然而在现实场景中，数据量往往难以满足大规模深度网络训练的需要。为了避免数据收集带来的人力和时间成本，一些学者提出小样本学习(Few-Shot Learning,FSL)[4]的概念，探索深度学习模型在小样本条件下泛化能力。关于小样本学习的早期研究，多集中于数据增强[5和正则化技术，通过这两种技术来缓解由数据稀疏引起的过拟合问题。有学者受人类学习过程的启发，提出了元学习[6](Meat-Learning，

ML)的概念。ML通常将小样本学习的训练过程分解为若干个元任务，元任务在不同mini-batch之间切换并从中提取一些可迁移的知识。因此，Few-shot模型只需使用少量标记样本可以对新类别进行分类。

然而，现有的小样本学习方法仍面临许多重要问题，包括强先验方法的弱移植性[7]、复杂的任务梯度转移[8]、以及微调目标问题[9]。Snell[10]和Sung[11]等人提出的方法结合了非参数方法和度量学习，为其中一些问题提供了解决方案。非参数方法的优势在于能够快速吸收新样本，且模型只需学习样本的表示和度量，这在一定程度上避免了过拟合。但同一类中的实例是相互关联的，并且有它们的统一分数和特定分数。在之前的研究中，类级表示多通过简单地求和或平均支持集样本特征来计算。鉴于实例样本的多样性，这种方法所获得的类级表示往往会受到不同形式样本的噪声影响。且现有小样本学习算法大多不会对支持集进行微调。当增加支持集的大小时，数据扩充带来的改进也会被更多的样本级噪声削弱。

2017年Sabour[12]等人提出了胶囊网络，该网络具有解决类表达问题的潜力，胶囊网络将样本向量封装为"胶囊”，并通过非参数的动态路由算法(Dynamic Routing，DR)对部分和整体之间的内在空间关系进行编码。类似的，在小样本任务中，将样本视为部分，类视为整体，DR算法编码的类表示更具代表性。

本文在胶囊网络的基础上，提出一种自适应胶囊网络(AdaptiveCapsuleNetwork，ACNet)，旨在从少量支持集样本中发掘样本类别的广义类表示。在胶囊网络中，DR算法的路由次数决定了部分到整体的层次关系，现有的路由算法对所有样本使用相同的路由次数，面对复杂的实例环境难以有效做到类归纳，ACNet对胶囊网络中的动态路由算法进行改进，提出一种自适应归纳算法(Self-adaptionInductiveAlgorithm，SIA)，SIA通过评估路由算法在实例样本上的执行过程，为不同类样本分配相应的路由次数，实现路由参数的自适应调整。同时，为了降低不同样本所带来的噪声干扰，ACNet引入了一种可训练的记忆模块帮助路由过程快速确定类表示，记忆模块中包含不同类的类特征，这些类级表示作为模型的学习经验，有效缓解了样本量过少带来的路由过程不准确问题。

综上所述，本文主要贡献包括：

a）提出一种自适应胶囊网络。该网络将记忆保存机制与动态路由算法结合，能够快速适应支持集样本，并在小样本场景中有效归纳样本类表示。b)提出一种自适应归纳算法。该算法在动态路由的基础上引入一种路由过程的评估机制，使模型能够针对不同样本自适应的分配路由参数，缓解因样本多样性导致的类特征难聚合、表达不完善等问题。

将本文方法在FewRel数据集上进行实验，实验结果证明了本文研究方法的有效性，对小样本场景下的关系抽取任务，具有较强的指导意义和应用价值。

# 1 问题描述

为了论述上的便利和准确，以下就实体关系抽取任务给出形式化描述。

设 $W = \{ w _ { i } \} _ { i = 1 } ^ { m }$ 和 $E = \left\{ e _ { i } \right\} _ { i = 1 } ^ { n }$ 分别为单词符号集合和实体标记集合，W上的文本t可视作W中元素构成的有限长度序列：$t = w _ { 1 } ^ { t } w _ { 2 } ^ { t } . . . w _ { h } ^ { t }$ ，在文本中，具有特殊语义的一个或一组单词符号被称为实体，每个实体于E中标记对应： $t = w _ { i } ^ { \prime } \cdots \underbrace { w _ { i } ^ { \prime } \cdots w _ { j } ^ { \prime } } _ { \epsilon _ { i } } \cdots \underbrace { w _ { i } ^ { \prime } \cdots w _ { i } ^ { \prime } } _ { \epsilon _ { i } } \cdots w _ { i } ^ { \prime }$ 其中， $\boldsymbol { w _ { i } ^ { t } \cdots w _ { j } ^ { t } }$ 和 $w _ { u } ^ { t } \cdots w _ { \nu } ^ { t }$ 分别对应于实体 $\boldsymbol { e } _ { p }$ 和 $\boldsymbol { e } _ { \boldsymbol { q } }$ 。实体识别和标注是NLP处理的另一项重要任务，在此不做讨论，本文在实体识别的基础上进一步分析语句中两个实体之间的关系。

实体间的联系构成了一个关系集合，记作 $\boldsymbol { R } = \{ r _ { \mathrm { } } \} _ { j = 1 } ^ { k }$ ，文本t中的一对实体 $\boldsymbol { e } _ { p }$ 和 $\boldsymbol { e } _ { \boldsymbol { q } }$ 的关系可用三元组 $\langle e _ { p } , r , e _ { q } \rangle$ 表示，其中$r \in R$ 为目标关系集的一个元素。实体关系抽取任务的目的是从自然语言文本中抽取出这样的关系三元组，为更深入的文本挖掘和理解奠定基础。以句子"London is the capital of theUK"为例，其中"London"和"UK"为两个反映地名的实体，两个实体间存在语义关系：“capitalof”，<London,Capital of,$\mathrm { U K } >$ 即为一个实体关系三元组。

小样本实体关系抽取任务是针对某些任务领域关系样本数量稀少，无法开展大规模模型训练的情况。在该场景下，给定关系集合R和只包含少量样本的支持集S，要求模型能够准确预测查询样本语句 $\mathbf { x }$ 中实体对 $\boldsymbol { e } _ { p }$ 和 $e _ { q }$ 间的关系。其中，支持集S和查询集Q均通过对数据集D采样获得，即在数据集D中随机选择C个类别，并在每个类别中随机选择K个样本构成支持集： ${ \cal { S } } = \{ { s _ { c , k } } \}$ ， ${ \boldsymbol { c } } = 1 , . . . , { \boldsymbol { C } } , { \boldsymbol { k } } = 1 , . . . , { \boldsymbol { K } }$ 。另外在C个类别的其余样本中随机选择R个样本构造查询集：$Q = \{ s _ { q } \} , q = 1 , . . . , R$ 。这种构建支持集与查询集的任务方式也被称作C-wayK-shot。在小样本学习中，支持集中的实例数量（即 $\mathrm { C ^ { * } K }$ 个)通常很少，关系分类模型需要在支持集的少数示例中学习样本特征，并预测查询实例 $\mathbf { x }$ 的关系类别。

# 2 自适应胶囊网络模型(ACNet)

本文提出了用于小样本关系分类的自适应胶囊网络模型(ACNet)，模型共包含基类数据 $s _ { i } ^ { b a s e }$ 、支持集 ${ \cal S } _ { c , k }$ 和查询集 $s _ { q }$ 三个输入，其中 ${ S _ { i } ^ { b a s e } }$ 由训练集 $D _ { t r a i n }$ 生成， $s _ { c , k }$ 和 $s _ { q }$ 以c-way-k-shot任务为标准在 $D _ { t r a i n }$ 中随机抽取获得。ACNet模型四个模块，具体如图1所示。

![](images/aaeeab65f0d08fa8b2888d8e49c08b1339ec48591b204c5d89ab27af0e781418.jpg)  
图1自适应胶囊网络(ACNet)结构示意图  
Fig.1Structure diagram ofAdaptive Capsule Network (acnet)

1）编码模块：采用预训练的BERT[13]模型分别对基类数据 $s _ { i } ^ { b a s e }$ 、支持集 ${ \cal S } _ { c , k }$ 和查询集 $s _ { q }$ 进行编码，分别得到基类向量$e _ { i }$ 、支持向量 $\boldsymbol { e } _ { c , k }$ 和查询向量 $\boldsymbol { e } _ { \boldsymbol { q } }$ 。

2）自适应归纳模块(Adaptive Induction Module，AIM):采用自适应归纳算法(SIA)对支持集向量 ${ \cal S } _ { c , k }$ 进行归纳，SIA在动态路由算法的基础上，加强对路由过程的评估，针对不同的支持向量自适应调整路由参数，经过多次路由迭代，获得支持集的嵌入向量 ${ e _ { c , k } } ^ { \prime }$ 。3）查询增强模块(Query Enhancement Module，QEM)：复用自适应归纳算法，在 $\boldsymbol { e } _ { c , k ^ { ' } }$ 的基础上对查询向量 $\boldsymbol { e } _ { \boldsymbol { q } }$ 进行调整，获得包含查询信息的类表示 $e _ { c }$ ，用于后续 $e _ { q }$ 的分类。4）分类模块：采用余弦相似度量计算查询向量 $e _ { q }$ 与类表示 $e _ { c }$ 的匹配分数，预测查询向量类别。

# 2.1编码模块

选择预训练的BERT模型作为编码工具，其模型架构是基于Transformer[14]的多层双向编码器。在关系语句中插入[cls]和[sep]作为开头和结尾的标识符号，并使用[cls]输出的d维向量作为给定实例关系语句 $\mathbf { w }$ 的向量表示，整个过程可以表示为 $e = E ( w | \theta )$ ，其中 $\theta$ 为BERT的模型参数。预训练的BERT模型提供了强大的上下文相关句子表示，可用于各种目标任务，并且适用于小样本关系分类。

使用wiki文本对BERT模型进行预训练，为了能够适应小样本关系分类任务，在训练集 $D _ { t r a i n }$ 中随机取 $C _ { b a s e }$ 个类别的数据组成基类样本 $\{ s _ { i } ^ { b a s e } \} _ { i = 1 } ^ { C _ { b a s e } }$ 用于对BERT编码器进行微调。对于每个输入 $s _ { i } ^ { b a s e }$ ，编码器 $E ( s _ { i } ^ { b a s e } \mid \theta )$ 输出d维向量 $\boldsymbol { e } _ { i }$ 。同时有矩阵 $\mathbf { M } = [ e _ { 1 } , e _ { 2 } \cdots e _ { i } \cdots e _ { C _ { b a s e } } ]$ ， $\mathbf { M }$ 作为记忆矩阵为每个基类样本保存一个记忆特征向量，为了保证记忆特征的有效性， $E ( s _ { i } \mid \boldsymbol { \theta } )$ 和 M都将在模型训练过程中进一步调整，具体细节将在2.2节中阐述。

# 2.2自适应归纳模块(Adaptive Induction Module，AIM)

AIM旨在利用记忆矩阵M对支持集进行调整，将多个记忆特征和支持向量输入到AIM中，经过自适应归纳算法(SIM)获得每个支持向量的嵌入向量，DR算法可以实现多向量到单一向量归纳的功能，SIM在此基础上改进了路由过程的评估方法，并依照其评估结果自适应的为不同样本分配路由参数，获得的嵌入向量能够有效整合记忆特征中的信息，适应支持集的能力更强。

具体地，支持集中的实例首先被BERT编码为样本向量 $\{ e _ { c , k } \} _ { k = 1 } ^ { K }$ ，然后输入到AIM中处理。在给定记忆矩阵M 和支持样本向量 $\boldsymbol { e } _ { c , k }$ 的情况下，AIM旨在使用记忆矩阵M来调整支持向量，整个过程可以概括为：${ e _ { c , k } } ^ { \prime } = A I M ( M , e _ { c , k } )$ 。

在胶囊网络中，存在1和 $^ { 1 + 1 }$ 两个胶囊层，低级胶囊分布在胶囊层1上，通过动态路由算法将多个低级胶囊以加权和的方式路由到胶囊层 $1 { + } 1$ 上，并获得高级胶囊 $\vert \nu _ { j }$ ，鉴于胶囊网络部分到整体的编码特性，在小样本学习中，将低级胶囊视为样本，而高级胶囊代表样本类别特征，因此在本文中，对于输入AIM的每个 $m _ { i } \in M$ 和 $\boldsymbol { e } _ { c , k }$ 进行标准矩阵转换，并应用squash函数[12]进行归一化:

$$
\begin{array} { c } { \hat { m } _ { i } = s q u a s h ( W _ { j } m _ { i } + b _ { j } ) } \\ { \hat { e } _ { c , k } = s q u a s h ( W _ { j } e _ { c , k } + b _ { j } ) } \end{array}
$$

这里的转换权重 $W _ { j }$ 和参数 $b _ { j }$ 在输入中共享，需要在网络中学习得到，squash函数为非线性压缩函数，目的是在保持向量方向不变的条件下，将其长度压缩至区间[0,1]内，函数通式如下：

$$
s q u a s h ( x ) = { \frac { \| x \| ^ { 2 } } { 1 + \| x \| ^ { 2 } } } { \frac { x } { \| x \| } }
$$

在胶囊网络中，高级胶囊 $\boldsymbol { \nu } _ { j }$ 由低级胶囊的加权和计算得到：

$$
\nu _ { j } = \sum _ { i = 1 } ^ { n } ( c _ { i j } + p _ { i j } ) \hat { m } _ { i }
$$

$c _ { i j }$ 为不同等级胶囊间的路由权重， $p _ { i j } = t a n h ( P C C s ( \hat { m } _ { i } , \hat { e } _ { c , k } ) )$ ，$\mathrm { P C C s ^ { [ 1 5 ] } }$ 用于度量基类类特征 $\hat { m } _ { i }$ 和支持向量 $\hat { e } _ { c , k }$ 间的相似程度，具体如式(5)所示。

$$
P C C s = \frac { C o \nu ( x _ { 1 } , x _ { 2 } ) } { \sigma _ { x _ { 1 } } \sigma _ { x _ { 2 } } }
$$

其中，Cov为协方差， $\sigma _ { x _ { 1 } }$ 和 $\sigma _ { x _ { 2 } }$ 分别为向量 $x _ { 1 }$ 和 $x _ { 2 }$ 的标准差，由于PCCs的值分布在[-1,1]区间内，因此可用于增强或惩罚路由参数 $c _ { i j }$ □

在传统DR 算法中，路由次数r的大小决定了不同胶囊层之间的层次关系，在强监督环境中，网络在开始训练时往往需要选取合适的 $\mathrm { ~ \bf ~ r ~ }$ 值，并将其应用在所有样本上，但在小样本RE任务中，数据规模不足且关系实例多样复杂，不同样本达到收敛要求的路由次数也不相同，固定的 $\mathrm { ~ \bf ~ r ~ }$ 值难以满足任务需要。因此，为了评估路由过程在小样本实例上的性能，并实现路由次数的自适应调整，本文提出一种自适应归纳算法(Self-adaption Inductive Algorithm，SIA)来解决此问题。SIA将路由过程描述成最小化负一致性分数(NegativeAgreementScore,NAS)的优化问题：

$$
\begin{array} { c } { { \displaystyle \operatorname* { m i n } _ { c , \nu } f ( u ) = - \sum _ { i , j } c _ { i j } \big \langle \nu _ { j } , \hat { m } _ { i } \big \rangle } } \\ { { \mathrm { s . t . } \forall i , j \colon c _ { i j } > 0 , \sum _ { j } c _ { i j } = 1 . } } \end{array}
$$

NAS的目的是将更高的 $c _ { i j }$ 值分配给更加接近的 $\langle \nu _ { j } , \hat { m } _ { i } \rangle$ 对，但鉴于向量的高维特征，NAS函数的计算一直是一个开放问题。核密度估计(KernelDensityEstimation，KDE)是一种非参数密度估计方法，不需要假设一致对是从参数分布中提取的，这为解决NAS问题提供了可能。通过KDE将式(6)转换成如下形式：

$$
\operatorname* { m i n } _ { c , m } f ( u ) = - \sum _ { i , j } c _ { i j } k ( d ( \nu _ { j } , \hat { m } _ { i } ) )
$$

其中： $d$ 为欧式距离， $k$ 为Epanechnikov[16]核函数：

$$
k ( x ) = \left\{ { \begin{array} { l l } { 1 - x } & { x \in [ 0 , 1 ) } \\ { 0 } & { x \geq 1 } \end{array} } \right.
$$

均值漂移(Mean Shift)[17]是一种基于密度梯度上升的非参数方法，可用于最小化NAS函数 $f ( u )$ 以解决KDE问题：

$$
\nabla f ( u ) = \sum _ { i , j } c _ { i j } k ^ { \prime } ( d ( \nu _ { j } , \hat { m } _ { i } ) ) \frac { \hat { c } d ( \nu _ { j } , \hat { m } _ { i } ) } { \hat { \sigma } \nu }
$$

确定 $c _ { i j } ^ { \tau }$ 的值后，对高级胶囊 $\nu _ { j } ^ { \tau + 1 }$ 进行更新：

$$
\nu _ { j } ^ { \tau + 1 } = \frac { \sum _ { i , j } c _ { i j } ^ { \tau } k ^ { \prime } ( d ( \nu _ { j } , \hat { m } _ { i } ) ) \hat { m } _ { i } } { \sum _ { i , j } k ^ { \prime } ( d ( \nu _ { j } , \hat { m } _ { i } ) ) }
$$

高级胶囊 $\nu _ { j } ^ { \tau + 1 }$ 中聚合了记忆特征的信息，通过取平均的方式对支持向量 $\hat { e } _ { c , k }$ 进行调整：

$$
\hat { e } _ { c , k } \gets \frac { \hat { e } _ { c , k } + \nu _ { j } } { 2 }
$$

$c _ { i j } ^ { \tau + 1 }$ 的值可以使用标准梯度下降进行更新：

$$
c _ { i j } ^ { \tau + 1 } = c _ { i j } ^ { \tau } + \alpha \cdot ( k ( d ( \nu _ { j } ^ { \tau } , m _ { i } ) ) + p _ { i j } )
$$

其中： $\alpha$ 为步长。 $k ( d ( \nu _ { j } ^ { \tau } , m _ { i } ) )$ 为不同等级胶囊间的相似度估计，$p _ { i j }$ 为 $k ( d ( \nu _ { j } ^ { \tau } , m _ { i } ) )$ 的修正量，代表记忆特征向量 $m _ { i }$ 与支持向量$\boldsymbol { e } _ { c , k }$ 的相似程度，相似程度越高对应的记忆特征在 $c _ { i j }$ 中的比重越大，反之则会削弱不相关的记忆特征占比。通过估计值加修正量的方式更新胶囊权重 $c _ { i j }$ ，保证生成高级胶囊 $\boldsymbol { \nu } _ { j }$ 时能够有效聚合记忆特征，并在此基础上实现对支持向量的调整。

为了解决路由算法在实例级样本上不会收敛的问题，SIA可以根据单个实例样本NAS取值自行调整路由迭代次数，详细过程如算法1所示：步骤a）代表遍历所有记忆特征$m _ { i }$ 和支持向量 $e _ { c , k }$ ，并在步骤b）和c）分别对其进行归一化计算，步骤e）代表采用加权和的方式计算类特征 $\boldsymbol { \nu } _ { j }$ 的初值，算法在步骤f）进入路由迭代循环，步骤h)代表 $\boldsymbol { \nu } _ { j }$ 的更新过程，具体见式(6)\~(10)，步骤i)和j）表示在获得最新的 $\boldsymbol { \nu } _ { j }$ 后，路由权重 $c _ { i j }$ 和支持向量 $\boldsymbol { e } _ { c , k }$ 的调整更新方式，步骤k）代表NAS函数的取值计算，步骤1)为判断语句，比较NAS更新前后的差值与阈值 $\beta$ 大小，若 $\mid N A S - L a s t \_ N A S \mid > \delta$ ，则表明NAS 函数不满足收敛标准，算法进入步骤o）和步骤p），分别对修正量 $p _ { i j }$ 和NAS进行更新，并重新返回步骤f)进行下一轮的路由迭代，直至 $\vert N A S - L a s t \_ N A S \vert < \delta$ ，即 NAS已具备收敛条件，退出步骤 f)的while 循环，进入步骤q)输出自适应嵌入向量 ${ { e } _ { c , k } } ^ { \prime }$ ，算法结束。

算法1自适应归纳算法(SIA)

输入：超参数 $\alpha$ ， $\beta$ ；路由权重 $c _ { i j } = 1 / n$ ;支持向量 $\boldsymbol { e } _ { c , k }$ ；记忆矩阵$M = [ m _ { 1 } , m _ { 2 } , . . . , m _ { n } ]$ 。

输出：自适应嵌入向量 $e _ { c , k } ^ { \prime }$ 。

a): for all $m _ { i } , e _ { c , k }$ do   
b): $\begin{array} { r l } & { \hat { m } _ { i } = s q u a s h ( W _ { j } m _ { i } + b _ { j } ) } \\ & { \hat { e } _ { c , k } = s q u a s h ( W _ { j } e _ { c , k } + b _ { j } ) } \\ & { p _ { i j } = t a n h ( P C C s ( \hat { m } _ { i } , \hat { e } _ { c , k } ) ) } \\ & { \nu _ { j } = \sum _ { i = 1 } ^ { n } ( c _ { i j } + p _ { i j } ) \hat { m } _ { i j } } \end{array}$   
c):   
d):   
e):   
f):While true do   
g）: Cij← softmax(cij)   
h): $\nu _ { j }  \frac { \sum _ { i } c _ { i j } k ^ { \prime } \big ( d ( \nu _ { j } , \hat { m } _ { i } ) \big ) \cdot \hat { m } _ { i } } { \sum _ { i = 1 } ^ { n } k ^ { \prime } \big ( d ( \nu _ { j } , \hat { m } _ { i } ) \big ) }$   
i): For all $\mathbf { i } \colon c _ { i j } \gets c _ { i j } + \alpha \cdot ( k ( d ( \nu _ { j } , \hat { m } _ { i } ) ) + p _ { i j } )$ （204号   
j): For all $\mathsf { k } \colon \hat { e } _ { c , k } \gets \frac { \hat { e } _ { c , k } + \nu _ { j } } { 2 }$   
k): $\begin{array} { r } { N A S = \log ( \sum _ { i , j } c _ { i j } k ( d ( \nu _ { j } , \hat { m } _ { i } ) ) ) } \end{array}$   
1): If $\mid N A S - L a s t \_ N A S \mid < \delta$ then   
m): break   
n): else   
0): For all $i , k : p _ { i j } = t a c h ( P C C s ( \hat { m } _ { i } , \hat { e } _ { c , k } ) )$   
p): Last $_ { - } N A S  N A S$   
q):Return $e _ { c , k } ^ { \prime } = \nu _ { j }$ （204号

# 2.3查询增强模块(QEM)

为了避免实例多样性所带来的噪声干扰，在上述两个模块获得的查询向量 $\boldsymbol { e } _ { \boldsymbol { q } }$ 以及嵌入向量 $\{ e _ { c , k } ^ { \prime } \} _ { k = 1 } ^ { K }$ 的基础上，构建查询增强模块。QEM目的是在嵌入向量中发掘与查询向量的相似部分，以此构造包含查询信息的类级向量。由于SIA具有自适应的能力，可以增强相似的嵌入和查询向量，并对不相关的向量权重进行削弱。因此，通过复用SIA在支持向量的基础上对查询集向量进行适应调整，并从与查询集更加相关的嵌入向量中得到类级别的向量表示：

$$
e _ { c } = \mathrm { A I M } ( \{ e _ { c , k } ^ { \prime } \} _ { k = 1 } ^ { K } , e _ { q } )
$$

# 2.4相似度分类器

在最后的分类阶段，对基类向量 $e _ { i }$ 和查询向量 $e _ { q }$ 进行分类，获得所有类别的概率分布。传统神经网络分类器是在提取特征向量 $e \in R ^ { d }$ 之后，使用内积 $s _ { k } = e ^ { T } w _ { k } ^ { * }$ 计算每个类别$k \in [ 1 , K ^ { * } ]$ 的初始得分，其中 $\boldsymbol { w } _ { k } ^ { * }$ 为权重向量，然后使用softmax函数计算特征向量在所有 $K ^ { * }$ 类上的分类概率。然而，这种方法不再适用于样本中包含新类的小样本学习。本文使用余弦相似度计算原始分类分数：

$$
s _ { k } = \tau \cdot \cos ( e _ { i } , w _ { k } ^ { * } ) = \tau \cdot \overline { { e } } _ { i } ^ { T } \overline { { w } } _ { k } ^ { * }
$$

其中， $\overline { { e } } _ { i }$ 和 $\overline { { \boldsymbol { w } } } _ { k } ^ { * }$ 是 $l _ { 2 }$ -正则化向量， $\tau$ 是可学习的参数。基类向量 $e _ { i }$ 在 $C _ { b a s e }$ 个类别上的分类概率为

$$
\hat { y } _ { s } = s o f t m a x ( s _ { k } )
$$

在小样本关系分类场景中，将查询向量 $\boldsymbol { e } _ { \boldsymbol { q } }$ 和类表示 $e _ { c }$ 统一输入分类器，得到小样本学习部分每个新类的分类得分：

$$
s _ { q , c } = \tau \cdot c o s ( e _ { q } , e _ { c } ) = \tau \cdot \overline { { e } } _ { q } ^ { T } \overline { { e } } _ { c }
$$

$$
s _ { q } = \{ s _ { q , c } \} _ { c = 1 } ^ { C }
$$

查询向量 $\boldsymbol { e } _ { \boldsymbol { q } }$ 在C个新类的分类概率为

$$
\hat { y } _ { q } = s o f t m a x ( s _ { q } )
$$

# 3 模型学习过程

在小样本关系分类任务中，训练集 $D _ { t r a i n }$ 和测试集 $D _ { t e s t }$ 具有不同的标签空间，即 $R _ { t r a i n } \cap R _ { t e s t } = \emptyset$ ，每个数据集的样本可表示为 $( x , p , y )$ 的形式，其中表包含t个单词的关系实例语句，$p = ( p _ { 1 } , p _ { 2 } )$ 表示中两个标注实体的位置，为实例语句中实体对间的关系类别标签。

ACNet模型在训练时采用Vinyals[18]提出的基于元任务的训练策略。在该策略中，小样本的学习过程被分成了元训练和元测试两个阶段。在元训练阶段，ACNet模型将面对许多独立的监督任务T(即元任务)，不同元任务间的类别不完全相同。每个T都以C-way-K-shot任务为标准，在训练集$D _ { t r a i n }$ 上随机构造，包括支持集 $S _ { T }$ 和查询集 $Q _ { T }$ 。将 $S _ { T }$ 中的样本输入ACNet 模型进行训练，并使用 $Q _ { T }$ 中的样本对模型进行测试，面对每个元任务T，采用如下交叉熵损失推动模型进行训练：

$$
L ( S _ { T } , Q _ { T } ) = - \frac { 1 } { C } \sum _ { c = 1 } ^ { C } \frac { 1 } { R } \sum _ { q } ^ { R } y _ { q } \log ( \hat { y } _ { q } )
$$

其中，C 代表 $S _ { T }$ 中的样本类别，R 为 $Q _ { T }$ 中的样本数量， $y _ { q }$ （204和 $\hat { y } _ { q }$ 分别表示样本真实标签和模型预测标签。在元测试阶段，测试集 $D _ { t e s t }$ 的设置与训练时相同。测试集与训练集合具有不同的标签空间，因此，新任务中的样本类别是之前学习过的任务中没有出现的，ACNet在训练过程中不断学习新的任务，在经过大量的不同任务训练之后，能够更好地处理任务之间的不同并忽略特定任务的特征，在面对新的小样本任务时，具有更强的泛化能力。

# 4 实验

# 4.1数据集、评估指标

本文在小样本关系分类数据集FewRel[19],[20]上对模型进行评估。FewRel数据集分为1.0与2.0两个版本，FewRel1.0使用Wikipedia作为数据源，首先通过远程监督方式生成，然后通过手工去除噪声数据。最终FewRel1.0数据集包含100个关系，每个关系有700个实例。每个句子的平均token 数量为24.99，共有124577个唯一标记。100个关系类被分为三部分，其中64个关系类用于训练，16个用于验证和20个用于测试。FewRel2.0沿用1.0的训练集，再此基础上增加生物医学文献数据库PubMed作为测试集，共包含25个关系类别，每个关系类别有100个实例，同时采用SemEval-2010任务8[21]作为验证集。表1描述了FewRe1数据集中的数据格式，其中包括关系ID、样本语句中包含的单词(tokens)、头尾实体及其位置的标注。

实验部分的样本设置以C-way-K-shot任务为标准，具体样本案例如表2所示，鉴于篇幅有限仅描述2-way-1-shot样本实例，其中蓝色字体代表头实体，红色代表尾实体，训练与测试阶段的样本分别来自FewRel1.0训练集和FewRel2.0测试集，本文主要研究4种小样本学习配置，即5-way-1-shot、5-way-5-shot、10-way-1-shot、10-way-5-shot。实验给出的所有结果均为10次训练重复的平均值和标准差，并使用20000个独立样本进行测试。

表1FewRel数据集中的数据格式

Tab.1 Data format in fewrel dataset   

<html><body><table><tr><td>key</td><td>value</td></tr><tr><td>实体关系 ID</td><td>P2094</td></tr><tr><td>句中包含的单词</td><td>["Sasakul","turned","pro","in","1991","and","captured","the","WBC","and","lineal","flyweight","titles",</td></tr><tr><td>头实体及位置</td><td>"with","a","win","over","Yuri","Arbachakov","in","1997","."] ["yuri Arbachakov","Q542462",[文献[17,18]]]</td></tr><tr><td>尾实体及位置</td><td>["flyweight", "Q508484",[文献[11]]</td></tr></table></body></html>

表2FewRel数据集样本设置案例

Tab.2Fewrel dataset sample setting case   

<html><body><table><tr><td>阶段</td><td>数据集</td><td>设置</td><td>案例</td></tr><tr><td rowspan="3">training phase</td><td rowspan="3">support set</td><td>(A)capitalof</td><td>Washington is the capital of the U.S.A.</td></tr><tr><td>(B)memberof</td><td>Leibniz was a member of the Prussian Academy of Sciences.</td></tr><tr><td>(A)or(B)</td><td>Newton served as the president of the Royal Society.</td></tr><tr><td rowspan="2">test phase</td><td rowspan="2">support set</td><td></td><td>(A)inheritancetypofHypdrotictoderaldpsiaisocomontyndisuallasmiedsax-lnkedait</td></tr><tr><td>(B)occurs in (A)or(B)</td><td>Congenital fxideficiency (hemophiliac)isarare bleeding disorderthathasbeendocumented mostly inashkenazi jews."</td></tr></table></body></html>

# 4.2实验验证

为了验证提出的ACNet模型在小样本RE任务中的有效性，并评估不同模块对网络的贡献，进行以下三组对比实验。

1）以原型网络(PROTO)为基线模型，与所提出的模型进行对比，为了保证实验的准确性，使用BERT替换PROTO中的编码模块。实验中的参数均保持一致，采用FewRel1.0的测试集，分别在5-way-k-shot和10-way-k-shot任务上进行实验，实验结果如图2所示。

图2(a)和(b)展示了5-way 和10-way 任务下，随着 shot数量增长两个模型准确率的变化曲线，其中灰色柱状图部分代表ACNet对比基线模型的提升效果。由图可知，在 $\scriptstyle { \mathrm { K } = 1 }$ 的极端小样本环境下，模型的提升效果最为明显，5-way任务中相比PROTO 性能提升 $7 . 8 3 \%$ ,10-way任务上提升 $6 . 2 7 \%$ 。PROTO通常需要一定数量的样本来确定同类样本的质心，并以此作为该类的原型向量，样本数量较少的情况下类原型难以准确反映类别特征，而在ACNet中记忆矩阵包含 $C _ { b a s e }$ 个类原型，模型在训练期间通过学习类原型的共性，实现样本由部分到整体的归纳。同时，记忆矩阵会在训练过程中对类原型向量进行更新，因此随着样本量的增加，依旧存在一定数量的性能提升。

![](images/d391286326a3d162f1405d56d171adffaf5d54e76d110988ce9589cf8ba18817.jpg)

与CapsNet不同，ACNet 通过引入的NAS函数来判断样本所需的路由迭代次数，图5记录了在10way-1shot任务设置下，达到NAS收敛标准时所需的路由迭代次数，图中的灰色和黑色水平线分别代表3次和5次的迭代次数设置，可以观察到不同类样本所需的迭代次数并不相同，最高需要9次路由迭代，最低则仅需要2次。数据多样性造成了收敛标准的差异，ACNet的优势在于针对不同样本的NAS分数，自适应调整路由迭代次数，在保证模型整体收敛的同时，满足在实例样本上的拟合标准，从而降低路由过程的不可控风险。

![](images/a4cb5a0eecd5b0f2fb822895a5e05280dfdc12df91656e3d3e60135e60ececef.jpg)  
图3两种不同路由迭代下CapsNet的loss 曲线 Fig.3Loss curve of capsnet under two different routing iterations

![](images/d23fc011e9b45640bdb00a0ed126fccbcfbddc8f3b2adbdf60626366cffacb0a.jpg)  
图4实例样本在不同路由次数下的NAS曲线

![](images/2294a0778c307f1c4ed4a24e578a178c5b426600a2f2e0d063d4d2469d560d78.jpg)  
(b)10-way-k-shot任务ACNet和PROTO准确率变化曲线图2ACNet和PROTO在5--ay 和10-way任务上的准确率 $. ( \% )$ 折线图Fig.2Accuracy(%)line chart ofacnet and PROTO on5-way and 10-way tasks2）以CapsNet为基线模型，将路由次数r设置为3和5,在FewRel1.0训练集中随机抽取5000个样本进行训练。图3记录了CapsNet在两种路由次数设置下的损失曲线，可以观察到两种配置下的CapsNet均达到了系统级收敛。图4反映了单个样本在不同路由次数下的NAS曲线，当 $\scriptstyle \mathbf { r } = 3$ 或5时NAS曲线仍成下降趋势，这证明预先设置的路由迭代次数虽然能够使模型满足系统级收敛，但却难以满足模型在实例级的收敛需求，这增加了路由过程的不确定性。  
Fig.4NAS curves of instance samples under different routing iterations   
图5ACNet在不同关系类下路由次数

Fig.5Routing iterations of acnet under different relationship classes3）以原型网络为基线模型，对比PROTO增加QEM模块前后和 ACNet 模型删除 QEM 模块前后的性能变化。PROTO在添加QEM模块后，将支持集样本和查询样本输入QEM模块中，以此获得每个类别的类特征。同时，ACNet在删除QEM后采用取平均的方式获得类特征，其余部分均保持不变。实验使用5-way-1-shot任务配置，并采用FewRel1.0测试集进行验证。

如表3所示，PROTO $^ { 1 + }$ QEM对比PROTO性能提升 $4 . 2 1 \%$ PROTO通过类内所有样本向量的加和平均获得类特征，当类内样本较少时，其向量分布存在偏差，无法准确代表样本类别，这进一步影响了查询样本的分类，造成准确率下降。ACNet-QEM对比ACNet精度下降 $2 . 0 7 \%$ ，这证明QEM具有比PROTO更强的样本归纳能力，尽管PROTO $^ +$ QEM采用QEM 模块获取类特征，但ACNet-QEM的性能依旧强于PROTO+QEM，上升幅度在 $13 \%$ 左右，这证明类特征的编码方式并不是左右性能的唯一指标，本文认为AIM模块对结果的影响更加明显，AIM旨在使用记忆矩阵对支持集向量进行调整，记忆矩阵的引入使得ACNet在不同元任务间切换时有效保留学习经验，模块自适应的特性也更加契合小样本学习，实验证明了AIM和QEM的有效性。

Tab.3Accuracy rate of different models under 5-way-1-shot task $1 \%$   

<html><body><table><tr><td>序号</td><td>模型</td><td>5 way-1 shot</td></tr><tr><td>1</td><td>PROTO</td><td>69.20</td></tr><tr><td>2</td><td>PROTO+QEM</td><td>73.41</td></tr><tr><td>3</td><td>ACNet-QEM</td><td>86.44</td></tr><tr><td>4</td><td>(AIM+QEM)ACNet</td><td>88.51</td></tr></table></body></html>

# 4.3模型比较

4.2节验证了ACNet中不同模块的作用，为了进一步检查ACNet的整体模型表现，本文对比了近几年几种常用的小样本基准模型，其中包括：

Meta-Net，MunkhdalaiT等人[8]于2017年提出元网络模型，Meta-Net包含基学习器和带有记忆模块的元学习器两部分，通过两部分的交互驱动模型理解非目标任务空间，减少模型对样本数量的需求。

GNN，GarciaV等人[22]于2017年提出的小样本图卷积网络模型，GNN将每个支持实例或查询实例视为图中的一个节点，并将其标签信息嵌入到节点表示中，依靠图卷积将基类别的分类器信息传递给新类别的分类器中，实现小样本的标签传播。

SNAIL，Mishra等人[23]于2018年提出的一种元学习框架，SNAIL将时序卷积网络和注意力机制相结合，利用时序卷积从已有经验中挑选特定信息特征，并通过注意力机制完成信息聚合，达到快速学习小样本任务的目的。

PROTO，Snell等人[10]于2017年提出原型网络，PROTO通过平均支持样本获得样本的类别中心，并将新样本与类别中心进行距离度量，以此实现少量样本下的分类任务。

BERT-PAIR，TianyuGao 等人[20]于 2019 年提出一种序列匹配模型，BERT-PAIR将每个查询实例与所有支持实例进行配对，并将每个实例对连接为序列输入到BERT模型中，获得表示同类实例的概率。

DBIN，RuiyingGeng等人[24]于2020 年提出动态内存引导网络，DBIN将内存模块和动态路由算法相结合，模型通过调整和聚合两个步骤在少量支持样本中获得类别表示，最后与查询样本比较完成关系分类。

实验结果如表4所示，其中Meta-Net、GNN、SNAIL、PROTO(CNN)等网络模型使用CNN进行编码，输入关系样本语句，并将每个单词表示转换为单词嵌入和位置嵌入的整合，整个关系实例表示作为输入向量。在CNN中输入向量经过卷积层、最大池化层和非线性激活层得到最终的语句嵌入。除了使用CNN编码结构外，PROTO(BERT)、BERT-PAIR、DMIN以及本文提出的ACNet模型均采用BERT作为编码器。从表一中可以看出PROTO(BERT)对比PROTO(CNN)存在显著的性能提升，在FewRel1.0数据集的4个任务上平均提升幅度为 $4 . 7 2 \%$ ，在FewRel2.0数据集上，平均的性能提升幅度为 $3 . 0 9 \%$ ，这证明BERT编码结构所生成的语句特征更加丰富，能够有效应对小样本任务。

同时，对比FewRel1.0数据集，所有的模型在FewRel2.0数据集上都存在性能大幅降低的现象，FewRel2.0的测试集来自生物医学领域，这说明小样本模型难以快速适应跨领域样本，模型的经验迁移能力还存在较大的提升空间。

表35-way-1-shot任务下不同模型的准确率  
表4不同模型在四个小样本任务设置上的对比  
Tab.4Comparison of different models in four few-shot task settings   

<html><body><table><tr><td rowspan="2">模型</td><td colspan="2">5-way-1-shot</td><td colspan="2">5-way-5-shot</td><td colspan="2">10-way-1-shot</td><td colspan="2">10-way-5-shot</td></tr><tr><td>On 1.0</td><td>On 2.0</td><td>On 1.0</td><td>On 2.0</td><td>On 1.0</td><td>On 2.0</td><td>On 1.0</td><td>On 2.0</td></tr><tr><td>Meta-Net (CNN)</td><td>64.46</td><td></td><td>80.57</td><td>-</td><td>53.96</td><td>-</td><td>69.23</td><td>-</td></tr><tr><td>GNN(CNN)</td><td>66.23</td><td>27.94</td><td>81.28</td><td>29.33</td><td>46.27</td><td>16.44</td><td>64.02</td><td>18.26</td></tr><tr><td>SNAIL(CNN)</td><td>66.79</td><td>26.22</td><td>79.04</td><td>30.28</td><td>45.73</td><td>16.21</td><td>68.33</td><td>19.36</td></tr><tr><td>PROTO(CNN)</td><td>74.52</td><td>35.09</td><td>88.40</td><td>49.37</td><td>62.38</td><td>22.98</td><td>80.45</td><td>35.22</td></tr><tr><td>PROTO(BERT)</td><td>80.68</td><td>40.12</td><td>89.60</td><td>51.50</td><td>71.48</td><td>26.45</td><td>82.89</td><td>36.93</td></tr><tr><td>DMIN</td><td>85.14</td><td>49.62</td><td>92.37</td><td>53.76</td><td>76.56</td><td>40.78</td><td>86.75</td><td>47.49</td></tr><tr><td>BERT-PAIR</td><td>88.32</td><td>56.25</td><td>93.22</td><td>67.44</td><td>80.63</td><td>43.64</td><td>87.02</td><td>53.17</td></tr><tr><td>ACNet</td><td>88.51</td><td>58.44</td><td>93.49</td><td>66.53</td><td>81.22</td><td>45.74</td><td>87.32</td><td>52.24</td></tr></table></body></html>

在FewRel1.0数据集上，本文提出的ACNet模型优于目前最优的BERT-PAIR模型，在FewRel2.0的两种one-shot任务上，对比BERT-PAIR也分别取得了 $2 . 1 9 \%$ 和 $2 . 1 \%$ 的提升，而在其他的两种5-shot任务上，ACNet也达到了与BERT-PAIR相似的性能。BERT-PAIR是一种基于匹配的小样本方法，通过计算查询集与支持集的匹配程度完成分类，但鉴于样本的特征多样性，同类样本的分布差异较大时会导致模型性能下降，而ACNet对支持集样本采用先调整后聚合的方式，SIA针对每个样本进行路由评估，调整后的样本能够有效减少类内分布差异，自适应的特性使样本在实例级别上获得收敛，因此面对跨领域的样本，ACNet仍具有一定的优势。

综合本节中的实验结果，本文提出的ACNet模型在FewRe1数据集的多数任务上都优于目前模型，实验验证了本文方法的有效性，同时也说明类特征建模的方法在小样本任务中的优势。

# 5 结束语

本文提出了一种自适应胶囊网络(ACNet)，并将其应用在小样本关系分类中。ACNet利用记忆矩阵帮助模型归纳类表示，并通过自适应归纳算法完成对支持集向量自适应调整，使模型能够发现新的未知类。在FewRel数据集上，与当前五个代表性模型相比，在FewRel1.0的4中小样本任务上取得了最好的结果，而在FewRel2.0的两种10-way任务上具有与目前最优模型BEER-PAIR的相似性能。目前ACNet还存在模型结构复杂，训练时间长等问题，在未来的工作中，本文将进一步研究模型规模对小样本关系抽取任务的影响，探索精简模型结构的可能。

# 参考文献：

[1]杨穗珠，刘艳霞，张凯文，等．远程监督关系抽取综述[J].计算机 学报,2021,44(08):1636-1660.   
[2]刘洋．神经机器翻译前沿进展[J].计算机研究与发展,2017,54(06): 1144-1149.   
[3]付雷杰，曹岩，白璃，等．国内垂直领域知识图谱发展现状与展望 [J]．计算机应用研究,2021.   
[4]Han Xu,Gao Tianyu,Lin Yankai,et al.“More Data,More Relations, More Context and More Openness:AReview and Outlook forRelation Extraction.”[C]//Proceedings of the 1st Conference of the Asia-Pacific Chapter of the Association for Computational Linguistics and the 10th International Joint Conference on Natural Language Processing,2020: 745-758.   
[5]Salamon J,Bello J.Deep convolutional neural networks and data augmentation for environmental sound classification [J]. IEEE Signal processing letters,2017,24(3):279-283.   
[6]Huisman M,VanRijn J,Plaat A.A survey of deep meta-learning [J]. Artificial Intelligence Review,2021,54 (6): 4483-4541.   
[7]Qu M,Gao T,Xhonneux L P,et al. Few-shot relation extraction via bayesian meta-learning on relation graphs [C]// International Conference on Machine Learning.PMLR,2020:7867-7876.   
[8]Munkhdalai T,Yu Hang.Meta networks.[C]// In ICML'17 Proceedings of the 34th International Conference on Machine Learning-Volume 70, 2017: 2554-2563.   
[9]Qi Hang,Brown M,Lowe D.Low-Shot Learning with Imprinted Weights. [C]//In 2018 IEEE/CVF Conference on Computer Vision and Pattern Recognition,2018: 5822-5830.   
[10] Snell J,Swersky K,Zemel R.Prototypical Networks for Few-Shot Learning [J]. In Advances in Neural Information Processing Systems, 2017,30:4077-87.   
[11] Sung F,Yang Yongxin, Zhang Li,et al.Learning to compare: Relation network for few-shot learning [C]//Proceedings of the IEEE conference on computer vision and pattern recognition.2018:1199-1208.   
[12] Sabour S,Frosst N, Hinton G.Dynamic Routing Between Capsules [J]. In Advances in Neural Information Processing Systems,2017,30:3856- 66.   
[13] Devlin J,Chang Mingwei,Lee K,et al.Bert: Pre-training of deep bidirectional transformers for language understanding [J].arXiv preprint arXiv:1810.04805,2018.   
[14] VaswaniA,ShazeerN,ParmarN et al.Attention Is All You Need.[C]// In Proceedings of the 31st International Conference on Neural Information Processing Systems,2017,30: 5998-6008.   
[15] Yang Zhengxin,Zhang Jinchao,Meng Fandong,et al.Enhancing Context Modeling with a Query-Guided Capsule Network for DocumentLevel Translation.[C]// In Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing and the 9th International Joint Conference on Natural Language Processing (EMNLP-IJCNLP),2019:1527-37.   
[16] Jones M,Keynes M.On kernel density derivative estimation [J]. Communications in Statistics-Theory and Methods,1994,23 (8):2133- 2139.   
[17] Comaniciu D,Meer P.Mean Shift:A Robust Approach toward Feature Space Analysis.[C]//IEEE Transactions on Pattern Analysis and Machine Intelligence.2002,24(5): 603-19.   
[18] Vinyals O,Blundell C,Lillicrap T,et al.Matching networks for one shot learning [J].Advances in neural information processing systems,2016, 29:3630-3638.   
[19] Han Xu, Zhu Hao,Yu Pengfei,et al. FewRel: A large-scale supervised few-shot relation classification dataset with state-of-the-art evaluation [J].arXiv preprint arXiv:1810.10147,2018.   
[20] Gao Tianyu,Han Xu,Zhu Hao,et al.FewRel 2.O:Towards more challenging few-shot relation classification [J].arXiv preprint arXiv: 1910.07124,2019.   
[21] Hendrickx I, Kim S,Kozareva Z,et al. SemEval-2010 Task 8: Multi-Way Classification of Semantic Relations between Pairs ofNominals.[C]//In Proceedings of the 5th International Workshop on Semantic Evaluation, 2010:33-38.   
[22] Garcia V,Bruna J.Few-shot learning with graph neural networks [J]. arXiv preprint arXiv:1711. 04043,2017.   
[23] MishraN,RohaninejadM,Chen Xi,et al.A simple neural attentive metalearner[J].arXiv preprint arXiv:1707.03141,2017.   
[24] Geng Ruiying,Li Binhua,Li Yongbin,et al. Dynamic memory induction networks for few-shot text classification[J].arXiv preprint arXiv:2005. 05727 (2020).