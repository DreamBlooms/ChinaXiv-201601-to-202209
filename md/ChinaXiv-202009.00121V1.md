# 基于TransE的表示学习方法研究综述

张正航a,b，钱育蓉a,b，行艳妮a,b，赵鑫a,b(新疆大学a.软件学院;b.新疆维吾尔自治区信号检测与处理重点实验室，乌鲁木齐 830046)

摘要：为了及时了解基于TransE的表示学习方法的最新研究进展，该文通过归纳与整理，将基于TransE 的表示学习方法分为基于复杂关系的方法、基于关系路径的方法、基于图像信息的方法，以及基于其他方面的方法这4种类型。对每一种方法的设计思路、优缺点等进行了详细的分析。同时，对基于TranSE的表示学习方法的公共数据集与评价指标进行了对比、总结，以及对各种基于TranSE的表示学习算法在实验中的表现进行了对比分析。最后，对全文的研究进行了总结，对今后研究的热点进行了展望。从研究结果来看，PaSKoGE方法、NTransGH方法、TCE方法、TranSD方法在做链接预测和三元组分类任务上表现效果最好，值得推广和进一步拓展，并可在其特定于路径的嵌入、两层神经网络、三元组上下文、动态构造映射矩阵上进一步完善。

关键词：知识图谱；表示学习；TransE模型；知识图谱嵌入；翻译模型中图分类号：TP doi:10.19734/j.issn.1001-3695.2020.02.0028

Survey of representation learning methods based on transe

Zhang Zhenghanga,b, Qian Yuronga, bt, Xing Yannia, b, Zhao Xina, b (a.CollegeofSoftware,b.KeyLaboratoryofsignal detection&processing in Xinjiang Uygur AutonomousRegion,Xinjiang University, Urumqi 830046, China)

Abstract: Inorder tounderstand the latest research progressof TransE based representation learning methods inreal time, this paperclasifies TransE basedrepresentation learming methods into four types: the methodbasedoncomplexrelationship, the method basedonrelationship path,the method based onimage information,and the method basedonother aspects.Then, this paper analyzes the design ideas,advantages and disadvantages of each method.At the same time,it compares and summarizes thecommondata setsand evaluation indexesof the TransEbasedrepresentation learning method,aswelas the performanceofvarious TransE based representationlearning algorithms inthe experiment.Finaly,this papersummarizes the researchof the whole paperand looks forward tothe future research hotspot.From the research results,PaSKoGE method, NTransGH method,TCE methodandTransDmethod performthebestinlink predictionand triple classificationtasks,which ar worthpromotingandfurther expanding,andcanbefurther improvedinpath specific embedding,two-layer neuralnetwork, triple context and dynamic mapping matrix construction.

Key words: knowledge graph; representation learning;transe model; knowledge graph embedding;translation model

# 0 引言

近年来，受到词向量模型的启发，以翻译模型为代表的表示学习在知识图谱(knowledge graph,KG)领域越来越受到人们的关注。知识表示指的是通过将符号化的三元组 $( h , r , t )$ 映射到低维稠密的向量空间，便于实体与关系之间的计算[I\~3]。在这种向量空间中，通过计算实体(关系)对象间的距离，从而推理出实体(关系)对象的语义相似度，能够高效解决数据稀疏的难题，使得知识获取和知识推理变得更加容易与精准[4,5]。同时，知识表示学习的研究能够服务于实体对齐、事件抽取，以及问答系统等应用之中，拥有非常广阔的前景[]。

考虑到知识表示的广泛应用前景，学者们相继提出了很多的知识表示模型，例如距离模型(structuredembedding，SE)、单层神经网络模型(single layer model，SLM)、语义能量匹配模型(semantic matching energy,SME)、张量分解模型、基于翻译的模型等[7]。在这些经典方法中，以 TransE[8]为代表的翻译模型最受到人们的重视，成为当下研究的热点。TransE模型是Bordes在2013年提出来的，这种方法在链接预测方面表现出了很好的效果，并且这种方法参数少，操作简单。但是，TransE方法在处理复杂关系时存在准确度不高的问题，例如在处理一对多、多对一、多对多和自反等复杂关系时，TransE方法不能精准推算出具有相同关系的实体[9\~I1]。

TransE方法优化问题一直都是学者们争相研究的热门话题，每年都会有许多新奇的模型出现[12\~15]。该文以TransE 方法存在的问题为分类原则，将基于TransE的表示学习方法的综述文献分为4类：第一类是基于复杂关系的方法的综述，如STransH、TransD、NTransGH、TransGraph、TransAH[16\~18];第二类是基于关系路径的方法的综述，如PTransE、PaSKoGE[19,20]，第三类是基于图像信息方法的综述，如ITMEA、 $\mathrm { T C E } ^ { [ 2 1 , 2 2 ] }$ ；第四类是其他方面的方法综述[23\~25]，如TransRD[26]、TransE-SNS[27]、AST_NZL[28]、GTrans[29]。与其他知识表示综述相比，本文的主要贡献如下：

a）对基于TransE的表示学习方法的算法思想、优缺点进行了介绍，并对其进行了较为全面、合理的分类与总结[30,31];b)对TransE表示学习方法存在的问题进行了较为细致的分析与概述；

c）对基于TransE的表示学习算法常用的实验数据集、算法性能评价指标进行了分析与总结；对每类问题中算法的主要指标进行了对比分析，并找出了可以继续推广和扩展的方法[32];

d）分析与总结了基于TransE的表示学习算法中当前存在的问题，已经解决的问题，以及未来的可能研究点[33]。

# 1 TransE表示学习方法概述

TransE方法解决的是在低维向量空间中嵌入实体和多关系数据的关系的问题，是一种通过将关系解释为对实体的低维嵌入进行操作的转换来对关系进行建模的方法[34,35]。通过对这种方法的基本原理、优缺点，以及算法的分析，可以加深对其作用机理的认识。

# 1.1TransE 方法概述

TransE是知识表示翻译模型中非常经典的方法，Trans系列的方法是在TransE的基础上扩展的。在TransE中，实体和关系被映射到向量空间，实体和关系的表示变成了向量之间的表示[36,37]。TransE 的主要思想是把三元组 $( h , r , t )$ 中的关系等价于从头实体向量到尾实体向量的操作过程，这种操作过程称为翻译[38,39]。同时，TransE 还对三元组 $( h , r , t )$ 中的实体和关系映射到向量空间作了一些假设(如图1所示)，假设每一个三元组 $( h , r , t )$ 都能表示为

$$
( h , r , t )
$$

其中， $h$ 指代头实体的向量表示； $\boldsymbol { r }$ 指代关系的向量表示， $\mathbf { \Phi } _ { t } \mathbf { \Phi } _ { t }$ 指代尾实体的向量表示。式(1)表示的含义是：在向量空间中，头实体向量 $h$ 加上关系 $\boldsymbol { r }$ 应该等于尾实体向量t。如果在向量空间上述式子成立，那么，就说明三元组 $( h , r , t )$ 在KG中是成立的。根据这种假设TransE模型的训练需要满足以下条件：

对正样本三元组： $h + r \approx t$ （204号对负样本三元组： $h + r \neq t$

![](images/b1f558a243f57a4f7410530f87f6bd1db0567c9371a9faf25d666a41528aab16.jpg)  
图1TransE 向量空间假设  
Fig.1Transe vector space hypothesis

在式(2)(3)中， $h + r$ 与 $t$ 的关系表示近似等价于向量相似度。对于向量相似度，TransE采用的方法是计算欧式距离，得分函数如下：

$$
f ( h , r , t ) = \left\| h + r - t \right\| _ { L _ { 1 } / L _ { 2 } }
$$

得分函数值越小，对正样本三元组越有利；得分函数值越大，对负样本三元组越有利。接着，TransE通过损失函数测试表示学习的效果，设计的损失函数如下：

$$
\mathrm { L } = \sum _ { ( h , r , t ) \in S } \ \sum _ { ( h ^ { \prime } , r , t ^ { \prime } ) \in S _ { ( h , r , t ) } ^ { \prime } } [ \gamma + f ( h , r , t ) - f ( h ^ { \prime } , r ^ { \prime } , t ^ { \prime } ) ] _ { + }
$$

