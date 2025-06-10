# 融合IMU去除运动模糊的改进光流匹配算法

栾小珍a，魏国亮ʰ，蔡洁a(上海理工大学 a.理学院;b.管理学院，上海 200093)

摘要：为进一步提高视觉 SLAM中的光流匹配精度和速度,提出一种融合惯性测量单元(InertialMeasurement Unit，IMU)去除运动模糊的改进光流匹配算法。该算法首先利用IMU运动信息计算的点扩散函数去除运动模糊，提高特征点匹配率；其次在LK(Lucas-Kanade)光流的基础上，引入梯度误差，并使用图像梯度L1范数作为正则项模拟稀疏噪声，构建代价函数；然后利用IMU预测特征点位置作为该算法初始值，并加入BB(Barzilar-Borwein)步长改进原有的高斯牛顿算法，提高计算速度。实验表明，通过两帧之间比较，该算法的效率和精度均优于LK光流法；然后将该算法集成到VINS-Mono框架，在数据集 EuRoC上，结果显示该算法提高了原有框架的定位精度和鲁棒性。

关键词：光流法；前端视觉里程计；运动模糊；多传感器融合 中图分类号：TP242 doi: 10.19734/j.issn.1001-3695.2022.02.0075

Feature tracking algorithm for removing motion blur by improving optical flow incorporating IMU

Luan Xiaozhena, Wei Guoliangb†, Cai Jiea (a.CollgeofSience,b.BusinessSchool,UniversityofanghaiforScience&Technologyhanghaio,China)

Abstract: Inorder to improve the accuracyand eficiencyof the feature point matching,this paper proposed a novel feature point matchingalgorithm in termsof visionand inertial measurementunit (IMU)fusion.Firstly,the algorithmcalculated the point diffusion function using the motioninformationofIMU to remove motion blur,and improved the feature point matching rate.Secondly,basedonLK(Lucas-Kanade)opticalflowmethod,thispaperintroduced gradient eroranduses L1parametric to simulate sparse noise.Furthermore,thefeature point positionbyusing IMUis theinitial valueofthealgorithm,and then this paperused BB(Barzilar-Borwein)step to improve the eficiencyofthe algorithm.Finally,thecomparison experiments showthattheeffciencyandaccuracyoftealgorithmare beterthantheLKopticalflow method.Especiall,thealgorithm improves the localization accuracy and robustness of the VINS-Mono framework on the dataset EuRoC.

Key words: optical flow; visual odometry; motion blur;multi-sensor fusion

# 0 引言

近年来，视觉同时定位与建图(VisualSimultaneousLocalization And Mapping，V-SLAM)[1]在机器人领域有着重要的作用，如物流配送、虚拟现实(VirtualReality，VR)[2]、智能家居等。虽然单目相机成本较低、使用方便，但是仅仅依靠相机，难以估计环境的尺度。因此在V-SLAM中，为了解决尺度不可观问题，众多学者更倾向于多传感器融合技术。由于惯性测量单元(InertialMeasurementUnit，IMU)能够在隔绝外部环境的影响下测量本体的角速度和加速度，从而使单目视觉的公制尺度可观测，并提供鲁棒和准确的帧间运动估计，因此视觉和IMU 融合的SLAM技术(VI-SLAM)异军突起[3-5]。VI-SLAM 框架主要分为前端里程计、后端优化、回环检测和建图。前端里程计作为首要步骤，在整个系统中显得尤其重要。在前端里程计中，不仅需要进行IMU预积分，而且需要对相机传入的图片进行特征点提取和匹配，进而根据匹配信息计算相邻两帧之间机器人的运动，并构建特征点的局部3D位置[6]。一旦发生误匹配[7]，会导致估计不准确，因此，特征点提取与匹配也是前端里程计中的重要一环。

特征点提取与匹配主要分为特征点法[8.9]、光流法[10]和直接法[]。特征点法在计算关键点、描述子，以及匹配描述子时计算量过大，而光流法和直接法弥补了以上缺陷，光流法只计算关键点，不计算描述子，通过两帧之间的光度不变假设，直接最小化光度误差并进行迭代匹配，本文重点研究光流法。

在光流法中目前主要存在以下两个问题，一方面，若物体运动过快，则在相机曝光期间，景物和摄像机之间存在相对运动，会导致像素重叠，出现图像模糊现象，称为运动模糊。而光流法对光度稳定和图像的连续有较强依赖，当不满足以上假设的时候，容易找不到跟踪点，更糟糕的情况是追踪到错误的特征点。另一方面，在光流法中使用非线性优化方法进行最小化光度误差迭代匹配的过程中，首先，非线性算法的最优值对初值有很强的依赖性，如果没有初值则需要进行全局搜索，计算量较大，且容易造成误匹配；其次，传统高斯牛顿方法的步长是固定步长或者直接由线搜索算法给出，如果步长取的太大，一开始会很快向最优解逼近，在收敛的最后阶段，容易跳过最优解；而步长取的太小，则导致收敛速度变慢。因此，去除运动模糊和选取非线性优化算法的初始值、步长是本文研究的两个问题。

基于以上问题，本文提出了一种融合IMU去除运动模糊的光流匹配算法。该算法通过融合IMU运动信息，计算点扩散函数去除运动模糊，之后再次融合IMU信息预测特征点位置，为光流跟踪提供初值，进而提高特征点提取与匹配的性能。最后，将该算法集成到了完整VI-SLAM框架中。

在VI-SLAM 框架特征点提取与检测方面，TongQin 等提出的VINS-Mono[12]前端使用光流法提取关键点，并使用多层金字塔LK(Lucas-Kanade)进行跟踪，虽然整体框架是基于IMU和视觉传感器融合，但在关键点提取和跟踪中，并未将IMU信息与视觉信息融合。QiGuan等提出的IFPT特征点匹配算法将特征点法与IMU进行融合[13]，通过IMU的位置和旋转方向预测下一帧关键点的位置，并以其为圆心，进行描述子局部搜索与匹配。OKVIS(Open Keyframe-based Visual-InertialSLAM)[14]的3D-2D的匹配中，利用IMU预测的位姿筛选当前帧可见的特征点，去除掉当前帧已经追踪不到的特征点，节省暴力匹配时间。OKVIS和IFPT共同点是将特征点法与IMU融合，即基于预积分理论进行预测，为待匹配的每个特征点提供新图像中的可能位置，进而完成前端特征点提取与匹配。不同点是IFPT 得到可能位置之后进行局部搜索，而OKVIS筛选去除当前帧已经看不到的点，然后进行全局暴力匹配。

