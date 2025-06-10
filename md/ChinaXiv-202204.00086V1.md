# RA-GCN：抑制过平滑现象的文本分类算法

苏凡军，马明旭，佟国香(上海理工大学 光电信息与计算机工程学院，上海 200093)

摘要：现有大多数利用图神经网络的算法进行文本分类时，忽略了图神经网络的过度平滑问题和由于文本图拓扑差异引入的误差，导致文本分类的性能不佳。针对这一问题，提出了衡量多个文本图表示的平滑度的方法WACD以及抑制过平滑现象的正则项RWACD。随后提出了基于注意力和残差的网络结构ARS，用于弥补由于图拓扑差异引起的文本信息的损失。最后，提出了图卷积神经网络文本分类算法RA-GCN。RA-GCN在图表示学习层使用ARS融合文本表示，在读出层使用RWACD抑制过平滑现象。在6个中英文数据集上进行实验，实验结果证明了RA-GCN的分类性能，并通过多个对比实验验证了RWACD和ARS的作用。

关键词：文本分类；图卷积神经网络；过平滑；注意力机制中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.02.0037

RA-GCN: text classification algorithm suppressing over-smoothing phenomenon

Su Fanjun, Ma Mingxu†, Tong Guoxiang (SchoolofOptical-Electrical&ComputerEngineering,UniversityofShanghaiforScience&TechnologyShanghai200093, China)

Abstract: Most existing text clasification algorithmsbased on graph neural network ignore the problem ofover-smoothing, andignorethe problemof information loss due to graphtopology,resulting inpoorclasification performance.Tosolve this problem,this paper proposed a method to measure the smoothness of multiple text graph representations WACD and a regularization term RWACD to suppress over-smoothing.Subsequently,this paper proposed anatentionandresidual-based network structureARStocompensateforthelossof textual information duetographtopologydiferences.Finally,his paper proposed a graph convolutional neural network text classification algorithm RA-GCN.RA-GCN used ARS to fuse text representations inthe graph representation learming layer,and used RWACDin the readout layer tosuppressover-smoothing. This paperconducted experiments on6Chineseand Englishdatasets.The experimentalresults demonstrate the classification performance ofRA-GCN,and the efects of RWACD and ARS are verified through multiple comparative experiments.

Key words: text classification; graph convolutional network; over-smoothing; attention mechanism

# 0 引言

文本分类作为自然语言处理领域的基础问题，已被应用于许多现实场景，例如垃圾邮件检测，新闻分类，情感识别等。文本分类模型的性能很大程度上取决于文本表示的质量。基于深度学习的方法避免了人工设计规则和特征，自动学习语义上有意义的表示[I]。基于CNN和RNN的深度学习方法可以很好地捕获局部连续序列中的语义和句法特征，但对非连续词和长距离语义信息的提取仍然存在限制[2\~4]。

