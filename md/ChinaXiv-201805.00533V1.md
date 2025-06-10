# FocusGEO软件系统的设计与实现

王维，毛银盾，陈国平，张永帅，于涌，罗浩（中国科学院上海天文台，上海200030）

摘要：FocusGEO是上海天文台自行研制的新一代地球同步轨道动态监视系统，与大部分商用成熟的天文望远镜相比缺乏标准的硬件底层驱动，同时受到运行环境限制，无法设计开发基于Linux的RTS2或基于Windows的ASCOM的全自动化软件系统。研究团队针对FocusGEO的特殊需求，自行设计开发了一套基于Windows的软件系统，可实现望远镜自动观测、资料实时处理、数据传输与数据管理等过程。介绍了软件系统的实现框架、整体流程和数据并行处理的原理，并重点讨论图像实时转换与传输和数据实时处理与入库的实现方法。长时间的观测运行表明，软件系统工作稳定可靠，可为非通用望远镜系统的自动控制软件开发提供借鉴。

关键词：望远镜；自动观测；通信协议；数据库中图分类号： 文献标识码：A 文章编号：1672-7673(2018)

在望远镜控制软件系统中，ASCOM平台和RTS2平台具有很强的通用性与可扩展性，它们为天文观测设备提供了接口标准，其中前者基于Windows操作系统，后者基于Linux操作系统，目前两者在通用望远镜控制上的应用比较广泛。

ASCOM（Astronomy Common ObjectModel）是一个免费开源的天文接口标准，它在天文观测设备与应用软件之间引入驱动层，为应用软件与天文观测设备之间提供了一个免费互通的中间桥梁，设备厂商只需要提供符合ASCOM标准的驱动程序，应用软件也只需要针对ASCOM进行操作，无需考虑不同厂商不同设备类型的特殊性。由于ASCOM采用了COM(Component Object Model)组件模型，极大提高了系统的可扩展性和兼容性，便于望远镜的远程操作和实时控制[1-2]。RTS2（Remote Telescope System，2nd Version）是一套开源的天文观测管理系统，基于Linux平台，采用 $\mathrm { C / C ^ { + + } }$ 语言开发，由于模块化的组件开发技术，使它具有可移植性，围绕即插即用的设计思想，要求每个模块和组件可以随时进入工作或退出，同时不影响系统的整体性能，特别是在有部分代码出错，任务无法继续进行时，不会造成系统崩溃[3-4]。

FocusGEO 是新一代地球同步轨道（Geosynchronousorbit，GEO）动态监视光学系统的简称，由中国科学院上海天文台研究团队历时两年自行研制完成。望远镜采用单机架三镜筒赤道式结构（见图1），在软件系统的支持下对台站上空地球同步轨道带反复扫描观测，实现对地球同步轨道空间目标编目管理和空间事件监测。由于FocusGEO有许多特殊的硬件设备，这些设备缺乏标准的硬件底层驱动，同时本项目的运行环境决定了驱动层和应用层需要分别放置在不同的电脑上，因此无法像常规天文望远镜一样，设计开发基于RTS2或基于ASCOM的全自动软件系统。需要从最底层开始设计，采用合适的网络通信，自行设计开发一套基于Windows环境的软件系统，实现望远镜自动观测、资料实时处理、数据传输与数据管理等过程。

基金项目：国家自然科学基金（11573055）;中国科学院国际合作重点项目(GJHZ1632)资助收稿日期:2017-09-15;修订日期:2017-10-12作者简介：王维，男，助理工程师.研究方向：天文技术与方法.Email：wangwei@shao.ac.cn

![](images/0e87f279570a1cc2a0f8f28df7e00f3a61541754098f009eb504a5548d6a462f.jpg)  
图1FocusGEO望远镜Fig.1 FocusGEO Telescope  
图2FocusGEO软件系统框架图  
Fig.2 The block diagram of FocusGEO software

FocusGEO软件系统包括望远镜控制软件、CCD相机控制软件、主控软件、预处理软件、GEO卫星量度坐标预报软件和图像压缩及传输软件共6部分。主控软件与各设备驱动软件采用用户数据报协议(User Datagram Protocol,UDP)进行通信，同时获取IP监控摄像头的视频流数据，监控望远镜运动情况。图像压缩及传输软件实时进行图像压缩及格式转换，利用FTP将图像和预处理结果主动推送至远端服务器，并即时统一录入到Oracle数据库中[4]。相较通常的望远镜控制软件仅服务于观测的功能，我们的软件系统集成了多核并行预处理、图像实时压缩及传输、资料入库等功能，功能更加完备，自动化程度更高。

