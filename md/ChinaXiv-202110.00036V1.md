# 基于MCR模型的卡拉麦里地区生态安全格局变化研究

赵晓峰1.2.3,4， 王金林1.2.3.4, 王珊珊1.,2.3,4，王权

(1.中国科学院新疆生态与地理研究所,荒漠与绿洲生态国家重点实验室,新疆 乌鲁木齐830011;2.新疆矿产资源与数字地质重点实验室,新疆乌鲁木齐830011；3.中国科学院新疆矿产资源研究中心，新疆乌鲁木齐 830011；4.中国科学院大学,北京100049；5.日本静冈大学,静冈422-8529)

摘要：随着生产力的发展，人类在开发活动中导致的植被破坏、水源污染、土壤污染等生态环境问题日益突出，人类活动与自然环境之间的矛盾和保障人类社会的可持续发展已经成为急需解决的问题。利用最小累积阻力模型(MCR)对1990—2019年卡拉麦里地区的生态安全格局变化规律进行分析，并结合元胞自动机-马尔可夫模型(CA-Markov)对2025年本地区的生态安全格局进行预测。结果表明：(1)将卡拉麦里地区的生态安全格局分为安全区、低安全区及不安全区，安全区的面积在2010—2015年萎缩至 $3 2 3 7 . 3 1 \mathrm { k m } ^ { 2 }$ ，主要转化为低安全区及不安全区，这一时期的人类活动严重影响到了本区的生态环境。(2)2019年，安全区面积为 $6 2 6 5 . 9 1 { \mathrm { ~ k m } } ^ { 2 }$ ，低安全区及不安全区基本恢复为自然状态，生态治理工作取得良好效果。(3)预测可知,2025年卡拉麦里地区景观格局变化不大，仍以草地、未利用地为主。生态安全区面积 $6 4 2 1 . 8 8 \mathrm { k m } ^ { 2 }$ ，低安全区及不安全区面积有继续下降趋势。(4）在卡山保护区中部的交通路线附近形成了一条带状低安全区，将成为今后保护区生态监测与保护的重点区域。

关键词：CA-Markov模型；生态安全格局；最小累积阻力模型(MCR)；卡拉麦里地区

# 文章编号：

21世纪以来，随着生态环境问题的日益突出，人类活动与自然环境之间的矛盾越发尖锐，如何缓解二者之间的矛盾，保障人类社会的可持续发展已经成为急需解决的问题。十九大报告明确提出“绿水青山就是金山银山”、“实行最严格的生态环境保护制度，形成绿色发展方式和生活方式，为全球生态安全做出贡献"等一系列生态环境保护政策与方针。在此背景下，人类活动影响下的生态脆弱区生态安全格局问题的研究具有很重要的现实意义。

生态脆弱区是指生态系统较为脆弱，在受到外来干扰(自然及人为)的影响下生态环境容易受到破坏且恢复能力较差，恢复代价较高的区域[1-2]。区域生态安全格局是针对特定地理单元，由该地理单元内局部、位置及其空间联系所构成的潜在空间格局[3-4]。通过构建生态脆弱区的生态安全格局，有助于识别生态安全核心区域及敏感区域，对保护区用地规划及保护政策的实施具有十分重要的意义，

近年来，在区域生态安全格局构建方面，主要方法有生态安全评价指标体系[5-6]、景观指数法[7]、压力-状态-响应(PSR)模型[8]、最小累积阻力(MCR)模型[9-10]等。MCR模型最早由国外学者Knaapen等[11]提出，经由我国学者俞孔坚等[3,12]改进被广泛应用于生态安全格局的构建当中。该模型以景观生态学中的源-汇理论为基础，研究物种从源到目的地所需克服的异质景观阻力的最小代价[9.12]它综合考虑了地区景观单元空间上的水平联系，有效反映了生态安全格局的空间变化规律，在区域生态安全格局的构建中具有广泛的应用[13-14]。

随着计算机技术的日益成熟，对景观格局动态变化进行模拟的方法也越来越多，如元胞自动机-马尔可夫模型(CA-Markov)[15]、小尺度土地利用变化及其空间效应(CLUE-S)模型[16]、系统动力学模型[7等。其中,将马尔可夫长期预测与元胞自动机模拟复杂空间格局相结合的CA-Markov模型是应用最为广泛的景观格局动态预测模型[18-19],它能够对区域土地覆被类型的变化进行有效模拟，同时也可以制定不同的转移规则对不同情境下的景观格局演变进行模拟与分析[20]

新疆卡拉麦里地区(简称为卡山地区)矿产资源丰富，南部的准东煤田是我国最大的整装煤田，其煤炭储量已探明的有 $2 1 3 6 \times 1 0 ^ { 8 } { \mathrm { t } }$ ，预测储量 $3 9 0 0 \times$ $1 0 ^ { 8 }$ t[21]。2005年底新疆维吾尔自治区政府开始对准东地带进行开发，于2010年正式设立准东煤电煤化工产业园区并划出卡拉麦里山有蹄类野生动物自然保护区（简称为卡山保护区）。2012年，经国务院批准，准东煤电煤化工产业园区正式成为国家级经济技术开发区。据准东官网(http://zd.cj.cn/)介绍，2019年准东经济技术开发区煤炭总产能高达$1 . 0 2 2 \times 1 0 ^ { 8 } \mathrm { t } \cdot \mathrm { a } ^ { - 1 }$ ,是新疆最大的煤炭产区。除煤炭资源外，卡山地区还是东准噶尔地带重要的铜、金、锡成矿地带[22],拥有浅成低温热液型金矿、斑岩型铜金矿、构造控制脉型铜矿和云英岩-石英脉型锡矿等多种矿床组合[23]。2005—2015年曾有崛发矿业、欧骆石材等企业在卡山保护区部分地区设立开矿点对这些资源进行开发，保护区空间范围也因此进行了数次调整，严重影响到了野生动物的生存环境[24]。

蒙古野驴与鹅喉羚是本区重点研究的野生动物物种，根据2019年的野外调查结果卡山保护区内的蒙古野驴和鹅喉羚种群数量分别约为4636头、7876头，大致分布在水源较多的卡山保护区中东部附近。这2种动物均有较强的季节性迁徙规律，一般会在每年的秋冬季节集体往卡山保护区西南部及南部地带移动，次年春季则会返回卡山保护区中部及北部地带[24-26]。除季节性迁徙外,这2种动物在夏季还会因为水源点环境的变化进行东西方向的移动。目前，卡山地区中部共有3条南北纵穿卡山保护区的交通路线，分别为国道216线及新建的全封闭高速公路与铁路，3线并行且相距较近。3条并行的交通路线将卡山保护区野生动物的栖息地一分为二,影响了野生动物的生境连通性。尽管在高速公路及铁路地段以桥洞、立交桥等形式建立了87个野生动物通道，但其使用效率仍在考察中，道路对野生动物迁徙及生活造成的影响仍然较为严重。

以上研究表明，2005年以来卡山地区矿产资源的开发对脆弱的生态环境造成了较为严重的破坏，生态保护迫在眉睫。2015年之后，由于生态文明政策实施力度的加强，卡山保护区内的开矿点被撤销整治，保护区的生态环境质量逐步恢复，但道路对野生动物的影响却在加大。在这种背景下，研究卡山保护区生态安全格局的变化规律及影响因素对本区生态保护建设具有十分重要的现实意义。

本文以卡山地区为研究区，利用卡山保护区相关单位提供的土地利用、水源点等数据，结合MCR模型对1990—2019年保护区的生态安全格局变化规律进行研究以期为保护区监测、保护野生动物生存环境，维护保护区生态安全，维系地区生物多样性，合理规划人类在本地区的活动提供初步的科学依据及建议。

# 1研究区概况

卡山地区位于 $8 8 ^ { \circ } 3 0 ^ { \prime } { \sim } 9 0 ^ { \circ } 0 3 ^ { \prime } \mathrm { E } . 4 4 ^ { \circ } 3 6 ^ { \prime } { \sim } 4 6 ^ { \circ } 0 0 ^ { \prime } \mathrm { N }$ 之间，包括卡山保护区及准东经济技术开发区，地处准噶尔盆地东部，总面积 $1 8 0 0 0 { \mathrm { k m } } ^ { 2 }$ （其中保护区面积 $1 4 8 5 6 . 2 \mathrm { k m } ^ { 2 } ,$ (图1)。研究区属典型的温带大陆性气候，年均温 $2 . 4 ~ \mathrm { ^ { \circ } C }$ ,年均降水量 $1 8 6 . 8 ~ \mathrm { m m }$ ,年均潜在蒸发量达 $2 0 9 0 \mathrm { m m } ^ { [ 2 5 ] }$ ,远大于年均降水量,导致该地区处于极度干旱的状态，永久性地表水系匮乏。卡山保护区平均海拔 $1 0 0 0 \mathrm { m }$ ，地势起伏较小。植被以典型的荒漠半荒漠植被为主。野生动物种

![](images/408a58a7f54f5f61bed4728295e5036a8a03221afd7dfadd67d5d5cb1ff5b0ad.jpg)  
图1研究区示意图  
Fig.1Schematic diagram of the study area

# 干旱区地理

类繁多，据资料记载共有288种，其中较为珍贵的有国家级保护动物普氏野马、蒙古野驴、鹅喉羚等[21]本地区极具干旱区域特色的环境使卡山地区的生态环境十分脆弱，而区域内珍贵的野生动物资源使本地区具有很高的生态保护和科学研究价值。

# 2数据与方法

# 2.1数据来源

为提高数据精度，本文土地利用数据采用卡山保护区提供的由Landsat影像目视解译得到的1990、2000、2010、2015、2019年5期高精度数据，空间分辨率为 $3 0 \mathrm { m }$ 。为研究卡山地区2025年景观格局演变的趋势及构建生态安全格局的需要，采用土地利用数据中的一级分类标准，将研究区土地类型划分为人工表面、林地、草地、湿地、未利用地5个类型。研究区数字高程模型(DEM)数据来源于地理空间数据云(http://www.gscloud.cn/）,空间分辨率为$3 0 \mathrm { ~ m ~ }$ ，并在ArcGIS10.2中提取坡度数据。土壤、水源点、植被类型、矿点、道路、保护区区划数据由卡山保护区部门提供。

# 2.2最小累积阻力(MCR)模型

MCR模型是研究物种从源地到目的地所需克服异质景观空间阻力的最小成本之和[9],其计算公式如下：

$$
\mathrm { M C R } = f _ { \mathrm { m i n } } \sum D _ { i } \times R _ { j }
$$

式中： $D _ { i }$ 表示“源"到空间单元 $i$ 的距离 $( \operatorname { k m } ) ; R _ { j }$ 表示空间单元j的阻力系数。 $f _ { \mathrm { m i n } }$ 表示正相关函数。

# 2.3元胞自动机-马尔可夫预测(CA-Markov)模型 原理及构建

元胞自动机是依赖于不同时间、空间特征的元胞及其领域的相互作用，能够模拟复杂系统时空演化过程的网络动力学模型[27-29]。马尔可夫模型是基于马尔可夫随机过程，描述事件在某一时期的变化特征，并以此为依据去预测该事件的未来发展趋势的模型[20.0-31]。CA-Markov模型利用上述2种模型的优势，将连续的空间要素引入马尔可夫的时间序列分析当中，从而预测模拟未来区域景观格局的时空变化[20]。

本文基于ArcGIS及IDRISI17.0软件中的CA-Markov模块对研究区2025年景观格局进行模拟。具体过程如下：（1）在ArcGIS中将2015、2019年两期土地利用数据及DEM、坡度等数据转换为ASCII格式，并将其导入IDRISI软件中进行重分类；（2）利用IDRISI中Markov模块，计算2015—2019年研究区土地利用类型的马尔可夫转移矩阵及概率转移图像。将人工表面、湿地设置为限制性用地并制作相应适宜性图集;（3）通过软件中CA-Markov模块，采用 $5 { \times } 5$ 滤波器，设置迭代次数为6次(1次为1a)，以2019年数据为基期数据，利用适宜性图集预测研究区2025年土地利用状况。同时以2015年数据为基期数据，以同样的方法得出2019年土地利用图，将数据导出并保存;（4）利用IDRISI中的crosstab模块，通过kappa检验来验证2019年土地利用预测结果与实际图像的精度，经计算，kappa系数为0.8152（通常kappa系数 $\geqslant 0 . 7 5$ 即认为预测精度较高[19.31]），可以作为研究分析之用。

# 3结果与分析

# 3.1基于CA-Markov的2025年景观格局预测模拟

根据模型预测(图2)，卡山地区的景观格局未发生明显的改变，未利用地作为本地区的主要景观类型，面积为 $9 8 9 1 ~ \mathrm { k m } ^ { 2 }$ ，占区域总面积的 $5 4 . 9 8 \%$ 。草地与林地是仅次于未利用地的第二、第三大景观类型，其中林地集中分布在西北部沙漠丘陵边缘，另有少量分布于中部卡拉麦里山地及东北部丘陵戈壁地带，总面积 $1 6 6 1 ~ \mathrm { k m } ^ { 2 }$ ，占比约 $9 . 2 3 \%$ ;草地面积 $6 2 7 9 \mathrm { k m } ^ { 2 }$ ,主要呈面状、条带状分布在东北部丘陵戈壁、中部卡拉麦里山地及南部将军戈壁地区，占区域总面积的 $3 4 . 9 1 \%$ 。人工表面以矿产开采及加工产业为主，总面积 $1 5 4 \mathrm { k m } ^ { 2 }$ ，占比仅 $0 . 8 6 \%$ ，集中分布在地区南部的准东经济区内，另有少量交通用地分布在卡山保护区内。由于气候原因，卡山地区湿地以人类建立的水库等供水设施为主，主要依附于人文景观，且面积仅 $4 \mathrm { k m } ^ { 2 }$ ，占比 $0 . 0 2 \%$ 。

# 3.2源地识别

卡山保护区设立的目标是为保护本区生存的大型有蹄类野生动物，研究本区域的生态安全格局实质上是对保护区内野生动物的生态安全格局进行研究。因此，应将地区代表性物种的栖息地作为生态安全格局研究中的源地。目前卡山地区重点研究的动物为蒙古野驴和鹅喉羚，因此，本文将这2种动物的栖息地作为卡山地区生态安全格局的“源”。由于卡山地区景观类型较为单一，因此不能简单地将某一类景观类型直接作为2种动物的栖息地，需要综合考虑自然要素、人为要素、综合要素等多要素的影响。

![](images/4e1ed34de9a10e9dd89f5176a93081305dd40369e9c25d7631066c1e15447c73.jpg)  
图22025年卡拉麦里地区景观格局预测  
Fig.2Forecast of Kalamaili region landscape pattern in 2025

自然要素：根据相关学者对卡山地区蒙古野驴及鹅喉羚的研究[21.25.32-34],蒙古野驴及鹅喉羚通常不会在距离水源点 $1 5 \mathrm { k m }$ 之外进行大规模活动，水源是限制本区大型野生动物的首要因素[21.32]；除水源点外，蒙古野驴及鹅喉羚通常会根据对植物种类的偏好选择适宜的活动地点，如蒙古野驴偏向于食用白茎绢蒿、梭梭、盐生假木贼、沙生针茅等，鹅喉羚则偏向于食用沙生针茅、梭梭、沙蒿等[21.32-35],因此本文将卡山地区的植被类型图按照这两类动物的采食偏好分为高、中、低3个类型，植被类型是影响野生动物分布的第二大要素。除水源及采食偏好外，地形及土壤也是较为重要的影响因素，鹅喉羚、蒙古野驴等通常在坡度较小、地形较平坦的地带活动[25.32],松软的土地则不利于蒙古野驴等大型野生动物的活动25，由于卡山地区松软的土地基本分布于研究区西北部，因此土壤对野生动物的影响要小于坡度。综合上述研究，将水源点、坡度、土壤、植被类型作为栖息地评价的自然要素。

人为要素：野生动物对人类活动具有回避效应[35],卡山保护区的人类干扰主要分为2种，一种是G216线等交通道路的影响，另一种则是2010一2015年间大规模的区域矿产开发及东南部准东经济区的建设，前者导致保护区被分割为2个相对独立的区域，从长远看不利于野生动物的种族交流，后者则挤压了野生动物的生存空间[25.35]。综合上述研究，将距道路距离、距矿点距离、距经济区距离作为栖息地评价的人为要素。

综合要素：土地覆被是人类与自然双重作用下的综合要素，能够直接反应土地的空间变化状态，同时也是野生动物活动的重要载体。

在确立影响因素体系后，参考其它研究者在源地识别时的研究成果[8.24.25.32],划分各影响因素的空间适宜程度并赋值(表1)：适宜(1）、次适宜(3)、低适宜(5）、不适宜(7)，并在ArcGIS中通过重分类及工具制作各栖息地指标图层。结合层次分析法对各影响因素的权重进行赋值(表2)，并在ArcGIS中进行叠加，得到最终的源地识别图(图3)。

1990、2000、2010、2015、2019、2025年(预测)栖息地面积分别为 $4 5 2 4 . 9 1 ~ \mathrm { k m } ^ { 2 } , 4 5 2 5 . 0 8 ~ \mathrm { k m } ^ { 2 } , 5 3 9 6 . 7 8$ $\mathrm { k m ^ { 2 } \setminus 4 7 3 6 . 3 1 ~ k m ^ { 2 } } \setminus 5 9 0 0 . 0 3 ~ \mathrm { k m ^ { 2 } } \setminus 6 2 0 0 . 1 0 ~ \mathrm { k m ^ { 2 } }$ ，分别占

表1栖息地识别指标体系  
Tab.1 Habitat identification index system   

<html><body><table><tr><td>栖息地指标</td><td>适宜(1)</td><td>次适宜(3)</td><td>低适宜(5)</td><td>不适宜(7)</td></tr><tr><td>距水源点距离(A1)/km</td><td><5</td><td>5~15</td><td>1</td><td>>15</td></tr><tr><td>坡度(A2)/()</td><td>0~5</td><td>5~15</td><td>1</td><td>>15</td></tr><tr><td>植被类型(A3)</td><td>高</td><td>中</td><td>低</td><td>一</td></tr><tr><td>土壤类型(A4)</td><td>1</td><td>1</td><td>1</td><td>风沙土</td></tr><tr><td>景观类型(A5)</td><td>草地</td><td>未利用地</td><td>林地</td><td>人工表面、湿地</td></tr><tr><td>距G216距离(A6)/m</td><td>> 1200</td><td>601~1200</td><td>400~600</td><td><400</td></tr><tr><td>距高速公路、铁路距离(A7)/m</td><td>> 1200</td><td>601~1200</td><td>400~600</td><td><400</td></tr><tr><td>距经济区距离(A8)/m</td><td>> 5000</td><td>4001~5000</td><td>2001~4000</td><td><2000</td></tr><tr><td>距矿点距离(A9)/m</td><td>> 5000</td><td>4001~5000</td><td>2001~4000</td><td><2000</td></tr></table></body></html>

注：-表示此处无内容。下同。

# 干旱区地理

# 表2各识别指标权重

Tab.2Weightofeachidentification indicator   

<html><body><table><tr><td>年份</td><td>A1</td><td>A2</td><td>A3</td><td>A4</td><td>A5</td><td>A6</td><td>A7</td><td>A8</td><td>A9</td></tr><tr><td>1990—2000</td><td>0.4160</td><td>0.0899</td><td>0.1873</td><td>0.0386</td><td>0.1001</td><td>0.0504</td><td>一</td><td>0.1178</td><td>1</td></tr><tr><td>2010—2015</td><td>0.3467</td><td>0.0843</td><td>0.1561</td><td>0.0322</td><td>0.0868</td><td>0.0403</td><td>1</td><td>0.0699</td><td>0.1932</td></tr><tr><td>2019—2025</td><td>0.3900</td><td>0.0843</td><td>0.1756</td><td>0.0362</td><td>0.0887</td><td>0.0429</td><td>0.0912</td><td>0.0912</td><td>二</td></tr></table></body></html>

![](images/bfd45e1864c5a27714758b6eca82ac89489904153591426dd505105a29a90edf.jpg)  
图3卡山保护区源地变化  
Fig.3Source site changes in Kalamaili Reserve

不同时期卡山保护区总面积的 $2 4 . 0 4 \% . 2 4 . 0 4 \%$ 、$3 7 . 7 3 \% . 3 3 . 1 2 \% . 4 0 . 0 1 \% . 4 2 . 0 4 \%$ 。总体来说，卡山保护区野生动物的栖息地面积呈增加-降低-增加的趋势，2010年之前，野生动物的栖息地在不断扩张，根据野外调查结果，这一时期蒙古野驴的种群数量及分布密度也一直处于增长趋势[26.36];2010年之后，随着人类在本地区矿产资源开发力度的加大，动物的栖息地也在持续萎缩，到2015年共降低$6 6 0 . 4 7 ~ \mathrm { k m } ^ { 2 }$ ,野生动物的生存环境已受到严重的影响，且影响程度较重的地区基本分布在栖息地的中东部地区。2019年，经过生态修复工作之后，本地区的动物源地已经有大幅度的恢复，新增面积共$1 1 6 3 . 7 2 \ \mathrm { k m } ^ { 2 }$ 。在现有保护条件下，根据预测，2025年栖息地面积将增加 $3 0 0 . 0 7 ~ \mathrm { k m } ^ { 2 }$ 。据野外调查结果，2015年后蒙古野驴等动物的分布密度明显增加[35.37],从一定程度说明动物栖息地的生态环境质量有所改善。

# 3.3最小累积阻力面及生态安全格局的构建

在源地识别研究的基础上，本文通过模拟研究蒙古野驴及鹅喉羚的空间扩散过程，将景观类型、保护区区划及距道路距离作为影响动物空间运动的阻力因子。利用层次分析法对阻力因子权重赋值，研究众学者对生态脆弱区、生态用地、单一生态系统、城市等不同区域类型的阻力因子赋值的成果[8-9.38-40],采用其赋值方式即将相对阻力值拟定在0\~100之内，阻力值越小则动物的空间扩散过程中克服的阻力越小，具体为空间阻力小(10)空间阻力较小(30）、空间阻力较大(50）、空间阻力大(100)。在确定阻力值(表3)后，在ArcGIS中将各单一空间阻力因子图按阻力值进行重分类，并按照表4中根据层次分析法计算得出的权重值将重分类后的单一空间阻力因子图在ArcGIS中进行叠加得到最终的综合阻力因子面。最终以源地识别的数据为空间源，以综合阻力因子面为成本数据，利用Arc-GIS中的成本-距离模型，构建研究区的最小累积阻力面，该最小累积阻力面即为本地区的生态安全格局(图4)。需要说明的是，水源点的数据由卡山保护区部门提供，其空间分布仅限于保护区范围内，缺乏准东经济区内的水源数据，同时准东经济区在2010年之后已被划出保护区范围，因此在构建1990—2025年生态安全格局时准东经济区部分不在考虑范围内。

# 表3生态安全阻力因子

Tab.3 Ecological safety resistance factors   

<html><body><table><tr><td>阻力值</td><td>10</td><td>30</td><td>50</td><td>100</td></tr><tr><td>保护区区划(B1)</td><td>核心区</td><td>缓冲区</td><td>实验区</td><td>开发区</td></tr><tr><td>景观类型(B2)</td><td>草地</td><td>未利用地</td><td>林地</td><td>人工表面、湿地</td></tr><tr><td>距道路距离(B3)/m</td><td>>1200</td><td>601~1200</td><td>400~600</td><td><400</td></tr></table></body></html>

# 表4阻力因子权重

Tab.4Weightofresistancefactors   

<html><body><table><tr><td>年份</td><td>B1</td><td>B2</td><td>B3</td></tr><tr><td>1990—2000</td><td>1</td><td>0.6667</td><td>0.3333</td></tr><tr><td>2010—2025</td><td>0.4373</td><td>0.3992</td><td>0.1635</td></tr></table></body></html>

# 3.4综合生态安全格局分析

综合相关学者对卡山保护区蒙古野驴、鹅喉羚适宜性生境的研究[25.32.35],将研究区的生态安全水平划分为安全、低安全、不安全3个等级（分别对应适宜性生境研究当中的适宜、较适宜及不适宜)。在确立划分为3个等级后，利用ArcGIS中的自然断点法将最小累积阻力面进行等级划分，并利用ArcGIS中的栅格计算器计算各安全等级区域的面积，最终得到的各时期生态安全格局图及其面积(图4、表5)。

安全区主要分布在卡山保护区的中东部地带，偏西部地带仅少量分布，景观类型以草地、未利用地为主。从各时间段来看，1990—2000年安全区未发生明显的变化，而2000—2010年、2010—2015年安全区的面积则分别下降了 $3 6 0 7 . 3 7 ~ \mathrm { k m } ^ { 2 } \cdot 5 9 4 . 3 2$ $ { \mathrm { k m } } ^ { 2 }$ ，分布明显趋于破碎化且减少区域多位于中东部地带。2019年，随着生态恢复与治理工作的实施，卡山保护区的安全区面积恢复为 $6 2 6 5 . 9 1 ~ \mathrm { k m } ^ { 2 }$ 占卡山保护区总面积的 $4 2 . 4 9 \%$ 。同时期，相较于2012年的蒙古野驴野外调查结果(609\~2107头）[37]，2019年的野外调查结果显示蒙古野驴的种群数量$( 2 2 7 3 \mathrm { - } 4 6 3 6$ 头)有了大幅度提升[35],从一定程度上说明地区的生态环境有所改善。据预测，2025年生态安全区面积将增长 $1 5 5 . 9 7 \ \mathrm { k m } ^ { 2 }$ ,但新建高速公路、铁路及G216国道3条并行的交通线路却将安全区隔断为2个相对独立的部分，从长期来看将对野生动物的生境连通性造成影响。

低安全区作为安全区与不安全区之间的缓冲地带呈环带状分布于安全区的外延区域，其面积在1990—2000年之间无明显变化。2000—2010年，低安全区面积扩大 $3 0 7 5 . 3 6 ~ \mathrm { k m } ^ { 2 }$ 。占卡山保护区总面积的 $2 1 . 4 5 \%$ ，从图4中可以看出，这一时期增加的低安全区多由安全区转化而来。2015年，低安全区面积下降 $1 1 5 . 0 1 ~ \mathrm { k m } ^ { 2 }$ ,结合图4,可以发现这一时期该部分区域转化为了不安全区。2019年，经过生态修复，低安全区的面积减少为 $3 8 6 3 . 5 7 ~ \mathrm { k m } ^ { 2 }$ ，中部地区的低安全区基本都恢复为安全区，且为蒙古野驴等快速利用[35]。需要注意的是,在卡山保护区中部交通线路附近形成了一条带状的低安全区，说明该区域作为人类影响最为直接的敏感地区应成为今后生态保护与监测工作的重点。

不安全区位于西部及南部地区，水资源匮乏，土壤以风沙土为主，自然环境条件较差且南部地区人类活动力度较大，不适宜作为动物的栖息地。值得注意的是2010年及2015年在卡山保护区中东部地带出现了部分不安全区域，且2015年的范围要大于2010年，2015年不安全区面积相较于2010年增长 $7 0 4 . 0 8 \ \mathrm { k m } ^ { 2 }$ （表5)，据野外调查，2012年的蒙古野驴种群数量(609\~2107头)[37]要低于2001年的种群数量（2632\~4200头）[3，说明这一时期卡山保护区

![](images/14e2382376ec4a190cc5f4a237c7c35b9d94fd6d0292ab94d85a1377cf5b08af.jpg)  
干旱区地理  
图4卡山保护区生态安全格局  
Fig.4 Ecological securitypattern ofKalamailiReserve

# 表5生态安全分级面积

Tab.5 Area of ecological safety classification   
/km²   

<html><body><table><tr><td>生态等级</td><td>1990年</td><td>2000年</td><td>2010年</td><td>2015年</td><td>2019年</td><td>2025年</td></tr><tr><td>安全</td><td>7438.64</td><td>7439.00</td><td>3831.63</td><td>3237.31</td><td>6265.91</td><td>6421.88</td></tr><tr><td>低安全</td><td>3182.42</td><td>3182.77</td><td>6258.13</td><td>6143.12</td><td>3863.57</td><td>3741.25</td></tr><tr><td>不安全</td><td>8199.04</td><td>8198.34</td><td>4214.41</td><td>4918.49</td><td>4616.66</td><td>4583.73</td></tr></table></body></html>

的生态环境达到了一个较差的状态。2019—2025年，经过治理，不安全区基本缩小为自然状态下的范围且有继续下降的趋势，说明生态治理取得了良好的效果。

# 4讨论

# 4.1驱动因素分析

（1）自然因素。卡山地区地表水系匮乏，仅有喀姆斯特、老鸭泉等14处矿化度较高的苦泉水及克孜勒日什、乔木稀拜等多处雨雪蓄水点[41],严重匮乏的水资源是限制卡山保护区内动物分布的主要因素[21,35.41-42]。另外,过于干燥的夏季及冬季的暴风雪天气也会对本地区野生动物的生存造成威胁。

(2）道路建设。目前，卡山地区共有3条南北纵向贯穿卡山保护区的交通线路，这些道路将安全区一分为二，使其完整性遭到破坏，对野生动物的正常迁徙与生活造成了不利影响。在卡山保护区的矿产资源开发得到整治之后，道路的影响已经成为本地区人类干扰的主要方式。

(3）矿产资源开发。卡山地区蕴藏着丰富的煤炭及其它矿产资源，其南部拥有我国目前最大的整装煤田[42]。2005—2015年,卡山地区相继成立了准东经济区、喀姆斯特经济区及部分采矿区对卡山保护区的矿产资源进行开发，这些开发活动不仅侵占了野生动物的水源点，而且在一定程度上导致了野生动物生境的破碎化[2]。这些影响在野生动物种群数量及分布密度的野外调查结果中有所证明[22.36]

# 4.2建议

2019年卡山地区的矿产开发得到整治，道路建设的影响已逐步成为人类在本地区施加影响的最直接体现。尽管在道路修建过程中预留了可供动物通过的生态通道，但道路交通对野生动物迁徙带来的威胁及噪声污染等依然会对本区野生动物的生活造成不利影响。今后应加大对卡山保护区道路周边及其设置的生态通道的监测与研究力度，设置红外相机及其它监测设备，掌握动物活动的历史数据，为卡山保护区野生动物的保护工作提供依据。

# 5结论

本文以卡山地区为研究区，从物种保护角度出发，借助MCR模型构建了1990—2019年卡山保护区生态安全格局，对生态安全格局的演变规律进行了分析，得出以下结论：

（1）根据CA-Markov模型预测，2025年卡山地区景观格局变化不大，以草地、未利用地为主，人工表面则集中分布在南部准东经济区内，占比仅为$0 . 8 6 \%$ 。需要说明的是，本文预测所使用的影响因子体系是基于已有的文献总结，可能会对预测结果造成一定偏差，因此在今后工作中应对影响因子体系进行完善，使预测结果更接近实际。

（2）根据MCR模型的计算结果将地区生态安全分为3个级别。其中，安全区主要位于卡山保护区的中东部，2019年其面积约占卡山保护区总面积的 $4 2 . 4 9 \%$ 。低安全区呈环带状分布于安全区外延地带，总面积 $3 8 6 3 . 5 7 ~ \mathrm { k m } ^ { 2 }$ ，占卡山保护区总面积的$2 6 . 2 0 \%$ 。在人类干扰最为严重的2010—2015年，曾有 $3 0 7 5 . 3 6 \mathrm { k m } ^ { 2 }$ 的安全区转化为低安全区，且蒙古野驴的种群数量在这一时期下降到609\~2107头[37]，明显低于2001年的种群数量2632\~4200头[36],从一定程度表明地区生态环境质量的下降。不安全区基本位于卡山保护区的西部与南部，2019年其面积为$4 6 1 6 . 6 6 \mathrm { k m } ^ { 2 }$ ,2010—2015年曾在中东部区域有所分布，主要由安全区及低安全区转移而来。

（3）根据计算，2019年，由于道路的影响，在卡山保护区中部将形成一条带状低安全区，该区域将成为保护区的生态敏感地带，是今后本地区生态安全研究的重点。

# 参考文献(References)

[1]苏芳,宋妮妮,马静,等.生态脆弱区居民环境意识的影响因素 研究——以甘肃省为例[J.十旱区资源与坏境,2020,34(5):9- 14.[Su Fang,Song Nini, Ma Jing,etal.Factors influencing the residents’environmental awareness in ecologically fragile areas of Gansu Province[J]. Journal of Arid Land Resources and Environment,2020,34(5):9-14.]

[2]卢艳丽,丁四保,王荣成,等.生态脆弱地区的区域外部性及其 可持续发展[J].中国人口·资源与环境,2010,20(7):68-73.[Lu Yanli,Ding Sibao,Wang Rongcheng,et al. Sustainable development of vulnerable ecological regions under the perspective of regional externalities[J]. China Population Resources and Environment, 2010,20(7): 68-73.]   
[3]俞孔坚.生物保护的景观生态安全格局[J].生态学报,1999(1): 10-17.[Yu Kongjian.Landscape ecological security patterns in biological conservation[J].Acta Ecological Sinica,1999(1):10-17.]   
[4]杨亮洁,王晶,魏伟,等.干旱内陆河流域生态安全格局的构建 及优化—以石羊河流域为例[J].生态学报,2020,40(17): 5915-5927.[Yang Liangjie,Wang Jing,Wei Wei,et al. Ecological security patern construction and optimization in arid inland river basin: A case study of Shiyang River Basin[J].Acta Ecological Sinica,2020,40(17): 5915-5927.]   
[5]郭利刚,冯珍珍,刘庚,等.基于物元模型的汾河流域土地生态 安全评价[J].生态学杂志,2020,39(6): 2061-2069.[Guo Ligang, Feng Zhenzhen,Liu Geng,et al. Evaluation of land eco-security in Fenhe River Basin based on mater-element model[J]. Chinese Journal of Ecology,2020,39(6): 2061-2069.]   
[6]马轩凯,高敏华.西北干旱地区绿洲城市土地生态安全动态评 价——以新疆库尔勒市为例[J].干旱区地理,2017,40(1):172- 180.[Ma Xuankai, Gao Minhua. Dynamic assessment of land ecologic safety of oasis city in arid northwest China: A case of Korla City in Xinjiang[J].Arid Land Geography,2017,40(1): 172-180.]   
[7]张丽芳,廖雨,杨存建,等.基于景观安全格局理论的寿城自然 保护区人类活动用地评价[J].水土保持通报，2019,39(6):217- 222.[Zhang Lifang,Liao Yu, Yang Cunjian,et al.Land evaluation for human activity in Shoucheng Nature Reserve based on theory of landscape safety pattern[J].Bulletin of Soil and Water Conserva tion,2019,39(3): 217-222.]   
[8]雷金睿,陈宗铸,陈毅青,等.1990—2018年海南岛湿地景观生 态安全格局演变[J].生态环境学报,2020,29(2):293-302.[Lei Jinrui, Chen Zongzhu,Chen Yiqing,et al.Dynamic analysisof wetland landscape ecological security pattern of Hainan Island in 1990——2018[J].Ecology and Environmental Sciences,2020,29 (2): 293-302.]   
[9]陈德权,兰泽英,李玮麒.基于最小累积阻力模型的广东省陆域 生态安全格局构建[J].生态与农村环境学报,2019,35(7):826- 835.[Chen Dequan, Lan Zeying, Li Weiqi. Construction of land ecological security in Guangdong Province from the perspective of

# 干旱区地理

ecological demand[J]. Journal of Ecology and Rural Environment, 2019, 35(7): 826-835.]   
[10] 李航鹤,马腾辉,王坤,等.基于最小累积阻力模型(MCR)和空 间主成分分析法(SPCA)的沛县北部生态安全格局构建研究[J]. 生态与农村环境学报,2020,36(8):1036-1045.[Li Hanghe,Ma Tenghui, Wang Kun, et al. Construction of ecological security pattern in northern Peixian based on MCR and SPCA[J].Journal of Ecology and Rural Environment,2020,36(8): 1036-1045.]   
[11]Knaapen JP,Scheffer M, Harms B.Estimating habitat isolation in landscape planning[J]. Landscape and Urban Planning,1992, 23 (1): 1-16.   
[12] 俞孔坚,王思思,李迪华,等.北京市生态安全格局及城市增长 预景[J].生态学报,2009,29(3):189-1204.[Yu Kongjian, Wang Sisi,Li Dihua,et al.The function of ecological security patterns as an urban growth framework in Beijing[J].Acta Ecological Sinica, 2009,29(3): 1189-1204.]   
[13] 袁大鹏,陈奇乐,石垚,等.河北典型样带土地利用生态安全格 局研究[J].中国生态农业学报,2019,27(11):1767-1778.[Yuan Dapeng,Chen Qile,Shi Yao,et al.Ecological security pattern of land use in a typical transect of Hebei Province[J]. Chinese Journal of Eco-Agriculture,2019,27(11): 1767-1778.]   
[14]黄木易,岳文泽,冯少茹,等.基于MCR模型的大别山核心区生 态安全格局异质性及优化[J].自然资源学报,2019,34(4):771- 784.[Huang Muyi, Yue Wenze,Feng Shaoru,et al.Analysis of spatial heterogeneity of ecological security based on MCR model and ecological pattern optimization in the Yuexi County of the Dabie Mountain area[J]. Journal of Natural Resources,2O19,34(4): 771-784.]   
[15] 岳东霞,杨超,江宝骅,等.基于CA-Markov模型的石羊河流域 生态承载力时空格局预测[J].生态学报,2019,39(6):1993- 2003.[Yue Dongxia, Yang Chao,Jiang Baohua,et al. Spatio-temporal patern prediction of the biocapacity in the Shiyang River Basin on the basis of the CA-Markov model[J].Acta Ecologica Sinica,2019,39(6): 1993-2003.]   
[16] 郝晓敬,张红,徐小明,等.晋北地区土地利用覆被格局的演变 与模拟[J].生态学报,2020,40(1):257-265.[Hao Xiaojing, Zhang Hong,Xu Xiaoming,et al.Evolution and simulation of land use/land cover pattrn in northern Shanxi Province[J]. Acta Ecological Sinica,2020,40(1): 257-265.]   
[17] 钱国英,张长勤,董斌,等.基于遥感与系统动力学模型的土地 利用/覆被变化研究[J].遥感信息,2014,29(1):44-55.[Qian Guoying,Zhang Changqin,Dong Bin,et al.Land use/land cover change based on remote sensing and system dynamics model[J]. Remote Sensing Information,2014,29(1): 44-55.]   
[18] 褚琳,张欣然,王天巍,等.基于CA-Markov 和InVEST模型的城 市景观格局与生境质量时空演变及预测[J].应用生态学报, 2018,29(12): 4106-4118.[Chu Lin, Zhang Xinran,Wang Tianwei,et al. Spatial-temporal evolution and prediction of urban landscape pattern and habitat quality based on CA-Markov and InVEST model[J].Chinese Journal of Applied Ecology，2018,29(12): 4106-4118.]   
[19]Ye B Y. Simulating land use/cover changes of Nenjiang County based on CA-Markov model[C]//Li D L. Computer and Computing Technologies in Agriculture: Proceedings of First IFIP TC 12 International Conference (CCTA2OO7). Beijing: Beijing Agricultural Internet of Things Engineering and Technology Research Center, China Agricultural University,20o7: 339-347.   
[20] 靳含,杨爱民,夏鑫鑫,等.基于CA-Markov模型的多时间跨度 土地利用变化模拟[J].干旱区地理,2019,42(6):1415-1426.[Jin Han, Yang Aimin,Xia Xinxin,et al.Simulationof land use change at different time spans based on CA-Markov model[J].Arid Land Geography,2019,42(6): 1415-1426.]   
[21］ 彭向前.准东煤电煤化工产业开发对卡拉麦里山蒙古野驴的影 响[J].新疆环境保护,2012,34(4):37-41.[Peng Xiangqian.Effect of the East Junggar coal-electricity and coal-chemical industry development on Equus hemionus in Kalamaili Mountain[J].Environmental Protection of Xinjiang,2012,34(4): 37-41.]   
[22] 闫海忠,谭森,王春,等.新疆卡拉麦里地区金矿成矿条件分析 及找矿预测[J].有色金属(矿山部分),2016,68(3):44-47.[Yan Haizhong,Tan Sen,Wang Chun, et al. Gold metallogenic condition analysis and prospecting prediction in Kalamaili region of Xinjiang[J]. Nonferrous Metals (Mining Section),2016,68(3): 44- 47.]   
[23] 张栋,路彦明,葛良胜,等.东准噶尔卡拉麦里地区金铜多金属 成矿系统和地球动力学[J].地质论评,2015,61(4):797-816. [Zhang Dong, Lu Yanming, Ge Liangsheng, et al. Metallogenic systems of polymetallic gold and copper deposits and related metallogenic geodynamic modelin Karamaili of Eastern Junggar, Xinjiang [J]. Geological Review,2015,61(4): 797-816.]   
[24]丁新.基于MAXENT对新疆卡拉麦里山自然保护区鹅喉羚生 境适宜性评价[D].哈尔滨:东北林业大学,2019.[Ding Xin. Habitat suitability assessment of Gazella subgutturosa in Karamely Nature Reserve based on MAXENT modeling[D]. Harbin: Northeast Forestry University,2019.]   
[25] 林杰,徐文轩,杨维康,等.卡拉麦里山有蹄类自然保护区蒙古 野驴生境适宜性评价[J].生物多样性,2012,20(4):411-419. [Lin Jie,Xu Wenxuan,Yang Weikang,etal. Habitatsuitabilityassessment of Equus hemionus in Kalamaili Mountain Nature Reserve[J]. Biodiversity Science,2012,20(4): 411-419.]   
[26] 初红军,蒋志刚,葛炎,等.卡拉麦里山有蹄类自然保护区蒙古 野驴和鹅喉羚种群密度和数量[J]. 生物多样性,2009,17(4): 414-422.[Chu Hongjun,Jiang Zhigang,Ge Yan,et al. Population densities and number of khulan and goitred gazelle in Mt. Kalamaili Ungulate Nature Reserve[J]. Biodiversity Science,2009,17 (4): 414-422.]   
[27]WickramasuriyaR C,Bregt A K,Van Delden H,et al. Thedynamics of shifting cultivation captured in an extended constrained cellular automata land use model[J]. Ecological Modelling,2009, 220

(18):2302-2309.

[28] Zhou L,Dang X W, Sun Q K,et al. Multi-scenario simulation of urban land change in Shanghai by random forest and CA-Markov model[J].Sustainable Citiesand Society，2020,55:102045,doi: 10.1016/j.scs.2020.102045.   
[29]Han J,Hayashi Y,Cao X,et al.Application of an integrated system dynamics and cellular automata model for urban growth assessment: A case study of Shanghai, China[J]. Landscape and Urban Planning,2009,91(3): 133-141.   
[30]Anderson T W,Goodman L A. Statistical inference about Markov chains[J].Annals of Mathematical Statistics,1957,28(1): 89-110.   
[31] 潘月,于东升,王秀虹,等.基于CA-Markov模型的土地利用景 观格局预测研究[J].土壤，2018,50(2):391-397.[Pan Yue,Yu Dongsheng,Wang Xiuhong,et al. Prediction of land use landscape pattern based on CA-Markov model[J]. Soil,2018,50(2): 391-397.]   
[32] 李莹,徐文轩,乔建芳,等.卡拉麦里山有蹄类自然保护区鹅喉 羚的时空分布与生境选择[J].干旱区地理,2009,32(2):261- 267. [Li Ying,Xu Wenxuan, Qiao Jianfang,et al. Spatio-temporal distribution and habitat selection of Gazella subgutturosa in Kalamaili Mountain Nature Reserve in four seasons[J].Arid Land Geography,2009,32(2): 261-267.]   
[33] 杨维康,徐文轩,刘伟,等.卡拉麦里山有蹄类保护区鹅喉羚的 采食地选择[J].干旱区研究,2010,27(2):236-241.[Yang Weikang,Xu Wenxuan,Liu Wei,etal.Feeding habitat characteristics of Gazella subgutturosa in the Karamaili Mountain Nature Reserve,Xinjiang[J].Arid Zone Research,2010,27(2): 236-241.]   
[34]岳建兵.卡拉麦里山有蹄类自然保护区蒙古野驴的种群数量分 布及食性选择的研究[D].北京:北京林业大学,2006.[Yue Jianbing. Stydies on the number distribution and food preference of Asiatic wild ass in Kalamaili Nature Reserve[D]. Beijing: Beijing Forestry University,2006.]   
[35] 张晓晨,邵长亮,葛炎,等.新疆卡拉麦里山有蹄类野生动物自 然保护区夏季蒙古野驴适宜生境与种群数量评估[J].应用生 态学报,2020,31(9):1-14.[Zhang Xiaochen, Shao Changliang, Ge Yan,et al. Suitable summer habitat of the Khulan in the MT. Kalamaili Ungulate Nature Reserve and estimation of its population[J]. Chinese Journal of Applied Ecology,2020,31(9): 1-14.]   
[36] 葛炎,刘楚光,初红军,等.新疆卡拉麦里山自然保护区蒙古野 驴的资源现状[J].干旱区研究,2003,20(1):32-35.[Ge Yan,Liu Chuguang,Chu Hongjun,et al. Present situation of the Equus hemionus resources in the Karamori Mountain Nature Reserve, Xinjiang[J]. Journal of Arid Land Resources and Environment, 2003,20(1): 32-35.]   
[37] 彭向前.卡拉麦里山蒙古野驴的现状与保护[J].野生动物学报, 2015,36(2):162-165.[Peng Xiangqian. The current status and protection of Asiatic wild ass (Equus hemionus) at Kalamailishan Nature Reserve[J]. Chinese Journal of Wildlife,2015,36(2):162-165.]   
[38] 尹婧博,李红,王冬艳,等.生态脆弱区生物多样性保护安全格 局研究——以吉林省大安市为例[J].资源开发与市场,2019, 35(2):38-44.[Yin Jingbo,Li Hong,Wang Dongyan,etal. Research on security pattern of biodiversity conservation in ecologically fragile regions:A case study of Da'an City in Jilin Province [J]. Resource Development & Market,2019,35(2): 38-44.]   
[39] 程迎轩,王红梅,刘光盛,等.基于最小累计阻力模型的生态用 地空间布局优化[J].农业工程学报,2016,32(16):248-257, 315.[Cheng Yingxuan,Wang Hongmei,Liu Guangsheng,et al. Spatial layout optimization for ecological land based on minimum cumulative resistance model[J]. Transactions of the Chinese Society of Agricultural Engineering,2016,32(16): 248-257,315.]   
[40] 张蕾,危小建,周鹏.基于适宜性评价和最小累积阻力模型的生 态安全格局构建—以营口市为例[J].生态学杂志,2019,38 (1): 229-236.[Zhang Lei,Wei Xiaojian, Zhou Peng. Construction of ecological security pattern based on suitability evaluation and minimum cumulative resistance model: A case study of Yingkou City[J]. Chinese Journal of Ecology,2019,38(1): 229-236.]   
[41] 陈香莲,李硕,彭向前,等.准东煤电煤化工产业开发建设对卡 拉麦里山野生动物的影响[J].干旱区资源与环境,2013,27(1): 185-189.[Chen Xianglian,Li Shuo,Peng Xiangqian, et al.The influence of coal electrical and chemical industry construction on the wild animal populations in the circumjacent regions,the east Junggar Basin[J].Journal of Arid Land Resources and Environment,2013,27(1): 185-189.]   
[42]Bannikov A G.The Asiatic wild ass[M]. Moscow: Institute of Ecological and Evolutionary Problems,1971.

# Changes of ecological security pattern in Kalamaili region based on MCR models

ZHAU Xiaoteng\*，WANG Jinlin，WANG Shanshan", WANG Shanshan1,23.4， WANG Quan   
(1.State KeyLaboratoryof DesertandOasis Ecology,Xinjiang InstituteofEcologyand Geography,ChineseAcademy   
of Sciences,Urumqi830ol1,Xinjiang,China;2.Xinjiang KeyLaboratoryof Mineral ResourcesandDigital Geology,   
Urumqi83ool1,Xinjiang,China;3.XinjiangResearch CentreforMineral Resources,Chinese AcademyofSciences, Urumqi 830o11,Xinjiang,China;4.University of Chinese Academy of Sciences,Beijing 10O049,China; 5.Shizuoka University,Shizuoka 422-8529,Japan)

Abstract: The Kalamaili Mountain Ungulate Nature Reserve (Kalamaili Reserve) is an important wildlife reserve in northern Xinjiang,China with high ecological conservation values.From 2005 to 2015,intense human development in Kalamaili region severely damaged the local ecological environment, dramatically reducing the number of khulan (Equus hemionus） and other large wildlife.Since 2O15,the quality of the Kalamaili region ecology has improved dramatically due to the development of ecological protection and restoration. Against this backdrop,the article is based on Landsat images of 1990,2000,2005,2010,2015,and 2019 and data on the natural and human condition in the study area.In adition,the Minimum Cumulative Resistance (MCR) model was used to study changes in the ecological security paterns of Kalamaili Reserve from 1990 to 2019. Furthermore,the cellular Automata-Markov (CA-Markov) model was combined to predict the ecological security patern of the region in 2O25.Next, important factors affcting the ecological securityof Kalamaili Reserve were analyzed.There is specific guiding importance for preserving the ecological environment and wildlife in Kalamaili Reserve. The results suggest that (1) ecological security pattrns can be divided into safe,low-safe,and unsafe zones. The safe zone shrank to $3 2 3 7 . 3 1 ~ \mathrm { k m } ^ { 2 }$ from 2010 to 2015,changing mainly to low-safe and unsafe Zones.Human activity during this period had a severe impact on the ecological environment of the region. (2) The area of the safe zone was $6 2 6 5 . 9 1 ~ \mathrm { k m } ^ { 2 }$ in 2019.Low-safe and unsafe zones have basically been restored to their natural state, indicating good results based on ecological governance efforts.(3）The Kalamaili Region landscape patern is not expected to change significantly by 2O25.Grasslands and unused land still dominate the region. The area of ecologically safe zone will increase to $6 4 2 1 . 8 8 ~ \mathrm { k m } ^ { 2 }$ ，and the low-safe and unsafe zones will continue to decrease. (4)Abelt of the low-safe zone will be formed nearthe trafic route in the middle of the Kalamaili Reserve,which will be the focus of future ecological monitoring and protection of the Kalamaili Reserve. (5) Human activity is a sensitive factor that affcts the ecological environment of Kalamaili Reserve.It has been suggested that future conservation effrts should continue to limit human economic development activities in Kalamaili Reserve.At the same time, it is necessary to strengthen the monitoring and inspection works around the roads in the Kalamaili Reserve,accumulate data on wildlife near the road,and provide the scientific basis for the future construction of the Kalamaili Reserve.

Key words: the celular automata-Markov (CA-Markov) model; ecological security pattern; the minimum cumulative resistance (MCR) model; Kalamaili region