# 基于街道尺度的西安市基础教育资源空间分布特征研究

王雪²，白永平，汪凡’，张旻，车磊(1西北师范大学地理与环境科学学院,甘肃兰州730070；2 西安博爱国际学校,陕西西安710021)

摘要：基于POI教育设施点数据，以街道为研究尺度，利用ArcGIS 的标准差椭圆、核密度估计以及GeoDa的探索性空间数据分析(ESDA)，对西安市主城区基础教育资源的空间分布特征进行分析。结果表明：在空间布局上，西安市基础教育资源表现出“外疏内密、东疏西密、北疏南密”的特征,在方向上，其空间布局呈现出“东北一西南”的特点;幼儿园及小学主要集中分布在中心城区，少部分集中在外围，中学主要集中在中心城区;H-H类型区主要集中在城南和城北,L-L类型区主要集中在中心城区的特殊区域。总体来看，基于街道尺度的西安市基础教育资源空间分布特征研究能够清晰地反映西安市基础教育资源的空间格局，可为政府相关部门合理规划教育设施的布局提供理论依据。

关键词：西安市；基础教育；空间分布；POI

近年来，随着社会的快速发展和生活质量的逐步提升,人们对基础教育的重视程度不断提高[1]基础教育资源(幼儿园、小学和中学)配置的不均衡性是当前我国发展教育事业面临的关键问题之一，具体反映在空间上则为基础教育资源的布局不均衡[1]。该问题涉及到民生、城乡发展、社会公平公正以及新型城镇化建设等多个方面。此外，由于经济的快速发展，城市空间和人口规模也产生了相应的变化，原有基础教育资源的布局已不能满足人们的需求[2]。国内外学者对基础教育资源进行了相关研究。在国外，早期研究主要涉及学校教育硬件设施的最低建设标准以及教育政策与教育资源空间布局的关系,LANGE等[3]通过构建教育机会空间指数对巴西两大城市适龄儿童的教育需求与当地学校的供应进行了研究;ANDERSSON 等[4]以瑞典学生2000一2006年上学距离变化为基础研究不同群体以及区位上的就学差异;随着社会的进步，学者们通过运用模型并结合不同地区政策、教育财政改革以及学区重新划分等，对基础教育资源进行了相关研究，研究表明高质量的学校资源能够有效促进房价上涨[5-8];近年来,学者们主要采用地理信息系统技术，同时结合可达性等指标对地区教育空间配置进行研究，研究内容主要包括学校学区划分、学生就学交通成本分析以及可达性变化所引起的经济效应等[9-13]。在国内,学者们对基础教育资源的研究主要表现在三个方面，第一，基础教育资源的配置与布局,黄新苹[14]以河南省为例研究了“全面二孩”政策下城乡基础教育资源优化配置与均衡发展，刘新意等[15]研究了GIS 在基础教育资源空间布局中的应用,张静华等[16]在Huff 模型支持下分析了基础教育资源分布，赵琳等[17]对山东省基础教育资源配置时空演变特征与影响因素进行了研究，姜宇榕等[18]研究了咸宁市基础教育资源空间配置及优化;第二,农村基础教育资源的相关研究,谢中起等[19]基于河北省基础教育对新型城镇化进程中农村基础教育资源优化配置进行了研究,宁召文[20]以山东省为例，在公平视角下对农村基础教育资源配置问题进行了研究；第三，基础教育资源对社会发展的影响,张珂等[2]以北京市海淀区为例研究了城市基础教育资源对住宅价格的影响，张力帆等[22]对基础教育资源的空间布局对新型城镇化的影响进行了研究,孟兆敏等[23]研究了基础教育资源配置对上海市人口空间演变的影响。

