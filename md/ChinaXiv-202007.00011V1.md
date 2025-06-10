# 基于ASCOM及PLC的随动天文圆顶控制

张冠军¹²，宋腾飞¹，程向明1,3,4，王晶星¹，张益恭1,2,3（1.中国科学院云南天文台，云南 昆明 650011；2.中国科学院大学，北京 100049；3.中国科学院天体结构与演化重点实验室，昆明，650216；4，云南省应用天文技术工程实验室，昆明，650216)

摘要：四川稻城县无名山址点是云南天文台新近选定的天文台址。为实现在无名山 50CM光学望远镜开展远程自动观测试验，需要对圆顶进行远程自动控制驱动开发。圆顶驱动基于ASCOM 标准，采用Modbus/TCP 协议连接PLC控制器，实现了圆顶的自动控制。重点介绍了圆顶控制原理和实现方法，结果表明，圆顶控制系统具有融合度高、使用方便的特点，满足远程自动观测的需求，对于相似的中小型观测系统具有一定的借鉴意义。

关键词：圆顶随动；ASCOM；PLC 控制；望远镜中图分类号：P111.2；TP273

天文圆顶是保护天文望远镜并协同其工作的机械装置，除了保护望远镜等观测设备免受外界雨水和灰尘等带来的损坏以外，还可减弱风载对观测设备的影响[2]。传统结构的天文圆顶是一个可旋转的带有可开闭天窗的建筑，常具有半球或超半球的外形，而较新型的天文圆顶则不拘于这种造型，但通常都具有天窗开闭和方位随动这两种基本控制方式。其中，圆顶的随动控制对于观测的影响较大，随着相关技术的进步，圆顶驱动和控制方式也在不断发展，控制方式从旋转变压器、脉宽调制等模拟技术[34演进到以单片机或可编程控制器（Programable Logical Controller，PLC)作为控制核心实现自动控制功能的数字式控制技术[5-8]。

无名山址点位于四川稻城县，是中国科学院云南天文台历时4年踏勘选定的候选天文台址，具备优良的天文观测条件9。拟在无名山址点的 $5 0 \mathrm { c m }$ 望远镜开展近地小行星高精度定位和测光观测，由于无名山海拔较高，到站观测较为困难，亟需实现远程自动观测。尽管目前远程自动观测技术已经有很大的进展，但系统的整合仍需要软硬件多方面的协调，需要定制甚至自行设计开发。稻城 $5 0 \mathrm { c m }$ 望远镜所配6m圆顶配有PLC控制系统，无法直接应用于远程自动观测系统，因此专门为其开发了相应的软件系统，使观测系统软件能够自如地实现圆顶控制，为实现小行星远程自动观测奠定了必要的基础。

# 1 ASCOM简介

ASCOM（Astronomy Common Ob ject Model，天文公共对象模型）诞生始于1998年，是由 Bob Denny 等人组成的 DC-3 Dreams 团队针对天文观测设备开发的一种接口标准。ASCOM的设计出发点在于，它在软件层和硬件层之间引入接口驱动层，在软件和硬件之间架起了统一对接的桥梁。天文设备生产商提供的设备驱动程序只要符合ASCOM标准，就可以很方便地将设备挂载到基于ASCOM开发的软件中，实现设备控制与信息传递。如今，望远镜、调焦器、相机、滤镜轮、圆顶、气象站等天文设备都被包括进来，ASCOM从一开始的望远镜脚本接口逐渐成长为兼容（几乎）所有天文设备的一整套接口协议，由于功能完善，用户众多，成为了天文设备控制的实施标准。

国内对于ASCOM的研究也逐渐深入，云南天文台、昆明理工大学、光电技术研究所等多家单位都基于ASCOM进行了望远镜自动观测方面的研究，实现了ASCOM标准的CCD、望远镜、圆顶等设备的控制开发[7,10-12]

对于稻城50cm望远镜圆顶控制开发，采用MaxImDL作为自动观测系统的核心软件，该软件支持连接 ASCOM 标准的相关设备，如望远镜（Telescope）、相机（Camera）、调焦器（Focuser）、滤光片轮（Filter）、圆顶（Dome）、气象站（Whether）等，有利于观测系统集成控制。

# 2 圆顶控制系统分析

无名山站点的 $5 0 \mathrm { c m }$ 口径的RC 望远镜配备了一个6.3m球形圆顶，圆顶天窗宽 $1 . 2 \mathrm { m }$ ，可实现 $3 6 0 ^ { \circ }$ 全方位转动。方位运动采用单相交流电机通过链传动实现，天窗为单帘式结构，采用三相交流电机通过链传动实现升起打开与关闭，圆顶通过基于PLC 的电控箱控制，可实现手动控制。同时，望远镜上安装了CCD相机、电子调焦器、滤镜轮、高性能工控机以及一架德国赤道式机架（German Equatorial Mount，GEM)。

