# 博格达峰地区冰川和积雪变化遥感监测及影响因素分析

周远刚1,²，赵锐锋1,²，张丽华1,²，赵敏1,2（1西北师范大学地理与环境科学学院,甘肃兰州730070；2甘肃省土地利用与综合整治工程研究中心,甘肃兰州730070)

摘要：20世纪以来，随着全球气候变暖加剧,冰川和积雪普遍退缩，严重影响到人类的生存和社会经济的可持续发展,这一问题在我国西北干旱区的博格达峰地区及其周边地区尤为突出。以博格达峰地区为例，利用1990—2016年Landsat5与Landsat8遥感影像，对比分析归一化积雪指数(NDSI)、归一化冰雪指数（NDSII）、归一化主成分雪指数（NDPCSI)和缨帽转换湿度指数（WET)在博格达峰地区监测冰川和积雪的能力，同时结合研究区周边气温、降水数据和研究区地形数据，探讨博格达峰地区冰川和积雪面积变化与区域地形、气候间的响应关系。结果表明：（1）WET相对于 NDSII、NDSI和NDPCSI精度值更高，可以替代NDSI、NDSII监测博格达峰地区冰川和积雪面积。（2）博格达峰地区冰川和积雪面积呈持续退缩的趋势。1990—2016年,冰川和积雪面积减少率约$2 0 . 0 7 \%$ ，且年退缩率不断增加。（3）高程、坡度和坡向对冰川和积雪面积变化的影响较显著，山地阴影对其影响较弱，气温的升高是冰雪面积减少的主要因素。

关键词：Landsat；指数；冰川和积雪变化；博格达峰

冰川和积雪是反应全球气候变暖的指标，也是干旱地区人类赖以生存和发展的重要水资源，对区域生态环境、人民生产生活和社会经济发展起到至关重要的作用[1-2]。近年来,在自然和社会经济因素双重驱动下，全球范围内冰川和积雪的数量和面积也呈现出不同程度的缩减状态[3-4] 0长期的冰川和积雪退缩可能会使区域水资源储量降低，也可能会使河川径流减少，这必然会对内陆干旱地区可持续发展带来深远的影响[5]。因此,加强冰川和积雪的监测水平对了解气候动态、干旱区水资源变化以及对干旱地区的可持续发展至关重要。

遥感监测是研究冰川和积雪的普遍方法。NO-AAAVHRR(Advanced Very High Resolution Radiom-eter）和 MODIS(Moderate Resolution Imaging Spectroradiometer)被广泛用于全球尺度上冰川和积雪监测研究，但因其空间分辨率相对较低（分别为 $1 . 1 \ \mathrm { k m }$ 和 $5 0 0 \mathrm { ~ m ~ }$ ）,不适用于区域研究[3.6]。近年来,Landsat因高分辨率( $3 0 ~ \mathrm { m } \dot { }$ 、全球覆盖和丰富的数据被广泛用于区域冰川和积雪研究[7]。在冰川和积雪信息的提取上，目前主要有人工解译、自动或半自动分类以及基于指数的提取方法[8]。人工解译和自动或半自动分类虽然精度较高，但需要丰富的判读经验和技巧,且耗时耗力,实际应用较为困难[9-10]。基于指数的方法通过监测阈值获取冰川和积雪的监测结果[],由于其快速、简单、准确的优点,在研究中得到了广泛的应用。如BURNS等[12]、DURAN-ALARCON 等[13]使用归一化积雪指数（NDSI)提取秘鲁科迪勒拉山脉冰川信息；SANKEY等[14]]WALTERS等[15]使用NDSI提取积雪覆盖信息,开发适合的积雪分类模型和降低季节性积雪融化面积的方法;孙永猛等[16]、孙志群等[17]使用NDSI提取新疆地区积雪覆盖信息，对积雪覆盖进行反演。但NDSI的准确性依赖光谱反射率,受到大气、地形的影响[18]。KHOPKAR等[19]采用归一化冰雪指数(NDSII)提取冰川信息，获取冰川时空分布变化特征及原因。SIBANDZE等[20]利用主成分分析(PCA)区分水体和阴影的优越性开发了归一化主成分雪指数（NDPCSI)。SATIR[3]将缨帽转换湿度指数（WET)用于冰雪监测，发现比NDSI精度更高，但WET难以区分固态和液态的水体。由此可见，利用遥感监测冰川和积雪的方法有很多，但不同研究者基于不同物理指标的冰川和积雪监测方法的适用性并不一致，所以在监测区域，对冰川和积雪监测方法进行系统验证和评估，确保监测结果的有效性和准确性是必要的。

博格达峰地区是东天山最大的冰川作用区，受到许多学者的关注。多数研究者提取该区域冰川和积雪信息时主要采用比值阈值法和NDSI。如何毅等[5]利用比值阈值法提取博格达峰冰川边界，获取了博格达峰冰川持续减少的信息及原因。信息提取方式略显单薄，且对该区域冰川和积雪信息提取方法准确性进行评估的研究不足。分析冰川和积雪覆盖面积变化影响因子时，多数研究考虑气候因素，考虑地形因素影响的文章较少。因此，本文以博格达峰地区为研究对象，应用遥感和地理信息系统等现代手段，对NDSI、NDSII、ND-PCSI、WET4个指数的冰川和积雪监测能力进行了评价，并对冰川和积雪面积变化及其原因进行了深人研究，为准确提取博格达峰地区冰川和积雪信息以及周边地区经济的可持续发展提供理论支撑和决策参考。

# 1 研究区域

