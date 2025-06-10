# 基于步进电机的位移促动器设计与实测

张宗猛'，王正兰¹，杨德华'，吴常铖'，金振宇²(1.南京航空航天大学自动化学院，江苏南京211106)(2.中国科学院云南天文台，云南昆明650011)

摘要：以环形太阳望远镜为应用背景，研制了一种基于步进电机的位移促动器，并进行了性能实验测试，获得了该位移促动器的性能指标。分析了常见的大行程高精度位移促动器的结构形式，选择位移缩放式作为位移促动器的基本结构。该位移促动器采用步进电机集成行星减速器作为驱动元件，以具有特殊消间隙结构的螺旋传动作为位移缩放机构，为实现高分辨率、高刚度和高精度的位移促动器的设计。开展了位移促动器的性能实验测试，结果表明：该位移促动器轴向位移量程为 $\pm 2 \mathsf { m m }$ ，不同负载下均能实现 $1 \mu \mathrm { m }$ 步长分辨率，位移闭环输出精度优于 $1 \mu \mathrm { m }$ 。研制的位移促动器为环形太阳望远镜的建设提供重要的技术支持，并可为其它精密光学镜面支撑系统的工程应用提供参考。

关键词：太阳望远镜；支撑定位；步进电机；位移促动器中图分类号：TH751 文献标识码：文章编号：

对于云南天文台 $2 m$ 环形太阳望远镜[1-4主镜的轴向位置及倾斜姿态的调整和定位，本文设计了一种基于步进电机的位移促动器。位移促动器作为主镜面的支撑和调节机构，是整个装置的核心部件之一，是一种精密的直线位移输出装置[5-6]。鉴于主镜面的面形需要达到环形太阳望远镜的成像要求，位移促动器需要具有较高的位移输出精度、大负载能力、高刚度以及毫米级有效行程。在环形太阳望远镜的主镜支撑调整技术中，位移促动器不仅需要实现稳定的位移输出，而且还要克服或减少摩擦、间隙和空回等不利的因素。目前，已经建成的太阳望远镜主要都是采用自行研制的位移促动器[7-8]。

针对 2m环形太阳望远镜技术对位移促动器的性能要求，设计一种基于步进电机的位移促动器对主镜镜面进行支撑和调节，并对设计的促动器进行了性能实验检测，开展了行程及线性度测试、位移促动器开环测试、输出分辨率测试、空回测试和位移闭环精度测试，获得了位移促动器的性能指标。

# 1位移促动器设计

# 1.1位移促动器设计指标

对于 $2 m$ 环形太阳望远镜的镜面与传统的全口径镜面的设计指标有所差异，而且环形主镜对定位支撑系统和姿态调整系统的灵活性和精准性要求更高。表1是 $2 m$ 环形太阳望远镜位移促动器的初步设计指标。

表1位移促动器设计指标要求  
Table1 Displacement actuator design index requirements   

<html><body><table><tr><td>技术参数</td><td>技术指标</td></tr><tr><td>最大负荷</td><td>>200N</td></tr><tr><td>位移总行程长度</td><td>±2mm</td></tr><tr><td>位移分辨率要求</td><td>≤1μm</td></tr><tr><td>位移闭环精度要求</td><td>≤1um</td></tr></table></body></html>

位移促动器要对主镜起支撑和调整的作用，因此位移促动器最大负荷应大于200N；为了满足驱动电机在开环状态下的行程需要，位移促动器的位移总行程长度范围 $\pm 2 \mathsf { m m }$ ；还需要满足位移促动器的校正能力，因此需要输出位移分辨率不大于 $1 \mu \mathrm { m }$ ，位移闭环精度要求不大于 $1 \mu \mathrm { m }$ 。

# 1.2位移促动器的结构形式

位移促动器输出位移能同时满足行程大、高精度、高负载等技术要求，常用的大行程高精度微位移促动器的结构形式主要有3种：

（1）位移缩放式。此类微位移促动器的结构形式是在驱动元件后附加位移缩放机构，位移缩放机构主要有减速器、液压减速机构、精密丝杠和柔性铰链等。对于位移缩放机构的优劣，可以从传动比、空回、响应速度、负载能力等几方面衡量。

（2）尺蠖式。尺蠖式微位移促动器是基于“箱位一驱动一箱位”的运动形式，以压电陶瓷、磁致伸缩材料、形状记忆合金等元件进行驱动的微位移促动器。这类驱动元件精度高、响应快，构成的尺蠖式微位移促动器理论上可以获得无限大的有效行程，但是尺蠖式微位移促动器的控制比较复杂，并且成熟的商品很少。

（3）宏/微动叠加式。宏/微动叠加式微位移促动器分为宏动部分和微动部分，宏动部分完成大行程微米级定位，微动部分完成小范围的纳米级定位。这种促动器的缺点是机械结构和控制系统都较为复杂[9]。

相比（2）和（3）两种结构形式的微位移促动器，位移缩放式微位移促动器的结构比较简单，控制也较为方便，通过对驱动元件和位移缩放机构的组合，可以在大行程内输出较高精度的位移。结合表1位移促动器设计指标要求，此设计的微位移促动器采用位移缩放的结构形式。

# 1.3位移促动器设计方案

参见图1（a），为实现高精度控制，微位移校准，采用步进电机集成行星减速器作为核心驱动元件。步进电机和位移促动器外壳均通过法兰对外联接紧固在镜室上。步进电机出轴采用紧定螺钉与转动螺母固连，转动螺母通过轴承安装于位移促动器外壳内，与之配合一直动螺杆，牙距1mm。直动螺杆上段设置有导向机构，这样，就将步进电机输出的旋转运动转换为直动螺杆的直线运动。由于位移促动器内部导杆，步进电机机构不可避免存在回程间隙，空回等现象，结构设计中加入了一根弹性元件预紧弹簧对轴向直线运动杆件预紧，预紧元件可吸收很大的能量，消除或缓解振动，消除间隙。直动螺杆上端为位移输出端，安装了一只拉压力传感器作为位移促动器负载的实时检测元件，并力传感器的上端设置位移输出接口；为实时检测位移促动器的输出位移，又集成了一只位移传感器 LVDT，LVDT的安装座与位移促动器外壳固连；同时，设置了一根横梁，横梁的一端与位移促动器输出接口固连，另一端的下侧与LVDT上端球头触点接触。图1（b）为位移促动器的3D 结构图。图1（c)为位移促动器的实物图。