本文提出的算法和之前相关工作有所区别，首先从算法本身比较：a）之前的工作[15]直接设置平移信息 $t = 0$ ，而提出的算法充分利用了IMU的信息，加入了加速度计得到的 $t$ ，实验结果表明融合平移信息后，IMU预测的特征点位置更加准确；b)之前的工作未将速度信息充分利用，而提出的算法利用IMU预积分得到的运动信息，计算点扩散函数，加入了运动模糊复原步骤，减少运动模糊导致匹配特征点失败现象；c）在非线性优化方法中，加入BB(Barzilar-Borwein)可变步长进行搜索，使步长大小可以自适应损失函数。其次，从框架上比较，之前的工作[15]把偏置当作状态向量的一部分去优化，并且在初始化前，偏置求解不准确的情况下，仍然预测相机位姿，导致视觉里程计的误差一直传递下去，更糟糕的是若系统中没有闭环检测，很难消除视觉里程计产生的累计误差。本文提出的算法利用IMU预测的时机是在系统初始化后，此时偏置信息已经求出，减小了累计误差。

# 1 系统框架

该算法在VINS-Mono 框架前端算法基础上进行研究。原VINS-Mono 框架前端算法使用 ShiTomasi[16,17]算法检测角点，LK光流法跟踪匹配。在运动幅度较大，光照变化剧烈情况下，匹配误差较大。

为解决以上问题，提高定位精度，本文对VINS-Mono前端算法进行改进。具体实施方案如下：首先在初始化前，仍通过传统光流法进行特征点提取，初始化完成之后，将得到的IMU加速度计和角速度计偏置代入到预积分中，融合预积分预测得到的速度、位置、旋转方向信息，发送到前端，判断速度是否大于阈值，如果大于阈值说明运动过快，则根据运动信息进一步对图像进行非盲复原[18,19]。如果上一步完成或者速度小于阈值，说明运动幅度较小，为满足实时性，则不进行图像复原操作。直接将IMU预测得到的位置、旋转方向与视觉信息融合，即将恢复之后的点投影到下一帧图像上，提供给光流追踪中高斯牛顿算法一个初始值，确定光流追踪匹配的局部搜索位置。该算法集成到框架上，其流程如图1所示。

# 2 预积分模型预测特征点位置

本节首先对常用到的一些符号进行定义。()表示传感器测量值， $R$ 表示 $3 \times 3$ 的旋转矩阵， $q$ 表示旋转的四元数表示，$t$ 表示3维平移向量， $\scriptstyle { T = [ R | t ] }$ 表示姿态的转换矩阵，包括旋转矩阵和平移向量。 $\left( \cdot \right) _ { I }$ 为IMU坐标系， $( \cdot ) _ { c }$ 为相机坐标系，特别地，令相机的第一帧为参考坐标系，即旋转为单位矩阵$R _ { C _ { 0 } } = E$ ，平移向量为零向量 $t _ { C _ { 0 } } = 0$ 。假设经过初始化[20,21]之后，从相机坐标系到IMU坐标系的旋转外参 $R _ { b c }$ ，平移外参 $t _ { b c }$ ，IMU陀螺仪的偏置 $b ^ { g }$ ，加速度计偏置 $b ^ { a }$ ，以及在参考帧坐标系下的重力矢量 $g _ { C _ { 0 } }$ 是已知的。

# 2.1基于预积分求解机器人的位置、速度、旋转方向

只考虑陀螺仪和加速度计的偏置白噪声以及偏置的随机游走噪声，则IMU模型为[22]：

$$
\hat { w } _ { C _ { 0 } I _ { j } } = w _ { C _ { 0 } I _ { j } } + b ^ { s } + n _ { j } ^ { g }
$$

$$
\hat { a } _ { C _ { 0 } I _ { j } } = q _ { C _ { 0 } I _ { j } } ^ { T } ~ ( a _ { C _ { 0 } I _ { j } } + g _ { C _ { 0 } } ) + b ^ { a } + n _ { j } ^ { a }
$$

其中： $w _ { C _ { 0 } I _ { j } }$ 为陀螺仪在IMU坐标系下真实的角速度值， $\hat { w } _ { C _ { 0 } I _ { j } }$ 为陀螺仪在IMU坐标系下测量得到的角速度值， $a _ { C _ { 0 } I _ { j } }$ 为加速度计在IMU坐标系下真实的加速度值， $\hat { a } _ { C _ { 0 } I _ { j } }$ 为加速度计在IMU坐标系下测量得到的加速度值。 $b ^ { g }$ ， $b ^ { a }$ 的导数服从高斯分布：

$$
\dot { b ^ { s } } \sim \mathbb { N } ( 0 , \sigma _ { b ^ { s } } ) , \dot { b ^ { s } } \sim \mathbb { N } ( 0 , \sigma _ { b ^ { s } } ) ;
$$

其中： $n _ { j } ^ { g }$ ， $n _ { j } ^ { a }$ 分别为陀螺仪、加速度计偏置的随机游走噪声，服从高斯分布：

$$
n _ { j } ^ { g } \sim \mathbb { N } ( 0 , \ \sigma _ { g } ) , \ n _ { j } ^ { a } \sim \mathbb { N } ( 0 , \ \sigma _ { a } ) ;
$$

![](images/d192bf07b7eb7ce50d26ca093d44bdc0efe9a89353166a05180923e3e84c8114.jpg)  
图1系统框架  
Fig.1System framework

在相机坐标系下，分别将 $j$ 时刻机器人位置、速度、旋转方向对时间分别求导得：

$$
\begin{array} { r l } & { \dot { p _ { { C _ { 0 } I _ { j } } } } = \nu _ { { C _ { 0 } I _ { j } } } } \\ & { \dot { \nu _ { { C _ { 0 } I _ { j } } } } = a _ { { C _ { 0 } I _ { j } } } } \\ & { \dot { q _ { { C _ { 0 } I _ { j } } } } = q _ { { C _ { 0 } I _ { j } } } \otimes \left[ \begin{array} { c } { 0 } \\ { 1 } \\ { - 1 } \end{array} \right] } \end{array}
$$

