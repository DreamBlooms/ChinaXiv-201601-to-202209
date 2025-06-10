# 基于NDVI时间序列影像的天山北坡经济带农业种植结构提取

熊元康1,²，张清凌1,3

（1中国科学院新疆生态与地理研究所,新疆乌鲁木齐830011；2中国科学院大学,北京100049;3中山大学航空航天学院，广州510006）

摘要：水资源匮乏是干旱区实现可持续发展的最大障碍。干旱区农业灌溉耗费大量的水资源，不同农作物在生长期所需的灌溉水量存在较大的差异，因此快速准确地了解干旱区的农业种植结构可以为节水型农业种植结构优化提供重要依据。以天山北坡经济带为研究区，以谷歌地球引擎（Google EarthEngine,GEE)云平台为支撑,以 Sentinel-2以及Landsat7-8的数据为遥感数据源,采取以下步骤进行研究区的农业种植结构提取：首先,为了简化农业种植结构提取的过程,利用一年最大NDVI值以及坡度信息构建耕地掩膜图层；然后，根据研究区内主要农作物的物候历，获取不同时间段内的最大NDVI值的时间序列数据以及农作物在一年中出现NDVI最大值的日期，并在此基础上构建一个包含10波段的特征波段影像;最后，结合野外实地考察获得的有效样本点以及经耕地掩膜图层掩膜后的10波段特征波段影像，利用随机森林分类器进行研究区的农业种植结构提取。分类结果表明：2018年研究区内棉花、玉米、小麦的总体分类精度为 $9 2 . 1 9 \%$ ,Kappa系数为0.883。为了进一步将分类结果与统计数据进行对比，我们将训练得到的分类器应用于2017年的遥感影像，提取了研究区内2017年的农业种植结构信息，其分类结果表明2017年研究区内棉花、玉米、小麦的种植面积分别为 $5 ~ 2 7 0 ~ \mathrm { { k m } ^ { 2 } \setminus 2 ~ 0 0 0 ~ \mathrm { { k m } ^ { 2 } \setminus 2 ~ 3 4 0 ~ \mathrm { { k m } ^ { 2 } } } }$ ，其相对精度分别为 $8 6 . 5 3 \%$ 、$7 7 . 5 4 \%$ ， $8 6 . 1 9 \%$ 。

关 键词：农业遥感；谷歌地球引擎；随机森林分类；种植结构提取；绿洲农业

农业种植结构是农作物空间格局的主要组成部分，指一个地区或生产单位内的农作物种植类型及其空间分布[1]。实时、准确地掌握农业种植结构的动态变化信息，可以为区域农作物估产、农业种植结构调整及其优化提供重要依据[2-4]。干旱区农业属于典型的灌溉农业，水资源匮乏是干旱区实现可持续发展的最大障碍，因此快速、准确地了解干旱区的农业种植结构可以为干旱区的节水型农业种植结构优化提供重要依据。由于利用人力调查一个地区或生产单位内的农业种植结构情况十分耗时耗力，近些年来遥感技术因其监测范围广、实时性强以及使用成本低等诸多优点，已被广泛地应用于对地观测中，其为快速和准确地获取大范围的农业种植结构信息提供了新的技术手段[5-6] ○

目前，基于遥感的农业种植结构提取方法主要利用农作物的光谱特征、时相特征以及空间特征，概括起来主要有3大类：（1）基于单一影像的农业种植结构提取方法。该方法适用于种植结构相对单一的地区，通过找到不同农作物的关键物候识别期以及农作物与其他地类在光谱特征上的差异进行农业种植结构提取。如MATHUR等[7]使用IRS-1D影像（IndianRemote Sensingsatellite-1D）以及棉花和水稻的光谱特征，结合支持向量机（SVM)分类算法，成功提取了印度旁遮普区域内水稻和棉花的空间分布状况。（2）基于时间序列影像的农业种植结构提取方法。该方法充分利用农作物的季相特征，根据农作物在不同时期的生长状态来进行农作物识别。目前该方法已经成为农业种植结构提取的主流方法。如ZHONG等[8]采用不同植被指数(EVI,NDSVI等）的时序特征以及累积积温（Growing-degree-day，GDD)等特征，使用随机森林分类算法成功提取了美国堪萨斯州多尼芬县内玉米与大豆的空间分布状况。（3）基于遥感影像与其他数据融合的农业种植结构提取方法。由于遥感数据受到获取能力等因素的影响，往往不能满足国家以及全球尺度下的农业种植结构提取。因此，许多学者尝试了将遥感数据与其他数据(如统计数据)进行融合的方式来实现国家以及全球尺度下的农业种植结构提取，如PORTMANN等[9]通过结合灌溉农作物和雨养农作物的物候历、农作物面积以及地形等信息进行重分类，成功获取了全球2000年5分栅格尺度的26种灌溉和雨养农作物的空间分布。

目前，利用时间序列影像进行大范围的农业种植结构提取主要使用的是低分辨影像，如MODIS数据，因其覆盖范围广、重复周期短等优势被广泛地应用于大尺度(区域、国家、全球)的农业种植结构提取，但影像的低分辨也会导致大量混合像元产生，从而降低农业种植结构提取的精度[10-11]。中高分辨率影像能减少混合像元，但由于其监测范围小和重返周期长等因素限制了其在大范围内进行农业种植结构提取的应用。目前，使用中高分辨率遥感影像在干旱区进行大范围的农业种植结构提取的研究较少。为解决大范围的干旱区农业种植结构提取所面临的低分辨率遥感影像混合像元严重和中高分辨率遥感影像监测范围小以及重返周期长等问题，本文以天山北坡经济带为研究区，基于GoogleEarthEn-gine（GEE)云平台，结合使用中高分辨率的Senti-nel-2和Landsat7-8等多源遥感数据，通过构建ND-VI时间序列以及其他辅助特征进行天山北坡经济带的农业种植结构快速提取。

