# 脉冲星信号相干消色散与非相干消色散的比较研究

黄玉祥l²，汪敏1，郝龙飞1，李志玄1，徐永华1(1．中国科学院云南天文台，云南 昆明 650011；2.中国科学院大学，北京 100049)

摘要：脉冲星信号在星际空间传播的过程中，由于星际介质的存在造成观测到的脉冲星信号发生色散，因此需要对接收的脉冲星信号进行消色散，以获得原始的脉冲星信号。目前，消色散方法主要分为两种，相干消色散和非相干消色散。相对来说相干消色散效果彻底，算法较简单，而且能保留原始数据的时间分辨率，不过计算量较大，但是现在快速进步的计算机技术已经使计算量的问题得到很好的解决。为了精确了解两种消色散方法的区别，利用相关系数的方法定量地比较了相干消色散、非相干消色散两种方法的效果：在一定的频率值之下，前者得到消色散效果优于后者。同时确定两种消色散方法在效果相同时的观测频率。

关键词：脉冲星；相干消色散；非相干消色散中图分类号：TN911.71 文献标识码：A 文章编号：1672-7673（2018)

脉冲星是一种具有超高温、超高压、超高密度、超强磁场、超强电场和超强引力场等极端物理条件的天体，一般认为是超新星爆发的产物，典型半径约为 $1 0 \mathrm { k m }$ ，而质量却与太阳相当，核心密度高达 $1 0 ^ { 1 4 } \ \mathbf { g } \cdot \mathbf { c m } ^ { - 3 [ 1 ] } ,$ 。目前，大多数人认为，脉冲星是高速旋转的磁中子星，其自转轴与磁轴之间有一个夹角，两个磁极各有一个辐射束。脉冲星的辐射几乎占据了整个电磁波谱，包括射电、红外、可见光、紫外、X射线和 $\gamma$ 射线等电磁波频段。其辐射具有较高的周期性，辐射周期和自转周期一致，且周期变化率较小。

脉冲星极端的物理特性和辐射的高周期性具有较大研究意义和应用前景[2]。从科学研究来讲，脉冲星可以用于验证和发展极端条件下的物理学和天文学理论，毫秒脉冲双星的研究已经检验了广义相对论和引力波辐射[3.4]；从工程应用来讲，毫秒脉冲星可以用于精确计时和星际导航[1.5]。由于毫秒脉冲星的周期变化率小于 $1 0 ^ { - 1 9 } \ s \cdot s ^ { - 1 }$ ，周期噪声极小，周期稳定度比较高，且随时间的增加会持续改善，甚至能超过氢原子钟，多个不同天区的毫秒脉冲星计时观测可以组合成一个平均的脉冲星钟，这可以用于现有原子钟长期稳定性的修正。

为了进行上述研究，就要获得精确的脉冲星脉冲到达时间[（Time Of Arrival，TOA)，由于星际介质的存在，观测设备接收到的脉冲星信号发生色散。为了简化理论，星际介质被看成是低温、低密度等离子体，它对在其中传播的频率为 $f$ 的电磁波的折射率为

$$
\begin{array} { r } { \mu = \sqrt { 1 - \left( \frac { f _ { p } } { f } \right) ^ { 2 } } } \end{array}
$$

其中， $f _ { p }$ 为等离子体频率， $\begin{array} { r } { f _ { p } = \sqrt { \frac { e ^ { 2 } n _ { e } } { \pi m _ { e } } } \sim 8 . 5 \mathrm { k H z } \left( \frac { n _ { e } } { \mathrm { c m } ^ { - 3 } } \right) ^ { 1 / 2 } \sim 1 . 5 \mathrm { k H z } } \end{array}$ . $n _ { e }$ 取 $0 . 0 3 \mathrm { c m } ^ { - 3 [ 1 ] }$ 。

