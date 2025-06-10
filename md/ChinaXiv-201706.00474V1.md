# DOI:10.5846/stxb201603180488

艾科拜尔·木哈塔尔,热木图拉·阿卜杜克热木,马合木提·哈力克.基于生态位模型的艾比湖国家级自然保护区马鹿生境评价.生态学报，2017，37(11)：3919-3925.  
AkbarMuhtarullu,utalikesbiatliuelsiiakoalturcEcologica Sinica,2017,37(11） :3919-3925.

# 基于生态位模型的艾比湖国家级自然保护区马鹿生境评价

艾科拜尔·木哈塔尔，热木图拉·阿卜杜克热木，马合木提·哈力克"

新疆大学生命科学与技术学院，资源生物研究所，乌鲁木齐830046

摘要：生境评价和预测是对濒危物种进行有效保护的基础。通过2013年9月和2014年10月对新疆艾比湖国家级自然保护区开展2次秋季野外调查共收集了92处马鹿(Ceruselaphus)出现数据,利用马鹿出现数据作为分布点数据,选取地形、植被类型和气候因子3类23种因子作为生境变量,利用MAXENT生态位模型分析了新疆艾比湖国家级自然保护区马鹿秋季生境适宜性分布特征和主要生境因子对马鹿分布的影响。结果表明：模型预测结果较高,平均 AUC（area under the curve,受试工作者曲线下面值)值为0.976;Jackknife 检验结果显示：最热月最高温度对马鹿生境分布的影响较大。植被类型和坡度对马鹿生境分布的影响不大。海拔、年降雨量、气温日较差和最热季平均温度是影响马鹿生境分布的主要生境因子。马鹿秋季生境划分为高适宜、次适宜、低适宜和不适宜4个等级,马鹿的高适宜生境区主要分布在研究区域的北部,次适宜及低适宜生境区则分布于高适宜生境区的边缘,而不适宜生境区主要集中在西部和东部地区。研究不仅提供了马鹿在艾比湖的实际分布状况,也为马鹿生境和生境因子的关系方面提供了一个重要的科学依据。

关键词：马鹿；生态位模型；生境适宜性;Jackknife检验

# Assessing habitat suitability for Cervuselaphus in the Ebinur Lake National Nature Reserve

Akbar Muhtar,Rahmutulla Abdukerim,MahmutHalik \* College of Life Science and Technology, Xinjiang University，Urumqi 830046,China

Abstract:Habitat assessingand prediction is important when atempting to protect endangered species.In the Ebinur Lake National Nature Reserve，Xinjiang，Atotal of 92 recordedGPS cordinatesshowed that Ceruuselaphus waspresent inthe reserve in September 2013and October 2014.We grouped 23 habitat predictorvariables into three classs—terrain, vegetationstructure，and climatic factors.Weused the MAXENT model topredictthe potentiallsuitableautum habitat distribution for C.elaphusand determined thecontributioneachhabitatfactor madetothedistribution characteristics.The accuracy of our prediction models wasaccessed by the area under the curve（AUC）values for a receiveroperating characteristic（ROC）curve，and thevalidation showed thattheresults had high average AUCof O.976.Theresults of a Jackknife test indicated that themaximum temperature in the warmest month hadthe strongest influenceonautumn C.elaphus habitatsuitability,followedbyaltitude,annual precipitation，mean diurnalrange,and mean temperature during the warmest quarter.Vegetationtypeandslope hadlitleefecton habitatdistribution.Thesimulatedhabitatwas divided into fourclases—the mostsuitablehabitat,，moderatesuitabilityhabitat,lowsuitabilityhabitat,andunsuitablehabitat.The most suitable habitats for $\boldsymbol { c }$ . elaphus were mainly distributed in the northern parts of the study area，and habitats with moderateand lowsuitabilitywerein the marginal areasof themostsuitablehabitats.Incontrast，thewester and eastern parts of the study area were classified as unsuitable habitats for $C$ .elaphus.This study provides information on the actual distribution of $\boldsymbol { C }$ . elaphus in the Ebinur Lake National Nature Reserveand identifies important indicators that could be investigated by future studieson this species and its habitat. 1

KeyWords:Cervuselaphus；niche model;habitat suitability；Jackknife test