GEE云平台是一个能在大尺度范围下进行遥感数据处理以及分析的云平台，该平台提供了一个完备的集成环境，其中包括遥感数据库（如Sentinel-2A/B、Landsat系列、MODIS等遥感数据），以及建立在JavaScript（或Python）APIs上的交互式算法开发环境[12]。目前,国内外多个研究组基于该平台开展了各种对地观测研究,如水稻遥感制图[13],耕地遥感提取[14],城市变化遥感检测[15],冬小麦遥感制图[16]等。

# 研究区概况与数据源

# 1.1 研究区概况

天山北坡经济带地处亚欧大陆腹地，位于天山北麓、准噶尔盆地南缘,属于干旱与半干旱气候区，地理范围为 $7 9 ^ { \circ } 5 2 ^ { \prime } \sim 9 1 ^ { \circ } 3 2 ^ { \prime } \mathrm { E } , 4 3 ^ { \circ } 0 1 ^ { \prime } \sim 4 6 ^ { \circ } 1 3 ^ { \prime } \mathrm { N } _ { \circ }$ 该区域以乌鲁木齐市为中心，东起木垒哈萨克自治县，西至温泉县,横跨17 个县市（图1)[17]。近十几年来，该地区每年的国内生产总值占新疆维吾尔自治区国内生产总值的 $5 0 \%$ 左右，是新疆经济、教育、科技等最为发达的地区，也是丝绸之路经济带通往中亚和欧洲的重要枢纽[17-18]。但由于受干旱气候环境的影响，水资源匮乏已成为制约该地区实现可持续发展的最大因素[19],而该地区的农业耗水占该地区总耗水的 $91 \%$ [20]。因此,深人了解该地区的农业种植结构，有利于该地区的水资源优化配置以及可持续发展。根据历年的《新疆统计年鉴》可知，该地区主要种植的农作物为棉花、玉米以及小麦等一年一熟的农作物，2017年这3类农作物的种植面积占整个地区农作物种植面积的76.9%[21]

# 1.2 数据源

1.2.1遥感数据多时相的遥感数据能够充分地反映农作物的生长特征[22-24],本文根据不同农作物在不同时期的生长状况信息(表1)来进行研究区的农业种植结构提取。为了充分获取研究区内不同农作物在不同时期的生长状况信息，在农作物种植结构提取的识别期内，我们在GEE云平台上一共获得了4313景遥感影像，其中Sentinel-2影像3582景，Landsat-8 影像381景,Landsat-7影像350 景（表2）。综合以上多源遥感影像一方面可以增加可用的遥感数据（光学遥感影像往往容易受到云的干扰使得可用像元减少）。另一方面，由于各卫星过境时间不同，融合使用多源遥感数据可以提高遥感监测时间频率以更好地捕捉农作物的生长过程（如Landsat-8在2018年3月在新疆过境的时间分别为3月7日与3月23日，而Landsat-7在2018年3月份在新疆过境的时间分别为3月15日与3月31日）。

1.2.2地面调查数据我们于2018年5\~6月在研究区内进行了野外实地考察，一共记录了有效样本点822个。其中，棉花有效样本点394个，玉米

![](images/678ae447b15b782aad6f95f47ec7c038cd9e25b4676e92d674b609a8cf6b436e.jpg)  
图1研究区位置与地面调查采样点  
Fig.1Location of the study area and the spatial distribution of the samples

# 表1研究区内主要农作物的物候历

Tab.1Crops calendars in study area   

<html><body><table><tr><td>月</td><td colspan="4">6月</td><td colspan="4">前一年9月</td><td colspan="4">7月</td><td colspan="4">3月</td><td colspan="4">4月</td><td colspan="4">9月</td><td colspan="4">5月</td></tr><tr><td>旬</td><td>上</td><td>中</td><td>下</td><td></td><td>上</td><td>中</td><td>下</td><td>上</td><td>中</td><td>下</td><td>上</td><td>中</td><td>下</td><td>上</td><td>中</td><td>下</td><td>上</td><td></td><td>中</td><td>下</td><td>上</td><td>中</td><td>下</td><td>上</td><td>中</td><td></td><td>下</td></tr><tr><td>棉花</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>播种</td><td></td><td></td><td>出苗</td><td></td><td>苗期</td><td></td><td></td><td>蕾期</td><td></td><td></td><td></td><td></td><td>花铃期</td><td></td><td></td><td>吐絮期</td><td></td><td></td></tr><tr><td>冬小麦</td><td colspan="4">播种</td><td colspan="4"></td><td colspan="9">拔节 抽穗</td><td colspan="5">成熟</td><td colspan="5"></td></tr><tr><td>春小麦</td><td colspan="13">播种</td><td colspan="7">成熟</td><td colspan="5"></td></tr><tr><td>春玉米</td><td colspan="7"></td><td colspan="4">播种</td><td colspan="5">出苗 苗期</td><td colspan="5">拔节</td><td colspan="5">乳熟</td></tr><tr><td></td><td colspan="7"></td><td colspan="4"></td><td colspan="5"></td><td colspan="5">抽雄</td><td colspan="4"></td></tr></table></body></html>

