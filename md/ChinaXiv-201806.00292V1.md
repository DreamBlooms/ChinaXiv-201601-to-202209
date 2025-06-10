# 抚仙湖一米新真空太阳望远镜空间二维偏振光谱

# 观测模式设计与实现

陈宇超² 徐稚李正刚²袁沭²柳光乾许骏金振宇²(1．中国科学院大学，北京 100049；2．中国科学院云南天文台，云南 昆明 650011)

摘要：作为抚仙湖1m新真空太阳望远镜的观测终端之一，多波段光谱仪需具备两个观测模式，即空间二维扫描观测以及偏振光谱测量，从而实现诊断太阳矢量磁场及其动力学特征的科学目标，本文工作则紧紧围绕如何架构和实现上述两种观测模式而展开。首先明确观测模式对三大重要光电机构（即空间扫描机构、偏振分析器和仪器偏振定标机构）的基本要求，其次从实测太阳物理需要出发，分析这些要求的具体实现方法（连续式或步进式）、控制精度（ ${ { 1 0 } ^ { - 2 } }$ 或 ${ { 1 0 } ^ { - 3 } }$ ）以及信噪比提高方法（多帧叠加或多组叠加）等。最后梳理并给出了多种观测模式的流程图，并将不同观测模式集成于一个采集控制程序之中，投入实测，分别进行了多组活动区二维空间扫描观测和黑子偏振光谱测量，取得了较好的结果。

关键词：太阳光谱、偏振光谱测量、空间二维扫描、观测模式中图分类号：TP311.1 文献标识码：A 文章编号：

# 0.引言

目前，抚仙湖一米新真空太阳望远镜（New Vacum Solar Telescope，NVST）的终端观测系统主要包括多通道高分辨成像系统（Multi-channel high resolution imaging system）[]和多波段狭缝-光栅光谱仪（Multi-band spectrometer）。其中成像系统包括3个窄带波段（H-alpha $6 5 6 . 3 \ \mathrm { n m }$ HeI $1 0 8 3 \ \mathrm { n m }$ 以及CaII393.3nm）以及2个宽带波段（G-band $4 3 0 \ \mathrm { n m }$ 和TiO 705.8nm）。多波段光谱仪主要包括2条经典色球谱线（H-alpha656.3nm和CaII854.2nm）以及1条光球谱线（Fe$\mathrm { ~ I ~ } 5 3 2 . 4 \ \mathrm { n m } )$ 。表1中给出了多波段光谱仪的基本参数以及常规工作谱线[2]。其中FeI532.4nm 的朗德因子高达 1.5，是目前我国国内进行光球磁场测量的主要工作波段[3]。

表1.多波段光谱仪参数  
Table 1. the parameters of the Multi-Band Spectrometer at NVST.   

<html><body><table><tr><td>狭缝宽带 沿狭缝方向视场</td><td>100μm/60μm 129”</td></tr><tr><td>光谱仪像素分辨率</td><td>0.082”/pixel</td></tr><tr><td>光谱仪光谱分辨率</td><td></td></tr><tr><td>@5324A</td><td>0.00087 nm/pixel</td></tr><tr><td>@6563 A</td><td>0.0024 nm/pixel</td></tr><tr><td>@8542 A</td><td>0.0022 nm/pixel</td></tr></table></body></html>

\*基金项目：国家自然科学基金(11473064)资助.收稿日期：2018-01-24；修订日期：2018-03-12作者简介：陈宇超，男，博士．研究方向：天文技术与方法.Email:cyc@ynao.ac.cn通讯作者：徐稚，女，研究员．研究方向：太阳光谱分析及光谱仪研制．Email:xuzhi@ynao.ac.cn

![](images/6bb5906d3d64417273a38a47c9707d20c791843dc294f6d35b8e2a1a7fe430d3.jpg)  
图1.抚仙湖1m新真空太阳望远镜终端观测系统侧视图 Fig.1Schematic of the terminals of the 1-m New Vacuum Solar Telescope.