其中， $p _ { C _ { 0 } I _ { j } }$ 为从相机第一帧坐标系到IMU第 $j$ 帧坐标系的平移向量； $\nu _ { C _ { 0 } I _ { j } }$ 为相机坐标系下， $j$ 时刻机器人速度，用三维向量表示； $q _ { C _ { 0 } I _ { j } }$ 为从IMU第 $i$ 帧坐标系到相机第一帧坐标系的旋转矩阵，用四元数表示。 $\dot { p _ { C _ { 0 } I _ { j } } }$ 、 $\dot { \nu _ { C _ { \circ } I _ { j } } }$ 、 $\dot { q _ { C _ { 0 } I _ { j } } }$ 表示将机器人的位置、速度、旋转方向分别对时间求导。

对式(2)进行积分得到在相机坐标系下， $j$ 时刻机器人的位置、速度、旋转方向：

$$
\begin{array} { l } { { \displaystyle p _ { C _ { 0 } I _ { j } } = p _ { C _ { 0 } I _ { j - 1 } + } \nu _ { C _ { 0 } I _ { j } } \triangle { t } + \displaystyle \frac { 1 } { 2 } a \triangle { t ^ { 2 } } } } \\ { { \displaystyle \nu _ { C _ { 0 } I _ { j } } = \nu _ { C _ { 0 } I _ { j - 1 } } + a \triangle { t } } } \\ { { \displaystyle q _ { C _ { 0 } I _ { j } } = q _ { C _ { 0 } I _ { j - 1 } } \otimes \left[ \displaystyle \frac { 1 } { 2 } w _ { \triangle { t } } \right] } } \end{array}
$$

其中 $\Delta t$ 为 $i$ 时刻与 $j$ 时刻的时间间隔，采用中值法得到 $j$ 时刻的加速度 $\boldsymbol { a }$ 和角速度 $w$ ：

$$
\begin{array} { l } { { a = \displaystyle \frac { 1 } { 2 } \Big [ q _ { C _ { 0 } I _ { j - 1 } } ( a _ { C _ { 0 } I _ { j - 1 } } - b ^ { a } ) - g _ { C _ { 0 } } + q _ { C _ { 0 } I _ { j } } ( a _ { C _ { 0 } I _ { j } } - b ^ { a } ) - g _ { C _ { 0 } } \Big ] } } \\ { { \quad w = \displaystyle \frac { 1 } { 2 } \Big [ ( w _ { C _ { 0 } I _ { j - 1 } } - b ^ { g } ) + ( w _ { C _ { 0 } I _ { j } } - b ^ { g } ) \Big ] } } \end{array}
$$

但是在优化位姿过程中，当前帧的速度和旋转矩阵等会发生改变，需要重新进行积分，计算量较大，故引入预积分[22.23]:

$$
q _ { C _ { 0 } I _ { j } } = q _ { C _ { 0 } I _ { k } } \otimes q _ { I _ { k } I _ { j } }
$$

其中， $\otimes$ 表示四元数乘法[22]，将(5)代入(4)更新加速度：

$$
a = q _ { C _ { 0 } I _ { k } } \otimes { \frac { 1 } { 2 } } \Big [ { q } _ { I _ { k } I _ { j - 1 } } ( a _ { C _ { 0 } I _ { j - 1 } } - b ^ { a } ) + q _ { I _ { k } I _ { j } } ( a _ { C _ { 0 } I _ { j } } - b ^ { a } ) \Big ] - g _ { C _ { 0 } }
$$

引入预积分之后运动学模型的离散形式：

$$
\begin{array} { r l } & { p _ { { C _ { 0 } I _ { j } } } = p _ { { C _ { 0 } I _ { j - 1 } } + } \nu _ { { C _ { 0 } I _ { j } } } \Delta t - \displaystyle \frac { 1 } { 2 } g _ { _ { C _ { 0 } } } \triangle t ^ { 2 } + q _ { { C _ { 0 } I _ { k } } } \otimes \alpha _ { { I _ { k } I _ { j } } } } \\ & { \nu _ { { C _ { 0 } I _ { j } } } = \nu _ { { C _ { 0 } I _ { j - 1 } } } - g _ { _ { C _ { 0 } } } \triangle t + q _ { { C _ { 0 } I _ { k } } } \otimes \beta _ { { I _ { k } I _ { j } } } } \\ & { q _ { { C _ { 0 } I _ { j } } } = q _ { { C _ { 0 } I _ { j - 1 } } } \otimes \gamma _ { { I _ { k } I _ { j } } } } \end{array}
$$

其中：

$$
\begin{array} { l } { { \displaystyle \alpha _ { I _ { k } I _ { j } } = \frac { 1 } { 2 } \Big [ q _ { I _ { k } I _ { j - 1 } } ( a _ { c _ { 0 } I _ { j - 1 } } - b ^ { a } ) + q _ { I _ { k } I _ { j } } ( a _ { c _ { 0 } I _ { j } } - b ^ { a } ) \Big ] \Delta t ^ { 2 } } } \\ { { \displaystyle \beta _ { I _ { k } I _ { j } } = \frac { 1 } { 2 } \Big [ q _ { I _ { k } I _ { j - 1 } } ( a _ { c _ { 0 } I _ { j - 1 } } - b ^ { a } ) + q _ { I _ { k } I _ { j } } ( a _ { c _ { 0 } I _ { j } } - b ^ { a } ) \Big ] \Delta t } } \\ { { 1 } } \\ { { \displaystyle \gamma _ { I _ { k } I _ { j } } = \left[ \frac { 1 } { 2 } ( ( w _ { c _ { 0 } I _ { j - 1 } } - b ^ { g } ) + ( w _ { c _ { 0 } I _ { j } } - b ^ { g } ) ) \right] } } \end{array}
$$

为预积分量，计算式(6)得到了相机坐标系下机器人的位置、速度、旋转方向。

# 2.2预测位姿以及特征点位置

结合2.1节得到的结果计算相机坐标系下 $i$ 和 $j$ 两帧之间的转换矩阵 $T _ { C _ { j } C _ { i } }$ ：

$$
T _ { C _ { 0 } C _ { j } } T _ { C _ { j } C _ { i } } = T _ { C _ { 0 } C _ { i } }
$$

