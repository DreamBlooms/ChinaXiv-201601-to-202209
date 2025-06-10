# 基于3S技术的天山历史云杉林空间分布的提取

邢菲¹，李虎²，李建贵³，张乃明4，刘玉锋²，陈冬花²（1．新疆农业大学草业与环境科学学院,新疆 乌鲁木齐830052；2．滁州学院地理信息与旅游学院,安徽 滁州239000；3．新疆农业大学林业研究所,新疆 乌鲁木齐830062；4．新疆师范大学地理科学与旅游学院,新疆 乌鲁木齐830054)

摘要：运用遥感手段结合历史时期遥感影像数据,以天山云杉（Picea schrenkiana var.tianschanica）林生境特征为固定因子,结合植被指数分析、地形因子分析、主成分分析及面向对象的决策树分类的方法提取历史时期天山云杉林的空间分布信息，从而为历史资料缺失情境下的天然林资源保护工程实施效益评价提供支持。研究表明： $\textcircled{1}$ 将天山云杉林的年龄特征作为固定因子,以现状年高空间分辨率遥感影像及森林资源二类调查数据作为本底资料，在面向对象分类方法支持下可以很好的从历史时期的遥感影像中提取出天山云杉林的历史空间分布信息，提取精度可达 $9 3 . 3 \%$ $\textcircled{2}$ 在植被指数因子中,NDVI对天山云杉林指示性最好,并确定用于天山云杉林提取的最佳 NDVI值域为[0.35，0.8」； $\textcircled{3}$ 地形因子及主成分分析方法可以大大压缩影像的冗余信息，在提升云杉林信息提取的精度的同时提高运行速度。从整体来看，利用历史时期遥感影像并结合天山云杉林的生境特征,可以很好的提取出历史时期云杉林空间分布信息，从而为资料缺失情境下的森林资源管理措施制定及应对气候变化提供数据支持。

关键词：历史遥感影像；决策树分类；天山云杉林；空间分布；阜康林场

森林既是历史自然环境的反映者，也是生物圈中最富有生机和巨大生产力的生态系统(1。位于干旱区的森林更是荒漠中的“湿岛”，对于改善周边局地气候，保持土壤和涵养水源具有显著的作用。天山云杉是亚洲中部山地的特有树种，在我国仅见于新疆，并且是新疆山地森林中分布最广、蓄积量最大的树种[2]。天山云杉林是天山山地最主要的地带性植被[3],以天山云杉为主体的天山山地森林生态系统对水源的涵养起着至关重要的作用[。天山云杉在新疆主要分布于天山北麓的西坡、北坡和西北坡;天山南麓分布较少；在昆仑山西部北坡也有少量分布。

目前,关于天山[4-6]及天山云杉的种群结构特征[7-11]、生物量及变化规律(12-15]、碳储量规律[16-17]和生境特征[18-19]等已有较多研究。但天山云杉林的历史分布情况如何，在相关历史资料遗失的情况下云杉林的分布如何进行调查？基于此，本文在缺乏历史调查数据的背景下，以天山北坡中段阜康林区天山云杉林为研究对象；结合现有林业调查资料，将云杉林分布信息与空间分析技术相结合(20];并综合考虑云杉林的生理特征[21]、地形、地貌特征[2];利用植被在遥感影像上的光谱信息特征[15];以历史遥感影像为数据源,在RS 软件平台支持下利用面向对象分类模型，提取天山云杉林历史空间分布信息，在为利用遥感技术提取森林信息提供了一种新的思路的同时，为森林资源可持续经营管理和应对全球气候变化提供数据支持。

# 1研究区概况

研究区选在天山中段北麓 $8 8 ^ { \circ } 0 0 ^ { \prime } \sim 8 8 ^ { \circ } 4 2 ^ { \prime } \mathrm { E }$ ，$4 3 ^ { \circ } 3 8 \sim 4 4 ^ { \circ } 0 5 ^ { \prime } \mathrm { N }$ 的阜康林场，阜康林场始建于1956年3月，总面积 $9 2 ~ 7 5 0 . 8 6 ~ \mathrm { h m } ^ { 2 }$ （图1）。原称阜康县四工森林经营所，林场经历6次变革后至2013年转为全额事业单位，归属阜康市管辖。多次的隶属关系变更导致林场内历史数据资料丢失严重，无法满足现有森林经营规划及林业保护工程工作的需要。研究区东与吉木萨尔林场相连，西与米泉林场相邻，南为东天山主峰博格达峰，北接准噶尔盆地。研究区内森林主要是由天山云杉构成的山地寒温带性针叶林,森林带出现在海拔 $1 5 0 0 \sim 2 7 0 0 \ \mathrm { m }$ 的坡面上,面积达 $1 5 ~ 8 4 1 . 4 5 ~ \mathrm { h m } ^ { 2 } ( \$ 2016 年数据）。研究区属于温带大陆性干旱、半干旱气候,年平均气温 $1 . 2 ~ \mathrm { { ^ { c } } }$ ，年降水量 $4 0 0 ~ \mathrm { { m m } }$ ,降水年内分配不均，主要分布在夏季和冬季。研究区土壤分布呈明显的垂直地带性，由低到高依次为：山地栗钙土、山地灰褐色森林土、高山草甸土和高山石质带。

![](images/bde684f17b39c7fc5054494a336ea337e9c95ff47d8e4e8d66185545d6028ccb.jpg)  
图1研究区示意图  
Fig.1Sketch of the study area

# 2 数据与方法

# 2.1 数据源与预处理

本研究所用的数据有：遥感影像数据、森林资源二类调查数据、研究区数字高程模型（DEM）、植被指数、坡度和坡向数据。数据的来源、参数及处理方法见表1。

表1数据源、参数及处理方法  
Tab.1Data sources，parameters and processing methods   

<html><body><table><tr><td>数据类型</td><td>分辨率/时间</td><td>数据来源及处理</td></tr><tr><td>高分2号卫星影像</td><td>0.8m/2016年</td><td>0.8m高分2号遥感影像数据(2016年)来源于中国资源卫星应用中心网站，利用 GIS 和RS平台进行影像的校正、拼接及研究区范围裁剪</td></tr><tr><td>LandsatTM5影像</td><td>30 m/1994年</td><td>30m分辨率LandsatTM数据来源于USGS网站，利用GIS和RS平台进行影像的校 正、拼接及研究区范围裁剪</td></tr><tr><td>2016 年森林资源二类调查数据</td><td></td><td>1:10 000/2016年阜康林场提供,利用GIS 平台对数据进行规范化处理,并提取云杉林信息</td></tr><tr><td>数字高程模型(DEM)</td><td>30m</td><td>来源于地理空间数据云网站，利用GIS平台进行拼接和研究区范围裁剪</td></tr><tr><td>坡度</td><td>30 m</td><td>利用GIS平台根据研究区DEM数据提取</td></tr><tr><td>坡向</td><td>30 m</td><td>利用GIS平台根据研究区DEM数据提取</td></tr><tr><td>植被指数(NDVI)</td><td>30 m/1994 年</td><td>利用RS软件平台根据1994 年遥感影像提取</td></tr></table></body></html>

# 2.2 采样点选择

以研究区2016年国产高分2号 $0 . 8 \mathrm { ~ m ~ }$ 分辨率遥感影像和从2016年开展的森林资源二类调查数据中提取的云杉林为本底资料，根据云杉林生长慢的特点，剔除龄组为幼龄林的云杉林，保留林龄为中龄林、近熟林、成熟林和过熟林的云杉林以保证云杉林在近30a内不发生变化，并在每个林班内随机选择1\~2个小班的中心点作为样点数据（不区分龄级），共选择100个样点（图1），样点中主要包括经、纬度信息，树龄信息，树种信息。其中经纬度信息主要用于与地形数据及植被指数叠加时位置匹配，树龄和树种信息作为云杉林生长的固定因子，以保证该处在历史上也是云杉林不变。并依据分类样点与检验样点7:3的原则，选择70个样点作为分类样点用于天山云杉林信息提取，30个样点作为检验样点进行精度验证。

# 2.3植被指数提取

遥感图像上的植被信息主要通过绿色植物叶子和植被冠层的光谱特性及其差异、变化反映[23]。从遥感数据中获取的植被指数已经被广泛用来定性和定量评价植被覆盖度及其生长活力[24-25]。本文选取3种常用的植被指数：比值植被指数（RVI）、归一化植被指数（NDVI)和增强型植被指数（EVI)作为天山云杉林提取的候选因子，通过对比天山云杉林对不同植被指数的响应程度，最终选取一种植被指数作为云杉林提取的参数因子。3种植被指数的提取方法如下：

$$
R V I = \rho _ { \mathrm { r e d } } / \rho _ { \mathrm { n i r } }
$$

$$
N D V I = ( \rho _ { \mathrm { n i r } } - \rho _ { \mathrm { r e d } } ) / ( \rho _ { \mathrm { n i r } } + \rho _ { \mathrm { r e d } } )
$$

$E V I = G \big [ \big ( \rho _ { \mathrm { n i r } } - \rho _ { \mathrm { r e d } } \big ) / \big ( \rho _ { \mathrm { n i r } } + \lambda _ { 1 } \rho _ { \mathrm { r e d } } + \lambda _ { 2 } \rho _ { \mathrm { b } } + L \big ) \big ]$ (3)式中： $\rho _ { \mathrm { r e d } }$ 为红波段的地表反射率； $\rho _ { \mathrm { n i r } }$ 为近红外波段的地表反射率； ${ \cdot \rho _ { \mathrm { b } } }$ 为蓝波段的地表反射率; $G _ { \setminus } \lambda _ { 1 } \setminus \lambda _ { 2 }$ 和 $L$ 分别取2.5、6.0、7.5和1.0。

# 2.4地形因子提取

参照杨昕、刘娇等 $[ 2 6 - 2 7 ]$ 的理论与方法,在GIS软件平台支持下提取研究区内坡向和坡度信息。并以北方向为起点，顺时针每隔 $4 5 ^ { \circ }$ 将坡向分为北、北东、东、东南、南、南西、西、西北8个方向;根据坡度值 $< 5 ^ { \circ } , 5 ^ { \circ } \sim 1 4 ^ { \circ } , 1 5 ^ { \circ } \sim 2 4 ^ { \circ } , 2 5 ^ { \circ } \sim 3 4 ^ { \circ } , 3 5 ^ { \circ } \sim 4 4 ^ { \circ }$ 和 $> 4 5 ^ { \circ }$ 将坡度分为平、缓、斜、陡、急、险6个等级，研究区DEM、坡度、坡向如图2a1,2b1,2c1。

![](images/40844f45c8561a7df2daf3ae78774fc60ba39631992b53a644a69be0bbbe7381.jpg)  
图2研究区地形因子  
Fig.2Topographic factors in the study area

# 2.5 主成分变换

主成分分析（又称K-L变换)是一种除去波段之间的多余信息，将多波段的图像信息压缩到比原波段更有效的少数几个转换波段的方法[23]。在 RS软件平台的支持下，主成分变换操作简单、处理速度快，在遥感数据信息提取中已经取得了较好的应用效果[28-31]。通过主成分变换,可以去除噪声对地物信息的影响，将影像的主要信息压缩到第一主成分中，增强地物的细部特征，更有利于对地物的分析与提取。本研究在RS软件平台的支持下，对研究区影像进行主成分分析，以降低影像噪声的影响，从而

突出天山云杉林信息

# 3结果与分析

# 3.1 研究区植被指数

根据植被指数提取方法，在RS软件支持下根据历史遥感影像（1994年）提取得到研究区EVI、NDVI和RVI3种植被指数（图3），并将70个采样点分别与3种植被指数进行叠加分析，统计各个样点所在位置植被指数的最大值、最小值、平均值、标准差,并分别计算各采样点与EVI、NDVI和RVI的相关系数，结果如表2。

从结果的最大值最小值来看，EVI、NDVI和RVI3种植被指数均在0～1范围内，从平均值来看，NDVI的均值为0.75，而EVI和RVI的均值分别为0.21和0.15；从云杉林采样点与3种不同植被指数注：EVI为增强植被指数，NDVI为归一化植被指数，RVI为比值植被指数。

![](images/b1d66f9a625381d1e36c431743d6b39d540f583b3fa5d09a5a8955059298f1b2.jpg)  
图3植被指数提取结果(1994年)  
Fig.3Extracted results of vegetation indexes in 1994   
图4地形因子分析  
Fig.4Analysis on topographical factors

表2云杉林与植被指数叠加分析结果  
Tab.2Coupled results of vegetation indexes   

<html><body><table><tr><td>植被指数类型</td><td>最小值</td><td>最大值</td><td>平均值</td><td>标准差</td><td>相关系数</td></tr><tr><td>EVI</td><td>0.14</td><td>0.44</td><td>0.21</td><td>0.06</td><td>0.36</td></tr><tr><td>NDVI</td><td>0.03</td><td>0.87</td><td>0.75</td><td>0.05</td><td>0.45</td></tr><tr><td>RVI</td><td>0.07</td><td>0.23</td><td>0.15</td><td>0.04</td><td>-0.02</td></tr></table></body></html>

注： $E W I$ 为增强植被指数， $N D W$ 为归一化植被指数，RVI为比值植被指数。

间的相关关系来看， $N D V I > E V I > R V I$ ，且采样点与NDVI相关系数（0.45）要明显大于采样点与EVI(0.36)和 $R V I ( ~ - 0 . ~ 0 2 )$ 。综合以上分析结果,并将NDVI用于提取实验，最终得出NDVI在值域［0.35，0.8]时天山云杉林的提取效果最好。

