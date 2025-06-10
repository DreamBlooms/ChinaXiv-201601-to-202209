# 一种新型分布式电源并网接口装置设计与应用

林其友」张兴生² 吴顺风2(1.国网芜湖供电公司芜湖2410272.南京能迪电气技术有限公司南京210000)

![](images/7026699104816fbb10484e42938b38ff14f2ee010402a427ad7aab2bbf6f7514.jpg)

林其友男 1976年生，高级工程师，主要从事电网规划与运行控制，电力市场分析与输配电自动化等方面的工作。

摘要：为了对分布式电源进行有效的管理，设计和开发了DARI-3317分布式电源并网接口装置。该装置不仅集成了保护、测控、反孤岛、电能质量监测、规约转换、远动和信息加密功能，同时具备与调度主站实时反馈电站信息、接受远程控制公共连接点开关投切及逆变器启停，实现调度端对分布式发电系统的实时监控。此外，该装置软硬件平台设计具备开放的接口和扩展裕度，便于将来的扩展和技术升级，保证装置更长的有效使用寿命周期。DARI-3317分布式电源并网接口装置已在国网某分布式光伏电站正式投运，在实际工程应用中得到验证。

关键词：分布式电源 并网接口分层分布式保护测控中图分类号：TM711

# Design and Application of A New Type Grid-Connected Interface Device forDistributed Generation

![](images/624151358927cd633c0a6b3af42d8a720df263a790e6eb0b7768c0e8c6c5715a.jpg)

Lin Qiyou'Zhang Xingsheng² Wu Shunfeng2 (1. Wuhu Power Supply Company of State GridWuhu241027 China 2.Nanjing Energy Digital Electric Co.,Ltd. Nanjing210000 China)

张兴生男 1987年生，工程师，主要从事电力系统保护控制系统、电力通信系统方面的工作。

Abstract: It is very necessary to design and develop a set of distributed power grid interface integration device. The DARI-3317 distributed power grid interface device is designed and developed in the paper,and this device not only integrates the protection, measurement and control, the island, code conversion, telecontrol, power quality monitoring and information encryption, but also can communicate with scheduling master station to feedback real-time power station information,and accept the remote control to switch on or off the point of common coupling,and to start or stop the inverter. This device can realize real-time monitoring of the distributed power system.In addition, the soft and hard platform design of this device is with open interface and the extension of margin, facilitating future extension and technology upgrades,and ensuring more effective plant life cycle.The DARI-3317 distributed power grid interface device has been successfully applied in some distributed photovoltaic power station,which is validated by the practical engineering application.

Keywords: Distributed power,interface device,hierarchical distributed architecture, protection,measurement and control

# 1 引言

发展清洁能源已是大势所趋。近年来，我国大力推动能源结构优化，但煤炭作为主体能源的格局没有改变，其在一次能源消费中的占比仍超六成。2014年，我国非化石能源占一次能源消费比重仅为$1 1 . 1 \% ^ { [ 1 ] }$ 。目前分布式电源多以接入配电网运行为主，分布式电源的接入使传统配电系统从辐射形网络变为遍布中小电源和用户的互联网络，对传统配电系统产生巨大的影响[2-4]。分布式电源分布较广，管理困难，如果不能对分布式电源进行有效的管理，将对电网的运行、维护、检修带来安全隐患，直接影响电网的安全稳定运行，因此，设计和开发一套分布式电源并网接口一体化装置十分必要。

目前，关于分布式发电并网的研究成为热点[5-7]。文献[8]在总结分布式发电并网发展及应用的基础上，对分布式发电并网技术、含分布式发电的系统进行分析，并从运行与控制等方面分别进行了详细的介绍和研究。文献[9]采用PS50CLA120IPM智能模块作为主逆变桥路，TMS320LF2407信号处理器作为控制芯片，分析了分布式发电装置在孤岛状态下的应对措施，并提出了综合性并网控制系统实现的可能性以及相应的控制策略，但该文献没有从电网端对分布式并网的要求进行分析。文献[10]等研制了分布式光伏并网接口装置，具备分布式光伏发电保护、测控、电能质量监测、运行控制、通信管理、远动、信息安全加密等功能，实现了调度端对分布式光伏发电系统的实时监控，但该文献主要介绍装置的个体功能，没有考虑通道的要求和现场应用的适应性。

