# 融合命题逻辑与神经网络的隐式深度协同推荐模型

陈邦1,2，吴茂念1,2′，朱绍军1,2，郑博1,2，彭蔚1,2(1.湖州师范学院 信息工程学院，浙江 湖州 313000;2.浙江省现代农业资源智慧管理与应用研究重点实验室，浙江湖州 313000)

摘要：以增强推荐算法模型认知推理能力，克服传统推荐算法高度依赖数据质量致使性能受限的现状为目标，提出一种将命题逻辑与神经网络融合的隐式深度协同推荐模型。首先，构建一个隐式逻辑表征模块，辅助联结实际问题中复杂变量与逻辑变量的隔阂，并将推荐问题转换为一个逻辑表达式。随后，利用神经网络拟合逻辑符号对逻辑表达式进行求解并完成推荐。在具有不同特点的三个经典数据集 MovieLens、Book-Crossing、Amazon-E上的实验表明提出的方法展现了更好的推荐性能。

关键词：推荐系统；协同过滤；神经网络；认知推理 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.02.0064

Implicit deep collaborative recommendation model based on propositional logic and neural network

Chen Bang1,2, Wu Maonian1,2†, Zhu Shaojun1,2, Zheng Bo1,2,Peng Wei1,2 (1.SchoolofInformation Enginering,Huzhou University,Huzhou Zhejiang 3130oo,China;2.ZhejiangProvince Key Laboratory ofSmartManagement &ApplicationofModernAgricultural Resources,Huzhou Zhejiang 3130o0,China)

Abstract: Withthe goalofenhancing thecognitivereasoning abilityoftherecommendationalgorithm model andovercoming theperformance limitationof te traditionalrecommendationalgorithmwhichis highlydependentonthedataquality,resent a deep collaborativerecommendation model which fusion of propositional logic and neural networks.First,buildingan implicit logic representation module to linking complex variables in real-world problemswith logical variables，and transformingtherecommendationproblem intoalogicalexpresion.SubsequentlyUsing neural networkstofitlogical symbols tosolvelogical expresionsandcompleterecommendations.Experimentsonthree classicaldatasets withdifferent characteristics,MovieLens,Book-Crossing,ndAmazon-E,showthat themodelinthispaperexhibitsbettrrecommedation performance.

Key words: recommendation system ; collaborative filtering; neural network ; cognitive reasoning

# 0 引言

近年来，高速发展的互联网及快速升级的移动设备给社会带来了丰富多彩的生活方式，如电子商务、新零售的进一步发展为人们提供大量生活方式及工作选择，但爆发式增长的信息和数据也使用户面临着难以从千方甚至上亿产品中捕捉潜在感兴趣商品的问题。推荐系统能够快速将用户与其最相关的商品进行匹配，有效节省用户购买时间并提升用户的体验感，已成为相关领域的研究热点[1。推荐系统主要有协同过滤推荐、基于内容的推荐、基于关联规则推荐等方法。目前的主流推荐方法多以协同过滤思想为基础进行改良与优化，即根据用户历史交互预测未来[2]。经典协同过滤方法以矩阵分解为代表[3]，随着深度学习的快速发展和广泛应用，利用深层模型对大规模数据进行学习以拟合匹配函数成为研究热点之一[4]。

然而，越来越多的学者发现推荐问题并非仅凭对交互历史进行统计归纳就能完美解决[5\~7]。例如，一位近期购买过电脑的用户不会再需要同类产品的推荐，而是需要键盘、鼠标等外设产品。总体来说，用户常常刚买完商品就被推荐相似商品，但实际需求已经消失。因此，仅凭对用户交互历史进行归纳统计以推断其未来意向很难达到理想效果。其次，基于统计匹配的方式在面对过于稀疏的数据集时将很难学习到足够的用户-商品特征对。这主要是因为商品与用户的可能组合总是伴随数据集增长呈指数级别增加，而经典的神经网络模型缺乏举一反三的推理能力，模型效果严重依赖于数据集优劣。相应的，尽管传统的逻辑系统擅于解决需要推理的问题，但基于硬规则的逻辑方法往往缺乏泛化性，导致在解决实际问题时无法很好的容纳内部冲突。例如，有着相同历史交互的用户也许会作出截然不同的决策，即同样的逻辑表达式也许有不同的解。由此不难看出，融合逻辑推理与神经网络以构建兼具推理能力与良好泛化能力的模型必然是研究者未来关注的焦点[]。

最近，Shi 等[8提出一种新颖思想，将推荐问题转换为一个逻辑表达式进行求解，以构建一种具有推理能力的推荐预测模型。类似的工作还有Chen 等[9,l0]与Fan 等[1]。然而，方法中的逻辑表达式仅考虑变量间的一阶关系，且串联求解会带来靠前单位的信息丢失问题。因此，本文在将推荐问题转换为逻辑表达式进行求解的基础上，于商品嵌入与逻辑求解间增加一个隐式逻辑表征模块，提出一种隐式深度协同推理模型。

与已有工作相比，本文模型的创新点为：a)本文将交互逻辑表达式中的变量视为一个序列，利用多层自注意力机制挖掘各变量间的隐性交互关系，缓解仅考虑一阶逻辑关系导致的表征信息不足问题。b)利用门控循环网络模块改善逻辑表达式串联求解过程中靠前变量的信息丢失问题。在MovieLens、Book-Crossing、Amazon-E数据集的实验结果表明，本文给出的模型在NDCG与HIT指标上要优于其他比较算法。

# 1 相关工作

# 1.1基于深度模型的协同过滤推荐