# 3.2 研究区地形因子

根据研究区海拔、坡度和坡向提取结果，利用GIS平台的空间分析功能将研究区森林资源二类调查数据与地形因子（图 $2 \mathrm { a } 2 , 2 \mathrm { b } 2 , 2 \mathrm { c } 2 \rangle$ 分别进行叠加分析得到结果如图4。

从研究区天山云杉林分布海拔来看，有$9 6 . 2 4 \%$ 的天山云杉林分布在海拔 $1 ~ 6 0 0 \sim 2 ~ 8 0 0 ~ \mathrm { ~ m ~ }$ 范围内，且在海拔 $1 \ 0 0 0 \sim 2 \ 2 0 0 \ \mathrm { ~ m ~ }$ 范围内天山云杉林的分布随海拔高度的上升而增加，并在海拔2200$\mathbf { m }$ 达到峰值，而后随着海拔高度的上升而减少。从云杉林分布坡度来看，在陡坡分布范围最广，占总分布范围的 $3 6 . 9 1 \%$ ，其次是斜坡和急坡，分别占$2 6 . 3 4 \%$ 和 $2 1 . 0 3 \%$ ,缓坡分布较少，占 $1 1 . 3 6 \%$ ,共计 $9 5 . 6 5 \%$ 的天山云杉林分布于缓坡、斜坡、陡坡和急坡。从天山云杉林坡向分布来看，共计 $8 5 . 4 9 \%$ 的天山云杉林分布于东坡、东北坡、西北坡和北坡，其中北坡和东北坡分布最广，分别占 $2 6 . 7 2 \%$ 和$2 4 . 8 6 \%$ 。结合研究区历史遥感影像及地形因子分析结果，确定海拔区间［1550,2890]，坡度区间［5，50」，坡向区间[0，135」和225，360」作为天山云杉林历史空间分布提取因子。

# 3.3 主成分分析

根据主成分计算方法，在RS平台支持下计算影像各个主成分（表3），其中前三个主成分包含了$9 9 . 7 6 \%$ 的信息量。将信息量小而噪声大的主成分波段舍弃，保留信息量最丰富的第一、第二和第三主成分，并将采样点与主成分波段进行耦合分析（表3）。其中，第一主成分在值域[-6,40]，占总体样点的 $9 0 . 7 5 \%$ ，在大于40以后虽然占总体样点的

30 40 36.91 30 26.7224.87 24.8625 21.9221.25 35 25 1□  
2 13.10 1 26.34 21.03 20 16.15 17.75  
占10 1150 □ 9.10 0.606.0 1 20 11.36 1 占 105 4.761.518284850 51.43 2.92 0 0.00 山□□ □ L10000 2 2 2 模拨拨 平缓斜陡急险 东南西配北海拔/m 坡度/(°) 坡向/(°)

# 表3样点与第一、第二及第三主成分耦合结果

Tab.3The results of sampling sites coupled withPCA1,PCA2 andPCA3   

<html><body><table><tr><td colspan="2">PCA1</td><td colspan="2">PCA2</td><td colspan="2">PCA3</td></tr><tr><td>值域</td><td>占比/%</td><td>值域</td><td>占比/%</td><td>值域</td><td>占比/%</td></tr><tr><td>-6~9</td><td>43.40</td><td>-1~10</td><td>56.60</td><td>-23~17</td><td>45.28</td></tr><tr><td>9~24</td><td>33.96</td><td>10~21</td><td>30.19</td><td>-17~10</td><td>32.08</td></tr><tr><td>24~39</td><td>13.21</td><td>21~32</td><td>7.55</td><td>-10~3</td><td>11.32</td></tr><tr><td>39~54</td><td>5.66</td><td>32~54</td><td>3.77</td><td>-3~3</td><td>9.43</td></tr><tr><td>54~59</td><td>3.77</td><td>54~65</td><td>1.89</td><td>3~10</td><td>1.89</td></tr></table></body></html>

$9 . 4 3 \%$ ,但分布离散，在 $3 9 \sim 5 9$ 范围内只有5个样点分布;第二主成分中值域［-1,32]，占总体样点的 $9 4 . 3 4 \%$ ,在32以上只占总体样点的 $5 . 6 6 \%$ 且分布离散,在 $3 2 \sim 6 5$ 范围内只有3个样点分布；第三主成分中值域[-23,3]，占总体样点的 $9 8 . 1 1 \%$ ，在$3 \sim 1 0$ 范围内只有1个样点分布，占总体样点的

