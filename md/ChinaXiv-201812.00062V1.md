# 丽江2.4米望远镜的圆顶侧窗自动化控制系统

王德清1,2.3丁旭1伦宝利1,³王传军1,2.范玉峰 和寿圣1,辛玉新1,2.余晓光1,3(中国科学院云南天文台，云南 昆明 650216)

（中国科学院大学，北京100049)

(中国科学院天体结构与演化重点实验室，云南 昆明 650011)

摘要：丽江2.4米望远镜的圆顶采用方位随动和滑动式天窗的超半球结构，起初为改善因圆顶和望远镜终端电子设备引起的内外大气湍动设计了大面积的多组机械式侧窗。但由于高平台手动操作危险、缓慢、不精确且易坏，为解决侧窗的稳定的多组自动控制，开发了基于STM32板的嵌入式设计的圆顶侧窗自动控制系统，利用WiFi模块、串口模块和手柄，实现侧窗的远程控制和多通道控制;同时结合气象数据、圆顶位置信息等使系统能根据气象阈值进行预警、自动开合、并使风对望远镜振动影响尽量小。侧窗控制系统的设计也可满足上层系统集成的需要，系统稳定可靠，能满足侧窗的自主运行与人为可控。

关键词：自动化控制圆顶侧窗嵌入式 STM32

# 0.引言

天文圆顶应满足在光学望远镜工作时，能让天体辐射自由而尽量少畸变地进入接收器，并尽量避免风振动、温度变化、外界不利天气等[1]。传统圆顶如我国2.16 米望远镜圆顶室封闭性较好，但相对通风性较差,会引起圆顶内外的温差;后来大多望远镜都吸取了前期圆顶建造的经验：如VLT，在圆顶下部设置了大面积通风口；4.2米的WHT 除增开大面积的百页窗外，百页窗还可根据外界风力、风向控制窗口开合与方向；斯隆巡天望远镜以及一米红外太阳望远镜的挡阻风板对减小风振起到较好的效果。

丽江2.4米望远镜通过如预留了如大面积多组侧窗这样的举措来进行热控制。原来设计的16扇大面积的侧窗，需通过人工摇动机械摇柄拉动细钢丝来开关侧窗。一则操作平台较高且费时，有人身安全隐患；二则细钢丝易绞合到一块且易断。同时现阶段侧窗要么全开，要么全关，仅依靠人为经验未考虑降水、云量、风速、湿度等外界气象因素的影响且没有气象预警[4]。风速对望远镜的扰动也影响到观测，通常天文望远镜只能在四级风之下才能正常工作[5]。考虑到上述实际情况，因此开发了圆顶侧窗的自动化控制系统，能够实现自动控制、多通道控制，并依据气象条件智能化地控制侧窗的开合：在满足所有气象设定阈值且风速较小的情况下，侧窗全部打开；一旦超过某一气象阈值侧窗就全部关闭；而满足阈值且风速较大的情况下，挡风即迎风面关闭只打开背风面侧窗能极大地降低对望远镜的扰动。通过精确化的自动化控制，使系统运行稳定可靠，提高望远镜的安全操作性能与观测效率。

![](images/5eb7f853be10bad2997b7b2ae945a837263dea56bd638f255ddffc89f9c11c10.jpg)  
图1丽江2.4米望远镜圆顶结构[]  
Fig 1 Thestructure of dome at Lijiang 2.4m telescope

# 1.机械改造

侧窗有不同形式改造形式，在目前基础且较小改动的情况下，一方面要实现侧窗的可行性与自动化控制，一方面也要考虑不影响圆顶整体结构与外观。之前曾考虑不需要改动原侧窗仅用电机驱动钢丝的方案，但存在细钢丝绞合到一块的情况；或考虑改造为可调风阀的百叶窗形式，但密封性不太良好。最后选用了依靠固有的圆顶钢架与龙骨，在圆顶外侧依照圆顶曲率搭建曲面滑动导轨，侧窗在此导轨上向两侧开合，然后利用电机连接链轮驱动链条。

![](images/b95e5f61e773d411b6da7ec506efeb3908825b78fcab44731728ba70f9241a59.jpg)  
图2原来的侧窗（左）与现改造后的侧窗外观（右）

