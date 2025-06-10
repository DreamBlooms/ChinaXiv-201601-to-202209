# 利用神经网络的城区机载激光雷达点云分类算法\*

释小松，程英蕾，赵中阳(空军工程大学 信息与导航学院，西安 710077)

摘要：为了将神经网络应用于城区激光雷达点云数据分类，并且针对大规模点云数据训练过程中计算量大、耗时长的问题，改进原有Point-Net神经网络，加入了点云邻域特征的提取和分析，基于该神经网络提出了一种新的点云分类算法。通过网格化聚类和重采样压缩原始点云数据量，提取多尺度邻域点云数据，利用改进Point-Net完成对城区点云数据的分类，用不同地区数据验证本文分类算法。结果表明该算法分类效果良好，分类精度较高；数据训练过程中的计算量减少。因此，该算法能够对城区机载激光雷达数据实现有效分类。

关键词：神经网络；激光雷达；数据压缩；邻域特征提取；点云分类 中图分类号：TP391.4 doi: 10.19734/j.issn.1001-3695.2018.10.0783

Airborne LiDAR point clouds classification algorithm for Urban classification using neural network

Shi Xiaosong, Cheng Yinglei, Zhao Zhongyang (College of Information&Navigation,Air Force Engineering University,Xi'an 71oo77,China)

Abstract: In order to apply neural network to urban LiDAR point clouds data classification,and to decrease large computation and long time consuming in the training process of large scale point clouds data,this paper improved the originalPoint-Net neural network byadding neighborhood characteristicsof point clouds，and it proposed a new classification algorithm for point cloudsbasedonthe improved Point-Net.This algorithmcompressed theoriginal point clouds data volume through gridclusteringand resampling,andthen it extracted multi-scale neighborhood point clouds data and classified urban point clouds byusing improved Point-Net.This paper verified the clasification algorithm with data fromdifferentregions.Theresults show thatthe algorithm has good clasification effect,high clasificationaccuracyand less calculation. Therefore,the algorithmcan realize effective clasification of airborne LiDAR data in urban areas.

Key words: neural network; LiDAR; data compression; neighborhood feature extraction; pointclouds classfication

近年来，随着激光雷达(light detection and ranging,LiDAR)技术的兴起，三维点云数据被广泛应用于遥感测绘等多个领域[1。点云数据不受光照、阴影等因素的影响，并且拥有丰富的三维空间信息[2]。目前，点云处理最热门的方向就是将机器学习应用于点云数据分类。最常用的机器学习方法有聚类分析[3]、支持向量机[4](support vector machine,SVM)、随机森林[5](random forest，RF)方法、贝叶斯网络[6]等方法。

机器学习从已有点云数据中提取的多种特征进行点云数据分类。Mallet等人[7提取全波形特征，用支持向量机进行点云分类。Anguelov等人[8]用马尔可夫随机场模型将点云数据分为建筑、植被、灌木等三类。Vu等人提出用基于激光脚点数据的高程值的K-均值聚类法将数据分割成高层建筑物、地面点及其他地物三大类。点云数据的特征提取通常需要连同邻域内的其他点进行分析，各种特征的定义需要考虑邻域的形状和大小，这些特征表征一个小范围内的点云数据特性[10]。激光雷达扫描得到的点云数据量通常非常庞大，机器学习方法需要人工提取特征，这一过程复杂耗时并且提取的特征存在表达的局限性。

随着深度学习的再次兴起，近几年人们开始用深度神经网络来对点云数据进行分类。深度学习作为机器学习的分支，通过级联神经网络逐层抽象得到特征，不需要人工提取特征，减少研究者的工作量，并取得比其他机器学习方法更好的效果[]。早期的点云深度学习分类方法先将点云进行体素化或压缩成二维数据，用二元神经网络进行处理，这种方法可以将输入点云有序化，但会造成点云信息的大量丢失；而且神经网络处理大规模点云数据时计算成本巨大[2]。这些问题使得城区点云数据的深度学习分类研究进展缓慢。Qi等人[13]在2017年提出了Point-Net神经网络，可以直接输入点云数据进行分类处理，避免了体素化或二维压缩造成的信息丢失。但Point-Net网络只考虑点云的单点特征和全局特征，忽略局部邻域特征，导致Point-Net神经网络在细节上出现分类错误，除此之外，Point-Net网络处理大规模点云数据时会产生庞大的计算量。

本文在原始Point-Net基础上进行了改进，提出了一种基于改进Point-Net的点云地物分类算法。该算法去除孤立点和冗余点，在保留训练点云必要信息的基础上压缩点云数据量，改进后的Point-Net网络在原有Point-Net的基础上加入局部邻域信息，训练分类模型，提高模型对点云数据细节的分类能力。本文将会从算法的原理和流程、仿真实验过程、实验结果分析这三个方面详细介绍该分类算法，总结算法优缺点，并提出下一步的工作方向。

# 1 算法描述与工作介绍

本节介绍本文点云分类算法的具体流程，并着重介绍本文所做的工作。算法的主要思想是：在保持点云必要信息的基础上压缩点云数据量，用改进后Point-Net网络训练，得到

点云分类模型。图1为具体的算法流程图。

![](images/69ff3d13702d73980681aa8521dec7fdad2ab5a536fd146ae9f82f85c425a688.jpg)  
图1算法流程图

# 1.1剔除孤立点和冗余点

点云数据中存在一部分点与其他的点相距较远，通常称为孤立点(或噪点)。孤立点会造成点云分类出现歧义，降低分类精度；而且孤立点增加不必要的计算量，占用存储资源。城区点云数据中部分区域点过于密集，比如房屋的屋顶、茂密的树丛等，这些区域的点被称为冗余点。去除冗余点对于点云数据影响不大，而Point-Net网络对输入点云的局部细微变化具有良好的鲁棒性，所以在保证点云局部特征的前提下可以通过去除冗余点适当压缩点云数据。图2为点云数据中的孤立点和冗余点。

![](images/ffb0ca894ac7919e8a208079e05d26d5061da9217f9b479eb9fccf3a0527e1ae.jpg)  
Fig.1Flow chart of algorithm   
图2孤立点(左）和冗余点（右)  
Fig.2Isolated points(left) and redundant points(right)

本文算法采用网格化聚类分析方法筛选并剔除孤立点，采用网格化重采样方法筛选并剔除冗余点。具体流程图如图3所示。

首先采用三维网格分割点云数据[14]，网格根据式（1)来构建：

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { d _ { x } = n , d } \\ { d _ { y } = n _ { x } d } \\ { d _ { z } = n _ { x } d } \\ { G r d _ { - } x = ( x _ { \mathrm { n n } } - x _ { \mathrm { n n } } ) / d _ { x } + 1 } \\ { G r d _ { - } y = ( y _ { \mathrm { n n } } - y _ { \mathrm { n n } } ) / d _ { y } + 1 } \\ { G r d _ { - } z = ( z _ { \mathrm { n n } } - z _ { \mathrm { n n } } ) / d _ { z } + 1 } \\ { i = ( x - x _ { \mathrm { n n } } ) / d _ { x } + 1 } \\ { j = ( y - y _ { \mathrm { n n } } ) / d _ { y } + 1 } \\ { k = ( z - z _ { \mathrm { n n } } ) / d _ { z } + 1 } \end{array} \right. } \end{array}
$$

其中： $x _ { \mathrm { m a x } } , x _ { \mathrm { m i n } } , y _ { \mathrm { m a x } } , y _ { \mathrm { m i n } } , z _ { \mathrm { m a x } } , z _ { \mathrm { m i n } }$ 是点云三维坐标的极大值和极小值； $x , y , z$ 为点云坐标； $G r i d _ { - } x , G r i d _ { - } y , G r i d _ { - } z$ 分别是三维坐标上的网格数量；i,j,k取整数后是坐标为 $( x , y , z )$ 的点所在网格的位置； $n _ { x } , n _ { y } , n _ { z }$ 为网格中各维度的放大因子； $^ d$ 是平均点距，平均点距计算公式如式（2）所示。

$$
d = { \sqrt [ 3 ] { \frac { V } { A } } }
$$

其中： $\boldsymbol { V }$ 为点云内最小外接多面体的体积； $A$ 表示点云数据中点的个数。点云数据网格化如图4所示。

![](images/b50b0cea0d7360c57782bf4133bc1481e0dac44d2042762a64e5970c9261cead.jpg)  
图3剔除孤立点(a)和冗余点(b)的算法流程图 Fig.3Flow chart of algorithm for eliminating isolated points(a) and redundant points(b)

均匀格网分割点云数据之后，统计每个单元格网内点的个数，作为每一单元格网的网格密度 $R _ { n } ( n = 1 , 2 , \cdots )$ 。

![](images/c7ab8e7cb7e6062a4cf6052c0bfca10a476322f2ff80f5d395f320cb715f67e4.jpg)  
图4点云数据网格化

1.1.1剔除孤立点

剔除孤立点时，首先选取一个阈值 $T _ { 1 }$ ，本文算法将 $T _ { \mathrm { l } }$ 设置为加权平均格网密度，即

$$
T _ { 1 } = a \overline { { { R } } } _ { n } ( n = 1 , 2 , \cdots )
$$

其中： $\overline { { R } } _ { n } ( n = 1 , 2 , \cdots )$ 为平均格网密度， $\mathbf { \Delta } _ { a }$ 为权值，权值可根据实际点云数据进行调整。当某一单元格网的密度 $R _ { n } ( n = 1 , 2 , \cdots )$ 大于 $T _ { 1 }$ 的时候，把该格网选为种子格网，落入种子网格内的点就是种子点，找出点云数据中的所有种子网格。将密度最大的格网中的所有种子点归为同一类，并将这些点作为初始聚类中心 $V _ { 0 }$ □

之后，计算剩余的格网 $V _ { n } ( n = 1 , 2 , \cdots )$ 中的种子点，到密度最大格网中种子点的距离。这里种子点间距设定为欧氏距离$D _ { 1 }$ ，公式为

$$
D _ { 1 } ( i , j ) = \sqrt { ( x _ { i } - x _ { j } ) ^ { 2 } + ( y _ { i } - y _ { j } ) ^ { 2 } + ( z _ { i } - z _ { j } ) ^ { 2 } }
$$

其中： $x _ { i } , x _ { j } , y _ { i } , y _ { j } , z _ { i } , z _ { j }$ 为输入的点云数据中第 $i$ 和 $j$ 两点的三维坐标，由于输入点云数据包含了每个点的三维坐标值$( x , y , z )$ ，所以可以很方便地用来计算点之间的距离。当点间距小于阈值 $T _ { 2 }$ 时，将其归为一类，遍历所有的种子格网$V _ { n } ( n = 1 , 2 , \cdots )$ 直至无相似点可以聚类或类内点数达到设定阈值为止。未归入任何类的种子点则按上述方法继续选出密度最大格网作为初始聚类中心 $V _ { 0 }$ ，重复上述运算。

剩下的非种子格网中的点，计算与其相距最近的种子点并计算距离 $D _ { 1 }$ 。如果距离 $D _ { 1 }$ 小于阈值 $T _ { 2 }$ ，将该非种子点与种子点做同类认定；否则，将其判为孤立点。遍历点云数据，找出并剔除所有孤立点。孤立点剔除结果如图5所示。

![](images/e6de6fd251c20c32de76d8e9a475a6bf522fbc83db5e7dd7f199fd01215f3b9e.jpg)  
图5孤立点剔除结果  
Fig.5Results of eliminating isolated points   
Fig.6Results of eliminating redundant points( $\scriptstyle \boldsymbol { \eta } = 6 6 . 6 \% , \boldsymbol { \mathrm { m } } = 2$

1.1.2 剔除冗余点

剔除孤立点时，首先根据每个点云格网 $V _ { n } ( n = 1 , 2 , \cdots )$ 的平均格网密度 $\overline { { { R } } } _ { n } ( n = 1 , 2 , \cdots )$ 设置阈值 $T _ { 3 }$ ， $T _ { 3 }$ 求解方法与 $T _ { \mathrm { l } }$ 相同，权值要根据实际点云数据进行调整，大于阈值 $T _ { 3 }$ 的选为种子格网，剩下的不作处理，遍历点云数据，筛选去除点云表面

和内部的稀疏点云格网。

之后，对每个种子格网 $V _ { n } ( n = 1 , 2 , \cdots )$ 中的点云数据进行重采样，采样率》根据实际点云数据的疏密程度进行选择。每次采样后重新计算各点云格网 $V _ { n } ( n = 1 , 2 , \cdots )$ 的密度$R _ { \ n } ^ { \prime } ( n = 1 , 2 , \cdots )$ ，之后重复整个采样过程， $m$ 次迭代后直到没有种子格网密度值大于阈值 $T _ { 3 }$ ，完成采样。冗余点去除后密集区域的种子点适当减少，但点云形状、高程、纹理等局部信息基本没有改变。冗余点去除结果如图6所示。

![](images/8b56ee748f5ed5136db1f0672d9085dd97614da9ee2adb5050fbc62edfc51a17.jpg)  
Fig.4Gridding of point clouds data   
图6冗余点剔除结果（ $\eta { = } 6 6 . 6 \%$ ， $m { = } 2$ ）

# 1.2改进Point-Net神经网络

Point-Net神经网络在网络中加入了T-Net输入变换矩阵和最大池化（maxpooling）层。T-Net可以通过点云的位置信息学习到一个旋转矩阵，通过损失函数来对旋转矩阵进行调整，把输入点云数据旋转到一个更有利于分类或分割的角度；MaxPooling层是在卷积层之后对输入做降采样的层结构：在降低输出维度的同时保留显著的特征[15]，在Point-Net 神经网络中用于提取点云的全局特征，maxpooling层公式如式（5）所示。

$$
f \left( \left\{ x _ { 1 } , . . . , x _ { n } \right\} \right) { } = \operatorname* { m a x } ( h ( x _ { 1 } ) , . . . , h ( x _ { n } ) )
$$

其中： $x _ { 1 } , x _ { 2 } , . . . , x _ { n }$ 为部分网络的输入点云数据，max 函数代表最大池化层， $h$ 为卷积函数。max函数是对称函数，使神经网络不受输入点云排序变化的影响，解决点云的无序性[16]。T-Net和MaxPooling层的引入克服了神经网络训练点云数据时的无序性和旋转性问题，因此Point-Net神经网络可以直接把点云数据作为输入进行处理，而无须再进行体素化或二维压缩处理。

引言中提到，Point-Net神经网络忽略了点的局部邻域信息和特征，导致在某些细节上出现分类错误。本文在原有Point-Net神经网络的基础上，提取了不同尺度的局部点云数据，用小型Point-Net网络提取点云局部特征用于分类模型训练。局部特征提取的整体思想就是：先选取一些重要的点作为每个局部区域的中心点，然后在这些中心点的周围选取 $k$ 个欧式距离近邻点；再将 $k$ 个近邻点作为一个局部点云，用小型网络来提取特征。

# 1.2.1邻域选取

通常不同类别的地物在多种尺度下的点云特征区别越明显，地物的可分性越强[17]；由于点云数据密度不均，所以通过固定范围选取的固定个数的近邻点是不合适的，这也说明要用不同尺度选取局部区域。

邻域选择首先从剔除冗余点后的样本点云数据中抽取出若干中心点，具体采用最远点采样法[18]选取。首先人工从8种不同地物类别中选取8个初始中心点组成中心点集，之后遍历点云数据，找到距各中心点欧式距离 $D _ { 2 }$ 最远点作为新的中心点，并加入中心点集，迭代该过程，直到所有中心点的最远距离 $D _ { 2 }$ 小于阈值 $\mathbf { \xi } _ { l }$ ，停止迭代，最终得到的中心点$O _ { n } ( n = 1 , 2 , \cdots )$ 组成完整中心点集，这里的阈值 $\mathbf { \xi } _ { l }$ 设置为样本点云中不同地物中心的最小距离。最远点采样法可以在整个区域范围内不断寻找符合条件的采样点，采样点分布由疏到密，防止过采样导致的采样数据冗余，同时阈值i保证了采样得到的中心点能够分布在不同的地物种类中。相比于均匀分布采样，最远点采样能够更好完成密度分布不均的点云采样任务。

之后进行邻域半径选取，利用前文中确定的点云平均点距 $^ d$ 确定尺度 $\textbf { \em L }$ ，尺度计算公式为

$$
L = s d
$$

其中： $s$ 为放大因子，需要根据具体的点云数据设定； $\textit { d }$ 为点云平均点距。最小尺度应大于平均点距 $\textit { d }$ ，最大尺度要根据实际地物尺寸进行设置。每个中心点都确定多个尺度的邻域，得到多个欧式距离邻域点云。本文选取两种邻域尺度的点云组合提取邻域特征，通过对不同尺度组合训练模型分类精度的测试，找到最优组合。经测定，数据集平均点距 $d$ 为$0 . 3 \mathrm { m }$ ，本文选定尺度范围为 $0 . 6 { \sim } 6 . 9 \mathrm { m }$ ，均匀划分8个尺度，平均尺度间隔为 $0 . 9 \mathrm { m }$ 。实验选定最优尺度组合为 $1 . 5 \mathrm { m }$ 和$6 . 9 \mathrm { m }$ ，以中心点 $O _ { n }$ 为圆心，尺度 $\boldsymbol { L }$ 为半径选取邻域，不同尺度邻域选取结果如图7所示。

![](images/588af3d38fbe8b0283dda67eb46d4450971b2d307cc918638fc92b5bdd628d0a.jpg)  
图7不同尺度邻域选取结果

Fig.7Results of multi-scale neighborhood selection

不同尺度邻域选取到了树木、建筑物、地面等各种地物样本，不同尺度下不同样本呈现不同的细节。地面在不同尺度下都比较平坦；整个树木会呈现立体效果，而小范围内的枝干和灌木表面则会呈现线或平面效果；建筑物在小尺度下的多为平坦的屋顶，在大尺度下会包含边缘的棱角和竖直墙面等细节。除此之外，多尺度提取可以有效应对点云数据分布不均的问题，小尺度邻域在稀疏区域难以有效提取点云特征，而大尺度邻域可以在对应区域实现有效特征提取。

# 1.2.2多尺度邻域特征提取

多尺度邻域点云提取后，将大尺度和小尺度的邻域点云分成两组，每组数据单独用一个小型神经网络提取特征。小型神经网络包含一个T-Net输入变换矩阵、双层感知机MLP和 Max Pooling层。

每个邻域点云块的 $k$ 个点作为神经网络中的一个patch输入小型神经网络，先通过T-Net校正数据，之后进行卷积和池化得到一个 $N$ 维特征向量作为此中心点的特征点。所有邻域点云块的输出特征点又可以组成新的邻域特征点块，再次输入相同结构的Point-Net网络进行特征提取。这样随着提取次数加深，特征点的个数越来越少，但是每个特征点包含的信息越来越多。

本文算法中，每个尺度分组中都设置了三层小型神经网络，第三层网络通过池化得到一个256维特征向量。每组的特征向量通过全连接层连接，得到最终的邻域特征向量，邻域特征提取及改进后Point-Net网络流程框图如图8所示。

邻域特征提取网络与原始Point-Net神经网络是并行运算关系，邻域特征可用其他设备并行处理后输入原始

Point-Net网络，不增加原始Point-Net网络的计算负担。邻域特征向量与原始Point-Net 神经网络得到的单点特征和全局特征通过全连接层结合，用于点云的地物分类，单点特征，局部特征和全局特征连接结构如图9所示。

![](images/93921109ad1e403123eac5ea96fefef83cb9a01155239ddfbd52ed0ab48a1a6a.jpg)  
图8改进后Point-Net网络流程和小型神经网络结构

![](images/95310c85d61ea4dc0d2223e8f9b8a991ab4dc04e2a5605e1c1d6f31bd3e3d193.jpg)  
Fig.8 Improved Point-Net network process(a) and small neural network   
图9特征连接结构  
Fig.9Structure of feature connection

改进后的Point-Net神经网络由于提取了点云的局部特征，所以有效克服了原始Point-Net神经网络细节分类上出现的错误，提高了整体的分类精度。

# 2 实验过程

本实验使用的激光雷达数据集是Semantic3D户外数据集[19]，该数据集总计超过40亿个点，包含了地形、植被、建筑等八种语义类别，涵盖了街道、广场、足球场等场景，共有15个训练场景和4个测试场景，平均每个场景有1000万到2000万不等的数据点，这些场景能够很好地模拟城区的地理环境。部分场景如图10所示。

首先处理点云训练数据，去除孤立点和冗余点。不同点云场景数据可能存在一定的差异，具体预处理时可以根据实际情况对各个参数进行适当调整。经过多次实验分析，本文算法设定分割单元网格大小为 $2 0 \mathrm { m } \times 2 0 \mathrm { m } \times 1 0 \mathrm { m }$ ，网格点云密度阈值为 $T _ { \mathrm { l } }$ 为60，点之间的距离阈值 $T _ { 2 }$ 为 $1 0 \mathrm { m }$ ；去除冗余点时，单元网格密度阈值 $T _ { 3 }$ 设定为100，采样率 $\eta$ 为 $6 6 . 6 6 \%$ 迭代次数 $\mid m$ 为2。处理后，场景点云数据平均数据量减少700万\~1500万。

![](images/46bfe1be8af33f60043813f072e7cab04f653ad96534c773502faf18e5ac340e.jpg)  
图10Semantic3D 数据集Fig. 10 Semantic3D dataset

之后对数据进行邻域选择。1.2.1小节已提到，点云平均点距 $d$ 为 $0 . 3 \mathrm { ~ m ~ }$ ，选定小尺度放大因子 $s _ { 1 }$ 为5，大尺度放大因子 $s _ { 2 }$ 为23，邻域半径 $\boldsymbol { L }$ 分别为 $1 . 5 \mathrm { ~ m ~ }$ 和 $6 . 9 \mathrm { ~ m ~ }$ 。最远点采样法选取中心点 $O _ { n } ( n = 1 , 2 , \cdots )$ ，点云分布密集区域的中心点采集小尺度邻域点云数据，分布稀疏区域采集大尺度点云数据。

整体点云数据输入原始Point-Net网络，得到点云的单点特征和全局特征；邻域点云数据输入改进后的邻域特征提取网络，得到局部邻域特征。局部邻域特征通过全连接层加入Point-Net网络分类器，网络结合所有特征对点云数据进行分类。Point-Net 网络训练时，最大迭代次数（epoch）设置为200，初始学习率为0.01，批尺寸（batchsize）为32，网络中使用Adam 优化算法[20]。通过对15个训练场景的训练，得到训练后的分类模型。之后利用训练好的模型对Semantic3D提供的测试数据集进行分类，分类结果如图11所示。

![](images/70e4e55edf72ac21b5d6f61737b80e04d22f90407501bb787f691c1cff073c39.jpg)  
图11Semantic3D 测试点云样本（左）和分类结果（右） Fig.11Semantic3D tested point clouds samples(left) and classification results(right)

# 3 实验结果分析与评价

首先，对本文中不同尺度邻域特征的提取效果进行评价。

1.2.1节中总共提取了8个尺度的邻域点云数据，范围为$0 . 6 { \sim } 6 . 9 \mathrm { m }$ 。最小尺度是点云平均点距 $^ d$ 的2倍，保证在密集区域该尺度邻域下点云能提取相应特征；最大尺度根据点云场景中地物尺寸设定为 $6 . 9 \mathrm { m }$ ，保证稀疏区域邻域包含足够多的点云细节。将尺度范围内较小的4个尺度划为小尺度集，较大的4个尺度划为大尺度集，每次从两个集中各选取一个尺度，分别提取稀疏区域和密集区域的点云数据训练分类模型，并对分类效果进行分析。分类效果用总体分类精度衡量，总体精度是模型在所有测试集上预测正确的与总体数量之间的比值。部分分类精度较高的尺度组合以及与单一尺度分类精度对比如表1所示。

Table1 Comparison of the overall classification   

<html><body><table><tr><td colspan="3">accuracy of different scales</td></tr><tr><td>小尺度(m)</td><td>大尺度(m)</td><td>总体分类精度(%)</td></tr><tr><td>3.3</td><td>6.9</td><td>90.9</td></tr><tr><td>1.5</td><td>6.9</td><td>90.8</td></tr><tr><td>2.4</td><td>6.9</td><td>90.6</td></tr><tr><td>0.6</td><td>6.9</td><td>89.9</td></tr><tr><td>1.5</td><td>6</td><td>90.1</td></tr><tr><td>1.5</td><td>5.1</td><td>89.4</td></tr><tr><td>无</td><td>6.9</td><td>89.8</td></tr><tr><td>1.5</td><td>无</td><td>89.1</td></tr></table></body></html>

由表1分析可知，单一尺度的总体分类精度远小于多尺度组合的分类精度。对比不同尺度组合，大尺度半径越大，邻域包含的点云细节增加，点云总体分类精度越高，所以大尺度半径选 $6 . 9 \mathrm { { m } }$ ；而小尺度半径为 $1 . 5 \mathrm { m }$ 时分类精度与半径为 $2 . 4 \mathrm { ~ m ~ }$ 和 $3 . 3 \mathrm { ~ m ~ }$ 的分类精度相差不大，并且略高于半径2.4m的分类精度，说明半径为 $1 . 5 \mathrm { ~ m ~ }$ 的尺度邻域可以充分提取密集区域的邻域特征，考虑到邻域半径增大会导致训练数据量增大，小尺度半径选取为 $1 . 5 \mathrm { m }$ 。

评估本文算法的分类效果并与其他算法进行对比，用平均重叠度、每类物体重叠度和总体精度三个具体指标进行评估，测试整体和单类物体的分类精度。重叠度用百分比表示，计算公式如式（7）所示。

$$
I o U = \frac { T } { T + F _ { 1 } + F _ { 2 } }
$$

其中： $_ { I o U }$ 为重叠度； $T$ 为某类样本中正确分类为该类别的点数； $F _ { 1 }$ 为该类别样本被错分类为其他类别的点数； $F _ { 2 }$ 为其他类别的样本被错分类为该类别的点数。分类精度的评估结果如表2和3所示。

# 表2Semantic3D数据集整体和各类别的重叠度

表1不同尺度的总体分类精度比较  
Table 2Overall iou and each category iou of Semantic3D dataset   

<html><body><table><tr><td>Dataset</td><td>3D-FCNN-TI</td><td>OctreeNet_CRF</td><td>SEG Cloud[21]</td><td>Point-Net 本文算法</td><td></td></tr><tr><td>Mean IoU(%)</td><td>58.2</td><td>59.1</td><td>61.3</td><td>66.7</td><td>68.1</td></tr><tr><td>路面IoU(%)</td><td>84.0</td><td>90.7</td><td>83.9</td><td>85.3</td><td>87.6</td></tr><tr><td>草地IoU(%)</td><td>71.1</td><td>82.0</td><td>66.0</td><td>88.0</td><td>90.3</td></tr><tr><td>树木IoU(%)</td><td>77.0</td><td>82.4</td><td>86.0</td><td>89.3</td><td>90.5</td></tr><tr><td>灌木IoU(%)</td><td>31.8</td><td>39.3</td><td>40.5</td><td>42.7</td><td>42.5</td></tr><tr><td>建筑物IoU(%)</td><td>89.9</td><td>90.0</td><td>91.1</td><td>92.5</td><td>92.7</td></tr><tr><td>人造物体IoU(%)</td><td>27.7</td><td>10.9</td><td>30.9</td><td>31.0</td><td>31.6</td></tr><tr><td>扫描伪影IoU(%)</td><td>25.2</td><td>31.2</td><td>27.5</td><td>41.1</td><td>41.0</td></tr><tr><td>车辆IoU(%)</td><td>59.0</td><td>46.0</td><td>64.3</td><td>66,7</td><td>68.8</td></tr></table></body></html>

表2展示了本文算法和其他算法在Semantic3D数据集上每个类别的IoU和平均IoU 值，表3对本文算法以及其他几种算法在Semantic3D数据集上的整体分类精度进行了比较。

本文算法在IU平均值和大部分类别的IoU上优于其他几种神经网络，能够取得比其他神经网络更高的整体分类精度。

Table 3Overall classification accuracy of Semantic3D dataset   

<html><body><table><tr><td>Dataset</td><td>整体分类精度/%</td></tr><tr><td>3D-FCNN-TI</td><td>87.5</td></tr><tr><td>OctreeNet_CRF</td><td>89.9</td></tr><tr><td>SEGCloud</td><td>88.1</td></tr><tr><td>Point-Net</td><td>89.1</td></tr><tr><td>本文算法</td><td>90.8</td></tr></table></body></html>

本文通过训练时间来衡量Point-Net神经网络计算成本，通过统计多组实验训练时间，求出原始Point-Net神经网络与本文算法的平均训练时间，如表4所示。通过对比可以发现，本文算法中网络训练时间比原始网络训练时间大大减少，证明本文算法有效减少计算量。

表3Semantic3D 数据集整体分类精度  
表4算法训练时间  
Table 4Training time of algorithm   

<html><body><table><tr><td>分类算法</td><td>训练时间/h</td></tr><tr><td>Point-Net</td><td>10.2</td></tr><tr><td>本文算法</td><td>7.9</td></tr></table></body></html>

# 4 结束语

本文提出了一种基于改进Point-Net 网络的机载激光雷达数据的地物分类方法，用于机载激光雷达点云数据分类。通过去除点云数据的孤立点和冗余点，压缩原始点云数据，减少训练过程计算量；并在原始Point-Net网络的基础上，加入点云的局部特征，弥补Point-Net网络细节分类上的不足，提高整体和单个物体的分类精度。用Semantic3D数据集进行测试，取得了较好的分类结果。同时从实验中看出，Point-Net神经网络的分类效果还有待提高，计算成本较大，搭建更加优化的神经网络结构，进一步提高运算的精度和效率是下一步需要努力的方向。

# 参考文献：

[1]吴军，刘荣，郭宁，等.SVM加权学习下的机载LiDAR数据多元分 类研究[J].武汉大学学报：信息科学版,2013,38(1):1-5.(WuJun, Liu Rong,Guo Ning,et al.Aerial LiDAR data classification using weighted support vector machines [J].Geomatics and Information Science ofWuhan University,2013,38(1):1-5.)   
[2] 郝雯，王映辉，宁小娟，等．面向点云的三维物体识别方法综述[J]. 计算机科学，2017,44 (9):11-16.(Hao Wen,Wang Yinghui,Ning Xiaojuan,etal.Surveyof 3Dobjectrecognition forpointclouds[J]. Computer Science,2017,44(9):11-16.)   
[3]朱磊，王健，许开辉，等．采用聚类分析的车载点云地物分类[J]. 测绘科学,2016,41(4):77-82.(Zhu Lei,Wang Jian,Xu Kaihui,et al. Classification method of vehicle-borne LiDAR point cloud based on clustering [J]. Science of Surveying and Mapping,2016,41 (4): 77-82.)   
[4]王旭东，段福洲，屈新原，等．面向对象和 SVM结合的无人机数据 建筑物提取 [J]．国土资源遥感,2017,29(1):97-103.(Wang Xudong， Duan Fuzhou,Qu Xinyuan,et al.Building extraction based on UAV imagery data with the synergistic use of objected-based method and SVM classifier [J].Remote Sensing for Land & Resources,2017,29 (1): 97-103.)   
[5]孙杰，赖祖龙．利用随机森林的城区机载LiDAR数据特征选择与分 类[J].武汉大学学报：信息科学版，2014,39(11):1310-1313.(Sun Jie，Lai Zulong.Airborne LiDAR feature selection for urban classification using random forests [J].Geomatics and Information Science of Wuhan University,2014,39(11):1310-1313.)   
[6]Stassopoulou A,Caelli T.Building detection using bayesian networks [J].International Journal of Pattern Recognition & Artificial Intelligence,2000,14(6): 715-733.   
[7]Mallet C,Soergel U,Bretar F.Analysis of full-waveform LiDAR data for classification of urban areas [J].Photogrammetrie Fernerkundung Geoinformation,2008,5 (5): 337-349.   
[8]Anguelov D,Taskar B,Chatalbashev V,et al.Discriminative learning of markov random fields for segmentation of 3D scan data [C]// Proc of IEEE Computer Society Conference on Computer Vision and Pattern Recognition.Washington DC: IEEE Computer Society,2005:169-176   
[9]Vu T T,Tokunaga M. Wavelet and scale-space theory in segmentation ofairbornelaserscannerdata[C]//Procofthe 22nd Asian Conference on Remote Sensing.2001.   
[10]郭波，黄先锋，张帆，等．顾及空间上下文关系的 JointBoost 点云分 类及特征降维[J]．测绘学报,2013,42(5):715-721.(Guo Bo,Huang Xianfeng,Zhang Fan,et al.Point cloud classification using JointBoost contextual information for feature reduction [J].Acta Geodaetica et Cartographica Sinica,2013,42 (5): 715-721.)   
[11]魏书法．基于三维点云与二维图像的场景理解[D].北京：中国科 学院大学,2016.(Wei Shufa. Scene Understanding based on Point Clouds and 2D Images [D]. Beijing: University of Chinese Academy of Sciences,2016.）   
[12] Zhou Y,Tuzel O. VoxelNet: End-to-End Learning for Point Cloud Based 3D Object Detection [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition．Washington DC:IEEE Computer Society,2017: 4490-4499.   
[13] Charles R Q, Su H,Mo K,et al. PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. Washington DC:IEEE Computer Society,2017: 652-660.   
[14] Hovad J, Komarkova J,Sedlak P. Slope based grid creation using interpolation of LIDAR data sets [C]/ Proc of International Conference on Software Engineering and Applications. Piscataway NJ: IEEE Press, 2013: 227-232.   
[15] Hackel T,Savinov N,Ladicky L，et al. Semantic3D.net:a new large-scale point cloud classification benchmark [C]// ISPRS Annals of the Photogrammetry,Remote Sensing and Spatial Information Sciences. 2017: 91--98.   
[16] Schmidhuber J. Deep learning in neural networks:an overview[J]. Neural Networks,2015,61(1):85-117.   
[17]岳冲，刘昌军，王晓芳．基于多尺度维度特征和 SVM的高陡边坡点 云数据分类算法研究[J].武汉大学学报：信息科学版,2016,41(7): 882-888.(Yue Chong,Liu Changjun,Wang Xiaofang.Research on point cloud data classfication algorithm for high and steep slope based on multi-scale dimension features and SVM[J].Geomatics and Information Science of Wuhan University,2016,41(7): 882-888.）   
[18] Moenning C, Dodgson N A. Fast Marching farthest point sampling (poster presentation) [C]// Proc of Eurographics.[S.1.]: Eurographics Association 2003.   
[19] Kingma D P,Ba J. Adam: a method for stochastic optimization [EB/OL]. (2017-01-30). htps://rxiv.org/pdf/1412.6980.pdf.   
[20] Tchapmi L, Choy C,Armeni I, etal. SEGCloud: semantic segmentation

of 3D point clouds[C]//Proc of IEEE International Conference on 3D Vision.Picataway,NJ: IEEE Press,2017: 537-547. [21] Lawin F J,Danelljan M,Tosteberg P,et al.Deep projective 3D semantic segmentation [C]//Proc of International Conference on Proc of International Conference on Computer Analysis of Images and Patterns.Cham: Springer,2017:95-107.