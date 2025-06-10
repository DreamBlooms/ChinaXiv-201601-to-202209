# 新疆天文台天文观测数据传输日志系统设计与实现

朱艳}²，张海龙,3\*，冶鑫晨，王杰ʰ，王万琼ʰ，托乎提努尔'，李嘉ʰ，张萌,2(1.中国科学院新疆天文台，新疆 乌鲁木齐830011；2.中国科学院大学，北京 100049；3.中国科学院射电天文重点实验室，江苏 南京 210008)

摘 要：新疆天文台望远镜所产生的观测数据通过数据专线传输到台本部数据中心进行长期存储。采用rSync进行数据传输，过程中没有详细的日志记录信息，无法对传输情况进行统计分析。本文通过调研新疆天文台数据传输需求，设计并开发了新疆天文台观测数据传输日志系统。系统以新疆天文台南山站、奇台站的数据存储服务器和台本部长期存储为基础，设计了日志系统的整体架构，实现了数据传输过程的日志记录。系统基于shel1多线程技术、qt框架开发了后台服务程序及日志系统软件界面，实现了日志分析、统计备份与数据传输可视化页面。

关键词：日志；数据传输；数据库；可视化中图分类号：TP391 文献标识码：A 文章编号：

# 0引言

由于天文观测的特殊性，望远镜观测台站与天文数据存储中心往往相距遥远，观测产生的科学数据需要通过专线传输到数据中心永久存储，传输的数据专线长期暴露在外会产生多种问题，导致数据传输中断。数据传输过程中需要控制系统与详细的日志系统以便及时发现问题，并在故障修复后重新传输数据，若有直观的展示和可视化管理界面，将极大方便数据管理员进行数据统计与分析。数据传输过程中的日志记录和之后对日志的分析查询是天文数据传输系统中重要组成部分，也是本文的主要内容。本文将以新疆天文台观测数据在传输过程中实际遇到的问题为基础，设计并开发了一套数据传输日志系统，实现数据查询、统计、分析等功能。

