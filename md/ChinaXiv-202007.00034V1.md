# 基于ARM架构的嵌入式系统在自动气象监测系统的应用：以NVST气象站为例

王新华1²，陈东」，罗林」，张涛」，杨磊」，徐稚」，谌俊毅1（1.中国科学院云南天文台 云南 昆明650011；2.中国科学院大学 北京100049）

摘要：自动气象监测系统是现代天文观测台站必备的辅助系统之一，传统自动气象系统是基于微控制器或PC开发的。微控制器多用于工业控制，无法满足多任务和批量数据的快速处理；PC由于高功耗、高成本及低可移动性无法在野外如选择台址时使用。为了克服上述两种开发方式的缺点，本文采用基于ARM架构的嵌入式系统为抚仙湖NVST开发一套低功耗、低成本、高稳定性的自动气象监测系统。本文介绍了NVST气象站的整体设计，软硬件功能以及调试中遇到的问题及解决方法。

关键词：自动气象监测系统；ARM架构嵌入式系统；NVST气象站中图分类号：TP274 文献标识码：A 文章编号：

# 0.引言

地基天文望远镜的成像质量与台址及其周围环境密切相关，在高分辨率太阳图像复原时需要知道观测时刻周围的准确环境信息从而更为精确的统计台站周围的大气性质。故自动气象监测系统是现代天文观测台站必备的辅助系统之一。其主要目的是：实时监控气象条件并提供给望远镜系统，以保障望远镜等设备仪器的安全;提供某些观测过程需要的精准气象及观测条件数据,作为数据处理的辅助参数;提供长期的气象及观测条件数据，用于评估台站观测条件[1][2][3]。

# 1．天文台站自动气象监测系统

一类是基于微控制器开发的自动气象监测系统，使用较为广泛的微控制器是STM32，STM32系列微控制器是ARMCortex-M3内核的高性能嵌入式控制芯片，主频为72MHz，拥有丰富的通信接口[4]。在文章[5]中作者基于此微控制器开发了一套较为轻便的气象站数据实时显示系统，系统结构图见图1a。此类气象站的优点是低功耗；高可移动性；资源占用少。其缺点主要表现在性能较低无法满足多任务、大批量数据的快速处理和管理同时难以提供完整的远程访问等软件功能（如Web 浏览和数据库等）。需要再添加服务器才能提供实时数据访问（含远程），数据库存储等功能，明安图射电频谱日像仪（MUSER）的 Vantage Pro气象站就是这类型气象站的代表[6]。

另一类是基于PC开发的自动气象监测系统。如图1b所示。PC完成数据的获取和处理工作，并提供如web界面、人机交互界面等丰富的软件功能。此类气象站的优点是高性能，数据处理快，高实时性；有强大的操作系统，可以为用户提供丰富的软件功能。其缺点主要

![](images/06b6d34701174171abf5642f284e45082a90a416a8ce5ae76bcbe701d5d9d947.jpg)  
图1两种常见的环境监测系统结构图  
Fig.1Structure diagram of two common environmental monitoring systems

根据未来天文台站自动气象站的发展趋势，气象站要具备低功耗、低成本、高可移动性和完备的软硬件功能等特点。本文将使用基于ARM的嵌入式系统来实现NVST自动气象监测系统的开发。基于ARM的嵌入式系统是微控制器和PC 的折中产品，其可以运行一个经过裁剪的Linux 系统，可以提供不亚于PC 的丰富软件功能，其性能可以满足多任务的快速数据处理需求，同时有较低的功耗和较高的可移动性。本文将以 NVST 气象站系统改进为例进行系统的开发和测试。

# 2．改造方案

2.1NVST现有自动气象监测系统存在的问题

NVST位于云南天文台抚仙湖太阳观测基地，隶属于中国科学院云南天文台，是“我国21 世纪初主要的地面光学及近红外太阳观测设备”。其有效口径为1米，真空窗直径达到1.2米，是目前世界上最大口径的真空望远镜，可在 $0 . 3 \sim 2 . 5$ 微米波段对太阳进行高分辨率成像和多波段光谱观测，测量太阳磁场的精细结构、高时空分辨率的演化过程。NVST 原自动气象监测系统结构图见图 $\mathrm { 2 a }$ 。

