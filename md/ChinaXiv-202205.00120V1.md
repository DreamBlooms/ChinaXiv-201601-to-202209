# 基于重叠域采样混合特征的点云配准算法

胡江豪，王丰

(广东工业大学，信息工程学院，广州 510006)

摘要：针对部分重叠的两片点云配准效率低、误差大等问题。提出了一种基于重叠域采样混合特征的点云配准算法。首先，通过编码和特征交互的方式预测每个点的重叠分数，获得更丰富的点云特征。其次，提取重叠点的局部几何特征，基于重叠分数和点特征的显著性保留重叠关键点。最后，利用重叠关键点的几何信息和空间信息构建混合特征矩阵，计算矩阵的匹配相似度，采取加权奇异值分解运算得到配准结果。实验结果表明，该方法具有较强的泛化能力，能在保证配准效率的同时，显著提升点云配准精度。

关键词：机器视觉；点云配准；重叠区域；混合特征 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.03.0111

Point cloud registration algorithm based on mixed-features sampling for overlapping domain

Hu Jianghao, Wang Feng† (School ofinformation engineering,Guangdong University of Technology,Guangzhou 51ooo6,China)

Abstract: Aimingat theproblemsofloweficiencyandlarge errorintheregistrationoftwopartiallyoverlappedpointclouds, this paper proposed a pointcloudregistration algorithmbased onthe mixed-features sampling foroverlapping domain.First, itused codingand feature interaction predicted theoverlap scoreofeach pointtoobtainricher pointcloud features.Second, it extracted the local geometric featuresofoverlapping points and retained the overlapping key points basedon overlapping scores andthe significanceofpoint features.Finally,itusedthe geometricinformationandspatial informationofoverlapping keypoints toconstruct a hybrid feature matrix,calculatedthe matching similarityofthe matrix,andobtainedregistration results by using weighted singular value decomposition.Experimental results show that the proposed method has strong generalizationability and can significantly improve the registration accuracyof point cloud while ensuring registration efficiency.

Key words:machine vision; point cloud registration; overlapping areas; hybrid feature

# 0 引言

点云配准是计算机视觉中的一项重要任务，旨在寻找一种刚体变换，使一个三维源点云与另一个三维目标点云对齐[1]。它在姿态估计[2]、三维重建[3]、目标定位[4]等领域有着广泛的应用，得到了国内外学者的广泛关注。配准问题可以描述为：给定源点云 $X = \{ x _ { i } \in R ^ { 3 } | i = 1 \cdots N \}$ 和目标点云 $Y = \left\{ y _ { j } \in R ^ { 3 } \left| j = 1 \cdots M \right. \right\}$ ，点云配准的目标是找到刚性变换 $\{ R , t \}$ 使得两个点云 $\boldsymbol { \cal X }$ 和Y能够对齐，其中 $R \in S O ( 3 )$ 是旋转矩阵， $t \in R ^ { 3 }$ 为平移向量，$X \in R ^ { N \times 3 }$ 为源点云， $Y \in R ^ { M \times 3 }$ 为目标点云。

