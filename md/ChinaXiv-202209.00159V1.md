# 生态系统服务权衡强度与供需匹配度的关联性分析以山西省为例

冯强¹，赵文武²，段宝玲¹(1.山西财经大学资源环境学院,山西 太原030006；2.北京师范大学地理科学学部地表过程与资源生态国家重点实验室，北京100875)

摘要：以山西省各区县为研究单元,将供给服务相对占优定义为1型权衡,将支持服务相对占优定义为2型权衡。通过冗余分析、分段线性回归等方法揭示权衡与供需的影响因素以及两者之间的关联特征。结果表明：(1)1型权衡高值区与供需比低值区主要位于省内盆地，2型权衡与供需比高值区主要位于省内山地。(2)1型权衡主要受耕地、林草地与气温等因素影响;2型权衡主要受耕地、林地、NDVI与土壤有机质等因素影响,但作用方向与1型权衡相反。（3）林草地与坡度对1型供需比呈显著正效应,耕地与建设用地对其呈显著负效应;环境因子对2型供需比的影响较小。（4）各影响因素对1型权衡与供需比的作用方向相反，是二者负向关联的内在原因。供需矛盾较小的情况下，供需比对权衡强度的响应较强烈，随着供需矛盾加深，这种响应反而变弱。该关联特征指示了生态上的困境：人类需求增加-开发强度增加-1型权衡增强-供需矛盾加剧。2型权衡与供需比存在较弱的正向关联,指示了生态盈余的局面。本研究发现生态系统服务权衡与供需存在关联，进而揭示了两者的关联特征及其形成机制，可为国土空间生态修复与管理提供依据。

关键词：生态系统服务；供需关系；权衡；驱动因素；黄土高原

生态系统服务是指人类从生态系统中直接或间接获得的所有收益[1]。生态系统服务权衡是指一种生态系统服务供给水平的增强以其他生态系统服务供给水平的降低为代价[2-4]。权衡分析提供了一个综合且辩证的视角来认识生态系统服务之间关系，受到地理学、生态学、社会学等多学科研究者的关注。因此，权衡分析已经成为生态系统服务研究的重要方向并取得了一系列进展[5-8]。权衡研究涵盖了小流域、流域、区域、国家、全球等空间尺度，涉及到农业生产、植被恢复、城市规划与城市群建设等诸多领域，而且权衡研究已经从本地分析拓展到了远程耦合[9-10]。可见,生态系统服务权衡理论在国土空间治理中发挥着越来越重要的作用，

生态系统服务权衡研究的核心问题是权衡的形成机制与驱动因素。目前，权衡的驱动因素可以归纳为土地利用和气候变化两大类，其中土地利用在短时序内更为普遍[8]。围绕这两大类驱动因素，学者们利用相关分析、回归分析、冗余分析、地理探测器、随机森林分析、结构方程模型、贝叶斯网络、数据包络分析等方法，确定了权衡对不同驱动因素的响应方向、程度、快慢和阈值[11-18]。尽管如此,以往权衡强度研究往往忽视两项服务的变化方向与相对优势，不利于权衡驱动机制的揭示。因此，有必要依据两项服务的消长方向区分权衡类型，并在此基础上揭示其驱动机制。此外，已有权衡研究从生态系统服务供给权衡、需求权衡、服务流权衡、供给与需求权衡等角度分别展开[13.19-20],或者是基于人类需求估算生态系统服务实际供给，探讨实际供给之间的权衡[2],但对权衡强度与供需关系的整合分析尚不充分。

生态系统服务的持续供给是自然与社会赖以维持的基础，人类利用生态系统服务来满足需求并提高自身福祉。对供给与需求关系的研究有助于阐释生态系统服务产生与使用的空间差异，并从空间上刻画生态系统服务从自然生态系统流向人类社会系统的动态过程。因此供需关系研究成为近年来生态系统服务研究的前沿和热点[22-25]。生态系统服务供需研究亟待解决的关键问题是如何实现供需匹配，权衡特征及其驱动机制为解决该问题提供了可能途径，这已经引起相关学者的关注。例如，Li等[26]估算了潮白河城市带5种生态系统服务的供给量，通过权衡分析确定该区域关键生态系统服务是产水量，然后对其进行了供需关系研究，但该研究中权衡分析仅是供需研究的前期基础工作；王壮壮等提出了将供需匹配特征、供需动态变化趋势以及权衡/协同关系进行综合考虑的生态系统服务风险评价框架，由于权衡/协同关系会对生态系统服务供需风险产生影响，因此将定性识别的权衡/协同关系作为划分供需风险的条件；Wang等[28]提出了一个基于权衡/协同特征的生态系统服务供需匹配框架并进行了案例研究，该框架的核心思想是将权衡/协同分析作为解决供需不匹配的途径，推动了供需关系与权衡强度的整合研究与应用，该框架通过权衡/协同分析提出了3类供需调控方案：“双赢"途径、“小损失-大收益"途径、“替代"途径。可见，已有研究只是将权衡作为供需关系研究的前期准备、约束条件或调控途径，尚未定量阐明生态系统服务供需与权衡的关联特征。