近年来，图神经网络缓解了上述现象。Yao[5]构建整个语料库的单张文本-单词异构图，使用GCN[学习词共现信息，更新文本、单词表示，进行文本分类。 $\mathrm { W u ^ { [ 7 ] } }$ 通过去除非线性激活函数和折叠连续层之间的权重矩阵，将GCN简化为SGC，并且在基于单张语料库异构图的数据上取得了不错的文本分类效果。但是，基于单张异构图的方法不利于测试新的文本，消耗了大量的内存空间，为此，Huang[8构建每个文本的图数据，共享全局单词表示和边的权值，更好的捕捉局部特征和减少内存消耗。Zhang为提高图方法的归纳学习能力，构建每个文本独特的图数据，使用GGNN[10]更新单词特征，获取文本表示及类别。但是，上述方法忽略了图神经网络的过度平滑问题，本文关注基于每个文本图表示的图分类[8.9,11]方向，缓解过度平滑现象，提升文本分类性能。

在GNN发展过程中，Li[2]首次引起对过度平滑的关注[13],证明了图卷积是一种特殊的拉普拉斯平滑，并且得出结论：对节点进行平滑操作是GCN工作的关键机制，但是执行多次拉普拉斯平滑后，节点特征会收敛至相似值，这个现象被称为过度平滑现象，也被称为过平滑，过平滑会导致节点之间无法区分，从而损害网络性能。Chen[14]验证了平滑是GNN的本质，给出了衡量平滑度的方法MAD(Mean Average Distance)，从图拓扑角度分析了过度平滑的原因，认为信息和噪声的过度混合是影响过度平滑的一个关键因素，提出了抑制过平滑的正则项MADreg和迭代训练算法AdaGraph。同时有研究者提出通过模型优化人为构造的图拓扑，提升模型性能，抑制过度平滑现象。Wang[15]通过多跳注意力机制扩大节点的感受野，使不直接连接但相聚多跳的节点之间进行远程交互，过滤高频噪声信息。Yang[16]利用指针网络[17]寻找多阶邻域中的相关节点，使用一维卷积提取高级特征，过滤噪声信息，减轻过度平滑问题。在网络结构方向，文献[18]借助残差、密集连接和扩张卷积堆叠深层GCN，显著提高了GCN在点云语义分割任务中的性能，缓解了过平滑现象。在数据方向，Rong[19]在每个训练期间随机丢弃图中一定比例的边，以充当数据增强器和消息传递减速器，降低过平滑的收敛速度。

根据文献[12,14]及本文的实验现象，可以发现使用GCN进行文本图表示学习时，平滑使得单词特征收敛至相似值，单词表示不可避免地变得相似，损害了文本分类的性能。为此，本文针对文本分类问题，为了更好的衡量及分析单词节点的平滑度，提出了衡量多个文本图表示的平滑度的方法加权平均余弦距离 WACD(Weighted Average Cosine Distance)。WACD与MAD[14]不同，MAD 适用于单张图，WACD 则作用于多个图，更适用于本文关注的图分类方向。本文借鉴节点分类中抑制过平滑的方法，在WACD的基础上提出了抑制过平滑的正则项 RWACD(Regularization based on WeightedAverageCosineDistance)。随后提出了基于注意力和残差的网络结构 ARS(Attention-based Residual Network Structure)，弥补由于图拓扑差异引起的文本信息损失。与[14\~16]不同，ARS无须迭代训练和寻找重要相关节点，仅使用注意力机制和残差结构，加快训练速度。最后，提出了图卷积神经网络文本分类算法RA-GCN(RWACD-ARSbasedGraphConvolu-tionalNeuralNetwork TextClassificationAlgorithm)。算法RA-GCN在图表示学习层使用ARS融合文本表示，在读出层使用RWACD抑制过平滑现象。实验在6个中英文数据集上进行，实验结果证明了RA-GCN的性能，并通过多个对比实验验证了RWACD和ARS的作用。总体来说，本文有以下创新点：

a）提出了衡量多个文本图表示的平滑度的方法WACD，并提出了抑制过平滑现象的正则项RWACD。b)提出了基于注意力机制和残差的网络结构ARS，弥补由于图拓扑差异引起的文本信息损失，同时抑制过平滑现象。c）提出了基于RWACD和ARS的图卷积神经网络文本分类算法RA-GCN，在6个中英文数据集上的实验结果证明了RA-GCN 的性能。d）多方面进行对比实验，验证了RWACD和ARS均能抑制过平滑现象和提升模型性能；证明了从图拓扑角度弥补文本信息损失决策的正确；分析并探讨了在本文关注的基于每个文本图表示的图分类方向中的过平滑现象。

# 1 相关研究

本文所提算法针对于文本图分类中的过平滑问题，是对文献[14]算法的改进和完善，因此本节重点介绍文献[14]。文献[14主要针对节点分类领域的过平滑现象，提出了衡量图表示的平滑度的方法 MAD，抑制过平滑的正则项 MADreg和迭代训练算法AdaGraph。

# 1.1MAD 与MADreg

MAD是基于余弦距离衡量图表示的平滑度的方法。给定图表示矩阵 $H \in R ^ { n \times d }$ ，其中 $n$ 为节点数， $^ d$ 为特征维度。通过余弦距离计算距离矩阵 $\mathrm { ~  ~ { ~ D ~ } ~ }$ ，每个节点对之间的距离计算为

$$
D _ { i k } = 1 - { \frac { H _ { i , : } \cdot H _ { k , : } } { | H _ { i , : } | \cdot | H _ { k , : } | } } \qquad i , k \in [ 1 , 2 , . . . , n ]
$$

其中 $H _ { \mathrm { i } } ,$ ：为图表示 $H$ 的第 $i$ 行。使用余弦距离的原因是余弦距离不受节点向量绝对值的影响，从而更好地反映了图表示的平滑性[14]。

为了得到目标节点对之间的余弦距离，构造目标掩码矩阵 $M ^ { t g t }$ ，得到目标节点对的距离矩阵，计算为

$$
D ^ { t g t } = D \circ M ^ { t g t }
$$

其中，·表示逐元素乘法， $M ^ { t g t } \in \{ 0 , 1 \} ^ { n \times n }$ ，当 $( i , k )$ 是目标节点对时， $M _ { i k } ^ { t g t } = 1$ 。然后计算每行非零值的平均值：

$$
\bar { D } _ { i } ^ { t g t } = \frac { \sum _ { k = 1 } ^ { n } D _ { i k } ^ { t g t } } { \sum _ { k = 1 } ^ { n } 1 ( D _ { i k } ^ { t g t } ) }
$$

$$
1 ( x ) = \left\{ { \begin{array} { l l } { 1 \qquad } & { x > 0 } \\ { 0 \qquad } & { x = 0 } \end{array} } \right.
$$

通过计算 $\overline { { D } } _ { i } ^ { t g t }$ 中非零值的平均值，得到给定目标节点的MAD，计算为

$$
\mathrm { M A D ^ { t g t } } = \frac { \sum _ { i = 1 } ^ { n } \bar { D } _ { i } ^ { t g t } } { \sum _ { i = 1 } ^ { n } 1 ( \bar { D } _ { i } ^ { t g t } ) }
$$

文献[14]观察到在节点分类中，拓扑距离小的两个节点更有可能属于同一类别，因此提出了利用图拓扑来近似节点类别，并计算远程和邻居节点的MAD差值来估计图表示的过平滑度MADGap，计算为

$$
\mathbf { M A D G a p } = \mathbf { M A D ^ { m t } \cdot M A D ^ { n e b } }
$$

其中，MADmt是图拓扑中远程节点的MAD值， $\mathbf { M A D ^ { n e b } }$ 是邻居节点的MAD值。将MADGap引入系数 $\lambda$ 后得到抑制过平滑的正则项MADreg，计算为

$$
\mathbf { M A D r e g } = - { \boldsymbol { \lambda } } \times \mathbf { M A D G a p }
$$

# 1.2Adagraph

文献[14]观察到在利用真实标签优化图拓扑时，缓解了过平滑现象，提升了节点分类的性能，因此提出了优化图拓扑的迭代训练算法AdaGraph。首先训练GNN，然后根据预测结果删除类间边和添加类内边优化图拓扑，多次执行该过程后，降低了图拓扑差异，抑制了过平滑现象，提升了节点分类的性能。

# 2 本文研究的算法

MAD、MADreg与AdaGraph适用于基于单张图表示学习的工作，然而本文关注的是基于多个文本图表示的图分类方向，因此文献[14并不能直接用于本文关注的方向，并且MADreg 需要寻找最优阶数计算MADGap，AdaGraph需要迭代训练优化图拓扑，增加了训练时间，与本文关注的方向有较大差异。

为此，提出了衡量多个文本图表示的平滑度的方法加权平均余弦距离WACD及抑制过平滑的正则项RWACD。提出了基于注意力和残差的网络结构ARS，弥补由于文本图拓扑差异引起的信息损失，同时抑制过平滑现象。最后，提出了图卷积神经网络文本分类算法RA-GCN。

# 2.1 WACD与RWACD

WACD衡量多个文本图的平滑度，值越高表示平滑度越低，过平滑概率越低，反之平滑度越高，过平滑概率越大。

首先，对于单个文本图表示 $H _ { T } \in R ^ { m \times d }$ ，其中 $m$ 为单词节点数， $^ d$ 为词嵌入维度。将所有单词对视为目标节点，利用式$( 1 ) \sim$ 式(5)计算文本图的平均余弦距离ACD(AverageCosineDistance)。利用每个文本的长度计算ACD的加权系数 $\mu _ { i }$ ，以更好的估计多个文本图表示的平滑度WACD，计算过程为

$$
\overline { { l } } = \frac { 1 } { b } \sum _ { i = 1 } ^ { b } l _ { i }
$$

$$
\mu _ { i } = \frac { l _ { i } } { \overline { { l } } }
$$

$$
\mathrm { W A C D } = \frac { 1 } { b } \sum _ { i = 1 } ^ { b } \mu _ { i } \times \mathrm { A C D } _ { i }
$$

其中， $b$ 表示文本数量， $l _ { i }$ 为第 $i$ 个文本的长度。正则项RWACD计算为

$$
\mathbf { R W A C D } { = } 1 { - } \mathbf { W A C D }
$$

基于文本长度加权平均ACD得到WACD，更好的衡量多个文本图的平滑程度；RWACD通过降低文本图表示的平滑度降低过平滑的概率。与MADreg[14]相比，RWACD无需寻找最优阶数，更适用于本文关注的文本图分类方向。

# 2.2 ARS

参考节点分类领域对图拓扑方向的探讨[14\~16]，本文认为人为构造的文本图拓扑与潜在真实文本拓扑存在偏差，造成了图表示学习中的文本信息损失。因此本文提出，对于每个网络层，利用注意力机制和残差的网络结构ARS缓解上述现象，同时抑制过平滑问题。与[14\~16]不同的是，ARS无须迭代训练和寻找重要相关节点，仅使用注意力和残差，加快训练速度，更适合本文关注的方向。ARS将在2.3.2节中详细介绍。

# 2.3RA-GCN

如图1所示为RA-GCN算法的框架图。为了使框架更加清晰，部分框架使用了红、蓝、绿三种颜色突出计算流程，其中红色表示GCN的前向计算流程；蓝色表示ARS的前向计算流程；绿色表示RWACD的前向计算流程。总的来说，RA-GCN可分为三个部分，分别为文本处理层、图表示学习层和读出层。文本处理层主要对文本进行处理，转换为图表示学习层的输入。图表示学习层学习文本表示，主要由GCN和ARS两部分构成，GCN学习图级别的文本表示，ARS弥补由于文本图拓扑差异引入的信息损失。读出层获取文本类别，使用交叉熵函数计算损失，使用RWACD抑制过平滑。下面详细介绍算法的各个部分以及流程。

![](images/f7406bfa11d2f3ee90f68dc88fff88d2cf347ce11e1d7b79efdf5cb5d0824c1c.jpg)  
图1RA-GCN 算法的框架  
Fig.1The framework of the RA-GCN algorithm

2.3.1文本处理层

如图1所示，对于文本 $T = \{ w _ { 1 } , w _ { 2 } , . . . , w _ { n } \}$ ， $w _ { i }$ 为单词，文本图数据表示为 $G = ( V , E , X )$ ， $V { = } \{ \nu _ { 1 } , \nu _ { 2 } , { \ldots } , \nu _ { m } \}$ 为唯一出现的单词节点集， $\mid V \mid = m$ 为单词个数， $m \leq n$ ， $\boldsymbol { \mathbf { \mathit { E } } }$ 为边集， $\boldsymbol { \cal X }$ 为初始单词特征矩阵。使用滑动窗口构建单词节点集 $\boldsymbol { V }$ 和边集 $\boldsymbol { \mathbf { \mathit { E } } }$ ，边集$E$ 通过邻接矩阵 $A$ 展现， $A = [ a _ { i k } ] \in R ^ { m \times m }$ ，其中 $a _ { i k } = 1$ 表示单词节点 $\nu _ { i }$ 和 $\nu _ { k }$ 相连，0表示不相连。构建邻接矩阵 $A$ 的度矩阵$D _ { r } = d i a g ( d _ { 1 } , d _ { 2 } , . . . , d _ { m } )$ ，其中 $\boldsymbol { d } _ { i }$ 是节点 $\nu _ { i }$ 的度。归一化的邻接矩阵定义为 $\overline { { A } } = D _ { T } ^ { - 1 / 2 } A D _ { T } ^ { - 1 / 2 }$ 。初始单词特征矩阵 $\boldsymbol { X } \in R ^ { m \times d }$ 使用预训练词嵌入构建，其中 $^ d$ 是词嵌入维度。

# 2.3.2图表示学习层

如图1所示，图表示学习层分为GCN和ARS两个部分，

GCN学习单词共现信息，获取文本图表示；ARS使用注意力机制和残差结构得到当前图表示学习层的文本表示输出。

1)GCN对于第 $\ l { + } 1$ 层的文本图表示，计算为

$$
H _ { g c n } ^ { l + 1 } = \rho ( \overline { { A } } H ^ { l } W ^ { l + 1 } )
$$

其中， $H ^ { \prime } \in R ^ { m \times d }$ 为第 $\mathbf { \xi } _ { l }$ 层的文本表示输出， $H ^ { \circ } = X$ ， $W ^ { l + 1 }$ 为可学习的参数矩阵， $\rho$ 为 Leaky_relu 激活函数。

2)ARS首先对前 $l + 1$ 层的所有文本表示输出与当前层的文本图表示分配注意力分数，计算为

$$
H _ { t o t a l } ^ { l + 1 } = [ H ^ { \scriptscriptstyle 0 } , H ^ { \scriptscriptstyle 1 } , . . . , H ^ { \scriptscriptstyle l } , H _ { g c n } ^ { \scriptscriptstyle l + 1 } ]
$$

$$
H _ { m e a n } ^ { l + 1 } = \mathbf { M e a n } ( H _ { t o t a l } ^ { l + 1 } )
$$

$$
L ^ { l + 1 } = \sigma ( W _ { l } H _ { m e a n } ^ { l + 1 } + b )
$$

其中， $H _ { t o t a l } ^ { l + 1 } \in R ^ { ( l + 2 ) \times m \times d }$ 、 $H _ { m e a n } ^ { l + 1 } \in R ^ { ( l + 2 ) \times d }$ 为不同维度的文本表示，$L ^ { l + 1 } = [ \lambda ^ { 0 } , \lambda ^ { 1 } , . . . , \lambda ^ { l } , \lambda _ { g c n } ^ { l + 1 } ]$ 为各文本表示的注意力分数， $W _ { \iota }$ 与 $b$ 为可学习的参数矩阵， $\sigma$ 为 sigmoid 函数。

随后，使用注意力分数和残差结构得到当前层的文本表示输出 $H ^ { l + 1 }$ ，计算为

$$
H ^ { l + 1 } = \lambda ^ { 0 } H ^ { 0 } + \lambda ^ { 1 } H ^ { 1 } + . . . + \lambda ^ { l } H ^ { l } + \lambda _ { g c n } ^ { l + 1 } H _ { g c n } ^ { l + 1 }
$$

2.3.3读出层

如图1所示，读出层利用注意力机制聚合单词特征，得到最终文本表示，并预测文本类别。最终文本表示 $h _ { G }$ 计算为

$$
h _ { i } = \sigma ( h _ { i } ^ { l + 1 } W _ { s } + b _ { s } ) \odot \psi ( h _ { i } ^ { l + 1 } W _ { t } + b _ { t } )
$$

$$
h _ { G } = \frac { 1 } { | V | } \sum _ { i = 0 } ^ { m } h _ { i } + \mathbf { M a x p o o l i n g } ( h _ { 1 } , . . . , h _ { m } )
$$

其中， $\sigma$ 为sigmoid函数， $\sigma ( \cdot )$ 表示对单词分配重要性系数，$\psi$ 为tanh 函数， $\psi ( \cdot )$ 表示对单词特征进一步转换， $W$ 与 $b$ 为可学习的参数矩阵。除此之外，为了发挥每个词和重要词的作用，提取平均特征和重要特征，得到最终文本表示 $h _ { G }$ 。

最后，使用softmax函数预测文本类别，目标函数为交叉熵损失函数，并使用正则项RWACD，计算过程为

$$
\overline { { y } } _ { G } = \mathrm { s o f t m a x } ( W _ { y } h _ { G } + b _ { y } )
$$

$$
L { = } { - } \sum _ { i } ^ { } { y _ { G } \log ( \overline { { y } } _ { G } ) } + \xi { \times } \mathrm { R W A C D }
$$

其中， $\overline { { y } } _ { G }$ 为预测的文本类别， $\boldsymbol { W } _ { y }$ 与 $b _ { y }$ 为可学习的参数矩阵，$y _ { G }$ 为真实的文本类别， $\xi$ 为RWACD的系数。

# 3 实验部分

# 3.1实验环境

文本算法的实验环境如表1所示。

Tab.1Experimental environment   

<html><body><table><tr><td>实验环境</td><td>环境配置</td><td>实验环境</td><td>环境配置</td></tr><tr><td>操作系统</td><td>Ubuntu 20.04.3</td><td>编程语言</td><td>Python 3.7.11</td></tr><tr><td>显卡</td><td>Nvidia GTX2060S</td><td>开发工具</td><td>Pycharm</td></tr><tr><td>CUDA版本</td><td>11.4</td><td>深度学习框架</td><td>Tensorflow 2.4.1</td></tr></table></body></html>

# 3.2 数据集

本文考虑使用以下6个数据集测试RA-GCN的性能，表2展示了数据集的统计数据，其中\*表示该数据集未给出验证集。

表1实验环境  
表2数据集信息  
Tab 2Dataset information   

<html><body><table><tr><td>数据集</td><td>训练集</td><td>验证集</td><td>测试集</td><td>类别</td><td>平均长度</td></tr><tr><td>MR*</td><td>7108</td><td>-</td><td>3554</td><td>2</td><td>18.46</td></tr><tr><td>Tnews</td><td>53360</td><td>10000</td><td>5000</td><td>15</td><td>12.01</td></tr><tr><td>Ohsumed*</td><td>3357</td><td></td><td>4043</td><td>23</td><td>79.49</td></tr><tr><td>R8*</td><td>5485</td><td>-</td><td>2189</td><td>8</td><td>41.25</td></tr><tr><td>SST-5</td><td>8544</td><td>1101</td><td>2210</td><td>5</td><td>17.75</td></tr><tr><td>SST-2</td><td>6919</td><td>871</td><td>1820</td><td>2</td><td>17.75</td></tr></table></body></html>

a)MR数据集。含有正负面极性的2分类英文情感数据集。b)Tnews[20]数据集。15个类别的中文新闻分类数据集。c)Ohsumed数据集。23个类别的英文心血管疾病医学摘