其中

$$
T _ { C _ { 0 } C _ { i } } = T _ { C _ { 0 } I _ { i } } T _ { I _ { i } C _ { i } } , T _ { C _ { 0 } C _ { j } } = T _ { C _ { 0 } I _ { j } } T _ { I _ { j } C _ { j } }
$$

将式(9)代入式(8)化简分别得到 $i$ 和 $j$ 两帧之间旋转矩阵$R _ { C _ { j } C _ { i } }$ 和平移向量 $t _ { C _ { j } C _ { i } }$ ：

$$
\begin{array} { r l } & { R _ { C _ { j } C _ { i } } = R _ { I C } ^ { - 1 } R _ { C _ { 0 } I _ { j } } ^ { - 1 } R _ { C _ { 0 } I _ { i } } R _ { I C } } \\ & { t _ { C _ { j } C _ { i } } = R _ { I C } ^ { - 1 } [ R _ { C _ { 0 } I _ { j } } ^ { - 1 } ( R _ { C _ { 0 } I _ { i } } t _ { I C } + t _ { C _ { 0 } I _ { i } } - t _ { C _ { 0 } I _ { j } } ) - t _ { I C } ] } \end{array}
$$

其中， ${ R _ { I C } } ^ { - 1 }$ 为从IMU坐标系到相机坐标系的旋转矩阵； ${ R _ { C _ { 0 } I _ { j } } } ^ { - 1 }$ 为从相机第一帧坐标系到IMU第 $j$ 帧坐标系的旋转矩阵;$R _ { C _ { 0 } I _ { i } }$ 为从IMU第 $i$ 帧坐标系到相机第一帧坐标系的旋转矩阵； $R _ { I C }$ 为从相机坐标系到IMU坐标系的旋转矩阵； $t _ { I C }$ 为从IMU坐标系到相机坐标系的平移向量； $t _ { C _ { 0 } I _ { i } }$ 为从相机第一帧坐标系到IMU第 $i$ 帧坐标系的平移向量。

将第 $i$ 帧的特征点归一化坐标 $p _ { i }$ ，映射到第 $j$ 帧。得到

$$
p _ { j } = R _ { C _ { j } C _ { i } } \stackrel { \cdot } { p _ { i } } + t _ { C _ { j } C _ { i } }
$$

其中 $\stackrel { * } { p _ { i } }$ 为 $p _ { i }$ 的齐次坐标，大小为 $3 { \times } 1$ 的向量， $p _ { j }$ 为IMU预测得到的特征点在第 $j$ 帧下的归一化坐标。

# 3 IMU去除运动模糊光流特征点跟踪算法

运动模糊图像的复原模型可以描述为一个清晰图像经过退化函数作用之后，再加上一个噪声项。设一幅清晰图像 $f ( x , y )$ ，经过退化函数卷积，则产生的退化图像 $g \left( x , y \right)$ ，具体为

$$
g \left( x , y \right) = f \left( x , y \right) ^ { * } h \left( x , y \right) + n \left( x , y \right)
$$

其中 $h ( x , y )$ 称为模糊算子或点扩散函数， $*$ 表示卷积， $n ( x , y )$ 为加性噪声。

复原模型可以根据有无运动先验分为盲复原和非盲复原。由于通过IMU得到的加速度和角速度可以确定运动信息，因此研究重点放在非盲复原模型。

# 3.1融合IMU先验信息的运动模糊非盲复原模型

当两幅图像的时间戳，即时间间隔 $t _ { i j }$ 已知时，通过(7)得到了机器人在两帧之间的速度信息，进而利用(11)计算了特征点在两帧的归一化坐标 $( u _ { i } , \nu _ { i } )$ 、 $( u _ { j } , \nu _ { j } )$ ，于是得到机器人运动模糊方向的角度和长度：