博格达峰地区（ $\langle 8 8 ^ { \circ } 0 3 ^ { \prime } \sim 8 8 ^ { \circ } 3 0 ^ { \prime } \mathrm { ~ I ~ }$ 、 $4 3 ^ { \circ } 4 0 ^ { \prime }$ \~$4 3 ^ { \circ } 5 5 ^ { \prime } \mathrm { N }$ ,海拔 $5 ~ 4 4 5 ~ \mathrm { m }$ )位于新疆维吾尔自治区阜康市境内，是天山东段博格达山的主峰(图1)。冬季受强大的蒙古冷高压控制，寒冷而干燥，峰顶温度常在冰点以下。夏季高空盛行西风环流，是典型的中纬西风带大陆型气候。南北坡年平均气温 $0 \mathrm { { ^ \circ C } }$ 等温线海拔分别为 $2 ~ 8 0 0 ~ \mathrm { ~ m ~ }$ 和 $2 ~ 5 0 0 ~ \mathrm { m } ^ { [ 5 ] }$ 。该区域分布有113条现代冰川，分别位于南坡的古班博格达河等，北坡的三工河等河流源头。

![](images/4e6bc99a05effa5d49d70ff86b423da79d0f169d0097fec3cd4d005abcda83f5.jpg)  
图1博格达峰地区冰川和积雪地理分布 Fig1Geographic distribution diagram of Mount Bogda glacier and snow

# 2 数据来源与方法

# 2.1 数据来源

LandsatTMLandsatETM $^ +$ 遥感影像数据和DEM数据来自地理空间数据云（http：//www.gscloud.cn/）。该产品经过了大气校正和地面控制点几何校正并且利用DEM进行地形校正。为减少不同时期冰雪变化所造成的误差，选取影像时间间隔为10a左右并且尽可能选取夏秋季获取的少云或者无云的遥感影像(表1）。气象数据来自中国气象数据网（http://data.cma.cn/site/index.html）,选用研究区周边的吐鲁番（站点编号 $5 1 5 7 3 , 8 9 . 2 ^ { \circ } \mathrm { E } , 4 2 . 9 ^ { \circ } \mathrm { N }$ 海拔 $3 4 5 ~ \mathrm { ~ m ~ }$ ）、奇台（站点编号51379，89. $3 4 ^ { \circ } \mathrm { E }$ ，$4 4 . 0 1 ^ { \circ } \mathrm { N }$ ,海拔 $7 9 3 . 5 \mathrm { ~ m } \mathrm { , ~ }$ )和乌鲁木齐（站点编51463，$8 7 . 3 7 ^ { \circ } \mathrm { E } , 4 3 . 4 7 ^ { \circ } \mathrm { N }$ ，海拔 $9 1 7 . 9 \mathrm { ~ m ~ }$ )3个气象站点近27a的年均气温和年均降水数据。

# 2.2 研究方法

本研究主要分3个步骤进行：（1）使用大气校正和几何校正后的2001年TM遥感影像获取 $N D S I .$

# 表1影像数据信息

Tab.1Images used in this study   

<html><body><table><tr><td>轨道号</td><td rowspan="3">成像日期</td><td rowspan="3">传感器</td><td rowspan="3">平均 云量</td><td rowspan="3">分辨率 /m</td></tr><tr><td>条带号 行编号</td><td></td></tr><tr><td></td><td>TM</td></tr><tr><td>142</td><td>30</td><td>1990 -10-09</td><td></td><td>0.44</td><td>30</td></tr><tr><td>142</td><td>30</td><td>2000-09-02</td><td>TM</td><td>0.60</td><td>30</td></tr><tr><td>142</td><td>30</td><td>2001-10-23</td><td>TM</td><td>0.28</td><td>30</td></tr><tr><td>142</td><td>30</td><td>2001-09-29</td><td>ETM +</td><td>0.06</td><td>30</td></tr><tr><td>142</td><td>30</td><td>2010-08-13</td><td>TM</td><td>0.03</td><td>30</td></tr><tr><td>142</td><td>30</td><td>2016-09 -30</td><td>ETM +</td><td>1.01</td><td>30</td></tr></table></body></html>

NDSII、NDPCSI、WET4个指数，并利用 $1 5 \mathrm { ~ m ~ }$ 的ETM $^ +$ 全色波段检测精度值。（2）使用精度最高的指数监测博格达峰地区冰川和积雪。（3）分析冰川和积雪面积变化影响因素。根据博格达峰地区的实际情况在第一个步骤中，需要使用高分辨影像检验低分辨率影像，而Landsat8与Landsat5数据在2001年同时存在，因此本文采用2001年数据进行精度检验（图2）。

2.2.1积雪和冰川监测指数归一化积雪指数（NDSI），通过绿波段 $( 0 . 5 6 ~ \mu \mathrm { m } )$ ）和近红外（1.65${ \mu \mathrm { m } } ,$ )的光谱反射率差异来识别冰川和积雪[3]；归一化冰雪指数（NDSII）,通过红波段 $( 0 . 6 3 \sim 0 . 6 9 \ \mu \mathrm { m } )$ 和中红外波段 $( 1 . 5 5 \sim 1 . 7 5 ~ \mu \mathrm { m } )$ 光谱反射率差异来识别冰川和积雪[19]；归一化主成分雪指数（NDPC-$S I$ )，通过对landsat波段主成分分析后两个最大$P C$ 值包含信息的差异识别积雪[19]；缨帽转换湿度（WET），采用BAIG等[21]的 $T M , E T M +$ 数据缨帽转换方法提取WETness数据，通过结合WETness与对应波段光谱反射率识别冰川和积雪（表2）。

2.2.2阈值与精度值通过精度分析，使用者能根据分类结果的精度，正确、有效地获取分类结果中的信息。精度评价主要有两种方案：第一种方案是Landsat产品与地面实测资料进行比较；第二种方案是与更高分辨率卫星影像或者航片来进行比较[22]在缺少站点的山区，实测数据缺乏且成本过高，且获取困难，因此本文采用第二种方案。全色波段与多光谱波段融合后空间分辨率为 $1 5 \mathrm { ~ m ~ }$ 的 $E T M +$ 数据比分辨率为 $3 0 \mathrm { ~ m ~ }$ 的TM数据多光谱波段优越4倍，

