# VLBI数据记录系统Mark6及相关技术研究进展

郭绍光，朱人杰，郑为民，范庆元，李纪云，赵融冰，张秀忠，徐志骏，甘江英，吴亚军

（中国科学院上海天文台，上海200030)

摘要：随着数据记录速率的提高以及对数据准确性的要求，老的采集系统已经不能满足新的要求，迫切要求采用新的终端和技术。Mark6是麻省理工学院研制的最新的记录终端，已经用于主要的天文机构，比如 JIVE、KASI、Max-Planck-Institute等。首先介绍了VLBI数据记录终端的现状，给出了上海天文台对Mark6软硬件的调试与配置；然后介绍了使用Mark6与CDAS2互连进行数据记录的测试及分析；最后对Mark6系统的应用及相关软件的后续研发进行了简洁阐述。可为后续终端采集系统的安装、配置及升级提供指导及参考。

关键词：Mark6；终端系统；数据记录；射电技术；甚长基线干涉测量中图分类号：P11 文献标识码：A 文章编号：1672-7673(2017)03-0281-07

甚长基线干涉测量(Very Long Baseline Interferometry，VLBI)是20 世纪60 年代后期发展起来的射电干涉新技术。独立本振以及信号记录设备的应用使得角分辨率得到提高，是现代天文观测中角分辨率最高的观测技术之一[1-3]。

为了适应不断提高的数据速率、不断增加的记录带宽、大数据量以及数字基带转换器各种观测模式的需求，新记录终端的需求迫在眉睫。例如，在大地测量学中，下一代的甚长基线干涉测量全球观测系统（VLBI2010GlobalObservingSyste，VGOS），希望在全球尺度上达到 $1 \ \mathrm { m m }$ 的定位精度，系统使用可以快速旋转的 $1 2 \mathrm { ~ m ~ }$ 灵敏小天线，并且所需带宽达到了 $4 ~ \mathrm { G H z } ^ { [ 4 ] }$ 。天文学中视界望远镜（EventHorizon Telescope，EHT)工作在毫米波段，角分辨率达到 $2 0 ~ \mu \mathrm { a s }$ ，考虑到大气相干对观测幅度值的影响，在短时间内获得足够的灵敏度也需要4GHz 的带宽[5]。两者目前的计划记录速率都是16 Gbps/台站，未来可能有更高记录速率的需求[4-5]。

Mark6数据采集和记录系统是为了满足日益增加的甚长基线干涉测量灵敏度研发的，遵循高速存储、容易维护的原则，Mark6系统具有16Gbps 的稳定记录速率，支持通用的甚长基线干涉测量数据格式，并且可以从原来老的Mark5系列数据采集记录系统平稳过度升级。

目前主要的天文数据处理机构已经将终端更新到了主流的 $\mathrm { M a r k } 6 ^ { [ 6 ] }$ 。上海天文台也已经配置了Mark6 系统，并与上海天文台第2代数据采集系统[7]（Chinese Data Acquisition System 2，CDAS2)进行了最新的数据采集记录测试实验。

# 1甚长基线干涉测量数据采集系统简介

数据终端采集系统是甚长基线干涉测量系统的重要部分，它支持的数据采集、数据编码、记录速率、记录模式、数据连续性等，将直接影响后续的相关处理。

美国国家射电天文台（National Radio Astronomy Observatory，NRAO)于1967 年研制了Mark1，经过 50年不断的更新和快速发展，目前已经研发升级到 Mark6 系统，其中的记录媒介也从一开始的磁带记录转

换到硬盘记录，并展开了相应的e-VLBI研究[8]。

数据记录媒介从磁带（Mark1，Mark2，Mark3）转移到硬盘（从Mark4系统开始），这主要得益于硬盘价格的下降、容量的增加以及硬盘相比于磁带的诸多优点，比如记录/回放数据质量高，几乎没有误码，不会有磁头磨损问题等[9]

到目前为止各类终端的系统性能及使用年份信息见表1。

