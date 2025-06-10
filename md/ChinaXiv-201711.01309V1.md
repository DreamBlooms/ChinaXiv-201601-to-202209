# CN 53-1189/P ISSN 1672-7673

# 基于ASCOM和Modbus/TCP协议的天文圆顶控制系统

和寿圣，辛玉新，伦宝利，范玉峰（中国科学院云南天文台，云南 昆明650011)

摘要：圆顶是天文望远镜系统的重要外围设备，随着望远镜技术的发展，圆顶控制技术得到不断进步。为实现云南天文台自动差分像运动大气视宁度监测仪完全自动化，开发了一套基于ASCOM和Modbus/TCP协议的圆顶控制系统。结合ASCOM天文技术标准和Modbus/TCP 协议规范，详细介绍了系统的结构原理和实现方法。实测结果表明，系统具有较好的稳定性和兼容性，完全满足自动观测的需求，为中小型天文望远镜圆顶设计提供了经验和方法。

关键词：天文圆顶；ADIMM；天文公共对象模型；Modbus/TCP中图分类号：P111.2；TP273 文献标识码：A 文章编号：1672-7673(2017)03-0356-07

圆顶是天文望远镜系统的重要外围设备，具有保护望远镜使其免受风吹、日晒、雨淋等恶劣天气袭击的功能。随着地面光学天文望远镜研制技术的迅速发展，与之配套的天文圆顶技术也越来越受到关注[1]。首先，圆顶类型越来越多。传统圆顶包括一个可以开启和关闭的天窗[2」，一般可以旋转随动以辅助望远镜跟踪观测。如今各种综合考虑了改善圆顶视宁度、减小风阻和振动等因素的圆顶陆续被研制出来，天文圆顶产品越来越丰富。其次，圆顶控制技术越来越成熟。随着科学技术的不断进步，各种智能控制技术和通信技术在圆顶控制上得到了完美的应用，圆顶已经步入智能化时代。

云南天文台自动差分像运动大气视宁度监测仪（Automatic Differential Image Motion Monitor，ADIMM)的圆顶采用蚌壳折叠式结构，该结构具有成本低、结构简单、控制方便等特点，被广泛应用于中小型天文望远镜系统。由于生产商未提供控制系统，云南天文台自行研制开发了一套基于Modbus/TCP 协议的圆顶控制系统，并在此基础上增加了天文公共对象模型①（Astronomy Common Object Model,ASCOM)支持，使其具备更好的兼容性和可扩展性。

# 1协议介绍

天文公共对象模型是 Bob Denny 为首的 DC-3 Dreams 团队为方便天文控制面板（Astronomer's ControlPanel，ACP）②和 MaxImDL软件控制望远镜、照相机、滤光片等设备于1998年提出的一个天文接口标准，它在控制软件和设备之间引人驱动层，为天文软件供应商和天文仪器厂家提供了一个免费互通的中间桥梁。如图1，相对于单一内嵌控制代码和未开放的可扩展驱动天文控制模式，它的优点显而易见：一方面，设备生产商只要提供符合天文公共对象模型标准的驱动程序，就可以将自己的设备挂接到天文公共对象模型平台；另一方面，控制软件只需要针对天文公共对象模型进行操作，无需考虑不同厂家、不同类型设备的特殊性[3]。

Modbus 是 Modicon于1979 年提出的一种开放的工业现场总线协议，1999 年该公司公布了基于以太网的 Modbus/TCP协议，2008年4月，我国正式发布了国家标准GB/T19582-2008《基于Modbus 协议的工业自动化网络规范》[4]，使其在我国工业控制领域得到了更为广泛的应用。Modbus/TCP 是基于以太网的传输协议，以太网的链路层校验机制可保证数据包传递的正确性，Modbus/TCP 数据帧不再采用额外数据校验，只要严格遵守协议规定的应用数据单元（Application Data Unit，ADU)格式（如表1)就能在以太网上实现数据传输[5]。

![](images/3d8112d74f7d7977364a50be20d4300825e0558631005d8aa7f4c71fa0f1cfc0.jpg)  
图1天文公共对象模型示意图Fig.1ASCOM schematic

# 2系统原理

