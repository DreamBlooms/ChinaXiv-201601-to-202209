引用格式:Chen Si,Liu Hao,Wu Ji,etal.Simulation of Microwave Interferometric Radiometer System based onSimulink[J].Remote Sensing Technologyand Application,2015,30(4)：757-766.[陈思,刘浩,吴季,等.基于 Simu-link 的干涉式微波辐射计系统仿真研究[J].遥感技术与应用,2015,30(4)：757-766.]  
doi:10.11873/j.issn.1004-0323.2015.4.0757

# 基于Simulink的干涉式微波辐射计系统仿真研究

陈思2,刘浩¹，吴季1,牛立杰1（1.中国科学院微波遥感技术重点实验室，中国科学院空间科学与应用研究中心,北京100190；2.中国科学院大学，北京100049)

摘要：介绍了通过Matlab/Simulink建立干涉式微波辐射计系统仿真模型的方法。针对干涉式微波辐射计的基本构成单元——二元干涉仪,搭建了仿真模型,通过对辐射计随机噪声测量过程的模拟，实现了单通道全功率测量仿真及双通道干涉测量仿真，在时域范围内实现了对系统测量精度、灵敏度指标的定量化分析。

键词：干涉式微波辐射计；可见度函数;仿真模型;Simulink中图分类号：TP732.1 文献标志码：A 文章编号：1004-0323（2015)04-0757-1(

# 引言

对全球海洋盐度的探测工作具有重大的意义，有助于人们进一步深入了解气候变化及水循环等领域的问题。但目前关于海洋盐度的探测方式还有很多局限性，现有的研究成果难以为水汽循环的研究提供有力的数据支撑。为了解决这一问题，在最佳探测海洋盐度的L波段，很多国家都开展了相关的课题研究，主要包括欧空局的探测土壤湿度与海水盐度的卫星(SMOS，SoilMoistureandOceanSalinity)1、美国测量海水盐度的宝瓶座计划（Aquari-us)[2]。针对这种背景，中国科学院空间科学与应用研究中心提出了主被动联合探测式盐度计项目计划，在系统总体方案上综合考虑SMOS和Aquarius的特点，利用高灵敏度、高稳定度的L波段一维干涉式综合孔径辐射计，实现对全球海洋盐度分布的高精度观测，同时利用共用反射面天线的L波段数字波束形成散射计，实现海面粗糙度信息的获取，有助于改进海洋盐度测量的精度[3」

本文的研究正是以主被动联合探测式盐度计项目为依托，针对其中的L波段高稳定度干涉式微波辐射计系统的基本构成单元——二元干涉仪，进行了Matlab/Simulink仿真工作，搭建出了仿真模型，利用仿真系统与实际硬件的一一对应关系，在仿真平台上实现对系统性能及相关指标的分析。

# 2 干涉式微波辐射计测量原理

# 2.1微波辐射计相关原理

根据辐射量子理论可以得知[4]，处于热力学平衡的物体所发射出的功率是其物理温度的线性函数。微波遥感的工作机理是利用高灵敏度的接收机来获得目标物质的辐射噪声功率，然后通过合理的时间积分累加，最终将辐射功率与接收机自身的噪声加以区分[5]。就辐射计而言，辐射噪声功率的发射源就是目标物质本身，辐射计被动地接收天线收集起来的辐射能量功率，可以通过功率最终定义出物体的辐射测量亮温度。

辐射测量的灵敏度定义为辐射计输出端可以检测到的天线辐射亮温的最小变化。假设整个接收机系统的噪声亮温值为 $T _ { \mathrm { s y s } }$ ，接收机的带宽为$B$ ，系统中积分器的积分时间为 $\tau$ ，则辐射测量灵敏度表示为：

$$
\Delta T = \frac { T _ { \mathrm { s y s } } } { \sqrt { B \tau } }
$$

从测量角度来说， $\Delta T$ 是与 $T _ { \mathrm { s y s } }$ 测量值有关的标准差的大小。

# 2.2 二元干涉仪相关原理

传统的微波辐射计在应用上有一些限制，一方面，高空间分辨率的要求受限于天线物理口径的大小，另一方面，天线波束在每个分辨单元越来越短的驻留时间也会降低辐射亮温值的分辨率[6]。基于这些问题，提出了干涉式微波成像技术。来源于射电天文领域的干涉式成像技术，基本思想就是在空间频率域实现空间域的测量效果[8，将天线接收到的信号进行复相关运算，输出目标亮温分布的空间频率采样点，称为可见度函数（VF，VisibilityFunc-tion)。由于微波辐射计的最终目的是得到物质的辐射亮温度，通过对可见度函数进行反傅立叶变换，可以获得辐射亮温分布图像。本文所涉及到的仿真模型是针对上述过程中的第一步，即通过Matlab/Simulink搭建一个二元干涉仪仿真系统，实现可见度函数测量过程的仿真。

干涉式微波辐射计系统比较复杂，目前针对此系统的仿真都是基于傅立叶关系的空间频率域和空间域的系统仿真[9]。然而，辐射计测量的噪声具有随机性和不相干特性，之前的仿真在系统的性能分析上受到一定程度的限制，比如对于量化过程无法仿真，也不能进行辐射计测量精度、灵敏度等指标的分析[10]。基于这个问题,考虑在时域上仿真干涉式微波辐射计系统，通过在Matlab/Simulink平台上对二元干涉仪进行时域仿真，实现系统功能。二元干涉仪的原理框图如图1所示。

![](images/9a54f5c94898f1dfdb4271d66dc5c6e6d12a6615ff08fce21ebf8c00e0d81216.jpg)  
图1二元干涉仪原理框图  
Fig.1Functional block diagram of binary interferometer

基于二元干涉仪的基本原理，结合主被动联合探测盐度计项目中的L波段高稳定度辐射计接收机系统，利用Matlab/Simulink搭建出干涉式微波辐射计仿真系统模型，实现可见度函数测量过程的仿真。

# 3仿真模型

Matlab/Simulink是由Mathworks公司推出的一种科学计算仿真软件，作为一种可视化仿真工具，目前已被广泛应用于控制理论和数字信号处理的复杂仿真和设计[1],前人经过探讨实验，已经将其应用于仿真模型的搭建工作中，并得到相应结果[10]。下面重点围绕本文的研究方向，详细说明仿真模型的搭建过程。

# 3.1L波段高稳定度辐射计硬件系统简介

主被动联合探测式盐度计中的辐射计系统采用一维综合孔径技术，设定为8单元，各单元接收机均为双极化[12]。高稳定度辐射计接收机组件由以下几个部分构成：双通道接收机前置、前端、中频、公共噪声源及功分单元、公共本振及功分单元、数字相关器模块，系统整体框图如图2所示。

![](images/dfaf9cbe3a312009213b6dcb01e59258468383115d212623c6e4dcf79f311c17.jpg)  
图2L波段高稳定度辐射计接收系统框图 Fig. 2 Block diagram of theL band radiometer systemwithhighstability

# 3.2 系统仿真模型概述

接下来重点说明利用Matlab/Simulink所搭建的仿真模型。仿真的模型系统由6部分模块构成，分别是前置单元、前端单元、中频单元、公共噪声源单元、公共本振单元以及相关器单元，系统的总仿真框图如图3所示。

天线信号源用Simulink的白噪声信号模块来模拟，参数的设置通过噪声功率值来表征相应的亮温。输入的天线信号经过前置、前端、中频、相关等模块单元的处理，完成二元干涉仪的基本功能，对两个单元天线信号的输出进行复相关运算，最终输出信号的空间频率采样点，即可见度函数VF 的采样值。接下来对系统中的4个重点单元模块进行描述。

# 3.2.1前置单元

前置单元主要包括一分二功分器、2OdB耦合器，仿真框图如图4所示。

![](images/0c2efb2ff56d1c94f79cc3556121632cd0159dd4343d542e0eb4b611f9195f1a.jpg)  
图3两单元辐射计系统仿真框图

![](images/8777c2234071e9b79c9e87b924fd062e98a5c9c8d68dffeadb949f5b9da9a4f5.jpg)  
Fig.3Simulation diagram of the radiometer system   
图4前置单元仿真框图

在前置单元中，主要实现天线信号与公共噪声源的混合，并完成噪声源注入的时序控制。仿真在控制公共噪声源的周期性注入时，涉及到脉冲时序的设定，搭建了一个迪克开关模块来控制时序，具体来说就是通过离散脉冲序列来实现时序循环，迪克开关的仿真框图如图5所示。

![](images/f3b315329059c779bd2ad2eb3a8875a9d300e07bf9b6adde20482bbe7437e4f7.jpg)  
Fig.4Simulation diagram of front unit   
图5迪克开关仿真框图  
Fig.5Simulation diagram of Dicke switch

# 3.2.2 前端单元

前端单元中，重点完成不同噪声源的切换性注入，通过迪克开关控制时序，将天线信号、公共噪声源、匹配负载以及内部噪声源接入接收机，同时考虑到接收机本身始终存在噪声，所以添加一个噪声源模块来模拟。仿真中涉及两个通道的接收机，搭建结构相同，其中一个通道的仿真框图如图6所示。

# 3.2.3 中频单元

中频单元包括带通滤波器、放大器、混频器以及平方律检波器等，主要功能是实现前端输出噪声信号的正交混频，得到I/Q两路信号，其中一个通道所对应的仿真框图如图7所示。

前端单元输出的信号进入中频单元，首先通过带通滤波器的处理实现带外抑制，经过放大后，与本地振荡信号进行混频运算，得到 $\mathrm { I } / \mathrm { Q }$ 两路信号，再经过中频滤波、放大，输出到后续相关器模块。另一方面，对主路输出的 $\mathrm { I } / \mathrm { Q }$ 两路信号进行 $1 5 ~ \mathrm { d B }$ 耦合，再经过平方律检波以及低通滤波器的处理，输出全功率信号。

# 3.2.4数字相关器单元

数字相关器单元主要包括采样、量化以及复相关值计算模块，仿真框图如图8所示。

图8中的VF模块用于实现数字复相关值的计算，仿真框图如图9所示。

在计算复相关值的过程中，涉及到信号相乘、累加积分等数据处理，输出信号的数字互相关值，对数

![](images/f3e6b48e70515193b6c368feb70b7b05727cc776a5874f1bdf90f76458d219e8.jpg)  
Fig. 6 Simulation diagram of front-end unit

![](images/c98029efeb05b87d9e566106ef422e723e5c99d9b93a405ea441a77ba7819973.jpg)  
图6前端单元仿真框图  
图7中频单元仿真框图

![](images/ff99e05fe483c62dc7fe79902cfd8b0cef54596ad7c63f9f2b2aa98bf0a4a08e.jpg)  
Fig.7Simulation diagram of IF unit   
图8数字相关器单元仿真框图  
Fig.8Simulation diagram of digital correlator

E ×  
IH1相乘器1 积分器1求平均器1求和 求均值1  
2 × 自 I  
QH1相乘器2积分器2求平均器2 显示输出 示波器  
③  
IV1 三相乘器3 求差值 求均值2积分器3求平均器3首 1  
④  
QV1 相乘器4积分器4求平均器4

据进行后续校正处理，获得模拟相关系数，之后再通过可见度函数归一化，最终获得空间频率采样点。

# 4仿真参数设定

# 4.1 系统参数压缩

在真实的辐射计硬件系统中，接收机工作在L波段，而要在计算机上运行MHz的时钟频率几乎是不可能的[10]，所以在仿真过程中，要将硬件系统中的信号频率、系统带宽等参数进行一定比例的压缩。在确保系统的采样及性能指标满足要求的前提下，优化后的系统参数情况如表1所示。

Table1Compression parameters of the receiver   

<html><body><table><tr><td>接收机参数</td><td>实际硬件系统</td><td>仿真模型系统</td></tr><tr><td>中心频率</td><td>1.413 GHz</td><td>10 kHz</td></tr><tr><td>3dB带宽</td><td>27 MHz</td><td>2 kHz</td></tr><tr><td>本振频率</td><td>1.35 GHz</td><td>8kHz</td></tr><tr><td>中频带宽</td><td>50～77 MHz</td><td>1～3kHz</td></tr></table></body></html>

压缩模型的原始频段范围会不可避免地降低系统的灵敏度指标，针对系统参数压缩后相较于原始系统的指标变化，进行了等效性对比分析。设定系统亮温值为 $2 8 0 ~ \mathrm { K }$ ，对应的系统主要参数指标如表2所示。

表1接收机参数压缩对比  
表2仿真系统与原系统指标对比表  
Table 2 Comparison of the system parameters   

<html><body><table><tr><td>参数</td><td>系统 亮温/K</td><td>带宽</td><td>单点积分 时间/s</td><td>观测 周期/s</td><td>灵敏度 /K</td></tr><tr><td>原系统</td><td></td><td>27 MHz</td><td>0.2</td><td>2</td><td>0.100</td></tr><tr><td>仿真系统</td><td>280</td><td>2 kHz</td><td>0.5</td><td>100</td><td>0.626</td></tr></table></body></html>

从2表中可以看出，仿真中相应参数的压缩确实对系统的指标带来了影响。其中辐射计的灵敏度指标取决于系统的噪声温度、信号带宽以及系统的积分时间。当系统的噪声温度一定时，辐射计的灵敏度与积分时间和系统带宽成反比，所以为了提高灵敏度指标，必须增加信号的带宽值或提高积分时间。但是由于仿真中计算机性能的限制，对原系统的带宽进行了压缩，不可避免地恶化了系统的灵敏度指标。为了弥补压缩带宽带来的指标影响，在仿真中考虑拉长系统的积分时间来优化灵敏度参数，通过在一个较长的观测周期内对单点积分时间进行统计平均，达到拉长积分时间的目的，有效地改善了系统的灵敏度指标。另外，为了使仿真模型能够产生可靠的噪声亮温估计，必须要提高校准和观察时间来保障长期稳定的目标场景温度，或者进行多次重复试验来获得平均值，以保证准确度。

# 4.2提高仿真效率

Simulink的仿真大多为非实时仿真，对于一些仿真实时性要求较高的场合，往往存在着仿真运行速度较慢的缺陷，达不到预期的理想效果[13]。为了解决这一矛盾，提出了利用RTW（Real-TimeWorkshop)实时代码生成工具的方法，将Simulink模型向其他语言模型转换，以满足不同实时仿真速度的要求。由于 $\mathrm { C / C + + }$ 语言的执行效率较高，具有稳定和运行速度较快的特点，能够满足实时仿真要求，因此选择将模型转换成 $\mathrm { C / C } + +$ 语言模型，提高仿真运行效率。

