# 全国降水天气现象平行观测对比分析

马宁12.3，任芝花4，王妍4，刘娜4，曹宁1.2

（1.中国气象局旱区特色农业气象灾害监测预警与风险管理重点实验室,宁夏 银川750002;2.宁夏气象防灾减灾重点实验室,宁夏 银川750002；3.宁夏气象信息中心,宁夏 银川750002;4.国家气象信息中心，北京100081)

摘要：采用2017-08—2018-08全国2363个气象站降水现象平行观测对比观测数据，分别从数据完整性和准确性方面对雨、雪、毛毛雨、冰雹、雨夹雪5种降水现象自动观测数据进行了对比分析。结果表明：(1）雨、雪、毛毛雨现象的过程捕获率最高，分别为 $6 6 . 9 \% . 6 9 . 2 \% . 5 0 . 1 \%$ ,冰雹的小时捕获率最高，为 $5 1 . 8 \%$ ,雨夹雪的各捕获率指标均较低。(2）毛毛雨的漏报率最高为 $6 5 . 9 \%$ ,雪的漏报率次之为 $3 5 . 6 \%$ ,冰雹的漏报率最低为 $1 6 . 2 \%$ ;毛毛雨、雨的错报率较低,雨夹雪和冰雹的错报率较高,毛毛雨、冰雹错报为雨的比例较高,雨错报成毛毛雨的比例较高,雪错报成毛毛雨和雨的比例较高，而雨夹雪则常常是毛毛雨、雨、雪交替出现;毛毛雨和冰雹的空报站点较多。（3）降水现象仪对降水现象的识别可达到分钟级,但与人工观测降水现象相比，存在漏报、错报和空报情况,需要在气象站数据采集端进行质量控制，不断优化降水现象识别算法，并结合其他天气要素进行降水现象综合判识,以提高仪器对降水天气现象的捕获率，降低漏报率、错报率和空报率。

关键词：降水现象；平行观测；数据准确性；捕获率；漏报率；错报率；空报率

降水天气现象(简称降水现象)与人类生活关系密切，影响我国的16种气象灾害中，有4种与降水现象有关[1-5]。我国气象站降水量在2005年底实现了使用自动气象站进行自动观测，国内很多学者开展了地面自动观测与人工观测数据的差异研究[6-10],结果表明，自动观测比人工观测的日降雨量平均偏高 $0 . 1 2 ~ \mathrm { m m }$ ,标准差为 $0 . 7 ~ \mathrm { m m }$ ,相对偏高$1 . 4 2 \%$ ，观测仪器不同会导致系统偏差。但长期以来我国气象站降水现象一直采用人工目测的方式进行观测[]。随着我国气象事业的发展，人工目测方式主观性强、观测频率低，已无法满足气象服务的需求，迫切需要实现降水现象及时、准确、连续的自动化观测。解决降水现象自动化观测的问题，降水现象的判识方法和利用仪器进行自动化观测是必然途径。

近年来国内学者在降水现象判识方面做了相关研究[12-16],基于雨滴谱光学测量技术的降水现象自动观测研究较多[12-14],光学原理测量降水不仅能够检测降水类型，如区分雨、雪、冰雹和混合降水，还可获取较多降水粒子信息。国际上常见的降水现象自动观测仪器(简称降水现象仪)主要有芬兰Vaisala公司的PWD12、PWD22系列降水现象传感器和FD12P天气传感器、英国BiralVPF-730和PWS100降水现象传感器、德国OTTParsivel雨滴谱仪、美国OSI公司Owi-430降水现象传感器[17],国内生产的降水现象仪主要有DSG1、DSG3、DSG4、DSG5、CJY-2C等型号。

中国气象局曾开展多次降水现象仪的对比试验工作。2009年8—9月中国气象局在北京国家基本气象站布设了美国OSI公司的OWI-430、英国Bi-ral公司的VPF-730 和美国Campbell公司的PWS-100和我国凯迈(洛阳)测控公司研发的CJY-2C/T降水现象仪，进行为期2个月的自动和人工降水现象对比观测，发现自动化设备记录与人工记录差异明显，且某些设备有较多漏报和错报现象[17-18] 。2011-12—2012-06中国气象局分别在北京国家基本气象站、庐山国家基准气候站对HY-MPW11型天气现象仪、DZT1型天气现象仪和TQXX-1型天气现象仪进行对比观测试验，结果表明各仪器观测降水现象的数据准确性均大于 $9 0 \%$ ，能够满足业务需求[19]。2014年7月，中国气象局组织6个厂家共18台降水现象仪，分别在北京国家基本气象站和长沙国家基本气象站进行了3个月的对比观测试验，结果表明参试设备对冰雹观测结果较为理想，对毛毛雨和未知现象的观测仍需改进[12]。以上观测实验表明，基于光学原理的降水现象仪在一定程度上能够满足气象业务需求，但对个别降水现象的观测仍需改进。

随着全国地面气象观测自动化改革的推进，2017年8月开始，除了上海市所属气象站早期已布设并开展降水现象自动观测外，中国气象局开始在全国其他30个省(区、市)2363个气象站逐步布设雨滴谱式降水现象仪，同年底均完成仪器安装。为了解自动与人工两种观测方式获取的资料差异，上述各气象站需要进行至少为期2a的平行对比观测[1]。按平行观测相关规定[20],本次平行观测第一年，自动观测结果仅记录，不允许对异常数据进行处理；平行观测一年后，自动观测降水现象数据若出现错误、漏报等异常情况，需对其尽可能进行质控、修正。从客观评价角度出发，本文以2363个气象站平行观测第一年的数据为基础，分别从数据完整性和准确性等方面对自动观测与人工观测降水现象结果进行对比分析，以便为降水现象自动观测数据的应用提供基础支撑。

# 1数据来源与方法

# 1.1数据来源

2363个气象站降水现象仪分别来自5个厂家的5种型号，包括DSG1、DSG3、DSG4、DSG5和CJY-2C型，其在全国的安装分布如图1所示。其中，DSG1占比为 $2 9 . 8 \%$ ,DSG3占比为 $9 . 5 \%$ ,DSG4占比为$2 3 . 7 \%$ ,DSG5占比为 $3 6 . 9 \%$ ,CJY-2C占比为 $0 . 1 \%$ 。

本次分析数据来自于全国2363个气象站自动与人工第一年平行观测对比资料，在处理资料的过程中，对仪器识别的降水现象异常值进行了剔除。仪器识别的降水现象类型为毛毛雨、雨、雪、雨夹雪和冰雹5种，人工观测到的阵雨、阵雪、阵性雨夹雪在评估时分别按雨、雪、雨夹雪处理。以人工观测的天气现象为参考标准，对降水现象仪白天(08：00—20：00)的自动观测数据分别从捕获率、漏报率、错报率和空报率等方面进行统计分析，夜间由于人工观测降水现象无起止时间记录，不参与对比分析。

![](images/7c6f557e39ed0fa3627bc73530af61058a94907cd83f06aa4fd97b5ee93c727f.jpg)  
图1全国降水平行观测站点分布  
Fig.1Distribution of parallel observation stations of precipitation in China

# 1.2数据完整性统计方法

观测数据以日数据为基本单位，对各厂家仪器的数据完整性作缺测率评估，计算缺测率。

式中：s为实际观测日数； $s$ 为应观测日数。

# 1.3数据准确性计算方法

1.3.1捕获率指标捕获率根据粒度的粗细分为分钟捕获率、小时捕获率和过程捕获率。人工观测到降水现象发生，同时仪器也观测到该降水现象的分钟数(b占人工观测到该降水现象分钟数 $( B )$ 的百分比定义为分钟捕获率；仪器观测到该降水现象发生的小时数 $( c )$ 占人工观测到该降水现象的小时数$( C )$ 的百分比定义为小时捕获率；仪器正确识别该降水现象发生的过程次数 $( a )$ 占人工观测到该降水现象过程次数(A)的百分比定义为过程捕获率。

百分比定义为漏报率；仪器错误识别该种降水现象的分钟数 $( e )$ 占人工观测到该降水现象分钟数 $( B )$ 的百分比定义为错报率；仪器缺测的分钟数 $( f )$ 占人工观测到该降水现象分钟数 $( E )$ 的百分比定义为缺报率；人工观测未有降水现象发生，仪器识别有该现象发生的分钟数 $( f )$ 占无该降水现象分钟数 $( D )$ 的百分比定义为空报率。

# 2结果与分析

# 2.1数据完整性分析

将全国30个省(区、市)各气象站应观测日数和实际观测日数求和，计算总缺测率，结果如表1所示。全国缺测率为 $6 . 2 \%$ 。云南、宁夏、新疆、河北、重庆等地的缺测率较高，都在 $10 \%$ 以上，其中新疆最高达到了 $1 3 . 9 \%$ ，重庆、河北次之，分别为 $1 1 . 8 \%$ 和$1 1 . 5 \%$ ;北京、四川、天津、安徽、山东、山西、广西、福建、贵州、辽宁10省(区、市)的缺测率较低，都在 $5 \%$ 以内，其余各省(区、市)的缺测率均在 $5 \% \mathrm { \sim } 1 0 \%$ 之间。各省(区、市)的数据缺测原因主要是对降水现象仪维护不及时和对数据采集处理软件操作不熟练，导致数据未及时生成并上传。

# 2.2数据准确性分析

降水过程定义8：间歇小于 $1 5 ~ \mathrm { m i n }$ 降水持续过程。在进行小时捕获率统计时，如果出现冰雹，则该小时降水现象以冰雹现象为准，如果某一小时出现多种其他降水现象，则无论是人工还是自动均以出现分钟数最多的降水现象为准；在进行过程捕获率统计时，以人工观测的降水过程为参考标准，如果某降水过程中仪器识别到了冰雹现象，则以冰雹现象为准，如果仪器识别到其他多种降水现象，则以出现分钟数最多的降水现象为仪器识别的过程降水现象。

1.3.2非捕获率指标人工观测到有某种降水现象发生，仪器未能识别该种降水现象(无降水现象）的分钟数 $( d )$ 占人工观测到该降水现象分钟数 $( B )$ 的

2.2.1降雨现象全国2363个气象站均出现了降雨现象(图2)。全国降雨分钟捕获率为 $4 6 . 7 \%$ ，小时捕获率为 $6 0 . 8 \%$ ，过程捕获率为 $6 6 . 9 \%$ ，漏报率为$3 4 . 9 \%$ ,错报率为 $1 3 \%$ 。各省(区、市)降雨分钟捕获率为 $2 5 \% { \sim } 7 3 \%$ ,贵州最低，天津最高，北京、福建、黑龙江、吉林、内蒙古均在 $6 0 \%$ 以上。各省(区、市)小时捕获率为 $3 7 . 2 \% { \sim } 8 4 . 3 \%$ ,贵州最低，天津最高，河南、河北、西藏等11省(区、市)的小时捕获率均在$7 0 \%$ 以上。各省（区、市)过程捕获率为 $4 7 . 6 \% \sim$ $8 8 . 1 \%$ ，贵州最低，天津最高，辽宁、山西、安徽等15省(区、市)的过程捕获率均在 $7 0 \%$ 以上。各省(区、市)降雨漏报率为 $1 3 . 5 \% { \sim } 5 2 . 6 \%$ ，天津最低，贵州最高，甘肃的漏报率也在 $2 0 \%$ 以下。各省(区、市)降

# 表1各省(区、市)自动观测降水现象数据缺测情况统计

Tab.1 Lack of data of automatic precipitation phenomenon observed in all provinces   

<html><body><table><tr><td>省(区、市)</td><td>缺测率/%</td><td>省(区、市)</td><td>缺测率/%</td></tr><tr><td>云南</td><td>10.5</td><td>河北</td><td>11.5</td></tr><tr><td>内蒙古</td><td>6.3</td><td>河南</td><td>9.7</td></tr><tr><td>北京</td><td>1.1</td><td>浙江</td><td>7</td></tr><tr><td>吉林</td><td>5.5</td><td>海南</td><td>7.8</td></tr><tr><td>四川</td><td>3.5</td><td>湖北</td><td>5</td></tr><tr><td>天津</td><td>2.2</td><td>湖南</td><td>6.4</td></tr><tr><td>宁夏</td><td>10.1</td><td>甘肃</td><td>5.4</td></tr><tr><td>安徽</td><td>3.7</td><td>福建</td><td>2.1</td></tr><tr><td>山东</td><td>1.1</td><td>西藏</td><td>9.5</td></tr><tr><td>山西</td><td>1.5</td><td>贵州</td><td>4.9</td></tr><tr><td>广东</td><td>9.3</td><td>辽宁</td><td>3.2</td></tr><tr><td>广西</td><td>3.2</td><td>重庆</td><td>11.8</td></tr><tr><td>新疆</td><td>13.9</td><td>陕西</td><td>7.6</td></tr><tr><td>江西</td><td>5.8</td><td>青海</td><td>9.2</td></tr><tr><td>江苏</td><td>6.9</td><td>黑龙江</td><td>5.7</td></tr></table></body></html>

雨错报率为 $2 \% { \sim } 2 6 . 6 \%$ ,吉林最低，湖南最高，安徽、北京等14个省(区、市)的错报率都在 $1 0 \%$ 以下。当出现错报时，大部分省(区、市)的雨错报成毛毛雨的比例较高，也有少数省(区、市)将雨错报成雪、雨夹雪或冰雹。浙江、湖南错报成毛毛雨的平均错报率最高，达到 $2 0 \%$ 以上。各省(区、市)雨错报成雪、雨夹雪或冰雹的平均错报率较低，都在 $1 \%$ 以内。

全国各气象站的空报率在 $0 \% { \sim } 1 2 . 8 \%$ ,其中，

$9 9 . 5 \%$ 的站点空报率小于 $5 \%$ ， $0 . 4 \%$ 的站点空报率介于 $5 \% { \sim } 1 0 \%$ ， $0 . 1 \%$ 的站点空报率大于 $10 \%$ ;从各省(区、市)看，西藏的空报率较高，为 $2 \%$ ,其余各省（区、市)均在 $2 \%$ 以内。

全国降雨的分钟捕获率较低，小时捕获率较分钟捕获率有所提高，过程捕获率最高;各省(区、市）的分钟捕获率也普遍较低，小时捕获率有所提高，过程捕获率最高;全国各省(区、市)中天津、吉林、内蒙古、福建的捕获率最好，贵州、湖南、海南的捕获率最低。各省(区、市)降雨现象捕获率的差异与各省(区、市)的降雨频次及强度有关，同时也与仪器和算法有关，使用DSG4和DSG5的省（区、市）对降雨的捕获率较高。出现错报，也是因为仪器会把雨识别为成毛毛雨，也有少数省(区、市)将雨识别成雪、雨夹雪或冰雹。

2.2.2降雪现象全国有1857个气象站出现了降雪现象(图3)。全国降雪分钟捕获率为 $5 0 . 3 \%$ ,小时捕获率为 $6 4 . 5 \%$ ，过程捕获率为 $6 9 . 2 \%$ ，漏报率为$3 5 . 6 \%$ ,错报率为 $7 . 1 \%$ 。各省(区、市)降雪分钟捕获率为 $5 . 3 \% \sim 7 5 . 7 \%$ ,贵州最低,甘肃最高，内蒙古、宁夏、安徽、江苏、黑龙江均在 $6 0 \%$ 以上。各省（区、市)小时捕获率为 $1 0 . 8 \% { \sim } 8 7 . 1 \%$ ,云南最低，内蒙古最高，宁夏、安徽、山东、甘肃、江苏、辽宁、黑龙江的小时捕获率均在 $70 \%$ 以上；各省(区、市)过程捕获率为 $1 6 . 7 \% \small { \sim } 8 9 . 1 \%$ ,云南最低，内蒙古最高，天津、宁夏、安徽、山东、江苏、湖北、甘肃、辽宁、黑龙江也均在 $7 0 \%$ 以上。各省(区、市)降雪漏报率为 $1 2 . 9 \%$ 2$7 6 . 7 \%$ ,安徽最低，贵州最高，内蒙古、天津、宁夏、安徽、浙江、甘肃、黑龙江的漏报率均在 $2 0 \%$ 以下。各省(区、市)降雪错报率为 $2 \% { \sim } 2 9 . 4 \%$ ,吉林最低，湖南最高，安徽、北京等14省(区、市)的错报率都在$1 0 \%$ 以下。当出现错报时，降雪现象一般会错判为毛毛雨、雨或雨夹雪，少数站点也会错判为冰雹。错判冰雹的情况出现在河北、陕西的部分站点。

![](images/27c2866032cfaec4f6d4ee08b98717a6998ff9b5ce00c9054005d238eb00ca62.jpg)  
图2各省(区、市)及全国降雨数据准确性各指标百分比  
Fig.2 Percentage of indicators for accuracy of provincial and national rainfall data

![](images/c48848e00ac05aa370fe57f5c0a7bc1b7b1fc765d9cb9144bc338b1c292ee8ab.jpg)  
图3各省(区、市)及全国降雪数据准确性各指标百分比计  
Fig.3Percentage of indicators of accuracy of provincial and national snowfall data

全国出现降雪各气象站的空报率在 $0 \% \sim$ $4 8 . 5 \%$ ,其中 $9 9 . 6 \%$ 的站点空报率为 $5 \%$ $0 . 3 \%$ 的站点空报率介于 $5 \% \sim 1 0 \% , 0 . 1 \%$ 的站点空报率大于 $10 \%$ 内蒙古的镶黄旗气象站空报率异常偏高；从各省（区、市)看，内蒙古、甘肃、黑龙江的空报率较高，在$1 \%$ 以上，其余各省(区、市)均在 $1 \%$ 以内。

全国降雪的分钟捕获率较低，小时捕获率较分钟捕获率有所提高，过程捕获率最高;各省(区、市）的分钟捕获率也普遍较低，且差距较大，小时捕获率有所提高，过程捕获率最高;其中，内蒙古、宁夏、甘肃、黑龙江的捕获率最好，云南、四川、贵州的捕获率最低。降雪现象主要出现在北方，南方出现较少，因而捕获率差异较大，同时，吹雪、柳絮、蒲公英等易被错误判识为雪，降雪现象也会被错判为毛毛雨、雨或雨夹雪，少数站点也会错判为冰雹，

2.2.3雨夹雪现象全国有1483个气象站出现雨夹雪现象(图4)。全国雨夹雪分钟捕获率为 $1 . 7 \%$ ，小时捕获率为 $2 . 5 \%$ ,过程捕获率为 $2 . 7 \%$ ,漏报率为$2 9 . 9 \%$ ,错报率为 $6 1 . 4 \%$ 。各省(区、市)雨夹雪分钟捕获率为 $0 \% { \sim } 1 2 . 3 \%$ ，云南、北京等11个省(区、市）的分钟捕获率为0,山西的分钟捕获率最高。各省(区、市)小时捕获率为 $0 \% { \sim } 1 3 \%$ ，云南、北京、天津等13个省(区、市)的小时捕获率为0，山西的小时捕获率最高;各省(区、市)过程捕获率为 $0 \% { \sim } 1 8 . 2 \%$ ，云南、北京、天津等14个省(区、市)的过程捕获率为0,山西最高。各省（区、市)雨夹雪漏报率为 $8 . 7 \%$ $8 5 . 4 \%$ ,安徽最低,贵州最高,浙江、湖北、甘肃、福建的漏报率也在 $2 0 \%$ 以下。各省(区、市)雨夹雪错报率为 $3 \% \sim 8 6 . 2 \%$ ，云南最低，安徽最高，除贵州在$1 0 \%$ 以下外，各省(区、市)雨夹雪错报率普遍较高，23个省(区、市)的错报率都在 $5 0 \%$ 以上。当出现错报时，一般会将雨夹雪现象误判为毛毛雨、雨、雪，有少数站点会误判为冰雹。湖南的雨夹雪误判为毛毛雨的平均错判率较高，达到 $2 1 . 3 \%$ ,其次是天津、山东、浙江,其他省(区、市)均在 $1 0 \%$ 以下;各省(区、市)将雨夹雪误判为雨的平均错报率较高，除云南、甘肃、贵州、青海误判为雨的平均错判率在$1 0 \%$ 以下外,其余各省(区、市)都在 $10 \%$ 以上，且安徽、广东、广西超过 $5 0 \%$ ;各省(区、市)将雨夹雪误判为雪的平均错报率也较高，除云南、广东、湖南、福建、贵州、重庆误判为雪的平均错报率在 $1 0 \%$ 以下，其余各省(区、市)都较高，甘肃高达 $5 9 . 3 \%$ ;将雨夹雪错判为冰雹的情况只出现在北京、吉林、四川、河北和陕西。

![](images/de60682a49e534e32686947b93580ddc18f036db2015d634b7de896be95e394c.jpg)  
图4各省(区、市)及全国雨夹雪数据准确性各指标百分比  
Fig.4Percentages of indicators of accuracy of provincial and national sleet data

全国699个气象站出现雨夹雪空报情况，其中有363个气象站人工观测未出现雨夹雪，但仪器观测有雨夹雪现象。各站的空报率在 $0 . 0 1 \% { \sim } 2 \%$ ，湖北的空报率较高，为 $0 . 8 \%$ ，其余各省(区、市)均在$0 . 5 \%$ 以内。

全国雨夹雪的分钟捕获率、小时捕获率、过程捕获率都很低，均不足 $3 \%$ ;各省(区、市)的分钟捕获率、小时捕获率和过程捕获率也普遍较低，全国各省(区、市)中山西的分钟捕获率、小时捕获率和过程捕获率均最高。雨夹雪的漏报和错报较高，除云南外，各省(区、市)及全国漏报率和错报率之和都达到 $8 5 \%$ 以上。雨夹雪是比较难识别的一种降水现象，各仪器对雨夹雪的识别都比较困难，且雨夹雪的出现频率也不高，因而整体捕获率较低。当出现雨夹雪时，一般会将雨夹雪现象误判为毛毛雨、雨、雪，有少数站点会误判为冰雹。

2.2.4冰雹现象全国有385个气象站出现冰雹现象(图5)。全国冰雹分钟捕获率为 $2 1 . 1 \%$ ，小时捕获率为 $5 1 . 8 \%$ ,过程捕获率为 $4 5 . 3 \%$ ,漏报率为 $1 6 . 2 \%$ ，错报率为 $5 7 . 6 \%$ 。各省(区、市)出现冰雹天气的站数较少，天津、广东、江苏、浙江、福建、重庆冰雹现象分钟数都在15分钟以内，不具有代表性。除上述省(区、市)之外，其余各省(区、市)的冰雹分钟捕获率为 $0 \% { \sim } 5 1 . 7 \%$ ,安徽最低，吉林最高。小时捕获率为 $0 \% { \sim } 8 8 . 4 \%$ ,安徽最低，吉林最高;过程捕获率为$0 \% { \sim } 8 0 . 5 \%$ ,安徽最低，吉林最高。漏报率为 $0 \%$ 2$3 2 \%$ ,安徽最低，广西最高。错报率为 $2 5 . 2 \% { \sim } 1 0 0 \%$ ，河南最低，安徽最高。当出现错报时，大多数省（区、市)的站点会将冰雹错报为雨，有少数站点会误判为毛毛雨、雪或雨夹雪。

全国有1714个气象站出现冰雹空报的情况，其中有1487个气象站人工均未观测到冰雹。各站的空报率在 $0 \% { \sim } 2 . 3 8 \%$ ,河北、陕西的空报率为 $0 . 1 \%$ ，其余各省(区、市)均在 $0 . 1 \%$ 以内。

全国冰雹的分钟捕获率最低，过程捕获率次之，小时捕获率最好；各省(区、市)的分钟捕获率、小时捕获率和过程捕获率情况也不一致，安徽的捕获率最低，吉林的捕获率最高。冰雹现象捕获率各省（区、市)差异较大，主要是冰雹现象在气象站的出现次数少，捕获率会出现两极分化，即 $100 \%$ 或$0 \%$ 。南方出现强降水误判为冰雹的情况较普遍。2.2.5毛毛雨现象全国有377个气象站出现了毛毛雨现象(图6)。全国毛毛雨分钟捕获率为 $2 1 . 7 \%$ ，小时捕获率为 $3 5 . 1 \%$ ，过程捕获率为 $5 0 . 1 \%$ ，漏报率为 $6 5 . 9 \%$ ,错报率为 $6 . 2 \%$ 。各省(区、市)中天津、宁夏、北京、吉林、海南出现毛毛雨现象的站点小于5个，不具有代表性，不作讨论。除上述省(区、市)之外，其余各省(区、市)的毛毛雨分钟捕获率为 $3 . 8 \% .$ ）$6 5 . 3 \%$ ,福建最低，浙江最高，甘肃的分钟捕获率也达到 $6 0 \%$ 以上；小时捕获率为 $8 \% { \sim } 7 8 \%$ ,云南最低,浙江最高,安徽、新疆、甘肃、黑龙江均在 $6 0 \%$ 以上；过程捕获率为 $1 7 . 5 \% { \sim } 8 5 . 7 \%$ ,陕西最低，甘肃最高，内蒙古、新疆、河北、浙江、黑龙江均在 $6 0 \%$ 以上;漏报率为 $1 6 . 4 \% \sim 9 4 . 5 \%$ ,浙江最低，福建最高；各省（区、市)错报率为 $0 . 9 \% { \sim } 2 4 \%$ ，贵州最低，西藏最高。当出现错报时，大部分省(区、市)的毛毛雨会错报成雨，少数省(区、市)的毛毛雨会错报成雪。如宁夏、安徽、黑龙江会错报成雪，安徽也出现错报成冰雹。云南、内蒙古、天津、宁夏、安徽、江西、浙江、西藏、黑龙江错报成雨的平均错报率较高，都在$10 \%$ 以上，其中内蒙古、宁夏分别达到 $2 7 . 7 \%$ 和

