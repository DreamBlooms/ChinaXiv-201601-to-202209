# 融合元数据及Attention机制的深度联合学习推荐

张全贵，李志强，张新新，曹志强(辽宁工程技术大学 电子与信息工程学院，辽宁 葫芦岛 125105)

摘要：融合元数据的协同过滤推荐即混合推荐算法是目前推荐系统领域研究的热点，能一定程度地解决数据稀疏及冷启动等问题。但融合元数据现有的建模方法大多数建立于用户/项目属性权重相同的情景下，以致于用户项目间重点关系表达不显著，难以获得较好的推荐性能。针对上述问题，提出一种融合元数据及Attention机制的深度联合学习推荐方法。它利用双深度网络联合学习，其中一个网络基于隐反馈数据实现矩阵非线性分解以学习用户/项目个性化关系，另一个利用 Attention 机制自动捕捉用户/项目关键属性对推荐工作的影响，通过赋予不同属性权重凸显的用户偏好关系建模辅以扩展模型。实验结果表明，所提出的推荐算法在MovieLens100K和MovieLens1M两个公开数据集上均表现出较为优越的推荐性能。

关键词：元数据；属性权重；Attention 机制；深度联合学习；非线性分解 中图分类号：TP182 doi: 10.3969/j.issn.1001-3695.2018.04.0285

# Deep Joint learning recommendation based on metadata and Attention mechanism

Zhang Quangui, Li Zhiqiang, Zhang Xinxin, Cao Zhiqiang (SchoolElectronics&Information Engineering LiaoningTechnical University,Huludao Liaoningl25105,China)

Abstract: Colaborative filteringrecommendation,which combines metadata,isahot topic inrecommender systems,which can solvedatasparsityandcold-startproblems to some extent.However,mostoftheexisting modeling methodsofcombines metadataare based onthe same user/item atribute weights,so that the keyrelationshipsbetween usersand items are not significant,and itisdificulttoobtain beterrecommendationperformance.Tosolvetheaboveproblems,thispaperproposes methodofdepjointlearningrecommendationbasedon metadataandattention mechanism.Ituses double dep network learning, one of the networks implements matrix nonlinear decomposition basedon implicit feedback data to learn user/project personalizationrelationships.，andanother network automaticallycapture affct theuser/item keyatributes torecommend by using Atention mechanism,through theuser preferencerelation with weights ofdiferent atributes modeling highlights the extended model.Experimental results show that theproposed recommendation algorithm hasbeterrecommendation performance on two public datasets of MovieLens 1ooK and MovieLens 1M.

Key Words: metadata; attribute weight; Atntion mechanism; deep joint learning; nonlinear factorization

# 0 引言

推荐系统是通过估测用户需求来缓解信息超载问题的一种技术，被广泛应用在新闻网站、社交媒体及电子商务等领域。美国专家Resnick于1997率先提出“推荐系统”这一概念，之后推荐系统在学术界和工业界均引起巨大的关注，相继不同的推荐机制被研究者提出，并成为推荐系统学术领域的研究热点。

