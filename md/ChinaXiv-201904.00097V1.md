# 附加相对约束关系的月表全景相机平差算法研究

倪涛 任鑫中国科学院国家天文台，北京，100012

摘要：我国近期发射的月球探测器携带了全景相机的科学载荷，负责获取巡视器着陆区的月球表面影像采集的重要任务。全景相机共有两台，采用双目立体成像，实际工作时保持相对位置和姿态关系不变。本文参考了地球测绘、计算机视觉等领域的多个相似案例，使用了一种改进的平差模型。经过实验验证，证明了该模型能够消除不同立体像对间相对位置和姿态的偏差，使平差结果更加可靠，为我国探月任务中月表全景相机影像数据的摄影测量处理提供了帮助和支持。

关键词：相对约束关系；光束法平差；全景相机；摄影测量中图分类号：P234.1

# 0引言

月表测绘制图是月球探测的重要任务之一，主要是通过月球探测器携带的科学载荷获取探测数据，然后利用摄影测量方面的技术进行处理和计算，得到月表正射影像、月表三维地形图等成果。我国近期发射的月球探测器，包括嫦娥三号、嫦娥四号和嫦娥五号都携带了两台全景相机，负责获取探测器着陆地区影像数据采集的任务。全景相机所获取的影像数据将用于制作月表着陆区cm级精度的地形数据，该成果能够为深入研究探测点附近准确的地质构造提供精确的形貌数据，为其它载荷（如矿物光谱仪）数据的综合研究提供基础数据，同时也是月球车探测点规划的重要参考数据之一，因此对于后续的研究意义重大。两台全景相机固定于巡视器的转台上，实际工作时采用双目立体成像，相机间的相对位置和姿态关系（以下简称相对外方位元素）保持不变，是后续摄影测量平差处理的重要约束条件之一。

目前主流的商业摄影测量软件，包括 smart 3D、photoscan 等在稀疏匹配时都是以单幅影像为单位进行光束法平差计算，成像模型基于摄影测量学的共线方程：

$$
\mathrm { x - x _ { 0 } = - f \frac { ( X - X _ { 0 } ) R _ { 1 1 } + ( Y - Y _ { 0 } ) R _ { 2 1 } + ( Z - Z _ { 0 } ) R _ { 3 1 } } { ( X - X _ { 0 } ) R _ { 1 3 } + ( Y - Y _ { 0 } ) R _ { 2 3 } + ( Z - Z _ { 0 } ) R _ { 3 3 } } }
$$

$$
{ \mathrm { y } } - { \mathrm { y } } _ { 0 } = - { \mathrm { f } } { \frac { \left( { \mathrm { X } } - { \mathrm { X } } _ { 0 } \right) { \mathrm { R } } _ { 1 2 } + ( { \mathrm { Y } } - { \mathrm { Y } } _ { 0 } ) { \mathrm { R } } _ { 2 2 } + ( { \mathrm { Z } } - { \mathrm { Z } } _ { 0 } ) { \mathrm { R } } _ { 3 2 } } { ( { \mathrm { X } } - { \mathrm { X } } _ { 0 } ) { \mathrm { R } } _ { 1 3 } + ( { \mathrm { Y } } - { \mathrm { Y } } _ { 0 } ) { \mathrm { R } } _ { 2 3 } + ( { \mathrm { Z } } - { \mathrm { Z } } _ { 0 } ) { \mathrm { R } } _ { 3 3 } } }
$$

式中， $\mathrm { \bf ~ { \cal ~ X } } _ { 0 } , \mathrm {  \large ~ { \cal ~ y } _ { 0 } ~ }$ ，f是相机的内方位元素， $\mathrm { X } _ { 0 }$ ， $\mathrm { Y } _ { 0 }$ ， $Z _ { 0 }$ 是相机的投影中心，R为旋转矩阵。