生态系统服务供需与权衡存在内在关联关系。一方面，由权衡的定义可知，一种生态系统服务的增强以降低其他生态系统服务为代价，降低的服务则很有可能因供给量不足而无法满足需求，即引发供需矛盾，说明权衡特征会影响供需关系。另一方面，供需关系也会影响权衡，例如木材供给与需求出现矛盾时，人们通过森林采伐提高木材供给量，但降低了生态系统固碳能力，即出现了木材供给与固碳服务的权衡。以上分析说明供需与权衡的关联在逻辑上成立，并且这种关联既可以表现为两者随时间的同步、滞后或反向的变化，也可以表现为空间上权衡与供需的对应规律(不同位置权衡与供需的关联特征）。因此，厘清供需与权衡关联机制，有助于深化生态系统服务理论，为缓解供需矛盾与服务冲突提供解决方案[29]

黄土高原地区生态系统服务权衡与供需矛盾突出，新中国成立后为解决粮食供给问题而大量开垦坡耕地导致土壤保持服务下降，这是粮食供给服务的供需矛盾所引发权衡的实例。为提高土壤保持服务，1999年国家实施了退耕还林(草)工程，使得生态系统调节与支持服务(水源涵养、土壤保持与碳固定等)增强,但部分供给服务(产水量)下降[1-12],这是土壤保持服务供需矛盾引发权衡的又一实例。如果此类权衡进一步增强，产水量持续降低，水资源供需矛盾将进一步加剧。因此，黄土高原地区是生态系统服务供需与权衡关联性研究的合适场所。山西省全境位于黄土高原范围内,约占黄土高原总面积的四分之一，因此，本研究测算了2018年山西省生态系统服务供给与需求，定义了2种权衡类型，供给服务相对增强而支持服务相对降低的情况为1型权衡，反之为2型权衡。试图解决如下问题：（1）生态系统服务权衡强度与供需比的驱动机制是什么？(2）生态系统权衡强度与供需比的关联特征如何，其关联的内在原因是什么？

# 数据与方法

# 1.1 研究区概况

山西省地处我国第二阶梯，东西两侧由太行山和吕梁山与外界分隔，中部汾河谷地发育，形成“两山夹一川"的地形。山西省山地与丘陵占全省总面积的 $8 0 . 1 \%$ ,平川与河谷占比 $1 9 . 9 \%$ 。山西省属大陆性季风气候，年均气温 $4 . 2 { \sim } 1 4 . 2 \mathrm { ~ } \mathrm { ^ { \circ } C }$ ,年均降水量仅$4 6 8 . 3 \ \mathrm { m m }$ $6 0 \%$ 集中于夏季。植被从南到北依次为：暖温带落叶阔叶林、暖温带针叶林、落叶阔叶林、温带、暖温带干草原。山西省 $5 3 \%$ 的地面被原生黄土或次生黄土覆盖，是我国水土流失最严重的省份之一；山西省矿产资源丰富，资源的开采带来一系列生态环境问题。考虑本研究的空间尺度以及城区的相似性，若地级市存在多个城区则将其合并，最终将山西省分为108个区县，作为本研究的空间分析单元(图1)。

# 1.2生态系统服务价值评估

基于Costanza等的生态系统服务价值理论，谢高地等[30-31]提出了用于生态系统服价值评估的当量因子法，在国内得到了广泛应用。首先，计算一个当量的生态系统服务价值（ $( E S V )$ ，公式如下：

$$
E S V { = } \frac { 1 } { 7 } \times \sum _ { i = 1 } ^ { n } \frac { m _ { i } \times v _ { i } \times y _ { i } } { M }
$$

式中： $m _ { i }$ 表示第 $i$ 种粮食作物播种面积 $\left( \mathrm { h m } ^ { 2 } \right)$ ; $v _ { i }$ 表示

110E 111E 112°E 113E 114E 115E   
N4 = 一 T 1 1 关镇县 阳高县 N000 大同城区 N   
No04 玉县县灵县 浑源县 偏关县 平鲁区山阴县应县 灵丘县 朔城区 繁峙县 N60 河曲县神池县 代县   
N6 五寨县 保德县 宁武县 原平市 五台县 苛岚县 定襄县 兴县 岚县 静乐县忻府区 孟县 N080 阳曲县   
N88 楼烦县 太原 临县 山县古交市 离石区文水县清徐县 交城县 输次区 昔阳县 柳林县 阳县广汾阳市 太谷 和顺县 NoL 孝义市平遥县榆社县 左权县   
NL 石楼县交口县市 武乡县 灵石县沁源县沁县城县 永和县阳县汾西县霍州市 襄垣县 大宁县蒲县洪洞县古县留城 州区平顺县 N90   
N99 吉县尧都区 乡宁县襄汾县浮山县 安泽县长子县 区壶关县 高平市 曲沃县翼城县沁水县 陵川县 河市山县新 晋城城区 夏县坦曲县 220   
250 永济市 平陆县 芮城县 1 0 50km N0 110E 111E 112E 113E 114E

该种粮食作物的价格（元· $\mathbf { k g } ^ { - 1 }$ ）； $y _ { i }$ 表示粮食单产$\left( \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 } \right)$ ; $M$ 表示粮食作物总面积 $\left( \mathrm { h m } ^ { 2 } \right)$ ）。利用2018年山西省主要粮食作物小麦、玉米和谷子计算一个当量生态系统服务价值 $( E S V )$ 为1412.6元· $\mathrm { h m } ^ { - 2 }$ 。其次，利用山西省净初级生产力和降水量与全国平均数据的比值计算调节因子（分别为0.562和0.782），利用调节因子对谢高地等[31]建立的当量因子表进行修正。最后，基于山西省土地利用数据，利用Arc-GIS栅格计算器的赋值功能将生态系统服务价值空间化。

# 1.3生态系统服务权衡强度计算

已有研究发现，供给服务与调节或支持服务之间存在权衡关系。本研究初步分析发现调节服务与支持服务之间存在显著正相关，因此，本文仅研究供给服务与支持服务之间的权衡关系。权衡强度通过均方根偏差(RMSD)法[32]计算，公式如下：

$$
\mathrm { R M S D } = \sqrt { \frac { 1 } { n - 1 } \sum _ { i = 1 } ^ { n } ( E S _ { i } - E S _ { m } ) ^ { 2 } }
$$

式中：RMSD为权衡强度； $E S _ { i }$ 为某项生态系统服务极差标准化值； $E S _ { m }$ 为某项生态系统服务的数学期望。均方根偏差法的实质是计算标准化后2项生态系统服务组成的坐标点距1：1线的距离。

均方根偏差法的优点是丰富了权衡内涵，不仅能够衡量2项服务之间的反向变化程度，还能衡量同向变化但步调不一致的情况，因此得到了广泛的应用[12.33-35]。但是以往研究往往不区分2项服务的具体消长方向，对权衡驱动机制的揭示不够充分。因此，本研究将权衡关系进一步细分为1型权衡与2型权衡，1型权衡是指供给服务增强的同时支持服务降低，2型权衡消长方向与1型权衡相反。依据上述坐标点在1:1线的下方和上方分别计算RMSD，用来表示1型权衡与2型权衡的强度值[36。

# 1.4生态系统服务供需比计算

很多学者将生态系统服务总价值作为生态系统服务供给量 $\left( E S S \right) ^ { [ 3 7 - 3 9 ] }$ ,用来反映生态系统提供服务的整体趋势。彭建等3将生态系统服务需求 $( E S D )$ （204号理解为被人类社会消耗或者希望获得的生态系统服务数量，并构建了 $E S D$ 核算公式。该公式能够反映区域 $E S D$ 的总体趋势，得到了广泛的应用[37-38.40-42]。公式如下：

$$
E S D = C o n L \times \lg ( R K M D ) \times \lg ( D J G D P )
$$

式中： $E S D$ 代表生态系统服务需求； $C o n L$ 代表建设用地比例 $( \% ) { ; R K M D }$ 代表人口密度（人 $\mathrm { k m } ^ { - 2 }$ ）； $D J G .$ （204号$D P$ 代表地均国内生产总值( $1 0 ^ { 4 }$ 元 $\cdot \mathrm { k m } ^ { - 2 }$ ）。

生态系统服务供需匹配度可以用供给量与需求量的比值衡量[40]。将生态系统服务供给量与需求量分别进行极差标准化，生态系统服务供需比为两者标准化后的比值，公式如下：

$$
G X B = \frac { E S S _ { s } } { E S D _ { s } }
$$

式中： $G X B$ 表示生态系统服务供需比； $E S S _ { s }$ 和 $E S D _ { s }$ 分别表示标准化之后的生态系统服务供给量与需求量。

为了与权衡类型相对应，本研究1型权衡区县 相应的供需比称为1型供需比，2型权衡区县相应的 供需比称为2型供需比。

# 1.5数据来源

2018年山西省土地利用( $1 \ \mathrm { k m } { \times } 1 \ \mathrm { k m } \$ 与归一化植被指数数据( $1 \ \mathrm { k m } { \times } 1 \ \mathrm { k m }$ 来自中国科学院资源环境科学与数据中心（https://www.resdc.cn/lds.aspx）;

降水与气温数据来自中国气象数据网(http://data.cma.cn);土壤有机质数据来自全国第二次土壤普查数据；DEM数据通过地理空间数据云平台下载获得(http://www.gscloud.cn/);主要粮食作物播种面积与产量、国内生产总值、人均收入、人口密度、社会消费品总额数据来自《山西统计年鉴》;粮食价格数据来自《中国农村统计年鉴》。

# 1.6数据分析

利用GeoDa软件双变量局部空间自相关模型揭示生态系统服务供给与需求的空间聚集特征。将环境因子分为自然因素(气温、降水、归一化植被指数、土壤有机质含量、坡度）、社会经济因素（人均GDP、人口密度、人均收入、社会消费品总额）土地利用(因土地利用既包括林草地等自然因素，也包括耕地与建设用地等社会经济因素，将其单列一类)3大类因素，以区县数据为样本，利用Canoco软件进行方差分解，揭示生态系统服务权衡与供需的主导因素。然后采用冗余分析(DCA排序轴Lengths of gradien $\cdot < 3$ )的简单效应阐明生态系统服务权衡与供需的具体影响因素。利用R软件 seg-mentedpackage进行分段线性回归，揭示生态系统服务权衡强度与供需比对自然与社会经济因素的响应阀值。利用Stata软件进行分位数回归，揭示权衡强度与供需比在不同强度下的关联特征。

# 2结果与分析

# 2.1生态系统服务权衡空间分异

由图2可知，山西省各区县生态系统服务总量差异较大，生态系统服务高值区主要位于太岳山、中条山、吕梁山等高植被覆盖区域，生态系统服务低值区主要位于运城盆地、临汾盆地、长治盆地的城区及农产品主产区。

由图2与图3可知，主要提供供给服务的区县数量(65个)明显多于提供支持服务的区县(43个），1型权衡强度 $( 0 . 1 5 6 ) { > } 2$ 型权衡强度(0.094)。1型权衡坐标点相对分散(图3中黑点），说明权衡强度的多样化，2型权衡坐标点靠近1:1线分布(图3中红点）,权衡强度差异不大。1型权衡强度处于前五位的是潞州区、临猗县、曲沃县、侯马市、万荣县，2型权衡强度位于前五位的是：沁源县、和顺县、五台县、交口县、左权县，权衡强度较低的区县为：晋城城区、岚县、平鲁区、太谷区、汾西县。可见，1型权衡高值区主要位于长治盆地、临汾盆地、运城盆地与大同盆地，2型权衡高值区位于太岳山与太行山区。

# 2.2生态系统服务供需匹配的空间分异

由图4可知，供需比高值区主要位于人口较少的山地，供需比低值区主要位于人口集聚的盆地。对生态系统服务供给与需求进行局部双变量空间自相关分析，Moran'sI指数为-0.022。88个区县表现为自相关不显著，4个区县表现为高-高聚集型(泽州县、壶关县、平顺县、长子县)，10个区县表现为低-低聚集型(大宁县、岚县、永和县等)，2个区县表现为低-高聚集型（上党区、清徐县），4个区县表现为高-低聚集型(左权县、方山县、兴县、岢岚县）。可见，多数区县生态系统服务供给与需求的空间聚集不显著，即便局部发生集聚现象，也以低-低聚集为主，即生态系统服务供给低，与之相对应的需求也低，主要位于晋西黄土丘陵区。

![](images/3a8b3af53c4d235389fbefd15fe09256da495031be1e64f96a48fca886c9e287.jpg)  
图2山西省生态系统服务价值(a)与权衡强度分布(b)  
Fig.2 Map of ecosystem service value (a) and trade-offs intensity (b) in Shanxi province

![](images/1e6a3c69757269bd5d1ba29f611cc4903e6de56bfc2f9cd6657ea0f2a22cda3a.jpg)  
图3生态系统服务标准值散点图与权衡强度(RMSD) Fig.3Scatter plot of ecosystem service standard values and trade-offs intensities (RMSD)

# 2.3生态系统服务权衡与供需关系的影响因素

2.3.1基于方差分解与冗余分析的主导因素分析影响因素对1型权衡的解释率之和达到 $9 1 . 7 \%$ ，其中土地利用的单独解释率最高( $4 9 . 9 \%$ )，土地利用与自然因素的共同解释率次之 $( 2 9 . 7 \% )$ )，三类因素的共同解释率再次 $( 1 0 . 2 \% )$ )，自然因素与社会经济因素的单独解释率很低，仅为 $0 . 5 \%$ 与 $1 . 0 \%$ （图5）。影响因素对2型权衡的影响与1型权衡相似，土地利用的独立影响最大，自然因素与社会经济因素的独立影响很小，两者主要通过与土地利用的交互作用对权衡产生影响。

影响因素对1型供需比的解释率之和为$3 4 . 5 \%$ ，其中，土地利用与社会经济因素的共同解释率最高（ $( 1 3 . 5 \% )$ )，土地利用的独立影响次之 $( 7 . 0 \% )$ ，土地利用与自然因素的交互作用再次 $( 5 . 0 \%$ )，自然因素与社会经济因素的独立影响很小（仅为 $0 . 2 \%$ 与$0 . 5 \%$ )，两者的交互作用稍高但仅为 $3 . 8 \%$ 。影响因素对2型供需比的解释率之和很低，仅为 $1 7 . 6 \%$ ，主要是土地利用的影响 $( 9 . 2 \% )$ 。

![](images/6aee714b9256fabfef7fb154f34900021c88dbdfc9c47ed1b5bf8ccf8bd8fd97.jpg)  
图4生态系统服务供需比(a)与空间相关性(b)  
Fig.4Ecosystem services supply-demand ratio (a) and spatial correlation (b)

![](images/099754530a604a910c504da20bbc07203f714cc17af306ae6089eb4e4e35ef74.jpg)  
图5权衡强度与供需比影响因素的方差分解

可见，土地利用是生态系统服务权衡强度与供需匹配程度的主导因素，土地利用对权衡的影响大于其对供需的影响。通过冗余分析进一步揭示具体影响因素，结果见图6和表1，1型权衡主要受耕地、草地、年均气温、林地与水域等因素的影响，这些因素的解释率均较高( $2 5 \%$ 以上)。其中,草地、林地、坡度与土壤有机质含量对权衡具有负效应，其他因素对权衡具有正效应。社会经济因素中仅人均收入与人口密度具有显著影响，但其解释率仅为$8 . 4 \%$ 和 $5 . 0 \%$ 。影响2型权衡的因素为耕地、林地、

![](images/52783a07cb4aad755e594bb0b3e87c5ae7eaa8e5bf8b9aa3c7ee388c8bccb51b.jpg)  
Fig.5Variation partitioning of influencing factors of trade-offs and supply-demand ratio   
Fig.6Redundancy analysis diagram of trade-offs and supply-demand ratio

注：Trade-off1:1型权衡;Trade-off2:2型权衡;GXB1:1型供需比;GXB2:2型供需比;GroL：耕地 $( \% )$ ;GraL：草地 $( \% )$ ;ForL：林地 $( \% )$ · $\mathrm { C o n L }$ ：建  
设用地 $( \% )$ · $\mathbb { W } \mathrm { a t L }$ ：水域 $( \% )$ ;WeiL：未利用地 $( \% )$ ： $\mathrm { T e m }$ ：气温 $( \operatorname { \mathcal { C } } )$ ；P：降水量 $\bf \Pi _ { \mathrm { m m } } )$ ;Slope:坡度();NDVI:归一化植被指数;SOM：土壤有机质含量 $( \% )$ ;RJGDP:人均国内生产总值( $1 0 ^ { 4 }$ 元)；RJSR：人均收入( $1 0 ^ { 4 }$ 元);RKMD：人口密度（人 $\cdot \mathrm { k m } ^ { - 2 }$ );XFZE：社会消费品总额( $1 0 ^ { 8 }$ 元）。图6权衡强度与供需比的冗余分析

表1影响因素对权衡强度与供需比影响的简单效应( $\mathbf { \dot { s i m E } }$ ）  
Tab.1 Simple effects of factors on trade-offs and supply-demand ratio   

<html><body><table><tr><td colspan="3">1型权衡</td><td colspan="3">2型权衡</td><td colspan="3">1型供需比</td><td colspan="3">2型供需比</td></tr><tr><td>因素</td><td>SimE</td><td>P</td><td>因素</td><td>SimE</td><td>P</td><td>因素</td><td>SimE</td><td>P</td><td>因素</td><td>SimE</td><td>P</td></tr><tr><td>CroL</td><td>49.4</td><td>0.002</td><td>CroL</td><td>82.2</td><td>0.002</td><td>RJSR</td><td>25.5</td><td>0.002</td><td>ConL</td><td>11.6</td><td>0.062</td></tr><tr><td>GraL</td><td>35.0</td><td>0.002</td><td>ForL</td><td>23.2</td><td>0.004</td><td>GraL</td><td>22.1</td><td>0.002</td><td>RKMD</td><td>7.1</td><td>0.038</td></tr><tr><td>Tem</td><td>32.0</td><td>0.002</td><td>NDVI</td><td>12.1</td><td>0.020</td><td>CroL</td><td>18.6</td><td>0.002</td><td>XFZE</td><td>5.3</td><td>0.036</td></tr><tr><td>ForL</td><td>27.2</td><td>0.002</td><td>SOM</td><td>9.3</td><td>0.050</td><td>ConL</td><td>18.4</td><td>0.006</td><td></td><td></td><td></td></tr><tr><td>WatL</td><td>25.9</td><td>0.002</td><td></td><td></td><td></td><td>Slope</td><td>15.4</td><td>0.010</td><td></td><td></td><td></td></tr><tr><td>Slope</td><td>18.0</td><td>0.002</td><td></td><td></td><td></td><td>RJGDP</td><td>11.3</td><td>0.010</td><td></td><td></td><td></td></tr><tr><td>ConL</td><td>12.1</td><td>0.008</td><td></td><td></td><td></td><td>ForL</td><td>9.4</td><td>0.012</td><td></td><td></td><td></td></tr><tr><td>RJSR</td><td>8.4</td><td>0.022</td><td></td><td></td><td></td><td>RKMD</td><td>8.1</td><td>0.038</td><td></td><td></td><td></td></tr><tr><td>SOM</td><td>7.9</td><td>0.020</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>P</td><td>6.6</td><td>0.042</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>RKMD</td><td>5.0</td><td>0.046</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

注：GroL：耕地 $( \% )$ ；GraL：草地 $( \% )$ ；ForL：林地 $( \% )$ ；ConL：建设用地 $( \% )$ ；WatL：水域 $( \% )$ ;WeiL：未利用地 $( \% )$ )；Tem：气温 $( \operatorname { \mathcal { C } } )$ ；P：降水量（ $( \mathbf { m m } )$ ;Slope:坡度 $( ^ { \circ } )$ ;NDVI:归一化植被指数;SOM:土壤有机质含量 $( \% )$ ;RJGDP:人均国内生产总值( $1 0 ^ { 4 }$ 元)；RJSR：人均收入（ $1 0 ^ { 4 }$ 元)；RK-MD：人口密度（人 $\cdot \mathrm { k m } ^ { - 2 }$ );XFZE：社会消费品总额（ $1 0 ^ { 8 }$ 元);灰色阴影部分表示负效应；无阴影表示正效应。

NDVI与土壤有机质含量，这些因素对2型权衡的作用方向与1型权衡相反，耕地对权衡具有负效应，而林地、NDVI与土壤有机质对权衡具有正效应。

对于1型供需比，人均收入、耕地、建设用地、人均GDP、人口密度具有负效应，这些因素会增加生态系统服务需求，从而导致生态系统服务供给的相对不足。草地、坡度与林地对1型供需比具有正效应，这些因素能够提高生态系统服务供给水平，进而满足人类需求。影响因素对2型供需比的影响相对较小，仅人口密度与消费品总额达到了显著水平，但解释率仅为 $7 . 1 \%$ 与 $5 . 3 \%$ ,说明还存在其他因素对2型供需比产生影响，需要进一步研究。

2.3.2 基于分段回归的影响因素阈值分析大部分环境因子对权衡的影响存在阈值，土壤有机质、坡度、林地与草地首先表现为明显抑制1型权衡，超过阈值(分别为 $1 . 2 \% , 2 . 2 ^ { \circ } , 2 3 . 1 \% , 2 7 . 6 \%$ 后表现为轻微促进或抑制权衡(图7)。年均气温能够加剧1型权衡，超过 $1 2 . 8 ~ \mathrm { \textdegree C }$ 后加剧作用更强。降水小于阈值

0.4 酒 0.4 程 0.3 0.3   
0.2 0.2 0.0 0.0   
0.0 0.0 6 8 10 12 14 400 500 600 1.0 1.2 1.4 1 2 3 4 5 年均气温/℃ 年均降水量 $/ \mathrm { m m }$ （204号 土壤有机质含量 $1 \%$ 坡度/()   
限 0.4 程 0.4 属 0.4 0.4   
0.2 0.2 0.2 0.2   
0.0 0.0 0.0 0.0 010 20 3040 10 30 50 0 1020 30 40 1.0 2.0 3.0 林地比例/% 草地比例/% 建设用地比例 $1 \%$ 人均收入/104元   
程 0.6 0.4 0.4 0.4   
0.3 0.2 0.2 0.2   
0.0 0.0 0.0 0.0 0 1000 2500 10 30 50 10 20 30 40 200 600 1000 人口密度/(人·km2) 林地比例 $1 \%$ （204 耕地比例/% 人口密度/(人·km2)

中 $\mathrm { 5 9 0 ~ m m } ,$ 时能够促进权衡，超过后开始抑制权衡，因为降雨量 $> 5 9 0 ~ \mathrm { m m }$ 的区域主要分布在高海拔山地，以自然植被为主。建设用地比例在 $8 . 2 \%$ 以下时强烈促进权衡，超过阈值后该作用变得十分微弱，原因是尽管建设用地比例增加，但其他土地利用类型(如林地)削弱了建设用地对权衡的正效应。人均收入低于阈值时，随着收入增加1型权衡增强，这是因为高收入意味着经济发达，资源开发利用程度高，供给服务相对强于支持服务。超过阈值后人均收入对权衡具有负效应，这主要体现在晋城与太原城区，2个城区建设用地比例高达 $4 3 . 5 \%$ 与 $3 2 . 9 \%$ ，供给服务与支持服务均很低，因此权衡较低。人口密度与人均收入类似，低于阈值时(1878人 $\mathrm { k m } ^ { - 2 }$ 促进权衡，超过后抑制权衡。大部分因素对2型权衡未表现出明显的阈值效应，只有林地、耕地与人口密度分段回归显著。林地对权衡具有促进作用，林地比例超过 $2 4 \%$ 后该作用减弱。耕地对权衡具有抑制作用，耕地比例超过 $3 2 \%$ 后该作用减弱。人口密度低于457人· $\mathrm { k m } ^ { - 2 }$ 时抑制权衡，超过后促进权衡，但是仅表现在洪洞县与阳泉城区，2个区县林地比例较低而建设用地比例相对较高，因此影响方向出现了转折。

影响因素对供需比的影响也存在阈值，除草地外，影响因素对供需比的影响具有相似的规律（图8)。小于阈值时，耕地、建设用地、人均收入、人口密度、消费品总额对1型或2型供需比具有明显的负效应，即这些因素能快速降低供需比（供需矛盾急速增加)。超过阈值后，这些因素的负效应变小（分段斜率很低)。草地对1型供需比具有正效应，超过阈值后正效应加剧。

# 2.4生态系统服务权衡强度与供需匹配度的关联特征

通过分位数回归研究生态系统服务权衡强度与供需比的关系，由表2可知，各分位数下1型权衡酒 40 书利 50 书 120 星书 5020 20 60 200 0 0 030 50 70 10 30 50 010203040 1.0 2.0 3.0耕地比例/% 草地比例/% 建设用地比例 $1 \%$ 人均收入/104元50 十 2书 350 书 书 60020 150 100 3000 00 00 1000 2500 0 5 10 1520 050 150 250 200 600 1000人口密度/(人·km-2) 建设用地比例 $1 \%$ （20 社会消费品总额 $^ { 1 0 ^ { 8 } }$ 元 人口密度/(人·km-2)

强度对供需比均表现为负效应，这种负效应随着分位数增加有增强的趋势，但只有 $5 0 \%$ ） $6 0 \%$ 、 $7 0 \%$ 分位数下显著。1型权衡表示供给服务相对占优而支持服务相对不足，此时生态系统服务总量无法满足需求，权衡强度越高，供需矛盾越大（供需比越小)。回归系数随分位数的变化指出了供需矛盾对权衡强度的响应情况：供需矛盾较小（供需比相对较大)的情况下，供需比对权衡的响应较为强烈，随着供需矛盾加深，这种响应反而变弱。原因可能是在供需矛盾达到一定水平后，本地的生态系统服务冲突已经不再重要，域外流入的生态系统服务开始起作用。因此，1型权衡与供需比的关系展现了生态上的困境：人类需求增加-开发强度增加-1型权衡增强-供需矛盾加剧。