![](images/7a0d21f201173e0f1d7c85e4b2a179efca38f601fd9e86146c2ecb22907b6555.jpg)  
图5各省(区、市)及全国冰雹数据准确性各指标百分比

![](images/37f7570298e6904e1343a314be99e7018200ec7c1e2d7ee432c111f71c922341.jpg)  
Fig.5Percentage of indicators for accuracy of hail data in provinces and in the whole country   
图6各省(区、市)及全国毛毛雨数据准确性各指标百分比  
Fig.6Percentage of indicators for accuracy of drizzle data in provinces and in the whole country

$2 8 \%$ 。

全国有1999个气象站出现毛毛雨现象空报情况。全国空报率为 $1 . 7 \%$ ,其中 $9 5 . 6 \%$ 的站点空报率低于 $5 \%$ ， $4 . 1 \%$ 的站点空报率为 $5 \% \mathrm { \sim } 1 0 \%$ ， $0 . 3 \%$ 的站点空报率大于 $10 \%$ ;从各省(区、市)看，浙江和湖南的空报率最高，分别为 $4 . 8 \%$ 和 $4 . 9 \%$ ,安徽为 $3 . 2 \%$ 其余各省(区、市)均在 $3 \%$ 以内。

全国毛毛雨的分钟捕获率最低，小时捕获率次之，过程捕获率最好;各省(区、市)也是分钟捕获率最低、小时捕获率次之，过程捕获率最好，其中浙江、甘肃的分钟捕获率最好，达到 $6 0 \%$ 以上，云南、四川、广东、江西、河南、湖北、福建、贵州、重庆的分钟捕获率最差，均不足 $10 \%$ 。毛毛雨现象的识别较难，各省(区、市)差异较大，主要是因为仪器的识别方法和人工观测的标准不一致。仪器主要是以雨滴谱的大小来识别，识别的准确性取决于仪器的敏感度和识别算法。普通的一场降雨，人工观测只记为雨，而仪器观测则会出现毛毛雨和雨交替的情况。此外，由于地域的原因，北方站点出现沙尘天气易判为毛毛雨，我国南方省(区、市)的站点大雾、空气湿度大也容易判成毛毛雨。

