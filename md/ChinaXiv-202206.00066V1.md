# 融合外部属性的短时交通流预测研究

王庆荣ä，吴玉玉ä，朱昌锋ʰ，王媛a(兰州交通大学 a.电子与信息工程学院;b.交通运输学院，兰州 730070)

摘要：针对现有交通流量预测算法大多仅考虑常态下的预测，而未考虑天气属性、周围地理属性对预测结果的影响，提出一种融合外部属性的组合预测模型(A-STIGCN)。首先，将外部属性作为路网中路段的属性，同时对路段的属性和交通特征进行建模，得到增强的特征向量。其次，采用图小波变换和自适应矩阵分别提取交通流局部和全局空间特征信息，并借助门控循环单元(GRU)对时间信息的长时记忆能力以提取其时间特性，最后，通过注意力机制来捕获时空动态变化性进行交通流预测。采用深圳出租车轨迹数据、对应天气数据以及POI数据进行预测，研究结果表明：A-STIGCN 组合模型预测效果优于传统线性模型及变体模型，与未引入注意力机制的ASTGCN模型相比，MAE 降低了约0.131，精度提高了0.068，与及未引入外部因素的TGCN模型对比分析，MAPE降低了约 $0 . 6 3 7 \%$ ，精度提高了0.079，从而更好地为交通管理提供指导意见。

关键词：交通流预测；图小波变换；自适应矩阵；外部因素；门控循环机制；注意力机制 中图分类号：TP399doi:10.19734/j.issn.1001-3695.2022.04.0119

Short-term traffic flow prediction studies integrated with external properties

Wang Qingronga,Wu Yuyua,Zhu Changfengb,Wang Yuana (a.Schooloflectronics&InformationEngineering,b.holofrasportationLazhouJatong Unversityzou 730070,China)

Abstract: Mostof the existingtrafic flow prediction algorithms onlyconsider the prediction under normalconditions,but notthe influenceofweather attibutes and surrounding geographicalattibutes onthe predictionresults,This paper proposed acombined prediction model (A-STIGCN) integrating external atributes.First,the external atributesare taken as the atributesofthesections intheroad network,andtheatributesandtrafficcharacteristicsofthesectionsarealsoputunder modeling to obtain the enhanced feature vectors.Secondly,the method used graph wavelet transformand adaptive matrix to extract thelocal and global spatial feature information ofthe traficflowrespectively,with the helpof thegating cycleunit (GRU)toextractthetemporalinformation.Finally,thetemporal dynamicvariabilityof theatention mechanism iscaptured to predictthetrafficflow.Shenzhentaxi trajectorydata,corresponding weatherdataandPOIdataforprediction,theresearch results showthatA-STIGCNcombinationmodelisbetterthanthe traditional linear modelandvariantmodel,compared with the ASTGCN model without introducing atention mechanism,MAEreducedabout 0.131,accuracy improved 0.068,and the TGCN model without introducing external factors, MAPE. The reduction by about $0 . 6 3 7 \%$ and the improved accuracy by 0.079 provides better guidance for traffic management.

Key words:trafcflow prediction; graph wavelettransformation;adaptivematrix;exteralfactors;gatingcycle mechanism; attentionmechanism

# 0 引言