图1为两套终端系统的侧视空间布局图。成像系统与光谱仪在空间上相互垂直，并在装调过程中实现了高精度共焦点和共视场的工作状态。其中 $4 5 ^ { \circ }$ 镜实则是一面分光镜，功能是将来自望远镜的光进行分光后进入两个观测系统。为满足不同科学观测需求，有多个 $4 5 ^ { \circ }$ 镜可以进行替换。例如，常规太阳色球光谱观测时（H-alpha $6 5 6 . 3 \ \mathrm { n m }$ 或CaII854.2nm），选择全波段1-9分分光镜，其功能是允许 $9 0 \%$ 的光子透射进入光谱仪系统，从而产生高信噪比、高分辨率的色球光谱。而剩余 $1 0 \%$ 的光子被反射进入成像系统，足以在成像系统中的宽波段通道中获得高信噪比的图像。在这种模式下，成像系统可被用作光谱仪狭缝位置的监视系统。光球偏振光谱测量的时候，选择使用带通分光 $4 5 ^ { \mathbf { o } }$ 镜，功能是高透射FeI $5 3 2 . 4 \ \mathrm { n m }$ 波段使其进入光谱仪系统进行偏振光测量，并高反射其他诸如H-alpha 656.3nm 和 $\mathrm { T i 0 7 0 5 . 8 ~ n m }$ 波段进入成像系统。该模式下，既可进行光球磁场测量，又可同时获得观测区域（或狭缝位置）的色球以及光球二维图像。

在实际工作中，除了 $4 5 ^ { \mathbf { o } }$ 分光镜的选择以外，整个光路中最为重要是空间扫描机构（Fieldscanner）、偏振分析器（Polarimeter）和仪器偏振定标机构（Instrument Calibration Unit）3部分。空间扫描机构是为了实现二维空间光谱观测的功能，放置在 $4 5 ^ { \circ }$ 分光镜之前，通过自身的运动实现太阳像相对光谱仪狭缝的平稳移动。偏振分析器放置在 $4 5 ^ { \circ }$ 分光镜之后，光谱仪狭缝之前，目的是把4类偏振信号（斯托克斯信号I，Q，U，V）调制成不同频率或不同相位的信号。仪器偏振定标机构是用于对仪器本身的偏振特性进行定标，放置在望远镜 $F _ { 2 }$ 焦点附近。只有在定标时，该机构才需要切入光路，产生各种标准偏振信号，用以完整地探测望远镜的偏振特性。

目前1m太阳望远镜的光谱观测模式分为常规光谱观测模式、偏振光谱观测模式和偏振定标观测模式。其中，要求常规光谱观测模式和偏振光谱观测模式与扫描机构相集成，以进行二维空间扫描观测。为满足这些观测模式的需求，上述这3个机构连同后端的探测器需要有序、快速地交替工作。此外，为便于观测人员操作，同时减少人为错误，上述所有的观测模式最好集成整合为一个综合框架，这对整体观测模式的设计和实现提出了较高的要求。

# 1．关键机构控制的要求分析

1m太阳望远镜光谱仪所有的观测模式主要是通过对空间扫描机构、偏振分析器和偏振定标机构3部分的控制实现。所以首先从科学目标出发理解和明确这些观测模式对各个机构运作的要求。

# 1.1空间扫描模式的要求

空间扫描机构由两组K形镜和一个电控垂直位移台组成。位移台通过垂直升降其中一组K镜实现太阳像相对于狭缝的移动。该位移台由北京卓立公司生产，采用外置光栅尺，闭环分辨率可达 $1 \mu \mathsf { m }$ 重复定位精度为 $2 \mu \ m$ ，复位精度误差为 $4 \%$ 。在前期的研制和装调过程中，已经实现并确保了扫描方向固定（与狭缝垂直）和多次扫描观测目标两点基本扫描要求[4]。

但在实测中发现，更重要的要求却体现在如何完成单次扫描的过程中，即扫描模式。位移台的运动方式可以产生两种扫描模式（如图2）。

（1）连续式扫描模式（图2a）：指电动位移台从初始位置开始以匀速运动方式运动到目标位置。（2）步进式扫描模式（图2b）：步进式扫描是指电动位移台从初始位置开始，行进固定距离后暂停，得到下次行进指令后再行进同等固定距离，直至目标位置。

如果采用连续式扫描模式，位移台不需要与偏振分析器或探测器等设备有通讯联系，只需要选择合适的扫描速度。但仅从终端探测器的采集以方式看，连续式扫描会遗漏部分扫描区域。以普通CCD为例，数据采集时间包括 曝光时间(Exposure)和读出时间 (Readout)两部分，而在读出时间内扫描机构的行进范围没有被采集到，因此最终采集的区域是不连续的。