表2实验选取的遥感影像源  
Tab.2Remote sensing data sources used in this study   

<html><body><table><tr><td>传感器类型</td><td>获取时间</td><td>波段</td><td>波段名称</td><td>波长/nm</td><td>分辨率/m</td><td>数据源</td></tr><tr><td>Sentinel-2MSI,TOA</td><td>2018-03-01—2018-12-01</td><td>B4</td><td>Red</td><td>665</td><td>10</td><td>ESA</td></tr><tr><td rowspan="3">Landsat 8 OLI,TOA</td><td></td><td>B8A</td><td>NIR</td><td>842</td><td>10</td><td></td></tr><tr><td>2018-03-01—2018-12-01</td><td>B4</td><td>Red</td><td>640~670</td><td>30</td><td>USGS</td></tr><tr><td></td><td>B5</td><td>NIR</td><td>850~880</td><td>30</td><td></td></tr><tr><td rowspan="2">Landsat7ETM+,TOA</td><td>2018-03-01—2018-12-01</td><td>B3</td><td>Red</td><td>630~690</td><td>30</td><td>USGS</td></tr><tr><td></td><td>B4</td><td>NIR</td><td>770~900</td><td>30</td><td></td></tr><tr><td colspan="2">ShuttleRadar Topography Mission(SRTM)</td><td>Slope</td><td></td><td></td><td>30</td><td>USGS</td></tr></table></body></html>

有效样本点220个，小麦有效样本点67个，葡萄有效样本点51个，其他农作物（包括打瓜、辣椒、葫芦瓜等)有效样本点90个。在进行地面采样的过程中，我们保证了各个样本点之间的独立性，即样本点之间均为独立的单个像元，以增强分类的可靠性，有效样本点在研究区内的空间分布如图1所示。

1.2.3统计数据根据最新的《新疆统计年鉴》（2017年），我们统计了该区域内各主要农作物（棉花、玉米、小麦等)的种植面积,并将其作为评价标准，对遥感提取的各主要农作物的种植面积进行精度评价。

# 1.3 数据预处理

云以及云阴影对光学遥感影像具有显著的影响[25],它们会严重影响基于遥感影像所进行的研究,如：遥感影像合成[26]、植被指数计算[27]以及地表覆盖分类[28]等。我们在GEE 云平台上采用了

FMASK[29]算法对获取的遥感数据进行了去云以及去云阴影处理，以减少数据合成,植被指数计算等对农业种植结构提取所造成的噪声影响。同时将Sen-tinel-2的数据产品（ $1 0 \mathrm { ~ m ~ } ,$ 重采样至Landsat7-8的$3 0 \mathrm { ~ m ~ }$ 分辨率,以保证使用的遥感数据在分辨率上的一致。

# 2 研究方法

# 2.1 耕地掩膜图层构建

为了减少非农作物植被对农业种植结构提取的影响，我们通过以下步骤提取了研究区2018年的耕地掩膜图层：首先，我们根据GoogleEarth的高清影像以及实地调研情况，在研究区内选择了大量的非农作物植被样本点，如森林、天然草地等，将收集到的非农作物植被样本点与有效的农作物样本点在各类遥感数据（如：NDVI、DEM等数据产品）上进行分析对比;其次，根据分析对比的结果以及以往的研究,构建耕地掩膜判别规则： $N D V I _ { \mathrm { { M a x } } } > 0 . ~ 4 ^ { [ 3 0 ] }$ 和$S l o p e < 7 ^ { \circ }$ 。其中 $N D V I _ { \operatorname { M a x } }$ 代表一年中最大的NDVI值,Slope代表坡度信息，由SRTM数据计算所得；最后，以Landsat-8的遥感数据以及SRTM数据为数据源，根据构建的规则提取耕地掩膜图层，并将获得的耕地掩膜图层与GoogleEarth的高清影像进行叠加，通过人工目视解译去除一些明显提取错误的区域，最终获得研究区2018年 $3 0 \mathrm { ~ m ~ }$ 分辨率的耕地掩膜图层（图2）。为了检验耕地提取的精度，我们在生成的耕地掩膜图层中随机生成1000个样本点，并利用GoogleEarth的高清影像对生成的样本点进行人工目视解译以判断其是否属于耕地。结果表明在这1000个随机样本点中有967个为耕地样本点，33个为非耕地样本点（其中多为防护林以及其他自然植被），耕地提取的精度为 $9 6 . 7 \%$ ,可以满足下一步的要求。

# 2.2农作物分类特征构建

2.2.1 NDVI时序特征构建植被指数常常被作为特征参数来评估地表植被的生长状况，其中归一化植被指数（Normalized Difference Vegetation Index,NDVI)使用最为广泛[31-33]。NDVI表达了红波段（植物吸收强烈)与近红外波段(植被反射强烈)之间的关系,其计算公式如下所示[34]：

$$
N D V I = { \frac { \rho _ { \mathrm { N I R } } - \rho _ { \mathrm { R e d } } } { \rho _ { \mathrm { N I R } } + \rho _ { \mathrm { R e d } } } }
$$

式中： $\rho _ { \mathrm { N I R } }$ 代表近红外波段的反射率； $\cdot \rho _ { \mathrm { R e d } }$ 代表红波段的反射率。由于NDVI能够很好地反映植被的生长状况，因此本文将NDVI作为评估农作物在不同时期生长状况的主要特征参数。