![](images/00ad1acea4da9be54617e304aa929819c8ebaca6c68e4af2a7ecc6f37c6bd6af.jpg)  
图2原NVST气象站  
Fig.2Original NVST weather station

此系统在实际使用中遇到以下问题：

(1）数据丢失：选取2017年至2018年的时间段，225天没有数据记录；对有数据的140余天进行数据统计，数据丢失率在 $6 \%$ 左右，整个系统处于不可控状态，数据丢失统计结果如图2b 所示；(2）数据离线存储，不便于远程和本地的数据查询;(3）自2019年7月起，系统频繁宕机导致NVST无法获取有关气象数据，尤其是风速等信息，对 NVST 设备安全造成了极大的隐患。同时，由于无法提供观测时间内的环境信息，已经影响如 AO(Adaptive Optics)系统的数据处理;(4）原自动气象监测系统软件是个封闭系统，无法根据实际情况自行增减功能。鉴于上述情况，本文计划在利用原有气象参数传感器的基础上，使用基于ARM架构的嵌入式系统开发一套功能完备、高稳定性、低功耗、低成本的自动气象监测系统。系统目的：以一定频率为FSO站内所有设备提供站点实时的气象信息，以保障 NVST及周边设备安全，同时站点内所有的仪器设备均可获取上述气象环境信息。

具体要求：

(1）以不高于1Os一次的频率为NVST提供基础的天气信息：温度、湿度、雨量、气压、  
风速、风向、露点、辐射强度，观测天区图像，并通过浏览器访问上述信息；(2）获取其他台站提供的基本太阳活动信息，并在发生剧烈太阳活动时给出提示;(3）极端气象条件报警功能：风速、湿度、温度、露点等达到预设警报值时，通过声光  
等手段报警；(4）由于传感器，数据传输以及其他原因等造成的数据丢失率 $< 1 0 \%$ ，即每天数据丢失  
小于864条（共8640条），约合2.4hrs的气象数据；(5）气象环境数据按标准归档到数据库，方便日后数据的查询和分析；(6）可在外网获取实时气象信息。

# 2.2系统设计

# 2.2.1系统总体结构和功能

系统由本地和远程两部分构成，本地包括数据获取、监控报警、数据入库等。图3显示了系统结构及功能图，远程包括显示实时气象数据和当天历史气象数据以及通过百度 Sugar的内网隧道功能为外网用户提供气象信息。图4是系统软件功能示意图。

![](images/b1b73095e43c7100a9ad5bb931e6aaf671d172df53838d1c8e6c1e7ec1397813.jpg)  
Fig.3System structure and function diagram

![](images/9c9f043c9e7a2753d8f1c5943ee9ebfe414c7b116fcdd2f3c4a525a307cab587.jpg)  
图3系统结构及功能图  
图4软件功能示意图  
Fig.4Software function diagram

# 2.2.2 本地

本地包括气象站数据采集、本地数据的存储、监控报警及数据处理。

（1）气象站数据采集

气象数据通过访问NVST原有气象站上位机获得，可以采集风速、雨量、温度、气压、辐射、风向、湿度等数据，通讯协议支持MODBUS 和XPH，本文采用MODBUS 通讯协议与气象站上位机通讯。

# (2）数据的存储

每隔十秒访问一次气象站上位机并将数据存储到本地，为了加快数据的成图速度，原始数据存放在内存中，并定期备份数据到本地磁盘。

# (3）监控报警

天气预警流程图如图5所示，当风速高于 $1 2 \mathsf { m } / \mathsf { s }$ 或有太阳活动爆发时通过声光等手段发出预警。

(4)数据处理

数据处理包括气象传感数据包的拆分和校验、数据的折线图显示（最大值、最小值、均值）、预警（天气预警和太阳活动预警）、全天图像的数据获取。

![](images/5017b8e43494966ca25184f8fe1dc1a06195147ae23381f54459ef56a6482c0b.jpg)  
Fig.5Weather Warning flow chart

# 2.2.3 远程访问

远程包括Web 服务器、MySql数据库及百度 Sugar。

(1) Web服务器

Web 服务器基于NodeJS开发，图6是Web服务器界面，提供气象数据、天区实况、耀斑爆发等信息。点击气象参数可以查看当天的对应参数的历史数据。

![](images/0ca8c10b6bcc74043aaacea870632b3ce502e32afe4496b03a2364c874484e70.jpg)  
图5天气预警流程图  
Fig.6The web page

图6 Web页面

(2)MySql数据库

由于气象数据的入库与采集是并行的。此模式会遇到两个问题：1.当数据库的连接和数据的写入所花时间小于10s，而数据的频率是10s一次，这会导致数据的重复存储；2.若数据库长时间连接异常，会造成数据丢失。为解决这两个问题，本系统的解决方案如下：

创建 missing.csv 文件，当发生数据库连接异常时，将这段时间的新数据缓存missing.csv内，待连接恢复后将数据库的最新数据的写入时间和丢失的数据做比较，如果不同则将 missing.csv 的数据存到数据库，如果数据库连接正常则将前一次存储的数据和最新获取的数据作比较，如果两者相同则不插入数据库，如果不同则插入数据库。这种方式既避免了数据的重复存储，也避免了数据的丢失，通过这种方式将数据库访问程序与访问上位机程序分离后不会再出现数据库数据与本地数据不同的情况，显著提高了数据的完整性和系统的鲁棒性。图7是防数据丢失程序流程图。

![](images/4ea57df1f2ef9e3c7d445a9e51313efda14f93f8e2f7bc1c9c2150af53dd7f05.jpg)  
图7防数据丢失程序流程图  
Fig.7Data loss prevention program flow chart

(3）百度 Sugar：为了便于外网用户访问气象数据，本文采用百度 Sugar平台来提供外网数据可视化服务；Sugar是百度云推出的数据可视化服务平台，目标是解决报表和大屏的数据可视化问题，解放数据可视化系统的开发人力。大屏与报表的图表数据源可以复用，用户可以方便地为同一套数据搭建不同的展示形式。实现在外网访问内网的气象站数据。本文使用MySQL模型直接拉取数据库中的数据，显示实时的环境信息和历史气象信息的折线图。

2.3系统调试及运行测试(1）运行状况：

从2019年10月8日至2020年4月30日已经稳定运行150余天，中途出现过网络断开多天的情况，但是网络恢复后，程序开始自动恢复数据，数据库的数据没有丢失，即断网期间本地存储的数据全部同步到数据库一端，说明此气象站的数据管理方案是比较可靠的。

# (2)数据量：

系统 $2 4 \mathrm { { h } } ^ { * } 7$ 运行，每天本地备份的数据量为 $5 0 0 \mathrm { K b }$ ，一年数据量约为 $1 8 0 \mathbf { M b }$ ；每天全天图像和各监测量趋势图总计1.5Mb，一年数据量约为 550Mb。每隔一年清理一次本地的备份。

(3）数据丢失率（除去停机等特殊情况）：

截至 2020 年4月底每天的数据丢失率如图8(a)，可以看到在气象站运行初期由于需要进行调试工作，整体运行状态较稳定运行期要差一点，但是仍然达到小于 $10 \%$ 数据丢失率的要求。图8(b)是4月底最后十天的运行状况，图8(c)是10月至4月的运行情况。通过统计发现此系统的数据丢失率在 $4 \%$ 附近，满足预期要求。

![](images/087099ae1300bdd3f6c7ab53c0f4b6ea32d2fb678d1d3d0817c81410d9d6b4ff.jpg)  
图8天文气象站数据数据丢失率统计图  
Fig.8Statistical chart of data loss ratio of astronomical meteorological stations

# 3．总结及未来计划

# 3.1总结:

目前的系统基本实现了预期的目标，运行稳定，满足日常使用要求。此系统在日常工作状态下功耗约为10w，在断电情况下7800mAh 的微型ups 能供电4个小时左右。同时，硬件成本只相当于同等功能PC（成本 2000元，不含显示器）的1/4左右。同时其搭载的 linux系统生态很完整，满足气象站数据处理的硬件和软件要求，又因其强大的扩展功能和便携性等特点，未来会考虑用基于ARM架构的嵌入式系统进行更多系统的开发。

3.2 未来计划

（1）采用更高性能的ARM开发板，如树莓派4b，Nano piM4v2等，提高数据处理能力，以及存储介质的访问速度；(2）采用更可靠的RS485串口服务器，获得更稳定的数据访问;(3）在高性能ARM开发板的加持下，开发集成SDIMM视宁度监测 $+$ 云量 $+ \prime$ 气象参数等下一代高性能、低功耗、低成本一体式天文环境监测系统。

# 参考文献：

[1] B Baker et al. An automatic weather station for operation in severe icing climates[J]. Phys.E: Sci. Instrum.[J],1979,12,734   
[2] D.A.Klinglesmith III, R.Alvarado,M.J. Creech-Eakman, et al. Astronomical Site Monitoring System for the Magdalena Ridge Observatory. Proceedings of SPIE[J]Vol. 5491   
[3] Stefan Sandrock, Rodrigo Amestica, Philippe Duhoux, Julio Navarrete,Marc Sarazin.VLT Astronomical Site Monitor:Control, Automation,and Data Flow. Proceedings of SPIE Vol. 4009(2000)   
[4] 王青松，高明，汪桂霞。基于DSP的小型气象站的硬件设计[J].传感器与微系 统，2010,29(7). Wang Qingsong,Gao Ming,Wang Guixia. Hardware design of small weather station based on DSP[J]. Transducer and Microsystem Technologies,2O10,29(7)   
[5] 高涛，江益。基于ARM的自动气象站数据实时显示系统[J].电子设计工程， 2019,27(4). Gao Tao, Jiang Yi. Real-time display system of automatic weather station data based on ARM[J]. Electronic Design Engineering,2O19,27(4)   
[6] 卫守林，石聪明，等.VantagePro气象站实时数据采集与在MUSER中的应用研 究[J].天文研究与技术,2016,13(1):117-123. Wei Shoulin， Shi Congming， et al. Real-time data acquisition and application research of Vantage Pro weather station in MUSER [J].Astronomical Research & Technology,2016,13(1):117-123   
[7] 王传军，范玉峰，陈东.基于TINI系统的网络气象站[J].天文研究与技术， 2007,4(3):288-295. Wang Chuanjun,Fan Yufeng,Chen Dong,A network weather station based on TINI system[J].Astronomical Research & Technology,2007,4(3):288-295   
[8] 辛玉新，王传军，范玉峰，等.丽江站台址信息监测系统[J].天文学进 展,2017,35(3):367. Xin Yuxin， Wang Chuanjun， Fan Yufeng， et al.Lijiang station information monitoring system[J]. Progress in Astronomy,2017,35(3):367   
[9] 范鹏程，曹烤，王大旺，陆建君。基于STM3自动气象站监测系统设计[J].气象 研究与应用，2018,39(2).Fan Pengcheng,Cao Kao,Wang Dawang,Lu Jianjun. Based on the monitoring system design of STM32 automatic weather station[J]. Journal Of Meleorological Research and Application,2O18,39(2)

# The Application of ARM-based Embedded System in Automatic Weather Monitoring System: NVST Weather

Station as an Example

Wang Xinhua11,²,Chen Dong1，Luo Lin',Zhang Taol，Yang Lei1, $\mathrm { { X u } } \mathrm { { Z h i } } ^ { \mathrm { { 1 } } }$ ，Chen Junyi (1.Yunnan Observations，Chinese academy of sciences，Kunming 65oo11，China

2.University of Chinese academy of sciences，1ooo49，China)

Abstract: The automatic weather monitoring system is one of the necessary auxiliary systems of modern astronomical observation stations. Traditional automatic weather monitoring system is based on microcontroller or PC development.Microcontroller is mainly used for industrial control, which cannot meet the requirements of multi-task and batch data rapid processing. Due to high power consumption,high cost and low portability,PC cannot be used in the field,such as when choosing a new site.In order to overcome the shortcomings of the above two development methods, this paper adopts an embedded system based on ARM architecture for NVST develops a low power consumption,low cost and high stability automatic weather monitoring system. This paper introduces the overall design of NVST weather station, hardware and software functions, as well as the problems and solutions.

Key Words : Automatic Weather Monitoring System ; ARM Architecture Embedded Systems ; NVST Weather Station