# 气候变化及人类活动对蒙古沙拐枣分布格局的影响

塞依丁·海米提²，努尔巴依·阿布都沙力克}²，李雪萍1,2，邵华³，阿尔曼·解思斯,²，阿腾古丽1,2(1．新疆大学资源与环境科学学院,新疆 乌鲁木齐830046；2.绿洲生态教育部重点实验室，新疆 乌鲁木齐830046；3．中国科学院新疆生态与地理研究所,新疆 乌鲁木齐830011)

摘要：蒙古沙拐枣（Callgonum mongolicum Turcz.）是中国荒漠植被的重要建群种,也是人工固沙造林的优选种。为了阐明气候变化及人类活动对其分布格局的影响,以119个蒙古沙拐枣地理分布信息和24个环境变量为基础，结合CMIP5的缩减全球模型数据,应用 MaxEnt模型和ArcGIS空间分析技术,分别构建不同气候情景及人类活动干扰下的蒙古沙拐枣适宜生境预测模型,定量展示未来不同气候变化情景（RCP2.6,RCP4.5,RCP8.5）和人类活动干扰下蒙古沙拐枣在我国的分布格局变化。结果表明：训练集的AUC 值为0.958,测试集的AUC 值为0.951,MaxEnt 模型的预测结果可靠;影响蒙古沙拐枣分布的主要气候因素是降水量和海拔;人类活动干扰下蒙古沙拐枣的适生比例由 $1 3 . 0 4 \%$ 下降到 $9 . 5 7 \%$ ,蒙古沙拐枣的繁殖栖息与人类活动成负相关。当前气候条件下蒙古沙拐枣总适生面积比例为 $1 3 . 0 4 \%$ ，在 $\mathrm { R C P 2 . 6 \_ R C P 4 . 5 \_ R C P 8 . 5 }$ 三种情景下至2050s，预测的总适生面积比例为 $1 3 . 3 6 \%$ 、$1 3 . 1 8 \%$ 和 $1 4 . 7 8 \%$ ;至2070s,预测的总适生面积为 $1 3 . 3 9 \%$ （204 $. 1 2 . 7 6 \%$ 和 $1 2 . 7 1 \%$ ,适生范围及面积变化趋势各有差异,各级适生区面积及总适生面积有不同程度的增减,且在高浓度排放情景（RCP8.5)下响应最为明显。

关键词：蒙古沙拐枣（Calligonum mongolicum Turcz.）；气候变化；人类活动；分布格局；中国