要分类数据集。

d)R8数据集。8个类别的路透社英文新闻分类数据集。e)SST-2、SST-5数据集。分别为2分类、5分类英文情感分类数据集。

# 3.3基线

由于文献[14]的方法适用于节点分类，与本文关注的文本图分类方向不符合，因此本文仅考虑与以下基线进行比较：a）传统的深度学习文本分类方法。包括TextCNN[21]和TextRNN[22]。b）基于单张文本-单词异构图的文本分类方法。包括TextGCN[5]和TextSGC[7]。c）基于每个文本图表示的图分类方法。包括Huang[8]和RA-GCN，不含RWACD和ARS的P-GCN，P-SGC。

# 3.4参数设置

对于未给验证集的数据集，将训练集随机分成9:1的比例用于实际训练和验证。对于初始单词特征，英文使用200维的预训练GloVe[23]词向量，中文采用文献[24]中通过搜狗新闻训练的300 维词向量。词汇外(OutofVocabulary，OOV)单词从均匀分布[-0.01,0.01]中随机采样得到。算法使用Adam[25优化器，学习率设置为0.001，其余参数根据不同数据集调整。模型性能使用准确度(Accuracy)进行衡量。

# 3.5实验结果

表3为各模型在6个数据集上的准确度表现，实验结果为各模型训练5次的平均值。可以看出，RA-GCN均取得了最好的结果。

表3实验结果  

<html><body><table><tr><td>模型</td><td>MR</td><td>Ohsumed</td><td>R8</td><td>SST-5</td><td>SST-2</td><td>Tnews</td></tr><tr><td>TextCNN</td><td>0.7775</td><td>0.5844</td><td>0.9571</td><td>0.423</td><td>0.8049</td><td>0.5602</td></tr><tr><td>TextRNN</td><td>0.7768</td><td>0.4927</td><td>0.9631</td><td>0.4263</td><td>0.8038</td><td>0.5518</td></tr><tr><td>TextGCN</td><td>0.7674</td><td>0.6836</td><td>0.9707</td><td>0.4063</td><td>0.8102</td><td></td></tr><tr><td>TextSGC</td><td>0.759</td><td>0.685</td><td>0.972</td><td>-</td><td></td><td></td></tr><tr><td>Huang</td><td>-</td><td>0.694</td><td>0.978</td><td>-</td><td></td><td></td></tr><tr><td>P-GCN</td><td>0.7853</td><td>0.684</td><td>0.9757</td><td>0.4376</td><td>0.8313</td><td>0.5684</td></tr><tr><td>P-SGC</td><td>0.783</td><td>0.6852</td><td>0.9689</td><td>0.4384</td><td>0.8264</td><td>0.5672</td></tr><tr><td>RA-GCN</td><td>0.796</td><td>0.695</td><td>0.978</td><td>0.462</td><td>0.8451</td><td>0.5724</td></tr></table></body></html>

对比传统方法，CNN和RNN在大部分数据集上的性能均不如基于图的方法，证明了图模型有利于文本分类。对比基于每个文本图分类的模型Huang、P-GCN、P-SGC、RA-GCN和基于单张异构图分类的模型TextGCN、TextSGC，前者在大多数情况下均优于后者，特别是在MR、SST-2等短文本数据集上，验证了基于每个文本图表示的图分类方法的有效性。

在6个数据集上的结果证明了所提文本分类算法RA-GCN的性能。RA-GCN在MR、SST-2、SST-5和Tnews短文本数据集上提升较大，在长文本数据集上提升较小。因为构造的实际文本图拓扑并非真实潜在的文本拓扑结构，然而由于短文本的图规模较小，在GCN消息传递机制的作用下，单词信息传播广泛且迅速，RWACD和ARS能够抑制过度平滑现象和弥补由于图拓扑差异引起的文本信息损失，所以RA-GCN能学习到更准确的文本表示。但是长文本的图规模较大，拓扑差异导致信息的传播速度不像小规模图一样流畅，造成了模型学习不到准确的文本表示，RWACD及ARS发挥的作用较小，因此RA-GCN在长文本数据集上的文本分类性能提升不显著。

# 3.6对比实验及过平滑现象分析

本小节以GCN、SGC为基础，验证RWACD、ARS对提升模型性能和抑制过平滑现象的作用，分析过平滑现象。实验均在MR、SST-5数据上进行，并抽取了4条MR测试集中的样本用于部分实验结果的可视化和分析，样本描述如表4所示。

Tab.4Sample description   

<html><body><table><tr><td>序号</td><td>样本(0/1类)</td></tr><tr><td>1</td><td>a magnificent drama well worth tracking down(1类)</td></tr><tr><td>2</td><td>anawkwardly contrived exercise in magic realism(O 类)</td></tr><tr><td>3</td><td>i'll put it this way if you're in the mood for a melodrama narrated by talking fish,this is the movie for you(1类)</td></tr><tr><td>4</td><td>children and adults enamored of all things pokemon won't be</td></tr><tr><td></td><td>disappointed(0类)</td></tr></table></body></html>

构造分别含有RWACD或ARS的模型RW-GCN、RW-SGC、ARS-GCN、ARS-SGC，不含及含有RWACD和ARS的模型P-GCN、P-SGC、RA-GCN、RA-SGC。观察各模型在MR和SST-5数据集上的性能表现，探讨RWACD和ARS对模型性能的影响和在样本上的表现。最后分析了本文关注的文本图分类方向的过平滑现象。为了更好的区分各模型的表现，使用不同符号表示不同模型，模型说明如表5所示。

表4样本描述  
表5模型说明  
Tab.5Model description   

<html><body><table><tr><td rowspan="2">模型</td><td rowspan="2">简称</td><td rowspan="2">符号</td><td colspan="2">含有结构</td></tr><tr><td>RWACD</td><td>ARS</td></tr><tr><td>P-GCN、P-SGC</td><td>P-模型</td><td>■</td><td>否</td><td>否</td></tr><tr><td>RW-GCN、RW-SGC</td><td>RW-模型</td><td>△</td><td>是</td><td>否</td></tr><tr><td>ARS-GCN、ARS-SGC</td><td>ARS-模型</td><td></td><td>否</td><td>是</td></tr><tr><td>RA-GCN、RA-SGC</td><td>RA-模型</td><td>?</td><td>是</td><td>是</td></tr></table></body></html>

3.6.1RWACD与ARS的作用

# 1)RWACD、ARS对模型分类性能的影响

表6为8个模型在MR、SST-5测试集上的文本分类准确度表现，实验结果为训练3次的平均值。

Tab.3Experimental results   
表6对比实验结果  
Tab.6Comparative experimental results   

<html><body><table><tr><td>模型</td><td>MR</td><td>SST-5</td></tr><tr><td>P-GCN</td><td>0.784</td><td>0.4376</td></tr><tr><td>P-SGC</td><td>0.7803</td><td>0.438</td></tr><tr><td>RW-GCN</td><td>0.7873</td><td>0.4429</td></tr><tr><td>RW-SGC</td><td>0.7847</td><td>0.4434</td></tr><tr><td>ARS-GCN</td><td>0.7943</td><td>0.4585</td></tr><tr><td>ARS-SGC</td><td>0.7926</td><td>0.4578</td></tr><tr><td>RA-GCN</td><td>0.7955</td><td>0.4623</td></tr><tr><td>RA-SGC</td><td>0.794</td><td>0.4586</td></tr></table></body></html>

从文本图构造方式的角度看，基于GCN和SGC提出的8个模型分类性能均优于TextGCN和TextSGC模型，这突出了基于文本图数据的文本图分类方法的优点。从是否含有RWACD和ARS的角度看，在MR和SST-5的实验结果中，不含RWACD和ARS的P-模型分类性能最差，含有RWACD的RW-模型较P-模型有略微提升，证明了RWACD能够提升模型分类性能。含有ARS的ARS-模型性能在MR和SST-5数据集上表现优异，取得了比P-模型和RW-模型更突出的分类性能，这凸显了从图拓扑角度优化模型性能决策的正确。含有ARS和RWACD的RA-模型分类性能最优，在MR和SST-5上取得了最好的分类效果，这证明了RWACD和ARS能够同时提升模型的分类性能。

# 2)RWACD、ARS对不同层数模型性能的影响

图2为各模型在MR测试集上的准确度和WACD随层数的变化曲线。可以看出，P-模型在分类性能和WACD上的表现均取得最差；在图2中，随着层数增加，P-模型的WACD逐渐下降，分类性能先增加后持续下降，说明一定程度的平滑可以提升模型性能，但是执行多次平滑后，会对模型性能带来影响。对比P-模型，RW-模型的分类性能和WACD略微提升，说明RWACD能够降低图数据的过度平滑，提升模型性能。ARS-模型的分类性能和WACD较P-模型和RW-模型提升明显，说明从图拓扑角度弥补文本信息损失能够显著提升模型性能和抑制过平滑现象。RA-模型的分类性能和WACD取得最佳，这说明RWACD和ARS能同时提升模型分类性能和抑制过平滑现象。

![](images/0a5f0c71bccd6b35b973778b119d345f9c8b77919d729cb35342ce2d44855ad1.jpg)  
图2性能随层数的变化

在上述两个实验中，ARS-模型性能表现突出，这是因为ARS从图拓扑角度出发，弥补了由于图拓扑差异带来的文本信息损失。为了更深一步证明ARS的作用，本小节设计了针对ARS的对比实验，探讨在破损的文本图数据上，模型是否能达到或接近在未破损图数据下模型的性能。

为了突出ARS的作用，以2层P-GCN、ARS-GCN为基线，去除读出层的注意力机制，随机删除文本图的边以破坏图拓扑，并逐渐提高删除比例。与文献[19]不同，对包括测试集的所有文本执行上述操作，并在训练过程中保持拓扑结构不变。为了突出实验结果，P-GCN 实验的删除比例最高为$20 \%$ ，ARS-GCN为 $50 \%$ ，两个模型在MR 测试集上的实验结果如图3所示。

![](images/ece3c27366929f4e934a7f4f014b9921b8996cd925e58a6de4a3f0b6f27265fe.jpg)  
Fig.2AccuracyandWACDchangeswith the number oflayers3)ARS的作用分析  
图3不同删除比例下的模型性能  
Fig.3Model performance with different deletion ratios