从已有研究来看，有关基础教育资源的空间分布研究成果颇丰，但是统计年鉴和调查问卷这两种方法是传统研究的主要手段。此外，能够精确到街道尺度的研究较少，以市级或县级研究尺度为主。随着技术的发展，以POI（PointofInterest）为代表的大数据在研究中越来越普遍，利用POI数据研究基础教育资源的空间分布及其影响因素已成为新趋势。因此,本文基于POI数据,研究西安市主城区53个街道的基础教育资源，分析该地区基础教育资源的空间分布特征，以期为西安市的基础教育资源合理配置提供参考。

# 研究区域与研究方法

# 1.1 研究区域

研究区域主要包括新城区、灞桥区、碑林区、雅塔区、莲湖区和未央区，为西安市绕城高速内的主城区,共划分出53个街道，面积 $8 4 3 . 5 6 ~ \mathrm { k m } ^ { 2 }$ ，人口$4 5 3 . 8 9 \times 1 0 ^ { 4 }$ 人[24]。中心城区位于明城墙内,主要包括南院门、柏树林、西一路、中山门、青年路、北院门和解放门等7个街道，外围区位于明城墙以外。

# 1.2 数据来源

研究使用的数据共有两类：(1)POI数据，通过GeoSharp软件提取出研究区内幼儿园、小学和中学的 POI位置数据分别为1395个、327个和192个（2017年5月），如图1所示，共1914个学校网点。表1为研究区的各区面积、人口数和学校数量概况(2)基础地图数据，来源于国家基础地理信息中心的西安市县级和乡级行政区图，进而矢量化出53个街道的行政区图。

# 1.3 研究方法

1.3.1标准差椭圆标准差椭圆是一种用于反映离散数据集空间分布特征的方法，主要通过空间分布特征椭圆来描述研究对象的空间分布特征，特征椭圆的基本参数有平均中心、方位角、长轴和短轴等[25-30] 。

1.3.2核密度估计法核密度估计法可从集聚和分散两个方面获取点数据的分布特征，从而直观地描述地理现象分布特征[31-33]。计算公式如下：

