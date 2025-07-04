# 量子科学实验光学地面站综合控制系统设计与开发

兀颖²，葛亮’，田健峰，姜晓军}²，王汇娟²，王建峰’， 贺东²³，李凤芝

(1.中国科学院天文光学重点实验室（国家天文台），北京100101；2.中国科学院大学，北京 100049；3.中国科学院光电技术研究所，成都610209；4.中国科学技术大学，合肥230026)

摘要“墨子号”量子科学实验卫星（简称“墨子号"）是国际首颗从事空间尺度量子科学实验的卫星。“墨子号”和4个量子科学实验光学地面站及一个量子隐形传态光学地面站构建了天地一体化量子科学实验平台。为了实现各地面站的综合协调工作，需要研制一套量子科学实验光学地面站综合控制系统（简称地面站综合控制系统)。地面站综合控制系统涉及4个量子科学实验光学地面站，包括2个新建地面站和2个改造地面站，需要对其实现统一的接口和平台控制。本文参考了国际标准接口，针对量子科学实验光学地面站的功能需求，采用分层和模块化的设计方法，将地面站综合控制系统分为：Web 服务层，网络交互层和设备控制层。设计完成的地面站综合控制系统实现了以下功能：（1）科学数据的发布；（2）内外数据的交互；（3）量子科学实验卫星项目科学实验计划的解析执行；（4）测站环境和设备状况的监测。作为量子科学实验光学地面站的统一控制平台，地面站综合控制系统为量子科学实验光学地面站的全面协调控制提供了有力保障和支持,同时作为通用的地面站控制系统，具有便于向其他望远镜控制系统移植的优点。

关键字：综合控制；量子科学实验光学地面站；数据交互中图分类号：P111.2 文献标识码： 文章编号：

# 1引言

传统的量子通信是基于光纤，受限于光纤的固有损耗，基于光纤的量子通信传输距离难以  
突破百公里量级。因此，科学家们将目光投向了自由空间，借助卫星平台，构建卫星与地面远  
距离量子科学实验平台，实现更远距离的量子通信[1]。2011年由中国科学技术大学牵头提出并  
策划的“量子科学实验卫星”项目正式立项，2016年8月16日“墨子号”量子科学实验卫星（简  
称“墨子号”）发射成功。量子科学实验卫星项目在中国科学院空间科学战略性先导科技专  
项的支持下完成了一系列具有国际领先水平的科学实验，取得了具有高显示度的科学成果[2-3]。卫星与地面远距离量子科学实验平台主要由“墨子号”和量子科学实验卫星——科学应用