物种保护不但要维持种群数量,还要保护种群的生存环境,而了解物种种群的分布状况是保护其生存环境的关键前提和基础[1]。生境为野生动物提供了生存、繁衍及种群发展所必须的资源[2],生境适宜度时是指生境能支持一个特定物种的潜在能力[3],是影响野生动物生存和发展的重要因素,对物种进行生境评价是对野生动物进行有效保护和管理的第一步[4]。

马鹿(Ceruselaphus)属于哺乳纲、偶蹄目、反刍亚目、鹿科、鹿亚科、鹿属[5],是国家Ⅱ级保护动物。在中国主要分布于东北林区、宁夏贺兰山、新疆北部、甘肃、青海、四川和西藏等地[6]。马鹿在中国尚有一定数量,在黑龙江和吉林可能有近10万只,但由于过量捕猎幼仔和生境的丧失,也逐渐产生危机。新疆是我国马鹿的重要分布区,有3个亚种：阿勒泰马鹿（C.e.sibiricus）、天山马鹿（C.e.songaricus）和塔里木马鹿（C.e.yarkandensis）。塔里木的野生种群已经由1.5万只下降到 4000—5000只;阿尔泰马鹿由 20 世纪70年代的10万只下降到4万只左右;野生天山马鹿则正以3000 只/a左右的速度锐减[7-10]。由于长期的乱捕滥猎和生境破坏导致马鹿种群数量急剧下降,分布区也逐渐缩减。而对保护物种生境的研究,明确其主要影响因子和分布,是分析物种种群数量减少、濒危原因的重要手段,同事也能为制定合理的保护对策提供依据[1]。

近年来 MAXENT生态位模型在国内外得到广泛应用,ISI Web of Science 数据库检索结果表明:MAXENT生态位模型进行预测研究的文献数和每年的引文数逐年递增[12]。有研究显示,在预测物种潜在分布区时,与同类的物种分布模型（species distribution models,SDMs）相比,MAXENT 生态位模型表现出较好的预测能力[12]。在预测濒危物种分布时也有明显的优势,如 Pena 等[13]利用3种生态位模型评估了巴西北部濒危鸟类地理分布,结果表明 MAXENT模型的预测精度最高;齐增湘等[14]利用 MAXENT模型预测秦岭山系黑熊（Ursusthibetanus）的生境适宜性,结果显示模型精度达到0.991。徐卫华等[15]采用MAXENT模型,对秦岭地区的川金丝猴（Rhinopithecusroxllanae）的生境进行评价,结果显示模型预测结果为0.979。本文应用MAXENT模型对艾比湖马鹿生境适宜性进行评价,分析影响马鹿生存的主要生境因子并模拟其空间分布区域。

# 1研究区域概况

艾比湖位于天山北侧新疆西部,博尔塔拉蒙古族自治州境内,在行政区划分上地跨博尔塔拉蒙古自治州精河县、博乐市和阿拉山口口岸区,总面积 $2 6 7 0 . 8 5 ~ \mathrm { k m } ^ { 2 }$ 。艾比湖为准噶尔盆地最低洼地,也是新疆仅次于吐鲁番艾丁湖的第二低点，湖面海拔 $1 8 9 \mathrm { ~ m ~ }$ 。年平均气温6- ${ \cdot 8 } \mathrm { { ^ \circ C } }$ ,年均降水量 $9 0 . 9 \ \mathrm { m m }$ ,年蒸发量 $3 7 9 0 ~ \mathrm { m m }$ ,年平均大风天数达 $1 6 5 \mathrm { ~ d ~ }$ 。区内典型的地带性土壤为灰漠土、灰棕土和风沙土。艾比湖湖底平坦,属浅水湖；目前平均水深 $1 . 4 \mathrm { ~ m ~ }$ ,最深 $3 \mathrm { ~ m ~ }$ 。保护区内目前的各种脊椎动物有167种,其中两栖动物1目2科4种（蟾蜍科、蛙科),爬行动物2目6科7属10种,哺乳动物6目12科32种,鸟类有16目28科111种,鱼类2科10种。野生维管植物131科755属3552种,种子植物53科191属[16]。

# 2研究方法

# 2.1 模型介绍

