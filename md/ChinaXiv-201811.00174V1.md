# 基于线特征的单目SLAM中的迭代数据关联算法‘

魏鑫熵1²，黄俊²，杨晓飞²，彭俊杰1(1．上海大学 计算机工程与科学学院，上海 200444;2.中国科学院上海高等研究院，上海 201210)

摘要：针对基于线特征的单目 SLAM（同时定位与地图构建）中的数据关联问题，提出了一种基于线段端点Patch确认的迭代数据关联算法。算法依据近似共线和端点近似重合两个指标来获取线特征的最近邻关联对，使用基于线段端点Patch 的定向匹配确认机制来剔除最近邻关联对中的错误项，同时以迭代处理的方式提高数据关联的准确性，综合利用了线特征间的几何约束和图像相似性约束。上述算法在公开数据集上进行了测试，与现有线特征数据关联算法的对比实验结果表明，该算法在满足系统实时性的前提下，在线特征关联对数目和关联准确率上均达到了较好效果。

关键词：同时定位与地图构建；数据关联；线段特征；迭代匹配；特征匹配 中图分类号：TP301.4 doi:10.19734/j.issn.1001-3695.2018.05.0508

# Iterative data association algorithm for line-based monocular SLAM

Wei Xinyu1, 2, Huang Jun², Yang Xiaofei², Peng Junjiel (1.SchoolofComputerEngineeing&Science,ShanghaiUniversityhanghai244,China;2.hanghaiAdvancedResearch Institute,Chinese Academy of Sciences,Shanghai 201210,China)

Abstract:Aiming at thedata asociation problem of line-based monocular SLAM,this paper proposed a iterativedata association algorithm based on confirmation of endpoint patch.The algorithm obtained closest feature line pairs acording to approximatecollnearityandapproximatecoincidenceofendpoints,thenused directionalsearch ofendpoint patches toremove the error pairs.Iterative approach isused to improve accuracy.The algorithmcomprehensiveused geometricconstraint and image similarityoffeature ine pairs.The experimentsarecarredoutonapublic dataset.Bycomparison with other similar methods,it is provedthatthe proposeddataassociationapproach notonlysatisfyreal-timerequirement,butalsohasagood performance on match amount and matching accuracy.

Key words:simultaneous localizationand mapping;data association;linesegment feature; iterative matching;feature matching

# 0 引言

随着增强现实、无人机导航等领域的蓬勃发展，视觉SLAM系统在近几年中发展迅速，其中基于特征的视觉SLAM系统在准确性和鲁棒性方面的表现尤为出色，涌现出了很多基于特征的视觉 SLAM系统[1,2]，这些视觉SLAM系统中最常使用的特征是点特征，但基于点特征的SLAM系统在纹理稀疏的场景中（如人造环境中的室内、走廊等）存在特征数量较少的问题；同时由于在数学意义上点的维度为零，基于三维点特征的地图无法表现更多层次的结构化信息，在增强现实等应用中常常需要在此基础上再次提取平面、直线等特征。部分学者尝试在视觉SLAM系统中使用其他特征，这些系统中又以基于线特征的系统为主流[3-]，其原因在于一方面基于线特征的三维地图能够提供更多环境结构信息；另一方面在视觉SLAM应用领域中纹理稀疏的场景常常具有较为丰富的结构化特征（走廊、空旷的房间)，而这些场景中可以提取的线特征数目较多。

相比于点特征，线特征SLAM的发展速度相对缓慢，而且目前已有的一些单目线特征SLAM系统均存在一定问题：这些SLAM一部分对应用环境有特殊要求[4,7,8]；一部分仅能处理线段极其稀疏的场景[3,5,9]。以上这些问题出现的一个重要原因在于目前单目线特征SLAM中数据关联部分存在一定困难。

数据关联是SLAM问题中的重要难点之一，对SLAM系统的鲁棒性和稳定性影响极大，数据关联是指在SLAM系统中的地图数据和当前传感器的输入数据之间建立关联的过程。在视觉SLAM系统中，点特征的数据关联问题已经研究地较为透彻，但由于线特征本身存在的端点不稳定、过度分割等问题，线特征的数据关联还有待进一步研究。

