# 2000—2019年新疆积雪终日时空变化特征

买合木提江·维吉旦¹，玉素甫江·如素力}²，仇忠丽1

（1.新疆师范大学地理科学与旅游学院,新疆 乌鲁木齐830054;2.新疆干旱区湖泊环境与资源重点实验室，新疆 乌鲁木齐 830054)

摘要：基于Google Earth Engine(GEE)遥感云平台,利用2000—2019年MODIS积雪产品资料提取和计算新疆积雪终日信息，利用趋势分析，变异系数等方法分析了新疆积雪终日时空变化特征和变化趋势。结果表明：(1)新疆积雪终日以天山为界，天山以北长于南部，山区为积雪终日的高值区,盆地为积雪终日的低值区。北疆准噶尔盆地和伊犁河谷积雪终日在75\~114d之间，南疆塔里木盆地在0\~31d之间属于低值区。阿尔泰山脉、天山山脉和昆仑山脉区域在 $2 2 4 { \sim } 3 6 5 \mathrm { ~ d ~ }$ 之间属于高值区。(2）南疆和北疆积雪终日有明显的时空差异，2000—2019年北疆准噶尔盆地和高海拔山脉地区积雪终日有明显的推迟趋势，推迟幅度达到 $1 4 \mathrm { d }$ ，占新疆总面积的 $8 \%$ 。南疆塔里木盆地和东疆区域有明显的提前趋势，提前幅度达到16d约占新疆总面积的 $4 4 \%$ 。塔里木盆地和准噶尔盆地具有相反的变化趋势。(3)新疆积雪终日年际变化差异显著，天山中段和北疆积雪终日出现不稳定状况，天山中段2002—2009年总体上呈现“M"型的特点，即多年积雪消融日年均值中出现明显的波峰和波谷，北疆2009—2019年积雪终日有较大的年际变化呈现出不稳定状况，出现明显的波峰和波谷，年际变化较大。

关键词：GEE云计算；积雪终日；时空分布；变化趋势文章编号：

积雪是冰冻圈的主要组成部分，具有较大的年际变化。季节性融雪的变化对世界的气候、水文、生态和人类进程产生了相当大的影响。年度季节性融雪的时间以及该时间的任何潜在变化都具有广泛的生态意义，因此会影响人类的生计。在高纬度和高山区，在水文循环最重要的阶段中，冬季积雪的年融水为全球约1/6人口提供了主要的水流和地下水补给源[1-2]。北极和南极融雪的时间影响了生长期，而且整个冬季持续的积雪使植被免受恶劣温度和风的影响[3-4]。这种季节性的水资源是在地球变暖的气候下变化最快的水文系统之一，将广泛影响区域经济、生态系统功能并增加潜在的洪灾危害[5-6]。预期较高气温将改变降水的类型和开始时间；包括北美落基山脉在内的多个地区已经测算出积雪量减少，而且气温升高使降水从降雪转向降雨,导致融雪更早发生[7-8]。冰雪融水是新疆干旱地区农业的命脉，区域气候变化引起的融雪变化对春夏季河川径流产生影响，将对干旱地区的经济和脆弱的生态环境造成严重后果，甚至导致旱涝灾害频发[9-13]。春季融雪时间异常正在对包括农业在内的水资源可持续性造成严重威胁[14],甚至会引起水文极端事件，比如春季洪水[15]。每年季节性融雪的时间以及时间上的任何潜在变化都具有广泛的生态影响，因此会影响人类的生计，尤其是在高纬度地区和山区系统及其周围地区。高山雪融水是新疆内陆河流水资源的主要来源[16]。因此,近些年来，对新疆积雪的研究较多，相关研究结果显示新疆地区积雪最大深度呈现增加趋势，而积雪覆盖期变短[17-18],但大都主要针对新疆局部区域,如北疆、天山山区[19]、阿勒泰[20]等进行探讨和研究。易颖等[21]

# 干吴区地理

使用MODIS数据产品提取了叶尔羌河流域积雪物候参数，系统地分析了其空间分布与变化特征。梁鹏斌等2利用遥感数据资料和气象数据，分析祁连山积雪面积动态变化特征，并与气温降水关系进行了分析和研究。目前大多数国内外研究主要聚焦于流域尺度的积雪特性，融雪产流过程及融雪径流模拟等[23-28]。针对新疆积雪消融过程的研究,前人多采用站点积雪数据与站点气象数据(点-点)的方法开展新疆融雪变化及径流模拟研究，大多数基于流域尺度的以雪特性、融雪产流过程及融雪径流模拟等，并取得了一定的成果。然而针对新疆积雪终日利用遥感技术研究较少，以年为时间尺度的长时间序列的积雪终日时空变化趋势研究则更少。研究新疆积雪终日对气候变暖的响应，不仅对亚洲区域和全球气候变化的诊断具有重要意义，也能为流域下游的农业，生态以及防灾减灾等提供信息服务。

本文基于GEE的云计算平台，利用MODIS每日积雪产品，像素为单位计算每年的无雪日，跟踪积雪终日年际变化，在长时间尺度上分析新疆积雪终日的时空变化，探讨近20a全球气候变暖背景下新疆各地积雪终日的时空变化规律，从而更好地了解新疆积雪终日时空变化如何响应气候变化，为应对气候变化以及融雪水资源的优化管理提供理论依据。

# 1研究区概况

新疆地处亚欧大陆中心、中国西北边陲，地处$7 3 ^ { \circ } 4 5 ^ { \prime } { \sim } 9 6 ^ { \circ } 3 9 ^ { \prime } \mathrm { E } . 3 4 ^ { \circ } 3 4 ^ { \prime } { \sim } 4 9 ^ { \circ } 1 7 ^ { \prime } \mathrm { N }$ ，总面积约 $1 . 6 6 \times$ $1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ 。新疆北为阿尔泰山脉，南为昆仑山脉，天山山脉横亘中部，把新疆分隔为北疆和南疆两大区域，北疆的准噶尔盆地和南疆的塔里木盆地与此三座高山构成了“三山夹两盆”的独特地貌格局（图1)。新疆具有典型的内陆干旱和半干旱气候特征，冰川积雪覆盖的山脉环绕在盆地的边缘，而沙漠和湖泊则在盆地中广泛分布。新疆隆冬时期积雪覆盖面积为 $1 0 0 \times 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ ，冬季雪贮量在全国最为丰富达 $1 8 1 . 8 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,水当量占全国冬季平均积雪贮量的$3 3 . 9 \% ^ { [ 2 9 ] }$ 。全疆降水量的时空分布不均匀且年均降水量较少，约 $1 4 5 ~ \mathrm { m m }$ ,其中北疆约 $1 5 0 { \sim } 2 0 0 ~ \mathrm { m m }$ ，南疆不到 $1 0 0 ~ \mathrm { m m }$ ,蒸发量为 $2 0 0 0 { \sim } 2 5 0 0 ~ \mathrm { m m }$ ,干旱度为$4 \mathrm { \sim } 1 6 ^ { [ 3 0 ] }$ 。由于特殊的地理位置、地形和气候条件,新疆总体上生态系统比较脆弱、敏感。

