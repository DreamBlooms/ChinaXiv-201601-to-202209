# 面向应用的RGB-D机器人道路坡度融合估计方法

凌晨飞，党淑雯，陈丽(上海工程技术大学 航空运输学院，上海 201600)

摘要：为提高机器人在移动路径中对道路坡度的估计精度，提出一种面向应用的RGB-D(RedGreen Blue-Depth)机器人融合型道路坡度估计方法。首先，引入随机采样一致性算法完成点云处理；其次，采用改进型平面拟合方法完成法向量估计；最后，采用余弦聚类及累加平均方法实现高精度道路坡度估计。实验结果表明，该算法在数据集下相较最小二乘法与稀疏子空间法，估计误差分别降低 $1 . 2 1 \% . 2 . 1 3 \%$ ，在实际环境下较最小二乘法平均误差降低 $1 . 4 3 ^ { \circ }$ ，这证明了所提方法的可行性和准确性。

关键词：RGB-D；机器人；法向量估计；坡度估计 中图分类号：TP242 doi:10.19734/j.issn.1001-3695.2022.03.0131

# Fusion slope estimation algorithm for RGB-D moving robot

Ling Chenfei, Dang Shuwen†, Chen Li (SchoolofAir Transport,Shanghai Universityof Engineering Science,Shanghai 2016oo,China)

Abstract:Inordertoimprove the estimation accuracyoftheroad slope duringthe movementoftherobot,this paper proposed afusion slope estimationalgorithm forRGB-D(red grenblue-depth)movingrobot.Firstly,themethodusedrandomsampling consistency algorithm tocomplete the pointcloud processing.Secondly,the normal vector estimation followed an improve plane fiting method.Finaly,thecosine clustering and cumulative average method wereused toaccuratelycomplete theroad slope estimation.Experimental results showed thatcompared with the least squares method andthe sparse subspace method under the data set, the estimation error of the algorithm is reduced by $1 . 2 1 \%$ and $2 . 1 3 \%$ respectively,in the actual environment, the average error is reduced by $1 . 4 3 ^ { \circ }$ compared with the least squares method,which verifies the feasibility and effectiveness of the proposed algorithm.

Key words:RGB-D; robot; normal vector estimation; slope estimation

# 0 引言

移动机器人在复杂地形环境下、尤其是坡面道路条件下运动过程中，准确并稳定的完成道面坡度估计成为关键性问题，目前基于激光[1,2]和视觉[3.4]传感器的环境信息探测是移动机器人完成地图构建[5、路径规划[的主要手段。激光传感器因其测量精度高这一优势常被应用于智能交通、智能防疫、甚至外星探测等领域，而提高道路坡度估计精度及稳定性成为亟待解决的问题。文献[7\~10]采用传统最小二乘法直接拟合区域化地形块的均值平面，拟合出平面的倾角即为该区域的坡度，该方法计算简便，设计精简，但易受异常值影响，估计误差较大；李海波等人[对传统最小二乘法进行优化，采用稀疏系数划分子空间，再对子空间进行平面拟合，最后在子空间采用随机搜索获取最优平面，进而完成坡度估计，该方法可有效减少异常值对坡度估计的影响，但需要根据平面情况预先设定搜索阈值，同时最优平面的随机搜索可能导致计算结果陷入局部最优，导致坡度估计结果有一定随机性;白莎莎等人[12]在中线拟合部分使用自适应阈值拟合算法，通过点云数量信息和坐标信息自动计算阈值，丰富了滑雪场雪道坡度计算的方法。

以上坡度估计方法采用激光雷达方案，激光测量发展迅速、测量范围广[13,14]，但与视觉相机相比，激光雷达所获取的三维环境信息较稀疏，丢失了很多三维特征；且多数视觉相机的体积小、重量轻，对机器人的承重影响较小[15]。目前，视觉相机主要应用于工件缺陷检测[16]、物体分拣[17]、视觉定位[18]等，但应用于移动机器人的坡度估计方案较少。从实际应用来说，相较激光传感器，基于视觉传感器的移动机器人在坡度道面环境下的应用更为合适，但目前面向视觉移动机器人的道面坡度估计方法普遍存在仅停留在仿真无法面向实际应用，估计误差较大的问题。

本文提出一种面向实际应用的视觉RGB-D机器人道路坡度融合型估计方法。该方法系统构建了包含点云滤波、平面分割、法向量提取、余弦聚类和累加平均滤波几个环节的融合型算法流程，并就数据集和真实环境下进行了道面坡度估计实验。经与传统方法比较分析，结果表明所提出方法在降低估计误差、提高坡度估计精度具备显著优势。

# 1 算法流程

本文算法流程如图1所示，其中：

a)对得到的点云信息，首先采用统计滤波方法，滤除视觉传感器采集所得点云表面的离群点，之后采用随机采样一致性算法进行平面分割，分别提取斜面和水平面。为提高点云处理效率，设定平面点云的数据判断阈值为10000，当数据点超阈值时，采用直通滤波方法降低数据点数目，并引入随机最小二乘方法拟合点云平面提取法向量。

b)对提取得到的法向量，首先采用余弦聚类，对异常向量进行聚类剔除，最后通过累加拟合方法以得到更为精确的坡度。

![](images/1d731e2b4d405fa1b3172a784955e92cf16ccccc99e6a3cd9b9f6d3dd9540e1f.jpg)  
Fig.1Algorithm flowchart

# 2 三维点云拟合平面的法向量获取

# 2.1滤波处理

使用视觉相机进行点云获取时，相机深度数据易受外界光线的干扰，故采集到的图像存在异常噪声，因此首先引入统计滤波方法对点云内每一个点的邻域进行统计分析，估计它到所有临近点的平均距离。假设某个点云为

$$
D = \{ p _ { i } \in R ^ { 3 } \} _ { i = 1 , 2 , \ldots , t }
$$

其中： $t$ 表示样本中点云中点的总个数； $p _ { i }$ 表示点云 $D$ 中无序点，只取每个无序点的 $\ x , \ y , \ z$ 三维坐标。计算点 $p _ { t }$ 的距离阈值 $d _ { a \nu g }$ ：

$$
d _ { \mathrm { a v g } } = \frac { 1 } { m } \sum _ { j = 1 } ^ { m } d _ { ( p _ { t } , p _ { j } ) } + \alpha \times d _ { \mathrm { s t d } }
$$

其中： $m$ 为点 $p _ { t }$ 的邻近点个数； $d _ { ( p t , p j ) }$ 为点 $\boldsymbol { p } _ { t }$ 与其邻近点 ${ \boldsymbol { p } } _ { j }$ 的欧氏距离，其计算公式为 $d _ { ( p _ { t } , p _ { j } ) } = \left\| p _ { t } - p _ { j } \right\| _ { 2 }$ ； $\alpha$ 为阈值系数； $d _ { s t d }$ 为点 $p _ { t }$ 与其邻近的 $m$ 个点之间的距离标准差。若某点与点 $p _ { t }$ 的距离大于 $d _ { a \nu g }$ ，则判定为离群点，将其剔除出点集[19,20]。经多组实验对比分析，统计滤波的参数设置为 $m = 2 0 , \alpha = 2$ 时，可更有效的滤除离群点[21]。

# 2.2平面分割

假定形成道面夹角的两个平面中，墙面为斜面，地面为水平面。引入随机采样一致算法以完成两个平台的点云提取，提取算法流程如下：

从待处理点云中随机选取3个不共线的点，得出由这3个点确定的平面的方程为

$$
A x + B y + C z = E
$$

其中 $^ { A , B , C , E }$ 为所确定平面方程的参数，其他点 $( a , b , c )$ 到平面的距离 $d _ { i }$ 为

$$
d _ { i } = { \frac { \left| A ^ { * } a + B ^ { * } b + C ^ { * } c - E \right| } { { \sqrt { A ^ { 2 } + B ^ { 2 } + C ^ { 2 } } } } }
$$

$d _ { i }$ 平均距离 $\bar { d }$ 以及 $d _ { i }$ 的标准偏差 $\sigma$ 为

$$
\overline { d } = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } d _ { i }
$$

