# 边疆旅游地县域旅游经济时空变迁及驱动机制研究新疆案例

朱怡婷},²，熊黑钢，白洋³，杨丽³，曹开军³，唐金稳4（1新疆大学资源与环境科学学院,新疆乌鲁木齐830046；2北京联合大学应用文理学院,北京100083；3新疆大学旅游学院,新疆乌鲁木齐 830049；4 华南理工大学经济与贸易学院,广东广州 510006)

摘要：以新疆74个县域单元为研究对象选取多个指标,利用 ESDA、ArcGIS和GeoDa等分析方法和手段及动态面板数据模型，分析2008—2017年新疆县域单元旅游经济空间格局演变特征地域差异及驱动机制。结果表明：(1）县域旅游经济集聚特征呈“下降—上升—下降一上升”的态势，彼此之间差异明显，集聚性存在显著的由北向南梯度增强的格局特征。（2）县域旅游经济的“多核心、多条带”分布逐渐形成,但并未改变“北热南冷”的分布格局。（3）受“东北—西南”方向牵引力影响,旅游经济重心轨迹变化呈多个“V”字型重叠分布，也使标准差椭圆的覆盖范围也在此方向上逐渐增大。（4）旅游资源禀赋和政策支持是影响县域旅游经济格局演变的主要驱动因素。交通条件的改善和人力资本水平的提高并非都能促进各县域旅游经济的发展，各影响因素在不同区域间存在明显的强度差异。

关键 词：边疆；县域；旅游经济；时空变迁；驱动机制文章编号： 1000-6060(2019)02-0392-12(0392\~0403)

旅游经济格局是深度描述区域旅游发展在一定时期内旅游经济内部结构的外在表现，也是不同地理单元之间的旅游发展实力的对比。适度的经济差距有助于推动资源要素的有效配置，反之会弱化已形成的经济关系[1]。旅游经济发展存在差异的现象较为普遍,一直备受学界关注[2-3]。国外学者对此研究范围从单一的旅游地转向区域化地理单元，研究问题从旅游活动与地域空间的关系与特征[4-6],以及不断丰富的旅游地理空间理论发展[7-8],为区域旅游经济研究积累了丰富的经验。我国有学者从地理空间角度描述或评价区域旅游发展[9-1],及与该现象相关的各种影响因素进行详细的论证[12-13]。并对旅游经济区域发展差异与变化趋势[14-15]、生产要素[16]、产业分布[17]等方面对区域旅游经济差异进行实证分析与规律总结。

随着国内外旅游环境的不断变化，对旅游经济区域差异与规律等问题的研究也伴随旅游产业不断演进与研究视角、方法的多元与统计工作的不断完善而成为需要持续总结的命题。目前的研究方法和研究视角趋于多元，研究尺度以宏观尺度的国家、省域、区域集群为主。根据新经济地理学理论,地理要素的分布与发展，会因不同的地域层次而具有不同的外在表现和内在联系。县域作为基层行政单元，不仅是政府工作的落脚点，也是目前考察特定地域内部发展差异的重要区域。

县域旅游是以乡村旅游为核心的小尺度研究单元[18],作为当下城市居民品质化休闲度假需求的最佳载体，是现阶段旅游活跃区。在我国旅游业阶段性升级的背景下，县域旅游作为现阶段旅游发展的重要支撑，逐渐成为未来旅游发展和研究的新方向[19]。目前对县域旅游经济的研究内容多以案例地的形式对其经济、制度、发展模式的研究[20-23],以及其旅游产业在规划与开发方面的讨论[24-25]。但对县域旅游经济的研究在国内的重视程度不够，理论视角与技术方法尚显薄弱[26],尚未开展针对县域旅游经济格局的测度、演变规律及形成机理的研究，也未形成一套成熟的方法体系。

新疆地处中国西北边陲，因地理区位与环境拥有数量多、种类全的旅游资源，而成为国内西北热门的边疆旅游目的地。作为丝绸之路经济带“核心区”，区域差异始终是制约新疆旅游发展的一大障碍，也是丝绸之路经济带旅游复兴政策落地的关键问题,更关乎新疆旅游的可持续发展。“一心一地”政策与“旅游大通道”建设为平衡南北旅游发展差异有一定成效。但不可否认，新疆旅游的非均衡发展已是共识。地缘广袤，资源齐全，但其旅游经济发展经历了怎样的变迁？现今的格局形态由何因素主导而成？把握这些问题，对于明确区域旅游发展战略和制定有针对性的产业发展政策具有重要的现实意义。基于此，本文以新疆74个县市为研究对象，在结合探索性分析与ArcGIS、GeoDa等空间统计分析模块的相关功能，从空间角度对其旅游经济发展格局与演化测度的基础上，并选取多个指标构建动态面板数据模型，对整个县域单元旅游经济格局的形成的主导要素进行诊断，已揭示旅游经济空间分异形成机理，进而对不同区域影响因素强度进行分析。透视新疆县域旅游经济发展的实践状况与时空格局演变规律及驱动机制，从微观层面上有效揭示新疆旅游发展的地域性与方向性，以期补充旅游经济格局在小尺度单元研究的不足，为县域旅游持续、健康发展提供理论借鉴。

# 1指标、数据与方法

# 1.1 指标选取

考虑到研究区旅游经济发展的相关特点及指标获取的可能性及意义，且能够客观准确反映县域旅游经济的实际情况，借鉴已有的研究成果，本文以旅游总收入(tel)表示旅游经济发展水平；旅游资源禀赋会影响旅游流与建设投资从而影响当地旅游经济发展，用旅游景区指数(tai)体现（本文在此仅统计2008—2017年各县3A级以上景区）；交通条件会影响游客的可进人程度，县域交通主要以公路为主，使用各县市公路网密度(hnd)来表示，经济发展水平从旅游供需方面都对旅游经济发展产生影响，用各县市人均 $\mathrm { G D P } ( g d p )$ 表征;政府调控会作用于地方产业结构并影响旅游业集聚，三产投入量占地区生产总值的比重 $( { i p } )$ 来反应地方政府对旅游经济的影响；人力资本水平 $( h c )$ 对于促进旅游经济发展具有重要意义，并对其发展的长期效用影响显著，采用人均教育财政支出来反映各县市在旅游人力资本投入的水平结构。

# 1.2 研究单元界定及数据说明

本文以2008—2017年面板数据为样本，因新疆的行政区划经历了较多的行政区变动，为保证数据的完整性和可获取性，将乌鲁木齐县归入乌鲁木齐市。在乌昌一体化的政策推动下，2008年米泉撤市并入乌鲁木齐市。将阿拉尔市、图木舒克市、五家渠市、北屯市、铁门关市、双河市、可克达拉市、昆玉市等直辖市归入原属行政单元。2015年吐鲁番地区撤地设市，同时撤县级原吐鲁番市设高昌区。2016年哈密地区撤地设市，县级原哈密市撤市设伊州区。为了便于分析，以下称原吐鲁番市、原哈密市。数据来源于各地市《统计年鉴》、部分县市相关年份的《国民经济和社会发展统计公报》、《政府工作报告》、《新疆县域社会经济资料》以及新疆维吾尔自治区2016年《A级景区名录》与新疆A级景区等级评定公告资料，最终选取74个数据完整的县市作为研究基础数据，借助GeoDa0.95i与ArcGIS10.3对数据进行分析。

# 1.3 研究方法

# 1.3.1空间自相关分析

（1）全局空间相关性分析。全局Moran's $I$ 指数。用以衡量新疆各县域旅游经济在全疆范围的空间关联与集聚特征。基于位置相近的县市间的比较,如果相近县市具有相似的变量取值,则为“正空间自相关”,反之则为“负空间自相关”[27]。公式为：

$$
I = \frac { \displaystyle { \sum _ { i = 1 } ^ { n } \sum _ { j \neq 1 } ^ { n } w _ { i j } \big ( x _ { i } - \bar { x } \big ) \big ( x _ { j } - \bar { x } \big ) } } { \displaystyle { S ^ { 2 } \sum _ { i = 1 } ^ { n } \sum _ { j \neq 1 } ^ { n } w _ { i j } } }
$$

式中： $\boldsymbol { w } _ { i j }$ 表示空间权重矩阵， $x _ { i }$ 和 $x _ { j }$ 为第 $i$ 个区域单元的观察值。采用邻接矩阵进行定义。Moran's $I$ 指数的取值范围为-1，1，当 $I { > } 0$ 时为正相关，即属性值高的区域相互聚集，属性值低的区域相互聚集；当 $I < 0$ 时为负相关，表示负相关， $I = 0$ 表示不相关： $I$ 越接近1，空间差异越小； $I$ 越接近-1，空间差异越大。

（2）局部空间相关性分析。局部Moran's $I$ 指数可以弥补全局空间自相关分析中是无法发现的空间异质性，并观测要素指标发生集聚所处的位置，可利用 $\mathrm { G e o D a 0 . \ 9 5 i }$ 软件将分析结果进行可视化表达[28]。公式为：

$$
I = \frac { n z _ { i } \sum _ { j } w _ { i j } z _ { j } } { z ^ { T } z } = { z _ { i } } ^ { \prime } \sum _ { j } w _ { i j } { z _ { j } } ^ { \prime }
$$

式中： ${ z _ { i } } ^ { \prime }$ 和 ${ z _ { j } } ^ { \prime }$ 是经过标准差标准化的观测值。当 $I$ 为正值时，区域 $i$ 与邻近区域之间呈空间正相关关系；反之则呈空间负相关关系。

结合Moran散点图来表达局部观测数据的分布与聚合情况，是能够反映数据的变化形态以及对空间数据进行可视化的图示，进而识别出不同县市之间属性特征值的相关性。通过分析局部指标来描述区域单元周围显著的相似值区域单元之间空间集聚程度的指标，来识别Moran散点图中不同象限对应的区域。

Getis-Ord $\mathrm { G i } *$ 统计。通过冷热区域要素在空间聚类分布的特征来判定核心及外围区域，本文考察的观测值中包括位置上的观测值，探索县域旅游经济的空间异质性[29],公式为：

$$
G _ { i } \ = \ \sum _ { j \ = 1 } ^ { n } w _ { i j } x _ { j } \Bigg / \sum _ { j \ = 1 } ^ { n } x _ { j }
$$

对统计量的检验与局部Moran指数相似，其检验值为：

$$
Z ( \ G _ { i } ) = G _ { i } - E ( \ G _ { i } ) { \Bigg / } { \sqrt { V A R ( \ G _ { i } ) } }
$$

式中： $w _ { i j }$ 为距离权重，是通过距离 $d$ 定义的。县域要素中的高值区易于被发现,若仅有单独一个县域要素的高值区不能视为热点，被同样具有高值的县域要素所包围才能被看做为热点区域。 $z$ 值得分越高，热点的聚类就越紧密，反之，冷点聚类就越紧密。1.3.2空间位移与方向性分布分析旅游经济重心可以反映新疆县域旅游经济发展重心轨迹变化情况[30]。重心计算方法如下：

$$
{ \cal T } _ { L o n } = \frac { \displaystyle \sum _ { i = 1 } ^ { n } { \cal T } _ { i } x _ { i } } { \cal T } _ { i } \ : , { \cal T } _ { L a n } = \frac { \displaystyle \sum _ { i = 1 } ^ { n } { \cal T } _ { i } y _ { i } } { \cal T } _ { i } \ :
$$

式中： $T _ { L o n } , T _ { L a n }$ 为各县市旅游经济重心的经纬度， $T _ { i }$ 表示各县市旅游经济水平。 $( x _ { i } , y _ { i } )$ 为各县市坐标。

要素重心的空间移动距离[31],公式为：

$$
D = c \ \sqrt { \left( T _ { l o n i } - T _ { l o n j } \right) ^ { 2 } + \left( T _ { l a n i } + T _ { l a n j } \right) ^ { 2 } } \left( 6 \right)
$$

式中：用 $D$ 表示要素重心 $( T _ { l o n i } , T _ { l a n j } ) \mathrm { _ { \Omega } } ( T _ { l o n j } , T _ { l a n i } )$ 的坐标值在不同年份的移动距离( $\mathbf { k m } _ { \mathbf { \Omega } , \mathbf { \Omega } } ^ { \dagger }$ )，常数 $C$ 取$1 1 1 . 1 1 1 \mathrm { ~ k m ~ } \cdot \mathrm { ~ ( ~ } ^ { \circ } \mathrm { ~ ) ~ } ^ { - 1 }$ ,可以通过该值将球面坐标单位 ${ \bf \Xi } ( { \bf \Lambda } ^ { \circ } )$ 转化为平面距离( $\mathbf { \bar { k m } } )$ 。

用标准差椭圆描述区域空间要素的分布特征与演变，此方法包括要素重心、转角 $\theta$ 、长轴、短轴等基本参数。转角 $\theta$ 为顺时针变化角度,用于反映旅游经济要素分布的移动方向，通过长轴与短轴反映旅游经济要素在主要与次要方向上的空间离散程度，判断要素值在空间分布的范围、整体轮廓与方向性[32]。以旅游经济重心为起点分别计算短轴与长轴方向的标准差确定椭圆轮廓，通过分析近十年的数据来观察椭圆随时间变化的特征，揭示新疆旅游经济要素的总体分布、差异特征以及时空演变过程。

1.3.3回归分析回归分析是对变量间的影响因素及相互关联性进行定量分析，通过建立因变量和自变量之间的关系函数，利用样本数据对模型参数做出估计。该分析方法对影响因素之间建立回归模型，测度各自变量对因变量的影响效果。

# 2 县域旅游经济空间演变分析

# 2.1 总体空间演变特征

新疆各县市旅游经济在2008—2017年间的Moran's $I$ 值结果均为正值(表1），检验值 $Z ( I )$ 均大于3.2495，且在（ $P \leqslant 1 \%$ )上显著，说明不同县市之间的旅游经济呈现明显的空间正相关，即邻近县市间旅游经济发展关联性强，整体空间集聚性逐渐增强。2009年因受事件影响，Moran'sI值出现大幅度下降。10a间各县市旅游经济的整体呈现“下降—上升—下降一上升"的集聚态势。根据Moran'sI值变化，旅游经济发展可分为四个阶段：2008一2009年为衰减期,受事件影响，各县市旅游经济大幅度降低，集聚强度减弱，区域间旅游经济联系强度降低；2010—2012为稳步攀升期，随着新疆旅游环境转好，县市间集聚度增强，旅游经济关联度增强，Mo-ran's $I$ 值有较大幅度的跃升。在旅游业发展的良性周期,旅游业发展所依托的旅游资源、劳动力以及各类生产要素的有效供给以及源于旅游消费需求的激励，信息、交通、网络等都会推进各类生产要素的提升，从而推动旅游全要素的发展，各县市间的旅游经济联系会逐步增强。2013—2014年为下滑期，受事件影响使新疆旅游发展遭遇艰难的一年，旅游要素在不同区域间交换频率减缓，各县市之间的旅游经济联系减弱，2015—2017的旅游经济再次迅速攀升。Moran'sI值因旅游经济状况上下波动，说明周边县市旅游发展的好坏会彼此互相影响，旅游经济联系的紧密程度也会随着旅游发展的阶段和时期而变化。

表1旅游经济全局Moran's $\pmb { I }$ 指数  
Tab.1Moran'sIindex of tourism revenue   

<html><body><table><tr><td>年份</td><td>Moran 指数I</td><td>Moran指数 期望值E(I)</td><td>显著性 检验值P</td><td>标准化 统计量 Z(I)</td></tr><tr><td>2008</td><td>0.243 8</td><td>-0.0118</td><td>0.001 0</td><td>3.547 1</td></tr><tr><td>2009</td><td>0.220 9</td><td>-0.0118</td><td>0.001 0</td><td>3.249 5</td></tr><tr><td>2010</td><td>0.2271</td><td>-0.0118</td><td>0.001 0</td><td>3.893 7</td></tr><tr><td>2011</td><td>0.235 4</td><td>-0.0118</td><td>0.0010</td><td>4.314 9</td></tr><tr><td>2012</td><td>0.253 6</td><td>-0.0118</td><td>0.0010</td><td>4.896 3</td></tr><tr><td>2013</td><td>0.258 1</td><td>-0.0118</td><td>0.0010</td><td>5.340 1</td></tr><tr><td>2014</td><td>0.230 1</td><td>-0.0118</td><td>0.0010</td><td>3.974 2</td></tr><tr><td>2015</td><td>0.3287</td><td>-0.0118</td><td>0.0010</td><td>5.424 5</td></tr><tr><td>2016</td><td>0.3451</td><td>-0.0118</td><td>0.001 0</td><td>7.213 2</td></tr><tr><td>2017</td><td>0.341 2</td><td>-0.011 8</td><td>0.001 0</td><td>7. 126 5</td></tr></table></body></html>

# 2.2 局部空间演变特征

2.2.1Moran'sI散点图分析为了对新疆县域范围内临近区域间的局部关联特征作进一步分析，利用 $\mathrm { G e o D a 0 . 9 5 i }$ 软件以2008、2012、2017年为3个时间截面，对74个县市进行局部动态分析（图1）。大部分县市的旅游经济发展水平Moran's $I$ 都集中分布于一、三象限。关联类型属于旅游高收入县市彼此包围，周边县市彼此之间差异度不大，成为高一高集聚区；旅游低收入县市彼此包围，且周边县市旅游经济发展水平整体较差，形成了低一低集聚区。一象限内的县市相对于三象限内县市在空间上更为集聚，说明旅游发展的优势资源在迅速积累。二象限内是低一高聚集区，意为旅游经济落后的县市被旅游经济发达的县市包围，出现区域旅游经济发展不平衡现象，属于负空间相关。四象限是高一低聚集区，即为旅游经济发达的县市被旅游经济落后的县市包围，也会出现区域旅游经济发展不平衡现象，属于负空间相关。象限内的点越靠近第一象限点，说明受到高一高区的辐射影响越强。靠近高一高区域的点越密集，表明新疆的旅游业存在较强的空间依赖性。随着一象限的点越来越密集、三象限的点越来越分散，表明，新疆近 $1 0 \mathrm { ~ a ~ }$ 旅游地域两极分化现象显著，但总体在向好的方向发展。

2008、2012、2017年通过显著性检验的县市分别有44个（占 $5 9 . 4 \%$ ）、51个（占 $6 8 . 9 \%$ )和40个（占 $54 \%$ ），集中分布在新疆的北部区域与南部区域（表2）。2008年的高一高类县市主要分布在新疆北部阿勒泰一伊犁一昌吉区域,2012年间，青河县、博乐县、霍城县、乌苏市、库尔勒市进入高一高区，分布范围逐渐由北向西、南拓展,并于2017年继续向西延伸,温泉县转变为高一高区。说明在高值区的集聚效应下，对周边县市形成了辐射带动作用。低一低类县市主要以阿克苏地区、和田地区、克州、喀什地区为主，县市间经济发展联通性差、交通闭塞，虽有丰富的人文旅游资源，但开发利用难度大，旅游关联度差，周边县市的空间集聚能力较弱，无法