该方法未加入相机间的相对约束关系，每幅影像都是自由地进行旋转平移以达到光线束的最佳交会，因此解算得到的左右相机的相对外方位元素不是严格固定的，由左右相机构成的立体像对解算的三维坐标必然存在一定的误差。

目前已经有大量关于行星表面全景相机双目立体影像的处理案例，邸凯昌（2009）总结了美国勇气号和机遇号的定位与制图方法，提出平差方法主要来源于光束法平差及其改进算法，王文睿等(2015)利用嫦娥三号全景相机的双目立体影像实现了月表地形的三维重建，算法部分主要利用了基于摄影测量学共线方程的前方交会算法[2。经过大量的文献调研和总结，本文发现目前行星表面双目立体成像数据处理大多采用基于传统共线方程的平差算法，很少考虑左右相机相对外方位元素固定的约束条件。

在航空摄影领域，多视影像成像同样存在相机间相对外方位元素固定的情况，与本文研究的月表全景相机成像方式有相似之处，且已经有大量的研究成果。Ebner等（1992）针对多镜头的 MOMS-02 相机提出了一种改进的成像模型[3]，闫利等（2016）提出了倾斜航空摄影中，考虑到同一测站下视与斜视相机间的约束关系，采用6个偏心参数来描述两者之间的变换[4，张力等（2017）提出多视影像的倾斜航空影像区域网平差可以采用3种平差方式，包括无约束的联合定向方式、附加相对约束的定向方式以及直接定向方式[5]。

本文在调研了大量航空摄影多视影像平差方法的文献后，总结出一种附加相对约束关系的月表全景相机平差算法，主要是将同一测站左右相机的相对外方位元素保持不变的条件加入到光束法平差模型当中，将每个摄站的多个相机整体作为一个刚体单位进行平差计算，该方法的平差模型更加严密，网型更加稳定。经过验证，该平差模型能够保证同一测站两台全景相机的相对外方位元素保持不变，并且减少了平差模型中的未知数，能够为我国探月任务中月表全景相机的摄影测量处理提供技术支持。

# 1月表全景相机及实验数据简介

本次实验数据包括嫦娥三号巡视器全景相机环拍数据和嫦娥五号全景相机外场科学验证试验数据，两组数据的成像方式均为全景相机双目立体成像，影像数据获取过程中保持左右相机相对外方位元素不变。

# 表1全景相机参数

Tab. 1 Parameters of panoramic cameras   

<html><body><table><tr><td colspan="2">嫦娥五号全景相机</td><td>嫦娥三号全景相机</td></tr><tr><td>波段范围</td><td>可见光</td><td>可见光</td></tr><tr><td>颜色</td><td>彩色（R，G，B)</td><td>彩色（R，G，B)</td></tr><tr><td>成像模式</td><td>彩色成像、全色成像(可切换)</td><td>彩色成像、全色成像(可切换)</td></tr><tr><td>正常成像距离（m)</td><td>3~8</td><td>3~8</td></tr><tr><td rowspan="2">有效像元数量</td><td>2352×1728（彩色）</td><td>2352×1728（彩色）</td></tr><tr><td>1176×864（全色）</td><td>1176×864（全色)</td></tr><tr><td>CCD 探测器像元大小</td><td>7.4μ m</td><td>7.4μ m</td></tr></table></body></html>

嫦娥五号全景相机科学验证试验的目的在于评价相机影像质量和验证全景相机几何参数和安装参数的测量方案。试验分为内场试验和外场试验两部分其中外场试验于2015年11月29日开展，全景相机在两种不同姿态条件下完成了两组图像数据的获取，图像数据覆盖了试验点附近 $1 8 0 ^ { \circ }$ 水平范围和$- 9 0 ^ { \circ } \ \sim 0 ^ { \circ }$ 俯仰范围，试验总共获取了195对影像数据，数据总量约为3GB。本文选取了其中的一组试验数据，总共包括93对影像。