最大熵原理(MAXENT)起源于信息科学,1957年最早由 Jaynes提出,在许多学科中有广泛应用,近年来引起了生态学家们的关注[12]。MAXENT是一种基于生态位原理的模型,根据物种“出现点”（出现马鹿粪便、食迹、足迹、卧迹等位置进行定点记录的数据)的生境变量特征得出约束条件,探寻此约束条件下最大熵的可能分布,以此来预测目标物种在研究地区的生境分布[17]。2004 年,Phillips 等人开发了 MAXENT软件,近来广泛用于物种生境适宜区的预测和评价,表现出了良好的预测能力[18]。该模型提供了自检验功能,可以自动生成ROC曲线进行模型的模拟预测自检，且在对动物生境进行评价与预测时，只需动物“出现点”的数据，并且具有较高的精度[19-21]

# 2.2 数据来源与处理

# 2.2.1 马鹿分布点数据

马鹿分布点数据来源于2013年9月和2014年10月通过走访当地居民和向导对新疆艾比湖国家级自然保护区开展2次秋季野外巡逻和检测以及艾比湖国家级自然保护区管理站的野外检测，用GPS对所观察到的马鹿实体或马鹿出现点位置进行定点记录，在艾比湖与马鹿同域分布的有蹄类还有鹅喉羚（Gazellasubgutturosa），可根据体型大小和形态特征对它们进行区分，第一次和第二次野外检测中分别得到了55和37处马鹿出现点，共得到了92处包含经纬度的马鹿出现点（包括粪便、足迹、食迹、卧迹等)(图1)。

# 2.2.2 生境变量数据

(1)气候因子。

![](images/5290983cf133caf6db441eb163e6dd44b9785165ac7da1a9f48d212998422eea.jpg)  
图1艾比湖马鹿出现点分布图Fig.1Species occurrence date

从世界气象数据库(http://www.worldclim.org/）中下载全球19个生物气候因子的 $1 ~ \mathrm { k m } ^ { 2 }$ 分辨率的栅格文件1950年至2000 年的平均值,然后用ArcGIS10.1软件来提取艾比湖区域的气候变量作为模型预测的生境变量(表1)。

表119个生物气候变量  
Table 1Bio climatic variables   

<html><body><table><tr><td colspan="2">变量代号 Code of variables 变量名称 Names of variables</td></tr><tr><td>BI01</td><td>年均温 Annual Mean Temperature</td></tr><tr><td>BI02</td><td>气温日较差 Mean Diurnal Range,Mean of monthly（max temp-min temp)</td></tr><tr><td>BI03</td><td>等温性Isothermal P2/P7 *100</td></tr><tr><td>BI04</td><td>温度季节性变动率 Temperature Seasonality,Standard deviation * 100</td></tr><tr><td>BI05</td><td>最热月最高温度 Max Temperature of Warmest Month</td></tr><tr><td>BI06</td><td>最冷月最低温度 Min Temperature of Coldest Month</td></tr><tr><td>BI07</td><td>年温度变化范围 Temperature Annual Range（P5—P6)</td></tr><tr><td>BIO8</td><td>最湿季平均温度 Mean Temperature of Wettest Quarter</td></tr><tr><td>BI09</td><td>最干季平均温度 Mean Temperature of Driest Quarter</td></tr><tr><td>BI010</td><td>最热季平均温度 Mean Temperature of Warmest Quarter</td></tr><tr><td>BIO11</td><td>最冷季平均温度 Mean Temperature of Coldest Quarter</td></tr><tr><td>BI012 htt</td><td>年降雨量 Annual Precipitation</td></tr><tr><td>BI013</td><td>最湿月降水量 Precipitation of Wettest Month</td></tr><tr><td>BIO14</td><td>最干月降水量 Precipitation of Driest Month</td></tr><tr><td>BI015</td><td>降雨量季节性变化Precipitation of Seasonality,Coefficient of Variation</td></tr><tr><td>BI016</td><td>最湿季降水量 Precipitation of Wettest Quarter</td></tr><tr><td>BI017</td><td>最干季降水量 Precipitation of Driest Quarter</td></tr><tr><td>BIO18</td><td>最热季降水量 Precipitation of Warmest Quarter</td></tr><tr><td>BIO19</td><td>最冷季降水量Precipitation of Coldest Quarter</td></tr></table></body></html>

