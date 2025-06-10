# 基于自适应门控图神经网络的交通流预测

王杨，郑津，刘影，李平(西南石油大学 计算机科学学院，成都 610500)

摘要：交通流预测是智能交通系统中的重要组成部分，由于交通数据的复杂性，长期而又准确的交通流预测一直是时间序列预测中最具挑战性的任务之一。近年来，研究人员将基于图神经网络的时空图建模方法应用于交通流预测任务，并取得了良好的预测性能。然而，现有的图建模方法仅通过预定义的邻接结构反映道路网络中的空间依赖关系，忽略了各节点之间的序列关联关系对预测的重要性。针对这一局限性,提出了一种自适应门控图神经网络(Ada-GGNN)，其核心为通过空间传递模块同时捕获道路网络的空间结构及自适应的时序相关性，并通过门控机制学习节点上的时间序列特征。在两个真实交通网络数据集 PeMSD7和Los-loop 上的实验结果证明了该模型具有更优越的性能。

关键词：交通流预测；时空图；自适应门控图神经网络；时序相关性 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.01.0017

Traffic flow prediction based on adaptive gated graph neural network

Wang Yang, Zheng Jin†,Liu Ying,Li Ping (College of Computer Science,Southwest Petroleum University,Chengdu 61o5oo,China)

Abstract:Trafic flow prediction isanimportant partofinteligent transportation system.Due tothecomplexityof traffic data,long-terandacuratetrafficflow predictionhasalwaysbeenoneofthe mostchallengingtasksintimeseriesforecasting. Inrecent years,researchers have appliedspatial-temporal graph modeling methods basedon graph neural networks to traffic flow prediction tasks which achieved good prediction performance.However, existing graph modeling methods onlyreflect the spatialdependence inroad networks through predefined adjacency structures,ignoring the importanceof time-series corelation between nodes for prediction.Aiming at this limitation,this paper proposed an Adaptive Gated Graph Neural Network(Ada-GGNN),thecoreofwhich was to simultaneouslycapture the spatial structureoftheroad network and adaptive time series correlation through the spatial passing module,and learned time-series featureson nodes through the gating mechanism.The experimentalresultson tworeal-world traffc network datasets PeMSD7and Los-loopshowthatthe model has better performance.

Key words: taffcflowprediction;spatial-temporal graph;adaptive gated graph neural networks;timeseriescorrelation

# 0 引言

智能交通系统是智慧城市发展不可或缺的组成部分，而准确实时的交通流预测作为智能交通系统的基础和重要研究方向，它是减少交通事故、缓解交通拥堵和提高交通运输效率的有效解决方案。在实际生活中，交通流通常由道路上的传感器记录，如流量、车速、道路占用率等。交通流预测旨在根据道路网络中的历史交通数据(如传感器记录)预测未来一段时间的交通数据。传统的交通流预测模型主要是基于统计或机器学习的方法，如历史平均模型(HA)[I]、自回归整合移动平均模型(ARIMA)[2]、向量自回归(VAR)[3]、k-最近邻模型(KNN)[4]等，以上方法在实际应用中往往预测效果不佳，它们依赖于数据的平稳性假设。然而交通状况是复杂的，受各种环境因素影响，表现出随机性、周期性、趋势性和时空性等特点。其次，这些方法需要经过复杂的特征工程进行建模，并且只考虑了序列的时间信息，而忽略了空间信息对于交通流预测的重要性。