![](images/3f75aaacf54954aa3bae677df1489ae2724be1c88a3a75746cbd1375865d2cd7.jpg)  
图1旅游经济Moran's $I$ 散点图  
Fig.1Moran's $I$ scatter plot of tourism economy

# 干旱区地理

Tab.2County-scale corresponding to the Moran's $\pmb { I }$ scatter plot of tourism economy   

<html><body><table><tr><td>年份</td><td>高一高</td><td>低一高</td><td>低一低</td><td>高一低</td></tr><tr><td></td><td>2008 年福海县、富蕴县、昌吉市、沙湾县、乌鲁木齐市、呼图壁县、奎屯市、轮台 鄯善县、奇台县、克拉玛依市、木垒县、富康市、县、玛纳斯县、和布克赛尔 原吐鲁番市、和硕县、博湖县、焉耆县、和静县、县、库尔勒市、石河子市 新源县、尼勒克县、伊宁县、伊宁市、尉犁县</td><td></td><td>伽师县、和田市、乌恰县、和田县、洛浦喀什市、 县、莎车县、阿克苏市、英吉沙县、策勒 县、墨玉县、阿克陶县、且末县、麦盖提 县、阿图什县、塔县</td><td>巴楚县</td></tr><tr><td></td><td>2012年福海县、富蕴县、青河县、奇台县、沙湾县、乌鲁呼图壁县、奎屯市、轮台 木齐市、木垒县、鄯善县、昌吉市、焉耆县、富康 市、原吐鲁番市、和硕县、博湖县、库尔勒市、和 静县、新源县、尼勒克县、伊宁县、伊宁市、尉犁尔县</td><td>县、石河子市、托里县、玛</td><td>喀什市、伽师县、和田市、乌恰县、和田 县、洛浦县、莎车县、阿克苏市、英吉沙 纳斯县、精河县、和布克赛县、策勒县、墨玉县、阿克陶县、且末县、 麦盖提县、阿图什县、塔县</td><td>巴楚县、 阿瓦提县</td></tr><tr><td></td><td>县、博乐市、霍城县、克拉玛依市、乌苏市 沙湾县、昌吉市、克拉玛依市、博乐市、巩留县、 库尔勒市、霍城县、鄯善县、焉耆县、原吐鲁番 市、乌苏市、博湖县、特克斯县、和静县、新源察布查尔县</td><td>子市、轮台县、玛纳斯县、麦盖提县、塔县</td><td>2017年温泉县、富康市、奇台县、乌鲁木齐市、和硕县、福海县、呼图壁县、木垒莎车县、伽师县、和田县、和田市、洛浦巴楚县 县、奎屯市、精河县、石河县、策勒县、墨玉县、且末县、英吉沙县、</td><td></td></tr></table></body></html>

