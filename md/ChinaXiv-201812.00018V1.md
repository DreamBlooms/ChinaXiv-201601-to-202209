# 宽视场成像网格化算法中w-plane最优经验值研究

于晓雨’邓辉1,2-梅盈‘卫守林‘石聪明‘王威³戴伟‘王锋12(1.昆明理工大学云南省计算机技术应用重点实验室；2．广州大学天体物理中心；3.中国科学院国家天文台)

摘要：射电干涉阵列宽视场成像网格化处理过程中必须考虑 $\boldsymbol { \mathsf { w } }$ 项的影响。w-projection和wlstacking 是两个重要的宽视场成像网格化处理算法，w-plane 参数是算法中影响计算速度和成图质量的一个重要因素。本文研究了w-projection和w-stacking两种网格化算法，利用 SKA1低频阵台站数据和ASKAP 软件包进行模拟观测，对两种算法在不同w-plane参数取值情况下的成图速度和成图质量进行了定量分析对比。结果进一步表明w-plane 是性能改善的重要参数，针对w-projection算法来说，w-plane取值应比一般给定的经验值要大才能较好的得到成像效果。w-stacking算法虽然有很大的速度优势，但算法实现中w-plane的影响更为显著，论文给出了推荐的w-plane取值。本文工作是大视场成像算法的基础研究工作，对未来SKA科学数据处理中的管线设计有较好的参考价值。

关键词：SKA-SDP宽视场成像 网格化算法中图分类号：P161 文献标识码：A 文章编号：1672-7673(2018)xx-xXXX-xX