$$
\sigma = { \sqrt { \frac { \displaystyle \sum _ { i = 1 } ^ { n } \bigl ( d _ { i } - { \overline { { d } } } \bigr ) ^ { 2 } } { n - 1 } } }
$$

如图2所示，取距离阈值 $t = 2 \sigma$ ，当 $d _ { i } > t$ 时，此点被认为是外点，予以删除；反之，则为内点，予以保留，并统计局内点的总数[22]；找出内点数量最多的平面点集，并返回相应内点的序号，将其记为一个平面区域。从场景点云中剔除已经得到的内点，重复上述步骤，直到场景中剩余的点数小于预先设定的阈值，或者最后一次得到的内点数量小于阈值[23,24]。

![](images/e4e7bda053795de432749fea3e4bb5d98387d6bafa70efc22b50e9ddafd4073f.jpg)  
图1算法流程  
图2坡道阈值示意图  
Fig.2Schematic diagram of ramp threshold

为便于后续计算，对于分割后的各平面点云中数据点进行判断，当数据点超过10000时,使用直通滤波来滤除部分点云。

# 2.3 法向量提取

对于分割得到的两平面，需要先提取其平面法向量，再进行夹角估计，点云法向量的提取过程分为法向量估计及法向量定向。

# 2.3.1法向量估计

根据随机选取的邻域内点 $p _ { i }$ ，并设置拟合邻域值 $k$ ，可得到一个拟合平面，平面的法线即为该点的法向量，点的邻域为

$$
\mathcal { N } = \{ p _ { i } \left( x _ { i } , y _ { i } , z _ { i } \right) \} \ i = 1 , 2 , . . . , n \}
$$

点 $p _ { i }$ 的三维空间坐标为 $\left( x _ { i } , y _ { i } , z _ { i } \right)$ ，可得拟合平面 $\mathcal { N }$ 的一般形式是

$$
F x + G y + H z = I
$$

其中 $F , G , H , I$ 为所得拟合平面 $\mathcal { N }$ 的平面方程参数

$$
F ^ { 2 } + G ^ { 2 } + H ^ { 2 } = 1
$$

使用随机最小二乘进行拟合，即求解以下最小值

$$
\operatorname* { m i n } _ { F , G , H , I } \sum _ { i = 1 } ^ { n } \left( F x _ { i } + G y _ { i } + H z _ { i } + I \right) ^ { 2 }
$$

可得以下线性方程组

$$
M \left[ \begin{array} { c } { F } \\ { G } \\ { H } \end{array} \right] = \left[ \begin{array} { c c c c } { \overline { { x ^ { 2 } } } - \overline { { x } } ^ { 2 } } & { \overline { { x y } } - \overline { { x } } \times \overline { { y } } } & { \overline { { x } } z - \overline { { x } } \times \overline { { z } } } \\ { \overline { { x y } } - \overline { { x } } \times \overline { { y } } } & { \overline { { y ^ { 2 } } } - \overline { { y } } ^ { 2 } } & { \overline { { y z } } - \overline { { y } } \times \overline { { z } } } \\ { \overline { { x z } } - \overline { { x } } \times \overline { { z } } } & { \overline { { y z } } - \overline { { y } } \times \overline { { z } } } & { \overline { { z ^ { 2 } } } - \overline { { z } } ^ { 2 } } \end{array} \right] \left[ \begin{array} { c } { F } \\ { G } \\ { H } \end{array} \right] = 0
$$

${ M } _ { i }$ 为 $3 x 3$ 的协方差矩阵，对其进行协方差分析

