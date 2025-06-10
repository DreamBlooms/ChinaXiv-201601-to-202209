# 基于遥感数据对毛乌素沙地腹部旱情等级的景观变化特征分析

王思楠，李瑞平，韩刚，王耀强，胡勇平，田鑫（内蒙古农业大学水利与土木建筑工程学院,内蒙古呼和浩特010018)

摘要：目前遥感监测土壤含水率的方法较多，本次研究选取了稳定性较好、应用较为广泛且所需气象资料少的3种监测方法——SWEPDI指数法、能量指数法与TVDI指数法。以2016年4月和9月两期中高分辨Landsat8数据为数据源，分别将 SWEPDI光谱法、能量指数法与TVDI指数法按不同时间、不同土层深度与对应时间的土壤含水率野外实测数据进行线性拟合，并进行各模型之间的比较,选择出更加适当的模型。同时利用景观指数在斑块类型上分析2时相土壤水分的变化趋势。结果表明：TVDI法效果明显优于SWEPDI光谱法和能量指数法，同时该方法还解决了其他方法不能连续监测土壤含水量的问题，适用于各种植被覆盖条件下以及各种土层深度的土壤水分反演。此外，选用6个景观指数分析了2016年4月与9月不同旱情等级干旱等级的景观格局变化，发现4月份PLAND指数达到了 $5 8 . 7 6 \%$ ，而9月份轻旱等级的PLAND指数达到了 $4 4 . 1 6 \%$ ，都占据优势地位，其中1 $. P I \ 、 A R E A \_ C V \_ A I$ 指数的值也都达到了最大，其旱情状况有了明显的改善。

关键词：SWEPDI指数法；能量指数法；温度植被干旱指数；景观格局中图分类号：TP79 文献标识码：A 文章编号：

土壤水分是反映荒漠化土地环境演变的重要因子，是监测土地退化的重要指标，也是气候环境、生态状况以及农牧业生产等领域的主要参数[],决定着区域荒漠化土地的发生、演变以及农牧业生产力等方面[2]。由于土壤含水率在时空分布情况上变化极大，传统的土壤含水量监测方法野外采集数据慢、消耗人力物力多、仅限于单点代表性差等缺点，难以满足大范围实时监测的需求，从而限制了它的应用范围。遥感方法监测土壤含水量的优势在于能以不同时空尺度不断地观测地表状况，提供地表特征信息，具有监测范围广、速度快、成本低，能够长期对研究区域的地表特征信息进行动态观测。

利用遥感手段监测土壤湿度的方法有热惯量法、蒸散法、植被指数法、SWEPDI指数法、能量指数法、温度植被指数法[3]。热惯量法通过求解地表热传导方程来实现，表达形式多样、参数复杂，且主要针对低植被覆盖的区域；蒸散法主要利用气象资料协同作物冠层温度反演土壤含水率，同样涉及大量参数，实现过程复杂；植被指数法借助于植被指数与植被覆盖下的土壤含水率相关性实现土壤水分监测，有一定的滞后性，不利于及时获取田间信息。利用植被指数与温度结合[4]进行土壤湿度的反演，是对于土壤干湿状态的一种新理解，现已被广泛研究应用[5]

遥感、地理信息系统与景观生态学理论共同形成了对大尺度生态系统空间格局进行研究的独具特色的研究模式，利用景观指数对空间格局进行定量化研究是这种研究模式的基本内容。国内外的许多学者已利用景观指数对不同地区、流域的植被景观格局进行了分析,并取得了良好的效果[6-8] O

乌审旗地处毛乌素沙地腹部。近年来，干旱灾害发生频率越来越高，牧草和畜产品减少;草地退化和荒漠化加剧；人畜饮水困难，生命遭到威胁。作为生态脆弱区，是我国北方半干旱区域生态变化研究的重点区域，具有很强的代表性。因此，本文以乌审旗地处毛乌素沙地腹部为例，比较分析SWEPDI指数法、能量指数法与TVDI指数法在乌审旗的适用性，并以实测的含水率对所挑选模型进行检验。以此为基础,对毛乌素沙地[9]景观格局变化进行分析，以期为当地生态环境治理提供科学参考。

# 1 研究区概况与研究数据

# 1.1 研究区概况

研究区乌审旗处于蒙、宁、陕的三角地带，位于内蒙古自治区最南端，地势由西北向东南倾斜，海拔一般在 $1 3 0 0 \sim 1 4 0 0 \mathrm { m } _ { \odot }$ 。 $1 0 8 ^ { \circ } 1 7 ^ { \prime } \sim 1 0 9 ^ { \circ } 4 0 ^ { \prime } \mathrm { E }$ ，$3 7 ^ { \circ } 3 8 ^ { \mathrm { ~ \prime ~ } } \sim 3 9 ^ { \circ } 2 3 ^ { \prime } \mathrm { N }$ ,面积 $1 1 6 4 5 ~ \mathrm { k m } ^ { 2 }$ 。其所处位置冬冷夏热,昼夜温差大，年平均气温 $6 . 8 ~ \mathrm { { ^ { 6 } C } }$ 。受东南季风影响，降水时段大多数集中在7、8、9月，年降水量$3 5 0 \sim 4 0 0 ~ \mathrm { m m }$ 。多年平均蒸发量 $2 \ 4 4 3 \ \mathrm { m m }$ 的干旱区，是中国中、东部平原重要的生态屏障。沙蒿是本地区沙生植被主体,该地区集荒漠和草原为一体，土地土质沙性大趋向沙漠化,盐碱土使典型草原稀疏,