近年来，深度学习因其强大的特征表达能力和非线性拟合能力被广泛应用于交通流预测任务。Yu等人[5]使用深度的长短期记忆网络(LSTM)来预测交通序列，实验证明了基于神经网络的方法相较于传统方法具有更优异的结果，但是该方法仍没有考虑交通路网的空间结构。Shi等人[设计了ConvLSTM模型用于降雨预测，它将卷积神经网络(CNN)和循环神经网络(RNN)进行结合，分别对空间和时间相关性进行建模。之后，Zhang等人[7将交通路网转换为规则的网格，然后采用CNN提取空间特征。虽然这些模型可以提取数据的时空特征，但交通道路本质上是不规则的，将交通数据视为规则的2维或3维网格数据会导致空间拓扑信息的丢失。

随后，研究人员引入了图神经网络(GNN)来对时空网络数据进行建模，并在交通流预测任务上取得了巨大进步。Li等人[8]提出了DCRNN模型，它将交通网络建模为有向图，采用双向随机游走捕获道路之间的空间依赖性，并使用RNN捕获时间相关性，该方法同时处理了时间和空间信息，具有更准确的预测结果。此后，研究人员对GNN与CNN或RNN结合起来的这种研究范式进行了深入挖掘，例如：文献[9\~11]都采用了GNN来获取拓扑结构中的空间依赖性，采用一维卷积或RNN来获取动态的时间依赖性。

尽管这些基于图神经网络的方法在交通流预测任务上已取得相对成功，但这些模型仍然存在缺陷。首先，这些方法仅采用预定义的图邻接结构捕获节点间的空间依赖关系，却忽略了各节点上时序之间的相关性。预定义的图邻接结构通常基于传感器地理位置之间的距离或上下游关系构建邻接矩阵，但这样会导致两个节点上时间序列相关却无直接连边的情况发生。如图1所示，左图表示交通路网中的节点分布，右图中实线表示预定义的邻接结构，虚线表示存在时序相关性的节点对。从图中可以看出，仅利用预定义的邻接关系无法全面反映节点之间的相互影响。其次，现有图神经网络建模交通流预测方法的另一个缺陷在于，这类方法往往分别探索时间和空间维度的特征，最后再进行融合，这种延迟融合策略会导致模型不能实时获取全局信息，从而影响模型预测效果。

![](images/02b1f82f7efad1d9140820f69a485e50d0142267135ac9ca54323a7eac506935.jpg)  
图1问题描述

为解决上述问题，本文提出了一种新的端到端的时空数据预测模型，即Ada-GGNN。首先，该模型通过空间传递模块捕获交通路网的空间依赖性，并从中挖掘出节点间时序的关联关系。然后通过GRU[I2]学习交通数据动态的时间依赖性，并在每个时间步进行多次的时空融合，探索时间和空间的高阶交互，获得时空嵌入表示，最后将这些表示通过全连接层进行最后的嵌入，得到预测结果。该工作的主要贡献如下：

(1)通过一种可学习的方式来获取时序间的自适应相关性矩阵，以捕获节点间因预定义邻接结构而丢失的关联关系。

(2)采用循环聚合方法来实时融合时空嵌入表示，使得模型的时空嵌入表示更丰富。

(3)在两个真实交通数据集上，Ada-GGNN的实验结果证明了该方法的有效性。同时，所提出的方法具有很好的泛化性，很容易拓展到其他时空数据挖掘任务中。

# 1 相关工作

# 1.1图神经网络

Gori等人[13]首次提出了图神经网络(GNN)，并将其应用于图结构数据。随后，关于GNN的改进及其变体在各项任务中取得了极大的进步。Defferrard等人[I4]采用一种快速局部卷积滤波器对GCN进行了改进，提出了ChebNet模型。Kipf等人[15]使用基于光谱卷积的一阶近似来简化ChebNet模型，并在半监督分类任务中达到了极好的分类效果。文献[16]通过采样每个节点固定数量的邻居并进行聚合，从而提高了大图的可扩展性。文献[17]提出了GAT模型，它是一种强大的GCN变体，通过引入一种注意力机制来动态地确定每个邻居节点对中心节点的重要性。然而，以上的GNN模型通常采用多层感知机更新节点的隐藏状态，因此，在图的长范围信息传播中存在限制。

为了解决上述问题，Li等人[18]提出了门控图神经网络(GGNN)，这是一种基于GRU的经典空间域消息传递模型。由于GGNN在时空数据上的有效性，它已被应用于各种任务。Zhang 等人[19]提出了TextING 模型，该模型为每个文档构建单独的图，然后使用GGNN来学习词节点的嵌入，通过大量实验，该方法已被证明优于最先进的文本分类方法。文献[20]专注于一种新颖的金融事件预测任务，它使用GGNN基于事件图来更新事件表示。文献[21]改进了GGNN 模型以更好地模拟节点交互并更好地从图中推断出兼容性。此外，GGNN还被应用于其他任务，如推荐[22]、图像分类[23]、情景识别[24]等。对于时空数据预测问题，GGNN表现出了优秀的性能，受此启发，本文采用GGNN框架和可学习的自适应节点相关性矩阵来共同应对长短期的交通预测问题。

# 2 模型

# 2.1问题定义

在交通预测任务中通常将每个传感器看做一个节点，传感器之间的距离或上下游关系构成节点之间的连边，则交通网络可被定义为无向图 $G = ( V , E , \mathbb { A } )$ ，其中 $\boldsymbol { V }$ 是节点集合， $\boldsymbol { E }$ 是节点间边的集合， $\mathbf { A } \in \mathbb { R } ^ { N \times N }$ 是图 $G$ 的邻接矩阵。在时间步t时，N 个节点的交通状况表示为 $\mathbf { X } ^ { \mathrm { t } } \in \mathbb { R } ^ { N \times D }$ ，其中 $\mathrm { ~ D ~ }$ 表示特征维度。因此，交通预测问题可以看做是给定一个路网拓扑结构 $\boldsymbol { G }$ 和T 个时间步的历史交通信息，学习一个映射函数 $f$ ，使得能够预测接下来 $\tau$ 个时刻的交通信息，其定义如式(1)所示。

$$
\left[ { \cal X } ^ { \iota + 1 } , \cdots , { \cal X } ^ { \iota + \tau } \right] = f \left( \left[ { \cal X } ^ { \iota \cdot \mathrm { T } + 1 } , \cdots , { \cal X } ^ { \iota - 1 } , { \cal X } ^ { \iota } \right] , G \right)
$$

# 2.2模型总体架构

Ada-GGNN模型主要由每个时间步的两阶段时空融合模块(STFusionmodule)组成，每个时空融合模块包含两个部分：空间传递模块(SPmodule，SpatialPassing module)和门控循环单元(GRU)。如图2所示，首先使用T个时间步的历史数据作为输入，在每个时间步中，利用空间传递模块捕获交通路网的固定拓扑结构和学习序列之间的自适应关联关系。然后，将具有空间特征的时间序列输入到门控循环单元，通过门控循环单元之间的信息传递获取序列数据的动态变化，捕捉时间特征并进行时空数据融合。最后，通过一个全连接层得到$\tau$ 个时间步的预测结果。

![](images/e35a9bfafa5f2a8e3c15ac52044c9149cc6aff54ce6f83ac371e42f748e47578.jpg)  
Fig.1Problem description   
图2模型框架  
Fig.2Model architecture diagram

# 2.3 空间传递模块

考虑到交通路网的拓扑结构，空间传递模块主要用来捕获道路之间的空间依赖性关系。如图3所示，空间传递模块包含两部分，一方面是通过预定义的邻接矩阵获取固定的空间关系，另一方面通过可学习的相关性矩阵获取节点间的关联关系。在该模块中，采用图卷积操作对节点间传递的信息进行提取。对于交通路网中显式的空间关系，通常基于传感器之间的位置距离构建其邻接矩阵，表示为 $\mathbf { A } _ { \mathrm { o r g } } \in \mathbb { R } ^ { N \times N }$ 。令

$I ^ { \mathrm { t , k } } \in \mathbb { R } ^ { N \times F }$ 表示输入的交通数据， ${ \bf W } _ { \mathrm { o r g } } ^ { \mathrm { k } } \in \mathbb { R } ^ { F \times D }$ 表示模型参数矩阵，并采用ReLU激活函数，因此该图卷积层定义如式(2)所示。

$$
Z _ { \mathrm { o r g } } ^ { \mathrm { t , k } } = R e L U \left( \mathrm { A } _ { \mathrm { o r g } } I ^ { \mathrm { t , k } } \mathrm { W } _ { \mathrm { o r g } } ^ { \mathrm { k } } \right) , k \in [ 1 , 2 ]
$$

对于交通路网中节点上时间序列的关联关系挖掘，令$\mathbf { A } _ { a d a } \in \mathbb { R } ^ { N \times N }$ 表示可学习的节点间自适应相关性矩阵，并随机初始化，通过模型的训练自动捕获和调整节点间关联关系的大小。该图卷积层定义如式(3)所示。

$$
{ \cal { Z } } _ { a d a } ^ { \mathrm { t , k } } = { R e L U } \left( { \mathrm { A } } _ { a d a } I ^ { \mathrm { t , k } } { \mathrm { W } } _ { a d a } ^ { \mathrm { k } } \right) , k \in [ 1 , 2 ]
$$

值得注意的是，该模块对交通路网中的拓扑关系进行了二阶交互( $\mathbf { k } \in [ 1 , 2 ]$ )，因此，当 $\mathbf { k }$ 为1时， $I ^ { \mathrm { t , k = 1 } } = \mathrm { X ^ { \mathrm { t } } }$ · $\mathbf { k }$ 为2时，$I ^ { \mathrm { t } , \mathrm { k } - 2 } = \mathrm { G R U ^ { \mathrm { t } , \mathrm { k } - 1 } }$ (如图1所示)。最后，将两部分提取到的信息通过拼接的方式进行特征融合，如式(4)所示。

![](images/45e3a7f4d516ce1b078abdf108a62bef3a6ddf54ca62bc1388e6a90bf74a3a01.jpg)  
图3空间传递模块结构 Fig.3The architecture of the SP module

# 2.4时空融合模块

空间传递模块捕获了每个时间步节点之间的空间特征和序列相关性，并提取了它们融合后的特征表达，但交通预测是一个时空预测任务，不仅仅要捕获空间信息，还需要捕获序列上的时间依赖性。因此，在时空融合模块，通过GRU捕获序列时间维度上的依赖性，并以循环聚合的方式在每个时间步进行实时的时空融合。如公式(5)所示，GRU接收两个输入，一个是具有空间信息的当前时刻数据嵌入表示 $\mathbf { Z ^ { \in , k } }$ ，另一个是上一状态表示 $\mathrm { H } _ { \mathrm { p } \varepsilon \in }$ 。由于在每个时间步Ada-GGNN采取了二阶的时空交互(如图1所示)，所以在 $\mathbf { k }$ 阶时的上一状态表达有所不同，具体如公式(6)所示。

$$
\mathrm { H ^ { t , k } } = G R U \left( \mathrm { Z ^ { t , k } , H _ { p r e } } \right)
$$

$$
\left\{ \begin{array} { l } { \mathrm { H } _ { \mathrm { p r e } } = \mathrm { H } ^ { \mathrm { t - 1 } , \mathrm { k + 1 } } , k = 1 } \\ { \mathrm { H } _ { \mathrm { p r e } } = \mathrm { H } ^ { \mathrm { t } , \mathrm { k - 1 } } , k = 2 } \end{array} \right.
$$

GRU通过门控机制来控制当前时刻输入和上一状态的写入程度，更新门的值越大，重置门的值越小，则表示上一状态的信息被写入的越少。以这种方式，Ada-GGNN能够捕获交通数据长期的时间相关性，其详细操作如下公式所示。

$$
\mathsf { u } ^ { \mathrm { t } , \mathrm { k } } = \sigma \big ( \mathsf { w } _ { \mathrm { u } } \left[ \mathsf { Z } ^ { \mathrm { t } , \mathrm { k } } , \mathsf { H } _ { \mathrm { p r e } } \right] + b _ { u } \big )
$$

$$
\boldsymbol { \Upsilon } ^ { \mathrm { t , k } } = \sigma \big ( \tilde { W } _ { \mathrm { r } } \left[ \boldsymbol { \mathrm { Z ^ { \mathrm { t , k } } } } , \boldsymbol { \mathrm { H _ { \mathrm { p r e } } } } \right] + \boldsymbol { b } _ { r } \big )
$$

$$
\tilde { \mathrm { h } } ^ { \mathrm { t } , \mathrm { k } } = t a n h \big ( \mathbb { W } _ { \mathrm { i } } \left[ \mathrm { Z } ^ { \mathrm { t } , \mathrm { k } } , \mathrm { r } ^ { \mathrm { t } , \mathrm { k } } ^ { * } \mathbb { H } _ { \mathrm { p r e } } \right] + b _ { \widetilde { h } } \big )
$$

$$
\mathrm { H ^ { \mathrm { t , k } } = \left( 1 - u ^ { \mathrm { t , k } } \right) ^ { \ast } H _ { \mathrm { p r e } } + u ^ { \mathrm { t , k } } \ast \tilde { \mathrm { h } } ^ { \mathrm { t , k } } }
$$

其中， $\uplus ^ { \uplus ^ { \dag , \boldsymbol { k } } }$ 和 $\mathbf { r } ^ { \mathrm { { t , k } } }$ 分别表示GRU中更新门和重置门大小，o表示Sigmoid激活函数， $W$ 和 $b$ 是可学习参数。

# 2.5 预测

经过 $\mathrm { ~ T ~ }$ 个时间步的时空融合后，Ada-GGNN采用全连接层得到最后的预测结果 $\hat { \Upsilon }$ ，如公式(12)所示。

$$
\hat { \mathrm { Y } } = \boldsymbol { \mathrm { W } } _ { \mathrm { o u t } } \mathrm { H } ^ { \mathrm { t = T } , \mathrm { k = 2 } } + \boldsymbol { b } _ { o u t }
$$

其中， $\boldsymbol { \mathsf { W } } _ { \mathrm { o u t } }$ 和 $b _ { o u t }$ 为全连接层参数。考虑到交通预测问题是一个回归任务，所以采用平均绝对误差(MAE)作为损失函数，其定义如公式(13)所示。

# 3 实验

# 3.1 数据集

为了评估所提出模型的有效性，在两个公开可用的真实交通数据集PeMSD7和Los-loop上进行了实验。PeMSD7数据集是加利福尼亚州2012年5月和6月(仅工作日，共44天)的交通数据，由228个传感器收集的交通速度组成。Los-loop数据集是洛杉矶高速公路上207个检测器收集的2012年3月1日至7日的交通速度数据。在所有实验中，将每间隔5分钟汇总一次的交通速度作为交通特征，并选择前 $80 \%$ 的数据作为训练集，剩下的 $20 \%$ 作为测试集。其数据集的具体统计信息如表1所示。

表1两个数据集的统计信息  
Tab.1Summary statistics of two traffic network datasets   

<html><body><table><tr><td>数据集</td><td>节点</td><td>边</td><td>时间步长</td><td>最大值</td><td>平均值</td></tr><tr><td>PeMSD7</td><td>228</td><td>832</td><td>12672</td><td>82.6</td><td>58.9</td></tr><tr><td>Los-loop</td><td>207</td><td>2833</td><td>2016</td><td>70.0</td><td>58.9</td></tr></table></body></html>

# 3.2实验设置

在实验中，采用Python 编程语言和Pytorch 深度学习框架对模型进行实现，将前60分钟的交通数据作为模型的输入预测未来15、30、60分钟的交通速度。训练过程中，学习率设置为0.001，epoch设置为1000，采用Adam优化器[25]。为防止模型过拟合，采用“早停法”(Early Stopping)进行训练。所有实验均在具有16GBRAM的单个NVIDIATeslaT4GPU上进行。

本文所提出的模型与以下七种基线方法进行比较：

a)ARIMA：自回归整合移动平均模型是一种经典的自回归模型，它将自回归、滑动平均以及差分法结合在一起对时间序列数据进行预测。

b)SVR[26]：支持向量回归模型是SVM的重要应用分支，实验中采用线性核函数进行交通预测任务。

c)ASTGCN[10]：该模型主要由三个独立的组件组成，分别对小时、天、周的时间属性进行建模，每个组件都包含了时空注意力机制和时空卷积两个操作部分，并通过加权融合的方式产生最终的预测。

