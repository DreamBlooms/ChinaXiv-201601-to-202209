# AgileDARN雷达数字信号处理的FPGA实现

蒋 松1²，蓝爱兰¹，阎敬业¹，孙林31（中国科学院国家空间科学中心，中国科学院微波遥感技术重点实验室，北京，100190)2（中国科学院大学，北京，100049）3（北京理工大学信息与电子学院，北京，100081）

摘要：AgileDARN雷达系统是一种基于全数字相控阵技术的灵敏型地基相干高频雷达系统，实现对中高纬度电离层的探测。本文对雷达系统的数字信号处理展开研究，设计分析雷达数字系统收发信号处理流程，基于FPGA芯片实现信号收发、幅相不一致性校正、数字滤波、数字波束合成处理，实现方向图的灵活扫描和回波定向精度的提升，通过仿真实验验证了FPGA设计的可行性和有效性。关键字：FPGA，AgileDARN，SuperDARN，阵列天线，波束合成，数字滤波

# Analysis of FPGA implementation for AgileDARN radar digital system

JIANG Song1,2，Lan Ai-lan1， YAN Jing-yel， Sun lin³1(CAS Key Laboratory of Microwave Remote Sensing， National Space Science Center,Chinese Academy of Sciences, Beijing, 100190, China)2(University of Chinese Academy of Sciences，Beijing，100049，China)3 （School of Information and Electronics， Beijing Institute of Technology，Beijing，1Oo08l， China)

Abstract: AgileDARN radar system is a kind of sensitive ground coherent high frequency radar system based on alldigital phased aray technology,which can realize the detection of Middle and high latitude ionosphere. In this paper,The digital signal processng of radar system is studied detailed.The mechanism of digital signal processing of radar system have been designed and analyzed. The FPGA is used to implement the signal transceiver,Amplitude-phase corrction,Digital beam forming and digital filter forradar system，So the system can realizes flexible scanning of the direction map and improves the Echo orientation precision.The feasibility and effectiveness of the FPGA design is verified through the simulation experiments.

Key words: FPGA, AgileDARN, SuperDARN, Array antenna, Digital beam forming(DBF), Digital filter

# 1引言

电离层是地球空间60公里以上部分电离的高层大气圈，是航天器运行的最主要区域，也是无线电波传播的主要媒介。电离层环境中的扰动会对以空间技术为基础的各种空间平台产生重大影响。电离层扰动幅度可达15dB以上，经常会引起通信中断、误码率增大现象；对于卫星导航的定位误差影响高达百米量级；地基雷达的目标探测、战略预警等亦将遭受严重影响。对电离层特性的认知和人工改变电离层变得异常重要[1,2]。

国际超级双极光雷达网（SuperDARN）正是为了研究中高纬度地区电离层异常而形成的雷达网络。SuperDARN由于其广泛的地域覆盖以及高精度的连续测量逐渐成为研究极区电离层活动重要的观测工具[3]。SuperDARN 是由三十几个发射频率在8\~20MHz的地基高频雷达组成网络。这些雷达由英国、美国、澳大利亚、日本等10多个国家合作建成[4]，我国于 2010 年在南极中山站建成了一部SuperDARN高频雷达。目前，中科院空间中心正在自主研制一部具有高灵活性的高频雷达（称为AgileDARN)，该雷达站位于黑龙江佳木斯市，将用于对中国中高纬度地区电离层进行探测，弥补 SuperDARN 雷达网络在中国上空的数据空白。AgileDARN雷 达 借 鉴 传统SuperDARN的设计理念，采用双阵列探测方式：具有收发功能的16单元主阵和只有接收功能的4单元子阵。同时，作为新一代SuperDARN雷达，AgileDARN采用全数字相控阵技术，可实现雷达波束的任意扫描，突破了传统SuperDARN雷达固定波束、以及固定波束间隔的限制。AgileDARN雷达主要由天线阵列、收发组件和数字系统三个部分组成[5.6]。其中，数字系统是雷达系统的心脏，用于实现雷达工作状态控制、发射信号生成、回波信号实时处理等功能。本文主要围绕数字系统的信号生成及回波信号处理的FPGA实现展开研究。