在式(5)中，S指的是正样本的集合； $\mathbf { S ^ { \prime } } _ { h , r , t }$ 指的是三元组$( h , r , t )$ 的负样本。KG中三元组 $( h , r , t )$ 的负样本是通过随机替换头实体 $h$ ，或者尾实体 $t$ ，进行大量的训练得到的。 $[ x ] _ { + }$ 指的是 $\operatorname* { m a x } ( 0 , x )$ ； $\gamma$ 指的是损失函数中的间隔，这个参数需要满足大于零的条件。TransE通过不断训练，算法的优化，可以使损失函数 $\mathrm { ~ \tt ~ L ~ }$ 达到最小值。

算法1 Learning TransE

input Training set ${ \bf { S } } = \{ ( h , r , t ) \}$ ，entities and rel.sets E and $\iota$ ，margin $\gamma$ ，embeddings dim. $k$ ·

1:initialize r←uniform(-6, $\frac { 6 } { \sqrt { \mathbf { k } } } , \frac { 6 } { \sqrt { k } }$ )for each r∈L   
$2 : r \gets r / \left. r \right.$ for each $r _ { \in \mathrm { L } }$ （204   
3:e←uniform( $\frac { 6 } { \sqrt { \mathrm { k } } } , \frac { 6 } { \sqrt { k } }$ ：)for each entityeεE   
4:loop   
$5 : { \mathsf e } \gets { \mathsf e } / \left\| { \mathsf e } \right\|$ for each entity $\boldsymbol { \mathsf { e } } _ { \in \mathrm { E } }$ （204   
（204号 $6 \colon \mathrm { S } _ { \mathrm { b a t c h } } \gets s a m p l e ( S , b ) /$ /sample a minibatch of size b   
（204号 $7 \colon \mathrm { T } _ { b a t c h } \gets \mathrm { 0 }$ //initialize the set of pairs of triplets   
8:for $( h , r , t ) \in \ S _ { b a t c h }$ do   
$\mathfrak { s } \colon ( h ^ { \prime } , r , t ^ { \prime } ) \gets$ sample ( $\mathbf { S } _ { ( h , r , t ) }$ )//sample a corrupted triplet   
（204号 $\begin{array} { r } { { 1 } \theta \colon \mathrm { T } _ { b a t c h } \gets \mathrm { T } _ { b a t c h } \cup \{ \left( \left( h , r , t \right) , \left( \mathbf { \Omega } _ { h ^ { \prime } , r , t ^ { \prime } } \right) \right) \} } \end{array}$ （204   
11:end for   
12:Update embeddings w.r.t   
$\sum _ { ( ( h , r , t ) , ( h ^ { \prime } , r , t ^ { \prime } ) ) } \nabla [ \gamma + d ( h + r , t ) - d ( h ^ { \prime } + r , t ^ { \prime } ) ] _ { + }$

# 13:end loop

# 1.2TransE方法的优缺点

TransE的提出是为了解决多关系数据的处理问题,是一种简单、高效的KG表示学习方法,并且能够完成多种关系的链接预测任务[40,41]。TransE 的简单高效说明了KG 表示学习方法能够自动且很好地捕捉推理特征,无须人工设计，很适合在大规模复杂的KG上推广,是一种有效的KG推理手段。尽管有效,TransE依然存在着表达能力不足的问题。按照关系头尾实体个数比例划分，KG中的关系可以分为四种类型，分别为一对一、一对多、多对一、多对多的关系,但是TransE无法有效处理一对多、多对一、多对多的关系,以及自反关系。此外,TransE通过最小化所有关系路径共享的余量损失函数，来确定实体、关系和多步关系路径，此设置无法考虑不同关系路径之间的差异[42]。同时,TransE模型还存在处理图像信息效果差、负例三元组的质量低、嵌入模型不能快速收敛、泛化能力差、边缘识别能力差等问题。

# 2 基于TransE的表示学习方法

针对TransE表示学习方法存在的不足，大量的研究者尝试建立不同的模型去对TransE表示学习方法进行优化。其中，绝大多数的研究者集中在基于复杂关系的方法、基于关系路径的方法、基于图像信息的方法，少数的研究者集中在其他方面的方法。

# 2.1基于复杂关系的方法

复杂关系的问题指的是TransE无法有效处理一对多、多对一、多对多的关系,以及自反关系。对于这个问题，有不少学者提出了一些比较经典的方法，例如TransR方法、TransH方法、TransA方法[43]。对于处理复杂关系的问题，常规的解决思路是对实体和关系在向量空间进行投影，再计算损失函数来推算实体和关系的语义联系[44]。但是，这在处理链接预测和三元组分类任务时会遇到效率低下的问题。

针对TransE方法不能很好处理实体之间复杂关系的问题，目前，在链接预测和三元组分类任务做得比较好的主要有五种解决方法：嵌入单层神经网络的方法、构造映射矩阵的方法、构建广义超平面翻译机制的方法、嵌入交叉训练机制的方法、嵌入超平面模型的方法。

嵌入单层神经网络的方法简称STransH方法，算法思想是：分别在实体空间和关系空间建模，并采用单层神经网络的非线性操作来加强实体和关系的语义联系。同时，受TransH模型的启发，引入投影到特定关系超平面的机制，使得实体在不同的关系中有不同的角色。这种方法的优点是引入投影到特定关系超平面的机制，好处是使得实体在不同的关系中有不同的角色；缺点是没有将关系路径考虑在内。

构造映射矩阵的方法简称TransD方法，算法思想是：在TransD方法中，使用两个向量来表示命名的符号对象(实体和关系)第一个表示一个实体(关系)的含义，另一个用于动态构造映射矩阵。不仅考虑关系的多样性，而且考虑实体(见图2)。这种方法的优点是提出一种动态变化矩阵的方法，好处是提供了一种灵活的样式来将实体表示投影到关系向量空间；缺点是忽略了关系的内在相关性，参数过多，知识共享困难。TransD模型的映射函数为

$$
M _ { r h } = r _ { p } h _ { P } ^ { T } + I ^ { m \times n }
$$

$$
M _ { n } = r _ { p } t _ { p } ^ { T } + I ^ { m \times n }
$$

在式(6)(7)中， $I ^ { m \times n }$ 是单位矩阵，头实体和尾实体分别用两个不同的映射矩阵 $\boldsymbol { M } _ { \scriptscriptstyle r h }$ 和 $\boldsymbol { M } _ { \scriptscriptstyle r t }$ 进行投影，头实体的映射矩阵由关系向量 $r _ { p }$ 与头实体映射向量 $h _ { p } ^ { T }$ 共同决定；尾实体的映射矩阵由关系向量 $r _ { p }$ 与尾实体映射向量 $t _ { p } ^ { T }$ 共同决定，映射后得到的头实体和尾实体向量分别是：

$$
h _ { \perp } = M _ { r h } h
$$

$$
t _ { \perp } = M _ { r t }
$$

TransD模型的损失函数因此变为

$$
f _ { r } ( h + t ) = \left\| h _ { \perp } + r - t _ { \perp } \right\| _ { l _ { 1 } / l _ { 2 } }
$$

![](images/323b91e029ca87a6a5b83ef292153c3a1e6365a9ac22d6b60584a62d8ec2ce4c.jpg)  
图2TransD实体表示空间和关系表示空间

构建广义超平面翻译机制的方法简称NTransGH方法，算法思想是：结合用于将关系建模为广义超平面的翻译操作的翻译机制，以及用于捕获实体与关系之间更复杂交互的神经网络，对两个数据集的链接预测和三重分类进行两项任务的实验。这种方法的优点是引入了两层神经网络来定义得分函数，好处是以便找到用于计算机的低维嵌入；缺点是需要操作的参数偏多。

NTransGH首先利用广义超平面将关系建模为翻译操作的翻译机制，然后设计一个用于捕获复杂关系模式的神经网络。具体地说，对于建模平移操作，如图3(a)所示，NTranGH基于TransH使用一组基向量而不是TransH中的一个法向量来确定广义超平面。为了表示复杂关系，NTransGH引入了一个两层神经网络来定义一个得分函数，以寻找复杂关系的低维嵌入。图3(b)所示NTransGH的基本思路是，对于给定的三元组 $( \mathrm { h , r , t } )$ ，在翻译短语中，NTransGH首先用一组基向量分别将嵌入在广义超平面上的实体 $h$ 和 $t$ 投影为 $h _ { \perp }$ 和 $t _ { \perp }$ ，但是，这会导致需要操作的参数偏多。

![](images/53e1a0cbc2c863cb7cb9c698c54b7d8f7e2e1dab3bc116a75e2d875eeea83394.jpg)  
Fig.2Transd entity representation space and relationship representation space   
图3TransH和NTransGH的简单可视化

