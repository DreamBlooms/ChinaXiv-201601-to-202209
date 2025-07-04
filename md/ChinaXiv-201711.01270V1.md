# 太阳高分辨观测图像与全日面像的高精度配准方法

冯涛，戴伟’，王瑞²，季凯帆1,²1.昆明理工大学云南省计算机技术应用重点实验室，云南 昆明 650500;2.中国科学院云南天文台，云南昆明650011

摘要：在太阳观测研究中，高分辨图像与全日面像的配准是一项非常有意义的工作，但由于他们之间存在着旋转、缩放和平移，因此很难高精度地进行匹配。提出一种结合局部统计信息和控制点匹配的图像配准方法，核心思想为将视场等间隔划分为大量重叠的局部区域，通过相关匹配在全日面像上寻找对应的局部区域，然后计算每一对局部区域间的亚像元偏移，根据偏移量确定每一对特征点的坐标位置，据此作为点匹配中的特征控制点；最后根据控制点建立仿射变换的转换方程，采用最小二乘求解整个视场的转换参数，根据解出的参数重新对图像进行迭代，得到收敛后的结果并进行配准。通过对高分辨观测图像和全日面SDO/HMI连续谱图像进行配准，拟合结果的偏差在0.25”以内。

关键词：太阳图像配准；高分辨图像；全日面图像;

中图分类号：P182.2 文献标识码：A 文章编号：1672-7673

