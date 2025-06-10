# NVST偏振观测系统的运动控制实现

覃瑛，彭建国1,²，张涛1，侯俊峰，顾伯忠4，许骏1(1.中国科学院云南天文台，云南昆明 650011；2.中国科学院大学，北京100049;

3.中国科学院国家天文台，北京100012;

4.中国科学院国家天文台南京天文光学技术研究所，江苏 南京 210042)

摘要：云南天文台的1m新真空太阳望远镜（NewVacuum Solar Telescope，NVST）是我国在太阳物理和空间科学对太阳进行光学和近红外观测的主力设备，主要科学目标是高精度、高时空分辨率的太阳磁场测量。NVST采用机械扫描偏振观测方式，由于其光学系统的结构特性导致望远镜在跟踪太阳的过程中不可避免地引入了随时间变化的偏振效应，因此在进行偏振观测时需要进行系统定标，整个系统由定标单元、分析单元和探测器组成，其间涉及的多个运动部件均有复杂精密的运动要求。针对偏振定标过程和偏振观测过程中各光学器件的运动需求，给出了定标单元和分析单元的控制要求，实现了不同观测模式时各部件的运动要求。基于TCP/IP协议的远程控制方案，集成了采用串口通讯的各商用驱动控制器，开发了一套在.NET架构下的定标单元控制软件和相应的用户界面，并预留了OCS接口。性能测试表明，系统符合实际观测要求，现已投入使用，为后续的偏振观测奠定了基础。

关键词：偏振观测；定标单元；控制方案；远程控制中图分类号：P111.33；TP311.5 文献标识码：A文章编号：1672-7673(2018)