系统结构如图2，根据蚌壳折叠式圆顶具有左右双开结构的特点，采用可编程逻辑控制器作为圆顶控制器（选择施耐德ZelioLogic系列产品SR3B261BD 和以太网通信接口模块 SR3NET01BD）,通过左右驱动器分别控制左右电机实现圆顶的开合动作，开启和关闭限位开关具有运动限位和状态反馈双重功能。圆顶工作模式有两种：一是通过计算机自动控制，采用Modbus/TCP协议实现；二是通过控制面板手动控制，通过按钮直接手动控制圆顶。气象站是自动圆顶必备的外围设备，通常也可以通过计算机连接气象站实现，但考虑其实时性和可靠性，这里采用气象站的雨雪信号直接触发圆顶控制器的方式。

表1Modbus/TCP应用数据单元帧格式Table1Modbus/TCP ADU  

<html><body><table><tr><td>帧结构</td><td>域</td><td>长度</td><td>描述</td></tr><tr><td>MBAP 帧头</td><td>Transaction</td><td>2</td><td>事物标识码, 标识帧次序</td></tr><tr><td rowspan="5"></td><td>ID</td><td></td><td>协议标识符，0</td></tr><tr><td>Protocol ID</td><td>2</td><td>为 Modbus 协议</td></tr><tr><td>Length</td><td>2</td><td>数据总长度 (Length+2)</td></tr><tr><td></td><td></td><td></td></tr><tr><td>Uint ID</td><td>1</td><td>单元标识符</td></tr><tr><td>功能码 数据</td><td>Function Code Data</td><td>1 Length</td><td>功能码 发送数据</td></tr></table></body></html>

系统设计充分考虑了圆顶操作的安全性和稳定性：首先，为确保维修人员的安全，控制面板手动开关按钮采用不闭锁常开按钮（按下动作，松开停止)，并且在圆顶内部署了相应的急停按钮，紧急情况可立即停止圆顶运动，最大程度地降低夹伤事故风险；其次，为保护望远镜使其免受恶劣天气袭击，设置自动模式的双层保护：第1层是气象站保护，第2层是通讯故障保护，即设置60s自动关闭功能，60s无动作请求自动关闭圆顶，避免控制软件或者网络通讯等造成的圆顶关闭故障；再次，为有效防止相互碰撞，左右圆顶不能同时动作。

![](images/9c2ed2d85436ab961611021f73b02db477dfdd950f725ceb02daef3964dd2f22.jpg)  
图2系统结构示意图Fig.2System schematic

# 3软件设计

软件设计包含可编程逻辑控制器控制程序和计算机端天文公共对象模型驱动两部分。

可编程逻辑控制器控制程序采用功能模块图语言编写，考虑将来Linux版本天文公共对象模型控制软件的开发，程序参考了云南天文台伽马暴与光学暂现源观测系统（Burst Optical Observer andTransient Exploring System，BOOTES) $^ { [ 6 ] } 4$ 号站圆顶控制并使之相互兼容。如图3，程序通过对8个数字输入量的逻辑判断，实现对4个继电器的输出控制，从而实现圆顶的开合功能。输入I1为自动/手动切换信号，输人I2为开启/关闭圆顶信号，输入 $\mathrm { I } 3 \sim \mathrm { I } 6$ 为限位开关（左开限位、左关限位、右开限位和右关限位），输入I7为气象信号，输入I8为急停按钮。4个输出信号分别控制左右圆顶电机的运动。

![](images/a173ebcc4bbcf0fdf7f8ca46874fad08f28cf374919ada4cc41fbbcfc1ea417e.jpg)  
图3可编程逻辑控制器时序图  
Fig.3PLC Program diagram

计算机端天文公共对象模型驱动在微软visual studio 2010集成开发环境下采用C#语言编写，天文公共对象模型平台选择 ASCOMPlatform6SP2。圆顶驱动实际上是由符合天文公共对象模型标准的各种属性和方法组成的Dome 类。如表2为Dome 类的一些常见属性和方法，Connected 为连接属性，Altitude、Azimuth 和 CanSlave 为圆顶随动属性，CanSetShutter、ShutterStatus 为天窗操作属性，OpenShutter（）、CloseShutter（）为天窗操作方法。

表2Dome类常用属性和方法  
Table 2 Common Properties and methods of Dome Class   

