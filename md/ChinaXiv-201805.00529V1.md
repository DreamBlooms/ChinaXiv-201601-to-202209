# MUSER的负数据库接口设计与实现

石聪明1,²，张晓丽²，王锋1,2,3，戴伟2,，杨秋萍2,31  
（1.昆明理工大学管理与经济学院，云南 昆明650093；2．昆明理工大学云南省  
计算机技术应用重点实验室，云南昆明650500；3．中国科学院云南天文台，云南昆明 650011)

摘要：明安图射电频谱日像仪（MingantU SpEctral Radioheliograph，MUSER）目前已经进入常规观测，必将产生海量的观测数据。针对日像仪需要高效管理其产生的海量观测数据并提供高效检索服务的需求，负数据库管理系统提出并被应用到日像仪中。详细介绍了负数据库的接口设计与实现，并通过实验验证了所设计接口的有效性和性能。负数据库管理系统不仅可以有效解决其面临的问题，也可以为新一代望远镜负数据库管理系统提供参考。

关键词：接口设计；负数据库；MUSER中图分类号： ${ \mathrm { T P 2 7 4 ^ { + } } } .$ 2文献标识码：A 文章编号：1672-7673(2018)

明安图射电频谱日像仪（MingantU SpEctral Radioheliograph，MUSER）是中国自行研制的新一代具有高时间、高空间、高频率分辨率的对太阳进行射电频谱成像的专用射电望远镜设备，观测频率范围为0.4GHz-15GHz[1]。明安图射电频谱日像仪由低频阵（MUSER-I）和高频阵（MUSER-II）两个子阵构成。低频阵由40面4.5m口径的抛物面天线及接收设备组成，在64个频点上成像,工作频率为0.4GHz\~2GHz；高频阵由60面2m口径的抛物面天线及接收设备组成，在528个频点上成像，工作频率为 $2 \mathrm { G H z } ^ { \sim } 1 5 \mathrm { G H z }$ 。低频阵和高频阵的数字接收机每3.125ms产生一个数据帧，并通过1.25Gb的光纤传送到数据获取服务器。低频阵和高频阵数据帧的大小分别为100000B、204800B。

随着明安图射电频谱日像仪进入常规观测，将产生海量的观测数据。如果每个观测日有10小时，理论上，每个观测日产生2.304千万个观测数据帧，总共3.5112TB的观测数据,每年有365个观测日的情况下将产生将近84.1亿个观测数据帧和将近1.3PB的观测数据。文[2]基于补集理论和明安图射电频谱日像仪的数据特征设计了一个高性能的海量数据管理系统（负数据库），不仅可以用较少的存储量来存储海量数据帧中的元数据，而且可以提高检索性能。然而，文[2]没有详细介绍负数据库中的接口设计与实现。

考虑到除了明安图射电频谱日像仪以外，其他望远镜也有类似的海量历史数据管理需求，有必要介绍负数据库中的接口设计与实现的介绍。本文主要介绍MUSER负数据库接口的设计和实现，进而为天文领域其他开源系统的海量数据管理提供一个有价值的参考。

# 1负数据库简介

文[3]在2004年首次将存储所有原始记录信息的数据库称为正数据库（the PositiveDatabase），存储通过补集理论从所有原始记录信息中推导的补集信息的压缩形式的数据库称为负数据库（the Negative Database），且证明了从一个给定的正数据库生成负数据库是可行的，反之是一个NP完全问题。文[4]在2005年提出信息的负表示（the negativerepresentation）是一种受人工免疫系统启发而来的新的数据表示方法，该方法与传统表示方法最大的区别在于负表示总是存储原始数据信息的补集信息的压缩形式来代替存储原始数据信息，同时指出负数据库是信息负表示的一种存储形式。在随后的2006年，信息负表示的思想被应用到调查方面并提出了负调查的方法，该方法能够达到保护被调查者隐私信息的目的'。文[5]利用负数据库的思想提出一种安全保护算法，使用该算法能够为通用的正数据库提供一个额外的安全保护层。文[6]将负数据库的思想应用于构建生物特征数据库，基于负数据库思想的生物特征数据库能够达到保护数据隐私的作用。文[7]利用负数据库的思想实现了一个基于网络环境的数据管理系统，该系统能够提供更高级别的数据安全。

