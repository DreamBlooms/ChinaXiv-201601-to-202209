# 一米新真空太阳望远镜光谱扫描观测系统设计

杨长春},²，李正刚¹，陈宇超1,²，许骏(1.中国科学院云南天文台，云南 昆明650011；2.中国科学院大学，北京100049)

摘要： $1 \mathrm { ~ m ~ }$ 新真空太阳望远镜(NewVacuum Solar Telescope，NVST)是国内用于对太阳进行观测和研究的大型科研设备，针对太阳活动区光谱观测的需求，在现有的大色散光谱仪及多波段光谱仪基础上，设计了光谱扫描设备，并基于C#设计了一套观测控制系统软件，实现扫描设备的运动控制和观测数据的采集。进行光谱扫描观测时，计算机控制扫描设备步进运动，并利用图像采集卡通过CameraLink总线采集CCD/CMOS相机的探测数据，基于多线程技术采集观测数据，将采集的图像数据存储成FITS（Flexible Image Transport System）文件，并将光谱图像数据处理成灰度图像用于软件界面监视。此套软件已用于 $1 \mathrm { m }$ 太阳望远镜光谱扫描观测，测试结果满足预期功能需求，为后续观测系统功能升级提供了良好的扩展性。

关键词： $1 \mathrm { m }$ 红外太阳望远镜；狭缝扫描；光谱观测；图像采集；FITS中图分类号：P111.41；TP311.1 文献标识码：A 文章编号：1672-7673(2016)02-0257-09

在太阳大气结构演化和剧烈活动中，磁场发挥着重要作用，通常磁场活动会产生如太阳黑子、耀斑、日珥及日冕物质抛射等现象[1]。利用偏振成像和光谱可测量太阳矢量磁场[2]。磁场测量也是许多太阳望远镜的重要科学目标[3]，如瑞典太阳望远镜（Swedish Solar Telescope，SST）、日本的无圆顶太阳望远镜(Domeless Solar Telescope，DST）、美国的新太阳望远镜（New Solar Telescope，NST)等太阳望远镜； $1 \mathrm { m }$ 新真空太阳望远镜（New Vacuum Solar Telescope，NVST）[4」作为抚仙湖太阳观测站的主要观测设备，是国内用于太阳物理研究的大型科研设备，其重要科学目标有针对太阳活动区磁场的高分辨率偏振成像观测和光谱扫描观测。

光谱扫描作为太阳磁场测量的重要部分，利用 $1 \mathrm { m }$ 太阳望远镜实现太阳光谱扫描观测，通过光谱扫描观测方法对太阳进行观测研究，在原有的大色散光谱仪及多波段光谱仪基础上，需要设计狭缝扫描机构，并基于扫描设备实现光谱扫描观测。

在太阳塔的设备结构中，在光谱仪消旋转台狭缝之后正交布置有大色散光谱仪和多波段光谱仪系统。为了得到太阳像的二维光谱信息，设计狭缝扫描系统，利用一套电动升降台和两对平面反射镜组成光路平移机构。控制升降台带动平面镜步进运动，镜面反射作用将光路平移，使太阳光斑像以步进扫描方式通过狭缝，进入狭缝后的大色散光谱仪或多波段光谱仪系统，利用CCD相机采集光谱图像，并将采集的光谱图像数据存储为FITS文件。

# 1系统硬件设备

图1描述了 $1 \mathrm { ~ m ~ }$ 太阳望远镜终端仪器设备的结构，光谱扫描系统涉及的主要硬件设备，包含光谱仪消旋转台上的电动扫描设备、CCD相机探测器以及光栅分光仪等。

在消旋转台上设计有宽度可调节的狭缝窗口，当太阳光斑像逐步通过狭缝后，经由大色散或多波段光谱仪系统，进入消旋转台上的 PCO 相机探测器成像。消旋转台上放置的计算机利用 Matrox 或Silicon系列图像采集卡，通过CameraLink 总线采集CCD/CMOS相机探测图像数据。为使太阳光斑像逐步扫过狭缝，借鉴了新太阳望远镜用于光谱扫描的平面镜组平移光路的思想[5]，设计了图1所示的一套电动升降台和两对平面反射镜。电动升降台需要实现微米级的精密运动控制，以保证高空间分辨率的图像数据，选取卓立汉光公司生产的电控升降台，并特别设计了架设扫描系统设备及光路分光设备的上平台仪器转换中枢。

![](images/db7c3a7925ef0f0c7916b192fddbe7dfd00da5855444aa592e643bbfd00f31d8.jpg)

# 2系统软件设计

光谱扫描观测系统工作时，计算机需要控制扫描机构的运动过程，同时控制CCD 相机进行图像数据采集，并实现光谱图像数据的存储。

# 2.1扫描设备运动控制

基于扫描设备实现光谱扫描观测，如图2(a)为光谱扫描机构实物及运动控制器。扫描机构中涉及的电控设备主要是由步进电机驱动的电动升降台，图2(b)为描述工作原理的运动示意图，图2（c)反映了设备运动与光路平移的数值关系 $\scriptstyle ( L = 2 d )$ 。

