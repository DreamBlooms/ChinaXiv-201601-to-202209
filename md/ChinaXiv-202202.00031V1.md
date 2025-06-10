# 基于格网GIS的黄河流域土地生态质量综合评价

奥勇¹²，蒋嶺峰³，白召弟³，杨潇³，张乐艺³（1.长安大学土地工程学院,陕西 西安710054；2.陕西省土地整治重点实验室,陕西 西安710054;3.长安大学地球科学与资源学院，陕西 西安710054)

摘要：以 $8 ~ \mathrm { k m } { \times } 8 ~ \mathrm { k m }$ 的格网为评价单元，从土地生态系统的景观特征、生境质量抗干扰能力、生态系统服务价值、社会经济效益4个角度构建土地生态质量评价体系，利用层次分析法和熵值法确定权重,通过空间自相关、冷热点分析和障碍度诊断模型，探究了黄河流域土地生态质量的空间分异规律。结果表明：(1)黄河流域土地生态质量空间上呈中部及西南部较高、东南和东北部中等、西北质量较低的态势，土地生态质量总体较低，临界安全及危险区域分别占 $3 1 . 4 \% . 2 7 . 7 \%$ (2）黄河流域土地生态质量的空间自相关程度高，热点主要分布于治理强度较高的黄土高原、毛乌素沙地生态保护区，冷点分布于流域西北部，应适当加强上游区域土地生态的治理，消除极端冷点。(3)黄河流域土地生态质量主要障碍因子为经济密度、土地利用结构多样性、离生态保护区距离、离水域距离，应立足区域自然基础和资源禀赋状况，加快绿色创新驱动，将丰富的自然资源、生物资源和历史文化资源转化为市场价值，在生态修复和改造时，合理配置人工生态系统结构，必要时可增设自然保护区。

关键词：Fragstats；格网GIS；土地生态质量；黄河流域文章编号：

土地是人类赖以生存与发展的物质基础，是由近地表的气候、地貌、表层的地质、水文、土壤、动植物以及过去和现在人类活动的结果所形成的综合体，其内部要素的不同组合方式对人类生存及可持续发展的适宜程度即为土地生态质量[1]。随着人口增加、社会经济发展,土地生态系统破坏日益严重，人地矛盾加剧，如何科学评价土地生态质量已成为21世纪人类社会可持续利用和发展土地资源亟需解决的难题[2]

土地生态质量的研究起源于20世纪40年代Al-do Leopold提出的"土地健康"的概念[3],早期土地生态质量主要从土壤理化性质及污染状况展开研究。70年代联合国粮食与农业组织(FAO)颁布了关于土地质量变化检测评估和适宜程度评价的一系列纲要文件，土地生态质量评价逐渐受到关注。随着研究不断深人以及景观生态学、区域经济学等理论的引入，土地生态质量指标体系不断完善，涉及自然、经济、社会各个方面。目前国内外关于土地生态质量的研究主要侧重于土地生态质量的内涵4、评价方法5-的探索以及土地生态适宜性、土地生态脆弱敏感性[8-9]、土地生态安全[10-12]、土地生态系统健康[13]、土地生态质量[14-16]。评价体系主要有3种：（1）基于联合国粮食及农业组织制定的《可持续土地利用评价纲要》修改后构建的土地生态质量评价体系[；(2）基于"压力-状态-响应"(PSR)模型构建的土地生态质量评价指标体系8；（3）基于“经济-环境-社会"(EES)模型改进后土地生态质量评价指标体系[19]。以往研究取得了一定的成果,但仍存在以下问题：（1）在土地生态质量的内涵以及评价指标体系的选择上尚未达成共识；(2）指标体系过多依赖统计数据使得研究成果受到行政边界的束缚；（3）在土地生态质量等级划分方面缺少标准和依据，需要进一步研究生态质量阈值，增强其等级划分的实际意义。

以行政区为评价单元，未充分考虑空间异质性，一定程度上割裂了原有的地表自然地理联系，不能反映单元内部差异，而采用格网作为评价单元可以避免这些缺点。土地生态系统的抗干扰能力、恢复能力、稳定性与景观要素的异质性和生态系统服务功能密切相关[20]，同时将景观特征、生态系统服务功能、生态本底、经济属性纳入土地生态质量评价体系的研究较少，可进一步探索四者对土地生态质量的综合影响。黄河流域是我国西北重要的生态屏障，流域内水资源短缺、水环境问题突出、生态环境极其脆弱，所经地区在国家发展中具有极为重要的战略地位，2019年9月习近平总书记提出黄河流域生态保护和高质量发展的重大国家战略[21],但关于黄河流域土地生态质量研究很少。鉴于以上3点，本文以格网为评价单元，从土地生态系统的景观特征、生境质量抗干扰能力、生态系统服务功能、社会经济效益4个角度探究了2018年流域内土地生态质量的空间分异状况并提出相应措施，以期为黄河流域土地的可持续利用与发展提供参考。

# 1 研究区概况

黄河流域 $( 9 6 ^ { \circ } \mathrm { \sim } 1 1 9 ^ { \circ } \mathrm { E } , 3 2 ^ { \circ } \mathrm { \sim } 4 2 ^ { \circ } \mathrm { N } )$ 自西向东依次流经青海、四川、甘肃、宁夏、内蒙古、陕西、山西、河南、山东9个省份，流域总面积为 $7 . 4 6 \times 1 0 ^ { 5 } ~ \mathrm { k m } ^ { 2 }$ 。流域西部为河源区，冰川地貌发育， $7 0 \%$ 以上为草地，草地退化、水源涵养功能下降较为严重;中部主要为黄土地貌，地形破碎、水土流失严重，生态环境极其脆弱;东部主要为冲积平原，泥沙淤积严重，河道摆动频繁且普遍高于地面(图1)。流域内为典型的大陆性气候，西北部为干旱型，中部为半干旱型，东南部为半湿润型。流域水资源量仅占全国的$2 \%$ ,却承担着全国 $1 5 \%$ 的耕地面积和 $12 \%$ 的人口。

# 2数据与方法

# 2.1数据来源

本文涉及到的数据有2018年 $1 ~ \mathrm { k m }$ 土地利用数据 $. 1 \mathrm { k m }$ 高程数据、2018年 $1 ~ \mathrm { k m }$ 年度归一化植被指数数据、生态保护区数据(来自资源环境科学与数据中心,http://www.resdc.cn/）、水系分布数据（来自全国地理信息资源目录服务系统，http://www.webmap.cn/）、2018年路网数据（来自开放街道地图Open Street Map平台,https://www.openstreetmap.org/）2018年黄河流域各市人口经济粮食数据(各市统计年鉴）、2018年 $1 \mathrm { k m }$ 人口密度数据（WorldPop全球人□数据产品,https://www.worldpop.org/）。

![](images/f14596d7740b8b74ca432327d778e542187220b36417f3e48dc4db4bcf036f4e.jpg)  
Fig.1 Topographic map of the Yellow River Basin

# 2.2指标体系构建

土地是自然、社会经济的复合体，具有系统性、复杂性的特点，因此在评价土地生态质量时要以土地生态系统为对象多维度、科学的选取评价指标[1]。本文基于“经济-环境-社会"(EES)模型，从土地生态系统的景观特征、生境质量抗干扰能力、生态系统服务功能和社会经济效益4个角度建立指标体系。土地的景观格局特征影响区域土地生态系统的生态过程，反映了土地生态系统结构的协调性[22]。景观要素在空间上分散或聚集的展布即景观格局，它是自然、生物和社会要素之间相互作用的结果。其斑块的形状、大小、数量和空间组合不仅影响着生物物种的分布和运输，同时对径流和侵蚀等生态过程和边缘效应也有一定的影响。生境质量的抗干扰能力是土地生态安全的基础，反映了土地生态系统功能的稳定性。生态系统服务是指生态系统的条件和过程提供给人的商品和服务，代表着人类直接和间接地从生态系统中得到的利益，它是链接自然过程与社会过程的桥梁与纽带，其不依人的存在而存在，只是在人类十扰后而发生一定的胁迫反应，而服务功能下降，又会影响人类的生存和发展。因此，生态系统服务功能是衡量“自然-社会”耦合系统可持续发展的重要指标依据[16.23-24]。社会经济效益则是土地生态可持续发展的动力和支撑，

# 干旱区地理

良好的经济发展水平有助于加大对土地生态系统建设的投入，增强区域发展后劲，实现区域土地生态系统高质量发展。

在景观特征层中依据景观生态学方法从土地利用景观斑块面积、斑块形状、斑块空间结构3个方面选取香农多样性指数(Shannon'sdiversityindex,SHDI）、最大斑块指数(Largest patch index,LPI）、景观形状指数(Landscape shape index,LSI）、景观蔓延度（Contagionindex,CONTAG)4个指标来高度浓缩景观格局信息。香农多样性指数表征景观类型的丰富度，多样性越强，景观异质性和生物生境的多样性越高，生态环境质量越好。最大斑块指数反映景观的优势度。景观形状指数可以衡量景观形状的规整程度和破碎度，反映了景观受人类活动干扰的程度。景观蔓延度用来反映优势景观空间上的连通性，其直接影响到物种的繁殖、扩散、迁移和保护[25]。在土地生态系统的抗干扰能力层根据相关研究[2.8.26],选取了自然生态基础指标中的高程、坡度、归一化植被指数、离水域距离以及人为干扰因素中的离生态保护区距离、离道路距离、土地利用结构多样性共7个指标。在生态系统服务功能角度，选取一级服务类型中的供给服务、调节服务、支持服务、文化服务4项指标。在土地生态系统的社会经济效益层根据文献[2」，选取人均收入水平、经济密度表征土地利用效率和土地资源优化配置程度，人均粮食产量反映土地生产的自给能力，人口密度表征人口与土地承载力之间的关系。具体指标选择见表1。

# 2.3格网划分及指标计算

黄河流域平均斑块面积为 $1 4 . 2 2 \mathrm { k m } ^ { 2 }$ ，依据景观生态学研究[28],格网面积应为平均斑块面积的2\~5倍，考虑研究区地理特征，选取 $8 ~ \mathrm { k m } { \times } 8 ~ \mathrm { k m }$ 格网进行评价。利用ArcGIS10.7创建黄河流域 $8  { \mathrm { k m } } \times 8  { \mathrm { k m } }$ 的格网共13255个。

景观特征指数的计算是基于Fragstats软件，分别计算出每个格网对应的景观指数

生境质量抗干扰能力层各指标主要基于Arc-GIS10.7的坡度分析及缓冲区分析得到各指标的空间分布情况。对于无法量化的指标则根据相应的标准和研究进行分级赋值[8.10.26],如表2所示，离水域距离为正指标，距离越近，则区域水资源越丰沛，有利于土地生态系统良序运转;高程和坡度均为逆向指标，高程和坡度越大，土地资源的利用难度越大；离一级道路的距离为逆向指标，离道路越近其生态敏感性也越强，区域生态系统的稳定性也一定程度上受到削弱；而生态保护区是生态系统、物种及其栖息地保护的核心阵地，可有效缓解社会快速发展对自然环境的破坏[2.10]

土地生态系统的社会经济效益层中，人均收入、经济密度、人均粮食产量是基于市级统计年鉴计算出各市的平均值并进行分区统计，人口密度采用空间化的栅格数据产品，

生态系统服务功能方面，因为生态系统服务功能具有强烈的空间异质性，基于全国尺度的当量因子计算黄河流域生态服务价值会产生较大误差，因此需要对黄河流域生态系统服务当量进行修正减小误差。修正方法详见参考文献[29」，得出区域修正系数为0.94，得到黄河流域1个生态系统服务当量因子为3202.11元， $\mathrm { h m } ^ { - 2 }$ 。结合黄河流域土地覆盖特征将研究区划分为农田、森林、草地、水域、建设用地、湿地和荒漠7类生态系统类型，根据当量因子表及修正后的当量因子值，可以计算黄河流域各土地利用类型的生态系统服务价值系数(表3)，进而计算出黄河流域土地生态系统服务价值，其中建设用地价值依据文献[30]计算得到。

# 2.4指标标准化及权重

2.4.1指标标准化为了使指标间具有可比性，同时便于加权求和，对指标进行极差归一化处理[2]，公式如下：

$$
R _ { i j } = { \frac { X _ { i j } - \operatorname* { m i n } \left| X _ { i j } \right| } { \operatorname* { m a x } { \left| X _ { i j } \right| } - \operatorname* { m i n } { \left| X _ { i j } \right| } } }
$$

$$
R _ { i j } = { \frac { \operatorname* { m a x } { \lvert X _ { i j } \rvert } - X _ { i j } } { \operatorname* { m a x } { \lvert X _ { i j } \rvert } - \operatorname* { m i n } { \lvert X _ { i j } \rvert } } }
$$

式中： $R _ { i j }$ 为指标标准化得分值； $X _ { i j }$ 为准则层 $i$ 中第$j$ 项指标的值; $ \operatorname* { m i n } | X _ { i j } | ,  \operatorname* { m a x } | X _ { i j } |$ 代表准则层 $i$ 中第$j$ 项指标内的最小值和最大值。其中公式(1)用于正向指标的处理，公式(2)用于负向指标的处理。

2.4.2指标权重熵权法可以准确的判断熵值的离散程度，从而较为客观和科学的确定指标权重，但当信息熵 $( E _ { j } )$ 接近1时，微小变化会导致权重变化很大，太过于依赖数学和统计定量方法，而层次分析法恰好可以弥补其主观定性分析不足。本文采用熵权法和层次分析法结合计算指标权重，计算公式详见参考文献[2]。

表1黄河流域土地生态质量综合评价指标体系  
Tab.1 Comprehensive evaluation index system of land ecological quality in the Yellow River Basin   

<html><body><table><tr><td>目标层准则层(权重)</td><td>黄河流景观特征</td><td>指标层(权重)</td><td colspan="4">指标计算</td><td>性质</td><td>参考文献</td></tr><tr><td>域土地 (0.140) 生态质 量综合 评价</td><td></td><td>景观形状指数(0.224) 最大斑块指数(0.173)</td><td colspan="4">LSI= 0.25L/√A 式中：LSI为景观形状指数;L为斑块周长(m);A为斑块面积(m)。</td><td>负</td><td>[2,16]</td></tr><tr><td></td><td></td><td></td><td colspan="4">LPI= Max(a, a2,,a) 式中：LPI为最大斑块指数；α为斑块n的面积(m2);A为景观总面</td><td>正</td><td>[2,16]</td></tr><tr><td></td><td></td><td>香农多样性指数(0.267)</td><td colspan="4">积(m²)。 SHDI= (P lnP)</td><td></td><td>[2,16]</td></tr><tr><td></td><td>景观蔓延度(0.336)</td><td></td><td colspan="4">式中：SHDI为香农多样性指数；P为斑块类型i占景观总面积的 比例;m为斑块类型总数。</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td colspan="4">CONTAG= ∑M</td><td>正</td><td></td></tr><tr><td></td><td></td><td colspan="4">i和k类型相邻的斑块数;m为类似的景观总数。</td><td>式中：CONTAG为景观蔓延度;pi为i类型景观占总景观比例；g为</td><td></td><td></td></tr><tr><td>干扰能力 (0.408)</td><td></td><td colspan="4">生境质量抗 归一化植被指数(0.046) NDVI=(NIR -R)(NIR + R)</td><td></td><td>正</td><td>[8,26]</td></tr><tr><td></td><td>高程(0.084)</td><td colspan="4">式中：NDVI为归一化植被指数;NIR为近红外波段;R为红波段。 由数字高程模型(DEM)得到</td><td></td><td>负</td><td>[8]</td></tr><tr><td></td><td>坡度(0.091)</td><td colspan="4">由DEM得到</td><td></td><td>负</td><td>[8,10]</td></tr><tr><td></td><td>离生态保护区距离(0.291)</td><td colspan="4">保护区数据缓冲区分析得到</td><td></td><td>正</td><td>[2]</td></tr><tr><td></td><td>土地利用结构多样性(0.233)</td><td colspan="4">C=-∑c.ln(C.)</td><td></td><td>正</td><td>[2]</td></tr><tr><td></td><td></td><td colspan="4">式中：C为土地利用结构多样性指数;Ci为第i种土地利用类型面</td><td></td><td></td><td></td></tr><tr><td></td><td>离水域距离(0.145)</td><td colspan="4">积(m);n为土地利用类型的数量。 由水系数据缓冲区分析得到</td><td></td><td></td><td>[8,26]</td></tr><tr><td></td><td>离道路距离(0.110)</td><td colspan="4">由道路数据缓冲区分析得到</td><td></td><td>正 负</td><td>[8,26]</td></tr><tr><td>会经济效益</td><td>土地利用社 人口密度(0.010)</td><td colspan="4"></td><td></td><td>负</td><td>[2,10]</td></tr><tr><td>(0.292)</td><td>人均粮食产量(0.186)</td><td colspan="4">空间化人口密度数据</td><td></td><td>正</td><td>[2]</td></tr><tr><td></td><td>人均收入水平(0.285)</td><td colspan="4">各市粮食总产量/常住人口</td><td></td><td>正</td><td>[2,10]</td></tr><tr><td></td><td>经济密度(0.519)</td><td colspan="4">各市生产总值/常住人口</td><td></td><td>正</td><td>[2,10]</td></tr><tr><td></td><td>土地生态系生态系统供给服务价值(0.285）依据中国生态系统服务价值当量因子表修正后计算得到</td><td colspan="4">各市生产总值/土地面积</td><td></td><td>正</td><td>[16,27]</td></tr><tr><td>统服务价值</td><td>生态系统调节服务价值(0.187）依据中国生态系统服务价值当量因子表修正后计算得到</td><td colspan="4"></td><td></td><td>正</td><td>[16,27]</td></tr><tr><td>(0.160)</td><td></td><td colspan="4"></td><td></td><td></td><td>[16,27]</td></tr><tr><td></td><td>生态系统文化服务价值(0.161)</td><td colspan="4">生态系统支持服务价值(0.367）依据中国生态系统服务价值当量因子表修正后计算得到 依据中国生态系统服务价值当量因子表修正后计算得到</td><td></td><td>正 正</td><td>[16,27]</td></tr></table></body></html>

# 2.5土地生态质量综合指数

$$
P { = } \sum _ { j { = 1 } } ^ { n } W _ { j } { \times } T _ { j }
$$

式中： $P$ 为评价对象的综合评价值； $n$ 为评价因子的个数； $\boldsymbol { W } _ { j }$ 为评价因子的组合权重； $T _ { j }$ 为第 $j$ 个评价因子的标准化得分值。

# 2.6空间统计分析

2.6.1空间自相关及冷热点分析空间自相关是对空间临近的区域单元属性值相似程度和空间关联模式的定量描述，用于揭示相邻地域间某种地理现象的空间相互作用关系。分为全局空间自相关和局部自相关,本文利用全局自相关Moran'sI探究整个研究区土地生态质量的空间相关性。Moran'sI的值介于-1到1之间，其绝对值大小代表相关程度，

# 干吴区地理

# 表2生境质量抗干扰能力层部分指标分级标准

Tab.2 Classification standard of some indices of antiinterferenceabilityof habitat   

<html><body><table><tr><td>指标</td><td>分级标准</td><td>评价值</td><td>指标</td><td>分级标准</td><td>评价值</td></tr><tr><td rowspan="5">高程/m</td><td>[0,1000]</td><td>1</td><td rowspan="5">离一级 水系距 离/m</td><td>[0,1000] (1000,2000]</td><td>9</td></tr><tr><td>(1000,2000]</td><td>3</td><td></td><td>7</td></tr><tr><td>(2000,3000]</td><td>5</td><td>(2000,3000]</td><td>5</td></tr><tr><td>>3000</td><td>7</td><td>(3000,5000]</td><td>3</td></tr><tr><td>1</td><td>离二级</td><td>>5000 [0,500]</td><td>1 9</td></tr><tr><td rowspan="4">坡度/()</td><td>[0,5] (5,15]</td><td>3</td><td>水系距</td><td>(500,1000]</td><td>7</td></tr><tr><td>(15,25]</td><td>5</td><td>离/m</td><td>(1000,1500]</td><td>5</td></tr><tr><td>>25</td><td>7</td><td></td><td>(1500,2500]</td><td>3</td></tr><tr><td></td><td></td><td></td><td>>2500</td><td>1</td></tr><tr><td>离生态 保护区</td><td>保护区内 保护区外</td><td>7</td><td>离三级</td><td>[0,500]</td><td>7</td></tr><tr><td>距离/m</td><td></td><td>1</td><td>水系距 离/m</td><td>(500,1000] (1000,1500]</td><td>5 3</td></tr><tr><td></td><td></td><td></td><td></td><td>>2500</td><td>1</td></tr><tr><td>离道路 距离/m</td><td>[0,1000] (1000,2000]</td><td>7</td><td></td><td></td><td></td></tr><tr><td></td><td>(2000,3000] >3000</td><td>5 3</td><td></td><td></td><td></td></tr></table></body></html>

大于0表示正相关，反之表示负相关[9。冷热点分析用于探索地理属性局部空间聚类特征，判断其是否存在高值或低值聚集，具体计算公式详见文献[9]。

2.6.2障碍度诊断障碍度模型作为土地生态质量障碍因子定量识别的重要方法，可为区域土地生态的精确治理管理方案的制定提供科学依据，障碍度模型由因子贡献度、指标偏离度和障碍度3个指标组成[31],公式如下：

$$
M _ { j } = \frac { W _ { j } \times \left( 1 - T _ { j } \right) } { \displaystyle \sum _ { j = 1 } ^ { n } \bigl [ W _ { j } \times ( 1 - T _ { j } ) \bigr ] }
$$

式中： $M _ { j }$ 为第 $j$ 项指标对土地生态质量的障碍度； $n$   
为评价因子的个数； $\textstyle \mathbf { \begin{array} { r l } \end{array} } \mathbf { \begin{array} { r l } \end{array} } \mathbf { \begin{array} { r l } \end{array} }$ 为评价因子的组合权重; $T _ { j }$

为第j个评价因子的标准化得分值。

# 3结果与分析

# 3.1土地生态质量的空间分析

3.1.1准则层空间特征分析利用自然断点法[32]对景观特征综合质量、生境质量抗干扰能力、生态系统服务价值、土地利用社会经济效益进行分等。如图2所示，高等及较高水平景观特征分布与黄河流域一级水系分布态势基本一致，而中低等水平景观特征主要分布于黄河流域中部的黄土高原区，该区域景观破碎程度高，斑块形状不规整，斑块小并且同类型景观连通度较差呈离散状分布，形成复杂、异质、不连续的镶嵌体。

生境质量抗干扰能力高值区分布于研究区中部的毛乌素沙地生态功能保护区、黄土高原生态功能保护区以及西南部的黄河源、若尔盖-玛曲生态功能保护区；低值区集中分布于研究区西北部的青海东南部、甘肃中部及西南部，该区坡度及海拔较高，植被类型主要为草地、土地利用结构多样性指数较低，自然基础较差。生态系统服务价值低值区域分布于鄂尔多斯和巴彦淖尔的局部，该区分布大量的沙地、裸岩、草地导致土地生态系统服务功能较差，生态敏感性较高。土地利用社会经济效益综合指数呈现东高西低阶梯状分布态势，高等及较高效益区主要分布于山西、陕西北部、鄂尔多斯，该区有丰富的煤炭、石油、有色金属等能矿资源，经济密度较高，同时人均粮食产量也稳居前列[33]

3.1.2土地生态质量综合等级空间特征分析利用自然断点法对土地生态质量进行分等，研究区土地生态质量综合等级空间分布如图3所示。黄河流域土地生态质量总体呈中部及西南部质量较高、东北部和东南部中等、西北部较低的态势。安全及较安全区主要分布于研究区西南部的黄河源、若尔盖-玛曲生态功能保护区、甘肃东部地区、鄂尔多斯南部、陕西北部地区、山西局部。临界安全区主要分布于黄河流域东北部和东南部。危险区域主要分布于黄河流域西北部的青海、甘肃、宁夏境内。

表3黄河流域各类土地生态服务价值系数  
Tab.3Ecological service value coeficients of all kinds of land in the Yellow River Basin /元·hm-²   

<html><body><table><tr><td>-级类型</td><td>二级类型</td><td>森林</td><td>草地</td><td>农田</td><td>湿地</td><td>水域</td><td>荒漠</td><td>建设用地</td></tr><tr><td rowspan="2">供给服务</td><td>食物生产</td><td>1056.70</td><td>1376.91</td><td>3202.11</td><td>1152.76</td><td>1697.12</td><td>64.04</td><td>0.00</td></tr><tr><td>原材料生产</td><td>9542.29</td><td>1152.76</td><td>1248.82</td><td>768.51</td><td>1120.74</td><td>128.08</td><td>1120.74</td></tr><tr><td rowspan="3">调节服务</td><td>气体调节</td><td>13833.12</td><td>4803.17</td><td>2305.52</td><td>7717.09</td><td>1633.08</td><td>192.13</td><td>0.00</td></tr><tr><td>气候调节</td><td>13032.59</td><td>4995.29</td><td>3106.05</td><td>43388.59</td><td>6596.35</td><td>416.27</td><td>0.00</td></tr><tr><td>水源涵养</td><td>13096.63</td><td>4867.21</td><td>2465.62</td><td>43036.36</td><td>60103.60</td><td>224.15</td><td>-49408.56</td></tr><tr><td rowspan="3">支持服务</td><td>净化环境</td><td>5507.63</td><td>4226.79</td><td>4450.93</td><td>46110.38</td><td>47551.33</td><td>832.55</td><td>-10342.82</td></tr><tr><td>保持土壤</td><td>12872.48</td><td>7172.73</td><td>4707.10</td><td>6372.20</td><td>1312.87</td><td>544.36</td><td>0.00</td></tr><tr><td>维持生物多样性</td><td>14441.52</td><td>5987.95</td><td>3266.15</td><td>11815.79</td><td>10983.24</td><td>1280.84</td><td>0.00</td></tr><tr><td>文化服务</td><td>提供美学景观</td><td>6660.39</td><td>2785.84</td><td>544.36</td><td>15017.90</td><td>14217.37</td><td>768.51</td><td>0.00</td></tr></table></body></html>

![](images/509116b1524baaf100c33a26d842e8f72a23e96f49e168b6dd4b99a382371824.jpg)  
Fig.2 Comprehensive evaluations of criteria layer indices ofland ecological quality in the Yelow River Basin

![](images/83fae78d47ea27bd4f9899f21180f09e277473e733c5f46557757f13b6362918.jpg)  
图2黄河流域土地生态质量准则层指标综合评价  
图3黄河流域土地生态质量综合等级  
Fig.3Comprehensive grade of land ecological quality in the Yellow River Basin

# 3.2土地生态质量的空间统计分析

3.2.1空间自相关分析利用Geoda软件的空间分析功能计算研究区土地生态质量在K-邻近、Rook邻接、Queen邻接3种空间权重下的Moran'sI指数（图4）。Moran'sI值分别为0.840、0.869、0.843，表明黄河流域土地生态质量存在较强的正相关现象，其空间分布存在聚集态势，即土地生态质量较高的区域倾向于与其他土地生态质量较高的区域毗邻，而土地生态质量较低的区域倾向于与其他土地生态质量较低的区域毗邻。

3.2.2冷热点分析全局空间自相关分析可以判别区域整体土地生态质量的空间关联情况，但对于局部相邻区域间要素和属性的关联模式却无法识别，需要借助冷热点分析方法探求局部土地生态质量的关联情况(图5)。热点即土地生态质量指数高值聚集区，热点区域占 $2 2 . 0 6 \%$ 共计2925个栅格，主要分布于鄂尔多斯南部、陕西北部、陕西南部、山西西部以及甘肃东部、四川北部。其中，鄂尔多斯南部、陕西北部、山西西部位于毛乌素沙地、黄土高原生态功能保护区，该区具有较高的生境质量抗干扰能力并凭借丰富的能矿资源取得较好的经济效益，因此出现高值聚集。冷点即土地生态质量指数低值聚集区，冷点区域占 $2 4 . 7 9 \%$ 共计3286个栅格，主要分布于青海东南部、甘肃大部、宁夏北部地区，该区域为高原温带半干旱区，坡度海拔较高，自然条件较差，经济发展水平低，因此出现低值聚集。冷热点分布趋势不仅反映了自然基础、资源禀赋的差异，也与治理政策的导向密切相关。2006年以来不断加大对黄河流域中游生态建设和环境治理力度，但是黄河上游区治理相对较弱，这是流域中游区高值聚集西北部冷点聚集格局形成的一个重要因素[34]

![](images/00b1fc212e0747296160811257454c87416af47c332b91013a497dec8820323e.jpg)  
图4土地生态质量Moran's $I$ 散点图 Fig.4 Moran's $I$ scatter plot of land ecological quality

![](images/8d8e638892d44f10691cdfaafce2f3053160ba4e9c5e46d37659fb486aca307a.jpg)  
图5黄河流域土地生态质量冷热点分布 Fig.5Distribution of cold and hot spots of land ecological quality in the Yellow River Basin

3.2.3障碍度诊断及建议研究区单指标及准则层障碍度测算结果如表4所示，障碍度较高的准则层为生境质量抗干扰能力和土地利用社会经济效益，平均障碍度分别为 $4 1 . 9 3 5 \% , 4 3 . 5 3 7 \%$ ,反映了黄河流域整体自然基础条件差、经济发展水平低的现状。单指标中经济密度、土地利用结构多样性、离生态保护区距离、离水域距离、人均收入水平5个指标平均障碍度较高，分别为 $2 8 . 4 5 9 \%$ 、 $1 3 . 9 0 3 \%$ 、$1 0 . 5 7 0 \% . 8 . 5 9 9 \% . 8 . 1 1 4 \%$ ，是限制黄河流域土地生态质量的主导因素。

土地生态质量处于安全等级的区域占比为$1 2 . 4 \%$ ,面积为 $1 0 0 1 7 6 . 1 1 { \mathrm { ~ k m } } ^ { 2 }$ ，主要分布于鄂尔多斯南部、榆林延安局部、山西西部以及陕西南部。其中，鄂尔多斯南部、榆林延安局部、山西西部地区处于黄土高原区，主要障碍因子为经济密度、土地利用结构多样性、离水域距离，在生态文明建设的推进下该区域生态环境得到很大改善，而支撑经济发展的传统高消耗、高污染、高排放产业下滑严重，第三产业发展水平较低，因此应积极升级改革产业结构，提升经济效益[33],同时继续水土保持治理与退耕还林等工作，合理配置人工生态系统结构[5],使区域土地生态系统"由黄变绿，由绿变稳”。

土地生态质量处于较安全等级的区域占比为$2 8 . 5 \%$ ,面积为 $2 3 0 6 2 2 . 7 7 ~ \mathrm { k m } ^ { 2 }$ ,主要分布于黄河流域中部的黄土高原生态功能保护区内以及流域西南部的黄河源、若尔盖-玛曲生态功能保护区内。主要障碍因子为经济密度、土地利用结构多样性、人均收入水平，该区资源相对匮乏生态经济失调较为严重[36],因此甘肃东部及宁夏南部区域应在加强黄土区治理的同时发展生态经济，促进生态经济协调发展，位于黄河源区的研究区西南部则要以保护为主，发展生态畜牧。

土地生态质量处于临界安全等级的区域占比为 $3 1 . 4 \%$ ,面积为 $2 5 3 9 3 7 . 6 6 \mathrm { k m } ^ { 2 }$ ,主要分布于黄河流域东北部和东南部。

土地生态质量处于危险等级区域占比为$2 7 . 7 \%$ ,面积为 $2 2 4 2 0 2 . 9 0 \mathrm { k m } ^ { 2 }$ ,主要分布于研究区西北部生态脆弱区，主要障碍因子为经济密度、离生态保护区距离、土地利用结构多样性，该区域应该摒除"先破坏、后治理"的粗放式经济增长模式，创新驱动新动能，通过水土保持、水污染防治、滩区综合治理、生物多样性保护等措施建设流域美丽生态带[34]

表4黄河流域土地生态质量各等级区障碍因素诊断结果  
Tab.4Obstacle level of barrier factors for land ecological quality in the Yellow River Basin   

<html><body><table><tr><td rowspan="2">准则层及指标</td><td colspan="4">指标障碍度/%</td></tr><tr><td>危险区</td><td>临界安全区</td><td>较安全区</td><td>安全区</td></tr><tr><td>景观特征</td><td>11.482</td><td>11.873</td><td>13.127</td><td>15.716</td></tr><tr><td>生境质量抗干扰能力</td><td>47.342</td><td>46.346</td><td>39.508</td><td>34.547</td></tr><tr><td>土地利用社会经济效益</td><td>39.925</td><td>40.371</td><td>45.863</td><td>47.990</td></tr><tr><td>土地生态系统服务价值</td><td>1.250</td><td>1.410</td><td>1.502</td><td>1.747</td></tr><tr><td>景观形状指数</td><td>2.807</td><td>2.867</td><td>3.007</td><td>3.839</td></tr><tr><td>最大斑块指数</td><td>1.351</td><td>1.295</td><td>1.261</td><td>1.832</td></tr><tr><td>香农多样性指数</td><td>2.740</td><td>3.092</td><td>3.808</td><td>3.839</td></tr><tr><td>景观蔓延度</td><td>4.584</td><td>4.619</td><td>5.051</td><td>6.206</td></tr><tr><td>归一化植被指数</td><td>0.617</td><td>0.891</td><td>0.820</td><td>0.956</td></tr><tr><td>高程</td><td>3.194</td><td>1.829</td><td>3.396</td><td>2.669</td></tr><tr><td>坡度</td><td>3.014</td><td>2.294</td><td>2.637</td><td>2.922</td></tr><tr><td>离生态保护区距离</td><td>16.621</td><td>17.121</td><td>7.314</td><td>1.226</td></tr><tr><td>土地利用结构多样性</td><td>12.554</td><td>13.325</td><td>14.390</td><td>15.344</td></tr><tr><td>离水域距离</td><td>7.563</td><td>8.004</td><td>8.759</td><td>10.073</td></tr><tr><td>离道路距离</td><td>3.780</td><td>2.883</td><td>2.191</td><td>1.357</td></tr><tr><td>人口密度</td><td>0.003</td><td>0.003</td><td>0.002</td><td>0.002</td></tr><tr><td>人均粮食产量</td><td>6.479</td><td>5.988</td><td>7.292</td><td>8.085</td></tr><tr><td>人均收入水平</td><td>8.166</td><td>7.247</td><td>8.760</td><td>8.284</td></tr><tr><td>经济密度</td><td>25.277</td><td>27.133</td><td>29.810</td><td>31.618</td></tr></table></body></html>

# 4讨论

本研究从景观特征、生境质量抗干扰能力、生态系统服务、社会经济效益多视角对土地生态质量进行刻画，同时结合主客观赋权和格网GIS，丰富了传统评价方法的内涵。郭利刚等3以县为评价单元，研究了汾河流域土地生态状况，结果显示生态质量高值主要分布于娄烦县、古交县、宁武县，与本研究结果基本一致，但本研究对县区内部土地状况的空间分异进行了精确刻画，体现格网GIS在生态评价方面的优越性。

2018年黄河流域中部及西南部土地生态质量较高，东北部和东南部中等，流域西北部存在低值聚集。究其原因：（1）西北部位于黄河流域上游区，生态脆弱面临生态保护和经济发展双重任务。该区域较高的海拔坡度、较低的路网密度限制了区域土地资源的有效规划利用；土地利用结构多样性低，主要为草地，生境质量抗干扰能力低;长期受特殊的生态和地理环境影响以及诸多地理资本缺陷的制约，经济发展水平低。(2）相对于中下游区，西北部生态保护指数一直偏低，属于“生态塌陷"区[34]2006年以来黄河流域生态保护重心不断向中游转移，中游建成了毛乌素、黄土高原、秦岭等生态保护区，而流域上游生态保护指数较低。（3）经济发展水平低，土地生态质量提升动力不足。经济效益是土地生态质量重要组分，同时经济增长能够进一步推动产业发展及升级，加快实现地区产业结构高级化与合理化，进而提高地区的生态效率，也能减少地区内资源型产品的消耗，有利于保护地区的生态环境[38]。流域西北部在生态保护建设中做出了巨大的牺牲，缺乏相应的生态环境补偿，同时产业结构偏低、生态效率低下，是贫困易发高发地区。

王思远等[39]的研究发现1990年黄河流域生态状况上游区较好，下游区较差，中游区尤其是黄土高原东部区域最差，与本研究对比，黄河流域土地生态状况由1990年上游 $\mathrm { \ddot { > } }$ 下游 $\mathrm { \dot { > } }$ 中游转变为中游>下

# 干吴区地理

游 $>$ 上游，尤其是问题最为严重的黄土高原东部和毛乌素沙地等地区土地生态状况得到极大改善，已达安全等级，反映了近30a的黄河流域治理取得阶段性成果。但问题也很突出，全区土地生态系统经济效益不佳、土地利用结构多样性较差，流域西北部(上游区)存在土地生态质量低值聚集。李达等4研究表明黄河流域各市均未跨过生态保护的人均国内生产总值拐点（拐点之前，环境质量随经济增长而下降，当经济增长跨过拐点时，环境质量将随着经济增长而上升），片面提升经济会导致环境恶化，环境质量过低也会抑制经济增长。鉴于经济发展与环境这种复杂的相互作用机制，以及流域内土地生态系统经济效益、生境质量抗干扰能力低下和生态脆弱的现状，黄河流域土地生态质量西北低、中部高、东南东北中等的格局短期内很难改变。未来应因地制宜打造绿色产业体系发展经济，合理规划土地利用，加强流域生态保护投入，防止经济发展带来的环境恶化，同时进一步厘清土地生态质量内部子系统的相互作用机理，从而制定合理的发展思路和战略。

土地生态质量评价是一项复杂系统工程，限于多方面因素影响及数据可获取性的制约，本研究对于土地生态质量在时间与空间复合维度上的演变及驱动机制未做深入研究，未考虑土壤属性，选取的指标也可能具有一定局限性。土地生态质量评价是一个长期复杂的学术课题，目前学术界对土地生态评价指标的选择分歧较大，需要进一步清晰明确的界定土地生态质量的概念从而挖掘可以表征土地生态质量的参量及其对应的地理空间数据，同时对土地生态安全的阈值也要进一步研究[41]

# 5结论

本文以格网为评价单元，从土地生态系统的景观特征、生境质量抗干扰能力、生态系统服务价值、社会经济效益4个角度构建指标体系，借助空间自相关、冷热点分析、障碍度诊断等方法探索了黄河流域土地生态质量的空间分布规律。得出以下结论：

（1）黄河流域土地生态质量空间上呈中部及西南部较高、东南和东北部中等、西北质量较低态势，土地生态质量总体较低，临界安全及危险区域分别占 $3 1 . 4 \% . 2 7 . 7 \%$ 。安全及较安全区主要分布于研究区西南的黄河源、若尔盖-玛曲生态功能保护区、甘肃东部、鄂尔多斯南部、陕西北部、山西局部。临界安全区主要分布于流域东北部和东南部。危险区域主要分布于黄河流域西北部的青海、甘肃、宁夏境内。

(2）黄河流域土地生态质量的空间自相关程度高，热点主要分布于治理强度较高的黄土高原、毛乌素沙地生态保护区，冷点分布于流域西北部，应适当加强上游区域土地生态的治理，消除极端冷点。

（3）黄河流域土地生态质量主要障碍因子为经济密度、土地利用结构多样性、距生态保护区距离、距水域距离，应立足区域自然基础和资源禀赋状况，加快绿色创新驱动，将丰富的自然资源、生物资源和历史文化资源转化为市场价值，在生态修复和改造时，合理配置人工生态系统结构，必要时可增设自然保护区。

# 参考文献(References)

[1]傅伯杰.土地资源系统认知与国土生态安全格局[J].中国土地, 2019(12): 9-11.[Fu Bojie. The cognition of land resource system and the pattern of land ecological security[J]. China Land,2019 (12): 9-11.]   
[2] 于婧，陈艳红,彭婕,等.基于GIS 和Fragstats 的土地生态质量 综合评价—以湖北省仙桃市为例[J].生态学报,2020,40(9): 2932-2943.[Yu Jing,Chen Yanhong,Peng Jie,et al. Comprehensive evaluation on land ecological quality based on GIS and Fragstats:A case study in Xiantao City,Hubei Province[J].Acta Ecologica Sinica,2020,40(9): 2932-2943.]   
[3] 王根绪，程国栋,钱鞠.生态安全评价研究中的若干问题[J].应 用生态学报,2003,14(9):1551-1556.[Wang Genxu,Cheng Guodong,Qian Ju.Several problems in ecological security assessment research[J].Chinese Journal of Applied Ecology，2003,14 (9): 1551-1556.]   
[4] Thomsen M,Faber JH, Sorensen PB.Soil ecosystem health and services:Evaluation of ecological indicators susceptible to chemical stressors[J]. Ecological Indicators,2012,16: 67-75.   
[5] Villa F,McLeod H. Environmental vulnerability indicators for environmental planning and decision-making: Guidelines and applications[J].Environmental Management, 20O2,29(3): 335-348.   
[6] DeLange HJ, Sala S,Vighi M,etal.Ecological vulnerability in risk assessment:A review and perspectives[J]. Science of the Total Environment, 2010, 408(18): 3871-3879.   
[7]刘焱序,王仰麟,彭建,等.耦合恢复力的林区土地生态适宜性 评价—以吉林省汪清县为例[J].地理学报,2015,70(3):476- 487.[Liu Yanxu, Wang Yanglin,Peng Jian, et al. Land ecological suitability assessment for forest coupled with the resilience perspective: A case study in Wangqing County,Jilin Province, China [J]. Acta Geographica Sinica,2015,70(3): 476-487.]   
[8]史娜娜,全占军,韩煜,等.基于生态敏感性评价的乌海市土地 资源承载力分析[J].水土保持研究,2017,24(1):239-243.[Shi Nana, Quan Zhanjun,Han Yu,et al. Analysis of land resources carrying capacity in Wuhai City based on ecological sensitivity[J]. Research of Soil and Water Conservation,2017,24(1): 239-243.]   
[9]马世五,谢德体,张孝成,等.三峡库区生态敏感区土地生态安 全预警测度与时空演变——以重庆市万州区为例[J].生态学 报,2017,37(24): 8227-8240.[Ma Shiwu, Xie Deti, Zhang Xiaocheng,etal. Measures of land ecological securityearly warming and its spatial-temporal evolution in the ecologically sensitive area of the Three Gorges Reservoir area: A case study of Wanzhou District,ChongqingCity[J].ActaEcologica Sinica,2017,37(24): 8227-8240.]   
[10] 王一山,张飞,陈瑞,等.乌鲁木齐市土地生态安全综合评价[J]. 干旱区地理,2021,44(2): 427-440.[Wang Yishan, Zhang Fei, Chen Rui,et al. Comprehensive ecological security assessment: A case study of Urumqi City[J].Arid Land Geography,2021, 44(2): 427-440.]   
[11] 郑岚,张志斌,宣晓军,等.嘉峪关市土地生态安全动态评价及 影响因素分析[J].干旱区地理,2021,44(1):289-298.[Zheng Lan, Zhang Zhibin,Da Xiaojun,et al.Dynamic evaluation and influencing factors of land ecological security in Jiayuguan City[J]. Arid Land Geography,2021,44(1): 289-298.]   
[12] 吴景全,吴铭婉,臧传富.西北诸河流域土地利用变化及土地生 态安全评估[J].干旱区地理,2021,44(5):1471-1482.[Wu Jingquan, Wu Mingwan, Zang Chuanfu. Land use change and land ecological security assessment in the river basins of northwestern China[J].Arid Land Geography,2021,44(5): 1471-1482.]   
[13]Peng J,Liu Y,Li T,etal. Regional ecosystem health response to rural land use change: A case study in Lijiang City, China[J]. Ecological Indicators,2017,72:399-410.   
[14]吴滢滢,吴绍华,周生路,等.昆山市土地生态质量空间分异及 其对土地利用程度的响应[J].水土保持研究,2015,22(4):201- 205,209.[Wu Yingying,Wu Shaohua, Zhou Shenglu,et al.Distribution of land ecological environment and its response to landuse intensity in Kunshan County[J].Research of Soil and Water Conservation,2015,22(4): 201-205,209.]   
[15] 肖姚,朱凤武,周生路,等.经济发达地区影响土地生态质量的 关键景观格局因子研究——以江苏省昆山市为例[J].自然资 源学报,2017,32(10):1731-1743.[Xiao Yao,Zhu Fengwu, Zhou Shenglu,etal.Keylandscapepatternfactors affectingland ecological quality in developed areas: Acase study of Kunshan City in Jiangsu Province[J]. Journal of Natural Resources,2017,32(10): 1731-1743.]   
[16] 徐昌瑜,陈健,孟爱农,等.基于FRAGSTATS 的区域土地生态 质量综合评价研究——以江苏省宜兴市为例[J].土壤,2013, 45(2):1355-1360.[Xu Changyu, Chen Jian,Meng Ainong,et al. Study on evaluation of land ecological quality based on FRAGSTATS: Acase ofYixing,Jiangsu Province[J]. Sils,2013,45(2): 1355-1360. ]   
[17]Messing I, Fagerstrom M HH,Chen L D,et al. Criteria for land suitability evaluation in a small catchment on the Loess Plateau in China[J]. Catena,2003,54(1-2): 215-234.   
[18] 张军以,苏维词,张凤太.基于PSR模型的三峡库区生态经济区 土地生态安全评价[J].中国环境科学,2011,31(6):1039-1044. [Zhang Junyi, Su Weici, Zhang Fengtai. Regional land ecological security evaluation in the case of Chongqing Three Gorges Reservoir ecological economy area based on the PSR model[J]. China Environmental Science,2011,31(6): 1039-1044.]   
[19]Paracchini M L,Pacini C,Jones ML M,et al.An aggregation framework to link indicators associated with multifunctional land use to the stakeholder evaluation of policy options[J].Ecological Indicators,2011,11(1): 71-80.   
[20] 彭建,党威雄,刘焱序,等.景观生态风险评价研究进展与展望 [J].地理学报,2015,70(4):64-677.[Peng Jian,Dang Weixiong, Liu Yanxu, et al.Review on landscape ecological risk assessment [J]. Acta Geographica Sinica,2015,70(4): 664-677.]   
[21] 陆大道,孙东琪.黄河流域的综合治理与可持续发展[J].地理学 报,2019,74(12): 2431-2436.[Lu Dadao,Sun Dongqi.Development and management tasks of the Yellow River Basin: A preliminary understanding and suggestion[J]. Acta Geographica Sinica, 2019, 74(12): 2431-2436.]   
[22] 岳德鹏,王计平,刘永兵,等.GIS与RS 技术支持下的北京西北 地区景观格局优化[J].地理学报,2007,62(11):1223-1231. [Yue Depeng,Wang Jiping,Liu Yongbing, et al. Landscape pattern optimization based on RS and GIS in northwest of Beijing[J]. Acta Geographica Sinica,2007, 62(11): 1223-1231.]   
[23] 傅伯杰,刘焱序.系统认知土地资源的理论与方法[J].科学通 报,2019,64(21): 2172-2179.[Fu Bojie,Liu Yanxu. The theories and methods for systematically understanding land resource[J]. Chinese Science Bulletin,2019,64(21): 2172-2179.]   
[24] 马琳,刘浩,彭建,等.生态系统服务供给和需求研究进展[J].地 理学报,2017,72(7):1277-1289.[Ma Lin,Liu Hao,Peng Jian,et al.A review of ecosystem services supply and demand[J]. Acta Geographica Sinica,2017,72(7): 1277-1289.]   
[25] 陈利顶,傅伯杰.黄河三角洲地区人类活动对景观结构的影响 分析——以山东省东营市为例[J].生态学报,1996,16(4):337- 344.[Chen Liding,Fu Bojie.Analysis of impact of human activity on landscape structure in Yellow River Delta: A case study of Dongying region[J]. Acta Ecologica Sinica,1996,16(4): 337-344.]   
[26] 甘琳,陈颖彪,吴志峰,等.近20年粤港澳大湾区生态敏感性变 化[J].生态学杂志,2018,37(8):2453-2462.[Gan Lin,Chen Yingbiao,Wu Zhifeng,et al.The variation of ecological sensitivity

# 干吴区地理

in Guangdong-Hong Kong-Macao Greater Bay Area in recent 20 years[J]. Chinese Journal of Ecology,2018,37(8): 2453-2462.] [27] 谢高地,张彩霞,张昌顺,等.中国生态系统服务的价值[J].资源 科学,2015,37(9): 1740-1746.[Xie Gaodi, Zhang Caixia, Zhang Changshun, et al.The value of ecosystem services in China[J]. Resources Science,2015,37(9): 1740-1746.] [28] 巩杰,赵彩霞,谢余初,等.基于景观格局的甘肃白龙江流域生 态风险评价与管理[J].应用生态学报,2014,25(7):2041-2048. [Gong Jie,Zhao Caixia, Xie Yuchu,etal.Ecological risk assessment and its management of Bailongjiang watershed, southern Gansu based on landscape patern[J]. Chinese Journal of Applied Ecology,2014,25(7): 2041-2048.] [29] 周小平,冯宇晴,罗维,等.两种生态系统服务价值评估方法比 较研究——以四川省金堂县三星镇土地整治工程为例[J].生 态学报,2020,40(5):1799-1809.[Zhou Xiaoping,Feng Yuqing, Luo Wei,et al. Comparing two ecosystem service evaluation methods of the ecological benefits fromaland consolidationproject at a township level: A case study in Sanxing Town, Jintang County of Sichuan Province[J].Acta Ecologica Sinica,2020,40(5):1799-   
1809.] [30]李敏.基于土地利用变化的生态系统服务价值研究[D].合肥: 合肥工业大学,2015.[Li Min. Study on ecosystem services value based on land use change[D]. Hefei: Hefei University of Technology,2015.] [31] 徐少癸,左逸帆,章牧.基于模糊物元模型的中国旅游生态安全 评价及障碍因子诊断研究[J].地理科学,2021,41(1):33-43. [Xu Shaogui, Zuo Yifan,Zhang Mu.Evaluation of tourism ecological security and diagnosis of obstacle factors in China based on fuzzy object element model[J]. Scientia Geographica Sinica, 2021,   
41(1): 33-43.] [32] 纪学朋,黄贤金,陈逸,等.基于陆海统筹视角的国土空间开发 建设适宜性评价—以辽宁省为例[J].自然资源学报,2019,   
34(3): 451-463.[Ji Xuepeng,Huang Xianjin,Chen Yi,et al. Comprehensive suitability evaluation of spatial development and construction land in the perspective of land-ocean co-ordination: A case study of Liaoning Province,China[J]. Journal of Natural Resources,2019,34(3): 451-463.] [33] 杨开忠,苏悦,顾芸.新世纪以来黄河流域经济兴衰的原因初探 —基于偏离-份额分析法[J].经济地理,2021,41(1):10-20. [Yang Kaizhong,Su Yue,Gu Yun. Causes of economic rise and fall in the Yellow River Basin after 2Ooo: Based on the shift-share analysis method[J]. Economic Geography,2021,41(1): 10-20.] [34] 刘琳轲,梁流涛,高攀,等.黄河流域生态保护与高质量发展的 耦合关系及交互响应[J].自然资源学报,2021,36(1):176-195. [Liu Linke,Liang Liutao,Gao Pan,et al.Coupling relationship and interactive response between ecological protection and high quality development in the Yellow River Basin[J]. Journal of Natural Resources,2021,36(1): 176-195.] [35] 姚文艺,刘国彬.新时期黄河流域水土保持战略目标的转变与 发展对策[J].水土保持通报,2020,40(5):333-340.[Yao Wenyi, Liu Guobin. Strategic goal change and development countermeasures of soil and water conservation in Yellow River Basin in new period[J].Bulletin of Soil and Water Conservation,2020,40(5):   
333-340.] [36] 张振东,常军.2001—2018年黄河流域植被NPP的时空分异及 生态经济协调性分析[J].华中农业大学学报,2021,40(2):166-   
177.[Zhang Zhendong, Chang Jun. Spatial-temporal differentiation and eco-economic coordination of vegetation NPP in the Yellow River Basin from 2O01 to 2018[J]. Journal of Huazhong Agricultural University,2021,40(2): 166-177.] [37] 郭利刚,冯珍珍,刘庚,等.基于物元模型的汾河流域土地生态 安全评价[J].生态学杂志,2020,39(6):2061-2069.[Guo Ligang, Feng Zhenzhen,Liu Gen,et al.Evaluation of land eco-security in Fenhe River Basin based on matter-element model[J]. Chinese Journal of Ecology,2020,39(6): 2061-2069.] [38] 任保平,杜宇翔.黄河流域经济增长-产业发展-生态环境的耦 合协同关系[J].中国人口·资源与环境,2021,31(2):119-129. [Ren Baoping,Du Yuxiang. Coupling coordination of economic growth,industrial development and ecology in the Yellw River Basin[J]. China Population,Resources and Environment,2021,31 (2): 119-129.] [39] 王思远,王光谦,陈志祥.黄河流域生态环境综合评价及其演变 [J].山地学报,2004,22(2):133-139.[Wang Siyuan,Wang Guangqian, Chen Zhixiang. Eco-environmental evaluation and changes in Yellow River Basin[J]. Mountain Research,2004,22(2):133-139.] [40] 李达,林龙圳,林震,等.黄河流域生态保护和高质量发展的 EKC 检验[J].生态学报,2021,41(10):3965-3974.[Li Da,Lin Longzhen, Lin Zhen,et al.EKC test of ecological protection and high-quality development in the Yellow River Basin[J].Acta Ecologica Sinica,2021,41(10): 3965-3974.] [41] 熊建华.土地生态安全评价研究回顾、难点与思考[J].地理与地 理信息科学,2018,34(6): 71-76.[Xiong Jianhua.Review,difficulties adthikingoflndcologicalsecurityevaluationJ]. G raphy and Geo-Information Science,2018,34(6): 71-76.]

# Comprehensive evaluation of land ecological quality in the Yellow River Basin based on Grid-GIS

AO Yong1²， JIANG Lingfeng²， BAI Zhaodi’， YANG Xiao³， ZHANG Leyi³ (1.SchoolofLandEngineering,Chang'anUniversity,Xi'an70o54,Shaanxi,China;2.Shaanxi KeyLaboratoryofLand Consolidation,Xi'n7Oo4,Shaanxi,China;3.SholofEarth ScienceandResource,Chang'an University,Xi'an7054, Shaanxi, China)

Abstract: The Yelow River Basin plays a key role in China’s social and economic development and the construction of ecological security patterns.The high-quality development of this basin has become a major national strategy. Assessing the land ecological quality objectivelyand quantitatively is crucial for comprehensive land management and policymaking in Yellow River Basin.To understand the land ecological qualityof Yelow River Basin and its spatial variation characteristics in 2O18,four factors were chosen to construct a comprehensive evaluation model ofthe ecological quality of land: landscape patern properties of land ecosystem, the anti-interference ability of habitat, ecosystem service value,and socioeconomic benefits.Improved entropy was used as an indicator of weight,and spatial autocorrelation,hot and cold spot analysis,and obstacle diagnosis model were used to explore the spatial characteristics of the land ecological quality.In this study,we take the landscape pattern properties of land ecosystem and ecosystem service value into consideration and use $8 ~ \mathrm { k m }$ rasters as the evaluation unit to obtain more accurate results than the traditional administrative evaluation units. Results show the following: (1） The land ecological quality of Yellow River Basin is spatially expressed as “northwest low and middle part high,moderate in the southeast and northeast".The overall land ecological quality is relatively low,and four safety grades from dangerous,critical safety,sub-safe,to safe accounted for $2 7 . 7 \%$ $3 1 . 4 \%$ $2 8 . 5 \%$ ,and $12 . 4 \%$ of the total area, respectively. (2) The land ecological quality passed significant tests and showed a positive autocorrelation with a strong clustering pattern.The hot spots are mainly distributed in the Loess Plateau and Maowusu Ecological Reserve with strong ecological protection measures,and the cold spots are distributed in the northwest Yellow River Basin (the upper reaches),especially in southeast Qinghai, north Ningxia,and central Gansu.Therefore,the management of land ecology in the upper reaches should be properly strengthened to eliminate extreme cold points.(3)The main obstacles to the ecological qualityof land in Yellow River Basin were economic density,diversity of land use structure,proximity to ecological protection area,and proximity to water. The government should focus on regional natural resources, encourage green innovation,convert rich natural resources,biological resources,historical and cultural resources into economic value,rationall allcate artificial ecosystems’ structure during ecological restoration and transformation,and add nature reserves when necessary.

Key words: Fragstats； Grid-GIS； land ecological quality； Yellow River Basin