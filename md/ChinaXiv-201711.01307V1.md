# CN 53-1189/P ISSN 1672-7673

# 交流伺服系统在天文望远镜中的应用研究初探

张升华¹，黄垒²，魏建彦²，郑莉芳¹，刘奇³（1.北京科技大学，北京100083；2.中国科学院国家天文台，北京1002；3.中国科学院大学，北京 100049）

摘要：交流伺服系统在工业控制领域得到了广泛应用，但在天文领域的应用仍处于初级阶段。以中法合作天文卫星（Space multi-band Variable Object Monitor，SVOM）的地面观测设备地基广角相机阵(Ground-basedWide-Angle Camera，GWAC）为研究平台，研究了交流伺服系统应用于望远镜转台控制的可行性。测试了望远镜的跟踪速度控制精度、赤经跟踪精度、最大角速度、最大角加速度、重复指向精度等关键技术指标。测试结果表明，和步进电机系统相比，交流伺服系统在低速控制上具有同样高的精度。在高速控制领域，其调速范围更宽，速度调节更快，运行更平稳，具有明显的优势。另外，还具有低噪声、大转矩、高性价比等优点。实验中还测定了交流伺服系统对ApogeeCCD $\mathrm { { U 9 0 0 0 x } }$ 的干扰，结果表明，交流伺服系统对CCD的干扰很小，在可接受的范围内。总之，交流伺服系统完全可用于中小型天文望远镜的转台控制，特别适用于快速转动和指向的系统。

关键词：地基广角相机阵；交流伺服系统；关键技术指标；对CCD的干扰中图分类号：P111 文献标识码：A 文章编号：1672-7673(2017)03-0337-10

地基广角相机阵[1是由一系列宽视场望远镜组成的阵列，位于河北兴隆观测基地，整个系统预计建成2组，每组包括9个转台，每个转台装有4台广角望远镜，共36个，每台望远镜的口径为 $1 8 ~ \mathrm { c m }$ ，焦距为 $2 2 \mathrm { c m }$ ，视场为 $1 2 ^ { \circ } \times 1 2 ^ { \circ }$ 。地基广角相机阵样机如图1。视场大是地基广角相机阵最显著的特点,每个转台的视场为 $2 4 ^ { \circ } \times 2 4 ^ { \circ }$ ，9个转台的视场达到4500平方度，全部建成后，将成为世界上同类望远镜中综合视场最大的望远镜阵，它的主要科学目标是监测伽玛射线暴[2]和探测伽玛射线的瞬时辐射。

![](images/d5ffd3bb407979243b4174fb9157e17486a021d1fe8acd7e21a1bd6ebfdf823c.jpg)  
图1地基广角相机阵样机Fig.1GWAC prototype

地基广角相机阵具有传动比大、调速范围宽等特点，样机之前使用的是步进电机。步进电机虽然具有易于控制、成本较低等优点，但是也有不足之处，比如在低速时容易出现低频振动现象，启动频率过高或负载过大时易出现丢步或堵转现象[3]等。文中采用交流伺服电机，交流伺服电机运行平稳，低速时速度波动小，控制精度高，具有对多台电机进行同步或跟随控制的功能，特别是转矩与转速可以分别独立控制，适于复杂系统的控制要求。通过研究，开发一套基于交流伺服电机的伺服控制系统，比较交流伺服电机与步进电机性能的异同，测定交流伺服系统对CCD成像的干扰，为后续地基广角相机阵的控制提供技术积累。另外，兴隆观测基地是亚洲最大的实测光学天文研究基地，但还没有自主研发的交流伺服系统，本文的研究对交流伺服技术在望远镜控制上的应用具有参考意义。

# 1地基广角相机阵交流伺服系统的设计

# 1.1地基广角相机阵控制要求

根据《地基广角相机阵赤道式望远镜机架任务书》的要求，提出了地基广角相机阵的技术指标，如表1。

表1地基广角相机阵的技术指标  
Table1 Thetechnical indicators of GWAC telescope   

<html><body><table><tr><td colspan="2">技术指标 内容</td></tr><tr><td>跟踪速度控制精度</td><td>优于0.45"/s(RMS)</td></tr><tr><td>重复指向精度</td><td>优于2'（RMS)</td></tr><tr><td>恒动跟踪精度</td><td>天顶附近5min 连续跟踪优于2"(RMS)</td></tr><tr><td>两轴转动速度</td><td>最大角速度1.5°/s；最大角加速度0.5/s²</td></tr><tr><td rowspan="2">电接口要求</td><td>控制系统采用上下位机结构，下位机位于紧邻机架的电控箱内，上位机</td></tr><tr><td>位于控制室内，上下位机采用网络通讯方式</td></tr><tr><td>轴角测量要求</td><td>同时需安装增量式旋转编码器和光栅尺。前者主要用作望远镜位置保护， 后者用作望远镜位置测量。</td></tr></table></body></html>

根据地基广角相机阵的科学目标，提出了系统的功能需求：

(1)快动功能望远镜指向和日常的维护时需要该功能，

(2)微动功能

赤经、赤纬速度调节应分别具有快动、慢动、微动功能。同时，赤经还应具备速度为 $1 5 ^ { \prime \prime } / \mathrm { s }$ 的恒动跟踪功能。另外，赤经恒动速度应能在 $1 4 ^ { \prime \prime } / \mathrm { s } \sim 1 6 ^ { \prime \prime } / \mathrm { s }$ 之间按照每时秒 $0 . 1 ^ { \prime \prime }$ 步长分档调节。

(3)控制软件具备硬件测试功能测试的主要对象为指向和跟踪过程的稳定性和精确性。该项功能提高了系统的可维护性。

(4)控制软件需具备软件保护功能

软件保护功能是指望远镜依据轴角测量系统，自动判断当前位置或者待指向位置是否超出或可能超出安全工作区域，并自动停止望远镜或者拒绝指向的一种望远镜保护功能。该功能使望远镜工作时的安全性得到提高。

# 1.2系统伺服控制原理

依据天文观测对望远镜控制系统的基本要求，望远镜轴系既追求稳定、精确的跟踪速度，高的指向定位精度，又要保证精确的定位和导星，为此，利用以电流环、速度环为内环，位置控制为外环的三闭环[4伺服控制原理，设计了地基广角相机阵转台的控制系统。地基广角相机阵伺服控制系统原理如图2。

![](images/a07f93b42a2e9575fd8d1a43360f629d2ef11b31d5cc3bed82ee4a1f98568334.jpg)  
图2地基广角相机阵伺服控制系统原理 Fig.2The principle of GWAC telescope servo control system

这是一个典型的三闭环伺服控制系统：由伺服驱动器内部的电流环、以增量式编码器为测速元件的速度环和以光栅尺为测角元件的外环组成。电流环通过调节电流实现电机正确的力矩输出以确保运行的平稳性，赤经、赤纬轴电机的启动性能和加减速性能也与该环密切相关。

望远镜指向时，外环起主要作用，通过实时的位置反馈与给定的轴角目标值比较，实现望远镜赤经和赤纬的定位。定位精度既受外界干扰量的影响，如蒙气差等因素，也与光栅尺本身的测量精度相关。定位过程中，虽然速度环对定位的最后结果没有影响，但速度的实时反馈，可以提高速度曲线的平滑度，提高望远镜运行时的平稳性[5]。

观测时，望远镜指向完成后，进入跟踪过程。跟踪时的理论速度为 $1 5 ^ { \prime \prime } / \mathrm { s }$ ，方向自东向西。跟踪时的速度特性好坏直接决定了观测质量的好坏，因此，跟踪速度的精度及稳定性至关重要。速度大小通过程序给定后，由伺服控制器产生控制信号，并由驱动器驱动电机转动，电机速度经编码器反馈，从而保证了速度的精确度。编码器的稳定性及其每周刻线数对速度的稳定和精度产生决定性影响。

建立在上述控制原理基础上的地基广角相机阵伺服系统，主要采用了基于PID伺服算法的反馈控制方法，并综合应用了前馈控制的原理[6]。

# 1.3硬件系统设计及选型

根据系统的伺服控制原理，硬件系统的组成包括系统管理控制级、伺服控制单元、伺服驱动单元、系统执行单元、系统测量和反馈单元。

# 1. 3. 1 系统管理控制级

系统管理控制级为上位控制计算机，由其发出望远镜控制命令，并实时显示望远镜的位置、速度反馈，实现人机交互。控制计算机和伺服控制器之间通过网络通讯进行数据和命令的交互。

# 1.3.2 伺服控制单元

伺服控制器选用雷塞运动控制器，型号为SMC6490，该控制器为基于 $1 0 / 1 0 0 \mathrm { ~ M ~ }$ 以太网的通用独立式4轴运动控制器，可支持多个控制器和计算机组成运动控制系统。本身相当于一台计算机，可脱机运行，与驱动器间的控制脉冲信号、来自光栅尺的反馈信号可实现近距离传输，降低了电磁干扰，提高了信号传输的稳定性。

# 1. 3. 3 伺服驱动单元

驱动器使用松下三相交流伺服驱动器，型号为MEDKT7364CA1，提供了USB 接口直接与控制计算机通信，可在控制计算机安装专用软件对驱动器进行参数设置，因而非常方便于PID 参数的整定,提供了专用连接器与控制器通讯，控制信号采用脉冲 $+$ 方向型。

# 1. 3.4 伺服执行单元

系统执行单元选用松下三相交流伺服电机，型号为MDME202GCGM，额定输出功率 $2 . 0 \mathrm { { k W } }$ ，额定转矩 $9 . 5 5 \mathrm { N M }$ ，额定转速 $2 0 0 0 ~ \mathrm { r / m i n }$ 。

# 1. 3.5 测量和反馈单元

轴角测量及反馈单元选用雷尼绍光栅尺，外径 $2 0 6 \mathrm { m m }$ ，栅距为 $2 0 ~ \mu \mathrm { m }$ ，读数头分辨率为 $0 . 1 ~ \mu \mathrm { m }$ 。速度测量及反馈单元选用20位增量式编码器，每转一圈产生104万个脉冲，控制精度高。

# 1.4软件系统设计

软件系统开发环境为Windows7，开发平台为VS2010，开发语言为 $\mathrm { C } + +$ ，采用面向对象的开发技术，实现了基于控制器的望远镜界面操作和控制。

# 1. 4. 1 设计思想及程序结构

望远镜转台控制的两大功能是指向和跟踪，指向要求快速准确，跟踪要求精度高、稳定性好，同时要做好指向和跟踪两者的衔接和转换。望远镜动作过程中应实时显示指向位置与实际位置，以便观测人员进行对比，因此设计了定时器实时获取望远镜的时角，并由此计算赤经。望远镜控制离不开精确的时间系统，调用Windows API获取了系统世界时和北京时间，并通过天文算法计算恒星时。

另外，为了便于望远镜的调试，设计快动、慢动两种调整方式，满足测试人员对望远镜位置不同粗细程度的调整，捕捉望远镜的动作，并在界面实时显示。采用多线程的方法创建数据采集模块，用于指向精度、跟踪速度、跟踪精度等指标的测试。通信方面，考虑到传输的快速性和可靠性，与控制器采用网络连接的通信方式。

软件界面主要依托MFC类库[7]实现，运行在控制计算机上。根据设计思想和系统功能需求，设计了软件系统程序结构，如图3。

![](images/7627f383fee6938f38b7e4fa1e3d5de28c451ca36622ddb764ad46ec69b06622.jpg)  
图3程序框架图  
Fig.3The frame of program

# 1. 4. 2 控制界面的实现

控制界面的开发主要依托MFC类库实现，开发平台为VS2010。主要调用的类有 Button类、StaticText类、Edit Control类、IP Address Control类等，各种类库结合起来构成了一个应用程序的框架，提供了用户接口的标准实现方法。采用这种技术可方便地调用框架提供的接口，编程方便快捷。界面友好，便于人机交互，实用性强。地基广角相机阵的控制界面如图4。

![](images/fb5fc6929a8be39a8fb45559c24fe30dc45d6af99aeab0158b457c13a89b4de7.jpg)  
图4地基广角相机阵控制界面  
Fig.4The control interface of GWAC telescope

界面左边最上部分为连接、断开连接控制器，与控制器通信结果显示在界面标题。时间栏实时显示北京时、世界时和恒星时。望远镜指向及跟踪栏实时显示望远镜的指向位置赤经、实际赤经和时角，设有指向、跟踪、指向并跟踪、复位、停止5个按钮，跟踪速度可调，初始设置为 $1 5 ^ { \prime \prime } / \mathrm { s }$ 。望远镜状态反馈栏实时反馈望远镜动作，包括指向中、跟踪中、复位中、调试中、停靠中。赤经控制栏设有东、西两个方向快动、慢动的望远镜位置调节按钮，赤纬控制栏设有南、北两个方向快动、慢动的望远镜位置调节按钮。

# 2地基广角相机阵交流伺服系统的实验测试

通过相同的控制器和控制软件在地基广角相机阵样机上分别驱动交流伺服电机、步进电机，步进电机为日本RORZE，型号为RM28G06S。测试两种执行机构下的跟踪速度控制精度、最大角速度、最大角加速度、赤经跟踪精度4个关键技术指标，并由此比较两者的差异。另外，测试了交流伺服系统的重复指向精度，针对交流伺服系统对CCD成像的干扰作了实验研究。

# 2.1关键技术指标实测

(1)跟踪速度控制精度

测试方法为控制赤经轴以 $1 5 ^ { \prime \prime } / \mathrm { s }$ 的速度转动，控制软件以1s为周期记录赤经轴角位移，通过采样周期和角位移得到角速度。交流伺服电机、步进电机驱动下的跟踪速度曲线如图5、图6。目标速度是 $1 5 ^ { \prime \prime } / \mathrm { s }$ ，横轴为采样数，纵轴为速度值，单位 $" / \mathrm { s }$ ，采样周期是 $2 0 0 ~ \mathrm { { m s } }$ ，测定时长 $3 0 ~ \mathrm { m i n }$ 。交流伺服电机的速度峰峰值为 $1 . 6 ^ { \prime \prime } / \mathrm { s }$ ，控制精度为 $0 . 3 0 ^ { \prime \prime } / \mathrm { s }$ （RMS）。步进电机的速度峰峰值为 $1 . 6 ^ { \prime \prime } / \mathrm { s }$ ，控制精度为 $0 . 2 8 ^ { \prime \prime } / \mathrm { s } ( \mathrm { R M S } )$ 。

# (2)最大角速度

测试方法为控制赤经轴以最大目标速度转动，以0.2s为周期记录光栅尺转过的角度。交流伺服电机实测值为 $5 . 0 1 ^ { \circ } / \mathrm { s }$ ，步进电机实测值为 $1 . 8 7 ^ { \circ } / \mathrm { s }$ 。

# (3)最大角加速度

测试方法为控制赤经轴加速到最大角速度，转动一段时间后减速至停止；反方向重复加减速过程。以0.2s为周期记录光栅尺转过的角度。交流伺服电机实测值为 $3 . 5 7 ^ { \circ } / \mathrm { s } ^ { 2 }$ ，步进电机实测值为 $1 . 1 1 ^ { \circ } / \mathrm { s } ^ { 2 }$ 。

![](images/b5f37e8069b8d87e56a4ab22314e2a61902a43a6d7713f3fcc37b6279951474a.jpg)  
图5交流电机跟踪速度曲线

![](images/122f70f871fdb5d81ccb3dec44acb8969a5b6601e71b01f18798437f8b22afab.jpg)  
Fig.5Tracing speed curve of AC motor   
图6步进电机跟踪速度曲线  
Fig.6Tracing speed curve of stepper motor

(4)赤经跟踪精度

测试方法为在天顶附近连续跟踪 $5 \mathrm { m i n }$ ，CCD连续曝光，曝光时间为 $1 0 \mathrm { ~ s ~ }$ ，比较CCD视场中央赤经的变化。交流伺服电机、步进电机驱动下的跟踪精度曲线如图7、图8。横轴为采样个数，纵轴为视场中央赤经，单位度。交流伺服电机实测值为 $1 . 0 ^ { \prime \prime } ( \mathrm { R M S } )$ ，步进电机实测值为 $1 . 4 ^ { \prime \prime } ( \mathrm { R M S } )$ 。

综合以上4个指标，交流电机与步进电机相比，均满足控制要求；在低速控制上精度相当，无明显差异，但交流电机最大速度、最大加速度明显高于步进电机，调速范围宽，响应频率大，速度调节快，在高速控制领域性能优于步进电机。

# (5)重复指向精度

测试方法为控制望远镜指向位置 $A$ 并跟踪，拍摄一幅图像；控制望远镜指向位置 $B$ 并跟踪，拍摄一幅图像，重复5次。改变位置A、 $B$ ，重复测试4组。图像及数据处理算法为：通过图像处理软件算得每幅图像的视场中心赤经、赤纬坐标，通过EXCEL工具软件算得每个位置点5次指向中心坐标减去平均值的均方根，各点中心坐标及重复指向精度如表2。从表2可以看出，重复指向精度的最大值为 $4 0 . 7 ^ { \prime \prime } ( \mathrm { R M S } )$ ，符合设计要求。

![](images/3d5f56f0fd8b44d9cf34e734873f6fc55579d99fb56c6706af089e7291368176.jpg)  
图7交流电机跟踪精度 Fig.7The tracking accuracy of AC motor

![](images/ad77c6bae0e6b3fe80166de18108a71000a67e5ed256db08c551efac40a2dd85.jpg)  
图8步进电机跟踪精度  
Fig.8The tracking accuracy of stepper motor

表2视场中心坐标及重复指向精度统计表  
Table 2The statistics of field center coordinates and repetitive pointing accuracy   

<html><body><table><tr><td>组别</td><td>NO.</td><td>A 点视场中心坐标/（°)</td><td>B 点视场中心坐标/（°)</td><td>重复指向精度</td></tr><tr><td rowspan="5">第1组</td><td>1.1</td><td>(342.0281，41.5379)</td><td>(237.2756，41. 7177)</td><td rowspan="5">A点为14.2"（RMS）, B点为18.5"（RMS）</td></tr><tr><td>1.2</td><td>(342.0387，41.541 7)</td><td>(237.2797，41.722 7)</td></tr><tr><td>1.3</td><td>(342.0314，41.541 2)</td><td>(237.273 5，41. 724 5)</td></tr><tr><td>1.4</td><td>(342.0368，41.542 4)</td><td>(237.2718， 41.726 3)</td></tr><tr><td>1.5</td><td>(342.0346，41. 546 4)</td><td>(237.2711，41.731 7)</td></tr><tr><td rowspan="6">第2组</td><td>2.1</td><td>(197.0220，83.415 8)</td><td>(298.8032，21.618 1)</td><td rowspan="6">A点为35.9"（RMS）， B点为40.7"（RMS）</td></tr><tr><td>2.2</td><td>(196.992 2，83.416 4)</td><td>(298.8066，21.633 5)</td></tr><tr><td>2.3</td><td>(196.8320，83.4119)</td><td>(298.7916，21.635 4)</td></tr><tr><td>2.4</td><td>(196.8448，83.413 5)</td><td>(298.799 4，21.640 4)</td></tr><tr><td>2.5</td><td>(196.8065，83.412 4)</td><td>(298.7920，21.649 2)</td></tr><tr><td>3.1</td><td>(339.985 5，77.948 4)</td><td>(260.6474，19.448 3)</td></tr><tr><td rowspan="5">第3组</td><td>3.2</td><td>(339.9809，77.948 7)</td><td>(260.649 7，19.449 6)</td><td rowspan="5">A点为14.6"（RMS）, B点为28.4"（RMS）</td></tr><tr><td>3.3</td><td>(340.0029，77.946 4)</td><td>(260.6499，19.448 7)</td></tr><tr><td>3.4</td><td>(340.0119，77.945 4)</td><td>(260.6517，19.453 9)</td></tr><tr><td>3.5</td><td>(339.985 6， 77.954 6)</td><td>(260.6581， 19.467 1)</td></tr><tr><td></td><td></td><td></td></tr><tr><td rowspan="4">第4组</td><td>4.1</td><td>(5.482 2， 19.3374)</td><td>(250.6911， 78.118 6)</td><td rowspan="4">A点为23.2"（RMS）, B点为12.7"（RMS）</td></tr><tr><td>4.2</td><td>(5.4689，19.333 2)</td><td>(250.6797，78.118 3)</td></tr><tr><td>4.3</td><td>(5.479 5，19.332 6)</td><td>(250.6913，78.116 3)</td></tr><tr><td>4.4 4.5</td><td>(5.4721， 19.326 5) (5.483 8，19.332 2)</td><td>(250.7148，78.1121) (250.696 3， 78.119 1)</td></tr></table></body></html>

2.2交流伺服系统对CCD的干扰

交流伺服系统用在望远镜控制中，对CCD 成像有无干扰，干扰程度是否在可接受范围内，对此问题进行了实验研究。

# 2.2. 1 CCD干扰原理分析

噪声特性是影响CCD 成像质量的关键技术指标之一，CCD 的噪声包括光子噪声[8]、暗电流噪声和读出噪声。光子噪声存在于打开快门曝光的过程中，暗电流噪声形成的根本原因是半导体的热激发，因此温度是影响暗电流噪声的一个重要因素，随着温度的升高或降低，暗电流数值按指数倍增加或减少。为减小暗电流，CCD都有制冷装置。另外，暗电流还与光积分时间有关，即曝光时间越长，暗电流越大。CCD 所有像素计数模数转换单元（Analog Digital Convert Unit，ADU）值波动的标准差称之为读出噪声[9]。读出噪声由CCD 系统电子电路引入，包括电路系统的复位噪声、输出放大器噪声、A/D 转换的量化噪声[10]，与曝光时间无关，但与读出速度有直接关系。

交流伺服系统虽然采取了接地、驱动器外壳屏蔽等措施，由于驱动单元内电力电子器件的电流通断造成的开关噪声，启动负载时的冲击电流和开关的抖动，给电机供电的电力传输线的干扰，控制单元内高速数字电路运行产生的干扰等[11]，对外界的电磁干扰仍然存在。因此交流伺服系统对CCD 的干扰主要是对电子电路的干扰，即主要影响读出噪声。

以地基广角相机阵交流伺服系统为平台，选用Apogee CCD $\mathrm { U } 9 0 0 0 \mathrm { x }$ ，以读出噪声为参考指标进行干扰性测试。为了规避光子噪声和暗电流噪声的影响，CCD 曝光模式选为本底，即快门关闭、曝光时间为0，而且温度降至 $- 1 5 ^ { \circ } \mathrm { C }$ 。数据处理时使用了图像相减的算法，以消除斜坡噪声和像素不一致产生的影响。

# 2.2.2实验方法及数据处理

测试使用的软件有地基广角相机阵控制软件、CCD 控制软件 MaxIm、图像处理软件DS9、工程软件MATLAB。测试分以下几步完成：

（1)首先进行CCD初始化，直到CCD温度降到 $- 1 5 ~ \mathrm { { ^ circ C } }$ 以下并稳定。