对于射电波段观测，接收到的脉冲信号是一维时域上的脉冲轮廓，不同频率的脉冲之间发生色散延迟，频谱起始频率信号相对于其截止频率信号延迟时间[为

$$
\begin{array} { r } { t _ { D } = D \times D M \times \mathrm {  ~ ( ~ } \frac { 1 } { f _ { l o w } ^ { 2 } } - \frac { 1 } { f _ { h i g h } ^ { 2 } } \mathrm {  ~ ) } , } \end{array}
$$

其中，DM(Dispersion Measure）为传播路径上的星际介质的色散量，色散量 $\begin{array} { r } { D M = \int _ { 0 } ^ { d } { n _ { e } } \mathrm { d } l = } \end{array}$ $\overline { { n _ { e } } } d$ ，单位为 $\mathrm { c m } ^ { - 3 }$ : pc;

$\overline { { n _ { e } } }$ 为传播路径上的平均电子数密度； $D$ 为星际介质的色散常量， $\begin{array} { r } { D = \frac { e ^ { 2 } } { 2 \pi m _ { e } c } = } \end{array}$ $4 1 4 8 . 8 0 8 \mathrm { { M H z } } ^ { 2 } \mathrm { { p c } } ^ { - 1 } \mathrm { { c m } } ^ { 3 } s ,$

flow和 $f _ { h i g h }$ 分别为接收频带的起始频率和截止频率，单位为MHz。

由(2)式可知，一定带宽脉冲星信号的色散延迟会造成时域脉冲的相位移动、幅度降低和脉冲轮廓展宽等色散现象，这限制了到达时间分辨率。因此需要对接收到的脉冲星信号进行消色散并获得精确的到达时间，通过对脉冲到达时间的拟合可以得到脉冲星的相关物理参数，进而研究其自身的辐射机制和其他相关特性。

![](images/770f09ad8ba67428a5a8df10bd7c78e4717dcf9881d04184191fab7f7de4ddcb.jpg)  
图1消色散算法流程图；上半部分是相干消色散的流程图，下半部分是非相干消色散的流程图

Fig.1Flowchartofcoherentde-dispersionalgorithm；theabovebelongstocoherentde-dispersion,thebelowbelongstoncohere

de-dispersion

消色散的宗旨是消除信号频带内的色散效应，目前主要有非相干消色散和相干消色散[1]。非相干消色散是基于时间序列，用滤波器组分通道，按相对于参考通道的延迟时间单个通道进行平移从而消除色散，如图1；相干消色散是在频域上利用星际介质的传输函数(chirp 函数)实现通带内的消色散，如图1。

![](images/7a8f76f326eb49400426c2595fbb5fa459b5ec76bbfebb398fae7ef77a091553.jpg)  
图2脉冲星PSR $\mathbf { J } 2 3 2 2 + 2 0 5 7$ 的脉冲轮廓。实线是相干消色散后的轮廓，虚线是非相干消色散后的轮廓[6] g.2 Pulse profile of PSR $\mathbf { J } 2 3 2 2 + 2 0 5 7$ Solid line: pulse profile observed by coherent de-dispersion.Dashed line: The same prol

filtered by incoherent de-dispersion

目前已经有学者在比较两种消色散方法方面进行了一些研究。文[6]在430MHz处对PSR$\mathbf { J } 2 3 2 2 + 2 0 5 7$ 进行了观测、获得了相干和非相干消色散后的平均脉冲轮廓，并计算出脉冲到达时间的精度，后者与前者到达时间的均方根误差比值为0.3，如图2。文[7]用DSP 算法在327MHz处比较了这两种方法得到的一些脉冲星信号的积分轮廓，相干消色散后数据的时域序列脉冲幅度和时间分辨率是非相干消色散后数据的10\~15倍[7]。国内，中国科学院新疆天文台的脉冲星观测团队利用基于MK5A的VLBI记录系统建立一套带宽为64MHz的相干消色散系统，得到了一些脉冲星的平均脉冲轮廓，与以前使用的 $2 { \times } 1 2 8 { \times } 2 . 5 \mathrm { M H z }$ 多通道非相干消色散系统的结果进行了比较[8，结论是相干消色散优于非相干消色散，但没有进行系统和定量的分析研究。本文旨在用相关系数的方法定量地分析两种方法消色散效果的差别。

# 1消色散原理

两种消色散方法基于不同的消色散原理。非相干消色散是基于时域上各个频段的信号相位移动进行的不连续消色散，相干消色散是基于频域乘积的连续消色散，具体描述如下。

# 1.1非相干消色散

非相干消色散的过程是首先把观测带宽为 $B W$ 的时域信号由滤波器组分成若干狭窄通道，然后在时域上把每个通道信号按适当的时延量进行平移，最后将脉冲对齐后的所有通道信号幅度累加得到消色散后的时域信号序列，如图3。非相干消色散的优点是数据量小，计算量少。这种方法的缺点：（1）单个通道内的色散效应没有消除，增大通道的数量可以减少剩余的色散效应，但是由不确定性原理 ${ \mathit { t } } _ { \mathrm r \mathrm e s } \propto 1 / ( 2 \times b w )$ 可知，增大通道数量，单个通道信号的时间分辨率会增大，所以要根据需求，适当调整通道数的数值；（2）由于非相干消色散过程是单通道时域序列的平移，该方法会损失信号的相位信息。

![](images/242d85d38c20f4c4b6a084e9dd1dc4ae5c7a98575582c0c812fd189f22e3ecb8.jpg)  
图3 消色散原理图9]。上半部分显示的是非相干消色散的原理，下半部分显示的是相干消色散的原理Fig.3Schematicdagramofncoherentde-dispersio.Thupperpartsowsthepcipleoficoherentde-dispersio,theuterpartshowsthe Principle of coherent de-dispersion.

# 1.2相干消色散

星际介质的色散效应相当于移相器的作用，因此接收到的脉冲星信号相当于原始信号加上移相器得到的结果，移相器可以用传递函数 $H ( f )$ 来表征，具体表达[1为

$$
\begin{array} { r } { H ( f _ { 1 } + f _ { o } ) = e ^ { \frac { i 2 \pi \mathrm { D } \cdot \mathrm { D } \mathbf { M } \cdot f _ { 1 } ^ { \ 2 } } { ( f _ { 1 } + f _ { o } ) f _ { o } ^ { 2 } } } } \end{array}
$$

其中， $f _ { o }$ 为本振频率； $f _ { 1 }$ 为中频频率。

由传递函数 $H ( f )$ 可知，原始信号可以通过乘以其复共轭 $H ( - f )$ 进行完全消色散，消除整个观测带宽内的色散相应，如图3，最大的时间分辨率为 $1 / ( 2 \cdot B W )$ 。这种消色散方法可用于高精度毫秒脉冲星计时和脉冲星射电辐射过程的研究。

理论上讲，两种消色散结果的差异主要由各个通道的剩余色散量造成的累加效应，因此分析两种消色散效果可以通过分析各个通道的剩余色散量实现。

对于上边带信号的非相干消色散，由(2)式可知，整个带宽 $B W$ 内的最大时延：

$$
\begin{array} { r } { t _ { D e l a y } = \boldsymbol { \mathrm { D } } \cdot \boldsymbol { \mathrm { D } } \boldsymbol { \mathrm { M } } \cdot \frac { ( 2 f _ { o } + B W ) \cdot B W } { f _ { o } ^ { 2 } ( f _ { o } + B W ) ^ { 2 } } \boldsymbol { \rlap / v } \ne \ , } \end{array}
$$

其中， $B W$ 为观测带宽。

单个通道的时间延迟：

$$
\begin{array} { r } { t _ { d e l y } = \mathrm { D } \cdot \mathrm { D } \mathsf { M } \cdot \frac { 2 \cdot b w } { \{ [ f _ { o } + n b w ] ^ { 3 / 2 } - \frac { b w ^ { 2 } } { 4 \cdot \sqrt { f _ { o } + n b w } } \} ^ { 2 } } \quad , } \end{array}
$$

其中， $b w$ 为单个通道带宽， $\begin{array} { r } { b w = \frac { 2 \cdot B W } { N \_ b i n f } } \end{array}$ Nbinf；N_binf为滤波器组的通道数；n的取值范围为[1,N_binf/2]。对于 $f _ { o } \gg b w$

$$
\begin{array} { r } { t _ { d e l y } \approx \mathrm { D } \cdot \mathrm { D } \mathrm { M } \cdot \frac { \boldsymbol { 2 } \cdot \boldsymbol { b } w } { [ f _ { o } + n b w ] ^ { 3 } } \quad . } \end{array}
$$

# 2脉冲星信号模拟、消色散算法及比较方法实现

本研究用MATLAB 程序模拟了被射电望远镜接收到的脉冲星信号，实现了两种消色散过程和两种消色散方法效果的定量比较过程，具体过程如下。

# 2.1原始信号模拟

脉冲星辐射的原始信号很弱，为了提高信噪比，需要长时间的积分。为了简化计算，此处模拟一个周期的基带信号。为了便于比较两种方法的消色散效果，周期采用短周期0.00390625秒，同时为了提高程序的运算效率，采样率（2Gbps）、采样时长和信号带宽BW等都取2的幂指数。加色散前的基带信号和加色散后基带信号如图4。

![](images/3c5f5ac05695964155db32c9e4b57b08a62e687930fd88659b3bfc3ab2171893.jpg)  
图4（a）加色散前的基带模拟信号，(b)加色散后的基带模拟信号；信号频谱带宽 $B W$ 为 $1 \mathrm { G H z }$ ，起始频率 $f _ { o }$ 为 $1 \mathrm { G H z }$ ，色散量 DM为 $4 0 ~ \mathrm { c m } ^ { - 3 }$ ·pc，图5也取同样的取值

Fig.4Theleftimageisthebasebandanalogsignalbeforeaddingdispersion,theightimageisthebasebandsignalaftertheadding dispersion; Signal spectrum bandwidth BW : 1 GHz, the starting frequency $f _ { o } : 1$ GHz,the Dispersion Measure DM : $4 0 ~ \mathrm { c m } ^ { - 3 }$ ' pc. In the figure.5 those variables also take same value

(1）模拟带宽为BW，起始频率为 $f _ { \mathrm { o } }$ ，谱指数为-2.0的基带信号[]。  
(2）把频域的模拟基带信号通过逆傅里叶变换到时域，进行高斯脉冲调制。(3）把调制后信号再通过傅里叶变换到频域，乘以传输函数H(f)后进行加色散。  
(4）把加色散的频域信号再变换到时域，加高斯白噪声成模拟的脉冲星时域信号。

# 2.2消色散算法实现

根据模拟长度为N_data的脉冲星信号数据，利用MATLAB程序实现信号的消色散过程，并实现两种消色散后的序列与加色散前序列的相关过程。

2.2.1 非相干消色散步骤

(1)数据分箱：把模拟的基带数据按顺序平均分箱。  
(2)多相位滤波[10.11]：对每个箱中的数据进行多相位滤波，数据序列长度减小原始的 $\textstyle { \frac { 1 } { 4 } } $ ；这可以减弱傅里叶变换的频谱泄露。多相位滤波过程为：利用相同长度的 sinc函数序列依次乘以每个箱中的数据，把得到的序列按顺序平均分成4段，并逐次对应相加得到原始箱内序列 ${ } _ { \frac { 1 } { 4 } } ^ { \cdot \frac { 1 } { 4 } \cdot }$ 长度数据。  
(3）傅里叶变换：对每个箱中的数据进行傅里叶变换。  
(4)分通道并平移数据：取参考频率为截止频率 $f _ { h i g h }$ ，任意通道中心频率 $f$ 的通道按延迟时间平移。由(2)式可知，相对延迟时间为

$$
t _ { - } d e l a y = D \times D M \times \mathrm {  { ~ \cal ~ ( ~ } } \frac { \mathrm {  { ~ 1 ~ } } } { f ^ { 2 } } - \frac { \mathrm {  { ~ 1 ~ } } } { f _ { h i g h } ^ { 2 } } \mathrm {  { ~ \Gamma ~ } } .
$$

(5）逆傅里叶变换并求和：把每个箱中数据在进行逆傅里叶变换，然后对箱内的数据求和得到分箱后的数据序列，非相干消色散后的信号见图5。

![](images/1182e241418bb71a4a37a047643a67857faefcbb2292facbf88b30ae170a9c62.jpg)  
图5 (a)非相干消色散后信号的二维频谱;(b)相干消色散后信号的二维频谱

Fig.5Thetwo-dimensionalspectrumofthesignalafterincoherentde-dispersion，thetwo-dimensionalspectrumofthesignalafte

coherent de-dispersion

# 2.2.2相干消色散步骤

基带信号只有一个周期，为了简化运算，将每次处理的数据长度也定为一个周期。具体步骤如下

(1)直接进行傅里叶变换：把模拟的基带数据进行傅里叶变换，得到频域数据。(2)频域消色散：把频域数据乘以消色散函数 $H ( - f )$ 得到消色散后的频域数据。(3)进行逆傅里叶变换：把消色散后的频域数据进行逆傅里叶变换得到原始序列长度的消色散后的时域数据。(4)折叠成分箱序列：把消色散后的数据依次折叠成与非相干消色散分箱后序列长度相同的箱，然后把每个箱中的数据累加得到序列，相干消色散后的信号见图5。

# 2.3消色散效果的定量比较

为了定量分析两种消色散，让两种消色散后的结果与加色散前的数据进行互相关，求它们的互相关系数:

$$
\begin{array} { r } { c o r \_ c o e f = \frac { \frac { 1 } { N } ( \sum _ { i = 1 } ^ { N } x _ { i } \cdot y _ { i } ) } { \sqrt { \frac { 1 } { N } \left( \sum _ { i = 1 } ^ { N } x _ { i } ^ { 2 } \right) \frac { 1 } { N } \left( \sum _ { i = 1 } ^ { N } y _ { i } ^ { 2 } \right) } } \quad , } \end{array}
$$

其中， $x _ { i }$ 属于长度为 $N$ 的序列 $X$ ， $\mathsf { y _ { i } }$ 属于长度为 $N$ 的序列 $Y$ 。目前普遍认为，相关系数的绝对值在0.3以下代表无直线相关，0.3以上代表直线相关，0.3-0.5代表低度相关，0.5-0.8代表显著相关（中等程度相关)，0.8以上代表高度相关；当且仅当其绝对值为1时，代表线性相关。对于研究的信号，表明两个信号完全相同，如相同的脉宽和信噪比。具体步骤为：

(1)把加色散前的模拟数据按上面的方法折叠累加成长度与非相干消色散分箱后序列长度相同的数据序列。

(2)把两种消色散后的数据与上一步的分箱数据进行互相关得到互相关系数。

# 3两种消色散的定量比较

首先，根据傅里叶变换的理论，给出两种消色散过程的主要计算量，并记录两种消色散过程的耗时；其次，定量比较两种消色散的效果；最后，两种消色散效果相当时，估计信号频谱的起始频率。

在信号模拟和消色散过程中，色散量的取值为 $1 { \sim } 4 0 \ \mathrm { c m } ^ { - 3 } \cdot \mathrm { p c }$ ，步长为 $1 ~ \mathrm { c m } ^ { - 3 } \cdot \mathrm { p c } .$ 信号频谱带宽BW取值为 $3 2 \mathrm { M H z }$ 、 $6 4 \mathrm { M H z }$ 、 $1 2 8 ~ \mathrm { M H z }$ 、 $2 5 6 ~ \mathrm { M H z }$ 、 ${ 5 1 2 } \mathrm { M H z }$ 和 $1 \mathrm { G H z }$ ，单通道带宽为 $1 \mathrm { M H z }$ 。信号频谱起始频率的取值范围为 $2 5 6 \mathrm { M H z } \sim 8 \mathrm { G H z }$ ，对于比较运算耗时和消色散效果,其步长为 $6 4 \mathrm { M H z }$ ，对于确定两种消色散效果相同时的频谱起始频率,其步长为$1 6 \mathrm { M H z }$ 。

# 3.1两种消色散结果得到的互相关系数的比较

通过计算得到两种消色散后的数据与加色散前数据的相关系数如图6、图7。首先分析两种消色散结果得到互相关系数随各变量的变化特点。

![](images/212eb47c1b05cff314b1cd2f30ebf79166a843a531df40b591a204ce0ac8a2fb.jpg)  
图6 相干消色散后的数据与加色散前的数据的相关系数；为了便于显示，此处相关系数乘了1000 倍 Fig.6thecoherencecoefficientoftedataftertecoherentde-dispersionwiththdatabeforeteaddingdispersion.Tofaciliatete display,the coherence coefficient is multiplied by 1000

由图6可知，相干消色散得到的相关系数接近于1，这说明，在不考虑离散化运算过程中引入的误差时，相干消色散可以完全恢复原始加色散之前的信号。结合两图可以发现，当BW减小时，相关系数的波动变大，这与(9)式有关；其次，数据处理过程存在频谱泄露，这是由于数据在周期性分箱过程中产生一些截断频点，有限长离散数据的傅里叶变换有频谱泄露，这些效应的影响随着BW的减小而增大。

两种消色散得到的相关系数见图7。对于相同的色散量 $D M$ ，频谱起始频率 $f _ { o }$ 的取值在一定范围内，相关系数之差随着变量 $f _ { o }$ 指数减小，但到某值 $f _ { 1 }$ 之上，该相关系数之差接近于1且波动逐渐变小，这说明在频谱起始频率 $f _ { o }$ 低于 $f _ { 1 }$ 时，非相干消色散的效果比相干消色散的差，且两种方法的消色散效果的差距随着 $f _ { o }$ 的增加而缩小，在 $f _ { o }$ 高于 $f _ { 1 }$ 时，两种方法的消色散效果相同。结合两图可以看出，相同 $f _ { o }$ 、随 $D M$ 变化对应的相关系数的变化曲线随着 BW的减小起伏变大，这是数据处理中的频谱泄露的误差造成的。相同 $f _ { o }$ 、相同DM对应的相关系数之差随BW的增大而减小，且 $f _ { 1 }$ 随 $B W$ 的减小而增大。结合(6)式和图7可知，在不考虑误差范围时，在一定观测频率内，相干消色散效果优于非相干消色散效果，两种方法的消色散效果的差距随观测带宽、观测频率的增加而按指数关系减小，而随着色散量的增大而按幂指数关系增大，同时能够确定，可以找到两种方法消色散效果相同时的观测起始频率。

![](images/9e65c1b28eeea0e2822ea965cd26b3b138fea4e1c4c414b5fa4de68ba67448a8.jpg)  
图7两种消色散方法得到的相关系数之差  
Fig.7Thecoherencecoeficientofthedataafter theincoherentde-dispersionwiththedatabefore theaddingdispersion

# 3.2两种消色散效果相同对应的通带起始频率

两种消色散效果相同时,这对应于非相干消色散单通道内的时延 $t _ { d e l y }$ 取某一接近零常数。非相干消色散过程，若通道带宽bw为常数，由(6)式可得

$$
\begin{array} { r } { t _ { d e l y } \propto \frac { \mathrm { D M } } { [ f _ { o } + n b w ] ^ { 3 } } \quad , } \end{array}
$$

由上式， $t _ { d e l y }$ 为常数，有

$$
f _ { o } + n b w \propto \sqrt [ 3 ] { D M }
$$

经过计算，在两种消色散后的数据与加色散前的数据的相关系数小于某一定值条件下，得到频谱起始频率 $f _ { o }$ 如表1，考虑到如上所述数据处理中引入的误差，这个值取0.01。

# 4结论

运用MATLAB程序实现了两种消色散过程的定量比较，并确定了两种消色散方法相同时的频谱起始频率。在实现比较过程,色散量的取值为 $1 { \sim } 4 0 ~ \mathrm { c m } ^ { - 3 } \cdot \mathrm { p c }$ ，步长为 $\mathrm { ~ 1 ~ } \mathrm { c m } ^ { - 3 }$ : pc;信号频谱带宽BW取值为 $3 2 \mathrm { M H z }$ 、 ${ 6 4 } \mathrm { M H z }$ 、 $1 2 8 ~ \mathrm { M H z }$ 、 $2 5 6 ~ \mathrm { M H z }$ 、 ${ 5 1 2 } \mathrm { M H z }$ 和 $1 \mathrm { G H z }$ ，单通道带宽为 $1 \mathrm { M H z }$ ；信号频谱起始频率的取值范围为 $2 5 6 \mathrm { M H z } \sim 8 \mathrm { G H z }$ ，对于比较运算耗时和消色散效果,其步长为 $6 4 ~ \mathrm { M H z }$ ，对于确定两种消色散效果相同时的频谱起始频率,其步长为 $1 6 \mathrm { M H z }$ 。定量的比较结果说明在一定的观测频率之内相干消色散的效果优于非相干消色散，实际观测中可以根据观测要求，参考这些结果，选择消色散方法；最后研究了在不同色散量和不同频谱带宽下，两种消色散技术消色散效果相同时的起始频率，非相干消色散脉冲星观测系统在实际的观测中可以参考这些频率制定观测频段。非相干消色散过程引用了多相位滤波器，一定程度上缓解了傅里叶变换的频谱泄露问题；但是频谱泄露问题依然存在，尤其在低频端和高频端。下一步将扩展色散量的变化范围和变化的单个通道带宽，同时继续改善频谱泄漏问题。

表1不同BW、DM对应消色散效果相同时的 $\mathcal { F } _ { \circ }$ ，其单位是MHz；这只是部分数据Table1the $f _ { o }$ to different BW and DM,which corresponds to the de-dispersion effect, theunit is MHz; Thisis just part of the data  

<html><body><table><tr><td>BW/MHz</td><td>32</td><td>64</td><td>128</td><td>256</td><td>512</td><td>1024</td></tr><tr><td>DM=5 cm-³ · pc</td><td>608</td><td>592</td><td>560</td><td>512</td><td>448</td><td>400</td></tr><tr><td>DM = 10 cm-³ · pc</td><td>800</td><td>736</td><td>704</td><td>656</td><td>592</td><td>528</td></tr><tr><td>DM = 15 cm-³ · pc</td><td>912</td><td>848</td><td>816</td><td>768</td><td>688</td><td>608</td></tr><tr><td>DM = 20 cm-³ · pc</td><td>976</td><td>928</td><td>896</td><td>848</td><td>768</td><td>688</td></tr><tr><td>DM = 25 cm-³ · pc</td><td>1056</td><td>1024</td><td>992</td><td>912</td><td>832</td><td>752</td></tr><tr><td>DM = 30 cm-³ · pc</td><td>1152</td><td>1072</td><td>1056</td><td>976</td><td>896</td><td>800</td></tr><tr><td>DM = 35 cm-³ · pc</td><td>1232</td><td>1152</td><td>1104</td><td>1040</td><td>960</td><td>848</td></tr><tr><td>DM = 40 cm-³ · pc</td><td>1232</td><td>1200</td><td>1152</td><td>1088</td><td>1008</td><td>896</td></tr></table></body></html>

致谢：由衷感谢北京大学李柯伽老师和国家天文台卢吉光博士在脉冲星信号模拟中的指导。

# 参考文献：

[1] Lorimer DR,Kramer M.Handbook of Pulsar Astronomy [M]. Cambridge: Cambridge University Press, 2005.   
[2] 徐永华，罗近涛，李志玄等．基于MARK5B $+$ DSPSR 的基带数字脉冲星观测系统 [J].天文研究与技 术—国家天文台台刊，2013，10(4)：72-78. Xu Yonghua, Luo Jintao,Li Zhixuan,et al. Apulsar observation system with a Mark 5B recording system anda DSPSR software [J]．Astronomical Research & Technology—Publications of National Astronomical Observatories of China，2013，10(4）：352-358.   
[3] Kramer M，Stairs IH,Manchester R N，et al.Tests of general relativity from timing the double pulsar[J]. Science，2006，314(5796):97-102.   
[4] Shappee B J, Simon JD, Drout M R,et al. Early spectra of the gravitational wave source GW170817: Evolution of a neutron star merger [J]. Science,2O17, 358: eaaq0186.   
[5] Downs G S. Interplanetary Navigation Using Pulsating Radio Sources[J]. NASA Technical Reports Server. 1974.   
[6] IHStairs，E M Splaver.A Baseband Recorder for Radio Pulsar Observations [J]. Monthly Notices of the Royal Astronomical Society，1999，1-20.   
[7] B R Nayana， S Madhava Kumar. Application of Coherent De-dispersion DSP Algorithms in Study of Pulsar Data [J].Digital Signal Processing,2012.   
[8] 刘立勇，艾力·伊沙木丁，张晋．乌鲁木齐天文站建立脉冲星相干消色散观测系统 [J].天文研究与技 术—国家天文台台刊，2007，4(1)：72-78. Liu Liyong，Ali Esamdin， Zhang Jin.Pulsar coherent de-dispersion system in the Urumqi Observatory [J]．Astronomical Research & Technology—Publications of National Astronomical Observatories of China，2007，4(1):72-78.   
[9] Hankins TH，Rickett B J.Pulsar Signal Processing[J].Methods in Computational Physics Advances in Research& Applications，1975，14：55-129.   
[10] Jayanth Chennamangalam.The Polyphase Filter Bank Technique [OL].https://asper.berkeley.edu/wi-ki/The_Polyphase_Filter_Bank_Technique.   
[11] 托乎提努尔，张海龙，王杰.基于CUDA 的射电天文多相滤波器组设计[J].天文研究与技术——国家 天文台台刊,2017,14(01):117-123. Tohtonur， Zhang Hailong，Wang Jie.A Design of Polyphase Filter Bank for radio astronomy based on CUDA[J]. Astronomical Research & Technology Publications of National Astronomical Observatories of China，2017，14(01):117-123.

# Comparative Study between the Coherent De-dispersion and the Incoherent De-dispersion of Pulsar Signal

Huang Yuxiang1,2, Wang Min1, Hao Longfei1,Li Zhixuan1, Xu Yonghual (1. Yunnan Observatory of Chinese Academy of Sciences, Yunnan Kunming 650o11; 2. University of Chinese Academy of Sciences, Beijing 100049)

Abstract: Spreading through in the interstellar space, pulsar signals,due to the existence of the interstellar medium, would be observed dispersively, therefore we need to remove dispersion of the received pulsar signals for obtaining the original pulsar signals. The current de-dispersion methods are mainly divided into two types,coherent de-dispersion and incoherent de-dispersion. Relatively speaking,the former is able to eliminate dispersion completely，which has simpler algorithm,and preserves the time resolution of the original signal, but has the larger amount of calculation. But the rapid progress of computer technology has already solved the problem of calculated amount. In order to accurately understand the difference between the two methods of de-dispersion, this paper,adopting the method of coherence coefficient, quantitatively compares the effects of coherent de-dispersion and incoherent de-dispersion: below a certain frequency, the former is better than the latter in obtaining the de-dispersion eects.Meanwhile,the observed frequency of the two de-dispersion methods at the same effect is determined.

Key words:Pulsar； Coherent de-dispersion；Incoherent de-dispersion