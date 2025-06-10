# 天文CMOS相机测试平台及控制系统的实现

罗志远1,2，许骏¹，刘黎明1,2，张涛‘

（1.中国科学院云南天文台，云南昆明650011；2.中国科学院大学，北京100049）

摘要：CMOS相机是一种重要的固体成像设备。随着科研级CMOS相机的性能不断提高，现在广泛应用于科研领域。抚仙湖的新真空太阳望远镜(NewVacuum SolarTelescope，NVST)的成像设备也在使用CMOS相机。因此建立一个天文CMOS相机测试系统，对于新购CMOS相机的验收以及现有CMOS相机的定期检测和维护有十分重要的意义。本文介绍了天文CMOS相机测试平台的硬件组成，并针对实际测试中对设备控制的需求，以及利用控制器对相应的设备直接控制，提出了基于TCP/IP协议以及串口通信的设计方案，利用C#编程语言设计了一套多线程并行的控制系统软件，实现各设备在局域网内的远程并行控制。通过对设备的运行测试，结果表明此系统能良好的控制各设备的正常运行，满足测试系统集成控制的需求。

关键词：CMOS相机测试平台；控制系统；远程控制；EMVA1288中图分类号：TP273 文献标识码：A文章编号：

# 0引言

抚仙湖观测站的新真空太阳望远镜(New Vacuum Solar Telescope，NVST)是目前国内最大的太阳望远镜，也是世界上最大的真空太阳望远镜，主要对太阳光球和色球进行高空间分辨率的成像观测和高光谱分辨率的光谱观测[l。而光电探测器是望远镜进行观测时不可或缺的终端。CMOS图像传感器作为光电探测器的一种，随着超大规模集成电路制造技术的发展，其性能不断提升。因CMOS相机具有动态范围大、读出速度快、功耗低、成本低等优点[2]，现在广泛应用于航空航天、生物医药、天文观测等诸多领域。

在天文观测领域，尤其是二维太阳成像探测领域CMOS相机被广泛使用，近两年抚仙湖观测站NVST的成像终端也在使用CMOS 相机。一方面，在采购CMOS 相机时，首先需要对它的性能参数进行了解，从而判断该相机是否能够满足整个观测系统的性能要求。但在实际应用中，由厂家提供的检测指标通常是以电视广播工业标准为标准的，往往缺乏天文观测实际应用所要求的指标。即使厂家提供天文观测所需的性能参数一般也是芯片厂家出厂前对其进行测试给出的典型值，由于生产工艺和半导体材料的变化，CMOS 相机性能参数的真实值会与给出的典型值有所不同，这会在波动相关光谱或计算成像等方法中引入误差[3]。因此，在进行成像系统设计前，必须对所用的CMOS 相机的性能参数进行测试。另一方面，相机在使用过程中由于元器件的老化等原因也会导致性能参数的变化，从而使光谱成像等引入更多的噪声，使观测数据产生误差，从而增加了分析处理难度，甚至会导致错误的结论。所以定期对天文相机进行测试和校准也是非常必要的。综上所述，建立一个以天文观测应用为目标的CMOS 相机测试平台，具有十分重要的意义。该平台可以用于新购相机的验收测试以及天文CMOS相机的定期检测，以此来保证天文CMOS相机性能满足天文观测的需求。

# 1天文CMOS相机测试平台概述

本测试平台是基于欧洲机器视觉协会发布的图像传感器和相机性能测试标准（European Machine Vision Association Standard 1288，EMVA 1288）而建立的。长期以来对于CMOS 的测试标准一直没有得到统一，几乎每个厂商都拥有他们的标准，这使得我们在不同相机间进行性能比价的时候，需要进行相应的参数转换。幸运的是在2005年以后，在绝大多数厂商的支持下——其中几乎涵盖了我们熟知的国内外知名厂商，例如 Andor、PI、Hamamatsu、pco等，建立了业内的统一标准。在测试标准中明确定义了相机模型，如图1所示，以及根据该模型进行测试的参数以及测试方法和流程[4]。

![](images/3aa78d4dc1b8eca3e6ad1b65439f2f334b3bec784f7ce8d403f211010cfce316.jpg)  
图1相机的物理模型(a)与单像元数学模型 $( b )$ （204号 Fig.1 $a$ Physical model of the camera and $b$ Mathematical model of a single pixel

图1(a)描述的是EMVA1288给出的相机物理模型。一定数量的光子照射到像元上，经过一段时间曝光后产生电子，这些电子通过电容极板转换为电压值，电压值经过放大和模数转换后输出为数字灰度值，即CMOS相机的数字输出信号。图1(b)描述的是EMVA1288给出的单像元数学模型。 $\mu$ 和 $\sigma$ 分别表示均值和方差，待测的未知量以红色标记。通过内光电效应，像元将光子数转换为相应的电子数，这个过程引入了暗电流噪声，然后一起被系统增益放大，之后模数转换时也不可避免的引入量化噪声[5]。

本项目旨在搭建一套符合EMVA1288标准的测试设备(包括软硬件)，并根据标准中的测试流程对各种参数进行相应的参数测试。目前本测试平台可以完成的测试参数如表1所示。

# 表1参数表

Tab.1 List of the parameters   

<html><body><table><tr><td>测试类型</td><td>强制与否</td><td>参考</td></tr><tr><td>量子效率</td><td>是</td><td>规定采用光源中心波长与FWHM波长</td></tr><tr><td>增益K，1/K</td><td>是</td><td>单位：DN/e及e/DN</td></tr><tr><td>暗噪声</td><td>是</td><td>单位：DN与e</td></tr><tr><td>DSNU1288</td><td>是</td><td>单位：DN与e</td></tr><tr><td>最大信噪比（SNRmax)</td><td>是</td><td>单位：比例或dB或 bits</td></tr><tr><td>SNR−1 max</td><td>是</td><td>单位：%</td></tr><tr><td>PRNU1288</td><td>是</td><td>单位：%</td></tr><tr><td>非线性误差LEmin，LEmax</td><td>是</td><td>单位：%</td></tr><tr><td>绝对灵敏度阈值</td><td>是</td><td>标示中心波长，用电子、光子或光子/um为单位</td></tr><tr><td>饱和容量</td><td>是</td><td>标示中心波长，用电子、光子或光子/um为单位</td></tr><tr><td>动态范围（DR)</td><td>是</td><td>单位：比例或dB或bits</td></tr><tr><td>暗电流</td><td>是</td><td>单位：DN/s与e/s</td></tr><tr><td>倍增温差(Td)</td><td>否</td><td>单位：K</td></tr></table></body></html>