![](images/61af6a5c2c12bb72e14bfcff926f0f2fdde40d3cdd00b41aa07e6a36df4ee149.jpg)  
图11m太阳望远镜终端仪器结构示意图Fig.1Schematic diagram of NVST terminal  
图2光谱扫描设备结构图。（a）扫描机构及运动控制器；（b）扫描设备工作原理；（c）扫描运动与光路平移关系Fig.2The structure of spectral scanning equipment

光谱扫描时，控制电动升降台步进运动，光路在水平方向平移的位移量与升降台在垂直面的移动距离成两倍关系。由于目前的狭缝宽度为 $2 0 0 ~ { \mu \mathrm { m } }$ ，后续观测中还会选择 $1 0 0 ~ { \mu \mathrm { m } }$ 、 $5 0 ~ { \mu \mathrm { m } }$ 等窄狭缝,因此，扫描步幅作为可调节参量，预设幅值选取 $1 0 0 ~ { \mu \mathrm { m } }$ ，并可灵活调节步幅大小；升降台每步进运动一步，光路平移两倍步长距离，步进停止时图像采集，根据采集图像区域大小设定扫描运动步数，扫描步数亦作为可调参量；扫描完一组图像时需要恢复扫描设备至设定零位，并设定可调扫描组数参量，实现升降台的往复扫描运动。

扫描系统中电控升降台的基本性能指标如表1。扫描机构的运动部件由步进电机驱动，步进电机在脉冲电源下运行，角位移量与输入的脉冲数成正比关系，可与相应驱动电路组成开环数控系统，具有良好的定位可靠性，也可与适当的反馈环节组成高性能的闭环数控系统。在此系统中，电动升降台配置了线光栅编码器用于位置反馈，并选取厂商配套设计的运动控制驱动器，运动控制器与计算机通过RS232接口实现通信控制。

表1电动升降台性能参数  
Table1 Basic performance parameters of the electric lifting platform   

<html><body><table><tr><td rowspan="2">行程</td><td rowspan="2">螺杆 导程 分辨率</td><td rowspan="2">开环</td><td rowspan="2">闭环 最大 分辨率 速度</td><td rowspan="2"></td><td rowspan="2">重复定 回程</td><td rowspan="2">直线度</td><td rowspan="2">俯仰 平直度</td><td rowspan="2">偏摆</td><td rowspan="2">步进</td><td rowspan="2">中心 负载</td></tr><tr><td>位精度 间隙</td></tr><tr><td>/mm</td><td>/mm</td><td>/μm</td><td>/μm</td><td>/mm/s</td><td>/μm</td><td>/μm</td><td>/μm</td><td>/”</td><td>电机</td><td>/kg</td></tr><tr><td>100</td><td>4</td><td>2.5</td><td>1</td><td>40</td><td><3</td><td><5</td><td><10</td><td><15</td><td>42M-1. 8S</td><td>30</td></tr></table></body></html>