(2)在未启动交流伺服系统、交流电机空载匀速转动、交流电机驱动赤经轴带载匀速转动3种情况下各控制CCD连续曝光16幅，电机转速为望远镜跟踪时的速度。为检测电机加减速对CCD 的干扰，控制CCD 连续曝光16幅，曝光过程中电机驱动望远镜多次加减速运动，最大速度为 $2 4 8 ~ \mathrm { r / m i n }$ ，共得到4组本底图像。

(3)对于同一组拍摄的图像，运用图像相减的方法，减去相同情况下的第1幅图像，统计差值图像所有像素计数模数转换单元的标准差 $\sigma$ ，根据误差传递公式， $\sigma / \sqrt { 2 }$ 即为读出噪声（单位：ADU），作为衡量交流伺服电机对CCD干扰的指标。

测试采集的图像经过软件存储为FIT格式文件，每幅图像占 $1 8 \mathrm { ~ M ~ }$ 左右空间，数据量巨大，人工计算显然不可取。为此以MATLAB2012为软件开发平台编制了图像的处理和数据计算程序。

# 2.2.3 测试结果分析

测试结果如图9，从图中可以看出，4组数据的读出噪声没有大的跳变，整体分布在较窄的范围内，说明在电机匀速转动、加减速过程中没有对CCD造成大的干扰，并算得未启动交流伺服时读出噪声的平均值为8.2861，空载匀速、带载匀速和带载加减速3种情况下的平均值分别为8.2799、8.2717、8.2774，相对未启动交流伺服系统的相对误差分别为 $0 . 0 7 \%$ 、 $0 . 1 7 \%$ 、 $0 . 1 0 \%$ 。从相对误差来看小于 $0 . 5 \%$ ，鉴于可能有其他因素造成误差，实验测得的误差在可以接受的范围内，交流伺服系统对Apogee CCD $\mathrm { U 9 0 0 0 x }$ 的干扰不影响观测结果。