形成良好的联动式发展。低一高与高一低类县市易受周边高一高与低一低类县市的影响而出现波动变化，这一点证实了区域旅游发展水平与其所处邻区旅游业发展状况有显著的相关性。

2.2.2Getis-Ord Gi $*$ 统计通过计算 2008、2012、2017年的 $G$ 指数，根据值的大小划分冷热点区域（表3）。新疆县域旅游经济热点区域总体分布在北部区域，旅游经济发展水平由南向北逐渐走高。热点区域中，新疆北部的布尔津县长期处于全疆县市旅游的核心，且于2012年位其周边区域联通性较好的西侧、东南侧部分县市出现向热点区发展的势头。以“乌一昌”经济圈为核心向西辐射至伊犁州，联通“乌一昌一伊”、向东辐射至吐鲁番一哈密地区联通“乌一昌一吐一哈”；向南辐射至巴州北部，联通“乌一昌一巴”等旅游要素流通顺畅的旅游经济带，区域旅游发展的联动效应显著增强，北部区域冷点区域范围逐渐缩小。其中，作为入疆东大门的吐鲁番一哈密地区，虽占区位交通优势，但2017年的新增核心区却出现在旅游资源丰富，高等级景区密集的伊犁州新源县，其地理优势并未转为旅游优势，依靠资源优势发展旅游仍是新疆的主导。由此表明北部资源富集区一直是旅游发展较为活跃的地区，是新疆旅游经济发展的动力引擎。全疆的冷点区域集中分布在阿克苏地区、克州、喀什地区、和田地区等南部区域。2008年在温宿县、阿瓦提县、巴楚县形成的带状区域旅游发展情况较南疆其他地区稍好，但2012年“解体”。2017年受北部区域辐射带动，温宿县与南疆盆地其他北缘县市由过去的冷点区逐渐好转，而除喀什市外的其他县市则进入“休眠”状态。随着北部区域旅游辐射功能促使区域间带状化联动发展，新增热点核心区域虽有南移，但县域旅游经济在地理分布上依旧呈现“北热南冷”的分布格局。