在现存方法中，协同过滤推荐已经被广泛研究和扩展，如Koren、Paterek、Lee 等人[l\~3]提出的基于传统的矩阵分解模型的协同过滤算法。此后研究人员还试图通过元数据建模以扩展矩阵分解模型即所谓的混合推荐，能在一定程度上解决稀疏性和冷启动问题。如Fu等人[4从不同视角度量元数据中用户/项目潜在的个性化关系，利用这种关系扩展矩阵分解模型以实现推荐；Li等人[5]提出物品耦合关系的相似性计算方法，然后将其整合到矩阵分解方法以提升推荐性能。但以上已有的方法均属于浅层模型，不能发现更为抽象的复杂交互关系。

而如今利用深度学习技术建立深层模型已广泛地应用在推荐系统领域[6]，它可以有效地捕获非线性和复杂的用户/项目关系以表示更复杂、抽象的数据结构。如Chang 等人[7]人通过在传统的协同过滤算法中应用神经网络算法达到了提高推荐质量的目的。文献中的CCCFNet也是双网络（协同过滤和内容信息）[8]，它模拟用户项目之间的相互作用在顶层的点积实现推荐工作。Guo等人[是一个无缝集成的分解机和MLP的端到端的模型。它通过因子分解机利用深层神经网络和低阶相互作用对高阶特征相互作用进行建模。He 等[10]也利用多层深度网络替代矩阵线性分解机制实现非线性分解，一定程度地解决了线性MF的局限性。但上述几种模型捕捉的是全部属性间的交互，但在实际应用中，部分交互是没有必要的。例如图1所示，学习用户/项目群体划分时，用户职业、项目类别等是关键的划分特征，而性别、地域等信息是非重要划分成分。另一个方面，以上现有的融合元数据建模方法大多数建立于用户/项目属性权重相同的情景下，即属性的值从模型的开始训练到结束都是不变的，忽视了用户/项目不同属性对推荐工作的影响，以致于用户项目间重点关系表达不显著，大大地降低了推荐模型的性能。因此研究人员逐渐认清无论模型是如何构建的，属性都在其中起着决定性的作用。

![](images/b27d50139f7595a90bde23567eff7c2d8faec0d7c995b7006415cf925d64875b.jpg)  
图1不同属性占比影响

近些年，Attention网络被研发并逐渐成为捕获全局信息的技术手段。因此，基于Attention机制的神经网络在各个领域成为一个热点，是解决上述问题的有效方法之一。如Luong 等[11]在自然语言处理领域使用Attention机制对所有词分配不同权值实现翻译工作。google mind 团队[12]在计算机视觉领域使用Attention 机制自动捕捉图像局部特征实现图像分类。文献[13]提出一种基于注意力机制的融合性深度神经网络，将Twitter 和用户兴趣之间的用户、作者、用户兴趣相似性信息融合作为学习属性实现预测用户的转发行为。但基于attention机制的应用在推荐领域中却少之又少。接下来，我们将这种思想应用于推荐系统领域中，即假设用户具有五个属性值e1、e2、e3、e4、e5，它们对推荐作用的权重为w1、w2、w3、w4、w5，在不加入attention情况下，权重w1\~w5是相同的，则总体的影响作用为 $\mathrm { e 1 } ^ { * } \mathrm { w } 1 + \mathrm { e } 2 ^ { * } \mathrm { w } 2 + \mathrm { e } 3 ^ { * } \mathrm { w } 3 + \mathrm { e } 4 ^ { * } \mathrm { w } 4 + \mathrm { e } 5 ^ { * } \mathrm { w } 5 ,$ 。反之加入时，attention模型根据数据学习出当前用户的属性的对当前推荐的不同影响因子ml、m2、m3、m4、m5，最后总体的影响作用$\mathrm { e l } ^ { * } \mathrm { m } 1 ^ { * } \mathrm { w } 1 + \mathrm { e } 2 ^ { * } \mathrm { m } 2 ^ { * } \mathrm { w } 2 + \mathrm { e } 3 ^ { * } \mathrm { m } 3 ^ { * } \mathrm { w } 3 + \mathrm { e } 4 ^ { * } \mathrm { m } 4 ^ { * } \mathrm { w } 4 + \mathrm { e } 5 ^ { * } \mathrm { m } 5 ^ { * } \mathrm { w } 5 .$

据此，本文提出融合元数据及Attention机制的深度联合学习推荐方法，将新型Attention网络特征学习推理和深度网络分解机功能相结合，形式化用于协同过滤的建模方法来解决上述研究问题。我们通过利用双深度网络联合学习实现预测推荐，其中一个网络基于隐式反馈数据实现矩阵非线性分解以学习用户/项目个性化关系，另一个利用Attention机制自动捕捉用户/项目关键属性对推荐工作的影响，通过赋予不同属性动态权重凸显用户偏好关系，能有效地挖掘出属性有用的隐含特征，从而减少特征冗余、盲目交互等带来的消极影响。本文算法在MovieLens100K和1M两个公开数据集上进行验证。最终实验结果表明所提出的算法均表现出较为优越的推荐性能。

# 1 算法概述

融合元数据及Attention机制的深度联合学习推荐算法（简称DJRMA）是将Attention网络特征学习推理和深度网络分解机相结合，通过学习个性化关系及挖掘元数据隐含关系来提升推荐模型的性能。如图2所示，左侧分解机制网络模型基于隐反馈数据且利用深度网络代替矩阵线性分解实现非线性分解，以学习用户/项目的个性化偏好。右侧模型利用Attention机制自动捕捉用户/项目关键属性对推荐工作的影响，通过赋予不同属性权重凸显的用户偏好关系建模辅助扩展模型。其核心思想是在原有的用户/项目交互矩阵基础上加上已排除干扰噪声的用户个性化向量与项目个性化向量乘积重构后的用户/项目交互矩阵，进而形成新的联合交互矩阵以实现预测推荐。

![](images/4dd38ccfda42119d256d8336fd1fe6c5ceb3698fe3c7000ff38f53da2d486c34.jpg)  
图2本文推荐算法实验模型

# 1.1 深度分解机制

深度分解机制是基于隐式反馈数据利用多层深度网络替代矩阵线性分解机制实现非线性分解，以学习用户项目的个体个性化关系。底部输入层分别由描述用户 $\boldsymbol { u }$ 和项目 $i$ 的两个特征向量组成，它们可被定制以支持用户和项目的广泛建模。在本文中，为了更方便说明问题，我们只采用用户/项目ID作为输入通用特征，而模型根据实际可以有不同的输入。其次，输入层的上方是嵌入层，如图3所示其将用户/项目ID这种稀疏向量映射成稠密向量，获得到的用户/项目特征向量可以被看作在潜在因素模型上下文中用户/项目潜在的特征。

![](images/217da28824c43db1fa96e402c69edd54facf29feb5c57cc8349b88f1db3996e0.jpg)  
图3稀疏向量映射稠密向量

因此，定义深度分解模型如下：

$$
\hat { y } _ { u i } ^ { 1 } = f \bigg ( V _ { u } ^ { U } , V _ { i } ^ { I } \Big | U , I , \theta \bigg )
$$

其中： $U \in { \boldsymbol { R } } ^ { M \times K }$ 和 $I \in { \cal R } ^ { N \times K }$ 分别表示用户和项目的潜在因素矩阵， $M$ 、 $N$ 和 $K$ 为用户、项目和潜在特征数量； $\theta$ 表示$f$ 函数的模型参数。接下来，稀疏向量用户（项目）ID通过嵌入层映射成稠密向量，即用户/项目的特征向量。我们使用$V _ { u } ^ { U }$ 和 $V _ { i } ^ { I }$ 分别为用户 $u$ 和项目 $i$ 的特征向量。其前向过程为

$$
z _ { 1 } = \psi _ { 1 } \big ( V _ { u } ^ { U } , V _ { i } ^ { I } \big ) = \left[ V _ { u } ^ { U } \right] \ ,
$$

$$
\psi _ { 2 } \left( z _ { 1 } \right) = \sigma \big ( W _ { 2 } ^ { \prime T } z _ { 1 } + b _ { 2 } ^ { \prime } \big ) \quad ,
$$

$$
\psi _ { H } \left( z _ { H - 1 } \right) = \sigma \big ( { \cal W } _ { H } ^ { \prime T } z _ { H - 1 } + b _ { H } ^ { \prime } \big )
$$

其中： $H$ 是层的深度， $\sigma$ 是激活函数。 $z _ { H } , \ W _ { H } ^ { \prime }$ 和 $b _ { H } ^ { \prime }$ 是第 $H$ 层的输出、模型权重和偏置项。经过 $L$ 层网络学习后，最终左侧模型的映射函数为

$$
\begin{array} { r l } & { \hat { \boldsymbol { y } } _ { u i } ^ { I } = \sigma ( { \boldsymbol { \psi } } _ { L } ( z _ { L - 1 } ) ) } \\ & { \qquad = \sigma \left( { \boldsymbol { W } _ { L } ^ { \prime } } ^ { T } \left( \sigma \left( \dots \sigma \left( { \boldsymbol { W } _ { 2 } ^ { \prime T } } ^ { T } { \boldsymbol { \overline { { V } } } _ { u } ^ { U } } \right) + b _ { 2 } ^ { \prime } \right) \dots \right) \right) + b _ { L } ^ { \prime } } \\ & { \qquad = \sigma \left( \boldsymbol { W } _ { L } ^ { \prime } \left( \sigma \left( \dots \sigma \left( { \boldsymbol { W } _ { 2 } ^ { \prime T } } ^ { T } { \boldsymbol { \overline { { V } } } _ { i } ^ { U } } \right) + b _ { 2 } ^ { \prime } \right) \dots \right) \right) + b _ { L } ^ { \prime } } \end{array}
$$

# 1.2基于 Attention 特征学习推理机制

Attentionmodel（注意力模型）是一种模拟人脑注意力的模型，即在特定的时刻人脑对事物的注意力会集中在某一特定的地方，忽略其他部分的特点，是一种人脑资源分配的模型。它是对重要部分分配较多的注意力，对于其他部分分配较少的注意力，合理利用人脑的计算资源，并且还可以去除非关键因素对人脑的影响。本文引入这种思想，利用Attention机制自动捕捉用户/项目关键属性对推荐工作的影响，通过赋予不同属性权重来凸显用户偏好关系，然后通过多层深度网络建模来辅助扩展上述非线性分解模型，有效地防止元数据隐含信息的丢失。

如图4所示，基于Attention特征学习推理机制将用户属性特征表示为one-hot编码形式向量，并输入到Attention网络中自动捕捉用户/项目关键属性，并推理出对推荐工作的影响度。本文实验中使用电影ID作为输入，用户属性则利用性别、年龄及职业信息作为输入。假设使用 $V _ { u } ^ { U }$ 用户 $u$ 的特征向量， $A _ { u }$ 表示用户 $u$ 的属性， $V _ { u } ^ { U } = \left\{ A _ { u I } , A _ { u 2 } , A _ { u 3 } , . . . A _ { u g } \right\}$ ，其中 $g$ 表示用户属性数量， $M$ 是用户的数量。

![](images/6148e68dd88581d2bc6eae07ba0079683f0feff92401c7e9f7f954315d85b1df.jpg)  
图4基于Attention 局部特征学习推理机制

如图5所示，可定义编码隐状态 $\left( h _ { 1 } , . . . , h _ { T _ { A } } \right)$ 和解码隐状态$\left( d I , . . . , d _ { T _ { B } } \right) = \left( h _ { T _ { A } + 1 } , . . . , h _ { T _ { A } + T _ { B } } \right) \mathrm { ~ , ~ }$ 。在输入的用户 $g$ 个属性上，为了计算每个输出时间 $t$ 的注意力权重的属性影响因子矩阵，定义为

$$
{ e _ { i } } ^ { t } = f ( h _ { i } , d _ { t } ) = { \nu _ { a } } ^ { T } t a n h \big ( W _ { a } h _ { i } + W _ { b } d _ { t } \big )
$$

其中： $f$ 表示一种模式函数， $W _ { a }$ ， $W _ { b }$ ， $\nu$ 是模型的学习参数。向量 $e ^ { \prime }$ 的长度是 $T _ { _ A }$ （即输入的用户属性数量）以及它的第$i$ 项包含一个有多少注意力应该放在第 $i$ 个编码隐藏状态 $h _ { i }$ 上。然后使用softmax标准化，得到属性 $A _ { u i }$ 在 $t$ 时刻的注意力。最后求和形成权重分配向量，即

$$
\mathbf { c } ^ { \mathrm { t } } = \sum _ { \mathrm { i = 1 } } ^ { T _ { \mathrm { A } } } a _ { i } ^ { t } h _ { i }
$$

![](images/b453624d9198ba38d6f0202e92f9bbb119589c89a96b12ec54736d891cb1924b.jpg)  
图5Attention layer

前向过程为

$$
z _ { 1 } = \psi _ { 1 } \big ( V ^ { U } , V ^ { I } , c \big ) = { \left[ \begin{array} { l } { c V ^ { U } } \\ { V ^ { I } } \end{array} \right] }
$$

$$
\psi _ { 2 } \big ( z _ { 1 } \big ) = \sigma \big ( W _ { 2 } ^ { \prime T } z _ { 1 } + b _ { 2 } ^ { \prime } \big )
$$

$$
\psi _ { H } \left( z _ { H - 1 } \right) = \sigma \big ( { \cal W } _ { H } ^ { \prime T } z _ { H - 1 } + b _ { H } ^ { \prime } \big )
$$

其中： $H$ 是层的深度， $\sigma$ 是激活函数。 $z _ { H } , \ W _ { H } ^ { \prime }$ 和 $b _ { H } ^ { \prime }$ 是第 $H$ 层的输出、模型权重和偏置项。经过 $L$ 层网络学习后，最终右侧模型的映射函数为

$$
\hat { y } _ { u i } ^ { 2 } = \sigma ( \psi _ { L } ( z _ { L - 1 } ) )
$$

模型框架顶层输入来自于两侧模型的输出。由此，我们定义联合预测函数为

$$
\hat { y } = \sigma ( \alpha \hat { y } _ { u i } ^ { I } + \left( I - \alpha \right) \hat { y } _ { u i } ^ { 2 } )
$$

其中： $\alpha$ 是决定双深度模型间训练权重的参数，通过深度模型自学习获得。算法将推荐问题形式化一个多分类问题来实现评分预测。采用Softmax函数作为最终的激活函数 $\sigma _ { o u t }$ 以及利用多分类对数损失来学习。通过上面所述设置，我们定义似然函数为

$$
P \Big ( O , O ^ { - } | U , I , \theta \Big ) = \prod _ { ( u , i ) \in O } \hat { y } _ { u i } \prod _ { ( u , i ) \in O ^ { - } } ( 1 - \hat { y } _ { u i } )
$$

其中： $o$ 表示用户交互集中可观察到的一组交互集合（作为正实例）， $o ^ { - }$ 为均匀地从未观察到的交互集中取样的一组集合（作为负实例）。将上式取似然负对数作为损失函数可得

$$
L = - \sum _ { \left( u , i \right) \in O \cup O ^ { - } } y _ { u i } \log \hat { y } _ { u i } + \left( 1 - y _ { u i } \right) \log \left( 1 - \hat { y } _ { u i } \right)
$$

# 2 实验及结论分析

# 2.1实验数据集

目前，对于推荐领域已经有很多公开的研究。为了验证本文提出的融合元数据及Attention机制的深度联合学习推荐算法的性能，将在实验使用MovieLens100K和MovieLens1M两个公开数据集作为实验数据集[14]。MovieLens 数据集由美国明尼苏达大学计算机科学与工程学院GroupLens 研究组提供。其中每个用户至少对20个电影进行评分，数据稀疏程度分别是0.9369和0.9553，并还提供了用户职业、电影流派等辅助信息。MovieLens100K包含943名用户、1682部电影、19种电影流派以及10万个5星级评价。1M数据集包含6040名用户、3952部电影、18种电影流派以及100万个5星级评价。除此之外，还提供了用户职业、性别等辅助信息。虽然隐式反馈信息要比显式反馈信息更容易获取，但由于目前基于隐式反馈信息并且具有用户元数据信息的公开数据集比较少，因此本文仿照目前常用的方法如文献[15,16]将显式评级数据转换成隐式数据。

# 2.2评估方法

本文所提出的算法利用深度网络实现多分类的评分预测工作。而目前推荐领域中被用来度量评分预测工作质量有很多不同的度量指标。为了评价项目推荐的性能，我们采用了leave-one-out方法评估，这种 top $\mathbf { \nabla } \cdot K$ 评价方法已被广泛地应用于文献[17\~19]。实验中根据时间戳随机抽取100 个不与用户进行交互的项目，将测试项目排列在这100个项目中。排名列表的性能

由命中率（HR）和归一化折扣累积增益（NDCG）[18]来衡量。  
若无特别说明，我们将这两个指标的排名列表截断 $K$ 均为10。

命中率HR能直观地衡量测试项目是否存在于前10项列表中，而NDCG是用来衡量排序质量的指标，通过将较高分数指定为顶级排名来计算命中的位置。HR与NDCG定义如下：

命中率（HR)

$$
H R @ K = { \frac { N u m b e r ~ o f ~ H i t @ K } { \left| G T \right| } }
$$

归一化折扣累积增益（NDCG）

$$
N D C G @ K = Z _ { K } \sum _ { i = 1 } ^ { K } \frac { 2 ^ { r _ { i } } - 1 } { \log _ { 2 } \left( i + 1 \right) }
$$

其中：GT表示测试项目与算法产生排名列表的集合， $Z _ { K }$ 是正规化，以确保排名列表中存在一个值1， $r _ { i }$ 是第 $i$ 个项目的评级相关性。在评估过程中我们使用简单的二进制进行表示：如果项目在测试集 $r _ { i } = 1$ ，否则为0。

# 2.3实验环境及参数设置

为了说明本文所提融合元数据及Attention 机制的深度联合学习推荐模型的优越性，本次实验在Cluster一个node上实现了所提出的算法（实验环境如表1所示）。同时将其与以下具有代表性的经典模型进行实验对比。

a)CBMF[2I]:内容加强矩阵分解模型,此模型将元数据信息直接加入到矩阵分解模型中。