Wicenec [1[2]等人研发了NGAS④(Next Generation Archive System)，其主要目标是处理来自望远镜的大数据流，该系统很好的满足了观测设备所输出的不断增长的数据传输与管理需要。NGAS提供用户基于URL命令的接口，支持包括归档、检索、在内的几十个命令。目前，NGAS已经应用在多个数据中心的数据传输中，ALMA、MWA、FAST产生的数据已经在使用NGAS进行传输，目前上海天文台也计划使用NGAS进行数据传输。

rsync 是一款数据镜像备份工具，可实现本地主机与远程主机上的文件同步，rsync 仅传送本地与远程两个位置的数据差异部分，数据传输效率较高[3]。rsync 执行日志默认输出到syslog，支持指定同步日志文件位置和定制日志文件的具体字段。rsync 存在记录日志信息单一问题，无法满足海量天文数据传输中状态判断和问题发现，真实的天文数据传输过程需要更为详尽的日志内容。

日志可审计跟踪发生在对象上的活动，日志在软件系统中起辅助作用，在满足需求的情况下应尽量简单高效。已经存在的成熟优秀的日志系统，如Glog等，由于框架庞大导致其开销也大[4]。NGAS 与 rsync 都不支持日志多目的地输出，rsync 也不提供日志轮转功能。日志文件轮转配置、多目的输出、存储数据按天或按文件夹的统计结果写入日志文件与数据库表中等需求都是已有日志系统无法满足的。

# 1天文数据传输日志系统设计

新疆天文台在南山建有26m射电望远镜，天文台本部位于南山观测站以北约100KM。望远镜观测得到的原始数据经专线传输到台本部进行异地备份[5]，本日志系统以rsync软件工具为基础实现。

1.1日志系统整体架构

![](images/51db1c88d25c7a98a9e0e670664b14816ab909fc8e08b5231bfef7b2cd9d4b72.jpg)  
图1日志系统结构图Fig.1 Log system structure

如图1所示，日志系统包括日志收集、存储、日志检索几个部分。通过日志收集器进行日志的收集，收集器对本机上观测数据存储目录定时扫描并进行处理，并根据配置文件中的数值选择扫描的间隔时间。存储服务进程接收到收集器的输出信息后存储为数据库表内容同时存入日志文件。日志检索系统根据管理员检索条件显示日志信息，控制后台服务程序（服务的启动、关闭、重启等），修改配置文件。

# 1.2关键点

图2为日志系统后台程序实现细节图。

监控脚本：执行监控任务的脚本，共有两个监控脚本，彼此监控。

控制脚本：根据配置文件内容，控制各个脚本的输入参数，如脚本内容的循环间隔等。

监控对象：检查更新和数据写入两部分组成。检查更新脚本通过检测发送接收两端数据对比来确定是否需要同步数据备份，该脚本只存在接收端日志系统中。数据写入由文件信息数据和统计信息数据组成。文件信息写入脚本记录最新一次存储目录扫描后新增的文件信息，统计信息脚本负责统计存储根目录与其下的各个文件夹以及每日增量信息。

![](images/c6ec7855b4d2fbf50a1c37bf6fe0b69f373a0ce57ae9ccc4fbdea6cc2b3f5d4f.jpg)  
图2实现细节图Fig.2 Implementation details

# 1.2.1互相监控体系

shel1脚本在linux系统运行中可能会非正常退出或异常结束，日志系统必须时时监测保证整套系统正常运行。监控脚本1、监控脚本2、监控对象组成了一个牢固的互相监控体系。监控脚本1与监控脚本2彼此互相监控，监控对象同时被两个监控脚本监控。监控脚本主要任务是检查脚本进程的运行状态，脚本一旦不在进程列表中会被立刻唤醒。这样的监控体系可以保证监控对象一直处在运行状态，保证日志系统在无人值守的情况下能够长时间稳定运行。

# 1.2.21inux 实现

控制脚本需要同时运行多个脚本，就需要启动多个后台进程，系统采用在执行脚本命令后加&操作符来实现多线程，即：

./script_name.sh &

加&操作符会对SIGINT信号免疫，表示该条命令将在子shel1中执行，但该条命令所在终端被关闭，进程也会被关闭。实现真正后台执行应在语句前面加上nohup，对SIGHUP信号免疫，即：nohup./script_name.sh &

监控对象包含多个脚本，通过she11的多线程技术实现一个控制脚本启动多个脚本。监控对象内脚本若停止运行将被控制脚本唤醒。

# 2系统实现

2.1开发语言简介

新疆天文台数据传输日志系统的后台程序由she11脚本组成，日志检索系统由Qt语言在集成环境Qt Creator内完成。

Shell是用户使用Linux系统的桥梁，接收用户键入的命令并送入内核去执行。shel1脚本就是用shel1命令组成的程序，shel1作为一种编程语言，也有分支控制结构和循环结构等普通编程语言所具有的特点，在Linux上统计信息使用命令组合可以方便得到统计结果。

Qt是一个跨平台 $\mathrm { C } { + } { + }$ 图形用户界面应用程序开发框架，Qt语言模块化程度高且可重用性较好，Qt简化了开发和维护图形用户应用程序的任务6，内部的组件通过Qt特有的信号槽机制通信。

# 2.2日志文件结构

数据传输日志系统的日志包括两部分，一部分是记录数据存储在本地机器上的处理后的统计日志，称为普通日志，这种日志以文件形式存储在以日期命名的log文件中，有数据存入就会产生新日志文件；另一部分则是使用日志检索系统产生的如登录、退出系统记录，界面操作的相关日志，记录用户行为轨迹，称为系统日志，这类日志的命名规则由配置文件决定，配置文件中日志文件轮转提供大小和时间两个选项。另外普通日志中的某些信息需要写入数据库表中。

# （1）普通日志

普通日志写入文本文件，同时也会将某些字段写入数据库表中，其输出格式如下：

[<Timestamp>] [<log type>] <folder path> <file number> <data volume><last modify time>-e.g.:  
[2018-06-0419:28:22][INFO] /data/2014/201401 1871493.342018-04-13 13:30:25字段意义对应如下：

<timestamp>表示日志记录日期和时间，<logtype>代表日志等级,可取“INFO”，"WARNING”,"ERROR","NOTICE”，<folder path>表示数据存储路径下的各文件夹绝对路径，<filenumber>表示该文件夹下文件个数，<datavolume>表示该文件夹下文件总量（单位为MB），<lastmodifytime>表示该文件夹最后修改时间。

（2）系统日志

系统日志以文本形式写入文件，其输出格式如下：<type>|<timestamp>|<user>|<operation>|<source file>|<log type> $\ O =$ Klogmessage>,<status>e.g.:SYSTEM_LOGIN|2018-06-20 18:23:21|samllogonlogindialog.cpp|INFO=log into system,SUCCEED字段含义如下：

<type>表示日志类型，登陆日志或者是操作日志，<timestamp>表示日志记录时间，<user>表示管理员姓名，<operation>表示操作，<source file>表示源文件，<logtype>表示日志等级，<logmessage>表示日志说明字符串，<status>表示操作状态

# 2.3数据库表

1）文件表（files)：记录每个文件的文件名、文件大小、文件存储时间、文件最后修改时间、文件的md5值  
2）天文数据表（data)：记录设备上天文数据的存储信息，包括数据总量(单位MB)、存储路径内数据总个数、存储时间与最后修改时间。（用户可以设置记录数据的间隔时间，如2分钟）  
3）文件夹表（folder)：记录存储路径根目录下的各文件夹的数据信息，包括自增字段、文件夹遍历次数、文件夹名称、该文件夹下存储的总数据量、该文件夹包括的数据文件总个数、文件夹记录时间、文件夹最后修改时间、根目录下文件夹总个数  
4）每日数据增量表(dayData)：记录每日天文数据存储路径下数据的变化信息，包括自增字段、当日日期、当日增加的数据总量、当日增加的文件总个数、备用字段  
5）每日文件夹数据增量表（dayFolderData)：记录天文数据存储路径根目录下各文件夹每天数据变化信息，包括自增编号字段、当日日期、文件夹名称、该文件夹存储数据总量、该文件夹下存储文件总个数、该文件夹当日增加的数据总量、该文件夹下当日增加的文件总个数、根目录下文件夹总个数  
6）脚本程序监控表（proc_status)：记录后台脚本程序的运行状态，四个脚本分别为写数据脚本、控制脚本、每日数据统计脚本、rsync 数据传输脚本，更新时间。

