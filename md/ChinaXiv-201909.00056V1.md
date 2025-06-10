# 基于Sentinel-2数据的干旱区典型绿洲植被叶绿素含量估算

顾峰1,2.3，丁建丽1,2.3，葛翔宇1,2.3，高石宝4，王敬哲1,2,.3（1．新疆大学资源与环境科学学院,新疆 乌鲁木齐830046；2．新疆大学智慧城市与环境建模自治区普通高校重点实验室,新疆 乌鲁木齐830046;新疆大学绿洲生态教育部重点实验室,新疆 乌鲁木齐830046；4．浙江大学地球科学学院,浙江杭州310027摘要：以渭干河一库车河绿洲(渭一库绿洲)为研究区,采用在机器学习方面具有明显优势的随机森林回归算法,对绿洲内的4种典型植被（棉花、芦苇、杨树、大枣)叶片的叶绿素相对含量(soil and plant analyzer development,SPAD)进行估算和验证。首先基于“红边"处光谱信息丰富的哨兵2号（Sentinel-2)影像和由其衍生的一阶微分、二阶微分影像各提取23种对叶绿素敏感的宽波段光谱指数,加入3种影响植物生长的土壤参量（土壤含水量，土壤有机质,土壤电导率)作为影响叶片 SPAD 的特征变量,再根据以上特征变量对每种植被叶片各建立3种方案的SPAD 估算模型,从而实现对绿洲内植被叶绿素的监测。结果表明： $\textcircled{1}$ 影像经一阶微分再提取的植被指数相比原位光谱植被指数，在SPAD估测模型中起到了更重要的作用,在随机森林算法的重要性排序中位居前列； $\textcircled{2}$ 4种植被叶片的 SPAD估测模型都取得了不错的效果,芦苇叶片尤为显著,确定系数 $( R ^ { 2 } )$ 达到了0.926; $\textcircled{3}$ 分析对比3种方案下模型预测能力，方案3(包含土壤参量)的预测能力卓越 $\left[ 2 . 1 4 3 < \right.$ 相对百分比偏差 $( R P D ) < 2 . 6 9 2 \$ ，其预测能力排序为：方案 $3 >$ 方案 $1 >$ 方案2,土壤属性和模型预测结果有较强的非线性相关。Sentinel-2数据具有理想的估算绿洲植被叶绿素含量的潜力,提供了一种高效、低成本、潜在高精度的方案来估算叶绿素含量,可为干旱区绿洲农业、生态系统实现更有效的保护和管理提供参考。

关键词：绿洲；Sentinel-2数据；SPAD；叶绿素；植被指数；随机森林；新疆

叶绿素是光合作用过程中吸收光能的植被色素，更是植被(尤其在衰老期)光合作用能力的指征，已成为监测绿洲植被生长健康状况的重要的生理参数[1-2]。大量研究表明植被叶片的叶绿素相对含量(SPAD)可直接用以衡量其实际叶绿素含量的高低[3-7]。植被是绿洲生态系统的重要组成成分，获取SPAD这一植被典型的生化参数并进行系统性研究,可以及时掌握绿洲生态系统的发展动向[8] C十旱区绿洲植被叶片叶绿素含量及时准确地估算及诊断，对制定科学的水肥管理措施及进行干旱状况评估具有重要的现实意义。受叶片中叶绿素吸收作用的影响，农作物叶片在“红边”位置( $6 9 0 \sim 7 8 0$ nm)存在着明显的光谱响应，这使得利用遥感技术对SPAD进行遥感估算成为了可能。常见的"红边”参数包括:红边位置、红边幅值、红边峰值等[9]。目前，MODIS、Landsat $\phantom { 0 } \cdot \mathrm { H J } - 1$ 、ASTER、QuickBird等多光谱遥感数据已成功应用于植被理化参数的监测[10-13],但它们通常缺少“红边”信息,这对植被SPAD的遥感估算是极为不利的。欧洲太空局于2015年6月发射的哨兵2号(Sentinel-2)多光谱传感器，具有最高可达 $1 0 \mathrm { ~ m ~ }$ 分辨率、可覆盖13个光谱波段的遥感数据[14]。此外,Sentinel-2数据也是目前唯一一个在“红边”范围含有3个波段的多光谱数据,对监测植被健康信息非常有效。Clevers 等[15]对3种多光谱影像的“红边”指数组合进行了比较，基于Sentinel-2的大豆红边叶绿素指数（CIre）与其叶绿素浓度具有极高相关性( $R ^ { 2 } = 0 . 9 4 { \mathrm { \Omega } } _ { , } ^ { \cdot }$ ）。Ver-relst 等[16使用了4 种机器学习算法在 Sentinel-2的"红边"范围内估算植被叶绿素， $R ^ { 2 }$ 达到了0.99。此外,李粉玲等[17]使用模拟高分1号的遥感光谱指数在关中地区建立了冬小麦叶片SPAD估算模型，指出基于随机森林算法构建的模型具有最优精度。这些研究成果证明了Sentinel-2的空间分辨率和光谱特性在SPAD遥感估算上的可行性，与机器学习算法的结合克服了样点数量较少、数据分布不均等不利条件。然而，上述研究多在非干旱地区开展，且大多只利用单一红边参数建模,没有深入考虑土壤属性的多种重要协变量，对干旱区绿洲植被SPAD的建模效果有待进一步的考证。

基于此，本研究以渭干河一库车河绿洲（渭一库绿洲)为研究靶区，基于Sentinel-2数据和原位SPAD数据,设立3种组合方案并利用随机森林算法构建了区域棉花、芦苇、大枣、杨树4种典型植被叶片的 SPAD估算模型，以期为干旱区植被叶绿素含量的无损监测以及当地精准农业提供数据支持和技术支撑。

# 数据与方法

# 1.1 研究区概况