# 2数据与方法

# 2.1数据来源

（1）积雪数据：本文使用的MODIS全球每日积雪产品数据来自于美国国家冰雪数据中心(https://

注：该图基于新疆维吾尔自治区自然资源厅标准地图服务网站下载的审图号为新S(2021)046号的标准地图制作，底图边界无修改。下同。

![](images/faa566bd1560a60f638abcbc79ad3f94e3a588b249466e9a1458fb98360bbc3c.jpg)  
图1研究区示意图  
Fig.1Sketch map of the research area

nsidc.org/data/MOD10A1)的MODIS/Terra合成积雪产品MODIS10A1,空间分辨率为 $5 0 0 \mathrm { m }$ ;时间范围为2000年1月1日—2019年12月31日。积雪覆盖是使用归一化积雪指数(Normalizeddifference snow in-dex，NDSI)和一系列旨在减轻错误并标记不确定的积雪检测结果来识别积雪。积雪终日为每年最后一次出现积雪的日期,积雪终日是指陆面上无任何像元被识别为雪覆盖的日期，文中将当年1月1日开始至12月31日结束定义为一个积雪年。

(2）DEM数据：DEM数据由美国国家航空航天局(NASA)与日本经济产业省(METI)合作完成的先进星载热发射和反射辐射仪全球数字高程模型AS-TERGDEMV2.0(分辨率为 $3 0 ~ \mathrm { m } )$ 数据下载获取。对高程数据进了投影转换，重采样等处理，最后统一为 $5 0 0 \mathrm { ~ m ~ }$ 空间分辨率，得到与积雪数据分辨率和投影系统相同的空间数据。

# 2.2 研究方法

本文积雪终日参数是使用平台GoogleEarthEngine（GEE)从MODIS每日降雪产品MOD10A1中分别逐像元为单位识别得出，GEE是用于地球观测数据分析的云平台[31]。用户可以在https://earthen-gine.google.com上注册后访问平台。在该平台上，MOD10A1产品与其他卫星图像和产品（例如MO-DIS、Landsat、Sentinel-1和Sentinel-2)在全球范围内被使用并经常更新。如果栅格和矢量数据不直接可用，也可以很容易地将其在平台中提取。在本研究中，使用GEE编程语言基于Web的集成开发环境IDE计算积雪终日参数。代码开发包括数据提取、预处理、积雪终日的计算、统计分析以及最终地图的导出都在该平台上进行。由于长时间序列(新疆每日数据)的计算可能非常密集，因此采用分层解决方案。首先，动态数据处理被用于代码开发和调试。其次，将每年和一年中不同时期的积雪产品另存，然后对这些文件进行最终的统计分析。