在研究太阳图像的观测数据时，经常需要将不同设备的观测数据进行对比，从而发挥它们各自在不同波段、不同视场、不同分辨率上的观测优势。太阳光学成像观测包括全日面和高分辨观测两类。对于全日面图像，由于太阳几何尺寸和运动方式已知，如太阳的半径、PO角、自转等，因此各种观测设备均把自己的数据在预处理后归算到标准的太阳坐标系。然而对于局部高分辨像，由于观测设备的指向误差、视场旋转以及焦距的变化，使得直接依赖仪器参数确定准确的太阳视场坐标是不精确的，因此只能借助太阳图像上相似的太阳结构（如光球层对应光球层，色球层对应色球层）与全日面像进行转换，即视场匹配。然而全日面观测有大于 $3 1 ^ { \prime }$ 的视场，但最高的空间像元分辨仅为 $\mathbf { 0 . 5 ^ { \prime \prime } }$ （空间太阳动力天文台的日球层磁场观测仪，SDO/HMI)。而地面高分辨观测，如中国的1m 新真空太阳望远镜(New VaccumSloar Telescope,NVST）和美国大熊湖天文台的新太阳望远镜(New Solar Telescope,NST），视场仅仅为1’到 $2 ^ { \bullet }$ ，但像元分辨率达到 $0 . 0 5 ^ { \cdot , }$ 以上，这就意味着需要将两个空间分辨率相差十倍的图像进行配准。即便不考虑其他畸变，局部像的视场旋转（R）、比例尺（S）和中心位置坐标（ $T _ { X . }$ ，Ty）是必须得到的4个参数。

图像配准是指在不同时间、不同条件下得到的并且位于不同坐标系下的同一场景的两幅或者多幅图像进行匹配的过程[]。由于存在各种不同的情况，同一场景的多幅图像会在分辨率、位置、尺度、成像模式等方面存在很多差异，图像配准是找到一个几何变换的最优解，使得图像上相对应的点，或者至少是有意义的点达到匹配状态。目前在图像配准领域，常见的配准方法有基于特征的点匹配方法，即根据图像中的特征点，或者显著特征构造描述子确定的匹配点，然后构造转换方程进行配准。理论上这个方法如果有足够多和足够精确的控制点是可以很好地解决两个图像的几何变换，如旋转、缩放、平移等问题。但关键问题是如何确定这些点，这方面在图像处理界有很多研究，如Harris 角点及其衍生的Harris-Laplace 方法[2]，尺度不变特征（Scale-invariant feature transform,SIFT）[3]及其衍生的PCA-SIFT 算法(Principal Com-ponent Analysis SIFT)[4]、局部特征描述子[5]、高速尺度不变特征算法（Very FastSIFT，VF-SIFT）[6]，加速鲁棒性特征（Speeded Up Robust Features,SURF）〔7-8]等。另外一种是基于区域信息的统计配准方法，主要通过图像区域的统计信息度量图像的相似程度，如互信息[9]，互相关函数[10-11]，模板匹配[12]，不变矩，相关匹配[13-14]等。但一般来讲这种方法主要解决图像间的平移问题，对于具有旋转和比例缩放的图像，又引申出在频率域的相位相关技术[15]，Fouier-Mellin[16-17]等。

然而，由于太阳观测图像和普通自然图像有很大的区别，其中的特征边界不清晰，结构相对模糊且存在很多噪声，同时动态范围大，运动速度较快，并且存在很多不同的活动现象，大部分运动现象为非刚性运动；同时太阳图像的图幅一般较大，有效目标小且缺少有效的纹理，不存在明显的梯度变化等特征，并且由于拍摄太阳图像的设备以及拍摄过程中的不确定性，采集的太阳图像还存在旋转、缩放及平移等情况，不同图像的空间分辨率经常不在同一尺度，这就为确定特征对应点带来非常大的困难。长期以来，在同一观测设备的太阳时间序列图像的视场对齐一直采用基于互相关的统计配准，而不同观测设备之间的图像配准，还停留在利用一些显著的太阳特征，如黑子、气孔、大米粒构造对应点的方式。然而这些特征点数量少,结构不规则，难以保证位置测量精度，同时也难以使用计算机技术进行自动化测量。尤其是将高分辨局部像对应到全日面像的时候，这种问题更为突出。但从另一方面，通过望远镜机械和终端光学系统，对局部太阳像指向、比例尺和位置有初步估计，只是这些数值不很精确且随时间有一些变化。因此实际面临的是如何提高配准精度，进行精细图像匹配的问题。

基于这些问题，本文提出了一种将统计信息和相关点匹配相结合的太阳图像配准算法，解决将不同分辨率下的局部高分辨观测数据和全日面数据进行高精度坐标转换的问题，其中包括测量图像指向角、像元比例尺和图像中心在全日面像上的位置。这一方法的基本思想是在初步匹配的基础上，首先将视场划分成大量重叠的局部区域代替点匹配中的控制点，通过基于统计的相关匹配确定对应区域间的亚像元位移，从而确定特征点对在同一坐标系中的位置；然后用最小二乘迭代求解整个视场的转换参数，并逐步迭代提高拟合的精度，成功将1M太阳望远镜和新太阳望远镜的TiO观测数据与几乎同时刻（最长间隔11s）的 SDO/HMI连续谱进行了匹配，拟合结果的偏差可达到0.25”之内。

# 1实验数据来源

本文实验使用的全日面图像来自太阳动力学观测卫星 SDO(Solar Dynamics Observatory,SDO）上日球层磁场观测仪HMI（Helioseismic and Magnetic Imager,HMI）采集的连续谱全日面像，而高分辨图像为1M太阳望远镜和新太阳望远镜 的 TiO 光球像。SDO/HMI设备的空间分辨率约为0.5043arcsec/pixel，图像尺寸为4096像元 $* 4 0 9 6$ 像元；1M太阳望远镜和新太阳望远镜图像的像元比例尺为0.04arcsec/pixel和0.03arcsec/pixel。

图1（a）为1M太阳望远镜的Ti0观测数据，观测时间为2013-7-1507:29:09，有效区域尺寸为2304像元 $* 1 9 2 0$ 像元；图1（b）为SDO/HMI连续谱观测数据，观测时间为2013-7-1507:29:15， 红框标记区域为1M太阳望远镜在 SDO/HMI中的大体位置。本文主要以此图像的匹配说明算法流程。

![](images/59227834f5ae3747748036976787bbce3d9901e68f06f557949ba861bd2cb09b.jpg)  
图1观测数据

# 2配准的方法

2.1配准方法的流程配准方法的主要流程如图2。

![](images/a79d88d0c2cbc7ba0076fd3d9574d3f7d7084b38ce2f4f35559320876a5b4497.jpg)  
Fig.1 Observed data   
图2算法流程图  
Fig.2 Algorithm flow chart

图2可以描述为下列11个步骤：

（1）对1M太阳望远镜像的指向、比例尺和位置进行初步估计，得到旋转（Rotation）、缩放（Scaling）及平移（Translation）参数（下文称RST参数）；  
（2）根据 RST参数，对 SDO/HMI全日面像进行旋转，并截取与1M太阳望远镜像视场相同的 SDO/HMI 子图 $I _ { s }$ ；  
（3）根据 RST 参数和 SDO/HMI 的比例尺，将1M太阳望远镜像缩小至和 SDO/HMI同一比例尺下，即对1M太阳望远镜图像进行降采样；  
（4）对降采样后的1M太阳望远镜像进行高斯平滑，减小采样过程中的频率混叠。平滑后的1M太阳望远镜降采样像用 $I _ { \scriptscriptstyle R }$ 表示;

(5） 将图像 $I _ { \scriptscriptstyle R }$ 等间隔划分为 $N$ 个重叠的子块，并将每个子块记为 $f _ { R } ^ { i }$ ；(6） 对每一个子块 $f _ { R } ^ { i }$ 和 SDO/HMI 子图 $I _ { s }$ 利用归一化互相关方法求得 $f _ { R } ^ { i }$ 对应的每一个 $I _ { s }$ 子块 $f _ { s } ^ { i }$ ;

（7）对每一组 $f _ { R } ^ { i }$ 和 $f _ { s } ^ { i }$ ，测量其亚像元偏移，并将子块中心设置为一组对应的控制点;

（8）筛选每组控制点，将控制点间距离大于一定像元的点剔除；  
（9）根据剩下的控制点，建立仿射变换的转换方程，采用最小二乘求解RST参数;

（10）计算残差 $\sigma$ 和迭代次数 $L$ ，若满足 $\left\{ \sigma < 0 . 5 \land \Delta \sigma < 0 . 1 \right\}$ ； $\left\{ \sigma < 0 . 3 \right\}$ ；$\left\{ L > 3 0 , \sigma = \operatorname* { m i n } \left( \sigma _ { _ { 1 \sim 3 0 } } \right) \right\}$ 任一条件，则停止迭代；否则，返回步骤（2)，根据步骤（9）解得的RST参数重新对 SDO/HMI 和1M太阳望远镜像进行迭代处理;

（11）最终得到迭代完成后的RST参数并进行配准。

在上述步骤中，（6）至（9）步为算法的核心步骤，下文对该部分进行更为具体描述。需要注意，开始迭代后（2）到（3）步中的RST参数会根据上一次迭代的结果进行下一次迭代，意味着算法会重新对图像进行平滑。

# 2.2分块确定特征控制点

设 $I _ { \scriptscriptstyle R }$ 为待匹配图像， $I _ { s }$ 为参考图像。将 $I _ { \scriptscriptstyle R }$ 划分 $N$ 个特征区域，记为集合 $\{ f _ { R } ^ { i } , i = 1 , 2 . . . , N \}$ ：$I _ { s }$ 的尺寸为 $U { \times } V$ ,每个区域 $f _ { R } ^ { i }$ 的尺寸为 $\boldsymbol { u } \times \boldsymbol { \nu }$ ，可知 $u < U , \nu < V$ ，则参考图像 $I _ { s }$ 和图像 $f _ { R } ^ { i }$ 的互相关函数 $\left. C o r r ( x , y ) \right.$ 定义为，

$$
C o r r \big ( x , y \big ) = \frac { \displaystyle \sum _ { s = 0 } ^ { u - 1 } \sum _ { t = 0 } ^ { \nu - 1 } \Bigl [ I _ { s } \big ( x + s , y + t \big ) - \overline { { f _ { s } ^ { i } } } \ " \ ] \Bigl [ f _ { s } ^ { i } \big ( s , t \big ) - \overline { { f _ { s } ^ { i } } } \Bigl ] } { \displaystyle \sqrt { \sum _ { s = 0 } ^ { u - 1 } \sum _ { t = 0 } ^ { \nu - 1 } \Bigl [ I _ { s } \big ( x + s , y + t \big ) - \overline { { f _ { s } ^ { i } } } \ " \sum _ { s = 0 } ^ { u - 1 } \sum _ { t = 0 } ^ { \nu - 1 } \Bigl [ f _ { _ R } ^ { i } \big ( s , t \big ) - \overline { { f _ { _ R } ^ { i } } } \Bigr ] ^ { 2 } } }
$$

其中， $\left( s , t \right)$ 为 $f _ { R } ^ { i }$ 上的坐标， $\overline { { { f _ { S } ^ { i } } } } = \frac { 1 } { u \nu } \sum _ { s = 0 } ^ { u - 1 } \sum _ { t = 0 } ^ { \nu - 1 } \left[ \begin{array} { c } { { { \cal I } _ { S } \left( x + s , y + t \right) } } \end{array} \right] \ , \quad \overline { { { f _ { R } ^ { i } } } } = \frac { 1 } { u \nu } \sum _ { s = 0 } ^ { u - 1 } \sum _ { t = 0 } ^ { \nu - 1 } \left[ \begin{array} { c } { { { f _ { R } ^ { i } } \left( s , t \right) } } \end{array} \right] \mathrm { { o r } } \ \overline { { { f _ { S } ^ { i } } } } = \frac { 1 } { \nu } \sum _ { s = 0 } ^ { u - 1 } \left[ \begin{array} { c } { { { f _ { R } ^ { i } } \left( s , t \right) } } \end{array} \right] .$ （204 $\overline { { f _ { s } ^ { i } } }$ 为

$I _ { s }$ 和 $f _ { R } ^ { i }$ 覆盖的那个区域图像的平均值，求和是对 $I _ { s }$ 和 $f _ { R } ^ { i }$ 覆盖的 $\left( s , t \right)$ 进行。

根据上述公式，每个 $f _ { R } ^ { i }$ 和 $I _ { s }$ 做归一化互相关，可得到一个互相关曲面，而峰值的坐标代表了 $f _ { R } ^ { i }$ 图像中心在 $I _ { s }$ 中的整数像元精度的匹配位置。

在 $I _ { s }$ 中根据上述位置可截取和 $f _ { R } ^ { i }$ 同样大小的特征区域，得到每一个 $f _ { R } ^ { i }$ 对应的 $f _ { s } ^ { i }$ 。由它们组成的集合记为 $\{ f _ { s } ^ { i } , i = 1 , 2 . . . , N \}$ 。

对于两组对应的特征区域的 $f _ { R } ^ { i }$ 和 $f _ { s } ^ { i }$ ，使用集合 $F$ 描述 $f _ { R } ^ { i }$ 和 $f _ { s } ^ { i }$ 任意两个特征区域之间的关系，即

$$
F _ { i } { = } F \Big ( f _ { R } ^ { i } , f _ { S } ^ { i } \Big ) , 1 { \leq } i \leq N \qquad ,
$$

$F _ { _ i }$ 表示任意两个对应的局部特征区域 $\left( f _ { R } ^ { i } , f _ { S } ^ { i } \right)$

对于每一对特征区域 $\left( f _ { R } ^ { i } , f _ { S } ^ { i } \right)$ ，计算标准的互相关函数。假设 $D$ 为特征区域 $\left( f _ { R } ^ { i } , f _ { S } ^ { i } \right)$ 间互相关函数分布的峰值局部区域，按照修正矩方法计算重心坐标 $\scriptstyle { \left( m , n \right) }$ ，

$$
m = \frac { \sum _ { D } \bigl ( I ^ { \prime } X \bigr ) } { \sum _ { D } I ^ { \prime } } , n = \frac { \sum _ { D } \bigl ( I ^ { \prime } Y \bigr ) } { \sum _ { D } I ^ { \prime } } \qquad ,
$$

其中，I为曲面强度值，则 $I ^ { \prime } { = } I { - } b$ ， $b { = } \operatorname* { m i n } ( I ) , I \in D$ 。每一对 $\left( f _ { R } ^ { i } , f _ { S } ^ { i } \right)$ 图像间互相关函数的局部重心坐标代表每一对特征区域 $\left( f _ { R } ^ { i } , f _ { S } ^ { i } \right)$ 间的亚像元偏移。

根据亚像元偏移的情况，可以建立每一对 $\left( f _ { R } ^ { i } , f _ { S } ^ { i } \right)$ 图像中心点对应的坐标，得到和 $I _ { s }$ 之间的 $N$ 对坐标转换控制点。用集合 $P$ 描述控制点对之间的关系，即

$$
P _ { i } { = } P \Big ( { p _ { R } ^ { i } , p _ { s } ^ { i } } \Big ) , 1 { \le } i { \le } N \quad .
$$

# 2.3最小二乘求解转换参数

考虑平移、旋转和缩放的情况，假设控制点对 $\left( p _ { R } ^ { i } , p _ { s } ^ { i } \right)$ ，对应的坐标分别为 $\left( x _ { A } , y _ { A } \right)$ 和$\left( { x _ { _ { B } } , y _ { _ { B } } } \right)$ ，变换关系为

$$
\begin{array} { c } { { x _ { _ B } = \Delta x + \left( 1 + m \right) x _ { _ A } \cos \theta - \left( 1 + m \right) y _ { _ A } \sin \theta } } \\ { { y _ { _ B } = \Delta y + \left( 1 + m \right) x _ { _ A } \sin \theta + \left( 1 + m \right) y _ { _ A } \cos \theta } } \end{array}
$$

转换为矩阵形式，

$$
{ \Bigg [ } { \left[ \begin{array} { l } { x } \\ { y } \end{array} \right] } _ { B } = { \left[ \begin{array} { l l l l } { 1 } & { 0 } & { x _ { A } } & { - y _ { A } } \\ { 0 } & { 1 } & { y _ { A } } & { x _ { A } } \end{array} \right] } { \left[ \begin{array} { l } { \Delta x } \\ { \Delta y } \\ { a } \\ { b } \end{array} \right] } , a = ( 1 + m ) \cos \theta
$$

误差方程为

$$
\left[ { \begin{array} { c } { V _ { x _ { A } } } \\ { V _ { y _ { B } } } \end{array} } \right] = \left[ { \begin{array} { c c c c } { 1 } & { 0 } & { x _ { A } } & { - y _ { A } } \\ { 0 } & { 1 } & { y _ { A } } & { x _ { A } } \end{array} } \right] \left[ { \begin{array} { c } { \Delta x } \\ { \Delta y } \\ { a } \\ { b } \end{array} } \right] - \left[ { \begin{array} { c } { x _ { B } - x _ { A } } \\ { y _ { B } - y _ { A } } \end{array} } \right] \ ,
$$

其中， ${ \left[ \begin{array} { l } { x } \\ { y } \end{array} \right] } _ { A }$ 为转换前坐标; ${ \left[ \begin{array} { l } { x } \\ { y } \end{array} \right] } _ { B }$ 为转换后坐标； $\begin{array} { r } { \left[ \Delta x \right] } \\ { \Delta y \rfloor } \end{array}$ 为平移参数； $\left( 1 + m \right)$ 为缩放参数;（204号 （204号  
θ为旋转参数。理论上，只要存在两组转换控制点，利用上式方程，可联立解出一组转换  
四参数;存在3个或3个以上的控制点时,可利用最小二乘法求解四参数 $\boldsymbol { X } = \left( \Delta x , \Delta y , m , \theta \right) ^ { T }$ ：  
然后将待匹配图像转换到参考图像。

需要注意，在视场平面坐标转换时，需要对误配点对进行筛选，通过计算控制点间的距离。在实际匹配中，如果控制点之间的距离大于5像元，即 $2 . 5 ^ { \prime \prime }$ 时，则认为该点为误配点对，将其剔除，根据筛选后的控制点求解的RST参数，重新对 SDO/HMI和IM太阳望远镜像进行RST迭代，计算RST参数，最后得到迭代完成后的RST转换参数。

# 3实验结果与分析

本文实验中，分块尺寸设置为30 像元 $^ { * 3 0 }$ 像元，块间隔为5像元。图3为利用上述方法，将1M太阳望远镜高分辨像和 SDO/HMI全日面像配准后重叠区域的对比图，

![](images/e6be95a2e30f215f07e2a04a9f57f71cdb2b517f7cd553794d0f35f6d50433ef.jpg)  
图31M太阳望远镜高分辨像和SDO/HMI全日面像配准后重叠区域的对比图

Fig.3 Comparison overlapping area of IM太阳望远镜 high-resolution image and full-disk Solar image after

registration

从图3可以看到，配准后图像的对应区域除清晰度明显不同外，其他特征已经完全匹配。为了更好地观察配准效果，将配准区域叠加后，对边界区域进行放大，如图4，可以看到边界细节的信息匹配度良好，气孔、米粒、米粒暗径均较好的衔接。

![](images/1169ba784d8eb555d5ff4e0930173aa02ca3e0a6794df813574d42d7b906abc5.jpg)  
图4配准区域的边界细节   
Fig.4 The edge details of the registration area

根据配准结果和SDO/HMI的标准参数，表1显示了推算的这张1M太阳望远镜图像P0角和像元比例尺，以及视场中心在 SDO/HNI全日面像中的位置。

# 表1配准结果

Tab.1 Registration results   

<html><body><table><tr><td rowspan="2">最终配准结 果</td><td rowspan="2">PO角度 （度）</td><td rowspan="2">比例尺 (arcsecond 像元）</td><td rowspan="2">全日面横坐标</td><td rowspan="2">全日面纵坐 标 （像元）</td><td rowspan="2">匹配点个数</td><td rowspan="2">残差均方根 （SDO 像元）</td></tr><tr><td>（像元）</td></tr><tr><td></td><td>-12.95°</td><td>0.04223</td><td>1524.163</td><td>2686.251</td><td>775</td><td>0.31像元</td></tr></table></body></html>

从表1可以知道平均残差为0.31SDO/HMI 像元，意味着拟合结果的偏差约为0.15”。图5显示了这些残差的空间分布。从图5可以看出，残差分布并不是完全随机，显示了1M太阳望远镜像存在畸变。这是由于地面高分辨观测图像重建后，依然还有一些低频的大气抖动残余未能消除，而这种原因限制了最终拟合结果的精度。同时由于两个图像的观测时间并不完全同步，有6s的间隔，因此有些太阳图像特征已经发生了改变。

![](images/aaf8a9438a36761c4beceaf64d4a7a0535c3ba815389ae0d34ba409c364dec55.jpg)  
图5配准后的向量场  
Fig.5 The vector field after registration

对多张1M太阳望远镜和新太阳望远镜观测的高分辨像和SDO/HMI全日面像进行了匹配，结果见表2。

表2新太阳望远镜和1M太阳望远镜的Ti0图像与SD0/HMI全日面像的配准结果 Tab.2 Registration result of TiO image（新太阳望远镜 and1M太阳望远镜）and SDO/HMI full-disk Solar image   

<html><body><table><tr><td>序号</td><td>望远镜</td><td>高分辨像观测时间</td><td>与 SDO/HMI的 观测间隔</td><td>残差均方根 (SDO 像元）</td></tr><tr><td>1</td><td>新太阳望远镜</td><td>2014-08-05 22:29:59</td><td>1s</td><td>0.33</td></tr><tr><td>2</td><td>新太阳望远镜</td><td>2014-08-05 16:50:13</td><td>2s</td><td>0.43</td></tr><tr><td>3</td><td>新太阳望远镜</td><td>2014-08-01 16:53:16</td><td>1s</td><td>0.45</td></tr><tr><td>4</td><td>新太阳望远镜</td><td>2012-07-05 16:36:28</td><td>7s</td><td>0.42</td></tr><tr><td>5</td><td>1M太阳望远 镜</td><td>2013-07-15 07:29:09</td><td>6s</td><td>0.31</td></tr><tr><td>6</td><td>1M太阳望远 镜</td><td>2012-10-29 06:03:37</td><td>8s</td><td>0.50</td></tr><tr><td>7</td><td>1M太阳望远 镜</td><td>2013-06-12 07:45:34</td><td>11 s</td><td>0.26</td></tr></table></body></html>

从上述结果可以看到，最大的匹配残差约0.5像元，相当于 $0 . 2 5 ^ { \prime \prime }$ 。实验过程中发现，不同参数的选取会对算法产生一定的影响，具体见图6-图

![](images/ebc4696d51dabda44fb1ff7ae3e6d0aee2ebb099e73549637eab8d48ecc11e91.jpg)  
图6不同的初始参数

图6显示了初步估计的参数对迭代次数的影响。图6中，三角型（绿色）、空心圆型（蓝色）、米字型（红色）、十字型（黑色）分别代表估计角度为 $3 0 ^ { \circ }$ 、 $3 5 ^ { \circ }$ 、 $4 0 ^ { \circ }$ 、 $4 5 ^ { \circ }$ 时的迭代过程。可以看出，随着初值误差增大，为了修正误差使结果收敛在合理的范围内，算法的迭代次数相应增加。当初始估计角度达到 $4 5 ^ { \circ }$ （此时的误差约为 $3 0 ^ { \circ }$ ）时，迭代次数由6 次增加到42次才能收敛。

![](images/3ac7cacd7561f9cad879b1d60e559d312ce76a388594f38a3464d20335e684f2.jpg)  
Fig.6 The different initial parameters   
图7不同的控制点筛选间距  
Fig.7 The different filter distance between control points

图7显示了筛选控制点间距离的设置对算法收敛速度的影响。图7中，十字型（红色）、空心圆型（黑色）分别代表筛选阈值为5Pixel和10 Pixel的迭代过程。可以看出，初值误差较大时，高阈值的迭代次数更少，意味着算法收敛更快，反之低阈值效果更理想。当角度误差在 $3 0 ^ { \circ }$ 附近时，不同阈值的迭代次数相差28次，高阈值更优。角度误差在 $1 0 ^ { \circ }$ 附近时，迭代次数仅相差9次，低阈值更优。

![](images/1713a47a295040a9cf54da3b6be822d4e88256b2ca44fe016ae01c7840df7a99.jpg)  
图8不同的平滑参数  
Fig.8 The different filtering parameters

图8显示了不同的平滑参数对迭代次数的影响。图8中，米字型（绿色）、空心圆型（蓝色）、十字型（红色）分别表示平滑参数为0.5、1、1.5时的迭代过程。可以看出，平滑参数增大使迭代次数增长，并且拟合结果有一定的降低。当平滑参数为0.5时，算法达到收敛所需的迭代次数和结果较优于其它情况。

# 4结论

本文提出了一种针对太阳高分辨像和全日面进行视场匹配的算法，从而解决了不同空间分辨率下、具有旋转角的太阳观测图像匹配问题。算法的基本思想是结合区域相关匹配和控制点最小二乘求解的方法。1M太阳望远镜和新太阳望远镜高分辨图像与SDO/HMI全日面像的视场匹配实验都证明了两者的图像拟合结果的偏差优于0.25”。通过匹配可以精确测量高分辨像的P0角，像元比例尺等。

这套方法要计算大量的小区域相关，同时进行迭代计算，因此，时间开销较大；以及不同参数对迭代次数的影响，是在方法应用时需要注意的。除此之外，小尺寸子块会导致匹配点数增加，计算量增大，拟合精度会存在一定的下降；而大尺寸虽然对精度有一定提升，但是会导致匹配区域变小，从而会影响整张图像的匹配效果。而子块间距更多的影响计算速度。结合实际情况，我们认为子块尺寸在30像元、块间距5像元附近，算法的稳定性较合理。在应用中，可根据实际情况对参数进行调整。

此外，将高分辨TiO像通过与 SDO/HMI全日面连续谱图像的高精度匹配，也意味着可以转换为和任意标准的全日面像进行匹配，如 SDO/HMI磁图、SDO/AIA各波段观测，甚至和色球全日面像进行匹配。这意味着可以在0.25”的偏差下，研究小尺度结构在各个波段，以及在磁场上的对应情况。

这套方案可以用于任何具有相似图像结构的太阳图像匹配，如TiO 和Gband、Hα 偏带、10830；也可以用于Hα 线心图像和GONG全日面像的配准。因此具有非常多的应用前景。

# 参考文献：

[1] Zitova B, Flusser J. Image registration methods: a survey [J].Image and vision computing,2003,21(11) :977-1000   
[2] K Mikolajczyk,C Schmid. Scale & affine invariant interest point detectors. International Journal of Computer Vision,2004,60(1) :63-86.   
[3] DG Lowe. Distinctive image features from scale-invariant keypoints. International Journal of Computer Vision,2004,60(60) :91-110. [4] K Yan, R Sukthankar.PCA-SIFT:a more distinctive representation for local image descriptors. IEEE Computer Society Conference on Computer Vision & Pattern Recognition,2004,2(2) :506-513   
[5] J Hou, N Qi， J Kang .Image Matching Based on Representative Local Descriptors. International Conference on Advances in Multimedia Modeling,2010,5916:303-313 [6] FAlhwarin, DRistic - Durrant,AGräser. VF-SIFT: Very Fast SIFT Feature Matching, Dagm Conference on Pattern Recognition， 2010， 6376:222-231   
[7] H Bay， T Tuytelaars,LV Gool. SURF: Speeded Up Robust Features. Computer Vision & Image Understanding,2006,110(3) :404-417.   
[8]张开玉，梁风梅.基于改进 SURF 的图像配准关键算法研究，科学技术与工程, 2013,13(10) :2875-2879.   
ZHANG Kaiyu, LIANG Fengmei. Research on Key Algorithms of image registration based on improved SURF. Science Technology and Engineering， 2013,13(10):2875-2879. [9] JPW Pluim, JBA Maintz, MA Viergever. Multual-information-based registration of medical images: a survey. IEEE Transactions on Medical Imaging,2003,22(8);986-1004. [10] JP Lewis. Fast Normalized Crossed-Correlation,Circuits Systems & Signal Processing,2001,82(2) :144-156.   
[11] SH Yong， KM Lee, UL Sang. Robust stereo matching using adaptive normalized cross-correlation. IEEETransactionsonPatternAnalysis&Machine Intelligence,2011,33(4) :807-22.   
[12］高军，李学伟，张建,等．基于模板匹配的图像配准算法，西安交通大学学报，2007 (3):307-311.   
Gao Jun, Li xuewei, Zhang Jian. et al. Image registration algorithm based on template matching. Journal of Xi'an Jiaotong University， 2007（3): 307-311.   
[13] JN Sarvaiya， S Patnaik， S Bombaywala. Image registration using log-polar transform and phase correlation， Tencon IEEE Region 10 Conference， 2009:1-5   
[14]辛登松，彭建雄．SAR图像的改进相位相关配准方法，计算机与数字工 程,2011,39(8) :126-128.   
Xin Dengsong， Peng Jianxiong. Improved phase correlation registration method for SAR images. Computer and Digital Engineering. 2011,39(8):126-128.   
[15] BS Reddy,BN Chantterji.An FFT-based technique for translation, rotation, and scale-invariant image registration, IEEE Transactions on Image Processing,1996,5(8) :1266-1271.   
[16]X Guo， Z Xu. An Application of Fourier-Mellin Transform in Image Registration, International Conference on Computer & Information Technology， 2005: 619-623. [17］王亮，刘蓉，张丽,等．基于Fourier-Mellin变换的气象卫星光谱图像配准，光谱学 与光谱分析，2013，33（3），855-858.   
Wang Liang, Liu Rong, Zhang Li,et al. Spectral image registration of meteorological satellite based on Fourier-Mellin transform. Spectroscopy and Spectral Analysis, 2013，33（3），855-858.

# High-accuracy Registration Method of Solar High-resolution Observation Images and Full-disk Solar Images

Feng Tao1，Dai Weil，WangRui²，JiKaifan1,2

1.KeyLaboratoryofAplicationsofComputerTechnologyoftheunanProvince,KunmingUnversityofScienceandTchology

Kunming 650500, China;

2.Yunnan Observatories,Chinese Academy of Sciences,Kunming 65oo11, China

Abstract: In the research of the Solar observation, the registration between high-resolution observation images and full-disk Solar images is a greatly meaningful work. However, it is difficult to register with high accuracy due to the rotation,scaling and translation between them. This paper presents an image registration method combining local statistical information and control point matching: At first, between the high-resolution observation image and the full-disk Solar image is preliminary estimated about the orientation, scale,and positional parameters.Then the images are pretreated based on the estimated parameters.And then the pretreatment of the field of view is divided into a large number of overlapping local regions equally. Each corresponding local area is determined by the Correlation matching on the full-disk after preprocessing. Next, the sub-pixel offset between each pair of local regions is then measured,and the coordinate positions of the feature point are determined according to the sub-pixel offset between each pair of local regions,which is used as the feature control point in the point matching.Finally,the conversion equations of the affine transformation are established according to the control point, then use the least squares to solve the entire field of view of the transformation parameters. The image is reiterated according to the parameters to be solved,and the transformation parameters are obtained after the final iteration to register images. By registering the high-resolution observation images and the full-disk Solar SDO/HMI continuous spectrum, the deviation of fitting results is within 0.25 arc-seconds.

Key words: Solar Image Registration; High-resolution Image; Full-disk Solar Images;