b)NeuMF[10]：基于神经网络协同过滤方法，对比辅助信息对推荐效果的影响;

c)ItemKNN[22]：标准的基于项目的协同过滤方法。

表1实验环境  

<html><body><table><tr><td>软硬件环境</td><td>环境配置</td></tr><tr><td>操作系统</td><td>Linux</td></tr><tr><td>主频</td><td>3.5GHz</td></tr><tr><td>内存</td><td>96.00GB</td></tr><tr><td>编程语言</td><td>Python 3.5</td></tr><tr><td>深度学习库</td><td>Tensorflow1.2.0、 Keras2.0.5</td></tr></table></body></html>

# 2.4 实验结果及分析

为了确定参数，本文采用5折交叉验证，使用了项目属性电影流派及用户属性性别、年龄及职业等信息，将正例以及对每个正例进行四个负实例的均匀采样作为输入。此后再通过多分类对数损失函数来评估。模型从零开始训练，学习率设置为0.001，并利用Adam经过偏置校正后每一次迭代学习率都有个确定范围以致于使得参数趋于平稳的优点优化模型。网络模型设计遵循塔式网络结构，每个连续较高层的层尺寸减半，层的结构为 $1 2 8 \substack {  } 6 4 \substack {  } 3 2$ 。中间层激活函数选择ReLU，因为它支持稀疏激活，使模型不太容易过拟合。首先，我们对本文模型的推荐性能进行了评测，最终实验结果如表2所示。