![](images/a59a5f0d583547c907b38069e984106f7baa9f77e46d86c1d18b70a492b8fe13.jpg)  
图1发射信号产生流程图

# 2.2回波采集处理模块

回波采集处理模块需要采集20路回波信号，包括16路主通道和4路辅通道。采集的数据通过FPGA处理板进行进行滤波、下变频等预处理，从而获得有效的雷达回波数据。其信号的处理流程如图2所示。

# 2 雷达数字系统

AgileDARN系统的数字信号处理部分主要包括发射信号产生模块和回波采集处理模块。其中，发射信号产生模块用于生成各通道所需的发射信号；回波采集处理模块则对AD采样后的回波信号进行一系列预处理，以获得所需要的数据。

AgileDARN雷达采用“ $1 6 { + } 4 ^ { , }$ 的双阵体制，包括16单元收发主阵和4单元接收子阵，因此共有16个发射通道和20个接收通道。

# 2.1发射信号产生模块

发射信号产生模块需要产生16路发射信号，模块主要包括DA处理板和DA回放板，处理板负责接收上位机配置的工作参数产生发射信号；DA回放板将数据转换为模拟发射信号。

DA处理板的FPGA需要完成的功能有：(1)DAC芯片的配置：使其处于正常工作状态；(2)信号的产生；(3)调制成16通道信号，分别进行发射通道不一致性校正； (4)根据波束指向要求对发射信号进行相位加权等功能。发射信号产生模块的主要流程如图1所示：

![](images/04db9a53a02ea901d0f8b2a9e39cd760b0c36589a583e717402fb1315e33e757.jpg)  
Fig.1Processing flow diagram of transmit signal   
图2回波采集处理流程图  
Fig.2Processing flow diagram of echo signal

其中，带通滤波器主要用于抑制采集数据的带外干扰信号；FPGA接收到ADC采样的原始中频数据，进行数字正交下变频处理，输出I、Q两路正交信号，以获取信号的相位信息；为了降低数据率，需要对正交下变频处理后的数据进行抽取；同时，为了避免数字下变频过程中引入的混频干扰及信号抽取时带来的谐波干扰，在进行幅相不一致性校正之前对I、Q信号分别进行了窄带滤波。由于全系统不同的接收通道间会由于硬件非理想性，使得接收通道之间存在幅相不一致性误差，回波处理模块利用接收定标数据对接收通道的幅相误差进行校正。通过不同波位选择，对校正后的接收信号完成数字波束合成（DBF)。系统DBF操作采用主16路回波信号并行7波束处理，4路辅通道单波束处理的机制，实现雷达系统的角分辨率和探测距离的提升，完成对不同波束指向的观测。

# 3信号处理单元的FPGA实现

# 3.1发射时序的设计

SuperDARN雷达最大探测距离超 $3 0 0 0 \mathrm { k m }$ ，同时中高纬度电离层漂移速度可高达 $2 0 0 0 \mathrm { m / s }$ 。为了解决距离模糊与速度模糊的矛盾，采用非等时间间隔多脉冲序列进行探测[8]；另外，为了降低雷达通道间不一致性的影响，在每个观测周期的初始先对发射机和接收机进行标定。具体发射时序如下图3所示。每个周期的时序分成定标和目标探测两个部分；定标包括接收定标和发射定标两部分，目标探测则包括对雷达视场内各个波位的观测。另外，定标时采用单脉冲序列，而目标探测时则采用多脉冲序列进行观测，且同一观测周期内的多脉冲序列形式保持一致。

![](images/4db605454a4de9cbc7529a67ee77e1c5089b741d86f42a6d2111fd793ebc0ea3.jpg)  
图3发射时序设计  
Fig. 3 Timing Design

上图所示发射时序中含有多个可调参数，包括脉冲宽度、最小延迟间隔、各脉冲间隔等等。这些参数的设置和雷达的探测距离、距离分辨率、时间分辨率等性能参数直接相关[7.8]。一个观测周期中含有接收定标、发射定标和N个多脉冲序列，如图3(a)，用来探测目标的N个多脉冲序列表征N个不同的波位指向及波位驻留次数等信息，如图3(b)为目标探测脉冲。

