# 德令哈毫米波望远镜本振谐波干扰问题

李振强，张旭国，李积斌，张海龙，孙继先(1.中国科学院紫金山天文台 青海观测站，青海 德令哈8170002.中国科学院射电天文重点实验室，江苏 南京210008)

摘 要：射电天文中，射频干扰问题多样而复杂，面对不同的射频干扰问题，针对不同的干扰机制，采用针对性的方法。从器件阶段消减射频干扰，可以预防射频干扰进入望远镜内部。介绍了德令哈毫米波望远镜9波束边带分离型超导接收机，1个本振链路系统分配18路本振信号方案，针对本振链路中信号发生器的谐波信号引起的中频窄带干扰，设计了注入模拟谐波信号的测试方案，确认了干扰产生机制并得出了谐波信号频率与干扰信号的频率和功率的对应关系，分析并验证了谐波干扰传输路径。为了消减谐波干扰，利用YIG滤波器的可变频段的带通特性，在本振链路上滤除谐波信号，防止谐波信号耦合到接收机系统，完成了谐波干扰的消减。

关键词：干扰消减；射频干扰；谐波信号；超导成像频谱仪中图分类号：P161.4 文献标识码：B 文章编号:

# 0引言

1932年，Jansky探测到天文物体的无线电波，发现了来自银河系的辐射，射电天文由此开始并快速发展，丰富了天文学的整体研究[]。之后，许多不同的无线电发射源，包括恒星和星系，以及全新的天体类别，如射电星系、类星体、脉冲星和脉泽源等，被射电天文观测到。通过射电天文发现的宇宙微波背景辐射是宇宙大爆炸理论的重要依据[2]。

