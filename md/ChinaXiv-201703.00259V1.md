# SOLYS Gear Drive 太阳跟踪器的控制系统设计

梁少林’²，王咏梅」，石恩涛‘，王天放‘，王后茂」（1.中国科学院国家空间科学中心，北京100190；2.中国科学院大学，北京100049）

摘要：太阳跟踪研究的发展，向太阳跟踪器的控制系统智能化提出了更高的要求。以 SOLYSGear Drive 太阳跟踪器为仪器平台，创新性地提出利用路由器建立控制主机和太阳跟踪器在局域网内，以及局域网和互联网之间的通信,并以虚拟仪器开发软件LabVIEW为软件平台，综合调用百度地图应用程序接口API和指令脚本文件，设计了一套控制系统。实现对仪器的状态监测，指令控制，远程访问等。系统功能丰富，操作简单，界面可视化好，普遍适用性强。

关键词：太阳跟踪器；控制；局域网；模式；百度地图；脚本文件中图分类号：TP273.5 文献标识码：B

# Design of the control system of the SOLYS GearDrive sun tracker

Liang Shaolin12, Wang Yongmei', Shi Entao', Wang Tianfang' ,Wang Houmao' (1.National Space Science Center ,Chinese Academy of Sciences, Beijing 1Oo190, China; 2. University of Chinese Academy of Sciences, Beijing 1Ooo49, China）

Abstract: The development of the sun tracking research has put forward the demand to the inteligence of the control system of the sun tracker. Using the SOLYS Gear Drive sun tracker as hardware platform, a method that sets up the communication between the host and instrument via the LAN, the communication between the LAN and Ethernet by router is put forward innovatively, using the virtual instrument development software LabVIEW as software platform and utilizing the Baidu Maps JavaScript API and command script file comprehensively,a control system is designed .It can monitor the operation status of the instrument timely,control the instrument by sending command and visit the instrument remotely. The system have multiple functions and can beoperated conveniently， the interface’ visualization is straightforward， the applicability is extensive.

Key words: sun tracker; control; LAN; mode; Baidu Maps; script file0引言

自上世纪90年代以来，气象观测的进步以及太阳能利用的发展，向太阳跟踪提出了更高的要求。国内外研制了各种类型的太阳跟踪器，从单轴跟踪到双轴跟踪，从单一跟踪到混合跟踪[1]，太阳跟踪器不断朝着高精度全自动多功能的目标发展。目前，已经进入了自动化芯片时代，传感器和处理器相结合以完成太阳自动跟踪，控制系统成为其工作核心[2]。

然而，大多数太阳跟踪器并不配备专门的控制系统，或控制功能较为单一，操作不够智能，界面可视化差。因此，研制一种功能丰富，操作方便，界面清晰，普遍适用性强的太阳跟踪器控制系统，已经迫在眉睫。

作者简介：梁少林（1992-)，男，安徽阜阳人，博士研究生，主要从事空间环境探测技术的研究，包括光电探测系统设计，智能仪器仪表技术等。

# 1 仪器介绍

SOLYSGearDrive太阳跟踪器是由荷兰Kipp&Zonen公司生产的一种新型全自动双轴太阳跟踪器。内置GPS接收器以获取时间和地理位置信息，经过J.JMichalsky算法（1988）的处理得到太阳的位置信息，再经过四象限传感器的校准，实现指向位置的微调，其精度可达 $0 . 0 2 ^ { \circ }$ 。SOLYS Gear Drive太阳跟踪器采用齿轮传动系统，最大载重达$8 0 \mathrm { k g } .$ 最大扭矩达 $6 0 \mathrm { { N m } }$ ，可抵抗 $2 0 \mathrm { { m } / \mathrm { { s } } }$ 的强风。采用220V交流和24V直流两种供电方式，且内置加热器，工作温度范围扩展到${ - 5 0 ^ { \circ } C { \sim } 6 0 ^ { \circ } C }$ ，使太阳跟踪器能够在恶劣环境下工作。