# 表1数据库表结构

Tab.1 database table structure   

<html><body><table><tr><td>表名</td><td>字段名</td><td>字段类型</td><td>字段描述</td></tr><tr><td rowspan="5">files</td><td>File_name</td><td>char</td><td>文件名</td></tr><tr><td>File_size</td><td>int</td><td>文件大小</td></tr><tr><td>storeDBtime</td><td>timestamp</td><td>文件存储时间</td></tr><tr><td>File_time_last</td><td>timestamp</td><td>文件最后修改时间</td></tr><tr><td>Md5value</td><td>char</td><td>文件md5 校验值</td></tr><tr><td rowspan="5"></td><td>data_no</td><td>int</td><td>自增字段</td></tr><tr><td>data_volume</td><td>double</td><td>存储数据总量</td></tr><tr><td>data_number</td><td>int</td><td>存储文件总个数</td></tr><tr><td>data_time</td><td>timestamp</td><td>写入数据库时间</td></tr><tr><td>data_time_last</td><td>timestamp</td><td>最后修改时间</td></tr><tr><td rowspan="7">folder</td><td>data_add auto_no</td><td>char int</td><td>备用字段 自增字段</td></tr><tr><td>folder_no</td><td>int</td><td>文件夹编号</td></tr><tr><td>foldet_cycle_no</td><td>int</td><td>文件夹被访问次数</td></tr><tr><td>folder_name</td><td>Char</td><td>文件夹名</td></tr><tr><td>folder_volume</td><td>Double</td><td>文件夹数据量</td></tr><tr><td>folder_number</td><td>Int</td><td>文件夹下文件总个数</td></tr><tr><td>folder_time</td><td>Timestamp</td><td>写入数据库时间</td></tr><tr><td rowspan="7"></td><td>folder_time_last</td><td>timestamp</td><td>文件夹最后修改时间</td></tr><tr><td>folder_add</td><td>char</td><td>备用字段</td></tr><tr><td>auto_no</td><td>int</td><td>自增字段</td></tr><tr><td>dayDate</td><td>date</td><td>当日日期</td></tr><tr><td>data_volume</td><td>double</td><td>历史数据总量</td></tr><tr><td>data_number</td><td>int</td><td>历史文件总个数</td></tr><tr><td>incre_volume incre_number</td><td>double</td><td>当日数据增加量</td></tr><tr><td rowspan="7"></td><td>dayData_add</td><td>int char</td><td>当日文件个数增加量 备用字段</td></tr><tr><td>auto_no</td><td>int</td><td>自增字段</td></tr><tr><td>dayDate</td><td>date</td><td>当日日期</td></tr><tr><td>folder_name</td><td>char</td><td></td></tr><tr><td>folder_volume</td><td>double</td><td>文件夹名 文件夹下数据总量</td></tr><tr><td>folder_number</td><td>int</td><td>文件夹下文件个数</td></tr><tr><td>incre_volume</td><td>double</td><td>文件夹下当日数据增加量</td></tr><tr><td rowspan="6"></td><td>incre_number</td><td>int</td><td>文件夹下当日文件个数增加量</td></tr><tr><td>dayFolderData_add</td><td>char</td><td>备用字段</td></tr><tr><td>auto_no</td><td>int</td><td>自增字段</td></tr><tr><td>writeData</td><td>tinyint</td><td>脚本 writeData</td></tr><tr><td>control</td><td>tinyint</td><td>脚本control</td></tr><tr><td>oneDayStat</td><td>tinyint</td><td>脚本 oneDayStat</td></tr><tr><td rowspan="2"></td><td>rsync</td><td>tinyint</td><td>脚本 rsync</td></tr><tr><td>update_time</td><td>timestamp</td><td>更新日期</td></tr></table></body></html>