为了简化FPGA硬件资源负担，图3中的工作时序的各项参数由上位机进行配置。FPGA设计逻辑是：工作时序中的各脉冲，由触发信号来进行启动。FPGA根据所设计的时序，解析出接收定标、发射定标和目标探测子脉冲的产生触发信号，通过检测触发信号的上升沿，利用DDSCompilerCore产生相应的原始发射信号。同时，FPGA接收上位机配置的各个脉冲脉宽等参数，控制脉冲信号的停止。如图4(a)所示，通过ModelSim产生的时序仿真图9]。

![](images/fb38913879404959d83ed88fc3ab1c6553c04015ed7e77e4bbb772d4e879f2f9.jpg)  
图4单通道的发射信号时序图  
Fig.4 Transmit signal timing diagram

图4(a)中第一行数据波形是FPGA解析的脉冲触发信号，触发信号的到来标志发射信号脉冲的产生。FPGA对脉冲宽度进行计时，当脉宽满足要求值时停止产生信号。图中的第三行波形表示产生的发射信号波形，左起第一个和第二个脉冲是接收定标和发射定标数据，其余为目标探测子脉冲。FPGA测试结果如图4(b)所示，和设计的工作时序完全相同。

# 3.2数字滤波器的设计

信号经过AD采样和数字下变频后会产生谐波干扰、互调干扰和交调干扰等，为了减小这些干扰信号的影响，提高信号的信噪比，需要对AD采样之后的数字信号进行带通滤波，以滤除采样过程中带来的干扰；同时也需要对数字下变频后的信号进行低通滤波处理，滤除数字正交下变频引入的和频分量，为了进一步抑制带外干扰信号的影响，需要再进行窄带低通滤波。这些滤波器是基于FPGA中的FIR滤波器IP核[12进行设计。

利用FPGA进行滤波器设计之前，需先利用Matlab软件中的FDAtool工具生成数字滤波器的系数配置文件（COE文件）。然后再将Matlab软件生成系数配置文件导入到FPGAFIR滤波器IP核中，生成数字滤波器[9,10]。

# 3.2.1带通滤波器

回波采样模块的接收定标数据和回波数据的频率为70MHz，经过60MHz采样后的中心频率为10MHz，发射定标数据采样后的中心频率为${ 8 { \sim } 2 0 \mathrm { M H z } }$ ，因此需要两套带通滤波器能够在AD采样后对采样数据进行实时处理，图5所示是系统要求的带通滤波器之一的幅频响应曲线，其中心频率为10Mhz，通带为2Mhz。

由于FPGA芯片的DSP资源限制，两套滤波器采用一组滤波器IP核资源，在进行实时滤波处理时，采用分时复用的机制进行滤波处理，即需要依据采样数据随时切换带通滤波器。利用FPGA实现时，将两组带通滤波器系数文件，通过IP核的两个通道载入到FIR滤波器IP核中，FPGA根据接收信号中心频率的不同产生切换新号，通过IP核配置端口发出指令实时切换滤波器的系数，配置的指令如表1所示[1]。

Table.1 FIR filter coeficient configuration instructions   

<html><body><table><tr><td>滤波器系数</td><td>配置指令</td></tr><tr><td>第一组带通滤波器</td><td>8'b00000000</td></tr><tr><td>第二组带通滤波器</td><td>8'b00000001</td></tr></table></body></html>

将图5滤波器的设计参数进行配置通过FPGA产生数字带通滤波器，利用MATLAB模拟原始数据，经过滤波后其幅频响应曲线如图6所示，对比前后结果发现经过滤波后带外的信号滤除掉了。

![](images/baee91f666a082502edbc0f020672ced72be976feeaf8ad7b3f36ec19a874ae7.jpg)  
图5带通滤波器的幅频响应曲线 Fig.5 The response curve of BPF

![](images/3f2511df639c76545c85747aa382162928add7469c382df4ddd0829ee8890e21.jpg)  
图6up.输入模拟原始信号的频谱响应; down.滤波器输出信号的频谱响应. Fig. 6 Up. the input signal's spectrum; Down. The spectrum of the filter output signal.

# 3.2.2低通滤波器

AD采集数据的处理过程中共有两级低通滤波器：正交下变频后的低通滤波器和窄带低通滤波器。数字正交下变频处理中的低通滤波器的功能是滤除混频引入的和频分量，再进行窄带低通滤波是为了进一步抑制带外干扰信号的影响。

为了减小系统的数据量，同时降低DSP资源的使用量，正交下变频后的低通滤波器和窄带低通滤波器的是带有抽取性质的数字滤波，系统对正交下变频中低通滤波后的数据进行抽取60倍，抽取后的采样率从60MHz将为1MHz。在FPGA的滤波器IP核中设置抽取倍数时，抽取倍数和IP核使用DSP资源量的关系如表2：

在FPGA设计时，配置下变频后FIR滤波器的抽取参数为6倍，同时，通过计数抽取方式进行10倍抽取滤波输出数据，从而满足60倍的抽取倍数。同时也使得数据采样率降低，数据量减少，为整个系统减负。

表1FPGA中FIR滤波器系数配置指令集  
表2滤波器IP核的抽取倍数和使用DSP个数 Table.2 The relationship between the extraction and the DSF number   

<html><body><table><tr><td>抽取倍数</td><td>DSP/个</td></tr><tr><td>无</td><td>4</td></tr><tr><td>1~6</td><td>1</td></tr><tr><td>7以上(含7)</td><td>2</td></tr></table></body></html>

通过对带通滤波器、低通滤波器的仿真实验验证了数字滤波器的滤波效果。基于FPGAIP核实现的FIR滤波器操控灵活、可靠性强，可以根据参数设置选择合适的硬件资源量和数据处理的速度，将成为未来数字滤波器应用的一大热点。

# 3.3幅相不一致性校正实现

AgileDARN雷达系统由16个发射通道和20个接收通道组成，由于硬件的非理想性，各通道之间会存在幅相不一致性误差。为了降低通道不一致性的影响，在每个观测周期的起始对接收通道间和发射通道间的不一致性进行标定，获取各接收通道间和发射通道间的幅度误差和相位误差，并在回波采集处理模块和发射信号产生模块中分别对接收通道间误差和发射通道间误差进行补偿实现通道间不一致性校正。其中，定标信号产生及误差补偿利用FPGA实现，而用于校正的不一致性幅相误差的获取则在上位机完成。接收通道间不一致性校正处理方法与发射通道基本相同，因此，本节中不对其进行区分。

![](images/76d188f98ece2fddf506d248ffdc2a3f1752fb83e7a4f9d5d74fdd02eac0cfef.jpg)

Fig.7 Acquisition of compensation factor

定标信号经过接收通道/发射通道后，经AD采样、滤波等一系列处理后，数字系统将处理后的定标数据传送给上位机，并在上位机对定标数据进行处理，获取各通道的不一致性幅相误差。不一致幅相误差的获取方法如图7所示。上位机获得第一通道的定标数据后，剔除无效数据计算出第一通道的幅值 $A _ { 1 }$ 和相位 $\Phi _ { 1 }$ ，相同的方式获得所有通道的幅值和相位，以第一通道输出为基准计算出各个通道的幅度误差 $\Delta a$ 和相位误差 $\Delta \varphi$ 。

上位机获取各通道的不一致性误差后，将不一致性幅相误差作为校正因子发送给数字系统。其中，接收通道的校正因子下发给回波采集处理模块，并在回波信号进行数字波束合成之前完成不一致性校正；发射通道的校正因子则发送给发射信号产生模块，亦在发射信号进行波束合成之前完成不一致性校正。此部分工作均由FPGA完成，具体实现过程为：上位机通过AXI-streaming协议将不一致性误差下发到FPGA的RAM核中进行存储，工作时利用FPGA内的ComplexMultiplierCore将不一致性误差和信号数据进行AXI协议格式的复乘完成，其原理如图8所示。

![](images/e41bfeed6fd035b0e79e0f4d6b1d940971a278a2b05514badf4ed3abed262700.jpg)  
图8幅相不一致性校正原理图  
Fig. 8 The principle of amplitude-phase consistency

# 3.4波束合成的实现

数字波束合成技术是相控阵雷达采用的最为广泛的技术之一，其具有快速自适应波束置零、超分辨定向、超低副瓣、阵元失效波束校正、密集多波束、自适应空时处理和灵活的时间控制等优点，是现代阵列信号系统必须采用的关键技术[13]

![](images/a1db2a53355150c95d53e02973b93f90bef1835f81710bc43461287e8d7ab5de.jpg)  
图7不一致性误差的获取  
图9波束合成时单波束内7个方向的示意图 Fig.9 the 7 directions of one single beam when beam-forming

AgileDARN雷达的天线阵列由两个线阵组成，主阵为16单元线阵，用于实现在方位向进行扫描观测；4单元接收子阵则通过与主阵信号进行干涉处理获取回波的仰角信息。为了在保持雷达时间分辨率的同时提高方位向上的角分辨率，AgileDARN雷达对主阵回波信号进行了多波束合成——7波束合成；即将一个波束宽度细分成7份（如图9所示)，将16通道的回波信号并行进行7个方向的波束合成，根据合成结果进行比较，判断回波的方位方向，从而获得更加精确的回波方位信息。