协同过滤是一种常见且主流的推荐方法[12]，传统的协同过滤方法都以匹配思想为基础，通过学习匹配函数实现推荐。最早的矩阵分解技术将用户-商品交互矩阵分解为两个或多个矩阵的乘积，以表征用户与商品间的关系[13]。当前，研究学者优化协同过滤模型主要有两种途径，一种是以优化嵌入为目标。例如，Gediminas等[4]通过上下文预过滤建模表征用户特征，Alexandros等[15]使用更高维的张量代替分解矩阵，通过维度的提升进一步丰富嵌入信息，Yehuda[16将动态的时间信息与用户行为加入到嵌入中进行学习。同时，部分学者在表征中集成更丰富的信息结构。例如，Zhang 等[17]使用图像、评级等信息联合表征用户嵌入，He等[18]直接从产品图像中提取视觉特征，并作为一项独立的指标影响模型决策，Ai等[19]借助知识图谱辅助构建推荐模型并优化嵌入学习。另一种优化方向是通过寻找更好的匹配函数构建协同过滤推荐模型，例如，Hsieh 等[20]使用向量转换代替内积并在联合空间中度量用户偏好。随着深度学习在图像、语言等领域展现出强大效果，越来越多的学者倾向于使用复杂的神经网络来学习匹配。如Ruslan 等[2I]首次提出了一种RBM模型将深度学习与协同过滤相结合，并在电影数据集上取得良好效果。类似的工作还有He[22]提出的神经协同过滤模型(neuralcollaborative filtering，NCF)和Travis等[23]提出的协同记忆网络模型(collaborative memory network，CMN)。上述方法均使用更丰富的先验知识或更复杂的内核模型提升推荐效果，但在面对需要推理能力的任务时，基于归纳统计的方式难以逾越从感知到认知的鸿沟。因此，必须将归纳统计与推理演绎的思想进行融合，以应对需要一定推理能力的复杂推荐任务。

# 1.2神经符号集成

作为人工智能领域中最经典的范式，符号主义将符号作为设定硬规则的媒介赋予AI认知智能。神经符号集成是一个将经典符号知识与神经网络相结合的领域，使模型能同时提供良好计算能力与逻辑推理能力。深度学习则被视为一个有希望克服符号与亚符号之间缝隙的方式[24\~26]。近年来，已有不少学者试图用深度学习的方法解决逻辑问题，例如Johnson等[27]和Yi等[28]设计了一种深度网络模型来生成程序并进行视觉推理。Yang等[29]提出了一种基于一阶逻辑的知识库神经逻辑推理系统。Dong 等[30]构建了一种用于关系推理及决策的神经逻辑模型。然而，以上工作均预设一种单一架构来处理不同的逻辑输入，虽然在面对特异性问题时展现出良好表现，但在面对需要泛化能力的复杂数据集时灵活性略显不足。为使推理模型保有更好的泛化性能，Shi等[8提出了逻辑集成网络(Logic-Integrated Neural Network,LINN)，将基本的逻辑符号视为神经网络进行拟合学习以作为神经网络与符号主义之间的良好媒介。但忽视了不同类型任务转换为逻辑问题后变量之间的隐式关系，同时根据逻辑表达式构造模型计算图的方式会导致前端逻辑单元信息丢失。本文以推荐系统为目标，设计一个由自注意力机制与门控循环网络结合而成的隐式逻辑表征模块，完善命题逻辑与神经网络融合过程中产生的问题。

# 2 方法

# 2.1方法概述

增强模型的认知推理能力是解决复杂推荐问题的有效手段之一。本文将推荐问题转换为逻辑表达式进行求解，提出一种融合命题逻辑与神经网络的隐式深度协同推理算法(implicitdeepcollaborative reasoning,IDCR)。模型主要由基于自注意力与门控循环单元的隐式逻辑表征模块和基于逻辑符号与BP神经网络集成的深度推理模块组成。首先，利用隐式逻辑表征模块从用户历史交互中挖掘商品间的隐式逻辑信息并生成隐式逻辑变量，随后，经由深度推理模块对隐式逻辑变量构成的逻辑表达式进行求解并作推荐预测。

模型主要由四个部分组成，分别是输入层、隐式逻辑表征模块、深度推理层以及输出层。下文将对模型的各个模块进行详细阐述。

# 2.2输入层

输入层将数据转换为模型所需的输入结构，原始数据集由一系列用户与商品的交互评分构成，主要包括用户的ID集合 $\scriptstyle \mathrm { U = \{ u 1 , u 2 , u 3 , \dots , u _ { i } \} }$ ，商品的ID集合 $\mathrm { V = \{ v 1 , v 2 , v 3 , \ldots , v j \} }$ 以及评分矩阵 $\mathrm { Y _ { i \times j } }$ 组成。由于模型将推荐问题转换为逻辑表达式进行求解，因此需要将评分转换为0和1，以5分制为例，大于等于4的评分被视为1，代表用户与商品产生正交互，小于4的评分被视为0，即用户与商品产生负交互。

随后，将所有用户-商品交互按时间排序并组成序列，每一个序列包含用户 $\mathrm { \ u _ { i } }$ 、商品 $\mathbf { v } _ { \mathrm { j } }$ 、用户对商品的评分 $\mathbf { y } _ { \mathrm { i j } }$ 以及在该条交互前的 $\mathrm { ~ m ~ }$ 个交互商品组 $\mathrm { H = \{ h _ { 1 } , h _ { 2 } , h _ { 3 } , . . . , h _ { m } \} }$ 。最后，为防止整数编码方式导致商品与用户之间产生错误的次序关系！使用一个EmbeddingLayer(嵌入层)将所有的整数编码映射到高维空间以得到特征向量。

# 2.3深度推理层

为了更好的引出隐式逻辑表征模块，本文首先介绍用于求解逻辑表达式的深度推理层，其输入是由逻辑变量与三个基本逻辑符号 $( \land , \lor , \lnot )$ 构成的逻辑表达式，输出为解向量。同时，基本的逻辑符号被视为三个独立的神经网络进行训练。

为便于理解，假设输入层处理后的数据直接进入到深度推理层中。输入包含目标用户 $\mathrm { ~ u ~ }$ ，目标商品 $\mathbf { v } _ { \mathrm { t } }$ ，交互评分 $\mathrm { y } _ { \mathrm { t } }$ 以及其之前交互的三个商品 $\mathbf { v } _ { 1 } , \mathbf { v } _ { 2 } , \mathbf { v } _ { 3 }$ （假定 $\mathrm { m } { = } 3$ )。于是，当用户在给予商品 $\mathbf { v } _ { 1 } , \mathbf { v } _ { 2 } , \mathbf { v } _ { \mathrm { t } }$ 正面评价，而给予商品 $\mathbf { v } _ { 3 }$ 负面评价后，可将其转换为一个逻辑表达式：

$$
( \nu _ { 1 } \wedge \nu _ { t } ) \vee ( \nu _ { 2 } \wedge \nu _ { t } ) \vee ( \nu _ { 3 } \wedge \nu _ { t } ) = T
$$

式(1)代表用户 $\mathrm { ~  ~ u ~ }$ 与 $\mathbf { v } _ { \mathrm { t } }$ 产生正交互的原因既可能与 $\mathbf { v } _ { 1 }$ 相关，也可能与 $\mathbf { v } _ { 2 }$ 或 $\mathbf { v } _ { 3 }$ 相关，每一个合取子式都是独立的，这将鼓励模型滤出不同的特征解，显著降低模型耦合性。

将历史交互转换为逻辑表达式后，推荐问题就被转换为一个逻辑表达式的求解问题。为了将符号逻辑与神经网络的优点结合起来，本文将三个基本逻辑符号视为三个可学习的神经网络 $\mathrm { A N D } ( \cdot , \cdot )$ ， $\mathrm { O R } ( \cdot , \cdot )$ ， $\mathrm { N O T ( \cdot ) }$ 。该做法得益于模型能自发的从数据中学习并理解逻辑推理规则，举例而言，在一维空间中0和1代表正与负，也就是说 $\mathrm { { N O T } } ( 1 ) = 0$ ；在二维空间中，任意向量 $\mathbf { v }$ 都仅存在一条与其相似度为0的向量-v代表NOT(V)；当维度达到三维即以上时，对于任意向量，与其相似度为0的向量将不再唯一。换言之，仅使用经典逻辑系统难以表达高维向量之间的逻辑关系，因此需要引入神经网络来拟合不同空间中的复杂逻辑关系。假设所有向量的维度都为d，则 $\mathrm { A N D } ( \cdot , \cdot )$ 与 $\mathrm { O R } ( \cdot , \cdot )$ 网络的输入为两个维度为d的向量，输出为一个维度为d的向量， $\operatorname { N O T } ( \cdot )$ 网络输入为一个维度为d的向量，输出也为一个维度为d的向量。本文的三个网络均采用单隐藏层的全连接神经网络结构，以 $\mathrm { \Delta N O T ( \cdot ) }$ 网络为例，其公式为

$$
\mathrm { N O T } ( \nu _ { t } ) = b + \sum _ { i } c _ { i } \sigma ( b _ { i } + \sum _ { j } w _ { i j } \nu _ { t } )
$$

其中 $_ { \infty }$ 为激活函数，本文使用的激活函数均为ReLU。

举例来说， $\mathrm { A N D } ( \nu _ { I } , \nu _ { t } )$ 的输出代表 $\mathbf { v } 1 \wedge \mathbf { v } \mathbf { t }$ 的结果， $ { \mathrm { N O T } } ( \nu _ { 3 } )$ 则代表 $\lnot _ { \mathbf { V } 3 }$ 。因此，式(1)在模型中的求解流程如图1所示。

![](images/d79bb6501498fea75bf12f219f5cf491989d105f28cdc47ee51fb30ac4f2da0d.jpg)  
图1式(1)在模型中的求解过程

值得注意的是，模型只取变量之间的一阶关系，这是由于高阶关系在变量个数增加时会呈指数增长，这将带来大量计算需求与模型过拟合的问题。

最后，将模型的输出向量与随机初始化的基准向量T求相似度得到表达式的解，相似度公式为

$$
\mathrm { S i m } ( \nu _ { o } , T ) = s i g m o i d ( \varphi \frac { \nu _ { o } \cdot T } { \left\| \nu _ { o } \right\| \times \left\| T \right\| } )
$$

其中: $\phi$ 为超参数，通过缩放相似度大小使模型能适配不同领域的数据集。相似度越接近1代表用户对该商品的预期评价越倾向正面。

# 2.4隐式逻辑表征

深度推理模型在实际应用中会产生两个问题，首先，逻辑表达式求解析取范式的过程是串联进行的，这将导致靠前的逻辑单位信息不断丢失，而靠后的逻辑单位则不可避免地对最终结果产生更大影响。其次，在前文中只保留变量间一阶逻辑关系的做法虽然能够精简模型，但也在一定程度上导致了逻辑变量间隐式信息的丢失。当面对以推荐任务为代表的实际问题时，不同变量间总是存在复杂的隐性关系，例如不同电影有上下部关系，不同商品也许从属于同一品牌或同一类目，这些隐式信息都会对推荐结果产生影响。但在深度推理模块中，每样商品都被表示为独立的逻辑变量。以2.2节中的假设为例，模型忽视了历史交互商品 $\mathbf { v } _ { 1 } , \mathbf { v } _ { 2 } , \mathbf { v } _ { 3 }$ 之间的二阶与三阶关系：

$$
( \nu _ { 1 } \wedge \nu _ { 2 } \wedge \nu _ { t } ) \vee ( \nu _ { 1 } \wedge \neg \nu _ { 3 } \wedge \nu _ { t } ) \vee ( \nu _ { 1 } \wedge \nu _ { 2 } \wedge \neg \nu _ { 3 } \wedge \nu _ { t } ) = T
$$

简而言之，当不考虑变量间的高阶关系时，也就主动舍弃了 $\mathbf { v } _ { 1 } , \mathbf { v } _ { 2 } , \mathbf { v } _ { 3 }$ 之间的隐式信息，这样的做法显然会对模型性能造成影响。

因此，需要针对上述深度推理模型的两个问题构造一个隐式逻辑表征模块，首先，借助自注意力机制(Self-Attention)来挖掘不同逻辑变量之间的隐式关系，解决忽略高阶关系带来的问题。其次，增加一个门控循环单元层(GatedRecurrentUnit,GRU)解决串联执行析取范式产生的信息丢失问题。隐式逻辑表征模块的具体结构如图2所示。

首先，Attention模块将代表商品的逻辑变量视作一个输入序列，通过学习各逻辑变量之间的相关权重来挖掘不同商品间的隐式交互信息。该计算过程主要由query、key、value三个部分组成，通过线性投影的方式得到 $\varrho$ ， $\pmb { K }$ ， $\nu$ 三个向量，将 $\varrho$ 与 $\pmb { K }$ 向量点乘得到相似度矩阵，相似度公式为

$$
f ( \pmb { \mathscr { Q } } , K _ { i } ) { = } \pmb { \mathscr { Q } } ^ { T } K _ { i }
$$

随后对相似度矩阵归一化得到关于向量 $\mathrm { ~ v ~ }$ 的权重分布，并点乘计算向量 $\mathrm { \Delta V }$ 的加权值，计算公式为

$$
{ \mathrm { A t t e n t i o n } } ( Q , K , V ) = { \mathrm { s o f t m a x } } \left( { \frac { f ( Q , K _ { i } ) } { \sqrt { d _ { k } } } } \right)
$$

为挖掘不同子空间中各逻辑变量间的复杂关系，需要引入多头注意力机制，在多个不同的投影空间中捕捉不同的交互信息并有效防止模型陷入局部最优陷阱，公式如下，其中$\pmb { W }$ 为可学习的参数矩阵。

$$
h e a d _ { i } = A t t e n t i o n ( \mathcal { Q } , K , V ) _ { i } V _ { i }
$$

$$
M H e a d = c o n c a t ( h e a d _ { 1 } , h e a d _ { 2 } . . . h e a d _ { i } ) W
$$

通过自注意力模块，可以得到包含各变量间高阶隐式交互信息的隐式逻辑变量 $\textit { \textbf { a } } _ { I }$ ， $\scriptstyle a _ { 2 }$ ， $\scriptstyle a _ { 3 }$ 。随后，利用门控循环网络进一步优化模型，解决深度推理模型中串联计算方式带来的信息丢失问题。

![](images/7ad0e270b3408515d588b3260d22927922c3e5c0957b927263bd976ef96eefb4.jpg)  
Fig.1Solution process of Formula(1) in the model   
图2隐式逻辑表征模块结构  
Fig.2Implicit logic representation module structure

门控循环网络内部结构展示在图3上方，主要由两个重要单元构成，分别是更新门 $\mathbf { \sigma } _ { Z \mathrm { { t } } }$ 与重置门 $\mathbf { r } _ { \mathrm { t } }$ ，更新门用于控制前一逻辑变量的状态信息被带入当前信息中的程度，重置门则控制前一状态有多少信息被写入当前的候选隐状态 $ { \mathrm { \ h } } _ { \mathrm { t } } ^ { \sim }$ 中，计算公式如下，其中 $[ \cdot ]$ 表示向量拼接：

$$
r _ { t } = \sigma ( W _ { r } \bullet [ h _ { t - I } , x _ { t } ] )
$$

$$
z _ { t } = \sigma ( W _ { z } \bullet [ h _ { t - 1 } , x _ { t } ] )
$$

$$
h = t a n h ( W _ { h } \bullet [ r _ { t } * h _ { t - 1 } , x _ { t } ] )
$$

$$
h _ { t } = ( 1 - z _ { t } ) * h _ { t - 1 } + z _ { t } * h _ { t }
$$

$$
y _ { t } = \sigma ( W _ { 0 } \bullet h _ { t } )
$$

通过门控循环网络，模型可以自发的学习并控制对表达式不同位置变量信息的取舍，有效改善深度推理模型中逻辑表达式前端变量信息丢失的问题。最后，将通过隐式逻辑表征模块得到的隐式逻辑变量视为一个逻辑表达式并作为深度推理模型的输入。

# 2.5 输出层

深度推理层根据输入的逻辑表达式进行计算后会输出一个d维解向量，将该向量与基准向量 ${ \bf T }$ 经过式(3)计算后得到介于0-1之间的数值即代表用户对目标商品的预期倾向。该数值越接近1则用户对该商品的预期评价越正面，在推荐任务中，预期评价越正面的商品在推荐序列中排名越靠前。

最后，算法1给出了IDCR模型的具体实现。

算法1 IDCR 算法

输入：历史交互序列 $\mathsf { V } \{ \mathsf { v } _ { 1 } , \mathsf { v } _ { 2 } , . . . \mathsf { v } _ { \mathsf { n } } \}$ ，评分序列 $\mathsf { S } \{ \mathsf { s } _ { 1 } , \mathsf { s } _ { 2 } , . . . \mathsf { s } _ { \mathsf { n } } \}$ ，目标 $\mathsf { v } _ { \mathtt { t } }$ 0

输出：用户对 $\mathsf { v } _ { \mathrm { t } }$ 的预期倾向 $\textsf { P }$ 。

1．初始化：AND()，OR()，NOT()是三个全连接神经网络模块，att()是Attention 模块，gru()是GRU 模块，embedding()是嵌入向量模块

2. $\textsf { x } \gets$ embedding(v)   
3. Xe← gru(att(X))   
4. $\mathsf { X } _ { \mathsf { n o t } } \gets \mathsf { N O T } ( \mathsf { X } _ { \mathsf { e } } ) ^ { * } \big ( 1 - { \mathsf { S } } \big ) + \mathsf { X } _ { \mathsf { e } } { } ^ { * } { \mathsf { S } }$   
5. Xor←Xnot[0]   
6. FOR( $\scriptstyle \mathbf { i } = 1$ ;i<=length(Xnot);i++）D0   
7. $\mathsf { X } _ { \mathsf { o r } } \gets 0 \mathsf { R } ( \mathsf { X } _ { \mathsf { o r } } , \mathsf { X } _ { \mathsf { n o t } } [ \dot { \bf { i } } ] )$   
8. ENDFOR   
9. Xand ← AND(Xor，embedding $( \mathsf { v } _ { \mathrm { t } } )$ ）   
10. $\mathsf { P  } \mathsf { S i m }$ C $\cdot \mathsf { X } _ { \mathsf { a n d } }$ ，T)//Sim为式(3)   
11．Return P

下面给出具体实现案例：首先，与同一用户交互的 $\mathrm { ~  ~ N ~ }$ 个商品根据交互时间排序并组成序列 $V \{ \nu _ { I } , \nu _ { 2 } , . . . , \nu _ { n } \}$ ，第 $_ { \mathrm { N + 1 } }$ 个商品则作为预测商品 $\nu _ { t }$ ，随后，将序列 $V$ 的每个变量嵌入生成高维向量(算法第 2行)，并将这一组向量输入自注意力模块与门控循环网络并生成一组隐式逻辑变量(第3行).接着，将这一组隐式逻辑变量视作一个逻辑表达式经由逻辑符号网络求解得到解向量(第4-9行)。最后，将该解向量与随机生成的基准向量T经由式(3)得到该逻辑表达式的解值，并作为用户对目标商品的预测评分(第10 行)。

# 3 实验与分析

# 3.1实验数据

本文利用三个具有代表性的公开数据集MovieLens、Book-Crossing、Amazon-E检验新建模型IDCR的推荐效果。

a)MovieLens[31]：由Grouplens 建立并维护的电影推荐数据集，是推荐领域的常用数据集。它数据密度较高，包含 $9 0 0 +$ 个用户对 $1 0 0 0 +$ 部电影发表的十万条评分数据。

b)Book-Crossing[32]：由 Book-Crossing 社区二十四万阅读者对图书评分构成的图书推荐数据集。它非常稀疏，对基于统计特征的深度学习方法具有很大的挑战。