# 2. 1. 1 扫描机构电控程序设计

鉴于扫描设备由对应的运动控制器直接控制，控制器已实现对步进电机运动的底层驱动及控制，控制器与计算机基于串口通讯，因此，对设备的运动控制可从上位机程序设计方面实现。基于厂商自定义的上位机通信指令协议，以 ASCII码标准进行串口通讯控制设计。当前基于VisualC#WindowsForm 的观测系统软件设计中，针对扫描设备的运动控制，利用串口通讯基于 SerialPort类开发运动控制程序。SerialPort类位于System.Io.Ports 空间下，主要用于串行端口文件资源的控制，提供了事件驱动 I/O 和同步I/O，对串行驱动程序属性的访问和对引脚及中断状态的访问[6]。对计算机串口进行操作，SerialPort 类常用的属性有 PortName、BaudRate、DataBits、Open、ReadExisting、Write、Close 等用于串口操作，串口通讯控制的基本实现流程如下表述：

(1)配置串口参数并打开串口。根据运动控制器的串口通信参数，为计算机分配一个串口用于扫描设备通信控制，设置串口参数与其匹配。利用SeriaIPort类的相关属性设置串口的端口号、波特率、数据位、奇偶校验、停止位等基本通讯参数，并打开对应计算机端口即可进行通讯控制，在此使用SerialPort 类的基本属性/方法有：PortName、BaudRate、Parity、DataBits、StopBits、ReadBufferSize、IsOpen、Close、Open 等。

(2)向串口发送数据。打开对应的计算机串口后，即可将运动命令发送给控制器执行，利用SerialPort类的Write()操作实现指令的发送。以“设备向前运动 $5 0 ~ \mu \mathrm { m }$ ”控制命令为例，通讯控制时可表述为：ScanPort.Write("GoPosition Z，O,R，P, $\boldsymbol { 5 0 } \backslash \mathbf { r } "$ )。对扫描机构中升降台的运动控制，为提高串口通讯设计的便捷性，可自定义一个 SendMsg(string Commands)类似的函数专用于指令发送，控制器的通讯指令皆转换为此函数的Commands 变量执行。

(3)接收串口数据。计算机与运动控制器间进行串口通信，控制器反馈电动升降台的运动状态给计算机，以便于计算机处理数据并执行后续控制。控制器反馈的数据传递至计算机串口分配的缓冲区中，读取串口缓冲区数据时主要利用 SerialPort类的DataReceived事件，并基于 SerialPort类的ReadExisting方法即时获取缓冲区数据。

(4)关闭串行通信端口。扫描工作结束后，控制设备运动复位，在控制软件退出或其它需要关闭串口的时候，需关闭已打开的串行端口，并释放占用的资源。串口关闭操作相对简单，可直接利用SerialPort类的Close 操作，即“ScanPort.Close（）；"方式实现。

如上所述通过串口控制实现数据的发送和接收，对于扫描设备的运动过程控制，从上位机软件控制实施的角度可表示为一系列字符串指令的发送和接收，通过扫描设备运动参数的通信指令描述，可实现设备的运动控制。 ---Vtop

由如图3的升降台运动过程示意图可知，曲线所围面积 $s$ 表示升降台步进距离，步进距离参数恒定时，不同的速度参量对应不同的运行时间，此运动中需求微小步进距离，较快的运动过程，才能保证图像采集时具有较高的时间分辨率。

![](images/fa39f497fd1614a638664fbabe207e95b531c4a41b756f4bba5012d41bef5069.jpg)  
Fig.3A schematic diagram of motor process

电动升降台扫描时，升降台与两对平面反射