# 3日志检索系统实现

日志检索系统主要为系统管理员所服务，通过一个友好的操作界面让使用者更加方便的查询和操作日志，为了便于控制整套天文数据传输日志系统，通过界面控制后台运行程序开启、停止或重启，更改配置文件参数达到控制日志输出行为的目的。

# 3.1功能结构

![](images/928fe30e4dc396a6dddc15e0d077c679c0e13afbb98b3cf3d931a83cbf3d35fc.jpg)  
图3日志检索系统结构Fig.3 structure of log retrieval system

如图3所示，日志检索系统有四部分功能组成，分别为普通日志检索、分类日志查询、日志备份、参数管理控制。

# 3.2各功能子模块描述

如图4所示，用户成功登录后页面显示发送端和接收端存储数据情况，包括两端的系统状态和各自存储的总文件量、总文件数。系统状态列出磁盘设备已占用空间大小、占用比例、可用空间等信息。

![](images/1c6896e4f8389afd154a81b128d25104db09cb342b5c08ee67914ab3a2b54889.jpg)  
图4发送端与接收端数据存储情况一览  
Fig.4 Summary of data storage at the sender and receiver

3.2.1普通日志检索（Log Retrievel)

AstronomyData TransmissionLogSystem File(E) Help BackService Q Log Retrieval sending server accepting server zhuyan system Log 茶 Configure Condition 2018-08-01 00:00:00 2018-08-05 00:00:00 keyword: search Backup file_name file_size generate_time ^ 130119_204249_ON 3558400 3 Aug 2018 14:03:51 三 1 2 130119_195522_OF 3558400 3 Aug 2018 14:03:33 3 130119_111326_OF 3558400 3 Aug 2018 14:03:37 4 130119_094320_OF 3558400 3 Aug 2018 14:03:47 5 130119_215747_ON 3558400 3 Aug 2018 14:03:52 6 130119_134029_ON 2375680 3 Aug 2018 14:03:43 7 130119_172916_OF 3558400 3 Aug 2018 14:03:44 8 130119_174013_ON 3558400 3 Aug 2018 14:03:56 9 130119_100549_OF 3558400 3 Aug 2018 14:03:53 10 130119_203910_OF 3558400 3 Aug 2018 14:03:47 11 130119_120634_ON 3558400 3 Aug 2018 14:03:43 12 130119_150252_OF 3558400 3 Aug 2018 14:03:57 13 130119_163040_OF 3558400 3 Aug 2018 14:03:44 14 130119_142955_ON 3558400 3 Aug 2018 14:03:39 √ welcome zhuyan