# 2系统设计

# 2.1系统原理

目前，大多数太阳跟踪器都是采用

RS232串口实现与主机的通信，虽然能够全双工工作，但数据传输速率较低且距离有限，保密性差[3]。SOLYS Gear Drive 太阳跟踪器除了可以通过RS485串口实现和主机的通信外，还具有一个以太网RJ45接口，因此，可以将主机和仪器直连或者同时接入局域网，实现对仪器的状态监测和指令控制，若再接入互联网，还可以实现对仪器的远程访问。这种方式不仅传输速率高且距离不受限制，主机通过IP地址的形式访问仪器，因而保密性好。

![](images/ddb3583e6a98b24f6fe97c2c5577ba01113a5183142a857f5ee261d605074761.jpg)  
图1系统原理图

如图1所示，利用路由器建立局域网，将主机和仪器接入不同的LAN口，WAN口接入互联网。再通过主机正确配置路由器的DHCP服务器，以分配给主机和仪器各一个IP地址[4]。

打开TCP连接[TCPOpen Connection]地址 TCP 连接ID远程端口或服务名称 邊 错误输出超时毫秒（60000）错误输入（无错误）本地口（0）打开由地址和远程端口或服务名称指定的TCP网络连接。

利用LabVIEW数据通信中的TCP协议，可以实现太阳跟踪器和主机的局域网内通信，打开TCP连接函数如图2所示，除了要输入IP地址外，还要输入远程端口或服务名称，以指定 TCP 网络连接，SOLYS GearDrive太阳跟踪器的远程端口如图3所示，

服务名称 端口号  
mDNS UDP端口5353  
网络界面 TCP端口80  
NTP服务 UDP端口123  
跟踪指 TCP端口15000  
状态信息 TCP端口15001

利用TCP端口15000和15001，可以实现对仪器的监控。其中，TCP15001端口不支持主机命令或请求的发送，只支持仪器向主机的单方面信息传递，包括当前时间信息，经纬度信息，太阳位置信息，电机动作信息等，更新率为1秒。而TCP15000端口既支持主机指令的发送，也可及时地接收反馈信息，部分主要指令使用说明如表1所示。SOLYSGearDrive太阳跟踪器主要有两种工作模式：跟踪模式和标准模式。跟踪模式下仪器自动跟踪太阳，标准模式下仪器根据动作指令运动，完成设定的运动轨迹。模式的切换通过FU指令实现。

![](images/aad38955dbc8a23077a8888845d726805b3f400484c5dd5d6961d7ea1740f429.jpg)  
图2打开TCP 连接函数  
图3远程端口号  
图4控制系统结构图

表1控制指令表  

<html><body><table><tr><td>指令</td><td>作用</td><td>指令</td><td>作用</td></tr><tr><td>AM</td><td>设置电机加速度</td><td>M0*</td><td>移动某一角度</td></tr><tr><td>CL*</td><td>停止运动</td><td>MS*</td><td>获取电机状态</td></tr><tr><td>C0*</td><td>恢复出厂设置并重启</td><td>PA*</td><td>暂停某段时间</td></tr><tr><td>CP</td><td>获取太阳位置</td><td>P0*</td><td>指向某一位置</td></tr><tr><td>CT</td><td>获取世界时</td><td>RE*</td><td>开始太阳跟踪</td></tr><tr><td>FU*</td><td>设置工作模式</td><td>SI</td><td>获取传感器光强</td></tr><tr><td>H0*</td><td>使电机返回初始位置</td><td>SP*</td><td>设置太阳运行速度</td></tr><tr><td>IS</td><td>获取仪器状态</td><td>TI*</td><td>设置世界时</td></tr><tr><td>LL*</td><td>设置位置和气压</td><td>VM*</td><td>设置电机速度</td></tr><tr><td>MC*</td><td>设置电机工作电流</td><td>WA*</td><td>根据当前设置重启</td></tr></table></body></html>