雷达系统对每个通道的信号进行7波束并行DBF的处理结构如图10所示：

![](images/8d2bc2eec590b437b13b57842cc0ac41f4e6c380b39b4fc82e414e70a421f996.jpg)  
图10并行7通道数据的波束合成  
Fig.10 The DBF of parallel 7 channels

FPGA将不一致性校正后的主16通道的数据后将每个通道复制成7份，上位机根据7个方向生成相应各通道的相移因子，并通过AXI-streaming协议将各移相因子下发存储在FPGA的RAMCore中，根据波位信号，FPGA从RAMCore中读取不同波束合成因子，将原始信号和合成因子进行

AXI协议格式的复乘完成波束合成操作。

发射信号产生模块可以直接采用ComplexMultiplierCore完成波束合成操作。而对于AD处理板，由于芯片DSP资源有限，波束合成不能采用利用ComplexMultiplierCore进行操作，而是通过调用乘法器，采用分时复用的方式依次完成复乘的实部相乘和虚部相乘，最后通过叠加得到DBF的结果，即将校正后的采样数据和波束合成因子的实部和虚部的乘法分时操作，使得乘法器资源的使用数量减半。

由于芯片资源和功能复杂度之间的矛盾，在利用FPGA实现雷达系统的功能时，对回波信号采集模块的带通滤波器、波束合成采用分时复用机制，并且对其它类型滤波器的采样频率进行降频（抽取）的操作，不仅减少了DSP资源的使用量，同时减少了整个系统的数据量，为数据的存储减负。表3所示为采用分时复用的方式实现带通滤波器后所使用的资源，而未采用此方式时DSP资源翻倍。

