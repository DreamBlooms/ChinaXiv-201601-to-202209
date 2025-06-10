# 基于Web.py的MUSER软件系统界面实现

蔡能健¹，刘东浩²，邓辉¹，卫守林1,，王锋1,3， 梅盈1,3，戴伟1,，刘应波4，吴静平5

（1.昆明理工大学云南省计算机技术应用重点实验室，云南 昆明650500；2.中国科学院国家天文台，北京100012；3.中国科学院云南天文台，云南 昆明650011；4.云南省科学技术情报研究院，云南 昆明650051；5.云南省信息技术发展中心，云南 昆明650034)

摘要：明安图射电频谱日像仪（Mingantu Ultrawide SpEctral Radioheliograph，MUSER）已经完成硬件建设，与之配套的数据处理系统也初步开发完成。为提高用户操作的可用性，简化操作难度，数据处理系统在提供传统的命令行用户界面的同时，也提供了网络交互方式。简单介绍了Web.py的基本概念和内部组件交互流程，讨论了基于Web.py 进行网络开发的方法和流程，并利用Web.py框架实现了数据处理系统的网络界面交互。成果已经应用，提高了日像仪数据处理系统的可用性，也为其它天文软件系统的开发提供了一定的借鉴与参考价值。

关键词：天文软件系统；Web.py；用户界面中图分类号：TP311.1 文献标识码：A 文章编号：1672-7673(2017)02-0229-07

为推动国内太阳射电天文观测技术的发展，我国天文学家提出建设的明安图射电频谱日像仪已经全面建成[1]。该设备可以在厘米-分米波段对太阳同时进行高空间、高时间和高频率观测，观测所得数据可以更好地研究太阳活动。项目分两期建设，第1期是MUSER-I低频阵 $( 0 . 4 { \sim } 2 \ \mathrm { G H z } )$ ，由40个$4 . 5 \mathrm { m }$ 的天线组成，在64个频率上成像；第2期MUSER-II高频阵( $( 2 \sim 1 5 ~ \mathrm { G H z } )$ ），由60面 $2 \mathrm { m }$ 的天线组成，在528个频率上成像。

明安图射电频谱日像仪的数据处理系统是整个项目的关键组成部分，设计并实现快速、可靠、方便的数据处理软件已成为发挥望远镜作用的重要支撑。当前基于浏览器/服务器(B/S)模式开发网络应用软件已经成为软件开发的主流，一方面，这一类软件具有高移植性的特点；另一方面，网络应用软件无需部署，对后期维护非常有利。从长远建设来看，实现一个具有友好人机交互的网络界面，集成相应的数据处理程序，满足现场观测以及远程数据处理的要求是非常必要的。

开发网络应用可用的技术很多，最为常见的是基于J2EE或者.NET技术，分别采用Java与C#语言开发。一般来说，这一类软件存在部署运行环境复杂、开发周期较长等不足。近年来，天文软件开发大多采用Python语言，明安图射电频谱日像仪的数据处理系统也是基于Python开发完成。为了更好地和数据处理系统集成和交互，明安图射电频谱日像仪的网络用户界面同样采用Python 语言开发。本文首先介绍了数据处理系统的架构及操作界面的功能，接着讨论了轻量级网络框架Web.py 的内部组件交互流程，重点讨论了使用Python 语言和Web.py 进行快速开发的方法，以及如何利用 Web.py框架实现网络界面与功能封装。

# 1明安图射电频谱日像仪数据处理系统

随着望远镜性能的显著提升，产生的数据成倍增长，处理过程日趋复杂，计算机软件系统已成为天文数据处理中不可或缺的工具。天文软件系统可以分为数据处理和数据发布两大类。数据处理软件一般部署于本地，采用单机或计算机集群方式完成观测数据的处理，包括最为常见的IDL、CASA、AIPS 等。数据发布软件一般基于网络应用和表述性状态传递（Representational State Transfer，REST）风格的网络服务发布技术，如虚拟天文台中的锥形检索等。

在明安图射电频谱日像仪的日常数据处理中，包含了两方面的需求，一是对历史数据的处理，另外一个是每5秒钟的采样观测数据的实时处理。为了满足高速数据处理的需求，开发和实现了一套部署于明安图观测站的高性能计算系统[2]。同时为了天文学家离线处理的需要，开发了一套可运行在单机上的客户端软件，实现与CASA类似的功能。日像仪软件系统整体功能结构如图1，主要包括3部分，分别用于核心数据处理、用于交互的用户界面以及数据库。核心数据处理模块采用Opencluster[3]框架，支持分布式任务调度。核心的底层数据获取、数据处理（包括CLEAN、FFT、IFFT等）、数据存储（UVFITS 等)等功能已经基于Python开发完成[4-5]，并通过Opencluster 实现整个计算资源的分配和调度。软件系统采用MySQL数据库存储数据处理中的若干关键参数，如光纤传输时延、气象数据等[6],同时为了提高查询速度，也支持将数据导出到Redis内存数据库。用户界面主要实现数据处理任务提交、天线状态维护、自动气象站和卫星数据修正配置等功能。