表2旅游经济Moran's $\boldsymbol { { \cal I } }$ 散点图对应县市分布  
表3旅游经济热点区域演变  
Tab.3Evolution of the hot spots and cold spots of the tourism economy   

<html><body><table><tr><td>年份</td><td>热点地区</td><td>次热点地区</td><td>冷点地区</td><td>次冷点地区</td></tr><tr><td>2008 年布尔津县</td><td></td><td>阜康市、原吐鲁番市、裕民 县、沙湾县、和静县、乌鲁 木齐市</td><td>温泉县、吉木乃县、和布克赛尔县、额敏县、塔城市、托里县、精 河县、石河子市、玛纳斯县、奎屯市、察县、英吉沙县、莎车县、 麦盖提县、伽师县、阿克苏市、库车县、沙雅县、新和县、拜城 县、乌什县、和田市、和田县、墨玉县、洛浦县、策勒县、阿图什 市、阿克陶县、乌恰县、库尔勒市、焉耆县、尉犁县、若羌县、且 末县、和静县、和硕县、博湖县</td><td>阿勒泰市、福海县、博 乐市、霍城县、伊宁 县、尼勒克县、特克斯 县、温宿县、尉犁县、 鄯善县、阿瓦提县、巴 楚县</td></tr><tr><td></td><td>哈巴河县</td><td>温泉县、霍城县、巩留县、 鄯善县、沙湾县、昌吉市、 乌鲁木齐市、奇台县、巴里 坤县、和静县、博湖县</td><td>2012 年布尔津县、、福海县、阜康市、裕民县、吉木乃县、和布克赛尔县、额敏县、塔城市、托里县、精河县、石 河子市、玛纳斯县、呼图壁县、奎屯市、喀什市、英吉沙县、莎车 县、麦盖提县、伽师县、巴楚县、阿克苏市、库车县、沙雅县、新湖县、尉犁县、焉耆县 和县、拜城县、乌什县、和田市、和田县、墨玉县、洛浦县、策勒 县、阿图什市、阿克陶县、乌恰县、库尔勒市、轮台县、若羌县、 且末县、和静县、和硕县、博湖县</td><td>木垒县、特克斯县、温 宿县、阿瓦提县、岳普</td></tr><tr><td></td><td>新源县</td><td>市、乌鲁木齐市、巴里坤 阜康市、博湖县</td><td>2017年布尔津县、哈巴河县、沙湾县、昌吉福海县、吉木乃县、和布克赛尔县、奎屯市、玛纳斯县、呼图壁尼勒克县、哈密市、伊 县、吉木乃县、木垒县、轮台县、焉耆县、察县、喀什市、英吉沙吾县、温宿县、拜城 县、原吐鲁番市、阜康市、县、莎车县、麦盖提县、伽师县、巴楚县、阿克苏市、沙雅县、新县、库车县、尉犁县 裕民县、巩留县、昌吉市、和县、乌什县、阿瓦提县、和田市、和田县、墨玉县、洛浦县、策 勒县、阿图什市、阿克陶县、乌恰县、库尔勒市、焉耆回族自治 县、轮台县、若羌县、且末县、和静县、和硕县、博湖县</td><td></td></tr></table></body></html>

2.2.3空间位移与方向性演变分析旅游经济重心在各年份波动范围主要在 $8 5 . 4 2 ^ { \circ } \sim 8 6 . 5 4 ^ { \circ } \mathrm { E }$ ，$4 3 . 5 4 ^ { \circ } \sim 4 5 . 4 0 ^ { \circ } \mathrm { N }$ 之间（表4），北起和布克赛尔和沙湾县，南至县昌吉州玛纳斯县，所对应的地理位置大位于昌吉州与塔城地区交界处。重心呈“V"字型位移，方向在“东北—西南一西北”方向上变迁。分布格局总体呈“北拉南扯”的态势，且位置相对固定（图2）。这表明在西北方向上，县域旅游发展速度有所加快，但10a间总体转移速度慢、幅度小，其中2010、2013年受事件影响是重心位移距离最小的两年。2008—2017年重心移动距离为 $8 6 . 5 3 1 ~ \mathrm { k m }$ ，侧面反映出新疆的旅游发展多年以来旅游产业僵化，各县之间的旅游发展步伐缓慢。

新疆旅游经济发展的标准差椭圆分布呈东北一西南方向分布，椭圆中心主要位于昌吉州玛纳斯县。椭圆主轴标准差变动范围不超过 $1 . 6 1 5 \ \mathrm { k m }$ ,2011、2012年出现相对明显的空间扩张。副轴变化范围不超过 $1 . 2 5 6 ~ \mathrm { k m }$ 。相对而言，沿X轴标准差的变动幅度大于沿Y轴标准差的变动幅度，说明来自东北一西南方向的县市旅游变化力量强劲。2008—2017年转角 $\theta$ 在 $5 7 . 6 6 ^ { \circ }$ 变动到 $7 1 . 1 0 ^ { \circ }$ 之间变动，而2008—2015年转角 $\theta$ 从 $5 7 . 6 6 ^ { \circ }$ 变动到 $7 1 . 7 8 ^ { \circ }$ 。东北一西南方向展布态势进一步加剧,充分显示出各县域旅游经济要素向东北方向集聚。这主要是因为昌吉州地处“乌一昌”经济圈内旅游发展起步早，是重要的旅游集散地，旅游发展较成熟。2016一2017年转角逐渐回归原位,这种变化趋势主要受的西北、新疆中部地带等椭圆长轴两端众多旅游地的影响，在聚拢有利资源促使旅游要素向其转移的同时，对椭圆范围的扩张也有一定影响。

表4旅游经济标准差椭圆参数变化  
Tab.4Change of standard eliptical deviation parameter of tourism economy   

<html><body><table><tr><td>年份</td><td>坐标</td><td>移动方向</td><td>转角</td><td>沿X轴标准差</td><td>沿Y轴标准差</td><td>移动距离</td></tr><tr><td>2008</td><td>86.54°E,45.40°N</td><td>西南</td><td>57.663</td><td>4.332</td><td>3.052</td><td>0.000</td></tr><tr><td>2009</td><td>86.05°E,43.63°N</td><td>南偏西</td><td>53.083</td><td>3.954</td><td>2.376</td><td>204.064</td></tr><tr><td>2010</td><td>86.04°E,43.54N</td><td>西北</td><td>51.695</td><td>3.936</td><td>2.242</td><td>10.062</td></tr><tr><td>2011</td><td>85.42°E,44.78°N</td><td>东南</td><td>64.600</td><td>5.197</td><td>2.815</td><td>154.040</td></tr><tr><td>2012</td><td>86.08°E,43.63°N</td><td>西偏北</td><td>67.724</td><td>5.551</td><td>3.490</td><td>147.326</td></tr><tr><td>2013</td><td>85.96°E,43.65N</td><td>北偏东</td><td>65.031</td><td>4.357</td><td>3.498</td><td>13.517</td></tr><tr><td>2014</td><td>86.16E,45.08°N</td><td>南偏西</td><td>71. 106</td><td>4.046</td><td>2.926</td><td>160.435</td></tr><tr><td>2015</td><td>86.14°E,43.85°N</td><td>西北</td><td>71.781</td><td>4.081</td><td>3.321</td><td>136.685</td></tr><tr><td>2016</td><td>85.59°E,44.96N</td><td>东北</td><td>59.357</td><td>4.672</td><td>2.749</td><td>140. 638</td></tr><tr><td>2017</td><td>85.78°E,45.23N</td><td></td><td>58.892</td><td>4.959</td><td>2.857</td><td>34.012</td></tr></table></body></html>

![](images/41ff34492075102e00ac7790914c025a0b961ba586cc03094d7f50fff1d73528.jpg)  
图22008—2017年新疆旅游经济重心变化 Fig.2Moving track of the gravity center of tourism economy in Xinjiang from 2008—2017