生态环境十分脆弱。

# 1.2数据源与处理

研究用的影像数据由美国地质调查局（USGS)获取2016年4月21日和2016年9月28日2期覆盖乌审旗的Landsat8OLI/TIRS影像数据。两期影像都选择在与野外数据同步采集的晴空无云或者少云成像质量相对好的天气情况。同时利用ENVI软件对Landsat8OLI/TIRS图像进行辐射定标、利用Modtran4模型进行大气校正、几何精纠正等一系列的预处理。

# 1.3野外样点布设与土壤含水率数据采集

为了使野外采样点可以充分代表乌审旗区域，结合研究区行政区域空间分布及道路交通状况，在24个样区布设了120个样点，每个样区( $1 0 \ \mathrm { k m } \times 1 0$ $\mathbf { k m } _ { \mathrm { ~ , ~ } } ^ { \mathrm { ~ \scriptsize ~ { ~ k ~ m ~ } ~ } }$ ）中各子样点之间的间距大致为 $1 ~ \mathrm { k m }$ 。考虑到不同深度的土壤含水率分布状况，每隔 $1 0 \ \mathrm { c m }$ 深度利用土钻对土壤含水率进行一次采样，共3组重复的 $0 \sim 1 0 \ \mathrm { c m } \ 1 0 \sim 2 0 \ \mathrm { c m } \ . 2 0 \sim 3 0 \ \mathrm { c m }$ 土壤样品，然后用烘干称重法测定其土壤含水量。由于研究区范围大，野外试验采样于2016年4、9月影像成像时间的前后3d内完成样点的采集。

![](images/764ebb602c9b46eed88874e67eccc3d0708cc22a54affabef82da4fec5a357f9.jpg)  
图1研究区地理位置和采样点分布  
Fig.1Geographical location in the study area and the sampling point distribution

![](images/6912a2735348371835225c2ca91cd3308bf758a17f37fb81d0a1097c9b2e3f08.jpg)  
图2子样点采样设计

# 2研究方法

遥感监测土壤含水率的方法较多，本次研究选取了稳定性较好、应用较为广泛且所需气象资料少的三种监测方法——SWEPDI指数法、能量指数法与TVDI指数法进行对比、分析，分别得出3种旱情指数的优劣及其适用范围。

以2016年4月与9月两期中高分辨Landsat8数据为数据源，分别将SWEPDI光谱法、能量指数法与TVDI指数法按不同时间、不同土层深度与对应时间的土壤含水率野外实测数据进行线性、指数及对数拟合，并进行各模型之间的比较，选择出更加适当的模型。以该方法为基础，提取毛乌素沙漠腹部3个年份的土壤水分并进行分级，然后选取景观指数对分级的影响进行景观格局计算和分析。

# 2.1 SWEPDI模型

$E ( \rho _ { r e d } \sqrt { \rho _ { n i r } } )$ 表示 NIR-Red 特征空间上的任意一点，由该点到直线L的距离的大小可以说明地表的干旱情况，即离L线越远地表越干旱，反之亦然。在 NIR-Red 特征空间上任意取一点 $E$ $\rangle ( \rho _ { r e d } \sqrt { \rho _ { n i r } } )$ 到直线L的距离的 $E F$ 可以描述干旱的状况，即距离等于垂直干旱指数 $( P D I )$ 大小，因此可以建立一个基于NIR-Red光谱空间特征的干旱监测模型PDI（图2）。本文中采用郭兵修正后的EPDI模型[10]公式如下：

$$
E P D I = \frac { \rho _ { r e d } + M \rho _ { n i r } - \mathrm { L } \times ( D V I - M \rho _ { r e d } ) } { E V I \times \sqrt { 1 + M ^ { 2 } } }
$$

式中： $| \rho _ { r e d } \ 、 \rho _ { n i r }$ 分别为经过FLAASH大气校正的红波段、近红外波段反射率; $M$ 为土壤线斜率; $E W I$ 为增强型植被指数;L为调整系数，按照研究区植被覆盖状况取值，在此取值为 $0 . 6$ 。

在土壤极度干旱时，EPDI指数均趋向于0，而当地表湿度很大或者地表为水体时，EPDI指数则趋近于1，因此用1减去各种归一化干旱指数便得到了土壤水分指数SWEPD,即为：

$$
S W E P D I = 1 - E P D I
$$

# 2.2 能量指数法模型

根据土壤热力学理论，地球表面接收太阳辐射以后，经过复杂的转换又以长波辐射的形式向外发射能量，因此，较强的长波辐射标志着地表温度较高。能量指数的基本思路是地球表面单位面积上得到的短波辐射为 $( 1 - A _ { 1 } )$ ，土壤越干燥,经过转换向外放出的长波辐射越强，表现为地表和植冠温度越高，因为土壤中或植被中的水分吸收了一部分太阳辐射，土壤越湿润，经过转换向外放出的长波辐射越弱，表现为地表和植冠温度越低。利用遥感数据与土壤熵情数据建立能量指数关系[11],公式如下：

$$
D = \left( 1 - A _ { 1 } \right) / T _ { s }
$$

式中： $\smash { : A _ { 1 } }$ 为近红外波段（光谱范围 $8 4 1 \sim 8 7 6 \ \mathrm { n m }$ 的反照率； $T _ { s }$ 为地表温度。

# 2.3 TVDI模型

PRICE 等[12]人研究发现植被指数和地表温度呈显著的负相关关系，土壤水分条件和植被覆盖情况变化较大时，以遥感数据反演出的植被指数和地表温度为 $X , Y$ 坐标的散点图呈三角形。在植被指数和地表温度的三角形特征空间中，可以提取到干、湿边方程：

$$
T _ { \mathrm { { S m a x } } } = a _ { 1 } + b _ { 1 } \times N D V I
$$

$$
T _ { \mathrm { S m i n } } = a _ { \mathrm { 2 } } + b _ { \mathrm { 2 } } \times N D V I
$$

式中： $T _ { \mathrm { s m a x } }$ 为干边, $T _ { \mathrm { s m i n } }$ 为湿边,分别由植被指数和

![](images/13dc224234f4766271062b2634fed99417368332feb992ef8f1f85b6d2053047.jpg)  
Fig.2The sample point sampling design   
图3 NIR-Red 特征空间 Fig.3 NIR-Red feature space

地表温度根据干边，湿边拟合得到; $a _ { 1 } \setminus b _ { 1 } \setminus a _ { 2 } \setminus b _ { 2 }$ 是干、湿边拟合方程系数。

TVDI依靠图像数据由植被指数和地表温度[13]计算得到，其定义为：

$$
T V D I = \frac { T _ { s } - T _ { S \operatorname* { m i n } } } { T _ { S \operatorname* { m a x } } - T _ { S \operatorname* { m i n } } }
$$

TVDI的取值范围为 $0 \sim 1$ ,与土壤表层含水量呈负相关，与干旱程度呈正相关。即：TVDI值越大，土壤湿度越低，相对干旱程度越严重；相反，相对干旱程度越低[14]

# 2.4 景观格局分析

基于景观指标定量分析景观格局的特征与变化是景观生态学研究的核心之一，合适的景观指数对景观格局分析的合理性十分重性。所以本文在借鉴前人研究结果的基础上，结合各指标生态学涵义和研究区特点，利用Fragstats4.2软件毛乌素沙地腹部2个时相的景观指数，在类型水平上面积 $( C A )$ 、斑块数量（NP）、比重（PLAND）、最大斑块数（LPI)斑块面积变异指数 $( A R E A \_ C V )$ 、斑块聚合度 $( A I )$ 等6个指标,各景观格局指标的生态学意义与计算公式参见文献[15] C

