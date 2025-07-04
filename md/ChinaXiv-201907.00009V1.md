# 远程天文台电源集成控制与监控模块的设计与实现

王川中”²，苏丽颖，韩军²，崔辰州²，王显海³，樊东卫²(1.北京工业大学，北京 100124；2.中国科学院国家天文台，北京 100101;3.常州信息职业技术学院，江苏 常州 213164)

摘 要：随着多波段时域天文学的快速发展，远程天文台逐渐显露出优势，成为时域天文学研究的重要工具。然而，国内还没有自主、成熟、稳定的系统可以应用到远程天文台的建设当中，为此中国虚拟天文台提出并设计了一套硬件集成系统以便于集成控制和扩展移植。电源模块是其中重要的组成部分，实现电源的集成控制将极大提升整个系统的稳定性。本文设计了一个闭环的电源集成控制模块，通过嵌入式技术实现了天文台各设备电源的集成控制、平顶的开关控制以及各个设备状态的监测，并提供多种控制模式。通过发送随机网络指令对该模块进行了24小时的连续测试，并测试了网络中断情况下短消息的控制。通过发送与监测数据的对比，结果表明系统具有艮好的稳定性。关键词：远程天文台；时域天文学；集成控制与监控；电源管理中图分类号：XXX 文献标识码：XXX 文章编号：XXX

天文学是一门以观测为主的学科，高质量的观测环境是开展天文观测的重要前提。随着城市现代化的发展，光污染、空气污染等问题严重影响了天文观测，因此天文观测通常优先选择在偏远地区，远程观测也就变的尤为重要。随着计算机与自动控制技术的进步，望远镜程控技术得到极大提升，不仅能够实现望远镜的远程观测控制，还能够使望远镜按照计划进行自动观测，甚至自主观测等[。远程天文台的历史可以追溯到上世纪六十年代，其发展可以分为四个阶段，即自动执行望远镜、远程操作望远镜、程控自主天文台以及未来由人工智能系统进行决策的程控智能天文台[2,3]。自动执行望远镜实现了按照预编制观测流程的自动执行，远程操作望远镜实现了按照观测者的要求执行远程观测的功能，程控自主天文台是当前设计的主流，不仅能够执行观测计划与远程观测，还需要能够自主适应环境的变化。

时域天文学是当前最为活跃并快速发展的天文研究热点，而远程天文台凭借连续观测、快速反应等方面的独特优势，将极大推动时域天文学的快速发展，并将成为重要的发展目标。国内外时域天文学的研究还属于起步阶段，各国都在开展系统的时域巡天观测计划，如ROBONET、ROTSE-III，还有如国内参与的首个程控天文台网络BOOTES。其实现了自主识别天气状况控制圆顶开合，自主选择观测目标进行科学观测，并在伽玛暴余辉和其它瞬变源的光学观测研究上都有了良好的应用4。另外，远程天文台在天文教育与公众科学方面也开始发挥重要作用，如英国的BRT(Bradford Robotic Telescope)已完成数万次观测请求，是第一套完全用于教育目的远程天文台，还有如美国的GTN(Global Telescope Network)已经走进课堂①。星明天文台始建于2007年，是由国内爱好者建立的远程天文台并向大众开放观测申请。星明天文台与中国虚拟天文台联合开展了公众超新星搜寻项目，是国内首个通过业余天文数据开展全民科学的项目，是专业天文和业余天文进行深度合作的成功尝试，为公众科学提供了一种新方式6]。

与国外相比，我国远程天文台的发展起步比较晚，不仅在望远镜数量上存在着极大的差距,而在望远镜程控技术上的差距更为明显，硬件的控制管理往往是多种功能模块的拼接，系统的兼容性、扩展性和集成性相对较差，更无法迁移推广[7]。目前，我国还没有一个成熟的设计可以应用到远程天文台的建设当中，这对于我国时域天文学的发展与研究非常不利。远程天文台由望远镜、赤道仪、圆顶、计算机、气象站、全天相机等设备构成，具有多个自动化的软件与硬件子系统，它们之间通过相互协调控制实现程控观测的功能。中国虚拟天文台经过多年的调研与研究，提出并设计了一套基于嵌入式的硬件集成系统，作为用户与天文台设备间连接的桥梁（详细请参考Han et al.2018），以便于各子系统的集成控制和扩展移植。该设计的推广使用对于我国远程天文台技术的发展具有重要的推进作用[89]。