$$
M _ { i } = \frac { { \cal { I } } } { k } \left( { p _ { i I } \cdot \overline { { { p } } } _ { i I } } \right) ^ { T } \left( { p _ { i I } \cdot \overline { { { p } } } _ { i I } } \right)
$$

$$
M _ { i } \times { \pmb \nu } _ { i } ^ { ( j ) } = \lambda _ { i } ^ { ( j ) } \times { \pmb \nu } _ { i } ^ { ( j ) } , i = \{ 1 , 2 , 3 \}
$$

其中， $\overline { { p } } _ { i }$ 是邻域的重心； $\lambda _ { i } ^ { ( j ) }$ 和 $\nu _ { i } ^ { ( j ) }$ 分别表示特征值及特征向量，若特征值满足 $\lambda _ { i } ^ { ( 1 ) } { \leqslant } \lambda _ { i } ^ { ( 2 ) } { \leqslant } \lambda _ { i } ^ { ( 3 ) }$ ，则 $\nu _ { i } ^ { ( 1 ) }$ 即点 $p _ { i }$ 的法向量 $\overrightarrow { n _ { i } }$ 。

# 2.3.2法向量定向

考虑到估计得到的法向量 $\overrightarrow { \pmb { n } _ { i } }$ 方向具有不确定性，并没有确定法向量的矢量方向，故采用视线方向进行统一以保证法向量方向的一致性，已知视点为 $\mathrm { \Delta V _ { p } }$ ，对所有法向量定向，使它们朝向视点方向，需满足如下公式：

$$
\overrightarrow { n _ { i } } \cdot \left( V _ { p } - P _ { i } \right) > 0
$$

# 3 道面坡度估计

稀疏子空间的平面优化方法，可有效减少异常值对坡度估计的影响，但其最优平面采用随机搜索获取，极有可能得到局部最优解，增加平面迭代次数等问题。为了减少随机取值带来的影响，本章在余弦 $\mathbf { k }$ -means聚类中引入余弦距离，解决聚类初始点随机取值问题。表1列出了本章中用到的重要公式变量的定义。

表1公式变量定义  
Tab.1Formula variable definition   

<html><body><table><tr><td>公式变量</td><td>定义</td></tr><tr><td>a.b</td><td>单个平面任意两法向量</td></tr><tr><td>dist(a,b)</td><td>a与的欧氏距离</td></tr><tr><td>cos(a,b)</td><td>a与的余弦相似度</td></tr><tr><td>a</td><td>a与的标准化向量</td></tr><tr><td></td><td></td></tr><tr><td>diste (a,b)</td><td>a与b的余弦距离</td></tr><tr><td>cd</td><td>欧式空间中任意两个标准化向量</td></tr></table></body></html>

# 3.1余弦聚类

在单个平面提取所得的法向量中，任意取两个向量 $\vec { \pmb { a } } , \vec { \pmb { b } }$ 在欧式空间中表示为 $\stackrel {  } { \pmb { a } } = ( a _ { 1 } , a _ { 2 } , \cdots , a _ { n } )$ ， $\pmb { \vec { b } } = ( b _ { 1 } , b _ { 2 } , \cdots , b _ { n } )$ ， $\overset { \vartriangle } { \boldsymbol { a } }$ 与 $\vec { \pmb { b } }$ 的欧氏距离 $\vec { d i s t } ( \vec { a } , \vec { b } )$ 为

$$
d i s t ( \stackrel {  } {  } , \stackrel {  } {  } ) = \sqrt { \sum _ { i = 1 } ^ { n } ( a _ { i } - b _ { i } ) ^ { 2 } }
$$

$\stackrel {  } { \pmb { a } }$ 与 $\vec { \pmb { b } }$ 的余弦夹角定义为余弦相似度，在法向量定向章节已保证向量朝向一致，故此时 $\cos ( \vec { a } , \vec { b } )$ 取值分布在[0.1]。

$$
\cos ( \vec { a } , \vec { b } ) = \frac { \displaystyle \sum _ { k = 1 } ^ { n } a _ { k } b _ { k } } { \sqrt { \displaystyle \sum _ { k = 1 } ^ { n } a _ { k } ^ { 2 } } \sqrt { \displaystyle \sum _ { k = 1 } ^ { n } b _ { k } ^ { 2 } } } = \frac { \displaystyle \sum _ { k = 1 } ^ { n } a _ { k } b _ { k } } { \displaystyle \vert \vert \vec { a } \vert \vert \cdot \vert \vert \vec { b } \vert \vert }
$$

余弦相似度是利用向量夹角的余弦值来刻画相似性，注重维度间相对层面的差异[25]，继续对上述公式推导。首先对欧式空间任意向量 $\stackrel {  } { \ b { a } } = ( a _ { 1 } , a _ { 2 } , \cdots , a _ { n } )$ ， $\pmb { \vec { b } } = \left( b _ { 1 } , b _ { 2 } , \cdots , b _ { n } \right)$ 进行标准化：

$$
\tilde { \pmb { a } } = \left( \frac { a _ { 1 } } { \lVert \vec { \pmb { a } } \rVert } , \frac { a _ { 2 } } { \lVert \vec { \pmb { a } } \rVert } , \cdots , \frac { a _ { n } } { \lVert \vec { \pmb { a } } \rVert } \right)
$$

$$
{ \tilde { \vec { b } } } = \left( { \frac { a _ { 1 } } { \lVert { \vec { b } } \rVert } } , { \frac { a _ { 2 } } { \lVert { \vec { b } } \rVert } } , \cdots , { \frac { a _ { n } } { \lVert { \vec { b } } \rVert } } \right)
$$

将标准化向量 $\tilde { \vec { \mathbf { a } } } , \tilde { \vec { \mathbf { b } } }$ ，带入式(2)得 $\tilde { \vec { a } }$ 与 $\tilde { \vec { \pmb { b } } }$ 的余弦相似度