目前单目线特征SLAM中并没有一个通用的数据关联方法，但已有的算法大致可以分为如下三类：第一类利用当前相机预测位姿将地图中的三维线段投影到二维图像平面上，使用最近邻匹配的方法得到三维线段与二维线段的匹配对[4]；第二类使用二维线段端点或其他采样点周围的图像块（Patch)[8.9]和线段描述子[10]来获取关联对，将三维线段已关联的二维线段的线段描述子或采样点Patch与待关联的二维线段进行比较，得到关联对，其中线段描述子以 MSLD[I]和LBD[12]为主；第三类方法结合了前两种数据关联方法[3,51，使用最近邻方法得到候选二维线段集合，然后使用基于线段端点Patch或线段描述子的方式得到最终匹配结果。其中第一类方法的速度最快，但在线段密集或预测位姿误差较大的情况下匹配错误率过高，而且如何判断最近邻线段也是一个没有很好解决的问题；第二类方法准确度较高，但其计算量较大，同时由于目前已有的线特征提取算法得到的线段端点可重复性较差的问题，仅使用图像特征难以得到足够的匹配对；第三类方法虽然改善了以上单一方法存在的问题，但已有的实现方式中计算量仍然较大，当预测位姿误差较大时，最后得到的正确匹配对数目仍然较少。

本文针对单目线特征SLAM中地图内三维线特征与图像中二维线段的关联问题展开研究，提出了一种基于线段端点Patch确认的迭代线特征关联算法。该算法融合了最近邻匹配算法和线段端点Patch匹配算法，在改进最近邻匹配中的最近邻线段定义、Patch 匹配中Patch 搜索策略的基础上，通过Patch匹配来减小最近邻匹配方法错误率较高的缺陷，利用迭代优化的框架处理关联算法中输入数据噪声较高的问题。

# 1 问题定义

本文讨论的数据关联问题的应用场景是基于图优化框架的单目线特征SLAM系统，本文将单目线特征SLAM系统中的数据关联问题定义为：给定一个三维线特征集合$\boldsymbol { L } = \left\{ \boldsymbol { L } _ { 1 } , \boldsymbol { L } _ { 2 } , \cdots , \boldsymbol { L } _ { a } \right\}$ 和当前帧 $I _ { \mathrm { c } }$ 内的二维线段集合 $\hat { l } = \{ l _ { 1 } , l _ { 2 } , \cdots , l _ { b } \}$ 在 $\mathbf { \Omega } _ { L }$ 与 $\hat { l }$ 两个集合中寻找正确匹配对的问题。

在SLAM系统中，数据关联模块的主要功能是为相机位姿和地图三维特征的优化过程提供输入数据，将数据关联算法的结果表示为 $G = \{ g _ { 1 } , g _ { 1 } , \cdots , g _ { n } \}$ ，其中 $g _ { i } { \left( i = 1 , 2 , \cdots , n \right) }$ 表示某个特定的关联对 $\left( L _ { _ i } , l _ { j } \right)$ ，关联对中三维线特征与二维线段的关联距离表示为 $d ( g _ { i } , T _ { \mathrm { c } } , K )$ ，其中 $T _ { \mathrm { c } }$ 为当前帧位姿， $\boldsymbol { \kappa }$ 为相机内参矩阵，将关键帧位姿集合表示为 $T = \{ T _ { 1 } , T _ { 2 } , \cdots , T _ { m } \}$ ，SLAM系统中以下两个优化过程会中使用到数据关联结果：

$$
T _ { \mathrm { { c } } } = \arg \operatorname* { m i n } _ { T _ { \mathrm { { c } } } } \sum _ { g _ { i } \in G } d \big ( g _ { i } , T _ { \mathrm { { c } } } , K \big )
$$

$$
\left( L , T \right) = \underset { \left( L , T \right) } { \arg \operatorname* { m i n } } \sum _ { g _ { i } \in G } \sum _ { T _ { j } \in T } d \left( g _ { i } , T _ { j } , K \right)
$$

其中式（1）用于优化当前相机位姿，式（2）用于优化地图中的关键帧位姿和三维线特征，以上两个优化过程的原理基本相

同，不失一般性，下文以优化当前相机位姿的过程为例阐述数据关联算法。

# 2 基于Patch确认的迭代线特征关联算法

基于Patch确认的迭代线特征关联算法首先基于最近邻线段定义得到候选匹配对，然后利用固定方向的图像块搜索策略剔除错误匹配，之后利用已得到的匹配对优化当前相机位姿，最后将上述过程进行迭代优化。下面对算法的各个步骤进行详细阐述。

# 2.1基于最近邻匹配的初步数据关联

初步关联结果的获取可分为两个步骤：缩小候选关联集合、确定最近邻匹配对象。详细介绍如下：

a）缩小候选关联集合。最近邻匹配中首先将三维线特征投影到当前相机平面得到二维投影线段，然后根据投影线段计算出图像中的候选关联线段集合。为加快匹配速度，本文利用线段的角度和距离属性来缩小候选关联集合。三维直线投影过程采用文献[13]中基于Plucker坐标的投影方法，在获取三维直线的二维投影线段之后，为提高投影线段对应的候选关联线段的搜索速度，将图像中的二维线段被划分为多个集合。本文使用线段角度和线段所在直线到图像中心点的距离两个属性来确定候选匹配集，其中线段角度指的是二维线段所在直线与图像坐标系 $\mathbf { x }$ 轴正方向的夹角。二维线段按线段角度（0-90度）被分为 $n$ 个集合 $l _ { i } ^ { \mathrm { A } } \left( i = 1 , 2 , \cdots , n \right)$ ，每个集合中的最大角度差值为$9 0 / n$ 度；按线段所在直线到图像中心点的距离二维线段被分为$\mathbf { \Sigma } _ { m }$ 个集合 $l _ { i } ^ { \mathrm { p } } ( i = 1 , 2 , \cdots , m )$ ，在图像长宽分别为640 像素和 480像素的数据集中，每个集合中的线段到图像中心的距离最大差值为 $4 0 0 / m$ 像素。对于待匹配三维线段的二维投影线段 $l _ { \scriptscriptstyle L }$ ，首先得到其角度值 $\beta$ 和到图像中心点的距离 $d$ ，由 $\beta$ 、 $d$ 及对应属性差值的阈值 $\beta _ { \mathrm { m a x } } \cdot d _ { \mathrm { m a x } }$ 分别确定候选集合 $l _ { \mathrm { t } } ^ { \mathrm { A } }$ 和 $l _ { \mathrm { t } } ^ { \mathrm { D } }$ ，最终的候选二维线段集合为 $l _ { \mathrm { t } } = l _ { \mathrm { t } } ^ { \mathrm { A } } \cap l _ { \mathrm { t } } ^ { \mathrm { D } }$ 。需要说明的是虽然同时使用了线段的两个属性进行分类，其分类算法的时间复杂度仍为常数阶，如果仅使用单一属性，在同向线段较多和线段分布不均匀的场景中候选匹配集会十分庞大，而这将大大增加后续步骤的计算时间。

b）确定最近邻匹配对象。在得到候选二维线段集合之后，需要在此集合中确定最近邻匹配线段，这一过程中的重点在于最近邻线段的定义。与点特征不同，定义最近邻线特征是一个较为复杂的问题[14]，由于通常使用线段端点到另一线段所在直线的距离来表示线段间距离，而这一数据是多维的，无法直观判断出最近邻线段，需要根据线段自身的属性对最近邻线段进行计算。将三维线段的二维投影线段表示为 $l _ { \scriptscriptstyle L }$ ，图像中提取出的二维线段为 $l _ { 1 }$ 、 $l _ { 2 }$ ，定义二维线段间距离 $d ( l _ { L } , l )$ 如下：

$$
d _ { \mathsf { P } _ { \mathsf { I } } { } _ { L } } \left( { \boldsymbol { l } } _ { L } , { \boldsymbol { l } } \right) = a ^ { \mathrm { { T } } } \cdot { \boldsymbol { l } } _ { L } \bigg / \sqrt { \left( { \boldsymbol { l } } _ { L } ^ { 1 } \right) ^ { 2 } + \left( { \boldsymbol { l } } _ { L } ^ { 2 } \right) ^ { 2 } }
$$

$$
d _ { 1 } \left( l _ { \scriptscriptstyle L } , l \right) = 0 . 5 \left( d _ { { \mathrm { P } } _ { 1 } l _ { \scriptscriptstyle L } } \left( l _ { \scriptscriptstyle L } , l \right) + d _ { { \mathrm { P } } _ { 2 } l _ { \scriptscriptstyle L } } \left( l _ { \scriptscriptstyle L } , l \right) \right)
$$

$$
d _ { 2 } \left( l _ { L } , l \right) = 0 . 5 \left( d _ { \mathrm { p _ { 1 } } } \left( l _ { L } , l \right) + d _ { \mathrm { p _ { 2 } } } \left( l _ { L } , l \right) \right)
$$

$$
d ( l _ { _ { L } } , l ) = ( d _ { _ { 1 } } ( l _ { _ { L } } , l ) + d _ { _ { 2 } } ( l _ { _ { L } } , l ) ) { \frac { l _ { _ { \mathrm { A } } } ^ { \ast } } { l ^ { \ast } } }
$$

其中: $d _ { \mathrm { P } _ { 1 } l _ { L } } \left( l _ { L } , l \right)$ 和 $d _ { \mathrm { P } _ { 2 } l _ { L } } \left( l _ { L } , l \right)$ 表示线段 $\mathbf { \xi } _ { l }$ 的两个端点到投影线段$l _ { \scriptscriptstyle L }$ 所在直线的距离，采用与文献[8]中相同的计算方法，以$d _ { \mathrm { P } _ { 1 } l _ { L } } \left( l _ { L } , l \right)$ 为例，式（4）中 $a$ 为线段 $l$ 的一个端点（用齐次坐标表示）， $l _ { \scriptscriptstyle L }$ 所在直线表示为 $\left( l _ { L } ^ { 1 } , l _ { L } ^ { 2 } , l _ { L } ^ { 3 } \right) ^ { \mathrm { T } } \colon d _ { \mathrm { P } _ { 1 } } \left( l _ { L } , l \right)$ 和 $d _ { \mathrm { P } _ { 2 } } \left( l _ { L } , l \right)$ 表示线段 $\mathbf { \xi } _ { l }$ 和线段 $l _ { \scriptscriptstyle L }$ 间对应端点的距离， $l _ { \mathrm { A } } ^ { \ast }$ 表示当前图像平面内全部二维线段的平均长度， $\boldsymbol { l } ^ { * }$ 表示线段 $\mathbf { \Phi } _ { l }$ 的长度， $l _ { \mathrm { A } } ^ { \ast } / l ^ { \ast }$ 参数可以使在位姿优化过程中贡献更大的长线段更容易被匹配。本文将线段的临近属性定义为两类：一类是共线属性，用端点到直线的距离，即 $d _ { \scriptscriptstyle 1 } ( l _ { \scriptscriptstyle L } , l )$ 量化表示这一属性；一类是位置重合属性，表示为对应端点间的距离 $d _ { 2 } \big ( l _ { L } , l \big )$ 。典型的线段距离定义一般仅以 $d _ { \scriptscriptstyle 1 } ( l _ { \scriptscriptstyle L } , l )$ 的形式出现，在线段密集的场景中传统定义方法无法分辨共线或近似共线的线段，而仅使用端点间距离又无法鲁棒地处理线段端点不稳定的情况。

在得到候选二维线段集合之后，对集合中的每一条二维线段 $\mathbf { \xi } _ { l }$ 分别计算其与三维线特征投影线段的距离 $d \left( l _ { L } , l \right)$ ，选取距离最小的二维线段，如果其最小距离小于阈值 $d _ { \operatorname* { m a x } } ^ { L }$ ，则将此二维线段作为三维线特征 $L$ 的关联特征。在实际操作中，本文采用的参数为 $n = 1 8 \ \cdot \ m = 2 0 \ \cdot \ \beta _ { \mathrm { m a x } } = 6 \ \cdot \ d _ { \mathrm { m a x } } = 4 0 \ \cdot \ d _ { \mathrm { m a x } } ^ { L } = 9 0$ 。

# 2.2基于线段端点Patch的错误关联剔除

由于SLAM系统中三维线段和当前帧预测位姿的误差，最近邻匹配算法得到的匹配对中不可避免地存在错误关联，这些错误关联将严重影响当前帧位姿计算结果的精度，本文采用基于线段端点图像Patch的错误匹配剔除策略来处理这些错误关联。

Patch为二维点附近的一个正方形图像块，使用线段上端点或中点附近的 Patch 来进行线段匹配是一个较为常用的做法[8,15]，这类方法可以简述为如下步骤（以线段端点为例)：