如图5所示，普通日志检索界面展示详细的文件记录，包括文件名、文件大小、文件生成时间。支持检索某一段存储时间内的记录，时间可精确到某一天的某一秒，支持关键字检索。关键字是文件名或者文件名的一部分，顶部可选择sender或者receiver按钮检索发送端或接收端的数据。底部的backup按钮支持备份当前检索的数据到本地默认目录,备份目录在Configure页中修改。

# 3.2.2 分类日志查询（System Log）

此界面分类显示系统日志内容，系统日志是指用户使用日志检索系统所产生的一系列日志信息。系统日志可查看系统登录日志与系统操作日志两类。

![](images/8e0b3b85b7231f726631430a43ff6a846a487495cbaa83cdaafa364ed4de0276.jpg)  
图5普通日志文件检索  
Fig.5 ordinary Log file retrieval   
图6日志概览  
Fig.6 log overview   
图7不同类型日志查询 (登录日志)  
Fig.7 different types of log queries(logging log)   
Fig.8 different types of log queries (operation log)

$\textcircled { 9 }$ zhuyan System Log Configure login log number:1110 login log □ C Backup T01806201:44:343SCTU Action Desniptiontem A

Q Log Retrieval O zhuyan   
具 System Log   
configure operate log number:185 operation log LEVEL L TIME STATUS Operation Description D Backup INFO 2018-07-10 13:08:19.758 SUCCEED categoryChoose selected item System Log 图8不同类型日志查询 (操作日志)

图6展示了系统日志概览，包括日志分类和各自的数量。如图7所示，系统登录日志记录每个用户登入或登出系统的时间，登录状态，动作（登入或登出）以及相关描述。如图8所示，系统的操作日志详细记录了用户使用本系统的行为轨迹，给出了用户操作的时间，操作的内容（如查询操作、备份操作等），操作的状态（成功或失败），操作的详细描述。

3.2.3参数管理控制（Configure）此界面可以控制后台服务的启动，关闭，重启，对参数进行设置。

![](images/b502c805359c807bbee3bb82eb7c8e06501b9f23f2344b00da04e7a833eec14f.jpg)  
Fig.9 system configuration

图9系统配置界面，自动显示已有的参数及参数内容：

OrdinaryLogBackupDir：普通日志远程备份到本地的默认路径SystemLogBackupDir：系统日志备份默认路径

OrdinaryLogMaxSize：普通日志单个文件最大值，默认值为5MB，若单个日志文件超过设定的最大值则将日志写入另一新文件中。

OrdinaryLogInterval：写入日志文件的间隔时间，也就是后台程序扫描根目录的间隔时间，默认间隔2分钟。

MonitorInterval：后台程序监控的时间间隔，即检测后台各shell程序的运行状态的间隔时间，默认间隔5分钟。

界面中的三个checkbox的设置分别对应OrdinaryLogMaxSize、OrdinaryLogInterval、MonitorInterval，更改设置后需点击restart（重启）按钮重启后台服务程序。Start与stop按钮表示后台服务的开启和停止。