$$
f _ { n } ( x ) = \frac { 1 } { n h ^ { 2 } \pi } \sum _ { i = 1 } ^ { n } K \bigg [ \bigg ( 1 -
$$

式中： $K$ 表示空间权重函数； $h$ 为阈值； $n$ 为阈值范围

![](images/5298aec7de59a158874ca21046a3d73026cf3653757c62c65624918857e4e75a.jpg)  
图1西安市基础教育资源分布图  
Fig.1Distribution of basic education resources in Xi'an City

# 表1研究区各区面积、人口和基础教育资源设施点数量概况

Tab.1Distribution of population and retail stores in the study area   

<html><body><table><tr><td>行政区 中学</td><td>总面积 /km²</td><td>常住人口 /104人</td><td>街道办事 处或镇／个</td><td colspan="3">学校数量/个 幼儿园 小学 中学</td></tr><tr><td>未央区</td><td>262</td><td>81.14</td><td>10</td><td>420</td><td>96</td><td>32</td></tr><tr><td>灞桥区</td><td>332</td><td>60.00</td><td>9</td><td>200</td><td>76</td><td>24</td></tr><tr><td>碑林区</td><td>23</td><td>62.89</td><td>8</td><td>107</td><td>40</td><td>30</td></tr><tr><td>新城区</td><td>31</td><td>60.78</td><td>9</td><td>102</td><td>35</td><td>30</td></tr><tr><td>雁塔区</td><td>152</td><td>117.85</td><td>8</td><td>414</td><td>87</td><td>51</td></tr><tr><td>莲湖区</td><td>43</td><td>71. 23</td><td>9</td><td>152</td><td>46</td><td>24</td></tr></table></body></html>

内的点数; $\left( x - x _ { i } \right) ^ { 2 } + \left( y - y _ { i } \right) ^ { 2 }$ 表示点 $( x _ { i } , y _ { i } )$ 和点$\scriptstyle ( x , y )$ 之间的距离； $d$ 为数据的维度。

1.3.3探索性空间数据分析法探索性空间数据分析法可以从区域间数据的空间异质性和关联性两个方面进行分析[34-35]。其中,全局自相关统计量可分析区域单元教育设施点数量的整体分布情况，从而反应出该区域内数据的平均集聚状况。为了反映出区域基础教育资源设施点数量与领近区域的相关程度，可采用局部自相关分析。计算公式为：

$$
I = Z _ { i } \sum _ { j = 1 } ^ { n } W _ { i j } Z _ { j }
$$

式中： $Z _ { i }$ 和 $Z _ { j }$ 分别代表区域 $\mathbf { \chi } _ { i }$ 和 $j$ 观测值的标准化形式； $\boldsymbol { W } _ { i j }$ 为空间权重矩阵; $n$ 为样本数;检验方法与全局莫兰指数相同。

# 2基础教育资源的空间分布

# 2.1基础教育资源的空间分布特征及方向

为了研究其空间分布特征及方向，利用标准差椭圆进行研究，得到西安市零售业空间分布特征椭圆的相关参数如表2所示。

由图2可知，幼儿园分布椭圆中心位于中心城区内，明显偏西南，反映出西安市主城区幼儿园在空间上表现出西多东少、南多北少的特点，但每个街道都有一定数量的幼儿园，一定程度上能够满足学前教育的需求；与幼儿园数量相比，小学的数量较少，主要分布在中心城区，越往外围数量越少；中学数量总体较少，且主要聚集于中心城区，而外围城区呈现出零星分布状态。

表2SDE参数 Tab.2Parameters of SDE in Xi'an City   

<html><body><table><tr><td>项目</td><td>长轴标准距离</td><td>短轴标准距离</td><td>方位角</td></tr><tr><td>幼儿园数量 SDE</td><td>0.069 9</td><td>0.102 1</td><td>72.283 2</td></tr><tr><td>小学数量SDE</td><td>0.072 3</td><td>0.107 5</td><td>80.336 4</td></tr><tr><td>中学数量 SDE</td><td>0.062 2</td><td>0.095 8</td><td>75.314 1</td></tr></table></body></html>

![](images/f11e7cb0289bfca95ea7aeff2bcf558aa1c78778a8a352910fd7aafcc87612d1.jpg)  
图2西安市基础教育资源空间分布椭圆Fig.2Specific ellipse of basic education resourcesin Xi'an City

通过上述分析及图2和表2可知，幼儿园在空间上的分布相对较公平，而中学存在严重的空间上的不均衡性,小学介于幼儿园与中学之间。总体而言，在空间分布上，西安市基础教育资源呈现出“内密外疏、西密东疏、南密北疏"的特征，根据长轴、短轴标准距离以及方位角，基础教育资源在空间分布方向上呈现出“东北一西南”的分布特点。

# 2.2基础教育资源的空间分布差异

根据核密度分析法识别的幼儿园设施点高值区域主要集中在中心城区以及城市的西南区域，在中心城区，规模明显较大，而外围区域规模较小，离散分布，该区域经济发展较快，人口密度大，对幼儿园教育资源的需求量较大；小学设施点的高值区域与幼儿园设施点一致，由于地理位置等原因，中心城区仍然处于城市发展的重要位置，但是外围城区尤其以城市西南部的高新区为典型；中学设施点的高值区域主要聚集在中心城区，在外围城区零星分布，从数量上中学较幼儿园与小学相比明显下降，中学教育资源集中分布在中心城区能够使优质教育资源更加充分地进行交流。

通过上述分析及图3，西安市基础教育资源在空间上形成了块状集聚、多中心发展的格局，主要集中在中心城区。

# 2.3基础教育资源的集聚状况

2.3.1全局空间自相关分析为了分析西安市基础教育资源的集聚状况，本文采用探索性空间数据分析法（ESDA)进行全局空间自相关研究。通过999 次随机检验，得到 $P = 0 . 0 0 1$ ，通过了 $9 9 \%$ 的显著性检验。得到研究对象的全局自相关Moran's $I$ 指数值分别为 $0 . 2 8 5 7 . 0 . 2 3 1 9 . 0 . 2 5 5 8$ ，如表3所示，结果说明数据空间正相关较强，因此基础教育资源空间集聚特征明显。

2.3.2局部空间自相关分析为了进一步研究基础教育资源设施点的集聚程度，用Moran散点图和局部Moran's $I$ 指数,在 $Z$ 值检验的基础上（ $\boldsymbol { P } <$ 0.05），绘制出幼儿园、小学和中学基础设施点LISA集聚图(图4)。图中白色的区域表示未通过显著性水平检验，即该区域自相关性不显著。

幼儿园设施点的H-H类型主要聚集在电子城、丈八沟及曲江街道,该区域位于西安市曲江新区;L-L类型区主要集中在中心城区的特殊区域，该区域街道面积较小，所能容纳的学校数量有限。小学的H-H类型区主要集中在徐家湾、汉城街、谭家街及张家堡街道;L-L类型区与幼儿园一致。中学的H-H类型区主要聚集在丈八沟、电子城、大雁塔、小寨

![](images/a63e0a546ca523c6c00d1fbfc94b49e99ae2333d705c5878df5ea2b030e6c49e.jpg)  
图3西安市基础教育资源空间分布核密度图Fig.3Kernel density of basic education resourcesin Xi'an City

# 表3西安市基础教育资源Moran'sI值

Tab.3Moran'sIfor basic education resources in Xi'an City   

<html><body><table><tr><td>类型</td><td>Moran'I值</td><td>Z值</td><td>P值</td></tr><tr><td>幼儿园</td><td>0.285 7</td><td>3.640 6</td><td>0.001</td></tr><tr><td>小学</td><td>0.231 9</td><td>2.990 8</td><td>0.001</td></tr><tr><td>中学</td><td>0.2558</td><td>3.4521</td><td>0.001</td></tr></table></body></html>

![](images/09bdb09d721460b0116dbb32f52732dd974314ef242dc0d2b066ef44076a17b9.jpg)  
图4西安市基础教育资源LISA图Fig.4LISA cluster of basic education resourcesin Xi'an City

和长延堡街道；L-L类型区主要集中在张家堡和未央宫街道。综合来看，西安市基础教育资源的H-H类型区主要集中在城南和城北，主要为城南的丈八沟、电子城、曲江街、小寨和大雁塔等街道,城北的汉城、徐家湾、张家堡和谭家街等街道，该类型区域与邻近区域的基础教育资源呈现较高的关联性，其自身的教育发展带动了周边区域的发展，说明了这些区域教育资源配置较高，同时得到了政策的影响;

H-L类型区主要为北院门、长乐坊、三桥、六村堡和草滩街等街道，这些区域自身教育资源配置水平较高，与邻近的区域有一定的差距，形成了空间差异性；L-H类型区主要为韩森寨以及红旗街等街道，该类型区域基础教育资源配置水平不高，与周边区域形成了一定的差距，产生了空间关联差异性；L-L类型区主要集中在中心城区的特殊区域，该类型区域自身与周围城市的教育空间关联呈现低值集聚性，由于自身与邻近区域的基础教育资源配置发展水平都不高，整体形成不发达区域，这类区域由于区域面积较小，教育资源配置被限制，导致基础教育资源配置较低。

# 3讨论

在快速城镇化和全面放开二孩政策背景下，基础教育将面临巨大压力，基础教育资源的合理配置必将成为一个焦点问题，该问题已被诸多学者所关注[36-38]。虽然学术界对基础教育资源做了大量相关研究，但多采用统计数据，同时，研究尺度较大，大多选择省、市或县级行政单元，很少以街道为研究单元进行研究[39-41]。基于以上研究背景,本文利用POI数据研究了西安市街道尺度的基础教育资源空间分布特征，研究结果与西安市的实际情况基本吻合。西安市基础教育资源在街道尺度上存在着不均衡性，主要集中在中心城区和城市的西南区域,随着西安市吸引人才进一步放开户籍准入条件，人口迅速增长，对基础教育资源的需求增加，这种布局无法满足人口增长对基础教育资源的需求。

POI数据为截面数据,无法进行时间序列上的研究，未能对研究对象的发展趋势进行较为准确的判断,有待进一步深入研究[42-44]。此外,由于数据的可获得性，没有对基础教育资源的影响因素进行分析，希望以后进一步深入研究。

# 4结论

（1）根据标准差椭圆可以看出，西安市基础教育资源设施点主要集中在主城区的中部和南部，在空间上，其分布表现出“内密外疏、西密东疏、南密北疏”的特征,在方向上，呈现出“东北一西南”的特点。

（2）根据核密度分析法识别的基础教育资源设施点高值区域主要集中在中心城区以及城市的西南区域，在空间上呈现出块状聚集、多中心发展的格局。

(3）从空间集聚特征来看，西安市基础教育资源的H-H集聚区主要集中在曲江新区及高新区；城市边缘的区域以及位于中心城区的特殊区域为L-L集聚区。

参考文献（References）   
[1］刘宏燕,陈雯.中国基础教育资源布局研究述评[J].地理科学 进展,2017,36(5）:557-568.[LIU Hongyan,CHEN Wen.A review of research on the distribution of basic education resources in China[J].Progress in Geography,2017,36(5）:557-568.]   
[2］夏坤.小城市中小学空间布局研究——以麻城市市区中小学 为例[D].西安：西安建筑科技大学,2014.［XIA Kun.Research on the spatial layout of primary and middle schools in small cities : The case of primary and middle schools in Macheng City[D].Xi' an:Xi'an University of Architecture and Technology,2014.]   
[3]LANGE W,ALVES F. Spatial index of educational opportunities : Rio de Janeiro and Belo Horizonte[J].Procedia-Social and Behavioral Sciences,2011,21(3） :287 -293.   
[4]ANDERSSON E,MALMBERG B,OSTH J. Travel-to-school distances in Sweden 2000—2006:Changing school geography with equality implications[J]. Journal of Transport Geography,2012,23 (2) :35 -43.   
[5]FACK G,GRENETJ. When do better schools raise housing prices ? Evidence from Paris public and private schools[J]. Journal of Public Economics,2010,94(1）:59 -77.   
[6]RIES J,SOMERVILLE T.School quality and residential property values:Evidence from Vancouver rezoning[J].The Review of Economics and Statistics,2010,92(4):928 -944.   
[7]AGARWAL S,RENGARAJAN S,SING TF,et al. School allocation rules and housing prices:A quasi-experiment with school relocation events in Singapore[J].Regional Science and Urban Economics,2016,58(5） :42-56.   
[8]IMBERMAN S A,LOVENHEIM M F.Does the market value value-added? Evidence from housing prices after a public release of school and teacher value-added[J]. Journal of Urban Economics, 2016,91(2) :104 -121.   
[9]SINGLETON A D,LONGLEY P A,ALLEN R,et al. Estimating secondary school catchment areas and the spatial equity of access [J].Computers，Environment and Urban Systems,2011,35（3）： 241 -249.   
[10]CHIN H C,OONG K W.Influence of school accessibility on housing values[J].Journal of Urban Planning and Development,2006, 132(3):120 -129.   
[11]KIM K,DEAN D J,KIMH,et al.Spatial optimization for regionalization problems with spatial interaction:A heuristic approach[J]. International Journal of Geographical Information Science,2O16,30 (3) :451-473.   
[12]GHOSHS.Strategic interactionamong public scholdistricts: Evidence on spatial interdependence in school inputs[J].Economics of Education Review,2010,29(3）:440-450.   
[13]KO J,NAZARIAN E,NAM Y,et al. Integrated redistricting,location-allocation and service sharing with intra-district service transfer to reduce demand overload and its disparity[J].Computers, Environment and Urban Systems,2015,54（3):132-143.   
[14］黄新苹.“全面二孩"政策下城乡基础教育资源优化配置与均 衡发展研究—以河南省为例[J].教育探索,2018,36（3）： 18 -23.[HUANG Xinping.“Comprehensive two children”policy in urban and rural areas and balanced development of basic education resources optimization research: In Henan Province as an example[J].Education Exploration,2018,36(3）:18 -23.]   
[15］刘新意,冯俊华.GIS 在基础教育资源空间布局中的应用[J] 信息与电脑（理论版）,2017,42（12）:96-97.[LIU Xinyi, FENG Junhua.Application of GIS in spatial layout of basic education Resources[J].China Computer and Communication,2017,42 (12) :96-97.]   
[16］张静华,任福,刘江涛,等.Huff模型支持下的基础教育资源分 布分析[J].地理信息世界,2015,22(2）:44-50.[ZHANG Jinghua,RENFu,LIU Jiangtao,et al.Analysis of the resource of primary schools by supporting of the Huff model[J]. Geographic information world,2015,22(2）:44-50.]   
[17］赵林,吕晓,于伟,等.山东省基础教育资源配置时空演变特征 与影响因素[J].干旱区资源与环境,2018,32(6):43-49. [ZHAO Lin,LYU Xiao,YU Wei,et al.The spatio-temporal evolution characteristics of basic education resources allocation and the influencing factors in Shandong Province[J]. Journal of Arid Land Resources and Environment,2018,32(6):43 -49.]   
[18］姜宇榕,黄鑫,何国松.咸宁市基础教育资源空间配置及优化 研究［J].科技资讯,2018,16(17）:167-169,171.［JIANG Yurong,HUANG Xin,HE Guosong.The basic education resource space configuration and optimization research in Xianning[J].Science and technology information,2018,16(17）:167-169,171.]   
[19］谢中起,刘学超.新型城镇化进程中农村基础教育资源优化配 置——基于河北省基础教育的实证分析[J].太原城市职业技 术学院学报,2014,43（3）：92－94.[XIE Zhongqi,LIU Xuechao.New urbanization in rural basic education resources optimization configuration: Based on an empirical analysis of the basic education in Hebei Province[J]. Journal of Taiyuan Urban Vocational College,2014,43(3）: 92-94.]   
[20］宁召雯.公平视角下的农村基础教育资源配置问题研究[D]. 沈阳：辽宁大学,2016.［NING Zhaowen.Study on allocation of resources of rural basic education under the fair view:Taking Shandong Province as an example[D]. Shenyang:Liaoning University, 2016.]   
[21］张珂,张立新,朱道林.城市基础教育资源对住宅价格的影 响——以北京市海淀区为例[J].教育与经济,2018,32（1)： 27-34,96.[ZHANG Ke,ZHANG Lixin,ZHU Daolin.Research

on the influence of basic educational resources on housing price:A

case study of Haidian district in Beijing[J].Education and economy,2018,32(1) :27 -34,96.]   
[22］张利凡,郭文博.基础教育资源的空间布局对新型城镇化的影 响[J].住宅与房地产,2016,42（33）：259.[ZHANG Lifan, GUO Wenbo.Basic education resources of the influence of the spatial layout of new urbanization[J].Housing and real estate,2016, 42(33) :259.]   
[23］孟兆敏,潘鑫.基础教育资源配置对上海市人口空间演变的影 响[J].城市问题,2018,32（5）:34-45.[MENG Zhaomin,PAN Xin.Basic education resource configuration space evolution of the population in Shanghai[J]. Urban problems,2018,32（5）34- 45.]   
[24］郭瑞斌,薛东前,暴向平,等.西安市主城区客观生活质量空间 格局研究[J].人文地理,2015,30(5）:43-48.[GUO Ruibin, XUE Dongqian,BAO Xiangping,et al.Spatial pattrn of objective life quality of downtown areas in Xi'an[J].Human Geography, 2015,30(5) :43 -48.]   
[25]O'LOUGHLIN J,WITMER F D W.The localized geographies of violence in the north Caucasus of Russia,1999—2007[J].Annals of the Association ofAmerican Geographers,2011,101（1）:178 201..   
[26]VANHULSEL M,BECKX C,JANSSENS D,et al. Measuring dissimilarity of geographically dispersed space-time paths[J]. Transportation,2011,38(1) :65-79.   
[27] MAMUSE A,PORWAL A,KREUZER O,et al. A new method for spatial centrographic analysis of mineral deposit clustersJ]. Ore Geology Reviews,2009,36(4）:293-305.   
[28]YUE TX,FAN Z M,LIU JY. Changes of major terrestrial ecosys tems in China since 196O[J].Global & Planetary Change,2005, 48(4) :287 -302.   
[29］赵媛,杨足膺,郝丽莎,等.中国石油资源流源—汇系统空间格 局特征[J].地理学报,2012,67（4）:455-466.[ZHAO Yuan, YANG Zuying,HE Lisha,et al.The evolution of spatial displacement pattern of China's crude oil flow source-sink system[J].Acta Geographica Sinica,2012,67(4） :455-466.]   
[30］赵璐,赵作权.基于特征椭圆的中国经济空间分异研究[J].地 理科学,2014,34（8）:979 -986.[ZHAO lu,ZHAO Zuoquan. Projecting the spatial variation of economic based on the specific elipses in China[J].Scientia Geographica Sinica,2014,34（8）: 979 - 986.]   
[31］陈蔚珊,柳林,梁育填.基于POI数据的广州零售商业中心热 点识别与业态集聚特征分析［J].地理研究,2016,35（4）： 703-716.[CHEN Weishan,LIU Lin,LIANG Yutian.Retail center recognition and spatial aggregating feature analysis of retail formats in Guangzhou based on POI data[J]. Geographical Research, 2016,35(4) :703 -716.]   
[32］禹文豪,艾廷华,杨敏,等.利用核密度与空间自相关进行城市 设施兴趣点分布热点探究[J].武汉大学学报（信息科学版)， 2016,41(2）:221-227.[YU Wenhao,AI Tinghua,YANG Min, et al.Detecting“hot spots”of facilitv POIs based on kernel densitv

estimation and spatial autocorrelation technique[J].Journal of

Wuhan University: Geomaticsand Information Science,2016,41 (2):221-227.]   
[33］张景秋,贾磊,孟斌.北京城市办公活动空间集聚区研究［J]. 地理研究,2010,9（4）：675-682.[ZHANG Jinggqiu,JIA Lei, MENG Bin.A study onoffce activities cluster in Beijing City[J]. Geographical Research,2010,29(4）:675-682.]   
[34］薛东前,黄晶,马蓓蓓,等.西安市文化娱乐业的空间格局及热 点区模式研究[J].地理学报,2014,69（4）:541-552.[XUE Dongqian,HUANG Jing,MA Beibei,et al. Spatial distribution charateristica and hot zone patterns of entertainment industry in Xi'an[J].Acta Geographica Sinica,2014,69(4）:541-552.]   
[35］周晓艳,郝慧迪,叶信岳,等.黄河流域区域经济差异的时空动 态分析[J].人文地理,2016,31(5）：119-125.[ZHOU Xiaoyan,HAO Minhui,YE Xinyue,et al.A spatial-temporal analysis of regional economic inequality in Yellow River Valley[J].Human Geography,2016,31(5）:119 -125.]   
[36］郑欢欢.教育资源配置实质公平探索[J].教学与管理,2018, 65（30）:31-33.[ZHENG Huanhuan.Education resource allocation essence fair exploration[J].Teaching and Management,2018, 65(30) :31-33.]   
[37］张红娟.河北省"全面二孩"政策对基础教育资源配置的影响 研究[D].石家庄:河北经贸大学,2018.［ZHANG Hongjuan. Research on the influence of the policy of“comprehensive twochild"policy on the allcation of basic education resources in Hebei Province[D].Shi Jiazhuang:Hebei University of Economy and Trade,2018.]   
[38］李洋洋.“全面二孩"政策下学龄前人口变动对学前教育资源 配置的影响研究［D].金华：浙江师范大学,2017.［LI Yangyang.The study on the impact of pre-school population change on the early childhood educational resources allocation under the universal two-child policywith Hangzhou for a case study[D]. Jinhua;Zhejiang Normal University,2017.]   
[39］李晨铭.天津市内六区基础教育均衡化问题研究［D].天津： 天津商业大学,2017.[LI Chenming.Study on the basic education equilibrium issue of six districts in Tianjin[D]. Tianjin; Tianjin Commercial University,2017.]   
[40］卢文思.浙江省基础教育均等化问题研究［D].南昌：南昌大 学,2017.［LU Wensi. Study on the development of basic education equalization in Zhejiang Province[D]. Nanchang: Nanchang University,2017.]   
[41］黄云.城市基础教育资源区域配置问题的研究[D].徐州：中 国矿业大学,2016.[HUANG Yun.Study on urban basic education resource regional allocation issue:Regarding Xuzhou as an example[D]. Xuzhou:China University of Mining,2016.]   
[42］池娇,焦利民,董婷,等.基于POI数据的城市功能区定量识别 及其可视化[J].测绘地理信息,2016,41（2）:68-73.[CHI Jiao,JIAO Liming，DONG Ting,et al. Quantitative identification and visualization of urban functional area based on POI date[J]. Journal of Geomatics,2016,41(2）:68 -73.]   
[43]LONG Y,SHEN Z J. Geospatial analysis to support urban planning in Beijing[M].Switzerland:Springer,2015.

# Characteristics of spatial distribution of basic education resources in Xi'an City on street scale

WANG Xuel2，BAI Yong-ping'，WANG Fan’， ZHANG Min¹，CHE Lei (1College of Geographicand Environmental Science,Northwest Normal University,Lanzhou73o07O,Gansu,China; 2College of Tourism and Environment,Shaanxi Normal University,Xi'an 71Oo62,Shaanxi,China)

Abstract：Based on the data of POI education facilities,thespatial distribution characteristics of basic education resources in main urban area of Xi'an City,Shaanxi Province,China were analyzed at street scale using ArcGIS's standard deviation ellipse,kerneldensity estimation and GeoDa exploratory spatial data analysis（ESDA).Theresults show as follows:（1）From the spatial distribution perspective,the basic education resources in Xi'an City showed apattern witha high densityinthe citycenter andalow density outofthecenter,ahighdensity inthe west of the cityandalowdensityintheeastof thecity,andahigh densityinthe south of thecitybutalowdensity in thenorthof thecity.Intheviewofthedirectionof this distribution,there seems tohavealinefrom the northeastto the southwest with the later having ahigh density.（2）Location wise,the kindergartens and primary schools gather inbulk to form multi-center layout,while middle scholsare mainly concentrated in the centerof the city.（3) From thespatial aggomeration characteristics,the High-High districtsaremainly concentrated in the south and northof thecity,whiletheLow-Low districts are mainlyconcentrated inthespecial areas of thecentralurban area. In general,the spatial distribution characteristicsof basic education resources in Xi'an Citybasedonstreet scale can clearly reflect the spatial patern ofbasic education resources in Xi'an City,which could provide atheoretical basis for the relevant government departments to rationally plan the layout of educational facilities.

Key words:Xi'an City；basic education；spatial distribution；POI