实际上，除了探测器采集方式这一个原因之外，还有两点问题不能忽略：（1）1m太阳望远镜最终需要实现偏振光谱的空间二维观测，而在偏振光谱的测量过程中，需要在每个空间位置上进行偏振调制观测，此时狭缝位置是绝对不能移动的，因此连续式扫描完全不适用。（2）1m太阳望远镜目前暂时没有稳像机构，在望远镜跟踪系统的精度、风速或视宁度的影响下，焦面太阳像会以大约1Hz 的频率随机晃动5，晃动幅度可超过1"。在这种情况下，连续式扫描的实际扫描视场与预设扫描视场有很大的出入，有效空间采样率很低。

基于上述的分析，1m太阳望远镜扫描机构在科学观测时选择使用步进式扫描模式。即扫描机构等待该位置偏振测量完成或探测器完成采集之后才移动到下一步。

![](images/072bcb1d435d612d4dbba63e362e388f7475cd44fc309215dad132f1a9173910.jpg)  
图2. (a)连续式扫描模式。 (b)步进式扫描模式Fig.2 (a） non-stop mode (b） step-by-step mode

明确扫描模式之后，实测中进一步发现仅采用步进式扫描还是不能够很好地解决由太阳像晃动造成的扫描空间采样问题。以普通光谱扫描观测为例（偏振分析器暂不运动），根据扫描的时间分辨率和空间采样的需求，步进式扫描的步幅通常设为狭缝宽度（如图2的红色窄条宽度，即空间采样宽度）。1m太阳望远镜常用狭缝缝宽 $1 0 0 \mu \mathrm { m }$ ，对应日面0.45”。但由于太阳像的晃动，实际上扫描区域并没有被狭缝等距离地采样，而是产生了图3(a)中的结果：有些地方重复采样，有些地方完全没有被观测到（即黑线所示位置）。

为了解决这个问题，在单步上使用了多帧采集(N-frame/step)的方案。该方案略微降低扫描的时间分辨率。但优点是（1）多帧采集的过程中，太阳像的高频晃动可用来提高狭缝的空间采样率，即提高某一帧里狭缝位于期望的位置的概率。（2）观测人员可以根据图像的晃动幅度、具体科学目标的要求、视宁度的好坏灵活调节 $N$ 的大小。图3(b)、(c)、(d)给出了增加 $N$ 后的效果，可以极大提高扫

![](images/87a0730c6656384508b59aeb39ac359ab222529093214190484b544c7acb4657.jpg)  
图3.步进式扫描模式拼接结果。黑线表示没有被扫描到的区域。从(a)到 (d)，参数N逐步增加。 Fig.3Reconstruction results of the raster images. The black line denotes the area，which is not actually sampled by the slit.

描观测的空间采样率以及空间分辨率[6]。

# 1.2偏振观测机构控制精度的要求

1m太阳望远镜偏振观测机构包括偏振分析器和定标单元，两者具有基本相同的结构，即偏振片、波片和旋转平台。在旋转平台的带动下，偏振片和波片进行不同角度的旋转。两者的旋转平台均使用了由PhysikInstrumente（PI）公司生产的超声波压电转台。

值得一提的是，定标单元位于望远镜真空镜筒内部，与其他终端设备距离甚远，所以采用了串口改网口的策略，即定标单元相关电机的控制器经多级交换机后通过局域网与采集计算机进行网络通信，充分解决了布线问题（如图4）。实验发现由网络通信造成的指令接收及发送延迟平均小于20ms，在实际观测中未发现由于网络延迟造成对仪器性能的影响。偏振分析器在终端平台上，其转台控制器则

![](images/a0fe0ecfa8ed2498b0259c83de607f3eca7e0b9922227a9e5fffa0084e6218f9.jpg)  
图4．光谱偏振观测设备部署图。 Fig.4The deployment diagram of the spectropolarimetric observation.

可以通过RS232数据线与采集计算机直接相连。

偏振分析器工作时，需要偏振片静止，而波片以 $2 2 . 5 ^ { \circ }$ 为固定步幅进行8步式步进旋转，实现对信号的调制观测，要求波片每次转到位后，探测器才能进行数据采集。最初的控制要求的冗余较大，认为 $0 . 0 4 \%$ 的角度定位误差（即角度定位偏差约0.01°）即可满足测量要求，而且在 $0 ^ { \circ _ { - 1 8 0 ^ { \circ } } }$ 和 $1 8 0 ^ { \circ _ { - } }$ $3 6 0 ^ { \circ }$ 之间分别进行8步式调制观测，合成之后希望能提高信噪比。

但是在实测中发现，偏振分析器的角度定位偏差造成明显的测量误差。图5的左半部分（横坐标$\scriptstyle = 4 0$ 之前），波片共转了8步完成 $0 ^ { \circ _ { - 1 8 0 ^ { \circ } } }$ 的旋转(此图中偏振分析器定位精度为 $0 . \ 0 0 2 \pm 0 . \ 0 0 1 \ ^ { \circ } )$ ，这8 个状态体现出来到的强度变化就是调制过程，他们之间的线性组合则用于偏振信号的最终解调。由于偏振信号非常弱（通常是强度信号的百分之一），为了调高信噪比，在每个状态上采集 $N \ ( = 5 )$ 张（如图5中的蓝色圆形标记），除了大气透明度等非人为原因之外，这 $N$ 张的强度不应当出现变化。而在实际光路中，偏振分析器 $0 . 0 1 ^ { \circ }$ 的角度定位偏差会使得 $N$ 张的强度起伏高达 $1 0 . \%$ 以上。当 $N$ 不够大（在特殊要求情况下， $\scriptstyle { \mathcal { N } } = 1$ 或3），平均效果不够强，这会直接影响最终的解调结果，即偏振测量的准确性。因此，观测时需要转台的角度定位精度提高至 $0 . 0 0 2 { \scriptstyle \pm 0 . 0 0 1 ^ { \circ } }$ （即转台能提供的最高定位精度），则可以完全消除上述强度起伏变化，保证偏振测量的准确性。

![](images/f92400b730818ee1cd7788d81022f16d3d95543e3a6fe3efd17159371e67b255.jpg)  
图5．偏振分析器不同角度强度分布。该图偏振分析器定位精度为0.002度。 Fig. 5the intensity distribution at different angles of the polarimeter with the accuracy of 0.002 degree.

其次，在完成 $0 ^ { \circ _ { - 1 8 0 ^ { \circ } } }$ 之间的旋转之后，波片可否在 $1 8 0 ^ { \circ } - 3 6 0 ^ { \circ }$ 之间继续旋转，从而回到0点，这样可否有助于提高偏振测量精度？

如图5，位置1对应波片旋转了 $2 2 . 5 ^ { \circ }$ ，位置1对应波片旋转了 $2 2 . 5 \substack { + 1 8 0 ^ { \circ } }$ 。位置1-8为前 $1 8 0 ^ { \circ }$ 的测量结果， $\mathrm { ~ 1 ~ } ^ { \circ } - 8 ^ { \circ }$ 为后 $1 8 0 ^ { \circ }$ 的测量结果。理想情况下，波片位于位置a与位置 $\mathrm { a + 1 8 0 ^ { o } }$ 时测量强度应当相同，但事实并非如此。通过对比发现，当波片转到某些角度时，例如位置4和 $\cdot \mathbf { \nabla } _ { 4 } ,$ ，他们的强度差异很小。但是对比位置1和 $_ { 1 } ,$ 、位置5和 5'或位置7和7'，他们的强度却存在明显差异。而这种差异最终导致用 $0 ^ { \circ } \mathrm { - } 1 8 0 ^ { \circ }$ 的测量计算出来的响应矩阵和用 $1 8 0 ^ { \circ } - 3 6 0 ^ { \circ }$ 的测量计算响应矩阵存在至少 ${ 1 0 } ^ { - 2 }$ 量级的差异，最大能得到 $1 . 3 \%$ 。为了避免不对称性引入的额外误差，目前 $\ln$ 太阳望远镜偏振分析器波片只在 $0 ^ { - 1 8 0 ^ { \circ } }$ 之间旋转，完成一组8步式调制后，旋转回光学0点，该方式增加了约为500ms 的额外设备运行时间。

# 1.3偏振观测多帧叠加模式

目前1m太阳望远镜是利用单光束进行偏振测量，要求偏振分析器调制的速度越快越好，尽力减小大气湍流引起的干扰。所以通常情况是先进行一组调制（一个角度姿态上拍 $\scriptstyle { \mathcal { N } } = 1$ 帧）观测和计算，后将多组结果进行叠加。即先解调后叠加。而叠加组数的大小取决于时间分辨率与信噪比折中。

但是，通过实测发现这种叠加模式很大程度上降低了时间分辨率。具体来说，每个调制位置上耗费的总时间 $\mathbf { \Sigma } = \mathbf { \Sigma }$ 波片旋转到位所需要的时间 $^ +$ 数据采集时间，而前者相比占据了很大的比例。如果单帧光谱采集时曝光时间为 $8 0 \mathrm { m s }$ ，一个位置拍1帧，一组8步式调制需4s左右完成，然而为了实现偏振信号连续谱的rms 在10-3左右，即 $\delta _ { s } / I _ { c } < 5 . 0 * 1 0 ^ { - 3 }$ ”的科学目标要求，需要叠加约 20组的调制信号，这样总共耗时 $8 0 \mathrm { s }$ 。

针对这种情况，对观测模式进行了相应的调整：在偏振观测中，先在每个调制状态采集足够的帧数，叠加得到高信噪比的调制信号，后进行解调计算，即，先叠加后解调。对比上述例子，如果每步采集 $\scriptstyle { \lambda = 2 0 }$ ，曝光时间不变，则一次偏振观测总共耗时降低为23s。表2给出偏振信号连续谱的 RMS 与$N$ 之间的实测关系。

# 表2.步式调制观测采集帧数、信噪比、总耗时对比

Table 2.The comparison of the temporal resolution and SNR of different demodulation frames number.

<html><body><table><tr><td>曝光时间（ms）</td><td>单一位置的连续采集帧数 (N)</td><td>RMS</td><td>耗时（s）</td></tr><tr><td>80</td><td>20</td><td>3.0x10-3.Ic</td><td>23</td></tr><tr><td>80</td><td>15</td><td>3.5x10-3.Ic</td><td>20</td></tr><tr><td>80</td><td>10</td><td>4.0x10-3.Ic</td><td>14</td></tr><tr><td>80</td><td>5</td><td>5.6x10-3.Ic</td><td>10</td></tr></table></body></html>

由表2可知，如果进行多空间点的（二维空间扫描）的偏振测量，每步耗时23s，以追求 $3 . 0 \mathrm { x } 1 0 ^ { - }$ 3·IC的信噪比，且共扫描110步（步幅 $0 . 5 ^ { \ ' } ,$ /步），想获得约1'的二维磁图的话，总耗时则长达42min。如果将信噪比放低至 $5 . 6 { \mathrm { x } } 1 0 ^ { - 3 . } { \mathrm { I C } }$ ，那么总耗时可以缩短为18min。

# 2．实测效果

在明确并实现了上述各个控制机构的要求后，进行了多次“光谱二维空间扫描观测”和“偏振光谱测量”的两项科学观测。下文将介绍两种科学观测的基本流程并讨论部分在实测过程中发现和解决的问题。

# 2.1光谱二维空间扫描观测

图6为光谱扫描的基本流程。这种观测模式是针对非磁敏的经典色球H-alpha 656.3nm和CaII854.2nm波段的光谱。在具体实现中，该模式作为偏振光谱观测的特殊模式，即偏振分析器状态不变（只起到消光的作用），只需要控制扫描机构和探测器。扫描机构的运动模式为1.1节中所述的步进扫描方式。

在1.1节中，已经提出了用多帧采集 $\left( N / \right)$ step)的方案提高二维扫描结果的空间分辨率，然而实测中发现如果能将准同时的成像系统利用起来，起到狭缝监视的作用，可以对狭缝位置进行实时、精确地定位，有助于进一步提高扫描结果的空间分辨率。

目前成像系统和光谱仪所匹配的探测器在型号、采集模式上完全不同，表3列出了两个系统所匹配的探测器的性能参数。在不增加外部触发设备的前提下，通过调整两套系统的采集速率，并兼顾实测数据量的合理大小达到准同时采集的目的。

首先光谱仪使用的3台 PCO4000型号CCD均连接在同一台采集计算机上，该计算机的带宽及中央处理器核数完全满足3台探测器的同时采集及控制采集软件进程数的要求。单个CCD采集时，采用$2 { \times } 2$ 像素binning模式，单帧光谱数据采集时间约为 $1 0 0 \mathrm { { m s } }$ （ $\mathrm { \overline { { \Omega } } = 6 0 m s }$ 曝光时间 $^ +$ 40ms读出时间），采集速率约10帧/s。单一光谱通道观测时，数据量大约为 $5 0 \mathrm { M / s }$ 。

![](images/40ef1d3fbef6afa056dd1120606767b62d6062f2e553d7ceaabfca5db6946276.jpg)  
图6．非偏振光谱二维空间扫描观测流程 Fig. 6 The activity diagram of raster scan.

进行色球光谱观测时，我们通常利用高分辨系统中的TiO通道进行狭缝位置监视。该通道使用AndorNeo公司生产的CMOS相机，常规高分辨观测时，采用 $1 { \times } 1$ 像素binning模式以及“nonburst-mode”采集模式，可在30秒内完成 200 帧数据的采集，但会造成“前18秒左右集中采集，后12 秒左右集中存储”的时间采样间断的情况。而当在用作狭缝监视观测时，我们首先改成burst-mode采集模式，数据不间断采集，同时采用 $4 { \times } 4$ 像素binning 模式来控制数据量，并做到采集速率15帧/秒。

<html><body><table><tr><td>终端</td><td>波长</td><td>探测器型号</td><td>成像芯片大小(pixels)</td><td>像素大小(umxum)</td><td>QE</td></tr><tr><td>多波段光谱仪</td><td>656.3nm</td><td>PCO4000</td><td>4008x2672</td><td>9x9 * binning</td><td>30%</td></tr></table></body></html>

<html><body><table><tr><td rowspan="2">854.2nm</td><td colspan="3"></td><td>10%</td></tr><tr><td>532.nm</td><td></td><td></td><td>50%</td></tr><tr><td rowspan="2">成像系统(狭缝监视像）</td><td>656.3nm PCO2000</td><td>2048x2048</td><td>9x9</td><td></td></tr><tr><td>705.8nm Andor Neo</td><td>2560x2160</td><td>6.5x6.5</td><td></td></tr></table></body></html>

# 表3.成像系统与光谱仪的匹配探测终端一览表

Table 3.The observation configuration of the High-resolution Imaging System and Multi-band Spectrometer.

通过上述参数的匹配，基本实现了双系统的准同时采集。利用这种观测方法进行了两个活动区的扫描观测，获得较高空间分辨率的二维空间扫描观测（光谱二维拼接结果见图3）。

# 2.2偏振光谱实测

![](images/cc94f94ade50a4467c4cb4a95f326fe3e21e8287cc169136a277e335a3cf7c79.jpg)  
图7．偏振光谱观测流程 (含科学观测与定标观测) Fig. 7the process diagram of the spectropolar imetric observation (including observation and instrumental calibration).

图7为偏振观测的基本流程。从图中可见，偏振实测存在偏振（科学）观测和偏振定标观测两个过程。偏振定标观测可以视为是一种特殊的偏振观测，即定标单元移入光路后进行的一系列偏振观测。定标每次耗时约1min，目的是为了获得望远镜的偏振状态。由于望远镜的偏振状态随时间有明显的变化，需要进行连续式定标观测，或者进行人为的间断式定标（间隔30min）观测。定标观测时，望远镜指向日面中心宁静区，无需启动扫描机构。目前1m太阳望远镜的偏振定标已经取得了很好的效果，偏振信号之间的串扰得到很大程度的矫正（如图8）。

定标结束开启科学观测时，定标单元移出光路，科学观测或进行空间扫描，或进行空间定点观测。考虑图片空间限制，该流程图没有赘述扫描流程，二维空间偏振光谱扫描的基本流程是：扫描机构以步进式进行空间扫描，在每个空间扫描位置上，偏振分析器再进行步进式偏振调制，在每个调制状态上，探测器采集 $N$ 帧，8个调制状态全部采集完毕后，扫描机构移动至下一空间位置，重复上述步骤，最终完成所有预设扫描步数。

![](images/9d4c1ad45634f22ea7931574f2933f810015021af3db4a6f610e1d16ead8150c.jpg)  
图8．偏振光谱定标前后对比。红（黑）色表示定标之前（后）的偏振轮廓。 Fgiure 8. The comparison of cross-talk uncorrected and corrected spectrum.The red profile denotes the spectrum without the correction of the instrumental cross-talk，while the black profile denotes the corrected the spectrum.

# 3．总结与讨论

目前1m太阳望远镜光谱观测的主要观测模式已经设计完成，各项功能进行了优化和整合，并投入常规观测。观测人员既可以通过一个综合观测控制界面完成复杂的二维空间偏振光谱观测，也可以单一执行普通二维空间光谱扫描观测（含定点）、定点偏振光谱测量和偏振定标等观测内容。完成《1m太阳望远镜光谱观测流程》（见附录）。本文所讨论的问题不是突出设计过程中所遇到的工程的问题，而是注重分析观测模式是如何满足最终的科学目标，以及各项电控机构的运动模式、精度、逻辑顺序是如何被提出和确定的。

另外，光谱观测可以与成像观测进行准同步运作。成像系统可以作为狭缝监视系统，可以用以提高光谱扫描的空间分辨率。为最终为实现1m太阳望远镜高空间分辨率、高光谱分辨率的双高观测模式迈出重要的一步。不过需要说明的是，目前1m太阳望远镜不同观测系统或不同观测通道之间并未实现严格的同步采集，这需要考虑硬件的外触发曝光模式。

最后讨论偏振光谱观测中的两个问题。(1)目前1m太阳望远镜偏振调制模式是步进式调制，空间二维观测时分辨率有限。近期已经开展了连续式调制模式的相关实验。连续式模式下，第1次的起始时刻（即波片方位角为 $0 ^ { \circ }$ 时），相机开始曝光,该曝光结束的时刻完成结束曝光并完成采集，同时开始下一次的曝光，而每次曝光应该保证波片旋转的角度一样。因此具体实现中将重点放于如何保证上述两者的同步，如果同步存在一定的误差，那么这个误差又会产生多大的测量误差。这个需要根据实验结果进行判断选择。(2)目前1m太阳望远镜偏振光谱观测模式采用的是单光束观测。单光束偏振分析器的调制解调过程中，由于无法同时获取两个相互垂直的偏振态，导致大气视宁度引起Stokes 参数I对Q，U，V的串扰，从而降低了望远镜的偏振测量精度。下一步希望能积极开展双光束方案，应用偏振光束分离器代替偏振分析器中的偏振片，在同一个CCD的不同位置同时得到两束偏振状态正交的偏振信号，两偏振信号相减消除了I对Q、U、V的串扰，与单光束偏振分析器相比，提高望远镜的偏振测量精度。

# The Design and Implementation of Spectropolarimetric Observation Mode at 1-Meter New Vacuum Solar Telescope

Yuchao CHEN'²,Zhi XU²,Zheng-gang LI²， Shu YUAN²，Guang-qian LIU²， Jun XU²， Zhen-yu JIN²(1.Universityedefse;eatosdefsn)

Abstract: Multi-band spectrometer is one of the terminals used at Fuxian-Lake 1-meter New Vacuum Solar Telescope (NVST). Its major objective is to investigate the vector magnetogram and dynamics of the solar features.To achieve this,two features,imaging observation and spectropolarimetric observation,are realized based on three groups of instruments: field scanner,polarimeter and instrumental calibration unit.For the calibration of the instruments,the instrumental calibration unit (ICU) is installed inside the vacuum telescope tube, near the F2 focus. It consists of two optical elements,a linear polarizer and a retarder,mounted on two independent rotating motorized stages.Both will be moved into the beam,rotating around the optical axis respectively with predefined angles during calibration,and moved out of the beam during observation.The polarimeter and field scanner are mounted in the coude room.The field scanner，for 2D spectrometric observation,is mounted before the beam splittr,which splits the incident beam into two parts,one reflected into the multi-channel high-resolution imaging system and the other passing the spliter and then entering the spectrometers through the slit. The field scanner is made up of two sets of K-shaped mirrors,one of which is mounted ona vertical direction motorized stage. Thescanning observation isrealized by verticallymovingstage in the directionperpendicular to the slit, which willshifts theincident light across the slit. The polarimeter is installed beneath the previous mentioned beam spliter and above the slit. It consists of a retarder,mounted on a rotating motorized stage,and a polarizer,fixed on the base of the same rotating stage, beneath the retarder.During spectropolarimetric observation or calibration,the retarder will be rotated around the optical axis.Since the ICU is installed inside the vacuum tube,a complicated deployment approach is thus used.The power cables and communication cables of the ICU are all connected to the external environment through sealed plug.The RS232 cables are converted to the Ethernet cable and then connected the router which is accessible to the data-acquisition and control PC in coude room.The power cables are connected to a Ethernet-controlled power relay which is also connected to the above the router.The remote PC could control the power switch-of/on action of the ICU and any operations of the motorized stages through Ethernet. The field scanner and polarimeter are connected to the PCby RS232 cable for versatilityand flexibility.This paper focuses on the design and implementation of imaging and spectropolarimetric observation mode at NVST. The scientific requirements of the field scanner,polarimeter and instrumental calibration unit are given in section 1.There are two working approaches of the field scanner available for scanning observation. One is acquiring the spectra continuously as the scanner is moved from the start position to the end position in steady velocity,while the other one is acquiring the n $( \mathrm { n } > = 1 )$ ） frames of the spectra after the scanner stops at the specific position. Considering spectropolarimetric observation,the field scanner uses step-by-step approach as the default mode.Since the step-by-step method is used to demodulate the Stokes parameters,the polarimeter also uses similar approach as the scanner does.The spectra are acquired after the rotation stage stops the specific angle.And to avoid introducing extra polarimetric measurements errors，the accuracy of the rotationstage is within O.OO2 degrees.And multiple successive frames are acquired at each polarimetric status and then averaged in post data-proccess to achieve beter signal-to-noise ratio.This, however,degrades the temporal resolution.Hence,the spatial resolution is sacrificed, $\mathbf { a } 2 \mathbf { x } 2$ binning is adopted for scientific observation.For instrumental calibration,however,the temporal resolution is considered the most important, for the effect of the variation of alt-azimuth of the telescope on cross-talk.A $2 \mathrm { x } 8$ binning is thus adopted in this case.To simplify the observation operations and minimize the manual errors,allthe functions are integrated into the observation control program, which is illustrated in section 2.And the observation result of active regions are also shown in this section.

Keywords: Solar spectrum, spectropolarimetric observation mode.

# 参考文献：

[1] Liu Z,Xu J,GuB Z,et al. New Vacuum Solar Telescope and observations with high resolution[J].Research in Astronomy and Astrophysics,2014,14(6):705-718.   
[2] Wang R，Xu Z, Jin Z Y,et al.The first observation and data reduction of the multi-wavelength spectrometerontheNewVacuumSolarTelescope[J].ResearchinAstronomy and Astrophysics,2013,13(10):1240-1254.   
[3] 艾国祥,胡岳风.太阳磁场望远镜的工作原理[J].天文学报,1986,27(2):173-180. Ai Guoxiang，Hu Yuefeng. On principle of Solar Magnetic Field Telescope[J]. Acta Astronomic Sinca, 1986,27(2):173-180.   
[4] 杨长春,李正刚,陈宇超,等.一米新真空太阳望远镜光谱扫描观测系统设计[J].天文研究与技 术,2016,13(2):257-265. Yang Changchun, Li Zhenggang, Chen Yuchao,et al.Thedesign of a spectrum scanning observation system for the New Vacuum Solar Telescope [J]. Astronomical Research & Technology,2016,13(2):257- 265.   
[5] 陈宇超,柳光乾.NVST的长期跟踪误差分析及改正[J].天文研究与技术,2016,13(02):205-212. Chen Yuchao,Liu Guangqian.The error analysis and correction of NVST's long-term tracking [J]. Astronomical Research & Technology, 2016,13(2): 205-212.   
[6] CaiY F, Xu Z, Chen Y C,et al.Composingmethod for the two-dimensional scanning spectra observed by the New Vacuum Solar Telescope[J]. Research in Astronomy and Astrophysics, 2018,18(4):61-70. 《附录》_

《NVST光谱观测流程》