a)获取三维线特征对应的Patch，此处一般使用已经关联到该三维线特征的二维线段端点附近的图像Patch;

b)将三维线特征投影到当前图像平面，在候选二维线段集合中进行搜索，计算每一条候选二维线段的端点Patch与三维线特征对应Patch之间的ZMSSD（零均值像素灰度差平方和）值，将ZMSSD值最小且小于阈值的二维线段关联到该三维线段。

基于端点附近图像Patch的匹配方案利用了线段端点处的图像相似性约束，但由于单目线特征SLAM中相机预测位姿误差相对较大，而且线段端点可重复性较差，此方案能够得到的关联对过少，在线段较为密集的场景中，此方案的计算量会明显增加。

本文将基于线段端点Patch的匹配方法用于最近邻匹配结果的错误剔除上。具体步骤为：

a)获取三维线特征对应Patch;

b)在三维线特征关联的二维线段端点的“松弛范围”（“松弛范围”的定义请见下文）内沿与“松弛范围”共线的方向进行Patch搜索，如果搜索到的图像Patch与原三维线特征对应Patch间的ZMSSD值小于阈值，则确认此关联正确，否则剔除掉此错误关联。

在获取三维线特征对应Patch 的过程中，首先需要选择三维线特征对应的关键帧 $F _ { L } ^ { b }$ ，将与当前帧中三维线特征 $\mathbf { \Omega } _ { L }$ 的观测角最相近的关键帧作为最佳观测关键帧 $F _ { L } ^ { b }$ 。其中观测角定义为当前帧相机主轴与过相机光心和三维直线的平面的夹角，如图1。其中 $L _ { z }$ 为相机主轴，即过光心 $c$ 垂直于图像平面的直线， $\pi _ { \boldsymbol { L } }$ 为过光心 $c$ 和三维直线 $\mathbf { \Omega } _ { L }$ 的平面，观测角为 $L _ { z }$ 与 $\pi _ { L }$ 的夹角 $\alpha$ 。取得关键帧之后从其中 $L$ 对应的二维线段 $l _ { \scriptscriptstyle L }$ 的端点处取得两个 $8 ^ { * } 8$ 的图像块，后续处理过程则与PTAM[1]中的Patch提取过程完全一致，其实现细节可参考文献[1]。