c)Amazon-E[33]：由亚马逊用户网上购物评分构成的电子商务推荐数据集。它密度适中，数据量非常大。

数据集基本情况如表1所示。

表1实验数据集基本情况  

<html><body><table><tr><td>Dataset</td><td>#User</td><td>#Item</td><td>#Positive</td><td>#Negative</td><td>Density</td></tr><tr><td>MovieLens</td><td>943</td><td>1682</td><td>55,375</td><td>44,625</td><td>6.3%</td></tr><tr><td>Book-Crossing</td><td>242,158</td><td>313,316</td><td>364,037</td><td>635,763</td><td>0.013%</td></tr><tr><td>Amazon-E</td><td>192,403</td><td>63,001</td><td>1,356,067</td><td>333,121</td><td>0.014%</td></tr></table></body></html>

# 3.2评价指标

采用top-K推荐方法对新建模型进行检验，对每一个用户给予积极评价的商品，随机选取100个用户给予消极评价或未进行交互的商品生成测试序列，并对这101份商品进行推荐排序。选用归一化折损累计增益NDCG(normalizeddiscountedcumulative gain)与命中率HR(hits ratio)衡量模型推荐效果：

NDCG $@$ K：越靠前的排名越能影响最终结果。该指标越大则说明目标商品在TOP-K序列中的位置越靠前，其定义为

