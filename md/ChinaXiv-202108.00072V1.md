# 吐鲁番盆地骆驼刺保护区植被覆盖度时空演变

李梓钰，陈启慧，黄峰，郭振天(河海大学水文水资源学院,江苏 南京210098)

摘要：基于Landsat TM/ETM+/OLI影像数据和无人机影像,通过建立归一化植被指数(normalized diference vege-tation index,NDVI)和植被覆盖度关系,计算像元二分模型的参数值,反演1996—2020年吐鲁番骆驼刺保护区的植被覆盖度，再利用一元线性回归分析,研究了吐鲁番骆驼刺保护区历年植被覆盖度演变时空特征。结果表明：25a来，骆驼刺保护区的植被覆盖度总体呈增加趋势，显著改善区面积占比 $2 0 . 1 4 \%$ ,植被覆盖度由 $3 . 0 9 \%$ 增加至$1 8 . 3 0 \%$ ，主要分布在由西向中部沿白杨河尾闾处和西部、东北部居住用地附近。研究结果可为像元二分模型参数值的确定提供科学参考，为吐鲁番盆地生态环境治理和保护提供科学依据。

关键词：像元二分模型；NDVI；植被覆盖度；无人机遥感；骆驼刺保护区；吐鲁番；新疆

吐鲁番盆地是我国典型的干旱区，多年平均降水量小于 $2 0 ~ \mathrm { m m }$ ，潜在蒸发量大约是降水量的200倍，降水量大部分消耗于蒸发，荒漠化面积曾呈不断扩大趋势。疏叶骆驼刺(Alhagisparsifolia)作为多年生深根系草本，具有生命力强，耐盐碱、干旱贫瘠等特性，是阻挡风沙入侵的重要屏障[1]。2009年吐鲁番盆地建立世界上面积最大单一品种的野生骆驼刺保护基地，研究其历年植被覆盖度变化特征、空间变化趋势，可为改善区域生态环境提供参考。植被覆盖度（fractional vegetation coverage,FVC）作为评价生态恢复的重要因子之一，目前主要有地表实测和遥感测量2种方法[2]。地表实测的准确度高，但耗时耗力，只能在小范围内得到植被分布状况变化的信息[3]，遥感测量具有宏观性、时效性且数据易获取的特点4，大致可分为经验模型、植被指数法、混合像元分解模型和光谱梯度差法，其中以像元二分模型最为常见[5]