短时交通流预测一直是智能交通系统的研究热点，境内外关于交通流预测的研究主要围绕基于统计理论、非线性理论、神经网络等方法开展,建立了大量预测模型，如时间序列模型、卡尔曼滤波模型、非参数回归模型、神经网络模型等[1]。随着模型的不断改进，包括贝叶斯估计、支持向量回归(SVR)模型和随机森林模型[2]等在内的浅层机器学习方法由于具备一定的泛化能力以及较低的维护成本而在短时交通流预测中显示出了良好的应用前景，但是这类模型在特征提取与处理大规模数据方面存在着局限性，深度学习是数据驱动方法最主要的分支之一，与其他数据驱动方法相比，深度学习在高维数据处理、时空关系分析等方面更具优势[3]。由于未来的交通状态不仅取决于历史状态，而且还可能受到各种静态和动态的外部因素的影响，因此很难实现准确的交通预测。其中，静态因素不会随时间持续变化，但会在一定时间内使交通状态受到影响，动态因素会随时间而变化，并导致交通状况的变化。这些因素造成了交通状态的随机性，并使得准确的交通预测变得更加[4复杂，如何结合多源数据来实现精确的交通流预测是一个迫切需要解决的问题。

文献[5,6]使用深度学习理论捕捉长期依赖关系的能力，并引入注意力机制调节编码向量的权重以进一步提高模型的预测精度，但未深入考虑空间特性的提取；文献[7]提出了STGCN(时空图卷积网络)，可以提取时空特征且捕捉空间的依赖关系。文献[8]提出了DCRNN(扩散卷积循环网络)，分别采用扩散卷积和循环网络在有向图上捕获交通流的空间和时间依赖性，结果表明该模型具有良好的预测精度。文献[9]构造了基于关键路段的混合卷积长短期记忆神经网络模型来估计未来的交通变化，首先根据时空相关算法鉴别出对子网络影响最大的关键路段，然后将关键路段的交通速度当作ConvLSTM的输入来预测整个网络的将来的交通状态。实验结果验证了模型在不同关键路段下的预测能力。

虽然以上方法都获得了较好的结果,但多是在单一影响因素或特定情况下进行的实验，文献[10]基于图小波卷积算子，对交通数据的时空相关性和动态相关性进行建模；通过叠加多层图小波神经网络模块从交通网络图节点邻域中捕获空间相关性。但文献[11,12]均没有考虑多特征信息。鉴于此，文献[13]提出一种多特征注意力机制捕获交通数据复杂的特征关系．设计了一种信息增强传输机制捕获交通数据复杂的动态空间依赖，采用数据线性与非线性融合机制，有效地提高模型的预测精度。文献[14]选用GBDT算法进行建模对高速公路交通流量进行预测，着重分析天气变化、时段特征、星期特征等因素对原本封闭的高速公路系统的交通状态的影响，而且不同车辆类型具有较强的不确定性和随机性,对后续模型的提出产生重大的意义。

在此基础上，本文提出了一种将外部属性视为路段的属性信息，结合天气因素与周围地理因素，预测外部因素对于交通流的影响。通过整合属性信息和交通特征，增强模型对外部信息的感知，图小波网络可以全局处理路段拓扑信息,挖掘短时交通的空间特性，而且可以通过GRU对时间信息的长时记忆能力来提取其时间特性，使用注意力机制对重要信息分布足够的权重，来提高交通流的预测精度。

# 1 交通属性定义

交通流预测的目标是根据道路上的历史交通信息，对一定时期内的交通信息进行预测。将城市路网中交通量和影响交通的外部因素作为初始变量，来预测未来的交通流量。

# 1.1 路网特征属性

定义1路网 $G$ 。以城市路网交通流探测传感器 $i$ 安装位置为节点，以 $\nu _ { i }$ 表示，并且以相邻路段上的传感 $j$ 为邻居节点 $\nu _ { j }$ ，构建交通路网图模型 $G$ ，定义如[15]：

$$
G = ( V , E , A )
$$

其中， $\nu$ 表示节点集合，在路网中表示交通流探测传感器集合，且 $\left. V \right. = N$ 。 $E$ 是一组边缘，表示图 $\textbf { \textit { G } }$ 中边的集合，它反映了路段之间的连接。元素 $e _ { i } = \langle \nu _ { i } , \nu _ { j } \rangle \in E$ 表示节点 $\nu _ { i }$ 和节点 $\boldsymbol { \nu } _ { j }$ 有联结关系。在路网图构建过程中，通常以节点 $\nu _ { i }$ 邻域范围内邻居节点构建边或联结。 $A \in R ^ { N \times N }$ 为图 $G$ 的邻接矩阵，邻接矩阵只包含0和1的元素。如果道路之间没有相关，元素为0,1表示有相关。本文构建的交通路网图 $\textbf { \textit { G } }$ 是无向图。

定义2特征矩阵 $\mathbf { X }$ 。将路段上的交通流量视为网络节点的属性，用特征矩阵 $\boldsymbol { X } \in R ^ { N \times P }$ 表示，其中 $P$ 为节点属性特征的个数，即历史时间序列的长度。 $X _ { i }$ 表示时刻 $i$ 各路段的交通流量。

定义3属性矩阵K。将影响交通流的外部因素作为城市路网上路段的增强属性。这些因素可以形成一个属性矩阵$K = \{ K _ { 1 } , K _ { 2 } , . . . , K _ { l } \}$ ，其中 $l$ 为辅助信息的类别数。辅助信息的类别 $j$ 可以表示为 $K _ { j } = \{ j ^ { 1 } , j ^ { 2 } , . . . , j ^ { t } \}$ ， ${ j _ { i } ^ { t } }$ 是 $t$ 时刻第i条路段的第j个辅助信息。因此，时空依赖的交通预测建模可以看做是基于路网G、特征矩阵 $\mathrm { \Delta X }$ ，属性特征K的映射函数 $\mathbf { f } ^ { [ 1 6 ] }$ 。未来T时间段的交通速度计算如下：

$$
[ x _ { t + 1 } , x _ { t + 2 , } . . . , x _ { t + T } ] = f ( G , X \mid K )
$$

# 1.2外部属性特征

为了综合考虑影响交通状态的因素，将外部因素分为动态 ${ \mathbf { \eta } } ( { \pmb { D } } )$ 属性和静态 $( S )$ 属性。然后，将交通特征矩阵 $\boldsymbol { \cal X }$ 和属性矩阵 $A / = \{ S , ~ D \}$ 作为输入，得到增广矩阵[17]。

a)静态属性融合。 $S \in R ^ { n \times p }$ 是指 $p$ 个不同的静态属性的集