注：上标为\*的指令只能在标准模式下使用

# 2.2系统结构

系统结构如图4所示，通过端口的选择可以实现系统功能的切换。若TCP端口选择15000，则可以向仪器发送指令，这里的指令来源有三种：自动更新，手动发送，脚本文件。若选择自动更新，则主机循环向仪器发送“CT,LL,IS,MS,SI,SE”六条指令，并将反馈信息实时在LabVIEW前面板显示。若选择手动发送，则可以在指令输入框输入指令，除了要符合仪器工作模式外，还要满足一定的格式要求。若将指令存储在脚本文件如txt文件中，通过对文件的读取，可以将指令取出执行，利用这个功能可以为仪器规划运动轨迹。

# 2.3前面板设计

基于LabVIEW的前面板界面设计如图5所示，此时TCP端口选择15000，仪器接受主机指令的发送，

![](images/e9fd3e80b05555f6e5a7d54de7e89aa2645ed4473eafe78ec0a2a1b46958603a.jpg)  
图5前面板界面

它主要分为以下几个功能模块：

(1)通信设置：输入仪器IP地址和TCP端口，建立主机与仪器的通信连接，并显示连接状态。

(2)密码保护：为“发送指令”功能设置密码保护（PRotection）。在前面板中选择PR 使能是否有效，若不使能，指令使用权限不受限制，若PR 使能，则只有输入正确密码，指令才会有效发送，进一步提高了控制系统的安全性。

(3)自动更新：若自动更新有效，则主机循环依次向仪器发送“CT,LL,IS,MS,SI,SE"六条指令，以获取“当前世界时和指向位置，经度、纬度和气压，仪器状态，电机状态（包括方位角电机和天顶角电机)，太阳光强，仪器序列号”等信息并用前面板控件显示。

其中，方位角和天顶角显示控件除了显示指向位置外，还可以将指向位置与当前太阳位置的误差及时计算并显示出来。光强值和四象限传感器值控件显示太阳光强值和四象限传感器经光电转换得到的电压值（一位有效位)，两者之间的转换关系与传感器参数有关。利用JavaScript 语言调用百度地图API，编写“输入经纬度显示位置”应用程序[5]，将其存储路径以统一资源定位符 URL的形式发送给 LabVIEW 中的浏览器控件[6],可以将经纬度信息实时在百度地图中显示出来。这里的经纬度默认情况下来自仪器获取的经纬度，也支持手动输入查询位置功能仪器状态显示控件显示当前仪器的工作模式、操作、自动或手动运行、内部加热以及调整情况等。电机状态显示控件用于显示电机的运动状态和工作电流等。

(4)常用指令：将常用指令以控件的形式表示，包括复位、WA、CO以及设置太阳运行速度等。其中，太阳运行速度为太阳跟踪算法中的运行速度，如选择“5min/day”，意思是使太阳一天的运行轨迹在5分钟内完成，此时，仪器的指向也会跟着运动。

(5)指令输入：在输入框中可以手动输入指令，以“PO”为例，输入“PO0150”，使方位角电机指向150度位置，其中0为方位角电机的编号。执行完成后将反馈信息和方位角及时显示，部分前面板如图6所示，

![](images/05b90fc2b278503b813a84708ecf61120c2e363339560e76cb0c3e0145ce3a98.jpg)  
图6PO指令下的部分前面板

(6)脚本文件：将指令存储在脚本文件如txt中，系统通过对文件的读取取出指令并发送给仪器执行，使电机按照规划的路径运动。一个脚本文件和执行状态如图7所示，该脚本文件共10条指令，发送间隔为60秒，设置电机最大速度 $2 . 5 ^ { \circ }$ /s,最大加速度 $3 . 6 ^ { \circ }$ /s²。