由于望远镜采用德国赤道式机架，因此圆顶天窗开口方位与望远镜指向存在方位角偏差。这一问题随着 ASCOM 圆顶接口的开发完成而得到解决。这项工作是 2003年8月，由佛罗里达大学的约翰.奥利弗（John Oliver）完成的，他采用克里斯.洛德（Chris Lord）的圆顶指向公式，解决了指向偏差问题[13]。

圆顶控制器基于PLC实现，PLC型号为西门子S7-200 Smart。方位传动的减速机输出轴同轴安装了角编码器，角编码器信号进入PLC高速寄存器，在PLC内部进行计数，并换算为圆顶方位转角。方位还设置了零点，由距离传感器产生信号给PLC，PLC 得到信号后将方位计数器清零。天窗控制设置了两个限位开关，用以防止天窗过冲。

![](images/da408bb3908cbf67cf3c1db3ee40c79a62e7ab548d7e06cdc86b3817a17129b4.jpg)  
图1设备安装图

Fig.1 Equipment installation diagram

在进行近地小行星观测时，圆顶需要执行以下动作：观测开始前打开天窗；在望远镜跟踪目标时圆顶天窗始终应跟随望远镜的指向(称为"随动");观测结束或根据需要关闭天窗。

欲实现圆顶的随动，就必须实现以下功能：

1, 电脑与圆顶控制中心（PLC）建立通信;  
2, 圆顶控制指令的生成。

由于整个望远镜系统的机架、电子调焦器、CCD相机、滤镜轮等均支持 ASCOM，并且采用 MaxImDL软件实现图像采集，因此将圆顶融入到基于ASCOM构建的观测系统中是合理的技术途径。

PLC的通信可以有多种选择，这里采用Modbus协议。

# 3 圆顶控制软件设计

在ASCOM标准的支持下，各类设备与核心软件的连接方式大同小异，只需准备好相关设备的ASCOM驱动即可，在核心软件中选择相关的驱动即可完成连接。圆顶的驱动程序应基于ASCOM 协议将上层软件和PLC进行连接：ASCOM圆顶驱动程序（上位机）作为上层控制软件（核心软件）与PLC（下位机）连接的中间媒介，PLC作为下位机的控制核心，与PLC 的通信采用了ModbusTCP协议。图2展示了天文设备和各设备之间的交互关系。

![](images/e2801ca1f9ba60aff92a21ee0fc8002ee8043a2cf5ea715ff13479b305398294.jpg)  
Fig.2 Observation system architecture diagram

圆顶所有控制功能的实现，都在PLC控制端提供了相应的功能支持。系统原理见图3。

![](images/c55332868edc11d9e74cd3b472f8f1522d95497d2b456c835e34c93ec3570277.jpg)  
图2 观测系统体系结构图  
图3 圆顶控制系统原理图

Fig.3 The Principle of the dome control system diagram

利用 ASCOM平台，由控制软件获得望远镜的指向位置；圆顶天窗的位置获取需要将配备光电编码器与驱动电机的减速器输出轴同轴安装，之后通过PLC内部高速计数器记录编码器的转动脉冲数，并根据传动比进行换算即可获得圆顶位置参数。

圆顶控制软件包括：ASCOM圆顶驱动程序和下位机控制程序，两者的通信采用Modbus TCP协议。ASCOM驱动程序与下位机必须采用相同的通信协议。在VisualStudio 2013开发环境下，使用NuGet 安装HslCommunication库文件，通过调用库中的函数与下位机建立有效连接后，对下位机进行相关寄存器读/写。

# 3.1ASCOM圆顶驱动程序设计

ASCOM 圆顶驱动程序（以下称“上位机"）是上层控制软件与PLC（下位机）之间命令与数据流的“转换器”。驱动程序基于微软VisualStudio 2013、ASCOMPlatform X64和 ASCOMPlatform Developer 配置开发环境。在完成软件开发的环境配置后，首先需要了解 Dome 驱动的成员和方法。ASCOM标准为圆顶驱动开发提供了模板，模板中的C#成员和方法在ASCOM的开发文档和 Template.cs 中都可以找到，主要的成员函数有driverID，comPort，ConnectedState，ShutterOpen，Azimuth，Connected，domeShutterState 等；然后向驱动项目中添加Modbus TCP 协议文件，最后编写程序实现与下位机通信对接。在 ASCOM 圆顶驱动中提供与望远镜的接口函数，将 Dome 中的相关函数设置为true，圆顶驱动即可获取望远镜的指向位置。通过调用函数，返回目标的方位角，并将方位值写入下位机寄存器中。部分圆顶驱动程序代码如下：