LandsatTM2001 LandsatETM+2001+ ↓大气校正和几何校正 大气校正和几何校正↓ √ ↓ 1 1  
NDSI NDSII WET NDPCSI 主要要素分类↓ ↓ + √ ↓阈值选择与精度值计算  
LandsatTM1990  
LandsatTM2000 1990—2016年积雪与冰川指数选择 面积变化  
LandsatTM2010  
LandsatETM+2016GDEMDEM气温数据 评估地形和气候因素对冰川和积雪面积变化的影响降水数据

表2冰川和积雪监测指数  
Tab.2 Glacier and snow monitoring indexes   

<html><body><table><tr><td>指数</td><td>计算公式</td></tr><tr><td>NDSI[3]</td><td>(TM2-TM5)/(TM2+TM5)</td></tr><tr><td>NDSII[19]</td><td>(TM3-TM5)/(TM3+TM5)</td></tr><tr><td>NDPCSI[19]</td><td>(1stPC-2ndPC)/(1stPC+2ndPC)</td></tr><tr><td>Landsat 5</td><td>0.1509×TM1+0.1973×TM2+0.3299×TM3+</td></tr><tr><td>WET[21]</td><td>0.3407×TM4-0.7112×TM5-0.4572×TM7</td></tr><tr><td>Landsat 8</td><td>0.1511×0L2+0.1973×0L3+0.3282×0LI4+</td></tr><tr><td>WET[3]</td><td>0.3407×0LI50-0.7117×0LI6-0.4559×OLI7</td></tr></table></body></html>

注： $T M$ 表示Landsat5的波段光谱反射率； $O L I$ 表示Landsat8的波段光谱反射率； $P C$ 代表主成分值

理论上可以用来评价精度。为了方便两种冰川和积雪图对比，将空间分辨率为 $1 5 \mathrm { ~ m ~ }$ 冰川和积雪图重采样成 $3 0 \mathrm { ~ m ~ }$ 的影像。利用混淆矩阵计算总精度检验阈值的合理性。

# 3 结果与分析

# 3.1指数阈值与精度值确定

通过人机交互式技术确定4个指数阈值的取值范围，为减少不必要的计算量，本文在各指数阈值范围内，以0.05为间隔，获取不同阈值的冰川和积雪图，统计其冰雪象元个数，分别与LandsatETM $^ +$ 冰川和积雪图进行对比确定精度最高的阈值。各指数最高精度的混淆矩阵展示在表3中。

通过总精度监测，WET在阈值0.8时精度最高为0.94；NDPCSI在阈值0.55时精度值最高为0.90;NDSII在阈值0.45时精度值最高为0.92;ND-$S I$ 在阈值0.4时精度值最高为0.91。WET具有最高的精度值（图3）。

# 3.2博格达峰地区冰雪面积的监测

根据在博格达峰地区反复验证冰川和积雪覆盖情况，得到精度值最高的指数WET。将WET指数应用于1990年、2000年、2010年、2016年的遥感数据，获取冰川和积雪覆盖图，计算冰川和积雪面积（表4)并比较面积变化情况（图4）。

结果表明：1990—2016年间冰川和积雪面积整体出现减少趋势，且速度明显加快。1990年9月\~1999年9月退缩率约 $7 . 3 2 \%$ ,2000年9月 $\sim 2 0 0 9$ 年9月退缩率约 $8 . 0 9 \%$ ,2010年9月 $\sim 2 0 1 6$ 年9月退缩率约 $6 . 1 7 \%$ ,1990一2016年冰川和积雪面积退缩率约 $2 0 . 0 7 \%$ 0

# 3.3影响冰雪面积变化的因素

根据1990一2016年冰川和积雪变化情况评估地形和气候因素对冰川和积雪面积变化的影响。在研究范围选取高程、坡度、坡向、山地阴影数据，分析博格达峰地区冰川和积雪随地形因素的变化规律。选取研究区周边3个气象站的多年年降水和年均气温数据，分析博格达峰地区冰川和积雪随气候因素的变化规律。

Tabl.3 Confusion matrix between Landsat and Landsat- $\mathbf { E T M + }$ glacier and snow cover classificatic   

<html><body><table><tr><td colspan="3">指数与阈值</td><td colspan="3">混淆矩阵</td><td>总精度</td><td>Kappa</td></tr><tr><td colspan="3"></td><td colspan="3">Landsat ETM +</td><td></td><td></td></tr><tr><td rowspan="3">NDSI =0.4</td><td>Landsat TM</td><td></td><td>冰川和积雪像元</td><td>非冰川和积雪像元</td><td>0.91</td><td></td><td>0.64</td></tr><tr><td></td><td>冰川和积雪像元</td><td>182 309</td><td>132 474</td><td></td><td></td><td></td></tr><tr><td>Landsat TM</td><td>非冰川和积雪像元</td><td>32 389</td><td>1 424 631 非冰川和积雪像元</td><td>0.92</td><td></td><td>0.68</td></tr><tr><td rowspan="3">NDSII =0.45</td><td></td><td>冰川和积雪像元</td><td>冰川和积雪像元 188 588</td><td>119 377</td><td></td><td></td><td></td></tr><tr><td></td><td>非冰川和积雪像元</td><td>26110</td><td>1 437 728</td><td></td><td></td><td></td></tr><tr><td>Landsat TM</td><td></td><td>冰川和积雪像元</td><td>非冰川和积雪像元</td><td></td><td>0.90</td><td></td></tr><tr><td rowspan="4">NDPCSI=0.55 WET=0.8</td><td></td><td></td><td>140 248</td><td></td><td></td><td></td><td>0.56</td></tr><tr><td></td><td>冰川和积雪像元 非冰川和积雪像元</td><td></td><td>101 654</td><td></td><td></td><td></td></tr><tr><td>Landsat TM</td><td></td><td>74 450 冰川和积雪像元</td><td>1 455 451 非冰川和积雪像元</td><td></td><td>0.94</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>0.69</td></tr><tr><td rowspan="3"></td><td></td><td>冰川和积雪像元</td><td>131 209</td><td>54 329</td><td></td><td></td><td></td></tr><tr><td></td><td>非冰川和积雪像元</td><td>45 821</td><td>1 540 444</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