上述文献涉及的负数据库主要应用在隐私保护和数据安全领域，且从负数据库推导出正数据库是一个NP完全问题。然而，为明安图射电频谱日像仪设计的负数据库不仅能够降低存储海量数据帧的元数据所需的存储容量，而且能够从检索的补集信息中快速推导数据帧对应的元数据信息。

# 2接口设计与实现

进一步完善了负数据库原型系统的功能，并在此基础之上抽象了负数据库的接口。进而方便通过修改少量的代码就可以将明安图射电频谱日像仪的负数据库系统移植或集成到其它望远镜的数据管理系统中。以下在简要介绍明安图射电频谱日像仪的数据特征、补集理论和记录格式的基础上，着重介绍负数据库的一些重要接口的设计与实现。

2.1明安图射电频谱日像仪的数据特征

当前的数据存储系统是按照目录、文件以及数据帧的形式组织数据。所有的观测数据以文件的形式存储在系统中，即低频阵和高频阵的文件分别存放在不同的目录中。每分钟观测产生的19200个连续的数据帧封装到一个文件中，观测日期、观测时间、波段、极化方式、可见度数据、自相关数据等信息封装到数据帧中。文件名是根据文件中第1个数据帧的观测日期时间以“YYYYMMDDhhmm”（YYYY:年，MM:月，DD:日，hh:时，mm:分）的格式命名。

由于受当前存储系统性能的限制，将观测数据帧写入磁盘时会随机丢失数据帧，这无法保证封装到同一个文件中的19200个数据帧在同一分钟内。并且，开始观测按钮是由人工启动的，无法保证在整分整秒恰好启动观测按钮。上述两种情况导致同一分钟观测产生的数据帧被存储到两个数据文件中。

# 2.2补集理论

假定已知全集U，数据集A，且数据集C是数据集A的补集。负数据库管理系统基于如下假设：（1）全集U已知，且可以被精确定义；（2）所有的记录可以通过给定的初始化条件推导；（3）数据集A可以从它的补集C中推导。依据补集理论设计的明安图射电频谱日像仪的负数据库管理系统可以通过存储少量的丢帧信息并利用大量的逻辑推导运算保证不会丢失任何已保存在文件中的数据帧元数据信息。

# 2.3记录格式

设计一种记录格式表示数据文件、观测日期时间以及数据帧之间的逻辑关系。为了方便叙述，用Record表示该记录格式，Record的具体格式如1图。

Record

![](images/d6eeb380d498b42669fbf1bfecea3a62e73c78a99ca6f79e4af95ee94a7becf0.jpg)  
图1记录格式  
Fig.1 The record format

Record由datetime，filel和file2构成。datetime由年（yyyy）、月（MM）、日（dd）、时（hh）、分（mm）构成。filel由文件名（filename）、文件中第一帧的时间（timeF）、文件中最后一帧的时间（timeL）、文件内帧的逻辑关系（FrameR）构成。

timeF和timeL的格式一样，由年（yyyy）、月（MM）、日（dd）、时（hh）、分（mm）、秒（ss）、毫秒（ffffff）构成。文件内帧的逻辑关系通过开始偏移量（S）、开始偏移量对应数据帧的波段（B）、开始偏移量对应数据帧的极化（P）、结束偏移量（E)以及累计丢帧数（CA）描述。

# 图2相应的接口和类

Fig.2 The related interface and class

# 2.4接口设计与实现

基于上述的明安图射电频谱日像仪数据特征、补集理论以及为数据特征设计的特定记录格式，本文为明安图射电频谱日像仪的负数据库设计了相应的接口函数和类，如图2。这些接口函数和类主要用于从观测数据文件构造特定格式的记录、从数据记录推导相应的数据帧信息以及连接底层数据库等。负数据库主要包括底层数据库可用性校验接口、望远镜数据文件操作有关的接口、数据库同步（初始化）接口、数据检索接口、元数据重构接口等。同时，MUSER的负数据库接口设计与实现在一定程度上遵守Python DB-API规范²,可以降低系统各部分的相互依赖，提高组成单元的内聚性，降低组成单元间的耦合程度，进而提高系统的可维护性和可扩展性。