表1在MovieLens数据集上实验对比（ $\mathrm { K } { = } 1 0$ ）  

<html><body><table><tr><td rowspan="2">Model</td><td colspan="3">DataSet\Metries</td></tr><tr><td>MovieLens100K</td><td></td><td>MovieLens 1M</td></tr><tr><td></td><td>HR</td><td>NDCG</td><td>HR</td><td>NDCG</td></tr><tr><td>NeuMF</td><td>0.672</td><td>0.384</td><td>0.705</td><td>0.423</td></tr><tr><td>ItemKNN</td><td>0.605</td><td>0.328</td><td>0.625</td><td>0.362</td></tr><tr><td>CBMF</td><td>0.632</td><td>0.367</td><td>0.679</td><td>0.393</td></tr><tr><td>DJRMA</td><td>0.685</td><td>0.402</td><td>0.712</td><td>0.428</td></tr></table></body></html>

![](images/d615165b46dc942f6e7e7c7dcf33def9ac1e37a67ed09b0eb3c740ed5b57d83f.jpg)  
图6100K数据集—命中率

![](images/33007901ef22249d8443e12b767640dc86a2c430655b2b6c8c18a4431ae8b9cd.jpg)  
图7100K数据集一归一化折扣累积增益

![](images/fed4d8b8e6878dbb2d583cd9eac1e0646ccd9dadd9bf2e36adba4cdca92eb995.jpg)  
图81M数据集一命中率