$1 . 8 9 \%$ 。

# 3.4决策树分类与结果后处理

决策树分类作为一种监督分类的专家分类方法。其方法灵活、直观、结构清晰，在处理多维问题上具有传统方法所不及的优势，而且对于不同数据源的植被分类具有一定的普适性，这些特点使得决策树分类方法在各种遥感信息提取中得到广泛应用[32-34]。在RS 软件平台支持下,将植被指数、海拔、坡度、坡向及主成分影像进行波段组合作为分类输入影像，结合研究区地形因子、植被指数和主成分分析结果，在RS软件平台支持下构建分类决策树规则（图5）。根据决策树分类规则，在RS软件中构建决策树分类模型并执行，对模型提取结果进行分类后处理得到天山云杉林历史空间分布提取结果（图5）。

![](images/953a1bd674c3dd4819150161ff2c8dbd8775d5d5d994a345dba85211d00cc467.jpg)  
图5决策树分类规则及天山云杉林历史空间分布提取结果  
Fig.5Clasificationrulesofthedecision treeandtheextractedresultsofthehistorydistributionofPiceaschrenkianaR

表4决策树分类验证   
Tab.4Verification of the decision tree classification   

<html><body><table><tr><td>耦合结果</td><td>样点个数</td><td>占比/%</td></tr><tr><td>云杉林</td><td>28</td><td>93.3</td></tr><tr><td>非云杉林</td><td>2</td><td>6.7</td></tr></table></body></html>