Fig.8Piecewise linear regression between supply-demand ratio and influencing factor   
表2权衡强度与供需比的分位数回归   
Tab.2 Quantile regression between trade-offs intensities and supply-demand ratio   

<html><body><table><tr><td rowspan="2">分位数</td><td colspan="2">1型权衡</td><td colspan="2">2型权衡</td></tr><tr><td>回归系数</td><td>显著性P</td><td>回归系数</td><td>显著性P</td></tr><tr><td>10%</td><td>-2.3</td><td>0.367</td><td>12.9</td><td>0.841</td></tr><tr><td>20%</td><td>-5.4</td><td>0.115</td><td>105.6</td><td>0.138</td></tr><tr><td>30%</td><td>-9.7</td><td>0.087</td><td>131.5</td><td>0.098</td></tr><tr><td>40%</td><td>-12.7</td><td>0.119</td><td>158.1</td><td>0.058</td></tr><tr><td>50%</td><td>-21.3</td><td>0.045</td><td>232.8</td><td>0.000</td></tr><tr><td>60%</td><td>-30.4</td><td>0.025</td><td>213.9</td><td>0.003</td></tr><tr><td>70%</td><td>-41.0</td><td>0.013</td><td>186.1</td><td>0.176</td></tr><tr><td>80%</td><td>-56.2</td><td>0.108</td><td>-6.7</td><td>0.984</td></tr><tr><td>90%</td><td>-82.8</td><td>0.215</td><td>-450.9</td><td>0.642</td></tr></table></body></html>