d)T-GCN[II]：该模型通过GCN学习交通路网的拓扑结构，GRU来学习交通数据的动态变化，从而捕获空间依赖性和时间依赖性。

e)A3T-GCN[27]：A3T-GCN在T-GCN 的基础上，引入了注意力机制来调整不同时间点的重要性并组装全局时间信息来进行交通预测。

f)LSGCN[28]：该模型将GCN和图注意力网络集成到一个空间门控块中，通过空间门控块和门控线性单元[29](GLU)来捕获数据的时空特征并得到预测结果。

g)GWN[30]：该模型通过一个可学习的方式来捕捉数据中隐藏的空间依赖，同时，使用扩张一维卷积组件扩大感受野以此来处理长序列数据。

为了验证Ada-GGNN的有效性，采用以下三个评价指标来测试各模型性能。

a）均方根误差(RMSE)

$$
\mathrm { R M S E } = \sqrt { \frac { 1 } { M } \sum _ { i = 1 } ^ { M } \left( \hat { y } _ { i } - y _ { i } \right) ^ { 2 } }
$$

b）平均绝对误差(MAE)

$$
\mathrm { M A E } = \frac { 1 } { M } \sum _ { i = 1 } ^ { M } \bigl | \hat { y } _ { i } - y _ { i } \bigr |
$$