设计中提出的硬件集成系统是用户与天文台连接控制的核心，包括ARM模块连接控制望远镜进行相关观测、电源集成控制与监控模块以及辅助设备（如：监控摄像、气象站、全天相机）的网络连接等。电源集成控制模块负责所有电源的控制与监控，是硬件集成系统重要的组成部分，是整个系统运行的基础，前人也做过一些设计，如采用ARM控制核心的方案[10],实现了基于网络的远程控制以及视频监控功能，但仍有一定的缺陷和提升空间。首先，在网络或电源中断的情况下无法获取设备状态并进行应急控制，仍需人工维护；其次，未充分考虑观测环境问题，适用范围较窄，如在低温下0V9655芯片并不能稳定输出视频图像等；最后，视频监控还需要人工实时参与判断，模块无法对本身进行监控并反馈状态，系统的集成度较低，成本也相对较高；

本文设计并实现了一个闭环的电源集成控制模块，通过使用成本与功耗更低的AVR单片机实现逻辑控制，所有功能模块通过PCB设计集成到一块电路板上，实现了本地、远程以及短消息使用模式，实现了天文台各设备电源的集成控制、平顶的开关控制、各个设备状态的监测以及应急反馈与操作功能。文中将对实现原理、方法以及稳定性测试进行详细的阐述。

# 1.电源集成控制与监控模块的基本框架设计

天文台包括多个观测与辅助设备，电源模块是保障整个天文台正常运行的重要组成部分。电源模块最终要实现天文台各设备的控制与监控，同时还需要能够适应天文台站的特殊工作环境，并拥有可靠的稳定性。基于此，我们对电源模块进行了规划设计，模块由多个组件构成，相互协调配合。模块基本框架如图1所示。

本模块设计了三种控制方式，远程控制、本地控制与短消息控制。远程控制是最常用的控制模式，远端计算机通过互联网将控制消息发送给本地计算机，后者将控制命令转发给模块的网络接口实现控制命令的传递。本地控制除接受本地计算机发送控制命令外，还提供外接按键实现天文台平顶的开关与暂停功能以方便本地控制。短信消息控制主要实现如网络故障、偶然断电等情况下的应急操作。在出现故障时及时通知用户，在UPS 的辅助下实现如望远镜复位、平顶关闭等，实现方式表现为短消息的收发。

![](images/5c19aebce640b9b5b4caf24d5ba5c0b87729b1ba721450c3f63f287f7a33c1af.jpg)  
Fig.1 The frame of power integrated control and monitoring module

本模块不仅需要实现对设备的控制，还需要能够及时获取设备的通断状态，因此我们通过硬件连接设计了控制模块与监控模块，它们各司其职以增强系统的可靠性。设备控制模块提供多组继电器模块作为设备管理接口，用于控制如气象站、CCD、全天相机、赤道仪等设备电源的通断，并提供多个扩展口用于计算机重启等操作。平顶开关的触发较少但需要优异的稳定性，因此我们将其设计为一个单独模块。该模块可以接收来自网络、短消息以及控制按键的控制指令，并通过继电器触发平顶的开关。GSM通讯模块用于短消息接收和发送，一方面可以将控制命令发送给控制模块，另一方面可以根据需求通过短消息反馈当前设备状态给用户。设备监控模块用来同步来自GSM、网络、本地的控制命令，并通过网络反馈给终端用户以实现数据流的闭环。用户通过发送与接收的信号可以判断当前设备的状态以及模块是否异常等。调压模块提供整个模块的电源接入，通过滤波、变压、稳压等步骤提供不同的电压。

# 2.电源集成控制与监控模块的实现

电源集成控制与监控模块作为用户与设备间连接控制的桥梁，其稳定性十分重要，因此我们对常用功能模块进行了集成以增强抗干扰能力，并遵循简单可靠的原则进行实现。模块组件之间相互协作实现逻辑控制、逻辑监控、短消息收发、网络数据收发等功能。为实现