![](images/0cf40a9971c0f73bedf73455763b0509ffc4798fca3aee6f19957880991dce4b.jpg)  
图3不同指数的冰川和积雪的监测结果

表3Landsat与Landsat- $\mathbf { \cdot E T M + }$ 冰川和积雪图分类结果混淆矩阵  
表41990一2016年博格达峰地区冰川和积雪面积变化  
Tab.4Snow and glacier area variation of Mount Bogda from1990—2016   

<html><body><table><tr><td>年份</td><td>冰川和积雪 面积／km²</td><td>时段</td><td>面积减少 量/km²</td><td>面积退缩 率/%</td></tr><tr><td>1990</td><td>127.10±0.01</td><td></td><td></td><td></td></tr><tr><td>1999</td><td>117.80 ±0.01</td><td>1990—1999 年</td><td>9.30±0.02</td><td>7.32</td></tr><tr><td>2009</td><td>108.27 ±0.01</td><td>2000—2009 年</td><td>9.53 ±0.02</td><td>8.09</td></tr><tr><td>2016</td><td>101.59 ±0.003</td><td>2010—2016年</td><td>6.68±0.01</td><td>6.17</td></tr><tr><td></td><td></td><td>1999—2016年 1990—2016 年</td><td>16.21 ±0.01 25.51±0.02</td><td>13.76 20.07</td></tr></table></body></html>

![](images/47f93eb366e154525d2416feec01c36b135bdae29435cc8478e6aeb57dadc22a.jpg)  
Fig 3Snow and glacier detection results of different index   
图4博格达连续的冰川和积雪变化  
Fig 4Continuous glacier and snow changes of Mount Bogda

3.3.1高程的影响为分析高程对冰川和积雪覆盖的影响，本文以 $2 5 \mathrm { ~ m ~ }$ 为间距对高程进行了分类，共202类。通过对研究区1990年9月 $\phantom { - } 2 0 1 6$ 年9月的冰川和积雪图与高程分类图叠加，并计算各高程2016年相对于1990年冰川和积雪的覆盖率变化。冰川和积雪覆盖率定义为积雪和冰川面积除以各高程研究区面积。用2016年减去1990 年冰川和积雪覆盖率代表多年冰川和积雪变化率，变化率大于0的部分表示冰川和积雪增加，反之，则是消融，计算结果如图5所示。

![](images/eeff1fd70f28894ef389e4d38ca98e3a130856c5dd3bf97a6e050cbe5a64c29f.jpg)  
图5冰川和积雪覆盖变化率与高程的关系  
Fig 5Variations of glacier and snow cover ratio with elevation

图5显示，博格达峰地区冰川和积雪覆盖率变化随海拔总体呈 $\mathbf { w }$ 型。 $2 ~ 5 0 0 \mathrm { ~ m ~ }$ 之前和 $4 ~ 5 0 0 \mathrm { ~ m ~ }$ 之后趋于平缓，冰川和积雪覆盖率基本不变。 $2 5 0 0 \sim$ $3 ~ 5 0 0 \mathrm { ~ m ~ }$ 海拔的冰川和积雪开始融化，消融率随海拔的增大而增大。 $3 \ 5 0 0 \sim 3 \ 8 0 0 \ \mathrm { m }$ 海拔，冰川和积雪消融变慢，消融率随海拔的增大而减少。 $3 ~ 8 0 0 \sim$ $4 ~ 0 0 0 ~ \mathrm { { m } }$ 海拔冰川和积雪消融速度随海拔增加而加快。 $4 0 0 0 \sim 4 5 0 0 \mathrm { ~ m }$ 冰川和积雪消融速度随海拔减缓。