针对目前分布式电源并网存在的问题，本文设计和开发了DARI-3317分布式电源并网接口装置，该装置不仅集成了保护、测控、反孤岛、电能质量监测、规约转换、远动和信息加密功能，同时具备与调度主站实时反馈电站信息、接受远程控制公共连接点开关投切及逆变器启停，实现了调度端对分布式光伏发电系统的实时监控。此外，该装置软硬件平台设计具备开放的接口和扩展裕度，便于将来的扩展和技术升级，保证装置更长的有效使用寿命周期。DARI-3317分布式电源并网接口装置已在国网某分布式光伏电站正式投运，在实际工程中得到了验证。

# 2分布式电源并网接口装置研制

DARI-3317分布式电源并网接口装置的设计参

考了国家相关规范[11-12]，并充分考虑了现场的实际需求与运行环境。

# 2.1硬件设计

（1）硬件结构总体说明。DARI-3317分布式电源并网接口装置采用4U高度、19英寸半层标准机箱。机箱采用整体面板及大背板结构。背板出线分上、下层布置，上层为弱电系统，下层为强电系统，包括直流电源、模拟量和开关量输入等。插件采用贴装技术，将DSP系统、模－数系统集于一体。为提高系统的可靠性，采用高可靠的光耦合器件，增强了装置的抗干扰能力。装置的安装方式为嵌入式安装；结构型式为组合插件式；接线方式为后接线方式。硬件结构总体框架如图1所示。

![](images/841ecb34ba893e88c3e1138afe3df25bc73c2790d704f864bfa6768bb33fc15c.jpg)  
图1硬件结构总体框架  
Fig.1 Overall framework of the hardware structure

分布式电源并网接口装置具有以下特点：