# 3讨论

降水现象自动化观测是气象观测自动化的必然趋势，以往的仪器与人工的平行对比观测都是小范围的观测试验，在全国的代表性不足，本次平行观测是全国大范围的对比观测，是降水现象仪正式业务运行前的准备，对仪器观测数据的业务化应用具有重要意义。本次对比分析结果表明，降水现象仪对降水现象的识别达到了分钟级，对降水过程的变化较人工观测更加敏感，一个降水过程各种现象可能会交替出现，地面观测规范中15分钟以内为一个降水过程的规定，在仪器观测时无法界定；降水现象仪观测的准确率取决于算法的识别率，出现频率高的降水现象，各项捕获率指标相对较高，5种降水现象中，雨、雪出现频率高，各项捕获率指标均高于其他现象；仪器本身的维护程度对降水现象的捕获结果也会产生影响，因而存在不同程度的漏报、错报和空报，如把吹雪、柳絮、蒲公英误记为雪，沙尘误判成毛毛雨等。本次研究的结果对降水现象仪业务化运行具有重要的指导意义，今后需要加强仪器的维护保养，在气象站数据采集端进行质量控制，不断改进仪器的识别算法，并结合其他天气现象进行综合判识，以提高仪器对降水天气现象的捕获率，降低漏报率、错报率和空报率。同时，地面观测规范也需要根据仪器的使用做出相应的修订，以适应观测自动化的发展方向。