该测试平台除了完成以上基本参数的测量，更主要的是完成相机特性的研究。例如相机非均匀性的研究，对于天文CMOS 相机而言，非均匀性是严重影响成像质量的重要因素，

由于非均匀性存在明显的时变特性[，因此很难通过传统的平场校正的方法进行校正，因此想通过本测试平台仔细研究非均匀性的时变规律，由此寻找消除非均匀性的解决办法。

# 2测试平台的搭建

测试平台主要包括四个部分，分别为光场生成部分、暗室部分、位移平台部分和环境监测控制部分，其构成框图如图2所示：

![](images/8f5dd5535028de1a75712357c68f950205000eace8fb514fb09e6c479f839049.jpg)  
图2测试平台框图Fig.2 Test platform schematic

光场生成部分的主要功能是用来产生稳定的均匀白光和均匀单色光，均匀白光用来测量相机的灵敏度、线性度和非均匀性等。而要测量不同光谱量子效率需要整个波长范围内的均匀单色光。因此光场生成部分主要由稳压电源控制器，光源，单色仪和积分球组成。稳压电源控制器为光源提供一个稳定可调的电源，防止因电流波动引起光源抖动，带来测量误差。我们采用的是Newport 公司的OPS-Q250 超稳压电源，其控制精度为0.1A，灯的波长和输出强度方面的稳定性，主要是通过尽可能保持灯外壳内卤素气体的温度和压力恒定来实现的。OPS-Q250电源为灯丝提供高度稳定的电流，从而将灯输出光强的波动保持在 $0 . 0 5 \%$ rms 以下，同时最大限度延长灯的寿命。灯泡采用的是欧司朗24V-275W的石英钨卤素灯泡，发光范围可以覆盖整个可见光波段。我们通过一个焦比为2.2的非球面透镜（平凸透镜）对光源发出的光进行准直，形成直径 $\mathrm { D } { = } 3 3 \mathrm { m m }$ 的光束，然后经过焦距$\mathrm { f } { = } 1 0 0 \mathrm { m m }$ 的凸透镜和焦距 $\mathrm { f } { = } 3 0 \mathrm { m m }$ 的凹透镜将准直光束聚焦后再次准直，形成直径为$\mathrm { { d } = 1 0 m m }$ 的光束入射到单色仪的进光口，其光路图如图 $3 ( a )$ 所示。光束通过单色仪内部的反射镜和光栅分光后从出光口射出，如图 $3 ( b )$ 所示，经过滤光片后进入积分球形成均匀单色光。

![](images/9a8a734b371c433c614f02f0c50c53aad0ae7e91a19c4de079664524aeabb50b.jpg)  
图3光束准直光路(a)和单色仪光路(b)Fig.3 a Beamcollimation path and $b$ light path of monochromator

暗室的主要功能是为CMOS相机提供一个无光照的暗场和相对稳定的测试环境。暗室整体尺寸为 $1 7 4 0 ^ { * } 1 0 0 0 ^ { * } 1 0 0 0 \mathrm { m m }$ ，并分为上下两个部分，下面部分用于放置干燥机和制冷机，并起到支撑作用，上面用于放置位移平台，如图4所示。暗室内壁由保温隔热层和空气循环层组成，保温隔热层中利用保温棉可以保证暗室内的温度不会随外界温度大幅度的变化，通过测试在室温为 $2 0 ^ { \circ } \mathrm { C }$ ，暗室温度为 $1 0 ^ { \circ } \mathrm { C }$ 时，自然上升 $1 ^ { \circ } \mathrm { C }$ 所需要的时间为5分钟，可以保证恒温条件下，对CMOS相机的测试。空气循环层中有半导体制冷机、加热机以及风扇可以快速的让暗室温度和湿度达到测试所需的要求，并保证暗室内的温湿度分布尽量均匀。

![](images/c01fc6c2955f5f3970d8a7aa3e1376d69c14eb411bea9d966117fbe4a178ee53.jpg)  
图4暗室结构图Fig.4 The structure of darkroom

位移平台的主要功能是为测试相机提供固定位置以及调节相机和积分球出光口的相对位置。位移平台主要由相机承载台、丝杆、支柱、滑槽、电机和运动控制模块组成。位移平台的X轴、Y轴和Z轴的最大运动距离为 $4 0 0 \mathrm { m m }$ ，最小运动距离为 $2 5 { \pm } 1 . 2 5 \mathrm { u m }$ 。位移平台的承载台可以实现对不同形状和体积的相机进行固定。通过控制位移平台的运动可以调节相机靶面和均匀光源即积分球出光口的相对位置，根据EMVA1288标准，相机靶面与出光口距离 $d$ 与出光口直径 $D$ 的关系为

$$
f = d / D = 8
$$

同时应该将CMOS相机靶面中心与积分球出光口中心对齐。此外，通过查阅文献和实际测试发现，距离积分球辐射光源出口平面较近 $( f { \leqslant } 5 )$ 时，照度均匀性较差，不适合在出口位置对光电器件进行测试实验，且积分球出口处温度较高，对器件测试精度也有影响；距离积分球辐射光源出口平面较远 $( f \geqslant 1 0 )$ 时，照度均匀性很好但是光照强度会降低很多。因此在 $f { = } 8$ 处更加适于对天文CMOS相机的测试。

环境监测控制部分的主要功能是对暗室内的温湿度进行实时监测和控制，以及对CMOS 相机靶面光功率的测量。温湿度监控主要用于CMOS相机暗电流对温度依懒性的测量以及恒温恒湿下性能参数的测试。上述已经介绍通过暗室的保温隔热层可以使温度在短时间内保持稳定，而温湿度监控系统可以使温度长时间的保持在恒定温度 $( \pm 1 ^ { \circ } \mathrm { C } )$ ，温湿度的监测通过温湿度传感器来完成，并通过网络传输回电脑端。温湿度的控制由半导体制冷机、压缩制冷机、加热机和干燥机依据温湿度传感器传回的数据共同完成，并利用风扇加速空气的流动使暗室内各个地方的温湿度相对均匀。CMOS相机靶面接收的光功率由光功率计进行测量，用于量子效率的计算。

将光场生成部分、暗室、位移平台和环境监测控制部分进行整体设计和安装，天文CMOS相机测试平台如图5所示，经过安装和调试后已经可以满足EMVA1288标准中相机测试条件，可以在实际测试中应用。

![](images/12769f0358d0287f8f3e1b9b5f3ba8e73652a8bf7c5c61bff5a586cbcb5c62a5.jpg)  
图5天文CMOS 相机测试平台Fig.5 Astronomical CMOS camera test platform

# 3控制系统的实现

CMOS相机测试系统平台虽然搭建完毕，但是因为使用了不同厂家的设备，其接口以及通讯协议都有所不同。如果使用各个设备的自带软件，将会大大增加操作难度，无法做到所有设备协同工作，因此实现对硬件设备的集成控制是非常必要的。为了方便集成以及后期设备的更换而不影响程序的运行，整个测试系统的电源开关通过网络继电器控制，以此来实现整个系统的远程控制。所有设备通过转接设备连接到路由器上，设置每个设备的IP地址为固定值，然后通过无线网络进行访问和控制。CMOS相机测试系统控制程序的设计与开发将实现控制指令与数据储存及显示相结合的一体化控制，这将大大提高测试效率，降低使用和学习成本。

# 3.1系统部署

CMOS相机测试平台控制程序部署在控制计算机上，位移平台、光源控制器等是标准的232串口通信，单色仪是USB通信，通过串口服务器和USB服务器将这些设备连接到交换机上。光功率计是TCP/IP通信，直接连接到交换机上，再通过交换机与控制计算机相连，如图6所示。控制计算机采用常用的Windows系统，控制程序基于MVC框架与C#语言进行开发。用户可以通过控制程序对CMOS相机测试系统平台实施远程操作，并对系统状态进行实时的监测。控制程序通过局域网实现对测试系统平台的远程操作。利用控制指令和执行结果与设备控制程序进行交互，实现整个通讯过程。

![](images/be2fd42dc297249f0905aaf4a5746cb92d3302225451503a108f33f9fe29da10.jpg)  
图6测试系统部署图 Fig.6 The deployment diagram of test system

# 3.2架构设计

为了在较短的时间内完成软件的开发，以及在使用过程中快速满足测试系统需求的变化，采用敏捷开发方式，首先快速搭建可以满足测试需要的软件，然后根据使用情况，调整原有功能的实现并增加新的功能。在控制系统搭建的过程中，为了方便以后系统的升级和功能的增加，而不影响现有功能的使用，主要通过降低系统耦合性的方式，提高其拓展性[8]。

由于CMOS测试系统仍然处于发展状态，后期可能需要更换光源控制器，调整温湿度控制系统，甚至存在更换操作系统的可能，因此需要系统架构能够满足功能和该功能相关计算机底层技术间的松耦合，所以将系统架构分为界面层、功能层和应用层如图7所示。

图7系统架构示意图 Fig.7 System architecture   

<html><body><table><tr><td>里苗</td><td colspan="2">数据显示、人机交互</td></tr><tr><td rowspan="3"></td><td>光功率计配置</td><td>温湿度控制</td></tr><tr><td>位移平台控制</td><td>数据获取</td></tr><tr><td>单色仪控制</td><td>光源控制</td></tr><tr><td rowspan="3"></td><td>超时管理</td><td>异步管理</td></tr><tr><td>时钟同步</td><td>系统输入/输出口</td></tr><tr><td>连接管理</td><td>线程管理</td></tr></table></body></html>

（1）应用层为实现具体功能提供了同步时钟、线程管理、远程通讯、事务处理机制等底层技术。

（2）功能层描述了光源控制器、单色仪、温湿度控制等的功能以及各个组件间的关系和交互行为。

（3）界面层用于接收用户输入的数据并将返回的数据和图表呈现出来，为用户提供一种交互式操作的界面。

为实现系统应用层、功能层和界面层的的分离，采用了容器-组件-服务模型。.Net提供了容器组件的实现，但由于设备硬件的差异和性能的不同，许多设备的SDK包不提供.Net环境的支持，所以选择自行开发。将系统的应用层、功能层和界面层分离具有以下优点：

(1)降低了层与层之间的依懒性。有利于控制系统后期的升级和改造。功能层与应用层的松耦合，可以减少后期软件调整的工作量。

(2)开发人员可以只关注整个系统的其中一层，在开发具体功能性应用时，不用关心应用层具体技术的实现，大大降低了维护成本和时间。

测试平台控制系统部署在控制计算机上，可以通过控制计算机上的控制界面直接控制测试平台上的设备，并返回执行的结果。也可以通过数据计算机发送指令，控制系统在接收到指令后进行解析，然后执行指令，间接控制测试平台上的设备。控制系统流程图如图8所示。

![](images/995266e738a265a5422232bd4cf83d307643a248b7efa3e967193eb64e91c784.jpg)  
图8控制系统流程图Fig.8 The flow chart of control system

控制系统的指令和硬件设备可执行的操作是一一对应的，测试平台包括光源控制器、单色仪、三维位移平台、光功率计和温湿度设备等，因设备比较多，控制指令也比较复杂，这里列举了部分常用的控制指令如表2所示。当网络连接正常时，根据控制指令执行的不同情况，控制系统会分别接收到执行成功、执行失败和指令错误三种结果。当网络连接中断时，发送控制指令会返回请检查网络连接是否正常。

表2常用控制指令表Tab.2 Common control instructions list  

<html><body><table><tr><td>指令</td><td>参数</td><td>说明</td></tr><tr><td>START/STOP</td><td>None</td><td>打开/关闭光源控制器</td></tr><tr><td>A-PRESET</td><td>Current value</td><td>设置光源控制器电流值</td></tr><tr><td>FILTER</td><td>pos</td><td>切换滤光片到指定位置</td></tr><tr><td>GRAT</td><td>pos</td><td>选择指定光栅</td></tr><tr><td>SetWave</td><td>Wavelength</td><td>将光栅切换到指定波长</td></tr><tr><td>Shutter</td><td>0/C</td><td>打开/关闭单色仪快门</td></tr><tr><td>Set X/Y/Z</td><td>pos</td><td>设置位移平台X/Y/Z轴位置</td></tr><tr><td>SetIntegrationTime</td><td>Integration Time</td><td>设置光功率计积分时间</td></tr><tr><td>GetPeakWave</td><td>None</td><td>查询峰值波长</td></tr><tr><td>GetPeakIntensity</td><td>None</td><td>查询峰值强度</td></tr></table></body></html>

# 3.3界面设计

为了方便测试人员操作，使用了图形交互界面如图9所示。界面设计以功能实现为基础，采用了极简风格，让测试人员对于功能一目了然，同时可以将数据信息快速的传递给测试人员。整个界面主要分为信息反馈、图表显示和设备控制三个部分方便测试人员快速了解和熟悉界面。在主界面中只列出了测试所必须使用的功能，如位移台的运动位置、单色仪的当前波长等。而在测试过程中较少使用的功能，如设备端口更改、位移平台加速度、单色仪滤光轮设置等，可以修改相应的配置文件来调整这些参数。

![](images/56ee569b5c78e7cdc35608afc9afc34b585728044c267023cd66b91c9d79c172.jpg)  
图9图形交互界面 Fig.9Interactionof the GUI

# 3结论与展望

天文CMOS 相机测试平台在功能上实现了对于相机的量子效率、增益、暗电流、信噪比、动态范围和光响应不均匀性等性能参数的测量，可以满足测试系统所需的测试条件。平台控制系统在多次运行和调试后，对于电源控制器、位移平台、单色仪和温湿度控制等的控制指令执行正确，数据返回正常，图表显示稳定。CMOS 相机测试平台和控制系统整体运行稳定、可靠，可以满足测试环境的要求。

天文CMOS 相机测试平台仍然处于发展之中，在控制系统的实现过程中，采用了敏捷开发方式，有良好的扩展性，可以在较低的开发周期内实现部署迭代，为以后测试系统已有功能的调整和新功能的加入打下了良好的基础。

# 参考文献：

[1]Zhong Liu,Jun Xu,Bo-ZhongGu,etal.Newvacuumsolartelescopeandobservations withhighresolution[J].Researchin Astronomy and Astrophysics,2014,14(06):705-718.   
[2]尚媛园,张伟功,宋宇,等.CMOS 成像器件性能测试方法的研究[J].激光与光电子学进展,2010,47(05):68-73. SHANG Yuan-yuan, ZHANG Wei-gong,SONG Yu,et al. Research on Evaluation Method of CMOS Imager[J]. Laser&Optoelectronics Progress,2010,47(05):68-73.   
[3]Rui Wang,ZhiXu,Zhen-YuJin,etal.Thefirstobservationanddatareductioof theMulti-wavelength SpectrometerontheNew Vacuum Solar Telescope[J].Research in Astronomy and Astrophysics,2013,13(1O):1240-1254.   
[4]European Machine Vision Association.EMVA Standard 1288:Standard for Characterization of Image Sensors and Cameras[EB].http://www.wmva.org,2016.   
[5］盆晓敏.基于 EMVA Standard 1288 的 CMOS 图像传感器测试系统研究[D].哈尔滨工程大学,2015. PEN Xiao-min.TheResearch of CMOS Image Sensor Testing System BasedonEMVA Standard 1288[D].Harbin Enginering University,2015   
[6]X.Y.Wang.Noise in sub-micron CMOS image sensors[D].University of Southampton,2008.   
[7]赫英威,李平,吴厚平,等.积分球辐射光源照度均匀性研究[J].应用光学,2012.33(03):548-553. HEYing-weiLPing,WUHou-ping,etal.OutputadianceuiforityoftegratingspheresourceJ].JoualofAppledOtic 2012,33(03):548-553.   
[8]陈宇超,金振宇,杨磊.NVST多通道高分辨观测系统软件设计[J].天文研究与技术,2016,13(01):75-81. CHEN Yu-chao,JIN Zhen-yu,YANG Lei.NVSTMulti-Channel High-Resolution Imaging System[J].Astronomical Research&Technology,2016,13(01):75-81.   
[9]Chiozi G,GustafssonB,JeramB,etal.CORBA-basedcommonsoftware for theALMAprojectC/ProcedingsofSE.2012: 43-54.

# The implementation of astronomical CMOS camera test platform and control system

Luo Zhiyuan1,2, $\mathrm { { X u } \mathrm { { J u n } ^ { 1 } } }$ ， Liu Liming1.2， Zhang Tao1 (1.Yunnan Observatories, Chinese Academy of Science, Kunming 65ooO1,China; 2.University of Chinese Academy of Sciences,Beijing,1OoO49,China)

Abstract: CMOS cameras are important solid-state imaging devices. As the performance of scientific CMOS cameras continues to improve, it is now widely used in scientific research. The imaging devices of the New Vacuum Solar Telescope (NVST) are also using CMOS cameras. Therefore, the establishment of an astronomical CMOS camera test system is of great significance for the acceptance of new CMOS cameras and has a high value for the regular detection and maintenance of existing CMOS cameras. This paper describes the hardware components of the astronomical CMOS camera test platform. Taking advantage of the direct control of the corresponding equipment by the controller,a design scheme based on TCP/IP protocol and serial communication is proposed to meet the requirement of equipment control in actual test. A multithreaded parallel control system is designed by using C# programming language to realize remote parallel control to each device in the LAN. Through the operation test of the equipment, the results show that the system can well control each equipment to operate and meet the requirement of the integrated control of the test system.

Key Words: CMOS cameras test platform; control system; remote control; EMVA 1288