# 2.4.1底层数据库可用性校验接口

底层数据库可用性校验接口（validate_underlying_database_availability）只提供了对MySQL、Redis这两个数据库的支持，在以后的工作中逐渐增加对其他数据库的支持。底层数据库可用性校验接口主要用于验证底层数据库配置文件(db_config.xml)中的底层数据库是否支持、底层数据库对应的模块是否安装以及其它与数据库连接相关的配置信息是否有效等。底层数据库可用性校验接口的伪代码如图3。

图3底层数据库可用性校验接口

Fig.3 Underlying database availability validation interface

# 2.4.2望远镜数据文件操作有关的接口

望远镜数据文件操作有关的接口主要基于明安图射电频谱日像仪数据处理系统（MUSEROS）中的muserdata.py实现，主要提供对 MUSER特有的裸数据文件（RawData[8]）进行操作。望远镜数据文件操作有关的接口（图4）主要包括给定帧序定位帧位置子接口、获取数据帧中观测日期时间等元数据的子接口、打开观测数据文件的子接口、关闭观测数据文件的子接口以及跳跃特定数目帧的子接口等。数据库同步接口以及数据检索接口等核心接口的功能都严重依赖望远镜数据文件操作有关的接口。

图4数据文件操作接口Fig.4Data file operation interface

# 2.4.3数据库同步（初始化）接口

数据库同步（初始化）接口主要提供首次将初始化数据库以及后来定期从新增的观测数据文件中提取的构造记录所需的相关元数据、利用相关元数据构造记录以及将记录存储到底层数据库等功能。数据库同步（初始化）接口的实现伪代码如图5，该接口是明安图射电频谱日像仪负数据库的一个核心接口。

图5数据库初始化接口

Fig.5 Database initialization interface

# 2.4.4数据检索接口

目前的数据检索接口只提供了依据给定的开始查询日期时间（ $\mathrm { T _ { s t a r t } }$ ）、结束查询日期时间（ $\mathrm { T _ { e n d } }$ ）、波段信息以及极化方式下的数据检索功能，其他更加复杂条件的数据检索功能还有待进一步完善。数据检索接口的实现伪代码如图6，该接口也是负数据库中的一个核心接口。同时，数据检索接口还调用了元数据重构函数（refactor_frame_metadata）、将Tstart及 $\mathrm { T _ { e n d } }$ 转换成起止查询帧范围（IndexS,IndexE）的转换函数（convert_filter_start_end_index）等接口函数。

# 图6数据检索接口的伪代码

Fig.6 The pseudocodes for the data retrievalinterface

# 3接口有效性验证