毫米波射电是观测研究宇宙各层次结构和演化的一个重要波段。随着相关技术的出现，毫米波射电是上世纪七十年代才逐渐发展起来。我国在国际上起步较早，上世纪八十年代初就部署研制了国内唯一的大中型设备德令哈13.7米毫米波望远镜，也是迄今为止国际上少有的中型设备[3]。自1996年该望远镜3毫米波段接收机建成使用以来，已经完成了两百多个天文研究课题，取得了一系列重要的天文发现。如北京大学吴月芳教授主持的对普朗克致密冷核的分子气体进行多谱线观测研究，完成国际上首个普朗克冷尘块谱线巡天，在多个天文期刊上发表了一系列文章[4-。紫金山天文台孙燕博士等利用德令哈望远镜的“银河画卷”C0巡天发现了72个远距离的星际分子云，这些分子云的空间分布勾画出了银河系的这段新旋臂。这段分子旋臂位于银河系已知的“外旋臂”之外更远位置上，是迄今为止探测到的离银河系中心最远的旋臂[8]。

1998年，该望远镜安装了以我国为主研制的超导SIS(超导-绝缘体-超导)接收机并且投入了实际天文观测，极大地提高了微弱信号的探测灵敏度，为当时我国超导技术应用最成功的例子之一[9。2002年，“3毫米波段多谱线系统”完成研制并投入使用，使13.7米毫米波望远镜单次的观测带宽得到了极大地延展。2010年，该望远镜装备了9波束边带分离型超导接收机--超导成像频谱仪。2011年自主开发了适合自身的OTF（On-The-Fly）观测方法[10]。OTF观测方法是一种应用于单天线成图观测的技术，观测时天线以恒定的速率对指定的区域进行扫描，多个采样点测量数据共用1个参考点测量数据和黑体测量数据进行校准，后端数据被频繁读取以避免波束污染，极大地减少了天线的摆动时间。超导成像频谱仪和OTF观测方法的应用，极大地提高了望远镜的观测效率。用时40分钟得到的区域成图图像，如果采用原有的单像元系统，覆盖同样的区域，采用逐点扫描方式得到质量接近的结果则需要700

射频干扰现象20世纪80年代在射电天文研究中开始出现，目前，射频干扰已经成为射电望远镜无法回避的问题。在国内的射电天文研究中，针对射频干扰建立测试条件和相关消减方法的研究一直在进行[11-12]。德令哈13.7米望远镜工作在毫米波段，该频段的外部干扰源极少，射频干扰基本是来源于中频频段的干扰[13]。然而在对干扰频谱分析时，发现有一类极窄带宽的固定频率（仅在本振频率变化时才出现变化）干扰谱同时出现在9个波束的18路中频输出上，测试结果显示该窄带干扰谱来自接收机的内部。本文对该窄带干扰谱产生机制及干扰传输路径进行探讨和分析，并采用针对性的措施消减这一干扰。

# 1窄带干扰频谱及干扰引入机制

目前，德令哈13.7米望远镜采用“超导成像频谱仪”这一多波束接收机进行天文观测。超导成像频谱仪有3个特色：超导SIS混频器，边带分离特性，9波束同时观测。超导SIS混频器构成的超导SIS接收机比传统的半导体萧特基型接收机的灵敏度提高了8-10倍，极大地提高了微弱信号的探测灵敏度。边带分离可以减少望远镜的系统噪声，提高观测数据的校准精度，减少可能出现的上下边带信号的谱线重叠问题。一台天线配备一个接收单元的单点铅笔束扫描方式限制了在空间上实现大范围的观测覆盖，在空间上同时进行多点接收的“成像”探测器可以提高空间覆盖的能力，9波束同时观测相较之前单波束观测，等于增加了8个望远镜。超导成像频谱仪前端采用9像元的焦平面阵列，每个像元的核心由边带分离型超导混频器构成。85-115GHz的输入射频（RF）信号经混频器变频到2.64GHz/带宽1GHz的中频（IF）信号后经过4K温度下低噪声放大器的放大和50K温度下的第二级放大器的放大后输出，这一部分工作在高真空、低温环境下杜瓦（Dewar）内部。前端输出的中频信号经后端的中频模块处理后输出18路0.5GHz/带宽1GHz的基频信号（经中频模块第二次混频后，在中频模块输出端输出的信号称基频信号）。基频信号由快速傅里叶变换频谱仪（FFTS，Fast Fourier transform spectrometer）实时处理，FFTS频谱处理的瞬时带宽是1GHz，共16384个通道，频率分辨率是61KHz。

1个边带分离型超导混频器（2SB SIS mixer）包含2个双边带SIS混频器（DSB SISmixer）。超导成像频谱仪需要18路本振信号，而这18路本振信号是由1个本振信号和功分器提供。本振链路及其到边带分离型超导混频器的连接示意图见图1。信号发生器是Anritsu公司生产的MG3692B型号产品。倍频器和放大器是一体器件，型号为AFM-x6-110,由德国Radiometer Physics GmbH公司生产。本振信号经1个一分三功分器分为3路，再经过3个相同性能的一分三功分器将本振信号分成9路。图1中显示了1个一分三功分器，边带分离型超导混频器内部包含1个一分二功分器，将1路本振信号分成2路供2个双边带SIS混频器使用。4个一分三功分器和9个边带分离型超导混频器最终完成了1路本振信号分成18路的功能。本振信号工作在3毫米波段，这里采用信号发生器和倍频器的模式代替之前的Gun式振荡器，实现本振频率调整的自动化，减少了调整本振频率的时间。单个双边带SIS混频器仅需要0.1uW的本振信号便可驱动其混频，过高或过低的本振功率均会增加混频器引入的噪声。在倍频器和放大器后增加电调衰减器，自动控制本振信号的输出功率供混频器使用。

在超导成像频谱仪投入到天文观测时，在18路的基频谱线上有一个固定频率的窄带干扰。如图2中左图所示，本振频率为88.8GHz时，由FFTS处理得到的窄带干扰频率在8539通道处，对应基频频率为0.521GHz，变换到中频频率为2.619 GHz。该窄带干扰信号带宽仅占一个通道。当关闭本振输出时，该窄带干扰消失。当改变本振频率时，该窄带干扰的频率会随之变化。本振频率与中频端的窄带干扰频率对应关系图见图2右图。

MG3692B信号发生器为本振链路中使用的信号发生器，输出信号频率为14.8GHz时，用AgilentE4407B频谱仪直接测试输出信号的谐波。谐波信号图见图3，通过分析各谐波信号和主信号频率可知，主信号由基频信号的17倍频得到，而基频信号的其他次谐波信号同样存在，与主信号功率差70dB以上，虽然谐波信号功率已经符合或低于产品说明书的要求，但对于更为灵敏的超导接收机而言，其信号仍可能被检测到。当主信号频率改变时，谐波信号频率同样发生改变。基本确定窄带干扰是来源于信号发生器的谐波信号。

![](images/fd22b7e1735f1483edb580d60259841de48469a1856b0c140a7988f828626d14.jpg)

图1上图是本振链路及其到边带分离型超导混频器的连接示意图。下图是器件实物图，分别为：倍频器和放大器模块、一分三功分器、边带分离型超导混频器。

![](images/0ba4ceda67176112d104093cd99986d93b5835c2f3e6c5c709f37399df28caa6.jpg)  
Fig.1Theupperfigure is theLOchainanditsconnectiondiagramtoSBSISmixer.Thelowerfigureisthephotosof thedevices: frequency multiplier and amplifier module,the one-to-tree power divider and the 2SB SIS mixer.   
图2左图：本振频率 $8 8 . 8 \mathrm { G H z }$ 时，FFTS 得到的窄带干扰谱线。右图：本振频率与中频端的窄带干扰频率对应关系图。 Fig.2Left figure: the narrowband interference line obtained by FFTS when LO frequency was $8 8 . 8 \mathrm { G H z }$ .Right figure: the frequency correspondence diagram of LO and the narrowband interference at IF port.

为了进一步验证该窄带干扰来源于本振链路中信号发射器的谐波信号和分析研究其产生机制，设计了如图4所示的测试方案。1号信号发生器是MG3692B，输出本振信号倍频前的主信号，输出的信号功率为5dBm，频率是14.8GHz，经6倍频后频率为88.8GHz，为本振信号。2号信号发生器是MG3692C，用于模拟谐波信号，输出2-10GHz频段内不同频率的信号，功率为0dBm，经衰减器10 dB衰减后通过合成器注入到主信号中，最终参与与主信号之间的各种倍频及混频关系。杜瓦部分省略了内部器件（见本章节第一段的介绍），其输出端是中频信号端，接E4407B频谱仪，主要测试1.8-3.2 GHz频段（2.14-3.14 GHz频段的一定范围的展宽）对应于的模拟谐波信号的中频干扰信号的功率和频率。当2号信号发生器模拟的谐波信号输出打开时，记录频谱仪观测到的干扰信号频率和功率，当2号信号发生器模拟的谐波信号输出关闭时，频谱仪观测到的该干扰信号消失。然后改变2号信号发生器模拟的谐波信号频率，进行其他频率点的测试。

![](images/d39abb7d60c8e13dcaee5a5e01ea6011158505037461d2e2aaae300a6524ed14.jpg)  
图3频谱仪测试到的信号发生器的主信号和谐波信号 Fig.3 The main and harmonic signals of signal generator tested by spectrometer   
图4通过注入模拟的谐波信号，测试谐波信号干扰机制 Fig.4The harmonic signal interference mechanism test diagram by injecting asimulated harmonic signal.

1号 同轴线  
信号发生器 频谱仪合路器 ×6 波导 网 杜瓦中频  
信号发生器 NN 倍频器 放大器 电调衰减器 输出衰减器

图5是谐波信号频率与相对应的中频干扰的频率和功率的关系图。可以看出模拟谐波信号在2-20 GHz频段内任一信号均能在1.8-3.2 GHz频段引起相应的中频干扰，只是部分干扰信号太弱，无法检测到。在检测到的信号中，不同频段引入的频率对应关系不一致，且干扰信号强度在不同频段有很大差别。我们将测试到干扰的频段分为11个频段区域分别分析。这里先定义主信号频率 $F _ { S } { = } 1 4 . 8$ GHz， $F _ { \mathrm { H } }$ 为模拟的谐波信号频率， $F _ { \mathrm { I F } }$ 为中频干扰的频率。表一给出了11个频段区域的谐波信号频率与中频干扰的频率关系式。谐波信号和主信号，在倍频器的作用下，均产生了多次谐波。当谐波信号和主信号的任意次数谐波混频（倍频器工作在非线性区时有混频效应）后的信号频率在1.8-3.2GHz范围内时，该信号将以中频干扰形式出现。而引起强功率干扰的信号是谐波信号自身、谐波信号与主信号的直接混频，即第1、8、11频段，其他频段由谐波信号的再次谐波或主信号再次谐波后互相混频产生的中频干扰功率较弱。

在倍频器内部已经产生了与中频干扰频率相同频率的信号，在初始阶段我们认为该信号是通过导体或地线直接耦合到杜瓦内部，然后被中频器件直接耦合进入接收机。为了验证这一猜测是否正确，我们进行如图6的测试。将本振链路系统与接收机系统完全独立隔离，将本振链路的供电端的地线断开，使得本振链路系统处于浮地状态，隔断了本振链路系统与接收机系统的地回路。在本振链路系统中断开本振波导，采用2个喇叭耦合来传输本振信号，隔断了本振链路系统与接收机系统的导体连接。测试结果显示，采样这一方式后，中频端相应的窄带干扰仍然存在，排除了该窄带干扰是通过导体或地线直接耦合杜瓦内的可能性。确认了该信号是通过波导传输到边带分离型超导混频器后经再次混频出现的。由于波导具有低频信号的截止特性，该信号在倍频器上被本振信号调制到高频后，可通过波导传输，到达边带分离型超导混频器后被混频器再次解调后出现在中频输出端，完成了窄带干扰信号的传输。

至此，谐波干扰机制已经明确：本振链路的谐波信号在倍频器上和本振信号倍频前的主信号自身或再次谐波后混频，再次被本振信号调制后，可通过波导进入边带分离型超导混频器，在边带分离型超导混频器上被再次解调后在中频端出现。而产生强功率干扰的频段也完成了定位。

114.8GHz  
3.2 上 ★★ ★ ★ ... .. ★ ... ★ .....\*.\*.\*.\*.\*.\*...\*\*..\*...\*\*.\*.\*.\*. ★ "\*· ★★★ ★ \*..\* ★ .11\*  
2.6 ★★ ★ ★★ ★ ★ ★★  
24 ★★ ★ ★★ ★ ★ ★★★ ..\*...\*★ ★ ★ ★ ★ ★ ： ★★ ★ ★ ★ ★★ ★ 中 ★ 童 ★ ★ ★ ★上 .. ...\*\*\*.\* ★ ............ .\*...\*.. .......··.. ★★ ★  
1.8 E ★ ★ 一 1 \*\* \* ... 10 ..2. 1....1 4 .… ...。.. .. 8 ..\*..\* R 12 .... 14 16 18 20  
-301 ..... 2 34 5 6 ...... 7 Muu 1 1  
? L 81 山1EE 三二三 .... ....\*\*.\*\*.\* .\*.\*\* ...... 1  
-70 ..\*. 善 = ..\* 1i ： 1 10 2 4 6 8 10 12 14 16 18 20谐波信号频率/GHz

表111个频段区域的谐波信号频率与中频干扰的频率关系式 Tab.1 The relational expression between harmonic signal frequency of 1 frequency bands and the frequency of IF interference

<html><body><table><tr><td>频段区域</td><td>1</td><td>2</td><td>3</td></tr><tr><td>频率对应关系 频段区域</td><td>FIF=FH 4</td><td>FIF =Fs-3×FH 5</td><td>FIF =-Fs+3×FH 6</td></tr><tr><td>频率对应关系 频段区域</td><td>FIF=Fs-2×FH</td><td>FIF =-Fs+2×FH</td><td>FIF =2×Fs-3×FH</td></tr><tr><td>频率对应关系</td><td>7 FIF=-2×Fs+3×FH</td><td>8 FIF=Fs-FH</td><td>9 FIF=2×Fs-2×FH</td></tr><tr><td>频段区域 频率对应关系</td><td>10 FF =-2×Fs+2×FH</td><td>11 FIF =-Fs +FH</td><td></td></tr></table></body></html>

![](images/b0492d7aca6033bba9509efaba8037d060dc9510145b3112dc2fd8d0daa31c64.jpg)  
图5 谐波信号频率与中频干扰的频率和功率的对应关系 'ig.5 The Correspondence between the frequency of harmonic signal and the frequency and power of $\mathrm { I F }$ interference   
图6在本振链路系统中断开波导，采用喇叭耦合方式传输本振信号 ig.6The waveguideisdisconnectedandtheLOsignalistransmitedbycouplingbetweenhornsattheLOchainsystem

# 2 谐波干扰消减

通过之上实测及分析验证，我们认识到窄带干扰的产生机制及耦合路径。由于超导成像频谱仪工作在85-115GHz频段，本振频率也是在这一频段内变化，因此需要1个可调整中心频率的窄带滤波器对信号发生器产生的谐波信号进行滤除，显然，在本振信号倍频前滤除谐波信号更容易实现。我们通过中国电子科技集团公司第九研究所定制了一款可自动化设定中心频率的窄带带通YIG（YtriumIron Garmet，钇铁柘榴石）滤波器。YIG滤波器型号为ZLT1020-1A，图10左上图是实物图，右上图是中心频率为14.01GHz时传输系数（S21），该频率下-3dB带宽为32MHz，插入损耗为-4dB。将该滤波器放置在本振链路系统的信号发生器和倍频器之间，位置见图10下图，从图中可以发现，信号发生器产生的信号经过YIG滤波器后，谐波信号在-3dB带宽外，可以很好地被滤除，主信号经滤波器衰减约4dB，完全可以通过改变信号发生器的输出功率来调整。YIG滤波器整体性能描述如下：工作频率范围 $1 0 { - } 2 0 ~ \mathrm { G H z }$ ，带外抑制40dB以上，-3dB带宽为 $3 2 { - } 3 8 ~ \mathrm { M H z }$ 。工作温度范围：-50到$+ 7 0$ 摄氏度。采用RS232协议和计算机通信来设置参数，中心频率可控制步长 $2 . 5 ~ \mathrm { M H z }$ 。工作电源电压 $+ 1 5 \mathrm { V }$ 和-5V，采用 $+ 2 4$ V电源单向加热进行简易的恒温控制，扩展在低温环境下的工作。

![](images/a92aa9befdae2c4dd1dc7cbff3ef68ecd80466133ae5b7151b60b7f1e2257c03.jpg)  
图10左上图是YIG滤波器。右上图是中心频率为 $1 4 . 0 1 \ : \mathrm { G H z }$ 时的滤波器的传输系数。下图是YIG滤波器的安装位置图 Fig.10TheupperleftfgureistheYIGfier.Thupperightfigureshowsthetransmissoncoeicientsoftefilterwhentecentral frequency is 14.O1 GHz.The lower figure shows the installation position of the YIG filter.

在YIG滤波器安装前后，我们在基频输出端使用FFTS测试了频谱图，LO频率 $8 8 . 8 ~ \mathrm { G H z }$ 未使用YIG滤波器前有明显的三条谐波干扰谱线，见图11的黑色曲线。当使用YIG滤波器后，三条谐波干扰谱线消失，见图11中的红色曲线。证实了YIG滤波器能很好的消除谐波信号引入的干扰。

# 3结论

分析研究谐波干扰的产生机制和耦合路径是谐波信号消除的基础，这里主要介绍了这一方面的内容，在此基础上针对性采用了合适的干扰消减方案，并最终解决了谐波干扰问题。YIG滤波器的引入很好地消减了谐波干扰，但也引入了新的问题：作为一个有源器件，其稳定性比无源器件的差。因此，在后期的工作中，YIG滤波器的输出信号的稳定性需要开展进一步的研究工作。

![](images/dc3a027148a1b2ba1988a780f1c404fdfc709d418dc5eab7ae50011b5a1337f2.jpg)  
图11YIG滤波器安装前后，基频输出的频谱图对比 Fig.11 The spectrum comparison of baseband output between before and after the installation of YIG filter

# The harmonic interference problem of LO in Delingha mm wave telescope

LI Zhen-qiang, ZHANG Xu-guo,LI Ji-bin， ZHANG Hai-long， SUN Ji-xian (1.Qinghai station,Purple Mountain Observatory,Chinese Academy of Sciences,Delingha 817ooo,China 2．Key Laboratory of Radio Astronomy,Chinese Academy of Sciences,Nanjing 21oo08,China)

Abstract: In radio astronomy,the problem of RFI(radio frequency interference) is various and complex.In the face of different RFI problems and interference mechanisms,the pertinent methods are adopted. The RFI mitigation at the device stage can prevent RFI from entering the telescope.A 9-beam sideband separation superconducting receiver for Delingha millimeter-wave telescope is introduced.18 LO signals are allocated by a LO(local oscillator) chain system. Aiming at the IF(Intermediate frequency) narrowband interference caused by the harmonic signal of the signal generator in the LO chain,a test scheme of injecting simulated harmonic signal is designed. The interference mechanism, the correspondence between the frequency and power of interference signal and the frequency of harmonic signal are confirmed.The transmission path of harmonic interference is analyzed and verified.In order to mitigate harmonic interference,the YIG filter with band-pass characteristic of variable frequency band is used to filter out harmonic signal in the LO chain system. The harmonic signal is prevented from coupling into the receiver system and the mitigation of harmonic interference is completed.

Key words: interference mitigation； RFI(radio frequency interference)； harmonic signal; SSAR(superconducting spectroscopic array receiver)

# 参考文献：

[1]Amold Steven.Getting started inradioastronomy[M]//The historyofradioastronomy.NewYork: Springer,2014:3-5.   
[2] 杨戟.中国射电天文的研究与发展[J].中国科学院院刊,2011,26(5):511-515.   
[3]杨戟,曹凝.超导成像频谱仪[J].中国科学院院刊,2011,26(4):478-481.   
[4] Wu YF,Liu T,Meng FY,et al.Gas emissions in Planck cold dust clumps-A survey of the $scriptstyle { \mathrm { J } = 1 - 0 }$ transitions of 12CO, 13CO,and C18O[J].Astrophysical jourmal,2012,756(1): 76.   
[5]LiuT,WuYF,ZhangHW.Molecularenvironmentsof51planckcoldclumps intheorioncomplex[J].The Astrophysical Journal Supplement Series,2012,202(1):4.   
[6] MengF,WuYF,LiuT.Mapping studyof71planckcoldclumps inthetaurus,perseus,ndcaliforniacomplexes[J].The Astrophysical Journal Supplement Series,2013,209(2),37.   
[7]LiuT,WuYF,Zhang HW.Gaseous co abundance-an evolutionary tracer for molecular clouds.The Astrophysical Journal,2013,775(1):L2.   
[8] Sun Y,Xu Y,Yang J,etal.Apossble extensionof the scutum-centaurus arm into theouter secondquadrant.The Astrophysical Journal,2014,798(2):L27.

[9] 单文磊，史生才,杨戟,等.3毫米波段9像元超导接收机前端[C]./中国电子学会微波分会.2009年全国微波毫米波会议论文集（下册）.贵州：中国电子学会微波分会，2009:1205-1207[10]孙继先,逐登荣,杨戟,等.德令哈 $1 3 . 7 \mathrm { m }$ 望远镜谱线OTF观测系统[J].天文学报，2018，59(1):24-35[11]胡浩,张海燕,甘恒谦,等.FAST工程综合测试微波暗室设计与实现[J].天文研究与技术,2018，15（4）:487-494.[12]朱世宇,王壮,王梦南,等.基于多项式模型的射电天文中的移动干扰消除[J].天文研究与技术,2017,14(3):297-303.[13]李振强,李积斌,张旭国,等.德令哈 $1 3 . 7 \mathrm { m }$ 望远镜接收机抗射频干扰研究[J].天文学报，2019，60(3).