渭一库绿洲 $( 4 0 ^ { \circ } 5 0 ^ { \prime } \sim 4 1 ^ { \circ } 3 8 ^ { \prime } \mathrm { N } , 8 1 ^ { \circ } 2 6 ^ { \prime } \sim 8 3 ^ { \circ } 1 7 ^ { \prime } \mathrm { E } )$ （2位于新疆南部阿克苏地区，天山南脉中段塔里木盆地北缘，塔里木河中游(图1）。绿洲涵盖库车、沙雅、新和3县，是典型的洪积－冲积倾斜平原,境内北高南低,平均海拔 $9 7 1 \mathrm { ~ m ~ }$ 。气温日较差大，2001一2016 年间年平均气温 $1 0 . 3 \sim 1 4 . 4 ~ \mathrm { ^ { \circ } C }$ ,最高气温$4 1 . 5 ~ \mathrm { { ‰} }$ ；潜在蒸发量 $2 ~ 4 2 0 ~ \mathrm { m m }$ ,多年平均降水量为$4 3 \ \mathrm { m m }$ ,蒸降比约54:1，降水季节性差异很大，多集中于6一7月，其他月份降水大幅减少，属于干旱与极端干旱区;土壤主要为潮土、草甸土、风沙土、盐土[18-19]。区域内主要水系为渭干河、库车河、木扎提河、英达雅河及塔里木河,水域多建有平原水库，如库车跃进水库、沙雅齐满水库。绿洲境内为该地主要农作物产区，人工植被以棉花（Gossypium hirs-sittum）杨树（PopulusL）枣树（Ziziphus jujube）为主，天然植被以芦苇（Phragmitesaustralis）、骆驼刺（Alhagisparsifolia）花花柴（Karelinacaspica）怪柳（Tamarixchinensis）盐爪爪（Kalidiumfoliatum）等耐盐植被为主[20] 。

# 1.2 实测数据

2017年10月8一19日，在渭一库绿洲进行了野外实地调查。依据研究区地表形态和地貌差异以及样点分布的均匀性，对绿洲范围内的66个远离其他明显特征(道路，河渠)的点进行采样，坐标通过GPS定位并记录。每个采样点测取了叶绿素相对含量（SPAD）、表层土壤有机质（soilorganicmatter,SOM）、土壤含水量（soil moisturecontent,SMC）以及土壤电导率（electricalconductivity，EC）等数据。

![](images/d18b8b91798c3cfed1e813766b90ef3fe6684605786c738fad263f1d087febab.jpg)  
Fig.1The study area and sampling sites

1.2.1植被叶片 SPAD 值使用日本美能达公司生产的 SPAD 快速叶绿素测定仪，从东、西、南、北方向以及植株冠层的上、中、下，采集25片健康、规则的叶片测定SPAD值，并将25个测定值的算术平均值作为对应采样点特定植被叶片的SPAD值。

1.2.2植被叶片光谱植被叶片光谱数据由 ASDFieldSpec4测量便携式光谱仪测定，测定时利用植被探头与叶片夹和光谱仪自带光源，将每个样点(25片)的每片叶片测定2次，注意避开叶脉，保证叶片平整且被探测的面积相同。采集结束后，对光谱数据进行 Savitaky-Golay 滤波，以去除噪声并对光谱曲线进行平滑，然后取均值得到该样点的叶片光谱[21]

1.2.3土壤含水量对每个采样点使用5点采样法采集5个 $1 5 \ \mathrm { c m }$ 土层的土样，共采集330个土壤样品，记录周边环境信息。在实验室，将土壤样本置于 $1 0 5 \ \mathrm { ^ \circ C }$ 的恒温烘干箱内烘 $^ { 4 8 \mathrm { ~ h ~ } }$ ,然后对同一采样点土壤水分实测值求平均值，得到该采样点的真实土壤含水量。

1.2.4土壤有机质将采集的土样在实验室自然风干、研磨，并剔除土样中的杂质后过 $0 . 2 5 \ \mathrm { m m }$ 孔径筛。采用重铬酸钾容量法-外加热法（油浴)测定分选好的土壤有机质含量。

1.2.5土壤电导率每组土样称取3份样品，每份为 $0 . 5 \mathrm { ~ g ~ }$ ,将每份样品置于消煮管中,用去离子水定标至 $2 0 ~ \mathrm { m L }$ ,将所有消煮管放置在摇床上，震动处理$^ { \mathrm { ~ 1 ~ h ~ } }$ ,静置 $3 0 \ \mathrm { m i n }$ ，采用德国Wissenschaftlich Tech-nischeWerkstätten公司生产的Cond7310电导仪测定，并将3份样品的电导率求平均，得到该组土样的电导率[20]

# 1.3 影像数据

根据实地采样时间和采样范围，选择2017年10月14日的2景Sentinel－2A影像（以下简称S2A），数据来源于欧洲太空局（http://www.esa.int/ESA）。影像基本无云，质量高。获得的S2A多光谱影像数据类型是Level-1C，是已经过几何校正的反射率数据（表1）。

表1本研究使用的S2A数据  
Tab.1 S2A data used in this study   

<html><body><table><tr><td>影像编号</td><td>获取日期</td><td>获取波段 卫星 数</td></tr><tr><td>N0205_R062_T44TPL_20171014T052639 2017-10-14</td><td></td><td>S2A 13</td></tr><tr><td>N0205_R062_T44TPM_20171014T052639 2017 -10 -14</td><td></td><td>S2A 13</td></tr></table></body></html>

1.3.1图像预处理使用ENVI5.5软件对影像进行地形校正、辐射定标和Flaash大气校正，获得其反射率数据。从表2和图2可以看出，S2A波段的空间分辨率不一致，本文使用3次卷积内插方法将大气校正后的波段重采样至效果最好的 $1 0 \mathrm { ~ m ~ }$ 空间分辨率。最后，使用GS（gram-schmidt pan sharpe-ning)融合方法将2幅影像拼接,并按照研究区范围进行裁剪。

1.3.2植被影像反射率的提取和精度使用大气校正处理后的影像，其植被光谱显示了绿色植被光谱的典型趋势（图2）。蓝波段( $4 9 0 \ \mathrm { n m } \cdot$ )和红波段（ $6 6 5 \ \mathrm { n m } \cdot$ )显示出2条吸收带，即光辐射光合作用形成2个叶绿素吸收层;在绿波段( $5 6 0 \ \mathrm { n m } ,$ )下小的反射峰代表了绿叶植物叶绿素对绿光的强烈反射效应;在 $7 0 5 \sim 7 8 3 ~ \mathrm { \ n m }$ 范围内，“红边”明显并且在近红外波段( $\mathrm { 8 6 5 ~ n m }$ )形成了更高的反射峰。利用大

# 表2 S2A数据信息

Tab.2Spectral bands and resolutions of S2A sensors   

<html><body><table><tr><td rowspan="2">波段</td><td colspan="2">S2A</td><td rowspan="2">空间分 辨率/m</td></tr><tr><td>中心波长/nm</td><td>波段宽度/nm</td></tr><tr><td>海岸波段(B1)</td><td>443.9</td><td>27</td><td>60</td></tr><tr><td>蓝波段(B2)</td><td>496.9</td><td>98</td><td>10</td></tr><tr><td>绿波段（B3）</td><td>560.0</td><td>45</td><td>10</td></tr><tr><td>红波段(B4)</td><td>664.5</td><td>38</td><td>10</td></tr><tr><td>植被红边1波段(B5)</td><td>703.9</td><td>19</td><td>20</td></tr><tr><td>植被红边2波段(B6)</td><td>740.2</td><td>18</td><td>20</td></tr><tr><td>植被红边3波段(B7)</td><td>782.5</td><td>28</td><td>20</td></tr><tr><td>近红外波段(B8)</td><td>835.1</td><td>145</td><td>10</td></tr><tr><td>近红外波段(B8A)</td><td>864.8</td><td>33</td><td>20</td></tr><tr><td>水汽波段（B9）</td><td>945.0</td><td>26</td><td>60</td></tr><tr><td>卷云波段(B10)</td><td>1 373.5</td><td>75</td><td>60</td></tr><tr><td>短波红外1(B11)</td><td>1 613.7</td><td>143</td><td>20</td></tr><tr><td>短波红外2(B12)</td><td>2 202.4</td><td>242</td><td>20</td></tr></table></body></html>