$$
\cos ( \tilde { \vec { a } } , \tilde { \vec { b } } ) = \sum _ { i = 1 } ^ { n } \tilde { a } _ { i } \tilde { b } _ { i } = \sum _ { i = 1 } ^ { n } { \frac { a _ { i } } { | | \vec { a } | | } } { \frac { b _ { i } } { | | \vec { b } | | } } = \sum _ { i = 1 } ^ { n } a _ { i } b _ { i } / | | \vec { a } | | \cdot | | \vec { b } | | = \cos ( \vec { a } , \vec { b } )
$$

即向量 $\vec { \pmb { a } } , \vec { \pmb { b } }$ ，在标准化前后的余弦相似度保持不变，此时向量长度为1，式(16)可简化为 $\sum _ { k = 1 } ^ { n } a _ { k } b _ { k }$ ，计算效率得到有效提高。

聚类初始点的选取是基于欧式距离的 $\mathbf { k }$ -means算法研究的热点问题[26]。其核心是在第一次迭代选点时对类别进行预测，使选点更接近于理想值，以减少聚类过程的迭代次数和计算开销。初始点的选取遵循以下原则：距离大的样本分到同一类的可能性小；相反，距离小的样本分到同一类的可能性大[27]。因此，聚类的初始迭代需要选取K个相互之间距离较远的样本以取得较好的效果。如何在余弦聚类中对空间向量进行第一轮选点成为接下来需要解决的问题。如果采用余弦相似度小作为初始选点的方式，向量 $\stackrel { \longrightarrow } { \pmb { a } _ { I } } , \stackrel { \longrightarrow } { \pmb { a } _ { 2 } }$ 作为初始的两点，距离两点尽可能远的 $\overrightarrow { \pmb { a } _ { 3 } }$ 是极难找到的[28]。因为在欧氏距离中：其第三点 $\left| a _ { 3 } \right|$ 选取采用分别到 $a _ { 1 } , a _ { 2 }$ 的距离和或积的最大值，然而和或积在余弦中是没有意义的，无法表示相距较远，因此引入余弦距离 $d i s t ^ { c } ( \stackrel { - } { \pmb { a } } , \vec { \pmb { b } } )$

$$
d i s t ^ { c } ( \stackrel {  } { c } , \stackrel {  } { d } ) = 1 - \cos ( \stackrel {  } { c } , \stackrel {  } { d } )
$$

$$
d i s t ^ { c } ( \vec { \pmb { c } } , \vec { d } ) = \frac { 1 } { 2 } d i s t ^ { 2 } ( \vec { \pmb { c } } , \vec { d } )
$$

余弦距离的引入，弥补了余弦 $\mathbf { k }$ -means聚类缺少距离度量的缺点。同时作为纽带将基于欧氏距离的 $\mathbf { k }$ -means算法迁移到本文余弦聚类算法之中，通过式(25)可知余弦距离在刻画距离的方法上与欧氏距离一致，并且与欧氏距离呈正相关，因此余弦距离可表达与欧式距离一样的距离意义；同时余弦距离完全由余弦相似度决定，聚类效果与余弦相似度一致。所以将样本点之间欧式距离远，作为聚类初始点的思想应用于余弦 $\mathbf { k }$ -means聚类，依次寻找余弦距离相对远的K个点。该方法帮助余弦k-means聚类有条件的选取初始聚类中心，以减少初始聚类中心随机取值的不利影响。设计聚类流程如图3所示。

$$
d i s t ^ { c } ( \stackrel {  } {  } , \stackrel {  } {  } ) = 1 - \cos ( \stackrel {  } {  } , \stackrel {  } {  } )
$$

由于 $\cos ( \vec { a } , \vec { b } )$ 取值分布在[0.1]，故 $d i s t ^ { c } ( \vec { \pmb { a } } , \vec { \pmb { b } } )$ 取值分布在0到1，且余弦距离与向量在空间上夹角大小呈正相关，即两向量在空间上夹角越小，余弦距离数值越小，两向量越容易分为一类，故余弦距离可作为衡量距离的指标。

取欧式空间中任意两个标准化向量 ${ \vec { \pmb { c } } } = \left( c _ { 1 } , c _ { 2 } , \cdots , c _ { n } \right)$ ，$\vec { \pmb { d } } = \left( d _ { 1 } , d _ { 2 } , \cdots , d _ { n } \right)$ 继续推导欧氏距离 $\stackrel { \triangledown } { \boldsymbol { d i s t } } ( \vec { \pmb { c } } , \vec { \pmb { d } } )$ ，余弦相似度 $\cos ( \stackrel {  } { c } , \stackrel {  } { d } )$ ，余弦距离 $d i s t ^ { c } ( \stackrel {  } { c } , \stackrel {  } { d } )$ 三者之间的关系。将标准化向量$\left. \vec { \pmb { c } } \right. ^ { 2 } = \sum _ { k = 1 } ^ { n } c _ { k } ^ { 2 } = 1 , \left. \vec { \pmb { d } } \right. ^ { 2 } = \sum _ { k = 1 } ^ { n } d _ { k } ^ { 2 } = 1$ ，结合式(16)得

$$
\cos ( { \vec { c } } , { \vec { d } } ) = { \frac { \displaystyle \sum _ { k = 1 } ^ { n } c _ { k } d _ { k } } { \sqrt { \displaystyle \sum _ { k = 1 } ^ { n } c _ { k } ^ { 2 } } \sqrt { \displaystyle \sum _ { k = 1 } ^ { n } d _ { k } ^ { 2 } } } } = { \frac { \displaystyle \sum _ { k = 1 } ^ { n } c _ { k } d _ { k } } { \displaystyle \| { \vec { c } } \| \cdot \left\| { \vec { d } } \right\| } } = \sum _ { k = 1 } ^ { n } c _ { k } d _ { k }
$$

由式(15)得

