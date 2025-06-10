# 基于 ${ \mathsf { K D } } ^ { * } { \mathsf { P } }$ 偏振调制和同程异构的图像同步采集的时序控制

王希群1,2，陈宇超1,2，柳光乾1

(1.中国科学院云南天文台 云南 昆明 650011；2.中国科学院大学 北京 100049)

摘要：为了满足1m新真空太阳望远镜高分辨率磁像仪对图像采集的需求，研制了基于${ \mathsf { K D } } ^ { * } { \mathsf { P } }$ 偏振调制和同程异构的图像同步采集时序控制系统。通过对 ${ \mathsf { K D } } ^ { * } { \mathsf { P } }$ 的偏振调制特性和SCMOS 相机的Rolling 曝光及外触发工作特性进行详细分析，设计了同步控制时序，并给出了系统的工作流程。在深入研究工作时序各参数之间的相互制约关系，并对各时间参数随机波动量进行了大量的实测和统计分析之后，得到了系统运行的时序条件。最后在几种工作状态下对时序系统进行了实测，从而证明了所设计的时序控制系统满足磁像仪对 ${ \mathsf { K D } } ^ { * } { \mathsf { P } }$ 偏振调制和同程异构的序列斑点图同步采集的要求。

关键词： $K _ { D } * _ { P }$ 偏振调制；同程异构；图像同步采集；时序控制中图分类号：P111 文献标识码：A 文章编号：1672-7673(2018)

基于 $K \mathsf { D } ^ { * } \mathsf { P }$ 电光调制原理的偏振分析器在太阳磁像仪中观测磁场已有较长的历史，早在20 世纪80 年代，文[1-4]中的磁场望远镜就采用了 $K _ { D } * _ { P }$ 作为磁场分析器和视向速度场分析器。随着图像传感器、电子和计算机技术的发展，以及天文学家对太阳磁场观测数据的质量和时空分辨率的要求提高，需要控制 $K _ { D } * _ { P }$ 的调制状态（即方波调制高压）与图像采集相机每帧图像曝光时间之间的严格同步，否则一帧图像将出现不同的偏振状态。文[5]在怀柔太阳观测基地35cm 真空折射太阳磁场望远镜上对数据采集系统进行升级，实现了 $K _ { D } * _ { P }$ 工作高压与CCD 曝光的同步。

随着我国1m 新真空太阳望远镜（New Vacuum Solar Telescope，NVST）对太阳实现了多波段的高分辨率成像观测，项目组提出了基于同光程异构图像统计重建（简称同程异构）技术的高分辨率磁像仪，目前正在研制中。

基本原理是在经典磁像仪的基础上增加一个信噪比高的白光通道，以同步于磁场通道采集大量短曝光（约10ms）斑点图来实施高分辨率统计重建[6-7]。磁场测量通道中偏振分析器可以是基于 $K \mathsf { D } ^ { * } \mathsf { P }$ 的电光调制，也可以是基于旋转波片式的机械调制，基于 $K _ { D } * _ { P }$ 调制速度快，成为了1m 太阳望远镜磁像仪的首选[8-9]。因此，除两个通道的斑点图采集必须严格同步之外，数据采集系统还需解决两个高速的短曝光斑点图采集与 $K _ { D } * _ { P }$ 调制的高压方波之间

的同步问题。

为了快速调制的 $K \mathsf { D } ^ { * } \mathsf { P }$ 偏振分析器能成功应用在基于同程异构技术的高分辨率磁像仪中，本文就其数据采集系统开展了深入的研究工作，并设计了基于 $K _ { D } * _ { P }$ 偏振调制和同程异构的高速高精度图像同步采集的时序控制系统。

# 1 1m太阳望远镜高分辨率磁像仪及 ${ \mathsf { K D } } ^ { * } { \mathsf { P } }$ 偏振调制原理

1.11m太阳望远镜高分辨率磁像仪的基本结构

1m 太阳望远镜高分辨率磁像仪工作的中心波长为 532.419 nm，其中滤光器带宽为0.01nm，因此窄带（0.01nm）偏振图像所含光子数极少（仅为正常光球图像的1/500），信噪比非常低，难以应用1m太阳望远镜在多波段成像系统中发展的观测方法和高分辨率图像统计重建技术获得亚角秒级的高分辨率太阳偏振图像。为了解决这一难题，提出了基于同光程异构图像统计重建技术的高分辨率磁像仪，这一技术简称同程异构技术。基本结构如图1,在经典磁场测量中增加一个信噪比高的白光通道，通过严格的同步采集两个通道的大量短曝光斑点图，从有足够信噪比的太阳光球连续谱图像中解算出重建窄带偏振图像所需的统计信息，并用这些信息实现对窄带偏振图像的统计重建[10]。

![](images/ebac6d8da8ae1b3b562503d43f2da160971ef779fb57191325a7ae3d11b5ef2b.jpg)  
图11m太阳望远镜高分辨率磁像仪基本结构  
Fig.1Basic structure of NVST high resolution magnetograph

# 1.2 $K _ { D } * _ { P }$ 偏振调制工作原理