![](images/db18ff641e26f1fb2eeaa4ee77962d0cb2d2b0d7b7daf665b7a2ef04307bd4bf.jpg)  
图1电源集成控制与监控模块框架  
图2电源集成控制与监控模块PCB走线与实物示意图

Fig.2Powerintegratedcontrolandmonitoring moduleforPCBwiringdiagramandthefinished productschematicdiagram以上功能，本模块采用嵌入式技术进行实现，所用器件都采用了工业级产品以满足天文观测在低温或高温等环境下的操作。本模块基于单片机进行实现，采用ATmega16作为控制芯片，该芯片是一款8位AVR 控制芯片，相比51单片机具有更丰富的接口，相比ARM或STM32具有更高的性价比；采用W5500作为网络接口芯片，其内部通过硬件实现了TCP/IP协议栈，无需网络协议驱动的开发，根据环境自动切换10/100Mbits网络，识别软件设置的通讯波特率；采用 SIM800C作为手机短信收发芯片，采用标准的AT指令进行操作，并可自适应通讯波特率。

ATmega16通过SPI协议与W5500连接，前者用于控制指令的解析与执行，后者用于网络数据的接收与发送。设备控制、平顶控制以及设备监控模块都采用相同的连接方式。设备监控模块既监视控制模块的发送出口，也监视继电器模块的工作状态。用户通过发送、接收以及反馈数据的比对，可及时定位设备状态或出现故障的模块。SIM800C与ATmega16采用UART 协议进行通讯，分别负责短消息的发送接收以及命令的解析。这些模块之间的通讯采用TWI协议进行连接，实现不同组件之间的数据同步。本地操作的按键与单片机接口进行连接并进行了消抖，通过编程可以实现不同的控制。调压模块采用MIC29302芯片、ASM1117芯片与LC滤波电路为以上芯片提供5V、4V与3.3V的稳定电压。本设计采用双层板设计，PCB 走线与实物图如图2所示，该模块的相关参数如表1所示。

表1电源集成控制与监控模块相关参数  
Table.1 Relevant parameters of the power integrated control and monitoring module   

<html><body><table><tr><td>序号</td><td>名称</td><td>参数值</td></tr><tr><td>1</td><td>输入电压</td><td> 5V DC</td></tr><tr><td>2</td><td>额定电流</td><td>0.46A</td></tr><tr><td>3</td><td>最大电流</td><td>3.2A</td></tr><tr><td>4</td><td>工作温度</td><td>-30℃ - 85℃</td></tr><tr><td>5</td><td>相对湿度</td><td>5% - 85%</td></tr></table></body></html>

# 3．电源集成控制与监控模块的驱动设计

远程观测是远程天文台的主要功能，观测时往往是无人值守的，观测开始到结束之间，用户根据实际情况需要对设备进行开关操作。硬件仅提供了功能实现的保障，只有配合软件驱动才能将各个模块功能进行连接，构成一个完整的系统，才能实现对各个功能组件的逻辑控制与监控。驱动软件的设计主要帮助远程用户实现对天文台各设备的远程控制，并能及时获取本地运行状态。具体结合到本文设计中，则是通过对ATmega 16 编程实现本地、远程和短消息控制模式的协同，同时实现多种控制命令的解析执行、数据同步、中断执行以及监控数据的传输等，从而形成一个闭环的系统。驱动设计流程如图3所示。

首先，模块上电芯片进行初始化，包括建立本地网络、连接GSM通讯通道、中断启用、看门狗启动、芯片引脚初始化等，这是驱动程序运行以及后续功能实现的根本保障。初始化成功后，监控模块和GSM模块对状态信息进行转换，并通过网络与短消息将设备状态信息发送给用户以便于确定设备的正常运行。然后，控制模块等待网络、本地或短消息的控制命令。在此期间，若无控制消息更新，监控模块将启动定时器进行计时，每隔一定时间间隔通过网络将监控信息发送给用户。若控制模块收到新的控制消息，控制模块进入中断模式，同时监控模块计时器中断失效，控制模块对信息进行解析并执行相应的操作。监控模块监测到控制逻辑发生变化后对各模块进行数据同步，并将状态信息转换后发送给用户。处理完本次消息后，控制模块继续等待新的控制指令，监控模块重新启动定时器功能，进入下一次的循环。芯片间的数据同步与监控信息的反馈是实现远程控制数据闭环的关键。本文设计了两种数据同步方式，即在设备状态信息发生变化后监控信息进行同步并发送给用户，在没有状态信息变更的状态下固定时间内发送一次监控数据。利用这两种数据同步方式既可以帮助远端观测者实现高效控制，还可以及时反馈本地不确定因素引发的系统故障。