![](images/f638a128d7b976eb521bb6624c229fca77ccefa54ee584eaa9a5432305a23cef.jpg)  
1.步进电机及减速器，2.法兰，3.轴承，4.转动螺母，5.直动丝杆，6.预紧弹簧，7.预紧弹簧压帽，8.外壳，9.导向机构，10.拉压力传感器，11.位移输出接口，12.横梁，13.LVDT，14.LVDT安装座

Fig.1(a)Designof displacementactuator；(b)3Dstructureof displacementactuator；(c)Physicalofdisplacementactuat

# 2位移促动器的性能测试

对位移促动器进行全面的性能实验测试。性能测试实验过程中，将位移促动器安装在测试平台进行实验。

# 2.1行程及线性度测试

由于驱动电机、导向机构存在间隙、空回、摩擦等非线性因素，对位移促动器开展了输出线性度测试。将位移促动器安装在测试平台如图2所示，进行位移促动器线性度检测。让驱动电机开环状态下按设计目标行程 $( - 2 ^ { \sim } + 2 \mathsf { m m } )$ ）从中间平衡位置开环运行，激光位移传感器（Keyence HO50，测量范围 $0 ^ { \sim } 1 0 \mathsf { m m }$ ，线性度 $\pm 0 . 0 2 \% F S$ ，重复定位精度 $2 5 \mathsf { n m }$ ）记录实际全量程输出位移轨迹，分析线性度，如图3所示。

![](images/1d6efbef9fb0a235691b29af35433b8ee960fc3ac50ebd7477c26fd39877cf96.jpg)  
图1（a）位移促动器设计图；图1（b）位移促动器3D结构图；图1（c）位移促动器的实物图  
图2位移促动器安装图

![](images/4fe9501f238fe076daccf8772eeea5a04781b3d006c2d20bcb3a43230a2f9bcd.jpg)  
图3位移促动器线性度测试曲线  
Fig.2displacementactuatormountingplatform   
Fig.3 Displacementactuator linearitytest curve

测试结果表明位移促动器可以实现正反向全量程范围驱动。线性拟合下残差的极大值$0 . 0 1 5 \mathsf { m m }$ ，在全量程范围内，正反向输出线性度良好。