c）平均绝对百分比误差(MAPE)

$$
\mathrm { M A P E } = \frac { 1 } { M } \sum _ { i = 1 } ^ { M } \left| \frac { \hat { y } _ { i } - y _ { i } } { y _ { i } } \right| \times 1 0 0 \%
$$

其中： $M$ 表示样本数量， $y _ { i }$ 表示第i个样本的实际交通速度，$\hat { y } _ { i }$ 表示第i个样本的模型预测值。

# 3.3 实验结果分析

表2显示了Ada-GGNN 和其他基线模型在两个数据集上进行15、30和60分钟交通预测的比较结果，从表2中可以得到以下观察结果：

基于神经网络的方法在两个数据集上的所有评估指标比传统的时间序列分析方法和机器学习方法(如ARIMA和 SVR)具有更低的预测误差。这些结果的原因是ARIMA和SVR模型的非线性建模能力有限。特别是ARIMA对数据的稳定性要求很高，但交通数据是复杂的，且影响因素较多，所以ARIMA呈现出最不理想的预测结果。相比之下，这些神经网络模型不仅擅长对非线性数据进行建模，还引入了拓扑结构获得交通路网的空间特征。因此，基于神经网络的方法表现出更好的性能。

Ada-GGNN在两个数据集的长期和短期预测上实现了比其他基线模型更先进的预测性能。例如，对于Los-loop 数据集上的15分钟交通预测任务，Ada-GGNN在RMSE上比GWN提高了 $2 . 2 1 \%$ ，比LSGCN提高了 $8 . 1 0 \%$ 。类似的结果也出现在其他时间跨度预测任务和评估指标的比较中。这主要是Ada-GGNN模型的架构因素促进了这些改进。首先，Ada-GGNN是一次输出多个时间步的预测结果，而LSGCN需要依靠先前的预测再生成下一时间步的预测，这样会导致预测误差的累积，所以在长期的预测结果上Ada-GGNN表现更优异。此外，Ada-GGNN采用可学习的方式挖掘了交通路网中节点序列之间的关联关系，使得节点的嵌入表达更丰富，为模型引入了新的有用信息，有助于提高预测精度。最后，所提出的模型应用了循环聚合方法以实时融合方式学习时空嵌入，而不是单独的提取和延迟融合范式，这有助于学习细粒度的动态时空关系。