$$
N D C G @ K = \frac { 1 } { N } \sum _ { \nu } \frac { \log _ { e } 2 } { \log _ { e } ( i + 2 ) }
$$

$\mathrm { H R } @ \mathrm { K }$ ：hit表示TOP-K中是否出现目标商品，出现为1，否则为0。 $\mathrm { H R } @ \mathrm { K }$ 代表在所有测试集S中命中目标商品的概率，其定义为

$$
H R \ @ K = { \frac { n u m b e r o f h i t s } { N } }
$$

# 3.3比对模型及参数设置

将新建模型与以下六个经典模型进行比较(其中两个模型基于矩阵分解思想，三个模型基于神经网络思想，最后的LINN 基于神经网络与逻辑推理相结合的思想)：

a)SVD $+ + [ 1 3 ]$ ：基于矩阵分解方法的改进模型，集成显式与隐式反馈的强大推荐模型。

b)BiasedMF[34]：成对学习的矩阵分解的代表性模型，关 注于商品之间的排序高于评价。

c)STAMP[35]：基于短期注意力与记忆优先级的模型，借助注意力机制获取用户长期及短期偏好，是热门模型之一。

d)GRU4Rec[36]：面向推荐问题的门控循环网络模型。

e)NARM[37]：将注意力机制与门控循环网络相结合的模型，是热门的序列推荐模型之一。