从图中看出，在未破损的文本图数据上，ARS-GCN模型性能明显优于P-GCN，说明人为构造的文本图拓扑与真实潜在的文本图拓扑存在偏差，这验证了2.2节中ARS 提出的初衷。随着删除比例的提高，不含ARS的P-GCN模型的性能急剧下降，然而对于ARS-GCN模型，尽管删除比例到达 $30 \%$ 左右，模型性能依旧能抵达或超越P-GCN模型的性能，说明了ARS能够弥补由于图拓扑差异带来的文本信息的损失，这再一次验证了从图拓扑角度出发优化模型性能决策的正确。

单从ARS-GCN曲线可以看出，删除比例在超过 $20 \%$ 后，模型性能急剧下降，这是因为高的删除比例会产生一些与其他节点无边连接的孤立节点，这种节点与其他节点无信息交互，造成了图模型捕捉不到词共现信息，学习不到准确的文本表示，因此造成了模型性能急剧下降；然而在 $0 \% - 2 0 \%$ 的删除比例下，孤立节点的产生概率小，但是依旧对模型性能产生了影响，然而ARS弥补了由于图拓扑差异带来的文本信息损失，模型性能依旧可以到达或接近在原始数据下ARS-GCN模型的性能。

为了更清晰的观察ARS的表现，本小节探讨了两个模型在表4样本上的分类表现。ARS-GCN的数据删除比例为 $30 \%$ ，P-GCN不设置删除比例，分类结果如表7所示，其中 $\surd$ 表示预测正确， $\times$ 表示预测错误，结果为模型训练3次的平均值。