![](images/e65f6dcebe6554bf862ab8c08b61a1cc5d0edd0b5e8a6fd65b55f08f74078f52.jpg)  
图91M数据集一归一化折扣累积增益

其次，实验改变层的结构来评测性能，即相当于改变矩阵分解维度。由图6与图7可知，DJRMA模型通过增强关键属性影响因子使得推荐性能指标HR及NDCG进一步增长。在同等设置情况下，100K 数据集 Factors 为 32 时的 HR 相比于NeuMF、CBMF和ItemKNN分别提升 $1 . 9 \%$ 、 $8 . 3 \%$ 和 $1 3 . 2 \%$ ，NDCG也提升 $4 . 6 \%$ 、 $9 . 5 \%$ 和 $2 2 . 5 \%$ 。同样通过图8和图9分析可知，对于在1M 数据集上，HR 相比于NeuMF、CBMF 和ItemKNN分别提升 $0 . 9 \% . 4 . 8 \%$ 和 $1 3 . 9 \%$ ，NDCG也提升 $1 . 1 \%$ ，$8 . 9 \%$ 和 $1 8 . 2 \%$ 。因此，推荐算法比基线方法表现出较为优越的推荐性能

此外，再次比较图6与图8、图7与图9可知，DJRMA推荐模型的推荐指标在1M数据集上较优越于 $1 0 0 \mathrm { K } . \mathrm { H R }$ 和NDCG提升了 $3 . 9 \%$ 和 $6 . 4 \%$ 。所以由于训练集增大以及样本的不平衡性，DJRMA能表现出较强的学习能力，但总体提升率降低，说明样本不平衡性等问题对模型具有一定的影响。