![](images/d78578c3a5e5dc64e6ede9db3b8405ad62ffd8ad3548809b6590f94f2c465dde.jpg)  
图1三维直线在当前帧中的观测角

Patch搜索阶段中计算候选二维线段端点的图像Patch与投影线段端点图像Patch间的ZMSSD值，当ZMSSD值小于阈值时，关联被判定为正确。但由于线段端点不稳定，这种方法可能会导致大量正确关联被剔除。为解决这一问题，本文定义了线段端点的“松弛范围”，“松弛范围”为以原线段端点为中心、与原线段共线的一段长度为S个像素的线段，如图2，其中 $F _ { 2 }$ 帧中 $a _ { 2 } b _ { 2 }$ 为原线段，端点 $a _ { 2 }$ 的“松弛范围”为线段 $a _ { 3 } b _ { 4 }$ ，其长度S定义如下：

$$
S = \left\{ { \begin{array} { l l } { 1 0 \qquad } & { l _ { L } ^ { \ast } \geq 2 0 } \\ { l _ { L } ^ { \ast } / 2 \qquad } & { l _ { L } ^ { \ast } < 2 0 } \end{array} } \right.
$$

其中: $\boldsymbol { l } _ { \boldsymbol { L } } ^ { * }$ 为原二维线段的长度，S 的最大值为10 个像素，当 $\boldsymbol { l } _ { \boldsymbol { L } } ^ { * }$ 过小时，S的值随 $\boldsymbol { l } _ { \boldsymbol { L } } ^ { * }$ 而变换。“松弛范围”使得错误剔除算法更为鲁棒，当线段端点的误差未超出“松弛范围”时，正确的关联对不会被错误剔除。

![](images/c9325e62d9684b51a1048ab1ea2c93d8cb5698fab9c4c11880cb093bc3f297ab.jpg)  
Fig.1Viewing angle of 3D lines in current frame   
图2松弛范围内的端点Patch 确认  
Fig.2Determination of endpoint-patch in relaxation range

# 2.3 迭代关联算法

迭代关联算法中使用上述最近邻匹配方法得到候选匹配对，然后采用基于线段端点Patch的错误关联剔除算法去除错误关联对，利用得到的关联对优化当前帧位姿，最后将以上过程迭代直至优化过程中的匹配错误率小于阈值。

在位姿优化过程中，目标函数表述为式（1)，为避免线段端点不稳定对优化过程带来的不利影响，目标函数中的距离函数 $d ( g _ { i } , T _ { \mathrm { c } } , K )$ 采用式（3）中描述的线段端点到直线的距离，本文使用 $\mathrm { g } 2 \mathrm { o } ^ { [ 1 6 ] }$ 中的LM算法来实现对相机位姿的优化。迭代运算结束的判定标准为相机位姿优化过程中的内点比例大于最近关键帧中内点比例的 $70 \%$ ，其中内点定义为位姿优化后距离小于阈值的关联对，同时考虑到SLAM系统的实时性，最大迭代次数定义为3次。