合。由于属性值不随时间变化，因此不断使用矩阵 $s$ ，而在每个时间戳生成增广矩阵的过程中，只提取相应的特征矩阵$X$ 列。具体来说，在 $t$ 时刻由静态属性增广的矩阵形成为

$$
E _ { s } ^ { t } = [ X ^ { t } , S ] , E _ { s } ^ { t } \in R ^ { n \times ( p + l ) }
$$

b)动态属性融合。不同于静态属性， $D \in R ^ { n \times ( w * t ) }$ 是指 $w$ 个不同的动态属性的集合。考虑到流量状态受动态因素的累积影响，没有选择时间 $t$ 对应的属性值，而是选择当形成 $E ^ { t }$ 时将窗口大小扩展到 $m { + } l$ ， $D _ { w } ^ { t - m , t } = [ D _ { w } ^ { t - m } , D _ { w } ^ { t - m - 1 } , . . . , D _ { w } ^ { t } ]$ ，最后，通过属性增强单元，形成包含静态和动态外部属性以及 $t$ 时刻的流量特征信息的增广矩阵为

$$
E ^ { t } = [ X ^ { t } , S , D _ { 1 } ^ { t - m , t } , D _ { 2 } ^ { t - m , t } , . . . , D _ { w } ^ { t - m , t } ]
$$

其中， $E ^ { t } \in R ^ { n \times ( p + l + w \ast ( m + 1 ) ) }$

# 2 交通流预测模型

# 2.1方法描述

本方法将交通流特征与属性增强单元相结合，利用图小波卷积层和自适应矩阵来提取空间路网特征信息，采用门控循环单元层提取其时间特性，并通过注意力机制做全局时空信息提取，以促进交通流预测。方法的整体框架如图1所示，本文将其命名为 A-STIGCN(Attribute-Augmented Spatiotemporal GraphConvolutional Network Integrating attention and graph wavelet)。

![](images/f99e02e5a04e6c2f434f840b051b648b502a6328bbc41bcbbde636c8c5eb8321.jpg)  
图1A-STIGCN 模型框架图  
Fig.1A-STIGCN model framework diagram

# 2.2 空间特征提取

本文基于图小波变换进行卷积操作，可以捕获信号的突变，与图傅里叶变换类似，图小波变换也是将图信号映射到频域中进行卷积操作，不同的是傅里叶变换只能将时域信号分解为频域信号的组合，而小波变换可以展示信号随时间变化过程中相位最大的频率的位置和时间[17]。图小波采用一个母小波函数将信号分解为不同的频率分量，在图网络中可以表示为一组小波基 $\psi _ { s } = [ \psi _ { s 1 } , \psi _ { s 2 } , . . , \psi _ { s n } ]$ ， $\psi _ { s i }$ 表示节点 $i$ 相关的小波基 $s$ 为尺度参数，控制小波的大小， $\lambda$ 表示 $\pmb { L }$ 的特征值。图小波基可以表示为

$$
\begin{array} { c } { { \psi _ { s } = U G _ { s } U ^ { T } } } \\ { { { } } } \\ { { G _ { s } = d i a g [ g ( s \lambda _ { 1 } ) , . . . , g ( s \lambda _ { n } ) ] } } \\ { { { } } } \\ { { g ( s \lambda _ { i } ) = e ^ { \lambda _ { i } s } } } \end{array}
$$

图小波可以将交通流数据 $X$ 映射到频域空间，得到在频域中的数据表示 $X = \psi _ { s } ^ { - 1 } X$ 。图小波卷积操作可以定义为