# 3.3.1隐藏层单元数目的影响

通常，隐藏层单元的数目是导致过拟合的直接原因，因此隐藏层单元数目的设置在模型调优过程中至关重要。本实验从[16,32,64,96,128,160]中选择隐藏单元数量，并分析不同隐藏单元数量对模型预测精度的影响。如图4所示，横轴表示隐藏单元的数量，纵轴表示不同的度量指标。从图中可以看出，随着隐藏单元个数的增加，RMSE和MAE指标先降低再增加，且当隐藏层单元个数为96时，Los-loop和PeMSD7数据集的预测误差最低。这主要是因为隐藏单元个数过大时，模型复杂度较大，容易发生过拟合。

![](images/a9bc37c7b9186f4595e83d7a2a012ca194f54fc7316c67a50aa243480492f2c4.jpg)  
图4在两个数据集上不同隐藏层单元个数的影响Fig.4Influence of different hidden units on both datasets  
图5高斯扰动和泊松扰动对Ada-GGNN在Los-loop 数据集上的影响Fig.5The influence of Gaussian perturbation and Poissonperturbation on the Ada-GGNN on the Los-loop dataset

3.3.2模型鲁棒性验证

在交通数据采集过程中，传感器难免会为数据引入噪声，因此，本实验通过扰动分析实验来测试Ada-GGNN的模型鲁棒性。如图5所示，在实验中添加了两种随机噪声，分别是高斯噪声和泊松噪声。高斯噪声服从高斯分布 $N \in ( \mu = 0 , \sigma ^ { 2 } )$ ，其中方差 $\sigma \in \left[ 0 . 2 , 0 . 4 , 0 . 6 , 0 . 8 , 1 \right]$ ；泊松噪声服从泊松分布 $P ( \lambda )$ ，其中参数 $\lambda \in \left[ 1 , 2 , 4 , 8 , 1 6 \right]$ 。从图中结果可以看出，Ada-GGNN无论在何种噪声分布中，其评估指标的变化都很微小。因此，Ada-GGNN可以适应噪声数据且具有很强的鲁棒性。

表2Ada-GGNN 与其他基准模型在PeMSD7和Los-loop 数据集上的性能比较  