在实际应用中，由于连续帧之间的摄像机运动，大多数情况下会产生部分重叠的三维点云[5]。部分点云配准是现实世界中常见的一种配准方法。由于部分重叠的点云数据规模不一致、特征密度低，部分重叠的点云面临着配准效率低、误差大等挑战。传统的配准方法中最常用的是迭代最近点(iterativeclosestpoint，ICP)算法，但该方法对点云初始位置较为敏感，容易陷入局部最优。快速全局配准(fastglobalregistration，FGR)[7算法通过快速点特征直方图[8]和交替优化技术来加速全局配准，但其对于噪声较为敏感。全局优化迭代最近点算法(Globally optimalICP，Go-ICP)[9]通过分支定界的方法解决了局部极小值问题，但其对初始位置仍然敏感。随着点云数据规模的剧增，传统的配准方法在效率和精度上已不能满足实际需求。

近年来，基于深度学习的点云配准算法和方案设计成为了三维点云配准的研究热点。与传统配准算法相比，深度学习的方法具有精度高、鲁棒性强等特点。Aoki等人[10]提出了一种鲁棒高效的点云配准算法 PointNetLK，将点网[1] (deeplearning on point sets，PointNet)深度学习网络和改进的Lucas-Kanade[12]算法相结合，在中等尺度变换和噪声条件下提高了配准精度。Wang等[13]人提出了深度最近点(deepclosest point，DCP)网络，运用动态图卷积神经网络[14]提取点云特征，并使用注意力机制计算点的相关性。Wang 等人[15]提出部分到部分配准的自监督学习(self-supervisedlearning forpartial-to-partialregistration，PRNet)深度学习网络，使用Gumbel-Softmax[16和一个直接梯度估计器来采样关键点的对应关系。Li等人[1]提出迭代距离感知相似矩阵卷积网络(iterativedistance-aware similarity matrix convolution，IDAM)，融合了点云的局部几何特征和距离特征，同时运用互监督的混合消元法提高了配准精度。Yew等人[17结合混合特征与退火算法，降低初始位置对最终配准结果的影响，增强了网络的泛化能力，但运算速度较慢。

然而，上述的方法都没有明确处理非重叠点。相比于重叠点，非重叠点可以提取的特征有限，而配准的准确性在很大程度上依赖于特征提取的质量。非重叠点对全卷积点特征描述符的有效感受野影响较小[18,19]。因此，改变特征的提取方法对部分重叠点云配准性能的提升是有限的。对于部分重叠的点云，若能学习在何处采样特征点，则可以有效提升部分点云配准的性能。熊丰伟等人[20提出了一种基于法向量投影协方差分析的关键点提取方法。Huang等人[21]对以往关键点提取方法进行了补充，并将其延伸至低重叠场景[22]。张元等人[23]将聚类区域分块和凸优化问题相结合，提升了重叠程度较低的点云的配准性能。李鑫等人[24]通过降采样和阈值分离的方式保留贡献度更大的点对。Xu等人[25通过学习重叠掩膜来拒绝非重叠区域，将部分重叠点云配准转换为相同形状的点云配准，并取得了优异的配准性能。但由于噪声点和非重叠点的存在，采样重叠点可能会使目标点云中正确的对应点被移除，导致配准性能的下降。

为此，本文提出了一种基于重叠域采样混合特征的点云配准算法。在有效提取重叠点的同时降低目标点云中正确对应点被移除的概率。首先，通过编码和特征交互的方式提取每个点云内部的交互特征，增强网络对局部几何结构的描述能力，提取具有丰富特征的重叠关键点，提高配准效率。其次，结合点云的局部几何特征和距离特征，利用了不同点对特征的相互作用，减少初始位置对配准性能的影响，提升了配准精度。最后，为了平衡性能和效率，提出了有效性分数计算网络。降低采样关键点时错误的移除目标点云中的对应点对配准性能的影响，提高点云配准尤其是部分重叠点云配准的精度和鲁棒性。

# 1 点云配准框架及算法设计

本文提出了一种基于深度学习的点云配准算法，算法结构如图1所示，主要由4个部分组成(1)重叠分数预测、(2)显著特征采样、(3)混合特征提取、(4)相似度和有效性分数计算。首先，使用PointNet网络对点云进行编码，编码后送入特征交互模块，用PointNet网络解码输出点云的重叠分数，根据重叠分数采样 $K$ 个重叠分数高的重叠点。其次，提取重叠点的局部几何特征，保留 $L$ 个显著特征点，并计算显著特征点的距离特征，将局部几何特征和距离特征结合构成混合特征矩阵，计算相似度和有效性分数，根据有效性分数为每个点分配不同的权值，采取加权奇异值分解求解得到刚性变换。

![](images/32e8f73c79fb0a04bb947ee37935e593372bd2d076319aaf765373387452456f.jpg)  
Fig.1Point cloud registration algorithm structure based on overlapping domain sampling mixed-feature

# 1.1重叠分数预测

值得注意的是，非重叠部分对全卷积特征点描述符的影响较小，而重叠部分点云包含更多的数据量，具有更丰富的特征[18,19]。因此，在重叠区域中的点能够有效提升配准性能。本文将重叠问题看成二分类问题[5]，提出了一种特征交互模块，如图2所示，计算源点云和目标点云中点的重叠分数，并采样重叠度较高的 $K$ 个数据点。

![](images/19e471d8871165e53481ace93f9360ef9af3c2ee0f957a77070734668214ca01.jpg)  
图1基于重叠域采样混合特征的点云配准算法结构  
Fig.2Feature interaction module

使用修改后的PointNet网络提取源点云的全局特征 $F _ { X }$ 和目标点云的全局特征 $F _ { Y }$ 。对全局特征 $F _ { X }$ 和 $F _ { _ Y }$ 进行一次最大池化操作，由此得到池化特征 $F _ { X } ^ { \mathrm { m } }$ 和 $F _ { Y } ^ { \mathrm { m } }$ 。接下来，堆叠若干个特征 $F _ { X } ^ { \mathrm { m } }$ 、 $F _ { Y } ^ { \mathrm { m } }$ ，使其特征维度和 $F _ { X }$ 、 $F _ { Y }$ 保持一致，如图2 所示。重叠分数预测的问题可视为二分类问题。因此，将全局特征、扩展后的池化特征及其差值相串联，并用修改后的PointNet网络进行解码操作，得到源点云的重叠分数 $O _ { x }$ 和目标点云的重叠分数 $O _ { Y }$ ，即：

$$
O _ { X } = p _ { d } \left( c a t ( F _ { X } , e ( F _ { X } ^ { m } ) , e ( F _ { Y } ^ { m } ) , e ( F _ { X } ^ { m } - F _ { Y } ^ { m } ) ) ) \right)
$$

$$
O _ { Y } = p _ { d } \left( c a t ( F _ { Y } , e ( F _ { Y } ^ { m } ) , e ( F _ { X } ^ { m } ) , e ( F _ { Y } ^ { m } - F _ { X } ^ { m } ) ) \right)
$$

其中 $p _ { d }$ 代表解码PointNet网络， $e ( \cdot )$ 代表堆叠扩展操作，cat

代表连接操作。获取重叠分数后，根据重叠分数采样K个点，得到采样后的源点云 $X ^ { \prime } = \{ x _ { i } ^ { \prime } \in R ^ { 3 } | i = 1 \cdots K \}$ 和目标点云$Y ^ { \prime } = \left\{ y _ { j } ^ { \prime } \in R ^ { 3 } \left| j = 1 \cdots K \right. \right\}$ 。

# 1.2 显著特征采样

使用所有的点特征进行对应关系搜索需要花费大量的内存和时间。不显著的特征会导致配准性能的下降，而显著的特征包含更丰富的信息，具有更强的判别性。因此，本文提出显著特征采样模块，如图3所示。首先，用图神经网络(graphneural networks，GNN)[26]提取源点云中点 $x _ { i }$ 的局部几何特征$f _ { x } \left( i \right)$ 和目标点云中点 $y _ { j }$ 的局部几何特征 $f _ { y } \left( j \right)$ 。其次，对特征向量应用多层感知机，得到源点云和目标点云特征的显著分数 $s ( i )$ 和 $s ( j )$ 。最后，保留显著分数最高的 $L$ 个数据点，去除显著分数低的点。采样后的源点云记为 $X ^ { \prime \prime } { = } \left\{ x _ { i } ^ { \prime \prime } \in R ^ { 3 } \left| i { = } 1 { \cdots } L \right. \right\}$ ，目标点云记为 $Y ^ { \prime \prime } = \left\{ y _ { j } ^ { ~ \prime \prime } \in R ^ { 3 } \left| j = 1 \cdots L \right. \right\}$ 。

![](images/4512b879fd76e7b8627476ea36a65bbd6dcfdf1d2685000dad54713a801df771.jpg)  
图2特征交互模块图  
图3显著特征采样模块图  
Fig.3Salient feature sampling module

# 1.3混合特征提取

现有的基于学习的方法大多仅采用局部几何特征进行对应关系匹配。由于不同点对之间的匹配方式是相同的，故仅采用局部几何特征识别两点之间相似度的能力有限。ICP使用距离特征进行对应关系匹配，该方法对点云的初始位置较敏感。结合局部特征和距离特征，充分利用点云的几何信息和空间信息，能获得更高的配准精度，减少初始位置对配准性能的影响。本文计算采样后点云中点的距离特征，将距离特征和1.2节获取的局部几何特征连接，得到采样后点云的混合特征，即：

$$
H ^ { \left( n \right) } \left( i , j \right) = c a t ( f _ { X } \left( i \right) , f _ { Y } \left( j \right) , \left. x _ { i } ^ { \prime \prime } - y _ { j } ^ { \prime \prime } \right. , \frac { x _ { i } ^ { \prime \prime } - y _ { j } ^ { \prime \prime } } { \left. x _ { i } ^ { \prime \prime } - y _ { j } ^ { \prime \prime } \right. } )
$$

其中cat表示连接操作， $n$ 表示更新距离特征后混合特征内部迭代的次数。

# 2 相似度与有效性分数计算

# 2.1相似度计算

1.3节得到了点云的混合特征矩阵。首先，对混合特征$H ^ { ( n ) } \left( i , j \right)$ 应用一系列二维卷积。然后对每一行都应用 Softmax函数得到相似度矩阵，记为 $S ^ { ( n ) } \left( i , j \right)$ 。 $S ^ { ( n ) } \left( i , j \right)$ 的每一行为归一化的概率分布，即 $x _ { i }$ 和 $y _ { j }$ 对应的概率。对相似度矩阵的每一行取最大值，得到一组点 $\left\{ { \left( x _ { i } ^ { \prime \prime } , x _ { i } ^ { \ast } \right) } | \forall x _ { i } ^ { \prime \prime } \in X ^ { \prime \prime } \right\}$ ，其中 $\boldsymbol { x _ { i } } ^ { * }$ 为目标点云中和 ${ x _ { i } } ^ { \prime \prime }$ 对应概率最大的点。

# 2.2有效性分数计算

采样源点云和目标点云中的特征显著数据点能够显著提高配准效率，但同时也可能造成源点云中某些点在目标点云中的正确对应点被消除。因此，本文提出了有效性分数计算网络，计算匹配结果的可信度，如图4所示。

![](images/08e8ac70caedcb1c5013e62e7805e6ac8ab4a07315b16a071db8f1d403d68e3e.jpg)  
图4有效性分数计算流程图Fig.4Validity score calculation

首先，计算源点云中每一个点的有效性分数，对混合特征矩阵运用一维卷积操作，对卷积后的结果取最大值并通过全连接层，计算有效性分数，如下：

$$
\nu ( i ) { = } s i g m o i d ( M L P ( \operatorname* { m a x } H ^ { ( n ) } ( i , j ) ) )
$$

有效性分数可以看做源点云和目标点云中的点匹配正确的概率。根据有效性分数，计算每一个点对应的权值，如下：

$$
m _ { i } = \frac { \nu ( i ) ~ \nu ( i ) \geq m e d i a n ( \nu ) } { \sum _ { i } \nu ( i ) ~ \nu ( i ) \geq m e d i a n ( \nu ) }
$$

其中·为判断指标函数，若函数中的条件满足则赋值为1，否则为0。得到每个点的权值后，采用加权奇异值分解(Singularvalue decomposition，SVD)运算，计算旋转矩阵 $R ^ { ( \mathrm { n } ) }$ 和平移向量 $t ^ { ( n ) }$ ，如下：

$$
R ^ { ( n ) } , t ^ { ( n ) } = \underset { R , t } { \arg \operatorname* { m i n } } \sum _ { i } m _ { i } \left\| R x _ { i } ^ { n } + t - x _ { i } ^ { * } \right\|
$$

# 2.3损失函数

网络的损失函数由四个部分组成，采用多监督的形式。重叠分数预测损失函数为 $L _ { O L }$ 。重叠分数预测只有重叠和非重叠两种情况，因此把它看做一项二分类任务，用交叉熵损失函数来监督它。重叠分数预测损失函数定义如下：

$$
L _ { o L } = \frac { 1 } { 2 N } { \sum _ { i } } { \sum _ { j } } ( \bar { O } _ { X } ) _ { i j } \cdot \log ( O _ { X } ) _ { i j } + \frac { 1 } { 2 M } { \sum _ { i } } { \sum _ { j } } ( \bar { O } _ { Y } ) _ { i j } \cdot \log ( O _ { Y } ) _ { i j }
$$

其中 $\bar { O } _ { x }$ 为源点云重叠分数的真实值， $\bar { O } _ { \scriptscriptstyle Y }$ 为目标点云重叠分数的真实值。关键点采样损失函数定义如下：

$$
L _ { k } = \frac { 1 } { L } \sum _ { i = 1 } ^ { L } \Biggl ( s ( i ) - \sum _ { j = 1 } ^ { L } H ^ { ( n ) } \left( i , j \right) \cdot \log \left( H ^ { ( n ) } \left( i , j \right) \right) \Biggr ) ^ { 2 }
$$

其中 $s ( i )$ 为源点云中第i个点 $x _ { i }$ 的显著分数。在早期配准时局部几何特征比距离特征更为重要。因此，仅在第一次迭代中使用关键点采样损失函数。

定义混合特征匹配监督的损失函数，如下所示。

$$
{ \cal L } _ { h } = \frac { 1 } { L } \sum _ { i = 1 } ^ { L } - \log \left( H ^ { ( n ) } \left( i , j ^ { * } \right) \cdot \overline { { { g } } } \right)
$$

其中 $j ^ { * }$ 为 $\boldsymbol { Y } ^ { \prime \prime }$ 中最接近 $x _ { i }$ 的真实值。 $\bar { \bf g }$ 为判断两点距离是否符合对应关系的指标函数：

$$
\overline { { g } } = \left\| \left\| R ^ { * } x _ { i } ^ { \prime \prime } + t ^ { * } - y _ { j } ^ { \prime \prime } \right\| \leq r ^ { 2 } \right\|
$$

可信度监督损失函数定义如下：

$$
L _ { c } = \frac { 1 } { L } \sum _ { i = 1 } ^ { L } - g ^ { * } \cdot \log \left( \nu ( i ) \right) - \left( 1 - g ^ { * } \right) \cdot \log \left( 1 - \nu ( i ) \right)
$$

其中 $g ^ { * }$ 为真实值变换情况下判断两点距离是否符合对应关系的指标函数：

$$
g ^ { * } = \biggl [ \biggl | \biggl | R ^ { * } x _ { i } ^ { \prime \prime } + t ^ { * } - y _ { \underset { j } { \operatorname { a r g m a x } } H ( i , j ) } ^ { \prime \prime } \biggr | \biggr | \leq r ^ { 2 } \biggr ] \biggr ]
$$

总的监督损失函数采用多监督形式，定义为四种损失函数的加权和，即：

$$
L = \alpha L _ { O L } + \beta L _ { k } + L _ { h } + L _ { c }
$$

其中 $\alpha$ 为可调节的超参数， $\beta$ 在第一次迭代时为1，其余时刻为0。

# 3 实验及结果分析

# 3.1 实验环境及设计

本文的实验使用Python 编程语言，配置环境为PyTorch深度学习框架。实验采用的计算机硬件环境为 Intel(R)Core(TM)i9-12900KF3.19GHZCPU处理器和RTX3080 GPU。

本文在合成点云数据集 ModelNet40 和斯坦福大学公布的真实点云数据集上评估所提出的算法，所选数据集被广泛应用于点云配准。ModeINet40数据集包含12311个CAD模型，共有40种不同的类别。数据集划分为训练集和测试集，训练集共有9843个物体，测试集共有2468个物体。对于一个物体，随机采样1024个点生成物体点云。对于每个点云，随机旋转 $[ 0 ^ { \circ } , 4 5 ^ { \circ } ]$ 并在每个坐标轴上平移[-0.5,0.5]。将初始点云视为源点云，变换过后的点云视为目标点云。为了生成部分重叠的点云，本文在与两个点云相距较远的地方随机固定一个点，每个点云保留离该点最近的768个点。

# 3.2实验参数设置

在算法实施中，采样重叠分数靠前的717个点，混合特征迭代次数为3，保留128个显著特征点，重叠分数预测损失函数超参数 $\alpha$ 设置为0.6。使用Adam优化器训练模型，训练次数为40个回合，初始学习率为0.0001，权重衰减设置为0.001，每30个回合学习率乘以0.1。

# 3.3实验评估

将本文的方法和传统的算法(例如迭代最近点ICP方法[6]，快速全局配准 FGR方法[7]，Go-ICP方法[9])以及基于深度学习的方法（例如PointNetLK[10]，DCP[13]，PRNet[15]和IDAM[1)进行比较。所有的基于深度学习的方法都是在同一个训练集上训练的，使用旋转矩阵和平移向量的均方根误差(RMSE)和平均绝对误差(MAE)作为评价指标。对于旋转矩阵：旋转均方根误差(RMSE(r))和旋转平均绝对误差(MAE(r))的单位为度。对于位移向量，用平移均方根误差(RMSE(t)）和平移平均绝对误差(MAE(t))表示。

# 3.4不可见形状的点云配准

对于不可见形状实验，在ModeINet40数据集上训练和测试本文的算法。ModelNet40 数据集包含9843个训练对象以及2468个测试对象，共计40种类别。

图5为本文方法和IDAM算法在测试集上的配准性能对比，当迭代次数为11时，IDAM算法性能达到最优，RMSE(r)为1.52,迭代次数为13时，本文方法性能达到最优,RMSE(r)为0.87。最终结果如表1所示。

![](images/0acdcc4f25cd3fa1db34648b6e11498cc611e57ca4879353e0f0a4d8533f3c2e.jpg)  
图5不可见形状时配准性能对比

Tab.1Registration results on modelnet4O unseen shapes point cloud   

<html><body><table><tr><td>配准算法</td><td>RMSE(r)</td><td>MAE(r)</td><td>RMSE(t)</td><td>MAE(t)</td></tr><tr><td>ICP</td><td>32.10</td><td>27.94</td><td>0.296</td><td>0.223</td></tr><tr><td>Go-ICP</td><td>13.54</td><td>3.62</td><td>0.031</td><td>0.009</td></tr><tr><td>FGR</td><td>11.24</td><td>2.83</td><td>0.030</td><td>0.008</td></tr><tr><td>PointNetLK</td><td>17.64</td><td>7.86</td><td>0.054</td><td>0.032</td></tr><tr><td>DCP</td><td>6.70</td><td>4.19</td><td>0.046</td><td>0.028</td></tr><tr><td>PRNet</td><td>3.77</td><td>1.97</td><td>0.021</td><td>0.013</td></tr><tr><td>IDAM</td><td>1.52</td><td>0.45</td><td>0.011</td><td>0.002</td></tr><tr><td>本文方法</td><td>0.87</td><td>0.29</td><td>0.004</td><td>0.001</td></tr></table></body></html>

由于缺乏良好的初始位置，迭代最近点ICP算法的配准性能较差，Go-ICP算法通过分支定界的方法解决了局部极小值问题，但其对初始位置仍然敏感。快速全局配准FGR算法利用几何形状特征进行配准，得到了更精确的配准结果，但和基于深度学习的方法相比，仍具有较高的误差。

基于深度学习的DCP、PRNet等算法均采用几何特征进行配准，而IDAM使用混合特征进行配准，比其他基于深度学习的方法获得了更好的性能。但其未对非重叠点进行处理，提取的特征中包含不丰富的特征信息。本文的算法结合几何特征和距离特征，同时考虑点云的重叠区域，采样比非重叠点具有更丰富特征的重叠关键点，去除非重叠点，消除冗余信息。将部分重叠点云配准转换为相同形状的点云配准。在配准时对包含丰富特征信息的重叠点给予更高的权重。相比IDAM算法以及其他的深度学习方法，本文的方法对点云的局部几何结构具有更强的描述能力。

实验结果表明，本文的方法优于所对比的传统的方法以及基于深度学习的方法，在四项评价指标上均得了更精确的配准结果，RMSE(r)和RMSE(t)分别为0.87和0.004，显著提升了点云配准的精度。

图6为本文方法的可视化配准结果，其中绿色点云为源点云，对源点云随机旋转 $[ 0 ^ { \circ }$ ， $4 5 ^ { \circ } ]$ 并在每个坐标轴上平移[-0.5,0.5]得到红色目标点云，如图6(a)所示。本文方法的配准结果如图6(b)所示，可以清楚的看出，本文提出的方法对不可见形状的点云能够精确的配准。

# 3.5不可见种类的点云配准

对于不可见种类的点云配准泛化实验，使用前20个类别进行训练，用剩下的20个类别进行测试。

图7为本文方法和IDAM算法在测试集上的配准性能对比，当迭代次数为24时，IDAM算法性能达到最优，RMSE(r)为1.59,迭代次数为26时，本文方法性能达到最优，RMSE(r)

为0.95。最终结果如表2所示，ICP、Go-ICP和FGR等传统的算法不需要使用训练集来学习参数。因此，传统的算法所受到的影响较小，而基于深度学习的方法由于训练模型和测试模型属于不同类别，配准性能有所下降。但本文的算法性能在各项指标上均优于其他的对比方法，对不可见类别的点云数据具有良好的泛化能力。

![](images/f1aaf62e1d36c38af6c5a01975fec2726c3913aadd9ef8159cabd2d04236040d.jpg)  
图6不可见形状实验配准结果

![](images/4e03c16075e356bedb1505026356a684b8785559db8ace8258539b52af2aa520.jpg)  
Fig.5Comparison of registration performance in unsee shape   
图7不可见种类时配准性能对比  
Fig.7Comparison of registration performance in unsee categorie:

表1ModelNet40上不可见形状点云配准的结果  
表2ModelNet40上不可见种类点云的配准结果  
[ab.2Registration results on modelnet40 unseen categories point clou   

<html><body><table><tr><td>配准算法</td><td>RMSE(r)</td><td>MAE(r)</td><td>RMSE(t)</td><td>MAE(t)</td></tr><tr><td>ICP</td><td>31.46</td><td>27.25</td><td>0.301</td><td>0.226</td></tr><tr><td>Go-ICP</td><td>13.10</td><td>3.01</td><td>0.028</td><td>0.008</td></tr><tr><td>FGR</td><td>9.93</td><td>1.95</td><td>0.038</td><td>0.007</td></tr><tr><td>PointNetLK</td><td>22.92</td><td>9.54</td><td>0.057</td><td>0.034</td></tr><tr><td>DCP</td><td>8.17</td><td>5.63</td><td>0.064</td><td>0.043</td></tr><tr><td>PRNet</td><td>4.99</td><td>2.33</td><td>0.021</td><td>0.015</td></tr><tr><td>IDAM</td><td>1.59</td><td>0.55</td><td>0.012</td><td>0.003</td></tr><tr><td>本文方法</td><td>0.95</td><td>0.34</td><td>0.005</td><td>0.002</td></tr></table></body></html>

图8为本文方法的可视化配准结果，其中绿色点云为源点云，对源点云随机旋转 $[ 0 ^ { \circ } , ~ 4 5 ^ { \circ } ]$ 并在每个坐标轴上平移[-0.5.0.5]得到红色目标点云，如图8(a)所示。本文方法的配准结果如图8(b)所示，可以清楚的看出，本文的方法对于不可见种类的点云能够精确的配准。

![](images/6f2ea172670087f8b106c46b3c2a633a1227258fafdb100338433ce616db4e0a.jpg)  
Fig.6Experimental registration results of unsee shape   
图8不可见种类实验配准结果  
Fig.8Experimental registration results of unsee categories

# 3.6含高斯噪声的不可见形状点云配准

由于连续帧之间的摄像机运动，真实场景中的扫描模型往往带有噪声。本文对所有的形状都加入标准差为0.01的随机高斯噪声，以模拟真实场景。将噪声裁剪到[-0.05,0.05]，其

他设置和3.4节的实验一致。

实验结果如表3所示，由于高斯噪声对形状特征的影响较大，FGR算法的配准性能受到了较大的影响。而ICP、Go-ICP算法对噪声具有一定的鲁棒性。由于训练过程中噪声的增强提高了局部特征描述符的鲁棒性，因此DCP、PRNet、IDAM以及本文的方法性能比无噪声时下降许多。本文的方法使用特征交互的方式过滤噪声点和非重叠点。在配准时计算有效性分数，对于不匹配的噪声点给予较低的权重，提高了算法面对噪声时的鲁棒性。本文方法的配准性能在RMSE(r)、MAE(r)和MAE(t)等三项指标上优于对比方法，在RMSE(t)上略次于PRNet，具有对抗噪声的良好泛化能力。

表3ModelNet40上不可见形状添加高斯噪声的结果

Tab.3Results on modelnet40 unseen shapes with Gaussian noise   

<html><body><table><tr><td>配准算法</td><td>RMSE(r)</td><td>MAE(r)</td><td>RMSE(t)</td><td>MAE(t)</td></tr><tr><td>ICP</td><td>31.74</td><td>27.56</td><td>0.301</td><td>0.227</td></tr><tr><td>Go-ICP</td><td>12.15</td><td>2.64</td><td>0.024</td><td>0.032</td></tr><tr><td>FGR</td><td>27.67</td><td>13.79</td><td>0.070</td><td>0.039</td></tr><tr><td>PointNetLK</td><td>20.91</td><td>9.26</td><td>0.068</td><td>0.049</td></tr><tr><td>DCP</td><td>8.34</td><td>6.07</td><td>0.066</td><td>0.046</td></tr><tr><td>PRNet</td><td>4.32</td><td>2.05</td><td>0.017</td><td>0.012</td></tr><tr><td>IDAM</td><td>3.60</td><td>1.79</td><td>0.022</td><td>0.011</td></tr><tr><td>本文方法</td><td>3.42</td><td>1.70</td><td>0.019</td><td>0.010</td></tr></table></body></html>

# 3.7算法时间复杂度

本文在 ModelNet40 测试集上对算法的运算性能进行评估，对比不同的算法处理一个点云数据的平均运行时间。对于点云数据，分别采样512、1024和2048个点，单位为秒，结果如表4所示。从结果可以得知，基于深度学习的方法通常比传统的方法更快。基于特征提取的深度学习算法无法避免地会提取非重叠点、不显著特征点的几何特征，导致配准效率不高。本文方法通过双层采样的方式对非重叠点、不显著的特征点进行过滤，极大减少了算法的计算量，提升了算法的运行效率。表4表明本文的方法的效率仅次于DCP 算法，是FGR算法的4\~5倍，是PRNet、PointNetLK算法的2\~3倍，显著优于ICP和IDAM等算法。

表4不同配准算法的运行时间  
Tab.4Running time of different registration algorithms/s   

<html><body><table><tr><td rowspan="2">配准算法</td><td colspan="3">采样点数</td></tr><tr><td>512</td><td>1024</td><td>2048</td></tr><tr><td>ICP</td><td>0.018</td><td>0.035</td><td>0.067</td></tr><tr><td>FGR</td><td>0.049</td><td>0.065</td><td>0.082</td></tr><tr><td>PointNetLK</td><td>0.028</td><td>0.038</td><td>0.069</td></tr><tr><td>DCP</td><td>0.006</td><td>0.008</td><td>0.013</td></tr><tr><td>PRNet</td><td>0.028</td><td>0.032</td><td>0.053</td></tr><tr><td>IDAM</td><td>0.015</td><td>0.021</td><td>0.037</td></tr><tr><td>本文方法</td><td>0.011</td><td>0.012</td><td>0.014</td></tr></table></body></html>

# 3.8斯坦福数据集上的点云配准实验

本文在斯坦福大学公布的 Stanford3D 扫描点云数据集上进行实验，以进一步验证本文算法的泛化能力。与ModelNet40 数据集相比，Stanford数据集中的点云分布不均匀，配准更具挑战性。本文选取数据集中的bunny、hand模型，将点云降采样至2048个点。对于每个点云，随机旋转$[ 0 ^ { \circ } , 4 5 ^ { \circ } ]$ 并在每个坐标轴上平移[-0.05,0.05]得到目标点云。采用和ModeINet40数据集相似的处理方式生成部分重叠的点云。本文选取在ModelNet40 数据集上性能较优的DCP、PRNet、IDAM算法与本文算法进行对比，最终结果如表5所示。

实验结果可视化如图9所示，其中红色点云为源点云，蓝色点云为变化后的目标点云。对于数据分布不均的点云，本文方法通过预测重叠分数、显著分数消除冗余的信息，保留更多的特征信息，同时对特征信息丰富的重叠点给予较高的权重。实验结果表明，本文的方法在配准性能误差上低于所对比方法，对数据分布不均匀的点云具有良好的泛化能力。

Tab.5Registration results on Stanford dataset   

<html><body><table><tr><td>配准算法</td><td>RMSE(r)</td><td>MAE(r)</td><td>RMSE(t)</td><td>MAE(t)</td></tr><tr><td>DCP</td><td>7.56</td><td>7.07</td><td>0.013</td><td>0.012</td></tr><tr><td>PRNet</td><td>4.77</td><td>3.83</td><td>0.008</td><td>0.007</td></tr><tr><td>IDAM</td><td>2.32</td><td>2.21</td><td>0.003</td><td>0.003</td></tr><tr><td>本文方法</td><td>1.75</td><td>1.27</td><td>0.002</td><td>0.002</td></tr></table></body></html>

![](images/c5777f3d124fd83bc665270b9f9498c296b6cb44f9f73dad79380eb34cd86848.jpg)  
图9斯坦福数据集配准结果

# 3.9含高斯噪声的斯坦福数据集配准实验

对真实数据模型加入标准差为0.01的随机高斯噪声，并将噪声裁剪到[-0.05,0.05]，其他设置和3.8节的实验一致。实验结果如表6所示，由于高斯噪声对形状特征的影响，所有模型的配准性能都有所下降。本文方法运用特征交互的方式过滤噪声点及非重叠点。对于不匹配的噪声点给予较低的权重，因此本文方法的性能在RMSE(r)、MAE(r)和MAE(t)等三项指标上优于对比方法，展现了面对噪声点云的鲁棒性。

表5斯坦福数据集上的配准结果  
表6斯坦福数据集上添加噪声的结果  
Tab.6Results on Stanford dataset with Gaussian noise.   

<html><body><table><tr><td>配准算法</td><td>RMSE(r)</td><td>MAE(r)</td><td>RMSE(t)</td><td>MAE(t)</td></tr><tr><td>DCP</td><td>9.46</td><td>5.86</td><td>0.015</td><td>0.010</td></tr><tr><td>PRNet</td><td>6.68</td><td>5.83</td><td>0.009</td><td>0.007</td></tr><tr><td>IDAM</td><td>4.95</td><td>4.77</td><td>0.011</td><td>0.008</td></tr><tr><td>本文方法</td><td>4.65</td><td>4.34</td><td>0.011</td><td>0.007</td></tr></table></body></html>

# 3.10 可视化分析

对于部分重叠的点云，本文通过采样相同数量的重叠关键点、提取重叠关键点的混合特征的方式解决部分重叠点云数据规模不一致、特征密度低等问题。可视化结果如图10所示，其中绿色点云为源点云，红色点云为目标点云，蓝色为提取的重叠关键点。本文仅采用重叠关键点进行配准，可以充分利用重叠点云的丰富特征信息，降低计算量，提高配准运算效率。

![](images/e6dde85e8ff093c45d6524a1c331f021f17d5f7b4ffd7b5d448053470221883a.jpg)  
Fig.9Stanford dataset registration results   
图10重叠关键点提取  
Fig.10Overlapping key points extraction

图11为本文方法与ICP算法、FGR算法的配准结果。其中绿色点云为源点云，红色点云为目标点云。从结果可以看出，面对点云数据规模不一致、特征密度低的部分重叠点云，ICP算法易陷入局部最优，FGR算法未能高效的识别两点之间相似度。本文的方法在面对部分重叠点云时能获得更高的配准精度，在数据集上的定量比较和视觉效果上都优于所对比的方法。

![](images/108fc48d2d09d5533a919e76aaf5287caac526f6eb37393afacebd8901f3a251.jpg)  
  
Fig.11Registration results of different algorithms

# 4 结束语

本文提出了一种基于重叠域采样混合特征的点云配准算法。在有效提取重叠点的同时降低目标点云中正确对应点被移除的概率。首先，运用特征交互和采样显著特征的方式获得更丰富的点云特征，增强了算法对特征信息的学习能力，降低了计算量。其次，结合点云的几何信息和空间信息构建混合特征矩阵，利用了不同点对特征之间的相互作用，降低了初始位置对点云配准的影响。最后，采用有效性分数计算网络为每个点分配相应的权值，增强了网络对重要信息的鉴别能力。在合成点云数据集ModelNet40和真实点云数据集上的实验结果表明，本文的方法在面对部分重叠点云时能获得更高的配准精度，在保持配准效率的同时具有更高的鲁棒性和更好的泛化能力。

# 参考文献：

[1]Li J,Zhang C,Xu Z,et al. Iterative distance-aware similarity matrix convolution with mutual-supervised point elimination for efficient point cloud registration [C]// Proc of European Conference on Computer Vision. Springer, Cham,2020:378-394.   
[2]Wong J M,Kee V,Le T,et al.Segicp:Integrated deep semantic segmentation and pose estimation [C]//Proc of IEEE/RSJ International Conference on Intelligent Robots and Systems.2017:5784-5789.   
[3]Blais G,Levine MD.Registering multiview range data to create 3D computer objects [J].IEEE Trans on Pattern Analysis and Machine Intelligence,1995,17 (8): 820-824.   
[4]Lu W,Zhou Y,Wan G,et al.L3-net: Towards learning based lidar localization for autonomous driving[C]//Proc ofIEEE/CVF Conference on Computer Vision and Pattern Recognition.Piscataway,NJ:IEEE Press,2019:6389-6398.   
[5]Zhu L,Liu D,Lin C,et al. Point cloud registration using representative overlapping points [EB/OL].(2021) .https://arxiv.org/abs/2107.02583.   
[6]BeslPJ,McKay ND.A method for registration of3-D shapes[J].IEEE Trans on Pattern Analysis and Machine Intelligence,1992,14 (2):239- 256.   
[7]Zhou Q Y,Park J,Koltun V.Fast global registration [C]// Proc of European Conference on Computer Vision. Springer, Cham,2016:766- 782.   
[8]Rusu RB,Blodow N,Beetz M.Fast point feature histograms (FPFH) for 3D registration [C]//Proc ofIEEE International Conference on Robotics   
[Iv] IICI point cloud registration using pointnet [Cl// Proc of IEEE/CVF Conference on Computer Vision and Pattern Recognition.Piscataway, NJ: IEEE Press,2019: 7163-7172.   
[11] Qi C R,Su H,Mo K,et al.Pointnet: Deep learning on point sets for 3d classification and segmentation [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.Piscataway,NJ: IEEE Press, 2017: 652-660.   
[12] Lucas B D,Kanade T.An iterative image registration technique with an application to stereo vision [Cl/ Proc of the 7th Intermational Joint Conference on Artificial Inteligence.Morgan Kaufmann Publishers Inc, 1997.   
[13] Wang Y, Solomon JM. Deep closest point: Learning representations for point cloud registration [Cl//Proc of IEEE/CVF International Conference on Computer Vision.Piscataway,NJ: IEEE Press,2019: 3523-3532.   
[14] Wang Y,Sun Y,Liu Z,et al.Dynamic graph cnn for learning on point clouds [J].Acm Trans On Graphics,2019,38 (5): 1-12.   
[15] Wang Y,Solomon JM.Prnet: Self-supervised learning for partial-topartial registration [J].Advances in Neural Information Processing Systems,2019,32.   
[16] Jang E,Gu S,Poole B. Categorical reparameterization with gumbelsoftmax [EB/OL].(2016).https://arxiv.org/abs/1611.01144   
[17] Yew Z J,Lee G H. Rpm-net: Robust point matching using learmed features [C]//Proc of IEEE/CVF Conference on Computer Vision and Pattern Recognition.Piscataway,NJ: IEEE Press,2020: 11824-11833.   
[18] Choy C, Park J, Koltun V.Fully convolutional geometric features [C]// Proc of IEEE/CVF International Conference on Computer Vision. Piscataway, NJ: IEEE Press,2019: 8958-8966.   
[19] Bai X,Luo Z, Zhou L,et al. D3feat: Joint learning of dense detection and description of 3d local features [C]//Proc of IEEE/CVF Conference on Computer Vision and Pattern Recognition. Piscataway，NJ: IEEE Press,2020: 6359-6367.   
[20]熊丰伟，庄健，沈人．基于邻域曲率的低特征辨识度点云配准方法 [J]．计算机应用研究,2022,39(1):6.(Xiong Fengwei,Zhuang Jian, Shen Ren.A low feature recognition degree point cloud registration method based on neighborhood curvature [J] Computer Application Research,2022,39(1):6)   
[21] Huang S,Gojcic Z,Usvyatsov M,et al.Predator: Registration of 3d point clouds with low overlap [C]// Proc of IEEE/CVF Conference on Computer Vision and Pattern Recognition.Piscataway,NJ: IEEE Press, 2021: 4267-4276.   
[22]秦红星，刘镇涛，谭博元．深度学习刚性点云配准前沿进展[J]．中 国图象图形学报,2022,27(2):329-348.(Qin Hongxing,Liu Zhentao, Tan Boyuan.Advances in rigid point cloud registration for deep learning [J] Chinese Journal of Image and Graphics,2022,27(2): 329-348)   
[23]张元，李晓燕，韩燮．一种低重叠率的三维点云配准方法[J].激光 与光电子学进展,2021,58(8):0810014.(Zhang Yuan,Li Xiaoyan, Han Xie.A 3D point cloud registration method with low overlap rate [J] Progress in Laser and Optoelectronics,2021,58 (8): 0810014)   
[24] 李鑫，莫思特，黄华，等．自动计算重叠度的多源点云配准方法[J]. 红外与激光工程,2021,50(12):270-278.(Li Xin,Mo Site,Huang Hua, et al.Multi source point cloud registration method for automatic calculation of overlap [J] Infrared and Laser Engineering,2O21,50 (12):

# 270-278)

[25]Xu H,Liu S,Wang G,et al.Omnet:Learning overlapping mask for partial-to-partial point cloud registration [C]//Proc of the IEEE/CVF International Conference on Computer Vision.2021:3132-3141.

[26] Wyu Z,Pan S,ChenF,et al.A comprehensive survey on graph neural networks [J].IEEE Trans on Neural Networks and Learning Systems, 2020,32 (1): 4-24.