（1）遥感数据处理。基于GEE云平台，根据影像的获取时间、影像质量，快速完成时间序列遥感数据的获取和预处理，包括云、阴影掩膜、拼接、裁剪等。本文以像素为单位计算每年的积雪终日，最终在经过以下几项处理后进行统计分析：掩膜很少被雪覆盖的像素，只分析在当年1月1日到12月31日至少有14d被 $1 0 \%$ 的雪覆盖的像素。掩膜长时间被雪覆盖的像素，在一年内 $1 0 \%$ 被雪覆盖的日数不能超过124d的像素。掩膜遥感影像上的水，仅分析在陆面上的像素。最终经过以上3种处理后再提取和统计当年1月1日开始 $0 \%$ 被雪覆盖的最后一天。并基于行政边界剪裁得到2000—2019年的新疆积雪终日数据，最后将影像导出到本地。

（2）一元线性趋势分析。一元线性回归模型可以模拟空间上每个像元的积雪终日时间变化，斜率(Slope)表示积雪终日时间变化的趋势，用最小二乘法来计算，公式如下：

$$
{ \mathrm { S l o p e } } = { \frac { n \displaystyle \sum _ { i = 1 } ^ { n } ( i \times p _ { i } ) - \sum _ { i = 1 } ^ { n } i \sum _ { i = 1 } ^ { n } p _ { i } } { n \displaystyle \sum _ { i = 1 } ^ { n } i ^ { 2 } - ( \sum _ { i = 1 } ^ { n } i ) ^ { 2 } } }
$$

式中： $n$ 为累计年数， $n { = } 2 0 ; p _ { i }$ 为第 $i$ 年融雪时间值;Slope为一元线性回归方程的斜率，是 $n$ 年连续年份的趋势，当Slope ${ > } 0$ 表示随时间 $i$ 的增加,积雪终日处于推迟趋势，反之则是提前趋势。

（3）变异系数法。利用变异系数(Coefficientofvariation, $C _ { \mathrm { v } , }$ )对研究区2000—2019年积雪终日的空间格局变化进行稳定性分析， $C _ { \mathrm { v } }$ 作为反映观测值变异程度的一个重要指标，为标准差与多年平均值的比值。计算公式如下：

$$
C _ { \mathrm { v } } = { \frac { S _ { \mathrm { S M } } } { \overline { { \mathrm { S M } } } } }
$$

式中： $S _ { \mathrm { S M } }$ 为每个栅格单元的标准差； $\overline { { \mathrm { S M } } }$ 为积雪终日的多年平均值。

# 3结果与分析

# 3.1新疆积雪终日的空间变化特征

根据积雪终日的分布情况，将新疆分为北疆、南疆和天山3个区域进行积雪终日的空间分析。如图2所示，2000—2019年新疆积雪终日空间分布存在明显的差异，整体上呈现出北疆的积雪终日晚于南疆，山区晚于盆地，且两者的空间分布状况存在明显的差异。北疆阿尔泰山脉一带、伊犁河谷以及天山西段、昆仑山一带积雪终日比其他区域显著晚，在299\~365d之间。北疆准噶尔盆地和伊犁河谷积雪终日明显晚于南疆，在 $7 6 { \sim } 1 5 2 \mathrm { d }$ 之间。哈密以及南疆塔里木盆地积雪终日明显早于北疆，在 $0 \sim$ 61d之间。

根据积雪终日的空间分布和变化情况可以看出(图2)，随着气候变暖北疆和南疆、山区和盆地积

# 干辛区地理

![](images/2eb55b854d0c29f99b41e6cf849d42c68efc5e845416c24118e5ca74c54505fd.jpg)  
图2新疆积雪终日多年平均与年际变化空间分布

Fig. 2 Spatial patterns of annual average and annual change in snow cover cessation day of Xinjiang雪终日出现不同的变化。南疆塔里木盆地和东疆区域积雪终日从2005年开始逐渐提前，北疆准噶尔盆地和伊犁河谷逐渐推迟，北疆和南疆高海拔山区积雪终日也逐渐推迟，由此可见在不同的海拔高度和不同的经纬度积雪终日的变化有所不同。

# 3.2新疆积雪终日研究期初终对比变化特征

根据积雪终日数据中选择2019年与2001年2a数据并计算出两者之差，比较积雪终日初终的差异（图3）。由图3可以看出，2019年和2001年存在明显的差异，整体上呈现出2019年南疆塔里木盆地、阿尔泰山脉一带以及东疆积雪终日比2001年提前，而北疆准噶尔盆地、天山中段和昆仑山脉一带比2001年有明显的推迟。北疆准噶尔盆地和南疆塔里木盆地空间分布状况恰好相反，塔里木盆地2019年积雪终日比2001年提前，准噶尔盆地比2001年推迟。北疆和南疆，高海拔山区和盆地变化特征恰好相反。