中国VLBI 网（Chinese VLBI Network，CVN）由上海 $2 5 \mathrm { ~ m ~ }$ 、佘山 $6 5 \mathrm { ~ m ~ }$ 、密云 $5 0 ~ \mathrm { m }$ 、昆明 $4 0 \mathrm { ~ m ~ }$ 及新疆 $2 5 \mathrm { ~ m ~ }$ 望远镜组成[11]，作为我国探月工程测控系统的甚长基线干涉测量测轨分系统，提供了嫦娥卫星的精确角位置信息，与我国航天测控网一起圆满完成了相应的测轨任务[12]

中国VLBI网目前的终端系统由上海天文台

表1各类终端的信息[10]  
Tabel1The information of different terminals   

<html><body><table><tr><td>型号</td><td>使用年份</td><td>记录速率</td><td>记录介质</td></tr><tr><td>Mark 1</td><td>1978</td><td>1 Mbps</td><td>计算机磁带</td></tr><tr><td>Mark 2</td><td>1981</td><td>4 Mbps</td><td>录像带</td></tr><tr><td>Mark 3</td><td>1986</td><td>112 Mbps</td><td>视频磁带</td></tr><tr><td>Mark 3B</td><td>1994</td><td>112 Mbps</td><td>视频磁带</td></tr><tr><td>VLBA4</td><td>2000</td><td>1 Gbps</td><td>薄视频磁带</td></tr><tr><td>Mark 5A</td><td>2004</td><td>1 Gbps/512 Mbps</td><td>硬盘/磁带</td></tr><tr><td>Mark 5B</td><td>2006</td><td>1 Gbps</td><td>硬盘</td></tr><tr><td>Mark 5B+</td><td>2006</td><td>2 Gbps</td><td>硬盘</td></tr><tr><td>Mark 5C</td><td>2010</td><td>4 Gbps</td><td>硬盘</td></tr><tr><td>Mark 6</td><td>2013</td><td>16 Gbps</td><td>硬盘</td></tr><tr><td>CVN 阵列</td><td>2016</td><td>8 Gbps</td><td>硬盘</td></tr></table></body></html>

自行研制的数据采集系统（Chinese Data Acquisition System，CDAS）和数据采集记录系统 Mark5B 组成。Mark6 系统相较于Mark5系统，在以下方面做出了改进：增加了记录数据率，将硬件全部更改为商用产品（Commercial Off The Shelf，COTS），软件全部开源[13-14]

# 2Mark6数据采集记录系统

Mark6系统起初是专门为甚长基线干涉测量优化的基于磁盘的数据获取和记录系统。作为Mark5系列的下一代产品，Mark6将稳定的记录速率提高到了16 Gbps。Mark6 相对于原来的产品最大的区别在于使用了商用产品并开源相应的软件。

# 2.1 设计原则

作为基于磁盘技术的最新一代高数据速率的甚长基线干涉测量数据记录与回放系统，Mark6在设计之初坚持两个原则[6]，一是主要原则，在硬件完成的基础上必须实现；二是扩展原则，在条件允许的情况下考虑实现。

目前测试使用的Mark6已经完成了主要的设计目标，主要目标如下：

（1)16 Gbps 持续稳定的记录能力：在4个硬盘模组全部在线的情况下，保持该速率进行持续记录;（2)支持通用的甚长基线干涉测量数据格式：目前支持天文通用的 Mark5B 和VDIF数据格式;（3)尽可能使用商用产品：数据传输使用Conduct 公司设计的底板[15]；（4)开源软件：在Debian系统上可以查看安装的所有源码及相应的程序；（5)价格相对便宜：不包括硬盘的Mark6，价格在2万美元左右；（6)保持对Mark5的硬件投资：从Mark5可以平稳过度到Mark6，以保留对Mark5的硬件研发投资，可以通过购买升级配件，将Mark5B升级到Mark6。

# 2.2 硬件设计

Mark6主要由商用部件组成，其主底盘机架内含有计算机主板、硬盘；机架后面板有外接显示器、键盘、鼠标、 ${ \mathrm { S F P } } +$ 网卡、千兆网卡等接口。

Mark6 的硬件如图1和图2，由5U的主底盘（图中数字1、2标示）、1U的线缆控制面板和5U的扩展底盘(图中数字3、4标示)组成，共占用空间 $1 1 \mathrm { ~ U ~ }$ 。