经验证，通过实时模型代码得到的结果与直接运行Simulink模型的结果几乎是相同的，表明了用RTW生成代码的正确性[14]。在代码环境下运行仿真模型，将原始的仿真速度提升了几个数量级，达到了提高仿真运行效率的目的。

# 5 仿真结果

# 5.1单通道全功率测量仿真

对于单通道的全功率测量，重点分析中频单元的耦合输出信号。在中频单元，信号混频后分成I/Q两路，通过平方律检波器，使得系统的输出信号功率值与信号亮温值成线性关系，再经过低通滤波器进行滤波，滤除信号中的高频起伏分量，即输出全功率信号。

仿真系统的参数设置为：整个系统的采样频率设置为 $1 2 0 ~ \mathrm { { k H z } }$ ，仿真时间 $2 1 0 \mathrm { ~ s ~ }$ ，系统中频带宽$2  { \mathrm { \ k H z } }$ ，中频耦合输出端的低通滤波器积分时间$\tau$ 为 $0 . 5 \mathrm { ~ s ~ }$ 。利用迪克开关控制噪声信号的周期性注入时，采用的脉冲时序采样周期为 $1 0 \mathrm { ~ s ~ }$ ,每个时序周期内设定10个脉冲值，通过不同噪声源对应脉冲时序值的设计，实现系统噪声注入状态的切换。另外，结合实际的辐射计硬件系统，将系统中涉及到的几种噪声源信号亮温值分别设置为：天线信号亮温值$T _ { a } = 8 0 \mathrm { ~ K ~ }$ ，公共噪声源(外噪)亮温值 $T _ { e } = 7 0 \textrm { K }$ ，匹配负载亮温值 $T _ { o } = 3 0 0 \textrm { K }$ ，内部噪声源亮温值 $T _ { n } =$ $1 0 0 \mathrm { ~ K ~ }$ ，接收机噪声亮温值 $T _ { \mathrm { r e c } } = 2 0 0 \ \mathrm { K }$ 。需要注意的是，以上噪声源亮温值均表示等效到同一输入端以后的数值大小。