Tab.7Model prediction results for 4 samples   

<html><body><table><tr><td rowspan="2"></td><td rowspan="2">样本 类别</td><td colspan="2">0/1类预测概率(是否预测正确)</td></tr><tr><td>P-GCN(原始数据)</td><td>ARS-GCN(删除比例30%)</td></tr><tr><td>1</td><td>1</td><td>0.000/1.000(√)</td><td>0.022/0.978(√)</td></tr><tr><td>2</td><td>0</td><td>0.996/0.004(√)</td><td>0.973/0.027(√)</td></tr><tr><td>3</td><td>1</td><td>0.239/0.761(√)</td><td>0.384/0.616(√)</td></tr><tr><td>4</td><td>0</td><td>0.358/0.642(X)</td><td>0.810/0.190(√)</td></tr></table></body></html>

从表7中看出，ARS-GCN对前3条样本的类别概率预测结果接近未设置删除比例的P-GCN结果；然而在第4条数据上，ARS-GCN预测正确，P-GCN预测错误，ARS-GCN的预测结果要优于P-GCN。这说明了在ARS的作用下，删除比例在 $30 \%$ 条件下的ARS-GCN的性能表现接近甚至超越了原始数据下P-GCN的性能，这从真实样本角度验证了图3中的实验结果。