Fig.3Simple visualization of transh and ntransgh嵌入交叉训练机制的方法简称TransGraph方法，算法思想是：采用随机梯度下降方法来求解目标函数L的最优化问题，通过计算梯度实现向量和参数的更新。在这种方法中，为了实现网络结构信息和三元组信息的深度融合，在TransE的基础上，给出了一个向量共享的交叉训练机制。这种方法的优点是融合了KG的网络结构特征，好处是进一步增强了KG的表示效果；缺点是忽略了实体的描述文本和互联网文本等信息。

嵌入超平面模型的方法简称TransAH方法，算法思想是：首先建立特定关系的超平面模型；其次，将三元组中的头实体与尾实体嵌入到这种超平面，从而进行实体关系的推理。这种方法的优点是引入面向特定关系的超平面模型，好处是以有效表征复杂关系；缺点是没有考虑在文本关系知识中的抽取，以及实体聚类等方面的任务。

对于复杂关系问题，STransH方法、TransD方法、NTransGH方法、TransGraph方法、TransAH方法都表现了很好的效果。其中，STransH方法采用单层神经网络的非线性操作来加强实体和关系的语义联系，然而，这样做之后预测复杂关系仍然很弱，再加上了超平面模型后预测效果才得到了显著提升，这种方法扩展性好，拥有一定的研究价值，同时，可以结合其他的翻译模型提高预测性能。对于TransD方法，用一个与实体相关的向量以及一个与关系相关的向量通过外积计算，动态地得到关系投影矩阵，这种方法不仅可以显著减少关系数量较大且实体数量不多的KG中的参数，而且增加了TrasnD 捕捉全局特征的能力。对于NTransGH 方法，核心是采用两层神经网络来定义一个得分函数，当前，利用神经网络来改变TransE预测的性能已经成为一种趋势，因此，拥有很广阔的发展空间。对于TransGraph方法，核心是给出了一个向量共享的交叉训练机制，这种思想是首次运用在TransE中，值得借鉴。对于TransAH方法，今后需要加强的点在于实体聚类任务方面。

# 2.2基于关系路径的方法

关系路径问题指的是知识库的表示学习旨在将实体和关系都嵌入一个低维空间，TransE方法仅在表示学习中考虑直接关系，多步关系路径还包含实体之间的丰富推理模式，没有考虑不同关系路径之间的差异[45]。针对这个问题，从收集的文献来看，基于关系路径优化是最近研究的热点，但是，在链接预测和三元组分类任务上做得比较好的方法却比较少

针对TransE方法不能很好解决关系路径的问题，目前，在链接预测和三元组分类任务做得比较好的主要有两种解决方法：路径的表示学习方法、特定于路径的嵌入方法。

路径的表示学习方法简称PTransE方法，算法思想是：将关系路径视为实体之间的转换，以进行表示学习，通过关系嵌入的语义组成来表示关系路径。这种方法的优点是使用与关系路径连接的实体对从知识库中构建三元组，好处是便于选择用于表示学习的可靠关系路径；缺点是只考虑直接关系与关系之间的推理模式，没有考虑关系之间有许多复杂的模式。

特定于路径的嵌入方法简称PaSKoGE方法，算法思想是：对于每个路径，它通过对任何给定实体对的关系和多步关系路径之间的相关性进行编码，来自适应地确定其基于边际的损失函数。这种方法的优点是提出了特定于路径的嵌入方法，好处是对于每条路径，它分别自适应地确定其余量；缺点是需要花费更多的时间来另外计算路径特定的余量。PaSKoGE的边界变化目标函数为

$$
\sum _ { ( h , r , t ) \in \varDelta } { \cal { l } } E _ { h , r , t } + \frac { 1 } { Z } \sum _ { p \in P _ { h , t } } R ( p / h , t ) H _ { p , r } J
$$