# 3结果与分析

# 3.1 模型的回归拟合

采用2016年4月和9月的2期各土层深度（0$\sim 1 0 \ \mathrm { c m } \ . 1 0 \sim 2 0 \ \mathrm { c m } \ . 2 0 \sim 3 0 \ \mathrm { c m } )$ 的土壤含水率数据，分别于SWEPDI指数法、能量指数法、TVDI指数法土层深度含水率建立回归方程( $W = a + b Q$ ），回归检验结果见表1、2、3。

总体来看，不同时期的SWEPDI指数法、能量指数法各呈现不同程度的正相关，即指数越低，土壤含水量越低，TVDI指数法呈现不同程度的负相关，即指数越高，土壤含水量越低，旱情程度越严重，因此可以用于表层土壤含水量和旱情监测研究。

4月份SWEPDI指数法、能量指数法与土壤含水率 $( 0 \sim 1 0 \ \mathrm { c m } \ . 1 0 \sim 2 0 \ \mathrm { c m } \ . 2 0 \sim 3 0 \ \mathrm { c m } )$ 的相关系数$R$ 值分别为 $0 . 6 0 6 , 0 . 5 4 1 , 0 . 5 0 2 ; 0 . 6 5 2 , 0 . 6 2 1 .$ 0.566，整体上低于9月份的相关系数 $R$ 值0.641、$0 . 5 9 4 \ 、 0 . 5 7 1 \thinspace ; 0 . 7 4 9 \ 、 0 . 6 7 0 \ 、 0 . 6 6 1$ 。而4月份TVDI指数法与土壤含水率 $( 0 \sim 1 0 \ \mathrm { c m } \ . 1 0 \sim 2 0 \ \mathrm { c m } \ . 2 0 \sim 3 0 \$ cm)的相关系数 $R$ 值分别为 $- \ : 0 . \ : 8 6 5 , - \ : 0 . \ : 8 4 0 ,$ -0.723整体上高于于9月份的 $- 0 . 7 5 2 、 - 0 . 7 0 3$ 、

# 表1SWEPDI对土壤含水率的拟合结果

Tab.1SWEPDI's fitting and test results of soil   

<html><body><table><tr><td colspan="8">moisture content</td></tr><tr><td>时间</td><td>土层 深度 /cm</td><td>样本 数 n</td><td>采用 模型</td><td>相关 系数 R</td><td>系数 项</td><td>常数 项</td><td>相对 误差 △%</td></tr><tr><td rowspan="3">4月</td><td>0~10</td><td>80</td><td>线性</td><td>0.606</td><td>35.381</td><td>- 17.444</td><td>14.96</td></tr><tr><td>10~20</td><td>80</td><td>线性</td><td>0.541</td><td>32.824</td><td>-15.157</td><td>21.96</td></tr><tr><td>20~30</td><td>80</td><td>线性</td><td>0.502</td><td>30.017</td><td>-12.531</td><td>23.45</td></tr><tr><td rowspan="3">9月</td><td>0~10</td><td>80</td><td>线性</td><td>0.641</td><td>50.779</td><td>-24.028</td><td>14.91</td></tr><tr><td>10~20</td><td>80</td><td>线性</td><td>0.594</td><td>41.462</td><td>-17.353</td><td>18.37</td></tr><tr><td>20~30</td><td>80</td><td>线性</td><td>0.571</td><td>38.016</td><td>-15.094</td><td>19.14</td></tr></table></body></html>

Tab.2The fitting and test results of soil moisture contentby energy index method   

<html><body><table><tr><td>时间</td><td>土深层 /cm</td><td>样数 n</td><td>采用 模型</td><td>R</td><td>系数 项</td><td>常数 项</td><td>相对差 △%</td></tr><tr><td rowspan="3">4月</td><td>0~10</td><td>80</td><td>线性</td><td>0.652</td><td>106.470</td><td>-18.623</td><td>13.84</td></tr><tr><td>10~20</td><td>80</td><td>线性</td><td>0.621</td><td>96.066</td><td>-15.523</td><td>16.27</td></tr><tr><td>20~30</td><td>80</td><td>线性</td><td>0.566</td><td>92.419</td><td>-14.024</td><td>21.41</td></tr><tr><td rowspan="3">9月</td><td>0~10</td><td>80</td><td>线性</td><td>0.749</td><td>119.800</td><td>-31.108</td><td>12.24</td></tr><tr><td>10~20</td><td>80</td><td>线性</td><td>0.670</td><td>101.620</td><td>- 24.465</td><td>15.67</td></tr><tr><td>20~30</td><td>80</td><td>线性</td><td>0.661</td><td>92.188</td><td>- 21.271</td><td>16.65</td></tr></table></body></html>

# 表3TVDI对土壤含水率的拟合结果

表2能量指数法对土壤含水率的检验结果  
Tab.3The fitting and test results of TVDI on soil moisture content   

<html><body><table><tr><td>时间</td><td>土层 深度 /cm</td><td>样本 数 n</td><td>采用 模型</td><td>相关 系数 R</td><td>系数 项</td><td>常数 项</td><td>相对 误差 △%</td></tr><tr><td rowspan="3">4月</td><td>0~10</td><td>80</td><td>线性</td><td>-0.865</td><td>-26.829</td><td>20.202</td><td>8.97</td></tr><tr><td>10~20</td><td>80</td><td>线性</td><td>-0.840</td><td>-23.312</td><td>18.834</td><td>10.95</td></tr><tr><td>20~30</td><td>80</td><td>线性</td><td>-0.723</td><td>-21.511</td><td>18.399</td><td>15.13</td></tr><tr><td rowspan="3">9月</td><td>0~10</td><td>80</td><td>线性</td><td>-0.752</td><td>-37.847</td><td>27.436</td><td>10.85</td></tr><tr><td>10~20</td><td>80</td><td>线性</td><td>-0.703</td><td>-31.592</td><td>24.730</td><td>11.01</td></tr><tr><td>20~30</td><td>80</td><td>线性</td><td>-0.679</td><td>-30.848</td><td>24.638</td><td>14.23</td></tr></table></body></html>

$- 0 . 6 7 9$ 。不管4月份还是9月份相关系数 $R$ 值都随着土层深度 $( 0 \sim 1 0 \ \mathrm { c m } \ . 1 0 \sim 2 0 \ \mathrm { c m } \ . 2 0 \sim 3 0 \ \mathrm { c m } )$ 的增加而整体呈现出下降趋势,说明SWEPDI指数法、能量指数法与TVDI指数法都适合 $0 \sim 1 0 ~ \mathrm { c m }$ 深度土壤表层含水率的监测，这与闫峰等[1认为Nir-Red监测土壤水分有效深度为 $0 \sim 1 0 \mathrm { c m }$ 极为相符。

# 3.2 验证

为了验证模型的结果，在同期野外实测数据中随机抽取40个采样点的土壤含水量进行统计分析取平均相对误差、均方根误差为评价指标来进行定量分析验证精度。相对误差的平均值指标反映了相

# 表4验证结果

Tab.4The verification results   

<html><body><table><tr><td>时间</td><td>监测模型</td><td>平均相对误差</td><td>均方根误差</td></tr><tr><td rowspan="3">4月</td><td>SWEPDI</td><td>14.31</td><td>4.65</td></tr><tr><td>能量指数法</td><td>13.65</td><td>4.13</td></tr><tr><td>TVDI</td><td>9.68</td><td>2.38</td></tr><tr><td rowspan="3">9月</td><td>SWEPDI</td><td>14.08</td><td>4.43</td></tr><tr><td>能量指数法</td><td>13.17</td><td>3.98</td></tr><tr><td>TVDI</td><td>10.24</td><td>2.67</td></tr></table></body></html>

对误差的整体状况，均方根误差表示了反演结果偏离其平均值的程度，均方根误差越大，表示偏离平均值越大。

从表4验证结果可看出：在4月SWEPDI指数法、能量指数法、TVDI指数法实测值与反演值的平均相对误差从小到大依次为9.68、13.65、14.31；均方根误差从小到大依次为2.38、4.13、4.65。在9月SWEPDI指数法、能量指数法、TVDI指数法实测值与反演值的平均相对误差从小到大依次为10.24、13.17、14.08;均方根误差从小到大依次为2.67、3.98、4.43，即平均相对误差、均方根误差越小稳定性越高。因此4月、9月反演结果稳定性从大到小依次为TVDI指数法、能量指数法与SWEPDI指数法。

# 3.3干旱指数适用性的比较与分析

为进一步比较前面分析的三种干旱指数的特点与适用性，整理表1、2、和3可以得到表5。

# 由表3、5可知：

（1）4月,TVDI方法在 $0 \sim 1 0 \mathrm { c m } _ { \cdot } 1 0 \sim 2 0 \mathrm { c m } _ { \cdot }$ $2 0 \sim 3 0 ~ \mathrm { c m }$ 深度所构建模型的相关系数 $R$ 均大于能量指数和SWEPDI方法。同时，TVDI方法在 $0 \sim 1 0$ $\mathrm { c m } _ { \mathrm { \scriptsize ~ 1 0 } } \mathrm { \sim } 2 0 \mathrm { c m } _ { \mathrm { \scriptsize , 2 0 } } \mathrm { \sim } 3 0 \mathrm { c m }$ 深度的平均相对误差分别为 $8 . 9 7 \% 1 0 . 9 5 \% \ . 1 5 . \ 1 3 \%$ ,各层平均相对误差$1 1 . 6 8 \%$ ;能量指数法在 $0 \sim 1 0 \ \mathrm { c m } \mathrm { . } 1 0 \sim 2 0 \ \mathrm { c m } \mathrm { . } 2 0 \sim$ $3 0 \ \mathrm { c m }$ 深度的平均相对误差分别为13. $84 \%$ 、$1 6 . 2 7 \%$ 、21. $41 \%$ ，各层平均相对误差 $1 7 . 1 7 \%$ ;SWEPDI法在 $0 \sim 1 0 \ \mathrm { c m } \ 1 0 \sim 2 0 \ \mathrm { c m } \ . 2 0 \sim 3 0 \ \mathrm { c m }$ 深度的平均相对误差分别为14. $9 6 \%$ 、21. $9 6 \%$ 、$2 3 . 4 5 \%$ ，各层平均相对误差 $2 0 . 1 2 \%$ ；由此可以知道,TVDI方法在各层土壤含水率的平均相对误差均小于SWEPDI法与能量指数法,并且均在 $10 \%$ 左右拟合效果较好。而SWEPDI法与能量指数法监测效果则相对较差。

表5三种方法的误差比较分析  
Tab.5Error analysis of three methods   

<html><body><table><tr><td>方法</td><td>深度</td><td>4月 △%</td><td>9月 △%</td><td>各期平均 △%</td></tr><tr><td>SWEPDI</td><td>0~10 cm</td><td>14.96</td><td>14.91</td><td>14.94</td></tr><tr><td rowspan="6">能量指数法</td><td>10~20 cm</td><td>21.96</td><td>18.37</td><td>20.17</td></tr><tr><td>20~30 cm</td><td>23.45</td><td>19.14</td><td>21.30</td></tr><tr><td>各层平均△%</td><td>20.12</td><td>17.47</td><td>18.80</td></tr><tr><td>0~10 cm</td><td>13.84</td><td>12.24</td><td>13.04</td></tr><tr><td>10~20 cm</td><td>16.27</td><td>15.67</td><td>15.97</td></tr><tr><td>20~30 cm</td><td>21.41</td><td>16.65</td><td>19.03</td></tr><tr><td rowspan="5">TVDI</td><td>各层平均△%</td><td>17.17</td><td>14.85</td><td>16.01</td></tr><tr><td>0~10 cm</td><td>8.97</td><td>10.85</td><td>9.91</td></tr><tr><td>10~20 cm</td><td>10.95</td><td>11.01</td><td>10.98</td></tr><tr><td>20~30 cm</td><td>15.13</td><td>14.23</td><td>14.68</td></tr><tr><td>各层平均△%</td><td>11.68</td><td>12.03</td><td>11.86</td></tr></table></body></html>

注：表格中的 $\Delta$ 为平均相对误差

（2）9月，TVDI在各层深度所构建模型的 $R$ 值均比能量指数法和SWEPDI方法的 $R$ 值稍大。 $T V _ { \overline { { \mathbf { \Gamma } } } }$ $D I$ 方法在 $0 \sim 1 0 \ \mathrm { c m } \ . 1 0 \sim 2 0 \ \mathrm { c m } \ . 2 0 \sim 3 0 \ \mathrm { c m }$ 深度的平均相对误差分别为 $1 0 . 8 5 \% . 1 8 . 0 1 \% \ . 1 9 . 2 3 \%$ ，各层平均相对误差为 $1 2 . 0 3 \%$ ;SWEPDI法在 $0 \sim 1 0$ $\mathrm { c m } { } _ { \mathrm { \Omega } , 1 0 } \sim 2 0 \ \mathrm { c m } { } _ { \mathrm { , } 2 0 } \sim 3 0 \ \mathrm { c m }$ 深度的平均相对误差分别为 $1 4 . 9 1 \% 1 8 . 3 7 \% 1 9 . 1 4 \%$ ,各层平均相对误差为 $1 7 . 4 7 \%$ ;能量指数法在 $0 \sim 1 0 \ \mathrm { c m } \ . 1 0 \sim 2 0 \ \mathrm { c m } \ .$ $2 0 \sim 3 0 ~ \mathrm { c m }$ 深度的平均相对误差分别为 $1 2 . 2 4 \%$ 、$1 5 . 6 7 \%$ ） $1 6 . 6 5 \%$ ，各层平均相对误差为 $1 4 . 8 5 \%$ ;由此可得，TVDI方法在各层的土壤含水率的平均相对误差均小于SWEPDI和能量指数方法，且各层平均相对误差为 $1 2 . 0 3 \%$ ,反演精度随着土层深度的增加而降低，但可以满足遥感反演精度要求。

总上所述，3种土壤含水率监测模型中SWEPDI模型的平均相对误差最低而TVDI模型最高，表明TVDI模型的土壤含水量估计值最接近真实值而SWEPDI模型的偏离程度最大;TVDI模型的相关系数最高，而SWEPDI最低，表明由TVDI模型反演得到的土壤含水量数据与观测数据间的相关程度最高，而SWEPDI最低。同时考虑到模型的简单、实用以及稳定性，可以确定TVDI模型是3种模型中最理想的监测模型。但是由于能量指数法计算公式中的$\textstyle A _ { 1 }$ 正是植被对近红外的强反射区的反照率，考虑到了高植被覆盖时植被反射作用的影响，同时也考虑到地表和植被冠层温度与土壤水分成反比的规律，所以能量指数法也不受应用下垫面限制的问题，对土壤旱情监测的精度比SWEPDI模型有所提高。

# 3.4斑块水平景观格局分析

选取稳定性最好的TVDI模型，提取毛乌素沙地腹部2016年4月、9月的TVDI指数，并参照干旱等级划分标准湿润( $0 < T V D I < 0 . 2 \$ ）、正常 $( 0 . 2 <$ $T V D I < 0 . 4 \$ ）、轻旱 $\mathit { ^ { \prime } 0 . 4 } < T V D I < 0 . 6 \mathit { ^ { \prime } }$ 、干旱 $( 0 . 6 <$ $T V D I < 0 . 8$ 、重旱 $\mathrm { ( 0 . ~ 8 < } T V D I < 1 \$ ），进行分级（图4）[16],从而分析不同旱情等级的景观格局变化。

对2016年4\~9月斑块类型上各景观指数的变化趋势进行分析，由表可看出， $\mathit { C A } , \mathit { N P }$ 从景观粒度层次揭示了景观破碎化程度。4\~9月旱情等级出现了“三减两增”的现象，其中湿润等级面积减少了4132.8，干旱等级、重旱等级面积减少了198441，74838.15；正常和轻旱等级面积增加，尤其以轻旱等级的面积最为显著，增加了261405.72。干旱等级的斑块数量NP从4月的4766个显著的增加到13 705个，增加了8939个。表明干旱等级的面积遭到不同程度的分割，转化为低旱情等级。这一主要原因为9月全旗降雨量稍多（图5)而导致，降雨量为 $3 9 1 ~ \mathrm { m m }$ 。PLAND度量斑块类型占整个景观面积的相对比例， $L P I$ 是某类型中最大斑块占整个景观面积的比例，可以作为确定优势景观元素的依据。2016年4\~9月正常、轻旱等级的PLAND呈上升趋势,其中轻旱等级的PLAND上升幅度最大，上升了$2 3 . 5 3 \%$ 。湿润、干旱、重旱等级的PLAND呈下降趋势，其中干旱等级的PLAND下降幅度最大，下降了$1 7 . 8 7 \%$ 。2016年4月、9月各旱情等级的LPI最大值都出现在PLAND的最大值处。说明低植被覆盖度的4月占优势旱情等级的为干旱等级；高植被覆盖度的9月占优势旱情等级的为轻旱等级。AREA_$C V$ 表示同种类型的斑块面积的差异程度。4月干旱等级的斑块面积变异系数最大，达到了6009.59。9月轻旱等级的斑块面积变异系数最大，达到了

![](images/3f11fb48c63fef7394f9824b3aa73c3646688962326651c8082eabf0747b405b.jpg)  
图42016年Landsat8反演TVDI空间分布状况  
Fig.4Spatial distribution of TVDI which inversed by Landsat8 in 2016

表6类型水平下不同旱情等级景观格局指数  
Tab.6The landscape pattern index of different drought conditions under the level of patch   

<html><body><table><tr><td>时间</td><td>等级</td><td>CA</td><td>PLAND</td><td>NP</td><td>LPI</td><td>AREA_CV</td><td>AI</td></tr><tr><td>2016.4</td><td>湿润</td><td>10 140.21</td><td>0.9130</td><td>1 719</td><td>0.0317</td><td>642.417 8</td><td>87.060 8</td></tr><tr><td rowspan="7"></td><td>正常</td><td>55 707.12</td><td>5.0151</td><td>3157</td><td>0.207 5</td><td>860.675 2</td><td>90.169 6</td></tr><tr><td>轻旱</td><td>229 137.30</td><td>20.628 6</td><td>6179</td><td>1.679 4</td><td>1 943.312 2</td><td>93.746 5</td></tr><tr><td>干旱</td><td>652 663.62</td><td>58.757 7</td><td>4 766</td><td>25.490 0</td><td>6 009.590 7</td><td>97.424 5</td></tr><tr><td>重旱</td><td>163 123.38</td><td>14.685 6</td><td>4 405</td><td>4.733 0</td><td>4 353.689 5</td><td>95.961 3</td></tr><tr><td>湿润</td><td>6 007.41</td><td>0.5408</td><td>2 445</td><td>0.0733</td><td>1 575.437 7</td><td>91.012 5</td></tr><tr><td>正常</td><td>71 713.35</td><td>6.456 2</td><td>10 792</td><td>0.172 9</td><td>866.404 6</td><td>87.845 2</td></tr><tr><td>轻旱</td><td>490 543.02</td><td>44. 162 4</td><td>8964</td><td>10.708 4</td><td>5 670.114 6</td><td>94.811 1</td></tr><tr><td>干旱</td><td></td><td>454 222.62</td><td>40.892 6</td><td>13 705</td><td>6.299 3</td><td>4 412.444 7</td><td>94.672 6</td></tr><tr><td>重旱</td><td></td><td>88 285.23</td><td>7.948 0</td><td>11 037</td><td>0.6186</td><td>2 184.242 5</td><td>91.769 7</td></tr></table></body></html>

![](images/b1fdcf0b5dbb45f9dca56341f0b8c051bf17800ddd01cfceaf276391f59c18a7.jpg)  
图52016年月降水量分布Fig.5Rainfall distribution in 2016

5670.11。反映出其内部面积具有较大的差异，而湿润、正常、旱情等级的斑块面积变异系数则一直较小，说明其面积差异不大。此外,从聚合度 $( A I )$ 来看，4月的干旱等级的聚合度达 $9 7 . 4 2 \%$ ,9月的轻旱等级的聚合度达 $9 4 . 8 1 \%$ ,其主要原因为这一年低植被覆盖度的4月的降雨量为 $0 ~ \mathrm { m m }$ ,处于干旱时期（图5）。

# 4结论

本研究在SWEPDI指数法、能量指数法与TVDI指数法3种监测方法的最优单一旱情指数选择的基础上，从而分析不同旱情等级的景观格局变化。虽然利用 $T _ { \mathrm { s } } { \mathrm { - } } N D V I$ 特征空间进行旱情监测已取得一定的进展，但对于覆盖较好的天然植被和农作物，使用NDVI造成的红光饱和问题比较严重，背景的土壤噪声也在一定程度上损害了NDVI的空间一致性，而土壤调节植被指数MSAVI相对NDVI更能描述植被覆盖度和土壤背景的优势。同时考虑到毛乌素沙地腹部地形、沙漠化、人为灌溉、降雨等复杂的地理环境，为了准确地反映干旱特征的目的，综合多源数据的干旱综合监测模型是研究复杂干旱监测问题的新途径。本研究采用的2个时相的遥感资料，仅代表着两个不同时点的现状水平，如果能够获得更加连续的遥感资料，则对研究更具有说服力。

土壤水分胁迫是制约毛乌素沙地生态环境和可持续发展的主要问题。开展区域尺度下大而积、高精度的土壤水分监测有利于旱情预报、气象水文等领域研究。本研究以毛乌素沙地腹部乌审旗为例，研究土壤水分的提取方法，并以此方法为基础，研究沙地腹部土壤水分的景观格局演变规律。得到如下结论：

（1）SWEPDI法与能量指数法进行土壤含水率监测的效果随着时间的变化而起伏较大,TVDI法监测土壤含水率效果的稳定性相对较好。同时，TVDI法监测土壤含水率精度要优于SWEPDI法与能量指数法，而能量指数法又稍微优于SWEPDI法。由此来确定TVDI的线性模型为本研究中最理想的拟合函数。

（2）拟合程度随着土层深度 $( 0 \sim 1 0 \ \mathrm { c m } \ . 1 0 \sim 2 0 \$ $\mathrm { c m } \ 、 2 0 \sim 3 0 \ \mathrm { c m }$ )的增加而呈现出整体降低趋势，而平均相对误差随着土层深度的增加而呈现出整体缓慢上升趋势，说明 $0 \sim 1 0 ~ \mathrm { c m }$ 土层深度的土壤含水率监测精度比 $1 0 \sim 2 0 ~ \mathrm { c m } \ : . 2 0 \sim 3 0 ~ \mathrm { c m }$ 土层深度的土壤含水率监测精度高，但相差不太大。

（3）4\~9月旱情等级出现了“三减两增”的现象，其中湿润等级面积减少了4132.8，干旱等级、重旱等级面积减少了198441，74838.15；正常和轻旱等级面积增加，尤其以轻旱等级的面积最为显著，增加了261405.72。其中4月和9月分别以干旱等级和轻旱等级为主,对应的其中LPI、AREA_CV、AI指数的值也都达到了最大。表明相较植被生长初期的4月而言，在较高植被覆盖且生长状况良好条件下的9月具有更高的土壤水分能力。

# 参考文献(References）

[1] BOWERS S,HANKS R J.Reflection of radiant energy from soils [J].Soil Science,1965,100(2):130-138.   
[2] KAHLE A B.A simple thermal model of the Earth's surface for geologic mapping by remote sensing[J].Geophys Res,1977,82: 1673-1680.   
[3] SANDHOLTI,RASMUSSEN K.ANDERSENJ.A simple interpretation of the surface temperature/vegetation index space for assessment of surface moisture status[J].Remote Sensing of Environment,2002,79:213- 224.   
[4] 陈斌,张学霞，华开,等.温度植被干旱指数TVDI在草原干旱 监测中的应用研究[J].干旱区地理，2013，36(5）：930-937. [CHEN Bin,ZHANG Xuexia,HUA Kai,et al.Application study of temperature vegetation drought index（TVDI） in grassland drought monitoring[J].AridLand Geography,2013,36(5）:930-937.]   
[5] 齐述华，王长耀，牛铮，等.利用温度植被旱情指数进行全国旱情 监测研究[J].遥感学报,2003,7（5）:420－427.［QI Shuhua, WANG Changyao,NIU Zheng,et al.Evaluating soil moisture status in China using the temperature/vegetation dryness index(TVDI) [J].Journal of Remote Sensing,2003,7(5）:420 -427.]   
[6] 杨磊,张梅，罗明良，等.基于MODIS NDVI的川中丘陵区植被 覆盖度景观格局变化[J].生态学杂志，2013，32（1)：171- 177.[YANG Lei,ZHANG Mei,LUO Mingliang,et al. Landscape pattern change of vegetation coverage in hilly area west China based on MODIS NDVI[J].Chinese Journal of Ecology,2013,32 (1):171-177.] [7］张建香，张勃,尹海霞,等.2000—2011年黄土高原植被景观格 局变化[J].生态学杂志,2013,32（2）：452-458.［ZHANG Jianxiang,ZHANG Bo,YIN Haixia,et al.Landscape pattern changes of vegetation coverage in Loess Plateau of northwest China in   
2000—-2011[J].Chinese Journal of Ecology,2013,32(2）:452-   
458.] [8］李恒凯,雷军,杨柳,等.基于Landsat 影像的离子稀土矿区植 被覆盖度提取及景观格局分析[J].农业工程学报，2016，32 (10）:267-276.[LI Hengkai,LEI Jun,YANG Liu,et al.Extrac tion of vegetation coverage and analysis of landscape pattern in rare earth mining area based on Landsat image[J].Transactions of the Chinese Society of Agricultural Engineering,2016,32(10）:267 -   
276.] [9］春风,洪园园,白海花,等.基于RS与GIS 的乌审旗植被景观 格局动态变化分析[J].草原与草业，2015,27（2)：12－19. [CHUNFeng,HONG Yuanyuan,BAI Haihua,et al.Analysis on the dynamic change of landscape patterns in Wushenqi Banner [J].Grassland and Prataculture,2015,27(2）:12-19.] [10］郭兵，姜琳,杨光，等.一种基于NIR-RED光谱特征空间的干 旱监测新方法［J].亚热带水土保持,2015,27（1)：10－14. [GUO Bin,JIANG Lin,YANG Guan,et al.A new monitoring method for drought based on NIR-RED spectral feature space[J]. Subtropical Soil and Water Conservation,2015,27(1):10-14.] [11］郑有飞,刘茜,王云龙,等.能量指数法在黑龙江干旱监测中的 适用性研究［J].土壤，2012，44（1）：149－157.［ZHENG Youfei,LIU Xi,WANG Yunlong,etal.Application of enemy index method on drought monitoring in Heilongjiang[J].Soils,2012,44 (1):149 -157.]   
[12]PRICE JC.On the analysis of thermal infrared imagery the limited utility of apparent thermal inertia[J].Remote Sensing of Environment,1985,18(1):59-73.   
[13］覃志豪,李文娟,徐斌,等.陆地卫星TM6 波段范围内地表比辐 射率的估计[J].国土资源遥感,2004，（3）：28-32.[QIN Zhihao,LI Wenjuan,XU Bin,et al.The estimation of land surface emissivity for Landsat TM6[J].Remote Sensing for Land & Resources,2004,(3):28 -32.]   
[14］王思楠,李瑞平,韩刚,等.基于多源遥感数据的TVDI方法在 荒漠草原旱情监测的应用[J].安徽农业大学学报,2017,44 (3）:458-464.[WANG Sinan,LI Ruiping,HAN Gang,et al. Application of the multi-source remote sensing data-based TVDI method in monitoring desert grassland drought[J]. Journal of Anhui Agricultural University,2017,44（3）:458-464.]   
[15］高彦净，谢余初,钱大文，等.甘肃白龙江流域植被覆盖度及景 观格局变化[J].水土保持研究,2015,22（1)：181-187.[GAO Yanjing,XIE Yuchu,QIAN Dawen,et al.Dynamic variations of vegetation coverage and landscape pattern in Bailongjiang Basin of southern Gansu[J].Research of Soil and Water Conservation, 2015,22(1):181-187.]   
[16］闫峰，王艳姣.基于Ts-EVI特征空间的土壤水分估算[J].生 态学报,2009,29（9）:4884-4891.[YANFeng，WANGYanjiao.Soil water estimation based on Ts-EVI feature space[J].Acta Ecologica Sinica,2009,29(9） :4884-4891.]

# Characteristics of the landscape changes under the hinterland drought conditions in Mu Us Sandland

WANG Si-nan， LI Rui-ping， HAN Gang， WANG Yao-qiang， HU Yong-ping， TIAN Xir(Inner Mongolia Agricultural University,Inner Mongolia,Hohhot O1ool8,Neimengu,China)

Abstract：At present the methods using remote sensing technology to monitor soil moisture content become popular. This paper selected three monitoring methods which are widely applied with beter stabilityand require less meteorological data,namelythe SWEPDIindex method,theenergy index methodandtheTVDIindex method,tobeerunderstandthecharacteristicsof the landscapechangesunderthehinterlanddroughtconditions inMuUs Sandland,Inner Mongolia,China.UsingLandsat8data in April2O16and September 2O16 as data source,each ofthe three methods was conductedalinear fiting withthe field surveydataaccording tothetime,thesoil depthandcorresponding soil moisturecontent.A comparison of the results from the models determined the more suitable model.At the same time,the change trend of soil moisture in 2 time phases was analyzed based on the plaque typeby using the landscape index. Theresults showed that the effectof TVDI index method is superior to both the SWEPDI index method and the energy index method,and the TVDI index method also solved theproblem thatexisted in continuously monitoring thesoil moisturecontent.The TVDI index method issuitable forall kindsof vegetationconditionsand various soildepth in droughtmonitoring.In adition,six landscape indexes were chosen to analyze the landscape patern changes in April 2016 and September 2Ol6 at diferent levels of drought,and it is found that the PLAND reached $5 8 . 7 6 \%$ in April,and it became $4 4 . 1 6 \%$ in September when it is at the light drought grade.Both were dominant as other indexes like $L P I$ ， $A R E A \_ C V$ and AI index all reached the maximum value.The drought condition was improved obviously.

Key words:SWEPDI index method；energy index method；drought index of temperature vegetation；landscape pattern ;