太阳磁场的测量首先要在某条稳定的磁敏谱线上获得窄带偏振图像，然后才能通过一系列的定标和磁场反演得到太阳磁图，偏振分析器正是这一核心部件。1m 太阳望远镜高分辨率磁像仪的偏振分析器参考怀柔太阳磁场观测偏振分析器，采用基于 $K \mathsf { D } ^ { * } \mathsf { P }$ 的电光调制原理的偏振分析器，结构如图2，优点是调制速度快，缺点是 $K _ { D } * _ { P }$ 需要上千伏的工作高压。

![](images/ee4adf3df4fc44c5708070c7e5a8389a2d75be2f95dd77d3f876e5aec947f626.jpg)  
图2基于 $K D ^ { * } P$ 的偏振分析器 Fig.2Polarmetric based on $K D ^ { * } P$

图2偏振分析器对斯托克斯参数 $( 1 , \ 0 , \ U , \ V )$ 调制的基本公式为

$$
\begin{array} { l } { { \mathrm { S } = 0 . 5 I + 0 . 5 \theta \big ( \cos \delta \cos ^ { 2 } 2 \theta - \sin \delta \sin 2 \theta \big ) } } \\ { { + 0 . 5 U \bigg ( \displaystyle \frac { 1 } { 4 } \cos \delta \sin ^ { 2 } 4 \theta + \sin \delta \cos ^ { 2 } 2 \theta \bigg ) - 0 . 5 V \sin ^ { 2 } 2 \theta \cos \delta } } \end{array}
$$

其中， $\theta$ 为 $\scriptscriptstyle { 1 / 4 }$ 波片轴的方位角； $K \mathsf { D } ^ { * } \mathsf { P }$ 轴的方位角为 $4 5 ^ { \circ }$ ；偏振片 $p$ 的轴方位角为 $0 ^ { \circ }$ ；  
$\boldsymbol { \delta }$ 为 $K _ { D } * _ { P }$ 的相位延迟量。偏振分析器测量斯托克斯参数 $( 1 , \ 0 , \ U , \ V )$ 的调制方法如下。

（1）测量 $v$ 时，将14波片移出，在 ${ \mathsf { K D } } ^ { * } { \mathsf { P } }$ 上加交变的方波电压，使得正半周期电压时， $K _ { D } * _ { P }$ 的相位延迟量为 $\pi / 2$ ，负半周期电压时， $K _ { D } * _ { P }$ 的相位延迟量为- $\pi / 2$ ，相机接收到的信号分别为 $\mathsf { S } _ { + } = 0 . 5 | - 0 . 5 \mathsf { V }$ 和 $\mathsf { S } _ { = } = 0 . 5 | + 0 . 5 \mathsf { V }$ ，则 $V = S \_ S _ { 1 }$ 。

（2）测量 $\upsilon$ 时，将14波片移入，轴方位角 $\theta$ 旋转到 $0 ^ { \circ }$ ，在 $K _ { D } * _ { P }$ 上加交变的方波电压，使得正半周期电压时， $K D ^ { * } P$ 的相位延迟量为 $\pi / 2$ ，负半周期电压时， $K _ { D } * _ { P }$ 的相位延迟量为- $\pi / 2$ ，相机接收到的信号分别为 $\mathsf { S } _ { + } = 0 . 5 \mathsf { I } + 0 . 5 \mathsf { U }$ 和 $\mathsf { S } _ { - } { = } 0 . 5 | { - } 0 . 5 \mathsf { U }$ ，则 $u = s - s .$ 。

（3）测量 $\boldsymbol { \mathscr { Q } }$ 时，将14波片移入，轴方位角 $\theta$ 旋转到 $4 5 ^ { \circ }$ ，在 $K _ { D } * _ { P }$ 上加交变的方波电压，使得正半周期电压时， $K _ { D } * _ { P }$ 的相位延迟量为 $\pi / 2$ ，负半周期电压时， $K D ^ { * } P$ 的相位延迟量为-π/2，相机接收到的信号分别为 $S _ { + } = 0 . 5 1 \mathrm { - } 0 . 5 \Omega$ 。 $\mathsf { S } _ { - } = 0 . 5 | + 0 . 5 \mathsf { Q }$ ，则 $a = S \cdot S +$ 。

# 1.31m太阳望远镜高分辨率磁像仪对数据采集的要求

1m 太阳望远镜高分辨率磁像仪对数据采集的总体要求是在尽量短的时间内，磁场通道和白光通道需要同步采集大量的短曝光斑点图， $K _ { D } * _ { P }$ 调制状态变化对图像采集的影响最小，且能辨识对应的图像帧（无效帧)。详细的时间参数要求如表1。表中时间分辨率指的是完成一次斯托克斯参数 $( 1 , \ 0 , \ U , \ V )$ 测量的时间，是对偏振分析器调制速度和图像采集速度的要求，单帧曝光时间是指两个相机每帧短曝光斑点图的曝光时间，每秒采集帧数是斑点图的采集帧率（采集速度)，异构图同步采集精度是指白光通道和磁场通道斑点图曝光时间的同步精度。