1）装置主CPU采用高性能DSP+PowerPC。2）其他主要器件均为工业级主流芯片。3）装置平台功能强大，为网络通信、多装置通  
信、数据实时采集、数据库管理、文件存储管理等  
功能应用提供足够的支撑和可扩充裕度。(2）分布式电源并网接口装置。分布式电源并  
网接口装置典型配置如图2所示，交流量、开入量、  
开出量的板卡数可根据现场需要进行增减配置，同  
一功能板卡的分支类型可根据现场情况选配。(3）插件。DARI-3317分布式电源并网接口装  
置插板主要包括CPU插件、GPRS 插件、交流变换  
插件、开入量采集插件、电源插件和操作回路插件  
等。CPU插件固定插槽位置，主要是光/电网口、  
RS 232串口、RS485串口的组合配置。GPRS插件  
为可选模块，用户可采用GPRS方式与主／子站通  
信时配置。交流输入变换插件共10个模拟量通道，  
包括三相电压（TV额定电压100/380V）、三相保护  
TA输入、三相测量TA输入和一相零序TA输入。  
开入量采集插件有DC110V或 $2 2 0 \mathrm { V }$ 自适应、DC

① ① ① ① ① ① ①+ + + + + + +SWI SWITCH COM POWER CPU DIN AC000□ PWR1 PWR2 PW3 □ 自 e□ 1 D 123 1 PM ROOT ALM 68 23 □ □ 23 日 23 1 24 □ LNK1 LNK2 LNK3 4 □ 4 2 4 團 國 456789101123415671892021 1 Tx2 D □□□ 567 67 中 3 567 □ 金金 5 68Rx ！ 8910 8910 □□□ 4 8910 T 密 聘1 2■3 x ！ 日 1 1213 1316□□□ □ 二□□□□ 2 3 □ □ 14 15 □ 團 國 17185 46 456 □□ 16171819 围墨 金步 2122232420 □O□ \~ 8 21 □22 □ 22 22 □D D D D+ + + + + + + +① ① ① ① ① ① ①

24V或48V自适应、AC110V或 $2 2 0 \mathrm { V }$ 自适应三种插件供选择，与电源输入电压保持一致。操作回路插件用于完成对断路器的各种操作，包含跳合闸触点和报警触点，适用于弹簧机构断路器和不带压力机构的永磁断路器。

（4）供电方式。分布式电源并网接口装置的主电源可同时接纳交流供电和直流供电，两者互为备用。蓄电池作为电源后备用，当交流供电中断，系统会自动切换蓄电池供电；交流供电和蓄电池供电可实现无缝切换，保证了系统设备的正常持续工作。

# 2.2 软件设计

分布式光伏并网接口装置软件系统采用面向对象的设计方法，由各个功能模块构成。程序设计简单明了，便于扩展，方便维护升级。图3为装置软件结构图。

![](images/5295da87ccaf1a376c8860bf29d3bb4d474b960e30864533bc554a7a99a1551b.jpg)  
图3装置软件结构图  
Fig.3 Device software structure

以保护程序为例，简要说明程序设计的流程，如图4所示。保护主程序在每个采样周期都会根据采集的模拟量、开关量的信息，以及装置硬件自检、外部异常情况检查，来判断是否其进入正常运行程序或故障计算程序。正常运行程序包括状态监视、数据预处理等功能，故障计算程序中进行各种保护的算法计算、跳闸逻辑判断等。当装置硬件自检出错，发装置闭锁信号同时闭锁装置，保护退出。

![](images/1d1dbfef245a4edb7487a8811bae08a15d0101bc1ccca51fd83497bc773a9f3d.jpg)  
图2分布式电源并网接口装置典型配置图 Fig.2Typical configuration diagram of distributed power grid interface device   
图4保护程序结构框图  
Fig.4Structure diagram of protection program

# 2.3通信机制

分布式电源并网接口装置不仅集成了保护、故障解列、测控、反孤岛和电能质量监测功能，还具备规约转换、远动和信息加密功能，为运行监控主站或调度主站与分布式电源设备之间建立了通信桥梁，起到承上启下的作用，一方面对上（运行监控主站、调度）上送遥信、遥测、电度、电能质量等信息，并接受主站的遥控、遥调等命令，另一方面对下（光伏逆变器控制器）转发遥调、启停等命令并接收光伏逆变器控制器上送的相关遥信信号。

DARI-3317集成通信管理装置的功能和光纤以太环网功能，能够实现光伏电站从逆变器、电度表、环境监测仪等智能设备的接入与信息的转发，通信规约既可扩展，又可配置。DARI-3317支持以太环网 (100M)，站内其他装置可以直接接入光纤构成以太环网，节省光端机，施工简单，通信可靠。

(1）通信端口：2个/4个光纤以太网接口，2个/4个电以太网接口，7个/10个RS485/RS232串口，内置／外置无线GPRS通信接口。

(2）对于不方便接入光缆的站点，通过GPRS/CDMA无线方式实现主站、子站的通信。内置GPRS板卡插件，或者外置GPRS/CDMA模块，通过串口与装置连接。

(3）对于CPU板上有以太网光纤口配置的情况，需要根据实际工程使用数量另外选择光纤模块；

光模块支持带电热插拔功能，直接插入CPU板的光模块插槽口即可用。光纤模块类型见下表。

# 表光纤模块类型

Tab．Optical fiber module type   

<html><body><table><tr><td>模块</td><td>介质</td><td>型号</td><td>波长及通信距离</td><td>接口</td><td>参数</td></tr><tr><td rowspan="3">百兆模块</td><td>多模</td><td>FTLF1217P2BTL</td><td>1310nm 2km@62.5/125um</td><td rowspan="2">LC接头</td><td>TX：-15dBm (Min) RX：-31dBm (Max)</td></tr><tr><td rowspan="2">单模</td><td rowspan="2">FTLF1323P1BTL-NJ</td><td rowspan="2">1 310nm 40km@9/125um</td><td>TX：-5dBm (Min)</td></tr><tr><td>0dBm (Max) RX：-34dBm（Min）；</td></tr></table></body></html>

(4）通信规约。对下可同时支持上百种规约，如Modbus、DLT645、IEC60870-5-103等；对上与调度主站通信，支持IEC60870-5-101：2002、IEC60870-5-103、IEC 60870-5-104 规约。

根据实际通信条件，分布式电源并网接口装置DARI-3317与主站之间的通信可以支持光纤通信或无线通信（GPRS）。

# 3 应用功能

(1）保护功能。主要包括三段可经方向和复压闭锁的过电流保护、两段零序过电流保护、过负荷保护以及逆功率保护。

(2）异常告警功能。包括事故总信号、TV断线报警、TA断线报警、控制回路断线报警、TWJ异常报警。

(3）故障解列功能。包括两段欠电压保护、两段过电压保护、两段低频保护和两段高频保护。

(4）遥测功能。采集三相电压、电流和零序电流，实现三相电压、线电压、零序电压、正序电压、负序电压，三相电流、零序电流，三相有功功率、三相无功功率、三相视在功率、三相功率因数、总有功功率、总无功功率、总视在功率、总功率因数、谐波等数据的测量。

(5）遥信功能。实时采集现场接入的位置状态和其他状态信息，通过“总召查询”、“变位主动上送”等方式将状态信息远传。采集线路间隔的开关位置(单/双位置)，弹簧末储能信号，遥控把手的远方／就地信号、保护、告警事件SOE等。

(6）控制功能。对具备遥控条件的开关进行远方遥控，开关检有压自动合闸。

（7）反孤岛功能。主要包括两段欠电压、过电压、低频、高频保护，自适应孤岛识别，主动式孤岛识别。

（8）电能质量监视。实时监测三相电压、线电压、零序电压、正序电压、负序电压，三相电流、零序电流，功率相关数据，三相电压基波和 $2 \sim 2 3$ 次谐波电压有效值、三相电流基波和 $2 \sim 2 3$ 次谐波电流有效值，谐波总畸变，电压、电流的不平衡率。

（9）装置自检异常。主要包括装置闭锁、装置报警、定值文件出错、定值整定出错、定值变更告警、A-D采样出错、光耦电源失电、通信中断、装置主/后备电源相关告警。

(10）电池管理。主要指蓄电池活化。可按照既定活化周期系统自动启动活化，也可本地以及远方人工启动活化。由于主电源失电，蓄电池放电至关断电压时，电池输出自动关断，保护蓄电池组不致过放。

（11）权限管理功能。对参数设置、查询、装置初始化、装置重要数据抄读等，提供装置登录权限、密码管理，防止对装置的非法操作，保证信息安全。

(12）参数查询及设置。装置相关参数以及定值可由主站、手持装置、专用调试软件取得对应权限后查询、设置。

此外，通过本地监控或调度侧主站与DARI-3317通信，能够实现定值的上送和远方修改、故障信息上送、运行告警信息上送，遥信变位上送、遥测上送、遥信上送、总查询和装置远方对时等功能。

# 4 应用

本文研制的DARI-3317分布式电源并网接口装置已取得了国网电科院检测中心的型式试验报告，各项指标符合检测规范，并成功应用于国网某分布式光伏电站。如图5所示，分布式电源并网接口装置交流插件并网口的TV、TA，主要用于测量电压、电流，监测电能质量、保护。分布式电源并网接口装置之间、分布式电源并网接口装置与调控主站之间采用光纤通信，分布式电源并网接口装置与逆变器之间采用串口通信，分布式电源并网接口装置与站内监控设备采用以太网通信。电压、电流测量精度为0.2级，有功功率、无功功率、视在功率、功率因数的测量精度为0.5级。平均无故障时间（MTBF）大于 $5 0 ~ 0 0 0 \mathrm { h }$ 。在主站报文对时，对时误差小于1s。自带时钟芯片，在无主站对时情况下，时钟在168h内走时小于1s。

![](images/9eb1d65d4c87968aa953396a769e3d37eb551ddc7f54e33c605d0d7efb159148.jpg)  
图5分布式电源并网接口装置的接线示意图 Fig.5The wiring diagram of distributed power grid interface device

# 5 结束语

分布式电源能量利用率高，环境污染少，被广泛应用到电力系统中。随着分布式电源不断地发展，并网对大电网的影响也越来越大。分布式电源分布比较广，管理比较困难，如果不能对分布式电源进行有效的管理，将对电网的运行、维护、检修带来安全隐患，直接影响电网的安全稳定运行，因此，设计和开发一套分布式电源并网接口一体化装置十分必要。

DARI-3317分布式电源并网接口装置采用先进的软硬件技术，精心的结构设计，使保护和测控既相对独立又相互融合，保护装置工作不受测控和外部通信的影响，确保保护的安全性和可靠性。采用分层分布式结构，可集中组屏，也可安装于开关柜上，整个系统灵活可靠，各间隔单元功能独立，没有相互依赖性，某一个装置的损坏不会影响其他装置的功能。充分发挥四合一的特点和通信网络的优势，集保护测控功能于一体，采用通信网络传递信息，可取消常规的二次信号控制电缆，简化二次电缆接线。不仅减轻了TA、TV负荷，而且节省了大量投资，节约了人力物力，减少了施工难度及维护工作量。同时为了同传统方式兼容，保留了部分远动信号及中央信号，背板端子也沿用了传统模式，兼容传统的操作控制模式。

本文研制了分布式电源并网接口装置，并成功投入了运行，为规范分布式电源电站的信息采集和上送提供了理论和实际指导。DARI-3000系列保护测控装置将进一步得到推广。

# 参考文献

[1] 刘振亚．全球能源互联网[M]．北京：中国电力出版社，2015.  
[2] 裴玮，盛鹃，孔力，等．分布式电源对配网供电电压质量的影响与改善[J]．中国电机工程学报，2008，28(13):152-157.Pei Wei,Sheng Kun,Kong Li,et al. Impactand improvement of distributed generation ondistribution network voltage quality[J]. Proceedingsof the CSEE,2008,28(13):152-157.  
[3] 柳睿，杨镜非，程浩忠，等．分布式电源并网的综合评价[J]．电力系统及其自动化学报，2013，25(1): 34-39.Liu Rui, Yang Jingfei, Cheng Haozhong.Comprehensive evaluation of grid-connecteddistributed generation[J]. Proceedings of the ChineseSociety of Universities,2013,25(1): 34-39.  
[4] 唐亮．分布式电源的分类及对配电网的影响[D].合肥：合肥工业大学，2007.  
[5] 赵毅，孙文瑶，许傲然．分布式电源并网对配电网影响的研究[J].沈阳工程学院学报（自然科学版），2012，8(1)：11-13.Zhao Yi, Sun Wenyao,Xu Aoran. Research oneffect of distributed generation grid-connected ondistribution network[J]. Journal of Shenyang Instituteof Engineering(Natural Science),2012,8(1):11-13.  
[6] 杨阳，孙侃，王建华．分布式电源接入的同期并网装置的设计[J]．科学技术与工程，2011，11(28)：6850-6854.Yang Yang, Sun Kan, Wang Jianhua. The equipment ofdistributed power in synchronized grid-connected[J].Science Technology and Engineering,2011,11(28):6850-6854.  
[7] 曾正，杨欢，赵荣祥，等．多功能并网逆变器研究综述[J]．电力自动化设备，2012，32(8)：5-15.Zeng Zheng, Yang Huan, Zhao Rongxiang. Overviewof multi-functional grid-connected inverters[J].Electric Power Automation Equipment,2012,32(8):5-15.  
[8] 刘杨华，吴政球，涂有庆，等．分布式发电及其并网技术综述[J]．电网技术，2008，32(15)：71-76.Liu Yanghua,Wu Zhengqiu, Tu Youqing,et al.Asurvey on distributed generation and its networkingtechnology[J].Power System Technology,2008,32(15): 71-76.  
[9] 陈理．分布式发电装置控制系统的设计和研究[D].杭州：浙江大学电气工程学院，2006.  
[10] 孙献春，徐光福，黄宏盛，等．分布式光伏发电并网接口装置研制与应用[J]．华东电力，2014,42(1):124-127.Sun Xianchun,Xu Guangfu,Huang Hongsheng,etal.Development and application of grid-connectedinterface device for distributed PV power[J].EastChina Electric Power,2014,42(1):124-127.  
[11] 国家电网公司.Q/GDW480—2010分布式电源接入配电网相关技术规定[S]．2011.  
[12] 国家电网公司．分布式电源接入系统典型设计[M].北京：中国电力出版社，2014.