![](images/4b9d1534080d329a33f35b377a4a2f6924b8cf88c926e81a49475a99d4a9900b.jpg)  
图3电源集成控制模块程序设计流程图  
Fig.3 The programming flow diagram for the power integrated control module

本文实现了三种控制方式，在驱动程序设计时全部采用了中断的方式进行实现，包括网络控制命令、本地控制命令以及短消息控制命令。本地控制是天文台现场的直接操作，因此具有最高的控制优先级。短消息命令的优先级次之，其通常在网络故障或电源中断等环境下使用，可在无人值守的情况下及时通知用户进行应急控制。网络控制命令的优先级最低。模块在驱动程序中添加通用的信息解析和状态信息转换功能，程序使用控制命令对照表进行相应的操作。信息解析是将本地、网络与短消息的内容，通过预定义的对照表将其转换成模块可以直接执行的二进制指令，状态信息转换是预定义对照表的反操作，将可执行命令解析成用户易于理解的内容。

# 4．稳定性测试

为方便模块的调试与测试，我们使用JAVA语言开发了调试软件，主要在软件调试与开发中使用，控制界面如图4所示。用户通过输入不同模块的IP地址和端口，实现计算机与电源模块驱动软件的连接，实现设备组件的网络控制与监控，期间发送与接收的消息会实时显示在左边文本区域。软件测试用于长时间稳定性测试，该功能可以在特定时长随机产生一定数量的测试命令，两组相邻网络控制命令时间间隔不小于1秒钟。

电源模块的稳定性是远程天文台稳定运行的前提，其稳定性主要表现在通讯链路长时间的稳定运行。远程控制是最常用的控制方法，是我们测试的重点，测试方法如下。系统接入5V 电源，将上一节中的驱动逻辑代码烧写到芯片当中，插入SIM卡，通过网线将三个网络接口连接到交换机上，计算机启动电源模块调试软件并在软件中输入各模块对应的IP 和端口号，建立连接。测试中，使用该软件设定24小时的测试时间，并在此时间内随机产生1000条控制命令，通过发送数据与监控数据的对比验证系统的可靠性。网络控制命令发送的频率如图5所示，横坐标为统计的时间段，每两小时作为一个统计段，纵坐标是该时间段内生成的命令次数。另外，在网络正常和突发中断的条件下分别通过短消息和按键触发控制指令，查看是否可以顺利执行。经过验证，在室温条件下经过24小时的连续测试，数据全部正确，网络中断的条件下也可以实现设备的控制，证明系统稳定性可靠。

Fig.4 The testing software graphical interface for power module

![](images/f2c75b707eea7987dbf8ea4123823951dcc76e2aa49578f9b372241629a29574.jpg)  
图4电源模块调试软件界面  
图5系统稳定性测试统计图  
Fig.5 System stability test chart

140 121 Jaqung 山ulht D H 6 g Q 2 又 16 & 20\~ 22\~ Time (hours)

# 5．总结与展望

本文通过嵌入式技术设计并实现了远程天文台电源模块的集成控制与监控，提供了本地、远程、短信消息三种操作方式，实现了天文台各设备控制与监测的闭环。本文所设计的电源模块将天文台设备的电源控制和监控进行了系统集成，并可在网络与电源中断情况下进行无人值守的应急操作。设计中全部使用了工业级器件进行实现，增强了系统的适用范围。本设计简化了电源控制系统，提高了系统的集成度，测试表明该模块具有良好的稳定性。该模块是远程天文系统中的一个重要组成部分，未来作者将进一步开展研究，将该模块的软件接口整合到远程天文台观测控制系统当中，使整个系统更加智能化。