![](images/7058fb701620057061d68cf4fd15700c88eb2bfdfb8feae03fdccd1dde85554a.jpg)  
图1嫦娥五号全景相机科学验证试验外场区域 Fig.1 Outfield of scientific verification

嫦娥三号巡视器搭载了全景相机的科学载荷，主要用于获取巡视区月表的三维光学影像，在着陆器与巡视器实现两器月面分离后，巡视器围绕着着陆器一圈获取了月表影像。全景相机在第一个月昼期间，在两器月面互拍点A-D上以彩色模式对着陆器成像51对，在 N0106点上分别以俯仰角 $- 7 ^ { \circ }$ 和 $- 1 9 ^ { \circ }$ ，偏航角 $1 7 5 ^ { \circ } - 1 7 6 ^ { \circ }$ 的探测模式对巡视器周围月面进行 $3 6 0 ^ { \circ }$ 环拍，分别获取了112 对全色图像和56 对彩色图像。第二个月昼期间，全景相机以彩色成像模式在 N0203和 N0205 两个探测点上对月面进行环拍，共获取环拍数据112对。本文选取了第一月昼在E点和S3点的全色图像环拍数据，包括56对影像。

![](images/a403f56f515227008360f68e4d207e0a563595a022101e70d945e5966f7824c8.jpg)  
Fig.2 Partial images taken by panoramic cameras in Chang’E-3 in point N0106

# 2双目立体相机的平差方法

为方便推导，首先说明摄影测量学中几个重要的坐标系。

（1）像平面坐标系：摄影方向与影像平面的交点称为像主点，以像主点为原点，两对边机械的框标的连线为 $\textsf { x }$ 和 $\mathsf { \pmb { y } }$ 轴，其中与航线方向一致的连线为 $\textsf { x }$ 轴，航线方向为正向

![](images/d1bf4226c722818717ffcbcd61d9cc5e864a1b33a28e34fe229098026bb61e91.jpg)  
图2嫦娥三号全景相机在N0106点获取的部分影像

（2）像空间坐标系：用于表示像点在像方空间的过渡坐标系，以摄影中心为原点，主光轴为z轴，正向为摄影的反方向，×、y轴与像平面坐标系的×、y轴平行

（3）像空间辅助坐标系：以摄影中心为原点，以铅垂方向为Z轴，航线方向为×轴，可以通过外方位元素构成的旋转矩阵对像空间坐标系进行旋转变换得到

如图3所示，0-xy 为像平面坐标系，S1-xyz为像空间坐标系，S1-XYZ为像空间辅助坐标系。

设左相机的投影中心为S1，S1的物方坐标为（XS1,YS1,ZS1)，外方位元素构成的旋转矩阵为R1，右相机的投影中心为S2，S2的物方坐标为（XS2,YS2,ZS2)，外方位元素构成的旋转矩阵为R2。设右相机的像空间坐标系旋转至与左相机的像空间坐标系平行时，旋转矩阵为M。

对于左相机，由像空间辅助坐标系旋转至像空间坐标系，再旋转到右相机的像空间坐标系，旋转变换表示为： $\mathbf { M } ^ { \mathrm { T } } \mathbf { R } _ { 1 } ^ { \mathrm { T } }$ ，对于右相机，由像空间辅助坐标系旋转至像空间坐标系，旋转变换表示为： ${ \sf R } _ { 2 } ^ { \sf T }$ ，两者的旋转是等价的，即 $\mathbf { M } ^ { \mathrm { T } } \mathbf { R } _ { 1 } ^ { \mathrm { T } } = \mathbf { R } _ { 2 } ^ { \mathrm { T } }$

![](images/8c110c70c4a8d0a4cb2ce2a6328b046c0a3a7cade178ed53def39901c6ad84d8.jpg)  
图3三个坐标系的位置关系 Fig.3Positionrelationshipsof three coordinate systems   
图5右相机旋转过程  
Fig.5 Rotation process of right camera