综上所述，人为构造的文本图拓扑与潜在文本真实图拓扑之间存在差异，ARS结构能够弥补由于这种差异带来的文本信息的损失，提升模型性能。

# 4）案例分析

在表4样本的基础上，本小节在2层P-GCN和RA-GCN条件下，可视化了第1、2条样本内单词与其他单词的平均距离(图4)；可视化了第1、2条样本ACD值随层数的变化曲线(图5)；可视化了不同层数的P-GCN和RA-GCN对第3、4条样本的预测结果(表8)，其中 $\surd$ 表示模型预测正确， $\times$ 表示预测错误。

表74个样本的模型预测结果  
表8第3和第4条样本的模型预测结果  
Tab.8Model predictions for sample 3 and sample 4   

<html><body><table><tr><td rowspan="2">模型(样本)</td><td colspan="5">不同层数模型的预测结果</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr><tr><td>P-GCN(Sanple3)</td><td>√</td><td>√</td><td>×</td><td>×</td><td>√</td></tr><tr><td>ARS-GCN(Sanple3)</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td></tr><tr><td>P-GCN(Sanple4)</td><td>√</td><td>X</td><td>√</td><td>√</td><td>×</td></tr><tr><td>ARS-GCN(Sanple4)</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td></tr></table></body></html>