![](images/433a0915f78f7bab671d9db65f7e28542755a18a88d2f0184ec247bf344cbd82.jpg)  
图2大气校正前后的植被像元反射率 Fig.2Reflectance of vegetation pixels before and after correction

气校正模型减弱了大气对遥感影像的影响，恢复了植被光谱曲线的典型趋势，

根据现场测量的GPS坐标，将位于S2A中的采样点控制在一个像元中。采样点的GPS坐标位于两个或多个像素的边界处，将相邻像元的光谱反射率的平均值作为样本点的影像反射率；坐标位于像元的中心位置，将像元的光谱反射率认定为样本点的影像反射率。如图3所示，S2A每组波段光谱响应效果较好的位置并不在波段中心波长位置处，因此要将样本点的光谱仪实测反射率重采样，与S2A各波段光谱响应较好的波长位置匹配，然后根据该点的影像反射率，按如下公式求出建立植被指数所需各波段的反射率相对误差：

$$
E _ { i } = \left| \frac { R _ { i a } - R _ { i b } } { R _ { i a } } \right| \times 1 0 0 \%
$$

![](images/2c1b76de3a609d4cfbd2fc462b88166f54a2741d78a529ffb50d94880c8b741a.jpg)  
图3S2A影像的波谱响应关系  
Fig.3Spectral response relationship of S2A images

式中： $E _ { i }$ 为第 $\mathbf { \chi } _ { i }$ 波段的相对误差； $R _ { i a }$ 是第 $i$ 波段对应的实测光谱反射率； $R _ { i b }$ 是第 $i$ 波段对应的大气校正后的光谱反射率[22]。结果表明,图像处理可以获得接近实测的叶片光谱（表3），这为后续分析提供了保证。

表3植被叶片光谱反射率与实测反射率间的相对误差  
Tab.3Relative errors between vegetation canopy spectral   

<html><body><table><tr><td colspan="4">reflectance and measured reflectance /%</td></tr><tr><td>植被</td><td>B2</td><td>B3 B4</td><td>B5</td></tr><tr><td>芦苇</td><td>14.07</td><td>36.47</td><td>2.07 3.86</td></tr><tr><td>棉花</td><td>17.31</td><td>22.97</td><td>16.14 11.25</td></tr><tr><td>大枣</td><td>12.48</td><td>28.62 7.83</td><td>10.51</td></tr><tr><td>杨树</td><td>19. 77</td><td>27.83</td><td>35. 14 7.63</td></tr><tr><td>植被</td><td>B6</td><td>B7</td><td>B8 B8A</td></tr><tr><td>芦苇</td><td>10.86</td><td>2.14</td><td>2.83 10.29</td></tr><tr><td>棉花</td><td>9.14</td><td>6.77 8.52</td><td>9.37</td></tr><tr><td>大枣</td><td>8.32</td><td>6.98 5.24</td><td>8.73</td></tr><tr><td>杨树</td><td>9.97</td><td>12.70</td><td>15.40 10.50</td></tr></table></body></html>

1.3.3构建和选择植被指数植被指数是将遥感影像上不同波段的光谱反射率使用线性或非线性组合，得到反映植被某种特征信息的指数。植被叶片光谱曲线在“红边”范围出现的急速上升的陡坡，是一阶导数光谱曲线在该区间内的拐点[23]。考虑到植被光谱特性和S2A影像的“红边”优势，建立23个植被指数[24-29],并对研究区的 S2A 影像进行一阶、二阶求导（图4），再分别建立相应的23种指数关系(表4）。

# 1.4构建估算模型

分别建立对采样点棉花、芦苇、杨树、大枣叶片的 SPAD估算模型,从现场随机抽取的总样本中，随机选取总数 $7 5 \%$ 的样本建立估算模型。其他 $2 5 \%$ 的样本用于模型试验（表5）。

随机森林算法（randomforest，RF）作为一种较新的集成学习算法，可以综合利用多种特征变量建模并评价。将野外测得的植被冠层SPAD值作为因变量;植被指数系列1（原影像的23个植被指数），植被指数系列2（原一阶微分影像、二阶微分影像的23个植被指数），土壤参数（SOM、SMC、EC)分别作为自变量。设立3种方案(表6），在matlab中利用随机森林回归算法分别对采样点的4种植被（棉花、芦苇、大枣、杨树)建立植被叶片SPAD的估算模型。

为了消除不同植被指数、土壤参量之间的量纲影响，对数值进行归一化处理，使各数值处于同一数量级,以便进行综合对比评价[30]。归一化函数为：

$$
a _ { n } = { \frac { a - \operatorname* { m i n } _ { a } } { \operatorname* { m a x } _ { a } - \operatorname* { m i n } _ { a } } }
$$

式中： $a$ 为需要进行归一化处理的数据； $\textstyle { a _ { n } }$ 为归一化后的样本数据; $\operatorname* { m a x } _ { a }$ 为 $\mathbf { \Delta } _ { a }$ 中的最大值; $\mathrm { m i n } _ { a }$ 为 $\mathbf { \Delta } _ { a }$ 中的最小值。归一化后的数值范围是[0，1]。

# 1.5 特征重要性评分

在随机森林模型中[29],通过选择原始数据集和训练数据集(即校准数据集)的随机样本，使用确定

主：(a)为假彩色( $B 8 A , B 4 , B 3 )$ 合成的 S2A;(b)为一阶微分影像同假彩色波段组合一致的 S2A;(c)为二阶微分影像同假彩色波段组合一致的 S2A。

![](images/a492ef67f4db95a522686a1aaa22bcfa9c1290db56a2ac8a490180e84d3b24fd.jpg)  
图4不同预处理后的 S2A数据  
Fig.4S2A data after different pretreatments

# 表4植被指数

Tab.4Vegetation indexes  