不同传感器在设计上的差异，导致了不同传感器具有不同的光谱响应函数（SpectralResponseFunctions, $S R F { \mathrm {     \Omega } } _ { \mathrm { { } } }$ ）。比如,Sentinel-2与Landsat-7的数据在红波段的均方根误差（Root Mean Square Error,RMSE)超过了 $8 \%$ [35]。为了减小由于不同传感器的不同光谱响应函数所带来的误差，我们以Land-sat-8数据计算的NDVI值为基准,将Sentinel-2以及Landsat-7数据计算所得的NDVI值进行相关的线性转换。其采用的线性模型计算公式如下所示[36-37]：

![](images/eefcdf9f17284e43129e630a6c9e74b22e36d4d56202d1d398ddf149331daa63.jpg)  
图2研究区的耕地提取结果  
Fig.2Extracted cropland in the study area

$$
N D V I _ { \mathrm { L a n d s a t - 8 } } = 0 . 0 2 3 ~ 5 + 0 . 9 7 2 ~ 3 \times N D V I _ { \mathrm { L a n d s a t - 7 } }
$$

$$
N D W _ { \mathrm { { L a n d s a t - 9 } } } = - 0 . 0 0 4 6 + 1 . 0 1 8 3 \times N D W _ { \mathrm { { S e n t i n e l - 2 } } }
$$

根据研究区内主要农作物的物候识别期（表1），我们利用去云后的Sentinel-2以及Landsat7-8数据计算了2018年3月1日 $\sim 2 0 1 8$ 年12月1日这个时间段内的所有NDVI值，同时根据以上的线性模型进行了NDVI值的转换，并依据获取影像的时间对NDVI数据进行时间排序。与此同时，我们对排好序的NDVI时间序列，计算2018年3月1日\~2018年12月1日这个时间段内每个月的最大NDVI值，并将每个月的最大NDVI值作为一个特征波段。2.2.2辅助特征构建通过对研究区内不同农作物的物候历进行深入分析后，我们发现不同农作物出现生长峰值的时间是有差异的。比如棉花出现NDVI最大值的日期在每年的第225d左右，玉米出现 NDVI最大值的日期在每年的第195d左右，小麦出现NDVI最大值的日期在每年的第155d左右（图3a)。为了更加突出不同农作物在不同时期的生长状况,我们将农作物在一年中获得NDVI最大值的日期也作为分类特征参数。为了扩大最大NDVI值与出现最大NDVI值日期的差异，我们采用以下公式将其进行归一化处理：

$$
N o r m a l i z e \_ D a t e = \frac { S u m _ { d a y } - M a x _ { d a y } } { S u m _ { d a y } }
$$

式中： $S u m _ { d a y }$ 代表该年一共有多少天， $M a x _ { d a y }$ 代表一年中出现NDVI最大值的日期。如小麦NDVI出现最大值的日期约为第155d（5月份左右），其 Nor-malize_Date值则为0.57，而棉花NDVI出现最大值的日期约为第255d（7月份左右），其Normalize_Date值则为0.3,既NDVI最大值出现的越早，其Normalize_Date值越大。

根据2.2.1获得的NDVI时相特征以及NDVI最大值日期特征，我们一共获取了10个分类特征量(F1: $\mathrm { M a x } \_ N D V I _ { \mathrm { M a r } }$ ； $\mathrm { F } 2 : \mathrm { M a x } _ { - } N D V I _ { \mathrm { A p r } }$ ；F3:Max_ND-${ { \cal { W } } _ { \mathrm { { M a y } } } }$ ; $\mathrm { F } 4 \cdot \mathrm { M a x } \_ N D V I _ { \mathrm { J u n } }$ ； F5 : $\mathrm { M a x } _ { - } N D V I _ { \mathrm { J u l } }$ ；F6:Max_$N D V I _ { \mathrm { A u g } }$ ；F $7 : \mathrm { M a x } _ { - } N D V I _ { \mathrm { s e q } }$ ; $\mathrm { F 8 } : \mathrm { M a x } _ { - } N D V I _ { \mathrm { 0 c t } }$ ；F9:Max_ $. N D V I _ { \mathrm { N o v } }$ ；F10：Normalize_Date）。研究区内主要农作物的分类特征曲线如图3b所示。

# 2.3 随机森林分类器

随机森林分类（RandomForest，RF）是一种集成学习分类器，是由一系列CART决策树以及投票机制组合而成的机器学习算法[38]。它比其他分类器在进行遥感图像分类时表现得更加健壮，分类速度相对更快,更容易实现[36]。它使用 bootstrap 抽样技术从原始数据集中抽取训练集，并通过训练集构建CART决策树。在构建CART决策树的过程中，同时采取一些规则(如Gini系数最小原则)来计算最佳分割方式并进行内部节点分割，以便减少CART决策树之间的相关性，减少过拟合现象。

我们将在GEE 云平台上集成的随机森林算法应用于本文的研究[12]。GEE 云平台上的随机森林分类器的参数如下所述：（1）随机森林分类器的决策树数量；（2）候选特征子集；（3）叶节点最小样本数；（4）再抽样比率；（5）是否计算袋外错误率（out-of-bag，OOB)；（6）随机种子数。其中随机森林分类器的决策树数量、候选特征子集以及叶节点最小样本数是影响随机森林分类器性能与效率的最主要参数。我们根据已有的大量研究[3941]以及本文研究的实际情况，将以下3个参数分别设置为：随机森林分类器的决策树数量 $= 1 0 0$ ；候选特征子集 $\mathbf { \sigma } = \mathbf { \sigma }$ 4;叶节点最小样本数 $= 1$ 。根据在2.2中构建的分类特征，在GEE云平台上融合生成了10 波段的分类特征影像，并将野外实地考察获得的有效样本点随机选择一半作为训练集进行随机森林分类器的训练，另一半作为测试集验证其分类精度。