平方公里阵 SKA(square kilometer array）将是国际上建造的最大综合孔径射电望远镜[1]。SKA 由数千个反射面天线和多达一百万个低频天线组成，总接收面积达到一平方公里。

SKA 科学数据处理(Science Data Processor,SDP)是 SKA 设计中的一个重要组成部分。SDP 专注于设计硬件平台、软件和算法来处理射电望远镜的观测数据[2]。SDP 的设计面临的挑战是多方面的。SDP 需要处理来自望远镜的海量观测数据量。SKA1(约占 $10 \%$ 的总体规模)数据量将达到300PB/年。为了满足SKA 科学研究开展的需要，SDP在数据处理管线设计中，需要充分地考虑数据处理的性能与质量。由于SDP 处理需要的计算力高出现有最大的天文数据处理系统两个数量级，SDP的关键算法的运行速率要达到百万兆级的运算水平。SKA2的计算力需求估计需要达到4Exaflops 的水平。因此，开展对 SDP 数据处理中关键算法的研究，提高数据处理的性能具有显著的意义。

网格化（Gridding）算法是综合孔径望远镜数据处理中的一个重要算法，对计算的消耗占据了很大比重。对网格化算法进行性能优化，对 SDP有显著的价值和意义。低频射电望远镜大视场成像受到很多条件的制约，其中最重要的一个影响因素是非共面基线效应。在大视场与非共面基线效应下，对可见度数据直接进行傅立叶变换会导致图像严重畸变，因此，在大视场成图时，解决w项的问题至关重要。目前，应对大视场与非共面基线效应的算法有：faceting[3]、三维傅立叶变换[4]、w-projection[5]、w-stacking[6]和 warped snapshots[4]等算法以及其他复合算法。在这些方法中，w-projection 和 w-stacking 是目前应用相对较广的网格化算法。其中w-projection 算法在牺牲较大内存的情况下，具有优越的计算速度和误差控制。该方法不仅可以使用传统的洁化(CLEAN)方法去卷积，还可以选择多尺度洁化方法，在高动态范围下，有较大的优势，相位中心基本不失真。w-stacking 算法在图像空间以消耗更多的内存为代价处理傅里叶空间中的w 项，计算速度优于w-projection 快[7]。

在 w-projection 和 w-stacking 算法的具体实现过程中，w-plane 是一个重要参数。在w 的最大值和最小值之间分出多个w-plane，对不同w-plane 的可见度数据使用不同的卷积核进行卷积运算。因此，w-plane 的数量直接影响到算法的计算速度、内存开销以及成图质量。本文主要对 w-projection 和 w-stacking算法在实现与实际运行中的w-plane 进行实验研究，利用 SKA1低频阵台站数据和 ASKAP 软件包进行模拟观测，以期掌握w-plane 对整体计算性能的影响，为后期的 SKA-SDP 建设以及国内科学数据中心建设中的管线系统设计提供参考。

# 1、w-plane

低频射电望远镜大视场成像最重要的一个影响因素就是非共面基线效应，在非共面基线效应的影响下w项的值将远远大于1，因此直接对可见度数据进行二维傅里叶变换的条件已经不满足，针对这一问题，天文学家提出了一系列算法用来应对非共面基线效应造成的图像畸变。w-projection 算法通过将不同w 值的可见度数据投影到 $\scriptstyle \mathbf { w } = 0$ 平面，从而消除w项的影响，有效提高成图质量。w-stacking 算法能够在像平面矫正非共面基线效应引起的相位偏移从而有效还原天空亮度分布。

# 1.1 w-projection算法中的 $| w - p |$ ane

在射电综合孔径成像处理过程中，可见度数据与天空亮度之间的关系如公式（1）所示：

$$
V ( u , \nu , w ) = \int _ { - \infty } ^ { \infty } \int _ { - \infty } ^ { \infty } \frac { I ( l , m ) } { \sqrt { l - l ^ { 2 } - m ^ { 2 } } } e ^ { - 2 \pi i [ u l + \nu m + w \sqrt { l - l ^ { 2 } - m ^ { 2 } } - l ] } d l d m
$$

-projection 算法将不同w值的可见度数据投影到 $\scriptstyle \mathbf { w } = 0$ 平面，公式（1）简化为（2

$$
V ( u , \nu , w \ = \ 0 ) \ = \ \int _ { - \infty } ^ { \infty } \int _ { - \infty } ^ { \infty } \frac { I ( l , m ) } { \sqrt { l \mathrm { ~ } - l ^ { 2 } \mathrm { ~ } - m ^ { 2 } } } e ^ { [ - 2 \pi i ( u l + \nu m ) ] } d l d m
$$

经过简单的指数运算，式（1）变化为式（3）和（4）：

$$
V ( u , \nu , w ) ~ = ~ \int _ { - \infty } ^ { \infty } \int _ { - \infty } ^ { \infty } { \frac { I ( l , m ) } { \sqrt { l - l ^ { 2 } - m ^ { 2 } } } } G ( l , m , n ) e ^ { - 2 \pi i [ u l + \nu m ] } d l d m
$$

$$
G ( l , { \pmb m } , { \pmb n } ) = e ^ { - 2 \pi i { \pmb w } ( \sqrt { { l } - { l } ^ { 2 } - { \pmb m } ^ { 2 } } - l ) }
$$

公式（3）、（4）可以改写为公式（5），其中卷积核通过公式（6）近似计算得到：

$$
V ( u , \nu , w ) = \hat { G } ( u , \nu , w ) \ast V ( u , \nu , w = 0 )
$$

$$
\hat { G } ( u , \nu , w ) = \frac { i } { w } e ^ { - \pi i [ \frac { u ^ { 2 } + \nu ^ { 2 } } { w } ] }
$$

上述过程显示，在w-projection 算法中，卷积核是算法的核心。理想情况下，位于不同w-plane 的可见度数据，在计算过程中应该采用不同的卷积核。在实际计算过程中，一般计算w的最大和最小值，在最大和最小值之间平均分成多个w-plane，然后对每个w-pane按照公式（6）计算卷积核并保存下来，最后对每个可见度数据与其距离最近的w-plane 的卷积核进行卷积，从而实现到 $\scriptstyle \mathbf { w } = 0$ 平面的投影。

显而易见，w-plane 的值越大，投影效果越好，但是计算量和内存消耗大；w-plane 的值越小，计算量和内存消耗小，但是投影效果欠佳。当w-plane 的数量为零，则直接退化为二维傅立叶变换。Comwell等在前期研究中取最大的w 值的平方根作为经验值[5]。

# 2 w-stacking 算法中w-plane

w-stacking 算法的提出也是为了消除非共面基线效应对大视场成像的影响，但是不同于w-projection 算法，w-stacking并没有消除w项，而是对其进行了修正。

根据公式(1)将uv空间转换到 $\mathrm { l m }$ 空间得到式（7）：

$$
\frac { I ( l , m ) } { \sqrt { I - l ^ { 2 } - m ^ { 2 } } } \ = \ e ^ { 2 \pi i w ( \sqrt { I - l ^ { 2 } - m ^ { 2 } } - I ) } { \int _ { - \infty } ^ { \infty } } \int _ { - \infty } ^ { \infty } V ( u , \nu , w ) e ^ { 2 \pi i ( u l + \nu m ) } d u d \nu
$$

$$
\frac { I ( l , m ) \left( w _ { \mathrm { m a x } } - w _ { \mathrm { m i n } } \right) } { \sqrt { I - I ^ { 2 } - m ^ { 2 } } } = \int _ { w _ { \mathrm { m i n } } } ^ { w _ { \mathrm { m a x } } } e ^ { 2 \pi i w ( \sqrt { I - I ^ { 2 } - m ^ { 2 } } - I ) } { \int _ { - \infty } ^ { \infty } } \int _ { - \infty } ^ { \infty } V ( u , \nu , w ) e ^ { 2 \pi i ( u I + v m ) } d u d \nu d w
$$

其中 ${ w _ { \mathrm { m a x } } }$ 和 ${ \pmb w } _ { \mathrm { m i n } }$ 代表 $\mathbf { w }$ 的最大值和最小值。式(8)的等号右侧包括两部分，一是二维傅立叶变换，二是对 $\mathbf { w }$ 的复数积分。对式（8）的等号右侧离散化得到式（9）：

$$
\frac { I ( l , m ) \left( w _ { \mathrm { m a x } } \mathrm { ~ - ~ } w _ { \mathrm { m i n } } \right) } { \sqrt { I - { l ^ { 2 } } \mathrm { ~ - ~ } m ^ { 2 } } } = \sum _ { a = w _ { \mathrm { m i n } } } ^ { { w _ { \mathrm { m a x } } } } e ^ { 2 \pi u w _ { a } ( \sqrt { I - { l ^ { 2 } } - m ^ { 2 } } - I ) } \mathcal { F } ^ { - l } \Big \{ { V ( u , \nu , w _ { a } ) } \Big \}
$$

其中 $\mathcal { F } ^ { - I } \big \{ V ( \pmb { u } , \pmb { \nu } , \pmb { w } _ { \pmb { a } } ) \big \}$ 表示将可见度数据在特定的离散 w-plane 上进行网格化。

w-stacking算法的实现步骤如下：

(1）根据可见度数据 $\mathbf { w }$ 的范围设定w-plane 的细分粒度；(2）依据每个可见度数据的w值，将可见度数据网格化到某一w-plane;(3）对每个w-plane 的可见度数据进行二维傅立叶变换得到相应图像;(4）根据w值对各个w-plane 的图像进行相位矫正;(5）加权叠加所有图像，得到最终图像。在 w-stacking 算法实现过程中，w-plane 分的过粗会导致产生伪影，分的过细又会增大计算量和内存消耗。同时，w-stacking 算法将不同w-plane 上的可见度数据看成是相互独立，各个面的数据可以并行进行二维傅立叶变换和相位改正，因此，w-stacking算法在并行实现方面具有优势。

# 3观测模拟仿真实验

# 3.1实验环境

为了验证w-plane 的影响，以期获得较为理想的w-plane 取值，在确保成像质量的情况下降低成像处理时间，本文进行了一系列实验。数据处理软件采用了澳大利亚 SKA 探路者(Australian SKA Pathfinder,ASKAP)的数据处理软件系统[8]。ASKAP通过名为ASKAPsoft的软件系统进行望远镜观测控制和数据处理[9]，ASKAPsoft框架由三部分组成：望远镜观测系统、处理中心和科学数据存档。ASKAP 通过 bash shell脚本组合ASKAPsoft 中的程序形成数据处理管线，主要的数据处理管线有数据摄取管线、定标管线和成图管线[10]。

本实验在8台汉柏服务器上完成，具体硬件配置如表1所示。

表1硬件设备参数  
Table1 The parametersof device   

<html><body><table><tr><td>硬件设备</td><td>设备参数</td></tr><tr><td>服务器型号</td><td>C640G3(8)</td></tr><tr><td>CPU</td><td>Intel Xeon E5-2620 v3</td></tr><tr><td>内存</td><td>128GB</td></tr><tr><td>网络</td><td>Infiniband+10Gb 以太网</td></tr></table></body></html>

# 3.2模拟观测与成像处理

为了分析 w-plane 对 w-projection 和w-stacking 中的影响，我们采用了模拟观测、成像、对后续图像进行分析的方法来验证不同的w-plane 造成的影响。

# 1、模拟观测

实验采用 SKA1-LoW 望远镜的 512个天线台站坐标数据，天线布局如图1所示。天空模型由 73个点源构成，整体形状为"米"字，如图2(a)所示。实验采用16个计算节点，每个计算节点处理一个通道的数据，通道带宽1MHZ，因此观测频率覆盖范围16MHz，积分时间间隔 150s，模拟观测时长6小时。

SKA1-Low天线频率覆盖范围 ${ 5 0 } { - 3 5 0 } \mathrm { M H z }$ ，本实验中心参考频率为 ${ 1 0 0 } \mathrm { M H z }$ ，设置16个带宽为1MHz的通道，因此观测频率范围为92-108MHz。

![](images/067d7398c9a230c6f3c58d9c0023551baec9e7809a9b1acc07b5e54b87f522a6.jpg)  
图1天线分布Fig.1 Antennas layout

使用模拟观测程序对天空模型进行16个通道的模拟观测，得到18837504行5.5GB 的模拟可见度数据。

# 2、成像处理

使用 w-projection 和 w-stacking 算法，对模拟观测获得的可见度数据16个通道进行连续谱成图。ASKAP成图管线在8个计算节点上并行运算，每个计算节点处理两个通道。实验过程中，不断改变W-plane 的数量，得到不同w-plane设置下的图像，并记录每次成图时间供后续分析使用。图4（a）显示了随着w-plane 数量的增长，两种算法处理时间的变化。

图2(b)是二维傅立叶处理得到的图像，可以看到w项影响导致的拖尾效应(Smearing)非常明显。图 3是 w-plane 数量设置为171的情况下，w-projection 和 w-stacking 算法处理得到的图像，拖尾效应得到抑制，但边缘的模拟星并没有被很好地还原。

![](images/ace939821a46e1a2e97e61914ee3257ef3b62c08289f593b0690040a6c44f4e3.jpg)  
图2(a)天空模型图；(b)二维傅里叶变换成像结果  
Fig.2(a) Sky model image; (b) The result of two-dimensional Fourier transform imaging

![](images/8e211632e9de6d7ca76a6b819f734fb21a00228f91980298ebd1f8770b7e92ec.jpg)  
图3(a)w-projection 算法的成图结果；(b)w-stacking 算法的成图结果 Fig.3 (a) The result of the W-projection imaging; (b) The result of the W-stack imaging

# 3、图像质量评价方法

为了评价不同w-plane 数量下的两种算法的成像质量，研究采用了SELAVY软件包，该软件包是Duchamp 星源搜索算法在 ASKAP 软件中的实现模块，用来搜索观测结果中的星数量。由于在仿真观测时已经预设了总的星数为73，同时所有星的位置已知。因此，通过 SELAVY搜索出的星与已知天空模型星进行对比，利用正确还原的星数量来快速判断成像的质量。图4（b）显示了随着w-plane 数量的增长，SELAVY 搜索出点源数量的变化。

![](images/92e13c2f0756c13c37a5d11567a6357fb77bd7955edf3f6bb34e7b4a70abe992.jpg)  
图4(a)计算时间与w-plane 的关系;(b)SELAVY搜索出点源数量与w-plane 的关系  
Fig.4(a)Therelationbetweetheruningtimeandw-plane;(b)Therelationbetweethenumberofsearchedsourcesandw-plane

# 3、结果分析

本实验最大基线长度81602米，最大w约为28000个波长。根据Cormwell等前期研究的结果，w-plane 值一般设置为最大w 的平方根，也就是167。

从图4(a)可以看到 w-projection 的运行时间随着 w-plane 值的增加呈近似线性增长。而 w-stacking 算法的运行时间则表现为：当 w-plane 的值小于 $\sqrt { \mathrm { w } }$ 的值的情况下其计算时间明显小于w-projection 算法；w-plane 的值大于 $\sqrt { \mathrm { w } }$ 的值后其增长速度很快并在w-plane 大于 $1 . 5 \sqrt \mathrm { w }$ 之后超过w-projection 算法的运算时间。这是由于大图像成像时太多的w-plane 需要进行相位的改正从而导致 w-stacking 算法的计算力消耗大增[1]，w-stacking 算法也就失去了速度优势。

SELAVY 软件包对两种算法在不同的w-plane下成图结果进行星像统计。从图4(b)可以看到在w-plane 较小的情况下w-stacking 算法成图得到星的数量多于w-projection 的结果，但是随着 w-plane 的增加两者的成图质量近似相同。

w-plane 的取值不同于以往的经验值 $\sqrt { \mathrm { w } }$ ，实验可以看出：在w-plane 大于 $1 . 5 \sqrt { \mathrm { w } }$ 之后成图质量更好，SELAVY 程序包可以得到所有的73个星源的数据，因此为获得高分辨率的天空图w-plane 的取值应大于 $1 . 5 \sqrt { \mathrm { w } }$ 。虽然两者的成图质量相同但是w-stacking 算法在w-plane 的值小于 $\sqrt { \mathrm { w } }$ 的值的情况下相较于 w-projection 具有很大的速度优势，但当w-plane 的值大于 $\sqrt { \mathrm { w } }$ 后，w-stacking 的速度优势将不存在。

通过分析这两种算法的成图质量和运行时间趋势，可以看到w-stacking 算法更适合w-plane 值小于$\sqrt { \mathrm { w } }$ 的情况，为弥补其w-plane较小引起的成像准确度的问题，今后可以考虑通过结合多波束观测进行成图，再通过 SKA的LINMOS(Linear Mosaic Applicator)软件包实现多波束成图后的拼接，该软件包实现一系列图片的线性拼接，从而提高成像质量。w-projection 算法则更适合通过提高w-plane 的值实现更为准确的成图。

# 4.结论

综上所述，针对w-projection 算法和w-stacking 算法在管线中的应用，有如下结论：

1、合理的w-plane 的取值对于成像有关键的作用。实验表明，w-plane 的取值应是经验取值 $\sqrt { \mathrm { w } }$ 的1.5 倍，此时 w-projection 算法和 w-stacking 算法都可以得到很好的成图质量，这与 Cormwell估计的有一定的偏差。2、W-plane 的取值对于结果的正确性有紧密的关系。事实上只有w-plane 取值较大时才有可能完整地恢复出天空信息。未来在数据处理时，应在准确度要求和计算时间需求方面进行折衷。当w-plane 的值小于 $\sqrt { \mathrm { w } }$ 的时候，w-stacking 算法比 w-projection 算法有很大的计算时间优势。对于成图分辨率要求高且 w-plane 的值大于 $\sqrt { \mathrm { w } }$ 的时候，w-stacking 算法将失去速度优势。

本文的工作表明 SKA-SDP 数据处理管线应根据不同的需求选择不同的gridding 算法，后续工作可以在运算速度提高，提高算法的并行性为研究重点，以期获得更好的处理能力。

# 参考文献

[1]DewdneyPE,HallPJ,Schilizi RT,et al.The square kilometre aray[J].Proc IEEE,2009,97:1482-1496   
[2]P.Alexander,V.Allan,etal.PDR.01SDArchitecture[EB/OL][018-09-13].htp://www.astron.nl/broekema/paprs/-   
PDR/PDR01%20System $\% 2 0 .$ Architecture.pdf   
[3]Coeles 261(1):353-364.   
[4] Perley R A. Synthesis Imaging in Radio Astronomy II[C].San Framcisco:NRA0/NMIMT,1999,180:383   
[5]ComwellataaropaseliiefetyeritJ]al Selected Topics in Signal Processing,2008,2(5):647-657.   
[6]B.HumphreysB,CowellTHumphesB,etal.AnalsisofCvolutioalResamplinglgrithPerforanceEB/L]-3.   
www.skatelescope.org/pages/page_memos.html   
[7]劳保强，安涛，陈晓,等．低频射电望远镜阵列宽视场成像技术研究[J].天文学报,2017,58(5):108-129.   
LaoBaoqiang,XietaseachdefeainglgiesfofreeJtatrocic 2017,58(5):108-129.   
[8]DeboerDRouGtoetaralatdergaagede-FeldurelepeJ]r the IEEE,2009,97(8):1507-1521.   
[9]Tim:/ [10] Chapman JM. CASDA: The CSIRO ASKAP Science Data Archive[J]. Iau General Assembly,2015,22.   
[1]GodrickLaecosructidtroi-olaatisDatdElectraldEctro University of Stellenbosch,2015.

# A Study on Optimal Experiential W-plane for Wide-Field Gridding Algorithm

Yu Xiaoyul, Deng Hui1,2,Mei Yingl,Wei Shoulin', Shi Congmingl,Wang Feng1,2 (1.Key Laboratory of Computer Technology Application;2.Center for Astrophysics, Guangzhou Universit

Abstract: Astronomy data processing platform is facing unprecedented big data challenge. SKA(square kilometer array)as the biggest radio synthesis telescope,its generated data rate of averaged visibilities will be hundred gigabit per second. SKA-SDP handles big data and extremely large computing cost by data processing pipeline. Gridding algorithm willtake a large proportion of compute load. How to save power cost and improve the computational eficiency,on the prerequisite of guaranteed imaging quality,need to be wel-onsidered. Wprojection and w-stacking are two gridding algorithms possibly be used in SKA-SDP; The present paper study on the effect of w-plane in those algorithms.Based on SKA continuum imaging pipeline and simulation observation, we analyze the effect of w-plane to the imaging results.Our experimental results show that w-plane is a crucial parameter for performance promotion, and w-plane should be bigger than experimental value in w-projection algorithm. Compare with w-projection algorithm, W-stacking have advantage in run time,yet w-plane have great effect on w-stacking algorithm.The present paper is a basic work for study on large field imaging,and a new wplane for w-projection and w-stacking algorithm is proposed. Our study can serve as a reference for designs of SKA data processing pipeline.

Key words: SKA-SDP; Wide-field imaging; Gridding algorithm