# 5.1.1 开关时序控制

由于仿真系统中涉及到多种不同的噪声源，包括天线信号、公共噪声源（外噪）、内部噪声源、匹配负载噪声源以及接收机噪声，要对这些噪声源的注入状态进行控制，就涉及到多个迪克开关的时序设置问题，不同噪声源对应的控制开关时序不同，下面详细说明脉冲时序的设置情况。首先，考虑到实际的接收机通道中始终存在系统噪声，所以接收机噪声源信号始终添加在系统中。其次，天线信号注入到系统中，在经过匹配负载噪声源处的迪克开关时，通过开关的切换选择功能，将系统整体切换于这两种信号源之间，所以将匹配负载噪声源处的控制时序设置为 $[ 0 \mathrm { ~ 0 ~ 0 ~ 0 ~ 0 ~ 0 ~ 0 ~ 1 ~ 1 ~ 1 ~ } ]$ ，其中，“0"表示信号不输入系统，“1"表示信号输入系统。可以看出，在第8、9、10这3个时序的情况下将匹配负载噪声源注入系统，其他时序情况下将天线信号注入系统。最后，在天线信号噪声源或匹配负载噪声源这两种状态切换的基础之上，搭配其他噪声信号的输入，实现不同的噪声状态，用以完成系统定标的功能。对于公共噪声源(外噪)的控制开关，设置的脉冲时序为$[ 0 \mathrm { ~ 0 ~ 0 ~ 0 ~ 0 ~ 0 ~ 1 ~ 0 ~ 0 ~ 0 ~ 0 ~ } ]$ ，即只在第6个脉冲时序将公共噪声源注入到系统中，其他时序情况下不注入。同理，内部噪声源配置的控制开关时序为[000000$\mathrm { ~ 1 ~ 1 ~ 0 ~ 0 ~ } \exists$ ，在第7、8两个时序将内部噪声源注入系统，其他情况下不注入。仿真中不同噪声源对应的迪克开关脉冲时序设置情况如表3所示。

表3系统开关时序控制表  
Table 3Sequential control of the system switch   

<html><body><table><tr><td></td><td colspan="10">脉冲开关控制时序</td></tr><tr><td>匹配负载</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>1</td></tr><tr><td>外部噪声源</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>内部噪声源</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td><td>0</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>Ta</td><td>Ta</td><td>T</td><td></td><td></td></tr><tr><td>系统噪声源</td><td></td><td></td><td>Ta</td><td></td><td></td><td>+Te</td><td>+T"</td><td>+T"</td><td>T。</td><td></td></tr><tr><td></td><td></td><td></td><td>+Trec</td><td></td><td></td><td>+Trec</td><td>+Trec</td><td>+Tree</td><td>+Trec</td><td></td></tr></table></body></html>

总之，通过上述多个开关脉冲时序的搭配设置，对系统注入不同的噪声源，以实现期望的几种输入噪声状态。

# 5.1.2 两点定标处理

在中频单元的耦合输出端观测全功率信号的波形，并且将输出值换算为对应的噪声源亮温值。在换算过程中，涉及到辐射计系统的两点定标问题。对仿真系统注入已知温度的噪声源及匹配负载，进行两点定标，获得系统的亮温一功率定标方程。在仿真过程中，系统首先注入匹配负载噪声源，再考虑到接收机本身的噪声，获得此时整个系统的亮温值${ T _ { 1 } } = 5 0 0 \mathrm { ~ K ~ }$ ,对测量得到的中频耦合输出功率值求平均，得到功率 $P _ { 1 } = 1 . 6 4 8 9 \times 1 0 ^ { - 1 2 }$ W;接着在以上系统中添加内部噪声源，整个系统对应的亮温值改变为 $T _ { \mathrm { 2 } } = 6 0 0 \mathrm { ~ K ~ }$ ，中频耦合输出功率求平均后得到$P _ { \mathrm { { 2 } } } = 1 . 9 8 0 3 \times 1 0 ^ { - 1 2 } \mathrm { { ~ W } }$ 。通过以上两组数据进行两点定标，从而确定接收机系统的亮温一功率定标线，接收机系统的定标线如图10所示。

图10中，直线的斜率对应系统的增益值，表征接收机系统亮温值与信号输出功率之间的线性关系。

![](images/740d798316fba75c778a7f3504e37a9ac1dcb8787acb1de611070c0e4edc5e14.jpg)  
图10接收机系统定标线  
Fig.10Calibration line of the receiver system

# 5.1.3系统指标参数分析

获得定标线以后，对于未知噪声亮温值的天线信号，就可以通过测量其在接收机系统输出端的输出功率，在该直线上进行亮温值的换算。进行功率换算以后的中频耦合输出的单通道全功率信号波形图如图11所示。

在图11中，上半部分表示中频耦合输出的功率值，下半部分表示换算以后的系统亮温值，图中的黑线表示仿真输出，灰线表示理论输出。系统切换于5种噪声源注入状态：第一种注入天线和接收机噪声信号，等效总亮温值为 $2 8 0 \mathrm { ~ K ~ }$ ;第二种注入天线、公共噪声源以及接收机噪声信号，等效总亮温值为$3 5 0 \mathrm { ~ K ~ }$ ;第三种注人天线、内部噪声源以及接收机噪声信号，等效总亮温值为 $3 8 0 ~ \mathrm { { K } }$ ;第四种注入匹配负载、内部噪声源以及接收机噪声信号，等效总亮温值为 $6 0 0 ~ \mathrm { K }$ ;第五种注入匹配负载以及接收机噪声信号，等效总亮温值为 $5 0 0 ~ \mathrm { K }$ 。从图中可以看出，通过对时序脉冲的控制，实现了不同噪声源比例的注入，将系统切换于不同的状态之间。对仿真中每个系统状态下输出的亮温值，经过求平均及均方差值处理，分别与理想数据进行对比，结果如表4所示。

![](images/6482b75b351b37225aefdd74fea55ae3656ab03f231dc7cfbe57b8469c09022f.jpg)  
图11中频耦合输出图

表4全功率测量仿真数据对比  
Table 4Comparison of the simulation data   

<html><body><table><tr><td>数据</td><td>状态1</td><td>状态2</td><td>状态3</td><td>状态4</td><td>状态5</td></tr><tr><td>Tsys/K</td><td>280</td><td>350</td><td>380</td><td>600</td><td>500</td></tr><tr><td>仿真亮温均值/K</td><td>278.8597</td><td>348.7614</td><td>378.8509</td><td>597.5534</td><td>497.5705</td></tr><tr><td>△T/K</td><td>8.8544</td><td>11.0680</td><td>12.0167</td><td>18.9737</td><td>15.8114</td></tr><tr><td>仿真亮温均方差/K</td><td>9.1030</td><td>11. 2928</td><td>12.1044</td><td>19.1612</td><td>15.8415</td></tr></table></body></html>

表4中，理想灵敏度 $\Delta T$ 的值是通过式(1)进行计算所得，在仿真系统中， $B$ 为 $2 \mathrm { \ k H z } , \tau$ 为 $0 . 5 \mathrm { ~ s ~ }$ 。通过数据对比可以看出仿真输出亮温平均值与理论值基本一致，相对误差在 $0 . 5 \%$ 左右；均方差值与理论灵敏度误差在 $2 . 5 \%$ 之内，理论值与仿真值相差不大，验证了仿真系统的正确性。

需要说明的是，此处在计算灵敏度参数时使用的 $\boldsymbol { \tau }$ 为系统的单点积分时间，实际仿真是在一个较长的观测周期内对单点积分时间进行统计平均，通过拉长系统的积分时间，达到优化系统灵敏度参数的目的。仿真中设定观测周期为 $1 0 0 \mathrm { ~ s ~ }$ ,将单点积分时间所对应的灵敏度数值优化了 $\sqrt { 2 0 0 }$ 倍。在表4对比过程中，为了重点讨论说明仿真所得与理论灵敏度参数的对应关系，所以只比较了单点积分时间所对应的灵敏度数值。

接下来考察系统的线性度指标，通过仿真系统的输入噪声温度值与输出功率值之间的线性关系进行说明。仿真系统中设置了几组不同的亮温输入值，分别得到了对应的功率输出值，利用所得数据绘制出辐射计线性度仿真曲线如图12所示。

![](images/515e2b48e4cacf1fc91d91a14bcd6521a100f414c03625297b8eade8e57ce8ed.jpg)  
Fig.11Coupling output of IF   
图12辐射计线性度仿真曲线图 Fig.12Linearity of the silulation system

由图12可以看出，仿真模型的输出值与输入的噪声温度之间具有良好的线性关系，其线性相关度用线性相关系数 $R$ 来表示：

$$
R = { \frac { \displaystyle \sum _ { i = 1 } ^ { N } ( V _ { i } - { \overline { { V } } } ) ( T _ { i } - { \overline { { T } } } ) } { \displaystyle \sqrt { \sum _ { i = 1 } ^ { N } ( V _ { i } - { \overline { { V } } } ) ^ { 2 } \sum _ { i = 1 } ^ { N } ( T _ { i } - { \overline { { T } } } ) ^ { 2 } } } }
$$

其中：V=- $\overline { { V } } = \frac { 1 } { n } \sum _ { i = 0 } ^ { n - 1 } V _ { i }$ ，表示输出功率的平均值， ${ \overline { { T } } } =$ 1Ti,表示对应噪声温度的平均值。

将图12中的数据分别代入式（2）中，计算得到搭建的辐射计仿真系统的线性相关系数为 $R =$ 0.9999，结果表明仿真系统的输出值与输入值之间具有良好的线性度。

# 5.2 双通道干涉测量仿真

对于双通道干涉测量，首先简化系统注入噪声源的状态，只把天线信号作为公共信号注入到两个接收机通道中，记为 $T _ { \mathrm { i n j e c t } }$ ，同时，接收机自身的噪声信号作为各个通道的系统噪声源，分别记为 $T _ { \mathrm { r e c l } }$ 和$T _ { \mathrm { r e c 2 } }$ 。在理论上，系统输出的理论模拟相关系数的幅值大小与噪声源的分配值有如下关系：

$$
\rho _ { \mathrm { i d e a l } } = { \frac { T _ { \mathrm { i n j e c t } } } { { \sqrt { T _ { \mathrm { i n j e c t } } + T _ { \mathrm { r e c l } } } } \bullet { \sqrt { T _ { \mathrm { i n j e c t } } + T _ { \mathrm { r e c } } } } } }
$$

通过在系统中配置不同比例的噪声源，实现模拟相关系数不同幅值的输出。另一方面，对于双通道的二元干涉仪仿真系统，还涉及到两个接收机通道之间的相位差问题，这个差值与得到的相关系数相位值是一一对应关系。

利用仿真系统输出数字相关系数 $\boldsymbol { r }$ ，经过对干涉测量输出值的校正，实现数字相关系数到模拟相关系数的估计[15],得到模拟相关系数 $\rho _ { \mathrm { s i m } }$ ，对比不同参数设置情况下 $\rho _ { \mathrm { i d e a l } }$ 与 $\rho _ { \mathrm { s i m } }$ 的差异。在数值对比过程中，主要从均值和均方差两个角度进行结果评估。一方面，仿真输出的模拟相关系数在幅度和相位上的均值应该与理论值相近;另一方面，理论上亮温值的均方差对应着系统灵敏度的大小，则利用式（3）可以得到模拟相关系数均方差值的理论值应该是$1 / \sqrt { B \tau }$ ，对比此理论值与实际仿真输出的模拟相关系数的均方差值，评估仿真性能。

# 5.2.1 相关系数仿真评估

将两个接收机通道的相位差值固定为 ${ 0 } ^ { \circ }$ ，接收机通道噪声源 $T _ { \mathrm { r e c l } }$ 和 $T _ { \mathrm { r e c 2 } }$ 固定为 $3 0 0 ~ \mathrm { K }$ ，只改变天线噪声信号 $T _ { \mathrm { i n j e c t } }$ 值大小,通过仿真输出测量 $\rho _ { \mathrm { i d e a l } }$ 与 $\rho _ { \mathrm { s i m } }$ 数据。

示例，设置天线噪声信号亮温为 $T _ { \mathrm { i n j e c t } } = 7 5 \mathrm { ~ K ~ }$ .根据式（3)，有 $| \rho _ { \mathrm { i d e a l } } | = 0 . 2$ 。系统输出数字相关系数，再利用数字相关系数到模拟相关系数的估计理论，得到估计的模拟相关系数值，估计得到的模拟相关系数如图13所示。