# 3.2.4日志备份（Backup）

此界面分为普通日志备份和系统日志备份两种，普通日志备份支持数据发送服务器或接受服务器上的日志备份，系统日志备份支持软件界面的日志备份。

![](images/e95dc23cebb6ca4624dee449c08b20d8ab2e24b0b8650d357e74c4e4c055be02.jpg)  
图10日志备份Fig.10 log backup

如图10所示，系统日志文件备份可备份今天以前、半年前、一年前的本地日志，默认配置页面的备份路径；普通日志备份支持用户选择的起始日期内的日志文件，包括按每个文件、每个文件夹、存储路径根目录每日变化的所有日志的压缩打包下载，默认配置页面中的备份路径。

# 4、数据传输可视化

在日志系统的基础上，通过html5、AJAX、PHP等web相关技术建立了数据传输可视化页面，如图12所示。可视化页面上可显示传输系统工作情况，便于系统管理员及相关人员了解数据传输情况。可视化页面分为6个部分：第一部分，通过柱状统计图显示出当日的数据存入和发送情况；第二部分，通过柱状统计图显示出过去一周的数据情况；第三部分，通过调用后台服务器的心跳数据，显示出发送服务器与接受服务器的状态，一但出现异常会通过警报程序自动发送提醒；第四部分，通过饼状图显示出服务器的存储情况，管理人员可通过直观的显示判断是否需要增加存储设备；第五部分，通过调用日志记录，显示正在进行的传输情况；第六部分，通过曲线图，显示过去一小时的数据传输速率。

Today's data transmission   
![](images/1c1ebea866a5c9c7c1aaf893dff00eeddb8dc91fe8e483a06930fddcfb6a9f9c.jpg)  
Networkconnection.

The amount ofdats produded(GB) The amount ofdats trans ferred(GB)   
180   
160 山山   
140   
120   
100 880 40   
20 0 05-16 05-17 05-18 05-19 05-20 05-21 05-22 ②

# Data situation of sending'server

Communication time $\cdot$ 2018-05-23 12:03:27   
Data-sencling server connection status :   
[normal]   
Data-accepting server connection status :   
[normal]   
Communication time : 2018-05-23 12:01:27   
Data-sending server connection status :   
[normal]   
Data-accepting server connection status :   
[normal]   
Communication time : 2018-05-23 11:59:27   
Data-sending server connection status :   
[normal]   
Data-accepting server connection status :   
[normal]

![](images/320374d84da8573e4039be25a6ff6ffc5e288c8220985f9e6406c9c79977baa9.jpg)

# Data transmission performance

Transferred file name:   
/2016/20160311/   
160311_032311_ON.rpf   
6.87MB/s   
61%   
Transferred file name:   
/2016/20160311/   
160311_032316_OF.rpf   
3.54MB/s   
100%

Rsync tool is running.

![](images/1219c9a5b816693bd211c82cb76bc8e8e31a3659c38a3c5653658699663d489c.jpg)  
Data situation of acceptinig server   
Using $\because$ 264159MB total space $\because$ 4718592MB Total File5 : 44785个 2018-05-23 12:06:17   
Using $\because$ 240817MB total space $\because$ 2097152MB Total File : 39542个 2018-05-23 12:05:09

![](images/5fb36887236f93796ab524b2b2da5326a49bee9d41cec932d76cd84fb89f3518.jpg)  
Data transmission in the past seven days   
Data transfer rate for the'past hour

![](images/f9d4bfef6b2b466c96c874bb09cb089282f28b66e09a55c678fe39673f6be6e8.jpg)  
图11可视化界面  
Fig.11 Visualization page

可视化系统将数据传输的日志内容较为直观的显示出来，为系统管理员提供了极大的便捷，可辅助判断系统的运行情况，及时发现系统存在的问题。可视化页面采用模块化开发技术，将来可以嵌入到大型观测装置的中控系统当中。

# 5总结