![](images/59d3726b324387d44819e9a9c7254289dc8a5df0573a7504a317b4f0d1f2f983.jpg)  
图4左相机旋转过程  
Fig.4 Rotation process of left camera

设 S1到S2的平移量为（ $\Delta \mathrm { ~ x } , \Delta \mathrm { ~ y } , \Delta \mathrm { ~ z ~ } )$ ，该平移量以左相机的像空间坐标系为参照。于是有以下关系：

$$
{ \left[ \begin{array} { l } { \mathrm { X } _ { \mathbb { S } 2 } } \\ { \mathrm { Y } _ { \mathbb { S } 2 } } \\ { \mathrm { Z } _ { \mathbb { S } 2 } } \end{array} \right] } = { \left[ \begin{array} { l } { \mathrm { X } _ { \mathbb { S } 1 } } \\ { \mathrm { Y } _ { \mathbb { S } 1 } } \\ { \mathrm { Z } _ { \mathbb { S } 1 } } \end{array} \right] } + \mathrm { R } 1 { \left[ \begin{array} { l } { \Delta \mathrm { x } } \\ { \Delta \mathrm { y } } \\ { \Delta \mathrm { z } } \end{array} \right] }
$$

原共线方程为：

$$
\left[ \begin{array} { c } { \mathrm { x - x _ { 0 } } } \\ { \mathrm { y - y _ { 0 } } } \\ { \mathrm { - f } } \end{array} \right] = \mathrm { k R _ { 2 } ^ { T } } \left[ \begin{array} { c } { \mathrm { X - X _ { S 2 } } } \\ { \mathrm { Y - Y _ { S 2 } } } \\ { \mathrm { Z - Z _ { S 2 } } } \end{array} \right]
$$

这里x0，y0，f为右相机的内方位元素，X，Y，Z和 $\mathsf { \Psi } \times , \mathsf { \Psi } \forall \mathsf { \Psi }$ 为观测点的物方坐标和像平面坐标，$\boldsymbol { \mathsf { k } }$ 为比例系数。

代入上文推导的平移和旋转关系，得到：

$$
\left[ \begin{array} { c } { \mathrm { X } - \mathrm { x } _ { 0 } } \\ { \mathrm { y } - \mathrm { y } _ { 0 } } \\ { - \mathrm { f } } \end{array} \right] = \mathrm { k } \mathrm { M } ^ { \mathrm { T } } \mathrm { R } _ { 1 } ^ { \mathrm { T } } \left[ \begin{array} { c } { \mathrm { X } - ( \mathrm { X } _ { \mathrm { } \mathrm { } \mathrm { } + } \Delta \mathrm { X } ) } \\ { \mathrm { Y } - ( \mathrm { Y } _ { \mathrm { } \mathrm { } \mathrm { } 1 } + \Delta \mathrm { Y } ) } \\ { \mathrm { Z } - ( \mathrm { Z } _ { \mathrm { } \mathrm { } 1 } + \Delta \mathrm { Z } ) } \end{array} \right]
$$

这里 $\mathbf { \Delta } [ \Delta \mathbf { X } ] = \mathrm { R } _ { 1 } \left[ \begin{array} { l } { \Delta \mathrm { X } } \\ { \Delta \mathrm { Y } } \\ { \Delta \mathrm { Z } } \end{array} \right]$

整理后得到：

$$
\left[ \begin{array} { c } { \mathbf { X } - \mathbf { X } _ { 0 } } \\ { \mathbf { y } - \mathbf { y } _ { 0 } } \\ { - \mathbf { f } } \end{array} \right] = \mathbf { k } ( \mathbf { M } ^ { \mathrm { T } } \mathbf { R } _ { 1 } ^ { \mathrm { T } } \left[ \begin{array} { c } { \mathrm { X } - \mathbf { X } _ { \mathrm { S 1 } } } \\ { \mathrm { Y } - \mathbf { Y } _ { \mathrm { S 1 } } } \\ { \mathrm { Z } - \mathrm { Z } _ { \mathrm { S 1 } } } \end{array} \right] - \mathbf { M } ^ { \mathrm { T } } \left[ \begin{array} { c } { \Delta \mathbf { x } } \\ { \Delta \mathbf { y } } \\ { \Delta \mathbf { z } } \end{array} \right] )
$$