表1NVST磁像仪对数据采集系统的基本要求  
Basic requirements of NVST magnetograph for data acquisition system   

<html><body><table><tr><td>名称</td><td>要求</td></tr><tr><td>时间分辨率</td><td>小于60s</td></tr><tr><td>单帧曝光时间</td><td>约10ms</td></tr><tr><td>每秒采集帧数</td><td>大于30帧</td></tr><tr><td>异构图同步采集精度</td><td>好于1ms</td></tr></table></body></html>

从 $K _ { D } * _ { P }$ 偏振调制工作原理看出，对斯托克斯参数中的 $\boldsymbol { \mathscr { Q } }$ ， $\upsilon$ ， $v$ 进行测量时， $K _ { D } * _ { P }$ 的相位延迟量需要在 $\pi / 2$ 和- $\pi / 2$ 之间交替变化，即 $K _ { D } * _ { P }$ 两端需要加1000V左右的方波电压，$K _ { D } * _ { P }$ 在 $\pi / 2$ 和- $\pi / 2$ 每个稳定状态时，两通道的相机需要采集到足够（400帧）的斑点图来进行高分辨率统计重建，而且 $K D ^ { * } P$ 在 $\pi / 2$ 和- $\pi / 2$ 之间跳变时，由于状态不稳定，必须丢弃对应帧的斑点图，这就要求两个同步工作的相机应与 $K _ { D } * _ { P }$ 的调制状态保持严格的同步，即与其工作的高压方波保持同步。

因此，要满足1m 太阳望远镜高分辨率磁像仪对数据采集的要求，需要严格控制两台相机之间，以及相机与 $K _ { D } * _ { P }$ 调制状态之间的同步。

# 2时序控制系统总体设计

# 2.1时序控制系统的总体设计及其工作流程

为了满足同程异构对斑点图采集速度的要求，1m太阳望远镜高分辨率磁像仪选用科学级的 sCMOS 相机，在 Rolling 曝光模式下，最高速度可以达到100 帧/s。sCMOS 提供多种触发工作模式，为了实现1m太阳望远镜高分辨率磁像仪中两台 sCMOS 相机的每帧图像都能精确同步曝光，并且能连续、高速采集短曝光斑点图，sCMOS 工作在 Rolling 模式，采用外触发启动，需要采集图像总帧数和每帧图像的曝光时间由采集程序事先设定。

由于 $K _ { D } * _ { P }$ 工作电压是1000V左右的高压方波，为了实现该高压与sCMOS 的同步工作，在设计 $K _ { D } * _ { P }$ 的高压电源时，同时从 $K _ { D } * _ { P }$ 输出级产生与高压方波频率和相位相同，而电压只有几伏的方波用于反馈控制。

根据系统要求、sCMOS相机特性和工作模式，以及 $K \mathsf { D } ^ { * } \mathsf { P }$ 高压电源结构，NVST高分辨率磁像仪数据采集的时序控制设计如图3（a)。sCMOS 相机的图像采集与存储、曝光时间、工作模式以及采集总帧数通过图像采集计算机进行控制。中控计算机负责采集两个相机以及$K _ { D } * _ { P }$ 的工作状态，然后向两个相机发送同步外触发信号。sCMOS相机、 $K D ^ { * } P$ 电源及IO控制卡之间电气特性不同，加入了相应的接口和驱动电路。

整个系统的工作流程如图3（b)，中控机设置好 $K _ { D } * _ { P }$ 的工作参数（频率和电压）以及图像采集计算机设置好相机的工作参数后，然后中控机通过IO口读取 $K _ { D } * _ { P }$ 的调制状态和相机工作状态（就绪、曝光、停止)，当两个相机都在就绪状态时，开始序列斑点图的采集。

![](images/5f3947fd6c0209991a1f18ea3110bd5f4404bcb2810eabbc9890f5e4d9219853.jpg)  
图3(a)1m 太阳望远镜高分辨率磁像仪数据采集时序控制系统;(b)系统工作流程 Fig.3(a) Data acquisition time sequence control system of NVST high resolution magnetograph; (b) System workflow.

# 2.2系统工作时序及参数

$K _ { D } * _ { P }$ 状态切换时对应的斑点图需要根据 $K _ { D } * _ { P }$ 频率、sCMOS 曝光时间和整个相机的工作模式之间的相互制约关系确定，这是整个系统的时序设计问题。理想情况下，系统的工作时序如图4,图中， $T _ { 1 + , } T _ { 2 + \cdots } \tau _ { \mathsf { N } + }$ 表示 $K _ { D } * _ { P }$ 偏振调制为 $\pi / 2$ 时的状态, $T _ { \mathrm { 1 \cdot , } } \ : T _ { \mathrm { 2 \cdots \cdots } } \ : T _ { \mathrm { N \cdot } }$ 表示 $K _ { D } * _ { P }$ 偏振调制为- $\pi / 2$ 时的状态， $\tau _ { \textsf { N } }$ 表示 $K _ { D } * _ { P }$ 总的工作周期， $N$ 表示 $K _ { D } * _ { P }$ 总的工作周期数。 $\boldsymbol { n }$ 表示一个 $K _ { D } * _ { P }$ 调制状态（ $\tau _ { + }$ 或 $\tau .$ ）下序列斑点图的帧数， $\boldsymbol { n }$ 不宜过大，10 帧以下为好，这是因为 $\mathfrak { n }$ 过大，一是导致获得的偏振信号S.和 ${ \sf S } _ { + }$ 之间时间过长带来测量误差，二是 $K D ^ { * } P$ 晶体特性不允许长时间工作在直流状态。2Nn表示一次工作采集到的斑点图总帧数。由于 $K D ^ { * } P$ 调制状态周期性变化，第n、2n、3n.....2Nn 帧对应于 $K _ { D } * _ { P }$ 调制状态切换时采集到的图像，是无效帧，数据处理时要将这些帧剔除。