![](images/62da9877c782dc7060eafcf084218ed79fc8b8378991ec3e8ca02043ac6c3b5f.jpg)  
图3研究区内主要农作物的NDVI值以及分类特征值变化曲线  
Fig.3Time-series of NDVI and classification variables of major crops in the study area

# 3分析与讨论

# 3.1 精度分析

本文采用混淆矩阵精度以及与统计数据对比这两种方式对分类结果进行精度验证。由于随机森林分类器是基于像元的分类器，分类结果中往往存在椒盐噪声。在进行混淆矩阵计算之前，我们采用众数滤波( $3 \times 3$ pixels)对分类结果进行滤波处理。最终用计算得到的用户精度（user'saccuracy， $U A$ ）生产者精度（produce'saccuracy， $P A$ ）、总体精度（over-all accuracy, $\ O A { \bf \Sigma }$ )以及Kappa系数来表征分类结果的混淆矩阵精度（表3）。如表3所示，分类结果的总体精度为 $9 2 . 1 9 \%$ ,Kappa系数为0.883，主要农作物的用户精度以及生产者精度都超过了 $8 5 \%$ ，但其他农作物的用户精度只有 $6 4 . 4 4 \%$ 。表明其他农作物(辣椒、打瓜、葵花等)也具有与棉花、玉米等作物相似的分类特征值，特别是易于与玉米混淆。

由于我们提取的是研究区内2018年主要农作物的种植结构信息，而目前对于研究区内的农业种植结构信息只统计到了2017年，因此我们将2018年农业种植结构提取所训练的模型应用于2017年研究区内的农业种植结构提取，以便与2017年的统计数据进行比较。据统计，2017年研究区内棉花、玉米、小麦的种植面积分别为 $4 6 5 0 \ \mathrm { k m } ^ { 2 } \ 、 1 \ 6 3 0 \ \mathrm { k m } ^ { 2 }$ 、$2 \ 0 5 0 \ \mathrm { k m } ^ { 2 }$ 。

根据2017年的分类结果得知，2017年研究区内棉花、玉米、小麦的种植面积分别为 $5 ~ 2 7 0 ~ \mathrm { k m } ^ { 2 }$ 、$2 ~ 0 0 0 ~ \mathrm { k m } ^ { 2 } \ 、 2 ~ 3 4 0 ~ \mathrm { k m } ^ { 2 }$ ,其分类精度分别为 $8 6 . 5 3 \%$ 、$7 7 . 5 4 \% . 8 6 . 1 9 \%$ 。同时我们还统计了各县市的农作物分类结果，并与统计数据进行了对比（图4）。由于五家渠市与石河子市属于新疆生产建设兵团地区，统计年鉴中缺少这两个地区的农业种植结构统计信息，因此本文没有对这两个地区的分类结果进行精度分析。由图4可知，乌鲁木齐市、克拉玛依市、昌吉回族自治州这3个地区的分类结果较统计数据而言有较大的误差，其主要原因是这3个地区的种植结构相对于其他地区更为复杂，导致了其他农作物与这3类主要农作物产生了混淆。但由于2017年农业种植结构提取模型是基于2018年的野外实地考察数据训练获得的，而不同年份之间的农业种植制度是有所差异的，因此更加准确的精度验证结果仍需新的统计数据(2018年)加以论证。

# 3.2种植结构提取结果

本文利用随机森林分类器以及构建的分类特征，成功获取了研究区内2018年 $3 0 \mathrm { ~ m ~ }$ 分辨率的农业种植结构信息（图5）。研究区内棉花种植主要分布在精河县、博乐县、乌苏市、克拉玛依市、奎屯市、沙湾县、石河子市、玛纳斯县、呼图壁县、五家渠市等10 个地区;玉米种植主要分布在温泉县、博乐市、呼图壁县、昌吉市、阜康市、吉木萨尔县、奇台县、木垒县等8个地区；小麦种植主要分布在奇台县、昌吉市、沙湾县、奎屯市、乌苏市、温泉县等6个地区；葡萄种植主要分布在乌鲁木齐市、阜康市、呼图壁县、玛纳斯县等4个地区。同时我们将遥感反演的主要农作物的空间分布信息与历年《新疆统计年鉴》中各地区的种植结构信息以及实地考察信息进行对比后发现，遥感反演的主要农作物的空间分布能较好

# 表3分类精度

Tab.3Accuracy of the classification result   

<html><body><table><tr><td rowspan="2">分类后数据</td><td colspan="5">参考数据</td><td rowspan="2">总计</td><td rowspan="2">用户精度</td></tr><tr><td>棉花</td><td>玉米</td><td>小麦</td><td>葡萄</td><td>其他农作物</td></tr><tr><td>棉花</td><td>190</td><td>5</td><td>0</td><td>2</td><td>0</td><td>197</td><td>96.44%</td></tr><tr><td>玉米</td><td>2</td><td>106</td><td>0</td><td>0</td><td>2</td><td>110</td><td>96.39%</td></tr><tr><td>小麦</td><td>1</td><td>2</td><td>29</td><td>0</td><td>1</td><td>33</td><td>87.87%</td></tr><tr><td>葡萄</td><td>1</td><td>0</td><td>0</td><td>24</td><td>0</td><td>25</td><td>96.00%</td></tr><tr><td>其他农作物</td><td>4</td><td>10</td><td>1</td><td>1</td><td>29</td><td>45</td><td>64.44%</td></tr><tr><td>总计</td><td>198</td><td>123</td><td>30</td><td>27</td><td>32</td><td>总体精度=92.19%</td><td></td></tr><tr><td>生产者精度</td><td>95.95%</td><td>86.17%</td><td>96.66%</td><td>88.89%</td><td>90.62%</td><td>Kappa系数=0.883</td><td></td></tr></table></body></html>