sunta-solys2-记事本   
文件（F）编辑（E）格式（O）查看（V）帮助（H)   
#orientation lap duurtest solysgd   
'TAG COUNT10   
'TAG INTERVAL 60   
#assume start in reference in function 1   
#azimuth 1 sequence,zenith 5 sequences at $\mathrm { { w } } 2 . 5$ and am 3.6. PO0367   
PO0-187   
P0090   
P0194   
PO1-8   
P0194   
PO1-8   
P0194   
P01-8   
PO194   
即本 计数 E[s] 剩余时间[5] CProgramFsKpZolsuta H 48

若TCP端口选择15001，则仪器会将状态信息实时发送给主机显示。如图8所示，格式是“信息种类；主机名称；日期；时间；太阳方位角；太阳天顶角；方位角电机位置；天顶角电机位置；纬度；经度；气压；状态码；运行状态；方位角电机状态，天顶角电机状态；校验和”，其中，运行状态以及电机状态以编码的形式表示。

反馈信息  
<-.status=1;SolysGD160018;2016/07/18:08:59:36；  
85.735627:6188381；150000900000；9.0002；10003;11300002008；26；6；A99E;  
<-.status=1;SolysGD160018;2016/07/18;08:59:37;-  
85.733086；61971500000000；90002；10003;130002；00；006；089FC;  
<status=1;SolysGD160018;2016/07/18:08:59:38:-  
85.730545;619471500009000902；110003;1300；000；6：；7460;

# 2.4远程访问

以控制主机作为远程访问的服务器，并利用LabVIEW软件自带的Web发布工具，可以将控制系统的前面板发布到互联网上，Web发布工具设置如图9所示，

![](images/ed6e364f5990b1698ec65311bf59276417464b67ce2b8e883885c2dbb60a4c06.jpg)  
图8仪器状态信息  
图9 LabVIEWWeb 发布工具

由于控制主机和仪器是通过路由器配置的局域网进行通信的，因此，若远程访问的客户端位于本局域网内，可以直接利用Web发布的地址URL对前面板进行访问，若客户端通过公网访问服务器，则需要通过路由器进行正确的端口映射[7]。控制系统远程访问面板如图10所示。

![](images/072fb75c448686b44e4d775bb07cecb3b62f843ee60d7eadb0ce5edc0b2664ba.jpg)  
图7一个 txt 脚本文件和其执行状态  
图10控制系统远程访问面板

4结论

SOLYSGearDrive太阳跟踪器控制系统利用以太网接口实现主机和仪器在局域网内以及局域网和互联网之间的通信，并以IP寻址的方式实现主机对仪器的访问，克服了传统串口通信速率慢，距离短，保密性差的缺点。基于LabVIEW设计了仪器的控制面板，功能丰富，且操作简单，界面可视化好。利用Web发布工具将前面板发布到互联网上，还可以实现对仪器的远程访问，极大地满足使用者的工作需求。此外，该系统只需要作简单的指令修改，即可应用于其他太阳跟踪器上，具有较强的普遍使用性。

# 【参考文献】

[1]朱志缸,阵纬,毛行奎.自动太阳跟踪器综述[C].第十八届全国电源技术年会论文集,2010:479-481.  
[2]赵建华,张婷婷.太阳跟踪控制系统的研究与设计[J].电子测量技术,2016,39(3):1-3.  
[3]向平,毕玉庆,程建民,陈方.基于ARM的太阳跟踪控制系统设计[J].计算机测量与控制,2009,17(6):1102-1105.  
[4]张勇,张德运,蒋旭宪,霍伟.路由器安全配置管理[J].计算机工程,2000,26(8):65-66.  
[5]弗拉纳根.JavaScript权威指南[M].北京:机械工业出版社,2007.  
[6]杨乐平.LabVIEW 高级程序设计[M].北京：清华大学出版社，2003.  
[7]傅丰,徐洪章.端口映射的分析与应用[J].天中学刊,2006,21(2):59-60.

联系方式：地址：北京市海淀区中关村南二条1号中科院国家空间科学中心梁少林收邮编：100190 手机：15201673051