本文测试设计的明安图射电频谱日像仪负数据库接口的性能使用的硬件环境为：Intel24核Xeon(R）E5-2620v2@2.10GHz处理器、64GBDDR3内存、6TB硬盘；软件环境为：CentOS7.4、Python2.7；数据库为：Redis 4.0、MySQL 5.7；测试数据为：MUSER-II进行常规观测产生的400个观测数据文件（1572GB）、低频阵进行日常观测产生的400个观测数据文件（768GB）。

本文主要在目前支持的 Redis以及MySQL底层数据库的基础之上测试设计的数据初始化接口以及数据检索接口的性能。

# 3.1数据库同步（初始化）接口性能测试

为了保证数据库初始化接口性能测试的有效性，对数据库初始化的实验重复进行了1000次，并将测试结果的平均值作为测试结果。测试得到的数据库初始化的平均时间对比见图7。对于相同的观测数据文件，基于内存的Redis数据库初始化速度比MySQL略微快；对于不同的观测数据文件，数据量大的高频阵的速度比数据量小的低频阵的略慢。

# 3.2数据检索接口性能测试

分别测试了从数据库中分别检索1、8、80、160、320、640个连续数据帧的响应时间。同时为了保证数据检索响应时间的有效性和精确性，对每种数据检索操作重复进行100000次并将测试结果的平均响应时间作为测试结果。测试后得到的数据检索的平均响应时间对比见图8。对于相同的数据，基于内存Redis 的负数据库检索性能比基于MySQL的负数据库快2到6倍。对于低频阵和高频阵，使用相同底层数据库的负数据库的检索性能基本上相同。随着检索数据帧的增加，基于MySQL的负数据库的检索性能比基于Redis 的负数据库检索性能恶化得更快。

MySQL(MUSER-I) Redis(MUSER-I) 500 500   
(puooas) 409.742 (puooas) 408.054 400 400 ★   
irn 3020 irn 3020   
100 100   
日 54.233 日 53.032 0 0 0 100 200 300 400 500 0 100 200 300 400 500 Thenumber of initialization data files The number of initialization data files MySQL(MUSER-II) Redis(MUSER-II) 500 500   
(puooas) 411.642 prrress erennsede 409.454 400 400   
n 3020 100 55.438 日 54.121 0 0 100 200 300 400 500 0 100 200 300 400 500 The number of initialization data files The number of initialization data files

![](images/353d9b53785b37d83825a6b3579364792be895a1e54fd9985a022ca680df7670.jpg)  
图8数据检索性能Fig.8Data retrieval performance

4结束语

本文简要介绍了明安图射电频谱日像仪负数据库管理系统中涉及的理论基础以及记录格式，并详细讨论了负数据库管理系统的接口设计与实现，通用实验验证了所设计和实现的接口具有较好的鲁棒性、通用性以及有效性。但是，由于负数据库设计的初衷是解决明安图射电频谱日像仪面临的海量数据管理问题，且数据存储使用其特有的裸数据文件格式，而不是通用的UVFITS、FITS-IDI等其他通用的文件格式，所以负数据库接口的通用性和可移植性还有待进一步验证。同时，明安图射电频谱日像仪负数据库中的接口还需要进一步完善。本文的研究成果可以为其它新一代望远镜系统的数据管理提供一个有价值的参考。

# 参考文献

[1] Yan Y， Zhang J，Wang W，et al. The Chinese spectral radioheliograph—CSRH[J]. Earth，Moon，and Planets，2009，104(1-4):97-100.   
[2] Shi Congming， Wang Feng， Deng Hui，et al. High-performance Negative Database for Massive Data Management System of The Mingantu Spectral Radioheliograph[J]. Publications of the Astronomical Society of the Pacific， 2017,129(978): 1-10. [3] EspondaF， ForrestS， HelmanP.Enhancingprivacythrough negative representations of data[R]. New Mexico: University of New Mexico, 2004.   
[4] Esponda F， Forrest S, Helman P. Negative representations of information[J]. International Journal of Information Security_,20o9,8(5) :331-345.   
[5] Dubey G, Khurana V, Sachdeva S. Implementing security technique on generic database[C]//Eighth International Conference on Contemporary Computing， 2015: 370- 376.   
[6] Bringer J，Chabanne H. Negative databases for biometric data[C]// Proceedings of the 12th ACM Workshop on Multimedia and Security. 2010: 55-62.   
[7]Patel A， Sharma N,EirinakiM. Negativedatabase for data security[C]//International Conference on Computing， Engineering and Information. 2009:67-70.   
[8] Wang F， Mei Y， Deng H, et al. Distributed data-processing pipeline for Mingantu Ultrawide Spectral Radioheliograph[J]. Publications of the Astronomical Society of the Pacific，2015，127(950):383-396.

# Design and Implementationof the MUSER Negative Database Interfaces

Shi Congming $^ { 1 , 2 }$ , Zhang Xiaoli²， Wang Feng1,23,Dai Wei2,3, Yang Qiuping2,3 (1. Faculty of Management and Economics，Kunming University of Science and Technology，Kunming 650093, China;2.Key Laboratory of Applications of Computer Technologyof the Yunnan Province，Kunming University of Science and Technology， Kunming 650504，China;3. Yunnan Observatories，Chinese Academy of Sciences, Kunming 650216,China）

Abstract:The MingantU SpEctral Radioheliograph (MUSER) has entered the stage of routine observation and will generate massive observation data. How to effectively manage and query massive observation data has become a critical and urgent problem for the MUSER. A negative database management system for the MUSER is used to solve the mentioned problem. In this paper，we have introduced the design and implementation of the MUSER negative database interfaces in detail. Meanwhile， the system can not only solve the problem of the MUSER effectively， but also provide a valuable reference for the next-generation telescope system.

Keywords: Interface design;Negative database; MUSER