通过标记的数字可以知道，模组1、2、3、4在线缆控制面板的顺序为1、3、2、4，这也对应了前后面板的连接线顺序。

Mark6 的前面板如图1，包括4个硬盘模组（含1、2主模块组以及3、4扩展模块组）、一个1U的线缆挡板以及4对 SAS 连接线，其中每对 SAS 负责一个硬盘模组的高速数据传输采集，后面板如图2，包括4个万兆光模块（用于10G网络数据的采集）、2个千兆光模块（其中一个用于对 Mark6的控制，另外一个保留）、及4对 SAS 线接口（用于连接前面板的硬盘模组）。其中通信控制接口位于最左端的1G以太网接口eth0，右端与之相邻的eth1目前保留不用。外接显示器的视频图形阵列（VideoGraphics Arry，VGA)插槽右边有2个网络接口卡（Network Interface Cards，NIC）。每个网络接口卡都有2个10G的 ${ \mathrm { S F P } } +$ 光纤模块（10 Gigabit Small Form Factor Pluggable， $\mathrm { \ S F P + }$ ），对应的接口分别为：eth2、eth3、eth4、eth5，各自的默认IP为192.168.1.2-5。

![](images/0dd071af626b61a5d1fbc6696e585beb8d908409df16e834286a945e3c0848e3.jpg)  
图1Mark6前面板 Fig.1Mark6 front panel

![](images/6800e31a881df6ed20154d36777919e2c27fa50656d193337e4258356789015e.jpg)  
图2Mark6后面板Fig.2Mark6 back panel

# 2.2.1 硬件连线示意图

考虑到不同型号的 Mark6有不同的接口规则，针对 Mark6主底盘型号为4023及以后的版本，硬件的连线示意图如图3，连接时需要特别注意硬盘模组的位置与线缆控制面板的连接顺序以及连接中的 SAS 线的顺序，其中前面板示意图上的颜色对应后面板的颜色接口。图4中4个万兆光模块eth2\~eth5主要用于10G网络数据的接收，千兆光模块ethO用于对Mark6的通讯控制，4对SAS线接口为光模块到硬盘模组的数据传输接口。

![](images/b8332f295a934db7256c7d0467f0faa57a32fd8dce245417b43f2252c4561320.jpg)  
图3Mark6前面板示意图Fig.3Mark6 front panel diagram

![](images/be962824311d0cb8947eb63b46528480255fc73b2d49499b04254a98329e851c.jpg)  
图4Mark6后面板示意图Fig. 4Mark6 back panel diagram

# 2.3 软件设计

Mark6 的操作系统采用通用的Debian 发行版系统[16]，该系统非常稳定，内核和内存的占用非常小，使用的软件都是经过测试的稳定版本，特别适合用做服务器操作系统。

Mark6 的软件设计使用分层的概念模型，Mark6软件模组化顶层设计，主要展示了软件设计的两个主要软件模组，即cplane 和dplane，其中的10 MB 数据块为每次缓存的存储量如图5。软件主要包

含cplane、dplane 和da-client3个组件，其中与用户交互的称为cplane，与网络和磁盘硬件交互的称为 dplane。cplane 和 dplane 通过UDP 协议通信。

# 2.3.1 cplane

cplane为用户提供了一个接口，并完成了一系列不同的高层次监控和控制。考虑到cplane的复杂性、易用性及可实现性，使用Python语言实现。用户的接口采用标准VSI-S 协议[17]该协议增加了对Mark6系统的指令集。cplane 同时也负责管理磁盘模组，诸如挂载、卸载并绑定不同的磁盘到一个虚拟磁盘模组，最多支持32个磁盘的管理。

![](images/b6c20adecc4d069f3ef416320a25a952bdcd1d7df1376555e69b56eb11f25a1b.jpg)  
图5Mark6软件设计图Fig.5Mark6 software design

# 2.3.2 dplane

dplane 负责所有与高速数据流相关的任务。dplane从10G网卡读取数据，首先放入一个容量为56 GB 的随机存取存储器(Random-Access Memory，ARM)大的缓存区中，然后写入多个磁盘的文件中。数据的起始时间通过读取数据包的数据帧并解码帧头信息精确控制。