<html><body><table><tr><td>分类</td><td>指数</td><td>全称</td><td>计算公式</td></tr><tr><td rowspan="6">传统指数[24]</td><td>NDVI</td><td>归一化植被指数</td><td>(B8A-B4)/(B8A+ B4)</td></tr><tr><td>RVI</td><td>比值植被指数</td><td>B8A/B4</td></tr><tr><td>DVI</td><td>差值植被指数</td><td>B8A-B4</td></tr><tr><td>CL</td><td>叶绿素指数－绿色</td><td>B8A/B3-1</td></tr><tr><td>CVI</td><td>叶绿素植被指数</td><td>B8A×B4/B3²</td></tr><tr><td></td><td>改良三角植被指数2</td><td>1.5[1.2(B8A-B4）-2.5(B4-B3)]</td></tr><tr><td rowspan="20"></td><td>MTVI2</td><td></td><td>√(2B8A+1)²-(6B8A-5√B4)-0.5</td></tr><tr><td>NDVIre1</td><td>红边归一化植被指数1</td><td>(B8A-B5)/(B8A+B5)</td></tr><tr><td>NDVIre2</td><td>红边归一化植被指数2</td><td>(B8A-B6)/(B8A+ B6)</td></tr><tr><td>NDVIre3</td><td>红边归一化植被指数3</td><td>(B8A-B7)/(B8A+ B7)</td></tr><tr><td>NDre1</td><td>红边归一化差值1</td><td>(B6-B5)/(B6+B5)</td></tr><tr><td>NDre2</td><td>红边归一化差值2</td><td>(B7-B5)/(B7+B5) B5</td></tr><tr><td>TCIre1 TCIre2</td><td>红边三角叶绿素指数1</td><td>1.2(B5-B3）-1.5(B4-B3) B4 B6</td></tr><tr><td>TCIre3</td><td>红边三角叶绿素指数2</td><td>1.2(B6-B3）-1.5(B4-B3) B4</td></tr><tr><td>TCARIre1</td><td>红边三角叶绿素指数3</td><td>1.2(B7-B3）-1.5(B4-B3) B7 B4</td></tr><tr><td>TCARIre2 红边指数[25-29]</td><td>红边转化叶绿素吸收反射率指数1</td><td>3[（B5-B4）-0.2(B5-B3)B5/B3]</td></tr><tr><td>TCARIre3</td><td>红边转化叶绿素吸收反射率指数2</td><td>3[（B6-B4）-0.2(B6-B3)B6/B3]</td></tr><tr><td></td><td>红边转化叶绿素吸收反射率指数3</td><td>3[（B7-B4）-0.2(B7-B3)B7/B3] B8A/B5-1</td></tr><tr><td>MSRre1</td><td>修正的简单比率1</td><td>B8A+1) √ B5 B8A/B6-1</td></tr><tr><td>MSRre2 MSRre3</td><td>修正的简单比率2</td><td>V B6 B8A/B7-1 B8A+1)</td></tr><tr><td></td><td>修正的简单比率3</td><td>B8A +1) B7</td></tr><tr><td>CIre1</td><td>红边叶绿素指数1</td><td>B8A/B5-1</td></tr><tr><td>CIre2</td><td>红边叶绿素指数 2</td><td>B8A/B6-1</td></tr><tr><td>CIre3</td><td>红边叶绿素指数3</td><td>B8A/B7-1</td></tr></table></body></html>

# 表5建模方案

Tab.5Modeling plans   

<html><body><table><tr><td>植被类型</td><td>样本总数</td><td>训练样本数</td><td>估算样本数</td></tr><tr><td>棉花</td><td>40</td><td>30</td><td>10</td></tr><tr><td>芦苇</td><td>45</td><td>34</td><td>11</td></tr><tr><td>杨树</td><td>23</td><td>17</td><td>6</td></tr><tr><td>大枣</td><td>30</td><td>23</td><td>7</td></tr></table></body></html>

# 表6实验方案信息

Tab.6Information of experimental programs   

<html><body><table><tr><td>实验方案</td><td>特征组合</td></tr><tr><td>1</td><td>植被指数系列1</td></tr><tr><td>2</td><td>植被指数系列1+植被指数系列2</td></tr><tr><td>3</td><td>植被指数系列1+植被指数系列2+土壤参数</td></tr></table></body></html>

性算法构建每颗树。需要在随机森林模型中确定3个参数： $N$ 是从原始数据集中抽取的 $N$ 个集合用于生成回归树的数量（默认值为500棵树）； $K$ 是从 $N$ 个训练集中提取的 $K$ 个特征变量（默认值是总数据量的 $6 6 . 6 7 \%$ ）； $X$ 是从 $K$ 个总特征变量中选取的最具重要性的 $X$ 个特征参数作为每棵树的分类节点$( X { \leqslant } K )$ 。此外,在抽取训练集 $X$ 过程中，未被抽取部分称为袋外数据（out-of-bag，OOB），使用此部分数据计算内部误差（OOB误差），OOB误差越小，说明随机森林模型的分类精度越高。OOB误差也可以计算特征变量的重要性，将需要计算的一个特征变量改变并保持的其他特征变量不变，计算被改变特征变量前、后OOB误差的差值和百分比，即为判断该特征变量重要性的依据[27]。其评估模型如下：

$$
V I ( { \cal M } _ { \cal A } ) = \frac { 1 } { N } { \sum _ { t = 1 } ^ { N } } \left( B _ { n _ { t } } ^ { { \cal M } _ { \cal A } } - B _ { o _ { t } } ^ { { \cal M } _ { \cal A } } \right)
$$

式中： $\boldsymbol { W }$ 表示特征变量的重要性； $M$ 为样本的全部特征数; $N$ 为生成的决策树的棵数; $B _ { o _ { t } } ^ { M _ { A } }$ 为任意特征值 $M _ { \scriptscriptstyle A }$ 未加入噪声干扰时第 $\mathbf { \chi } _ { t }$ 棵决策树的OOB误差； $B _ { n _ { t } } ^ { M _ { A } }$ 为任意特征值 $M _ { \scriptscriptstyle A }$ 加入噪声干扰时第 $\mathbf { \chi } _ { t }$ 棵决策树的OOB误差。特征变量的重要性 $\boldsymbol { \mathit { W } }$ 值越大,则说明特征 $M _ { A }$ 对分类结果的影响越大。

# 1.6模型精度检验方法

本研究利用估算样本对基于不同输入变量的模型精度进行检验，并使用以下指标评估模型效果[31]：确定系数 $( R ^ { 2 } )$ 、均方根误差（RMSE）、相对百分比偏差 $( R P D )$ 。本研究中， $R ^ { 2 }$ 包括建模集的确定系数( $R ^ { 2 } \mathrm { c a l } )$ 和验证集的确定系数 $( R ^ { 2 } \mathrm { v a l } )$ 。RMSE包括建模集的均方根误差！ $( R M S E _ { c }$ )和验证集的均方根误差 $( R M S E _ { \mathrm { v } }$ )。采用3类标准评估模型的可预测性，即I类( $R P D > 2 . 2 )$ 具有良好的可预测性;$\mathbb { I }$ 类 $( 2 . \ 0 < R P D \ < 2 . \ 2 )$ 具有中度可预测性；Ⅲ类（RPD<2.0)具有较差的可预测性(32） 。

# 2结果与分析

# 2.1 特征重要性分析

在本研究中，当树的数量 $( N )$ 为500时，袋外误差OOB基本收紧并趋于稳定，因此，所有实验方案的 $N$ 为 ${ 5 0 0 , K }$ 为 $^ { 3 3 5 , X }$ 则设为2。上文中的方案1和方案2均为对照实验，不需要做特征变量的重要性评价，故在方案3的基础上，对参与建模的72个特征变量进行特征重要性评价，并选取前31个得分较高的重要性生成重要性分布图（图5）。

在4种植被叶片的SPAD估算模型中,棉花、芦苇、枣树的一阶指数的重要性都是各自建模特征中占比最大的，尤其是芦苇，达到了 $4 2 \%$ ;而土壤参量虽然只有3个特征变量(SMC、SOM、EC)参与，占所有特征变量总数的 $4 . 1 7 \%$ ，在每种估算模型中贡献的重要性都高于 $6 \%$ ,特别是杨树叶片的SPAD估算模型，其占比达到了 $1 5 \%$ ，且SMC和EC是重要性前2位的特征变量，分别到达了 $5 . 4 3 \%$ 和 $5 . 0 1 \%$ （图6)。可见，土壤参量对植被叶片的叶绿素相对含量有较强的响应。