(2)地形因子。

地形选取3个因子,包括海拔(altitude）、坡度(slope）和坡向（aspect）。采用来源于中国科学院科学数据库分辨率 $3 0 \mathrm { m } \times 3 0 \mathrm { m }$ 的数字高程地图(DEM)数据,在ArcGIS10.1中进行空间分析获得。

(3)植被数据。

先从谷歌剪切器下载艾比湖地区的地形图,然后通过目视解析法做出植被分布图,把艾比湖地区的植被类型分为泡泡刺（Nitrariasphaerocarpa Maxim）,草地（Meadow），柽柳（Tamarix spp.），胡杨林（Populuseuphratica）沼泽（Swamp）,湖泊（Lake）,宜林地（Suitable land for forest）,枸杞（Lyciumchinense）,芦苇（Phragmitesaustralis），柳树（salixbabylonica）,梭梭(Haloxylonammodendron）,沙漠(Desert）,等12类（图2）。

# 2.3 MAXENT模型的分析方法

# 2.3.1 MAXENT模型的数据

物种分布点数据：将物种分布点的数据在Excel中保存为MAXENT软件可以识别的以逗号分隔的CSV数据格式，字段包括物种名称、经度和纬度。

生境变量数据：以ArcGIS10.1为平台，分别建立各种生境变量的栅格文件,将所有生境变量数据,包括气候因子（BIO1-BIO19）、地形因子（DEM）、植被类型在ArcGIS10.1软件下转换为ASCII格式，并且按照MAXENT软件要求将所有图层统一边界和坐标系统。

# 2.3.2影响马鹿潜在分布关键生境变量的筛选

MAXENT模型预测中必须用到的数据有两个，分别是物种空间分布点的数据和生境变量数据，其中物种分布点的数据是必不可少的，而生境变量数据因为有多个变量，并不是每个变量对物种潜在分布预测都是必需的，因此需要剔除掉一些对MAXENT模型预测结果贡献较小的生境变量,只留下对模型预测结果贡献较大的关键限制因子,以提高模型的预测精度。在 MAXENT模型中软件本身提供了实现这一步骤的模块,即刀切法(Jackknife 检验)测定变量的重要性,通过比较每个生境变量对模型结果的影响程度来来剔除影响较小的变量。

![](images/a164de08645c7cf85f65eb2bf16473305afb5a7de408f249a88c7585333e53b8.jpg)  
图2研究区域的植被分布图  
Fig.2Vegetation distribution map of the study area

# 2.3.3马鹿生境模型构建

将物种的分布点的数据和生境变量数据导人MAXEN模型中，随机选取 $7 5 \%$ 的分布点的数据用于建立模型,剩下 $2 5 \%$ 的分布点的数据用于模型检验,其余参数设为模型默认值,构建马鹿分布模型进行模拟,取10 次模拟结果的平均值作为最终模拟结果[22]。

# 2.3.4 MAXENT模型的检验方法

模型的检验采用受试者工作特征曲线,即ROC 曲线（receiver operating characteristic curve）,该方法最早用于雷达信号接受能力的评估[23],后被广泛用于评价医学诊断试验试验性能,ROC 曲线以假阴性率为横坐标，真阳性率为纵坐标,绘制而成,ROC 曲线下的面积即为AUC 值(area under curve）[24]。AUC 值越大,表示生境变量与预测物种地理分布模型之间相关性越大,越能将该物种有分布和无分布判别开,预测效果也就越好[25-26]。评价标准为:AUC 值为0.50—0.60,失败（fail);0.60—0.70,较差（p0r）;0.70—0.80,一般（fair）；0.80—0.90,好（good）;0.90—1.0,非常好（excellent)[27-28]（图3）。

# 3结果与分析

# 3.1 MAXENT预测结果检测

ROC曲线评价结果显示：AUC值为0.976，表明MAXENT模型预测结果非常好。所建模型可用于艾比湖地区马鹿生境评价。

# 3.2生境变量筛选结果

由图4刀切法测定生境变量的重要性中可以看出，植被类型、坡度对其分布影响最小，因此，在选择最优秀MAXENT预测模型时剔除这两个影响最小的因子来构建最优秀模型进行预测

![](images/6fac4f7a1c52cfc0ed35afa67d0f7d2a0a9089f14a0c9fce14342da2a0efb6ac.jpg)  
图3MAXENT模型的ROC曲线及AUC面积  
图4MAXENT模型刀切法测定的各种生境变量的重要性 Fig.4MAXENT Jackknife measuring ofhabitat variable importance

从图中可以看出最热月最高温度(BIO5)对艾比湖 Fig.3ROC Curve and AUC values of the MAXENT 1马鹿分布影响最大,其次是海拔、年降雨量（BIO12）、气温日较差（BIO2）、最热季平均温度（BIO1O）、最冷月最低温度（BIO6)和最干季降水量（BIO17）。

# 3.3各种生境变量对MAXENT模型预测的影响

图5列出了全部生境变量的反馈曲线，显示了每个生境变量对模型预测的影响。从图中可以看到，植被类型和坡度的变化对MAXENT模型预测的结果不明显，海拔、最热月最高温度（BIO5）、年降雨量（BIO12）、温日较差（BIO2）的变化对MAXENT模型预测的结果很明显，而其他变量的变化对模型预测的结果没有较大的影响。

# 3.4艾比湖马鹿生境适宜性分布

利用MAXENT模型对艾比湖马鹿的生境适宜性进行评价，将模型输出的ASCII文件导入到ArcGIS10.1中转换成浮点型栅格数据，按照专家经验法将生境适宜图重新分类4个适宜等级：0—0.05为不适宜区，0.05—0.2为低适宜区,0.2—0.5为次适宜区,0.5—1为高适宜区，最终得到艾比湖地区马鹿的生境适宜性分布图(图6)

从图中可以看出，艾比湖马鹿的高适宜生境区主要分布在研究区域的北部，次适宜及低适宜生境区则分布于高适宜生境区的边缘，而不适宜生境区主要集中在西部和东部地区,其中适宜生境区和不适宜生境区占总面积的 $9 . 4 \%$ 和 $9 0 . 6 \%$ 。

□不包含该变量 包含该变量包含全部变量Altitude ANaspectybio1bio10 Nbio11bio12 Abio13 AN  
rarirraeiirrilil bio14AWY bio15 AANbio16 Vbio17bio18bio19bio2.Abio3o4bio5bio6 Nbio7bio8bio9 Nslope  
vegetation MX80.500.55 0.600.650.700.750.800.850.90 0.951.00检测得分 Test gain

# 4讨论

生境评价模型目前可以分为3种类型：机理模型、回归模型和生态位模型。机理模型并不需要物种分布点数据,而是根据生境因子对物种分布的影响建立相应的评价准则,进而模拟得到物种的适宜性生境,但因其没有考虑生境的可达性,且在对因子划分等级及确定权重上存在主观性,因此具有一定局限性[4]。相比回归模型,生态位模型只需动物“出现点”的数据而不需要“未出现点”的数据,根据在艾比湖野外考察的实际经验,发现在某个地点未发现马鹿的踪迹并不代表马鹿未曾在此地出现过,因此记录的“出现点”的数据并非十

海拔 坡向 气候因子1 气候因子10 气候因子11 气候因子12   
1.0 1.0 1.0 1.0 1.0 1.0   
0.5 1 0.5 0.5 0.5 八 0.5 0.5 0 0 0 0 0 0 187 408 -1 359-676 78 90 240 257 -257 -105 104 148 气候因子15 气候因子16 气候因子17 气候因子18 气候因子19 气候因子2   
1.0 1.0 1.0 1.0 1.0 1.0   
0.5 7 0.5 7 0.5 > 0.5 N 0.5 八 0.5 0 0 0 0 0 0 32 48 40 57 15 22 185 240 -121 -78 115 125 气候因子5 气候因子6 气候因子7 气候因子8 气候因子9 坡度   
1.0 1.0 1.0 1.0 1.0 1.0   
0.5 A 0.5 > 0.5 人 0.5 0.5 1 0.5 0 0 0 0 0 0 324 340 -197 -184 514 529 185 240 -121 -78 0 89.996 气候因子13 气候因子14 气候因子3 气候因子4 植被类型   
1.0 1.0 1.0 1.0 1.0   
0.5 0.5 0.5 0.5 人 0.5 0 0 0 0 0 14 20 4 6 22 24 13632 14494 -0.083 0.083

分准确，此外，物种“出现点”数据的多少对模型预测结果也有很大影响，通常物种分布点的数据越多，模型预测结果越可靠，但该模型在“出现点”数据较少的情况下,也具有较高的预测精度,如 Silva 等[29]在研究蜥蜴的1个稀有种的潜在分布区时，仅仅利用17个分布点的信息构建模型，得到的模型精度达到0.99，在获得少量分布点的信息情况下模型精度仍达到优秀水平。该方法避免了机理模型的主观性和回归模型的输入数据不易获取等缺点，更适用于分布点的信息匮乏的野生动物生境分布研究[30]

本研究基于MAXENT生态为模型，结合ArcGIS10.1,以地形因子、植被类型和气候因子作为生境变量因子，与分布点的数据结合对新疆艾比湖国家级自然保护区里面的马鹿的生境进行评价，模型分析表明：最热月最高温度（BIO5）、年降雨量（BI012）、气温日较差（BIO2）、最热季平均温度（BIO1O）、最冷月最低温度（BIO6)和最干季降水量（BIO17)等气候因子对艾比湖马鹿的分布影响起重要的作用,在地形因子方面,海拔最为重要,其次是坡向。李言阔等[31]的研究结果也指出海拔和坡向是黑龙江省完达山地区马鹿生境分布的主要影响因子。本研究中坡度因子对马鹿生境分布的影响很小,主要是因为马鹿行动敏捷、活动范围较大,对坡度要求较低,同时,本研究区地势比较平缓,几乎没有坡度很大的地方。植被类型对艾比湖马鹿的生境分布没有太大的影响,主要原因是虽然把植被分为不同的几个类型,但是艾比湖国家级自然保护区里面大部分地区的植被类型是混交林,同一区域范围会有各种植被共存,这是导致植被类型对艾比湖马鹿生境分布没有明显的影响。