表3数字带通滤波器消耗资源  
Table.3 Resource consumption of BPF   

<html><body><table><tr><td>抽取倍数</td><td>未采用</td><td>采用</td></tr><tr><td>NumberofBlockRAM/FIFO:</td><td>20</td><td>10</td></tr><tr><td>Number ofDSP48E1s:</td><td>440</td><td>220</td></tr></table></body></html>

# 4总结语

本文利用FPGA数字电路和VerilogHDL语言软件实现了AgileDARN雷达数字系统的各项功能通过IPCore和软件逻辑完成发射时序的产生、发射通道间不一致性校正和相位加权，将发射信号转换成模拟发射信号；同时利用IPCore完成对采样后回波信号处理，包括带通滤波、数字下变频、低通滤波、接收通道间不一致性校正及波束合成。带通滤波和低通滤波分别用于抑制采样过程和下变频过程中引入的干扰；通道间不一致性校正用于消除通道间不一致性引起的幅度误差和相位误差，提高雷达的测量精度；而通过对主阵回波进行多波束合成，则大大提高了雷达在方位向上的角分辨率。

AgileDARN雷达共有16个发射链路和20个接收链路，系统复杂度比较高。系统复杂度越高，对硬件资源的需求越大。为了节约硬件资源，降低硬件成本，设计时利用分时复用的思想实现系统中的带通滤波、波束合成等功能模块，节省了大量的DSP资源。通过使用FPGA芯片中的IPCore,更加灵活可靠的实现系统的各项功能，通过实验分析表明，对于数字信号处理，FPGA电路有很强的灵活性和可操作性，并且具有较高的可靠性。