![](images/5bbe68b3902398b6ec94cdcdd80467570b21bac260e52b2f535319e8ea9da5b3.jpg)  
图4数据采集系统理想工作时序  
Fig.4Ideal working sequence of data acquisition system

但是，两个sCMOS相机的曝光模式、曝光时间长度、 $K _ { Ḋ } \mathsf { D } ^ { * } \mathsf { P } Ḍ$ 电压频率、高低电平的占空比、高压调制方波与低压反馈方波的一致性，以及外触发信号的稳定性、系统中各延时环节的时间稳定性、一次采集总图像帧数2Nn 都影响系统的正常工作，致使废弃帧不规则出现，导致无法辨识无效帧。因此，实际工作时序要综合考虑以上因素，相比理想工作的时序要复杂得多，如图5。图中， $t _ { 1 }$ 表示 $K _ { Ḋ } \mathsf { D } ^ { * } \mathsf { P } Ḍ$ 工作高压与计算机采集到的同步反馈低压时刻之间的时间延迟，这是由 $K _ { D } * _ { P }$ 高压电源硬件系统以及软件的不实时造成的。 $t _ { 2 }$ 为计算机采集 ${ \mathsf { D } } { \mathsf { K } } ^ { * } { \mathsf { P } }$ 同步反馈低压时刻到相机触发信号发出时刻的时间延迟。 $t _ { 3 }$ 为触发信号发出到相机第一帧开始曝光时刻的时间延迟。 $t _ { 1 }$ 、t2、 $t _ { 3 }$ 的稳定性影响每次序列斑点图开始采集时的稳定性，即每次采集时，是否是第 $\mathfrak { n }$ 帧对应 $K \mathsf { D } ^ { * } \mathsf { P }$ 第1次（ $T _ { 1 + }$ 到 ${ { T } _ { 1 - } }$ ）调制状态的变化。相机的曝光时间te、 $K _ { D } * _ { P }$ 的频率和占空比（即 $\tau _ { + }$ 和 $\tau .$ ）以及总曝光帧数2Nn将决定后面图像的稳定性，也就是第 2n、.n...2Nn .是否为无效帧。

![](images/426e54478a86b35447c642656f2af547f75b3d4b2dae67fc7cfcb69b224f7cff.jpg)  
Fig.5Actual working sequence of data acquisition system

当sCMOS工作在Rolling模式时，曝光是从相机中心向两边逐行进行，如图6。

![](images/7d64515dc557c93322be55c62c123961d04955f1780cf1e9b37e901deec7e9cb.jpg)  
图5数据采集系统实际工作时序  
图6sCMOS 相机的外触发Rolling曝光模式  
Fig.6External triggerand Rolling exposure mode of the sCMOS camera

对于该数据采集系统采用的滨松C11440-22CU 型sCMOS 相机，像元 $2 K \times 2 K$ ，Rolling 曝  
光模式下，后一行相对前一行延迟约 $1 0 . 0 ~ \mu \ s$ ，对于所选用的 $2 K \times 2 K$ 的相机，最后曝光的一  
行相对最开始曝光的一行延迟了约 $1 0 . 0 \mathrm { m s }$ ，如果曝光时间 $t _ { \mathrm { e } }$ 小于 $1 0 . 0 \mathrm { m s }$ ，则 $K D ^ { * } P$ 调制状  
态变化时影响多帧图像，即无效帧为多帧，如果曝光时间 $t _ { \mathrm { e } }$ 大于 $1 0 . 0 ~ \mathsf { m s }$ ，则一帧图像中所  
有行都在曝光的时间为 $t _ { \mathrm { g } } { = } t _ { \mathrm { e } } { - } 1 0 . 0 \mathsf { m s }$ (参加图6)，理想情况下，一次采集的序列斑点图中，  
应把 $K _ { D } * _ { P }$ 所有调制状态变化对应对在 ${ n . 2 n . 3 n . . . . . 2 N n }$ 的 $t _ { \mathrm { g } }$ 时间内，即只影响一帧图像，  
因此 $t _ { \mathrm { g } }$ 越大越好，也就是斑点图的曝光时间 $t _ { \mathrm { e } }$ 越大越好，但高分辨率图像统计重建中，斑  
点图曝光时间又最好小于或接近大气冻结时间（典型值为 $1 0 \mathsf { m s }$ )，因此，控制时序到达最完  
美的条件是在满足总斑点图帧数2Nn（800帧）的条件下 $t _ { \mathrm { e } }$ 大于并越接近 $1 0 . 0 \mathrm { m s }$ 越好。由于两个通道 sCMOS 相机型号相同，工作模式相同，曝光能实现严格同步。让两台相

