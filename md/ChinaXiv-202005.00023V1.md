# 丽江 $2 . 4 \mathsf { m }$ 望远镜双视场终端的控制与图像采集

穆恒宇1²，王希群1²，马琳¹，柳光乾1(1.中国科学院云南天文台 云南 昆明 650011；2.中国科学院大学 北京100049)

摘要：为充分利用丽江2.4米望远镜有限的卡焦接口，提高观测效率，研制了一个双视场天文观测终端，在2.4米望远镜上实现不同视场和图像比例尺等参数，进行快速测光和高分辨成像等天文观测，以满足天文学家的不同观测需求。针对该终端对滤光片轮精度和大视场光路与小视场光路切换的精度要求，以及对 EMCCD相机图像采集的速度要求，本文采用三层电机闭环控制以及多线程并发执行等技术，实现了该终端中滤光片轮、大视场光路与小视场光路切换的精确控制，以及EMCCD相机图像的快速采集与存储。最后在实验室进行了详细测试，结果表明所设计的控制与图像采集能满足该终端的各项性能指标和功能指标的要求。

关键词： $2 . 4 \mathsf { m }$ 望远镜；双视场终端；位置精度；快速图像采集中图分类号：P111 文献标识码：A

# 0 引言

目前国内只有兴隆2.16米望远镜和丽江2.4米望远镜两台2米级的大型地基光学通用望远镜[]，但天文领域研究目标众多，对不同科学目标的研究需要匹配不同的终端观测设备，而望远镜的终端接口有限，无法同时安装各种终端观测设备[2]。丽江2.4米望远镜共有5个卡焦终端接口可用，目前已有PICCD 相机、云南暗弱天体光谱及成像仪、丽江太阳系外行星探测器、高色散光谱仪和中国丽江积分视场光谱仪五套主要终端设备[3-4]。所以为了满足天文学家对不同科学目标的观测需求，为2.4米望远镜的卡焦研制了一个双视场天文观测终端，其目标是改变观测系统的视场和图像比例尺等参数，实现快速测光和高分辨成像等天文观测，进行快速时变天文现象的研究：比如观测恒星大尺度短时标的光学闪烁和耀斑现象、测定极短周期食双星系统和观测亚角秒时标量级的恒星脉动等[5-6]，以及对研究暗弱伴星及太阳系内行星具有重要作用，通过短时间曝光消除大气湍流对成像质量的影响，保留目标源的高频信心，重建出接近地基望远镜衍射极限的高分辨率图像，能够高精度复原出目标源的精细结构[7-8]。

# 1 双视场终端对控制和图像采集系统的要求

该双视场终端采用双通道共焦光学系统，波段覆盖范围为350nm-950nm，基本原理和实物如图1所示。最前端是滤光片转轮，分别安装U、B、V、R、I五个波段的滤光片和一个补偿板。滤光片轮之后是2.4米望远镜的卡焦焦面，即该终端的物面，之后依次是前固定透镜组、变倍透镜组（包括高倍率镜组和低倍率镜组，高倍率镜组用于小视场成像；低倍率镜组用于大视场成像）、后固定透镜组和 EMCCD。变倍透镜组中的高倍率镜组和低倍率镜组分时复用，即不同时出现在光路中；前透镜组、后透镜组和 EMCCD 是大小视场成像的共用组件。

图1 丽江2.4米双视场终端  
![](images/2cd28adc98611f6656ad76e49d016b7d32b96c592601e786475f8b3a0b1568b6.jpg)  
Fig.1 Dual-FOV terminal on Lijiang 2.4-meter telescope

当终端工作在小视场时，焦比为F32，视场为 $0 . 8 5 ^ { \prime }$ ，EMCCD 像素比例尺为 $0 . 0 3 5 ^ { \prime \prime }$ ，当终端工作在大视场时，焦比为 $F / 3$ ，视场为 $\mathsf { \pmb { \mathsf { g } } ^ { \prime } }$ ，EMCCD 像素比例尺为 $0 . 3 7 ^ { \prime \prime }$ 。在进行不同视场观测时，控制系统要能快速、精确实现高倍率透镜组和低倍率透镜组之间、以及滤光片之间的自动切换，且切换时间小于30秒，根据光学系统成像质量要求，透镜组切换时定位精度好于 $\pm 2 ^ { \prime }$ ，滤光片切换时定位精度好于 $\pm 5 ^ { \prime }$ 。为实现高分辨图像统计重建，要求EMCCD 要能快速采集并存储大量的序列斑点图，另外，快速测光也要求能快速采集大量的图像，图像采集和存储系统要能连续稳定工作，并充分发挥所选 EMCCD 相机的极限图像采