致谢：本论文得到中国虚拟天文台和中国天文数据中心提供的技术支持。感谢国家科技部国家科技基础条件平台项目"地球系统科学数据共享服务平台"和"国家基础科学数据共享服务平台"的资助。感谢国家天文台-阿里云天文大数据联合研究中心对本项工作的支持。

# 参考文献：

[1] CastrotiradoAJ.RoboticAutonomous Observatories: A Historical Perspective[J]. Advances in Astronomy,2010,2010(1687-7969):8   
[2] JFMcNall，JL Miedaner，AD Code．A computer-controlled photometric telescope[J]．The Astronomical Journal,1968,73:761.   
[3] 崔辰州，李建，蔡栩等.程控自主天文台网络的发展[J].天文学进展，2013，31(2):141-159. CUI Chen-zhou,LIJian,CAIXu,etal..Robotic Autonomous Observatory NetworkReview[J].，Progress inastronomy, 2013，31(2):141-159.   
[4] 范玉峰，辛玉新，白金明，等．丽江站 BOOTES-4 综述[J].天文研究与技术，2015，12（1）：78-88 FanYufeng,XinYuxin,Bai Jinmingetal.AnOverviewof theBOOTES-4attheLijiangObservatory[J],Astronomical Research and Technology,2015,12（1） : 78-88   
[5] E.L. Gomeza,M.T.Fitzgeraldb.Robotic telescopes ineducation[J].Astronomical Review,2O17,13(1):128-68   
[6] S.Li,D.Fan,X.Gao,C.Cui.POPULAR SUPERNOVA PROJECT:A CITIZEN SCIENCE PROGRAM BASED ON AMATEUR ASTRONOMICAL OBSERVATIONS[J], INTED2016 Proceedings   
[7] 赵永恒．天文望远镜的自动观测技术[J].科研信息化技术与应用，2012，3(4):11-16. Zhao Yongheng.Automatic Observation Technology of Astronomical Telescope[J].Research and Application of Information Technology, 2012,3(4): 11-16.   
[8] Han,J.Fan,D,Cui,C.,Wang,C.,L,S.,Mi,L.,Li,Z.,Xu,Y.,He,B.,Li,C.,Tao,Y.,Yang,S.,2O18.A conceptioof engineering design for remote unattended operation public observatory,arXiv:18O1.03667.   
[9] J. Han,C.Wang,D.Fan,C.Cui,S.Li,L.Mi,Z.Li,Y.Xu,B.He,C.Li,S.Yang.Amateur public observatoryI:The observatory and hardware integration system[J].Astronomy and Computing,25 (2018) 89-93   
[10]袁智，梁波，邓辉，等．一种面向选址的低功耗远程电源控制和视频监控系统设计与实现[J].天文研究与技术-国家 天文台台刊,2015,12(1). Yuan Zhi,Liang Bo,Deng Hui,etal.The Designand Implementationof aLow Power Consumption Systemof Remote Power Control and Video Monitoring for Telescope-Site Selection[J].Astronomical Research and Technology-National Astronomical Observatory,2015,12(1).

# Design and Realization of Remote Observatory Power Integrated Control and Monitoring Module

Wang Chuanzhong1,²， Su Liying'， Han Jun²， Cui Chenzhou’， Wang Xianhai³， Fan Dongwei²(1BeijingUesityofchoogyeijg4;atioalAstronomicalObserators,ecadeyofienin100012;3 Changzhou Institute of Information Technology, Changzhou,Jiangsu,213164)

Abstract: With the rapid development of time domain astronomy, remote observatory has been an important tool for time domain research in virtue of its advantages.However, there is not yet a stable and independent system for the construction of public observatory.For solving this problem, China-VO proposed and designed an embedded hardware-based integration system so as to facilitate the integration control and extension. Power module is the basis of this system and plays an important role in promoting system stability. This paper designs a closed-loop power integrated control module and realizes the power integrated control of observatory equipment, the switching control of the roof and the monitoring of equipment,and provides multi control modes. We carried out 24 hours continuous test to this module using random network commands,and tested short message control mode under network interruption. It shows that this module has good stability through the comparison between the commands sent from client and the monitored data.

Key words: Remote observatory; Time domain astronomy; integrated control and monitoring; Power management