$$
E _ { h , r , t } = \sum _ { ( h ^ { ' } , r ^ { ' } , t ^ { ' } ) \Delta ^ { ' } } ( | | h + r - t | | + \gamma _ { o p t } - | | h ^ { ' } + r ^ { ' } - t ^ { ' } | | ) _ { + }
$$

用 $h ^ { ' }$ 、 $t ^ { ' }$ 、 $\boldsymbol { r ^ { \prime } }$ 代替集合 $\Delta$ 中 $( h , r , t )$ 的三个分量h、 $t$ 和 $\boldsymbol { r }$ 中的一个， $[ x ] _ { + }$ 返回 $\mathbf { x }$ 到0之间的最大值；表示 $\mathbf { L } _ { 1 }$ 范数或 $\mathbf { L } _ { 2 }$ 范数； $\gamma _ { o p t }$ 是将正三元组与负三元组分离的最佳裕度，定义方式与TransA相同。学习过程采用随机梯度下降SGD方法，正三元组随机遍历多次。当正三元组被访问时，负三元组$( h ^ { \prime } , r ^ { \prime } , t ^ { \prime } )$ 通过将(h,r,t)的三个分量中的一个替换为KG 中的其他实体或关系来随机构造。此外，给定头部实体和尾部实体之间任意长度的关系路径，需要对关系和连接它们的多步关系路径之间的相关关系进行建模，这需要花费更多的时间。

总体来看，PTransE方法和PaSKoGE方法都能很好解决TransE存在的关系路径问题，只是每种方法的侧重点不一样。其中，PTransE方法侧重于将关系路径视为实体之间的转换，以及通过路径约束资源分配来衡量关系路径的可靠性，而PaSKoGE方法侧重于通过最小化KGE的基于路径的特定边距损失函数来学习实体，关系和多步关系路径的表示。从目前来看，基于关系路径是研究的热点，因此，这两种方法仍然拥有很大的发展空间。

# 2.3基于图像信息的方法

TransE模型在模型学习期间将KG视为一组独立的三元组，但是，这样使得图结构中包含的实体特征信息，以及三元组之间的大量链接都无法有效利用。同时，TransE 模型基于这样的假设：KG是一组单独的三元组，往往关注文本信息而忽视图像信息，导致图像中实体特征信息未被有效利用。为了解决此问题，研究者们提出了不少新颖的方法，比较典型的有ITMEA方法、TCE方法。

ITMEA方法的核心是使用多模态实体对齐。算法思想是：联合多模态(图像、文本)数据，采用翻译嵌入模型TransE与动态映射矩阵嵌入模型TransD相结合的知识表示学习模型，使多模态数据能够嵌入到低维语义空间。在低维语义空间中迭代地学习种子集合中已对齐多模态实体之间的链接映射关系，并将学习到的关系应用到未对齐实体上，从而实现多模态数据的实体对齐。然而，这种方法也存在一些局限性，例如对迭代过程中新找到的对齐实体未进行置信度评估，迭代效果偏低。

TCE方法的核心是利用三元组上下文。算法思想是：定义由邻居上下文和路径上下文组成的三重上下文，并定义一个函数来评估三重上下文与其上下文之间的相关性，而不是单独使用每个三元组；将三元组上下文合并到评分函数中，该函数用于评估三元组的置信度。对于每个三元组，在图中将两种结构信息视为其上下文：一个是实体的传出关系和相邻实体，另一个是一对实体之间的关系路径，两者都反映了三元组的各个方面。三元组及其上下文在统一框架中表示，这样可以体现三元组上下文中的结构信息(见图4)。然而，此方法也存在一些缺陷，例如在基线上不如经典的翻译模型。

![](images/a6b091553b2aca4c8b2c39c9b34c7877a79b08971bbc2824032c682c074edb7f.jpg)  
图4KG中三元组的三重上下文的说明  
Fig.4Description of triple context of triples in KG

三重上下文 $( \mathrm { h , r , t } )$ 由头实体的邻居上下文和实体对(h，t)的路径上下文组成，可以形式化为

$$
\mathrm { C } ( h , r , t ) = C _ { N } ( h ) \cup C _ { p } ( h , t )
$$

三重上下文可以被认为是在图形中体现了它的周围结构，这使得模型能预测图形结构中包含的信息。在分数函数中引入了三重上下文，给定一个候选三元组(h,r,t)，分数函数是给定三重上下文和所有嵌入的条件概率，可以形式化为

$$
f ( h , r , t ) = P ( ( h , r , t ) | C ( h , r , t ) ; \Theta )
$$

在式(14)中， $\mathbf { C } ( \mathrm { h , r , t } )$ 是(h,r,t)的三重上下文。通过最大化K中所有三元组的联合概率来定义一个目标函数，它可以表示为

$$
P ( K | \Theta ) = \prod _ { ( h , r , t ) \in K } f ( h , r , t )
$$

最后，用式(16)合并邻居上下文和三重路径上下文：

$$
\boldsymbol { f } ( h , r , t ) \approx \boldsymbol { P } ( h \mid C _ { N } ( h ) ; \Theta ) \cdot \boldsymbol { P } ( t \mid C _ { p } ( h , t ) , h ; \Theta ) \cdot \boldsymbol { P } ( r \mid h , t ; \Theta )
$$

总体来看，无论是ITMEA方法，还是TCE方法，在处理图像信息问题时都各自具有自己的优势。其中，ITMEA方法的优势是使多模态数据能够嵌入到低维语义空间，进而显著加强多模态数据的嵌入；TCE方法的优势是能很好利用KG中的结构，特别是三元组周围的局部结构，进而加强图上下文的表示学习。目前，图像信息问题依然是研究者们关注的重点，弥补这两种方法的局限性将是今后的研究方向。

# 2.4基于其他方面的方法

TransE方法除了存在以上的几种比较常见的问题外，还存在其他的一些问题，例如泛化能力差、生成的负例三元组大部分都是低质量的、不能快速收敛、边缘识别能力弱等。针对这些问题，从收集的文献来看，只有少数的学者对其进行了研究，取得实质性研究成果的也比较少。因此，这方面的研究拥有很大的发展空间。

泛化能力差的问题指的是在训练过程中，如果KG中三元组关系的数量越多，嵌入的效果就越好，但是，当三元组关系的数量比较少时，意味着只有很少的三元组关系会被映射到矩阵中，造成更新的次数偏低，嵌入效果差[46]。针对TransE还存在泛化能力差的问题，目前，在链接预测和三元组分类任务做得比较好的主要有一种解决方法，即嵌入不对等转换矩阵方法。嵌入不对等转换矩阵方法简称TransRD方法，算法思想是：先对头尾实体进行投影，并在其中嵌入不对等转换矩阵。此外，通过ADADELTA算法调整学习率；接着，将关系进行分组，对每组的关系都是采用投影矩阵完成信息的共享。这种方法的优点是使用同一对投影矩阵来捕获关系，好处是通过建模关系之间的内在相关性来改善泛化能力差的问题；缺点是没很好利用KG中的关系路径信息。

TransE生成的负例三元组大部分都是低质量的问题指的是，在进行知识图谱嵌入(knowledge graph embedding,KGE)的模型训练时，会删除正例三元组中的头实体或者尾实体，再从实体集中随机选择一个实体进行补充，用来生成负例三元组，而生成的这些负例三元组很多都是低质量的。对于这个问题，目前，在链接预测和三元组分类任务做得比较好的主要有一种解决方法，即采用K-means 聚类算法，这种算法简称TransE-SNS方法，算法思想是：先利用K-means聚类算法对KG中的实体进行分组；其次，随机从正例三元组中选择一个实体去换头实体，尾实体也是采用同样的方法进行替换。这种方法的优点是相似性负采样与TransE模型相结合好处是提高了替换实体与被替换实体间的相似性；缺点是相似性负采样对于较为稀疏的大规模KG较难实现相似实体的聚类与采样。

TransE不能快速收敛的问题指的是在进行模型训练时，随机训练的数据，有些会因为不容易训练，造成数据很久得不到训练，导致模型质量不高。针对TransE不能快速收敛的问题，目前，在链接预测和三元组分类任务做得比较好的主要有一种解决方法，即自适应的筛选训练数据方法。这种方法简称AST_NZL方法，算法思想是：首先根据概率选择关系类别，其次从选定的分组中随机选择一个实例进行训练。根据训练效果，对每组实例被选择的概率进行自适应调整。这种方法的优点是加入了“损失非零”机制，好处是以便相对更加准确的估计分组概率；缺点是没有探究关系分组。

边缘识别能力弱的问题指的是关系表示的能力弱，并且其他关系的噪声明显。针对这个问题，目前，在链接预测和三元组分类任务做得比较好的主要有一种解决方法：嵌入通用翻译框架方法。这种方法简称GTrans方法，算法思想是：每个实体由两种状态(本征状态和模仿)组合来解释，本征态表示实体固有拥有的特征，而模仿表示受关联关系影响的特征。尝试首先将每个实体分别建模为两种状态的组合来反映其内在和外在属性，然后通过为不同的实体分配不同的权重来构建动态关系空间。方法的优点是为每个关系构造一个动态关系空间，好处是使模型具有灵活性，而且还减少了来自其他关系空间的噪声；缺点是仅考虑从单个三元组中提取。

总体来看，TransRD方法、TransE-SNS方法、ASTNZL方法、GTrans方法在分别处理TransE泛化能力差、生成的负例三元组大部分都是低质量、不能快速收敛、边缘识别能力弱问题上都发挥了各自的优势，提高了预测的效果。但是，由于这些问题属于TransE领域的难点，因此，关于这方面的研究，取得实质性突破的并不多。今后，这些方面的研究方向将是在上述方法的基础上再结合比较热门的注意力机制，以及卷积神经网络来寻求突破。

# 3 基于TransE的表示学习算法实验

本节介绍目前常用的基于TransE的表示学习算法性能的公用数据集,以及定量地衡量算法性能的各种评价指标，并对前述各种类型的基于TransE表示学习算法进行了分析、总结和比较,最后,通过实验展示各种算法的效果[47-49]。

# 3.1常用数据集

为了科学、一致地评价各类基于TransE的表示学习方法的性能[50],需要使用标准的实体关系数据集进行测试和对比，目前，常用的实体关系数据集见表1,包括：

a)WN18：是WordNet知识库的一个子集，有关系18个，实体 40943 个。b)FB15K：是FreeBase中一个相对稠密的子集，有关系1345个，实体14951个。c)WN11:是WordNet 知识库的一个子集，有关系11个，实体 38696个。d)FB13：是FreeBase 中一个相对稠密的子集，有关系13个，实体75043个。e)FB40K：是FreeBase中一个相对稠密的子集，有关系1336个，实体39528个。f)MPBC_20：有关系20个，实体175624个。g)FB15K-237:是FreeBase 中一个子集，有关系 237个，实体14541个。

表1实体关系常用数据集  
Tab.1Common data sets of entity relationship   

<html><body><table><tr><td>数据集</td><td colspan="5">关系/个 实体/个 训练集/个 验证集/个 测试集[71]/个</td></tr><tr><td>WN18[8]</td><td>18</td><td>40943</td><td>141442</td><td>5000</td><td>5000</td></tr><tr><td>FB15K[8]</td><td>1345</td><td>14951</td><td>483142</td><td>50000</td><td>59071</td></tr><tr><td>WN11[7]</td><td>11</td><td>38696</td><td>112581</td><td>2609</td><td>10544</td></tr><tr><td>FB13[7]</td><td>13</td><td>75043</td><td>316232</td><td>5908</td><td>23733</td></tr><tr><td>FB40K[19]</td><td>1336</td><td>39528</td><td>370648</td><td>67946</td><td>96678</td></tr><tr><td>MPBC_20[26]</td><td>20</td><td>175624</td><td>649439</td><td>73693</td><td>72828</td></tr><tr><td>FB15K-237[28]</td><td>237</td><td>14541</td><td>272115</td><td>17535</td><td>20466</td></tr></table></body></html>

表1列出了用于实体关系的常用数据库集,比较因素包括关系、实体、训练集、验证集、测试集。

# 3.2基于TransE表示学习算法的评价指标

通过对收集到的综述进行分类与整理，将量化表示学习的指标分为正确实体的平均排名、正确实体排在前10名的概率和准确率的评价指标[51\~53]。其中，正确实体的平均排名的评价指标、正确实体排在前10名的概率的评价指标主要是衡量链接预测的效果，准确率的评价指标主要衡量三元组分类的效果[54,55]。

# a）正确实体的平均排名

正确实体的平均排序得分简称MeanRank，此值越小越好，这是衡量链接预测的重要指标[56]。

# b）正确实体排在前10名的概率

正确实体排在前10名的概率简称 $\mathrm { H i t s } @ 1 0$ ，此值越大越好，这是衡量链接预测的重要指标。

# c）准确率

三元组分类任务使用准确率作为评价指标，计算方法如下所示。

$$
\mathrm { A C C } = \frac { T _ { p } + T _ { n } } { N _ { p o s } + N _ { n e g } }
$$

其中， $T _ { p }$ 表示预测正确的正例三元组个数； $T _ { n }$ 表示预测正确的负例三元组个数； $N _ { p o s }$ 和 $N _ { n e g }$ 分别表示训练集中的正例三元组和负例三元组的个数。ACC越高，表示模型在三元组分类这一任务上的效果越好[57\~59]。