154 机采用Roling工作模式，单次外触发连续曝光800 帧，利用示波器观察相机800 帧输出波  
155 形，由于800 帧同步采集输出信号较为密集，故仅仅贴出800 帧中开始曝光与结束曝光的情  
156 况，实测结果如图7。因此，重点问题是两个相机与 $K \mathsf { D } ^ { * } \mathsf { P }$ 的偏振分析器的同步工作。

![](images/229845eeaf374b0511e5710d95e59b5ae411cfbd7bcd3acf552484d382ea7280.jpg)  
图7800 帧连续曝光两相机同步情况；(a)开始曝光；(b)结束曝光  
Fig.780o frames continuous exposure of two cameras synchronously;(a)exposure start;(b)exposure end

设 $\scriptstyle t _ { \mathrm { d m } }$ 表示第 $\boldsymbol { n }$ 、2n、.n.....2Nn 帧中 $t _ { \mathrm { g } }$ 时段的中间时刻与 $K \mathsf { D } ^ { * } \mathsf { P }$ 高压切换时刻的时间偏差（可正可负），单位为毫秒（ms）时，整个系统的时间精度需要满足关系式：

$$
\begin{array} { r } { \nabla { t _ { 1 } } + \nabla { t _ { 2 } } + \nabla { t _ { 3 } } + \nabla { \left( { { T } _ { \mathrm { + } } } - { { T } _ { \mathrm { - } } } \right) } + \frac { { { t } _ { \scriptscriptstyle { R D * P \pm } } } } { 2 } + N \big | { { T } _ { N } } - 2 \times n \times { { t } _ { \mathrm { - } } } \big | = { { t } _ { \scriptscriptstyle { a d } } } } \end{array}
$$

$$
t _ { _ { I m d } } \leq \frac { t _ { g } } { 2 } = \frac { t _ { e } - 1 0 . 0 0 0 } { 2 }
$$

式中， $\nabla t _ { 1 } \setminus \nabla t _ { 2 } \setminus \nabla t _ { 3 }$ 分别表示图5中 $\mathbf { t } _ { 1 }$ 、t2、t的波动量， $\nabla \left( T _ { + } \ - \ T _ { - } \right)$ 表示 $K D ^ { * } P$ 高压方波两个状态持续时间差的波动量（方波占空比不是 $50 \%$ )，引入该项是要求 $T _ { + }$ 到 $\tau$ 和T.到 $T _ { + }$ 状态之间的不同转换时都对应无效帧， $t _ { \mathsf { K D } ^ { \ast } \mathsf { P } \pm }$ 表示 $K _ { D } * _ { P }$ 两个高压状态的切换时间（即高压方波的上升或下降时间)， $\left| N ( T _ { _ { N } } \mathrm { ~ - ~ } 2 * \mathrm { ~ } _ { n } * \mathrm { ~ } _ { t _ { e } } ) \right|$ 主要由两部分组成，（1) $K _ { D } * _ { P }$ 高压信号周期 $T _ { \mathsf { N } }$ 的最小分辨率 $d { \sf T } _ { \sf N }$ ，（2）相机的最小分辨率 $d \mathfrak { t } _ { \mathrm { e } }$ ，由于 $d { \sf T } _ { \sf N }$ 和 $d \mathfrak { t } _ { \mathrm { e } }$ 的存在，如果$\lvert T _ { x } \mathrm { ~ - ~ } 2 \ast \ n \ast \ t _ { e } \rvert$ 不为零，则会随 $N$ 累积。因此，时序控制需要根据 $K _ { D } * _ { P }$ 高压电源控制器 $d { \sf T } _ { \sf N }$ 和相机控制器的 $d \mathfrak { t } _ { \mathrm { e } }$ 使得 $\left| T _ { \scriptscriptstyle N } \mathrm { ~ - ~ } 2 * n * t _ { e } \right| )$ 为 $0$ ，并满足条件（2）、（3）、（4）式，除此之外，在斑点图信噪比满足要求的情况下，要使得曝光时间 $\mathfrak { t } _ { \mathrm { e } }$ 尽量大于并接近于 $1 0 . 0 \mathrm { m s }$ 。

# 3系统时间参数实测与分析

时序条件关系式（2）中，前5项 $\nabla t _ { 1 }$ 、 $\nabla t _ { 2 }$ 、 $\nabla t _ { 3 }$ 、 $\nabla \left( T _ { + } \ - \ T _ { - } \right)$ 、 t KD\*P±是系统固有 $\frac { t _ { _ { K D * P \pm } } } { 2 }$