<html><body><table><tr><td>名称</td><td>描述</td><td>名称</td><td>描述</td></tr><tr><td>Connected</td><td>连接属性</td><td>CanSetShutter</td><td>是否带天窗</td></tr><tr><td>Altitude</td><td>高度角</td><td>OpenShutter()</td><td>开启天窗</td></tr><tr><td>Azimuth</td><td>方位角</td><td>CloseShutter()</td><td>关闭天窗</td></tr><tr><td>CanSlave</td><td>是否随动</td><td>ShutterStatus</td><td>天窗状态</td></tr></table></body></html>

软件流程如图4（严格意义上说是结合控制软件的流程，天文公共对象模型驱动只是一些离散的属性和方法），分为连接设备、圆顶操作和断开连接3个阶段。连接设备：通过 ASCOMDome Chooser选择设备 ASCOMDome Driver for ADIMM，配置圆顶IP 地址和端口进行网络连接，初始化圆顶，设置Connected $\ c =$ True。圆顶操作：开启圆顶，执行OpenShutter()方法发送开启命令至圆顶控制器，查询圆顶状态直至 ShutterStatus $\mathbf { \Sigma } = \mathbf { \Sigma }$ Opened，然后开启一个小于 $6 0 \mathrm { ~ s ~ }$ 的定时器定时执行OpenShutter（）方法让圆顶保持开启；关闭圆顶需先关闭定时器避免圆顶被再次开启，执行CloseShutter（）方法发送关闭命令至圆顶控制器，查询圆顶状态直至ShutterStatus $\mathbf { \Sigma } = \mathbf { \Sigma }$ Closed再返回。断开设备：如有定时器先关闭定时器，关闭圆顶并设置Connected $\mathbf { \Sigma } = \mathbf { \Sigma }$ False。如图5为圆顶连接配置界面，由于圆顶控制器采用网络通信，程序设计时需要考虑把圆顶IP和端口保存到计算机中。

![](images/e128a66c2389ee50ecada4b4ea81d241418998704475b5051b3aa04e467420f1.jpg)  
图4软件流程图  
Fig.4Software flowchart

从软件流程可以看出驱动设计思路的关键是将蚌壳折叠式圆顶当作不会随动的经典天文圆顶处理，把圆顶开合操作视为经典圆顶天窗开合操作，这样设计有利于降低软件编写的复杂度，提高稳定性和可靠性。

由于控制软件对天文公共对象模型驱动的调用如发送命令、获取属性等具有特定的时间周期，驱动设计特别需要注意通信阻塞问题，不宜采用同步通信处理耗时间的工作如查询状态等，否则会因为阻塞产生软件假死现象。本设计对网络通讯进行了合理的超时设置，并采用非阻塞线程类定时器，彻底解决了软件通信阻塞的问题。

A ASCOM Dome Chooser x ADIMM Dome Setup ×   
Telethetypefdoeyouaethenbeuet click the Properties... button to configure the ip 192.168.100.106 A   
driver for your dome. ASCOM ASCOM Dome Driver for ADIMM. Properties. port 502 Click thetloscot eset OK Trace on 0k 7 ifteraoderdsifor of Cancel Cancel ASCOM

# 4系统测试

自动差分像运动大气视宁度监测仪天文圆顶的手动控制实现较早，天文公共对象模型支持于2016 年初完成。分别使用 MaxImDL、MaxPilote 控制软件对其进行多次测试，系统均能正常工作，未出现任何软硬件故障。图6和图7分别为二者控制圆顶截图，图像左边为相机拍摄的圆顶实时照片截图，图像右边为TeamViewer远程登录控制计算机并用天文公共对象模型控制圆顶的截图。

![](images/248cfc42cfeededf87450a7a0d29d01198fcfbe9146b2cb3b8e4f2cbdd01c2b6.jpg)  
14卷  
图5连接配置  
Fig.5Connection configuration   
图6圆顶控制界面  
Fig.6Interface of dome control

目前云南天文台自行开发的Windows版本自动差分像运动大气视宁度监测仪的控制软件已经实现通过 Modbus/TCP 协议对圆顶的控制，下一步将逐步加人天文公共对象模型支持，使其支持更多的兼容设备。

![](images/9d55abf0c2263c30937672f0a592439b4628e28d008c0211127194e647a53f31.jpg)  
图7圆顶控制界面Fig.7Interface of dome control

# 5结语

