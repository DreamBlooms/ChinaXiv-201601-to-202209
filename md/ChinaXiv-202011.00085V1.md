# 关中平原城市群植被覆盖的时空特征与影响因素

王治国，白永平，车磊，陈志杰，乔富伟(西北师范大学地理与环境科学学院,甘肃兰州730070)

摘要：植被是全球及区域生态系统环境变化的重要指标，也是对人类社会活动有重要贡献的资源之一。为了研究关中平原城市群不同区域植被覆盖变化对自然和人文因子的响应，以划分为三个区域的植被作为研究对象,选取2000—2017年MODIS-NDVI遥感数据,运用趋势分析、探索性空间数据分析与地理探测器等方法，从时序演进与空间分布方面研究了18a内植被覆盖的演化及分布特征，定量分析影响植被覆盖的主导因子。遥感数据要通过投影转换、拼接、最大值合成等方法进行处理，再运用Python程序进行影像批量裁剪，将遥感数据和气象数据进行分区统计，最后对该处理数据进行讨论研究。结论表明：(1)研究期内关中平原城市群植被覆盖呈显著上升趋势，NDVI平均值增速为 $0 . 0 7 7 \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ ，阶段性变化特征明显，其中2005—2007阶段和2011—2013阶段极显著增加，最大上升速率达到了 $0 . 0 5 \cdot \mathrm { a } ^ { - 1 } \circ ( 2 )$ 空间上总体呈现“南高北低”的分布特征，研究区总体得到改善；高值区主要分布在南部秦岭北坡,受气候因子的影响更大，植被覆盖增加速度缓慢,达到轻度改善水平；低值区聚集在黄土高原边缘地区,植被增加趋势明显；中部关中平原极少部分地区植被覆盖出现了轻度退化或严重退化，以西安市及临近城市最为典型。(3)热点区主要分布在秦岭山区及关中平原中部地区,冷点区则集中于黄土高原边缘地区,植被覆盖总体以增长为主。热点区格网数量持续增多，2013年达到最大为 $4 5 . 0 7 \%$ ;冷点区域数量不断减少，2017年减少到 $9 . 8 2 \%$ ;次热点区与次冷点区主要分布在中部平原地带及北部地区，由连片分布转化为零散分布，且总量不断减少。(4）自然因素对植被覆盖的影响最为突出，其中气温和降水为影响植被覆盖的主导因子，决定力 $q$ 值分别为0.955和0.931,且气温的影响大于降水的影响；人文因子影响力较为显著，GDP因子决定力 $\textit { q }$ 值达到0.387。研究可为当地改善植被覆盖环境提供理论依据。

关键词：NDVI；趋势分析；ESDA；地理探测器；关中平原城市群文章编号： $1 0 0 0 - 6 0 6 0 \lfloor 2 0 2 0 \rfloor 0 4 - 1 0 4 1 - 1 0 \lfloor 1 0 4 1 \sim 1 0 5 0 \rfloor$

植被是陆地生态系统中不可或缺的一部分，在环境保护和水土保持方面意义重大，甚至严重影响全球气候变化和能量循环系统[1],因此，年际气候变化及植被覆盖动态监测成为了国内外研究重点。遥感技术的不断发展增加了提取植被数据的路径[2],其中MODIS系列产品多运用于气候变化与植被覆盖之间的研究，为监测植被动态演变提供了重要的科学依据和现实价值[3-4]。归一化植被指数作为植被覆盖的量化表现，可直接反映植被覆盖及演化过程[5-6,甚至对生物量等众多生态变化过程与发展状态也有很大研究价值[7-8]。

近年来，打破自然环境对经济发展的束缚、实现全球可持续发展逐渐成为研究热点，对植被覆盖的时空演变更加不容忽视[9]。国内外学者在探讨植被覆盖变化原因时，多借助遥感卫星反演数据[10],对全球植被覆盖研究做出了巨大贡献，主要包括自

# 干旱区地理

然因素和人文因素两个方面[11-14]。研究发现,中亚地区植被对气候变化尤为敏感，年NDVI值与年降水量为正相关，与气温变化呈现弱负相关性[5]；而我国的中高纬度地区NDVI值呈下降趋势[6],并在一定范围内NDVI值随海拔升高逐渐减弱[17];黄土高原地区植被在空间上呈阶梯式分布特征，且不同季节内空间差异显著[18]；阿勒泰地区大部分区域植被覆盖度变化与气温呈负相关，部分地区由于气温变暖而盖度降低[19]。植被覆盖变化虽然主要受自然因素影响，人类活动对植被的影响也不容忽视[20-2I]；内蒙古生态区发现NDVI变化受自然因素影响较大，人类活动同样对生态区内植被有较强促进或抑制作用[22]；尤其在华北地区植被改善区和退化区，人类活动的影响均大于气候变化[23]，并在稳定性评估基础上对未来趋势进行预测[24-25]。

综合前人对植被覆盖的相关研究，发现研究区域主要集中在自然条件基础较好地区，对我国中西部干旱地区研究不足，且部分研究仅定量分析了植被覆盖的影响因子[26],鲜有学者对自然条件复杂多样区域的植被覆盖变化及影响因子进行综合研究，尤其是关中平原城市群这样的生态敏感区。地处于秦岭山区与黄土高原之间，作为我国关键地带，存在复杂的自然区划特征，其地理要素研究尚显薄弱。分析该区域植被覆盖的时空变化特征与关键影响因子，有助于更好地理解植被覆盖动态变化规律，把握生态系统演变方向，揭示人地关系地域系统内相互作用。因此本文利用2000一2017年NDVI数据，对关中平原城市群植被覆盖的时空演化进行研究，分析植被覆盖的时序演进特征和空间分布规律，定量分析植被覆盖主导因子，以期为合理应对区域生态环境变化及调整提供科学依据。

# 1研究区概况

关中平原城市群包括陕西省58个市辖区和县级单位、甘肃省13个县级行政单位及山西省19个市县(图1)。西起天水市武山县，东至临汾市浮山县，东西横跨9个经度带。南接秦岭山地，北界临汾霍州市，自南向北跨过4个纬度带，占地面积达$1 0 . 7 1 \times 1 0 ^ { 4 } { \mathrm { k m } } ^ { 2 }$ 。区域整体"西南高，中东部低”,海拔$2 1 7 \sim 3 ~ 7 4 8 ~ \mathrm { m }$ ，起伏较大，按地势可分为三个部分：北部黄土高原边缘地区，中部关中平原地区，南部秦岭北坡。气候温和湿润，年均气温 $6 \sim 1 3 ~ \mathrm { { ^ circ C } }$ ,年降水量 $5 0 0 \sim 8 0 0 \mathrm { m m }$ ,南北差异较大。其中，中部和东部地区平均海拔较低，以平原地区为主，为居民点和农耕地的主要分布区。而秦岭北坡为温带和中温带气候环境，主要植被类型有阔叶林、针叶林、针阔混交林及高山草甸，适宜植被生长，植被覆盖面积广。

![](images/4ddcd97fb968cafeb3931a982478226fe0e25243e756cff2a97a90cb05addbf0.jpg)  
图1关中平原城市群位置及概况图  
Fig.1Location and overview of the urban agglomeration of Guanzhong Plain

# 2数据与方法

# 2.1 数据来源与处理

本文选用2000—2017年植被生长季MODIS13A1产品数据，该产品时间分辨率为16d,空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ ,来源于NASA官网(https://modis.gsfc.nasa.gov），遥感卫星轨道号为h26v05和 ${ \mathrm { h } } 2 7 { \mathrm { v } } 0 5 $ 。用MRT进行投影转换、拼接、最大值合成等方法，将NDVI数据处理为时间分辨率为 $1 ~ \mathrm { m o n }$ ，便于按月份进行分析，再运用Python程序进行影像批量裁剪，获得研究区NDVI数据集。利用ArcGIS软件将NDVI值统计到 $5 \mathrm { k m } \times 5 \mathrm { k m }$ 栅格上，去除异常值后进行空间分析，提取月最大值和平均值作为基础数据。定义每年 $5 \sim 9$ 月为植被生长季，用生长季内NDVI平均值表示该年植被覆盖状态。气象数据来自于中国气象数据共享网，受数据获取限制，选取2000一2015年研究区内有效站点的逐月平均气温和降水量，基于DEM数据对逐月气温和降水数据进行空间差值分析，得到气温降水的空间数据。在气候影响因子的基础上加入2015年GDP数据，通过地理探测器方法，分析2015年植被覆盖的主导影响因

子及影响程度。

# 2.2 研究方法

2.2.1时空热点分析热点分析已受到生态学、区域经济、土壤学[27-29]等相关领域的广泛关注，在研究空间位置关系时具有极大优势，对个体空间单元在区域内相关程度的分析极为重要。关中平原城市群植被覆盖在空间上具有明显集聚特征，尤其南北差异巨大，受地形、气候影响较大，对局部集聚模式进行分析显得尤为重要。具体计算方法见文献[30-31]

2.2.2趋势分析回归方程的斜率(slope)表示研究区域监测期间NDVI的斜率，可以反映植被变化的趋势和特征。对不同时期植被覆盖变化的空间分布特征进行趋势分析，试图演绎植被覆盖空间变化规律。计算公式如下：

$$
s l o p e = \frac { n \times \displaystyle { \sum _ { i = 1 } ^ { n } i \times N D V I _ { i } } - \displaystyle { \sum _ { i = 1 } ^ { n } i \sum _ { i = 1 } ^ { n } N D V I _ { i } } } { n \times \displaystyle { \sum _ { i = 1 } ^ { n } i ^ { 2 } - \left( \displaystyle { \sum _ { i = 1 } ^ { n } i } \right) ^ { 2 } } }
$$

式中： $n$ 是研究时间序列的长度； $i$ 代表第 $i$ 年； $N D V I _ { i }$ 表示第 $i$ 年的 $N D W$ 值； $s l o p e$ 代表趋势线的斜率。若$s l o p e > 0$ ，表示该栅格内植被覆盖面积变化趋势增大，且数值越大说明趋势越大，植被改善结果越好。反之，则表明该栅格内变化趋势减小。

2.2.3地理探测器地理探测器主要针对于类别数据，为了分析关中平原城市群NDVI变化的主导因子，通过地理探测器方法，选取气温、降水、人口和GDP等4个因子进行分析，计算这些因子对植被覆盖的影响。通过比较各因素 $\textit { q }$ 值的大小，定量分析植被覆盖度的主导因素。模型如下[32-34]：

$$
q = 1 - \frac { 1 } { N \sigma ^ { 2 } } { \sum } _ { h \scriptscriptstyle \cdot 1 } ^ { L } N _ { h } \sigma _ { h } ^ { 2 }
$$

式中： $q$ 值表示影响因子 $( X _ { i } )$ 对植被变化空间分布的决定力，取值范围[0，1」， $q$ 值越大表明影响因素 $( X _ { i } )$ 对植被覆盖度的影响越大，反之亦然；当值为0时表明影响因素 $( X _ { i } )$ 与植被覆盖度(Y)没有任何关系，表明植被覆盖呈现出随机性。 $N$ 和 $\sigma ^ { 2 }$ 分别表示研究区域植被覆盖的解释变量和方差； $\boldsymbol { \sigma } _ { h } ^ { 2 }$ 是某一变量的方差； $L$ 表示分层数，即影响因子分类的层数。

# 3结果与分析

# 3.1 时空格局特征

3.1.1 时序变化特征2000—2017年关中平原城市群NDVI主要呈缓慢上升趋势，生长季年际NDVI平均值均大于0.7（图2a），植被覆盖基础情况良好。18a的NDVI平均值达到0.779，且最大值出现在2013年(0.849)，最小值出现在2017年(0.705)，年际NDVI变化整体波动上升。年际变化的平均值在时间维度上可分为四个上升期：第一次上升期(2001—2004）、第二次上升期（2005—2007）、第三次上升期(2011一2013)和第四次上升期(2014—2015);其中，第二个上升期与第三个上升期增加速度分别为 $0 . 0 3 1 \cdot \mathrm { a } ^ { - 1 }$ 和 $0 . 0 3 6 \cdot \mathrm { a } ^ { - 1 }$ ,增长加速度也有较小幅度提升。五个下降期：第一次下降期(2000一2001）第二次下降期(2004—2005）第三次下降期(2007—2011）、第四次下降期(2013—2014)及第五次下降期(2015—2017)。年际NDVI平均值变化呈缓慢上升变化，上升速率为 $0 . 0 7 7 \cdot ( 1 0 \mathrm { ~ a } ) ^ { - 1 }$ ,尤其2011年以后NDVI值上升加快(图2b），最大值出现在2013年(0.949)，最小值在2005年(0.893)。由平均值及最大值的年际变化趋势可以看出，关中平原城市群的植被覆盖在时间维度上表现出波动上升的趋势。

![](images/417221ba165be5a0c7c07bdee84619e730f054b8deb4d9e146cb3f3ad1a6d952.jpg)  
图22000—2017年NDVI平均值与最大值年际变化走向图  
Fig.2Inter-annual variation trend of $N D W$ average and maximum values from 2OoO to 2017

3.1.2空间分异特征空间上关中平原城市群植被覆盖呈现出南高北低、平原地区破碎化的总体特征。为了清晰辨别植被覆盖演化情况，植被生长差异最大化考虑，选取NDVI变化拐点处年份数据进行可视化(图3)。由于研究区自然条件复杂多样，将研究区具体划分为三个区域：北部黄土高原边缘地区、中部关中平原地区与南部秦岭山区。其中，秦岭山区天然分布有大量植被，属于温带季风气候、半湿润区，为植物生长提供了有利的水热条件，植被覆盖度较高，包括天水市、宝鸡市、商洛市及运城市等地的部分地区。除了通过生态自然恢复外，还进行了封育保护、退耕禁牧、还林还草和植树造林等措施，以提高植被覆盖率，改善生态环境。

中部平原地区植被覆盖状况处于中等水平，受人类活动影响较大。该地区以人工植被为主，平原中部地区多为耕地，包括各种农作物、蔬菜、果林和各类城市绿地，受城市扩张影响较大，因此总体植被覆盖面积较小，且城市周边退化严重。部分低值区逐渐被高值区所取代，高值区由(图3a)零散分布发展到片状分布(图3f)，植被覆盖有所改善，

北部黄土高原边缘地区主要受地理条件和气候因素影响，最直接的影响因子为降水。由于黄土高原为极敏感地区，水土严重流失，水量极度不足，导致植被减少，也极大地制约了植被的大面积覆盖，导致大部分地区植被覆盖较低(图3a)。随着环境治理工作的进行，铜川市以东地区逐渐发展为高值区，植被覆盖逐渐发生改善。

![](images/1ebd4f5f3aacedb585a210ab55eace155d141432ac6d6a0149d65d6abf2f400a.jpg)  
图3关中平原城市群植被覆盖的空间分布变化分析  
Fig.3Analysis of spatial distribution of vegetation cover in urban agglomeration of Guanzhong Plain

# 3.2 动态演变特征

3.2.1趋势变化特征趋势分析可以很好的反映18a间关中平原城市群NDVI的演变方向，整体表现出从南到北越来越明显，仅中部极少部分地区出现退化现象(图4)，植被退化集中在西安市、宝鸡市等城市化进程较快区域。具体来说，研究区北部整体植被覆盖得到明显改善，尤其是甘肃省的天水市、平凉市及西峰区等黄土高原边缘地区。上述区域是国家退耕还林还草的重点实施区域，通过对植树造林、退耕还林等保护环境观念的转变，保水固土效果显著，生态条件不断改善，植被生长的空间基础发展迅速，覆盖情况变化明显。其他北部地区同样得益于政策指导，生态系统得到优化，NDVI值上升较快。

轻度改善区域连片分布在东南部的秦岭山区。该区域气候适宜植被生长，植被覆盖基础良好。受人类活动的正面影响，政策保护和环境意识不断加强，植被覆盖趋于平稳上升阶段，增速较慢。严重退化区集中在西安市中心地区，该地区处于平原中部，多以农耕地为主。为了支持城市化的快速发展，城市周围大面积地区被占用，包括耕地、草地和林地等植被类型被动转换成建设用地及公共用地，从而减少了经济发达地区及周边区域植被覆盖面积，NDVI明显降低。城市扩张导致周边地区NDVI值下降明显，但对植被破坏的间接影响更加可怕，包括金台区、杨凌农业高新技术产业示范区、新城区、莲湖区和碑林区等区域均出现严重退化现象。轻度退化区零散分布在严重退化区域周围，以及部分经济基础较好的地区，如凤翔县、扶风县、武功县等。

![](images/76125791df329a6dd7aca2ef0798236552da8950d689d7f5c991bd28845d7a0d.jpg)  
图4关中平原城市群生长季NDVI变化趋势 Fig.4NDVI trends in the growing season of urban agglomeration of Guanzhong Plain

基本不变区域主要位于南部地区及黄土丘陵沟壑区，河谷平原地区也有较少分布。该地区气候更加适宜植被生长，受人类行为干扰较少。且近几年未出现大范围的极端天气，植被保持自然的生长状态，因此并没有发生大的变化。

3.2.2空间集聚特征局部空间格局采用优化的热点分析，继续分析研究植被覆盖的空间格局演化特征，用于识别具有统计显著性的高值(热点)和低值(冷点)的空间聚类，以期深刻理解 $Z$ 值可视化后的结果，以 $5 \mathrm { k m } \times 5 \mathrm { k m }$ 格网单元为对象，按自然间断点法分为四类：冷点、次冷点、次热点和热点，生成关中平原城市群植被覆盖的空间格局冷热点演化图(图5)。

热点区域在秦岭北坡、宝鸡市西北部、咸阳市东北部及运城市东南部部分地区集聚模式明显（图5a)，因自然环境良好，形成大面积的植被覆盖区。2001年热点网格共有1455个，到2013年已达到2069个，数量上有明显的上升。空间上高值区发展越来越多，包括宝鸡市北部、渭南市北部及关中平原中部大部分地区(图5f)，并沿着关中平原边缘不断向东部发展，一直延续到夏县、绛县与浮山县一带，覆盖区域从2001年的 $3 1 . 2 8 \%$ 增加到2013年$4 0 . 4 3 \%$ 。区域之间植被覆盖联系不断加强，空间异质性减弱。

冷点区域分布在黄土高原边缘地区及研究区北部渭南市、运城市和临汾市大部分地区。但冷点区域在自然恢复和人为调节作用下不断减少，网格数量从2001年的981个降低到2013年的523个，降低了 $9 . 9 9 \%$ 。集中在西安、咸阳、宝鸡等地的经济发展较快地区及黄土高原边缘地区，尤其关中平原和汾渭平原冷点区域减少程度大，逐渐转化为热点或

![](images/e5712b7350abe89cac521a55fc4424d4d5f854fb644ecca4907f986a8ce55005.jpg)  
图5关中平原城市群空间冷热点分布图  
Fig.5Cold hot spot distribution map of urban agglomeration of Guanzhong Plain

次热点地区。

NDVI呈次热点与次冷点区域连片分布在关中平原的中部地区、黄土高原沟壑地带及汾渭平原地区，受到自然与人文的多方面影响，次冷点与次热点也不断由片状分布变为零散分布，镶嵌在热点区与冷点区之间，由2001年2147个网格数量减少到1991，减少了 $3 . 4 0 \%$ ，尤其中东部地区的冷点区域减少明显。关中平原中心地区植被在人类活动负面影响下受到强烈干扰，经济发展和城市扩张迫使城郊地区植被覆盖度减少，所以西安、咸阳等城市冷点区逐渐扩大。黄土高原边缘地区则在政策导向下，部分地区由冷点转化为次冷点，植被覆盖发展趋势变好。

# 3.3 影响因素分析

研究区内植被覆盖受到自然、人文、社会等多种因素的综合影响。本文通过梳理将NDVI值作为植被覆盖的指标，以2015年GDP、多年平均气温(tem)和多年平均降水 $\left( { \boldsymbol { p r e } } \right)$ 作为影响因子指标，利用地理探测器分析人为因素和自然因素对研究区植被变化的影响。因子探测主要通过影响因子在一定程度上比较分析变量的空间分异( $( g$ 值),选用因子探测的结果进行分析，结果显示决定力大小排序依次为：气温 $( 0 . 9 5 5 ) >$ 降水 $( 0 . 9 3 1 ) \ > \mathrm { G D P }$ (0.387)，且 $p = 0$ 通过检验，具有统计学意义。气温、降水和GDP对植被覆盖的空间分异程度有不同程度的影响，都是影响植被覆盖的主要因子。

各探测因子的 $q$ 值均显示较高值，表示各个因子对植被覆盖的影响都比较大(表1)。从空间分异的结果来看，气温对植被的影响最为显著，是植被覆盖变化的主导因子。不仅直接影响植被的生长过程，对植物种类也影响较大，表现在山区大量针叶林、阔叶林、灌木丛等不同的区位分布。气温因子的 $q$ 值达到了0.955,说明该区域气温对植被生长的影响力更大，而降水因子的 $q$ 值为0.931,也具有较高的影响力，说明自然因素是植被生长过程中的

# 表1因子探测器结果

Tab.1 Factors detector results   

<html><body><table><tr><td></td><td>pre</td><td>tem</td><td>GDP</td></tr><tr><td>q statistic</td><td>0.931</td><td>0.955</td><td>0.387</td></tr><tr><td>p value</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

注:pre代表降水因子； $t e m$ 代表气温因子： $\cdot$ 为因子探测值大小

控制因素。综合来说，气候是植被覆盖的主导动力因子，太白山地区常年郁郁葱葱，主要因为在这一地区夏季受西南及太平洋暖湿气流影响，气候炎热湿润;而秦岭以北是温带季风气候、半湿润区，也非常利于植物的生长，主要植被类型有针叶林、阔叶林、混交林、高山灌丛和高山草甸，所以该地区NDVI值处于较高水平。

由表1可知，GDP为次要控制因素，虽然城市周边地区也受到城市化的影响，但GDP刚刚开始发展，仅在起步阶段，所以并没有达到较高水平，对生态方面的影响力并不大。虽然 $q$ 值略小于气候因子的决定力，但仍具有较强的影响。人文因子包括促进作用和抑制作用：一方面，人类为了应对城市化的快速扩张和经济的高速发展，不得不占用城郊结合部及周边地区的农用地、草地及林地等，减少了植被覆盖的面积。另一方面，提出对植被的保护政策，大力倡导退耕还林还草工程。特别是三北防护林工程的实施，通过生物措施和工程措施的结合，根据山地系统和子流域的综合管理,创造了大量的水源涵养林，有效地提高了生态环境质量

# 4结论

利用ArcGIS10.2软件分析了2000—2017年关中平原城市群的MODIS-NDVI时序影像，通过热点分析、趋势分析和地理探测器等方法研究了关中平原城市群植被覆盖的时序演进和空间分布，定量分析了植被覆盖的主导因子及其他影响因子。结果表明：

（1）2000一2017年，关中平原城市群生长季植被覆盖变化呈波动上升趋势，平均上升速率为$0 . 0 7 7 \cdot ( 1 0 \mathrm { ~ a ~ } ) ^ { \mathrm { ~ - ~ } 1 }$ ，其中 2005—2007阶段和 2011—2013阶段增长明显，呈极显著增加。生长季NDVI平均值都超过了0.7，最大值达到0.849，最大上升速率达到了 $0 . 0 5 \cdot \mathrm { a } ^ { - 1 }$ ，植被覆盖水平良好。

(2）植被覆盖各地区差异较大，发展速率也不尽相同，总体为改善状态。其中，黄土高原边缘地区受降水的影响最大，在政策保障下植被不断增加，得到显著改善；关中平原大部分地区处于改善明显趋势，只有西安及周边地区由于人类活动的影响大于气候因子的影响，出现严重退化或轻微退化的趋势；南部秦岭山区植被受气候因子的影响更

大,处于基本不变状态。

（3）热点数量不断增多，从2001年的 $3 1 . 7 5 \%$ 上升至2013年的 $4 5 . 1 5 \%$ ,主要集中在秦岭北坡及关中平原中部地区，并缓慢向东扩张；冷点数量不断减少，从2001年的 $2 1 . 4 1 \%$ 降低为2013年的 $1 1 . 4 1 \%$ ，由北部逐渐转移到西北部黄土高原沟壑区，次热点与次冷点由连片分布在平原地带转化为零散分布，且总量不断减少。

（4）气候因素对植被覆盖的影响更为突出，为植被覆盖的主导因子,其中降水和气温的决定力 $\boldsymbol { q }$ 值分别为0.931和0.955，对植被覆盖影响显著，且气温的影响大于降水的影响;GDP对该区域植被覆盖的决定力为0.387，影响力较小。

# 5讨论

本文通过局部空间自相关分析，对研究范围内植被变化趋势进行了探索，发现不同区域影响植被覆盖的主导因素不同。由于黄土高原边缘区、关中平原地区及秦岭山区地形起伏变化较大，空间差异特征显著，植被类型多种多样，不同地区植被覆盖度及变化趋势大不相同。若要具体的进行植被恢复建设工作，应该把黄土高原区、关中平原区和秦岭山区分开研究，针对各个区域不同植被类型主导因子进行具体研究。对研究区资源禀赋进行分类研究才能对症下药，使植被改善效果达到最大化。黄土高原地区植物主要靠降水生长，对降水因素依赖很大，但该地区严重缺水，土壤保水性差，植被覆盖度偏低，所以建设重点应放在人为技术保水固土、恢复植被。平原地区除了自然条件的影响，人文因素对植被覆盖的影响也不可忽视，应在政策方面加大植被管理力度，包括封育保护、退耕禁牧等手段。秦岭山区自然条件非常适合植被生长，人类活动的负面作用微弱，应严格控制资源开发与利用。

本文所使用的气象数据是通过差值分析获得的，精度上受到很大影响，下一步研究应该重新考虑数据源的获取，对不同类型地区进行精确划分，提高研究价值。本文研究范围较大，以城市群为研究区域，对城市内的植被影响考虑欠缺，没有体现出每个城市的演化路径及演变趋势，应该按城市实际资源进行研究，对城市内植被覆盖有具体的参考价值。另外对植被覆盖的影响力应该是多因子交互影响的，单一因子的影响几乎不存在，应考虑多重因子对植被的影响，尤其人文方面的政策或者技术，可以短时间产生显著影响。

参考文献(References）   
[1]SONG Xiaopeng,HANSEN M C,STEHMAN S V,et al. Global land change from 1982 to 2016[J]. Nature,2018,560,639 - 643.   
[2]何兴元,任春颖,陈琳,等.森林生态系统遥感监测技术研究进 展[J].地理科学,2018,38(7):997-1011[HE Xingyuan,REN Chunyin,CHEN Lin,et al. The progress of forest ecosystems monitoring with remote sensing techniques [J]. Scientia Geographica Sinica,2018,38(7):997-1011.]   
[3］丁翔,白中科.黄土区露天煤矿复垦土地植被覆盖度监测及影 响因素[J].经济地理,2017,37(11):198－204.[DING Xiang, BAI Zhongke. The calculation method of vegetation coverage and influencing factors in Antaibao open pit coal mine in loess area[J].Economic Geography,2013,37(11):198-204.]   
[4]钱琛,陈海滨，侯现慧.生态建设背景下陕西省植被覆盖时空 变化及其影响因素研究[J].干旱区地理,2020,43(2)：425- 433.[QIAN Chen,CHEN Haibin,HOU Xianhui. Temporal and spatial variation of vegetation cover and its influencing factors in Shaanxi Province in the context of ecological construction[J]. Arid Land Geography.2020,43(2):425-433.]   
[5］刘斌,孙艳玲,王永财,等.基于SPOT／NDVI华北地区植被变 化动态监测与评价[J].干旱区资源与环境,2013,27(9)：98- 103.[LIU Bin,SUN Yanling,WANG Yongcai,et al. Monitoring and assessment of vegetation variation in north China based on SPOT/NDVI[J]. Journal of Arid Land Resources and Environment,2013,27(9):98-103.]   
[6]白建军,白江涛,王磊,等.2000—2010年陕北地区植被 NDVI 时空变化及其与区域气候的关系[J].地理科学,2014,34（7)： 882 - 888.[BAI Jianjun,BAI Jiangtao, WANG Lei,et al. Spatio-temporal change of vegetation NDVI and its relations with regional climate in northern Shaanxi Province in 20oo - 2010[J]. Scientia Geographica Sinica,2014,34(7):882-888.]   
[7]LEVEAU LM,ISLAFI,BELLOCQ MI. Predicting the seasonal dynamics of bird communities along an urban-rural gradient using NDVI[J].Landscape and Urban Planning,2018,177: 103-113.   
[8]WANG L,PAN Y,CAO Y,et al. Detecting early signs of environmental degradation in protected areas:An example of Jiuzhaigou Nature Reserve,China[J]. Ecological Indicators,2018, 91:287 -298.   
[9］苟娇娇,王飞,金凯,等.黄土高原植被恢复引发区域气温下降 [J].生态学报,2018,38（11）：3970－3978.[GOUJiaojiao, WANG Fei,JINKai,et al. Cooling effect induced by vegetation restoration on the Loess Plateau[J].Acta Ecologica Sinica,2018, 38(11) :3970 -3978.]   
[10］周亮,车磊,周成虎.中国城市绿色发展效率时空演变特征及 影响因素[J].地理学报,2019,74(10):2027－2044.[ZHOU Liang，CHE Lei,ZHOU Chenghu. Spatio-temporal evolution and influencing factors of urban green development eficiency in China[J].Acta Geographica Sinica,2019,74（10）：2027 - 2044.]   
[11］李学梅,任志远,张.气候因子和人类活动对重庆市植被覆 盖变化的影响分析[J].地理科学,2013,33(11)：1390-1394. [LI Xuemei,REN Zhiyuan,ZHANG Chong,Spatial-temporal variations of vegetation cover in Chongqing City （1999- 2010）: Impacts of climate factors and human activities[J]. Scientia Geographica Sinica,2013,33（11):1390-1394.]   
[12]赵丽红,王屏,欧阳勋志,等.南昌市植被覆盖度时空演变及 其对非气候因素的响应[J].生态学报,2016,36(12)：3723- 3733.[ZHAO Lihong,WANG Pin,OUYANG Xunzhi,et al. An analysis of the spatio-temporal variation in fractional vegetation cover andits relationship with non-climate factors in Nanchang City,China[J].Acta Ecologica Sinica,2016,36(12）:3723- 3733.]   
[13］赵鸿雁,陈英,周翼,等.甘肃中东部植被生长季 NDVI时空变 化及其对气候因子的响应[J].干旱区地理，2019,42(6)： 1427 - 1435.[ZHAO Hongyan，CHEN Ying,ZHOU Yi,et al. Spatiotemporal variation of NDVI in vegetation growing season and its responses to climatic factors in mid and eastern Gansu Province from 2008 to 2016[J].Arid Land Geography. 2019,42 (6):1427 - 1435.]   
[14]LI Xinhui,LEI Shaogang,CHENG Wei,et al. Spatio-temporal dynamics of vegetation in Jungar Banner of China during 2000 - 2017[J].Journal of Arid Land,2019,11(6):837- 854.   
[15］殷刚，孟现勇,王浩,等.1982—2012年中亚地区植被时空变化 特征及其与气候变化的相关分析[J].生态学报，2017，37 （9):3149- 3163.[YIN Gang,MENG Xianyong,WANG Hao, et al.Spatial-temporal variation of vegetation and its correlation with climate change in Central Asia during the period of 1982——2012[J].Acta Ecologica Sinica,2017,37(9）:3149 - 3163.]   
[16］刘宪锋,朱秀芳,潘耀忠,等.1982—2012年中国植被覆盖时空 变化特征[J].生态学报，2015,35（16)：5331－5342.[LIU Xianfeng, ZHU Xiufang,PAN Yaozhong,et al. Spatiotemporal changes in vegetation coverage in China during 1982—2012[J]. Journal of Arid Environments,2015,35(16):5331- 5342.]   
[17］张静静,郑辉,朱连奇,等.豫西山地植被 NDVI及其气候响应 的多维变化[J].地理研究,2017,36(4)：765-778.[ZHANG Jingjing，ZHENG Hui,ZHU Lianqi,et al.Multi-dimensional changes of vegetation NDVI and its response to climate in Western Henan Mountains[J].Geographical Research,2017,36(4): 765 - 778.]   
[18］刘旻霞,赵瑞东,邵鹏,等.近15a黄土高原植被覆盖时空变化 及驱动力分析[J].干旱区地理,2018,41(1)：99－108.[LIU Minxia, ZHAO Ruidong,SHAO Peng,et al. Temporal and spatial variation of vegetation coverage and its driving forces in the Loess Plateau from 2001 to 2015[J].Arid Land Geography. 2018,41(1):99-108.]   
[19］韩飞飞,闫俊杰,郭斌.阿勒泰地区植被覆盖度及ET对气温变 化的响应[J].干旱区地理,2019,42(6)：1436-1444.[HAN Feifei,YAN Junjie,GUO Bin.Response of vegetation cover and ET to temperature variation in Altay Prefecture[J].Arid Land Geography.2019,42(6):1436-1444.]   
[20］李建飞,李小兵,周义.2000—2015年乌兰察布市生长季NDVI 时空变化及其影响因素[J].干旱区研究,2019,36(5):1238- 1249.[LI Jianfei,LI Xiaobing,ZHOU Yi. Spatiotemporal variation of NDVI and its affecting factors in Ulanqab City in growing season from 2000 to 2015[J].Arid Zone Research，2019,36 (5):1238-1249.]   
[21］李卓,孙然好,张继超,等.京津冀城市群地区植被覆盖动态变 化时空分析[J].生态学报,2017,37（22)：7418-7426.[LI Zhuo，SUN Ranhao，ZHANG Jichao，et al.Temporal-spatial analysis of vegetation coverage dynamics in Beijing-Tianjin-Hebei metropolitan regions[J]. Journal of Arid Environments,2017, 37(22):7418- 7426.]   
[22］张清雨,赵东升,吴绍洪,等.基于生态分区的内蒙古地区植被 覆盖变化及其影响因素研究[J].地理科学,2013,33(5)： 594 - 601.[ZHANG Qingyu,ZHAO Dongsheng，WU Shaohong,et al. Research on vegetation changes and influence factors based on eco-geographical regions of Inner Mongolia[J]. Scientia Geographica Sinica,2013,33（5):594- 601.]   
[23］刘斌,孙艳玲，王中良,等.华北地区植被覆盖变化及其影响因 子的相对作用分析[J].自然资源学报，2015，（1)：12－23. [LIU Bin,SUN Yanling, WANG Zhongliang,et al. Analysis of the vegetation cover change and the relative role of its influencing factors in north China[J].Journal of Natural Resources, 2015,(1):12-23.]   
[24] CHANG Xu, KATCCHOVA A L. Predicting soybean yield with NDVI using a flexible fourier transform model[J]. Journal ofAgricultural and Applied Economics,2019,51(3):402-416   
[25］李俊刚,闫庆武,熊集兵,等.贵州省煤矿区植被指数变化及其 影响因子分析[J].生态与农村环境学报,2016,32(3):374- 378.[LI Jungang,YAN Qingwu, XIONG Jibing,et al. Variation of vegetation index in coal mining areas in Guizhou Province and its affecting factors[J].Journal of Ecology and Rural Environment,2016,32(3):374- 378.]   
[26］岳辉,刘英.近15a陕西省植被时空变化与影响因素分析[J]. 干旱区地理,2019,42(2):314-323.[YUE Hui,LIU Ying. Vegetation spatiotemporal variation and its driving factors of Shaanxi Province in recent15 years[J].AridLand Geography, 2019,42(2):314-323.]   
[27］朱军,李益敏,余艳红.基于GIS 的高原湖泊流域生态安全格 局构建及优化研究——以星云湖流域为例[J].长江流域资源 与环境,2017,26(8):1237-1250.[ZHUJun,LIYimin,YU Yanhong. Study of construction and optimization of ecological security pattern of lake basin in plateau based on GIS:A case study ofXingyun Lake Basin[J].Resources and Environment in the Yangtze Basin,2017,26(8):1237-1250.]   
[28」郑德凤，郝帅，孙才志.基于DEA-ESDA的农业生态效率评价 及时空分异研究[J].地理科学，2018,38（3)：419－427. [ZHENG Defeng,HAO Shuai,SUN Caizhi.Evaluation of agricultural ecological efficiencyandits spatial-temporal differentiation based on DEA-ESDA[J]. Scientia Geographica Sinica, 2018,38(3):419- 427.]   
[29］胡碧峰，王佳昱,傅婷婷,等.空间分析在土壤重金属污染研究 中的应用[J].土壤通报，2017,48(4)：1014－1024.[HUBifeng，WNAG Jiayu,FU Tingting,et al.Application of spatial analysis on soil heavy metal contamination:A review[J].Chinese Journal of Soil Science,2017,48(4):1014-1024.]   
[30］周亮，周成虎，杨帆，等.2000一2011年中国 $\mathrm { P M } _ { 2 . 5 }$ 时空演化特 征及驱动因素解析[J].地理学报，2017，72(11)：2079-2092. [ZHOU Liang,ZHOU Chenghu,YANG Fan,et al. Spatio-temporal evolution and the influencing factors of $\mathrm { P M } _ { 2 . 5 }$ in China between 2000 and 2011［J].Acta Geographica Sinica,2017,72 (11):2079-2092.]   
[31］汪凡，白永平，周亮，等.中国高校科技创新能力时空格局及影 响因素[J].经济地理,2017,37(12):49－56.[WANG Fan, BAI Yongping,ZHOULiang,et al.Spatio-temporal pattern and influencing factors of scientific and technological innovation capability of universities in China[J].Economic Geography,2017, 37(12):49-56.]   
[32]丁悦，蔡建明，任周鹏，等.基于地理探测器的国家级经济技术 开发区经济增长率空间分异及影响因素[J].地理科学进展， 2014,33(5):657-666.[DING Yue,CAI Jianming,REN Zhoupeng,et al. Spatial disparities of economic growth rate of China's National-level ETDZs and their determinants based on geographical detector analysis[J].Progress in Geography,2014,33 (5):657-666.]   
[33］徐秋蓉，郑新奇.一种基于地理探测器的城镇扩展影响机理分 析法[J].测绘学报,2015,44(b12):96－101.[XU Qiurong, ZHENG Xinqi.Analysis of influencing mechanism of urban geographical detector[J].Acta Geodaetica et Cartographica Sinica, 2015,44(b12):96-101.]   
[34]刘彦随，杨忍.中国县域城镇化的空间特征与形成机理[J].地 理学报,2012,67(8):1011-1020.[LIU Yansui,YANG Ren. The spatial characteristics and formation mechanism of the county urbanization in China［J].Acta Geographica Sinica,2012,67 (8):1011-1020.]

# Spatio-temporal characteristics and influencing factors of vegetation coverage in urban agglomeration of Guanzhong Plain

WANG Zhi-guo， BAI Yong-ping， CHE Lei， CHEN Zhi-jie， QIAO Fu-wei(College ofGeographyand Environmental Science,Northwest Normal University,Lanzhou73oo7o,Gansu,China)

Abstract:Vegetation is an important indicator of environmental changes in global and regional ecosystems, and it is also one of the resources that make an important contribution to human social activities.To study the response of vegetation coverage to natural and human factors in different parts of the Guanzhong Plain urban agglomeration in western China,we divided the region of interest into three vegetation areas for our research. We selected MODIS-NDVI remote-sensing data obtained during 2000-2017. Using trend analysis,exploratory spatial data analysis,and geodetector methods，we studied the evolution and distribution characteristics of vegetation cover during those 18 years from the perspectives of temporal evolution and spatial distribution. We quantitatively analyzed the main factors afecting vegetation coverage.We first processed remote-sensing data by such methods as projection conversion,splicing,and maximum-value synthesis and then applied batch image cropping using Python.The remote-sensing and meteorological data were categorized by applying statistical methods.From the processed data,we drew the following conclusions:(（1） During the study period,vegetation coverage of the Guanzhong Plain urban agglomeration showed a significant upward trend. The average NDVI growth rate was 0.077 every 10 years,and the characteristics of periodic changes were obvious.Among them,the 2005-2007 and 2011-2013 periods increased significantly,and the maximum ascent rate reached O.05 per year.（2） Our spatial data generalyconfirmed the distribution characterized as“high in the south and low in the north,”and vegetation coverage improved overallin the study area.The high-value areas are mainly distributed on the northern slope of the southern Qinling Mountains,which is more affected by climatic factors.The vegetation coverage is increasing

# 干半区地理

slowly and has slightly improved.The low-value areas are concentratedon the edge of the Loess Plateau,and the vegetation coverage is obviously increasing there,whereas a small portion of the central part of the Guanzhong Plain showed slightto severe degradation,with Xi'anand its neighboring cities being the most typical.（3）Hot spots are mainly distributed in the Qinling Mountains and the central of the Guanzhong Plain,while cold spots are concentrated along the margins of the Loess Plateau，where vegetation coverage is mainly increasing. Hot-spot areas continue to increase,having reached a maximum of $45 . 0 7 \%$ in 2013,while the number of cold spots continues to decrease,having been reduced to $9 . 8 2 \%$ in 2017. The hot and cold spots are mainly distributed in the central plains and northern areas,which have changed from continuous to scattred distribution,and the total volume is continuously decreasing.（4）The most-prominent influences on vegetation coverage are natural factors,among which temperature and precipitation are dominant. The determinant $q$ values are 0.955 and 0.931,respectively,the influence of temperature being greater than that of precipitation.The influence ofhuman factors is important but not prominent; the determinant $q$ value of the GDP factor reaches only O.387.The conclusions of this paper could provide some theoretical basis to improve vegetation-coverage environment in the study area.

Key words:NDVI; trend analysis； ESDA； Geodetector；urban agglomeration of Guanzhong Plain

# 中国科学院新疆生地所与阿姆斯特丹大学合作在中亚新生代荒漠草原生态系统演化研究中获进展

中亚拥有世界最大的荒漠草原生态系统，尽管学者们猜测古荒漠草原生态系统与现代时期具有显著差异，但是造成这个结果的原因尚不明确。

针对这一问题，中国科学院新疆生态与地理研究所荒漠与绿洲生态国家重点实验室张宏祥副研究员、常存高级工程师参与中国科学院“国际人才计划"荷兰阿姆斯特丹大学CarinaHoom教授研究团队，通过结合精确的中亚花粉化石记录与地质、动物区系和气候数据，重建了4300万年以来荒漠草原生态系统的演化历史。研究发现，中亚荒漠草原在始新世-渐新世气候转变时期迅速变冷变干，并造成灾难性的变化。低海拔地区变成了几乎没有植被覆盖的干旱荒漠。由于缺乏食物，大型动物被啮齿类和免类等小型动物所替代。这一时期是中亚生态系统演化的重要节点，并塑造了现代生态系统的原型。在中新世气候适宜期，禾本科等草本植物开始在中亚低海拔地区大面积扩张。此时的植被与始新世-渐新世气候转变时期的植被完全不同。

现在，快速的气候变化正在造成广泛的荒漠化，更好地认识干旱区过去的环境变化情况具有重要意义，它有助于揭示干旱生态系统的稳定性和优先保护的必要性。

相关研究成果以 Cenozoic evolution of the steppe-desert biome in Central Asia为题发表在 Science Ad-vances。文章链接:https://advances.sciencemag.org/content/6/41/eabb8227。