的时间特性，需要对系统进行实测。 ${ \mathsf { d T } } _ { \mathsf { N } }$ 是 $K _ { D } * _ { P }$ 高压电源控制器决定的，其值是160us，dte是相机控制器决定，其值是10us。确定 $\mathfrak { t } _ { \mathrm { e } }$ 最理想值，首先要实测系统中各个时间环节的波动量，最坏情况下，以P-V值（最大值与最小值之差）表示相关的波动。

3.1系统延时参数波动的实测

系统整体延时主要是从 ${ \mathsf { D } } { \mathsf { K } } ^ { * } { \mathsf { P } }$ 的调制高压状态变化时刻到相机第一帧曝光时刻的延迟，包括t1、t2、t3，这些参数的波动将影响到所有的无效帧（t、2t、3t....t)。

通过系统实验，设定 $K _ { D } * _ { P }$ 高压工作电源和相机曝光时间，采用示波器并配合高压探头对t1、t2、t3进行测量，经过多次测量的结果如图8，其中横坐标为测量次数。最大值、最小值、平均值、P-V各参数的统计如表2。

![](images/fdb4f33b41c4acbc560963dcf880994a694bf2fce0dd4816d81cf79d4a317e06.jpg)  
图8系统整体延时参数稳定性  
Fig.8Stability of the overall delay parameter of the system

# 表2系统整体延时参数统计值

Table 2 Statistics of total delay parameters of the system   

<html><body><table><tr><td>时间参数</td><td>最大值/us</td><td>最小值/us</td><td>平均值/us</td><td>P-V值/us</td></tr><tr><td>t1</td><td>364</td><td>280</td><td>309.49</td><td>84</td></tr><tr><td>t2</td><td>52.2</td><td>4</td><td>13.9684</td><td>48.2</td></tr><tr><td>t3</td><td>2065.2</td><td>2032.8</td><td>2046.844</td><td>32.4</td></tr></table></body></html>

通过测量，t1对应的时间波动的 P-V 值 $\nabla t _ { 1 }$ 为 84us，t2对应的时间波动的P-V 值 $\nabla t _ { 2 }$ 为48.2us，t3 对应的时间波动的 P-V 值 $\nabla t _ { 3 }$ 为 $3 2 . 4 \mathsf { u s }$ ，t1、t2、t3 时间延迟的 P-V 值总和$\nabla t _ { 1 } + \nabla t _ { 2 } + \nabla t _ { 3 }$ 为 $1 6 4 . 6 \mu s$ 。

3.2 $K D ^ { * } P$ 时间特性参数实测

$K _ { D } * _ { P }$ 时间参数中，影响系统无效帧（n、2n、3n...2Nn）的时间因素主要是占空比，即 $T _ { + }$ 与 $\tau { } _ { \cdot }$ 的时间差，以及 $\tau _ { + }$ 与 $\tau { _ { - } }$ 状态之间的切换时间 𝑡KD\*P±，即高压方波的上升或下降时间。设定 $K \mathsf { D } ^ { * } \mathsf { P }$ 高压工作电压和工作频率在实际工作状态附近，通过多次测量，测量结果见

![](images/768b840cc7892181700b404703a1aade3de67f6daa3720a0184fcfb32d7f4ed6.jpg)  
图9，得到 $T _ { + }$ 与T.之差的P-V值 $\nabla \left( T _ { + } \ - \ T _ { - } \right)$ 为 $1 5 0 \mu s$ ， $\mathsf { t } _ { \mathsf { K D } ^ { * } \mathsf { P } \pm }$ 最大值为 $3 1 5 . 0 _ { \mu \mathrm { s } }$ 。  
图9 $( \mathsf { a } ) \mathsf { K D } ^ { * } \mathsf { P }$ 占空比情况； $( mathsf { b } ) \mathsf { K D } ^ { * } \mathsf { P }$ 高压上升下降时间  
Fig.9 (a)Duty cycle of $K D ^ { * } \mathsf { P } ; ( \mathsf { b } )$ Rise and fall time of ${ \mathsf { D } } { \mathsf { K } } ^ { * } { \mathsf { P } }$ high voltage

# 4不同参数模式下的时序控制实验

根据系统延迟和 $K _ { D } * _ { P }$ 高压电源时间参数的实测值，统一公式量纲为毫秒（ms)，代入时序关系（2）、（3）、（4）式得

$$
t _ { e } \ \ge 1 0 . \ 0 0 0 \ + \ 2 \biggl ( \nabla t _ { 1 } + \nabla t _ { 2 } + \nabla t _ { 3 } + \nabla \bigl ( T _ { + } - T _ { - } \bigr ) + \frac { t _ { K / \beta \approx P \pm } } { 2 } \biggr ) = 1 0 . 9 4 4 2 ,
$$

$$
N \big | T _ { \scriptscriptstyle N } - 2 \times n \times t _ { \scriptscriptstyle e } \big | = 0
$$

$$
T _ { \scriptscriptstyle \cal N } = m _ { \scriptscriptstyle \cal T } \cdot d T _ { \scriptscriptstyle \cal N } t _ { \scriptscriptstyle e } = m _ { \scriptscriptstyle \cal t } \cdot d t _ { e } \mathrm { ~  ~ \lambda ~ n ~ } , { \sf m } _ { \scriptscriptstyle \sf \Gamma } , { \sf m } _ { \scriptscriptstyle \mathrm { t } } \Psi _ { \scriptscriptstyle \mathrm { L } } \mathbb { E } \frac { \ast \mathrm { i } \xi _ { \scriptscriptstyle \cal N } } { \kappa _ { \scriptscriptstyle \mathrm { E } } + \xi _ { \scriptscriptstyle \cal N } }
$$