# 3空间格局演变驱动机制

# 3.1 模型构建

通过上述综合分析表明新疆县域旅游经济在空间上表现出显著的南北差异，为进一步寻找这种两极分化格局的形成机理，本文以旅游经济水平作为被解释变量，其余指标为解释变量来构建动态面板数据模型。建立固定效应面板数据模型如下[33]：

$$
\ln t e l _ { i t } = \beta _ { 0 } + \beta _ { 1 } \ln t a i _ { i t } + \beta _ { 2 } \ln h n d _ { i t } + \beta _ { 3 } \ln g d p _ { i t } +
$$

$$
\beta _ { 4 } \mathrm { l n } i p _ { i t } + \beta _ { 5 } \mathrm { l n } h c _ { i t } + \mu _ { i } + \varepsilon _ { i t }
$$

式中， $i = 1 , 2 \cdots , n ; t = 1 , 2 , \cdots , T ,$ 其中， $n$ 表示74个县市， $T$ 表示 $1 0 \mathrm { ~ a ~ }$ 时间周期。为保证面板数据的平稳性且避免出现伪回归，采用LLC，IPS，ADF和PP等方法对其进行单位根检验[34],对不平稳的因素进行一阶差分后再进行检验，检验结果至少在 $10 \%$ 的统计水平上显著，表明变量指标具有平稳性的特征。协整检验结果显示，PanelADF和GroupADF统计量的检验效果较好，解释变量数据均通过 $10 \%$ 统计水平上的显著性检验，表明其之间存在协整关系，限于篇幅，单位根与协整检验结果略去。利用Eviews8.0软件进行面板数据回归分析，估计结果见表4。

# 3.2 驱动力分析

从表5回归模型结果的系数来看，lntai的影响系数均为正，且在全疆、北疆、南疆、东疆各变量系数中都是最高的。其次是lnip对优势资源的调控具有较强的自我强化机制，二者对旅游经济水平的增长的正向效应影响最强。另外，lnhnd发达程度对全疆县域单元影响有较强的正效应，但局部之间存在政府效应不一致的情况。Ingdp的发展水平与 $\ln h c$ 水平影响最弱。

旅游资源禀赋因素的回归系数均为正且对全疆县域旅游经济增长的作用最大，景区指数每增加$1 \%$ ,县域旅游经济水平增长 $0 . 3 7 1 \%$ ,表明旅游新常态下，县域旅游经济的发展对景区的发展有较强的程度的依赖。受天山山脉的阻隔，地貌与气候条件赋予南北疆不同的地表景观和水热条件，旅游资源分布受自然地理条件的影响更为直接；旅游景区指数由2008年的128提高到2017年的859，10a间累积增长5倍，旅游资源的开发、建设不断提升。其中北部区域生态环境质量优，景观资源数量多、品级高且基数设施较为完备，3A级以上景区在2008—2017年间的平均增长速度为 $9 . 8 \%$ ，回归计量模型的系数为0.547，在三大区域间影响程度最大。而以喀什、和田、克孜勒苏州为主的南疆地区中许多县市生态环境脆弱，降水少、气温高，沙漠和戈壁景观占多数，形成与北疆截然不同的景观资源，随着游客游览纵深向西南扩展，南疆地区3A级以上景区在近 $1 0 \mathrm { ~ a ~ }$ 间的平均增长速度为 $6 . 3 \%$ ，旅游资源禀赋每增加 $1 \%$ ，对南疆地区县域旅游经济增长$0 . 3 8 5 \%$ 。东疆县市数量少，影响系数最小,旅游资源主要以吐鲁番地区，对旅游经济的拉动作用也十分明显，说明旅游资源作为吸引物虽对旅游活动具有控制和分异作用，但无论是在全疆范围还是三大区域对旅游经济的拉动都十分明显。

表52008—2017年面板数据回归结果  
Tab.5Panel data regression results form 20o8 to 2017   

<html><body><table><tr><td colspan="2">变量</td><td colspan="2">全疆</td><td colspan="2">北疆</td><td colspan="2">南疆</td><td>东疆</td></tr><tr><td>旅游资源禀赋(lntai)</td><td>β</td><td>0.371***</td><td>β</td><td>0.547 ***</td><td>β</td><td>0.385***</td><td>β</td><td>0.376***</td></tr><tr><td rowspan="2">交通条件(lnhnd)</td><td>β</td><td>(11.424)</td><td></td><td>(7.632)</td><td></td><td>(6.033)</td><td></td><td>(5.305)</td></tr><tr><td></td><td>0.206**</td><td>β</td><td>0.416 ***</td><td>β</td><td>-0.249 **</td><td>β</td><td>0.164**</td></tr><tr><td rowspan="2">社会经济发展水平(Ingdp)</td><td>β</td><td>(1.982)</td><td></td><td>(8.404)</td><td></td><td>(-1.970)</td><td></td><td>(2.035)</td></tr><tr><td></td><td>0.308 **</td><td>β</td><td>0.341**</td><td>β</td><td>0.202**</td><td>β</td><td>0.159 **</td></tr><tr><td rowspan="2">政策支持(lnip)</td><td>β4</td><td>(11.151)</td><td></td><td>(2.309)</td><td></td><td>(2.331)</td><td></td><td>(2.213)</td></tr><tr><td></td><td>0.367***</td><td>β4</td><td>0.481***</td><td>β4</td><td>0.267 **</td><td>β</td><td>0.204 **</td></tr><tr><td rowspan="2">人力资本水平（lnhc)</td><td>β5</td><td>(5.247)</td><td></td><td>(6.837)</td><td></td><td>(2.399)</td><td></td><td>(1.983)</td></tr><tr><td></td><td>-0.071 *</td><td>β</td><td>0.247**</td><td>β</td><td>-0.131 **</td><td>β</td><td>0.140 **</td></tr><tr><td>常数项</td><td></td><td>(-1.395)</td><td></td><td>(2.107)</td><td></td><td>(-2.095)</td><td></td><td>(2.007)</td></tr><tr><td></td><td></td><td>-6.807</td><td></td><td>2.495</td><td></td><td>- 4.964</td><td></td><td>8.190</td></tr><tr><td>nT</td><td></td><td>740</td><td></td><td>370</td><td></td><td>310</td><td></td><td>60</td></tr><tr><td>R²</td><td></td><td>0.819</td><td></td><td>0.771</td><td></td><td>0.821</td><td></td><td>0.794</td></tr></table></body></html>

注：括号内为 $\mathbf { \chi } _ { t }$ 值, $* * * * * * *$ $*$ 分别表示 $P$ 值在 $1 \%$ （2 $5 \%$ $. 1 0 \%$ 的统计水平显著。

政府主导的三产投入计量回归系数均为正，且通过 $1 \%$ 和 $5 \%$ 显著性检验。全疆范围政策每提高$1 \%$ ,县域旅游经济水平将提升 $0 . 3 6 7 \%$ 。作为特殊的“功能资源”的政策，其特定的优先发展权对于县域旅游经济水平的提升具有重要的外力导向与调控作用。北疆区域以地缘优势带动优势资源，政府的主导作用依资源与经济条件的不同而进行调控。1995年，优先发展天山北坡经济带；2000年西部大开发战略，使北疆逐步经贸产业集群;2013年“一带一路"政策的提出;2015年新疆被定位于丝绸之路经济带核心区等政策，使县域旅游经济发展重点集中逐步向北疆聚集，空间上集中在资源丰富、环境良好、交通便利的县市，形成了以“乌一昌一伊”为极化中心的旅游发展局面。旅游发展不仅是一种经济活动，也是复杂的政治活动，会受到不同程度政治因素的影响[35],全域旅游的提出对新疆旅游业的发展亦是以优势资源、社会经济条件等为优选，并落地于各县市着重发展。三大区域通过影响生产要素流动方向，也引起了县域旅游经济区域增长分异。这与2008—2017年的旅游经济重心始终出现在伊－昌附近的结论相符，两州所辖的大部分县市均进入标准差椭圆的覆盖范围，为热点或次热点的区域，为椭圆的移动贡献力量。