像元二分模型假定遥感传感器所获得的信息由植被和土壤两部分信息组成6，通过对调节因子做线性拉伸从而削弱大气、土壤背景与植被类型的影响[],其中基于NDVI利用像元二分模型计算植被覆盖度得到了广泛的应用。模型精度在于2个参数的确定，即纯植被覆盖像元对应的 $\mathrm { N D V I _ { v e g } }$ 和纯裸土像元对应的 $\mathrm { \Delta N D V I _ { s o i l } }$ 。大部分学者以NDVI累计频率曲线法来确定参数值，但在我国西北干旱区存在大量荒漠和裸土，这些区域NDVI值普遍偏高，利用频率累计法获取 $\mathrm { N D V I _ { \mathrm { s o i l } } }$ 值偏低，导致植被覆盖度计算结果偏大[8]。因此,累计频率法不宜用于反演稀疏植被覆盖区[9]，如何精确获取像元二分模型的2个参数,是估测稀疏植被覆盖度的难点。罩志豪等[0]提出取明显茂密植被区的平均NDVI作为 $\mathrm { \Delta N D V I _ { v e g } }$ 明显裸土区的平均NDVI作为 $\mathrm { N D V I _ { \mathrm { s o i l } } }$ 进行估计；何宝忠等[9结合土地利用分类图取无水体和积雪区NDVI的最大和最小值作为 $\mathrm { N D V I _ { v e g } }$ 和 $\mathrm { \Delta N D V I _ { s o i l } }$ ，但高空遥感影像获取的植被光谱信息较为微弱，通常需要结合实地调查[]。无人机遥感作为生态环境领域新的观测技术手段，弥补了航天和航空遥感在分辨率、重访周期、云层影响以及高成本等方面的不足[2]，且利用搭载可见光传感器的无人机进行低空拍摄，可以快速准确地确定绿色植被的范围，降低了野外工作量，减小了人工测量时的面积量算误差[9]。无人机相较于卫星遥感和人工测量具有一定优势，近几年被用于种群分布、动态监测、作物生物量估算[13]等方面，对于野外样方调查[4]以及结合植被指数计算植被覆盖度5的相关研究也在逐渐进行。

利用1996—2020年的LandsatTM/ETM+/OLI遥感影像计算NDVI,结合无人机低空遥感得到的植被覆盖度建立关系曲线，得到像元二分模型中的参数值 $\mathrm { N D V I _ { v e g } }$ 和 $\mathrm { N D V I _ { \mathrm { s o i l } } }$ ，反演骆驼刺保护区历年植被覆盖度，并在此基础上进行一元线性回归趋势性和显著性检验，分析骆驼刺保护区1996一2020年植被覆盖的时空变化特征，以期为吐鲁番盆地今后的生态环境保护和改善提供依据。

# 1 数据和方法

# 1.1骆驼刺保护区概况

骆驼刺保护区于2009年建立，地理位置介于$4 2 ^ { \circ } 3 2 ^ { \prime } { \sim } 4 2 ^ { \circ } 5 5 ^ { \prime } \mathrm { N } , 8 8 ^ { \circ } 4 3 ^ { \prime } { \sim } 8 8 ^ { \circ } 4 6 ^ { \prime } \mathrm { E }$ 之间(图1)，面积达 $1 . 0 7 \times 1 0 ^ { 5 } \mathrm { h m } ^ { 2 }$ ,地处吐鲁番盆地腹地，西南为托克逊县郭勒布依乡，东南边为鄯善县迪坎尔乡，南边紧邻吐鲁番盆地最低处艾丁湖。吐鲁番盆地四周环山，地势低凹，太阳辐射强，地面增温迅速，热量不易散失，加上受塔里木热低压的影响，炎热期长，多风[16],导致了盆地现今的极端干旱气候。盆地内年降雨量仅为 $1 0 { \sim } 2 6 ~ \mathrm { m m }$ ，而蒸发量却高达3000$\mathbf { m } \mathbf { m } ^ { [ 1 7 ] }$ 。极端最高气温达 $4 9 . 6 ~ \mathrm { { ‰} }$ ,地面直射最高温度为 $7 6 . 6 \mathrm { { ^ { \circ } C } }$ ,最大风速可达 $4 0 \mathrm { m } \cdot \mathrm { s } ^ { - 1 [ 1 8 ] }$

# 1.2数据来源与处理

1.2.1遥感数据采用研究区1996—2020年的LandsatTM/ETM $+ / \mathrm { O L I }$ 影像数据，选取7—9月植被年内繁盛期，云量稀少、数据真实度较高的影像，可以较好地反映研究区的植被覆盖状况。影像数据来源于地理空间数据云(http://www.gscloud.cn/）和USGS美国国家航空航天局（NationalAeronauticsand Space Administration）的官方网站（http://glovis.usgs.gov/），影像分辨率为 $3 0 \mathrm { ~ m ~ }$ ，利用ENVI5.3软件对影像进行辐射定标、大气校正等处理后，沿骆驼刺保护区边界矢量图进行裁剪，得到遥感影像并计算NDVI。

1.2.2无人机数据2019年8月中上旬，开展了无人机拍摄骆驼刺保护区典型植被样方工作。根据保护区内现场植被分布特征和道路可达性，选取低、中、高不同植被覆盖度类型设置样方(图1)。利用搭载可见光传感器的DJIPhantom4RTK型无人机对野外样方航拍，高度为 $1 0 0 \mathrm { m }$ ,拍摄范围大于样方范围，以便后期影像预处理，一共获取11张无人机影像。从无人机影像中共提取260个样点，利用基于0 阈值的过绿减过红指数(excess green minusexcess red, $\mathrm { E x G - E x R }$ )生成二值化图像，可将植被和背景很好分离[19],根据ArcGIS分区统计植被覆盖度值。

# 1.3 研究方法

1.3.1精度评价Kappa系数适用于无序分类资料和等级资料的一致性检验，已成为目前应用非常广泛的评价指标[20]。利用ArcGIS在无人机影像中随机生成150个点，通过目视解译判别植被和裸土，与ExG-ExR的二值化结果建立混淆矩阵，计算Kappa系数和总体精度。

1.3.2基于NDVI的像元二分模型归一化植被指数NDVI指示植被生长状况及空间分布，选取像元二分模型将NDVI植被指数转化为植被覆盖度，可以弥补NDVI受土壤背景和大气影响的不足[21],计算公式如下：

$$
\mathrm { F V C } = \frac { \mathrm { N D V I - N D V I _ { \mathrm { s o i l } } } } { \mathrm { N D V I _ { \mathrm { v e g } } - N D V I _ { \mathrm { s o i l } } } }
$$

式中：FVC和NDVI分别是某一像元的植被覆盖度和归一化植被指数; $\mathrm { N D V I _ { v e g } }$ 为纯植被覆盖像元的NDVI值； $\mathrm { N D V I _ { \mathrm { s o i l } } }$ 为纯裸土覆盖像元的NDVI值。

由NDVI-FVC散点图得到拟合曲线。令 $\mathrm { F V C = 1 }$ 和 $\mathrm { F V C = 0 }$ 分别得到纯植被覆盖像元对应的 $\mathrm { \Delta N D V I _ { v e g } }$ 和纯裸土像元对应的 $\mathrm { \Delta N D V I _ { s o i l } }$ ，代入像元二分模型对保护区内植被覆盖度进行估算，得到历年植被覆盖图。

![](images/44a8f048321faf79a08f6876729020d9ba8b7069c03ef5e6e24cbf5d09cdb908.jpg)  
图1骆驼刺保护区位置及样点分布图  
Fig.1Location of Alhagi sparsifolia Reserve and distribution of sample points

1.3.3植被覆盖度时空变化趋势分析采用一元线性回归分析1996—2020年骆驼刺保护区植被覆盖度的变化趋势，其公式如下：

$$
\theta _ { \mathrm { s l o p e } } = \frac { n \times \displaystyle \sum _ { i = 1 } ^ { n } i \times \mathrm { F V C } _ { i } - \displaystyle \sum _ { i = 1 } ^ { n } i \displaystyle \sum _ { i = 1 } ^ { n } \mathrm { F V C } _ { i } } { n \times \displaystyle \sum _ { i = 1 } ^ { n } i ^ { 2 } - \left( \displaystyle \sum _ { i = 1 } ^ { n } i \right) ^ { 2 } }
$$

式中： $\theta _ { \mathrm { s l o p e } }$ 为植被覆盖度变化斜率;年份 $n { = } 2 5$ ; FVCi为第 $i$ 年的植被覆盖度。斜率为正表示植被覆盖度增加，反之减少。 $F$ 检验用来判别解释变量和因变量之间有无线性相关关系[22],采用 $P$ 来确定植被覆盖度变化趋势的显著性水平。根据检验结果将变化趋势分成3个区域：显著改善区（ $\theta _ { \mathrm { s l o p e } } > 0 , P <$ 0.05);不显著变化区(P≥0.05);显著退化区（θslope<$0 , P < 0 . 0 5$ ）。

# 2结果与分析

# 2.1植被覆盖度与NDVI关系曲线

目视解译的总体分类精度为 $9 8 . 6 \%$ ,Kappa系数为0.84,精度较高，分类结果可靠。将FVC与NDVI建立关系曲线(图2)， $R ^ { 2 }$ 达到0.85，拟合程度较好。

在 $0 . 1 < \mathrm { N D V I } < 0 . 2$ 区域内，样点靠近横轴聚集分布，这是由于在低植被覆盖区域，部分红外光散射或透射到无植被冠层覆盖的地表，然后反射回传感器，造成传感器接收到的植被信息包含部分的土壤信息，导致植被指数偏大23；在 $\mathrm { N D V I } { > } 0 . 5$ 区域内，样点多分布于曲线左侧，表明在植被覆盖度较高的区域，NDVI逐渐趋近饱和，不再随着FVC增长。

![](images/886bfae833d06731f29092088698b50b428d0a542b2bceab4c5e50c0f87b61b2.jpg)  
图2FVC与NDVI关系曲线

根据NDVI和FVC的定义，令 $\mathrm { F V C = 0 }$ ,得到ND-  
$\mathrm { V I } { = } 0 . 0 9$ ,即纯裸土像元 $\mathrm { N D V I _ { \mathrm { s o i l } } } { = } 0 . 0 9$ ；令 $\mathrm { F V C = 1 }$ ，得  
到 $\mathrm { N D V I } { = } 0 . 7 4$ ,即纯植被像元 $\mathrm { N D V I _ { v e g } } { = } 0 . 7 4$ 。二者关  
系可以描述为：  
FVC $\mathbf { \Sigma } = \mathbf { \Sigma }$ 0 $\mathrm { N D V I } < 0 . 0 9$   
1.9766NDVI+0.0247NDVI-0.0146， $0 . 0 9 \leqslant \mathrm { N D V I } < 0 . 7 4$ 1 ， $\mathrm { N D V I } \geqslant 0 . 7 4$

当 $\mathrm { N D V I } { < } 0 . 0 9$ 时，所对应像元为纯裸土像元，即$\mathrm { N D V I _ { \mathrm { s o i l } } } { = } 0 . 0 9$ ；当 $\mathrm { N D V I } { \geqslant } 0 . 7 4$ 时，所对应像元为纯植被像元，即 $\mathrm { N D V I _ { v e g } } { = } 0 . 7 4$ ；当 $0 . 0 9 { \leqslant } \mathrm { N D V I } { < } 0 . 7 4$ 之间时，FVC和NDVI为二次函数关系。理论上，纯裸土像元 $\mathrm { \Delta N D V I _ { \mathrm { s o i l } } }$ 应当为0,但由于土壤颜色、大气影响等，其值一般在-0.1\~0.2之间[24]， $\mathrm { N D V I _ { \mathrm { s o i l } } } { = } 0 . 0 9$ 可认为合理；由NDVI算式结构可知，NDVI的增加与NIR/RED增加不是线性关系，当植被覆盖度达到一定值，红光通道的吸收饱和，导致NDVI达到最大值,一般认为NDVI在0.8左右达到饱和[25], $\mathrm { \Delta N D V I _ { v e g } = }$ 0.74可认为合理。

# 2.2植被覆盖度变化趋势分析

2.2.1 植被覆盖度年际变化特征1996—2020年骆驼刺保护区的植被覆盖度均值较低(图3)，但整体呈显著增加趋势 $( P { < } 0 . 0 1 )$ ，由 $0 . 7 6 \%$ 上升至 $1 . 5 5 \%$ ，增加速度为 $2 . 3 \% \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 。大致可以将其分为2个阶段：（1）1996—2011年，整体植被覆盖度偏低，均值为 $1 . 1 2 \%$ ；（2）2012—2020年，植被覆盖度均值增加，均值为 $1 . 4 8 \%$ ,相比前一阶段明显提高。

![](images/50291358889c783689b92db1e3f7a9afeccea897635066131b51479d8f0c038c.jpg)  
Fig.2 Correlation curve between FVC and NDVI   
图31996—2020年骆驼刺保护区植被覆盖度变化Fig.3VariationchartofFVC inAlhagi sparsifoliaReservefrom 1996 to 2020

2.2.2植被覆盖度变化趋势分析植被覆盖度显著改善区面积为 $2 0 0 . 4 6 \mathrm { k m } ^ { 2 }$ (表1)，占整个骆驼刺保护区 $2 0 . 1 4 \%$ ,植被覆盖度均值为 $9 . 8 4 \%$ ，主要分布在沿北部天山而下的白杨河两岸和西部、东北部居民区附近(图4)。

# 表1骆驼刺保护区植被覆盖度变化面积及比例

Tab.1 Area and ration of vegetation coverage change in the Alhagi sparsifolia Reserve   

<html><body><table><tr><td>区域</td><td>植被覆盖度/%</td><td>面积/km²</td><td>面积比例/%</td></tr><tr><td>显著改善区</td><td>9.84</td><td>200.46</td><td>20.14</td></tr><tr><td>不显著变化区</td><td>2.92</td><td>486.31</td><td>48.87</td></tr><tr><td>显著退化区</td><td>2.65</td><td>308.37</td><td>30.99</td></tr></table></body></html>

![](images/b0429decf104967873d1b1b3a4459d3509c5ed78719af924823c6aeb41599bc6.jpg)  
图41996—2020年骆驼刺保护区植被覆盖度变化趋势Fig.4Change trend ofFVC in theAlhagi sparsifoliaReserve from 1996 to 2020

2.2.3不同区域植被覆盖度变化对显著改善区、不显著变化区、显著退化区3个区域进行区域内的植被覆盖度时间趋势分析(图5)：(1）25a以来，显著改善区域植被覆盖度增长幅度最大，从 $3 . 0 9 \%$ 增至 $1 8 . 3 0 \%$ ;(2）退化区域植被覆盖度从 $3 . 3 8 \%$ 降至$0 . 8 9 \%$ ,变化幅度很小，且本身植被覆盖度很低，接近裸土，退化并不明显，可将其归为不显著变化区域。总体上显著改善区域植被覆盖度大幅度增加，同时其他区域植被覆盖度变化不明显，使得骆驼刺保护区内植被覆盖度整体呈增加趋势。

# 3讨论

植被覆盖度变化趋势的分析结果表明，1996—2020年新疆吐鲁番盆地骆驼刺保护区植被覆盖度波动上升（图3）。2009年骆驼刺保护区的确立后，第二阶段2012—2020年植被覆盖度均值明显提高，表明生态环境的改善存在着一定的滞后效应，

![](images/5f507c4d79793122b4aab3a6896e28c04a82045983d947f9bf4bc94c5c7e481e.jpg)  
图51996—2020年骆驼刺保护区不同区域植被覆盖度变化  
Fig.5Variation ofclassified FVC in different areas of the Alhagi sparsifoliaReserve from1996 to 2020

植被变化受控于气候变化，由于水汽来源、地形组合的影响，新疆地区水热组合条件对植被的影响较为复杂[26]。刘洋等[27]认为,在新疆以耐盐碱植被为主要植被类型的绿洲和荒漠交错带，水分条件是影响植被生长的主要因素。吐鲁番盆地骆驼刺保护区位于盆地腹地，因降水极为稀少导致植被对降水依赖性较小，植被主要的水分来源依靠周边山区降水形成的地下径流和地表径流。

植被覆盖度变化空间分布特征的分析结果表明，显著改善区域分布于沿白杨河两岸、尾闾和保护区西部、东北部居民区附近(图4)。白杨河发源于北侧东天山山脉博格达山南麓，是吐鲁番盆地内集水面积最大的河流[28]。部分散流穿过托克逊县，由西北向东南流经骆驼刺保护区，最后在保护区中部地势最低处汇入尾闾艾丁湖，可供给河岸带、尾闾骆驼刺生长需水。张爱民等2遥感解译得到白杨河供给骆驼刺生态用水面积 $1 7 9 5 3 . 6 \mathrm { h m } ^ { 2 }$ ，占白杨河流域平原区生态用水总面积 $6 5 \%$ ，补给艾丁湖及周边骆驼刺草地生态水量 $4 . 2 6 \times 1 0 ^ { 7 } \mathrm { m } ^ { 3 }$ 。同时，保护区西部是托克逊县所在绿洲，主要分布于阿拉沟河和白杨河冲洪积扇下部，水源条件良好，保护区东北部是火焰山以南的绿洲，位于冲击平原下部，水源主要来自火焰山泉水，水量稳定，土地平坦开阔，是良好的农作区[30]。在吐鲁番盆地特殊的地形作用下，农业灌溉用水下渗，对保护区内植被生长起着一定的促进作用。干旱区的水资源对于植被的生长和恢复至关重要，显著改善区的植被由于充足的水分来源，其植被覆盖度均值远高于不显著变化区和显著退化区(图5)，且长势良好，更容易改善。

李均力等认为，人工生态输水可维持下游干旱区荒漠河岸带植被正常生长所需的地下水位，使植被得到有效恢复。对于潜在蒸发量可达 $3 0 0 0 \mathrm { m m }$ 的吐鲁番盆地而言，本身降水量稀少，同时还由于托台渠首沿程的农业引水导致白杨河、托台渠首之前汇入白杨河的阿拉沟等河流流入尾闾艾丁湖的流量减少[32]。可适当减少农业引水、增加生态输水或人工浇灌骆驼刺等措施，以增加水资源量的补给，进一步提高骆驼刺保护区的植被覆盖度。

新疆南部夏季平均高温日数分布在以吐鲁番盆地为中心向西、南、东方向延伸的区域[33]。受热气候影响,吐鲁番盆地荒漠地貌广泛发育[17]。大部分学者以吐鲁番盆地为研究对象，探究植被覆盖度的变化[16.27]。骆驼刺保护区位于吐鲁番盆地托克逊县绿洲区和火焰山以南绿洲区间的戈壁区域，自然条件较差，土壤盐渍化程度较大，植被覆盖度低。本研究聚焦骆驼刺保护区，研究其植被覆盖度时空变化，可为遏制绿洲荒漠化提供一定的科学依据。

在利用像元二分模型估算干旱区区域尺度植被覆盖度研究中，如何获取像元二分模型中的参数值一直是技术难点。相较于传统的累计频率法获取参数值，本研究采用无人机遥感与卫星遥感结合的方法估计参数值，可为像元二分模型的参数确定提供技术支撑。

本研究还存在一定的局限性，有待进一步完善和改进：（1）由于天气和时间条件对野外工作的限制性，无法使无人机实测数据与遥感影像的获取时间保持完全同步。（2）由于卫星传感器的不同，在获取Landsat影像资料时，数据源不完全一致。（3）只定性地对植被覆盖度的影响因素进行了分析，下一步可以对保护区内白杨河径流演变、径流影响因素与植被覆盖度做进一步相关分析。

# 4结论

（1）从整体变化趋势来看：1996—2020年新疆吐鲁番骆驼刺保护区FVC均值为 $1 . 2 5 \%$ 。植被覆盖度低但整体上呈上升趋势，增加速度为 $2 . 3 \%$ ·$( 1 0 \mathrm { a } ) ^ { - 1 }$ ，且在2012年后出现较大幅度的增长，平均植被覆盖度由 $1 . 1 2 \%$ 增加为 $1 . 4 8 \%$ 。总体上看，骆驼刺保护区的建立对当地生态起到了一定的改善作用。

（2）从区域变化趋势来看：1996—2020年骆驼刺保护区显著改善区域占 $2 0 . 1 4 \%$ ，植被覆盖度从$3 . 0 9 \%$ 增至 $1 8 . 3 0 \%$ ，主要分布于从西北部向中部的白杨河尾闾两侧，以及西部、东北部紧邻居民区。

# 参考文献(References)：

[1]罗瀚林,曾凡江,郭自春,等.春季与秋季刈割对疏叶骆驼刺叶 片功能性状的影响[J].草业科学,2016,33(4):691-699.[Luo Hanlin,Zeng Fanjiang,Guo Zichun,et al.Influence of spring and fallclipping onthe leaf functional traitsof Alhagi Sparsifolia[J]. Pratacultural Science,2016,33(4): 691-699.]   
[2]邢著荣,冯幼贵,杨贵军,等.基于遥感的植被覆盖度估算方法 述评[J].遥感技术与应用,2009,24(6):849-854.[Xing Zhurong, Feng Yougui, Yang Guijun, et al. Method of estimating vegatation coverage based on remote sensing[J]. Remote Sensing Technology and Application,2009,24(6): 849-854.]   
[3]程红芳,章文波,陈锋.植被覆盖度遥感估算方法研究进展[J]. 国土资源遥感,2008,20(1):13-18.[Cheng Hongfang,Zhang Wenbo,Chen Feng.Advances in researches on application of remote sensing method to estimating vegetation coverage[J]. Remote Sensing for Land & Resources,2008,20(1): 13-18.]   
[4]郭玉川,何英,李霞.基于MODIS的干旱区植被覆盖度反演及 植被指数优选[J].国土资源遥感,2011,23(2):115-118.[Guo Yuchuan,He Ying, Li Xia.Remote sensing inversion of vegetation coverage and optimization of vegetation index based on modis data in arid area[J].Remote Sensing for Land & Resources,2011,23 (2): 115-118.]   
[5]古丽·加帕尔,陈曦,包安明.干旱区荒漠稀疏植被覆盖度提取 及尺度扩展效应[J].应用生态学报,2009,20(12):2925-2934. [Guli Jiapaer, Chen Xi, Bao Anming. Coverage extraction and upscaling of sparse desert vegetation in arid area[J]. Chinese Journal of Applied Ecology,2009,20(12): 2925-2934.]   
[6]陈晋,陈云浩,何春阳,等.基于土地覆盖分类的植被覆盖率估 算亚像元模型与应用[J].遥感学报,2001,5(6):416-422.[Chen Jin, Chen Yunhao,He Chunyang,etal.Sub pixel model for vegetation fraction estimation based on land cover classification[J]. Journal of Remote Sensing,2001, 5(6): 416-422.]   
[7]白彦.呼伦贝尔沙地植被覆盖度变化遥感监测研究[D].呼和浩 特:内蒙古农业大学,2013.[Bai Yan.Study on Vegetation Coverage Change of Hulunbeier Sand Land By Remote Sensing[D]. Hohhot: Inner Mongolia Agricultural University,2013.]   
[8]沈谦,朱长明,张新.GF-2支持下的干旱区稀疏植被区植被覆 盖度估算[J].测绘通报,2019(7):33-38.[Shen Qian,Zhu Changming,Zhang Xin.Fractional vegetation cover estimation in arid and rare vegetation area aided by GF-2 remote sensing data[J]. Bulletin of Surveying and Mapping, 2019(7): 33-38.]

[9]何宝忠,丁建丽,张喆,等.新疆植被覆盖度趋势演变实验性分 析[J].地理学报,2016,71(11):1948-1966.[He Baozhong,Ding Jianli, Zhang Zhe,et al.Experimental analysis of spatial and temporal dynamics of fractional vegetation cover in Xinjiang[J]. Acta Geographica sinica,2016,71(11): 1948-1966.]

[10] 覃志豪,李文娟,徐斌,等.陆地卫星TM6波段范围内地表比辐 射率的估计[J].国土资源遥感,2004,16(3):28-32.[Qin Zhihao, Li Wenjuan, Xu Bin,et al. The estimation of land surface emissivity for landsat TM6[J].Remote Sensing for Land & Resources, 2004, 16(3): 28-32.]   
[11]卞雪.基于无人机低空遥感影像可见光波段的植被覆盖率研究 [D].南京:南京农业大学,2017.[Bian Xue.Vegetation Coverage Calculation Using Remote Sensing Image of Unmanned Aerial Vehicle Based on Visible Spectrum[D]. Nanjing: Nanjing University, 2017.]   
[12] 高永平,康茂东,何明珠,等.基于无人机可见光波段对荒漠植 被覆盖度提取的研究——以沙坡头地区为例[J].兰州大学学 报(自然科学版),2018,54(6): 770-775.[Gao Yongping,Kang Maodong,He Mingzhu,etal.Extractionofdesert vegetationcoverage basedon visible light band information of unmanned aerial vehicle: A case study of Shapotou region[J]. Journal of Lanzhou University(Natural Sciences Edition),2018,54(6): 770-775.]   
[13]Elazab A, Raziel A. Ord6ez, Savin R,et al. Detecting interactive effects of N fertilization and heat stress on maize productivity by remote sensing techniques[J]. European Journal of Agronomy, 2016,73: 11-24.   
[14]万炜,肖生春,陈小红,等.无人机遥感在野外植被盖度调查中 的应用——以阿拉善荒漠区灌木为例[J].干旱区资源与环境, 2018,32(9):150-156.[Wan Wei, Xiao Shengchun, Chen Xiaohong,et al.Application of unmanned aerial vehicles to field vegetation coverage survey: A study of shrubs on Alxa desert[J]. Journal of Arid Land Resources and Environment, 2018,32(9): 150-156.]   
[15] 宋清洁,崔霞,张瑶瑶,等.基于小型无人机与MODIS数据的草 地植被覆盖度研究——以甘南州为例[J].草业科学,2017,34 (1): 40-50.[Song Qingjie, Cui Xia, Zhang Yaoyao,et al.Grassland fractional vegetation cover analysis using small UVAs and MODIS: Acase study in Gannan Prefecture[J]. Pratacultural Science, 2017,34(1): 40-50.]   
[16] 阿不都克依木·阿布力孜,地里夏提·买买提,阿布都沙塔尔·买 买提明,等.吐鲁番盆地植被盖度变化的自然及人文耦合分析 [J].新疆农业科学,2007,44(5): 667-671.[Abudukeyimu Abulizi,Dilixiati Maimaiti,Abudushataer Maimaitiming,et al.Research of the natural vegetation coverage changes and humanities degrees combination in Turpan Basin[J]. Xinjiang Agricultural Sciences,2007,44(5): 667-671.]   
[17] 张晓,魏青军,刘亮.吐鲁番盆地地下水与植被的关系研究[J]. 山东国土资源,2016,32(7): 42-48.[Zhang Xiao,Wei Qingjun, Liu Liang.Research on relation between groundwater and vegetation in Turpan Dasin[J]. Shandong Land and Resources,2016,32 (7): 42-48.]   
[18] 熊黑钢.新疆资源环境与可持续发展[M].乌鲁木齐:新疆大学 出版社,2001. [Xiong Heigang. Resources Environment and Sustainable Development in Xinjiang[M]. Urumqi: Xinjiang University Press, 2001.]   
[19]Meyer GE,Neto JC.Verification of color vegetation indices for automated crop imaging applications[J]. Computers and Electronics in Agriculture,2008,63(2): 282-293.   
[20] 郭轶斌,郭威,秦宇辰,等.基于Kappa 系数的一致性检验及其 软件实现[J].中国卫生统计,2016,33(1):169-170.[Guo Yibin, Guo Wei, Qin Yuchen, et al. Consistency test based on Kappa coefficient and its software implementation[J]. Chinese Journal of Health Statistics,2016,33(1): 169-170.]   
[21] 李苗苗.植被覆盖度的遥感估算方法研究[D].北京:中国科学 院研究生院遥感应用研究所,2003.[LiMiaomiao.The Method of Vegetation Fraction Estimation by Remote Sensing[D]. Beijing: Mapping and Geographical Information System,2003.]   
[22] 董振宁,张良.回归分析预测认识中的一个误区[J].统计与决 策,2007(9): 135-136.[Dong Zhenning, Zhang Liang.A misunderstanding of regression analysis and prediction[J]. Statistics & Decision, 2007(9): 135-136.]   
[23]Qi JG,Chehbouni AR, Huete AR,et al.A modified soil adjusted vegetation index[J]. Remote Sensing of Environment,1994,48(2): 119-126.   
[24]Carlson TN,Ripley DA.On the relation between NDVI, fractional vegetation cover,and leaf area index[J]. Remote Sensing of Environment,1997,62(3): 241-252.   
[25] 杨嘉,郭锯,黄蕾诺,等.西北地区MODIS-NDVI指数饱和问题 分析[J].高原气象,2008,27(4):896-903.[Yang Jia,Guo Ni, Huang Leinuo,et al.Analyses on MODIS-NDVI index saturation in Northwest China[J].Plateau Meteorology,2008,27(4): 896-903.]   
[26] 庞冉,王文.基于MODIS 数据的吐鲁番盆地 2001—2017年植被 变化及水热组合影响分析[J].干旱区地理,2020,43(5):1242- 1252.[Pang Ran, Wang Wen.Analysis of vegetation index changes and the influence of hydrothermal combination in Turpan Basin from 2001 to 2017 Based on MODIS Data[J].Arid Land Geography, 2020,43(5): 1242-1252.]   
[27] 刘洋,李诚志,刘志辉,等.1982—2013年基于GIMMS—NDVI 的新疆植被覆盖度时空变化[J].生态学报,2016,36(19):6198- 6208.[Liu Yang,Li Chengzhi, Liu Zhihui, et al. Assessment of spatiotemporal variations in vegetation cover in Xinjiang from 1982 to 2013 basedon GIMMS-NDVI[J].Acta Ecologica Sinica, 2016,36(19): 6198-6208.]   
[28] 阿不力米提·阿不力克木,周京武.新疆吐鲁番盆地地表径流特 征[J].冰川冻土,2014,36(3):717-723.[Abulimiti Abulikemu, Zhou Jingwu. Surface discharge characteristics of the Turpan Basin,Xinjiang[J]. Journal of Glaciologyand Geocryology,2014,36 (3): 717-723.]   
[29] 张爱民,郝天鹏,周和平,等.新疆白杨河流域特征及生态植被 需水分析[J].生态学报,2021,41(5):1-10.[Zhang Aimin,Hao Tianpeng, Zhou Heping,et al. Analysis on characteristics of Baiyang River Basin and water requirement of ecological vegetation in Xinjiang[J]. Acta Ecologica Sinica,2021,41(5): 1-10.]   
[30]王永兴.吐鲁番盆地绿洲环境区划研究[J].干旱区地理,1996,19 (2):30-36.[Wang Yongxing. Environmental regionalization of the oases in Turpan Basin[J].Arid Land Geography,1996,19(2): 30-36.]   
[31]李均力,肖昊,沈占锋,等.2013—2018年塔里木河下游植被动 态变化及其对生态输水的响应[J].干旱区研究,2020,37(4): 985-992.[Li Junli,Xiao Hao,Shen Zhanfeng,et al.Vegetation changes during the 2O13-2O18 period and its response to ecological water transport in the lower reaches of the Tarim River[J].Arid Zone Research,2020,37(4): 985-992.]   
[32]曹国亮,李天辰,陆垂裕,等.干旱区季节性湖泊面积动态变化 及蒸发量—以艾丁湖为例[J].干旱区研究,2020,37(5): 1095-11O4.[Cao Guoliang,Li Tianchen,Lu Chuyu,et al.Dynamic variation and evaporation of seasonal lakes in arid areas:A case study for the Aiding Lake[J]. Arid Zone Research,2O2O,37(5): 1095-1104.]   
[33] 陈颖,邵伟玲,曹萌,等.新疆夏季高温日数的变化特征及其影 响因子[J].干旱区研究,2020,37(1):58-66.[Chen Ying,Shao Weiling,Cao Meng,et al.Variation of summer high temperature daysand its affecting factors in Xinjiang[J].Arid Zone Research, 2020,37(1): 58-66.]

# Spatiotemporal evolution of vegetation coverage in Alhagi sparsifolia Reserve in Turpan Basin, Xinjiang

LI Ziyu， CHENG Qihui， HUANG Feng， GUO Zhentian (College of Hydrology and Water Resources,Hohai University,Nanjing 21Oo98,Jiangsu, China)

Abstract: It is of substantial significance for ecological and environmental protection to restore vegetation coverage byreturning grazing land to grassand.In this study,the regional normalized diference vegetation index (NDVI) data were extracted from Landsat Thematic Mapper (TM)/ Enhanced Thematic Mapper Plus $( \mathrm { E T M ^ { + } } ) /$ （204 Operational Land Imager multi-phase remote sensing images, which were selected from July to September of each year from 1996 to 2020. Meanwhile,Fractional Vegetation Coverage (FVC) was calculated by computing the equation of Excess Green minus Excess Red (ExG-ExR).Additionally,the variables in the equation were based on Unmanned Aerial Vehicle images in the early part of August 2019.The best-fit curve between NDVI and FVC was first established based on the above NDVI and FVC data in the same period.Then,two parameters of the pixel binary model were calculated through the fited curve between NDVI and FVC: NDVIfor the pure bare soil pixels and NDVI for the pure vegetation cover pixels.Then,the pixelbinary model was used to retrieve thevegetation coverage of the Alhagi sparsifolia reserve in the Turpan Basin from 1996 to 2O20.Finally, linear regression analysis was used to investigate the evolution of vegetation coverage in the A.sparsifolia Reserve in the Turpan Basin throughout the study period.The results showed that vegetation coverage increased in the $A$ sparsifolia Reserve in the Turpan Basin over the past 25 years.The area of the significant improvement area accounted for $2 0 . 1 4 \%$ of the total area of the A. sparsifolia Reserve in the Turpan Basin,and the vegetation coverage of the significant improvement area increased from $3 . 0 9 \%$ to $1 8 . 3 0 \%$ over the past 25 years.A. sparsifolia was primarily distributed from western to central regions in the significant improvement area along the tail ofthe Baiyang River,which empties into the Aiding Lake,its terminal lake,at the lowest altitude of the $A$ sparsifolia Reserve. The areas in the west and northeast of the A.sparsifolia Reserve,which were close to residential land located in the south of the Flaming Mountains and east of Tuokesun County,also belonged to the significant improvement area.The results of this research provide a scientific reference for selecting the two parameters of the pixel binary model and a scientific basis for ecological environment management and protection of the Turpan Basin in Xinjiang.

Keywords: the pixel binary model; normalized diffrence vegetation index； fractional vegetation coverage；unmanned aerial vehicle remote sensing; Alhagi sparsifolia Reserve; Turpan; Xinjiang