# 2.2位移促动器开环测试

因为 LVDT的精度直接影响主镜位置检测的精度，所以对于LVDT的数值进行标定至关重要。本设计选用的LVDT线性误差输出为 $0 . 5 \% 5$ 。

实验命令位移促动器从行程 $0 \mathsf { m m }$ 处运动到 $5 \mathsf { m m }$ 处，用LVDT读取采样记录位置变化情况。位移促动器误差曲线如图4所示，可以判断螺纹全长上螺距不均匀。

![](images/1bdde118bc453ffca2037310ceedc770ab5733fa4ad7178309b6e132bef3df10.jpg)  
图4LVDT标定误差曲线。  
Fig.4LVDTcalibrationerrorcurve.

我们采用傅里叶拟合，尝试对位移误差进行校正补偿，拟取误差位移函数解析式如下。经拟合得到相应各系数如表2所列。

$\mathbf { f } ( \mathbf { x } ) { = } \mathbf { a } _ { 0 } \mathbf { S i n } ( 0 . 0 1 \mathbf { x } + \mathbf { b } _ { 0 } ) { + } { \mathbf { c } } _ { 0 } \mathbf { C o s } ( 0 . 0 1 \mathbf { x } + \mathbf { d } _ { 0 } ) { + } \mathbf { a } _ { 1 } \mathbf { S i n } ( 0 . 0 1 2 \mathbf { x } + \mathbf { b } _ { 1 } ) { + } { \mathbf { c } } _ { 1 } \mathbf { C o s } ( 0 . 0 1 2 \mathbf { x } + \mathbf { d } _ { 1 } ) + \mathbf { a } _ { 2 } \mathbf { S i n } ( 0 . 0 1 2 \mathbf { x } + \mathbf { b } _ { 2 } ) , $ $+ \mathbf { a } _ { 2 } \mathrm { S i n } ( 0 . 0 1 5 \mathbf { x } + \mathbf { b } _ { 2 } ) + \mathbf { c } _ { 2 } \mathrm { C o s } ( 0 . 0 1 5 \mathbf { x } + \mathbf { d } _ { 2 } ) + \mathbf { a } _ { 3 } \mathrm { S i n } ( 0 . 0 1 8 \mathbf { x } + \mathbf { b } _ { 3 } ) + \mathbf { c } _ { 3 } \mathrm { C o s } ( 0 . 0 1 8 \mathbf { x } + \mathbf { d } _ { 3 } ) + \mathbf { e } _ { 4 } \mathrm { S i n } ( 0 . 0 1 8 \mathbf { x } + \mathbf { b } _ { 4 } ) + \mathbf { c } _ { 4 } \mathrm { S i n } ( 0 . 0 1 8 \mathbf { x } + \mathbf { b } _ { 4 } )$

表2解析式相应系数  
Table2Analytical coefficients   

<html><body><table><tr><td colspan="2">Tabie2Anaiyticarcoencients</td></tr><tr><td>系数</td><td>数值/mm</td></tr><tr><td>ao</td><td>0.7403</td></tr><tr><td>a1</td><td>-4.5884*10-2</td></tr><tr><td>a2</td><td>0.7302</td></tr><tr><td>a3</td><td>1.5582</td></tr><tr><td>bo</td><td>3.3674*10-3</td></tr><tr><td>b1</td><td>-1.0699</td></tr><tr><td>b2</td><td>3.552*10-4</td></tr><tr><td>b3</td><td>-1.2102</td></tr><tr><td>C0</td><td>0.8817</td></tr><tr><td>C1</td><td>-2.7320</td></tr><tr><td>C2</td><td>0.8863</td></tr><tr><td>C3</td><td>-1.1593</td></tr><tr><td>d</td><td>0.5253</td></tr><tr><td>d</td><td>-0.6222</td></tr><tr><td>d</td><td>0.5187</td></tr><tr><td>d</td><td>0.9482</td></tr><tr><td>e</td><td>-1.2271*10-3</td></tr></table></body></html>

参见图4残差曲线图，残差极限最大值 $0 . 0 1 5 9 \mathrm { m m }$ 、最小值 ${ \cdot 0 . 0 1 6 2 } \mathsf { m m }$ ；残差的均方根为0.0067。造成这样的误差是由于位移促动器开环控制精度不理想，因此要进行闭环控制来校正。