根据图3建立的时序控制系统，在满足时序条件（5）、（6)、（7）式的情况下，开展了不同 $n , t _ { \mathrm { e } }$ 的相关实验。由于示波器显示800 帧相机输出会略显拥挤，以及开始触发后各个周期匹配效果都能够达到磁像仪对数据采集系统的要求，故以上多种工作模式实验结果仅仅贴出实验数据的首个 ${ \mathrm { K D } } * { \mathrm { P } }$ 周期与末个 $\mathrm { K D * P }$ 周期，用来表示该种工作模式能够很好的实现800 帧数据采集。

(1)当 $\scriptstyle n = 1 0$ 时，满足（5）、（6）、（7)式的 $t _ { \mathrm { e } }$ 的最小取值为 $1 0 . 9 6 \mathsf { m s }$ ， $T _ { \mathsf { N } }$ 取值为：219.2ms。  
实测的时序如图10。

![](images/6c7c5ef3fd71cdbcbc2ee756e347b7e69f1b7ccd6d053248823fa8478ab572fe.jpg)  
图10 $\scriptstyle n = 1 0 , t _ { \mathrm { e } } = 1 0 . 9 6 \mathsf { m s }$ 时同步采集时序，(a)首个 $K D ^ { * } P$ 周期;(b)末个 $k \mathsf { D } ^ { * } \mathsf { P }$ 周期

(b) the last cycle of $K D ^ { * } P$