交通是区域旅游快速发展的重要驱动力，影响着旅游发展的极化于分散。 $1 0 \mathrm { ~ a ~ }$ 间全疆公路路网密度由 $8 . 7 \%$ 提升到 $1 1 . 2 \%$ ，交通设施水平不断改善。计量回归系数通过了 $1 \%$ 和 $5 \%$ 水平显著性检验，表明交通设施的改善对全疆县域旅游经济的发展作用明显。全疆范围公路网密度每提高 $1 \%$ ,县域旅游经济水平提高 $0 . 2 0 6 \%$ 。北疆交通区位优良，各县市间交通网络覆盖度高，与省外联合开通多条旅游专线，自驾公路建设力度加大为各县市带来更多的客源。同时，新疆32个边境县中，20个位于北疆地区，其中连接中哈、中蒙、中塔、中俄边境的县市，如哈巴河县、温泉县、昭苏县、奇台县、木垒县、富蕴县、塔城市、布尔津县等目前都已是热门的边境旅游区，旅游交通效率的提升加速了旅游经济重心向西、北移动。南疆地区交通基础设施薄弱、公路数量少等级低，对外交通运输仅有喀什、库尔勒初步形成了综合运输体系，铁路仅为一条南疆铁路连通外界，不仅不利于信息流、资本流的注入，还造成产品与市场的经济联系困难。现今的交通基础设施虽有提升，但未能很好的作用在旅游经济的发展上，lnhnd的影响系数均为负，公路网密度每增加 $1 \%$ ,县域旅游经济发展降低 $0 . 2 4 9 \%$ ，说明对于经济欠发达区域，路网密度的改善还未能达到能够促进旅游经济发展的水平线。

社会经济发展水平与人力资本的注入是新疆县域旅游经济格局演化的重要驱动力。一方面，人均GDP 的增长对全疆旅游经济发展的拉动作用明显。但新疆包含空间因素的“地带性”区域经济发展要素供给的非均衡导致全疆经济均量能力较弱[36]。新疆南北城镇化水平“北高南低”差异明显[37]，北部"经济区”、“经济带”汇集，经济强县多，旅游产业发展经济基础条件较好,便于各县旅游产业集中发展。北疆县域人均GDP 每增加 $1 \%$ ,各县市旅游经济水平提高 $0 . 3 4 1 \%$ ,在三大区域中影响最显著。“一带一路”和"丝绸之路经济带核心区”的建设,为保障北疆各县旅游业发展提供生产要素的有效供给，进一步助推北部区域成为旅游经济强区，也促使了县域旅游经济重心和标准差椭圆不断向西、北移动。新疆的27个国家级贫困县中有21个分布在南疆，占南疆县市总数的 $49 \%$ ,经济基础薄弱,对县域旅游经济的拉动作用较北疆县市稍显不足，但相较东疆效果明显，这可能与旅游资源过度集中在吐鲁番地区且业态单一有关。这种“地带性”差异最终将新疆南北区域县域旅游经济发展分割成“三分天下”的经济格局形态，并且这种局面在研究期间始终保持不变。另一方面,实现经济增长需要人力资本的注入，也是实现全要素发挥生产力的重要因素[38]。随着新疆旅游经济业态的逐渐分化,全疆范围人力资本水平的计量回归系数为-0.071，通过$10 \%$ 水平显著性检验，说明人均教育财政支出对全疆范围旅游经济提升的影响力较弱，对不同区域而言，对北疆旅游经济的影响系数为正且最大，对南疆旅游经济的影响系数为-0.131。表明北疆、东疆地区人资本水平的提高有助于旅游经济发展，而南疆地区人力资源的提升并未促进旅游经济的发展，这是由于北疆、东疆社会经济条件基础较好,人才集中度相对较高，旅游发展良性循环，旅游业人力资本培育效果较好。特别是北部各县市居民参与旅游积极性较高，旅游富民工程不但使本地文化素质得以提高，以布尔津县、新源县、特克斯县等龙头品牌为示范的旅游产业链吸引外来人资本的注入，形成逐渐专业化的旅游服务体系，增强了县域经济发展能力。南疆经济相对落后，政府虽在各县普及九年义务教育，但因地域环境、传统思想观念等原因使文化程度依然较低，加之非制度因素在一定程度上阻碍县域经济的发展与社会进步[39-40]。教育均等化的推进，弱化了城镇人力资本水平的集聚能力，许多南疆各县市具备高素质的人才工作范围半径变大，进一步加重了人才外流，优秀的当地文化资源未能充分挖掘，如喀什市、巴楚县的旅游仍以“点状化”模式发展，与周围县市联动效应弱旅游产品难以适应现代消费需求。现有的旅游从业人员文化素质低，自主发展能力差。社会经济环境的好坏与人力资本的聚集对县域旅游产业良性循环与人力资本价值的转化至关重要，提升二者的发展水平应是促进今后县域旅游经济发展的重点。

# 4结论与启示

本文通过空间统计学方法对新疆县域旅游经济的时空分布与格局演变的实证分析，描述出县域旅游经济在空间上的变动轨迹，揭示其演变过程，较好的反映出新疆县域旅游经济的空间异质性特征，结论如下：

（1）2008—2017年，新疆县域旅游经济格局总体表现明显的关联性与空间异质性特征。其空间集聚程度表现为“下降一上升一下降一上升”的态势。局部集聚特征显示，一、三象限县市分布集中程度高，北疆阿勒泰—伊犁—昌吉县市高—高聚集区逐渐连片，辐射范围向西、南两侧。随着空间关联范围的不断扩大，区域局部差异逐渐缩小;分布在南疆的部分县市的低一低空间集聚形态逐渐分散至周围直至覆盖三地州的大部分片区，其中喀什市最早落出高一低形态区域，泽普与巴楚因孤立无援持续保持高一低聚集的空间形态难以改变，南北两极分化旅游经济格局十分明显。

（2）随着区域联通性的改善，旅游要素流通加快，以布尔津县为旅游核心区、乌一昌旅游为热点区域的局面逐渐被打破，形成由“乌一昌”经济圈向东、西、南多个方向辐射的局面，“多核心、多条带”分布显著，县市旅游联动效应明显。除喀什市外南疆三地州始终处于“休眠”状态，“北热南冷”的分布格局逐渐固化。

（3）2008—2017年间，新疆县域旅游经济重心变动不大，方向性位移轨迹呈多个“V”字型重叠分布，表明新疆旅游发展持续存在南北方向的牵引力。10a间标准差椭圆的覆盖范围除2011、2012年明显增大外，其余年份呈稳步扩张趋势，总体呈“缩小一扩大”的展布特征，且明确牵引力主要来自东北一西南方向。

（4）旅游资源禀赋和政策支持是引导县域旅游经济时空格局演变主要的驱动力。交通设施的改善与人力资本水平有可能提升县域旅游经济发展，也可能抑制其发展水平并加剧各县域间的旅游经济空间异质性分布。经济发展水平次之，其对县域旅游经济时空格局演变影响较小，是今后需要大力加强的。

新疆旅游业地位不断提升，随着乡村旅游蓬勃兴起，对其县域旅游经济格局的探索，无论是从实践角度还是从理论层面都具有重要意义。本文通过多项指标对新疆对县域旅游经济时空关联特征、差异格局演化及形成机理的研究，梳理出县域旅游经济发展变化过程。未来发展应着重发展北部、东部、南部区域的比较优势。北部区域应重点提升旅游品质，继续拓展区域旅游发展空间，加快培育适应不同消费层级的旅游产品。东部区域应把握丝绸之路经济带的建设良机，加强区域间合作，挖掘旅游资源。南部区域应在“创新、开放、共享”的理念下，以政府引导为主，从政策、资金、专业知识等方面给予帮助，不断提升公共服务的能力，逐步实现新疆旅游业整体快速发展的局面。