0.40.30.10 20 40 60 80 100 120 140 160 180200时间/s(a)估计得到的模拟相关系数幅值200100Www相-100-2000 20 40 60 80 100120 140 160180 200时间/s(b)估计得到的模拟相关系数相位

对所得的仿真数据结果进行处理分析，分别求得模拟相关系数幅值和相位的均值与均方根值，得到仿真输出的模拟相关系数 $\mid \rho _ { \mathrm { s i m } } \mid$ 均值为0.2033，而理想模拟相关系数 $\mid \rho _ { \mathrm { i d e a l } } \mid$ 为0.2，相对误差为$1 . 6 5 \%$ ;模拟相关系数 $\angle \rho _ { \mathrm { s i m } }$ 均值为- $\boldsymbol { \cdot } 0 . 2 9 3 2 ^ { \circ }$ ,理想模拟相关系数 $\angle \rho _ { \mathrm { i d e a l } }$ 为 ${ 0 } ^ { \circ }$ 。差值控制在 $0 . 3 ^ { \circ }$ 以内；仿真相关系数 $\rho _ { \mathrm { s i m } }$ 均方根值为0.0380，理论模拟相关系数 $\rho _ { \mathrm { i d e a l } }$ 的均方根值为0.0322，两者较为接近。通过数值对比看出仿真输出与理论值差异不大，说明了仿真系统的正确性。