集速度。

# 2 控制与数据采集系统设计

# 2.1系统结构

系统总体结构设计如图2所示，系统主要包括三个部分：一是高倍率透镜组与低倍率透镜组的光路切换控制，二是滤光片轮的旋转控制，三是EMCCD 相机的控制及图像采集与存储，三个模块集成到一台控制计算机上。透镜组切换和滤光片轮旋转采用两个单独的电机，同一台多路驱动器，电机与负载之间的传动比都是1:1的直接驱动，没有传动系统带来的中间误差。两台电机都采用德国 Beckhoff 公司的AM8013 同步伺服电机1，在电机轴上装配有18 位绝对编码器，分辨率好于 $0 . 5 ^ { \prime \prime }$ ，精度好于 $5 ^ { \prime \prime }$ 。电机轴上还配有抱轴制动器，系统旋转到位时可对轴进行锁定。电机驱动控制器采用 Beckhoff 公司配套的AX5203 驱动控制器，可同时控制两台电机，电机、编码器和制动器采用OCT电缆与驱动器相连，驱动器通过EtherCAT 现场总线与计算机通信，电机位置规划、位置和速度控制算法以及逻辑控制在Beckhoff 实时内核TwinCAT3.0[10]平台上实现，然后通过API函数与图像采集软件集成，实现电机状态、位置反馈数据以及人机操控接口等信息交互。

![](images/057e221313ae3c0b8b4cb3c5fd61b8769eccc41e3c647b7a5e685acc3ef129d7.jpg)  
图2 控制与图像采集系统结构原理图  
Fig.2 Schematic diagram of control and image acquisition system

EMCCD采用ANDOR 公司iXonUItra 888 型EMCCD 相机²，靶面为 $1 0 2 4 \times 1 0 2 4$ ，像元大小为 $1 3 \mu \mathrm { ~ m ~ }$ ， $A / _ { \mathsf { D } }$ 为16位，单帧数据为2M，全靶面读出速度为26fps（帧/秒）。EMCCD 的图像采集和相机控制通过USB3.0与控制计算机相连。

该终端系统的大视场和小视场分时复用，但都要求对图像进行快速的采集与存储，观测时还要求对应不同的滤光片。其总体观测控制流程如下：

（1）根据观测需求，选择不同视场，然后切换到对应的透镜组，并通过位置编码器判断系统是否切换到位；（2）根据观测波段，选择滤光片，并通过位置编码器判断滤光片轮是否转动到位；（3）让望远镜指向观测目标，并根据相机实时监测图像，判断是否进行图像采集；（4）进行图像采集与存储，并判断是否需要结束采集;（5）完成一次观测，进行系统复位，并判断是否进行后续观测或关闭系统。

# 2.2滤光片轮与透镜组切换控制

滤光片轮与透镜组切换的控制采用相同的控制结构，设计为三层闭环控制，从内到外分别是电流环、速度环和位置环，分别控制电机的电流、速度和位置，控制结构如图3所示：

![](images/7012d5f13494b540c5bcb0baa9198dac0786e16c2b0d97687353348e97d26a8a.jpg)  
图3 控制系统结构示意图

电流控制算法由AX5203 驱动器执行，速度控制算法和位置控制算法则利用TwinCAT3.0内核执行[1]。控制算法都采用 PID 控制算法，电流环和速度环的控制算法保证电机的平稳运行，位置控制算法则确保系统的定位精度。在TwinCAT3.0开发平台上，各控制模式的实现如图4所示。图4（a）是电机三层闭环控制的具体实现，位置环采用比例控制，即在 PID控制中只启用比例（P）控制，速度环和电流环采用比例和积分控制，即PI控制。图4（b）、图4（c）、图4（d）分别是电流环、速度环和位置环更为具体的结构，包括输入、输出、反馈、积分时间、信号限幅、加速减速的曲线规划等。

![](images/14fcc8d1169f0f8404f3aebe8135f959680b99a5230b501fbf6842aaf1084fbc.jpg)  
Fig.3 Schematic diagram of control system

（a）三层闭环总体控制结构 （b）电流闭环控制结构

(a) Three-layer closed-loop overall control structure