目前，明安图射电频谱日像仪已经实现了与CASA操作类似的命令行(CLI)接口[7]，但命令行方式存在命令多、表现方式不直观等不足。为了进一步提高数据处理系统的使用效率，使用Web.py开发了更为友好的数据处理系统交互界面。

![](images/be6aa84c4284925cb747882c3a7d5fc4a60cd1a255b3874074e0905e99137b0f.jpg)  
图1明安图射电频谱日像仪数据处理系统结构图  
Fig.1The structure chart of MUSER data processing system

# 2Web.py 框架分析

Web.py[8]是一个纯Python 实现的轻量级网络应用开发框架，支持模型-视图-控制器（Model ViewController，MVC)模式开发，可通过简单的编程将普通的Python 类映射为请求处理对象，原生支持编写 REST架构风格的网络服务，当前的版本是0.38。Web.py 提供了最小化的网络服务器，可以作为一个独立的守护进程运行，或者借助于网络服务器网关接口（Web Server Gateway Interface，WSGI)在任何兼容它的服务器上运行。

Web.py 不依赖于其他第三方Python 库，可以下载官方的二进制包(http://webpy.org/static/web.py-0.38.tar.gz），解压缩后执行 python setup.py install命令进行安装，也可以通过 easy_install或pip方式安装。

Web.py 框架执行过程主要在 application.py、wsgi.py、htpserver.py 和 wsgiserver 目录的模块初始化文件_init_.py这4个文件中定义。application.py是一个网络应用运行的入口；wsgi.py 是将网络应用运行在内置的简单的网络服务器，或者兼容 WSGI标准的服务器（如FastCGI)；htpserver.py 是内置的网络服务器，符合WSGI规范；wsgiserver 目录中的_init_-py文件负责创建服务器，接收客户端请求，并响应请求。从浏览器访问开始，Web.py 的内部执行流程如图2。

![](images/756dc1250780bf507b8d1c7a2eabeccf5348ca99316f97273fc80ae013e84b89.jpg)  
图2Web.py 组件图  
Fig.2The component diagram of Web.py

Web.py 中网络应用在构建时，需传人统一资源定位符（Uniform Resource Locator，URL），它是访问当前网络应用的相对路径和负责处理该路径请求的Python类的一个二元组的集合。每当浏览器发出新的请求，Web.py将请求的路径和URLs中路径做匹配，最终将请求代理到定义的Python 类中相应的方法执行。应用启动时，在wsgi.py 文件中根据环境变量配置不同，分别启动不同的WSGI处理器（FastCGI、flup、内置简单网络服务器）。启动内置网络服务器时，首先调用 htpserver.py 中的runsimple方法，runsimple方法再调用WSGIServer方法，WSGIServer 中创建使用了CherryPy的基于线程池的WSGI服务器，其类的定义为CherryPyWSGIServer。

CherryPyWSGIServer的构造函数中，执行初始化线程池、WSGI网关等操作。启动服务器时执行CherryPyWSGIServer 的基类 HTTPServer 中的 start方法，在指定地址和端口监听客户端请求，具体的请求处理，由执行请求任务的WorkerThread线程处理。

# 3交互界面设计

数据处理系统用户界面需要实现天线状态、天线位置、气象条件、光纤延迟等数据维护及数据处理任务提交等功能。本节重点介绍使用Web.py开发过程中几个关键技术。

# 3.1 URL设计与处理

就一个网络应用而言，URL的组织是最重要的部分，良好的URL设计能清晰地表达整个网络应用软件的控制思路。Web.py中URL 的定义支持RESTful的格式，RESTful的 URL具有结构清晰、符合标准、易于理解、扩展方便等优点，因此网络交互界面的URL也使用RESTful设计。