博格达峰地区高海拔地区全年气温都较低能够满足冰川和积雪的温度条件，使得冰川和积雪覆盖的决定性条件变成降水，而新疆地区在高于 $2 5 0 0 \mathrm { ~ m ~ }$ 海拔的区域降水量随高程增加呈近似二次曲线类型，最大降水高度带在山腰（ $( 3 ~ 1 0 0 \sim 3 ~ 8 0 0 ~ \mathrm { m }$ ，在

$5 ~ 5 0 0 ~ \mathrm { m }$ 左右出现第二极大值带[23-24],降水抑制了冰川和积雪的消融。另一方面，随着海拔高度的增加，气温下降，水汽压下降、太阳辐射加强，既减少了温度引起的消融又增加了冰川和积雪的升华量[25]。3.3.2坡度的影响为了分析坡度对博格达峰地区冰川和积雪冻融的影响，本文以 $1 ^ { \circ }$ 为间距对坡度进行了分类，共90类。与前文高程对冰川和积雪覆盖的影响分析相似，对研究区1990年9月、2016年9月的冰川和积雪图与坡度分类图叠加得到冰川和积雪覆盖变化率，结果如图6所示。

![](images/6e3f7a7d581f3030b8f12db2d43fbad12780a9fe9633d1d67d8ef082c298cf2b.jpg)  
图6冰川和积雪覆盖变化率与坡度的关系 Fig 6Variations of glacier and snow cover ratio with slope

图6表明，博格达峰地区冰川和积雪变化率随坡度呈V型。坡度低于 $4 0 ^ { \circ }$ 的区域，冰川和积雪覆盖变化率总体随坡度增大而增大，坡度高于 $4 0 ^ { \circ }$ 的区域则随坡度增大而减小，最后趋于平稳。

冰川和积雪覆盖率随坡度呈现非线性变化，在$4 0 ^ { \circ }$ 前变率增大， $4 0 ^ { \circ }$ 度后变率减少。这种现象一方面可能是因为不同坡度条件下因正午太阳高度导致太阳辐射和气温差异，引起冰川和积雪升华和融化量不同。另一方面，在坡度低于 $4 0 ^ { \circ }$ 的区域冰川面积随坡度增加呈正态分布趋势[5],而博格达峰地区冰川和积雪主要分布于坡度低于 $4 0 ^ { \circ }$ 区域。

3.3.3坡向的影响为了分析坡向对博格达峰地区冰川和积雪冻融的影响，本文以 $2 ^ { \circ }$ 为间距对坡向进行了分类,为便于统计，把连续的坡向分为平地$\big ( \mathrm { ~ - ~ } 1 ^ { \circ } \big )$ 、正北( $3 3 7 . 5 ^ { \circ } \sim 3 6 0 ^ { \circ }$ ， $0 ^ { \circ } \sim 2 2 . 5 ^ { \circ }$ ）、东北（ $2 2 . 5 ^ { \circ } \sim 6 7 . 5 ^ { \circ } ;$ 、正东 $( 6 7 . 5 ^ { \circ } \sim 1 1 2 . 5 ^ { \circ } )$ 、东南（ $1 1 2 . 5 ^ { \circ } \sim 1 5 7 . 5 ^ { \circ } ;$ 、正南 $( 1 5 7 . 5 ^ { \circ } \sim 2 0 2 . 5 ^ { \circ } )$ 、西南$( 2 0 2 . 5 ^ { \circ } \sim 2 4 7 . 5 ^ { \circ } )$ 、正西 $( 2 4 7 . 5 ^ { \circ } \sim 2 9 2 . 5 ^ { \circ } )$ 、西北$( 2 9 2 . 5 ^ { \circ } \sim 3 3 7 . 5 ^ { \circ } ) 9$ 类。对1990年9月、2016年9月的冰川和积雪图与坡向分类图叠加得到冰川和积雪覆盖率，用2016 年减去1990 年冰川和积雪覆盖率代表多年冰川和积雪变化，结果如图7所示

![](images/c71ead5976967a02c28e560f5389613aea8bf837f354006c619431e7367d3edb.jpg)  
图7冰川和积雪覆盖变化率与坡向的关系

图7显示，博格达峰地区冰川和积雪覆盖率变化总体呈现出由北到南逐渐递减，平地区域的变化率较低。从北坡顺时针至西南坡，变化幅度不断减小，由西南坡至北坡逐渐增大,正北方向变化率最高，西南方向的变化率最低。

博格达峰地区冰川和积雪覆盖率变化随坡向（由西北向西南)呈现逐渐变小的趋势。这种现象可能是坡向影响水汽运动方向和太阳光照引起温度差异造成[26]。博格达峰地区位于盛行西风带,水汽主要来源于偏西方向，西南光照时间和太阳高度均大于东北向。水汽和太阳光照引起的冰川和积雪分布不均。

3.3.4山地阴影的影响为了分析山地阴影对博格达峰地区冰川和积雪冻融的影响，本文以2为间距对山地阴影灰度值进行了分类，共127类。对研究区1990年9月、2016年9月的冰川和积雪图与山地阴影分类图叠加得到冰川和积雪覆盖率，用2016年减去1990 年冰川和积雪覆盖率代表多年冰川和积雪变化，结果如图8所示。

图8表明，博格达峰地区冰川和积雪覆盖变化率随坡度上下波动，整体上随山地阴影灰度值增加而消融速度变缓。但山地阴影灰度值100左右冰川和积雪消融最快，山地阴影灰度值230左右冰川和积雪消融缓慢，规律性不明显。因此，我们可以推测山地阴影与冰川和积雪覆盖率变化关系不显著，对冰川和积雪冻融的影响较小。

3.3.5气候的影响为了分析气候对博格达峰地区冰川和积雪的影响，本文结合博格达峰地区边缘的奇台、吐鲁番、乌鲁木齐3个气象站的降水年距平和年均温变化数据（http：//data.cma.cn/）,推测出博格达峰地区降水年距平和年均气温变化量（图9)。张明军等[27]认为气温每升高 $1 \ \mathrm { { ^ { \circ } C } }$ 需要降水量增加 $47 \%$ 或 $56 \%$ 才能弥补由升温引起的冰川消融。本文选取3个站点的平均升温率大约在 $0 . 3 0 \mathrm { ~ } ^ { \circ } \mathrm { C }$ ：（204号 $\left( 1 0 \mathrm { ~ a ~ } \right) ^ { - 1 }$ 左右，而降水增加幅度只有 $1 3 ~ \mathrm { \ m m }$ ·（10a）-左右，降水量增加远不足以弥补升温引起的消融。何毅等[5利用Morlet小波分析研究表明东天山博格达峰地区在1972—2013年处于气温偏高降水偏少期。因此，可以推断气温对博格达峰地区冰川和积雪面积变化影响较为显著。

![](images/69e2bec28e42da3f6e636c37ad9b30adbff06c66bc7a2eded57011038b3b1ca5.jpg)  
Fig7Variations of glacier and snow cover ratio with aspec   
图8冰川和积雪覆盖变化率与山地阴影的关系  
Fig 8Variations of glacier and snow cover ratio with hillshade

# 4讨论

本研究提出基于指数的冰雪监测方法，通过对博格达峰地区冰川和积雪情况监测反复验证NDSI、NDSII、NDPCSI、WET的适用性。本研究中，WET指数被证明是最准确的指标，但WET和NDSI的准确性差异极小，很容易受地物分布状况、云量等因素的影响,导致准确性发生变化。SIBANDZE 等[20]在研究祁连山的积雪时发现NDPCSI监测积雪比NDSI有更好的精度。但本文NDPCSI监测最高精度是0.9,低于NDSI、NDSII、WET的最高精度。在SAT-$\mathrm { I R } ^ { [ 3 ] }$ 的研究中也出现了类似的情况,这可能是受数据类型或冰雪的差异影响。

本文使用WET指数监测博格达峰地区冰川和积雪变化时发现1990—1999年、2000—2016年的退缩率与何毅等[2,5]的研究结果基本一致,表明使用WET指数监测博格达峰地区冰川和积雪是可行的。而差异的出现可能是受研究区域范围、冰川数目和分布区域的差异等的影响。对比近几年我国西部冰川变化研究成果：祁连山中段冰川年退缩率为$0 . 4 6 \% \cdot \mathrm { ~ a ~ } ^ { - 1 [ 2 8 } .$ ；阿尔金山地区冰川年退缩率为$0 . 4 2 \% \cdot \mathrm { ~ a ~ } ^ { - 1 [ 2 9 }$ ;喜马拉雅山东段洛扎冰川年退缩率为 $0 . 6 0 \% \cdot \mathrm { ~ a ~ } ^ { - 1 [ 3 0 ] }$ ;克拉昆仑山克勒青河流域冰川年退缩率为 $0 . 2 2 \% \cdot \mathrm { ~ a ~ } ^ { - 1 [ 3 1 ] }$ 等。结果表明,在全球变暖的大背景下，博格达峰地区冰川和积雪变化趋势与中国西部其他冰川所反映出来的大趋势相吻合，但退缩速率上存在差异，这可能和冰川面积、盛行风影响等有关。

![](images/ba2b0098f639ad9c5c265c5bf84296877f23ea9c247e89058c805b1bfd0c8677.jpg)  
图9年均气温与年降水距平变化 Fig 9 Variation of average annual temperature and precipitation anomaly

博格达峰地区冰川和积雪面积变化影响因素主要包括地形和气候两个方面。张明军等[27]认为气候是影响博格达峰地区冰川和积雪面积变化的主要因素，但本文在分析博格达峰地区附近的奇台气象站的气温、降水变化时发现1990一1999 年的平均年均温为 $5 . 6 3 ~ \mathrm { { ^ { \circ } C } }$ ,平均年降水量为 $2 2 1 . 1 \ \mathrm { m m }$ ,1999—2013 年的平均年均温为 $5 . 5 7 \ \mathrm { ^ { \circ } C }$ ,平均年降水量为$1 9 6 . 8 5 \ \mathrm { m m }$ 。冰川和积雪面积退缩与温度和降水变化线性关系不明显。因此地形因素在博格达峰地区冰川和积雪面积变化中有着重要作用。尽管气温是冰川和积雪冻融的关键因素，但坡度、坡向等也有重要的影响[32]。气候因素与地形因素结合,更多的太阳辐射和更少的降水量能引起更多的冰川和积雪融化和升华。而山地阴影并没有像预期的那样影响冰川和积雪冻融，这意味着太阳辐射并不是影响博格达峰地区冰川和积雪的重要因素。

# 5结论

本文利用博格达峰地区1990—2016年的Land-satTM、ETM $^ +$ 数据分析了NDSI、NDSII、NDPCSI、WET4个指数的适用性，以及地形和气候因素对冰川和积雪冻融的影响，得到了以下主要结论：

（1）WET能很好的替代NDSI和NDSII精确监测博格达峰地区冰川和积雪。在博格达峰地区反复验证NDSI、NDSII、NDPCSI、WET的适用性，4个指数的精度表现为： $W E T > N D S I I > N D S I > N D P C S I _ { \circ }$

(2）1990一2016年，博格达峰地区冰川和积雪面积持续减少，且速度呈增加趋势。1990一1999 年冰川和积雪面积退缩率约 $7 . 3 2 \%$ ;2000—2009 年冰川和积雪面积退缩率约 $8 . 0 9 \%$ ;2010—2016 年冰川和积雪面积退缩率约 $6 . 1 7 \%$ 。

(3)冰川和积雪气候和地形因素呈现出不同的特点。地形要素中，冰川和积雪覆盖变化率总体随海拔增大而增大，随坡度增大呈现V型分布，随坡向变化由西南向东北方向减小。气候要素中，气温是冰川和积雪覆盖变化的主要因素，降水影响较弱。

# 参考文献(References）

[1]ARMSTRONG RL,BRUN E.Snow and climate:Physical processes,surface energy exchange and modeling[J].Polar Research, 2010,29(3):461-462.   
[2］胡顺军,陈永宝,朱海.古尔班通古特沙漠南缘融雪水土壤入 渗量［J].应用生态学报，2015,26（4）：1007-1015.［HUSunjun,CHEN Yongbao,ZHU Hai.Soil infiltration of snowmelt water in the southern Gurbantunggut Desert,Xinjiang,China[J].Chinese Journal of Applied Ecology,2015,26(4):1007 -1015.]   
[3]SATIR O.Comparing the satelite image transformation techniques for detecting and monitoring the continuous snow cover and glacier in Cilo Mountain chain Turkey[J].Ecological Indicators,2016, 69:261 -268.   
[4]LI Z X,HE Y Q,PU T,et al. Changes of climate,glaciers and runoffin China's monsoonal temperate glacier region during the last several decades[J].Quaternary International,2010,218（1-2）： 13-28.   
[5］何毅,杨太保,陈杰,等.1972—2013年东天山博格达峰地区冰 川变化遥感监测[J].地理科学,2015,35（7）:925－932.[HE Yi,YANG Taibao,CHEN Jie,et al. Remote sensing detection of glacier changes in Dong Tianshan Bogda Region in 1972—2013 [J].Scientia Geographica Sinica,2015,35（7）:925-932.]   
[6]FAUSTO R S,AS D,ANTORF JA,et al. Greenland glacier sheet melt area from MODIS（2000—2014）[J]. Geological Survey of Denmark & Greenland Bulletin,2015,（33）：57-60.   
[7]RITTGER K,PAINTER T H,DOZIER J. Assessment of methods for mapping snow cover from MODIS[J]. Advances in Water Resources,2013,51(1) :367 -380.   
[8]YIN D,CAO X,CHEN X,et al.Comparison of automatic thresholding methods for snow-cover mapping using Landsat TM imagery [J].International Journal of Remote Sensing,2013,34（19）： 6529 -6538.   
[9]RAUP B,KAAB A,KARGEL JS,et al.Remote sensing and GIS technology inthe global land glacier measurements from space （GLIMS）project[J]. Computers & Geosciences,2007,33（1）: 104 - 125.   
[10]KARIMI N,EFTEKHARI M,FARAJZADEH M,etal.Use of multitemporal satellite images to find some evidence for glacier changes in the Haft-Khan glacier,Iran[J].Arabian Journal of Geosciences, 2015,8(8) :5879 -5896.   
[11] MAHER A I,TREITZ P M,FERGUSON M A D.Can landsat data detect variations in snow cover within habitats of arctic ungulates ? [J].Wildlife Biology,2012,18(1）:75-87.   
[12]BURNS P,NOLIN A. Using atmospherically-corrected Landsat imagery to measure glacier area change in the Cordillera Blanca,Peru from 1987 to 2010[J]. Remote Sensing of Environment,2014,140 (1) :165 -178.   
[13]DURAN-ALARCON C,GEVAERT C M,MATTAR C,et al. Recent trends on glacier area retreat over the group of Nevados CaullarajuPastoruri （Cordillera Blanca,Peru）using Landsat imagery[J]. Journal of South American Earth Sciences,2015,（59):19 -26.   
[14]SANKEY T,DONALD J,MCVAY J,et al. Multi-scale analysis of snow dynamics at the southern margin of the north American continental snow distribution[J].Remote SensingofEnvironment, 2015,169(1) :307 -319.   
[15]WALTERS R D,WATSON K A,MARSHALL HP,et al. A physiographic approach to downscaling fractional snow cover data in mountainous regions[J]. Remote Sensing of Environment,2014, 152:413 - 425.   
[16］孙永猛,丁建丽,瞿娟.基于 NDSI-Albedo 特征空间的 MODIS 积雪丰度信息反演方法研究[J].干旱区地理,2013,36（3）： 521-527.[SUN Yongmeng,DING Jianli,ZHAI Juan. Inversion of the MODIS snow abundance ratio based on NDSI-Albedo feature space[J」.Arid Land Geography,zUi5,so(5） :5£1 -521.   
[17］孙志群,刘志辉,邱冬梅.基于HJ-1B 数据的雪盖提取方法研 究——以军塘湖流域为例[J].干旱区地理,2012,35（1)： 125-132.[SUN Zhiqun,LIU Zhihui,QIU Dongmei.Methods of extracting snow cover information based on HJ-1B data:A case of the Juntanghu watershed[J].Arid Land Geography,2012,35（1）： 125 -132.]   
[18]PAN P,SARUTA K,TERATA Y,et al. Observations for snow cover detection in Akita via thecombinationof normalized difference vegetation index and normalized diference snow index[J].Transactions of the Japan Society for Aeronautical & Space Sciences Aerospace Technology Japan,2014,12(ists29）:1 -7.   
[19]KHOPKAR P S,JAWAK S D,LUIS A J. Multisource classification and pattern recognition methods for polar geospatial information extraction using WorldView-2 data[J]. Proceedings of SPIE-The International Society for Optical Engineering,2016:98801R.   
[20] SIBANDZE P,MHANGARA P,ODINDI J,et al.A comparison of normalised difference snow index（NDsI）and normalised difference principal component snow index（NDPCSI） techniques in distinguishing snow from related cover types[J]. South African Journal of Geomatics,2014,3(2）:197 -209.   
[21] BAIG M H A,ZHANG L,TONG S,et al.Derivation of a tasselled cap transformation based on Landsat 8 at-satelite reflectance[J]. Remote Sensing Letters,2014,5(5）:423 -431.   
[22］陈晓娜,包安明,张红利,等.基于混合像元分解的 MODIS 积 雪面积信息提取及其精度评价——以天山中段为例[J].资源 科学,2010,32（9）:1761-1768.[CHEN Xiaona,BAO Anming, ZHANG Hongli ,et al. A study on methods and accuracy assessment for extracting snow covered areas from MODIS images based on pixel unmixing：A case on the middle of the Tianshan Mountain [J].Resources Science,2010,32(9）:1761-1768.]   
[23］赵成义,施枫芝,盛钰,等.近50a来新疆降水随海拔变化的区 域分异特征[J].冰川冻土,2011,33(6):1203－1213.[ZHAO Chengyi,SHI Fengzhi,SHENG Yu,etal.Regional differentiation characteristics of precipitation changing with altitude in Xinjiang region in recent 5O years[J]. Journal of Glaciologyand Geocryology,2011,33(6):1203-1213.]   
[24］张正勇,何新林,刘琳,等.中国天山山区降水空间分布模拟及 成因分析［J]．水科学进展,2015,26（4）：516.［ZHANG Zhengyong,HE Xinlin,LIULin,etal.Patial distributionof rainfall simulation and the cause analysis in China's Tianshan Mountains area[J].Advances in Water Science,2015,26(4）:516.   
[25］胡伟杰,刘海隆,王辉,等.地形对天山积雪冻融变化的影响分 析[J].冰川冻土,2016,38（5）:1227-1232.[HU Weijie,LIU Hailong,WANG Hui,et al.Analysis of the terrain effect onsnow cover accumulating and melting in the Tianshan Mountains[J]. Journal of Glaciologyand Geocryology,2016,38（5）: 1227- 1232]   
[26］王宏伟,黄春林,郝晓华,等.北疆地区积雪时空变化的影响因 素分析[J].冰川冻土,2014,36(3):508-516.[WANG Hongwei,HUANG Chunlin,HAO Xiaohua,et al.Analyses of the spatiotemporal variations of snow cover in north Xinjiang[J].Journal of Glaciology and Geocryology,2014,36(3）:508-516]   
[27］张明军,王圣杰,李忠勤,等.近50 年气候变化背景下中国冰 川面积状况分析[J].地理学报,2011,66（9）：1155－1165. [ZHANG Mingjun,WANGShengjie,LI Zhongqin,etal.Variation of glacier area in China against the warming in the past 5O years [J].Acta Geographica Sinica,2011,66(9）:1155-1165.]   
[28］陈辉,李忠勤,王璞玉，等.近年来祁连山中段冰川变化[J].干 旱区研究,2013,30（4）:588-593.[CHEN Hui,LI Zhongqin, WANG Puyu,et al.Change of glaciers in the central Qilian Mountain[J].Arid Zone Research,2013,30(4):588-593.]   
[29］祝合勇,杨太保，田洪阵.1973—2010 年阿尔金山冰川变化 [J].地理研究,2013,32（8）:1430-1438.［ZHU Heyong, YANG Taibao,TIAN Hongzhen.Glacier variation in the Altun Mountains from 1973 to 2010[J].Geographical Research,2013, 32(8):1430 -1438.]

[30］李治国，姚檀栋，叶庆华，等.1980—2007年喜马拉雅东段洛扎地区冰川变化遥感监测［J].地理研究，2011，30（5）：939-

952.［LI Zhiguo,YAO Tandong,YE Qinghua,et al.Monitoring glacial variations based on remote sensing in the Luozha region, eastern Himalayas，1980—2007［J]．Geographical Research, 2011,30(5):939-952.]

[31］许艾文,杨太保，王聪强,等.1978—2015 年喀喇昆仑山克勒青 河流域冰川变化的遥感监测[J].地理科学进展,2016,35（7)： 878-888.[XU Aiwen,YANG Taibao,WANG Congqiang,et al. Monitoring glacial variations based on remote sensing in the Luozha region,eastern Himalayas,1980—20O7［J].Geographical Research,2016,35(7) :878-888.]

[32]ZHAOJ,SHIYF,HUANGYS,etal.Uncertainties of snow cover extraction caused by the nature of topography and underlying surface[J].Journal of Arid Land,2015,7(3):1-11.

# Remote sensing monitoring of the change of glacier and snow cover and its influencing factors in Mount Bogda

ZHOUYuan-gang12，ZHAORui-feng122，Zhang Li-hua122，ZHAO Min12 (1College of Geographyand Environment Science,NorthwestNormal University,Lanzhou73Oo7o,Gansu,China; 2Gansu Engineering Research CenterofLandUtilizationand ComprehensionConsolidation,Lanzhou73oo70,Gansu,China)

Abstract：Glaciers and snow cover are indicators of global warming and important water resources for human survival and development in arid regions.Since 19OOs,the glacierand snow area has generally been shrinking as global warming intensifies,which seriouslyaffects people'slife,socialandeconomic activities inthe relatedareas.Particularly,inthe surounding areasof Mount Bogda whichlocated inthearidareaof northwest China,this kindof effects is much more significant.By strengthening the monitoring the change of glacierand snow cover,we can notonlyunderstand the characteristicsand trends of glacier and snow change,but also reveal the responseof glacier and snow to climate change,and thus to posibly predict future changes of glacier and snow.We chose Mount Bogda at Fukang County,Xinjiang,China as the research area and obtained remote sensing images of Landsat 5and Landsat 8,DEM data and surounding temperature and precipitation data from 1990 to 2016.Firstly,we employed the satelite images ofLandsat 5and Landsat 8 to calculate valueof Normalized Difference Snow Index（NDSI),Normalized Diference Snow-Glacier Index（NDSII）,Normalized Diffrence Principle Component Snow Index（NDPCSI）and Tasseled Cap Wetness transformation （WET）and to analyze the respective ability to detect glacier and snow.Secondly,we used WET with high accuracy toobtain glacier and snow cover data in 1990,2000,2010 and 2016 respectively and analyzed the changes of glacierand snow cover.Finally,combining with the temperaturedata and the terraindata of the study area,we exploredthe relationship between the change of snow and glacier area of Mount Bogda and the terrain and climate in this area.The results showas follows:（1）The WETindex has a higher overallaccuracy than the NDSI index,which can replace NDSI and NDSII to detect and monitor the glacier and snow area changes in Mount Bogda.（2）The area of snow and glacier continued to shrink in Mount Bogda.From 199O to 2O16,the snow and glacier area was reduced by $2 0 . 0 7 \%$ ,and the annual reduction rate continues to increase.（3）The influence of temperature and slope on the change of snow and glacier area is strong,whilethe influence of mountain shadow and altitude is weak.And the rising temperatures is the main factorof the decreased area of snow and glacier.The research results could provide theoretical support and decision reference for accurate extraction of glacier and snow cover information in Mount Bogda area and for the sustainable economy development in the surrounding areas.

Key words:Landsat；index；variations of glacier and snow；Mount Bogda