从图4中看出，RA-GCN模型显著提升了单词间的平均距离，例如单词worth与其他单词的平均距离从P-GCN的0.12上升为RA-GCN的0.61。在图5中P-GCN结果中，样本的ACD值在第三层接近于0，单词之间变的相似，符合文献[12]中所描述的过平滑现象；然而在RA-GCN的结果中，样本的ACD值提升明显，说明RWACD和ARS抑制了过平滑现象。在表8样本3、4的结果中，P-GCN预测正确3次，RA-GCN全部预测正确，说明RWACD和ARS提升了模型对样本的分类性能。

![](images/5010b3f81bcefa6d626ed4c516b097ca2e5c04c97c84bb58017d1385bbac1ab7.jpg)

图4单词与其他单词的平均距离

![](images/1026deafa828e1ea8a480dc34ccb9daa4563de2a6ae3ac829b4db155827a4b49.jpg)  
Fig.4Average distance of words from other words words   
Fig.5The change curve of the sample ACD value

3.6.2过平滑现象分析

从3.6.1节案例分析中的图5观察到，3层的P-GCN就已经使样本的ACD趋近于0，两个样本均出现了文献[12]描述的过平滑现象；并且在图2中观察到，随着层数的堆叠，P-模型的WACD逐渐下降，分类性能先上升后持续下降，说明一定程度的平滑有利于提升文本分类性能，但执行多次平滑后会损害模型分类性能。为此，本文假设：本文所关注的基于每个文本图表示的文本图分类领域，随着网络层数的堆叠，数据集内部分样本出现过平滑现象，且随着层数的堆叠，出现过平滑现象的文本越来越多，影响了模型的分类性能。

为了验证上述假设，借助构造的8个模型，分析在MR和SST-5测试集中文本图ACD小于某阈值时的文本数随网络层数的变化。实验结果如图6所示，为了突出部分模型的性能，模型之间的阈值取值不同，阈值取值已在图中标注，其中(a)(b)图为GCN、SGC在MR 测试集上的结果，(c)(d)图为在GCN、SGC在SST-5测试集上的结果。

结合图2和图6中P-模型的实验结果看出，ACD小于0.3的文本数随网络层数的上升逐渐增多，WACD随层数的上升逐渐下降，分类性能先上升后下降，结合图4、图5中P-GCN的可视化结果，说明：本文所关注的基于每个文本图表示的图分类领域，过平滑现象体现在以文本图为单位的文本表示中，这种过平滑现象在浅层网络就已出现，并且随着网络层数的堆叠，出现过平滑现象的文本逐渐增多，过平滑现象愈加明显，但是模型性能在2-3层时才开始出现下降。

从RW-模型、ARS-模型的曲线看出，RWACD和ARS均能减少出现过平滑的文本数，抑制过平滑现象，提升模型性能。

RA-模型的结果均取得最佳，说明RWACD和ARS同时减少了出现过平滑的样本数，抑制了过度平滑现象，提升了模型分类性能。

综上所述，以P-模型为基准，本文关注方向的过平滑现象以文本图为单位，在浅层网络就已出现，且过平滑文本数随着网络堆叠而逐渐增加，损害了模型性能；RWACD和ARS均能减少过平滑样本数，抑制过平滑现象，提升模型分类性能。

![](images/33fc8a268dafa1ee1fbb7b60ec72492df4bfb86e7613d881e133a1f54d7d181c.jpg)  
图5样本ACD值的变化曲线图  
图6样本数随层数的变化  
Fig.6Variation of the number of samples with the number of layers

# 4 结束语

本文提出了适用于多个文本图表示的平滑度衡量指标加权平均余弦距离WACD，提出了抑制过度平滑的正则项RWACD。提出了注意力和残差的网络结构ARS，弥补由于文本图拓扑差异引起的图表示学习带来的文本信息的损失，同时抑制过度平滑现象。提出了基于RWACD 和ARS的图卷积神经网络文本分类算法RA-GCN。在6个数据集上证明了RA-GCN的性能，并且通过多个对比实验验证了RWACD和ARS的作用。

# 参考文献：