镜面组成光路平移系统，使太阳像以步进扫描的方式通过狭缝，进入狭缝之后的光谱仪系统进行光谱成像观测。光谱扫描时，首先对扫描设备进行初始化设置，包含通信端口设置、升降台运行速度设置、扫描初始零位设置以及复位模式等参量的设置；制定扫描方案，即对扫描区域的具体步进运动控制，包含扫描机构的扫描方向、步进幅值、步进次数、步进间隔时间以及扫描的次数；扫描完成时复位设备，等待下一轮扫描或其它运动控制。基于串口通讯，利用配置的线光栅编码器检测升降台位置，并结合平台上的光电开关及机械限位开关实现一系列运动过程控制。

# 2.2光谱图像的采集存储

扫描系统工作中，每当扫描装置步进一步等待图像采集时，利用CCD/CMOS 相机采集一帧图像数据。系统选择了德国PCO公司生产的PCO2000/PCO4000系列相机及对应的相机控制器，并通过Matrox或 Silicon 系列采集卡采集图像数据，并将采集的图像数据以FITS（Flexible Image TransportSystem)文件存储，以满足天文数据处理的需求。

# 2.2.1 图像采集程序设计

在此系统中，为实现图像数据的采集，计算机通过Matrox 系列采集卡获取PCO2000 相机的探测图像，并通过Camera Link[7]总线传输数据。图像采集程序的设计利用了PCO 公司提供的相机控制开发包①，利用SDK资源能提高开发效率。

图像采集的主要工作流程见图4，CCD探测到模拟图像信号后，经过模数转换器转换，将模拟量转换为数字图像数据，并存入相机内存空间，直到相机内存里准备完全一幅图像数据之后，触发事件信号，并将数字图像数据传输至计算机内存，计算机再作后续的FITS 文件存储和显示等操作。

![](images/7b32724658640d7f59906998fc875fd861a3d6768a516b96efba1cea7b96d54f.jpg)  
图3运动过程示意图  
图4图像采集工作流程示意图  
Fig.4The schematic diagram of image acquisition process

图像采集程序设计中，基于PCO 公司提供的 SDK，它整合了相机控制的一些 API函数，便于此处基于C#的观测系统软件设计。控制相机采集图像的基本设计流程见图5，需要先完成相机的初始化控制，调用“PCO_OpenCamera（）”打开相机之后，再利用“PCO_SDK_LibWrapper”SDK里面相关函数获取并设置相机参数，计算机利用采集卡通过CameraLink总线获取相机探测数据。相机控制程序设计时，主要的步骤有：声明一些数据结构用于相机状态控制并初始化结构的大小，获取CCD 当前参数值，设置相机曝光及采集图像面元大小等参数，获取相机采集图像的大小并申请内存空间存储数据，单帧或循环的采集及存储图像，停止采集及关闭相机并释放空间。

# 2.2.2图像数据采集存储设计

望远镜跟踪太阳运动时，光谱仪狭缝所处平面上的太阳像随时间绕主光轴旋转，需要利用光谱仪消旋转台抵消其影响才能实现光谱扫描[8]。计算机采集到光谱图像数字信号后，需要将图像数据存储为FITS 文件，图像存盘时利用NASA提供的CSharpFITS②类资料。FITS 文件由文件头信息和数据矩阵组成，文件头用于存储该文件的描述，如观测对象、观测时间、曝光时间等信息，以便于后期数据分析使用，文[9]与文[10]等对图像数据存储FITS文件进行了详细介绍。FITS 图像文件存盘时，需记录文件当前状态信息以便于后续数据处理，文件名可包含当前日期及时间，图像对应扫描机构的扫描位置，并将图像文件存储于自动分类创建的文件夹中，存储时可基于 DateTime 类及 DirectoryInfo类灵活地创建文件存储路径及文件名称。

![](images/bb3fa7d2770fb512a592a451c976d6867066ad9e0b7ba94b836791f12effad73.jpg)  
图5图像采集程序设计基本流程  
Fig.5The basic programming process of image acquisition