自动差分像运动大气视宁度监测仪是云南天文台自行研制的天文站址监测设备，由于全自动无人值守的特性，天文圆顶自动化非常重要。实测结果表明，基于天文公共对象模型和 Modbus/TCP协议的天文圆顶控制系统具有较好的稳定性、兼容性和可扩展性，为自动差分像运动大气视宁度监测仪完全实现自动观测提供了可靠的保证，同时为中小型天文望远镜圆顶设计提供了可借鉴的经验和方法。

Linux 操作系统下第2代远程望远镜系统（Remote Telescope System，2nd Version，RTS2） $\textcircled{4}$ 已逐渐成为远程望远镜控制系统的标准，该圆顶控制系统设计也充分考虑了对RTS2的支持，具备了跨平台的特点，这为将来自动差分像运动大气视宁度监测仪控制软件开发基于RTS2的Linux版本提供了前提条件和可靠保证。

# 参考文献：

[1] 姚正秋，周放.近代天文圆顶发展概况［J].天文学进展，2003，21（3)：206-218.Yao Zhengqiu, Zhou Fang. Progress in modern astronomical enclouse [J]. Progressin Astronomy,2003，21(3):206-218.  
[2] 陆栋宁，黄垒，陈颖为，等. $8 5 ~ \mathrm { c m }$ 天文望远镜圆顶和天窗自动化系统研制［J].天文研究与技术——国家天文台台刊，2008，5(4)：386-391.Lu Dongning，Huang Lei，Chen Yingwei，et al.Research and development of the dome/slitcontrol system for the $8 5 \mathrm { c m }$ reflector of NOAC-BNU [J].Astronomical Research & Technology-Publications of National Astronomical Observatories of China，2008，5(4）:386-391.  
[3] 彭亚杰，季凯帆，梁波，等.ASCOM在选址望远镜远程控制中的可用性研究［J]．天文研究与技术——国家天文台台刊，2013，10(1)：49-54.Peng Yajie，Ji Kanfan，Liang Bo，etal.The Usability of the ASCOM in remote control of a slit-survey telescope [J].Astronomical Research & Technology———Publications of National AstronomicalObservatories of China，2013，10(1）:49-54.  
[4] 翁建年，张浩，彭道刚，等.基于嵌入式ARM的Modbus/TCP协议的研究与实现［J]．计算机应用与软件，2009，26(10)： $3 6 - 3 8 + 6 8$ ：Weng Jiannian， Zhang Hao，Peng Daogang，et al. On embedden ARM-based Modbus/TCPprotocol and its implementation [J]. Computer Applications and Software，20O9,26(10）: 36-$3 8 + 6 8$ ，  
[5] 李宝仁，周磊，周洪.基于Modbus/TCP协议通信节点的实现［J]．机床与液压，2004(12): 153-155.Li Baoren， Zhou Lei, Zhou Hong.The realization of communication node based on Modbus/TCPprotocol ［J].Machine Tool & Hydraulics，2004(12）:153-155.  
[6] 范玉峰，辛玉新，白金明，等．丽江站 BOOTES-4 综述［J]．天文研究与技术，2015，12(1): 78-88.Fan Yufeng，Xin Yuxin，Bai Jinming，et al. An overview of the BOOTES-4 at the LijiangObservatory [J].Astronomical Research & Technology，2015，12(1）:78-88.

# Astronomical Dome Control System Based on ASCOM and Modbus/TCP Standard

He Shousheng，Xin Yuxin，Lun Baoli,Fan Yufeng （Yunnan Observatories，Chinese Academy of Sciences，Kunming 65ool,China,Email：heshousheng@ ynao.ac.cn）

Abstract：Astronomical dome is an important peripheral of optical telescope system，with the development of the telescope technology，astronomical dome control technology has also been improved.In order to realize the full automation of Yunnan observatory Automatic Diffrential Image Motion Monitor（ADIMM），an astronomical dome control system based on ASCOMand Modbus/TCP protocol is developed.Combined with ASCOM astronomical technical standard and the Modbus/TCP protocol specification，the control system structure principle and realization method of Yunnan observatory ADIMM astronomical dome control system is introduced in detail.The measured results show that the dome control system has good stability and compatibility，which fully meets the requirements of ADIMMautomatic observation，and it provides a reference of experience and methods for the designs of the smalland medium-sized astronomical telescope dome.

Keywords：Astronomical Dome；ADIMM；ASCOM；Modbus/TCP