实验仿真了多组不同分配比例的 $T _ { \mathrm { i n j e c t } }$ 和 $T _ { \mathrm { r e c } }$ ，分别求得对应的均值及均方差值，并与理论值进行对比，结果如表5所示。

表5改变噪声亮温值结果对比   
Table5 Result of different bright temperature   

<html><body><table><tr><td>数据</td><td>设置1</td><td>设置2</td><td>设置3</td><td>设置4</td><td>设置5</td></tr><tr><td>Tinjeet/K</td><td>33.3</td><td>75</td><td>100</td><td>200</td><td>300</td></tr><tr><td>| pideal|</td><td>0.1</td><td>0.2</td><td>0.25</td><td>0.4</td><td>0.5</td></tr><tr><td>|psim|</td><td>0.0998</td><td>0.2033</td><td>0.2595</td><td>0.4431</td><td>0.5802</td></tr><tr><td>∠pideal/°</td><td></td><td></td><td>0</td><td></td><td></td></tr><tr><td>∠psim/°</td><td>0.1670</td><td>一0.2932</td><td>-0.3680</td><td>-0.2040</td><td>-0.1440</td></tr><tr><td>Pideal均方差</td><td></td><td></td><td>0.0322</td><td></td><td></td></tr><tr><td>psim均方差</td><td>0.0360</td><td>0.0380</td><td>0.0382</td><td>0.0392</td><td>0.0398</td></tr></table></body></html>