由于10G网卡需要达到4Gbps 的记录速率（非爆发模式下），考虑到dplane对高速处理的需求，使用C 编写，并将代码进行了高度优化。

程序dplane 采用多线程编程，针对每个输入流将单独分配一个线程资源，其中分配的缓存为全部 64 GB 物理内存的 56GB，占比达到 $8 7 . 5 \%$ 。

# 3与CDAS2 联调测试

Mark6 的输入为10G网络数据，此处采用上海天文台自行研制的第2代数据采集系统，输入的数据格式为VDIF，每台CDAS2输入速率为4Gbps。

测试中，使用4台CDAS2系统分别连接Mark6系统提供的4个10G光模块，记录的数据保存在Mark6硬盘上，Mark6与CDAS2的连接示意图如图6。图6展示了记录速率为16Gbps的示例，存储使用32块SATA硬盘，每块容量6TB，共 $1 9 2 \mathrm { T B }$ 。

![](images/78a745c516d6e69135c925859104fdc00af868181c393724855fd14ce7cf8d04.jpg)  
图6 CDAS2与Mark6互连示意图  
Fig.6The connection of CDAS2 and Mark6

# 3.1 测试步骤

在对Mark6进行数据采集记录之前，首先需要对输入源进行设置，实验中使用CDAS2，带宽可以设置 $1 0 0 ~ \mathrm { K H z } \sim 3 2 ~ \mathrm { M H z }$ ，支持16通道，最高支持 $1 6 \mathrm { b i t }$ 采样，详细的设置如图7。该图为设置其中一台CDAS2 系统，其中带宽为 $8 ~ \mathrm { M H z }$ ，8通道，2bits采样。

CDAS2 CONTROL PANEL V1.03_20160704 Serial No.:H-2-C-Z-1-1-01D-51103-02F Firmware:F-320-60426-400-60719 Device IP: 192 168 100 125 Disconnect Software: S-320-60309-430-60711 Sync Source FORMATSystem Time: 2016-08-04 09:11:27 ONTP OMK5B OVSR Time Sync Device Setting Advanced ORTC OVDIF Set Format Time: 2016-08-04 09:11:27 Reboot Data Capture Exit Frequency Bandwidth- -Mask- Channel Power  
CHO:321.750000 MHz CH8:337.750000 MHz ○ 32 MHz 00FF0001 ADCI-14.4804 CH7:37.5778   
CH1:323.750000MHz CH9:339.750000MHz ○ 16MHz Channel Select- ADC_Q-32.4136 CH8:37.5166   
CH2:325.750000 MHz CH10:341.750000 MHz 8 MHz CHO ☑CH4 口CH8 口CH12 CHO:37.7772 CH9:37.5189   
CH3:327.750000 MHz CH11:343.750000 MHz O 4 MHz CH1 ☑CH5 口CH9 口CH13 CH1:37.7459 CH10:37.4772   
CH 0 SOt OEGE CH2: Cg CH7:335.750000MHz CH15:351.750000 MHz ○ 200 KHz 01 02 0408 016 CH6:37.5831 CH15:37.3094 Mapping >> Set ○ 100 KHz InitegralTime None ○1s 0 5s □Use default settings Set Set O10s o20s Plot 10GE Destination IP Mapping- 10GEEnable FPGA Status Sourc Destination   
10GE-0: 192.168.2.2:3000 $$ 192 168 2 222 50000 回Enable 10GE-0 Kernel Voltage: 0.84045 $v$   
10GE-1:192.168.100.120:3001 $$ 255 255 255 255 65535 □Enable 10GE-1 Kuxe Tep: 61.2748 $\boldsymbol { \mathsf { v } }$ Set Aux Voltage 2: 0.84384 $\boldsymbol { \mathsf { v } }$

Mark6的采集记录流程与Mark5B不同，所有的记录操作在一个称为da-client的可交互程序里完成，da-client 通过接口协议与cplane 和dplane 进行通信。

具体的测试步骤如下：