# 2.3叶片SPAD值模型估算结果

在所有植被叶片SPAD估算模型中，从方案1到方案3的建模集效果逐步提升， $R _ { \mathrm { C A L } } ^ { 2 }$ 逐渐增大,$R M S E _ { \mathrm { c } }$ 也呈现出逐渐变小的趋势（图7）。加入微分影像的植被指数和实测土壤属性后，建模效果显著提高。在预测效果方面，所有估算模型的RPD都达到了Ⅱ类标准，具有中度及以上的可预测性，但与建模集效果都逐渐提高的情况不同，芦苇、枣树、杨树叶片SPAD估算模型的验证集中，相比方案1，方案2的RPD反而减小，其可预测性出现了下降的情况，尤其是芦苇叶片 SPAD 估测模型的RPD值，由方案1的2.620骤降到方案2的2.009，模型的可预测性也从良好变成了中等，可能是方案2加入的植被指数较多，导致了部分特征变量冗余，降低了模型的预测效果（表7）。此外，杨树叶片SPAD估算模型的方案 $^ { 2 , R ^ { 2 } }$ 仅比方案1提升了0.01，但其RM-$S E _ { \mathrm { v } }$ 却增大了 $0 . 7 2 4 , R P D$ 下降了0.014，可见其方案2的模型整体效果较方案1下降。而所有植被在方案3的验证效果却都是3种方案中最优的， $R ^ { 2 }$ 最注：1st表示已经过一阶导之后的影像，2nd表示经过二阶导之后的影像。

![](images/1b9e1e032248150a6e90d372ce20f17b01a7fc7811947939193dc258de2172e5.jpg)  
图5特征重要性分布

![](images/ffc654c0176fd446970c40e44a81c9e1885d48566651c6e4815859c03cf2fc67.jpg)  
Fig.5 Distribution of characteristic importance   
图6特征重要性占比  
Fig.6Proportions of characteristic importance

大， $R M S E _ { \mathrm { v } }$ 最小, $R P D > 2 . 2$ 。这说明方案3加入的土壤参量不是冗余变量，且对估算叶片 SPAD 值具有积极影响。

图8为利用方案3的4种植被叶片SPAD值预测模型制作的研究区植被叶片SPAD遥感监测专题图。以同步采集的地面实测数据进行精度检验：将地面实测SPAD值与叶绿素含量分布图上同样点的估算值进行回归拟合。分布图估算值与实测数据的拟合方程决定系数 $R ^ { 2 }$ 为 $0 . 8 2 6 , R M S E$ 为3.794，结果表明，基于估算模型的植被叶片SPAD值空间分布与实测值基本一致。

