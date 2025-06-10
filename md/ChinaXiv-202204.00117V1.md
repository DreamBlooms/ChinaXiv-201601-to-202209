# 提高YFOSC光谱观测效率方法的研究

陈宇扬1,2,3、王传军1,²、范玉峰1,²、伦宝利1,2（1.中国科学院云南天文台，云南 昆明650216;2.中国科学院天体结构与演化重点实验室.云南 昆明 650216;3.中国科学院大学，北京100049)

摘 要：丽江2.4米望远镜作为目前国内最大口径的通用型光学望远镜，在我国的夜天文观测领域有着十分重要的地位。从近几年观测时间分配的整体情况来看，云南暗弱天体成像光谱仪（YFOSC）的光谱观测在丽江2.4米望远镜总观测时间中的占比是最多的，因此提高其光谱观测效率和数据质量就成为了保证望远镜稳定科学产出的关键因素。本文将从影响YFOSC 光谱观测效率的两个重要因素——星像入狭缝和望远镜闭环跟踪出发，对提高丽江2.4米望远镜YFOSC光谱观测效率和质量的方法进行介绍。

关键词：光谱观测星像入狭缝望远镜闭环跟踪中图分类号：P111.33 文献标识码：A 文章编号：

# 引言

光谱观测一直是丽江2.4米望远镜最重要的观测模式之一。2012年丽江2.4米望远镜卡焦终端快速切换系统的装配完成，使观测者可以根据观测需求选择云南暗弱天体成像光谱仪（YFOSC）、丽江系外行星探测仪（LiJET）、高色散光谱仪（HiRES）、多色测光系统（PICCD）和中国丽江积分视场光纤光谱仪（CHiLI）这五个科学终端，并且可以在不到半分钟的时间内进行相互切换[1I[2]，覆盖了长缝、光纤与积分视场光纤的光谱观测，实现丽江2.4米望远镜从测光观测到低、中、高色散光谱观测的科学需求。图1为丽江2.4米望远镜的光路图，YFOSC位于卡焦直通端口。YFOSC大部分的光谱观测目标通常较为暗弱、光度低，由此导致观测数据信噪比较低。在视宁度一定的情况下，望远镜跟踪精度是影响星像与YFOSC 的狭缝耦合效率的重要因素，而星像-狭缝耦合效率亦是决定光谱观测数据质量的决定因素。因此为了实现光谱观测的高质量与高效率，需要在丽江2.4米望远镜的望远镜控制系统（TCS）与导星系统硬件相互配合的基础上达到以下3个要求，以满足YFOSC光谱观测的科学需求：

1）小指向误差：目前丽江2.4米望远镜在使用指向模型修正后，其指向误差小于4"，可以保证观测目标不会“跑出”视场外；2）高精度入缝：指向观测目标后，确保星像与YFOSC狭缝耦合的高精度与高效率；3）高精度闭环跟踪：由于YFOSC大部分的光谱观测目标具有较暗弱的特点，故在一次观测过程中其科学采集相机的积分时间通常在1000秒以上，因此需要保证望远镜在此期间具备较高的闭环跟踪精度。

本文将围绕上述第2个和第3个影响YFOSC 光谱观测效率的技术难点，对如何在丽江2.4米望远镜现有的软件控制与导星系统硬件基础上实现高精度入缝与闭环跟踪进行阐述。本文第1节介绍了YFOSC 的光谱观测和影响 YFOSC 光谱观测效率的因素；第2节以望远镜闭环跟踪为例，介绍了点模式匹配算法的应用；第3节介绍了YFOSC星像入狭缝算法的优化；第4节对YFOSC光谱观测效率提升后的性能进行了测试；第5节进行了简要的总结

与展望。

![](images/be2cd61c2526f3527bc1f65f4ebcb9a5661ed06820af8f43b9766a43306151fc.jpg)  
图1丽江2.4米望远镜的光路

# 1YFOSC光谱观测的介绍

1.1YFOSC光谱观测流程

如图2所示，YFOSC的光谱观测是在望远镜观测控制系统（OCS）下的其各个子系统共同参与下完成的，其中TCS为望远镜控制系统；ICS 为仪器控制系统；OAS 为观测辅助系统。目前使用YFOSC进行一次光谱观测流程大致为：观测者利用望远镜观测控制系统所提供的用户接口输入待观测目标的坐标；待望远镜指向观测目标后，通过望远镜控制系统下达调整望远镜指向的命令，实现待观测目标在视场内的移动；计算待观测目标在YFOSC 相机靶面的坐标与狭缝中心位置坐标之差，小于阈值即认为该目标位于狭缝中心处或中轴线上；根据观测目标类型、视宁度等选择不同尺寸的狭缝，加入狭缝并拍摄一副狭缝像检查无误后，加入光栅，并开启导星相机进行闭环跟踪，同时根据待观测目标的科学需求选择光谱观测积分时间；观测完成后，检查数据并进行归档。

![](images/45ac5b70bb6685c6d58d8f1e3ce43569ec45cc6fd9064b8bff48f42044b8a227.jpg)  
Figure1 The optical path ofLijiang 2.4-metre telescope   
图2YFOSC光谱观测流程  
Figure 2 The process ofYFOSC spectrum observation

# 1.2卡焦导星系统

# 1.2.1卡焦导星系统的光学结构

导星系统作为闭环跟踪时的重要组成部分，是提高望远镜光谱观测效率的基础。为了满足YFOSC等卡焦终端仪器的高精度测光以及光谱观测的需求，2.4米望远镜卡焦端配备了基于偏置导星的自动导星系统[3]。如图3所示，通过卡焦焦点前的 $4 5 ^ { \circ }$ 反射镜提取望远镜主视场 $4 0 ^ { \prime } { \times } 4 0 ^ { \prime }$ 内 $4 ^ { \prime } { \times } 4 ^ { \prime }$ 的视场作为自动导星的视场。此外为了提高导星CCD的覆盖视场和极限探测星等，在其导星光路中增加了缩焦系统，缩焦后的导星视场从 $4 ^ { \prime } { \times } 4 ^ { \prime }$ 扩大到 $1 0 ^ { \prime } \times 1 0 ^ { \prime }$ ，每个 $1 3 . 5 \mu m$ 的像素对应0.24"天空角。经过测试，在视宁度为1.5"时，自动导星相机 2s积分时间可探测到的极限星等约为17mag。此外，自动导星机构可以取不遮挡仪器视场的

10'至20'环形区域作为导星视场，同时操作人员可以通过ag-rad命令实现 $4 5 ^ { \circ }$ 平面镜的径向移动，以解决导星相机视场内缺少亮星无法完成导星的问题。如图4所示。

![](images/f7b9c20b2c2b2014c948ac19fb5620ca5903d4323fcbfdd0147534fa614c1f15.jpg)  
图3丽江2.4米望远镜卡焦导星系统光路 Figure 3 The optical path of the Cassegrain AGU of Lijiang 2.4-metre telescope

![](images/34fd33000bb96914ec71e04f7415bc94124bd7fd6ada3bea8d541ddcdb4abb06.jpg)  
图4丽江2.4米望远镜导星视场  
Figure4TheFOVof theCassegrainAGcamera of Lijiang 2.4-metre telescope

1.2.2卡焦导星相机

随着使用时间的增加，原导星相机CCD靶面的坏点越来越多，导致探测极限星等的能力下降，极大影响了望远镜闭环跟踪时星像质心提取的成功率。因此丽江2.4米望远镜运维团组在2013年对自动导星相机进行更换，新旧导星相机的性能对比见表1。

# 表1新旧导星相机的性能对比

Table1 The performance comparison of the new and former AG-camera   

<html><body><table><tr><td>Compare items</td><td>The new AG-camera</td><td>The former AG-camera</td></tr><tr><td>The name of cameras</td><td>SBIG ST-3200ME</td><td>Customed by Manchester Scientific Instruments</td></tr><tr><td>The effective pixels</td><td>2184pixel×1472pixel</td><td>1024pixel×1024pixel</td></tr><tr><td>The pixel size</td><td>6.8μ m</td><td>13μ m</td></tr><tr><td>Full frame readout time</td><td>≈4seconds</td><td>≈10seconds</td></tr></table></body></html>

更换后的导星相机全幅读出时间由原来的10秒左右减少到4秒左右，缩短了寻找导星目标的时间，提高了误差采样和反馈的频率。此外新导星相机的量子效率峰值达 $87 \%$ ，提升了在同等观测条件下导星系统的极限探测星等[4][5]。然而由于导星系统改造时的经费有限，选择的导星相机的CCD靶面较小，对应天空角仅为 $2 ^ { \prime } { \times } 4 ^ { \prime }$ ，并没有充分利用好缩焦后的导星视场（ $1 0 ^ { \prime } { \times } 1 0 ^ { \prime }$ ），因此会在未来配置更大成像靶面的导星相机，从而提高丽江2.4米望远镜的光谱观测效率。

# 1.3影响YFOSC光谱观测效率的因素

对YFOSC星像入狭缝与望远镜闭环跟踪算法进行优化是提高YFOSC光谱观测效率的重要途径。经过在丽江2.4米望远镜上使用YFOSC进行多年的光谱观测后，通过总结经验，运维团队发现在视宁度一定的情况下，星像入狭缝的效率及望远镜闭环跟踪的精度是影响YFOSC光谱观测效率的主要因素。

# 1.3.1星像-狭缝耦合的效率与精度

对于原先的YFOSC的长缝光谱观测算法来说，在望远镜指向目标天区后，如果对单一目标进行光谱观测，首先需要计算目标星像质心与狭缝中心位置在像平面的坐标偏差量，然后由操作人员将该偏差量输入望远镜控制系统，望远镜的控制系统会将像平面的偏差量通过矩阵运算变换为望远镜的指向校正量。通常一次这样的操作难以保证星像与狭缝正确耦合，经过多次重复调整后，方可实现星像入狭缝，这一过程通常花费10分钟左右。此外将科学目标和在其附近选取的流量恒定的恒星(以下称为比较星)放入狭缝同时观测，便可同时获得穿过完全相同大气层且具有完全相同的观测条件的目标和比较星光谱。这需要在移动望远镜指向的同时旋转视场，使这两个目标均进入狭缝，花费的时间往往要超过10分钟。以YFOSC常用的天空角2.51"的狭缝为例，其狭缝宽度对应像平面的8.9个pixel。而从目标的定标精度可以反推出目标在狭缝中心的位置精度要求，因此对图5所示的单一目标进行光谱流量定标来说，至少要保证该目标一半以上的星光进入狭缝中，即该星像的质心与狭缝中心位置在像平面上的偏差量不大于4个pixel；而如果需要同时观测科学目标和比较星，如图6所示，由于科学目标和比较星在狭缝中心的偏差会引起光子损失的差异，从而给传统的流量定标方法引入新的弥散，因此科学目标和参考星的质心与狭缝中线耦合的偏差均应越小越好，通常在像平面上要保证误差小于0.5个pixel。

![](images/a4eea373e1e032afb20b83cc11cc650967c4e1f9902d794531b160035341c7fc.jpg)  
图5单一目标入缝

![](images/06c80537e10d852d25536254157757d681d5f97225da820214721e986698ad47.jpg)  
Figure5Acquire single starinto slit   
图6科学目标和参考星同时高精度入缝  
Figure 6 Acquire scientific target and the reference into slit at

the same time

人工调整望远镜实现上述过程不仅需要操作人员的实操经验，而且效率低下，浪费了宝贵的观测时间，此外星像入狭缝的精度也需要花费很多时间才能保证。

# 1.3.2望远镜闭环跟踪精度

原先的望远镜闭环跟踪算法是“单亮星”法。即在目标移动到狭缝中心位置后，启动导星相机并提取导星视场中“最亮”的星像质心，比较前后帧中该星像坐标偏移量，实现望远镜的闭环跟踪[]。然而如果视场中存在相邻的亮星干扰，该算法会将错误的星像坐标输入给望远镜控制系统，从而影响光谱观测的数据质量。因此闭环跟踪时要保证星像不能偏出狭缝，即在积分时间内要保证星像质心与狭缝中心位置的偏移量不超过1"。

基于以上两个影响YFOSC 光谱观测效率的关键因素的分析，需要针对这两个因素进行算法的优化，以提高整体的光谱观测效率。

# 2点模式匹配算法

在优化后的星像入狭缝算法与望远镜闭环跟踪中，均应用到了点模式匹配算法。该算法是在F.Murtagh 所提出的PPM（Point-Patrn Matching）算法的基础上进行了改进得到的[7],本节将以该算法在丽江2.4米望远镜闭环跟踪过程中的应用为例对该算法进行介绍。Murtagh点模式匹配算法的描述如下：首先建立出基于图像中各个星像特征（星等、邻星距）的特征向量集；接着对参考帧与比较帧的特征向量集进行相似度和阈值筛查，从而完成匹配。

# 2.1星像特征向量集的建立

建立星像的特征向量集通常有两种思路：

1）采用各个星的（视）星等 $\omega$ 和其邻星距 $d \big ( i , j \big )$ 作为星像的特征向量参数，这两个参

$i$ $P _ { i j } = \frac { \omega _ { j } } { d ^ { 2 } ( i , j ) }$ ，其中 $\omega _ { j }$ 为星 $i$ 的任一邻星 $j$ 的星等， $d ^ { 2 } \left( i , j \right)$ 为星 $i$ 的与星 $j$ 的星心之间的二维坐标下距离的平方值，即： $d ^ { 2 } \big ( i , j \big ) = \big ( x _ { i } - x _ { j } \big ) ^ { 2 } + \big ( y _ { i } - y _ { j } \big ) ^ { 2 }$ 。这样，就利用两个无相关性的特征量建立了星（20 $i$ 的 $\boldsymbol { R } ^ { N - 1 }$ 维特征向量集： $\left\{ P _ { i j } \middle | i \neq j , i \in N , 1 \leq j \leq N - 1 \right\}$ ，其中 $N$ 为图像中的所有星。

2）在构建星 $i$ 的特征 $P _ { i j }$ 时，不考虑邻星 $j$ 的星等，即： $P _ { i j } = d ^ { 2 } \big ( i , j \big )$ 。并以图像中的任一星 $i$ 为圆心，计算它和此图像中的星 $j$ 沿 $\mathrm { \Delta } \mathrm { X }$ 轴正方向、逆时针旋转所成的角度记为 $\theta _ { i j }$ ，并将星i的特征向量集 $P _ { i j }$ 按照向量集 $\left\{ \theta _ { i j } \big | 1 \leq j \leq N - 1 \right\}$ 的顺序进行升序排列。这个思路是目前 YFOSC光谱观测时所采用的星像特征提取方式，原因是仅靠短暂的积分时间，导星相机不足以完成高精度测光，使用第一种思路计算特征向量可能会引入误差。

![](images/ca2bda472d1aff940845f5cf3191b1c88cf7d4ceea9d17904bd3006f1c5b5ead.jpg)  
图7特征向量参数  
Figure 7 The feature vectors parameters

2.2基于特征向量集相似度的匹配星对提取

定义导星相机拍摄的第一帧图像为参考帧(Reference)，而后续帧为比较帧(Comparison)。完成星像特征向量的提取后，需要对特征向量进行匹配并计算其匹配相似度，以得到匹配的星对。对于比较帧中的任一星 $i "$ ，构建其特征向量集 $\left\{ P _ { i ^ { \prime } j ^ { \prime } } \middle | i ^ { \prime } \neq j ^ { \prime } , i ^ { \prime } \in N , 1 \leq j ^ { \prime } \leq N - 1 \right\}$ ，其中$P _ { i ^ { \prime } j ^ { \prime } } = d ^ { 2 } ( i ^ { \prime } , j ^ { \prime } )$ ，并计算 $P _ { i j }$ 与 $P _ { i ^ { \prime } j ^ { \prime } }$ 之间的欧氏距离（Euclidean Distance）。欧式距离即 $\mathfrak { n }$ 维空间中两个点之间的实际距离，其数学表达式如下：

$$
d { \binom {   } { x , y } } = { \sqrt { { \binom {  \quad  } { x - y } } ^ { T } { \binom {  \quad  } { x - y } } } } = { \sqrt { \sum _ { i = 1 } ^ { n } ( x _ { i } - y _ { i } ) ^ { 2 } } }
$$

其中： $\stackrel {  } { x } = ( x _ { 1 } , . . . , x _ { n } ) , \stackrel {  } { y } = ( y _ { 1 } , . . . , y _ { n } ) _ { \stackrel { \cdot } { x } }$ 1…,y")均是n维空间的向量。

从上述的一般性公式可以看出，欧氏距离 $d$ 的取值范围在0到正无穷之间。参考通常的相似度计算，其取值范围应该在 $\left[ - 1 , 1 \right]$ 之间，因此最好对 $d$ 求倒数将结果控制在(0,1]之间，作为衡量匹配相似度的参量：

$$
\omega _ { c o m p , r e f } = \frac { 1 } { 1 + d }
$$

公式（3）

由上式可知， $\omega _ { c o m p , r e f }$ 最接近1的星 $i$ 与 $i "$ 就是匹配相似度最优的星对，将整个星 $i "$ 记为星 $i _ { s u c c e e d } ^ { \prime }$ 。最后为了提高匹配算法的鲁棒性，防止匹配错误导致导星失败，星 $i _ { s u c c e e d } ^ { \prime }$ 还需要进行筛查。设定阈值条件：

$$
\left\{ \begin{array} { l l } { \displaystyle { \int \left( x _ { i _ { s u c e e d } } - x _ { i } \right) ^ { 2 } + \left( y _ { i _ { s u c e e d } } - y _ { i } \right) ^ { 2 } \leq \varepsilon _ { d } } } \\ { \displaystyle { \log \left( \frac { f l u x _ { r e f } } { f l u x _ { c o m p } } \right) \leq k \times \varepsilon _ { m a g } } } \end{array} \right.
$$

在上式中，分别计算了匹配星对 $i _ { s u c c e e d } ^ { , }$ 与 $i$ 的位置偏移误差以及星等差。其中 $ { \varepsilon } _ { d }$ 为偏移量阈值； $\mathit { f l u x } _ { \mathit { r e f } }$ 和 $\mathit { f l u x } _ { \mathit { c o m p } }$ 分别为比较帧与参考帧的总光度； $\varepsilon _ { m a g }$ 为星等阈值， $k$ 为可调系数。

以上所述即为点模式匹配算法在丽江2.4米望远镜闭环跟踪过程中的应用。在下一节中的星像入狭缝时的星表匹配法与此类似，由从星表中提取的指向天区图像对应闭环跟踪时的参考帧，而YFOSC相机所拍摄的天区图像对应闭环跟踪时的比较帧。

# 3星像入狭缝算法的优化

在使用YFOSC进行光谱观测的时候，望远镜指向观测目标后，还需要将目标星像移入到所要使用的狭缝的中心位置，使得星像与狭缝的中心位置正确耦合才能保证更多的星像能量最终到达相机，从而提高观测数据的信噪比以提高观测质量。因此，在光谱观测积分之前，需要利用相机拍摄的图像完成目标星像入狭缝的工作。

其中星像入狭缝的算法按时间顺序可分为“粗调”和“精调”两步，具体的流程如图8所示。

![](images/729316dfce38e9c514744eae0325d16194b8b156c036630f277cc09c12da34f7.jpg)  
图8星像入狭缝的流程  
Figure 8 The process of acquire stars into slit

3.1指向“粗调”

指向“粗调”的目的是为了将星像尽可能接近狭缝中心位置。在指向“粗调”时，星像坐标有两种解算方式：

1）使用Astrometry.net 解算星像坐标[8]l9]：当望远镜指向目标天区后YFOSC 相机开始曝光，并对其所得图像利用 Astrometry.net 解算视场内星像的世界坐标系（WCS）坐标。在成功解算出视场内星像的WCS坐标后，就可以指导望远镜指向正确的RA、DEC，从而使待观测目标星的质心像平面坐标接近狭缝中心位置。但由于Astrometry.net解算算法限制，通常视场内有3颗以上可探测的星像时才能进行成功解算。即便如此，Astrometry.net 解算出星像WCS坐标的高精确度使其依然成为指向“粗调”时首选的星像匹配方式。此外，利用Astrometry.net所产生的星像WCS坐标数据还可以用于监测望远镜的指向性能，并用来改进望远镜的指向模型。

2）星表模式匹配法：在目标天区中的可见星像较少时，Astrometry.net对星像坐标的解算可能会出现失败。这时就可以采用星表模式匹配法进行星像匹配。首先在进行观测之前，需要对待观测目标星对应天区的FITS图像进行预处理：添加焦面比例尺 $\boldsymbol { \mathscr { a } }$ 、场旋角ROT、目标星像的WCS坐标以及它们质心的像平面坐标（从星表中推算得到）等参数。然后应用点模式匹配算法，将由星表产中星像的像平面坐标与YFOSC相机获取到的星像像平面坐标进行点模式匹配，并将该偏移量的均值通过坐标变换传递到望远镜控制系统，实现望远镜的指向“粗调”，以达到星像与狭缝正确耦合的目的。

# 3.2指向“精调”

指向“精调”的目的是使星像质心位置与狭缝中心处尽可能重合。在完成指向“粗调”后，通常待观测目标星的像平面坐标是与狭缝中心位置像平面坐标距离最近的，故以狭缝中心为圆心，5\~10pixel为半径，利用 SExtractor 检索该圆形范围内的最亮源，并得到其质心坐标[10]。接下来逐步迭代计算目标星像在像平面上的质心坐标与其与狭缝中心位置坐标之间的偏差量以“精调”望远镜的指向，直到该偏差量小于公差范围内阈值。此外如果需要同时观测两个目标，则在视场内最亮的目标移入狭缝中心后，根据“粗调”时解算出的另一个自标所对应的像平面坐标旋转视场，从而实现两个目标均与狭缝正确耦合。

![](images/5d7781af6ad00d48d5c1fad3d1db3de5b086c4614b22de3622f0a72378ea644c.jpg)  
图9视场旋转前后的对比  
Figure 9 The Comparison of before and after FOV rotated

![](images/734ee2e1f117f45fc94244e1f654ec73430e8ea0257f226282a737609c3e5f4a.jpg)  
图10图9中星像的狭缝像

![](images/4a33d2272a368dff437be477d2ab957fb35f695bd1f4167936adaf9d28827e8d.jpg)  
Figure 10 The star-slit image of figure 9

图9为视场旋转前后的对比图，红框内为视场旋转前的天区，背景为视场旋转后的图像（目标星为17L08，拍摄时间UTC 2022-02-0318:57:36.945，曝光时间5s）。蓝、绿色箭头所指处均为待观测目标星，其中绿色箭头所指为CCD靶面中心（即狭缝中心）附近最亮的源。图10为该目标旋转视场后的狭缝像，该狭缝宽度对应天空角5.05"，所占像素数为17.67pixel。而如果该亮星恰为待观测目标星，即对单一目标进行光谱观测，则不需要旋转视场，如图11所示。

经过测试，优化后的YFOSC 星像入狭缝算法使星像与狭缝耦合时的各项指标均得到了提升，极大地提高了YFOSC光谱观测的效率。具体对比项如表2所示，其中人工星像入缝测试时间为UTC 2021-01-08 15:50:22.621至 2021-01-0821:59:15.340，观测目标为J0309、$\mathrm { p g } 1 0 1 2 \substack { + 0 0 8 }$ ；新星像入缝算法的测试时间为UTC 2022-02-0318:49:28.948至2022-02-0322:01:03.105，观测目标为HD105183、17L08。

Table 2 The comparison of formal and present guiding system

表2新旧星像入狭缝算法的比较  

<html><body><table><tr><td>Compare items</td><td>Artificially acquiring star(s) into slit</td><td>The new star(s)acquisition algorithm</td></tr><tr><td>The time of acquiring</td><td>Heavy reliance on the experience of operator,which usually</td><td>Less than 5 minutes under the correct</td></tr><tr><td>single star into slit</td><td>takes around 10 minutes.</td><td>operation.</td></tr><tr><td></td><td>After moving the telescope for the first time,the offset between</td><td></td></tr><tr><td>The precision of acquiring</td><td>the star centroid and the center of slit is about 1O pixel,and after</td><td>The offset between the star centroid</td></tr><tr><td>single star into slit</td><td>moving the telescope for several times,the offset between the</td><td>and the center of slit is less than 3</td></tr><tr><td></td><td>star centroid and the center of slit is about 5 pixel,as shown in</td><td>pixel,as shown in Figure 11.</td></tr><tr><td>The time of acquiring two</td><td>Figure 13 and Figure 14.</td><td></td></tr><tr><td></td><td>Heavy reliance on the experience of operator,which usually takes</td><td>Less than 5 minutes under the correct</td></tr><tr><td>stars into slit</td><td>more than 10 minutes.</td><td>operation.</td></tr><tr><td></td><td>After moving the telescope for the first time,the offset between</td><td></td></tr><tr><td>The precision of acquiring</td><td>both two stars centroid and the center of slit is about 1O pixel,</td><td>The offset between both two stars</td></tr><tr><td>two stars into slit</td><td>and after moving the telescope for several times,the offset</td><td>centroid and the central axis of the</td></tr><tr><td></td><td>between both two stars centroid and the center of slit is about 5</td><td>slit are both less than 3 pixel,as</td></tr><tr><td></td><td>pixel, while the FOV is rotated,both two stars centroid can not</td><td>shown in Figure 10.</td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td>located on the central axis of the slit accurately,as shown in</td><td></td></tr></table></body></html>

![](images/d25790e0f7acae08ebedc970d6ab29ac300a810d586a9269936ae462f137ed25.jpg)  
图11单一目标的狭缝像  
图12人工入缝狭缝像（双星）  
Figure 12 Artificially acquiring two stars into slit

![](images/3cc4f54b998b9e81bb7cec96e4cb9c03f85fee278bd17017a3d1c0c067ec3d28.jpg)  
Figure 11 The single star -slit image   
图13人工入缝法第一次移动望远镜后的狭缝像(单星）  
Figure 13Artificially acquiring single star into slit at the first time

![](images/4f87fd3c6449ebc0f99fe40b8e33db453c3786efddb54b00ccbdb70e7c7c25eb.jpg)  
图14单星人工入缝法多次移动望远镜后的狭缝像（单星）

# 4望远镜闭环跟踪算法的优化

为了保证光谱观测的质量，需要通过自动导星实现望远镜的闭环跟踪以保证目标星像始终在狭缝内。在实际观测过程中，当得到图10或图11所示的狭缝像后，就可以在YFOSC相机前加入光栅，同时启动导星相机开始望远镜的闭环跟踪，之后再进行曝光，以确保YFOSC在长期积分时间内光谱数据的质量。其流程如图15所示。

![](images/ca17869abb4ec5b2f210eaae29189d23afbfd90e84fef8280c37fb0322dcf559.jpg)  
Figure14Artificiallyacquiring single starinto slit forseveral times   
图15望远镜闭环跟踪流程图  
Figure 15 The process of telescope close -loop guiding

望远镜闭环跟踪是通过比较导星相机参考帧中的星 $i$ 与比较帧中的星 $i "$ 在像平面上的位置偏移量，校正望远镜的跟踪误差。其步骤如下：

1)计算星像的偏移量。对星 $i$ 与星 $i "$ 应用点模式匹配算法、匹配相似度计算与匹配筛查，从而得到成功匹配的星 $i _ { s u c c e e d } ^ { , }$ 并计算它们在像平面上的坐标（ $\cdot { } _ { x _ { i } }$ 'succeed,yisucceed ）与星 $i$ 的坐标 $( x _ { i } , y _ { i } )$ 在 $x$ 轴方向和 $y$ 轴方向偏移量的均值，即：

$$
\begin{array}{c} \left\{ \begin{array} { c } { \displaystyle { \sum _ { i \neq j \mathcal { T } _ { x } = \frac { i - 1 , i ^ { \prime } \mathrm { s t e c e d } ^ { - 1 } } { N } } ^ { n } } \Big ( x _ { i } , } \\ { \displaystyle { \sum _ { i \neq j \mathcal { T } _ { y } = \frac { i - 1 , i ^ { \prime } \mathrm { s t e c e d } ^ { - 1 } } { N } } ^ { n } } \Big ( y _ { i } , } \\ { \displaystyle { D i f f _ { y } = \frac { i - 1 , i ^ { \prime } \mathrm { s t e c e d } ^ { - 1 } } { N } N } } \end{array} \Big )  \end{array} \right.
$$

公式（1）

图16 为参考帧（左）、成功匹配的帧与参考帧叠加后（右）的示意图，其中参考帧中StarA、StarB、StarC分别与成功匹配的帧中Star $\mathbf { A } ^ { * }$ 、Star $\mathbf { B } ^ { * }$ 、Star $C ^ { * }$ 为匹配星对。4A、4B、4C分别为这三组匹配星对之间的偏移量，分别对三组偏移量在X轴和Y轴方向的投影进行计算并取平均值作为Difx和Dif,。

导星相机每次积分后都可以得到一组偏移量 $D i f f _ { x }$ 、Diff,，但是如果每次都使用这组偏移量来指导望远镜校正跟踪误差，反而会导致望远镜的不正常抖动。尤其对于丽江2.4米望远镜这种转动惯量很大的望远镜情况更为严重。除此之外，这种抖动误差还可能会被检测为偏移矢量并发送给望远镜控制系统。因此为了避免这种现象的出现，将多次偏移量的结果进行累计求和取平均值，并分别记作 $\hat { D } _ { x }$ 和 $\hat { D } _ { y }$ ，作为指导望远镜校正跟踪误差的信号。

![](images/8f4e90bd0f6b97e3658e6a2c81475b2664c371165f3e2c1572badd379dbbd209.jpg)  
图16星像偏移量

2）利用 $\hat { D } _ { x }$ 和 $\hat { D } _ { y }$ 指导望远镜补偿跟踪误差。即通过坐标系变换的矩阵运算建立导星相机星像偏移量与望远镜三轴（ALT、AZ、ROT）修正量之间的关系，实现望远镜的闭环跟踪。坐标系之间变换不是本文的研究重点，不再赘述。

在将点模式匹配法应用于丽江2.4米望远镜的闭环跟踪后，作者于2021年8月3日测试了望远镜的跟踪精度。实际结果表明其一小时闭环跟踪精度优于 $0 . 5 "$ ，同时在像平面上的星像位置偏移量不大于1.8pixel。而原“单亮星”跟踪法在视场内没有亮星干扰情况下的一小时闭环跟踪精度为0.5"，若存在亮星干扰，则可能出现星像“跳变”，导致跟踪失败。由此可见应用点模式匹配法使视场中可探测到的星像均得到利用，提高了望远镜长期跟踪期间的精度与鲁棒性。导星相机像平面星像位置偏移量 $D i f f _ { x }$ 、Diff,如图17所示。

![](images/e32c327d7dd4caafcabf4b7685cd41cc17afac71209dead4d09be49d85ef8106.jpg)  
Figure 16 The stars offset   
图17导星相机像平面星像偏移量  
Figure 17 The error of stars position on the AG camera's image plane

# 5总结与展望

综上所述，提升丽江2.4米望远镜主力观测设备YFOSC的光谱观测效率，离不开星像与狭缝耦合的效率以及望远镜闭环跟踪的高精度，丽江站运维团队在近年已针对这两点进行了不断的优化，本文介绍了优化的算法以及优化后的效果。但经过观测测试发现，还有进一步提升的空间，如导星CCD 的视场和探测能力的提升可以带来YFOSC 的光谱观测效率提高。

此外，丽江2.4米望远镜的耐焦切换平台已经装调完毕，实现了耐焦与卡焦、耐焦两个焦点之间的自由切换，本文介绍的相关算法也可以应用到耐焦的导星系统研发过程中，从而提高耐焦相关仪器的光谱观测效率，进而可以提升丽江2.4米望远镜的综合观测能力，开展

更多种类的天文观测和科学研究。

# 参考文献：

[1]WANGCJ，BAIJM,FANYF,etal.Lijiang 2.4-meter Telescope and itsinstruments[J].Research inAstronomy and Astrophysics,2019,19(10):149.   
[2] FANYF,BAI JM,ZHANG JJ,et al.Rapid instrument exchanging system for the Cassegrainfocusof the Lijiang 2.4-m Telescope[J]. Research in Astronomy and Astrophysics,2015,15(6):918.   
[3] 谭徽松，赵昭旺，卢汝为．偏置导星的性能和使用[J].云南天文台台刊,1980,1. TANHS,ZHAOZW,LURW.ThePerformance and Usage ofOffset Guiding[J].PublicationsofYunnanObservatory1980,1.   
[4]范玉峰．中型望远镜观测系统集成[J].2014. FANYF. Observing System Integration of Mid-Size Telescope [J].2014.   
[5] 南方天文观测基地．丽江天文观测站年报 (2008—2015)[R]. South Astronomical Observatory.The annual report of Lijiang observatory (2008—2015)[R].   
[6]张介，白金明，范玉峰．机器视觉高斯拟合法自动导星定心系统设计[J].天文研究与技术,2013,10(2):171-178. ZHANG J,BAIJM,FANYF.Design ofan Auto-Guiding System with Machine Visionand the Gausian-Fiting Method[J]. Astronomical Research & Technology,2013,10(2): 171-178.   
[7]Murtagh F.Anewapproach topointpatern matching[J].PublicationsoftheAstronomical SocietyofthePacific,1992, 104(674): 301.   
[8]LangD,HoggDW,MierleK,etal.Astrometry.net:Blindastrometriccalibrationofarbitraryastronomicalimages[J]. The astronomical journal,2010,139(5):1782.   
[9]Foale S,Bowman MK,Nation JS,etal.Robotic acquisition of spectrograph targetsacross the Las Cumbres Observatory global network of telescopes[C] Softwareand Cyberinfrastructure for AstronomyV.International Society for Optics and Photonics,2018,10707: 107070Y.   
[10] Holwerda B W.Source extractor for dummies v5[J].arXiv preprint astro-ph/0512139,2005.

# Research on Improving The Efficiency of YFOSC Spectrum Observation

Chen Yuyang1.2.3, Wang Chuanjun1.2, Fan Yufeng1,2, Lun Baoli1,2 (1.Yunan Observatories,Chinese Academy of Sciences,Kunming650216,China,Email: wcj@ynao.ac.cn;

KeyLaboratory for Structure and Evolutionof Celestial Objects,Chinese Academy of Sciences,Kunming,65021

3. University of Chinese Academy of Sciences,Beijing,100049)

Abstract: Lijiang 2.4-metre telescope, as the largest general-purpose optical telescope of China currently, plays a very important role in the field of night astronomy observation. From the recent distribution time of observation ,the spectrum observation of Yunnan Faint Object Spectrograph and Camera (YFOSC) accounts for the largest proportion of the total observation time.Thus improving its spectrum observation efficiency has become the key factor in ensuring the telescope's stable scientific output. This paper will discuss two key factors which affecting the efficiency of YFOSC spectrum observation—acquire stars into slit and close-loop guiding of telescope,and introduce the way of improving the quality and efficiency of YFOSC spectrum observation.

Keywords: Spectrum observation Acquire stars into slit Telescope lose-loop guiding