# 3.5 分类精度验证

以30个检验样点构建感兴趣区并利用监督分类中的最大似然法进行精度评价，结果显示：最大似然法结果总体分类精度为 $9 0 . 9 3 \%$ ,Kappa系数为0.89。同时，将相同的检验样点与天山云杉林提取结果进行耦合，记录每个检验样点所在位置的提取结果并进行统计，结果显示：在所有30个检验样点中有28个样点分为云杉林，占总体检验样点的

$9 3 . 3 \%$ ;2个样点被分为非云杉林，占总检验样点的$6 . 7 \%$ ;对比监督分类结果,决策树分类精度高出2.37个百分点，如表4所示。

# 4结论与讨论

（1）将天山云杉林与地形因子叠加分析时得出如下结果：天山云杉林分布海拔范围为 $\mathrm { ~ 1 ~ 5 5 0 ~ \sim ~ }$ $2 ~ 8 9 0 ~ \mathrm { m }$ ,坡向为 $5 ^ { \circ } \sim 5 0 ^ { \circ }$ 和 $2 2 5 ^ { \circ } \sim 3 6 0 ^ { \circ }$ 的东北坡、西北坡和少量西南坡,坡度在 $5 ^ { \circ } \sim 5 0 ^ { \circ }$ 之间。海拔范围、坡向略宽于已有研究成果，坡度与其他学者的研究结果出入不大[22,35] 。