![](images/c8239a5a6b68a65e63d253e75970e49baba2f1409e35d267049ed795bbb4ee7b.jpg)  
图94种情况下的读出噪声分布曲线  
Fig.9The distribution curve of readout noise for the four cases

# 3总结

本文根据望远镜的控制要求，开发了望远镜转台的伺服控制系统，并对系统的控制环节、驱动环节、执行环节、轴角测量反馈环节的硬件进行选型。开发了软件控制系统，与控制器采用网络通信的方式，调用编程接口函数发送控制命令，设计了通信、动作、辅助观测信息、状态反馈、数据采集、位置调整6大功能模块，实现了可视化的界面控制。

通过跟踪速度控制精度、最大角速度、最大角加速度、赤经跟踪精度、重复指向精度5个技术指标的实测，一方面证明交流伺服系统的性能满足设计要求，另一方面，在同一平台、相同指标、相同软件系统下，比较交流伺服系统和步进电机系统性能的差异，对天文等相关领域具有借鉴和参考意义。

交流伺服系统用于望远镜控制是否影响CCD 成像质量，本文进行了实验研究。分析CCD 的噪声特性得出，交流伺服系统主要通过影响读出噪声的方式干扰 $\boldsymbol { \mathrm { C C D } }$ 。因此在未启动交流伺服、交流伺服电机空载匀速转动、带载匀速转动、多次加减速4种情况下，分别测定CCD的读出噪声进行比较。由实验结果得出，交流伺服系统运行时读出噪声的相对误差均小于 $0 . 5 \%$ ，对 Apogee CCD $\mathrm { { U 9 0 0 0 x } }$ 的干扰不影响观测数据的质量，即完全可以用于望远镜控制。