通过表5可以看出，仿真得到的模拟相关系数$\rho _ { \mathrm { s i m } }$ 与理论模拟相关系数 $\rho _ { \mathrm { i d e a l } }$ 幅度均值相对误差在$5 \%$ 左右，相位误差控制在 $0 . 4 ^ { \circ }$ 以内，均方差值也具有很好的一致性。对比结果表明仿真过程的正确性。

# 5.2.2相关相位仿真评估

固定 $T _ { \mathrm { i n j e c t } }$ 、 $T _ { \mathrm { r e c } }$ 大小比例的分配，只对两个接收机通道的相位差值进行改变，观测仿真输出的 $\rho _ { \mathrm { i d e a l } }$ 与 $\rho _ { \mathrm { s i m } }$ 的差异。 $T _ { \mathrm { i n j e c t } } { = } 7 5 \mathrm { ~ K } , T _ { \mathrm { r e c l } } { = } T _ { \mathrm { r e c 2 } } { = } 3 0 0 \mathrm { ~ K }$ ，则理论模拟相关系数 $\mid \rho _ { \mathrm { i d e a l } } \mid$ 为0.2。同样进行了多组仿真实验，得到的数据结果如表6所示。

表6改变接收机相位差结果对比  
Table6 Result of different phase of reciever   