#region IDome Implementation   
public bool CanSetAzimuth get { tl.LogMessage("CanSetAzimuth Get"，true.ToString(）; return true ; }   
}   
Public double Azimuth   
{ get 广 tl.LogMessage("Altitude Get"， true.ToString(）; int value $\mathbf { \Psi } = \mathbf { \Psi }$ ALT; HslCommunication.OperateResultwrite $=$ Dome.TcpClient.Write $( ^ { \prime \prime } 0 ^ { \prime \prime }$ value) ; if (write.IsSuccess) { testMassageBox.Text $\mathbf { \Sigma } = \mathbf { \Sigma }$ " Memory write successful"; } 1   
}   
#endregion

在 Modbus/TCP 通信协议的支持下，PLC 作为服务端，一方面为上位机提供数据服务，比如讲圆顶运行过程中的方位、天窗状态、编码器、PLC 控制器 $\mathrm { I } / 0$ 状态等传入上位机；另一方面，接收并执行上位机传送来的指令和数据，最终达到圆顶控制的目的。

# 3.2 PLC程序设计

下位机实现以下功能：手/自功能模式分离和选择、圆顶自动找零、方位位置计算、Modbus-TCP通信、天窗开/关、方位转动以及返回系统运行状态参数。在Modbus 协议下，下位机是被动应答的，需要完成以下几个功能，以配合ASCOM圆顶驱动程序工作：通信模块，高速计数器模块，手动控制与随动控制。部分功能模块的梯形图程序如图4所示。

![](images/deeae4a1e37299f0145c72d8b8399f2ecb14e4b275aaafda89bae226dae49c0a.jpg)  
图4 PLC控制程序  
Fig.4 The control program of PLC

西门子 S7-200 SMART 采用客户端-服务器方法，Modbus客户端设备（上位机）通过该方法向服务器（下位机）发出请求，服务器将响应客户端的请求。客户端可请求从服务器设备读取部分存储器，或将一定数量的数据写入服务器设备的存储器。下位机作为Modbus TCP服务器，关键点一是实现相应的逻辑控制功能；二是配置与上位机的通信功能，在 PLC 程序中所做的是配置 Modbus 地址与CPU 地址的映射关系。

表3.1Modbus与CPU 地址映射表  
Table 3.1 Address mapping table between Modbus and CPU   

<html><body><table><tr><td>Modbus starting address</td><td>Modbus ending address</td><td>CPU address mapping</td><td>Function Introduction</td></tr><tr><td>00001</td><td>00256</td><td>Q0.0—Q31.7</td><td>Switch value outputting coil</td></tr><tr><td>10001</td><td>10256</td><td>I0.0—I31.7</td><td>Switch value inputting contacts</td></tr><tr><td>30001</td><td>300056</td><td>AIWO—AIW110</td><td>Analog inputting channel</td></tr><tr><td>40001</td><td>4XXXX</td><td>Set the starting address</td><td>The holding register(V memory)</td></tr></table></body></html>

# 4软件试运行

系统于2020年初进行了运行测试，利用MaxImDL5.14软件测试了圆顶控制程序，在连续的功能测试中，运行稳定，基本满足随动要求。如图5所示，可以详细的查看圆顶运行的一些关键的参数。

品DomeControl □ ×   
Observatory ？ × 圆项天窗控制 运行状态   
Al Sky | Zoom Catalog Telescope Dome  Focus  StatusSetup 天窗开 STOP 天窗关 当前方位α 27. 53 Telescope Dome Simulator ASCOM Dome Driverfor Daocheng 目标方位β 50. 0 圆项方位控制 圆项方位手动调节 差值β-α 22. 47 Options Options Park 方位角 50.0 天窗状态 打开 Connect Disconnect Connect Disconnect 逆 顺 限位状态 上限位 Focuser 1 Focuser 2 时针 Home 时针 高度角 60.0 镜筒高度角 60. 0 No Device Selected No Device Selected HomePosition 0. 00 □跟随赤道仪 GoTo Options Options ParkPosition Connect Disconnect Connect Disconnect 编码器 PLC输出状态 Rotator 天窗打开 天窗关闭 读取 X No Device Selected 角度 27. 53 Options 计数器 1446 方位正向 方位反向 0 写入 ASCOM Options 1 状态消息 1日动找零 Connect Disconnect Connect All Disconnect Al 读取 写入 打目标位置 <> 关机

通过进行后续调试和系统试运行，使用编码器的理论数值和实际数值比对，对软件性能评价如下：

功能完备性：圆顶控制系统兼容手动控制和自动随动，具备圆顶控制的基本功能，可以实现远程操作和运行参数反馈，功能较为完备。

方位机动性：圆顶旋转一周约170s，单次随动过程转动角度不超过 $1 8 0 ^ { \circ }$ ，正常情况下可在85s内转至目标位置。

位置重复性：多次反复使圆顶方位停在固定位置，重复精度 ${ \ < } 2 0 ^ { \prime }$ ：

系统稳定性：圆顶随动到目标位置后，方位转动不会发生来回震荡现象，稳定性良好。

启停性：由于链传动的机械传动特点，存在一定的间隙，在方位换向时的误差较大，误差 ${ < } 8 ^ { \prime }$ ；在下位机接收到停止指令后，电机滑行所带来的圆顶方位变动 $\langle { 6 ^ { \prime } }$ ：

目标准确性：目标位置 $\pm 0 . 3 ^ { \circ }$ 内停止转动。

# 5结束语

基于ASCOM为稻城 50CM望远镜所配天文圆顶设计了控制软件，该软件可以将PLC控制的圆顶与其他天文设备一起连接到常用的天文控制软件中，从而可以方便地构建一套完整的自动观测系统，为实现近地小天体的天体测量远程自动观测奠定了基础。同时对于类似的中小型观测系统的圆顶自动控制提供了可借鉴的经验。

# 参考文献:

[1]姚正秋，周放．近代天文圆顶发展概况 [J]．天文学进展,2003,03):206-18.  
[2]徐江海，宫雪非．利用数值风洞实验进行四种天文圆顶的风载研究 [J]．光学学报，2015,35(05): 45-55.  
[3]沈磐安.60 厘米望远镜圆顶随动系统 [J].天文学报,1979,02):211-6.  
[4]杜宇．脉冲调宽型圆顶随动系统 [J]．光学精密工程,1995,05):116-20.  
[5]祝杰，曹凯，郑义劲．1.56m 望远镜天文圆顶电控的改造 [J].中国科学院上海天文台年刊,2009,00): 79-86.  
[6]陆栋宁，黄垒，陈颖为，etal.85cm 天文望远镜圆顶和天窗自动化系统研制[J]．天文研究与技术,2008,5(04): 386-91.  
[7]和寿圣，辛玉新，伦宝利，et al．基于 ASCOM 和 Modbus/TCP 协议的天文圆顶控制系统 [J].天文研究与技术,2017,14(03):356-62.  
[8]周福良，张乐年，郑启旺．西门子 S7-200PLC 在天文台圆顶控制系统中的应用[J]．机械制造与自动化,2009,38(05): 121-3.  
[9]SONG TF. Automatic Solar Seeing Observations at Mt.Wumingshan in Western China [J].SolarPhysics,2018, 293(2): 37.  
[10] 彭亚杰，季凯帆，梁波，et al.ASCOM 在选址望远镜远程控制中的可用性研究[J].天文研究与技术,2013,10(01): 49-54.  
[11]和寿圣，范玉峰，王传军．基于ASCOM标准的CCD 自动观测系统 [J]．天文研究与技术,2013,10(04): 386-91.  
[12]武鹏．天文望远镜的 ASCOM 开发技术研究[D]；中国科学院研究生院（光电技术研究所），2015.  
[13]https://ascom-standards.org/About/History.htm

# Automatic control of astronomical dome based on AScOM and PLC

ZhangGuanjun1,2, SongTengfei1,ChengXiangming1,3,4, WangJingxing1,ZhangYigong1,2,3 (1.Yunnan Observatories, Chinese Academy of Sciences, Kunming 65o011, China;2.Universityof Chinese   
Academyof Sciences, Beijing10o049;3.Key Laboratory for the Structure and Evolution of Celestial Objects,   
Chinese Academy of Science, Kunming 650216,China; 4.Yunnan Applied Astronomical Technology Engineering Laboratory, Kunming 650216, China)

Abstract: Mountain Wumingshan, Located in the Daocheng county, Sichuan province,was sited by Yunnan Observatory recently. For the purpose of carrying out remote automatic observation test with 5Ocm telescopes on mountain Wuminshan,we need to develop the driver for dome. The driver which was based on ASCOM standard and connected to PLC controllr with Modbus/TCP protocol, realized the automatic control of dome.Mainly introduced dome control principle and realization method.The results showed that the control system of the dome is characterized by its high alignment and convenience.Besides,it can meet the needs of remote and automatic observation and can be used as a reference for similar small and medium-sized observation systems.

Key words: Synchronization Dome; ASCOM; PLC controller; Telescope