系统（简称量子科学应用系统）组成。量子科学应用系统由一个中心五个测站（4个量子科学实验光学地面站和1个量子隐形传态光学地面站）组成4。为了充分利用我国广袤的地域，延长单轨可观测时间，量子科学实验光学地面站的地理分布跨度较大。同时，超过1200 公里的量子纠缠分发实验[3需要多个量子科学实验光学地面站的协同工作。为了便于量子科学实验中心高效稳定的调度量子科学实验光学地面站进行实验，需要建立统一的地面站综合控制系统。考虑到以下因素：（1）量子科学实验光学地面站设备较多且有多层次的功能需求；（2）用于ATP的望远镜和用于数据采集的量子终端都是专门研制设备，不具备通用控制接口；（3）现有望远镜控制系统（ASCOM,RTS2）[5-]无法满足地面站综合控制系统的需求，因此，专门设计开发量子科学实验光学地面站综合控制系统（简称地面站综合控制系统），实现对量子科学实验光学地面站的综合控制。

# 2 系统设计

# 2.1总体设计

地面站综合控制系统作为4个量子科学实验光学地面站的统一控制平台，需要完成科学数据的发布；内外数据的交互；实验计划的解析执行；环境信息和设备状态信息的监测和发布等功能。地面站综合控制系统在功能上有多层次要求，针对这一特点，对不同层次的需求进行分割，采用分层设计的设计方式和自顶向下的设计原则进行系统架构设计，通过网络通信接口实现耦合，使整个系统构架灵活，易于维护。

地面站综合控制系统由Web服务层、网络交互层和设备控制层构成，如图1所示。Web服务层提供实验状态信息和气象数据的Web访问；网络服务层主要实现：实验计划的内外交互、内部各组件之间数据的交互、实验监测数据及环境数据的入库；设备控制层对实验计划进行解析并执行，同时采集实验数据和设备状态数据。为了便于开发，将整个地面站综合控制系统划分为以下相互松耦合的四个模块：（1）Web网页显示模块、（2）网络通信服务模块、（3）主控模块、（4）环境监测和视频监控模块，各模块之间通过网络通信接口实现耦合。

![](images/0dd84539f84b907e1c6233f4301eb98aaee46b72fd169823067525c7a6392619.jpg)  
图1地面站综合控制系统软件架构图  
Fig1System architecture ofcomprehensive control system for the quantum scienceexperimental optical ground station

4个量子科学实验光学地面站之间相距较远，为了保障量子科学卫星项目的顺利进行，量子科学实验中心开通了量子专网，将量子科学实验卫星项目中所涉及的各个量子科学实验光学地面站和实验节点都纳入量子专网。在单个量子科学实验光学地面站的网络布局设计中，考虑到如果将量子科学实验光学地面站的所有设备控制计算机均接入量子专网，不仅在安全上存在隐患，而且大量数据的传输会给网络带来压力。因此，针对这个问题，地面站综合控制系统的网络布局采用内外网隔离的方式，如图3所示，用于网页发布和外部数据交互的网络通信服务器作为对外的一个通信节点，对外连接量子专线，对内连接内部网络，实现内外数据的交互。设备层的控制主机（综控主机、望远镜子系统主机、量子主机、环境监测系统主机）均布局在内部网络里，分配固定IP，确保数据传输的速率和安全性。

# 2.2Web网页显示模块

科学实验中心需要监测各个量子科学实验光学地面站的实验进度、设备状态和气象条件，以便更加及时高效地安排实验计划。为了方便用户浏览信息，设计开发了Web网页显示模块。网页采用ASP.NET开发，数据库采用MYSQL，采用单网页模式，实现在一个界面上显示全部信息。网页显示内容如表1所示，主要包含实验状态和设备状态等。

Tab.1 Essential elements for displaying   

<html><body><table><tr><td>显示项目</td><td>显示要素</td></tr><tr><td>时间信息</td><td>日期、历元、UTC时间、恒星时</td></tr><tr><td>望远镜位置信息</td><td>当前赤经、当前赤纬、当前方位、当前俯仰</td></tr><tr><td>跟踪状态信息</td><td>目标赤经、目标赤纬、赤经跟踪误差、赤纬跟踪误差</td></tr><tr><td>量子信息采集结果</td><td>采集状态、通道数据、电压、电流、半波片角度</td></tr><tr><td>望远镜底层反馈信息</td><td>传感器温度、设备状态信息、故障状态信息、后光路设备信息</td></tr><tr><td>任务状态信息</td><td>任务状态、信标光开关状态、粗相机状态、精相机状态</td></tr><tr><td>气象信息</td><td>全天云量图片、温度、湿度、气压、风速、风向</td></tr><tr><td>监控信息</td><td>圆顶监控、观测室监控、粗相机视频监控、精相机视频监控</td></tr></table></body></html>

# 2.3网络服务模块

地面站综合控制系统作为量子科学实验光学地面站的统一服务平台需要负责内外数据的交互。针对这一需求，设计开发了网络服务模块，对外负责与量子科学实验中心及地面支撑系统的数据交互；对内负责内部各控制组件的之间的数据交互。

为满足不同数据类型和不同功能的数据交互，将网络服务模块划分为以下组件：（1）FTP服务器：主要用于接收量子科学实验中心发来的实验计划和反馈实验数据到量子科学实验中心;（2）数据库：存储设备的状态信息、测站环境信息、实验信息等；（3）网络协议接口：用于内部各模块之间数据交互；用于内外部模块之间数据交互。

如图2所示，量子科学实验中心通过FTP服务器发送实验计划，主控程序的控制模块解析实验计划，通过主控软件与终端设备之间网络通信协议，发送控制命令，控制终端设备执行实验计划，同时，主控软件的数据采集模块采集设备参数及状态数据，写入数据库。气象数据通过与数据库之间的网络协议，写入数据库。实验数据通过FTP服务器反馈至量子科学实验中心。实时的监测显示数据通过主控数据采集模块与地面支撑系统之间的网络接口发送至地面支撑系统。

![](images/324f9ebc33aa9deda6ae7b95e3980b1debde1792d471e3980e46915e430016a1.jpg)  
图2地面站综合控制系统数据流图  
Fig.2Data flow diagrams of the comprehensive control system

# 2.4主控模块

主控模块是地面站综合控制系统的核心部分，主要负责实验计划的解析执行。量子科学实验光学地面站的硬件包括量子光通信望远镜[89]、量子终端和环境监测设备，在硬件组成上和天文望远镜系统比较相似。因此，主控模块的设计采用观测控制软件(Observing Control Software，简称0CS）的设计思想，将整个模块分为：设备控制层和观测策略控制层。设备控制层由量子光通信望远镜控制软件和量子终端控制软件构成，量子光通信望远镜控制软件（成都光电技术研究所研制）负责观测目标的捕获、跟踪和瞄准控制，量子终端控制软件（中国科学技术大学研制）负责量子终端设备的控制。在这些设备控制软件的基础上，分别制定了《量子科学实验光学地面站望远镜对外接口》和《量子科学实验光学地面站量子通信终端对外接口》。主控软件通过这些网络通信接口对设备进行调度，完成量子科学实验卫星项目科学实验(简称量子科学实验)的流程控制。

设备层和主控软件之间的通信采用单链路全双工模式，命令控制数据流和状态反馈数据流的传输相互独立，各使用一条通信链路。设备控制端（量子光通信望远镜控制软件、量子终端控制软件）以固定频率向主控软件推送反馈状态帧，主控软件解析反馈状态帧确定设备状态，进行流程控制。

![](images/5e04979431f2b1b280d5531fa17d8ef9e0743ef531a2c5f0ba9f73b41aceed4c.jpg)  
图3主控软件流程图  
Fig.3Flowchart of the main control software

“墨子号”是一颗低轨道的卫星，运行速度较快，需要以较高频率对量子光通信望远镜进行位置和速度的控制。如果由主控软件进行轨道跟踪控制，由于网络通信频率和网络通信延迟的影响，无法实现高频率、高精度的跟踪控制。因此，在本设计中，由量子光通信望远镜控制软件负责轨道跟踪控制，主控软件提前将轨道数据转换为测站坐标系下的时间位置序列，发送给量子光通信望远镜控制软件。同时，为了提高效率，任务开始前，主控软件控制量子光通信望远镜运动到轨道序列的第一个位置，等待任务开始便开始进行轨道跟踪，

# 2.5环境监测和视频监控模块

环境监测和视频监控模块是地面站综合控制系统的辅助模块，为实验计划的顺利执行提供保障。测站环境信息是实验计划制定和调整的重要参考信息，同时也为实验结果的分析提供参考。环境监测设备如图4所示，由云量相机和气象站组成，负责测量和记录地面站的环境参数，采集的信息要素如表2所示，主要包括云量、温度、湿度、风速、风向等。在环境监测设备建设初期，由于云量相机和气象站距离控制室较远，采用传输延长线的方式进行长距离传输，但在实际应用中会出现设备与采集电脑通信不稳定的情况，造成数据采集不完整。经过测试分析，发现是由于控制计算机和采集设备之间延长线过长引起通信不稳定。于是对相关系统进行了升级，新的系统采用ARM单片机完成对全天相机及气象站的控制及数据采集工作，采集结果通过socket发给服务器上的数据接收程序，数据接收程序对接收文件进行存储[1]。在实际使用过程中故障率显著降低。

视频监控部分主要包括环境视频监控和粗跟踪相机视频及精跟踪相机视频（简称粗精跟踪相机视频）。通过摄像头采集实时监控视频和粗精跟踪相机视频，传输到硬盘录像机，存储到网络硬盘，并通过Web发布到量子专网里。视频监控模块为实验过程的回溯提供了材料，为事后实验结果分析提供参考。

表2气象站采集信息要素  
Tab.2 Essential elements of meteorological monitor   

<html><body><table><tr><td>要素</td><td>云量</td><td>温度</td><td>露点温度</td><td>相对湿度</td><td>气压</td><td>风向、风速</td></tr><tr><td>采集间隔</td><td>5min</td><td>1min</td><td>1min</td><td>1min</td><td>1min</td><td>10min平均值</td></tr><tr><td>数据形式</td><td>图片</td><td>数据</td><td>数据</td><td>数据</td><td>数据</td><td>数据</td></tr></table></body></html>

![](images/b483601a01e31c9af3ffcbd1d8ed08dc858b6aa64344d5b3d89ea66e829c8af2.jpg)  
图4环境监测设备  
Fig.4Meteorological monitoring instruments

# 3 系统测试与运行

为了保障“墨子号”发射后星地量子通信光链路的顺利建立，地面站综合控制系统设计完成后，对其进行分阶段的系统性测试。

系统测试分为实验室测试、低轨道卫星模拟测试、在轨测试阶段测试三个阶段。系统设计完成后首先进行了实验室模拟测试，实验室模拟测试阶段主要完成了各模块的功能测试和模拟实验流程测试，测试项目和结果如表3所示。为了保证“墨子号”发射后星地对接的顺利进行，需要在实验室测试完成后对软件进行实验流程测试，由于“墨子号”未发射，无法进行实际观测。为了尽可能模拟实际观测情况，选择跟踪低轨道卫星进行模拟测试。低轨道卫星模拟测试阶段，将地面站综合控制系统配备到4个量子科学实验光学地面站，通过跟踪低轨道卫星对地面站综合控制系统进行实验流程测试，经过充分测试，地面站综合控制系统服务于发射前4个量子科学实验光学地面站的实验测试工作。“墨子号”发射后进入在轨测试阶段，实际跟踪“墨子号”对地面站综合控制系统进行测试。在轨测试阶段，兴隆量子科学实验光学地面站最先与“墨子号”成功对接，随后各个量子科学实验光学地面站也成功的与“墨子号”完成对接。在4个量子科学实验光学地面站均成功与“墨子号”对接后，地面站综合控制系统进入常规运行阶段。

表3测试项目及结果  
Tab.3 Test items and results   
量子科学实验卫星信息显示系统  

<html><body><table><tr><td>测试项目</td><td>测试结果</td></tr><tr><td>量子科学实验光学地面站望远镜对外接口功能测试</td><td>协议解析正确，命令响应与反馈正常</td></tr><tr><td>量子科学实验光学地面站量子终端对外接口功能测试</td><td>协议解析正确，命令响应与反馈正常</td></tr><tr><td>环境监测功能</td><td>正确采集云量、温度、湿度、气压、风速、风向的等信息</td></tr><tr><td>视频监控功能</td><td>正确录制并存储粗精跟踪相机视频和视频监控</td></tr><tr><td>Web 显示测试</td><td>网页正确显示实验信息、环境信息和监控视频信息；网页刷新正常，运行稳定</td></tr><tr><td>实验流程控制功能</td><td>主控软件流程控制正确</td></tr><tr><td>内外数据交互功能</td><td>准确接收短期计划并准确反馈实验结果</td></tr></table></body></html>

图5和图6分别是常规运行阶段的Web显示页面和主控软件界面。Web页面可实时显示实验信息、环境信息和监控视频信息。主控软件实现了实验计划的解析和执行、实验数据和设备状态的采集记录，同时具备恒星观测功能。

时间信息 望远镜信息 望远镜信息 气象信息日期 2016-08-14 精跟踪报警 报警 方位人工修正 0 采集时间 2016-08-14 16:59:49历元 J2016.62 粗跟踪报警 正常 方位模拟修正 0 当前温度 18.2UTC时间 07:25:45 温度0 149.875 俯仰人工修正 0 当前湿度 53.2恒星时 10:47:04 温度1 148.312 俯仰模型修正 0 露点温度 8.52温度2 149.625 俯仰大气修正 0 大气压强 793.3位置信息 温度3 147.625 粗电视脱靶量X -9999 风速 1.9当前赤经 00:40:01 温度4 150.375 粗电视脱靶量Y -9999 风向 160当前赤纬 -10:19:44 温度 149.375 精电视脱靶量X 0当前方位 105.52 温度6 153.312 精电视脱靶量Y 0 站点信息当前俯仰 1.23465 温度7 155.25 M3镜位置 天文 当前站点 南山温度8 147.438 后光路导轨位置 当前时间 2016-08-14 17:00:22跟踪信息 温度9 147.562 多圈计数 0目标赤经 00:00:00 自动跟踪闭环 开环 单圈计数 0目标赤纬 00:00:00 精跟踪状态 未使能 扫描序列号 0方位误差 0 方位模式 未使能 粗电视密度盘工作状态 0 C俯仰误差 0 俯仰模式 未使能 精电视密度盘工作状态 0俯仰软超限 正常 精电视滤光片工作状态 5量子信息 俯仰硬超限 正常 后光路扫描返回X -32768监控状态 停止采集 俯仰超速 正常 后光路扫描返回Y -32768GPS计数 0 俯仰过载 正常 粗电视曝光时间 0同步光计数 0 俯仰驱动故障 正常 粗电视曝增益 0H(850)计数 0 俯仰硬件保护 正常 精电视曝光时间 0 视频（admin:12345）V(850)计数 0 方位软超限 正常 精电视增益 0+(850)计数 2824805 方位硬超限 正常 FX -0.477104(850）计数 0 方位超速 正常 FY -1.1851投射(810）计数0 方位过载 正常 Fz 0.243999反射(810）计数0 方位驱动故障 正常 Fu 0.21370112V电压 12 方位硬件保护 正常 Fv -0.20419812V电流 0.198 方位限位状态 正常 F_w 05V电压 4.8626 俯仰限位状态 正常 信标光状态 关闭5V电流 0.804 消旋模式 不消旋 任务状态 空闲3电 3.26133 旋实际置 99.8半波片角度 0 消旋限位状态 正常

![](images/a15d544efe2a3f205a61d395d5152e2624bb0e91e31aaa901096065e56ad9b3c.jpg)  
图6主控软件界面Fig.6 GUIof the main control software

# 4总结与展望

设计完成的地面站综合控制系统实现了量子科学实验光学地面站的自动化控制，观测人员经过简单培训，即可胜任观测任务。地面站综合控制系统分别配置到4个量子科学实验光学地面站，服务于星地高速量子密钥分发实验2和超过1200 公里的量子纠缠分发实验3，顺利完成其在量子科学实验卫星项目中的任务。地面站综合系统中的环境监测模块，目前是独立于观测控制系统，在天气发生突发变化时，尚不具备自动调整实验计划的功能。在未来工作中，计划基于气象信息动态调整观测计划，从而实现高度自动化的观测控制，进一步提高观测效率。

# 参考文献

［1］彭承志,潘建伟.量子科学实验卫星— -“墨子号”[J]．中国科学院院刊，2016，31(9）:1096-1104.Peng Chengzhi,Pan Jianwei. Quantum Science Experimental Satellite “Micius” [J].Bulletin of Chinese Academy of Sciences.2016，31 （9） :1096-1104.  
[2] Sheng-Kai Liao,Wen-Qi Cai,Wei-Yue Liu,et al. Satellite-to-ground quantum keydistribution ［J]. Nature，2017， 549: 43-47  
[3] Juan Yin, Yuan Cao, Yu-Huai Li,et al. Satellite-based entanglement distributionover 1200 kilometers [J]. Science. 2017，356:1140-1144  
[4] PAN Jianwei. Progress of the Quantum Experiment Science Satellite (QUESS) MiciusProject[J].Chinese Journal of Space Science. 2018,38(05),604-609  
[5］彭亚杰，季凯帆，梁 波，等．ASCOM 在选址望远镜远程控制中的可用性研究［J].天文研究与技术，2013,10（1）：49-54Peng Yajie，Ji Kaifan，Liang Bo，et al. The Usability of the ASCOM in Remote Controlof a Site-Survey Telescope[J].Astronomical Research & Technology.2013,10(1) :49-54  
[6]和寿圣，辛玉新，伦宝利，等.基于ASCOM和Modbus/TCP协议的天文圆顶控制系统［J].天文研究与技术，2017，14（3）:356-362. HeShousheng， Xin Yuxin，Lun Baoli，et al.Astronomical dome control system based onASCOM and Modbus/TCP standard[J].Astronomical Research&Techonolgy， 2017，14(3) :356-362.  
[7] Petr Kubánek， RTS2—The Remote Telescope System[J],Advances in Astronomy.Vol.2010,Article ID 902484,9 pages，http://doi.org/10.1155/2010/902484  
[8］元波.量子通信光学地面站ATP关键技术研究[D]．中国科学院大学.2014Qi Bo. Study on Acquisition, Tracking and Pointing Key Technology of Optical GroundStation for Quantum Communication [D].University of Chinese AcademyofSciences.2014  
[9］苏艳蕊.量子光通信望远镜跟踪控制技术研究[D]．中国科学院大学.2016Su Yanrui. The Study on Tracking and Control Technology of Optical Ground Stationfor Quantum Communication [D].University of Chinese Academy of Sciences.2016  
[10]田健峰,邓李才，闫正洲，王坤，兀颖．中国SONG项目节点全天云量监测方案[J].天文学报，2016，57（3）:366-375Tian Jianfeng,Deng Licai,Yan Zhengzhou, Wang Kun,Wu Ying. All Sky Cloud CoverageMonitoring for SONG-China Project [J]. Acta Astronomica Sinica 2016,57(3):366-375

# Design and Development of Comprehensive Control System for Quantum Science Experimental Optical Ground Stations

Wu Ying12,Ge Liang1,Tian Jianfeng1,Jiang Xiaojun12, Wang Huijuan1.2， Wang Jianfeng1 He dong2,3,Li Fengzhi 4 (1.KeyLaboratoryofpticalstrooyatioalstronoicalObservtores,iecadeyofiencs,eijgi;

2.University of Chinese Academy of Sciences，Beijing 1Ooo49，China; 3.Institute of Optics and Electronics,Chinese Academy of Science,Chengdu 61O2O9,China; 4.University of Science and Technology of China,Hefei 23oo26,China)

Abstract: “Micius” quantum science experiment satelite (referred to as “Micius") is the world's first satelite engaged in quantum science experiments at the space scale.“Micius”, together with four optical ground stations for quantum science experiments and one optical ground station for quantum teleportation, has built a platform for satelite-ground quantum science experiments. In order to realize the integrated coordination of the optical ground stations of quantum science experiment, it is necessary to develop a set of integrated control system of quantum science experiment (referred to as the integrated control system of ground station).The integrated control system of the ground station consists of four quantum science experimental optical ground stations, including two new optical ground stations and two modified ones,and the unified interface and platform need to be established for them. In this paper, the integrated control system of the ground station is divided into web service layer, network interaction layer and device control layer by adopting the layered and modular design method,refers to international standard interfaces and according to the functional requirements of the optical ground station in quantum science experiment. The designed ground station integrated control system has realized the following functions :(1) the release of scientific data; (2) the interaction between internal and external data; (3) the analytical implementation of the scientific experiment plan of the quantum scientific experiment satelite project; (4) monitoring the environment and equipment conditions of the station. As a unified control platform for the optical ground station of quantum science experiments,the integrated control system of the ground station provides a strong guarantee and support for the overall coordinated control of the optical ground station of quantum science experiments. At the same time, as a general ground station control system, it has the advantages of being easy to transplant to other telescope control system.

Key words:Comprehensive control; Quantum science experimental optical ground station; Data interaction