$$
d i s t ^ { 2 } ( \vec { c } , \vec { d } ) = \sum _ { i = 1 } ^ { n } \bigl ( c _ { i } - d _ { i } \bigr ) ^ { 2 } = \sum _ { i = 1 } ^ { n } \bigl ( c _ { i } ^ { 2 } - 2 c _ { i } d _ { i } + d _ { i } ^ { 2 } \bigr ) = 2 - 2 \sum _ { i = 1 } ^ { n } c _ { i } d _ { i }
$$

结合式(21)，得关系式 $\cos ( \stackrel { - } { c } , \stackrel {  } { d } ) = 1 - \frac 1 2 d i s t ^ { 2 } ( \stackrel {  } { c } , \stackrel {  } { d } )$ ，可知余弦相似度与欧式距离具有直接函数关系，两者间存在紧密联系。将式(20)代入得到欧氏距离 $\stackrel { \triangledown } { d i s t ( \vec { c } , \vec { d } ) }$ ，余弦相似度 $\cos ( \stackrel {  } { c } , \stackrel {  } { d } )$ ，余弦距离 $d i s t ^ { c } ( \vec { \pmb { c } } , \vec { \pmb { d } } )$ 三者的关系如下：

$$
\cos ( \stackrel { - } { c } , \stackrel {  } { d } ) = 1 - \frac { 1 } { 2 } d i s t ^ { 2 } ( \stackrel { - } { c } , \stackrel {  } { d } )
$$

![](images/bcc9be9a799c2db2d0adadaeac071a87b5a16493f49ba60af777fb3b5e472c80.jpg)  
图3聚类流程  
Fig.3Clustering flowchart

# 3.2 累加拟合

经余弦聚类后的斜面和水平面法向量夹角 $r _ { \theta }$ 可定义为 [29]:

$$
r _ { \theta } = \arctan \frac { \lVert \vec { n } _ { i } \times \vec { n } _ { j } \rVert } { \vec { n } _ { i } \times \vec { n } _ { j } }
$$

其中： $\vec { \pmb { n } } _ { i }$ 表示斜坡面任一点 ${ \boldsymbol { p } } _ { i }$ 的法线； $\vec { \pmb { n } } _ { j }$ 表示地面任一点 ${ p } _ { j }$ 的法线。

采用随机取值方法的坡度估计结果常具有较大的不确定性，故采用累加拟合的方法完成坡度估计，夹角值取 $\overline { { r _ { \theta } } }$ ，其公式如下：

$$
\overline { { r _ { \theta } } } = \frac { 1 } { n } \sum _ { \theta = 1 } ^ { n } r _ { \theta }
$$

# 4 实验与分析

# 4.1实验平台

本文实验所用移动机器人结构如图4所示，其底盘采用两主动轮、两驱动轮的四轮结构，主动轮控制方向调整，驱动轮提供行进动力，从而完成移动机器人的运动过程。机器人配备了基于二代Kinect的RGB-D视觉相机，用以感知环境信息，并搭载CoreI7主机来完成数据处理和运动控制。

# 4.2 与常用方法比较

为验证本文提出的融合型算法的优越性，将其与基于传统最小二乘法的坡度估计方法，以及基于稀疏子空间法的坡度估算方法进行对比。在华盛顿大学公开数据集Rgb-scenes-v2中选取了数据集中角度为 $9 0 ^ { \circ }$ 的墙体与地面(模拟道面坡度为 $9 0 ^ { \circ }$ )用于仿真实验分析，数据集点云图如图5所示。

![](images/f6550566b17456a041e34843d8a2e44a240a01bc0433128ab8a378dda02c382f.jpg)  
图4实验平台机器人结构

![](images/6dfab3f028dcb7c4ab94661fe86c9a88dfd14db72eb56b5eb58f0f4e484f3dbd.jpg)  
Fig.4Experimental platform robot structure

本文所述融合型算法实验步骤如下：

对滤波处理后的数据集进行平面分割，图6为数据集分割后得到的斜面(蓝色)和水平面(红色)。

![](images/3c3850da239f894b56a1485332aa8edb81556adedb349415f4dab57d99fc6df5.jpg)  
图5数据集点云图  
Fig.6Plane segmentation result

对向量提取的拟合邻域值 $k$ 取值进行讨论：当拟合邻域范围的k足够大时，得到的法向量效果更好，噪声小，但随之而来的是成倍增长的运算时间和计算压力，为了保证运算的实时性和准确性。对数据集点云不同邻域范围的k值进行实验验证：对于坡度为 $9 0 ^ { \circ }$ 的两平面，分别取 $k$ 为25，35，50，60，100，1000，2000进行实验。图7为不同 $k$ 值时得到的坡道夹角情况，随着 $k$ 值增大，夹角变化趋于稳定，测量值更接近于真实值。

![](images/bfc393de867619c949b8264a950aebcf4272be6b07b8acfdb6150ca1a2ea941b.jpg)  
图6平面分割结果  
图7坡道夹角随k值变化情况 Fig.7Angle change withkvalue

实验结果表明，当 $k$ 小于100时，所得角度与真实值误差在 $1 ^ { \circ }$ 以上，且具有较多异常值；当 $k$ 大于100时，所得角度其误差变化稳定在 $0 . 5 ^ { \circ }$ 左右，综合考虑选择 $k = 1 0 0$ 作为邻域值。根据拟合邻域值 $k$ 分别提取斜面和水平面法向量，如图8、9所示。

![](images/b49946165f0517521b4c55fa93a57438c456f8986906095618f108842c131a0d.jpg)  
图8斜面法向量提取

![](images/3379c19669b41d87e4636a4a8e2935d00ba02fd53529e824113914bd9449004c.jpg)  
Fig.5Data set point cloud image   
图9水平面法向量提取  
Fig.9Normal vector extraction of horizontal plane