根据新疆天文台数据传输的实际需求，构建了日志收集-存储服务-日志检索的日志系统架构，在数据发送服务器与接收服务器上都搭建了日志系统的后台服务程序。创新提出了脚本程序间互监控系统，完成了数据传输中对文件信息、文件md5校验值记录的普通日志，与按天按存储数据文件夹记录的统计日志。另外，在数据接受服务器端的系统具有自动检测数据更新功能。

日志检索系统作为客户端软件安装在第三方设备上，软件读取配置文件信息，自动连接数据发送服务器端与数据接收服务器端数据库。实现了按时间、关键字检索两端远程服务器日志信息，备份由检索结果组成的日志信息。查看软件本地产生的登录、操作等不同类别日志，压缩备份本地日志。实现了对服务器两端配置文件参数修改，提供用户对服务器两端系统的启动、停止、重启功能。

实现了数据传输的可视化，通过WEB形式显示日志内容，可以辅助系统管理员了解传输系统的运行状态，采用模块化开发技术，便于后期的移植和复用。

# 参考文献：

[1] Wicenec A，Knudstrup J，Johnston S.ESO's Next Generation Archive System[J]． Messenger，2002,129:27-31   
[2]Wicenec，A.；Knudstrup，J.ESO's NextGeneration Archive SysteminFullOperation[J].Messenger,2007,129:27-31   
[3]左珍德．基于Rsync的结构化数据库实时高速备份研究及工具开发[D].华南理工大学,2017. Zuo Zhende,Research and Tool Development of Real-time High-speed Backup for Structured Database Based on Rsync [D].South China University of Technology,2017.   
[4]杨善宁.一个轻量高效跨平台日志系统的设计与实现[J].电脑知识与技术,2017,13(28):77-78+115. Yang Shanning,The Designand Implementation of a Lightweight and High-efficient Cross-platform Loging System[J].Computer Knowledge and Technology,2017,13(28):77-78+115.   
[5] 张海龙,朱艳,聂俊,袁建平,吴刚,刘俊，王杰，王万琼,冶鑫晨,托乎提努尔,张萌.新疆天文台NSRT观测数据存储系统[J].天文研究 与技术,2018,15(02):181-187. Zhang Hailong,Zhu Yan,Nie Jun,Yuan Jianping,WuGang,Liu Jun,Wang Jie,Wang Wanqiong,Ye Xinchen,Tohtonur,Zhang Meng.Xinjiang Astronomical Observatory NSRT Data Storage System[J].Astronomical Research & Technology,2018,15(02) :181-187.   
[6] Rischpater R. Application Development with Qt Creator[J]．2014.   
[7]Blanchette J，Summerfield M. $\mathrm { C } { + } { + }$ GUI Programming with Qt 4[J].2006，45(6):747 - 749.

# Design and implementation of Xinjiang Astronomical Observatory Observation data transmission log system

Zhu Yan’²， Zhang Hailong1,,Ye Xinchen', Wang Jie'，Wang Wanqiong'，Tohtonur'，Li Jia’, Zhang Meng1,²   
(1.XinjiagAstroocalObseatoryCsecdeyfieesUioina;2Uivesityofseademf, Beijing 0oo49,China；3.KeyLaboratoryof RadioAstronomy,Chinese Academyof Sciences,Nanjing 21008,China)

Abstract: The observation data generated by Xinjiang Astronomical Observatory(XAO） telescope was transmitted to the data center at XAO headquarters for long-term storage through the dedicated transfer line. Statistical analysis cannot be performed due to the lack of detailed log records during transmission using rsync. The data transmisson log system of XAO was designed and developed on the basis of fully investigating the data transmission demand. Based on the data storage server of Nanshan Station, Qitai Station and the long-term storage server at the XAO headquarters,the overall architecture of log system was designed and the logging of the data transmission process was realized. The shell multi-threading technology and qt framework were adopted to develop the back-end service program and system software interface which realized log analysis,data statistics,log backups and data transfer visualization page.

Keywords: Log;Data Transmission; Database; Visualization