# d)运行时间

运行时间t主要比较不同方法的效率，此值越小越好[60,61]。

# 3.3基于TransE的表示学习算法的分析与比较

基于TransE的表示学习典型算法研究工作的分析与比较结果见表2.主要比较因素包括算法分类、算法名称、发表年份、算法测试用数据集、算法评价指标、算法思想、优缺点[62,63]。

# 3.4基于TransE的表示学习算法实验

为了加深对上述基于复杂关系的方法、基于关系路径的方法、基于图像信息方法、基于其他方面的方法中各种算法的理解，本节将会对这些方法的实验进行对比、分析与总结[64-66]。实验选取公测数据集中的模型作为对象，实验分为两部分：第1部分针对链接预测(见表3)，第2部分针对三元组分类(见表4)。

实验的参数设置为：学习速率 $\scriptstyle \alpha = \{ 0 . 0 0 2$ ，0.005，0.01},差距 $\gamma = \{ 0 . 2 5$ ，0.5，1，2}，表示维度 $\kappa = \{ 5 0 , 7 5 , 1 0 0 \}$ ,权重 $\eta$ $= \{ 0 . 0 5$ ，0.0625，0.25，1.0}，训练批次的大小$\mathrm { B } { = } \{ 2 0 , 7 5 , 2 0 0 , 1 2 0 0 , 4 8 0 0 \}$ 。从表3可以看出，在做链接预测实验时，当采用WN18作为实验数据集测试MeanRank时，TransD、NTransGH、TransGraph、PaSKoGE、TransRD、TransE-SNS、GTrans相较于TransE方法效果更好，其中，PaSKoGE方法的效果最好；当测试Hits $@ 1 0$ 时，STransH、TransD、NTransGH、TransGraph、PaSKoGE、TransRD、TransE-SNS、AST_NZL、GTrans的效果相较于TransE方法效果更好，其中，NTransGH效果最好[67-69]。当采用FB15K作为实验数据集测试MeanRank时，STransH、TransD、NTransGH、TransGraph、TransAH、PTransE、PaSKoGE、TCE、TransRD、TransE-SNS、GTrans方法相较于TransE效果更好，其中，TCE 效果最好[70-71]；当测试 $\mathrm { H i t s } @ 1 0$ 时，所有的方法都要好于TransE，但是，PaSKoGE效果最好。综上所述，PaSKoGE方法、TCE方法、NTransGH方法值得去推广，并且今后的研究可以在这两种方法的基础上继续进行拓展，不断提高做链接预测任务的效果。

表2基于TransE 表示学习算法对比  
Tab.2Comparison of representation learning algorithms based on transe   