对单个平面的向量进行余弦聚类后采用累加拟合，累加拟合次数在与随机取值对比后，选择设定为100次。部分结果如表2所示，全部数值对比情况如图10所示，可知累加拟合方法在取值100次后趋于稳定，而随机取值方法计算结果波动仍较大，再次证明引入累加拟合后，极大保证了融合型算法的估计精度。

表2累加拟合与随机取值部分对比  
Tab.2Comparison between cumulative fitting and random value   

<html><body><table><tr><td>计算次数</td><td>随机取值 累加拟合</td></tr><tr><td>1</td><td>90.5649 90.8025</td></tr><tr><td>2</td><td>89.3503 90.7853</td></tr><tr><td>3</td><td>90.8679 90.7172</td></tr><tr><td>4 90.5569</td><td>90.7679</td></tr><tr><td>5</td><td>90.6058 90.7852</td></tr><tr><td>： ：</td><td>：</td></tr><tr><td>98</td><td>90.9083 90.5353</td></tr><tr><td>99</td><td>90.6522 90.5346</td></tr><tr><td>100</td><td>90.5425 90.5460</td></tr><tr><td>101</td><td>90.5425 90.5471</td></tr><tr><td>102 90.7795</td><td>90.5480</td></tr></table></body></html>

平均

![](images/ce35f633b516623dd8d20d2501e4feb29de413c8be65514e8f344fedda153134.jpg)  
Fig.8Normal vector extraction of inclined plane   
图10累加拟合与随机取值对比  
Fig.1OComparison chart ofcumulative average and random value 最终本文算法在数据集Rgb-scenes-v2中 $9 0 ^ { \circ }$ 墙面坡度

下，估计结果为 $9 0 . 5 5 ^ { \circ }$ ，测量相对误差为 $0 . 5 5 ^ { \circ }$ ，与其余两种算法的估计结果对比见表3。图11、12分别给出了基于传统最小二乘法提取的斜面及水平面法向量；基于稀疏子空间聚类法结果引用文献[11]数据。由对比结果可知，在数据集中相较最小二乘法及稀疏子空间算法，本文提出的融合型算法估计精度更高，相对误差分别降低了 $1 . 2 1 \%$ 和 $2 . 1 3 \%$ 。

![](images/dd42ad38efe0a4377524527fbc2816417e55697419c27a88b307b80b7a83aae4.jpg)  
图11斜面提取法向量

![](images/476ed7e88c9120d1cbb5a95b005fea1cb046782c0ccd4a8a25704fb325271152.jpg)  
Fig.11 Oblique extraction normal vector

Tab.3Analysis of Data set measurement results   

<html><body><table><tr><td>测量方法</td><td>测量结果测量相对误差/°</td><td></td><td>测量相对误差/%</td></tr><tr><td>最小二乘法</td><td>88.36</td><td>1.64</td><td>1.82</td></tr><tr><td>稀疏子空间</td><td>87.53</td><td>2.47</td><td>2.74</td></tr><tr><td>本文方法</td><td>90.55</td><td>0.55</td><td>0.61</td></tr></table></body></html>

此外，如图13在实际环境中，搭建坡度分别为 $1 6 ^ { \circ }$ 、$4 7 ^ { \circ }$ 、 $6 0 ^ { \circ }$ 的斜坡平面，对比最小二乘法与本文方法在实际应用场景下不同坡度的具体表现。测量结果见表4，相较最小二乘算法，本文方法坡度估计准确率仍保持在较高水准，在所给的三种坡度下平均误差为 $0 . 8 6 ^ { \circ }$ ，较最小二乘算法的平均误差降低 $1 . 4 3 ^ { \circ }$ 。

![](images/450d4779c1757189d1d764a09ed5f8cd8cd6a4411362746cfebe3ff06d9396fc.jpg)  
图12水平面提取法向量  
图13室内搭建坡度环境  
Fig.13Buildinga sloped environment indoors

表3数据集测量结果分析  
表4实际环境测量结果分析  
Tab.4Analysis of actual environmental measurement results   

<html><body><table><tr><td>测量方法</td><td>斜坡角度</td><td>测量结果</td><td>测量相对误差/</td><td>平均误差/</td></tr><tr><td rowspan="3">最小二乘法</td><td>16</td><td>18.63</td><td>2.63</td><td rowspan="3">2.29</td></tr><tr><td>47</td><td>49.27</td><td>2.27</td></tr><tr><td>60</td><td>61.97</td><td>1.97</td></tr><tr><td rowspan="3">本文方法</td><td>16</td><td>16.89</td><td>0.89</td><td rowspan="3">0.86</td></tr><tr><td>47</td><td>47.75</td><td>0.75</td></tr><tr><td>60</td><td>60.93</td><td>0.93</td></tr></table></body></html>

# 4.3实际环境下的坡道角度识别

为进一步验证融合型算法在室外环境的有效性及可行性，选取搭载ROS系统的RGB-D移动机器人在户外坡道环境下进行半物理仿真实验，实验环境如图14。

![](images/10882dda059bcc0cca8bfe6a22896a92de6a83a52201a1bb17302ccf34c9cd76.jpg)  
图14移动机器人与坡道相对位置

未处理的坡道点云如图15所示，其点云边缘存在可见的离群点，离群点对于法向量的提取是十分不利的，需要对其进行滤波处理。

![](images/c7e24867d28ce37a8c2c41a3e8d7da25973335dbc335ac7ff577cf8a59065453.jpg)  
Fig.l2 Horizontal plane extraction normal vector   
图15坡道点云图

本文使用统计滤波方法对原点云进行处理，滤波参数设置为： $m = 2 0 , \alpha = 2$ 。滤波后点云如图16，被过滤的点云离群点如图17，可见点云离群点已被有效滤除。

![](images/015ee78823bedbbedbe113982649f025a7168a7827433a53a34402bb6c42e09b.jpg)  
Fig.l4The position of the mobile robot and the slope   
图16滤波后斜坡点云