# 参考文献：

[1] 黄垒，辛立平，韩旭辉，等．广角天文望远镜的自动调焦［J］．光学精密工程，2015，23(1):174-183.Huang Lei， Xin Liping，Han Xuhui，et al. Auto-focusing of wide-angle astronomical telescope[J].Optics and Precision Engineering，2015，23(1）：174-183.  
[2] Kurt W W. Lecture Notes in Physics : Supernovae and Gamma-Ray Bursters [M]. Berlin : Springer,2003:1-2.  
[3] 王志强.步进电机和交流伺服电机性能综合比较［J]．天津职业院校联合学报，2006，8(5): 14-17.Wang Zhiqiang. Comprehensive comparison between the stepper motor and the DC servo motor[J].Journal of Tianjin Vocational Institutes，2OO6，8(5）：14-17.  
[4] 葛亮，王金虎，卢晓猛.1.26米红外望远镜电控系统软件设计与实现［J]．天文研究与技术，2015，12(3):317-322.Ge Liang，Wang Jinhu,Lu Xiaomeng. Design and implementation of software for operations of theservo system of the $1 . 2 6 \mathrm { m }$ infrared telescope of the NAO [J].Astronomical Research &Technology，2015，12(3）:317-322.  
[5] 黄垒．天文望远镜控制系统研究及故障诊断［D].北京：中国科学院大学，2014：97-101.Huang Lei. Study on technology of astronomical telescope control system and fault diagnosis [D].Beijing: University of Chinese Academy of Sciences，2014: 97-101.  
[6] 黄垒，魏建彦，姜晓军，等.基于PMAC的天文望远镜控制系统研究及应用［J].天文研究与技术，2015，12(1)：44-53.Huang Lei，Wei Jianyan，Jiang Xiaojun，et al. A study of a PMAC-based astronomical telescopecontrol system and its application ［J]. Astronomical Research & Technology，2O15，12(1): 44-53.  
[7] 欧阳志宏，董霖，钟俊华．MFC 程序设计轻松入门［M]．北京：人民邮电出版社，2009：174-195.  
[8] 李云飞，司国良，郭永飞.科学级CCD 相机的噪声分析及处理技术［J］．光学精密工程，2005，13(S1) : 158-163.Li Yunfei， Si Guoliang，Guo Yongfei. Noise analyzing and processing for scientific grade CCDcamera[J].Optics Precision Engineering，2005，13(S1）：158-163.  
[9] 张双根，黄文忠，谷渝秋，等．用于激光等离子体中X射线测量的单光子计数型CCD的标定［J].强激光与粒子束，2006，18（1)：77-80.Zhang Shuanggen，Huang Wenzhong，Gu Yuqiu，et al. Calibration of single-photon counting X-ray CCD [J]. High Power Laser and Particle Beams，2006，18(1）: 77-80.  
[10]Dussault D，Hoess P.Noise performance comparison of ICCD with CCD and EMCCD cameras[C]/／Eustace L Dereniak,Robert E Sampson,C Bruce Johnson. Infrared Systems and PhotoelectronicTechnology.Proceeding of the SPIE，2004，5563：195-204.  
[11］董华兴，张东宁，张瑷.减少交流伺服系统电磁干扰的方法［J]．微特电机，2007,35（10)：21-23.Dong Huaxing， Zhang Dongning， Zhang Yuan. The method of reducing EMI on AC servo system[J].Small & Special Electrical Machines，2007，35(10）:21-23.

# The Preliminary Study on Application of AC Servo System in Astronomical Telescope

Zhang Shenghua $\cdot ^ { 1 }$ ，Huang Lei $^ 2$ ，Wei Jianyan $^ 2$ ，Zheng Lifang'，Liu Qi $^ 3$ (1. University of Science and Technology Beijing，Beijing 10o083,China,Email；zhenglifang@ustb.edu.cn; 2.National Astronomical Observatories，Chinese Academy of Sciences，Beijing 1Ooo12,China; 3.University of Chinese Academy of Sciences，Beijing 1Ooo49，China)

Abstract：AC servo system is widely used in industrial control field，but the practical application in the controlling of astronomical telescope is still inthe initial stage.In this paper，ground-based wide-angle camera (GWAC）which is the ground observation equipment of SVOM astronomical satelite is usedas the research platform，and the AC servo system is applied to the turntable controling of telescope.The telescope's tracking speed accuracy，tracking accuracy，pointing accuracy and other key technical indicators are tested and compared with the indicators of stepper motor system.The test results show that the two systems have high precision in low-speed controling.AC servo system has advantages in high-speed controlling，with wider speed range,faster speed regulation and smoother running.In addition，AC servo system also has low noise，high torque,high performance and low price.The interference of AC servo system with the CCD is tested by experiment.The results show that interference of AC servo system with CCD is in acceptable range.In short, the AC servo system can be used for the turntable controlling of smalland medium-sized telescope，especially for the system of fast rotation and pointing.

Key words:GWAC；AC servo system；Key technical indicators;Interference of CCD