2019年和2001年新疆积雪终日差异中，积雪终日提前的区域占新疆总面积的 $2 6 \%$ ,积雪终日推迟的区域占新疆总面积的 $1 5 \%$ ,基本不变的区域占总面积的 $5 9 \%$ 。新疆积雪终日提前的面积大于推迟

![](images/2dea5f450bcd33715cd55ad65891022c1734637892d5da66f5d64c84feccda25.jpg)  
图3新疆积雪终日初终差异空间分布  
Fig.3Spatial pattern of the difference in snow cover cessation day of Xinjiang

的面积。

# 3.3新疆积雪终日趋势分析

图4表示近20a来新疆积雪终日变化趋势空间分布情况。从图4中可以看出，积雪终日在准噶尔盆地西部和南部、阿尔泰山脉一带、天山山脉和昆仑山脉部分高海拔区域有推迟趋势，最大推迟幅度达到16d,面积占新疆总面积的 $8 \%$ 。准噶尔盆地中部、伊犁河谷西部和塔里木盆地东部基本不变，面积占新疆总面积的 $4 8 \%$ ;积雪终日在塔里木盆地、东疆地区、准噶尔盆地北部区域、天山南坡和部分高海拔区域有提前趋势，轻微提前和明显提前区域面积约占新疆总面积的 $4 4 \%$ 。积雪终日明显提前地区主要分布在天山南坡、塔里木盆地西北地区和东疆地区，提前幅度达到 $1 4 { \mathrm { ~ d ~ } }$ 。积雪终日在南疆塔里木盆地和东疆等区域总体上有提前趋势，北疆准噶尔盆地积雪终日呈现提前趋势或保持不变。在阿尔泰山脉一带、天山山脉中部、昆仑山脉等区域，积雪终日总体上呈现提前趋势，只有部分区域存在轻微推迟趋势。新疆积雪终日基本不变的区域面积占新疆总面积的 $4 8 \%$ ,提前趋势的区域面积占新疆总面积的 $4 4 \%$ ，推迟趋势的区域面积占新疆总面积的 $8 \%$ 。新疆积雪终日呈现提前趋势的区域面积明显大于推迟趋势的区域面积。

![](images/91c9a66a6c153159f2b594d2e3543e724e5bb2f8bdcdad5f451adf1d345da95a.jpg)  
图4近20a新疆积雪终日变化趋势  
Fig.4Variation trend of the snow cover cessation day in Xinjiang in recent 2O years

# 3.4积雪终日年际波动程度

图5表示经波动值栅格计算后得到的新疆近20a的积雪终日年际波动程度。本文将 $C _ { \mathrm { v } }$ 值定义为显著波动，轻微波动和中度波动3个波动区间，具体分类情况见表1。

新疆积雪终日整体呈现中度波动居多，中度波动和显著波动接近的特征。积雪终日呈现显著波动的面积占新疆总面积的 $2 6 . 1 2 \%$ ，主要分布在南疆塔里木盆地中部和南部;呈现中度波动的面积占总面积的 $4 0 . 3 1 \%$ ，主要分布南疆；呈现轻微波动的面积占总面积的 $3 3 . 5 7 \%$ ，主要分布在北疆。由此可见，新疆积雪终日近 $2 0 \textrm { a }$ 来不稳定，南疆波动性最大。

# 3.5新疆积雪终日的年平均时间变化特征

根据积雪终日的分布情况，将新疆分为北疆、南疆和天山中段3个区域进行积雪终日的时间序列分析；根据天山中段、北疆、南疆积雪终日数据，分别计算了天山中段、北疆、南疆区域内积雪终日的年平均值。从图6中可以看出，天山中段区域内积雪终日年平均值2001年和2004年开始增加，2003年和2006年降低，天山中段积雪终日随年际变化显著，呈现少见的"M"特征，即多年积雪年份中明显的波峰和波谷各有2个(图6a)，波峰位置出现在2003年和2006年，波谷位置则出现在2004年和2009年，之后天山中段积雪年均值呈现不稳定状况。北疆积雪终日年均值从2000—2006年基本稳定70\~80d之间，2006年开始出现不稳定状况，2006—2008年积雪终日年均值迅速减少，之后2008一2010年迅速上升，积雪终日年均值增加,北疆2008—2019年呈现不稳定状况(图6b)。根据南疆积雪终日数据，计算了南疆区域内积雪终日的年平均值，从结果可以

![](images/a5f557de992e4e17406794bd839b34e619d1e2348b0fe20783978d891a8cb943.jpg)  
干旱区地理  
图5新疆年际积雪终日的波动程度

表1新疆年际积雪终日的 $C _ { \mathrm { v } }$ 空间分布分类  
Tab.1 Classification of $C _ { \mathrm { v } }$ spatial distribution of interannual snow cover cessation day in Xinjiang   