![](images/8f68539f1b723a43e157a750189ef9c3b298246090a489cb1438d1694c6e5c29.jpg)  
图42017年农作物分类结果与统计年鉴数据的比较  
Fig.4Comparison between classification results and statistical reports in 2017

的与之相对应。

虽然根据遥感分类的结果来看，运用随机森林分类器以及构建的分类特征能较好的应用于研究区的农业种植结构提取，但是仍有以下问题需要进一步分析：由于天山北坡经济带主要从事的是1年1季的农业生产且种植结构较为单一，因此，本文并未考虑多季、套种、间种等农业种植模式；从遥感分类结果来看，棉花、玉米、小麦是研究区的主要农作物，这一点与统计年鉴的统计信息是基本吻合的。但由于其他作物(辣椒、葵花等)也具有与这3类主要农作物相似的季相节律，导致了遥感提取的这3类农作物的种植面积大于实际的种植面积，因此在后续的研究中需要更加深入地了解该地区各个农作物在其他特征(空间特征等)上表现出来的差异，以便提高分类的精度。

# 4结论

受制于有限的水资源，农业种植结构优化以及采用节水型农业灌溉技术是现代干旱区绿洲农业实现可持续发展的必经之路。本文以天山北坡经济带为研究区，通过利用研究区内主要农作物的物候历信息以及野外考察数据，基于遥感数据构建了10 个分类特征。同时基于GEE云平台融合生成了研究区内Sentinel-2、Landsat7-8的NDVI时序数据以及1年中出现NDVI最大值的日期数据，并在此基础上构建了10波段的特征波段影像。同时通过野外考察获得的有效样本点以及随机森林分类器进行了研究区内2018年主要农作物(棉花、玉米、小麦)的种植结构提取。根据对其分类结果进行分析后，我们得出以下主要结论：

![](images/4ba2799fd3540d75e7f556268d0bec74f82093b43e33d86c6fb64cd6d53e7375.jpg)  
图5研究区内2018年主要农作物的空间分布  
Fig.5Spatial distribution of major crops in the study area in 2018

（1）多源数据的融合使用能更加准确的表征不同农作物在不同时期的生长状态。由于我们综合使用了Sentinel-2以及Landsat7-8作为遥感数据源，因此能更为准确地获取不同农作物在不同时期的生长状况以及1年中出现NDVI最大值的日期，同时构建的最大NDVI值特征又能够有效的去除薄云及其阴影对种植结构提取的影响。

（2）构建的10个分类特征以及随机森林分类器能够较好的适应于研究区内的种植结构提取。运用构建的分类特征以及随机森林分类器进行种植结构提取的总体精度达到了 $9 2 . 1 9 \%$ ,Kappa系数为0.883。与统计数据对比也说明了构建的10个分类特征以及随机森林分类器能够较好的适应于该研究区的种植结构提取。

（3）天山北坡经济带内主要种植的农作物为棉花、玉米、小麦，这3种农作物的播种面积占整个研究区农作物播种面积的 $7 5 \%$ 左右。同时，新的对地观测卫星如Sentinel-2星座以及遥感云平台如GEE的出现，为进行基于时间序列影像的大区域农业种植结构快速提取带来了新的技术手段。

# 参考文献(References）