75 (a)M1 75 (b)M2 75 (c)M37065 4· 建模集 A 7065 4· 建模集 A 7065 4· 建模集60 1:1线 60 1:1线 A 60 1:1线 .  
值55 值55 . 值55  
50 预45 40 A A R=0.829 RMSEc=3.004 5 40 4 R=0.858 RMSE=2.638 50 预 45 40 上 0.84 RMSEc=2.47135 △ . RD=2.03476 3530 RMDE2-2.646 330 ： RPD=2=290/2530354045505560657075 25303540455055606570 75 2530354045505560657075实测值 实测值 实测值65 (d)L1 65 (e)L2 65 (f)L360 △ 建模集 60 建模集 60 建模集55 . 验证集 55 ·验证集 55 ·验证集1:1线 1:1线 -1:1线 0982  
预40 Ra=0.912 预40 R²a=0.918 预4035 上山 R=0.864 35 Y R=0.913 35 Y A R=0.932》 RMSE=2.528 RMSE=2.419 RMSE=2.43630 A RMSEv=2.160 30 . RMSE=2.380 30 ? RMSEv=1.91325 △ 25 25RPD=2.620 A RPD=2.009 RPD=2.48420253035404550556065 20253035404550556065 20253035404550556065实测值 实测值 实测值60 (g)H1 △ 60 (h)H2 60 (i)H3 △55 △建模集 55 建模集 55 建模集. 验证 验证集 验证50 50 50  
45 45 Y 45 V  
预40 ? 4 R²=0.823 预40 A Ra=0.875 预40 △ R²=0.946△ R=0.832 女 R=0.871 △ R=0.92635 △ RMSE=3.977 35 N RMSE=3.290 35 长 RMSE=3.04230 RMD=2=3.995 30 △ RPD=2=3.002 30 A RPD=2=3.08525303540455055606570 75 2530354045505560657075 2530354045505560657075实测值 实测值 实测值65 (jY1 65 (k)Y2 65(l)Y360 建模集 60 建模集 60 建模集55 ·验证集 55 ·验证集 55 ·验证集  
53 国 4053 1：1线 580 ！品 P ? 心 4△25 25 25 ARPD=2.035 RPD=2.021 RPD=2.14320 253035404550556065 70 2025303540455055606570 20 25303540455055606570实测值 实测值 实测值

注：M代表棉花叶片,L代表芦苇叶片,H代表枣树叶片,Y代表杨树叶。1代表方案1,2代表方案2,3代表方案3,M1是方案1的棉花叶片SPAD 估算模型,以此类推。 $R ^ { 2 } { \mathrm { c a l } }$ 表示建模集的确定系数， $R ^ { 2 } \mathrm { v a l }$ 表示验证集的确定系数， $R M S E _ { \mathrm { c } }$ 表示建模集的均方根误差， $R M S E _ { \mathrm { v } }$ 表示验证集的均方根误差， $R P D$ 是验证集的相对百分比偏差,SPAD表示叶绿素相对含量。

# 3讨论

SPAD值反映了植被叶片单位表面积的叶绿素含量，并可以表征植被叶片、冠层的养分和长势状况，它与植被叶片的反射光谱之间存在较强的相关性[,选取特征波段构建光谱指数在不同程度上降低了由环境变化而引起的反射率误差，可以用来定

量反演植被的理化参数。

（1）结合图1和图8，绿洲SPAD值的空间分布大体上为内部高，四周低，且受水系的影响较大。河流水系及水域周边植被的叶绿素含量明显较高，在$5 0 \sim 6 0 \$ 之间，而研究区西北角处叶绿素较高且没有主要水系，可能是由于暂时性灌溉导致的。要对SPAD在空间尺度上进行更深入分析，除了掌握主

# 表7叶片SPAD预测值与实测值分布

Tab.7Distribution of estimated and measured leafSPAD values   

<html><body><table><tr><td rowspan="2">植被型</td><td rowspan="2">方案</td><td colspan="2">建模集NSEC</td><td colspan="3"></td></tr><tr><td></td><td></td><td>RVAL</td><td>验证</td><td>RPD</td></tr><tr><td rowspan="3">棉花</td><td>方案1</td><td>0.829</td><td>3.004</td><td>0.825</td><td>3.476</td><td>2.045</td></tr><tr><td>方案2</td><td>0.858</td><td>2.638</td><td>0.843</td><td>2.646</td><td>2.626</td></tr><tr><td>方案3</td><td>0.894</td><td>2.471</td><td>0.881</td><td>2.290</td><td>2.692</td></tr><tr><td rowspan="3">芦苇</td><td>方案1</td><td>0.912</td><td>2.528</td><td>0.864</td><td>2.159</td><td>2.620</td></tr><tr><td>方案2</td><td>0.918</td><td>2.419</td><td>0.913</td><td>2.380</td><td>2.009</td></tr><tr><td>方案3</td><td>0.932</td><td>2.436</td><td>0.932</td><td>1.913</td><td>2.484</td></tr><tr><td rowspan="3">枣树</td><td>方案1</td><td>0.823</td><td>3.977</td><td>0.832</td><td>3.995</td><td>2.032</td></tr><tr><td>方案2</td><td>0.875</td><td>3.290</td><td>0.871</td><td>3.002</td><td>2.001</td></tr><tr><td>方案3</td><td>0.946</td><td>3.042</td><td>0.926</td><td>3.085</td><td>2.457</td></tr><tr><td rowspan="3">杨树</td><td>方案1</td><td>0.863</td><td>3.979</td><td>0.788</td><td>3.927</td><td>2.035</td></tr><tr><td>方案2</td><td>0.889</td><td>3.959</td><td>0.798</td><td>4.651</td><td>2.021</td></tr><tr><td>方案3</td><td>0.943</td><td>3.500</td><td>0.907</td><td>3.039</td><td>2.143</td></tr></table></body></html>

注： $R _ { \mathrm { c a l } } ^ { 2 }$ 表示建模集的确定系数; $R _ { \mathrm { v a l } } ^ { 2 }$ 表示验证集的确定系数； $R M S E _ { \mathrm { c } }$ 表示建模集的均方根误差； $R M S E _ { \mathrm { v } }$ 表示验证集的均方根误差； $R P D$ 是验证集的相对百分比偏差。

![](images/6ee0a11e055266463fe166c91161a31a6d01f8a42935472a88361e03eeae1cf7.jpg)  
图8叶片SPAD遥感监测专题图  
Fig.8Spatial distribution of leaf SPAD values at greenup stage

要自然水系，还应掌握该地的灌溉区划。

（2）利用多光谱数据对叶绿素的遥感估算，以往研究选取的光谱指数类型较少，对叶绿素敏感的红边光谱指数更少(33]。本文选取23 种光谱指数参与模型构建，发现基于多个植被指数的SPAD估算模型效果( $R ^ { 2 } { \geqslant } 0 . 8 )$ 明显好于以往基于单个植被指数的SPAD估算模型。且基于“红边”的光谱指数对估算模型起到了更为关键的作用，更能反映叶绿素较高时的吸收差异。而在一阶微分影像上建立的传统光谱指数（1st_DVI,1st_NDVI,1st_RVI）,在模型中的重要性比在原影像上（DVI,NDVI,RVI)有了大幅提升。这是由于植被反射光谱在“红边”处的斜率变化剧烈，一阶微分影像的光谱指数反映出了“陡坡”上下的斜率差异。本文使用的指数是在前人的植被指数模型基础上结合S2A构建的，并未深入研究光谱指数的机理，致使部分重要性偏低的指数也参与了模型构建，如芦苇叶片在绿波段(B3）与实测光谱相对误差达到了 $3 6 . 4 7 \%$ ，绿波段（B3）参与构建的植被指数导致模型的预测能力偏低，今后需在优选特征的基础上进行模型构建。

（3）除光谱指数外，土壤属性也对预测结果有较大影响。在估算模型加入土壤含水量（SMC）、土壤有机质（SOM）、土壤电导率(EC)3个土壤参量后，可预测性显著提高，特别是SMC在4种植被叶片SPAD的估算模型中，重要性都在前5位，可见，将易获取的土壤参量加入模型能提升估算精度。

（4）本文采用的随机森林回归算法是估算植被生物量的优选方法[34]。它能最大程度地综合多种特征变量，因此影像数据覆盖的范围越广、空间分辨率和光谱分辨率越高，模型效果越好。且随机森林算法能给出不同变量对模型的影响评分，这替代并且升华了以往线性模型的相关性，还可将模型优选出的重要性排序靠前的特征变量与估算对象做更深入的研究。构建的模型实现了一定范围、特定时间上的 SPAD值的快速估算，但实现更大范围更高精度的SPAD值估算还需要利用多年的新数据加以改进。

# 4结论

在12个基于随机森林回归算法的植被叶片叶绿素相对含量（SPAD）估算模型中，所有红边指数和土壤属性参数的组合展现出最佳SPAD预测能力,芦苇叶片表现效果最佳 $\mathrm { ^ { \prime } } R _ { \mathrm { { C A L } } } ^ { 2 } = 0 . 9 3 2 , R M S E _ { \mathrm { _ c } } =$ 2. 436, $R _ { \mathrm { V A L } } ^ { 2 } ~ = ~ 0$ .932， $R M S E _ { \mathrm { ~ v ~ } } = 1$ . 913, $R P D =$ （202.484）。而一阶微分指数和土壤含水量（SMC）在随机森林重要性排序中，与SPAD具有显著非线性关系。依据该模型制作的研究区植被叶片SPAD遥感监测专题图，实现了植被叶片SPAD值在空间尺度上的表达，为多光谱遥感监测植被叶绿素含量提供了参考。综上所述，S2A数据具有较强的预测绿洲植被SPAD值的潜力，基于多种光谱指数和土壤参量组合的随机森林模型为监测、估算和预测干旱和半干旱地区绿洲中植被的SPAD提供了一种快速，经济且稳定的方法。

参考文献（References）:   
[1]Hanelt D.Photosynthesis assessed by chlorophyllfluorescence[J]. Bioassays,2018,119:169 -198.   
[2]Jhanji S,Sekhon N K.Evaluation of potential of portable chlorophyll meter to quantify chlorophyll and nitrogen contents in leaves of wheat under different field conditions[J].Indian Journal of Experimental Biology,2018,56(10）:750-758.   
[3]Chang S X,Robison D J.Nondestructive and rapid estimation of hardwood foliar nitrogen status using the SPAD-502 chlorophyll meter[J].Forest Ecology and Management,2003,181(3）:331-338.   
[4]Songsri P,Jogloy S,Holbrook C C,et al.Association of root,specific leaf area and SPAD chlorophyll meter reading to water use efficiency of peanut under diferent available soil water[J].Agricultural Water Management,2009,96(5）:790-798.   
[5]Swiader JM,Moore A.SPAD-chlorophyl response to nitrogen fertilization and evaluation of nitrogen status in dryland and irrigated pumpkins[J]. Journal of Plant Nutrition,2002,25（5）:1 089- 1100.   
[6]Yuan S,Goron TL,Huang L,et al. Rice leaf lateral asymmetry in the relationship between SPAD and area-based nitrogen concentration[J].Symmetry,2017,9(6) :83.   
[7]王娟,韩登武,任岗,等.SPAD值与棉花叶绿素和含氮量关系 的研究[J].新疆农业科学,2006,43（3）:167－170.[Wang Juan,Han Dengwu,Ren Gang,et al.A study on relation between SPAD value,chlorophyll and nitrogen content in cotton[J]. Xinjiang Agricultural Sciences,2006,43（3）:167 -170.]   
〔8］邓兴耀,姚俊强,刘志辉.基于GIMMS NDVI的中亚干旱区植 被覆盖时空变化[J].干旱区研究,2017,34(1):10-19.[Deng Xingyao,Yao Junqiang,Liu Zhihui.Spatiotemporal dynamic change of vegetation coverage in arid regions in central Asia based on GIMMS NDVI[J].Arid Zone Research,2017,34(1):10-19.]   
[9]邹红玉,郑红平.浅述植被"红边"效应及其定量分析方法[J]. 遥感信息,2010(4）:112-116.［Zou Hongyu,Zheng Hongping. The effect and method of quantitative analysis of“Red Edge”of vegetation[J].Remote Sensing Information,2010（4）:112- 116.]   
[10］程乾,黄敬峰,王人潮,等．MODIS 植被指数与水稻叶面积指 数及叶片叶绿素含量相关性研究[J]．应用生态学报,2004,15 (8）:1 363-1367.[Chen Qian,Huang Jingfeng,Wang Renchao, et al.Correlation analysis of simulated MODIS vegetation indices and rice leaf area index and leaf chlorophyll content[J].Chinese Journal of Applied Ecology,2004,15(8）:1 363-1 367.]   
[11]Shou L N,Jia LL,Chen XP,et al. Using high-resolution satellite image to evaluate nitrogen status of winter wheat in the North China plain[J].Journal of Plant Nutrition,2007,30（10）:1 669- 1 680.   
[12]宋晓宇,黄文江,王纪华,等.ASTER卫星遥感影像在冬小麦品 质监测方面的初步应用[J].农业工程学报,2006,22（9）： 148-153.[Song Xiaoyu,Huang Wenjiang,Wang Jihua,et al.Preliminary application of ASTER images in winter wheat quality monitoring[J].Transactions of the CSAE,2006,22(9):148 -153.]   
[13］谭昌伟,王纪华,赵春江,等.利用Landsat TM遥感数据监测冬 小麦开花期主要长势参数［J].农业工程学报，2011,27（5）： 224-23o.[Tan Changwei,Wang Jihua,Zhao Chunjiang,et al. Monitoring wheat main growth parameters at anthesis stage by Landsat TM[J].Transactions of the CSAE,2011,27（5）:224- 230.]   
[14]Delegido J,Verrelst J,Alonso L,et al. Evaluation of sentinel22 rededge bands for empirical estimation of green LAI and chlorophyll content[J].Sensors,2011,11(7) :7 063-7 081.   
[15]Clevers JG P W,Gitelson A A.Remote estimation of crop and grass chlorophy II and nitrogen content using red-edge bands on Sentinel $^ { - 2 }$ and -3[J]. International Journal of Applied Earth Observation and Geoinformation,2013,23:344 -351.   
[16]Verrelst J,Munoz J,AlonsoL,et al. Machine learning regresion algorithms for biophysical parameter retrieval:Opportunities for Sentinel-2 and-3[J].Remote Sensingof Environment,2012,118: 127 - 139.   
[17］李粉玲,王力,刘京,等.基于高分一号卫星数据的冬小麦叶片 SPAD 值遥感估算[J].农业机械学报,2015,46(9）：273-281 [Li Fenling,Wang Li,Liu Jing,et al.Remote sensing estimation of SPAD value for wheat leaf based on GF-1 data[J]. Transactions of the Chinese Society for Agricultural Machinery,2015,46（9）: 273 - 281. ]   
[18］王丹丹,程猛,杨瑞红,等.近20 a渭干河绿洲土壤盐分变化特 征[J].干旱区研究,2015,32(6）:1076-1081.[Wang Dandan,Cheng Meng,Yang Ruihong,et al. Changing characteristics of soil salt in Weigan river oasis for the last 2O years[J].Arid Zone Research,2015,32(6):1 076 -1 081.]   
[19］康璇,王雪梅,柴仲平.近25a来渭—库绿洲土地利用/覆被变 化及其影响因素[J].水土保持通报,2016,36(5）：333-339. [ Kang Xuan,Wang Xuemei,Chai Zhongping.Land use/cover changesand Influencing factors indelta oasis of Weigan-Kuqa river during last 25years[J]. Bulletin of Soil and Water Conservation, 2016,36(5):333 -339. ]   
[20］丁建丽,瞿娟,孙永猛,等.基于 MSAVI-WI特征空间的新疆渭 干河一库车河流域绿洲土壤盐渍化研究[J].地理研究,2013, 32(2）:223- 232.[Ding Jianli,Qu Juan,Sun Yongmeng,et al. The retrieval model of soil salinization information in arid region based on MSAVI-WI feature space:A case study of the delta oasis in Weigan-Kuqa watershed[J]. Geographical Research,2013,32 (2) :223 -232.]   
[21］杨爱霞,丁建丽.新疆艾比湖湿地土壤有机碳含量的光谱测定 方法对比[J].农业工程学报,2015,31（18）:162-168.[Yang Aixia,Ding Jianli.Comparative assessment of two methods for estimation of soil organic carbon content by Vis-NIR spectra in Xinjiang Ebinur Lake Wetland[J].Transactions of the Chinese Society of Agricultural Engineering,2015,31（18）:162-168.]   
[22]Green M.A relative error bound for balanced stochastic truncation [J].IEEE Transactions on Automatic Control,1988,33（10）: 961 - 965.   
[23]Filella I,Penuelas J. The red edge position and shape as indicators of plant chlorophyll content,biomass and hydric status[J]. International Jourmal of Remote Sensing,1994,15(7）:1 459-1 470.   
[24]Shang J,Liu J,Ma B,etal. Mapping spatialvariabilityof crop growth conditions using RapidEye data in Northern Ontario,Canada [J].Remote Sensing of Environment,2015,168:113-125.   
[25]Gitelson A A,Gritz Y,Merzlyak MN.Relationships between leaf chlorophyll content and spectral reflectance and algorithms for nondestructive chlorophyll assessment in higher plant leaves[J]. Journal of Plant Physiology,2003,160(3）:271-282.   
[26]Jiang Z,Huete AR,DidanK,et al.Development of a two-band enhanced vegetation index without a blue band[J].Remote Sensing of Environment,2008,112(10）:3 833-3 845.   
[27]Haboudane D,Tremblay N,Miller JR,et al.Remote estimation of crop chlorophyll content using spectral indices derived from hyperspectral data[J].IEEE Transactions on Geoscience and Remote Sensing,2008,46(2):423-437.   
[28]Vincini M,Frazzi E,D'Alessio P.A broad-band leaf chlorophyll vegetation index at the canopy scale[J].Precision Agriculture, 2008,9(5) :303 -319.   
[29]Wu C,Niu Z,Tang Q,et al.Estimating chlorophyll content from hyperspectral vegetation indices:Modelingand validation[J].Agricultural and Forest Meteorology,2008,148(8-9）:1 230-1 241.   
[30]程志庆，张劲松,孟平，等.杨树叶片叶绿素含量高光谱估算模 型研究[J].农业机械学报,2015,46（8）:264－271.[Cheng Zhiqing,Zhang Jinsong,Meng Ping,et al.Hyperspectral estimation model of chlorophyll content in poplar leaves[J].Transactions of the Chinese Society for Agricultural Machinery,2O15,46（8）： 264 -271.]   
[31]葛翔宇，丁建丽，王敬哲，等.基于竞争适应重加权采样算法耦 合机器学习的土壤含水量估算[J].光学学报，2018,38（10）： 1-8.[Ge Xiangyu,Ding Jianli,Wang Jingzhe,et al.Estimation of soil moisture content based on competitive adaptive reweighted sampling algorithm coupled with machine learning[J].Acta Optica Sinica,2018,38(10):1-8.]   
[32]Armstrong JS,Collopy F.Error measures for generalizing about forecasting methods:Empirical comparisons[J].International Journal ofForecasting,1992,8(1):69 -80.   
[33]Main R,Cho MA,Mathieu R,et al.An investigation into robust spectral indices for leaf chlorophyll estimation[J]. ISPRS Journal ofPhotogrammetry and Remote Sensing,2011,66(6):751-761.   
[34]Mutanga O,AdamE,Cho MA.High density biomass estimation for wetland vegetationusingWorldView $^ { - 2 }$ imageryand random forest regression algorithm[J].International Journal of Applied Earth Observation and Geoinformation,2012,18:399 -406.

# Estimation of Chlorophyll Content of Typical Oasis Vegetation in Arid Area Based on Sentinel -2 Data

GU Feng1,2.3，DING Jian-li1,2.3，GE Xiang-yu1,2,3，GAO Shi-bao4，WANG Jing-zhe $^ { 1 , 2 , 3 }$ (1.College of Resources and Environment Sciences,Xinjiang University,Urumqi 830046,Xinjiang,China; 2.KeyLaboratoryof Wisdom Cityand Environmental Modeling under Departmentof Educationof Xinjiang Uygur Autonomous Region,Urumqi83046,Xinjiang,China；3.KeyLboratoryofOasisEcologyundertheinistryofEducation,XinjiangUiesity Urumqi 830046,Xinjiang,China；4.SchoolofEarth Sciences,Zhejiang University,Hangzhou310027,Zhejiang,China)

Abstract：The Ogan-Kuqa River Delta Oasis,atypical oasis in the arid zone in China,was takenas the study area.The method of Random Forest with a comparative advantage in machine learning was chosen to model and estimate the relative contents of chlorophyll（SPAD values）of leaves from four kinds of representative vegetation（cotton,reed,poplarand jujube).The23broadband spectral indicesof vegetation,whicharesensitive tochlorophyl content,were obtained basedon thereflectance of original Sentinel-2 image withrich spectral information inthe “red edge”bands.These vegetation indices wereextracted again in the original band order on the firstly-derived Sentinel $^ { - 2 }$ image and secondly-derived Sentinel $^ { - 2 }$ image.Three soil parameters （soil moisture content,SMC ;soil organicmater,SOM;electricalconductivity,EC）related to vegetation growth wereallconductedas thecharacteristic variables affcting SPAD values.According to the characteristic variablesabove,three modelling schemes could be developed to monitor the SPAD values of vegetation leaves in oasis.The results showed that : $\textcircled{1}$ Vegetation indices obtained from the firstly-derived image played a more important role than theoriginal vegetation indices inthe SPAD estimation model. $\textcircled{2}$ It could be concluded that SPAD-RF regression model,based on the Sentinel -2 satellite imagedata,couldbe used to efectively monitorthe SPAD values of leaves ofthe four vegetation types.Especially for the estimation model of SPAD of reed leaves, $R ^ { 2 }$ reached 0. 926. $\textcircled{3}$ By analyzing and comparing the model prediction capability under the three schemes,the predictioncapability of scheme 3（including soil parameters）was excellent （2. $1 4 3 <$ relative percentage deviation $( R P D ) < 2 . 6 9 2 \$ ,and the prediction capability was ranked as scheme $3 >$ scheme $1 >$ scheme 2.There was a significant nonlinear correlation between the soil properties and the model prediction results.Holistically,Sentinel-2data hasgreat potential for predictingchlorophyll contentof oasis vegetation.This study provided an eficient,low-cost,potentially high-precision solution to estimate SPAD.

Key words:oasis；Sentinel -2 data； SPAD；chlorophyll；vegetation index； random forest； Xinjiang