![](images/ba39e4a9729a83d665ba9fb1b1d861106f1b97c366f4d7f35cc746c07319a36c.jpg)  
图10模型训练损失

图10显示在MovieLens1M数据集下不同迭代次数的迭代损失。模型利用隐式反馈实现二进制分类推荐工作，我们通过训练对数损失获取最优的模型参数。由图可知，随着模型迭代次数的增加，模型训练损失依次逐渐减小，直至稳定。实验中最有效的迭代次数约为10-20次左右。在后续MovieLens100K实验中，我们也发现其变化趋势与1M类似，并且更多的迭代可能使模型饱和，以致于训练损失指标不再提升。

# 3 结束语

本文将新型Attention网络特征学习推理和深度网络分解机功能相结合，提出融合元数据及Attention机制的深度联合学习推荐方法，其一实现矩阵非线性分解以学习用户/项目个性化关系，另一个利用Attention机制自动捕捉用户/项目关键属性对推荐工作的影响，通过赋予不同属性权重凸显的用户偏好关系建模来扩展模型。该算法通过形式化用于协同过滤的建模方法来解决推荐问题。最终通过双深度网络联合学习实现评分预测。最后，本文算法在MovieLens100K和1M两个公开数据集上进行验证。实验结果表明所提出的推荐算法比基线方法不仅仅表现出了较为优越的推荐性能，而且在学习效率上也相差较