f)LINN[10]：将神经网络与逻辑推理相结合的模型，是神经网络与逻辑毅力相结合的热门模型之一。本文新建模型也基于神经网络与逻辑推理相结合的思想，本文方法在该模型基础之上增加了一个隐式逻辑表征模块以进一步提升模型面对推荐问题时的性能。

上述模型均采用Pytorch 实现，对于每个模型，都以在验证集上取得最好效果那轮的测试结果作为模型最佳性能，并在多个随机种子下模型取得的效果取平均值作为模型平均性能指标。神经网络基线模型的参数设置如表2所示。

Tab.1 Basic information of experimental data set   
表2模型的超参数设置  
Tab.2Hyperparameter setting of model   

<html><body><table><tr><td>超参数名称</td><td>参数值</td></tr><tr><td>优化器</td><td>Adam</td></tr><tr><td>迭代次数</td><td>100</td></tr><tr><td>学习率</td><td>0.001</td></tr><tr><td>批处理大小</td><td>128</td></tr><tr><td>丢弃率(dropout)</td><td>0.2</td></tr><tr><td>L2正则项系数</td><td>1e-5</td></tr><tr><td>GRU4Rec 隐藏维度</td><td>64</td></tr><tr><td>STAMP隐藏维度</td><td>64</td></tr><tr><td>NARM隐藏维度</td><td>64</td></tr><tr><td>NARM注意力维度</td><td>16</td></tr></table></body></html>

# 3.4结果与分析

为避免偶然性影响，本文选取 $\mathrm { H R } @ \mathrm { K } ( \mathrm { K } { = } 1 , 5 , 1 0 , 2 0 , 5 0 )$ 及NDCG $@ .$ K $\mathrm { K } { = } 5 , 1 0 , 2 0 )$ 共八个指标的平均值作为比较参数。七个模型在三个数据集的平均性能见表2，可以看到本文新建模型在三个数据集上的性能均高于六个经典模型，可知本文方法能有效提高推荐准确率，增强推荐准确性。

在密度与质量较高的数据集MovieLens和Amazon-E上，基于神经网络的方法显著优于矩阵分解方法，可能是由于神经网络方法能够赋予模型非线性学习能力，在面对特征丰富的数据集时能利用到更多交互信息。在Book-Crossing 数据集上，除本文方法外的神经网络模型性能均低于矩阵分解方法，而矩阵分解模型则依然能保持它们在其余两个数据集上的推荐性能。分析原因是过于稀疏的数据集导致神经网络难以捕捉足够多的特征，致使模型收敛效果不佳。