<html><body><table><tr><td>类型</td><td>波动程度</td><td>C取值范围</td><td>像元数</td><td>面积比列/%</td></tr><tr><td rowspan="3">积雪终日</td><td>轻微波动</td><td>0.037<C≤1.038</td><td>2909778</td><td>33.57</td></tr><tr><td>中度波动</td><td>1.038<C≤2.320</td><td>3493170</td><td>40.31</td></tr><tr><td>显著波动</td><td>2.320<C≤4.514</td><td>2263823</td><td>26.12</td></tr></table></body></html>

注：C为变异系数。

![](images/1b24f607b5d4cc56f4381ded6997c43db870d36c503ef7b6639d17e51e3394d5.jpg)  
Fig.5Variation coefficient of interannual snow cover cessation day in Xinjiang   
图62000—2019年新疆积雪终日年平均时间序列变化

Fig.6Variations of the annual average snow cover cessation day in Xinjiang from 2ooo to 2019看出，南疆2003年开始积雪终日年均值增加，2006年达到最高值之后逐渐减少2007年年均值最小，2003—2009年呈现不稳定状况（图6c）。

![](images/2523b198537897555207a341b00b73f22c0668a4ac34a46c956f3cba0edce1d5.jpg)  
注：红色表示集中分布的区域，红至蓝表示集中分布逐渐减少。  
图72000—2019年新疆积雪终日多年均值与海拔高度的关系  
Fig.7Relationshipbetween themulti-year mean valueofsnowcovercessationdayandaltude in Xinjiang from 200 to 2019

# 3.6新疆积雪终日与海拔高度之间的关系

利用DEM数据和积雪终日多年平均数据进项了分析和研究，新疆年均积雪终日与海拔高度之间的关系中(图7)，新疆南疆、北疆和天山中段积雪终日在不同的海拔高度上具有较大的差异性。北疆大部分积雪终日主要分布在海拔高度为150\~1000m的区域，积雪终日为 $6 0 { \sim } 9 0 \mathrm { d }$ 之间，积雪终日随着海拔高度的升高且呈增加的趋势。南疆大部分积雪终日主要分布在海拔高度为 $9 0 0 { \sim } 1 0 0 0 \mathrm { m }$ 的区域,积雪终日为0\~25d之间，海拔高度大于 $3 0 0 0 \mathrm { m }$ 的一部分区域随着海拔高度增加积雪终日开始增加，但大部分高海拔区域在 $0 { \sim } 2 0 \mathrm { d }$ 之间，主要跟降水气流来源密切相关。天山中段降水量少的区域积雪终日主要分布在海拔高度为 $5 0 0 { \sim } 1 5 0 0 ~ \mathrm { m }$ 的区域，积雪终日是 $0 { \sim } 3 0 \mathrm { d }$ 之间。天山中段降水量高区随着海拔高度的增加积雪终日天数增加明显，积雪终日主要出现在海拔高度 $2 0 0 { \sim } 1 5 0 0 \ \mathrm { m }$ 区域，积雪终日为$7 5 { \sim } 1 0 0 \mathrm { d }$ 。北疆积雪终日与海拔高度线性相关性较强0.35，其次是天山中段为0.20，最低的南疆为0.18。

# 4讨论

本文仅结合遥感时间序列数据对新疆积雪终

# 干吴区地理

日时空分布特征进行了分析与研究，今后的工作中还需要着重将积雪遥感数据与其他辅助资料相结合对新疆积雪期，积雪厚度的变化和趋势进行深入研究。此外，积雪终日年均值呈现出“M"型特征的原因及其形成机理不甚明朗，有待今后进一步深入研究。本研究只对全年的积雪终日时空变化特征进行了分析，未来有必要增加年、季尺度气象因子与积雪终日的相关性研究。同时，也需要采用更长时间序列的积雪数据，对新疆积雪终日时空变化规律及积雪时空变化特征与气候因子之间的响应关系进行更加深入的研究。

新疆积雪终日时空变化特征中南疆2004—2005年呈现不稳定状况，之后南疆积雪终日变化较稳定。新疆积雪终日整体上呈现出的不稳定状况可能与新疆的特殊地势、特殊地貌、研究数据采集时间序列有关。在某种程度上，这不仅反映了新疆积雪终日年内变化的不稳定性，也表现出不同区域积雪变化的地域特殊性。积雪终日年均值和海拔高度之间的关系而言，南疆、北疆和天山中段积雪终日在不同的海拔高度上具有较大的差异性，主要跟降水气流来源密切相关。在全球气候变暖的背景下，新疆气候也在经历着显著变暖，可以看出全球气候变暖对新疆不同区域积雪终日的影响有所不同。

# 5结论