# 2.3输出分辨率测试

分辨率测试的目的是测量位移促动器的校正能力，即最小的可控步长。以下通过对位移促动器施加轴向负载，测试拉伸或压缩情况下位移促动器的输出分辨率。

1）轴向施加压力测试

测试的实验平台如图5所示。位移促动器在轴向对其施加 $2 \mathsf { k g }$ 负载时输出分辨率测试曲线如图6所示。

![](images/82a329aabef09d2d9f1c3a23a13adda50e692b4b0a0bd90887112cca8efb67a0.jpg)  
图5压力测试实验平台

![](images/f53869be5f42729354b2bda637b643a30409b7ae456634187f9238d5f303723a.jpg)  
图6位移输出分辨率轴向压力测试曲线

Fig.5Stress test experimental platform

如图6 可知位移促动器在负载2kg 时候分辨率可以达到 $0 . 6 \mu \mathrm { m }$ 步长，实现分辨率 $1 \mu \mathrm { m }$ 技术要求。

# 2）轴向施加拉力测试

对轴向施加拉力测试时构建的实验平台如图7所示。在1kg负载下对于位移促动器在轴向施加拉力得到输出分辨率测试曲线如图8所示。

![](images/79401963dd043beadfdb306130076cb74f0165a1cab711c84655dc217a1c1eb2.jpg)  
Fig.6Displacement output resolution axial pressure test curve   
图7拉力测试实验平台  
Fig.7Pull test experimental platform

![](images/b302e54e7b2aed6c7c2220d77d47a6dedad5f552d05e8fbe1050a3090d4bfda7.jpg)  
图8位移输出分辨率轴向拉力测试曲线  
Fig.8Displacement output resolution axial pull test curve

由图8可知，位移促动器在施加轴向拉力时，在负载为 $1 \mathsf { k g }$ 是输出位移分辨率可达$0 . 4 \mu \mathrm { m }$ ，可以满足设计指标 $1 \mu \mathrm { m }$ 的要求。

理论上无细分时分辨率为100nm/step，上述采用二细分来处理，由图6和图8可知还可以进行再细分来进行处理。15个单独步进量所走位移行程不一致是由于电机间隙、摩擦等原因造成。

# 2.4空回测试

位移促动器在受重 $2 \mathsf { k g }$ 压力负载下，位于 $0 . 1 \mathrm { m m }$ 这一点上，发出一个步进脉冲。然后，在从最终位置发出与先前步长和步进次数都相同的反向运动，最终得到位置误差。得到的空回测试曲线如图9所示。

![](images/97a90643f7d72306c2163a56230de16317b3ac0b9c7f7eff01fb16073be35f05.jpg)  
图9负载下空回测试曲线  
Fig.9 Empty return test curve under load

由图9可得中间位置上方 $0 . 1 \mathsf { m m }$ 处的位置误差为 $4 . 1 \mu \mathrm { m }$ ，这是由于步进电机中螺纹全长上螺距不均匀和在负载状况下结构弹性变形造成的。这也说明位移促动器开环控制精度不高，需要闭环控制进行校正。

# 2.5位移闭环精度测试

根据2.3小节输出分辨率测试分析可得，位移促动器处于不同轴向拉压力下开环控制分辨率均优于 $0 . 6 \mu \mathrm { m }$ 。基于这个结论，开展了位移促动器闭环测试。即输出目标位移，通过驱动控制系统开环控制电机步进量，LVDT位移传感器实时监测位移步进量反馈回控制系统与目标位移比对，实现位移闭环输出。

根据测试，位移促动器能够实现目标位移闭环输出精度优于 $1 \mu \mathrm { m }$ ，符合技术指标要求。

# 3结论

本文设计了一种基于步进电机的位移促动器，并进行一系列性能测试。测试结果表明，该位移促动器输出位移线性度良好，满足轴向位移 $\pm 2 \mathsf { m m }$ 行程要求，螺纹间隙为 $5 \mu \mathrm { m }$ 左右。开环控制下的分辨率优于 $0 . 6 \mu \mathrm { m }$ ，达到设计指标小于 $1 \mu \mathrm { m }$ 的分辨率要求。位移闭环精度可以实现技术目标优于 $1 \mu \mathrm { m }$ 的要求。但螺纹间距不均匀导致开环控制精度不理想，想要达到高精度位移调整与定位，实验系统仍需采用位移闭环实现校正。测试结果验证了该位移促动器原理和结构简单，安装维护工艺良好，达到设计指标，为 $2 m$ 环形望远镜主镜轴向支撑和调整提供技参考。