(1)#初始化硬盘模组，分别为4组硬盘模组   
(2)mod_init $\ c =$ 1:8:SHAO_001: sg:new ;   
( $3 ) \mathrm { m o d \_ i n i t } = 2 : 8 : \mathrm { S H A O \_ 0 0 2 : s g : n e w } ;$ （20   
（ $4 ) \mathrm { m o d \_ i n i t } = 3 : 8 : \mathrm { S H A O \_ 0 0 3 : s g : n e w } ;$ （204号   
（ $5 ) \mathrm { m o d \_ i n i t } = 4 : 8 : \mathrm { S H A O \_ 0 0 4 : s g : n e w } ;$ （20   
(6)#建立虚拟硬盘组   
(7)group $\ c =$ new : 1234 ;   
(8) group $\mathbf { \tau } = \mathbf { \tau }$ open : 1234;   
(9)#设置输入数据流并提交   
（10)input_stream $\ c =$ add:CDAS2:vdif:1032:42:0:eth2:192.168.100.61:12000; (11)input_stream $\ c =$ commit ;   
(12)#开始记录，参数可配置   
(13)record=on

3.2测试结果分析

测试中，CDAS2采用Mark5B格式器编码，输入数据记录系统 Mark6中；Mark6使用分散-收集(Scatter-Gather，SG)模式对输入数据进行记录保存，保存的数据包括 meta 数据与二进制数据，其中meta 数据称为元数据，包含保存数据的各种信息，用于将分散的数据在聚合时提供参数。

图8为使用CDAS2与Mark6连接记录的5秒左右的VDIF格式数据，对该数据进行解帧头检验，横坐标为时间，纵坐标为秒内帧号，可以看到帧头信息联系，数据正确。

# 4总结与展望

为了应对VLBI2010、毫米波甚长基线干涉测量及其他日益增加的宽带观测，Mark6包括硬件和软件的研发还在更新升级，硬件的更新表现在后面板的设计布局在不断变化，包括对应的线缆插槽也可能更改，软件的升级表现在数据采集及更新中支持指令的扩充及参数更改，这也是Mark6在调试过程中容易出现问题的主要原因。所以，在调试时需要特别注意硬软件版本。

![](images/8fc6e591bd2bb7d22179f1c440159b96648b450155b62778764c076a3408672c.jpg)  
图8CDAS2与Mark6联调测试结果 Fig.8Joint test result of CDAS2 and Mark6

后续关于Mark6的测试，将考虑使用ROACH数字终端作为输入数据源，并将输出的数据使用上海天文台相关处理机或DiFX进行相关处理，并测试32Gbps爆发模式的记录能力，以及对 $\mathbf { e }$ -VLBI和回放的支持。

# 参考文献：