（1）新疆2000—2019年积雪终日具有明显的空间分异特征，积雪终日空间分布体现北疆大于南疆、东部大于西部的分布特征。北疆阿尔泰山一带、伊犁河谷和准噶尔盆地以及天山中段和南疆高海拔区域积雪终日较长，哈密以及南疆塔里木盆地低海拔区域积雪终日较短，北疆的积雪终日分布明显长于南疆的积雪终日。根据积雪终日多年变化可以看出，从2005年开始南疆塔里木盆地积雪终日逐渐缩短，北疆积雪终日逐渐变长，空间分布与多年情况有明显的变化。

（2）根据2019年和2001年新疆积雪终日年度差异变化特征中可以看出：2019年和2001年积雪终日提前的区域面积占新疆总面积的 $2 6 \%$ ,主要分布在南疆塔里木盆地和阿尔泰山脉一带和东疆区域。基本不变的区域面积占新疆总面积的 $5 9 \%$ ，积雪终日推迟的区域面积占新疆总面积 $1 5 \%$ ，主要分布在北疆准噶尔盆地、天山中段和昆仑山脉一带。北疆准噶尔盆地、天山中段和昆仑山脉一带积雪终日2019年比2001年有明显的推迟特征。

（3）根据2000—2019年新疆积雪终日趋势变化来看，积雪终日提前的区域面积占新疆总面积的$4 4 \%$ ，主要分布在南疆塔里木盆地和东疆。积雪终日延迟的区域面积占新疆总面积的 $8 \%$ ，主要分布在阿尔泰山脉、准噶尔盆地西部、天山中段、北疆和南疆高海拔山区。积雪终日不变的区域面积占新疆总面积的 $4 8 \%$ ,主要分布在准噶尔盆地中部。南疆塔里木盆地和北疆准噶尔盆地有明显的相反趋势。从年际波动程度上看，新疆积雪终日近 $2 0 \mathrm { a }$ 来呈现不稳定状况;按不同地理位置，北疆轻微波动，南疆波动性最大，东疆呈现中度波动。

(4)时间上，2000—2019年北疆和天山中段积雪终日年均值变化较为明显，天山中段呈现"M"型的波动特点，年均值在2003年和2006年处于高位水平，在2009年处于低谷水平。北疆2006年开始呈现不稳定状况，2008—2015年积雪终日年均值迅速减少处于低谷水平，2010年积雪终日年均值处于高位水平。北疆随着海拔高度增加积雪终日变长，南疆和天山中段积雪终日与海拔高度之间的相关性较复杂。

# 参考文献(References)