2型权衡对供需比主要表现为正效应( $1 0 \% .$ ）$70 \%$ 分位数)，并且正效应随分位数增加而增加，但仅 $5 0 \%$ 与 $6 0 \%$ 分位数下显著。在高供需比情况下中 $80 \% { \sim } 9 0 \%$ 分位数)表现为负效应。2型权衡表示支持服务相对占优而供给服务相对不足，权衡强度越大，生态系统服务总量越大，越有利于缓解生态系统服务供需矛盾。2型权衡与供需比的关系与上述1型权衡相反，展现了生态上盈余的局面。

# 3讨论

# 3.1生态系统服务权衡强度与供需匹配度的内在 关联

生态系统服务权衡是指一项生态系统服务供给水平的增加以另一项服务的降低为代价，可能引起该服务供需比增加，而导致另一项服务供需比降低，甚至出现供需矛盾。因此，生态系统服务权衡与供需的关联在逻辑上成立。本研究生态系统服务权衡与供需关系受土地利用、地形、气候、土壤、以及社会经济因子的影响，其中权衡的主导因素是土地利用与自然环境条件，供需关系的主导因素是土地利用与社会经济条件。主导因素存在部分重叠，这是权衡与供需关联的内在因素。本研究发现耕地、建设用地、人均收入与人口密度对1型权衡具有显著正效应但对供需比存在显著负效应，草地、林地与坡度对1型权衡具有显著负效应但对供需比具有存在正效应。影响因素对权衡与供需比具有相反作用，是两者负向关联的内在原因。2型权衡与供需比存在较弱的正向关联,尽管NDVI、降水与林地对两者具有正效应，耕地、建设用地与人口密度对两者具有负效应，但是并未出现共同且显著的影响因素，这也是两者弱关联的原因。从拐点分析来看，仅草地比例对1型权衡与供需比的影响阈值接近，为 $3 0 \%$ 左右。其他因素对权衡与供需比的影响阈值存在较大差异，说明权衡与供需比内在关联的影响因素相对复杂,即使影响方向整体出现一致或相反的规律，但其影响的具体过程也存在差异性。鉴于目前国内外尚缺乏权衡强度与供需匹配度之间定量关系的研究，无法进行类比分析，厘清该具体过程差异性的形成机制尚需要进一步研究。