扫描系统实现图像数据的获取，考虑到循环采集的过程，即扫描机构步进运动一步后自动采集并存储一帧图像。程序设计实现文件存储时，计算机获取到相机采集传递的数字图像数据后，需将二维大数组形式的数据转存为FITS 文件。图6描述了测试的两种设计模式的工作时序。设计之初曾在一个控制线程内顺序执行图像采集和存储(Model-1），即扫描设备步进一步完成时开始控制相机采集图像，计算机获取图像数据后存储为FITS文件，软件界面显示当前采集的图像，文件存储完后进行下一步扫描，如此循环进行光谱扫描。经过实测发现此种方案非常耗时，完成一帧扫描图像的获取需要接近 $4 \mathrm { s }$ ，不能得到较高的时间分辨率，测试发现主要的耗时发生在FITS文件的存储部分（3s）。后来测试了计算机内存暂存图像方案(Model-2)，将文件存储分离出来，即扫描工作中，计算机每得到一帧图像数据，将图像数据矩阵暂存于计算机内存，并不立即存储FITS 文件，循环获取图像至完成一轮扫描后，再将内存中的多幅图像数据转存到硬盘中。此种方案虽提高了扫描的时间分辨率(1s），但由于一帧图像数据是 $2 0 4 8 \times 2 0 4 8$ (PCO2000相机)的数据矩阵，计算机分配大数组的空间有限，测试发现在分配超过100帧图像空间时，程序不能稳定运行，数据溢出，大大限制了扫描步数，并且在扫描结束时，图像逐帧转存到硬盘中，大量的耗时造成软件界面假死现象，此方案也因此舍弃。

![](images/f9e2282b519dfa34f476b03ca45186aae903268b1ccb4e1ed41ee4f7be86aab1.jpg)  
Fig.6A schematic diagram of image acquisition timing sequence

当前系统中设计了多线程方式实现光谱扫描图像的采集存储。每一个子线程主要实现的功能，即控制扫描机构步进一步，计算机控制相机采集一帧光谱图像，采集到图像数据后即进行FITS 文件存储，存储完成后自动结束子线程，图7为多线程方式实现光谱扫描图像获取的工作时序示意图。在第1个采集线程里，扫描机构步进完一步后，控制相机探测图像，曝光完成后将图像经过模数转换器转换得到数字图像数据，将数据转存到一个数组用于后续数据处理，经过数据转换处理后，开始存储FITS 图像文件，此刻开启另一个线程执行下一步扫描并采集图像。每一个线程执行图像采集的过程，如图6中Model-1方案所述，耗时 $ { 4 \mathrm { ~ s ~ } }$ 完成一帧光谱图像获取，如图7间隔开启多个线程之后，前几个线程陆续执行完毕退出，并存储了对应的FITS 图像文件。扫描过程中，需要了解采集的图像情况，可将采集的数字图像数据进行灰度处理并重绘于软件界面中，程序设计在每扫描7步时显示一帧当前采集图像，同时在扫描首尾步时亦显示当前图像，以便于界面更新和查看。此方案能保证更高的扫描时间分辨率，并能实时存储大量的FITS图像文件。

![](images/b6948e9078005850ffe334283684db128cf5f66e99257375ea82cb14d0b4eef2.jpg)  
图6图像采集工作时序示意图  
图7图像采集时序示意图  
Fig.7The schematic diagram of image acquisition timing sequence

# 2.3用户界面设计

对此光谱扫描观测系统，前文分别阐述了扫描设备的运动控制，以及控制相机进行图像采集存储的设计框架。针对光谱扫描观测需求，控制扫描机构步进一步，之后控制相机采集一帧光谱图像，得到数字图像数据后进行FITS文件存储以及于软件界面重绘。程序设计的基本流程如图8，首先实现扫描设备和相机初始化控制，包含扫描设备的运行速度、扫描零位、相机采集面元大小和曝光时间等参数设置；两者初始化完成之后，进行光谱扫描参数设置，包括扫描机构步进幅值、步进次数、扫描次数等，即控制扫描机构运动实现太阳光路平移扫描过狭缝，并根据像质情况修定相机曝光时间等设置；若不做光谱扫描，可只控制相机采集图像而不存储以作图像监视使用，若进行光谱扫描观测，则可触发扫描方案的执行，程序自动地控制扫描设备运动，以及光谱图像的采集、存储和显示。

光谱扫描的实现，需要对扫描设备及相机两者进行控制，为便于用户操作，控制逻辑实现上应具有较高的自动化程度，用户界面设计时应当简洁友好，此软件主界面设计如图9，其UI主视图主要分为：“Instruments”即设备管理操作区，“ScanSetting”即扫描参数设置操作区，“Observation”即观测操作区，“Current Setting”和“Status”显示当前设置和当前运行状态，“IntensityGraph”控件显示图像的区域。为在界面中显示采集的图像效果，选择了NI（NationalInstruments)公司Measurement Studio 201O产品中的IntensityGraph图像显示控件，将采集的图像数据进行归一化处理转换为灰度图后再显示，用此控件高效地满足了数字图像数据的显示需求。

# 3扫描系统实测

此套扫描系统已应用在 $1 \mathrm { m }$ 太阳望远镜进行光谱扫描观测。为检验扫描机构运动的稳定情况，基于激光光源和 $1 \mathrm { m }$ 太阳望远镜原有的图像采集通道，控制扫描设备每步进一步拍摄一帧图像，最后利用IDL软件对所有图像运行轨迹进行分析，验证了扫描设备的运动稳定性，能满足望远镜跟踪太阳进行光谱扫描观测的需求。光谱扫描观测时，当前使用宽狭缝（ $2 0 0 ~ \mu \mathrm { m }$ )，后续会使用窄狭缝，扫描步幅选取了 $1 0 0 ~ { \mu \mathrm { m } }$ 及更小步

