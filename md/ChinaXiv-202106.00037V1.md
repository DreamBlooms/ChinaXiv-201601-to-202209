# 银川市湿地景观演变及其驱动因素

王晓峰¹²，延雨³，李月皓³，张兴³，符鑫鑫(1.长安大学土地工程学院,陕西 西安710054；2.陕西省土地整治重点实验室,陕西 西安710054;3.长安大学地球科学与资源学院，陕西 西安710054)

摘要：基于1990—2019年Landsat TM/OLI遥感影像,采用面向对象分类方法提取银川市湿地景观信息,通过景观指数、冗余分析方法定量分析研究区湿地景观演变特征及其驱动因素。结果表明：(1）银川市湿地面积由1990年的 $2 6 4 . 8 6 ~ \mathrm { k m } ^ { 2 }$ 减少到2019年的 $2 4 1 . 3 2 \mathrm { k m } ^ { 2 }$ ，减少了 $2 3 . 5 4 ~ \mathrm { k m } ^ { 2 }$ 。与1990年相比，2019年的自然湿地面积减少了$3 3 . 5 7 \mathrm { k m } ^ { 2 }$ ,人工湿地面积增加了 $1 0 . 0 3 \ \mathrm { k m } ^ { 2 }$ 。(2）1990一2019年间，银川市湿地景观的破碎化程度下降、聚集程度降低、形状逐渐不规则化、多样性与异质性增加。（3）选取12个驱动因素指标进行冗余分析，社会经济因素是湿地景观演变的主导因素,非农业人口数、水产品产量、第二产业产值与建成区面积对湿地景观变化的影响最为显著,降水量、气温等自然因素作用相对较弱。研究结果可为银川市的湿地资源的合理利用与保护提供重要参考。

关键词：湿地；景观格局；演变；驱动因素；银川市

湿地是位于陆生生态系统与水生生态系统之间的过渡性地带，在调节气候、调洪蓄水、净化水质、保护生物多样性等多个方面发挥着至关重要的作用，是自然界最富生物多样性的生态景观与人类最重要的生存环境之一[1-3]。近年来,在全球气候的变化与人类活动的影响下，湿地面积逐渐萎缩、湿地生态功能退化，湿地生态安全受到严重威胁[4-6]因此，适时监测湿地资源现状，掌握其动态变化规律，探究动态变化的驱动因素，对湿地资源的合理开发与保护具有重要意义。

湿地景观格局是指大小与形状各异的湿地景观斑块在空间上的排列，是自然、生物与社会经济因素综合作用的结果，是景观异质性的表现[7-8]。随着景观生态学理论与方法的不断发展，湿地景观格局变化研究逐渐成为湿地生态学与景观生态学的研究热点[9-I]。RS与GIS技术的迅速发展,也为湿地景观格局变化研究提供了重要的技术手段[12-13]。刘吉平等[14]基于地形图与Landsat遥感影像,分析了1954一2015年三江平原各子流域沼泽湿地时空变化特征，并定量分析了其影响因素;彭凯锋等[5]基于1995一2015年的土地利用数据和连续时间序列的水体数据集，识别了武汉城市圈湿地受损程度及其驱动机制;Jiang等[16]基于2000—2014年的Land-sat与MODIS遥感影像，对若尔盖高原沼泽湿地退化进行了风险评估。基于以往研究发现，我国开展的湿地景观研究大多集中在东北地区[17-18]、长江中下游地区[19-20]、东南部滨海地区[21-22]、青藏高原等地[23-24],对西北干旱半干旱地区内陆湿地研究较少[25]。干旱半干旱地区内陆湿地作为我国重要的湿地类型之一，不论是与东部平原湖群相比，还是与青藏高原湖群相比，其成因、分布、种类以及所产生的效益均具有鲜明的区域特性。同时，因其多分布于全球环境变化敏感区和生态环境脆弱地带，一旦破坏难以恢复，给区域生态环境与社会经济的可持续发展带来了不利影响[26-27]

银川市地处西北干旱半干旱区，黄河的不断迁移、改道与演化，农业灌溉工程的大规模开发，为其孕育了丰富的湿地资源。随着沿黄城市带的快速发展，水资源的日益紧缺，湿地面积减小、生态功能减弱等现象的日趋显著，制约着当地社会经济的发展[28]。对银川市湿地资源的深入研究,加强湿地的恢复与保护，对于改善湿地生态环境、促进银川市水资源合理利用、推进黄河流域宁夏段生态保护与高质量发展、促进银川及宁夏的社会经济发展起着举足轻重的作用[29]

本文基于1990—2019年Landsat遥感影像，依托银川市现有行政区划单元，选取5个景观指数，如斑块密度、景观形状指数、聚集度指数等，探究湿地景观时空演变及其规律，通过冗余分析方法揭示自然因素(降水量、气温、日照时数)与社会经济因素（总人口数、非农业人口数、耕地面积、各产业产值等)和湿地景观演变间的相关关系，为银川市湿地保护、管理与恢复重建提供科学依据。

# 数据与方法

# 1.1 研究区概况

银川市 $\mathrm { 1 0 5 ^ { \circ } 4 9 ^ { \prime } } \mathrm { \sim } 1 0 6 ^ { \circ } 5 3 ^ { \prime } \mathrm { E } \mathrm { , } 3 7 ^ { \circ } 2 9 ^ { \prime } \mathrm { \sim } 3 8 ^ { \circ } 5 3 ^ { \prime } \mathrm { N } )$ 位于黄河上游，宁夏引黄灌区中部，地形分为平原与山地两大部分，地势呈西南一东北向倾斜(图1）。属典型的中温带大陆型气候，日照充足、干旱少雨、蒸发旺盛。因黄河穿流而过，区域内湿地资源丰富，湿地类型多样，形成了独特的城市湿地景观。近年来，随着人口的增长与城镇化水平的提高，人地矛盾激增，围湖造田、排水垦殖等现象加剧，再加之降水量、气温等自然因素的变化，使湿地生态系统受到严重的威胁。

![](images/bef9dc361fe7137ff15aa6d9a96251e203bf4ddfd04f58f914af370e516eebe4.jpg)  
图1研究区示意图  
Fig.1 Map of the study area

# 1.2数据来源及处理

本文以Landsat系列卫星遥感影像(http://glovisusgs.gov/)作为数据源，根据银川市地表景观季相差异、天气状况、影像质量及可获取性等因素，选择

1990—2010年TM影像,2015—2019年0LI影像，影像空间分辨率为 $3 0 \mathrm { ~ m ~ }$ ，时相以9月、10月为主。经过校正、镶嵌与裁剪等处理后，计算归一化差异水体指数(MNDWI）、归一化植被指数(NDVI)、归一化建筑指数(NDBI)，并基于二进制的滤波工具（Co-occurrencemeasures)获取影像纹理特征，将以上计算结果作为输入波段参与面向对象分类过程。

以高分辨率Google影像与土地利用数据作为湿地景观提取结果的验证数据，包括1990一2000年土地利用数据，来源于中国科学院资源环境科学与数据中心(http://www.resdc.cn/）,空间分辨率为$3 0 \mathrm { m } ^ { [ 3 0 - 3 1 ] }$ 。2005——2019年Go0gle影像获取自GoogleEarth平台，空间分辨率为 $1 . 8 8 \mathrm { ~ m ~ }$ 。气象数据来源于国家气象科学数据共享网(https://data.cma.cn/），统计数据来源于《宁夏统计年鉴》和《银川统计年鉴》。

# 1.3 研究方法

1.3.1湿地景观分类系统根据《湿地公约》与国家林业局《全国湿地资源调查与检测技术规程》[32-33],结合银川市自然环境与湿地特征，借鉴现有湿地景观分类体系，将银川市湿地划分为自然湿地与人工湿地两个一级类别。其中，自然湿地包括河流湿地、湖泊湿地、沼泽湿地，人工湿地包括水库/坑塘、水产养殖地和沟渠；具体分类标准如表1所示。

表1湿地景观分类系统  
Tab.1 Classification system of wetland landscape   

<html><body><table><tr><td>一级分类 二级分类</td><td>说明</td></tr><tr><td>自然湿地河流湿地</td><td>包括永久性河流、季节性或间歇性河 流、洪泛平原湿地</td></tr><tr><td>湖泊湿地</td><td>包括永久性淡水湖、季节性淡水湖和 季节性咸水湖</td></tr><tr><td>沼泽湿地</td><td>主要以草本植物为主的沼泽湿地</td></tr><tr><td>人工湿地 水库/坑塘</td><td>以蓄水、农业灌溉、城市景观等为主 要目的的人工湿地</td></tr><tr><td>水产养殖地</td><td>以鱼、虾等水产品养殖为目的的人工</td></tr><tr><td>沟渠</td><td>湿地 以输水、灌溉为目的的沟、渠</td></tr></table></body></html>

1.3.2面向对象分类面向对象分类方法对地物光谱、形状、纹理等多元信息进行综合考虑，通过影像分割技术将遥感影像分割成一系列由相同或相似像元组成的富含多语义信息的聚类图斑对象，在一定程度上解决了基于像元分类方法的不足，提高了分类的准确性和稳定性。面向对象分类方法主要

包括影像分割与分类。

（1）影像分割

影像分割是影像中相邻同质像元合并而异质像元分离的过程，是面向对象分类的关键。其中，多尺度分割是以影像中的任意像元为起点，在波段权重、分割尺度、异质性参数的制约下，通过自上而下区域逐级合并的反复迭代，实现分割对象平均异质性最小化[34]。对象异质性是由光谱异质性与形状异质性两部分组成，计算公式为：

$$
f \mathrm { = } w h _ { \mathrm { _ { c o l o r } } } + ( 1 - w ) h _ { \mathrm { _ { s h a p e } } }
$$

式中： $f$ 为对象异质性; $w$ 为光谱异质性权重; $h _ { \mathrm { c o l o r } }$ $h _ { \mathrm { s h a p e } }$ 分别为光谱异质性和形状异质性：

$$
h _ { \mathrm { { c o l o r } } } = \sum _ { c } w _ { c } { \left[ n _ { \mathrm { { m e r g e } } } \delta _ { c } ^ { \mathrm { { \scriptsize ~ m e r g e } } } - \left( n _ { \mathrm { { o b j l } } } \delta _ { c } ^ { \mathrm { { \scriptsize ~ o b j l } } } + n _ { \mathrm { { o b j 2 } } } \delta _ { c } ^ { \mathrm { { \scriptsize ~ o b j 2 } } } \right) \right] }
$$

$$
h _ { \mathrm { { s h a p e } } } = w _ { \mathrm { { c o m p a c t } } } h _ { \mathrm { { c o m p a c t } } } + ( 1 - w _ { \mathrm { { c o m p a c t } } } ) h _ { \mathrm { { s m o o t h } } }
$$

式中： $w _ { c }$ 为 $\mid c \mid$ 波段的权重； $n _ { \mathrm { m e r g e } }$ 为合并后对象内的像元个数； $n _ { \mathrm { o b j 1 } }$ 和 $n _ { \mathrm { o b j 2 } }$ 为合并前对象的像元个数； $\delta _ { \mathrm { c } }$ 为合并后对象在 $\boldsymbol { \mathbf { \mathit { c } } }$ 波段的光谱标准差； $\delta _ { c } ^ { \mathrm { \scriptsize ~ o b j 1 } }$ 和 $\mathbf { \delta } \delta _ { c } ^ { \mathrm { \scriptsize ~ o b j 2 } }$ 为合并前对象在 $\boldsymbol { \mathbf { \mathit { c } } }$ 波段的光谱标准差; $w _ { \mathrm { c o m p a c t } }$ 为紧致度异质性权重； $h _ { \mathrm { c o m p a c t } }$ 为紧致度异质性，表示对象形状接近圆形和接近正方形的程度； $h _ { \mathrm { s m o o t h } }$ 为光滑度异质性，表示对象边界的破碎程度。

$$
h _ { \mathrm { c o m p a c t } } = n _ { \mathrm { m e r g e } } \frac { l _ { \mathrm { m e r g e } } } { \sqrt { n _ { \mathrm { m e r g e } } } } - \left( n _ { \mathrm { o b j 1 } } \frac { l _ { \mathrm { o b j 1 } } } { \sqrt { n _ { \mathrm { o b j 1 } } } } + n _ { \mathrm { o b j 2 } } \frac { l _ { \mathrm { o b j 2 } } } { \sqrt { n _ { \mathrm { o b j 2 } } } } \right)
$$

$$
h _ { \mathrm { { s m o o t h } } } = n _ { \mathrm { { m e r g e } } } \frac { l _ { \mathrm { { m e r g e } } } } { b _ { \mathrm { { m e r g e } } } } - \left( n _ { \mathrm { { o b j l } } } \frac { l _ { \mathrm { { o b j l } } } } { b _ { \mathrm { { o b j l } } } } + n _ { \mathrm { { o b j 2 } } } \frac { l _ { \mathrm { { o b j 2 } } } } { b _ { \mathrm { { o b j 2 } } } } \right)
$$

式中： $n$ 为对象像元个数； $l$ 为对象的周长； $b$ 为对象外接矩形的周长。

研究区湿地景观斑块大小与形状各异，利用多尺度分割技术生成三种不同尺度的分割对象层，基于不同的影像分割层实现湿地景观的分类提取。经多次尝试，确定50、100、150三个影像分割尺度。在尺度为50的影像分割层中剔除非湿地景观信息，提取沼泽湿地；在尺度为100的影像分割层中提取湖泊湿地、水库/坑塘、水产养殖地；在尺度为150的影像分割层中提取河流湿地与沟渠。

# （2）影像分类

影像分割后，依据地物多元特征信息，逐级构建湿地分类规则体系,实现湿地的准确分类。eCog-nition软件中包括阈值分类、最邻近分类、隶属度函数分类等方法。最邻近分类实质上是对地物进行传统的监督分类;隶属度函数分类是利用模糊数学方法来构造隶属函数，函数返回值在[0,1]范围内，通过函数返回值表征对象的某一特征属性，最终确定对象的归属类别[35]。本文应用阈值分类与隶属度函数分类方法，以影像分割对象为基本单元，综合对象的光谱、纹理与形状特征差异，确定隶属度函数类型与特征阈值，构建湿地分类规则集(图2)。

注：MNDWI表示归一化差异水体指数;NDVI表示归一化植被指数；NDBI表示归一化建筑指数;Area表示影像对象面积;Dissimilatity表示相异性纹理滤波;Ellipitic Fit表示影像对象椭圆拟合度;Density表示影像对象密度；Length/width表示影像对象长宽比。

![](images/ea6d366140eb4e9bb8b42d76722eeb996eedd2347b56cd03be47cd96e892b26a.jpg)  
图2湿地分类规则集  
Fig.2 Wetland classification rule

1.3.3景观格局演变分析景观指数高度浓缩了景观格局信息，是反映其结构组成与空间配置特征的简单定量指标[36]。根据各景观指数的生态意义、彼此间的相互独立性及其对银川市湿地景观格局变化的响应敏感程度，从类型水平与景观水平上选择：斑块密度（PatchDensity，PD）、景观形状指数(Landscape Shape Index,LSI）、聚集度指数（Aggrega-tionIndex，AI）、斑块结合度指数(PatchCohesionIn-dex，COHESION）、香农多样性指数（Shannon'sDi-versityIndex,SHDI),对银川市湿地景观格局演变特征进行定量分析。采用Fragstats4.2软件计算各景观指数，计算公式参见文献[37]。

1.3.4冗余分析冗余分析(Redundancy Analysis,RDA)是生态学中常用的一种直接梯度排序分析法，该方法对多个解释变量与响应变量进行多元回归分析，用以寻找潜在的最大程度能够解释响应变量变化过程的一系列解释变量的线性组合，并以二维排序图的形式可视化解释变量与响应变量间的关系[38-39]。本研究运用CANOCO4.5软件对湿地景观数据矩阵与驱动因素数据矩阵进行除趋势对应分析（Detrended Correspondence Analysis,DCA）,得到排序轴的梯度均小于3,确定选用冗余分析方法。变差分解是一种量化分析多个变量或变量组单独或共同解释响应变量变差比例的方法[40],为探究各驱动因素对湿地景观变化的独立贡献率、交互贡献率以及未能解释的部分，本文基于R4.0.1和Vegan包进行变差分解，确定能够较好解释影响湿地景观变化的驱动因素并计算其贡献率大小。

# 2结果与分析

# 2.1湿地分类精度评价

利用ArcGIS10.2软件的CreateRandomPoints工具随机生成500个样本点，根据银川市各年高分辨率Google影像和土地利用数据，确定样本点处湿地景观类型，生成混淆矩阵对面向对象分类结果进行精度评价。评价指标包括：用户精度(UA）、制图精度(PA）、总体精度(OA)与Kappa系数。如表2所示，银川市1990—2019年各时期湿地信息提取结果的总体精度均大于 $8 0 \%$ ,Kappa系数大于0.75,满足本研究的需求。

# 2.2湿地时空动态变化

银川市湿地呈面积分布的不均匀性与空间分布的差异性(图3)。河流湿地、水产养殖地为银川市主要湿地类型，2019年分别占湿地总面积的$2 9 . 9 3 \% . 2 4 . 8 3 \%$ 。河流湿地以黄河为主，主要分布在灵武市、永宁县、兴庆区、贺兰县；得黄河灌溉之利，历代人民对宁夏平原农田灌溉工程的大规模开发，逐渐形成了完整的灌排体系；湖泊湿地、沼泽湿地、水库/坑塘、水产养殖地星罗棋布，湖泊湿地与水产养殖地主要分布在贺兰县、永宁县、兴庆区，水库/坑塘和沼泽湿地呈零星分布。

1990—2019年，银川市各湿地类型面积统计如表3所示。 $3 0 \mathrm { a }$ 来，银川市湿地总面积呈减少趋势，减少了 $2 3 . 5 4 ~ \mathrm { k m } ^ { 2 }$ ;1990一2000年，湿地面积呈快速下降的趋势，由1990年的 $2 6 4 . 8 6 \mathrm { k m } ^ { 2 }$ 减小到2000年的 $2 3 2 . 3 6 ~ \mathrm { k m } ^ { 2 }$ ，减少了 $3 2 . 5 0 \ \mathrm { k m } ^ { 2 } ; 2 0 0 0 - 2 0 1 9$ 年，湿地面积呈缓慢恢复的趋势，至2019年银川市湿地面积 $2 4 1 . 3 2 ~ \mathrm { k m } ^ { 2 }$ ，与2000年相比，湿地面积增加了$8 . 9 6 \mathrm { k m } ^ { 2 }$ 。

从湿地类型来看，1990—2019年，人工湿地面积逐渐增加，共增加了 $1 0 . 0 3 \ \mathrm { k m } ^ { 2 }$ ;其中，沟渠面积由1990年 $2 1 . 4 9 \ \mathrm { k m } ^ { 2 }$ ，占比为 $8 . 1 1 \%$ ,增加到2019年的$3 2 . 5 4 \mathrm { k m } ^ { 2 }$ ，占比为 $1 3 . 4 9 \%$ ,共增加了 $1 1 . 0 5 \mathrm { k m } ^ { 2 }$ ;水产养殖地面积由1990年的 $5 7 . 7 3 \ \mathrm { k m } ^ { 2 }$ ，占比为 $2 1 . 8 1 \%$ ，增加至2005年的最大值 $7 4 . 7 0 \mathrm { k m } ^ { 2 }$ ,占比为 $3 0 . 5 4 \%$ ，2005—2019年,水产养殖地面积减少了 $1 4 . 7 7 ~ \mathrm { k m } ^ { 2 }$ 水库/坑塘面积由1990年的 $2 1 . 9 8 \mathrm { k m } ^ { 2 }$ 减少为2019年的 $1 8 . 7 6 \mathrm { k m } ^ { 2 }$ ,减少了 $3 . 2 2 \mathrm { k m } ^ { 2 }$ 。自然湿地面积变化呈相反趋势。1990一2000年，由于人口的持续增长、土地资源的不合理利用、再加之居民生态环境保护意识较差，大片河流、沼泽等自然湿地被迫转为其他土地利用类型。10a间，自然湿地面积共减少了 $3 6 . 6 4 \mathrm { ~ k m } ^ { 2 }$ ，其中，河流湿地、湖泊湿地面积分别减少了 $3 5 . 5 9 \ \mathrm { k m } ^ { 2 } , 2 . 9 2 \ \mathrm { k m } ^ { 2 } ; 2 0 0 0 - 2 0 1 9$ 年，随着国家林业局的高度重视当地居民环保意识的提高，银川市进行了科学规划并实施了多项湿地保护与恢复建设措施，以及当地节水农业灌溉技术的发展与水资源的合理利用，使湖泊、河流等自然湿地生态

表2面向对象分类精度评价  
Tab.2 Accuracy assessment of Object-oriented classification   

<html><body><table><tr><td>年份</td><td>指标</td><td>河流湿地/%</td><td>湖泊湿地/%</td><td>沼泽湿地/%</td><td>水库/坑塘/%</td><td>水产养殖地/%</td><td>沟渠/%</td><td>0A/%</td><td>Kappa</td></tr><tr><td rowspan="2">1990</td><td>UA</td><td>83.33</td><td>80.56</td><td>77.78</td><td>88.10</td><td>87.90</td><td>85.71</td><td rowspan="2">85.65</td><td rowspan="2">0.80</td></tr><tr><td>PA</td><td>88.24</td><td>80.47</td><td>84.85</td><td>86.05</td><td>88.62</td><td>80.00</td></tr><tr><td rowspan="2">1995</td><td>UA</td><td>76.19</td><td>85.23</td><td>79.07</td><td>83.70</td><td>88.37</td><td>76.47</td><td rowspan="2">84.66</td><td rowspan="2">0.79</td></tr><tr><td>PA</td><td>80.00</td><td>80.65</td><td>77.27</td><td>88.28</td><td>86.86</td><td>81.25</td></tr><tr><td rowspan="2">2000</td><td>UA</td><td>76.92</td><td>84.48</td><td>84.09</td><td>87.94</td><td>85.37</td><td>84.62</td><td rowspan="2">85.71</td><td rowspan="2">0.81</td></tr><tr><td>PA</td><td>83.33</td><td>85.96</td><td>82.22</td><td>86.11</td><td>87.50</td><td>78.57</td></tr><tr><td rowspan="2">2005</td><td>UA</td><td>81.82</td><td>80.77</td><td>82.61</td><td>89.22</td><td>82.76</td><td>77.78</td><td rowspan="2">85.09</td><td rowspan="2">0.79</td></tr><tr><td>PA</td><td>85.71</td><td>81.55</td><td>83.82</td><td>88.46</td><td>81.36</td><td>82.35</td></tr><tr><td rowspan="2">2010</td><td>UA</td><td>82.61</td><td>83.33</td><td>78.43</td><td>88.95</td><td>81.03</td><td>86.67</td><td rowspan="2">84.91</td><td rowspan="2">0.79</td></tr><tr><td>PA</td><td>86.36</td><td>80.81</td><td>86.96</td><td>87.50</td><td>82.46</td><td>81.25</td></tr><tr><td rowspan="2">2015</td><td>UA</td><td>80.77</td><td>85.09</td><td>81.40</td><td>87.39</td><td>84.81</td><td>78.95</td><td rowspan="2">84.75</td><td rowspan="2">0.80</td></tr><tr><td>PA</td><td>80.77</td><td>83.62</td><td>81.40</td><td>89.66</td><td>82.72</td><td>83.33</td></tr><tr><td rowspan="2">2019</td><td></td><td></td><td>77.11</td><td>84.85</td><td>91.96</td><td></td><td></td><td rowspan="2">87.43</td><td rowspan="2">0.78</td></tr><tr><td>UA</td><td>85.71</td><td></td><td></td><td></td><td>80.85</td><td>76.92</td></tr><tr><td></td><td>PA</td><td>80.00</td><td>84.21</td><td>84.85</td><td>89.94</td><td>80.85</td><td>83.33</td><td></td><td></td></tr></table></body></html>

![](images/77bb942f75f6c03f004ec6de12ebfc6ff12b59aa351ecd9a5557aaecf0f9faf7.jpg)  
图3银川市湿地空间分布  
Fig.3Spatial distribution of Yinchuan wetland

表3银川市湿地面积变化  
Tab.3 Change of wetland area in Yinchuan   

<html><body><table><tr><td>年份</td><td>面积及占比</td><td>河流湿地</td><td>湖泊湿地</td><td>沼泽湿地</td><td>水库/坑塘</td><td>水产养殖地</td><td>沟渠</td><td>总计</td></tr><tr><td rowspan="2">1990</td><td>面积/km²</td><td>111.88</td><td>37.13</td><td>14.65</td><td>21.98</td><td>57.73</td><td>21.49</td><td>264.86</td></tr><tr><td>比例/%</td><td>42.24</td><td>14.02</td><td>5.53</td><td>8.30</td><td>21.80</td><td>8.11</td><td>100</td></tr><tr><td rowspan="2">1995</td><td>面积/km²</td><td>90.86</td><td>37.32</td><td>15.05</td><td>20.22</td><td>66.43</td><td>20.31</td><td>250.20</td></tr><tr><td>比例/%</td><td>36.32</td><td>14.92</td><td>6.02</td><td>8.08</td><td>26.55</td><td>8.12</td><td>100</td></tr><tr><td rowspan="2">2000</td><td>面积/km²</td><td>76.29</td><td>34.21</td><td>16.52</td><td>18.77</td><td>64.25</td><td>22.32</td><td>232.36</td></tr><tr><td>比例/%</td><td>32.83</td><td>14.72</td><td>7.11</td><td>8.08</td><td>27.65</td><td>9.61</td><td>100</td></tr><tr><td rowspan="2">2005</td><td>面积/km²</td><td>71.19</td><td>43.76</td><td>15.87</td><td>17.38</td><td>74.70</td><td>21.69</td><td>244.60</td></tr><tr><td>比例/%</td><td>29.11</td><td>17.89</td><td>6.49</td><td>7.11</td><td>30.54</td><td>8.87</td><td>100</td></tr><tr><td rowspan="2">2010</td><td>面积/km²</td><td>73.37</td><td>46.66</td><td>14.99</td><td>17.62</td><td>68.55</td><td>31.33</td><td>252.52</td></tr><tr><td>比例/%</td><td>29.06</td><td>18.48</td><td>5.93</td><td>6.98</td><td>27.15</td><td>12.41</td><td>100</td></tr><tr><td rowspan="2">2015</td><td>面积/km²</td><td>70.10</td><td>52.07</td><td>11.43</td><td>16.41</td><td>61.13</td><td>30.07</td><td>241.19</td></tr><tr><td>比例/%</td><td>29.06</td><td>21.59</td><td>4.74</td><td>6.80</td><td>25.34</td><td>12.47</td><td>100</td></tr><tr><td rowspan="2">2019</td><td>面积/km²</td><td>72.23</td><td>46.99</td><td>10.87</td><td>18.76</td><td>59.93</td><td>32.54</td><td>241.32</td></tr><tr><td>比例/%</td><td>29.93</td><td>19.47</td><td>4.50</td><td>7.77</td><td>24.83</td><td>13.49</td><td>100</td></tr></table></body></html>

环境得到了有效改善。

通过1990—2019年湿地类型数据叠加分析得到银川市湿地类型变化空间分布图(图4)。30a来，银川市共有 $1 . 5 0 \mathrm { k m } ^ { 2 }$ 湿地区域转为非湿地区域，有$1 . 2 8 \ \mathrm { k m } ^ { 2 }$ 非湿地区域转为湿地区域，湿地转出面积大于转入面积,湿地面积逐渐减少。从湿地类型来看，自然湿地转出面积大于转入面积，有 $0 . 6 8 \mathrm { k m } ^ { 2 }$ 的河流湿地、 $0 . 0 2 \mathrm { k m } ^ { 2 }$ 的湖泊湿地与 $0 . 0 6 \mathrm { k m } ^ { 2 }$ 的沼泽湿地转出为耕地、建设用地、草地等其他地类；人工湿地转入面积大于转出面积，分别有 $0 . 1 6 \ \mathrm { k m } ^ { 2 } , 0 . 1 6$ $\mathrm { k m } ^ { 2 } , 0 . 1 3 \mathrm { ~ k m } ^ { 2 }$ 的其他土地利用类型转入为水库/坑塘、水产养殖地、沟渠。

银川市湿地类型变化具有空间异质性。黄河的来回摆动，造成了河流湿地的频繁转入转出。河流湿地的变化主要分布在兴庆区、灵武市、永宁县，转出面积分别为 $0 . 2 9 \ \mathrm { \ k m } ^ { 2 } \setminus 0 . 1 6 \ \mathrm { \ k m } ^ { 2 } \setminus 0 . 1 3 \ \mathrm { \ k m } ^ { 2 }$ 2000一2019年，在当地人民实施湿地保护与恢复措施的影响下，湿地生态环境得到了显著改善，湖泊湿地变化主要发生在兴庆区、金凤区、贺兰县与灵武市，转入面积大于转出面积。受退渔还湖政策的影响，水产养殖地主要呈转出趋势，主要发生在兴庆区与贺兰县。水库/坑塘与沟渠呈转人趋势，但变

化幅度较小。

# 2.3湿地景观格局变化

2.3.1类型水平上的湿地景观格局变化不同时期湿地景观类型水平上的景观指数变化趋势如图5所示。从类型水平的景观指数分析银川市不同湿地类景观格局演变特征。斑块密度(PD)是对景观破碎化程度的度量。由图5a可知，1990—2019年，银川市水库/坑塘、湖泊湿地、水产养殖地的PD值波动幅度较大，破碎化程度变化显著;其中，水库/坑塘与湖泊湿地的PD值先减小后增大，1990年水库/坑塘的PD值为4.87个， $\mathrm { k m } ^ { - 2 }$ ,2010年降至最低值2.32个·$\mathrm { k m } ^ { - 2 }$ ,2019年增加至3.06个· $\mathrm { k m } ^ { - 2 }$ ;1990年湖泊湿地的PD值为0.98个· $\mathrm { k m } ^ { - 2 }$ ,2000年降至最低为0.49个·$\mathrm { k m } ^ { - 2 }$ ,2019年增加至0.89个 $ { \mathrm { k m } } ^ { - 2 }$ ;水产养殖地的PD值呈连续下降的趋势，1990年为0.78个· $\mathrm { k m } ^ { - 2 }$ ,2019年减小为0.42个· $\mathrm { k m } ^ { - 2 }$ ;河流湿地、沼泽湿地、沟渠的PD曲线波动较小，破碎化程度变化不显著

景观形状指数(LSI)表征景观形状的复杂性。由图5b可知，1990—2019年沟渠、湖泊湿地、河流湿地、沼泽湿地的LSI值增加，1990年LSI值分别为80.08、25.46、20.11、12.31，分别增加至2019年的88.90、26.18、30.89、14.29;水产养殖地与水库/坑塘的LSI值减小，分别由1990年的23.59、42.86，减少至2019年的15.45、36.00;各湿地类型LSI曲线波动均较小,景观斑块的复杂性变化幅度较小。

![](images/66c8ba8303cd21e0dd34db9f6275293accd946db6d172f687efc00adadf538a1.jpg)  
图41990—2019年银川市湿地类型变化空间分布  
Fig.4 Spatial distribution of wetland type change in Yinchuan from 1990 to 2019

![](images/2fbb8355c9c60839b04976f23b95290ed01da8e595add56759ba012dc9a78238.jpg)  
图5类型水平上的景观指数变化  
Fig.5The landscape index change in class level

聚集度指数(AI)用以表征景观类型间的聚集程度。由图5c可知，30a来，河流湿地、湖泊湿地、水产养殖地、沼泽湿地的聚集程度较高且变化幅度较小；沟渠的AI值最低，聚集程度最低，2005—2010年沟渠的AI值显著增加，聚集程度增加，人为干扰强度减弱。

斑块结合度指数(COHESION)用以度量景观斑块间的自然连通性。由图5d可知，1990—2019年，水库/坑塘的COHESION值最低，斑块间的连通性较差。河流湿地、沟渠、水产养殖地、湖泊湿地、沼泽湿地的COHESION值有不同程度的减小，但变化幅度较小，连通性仍较高。

2.3.2景观水平上的湿地景观格局变化景观水平上的景观指数可以反映区域整体的景观格局特征。由表4可知，1990—2019年银川市湿地景观的斑块密度(PD)总体波动下降，表明湿地景观破碎度下降。景观形状指数(LSI)整体呈增加的趋势，1990—2000年，由70.98减小至65.69，到2019年增加至81.18，说明景观形状复杂性先降低后逐渐趋于不规则化。聚集度指数(AI)逐渐减小，说明湿地景观间的聚集程度逐渐降低。香农多样性指数(SHDI)呈现上升趋势，与聚集度指数呈相反的变化趋势，表明此阶段银川市湿地景观多样性与异质性增加。30a来，银川市湿地景观破碎化程度下降、聚集程度降低、形状趋于复杂、多样性与异质性增加。

表4景观水平上的景观指数变化  
Tab.4 Landscape index change in landscape level   

<html><body><table><tr><td>年份</td><td>PD/(个·km-2)</td><td>LSI</td><td>AI/%</td><td>SHDI</td></tr><tr><td>1990</td><td>6.99</td><td>70.98</td><td>97.85</td><td>0.74</td></tr><tr><td>1995</td><td>6.96</td><td>72.10</td><td>97.81</td><td>0.77</td></tr><tr><td>2000</td><td>5.42</td><td>65.69</td><td>97.87</td><td>0.77</td></tr><tr><td>2005</td><td>4.52</td><td>68.23</td><td>97.82</td><td>0.78</td></tr><tr><td>2010</td><td>4.66</td><td>73.27</td><td>97.71</td><td>0.79</td></tr><tr><td>2015</td><td>4.51</td><td>78.04</td><td>97.49</td><td>0.78</td></tr><tr><td>2019</td><td>5.01</td><td>81.18</td><td>97.40</td><td>0.78</td></tr></table></body></html>

# 2.4驱动因素分析

湿地景观演变受多因素的综合作用。本文通过冗余分析方法揭示自然因素(降水量、气温、日照时数)与社会经济因素(总人口数、非农业人口数、耕地面积、各产业产值等)和湿地景观演变间的相关关系。对湿地景观数据矩阵与驱动因素数据矩阵进行RDA排序(表5)，蒙特卡罗置换检验结果表

# 表5冗余分析

Tab.5 Redundancy analysis   

<html><body><table><tr><td>排序轴</td><td>特征值</td><td>湿地景观-驱动 因素相关系数</td><td>湿地景观变化 累积百分比</td><td>湿地景观-驱动 因素关系变化</td><td>特征值总和</td><td>典型特征</td><td colspan="2">蒙特卡罗置换检验</td></tr><tr><td></td><td></td><td></td><td></td><td>累积百分比</td><td></td><td>值总和</td><td>第一排序轴 显著性检验</td><td>所有排序轴 显著性检验</td></tr><tr><td>Axis1</td><td>0.62</td><td>0.99</td><td>61.60</td><td>66.20</td><td rowspan="4"></td><td rowspan="4">0.93</td><td rowspan="4">F=25.66</td><td rowspan="4">F=17.69</td></tr><tr><td>Axis2</td><td>0.23</td><td>0.95</td><td>84.30</td><td>90.60</td></tr><tr><td>Axis3</td><td>0.04</td><td>0.90</td><td>88.70</td><td>95.40</td></tr><tr><td>Axis4</td><td>0.04</td><td>0.85</td><td>92.70</td><td>99.70</td></tr></table></body></html>

明，所有排序轴的显著性检验均达到极显著( $P <$ 0.01)，表明RDA排序结果可信，可以较好地解释湿地景观与驱动因素间的关系。第一、二排序轴特征值分别为0.62、0.23，湿地景观与驱动因素相关系数分别为0.99、0.95，前两个排序轴对湿地景观变化的累计解释量达到 $8 4 . 3 \%$ ,对湿地景观与驱动因素关系变化的累计解释量达到 $9 0 . 6 0 \%$ ,说明第一、二排序轴能够很好地反映湿地景观与驱动因素间的关系，且主要由第一排序轴决定。

由图6a可知，湿地景观变化过程主要受非农业人口数、总人口数、水产品产量、各产业产值、建成区面积等因素的影响。通过各驱动因素与排序轴的相关性大小可知，第一排序轴与总人口数、非农业人口数、水产品产量、各产业产值和建成区面积呈极显著正相关 ${ \bf \Phi } _ { r > 0 . 9 0 } )$ ，与日照时数呈显著负相关 $\scriptstyle ( - - 0 . 4 3 )$ ，说明第一排序轴主要反映了总人口数、非农业人口数、水产品产量、各产业产值、建成区面积以及日照时数的综合变化情况；第二排序轴与粮食产量呈显著正相关( $\scriptstyle ( - 0 . 5 9 )$ ，说明第二排序轴主要反映了粮食产量的变化情况。从各因素贡献率来看，非农业人口数对湿地景观变化贡献率最大，为 $6 0 . 9 0 \%$ ,其次总人口数、水产品产量、第一产业产值、建成区面积、第二产业产值、第三产业产值的贡献率分别为 $6 0 . 5 0 \% , 5 9 . 9 0 \% , 4 9 . 1 0 \% , 5 8 . 3 0 \%$ $5 7 . 1 0 \%$ ） $. 5 5 . 4 0 \%$ ○

因各驱动因素间的交互作用，所得驱动因素贡献率之和远大于 $100 \%$ ,为进一步探明各因素的独立贡献率、因素间的交互贡献率以及因素未能解释的部分，本研究基于R4.0.1和Vegan包，选择贡献率较大的非农业人口数，水产品产量、第二产业产值、建成区面积进行变差分解。结果如图6b所示，非农业人口数、水产品产量、第二产业产值、建成区面积的交互贡献率包括4个因素的独立贡献率( $2 . 5 6 \% +$ $1 6 . 6 5 \% + 1 9 . 0 0 \% - 0 . 6 8 \% ,$ ,任意两个因素的交互贡献率 $( - 0 . 9 2 \% + 3 . 8 4 \% + 0 . 5 9 \% + 6 . 7 7 \% - 1 . 0 6 \% + 0 . 3 8 \%$ ），任意三个因素的交互贡献率 $( - 4 . 8 1 \% + 4 . 7 7 \% +$

注：图6a中 $P r e$ 表示降水量;Temp表示气温； $S u n$ 表示日照时数； $P o p$ 表示总人口数;Napop表示非农业人口数； $C a$ 表示耕地面积;  
$A p y$ 表示水产品产量; $G y$ 表示粮食产量； $P i$ 表示第一产业产值; $S i$ 表示第二产业产值; $\boldsymbol { { \mathit { T } } } _ { i } ^ { \phantom { \dagger } }$ 表示第三产业产值； $D a c$ 表示建成区面积。图6b中变差分解小于0的值未显示。

![](images/2f0d39d1cb1b403f6a7384afd12ddae9b985778cb82d73f8ebe9638e7dfb6aa6.jpg)  
图6冗余分析二维排序图(a)与变差分解(b)  
Fig.6Redundancy analysis ranking map and decomposition of variation

$2 1 . 9 5 \% - 3 . 9 2 \%$ )以及4个因素的交互贡献率（ $1 0 . 9 5 \%$ ),4个驱动因素的累积贡献率为 $7 6 . 0 6 \%$ ,存在 $2 3 . 9 4 \%$ 的残差不能被非农业人口数、水产品产量、第二产业产值、建成区面积所解释。

# 3讨论

本文基于面向对象分类方法，采用景观指数法探讨银川市湿地景观演变规律。结果表明，30a来，银川市自然湿地面积不断减少，人工湿地面积持续增加，湿地总面积减少。宫宁、牛振国等在中国湿地时空演变研究中表明，随着全球变化与中国经济的快速发展，中国湿地呈自然湿地持续减少与人工湿地持续增加的趋势[5.41]；同时，各省市湿地变化研究表明，1990—2000年宁夏湿地总面积减小幅度较大，2000年后湿地面积有所恢复。这与本文1990—2000年湿地面积迅速缩小，2000年后，在退田还湖、河湖清淤等人为干预下，湿地面积有所恢复的结论相同。

本文分别从类型水平和景观水平上对湿地景观格局变化进行分析。30a来，银川市湿地景观破碎化程度下降、聚集程度降低、形状趋于复杂、多样性与异质性增加。城镇化过程中对湿地斑块的侵占与当地气候的逐渐暖干化，使湿地斑块数量减少、破碎化程度降低，有利于湿地间的物质交换与能量流动；人为活动的干扰与自然因素的影响，湿地斑块形状逐渐不规则化，湿地的多样性与异质性增加，导致湿地生态系统的稳定性与自我恢复能力减弱。相关研究表明，景观格局的变化对生态系统结构、功能与稳定性均会产生不同程度的影响。如黄宁等[42]对厦门市海岸带景观格局变化研究表明,海岸带自然景观的连通度、破碎度、分离度与景观形状的变化对自然生态系统结构、功能和稳定性产生了不利影响;许吉仁等[43]对南四湖湿地景观格局变化研究表明，湖泊湿地的生物多样性保护、土壤保持、水源涵养等服务功能均会受到湿地景观格局变化的影响；张双双等[44对升金湖湿地景观格局研究表明，升金湖湿地景观破碎化程度增大，导致湖泊湿地的生境质量变差。本文仅对湿地景观格局变化作了简单的分析，景观格局变化对生态系统的影响有待进一步的探索。

银川市湿地景观是自然因素与社会经济因素综合作用的结果，并以社会经济因素为主导，这与王朔、张美美等[45-46]对银川平原湿地景观研究结论相类似。本文通过RDA分析了银川市湿地景观演变与自然、社会经济因素间的关系，结果表明，非农业人口数、水产品产量、第二产业产值与建成区面积的变化对湿地景观变化影响较大。人口的持续增长,耕地、建设用地需求增大,围湖造田、改湖建塘、城市扩张，侵占了大量的湿地资源;水产养殖地、水库/坑塘等人工湿地的增加,在一定程度上可解决居民的生活需求，促进区域经济的发展，但人工湿地受人为和季节因素的影响较大，具有较强的不稳定性，其生物多样性保护、水源涵养等生态功能不及自然湿地，造成该地区湿地生态功能下降;各产业的快速发展,农药、化肥不合理使用、工业废气、废水、废渣不达标排放、旅游业过度开发，以及人类生活生产需水量的增加,对湿地生态环境产生了严重威胁。此外，区域水文生态过程,如黄河干流宁夏段径流量、黄河水位高低、引黄灌溉区黄河引水量、农田灌溉、排水量、地下水位高低等均可能对银川市湿地景观变化造成影响[47]。根据相关文献资料显示，1990—2019年，黄河干流宁夏段径流量、黄河水位高低并未发生显著变化[28];同时,宁夏引黄灌溉多集中于春季和冬季开闸放水，农业灌溉退、排水实际是处于灌排循环阶段的黄河水，引黄灌区地下水位也主要受到引黄灌溉水量的影响，引黄灌溉对湿地的补给不仅取决于季节的变动，还取决于湿地的位置及其与排水沟的连通性。为更清楚的认识银川市湿地景观的动态变化过程及其驱动因素，需加强湿地景观的季节性变化研究。

# 4结论

本文基于面向对象分类方法，从1990一2019年间7期Landsat遥感影像中提取银川市湿地景观信息，分析湿地景观变化及驱动因素，结论如下：

（1）银川市湿地类型以河流湿地为主，其他依次为水产养殖地、湖泊湿地、沟渠、水库/坑塘、沼泽湿地。30a来，银川市湿地总面积由1990年的$2 6 4 . 8 6 ~ \mathrm { k m } ^ { 2 }$ 减少到2019年的 $2 4 1 . 3 2 ~ \mathrm { k m } ^ { 2 }$ ,减少了$2 3 . 5 4 \mathrm { k m } ^ { 2 }$ 。与1990年相比，2019年的自然湿地面积减少了 $3 3 . 5 7 ~ \mathrm { k m } ^ { 2 }$ ，而人工湿地面积增加了10.03$ { \mathrm { k m } } ^ { 2 }$ 。

（2）景观指数分析表明，1990—2019年，银川市湿地景观破碎化程度下降、聚集程度降低、形状趋于复杂、多样性与异质性增加。

(3）银川市湿地景观演变过程受自然因素与社会经济因素的共同影响，其中，社会经济因素中的非农业人口数、水产品产量、第二产业产值与建成区面积的影响最为显著；自然因素中的降水量、气温、日照时数对湿地景观影响相对较弱。

# 参考文献(References):

[1]雷金睿,陈宗铸,陈毅青,等.1990—2018年海南岛湿地景观格 局演变及其驱动力分析[J].生态环境学报,2020,29(1):59-70. [Lei Jinrui, Chen Zongzhu, Chen Yiqing,et al. Landscape pattern changes and driving factors analysis of wetland in Hainan Island during 1990-2018[J]. Ecology and Environmental Sciences,2020, 29(1): 59-70.]   
[2]Guo M,Li J, Sheng C,et al.A review of wetland remote sensing[J]. Sensors,2017,17(4): 777.   
[3]Li Z, Jiang W,Wang W,et al. Ecological risk assessment of the wetlands in Beijing-Tianjin-Hebeiurbanagglomeration[J].Ecological Indicators,2020,117: 106677.   
[4]Mao D, Wang Z,Wu J,et al. China's wetlands lossto urban expansion[J].Land Degradation & Development,2018,29(8):2644- 2657.   
[5]宫宁,牛振国,齐伟,等.中国湿地变化的驱动力分析[J].遥感学 报,2016,20(2):172-183.[Gong Ning,Niu Zhenguo,Qi Wei,et al.Driving forces of wetland change in China[J]. Journal of Remote Sensing,2016,20(2): 172-183.]   
[6]Asselen SV, Verburg PH, Vermaat JE,etal. Drivers of wetland conversion: A global meta-analysis[J]. PLoS One,2018,8(11): e81292.   
[7]傅伯杰.黄土区农业景观空间格局分析[J].生态学报,1995,15 (2):113-12O.[Fu Bojie. The spatial pattern analysis of agricultural landscape in the loess area[J].Acta Ecologica Sinica,1995,15 (2): 113-120.]   
[8]张敏,宫兆宁,赵文吉,等.近30年来白洋淀湿地景观格局变化 及其驱动机制[J].生态学报,2016,36(15):4780-4791.[Zhang Min, Gong Zhaoning, Zhao Wenji, et al. Landscape pattern change and the driving forces in Baiyangdian wetland from 1984 to 2014 [J]. Acta Ecologica Sinica,2016,36(15): 4780-4791.]   
[9]洪佳,卢晓宁,王玲玲.1973—2013年黄河三角洲湿地景观演 变驱动力[J].生态学报,2016,36(4): 924-935.[Hong Jia,Lu Xiaoning,Wang Lingling. Quantitative analysis of the factors driving evolution in the Yellow River Delta wetland in the past 40 years [J]. Acta Ecologica Sinica,2016,36(4): 924-935.]   
[10] 徐晓龙,王新军,朱新萍,等.1996—2015年巴音布鲁克天鹅湖 高寒湿地景观格局演变分析[J].自然资源学报,2018,33(11): 1897-1911.[Xu Xiaolong,Wang Xinjun, Zhu Xinping,et al. Landscape pattern changes in alpine wetland of Bayanbulak Swan Lake during 1996-2015[J]. Journal of Natural Resources,2018,33(11):

1897-1911.]

ing the middle of dry season on landscape pattern of the two larg est freshwater lakes of China[J]. Ecological Indicators,2020,113: 106283.   
[12]Rundquist DC,Narumalani S,Narayanan R M.A review of wet lands remote sensing and defining new considerations[J].Remote Sensing,2001,20(3): 207-226.   
[13]Gallant A.The challenges of remote monitoring of wetlands[J].Remote Sensing,2015,7(8): 10938-10950.   
[14]刘吉平,高佳,董春月.1954—2015年三江平原沼泽湿地变化 的区域分异及影响因素[J].生态学报,2019,39(13):4821- 4831.[Liu Jiping,Gao Jia,Dong Chunyue.Regional differentiation and factors influencing changes in swamps in the Sanjiang Plain from 1954 to 2015[J].Acta Ecologica Sinica,2019,39(13): 4821-4831.]   
[15] 彭凯锋,蒋卫国,邓越.武汉城市圈湿地受损程度识别及驱动因 素分析[J].自然资源学报,2019,34(8):1694-1707.[Peng Kaifeng, Jiang Weiguo, Deng Yue. Identification of wetland damage degree and analysis of its driving forces in Wuhan Urban Agglomeration[J]. Journal of Natural Resources,2019,34(8): 1694-1707.]   
[16]JiangW,LvJ,Wang C,etal.Marsh wetland degradation risk assessment and change analysis: A case study in the Zoige Plateau, China[J]. Ecological Indicators,2017,82: 316-326.   
[17] 刘畅,王继富.5个时期黑龙江省天然湿地动态及其影响因素 研究[J].湿地科学,2017,15(1):80-84.[Liu Chang,Wang Jifu. Dynamic of natural wetlands in Heilongjiang Province in five periods and influence factors[J]. Wetland Science,2017,15(1): 80-84.]   
[18] 毛德华,王宗明,罗玲,等.1990—2013年中国东北地区湿地生 态系统格局演变遥感监测分析[J].自然资源学报,2016,31(8): 1253-1263.[Mao Dehua, Wang Zongming,Luo Ling,et al. Monitoring the evolution of wetland ecosystem pattern in Northeast China from 1990 to 2O13 based on remote sensing[J]. Journal of Natural Resources,2016,31(8): 1253-1263.]   
[19] 梁旻轩,谢正磊,毛德华,等.1980年以来5个时期洞庭湖区国 际重要湿地景观动态研究[J].湿地科学,2020,18(1):40-46. [Liang Minxuan,Xie Zhenglei, Mao Dehua,et al.Landscape dynamics of wetlands of international importance in Dongting Lake area for 5 periods since 1980[J].Wetland Science,2020,18(1): 40-46.]   
[20] 陈昆仑,齐漫,王旭,等.1995—2015年武汉城市湖泊景观生态 安全格局演化[J].生态学报,2019,39(5):1725-1734.[Chen Kunlun, Qi Man, Wang Xu,et al. Studyof urban lake landscape ecological security pattern evolution in Wuhan,1995-2015[J].Acta Ecologica Sinica,2019,39(5):1725-1734.]   
[21] 焉恒琦,朱卫红,毛德华,等.长江三角洲国际重要湿地人为胁 迫遥感解析[J].中国环境科学,2020,40(8):3605-3615.[Yan Hengqi, Zhu Weihong,Mao Dehua,et al. Landsat-based observation of human pressure to wetlands in Ramsar sites over the YangtzeRiver Delta[J]. China Environmental Science,2020,40(8): 3605-3615.]   
[22] 张东方,杜嘉,陈智文,等.20世纪60年代以来6个时期盐城滨 海湿地变化及其驱动因素研究[J].湿地科学,2018,16(3):313- 321.[Zhang Dongfang,Du Jia,Chen Zhiwen,et al.Changes of coastal wetlands in Yancheng for 6 periods since l96Os and their driving factors[J].Wetland Science,2018,16(3): 313-321.]   
[23]白军红,欧阳华,崔保山,等.近40年来若尔盖高原高寒湿地景 观格局变化[J].生态学报,2008,28(5):2245-2252.[Bai Junhong, Ouyang Hua, Cui Baoshan, et al. Changes in landscape pattern of alpine wetlands on the Zoige Plateau in the past four decades[J]. Acta Ecologica Sinica,2008,28(5): 2245-2252.]   
[24] 李妍妍,王景升,税燕萍,等.拉萨河源头麦地卡湿地景观格局 及功能动态分析[J].生态学报,2018,38(24):8700-8707.[Li Yanyan,Wang Jingshen, Shui Yanping,et al.Analysis of landscape pattern and ecological service function of the Mcdika wetland reserve[J]. ActaEcologicaSiica,2018,38(24): 8700-8707.]   
[25] 周华荣.干旱区湿地多功能景观研究的意义与前景分析[J].干 旱区地理,2005,28(1):16-20.[Zhou Huarong.Prospect on multifunctiona landscapes of marshesinaridareas[J].AridLand Geography,2005,28(1): 16-20.]   
[26] 緱倩倩,屈建军,王国华,等.中国干旱半干旱地区湿地研究进 展[J].干旱区研究,2015,32(2):213-220.[Gou Qianqian,QuJianjun, Wang Guohua,et al.Progress of wetland researches in arid and semi-arid regions in China[J].Arid Zone Research,2015,32 (2): 213-220.]   
[27] 周亚军,刘廷玺,段利民,等.锡林河流域上游河谷湿地景观格 局演变及其驱动力[J].干旱区研究,2020,37(3):580-590. [Zhou Yajun,Liu Tingxi, Duan Limin,et al. Driving force analysis and landscape pattern evolution in the upstream valley of Xilin River Basin[J].Arid Zone Research,2020,37(3): 580-590.]   
[28] 张娜,韩小龙,汤英,等.宁夏石嘴山市引黄灌区地下水时空变 化特性及影响因素[J].干旱区研究,2020,37(5):1124-1131. [Zhang Na, Han Xiaolong,Tang Ying,et al. Temporal and spatial characteristics of groundwater and its influencing factors in the Yellow River diversion irrigation area of Ningxia Shizuishan[J].Arid Zone Research,2020,37(5): 1124-1131.]   
[29] 高祖桥,白永平,周亮,等.宁夏沿黄城市带湿地景观格局演变 特征及驱动力[J].应用生态学报,2020,31(10):3499-3508. [Gao Zuqiao,Bai Yongping, Zhou Liang,et al. Characteristics and driving forces of wetland landscape pattern evolution of the city belt along the Yellow River in Ningxia,China[J].Arid Zone Research,2020,31(10): 3499-3508.]   
[30]Liu J, Liu M, Zhuang D,et al. Study on spatial patern of land-use change in China during 1995-2000[J]. Science China Earth Sciences, 2003,46(4): 373-384.   
[31] 刘纪远,匡文慧,张增祥,等.20世纪80年代末以来中国土地利 用变化的基本特征与空间格局[J].地理学报,2014,69(1):3- 14.[Liu Jiyuan, Kuang Wenhui, Zhang Zenxiang,et al. Spatiotemporal characteristics,paterns and causes of land use changes in China since the late 198Os[J].Acta Geographica Sinica,2014, 69 (1): 3-14.]   
[32] 国家林业局《湿地公约》履约办公室.湿地公约履约指南[M].北 京：中国林业出版社,2001:1-8.[Ramsar Convention Compliance Office, State Forestry Administration.Wetland Convention Guideline[M]. Beijing: China Forestry Publishing House,2Ool: 1-8.]   
[33] 国家林业局湿地保护管理中心.全国湿地资源调查与检测技术 规程(试行)[M].北京:中国林业出版社,2008:4-20.[Wetland Conservation and Management Center,State Forestry Administration. Technical Rules for National Wetland Resources Survey and Monitor(Trial Implementation)[M].Beijing: China Forestry Publishing House, 2008: 4-20.]   
[34]Benz U C,Hofmann P,Willhauck G,et al.Multi-resolution,objectoriented fuzzy analysis of remote sensing data for GIS-ready information[J]. ISPRS Journal of Photogrammetryand Remote Sensing, 2004,58(3): 239-258.   
[35] 陈建龙,王语檬,侯淑涛,等.面向对象和DEM的ZY-102C影像 湿地提取研究[J].地球信息科学学报,2015,17(9):1103-1109. [Chen Jianlong,Wang Yumeng,Hou Shutao,et al.Wetland information extraction of ZY-102C image based on the Object and DEM [J]. Journal of Geo-information Science,2015,17(9): 1103-119.]   
[36] 傅伯杰,徐延达,吕一河.景观格局与水土流失的尺度特征与耦 合方法[J].地球科学进展,2010,25(7): 673-681.[Fu Bojie,Xu Yanda,Lyu Yihe. Scale characteristics and coupled research of landscape pattern and soil and water loss[J]. Advances in Earth Science,2010,25(7): 673-681.]   
[37]邬建国.景观生态学:格局、过程、尺度与等级[M].北京:高等教 育出版社,2007: 106-120.[Wu Jianguo.Landscape Ecology: Pattern,Process,Scale and Hierarchy[M]. Beijing: Higher Education Press,2007: 106-120.]   
[38]Wang X,LiY,ChuB,etal.Spatiotemporaldyamicsdriing forces of ecosystem changes: A case study of the National Barrier Zone, China[J]. Sustainability,2020,12(16): 6680.   
[39] Xiao F, Gao G,Shen Q,et al.Spatio-temporal characteristics and driving forces of landscape structure changes in the middle reach of the Heihe River Basin from 1990 to 2015[J]. Landscape Ecology,2019,34(4): 755-770.   
[40] 李肇晨,罗微,陈永富,等.海南霸王岭陆均松空间分布格局及 其与微生境异质性的关系[J]).生态学报,2015,35(8): 2545- 2554.[Li Zhaochen,Luo Wei, Chen Yongfu, et al. The relationships between microhabitat heterogeneity and the spatial distribution of Dacrydium pectinatum in Bawangling,Hainan Island[J]. Acta Ecologica Sinica,2015,35(8): 2545-254.]   
[41] 牛振国,张海英,王显威,等.1978—2008年中国湿地类型变化 [J].科学通报,2012,57(16):1400-1411.[Niu Zhenguo,Zhang Haiying,Wang Xianwei, et al. Mapping wetland changes in China between 1978 and 2008[J]. Chinese Science Buletin, 2012,57 (16): 1400-1411.]   
[42] 黄宁,杨绵海,林志兰,等.厦门市海岸带景观格局变化及其对

生态安全的影响[J].生态学杂志,2012,31(12):3193-3202. [Huang Ning,Yang Mianhai, Lin Zhilan, et al. Landscape pattern changes of Xiamen coastal zone and their impacts on local ecological security[J]. Chinese Journal of Ecology,2012,31(12):3193- 3202.]

[43]许吉仁,董雾红.南四湖湿地景观格局变化的生态系统服务价 值响应[J].生态与农村环境学报,2013,29(4):471-477.[Xu Jiren,Dong Jihong.Response of ecosystem in service value to changes in landscape pattern of the Nansi Lake wetland[J]. Journal of Ecology and Rural Environment,2013,29(4): 471-477.]

[44] 张双双,董斌,杨斐,等.升金湖湿地景观格局变化对越冬鹤类 地理分布的影响[J].长江流域资源与环境,2019,28(10):2461- 2470.[Zhang Shuangshuang,Dong Bin, Yang Fei,et al. Influence of landscape pattern change of Shengjin Lake wetland on the geographical distribution of overwintering cranes[J]. Resources and Environment in the Yangtze Basin,2019,28(1O): 2461-2470.]

[45]王朔,张荣群,乔月霞.银川平原湿地时空变化信息的可视化分 析[J].测绘科学,2017,42(11):56-61,73.[Wang Shuo,Zhang Rongqun,Qiao Yuexia.Visual analysis of wetland spatio-temporal variation in Yinchuan Plain[J]. Science of Surveying and Mapping, 2017,42(11): 56-61, 73.]

[46]张美美,张荣群,郝晋珉,等.基于ANN-CA的银川平原湿地景 观演化驱动力情景模拟分析[J].地球信息科学学报,2014,16 (3):418-425.[Zhang Meimei, Zhang Rongqun,Hao Jinmin,et al. The scenario simulation analysis of driving forces of wetland landscape evolution using ANN-CA in Yinchuan Plain[J]. Journal of Geo- information Science[J]. Journal of Geo-information Science 2014,16(3): 418-425.]

[47]国家林业局.中国湿地资源·宁夏卷[M].北京:中国林业出版 社,2015:61.[State Forestry Administration.China Wetlands Resources(Ningxia Volume) [M].Beijing:China Forestry Publishing House,2015: 61.]

# Wetland landscape evolution and its driving factors in Yinchuan

WANG Xiaofeng1²， YAN Yu³， LI Yuehao³， ZHANG Xing³， FU Xinxin³ (1.School of Land Engineering,Chang'an University,Xi'an 71Oo54,Shaanxi, China; 2.Shaanxi Key Laboratory of Land Reclamation Engineering,Xi'an 71Oo54, Shaanxi, China; 3.School of Earth Science and Resources,Chang'an University,Xi'an 71Oo54,Shaanxi, China)

Abstract: Wetland is the transitional zone of aquatic and terrstrial ecosystems,and it is an ecosystem with the highest biodiversity and productivity on Earth.Recently,under the influence of climate change and human activities,the wetland ecosystem has rapidly degraded.Spatio-temporal dynamic monitoring of wetland plays a vital role in the sustainable development of wetland landscape.The object-oriented classification method was used to extract the wetland landscape information in Yinchuan based on the Landsat TM/OLI remote sensing images from 1990 to 2O19.The landscape index and redundancy analysis methods were used to analyze the dynamic changes and their driving factors in wetlands.The results showed that Yinchuan's wetland area decreased from $2 6 4 . 8 6 ~ \mathrm { k m } ^ { 2 }$ in 1990 to $2 4 1 . 3 2 ~ \mathrm { k m } ^ { 2 }$ in 2019,a decrease of $2 3 . 5 4 ~ \mathrm { k m } ^ { 2 }$ .The area of natural wetlands in 2019 decreased by $3 3 . 5 7 ~ \mathrm { k m } ^ { 2 }$ ，while artificial wetlands increased by $1 0 . 0 3 \ \mathrm { k m } ^ { 2 }$ . In the past 3O years,PD and AI of the landscape paterns have decreased,while the LSI and SHDI increased.This indicated that the wetland landscape paterns has undergone significant changes，fragmentation and aggregation degree gradually decreased,patch shape tended to be more complicated,and landscape diversity and heterogeneity increased.Twelve driving factors were selected for redundancy analysis,and socio-economic factors played a dominant role in the wetland landscape change,including nonagricultural population and aquatic products yield,the output value of various industries,and developed areas of cities.Altogether,natural factors such as precipitation,temperature,and hours of sunshine change could also impact the wetland landscape change,which is relatively weak.The research results provide important references to protect and rationally use wetlands resources in Yinchuan.

Keywords: wetland; landscape pattern； evolution； driving factors; Yinchuan