气候变化和人类活动对物种分布的影响是物种资源保护研究的热点之一，其中气候变化作为全球变化的一个重要方面[,主要表现在未来气温的上升,降水格局的改变以及极端气候事件的增加[2]。在区域尺度上，气候是影响物种分布的主要环境变量[3],气候因素会对物种的生长繁殖、物候、地理分布范围等产生诸多影响[4-5]。随着全球温室气体排放量的指数型增长，我国区域内气候相对于现代气候会有大幅度变化,唐继洪等[的研究表明,在BCC-CSM1-1气候模式下,2050s年均气温上升$1 . 5 \sim 3 . 5 \ \mathrm { { ‰ } } , 2 0 7 0 \mathrm { { s } }$ 年均温上升 $1 . 5 \sim 4 \mathrm { ~ } ^ { \circ } \mathrm { C } \mathrm { ~ } , 2 0 7 0 \mathrm { s }$ 气温上升幅度更大，全国大部分地区的降水量会有所增加，但是西部地区降水量将会减少。而人类活动及其造成的环境条件会对植物多样性造成严重的影响，人类活动范围、方式、强度的不同产生了不同的土地利用类型，耕地、林地、灌丛、居民用地分别产生了不同的交界面类型，而交界面会对植物的空间分布和多样性产生直接影响[7]。因此,将空间化的未来气候因子和人类活动因子作为预测变量，可以定量的展示未来气候变化及人类活动对蒙古沙拐枣潜在分布范围及空间格局的影响。

蒙古沙拐枣（Calligonum mongolicum Turcz.）属于沙拐枣属刺果组，为落叶灌木,果期为7一8月，株高差异较大，在流动沙丘上常常形成 $1 \sim 1 . 5 \mathrm { ~ m ~ }$ 高的灌丛,起到很好的防风固沙作用[8]。其不仅具有耐干旱、耐盐碱、耐高温、耐瘠薄、抗风蚀和适应流沙的特性，而且还具有很强的繁殖能力，是人工固沙造林的优选物种，在我国西北干旱、半干旱地区被广泛用于防风固沙和生态修复及恢复工程中[8-9]。蒙古沙拐枣也是沙拐枣属植物在我国分布最广的种，分布范围自内蒙古的锡林浩特至新疆哈密、吐鲁番、罗布泊南缘、若羌东面、奇台和乌鲁木齐以东的达坂城[8]。在沙漠治理、生态环境保护与恢复、畜牧业发展、观赏、中医学制药研究等方面具有重要的应用价值[10]

研究荒漠植物对气候变化的响应，量化人类活动对物种分布格局的影响是国内外学者关注的热点问题。目前，对蒙古沙拐枣的研究主要集中在风沙环境下自然更新策略[1]、同化枝解剖结构与生态因子关系[12]、抗旱性比较[13]、光合及荧光特性比较[14]等方面,未发现气候变化及人类活动对蒙古沙拐枣分布格局影响的研究报道。鉴于蒙古沙拐枣是干旱区荒漠植被的重要建群种和人工固沙造林的优选种,也是沙拐枣属植物在我国分布最广的种(1)本文结合CMIP5的缩减全球模型数据，应用MaxEnt模型和ArcGIS空间分析技术，分别构建了现代及未来不同气候情景下蒙古沙拐枣的适宜生境预测模型，并与其在人类活动干扰下的分布格局相比较，旨在揭示全球气候变化和人类活动对蒙古沙拐枣潜在分布的影响，为固沙先锋种蒙古沙拐枣的野生抚育及引种栽培提供数据支持，为沙拐枣属植物的保护与科学研究提供理论依据。

# 数据与方法

# 1.1 物种分布数据的获取

蒙古沙拐枣在国内的地理分布数据主要通过以下方式获得： $\textcircled{1}$ 新疆境内的分布数据来源于第二次全国植物资源普查新疆片区的调查工作。调查点主要有哈密伊乌县、吐鲁番鄯善县、巴音郭楞库尔勒及若羌县、奇台、乌鲁木齐达坂城、奎屯和精河等，划定蒙古沙拐枣的果期为野外考察期，于2015—2017 年7—8月在调查点进行野外实地调研，发现蒙古沙拐枣即记为“存在点（presence）”，用GPS记录经纬度和海拔。 $\textcircled{2}$ 查找国内外公开发表的期刊论文、学位论文和会议论文，查阅相关植物文献资料和书籍。$\textcircled{3}$ 查看中国数字植物标本馆（CVH)和中国植物图像库（PPBC）。 $\textcircled{4}$ 查看国家自然科技资源平台教学资源共享平台（http://muh.scu.edu.cn）中的34所标本馆[15],共获得119 个有效的蒙古沙拐枣地理坐标信息（图1）。

# 1.2 环境变量数据及预处理

本文共选取24个环境变量，包括2个代表人类活动的对比干扰因子、19个生物气候因子和3个地形因子。其中，现代(1960一1990 年的均值)和未来气候情景 2050s（2041—2060 年的均值）和2070s(2061一2080 年的均值)的19个生物气候变量均来源于Worldclim 数据集（http://www.worldclim.org/）〔16],该数据集分辨率为 $1 ~ \mathrm { k m }$ ,由19 个降水量、气温的极值和变化范围的变量构成，根据中国行政区地图对下载的全球气候数据进行影像配准、裁剪和叠加。海拔高程数据(DEM)从美国国家航空航天局发布的全球数字高程模型（SRTMv4.1,http：//datamirror.csdb.cn/）下载,空间分辨率为100 m[17]坡向和坡度利用ArcToolbox工具箱的表面分析工具根据DEM生成。人类活动强度数据（模型中称为hfp_China）来源于国际地球科学信息网络中心（CIESIN）的人类足迹（human footprint）数据层[18]对全球人类足迹的原始数据进行坐标与格式转换等处理，再利用ArcGIS根据中国行政区地图对全球人类足迹中的数据进行影像裁剪、配准和叠加[19]。土地利用数据(模型中称为LUCC)选用2015年Land-sat TM 影像，下载地址为http://www.resdc.cn/（中国科学院资源环境科学数据中心），对其进行重分类、投影变换等处理。

![](images/f499a807ced3906f25182d4805b86af23083baa4b65a5ff644ee9db7edad837c.jpg)  
图1蒙古沙拐枣在中国的地理分布Fig.1Geographical distribution of Calligonummongolicum Turcz．in China

本文选取人类活动强度数据和土地利用数据作为对比干扰变量代表人类活动（表1），未来气候情景采用由中国气象局开发的BCC-CSM1-1模式下的3种不同气候变化情景数据（RCP2.6，RCP4.5，RCP8.5）〔20]。RCPs情景与大家经常采用的 SRES排放情景相比，更加细致地考虑了应对气候变化的各种策略对未来温室气体排放的影响，预估结果更加科学和准确[6。本文选取的 RCP2.6、RCP4.5、RCP8.5气候情景分别代表低、中、高3种 $\mathrm { C O } _ { 2 }$ 浓度排放情景[20] 。

在建模过程中为了避免变量之间存在自相关和多重线性重复等问题,参考Worthington 等[21]、王茹琳等[22]的方法对环境变量进行了筛选,用2个对比干扰变量外的其他22个环境变量构建初始模型，采用皮尔逊相关系数检验变量间的多重共线性[23],对于相关性较高的变量进行单因子建模，运行刀割法(Jackknife)测定其对模型预测的贡献率大小，以此剔除对物种分布贡献率较小的环境变量，最终确定13个环境变量作为预测蒙古沙拐枣适生区的环境数据(表1）。

表1环境变量描述及相对贡献率  

<html><body><table><tr><td>变量分类</td><td>变量名称</td><td>描述</td><td>贡献率/%</td></tr><tr><td>生物气候变量</td><td>BIO1</td><td>年平均温度</td><td>0.6</td></tr><tr><td></td><td>BIO2</td><td>平均周温度变化范围</td><td>1.4</td></tr><tr><td></td><td>BI05</td><td>极端最高气温</td><td>1.1</td></tr><tr><td></td><td>BIO10</td><td>最湿季平均温度</td><td>1.6</td></tr><tr><td></td><td>BIO11</td><td>最冷季平均温度</td><td>1.0</td></tr><tr><td></td><td>BIO12</td><td>年降水量</td><td>0.8</td></tr><tr><td></td><td>BI013</td><td>最湿月降水量</td><td>5.6</td></tr><tr><td></td><td>BIO15</td><td>降水量的季节性变化</td><td>0.6</td></tr><tr><td></td><td>BIO18</td><td>最热季降水量</td><td>61.9</td></tr><tr><td></td><td>BIO19</td><td>最冷季降水量</td><td>9.6</td></tr><tr><td>地形变量</td><td>alt</td><td>海拔</td><td>13.0</td></tr><tr><td></td><td>aspect</td><td>坡向</td><td>0.2</td></tr><tr><td rowspan="3">对比干扰变量</td><td>slope</td><td>坡度</td><td>2.4</td></tr><tr><td>hfp_China</td><td>人类活动强度</td><td>18.3</td></tr><tr><td>lucc</td><td>土地利用</td><td>0.6</td></tr></table></body></html>

# 1.3矢量图及软件来源

本文所用的中国行政区划矢量图来源于国家基础地理信息系统网站，地址为http://nfgis.nsdi.gov.en。MaxEnt 模型是由 Philliips 于2004 年构建的用于预测物种分布的技术方法[24],目前在生态学领域中被广泛使用[25]。本文所使用的 MaxEnt 软件版本是3.3.3k[26-28]

# 1.4模型构建及分析

将蒙古沙拐枣地理分布数据和环境变量数据导入MaxEnt中，随机选取 $7 5 \%$ 的蒙古沙拐枣分布点作为训练集（testingdata），剩余 $2 5 \%$ 的蒙古沙拐枣分布点作为测试集（trainingdata）[29]。运行刀割法测定各环境变量所占的权重，并创建环境变量响应曲线,模型的其余参数均选择默认值。本文模型模拟结果的评价标准规定为受试者操作特征曲线（receiveroperatingcharacteristic curve，ROC）下面积值[30],即 AUC 值(area under curve，AUC）,不同的

Tab.1 Descriptions and relative contribution rates ofenvironmentvariables   
表2AUC评价标准  
Tab.2The evaluation criteria of AUC   

<html><body><table><tr><td>AUC取值范围</td><td>评价标准</td></tr><tr><td>0.5≤AUC<0.6</td><td>失败</td></tr><tr><td>0.6≤AUC<0.7</td><td>较差</td></tr><tr><td>0.7≤AUC<0.8</td><td>一般</td></tr><tr><td>0.8≤AUC<0.9</td><td>好</td></tr><tr><td>0.9≤AUC<1.0</td><td>优秀</td></tr></table></body></html>

AUC值代表了不同预测结果（表2）。

将MaxEnt模型输出的结果导入ArcGIS软件中进行生境适宜性分析，首先通过ArcGIS进行重分类操作[31],并根据专家经验法及野外调查得到的实际情况，将蒙古沙拐枣生境分布区划分成4个等级：0\~0.1为非适生区， $0 . \ 1 \sim 0 . \ 3$ 为低适生区，0.3\~0.5 为中适生区, $0 . 5 \sim 1 . 0$ 为高适生区[32]。运用ArcGIS的 SDM工具箱和统计工具Zonal计算4类分区的面积，分析比较人类活动干扰下及不同气候变化情景下各级适生区的面积变化。

# 2结果与分析

# 2.1 模型预测结果评价

受试者操作特征曲线下面积值（AUC)越大，表示与随机分布相距越远，选取的环境变量与预测的物种地理空间分布模型之间的相关性越大，即表示模型的预测效果越好(33-34]。本文中训练数据集和测试数据集的AUC值分别为0.958和0.951（图2），表明MaxEnt模型的预测结果可靠，此次预测的地理分布结果与实际分布区域的相符度较高，预测结果可用于蒙古沙拐枣的适生区划。在模型中运行刀割法，运行结果显示出各环境变量对蒙古沙拐枣适宜生境预测的相对贡献率（表1），BIO18最热季降雨量的贡献率最高 $( 6 1 . 9 \%$ )，是影响蒙古沙拐枣分布的决定因子；alt海拔的贡献率为 $1 3 \%$ ，仅次于最热季降雨量，是影响蒙古沙拐枣分布的次要因子;其次，BIO19最冷季降水量 $( 9 . 6 \%$ ），BIO13最湿月降水量 $( 5 . 6 \%$ )的贡献率也都超过 $5 \%$ ，以上4个因子的贡献率总和高达 $9 0 . 1 \%$ ,是影响蒙古沙拐枣分布的主导环境因子。

![](images/2fb6d2ae7e2dece5a49735d7a7d3282d570247bf3febb161ecd916af3edbe73a.jpg)  
图2蒙古沙拐枣潜在分布预测结果的ROC 验证 Fig.2ROC verification of predicted results of potential distribution of Calligonum mongolicum Turcz.

# 2.2蒙古沙拐枣在当前气候及人类活动干扰下的适生区预测

由预测结果（图3)和统计分析可知（表3），蒙古沙拐枣在我国的适生范围主要集中在内蒙古、宁夏、甘肃、青海、新疆等省份。其中高适生区面积为$6 3 . 9 9 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,主要位于内蒙古中部和西部、宁夏北部、甘肃北部、青海中部、新疆中部和东部。中适生区面积为 $6 1 . 6 1 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,主要位于高适生区的边缘及四周，总适生面积为 $1 2 5 . 6 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 。人类活动干扰下，各级适生区面积不同程度减小，高适生区面积减少 $3 9 . 8 \%$ ，为 $3 8 . 5 4 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,中适生区面积减少 $1 2 . 8 \%$ ，为 $5 3 . 7 0 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ，总适生面积为$9 2 . 2 4 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 。人类活动干扰下蒙古沙拐枣适宜生境大幅度缩减，适生比例由 $1 3 . \ 0 4 \%$ 下降到$9 . 5 7 \%$ 。

![](images/c17b5f376c75213978b953e9a1de4aab7edf46475c98fb8ba3fc545950706f44.jpg)  
图3蒙古沙拐枣在当前气候(a)及人类活动(b)干扰下的适生区预测  
Fig.3PredictedsuitablezonesofCallgonum mongolicum Turcz.undercurrentclimate（a）anddisturbanceofhumanactivities(l

表3蒙古沙拐枣在当前气候及人类活动干扰下的适生区面积 Tab.3The area of suitable habitats of Callgonum mongolicum Turcz.under current climate and disturbance of human activities $/ 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$   

<html><body><table><tr><td>类型</td><td>高适生区面积</td><td>中适生区面积</td><td>低适生区面积</td><td>非适生区面积</td><td>总适生面积(比例)</td></tr><tr><td>无人类活动干扰</td><td>63.99</td><td>61.61</td><td>84.49</td><td>753.31</td><td>125.6 (13.04%)</td></tr><tr><td>有人类活动干扰</td><td>38.54</td><td>53.70</td><td>82.09</td><td>789.08</td><td>92.24 (9.57%)</td></tr></table></body></html>

# 2.3不同气候变化情景下蒙古沙拐枣空间分布格局变化

不同气候变化情景下，蒙古沙拐枣在我国的适生范围未发生大幅度变化（图4），但各级适生区面积及总适生面积有不同程度的增减（表4）。在RCP2.6（低 $\mathrm { C O } _ { 2 }$ 浓度排放)情景下，总适生面积呈波动增加的趋势，且变化幅度较小。在RCP4.5（中$\mathrm { C O } _ { 2 }$ 浓度排放）、RCP8.5（高 $\mathrm { C O } _ { 2 }$ 浓度排放)情景下，总适生面积呈先增后减的趋势，且RCP8.5情景下的变化幅度较RCP4.5情景更为明显。当前气候条件下蒙古沙拐枣总适生面积比例为 $1 3 . 0 4 \%$ ，在

RCP2.6、RCP4.5、RCP8.5情景下，2050s预测的总适生面积比例为 $1 3 . 3 6 \%$ ） $1 3 . 1 8 \%$ ） $1 4 . 7 8 \%$ ，2070s预测的总适生面积比例为13. $3 9 \%$ 、12. $76 \%$ 、$1 2 . 7 1 \%$ 。3种气候情景下2050s蒙古沙拐枣的适宜生境均呈增加趋势，可以说明到21世纪中叶蒙古沙拐枣在我国的分布范围会有一定程度的扩增。分析面积变化率（图5）发现，高适生面积在RCP2.6和RCP4.5情景下呈先增后减的趋势，在RCP8.5情景下呈持续下降趋势。总适生面积在RCP4.5和RCP8.5情景下呈先增后减的趋势，在RCP2.6情景下呈持续上升趋势。RCP8.5情景下面积变化率最为明显，RCP4.5情景次之，而RCP2.6情景下较为平稳。说明在未来气候变化情景下，蒙古沙拐枣的分布范围及面积变化趋势各有差异，且在高浓度排放情景下响应最为敏感

![](images/b956d4ecf881afedd1c58632f430c829931e64654ede8d032af07a3796904d90.jpg)  
图4不同气候变化情景下2050s和2070s我国蒙古沙拐枣适生区分布预测

表4不同气候变化情景下蒙古沙拐枣在中国的适生区面积  
Tab.4The areas of suitable habitats of Calligonum mongolicum Turcz.in China under diferent   
  

<html><body><table><tr><td colspan="7">climatic conditions</td></tr><tr><td>气候变化情景</td><td></td><td>高适生区面积</td><td>中适生区面积</td><td>低适生区面积</td><td>非适应区面积</td><td>总适生面积(比例)</td></tr><tr><td>当前</td><td></td><td>63.99</td><td>61.61</td><td>84.49</td><td>753.31</td><td>125.6 (13.04%)</td></tr><tr><td>RCP2. 6</td><td>2050s</td><td>69.72</td><td>58.95</td><td>94.42</td><td>740.31</td><td>128.67(13.36% )</td></tr><tr><td rowspan="3">RCP4.5</td><td>2070s</td><td>66.79</td><td>62.23</td><td>83.34</td><td>751.04</td><td>129.02(13.39%)</td></tr><tr><td>2050s</td><td>64.82</td><td>62.18</td><td>85.66</td><td>750.74</td><td>127.00(13.18%)</td></tr><tr><td>2070s</td><td>61.10</td><td>61.90</td><td>93.51</td><td>746.90</td><td>123.00(12.76% )</td></tr><tr><td rowspan="2">RCP8.5</td><td>2050s</td><td>61.37</td><td>81.06</td><td>87.71</td><td>733. 25</td><td>142.44(14.78% )</td></tr><tr><td>2070s</td><td>58.00</td><td>64.46</td><td>91.28</td><td>749.67</td><td>122.46(12.71%)</td></tr></table></body></html>

![](images/053ba1a62cb9c59e8d6cb88bfa1e17c708822e4ac741f3816343730ffecb64f7.jpg)  
图5不同气候变化情景下蒙古沙拐枣的高适生和总适生面积变化率 Fig.5The change rate of the high suitable and total suitable areas of Calligonum mongolicum Turcz.under different climatic conditions

# 3讨论与结论

将模型预测的蒙古沙拐枣适宜生境预测结果与实际分布点进行比较，发现其记录分布点都分布于高适生区内，数据可信度较高。采用刀割法运行结果显示，最热季降水量、海拔、最冷季降水量、最湿月降水量等4个因子的贡献率总和为 $9 0 . 1 \%$ ,是影响蒙古沙拐枣分布的主导环境因子。其中最热季降水量、最冷季降水量、最湿月降水量为代表降水量的气候因素，海拔为地形因素，由此可见影响蒙古沙拐枣分布概率的主要气候因素是降水量，地形因素是海拔。同时降水量会对土壤湿度产生直接的影响，这也间接证明了吴建国等[35认为蒙古沙拐枣的种子发芽主要受温度和土壤湿度影响的研究结论。对于其他沙拐枣属植物的研究结果表明[32],影响塔里木、库尔勒、英吉沙、若羌等沙拐枣属植物潜在分布的主要气候因素也是降水量，但影响沙拐枣属植物分布的主要气候因素是否是降水量有待于进一步验证。在加入代表人类活动的两个干扰因子后运行刀割法，其结果显示人类活动强度和土地利用的贡献率分别为 $1 8 . 3 \%$ 和 $0 . 6 \%$ ,贡献率总和为 $1 8 . 9 \%$ ，且人类活动干扰下适生比例由 $1 3 . 0 4 \%$ 下降到$9 . 5 7 \%$ 。可见,人口压力、土地利用、基础设施建设、交通运输等一系列的人类活动对蒙古沙拐枣的繁殖栖息造成了一定程度的负面影响，蒙古沙拐枣的繁殖栖息与人类活动成负相关。

蒙古沙拐枣在我国的适生范围主要集中在内蒙古、宁夏、甘肃、青海、新疆等省份，在不同气候变化情景下也未发生大幅度变化。将当代气候及未来不同气候变化情景下构建的蒙古沙拐枣适宜生境预测结果与中国沙漠分布图对比发现，蒙古沙拐枣在当代及未来气候条件下均分布在塔克拉玛干沙漠、古尔班通古特沙漠、库姆塔格沙漠、柴达木沙漠、巴丹吉林沙漠、腾格里沙漠、乌兰布和沙漠、库布齐沙漠和毛乌素沙地及其周围，包括了中国所有的沙漠和部分潜在沙化地区，而其又作为干旱区荒漠植被的重要建群种和人工固沙造林的优选种，说明可以对蒙古沙拐枣在现代及未来气候情景下的适宜生境进行人工栽培和野生抚育，扩大蒙古沙拐枣的种群数目和分布范围，以应对和减少气候变化对其的影响[36],并将其广泛应用于沙漠防控与治理工作中。不同气候情景下蒙古沙拐枣的适生范围虽未发生大幅度变化，但各级适生区面积及面积变化趋势各有差异，表现出不同程度的增减，且在高浓度（RCP8.5）排放情景下响应最为敏感。3种气候情景下2050s蒙古沙拐枣的适宜生境均呈增加趋势，可以说明到21世纪中叶蒙古沙拐枣在我国的分布范围会有一定程度的扩增，这也证实了刘娜等对蒙古沙拐枣分布范围外扩的猜测。

本文仅探讨了气候因素、地形因素及人类活动对蒙古沙拐枣分布范围及空间格局的影响，而未考虑河流、生物相互作用、种间竞争等因素。并且预测是以当前蒙古沙拐枣的分布点作为预测变量，未考虑未来实际分布点的变化。在今后的研究中需要进一步考虑环境变量的选取及分布点的变化，并建议在今后的土地利用规划、基础设施建设、交通运输、道路建设和自然资源管理等方面给予沙拐枣属植物更多关注。

参考文献（References）:   
[1]Parmesan C,Yohe G.A globally coherent fingerprint of climate change impacts across natural systems[J]. Nature,2003,421 (6 918) :37 -42.   
[2]Edwards P N.A Vast Machine: Computer Models,Climate Data, and the Politics of Global Warming[M].Cambridge:MIT Press, 2010.   
[3]Pounds JA,Bustamante M R,Coloma L A,et al. Widespread amphibian extinctions from epidemic disease driven by global warming[J].Nature,2006,439(7 073）:161 -167.   
[4]Kozak K H,Graham C H,Wiens JJ. Integrating GIS-based environmental data into evolutionary biology[J].Trends in Ecology & Evolution,2008,23(3）:141-148.   
[5]苏志豪,潘伯荣,卓立,等.未来气候变化对特有物种沙生怪柳 分布格局的影响及其保护启示[J].干旱区研究,2018,35 (1）:150-155.[Su Zhihao,Pan Borong,Zhuo Li,et al.Impact of future climate change on distribution pattern of Tamarix taklamakanensis and its conservation revelation[J].Arid Zone Research, 2018,35(1) :150 -155.]   
[6]唐继洪,程云霞,罗礼智,等.基于 Maxent 模型的不同气候变化 情景下我国草地螟越冬区预测[J].生态学报,2017,37（14）： 4 852-4863.[Tang Jihong,Cheng Yunxia,Luo Lizhi,et al. Maxent-based prediction of overwintering areas of Loxostege sticticalis in China under diferent climate change scenarios[J].Acta Ecologica Sinica,2017,37(14):4 852 -4 863.]   
[7」高俊峰.北京东灵山地区人类活动对植物多样性分布的影响 研究［D].北京：北京林业大学,2007.[Gao Junfeng.Ecological Effects of Human Disturbance on Plant Diversity Distribution in Dongling Mountain,Beijing[D].Beijing:Beijing Forestry University,2007.]   
[8]刘娜,冯缨,管开云,等.蒙古沙拐枣（Calligonum mongolicum） 的地理分布与气候关系[J].干旱区研究,2015,32(4)：934- 940.[Liu Na,Feng Ying,Guan Kaiyun,et al. Relation between geographic distribution of Calligonum mongolicum and climatic factors[J].Arid Zone Research,2015,32(4）:934-940.]   
[9]师玮,潘伯荣,段士民,等.蒙古沙拐枣（Calligonum mongolicum)与其相关种的果实形态差异性分析〔J].中国沙漠， 2011,31(1）:121-128.[Shi Wei,Pan Borong,Duan Shimin,et al.Difference of fruit morphological characters of Calligonum mon golicum and related species[J]. Journal of Desert Research,2011, 31(1):121-128.]   
[10]刘惠兰,马德滋.蒙古沙拐枣同化枝的解剖观察[J].植物学 报,1985,3(1):45-46.[Liu Huilan,Ma Dezi.Anatomical observation of assimilating branches of Calligonum mongolicum[J]. Chinese Bulltin of Botany,1985,3（1）:45-46.]

[11］樊宝丽.风沙环境下沙拐枣（Calligonummongolicum）自然更新 策略研究［D].兰州：兰州大学，2017.［FanBaoli.Natural Regeneration Strategies of Calligonum mongolicum under Different Aeolian Environments[D].Lanzhou:Lanzhou University,2017.] [12]赵小仙，李毅，苏世平，等.6个种群蒙古沙拐枣同化枝解剖结 构及与地理生态因子的关系[J].干旱区资源与环境，2015，29 (2）:55-6O.[Zhao Xiaoxian,Li Yi,Su Shiping,et al.Anatomical structure of assimilating shoots of Calligonum mongolicum from six populations and its relationship with geo-ecological factors[J]. Journal of Arid Land Resources and Environment,2015,29（2）: 55-60.]

[13]赵小仙，李毅，苏世平，等.3个地理种群蒙古沙拐枣同化枝解 剖结构及抗旱性比较[J].中国沙漠，2014，34（5）：1293- 1 300.［Zhao Xiaoxian,Li Yi,Su Shiping,et al.Drought resistance analysis based on anatomical structures of assimilating shoots of Calligonum mongolicum from three geographic populations[J]. Journal of Desert Research,2014,34(5):1293-1 300.]

[14]种培芳，李毅，苏世平.干旱胁迫下不同地理种源蒙古沙拐枣 （Calligomummongolicum）光合及荧光特性比较[J].中国沙 漠,2014,34(5）:1 301-1 306.[Zhong Peifang,Li Yi,Su Shiping.The responses of photosynthetic and chlorophyll eluorescence to water stress in three provenances of Calligomum mongolicum [J].Journal ofDesert Research,2014,34(5）:1301-1306.] [15]张东方，张琴，郭杰，等.基于MaxEnt模型的当归全球生态适 宜区和生态特征研究[J].生态学报，2017，37（15)：5111- 5120.[Zhang Dongfang,Zhang Qin,Guo Jie,et al.Research on theglobal ecological suitability and characteristics of regionswith Angelica sinensis based on the MaxEnt model[J].Acta Ecologica Sinica,2017,37(15):5111-5120.]

[16]刘艳，赵正武.基于最大熵模型模拟气候变化下中国两个沼泽 藓类属的潜在分布[J].应用与环境生物学报，2017（5）： 792-799.[Liu Yan,Zhao Zhengwu.Modeling potential distributions of two wetland moss genera in China under climate change based on a maximum-entropy（Maxent）model[J].Chinese Journal ofApplied and Environmental Biology,2017(5）:792-799.] [17」刘艳，阿提古丽·毛拉，沙毕热木·斯热义力，等.气候变化下 耐旱藓类连轴藓属在新疆的分布模拟[J].西北植物学报， 2017,37(9）:1 881-1887.[Liu Yan,Atigul Molla,Sabiram Esrayl,et al.Modeling potential distributions of the desiccation-tolerant moss genus Schistidium in Xinjiang under climate change[J]. ActaBotanicaBoreali-Occidentalia Sinica,2017,37(9）:1 881 - 1 887.]

[18]迈迪娜·吐尔逊.意大利苍耳在新疆的适生区分析研究[D].乌鲁木齐：新疆大学,2017.［Maidina Tursun.Studies on Suit-ableGeographieDistributionofXanthiumitalicumMorettiin Xin-jiang[D].Urumqi:XinjiangUniversity,2017.]

[19]Anderson RP,Raza A.The effect of the extent of the study region on GIS models of species geographic distributions and estimates of niche evolution:Preliminary tests with montane rodents （genus

Nephelomys）in Venezuela[J].Journal of Biogeography,2010,37

(7):1 378 -1 393.   
[20］应凌霄,刘晔,陈绍田,等.气候变化情景下基于最大熵模型的 中国西南地区清香木潜在分布格局模拟[J].生物多样性, 2016,24(4）:453-461.[Ying Lingxiao,Liu Ye,Chen Shaotian, et al.Simulation of the potential range of Pistacia weinmannifolia in Southwest China with climate change based on the maximumentropy（Maxent）model[J].Biodiversity Science,2016,24（4）： 453 -461. ]   
[21]Worthington TA,Zhang T,Logue D R,et al.Landscape and flow metrics affecting the distribution of a federally-threatened fish:Improving management,model fit,and model transferability[J].Ecological Modelling,2016,342:1-18.   
[22］王茹琳,李庆,何仕松,等.中华猕猴桃在中国潜在分布及其对 气候变化响应的研究[J].中国生态农业学报,2018,26(1)： 27-37.[Wang Rulin,Li Qing,He Shisong,et al.Potential distribution of Actinidia chinensis in China and its predicted response to climate change[J]. Chinese Journal of Eco-Agriculture,2018,26 (1) :27 -37.]   
[23]Yang XQ,Kushwaha S P S,Saran S,et al.Maxent modeling for predicting the potential distribution of medicinal plant,Justicia adhatoda L.in Lesser Himalayan foothills[J].Ecological Engineering,2013,51:83 -87.   
[24]Philips SJ,Dudik M.Modeling of species distributions with Maxent:New extensions and a comprehensive evaluation[J].Ecography,2008,31(2) :161-175.   
[25]Padalia H,Srivastava V,Kushwaha SP S.Modeling potential invasion range of alien invasive species,Hyptis suaveolens（L.）Poit. in India:Comparison of MaxEnt and GARP[J].Ecological Informatics,2014,22:36 -43.   
[26]Ha H,Heumann B W,Liesch M,et al. Modelling potential conservation easement locations using physical and socio-economic factors:A case study from south-east Michigan[J].Applied Geography,2016,75:104-115.   
[27]Vinod P N,Chandramouli PN,Koch M.Estimation of nitrate leaching in groundwater in an agriculturally used area in the State Karnataka,India,using existing model and GIS[J].Aquatic Procedia,2015,4:1 047 -1 053.   
[28]Bjornlie D D,Thompson D J,Haroldson M A,et al. Methods to estimate distribution and range extent of grizzly bears in the Greater Yellowstone Ecosystem[J].Wildlife Society Bulletin,2014,38 (1) :182 -187.   
「）文娼 防计 丁古&竿 利用MAVFNT颈测工半需雪症巾

国的适生区[J].植物保护,2009,35（2）:32-38.[Zhao Wenjuan,Chen Lin,Ding Kejian,et al.Prediction of potential geographic distribution areas of the maize downy mildew in China by using MAXENT[J].Plant Protection,2009,35(2）:32-38.]   
[30]段居琦,周广胜.中国双季稻种植区的气候适宜性研究[J].中 国农业科学,2012,45(2）:218-227.[Duan Juqi,Zhou Guangsheng. Climatic suitability of double rice planting regions in China [J].Scientia Agricultura Sinica,2012,45(2）:218-227.]   
[31］吴显坤,南程慧,汤庚国,等.气候变化对浙江楠潜在分布范围 及空间格局的影响[J].南京林业大学学报（自然科学版）， 2016,40(6):85-91.[Wu Xiankun,Nan Chenghui,Tang Gengguo,et al. Impact of climate change on potential distribution range and spatial patern of Phoebe chekiangensis[J].Journal of Nanjing Forestry University（Natural Sciences Edition）,2016,40（6）: 85-91.]   
[32]刘娜,冯缨,管开云.沙拐枣属(Calligonum L.）植物在中国的 潜在分布区预测[J].干旱区资源与环境,2016,30(3）：112- 120.[Liu Na,Feng Ying,Guan Kaiyun.Potential distributionprediction of Caligonum L.in China[J].Journal of Arid Land Resources and Environment,2016,30(3）:112-120.]   
[33]王运生,谢丙炎,万方浩,等.相似穿孔线虫在中国的适生区预 测[J].中国农业科学,2007,40（11）:2 502-2 506.[Wang Yunsheng,Xie Binyan,Wan Fanghao,et al.Potential geographic distribution of radopholus similis in China[J].Scientia Agricultura Sinica,2007,40(11):2 502-2 506.]   
[34］张颖,李君,林蔚,等.基于最大熵生态位元模型的入侵杂草春 飞蓬在中国潜在分布区的预测[J].应用生态学报,2011,22 (11）:2 970-2 976.[Zhang Ying,Li Jun,Lin Wei,et al.Prediction of potential distribution area of Erigeron philadelphicus in China based on MaxEnt model[J]. Chinese Journal of Applied Ecology,2011,22(11) :2 970 -2 976.]   
[35]吴建国,甚伟,吕佳佳.气温和土壤湿度变化对3种典型荒漠 植物种子发芽的影响[J].环境科学研究,2009,22（3）：343- 350.[Wu Jianguo,Chang Wei,Lv Jiajia.The effects of change in temperature and soil moisture on the seed germination of three typical desert plants[J].Research of Environmental Sciences,2009, 22(3) :343 -350.]   
[36］张殷波,高晨虹,秦昊.山西翅果油树的适生区预测及其对气 候变化的响应[J].应用生态学报,2018,29（4）：1156- 1 162.[Zhang Yinbo,Gao Chenhong,Qin Hao.Prediction of suitable distribution of Elaeagnus mollis in Shanxi Province,China and its response to climate change[J].Chinese Journal of Applied Ecology,2018,29(4):1156-1 162.]

# Effects of Climate Change and Human Activities on the Distribution Pattern of Calligonum mongolicum Turcz.

SayitHamit²，urbabushalih²2，Xue-ping，Ha， Arman Jiesisi $^ { 1 , 2 }$ ，Ateng Guli1.2 (1.College of ResourcesandEnvironmental Sciences，Xinjiang University，Urumqi 83o046,Xinjiang,China;   
2. Key Laboratoryof Oasis Ecologyof Ministryof Education，Xinjiang University，Urumqi 830046,Xinjiang,China;   
3. Xinjiang Instituteof Ecologyand Geography，Chinese Academy of Sciences， Urumqi 830011， Xinjiang,China)

Abstract:Callgonum mongolicum Turcz. isan important species of vegetation in desert，and is also a preferred species forartificial sand-fixation and aforestation.This study wasbased onthe geographical distributionof 119 geographical distribution data of $C$ . mongolicum and 24 environmental variables. The effects of climate change and human activities on the distribution pattern of $C$ . mongolicum were elucidated using the CMIP5 reduction global model data.The MaxEnt model and ArcGIS spatial analysis means were used to develop the models of predicting suitable habitats of $C$ .mongolicum under diferent climatic conditions and human activities so as to quantitatively demonstrate the diferent climate change scenarios （RCP2.6，RCP 4.5，RCP8.5）and the change of distribution pattern of $C$ .mongolicum in China under climate change.The results showed thatthe prediction accuracy of the model was relatively high(the AUC valuesof the training data set and the test data set were O.958 and O.951 respectively). The main climatic factors affcting the distribution of $C$ .mongolicum were precipitation， topographical factors and elevation，and the disturbance of human activities made the suitable proportion of $C$ . mongolicum decrease from （20 $1 3 . 0 4 \%$ to $9 . 5 7 \%$ . The breeding habitat of $C$ .mongolicum was negatively correlated with human activities. Under current climatic conditions，the proportions of total suitable area of $C$ . mongolicum was $1 3 . 0 4 \%$ ；in the three scenarios of RCP2.6，RCP4.5 and RCP8.5，the predicted proportions of total adaptive area would be $1 3 . 3 6 \%$ ， $1 3 . 1 8 \%$ and $1 4 . 7 8 \%$ up to the 205Os，and they would be $1 3 . 3 9 \%$ ， $1 2 . 7 6 \%$ and $1 2 . 7 1 \%$ up to the 2070s．The change of scope and area of adaptation is different.

Key words:Caligonum mongolicum Turcz.；climate change；human activity；distribution pattern；China