![](images/7e4d4a2add51d9162cd34bafe4c6bb8a49a3f762bf9bb19b4c758645d32f4d26.jpg)  
Fig.15Point cloud map of slope   
Fig.16Slope point cloud after filtering   
图17斜坡点云外围离群点  
Fig.17Outliers on the periphery of the slope point cloud

经滤波处理后的点云，其数据点较多，需要在分割的同时进行降采样处理，以满足点云设定要求。分割后的点云如图18所示，其中水平面呈红色，坡道呈蓝色，绿框标注部分为该坡道一处台阶凸起，该凸起对于法向量的生成存在干扰；经平面分割，水平面(红色)和坡道(蓝色)均残存部分凸起，且该坡道点云点数为12405，远超过设定阈值，故使用直通滤波法滤除绿框所示的凸起道面点云，直至所含点云个数低于10000。

平面分割后进行法向量提取，此时法向量提取阈值 $k$ 设定为100，斜面和水平面法向量提取结果如图19、20所示。其中共提取斜面法向量4329组，水平面法向量4830组；通过余弦聚类对异常值进行聚类剔除，之后采用累加拟合，拟合次数设置为100，最终得到该斜坡角度为12.5度。

![](images/527742eadbf807c824a29913f0e2155444bcf4688ff45973b6c91001ad2721e4.jpg)  
图18坡道点云平面分割

![](images/5dd34d8a96e6638a1d13f212825f530f8aa8c5f7b2d45129ebed9b50a90325bb.jpg)  
Fig.18Point cloud plane segmentation of slope   
图19斜面法向量提取

![](images/f5a82d2b03847886df987326fcae5e3fbdef07f764378d2b7da490f138ae0e79.jpg)  
Fig.19Normal vector extraction of inclined plane   
图20水平面法向量提取  
Fig.20Normal vector extraction of horizontal plane

# 5 结束语

本文提出一种面向实际应用的视觉RGB-D机器人道路坡度估计融合型算法。针对坡度估计算法普遍局限于仿真，在真实环境中估计精度不高的问题，设计并实现了融合统计滤波、平面分割、法向量提取、余弦聚类和累加平均等多种方法的可用于真实环境的坡道估计方法，并与传统方法比较分析。结果表明所提出的融合型算法在降低估计误差、提高坡度估计精度上有显著优势。在数据集下，相较传统最小二乘法与稀疏子空间算法，基于新融合算法的坡道估计误差分别降低 $1 . 2 1 \%$ 、 $2 . 1 3 \%$ ；在真实环境下，本文方法较最小二乘方法平均误差降低 $1 . 4 3 ^ { \circ }$ 。为其后续移动机器人在真实环境中的路径规划和移动避障提供了精确环境信息保障。

# 参考文献：

[1]Hess W,KohlerD,Rapp H,et al.Real-time loop closure in 2DLIDAR

SLAM[C]//Proc of 2016 IEEE International Conference on Robotics