# 3.2研究不足与展望

本研究通过当量因子法[30-31]计算生态系统服务供给量，利用彭建等3构建的公式计算生态系统服务需求量(将需求理解为被人类社会消耗或者希望获得的生态系统服务数量）。已有研究表明，该方法能够反映生态系统服务供给与需求关系的整体趋势[37-42],本研究在此基础上开展权衡与供需的关联性分析，发现了二者关联的整体特征与内在原因。本研究是权衡与供需关系的探索性分析，采用的方法与数据相对宏观，旨在揭示权衡与供需关联的宏观趋势，期望更多学者开展相关研究。未来研究中可利用监测或模型手段量化具体服务的权衡强度与供需匹配度，进一步精细刻画二者关联特征并厘清其影响机制。

# 4结论

生态系统服务高值区主要位于太岳山、中条山、吕梁山等高植被覆盖区域，低值区主要位于运城盆地、临汾盆地与长治盆地的城区及农产品主产区。1型权衡强度大于2型权衡，1型权衡高值区主要位于各大盆地，2型权衡高值区位于太岳山与太行山区。供需比的高值区主要位于人口较少的山地，低值区主要位于人口集聚的盆地。

1型权衡主要受耕地、草地、年均气温、林地与水域等因素的影响(解释率在 $2 5 \%$ 以上)，其中草地与林地对权衡具有负效应，其他因素具有正效应。影响2型权衡的因素仅为耕地、林地、NDVI与土壤有机质，这些因素对2型权衡的作用方向与1型权衡相反。人均收入、耕地、建设用地等因素对1型供需比具有负效应，而草地、坡度与林地具有正效应。因子对2型供需比的影响相对较小。大部分因子对1型权衡的影响存在阈值，土壤有机质、坡度、林地与草地比例首先表现为抑制1型权衡，超过阈值后则对权衡影响很小。林地和耕地对2型权衡的影响存在阈值，林地比例超过 $2 4 \%$ ,其对权衡的促进作用减弱。耕地比例超过 $3 2 \%$ ,其对权衡的抑制作用减弱。

影响因素对1型权衡与供需比的作用方向相反，是两者负向关联的内在原因。供需矛盾较小的情况下，供需比对权衡的响应较为强烈，随着供需矛盾加深，这种响应反而变弱，该关联特征指示了生态上的困境。2型权衡与供需比存在较弱的正向关联，指示了生态盈余的局面。本研究从宏观上阐释了生态系统服务权衡与供需的影响因素及二者的关联特征，能够为国土空间治理提供决策参考。

# 参考文献(References):

[1]Costanza R,D’Arge R,Groot R D,et al. The value of the world's ecosystem services and natural capital[J]. Nature,1997,387 (6630): 253-260.   
[2]MA(Millennium Ecosystem Assessment). Ecosystems and Human Well-being: Synthesis[M]. Washington DC: Island Press,2005: 6- 11.   
[3]Bennett E M,Peterson G D,Gordon L J. Understanding relationshipsamong multiple ecosystem services[J]. Ecology Letters, 2009,12(12): 1394.   
[4]彭建,胡晓旭,赵明月,等.生态系统服务权衡研究进展：从认知 到决策[J].地理学报,2017,72(6):960-973.[Peng Jian,Hu Xiaoxu,Zhao Mingyue,et al.Research progress on ecosystem service trade-offs:From cognition to decision-making[J].Acta Geographica Sinica,2017,72(6): 960-973.]   
[5]傅伯杰,于丹丹.生态系统服务权衡与集成方法[J].资源科学, 2016,38(1):1-9.[Fu Bojie,Yu Dandan. Trade-off analyses and synthetic integrated method of multiple ecosystem services[J]. Resources Science,2016,38(1): 1-9.]   
[6]戴尔阜,王晓莉,朱建佳,等.生态系统服务权衡:方法、模型与 研究框架[J].地理研究,2016,35(6):1005-1016.[Dai Erfu, Wang Xiaoli, Zhu Jianjia,et al. Methods,tools and research framework of ecosystem service trade-offs[J]. Geographical Research, 2016,35(6): 1005-1016.]   
[7]赵文武,刘月,冯强,等.人地系统耦合框架下的生态系统服务 [J].地理科学进展,2018,37(1):139-151.[Zhao Wenwu,Liu Yue,Feng Qiang,et al. Ecosystem services for coupled human and environment systems[J]. Progress in Geography,2018,37(1): 139-151.]   
[8]Zheng H, Wang L J, Wu T. Coordinating ecosystem service tradeoffs to achieve win-win outcomes: A review of the approaches[J]. Journal of Environmental Sciences,2019,82:103-112.   
[9]Jiang C J,Guo HW,Wei YP,et al. Ecological restoration is not suffcient for reconciling the trade-off between soil retention and water yield: A contrasting study from catchment governance perspective[J].Science of the Total Environment,2021,754: 142139.   
[10]Zhao W W,Liu Y,Daryanto S,et al. Metacoupling supply and demand for soil conservation service[J]. Current Opinion in Environmental Sustainability,2018,33:136-141.   
[11]Feng Q, Zhao W W,Fu B J,et al.Ecosystem service trade-offs and their influencing factors:A case study in the Loess Plateau of China[J]. Science of the Total Environment,2017,607-608:1250- 1263.   
[12]Feng Q, Zhao W W,Hu XP,et al. Trading-off ecosystem services for better ecological restoration:A case study in the Loess Plateau of China[J]. Journal of Cleaner Production,2020,257: 120469.   
[13]Kathleen C S,Richard SQ,Nils B,et al. Quantifying stakeholder understanding of an ecosystem service trade-of[J]. Science of the Total Environment, 2019,651: 2524-2534.   
[14]Forio M,Villa-Cox G,Echelpoel W V,et al. Bayesian Belief Network models as trade-off tools of ecosystem services in the Guayas River Basin in Ecuador[J]. Ecosystem Services, 2020,44: 101124.   
[15]Sun X Y, Shan RF, Liu F. Spatio-temporal quantification of patterns,trade-offs and synergies among multiple hydrological ecosystem services in different topographic basins[J]. Journal of Cleaner Production,2020,268:122338.   
[16]Su B Q,Su Z X, Shangguan Z P. Trade-off analyses of plant biomass and soil moisture relations on the Loess Plateau[J]. Catena, 2021, 197: 104946.   
[17]Wang C,Wang S,Fu B J,et al.Precipitation gradient determines the tradeoff between soil moisture and soil organic carbon,total nitrogen,and species richness in the Loess Plateau, China[J]. Science of the Total Environment,2017,575:1538.   
[18] 高江波,王欢.基于GWR模型的喀斯特地区产流量与土壤侵蚀 权衡的时空特征——以贵州省三岔河流域为例[J].山地学报, 2019,37(4): 518-527.[Gao Jiangbo, Wang Huan. Spatio-temporal tradeoff of Karst water yield and soil erosion based on GWR model: A case study in Sancha River Basin of Guizhou province, China [J]. Mountain Research,2019,37(4): 518-527.]   
[19]Maud A M,Penelope L, Berta M, et al. An interdisciplinary methodological guide for quantifying associations between ecosystem services[J]. Global Environmental Change,2014,28: 298-308.   
[20]Peng J, Wang XY,LiuYX,etal. Urbanizationimpactonthesupply-demand budget of ecosystem services: Decoupling analysis[J]. Ecosystem Services,2020,44: 101139.   
[21]Rozas- Vasquez D, Fuerst C, Geneletti D. Integrating ecosystem services in spatial planning and strategic environmental assessment: The role of the cascade model[J]. Environmental Impact Assessment Review,2019,78: 106291.   
[22]马琳,刘浩,彭建,等.生态系统服务供给和需求研究进展[J].地 理学报,2017,72(7):1277-1289.[Ma Lin,Liu Hao,Peng Jian,et al.A review of ecosystem services supply and demand[J].Acta Geographica Sinica,2017,72(7):1277-1289.]   
[23]王嘉丽,周伟奇.生态系统服务流研究进展[J].生态学报,2019, 39(12):4213-4222.[Wang Jiali,Zhou Weiqi. Ecosystem service flows: Recent progress and future perspectives[J]. Acta Ecologica Sinica,2019,39(12): 4213-4222.]   
[24] 杨丽雯,董丽青,张立伟,等.固碳服务供需平衡和服务流量化 评估——以引黄入晋南干线为例[JJ.资源科学,2019,41(3): 557-571.[Yang Liwen, Dong Liqing,Zhang Liwei, et al. Quantitative assessment of carbon sequestration service supply and demand and service flows:A case study of the Yellow River Diversion Project South Line[J]. Resources Science, 2019,41(3): 557-   
571.] [25] 刘慧敏,范玉龙,丁圣彦.生态系统服务流研究进展[J].应用生 态学报,2016,27(7): 2161-2171.[Liu Huimin,Fan Yulong, Ding Shengyan. Research progress of ecosystem service flow[J]. Chinese Journal of Applied Ecology,2016,27(7): 2161-2171.] [26] Li X, Yu X,Wu K N,et al. Land-use zoning management to protecting the regional key ecosystem services:A case study in the city belt along the Chaobai River, China[J].Science of The Total Environment,2020,762: 143167. [27] 王壮壮,张立伟,李旭谱,等.区域生态系统服务供需风险时空 演变特征—以陕西省产水服务为例[J].生态学报,2020,40 (6): 1887-190o.[Wang Zhuangzhuang, Zhang Liwei,Li Xupu,et al. Spatio-temporal pattern of supply-demand risk of ecosystem services at regional scale: A case study of water yield service in Shaanxi Province[J]. Acta Ecologica Sinica,202O,40(6):1887-   
1900.] [28] Wang L J, Zheng H,Wen Z. Ecosystem service synergies/tradeoffs informing the supply- demand match of ecosystem services: Framework and application[J].Ecosystem Services，2019,37:   
100939. [29]Feng Q, Zhao W W,Duan B L,et al.Coupling trade-offs and supply-demand of ecosystem services (ES): A new opportunity for ES management[J]. Geography and Sustainability,2O21,2: 275-280. [30] 谢高地,甄霖,鲁春霞,等.一个基于专家知识的生态系统服务 价值化方法[J]. 自然资源学报,2008,23(9):911-920.[Xie Gaodi, Zhen Lin,Lu Chunxia,et al.Expert knowledge based valuation method of ecosystem services in China[J]. Journal of Natural Resources,2008,23(9): 911-920.] [31] 谢高地,张彩霞,张雷明,等.基于单位面积价值当量因子的生 态系统服务价值化方法改进[J].自然资源学报,2015,30(8):   
1243-1254.[Xie Gaodi, Zhang Caixia, Zhang Leiming,et al. Improvement of the evaluation method for ecosystem service value based on per unit area[J]. Journal of Natural Resources,2015,30 (8): 1243-1254.] [32] Bradford JB,D'amato A W.Recognizing trade-offs in multi-objective land management[J].Frontiers in Ecology and the Environment,2012,10(4): 210-216. [33]Lu N,Fu B,Jin T,et al. Trade-off analyses of multiple ecosystem services by plantations along a precipitation gradient across Loess Plateau landscapes[J].Landscape Ecology，2014,29(5):1697-   
1708. [34] Yang SQ, Zhao W W,Liu Y,et al. Influence of land use change on the ecosystem service trade-offs in the ecological restoration area: Dynamics and scenarios in the Yanhe watershed, China[J]. Science of The Total Environment,2018,644(23): 556-566.   
[35]Liang J,Li S,Li X, et al. Trade-off analyses and optimization of water-related ecosystem services (WRESs) based on land use change in a typical agricultural watershed,southern China[J]. Journal of Cleaner Production,2021,279:123851.   
[36] 段宝玲,冯强,原燕燕,等.钱江源国家公园体制试点区生态系 统服务权衡与协同分析[J].旅游科学,2021,35(5):11-31. [Duan Baoling,Feng Qiang, Yuan Yanyan,et al.Ecosystem Services Trade-offs and Synergies in Qianjiangyuan National Park System Pilot[J]. Tourism Science,2021,35(5): 11-31.]   
[37] 谢余初,张素欣,林冰,等.基于生态系统服务供需关系的广西 县域国土生态修复空间分区[J].自然资源学报,2020,35(1): 217-229.[Xie Yuchu,Zhang Suxin,Lin Bing,et al.Spatial zoning for land ecological consolidation in Guangxi based on the ecosystem services supply and demand[J]. Journal of Natural Resources, 2020,35(1): 217-229.]   
[38] 王萌辉,白中科,董潇楠.基于生态系统服务供需的陕西省土地 整治空间分区[J].中国土地科学,2018,32(11):73-80.[Wang Menghui, Bai Zhongke,Dong Xiaonan. Land consolidation zoning in Shaanxi Province based on the supply and demand of ecosystem services[J]. China Land Science,2018,32(11): 73-80.]   
[39] 彭建,杨肠,谢盼,等.基于生态系统服务供需的广东省绿地生 态网络建设分区[J].生态学报,2017,37(13):4562-4572.[Peng Jian,Yang Yang,Xie Pan,et al.Zoning for the construction of green space ecological networks in Guangdong Province based on the supply and demand of ecosystem services[J]. Acta Ecologica Sinica,2017,37(13): 4562-4572.]   
[40] 翟天林,王静,金志丰,等.长江经济带生态系统服务供需格局 变化与关联性分析[J].生态学报,2019,39(15):5414-5424. [Zhai Tianlin,Wang Jing, Jin Zhifeng,etal. Change and correlation analysis of the supply-demand pattern of ecosystem services in the Yangtze River Economic Belt[J].Acta Ecologica Sinica, 2019, 39(15): 5414-5424.]   
[41]Wang J, Zhai TL,Lin YF,et al. Spatial imbalance and changes in supply and demand of ecosystem services in China[J]. Science of the Total Environment,2019,657: 781-791.   
[42] 刘晶晶,王静,戴建旺,等.黄河流域县域尺度生态系统服务供 给和需求核算及时空变异[J].自然资源学报,2021,36(1):148- 161.[Liu Jingjing,Wang Jing, Dai Jianwang,et al. The relationship between supply and demand of ecosystem services and its spatio-temporal variation in the Yellow River Basin[J]. Journal of Natural Resources,2021,36(1): 148-161.]

# Relationship between trade-off intensity of ecosystem services and matching degree of supply and demand: A case study in Shanxi Province

FENG Qiang'， ZHAO Wenwu²， DUAN Baoling'   
(1.College of Resources and Environment,Shanxi UniversityofFinanceand Economics,Taiyuan O3ooo6,Shanxi,   
China; 2.State KeyLaboratory of Earth Surface Processes and Resource Ecology,Facultyof Geographical Science, Beijing Normal University,Beijing 1O0875,China)

Abstract: Revealing the relationship characteristics between the intensity of ecosystem service (ES) tradeoffs and the matching degree of ES supply and demand can provide possible ways to alleviate the ES conflict and supply-demand contradiction simultaneously.The districts and counties of Shanxi Province are selected in this study. Considering the tradeoffbetween supply and support service,tradeofftype 1 is when the supply service is relatively enhanced but support service is decreased,whereas tradeoff type2 is the opposite condition.The influencing factors of ES tradeoffs and supply-demand and their related characteristics are revealed by redundancy analysis and piecewise linear regression. The following resultsare presented.(1）The high- value regions of tradeoff type l and the low-value regions of supply-demand ratio are mainly located in the basins,and the highvalue regions of tradeoff type 2and supply-demand ratio are mainly located in the mountainous area.(2) Tradeoff type 1 is mainly affcted by cropland,forestland,grassand,air temperature,and other factors.Meanwhile, tradeoff type2is primarilyinfluenced byropland,forestland,NDVI,andsoilorganic matter,butthedirectionof effects is opposite to that of tradeoff type1.(3)The forestland,grassland,and slope gradient have significant positive efects on the supply-demand ratio of type 1,while the cropland and construction land have significant negative effects.The factors have minimal effects on the supply-demand ratio oftype2.(4)The effects of factor direction on tradeof type 1 and the supply-demand ratio are opposite,which mainly contributes to the negative correlation between them.The response of the ES supply-demand ratio to tradeoffs is relatively strong when the contradiction between ES supply and demand is small.However, this response weakens with the deepening of the supply-demand contradiction.The relationship characteristics indicate the ecological dilemma:the human demand increases-development intensity increases-tradeofftype 1 enhances-the contradiction between supply and demand intensifes.A weak positive correlation is observed between tradeoff type 2 and supply-demand ratio,indicating the situation of ecological surplus.Overall,a correlation is observed between ES tradeoff and supply-demand. The results generally present the correlation characteristics and its formation mechanism,which can provide a scientific basis for land ecological restoration and management.

Keywords: ecosystem services； supply and demand; trade-offs； drivers； Loess Plateau