对于每一对相片，旋转矩阵 $\mathsf { M }$ 和平移量 $( \Delta \mathsf { x } , \Delta \mathsf { y } , \Delta \mathsf { z } )$ ，都是保持不变的。通过上述式子，每个右相机影像共线方程中的外方位元素可以用对应的左相机外方位元素以及旋转矩阵M 和平移量 $( \Delta \mathsf { x } , \Delta \mathsf { y } , \Delta \mathsf { z } )$ 转换得到。实际的平差计算中，对于左相机的误差模型采用原始的共线方程，对于右相机的误差模型采用本文推导的方程。

# 3实验验证及分析

首先对影像进行了特征点提取和同名像点匹配。本次试验采用了SIFT算子，SIFT 即尺度不变特征变换（Scale-invariant feature transform）[7]，是用于图像处理领域的一种描述，对旋转、尺度缩放、亮度变化保持不变，对视角变化、仿射变换、噪声也具有一定程度的稳定性。一般来说 SIFT 算子的计算结果存在一定数量的误匹配点，本文对匹配结果使用了随机抽样一致性算法（RANSAC）进行进一步的筛选，最终嫦娥三号巡视器环拍数据选取了其中 54 对影像，共提取了42085个匹配点，嫦娥五号科学验证试验数据选取了其中75 对影像，共提取了141498个匹配点。

由于光束法平差属于非线性优化，需要提供未知数的初始值。本文利用了计算机视觉领域的运动恢复结构问题（Structure From Motion，SFM）的相关理论，根据匹配结果使用 5点法计算本质矩阵，再用SVD分解该矩阵得到相机外方位元素的估算值，最后利用基于共线方程的前方交会方法估算了像点对应的物方三维坐标。

本文的相机镜头畸变模型采用了brown 模型，只考虑径向畸变的部分，误差模型如下：

$$
\Delta \mathrm { x } = - \mathrm { x } ( \mathrm { k } _ { 0 } + \mathrm { k } _ { 1 } \mathrm { r } ^ { 2 } + \mathrm { k } _ { 2 } \mathrm { r } ^ { 4 } )
$$

$$
\Delta \mathbf { y } = - \mathbf { y } ( \mathbf { k } _ { 0 } + \mathbf { k } _ { 1 } \mathbf { r } ^ { 2 } + \mathbf { k } _ { 2 } \mathbf { r } ^ { 4 } )
$$

其中， $\mathrm { r } = \sqrt { \mathrm { x } ^ { 2 } + \mathrm { y } ^ { 2 } }$ 是以像主点为极点的向径， $\Delta \mathrm { x }$ ， $\Delta \mathfrak { y }$ 为像点坐标改正数，×，y为像点坐标， $\mathbf { k } _ { 0 }$ ， $\mathbf { k } _ { 1 }$ ， $\mathbf { k } _ { 2 }$ 为物镜畸变差改正系数。

误差模型中未知数与观测值为非线性关系，故先对方程进行线性化，采用泰勒级数展开

并保留一次项，然后采用经典的Gauss-Newton法进行迭代求解。

考虑到迭代计算中可能存在粗差的影响，本文加入了Huber loss 函数，该函数是一种常用的鲁棒的回归损失函数，具体形式如下：