$$
F * _ { g } X = \psi _ { s } [ ( \psi _ { s } ^ { - 1 } F ( L ) \otimes ( \psi _ { s } ^ { - 1 } X ) ]
$$

相比于傅里叶变换而言，图小波基 $\psi _ { s }$ 和 $\psi _ { S } ^ { - 1 }$ 更加稀疏，因此计算更加快速有效。此外，图小波变换聚合局部节点信息来表征节点特征，从而提高了方法的可解释性。

然而交通网络中的空间关系是不确定的，道路节点除了与邻居节点密切相关以外，还和位于网络中心的重要道路节点相关，而这些节点可能相距较远，而通过基于距离计算的邻接矩阵无法体现出这些道路的相关性[18]，因此本文采用了一个自适应矩阵在全局范围内进行空间特征学习，其表达式为

$$
p , m = S W D ( A )
$$

$$
E _ { \mathrm { { l } } } = p m
$$

$$
A _ { a d p } = s o f t \operatorname* { m a x } ( \mathbf { R e } L U ( E _ { 1 } E _ { 2 } { } ^ { T } ) )
$$

其中， $\pmb { p }$ 和 $\textbf { \em m }$ 分别是 $\textbf {  { A } }$ 前 $\mathrm { ~  ~ c ~ }$ 个特征值组成的特征向量和对角矩阵， $E _ { 1 } , E _ { 2 } \in R ^ { N \times c }$ ，自适应矩阵以及图小波卷积可以分别提取局部和全局空间特征信息。由于空间依赖通常是非线性的，所以需要一个非线性激活函数，在本文中采用ReLU函数。通过一个对角权重矩阵 $A$ 可以得到的图卷积层迭代式为

$$
H _ { s } ^ { ( l ) } = \mathrm { R e } L U ( \psi _ { s } \Lambda \psi _ { s } ^ { - 1 } H _ { s } ^ { ( l - 1 ) } W _ { 1 } ) + \mathrm { A } _ { a d p } H _ { s } ^ { ( l - 1 ) } W _ { 2 }
$$

# 2.3 时间特征提取

门控循环单元GRU是为了改善循环神经网络RNN的长程依赖问题，是一种比长短时记忆网络LSTM更加简单的循环神经网络。GRU用门控机制控制输入、记忆等信息而在当前时间步作出预测，门控循环单元不会随时间而清除以前的信息，它会保留相关的信息并传递到下一个单元，因此它利用全部信息而避免了梯度消失问题。其网络结构如图2所示。

![](images/e5db3f5e9ca37b52bb8bd79be4e2f2aa0325d9f3b314f430454cf0a3da07d6c5.jpg)  
图2门控循环单元网络结构图

GRU 有两个门，即一个重置门(reset gate)和一个更新门(updategate)。重置门决定了如何将新的输入信息与前面的记忆相结合，更新门定义了前面记忆保存到当前时间步的量。表达式定义如下：

$$
z _ { t } = \sigma ( W ^ { ( z ) } x _ { t } + U ^ { ( z ) } h _ { t - 1 } )
$$

$$
\mathbf { r } _ { t } = \sigma ( W ^ { ( r ) } x _ { t } + U ^ { ( r ) } h _ { t - 1 } )
$$

$$
h _ { t } ^ { ' } = \operatorname { t a n h } ( W x _ { t } + r _ { t } \otimes U h _ { t - 1 } )
$$

$$
h _ { t } = z _ { t } \otimes h _ { t - 1 } + ( 1 - z _ { t } ) \otimes h _ { t } ^ { ' }
$$

其中， $X _ { t }$ 为第 $t$ 个时间步的输入向量， $W ^ { ( z ) }$ 为权重矩阵， $h _ { t - 1 }$ 是前一个时间步 $_ { t - 1 }$ 的信息， $\sigma$ 为 $S i g \mathrm { m o d }$ 激活函数， $z _ { t } \in [ 0 , 1 ]$ 为更新门。 $r _ { t } \in [ 0 , 1 ]$ 为重置门， $h _ { t } ^ { ' }$ 代表当前时刻的候选状态，$h _ { \scriptscriptstyle t }$ 代表当前时间步的最终记忆。

# 2.4融合注意力机制的时空特征提取

但是在实际交通网络中时间依赖关系往往是复杂的，而不只是顺序相关的。例如某时刻发生了交通事故，则该时间点对未来的时间点影响将是最大的且会持续很长一段时间，而非主要受前一个时刻的影响。本文引入注意力机制层来自动捕获不同输入特征，以概率分布的思想对重要的信息分布足够的权重[4,15]，以此来提升交通流的预测精度。其结构图如图3所示。

![](images/41dded55ec4d6393cc68c09ffdb00f2c21c2cb676d4447c25a52dc56da168af3.jpg)  
Fig. 2 GRU network structure diagram   
Fig.3Structural diagram of the fusion attention mechanism

通过结合静态和动态的外部属性来扩展原始特征矩阵的维数。其中， $X ^ { t }$ 是从原始流量特征矩阵 $\boldsymbol { \cal X }$ 中提取，$\{ D ^ { t - m } , D ^ { t - m - 1 } , . . . , D ^ { t } \}$ 是从时间 $t ^ { - } m$ 到 $t$ 的动态信息的集合， $s$ 是静态属性，对于不同的时间戳始终是相同的。而 $E ^ { t }$ 是将外部属性和原始交通流量特征融合后的增广矩阵。用增广矩阵作为时空模型的输入，随即获得 $n$ 个包含时空特征的隐藏状态 $( h ) ^ { [ 2 0 ] }$ ，利用图小波网络和自适应矩阵捕获道路网络的拓扑特征，获得空间依赖性，利用GRU捕获节点属性的动态变化，获得交通状态的局部时间趋势，然后将隐藏状态输入到注意力模型中，计算公式如下：

$$
e _ { t } = \operatorname { t a n h } ( w _ { e } h _ { \mathit { t } } + b _ { e } )
$$

$$
\alpha _ { t } = \frac { \exp ( e _ { t } ) } { \displaystyle \sum _ { i = 1 } ^ { H } \exp ( e _ { i } ) }
$$

$$
\mathcal { Q } _ { t } = \sum _ { i = 1 } ^ { H } \alpha _ { t } h _ { t }
$$

其中， $\boldsymbol { e } _ { t }$ 表示 $t$ 时刻由输出向量 $h _ { t }$ 所决定的注意力概率分布值； $\alpha _ { t }$ 为 $t$ 时刻的权重系数； $Q _ { t }$ 表示输出值； $w _ { e }$ 和 $b _ { e }$ 为权重和偏置。本文通过数据预处理、交通特征与外部属性的结合，构建A-STIGCN模型，然后完成模型的参数设置与误差评估，将提取出的全部特征使用全连接层的Dense层进行输出。系统模型流程图如图4所示。

# 3 实验应用研究

# 3.1实验数据

a)交通流数据。SZ出租车，该数据集包含2015年1月1日至1月31日收集的深圳出租车轨迹数据。共选择罗湖区156个主要路段，其连通性采用 $1 5 6 ^ { * } 1 5 6$ 邻接矩阵建模。计算选定路段的交通速度时间序列，形成一个特征矩阵，其中行按路段索引，列按时间戳索引。

b)天气数据。SZ天气，此辅助信息包含了2015年1月每15分钟记录一次的研究区域的天气状况。天气条件分为晴天、多云、雾、小雨和大雨五种类型。利用时变天气条件的信息，构造了大小为 $1 5 6 ^ { * } 2 , 9 7 6$ 的动态属性矩阵。

c)POI数据。SZPOI，此数据集提供了有关选定路段周围的POI的信息。POI类别可分为9类：餐饮服务、企业、购物服务、交通设施、教育服务、生活服务、医疗服务、住宿等。在计算出各路段的POI分布后，以比例最大的POI类型作为该路段的特征。因此，得到的静态属性矩阵的大小为 $1 5 6 ^ { * } 1$ 。

# 3.2模型评价与参数设置

3.2.1评估指标

![](images/fa13aea0dfe552861076377b8683b57039817ddd89045baeacb662bfec683639.jpg)  
图3融合注意力机制的结构图  
图4系统模型流程图  
Fig.4Flow chart of the system model

在实验过程中，选用平均绝对误差(mean absolute errors,MAE)，平均绝对百分比误差(mean absolute percentage errors,MAPE)和精度(Accuracy)三种度量指标来评估模型，具体定义分别如下：

$$
M A E ( y _ { i } , \hat { y } _ { i } ) = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \left| ( y _ { i } - \hat { y } _ { i } ) \right|
$$

$$
M A P E ( y _ { i } , \hat { y } _ { i } ) = \sum _ { i = 1 } ^ { n } ( \frac { y _ { i } - \hat { y } _ { i } } { y _ { i } } ) \cdot \frac { 1 0 0 } { n }
$$

$$
A c c u r a c y = 1 - { \frac { \left\| y - { \hat { y } } \right\| } { \left\| y \right\| F } }
$$

其中， $y _ { i }$ 为观测值， $\hat { y } _ { i }$ 为预测值， $n$ 为选取样本的数量， $\left\| \cdot \right\| F$ 代表Frobenius 范数。

# 3.2.2参数设置

基于谷歌TensorFlow 深度学习框架在PyCharm开发环境中完成交通流预测模型的训练环境的搭建，在进行建模前，为提升模型的收敛速度及预测准确度，数据的划分策略为：数据前 $80 \%$ 作为训练集，剩下的 $20 \%$ 数据作为测试集。模型的超参数主要包括学习率、epoch、隐藏单位、批处理大小，而将学习率和批量大小设置为0.001和64，并通过实验搜索其他参数。首先，测试了集合[50,100,150,200,300,350]中的训练能力，以分析模型性能的变化。图5为不同训练设置下的评价结果。随着训练值的增加，评价指标的变化变得稳定，转折点为200。然后，当epoch 固定为 200 时，从候选集[8,16,32,64,100,128]中选择隐藏单元的数量。如图6所示，当单位数达到100时，模型保持稳定。因此，epoch确定为200,而隐藏单位的数量为100个。

![](images/a01f68061eb402165ef3bdf35cc9e2f6778d4c1b7360c3e15e1a2cf64a3361a6.jpg)  
图5epoch 对于预测性能的影响

![](images/e355f4013a1ba551f956985c4d1038fcc07b74a0a62f06b164a0ff42223d9859.jpg)  
Fig.5The influence of the selection of epochs on the prediction performance   
图6单元数对于预测性能的影响  
图7扰动分析  
Fig.7Perturbation analysis

Fig.6The influence of the selection of units on the prediction performance

# 3.3 实验结果与分析

# 3.3.1传统模型的对比分析

为了验证A-STIGCN模型在交通流预测任务中的有效性，将其与基线模型进行比较，如表1所示。从实验结果中可以看出，组合预测模型预测精度具有大幅度提高，平均绝对误差MAE、平均绝对百分比误差MAPE均比其他3个基线模型的平均性能低，与SVR和GRU传统模型相比，MAE分别减少了约3.422和2.811。与只关注时空关系的GCN相比，MAPE降低了约 $1 . 7 7 7 \%$ ，其他指标的总体评价也有显著改善。比较结果验证了A-STIGCN组合模型的有效性。

# 3.3.2变体模型的对比分析

如表2所示,TGCN的预测效果相对较差，交通流数据由于受到多种外部因素的影响而呈现随机性变化，与未引入外部因素的TGCN模型相比，MAE降低了约0.173，MAPE降低了约$0 . 6 3 7 \%$ ，与没有加入注意力机制的ASTGCN模型相比，MAE降低了约0.131，精度提高了0.068，可以看出，当考虑外界因素对交通流量的影响时，A-STIGCN模型仍具有良好的预测效果。

Tab.1Comparison of traffic flow prediction error for different models   

<html><body><table><tr><td>预测模型</td><td>MAE</td><td>MAPE/%</td><td>Accuracy</td></tr><tr><td>SVR</td><td>7.423</td><td>4.763</td><td>0.371</td></tr><tr><td>GRU</td><td>6.812</td><td>4.701</td><td>0.392</td></tr><tr><td>GCN</td><td>5.701</td><td>4.300</td><td>0.486</td></tr><tr><td>A-STIGCN</td><td>4.001</td><td>2.523</td><td>0.743</td></tr></table></body></html>

表2变体模型的预测对比分析

表1不同模型的交通流预测误差对比  

<html><body><table><tr><td>评价指标</td><td>TGCN</td><td>ASTGCN</td><td>A-STIGCN</td></tr><tr><td>MAE</td><td>4.173</td><td>4.131</td><td>4.000</td></tr><tr><td>MAPE(%)</td><td>2.750</td><td>2.532</td><td>2.113</td></tr><tr><td>Accuracy</td><td>0.721</td><td>0.732</td><td>0.800</td></tr></table></body></html>

3.3.3不同时段特征的预测性能对比分析

本实验测试A-STIGCN模型在不同视野下 $( 1 5 \mathrm { m i n } , 3 0 \mathrm { m i n }$ $4 5 \mathrm { m i n }$ 和 $6 0 \mathrm { { m i n } } \dot { }$ 的预测性能，A-STIGCN模型和基线模型之间的性能比较如表3所示。在15分钟的预测范围内，A-STIGCN模型的MAE大约比TGCN和DCRNN模型低0.047和 $0 . 0 9 7$ 。在30分钟的预测范围内，A-STIGCN模型的预测误差MAPE约比TGCN和DCRNN低 $0 . 1 0 7 \%$ 和 $1 . 1 2 \%$ 。对于 $4 5 \mathrm { m i n }$ 的预测范围，A-STIGCN模型的精度分别比TGCN和DCRNN高0.015和0.024。当预测范围设置为 $6 0 \mathrm { { m i n } }$ 时，A-STIGCN 模型的MAPE分别比 TGCN和DCRNN低约$0 . 0 7 7 \%$ 和 $1 . 0 7 3 \%$ 。结果表明，本文模型在不同视野下能够保持良好的性能和长期预测能力。

Tab.2Preast analysis of the variant models   
表3不同时段特征的模型预测性能对比分析  
Tab.3Performance comparison between the A-STIGCN model and the baseline models for different prediction horizons   

<html><body><table><tr><td>Time</td><td>Metric</td><td>TGCN</td><td>DCRNN</td><td>A-STIGCN</td></tr><tr><td rowspan="4">15min</td><td>MAE</td><td>2.734</td><td>2.784</td><td>2.687</td></tr><tr><td>MAPE</td><td>3.473</td><td>4.449</td><td>3.319</td></tr><tr><td>Accuracy</td><td>0.715</td><td>0.716</td><td>0.720</td></tr><tr><td>MAE</td><td>2.743</td><td>2.790</td><td>2.703</td></tr><tr><td rowspan="3">30min</td><td>MAPE</td><td>3.530</td><td>4.543</td><td>3.423</td></tr><tr><td>Accuracy</td><td>0.713</td><td>0.712</td><td>0.719</td></tr><tr><td>MAE</td><td>2.778</td><td>2.793</td><td>2.691</td></tr><tr><td rowspan="3">45min</td><td>MAPE</td><td>3.573</td><td>3.569</td><td>3.513</td></tr><tr><td>Accuracy</td><td>0.702</td><td>0.693</td><td>0.717</td></tr><tr><td>MAE</td><td>2.798</td><td>2.803</td><td>2.692</td></tr><tr><td rowspan="2">60minn</td><td>MAPE</td><td>3.613</td><td>4.609</td><td>3.536</td></tr><tr><td>Accuracy</td><td>0.696</td><td>0.684</td><td>0.716</td></tr></table></body></html>

3.3.4扰动分析

在数据中加入高斯噪声和泊松噪声，以验证模型的鲁棒性。两种类型的噪声分别服从高斯分布$N \in ( 0 , \sigma ^ { 2 } ) ( \sigma \in 0 . 2 , 0 . 4 , 0 . 6 , 0 . 8 , 1 )$ 和泊松分布 $P ( \lambda ) ( \lambda \in 1 , 2 , 4 , 8 , 1 6 )$ ,实验结果如图7所示，通过在不同噪声设置下评价指标的变化可以忽略不计，验证了A-STIGCN模型的鲁棒性。

MAE MAPE MAccuracy m a 入 (a) Gaussian distribution (b) Poisson distribution

# 4 结束语

本文通过整合外部属性信息和交通特征，形成属性增强矩阵，增强模型对外部信息的感知，结合图小波网络与自适应矩阵，提取短时交通流的局部与全局空间特性，并利用门控循环单元提取时间特性，使用注意力机制对重要信息分布足够的权重，设置对比实验，测试A-STIGCN模型的预测性能，从而提高交通流预测的精度。但模型对于交通道路上的车型特征，时段特征考虑不足，下一步将预测粒度更加细化，考虑路网复杂性来改进模型，进行相关的交通流预测研究。

# 参考文献：

[1]刘静，关伟．交通流预测方法综述[J].公路交通科技,2004,(3):82- 85.(Liu Jing,Guan Wei.AReview of Traffic Flow Prediction Methods [J].Highway Traffic Technology,2004,(3): 82-85)   
[2] Zhang S,Lin K P. Short-term traffic flow forecasting based on datadriven model[J].Mathematics,2020,8(2):152-169.   
[3]Zhou T, Jiang D,Lin Z,et al.Hybrid dual kalman filtering model for short-term traffic flow forecasting [J].IET Intelligent Transport Systems, 2019,13 (6):1023-1032.   
[4]SUNB,SUN T, ZHANGYJ,et al. Urban traffic flow online prediction based on multi-component attention mechanism [J].IET Intelligent Transport Systems,2020,14 (10):1249-1258.   
[5]曹阳，茅一波，施佺等．日交通流预测的编码器-解码器深度学习模 型研究[J/OL].计算机工程与应用：1-11[2021-11-22].http://kns. cnki.net/kcms/detail/11.2127.TP.20210913.1903.020.html.(Cao Yang,MAO Yibo,Shi Quan,et al. Encoder-decoder Deep Learning Model Study for Daily Traffic Flow Prediction [J/OL].Computer Engineering and Application:1-11 [2021-11-22]. http://ns.cnki. net/kcms/detail/11.2127.TP.20210913.1903.020.html.)   
[6] 桂智明，李壮壮，郭黎敏等．基于 ACGRU 模型的短时交通流预测 [J]．计算机工程与应用，2020,56(21):260-265.(Gui Zhiming,Li Zhuangzhuang,Guo Limin,et al. Short-time trafic flow prediction based on the ACGRU model[J].Computer Engineering and Applications,2020, 56 (21):260-265)   
[7]Yu B,Yin H, Zhu Z. Spatio-temporal graph convolutional networks: a deep learning framework for traffic forecasting [C]//27th International Joint Conference on Artificial Intelligence,2018:3634-3640.   
[8]Li Y,Yu R,Shahabi C,et al.Diffusion convolutional recurren tneura lnetwork: Data-driven traffic forecasting [J].arXiv preprint arXiv:1707. 01926,2017.   
[9]Yang G,Wang Y,Yu H,et al. Short-term traffic state prediction based on the spatiotemporal features of critical road sections [J]. Sensors,2018, 18 (7): 2287.   
[10]姜山，丁治明，徐馨润等．面向路网交通流态势预测的图神经网络 模型[J].计算机科学与探索,2021,15(06):1084-1091.(Jiang Shan, Ding Zhiming,Xu Xinrun,et al.Graphaph Neural Network Model [J]. Computer Science and Exploration,2021,15 (06): 1084-1091)   
[11]戴俊明，曹阳，沈琴琴等．基于多时空图卷积网络的交通流预测[J]. 计算机应用研究,2022,39(03):780-784.DOI:10.19734/j.issn.1001- 3695.2021.O8.O361.(Dai Junming,Cao Yang,Shen Qinqin,et al. Trafficflowpredictionbasedonmulti-spatiotemporal graphconvolutional networks [J]. Computer Application Research,2022, 39 (03): 780-784.DOI: 10.19734/j.issn.1001-3695.2021.08.0361.)   
[12] Zhang L,Alharbe NR,Luo G,etal.A hybrid forecasting framework based on support vector regression with a modified genetic algorithm and a random forest for traffic flow prediction [J].Tsinghua Science and Technology,2018,23 (4): 479-492.   
[13]倪庆剑，彭文强，张志政等．基于信息增强传输的时空图神经网络 交通流预测[J].计算机研究与发展，2022,59(02):282-293.(Ni Qingjian,Peng Wenqiang,Zhang Zhizheng,et al. Spatiotemporal graph neural network traffic flow prediction based on information-enhanced transmission [J].Computer Research and Development,2022,59 (02): 282-293.)   
[14]张耀方，陈坚．基于GBDT 算法的高速公路分车型交通流短时预测 模型[J].公路,2022,67 (01):221-227.(Zhang Yaofang,Chen Jian. Short-time prediction model of highway subvehicle trafic flow based on GBDT algorithm [J].Highway,2022,67(01): 221-227.)   
[15] LI M, WANGY W,WANG Z W,et al. A deep learning method based on an attention mechanism for wireless network traffic prediction [J].Ad Hoc Networks,2020,107:102258.   
[16] Tang J. Sun Y, Sun."Dynamic Spatial-Temporal Graph Attention Graph Convolutional Network for Short-Term Traffic Flow Forecasting, "2020 IEEE International Symposium on Circuits and Systems (ISCAS),2020, pp.1-5,doi: 10.1109/ISCAS45731.2020.9181234.   
[17] Zhu Q.Wang C. Tao H,et al. "AST-GCN:Atribute-Augmented Spatiotemporal Graph Convolutional Network for Traffic Forecasting, "in IEEE Access,vol.9,pp.35973-35983,2021,doi: 10.1109/ACCESS. 2021. 3062114.   
[18] Wu Z,Pan S,Long G,et al.,Graph WaveNet for Deep Spatial-Temporal Graph Modeling [C]// Proceedings of the 28th International Joint Conference on Artificial Intelligence,Macao,China,Augl0-16,2019: 1907-1913.   
[19] Zhao L,et al."T-GCN:A Temporal Graph Convolutional Network for Traffic Prediction,"in IEEE Transactions on Intelligent Transportation Systems,vol.21,no.9,pp.3848-3858,Sept.2020,doi:10.1109/TITS. 2019.2935152.