（2）在几种常用的植被指数中，对比EVI、NDVI及RVI与云杉林的相关性，NDVI对天山云杉林的信息表达最为明显，且用于天山云杉林提取的最佳NDVI值域为[0.35,0.8]。

（3）结合云杉林生境特征，使用决策树分类方法对云杉林分布信息提取精度可达 $9 3 . 3 \%$ ，比使用传统监督分类方法精度高2.37个百分点，可以准确的提取出天山云杉林的历史空间分布信息。

（4）通过分类精度评价及其与传统方法比较，本研究所使用方法可以有效提取历史时期的天山云杉林分布信息，从而解决历史数据丢失的问题，为森林经营管理规划和应对气候变化提供数据支撑。

本研究使用的决策树分类方法对云杉林历史时期的空间分布信息的提取，取得了较好的结果。本研究区内云杉林分布特征与其他学者研究成果稍有出入，可能与天山云杉自身地理分布差异及使用的数据精度有关。通过本研究使用的方法可以提取出天山云杉林的历史分布信息，却无法得到云杉林的小班区划信息和蓄积量信息，这都有待于深入探讨。

# 参考文献（References）：

[1]《新疆森林》编辑委员会.新疆森林[M].北京：中国林业出版 社,1989:2-3.[Editorial Commitee of Xinjiang Forest.Xinjiang Forest[M].Beijing:China Forestry PublishingHouse,1989.]   
[2]唐光楚.新疆的天山云杉[J].新疆农业科学,1989(5）：32- 33.[Tang Guangchu.Picea sohrenkiana Fisch et Mey.var.tianschanica in Xinjiang[J].Xinjiang Agricultural Sciences,1989(5）： 32-33.]   
[3] 李虎,慈龙骏，方建国,等.新疆西天山云杉林生物量的动态监 测[J].林业科学,2008,44（10）:14-19.[Li Hu,Ci Longjun, FangJianguo,etal.Dynamic monitoring ofPicea schrenkiana forest biomass in west Tianshan Mountain region of Xinjiang[J].Scientia Silvae Sinicae,2008,44（10):14-19.]   
[4] 姚俊强,杨青，韩雪云，等.气候变化对天山山区高寒盆地水资 源变化的影响——以巴音布鲁克盆地为例[J].干旱区研究， 2016,33(6):1 167-1173.[Yao Junqiang,Yang Qing,Han Xueyun,et al.Impact of climate change on surface water resources in Alpine Basin in the Tianshan Mountains:A case study in the Bayanbuluk Basin[J].Arid Zone Research,2016,33（6）:1 167 - 1 173.]   
[5]王晓丽,李凯辉,宋韦,等.新疆天山北坡中段森林生态系统氮

素干沉降[J].干旱区研究，2016，33（4）：830-836.[WangXi aoli,Li Kaihui,Song Wei,et al.Atmospheric nitrogen dry depositionin forest ecosystem in the central Tianshan Mountains,Xin jiang[J].Arid Zone Research,2016,33(4):830-836.]

[6]李丽,张正勇,刘琳,等.基于DEM的天山山区气温时空模拟 研究[J].干旱区研究,2018,35（4）:855-863.[LiLi,Zhang Zhengyong,Liu Lin,et al. Spatiotemporal distribution of temperature in the Tianshan Mountains based on DEM[J].Arid Zone Research,2018,35（4):855-863.]