$$
\begin{array} { l } { \left\{ \theta = \arctan ( \frac { \nu _ { j } - \nu _ { i } } { u _ { j } - u _ { i } } ) \right. } \\ { \left. L = \nu \times t _ { i j } \right. } \end{array}
$$

其中 $\nu$ 表示机器人速度， $t _ { i j }$ 为时间间隔。通过运动模糊的方向 $\theta$ 和长度 $\boldsymbol { L }$ ，则可确定运动模糊的点扩散函数宽度 $b$ 、高度 $h$ ：

$$
\left\{ \begin{array} { l } { b = L \times \cos \theta } \\ { h = L \times \sin \theta } \end{array} \right.
$$

点扩散函数 $h ( x , y )$ 由以下隐函数表示为

$$
h ( x , y ) = \left\{ \begin{array} { l l } { \displaystyle y = \lbrack \frac { b } { h } \times x \rbrack } & { ~ x = 0 , ~ 1 , ~ . . . , h - 1 } \\ { \displaystyle x = \lbrack \frac { h } { b } \times y \rbrack } & { ~ y = 0 , ~ 1 , ~ . . . , b - 1 } \end{array} \right.
$$

根据点扩散函数建立模糊复原模型 $f ( x , y )$ [24]为

$$
f ( x , y ) = \underset { f ( x , y ) } { \arg \operatorname* { m i n } } \left\| g ( x , y ) - f ( x , y ) \otimes h ( x , y ) \right\| _ { 2 }
$$

其中 $\left\| g ( x , y ) - f ( x , y ) \otimes h ( x , y ) \right\| _ { 2 }$ 为图像保真项，保证清晰图像经过点扩散函数作用后，与模糊图像一致。式(16)可通过快速傅里叶变换求解[19]。

# 3.2改进原有光流法优化求解匹配特征点

本文在原有LK光流假设两帧图像之间同一特征点光度不变的基础上，首先，加入梯度不变假设：

$$
\nabla I _ { 1 } ( x , y ) = \nabla I _ { 2 } ( x + \Delta x , \Delta y )
$$

充分利用特征点与相邻像素的信息，保证正确的匹配对。其次，为了防止过拟合，使用第二帧图像梯度 $L _ { 1 }$ 范数模拟稀疏噪声，构建正则化项，最终模型建立如下：

$$
\begin{array} { r l r } & { } & { ( \Delta x , \Delta y ) { = } \underset { ( \Delta x , \Delta y ) } { \arg \operatorname* { m i n } } ( \left\| I _ { 1 } ( x , y ) - I _ { 2 } ( x + \Delta x , \Delta y ) \right\| _ { 2 } + } \\ & { } & { } \\ & { } & { \alpha \left\| \nabla I _ { 1 } ( x , y ) - \nabla I _ { 2 } ( x + \Delta x , \Delta y ) \right\| _ { 2 } + \beta \left\| \nabla I _ { 2 } ( x , y ) \right\| _ { 1 } ) } \end{array}
$$

其中： $I _ { 1 } ( x , y )$ 表示参考帧在像素坐标 $\left( x , y \right)$ 处图像的灰度值;$I _ { 2 } ( x + \Delta x , \Delta y )$ 表示当前帧在像素坐标 $( x + \Delta x , \Delta y )$ 处图像的灰度值； $\nabla I _ { 1 } ( x , y )$ 表示参考帧在像素坐标 $\left( x , y \right)$ 处图像的梯度值；$\nabla I _ { 2 } ( x + \Delta x , \Delta y )$ 表示当前帧在像素坐标 $( x + \Delta x , \Delta y )$ 处图像的梯度值； $\alpha$ 为梯度权重系数， $\beta$ 为稀疏噪声项权重系数。

在2.2节中，已经通过IMU预测得到第二帧特征点的位置，将预测位置作为高斯牛顿非线性优化算法初始值，并在原来固定步长基础上加入BB可变步长进行迭代。

将式(17)非线性函数 $F ( X )$ 进行泰勒展开至二阶：

$$
\begin{array} { c } { F ( { \boldsymbol { X } } ) { = } F ( { \boldsymbol { X } } _ { k } ) + { \nabla } F ( { \boldsymbol { X } } _ { k } ) ( { \boldsymbol { X } } - { \boldsymbol { X } } _ { k } ) + { } } \\ { \displaystyle { \frac { 1 } { 2 ! } } ( { \boldsymbol { X } } - { \boldsymbol { X } } _ { k } ) ^ { T } H _ { x _ { k } } ( { \boldsymbol { X } } - { \boldsymbol { X } } _ { k } ) } \end{array}
$$

其中， $\boldsymbol { \cal X }$ 为优化变量， $X _ { k }$ 为优化变量在第 $k$ 步的取值， $F ( X _ { k } )$ 为非线性函数 $F ( X )$ 在 $X _ { k }$ 处的取值， $\nabla F ( X _ { k } )$ 为非线性函数$F ( X )$ 在 $X _ { k }$ 处的梯度值， $H _ { { X _ { k } } }$ 为 $F ( X )$ 在 $X _ { k }$ 处的海塞矩阵。

对式(18)求导，令其为0，得优化变量 $X { = } X _ { k } - H _ { \mathrm { \Lambda } _ { X _ { k } } } ^ { - 1 } \nabla f ( X _ { k } )$ ，则优化方向 $\boldsymbol { d } _ { k }$ 为

$$
d _ { k } = - H _ { \scriptscriptstyle X _ { k } } ^ { \scriptscriptstyle - 1 } \nabla F ( X _ { k } )
$$

下面对步长进行求解，对于一般地二次函数优化问题，

$$
F ( X ) = \frac { 1 } { 2 } X ^ { T } A X + b ^ { T } X
$$

其中 $A$ 表示二次函数的系数矩阵， $b$ 为偏置。对式(20)求导，得一阶导函数 $F ^ { \prime } ( X ) = A X + b$ ，则第 $k$ 步迭代梯度为

$$
\nabla F ( X _ { k } ) = A X _ { k } + b
$$

将式(21)代入式(19)，加入常数高斯牛顿迭代步长 $g _ { k }$ ，近似迭代方向：

$$
d _ { k } = - H _ { x _ { k } } ^ { - 1 } \nabla F ( X _ { k } ) \approx - g _ { k } I \nabla F ( X _ { k } ) = - ( g _ { k } ^ { - 1 } I ) ^ { - 1 } \nabla F ( X _ { k } )
$$

其中 $I$ 为单位矩阵，定义自变量的差 $S _ { k - 1 }$ ，梯度差 $Y _ { k - 1 }$ ：

$$
S _ { k - 1 } = X _ { k } - X _ { k - 1 } , Y _ { k - 1 } = \nabla F \left( X _ { k } \right) - \nabla F \left( X _ { k - 1 } \right)
$$

对式(21)在第 $k$ 与第 $k - 1$ 处做差：

$$
\nabla F ( X _ { k } ) - \nabla F ( X _ { k - 1 } ) = A X _ { k } - A X _ { k - 1 } = A S _ { k - 1 }
$$

则得到拟牛顿方程：

$$
A S _ { k - 1 } = ( g _ { k } ^ { - 1 } I ) S _ { k - 1 } = Y _ { k - 1 }
$$

在式(25)中令 $\delta = g ^ { - 1 }$ ，则第 $k$ 步步长：

$$
g _ { k } ^ { - 1 } = \underset { g } { \arg \operatorname* { m i n } } \frac { 1 } { 2 } \big \| S _ { k - 1 } \delta - Y _ { k - 1 } \big \| _ { 2 }
$$

求得式(26)的最小二乘解：

$$
g _ { k } = { \frac { S _ { k - 1 } ^ { T } S _ { k - 1 } } { S _ { k - 1 } ^ { T } Y _ { k - 1 } } }
$$

由式(27)可以看出， $g _ { \boldsymbol { k } }$ 仅与第 $k$ 步自变量状态信息和相邻两步函数的梯度有关，与其他变量无关。

# 4 实验结果与分析

本文所有实验均在同一平台进行，平台主要配置为AMDRyzen53500UwithRadeonVegaGfx四核笔记本处理器，内存为12GB，基准频率为 $2 . 1 0 \mathrm { G H z }$ ，Ubuntu18.04操作系统。

在本节，首先单独对算法本身的性能进行评估，将提出的算法与VINS-Mono 框架中匹配算法LK光流法、ORB 特征点检测算法对比，测试在两帧之间匹配运行时间和匹配精度。其次，为了进一步验证提出的优化算法的准确性以及在系统框架中的稳定性，将该算法集成到VINS-Mono 系统框架，与原VINS-Mono、PL-VIO[25]、VINS-Fusion[26]单目相机加IMU(Mono-IMU)、VINS-Fusion 双目相机加IMU(Stereo-IMU进行对比，评价定位精度。

实验选用的数据集是机器人微型飞行器(MicroAerialVehicle，MAV上收集的视觉惯性数据集EuRoC，飞行场景是苏黎世联邦理工学院 ETH 的一个机器工厂和两个普通房间场景。为了验证所提出算法在普通场景数据下的有效性，该算法使用了3个场景不同难度的9个序列：MH_02_easy,MH_03_medium，MH_04_difficult，V1_01_easy，V1_02_medium，V1_03_difficult，V2_01_easy，V2_02_medium，V2_03_difficult。

# 4.1两帧之间算法运行时间对比

本文提出的算法与LK光流法同属于光流法，在比较匹配的运行时间时，实验控制特征点提取算法相同，均采用ShiTomasi算法的角点检测，利用OpenCV中的函数cv::goodFeaturesToTrack，其中提取算法参数：最大角点数目500，质量水平系数0.01，最小距离30，其他参数都采用cv::goodFeaturesToTrack默认参数。将算法循环100o次，取平均值，提出的算法平均运行时间为：1.361毫秒；OpenCV中LK光流法：2.892毫秒，速度提高 $5 2 . 9 3 9 \%$ ，随即取20次实验结果如图2所示。

当所提出的算法和特征点法比较的时候，由于特征点法利用描述子进行匹配，所以在比较的过程中，需要加入计算描述子的时间，另外，描述子与特征点检测算法往往是一一对应的，所以最终的比较策略是将特征点提取时间加匹配时间一起进行比较。同样将算法循环1000次，取平均值，提出的算法平均运行时间为：8.382毫秒；OpenCV中ORB 特征点法特征点提取与匹配平均时间为：35.110毫秒，速度提高$7 6 . 1 2 5 \%$ ，结果如图3所示。

![](images/8570feb607e4c475db332b0e3ee5b39ff77b8db979ceff30d4a437766e9a1289.jpg)  
图2提出的算法与LK光流法匹配时间对比 Fig.2Comparison of matching time between proposed algorithm and LK optical flow method

# 4.2两帧之间匹配精度评估

如果两帧的特征点 $x _ { 1 }$ 和 $x _ { 2 }$ 是正确匹配点，则应该满足对极约束：

$$
x _ { 2 } ^ { T } t _ { 2 1 } ^ { \wedge } R _ { 2 1 } x _ { 1 } = 0
$$

由于测量误差存在，上式几乎不可能成立，故求其最小

二乘误差最小解：

$$
a l l \_ e r r o r = \sum _ { i = 1 } ^ { s i z e } e r r o r ( i ) ^ { T } W ^ { - 1 } e r r o r ( i )
$$

其中error(i)为观测数据， $W$ 为协方差矩阵，当最小二乘解越小时，两帧之间匹配程度也越高，定义匹配分数：

$$
s c o r e = \sum _ { i = 1 } ^ { s i z e } \left( 1 / \left( e r r o r ( i ) + 1 \right) \right) ^ { T } W ^ { - 1 } \left( 1 / \left( e r r o r ( i ) + 1 \right) \right)
$$

![](images/0527859d77804dd4006dad06a8659db68f664d9dd743c8aa68f96d4e7ec8f4ea.jpg)  
图3提出的算法与ORB特征点法检测加匹配时间对比 Fig.3Comparison of detection and matching time between the proposed algorithm and ORB method

根据以上定义的评估标准，计算匹配分数。如表1所示，本文提出的算法精度比光流法精度提高了 $5 3 . 2 9 5 \%$ ，这得益于提出的改进优化模型(17)，即在原有光度不变假设的基础上，引入梯度误差和噪声稀疏项。这一对比结果充分说明了改进优化模型的合理性和有效性。另外，当与OpenCV中ORB特征点检测算法相比时，虽然算法精度降低了 $1 3 . 5 5 4 \%$ ，但其运行时间提高了 $7 6 . 1 2 5 \%$ ，考虑实际情况中的实时性要求，这个精度结果也是可以被接受的。

表1对极约束得分

Tab.1Score for polar constraints   

<html><body><table><tr><td></td><td>得分</td><td>提高</td></tr><tr><td>proposed</td><td>28.7961</td><td></td></tr><tr><td>LK光流</td><td>18.7847</td><td>53.295%</td></tr><tr><td>ORB</td><td>33.3111</td><td>-13.554%</td></tr></table></body></html>

图4\~6分别为传统高斯牛顿法优化结果、OpenCV中匹配优化结果以及本文提出算法匹配优化结果，展示选用的图片为MH_02_easy序列中相邻两张图片，并以左图特征点顺序为匹配对信息编号。图4在没有给定初始值的情况下，默认初始值旋转矩阵为单位矩阵，平移向量为零向量。当物体运动过快，图像模糊程度较高，旋转位姿与默认初始值偏差较大，误匹配现象较多。对比图5、6可以看出，由于给定了初始值进行当前帧局部邻域搜索匹配点，基本避免了特征点对的误匹配，OpenCV中光流法仍然会出现误匹配现象，例如编号：2，11，20，21，22，27，33，39，49等。

# 4.3系统定位精度评估

本小节本文将提出的改进光流匹配算法移植到经典的VINS-MONO前端中，其目的是进一步验证提出的优化方法在VI-SLAM系统上的准确性和稳定性。为此，将改进的框架与VINS-Mono、PL-VIO、Mono-IMU、Stereo-IMU通过EVO评估工具[27进行对比。其中，PL-VIO是在VINS-Mono 前端加入点线特征改进；Mono-IMU、Stereo-IMU是VINS-Fusion在VINS-Mono 基础上加入多传感器改进，并且是KITTIVisualOdometry榜单中排名最靠前的开源方案及改进算法。

与文献[12]一样，将对齐之后绝对轨迹误差(AbsoluteTrajectoryError，ATE)的均方根误差(RootMeanSquareError,RMSE)和误差均值作为评估指标。为防止结果的偶然性，进行20次实验取均值对比，如表2所示，提出的算法在EuRoC数据集上，均优于PL-VIO 框架，与VINS-Fusion性能相近，并且经多次实验，VINS-Fusion在V2_03_difficult 数据集上会出现偏离真实轨迹特别远的情况。值得注意的是，由于MH_03_medium与V2_01_easy数据集在两个主导方向 $\textbf { x }$ 和y 的陀螺仪、加速度计偏置较其他数据集平均误差较大，不符合提出算法强依赖于整个系统运动的精确初始化这一基本假设，所以这两个序列性能差于VINS-Mono。更具体而言，如果没有好的初始值，优化算法将退化为无初始化的高斯牛顿法，这不仅会增加寻优时间，也会影响系统精确度。除这两个数据集外，其他序列都有提升，最为显著的是V203difficult序列，具有飞行器摆动较快，图像模糊程度较高等特点，是具有挑战性的数据集之一，其RMSE降低$1 8 . 0 6 6 \%$ ，误差均值降低 $2 8 . 9 0 2 \%$ 。另外，图7、8展示了提出的算法与在V2_03_difficult序列估计轨迹与真实轨迹比较热力图；图9、10展示了V2_03_difficult序列中提出的算法与VINS-Mono 算法相对轨迹误差的均方根、均值、标准差。通过这些比较，表明提出的算法在相机剧烈抖动情况下，鲁棒性更好。

![](images/24df6d94192622f4483a51c93aa2e284fa6a928a568c4b55dd608c131ec66882.jpg)

![](images/166e9572bc67b14873213587e2c045fe1cf384a268c8f99775a3e8a4fd7350e2.jpg)  
Fig.4Gaussian Newton iterative matching algorithm without initial values   
图5OpenCVLK光流匹配算法

![](images/cbef338e3dfd059eb7df3e8c18f598cc9d804ade8f877cc93b13aa249e5a9adc.jpg)  
图4无初始值的高斯牛顿迭代匹配算法  
Fig.5OpencvLK optical flow matching algorithm   
图6提出的匹配算法  
Fig.6The proposed matching algorithm 表2多种框架性能比较

Tab.2Performance comparison of multiple frameworks   

<html><body><table><tr><td rowspan="2">序列</td><td colspan="2">提出的算法/(m)</td><td colspan="2">VINS-Mono/(m)</td><td colspan="2">PL-VIO/(m)</td><td colspan="2">Mono-IMU/(m)</td><td colspan="2">Stereo-IMU/(m)</td></tr><tr><td>RMSE</td><td>均值</td><td>RMSE</td><td>均值</td><td>RMSE</td><td>均值</td><td>RMSE</td><td>均值</td><td>RMSE</td><td>均值</td></tr><tr><td>MH_02_easy</td><td>0.173</td><td>0.139</td><td>0.194</td><td>0.164</td><td>0.186</td><td>0.158</td><td>0.184</td><td>0.152</td><td>0.184</td><td>0.151</td></tr><tr><td>MH_03_medium</td><td>0.408</td><td>0.322</td><td>0.402</td><td>0.314</td><td>0.422</td><td>0.334</td><td>0.391</td><td>0.296</td><td>0.468</td><td>0.416</td></tr><tr><td>MH_04_difficult</td><td>0.394</td><td>0.325</td><td>0.402</td><td>0.331</td><td>0.466</td><td>0.395</td><td>0.398</td><td>0.326</td><td>0.520</td><td>0.463</td></tr><tr><td>V1_01_easy</td><td>0.143</td><td>0.119</td><td>0.154</td><td>0.131</td><td>0.145</td><td>0.125</td><td>0.147</td><td>0.125</td><td>0.172</td><td>0.156</td></tr><tr><td>V1_02_medium</td><td>0.306</td><td>0.249</td><td>0.307</td><td>0.250</td><td>0.323</td><td>0.269</td><td>0.307</td><td>0.256</td><td>0.307</td><td>0.254</td></tr><tr><td>V1_03_difficult</td><td>0.319</td><td>0.278</td><td>0.325</td><td>0.287</td><td>0.374</td><td>0.330</td><td>0.299</td><td>0.261</td><td>0.265</td><td>0.218</td></tr><tr><td>V2_01_easy</td><td>0.127</td><td>0.108</td><td>0.124</td><td>0.106</td><td>0.142</td><td>0.121</td><td>0.123</td><td>0.103</td><td>0.150</td><td>0.131</td></tr><tr><td>V2_02_medium</td><td>0.259</td><td>0.213</td><td>0.262</td><td>0.216</td><td>0.271</td><td>0.226</td><td>0.275</td><td>0.228</td><td>0.260</td><td>0.218</td></tr><tr><td>V2_03_difficult</td><td>0.322</td><td>0.276</td><td>0.393</td><td>0.346</td><td>0.486</td><td>0.435</td><td>/</td><td></td><td>0.404</td><td>0.364</td></tr></table></body></html>

![](images/1584ad67c784eda79ecfe029f9ce6b88db8ebae9b8abb5f7b3f618f317a9b107.jpg)

![](images/11ad3d552b62b09ac200f95ebe898f91e41364bcd9d3d60c1f17d75b967a1a1a.jpg)  
图7提出的算法在V2_03_difficult序列热力图 Fig.7Heat map of the proposed algorithm in V2_03_difficult sequence

![](images/3392a0a9d609b39a790839a878b6e2e24bdafb19441720e5f6e62038a681f3a5.jpg)  
Fig.8Heat map of the Vins-Mono inV2_O3_difficult sequence   
图9提出的算法在V2_03_difficult序列表现

![](images/2dc3f3fa64f500f10ecc195bd18e4b68ca001eb572de1f57f129b7a8f0cdc020.jpg)  
图8Vins-Mono在V2_03_difficult序列热力图  
Fig.9Performance of the proposed algorithm in V2_O3_difficult   
图10VINS-Mono 在V2_03_difficult序列表现  
Fig.10Performance of the VINS-Mono in V2_03_difficult sequence

# 5 结束语

本文提出了一种融合视觉和IMU对图像进行去除运动模糊预处理，再改进光流法对特征点匹配的新算法。该算法充分利用IMU的运动信息，实现去除图像运动模糊信息并为迭代匹配算法提供初始值，减小特征点对误匹配概率。该算法是一个通用的模块，可以移植到其他VI-SLAM框架中。通过在三个不同难度层次的数据集上进行验证表明，该算法本身效率和精度都优于OpenCV库函数中光流匹配算法，并且将提出的算法集成到最先进的VIO框架VINS-Mono上，在位姿估计方面提高了精度。将来可以对去模糊算法进一步研究，加入正则项去除伪影，进一步提高匹配精度。

# 参考文献：

[1]Durrant Whyte H,Bailey T.Simultaneous localization and mapping: part I[J].IEEE Robotics & Automation Magazine,2006,13 (2): 99-110.

[2] Pradeep V,Rhemann C,Izadi S,et al. MonoFusion: Real-time 3D reconstruction of small scenes with a single web camera [C]// Proc of IEEE International Symposium on Mixed and Augmented Reality. Australia: IEEE,2013:83-88.   
[3]郭金辉，陈秀万，王媛．视觉惯性 SLAM研究进展[J]．火力与指挥 控制，2021,46(1):1-8.(Guo JinHui,Chen Xiuwan，Wang Yuan. Research progress of visual inertia slam [J]. Fire control and command control,2021,46 (1): 1-8.)   
[4] 胡立华，左威健，张继福．采用逆近邻与影响空间的图像特征误匹 配剔除方法[J].计算机辅助设计与图形学学报，2022,34(3):449- 458.(Hu LiHua, Zuo Weijian, Zhang Jifu. The image feature mismatch elimination method of inverse nearest neighbor and influence space is adopted [J]. Journal of Computer-Aided Design and Computer Graphics, 2022,34 (3): 449-458.)   
[5]付煜，郑爽，别桐等．融合点线特征的视觉惯性 SLAM 算法[J].计 算机应用研究:2022,39(2):1-8.(FuYu,Zheng Shuang,BieTong,et al.Visual inertialSLAMalgorithmithfusedpointandlinefeatures [J]. Application Research of Computers: 2022,39 (2): 1-8.)   
[6]Triggs B,Mclauchlan PF,Hartley RI,et al.Bundle adjustment-A Modern Synthesis [C]// Proc of International Workshop on Vision Algorithms.Heidelberg:Springer,1999:298-372.   
[7]伞红军，王汪林，陈久朋等．改进误匹配剔除的 SLAM 算法[J]．软 件导刊,2021,20 (08): 99-104.(San Hongjun,Wang Wanglin, Chen Jiupeng,et al. Improved SLAM algorithm for error matching elimination [J]. Software Guide,2021,20 (08): 99-104.)   
[8]Lowe DG. Distinctive image features from scale-invariant keypoints [J]. International Journal of Computer Vision,2004,60 (2): 91-110.   
[9] Rosten E，Drummond T. Machine learning for high-speed corner detection [C]//Proc of European conference on computer vision. Berlin: Heidelberg,2006: 430-443.   
[10] Lucas B D,Kanade T.An iterative image registration technique with an application to stereo vision [C]/ Proc of Imaging Understanding Workshop,1981.   
[11] Engel J,Schóps T,Cremers D.LSD-SLAM:Large-scale direct monocular SLAM[C]/ Proc of European conference on computer vision. Cham: [s.n.],2014: 834-849.   
[12] Qin Tong,Li Peiliang,Shen Shaojie.VINS-Mono: A robust and versatile monocular visual-inertial state estimator[J].IEEE Transon Robotics, 2018,34 (4): 1004-1020.   
[13] Guan Qi,Wei Guoliang,Wang Licheng,et al.A novel feature points tracking algorithm in terms of IMU-aided Information Fusion [J]. IEEE Trans on Industrial Informatics,2021,17(8): 5304-5313.   
[14] Leutenegger S,Lynen S,Bosse M, et al. Keyframe-based visual-inertial odometry using nonlinear optimization [J]. The International Journal of Robotics Research,2015,34 (3): 314-334.   
[15] Mourikis Anastasios I,Roumeliotis SI.A Multi-State Constraint Kalman Filterfor Vision-aided Inertial Navigation [J].IEEE International Conference on Robotics and Automation,2007: 3565-3572.   
[16] Davison AJ.Active search for real-time vision [C]// Proc of Tenth IEEE International Conference on Computer Vision Volume 1. [S.1.] : IEEE, 2005: 66-73.   
[17] Shi J,Tomasi C.Good features to track [C]//Proc of IEEE conference on computer vision and patern recognition.[S.1.]: IEEE,1994: 593-600.   
[18] Fergus R,Singh B,Hertzmann A,et al.Removing camera shake from a single photograph [M]//[S.1.]:ACMSIGGRAPH,2006:787-794.   
[19] Chen Liang,Fang Faming,Wang Tingting,et al.Blind image deblurring with local maximum gradient prior [C]// Proc of the IEEE/CVF Conference on Computer Vision and Pattern Recognition.2019:1742- 1750.   
[20] Mur-ArtalR,Tardós JD.ORB-SLAM2:An open-source slam system for monocular,stereo,and RGB-D cameras [J].IEEE Trans on Robotics, 2017,33(5):1255-1262.   
[21] Qin Tong,Shen Shaojie.Robust initialization of monocular visualinertial estimation on aerial robots[C]//Proc of IEEE/RSJInternational Conference on Intelligent Robots and Systems.Vancouver: IEEE,2017: 4225-4232.   
[22] Lupton T,Sukkarieh S.Visual-inertial-aided navigation for highdynamic motion in built environments without initial conditions [J]. IEEE Trans on Robotics,2012,28(1):61-76.   
[23] Shen Shaojie,Michael N,Kumar V.Tightly-coupled monocular visualinertial fusion for autonomous flight of rotorcraft MAVs $[ \mathrm { C } ] / \AA$ Proc of IEEE International Conference on Robotics and Automation.[S.1.]: IEEE,2015:5303-5310.   
[24] Chen Liang,Fang Faming,Lei Shen,et al.Enhanced sparse model for blind deblurring [C]//Proc of European Conference on Computer Vision. [S.1.]:Springer,2020:631-646.   
[25] He Yijia,Zhao Ji,Guo Yue,et al.PL-VIO:tightly-coupled monocular visual-inertial odometry using point and line features [J]. Sensors,2018, 18 (4): 1159.   
[26] Qin Tong,Pan Jie,Cao Shaozu,et al.A general optimization-based framework for local odometry estimation with multiple sensors [J/OL]. (2019-01-11) [2022-04-11].http://arxiv.org/abs/1901.03638.   
[27] Grupp M.EVO:Python package for the evaluation of odometry and SLAM [J/OL]．(2017-01-01) [2022-04-11]. https://github. com/MichaelGrupp/evo.