<html><body><table><tr><td>分类</td><td>名称</td><td>发表年份</td><td>数据集</td><td>评价指标</td><td>算法思想</td><td>优缺点</td></tr><tr><td>TransE方 法</td><td>TransE[8]</td><td>2013</td><td>FB15K、WN18、 FB13、WN11</td><td>MeanRank、Hits@10</td><td>基于欧式距离上的偏移量来衡量实体之 间的语义相似度</td><td>优点：学习的参数少，计 算复 杂 度 低，操作简单。缺点：无法处理 复杂关系、负例三元组的质量低、嵌 入模型不能快速收敛、泛化能力差、</td></tr><tr><td></td><td>STransH[7]</td><td>2019</td><td>FB15K、WN18、</td><td>MeanRank、</td><td>分别在实体空间和关系空间建模，并采优点：引入投影到特定关系超平面的 用单层神经网络的非线性操作来加强实机制。缺点：没有将关系路径考虑在</td><td>边缘识别能力差等</td></tr><tr><td></td><td>TransD[16]</td><td>2015</td><td>FB15K、WN18、 FB13、WN11</td><td>MeanRank、</td><td>体和关系的语义联系 内 使用两个向量来表示命名的符号对象(实 优点：提出一种动态变化矩阵的方 体和关系)。第一个表示一个实体(关系）法，运算速度快。缺点：忽略了关系 Hits@10、ACC的含义，另一个用于动态构造映射矩的内在相关性，参数过多，知识共享</td><td></td></tr><tr><td>基于复杂 关系的方 NTransGH[17]2019</td><td></td><td></td><td>FB15K、WN18、 FB13、WN11</td><td>MeanRank、</td><td>阵。 结合用于将关系建模为广义超平面的翻 译操作的翻译机制，以及用于捕获实体</td><td>困难 优点：引入了两层神经网络来定义得 分函数。缺点：需要操作的参数偏多</td></tr><tr><td>法</td><td>TransGraph[8]2019</td><td></td><td>FB15K、WN18、 FB13、WN11</td><td>MeanRank、 Hits@10、ACC</td><td>与关系之间更复杂交互的神经网络 量和参数的更新</td><td>采用随机梯度下降方法来求解目标函数 优点：融合了KG 的网络结构特征。 L 的最优化问题，通过计算梯度实现向缺点：忽略了实体的描述文本和互联</td></tr><tr><td></td><td>TransAH[18]</td><td>2018</td><td>FB15K、WN18、 FB13、WN11</td><td>MeanRank、</td><td>首先建立特定关系的超平面模型；其 Hits@10、ACC到这种超平面，从而进行实体关系的推 中的抽取，以及实体聚类等方面的任 理</td><td>网文本等信息 优点：引入面向特定关系的超平面模 次，将三元组中的头实体与尾实体嵌入型。缺点：没有考虑在文本关系知识</td></tr><tr><td>基于关系 路径的方 法</td><td>PTransE[19]</td><td>2015</td><td>FB15K、FB40K</td><td>MeanRank、 Hits@10、ACC</td><td>将关系路径视为实体之间的转换，以进 行表示学习，通过关系嵌入的语义组成 来表示关系路径</td><td>务 优点：使用与关系路径连接的实体对 从知识库中构建三元组。缺点：只考 虑直接关系与关系之间的推理模式， 没有考虑关系之间有许多复杂的模式</td></tr><tr><td>基于图像 信息的方</td><td>PaSKoGE[20]</td><td>2018</td><td>FB15K、WN18</td><td>Hits@10、t</td><td>对于每个路径，它通过对任何给定实体 对的关系和多步关系路径之间的相关性 进行编码，来自适应地确定其基于边际 的损失函数 采用翻译嵌入模型 TransE与动态映射矩 优点：使多模态数据能够嵌入到低维</td><td>优点：提出了特定于路径的嵌入方 法。缺点：需要花费更多的时间来另 外计算路径特定的余量</td></tr><tr><td>法</td><td></td><td>2019</td><td>WN9-IMG</td><td></td><td>Hits@10、Hits@1 习模型，使多模态数 据能够嵌入到低维到的对齐实体未进行置信度评估，迭</td><td>阵嵌入模型 TransD 相结合的知识表示学 语义空间。缺点：对迭代过程中新找</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>FB13、WN11</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>MPBC_20</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>语义空间</td><td>代效果偏低</td></tr><tr><td></td><td>TCE[22]</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>2017</td><td>FB15K</td><td></td><td></td><td>优点：能很好利用KG中的结构，特</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>MeanRank、Hits@10利用了KG中每个三元组的上下文</td><td>别是三元组周围的局部结构。缺点：</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>在基线上不如经典的翻译模型</td></tr><tr><td></td><td>TransRD[26]</td><td>2019</td><td>FB15K、WN18、</td><td>MeanRank、Hits@10</td><td>对头尾实体进行投影，并在其中嵌入不</td><td>优点：使用同一对投影矩阵来捕获关</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>对等转换矩阵</td><td>系。缺点：没很好利用KG中的关系</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>路径信息</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>先利用 K-Means 聚类算法对 KG 中的实 优点：将相似性负采样与 TransE 模型</td><td></td></tr><tr><td>基于其他</td><td>TransE-</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>FB15K、WN18、</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>2019</td><td></td><td></td><td>体进行分组；其次，随机从正例三元组相结合。缺点：相似性负采样对于较</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>MeanRank、Hits@10</td><td></td><td></td></tr><tr><td>方面的方</td><td>SNS[27]</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>中选择一个实体去换头实体，尾实体也为稀疏的大规模KG 较难实现相似实</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>法</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>是采用同样的方法进行替换</td><td>体的聚类与采样</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>FB15K-237、</td><td></td><td>根据概率选择关系类别，其次从选定的优点：加入了"损失非零"机制。</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>AST_NZL[28]2019</td><td></td><td>MeanRank、Hits@10</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>FB15K、WN18</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>分组中随机选择一个实例进行训练</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>缺点：没有探究关系分组</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td></table></body></html>

从表4可以看出，在做三元组分类实验时，当采用WN11时，STransH、TransD、NTransGH、TransGraph、TransAH、TransE-SNS相较于TransE方法效果更好，其中，NTransGH效果最好；当采用FB13时，STransH、TransD、NTransGH、TransGraph、TransAH、TransE-SNS相较于TransE方法效果更好，其中，TransD效果最好；当采用FB15时，STransH、TransD、NTransGH、TransAH、TransE-SNS相较于TransE方法效果更好，其中，NTransGH 效果最好[72-73]。综上所述，NTransGH方法和TransD方法值得推广，并且今后的研究可以在这两种方法的基础上继续进行拓展，不断提高做三元组

分类任务的效果。

Tab.3Link prediction experiment results   

<html><body><table><tr><td rowspan="3">Method</td><td colspan="3">WN18</td><td colspan="4">FB15K</td></tr><tr><td colspan="6">MeanRank(名次)Hits@10(%)MeanRank(名次)Hits@10(%)</td></tr><tr><td>Raw</td><td>Filt</td><td>Raw</td><td>Filt</td><td>Raw</td><td>Filt</td><td>Raw Filt</td></tr><tr><td>TransE[8]</td><td>263</td><td>251</td><td>75.4</td><td>89.2</td><td>243 125</td><td>34.9</td><td>47.1</td></tr><tr><td>STransH[7]</td><td>347</td><td>330</td><td>77.1</td><td>90.6</td><td>196</td><td>68</td><td>46.6 69.5</td></tr><tr><td>TransD[16]</td><td>224</td><td>212</td><td>79.6</td><td>92.2</td><td>194</td><td>91</td><td>53.4 77.3</td></tr><tr><td>NTransGH[17]</td><td>165</td><td>150</td><td>87.1</td><td>97.8</td><td>139</td><td>51</td><td>61.7 85.6</td></tr><tr><td>TransGraph[8]</td><td>181</td><td>170</td><td>83.6</td><td>92</td><td>153</td><td>67</td><td>58.3 81.6</td></tr><tr><td>TransAH[18]</td><td>182</td><td>171</td><td>72.8</td><td>82.9</td><td>141</td><td>65</td><td>58.1 82.4</td></tr><tr><td>PTransE[19]</td><td></td><td></td><td></td><td></td><td>207</td><td>58</td><td>51.4 84.6</td></tr><tr><td>PaSKoGE[20]</td><td></td><td>81.3</td><td></td><td>95.0</td><td>-</td><td>53.1</td><td>88.0</td></tr><tr><td>ITMEA[21]</td><td>，</td><td></td><td>，</td><td></td><td></td><td></td><td>-</td></tr><tr><td>TCE[22]</td><td></td><td></td><td></td><td>-</td><td>110</td><td>25</td><td>55.3 83.1</td></tr><tr><td>TransRD[26]</td><td></td><td>194</td><td></td><td>95.5</td><td></td><td>68</td><td>78.9</td></tr><tr><td>TransE-SNS[27]</td><td>220</td><td>208</td><td>80.2</td><td>94.0</td><td>198</td><td>56</td><td>48.9 80.1</td></tr><tr><td>AST_NZL[28]</td><td></td><td>490</td><td>，</td><td>93.2</td><td></td><td>142</td><td>= 71.4</td></tr><tr><td>GTrans[29]</td><td>215</td><td>202</td><td>80.2</td><td>93.5</td><td>189</td><td>85</td><td>52.9 75.3</td></tr></table></body></html>

表4不同模型的三元组分类精度

表3链接预测实验结果  
Tab.4Classification accuracy of triples of different models   

<html><body><table><tr><td>method</td><td>WN11(%)</td><td>FB13(%)</td><td>FB15K(%)</td></tr><tr><td>TransE[8]</td><td>75.9</td><td>70.9</td><td>79.7</td></tr><tr><td>STransH[7]</td><td>79.6</td><td>85.2</td><td>89.6</td></tr><tr><td>TransD[16]</td><td>86.4</td><td>89.1</td><td>88.0</td></tr><tr><td>NTransGH[17]</td><td>88.8</td><td>87.5</td><td>92.9</td></tr><tr><td>TransGraph[8]</td><td>83.7</td><td>86.5</td><td>-</td></tr><tr><td>TransAH[18]</td><td>83.8</td><td>84.5</td><td>89.2</td></tr><tr><td>PTransE[19]</td><td></td><td>-</td><td>-</td></tr><tr><td>PaSKoGE[20]</td><td></td><td>-</td><td>-</td></tr><tr><td>ITMEA[21]</td><td></td><td></td><td></td></tr><tr><td>TCE[22]</td><td></td><td></td><td>-</td></tr><tr><td>TransRD[26]</td><td></td><td></td><td>-</td></tr><tr><td>TransE-SNS[27]</td><td>83.2</td><td>87.1</td><td>86.6</td></tr><tr><td>AST_NZL[28]</td><td></td><td></td><td>-</td></tr><tr><td>GTrans[29]</td><td>84.0</td><td>87.1</td><td>95.5</td></tr></table></body></html>

# 4 总结与展望

如今,基于TransE的表示学习方法已成为KG表示学习研究的热点。本文对基于TransE的表示学习方法进行了较为科学、合理的分析与总结,对基于复杂关系的方法、基于关系路径的方法、基于图像信息的方法和基于其他方面的方法分别进行了介绍，对每类方法中的代表性算法进行了研究、分析和对比,指出了其特点。从研究结果来看，PaSKoGE方法、NTransGH方法、TCE方法和TransD方法在做链接预测和三元组分类任务上表现效果最好，值得推广和进一步拓展，并可在其特定于路径的嵌入、两层神经网络、三元组上下文、动态构造映射矩阵上进一步完善。在现有研究成果的基础上，该文认为,在基于TransE的表示学习方法方面,还存在以下的研究趋势。

# 1)基于高斯混合嵌入的方法

TransE方法还会遇到多重关系语义问题，这种问题指的是一个关系可能具有与对应的三元组关联的实体对存在多种含义。当前的许多方法在处理基于多重关系语义问题时，表现的效果不明显。因此，该文提出了一种新颖的嵌入高斯混合模型TransGM。这种模型的思想是在TransE基础上充分利用关系分量向量的混合，不断进行嵌入事实三元组的训练。

大量实验表明，这种模型仍有待进一步提高。

2)基于单层神经网络的更少参数的方法

可以通过使用深度神经网络模型增强实体描述的嵌入来扩展TransE。但是，使用这种方法需要额外的空间来存储内层的参数，并且依赖于更多的超参数进行调整。因此，该文创建了一个单层的更少参数的模型。该模型通过最大化观察到的知识的对数似然性，测量每个三元组的概率以及相应的实体描述，并同时学习实体，关系和描述中单词的上下文嵌入。实验表明，该模型在学习更好的知识库分布式表示时有一定的研究意义。

3)基于在单独的实体空间和关系空间中构建实体和关系嵌入的方法

诸如TransE之类的模型通过将关系视为从头实体到尾实体的翻译来构建实体和关系嵌入，这些模型只是将实体和关系放在相同的语义空间内。实际上，一个实体可能具有多个方面，各种关系可能集中在实体的不同方面，这使得公共空间不足以进行建模。因此，该文建议TransR在单独的实体空间和关系空间中构建实体和关系嵌入。之后，通过将实体从实体空间投影到对应的关系空间，然后在投影的实体之间建立翻译来学习嵌入。实验证明，这种模型仍然需要进一步得到完善。

# 5 结束语

TransE模型除了存在无法有效处理一对多、多对一、多对多的关系,以及自反关系，还存在处理图像信息效果差、负例三元组的质量低、嵌入模型不能快速收敛、泛化能力差、边缘识别能力差等问题。针对这些问题，该文以TransE方法存在问题为分类标准，将基于TransE的表示学习方法分为基于复杂关系的方法、基于关系路径的方法、基于图像信息的方法，以及基于其他方面的方法这4种类型。为了对比每种方法的有效性，分别在链接预测和三元组分类实验上做了对比分析，下一步将在实体对齐上进行有效性的测试。

# 参考文献：