[7］张震,刘萍,丁易,等.天山云杉林物种组成及其种群空间分布 格局[J].南京林业大学学报（自然科学版）,2010,34（5）： 157-160.[Zhang Zhen,Liu Ping,Ding Yi,et al.Species compositions and spatial distribution pattern of tree individuals in the Schrenk spruce forest,Northwest China[J].Journal of Nanjing Forestry University（Natural Sciences Edition）,2010,34（5）:157 - 160.]   
[8]柏云龙,刘华,白志强,等.天山云杉天然林群落空间结构异质 性分析[J].植物科学学报，2012,30(6）：552-557.［BaiYunlong,Liu Hua,Bai Zhiqiang,et al. Spatial pattern heterogeneity of Piceaschrenkiana var.tianschanica natural forest in the Tianshan Mountains,Northwest China[J].Plant Science Journal,2012,30 (6) :552 -557.]   
[9］李荣,罗惠文,宋于洋,等.天山北坡天山云杉的种群结构特征 和空间分布格局[J].干旱区资源与环境,2013,27（1)：91- 96.[Li Rong,Luo Huiwen,Song Yuyang,et al. Structure characteristics and spatial distribution of Picea schrenkiana population on the northern slopes of the Tianshan Mountain[J]. Journal of Arid Land Resources and Environment,2013,27(1） :91-96.]   
[10]李明辉,何风华,刘云,等.天山云杉种群空间格局与动态[J]. 生态学报,2005,25（5）:1000-1006.[Li Minghui,He Fenghua,Liu Yun,et al. Spatial distribution pattern of tree individuals in the Schrenk spruce forest,Northwest China[J].Acta Ecologica Sinica,2005,25(5）:1000-1 006.]   
[11］李建贵,潘存德,彭世揆,等.天山云杉种群统计与生存分析 [J].北京林业大学,2001,23（1）:84－86.[Li Jiangui,Pan Cunde,Peng Shikui,et al. Demography and survival analysis of $P i$ ceaschrenkiana[J]. Journal of Beijing Forestry University,2001, 23(1) :84 -86.]   
[12]刘贵峰,刘玉平,郭仲军,等.天山云杉林生物量及其变化规律 的研究［J].西北林学院学报,2013,28（5）：13－17.〔Liu Guifeng,Liu Yuping,Guo Zhongjun,et al.Study of biomass of $P i$ cea schrenkiana var.tianschanica and its veriation[J]. Journal of Northwest Forestry University,2013,28(5):13-7.]   
[13]王燕,赵士洞.天山云杉林生物量和生产力的研究[J].应用生 态学报,1998,10(4）:389-392.[Wang Yan,Zhao Shidong.Biomass and net productivity of Picea schrenkiana var.tianshanica forest[J].Chinese Journal of Applied Ecology,1998,10（4）:389 - 392.]   
[14］张思玉,潘存德.天山云杉人工幼林相容性生物量模型[J].福 建林学院学报,2002,22（3）:201－204.[Zhang Siyu,Pan Cunde.Study on the compatible biomass model of Picea schrenkiana young plantation[J]. Jourmal ofFujian Colege of Forestry, 2002,22(3):201-204.]   
[15］陈冬花,邹陈,李滨勇,等.西天山云杉林生物量与植被指数关

系研究[J].北京师范大学学报（自然科学版）,2011,47（3）：321-325.［Chen Donghua,Zou Chen,Li Bingyong,et al.Rela-tionships between biomass and vegetation index of Picea schrenki-ana var.tianshanica in western Tianshan Mountain[J]. Journal ofBeijing Normal University（Natural Science Edition）,2O11,47(3):321-325.]

[16]包艳丽，牛树奎，张国林.天山云杉林碳储量研究[J].干旱区资源与环境,2009,23（9）：113-117.［Bao Yanli,Niu Shukui，Zhang Guolin.Study on carbon storage in the forest of Picea schren-kiana[J].Journal of Arid Land Resourcesand Environment,2009,23(9):113 -117.]

[17]范静.天山云杉林地表凋落物养分和持水性的初步研究[D]. 合肥：安徽农业大学,2O13.［FanJing.NutrientandWater-holdingCharacteristics of Litter ofPicea schrenkiana var.Tianchanica Forest in the Tianshan Mountains[D].Hefei:Anhui Agricultural University,2013.]

[18］陈迪马.天山云杉天然更新微生境及其幼苗格局与动态分析 [D].乌鲁木齐：新疆农业大学,2006.［Chen Dima.Analysis on Microsite of Picea schrenkiana Natural Regeneration and Seding Spatial Pattern and Dynamic[D]. Urumqi:Xinjiang Agricultural University,2006.]

[19]丁程锋，李霞，张绘芳.基于生境指数的天山中部云杉林潜在分布区预测[J].应用生态学报，2016，27（8）：2401-2408.[Ding Chengfeng,Li Xia,Zhang Huifang.Prediction of potentialdistribution area of the spruce forest on the central Tianshan Moun-tain based on site index[J].Chinese Journal of Applied Ecology,2016，27(8):2 401-2 408.]

[20］赵传燕，别强，彭焕华.祁连山北坡青海云杉林生境特征分析[J].地理学报,2010,65（1）：113-121.［Zhao Chuanyan,BieQiang,Peng Huanhua.Analysis of the niche space of Picea crassi-foliaon thenorthern slope of Qilian Mountains[J].Acta Geo-graphica Sinica,2010,65（1）:113-121.]

[21]宋璐.云杉属主要树种生长生理特征研究［D].兰州：甘肃农 业大学,2O15.[Song Lu.The Study on Growth and Physiological Characteristics of Main Species in Picea[D].Lanzhou:Gansu Agricultural University,2015.]

[22]张毓涛,李吉玫，常顺利.天山中部天山云杉种群空间分布格 局及其与地形因子的关系[J].应用生态学报,2011,22（11)： 2 799 -2 8O6.[Zhang Yutao,Li Jimei,Chang Shunli. Spatial distribution pattern of Picea schrenkiana var.tianshanica population and its relationships with topographic factors in middle part of Tianshan Mountain[J].Chinese Journal of Applied Ecology,2011, 22(11) :2 799 -2 806.)