$$
\begin{array} { r } { \mathrm { L } _ { \delta } ( \mathrm { a } ) = \left\{ \begin{array} { c } { \displaystyle \frac { 1 } { 2 } \mathrm { a } ^ { 2 } , \qquad | \mathrm { a } | < \delta } \\ { \displaystyle \delta \cdot \left( | \mathrm { a } | - \frac { 1 } { 2 } \delta \right) , \ddag \langle \underline { { t } } | \underline { { t } } \rangle } \end{array} \right. } \end{array}
$$

其中，a为误差方程算出的残差值，δ为函数的参数，可以根据具体残差的大小给定。

本文利用嫦娥五号数据对δ的取值进行了实验，最终通过对比结果选取 $\delta = 1 . 0$ ，即观测点反投影残差大于1个像素时，减弱其对整体误差的影响。

本文对试验数据分别进行了附加相对约束关系和未附加相对约束关系的平差计算，并统计了平差计算的相关数据，制成了表2。另外，本文通过共线方程计算像点反投影的残差，并将像点中误差以影像为单位进行统计，得到两种方法结果的像点残差分布规律，结果如图4所示，其中，左图为嫦娥五号数据处理结果，右图为嫦娥三号数据处理结果。

# 表2平差实验结果

Tab.2 Results of adjustment tests   

<html><body><table><tr><td>实验数据</td><td>是否附加相对约 束关系</td><td>迭代次数</td><td>外方位元素未知数 个数</td><td>连接点中误差（像 素）</td><td>连接点最大误差（像 素）</td></tr><tr><td rowspan="2">嫦娥五号科学验 证试验数据</td><td>是</td><td>6</td><td>456</td><td>0.207</td><td>2.974</td></tr><tr><td>否</td><td>7</td><td>900</td><td>0.199</td><td>2.743</td></tr><tr><td rowspan="2">嫦娥三号巡视器 环拍数据</td><td>是</td><td>5</td><td>330</td><td>0.191</td><td>2.925</td></tr><tr><td>香</td><td>4</td><td>648</td><td>0.190</td><td>2.903</td></tr></table></body></html>

![](images/63b3a788ef3fd2418dfaf1f1c71998735f0e19c9d343298cc075a37400652af8.jpg)  
图4平差结果像点中误差统计  
Fig.4 RMS statistics of points of adjustment results

从以上的统计结果可以看出，两种方法得到结果的像点反投影误差规律非常接近，而在未知数个数方面，附加相对约束关系的平差方法能够减少部分外方位元素，对于节约计算机内存空间具有一定意义。

另外，本文通过平差计算得到的影像外方位元素反求左右相机的相对姿态，转角系统按照x-y-z轴的顺序，三个旋转角分别为@， $\Phi$ ，K，统计了三个转角的平均值、中误差、最大误差等结果，得到表3。另外，通过相机的外方位线元素求取了左右相机间的距离，并且统计了相关的误差指标，得到表4。

# 表3立体像对相对姿态误差统计

Tab.3 Error statistics of relative pose between stereo images   
表4立体像对距离的误差统计  

<html><body><table><tr><td rowspan="2">实验数据</td><td rowspan="2">Tab rror 是否附加 相对约束</td><td colspan="8">C0 Tages ω (度）</td></tr><tr><td>关系 平均值</td><td>中误差</td><td>最大误 差</td><td>平均值</td><td>Φ(度) 中误差</td><td>最大误</td><td>平均值</td><td>K(度） 中误差</td><td>最大误</td></tr><tr><td>嫦娥五号</td><td>是</td><td>0.084</td><td>0</td><td>0</td><td>6.917</td><td>0</td><td>差 0</td><td>0.044</td><td>0</td><td>差 0</td></tr><tr><td>科学验证</td><td>否</td><td>0.078</td><td>0.007</td><td>0.025</td><td>6.917</td><td>0.009</td><td>0.029</td><td>0.045</td><td>0.001</td><td>0.005</td></tr><tr><td>试验数据 嫦娥三号</td><td>是</td><td>0.133</td><td>0</td><td>0</td><td>1.987</td><td>0</td><td>0</td><td>-0.039</td><td>0</td><td>0</td></tr><tr><td>巡视器环 拍数据</td><td>否</td><td>0.134</td><td>0.006</td><td>0.019</td><td>1.990</td><td>0.003</td><td>0.011</td><td>-0.040</td><td>0.003</td><td>0.010</td></tr></table></body></html>

Tab.4 Error statistics of distance between stereo images   

<html><body><table><tr><td rowspan="2">实验数据</td><td rowspan="2">是否附加相对约束关系</td><td colspan="2">立体像对距离</td></tr><tr><td>平均值 (米)</td><td>最大误差 (米)</td></tr><tr><td>嫦娥五号科学验证试验数</td><td>是</td><td>0.254</td><td>0</td></tr><tr><td>据</td><td>否</td><td>0.254</td><td>0.002</td></tr><tr><td rowspan="2">嫦娥三号巡视器环拍数据</td><td>是</td><td>0.268</td><td>0</td></tr><tr><td>否</td><td>0.269</td><td>0.003</td></tr></table></body></html>

表3表4显示，附加相对约束关系的平差方法能够确保模型内部的刚性关系，而传统方法由于是完全自由平差，在这方面会产生一定误差，为了估算该误差产生的影响，本文利用瞬时视场角（IFOV）对其进行估算，两组实验数据的全景相机焦距约为 $5 0 \mathsf { m m }$ ，像元大小为$7 . 4 \mu \mathrm { ~ m ~ }$ ，取两者比值得到瞬时视场角约为0.148mrad，再通过与旋转角的误差值取比值，可以估算得到立体像对相对旋转角误差造成的像点误差大小，最后以像对为单位进行统计，结果如图6所示，左图为嫦娥五号数据处理结果，右图为嫦娥三号数据处理结果：

![](images/f60afb44d63f12daf932a8e429f3f189c83aebbd9c3d9243e2b765745ada18e0.jpg)  
图5相对姿态误差导致的像点误差分布情况  
Fig.5 Distribution of image point error caused by inaccurate relative pose

图5可以看出，嫦娥五号科学验证试验数据的处理结果中，像点误差约为1个像素，最大超过3个像素，嫦娥三号巡视器全景相机环拍数据的处理结果中，像点误差约为1个像素，最大超过2个像素。相对姿态误差导致的像点误差达到了像素级别，对于最终解算得到的三维坐标必然会产生一定影响。

最后本文利用附加相对约束关系的平差结果对影像数据进行了密集匹配，通过前方交会的计算方法，得到像点对应的物方三维坐标，并生成影像区域的三维模型。这部分内容借助

软件Smart3D完成，结果如图6、图7所示。

![](images/5960ca2607da07f95c97f7db936a91dae4874d330dcd479b80478207140ba7c4.jpg)  
图6嫦娥五号全景相机科学验证试验外场区域三维模型 Fig.6 3D model of outfield for scientific verification test of panoramic cameras in Chang'E-5

![](images/c83f068719eb4e3c652ac5124057d52c8e1efea6240f1cbd4faf9324e9331cda.jpg)  
图7嫦娥三号巡视器月表环拍区域三维模型  
Fig.73D model of lunar surface around Chang’E-3 rover

# 4总结与展望

本文分析了当前月表双目立体相机平差处理存在的问题，参考了计算机视觉和航空摄影测量领域的处理经验后使用了一种改进的平差模型，利用嫦娥五号科学验证试验数据和嫦娥三号巡视器环拍数据进行了验证。通过结果比较，证明了本文使用的方法能够确保不同立体像对之间的相对外方位元素保持一致，提高左右相机间的内部吻合精度，得到的平差结果更加可靠。另外，该方法还能减少部分外方位元素未知数，在节约计算机内存方面有一定意义。因此，本文提出的平差方法可以应用于相关的月表影像处理工作，为后续的研究提供支持。

# 参考文献：

[1]邸凯昌．火星车定位与制图技术现状以及对发展中国月球车/火星车定位制图技术的建议[J]．遥感学报，2009,13:101-112.Di kaicang.Current Situation of Mars Vehicle Location and Mapping Technology and Suggestions on DevelopingLocation Mapping Technologyof Lunar rover/Mars roverin China[J].Journalof Remote Sensing,2009,13:101-112.  
[2] WR Wang，X Ren，FF Wang，JJLiu,CLLi.Terrain reconstruction from Chang’e-3 PCAMImages［J]．Research inAstronomy and Astrophysics，2015，15(7):1057-1066.  
[3] Ebner，H，Kornus,W.，Ohlhof,T.，1992.A simulation study on point determination for the MMS-02/D2 spaceproject using an extended functional model[J].Int.Arch.Photogramm.Remote Sens.29 (B4)，458- 464.  
[4]闫利，费亮，叶志云，夏旺．大范围倾斜多视影像连接点自动提取的区域网平差法[J]．测绘学报，2016，45(3）：310-317.Yanli,Feiliang,Ye zhiyun,Xiawang.Automatic Tie-points Extractionfor TriangulationofLarge-scale ObliqueMulti-view Images.Acta Geodaetica Cartograpgica Sinica，20l6,45(3）：310-317.  
[5］张力，艾海滨，许彪，孙钰珊，董友强．基于多视影像匹配模型的倾斜航空影像自动连接点提取及区域网平差方法[J].测绘学报，2017，46(5）：554-564.Zhang li,Ai hai-bin,Xu biao,Sun yu-shan,Dong you-qiang.Automatic Tie-point Extraction Based onMultiple-image Matching and Bundle Adjustmentof Large Block of Oblique Aerial Images[J].Acta GeodaeticaCartograpgica Sinica，2017，46(5）：554-564.  
[6]李德仁，袁修孝．误差处理与可靠性理论．武汉：武汉大学出版社[M]，2002.Li deren,Yuan xiuxiao.Error Processing and Reliability Theory[M]．Wuhan:Wuhan University Press,2002.  
[7] LOWE DG.Distinctive Image Features from Scale invariant Keypoints[J].International Journal of ComputerVision，2004，60(2)：91-110.  
[8] 张剑清，潘励，王树根．摄影测量学[M]．武汉：武汉大学出版社,2009.Zhang jian-qing，Pan li，Wang shu-gen.Photogrammetry[M]．Wuhan:Wuhan University Press，2009.  
[9] 薛喜平，张洪波，孔德庆．深空探测天文自主导航技术综述［J]．天文研究与技术，2017，14(3）：382-391.Xue xiping，Zhang hongbo，Kong deqing.An Overview of Celestial Autonomous Navigation Technology for DeepSpace Exploration[J]．Astronomical Research & Technology，20l7，14(3）：382-391.  
[10］李佳威，李芳，何瑞珠．利用GPS 测速估算接收机载体运动方位角[J]．天文研究与技术，2017，14(1）：45-51.Li jiawei，Li fang，He ruizhu.Azimuth Estimation of a Moving Receiver by GPS Speed Measurement[J].Astronomical Research & Technology，2017，14(1）:45-51.

# Adjustment Algorithm for Lunar Panoramic Camera with Additional Relative Constraints

Ni Tao, Ren Xin National Astronomical Observatory, Chinese Academy of Sciences, Beijing,100012

Abstract: The lunar probe launched recently in China carries the scientific load of the panoramic camera,which is responsible for the important task of acquiring lunar surface image of the landing area of the inspector. The two panoramic cameras in the lunar probe use the method of binocular stereo imaging and the relative position and pose between cameras remain unchanged during the imaging process. After consulting several similar cases in the fields of earth surveying and mapping and computer vision,an improved adjustment model is used.Test results show that the new model can eliminate the deviation of relative position and attitude between different stereo pairs and makes the adjustment results more reliable.In conclusion,the new adjustment algorithm can provide help and support for photogrammetric processing of lunar panoramic camera image data in lunar exploration missions in China.

Key words: Relative constraints; Bundle adjustment ; Panoramic cameras; Photogrammetry