![](images/3438c39055d53eb223f23e30f3e38bd09bba9f22e86eb6b3c5dd35e3d9d920bf.jpg)  
图4 电机控制在TwinCAT3.0平台上的实现

# 2.3EMCCD相机的控制与图像采集

EMCCD 相机的控制功能包括机械快门、电子快门、冷却温度、曝光时间、曝光模式、倍增倍数等功能设定和采集存储速度性能的控制[12]。为达到快速测光和序列斑点图快速采集的目标，使相机工作在连续采集模式，倍增倍数则根据观测目标星的星等、曝光时间要求进行自由调节。为实现相机的连续曝光，并以最快的速度读出和图像连续采集与存储，系统采用多线程技术来实现，图像采集和存储工作在最高的优先级。图像采集流程如图5所示。

![](images/a44859b0a18df410174739302ffb7171d1ce2ddd94ef8f1d8538c8adb0f3d067.jpg)  
Fig.4 Realization of motor control on TwinCAT3.0 platform   
图5 相机控制与图像采集流程  
Fig.5 Flowchart of camera control and image acquisition

为了提高图像采集速度和系统工作的稳定性，在图像采集、图像存储、图像显示线程之间建立100帧的图像缓冲区，几个线程采用互锁机制实现数据的同步与共享，以降低线程之间的阻塞率，提高系统的工作速度和稳定性。

# 2.4软件与人机接口设计

该终端系统的控制与图像采集软件的基本架构是图像采集与电机控制运行在不同的进程，而相机控制、图像采集、存储与显示、切换机构人机接口等又运行在图像控制进程中的不同线程下。软件在Windows7平台上实现，使用Visual Studio 2015的MFC开发，系统切换、滤光轮控制、相机的控制、图像采集与人机操控接口为可视化界面，如图6所示。该界面提供相机启停、快门和采集模式设置、温度设置、存储设置、图像显示及相机状态显示，该界面亦包含镜组切换及滤光轮切换电机的目标位置选择、当前位置显示及制动控制。电机控制在后台的TwinCAT3.0 内核中实现，高倍率镜组与低倍率镜组切换，以及滤光轮控制的人机操控接口与TwinCAT3.0 内核中电机控制程序之间的通信采用TwinCAT3.0提供API函数进行信息交互。

![](images/f29809fb9a05b743262656e507474defe8c41ca5e0eb2ab9f3f5427ddb363cdb.jpg)  
图6 可视化界面  
Fig.6 Visual interface

# 3 系统测试及结果

3.1滤光轮与透镜组电机控制回路参数整定

根据图4和电机平稳运行为目标，对系统进行调试，以阶跃响应曲线为判断依据，整定各回路PID控制参数。具体过程：从电流环开始、调整电流环PID 参数，监控电流输出的阶跃响应和稳态误差是否平稳，平稳之后再调整速度环PID 参数，监控速度输出的阶跃响应和稳态误差是否平稳，平稳之后再调整位置环PID 参数，并监控位置环的阶跃响应和稳态误差。带上实际负载进行系统调试，最终得到各闭环控制回路的PID参数如表1所示。

表1电机各控制回路的PID参数  
Table 1 PID parameters of each motor control loop   

<html><body><table><tr><td>参数</td><td>电流环比例积分(PI)</td><td>速度比例积分(PI)</td><td>位置环比例控制(P)</td></tr></table></body></html>

<html><body><table><tr><td>电机</td><td>比例系数 Kpi(A /V)</td><td>积分时间 Tni(ms)</td><td>比例系数 Kpv(V/rad/s)</td><td>积分时间 Tnv(ms)</td><td>比例系数 Kpp (1000（rad/s))/ rad)</td></tr><tr><td>透镜组切换电机</td><td>27.0</td><td>4.0</td><td>0.012</td><td>2.0</td><td>1.0</td></tr><tr><td>滤光片轮控制电机</td><td>27.0</td><td>4.0</td><td>0.070</td><td>2.0</td><td>2.0</td></tr></table></body></html>

3.2滤光轮切换位置精度测试