[23]赵英时.遥感应用分析原理与方法：第二版[M].北京：科学出版社,2013：174-175.[Zhao Yingshi.Principlesand MethodsofAnalysis of Remote Sensing Application:2nd[M].Beijing:SciencePress,2013:174 -175.]

[24]Zhu GL,Liu YB,Ju WM,et al.Evaluation of topographic effects on four commonly used vegetation indices[J]. Journal of Remote

Sensing,2013,17(1）:210-221.

[25]田庆久，闵详军.植被指数研究进展[J].地球科学进展，1998，13（4）:327-333.[Tian Qingjiu,Ming Xiangjun.Advances instudy on vegetation indices[J].Advances in Earth Science,1998,13(4) :327 -333.)

[26］杨昕,汤国安,刘学军,等.数字地形分析的理论、方法与应用 [J].地理学报,2009,64（9）:1058-1070.[Yang Xin,Tang Guoan,Liu Xuejun,etal. Digital terrainanalysis:Theory,method and application[J].Acta Geographica Sinica,2009,64（9）: 1 058 -1070.]   
[27]刘娇,黄显峰,方国华,等.基于GIS 缓冲区功能的塔里木河中 游植被指数时空变化分析[J].干旱区研究,2018,35（1）： 171-180.[Liu Jiao,Huang Xianfeng,Fang Guohua,et al.Spatiotemporal variation of NDVI in the middle reaches of the Tarim Riverbased on GIS buffer function[J].Arid Zone Research,2O18,35 (1) :171 -180.]   
[28］陈利,林辉.基于K-T变换和主成分变换的植被信息提取[J]. 中南林业科技大学学报,2014,34(6）:81-84.[Chen Li,Lin Hui.Vegetation information extraction based on K-T transform and principal component transform[J]. Journal of Central South University of Forestry & Technology,2014,34(6）:81-84.]   
[29]徐天蜀,张王菲,岳彩荣.基于PCA 的森林生物量遥感信息模 型研究[J].生态环境,2007,16(6）:1 759-1762.[Xu Tianshu,Zhang Wangfei,Yue Cairong.Remote-sensing information model of forest biomass based on principal components analysis [J].Ecology and Environmental,2007,16(6）:1 759 -1 762.]   
[30］刘友山,吕成文,祝凤霞,等.基于PCA 和多尺度纹理特征提取 的高分辨率遥感影像分类[J].遥感技术与应用,2012,27（5）： 706-711.[Liu Youshan,Lu Chengwen,Zhu Fengxia,et al. Extraction of high spatial resolution remote sensing image classification based on PCA and multi-scale texture feature[J].Remote Sensing Technology and Application,2012,27(5）:706 -711.]   
[31]刘文雅,潘洁.基于神经网络的马尾松叶绿素含量高光谱估算 模型[J].应用生态学报,2017,28(4）：1128-1136.[LiuWenya,Pan Jie.A hyperspectral assessment model for leaf chlorophyll content of Pinus massoniana based on neural network[J].Chinese Journal of Apied Ecology,2017,28(4):1128-1136.]   
[32]McIver DK,Friedl MA. Using prior probabilitites in decision-tree classification of remotely Ssensed data[J].Remote Sensing of Environment,2002,81:253 - 261.   
[33］严恩萍.中高分辨率遥感影像阔叶林信息提取研究[D].长 沙：中南林业科技大学,2011.[Yan Enping.Study on Extraction of Based-leaved forest Information Based on Meidum and High Spatial Resolution Remote Sensing Image[D].Changsha: Central South University of Forestry and Technology,2011.]   
[34］韩婷婷,习晓环,王成,等.基于决策树方法的云南省森林分类 研究[J].遥感技术与应用,2014,29(5）:744-751.[Han Tingting,Xi Xiaohuan,Wang Cheng,et al. Study on forest classification in yunnan based on decision tree algorithm[J].Remote Sensing

Technologyand Application,2014,29(5）:744-751.][35]丁程锋，张绘芳，高亚琪,等.乌鲁木齐河流域天山云杉林空间分布格局分析——基于GIS技术的应用[J].干旱区资源与环境,2016,30（9）:190－195.[Ding Chengfeng,Zhang Huifang,

GaoYaqi,et al.The spatial distribution pattern of Picea schrenkiana var.tianschanica at Urumqi River Basin:Based on the application of GIS technology[J].Journal of Arid Land Resources and Environment,2016,30(9):190-195.]

# 3S-Based Extraction of Spatial Distribution of Picea schrenkiana var. tianschanica in History in the Tianshan Mountains

{ING Fei¹，LI Hu²，LI Jian-gui³，ZHANG Nai-ming4， LIU Yu-feng²， CHEN Dong-hua²   
1. College of GrassandandEnvironment Science，Xinjiang Agricultural University，Urumqi 830o52，Xinjiang，China;   
2.Collge of Geographical Information and Tourism，Chuzhou University，Chuzhou 2390O,Anhui，China;   
3. Institute of Forestry， Xinjiang Agricultural University， Urumqi 83oo52， Xinjiang，China；   
4.College of Geographic Science and Tourism，Xinjiang Normal University，Urumqi 830o54，Xinjiang，China)

Abstract：The spatial distribution information of Picea schrenkianavar.tianschanica in the Tianshan Mountains in historical period was extracted based on the vegetation index，topographic factor，principal componentanalysis, the decision tree classfication method and the habitat characteristics of $P$ . schrenkiana in the study area using the remote sensing methods combined with the historical remote sensing image data.So as to provide support for the benefit evaluation of the natural forest resources protection project under the situationof missing historical data.Results showed that : $\textcircled{1}$ the historical spatial distribution information of $P$ .schrenkiana in the Tianshan Mountains could be extracted from the remote sensing images，the forest stand age of $P$ . schrenkiana was set as a fixed factor, and the present remote sensing images with high spatial resolution and forest management investigation data were used as the background information. The accuracy of information extraction of $P$ .schrenkiana in the study area could be as high as $9 3 . 3 \%$ ，and the remote sensing images can be used to extract the spatial distribution information of $P$ .schrenkiana in the Tianshan Mountains; $\textcircled{2}$ In the vegetation index factors，the response of $P$ .schrenkiana in the Tianshan Mountains to NDVI was the most sensitive，and the best $N D W$ range for extracting the information of $P$ .schrenkiana in the Tianshan Mountains was $\left[ 0 . 3 5 , 0 . 8 \right]$ ; $\textcircled{3}$ Topographic factor and principal componentanalysis method could greatly compressthe redundant information of image，which improved the accuracy of information extraction of $P$ . schrenkiana forest and improved the running speed. On the whole，the spatial distribution information of $P$ . schrenkiana forest in the historical period can be well extracted by using the historical remote sensing images and combining with the habitat characteristics of $P$ .schrenkiana forest in Tianshan Mountains，so as to provide data support for the formulation of forest resource management measures and the response to climate change in the context of data missing.

Key words:historical remote sensing image；decision tree clasification；Picea schrenkiana var. tianschanica; spatial distribution；Fukang Forest Farm