(2）当 $n = 5$ 时，满足（5）、（6）、（7）式的 $t _ { \mathrm { e } }$ 的最小取值为 $1 0 . 9 6 \mathrm { m s }$ ， $T _ { \mathsf { N } }$ 取值为：109.6ms。  
实测的时序如图11。

![](images/032e3e3c883ccd5786bd93eeeb8ecc54925f39f55a78f6907c946751b76d8dbe.jpg)  
Fig.10When/ $\scriptstyle 1 = 1 0 , t _ { \mathrm { e } } = 1 0 . 9 6 \mathsf { m }$ s,the timing sequence of synchronization acquisition (a) the first cycle of $K D ^ { * } P$   
图11 $\scriptstyle n = 5 , t _ { \mathrm { e } } = 1 0 . 9 6 \mathsf { m s }$ 时同步采集时序， (a)首个 $K D ^ { * } P$ 周期;(b)末个 $K D ^ { * } P$ 周期

(b) the last cycle of $K D ^ { * } P$

(3）当 $n = 5$ 时， $t _ { e }$ 非最小，取值为 $1 5 \mathsf { m s }$ ， $T _ { N }$ 取值为： $1 5 0 \mathrm { m s }$ 。

实测的时序如图12。

![](images/a001ddd6283ec9bece776d0fa839f0261382816075aaa91e60f273404052de36.jpg)  
Fig.11 When $\scriptstyle n = 5 , { t _ { \mathrm { e } } } = 1 0 . 9 6$ ms,the timing sequence of synchronization acquisition (a) the first cycle of $K D ^ { * } P$   
图 $1 2 n = 5$ $\scriptstyle t _ { \mathrm { e } } = 1 5 m s$ 时同步采集时序，(a)首个 $K D ^ { * } P$ 周期;(b)末个 $K D ^ { * } P$ 周期

Fig.12 When $\scriptstyle n = 5 , t _ { \mathrm { e } } = 1 5$ ms,the timing sequence of synchronization acquisition (a) the first cycle of ${ \mathsf { K D } } ^ { * } { \mathsf { P } } .$

(b) the last cycle of $K D ^ { * } P$

在不同的实验条件下，对工作时序进行了实测，得到如下结论：

（1）同程异构中的磁场通道与同步通道两个相机能同步工作，序列斑点图的曝光时间

严格对齐。

（2）两个相机序列斑点图的所有无效帧 $( n , ~ 2 n , ~ 3 n ^ { \bullet \cdots \bullet \cdot } 2 N n )$ 能严格对应 ${ \mathrm { K D } } { * } { \mathrm { P } }$ 的状态变化，而且每个状态变化只有一帧无效帧，即 $\mathrm { K D * P }$ 高压切换的过程均对应无效帧的高电平时刻。

（3）时序系统正常工作时，斑点图的最小曝光时间为 $1 0 . 9 6 \mathrm { m s }$ ，满足高分辨率图像统计重建对曝光时间的要求。

# 5总结

根据1m太阳望远镜高分辨率磁像仪对数据采集系统的需求，根据 $\mathrm { K D * P }$ 偏振调制特性、同程异构以及sCMOS 相机 Rolling 曝光和外触发工作的特点，设计了满足数据采集的同步时序控制系统。通过系统各时间参数的详细测试与分析，得到了满足时序系统同步工作的条件参数设置条件。最后实测了几种模式下系统的工作时序，表明所设计的时序控制系统能满足NVST高分辨率磁像仪对数据采集系统的需求。

# 参考文献：

[1］艾国祥.太阳磁场望远镜[J].云南天文台台刊,1989(S1)：5-7. Ai Guoxiang.Solar Magnetic Field Telescope[J]. Publications of Yunnan Observatory,1989 (S1) :5-7.   
[2]艾国祥,胡岳风.太阳磁场望远镜的工作原理[J].天文学报,1986,27(2):173-180. Ai Guoxiang.Hu Yuefeng. On principle of Solar Magnetic Field Telescope [J]. Acta Astronomica Sinica,1986,27(2) :173-180.   
[3]艾国祥,胡岳风.太阳磁场望远镜中 ${ \mathsf { K D } } ^ { * } { \mathsf { P } }$ 电光调制器[J].天体物理学报,1981, 1(4) :273-284. Ai Guoxiang. Hu Yuefeng. The ${ \mathsf { K D } } { \ast } { \mathsf { P } }$ modulator in the Solar Magnetic Field Telescope [J].Chinese Journal of Astronomy and Astrophysics,1981，1(4) :273-284   
[4] Bai XY, Deng YY,Teng F,et al. Improved magnetogram calibration of Solar Magnetic Field Telescope and its comparison with the Helioseismic and Magnetic Imager[J]. Monthly Notices of the Royal Astronomical Society, 2014, 445(1):49-55.   
[5]林佳本,沈洋斌，朱晓明,等.怀柔太阳观测基地全日面磁场自动化观测系统[J].天文研 究与技术—国家天文台台刊，2013,10(4):392-396. Lin Jiaben,Shen Yangbin, Zhu Xiaoming， et al. Design of the automatic observation system for full-disk solar magnetograms in the HSOS [J]. Astronomical Research & Techno logy—Publications of National Astronomical Observatories of China,2013,10(4) :392-396.   
[6]向永源，刘忠，金振宇,等．高分辨率太阳图像重建方法[J]．天文学进展，2016， 34(1) :94-110. Xiang Yongyuan， Liu Zhong， Jin Zhenyu，et al.High resolution solar image reconstruction [J].Progress in Astronomy，2016，34(1): 94-110.   
[7] Van Noort M J, Rouppe van der Voort L H M. Stokes imaging polarimetry using image restoration at the Swedish 1-m Solar Telescope[J]. Astronomy & Astrophysics, 2008, 489(1):429-440.   
[8]林佳本，胡柯良，邓元勇.太阳磁场望远镜 KDP 高压脉冲电源设计[J].现代电子技 术,2013,36(2) :154-157+164. Lin Jiaben, Hu Keliang, Deng Yuanyong. Design of high-voltage pulse power supply for KD\*P in solar magnetic field telescope [J].Modern Electronics Technique,2013,36(2) :154-157+164.   
[9]陈春荣,王学荣,库黎明.KDP 晶体电光调制器件的研制及性能测试[J].长春理工大学学 报,2003,26(4) :40-42. Chen Chunrong, Wang Xuerong, Ku Liming. The manufacture and property test of KDP crystal electro-optics modulationo apparatus [J].Journal of Changchun University of Science and Technology,2003,26(4) :40-42.   
[10]李玉艳,陈宇超,杨磊，等.NVST多通道成像观测系统的数据同步采集[J].天文研究与技 术,2015,12(3) :323-330. Li Yuyan,Chen Yuchao, Yang Lei， et al.A synchronized data acquisition system in the multi-channel observation system on the NVST of the YNAO[J]. Astronomical Research&Technology,2015,12(3) :323-330.

# Timing sequence control based on KD\*P polarization modulation and the image synchronization acquisition for different structure of optical path

Wang Xiqun1,2，Chen Yuchao1,2，Liu Guangqian1 (1.Yunnan Observations，Chinese academy of sciences，Kunming 65oo11，China

2.University of Chinese academy of sciences，1ooO49，China)

Abstract: In order to meet the requirements of image acquisition of the high resolution magnetograph installed at $1 \mathrm { ~ m ~ }$ new vacuum solar telescope, the timing sequence control system based on $\mathrm { K D ^ { * } P }$ polarization modulation and image synchronization acquisition for different structure of optical path is developed and depicted in this paper. The scientific requirements of the The polarimetric characteristics of ${ \mathrm { K D } } ^ { * } { \mathrm { P } } ,$ the Rolling exposure mode of sCMOS camera and its external trigger on the control system is given in section 1. And based on this，the synchronization-control timing sequence was designed and the workflows of the system with different parameters are given in section 2. Then each parameters of the timing sequence are analysed and their fluctuation are carefully measured and analysed statistically. The constraints on the timing sequence of the system are then defined. The implementation and the test result of different workflows are given in the final part and the results shows the design of the system could meet the given requirements on the accuracy of the synchronised acquisition.

Key words : $\mathrm { K D ^ { * } P }$ polarization modulation; different structure of optical path； image synchronization acquisition; Timing sequence control