<html><body><table><tr><td colspan="12">pemsd7 and Los-loop datasets</td></tr><tr><td rowspan="3">Datasets</td><td rowspan="3">Models</td><td rowspan="3"></td><td colspan="3">15min</td><td colspan="3">30min</td><td colspan="3">60min</td></tr><tr><td colspan="3">RMSEMAEMAPE</td><td colspan="3">RMSEMAE MAPERMSEMAE MAPE</td><td colspan="3"></td></tr><tr><td>ARIMA 12.29</td><td></td><td>10.12 25.29%</td><td></td><td>12.30 10.12 25.30% 12.35</td><td></td><td></td><td></td><td>10.23 25.42%</td></tr><tr><td rowspan="8">PeMSD7</td><td>SVR</td><td>4.89</td><td></td><td>4.08 8.28%</td><td></td><td>5.90</td><td>4.66</td><td>9.77%</td><td>7.43</td><td>5.64</td><td>12.30%</td></tr><tr><td>ASTGCN</td><td></td><td>3.41</td><td>1.94 4.50%</td><td></td><td>4.56</td><td>2.58</td><td>6.11%</td><td>6.11</td><td>3.31</td><td>8.39%</td></tr><tr><td>T-GCN</td><td></td><td>3.45</td><td>1.93</td><td>4.41%</td><td>4.50</td><td>2.52</td><td>5.93%</td><td>6.08</td><td>3.23</td><td>8.32%</td></tr><tr><td>A3T-GCN</td><td></td><td>3.40</td><td>1.89</td><td>4.30%</td><td>4.38</td><td>2.35</td><td>5.68%</td><td>5.82</td><td>3.39</td><td>8.19%</td></tr><tr><td>LSGCN</td><td></td><td>3.37</td><td>1.92</td><td>4.33%</td><td>4.43</td><td>2.33</td><td>5.66%</td><td>6.17</td><td>3.48</td><td>8.38%</td></tr><tr><td>GWN</td><td></td><td>3.39</td><td>1.89</td><td>4.32%</td><td>4.45</td><td>2.39</td><td>5.62%</td><td>5.96</td><td>3.15</td><td>7.86%</td></tr><tr><td>Ada-GGNN</td><td></td><td>3.30</td><td>1.82</td><td>4.21%</td><td>4.34</td><td>2.32</td><td>5.59%</td><td>5.46</td><td>2.91</td><td>7.18%</td></tr><tr><td>ARIMA</td><td></td><td>10.05</td><td>7.71 20.84%</td><td></td><td>10.06</td><td></td><td>7.71 20.86% 10.07</td><td></td><td>7.72</td><td>20.90%</td></tr><tr><td colspan="2">SVR</td><td></td><td>5.65</td><td>3.86 9.33%</td><td></td><td>6.73</td><td>4.65</td><td>11.51%</td><td>8.03</td><td>4.22</td><td>14.65%</td></tr><tr><td colspan="2">ASTGCN</td><td></td><td>5.25</td><td>3.27</td><td>8.05%</td><td>6.14</td><td>3.76</td><td>9.68%</td><td>7.47</td><td>4.43</td><td>12.29%</td></tr><tr><td colspan="2">Los- T-GCN</td><td></td><td>5.21</td><td>3.27</td><td>8.34%</td><td>6.12</td><td>3.81</td><td>9.96%</td><td>7.27</td><td>4.42</td><td>12.11%</td></tr><tr><td colspan="2">loop A3T-GCN</td><td></td><td>5.12</td><td>3.17</td><td>8.08%</td><td>6.10</td><td>3.73</td><td>9.98%</td><td>7.23</td><td>4.56</td><td>12.21%</td></tr><tr><td colspan="2">LSGCN</td><td></td><td>5.31</td><td>3.35</td><td>8.33%</td><td>6.24</td><td>3.82</td><td>9.95%</td><td>7.63</td><td>4.88</td><td>12.94%</td></tr><tr><td colspan="2">GWN Ada-GGNN</td><td>4.88</td><td>4.99</td><td>2.86 2.79</td><td>7.32% 7.16%</td><td>5.93 5.83</td><td>3.26</td><td>8.81%</td><td>7.15</td><td>3.98</td><td>11.48%</td></tr><tr><td colspan="10">RMSE MAE 5 5</td><td>RMSE</td><td>000000</td><td>MAE</td><td></td></tr><tr><td>4 3</td><td></td><td></td><td></td><td></td><td></td><td></td><td>4 3</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>2 1 0</td><td></td><td></td><td></td><td></td><td></td><td>2 1</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>0.2</td><td>0.4 (a）高斯扰动</td><td>0.6 0</td><td>0.8</td><td>1</td><td>0</td><td>Po 1</td><td>2</td><td>4 入</td><td>(b)泊松扰动</td><td>8</td><td>16</td><td></td></tr></table></body></html>

# 3.3.3自适应相关性矩阵的验证

为了验证空间传递模块中自适应相关性矩阵学习的有效性，设计了如下对比实验。其中，NoAda 模型在Ada-GGNN的基础上去除了自适应时序相关性学习操作，仅采用预定义邻接矩阵来捕获交通路网的空间依赖性。在两个数据集上的15分钟和60分钟预测任务上的实验结果如表3所示。

Tab.2Performance comparison of Ada-GGNN and other baselines on   
表3空间传递模块中时序相关性学习的影响  
Tab.3Influence of learning time-series correlation in the SP module   

<html><body><table><tr><td rowspan="2">Datasets</td><td rowspan="2">Models</td><td colspan="2">15min</td><td colspan="3">60min</td></tr><tr><td>RMSE</td><td>MAE</td><td>MAPE</td><td>RMSE MAE</td><td>MAPE</td></tr><tr><td rowspan="2">PeMSD7</td><td>No_Ada</td><td>3.59</td><td>1.99</td><td>4.62% 5.99</td><td>3.18</td><td>7.98%</td></tr><tr><td>Ada-GGNN</td><td>3.30</td><td>1.82</td><td>4.21% 5.46</td><td>2.91</td><td>7.18%</td></tr><tr><td rowspan="2">Los-loop</td><td>No_Ada</td><td>5.05</td><td>2.86</td><td>7.28%</td><td>7.59 4.08</td><td>11.55%</td></tr><tr><td>Ada-GGNN</td><td>4.88</td><td>2.79</td><td>7.16% 7.07</td><td>3.90</td><td>10.96%</td></tr></table></body></html>

从表3的实验结果可以发现，在两个数据集的不同任务中，所提出的Ada-GGNN模型的预测性能明显优于No_Ada模型。这主要是因为Ada-GGNN模型不仅捕获了道路网络的空间关系，还学习到了各节点间的时序相关性，弥补了以往基于图神经网络的交通流预测方法仅含有单一的空间关系的缺陷。

同时，为进一步解释学习到的自适应相关性矩阵的作用，还进行了以下实验，即通过Los-loop数据集上部分节点的地理位置可视化和学习到的节点序列间相关性矩阵的热力图做进一步探索。图6(a)是6个节点的地理位置图，图6(b)是经过归一化处理后对应的6个节点序列之间的相关性矩阵热力图。首先，从图6(b)可以明显看到，2号节点所在列比其他列的高值点更多，这表明2号节点在预测时对图中其他节点更具影响，且该节点与其他节点序列相关性较高。其次，在预定义的固定邻接矩阵中，6号节点由于距离3、4号节点太远，并不存在连接关系。然而从图6(b)中能够发现，6号节点对3、4号节点有较大影响且存在关联关系。这表明Ada-GGNN能够通过自适应相关性矩阵发现因距离原因在预定义邻接矩阵中丢失的节点连接，并为模型引入新的有用信息，提高模型预测精度。

![](images/06f1ade8720cdf67517e03ebcca9926aa17a9a9b7a61a20bc53d794689eb8ce7.jpg)  
图6学习到的自适应相关性矩阵  
Fig.6The learned self-adaptive correlation matrix

3.3.4模型计算花销

表4展示了Ada-GGNN和其他基于神经网络的基线模型在Los-loop数据集上关于计算时间花销的比较。在训练阶段，Ada-GGNN比ASTGCN快1.07秒，比GWN快8.65秒，但是比T-GCN、A3T-GCN和LSGCN大概慢2\~3秒左右，这主要是因为T-GCN仅使用一层图卷积和一个GRU进行流量预测，而GWN却具有复杂的模型结构，它在每个时空层都有残差连接，计算量更大。在测试集上，LSGCN比其他模型花费了更多时间，这是因为LSGCN必须根据先前的预测来生成之后的预测结果，而其他模型都是一次生成多个时间步预测结果。因此考虑模型的预测精度和时间花销，所提出的Ada-GGNN仍然具有很强的综合表现。

表4Los-loop 数据集上的计算时间  
Tab.4 Computation time on the Los-loop dataset   

<html><body><table><tr><td rowspan="2">Models</td><td colspan="2">Computation Time</td></tr><tr><td>Training(s/epoch)</td><td>Testing (s)</td></tr><tr><td>ASTGCN</td><td>5.59</td><td>0.44</td></tr><tr><td>T-GCN</td><td>0.95</td><td>0.11</td></tr><tr><td>A3T-GCN</td><td>1.05</td><td>0.11</td></tr><tr><td>LSGCN</td><td>1.95</td><td>1.83</td></tr><tr><td>GWN</td><td>13.17</td><td>0.60</td></tr><tr><td>Ada-GGNN</td><td>4.52</td><td>0.41</td></tr></table></body></html>

# 4 结束语

本文针对交通流预测问题提出了一种新的端到端的自适应门控图神经网络(Ada-GGNN)模型。该模型利用可学习的自适应矩阵从数据中获取节点间的序列相关性，为模型引入了新的有用信息，并基于门控图神经网络来处理长期的预测问题。在两个公共交通数据集上，Ada-GGNN取得了最优异的结果。考虑到实际的交通预测问题受到许多外部因素的影响，例如天气、温度、社会事件等，因此，在未来的工作中，将引入更多的额外因素作为特征，并探索在大图上应用Ada-GGNN的可扩展方法。

# 参考文献：

[1]刘静，关伟．交通流预测方法综述[J].公路交通科技,2004,21(3): 82-85.(Liu Jing,Guan Wei. A summary of traffic flow forecasting methods [J]. Journal of Highway and Transportation Research and Development,2004,21 (3): 82-85.)   
[2]Williams B M,Hoel LA.Modeling and forecasting vehicular traffic flow as a seasonal ARIMA process: theoretical basis and empirical results [J]. Journal of Transportation Engineering,2003,129 (6): 664-672.   
[3] Zivot E,Wang Jiahui.Vector autoregressive models for multivariate time series [M]//Modeling Financial Time Series with S-Plus?.New York, NY, USA: Springer, 2003: 369-413.   
[4] 张晓利，贺国光，陆化普．基于K-邻域非参数回归短时交通流预测 方法[J]系统工程学报,2009,24(2):178-183.(Zhang Xiaoli,He Guoguang,Lu Huapu. Short-term traffic flow forecasting based on Knearest neighbors non-parametric regression [J]. Journal of Systems Engineering,2009,24 (2): 178-183.)   
[5] Yu R,Li Yaguang, Shahabi C,et al. Deep learning: a generic approach for extreme condition traffic forecasting [C]//Proc of SIAM International Conference on Data Mining. 2017: 777-785.   
[6]Shi Xingjian,Chen Zhourong,Wang Hao,et al. Convolutional LSTM network: a machine learning approach for precipitation nowcasting [C]// Proc of the 28th International Conference on Neural Information Processing Systems. Cambridge, MA: MIT Press,2015: 802-810.   
[7]Zhang Junbo, Zheng Yu,Qi Dekang.Deep spatio-temporal residual networks for citywide crowd flows prediction [Cl// Proc of the 31st AAAI Conference on Artificial Intelligence.Palo Alto,CA: AAAI Press, 2017: 1655-1661.   
[8]Li Yaguang, Yu R, Shahabi C,et al. Diffusion convolutional recurrent neural network:data-driven traffic forecasting [C/OL]/Proc of the 6th International Conference on Learning Representations.[S.1.]: OpenReview.net，2018．(2018）[2022-01-12]. https://openreview. net/forum?id=SJiHXGWAZ.   
[9] Yu Bing，Yin Haoteng， Zhu Zhanxing. Spatio-temporal graph convolutional networks:a deep learning framework for traffic forecasting [C]// Proc of the 27th International Joint Conference on Artificial Intelligence.California: IJCAI,2018: 3634-3640.   
[10] Guo Shengnan,Lin Youfang,Feng Ning,et al. Attention based spatialtemporal graph convolutional networks for traffic flow forecasting [C]/ Proc of the 33rd AAAI Conference on Artificial Intelligence.Palo Alto, CA: AAAI Press,2019: 922-929.   
[11] Zhao Ling,Song Yujiao,Zhang Chao,et al. T-GCN: a temporal graph convolutional network for traffic prediction [J].IEEE Trans on Intelligent Transportation Systems,2020,21(9): 3848-3858.   
[12] Cho K,Van Merrienboer B，Gulcehre C,et al. Learning phrase representations using RNN encoder-decoder for statistical machine translation [C]//Proc of EMNLP. Stroudsburg,PA: ACL,2014: 1724-1734.   
[13] Gori M, Monfardini G, Scarseli F. A new model for learning in graph domains [C]//Proc of IEEE IJCNN.Piscataway,NJ: IEEE Press,2005:729-734.   
[14] Defferrard M，Bresson X,Vandergheynst P. Convolutional neural networks on graphs with fast localized spectral filtering [C]//Proc of the 30th International Conference on Neural Information Processing Systems. Red Hook,NY: Curran Associates Inc,2016: 3837-3845.   
[15] Kipf T N，Welling M. Semi-supervised classification with graph convolutional networks [C/OL]/ Proc ofthe 5th International Conference on Learning Representations.[S.1.] : OpenReview.net,2017. [2022-01- 12]. https://openreview. net/forum?ic $\vDash$ SJU4ayYgl.   
[16] Hamilton WL,Ying R,Leskovec J. Inductive representation learning on large graphs [C]//Proc of the 31st International Conference on Neural Information Processing Systems.Red Hook,NY:Curran Associates Inc, 2017:1025-1035.   
[17]Velickovic P,Cucurull G,Casanova A,et al.Graph attention networks [C/OL]/ Proc of the 6th International Conference on Learning Representations.[S.1.] : OpenReview. net,2018.(2018) [2022-01-12]. https://openreview.net/forum?id=rJXMpikCZ.   
[18]Li Yujia, Zemel R,Brockschmidt M,et al.Gated graph sequence neural networks [C/OL]/Proc of the 4th International Conference on Learning Representations.2016.(2016)[2022-01-12].http://arxiv.org/abs/1511.05493.   
[19] Zhang Yufeng,Yu Xueli,Cui Zeyu,et al.Every document owns its structure: inductive text classification via graph neural networks [C]/ Proc of the 58th Annual Meeting of the Association for Computational Linguistics. Stroudsburg,PA:ACL,2020:334-339.   
[20] Yang Yiying,Wei Zhongyu,Chen Qin, et al.Using external knowledge for financial event prediction based on graph neural networks [C]//Proc of the 28th ACM International Conference on Information and Knowledge Management.New York,NY,USA:ACM Press,2019: 2161-2164.   
[21] Cui Zeyu,Li Zekun，Wu Shu,et al.Dressing asa whole:outfit compatibility learning based on node-wise graph neural networks [C]// Proc ofWWW Conference.New York,NY,USA:ACM Press,2019: 307-317.   
[22]Wu Shu,Tang Yuyuan， Zhu Yanqiao， etal. Session-based recommendationwith graph neural networks [C]//Proc of the 33rd AAAI Conference on Artificial Intelligence.Palo Alto,CA:AAAIPress,2019: 346-353.   
[23] Marino K,Salakhutdinov R,Gupta A. The more you know:using knowledge graphs for image classification[C]//Proc ofIEEE CVPR.Los Alamitos,CA:IEEE Computer Society,2017: 20-28.   
[24]LiRuiyu,Tapaswi M,Liao Renjie,et al.Situation recognition with graph neural networks [C]//Proc ofIEEE ICCV.Los Alamitos,CA,USA: IEEE Computer Society,2017:4183-4192.   
[25]Kingma DP,Ba J.Adam: a method for stochastic optimization [C/OL]/ Proc of the 3rd International Conference on Learning Representations. 2015.(2015)[2022-01-12].http://arxiv.org/abs/1412.6980.   
[26] Smola A J,Scholkopf B.A tutorial on support vector regression [J]. Statistics and Computing,2004,14 (3):199-222.   
[27] Bai Jiandong,Zhu Jiawei,Song Yujiao,et al.A3T-GCN:attention temporal graph convolutional network for traffic forecasting [J].ISPRS International Journal of Geo-Information,2021,10(7): 485.   
[28]Huang Rongzhou,Huang Chuyin,Liu Yubao,etal.LSGCN: long shortterm traffic prediction with graph convolutional networks [C]//Proc of the 29th International Joint Conference on Artificial Intelligence. California: IJCAI, 2020:2355-2361.   
[29]Dauphin Y N,Fan A,Auli M,et al.Language modeling with gated convolutional networks [C]//Proc of the 34th International Conference on Machine Learning.[S.1.]:PMLR,2017: 933-941.   
[30] Wu Zonghan,Pan Shirui,Long Guodong,et al.Graph WaveNet for deep spatial-temporal graph modeling[C]//Proc of the 28th International Joint Conference on Artificial Intelligence.California:IJCAI,2019:1907- 1913.