REST中包含了两个重要概念，一是资源，二是状态转移。资源代表了操作对象，通常是名词，命名方式一般和数据库的表名对应。表1列出了网络交互界面的部分类和资源的对应关系。状态转移代表了对资源的操作导致资源的状态发生变化，具体到HTTP协议中就是4个表示操作方式的动词：GET，POST，PUT和 DELETE，正好对应到增、删、查、找（Create，Read，Update，Delete，CURD）4 种数据操作。在Web.py 框架实现GET，POST，PUT，DELETE 方法，只需要在相应的处理类中定义同名的函数即可。系统主要用到GET和POST两种请求，GET请求用于获取数据，POST请求主要用于插人或者修改数据时提交新的表单请求。

Table 1Mappings of classes to resourcesin MUSER web design   

<html><body><table><tr><td>URL</td><td>Python类</td><td>说明</td></tr><tr><td>/</td><td>Index</td><td>首页</td></tr><tr><td>/antenna</td><td>Antenna</td><td>天线</td></tr><tr><td>/antenna/position</td><td>AntennaPosition</td><td>天线位置</td></tr><tr><td>/antenna/flag</td><td>AntennaFlag</td><td>天线状态</td></tr><tr><td>/antenna/delay</td><td>AntennaDelay</td><td>光纤延迟</td></tr><tr><td>/parameter</td><td>Parameter</td><td>系统参数</td></tr><tr><td>/job</td><td>Job</td><td>计算任务</td></tr></table></body></html>

Web.py 的 URL控制模式简单、灵活。网络应用启动时，需要将所有URL 和Python类的映射关系统一定义在一个元组列表中，元组的格式为：（“URL相对路径”，“处理类”），例如表1中对天线的操作，使用的路径是“/antenna”，处理类是“Antenna”，则元组的定义为（“/antenna”，“Antenna”）。

此外，Web.py 提供了强大的正则表达式设计更灵活的URL 路径，例如查询一个计算任务状态的URL可以定义为 ${ ^ { \ast } } / \mathrm { j o b } \mathrm { / } ( . + )$ ”，在/job/后面的内容会被捕捉，然后作为参数被用在GET或POST方法中。假设一个计算任务ID为10，可以使用“/job/10”查询其执行状态。“/job/10”能成功匹配“/$\mathrm { j o b / ( . + ) } ^ { \prime }$ ”，在具体查询的处理类中可以获得这个计算任务ID，再执行具体的查询，并返回结果。

# 3.2数据库操作

Web.py 支持多种数据库操作。Web.py封装了各种数据库的操作，支持事务，提供了简单易用的应用程序编程接口，如表2。具体和数据库的底层操作需要借助于相应数据库操作模块，如 MySQL的Python 库 MySQLdb，SQLServer的Python库pymssql。Web.py 的数据库部分的相关代码在db.py文件中，入口函数是database（）。根据dbn(数据库名)从dict 里查找对应类型数据库的实现类，再用其余参数初始化这个数据库实现类，返回具体的数据库操作对象，使用这个对象实现对数据库表执行增、删、改、查的操作。

表1网络交互界面的类和资源的对应关系  
表2Web.py数据库操作方法  
Table 2Methods of database operations in Web.py   

<html><body><table><tr><td>方法</td><td>功能</td><td>实例</td></tr><tr><td>insert</td><td>新增</td><td>db.insert（self，表名，变量1，变量2，）</td></tr><tr><td>query</td><td>查询</td><td>db.query（self，表名，变量1，变量2，…)</td></tr><tr><td>update</td><td>更新</td><td>db.update（self，表名，变量1，变量2，)</td></tr><tr><td>delete</td><td>删除</td><td>db.delete（self，表名，变量1，变量2，…）</td></tr></table></body></html>

数据处理系统用到了MySQL 和 Sqlite 数据库，以及 Redis 内存存储。其中 MySQL作为主数据库支持读写操作，Sqlite 在单机版处理系统使用，Redis 主要在分布式环境中使用。系统定时将 MySQL的数据导出到 Sqlite 和 Redis，Sqlite 和 Redis 在数据处理系统中提供只读操作，以保障数据的一致性。Redis 是一个基于内存键值存储系统，支持高速高并发的读写操作，为明安图射电频谱日像仪的分布式处理环境气象、天线相关参数的高速访问提供了保障。Redis不是关系型数据库，它的访问和操作需要使用Python 的 redis 库。

