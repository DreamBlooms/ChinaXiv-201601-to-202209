# 基于地理探测器的乌鲁木齐市城区扩展及影响因素分析

赵永玉¹，阿里木江·卡斯木}²，高鹏文}，梁洪武}

（1.新疆师范大学地理科学与旅游学院,新疆 乌鲁木齐830054;2.新疆师范大学丝绸之路经济带城镇化发展研究中心,新疆 乌鲁木齐830054)

摘要：以西北干旱区城市新疆乌鲁木齐市为例，利用2000、2010年和2020年3期LandsatTM及OLI遥感影像数据，采用随机森林分类方法，基于 $2 5 0 \mathrm { m } { \times } 2 5 0 \mathrm { m }$ 网格单元，计算每个网格单元中各类用地面积比率，对2000—2020年乌鲁木齐市土地覆被/土地利用(LUCC)空间特征进行分析，运用地理探测器模型进一步揭示其驱动因素，定量分析评价了2000—2020年乌鲁木齐市土地覆被/土地利用时空变化特征及响应因素。结果表明：(1)近20a乌鲁木齐市城市化发展迅速，建设用地面积大幅增加,在2000年建成区基础上向北、东北、西北以及东南方向不断蔓延发展，主要以向外扩张式发展，也存在向城市内部填充式集约增长的趋势。(2）近 $2 0 \mathrm { a }$ 绿地虽出现一定程度的波动，但总体表现为增长趋势;裸地始终在朝向持续减少的趋势发展。(3）影响乌鲁木齐市土地覆被/土地利用时空变化分异的主导影响因子是归一化植被指数(NDVI),其贡献率最高;在交互因子探测结果中，NDVI与高程共同作用时，呈现双因子增强,解释力最大。监测近20a乌鲁木齐市土地利用的动态变化，可更好地为当前乌鲁木齐城市发展提供借鉴，同时还可对城市未来规划方向进行借鉴。

关键词：土地利用；随机森林算法；网格单元；地理探测器；乌鲁木齐市

# 文章编号：

城市作为人类生活聚居的基本单元之一，其土地覆被/土地利用变化(LUCC)的空间量化作为全球变化研究的时代命题，已成为地理学研究的热点领域[-2],城市化进程步伐的不断推进,LUCC已成为人类与自然环境联结最密切的纽带之—[3-4]。国家新型城镇化规划(2014—2020年）中明确指明要逐步优化中国城镇化的发展格局，使中西部地区的城市逐渐作为区域协调发展的新的重要增长极点，促进中国同中亚乃至整个欧亚大陆的区域合作。土地是人类生产生活最基本的场所，为人类一切社会经济生产提供物质保障。针对区域土地覆被/土地利用进行时空分布特征研究，对未来区域土地合理利用与保护有较为深远的意义。

随着地理信息系统对于空间数据格局演变分析技术的迅速发展，针对LUCC空间信息可视化[5]定量化的研究开始大量涌现，国内外学者针对LUCC的动态变化[]环境效应[8]趋势走向及预测[9]等方面做了大量研究;在土地覆被/土地利用分类研究方法中，计算机学习算法得到大量应用，如陈磊士等[o利用Landsat8与Sentinel-1A影像为原始数据采用卷积神经网络和BP神经网络对昆明市主城区进行土地利用信息提取;李平等[针对遥感图像在土地利用监测应用中采用人工识别导致监测效率低的问题，提出采用支持向量机的自动识别方法和识别流程，以提高土地利用动态监测的自动化程度和监控效率；李国庆等使用Landsat8OLI数据同时采用随机森林分类模型和最大似然法对陕西省北部麻塔流域进行土地利用景观破碎化研究，赵海莉等[3使用地理探测器针对欠发达地区健康资源时空分异及影响因素进行研究，结果表明随机森

# 干吴区地理

林算法处理数据能力突出，抗噪音和拟合能力较为优越，分类结果清晰明确，随机森林分类模型整体准确性高于传统最大似然法。

对于土地利用的驱动机制研究，是揭示土地利用时空变化的重要途径，驱动力研究方法主要以主成分分析、Logistic回归模型和灰色关联度分析法等。近年来，地理探测器在分析因素驱动力方面得到了大量关注[4]，该方法对于类别变量的计算不需要额外的线性假设[15],采用地理探测器所建立变量之间的关系比经典回归更加准确[16]。目前针对城市各土地利用类型时空变化分析中，多以城市内整体动态变化为主"，针对各区域内局部精细变化的定量分析相对缺乏，因此无法定量分析研究区内不同土地类型的空间分异性[18]。空间网格单元可以更好的基于微观角度定量分析区域土地利用的时空变化["]，能够将相关的各类自然以及社会经济因素转入网格单元，微观、定量的分析研究区内各区域土地利用类型的驱动力因素。

本研究从网格视角出发，精确、微观地分析2000一2020年乌鲁木齐市在不同方向、不同区域的时空变化特征，采用分类精度更高、性能更优越的随机森林算法计算，结合土地利用转移矩阵，针对各土地利用类型之间的替代和互相转化的过程进行定量分析。在使用遥感技术方法的基础上叠加网格的方法，更加精细和准确的反映近20a乌鲁木齐市土地利用的动态变化，可更好地为当前乌鲁木齐城市发展提供借鉴，同时还可对城市未来发展进行预测。

# 1研究区概况

乌鲁木齐市地处我国西北部，位于新疆天山中段北麓、准噶尔盆地南缘，坐落于欧亚大陆中心腹地，是我国向西开放的重要门户，也是“一带一路”倡议下丝绸之路经济带核心区的首府城市。市区三面环山，东南部与吐鲁番地区相邻，东部和西部与昌吉回族自治州相接，南部与巴音郭楞蒙古自治州交界[20],市区呈现形似狭长的"T"形峡谷盆地，地势呈现西北低、南北高，平均高程 $8 0 0 \mathrm { ~ m ~ }$ 左右，兼具平原城市和山地城市的特点[21]。近年来乌鲁木齐市城市化进程不断加快，逐渐成为新疆政治、文化、金融的核心区位，对全疆及中亚地区的辐射作用日益增强。由于乌鲁木齐市得天独厚的地缘和区位优势，逐步发展为一座新型综合性绿洲城市。

# 2 数据来源与研究方法

# 2.1数据来源

本研究采用3期Landsat TM(Thematic mapper)及OLI(Operationalland imager)遥感影像数据（表1），分别为2000、2010年和2020年，来源于USGS（美国地质调查局,http://www.usgs.gov/）,成像时间均选择7一9月，在一定程度上避免土地覆被/土地利用变化季节性变化的影响，空间分辨率 $3 0 \mathrm { ~ m ~ }$ ，天气状况良好。气象数据采用中国气象数据共享服务网，包括乌鲁木齐市1981—2015年年均降水量、年平均气温、月降水量、日照时数、蒸发量、日平均风速等数据。数字高程模型(Digitalelevation mod-el,DEM)数据来源于地理空间数据云，分辨率为90$\mathrm { m } { \times } 9 0 \mathrm { m }$ ，并通过ArcGIS计算坡度、地形起伏度和河网密度。归一化植被指数（Normalizeddifferencevegetationindex，NDVI)数据来源于中国科学院资源环境科学数据中心的中国年度植被指数空间分布数据集。社会经济数据包括2000一2018年新疆维吾尔自治区统计年鉴;人口、国内生产总值(GDP)网格插值数据，来源于中国科学院资源环境科学数据中心。

表1遥感影像数据信息说明  
Tab.1 Information description of remote sensing image data   

<html><body><table><tr><td>年份</td><td>影像选取时间(年-月-日)</td><td>条带号(列/行)</td><td>传感器</td><td>分辨率/m</td></tr><tr><td>2000</td><td>2000-09-02</td><td>142/30</td><td>Landsat 5 TM</td><td>30</td></tr><tr><td></td><td>2000-09-12</td><td>143/29</td><td></td><td></td></tr><tr><td></td><td>2000-08-08</td><td>143/30</td><td></td><td></td></tr><tr><td>2010</td><td>2010-08-13</td><td>142/30</td><td>Landsat 5 TM</td><td>30</td></tr><tr><td></td><td>2010-08-20</td><td>143/29</td><td></td><td></td></tr><tr><td></td><td>2010-08-20</td><td>143/30</td><td></td><td></td></tr><tr><td>2020</td><td>2020-08-24</td><td>142/30</td><td>Landsat 8 OLI</td><td>30</td></tr><tr><td></td><td>2020-07-14</td><td>143/29</td><td></td><td></td></tr><tr><td></td><td>2020-09-16</td><td>143/30</td><td></td><td></td></tr></table></body></html>

# 2.2 研究方法

2.2.1土地覆被/土地利用分类由于干旱区城市土地分类普遍出现"异物同谱，同物异谱"现象[22],基于中低分辨率的遥感影像针对城市用地提取有一定难度，裸地和建设用地在影像分类结果中混淆提取的现象较为频繁[23],而本研究不仅研究乌鲁木齐市近20a土地利用的整体时空变化，更侧重于城市不同区域内部精细变化，因此对土地利用分类精度要求非常高[24]。在充分考虑到乌鲁木齐市土地利用类型特征，将11个土地利用类型合并为4个一级土地利用单元(表2)，即绿地、建设用地、水体和裸地(包括没有植被覆盖的山体)[25],以期通过减少土地利用类型来提高分类精度[26]

2.2.2随机森林分类随机森林分类是一种集成学习的组合分类方法，其核心思想就是将若干个基于决策树的弱分类器组合起来，得到一个分类结果精确的强分类器森林[27]。由学者Breiman[28]提出的一种基于决策树算法构成的机器训练算法，最终由多颗树的分类器采用投票方式得到分类结果[29]。该算法无需对数据进行降维处理，适用于处理高维数据,不易产生过拟合的问题[30]。相较于支持向量机、决策树、人工神经网络等传统机器算法，在分类

# 表2乌鲁木齐市土地利用分类

Tab.2 Land use classification of Urumqi City   

<html><body><table><tr><td rowspan="2">一级分类</td><td colspan="2">二级分类</td></tr><tr><td>编号</td><td>类型</td></tr><tr><td>建设用地</td><td>11</td><td>城镇</td></tr><tr><td rowspan="7">绿地</td><td>12</td><td>工矿</td></tr><tr><td>13</td><td>交通用地</td></tr><tr><td>14</td><td>居民点</td></tr><tr><td>21</td><td>林地</td></tr><tr><td>22</td><td>草地</td></tr><tr><td>23</td><td>耕地</td></tr><tr><td>31</td><td>水库</td></tr><tr><td rowspan="3">裸地</td><td>32</td><td>湖泊</td></tr><tr><td>41</td><td>山地</td></tr><tr><td>42</td><td>未利用地</td></tr></table></body></html>

效率和分类精度等方面具有更优秀的性能[31]。因此，越来越多学者在通过遥感影像提取高精度分类结果时使用随机森林机器算法[32-33]。

2.2.3网格单元法网格单元法是以ArcGIS为平台，以研究区边界为范围根据研究实际需要建立矢量网格，将基于遥感影像得到的分类结果转入相应位置的网格单元中，分别统计每个网格单元内各地类所占网格单元面积百分比(图1)。在各土地利用转入网格单元时存在横跨多个网格单元边界像元的现象，以往研究多将此类像元优先纳入所占网格面积较大的单元，这会造成每一网格单元实际面积小于分配到网格单元的用地面积，与实际情况有出人[19]。本研究将基于遥感影像数据采用随机森林机器算法的土地利用分类结果转为矢量数据，与建立的矢量网格进行相交处理，使横跨多个网格单元边界的斑块被网格裁剪为多个小块面积 $\left( { { A } _ { t } } \right)$ ，计算每一网格单元内土地利用类型面积并求和，然后计算在相应网格单元内所占面积比例 $( P _ { t } )$ ，公式如下：

![](images/a225d4907b49c6096e99cd222f66dd98ede65cb52cdadbd1676978a1be386271.jpg)  
图1土地覆被/土地利用数据网格化示意图Fig.1 Grid diagram of land cover/land use data

# 干吴区地理

$$
P _ { \mathrm { \Delta } t } = \frac { \displaystyle \sum _ { i = 0 } ^ { n } A _ { \mathrm { \Delta } } } { A _ { \mathrm { \Delta } g } } \times 1 0 0 \%
$$

式中： $P _ { t }$ 为土地利用类型 $\mathbf { \Phi } _ { t }$ 在每个网格单元内所占面积比重 $( \% ) { \bf { \sigma } } _ { ; { \bf { \mathcal { A } } } _ { t } }$ 为每个网格内土地利用类型 $\mathbf { \Phi } _ { t }$ 被分割后的小块图斑面积 $( \mathrm { k m } ^ { 2 } ) ; n$ 为每一网格单元内土地利用类型 $\mathbf { \Phi } _ { t }$ 被裁剪后的数量； $A _ { g }$ 为每个网格单元实际面积 $( \mathrm { k m } ^ { 2 } ) ; g$ 为网格单元数(个）。

考虑到研究区面积、计算机运行效率以及本文研究目的等，反复实验后，确定将每个矢量网格单元大小设定为 $2 5 0 ~ \mathrm { m } \times 2 5 0 ~ \mathrm { m }$ ，总计27694个网格单元。

2.2.4地理探测器针对空间分异性的探测是地理探测器的核心特点之一，旨在揭示其内在驱动力的一种新兴统计学手段，能够有效地筛选各变量因子之间的空间分异性[]。因子探测器可以量化不同变量之间对土地利用类型时空变化分异性，并探测其影响程度大小，公式如下：

$$
q = 1 - \frac { \displaystyle \sum _ { h = 1 } ^ { L } N _ { h } \sigma ^ { 2 } h } { N \sigma ^ { 2 } }
$$

式中： $L$ 为影响因子的类型数； $N _ { h \setminus } N$ 分别为类型量 $h$ 和整个区域的样本数; $\sigma ^ { 2 }$ 为影响因子的离散方差; $q$ 为某个因子对土地利用类型的探测力值， $q$ 的值域是 $[ 0 , 1 ] , q$ 值越大表明该因子对土地利用类型空间分布影响越大，反之则越小。

交互作用探测即判断不同影响因子之间的交互作用，即评价因子 $X$ 和Y共同作用时是否会改变其对土地利用类型的解释力，2个因子之间的相互作用关系可分为5类(表3)。

# 3 结果与分析

3.1乌鲁木齐市土地覆被/土地利用总体变化分析基于遥感影像分类结果以及统计近20a各土地利用类型面积和变化比例(图2、表4)可知：(1)2000年以来裸地面积逐渐减少，由2000年的$7 7 2 8 . 1 3 \ \mathrm { k m } ^ { 2 }$ 减少到2020年的 $7 5 6 8 . 6 8 \mathrm { ~ k m } ^ { 2 }$ ;(2)建设用地在这20a不断增加，由2000年的 $2 4 1 . 4 3 ~ \mathrm { k m } ^ { 2 }$ 增加到2020年的 $8 7 7 . 8 6 ~ \mathrm { k m } ^ { 2 }$ ,建成区面积增长率达$2 6 3 . 6 0 \%$ 以上；（3）绿地面积在2000—2020年呈现一定波动，从2000年 $4 0 . 8 2 \%$ 到2010年 $3 3 . 9 4 \%$ 再到2020年的 $3 8 . 3 6 \%$ ，呈现先减少再增加的趋势；(4)水体面积有所波动，总体表现为增加趋势，但整个土地利用类型中所占比例在 $3 . 0 0 \%$ 左右，面积变化不太明显。

从图3不同时期土地利用动态度来看，各类土地利用变化的大小依次为：建设用地 $>$ 绿地 $>$ 裸地>水体。2000一2020年，各土地利用类型的动态变化起伏度较大，其中建设用地和绿地面积以 $2 2 . 5 1 \%$ 、$0 . 9 5 \%$ 的速率增加，而裸地和水体面积以 $0 . 2 4 \%$ 、$1 . 1 6 \%$ 的速率在逐渐减少。主要原因是随着乌鲁木齐这些年城市化进程的加快，城市用地面积不断增加，建设用地不断侵占周边裸地、农田、草地等，使得他们的面积不断减少。

# 3.2乌鲁木齐市土地覆被/土地利用转移矩阵特征分析

土地利用类型面积的增减不能直观反映各土地利用类型间的转化情况，采用转移矩阵(图4、表5)对乌鲁木齐市2000—2020年土地覆被/土地利用各类型之间相互转化的过程进行分析。近20a乌鲁木齐市的建设用地面积有了大幅增加，从多时相遥感影像数据各土地类型转化图中可知，在整个研究期间，各土地利用类型都发生了一定程度的相互转化，2000一2020年，裸地、绿地和建设用地的转化较为明显，转为建设用地的土地利用类型的转移面积大小顺序为裸地 $>$ 绿地 $>$ 水体，3种土地利用类型在大面积转入的同时存在大面积的转出(表5)。建设用地的增加主要是由 $4 8 . 7 5 ~ \mathrm { k m } ^ { 2 }$ 裸地和 $3 8 . 8 2 \mathrm { k m } ^ { 2 }$ 绿

# 表3双因子交互作用结果类型

Tab.3 Types of two-factor interaction result   

<html><body><table><tr><td>判断依据</td><td>交互作用类型</td></tr><tr><td>q(Xi∩X2)<Min[q(Xi),q(X2)]</td><td>非线性减弱</td></tr><tr><td>Min[q(Xi1),q(X2)]<q(X,∩X2)<Max[q(X1),q(X2)]</td><td>单因子非线性减弱</td></tr><tr><td>q(Xi∩X2)>Max[q(Xi),q(X2)]</td><td>双因子增强</td></tr><tr><td>q(Xi∩X2)=q(Xi)+q(X2)</td><td>独立</td></tr><tr><td>q(X∩X2)>q(Xi)+q(X)</td><td>非线性增强</td></tr></table></body></html>

注：q为某个因子对土地利用类型的探测力值； $X _ { 1 } , X _ { 2 }$ 为某两评估因子。下同。

![](images/7b9c5fd95dbed0dbaf225a938837aa3be9af71a70defd5ea9e4f28dff5910df2.jpg)  
赵永玉等：基于地理探测器的乌鲁木齐市城区扩展及影响因素分析  
图2不同时期乌鲁木齐市土地覆被/土地利用

表4不同时期乌鲁木齐市土地利用面积特征  
Tab.4Characteristics of land use area in Urumqi City in different periods   

<html><body><table><tr><td rowspan="2">土地利用类型</td><td colspan="2">2000年</td><td colspan="2">2010年</td><td colspan="2">2020年</td></tr><tr><td>面积/km²</td><td>比重/%</td><td>面积/km²</td><td>比重/%</td><td>面积/km²</td><td>比重/%</td></tr><tr><td>建设用地</td><td>241.43</td><td>1.70</td><td>542.73</td><td>3.82</td><td>877.86</td><td>6.18</td></tr><tr><td>绿地</td><td>5795.47</td><td>40.82</td><td>4818.91</td><td>33.94</td><td>5446.31</td><td>38.36</td></tr><tr><td>裸地</td><td>7728.13</td><td>54.43</td><td>8608.12</td><td>60.63</td><td>7568.68</td><td>53.31</td></tr><tr><td>水体</td><td>433.13</td><td>3.05</td><td>228.40</td><td>1.61</td><td>305.31</td><td>2.15</td></tr><tr><td>总计</td><td>14198.16</td><td>100.00</td><td>14198.16</td><td>100.00</td><td>14198.16</td><td>100.00</td></tr></table></body></html>

![](images/d28744a3d0c5cd8a50f367b1e30cd2e609fcbecef277155f3a12d01a9c649aee.jpg)  
Fig.2Land cover/land use distributions of Urumqi City in different periods   
图3不同时期土地利用动态度面积特征  
Fig.3 Characteristics of dynamic degree and area of different land use types in different periods

地转入，这是因为城市化的不断发展，导致大面积耕地被转化为建设用地，部分城市内绿地、林地和裸地伴随着土地利用活动的加剧逐渐转化为建设用地。近20a绿地面积也在不断增长，主要由$1 2 4 9 . 8 2 ~ \mathrm { k m } ^ { 2 }$ 裸地转入，这与乌鲁木齐市近年实行“荒山绿化”工程密切相关，建成区绿化普及率由1990年的 $2 1 . 8 \%$ 提高到现在的 $3 6 . 1 6 \% ^ { [ 3 4 ] }$ ,这项工程使得乌鲁木齐市许多区域绿地面积大幅度增加，如雅玛里克山、红光山、蜘蛛山等乌鲁木齐市重点改造绿化的区域。

![](images/aa608d08e4ac3538b9a61060743063e337b03a37a9033bca99c2ea307c0c81f7.jpg)  
干吴区地理  
图42000—2020年乌鲁木齐市年土地类型转移矩阵  
Fig.4Transfer matrix of land types in Urumqi City from 20o0 to 2020

表52000—2020年乌鲁木齐市土地类型转移矩阵  
Tab.5 Transfer matrix of land types in Urumqi City from 2ooo to 2020   

<html><body><table><tr><td rowspan="2">2000年</td><td colspan="5">2020年</td></tr><tr><td>建设用地</td><td>裸地</td><td>绿地</td><td>水体</td><td>总计</td></tr><tr><td>建设用地</td><td>138.13</td><td>419.31</td><td>276.02</td><td>35.66</td><td>869.12</td></tr><tr><td>裸地</td><td>48.75</td><td>6168.61</td><td>1249.82</td><td>99.75</td><td>7566.93</td></tr><tr><td>绿地</td><td>38.82</td><td>1063.89</td><td>4252.87</td><td>103.17</td><td>5458.75</td></tr><tr><td>水体</td><td>4.37</td><td>92.32</td><td>15.51</td><td>191.16</td><td>303.36</td></tr><tr><td>总计</td><td>230.07</td><td>7744.13</td><td>5794.22</td><td>429.74</td><td>14198.16</td></tr></table></body></html>

近 $2 0 \mathrm { a }$ 建设用地面积一直呈递增趋势，在不同方向、不同区域有非常大的差异，在2000年的建成区基础上向北、东北、西北以及东南方向不断蔓延发展，主要以向外扩张式发展，也存在向城市内部填充式集约增长的趋势(图5)。这是由多重因素叠加作用形成，近几年乌鲁木齐市一直实行区域一体政策，如"乌昌一体化”“乌昌都市圈""兵地融合"[35]等，促进了乌鲁木齐市与位于西北方向的昌吉市、石河子市、北部兵团城市五家渠市、东北部阜康市等地的经济往来日益增加，形成密切融合交往的联合发展，以及在2007年乌鲁木齐市将位于东北部的米泉市并入行政区，推动了建成区继续向东北方向建设;城市道路系统对城市扩展具有一定的“牵引"特性[36-37],如S111省道、连霍高速、吐乌大高速、乌昌快速路、G216等对城市建设用地向西北、东北和东南方向牵引发展起到了一定促进和推动作用。从自然环境来看，乌鲁木齐市三面环山，主城区地势较高，这种地形地貌导致了主城区沿河流两岸由南向北延伸，在北部平原又向东西两侧伸展，加剧“T"形分布。

# 3.3乌鲁木齐市土地覆被/土地利用时空分布驱动因子分析

由因子探测结果可知（表6)，2000、2010年和2020年不同因子对土地利用时空分布的解释力从大到小排序依次为NDVI>DEM>坡度>河网密度>人口密度 $>$ 降水量 $\mathrm { > }$ GDP>年平均气温>日照时数。影响乌鲁木齐市2000—2020年土地覆被/土地利用时空分布的第一主导因素是NDVI,其平均贡献率达0.33,第二主导因素为DEM，平均贡献率为0.24。由此可知,NDVI是引起乌鲁木齐市2000—2020年土

![](images/9eb6dbe20a52d75aa75a7bdedec54514926ee2987e4dca7a0f70a025f390a8a8.jpg)  
图5不同时期乌鲁木齐市建设用地分布  
Fig.5Distribution of construction land in Urumqi City in different periods

# 表6乌鲁木齐市土地利用年际因子探测结果

Tab.6 Detection results of interannual factors of land use in Urumqi City   

<html><body><table><tr><td colspan="4">IanduseinUrumql City</td></tr><tr><td rowspan="2">因子</td><td colspan="3">q值</td></tr><tr><td>2000年</td><td>2010年</td><td>2020年</td></tr><tr><td>DEM</td><td>0.30</td><td>0.14</td><td>0.29</td></tr><tr><td>GDP</td><td>0.11</td><td>0.07</td><td>0.10</td></tr><tr><td>NDVI</td><td>0.34</td><td>0.35</td><td>0.29</td></tr><tr><td>河网密度</td><td>0.18</td><td>0.12</td><td>0.22</td></tr><tr><td>降水量</td><td>0.10</td><td>0.09</td><td>0.11</td></tr><tr><td>坡度</td><td>0.21</td><td>0.15</td><td>0.19</td></tr><tr><td>人口密度</td><td>0.12</td><td>0.02</td><td>0.06</td></tr><tr><td>日照时数</td><td>0.07</td><td>0.15</td><td>0.07</td></tr><tr><td>年平均气温</td><td>0.08</td><td>0.09</td><td>0.08</td></tr></table></body></html>

注：DEM为高程;GDP为地区生产总值;NDVI为归一化植被指数。

地覆盖/土地利用时空分布的重要驱动因子，成为乌鲁木齐市土地覆盖/土地利用变化最大威胁源。这也体现了乌鲁木齐市作为典型的干旱区绿洲城市，受干旱区自然和人文因素双重影响的脆弱生态系统，人地关系极为敏感，城市发展依托绿洲的分布，具有唯水性，使得乌鲁木齐市城市无法成为特大城市，只能依托其生态承载力在绿洲内集聚生活生产。

由交互探测结果可知(图6)，以2020年结果为例（2000年和2010年的结果与其作用方式相同），各因子交互作用呈现非线性增强和双因子增强的结果，总体表现为各因子交互作用均为增强作用，说明各因素之间具有显著的协调性与关联性。其中NDVI与DEM共同作用时，呈现双因子增强，解释力最大。

# 4结论

本文利用遥感数据，分析了2000一2020年乌鲁木齐市土地覆盖/土地利用的时空变化规律，反映了乌鲁木齐市城市扩展的动态变化。基于转移矩阵与变化检测的文章多以研究区内土地覆被/土地利用总体变化以及类型相互转化为主，针对城市内部精细化定量分析较少。因此，本研究基于网格视角，精确、微观的分析乌鲁木齐市在不同方向、不同区域的时空变化特征，采用分类精度更高、性能更优越的随机森林算法计算，结合土地利用转移矩阵，可以更好的针对各土地利用类型之间的替代和互相转化的过程进行定量分析，得出以下结论：

（1）近20a乌鲁木齐市在城市化发展迅速，建设用地面积大幅增加，在2000年的建成区基础上向北、东北、西北以及东南方向不断蔓延发展，主要以向外扩张式发展，也存在向城市内部填充式集约增长的趋势。

(2）近20a绿地虽出现一定程度的波动，但总体表现为增长趋势;裸地始终在朝向持续减少的趋势发展。政府长期实行“荒山绿化"工程，如雅玛里克山、红光山、蜘蛛山等乌鲁木齐市重点改造绿化的区域，使得乌鲁木齐市许多区域绿地面积大幅度增加。

干旱区地理  
图62020年乌鲁木齐市交互探测结果  
Fig.6Interactive detection results of Urumqi City in 2020   
![](images/4b6a4c9568264b4a7abcca89784923acba1dd537141c0b1548d79bdcc80bc55e.jpg)  
注：\*代表两两因子的交互作用为非线性增强； $^ +$ 代表双因子增强；无标记代表无显著差异。DEM为高程;GDP为地区生产总值；NDVI为归一化植被指数； $q$ 为某个因子对土地利用类型的探测力值。

(3）采用地理探测器辨别引起土地覆被/土地利用时空变化分异的主要影响因素，得出主导影响因子是NDVI贡献率最高，其次为DEM,绿洲分布和地形地貌条件导致了乌鲁木齐市土地覆被/土地利用分布格局；在交互因子探测结果中，均呈现非线性增强和双因子增强，说明各因素之间具有显著的协调性与关联性。其中NDVI与DEM共同作用时，呈现双因子增强，解释力最大。

# 参考文献(References)

[1]刘亚茹,王聪,严力蛟.华北平原农区土地利用变化对生态系统 服务的影响—以河南省商丘市为例[J].应用生态学报, 2018,29(5):1597-1606.[Liu Yaru,Wang Cong,Yan Lijiao.Impacts of land use change on ecosystem services in the agricultural area of North China Plain:A case study of Shangqiu City,Henan Province,China[J]. Chinese Journal of Applied Ecology,2018,29

(5): 1597-1606.]

[2] 刘金勇,孔繁花,尹海伟,等.济南市土地利用变化及其对生态 系统服务价值的影响[J].应用生态学报，2013,24(5)：1231- 1236.[Liu Jinyong,Kong Fanhua,Yin Haiwei,et al. Land use change and its effects on ecosystem service value in Jinan City of Shandong Province,east China[J]. Chinese Journal of Applied Ecology,2013,24(5): 1231-1236.]   
[3] Gao J,Li F,Gao H,et al. The impact of land-use change on waterrelated ecosystem services:A study of the Guishui River Basin, Beijing, China[J]. Journal of Cleaner Production,2O16,163(Suppl.1): 148-155.   
[4] Shen G,Yang X C,Jin Y X,etal. Land use changes in the Zoige Plateau based on the object-oriented method and their effects on landscape patterns[J].Remote Sensing,2019,12(1):14,doi: 10.3390/rs12010014.   
[5] Genbatu Ge,Shi Z J, Zhu YJ,et al.Land use/cover classification in an arid desert-oasis mosaic landscape of China using remote sensed imagery: Performance assessment of four machine learning algorithms[J].Global Ecology and Conservation,2020,22,doi: 10.1016/j.gecco.2020.e00971.   
[6] Meghan Blumstein, Jonathan R Thompson.Land-use impacts on the quantity and configuration of ecosystem service provisioning in Massachusetts,USA[J]. Journal of Applied Ecology,2015,52(4): 1009-1019.   
[7]韩海青,王旭红,牛林芝,等.1992—2015年中亚五国LUCC 特 征及耕地驱动力研究[J].中国生态农业学报,2021,29(2):325- 339.[Han Haiqing,Wang Xuhong,Niu Linzhi, et al. The LUCC characteristics and driving forces of cultivated land in the five Central Asian countries from 1992 to 2015[J].Chinese Journal of Eco-Agriculture, 2021, 29(2): 325-339.]   
[8]Zhang M Y, Zhang L, Ren X L,et al. Effect of land use and land cover change on the changes in net primary productivity in karst areas of southwest China: A case study of Huanjiang Maonan Autonomous County[J]. Journal of Resources and Ecology,2020,11 (6): 606-616.   
[9]朱增云,阿里木江·卡斯木.基于CA-Markov模型的呼图壁县土 地利用景观格局预测研究[J].生态科学,2020,39(1):136-145. [Zhu Zengyun, Kasimu Alimujiang.Prediction of land use landscape patten in Hutubi County based on CA-Markov model[J]. Ecological Science,2020,39(1): 136-145.]   
[10] 陈磊士,赵俊三,李易,等.基于机器学习的多源遥感影像融合 土地利用分类研究[J].西南师范大学学报(自然科学版),2018, 43(10): 103-111.[Chen Leishi, Zhao Junsan,Li Yi,et al. On land use clasification by means of machine learning based on muitisource remote sensing fusion[J]. Journal of Southwest China Normal University (Natural Science Edition),2018,43(10): 103-111.]   
[11] 李平,吴曼乔,曾联明.支持向量机技术在土地利用监测的应用 研究[J].测绘通报,2010(8):28-30,67.[Li Ping,Wu Manqiao, Zeng Lianming. On application of suport vector machine technology to land use monitoring[J]. Bulletin of Surveying and Mapping, 2010(8): 28-30, 67.]   
[12] 李国庆,黄菁华,刘冠,等.基于Landsat8卫星影像土地利用景 观破碎化研究——以陕西省延安麻塔流域为例[J].国土资源 遥感,2020,32(3): 121-128.[Li Guoqing,Huang Jinghua, Liu Guan, et al.A study of the landscape fragmentations of land cover structure based on Landsat8 remote sensing image: A case study of Mata Watershed in Yan'an, Shaanxi Province[J].Remote Sensing for Land and Resources,2020,32(3): 121-128.]   
[13] 赵海莉,王启雯,朱立祥,等.基于地理探测器的欠发达地区健 康资源时空分异及影响因素研究[J].干旱区地理,2021,44(2): 594-603.[Zhao Haili,Wang Qiwen, Zhu Lixiang,et al.Analysis of spatial-temporal evolution and influencing factors of health resources in underdeveloped areas basedon geodetectors[J].Arid Land Geography,2021,44(2): 594-603.   
[14] 郑续,魏乐民,郭建军,等.基于地理探测器的干旱区内陆河流 域产水量驱动力分析——以疏勒河流域为例[J].干旱区地理, 2020,43(6):1477-1485.[Zheng Xu,Wei Lemin,Guo Jianjun,et al. Driving force analysis of water yield in inland riverbasins of arid areas based on geo-detectors: A case of the Shule River[J]. Arid Land Geography,2020,43(6): 1477-1485.]   
[15]吕晨,蓝修婷,孙威.地理探测器方法下北京市人口空间格局变 化与自然因素的关系研究[J].自然资源学报,2017,32(8): 1385-1397.[Lu Chen,Lan Xiuting,Sun Wei.A study on the relationship between natural factors and population distribution in Beijing using geographical detector[J]. Journal of Natural Resources, 2017,32(8): 1385-1397.]   
[16] 王劲峰,徐成东.地理探测器:原理与展望[J].地理学报,2017, 72(1): 116-134.[Wang Jinfeng, Xu Chengdong. Geodetector: Principle and prospective[J].Acta Geographica Sinica,2017,72(1): 116-134.]   
[17] 王冬辰,杜培军,苏红军,等.近20年大同市土地利用/覆盖遥 感变化分析[J].干旱区资源与环境,2015,29(7):68-75.[Wang Dongchen,Du Peijun,Su Hongjun,et al. Land use/land cover changes in Datong based on remote sensing data[J]. Journal of Arid Land Resources and Environment,2015,29(7): 68-75.]   
[18]Schirpke U,Kohler M,Leitinger G,etal.Future impacts ofchanging land-use and climate on ecosystem services of mountain grassland and their resilience[J]. Ecosystem Services,2017,26: 79-94.   
[19] 鄂子骥,阿里木江·卡斯木,买买提江·买提尼亚孜,等.基于网 格单元的西北干旱区城市土地覆被/土地利用时空变化研究 —以新疆喀什市为例[J].干旱区地理,2018,41(3):625-633. [E Ziji,Kasimu Alimiujiang,Maitiniyazi Maimaitijiang,etal. Temporal and spatial variations of urban land cover/land use based on grid element in northwest arid area of China: A case of Kashgar City in Xinjiang[J].Arid Land Geography,2018,41(3): 625-633.]   
[20] 阿里木江·卡斯木,玉苏普江·艾麦提.基于ALOS数据的乌鲁 木齐市绿地景观格局研究[J].地域研究与开发,2012,31(2): 86-89. [Kasimu Alimujiang, Aimaitia Yusupujiang. Study on spatial structure of urban greenbelt landscapes in Urumqi City based on ALOS satelite image[J].Areal Research and Development, 2012,31(2): 86-89.]   
[21] 哈孜亚·包浪提将,毋兆鹏,陈学刚,等.乌鲁木齐市景观格局变 化及驱动力分析[J].生态科学,2018,37(1):62-70.[Baolangtijiang Haziya, Wu Zhaopeng, Chen Xuegang,et al. Analysis of landscape pattern change and driving force in Urumqi City[J]. Ecological Science,2018,37(1): 62-70.]   
[22] 赵领娣,李莎莎,赵志博,等.干旱半干旱区城市生态效率时空 演变及区域差异分析[J].干旱区地理,2020,43(2):449-457. [Zhao Lingdi,Li Shasha, Zhao Zhibo,et al. Temporal and spatial evolution and regional diference analysis of urban ecological eficiency in arid and semiarid areas[J]. Arid Land Geography,2020, 43(2): 449-457.]   
[23] 吴志杰,赵书河.基于TM图像的"增强的指数型建筑用地指 数”研究[J].国土资源遥感,2012,93(2):50-55.[Wu Zhijie, Zhao Shuhe.A study of enhanced index-based built-up index based on Landsat TM imagery[J]. Remote Sensing for Land & Resource,2012,93(2): 50-55.]   
[24]Ghulam Abduwasit, Ghulam Oghlan,Maitiniyazi Maimaitijiang,et al.Remote sensing based spatial statistics to document tropical rainforest transition pathways[J].Remote Sensing，2015，7(5):

# 干吴区地理

6257-6279.

[25] 王珊珊,陈曦,段含明,等.城市地表温度对土地利用/覆被变化 响应的遥感研究—以乌鲁木齐为例[J].中国沙漠,2012,32 (3): 878-884.[Wang Shanshan, Chen Xi, Duan Hanming,et al. Study on responsse of land surface temperature to land use and land cover change using remote sensing data: A case on Urumqi, China[J]. Journal of Desert Research,2012,32(3): 878-884.]   
[26]Sexton JO, Urban D L,Donohue M J,et al. Long-term land cover dynamics by multi-temporal classification across the Landsat-5 record[J].Remote Sensing of Environment, 2013,128: 246-258.   
[27] 赵亚杰,王立辉,孔祥兵,等.基于Sentinel-2和Landsat 8 OLI数 据融合的土地利用分类研究[J].福建农林大学学报(自然科学 版),2020,49(2): 248-255.[Zhao Yajie,Wang Lihui,Kong Xiangbing,et al.Land use classification based on data fusion of Sentinel-2 and Landsat 8 OLI[J]. Journal of Fujian Agriculture and Forestry University (Natural Science Edition),2020,49(2): 248-255.]   
[28]Breiman L. Random forests[J]. Machine Learning, 20O1,45(1): 5- 32.   
[29] 董师师,黄哲学.随机森林理论浅析[J].集成技术,2013,2(1):1- 7.[Dong Shishi,Huang Zhexue.A brief theoretical overview of random forests[J]. Journal of Integration Technology,2013,2(1): 1-7.]   
[30]张卫春,刘洪斌,武伟.基于随机森林和Sentinel-2影像数据的 低山丘陵区土地利用分类——以重庆市江津区李市镇为例 [J].长江流域资源与环境,2019,28(6):1334-1343.[Zhang Weichun,Liu Hongbin,Wu Wei.Classification of land use in low mountain and hilly area based on random forest and Sentinel-2 satelite data: A case study of Lishi Town, Jiangjin,Chongqing[J]. Resources and Environment in the Yangtze Basin,2019,28(6): 1334-1343.]   
[31] 谷晓天.基于机器学习的湟水流域土地利用/土地覆被分类研 究[D].西宁:青海师范大学,2018.[Gu Xiaotian.Research on land use/land cover classification based on machine learning in

the Huangshui River Basin[D].Xining:Qinghai Normal University,2018.]

[32] 王娜,李强子,杜鑫,等.单变量特征选择的苏北地区主要农作 物遥感识别[J].遥感学报,2017,21(4):519-530.[Wang Na,Li Qiangzi,Du Xin,et al.Identification of main crops based on the univariate feature selection in Subei[J]. Journal of Remote Sensing,2017,21(4): 519-530.]   
[33] 朱永森,曾永年,张猛.基于HJ卫星数据与面向对象分类的土 地利用/覆盖信息提取[J].农业工程学报,2017,33(14):258- 265.[Zhu Yongsen, Zeng Yongnian, Zhang Meng. Extract of land use/cover information based on HJ satellites data and object-oriented classification[J]. Transactions of the Chinese Society of Agricultural Engineering,2017,33(14): 258-265.]   
[34] 买买提江·买提尼亚孜,阿里木江·卡斯木.基于网格单元的乌 鲁木齐市土地覆被/利用时空变化[J].农业工程学报,2018,34 (1): 210-216.[Maitiniyazi Maimaitijiang,Kasimu Alimujiang. Spatial-temporal change of Urumqi urban land use and land cover based on grid cell approach[J]. Transactions of the Chinese Society of Agricultural Engineering,2018,34(1): 210-216.]   
[35]方创琳.天山北坡城市群可持续发展战略思路与空间布局[J]. 干旱区地理,2019,42(1): 1-11.[Fang Chuanglin. Strategic thinking and spatial layout for the sustainable development of urban agglomeration in northern slope of Tianshan Mountains[J].Arid Land Geography,2019,42(1): 1-11.]   
[36] 杨雅楠,阿里木江·卡斯木.“一带一路"背景下新疆城镇交通优 势度与区域经济发展水平的关系分析[J].干旱区地理,2017, 40(3): 680-691.[Yang Ya'nan, Kasimu Alimujiang.Relationship between regional transportation advantage and development of reginal economy in Xinjiang under the background of the national strategy of the Belt and Road[J].Arid Land Geography,2017,40 (3): 680-691.]   
[37] 王雪微,王士君,宋飚,等.交通要素驱动下的长春市土地利用时 空变化[J].经济地理,2015,35(4):155-161.[Wang Xuewei,Wang Shijun,Song Yang,et al. Changchun land use spatio-temporal variation under the trasportation elements’driving[J]. Economic Geography,2015,35(4): 155-161.]

# Quantitative analysis of urban expansion and response factors in Urumqi City based on random forest algorithm and geographical detector

ZHAO Yongyu'， Alimujiang KASIM'²， GAO Pengwen'， LIANG Hongwu' (1.SchoolofGeographicSienceandTourism,XinjiangNormalUniversity,Urumqi830o4,Xinjiang,China;.ResearchCenter forUrbanizationDevelopmentofSilkRoadEconomic Belt,Xinjiang NormalUniversityUrumqi83Oo54,Xinjiang,China)

Abstract: In this paper,taking Urumqi City in northwest China as an example,the spatial land cover/land use (LUCC) characteristics of Urumqi from 2000 to 2020 were analyzed on the basis of the thematic mapper (TM) and oil remote sensing image data from three phases of Landsat in 200o,2010,and 2020.This wasachieved using the random forest classification method based on a $2 5 0 ~ \mathrm { m } \times 2 5 0 ~ \mathrm { m }$ grid cell. The underlying factors were further revealed using a geographic detector model, and a quantitative analysis and an evaluation of Urumqi City from 2000 to 2020 were carred out to determine the spatial and temporal changes and response factors of LUCC over the past 2O years.The results demonstrated the following: (1) Over the past 20 years,Urumqi has been rapidly urbanized,and the land area dedicated to construction has greatly increased. On the basis of the built-up area in2Ooo,Urumqi has been developing to the north,northeast,northwest,and southeast,mainly in the outward expansion mode,although urban interior filing-type growth also exhibits a trend of intensive growth. (2) Over the past 2O years,the green space in Urumqi City has fluctuated to a certain extent,although there has been an increasing trend overallAt the same time,the amount ofbare land has shown a trend of continuous decrease. (3)The main influencing the temporal and spatial variation of LUCC in Urumqi City were identified using a geographical detector,and the results revealed that the dominant factor with the highest contribution rate was normalized difference vegetation index (NDVI).According to the interactive factor detection results, when NDVI and digital elevation model were used together, the two enhanced each other,and the explanatory power was the greatest.

Key words: land use; random forest algorithm; grid cell; geographical detector; Urumqi City