[1] Thompson A R，Moran JM,Jr G W S.Interferometry and synthesis in Radio Astronomy[M].Wiley，2001: 648-648.  
[2] 钱志瀚.甚长基线干涉测量技术在深空探测中的应用［M].北京：中国科学技术出版社，2012.  
[3] 林克雄.甚长基线干涉测量技术［M].北京：中国宇航出版社，1985.  
[4] Petrachenko W，Behrend D,Hase H,et al. The VLBI2010 Global Observing System（VGOS)[C].EGU General Assembly Conference，2013.  
[5] Doeleman S.Building an event horizon telescope:（sub）mm VLBI in the ALMA era [C/OL].(2010）[2016-11-29]. https://pos.sissa.it/cgi-bin/reader/conf.cgi? confid $= 1 2 5$ ：  
[6] Whitney A,Lapsley D.Mark 6 Next-Generation VLBI Data System [C]//Behrend D,Baver KD.Seventh General Meeting（GM2O12）of the international VLBI Service for Geodesy andAstrometry（IVS).National Aeronautics and Space Administration，2O12：86-90.  
[7] 朱人杰，张秀忠，韦文仁，等.我国新一代VLBI数字基带转换器研制进展［J］.天文学进展，2011，29(2)：207-217.Zhu Renjie，Zhang Xiuzhong，Wei Wenren，et al. The progress of modern Chinese DataAcquisition System [J]. Progress in Astronomy，2011，29(2） :207-217.  
[8] 杨文军，郝龙飞.VLBI终端系统的发展历史和未来展望［J].天文研究与技术——国家天文台台刊，2012，9(4)：374-381.Yang Wenjun，Hao Longfei. Development history and future prospects of VLBI terminals[J].Astronomical Research & Techonolgy- —Publications of National Astronomical Observatories ofChina，2012，9(4):374-381.  
[9] 韦文仁，薛祝和.基于磁盘的新型VLBI终端系统-MK5A终端系统［J]．天文学进展，2004，22(3):269-274.Wei Wenren，Xue Zhuhe.The disk-based VLBI terminal system：MK5A terminal system [J].Progress in Astronomy，2004，22(3）:269-274.  
[10] 薛祝和，王玲玲，王锦清，等.上海天文台MK5A终端系统的安装与测试［J].天文学进展，2004，22(4)：344-349.Xue Zhuhe，Wang Lingling，Wang Jinqing，et al. The installation and testing of MK5A terminalat Shanghai Astronomical Observatory [J]. Progress in Astronomy，2004，22(4）: 344-349.  
[11] 洪晓谕.VLBI技术的发展和“嫦娥工程”中的应用［J]．自然杂志，2007，29(5)：297-299.Hong Xiaoyu. VLBI techniques and application in the Chang'e lunar orbiter［J]. ChineseJournal of Nature，2007，29(5）:297-299.  
[12] 蒋栋荣，洪晓谕.甚长基线干涉测量技术在深空导航中的应用［J].科学：上海，2008,60(1):10-14.Jiang Dongrong，Hong Xiaoyu. VLBI for deep-space navigation [J]. Science，2OO8,60（1）:10-14.  
[13] Whitney A R，Beaudoin C J,Cappalo R J，et al.Demonstration of a broadband-RF VLBIsystem at 16 Gbps data rate per station [J/OL]. （2012）［2016-11-29]. htps://www.researchgate.net/publication/232503776_Demonstration_of_a_broadband-RF_VLBI_system_at_16_Gbps_data_rate_perstation? ev $\ c =$ auth_pub.  
[14] Whitney A R，Lapsley D E，Doeleman S S.Giga-bit/sec VLBI and e-VLBI [C]. AmericanAstronomical Society Meeting. Bulletin of the American Astronomical Society，2OO3，35：1209.  
[15] Conduant's multidrive recoder stores 16 Tbytes [R/OL].（2008-05-55）[2016-11-29].http://www.edn.com/design/test-and-measurement/4385900/Conduant-s-multidrive-recoder-stores-16-Tbytes.  
[16] Hunger B MI.Debian GNU/Linux Bible[M].Wiley，2001.  
[17] Whitney A. VLBI Standard Interface Specification [J/OL].（2009-01）[2016-11-29].https://www.researchgate.net/publication/265010140_VLBI_Standard_Interface_Specification.

# The Progress of VLBI Data Acquisition System-Mark6 and Related Techenologies

Guo Shaoguang，Zhu Renjie， Zheng Weimin，Fan Qingyuan，Li Jiyun， Zhao Rongbing,Zhang Xiuzhong，Xu Zhijun，Gan Jiangying，Wu Yajun(Shanghai AstronomicalObservatory，Chinese Academyof Siences，Shanghai 2Oo3o,China,Email：sgguo@ shao.ac.cn）

Abstract：With the improvement of the data recording rate and higher requirements to the accuracy of the data，the traditional acquisition system can not meet the new requirements，and it is urgent to use the new terminal and technology.Mark6 is thelatest recording terminal that is currently developed by MIT.It has been used by the main astronomical institutions，such as JIVE,KASI,Max-Planck-Institute and so on.This paper first introduces the VLBI data acquisition terminal and provides the debugging and configuration of the hardware and software of Mark6 in Shanghai Astronomical Observatory；Then，the data recording test and analysis of the interconnection between Mark6and CDAS2 are introduced；Finally，theapplication of Mark6 system and the subsequent research and development of related software are briefly described. This paper can provide guidance and reference for the installation，configuration and upgrade of the follow-up terminal acquisition systems.

Key words:Mark6；Terminal system；Data record；Radio technology；VLBI