小。

在未来工作中，将考虑引入更为丰富的元数据信息，进而挖掘交叉属性间对关系表达的影响因子以改进算法使得推荐质量提高。另外，仍考虑利用残差网络、卷积网络或其它深度模型[23]构建更合理的推荐框架以综合利用不同抽象级别的特征，也是目前推荐领域研究的热点。

# 参考文献：

[1]Bell R,Koren Y, Volinsky C.The bellkor 2008 solution to the Netflix prize [R]. Korbell Teams Report to Netflix,2008: 709-714.   
[2]Paterek A． Improving regularized singular value decomposition for collaborative filtering[C]//Proc of KDDCup & Workshop,2007: 319-325.   
[3]Lee D D, Seung H S.Learning the parts of objects by non-negative matrix factorization [J]. Nature,1999,401: 788-791.   
[4]Fu Bin,Xu Guangdong,Cao Longbing,et al. Coupling multiple views of relations for recommendation [M]//Advances in Knowledge Discovery and Data Mining.[S.1.] : Springer International Publishing,2015: 732-743.   
[5]Li Fangfang. Non-IID recommender system [D]. Beijing: Beijing Institute of Technology. 2014.   
[6]Salakhutdinov R,Mnih A,Hinton G.Restricted Boltzmann machines for collaborative filtering [C]// Proc of International Conference on Machine Learning. New York: ACM Press,2007: 791-798.，   
[7]Zhang Feng, Chang Huiyou.A collaborative filtering algorithm embedded BP network to ameliorate sparsity issue [C]// Proc of International Conference on Machine Learning and Cybernetics. 20o5 1839-1844.   
[8]Lian Jianxun, Zhang Fuzheng, Xie Xing,et al. CCCFNet: a content-boosted collaborative filtering neural network for cross domain Recommender Systems [C]// Proc of International Conference on World Wide Web Companion. International World Wide Web ConferencesSteering Committee,2017: 817-818.   
[9]Guo Huifeng,Tang Ruiming,Ye Yunming,et al. DeepFM: a factorizationmachine based neural network for CTR prediction [C]// Proc of 26th International Joint Conference on Artificial Intelligence.2017:1725-1731.   
[10] He Xiangnan,Liao Lizi,Zhang Hanwang,et al.Neural collaborative filtering [C]// Proc of International World Wide Web Conference Commitee. 2017: 3-7.   
[11] Luong MT,Pham H,Manning C D.Effective approaches to attention-based neural machine translation [C/ Empirical Methods on Natural Language Processing.2015: 31-41.   
[12] Mnih V, Heess N,Graves A. Recurrent models of visual attention [C]// Advances in Neural Information Processing Systems.2014: 2204-2212.   
[13] Zhang Qi,Gong Yeyun,Wu Jindou, et al. Retweet prediction with attentionbased deep neural network [C]// Proc of the 25th ACM International on Conference on Information and Knowledge Management. New York: ACM Press,2016: 75-84.   
[14] Harper FM,Konstan JA.The MovieLens datasets: history and context [J]. ACM Trans on Interactive Intelligent Systems,2016,5 (4): 19.   
[15]Hu Yifan,KorenY,VolinskyC.Collaborative filtering for implicit feedback datasets [Cl//Proc ofthe 8th IEEE International Conference on Data Mining. Washington DC: IEEE Computer Society,2008: 263-272.   
[16]Pan Rong,Zhou Yunhong,Cao Bin,et al. One-class collaborative filtering [Cl// Proc of the 8th IEEE International Conference on Data Mining. Washington DC: IEEE Computer Society,2008: 502-511.   
[17] Bayer I,He Xiangnan,Kanagal B,et al.A generic coordinate descent framework for learning from implicit feedback[C]//Proc of International Conferenceon World Wide Web. International World Wide Web Conferences Steering Committee, 2017: 1341-1350.   
[18] He Xiangnan, Zhang Hanwang, Kan MY,et al. Fast matrix factorization for online recommendation with implicit feedback [Cl/ Proc of International ACM SIGIR Conference on Research and Development in Information Retrieval. New York: ACM Press,2016: 549-558.   
[19]Rendle S,Freudenthaler C,Gantner Z,et alBPR: Bayesian personalized ranking from implicit feedback [C]// Proc of the 25th Conference on Uncertainty in Artificial Intelligence.20l2: 452-461.   
[20] Wang Hao,Wang Naiyan, Yeung D Y. Collaborative deep learning for recommender systems[C]// Proc of ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. New York: ACM Press, 2015: 1235-1244.   
[21] Forbes P, Zhu Mu. Content-boosted matrix factorization for recommender systems: experiments with recipe recommendation [C]// Proc of ACM Conference on Recommender Systems.New York: ACM Press,2011: 261- 264.   
[22]SarwarB,KaryisG,KonstanJ,etal.Item-basedcollaborativefiering recommendation algorithms [C]/ Proc of International Conference on World Wide Web.New York: ACMPress,2001: 285-295.   
[23] 刘海龙，李宝安，吕学强，等．基于深度卷积神经网络的图像检索算法 研究[J].计算机应用研究,2017,34(12):3816-3819.(Liu Hailong,Li Baoan,Lu Xueqiang,et al. Image retrieval algorithm based on deep convolutional neural network [J]. Research ofComputer Applications,2017, 34 (12): 3816-3819.