在浩瀚的宇宙中，太阳是与人类关系最为密切的天体，也是人类可以深入研究的最近的恒星。不同起源的磁力线纵横交错地存在于太阳大气中的各个部分，磁场活动在太阳大气的结构演化中占据主导地位2。为了能够更为深入地了解和研究太阳活动的物理机制，国内外许多天文台站和研究机构将磁场测量作为重要的研究目标。比如美国大熊湖天文台的新太阳望远镜（New Solar Telescope，NST），日本的无圆顶望远镜（Domeless SolarTelescope，DST）[3]，瑞典1m太阳望远镜（Swedish Solar Telescope，SST）[4]，以及德国的1.5 米太阳望远镜（GREGOR Solar Telescope）{5-等都可用于太阳磁场的精细结构观测，并且取得了显著的成果。国家天文台怀柔观测站的太阳磁场望远镜以及云南天文台的太阳斯托克期(Stokes)光谱望远镜也都在太阳磁场的偏振测量方面做出了突出贡献。

1m新真空太阳望远镜在建立之初就将太阳活动区磁场的高分辨率光谱观测作为重要的科学目标。目前已实现了基于光谱仪的偏振光谱观测，正在进行基于窄带滤光器的二维高分辨磁像仪的研制。无论是偏振光谱观测还是二维磁像仪，其偏振测量都受到望远镜系统的调制，因此需要对望远镜系统进行偏振定标[10-11]。

1m太阳望远镜采用地平式结构，光学系统为修正格里高利系统，在 $F _ { 2 }$ 焦点之后使用了多面反射镜进行折轴，如图1。望远镜在跟踪太阳的过程中，这组反射镜（即图1中 $M _ { 3 } , M _ { 4 }$ 、$M _ { 5 \setminus M _ { 6 \setminus M _ { 7 } } }$ 部分）之间的相对方位角度随望远镜的高度角和方位角的变化而改变，给望远镜系统引入随时间变化的偏振效应。要得到太阳活动区观测目标每一时刻真实的偏振光谱，就需要在望远镜对称光路中安装一套偏振定标单元（CalibrationUnit）实时定标，结合NVST偏振观测系统的实际工作环境，定标单元采用了基于TCP/IP的远程控制方式。

![](images/f9fee8bd10b4b1bfd4b3a5da759d72eb6e57bce3ae0df96baae5c02615eeb5ef.jpg)  
Fig.1 The optical system of NVST

# 1偏振观测系统的总体设计

目前在天文实测领域，对于太阳磁场的测量主要还是依托于太阳光谱线的塞曼（Zeeman）效应，通常采用斯托克斯（Stokes）参量阐释太阳磁场产生的偏振状态[12]。1m太阳望远镜偏振观测系统按功能可分为定标单元和分析单元两部分，对太阳进行偏振观测时定标单元切出光路，分析单元工作；对系统进行定标时，定标单元切入光路，配合分析单元共同获取校正矩阵，校正观测误差。根据偏振观测系统的总体设计，分析单元放置在仪器平台上的 $F _ { 3 }$ 焦点附近，定标单元放置在1m太阳望远镜真空主镜筒内的 $F _ { 2 }$ 光学焦点处，如图1，除自身工作时的运动外，分析单元和定标单元还随光谱筒和望远镜整体运动。因此，两个单元的控制信号及供电设计变得较为复杂。

此外，对于定标单元，无论是切入工作状态还是切出光路，都不能遮挡光路，破坏光路的对称性，在机械结构上需要优化相应设计。

# 2定标单元和分析单元的运动方案

定标单元用于发生偏振态已知的偏振光，主体部分需要由一台步进电机控制以实现切入工作状态和切出光路两种模式，如图2。为了配合观测中对视场大小的不同需求，在 $F _ { 2 }$ 焦点处安装一个可调节的视场光阑，并由单独的步进电机控制切换观测视场的大小。

图1NVST光学系统  
图2定标单元工作状态示意图  
![](images/ba6fe62cb8b437e5b97de8d266a32a0300e02e929e445f109e51cd6a028011e7.jpg)  
Fig.2 The working status of the calibration unit

定标单元采用一片1/4波片和一片反射式偏振片构成偏振发生器，波片和偏振片应分别安装在两台独立的带有通孔的超声波电机上，按照光学要求通过两台电机带动旋转，组合产生定标所需的6组已知状态的偏振光（ $_ { \mathrm { I \pm Q } }$ 、 $\mathrm { I \pm U }$ 、 $\mathrm { I } \mathrm { \pm } \mathrm { V }$ ），在望远镜 $F _ { 3 }$ 焦点处使用偏振分析器对经过望远镜折轴镜组后的偏振光进行测量。

偏振分析器由一片可旋转的延迟量为 $1 2 7 . 8 ^ { \circ } @ 5 3 2 4 \mathrm { \AA }$ 的波片和一片位置固定的偏振片组成，波片的旋转也由中空超声波电机直驱，实物如图3。理论上，不同的波片位置的测量强度应具有对称性，但在实测中结果存在一定的差异。因此，偏振分析器只使用0至180度进行测量，在完成一组偏振测量后，为了避免由不对称性带来的测量误差，电机应旋转回到光学0点再开始下一组测量。目前采用该方式唯一的不足是造成了大约 $5 0 0 \mathrm { { m s } }$ 的额外设备运行时间耗损。

![](images/f9b846935fd5584f6b94b18b9e955179a73ef148b706fa391396643707cb0ff4.jpg)  
图3偏振分析器  
Fig.3 Polarization analyzer

定标观测时，定标单元共需组合81种状态，这些状态是冗余的，用以提高精度；在定标单元组合的每组偏振状态下，偏振分析器中的波片旋转8个位置，并对每个位置下的光强进行测量，根据定标单元产生的已知状态偏振光和偏振分析器的测量结果可计算出望远镜系统在此高度角和方位角下的偏振特性（即Mueller矩阵），从而校正偏振光谱观测中的主要误差[13]。由于高度角和方位角的组合关系随观测时间和季节变化，因此这一过程需长期重复。

# 3控制系统设备介绍

定标单元的控制系统总体可分为3部分，分别是上位机、控制机箱以及驱动电机。经过对定标单元的需求分析和资料调研，采用超声波电机和步进电机作为定标单元主体工作部件的驱动电机。定标单元安装在望远镜真空主镜筒内，通过真空插头与控制机箱有线连接，为了保证控制指令的正确传输，控制机箱应放置在望远镜镜筒旁。定标单元、分析单元和上位机放置在不同地方，不在同一工作现场，为了使整个子系统同步协调工作，上位机和控制机箱之间使用太阳塔的局域网进行远程无线通讯，如图4是定标单元控制系统整体连接示意图。

分析单元的控制与此类似，但它不在真空环境中并且只有一个电机，本文没有给出详细描述，可参考定标单元的有关控制实现。

![](images/ca67589024a8b98d86dfc84edbf365465c963b4b59e3c29ad3c7e2054f6a2235.jpg)  
图4控制系统连接示意图  
Fig.4 Control system connection diagram

# 3.1超声波电机

超声波电机是以超声频域的机械振动为驱动源的新型驱动器。工作原理是利用压电材料的逆压电效应将电能转换为超声频段（频率为20KHZ以上）的微观机械振动，并将这种振动通过共振放大和摩擦耦合变换成运动体的直线或旋转运动。与传统的依靠电磁效应工作的电机相比，超声波电机具有无电磁干扰、起停控制性好、可直接驱动、控制精度高等优点，在航天航空、精密仪器仪表、微机电系统等领域得到了广泛运用。

驱动波片和偏振片旋转的电机为PI（PhysikInstrumente）公司生产的M-660.55V超声波电机。该电机为中空式的旋转结构，外直径为 $1 1 6 \mathrm { m m }$ ，中孔直径为 $3 6 \mathrm { m m }$ ，满足望远镜光束的尺寸要求；其次电机厚度为 $1 4 \mathrm { m m }$ ，满足光学设计对定标单元总体厚度的要求。电机重量为 $4 7 0 \mathrm { g }$ ，最高转速为 $2 \mathrm { r p m / s }$ ；通过实测发现，当电机角度定位误差为 $0 . 0 4 \%$ 引起 $6 . 2 5 \%$ 的测量强度起伏，因此，为了减小由于强度起伏引入的测量精度误差，电机的角度精度需远小于 $0 . 0 4 \%$ ，即角度偏差远小于0.01度，该超声波电机配有精度为34urad（ $0 . 0 0 1 9 5 ^ { \circ }$ ）的绝对码盘，符合定标单元的设计需求。

配套购置了厂家的运动控制器，该控制器采用RS232与上位机连接，定标单元控制上位机与超声波电机控制器之间基于厂家约定的通讯协议格式和控制指令通讯。

# 3.2步进电机

由波片、偏振片和超声波电机组成的定标单元偏振发生器主体工作部件，由电机驱动以实现切入工作状态和切出光路两种模式。可调节视场光阑由3个孔径分别为 $1 ^ { \prime } , 3 ^ { \prime } , 5 ^ { \prime }$ 的视场组成，在实际应用中需要根据观测需求切换。定标单元机构安装在望远镜的真空主镜筒内，工作环境温度较高且热密闭性较好，存在一定的散热困难，但是无论是控制切换光路还是控制切换视场光阑的电机，每次都只工作较短的时间，驱动负载不大，选择常规的步进电机即可，当然，线缆和润滑油需根据高温和真空环境选型。

步进电机具有动态响应性好、可靠性高的特点。结合定标单元的机械结构设计需求，选择国产的两款型号分别为42HS4813A4和20HS4006A4的两相混合式步进电机[14]驱动相应的设备。驱动控制器选择硕科数控的M4505A-I通迅步进控制驱动器，该驱动器内置超高性能运动控制器，功能完备，性能优良，支持RS232和RS485通讯。编写的上位机控制程序基于ModbusASCII通信标准，指令格式为：

“：设备地址 $^ +$ 功能代码 $^ +$ 数据长度 $+$ 参数 $^ { \cdot + }$ 校验码\r\n”。

由于定标单元机械结构的限制，切换光路主体机构的运动范围为（90±2）°，为了不损坏电机，同时又保证光路的正常入射，设计加入反馈环节与步进电机和驱动控制器组成闭环数控系统，综合机械设计的尺寸和系统性能要求选择JK8002D接近传感器开关，安装位置如图5。JK系列的接近开关是根据霍尔效应原理制成的新型自动化开关器件，特点为响应频率高、重复定位精度高、抗干扰能力强、可靠性高、使用寿命长，可以和PLC直接接口使用。

![](images/d8d646649b4bddcf66439a9dc33bbf7fcfee8ec3da41bbf3348f114af583d40e.jpg)  
图5霍尔开关安装示意图  
Fig.5 The hall switch installation diagram

为了提高偏振观测系统的时间分辨率，在切换光路主体机构的运动中，采用变速控制方式控制该步进电机，实现了10s以内即可完成切入或切出动作，具体运动方式为：当步进电机做切入运动时，以初速度Vstart开始运动，以加速度 $a _ { 1 }$ 后达到最大速度Vmax，Vmax做匀速运动，为防止转动件与固定件机械碰撞，霍尔开关的定位设计了少许提前量，为了满足光束的正常入射，当控制器接收到霍尔开关的反馈信号后还需再以固定脉冲数做匀速运动，到达预定位置，这种方式减少了可能的丢步等带来的累计误差；当电机做切出运动时忽略霍尔开关的反馈信号，以固定脉冲数依照先加速运动再匀速运动最后减速停止的模式控制。电机运动距离（即总脉冲数）经过多次实验后得到。

对于视场光阑切换电机，设定了快、中、慢3种匀速模式，选定后点击旋转方向即可实现切换。

# 3.3PC上位机

在硬件设备搭建完成的基础上，基于超声波电机控制器和步进电机驱动器的上层通讯协议以及C#.NET框架，上位机控制程序采用Visual Studio 2015软件编写。上位机系统分为通信设置、光路切换电机控制、视场光阑电机控制、超声波电机控制4个模块，并开发了Windows窗体形式的用户界面，如图6。用户只需选择并打开相应电机的控制串口号，就能根据实测需要对定标单元进行控制，结合观测软件得到用于校正偏振光谱观测中的主要误差。软件预留了OCS接口，该界面只用于目前的工作，未来OCS完成后，天文学家并不使用该界面。

![](images/81da5c2791863458405fd230228eb60d68dd87475ff3c2e30313b71547d33ea9.jpg)  
图6定标单元控制软件界面  
Fig.6 The software interface of calibration unit

# 4无线远程控制的实现

控制定标单元的超声波电机和步进电机通过真空插头与控制机箱内的控制器有线连接，并且各电机厂家建议上位机与控制器之间均通过RS232串口协议进行通讯。由于RS232通讯距离有限，同时，在运动中的望远镜和光谱筒上布线需解决拖缆问题，因此采用无线TCP/IP作为RS232的中继，这一方案同时解决了远程和拖缆问题。

有人物联网公司生产的USR-N540四串口服务器配有一个10/100Mbps以太网口，支持Auto-MDI/MDIX，交叉或直连网线均可使用，支持TCP Server，TCPClient，UDP，UDPServer，HTTPDClient多种工作模式，配合自带的虚拟串口软件（USR-VCOM），可虚拟4个与硬件端口号对应的独立工作、互不影响的串口，串口波特率范围为600bps\~230.4Kbps。采用该串口服务器作为介质，实现了上位机和各控制器之间的双向数据传输。

在物理连接方面，定标单元各电机的控制器均采用RS232接口，连接到USR-N540上，然后，USR-N540与无线路由器相连，并通过WIFI接入1m太阳望远镜观测楼控制局域网。这样，实现了上位机（位于三楼观测室）与定标单元的物理连接。图7为控制连接示意图。

在软件方面，USR-N540及与之相连的无线路由器被虚拟成上位机的四个串口，上位机位于观测楼控制局域网中，无线路由器采用固定IP，完成这些工作后，对定标单元的控制形式变成对这四个串口的操作，有关物理连接透明化。

针对1m太阳望远镜的网络架构，实现定标单元的远程无线控制的具体方式为：首先，将PC机接入局域网，在控制机箱内安装一个带无线中继的路由器，然后设置路由器将接收的wifi信号通过网线直接连接到串口服务器的以太网口，最后使用USR-VCOM软件虚拟所需的串口，通过串口连接线与控制器相连。PC机作为TCP客户端发起并建立网络连接，串口服务器作为TCP服务端监听端口，并通过自带的协议转换机制将TCP/IP协议转换为RS232格式，借由虚拟串口实现控制器与上位机之间的远程无线通讯。

通过多次实验发现，由网络通信造成的指令发送和接收的延迟平均在 $2 0 \mathrm { m s }$ 以内，同时在观测中并未发现由于网络延迟造成对仪器性能的影响，该无线远程控制方案切实可行。

# ChinaXiv合作期刊

![](images/45832336df084bf2c7d7fe2ae5ca857ac300619386c8364b127957c6c1bd8697.jpg)  
Fig.7 The wireless remote control connection diagram

# 5结束语

NVST偏振观测系统，特别是定标单元工作环境恶劣，加上有光学的、机械方面的约束，又有不能破坏光路对称性的要求，先后提出过两种大的技术路线，具体实施方案更多。经过几年的工作后，云南天文台于2016年8月27日在国家天文台和南京天文光学技术研究所的支持下合作完成了系统上镜工作，图8（a）为定标单元在真空主镜筒内的安装位置，（b）为定标单元与镜筒外控制机箱的连接位置。安装完成后，对整个偏振观测系统进行了实测，结果表明，使用定标单元控制软件可较为准确地切换光路，对超声波电机输入6组不同角度的偏振状态， $5 { \sim } 6 \mathrm { m i n }$ 即可得到一个Mueller矩阵，可以对 $1 5 \mathrm { m i n }$ 以内的观测数据进行校正，目前系统定标相对精度为 $\mathrm { l e } ^ { - 3 }$ 。定标单元的安装使用，是1m太阳望远镜偏振观测系统研制工作的重要进展，标志着1m太阳望远镜具备了高精度偏振测量所需的全部硬件基础。

![](images/4bdee25512eaf26d37b336c2c2e07cdb3f9aa5a46891be28b8ef272175958a40.jpg)  
图7无线远程控制连接示意图  
图8定标单元安装现场图  
Fig.8 The software interface of calibration unit

# 参考文献

[2]刘煜,张洪起,包曙东.太阳磁场观测研究[J].天文学进展,2001,19(1):34-44.   
Liu Yu, Zhang Hongqi, Bao Shudong. A research on observation of solar magnetic field[J]. Progress in Astron0my, 2001, 2001, 19(1):34-44.   
[3] Cao W, Gorceix N, Coulter R, et al. Scientific instrumentation for the 1.6m new solar telescope in big bear[J]. Astronomische Nachrichten,2010, 331(6): 636-639.   
[4] Van Noort M J, van der Voort,L. H. M. Rouppe. Stokes imaging polarimetry using image restoration at the Swedish 1-m Solar Telescope[J]. Astronomy & Astrophysics,2008, 489(1):429- 440.   
[5] Schmidt W, von der Lüihe O, Volkmer R,et al. The 1.5 meter solar telescope GREGOR[J]. Astronomische Nachrichten,2012, 333(9): 796-809.   
[6] Lagg A, Solanki S K, Doerr H P, et al. Probing deep photospheric layers of the quiet Sun with high magnetic sensitivity[J]. Astronomy & Astrophysics,2016, 596: A6-A18.   
[7] Bai X Y, Deng Y Y, Teng F, et al. Improved magnetogram calibration of Solar Magnetic Field Telescope and its comparison with the Helioseismic and Magnetic Imager[J]. Monthly Notices of the Royal Astronomical Society, 2014, 445(1):49-55.   
[8]梁红飞,苏同卫,赵海娟.太阳 Stokes 光谱望远镜的结构及其数据处理方法[J].天文研究与 技术—国家天文台台刊,2007,4(3):249-257.   
Liang Hongfei, Su Tongwei, Zhao Haijuan. Structure and data processing of the solar Stokes spectral telescope[J]. Astronomical Research & Technology Publications of National Astronomical Observatories of China, 2007, 4(3):249-257.   
[9] Liu Z, Xu J. 1-meter near-infrared solar telescope[C]//First Asia-Pacific Solar Physics Meeting ASI Conference Series.2011,2: 9-17.   
[10]Yuan S. Polarization model for the New Vacuum Solar Telescope[C]//APS Conference, 2014:297-304.   
[11]袁述.NVST偏振测量进展[R].陕西临潼:中国天文学会,2014.   
[12]邓林华.太阳小尺度结构的观测特征及物理机制的研究[D].北京：中国科学院大学（云 南天文台）,2014.   
[13]侯俊峰,王东光,邓元勇，等.基于非线性最小二乘拟合法的Mueller矩阵椭偏仪[J].中国 激光,2013,40 (4):179-186.   
Hou Junfeng， Wang Dongguang, Deng Yuanyong, et al. Muler mtrix ellipsometer based on nonlinear least squares fiting method[J]. Chinese Journal of Lasers, 2013, 40(4):179-186. [14]徐慎敏,罗建.基于DSP 的两相混合式步进电机细分驱动设计[J].机械工程与自动化, 2011 (2) :134-135+138.   
Xu Shenmin, Luo Jian. Design of two-phase hybrid stepping motor micro-stepping driver based on DSP [J]. Mechanical Engineering& Automation, 2011 (2):134-135+138.

# The Movement and Control Realization of NVST

# Polarization Observation System

Qin Ying1， Peng Jianguo1², Zhang Tao1， Hou Junfeng³， Gu Bozhong4,Xu Jun1 (1.Yunnan Observatories,Chinese Academy of Sciences，Kunming 65oo11, China;

2.University of Chinese Academy of Sciences，Beijing 1ooo49,China;

3.National Astronomical Observatories,Chinese Academy of Sciences,Beijing 10ool2,China;

4.Nanjing InstituteofAstronomicalOptics&Technolog,NationalAstronomicalObservatories,ChneseAcademyfcience

Nanjing 210042, China;)

Abstract: The new Vacuum Solar Telescope (NVST) is one of the most important solar observing systems,one of its main scientific goal includes high precision and high temporal resolution measurement of the solar magnetic field. NVST polarization analysis system should be precalibrated before observing,and, due to the structural characteristics of its optical system, NVST inevitably introduces a time-varying biasing effect during the tracking of the sun. Therefore, calibration of the system requires calibration of the system. The whole The system consists of a calibration unit, an analysis unit and a detector. A plurality of moving parts involved in the process have complex and precise movement requirements. This paper is aimed at the motion requirements of each optical component during polarization calibration process and polarization observation， gave the control requirements of the calibration unit and the analysis unit,and realized the movement requirements of the components in different observation modes. Based on TCP /IP protocol remote control program， integrated with serial communication of the commodity drive controller, the software is developed under the .NET architecture and set aside the OCS interface. System performance tests show that, in line with the measured application requirements,is now put into use, for the subsequent polarization observation laid the foundation.

Key Words: Polarization observation; Calibration unit; Control scheme; Remote Control