![](images/b5c332245c09c37f0ad42106203e86e4804309cb1e13c90bd1fb43f736a1a1e0.jpg)  
图8程序设计流程图

![](images/35d6be929c037f6c9eef4e308ecfbec9f0f47bcb575b107fdafc27a2956c254e.jpg)  
Fig.8The program design flow diagram   
图9光谱扫描系统软件主界面  
Fig.9The main interface of spectral scanning software

幅测试，扫描设备步进工作时，相机采集光谱图像，执行完一轮扫描后设备自动复位并进行下一轮扫描观测。图10为扫描系统现场实测图，图中描述了对太阳黑子进行光谱扫描观测，观测中得到了所需的光谱图像数据，可用于光谱分析。

![](images/80b1607c1813b1d4c379c766ac816e65bcf94fc2c0f3eb98ee9b075446d61c6f.jpg)  
图10光谱扫描观测现场测试图 Fig.10The field test of scanning software

# 4结语

光谱扫描观测作为 $1 \mathrm { m }$ 太阳望远镜的重要科学观测目标，设计了狭缝扫描设备用于光谱扫描，并在VS2010环境下基于C#开发了一套观测软件，已用于 $1 \mathrm { m }$ 太阳望远镜的光谱扫描观测，满足了观测所需的基本功能。在原有光谱仪系统设备的基础上，设计了扫描设备实现光谱的扫描观测；针对扫描机构的运动控制，基于C# SerialPort类开发控制程序，具有较好的通用性；利用PCO 公司提供的对CCD 相机控制的SDK，提高了相机控制程序的开发效率；将图像数据存储为FITS文件时，利用NASA 提供的CSharpFITS 类资料，提高了图像存储程序设计的效率；软件界面显示图像时，利用IntensityGraph图像显示控件，程序设计效率优于基于GDI $^ +$ Bitmap方式绘图。由于 $1 \mathrm { ~ m ~ }$ 太阳望远镜科学目标需求中还有针对太阳活动区的偏振测量，结合 $1 \mathrm { m }$ 太阳望远镜的高分辨图像采集系统，在后续观测系统升级改造中，还需要实现光谱扫描系统与偏振测量系统同时工作，本文所述内容将为后续相关工作提供参考。