[1]Li Qian,Peng Hao,LiJianxin,et al.A survey on text classification: from shallow to deep learning[J/OL].ACM Trans on Interactive Intelligent Systems，2021，37(4)．(2021-04)[2021-12-11]. https://arxiv. org/pdf/2008.00364.pdf.   
[2]Kowsari K,Jafari M K,Heidarysafa M,et al.Text classification algorithms:a survey[J].Information,2019,10 (4):150.   
[3]Chiu B,Sahu S K,Sengupta N,et al.Attending to inter-sentential features in neural text classification [C]// Proc of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval.New York:ACM,2020: 1685-1688.   
[4] 何力，郑灶贤，项凤涛，等．基于深度学习的文本分类技术研究进展 [J]．计算机工程,2021,47(2):1-11.(He Li, Zheng Zaoxian,Xiang Fengtao,et al. Research progress of text classification technology based on deep learning [J].Computer Engineering,2021,47(2):1-11.)   
[5]Yao Liang,Mao Chengsheng,Luo Yuan. Graph convolutional networks for text classification [C]//The 33rd AAAI Conference on Artificial Intelligence.Palo Alto:AAAIPress,2019,33(1):7370-7377.   
[6]Kipf T N，Welling M. Semi-supervised classification with graph convolutional networks [C/OL]/ The 5th International Conference on Learning Representations.2017.(2017-02) [2021-12-11]. https:/arxiv. org/pdf/1609. 02907. pdf.   
[7]Wu,F, Zhang Tianyi, Souza A,et al. Simplifying graph convolutional networks [C]// Proc of the 36th International Conference on Machine Learning.[S.I.] : PMLR,2019: 6861-6871.   
[8]Huang Lianzhe,Ma Dehong,Li Sujian,et al.Text level graph neural network for text classification [Cl// Proc of Conference on Empirical Methods in Natural Language Processing and the 9th International Joint Conference on Natural Language Processing. Stroudsburg: ACL,2019: 3442-3448.   
[9]Zhang Yufeng,Yu Xueli,Cui Zeyu,et al.Every document owns its structure: inductive text classfication via graph neural networks $[ \mathrm { C } ] / \hbar$ Proc of the 58th Annual Meeting of the Association for Computational Linguistics. Stroudsburg:ACL,2020: 334-339.   
[10] Li Yujia,Tarlow D,Brockschmidt M,et al. Gated graph sequence neural networks [C/OL]/ The 4th International Conference on Learning Representations.2016.(2016)[2021-12-11]. htps://arxiv.org/pdf/1511. 05493. pdf.   
[11]范国凤，刘睨，姚绍文，等．基于语义依存分析的图网络文本分类模 型[J].计算机应用研究,2020,37(12):3594-3598.(Fan Guofeng,Liu Gui,Yao Shaowen,et al. Text clasification model with graph network based on semantic dependency parsing [J].Application Research of Computers,2020,37 (12): 3594-3598.)   
[12] Li Qimai,Han Zhichao,Wu Xiaoming.Deeper insights into graph convolutional networks for semi-supervised learning [C]// Proc of the 32nd AAAI Conference on Artificial Intelligence.Palo Alto: AAAI Press, 2018: 3538-3545.   
[13] Cai Chen,Wang Yusu.A note on over-smoothing for graph neural networks[EB/OL].(2020-06-23）[2021-12-11].https:/rxiv. org/pdf/2006.13318.pdf.   
[14] Chen Deli,Lin Yankai,Li Wei,et al.Measuring and relieving the oversmoothing problem for graph neural networks from the topological view [C]/ The 34th AAAI Conference on Artificial Intelligence.Palo Alto: AAAI Press,2020: 3438-3445.   
[15] Wang Guangtao,Ying R,Huang Jing,et al.Multi-hop attention graph neural networks [C]// Proc of the 3Oth International Joint Conference on Artificial Intelligence.[S.I.]: ijcai.org,2021: 3089-3096.   
[16] Yang Tianmeng,Wang Yujing,Yue Zhihan,et al.Graph pointer neural networks [EB/OL].(2021） [2022-01-05]. htps://arxiv.org/pdf/2110. 00973. pdf.   
[17] Vinyals O,Fortunato M, Jaitly N.Pointer networks [C]//Advances in Neural Information Processing Systems 28:Annual Conference on Neural Information Processing Systems.2015: 2692-2700.   
[18] Li Guohao,Muller M,Thabet A,et al.DeepGCNs: Can GCNs go as deep as CNNs?[C]//Proc of the IEEE/CVF International Conference on Computer Vision.Piscataway,NJ: IEEE Press,2019: 9266-9275.   
[19] Rong Yu, Huang Wenbing,Xu Tingyang,et al. DropEdge: towards deep graph convolutional networks on node classification [C/OL]/ The 8th International Conference on Learning Representations.2020.(2020-05- 12)[2022-01-05]. https://arxiv.org/pdf/1907.10903.pdf.   
[20] Xu Liang,Hu Hai, Zhang Xuanwei, et al. CLUE: A Chinese language understanding evaluation benchmark [C]//Proc of the 28th International Conference on Computational Linguistics.[S.I.]： International Committee on Computational Linguistics,2020: 4762-4772.   
[21] Kim Y.Convolutional neural networks for sentence classification [C]/ Proc of Conference on Empirical Methods in Natural Language Processing. Stroudsburg: ACL,2014: 1746-1751.   
[22] Liu Pengfei, Qiu Xipeng, Huang Xuanjing.Recurrent neural network for text classification with multi-task learning [C]// Proc of the 25th International Joint Conference on Artificial Inteligence.[S.I.]： IJCAI/AAAI Press,2016: 2873-2879.   
[23] Pennington J,Socher R,Manning C D.Glove: Global vectors for word representation [Cl//Proc of Conference on Empirical Methods in Natural Language Processing. Stroudsburg: ACL,2014:1532-1543.   
[24] Li Shen,Zhao Zhe,Hu Renfen,et al.Analogical reasoning on Chinese morphological and semantic relations [C]// Proc of the 56th Annual Meeting of the Association for Computational Linguistics.Stroudsburg: ACL,2018:138-143.   
[25] Kingma D P,BaJL.Adam: A method for stochastic optimization [C/OL]/ The 3rd International Conference on Learning Representations.2015. (2015)[2022-01-05]. https://arxiv.org/pdf/1412. 6980.pdf.