望远镜控制软件和CCD相机控制软件的功能相对单一，本文不再赘述其详细设计和实现过程。本文将对其余4部分软件展开详细描述，尤其是与观测人员直接进行人机交互的主控软件。

# 1系统设计

# 1.1需求分析

系统软件是实现FocusGEO高效准确运行的关键因素，需要满足下面几方面的重要要求：

(1）自动化程度要求高。要实现FocusGEO对台站上空地球同步轨道带反复扫描观测、数据预处理、  
图像压缩与数据传输等全过程操作，高度自动化是对系统软件的必然要求，以  
尽可能减少人工干预的频次[5]。(2）时序要求严。采用图像采集与数据实时处理并行工作的方法，确保所有进程在时间上不

发生冲突，除了严格计算每一个天区的观测耗时、望远镜每一次摆位耗时和每一次数据处理耗时等，还要设计严格的数据流向和时序关系。同时为了有效减少数据预处理耗时，采用多核并行处理的方式。

(3）鲁棒性要求强。

多个端口同时监听UDP消息，避免端口收发指令时发生冲突，并且本软件的UDP通信与FTP传输通信同时工作，做到各个通信线程互不干扰。对用户的每一步操作都要进行校验，避免用户操作不当导致的系统异常或崩溃。主控软件需要与望远镜软件、CCD相机软件和预处理软件同时通信，端口号一一对应，不能错发指令，指令的格式需要提前确认，并对接收到的指令进行格式校验，排除错误的消息。

(4）人际交互友好。

交互界面要做到简洁直观，软件的交互需要提供最明确的需求，可以使用户快速操作，即使不熟悉系统，也能快速操作[5-6]。

# 1.2系统功能

根据上述需求，除了望远镜控制和CCD相机控制软件以外，软件系统还包括任务解析控制、工况信息处理、图像压缩与传输、数据预处理和数据入库共5个模块或软件，功能如下：

(1）任务解析控制

解析任务计划的点位信息，发送时角赤纬等位置参数给望远镜软件，控制望远镜摆位，相机曝光，执行观测任务。

# (2）工况信息处理

即时处理前端观测设备的工况信息，处理过程包括工况信息获取、显示与传输等，以及根据即时工况信息提供设备故障报警功能。

# (3）图像压缩与传输

监控CCD 相机拍摄的FITS（FlexibleImage Transport System）图像，实时转换为JPG格式，同时主动将压缩图像推送到服务器。

# (4)数据预处理

接收主控软件发送的启动预处理的命令，在望远镜进行下一个天区观测的同时进行图像处理，在下一个天区拍摄完成之前数据处理结束。

# (5）数据入库

该模块在远程服务器终端运行，其作用是建立Oracle数据库，接收FTP传输的处理数据文件，做到数据的实时入库。

# 1.3系统流程

FocusGEO正式运行前，需先把主控软件、望远镜控制软件和CCD相机控制软件的IP地址以及端口号按照既定规则正确配置，保证UDP消息收发正常，并在服务器终端开启FTP服务器，确保观测图像和数据处理结果的流程正常运行。

正常工作时，主控软件根据任务计划发送UDP消息给望远镜控制软件，望远镜摆位到第1个天区，确认望远镜到位后，CCD相机按预先设置的模式（包括曝光时间和拍摄帧数）采集图像，采集过程中，图像转换与FTP传输模块监控新生成的Fits 图像并转换成JPG格式，通过FTP传输到远程服务器端。图像采集结束后，CCD相机软件发送拍摄结束的消息指令给主控软件，系统开始下一个天区的观测，与此同时，调用数据预处理模块开始执行数据预处理，并行的工作方式大大缩减了工作时间，预处理结束后主动通过FTP将处理结果传输远程服务器端并立即入库管理。整体执行流程如图3：

Fig.3The flowchart of FocusGEO software

# 2系统实现

软件系统采用C#语言作为软件系统的编程语言，开发平台为Visual Studio2012，开发环境为.NETFramework4.5框架。

主控软件包含两部分，(1)GUI界面，实现与用户的人机交互；(2)UDP控制端口，通过UDP集成控制望远镜、CCD相机和圆顶等设备。图4为主控软件工作状态图，点开始观测按钮后，自动执行任务计划，给望远镜和CCD相机发送设备观测参数指令，并判断接收的望远镜和相机反馈状态消息进行下一步操作，实现自动化观测。由于设备故障是望远镜系统运行不可避免的问题，为了增加系统的可靠性，GUI界面提供了工况信息模块，实时显示望远镜、CCD相机和时统的状态信息，工况信息的状态栏中都有设备故障报警功能[7]。

在局域网内，针对本项目发送频率低、报文很小的情况，同时又需要与6个网络端口进行通信的特点，经过认真分析和比较UDP和TCP通信的优劣，最终选择UDP协议通讯，因为UDP消耗资源少，响应迅速，灵活性强且无需像TCP那样建立连接消耗很长的时间。当然UDP协议通讯存在一个固有的问题：当发送频率过高、报文过大时容易发生丢包的问题。为此通过设置丢包重发机制和超时机制避免了上述问题，事实证明非常有效。为了避免主控软件多个端口同时接收消息时发生冲突，同时监听多个网络端口,采用委托的方式处理接收的UDP消息，当某个端口接收消息后会触发与该端口对应的事件，并使用Dispatcher.BeginInvoke函数异步执行触发的事件，确保程序的主线程正常工作，不受干扰。实现流程图见图 $5 ^ { [ 8 ] }$ 。

![](images/4caae774d1351e56d77b74689b5585e93eca83979929a4fb575b122bfca2ac20.jpg)  
图4主控软件工作状态界面  
Fig.4The screenshot of working status of the master software 图5UDP监听模块流程图 Fig.5 The flowchart of UDP listening   
图6图像监测、压缩与传输流程图

CCD 相机采集数据过程中，图像压缩与传输软件实时监控Fits文件的创建并进行压缩转换，软件采用FileSystemWatcher类监测D:DATA文件夹内.fit后缀文件的创建，当有图像创建后触发FileSystemEventHandler 事件，事件中执行图像压缩及转换图像格式的委托函数,委托函数需新建一个EncoderParameter类的实例对象配置图像质量比。在确保大屏幕(分辨率 $1 9 2 0 ^ { * } 1 0 8 0 )$ 能清晰显示的前提下，同时满足FTP快速传输的要求，经反复测试选择 $8 5 \%$ 的图像质量比最为合适，该参数下一幅5M的Fits图像压缩成JPG格式后大小为400K左右，压缩比约为10:1。压缩后的JPG图像通过FTP推送到远程服务器端，并将12个天区的图像显示到大屏幕上，同时数据立即录入Oracle数据库中。观测图像监测、压缩和传输流程见图6。

Fig.6 The flowchart of images monitoring, compression and transmission

Oracle在数据库领域一直处于领先地位,是目前世界上流行的关系数据库管理系统，系统可移植性好、使用方便、功能强，适用于各类微机环境。使用C#语言开发的应用程序可以很方便地应用Oracle数据库,C#语言与Oracle数据库之间的接口是指对Oracle 数据表的调用与数据更改等操作[9-10]。

.NETFramework框架包括4个数据提供者，分别用于不同的数据库标准，本软件针对Oracle数据库使用Oracle.NET数据提供者，包括了如下5个数据库对象：(1)数据库连接对象OracleConnecion，是一个与数据库进行连接的对象，包含着与数据源创建连接的信息。 (2)数据库命令对象OracleCommand，用于对数据源发出命令。(3)命令构造对象 OracleCommandbuilder，用于构建 SQL命令。(4)数据读取对象OracleDatareader，专门用于读取数据。 (5)数据适配器对象OracleDataAdpter，取得数据并且在数据与数据集之间建立一座桥梁。

在程序中使用数据库连接对象建立与数据库的连接，实例化一个数据库连接对象的实例对象con,连接字符串的参数在客户端程序的名称解析一致，使用con.Open（）打开数据库。应用数据库命令对象发送命令，对于从数据库中检索数据的语句可以使用OracleDataReader指令进行操作，更多的使用Insert操作向数据表中写入数据。操作完成后使用con.Close(关闭数据库[10]。

# 3结束语

本文介绍了FocusGEO系统软件的总体框架，采取主控软件集成控制望远镜和CCD相机的基本思路，实现系统自动化运行，减轻了观测人员的工作强度。截止目前，FocusGEO已经在上海天文台余山科技园区开始正常观测，系统软件运行状况良好，在系统软件的支持下，FocusGEO实现了对台站上空地球同步轨道带的反复扫描观测和数据实时处理，有效提高了系统可靠性和观测效率。系统软件全部为FocusGEO团队自行研发，通过该工程的实现，研究团队掌握远程控制、观测与数据处理、图像压缩、数据库设计与数据管理等方面的关键技术，为实现非通用系统的自动化控制提供了技术支撑。

考虑到上海的天气不利于光学观测，计划近期将FocusGEO搬迁至云南天文台丽江观测站，利用该观测站的良好夜天光和旱季连续观测的条件，开展常规观测，获取稳定持续的观测数据。同时为了实现在上海通过互联网进行远程控制，软件系统的通信协议将升级为HTTP协议，为后续的国际观测网做技术准备。

# 致谢：

感谢上海天文台光学天文技术室参与本项目的部分观测助手，他们在FocusGEO 软件系统的集成调试和试验观测阶段发现了不少问题，对软件的持续改进提供了大量有益的意见和建议。

# 参考文献：

[1]和寿圣,辛玉新，伦宝利，等.基于ASCOM和Modbus/TCP 协议的天文圆顶控制系统[J].天文研究与技术,2017,14(3):356-362.  
He ShouSheng,Xin Yuxin, Lun Baoli, et al. Astronomical dome control system based onASCOM and Modbus/TCP standard[J]. Astronomical Research & Technology, 2017,14(3):356-362  
[2]武鹏.天文望远镜的ASCOM开发技术研究[D].成都:中国科学院光电技术研究所,2015.[3]梁波，袁智，邓辉，等.一种基于异构操作系统的RTS2CCD 相机扩展方法[J].天文研究与技术—国家天文台台刊，2015,12(4)：466-472.  
Liang Bo, Yuan Zhi, Deng Hui, et al. A method to extend CCD operations across differentoperating systems in the RTS2 [J]. Astronomical Research & Technology—Publications ofNational Astronomical Observatories of China,2015,12(4):466-472.  
[4]卫守林,曹子皇，王峰，等.基于WebSocket 的RTS2Web控制研究[J].天文研究与技术—国家天文台台刊，2014,11(4):404-409.  
Wei Shoulin, Cao Zihuang, Wang Feng, et al. A study of Web control of an RTS2 system basedonthe WebSocket[J]. Astronomical Research & Technology—Publications of NationalAstronomical Observatories of China,2014,11(4):404-409.  
[5]和寿圣，范玉峰，王传军.基于ASCOM标准的CCD 自动观测系统[J].天文研究与技术—国家天文台台刊，2013,10（4）:386-391.  
He Shousheng,Fan Yufeng,Wang Chuanjun. An automatic CCD observation system based onthe ASCOM Standard[J].Astronomical Research & Technology—Publications of NationalAstronomical Observatories of China,2013,10(4):386-391.  
[6]陆栋宁，黄磊,陈颖为,等.85cm天文望远镜圆顶和天窗自动化系统研制[J].天文研究与技术一国家天文台台刊,2008,5(4):386-391.  
Lu Dongning, Huang Lei, Chen Yinwei, et al. Research and development of the dome/slit controlsystem for the 85cm reflector of NOAC-BNU[J]. Astronomical Research & TechnologyPublications of National Astronomical Observatories of China, 2008, 5(4): 386-391.  
[7]王武，王金锁，姜崇国.1.2米地平式望远镜软件系统设计与实现[J].云南天文台台刊,1991(1):53-60.  
Wang Wu,Wang Jinsuo, Jiang Congguo. Design and accomplishment of the Software for thecontrol system of the 1.2-m horizontal Telescope[J]. Publications of Yunnan Observatory,1991(1):53-60.  
[8]姚正秋，周必方，汪达兴.1.2米红外望远镜[J].天文学报,1990,31(3):284-290.  
Yao Zhengqiu, Zhou Bifang, Wang Daxing. 1.2m infrared telescope[J]. Acta Astronomica Sinica,1990,31(3): 284-290.  
[9]郑宇君.C#面向对象程序设计[M].北京：人民邮电出版社，2007.  
[10]刘秋香，张永胜．VisualC#下利用ADO.NET访问 SQL Server 技术[J].计算机系统应用，2004(11):66-69.  
Liu Qiuxiang, Zhang Yongsheng. The technique of visiting SQL Server using ADO.NET inVisual C#[J]. Computer Systems & Applications，2004(11):66-69.

# Design and Implementation of Software System for FocusGEO

WANG wei, MAO yin-dun, CHEN guo-ping, ZHANG yong-shuai, YU yong, LUO hao (Shanghai Astronomical Observatory, Chinese Academy of Sciences, Shanghai, 200030)

Abstract: FocusGEO is a new generation of geostationary orbit dynamic monitoring system developed by Shanghai Observatory, it lacks the standard hardware underlying driver compared to most commercially available astronomical telescopes, which can not design and develop Linuxbased RTS2 or Windows-based ASCOM fully automated software system. The research team developed a set of Windows-based software systems for the special needs of geosynchronous orbit dynamic monitoring optical system(FocusGEO)， which can realize telescope automatic observation, data real-time processing,data transmission and data management process. In this article,introduced the system implementation framework and the overall process for the GEO dynamic monitoring telescope,and focus on the method of real-time image conversion and transmission, real-time data processing and storage of the realization. The software system is stable and reliable,which can provide reference for the development of automatic control software for non-universal telescope system.

Key words: telescope; automatic observation; communication protocol; database