[1] Barnhart TB,Molotch NP,Livneh B,etal.Snowmelt rate dictates streamflow[J].Geophysical Research Letters,2016,43(15):8006- 8016.   
[2] Bengtsson L. Snowmelt estimated from energy budget studies[J]. Hydrology Research,1976,7(1): 3-18.   
[3] Duchesne L,Houle D,D'Orangeville L. Influence of climate on seasonal patterns of stem increment of balsam fir in a boreal forest of Quebec,Canada[J].Agricultural and Forest Meteorology,2012, 162: 108-114.   
[4] Kudo G,Nordenhall U,Molau U.Effects of snowmelt timing on leaf traits,leaf production,and shoot growth of alpine plants: Comparisons along a snowmelt gradient in northern Sweden[J]. Coence, 1999,6(3): 439-450.   
[5] Solomon S,Qin D,Manning M,et al.Climate change 2OO7: The physical science basis.Contribution of working group I to the fourth assessment report of the intergovernmental panel on climate change (IPCC)[J]. Computational Geometry,2007,18(2): 95-123.   
[6] Beniston M.Impacts of climate change on water and associated economicactivitiesintheSwissAlps[J].JournalofHydrology, 2010,412: 291-296.   
[7]Clow D W. Changes in the timing of snowmelt and streamflow in Colorado: A response to recent warming[J]. Journal of Climate, 2010,23(9): 2293-2306.   
[8]Harpold A A,Brooks PD, Rajogopalan S,et al. Changes in snowpack volume and snowmelt timing in the Intermountain West[J]. Water Resources Research,2012,48(11): 1-11.   
[9]魏月.北疆区域积雪深度变化的遥感监测研究[D].乌鲁木齐: 新疆师范大学,2010.[Wei Yue.Remote sensing monitoring of snow depth change in north part of Xinjiang[D]. Urumqi: Xinjiang Normal University,2010.]   
[10] 仇家琪,孙希华.天山积雪初步研究[J].干旱区地理,1992,15 (3): 9-21.[Qiu Jiaqi, Sun Xihua. Preliminary study on snow cover in the Tianshan Mountain[J].AridLand Geography,1992,15(3): 9-21.]   
[11] 张一驰,李宝林,包安明,等.开都河流域融雪径流模拟研究[J]. 中国科学:地球科学,2006,36(增刊2):24-32.[Zhang Yichi,Li Baolin,Bao Anming,et al. Simulation study on snowmelt runoff in Kaidu River Basin[J]. Scientia Sinica (Terrae),2006,36(Suppl.2): 24-32.]   
[12] 杨绍富.融雪过程中水热耦合实验研究——以军塘湖流域为例 [D].乌鲁木齐:新疆大学,2009.[Yang Shaofu.The study of water and heat coupling experimentin snow melt processing: Take Juntang River Basin Watershed in northern slope of Tianshan Mountains as an example[D]. Urumqi: Xinjiang University,2009.]   
[13] 岳春芳,何训江,艾丽米古丽·艾萨.金沟河流域水权分配及转 让研究[J].水资源与水工程学报,2012,23(3):48-50.[Yue Chunfang,He Xunjiang,Aisha Ailimiguli. Research on the allocation and transfer of water rights in Jingouhe River Basin[J]. Journal of Water Resources and Water Engineering,2012,23(3): 48-50.]   
[14]Qin Y,Abatzoglou JT, Siebert S,et al. Agricultural risks from changing snowmelt[J]. Nature Climate Change,2020,10(5): 459- 465.   
[15]Diffenbaugh N S,Scherer M, Ashfaq M. Response of snow-dependent hydrologic extremes to continued global warming[J].Nature Climate Change,2013,3(4): 379-384.   
[16] 唐尔泗,程国栋,董增川.中国西北干旱区冰雪水资源与出山径 流[M].北京:科学出版社,2002:1-2.[Tang Ersi, Cheng Guodong, Dong Zengchuan. Snow and ice water resources and mountain runoff in arid areas of northwest China[M]. Beijing: Science Press, 2002: 1-2.]   
[17]王秋香,魏文寿,王金民.新疆北疆最大积雪深度EOF展开场 的时间变化规律[J].冰川冻土,2008,30(2):244-249.[Wang Qiuxiang,Wei Wenshou,Wang Jinmin.Temporal variation of the maximum snow cover depth in north Xinjiang derive from EOF[J]. Journal of Glaciology and Geocryoiogy,2008,30(2): 244-249.]   
[18]Guo L P,Li L H.Variation of the proportion of precipitation occurring as snow in the Tianshan Mountains,China[J]. International Journal of Climatology,2015,35(7): 1379-1393. [19] 秦艳,丁建丽,赵求东,等.2001—2015年天山山区积雪时空变 化及其与温度和降水的关系[J].冰川冻土,2018,40(2):249-   
260.[Qin Yan,Ding Jianli, Zhao Qiudong,etal. Spatial-temporal variation of snow cover in the Tianshan Mountains from 2O01 to   
2015,and its relation to temperatureand precipitation[J]. Journal of Glaciology and Geocryology,2018,40(2): 249-260.] [20] 王国亚,毛炜峰,贺斌,等.新疆阿勒泰地区积雪变化特征及其 对冻土的影响[J].冰川冻土,2012,34(6):1293-1300.[Wang Guoya, Mao Weiyi,He Bin,et al. Changes in snow covers during 1961—   
2010anditsfetsofrozgroundinlaegn,XigJ]. Journal of Glaciology and Geocryology,2012,34(6): 1293-1300.] [21] 易颖,刘时银,朱钰,等.2002—2018年叶尔羌河流域积雪时空 变化研究[J].干旱区地理,2021,44(1):15-26.[Yi Ying,Liu Shi yin, Zhu Yu,et al.Spatiotemporal variation of snow cover in the Yarkant River Basin during 2002—2O18[J].Arid Land Geography, 2021,44(1): 15-26.] [22] 梁鹏斌,李忠勤,张慧.2001—2017年祁连山积雪面积时空变 化特征[J].干旱区地理,2019,42(1): 56-66.[Liang Pengbin,Li Zhongqin, Zhang Hui. Temporal-spatial variation characteristics of snow cover in Qilian Mountains from 2001 to 2017[J].Arid Land Geography,2019,42(1): 56-66.] [23] 沈永平,苏宏超,王国亚,等.新疆冰川、积雪对气候变化的响应 (I):水文效应[J].冰川冻土,2013,35(3):513-527.[Shen Yongping,Su Hongchao,Wang Guoya,et al.The responses of glaciers and snow cover to climate change in Xinjiang (I): Hydrological effect[J].Journal of Glaciology and Geocryology,2013,35(3): 513-   
527.] [24] 刘吉强.基于空间分析法的新疆融雪洪水径流模拟[J].黑龙江 水利科技,2020,48(10):17-20.[Liu Jiqiang.Runoff simulation of snowmelt flood in Xinjiang based on spatial analysis method[J]. Heilongjiang Water Conservancy Science and Technology，2020,   
48(10): 17-20.] [25] 杨金明,李诚志,房世峰,等.新疆地区季节性融雪洪水模拟与 预报研究[J].新疆大学学报(自然科学版),2019,36(1):80-88. [Yang Jinming,Li Chengzhi,Fang Shifeng,et al. Simulation and forecastofseasonalsnowmeltflodin XinjiangJ].Joualof Xijiang University (Natural Science Edition),2019,36(1): 80-88.] [26] 王冉旋.基于气象数值预报的高精度融雪径流预报技术研究 [J].科技创新导报,2019,16(32): 21-23.[Wang Ranxuan.Research on high-precision snowmelt runoff prediction technology based on meteorological numerical prediction[J]. Science and Technology Innovation Herald,2019,16(32): 21-23.] [27] 张云云,张毓涛,师庆东,等.天山北坡中段草地,林地积雪消融 过程的定量化分析[J].水土保持学报,2019,33(3):108-114. [Zhang Yunyun, Zhang Yutao, Shi Qingdong,et al. Quantitative analysis of snow melting process in grassland and forest land on the middle section of northern slope of Tianshan Mountain[J]. Journal of Soil and Water Conservation,2019,33(3): 108-114.]