[1]唐华俊,吴文斌,杨鹏,等.农作物空间格局遥感监测研究进展 [J].中国农业科学,2010,43（14）:2879-2888.［TANG Huajun,WU Wenbin,YANG Peng,et al.Recent progresses in monitoring crop spatial patterns by using remote sensing technologies[J]. Scientia Agricultura Sinica,2010,43（14）:2879 -2888.]   
[2] OZDOGAN M.The spatial distribution of crop types from MODIS data:Temporal unmixing using independent component analysis [J].Remote Sensing of Environment,2010,114（6）：1190- 1204.   
[3] 马丽，顾晓鹤，徐新刚，等.地块数据支持下的玉米种植面积遥 感测量方法[J].农业工程学报,2009,25（8）：147-151.［MA Li,GU Xiaohe,XU Xingang,et al. Remote sensing measurement of corn planting area based on field-data［J].Transactions of the CSAE,2009,25(8):147-151.]   
[4] WARDLOWBD,EGBERT SL,KASTENSJH.Analysis of timeseries MODIS 25O m vegetation index data for crop classification in the US Central Great Plains[J].Remote Sensing of Environment, 2007,108(3):290-310.   
[5] XIAO X,BOLES S,FROLKING S,et al. Mapping paddy rice agriculture in South and Southeast Asia using multi-temporal MODIS images[J].Remote Sensing of Environment,2006,100（1） :95- 113.   
[6] VINTROU E,DESBROSSE A,BEGUE A,et al. Crop area mapping in West Africa using landscape stratification of MODIS time series and comparison with existing global land products[J].International Journal of Applied Earth Observation and Geoinformation,2012, 14(1) :83 -93.   
[7]MATHUR A,FOODY G M. Crop classification by support vector machine with intelligently selected training data for an operational application[J].International Journal of Remote Sensing,2008,29 (8):2227 -2240.   
[8]ZHONG L,GONG P,BIGING G S.Effcient corn and soybean mapping with temporal extendability:A multi-year experiment using Landsat imagery[J].Remote Sensing of Environment,2014, 140:1 - 13.   
[9]PORTMANN F T,SIEBERT S,DOLL P.MIRCA20O0-Global monthly irigated and rainfed crop areas around the year 2000: A new high-resolution data set for agricultural and hydrological modeling[J].Global Biogeochemical Cycles,2010,24(1）:1-24.   
[10]JIA K,LIANG S,WEI X,et al.Land cover classification of Landsat data with phenological features extracted from time series MODIS NDVI data[J]. Remote Sensing,2014,6(11):11518 -11532.   
[11] GUSSO A,FORMAGGIO A R,RIZZI R,et al. Soybean crop area estimation by MODIS/EVI data[J].Pesquisa Agropecu(ria Brasileira,2012,47(3）:425-435.   
[12]GORELICK N,HANCHER M,DIXON M,et al. Google earth engine: Planetary-scale geospatial analysis for everyone[J].Remote Sensing of Environment,2017,202:18 -27.   
[13] DONG J,XIAO X,MENARGUEZ M A,et al. Mapping pady rice planting area in Northeastern Asia with Landsat 8 images,phenology-based algorithm and Google Earth Engine[J]. Remote Sensing of Environment,2016,185:142 -154.   
[14] XIONG J,THENKABAIL P S,TILTON JC,et al. Nominal 30-m cropland extent map of continental Africa by integrating pixelbased and object-based algorithms using sentinel-2 and Landsat-8 data on Google Earth Engine[J].Remote Sensing,2017,9（10）: 1065.   
[15]GOLDBLATT R,YOU W,HANSON G,et al.Detecting the boundaries of urban areas in India:A dataset for pixel-based image classification in Google Earth Engine[J].Remote Sensing,2016,8 (8) :634.   
[16］王九中,田海峰,邬明权,等.河南省冬小麦快速遥感制图[J]. 地球信息科学学报,2017,19（6）:846-853.[WANG Jiuzhong， TIAN Haifeng,WU Mingquan,et al. Rapid mapping of winter wheat in Henan Province[J]. Journal of Geo-information Science, 2017,19(6) :846 - 853.]   
[17］朱慧,王哲,焦广辉,等.天山北坡经济带经济格局时空演变特 征研究[J].干旱区资源与环境,2012,26(3）：23-29.[ZHU Hui,WANG Zhe,JIAO Guanghui,et al. Spatial dynamic evolution of economic pattern in economic belt on the north slope of Tianshan [J]. Journal of Arid Land Resources and Environment,2012,26 (3):23 -29.]   
[18］董雯,杨宇,周艳时.干旱区绿洲城市土地利用效益研究- 以乌鲁木齐为例[J].干旱区地理,2011,34（4)：679-685. [DONG Wen,YANG Yu,ZHOU Yanshi.Land use changes and evaluation of land use eficiency in an arid oasis city:A case of Urumqi,China[J].Arid Land Geography,2011,34(4):679-685.]   
[19]DINDA S,COONDOO D,PAL M.Air qualityand economic growth:An empirical study[J].Ecological Economics,2000,34 (3) :409 -423.   
[20］吴业鹏,袁汝华.丝绸之路经济带背景下新疆水资源与经济社 会协调性评价[J].水资源保护,2016,32（4）:60-66.［WU Yepeng,YUAN Ruhua.Evaluation of coordination between water resources and economic and social development in Xinjiang in context of Silk Road Economic Belt[J]. Water Resources Protection, 2016,32(4) :60 -66.]   
[21］新疆维吾尔自治区统计局.新疆统计年鉴[M].北京：中国统 计出版社,2O17.[Statistic Bureau of Xinjiang Uygur Autonomous Region.Xinjiang statistical yearbook[M].Beijing:China Statistics Press,2017. ]   
[22]PAN Y,HU T,ZHU X,et al. Mapping cropland distributions using a hard and soft classification model[J]. IEEE Transactions on Geoscience and Remote Sensing,2012,50(11） :4301-4312.   
[23]CLAVERIE M,DEMAREZ V,DUCHEMIN B,et al. Maize and sunflower biomass estimation in Southwest France using high spatial and temporal resolution remote sensing data[J].Remote Sensing of Environment,2012,124:844-857.   
[24]LHERMITTE S,VERBESSELT J,VERSTRAETEN W W,et al.A comparison of time series similarity measures for classification and change detection of ecosystem dynamics[J]. Remote Sensing of Environment,2011,115(12）:3129-3152.   
[25]ZHU Z,WOODCOCK C E. Object-based cloud and cloud shadow detection in Landsat imagery[J].Remote Sensing of Environment, 2012,118:83 -94.   
[26]ROY D P,JU J, KLINE K,et al. Web-enabled Landsat Data （WELD）:Landsat ETM $^ +$ composited mosaics of the conterminous United States[J]. Remote Sensing of Environment,2010,114(1): 35-49.   
[27]HUETE A,DIDAN K,MIURA T,et al. Overview of the radiometric and biophysical performance of the MODIS vegetation indices[J]. Remote Sensing of Environment,2002,83(1-2）:195-213.   
[28] ZHANG Y,GUINDON B,CIHLAR J. An image transform to characterize and compensate for spatial variations in thin cloud contamination of Landsat images[J].Remote Sensing of Environment, 2002,82(2-3):173 -87.   
[29] ZHU Z,WANG S,WOODCOCK C E. Improvement and expansion of the Fmask algorithm:Cloud,cloud shadow,and snow detection forLandsats 4-7,8,and Sentinel 2 images[J].Remote Sensing of Environment,2015,159:269- 277.   
[30]ZHANG Q,LI B,THAU D,et al. Building a better urban picture: Combining dayand night remote sensing imagery[J].Remote Sensing,2015,7(9) :11887 -11913.   
[31]TOWNSHEND JR,GOFF TE,TUCKER C J. Multitemporal dimensionality of images of normalized diference vegetation index at continental scales[J]. IEEE Transactions on Geoscience and Remote Sensing,1985,6(6) :888 -895.   
[32]TARPLEY J,SCHNEIDER S,MONEY R L. Global vegetation indices from the NOAA-7 meteorological satelite[J]. Journal of Climate and Applied Meteorology,1984,23（3）:491 -494.   
[33]ROSENTHAL W D,BLANCHARD B J,BLANCHARD A J. Visible/infrared/microwaveagriculture classification，biomass，and plant height algorithms[J]. IEEE Transactions on Geoscience and Remote Sensing,1985,23(2）:84-90.   
[34]TUCKER C J. Red and photographic infrared linear combinations formonitoring vegetation[J].Remote Rensing of Environment, 1979,8(2) :127-150.   
[35]D'ODORICOP,GONSAMO A,DAMMA,et al.Experimental evaluation of Sentinel-2 spectral response functions for NDVI timeseries continuity[J].IEEE Transactions on Geoscience and Remote Sensing,2013,51(3):1336-1348.   
[36］ROYD,KOVALSKYYV,ZHANGH,et al.Characterization of Landsat-7 to Landsat-8 reflective wavelength and normalized difference vegetation index continuity[J].Remote Sensing of Environment,2016,185:57-70.   
[37］MANDANICI E,BITELLIG.Preliminary comparison of Sentinel-2 and Landsat 8 Imagery for a combined use[J].Remote Sensing, 2016,8(12):1014.   
[38］BREIMANL.Random forests[J].Machine Learning,2OO1,45 (1):5-32.   
[39］刘敏,郎荣玲，曹永斌.随机森林中树的数量[J].计算机工程 与应用,2015,51（5）:126-131.[LIU Min,LANG Rongling, CAO Yongbin.Number of trees in random forest[J].Computer Engineering and Applications,2015,51(5）:126-131.]   
[40]DIAZ-URIARTE R,DE ANDRES S A.Gene selection and classification of microarray data using random forest[J].BMC Bioinformatics,2006,7(1) :3.   
[41]SVETNIKV,LIAWA,TONG C,et al.Random forest:A classification and regression tool for compound classification and QSAR modeling[J].Journal of Chemical Information and Computer Sciences,2003,43(6):1947-1958.

# Cropping structure extraction with NDVI time-series images in the northern Tianshan Economic Belt

XIONG Yuan-kang1,2，ZHANG Qing-ling1,3 (1ResearchCenteronEcologyandEironmentofentralAsia,XinjiangInstituteofEcologyndGeography,ChneseAcademy of Sciences,Urumqi 830o11,Xinjiang,China；2Universityof Chinese Academyof Sciences,Beijing 100049,China; 3School of Aeronautics and Astronautics,Sun Yat-sen University,Guangzhou 51oo06,Guangdong,China)

Abstract：Limited water resources is the major factor afecting sustainable development in arid areas,and the water resources in arid areas are mostly used for agricultural irigation. Rapidlyand accurately mapping cropping structure inarid areas can provide an important basis foroptimizing water use inagriculture.In this study,the Northern Tianshan Economic Belt,Xinjiang,China was chosen as the study area,and a method to map the cropping structure in this region with multi-source remote sensing data based on the Google Earth Engine（GEE）cloud platform was proposed.The Sentinel-2 and Landsat7-8 data were chosen as the remote sensing data sources to extract the cropping structure in the study area through the following steps.First,in order to simplify the cropping structure extraction processand minimize the impacts from non-crop vegetation,acropland mask was constructed by using the maximum NDVI value and slope information throughout the year in the study area.Second,acording to the phenology calendars ofthe main crops in the study area,the time-series data ofthe maximum NDVI value and the corresponding date was calculated with remote sensing data.Then,the1O feature bands were constructed.Third,the1O feature bands were masked with the cropland mask.Based on thesedata together with the field samples,the random forest clasifier was applied to cropping structure extraction.The acuracy evaluation results showed the overallaccuracy of the classification results in 2O18 was $9 2 . 1 9 \%$ ,and the Kappa coefficient was O.883.In order to further verify the accuracy ofthe clasification algorithm,the crop structure in the study area in2O17was also extracted,the classification results showed that the planted area of coton,corn and wheat in the study area were $5 ~ 2 7 0 ~ \mathrm { k m } ^ { 2 }$ ， $2 \ 0 0 0 \ \mathrm { k m } ^ { 2 }$ （20 and $2 ~ 3 4 0 ~ \mathrm { k m } ^ { 2 }$ respectively in 2O17,and then compared it with the results of statistical yearbook data in 2017.The relative accuracy of cotton,corn and wheat planted area were $8 6 . 5 3 \%$ ， $7 7 . 5 4 \%$ and $8 6 . 1 9 \%$ ,respectively.

Key Words:remote sensing in agriculture；Google Earth Engine；random forest clasification；crop structure extraction；oasis agriculture