# 4结论

本文采用2017-08—2018-08全国2363个气象站降水现象平行观测对比观测数据，分别从数据完整性和准确性方面对降水现象自动观测数据进行了对比分析，得出以下结论：

（1）全国各气象站5种降水现象捕获率指标中，雨、雪、毛毛雨的过程捕获率最高，小时捕获率次之，分钟捕获率最低；雨夹雪的分钟捕获率、小时捕获率和过程捕获率均较低；冰雹的小时捕获率最高，过程捕获率次之，分钟捕获率最低。

(2）全国各气象站5种降水现象漏报率和空报率指标中，毛毛雨的漏报率最高，空报率也较高，出现空报的站点中， $8 5 \%$ 的站点人工均未观测到毛毛雨；雪的漏报率次之；冰雹的漏报率最低，但空报率较高，仪器观测到冰雹的气象站中， $8 7 \%$ 的站点人工均未观测到冰雹；雨的漏报率较低，雨夹雪的漏报率大部分在 $5 0 \%$ 以下。

（3）全国各气象站5种降水现象错报率指标中，毛毛雨、雨、雪的错报率较低，雨夹雪和冰雹的错报率较高。当出现错报时，毛毛雨、冰雹错报为雨的比例较高，雨错报成毛毛雨的比例较高，雪错报成毛毛雨和雨的比例较高，而雨夹雪则常常是毛毛雨、雨、雪交替出现。

# 参考文献(References）：

[1]中国气象局.中国灾害性天气气候图集(1961—2015)[M].北京: 气象出版社,2O18.[China Meteorological Administration.Atlas of Hazardous Weather and Climate in China(1961-2015)[M]. Beijing: China Meteorological Press,2018.]   
[2] 杜建华,郑虹晖,赵蕾,等.海南环岛高速强降雨灾害风险分析 [J].干旱气象,2020,38(4): 683-688.[Du Jianhua,Zheng Honghui,Zhao Lei,et al.Analysis on meteorological disaster risk of highway around Hainan Island caused by heavy rainfall[J]. Journal of Arid Meteorology,2020,38(4): 683-688.]   
[3]马爱华,岳大鹏,赵景波,等.近60a来内蒙古极端降水时空变 化及其影响[J].干旱区研究,2020,37(1):74-85.[Ma Aihua, Yue Dapeng, Zhao Jingbo,et al. Spatiotemporal variation and effect of extreme precipitation in inner mongolia in recent 6O years [J].Arid Zone Research,2020,37(1): 74-85.]   
[4]刘义花,李红梅,温婷婷,等.柴达木盆地夏季暴雨灾害风险区 划及其影响[J].干旱区研究,2021,38(3):757-763.[Liu Yihua, Li Hongmei, Wen Tingting,et al.Risk zoning of summer rainstorm disaster and its influence in Qaidam Basin[J]. Arid Zone Research,2021,38(3): 757-763.]   
[5]王妮,崔彩霞,刘艳.新疆暴雨洪涝灾害损失的时空特征及其影 响因素[J].干旱区研究,2020,37(2):325-330.[Wang Ni,Cui Caixia,LiuYan. Temporal-spatial characteristics and the influencing factors of rainstorm-flood disasters in Xinjiang[J].Arid Zone Research,2020,37(2): 325-330.]   
[6]任芝花,冯明农,张洪政,等.自动与人工观测降雨量的差异及 相关性[J].应用气象学报,2007,18(3):358-364.[Ren Zhihua, Feng Mingnong, Zhang Hongzheng,et al.The diference and relativity between rainfall by automatic recording and manual observation[J].Journal of Applied Meteorological Science,2007,18(3): 358-364.]   
[7]郑红,王波,周永吉,等.黑龙江省人工观测与自动观测气象数 据均一性检验[J].干旱气象,2014,32(2):292-297.[Zheng Hong,Wang Bo, Zhou Yongji,et al.Homogeneity test of artificial and automatic meteorological observation data in Heilongjiang Province[J]. Journal of Arid Meteorology,2014,32(2): 292-297.]   
[8]张宁,江志红,吴立广.江苏省自动站与基础站降水观测资料质 量分析[J].大气科学学报,2010,33(5): 606-614.[Zhang Ning, Jiang Zhihong,Wu Liguang. Quality analysis of rainfall data from automatic weather station and basic weather station and basic weather station in Jiangsu Province[J]. Transactions of Atmospheric Sciences,2010,33(5): 606-614.]   
[9]连志鸾.自动站与人工站观测记录的差异分析[J].气象,2005, 31(3):48-52.[Lian Zhiluan.Analysis and correction of observation difference between two kinds of AWS and man-observed station in Shijiazhuang[J].Meteorological Monthly,20o5,31(3): 48- 52.]   
[10] 王柏林,王经业,任芝花,等.固体降水自动化观测试验[J].气象 科技,2009,37(1): 97-101.[Wang Bolin,Wang Jingye,Ren Zhihua,et al.Automatized observational experimenton solid precipitation[J]. Meteorological Science and Technology,20o9,37(1): 97- 101.]   
[11]中国气象局.地面气象观测规范[M].北京:气象出版社,2003: 21-27.[China Meteorological Administration. The Criterion of Surface Meteorological Observation[M]. Beijing: China Meteorological Press,2003: 21-27.]   
[12] 杨宁,张晋,刘钧.雨滴谱式降水现象仪降水类型判定算法优化 探究[J].气象科技进展,2018,8(6):89-94.[Yang Ning,Zhang Jin,Liu Jun.Research on the algorithm optimization of precipitation type recognition based on raindrop spectrum precititation phenomenon instrument[J].Advances in Meteorological Science and Technology,2018,8(6): 89-94.]   
[13] 吴亚昊,周筠珺,刘黎平.雨滴谱的变化对降水估计的影响[J] 成都信息工程学院学报,2015,30(1):88-95.[Wu Yahao,Zhou Yunjun,Liu Liping.The influence of raindrop spectral changes on precipitation estimation[J]. Journal of Chengdu University of Information Technology,2015,30(1): 88-95.]   
[14] 余东升,徐青山,徐赤东,等.雨滴谱测量技术研究进展[J].大气 与环境光学学报,2011,6(6): 403-408.[Yu Dongsheng, Xu Qingshan,Xu Chidong, et al. Progress of measurement of raindrop size distribution[J]. Journal of Atmosphericand Environmental Optics, 2011, 6(6): 403-408.]   
[15] 朱文刚,李昌义,曲美慧,等.深度神经网络方法在山东降水相 态判别中的应用[J].干旱气象,2020,38(4):655-664.[Zhu Wengang,Li Changyi,Qu Meihui, et al.Application of deep neural networks method in precipitation phase identification in shandong province[J]. Journal of Arid Meteorology,2020,38(4): 655-664.]   
[16] 苗爱梅,董文晓,贾利冬,等.近30a山西不同相态降水的统计 特征及概念模型[J].干旱气象,2014,32(1):23-31.[Miao Aimei,Dong Wenxiao,Ji Lidong,et al.The statistical characteristics and conceptual model of different phase precipitation in recent 30 a in Shanxi Province[J].Journal of Arid Meteorology,2O14,32(1): 23-31.]   
[17] 陈冬冬,施丽娟,李肖霞,等.天气现象自动化观测现状调研[J] 气象科技,2011,39(5): 596-602.[Cheng Dongdong,Shi Lijuan,Li Xiaoxia,et al. Status investigation of automatic weather observation [J]. Meteorological Science and Technology,2011,39(5): 596-602.]   
[18] 马舒庆,吴可军,陈冬冬,等.天气现象自动化观测系统设计[J]. 气象,2011,37(9):1166-1172.[Ma Shuqing,Wu Kejun, Cheng Dongdong,et al. Automated present weather observing system and expreiment[J]. Meteorological Monthly,2011,37(9): 1166-1172.]   
[19] 杜波,张雪芬,胡树贞,等.天气现象仪自动化观测资料对比分 析[J].气象科技,2014,42(4): 617-623.[Du Bo,Zhang Xuefen, Hu Shuzhen, et al.Automatized observational experiment on several present weather sensors[J]. Meteorological Scienceand Technology,2014,42(4): 617-623.]   
[20] 刘平,王磊,祁生秀,等.天气现象仪降水观测分析[J].成都信息 工程大学学报,2020,35(1):104-110.[Liu Ping,Wang Lei, Qi Shengxiu,et al.Analysis of precipitation observation of weather phenomenon instrument[J]. Journal of Chengdu University of Information Technology,2020,35(1): 104-110.]

# Comparative analysis of parallel observations of precipitation phenomena in China

MA Ning12³， REN Zhihua4， WANG Yan4, LIU Na4, CAO Ning1²

(1.KeyLaboratoryforMeteorological Disaster Monitoringand Early WarningandRisk ManagementofCharacteristic   
Agriculture inAridRegions,China Meteorological Administration,Yinchuan 750o2,Ningxia,China;2.Ningxia KeyLab of Meteorological DisasterPrevention and Reduction,Yinchuan 75ooO2,Ningxia,China;3.Ningxia Meteorological Information Center,Yinchuan 750oO2,Ningxia,China;4.National Meteorological Information Center,Beijing 100081, China)

Abstract:Manual and automatic precipitation data (i.e.，paralel observation data） collcted at 2363 meteorological stations in China between August 20l7 and August 2O18 were used to analyze the integrity and accuracy of automatic observed data (singular value removed).Firstly,the comparison of the capture rate indices of rain,snow，sleet，hail，and drizzle obtained from parallel observations shows that,during the entire precipitation processrain,snow,and drizze had a higher capture rate than slet and hail had, with values of $6 6 . 9 \%$ ， $6 9 . 2 \%$ ,and $5 0 . 1 \%$ ,respectively;and the hourly capture rate of hail $( 5 1 . 8 \% )$ ）was the highest. Secondly,as for miss rate of phenomenon automatic observed, the highest value was recorded for drizzle $( 6 5 . 9 \% )$ ,the secondhighest for snow $( 3 5 . 6 \% )$ ),and the lowest for hail $( 1 6 . 2 \% )$ ). Thirdly, the misreported rates of drizzle,rain,and snow were lower than those of sleet and hail: Analogous percentages of rain were misreported as drizle, higher percentages of drizze or snow were misreported as rain,and also higher percentages of snow were misreported as drizzle or rain.The last statistical result is that the index of empty report rate shows that drizzle and hail were notcaptured at a substantial number of meteorological stations through automatic observations.Compared with manual observations,a portion of precipitation phenomena was missed, misreported,or even not captured by automatic observations using disdrometers,although these instruments have a minute level temporal resolution. Brook no delay,quality control procedures should be carried out once the data are coleted by disdrometers,the algorithm for phenomenon identification should be continuously optimized,and the comprehensive identification of precipitation phenomena should be carried out by combining other weather elements.

Keywords: precipitation phenomenon; parallel observation； data accuracy；capture rate; missrate；misreported rate