<html><body><table><tr><td>数据</td><td>设置1</td><td>设置2</td><td>设置3</td><td>设置4</td><td>设置5</td><td>设置6</td><td>设置7</td></tr><tr><td>| pideal |</td><td></td><td></td><td></td><td>0.2</td><td></td><td></td><td></td></tr><tr><td>|psim|</td><td>0.2033</td><td>0.2029</td><td>0.2034</td><td>0.2033</td><td>0.2029</td><td>0.2034</td><td>0.2033</td></tr><tr><td>∠pideal/°</td><td>0</td><td>30</td><td>60</td><td>90</td><td>120</td><td>150</td><td>180</td></tr><tr><td>∠psim/°</td><td>-0.2932</td><td>29.6953</td><td>59.7082</td><td>89.7068</td><td>119.6953</td><td>149.70182</td><td>179.7068</td></tr><tr><td>Pideal均方差</td><td></td><td></td><td></td><td>0.0322</td><td></td><td></td><td></td></tr><tr><td>psim均方差</td><td>0.0380</td><td>0.0372</td><td>0.0377</td><td>0.0380</td><td>0.0372</td><td>0.0377</td><td>0.0380</td></tr></table></body></html>

通过表6数据可以看出，仿真得到的模拟相关系数 $\rho _ { \mathrm { s i m } }$ 与理论模拟相关系数 $\rho _ { \mathrm { i d e a l } }$ 幅度均值相对误差为 $1 . 7 \%$ 以内，相位误差控制在 $0 . 3 ^ { \circ }$ 左右，均方差值也很接近。综合对比结果表明了仿真的正确性。

# 5.3ADC采样频率对相关结果的影响

对干涉式微波辐射计系统来说，ADC部分对信号的处理是得到复相关输出的关键环节。在ADC中，涉及到对原始信号的采样问题，要想获得信号完整的重建，采样时钟频率必须满足奈奎斯特准则。对于所搭建的仿真系统，采用了正交混频方法，将中频输出信号分为I/Q两路，则理论上只需要一半的奈奎斯特采样率即可保证不发生信号的频域混叠。理论上，不同的时钟采样频率对相关结果会产生影响，采样频率越高，信号的重建越准确，输出的相关结果指标会越好。

仿真系统的中频带宽为 $2  { \mathrm { \ k H z } }$ ，则可以确定对信号进行完整重现的最低采样频率是 $2  { \mathrm { \ k H z } }$ 。固定天线噪声信号的亮温值为 $T _ { \mathrm { i n j e c t } } { = } 7 5 \mathrm { ~ K ~ }$ ，接收机噪声信号的亮温值为 $T _ { \mathrm { r e c 1 } } { = } T _ { \mathrm { r e c 2 } } { = } 3 0 0 \ \mathrm { K }$ ,接收机之间相位差为 $0 ^ { \circ }$ ，对仿真系统设置不同的采样频率 $f _ { s }$ ，测量相关输出的均值及均方差值。

数据结果显示，随着采样率的变化，相关系数的均值变化不大，但均方差值有所影响。利用所得数据绘制图形，观测采样率对相关系数均方差值的影响趋势，横轴取采样率与系统带宽的比值，即 $f _ { s } / B$ ，纵轴取理论均方差与仿真输出均方差的比值，即$\rho _ { \mathrm { i d e a l } } / \rho _ { \mathrm { s i m } }$ ，观察仿真输出数据随采样率的变化，得到的图形如图14所示。

图14中显示的散点就是仿真获得的数据，通过数据拟合以后产生图中所示曲线。由上图可以看出，随着系统采样率的增加，仿真输出相关值的均方差越来越趋近于理论值，表明系统的灵敏度指标不断提升。

同时，曲线前期上升趋势比较明显，而后期趋近于平缓，说明在满足奈奎斯特准则的条件下，初始采样率的增加对系统性能有明显提升效果，而当采样率达到一定指标之后，改善系统灵敏度的效果不再显著。

![](images/9c847af7123c728c2807ea407fcce7c63979d623d062d57f37f44db671b7d8cf.jpg)  
图14采样率对相关输出的影响图  
Fig.14The influence of sampling rate on the correlation

# 6结语

本文所做的主要工作是利用Matlab/Simulink平台搭建出干涉式微波辐射计系统，对二元干涉仪进行了时域上的仿真。利用所搭建的模型实现了单通道全功率测量仿真以及双通道干涉测量仿真，完成了系统定标、三阶量化数字相关结果的转化以及ADC采样频率影响的评估，在时域范围内实现了对系统测量精度、灵敏度指标的定量化分析。

# 参考文献(References)：