本文方法在三个不同数据集上均表现了最佳性能，这主要归功于增加的隐式逻辑表征模块在保有模型推理能力的同时弥补了LINN模型难以捕获变量间高阶隐式信息的缺陷以及串联计算图带来的信息丢失问题。

从稀疏稳定性来看，基于矩阵分解的模型在不同数据集上性能相近，这可能是由于矩阵分解方法对数据集质量的依赖较弱。其余五种神经网络模型的性能均在Book-Crossing数据集上出现明显下滑，但本文方法的降幅显著低于其余神经网络模型，分析原因是增加的隐式逻辑表征模块强化了模型的鲁棒性，在面对稀疏数据时仍能通过挖掘各变量间的隐式信息以取得良好表现。

更详细的实验结果如表3\~5所示。可以看到，当选择不同K 值时，模型性能排序会有轻微变化，如Book-Crossing数据集的HR@1与 ${ \mathrm { H R } } ( \varnothing 5 $ 指标上， ${ \mathrm { S V D } } + +$ 取得优异表现，而Amazon-E数据集的 $\mathrm { N D C G } @ 5$ 与 ${ \mathrm { H R } } ( \emptyset 1 $ 指标上，LINN表现更佳。这可能是由于本文方法考虑不同商品间的隐式交互使得相似商品在排序中更加接近，导致极小范围的推荐精度出现降低，未来将考虑引入额外信息优化嵌入，改善模型小范围推荐精度。

Tab.3Average experimental results of each model in three data sets   

<html><body><table><tr><td rowspan="2">对比方法</td><td colspan="2">MovieLens</td><td colspan="2">Book-Crossing</td><td colspan="2">Amazon-E</td></tr><tr><td colspan="6">NDCG@AVEHR@AVENDCG@AVEHR@AVENDCG@AVEHR@AVE</td></tr><tr><td>SVD++</td><td>0.3658</td><td>0.6137</td><td>0.3461</td><td>0.6197</td><td>0.3528</td><td>0.5404</td></tr><tr><td>BiasedMF</td><td>0.3542</td><td>0.5987</td><td>0.3497</td><td>0.5929</td><td>0.3426</td><td>0.5255</td></tr><tr><td>STAMP</td><td>0.3853</td><td>0.6198</td><td>0.3155</td><td>0.5890</td><td>0.3911</td><td>0.5858</td></tr><tr><td>GRU4Rec</td><td>0.3899</td><td>0.6248</td><td>0.3023</td><td>0.5799</td><td>0.3989</td><td>0.5934</td></tr><tr><td>NARM</td><td>0.3922</td><td>0.6252</td><td>0.3040</td><td>0.5712</td><td>0.3990</td><td>0.5933</td></tr><tr><td>LINN</td><td>0.3849</td><td>0.6192</td><td>0.3192</td><td>0.5973</td><td>0.4162</td><td>0.6062</td></tr><tr><td>IDCR</td><td>0.3989</td><td>0.6314</td><td>0.3560</td><td>0.6639</td><td>0.4187</td><td>0.6094</td></tr></table></body></html>

表4各模型在MovieLens数据集的实验效果

表3各模型在三个数据集的平均实验结果  

<html><body><table><tr><td colspan="6">对比方法 NDCG@5 NDCG@10 NDCG@20 HR@1HR@5HR@10 HR@20 HR@50</td></tr><tr><td>SVD++</td><td>0.3344</td><td>0.3679</td><td>0.3951</td><td>0.1715 0.4669 0.6615</td><td>0.8115</td><td>0.9572</td></tr><tr><td>BiasedMF</td><td>0.3054</td><td>0.3600</td><td>0.3974</td><td>0.1485 0.4571 0.6260</td><td>0.8033</td><td>0.9588</td></tr><tr><td>STAMP</td><td>0.3330</td><td>0.3929</td><td>0.4299</td><td>0.1732 0.4839 0.6683</td><td>0.8157</td><td>0.9582</td></tr><tr><td>GRU4Rec</td><td>0.3400</td><td>0.3949</td><td>0.4350</td><td>0.1694 0.4995 0.6693</td><td>0.8242</td><td>0.9620</td></tr><tr><td>NARM</td><td>0.3439</td><td>0.3967</td><td>0.4360</td><td>0.1759 0.5027 0.6654</td><td>0.8226</td><td>0.9593</td></tr><tr><td>LINN</td><td>0.3385</td><td>0.3876</td><td>0.4287</td><td>0.1733 0.5005 0.6517</td><td>0.8130</td><td>0.9577</td></tr><tr><td>IDCR</td><td>0.3492</td><td>0.4053</td><td>0.4423</td><td>0.18380.50750.6801</td><td>0.8259</td><td>0.9595</td></tr></table></body></html>

表5各模型在Book-Crossing数据集的实验结果

Tab.4Experimental results of each model in movielens datase   

<html><body><table><tr><td colspan="7">对比方法 NDCG@5NDCG@10 NDCG@20 HR@1HR@5HR@10 HR@20 HR@50</td></tr><tr><td>SVD++</td><td>0.3163</td><td>0.3532</td><td>0.3687</td><td>0.33250.57890.6595 0.70740.8202</td><td></td><td></td></tr><tr><td>BiasedMF</td><td>0.3167</td><td>0.3576</td><td>0.3748</td><td>0.32000.53950.6157</td><td>0.6943</td><td>0.7949</td></tr><tr><td>STAMP</td><td>0.3059</td><td>0.3158</td><td>0.3247</td><td>0.3207 0.5352 0.6108</td><td>0.6845</td><td>0.7940</td></tr><tr><td>GRU4Rec</td><td>0.2930</td><td>0.2996</td><td>0.3144</td><td>0.2917 0.5260 0.6012</td><td>0.6843</td><td>0.7964</td></tr><tr><td>NARM</td><td>0.2968</td><td>0.3014</td><td>0.3139</td><td>0.30770.51150.5910</td><td>0.6634</td><td>0.7825</td></tr><tr><td>LINN</td><td>0.3119</td><td>0.3175</td><td>0.3282</td><td>0.3120 0.5450 0.6256</td><td>0.6918</td><td>0.8122</td></tr><tr><td>IDCR</td><td>0.3317</td><td>0.3597</td><td>0.3767</td><td>0.31050.57180.7436</td><td></td><td>0.8139 0.8798</td></tr></table></body></html>

表6各模型在Amazon-E数据集的实验结果

Tab.5Experimental results of each model in Book-Crossing dataset   
Tab.6Experimental results of each model in amazon-e datase   

<html><body><table><tr><td colspan="8">对比方法 NDCG@5 NDCG@10 NDCG@20 HR@1HR@5HR@10 HR@20 HR@50</td></tr><tr><td>SVD++</td><td>0.3159</td><td>0.3554</td><td>0.3873</td><td>0.1891 0.4331 0.5551</td><td></td><td>0.6813</td><td>0.8436</td></tr><tr><td>BiasedMF</td><td>0.3063</td><td>0.3445</td><td>0.3771</td><td>0.1909 0.4136 0.5316</td><td></td><td>0.6610</td><td>0.8308</td></tr><tr><td>STAMP</td><td>0.3529</td><td>0.3938</td><td>0.4267</td><td>0.2202 0.4754 0.6020</td><td></td><td>0.7321</td><td>0.8992</td></tr><tr><td>GRU4Rec</td><td>0.3609</td><td>0.4016</td><td>0.4344</td><td>0.22540.4855 0.6106</td><td></td><td>0.7404 0.9051</td><td></td></tr><tr><td>NARM</td><td>0.3611</td><td>0.4018</td><td>0.4343</td><td>0.2254 0.4855 0.6116</td><td></td><td>0.7396</td><td>0.9047</td></tr><tr><td>LINN</td><td>0.3802</td><td>0.4185</td><td>0.4501</td><td>0.2449 0.5019 0.6247</td><td></td><td>0.7494</td><td>0.9104</td></tr><tr><td>IDCR</td><td>0.3801</td><td>0.4224</td><td>0.4537</td><td>0.2428 0.5075 0.6305</td><td></td><td>0.7543</td><td>0.9121</td></tr></table></body></html>

# 3.5参数敏感性实验

对新建模型的嵌入维度与隐式逻辑表征中自注意力层数进行参数敏感性测试。分别设定嵌入维度为64、72、84、96、108，自注意力层数为1、2、3在三个数据集上测试，结果如图3\~5所示，发现当自注意力层数为2时，模型性能出现明显提升，可知2层自注意力网络就能挖掘各变量之间的隐式高阶关系。同时,模型的性能也随着嵌入维度的增加而提升，在三个数据集上获得最好性能的嵌入维度分别是84、96、96，可知在不同结构的数据集上隐藏的交互信息丰富程度有轻微差异。

![](images/1cbdd850ebf9c55bd36f9fd4670ac4c15940c1ce06edf115256d1d8e7ae60aa6.jpg)  
图3MovieLens数据集上参数敏感测试结果

![](images/7561d6cf0c01deb0ecbe95dd6d1765651978946b28126d96193ec415fa131471.jpg)  
Fig.3Parameter sensitivity test results on movielens dataset   
图4Book-Crossing数据集上参数敏感测试结果

![](images/de4a18178c99c4f6dc407f464bd358978aae6e63afd72c82b3023079076fdba1.jpg)  
Fig.4Parameter sensitivity test results on Book-Crossing dataset   
图5Amazon-E数据集上参数敏感测试结果  
Fig.5Parameter sensitivity test results on Amazon-E dataset

# 4 结束语

本文以将推荐问题转换为逻辑表达式进行求解的思想为基础，提出一种融合命题逻辑与神经网络的隐式深度协同推理算法。算法将逻辑表达式中的一组逻辑变量视为序列，使用多层自注意力与门控循环网络构造隐式逻辑编码器挖掘各变量间的隐式交互信息并生成隐式逻辑变量，使模型在求解过程中能利用到不同变量间的高阶交互关系与信息，改善模型解决复杂现实问题的能力。同时，门控循环网络的记忆机制也在一定程度上改善了模型串联求解过程中产生的靠前单位信息丢失问题。基于三个公开数据集MovieLens、Book-Crossing、Amazon-E的实验结果表明，本文方法较基线方法有明显提升。

本文方法也存在一定不足，例如，本文没有考虑基本逻辑规则中先验知识对符号模块的影响，也没有充分利用外界丰富的辅助信息，而是通过模型训练挖掘变量间的隐式交互信息。未来将考虑在嵌入中加入更多用户与商品的辅助信息以丰富特征，同时尝试利用基本逻辑规则强化模型推理能力。

# 参考文献：

[1]Cui Zhihua,Xu Xianghua,Xue Fei,et al.Personalized recommendation system based on collaborative filtering for IoT scenarios [J].IEEE Transactions on Services Computing,2020,13 (4): 685-695.

计算机工程,2021,47(7):1-12.(LiuHualing,MaJn,ZhangGuoiang. Summary of research on content recommendation algorithm based on deep learning[J] Computer engineering,2021,47(7): 1-12.)   
[3]He Xiangnan, Zhang Hanwang,Kan MY,et al.Fast matrix factorization for online recommendation with implicit fedback [C]// Proc of the 39th International ACM SIGIR conference on Research and Development in Information Retrieval. 2016: 549-558.   
[4] Cheng H T,Koc L,Harmsen J,et al.Wide & deep learning for recommender systems [C]// Proc of the lst workshop on deep learning for recommender systems. 2016: 7-10.   
[5]Dacrema M F,Cremonesi P,Jannach D.Are we really making much progress?A worrying analysis of recent neural recommendation approaches [Cl//Proc of the 13th ACM Conference on Recommender Systems.2019:101-109.   
[6]Rendle S, Krichene W, Zhang L,et al. Neural collaborative filtering vs. matrix factorization revisited [C]// Fourteenth ACM Conference on Recommender Systems.2020: 240-248.   
[7]Bengio Y.From system 1 deep learning to system 2 deep learning [C]// Thirty-third Conference on Neural Information Processing Systems. 2019.   
[8]Shi Shaoyun,Chen Hanxiong,Ma Weizhi,et al.Neural logic reasoning [C]/ Proc of the 29th ACM International Conference on Information & Knowledge Management. 2020: 1365-1374.   
[9] Chen Hanxiong,Li Yunqi, Shi Shaoyun,et al. Graph Collaborative Reasoning [C]// Proceedings of the Fifteenth ACM International Conference on Web Search and Data Mining.2022:75-84.   
[10] Chen Hanxiong,Shi Shaoyun,Li Yunqi,et al. Neural collaborative reasoning [C]//Proc of the Web Conference 2021.2021: 1516-1527.   
[11] Fan Yujia, Zhang Yongfeng.Neural Logic Analogy Learning[J].arXiv preprint arXiv: 2202. 02436,2022.   
[12] Huang Zhenya,Liu Qi, Zhai Chengxiang，et al. Exploring multiobjective exercise recommendations in online education systems [C]// Proc of the 28th ACM International Conference on Information and Knowledge Management. 2019: 1261-1270.   
[13] Koren Y. Factorization meets the neighborhood:a multifaceted collaborative filtering model[C]// Proc of the 14th ACM SIGKDD international conference on Knowledge discovery and data mining.2008: 426-434.   
[14] AdomaviciusG.Context-awarerecommendersystems[M]// Recommender systems handbook. Springer, Boston,MA,2011: 217-253.   
[15] Karatzoglou A，Amatriain X,BaltrunasL，et al.Multiverse recommendation: n-dimensional tensor factorization for context-aware collaborative filtering [C]// Proc of the fourth ACM conference on Recommender systems. 2010: 79-86.   
[16] Koren Y.Collaborative filtering with temporal dynamics [C]//Proc of the 15th ACM SIGKDD international conference on Knowledge discovery and data mining. 2009: 447-456.   
[17] Zhang Yongfeng,Ai Qingyao,Chen Xu,et al. Joint representation learning for top-n recommendation with heterogeneous information sources [C]/ Proc of the 2017 ACMon Conference on Information and Knowledge Management. 2017: 1449-1458.   
[18] He Ruining, McAuley J. VBPR: visual bayesian personalized ranking from implicit feedback [C]/ Proc of the AAAI Conference on Artificial Intelligence. 2016,30(1).   
[19] Ai Qingyao,Azizi V, Chen Xu,et al. Learning heterogeneous knowledge base embeddings for explainable recommendation [J].Algorithms,2018, 11 (9): 137.   
[20] Hsieh C K, Yang Longqi, Cui Yin,et al. Collaborative metric learning [C]// Proc of the 26th international conference on world wide web.2017: 193-201.   
[21] Salakhutdinov R,Mnih A,Hinton G.Restricted Boltzmann machines for collaborative filtering[C]// Proc of the 24th international conference on Machine learning.2007: 791-798.   
[22] He Xiangnan,Liao Lizi, Zhang Hanwang,et al. Neural collaborative filtering[C]// Proc of the 26th international conference on world wide web. 2017: 173-182.   
[23] Ebesu T,Shen Bin,Fang Yi.Collaborative memory network for recommendation systems [C]/ The41st international ACM SIGIR conference on research & development in information retrieval.2018: 515-524.   
[24] Jiang Zhuxi, Zheng Yin,Tan Huachun,et al. Variationaldeep embedding: an unsupervised and generative approach to clustering [C]//Proc of the 26th International Joint Conference on Artificial Intellgence.2017: 1965-1972.   
[25] Hohenecker P, Lukasiewicz T. Ontology reasoning with deep neural networks [J]. Journal ofArtificial Intelligence Research,202o,68: 503- 540.   
[26] Makni B,Hendler J. Deep learning for noise-tolerant RDFS reasoning [J].Semantic Web,2019,10 (5): 823-862.   
[27] JohnsonJ, Hariharan B,Van Der MaatenL,etal. Infering and executing programs for visual reasoning [C]// Proc of the IEEE International Conference on Computer Vision.2017: 2989-2998.   
[28] Yi Kexin,Wu Jiajun, Gan Chuang，et al. Neural-symbolic VQA: disentangling reasoning from vision and language understanding [C]// Proc of the 32nd International Conference on Neural Information Processing Systems. 2018: 1039-1050.   
[29] Yang Fan,Yang Zhilin,Cohen WW.Differentiable learning of logical rules for knowledge base reasoning [C]// Proc of the 31st International Conference on Neural Information Processing Systems.2017:2316-2325.   
[30] Dong Honghua, Mao Jiayuan,Lin Tian,etal. Neurallogic machines [C]/ International Conference on Learning Representations. 2018.   
[31] Harper F M,Konstan JA. The movielens datasets: history and context [J].Acm transactions on interactive intelligent systems (tiis),2015,5 (4): 1-19.   
[32] Ziegler CN, McNee S M, Konstan JA,et al. Improving recommendation lists through topic diversification [Cl// Proc of the 14th international conference on World Wide Web.2005:22-32.   
[33] He Ruining,McAuley J. Ups and downs: modeling the visual evolution of fashion trends with one-class collborative filtering [C]//Proc of the 25th international conference on world wide web.2016: 507-517.   
[34] Rendle S,Freudenthaler C,Gantner Z,et al. BPR: Bayesian personalized ranking from implicit feedback [C]// Proc of the Twenty-Fifth Conference on Uncertainty in Artificial Intelligence.20o9: 452-461.   
[35]Liu Qiao，Zeng Yifu，Mokhosi R,et al.STAMP:short-term attention/memory priority model for session-based recommendation [C]// Proc of the 24th ACM SIGKDD International Conference on Knowledge Discovery & Data Mining. 2018: 1831-1839.   
[36] Hidasi B，Karatzoglou A，Baltrunas L，etal.Session-based recommendations with recurrent neural networks [J]// International Conference on Learning Representations (2016) .   
[37] Li Jing,Ren Pengjie,Chen Zhumin,et al. Neural attentive session-based recommendation [C]// Proc of the 2017 ACM on Conference on Information and Knowledge Management. 2017: 1419-1428.