# 3.3 模板渲染

网络框架都提供模板技术实现复杂的网络页面，Web.py 也不例外。Web.py 的模板功能实现的源码在 template.py 文件中。Web.py 的模板语言使得可以在模板文件 HTML 中使用Python 语言的强大功能，每一个HTML文件必须在第1行通过 $\mathfrak { s }$ def with()定义在该文件中用到的所有变量，这些变量名需要和Python 中返回模板文件的变量命名一致，在HTML 中就可以直接使用这些变量。

Web．py 模板的强大之处除了引用Python中变量，还支持流程控制，语法与Python 类似。控制结构语句前面需要加上“ $\mathfrak { s }$ ”，可以实现 for、while、if、elif 和else 等语句。如明安图射电频谱日像仪中的任务处理列表的部分模板如下：

$\mathfrak { s }$ for job in jobs://jobs为任务列表变量 $\mathfrak { s }$ job.status//输出单个任务的状态

Web.py 的模板支持在Python 中Render 渲染模板文件，也可以直接渲染HTML的字符串。如显示气象数据列表，需要匹配weather.html模板，使用如图3的代码。

![](images/f2977923c42f584d2d7ba8108e2c3e333409f1f37a9944c861685d6b2053ef23.jpg)  
图3Web.py模板渲染说明  
Fig.3Specification of template-rendering in Web.py

明安图射电频谱日像仪中使用一个专门的模板文件夹 templates，存放所有的模板文件。响应客户端请求时，Web.py从模板目录寻找模板文件，匹配相应的模板文件后，渲染这个模板文件并返回浏览器。Web.py支持模板嵌套，可以使用base 指定母模板。

# 4系统界面

基于Web.py开发的数据处理系统用户界面已基本开发完成并应用到实际数据处理中，前端使用Bootstrap 构建了响应式页面，系统界面如图4。系统实现了在命令行界面配置系统参数，为多方面数据（原始数据、异常天线信息、仪器状态、天气)的录入、维护、查询和使用提供了方便，确保了后续数据处理的有效性和可靠性。同时，网络界面提供的数据处理参数的配置，方便了复杂任务的提交，与命令行界面相比，具有更好的交互性和可用性。

# 5结束语

本文介绍了基于Web.py框架进行明安图射电频谱日像仪数据处理系统用户界面开发的过程。通过Web.py 轻量级框架提供的核心模块可以根据需求快速开发出一个稳定有效的网络应用程序。Web.py具有轻巧简单、代码设计风格简洁的特点。实践证明，采用Web.py开发的程序稳定可靠，能够满足日像仪数据处理系统中用户界面开发的需求。目前，系统初步搭建完毕，但是仍然有不足的地方，例如更可靠地数据错误校验，数据编辑用户友好性提升，以及提供更多的实时交互功能，这些将在后续工作中继续研究和探讨。

