# 缺测站干旱流域生态输水遥感监测与农业节水效益分析

潘子豪¹，杨胜天¹，娄和震¹，于静洁²³，王忠静4，张军1  
(1.北京师范大学水科学研究院,北京100875；2.中国科学院地理科学与资源研究所中国科学院陆地水循环及  
地表过程重点实验室,北京100101；3.中国科学院大学,北京100049；4.清华大学水利系水沙科学与水利水电工程国家重点实验室，北京100084)

摘要：生态输水与农业节水是实现内陆干旱流域可持续发展的重要手段,连续水文观测资料的缺乏制约了生态输水与农业节水效益评价。为此，以中国甘肃敦煌疏勒河流域下游为例，基于遥感水文站与谷歌地球引擎进行2016—2020年月尺度的生态输水遥感监测，在此基础上结合蒸散发和土地覆盖类型等多源遥感数据评价生态输水与农业节水效益，分析两者之间在水资源方面的平衡关系。结果表明：(1)遥感水文站与谷歌地球引擎(Google Earth Engine,GEE)能够为生态输水遥感监测与农业节水效益评价提供可靠的数据支撑。（2）2017—2020年生态输水能够为下游湿地与河道平均每年提供 $2 . 5 0 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 生态用水，其中 $3 0 . 0 6 \%$ 的水量到达下游湿地， $1 8 . 4 7 \%$ 的水量被下游河道周边的植被所利用，且使下游河道周边植被面积增加 $1 1 2 . 2 5 \mathrm { k m } ^ { 2 } \circ ( 3 )$ 农业节水在保持耕地面积维持上升趋势的前提下，2017一2020年平均每年降低耕地的蒸散发量 $0 . 3 9 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ；耕地蒸散发减少量平均占生态输水量的 $1 4 . 2 2 \%$ ，农业节水有效缓解了内陆干旱流域农业用水挤占生态用水的问题。本文将为内陆干旱缺测站流域的生态输水遥感监测与农业节水效益评价提供新的思路，以期为未来的生态输水与农业节水工程的实施提供理论支撑。

关 键词：生态输水；农业节水；内陆干旱流域；遥感水文站；谷歌地球引擎

# 文章编号：

水资源对内陆干旱流域人类社会经济的发展和生态环境系统的可持续性至关重要[1]。在许多内陆干旱流域，农业用水占据了大部分的水资源，严重挤占了生态用水，导致了河流断流、植被消失、湖泊湿地萎缩等一系列生态环境问题[2]。生态输水是目前内陆干旱流域最常用的补救措施，其通过重新配置人类社会经济系统和自然系统之间水资源，有计划地向下游输送水资源，有利于流域生态环境的恢复[3]。而为了在满足社会经济发展需要的同时获得多余的水资源来进行生态输水，这就势必将促使区域内现有的用水方式发生改变，而农业又是内陆干旱流域用水最多且节水潜力最大的产业4,通过农业节水能够为生态输水提供一定的生态用水，有效缓解农业用水挤占生态用水的问题。因此，进行生态输水效益遥感监测并合理评价农业节水所产生的效益，对内陆干旱流域水资源可持续规划与管理至关重要[5]。