由于滤光片轮由电机直接驱动，电机轴上的绝对编码器就实际标识了滤光轮的实际转角位置。但每一个滤光片绝对的精确位置（或对应于编码器的实际位置）需要用光学的方法标定。为了完成控制上定位精度在实验室的测试，滤光片转轮的六个位置对应的编码器暂定位0°、60°、 $\boldsymbol { 1 2 0 } ^ { \circ }$ 、180°、240°、 $3 0 0 ^ { \circ }$ 。然后控制滤光轮电机按照这些点往复运动，分别测试某个点正向（编码器读数增大的方向）复位精度，反向（编码器读数减小的方向）复位精度，并记录编码器反馈值与给定值之间的误差，测量次数为200次，即采集200个误差值进行统计分析。测试结果如图7所示，图7（a）给出了 $\boldsymbol { 1 2 0 } ^ { \circ }$ 点的正向定位精度，图7（b)

![](images/76681ad343903332e3f1b02feedc9858569c5c97553db8b13ec65574c5d03780.jpg)  
图7 滤光片切换电机定位误差  
Fig.7Positioning error of the filter switching motor

给出了 $1 2 0 ^ { \circ }$ 点的反向定位精度，图7（c）、7（d）分别给出了 ${ 6 0 } ^ { \circ }$ 点、 ${ 1 8 0 } ^ { \circ }$ 点的正向定位精度。为确认任意一次控制的定位精度都能满足要求，统计误差P-V值、最大正偏离和最大负偏离。图7（a）和图7（b）为 ${ 1 2 0 } ^ { \circ }$ 点的正反向的P-V 值分别为 $0 . 3 6 ^ { \prime }$ 和 $0 . 4 2 ^ { \prime }$ 、最大正偏离分别是 $0 . 1 8 ^ { \prime }$ 和 $0 . 2 4 ^ { \prime }$ 、最大负偏离分别是 ${ \bf - 0 . 1 8 ^ { \prime } }$ 和 ${ \bf - 0 . 1 8 ^ { \prime } }$ 。表明滤光轮的正反向定位精度都能满足系统 $\pm 5 . 0 ^ { \prime }$ 精度要求，从图7（a）、图7（c）、图7（d）为 ${ 1 2 0 } ^ { \circ }$ 、${ 6 0 } ^ { \circ }$ 、 $1 8 0 ^ { \circ }$ 不同点的P-V值分别为 $0 . 3 6 ^ { \prime }$ 、 $0 . 4 9 ^ { \prime }$ 、 $0 . 6 0 ^ { \prime }$ ,最大正偏离分别是 $0 . 1 8 ^ { \prime }$ 、 $0 . 2 5 ^ { \prime }$ 、$0 . 3 0 ^ { \prime }$ ，最大负偏离分别是 $. 0 . 1 8 ^ { \prime }$ 、 $- 0 . 2 4 ^ { \prime }$ 、 $- 0 . 3 0 ^ { \prime }$ 。表明滤光轮的任意点的定位精度都能满足系统 $\pm 5 . 0 ^ { \prime }$ 精度要求。

# 3.3透镜组切换位置精度测试

与滤光轮切换结构相同，透镜组切换电机也是直接驱动切换装置，两个点也同样需要光学定标，为了控制系统能在实验室进行定位精度测试，同样设定 ${ 1 2 0 } ^ { \circ }$ 和 $3 0 0 ^ { \circ }$ 两个点， $1 2 0 ^ { \circ }$ 为小视场系统， $3 0 0 ^ { \circ }$ 为大视场系统。测量次数为200次，误差分布如图8所示。

![](images/381ce401785adc2071120ed2fd715f5063b571e73d07956bf5b00cc426589b0c.jpg)  
图8 小视场与大视场电机位置定位误差  
Fig.8Motor positioning error in the small and large FOV position

图8（a）和图8（b）的P-V值分别为 $0 . 5 4 ^ { \prime }$ 和 $0 . 6 6 ^ { \prime }$ ，最大正偏离分别是 $0 . 2 4 ^ { \prime }$ 和 $0 . 3 0 ^ { \prime }$ 、最大负偏离分别是 $- 0 . 3 0 ^ { \prime }$ 和 ${ \cdot } 0 . 3 6 ^ { \prime }$ 。表明小视场系统和大视场系统的定位精度都能满足系$\pm 2 . 0 ^ { \prime }$ 的精度要求。

# 3.4图像采集系统测试

图像采集系统的测试包括相机控制的功能测试和图像采集系统速度与稳定性测试。功能的测试相对简单，本文重点进行图像采集系统的性能测试。图像系统的测试就测试图像采集速度，以及是否稳定工作在相机的最大速度。测试结果如图9所示。图9（a）是短时标