Fig 2 the old Windows-Blinds (left） and the profile of new Windows-Blinds (right)

# 2.侧窗控制系统设计概述

目前侧窗共有16扇，将分8组控制开关运动，每个节点控制两扇侧窗，这样将减少控制网络的负荷。丽江2.4米望远镜的超半球圆顶的内径达到13米，因此若选用串口线或是有线以太网将至少长20米，且线缆过多，因此根据圆顶结构选用无线网络进行WiFi控制。除一对一控制外，还要解决一对多的控制，解决单独控制与整体控制的问题；考虑到现场调试与维护，除远程网络控制外，还要考虑其他控制通道问题；同时需要网络稳定性以及掉电等实际情况；并能够有效根据电机调节步长与速度等。

因此，侧窗的控制系统架构采用了基于 STM32的嵌入式控制板现场控制、无线网络通信的方式，可通过USB转串口或者手柄实现本地调试与控制。它包括上位机模块、WiFi 模块、CH340G 模块、手柄控制模块、主控芯片、电机驱动模块和电机模块，以及外围辅助电路几大模块。上位机即远程控制主机，它作为Server端发送命令和接受下位机的状态信息，同时在网络上调用气象与望远镜数据库，解析字符串与比较阈值来判断圆顶及侧窗的自动化控制，并提供警报便于人工干预,其系统架构如图3所示：

![](images/c581fb18dc40748d5ba57d551027fa40d4846e844ec4cce38dc0d6daa673a7b5.jpg)  
图3侧窗自动化控制构架图

Fig 3 The architecture of Side-Windows control system

# 3.下位机设计

# 3.1下位机硬件设计

下位机电路的主控芯片采用基于ARMCortex-M内核的32 位微控制器STM32F103C8T6[7]，它具有三个串口端，我们分别采用其串口1通过CH340G 和计算机通信；串口3和WiFi模块相连；通过中断GPIO口和手柄电路相连；通过PWM口、普通GPIO口和电机驱动模块相连。WiFi使用ESP8266 模块①，它内置了TCP/IP 协议栈，其通信通过串口USART3与STM32来完成。ESP826 模块具有 STA、AP、 ${ \mathsf { S T A } } { + } { \mathsf { A P } }$ 三种模式，选用STA模式，ESP8266 模块通过路由器连接到网络，实现无线网络通信。

![](images/8cf2172f25c4be9a2961b8249f8463ed529bf6109965be85aef2b984a7c03d5b.jpg)  
图4ESP8266控制模块  
Fig 4 ESP866 control module

CH340G为USB转串口模块，通过它将下位机程序烧录到STM32板卡中。手柄模块包含了手柄电路、RJ11、PC817光耦电路几大部分，它起到了手柄电压的转换与信号隔离的作用，并将控制信号稳定地连到STM32的IO口。

电机驱动模块为通过DRV8825芯片来驱动两个步进电机，通过电机步数来调节到位与否。STM32通过PWM口、普通GPIO口和电机驱动模块相连。STEP引脚产生脉冲供给驱动芯片，其脉冲由STM32内部PWM生成；MO、M1、M2为细分设置引脚，DRVEN为连接至STM32做使能设置，DIR为驱动方向控制。电机采用轴径为8mm、电流为2.5A插线式两相四线57BYGH步进电机，电机走一步是 $1 . 8 ^ { \circ }$ ，一圈为200步，采用全步进的方式来驱动，通过调节PWM的时钟频率与脉冲数来调节电机的速度与步长。

![](images/d1a993a8e4fbac53f929583b25a29497f268b7531e85922be5280640c7ff9e84.jpg)  
图5步进电机驱动drv8255模块Fig 5 The drv8255 stepper driver

# 3.2下位机控制板软件设计

下位机软件利用STM32库函数V3.5，KeilMDK5来开发。侧窗控制板的软件主要包含板卡的如GPIO、串口、定时器、中断等基本设置、WiFi模块连接、电机驱动底配置、协议定义、网络通信等控制。

下位机软件中自定义数据帧格式为“：F\*#”，其中“：F”表示帧头，“#”表示帧尾，中间部分“\*”表示帧内容。接收到上位机的是第一字符是“：”，则表示接收到的是有效数据。最后一个结束的是“#”，表示一帧数据传输完成，等待下一帧数据传输。解析第三个字符并执行相关指令与内部调用的函数。控制指令表示如下：

表1指令控制集  
Tab 1 The instruction set of Side-Windows control   

<html><body><table><tr><td>指令格式</td><td>指令含义及调用函数</td></tr><tr><td>A</td><td>WiFi 名字设置 SetWifiName()</td></tr><tr><td>C</td><td>WiFi密码设置SetWifiCode()以及侧窗全关;</td></tr><tr><td></td><td>电机全开</td></tr><tr><td>Q</td><td>电机使能 ControlMotor()</td></tr></table></body></html>

<html><body><table><tr><td>S</td><td>电机步长调节</td></tr><tr><td>V</td><td>设置电机速度SetSpeed()</td></tr><tr><td>W</td><td>IP 设置 SetIP()</td></tr><tr><td>Y</td><td>设置电机速度 SetSpeed()/SetSpeedCover()、设置用户名 SetNameCode()、设置WiFi 连接 SetWifiConnect()</td></tr><tr><td>+</td><td>设置单个步进电机运转方向，用于单个模块打开 ControlMotor()</td></tr><tr><td></td><td>设置单个步进电机运转方向，用于单个模块关闭 ControlMotor()</td></tr><tr><td>？</td><td>查询 Socket连接及编号</td></tr></table></body></html>

WiFi 设置界面用于下位机，主要是将服务器端的IP、端口、使用路由、密码这些字符串处理转换为相关格式写入Flash中，利用了联合体(union)共享内存和内存长度为其最大成员的内存长度这两个特点，即使断电也不会丢失这些信息：在联合体中包含结构体，结构体中含有WiFi设置界面里的Name、Code、IP三个变量成员，通过指针将上位机传递到union，其长度为最大成员长度，然后利用Flash接口函数写入。

控制软件首先对GPIO、时钟、定时器、中断、串口引脚与串口通信参数设置完成初始化设置；再对两个drv8255引脚进行设置。完成这些基本设置后，程序对串口1、3的布尔类型的数据帧标志位bFlagRun、bMoterRun 分别初始值置为false；然后两个串口等待数据的到来。接收到一帧数据时，数据帧标志位被置为true，接着解析数据帧内容，如果符合自定义指令，则执行相应操作；如果不符合则直接清除缓存且把标志位置为false。最后检测到数据帧尾为"#”，则完成整个数据帧的处理，将缓存清除且置标志位为false，然后等待下一帧数据到来。其控制流程框图如图6所示：

![](images/36575b58efd8cfbca6beedc6133385812970144be297d7356efb700d34bc1158.jpg)  
图6：控制流程框图  
Fig6The control flow of STM32 board

# 4．上位机控制软件设计

STM32控制板通过WiFi模块 ESP8266与上位机采用TCP 通信。STM32板即下位机作为客户端，上位机作为服务端，一个控制主机控制8块STM32板。上位机软件在Win7下采用C#4.0来编写，使用Visual Studio 2010集成开发环境来开发。

上位机主动通过执行及查询指令到STM32板，STM32板则执行相应指令动作，以及把实时状态反馈回上位机。控制板自动通过AP获取一个该网段的IP，考虑到WiFi的IP会因断电或信号强弱等情况会变，使用字典（Dictionary $\mathrel { \mathop  }$ ）将连接的相关字符串 String与 Socket 绑定到一块,同时每一个字符串 String 对应一个线程,它通过哈希表的键值映射来实现[。8个节点通过8个线程来管理，每一个节点的断开与连接不影响其他节点。

![](images/78012728073434ce401c6d9260d26ddfa55ada679a4b19c133b35eb390db3ef3.jpg)  
图7WiFi设置界面（左）与上位机控制界面（右）

Fig 7WiFi setting interface (left） and the host computer interface (right)

上位机Server端界面在启动后，在线列表中列出了连接到的下位机Client端的IP情况，每一个Socket有对应的线程来管理。主界面主要包含状态的查询与命令的发送。我们可以控制一个板卡节点来单独开关侧窗，也可通过遍历String来绑定Socket发送开关指令到每一个节点上。可能因节点IP的变动，要通过节点的查询指令“:F?#”的反馈字符串“:FN#”的“N”值截取来判断 IP对应的侧窗编号。

# 5.侧窗控制模式

侧窗有四种控制模式：手柄控制、本地串口控制、远程控制和自动控制。前三种控制介绍如上，而自动控制，调用了望远镜及气象数据库：降雨、云量、湿度、风速风向等气象参数都影响到圆顶天窗、侧窗的开合与天文观测。我们利用望远镜已有的望远镜及气象数据表 TCSStatusNow9]，通过定时器每五分钟读取一次最新气象参数以及望远镜方位值。如果望远镜方位值为null，表示望远镜没有开启或者出错，执行自动关闭。在望远镜方位有数值情况下，通过云量、降水、湿度、风速气象参数开启和关闭的阈值设定来自动判断侧窗的开关，一旦上述任何一个气象参数值超过其设定关闭阈值就自动关闭侧窗；且在天窗打开时通过蜂鸣器来进行报警，便于人工立马对望远镜进行保护操作。满足以上所有这些开启阈值（无降雨、云量低、湿度低、风速较小 $\mathrm { { V } { < } } 4 \mathrm { { m } / \mathrm { { s } } } \mathrm { { . } }$ )，将打开所有侧窗。其他条件符合且风速适中 （ $ { \langle 4 \mathrm { m } / \mathrm { s } \mathrm { ~ ‰ ~ } \rangle }$ ）时，自动开关将较为特殊：迎风面侧窗关闭，背风面侧窗打开。

大天窗编号为0,侧窗节点编号顺时针开始从1到8；则第个N节点对应的角度0N为：

$$
\theta _ { N } = \mathrm { A z } + \mathrm { N } * 4 5
$$

因为气象参数风向范围为 $0 ^ { \circ }$ 到 $3 6 0 ^ { \circ }$ ；而望远镜方位为 $- 1 8 0 ^ { \circ }$ 到 $3 6 0 ^ { \circ }$ ，需要保证值范围的一致，因此需要把0N转换到0到 $3 6 0 ^ { \circ }$ 范围，反求出最靠近风向的节点N来。再根据查询节点编号“：FN#”的N数值来执行迎风面和背风面的侧窗开合。

# 6.结果和讨论

圆顶侧窗自动控制系统方案解决了侧窗机械的改造与驱动、自动控制和多组控制、智能判断等问题。系统通过WiFi模块、CH340G、手柄实现侧窗的多通道控制；调用气象与望远镜数据库及阈值判断，该方案实现了丽江2.4米望远镜圆顶的侧窗自动化与智能化控制，并能有效减少风对望远镜的振动。经过两个月的试运行，系统稳定、可靠，能满足侧窗的自主运行与人为可控。致谢：感谢张瑞龙老师、业凯老师在圆顶侧窗机械设计与安装上给予的帮助。

# 参考文献：

[1]姚正秋,周放.近代天文圆顶发展概况.天文学进展，2003，21(3)：206-218.[2]毛同生，蒋世仰.2.16 米反射式望远镜圆顶室[J].天文学报，1992,33(2)：220-228.  
[3]李志，宋腾飞，许骏.挡风板及其在NVST上的测试结果［J].天文研究与技术,2012，9（3）:329-334.  
[4]余晓光，辛玉新.一种天文圆顶气象气象报警系统：中国，  
CN207650424U[P].2018-07-24.  
[5」.黄佑然，许敖敖.实测天体物理学[M].北京:科学出版社,1987：354-363.[6]范玉峰.中型望远镜观测系统集成[D].昆明：中国科学院云南天文台,2014.[7]刘火良,杨森.STM32库开发实战指南：基于STM32F103[M].机械工业出版社，2017: 17-23.  
[8]姜晓东.C#4.0权威指南[M].机械工业出版社,2011：298-342.  
[9]王传军,范玉峰,易卫敏.丽江2.4米望远镜 TCS Sequencer 程序的设计与开发［J]．天文研究与技术,2013，10（4)：378-385.