# 参考文献：

[1]Zhong Liu,Zhenyu Jin,Shu yuan.The progresses of Chinese Giant Solar Telescope[C]// Proceedings of SPlE.2014,9145:412-417.   
[2]Zhong Liu, Zhenyu Jin.Simulation of Chinese Giant Solar Telescope[C]// Proceedings of SPlE. 2011,8336:54-62.   
[3]杨长春,李正刚,陈宇超,许骏.一米新真空太阳望远镜光谱扫描观测系统设计[J].天文研究 与技术,2016,13(02): 257 -265. Yang Changchun, Li Zhenggang, Chen Yuchao, Xu Jun.The Design of Spectrum Observation System for the New Vacuum Solar Telescope[J]. Astronomical Research & Technology, 2016,13(02): 257-265.   
[4]刘清,姜爱民.光学综合孔径望远镜光程探测方法研究[J].天文研究与技术,2017,14(04): 519-525. Liu Qing, Jiang Aimin. Experimental Research on Piston Detecting Method for Optical Synthetic Aperture Systems[J]. Astronomical Research & Technology,2017,14(04):519-525.   
[5]Zhong Liu,ZhenyuJin, Yan Li, et al. Introduction to the $3 0 \mathsf { m }$ Ring Interferometric Telescope [J]. Proc.SPIE,2006, 6267:62672L.   
[6]王正兰,杨德华,吴常铖,金振宇.基于波纹管的气压式力促动器设计与实测[J].天文研究 与技术,2018,15(03):347-353. Wang Zhenglan, Yang Dehua,Wu Changcheng,Jin Zhenyu.Design and Test of a Bellow-based Pneumatic Force Actuator[J]. Astronomical Research & Technology, 2018,15(03):347-353.   
[7]Z, Liu,J, Xu, BZ,Gu. New vacuum solar telescope and observations with high resolution[J]. Research in Astronomy and Astrophysics,2014,14(6): 705-718.   
[8]杨德华.中国科学院云南天文台2米环形太阳望远镜主镜几何参数及支撑机构计算-总 结报告[R],南京航空航天大学自动化学院,2015.12.7.   
[9]白清顺,王群,张庆春,梁迎春,娄铮.低温微位移促动器的设计与实验[J].天文研究与技 术,2016,13(02):199-204. Bai Qingshun, Wang Qun, Zhang Qingchun, Liang Yingchun, Lou Zheng.The Design and Test of a Cryogenic Micro-Displacement Actuator[J]. Astronomical Research & Technology, 2016,13(02):199-204.

# Development and Test of a Stepper Motor Driven Displacement Actuator

Zhang Zongmeng¹,Wang Zhenglan¹,Yang Dehua¹,Wu Changcheng¹, Jin Zhenyu² (1.College of Automation Engineering，Nanjing Universityof Aeronauticsand Astronautics，Nanjing 211106, China，Email: zhenglanwang@nuaa.edu.cn; 2.Yunnan Observatories， Chinese Academy of Sciences， Kunming 65o011，China)

Abstract: A displacement actuator using a stepper motor was developed for a ring solar telescope,and comprehensive tests were performed to evaluate of its performance.Three design schemes were commonly used in the development of large-stroke and high-precision displacement actuators.And we chose the Displacement Scaling as the basic structure of Displacement Actuator.To achieve high resolution, high stiffness and high precision, Displacement Actuator was driven by Stepper Motors and Planetary Reducers,and eliminated the interval by screwrotation.The experiments of performance test results indicated that the Displacement Actuator's axial displacement range is $\pm 2 \mathsf { m m } , 1 \mu \mathsf { m }$ step resolution can be achieved under diferent workloads,and step resolution can be achieved under different workloads,and the output accuracy of the position closed-loop is better than $1 \mu \mathrm { m }$ . The Displacement Actuator we developed provided important technical support for the ring solar telescope,as well as references for the engineering application of other precision optical mirror support system.

Key Words: Solar telescope; Support positioning; Stepper motor; Displacement actuator