# 参考文献

[1]Liang Baixian.Li Jun,Feng Shuying，Research on the ionosphere of our country[J]. Chinese Journal of Geophysics.41:51-73.1994.[梁百 先.李钧.冯淑英，我国的电离层研究.地球物理学报[J].41(增刊):51-73.

[2] Zhang Shunrong,Huang Xinyu. Oscillations of plasma drifts in ionosphere[J]. Chinese Journal of Geophysics.37:10-16 .1995.[张顺荣. 黄信榆.苏元智．电离层等离子体漂移的振荡．地球物理学报[J]. 37:10-16 . 1995.]   
[3] M. Lester,P.J. Chapman,S.W. H. Cowley,Stereo CUTLASS - A new capability for the SuperDARN HF radars. Annales Geophysicae (2004) 22: 459-473 $\circleddash$ European Geosciences Union 2004.   
[4] K. McWilliams,D.Andre,R.Greenwald,A. Schiffler, G. Sofko,T. Yeoman,SuperDARN Pulse Sequences - Optimizat ion and Testing,a tutorial presented at the SuperDARN 2003 meeting.   
[5] Yan jingye, Lan ailan.Project report for AgileDARN radar[R].Bei jing,NSSC.[阎敬业.蓝爱兰等.AgileDARN雷达的项目报告[R]．北京： 中国科学院国家空间科学中心.]   
[6] Zhang Guanyi.Phased array radar system[M].Bei jing,National Defence Industry Press.1994[张光义.相控阵雷达系统[M].北京:国防工 业出版社.1994.]   
[7] AS Yukimatu,M Tsutsumi. a new SuperDARN meteor wind   
measurement: raw time series analysis method and its application to mesopuase region dynamics.Geophy Re.29(29):42-1-42-4.2002.   
[8] Farley,D.(1972),Multiple-pulse incoherent-scater correlation   
function measurements, Radio Sci.,7(6), 661-666,   
doi:10.1029/RS007i006p00661.   
[9]Dick Blandford.John Parr.Introduction to Digital Signal Processing[M].2015.[陈后金等译．数字信号处理及MATLAB 仿真[M]. 北京:机械工业出版社.2015.]   
[10] Sun Yaoqi, Gao Huotao. Design and Implementat  
ion of FIR Digital Filter Based on Matlab and FPGA[J].Modern Electronics Technique,11:89-92.2008.[孙耀奇,高火涛等．基于 Matlab 和 FPGA 的 FIR 数字滤波器设计及实现[J].现代电子技术.11:89-92. 2008.]   
[11] Xilinx.FIR Compiler v7.2 LogiCORE IP Product Guide.[DB/OL]. PG149 November   
18,2015.http://www.xilinx.com/support/documentation/ip_documentatio n/fir_compiler/v7_2/pg149-fir-compiler.pdf   
[12]Liu Donghua.IP core of Xilinx series FPGA chip[M].Bei jing. Electronic Industry Publishing House.2013[刘东华.Xilinx 系列 FPGA芯 片 IP 核详解[M].北京：电子工业出版社.2013.]   
[13] Yang Tanxue,XuChungang,Li Shuang.Digital beam forming for Ultrasonic Phased Array based on FPGA[J].NondestructiveTesting.11.30:813-815.2008.[杨天雪,徐春广,李 爽.基于FPGA的超声相控阵波束合成技术[M].无损检 测.11.30:813-815.2008.]

# 第一作者简介：

蒋松（1990.5—），男，河北省邯郸市人，硕士研究生。研究方向：数字信号处理，雷达数字系统。E-mail：jasonjs2013 $@$ 163.com  
课题负责人：  
阎敬业（1972.4—），男，黑龙江省佳木斯市，博士，博士生导师。研究方向：有源及无源微波遥感理论及系统研究。  
E-mail: yanjingye@mirslab.cn