# 干吴区地理

[28]梁建辉.气候变化环境下新疆喀什冰川河流融雪径流动态响应 研究[J].水利规划与设计,2017(5):41-43,62.[Liang Jianhui. Study on dynamic response of snowmelt runoff of Xinjiang Kashgar glacier river under climate change environment[J].Water Resources Planning and Design,2017(5): 41-43,62.]

[29]李培基.中国季节积雪资源的初步评价[J].地理学报,1988(2):108-119.[Li Peiji.Preliminary evaluation of seasonal snow resourc-es in China[J].Acta Geographica Sinica,1988(2):108-119.]

[30] 周华荣,黄韶华.对新疆生态环境问题及其对策的若干思考[J]. 干旱区资源与环境,1999(4):1-8.[Zhou Huarong,Huang Shaohua.On Xinjiang ecological enviromental problem and its countermeasures[J]. Journal of Arid Land Resources and Environment, 1999(4): 1-8.]   
[31]Gorelick N,Hancher M,Dixon M,et al.Google Earth Engine: Planetary-scale geospatial analysis for everyone[J].Remote Sensing of Environment,2017,202:18-27.

# Temporal and spatial changes of the snow cover cessation day from 2000 to 2019 in Xinjiang, China

Maihemutijiang WEIJIDAN'， Yusufujiang RUSULI'²， QIU Zhongli' (1.College of Geographic Science and Tourism,Xinjiang Normal University,Urumqi 830o54,Xinjiang, China; 2.Xinjiang KeyLaboratoryofLakeEnvironmentandResourcesinAridZone,XinjiangNormalUniversityUrumqi830054, Xinjiang, China)

Abstract: In this study,based on Google Earth Engine(GEE) remote sensing cloud platform,using MODIS snow product from 2000 to 2019,the diurnal snow cover cessation day information in Xinjiang,China is extracted andcalculated,and the diurnal spatial and temporal variation characteristics and variation trend of snow cover cessation day in Xinjiang are analyzed by using trend analysis,coeffcient of variation methods.The results show the following: (1) withthe Tianshan Mountains as the dividing line,and the snow cover cessation day of the north of the Tianshan Mountains is longer than thatof the south.The mountainous area is the high-value area of snow cover cessation day,and the basin is the low value area of snow cover cesstion day.The snow cover cessation day in the Junggar Basin and Ili River Valley in northern Xinjiang lasts $7 5 \mathrm { - } 1 1 4 \mathrm { d }$ all year long.The Tarim Basin in southern Xinjiang is a low-value area between Oand 31 d.The Altai Mountains,Tianshan Mountains and Kunlun Mountains belong to high value areas between 24 and 365 days. (2)There are obvious spatio-temporal differences in snow cover cessation days in southern Xinjiang and northern Xinjiang.From 2Ooo to 2019,the snow cover cessation day in the Junggar Basin and the high-altitude mountains in northern Xinjiang has an obvious trend of delaying,with a delay of 14 days,accounting for $8 \%$ of the total area of Xinjiang. The Tarim Basin and the areas across eastern Xinjang showed an obvious advance advancing trend, the advance advancing rate reached $1 6 \textup { d }$ ,accounting for $44 \%$ of the total area of Xinjiang. Tarim Basin and Junggar Basin have opposite trend.(3)The snow cover cessation day of Xinjiang varied allyear,and central Tianshan Mountains and northern Xinjiang showed instability inchanges of snow cover cessation day all year long.The snow cover cessation day of central Tianshan Mountains showed overall“M"characteristics shape curve, with the annual average snow melting days showing obvious peaks and troughs during 2002—2009.Moreover, northern Xinjiang showed large interannual changes with instability during 2009—2019 and with obvious peaks and troughs as well as large interannual variability.

Key words: GEE cloud computing; snow cover cessation day; temporal and spatial distribution; change trend