![](images/77d9fbd04199378e9ea95bf19fda71974f73f987e9ecd76490957d8437f84524.jpg)  
图5MAXENT模型中研究物种对各种生境变量的响应曲线反馈曲线Fig.5Response curves of habitat variables in MAXENT models  
图6艾比湖马鹿生境分布  
Fig.6Habitats distribution of Cervuselaphus in the Ebinur Reserve

研究过程中没有加上水源因素，是因为艾比湖国家级自然保护区大部分区域总体上类似，以前的水源都不存在了,即艾比湖里面不同的区域离水源距离没有明显的差异,而且吴文等[32]利用MAXENT生态为模型对小兴安岭南麓马鹿冬季适宜生境进行研究,结果发现,水源对马鹿生境分布的影响很低,所以以艾比湖的实际情况出发本研究没有考虑了水源因素。

致谢：新疆博州艾比湖国家级自然保护区员工帮助采样,新疆大学资环与环境科学学院许仲林老师帮助软件使用、数据分析及讨论,新疆大学资环与环境科学学院阿不都拉·阿不力孜博士帮助写作,特此感谢。

# 参考文献（References）：

[1]WilsonJWetoJO,JobR,Haddelativecotriutioofteain,landoer，ndvegeatiostructureidicsdistribution models.Biological Conservation，2013，164：170-176.  
[2］王金亮，陈姚.3S 技术在野生动物生境研究中的应用.地理与地理信息科学，2004,20(6)：44-47.  
[3］王秀磊.普氏原羚生境的景观动态与适宜性评价研究[D].北京：中国林业科学研究院，2004.  
[4］刘振生，高惠，滕丽微，苏云，王晓勤，孔芳毅.基于MAXENT模型的贺兰山岩羊生境适宜性评价.生态学报，2013，33（22)7243- 7249.  
［5］吴建平.哺乳动物分类讲义.哈尔滨：东北林业大学，2005;120-133.[6] 盛和林.中国鹿类动物.上海：华东师范大学出版社，1992.  
［7］许庆翔，张明海，路秉信.黑龙江省野生马鹿种群资源调查研究.经济动物学报，2004，4（1)：57-62.  
[8] 高行宜,姚军.北天山喀拉乌成山的马鹿资源调查.地方病通报，2007，22(2)：6-8.  
[9] 艾尼瓦尔·吐米尔，马合木提·哈力克.塔里木河中游塔里木马鹿种群数量及其栖息地现状的初步分析.新疆农业科学，2008，45（4)：743-749.  
[10］张显理，李志刚，李正，马勇玺，张铁师，翟浩.宁夏贺兰山马鹿春季种群数量与种群动态研究.宁夏大学学报：自然科学版，2006，27(3):263-265.  
[11］欧阳志云，刘建国，肖寒，谭迎春，张和民.卧龙自然保护区大熊猫生境评价.生态学报，2001,21（11)：1869-1874.  
[12] 邢丁亮，郝占庆.最大熵原理及其在生态学研究中的应用.生物多样性，2011，19(3)：295-302.  
[13]De Castro Pena JC,Kamino L HY,Rodrigues M,Mariano-Neto E,De Siqueira M F.As sessing the conservation status of species with limitedavailable data and disjunct distribution.Biological Conservation,2014,170：130-136.  
[14］齐增湘，徐卫华，熊兴耀，欧阳志云，郑华，甘德欣.基于 MAXENT模型的秦岭山系黑熊潜在生境评价.生物多样性，2011，19（3)：343-352.  
[15］徐卫华，罗.MAXENT模型在秦岭川金丝猴生境评价中的应用.森林工程，2010,26(2)：1-3,26-26.  
［16］陈蜀江，侯平，李文华，李虎.新疆艾比湖湿地自然保护区综合科学考察.乌鲁木齐：新疆科学技术出版社，2006.  
[17]PhiliSdRieR.auetooofsacstrbolleln9/4): 231-259.  
[18］罗翀，徐卫华，周志翔，欧阳志云，张路.基于生态位模型的秦岭山系林麝生境预测.生态学报，2011，,31（5)：1221-1229.  
[19]Stacu-eebitatpededilfofbiologically valuable forests.Forest Ecology and Management，2009,258(5）: 697-703.  
[20]HaegenB,ieRtroizatdatiastrtioofseiecanturalist，(）：E90.  
[21］李明阳，巨云为，Kumar S，StohlgrenTJ.美国大陆外来入侵物种斑马纹贻贝（Dreisenapolymorpha）潜在生境预测模型.生态学报，2008，28(9):4253-4258．  
22]BehdrandN,aboliadiouaniE,iniAS,ghbolagiM.Satialismodeldmitigatioimplicatiosforaconflict in a highly modified agroecosystem in western Iran. Biological Conservation，2014,177：156-164.  
[23]Leshipdeleueofcey6,46(2B):399-402.  
[24］王运生，谢丙炎，万方浩，肖启明，戴良英.ROC 曲线分析在评价入侵物种分布模型中的应用.生物多样性，200，15(4)：365-372.  
[25］侯宁，戴强，冉江洪，焦迎迎，程勇，赵成.大相岭山系泥巴山大熊猫生境廊道设计.应用与环境生物学报，2014，20(6)：1039-1045.[26] CatryFXRegForeiaFodelgdaingesirgalteatialJalfe18(8) : 921-931.27 Swets JA. Measuring the accuracy of diagnostic systems. Science，1998,240(4857）:1285-1293.  
[28]ArajoMB，PearsonRGuilerW,ErhardM.Validationofspecies-limateimpactodelsunderclimatecangeGlobalChangeiolog，2005,11(9): 1504-1513.[29]DeNovslV,PreseyRL,acdoRB,VDerWalJ,WedereckerHCWeec,CollG.Fulatingcoseratietfra gap analysis of endemic lizards in a biodiversity hotspot.Biological Conservation,2O14，18O：1-10.  
[30］陈新美，雷渊才，张雄清，贾宏炎.样本量对 MaxEnt 模型预测物种分布精度和稳定性的影响.林业科学，2012，48（1)：53-59.  
[31］李言阔，张明海，蒋志刚.基于生境可获得性的完达山地区马鹿（Cervuselaphusxanthopygus）冬季生境选择．生态学报，2008，28（10)：4619-4628.  
[32］吴文，李月辉，胡远满，陈龙，李悦，李泽鸣，聂志文，陈探.小兴安岭南麓马鹿冬季适宜生境评价.生物多样性，2016,24（1)：20-29.