目前对生态输水监测与农业节水效益已经分别开展了诸多研究。对于生态输水效益，Hao等[6]根据塔里木河下游13a的监测资料，从地下水埋深和植被覆盖方面，在大时空尺度上评价了生态输水的生态效应;Liu等采用土壤调整植被指数阈值法分析了塔里木河下游1999—2010年植被覆盖的时空变化分布及其对生态输水的响应;Peng等[8以塔里木河下游胡杨林为研究对象，用陆地卫星传感器图像和IKONOS卫星图像监测了胡杨林的变化，并采用双时相变化检测和时间轨迹分析的方法探讨了生态输水对胡杨林的影响;Yang等[9]利用Choud-hury-Yang方程对塔里木河流域下游1960—2015年干流与源流的径流变化进行了定量描述，并对18次生态输水的效果进行了评价;在西北黑河流域[10-11]以及石羊河流域[12-14]也有许多学者开展了相应的研究。而对于农业节水效益，目前的诸多研究已经由传统的灌溉效益评价逐渐转向了社会、经济和生态的多效益综合评价，姚增福等[15]基于改进的AHP分析法和Delphi法，对节水农业建设产生的经济、生态和社会效益进行了分析；田浪等[基于物元可拓理论建立了灌区水资源综合效益评价的物元可拓模型；高金花等基于AHP法和熵权法对农业节水灌溉技术综合效益进行了评价；籍欢欢等8提出了基于多目标评价和基于Topsis方法的节水农业综合效益评价方法。虽然，目前关于生态输水效益或者农业节水效益的研究已经取得了很多成果，但是亟待同时评价生态输水与农业节水效益，并分析其在水资源方面的平衡关系。

河流流量是生态输水效益评价中最关键的因素之一[10]。受制于气候及恶劣的地理环境等因素，目前许多内陆干旱流域缺乏建立水文站点的条件[19],难以掌握生态输水前后河流流量的变化。国际水文科学协会明确2003—2012年开展无观测资料流域水文预测研究（Predictionof ungauged ba-sin,PUB)的计划[20],此后许多研究也在大型河流流量计算中引入卫星遥感数据并取得了一系列成果，例如 SWOT卫星[21]、GRACE卫星[22]、Landsat卫星[23]等，但由于卫星遥感数据的空间分辨率较低，且水下地形测量较为困难2，限制了卫星遥感数据在中小河流流量计算中的应用。针对上述困难，“遥感水文站"通过结合无人机低空遥感影像与卫星遥感影像来估算长时间序列河流流量，可以实现生态输水遥感监测[24-25]。遥感水文站利用无人机遥感影像结合实地测量来生成厘米级的数字河道模型[26],根据水面宽度计算过流面积、坡降和水力半径等水力学参数，然后使用曼宁公式计算河流流量[27]。目前已经于艾比湖流域和青藏高原等缺测站流域建立遥感水文站并估算长时间序列河流流量[28-29]。经野外实测数据和水文站的实测资料验证，估算流量与实测流量的相对精度和纳什效率系数均表现良好，表明遥感水文站适合用于缺测站流域的中小河流流量估算[30]

为了更加深刻和全面地评价内陆干旱缺测站流域生态输水与农业节水工程所产生的效益，并分析其内在的平衡关系，本文基于遥感水文站在河流流量估算方面以及谷歌地球引擎(GoogleEarthEn-gine,GEE)在空间数据处理方面的优势，以中国甘肃敦煌疏勒河流域下游为案例，开展以下4项研究：（1）基于遥感水文站估算长时间序列月尺度河流流量，实现疏勒河下游生态输水遥感监测，并基于GEE获取与处理疏勒河流域下游下垫面和蒸散发量数据；(2）从生态输水量与输水效率变化、植被面积变化和植被蒸散发变化量这3个方面定量化评价生态输水效益；(3）从耕地面积变化和耕地蒸散发减少量这2个方面定量化评价农业节水效益；(4)分析生态输水与农业节水在水资源方面的平衡关系。本文将为内陆干旱缺测站流域的生态输水监测，以及生态输水与农业节水效益评价提供新的思路，以期为未来的生态输水与农业节水工程的实施提供理论支撑。

# 1研究区、数据与方法

# 1.1 研究区概况

疏勒河位于中国甘肃省境内，发源于祁连山西段，由东向西干流全长 $6 7 0 \mathrm { k m }$ 。流域内降水稀少，气候干旱，多年平均气温 $6 . 9 { \sim } 8 . 8 \ \mathrm { ^ { 9 } C }$ ，年平均降水量$4 0 . 2 { \sim } 5 7 . 5 ~ \mathrm { m m }$ ,年平均蒸发量 $2 5 7 7 . 4 { \sim } 2 6 5 3 . 3 \ \mathrm { m m } ^ { [ 3 1 ] }$ 。西湖湿地位于疏勒河末端，总面积 $6 6 0 0 { \mathrm { k m } } ^ { 2 }$ ,有利于维持敦煌市及河西走廊西段的生态稳定。双塔水库位于疏勒河干流上，设计总库容 $2 . 4 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,双塔水库以下至西湖湿地即为疏勒河下游段(图1)。由于疏勒河流域水资源短缺，在下游河道以及西湖湿

![](images/daa56430806e1d192a654e6159ec8b56ab2b4c14da6c6cf61b58b812b8d0d88a.jpg)  
图1疏勒河流域下游概况图  
Fig.1Sketch map of the lower reaches of Shule River Basin

# 干吴区地理

地出现了河流断流和植被消失等环境问题。随着2011年《敦煌水资源合理利用与生态保护综合规划》的提出，双塔灌区 $3 0 9 . 5 3 \mathrm { ~ k m } ^ { 2 }$ 耕地进行了农业节水改造，疏勒河下游 $8 2 . 9 4 ~ \mathrm { k m }$ 古河道进行了整治与归束。2017年8月，双塔水库开始向下游西湖湿地输送大量生态用水[32]。目前,疏勒河下游的水位站于2017年8月之后建成，且位于河道整治与归束工程完成后才形成的2号断面处，所以现有水文站点难以监测生态输水前后河流流量的变化。

# 1.2数据来源与处理

1.2.1低空遥感与野外实测数据以大疆MavicAir2无人机为低空遥感数据获取平台，配合Pix4D软件规划飞行任务，于2020年10月12—13日对疏勒河流域下游3个遥感水文站断面(图1)周围地形进行扫描，并分别采用电波流速仪与声呐测量各断面处的流速与水深(表1)。其中，1号断面位于敦煌市西湖乡的柳敦公路桥处，断面下游的疏勒河古河道于2017年8月完成了河道整治与归束工程，1号断面流量变化将反映生态输水量的变化；2号断面位于疏勒河与党河交汇处附近的南梁断面处，在河道整治与归束工程完成后设有水位站，其实测流量数据将应用于遥感水文站的精度评价；3号断面位于西湖湿地内的疏勒河大桥处，其流量将反映生态输水前后到达西湖湿地的水量

1.2.2GEE卫星遥感数据归一化差分水体指数（Normalizeddifferencewaterindex,NDWI）、土地覆盖类型以及蒸散发数据均由GEE获取与处理（表

2)。各遥感数据的时间跨度选取、处理方式以及研究边界选取如下：

（1）NDWI:由于GEE中缺少NDWI产品，因此将GEE中2016—2020年Sentinel-2地表反射率数据以均值算法融合成月尺度数据后，根据式(12)计算成月尺度NDWI数据，从而为遥感水文站提供各月的水体面积。

$$
\mathrm { N D W I } { = ( \rho _ { _ \mathrm { G R E E N } } - \rho _ { _ \mathrm { N I R } } ) / ( \rho _ { _ \mathrm { G R E E N } } + \rho _ { _ \mathrm { N I R } } ) }
$$

式中： $\rho _ { \mathrm { G R E E N } }$ 和 $\rho _ { \mathrm { { N I R } } }$ 分别为遥感影像中绿光波段和近红外波段的反射率值，

(2）土地覆盖类型：由于2010年时生态输水与农业节水均未实施，因此由GEE获取的2010—2019年MODIS土地覆盖类型产品能够满足研究需要。其中，所缺少的2020年的土地覆盖类型数据则默认与2019年的相同。

（3）蒸散发：由GEE获取2010—2020年MODIS地面净蒸散发产品并以均值算法融合成年尺度蒸散发数据。但是MODIS的蒸散发值在干旱区耕地通常都会偏小，2017年疏勒河上游昌马灌区的实测蒸散发约为 $7 5 0 ~ \mathrm { m m } ^ { [ 3 1 ] }$ ,而MODIS蒸散发产品中双塔灌区的年平均实测蒸散发量仅 $2 0 7 . 5 ~ \mathrm { m m }$ ，因此本文将MODIS蒸散发产品统一乘以3.6以实现系统误差校正。

至于研究边界，由于党河水库不承担生态输水任务，基于GEE获取与处理卫星遥感数据时，将选取受生态输水与农业节水的主要影响区域(包括双塔灌区、疏勒河干流河道周边和西湖湿地)作为研究边界来评价生态输水与农业节水效益(图1)。

表1低空遥感与野外实地测量数据  
Tab.1 Low altitude remote sensing and field measurement data   
表2GEE卫星遥感数据  

<html><body><table><tr><td rowspan="2">断面名称</td><td rowspan="2">经纬度</td><td colspan="3">低空遥感</td><td colspan="2">野外实地测量</td></tr><tr><td>飞行高度/m</td><td>影像数量/张</td><td>覆盖面积/m</td><td>流速/m·s-1</td><td>水深/m</td></tr><tr><td>1号断面</td><td>94°58'16"E,40°31'01"N</td><td>120</td><td>218</td><td>190577</td><td>2.0</td><td>0.5</td></tr><tr><td>2号断面</td><td>94°32'13"E,40°30'00"N</td><td>120</td><td>307</td><td>179793</td><td>0.8</td><td>0.7</td></tr><tr><td>3号断面</td><td>93°41'13"E,40°24'25"N</td><td>120</td><td>320</td><td>191816</td><td>0.5</td><td>0.5</td></tr></table></body></html>

Tab.2 GEE satellite remote sensing data   

<html><body><table><tr><td>数据集名称</td><td>GEE地址</td><td>波段</td><td>空间分辨率/m</td><td>时间分辨率</td><td>年份</td></tr><tr><td>Sentinel-2地表反射率</td><td>COPERNICUS/S2_SR</td><td>NIR, GREEN</td><td>10</td><td>5d</td><td>2016—2020</td></tr><tr><td>MODIS土地覆盖类型</td><td>MODIS/006/MCD12Q1</td><td>LC_TYPE1</td><td>500</td><td>1a</td><td>2010—2019</td></tr><tr><td>MODIS地面净蒸散发量</td><td>MODIS/006/MOD16A2</td><td>ET</td><td>500</td><td>8d</td><td>2010—2020</td></tr></table></body></html>

注:NIR为近红外光波段;GREEN为绿光波段;LC_TYPE1为国际地圈-生物圈计划(International geosphere-biosphere programme,IGBP)的年度土地覆盖类型分类;ET为实测蒸散发波段。

# 1.3研究方法

研究步骤如下：（1）获取无人机低空遥感数据与野外实测数据，并基于GEE获取NDWI、土地覆盖类型和蒸散发量数据。（2）利用遥感水文站估算长时间序列月尺度河流流量。(3）基于土地覆盖类型和蒸散发量数据，从生态输水量与输水效率变化、植被面积变化和植被蒸散发变化量这3个方面定量化评价生态输水效益。(4）基于土地覆盖类型和蒸散发量数据，从耕地面积变化和耕地蒸散发减少量这2个方面定量化评价农业节水效益。（5）分析生态输水与农业节水在水资源方面的平衡关系(图2)。

1.3.1遥感水文站建立遥感水文站主要包括以下  
4个步骤：数字河道模型构建、河流流量估算、长时

数据无人机低空 归一化差分水 土地覆盖类型 蒸散发遥感数据与 体指数NDWI (MODIS, (MODIS,  
野外实测数据 (Sentinel-2,10 m) 500 m) 500 m)√ √  
(1)遥感水文站 (2)生态输水效益评价 (3)农业节水效益评价数字河道模型 生态输水量与+ 输水效率变化耕地面积变化  
单次河流流量估算√ 植被面积变化长时间序列 耕地蒸散发河流流量估算减少量√ 植被蒸散发变化量  
河流流量精度评价生态输水与农业节水平衡关系分析

间序列河流流量估算和河流流量精度评价。所需获取的主要数据见表3。

表3遥感水文站主要数据  
Tab.3 Main data of remote sensing hydrological station   

<html><body><table><tr><td>数据名称</td><td>获取方式</td></tr><tr><td>坡降 (J)</td><td>由无人机影像测量</td></tr><tr><td>糙率(n)</td><td>根据河道情况查表获取</td></tr><tr><td>水面宽度(W)/m</td><td>由无人机影像测量或卫星遥感NDWI反演</td></tr><tr><td>水深(D)/m</td><td>由水面宽度和数字河道模型获得</td></tr><tr><td>水位(WL)/m</td><td>由水面宽度和数字河道模型获得</td></tr><tr><td>过流面积(A)/m</td><td>由水面宽度和数字河道模型获得</td></tr><tr><td>湿周长(L)/m</td><td>由水面宽度和数字河道模型获得</td></tr><tr><td>水力半径(R)/m</td><td>由过流面积除以湿周长获得</td></tr><tr><td>流速(V)/m·s-1</td><td>根据曼宁公式计算</td></tr><tr><td>流量(Q)/m·s-1</td><td>由流速与过流面积相乘获得</td></tr></table></body></html>

注：NDWI为归一化差分水体指数。

# (1）数字河道模型构建

将天然河道进行数字化处理可以准确地提取河道的地形信息。利用无人机获取河道周边地形的低空遥感数据，使用Pix4D软件生成数字表面模型与数字正射影像，结合野外实地测量的流速与水深数据，最终生成数字河道模型(图3)。然后，利用无人机影像结合实地测量结果确定坡降和糙率，并测量得到当日水面宽度。

# （2）长时间序列水面宽度计算

发挥卫星遥感历史数据可回访以及NDWI在识别水体上的优势，利用卫星遥感历史数据与亚像元分解法即可计算长时间序列水面宽度数据。具体为根据Sentinel-2月尺度NDWI数据提取一定长度河段内各月水面面积，使用水面面积与河段长的比

![](images/16eba7e7e63a7d0c117d8b1f76c79f46c30bc03bfd7626909c6bb934cf8de2ce.jpg)  
图2技术路线  
Fig.2 Technology route   
图32号断面数字河道模型构建   
Fig.3 Construction of digital channel model for section 2

# 干辛区地理

值得到的各月平均水面宽度。计算公式如下：

$$
W { = } A _ { \mathrm { { w a t e r } } } / L _ { \mathrm { { w a t e r } } }
$$

式中： $W$ 为平均水面宽度 $\mathrm { ( m ) }$ ； $A _ { \mathrm { { w a t e r } } }$ 为河段水面面积 $\left( \mathbf { m } ^ { 2 } \right)$ ; $L _ { \mathrm { w a t e r } }$ 为河段长度 $\left( \mathrm { m } \right)$ ○

（3）长时间序列河流流量估算

由于选取断面处河道的地形一般变化不大，所以河道流量与河宽存在着一一对应的关系。首先，根据所得到的长时间序列水面宽度，利用数字河道模型计算水面宽度所对应的水深、水位、过流面积、湿周长和水力半径，然后依据曼宁公式计算流速和流量。计算公式如下：

$$
V { = } \frac { k } { n } \times R ^ { 2 / 3 } \times J ^ { 1 / 2 }
$$

$$
R = A / L
$$

$$
Q = V \times A = \frac { k } { n } \times A ^ { 5 / 3 } \times J ^ { 1 / 2 } \div L ^ { 2 / 3 }
$$

式中： $V$ 为流速 $( \boldsymbol { \mathrm { m } } \cdot \boldsymbol { \mathrm { s } } ^ { - 1 } ) : k$ 为转换常数， $k { = } 1 ; n$ 为糙率，使用时可查表选用； $R$ 为水力半径 $\mathbf { \Pi } ( \mathbf { \Pi } _ { \mathrm { m } } ) : J$ 为坡降； $A$ 为过流面积 $\left( \mathrm { m } ^ { 2 } \right) ; L$ 为湿周长，指流体与河道断面接触的周长 $\mathrm { ( m ) }$ ； $Q$ 为流量 $\left( \mathbf { m } ^ { 3 } { \cdot } \mathbf { s } ^ { - 1 } \right)$ 0

# （4）河流流量精度评价

选用纳什效率系数(Nash-Sutcliffe efficiency co-efficient,NSE)和均方根误差(Root mean square er-ror，RMSE)来评价遥感水文站的河流流量估算精度。NSE是用来评价流量估算的优劣，其取值为负无穷至1，越接近1表明结果越好;RMSE是用来衡量流量估算值同实测流量之间的偏差。计算公式如下：

$$
\mathrm { N S E } = 1 - \frac { \displaystyle \sum _ { t = 1 } ^ { T } ( Q _ { \mathrm { m } } ^ { t } - Q _ { \mathrm { c } } ^ { t } ) ^ { 2 } } { \displaystyle \sum _ { t = 1 } ^ { T } ( Q _ { \mathrm { m } } ^ { t } - \overline { { Q _ { \mathrm { m } } } } ) ^ { 2 } }
$$

$$
\mathrm { R M S E } = \sqrt { \frac { \displaystyle \sum _ { t = 1 } ^ { T } ( Q _ { \mathrm { m } } ^ { t } - Q _ { \mathrm { c } } ^ { t } ) ^ { 2 } } { T } }
$$

式中： $T$ 为总时段数; $Q _ { \mathrm { m } } ^ { t }$ 为 $\mathbf { \Phi } _ { t }$ 时段的实测流量 $\left( \mathbf { m } ^ { 3 } { \cdot } \mathbf { s } ^ { - 1 } \right)$ $Q _ { \mathrm { { c } } } ^ { t }$ 为 $\mathbf { \Phi } _ { t }$ 时段的估算流量值 $\left( \mathbf { m } ^ { 3 } { \cdot } \mathbf { s } ^ { - 1 } \right)$ ; $\overline { { Q _ { \mathrm { m } } } }$ 为 $T$ 时段内实测流量的平均值 $\left( \mathbf { m } ^ { 3 } { \cdot } \mathbf { s } ^ { - 1 } \right)$ 。

1.3.2生态输水效益评价从3个方面对生态输水效益进行评价：生态输水量与输水效率变化、植被面积变化和植被蒸散发变化量。其中，生态输水量指每年进入下游河道的总水量，输水效率指每年到达西湖湿地的总水量与生态输水量的比值，公式见式(7)\~(9)；植被面积变化是生态输水所引起的下垫面变化，主要通过分析土地覆盖类型产品来进行分析;植被的蒸散发变化量可以反映植被的生长发育情况，采用该年的植被面积减去基准年（序列数据中的第一年)的植被面积得到植被面积的变化量后，再乘以该年的单位面积植被MODIS蒸散发量，就可以依次得出各年植被蒸散发变化量，公式见式(10)。计算公式如下：

$$
\mathrm { E W } _ { 1 } = \sum _ { t = 1 } ^ { 1 2 } Q _ { 1 } ^ { t } \times 3 6 0 0 \times 2 4 \times 3 0
$$

$$
\mathrm { E W } _ { 3 } = \sum _ { t = 1 } ^ { 1 2 } Q _ { 3 } ^ { t } \times 3 6 0 0 \times 2 4 \times 3 0
$$

$$
\sigma = \mathrm { E W } _ { 3 } / \mathrm { E W } _ { 1 } \times 1 0 0 \%
$$

$$
\mathrm { E } _ { - } \mathrm { C } _ { \mathrm { v e g } } ^ { y } = \left( A _ { \mathrm { v e g } } ^ { y } - A _ { \mathrm { v e g } } ^ { s } \right) \times E _ { \mathrm { v e g } } ^ { y } \times 1 0 0 0
$$

式中： $\mathrm { E W } _ { 1 }$ 为生态输水量，即某年到达1号断面的总水量 $\left( \mathbf { m } ^ { 3 } \right)$ ； $\mathrm { E W } _ { 3 }$ 为到达西湖湿地的总水量，即某年到达3号断面的总水量 $\left( \mathbf { m } ^ { 3 } \right)$ ； $Q _ { 1 } ^ { t }$ 和 $Q _ { 3 } ^ { t }$ 分别为 $\mathbf { \Phi } _ { t }$ 月1号断面和3号断面的月平均流量 $\left( \mathbf { m } ^ { 3 } { \cdot } \mathbf { s } ^ { - 1 } \right)$ ; $\sigma$ 为输水效率 $( \% ) : { \mathrm { E } } _ { - } { \mathrm { C } } _ { \mathrm { v e g } } ^ { \gamma }$ 为第 $y$ 年的植被蒸散发变化量$( \mathbf { m } ^ { 3 } )$ ； $A _ { \mathrm { v e g } } ^ { y }$ 与 $A _ { \mathrm { v e g } } ^ { s }$ 分别为第 $y$ 年和基准年的植被面积 $\left( \mathrm { k m } ^ { 2 } \right)$ ; $\boldsymbol { E } _ { \mathrm { v e g } } ^ { y }$ 为第 $y$ 年的单位面积植被年平均蒸散发量 $( \mathrm { m m }$ ）。

1.3.3农业节水效益评价从以下2个方面对农业节水效益进行评价：耕地面积变化和耕地蒸散发减少量。其中，（1）耕地面积变化可以反映生态输水是否阻碍了农业的发展，主要通过分析土地覆盖类型数据来进行评价；（2）耕地蒸散发减少量可以定量化反映农业节水的效益，以双塔灌区以外无农业节水耕地的MODIS蒸散发为基准，参考水文中同倍比放大法估计双塔灌区耕地无农业节水情景下蒸散发量，然后用其减去双塔灌区耕地MODIS蒸散发量，即可得到农业节水引起的双塔灌区耕地蒸散发减少量。计算公式如下：

$$
\mathrm { E } \_ \mathrm { C } _ { \mathrm { c u l } } ^ { y } = \mathrm { E } \_ { \mathrm { e s t } _ { \mathrm { c u l } } ^ { y } } - E _ { \mathrm { c u l } } ^ { y }
$$

$$
\mathrm { E { \_ } e s t } _ { \mathrm { c u l } } ^ { y } = \frac { { E _ { \mathrm { c u l } } ^ { y } } ^ { \prime } \times { E _ { \mathrm { c u l } } ^ { s } } } { E _ { \mathrm { c u l } } ^ { s } }
$$

式中： $\mathrm { E } _ { - } \mathrm { C } _ { \mathrm { c u l } } ^ { y }$ 为第 $y$ 年双塔灌区耕地的蒸散发减少量 $( \mathbf { m } ^ { 3 } ) ; \mathrm { E \_ e s t } _ { \mathrm { c u l } } ^ { \gamma }$ 为第 $y$ 年无农业节水情景下双塔灌区耕地的估计蒸散发量 $\left( \mathbf { m } ^ { 3 } \right)$ ; $\boldsymbol { E } _ { \mathrm { c u l } } ^ { y }$ 和 $E _ { \mathrm { c u l } } ^ { s }$ 分别为第 $y$ 年和基准年的双塔灌区耕地MODIS蒸散发量 $\left( \mathbf { m } ^ { 3 } \right)$

$E _ { \mathrm { c u l } } ^ { y } { } ^ { \prime }$ 和 $E _ { \mathrm { c u l } } ^ { s } { } ^ { \prime }$ 分别为第 $y$ 年和基准年无农业节水耕地的MODIS蒸散发量 $\left( \mathbf { m } ^ { 3 } \right)$ 0

# 2结果与分析

# 2.1遥感水文站精度评价

于2号断面处建立遥感水文站及数字河道模型，计算2号断面2020年1—10月的水面宽度，并估算河流流量。与2号断面水位站实测流量进行比较，并根据式(5)与式(6)评价估算精度(表4、图4)。其中1月和2月属于结冰期，故不进行计算而直接将流量设为0。

由图中4可知,2号断面估算结果与实测结果在大多数月份误差较小，NSE为0.57，RMSE为3.91$\mathbf { m } ^ { 3 } \cdot \mathbf { s } ^ { - 1 }$ 。其中,最明显的误差来源于2020年3月遥感水文站估算流量出现了一个峰值，这是因为随着2017年8月河道整治与归束工程的完成，生态用水能够顺着河道被输送至西湖湿地内，所以从2018年开始每年的3月都将会因为河流解冻而出现流量的大量增加。因此，在不考虑2020年3月的误差的情况下,NSE将提升至0.94,RMSE将降低至 $1 . 4 9 \mathrm { m } ^ { 3 } { \cdot } \mathrm { s } ^ { - 1 }$ ,这说明遥感水文站的流量估算结果可靠，适合应用于缺测站流域的河流流量监测。

表42号断面遥感水文站结果  
Tab.4 Results of remote sensing hydrological station of section 2   

<html><body><table><tr><td>日期 (年-月)</td><td>遥感反演 河宽/m</td><td>水深/m</td><td>过流面积 /m²</td><td>流速 /m·s-1</td></tr><tr><td>2020-01</td><td>一</td><td>1</td><td>1</td><td>1</td></tr><tr><td>2020-02</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>2020-03</td><td>36.2</td><td>0.66</td><td>21.79</td><td>0.80</td></tr><tr><td>2020-04</td><td>35.4</td><td>0.54</td><td>17.62</td><td>0.70</td></tr><tr><td>2020-05</td><td>35.7</td><td>0.59</td><td>19.16</td><td>0.74</td></tr><tr><td>2020-06</td><td>35.7</td><td>0.59</td><td>19.16</td><td>0.74</td></tr><tr><td>2020-07</td><td>33.0</td><td>0.28</td><td>8.51</td><td>0.45</td></tr><tr><td>2020-08</td><td>33.5</td><td>0.32</td><td>10.02</td><td>0.50</td></tr><tr><td>2020-09</td><td>35.8</td><td>0.61</td><td>19.79</td><td>0.75</td></tr><tr><td>2020-10</td><td>36.5</td><td>0.71</td><td>23.56</td><td>0.83</td></tr></table></body></html>

注：“-"表示无数据。下同。

![](images/674d93d5c2f41d4364ca587f461aa59d325ce209c2dfc69e82c0dcd5e75b294a.jpg)  
图42号断面估算流量与实测流量  
Fig.4Estimated discharge and measured discharge of section 2

# 2.2生态输水效益评价

2.2.1生态输水量与输水效率变化首先，基于GEE获取的2016—2020年Sentinel-2月尺度NDWI数据，采用遥感水文站计算1号与3号断面2016—2020年月尺度的河流流量(图5)，并依据式(7)和式(8)计算生态输水量与输水效率(图5)。由图5可知，1号与3号断面的流量在2016—2020年内整体均呈现明显上升趋势( $_ { \scriptstyle P < 0 . 0 5 } )$ ),其平均增长速率分别为每月 $0 . 0 9 9 { \mathrm { ~ m } } ^ { 3 }$ 和 $0 . 0 4 9 \mathrm { m } ^ { 3 }$ 。其中，由于2016年1月一2017年7月下游河道整治与归束工程尚未完成，1号断面之后的疏勒河古河道宽浅散乱，所以双塔水库并未下泄大量生态用水，到达1号断面的水量总计共 $1 . 3 7 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，且均在疏勒河下游古河道中经由蒸发与下渗损耗殆尽，导致最终到达3号断面的水量为0，输水效率也为0。随着2017年8月河道整治与归束工程的完成，双塔水库大幅增加了生态输水量，2017—2020年到达1号断面的水量增加至平均每年 $2 . 5 0 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,并且平均每年有 $0 . 7 5 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 的生态用水到达了3号断面，平均输水效率增长至$3 0 . 0 6 \%$ 。这说明生态输水的实施大幅增加了进入下游河道中的总水量，且河道整治与归束工程的完成大幅降低了生态输水的沿线损耗，使生态用水能够顺利抵达西湖湿地。

2.2.2 植被蒸散发变化量基于土地覆盖类型产品和蒸散发产品，统计各年植被面积，并计算各年植被蒸散发变化量(图6)。由图6可知，植被面积在2010—2020年呈现明显的上升趋势（ $( P { < } 0 . 0 5 )$ ，总计增加 $1 1 2 . 2 5 \ \mathrm { k m } ^ { 2 }$ ,年平均增长率达 $1 0 . 2 1 ~ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ，且2018—2019年增幅最大，高达 $3 9 . 7 5 \mathrm { k m } ^ { 2 }$ 。植被单位面积蒸散发量呈现波动的趋势，但其年平均增长率仅为 $0 . 0 0 7 \ \mathrm { m m ^ { \cdot } a ^ { - 1 } }$ ,基本可以视为不变。因此,在植被面积增长以及单位面积蒸散发量变化不大的情况下，植被蒸散发变化量以平均 $0 . 0 5 2 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 }$ 的

(a)月尺度断面流量变化 (b)生态输水量与输水效率302520 1号断面 5030323 0 010203027.00 30.36su/雪 15 WW AA 2.46 2.52 2.68 2.33 4050 %/舞10 605 A 1.02 0.66 0.76 0.89 0.68 7080 0.5 0 900的汉力 2016 2017 2018 2019 2020% 年份日期(年-月)

![](images/da2460a367a192d304df230eee1ced934e4b2925cb1a16e496851e773bb91610.jpg)  
Fig.5Quantity of ecological water conveyance and water conveyance efficiency   
图6植被蒸散发量  
Fig.6 Evapotranspiration of vegetation

![](images/e976ce17a86e1e3adcafd27875f6a41ba6332cd767b20ab3e4fc159bde5d5d2d.jpg)  
图5生态输水量与输水效率  
图7耕地面积与蒸散发量  
Fig.7 Area and evapotranspiration ofcultivated land

速率呈现明显的增长趋势 $( P { < } 0 . 0 5 )$ 。其中，2019年和2020年植被面积快速增长，植被蒸散发变化量出现大幅增长，这主要是与2017年8月之后生态输水量的加大以及植被生长对生态输水的滞后性相关。

# 2.3农业节水效益评价

以远离双塔灌区的一处耕地作为无农业节水耕地(图1)，基于土地覆盖类型与蒸散发数据，估算无农业节水情景下双塔灌区耕地的蒸散发量，并计算各年耕地蒸散发减少量(图7)。由图7可知，在2010一2020年耕地面积呈现波动上升趋势，年增长率为 $2 . 8 9 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ,且在2013年和2018年均达到了较高水平，分别为 $3 3 3 . 7 5 \mathrm { k m } ^ { 2 }$ 和 $3 4 0 . 5 0 \mathrm { k m } ^ { 2 }$ 。整体来看，2010一2020年无农业节水时耕地估计年累积蒸散发量的上升趋势比实测耕地蒸散发量的上升趋势更明显，年平均增长率分别为 $0 . 0 6 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } \cdot \mathrm { a } ^ { - 1 }$ 和$0 . 0 1 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 } { \cdot } \mathrm { a } ^ { - 1 }$ 。其中,2010—2014年耕地估计与实测蒸散发量相差不大，到2014年时基本相同。但从2015年开始，耕地的实测蒸散发量持续低于估计蒸散发量。其中2015年和2016年耕地蒸散发减少量较高，分别达到了 $0 . 6 3 5 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 和 $0 . 7 1 2 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 。而2017一2020年的耕地蒸散发减少量相对有所下降但趋于稳定，平均每年为 $0 . 3 9 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,占耕地估计蒸散发量的 $1 3 . 1 6 \%$ 。这说明农业节水可以在保持耕地面积维持上升趋势的前提下，有效地降低耕地的蒸散发量，提高耕地的灌溉效率。

# 3讨论

# 3.1生态输水与农业节水的平衡关系

综合生态输水量与输水效率变化、植被蒸散发变化量以及耕地蒸散发减少量的结果分析生态输水与农业节水在水资源方面的平衡关系(表5)。由表5可知，2015—2016年就已经开始农业节水且耕地蒸散发减少量较大，但由于此时河道整治与归束工程还未完成，双塔水库还未开始大量下泄生态用水；2017一2020年，双塔水库通过整治与归束后的河道进行输水，生态输水量达到了平均每年 $2 . 5 0 \times$ $1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,耕地蒸散发减少量平均每年为 $0 . 3 9 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 占生态输水量的 $1 4 . 2 2 \%$ 。这说明双塔灌区的农业节水还是能够在一定程度上缓解农业用水挤占生态用水的现象，但由于灌区面积以及节水技术的限制，双塔灌区的农业节水所能提供的生态用水终究还是比较有限，剩余的生态输水量还是需要靠水库生态调水来提供

表5生态输水与农业节水平衡关系  
Tab.5Balance relationship between ecological water conveyance and agricultural water-saving   

<html><body><table><tr><td rowspan="2">年份</td><td rowspan="2">1号断面水量/10m</td><td colspan="2">耕地蒸散发减少量</td><td colspan="2">植被蒸散发变化量</td></tr><tr><td>数值/10m</td><td>百分比/%</td><td>数值/10m</td><td>百分比/%</td></tr><tr><td>2010</td><td>1</td><td>0.00</td><td>一</td><td>1</td><td>1</td></tr><tr><td>2011</td><td>一</td><td>0.06</td><td>1</td><td>0.08</td><td>一</td></tr><tr><td>2012</td><td>一</td><td>-0.13</td><td>一</td><td>0.18</td><td>一</td></tr><tr><td>2013</td><td>一</td><td>0.28</td><td>一</td><td>0.20</td><td>一</td></tr><tr><td>2014</td><td>1</td><td>0.00</td><td>一</td><td>0.24</td><td>1</td></tr><tr><td>2015</td><td>1</td><td>0.63</td><td>1</td><td>0.30</td><td>1</td></tr><tr><td>2016</td><td>1.02</td><td>0.71</td><td>69.49</td><td>0.32</td><td>31.43</td></tr><tr><td>2017</td><td>2.46</td><td>0.38</td><td>15.31</td><td>0.35</td><td>14.26</td></tr><tr><td>2018</td><td>2.52</td><td>0.48</td><td>19.05</td><td>0.31</td><td>12.48</td></tr><tr><td>2019</td><td>2.68</td><td>0.37</td><td>13.90</td><td>0.59</td><td>21.87</td></tr><tr><td>2020</td><td>2.33</td><td>0.35</td><td>15.09</td><td>0.59</td><td>25.26</td></tr></table></body></html>

注："百分比"表示各项蒸散发量数值占1号断面水量的百分比。

由表5还可知,2017—2020年植被蒸散发变化量平均为 $0 . 4 6 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ ，平均占生态输水量的$1 8 . 4 7 \%$ 。由于植被生长对于生态输水具有一定的滞后性[13],2017—2018年植被蒸散发变化量较少，仅占生态输水量的 $1 4 . 2 6 \%$ 和 $1 2 . 4 8 \%$ 。而2019年开始有大量新的植被出现于双塔灌区以及河道周边的低洼处，导致2019年和2020年该百分比也增长为平均 $2 3 . 5 7 \%$ 。这说明随着生态输水的不断进行，下游生态环境逐渐恢复，更多的水资源将会被植被所利用，提高了流域的水源涵养能力，这与目前研究中提出的疏勒河下游植被恢复的结论相符合[33-34]

此外，本文所研究的生态输水与农业节水之间的平衡关系主要还是侧重于水资源方面，即重点回答了生态输水量和农业节水量有多少的问题，对两者之间的关联性研究还很不足。在将来的研究中，应综合考虑两者在生态效益与社会经济效益之间的平衡[35],从社会水文学的角度来研究驱动生态输水与农业节水发展的内因，提供能够指导流域生态输水与农业节水的临界阈值，以期更好地为未来的生态输水与农业节水工程的实施提供理论支撑。

# 3.2生态输水量与农业节水量可靠性分析

王合创等3的研究中指出，2016—2018年双塔水库平均下泄生态用水 $2 . 3 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，其中2018年到达1号断面附近的水量为 $0 . 8 8 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 。而本文结果中2018年到达1号断面的水量高达 $2 . 5 2 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 。出现这种现象是因为，流域内的降雨、灌溉回水以及地下水渗出都将会增加河流流量，各水文要素之间的具体关系需要在后续研究中引入水文模型来进行准确模拟。此外，2010一2020年研究区内耕地和植被的年平均蒸散发量分别为 $7 7 1 . 7 1 \ \mathrm { m m }$ 和492.41$\mathbf { m } \mathbf { m }$ ，折合为亩定额的话为每亩 $5 1 4 . 0 0 \mathrm { m } ^ { 3 }$ 和328.27$\mathbf { m } ^ { 3 }$ ,要略小于金荣3研究中双塔灌区耕地的灌溉用水每亩 $7 5 3 . 4 8 \mathrm { ~ m } ^ { 3 }$ 。同时，张彦武[37的研究表明，通过对双塔灌区的农业节水改造，双塔灌区节水 $0 . 6 8 \times$ $1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 。而本文结果中的2017—2020年双塔灌区的耕地蒸散发减少量平均为 $0 . 3 9 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,为现有研究结果的 $5 8 . 0 8 \%$ 。而出现这种现象是因为耕地蒸散发减少量的多少能从一定程度上反映农业节水效果的变化趋势，但其还受灌溉用水损耗、气候等因素的影响，所以小于实际的灌区节水量。

# 3.3研究不确定性分析

本文关于生态输水量与输水效率变化的研究

# 干旱区地理

时间跨度为2016一2020年，与其余相似研究相比较短，这主要是由于疏勒河流域2017年8月才开始向西湖湿地进行生态输水，所以在此之前下游河道均无流量。但在这5a中，2016年1月一2017年7月的河流流量代表通过渠道进行生态输水前的情况，2017年8月一2020年12月的河流流量代表通过渠道进行生态输水后的情况，如此进行对比分析将能反映生态输水的影响。

本文对于缺测站内陆干旱流域的生态输水与农业节水效益评价以及其平衡关系分析是基于年尺度来进行的，这样将更有利于从整体上把握生态输水量和农业节水量的变化趋势。主要原因如下，疏勒河双塔灌区每年的灌溉期为3月5日一4月30日、6月5日—8月25日、10月15日—11月20日，总灌溉期约170d,基本跨越了一年内除结冰期(12、1月和2月)以外的其余时间[38]

本文没有考虑降雨量的年际变化对于生态输水与农业节水效益评价以及平衡关系分析的影响。为了更好地解释其原因，本文基于GEE获取了2001—2020年ERA5月平均栅格降雨数据，流域的年降雨量整体呈上升的趋势，但平均降雨量仍然要小于 $1 0 0 \mathrm { m m }$ ,要远远小于其年平均潜在蒸发量。同时，孙栋元等[39阐明了1956—2016年疏勒河干流的昌马堡站、潘家庄站和双塔堡水库站的多年平均径流量分别为 $9 . 9 1 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } . 2 . 7 9 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 和 $3 . 1 1 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，年均径流量分别以 $1 . 0 7 5 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 } \cdot 0 . 1 2 6 \times 1 0 ^ { 8 }$ $\mathrm { { m } ^ { 3 } \cdot ( 1 0 a ) ^ { - 1 } }$ 和 $0 . 2 5 3 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 速率增加，且在2010年之后也均处于特丰水年。降雨的增加虽然会使流域的来水增加，但这不是使疏勒河下游产生径流的主要因素，生态输水量的多少才会显著影响疏勒河下游流量的多少。此外，2010一2020年研究区内耕地和植被的年平均蒸散发量分别为771.71$\mathbf { m } \mathbf { m }$ 和 $4 9 2 . 4 1 ~ \mathrm { { m m } }$ ,也均远远大于年降雨量。这说明降雨也不是农作物和植被生长的主要水资源来源，灌区内农业发展的方式还是人工引水灌溉，植被也主要是分布河流周边以及低洼的地下水渗出处。

此外，休耕地以及稀疏草地的面积将会对本文中耕地以及植被蒸散发量计算产生一定的影响。由于关于耕地是否为休耕地的相关数据难以直接获取，且难以获取更高分辨率卫星遥感产品来进行稀疏草地的辨别，目前恐怕还没有办法考虑上述这2个问题。不过在将来的研究中，如果能结合更高分辨率的遥感影像，可以通过对不同耕地在年内的蒸散发分布的差异来进行休耕地的判断，并且可以利用重采样方法来提取未被土地利用产品所识别出来的稀疏草地。

# 4结论

本文以中国甘肃敦煌疏勒河流域下游为例，基于遥感水文站与GEE进行2016—2020年月尺度的生态输水遥感监测,并在此基础上结合蒸散发和土地覆盖类型等多源遥感数据评价生态输水与农业节水效益，并分析两者之间在水资源方面的平衡关系。主要结论如下：

（1）遥感水文站与GEE能够为缺测站内陆干旱流域的生态输水遥感监测与农业节水效益评价提供数据支撑。遥感水文站充分发挥了无人机低空遥感高精度以及卫星遥感历史信息回访的优势，估算缺测站流域长时间序列河流流量，实现了长时间序列生态输水遥感监测，且验证结果表明遥感水文站的流量估算结果表现良好。

(2）在河道整治与归束工程大幅降低生态输水的沿线损耗的前提下，生态输水能够为下游湿地以及下游河道周边提供充足的水资源，植被恢复显著。2017—2020年生态输水使进人疏勒河下游河道和湿地的水量增加至平均每年 $2 . 5 0 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,其中$3 0 . 0 6 \%$ 的水量到达下游湿地， $1 8 . 4 7 \%$ 的水量被下游河道周边的植被所利用，使得下游河道周边的植被面积增加了 $1 1 2 . 2 5 \mathrm { k m } ^ { 2 }$ O

(3）农业节水可以在保持耕地面积维持上升趋势的前提下，有效地降低耕地的蒸散发量。双塔灌区在耕地面积保持 $2 . 8 9 \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 的增长速率的前提下，通过农业节水使2017—2020年耕地蒸散发量平均每年减少 $0 . 3 9 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，占无农业节水情景下耕地估计蒸散发量的 $1 3 . 1 6 \%$ 。

(4)农业节水缓解了内陆干旱流域农业用水挤占生态用水的问题。疏勒河流域下游2017一2020年平均生态输水量 $2 . 5 0 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,平均耕地蒸散发减少量为 $0 . 3 9 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，农业节水量平均占生态输水量的 $1 4 . 2 2 \%$ 。

# 参考文献(References)

[1]Zhang Z,Hu HP,Tian FQ,et al.Groundwater dynamics under

water saving irrigation and implications for sustainable water management in an oasis: Tarim River Basin of western China[J]. Hydrology and Earth System Sciences Discussons,2014,18(10): 3951-3967.   
[2]庞爱萍,易雨君,李春晖.基于生态需水保障的农业用水安全评 价——以山东省引黄灌区为例[J].生态学报,2021,41(5): 1907-192O.[Pang Aiping,Yi Yujun,Li Chunhui. Evaluation of agricultural water-use security with ecological water demand as a priority:A case study of the Yellow River estuary in Shandong Province[J]. Acta Ecologica Sinica,2021,41(5): 1907-1920.]   
[3]Zhang Y,Zhu GF,Ma HY,etal.Effects of ecological waterconveyance on the hydrochemistry of a terminal lake in an inland river: A case study of Qingtu Lake in the Shiyang River Basin[J]. Water,2019,11(8): 1673,doi: 10.3390/w11081673.   
[4]康绍忠,许迪.我国现代农业节水高新技术发展战略的思考[J]. 中国农村水利水电,2001(10):25-29.[Kang Shaozhong, Xu Di. Reflection on high-tech development strategies for water-saving of modern agriculture in China[J]. China Rural Water and Hydropower,2001(10): 25-29.]   
[5]Huang F, Chunyu X Z, Zhang D R,et al.A framework to assess the impact of ecological water conveyance on groundwater-dependent terrestrial ecosystems in arid inland river basins[J]. Science of the Total Environment,2020,709:136155,doi: 10.1016/j.scitotenv.2019.136155.   
[6]Hao X M,Li W H. Impacts of ecological water conveyance on groundwater dynamics and vegetation recovery in the lower reaches of the Tarim River in northwest China[J].Environmental Monitoring and Assessment,2014,186(11): 7605-7616.   
[7]Liu GL, Kurban A,Duan HM,etal.Desert riparian forest colonization in the lower reaches of Tarim River based on remote sensing analysis[J].Environmental Earth Sciences,2014,71(10): 4579-4589.   
[8]Peng S H, Chen X,Qian J,et al.Spatial pattern of Populus euphratica forest change asaffected by water conveyance in the lower Tarim River[J].Forests,2014,5(1): 134-152.   
[9]Yang F,Xue L,Wei G,et al.Study on the dominant causes of streamflow alteration and effects of the current water diversion in the Tarim River Basin, China[J]. Hydrological Processes,2018,32 (22): 3391-3401.   
[10] Zhang S H, Ye Z X, Chen Y N,et al. Vegetation responses to an ecological water conveyance project in the lower reaches of the Heihe River Basin[J].Ecohydrology，2017,10(6):e1866,doi: 10.1002/eco.1866.   
[11]Shen Q,Gao G Y,Lu Y H,et al.River flow is critical for vegetation dynamics: Lessons from multi-scale analysis in a hyper-arid endorheic basin[J]. Science of the Total Environment,2017,603: 290-298.   
[12]Wang X Y,Peng S Z,Ling HB, et al. Do ecosystem service value increase and environmental quality improve due to large-scale ecological water conveyance in an arid region of China?[J]. Sustainability,2019,11(23): 6586,doi: 10.3390/su11236586.   
[13]Liao S M, Xue L Q, Dong Z C,et al. Cumulative ecohydrological response to hydrological processes in arid basins[J]. Ecological Indicators,2020,111: 106005,doi:10.1016/j.ecolind.2019.106005.   
[14] 董志玲,徐先英,金红喜,等.生态输水对石羊河尾闾湖区植被 的影响[J].干旱区资源与环境,2015,29(7):101-106.[Dong Zhiling,Xu Xianying,Jin Hongxi,et al. The impact of eco- water transportation to the vegetation in tail lake of Shiyang River[J]. Journal of Arid Land Resourcesand Environment,2O15,29(): 101-106.]   
[15] 姚增福,李全新.节水农业综合效益价值差异评估——基于甘 肃省数据研究[J].华东经济管理,2014,28(7):81-85.[Yao Zengfu,Li Quanxin.An evaluation on the value discrepancies of water-saving agriculture comprehensive benefits: Based on the data of Gansu Province[J]. East China Economic Management, 2014, 28(7): 81-85.]   
[16] 田浪,刘永强,王珍,等.基于物元可拓模型的灌区水资源综合 效益评价[J].排灌机械工程学报,2016,34(4):351-356.[Tian Lang,Liu Yongqiang,Wang Zhen,et al. Comprehensive benefit evaluation of water resources in irrigation district based on matter element extension model[J]. Journal of Drainage and Irrigation Machinery Engineering, 2016,34(4): 351-356.]   
[17] 高金花,高晓珊,廉冀宁,等.基于AHP-熵权法的农业节水技 术综合效益评价[J].农机化研究,2019,41(12):58-63.[Gao Jinhua, Gao Xiaoshan,Lian Jining,et al. Comprehensive benefit evaluation of agricultural water-saving technology based on AHP-entropy weight method[J]. Journal of Agricultural Mechanization Research, 2019,41(12): 58-63.]   
[18] 籍欢欢,胡振华,雷波,等.基于多目标评价及Topsis方法的节 水农业综合效益评价——以黑龙江和平灌区为例[J].节水灌 溉,2019(4): 41-45.[Ji Huanhuan,Hu Zhenhua,Lei Bo,et al. Comprehensive benefit evaluationof water-saving agriculturebased on multi-objective evaluationandtopsis method: Taking Heilongjiang Peace Irigation District as an example[J]. Water Saving Irrigation, 2019(4): 41-45.]   
[19]Razavi T, Coulibaly P. Streamflow prediction in ngauged basins: Review of regionalization methods[J]. Journal of Hydrologic Engineering,2013,18(8): 958-975.   
[20] Sivapalan M, Takeuchi K,Franks S W,et al. IAHS decade on predictions in ungauged basins (PUB),2003—2012: Shaping an exciting future for the hydrological sciences[J].Hydrological Sciences Journal,2003,48(6): 857-880.   
[21]Garambois PA,Monnier J. Inference of effective river properties from remotely sensed observations of water surface[J]. Advances in Water Resources,2015,79: 103-120.   
[22] Wang S S, Zhou F Q, Russell H A J. Estimating snow mass and peak river flows for the Mackenzie River Basin using GRACE satellite observations[J]. Remote Sensing,2017,9(3): 256,doi: 10.

# 干旱区地理

# 3390/rs9030256.

[23]Gleason C J, Smith L C.Toward global mapping of river discharge using satelite images and at-many-stations hydraulic geometry[J]. Proceedings of the National Academy of Sciences of the United States of America,2014,111(13): 4788-4791.   
[24] Zhao C S, Zhang C B,Yang S T,et al. Calculating e-flow using UAV and ground monitoring[J]. Journal of Hydrology,2O17,552: 351-365.   
[25] Yang S T, Wang J, Wang PF,et al. Low altitude unmanned aerial vehicles (UAVs) and satellite remote sensing are used to calculated river discharge attenuation coefficients of ungauged catchments in arid desert[J].Water,2019,11(12):2633,doi: 10.3390/w111 22633.   
[26] 张纯斌,杨胜天,赵长森,等.小型消费级无人机地形数据精度 验证[J].遥感学报,2018,22(1):185-195.[Zhang Chunbin,Yang Shengtian, Zhao Changsen,et al. Topographic data accuracy verification of small consumer UAV[J]. Journal of Remote Sensing, 2018,22(1): 185-195.]   
[27]Yang S T,WangPF,Lou H Z,et al. Estimating river discharges in ungauged catchments using the slope-area method and unmanned aerial vehicle[J].Water,2019,11(11): 2361,doi:10.3390/w1111 2361.   
[28] Lou H Z, Wang PF, Yang S T,et al. Combining and comparing an unmanned aerial vehicle and multiple remote sensing satellites to calculate long-term river discharge in an ungauged water source region on the Tibetan Plateau[J].Remote Sensing,2020,12(13): 2155,doi: 10.3390/rs12132155.   
[29]Wang PF,Yang ST,Wang J,et al.Discharge estimation with hydraulic geometry using unmanned aerial vehicle and remote sens ing[J]. Journal of Hydraulic Engineering,2020,51(4): 492-504.   
[30]Yang S T,Li C J,Lou H Z,et al. Performance of an unmanned aerial vehicle (UAV) in calculating the flood peak discharge of ephemeral rivers combined with the incipient motion of moving stones in arid ungauged regions[J]. Remote Sensing, 2020,12(10): 1610, doi: 10.3390/rs12101610.   
[31] 宁亚洲,张福平,冯起,等.基于 SEBAL模型的疏勒河流域蒸散 发估算与灌溉效率评价[J].干旱区地理,2020,43(4):928-938. [Ning Yazhou, Zhang Fuping, Feng Qi,et al. Estimation of evapotranspiration in Shule River Basin based on SEBAL model and evaluation on irrgation efficiency[J].Arid Land Geography,2020, 43(4): 928-938.]   
[32] 王合创,徐宝山,南洋,等.疏勒河流域敦煌生态输水问题研究 [J].水利规划与设计,2020,5(5):38-43.[Wang Hechuang,Xu Baoshan,Nan Yang,et al. Study on Dunhuang ecological water conveyance in Shule River Basin[J]. Water Resources Planning and Design,2020,5(5): 38-43.]   
[33] 岳东霞,陈冠光,朱敏翔,等.近20年疏勒河流域生态承载力和 生态需水研究[J].生态学报,2019,39(14):5178-5187.[Yue Dongxia,Chen Guanguang, Zhu Minxiang,et al. Biocapacity and ecological water demand in Shule River Basin over the past 20 years[J]. Acta Ecologica Sinica,2019,39(14): 5178-5187.]   
[34] 岳东霞,苗俊霞,朱敏翔,等.疏勒河流域陆地水储量与植被指 数的时空耦合关系[J].生态学报,2019,39(14):5268-5278. [Yue Dongxia, Miao Junxia,Zhu Minxiang,et al. Spatio-temporal coupling between terrestrial water storage and vegetation index in Shule River Basin[J].Acta Ecologica Sinica, 2019,39(14): 5268- 5278.]   
[35] 王希义,彭淑贞,徐海量,等.大型输水工程的生态效益与社会 经济效益评价——以塔里木河下游为例[J].地理科学,2020, 40(2): 308-314.[Wang Xiyi,Peng Shuzhen,Xu Hailiang,et al.Evaluation of ecological and social-economic benefits of large water conveyance projects:A case study on the lower reaches of the Tarim River[J]. Scientia Geographica Sinica,2020,40(2): 308-314.]   
[36]金荣.双塔灌区2019年农田灌溉水有效利用系数测算分析[J]. 地下水,2021,43(3): 104,168.[Jin Rong.Calculation and analysis of effective utilization coefficient of farmland irrigation water in Shuangta irrigation area in 2019[J]. Ground Water,2021,43(3): 104,168.]   
[37] 张彦武.疏勒河的变迁对敦煌西湖湿地的影响分析[D].北京: 清华大学,2016.[Zhang Yanwu.Analysis of the influence of the Shule River changes on West Lake wetland at the Dunhuang City [D]. Beijing: Tsinghua University,2016.]   
[38] 曾有孝,周毅.甘肃省疏勒河流域尾闾生态补水工程措施研究 [J].人民 黄河,2018,40(11): 88-91.[Zeng Youxiao,Zhou Yi. Study on measures of ecological replenishment engineering at the tail of Shule River Basin in Gansu Province[J].Yellow River, 2018,40(11): 88-91.]   
[39] 孙栋元,齐广平,马彦麟,等.疏勒河干流径流变化特征研究[J]. 干旱区地理,2020,43(3): 557-567.[Sun Dongyuan,Qi Guangping,Ma Yanlin,et al.Variation characteristics of runoff in the mainstream of Shule River[J]. Arid Land Geography,2020,43(3): 557-567.]

# Remote sensing monitoring of ecological water conveyance and benefits evaluation of agricultural water-saving in arid basin without observation station

PAN Zihao'， YANG Shengtian'， LOU Hezhen'， YU Jingjie²3, WANG Zhongjing4， ZHANG Jun' (1.CollegeofWaterScience,BeijingNormalUniversity,Beijing875,China;2.KeyLaboratoryofWaterCycleandRelated Land Surface Processes,InstituteofGeographic Sciencesand atural Resources Research,CAS,BeijingOolo,China; 3.UniversityofCineseAcademyofSiences,Beijing049,China;4.StateKeyLaboratoryofHydro-ScienceandEging, Tsinghua University,Beijing 100084, China)

Abstract: Ecological water conveyance and agricultural water-saving are known to be important means to achieve sustainable development in inland arid basins.Due to the scarcity of hydrological stations,the monitoring and benefit evaluation of ecological water conveyance and agricultural water-saving are limited.Thus,in this study, we will examine the lower reaches of the Shule River Basin in Dunhuang,Gansu Province,China.First, monthly remote sensing monitoring of ecological water conveyance from 2016 to 2020 was performed using remote sensing hydrological stations and Google Earth Engine (GEE).The benefits of ecological water conveyance and agricultural water-saving are then evaluated in conjunction with evapotranspiration and landcover types. Finally, the balance between ecological water conveyance and agricultural water-saving is analyzed in terms of water resources.The results show that (1) the remote sensing hydrological station and GEEcan provide reliable data support for remote sensing monitoring of ecological water conveyance and evaluating water-saving benefits of agriculture. (2) From 2017 to 2020, ecological water conveyance can provide an average of $2 . 5 0 \times 1 0 ^ { 8 } ~ \mathrm { m } ^ { 3 }$ ecological water per year to the downstream wetland and river, of which $3 0 . 0 6 \%$ reaches the downstream wetland and $1 8 . 4 7 \%$ is used by the vegetation around the downstream river,resulting in a significant increase in vegetation area of $1 1 2 . 2 5 \mathrm { k m } ^ { 2 }$ .(3) From 2017 to 2020,agricultural water-saving can effectively reduce the evapotranspiration of cultivated land by an average of $0 . 3 9 5 \times 1 0 ^ { 8 } \mathrm { ~ r ~ }$ n per year, assuming that arable land area continues to grow. The decrease in evapotranspiration on cultivated land accounted for $1 4 . 2 2 \%$ of the ecological water conveyance capacity,thus efectively alleviating the problem of agricultural water occupying ecological water in the inland arid basin. This study proposes a novel approach for monitoring ecological water conveyance and evaluating agricultural water-saving benefits in the inland drought lack station basin via remote sensing,with the goal of providing theoretical support for the implementation of ecological water conveyanceand agricultural watersaving projects in the future.

Key words: ecological water conveyance; agricultural water-saving； inland arid basin； remote sensing hydro-logical station; Google Earth Engine (GEE)