[1]Sabina K,Leonids N,Natalya P,Vladimir U.Colleen Heinemann. Intelligent Collaborative Educational Systemsand Knowledge Representation [J].Procedia Computer Science,2017(104):166-173.   
[2]Kargin A,Petrenko T.Knowledge Representation in Smart Rules Engine [C]// 2019 3rd International Conference on Advanced Information and Communications Technologies(AICT),Lviv:IEEE Press,2019:231- 236.   
[3]Ren Lijuan,Lu Jun,Guo Wei.Multi-source Knowledge Embedding Research of Knowledge Graph [C]// 2019 IEEE 3rd International Conference on Circuits.Ukraine:Systems and Devices (ICCSD),2019: 163-166.   
[4]Cesar S,Zhang Haoxi, Imran S,Md MW, Caterine Silva de Oliveira, Edward Szczerbicki. Experience based knowledge representation for Internet of Things and Cyber Physical Systems with case studies [J]. Future Generation Computer Systems,2019 (92):604-616.   
[5]Miao Fan, Qiang Zhou,Thomas F Z,Ralph G.Distributed representation learning for knowledge graphs with entity descriptions [J].Pattern Recognition Letters,2017(93):31-37.   
[6]Duc-Hong P,Anh-Cuong L.Learning multiple layers of knowledge representation for aspect based sentiment analysis [J].Data& Knowledge Engineering,2018 (114): 26-39.   
[7]陈晓军，向阳.STransH:一种改进的基于翻译模型的知识表示模型 [J].计算机科学,2019,46 (09):184-189.(Chen Xiaojun,Xiang Yang. STransH: an improved knowledge representation model based on translation model[J]. Computer science,2019,46 (09): 184-189.)   
[8] 陈文杰，文奕，张鑫，杨宁，赵爽．一种改进的基于 TransE 的知识 图谱表示方法[J].计算机工程,2019(11):1-8.(ChenWenjie,Wen Yi, Zhang Xin,Yang Ning,Zhao Shuang.An improved representation method of knowledge map based on Transe [J]. Computer Engineering 2019 (11): 1-8.)   
[9]Li Wang,Fernanda L.Formalized knowledge representation for spatial conflflict coordination of mechanical, electrical and plumbing (MEP) systems in new building projects [J].Automation in Construction, 2016 (64): 20-26.   
[10] Yuxin Ding，Rui Wu，Xiao Zhang.Ontology-based knowledge representation for malware individuals and families [J]. Computers & Security,2019 (87): 101574.   
[11] Marina I,Miran P, Slobodan R.Two-tier image annotation model based on a multi-label classififier and fuzzy-knowledge representation scheme [J].Patterm Recognition,2016 (52): 287-305.   
[12] David R, Mor P,Anette T. Ten years of knowledge representation for health care (2009-2018): Topics,trends,and challenges [J].Artificial Intelligence In Medicine,2019 (100):101713.   
[13] Zhang Qin. Dynamic Uncertain Causality Graph for Knowledge Representation and Reasoning:Utilization of Statistical Data and Domain Knowledge in Complex Cases [J].IEEE Transactions on Neural Networks and Learning Systems,2018,29 (5): 1637-1651.   
[14] Philippe C, Stephane N, Ludovic M. Flexible knowledge representation and new similarity measure:Application on case based reasoning for waste treatment [J]. Expert Systems With Applications,2016 (58): 143- 154.   
[15] Bart B,Joost V,Marc D.Safe inductions and their applications in knowledge representation[J].Artifificial Intellgence,2018 (259)167 185.   
[16] Dou Jinhua, Qin Jingyan, Zanxia,Jin Zhuang li,Knowledge graphbased on domain ontology and natural language processing technology for Chinese intangible cultural heritage [J]. Journal of Visual Languages & Computing,2018 (48): 19-28.   
[17] Zhu Qiannan, Zhou Xiaofei, Zhang Peng, Shi Yong.A neural translating general hyperplane for knowledge graph embedding[J]. Journal of Computational Science,2019 (30): 108-117.   
[18]方阳，赵翔，谭真，杨世宇，肖卫东．一种改进的基于翻译的知识图 谱表示方法[J].计算机研究与发展,2018(55):139-150.(Fang Yang, Zhao Xiang,Tan Zhen, Yang Shiyu, Xiao Weidong.An improved representation method of knowledge map based on translation [J]. Computer research and development,2018 (55): 139-150.)   
[19] Lei Zhenfeng,Sun Yuan,et al. A novel data-driven robust framework based on machine learning and knowledge graph for disease classification [J].Future Generation Computer Systems,2020 (102): 534-548.   
[20] Jia Yantao, Wang Yuanzhuo,Jin Xiaolong, Cheng Xueqi. Path-specific knowledge graph embedding [J]. Knowledge-Based Systems,2018 (151): 37-44.   
[21]王会勇，论兵，张晓明，孙晓领．基于联合知识表示学习的多模态实 体对齐[J].控制与决策.2019:1-10.(Wang Huiyong,Lun Bing,Zhang Xiaoming,Sun Xiaoling. Multimodal entity alignment based on joint knowledge representation learning [J]. Control and decision. 2019: 1-10.)   
[22] Gao Shiun, Qi Huan, Zhou Guilin, Zhang Quan. Knowledge Graph Embedding with Triple Context[J]. CIKM，2017: 2299-2302.   
[23] Khalil A, Xu Dongling,Chen Yuwang. Anew beliefrule base knowledge representation scheme and inference methodology using the evidential reasoning rule for evidence combination [J]. Expert Systems With   
[24] Liu Huchen,Xue Luan,L1 Zhiwu,Wu Jianing.Linguistic Petri Nets Based on Cloud Model Theory for Knowledge Representation and Reasoning [J]. IEEE Transactions on Knowledge and Data Engineering, 2018,30 (4): 717-728.   
[25]Pan Yunhe.Multiple Knowledge Representation ofArtificial Intelligence [J].Engineering,2019 (3): 2095-8099.   
[26]朱艳丽，杨小平，王良，张志宇.TransRD:一种不对等特征的知识 图谱嵌入表示模型[J]．中文信息学报,2019,33(11):73-82.(Zhu Yanli,Yang Xiaoping,Wang Liang,Zhang Zhiyu. TransRD:a knowledge map embedding representation model with unequal features [J]. Chinese Journal of information technology,2019,33 (11): 73-82.)   
[27]饶官军，古天龙，常亮，宾辰忠，秦赛歌，宣闻．基于相似性负采样 的知识图谱嵌入[J].智能系统学报,2019,23(10):1-9.(Rao Guanjun, Gu Tianlong,Chang Liang,Bin Chenzhong,Qin Saige,Xuan Wen. Knowledge map embedding based on similarity negative sampling [J]. Journal of intelligent systems,2019,23(10):1-9.)   
[28]欧阳丹彤，马聰，雷景佩，冯莎莎．知识图谱嵌入中的自适应筛选 [J].吉林大学学报（工学版),2019:1-8.(Ouyang Dantong,Ma Xiang, Lei Jingpei, Feng Shasha.Adaptive selection in knowledge map embedding[J].Journal of Jilin University (Engineering Edition),2019: 1-8.)   
[29] Zhen Tan, Xiang Zhao,Yang Fang,Xiao Weidong. GTrans: Generic Knowledge Graph Embedding via Multi-State Entities and Dynamic Relation Spaces [J]. IEEE Access,2018 (6): 2169-3536.   
[30] Katrin J，André B. Semi-automated site equipment selection and confifiguration through formal knowledge representation and inference [J]. Advanced Engineering Informatics,2018 (38): 488-500.   
[31] Loredana C，Giuseppe P,Genoveffa T，Daniele I.A knowledge representation framework to enhance automatic video surveillance [J]. Expert Systems With Applications,2019 (131): 190-207.   
[32] Tang Xing, Chen Ling, Cui Jun, Wei Baogang. Knowledge representation learning with entity descriptions,hierarchical types,and textual relations [J].Information Processing and Management,2019 (56): 809-822.   
[33] Zheng Weiguo,Cheng Hong,Jeffrey X Y, Zou Lei, Zhao Kangfei, Interactive natural language question answering over knowledge graphs [J].Information Sciences,2019 (481): 141-159.   
[34] Xaro B,Angel C,Esther V,Ana G S,Juan C. FCA-based knowledge representation and local generalized linear models to address relevance and diversity in diverse social images [J]. Future Generation Computer Systems,2019 (100) 250-265.   
[35] Pablo AQ,Jessica CM, Concepcion R,Juan C M.Abody of knowledge representation model of ecotourism products in southeastern Ecuador [J]. Heliyon,2018 (4): 1063.   
[36] Nie Binling,Sun Shouqian, Knowledge graph embedding via reasoning over entities,relations,and text [J].Future Generation Computer Systems,2019 (91): 426-433.   
[37] Zhang Wen. Knowledge Graph Embedding with Diversity of Structures [C]./In Proceedings of the 26th International Conference on World Wide Web Companion(WWW'17 Companion）.International World Wide Web Conferences Steering Committe, Republic and Canton of Geneva, CHE, 2017: 747-753.   
[38] Xia Xiaoqiang, Zhang Dehai,Liu Qing, Wang Yanpeng, Cui Menglong. Synergistic Union of Word Embedding and Knowledge Graph for Words Semantic Similarity Measure [C]./2018 IEEE 4th International Conference on Computer and Communications (ICCC),Chengdu, China 2018:2349-2353.   
[39] Guan Niannian,Song Dandan,Liao Lejian,Knowledge graph embedding [J].IEEE Access,2019(7): 26466-26473.   
[41] Arpad G,drianF,UgoF,PaoloZ,LucianV.Performanceandeerg optimisation in CPUs through fuzzy knowledge representation [J]. Information Sciences,2019 (476): 375-391.   
[42] Liu Wenqiang,LiuJun,Wu Mengmeng,Samar A,Hu Wei, Wei Bifan, Zheng Qinghua.Representation learning over multiple knowledge graphs for knowledge graphs alignment [J]. Neuro computing，2018 (320): 12-24.   
[43] David P, Sun Yu.A Survey of Knowledge Representation in Service Robotics [J].Robotics and Autonomous Systems,2019 (118): 13-30.   
[44] Debarpita S,Swapan K B,Jyotsna K M, Subrata G. Rough set based lattice structure for knowledge representation in medical expert systems: Low back pain management case study [J]. Expert Systems With Applications,2020 (145): 113084.   
[45] Kaushalya K,Nikola K, Denise T.Deep learning and deep knowledge representation in Spiking Neural Networks for Brain-Computer Interfaces [J]. Neural Networks,2020 (121): 169-185.   
[46] Ji Guoliang,Liu Kang,He Shizhu,Zhao Jun．Knowledge Graph Completion with Adaptive Sparse Transfer Matrix [C]// Proceedings of the Thirtieth AAAI Conference on Artificial Intelligence. Arizona: AAAI Press, 2016: 985-991.   
[47]姜枫，顾庆，郝慧珍，李娜，郭延文，陈道蓄．基于内容的图像分割 方法综述[J].软件学报,2017,28(01):160-183.(Jiang Feng,Gu Qing, Hao Huizhen,Li Na,Guo Yanwen, Chen Daochu. Overview of contentbased image segmentation methods [J]. Journal of software,2017, 28 (01): 160-183.)   
[48] Wang Fan,Li Heng，Dong Chao，Ding Lieyun. Knowledge representation using non-parametric Bayesian networks for tunneling risk analysis [J]. Reliability Engineering and System Safety,2019 (191): 106529.   
[49] Didem G,Aneta VF, Jad E, Swarup KM. Knowledge Representation of Cyber-physical Systems for Monitoring Purpose [J]. Procedia CIRP, 2018 (72): 468-473.   
[50] A E Suleimankadieva,V I Pilipenko,J Sägi. Knowledge Company: Approaches to Assessing New Knowledge and Representation it to Society [J].Procedia Computer Science,2019 (150): 730-736.   
[51] Han Xiao,Zhang Chunhong,SunTing,Ji Yang,Hu Zhen.A TripleBranch Neural Network for Knowledge Graph Embedding [J]. IEEE Access,2018 (6): 76606-76615.   
[52] Qiu Jiangnan，Zuo Min,Yan Shunin,Shi Huayan.A qualitative knowledge representation model and application for crisis events [J]. Procedia Computer Science,2018 (126):1828-1836.   
[53] Pridi S,Nathalie J,Peter H,George M.A general framework dedicated to computational morphogenesis Part II-Knowledge representation and architecture [J].BioSystems,2018 (173): 314-334.   
[54] Nathaniel R,Philip M,Fernbach,Steven A. Sloman．Individual Representation in a Community of Knowledge [J]. Trends in Cognitive Sciences,2019 (23): 10.   
[55] Manuel C,Juan C,Darren P,John A.A new paradigm for uncertain knowledge representation by Plausible Petri nets [J]. Information Sciences,2018 (453): 323-345.   
[56] Masita,Masila A J,Chia P L,Noor M M,Fatihah M.Knowledge Representation Model for Crime Analysis [J]. Procedia Computer Science,2017 (116): 484-491.   
[57] Amelec V,Omar B P.An intelligent approach for the design and Procedia Computer Science,2019 (151): 1225-1230.   
[58] Honoreé-Chedozeau C,Lelievre-Desmas M，Ballester J，Cholet S, Valentin D. Knowledge representation among assessors through free hierarchical sorting and a semi-directed interview: Exploring Beaujolais wines [J].Food Quality and Preference,2017(57):17-31.   
[59]Qi Jinda，Ding Lan，SamsungL．Ontology-based knowledge representation of urban heat island mitigation strategies [J]. Sustainable Cities and Society,2020 (52): 101875.   
[60] Liu Huchen,You Jianxin,Li Zhiwu,Tian Guangdong.Fuzzy Petri nets for knowledge representation and reasoning:A literature review [J]. Engineering Applications of Artificial Intelligence,2017 (60): 45-56.   
[61] Giovannini A,Aubry A,Panetto H, Haouzi H. Associated Professor, O Canciglieri Junior Full Professor,L.Pierrel Phd Business Analyst. Knowledge representation,retrieval and reuse for product family design: Ananti-logicist approach[J].Computers & Industrial Engineering,2016 (101): 391-402.   
[62] J Montero,H Bustince,C Franco,J.TRodriguez,D Gómez,MPagola, JFernandez，E Barrenechea. Paired structuresin knowledge representation [J]. Knowledge-Based Systems,2016 (100): 50-58.   
[63] Zhao Chao,Jiang Jingchi,Guan Yi,Guo Xitong,He Bin. EMR-based medical knowledge representation and inference via Markov random fifieldsand distributed representation learning [J].Artifificial Intelligence in Medicine,2018 (87): 49-59.   
[64] Yang Li, Geng Xinyu, Cao Xiedong. A novel knowledge representation model based on factor state space[J]. Optik,2016 (127): 5141-5147.   
[65] Paul W,Paul M, Trevor C,Enrico M. Improving comprehension of knowledge representation languages: A case study with Description Logics[J].International Journal of Human-Computer Studies,2019 (122): 145-167.   
[66] Han Xiao,Zhang Chunhong，Guo Chenchen,Ji Yang，Zheng Hu. Distributed representation of knowledge graphs with subgraph-aware proximity [J]. Theoretical Computer Science,2020 (803): 48-56.   
[67] Xiao Han, Huang Minlie,Zhu Xiaoyan. TransG: A Generative Model for Knowledge Graph Embedding [J]. Computer Science,2016 (1): 2316- 2325.   
[68] Zhang Yi，Cao Wanhua，Liu Juntao.A Novel Negative Sample Generating Method for Knowledge Graph Embedding [C]./In Proceedings of the 2019 International Conference on Embedded Wireless Systems and Networks.Junction Publishing,USA,2019: 401-406.   
[69] KoheiI，YukihisaK,ShinsukeK，AtsushiS,Structuring engineers'implicit knowledge offorming process design by using a graph model [J],Procedia CIRP,2018 (67): 563-568.   
[70]王会勇，论兵，张晓明，孙晓领．基于联合知识表示学习的多模态实 体对齐[J]．控制与决策.2019:1-10.(Wang Huiyong,Lun Bing,Zhang Xiaoming,sun Xiaoling.Multimodal entity alignment based on joint knowledge representation learning [J]. Control and decision.2019:1-10.)   
[71] Gayathri R, VUma. Ontology based knowledge representation technique, domain modeling languages and planners for robotic path planning:A survey [J]. ICT Express,2018 (4): 69-74.   
[72] Wu Zhenyong,Liao Jihua, Song Wenyan, Mao Hanling,Huang Zhenfeng, Li Xinxin，Mao Hanying.Semantic hyper-graph-based knowledge representation architecture for complex product development [J]. Computers in Industry,2018 (100): 43-56.   
[73] Guo Shu,Wang Quan,Wang Bin,Wang Lihong. SSE: Semantically Smooth Embedding for Knowledge Graphs [J].IEEE Transactions on Knowledge and Data Engineering,2017 (29): 884-897.