![](images/d14b35ac4155638a859c433fca718cc20075d8cbe4d8242cb12d325dec695136.jpg)  
图9 图像采集系统的工作速度测试 Fig.9 Speed test of the image acquisition system

的测试，为相机连续采集5000帧时的速度变化，采用前后相邻两帧之间的时间差来计算采集速度，最后得平均工作速度为25.79fps，速度波动的 P-V为0.25fps。图9（b）是长时标的测试，相机连续采集2小时，采用一分钟所采集到的图像帧数来计算采集速度，最后得到相机平均工作速度是25.78fps，速度波动的P-V是0.30fps。短时标和长时标的测试结果都表明：相机工作速度与理论值26fps 相当，表明图像采集系统完全发挥了该相机的最大采集速度并能稳定工作。

# 4总结

2.4米双视场天文观测终端已经在实验室完成了光机电的联调，并对控制和数据采集系统进行了详细的性能和功能测试。系统的位置编码器与光学之间的偏差还需要进一步用光学的方法标定，但它是一个固定的偏差，并不影响滤光片轮、大小视场之间的位置切换精度的测试结果。所以以上的测试方法是可行的，测试结果也表明该终端的控制和图像采集系统达到了系统设计的指标要求。

# 参考文献

[1]薛艳杰,薛随建,朱明，等.天文望远镜技术发展现状及对我国未来发展的思考[J].中国科学院院刊,2014,29(3):368-375.[2]范玉峰．中型望远镜观测系统集成[D].昆明:中国科学院云南天文台,2014.[3] 陈林勰,王传军,范玉峰，等.丽江2.4米望远镜多波段测光观测控制系统的设计与开发[J].天文研究与技术,2018,15(4):441-447.

[4] FAN Y F, BAI J M, ZHANG JJ, et al. Rapid instrument exchanging system forthe cassegrain focus of the Lijiang $2 . 4 \mathrm { - m }$ Telescope[J]. Research in Astronomyand Astrophysics, 2015,15(6):918-928.  
[5]杨光普,邬文强.CCD 恒星光度测量方法研究进展[J].天文学进展,2012,30(4):467-486.  
[6] 范舟,赵刚,王炜，等.SAGE 巡天介绍I—测光系统和数据处理[J].天文学进展,2018,36(2):101-121.  
[7]张西亮,刘忠,钱声帮.恒星系统中暗弱伴星的高分辨率成像探测[J].天文研究与技术-国家天文台台刊,2008,5(4):349-354.  
[8]杨晓晗．成像系统的数值模拟及幸运成像技术研究[D].昆明：昆明理工大学,2016.  
[9]马琳，金振宇，李正刚，等．一种多功能天文观测装置：201920136859.3[P].2019-09-24【2019-12-24】.  
[10]郑士富,彭铭 $\mathrm { . V C + + }$ 与TwinCAT的混合编程研究[J].仪器仪表用户,2008,15(3):109-110.  
[11]黎妞.基于EtherCAT的伺服运动控制系统研究[D].武汉：武汉科技大学,2012.  
[12]李达伦.基于USB3.0 的EMCCD 相机高速数据传输系统的研究[D].昆明：昆明理工大学，2014.

# Control and Image Acquisition of the Dual-FOV Terminal on Lijiang 2.4-meter Telescope

Mu Hengyu1,²，Wang Xiqun1,2，Ma Lin1，Liu Guangqian1 (1.Yunnan Observations，Chinese academy of sciences，Kunming 65oo11，China

2.University of Chinese academy of sciences，1ooO49，China)

Abstract : To make full use of the limited interface of Lijiang 2.4-meter telescope's cassegrain focus and improve the efficiency of observation,a dua-field astronomical observation terminal is developed. This terminal will provide different FOV and image scales,and carry out astronomical observation such as rapid photometry and high-resolution imaging，so as to meet the different observational needs of astronomers.According to the requirements of the terminal for the precision of the filter wheel, the switch between the large and the smallfield optical path,and the speed requirements for the image acquisition of EMCCD camera, this paper uses three-layer closed-loop motor control and multi-thread technologies to realize the precise control of the filter wheel, the FOV switching,as well as the rapid image acquisition and saving of the EMCCD camera. Finally,a detailed test is carried out in the laboratory. According to the results,the control and image acquisition system we designed can meet the requirements of the terminal's performance indicators and functional indicators.

Key words : 2.4-meter telescope; dual-FOV terminal; positional accuracy; rapid image acquisition