and Automation. Stockholm: IEEE,2016: 1271-1278.   
[2]庞帆，危双丰，师现杰，等．激光雷达惯导耦合的里程计与建图方法 [J]．计算机应用研究，2021，38（7):2188-2193.(Pang Fan，Wei Shuangfeng,Shi Xianjie,et al. Odometry and mapping method for coupling LiDAR and IMU[J]. Application Research of Computers,2021, 38 (7): 2188-2193.)   
[3] Mur A R, Tardos JD. ORB-SLAM2: An open-source SLAM system for monocular,stereo,and RGB-D cameras [J]. IEEE Trans on Robotics, 2017,33 (5): 1255-1262.   
[4] Campos C, Elvira R, Juan J, et al. ORB-SLAM3: An Accurate OpenSource Library for Visual,Visual-Inertial and Multi-Map SLAM[J]. arXiv preprint arXiv: 2007.11898.   
[5] 潘林豪，田福庆，应文健，等．基于直接法的视觉同时定位与地图构 建技术综述[J]．计算机应用研究,2019,36(4):961-966.(Pan Linhao, Tian Fuqing,Ying Wenjian,et al. Survey on direct-method visual simultaneous localization and mapping [J]. Application Research of Computers,2019,36 (4): 961-966.)   
[6] 王梓强，胡晓光，李晓筱，等．移动机器人全局路径规划算法综述 [J]．计算机科学,2021,48 (10):19-29.(Wang Ziqiang,Hu Xiaoguang, Li Xiaoxiao,et al. Overview of Global Path Planning Algorithms for Mobile Robots [J]. Computer Science,2021,48 (10):19-29.)   
[7] 梁栋，王鹏基，刘良栋．一种基于LIDAR 的精确月球软着陆目标点 选定方法[J]．空间控制技术与应用,2009,35(6):24-29.(Liang Dong, Wang Pengji, Liu Liangdong. A LIDAR-Based Autonomous Landing Site Selection Method for Pinpoint Lunar Soft Landing[J].Aerospace Control and Application,2009,35 (6): 24-29.)   
[8] 张泽旭，王卫东，崔平远，等．一种行星软着陆地形风险评估方法 [J]．哈尔滨工业大学学报,2011,43 (5):25-29.(Zhang Zexu,Wang Weidong, Cui Pingyuan,et al.An algorithm ofterrain hazard assessment forplanetarysoftladgJ]JoualofHabinIstuteochology. 2011,43 (5): 25-29.)   
[9]王亚林，刘鹏，吴辉阳，等．碎石堆构造小行星表面地形分析与仿真 验证[J].深空探测学报,2019,6(5): 481-487.(Wang Yalin,LiuPeng, Wu Huiyang，et al. Terrain Analysis and Simulation Verification on Rubble-Pile-Constructed Asteroid Surfaces [J]. Journal of Deep Space Exploration,2019,6 (5): 481-487.)   
[10] Li Boyuan, Zhang Jiawei,Du Haiping,et al. Two-layer structure based adaptive estimation for vehicle mass and road slope under longitudinal motion [J]. Measurement,2017,95: 439-455.   
[11]李海波，曹云峰，丁萌，等．基于三维点云聚类的坡度估计方法[J]. 计量学报,2018,39(3):4-309.(LiHaibo,CaoYunfeng,DngMeng, et al.A Method of Slope Estimation Based on Clustering of Threedimensional Point Cloud[J].Acta Metrologica Sinica,2018,39 (3): 304- 309.）   
[12]白莎莎，张海洋，许世东，等．基于机载激光雷达点云的雪道坡度提 取算法[J]．应用光学,2021,42(3):481-487.(Bai Shasha,Zhang Haiyang,Xu Shidong,et al. Slope extraction algorithm of ski tracks based on airborne LIDAR point cloud [J]. Journal of Applied Optics, 2021, 42 (3): 481-487.)   
[13] Debeunne C,Vivet D.A Review of Visual-LiDAR Fusion based SimultaneousLocalization and Mapping[J].Sensors,2020,20(7): 2068- 2088.   
[14]周治国，曹江微，邸顺帆.3D激光雷达 SLAM算法综述[J].仪器仪 表学报,2021,42(9): 13-27.(Zhou Zhiguo,Cao Jiangwei,Di Shunfan. Overview of 3D Lidar SLAM algorithms [J]. Chinese Jourmal of Scientific Instrument,2021,42 (9): 13-27.)   
[15]李尚璁．基于深度视觉信息的四足机器人野外可通过性分析[D]. 济南：山 东 大学，2020.(Li Shangcong.Off-Road Environmental Travers ability Analyzing for Quadruped Robots Based on Depth Sensing Information [D]. Jinan: Shandong University,2020.) [16]吕宁，肖剑，高健，等．基于改进 MRF 的冲压件轮廓缺陷图像分割 算法[J].锻压技术,2022,47(4):101-109.(Lyu Ning,Xiao Jian,Gao Jian，et al. Image segmentation algorithm on contour defects for stamping part based on improved MRF [J]．Forging & Stamping Technology,2022,47 (4):101-109.) [17] Han Song,Liu Xiaoping,Han Xing,et al.Visual Sorting of Express Parcels Based on Multi-Task Deep Learning [J]. Sensors,2020,20 (23):   
6785-6803. [18] Young JK,Seon IK,Yeol DY,etal.Visual Positioning System Based on 6D Object Pose Estimation Using Mobile Web [J].Electronics,2022,   
11 (6): 865-879. [19]彭育辉，郑玮鸿，张剑锋．基于深度学习的道路障碍物检测方法[J]. 计算机应用,2020,40(8):2428-2433.(Peng Yuhui,Zheng Weihong, Zhang Jianfeng.Deep learning-based on-road obstacle detection method [J].Journal of Computer Applications,2020,40 (8):2428-2433.) [20] QiCR,Su H,Mo K,et al.PointNet: Deep learning on point Sets for 3D Classification and Segmentation [C]//Proc of 2O17 IEEE Conference on Computer Vision and Pattern Recognition.Piscataway:IEEE,2017:77-   
85. [21]王新杰，张莹，张东波，等．自主移动机器人路径规划中的点云噪声 处理[J].智能系统学报,2021,16 (4): 699-706.(Wang Xinjie,Zhang Ying, Zhang Dongbo,et al.Point cloud noise processing in path planning of autonomous mobile robot [J].CAAI Trans on Intelligent Systems,   
2021,16 (4): 699-706.) [22]吴庆华，朱思斯，周阳，等．基于随机采样一致性的规则棒料位姿识 别[J].传感器与微系统,2019,38(9):137-140.(WuQinghua,Zhu Sisi, Zhou Yang,et al. Regular sticks pose position and orientation recognition based on RANSAC[J].Transducer and Microsystem Technologies,2019, 38 (9):137-140.)   
[23]鲁荣荣，朱枫，吴清潇，等．一种板型物体混叠场景的快速分割算法 [J]．光学学报,2019,39(4):151-160.(Lu Rongrong,Zhu Feng,Wu Qingxiao,et al.A Fast Segmenting Method for Scenes with Stacked Plate-Shaped Objects [J].Acta Optica Sinica,2019,39 (4):151-160.)   
[24] Schnabel R,Wahl R,Klein R.Efficient RANSAC for Point-Cloud Shape Detection [J].Computer graphics forum,2010: 214-226.   
[25] Jain A K.Data clustering:5O years beyond K-means [J]. Pattern Recognition Letters,2010,31(8):651-666.   
[26]章永来，周耀鉴．聚类算法综述[J].计算机应用,2019,39(7):1869- 1882.(Zhang Yonglai, Zhou Yaojian.Review of clustering algorithms [J]. Journal of Computer Applications,2019,39(7):1869-1882.)   
[27]翟东海，鱼江，高飞，等．最大距离法选取初始簇中心的K-means 文 本聚类算法的研究[J].计算机应用研究,2014,31(3):713-715.(Zhai Donghai,Yu Jiang,Gao Fei,et al.K-means text clustering algorithm based on initial cluster centers selection according to maximum distance [J].Application Research of Computers,2014,31 (3): 713-715.)   
[28]王彬宇，刘文芬，胡学先，等．基于余弦距离选取初始簇中心的文本 聚类研究[J].计算机工程与应用,2018,54(10):11-18.(Wang Binyu, Liu Wenfen, Hu Xuexian,et al. Research on text clustering for selecting initial cluster center based on Cosine distance.Computer Engineering and Applications,2018,54(10):11-18.)   
[29]王飞，刘如飞，任红伟，等．利用道路目标特征的多期车载激光点云 配准[J]．测绘科学技术学报,2020,37(5):496-502.(Wang Fei,Liu Rufei,Ren Hongwei,et al.Multi-Stage Vehicle-Mounted Laser Point Cloud Registration Using Road Target Features [J]. Journal of Geomatics Science and Technology,2020,37(5):496-502.)