基于Patch确认的迭代线特征关联算法如下所示。

算法1基于Patch确认的迭代线特征关联算法 输入：二维线段集合 $l { = } ( l I , l 2 , . . . . , l n )$ ，三维线段集合 $\scriptstyle L = ( L ^ { \_ l } , L ^ { 2 } , \ldots , L m )$ ，当 前相机位姿P

输出：三维线段与二维线段匹配对G

1: function IterativeLineAssociation $( l , L , { \tt P } )$ （204号   
2: for $\mathrm { i } = 0  3$ do   
3: $\mathrm { G } \gets \mathrm { L i n e A s s o c i a t i o n } ( l , L , \mathrm { P } )$   
4: $\mathrm { \Delta P \gets }$ OptimizePose(P,G)/按照公式1优化相机位姿   
5: if Inliers(P.G) then /根据内点数目判断是否结束循环   
6: break   
7: end for   
8: return G   
9: end function   
10:   
11: function LineAssociation $( l , L , { \tt P } )$ （204   
12: for $\dot { \bf { i } } = 0  \mathrm { { m } }$ do   
13: pt ← GetPatch(L[i]) //获取三维线段端点Patch   
14: $l \mathrm { p } \gets$ Project3DLine(l[i],P）//将三维线段投影到图像平面   
15: $l \mathrm { s } \gets$ Get2DLineSet(lp,l）//获取缩小后的候选线段集合   
16: fNear $$ false   
17: $\mathbf { f o r } \mathrm { j } = 0 \longrightarrow \mathrm { l e n } ( { l } \mathrm { s } ) \mathbf { d o }$   
18: $\mathsf { d } \gets \mathrm { D i s } ( l \mathrm { s } [ \mathsf { j } ] , l \mathsf { p } )$ （204号 //按照公式6计算线段间距离   
19: if $\mathrm { ~ d ~ } <$ Dth then //距离满足阈值   
20: fNear $$ true   
21: $l \mathrm { b } \gets l \mathrm { s } [ \mathrm { j } ]$   
22: $\mathrm { { D t h }  \mathrm { { d } } }$ （20   
23: end if   
24: end for   
25: if fNear then /找到最近邻线段   
26: fPatch $$ MatchPatch $( \mathrm { p t } , l \mathrm { b } )$ //按照 2.2 节进行Patch 确认   
27: if fPatch then   
28: 1 $\mathsf { s s u l t } \gets ( L [ \mathrm { i l } , l \mathbf { b } )$ （204号   
29: end if   
30: end for   
31 return result   
32: end function

# 3 实验及结果分析

# 3.1 实验设计

为验证本文所提出的迭代线特征关联方法的准确性和高效性，与同类算法进行了对比，并在公开数据集上进行了相关实验。

本文采用如图3所示的实验方案。实验所用SLAM系统采用与ORB-SLAM[2]相同的系统框架，将其中的点特征操作替换为了对应的线特征操作，并去除了闭环检测模块，使用速度较快的 EDLine[17]算法提取图像中的二维线段。同时对原系统中跟踪线程的局部地图跟踪模块做了改动，并在此模块后增加了关联误差评价模块。局部地图跟踪模块中同时使用了三种线特征关联算法，将待处理的数据同时输入到三种算法中，算法分别如下：

算法1为本文提出的数据关联算法;

算法2为基于最近邻线段的迭代匹配算法，即在本文算法的基础上去除Patch匹配确认的步骤，在文献[5]中采用；

算法3为基于LBD描述子的关联算法，在文献[10]中采用。

![](images/bc612d1a67b887b1fc8b771baae97984ac817f9057b12d85780df3748a5bf23e.jpg)  
图3数据关联算法对比实验设计  
Fig.3Design of contrastive experiment between different data association algorithms

由于SLAM系统内三维地图是实时建立和更新的，所以数据关联算法的输入数据中不可避免地存在误差项，关联误差评价模块很难把这部分误差项完全剔除。为了准确评价SLAM应用中数据关联算法的准确性和效率，本文实验方案中三种算法在每一帧的输入数据完全相同，关联误差评价模块分别对三种线特征关联算法的输出数据使用相同的方法进行评价。本文采用文献[18]中的参数作为评价指标，包括匹配线段长度比率M、平均投影误差G和最小角度区内匹配线段长度之和L。具体计算方法如下：

$$
M = \frac { \sum _ { i , j } l _ { i j } } { \operatorname* { m i n } ( \sum _ { i } \mathrm { I } ^ { i } , \sum _ { j } \hat { \mathrm { I } } ^ { j } ) }
$$

其中: $l _ { i j }$ 表示关联算法获得的关联对中二维线段的长度，I表示图像中提取的二维线段的长度， $\hat { \mathrm { ~ I ~ } }$ 表示可以投影到当前帧的三维线段在图像内的二维投影线段的长度。匹配线段长度比率M用于描述算法是否能够获得足够多的匹配对。

$$
G = 0 . 5 \frac { \sum _ { i , j } \big ( d _ { \mathrm { p } _ { 1 } l _ { L } } \left( l _ { L } ^ { i } , l ^ { j } \right) + d _ { \mathrm { p } _ { 2 } l _ { L } } \left( l _ { L } ^ { i } , l ^ { j } \right) \big ) l _ { i j } } { \sum _ { i j } l _ { i j } }
$$

平均投影误差G表述了线特征关联算法所获取的关联对的平均 $L$ 投影误差。

$$
L = l _ { 1 } + l _ { 2 } + l _ { 3 }
$$

其中: $l _ { 1 } \cdot l _ { 2 } \cdot l _ { 3 }$ 分别表示关联对中不同角度区间内二维线段的长度之和。本文将二维线段的角度限定为0\~180度之间，按照文献中类似的处理方法将角度分为4个区间：表示水平方向线段的区间，角度范围包括 $( 0 ^ { \mathrm { o } } , 2 2 . 5 ^ { \mathrm { o } } )$ 和（ $1 5 7 . 5 ^ { \mathrm { o } } , 1 8 0 ^ { \mathrm { o } } \rangle$ ；表示垂直方向线段的区间，角度范围为 $( 6 7 . 5 ^ { \circ } , 1 1 2 . 5 ^ { \circ } )$ ；其余方向则分为两个区间（ $( 2 2 . 5 ^ { \mathrm { o } } , 6 7 . 5 ^ { \mathrm { o } } )$ 和（ $1 1 2 . 5 ^ { \circ } , 1 5 7 . 5 ^ { \circ } ;$ ，每个区间内的已关联的线段长度之和表示为 $l _ { i } ( i = 1 , 2 , 3 , 4 )$ ，去除其中最长的$l _ { 4 }$ ，将剩下的3项相加得到指标 $\mathbf { \Omega } _ { L }$ ，用于表示关联算法在处理不同方向线段时的性能。

文献[18]中为以上三个参数分别设置了相应阈值，当有任意一项指标无法满足阈值要求时判断此帧数据关联失败，本文采用相同的方法来计算关联错误的帧率。由于文献[18]是基于双目摄像头的系统，系统中可以直接得到三维线段的深度信息，而本文的单目系统中无法直接获取深度信息，三维线段的误差相对较大，这使得数据关联算法的输入数据中存在较大误差，因此本文中G和M两项评价指标采用了更宽松的阈值设置，具体为 $L _ { \mathrm { m i n } } = 1 0 0 p x$ 、 $G _ { \mathrm { m a x } } = 4 . 5$ 和 $M _ { \mathrm { m i n } } = 0 . 1$ 。

除以上指标之外，本文还对不同数据关联算法的在每帧的运算时间均值和得到的关联对数目均值进行了统计，同时为了进一步对算法进行分析，实验中记录了参数G相对于每一帧的平均值。

# 3.2 实验结果及分析

实验平台中CPU型号为Inteli7-3700，3.4GHz，4G内存。实验数据采用TUMRGBD数据集[19]，本文选取了数据集中的四个场景作为数据关联算法的实验数据，见图4，其中从上到下，从左至右分别为fr2_xyz、fr3_long_office、fr3_str_tex_far、fr2_rpy场景中的典型图像帧，按照此顺序将四个场景分别命名为场景1-4。

![](images/3e0ceac21c5a9807fc3df4dc3878310d5b74325288e2c8cc8963315a4527367b.jpg)  
图4TUMRGB-D数据集中的典型图像帧  
Fig.4Typical frame samples in TUMRGB-D dataset   
Fig.5Comparison of effect of different data association algorithms

实验中，分别将数据集中的图像输入到单目线特征SLAM系统中，依照3.1节中介绍的实验设计方案，在局部地图跟踪模块中依次运行三种线特征关联算法，其中输入数据为当前局部地图中的三维线段集合以及当前帧内二维线段集合，输出数据为三维线特征与二维线段的匹配对，记录每种数据关联算法的四项指标。

![](images/af08614a9c683802c0751484930708a958e4d418fc64640068efdce9bc945bd2.jpg)  
图5不同数据关联算法的效果对比

图5为实验运行时的系统截图，其中A、B、C、D分别为输入图像、算法3、算法2和算法1得到的关联结果。关联结果图像中粗实线为关联对距离在一定阈值以内的三维线段的二维投影线段，视为正确关联；粗虚线为关联对距离超出阈值的二维投影线段，视为错误关联；细实线为图像中提取出的二维线段。图像B、C中的黑色箭头指明了重点分析区域。

图像A来自于数据集场景2，由于算法3仅基于线段描述子LBD，当地图中三维线段的优化结果存在误差时，算法3难以剔除这样的误差关联项，如图像B中箭头所指的二维投影线段为地图中误差较大的三维线段投影所得，算法3未能将其剔除。而算法2中仅根据投影线段的距离来检测关联对，当线段分布密集时会得到较多错误关联对，图像C中箭头指向处线段较为密集，此时算法2得到的错误关联对较多，而在本文提出的算法中则可以使用Patch确认来剔除这些错误关联。

表1线特征关联算法实验结果  
Table 1Experimental result of data association algorithms   

<html><body><table><tr><td rowspan="2">数据集场景（1-4)</td><td colspan="3">线特征关联算法</td></tr><tr><td>算法1</td><td>算法2</td><td>算法3</td></tr><tr><td rowspan="4">错误关联帧比例 1</td><td>0.245%</td><td>1.09%</td><td>4.52%</td></tr><tr><td>平均关联对数目 84</td><td>96</td><td>48</td></tr><tr><td>平均算法时间（ms）</td><td>11.039 6.2899</td><td>12.316</td></tr><tr><td>平均投影误差G 1.360</td><td>2.083</td><td>1.736</td></tr><tr><td rowspan="4">2</td><td>错误关联帧比例 2.29%</td><td>12.94%</td><td>6.36%</td></tr><tr><td>平均关联对数目</td><td>71 76</td><td>46</td></tr><tr><td>平均算法时间（ms）</td><td>16.362</td><td>7.641 18.108</td></tr><tr><td>平均投影误差G</td><td>1.866 3.010</td><td>2.253</td></tr><tr><td rowspan="5">3</td><td>错误关联帧比例</td><td>1.95% 7.07%</td><td>9.24%</td></tr><tr><td>平均关联对数目</td><td>126 126</td><td>97</td></tr><tr><td>平均算法时间(ms)</td><td>25.514 10.094</td><td>18.148</td></tr><tr><td>平均投影误差G</td><td>2.159</td><td>2.908 2.749</td></tr><tr><td>错误关联帧比例</td><td>0.52% 2.17%</td><td>2.42%</td></tr><tr><td rowspan="4">4</td><td>平均关联对数目</td><td>64</td><td>71</td><td>58</td></tr><tr><td>平均算法时间（ms）</td><td>9.10</td><td>5.151</td><td>13.35</td></tr><tr><td>平均投影误差G</td><td>1.139</td><td></td><td></td></tr><tr><td></td><td></td><td>1.875</td><td>1.830</td></tr></table></body></html>

表1为3.1节中介绍的关联误差评价模块对各算法的输出结果记录，其中错误关联帧比例为G、M和L三项评价指标中任意一项超出阈值的帧占全部帧的比例，平均投影误差为评价指标G相对于每一帧的平均值。从错误关联帧比例和平均投影误差G来看，本文算法在四个数据集场景上的运行结果均为最低，显著提高了关联算法的正确率；从关联对数目来看，本文算法的关联对数目稍小于算法2，但其中错误关联对数目最少，而过多的错误关联对会明显降低SLAM系统的鲁棒性；从算法时间上来看，本文算法在四个实验场景中每帧的运行时间均在30ms以内，其中二维线特征数目最多的场景3和包含闭环的场景2中的算法运行时间较长，场景2中相机的闭环运动使线特征数据关联算法的输入数据中增加了很多被遮挡的三维线特征但由于采用了2.1节所描述的缩小候选关联集合的策略和2.3节中的迭代优化方法，当输入的二维线特征或三维线特征数量增多时，算法规模并不会急剧扩大，算法仍然能够保证实时运行。其他算法中算法2速度最快，但其错误关联帧比例在不同运行场景下变化较大，难以处理线段密集的场景；算法3是较为常用的基于线段的LBD描述子的关联方法，其错误关联帧比例在不同场景中较为稳定，但此算法耗时较长、得到的关联对数目最少，由之前的单帧运行情况来看，该算法不易处理输入数据中的误差项和纹理稀疏的线段。

为了分析不同线特征关联算法对SLAM系统性能的影响，本文在同一套 SLAM系统中分别采用基于算法1、算法2和算法3的局部地图跟踪模块进行了实验。由于算法2在场景2中的错误关联帧比例过高，仅对数据集场景1、3、4进行实验，SLAM系统得到的相机位姿的相对误差见表1。

表2不同线特征关联算法的相对位姿误差  
Table 2Relative pose error of different data association algorithms   

<html><body><table><tr><td rowspan="2">数据集场景</td><td colspan="3">线特征关联算法</td></tr><tr><td>算法1</td><td>算法2</td><td>算法3</td></tr><tr><td rowspan="3">RMSE (m/s) 1</td><td>0.0304</td><td>0.0436</td><td>0.0484</td></tr><tr><td>中值(m/s) 0.0252</td><td>0.0371</td><td>0.0413</td></tr><tr><td>RMSE (deg/s) 0.5587</td><td>0.8092</td><td>0.8529</td></tr><tr><td rowspan="6">3</td><td>中值(deg/s)</td><td>0.3599</td><td>0.3876</td><td>0.4413</td></tr><tr><td>RMSE (m/s)</td><td>0.1253</td><td>0.1689</td><td>0.1403</td></tr><tr><td>中值(m/s)</td><td>0.1218</td><td>0.1676</td><td>0.1342</td></tr><tr><td>RMSE (deg/s)</td><td>1.5433</td><td>3.7659</td><td>1.9632</td></tr><tr><td>中值(deg/s)</td><td>1.1089</td><td>2.4806</td><td>1.3593</td></tr><tr><td>RMSE (m/s)</td><td>0.0158</td><td>0.0176</td><td>0.0267</td></tr><tr><td>中值(m/s) 4</td><td>0.0112</td><td>0.0128</td><td>0.0118</td></tr><tr><td>RMSE (deg/s)</td><td>1.3184</td><td>1.7336</td><td>1.160</td></tr><tr><td>中值(deg/s)</td><td>0.4179</td><td>0.7874</td><td>0.4864</td></tr></table></body></html>

表2中的位姿轨迹相对误差表明本文提出的线特征关联算

法提高了单目线特征SLAM系统的整体性能，相对于仅使用线特征几何关系的迭代最近邻关联算法和仅使用线段描述子的基于LBD的关联算法，本文提出的算法具有更高的稳定性和准确性。

# 4 结束语

线特征的数据关联是单目线特征SLAM 面临的一个重要问题。近年来点线结合的单目SLAM系统因其准确性和鲁棒性的优势引起了较多学者的注意[10,15,20]，但这些与线特征相关的基础问题限制了线特征优势的发挥。本文针对难度较大的单目线特征SLAM系统，提出了一种新的线特征数据关联算法。本文提出的算法融合了最近邻匹配和基于线段端点图像Patch 的错误关联剔除策略，使用迭代的处理方式。在公共数据集上的实验表明，本文提出的迭代线特征关联算法在关联准确率和关联对数目上均达到了较好的性能要求。后续工作中将进一步研究点特征和线特征的联合关联算法，研究提升点线融合SLAM性能的方法。

# 参考文献：

[1]Klein G,Murray D.Parallel tracking and mapping for small AR workspaces [C]//Proc of IEEE and ACM International Symposium on Mixed and Augmented Reality. Piscataway, NJ: IEEE Press,2007: 225-234.   
[2]Mur-Artal R,Montiel JM M, Tardós JD. ORB-SLAM: a versatile and accurate monocular SLAM system [J].IEEE Trans on Robotics,2015,31 (5): 1147-1163.   
[3]Perdices E,López LM,Canas JM.LineSLAM: visual real time localization using lines and UKF[C]//Proc of the 1st Iberian Robotics Conference.2014: 663-678.   
[4]Zhang Guoxuan, Suh IH. SoF-SLAM: segments-on-floor-based monocular SLAM[C]// Proc of IEEE//RSJ International Conference on Intelligent Robots and Systems.Piscataway,NJ:IEEE Press,2010:2083-2088.   
[5]Zhang Lilian,Koch R.Hand-held monocular SLAM based on line segments [C]// Proc of Machine Vision and Image Processing Conference.Piscataway, NJ: IEEE Press,2011: 7-14.   
[6]武涛，孙凤池，苑晶,etal.一种基于线段特征的室内环境主动 SLAM 方法[J].机器人,2009,31(2):166-70.(Wu Tao,Sun Fengchi,Yuan Jin, et al.An active SLAM approach based on line segment feature in indoor environment [J].Robot,2009,31 (2): 166-70.)   
[7]Zhang Guoxuan,Suh IH.A vertical and floor line-based monocular SLAM system for corridor environments [J].International Journal of Control Automation & Systems,2012,10(3): 547-557.   
[8] Zhou Huizhong, Zou Danping,Pei Ling,et al. StructSLAM: Visual SLAM With Building Structure Lines [J]. IEEE Trans on Vehicular Technology, 2015,64(4): 1364-1375.   
[9]Smith P,Reid I,Davison A. Real-Time Monocular SLAM with Straight Lines [C]//Proc of British Machine Vision Conference.Berlin: Springer,

2006:17-26.

[10]Pumarola A,Vakhitov A,Agudo A,et al.PL-SLAM:Real-time monocular visual SLAM with points and lines [C]// Proc of IEEE International Conference on Robotics and Automation.Piscataway,NJ: IEEE Press,2017: 4503-4508.   
[11] Wang Zhiheng,Wu Fuchao,Hu Zhanyi.MSLD:a robust descriptor for line matching[J].Pattern Recognition,2009,42(5):941-53.   
[12] Zhang Lilian,Koch R.An efficient and robust line segment matching approach based on LBD descriptor and pairwise geometric consistency[J]. Journal of Visual Communication & Image Representation,2013,24(7): 794-805.   
[13] Zhang Lilian,Koch R. Structure and motion from line correspondences: Representation,projection,initialization and sparse bundle adjustment [J]. Journal of Visual Communication & Image Representation,2014,25(5): 904-915.   
[14] Bartoli A,Sturm P. The 3D line motion matrix and alignment of line reconstructions [J]. International Journal of Computer Vision,2oo4,57(3): 159-178.   
[15] Gomez-Ojeda R,Briales J,Gonzalez-Jimenez J.PL-SVO:semi-direct monocular visual odometry by combining points and line segments [C]// Proc of IEEE//RSJ International Conference on Intelligent Robots and Systems.Piscataway,NJ:IEEE Press,2016:4211-4216.   
[16]Kimmerle R,Grisetti G,Strasdat H,et al.G2o:a general framework for graph optimization [C]//Proc of IEEE International Conference on Robotics and Automation.Piscataway, NJ:IEEE Press,2011:3607-3613.   
[17]Akinlar C,Topal C.EDLines:A real-time line segment detector with a false detection control[J].Pattern Recognition Letters,2011,32(13): 1633-42.   
[18]Witt J,Weltin U.Robust stereo visual odometry using iterative closest multiple lines [C]// Proc of IEEE//RSJ International Conference on Intelligent Robots and Systems.Piscataway,NJ:IEEE Press,2013:4164- 4171.   
[19]Sturm J,Engelhard N,Endres F,et al.A benchmark for the evaluation of RGB-D SLAM systems [C]//Proc of IEEE//RSJ International Conference on IntelligentRobots and Systems.Piscataway,NJ:IEEE Press,2012:573- 580.   
[20] Yang Shichao,Scherer S.Direct monocular odometry using points and lines [C]//Proc of IEEE International Conference on Robotics and Automation. Piscataway,NJ:IEEE Press,2017:3871-3877.