# The Auto ControlSystem of Dome's Window-Blinds at Lijiang 2.4m Telescope

Wang Deqing12.3, Ding $\mathsf { X u } ^ { 1 , 3 }$ ,LunBaoli1，WangChuanjun123,FanYufeng1，Hehoushenin Yuxin123,Yu Xiao-guang1,

(1Yunnan Observatories, Chinese Academy of Sciences, Kunming 650216, China) (2 University of Chinese Academy of Sciences, Beijing 100049, China) (³Key Laboratory for the Structure and Evolution of Celestial Objects, Chinese Academy of Science, Kunming 650011, China)

Abstract:Super-hemispherical dome with tracking and sliding devices was built for Lijiang $2 . 4 \mathsf { m }$ optical telescope,and windows-blinds as an important parts of dome,were designed to reduce the turbulence which was caused by enclosure itself and electric devices. But windows-blinds were manipulated by man through rocking steel wires with risk factors in high platform. Moreover they would cost time and be broken easily. Now they can be controlled automatically after transforming their mechanical structure.The auto control system's architecture is that host computer controls the embedded system in STM32 board through interface of WiFi module,serial port,or handles to realize multi-channel control.The STM32 board,as the slave part, provides the PWM to drv8255 to drive the stepper motor. In this way, we realize the automatic control, and further on we call telescope's DB and set the threshold of weather parameter in orderto control the dome more accurately.Through a month of trial, the system is stable,reliable,and can meet the needs of observation.

Key Words:Automation control; Dome's Windows-Blinds; Embedded System; STM32;