MUSER DashBoard Task +Calibration- {Antenna- Weather QConfiguration About   
Integration Task   
From: 2012-11-22 00:00:00 To 2016-12-22 23:59:59 Q Search +New   
ID Time Span Integration Time(Seconds) Array Create Time Status Operations   
17 2015-11-01 12:08:50\~2015-11-01 12:08:51 1.0 MUSER-I 2016-04-06 15:53:36 Running... 三DetaiReset   
16 2015-11-01 12:08:50\~2015-11-01 12:08:52 1.0 MUSER-I 2016-03-10 00:00:00 Completed DetaiReset   
2 2015-11-01 12:08:50\~ 三DetaiReset MUSER   
6 2015-11-01 12:08:50\~2 三DetaiReset   
1 2015-11-01 12:08:50\~20 Integration Task (Integration-9) DetailReset   
3 2015-11-01 12:08:50\~2 三DetaiCReset Time Span 2015-11-0112:08:50\~2015-11-0112:08:52 Integration Time 1.0 seconds   
4 2015-11-01 12:08:50\~2 三DetaiReset Array MUSER-I Status CompletedDownload   
5 2015-11-01 12:08:50\~20 EDetaiReset   
9 2015-11-01 12:08:50\~2 三DetaiReset Sub Tasks   
14 2015-11-01 12:08:50\~20 三DetaiReset   
15 2016-03-01 10:00:00\~20 Integral Repeat 三Detail CReset Time Array Number Number Status Operation 1 20151101120850.007259 MUSER-I 40 1 Success.. Total:11,1/1Pages 20151101120851.007259 MUSER-I 40 1 Success..

# 参考文献：

[1] 颜毅华，张坚，陈志军，等.关于太阳厘米-分米波段频谱日像仪研究进展［J].天文研究与技术——国家天文台台刊，2006，3(2)：91-98.Yan Yihua，Zhang Jian，Chen Zhijun，et al. Progress on Chinese radioheliograph in cm-dmwavebands [J].Astronomical Research & Technology——Publications of National AstronomicalObservatories of China，2006，3(2）:91-98.  
[2] Wang Feng，Mei Ying，Deng Hui，et al.Distributed data-processing pipeline for MingantuUltrawide Spectral Radioheliograph [J].Publications of the Astronomical Society of the Pacific,2015，127(950):383-396.  
[3] Wei Shoulin，Wang Feng，Deng Hui，et al. OpenCluster: a flexible distributed computingframework for astronomical data processing [J]. Publications of the Astronomical Society of thePacific，2017，129(972):1-14.  
[4] 马荣庭，刘飞，邓辉.CSRH-I观测数据接收子系统的设计与实现［J]．天文研究与技术，2015，12(1):63-69.Ma Rongting，Liu Fei，Deng Hui. The design and implementation of a data-receiving subsystemof the CSRH-I ［J].Astronomical Research & Technology，2015，12（1）:63-69.  
[5] 梅盈，刘东浩，王锋，等.中国频谱射电日像仪FITS-IDI文件格式研究［J].天文研究与技术——国家天文台台刊，2014，11(4)：388-395.

Mei Ying，Liu Donghao，Wang Feng，et al.A study of the FITS-IDI format for the ChineseSpectral Radio Heliograph［J].Astronomical Research & Technology——Publications ofNational Astronomical Observatories of China，2014，11(4）:388-395.[6] 卫守林，石聪明，高姣姣，等.VantagePro气象站实时数据采集与在MUSER中的应用研究[J]．天文研究与技术，2016，13(1)：117-123.Wei Shoulin，Shi Congming，Gao Jiaojiao，et al.A study on the real-time collection of theVantage Pro weather station and the application in the MUSER ［J]. Astronomical Research &Technology，2016，13（1）：117-123.[7] 陈蒙，王锋，邓辉，等.基于Python 的天文软件命令行界面设计与实现［J].天文研究与技术，2015，12(2)：196-203.Chen Meng，Wang Feng，Deng Hui，et al.Design and implementation of an astronomicalcommand line interface system based on the Python [J].Astronomical Research & Technology,2015，12(2):196-203.[8] Swartz A.Web.py Install Guide ［EB/OL]. http://webpy.org/install.

# The Application Method of Web.py in Developing MUSER Software System

Cai Nengjian $^ { 1 }$ ，Liu Donghao²，Deng Hui’，Wei Shoulin $^ { 1 , 3 }$ ，Wang Feng $^ { 1 , 3 }$ ， Mei Ying $^ { 1 , 3 }$ ，Dai Wei $^ { 1 , 3 }$ ，Liu Yingbo4，Wu Jingping§ (1.KeyLaboratoryofApplicationsofComputerTechnologyoftheYunnanProvince,UniversityofScienceand TechnologyofKunming, Kunming 65050,China，Email：denghui@cnlab.net；2.National Astronomical Observatories，ChineseAcademyof Sciences, Beijing 10o012,China；3.Yunnan Observatories，Chinese Academy of Sciences，Kunming 65O0l1,China； 4.Yunnan Academy of Scientific & Technical Information，Kunming 65Oo51,China;； 5.Yunnan Information Technology Development Center，Kunming 65O034,China)

Abstract：The hardware construction of Mingantu Ultrawide SpEctral Radioheliograph（MUSER）has been completed，and data processng system for the MUSER project has also been completed.In order to improve its user operation availability，simplifyits operation diffculty，MUSER data processing system provides both the traditional command-line interface and the WEB interface for the users.This paper introduced a framework named web.py and discussed how to apply the framework to quickly develop a WEB interface for MUSER. Overall，for astronomy software written in Python，web.py is a proper choice in developing its WEB interface.

Key words: Astronomy software；Web.py；User interface