[1]Obligis E,Boone C,Larnicol G,et al.Benefits of the Future Sea Surface Salinity Measurements from SMOS:Generation and Characteristics of SMOS Geophysical Products[J].IEEE Transactions on Geoscience and Remote Sensing,2008,46(3):746-753.

[2]Le Vine D M,Lagerloef G S,Colomb F R,et al.Aquarius:An Instrument to Monitor Sea Surface Salinity from Space[J]. IEEE Transactions on,Geoscience and Remote Sensing,2007, 45(7):2040-2050.   
[3]Liu H,Zhang X K,Niu L J,et al.A Combined L-band Synthetic Aperture Radiometer and Fan-Beam Scatterometer for Soil Moisture and Ocean Salinity Measurement[C]//2012 IEEE International: Proceedings of the Geoscience and Remote Sensing Symposium(IGARSS),2012,4644-4647.   
[4]Ulaby F T,Moore AK,Fung AK.Microwave Remote Sensing Active and Passive Vol. I,Microwave Remote Sensing Fundamentals and Radiometry[M].Addison-Wesley Publishing Company,1986.   
[5]Wu Ji,Liu Hao,Yan Jingye,et al. Interferometric Imaging Technology for Passive Microwave Radiometry[J].Remote Sensing Technology and Application,2009,24（1)：1-12.[吴 季，刘浩，阎敬业，等.干涉式被动微波成像技术[J].遥感技术 与应用，2009,24(1)：1-12.]   
[6] Dong Xiaolong，Wu Ji,Huang Yonghui. Synthetic Aperture Microwave Radiometer and Image Retrieval[J].Remote Sensing Technology and Application，2000,15（2):74-78.[董晓 龙，吴季，黄永辉.综合孔径微波辐射计及其反演成像[J].遥 感技术与应用,2000,15(2)：74-78.]   
[7]Ruf C S,Swift C T,Tanner A B,et al.Interferometric Synthetic Aperture Microwave Radiometry for the Remote Sensing of the Earth[J].IEEE Transactions on Geoscience and Remote Sensing,1988,26(5):597-611.   
[8]Wu Ji,Liu Hao,Sun Weiying,et al. Technical Development and Application Prospect of Synthetic Aperture Radiometer[J].Remote Sensing Technology and Application,20o5,20（1):24-29. [吴季，刘浩，孙伟英，等.综合孔径微波辐射计的技术发展及其 应用展望[J].遥感技术与应用，2005，20(1)：24-29.] [9]Camps A,Corbella I,Vall-Llossera M,et al.The SMOS Endto-end Performance Simulator:Description and Scientific Ap plications[C]//IGARSS'o3 Proceedings Toulonse，France, 2003,1:13-15.   
[10]Burrage D M,Goodberlet MA,Heron ML.Simulating Passive Microwave Radiometer Designs Using Simulink[J].Simulation,2002,78(1):36-55.   
[11]Huang Yongan,Ma Lu,Liu Huimin. MATLAB7.O/Simulink6.0 Modeling and Simulation Development and Advanced Engineering Applications[M].Beijing:Tsinghua University Press,2Oo5.[黄永 安，马路,刘慧敏.MATLAB7.O/Simulink6.O建模仿真开发与 高级工程应用[M].北京：清华大学出版社,2005.]   
[12]Liu H,Niu L J,Zhang C.System Study and Development of An L-band 1-D Synthetic Aperture Radiometer for Ocean Salinity Measurement[C]//2ol3 IEEE International:Proceedings of the Geoscience and Remote Sensing Symposium (IGARSS),2013,1916-1919.   
[13]LiQiang,Wang Mingang,Yang Yao.Code Generation of Simulink Models in the Hardware-in-loop Simulation[J].Electronic Measurement Technology,2009,32（2)：28-31.[李强， 王民钢，杨尧.快速原型中Simulink模型的代码自动生成 [J].电子测量技术，2009,32（2)：28-31.]   
[14]Tian Wei,Xiong Jinkui. $\mathrm { C / C } + +$ Coder Generation of Simulink Models[J].Applied Science and Technology，2005，31 (11)：16-18.[田伟，熊晋魁.Simulink 模型的 $\mathrm { C / C } + +$ 代码实 现[J].应用科技，2005，31(11)：16-18.]   
[15]Li Huiling,Liu Hao,Wu Ji,et al.Research on the Preprocessing Method for the Visibility Functions in Synthetic Aperture Radiometer[J].Journal of Electronics&. Information Technology,2012,34(10)：2475-2481.[李慧玲，刘浩，吴季，等.综合 孔径辐射计可见度函数预处理算法及时域仿真研究[J].电子 与信息学报，2012，34（10)：2475-2481.]

# Simulation of Microwave Interferometric Radiometer System based on Simulink

Chen Si²,Liu Hao1,Wu ji1,Niu Lijiel (1.CAS Key Laboratory of Microwave Remote Sensing ,National Space Science Center/Center for Space Science and Applied Research ,Chinese Academy of Sciences ,Beijing lOol9o,China; 2.University of the Chinese Academy of Sciences ,Beijing lOoo49,China)

Abstract:A method using Simulink to build the simulation model of the microwave interferometric radiometer （MIR）system is introduced in this paper.Two-element interferometer is the basic unit of the MIR system.By the Simulink platform,a simulation model of the two-element interferometer was built and the measurement process of the random noise was simulated. Through the simulation of the fullpower measurement achieved interference measurement of single channel and two channels.Quantitative analysis of the radiometric accuracy and radiometric sensitivity were achieved in the time domain.

Key words: Microwave interferometric radiometer; Visibility function;Simulation model; Simulink