# 参考文献：

[1] 方成，丁明德，陈鹏飞．太阳活动区物理［M］．南京：南京大学出版社，2008.  
[2] 梁红飞．太阳黑子矢量磁场的测量及视向电流密度的计算［D]．昆明：中国科学院云南天文台，2006.  
[3] 刘忠，邓元勇，季海生，等.中国地基大太阳望远镜［J］．中国科学：物理学力学天文学，2012，42(12):1282-1291.Liu Zhong，Deng Yuanyong，Ji Haisheng，et al.Ground-based giant solar telescope of China[J]. Scientia Sinica:Physica Mechanica Astronomica，2012，42(12）:1282-1291.  
[4] Liu Zhong，Xu Jun，Gu Bozhong，et al.New vacuum solar telescope and observations with highresolution [J].Research in Astronomy and Astrophysics，2014，14(6） :705-718.  
[5] Chae J,Park H M,Ahn K，et al. Fast Imaging Solar Spectrograph of the 1.6 meter New SolarTelescope at Big Bear Solar Observatory ［J]. Solar Physics，2013，288(1）:1-22.  
[6] 王国胜，刘攀，尼春雨.C#基础与案例开发详解［M].北京：清华大学出版社，2009.  
[7] Camera Link:Specifications of the Camera Link interface standard for digital cameras and framegrabbers [M].Automated Imaging Association，2007.  
[8] 柳光乾，付玉，程向明.1米太阳望远镜光谱仪像旋转及消旋控制［J].天文研究与技术-国家天文台台刊，2012，9(1)：86-92.Liu Guangqian，Fu $\mathrm { Y u }$ ，Cheng Xiangming. Image field rotation and control of counter rotation forthe spectrograph of the 1m solar telescope of the Yunnan Observatory ［J]. AstronomicalResearch and Technology———Publications of National Astronomical Observatories of China,2012,9(1) : 86-92.  
[9] 刘应波．太阳望远镜海量数据存储关键技术研究［D].昆明：中国科学院云南天文台，2014.  
[10] 程祖桥，邓辉，王锋，等.基于Camera Link总线的CCD高速图像采集技术［J].天文研究与技术——国家天文台台刊，2011，8(4)：363-368.Cheng Zuqiao,Deng Hui，Wang Feng，et al. A sudy on Camera Link bsedhigh speed CCD imageacquisition techniques [J].Astronomical Research and Technology———Publications of NationalAstronomical Observatories of China，2011，8(4）：363-368.

# The Design of a Spectrum Scanning Observation System for the New Vacuum Solar Telescope

Yang Changchun $^ { 1 , 2 }$ ，Li Zhenggang1，Chen Yuchao1,²，Xu Jun1 (1.Yunnan Observatories，Chinese Academy of Sciences，Kunming 650011,China,Email； xj@ynao.ac.cn； 2.University of Chinese Academy of Sciences，Beijing 1Ooo49，China)

Abstract:The New Vacuum Solar Telescope（NVST） is for solar observation use. It is equipped with high resolution imaging instruments and spectrometers combining with polarization analyzer.Two vertical grating spectrometers，placed in the hanging bracket below the rotating platform，aim to observe the sun spectrum finely.On the base of these instruments and equipment，this article designs a slit scanning equipment placed above the rotating platform，and based on the C#this paper develops a set of observation and control system software.For spectral scanning observation，computer controls scanning equipment's stepping movement; then image acquisition card acquires observation data through camera link bus.When the digital image data are obtainedbymulti-threadtechnologycontrol，they will bestored inthe FITS（Flexible Image Transport System）file and processed and outputed as grayscale images so as to be monitored in the software user interface.The experimental results show that this control system software is a feasible design for slit scanning observation； it provides considerable potentials for subsequent observation system upgrades.

Key words:NVST； Slit scanning； Spectroscopic observations； Image acquisition； FITS