# 参考文献(References)

[1]王圣云,单梦静,谭嘉玲.中部地区经济发展跟踪评价与“十三 五"加速崛起对策[J].地域研究与开发，2018，37（1)：20-25. [WANG Shengyun,SHAN Mengjing,TAN Jialing.Comprehensive follow-up evaluation of economic development and strategic countermeasures on rising of Central China in the $1 3 ^ { \mathrm { t h } }$ Five-Year Plan [J].Areal Research and Development,2018,37(1）:20 -25.]   
[2]宋慧林,马运来.基于空间分析的中国省域旅游经济差异[J]. 经济管理,2010,32（10）:114-118.[SONGHuilin,MAYunlai. Evaluation on regional disparity of tourism economy in China based onspatial analysis［J].Business Management Journal,2O10,32 (10):114-118.]   
[3］陈刚强.中国地市旅游经济差异的时空演变特征[J].地域研 究与开发,2012,31（4）:91-95.［CHENGangqiang.Temporalspatial evolution of regional tourism economic disparity in China [J].Areal Research and Development,2012,31(4）:91-95.]

[4]CHRISTALLER W.Some considerations of tourism location in Europe:The peripheral regions-under-developed countries-recreation areas[J」.Papers of the Regional Science Association,1964, (16) :95 -105.

[5]GUNN C A.Vacationscape:Designing tourist regions[M].NewYork :Van Nostrand Reinhold,1988.   
[6]CHRIS Ryan. Tourism and cultural proximity:Examples from New Zealand[J].Annals of Tourism Research,2002,29（4）:952- 971.   
[7]HILLS T,LUNDGREN J. The impacts of tourism in the Caribean: A methodological study[J].Annals of Tourism Research,1997,4 (5) :248 -267.   
[8]BUTLER R W.The concept of a tourist area cycle of evolution:Inplications for management of resources[J].Canadian Geograoher, 1980,(11) :5 -12.   
[9］彭宝玉,谢桂珍,魏雪燕,等.中国区域经济、金融发展差异分 析[J].地域研究与开发,2016,35（4）：1-5,11.［PENG Baoyu,XIE Guizhen,WEI Xueyan,et al.Regional disparity comparisons between economic and financial development in China [J].Areal Research and Development,2016,35(4）:1-5,11.]   
[10］彭睿娟.欠发达地区旅游经济差异的空间分析——以甘肃省 为例[J].干旱区地理,2017,40（3）:664-670.[PENG Ruijuan.Spatial analysis of tourism economy disparity of less developed areas in Northwest China[J].Arid Land Geography,2017,40 (3) :664 -670.]   
[11］周礼,蒋金亮.长三角城市旅游竞争力综合评价及其空间分异 [J].经济地理,2015,35(1）:173-179.[ZHOU Li,JIANG Jinliang.Comprehensive evaluation of urban tourism competitiveness in the Yangtze River Delta and its spatial patterns analysis[J].Economic Geography,2015,35（1）:173-179.]   
[12］苏建军,孙根年.中国旅游投资与旅游经济发展的时空演变与 差异分析[J].干旱区资源与环境,2017,31（1)：185－191. [SU Jianjun,SUN Gennian.Space evolution and difference of tourism investment and tourism economic development in China [J]. Journal of Arid Land Resources and Environment,2017,31 (1) :185 -191.]   
[13］白洋，瓦哈甫·哈力克,邓峰,等.交通基础设施对区域旅游经 济增长的空间效应——基于丝绸之路经济带 2001—2014 年 省际面板数据的分析[J].陕西师范大学学报（自然科学版）, 2017,45（6）:108-114.[BAI Yang,HALIK Wahap,DENG Feng,et al.Spatial effect of traffic infrastructure on regional tourism economic growth: Based on provincial panel data during 2001— 2014 in the Silk Road Economic Belt[J]. Journal of Shaanxi Normal University（Natural Science Edition）,2017,45（6）:108- 114.]   
[14］孙盼盼,戴学锋.中国区域旅游经济差异的空间统计分析[J]. 旅游科学,2014,28（2）:35-48.[SUN Panpan,DAI Xuefeng. An analysis on the spatial data of China's regional tourism econom ic disparity[J].Tourism Science,2014,28(2）:35-48.]   
[15］胡文海.孙建平.余菲菲.安徽省区域旅游经济发展的时空格

局演变[J].地理研究,2015,34（9）：1795-1806.［HUWen-hai,SUN Jianping,YU Feifei. Temporal-spatial evolution patterns

of regional tourism economic development in Anhui Province[J]. Geographical Research,2015,34（9）:1795 -1806.]   
[16］唐晓云.生产要素视角的中国旅游经济发展区域差异研究 [J].经济地理,2010,30（10）:1741-1745.[TANG Xiaoyun. Study on regional disparity of tourism development in China:The perspectiveof factors of production[J]. Economic Geography, 2010,30(10) :1741 -1745.]   
[17］钟章奇,李山,王铮,等.中国旅游业空间分异的 ABS 分析[J]. 地理研究,2014,33（8）:1427-1441.[ZH0NG Zhangqi,LI Shan,WANG Zheng,et al.Agent-based simulation of the spatial diferentiation of the tourism industry in China[J].Geographical Research,2014,33（8):1427-1441.]   
[18］张子昂,黄震方,曹芳东,等.浙江省县域入境旅游时空跃迁特 征及驱动机制［J].地理研究,2016,35（6)：1177－1192. [ZHANG Zi'ang,HUANG Zhenfang,CAO Fangdong,et al. The space-time transition characteristics and its driving mechanism of county-scale inbound tourism in Zhejiang Province[J]. Geographical Research,2016,35(6）:1177 -1192.   
[19］徐冬,黄震方,胡小海,等.浙江省县域旅游效率空间格局演变 及其影响因素[J].经济地理,2018,38（5）：197－207.［XU Dong,HUANG Zhenfang,HU Xiaohai,et al.The spatial pattern evolution and its influencing factors of county-scale tourism efficiency in Zhejiang Province[J]. Economic Geography,2018,38（5）: 197 - 207.]   
[20］汪雪,葛幼松.山西省县域经济空间格局及驱动机制分析[J]. 地域研究与开发,2018,37（1）:31-35,40.[WANG Xue,GE Yousong.Spatial patern evolution and driving mechanism analysis of county economy in Shanxi Province[J].Areal Research and Development,2018,37(1） :31-35,40.]   
[21］郭鲁芳.县域旅游经济制度变迁的实证分析——以杭州地区 二县市(淳安县、临安市)为例[J].旅游学刊,2004，(2）：22- 25.[GUO Lufang.A demonstrative analysis of institutional changes of county tourism economy:A case of two counties （Chun'an and Lin'an）in Hangzhou Area[J].Tourism Tribune,2004,(2）:22- 25.]   
[22］蒋若凡,李菲雅.汶川县域旅游经济发展模式探索[J].商业研 究,2014,（10）:158-165.[JIANG Ruofan,LI Feiya.Exploration on the development mode of tourism economy in Wenchuan County [J]. Commercial Research,2014,（10）:158-165.]   
[23］王辉,张萌,石莹,等.中国海岛县的旅游经济集中度与差异化 [J].地理研究,2013,32（4）:776-784.[WANG Hui,ZHANG Meng,SHI Ying,etal. Concentration and differentiation of tourism economy inisland counties，China[J].Geographical Research, 2013,32(4) :776-784. ]   
[24］陈涛,徐瑶.西部县域旅游发展模式研究—以仪陇县“十二 五"旅游发展规划为例[J].软科学,2013,27（8）：141－144. [ CHEN Tao,XU Yao.Research on tourism development planing pattern of western county scale:A case of Yilong“Twelve-Five” tourism development planning[J]. Soft Science,2013,27（8）: 141 -144. ]   
[25］陈建设,朱翔.县域旅游空间布局模型构建研究[J].经济地 理,2012,32(12）:163-168.[CHEN Jianshe,ZHU Xiang.Study on model construction of county tourism spatial layout[J].Economic Geography,2012,32（12）:163-168.]   
[26］李瑞,吴殿廷,郭谦,等.20 世纪90 年代中期以来中国县域旅 游研究进展与展望[J].地理与地理信息科学,2012,28（1)： 94 -99.[LI Rui,WU Dianting,GUO Qian,et al. Progress and prospect of the research on county tourism in China over the past fifteen years[J]. Geography and Geo-Information Science,2012,28 (1):94 -99.]   
[27］张建伟,窦攀烽,张永凯,等.江苏省县域创新产出的空间计量 经济分析[J].干旱区地理,2017,40（1）：22-229.［ZHANG Jianwei,DOU Panfeng,ZHANG Yongkai,et al.Spatial econometric analysis of innovation output of Jiangsu Province in terms of county scale[J].Arid Land Geography,2017,40(1) :222 -229.]   
[28］孟德友,陆玉麒.基于县域单元的江苏省农民收入区域格局时 空演变[J].经济地理,2012,32（11）:105-112.[MENG Deyou,LU Yuqi.The spatial-temporal evolution of spatial pattern of rural residents'net income at county level in Jiangsu[J].Economic Geography,2012,32（11）:105-112.]   
[29］陈翊,冯云廷,俞杨安.浙江省县域经济格局的空间演变分析 [J].地域研究与开发,2017,36(3）：16-21.［CHENYi,FENG Yunting,YU Yang'an.Spatial evolution analysis of county-level economy in Zhejiang Province[J].Areal Research and Development,2017,36(3):16-21.]   
[30］涂建军,刘莉,张跃,等.1996—2015 年我国经济重心的时空演 变轨迹-基于291个地级市数据[J].经济地理,2018,38（2）： 18 -26.[TU Jianjun,LIU Li,ZHANG Yue,et al. Temporal and spatial evolution of China's economic center of gravity in 1996— 2015:Based on the 291 prefecture-level data[J].Economic Geography,2018,38(2):18-26.]   
[31］李如友,黄常州.江苏省旅游经济重心演进格局及其驱动机制 [J].地域研究与开发,2015,34（1）:93-99,116.[LIRuyou, HUANG Changzhou.Evolution pattern of the tourism economic gravity center and its driving forces of Jiangsu Province[J].Areal Research and Development,2015,34（1) :93-99,116.]   
[32］王慧娟,兰宗敏,金浩,等.基于夜间灯光数据的长江中游城市 群城镇体系空间演变研究[J].经济问题探索,2017,（3）： 107-114.[WANG Huijuan,LAN Zongmin,JINHao,et al. Spatial evolution of urban system of urban cluster in middle reaches of Yangtze River based on night lighting data[J].Inquiry Into Eco

nomic Issues,2017,(3):107-114.][33］刘兆德,刘强，刘振明，等.中国省域城-镇化综合水平的空间特征与影响因素[J].城市发展研究，2017，24（3）：95－101.[LIU Zhaode,LIU Qiang,LIU Zhenming,etal. Spatial characteris-tics and factors affecting of comprehensive level of urbanization inthe provinces of China[J].Urban Development Studies,2O17,24

(3):95-101.]

[34］卢丽文，张毅,李永盛.中国人口城镇化影响因素研究－基于31个省域的空间面板数据［J].地域研究与开发，2014，33(3）:54-59.[LU Liwen,ZHANGYi,LI Yongsheng.The factorsinfluence on China population urbanization:Based on 31 provincialspatial panel data[J].Areal Research and Development,2014,33(3):54-59.]

[35]KIM S,TIMOTHY D,HAN H. Tourism and political ideologies:A case of tourism in North Korea[J].Tourism Management,2006,28 (4):1031-1043.

[36］KRUGMAN P.The new economic geography,now middle-aged [J].Regional Studies,2011,45(1):1-7.

[37］杨振，雷军,英成龙，等.新疆县域城镇化的综合测度及空间分异格局分析[J].干旱区地理,2017，40（1）：230-237.［YANGZhen，LEI Jun,YING Chenglong,et al.Comprehensive measure-ment and spatial differentiation pattern analysis of the county ur-banization in Xinjiang[J].Arid Land Geography,2017,40（1）：230 -237.]

[38］杨云.论人力资本积累视野下西部民族地区经济增长方式的转变[J].经济问题探索,2006,（12）：114-119.[YANGYun.Transformation of economic growth mode in western minority areasfrom the perspective of human capital accumulation[J].Inquiry in-to Economic Issues,2006,（12）:114-119.]

[39］孙庆刚，秦放鸣.中国西部少数民族地区经济社会全面发展的影响因素—综述与评价［J].经济问题探索，2010，（4）：188 -190.[SUN Qinggang,QIN Fangming.Factors influencing theoverall economic and social development of ethnic minority areas inWestern China:Summary and evaluation[J].Inquiry into Econom-ic Issues,2010,(4) :188-190.]

[40］顾华详.丝绸之路经济带核心区经济协调发展研究[J].新疆师范大学学报（哲学社会科学版），2016，37（5）：29-40.［GUHuaxiang.Research in economic coordinated development in Silk-RoadEconomic Belt in Core Area[J].Journal of Xinjiang NormalUniversity(Edition of Philosophy and Social Sciences）,2016,37(5):29-40.]

# Spatial and temporal changes and driving mechanism of county-scale tourism in frontier tourism destinations

ZHUYiting²，XIONG Hei-gang²，BAIYang³，YANGLi³，CAO Kai-jun³，TANGJin-went (1College of Resource and Environmental Science,Xinjiang University,Urumqi 83o046,Xinjiang,China;   
2College of Applied Arts and Science,Beijing Union University,Beijing 1Ooo83,Xinjiang,China;   
3College of Tourism,Xinjiang University,Urumqi 830049,Xinjiang,China;   
4School of Economics and Commerce,South China Universityof Technology,Guangzhou 5106,Guangdong,China)

Abstract：Asa western frontier region,Xinjiang has gradualy become a popular destination for tourism in the northwest of China due to its rich natural and cultural tourism resources generated by itsspecial geographical locationand social environment.To grasp the spatial development law of tourism economy isconducive to the formulationof regional tourism economic policies and the sustainable development of regional tourism economy in Xinjiang. The change of spatial pattern of tourism economy is a complicated process.In order to get more accurate and comprehensive analysis of the change processand reasons,taking 74 county units in Xinjiang as the research object and selecting multiple indicators,this paper uses the tools including ESDA,ArcGIS and GeoDa,and the dynamic panel data model to analyze the regional diferences anddriving mechanism of spatial pattrn evolution of tourism economy atthe county levelin Xinjiang from 2O08 to 2017.Theresults show that theagglomerationof thecounty scale tourism economy displayed the tendencyof“down-up-down-up”because the level of regional tourism development has some correlation with the development of tourism in its neighboring areas.It presents a significant graded change characteristics from the north tothe south with anobvious diference from county tocounty.Theenhancement of the fallout of the tourism in the northern regions promoted the interaction between those counties and their neighboring countiesand thus formed a spatial distribution pattern of“multi-coreand multi-strip”,pushing the newlyadded hot spots southward although this could not change the long-term distribution paern of“the north being the tourist honeypots whilethe south being keptin the doghouse”in Xinjiang.Affected bythe traction from northeast to southwest, thetrajectory ofthe gravity of the county-scale tourism economy was overlapped with several“V” shapes,which also makes the coverage of the ellpse of the standard deviation be increased graduall in this direction.Byregression analysis,there were significantdiferences in intensityof the influencing factors from county tocounty.The characteristics of the tourism resources and policysupport are the main driving factors.The improvement of traffc condition and human capital level can not necessarily promote the development of county-scale tourism economy in each county.The level of economic development has no obvious influence onthe spatial and temporal evolution of tourism economy in the county region.

Key words:The frontier；county-scale；tourism economic；temporal and spatial change；driving mechanism