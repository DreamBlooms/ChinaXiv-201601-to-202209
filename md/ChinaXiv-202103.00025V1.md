# 基于多源地理数据融合的黑河中游土地多功能性时空格局与权衡研究

程浩然¹，蒙吉军¹，朱利凯²(1.北京大学城市与环境学院,地表过程分析与模拟教育部重点实验室,北京100871;2.临沂大学资源环境学院，山东 临沂276000)

摘要：土地多功能利用是提高土地利用效率、缓解人地矛盾、促进区域可持续发展的重要途径。研究构建了“生产-生活-生态”功能的土地多功能性评价指标体系，基于 $3 \mathrm { k m } \times 3 \mathrm { k m }$ 格网，融合了遥感、统计、POI等多源地理数据，利用投影寻踪模型对黑河中游土地多功能性进行评价，通过变量相关分析和双变量局部空间自相关分析，揭示了土地多功能权衡与协同关系，并采用RGB三通道合成与二阶聚类分析相结合进行土地功能分区。结果表明：(1)黑河中游在不同利用方式下呈现不同功能，在走廊平原区土地功能以生产功能为主导，生活功能和生态功能为辅。生产功能在走廊绿洲农业区优势明显，生活功能高值区集中于城镇等基础设施条件较好的地区，祁连山、龙首山发挥着生态屏障作用。(2)研究时段内，土地多功能性稳中增强。土地多功能性与一级功能的空间格局保持稳定，土地功能间协调性普遍增强，不同功能在空间上日益重叠。(3)按照主导利用方向，土地可划分为以农业生产与城镇空间为主体的重点开发区、优化开发区和适度开发区，以及以生态空间为主的生态屏障区、生态缓冲区和生态修复区。(4)土地多功能利用仍有提升空间，尤其要加强对非主导功能的关注，协调功能间的固有矛盾；统筹推进生态修复，关注自然资本增值，从构建区域绿水青山的格局挖掘土地价值新的增长点。

关 键 词：土地多功能性；多源地理数据；时空格局；权衡与协同；功能分区；黑河中游

# 文章编号：

土地利用是人类为获取所需产品或服务而进行的有目的的、主观能动的土地资源开发、利用方式[1]。各种土地利用方式为人类提供产品或服务的能力便是土地利用功能[2]。随着城市化进程的不断推进和人口数量的持续增长，人类的消费需求不断增加，对土地不断提出新的要求，向土地索取新的产品或服务[3],尤其是随着可利用土地资源愈益稀缺,土地的多元化利用成为必然[4]。由于土地多功能性研究能够为度量土地功能多元化提供的产品、服务及其环境效应提供帮助，能够有效提高土地利用效率5，因此也成为缓解人地矛盾、助推乡村振兴、促进区域可持续发展的重要途径[6-7]

“多功能性”的概念在农业功能多元化研究中被首先提出[8]。20世纪80年代末，日本的"稻米文化”中最先出现“农业多功能性"概念；2001年经济合作与发展组织(OECD)进一步定义了农业多功能性概念并提出了分析框架[9]。结合多功能性的概念，基于生态系统服务和景观功能，并考虑可持续性的经济、社会和环境三大维度之间的平衡，欧盟第六框架项目“可持续性影响评估：欧洲多功能土地利用的环境、社会、经济效应"(SENSOR)在2004年正式提出了土地利用多功能性概念[]。在此基础上，不同学者从不同角度对土地多功能进行识别与分类[12],如从“生产-生态-社会"[4]；“生产-空间-生态-社会保障”[13]；"生产-生活-生态-空间-文化"等[4]维度进行分类和评价。不同土地功能之间常表现为此消彼长的权衡、相互增益的协同等形式[15]。土地系统某种功能的提升常常以牺牲其他功能为代价[16],对权衡与协同关系的研究有助于准确分析比较土地功能之间的关系[]，进而提高人类福祉[18]。近年来，人们采用统计学方法[19]、空间分析方法[20-21]、情景模拟方法[22]和生态系统服务流动性分析等方法进行了土地系统功能之间权衡与协同的研究[23-25]

黑河中游是黑河流域人类活动最密集、绿洲最集中、经济最发达的地区，集中了全流域 $8 0 \%$ 以上的人工绿洲、 $9 5 \%$ 的耕地、 $9 2 \%$ 的人口和 $8 3 \%$ 的$\mathrm { G D P } ^ { [ 2 6 ] }$ 。但是,黑河中游生态系统非常脆弱敏感,不合理的土地利用方式极易引起生态系统破坏，并导致土地盐碱化、沙漠化[27]等一系列生态环境问题[28]。随着黑河中游人口数量的增加和城镇化进程的加快，大量农用地被转换为建设用地，绿洲周边的荒地又被开垦为农田。严重超载的人口、快速发展的经济与原本脆弱的生态环境和有限的自然资源之间的矛盾日渐突出。因此，深入挖掘土地利用的多功能性，是协调用地矛盾、实现土地资源持续利用的关键。梳理已有研究可以发现：(1)数据来源多限于社会经济统计数据与土地利用数据，鲜有采用POI等现势性较强的数据以反映人类社会经济活动信息。(2)评价尺度多基于行政区划单元，难以准确刻画土地功能的具体空间分布。(3)权衡与协同多关注于耕地多功能性，缺少对土地系统多功能性的研究。本研究基于格网尺度，集成多源地理数据，揭示黑河中游土地多功能性时空格局及权衡与协同关系，旨在深入挖掘土地利用多功能性，协调用地矛盾、实现区域土地资源持续利用。

# 1研究区概况与数据来源

# 1.1 研究区概况

黑河是中国第二大内陆水系，发源于祁连山中段北坡，流经河西走廊中部，尾闾消失于额济纳旗的东、西居延海。莺落峡至正义峡之间为中游，位于河西走廊中段，流域总面积约为 $1 . 9 6 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 。黑河中游地貌大体可分为高山、中低山和走廊平原三大类，地势南高北低，东部略高于西部，中部为绿洲、戈壁相间分布的走廊平原(图1)。区内属温带大陆性干旱气候，全年蒸发量高达 $1 7 0 0 \mathrm { m m }$ ，但年降水量仅 $5 4 . 9 { \sim } 4 3 6 . 2 ~ \mathrm { m m }$ ，且年内分布很不均匀，大部分地区的农业生产依赖于人工灌溉[29]。长期以来，黑河中游一直是一个传统的农业绿洲，但随着国家产业布局及经济发展战略的改变，其三次产业比例经历了从1949年的58.06:3.23:38.71到1978年的48.41:18.84:31.75，再到2018年的21.9:22.3:55.8的转变，表现出由传统的耕作农业向综合型产业转变的趋势。相应地，区域土地利用功能亦呈现如下变化特点：从农牧业生产的单一生产方式向工业和第三产业用地不断增大的多功能利用转变、从注重生产功能向重视"生产、生活、生态"三维一体功能转变[30]

![](images/2926647bf5f534565b58192a363572057598d1916479bb7419796a105b1b22da.jpg)  
图1黑河中游区位概况  
Fig.1Geographical location of the middle reaches of the Heihe River

# 1.2数据来源

研究采用的行政区划、道路、水系数据来自寒区旱区科学数据中心（http://westdc.westgis.ac.cn/）;DEM数据来自地理空间数据云(http://www.gscloud.$\mathrm { c n / }$ );土地利用数据来自FROM-GLC数据集(http://data.ess.tsinghua.edu.cn/)；土壤侵蚀强度数据(2005年，空间分辨率 $1 \mathrm { k m }$ 、人口公里格网数据(2015年，空间分辨率 $1 ~ \mathrm { k m }$ )来自资源环境数据云平台(http://www.resdc.cn/Default.aspx）;夜间灯光数据(2013年和2016年)来自美国国家海洋和大气管理局国家环境信息中心（https://www.ngdc.noaa.gov/eog/index.ht-ml);社会经济统计数据来自张掖市各区县统计年鉴(2013年和2016年)和中国知网甘肃省经济社会发展统计数据库（http://data.cnki.net/area/home/in-dex/D28);互联网地图兴趣点(Pointofinterest,POI)数据(2013年和2016年，包括交通、生活、医疗设施等）通过应用程序编程接口（Application programming interface,API)从百度地图开放平台(http://lb-syun.baidu.com/)获取，经过去重、随机核验、矢量化等预处理，形成点数据图层。

# 2 研究方法

# 2.1土地多功能性评价

2.1.1指标体系的构建借鉴“三生空间"的划分，本文将土地功能划分为生产功能、生活功能和生态功能3个维度。其中，生产功能指土地支持产品生产、经济持续发展的能力;生活功能指土地支持人类就业、提供社会保障和居住家园的能力；生态功能指土地维持生态系统稳定、提供高质量生态环境的能力。结合黑河中游产业结构、生活水平以及突出生态问题等，在一级功能下划分出了农业生产、经济生产、交通运输、就业支持、居住家园、健康保障、生态维持、减轻污染8项二级功能。考虑到指标与土地功能间通常存在多维对应的复杂关系，依据系统性、主导性、简洁性和可操作性原则，选取了14个指标(表1)。

2.1.2指标的空间化与标准化由于采用的社会经济统计数据基于乡镇级行政单元，为揭示其内部的空间异质性，并能与自然环境数据融合，研究中分别采用土地利用、夜间灯光、人口公里格网等高空间分辨率的地理代理数据对农业生产 $( X _ { 1 } , X _ { 2 } , X _ { 3 } )$ ）减轻污染 $( X _ { 1 4 } )$ 、经济生产 $( X _ { 4 } )$ 和就业支持 $( X _ { 6 } , X _ { 7 }$ 、$X _ { 8 }$ )数据进行了空间离散化处理，从而获得 $3  { \mathrm { \ k m } } \times 3$ $\mathrm { k m }$ 格网尺度的指标值。

对于交通 $( X _ { 5 } )$ 、生活 $\left( { { X } _ { 9 } } \right)$ 、医疗设施 $( X _ { 1 1 } )$ 兴趣点数据，本文运用核密度估计方法进行空间化处理（图2)。核密度估计是一种能够将点数据转换为连续密度场的非参数方法[31]。以设施点 $i$ 为中心， $h$ 为带宽，随着与设施点距离的增大，密度值逐渐减小，并在距离为 $h$ 处衰减为0，计算公式如下：

$$
f ( x , y ) { = } \frac { 1 } { h ^ { 2 } } { \sum _ { i = 1 } ^ { n } K \bigg ( } \frac { d _ { i } } { h } { \bigg ) }
$$

式中： $f ( x , y )$ 为 $( x , y )$ 位置上的核密度估计值; $h$ 为带宽,根据多次试验和经验判断,本文设为 $1 0 \mathrm { k m } ; n$ 为与 $( x , y )$ 位置的距离小于或等于带宽的设施点数量； $d _ { i }$ 为 $( x , y )$ 位置与第 $i$ 个设施点的距离; $K ( x )$ 为核函数，决定距离衰减的幅度，本文以Silverman提出的4次核函数为基础，公式如下：

$$
K ( x ) = \left\{ { \begin{array} { l } { { \frac { 3 } { \pi } } { \big ( } 1 - x ^ { 2 } { \big ) } ^ { 2 } } \\ { 0 , \qquad { \stackrel { \mathrm { H } } { \ne } } 1 \dag \mathbf { \underline { { t } } } } \end{array} } , x \in [ - 1 , 1 ] \right.
$$

此外，土壤侵蚀强度 $( X _ { 1 2 } )$ 取格网内各栅格土壤侵蚀强度的平均值；林地面积比例 $( X _ { 1 3 } )$ 为格网中林地面积占比；自来水受益户数比 $\left( { { X } _ { 1 0 } } \right)$ 将乡镇统计数据与格网叠置获得。

根据指标对评价结果的作用方向，分别进行了越大越优型和越小越优型极值标准化处理

2.1.3基于加速遗传算法的投影寻踪模型投影寻踪模型是一种直接由样本数据驱动的探索性数据分析模型，适合分析非线性、非正态高维数据。其原理是将 $n$ 维指标数据 $\left\{ \left. x _ { i j } \right| j = 1 , 2 , \cdots , n \right\}$ 综合成以$a = \left\{ a _ { 1 } , a _ { 2 } , \cdots , a _ { n } \right\}$ 为投影方向的综合评价得分 $Z _ { i }$

表1黑河中游土地多功能性评价指标体系  
Tab.1 Evaluation index system of land multi-function of the study area   

<html><body><table><tr><td>目标层</td><td>准则层</td><td>指标层(作用方向)</td><td>数据层</td><td>2013年权重</td><td>2016年权重</td></tr><tr><td>生产功能</td><td>农业生产</td><td>第一产业增加值X (+)</td><td>第一产业增加值总额/10元</td><td>0.1383</td><td>0.1526</td></tr><tr><td></td><td></td><td>猪牛羊肉产量X (+)</td><td>猪牛羊肉总产量/10kg</td><td>0.0651</td><td>0.0690</td></tr><tr><td></td><td></td><td>有效灌溉面积X (+)</td><td>有效灌溉面积/hm</td><td>0.1526</td><td>0.1592</td></tr><tr><td></td><td>经济生产</td><td>第二三产业增加值X4(+)</td><td>第二三产业增加值总额/10元</td><td>0.0785</td><td>0.0703</td></tr><tr><td></td><td>交通运输</td><td>交通设施密度X (+)</td><td>百度地图交通设施POI</td><td>0.1563</td><td>0.1739</td></tr><tr><td>生活功能</td><td>就业支持</td><td>城镇居民可支配收入X(+)</td><td>城镇居民可支配收人总额/元</td><td>0.0505</td><td>0.0613</td></tr><tr><td></td><td></td><td>农村居民可支配收入X(+)</td><td>农村居民可支配收入总额/元</td><td>0.0697</td><td>0.0528</td></tr><tr><td></td><td></td><td>第二三产业从业人员规模X(+)</td><td>第二三产业从业人员总数/人</td><td>0.0301</td><td>0.0524</td></tr><tr><td></td><td>居住家园</td><td>生活设施密度X (+)</td><td>百度地图生活设施POI</td><td>0.0632</td><td>0.0626</td></tr><tr><td></td><td></td><td>自来水受益户数比X10 (+)</td><td>自来水受益户数/总户数</td><td>0.0532</td><td>0.0668</td></tr><tr><td></td><td>健康保障</td><td>医疗设施密度X (+)</td><td>百度地图医疗设施POI</td><td>0.0507</td><td>0.0215</td></tr><tr><td>生态功能</td><td>生态维持</td><td>土壤侵蚀强度Xi2（-)</td><td>土壤侵蚀强度</td><td>0.0235</td><td>0.0197</td></tr><tr><td></td><td></td><td>林地面积比例Xi3 (+)</td><td>林地面积/土地总面积</td><td>0.0365</td><td>0.0226</td></tr><tr><td></td><td>减轻污染</td><td>化肥施用强度Xi4（-)</td><td>化肥施用实物量/t</td><td>0.0318</td><td>0.0154</td></tr></table></body></html>

![](images/acf97cd7c475484b22c41e8838ab1c29a5d0ddae66433dc0e076a9ef9a043e56.jpg)  
图2黑河中游交通设施、生活设施和医疗设施空间化处理结果  
Fig.2Spatialization results of transportation,living and medical facilities in the study are

$$
z _ { i } = \sum _ { j = 1 } ^ { n } a _ { j } x _ { i j } \ \left( i = 1 , 2 , \cdots , k \right)
$$

投影时，要使局部投影点尽可能密集，而整体上投影点团间要尽可能离散。因此，投影目标函数可构造为：

$$
Q ( a ) = S _ { \scriptscriptstyle z } D _ { \scriptscriptstyle z }
$$

式中： $S _ { z }$ 为投影值 $Z _ { i }$ 的标准差； $D _ { z }$ 为 $Z _ { i }$ 的局部密度值。计算公式如下：

$$
S _ { z } = { \sqrt { \frac { \displaystyle \sum _ { i = 1 } ^ { k } ( z _ { i } - E ( z ) ) ^ { 2 } } { k - 1 } } }
$$

$$
D _ { z } = \sum _ { i = 1 } ^ { k } \sum _ { h = 1 } ^ { k } ( R - r _ { i h } ) \times u ( R - r _ { i h } )
$$

式中： $E ( z )$ 为 $\left\{ z _ { i } | i = 1 , 2 , \cdots , k \right\}$ 的平均值; $R$ 为局部密度的窗口半径,取 $0 . 1 S _ { z } \ ; \ r _ { i h } = \vert z _ { i } - z _ { h } \vert$ 为样本间的距离； $u ( t )$ 为单位阶跃函数，当 $t { \geq } 0$ 时， $u ( t ) { = } 1$ ,当 $t < 0$ 时，其值取0。

样本数据集确定后，目标函数 $Q ( a )$ 只随着投影方向 $a = \{ a _ { 1 } , a _ { 2 } , \cdots , a _ { n } \}$ 而改变。最佳投影方向是能最大程度暴露高维数据结构特征的投影方向，可通过求解投影目标函数最大值来寻找：

$$
\mathrm { a x } \colon Q ( a ) = S _ { z } D _ { z }
$$

约束条件：

$$
\mathrm { s . t . } \sum _ { j = 1 } ^ { n } { a _ { j } } ^ { 2 } = 1
$$

基于实数编码的加速遗传算法能够进行持续有效的全局搜索[32],对于寻找最佳投影方向有较好效果。本研究在Matlab环境下，设置父代初始种群规模 $n { = } 4 0 0$ ,交叉概率 $p _ { c } { = } 0 . 8 0$ ,变异概率 $p _ { m } { = } 0 . 8 0$ ，优秀个体数目为20个， $\scriptstyle { a = 0 . 0 5 }$ ，迭代2次后进入加速循环，加速次数为20次。

将得到的最佳投影方向向量线性调整至总和为1后，作为对应指标的权重(表1)，代入公式(3)，即得到土地多功能性综合得分。

# 2.2土地多功能权衡与协同

2.2.1变量相关分析变量相关分析可以提供变量之间相互关系的量化指标，直观反映变量之间的权衡与协同关系。Spearman秩次相关系数分析属于非参数方法，更适合常具有非线性和非正态特征的

# 干吴区地理

地理数据[33]。本文利用 SPSS 24软件中的Spearman相关分析功能进行变量相关分析。

2.2.2双变量局部空间自相关分析局部空间自相关能够测度各空间位置与邻近位置同一属性值的相关性[34],揭示空间局部不平稳性，更准确地体现地理要素在局部空间上的分布特征[35]。本文采用Anselin提出的双变量空间自相关以测度多个属性之间的空间相关性[36]

2.2.3二阶聚类分析聚类分析能够揭示数据集中的自然分组，识别土地功能的组合模式，为综合分区提供辅助支撑[37]。二阶聚类分析法可以同时处理连续变量与分类变量，适合多类型数据融合的分析。本文使用SPSS24软件中的二阶聚类功能，以海拔高度、土地一级功能评价值、一级功能冷热点类型、一级功能权衡与协同类型作为输入变量，对格网单元进行聚类分区。

# 3 结果与分析

# 3.1土地多功能性时空特征

从图3a可以看出，生产功能是黑河中游土地的主导功能，从2013年至2016年，生产功能从 $4 4 . 1 1 \%$ 上升至 $5 7 . 5 4 \%$ ;生活功能处于次要位置（占 $2 0 \%$ 左右），且变化不大；生态功能下降较大，贡献率从$3 8 . 8 4 \%$ 下降到 $2 5 . 1 2 \%$ ○

自然断裂法是Jenks提出的一种地图分级算法，依据组内方差最小，组间方差最大的原则，利用数据自身的结构特征对其进行聚类分级[38]。据此，本文将研究区土地多功能性综合得分划为5级，分级阀值如表2。结果显示(图3b)，黑河中游土地多功能性以低和较低的格网占绝对比例（ $7 7 \%$ \~$8 2 . 9 \%$ )，高和较高的格网只占 $1 0 \%$ 左右；从2013年至2016年，低和较低的格网有所减少 $( 5 . 8 9 \% )$ ，而中等、较高和高的格网有所增加。

从图4可以看出，黑河中游土地多功能性存在明显的空间异质性。利用Getis-OrdGi\*指数来判断局部位置上是否存在显著的高值或低值集聚。在给定的显著性水平下，若该指数为正，且通过了显著性检验，则表明该区域存在高值集聚现象，即判定为热点区；同理，若指数为负且显著，则判定为冷点区[39]。冷热点分析识别出走廊平原的高台县、临泽县、甘州区和民乐县等传统绿洲农业区为高值集聚区，西北部沙漠、戈壁地区与祁连山、龙首山地区为低值集聚区。从2013年至2016年，山丹、民乐2县中部和山丹马场的土地多功能性增强，甘州、临泽、高台3县组团与民乐县的高值集聚区连接成为贯穿走廊的土地多功能性高值带；但高台县西南部土地多功能性减弱。

3.1.1生产功能如图5所示，生产功能高值区主要出现在甘州、临泽、高台3县区中部，沿走廊绿洲农业区分布，并形成了高值集聚区；生产功能中等地区主要出现在山丹县和民乐县内主要道路附近;低值区主要出现在沙漠、戈壁以及祁连山、龙首山地区，形成了显著的低值集聚区，反映出自然条件和生态保护政策等对土地资源开发的限制。从2013年至2016年，山丹、民乐2县中部生产功能增强，高台县西南部生产功能减弱；生产功能高值集聚区由3块组团连接成为一个整体。

3.1.2生活功能由图6看出，生活功能高值区主要分布在甘州区中部以及高台、临泽、山丹、民乐4

![](images/1cbb52dbf44e7944b41f4b9b30ce66832f69d2bbced38c5d503f8fab17f49a34.jpg)  
图3黑河中游土地多功能性组成和等级结构

Fig.3Composition and grade structures of land multi-function in the middle reaches of the Heihe River

# 表2自然断裂法分级阈值

Tab.2 Classification thresholds ofthe naturalbreakpointmethod   

<html><body><table><tr><td>年份</td><td>低</td><td>较低</td><td>中等</td><td>较高</td><td>高</td></tr><tr><td>2013</td><td>0.3248</td><td>0.5959</td><td>0.9710</td><td>1.4776</td><td>2.3398</td></tr><tr><td>2016</td><td>0.2510</td><td>0.5165</td><td>0.8753</td><td>1.3148</td><td>1.9034</td></tr></table></body></html>

县的政府驻地附近，其中甘州区大部以及临泽、民乐、高台3县中部形成了高值集聚区;生活功能低值区主要分布在西北部以及祁连山、龙首山地区，并形成了低值集聚区。从2013年至2016年，各区县政府驻地附近生活功能增强明显，高值区范围扩大；其他地区变化不明显

3.1.3生态功能由图7看出，生态功能高值区主要出现在祁连山山麓、山丹马场以及龙首山山麓地区，并形成了高值集聚区，反映出祁连山、龙首山的生态屏障作用；低值区主要出现在西北部的沙漠、

![](images/e9ffe28db7a1696967f2635327490147f8cae6d28721c6ab124dfb0d3c9f868d.jpg)  
Fig.4Assessment result ofland multi-function and hotspot distributions in the middle reachesofthe Heihe River

![](images/3405d7feed6e4fedb78d03a76ca61e21882f0ef3eb8828e0aa6200bd4e1cc669.jpg)  
图4黑河中游2013和2016年土地多功能性综合得分及冷热点分布  
图5黑河中游2013和2016年土地生产功能评价结果及冷热点分布

![](images/47fc739e7bdaf2c8d5ced5d0defc327075fee39ebd87a8a80e11b1f0adab9b42.jpg)  
Fig.5Assessment result ofproduction functionand hot spot distributions in the middle reaches ofthe Heihe River   
图6黑河中游2013和2016年土地生活功能评价结果及冷热点分布

Fig.6Assessment result of living function and hot spot distributions in the middle reaches ofthe Heihe River

![](images/54b2f3c79caa8ef0e7f9d2cce6dc49f0d54943bac611fe997ecfa03364c3eb5a.jpg)  
干旱区地理  
图7黑河中游2013和2016年土地生态功能评价结果及冷热点分布

Fig.7Assessment result of ecological function and hot spot distributions in the middle reaches of the Heihe Rive戈壁地区以及临泽、高台的绿洲农业区，形成了显著的低值集聚区。从2013年至2016年，甘州区中部生态功能增强，龙首山山麓地带高值集聚区扩大；生态功能减弱区主要出现在民乐、山丹2县中部，其中民乐县中部出现了大片低值集聚区，主要原因是化肥大量施用造成的面源污染。

# 3.2土地多功能权衡与协同关系

3.2.1 权衡与协同全局特征黑河中游土地一级功能间的Spearman相关系数如表3。可以看出，生产功能与生活功能间存在显著的协同关系，且随时间的推移关系增强，反映出生产功能与生活功能整体上的协调性增强；生态功能与生产功能、生活功能之间的权衡关系随着时间的推移而增强，在全局上反映出生产、生活功能导向的土地开发利用活动对生态环境的挤占呈加剧趋势。

土地二级功能间的Spearman相关系数如表4。生产功能、生活功能的二级功能间均存在显著的协同关系，显示出这些功能在空间上相互重叠、协同发展的特征。随着时间的推移，大部分功能间的协

# 表3黑河中游土地一级功能间Spearman相关系数

Tab.3 Spearman correlation coefficients between primary land functions in the middle reaches of the Heihe River   

<html><body><table><tr><td rowspan="2">2013年</td><td colspan="3">2016年</td></tr><tr><td>生产功能</td><td>生活功能</td><td>生态功能</td></tr><tr><td>生产功能</td><td>1</td><td>0.647**</td><td>-0.123**</td></tr><tr><td>生活功能</td><td>0.565**</td><td>1</td><td>-0.241**</td></tr><tr><td>生态功能</td><td>-0.053**</td><td>-0.221**</td><td>二</td></tr></table></body></html>

注：\*\*表示在0.01水平上显著，\*表示在0.05水平上显著，下同。

同关系增强，反映出传统农业生产空间中发展出了日益增强的交通、就业等功能。生态维持功能同农业生产、经济生产、就业支持、健康保障之间存在显著的协同关系，反映出后4项功能在空间上对于良好生态环境的偏好。减轻污染与所有二级功能间均存在显著的权衡关系，且强度大都增强，反映出生态环境面临着越来越大的压力。

3.2.2权衡与协同局部特征通过双变量局部空间自相关分析得到土地一级功能间权衡与协同格局（图8)。2013年与2016年，黑河中游土地一级功能间的权衡与协同格局相似，权衡与协同的热点区域出现在以下3类地区。

表4黑河中游土地二级功能间Spearman相关系数  
Tab.4Spearman correlation coeficients between secondaryland functions in the middle reachesof the Heihe River   

<html><body><table><tr><td rowspan="3" colspan="2">2013年</td><td colspan="8">2016年</td></tr><tr><td colspan="3">生产功能</td><td colspan="3">生活功能</td><td colspan="2">生态功能</td></tr><tr><td>农业生产</td><td>经济生产</td><td>交通运输</td><td>居住家园</td><td>就业支持</td><td>健康保障</td><td>生态维持</td><td>减轻污染</td></tr><tr><td>生产功能</td><td>农业生产</td><td>1</td><td>0.466**</td><td>0.611**</td><td>0.606**</td><td>0.623**</td><td>0.695**</td><td>0.338**</td><td>-0.907**</td></tr><tr><td></td><td>经济生产</td><td>0.446**</td><td>1</td><td>0.555**</td><td>0.466**</td><td>0.421**</td><td>0.524**</td><td>0.056**</td><td>-0.418**</td></tr><tr><td>生活功能</td><td>交通运输</td><td>0.481**</td><td>0.526**</td><td>1</td><td>0.564**</td><td>0.518**</td><td>0.797**</td><td>0.033</td><td>-0.626**</td></tr><tr><td></td><td>居住家园</td><td>0.520**</td><td>0.480**</td><td>0.504**</td><td>1</td><td>0.964**</td><td>0.695**</td><td>0.031</td><td>-0.564**</td></tr><tr><td></td><td>就业支持</td><td>0.542**</td><td>0.429**</td><td>0.477**</td><td>0.970**</td><td>1</td><td>0.643**</td><td>0.072**</td><td>-0.559**</td></tr><tr><td></td><td>健康保障</td><td>0.555**</td><td>0.549**</td><td>0.748**</td><td>0.569**</td><td>0.539**</td><td>一</td><td>0.108**</td><td>-0.698**</td></tr><tr><td>生态功能</td><td>生态维持</td><td>0.388**</td><td>0.052*</td><td>0.013</td><td>0.043°</td><td>0.075**</td><td>0.109**</td><td>1</td><td>-0.256**</td></tr><tr><td></td><td>减轻污染</td><td>-0.964**</td><td>-0.429**</td><td>-0.496**</td><td>-0.504**</td><td>-0.524**</td><td>-0.569**</td><td>-0.316**</td><td>二</td></tr></table></body></html>

![](images/96a248c5022a8179dc73908b8eb9ae666a611d291e3d69c1f7a1a29dba2ab575.jpg)  
图8黑河中游土地一级功能间双变量LISA聚类图  
Fig.8Bivariate LISA cluster map among primary land functions in the middle reaches of the Heihe River

（1）绿洲农业区。黑河水系周围的灌溉绿洲农业区普遍存在“高生产-高生活"的协同关系，反映出干旱区农业绿洲“逐水草而居"的最基本的人地关系特征，各级聚落呈点状分布于各大绿洲中，生产水平与生活质量呈现相互增益的特征。但在高台、临泽、民乐的部分绿洲农业区，也存在"高生产-低生态"的权衡关系；2016年民乐县的权衡区几乎覆盖县内全部绿洲。这些权衡关系反映出人们为追求生产功能的提升而挤占了生态功能

(2)祁连山、龙首山地区。如肃南县马蹄乡、民乐县南部、山丹马场、山丹县北部等地存在“低生产-低生活-高生态"的权衡关系，反映出在地形、气候等自然因素和生态保育等政策的影响下，该区农业生产适宜性较差、生活功能受到很大限制，而更适宜于生态功能的发挥，作为整个流域的生态安全屏障应给予保护。

(3）戈壁和荒漠地区。如肃南县明花乡、高台县、临泽县、甘州区北部等地呈现出“低生产-低生活-低生态"的共变关系。在这些生态脆弱的荒漠戈壁区，由于资源环境承载力非常低下，因而在国土空间规划中，应以生态抚育为重点，减少人类社会经济活动干扰，增强其生态功能。

3.2.3土地功能分区采用RGB三通道合成显示黑河中游土地各一级功能对土地多功能的贡献(2016年），获得黑河中游土地主导功能空间格局（图9a）。在此基础上，结合二阶聚类分析结果（图9b)，最终将黑河中游土地功能区分为2大类6小类（图9c）。

重点开发区、优化开发区、适度开发区体现出干旱区农业绿洲生产功能与生活功能相互交织的典型特征，成为黑河中游农业生产与城镇空间的主体。

（1）重点开发区，主要位于甘州区中、南部和高台、民乐县城附近，地势平坦，水资源较丰富，交通条件较好，人口密集，生产功能与生活功能高度发达，且对生态环境的负面影响较小，适宜继续承担黑河中游较强密度的经济社会活动，但应严格限制高污染、高耗水产业的发展。

![](images/fe80d8bc2b6788e6d948fc6c10ae1446f6ffbd6decaf0a0b1c6d17f0300d9c58.jpg)  
干辛区地理  
图9黑河中游土地主导功能、二阶聚类结果与土地功能分区  
'ig.9Dominant function,result of two-step clustering and land functional zoning inthe middle reaches ofthe Heihe

(2）优化开发区，主要位于民乐县、临泽县、高台县的绿洲农业区，区位条件相对较好，主要是传统的农业绿洲，但生产活动对生态功能造成了较大的影响。今后应适当控制农药、化肥施用量，减少面源污染，保护生态功能；同时可以发展中草药种植等高附加值产业，向依靠知识、管理和地区特色的生产方式转变。

(3）适度开发区，主要位于绿洲边缘向荒漠过渡的地区，水资源较匮乏，农业和城镇指向的开发适宜性较差。适合发展光伏及风电等对环境影响较小的产业；同时可依托高生活功能的保障优势，适度发展设施农业，引进干旱区沙产业技术弥补自然条件短板。该区需严格控制开发强度，限制新开垦荒地的规模。

生态屏障区、生态缓冲区、生态修复区构成了黑河中游的生态空间，3类不同保护等级的区域均应落实生态补偿政策，防止土地复耕复牧，禁止新增建设活动，严格控制人类扰动。

(4)生态屏障区，主要位于祁连山、龙首山山前地带，受人类活动扰动较少，林草地覆盖度高，降水量相对充沛，生态系统较为完善，发挥着生态屏障的作用。应强化生态保护政策与措施，防治水土流失，维护生物多样性，持续增强该区的生态功能；同时可在祁连山国家公园适度开展自然科普教育与生态旅游等活动，深人挖掘绿水青山的价值。

(5）生态缓冲区，主要位于山丹县东北部、高台县西部和肃南县明花乡，气候暖干、风力强盛，以荒漠景观为主，间有零星耕地分布。该区应逐步实施退耕还草，恢复自然植被，将人类活动控制在资源环境承载能力以内，引导生态系统自然恢复。

(6)生态修复区，主要位于高台、临泽2县南、北部的荒漠地区，与生态缓冲区相比，植被更为稀少，土壤侵蚀剧烈，生态环境非常脆弱。应实施更严格的生态保护政策，禁止一切开发活动，系统开展扎草压沙、补水保湿等人工修复工程。

# 4结论

（1）黑河中游土地功能在组成结构和空间格局上均存在显著的异质性。结构上，该区土地功能以生产功能为主导，而以生态功能和生活功能为辅，体现出传统农业绿洲的比较优势。空间上，多功能性高值区主要出现在走廊平原绿洲农业区与县级行政中心；生产功能高值区沿传统绿洲农业区分布；生活功能高值区位于集镇等基础设施条件优、人口分布密集的地区；祁连山、龙首山地区生态功能较强，而施用化肥较多的农业区和环境脆弱的荒漠地区生态功能较弱。

(2）黑河中游土地多功能性近年来稳中增强。研究时段内，土地多功能性与一级功能的空间格局没有明显变化，反映出区内土地多功能性整体格局保持稳定；多功能得分中等及以上的格网数量明显增加，生产功能与生活功能协调性增强，大部分二级功能间的协同关系也在增强，反映出不同功能在空间上逐渐重叠，土地多功能性日益增强。

(3）黑河中游土地多功能利用仍有提升空间。

土地多功能权衡的结果揭示出不同功能间内在冲突状况，区内低生态功能权衡区体现出人类开发利用活动对土地生态功能的挤占；部分绿洲边缘地区较好的开发条件以及祁连山地区优质的生态旅游、科普教育资源均没有得到充分利用，与相关研究[40]结论基本一致。未来土地用途规划和土地资源开发利用时须权衡土地的不同功能，充分挖掘土地多功能性。

（4）黑河中游需要加强对非主导功能的关注。从土地功能分区结果来看，黑河中游需要统筹规划生产与生活空间布局，提升生活功能水平；依托技术、管理等要素协调土地功能间的固有矛盾，向环境友好的高附加值产业转型，减轻生态环境的负担；统筹推进生态系统自然恢复和人工修复，重视自然资本增值，从构建区域绿水青山的格局挖掘土地价值新的增长点。

# 5讨论

本研究引入了互联网地图兴趣点数据，相比传统的基于统计数据的指标，交通、生活和服务设施等兴趣点数据具有更高的空间分辨率和更强的现势性，能更为直观、准确地度量土地提供的相关服务。但是，由于互联网地图POI数据共享服务于2013年才开始，更早的数据难以获取，限制了本研究的时间跨度。

利用土地功能冷热点类型和功能间权衡与协同类型的分析结果，能够从单一功能的空间集聚现状和多功能间的内在关系2个维度，反映土地对不同功能的适宜程度和承载能力。在土地功能分区中考虑上述特征，能够更准确地区分土地的适宜用途，提高分区结果的准确性和实用性，为国土空间规划、土地资源管理等提供更具参考意义的指导。

对双变量空间自相关分析结果进行解读时，要注意共变关系的影响。如临泽县中部绿洲农业区，化肥施用导致该区生态功能较弱，发达的农业生产却为区内较强的生活功能提供了条件。认为该区存在“高生产-低生态”的权衡关系是较为合理的，但是否存在“高生活-低生态"的权衡关系却是难以确定的。因此，应当综合考虑土地功能间作用类型、途径以及区域本身自然环境和社会经济特点，才能得出更为可靠的结论。

参考文献(References）   
[1]蒙吉军.土地评价与管理[M].3版.北京:科学出版社,2019. [Meng Jijun.Land evaluation and management [M]. $3 ^ { \mathrm { n d } }$ ed. Beijing: Science Press,2019.]   
[2]Verburg PH,van de Steeg J, Veldkamp A,et al.From land cover change to land function dynamics:A major challenge to improve land characterization[J].Journal of Environmental Management, 2009,90(3): 1327-1335.   
[3]Foley JA,Ramankuty N,Brauman K A,et al. Solutions for a cultivated planet[J]. Nature,2011,478(7369): 337-342.   
[4]王枫,董玉祥.基于灰色关联投影法的土地利用多功能动态评 价及障碍因子诊断——以广州市为例[J].自然资源学报， 2015,30(10):1698-1713.[Wang Feng,Dong Yuxiang.Dynamic evaluation oflanduse functions basedongrey relation projection method and diagnosis of its obstacle indicators: A case study of Guangzhou City[J]. Journal of Natural Resources,2015,30(10): 1698-1713.]   
[5]张晓平,朱道林,许祖学.西藏土地利用多功能性评价[J].农业 工程学报,2014,30(6):185-194.[Zhang Xiaoping,Zhu Daolin, Xu Zuxue.Assessment on multi-functionality of land use in Tibet [J]. Transactions of the Chinese Society of Agricultural Engineering, 2014,30(6): 185-194.]   
[6]朱琳,黎磊,刘素,等.大城市郊区村域土地利用功能演变及其 对乡村振兴的启示——以成都市江家堰村为例[J].地理研究, 2019,38(3): 535-549.[Zhu Lin,Li Lei,Liu Su,et al. The evolution of village land-use function in the metropolitan suburbs and its inspiration toruralrevitalization:Acasestudyof Jiangjiayan Village in Chengdu City[J]. Geographical Research,2019,38(3): 535-549.]   
[7]Mander U,Helming K,Wiggering H. Multifunctional land use: Meeting future demands for landscape goods and services[M]. Berlin,Heidelberg: Springer,2007.   
[8]甄霖,曹淑艳,魏云洁,等.土地空间多功能利用:理论框架及实 证研究[J].资源科学,2009,31(4):544-551.[Zhen Lin,Cao Shuyan, Wei Yunjie,et al. Land use functions: Conceptual framework and application for China[J].Resources Science,2009,31 (4): 544-551.]   
[9]OECD.Multifunctionality:Towardsananalytical framework[M]. Paris: Organization for Economic Co-operation and Development (OECD), 2001.   
[10]Paracchini M L,Pacini C, Jones M L M,et al.An aggregation framework to link indicators associated with multifunctional land use to the stakeholderevaluationof policyoptions[J].Ecological Indicators,2011,11(1): 71-80.   
[11]Pérez-Soba M,Petit S,Jones L,et al.Land use functions: A multifunctionality approach to assess the impact of land use changes on land use sustainability[C]//Helming K,Perez-Soba M, Tabbush P. Sustainability Impact Assessment of Land Use Changes.Berlin,

# 干吴区地理

Heidelberg: Springer,2008: 375-404.

[12] 甄霖,魏云洁,谢高地,等.中国土地利用多功能性动态的区域 分析[J].生态学报,2010,30(24):6749-6761.[Zhen Lin,Wei Yunjie,Xie Gaodi,et al.Regional analysis of dynamic land use functions in China[J].Acta Ecologica Sinica,2010,30(24): 6749- 6761.]   
[13] 郭欢欢,李波,侯鹰.基于土地功能的土地资源承载力研究- 以北京市海淀区为例[J).北京师范大学学报(自然科学版), 2011,47(4): 424-427.[Guo Huanhuan,Li Bo,Hou Ying.Research on the capacity of land resources based on land function: Haidian as an example[J]. Journal of Beijing Normal University (Natural Science), 2011, 47(4): 424-427.]   
[14]范业婷,金晓斌,项晓敏,等.苏南地区耕地多功能评价与空间 特征分析[J].资源科学,2018,40(5):980-992.[Fan Yeting,Jin Xiaobin, Xiang Xiaomin,et al.Evaluation and spatial characteristics of arable land multifunction in southern Jiangsu[J]. Resources Science,2018,40(5): 980-992.]   
[15] 戴尔阜,王晓莉,朱建佳,等.生态系统服务权衡:方法、模型与 研究框架[J].地理研究,2016,35(6):1005-1016.[Dai Erfu, Wang Xiaoli,Zhu Jianjia,et al.Methods,tools and research framework of ecosystem service trade-ofs[J]. Geographical Research, 2016,35(6): 1005-1016.]   
[16]Barbier EB,Koch E W,Silliman BR,et al. Coastal ecosystembased management with nonlinear ecological functions and values [J]. Science,2008,319(5861): 321-323.   
[17] 钱彩云,巩杰,张金茜,等.甘肃白龙江流域生态系统服务变化 及权衡与协同关系[J].地理学报,2018,73(5):868-879.[Qian Caiyun,Gong Jie,Zhang Jinxi, et al. Change and tradeoffs-synergies analysis on watershed ecosystem services: A case study of Bailongjiang Watershed, Gansu[J].Acta Geographica Sinica,2018, 73(5): 868-879.]   
[18]Wu J. Landscape sustainability science: Ecosystem services and human well-being in changing landscapes[J]. Landscape Ecology, 2013,28(6): 999-1023.   
[19]Bai Y, Zhuang C, Ouyang Z Y,et al. Spatial characteristics between biodiversity and ecosystem services in a human-dominated watershed[J]. Ecological Complexity,2011,8(2): 177-183.   
[20] 朱庆莹,胡伟艳,赵志尚.耕地多功能权衡与协同时空格局的动 态分析—以湖北省为例[J].经济地理,2018,38(7):143-153. [Zhu Qingying,Hu Weiyan, Zhao Zhishang. Dynamic analysis on spatial-temporal pattern of trade-offs and synergies of multifunctional cultivated land: Evidence from HubeiProvince[J].Economic Geography,2018,38(7): 143-153.]   
[21]王川,刘春芳,乌亚汗,等.黄土丘陵区生态系统服务空间格局 及权衡与协同关系——以榆中县为例[J].生态学杂志,2019, 38(2): 521-531.[Wang Chuan,Liu Chunfang,Wu Yahan, et al. Spatial pattern, tradeoffs and synergies of ecosystem services in loess hilly region: A case study in Yuzhong County[J]. Chinese Journal of Ecology,2019,38(2): 521-531.]

[22]Egoh B N,Reyers B,Rouget M,etal.Identifying priority areas for ecosystem service management in South African grasslands[J]. Journal of Environmental Management,2011,92(6): 1642-1650.

[23] 李双成,张才玉,刘金龙,等.生态系统服务权衡与协同研究进 展及地理学研究议题[J].地理研究,2013,32(8):1379-1390. [Li Shuangcheng, Zhang Caiyu,Liu Jinlong,et al. The tradeoffs and synergies of ecosystem services: Research progress,development trend,and themes of geography[J]. Geographical Research, 2013,32(8): 1379-1390.]   
[24] 方莹,王静,孔雪松,等.耕地利用多功能权衡关系测度与分区 优化———以河南省为例[J].中国土地科学,2018,32(11):57- 64.[Fang Ying,Wang Jing,Kong Xuesong,et al. Trade-off relation measurement and zoning optimization of multi-functionality of cultivated land use: A case study of Henan Province[J]. China Land Science,2018,32(11): 57-64.]   
[25] Zhou D,Xu J,Lin Z. Conflict or coordination? Assessing land use multifunctionalizationusing production-lving-ecologyanalysisJ] Science of the Total Environment,2017,577:136-147.   
[26] 王晓君,石敏俊,王磊.黑河中游水资源空间动态优化配置- 基于分布式水资源管理模型[C]//中国自然资源学会2011年学 术年会论文集(下册).乌鲁木齐:中国自然资源学会,2011: 479-486.[Wang Xiaojun,Shi Minjun,Wang Lei. Spatial dynamic optimal allocation of water resources in the middle reaches of Heihe River: Based on distributed water resources management model [C]/Proceedings of the 2011 Annual Conference of China Society of Natural Resources (Vol.2).Urumqi: China Society of Natural Resources,2011: 479-486.]   
[27] 杜巧玲,许学工,刘文政.黑河中下游绿洲生态安全评价[J].生 态学报,2004,24(9):1916-1923.[Du Qiaoling,Xu Xuegong, Liu Wenzheng. Ecological security assessment for the oases in the middle and lower Heihe River[J]. Acta Ecologica Sinica,2004,24 (9): 1916-1923.]   
[28] 蒙吉军,吴秀芹,李正国.黑河流域1988—2000年土地利用覆 被变化研究[J].北京大学学报(自然科学版),2004,40(6):922- 929.[Meng Jijun,Wu Xiuqin,Li Zhenguo.Land use and land cover changes in Heihe River Basin during the period of 1988- 2000[J].Acta Scientiarum Naturalium Universitatis Pekinensis, 2004,40(6): 922-929.]   
[29]王祺,蒙吉军.黑河中游水资源空间分布对绿洲核心景观类型 变化的驱动分析[J].北京大学学报(自然科学版),2016,52(5): 919-930.[Wang Qi, Meng Jijun. Driving analysis of oasis key landscape types changes based on water resource spatial distribution in middle reaches of Heihe Basin[J].Acta Scientiarum Naturalium Universitatis Pekinensis,2016,52(5): 919-930.]   
[30]蒙吉军,王祺,李枫,等.基于空间差异的黑河中游土地多功能 利用研究[J].地理研究,2019,38(2):369-382.[Meng Jijun, Wang Qi,Li Feng,et al.Assessing multifunctional land use in the middle reach of the Heihe River Basin based on spatial variances [J]. Geographical Research,2019,38(2): 369-382.]   
[31] 高子轶,张海峰.基于POI数据的西宁市零售业空间格局探究 [J].干旱区地理,2019,42(5):1195-1204.[Gao Ziyi,Zhang Haifeng.Spatial structure of the retail industry in Xining City based on POI data[J].Arid Land Geography,2019,42(5): 1195- 1204.]   
[32] 金菊良,杨晓华,丁晶.基于实数编码的加速遗传算法[J].四川 大学学报(工程科学版),2000,32(4):20-24.[Jin Juliang,Yang Xiaohua,Ding Jing.Real coding based acceleration genetic algorithm[J]. Journal of Sichuan University (Engineering Science Edition),2000,32(4): 20-24.]   
[33] 彭建,刘志聪,刘焱序,等.京津冀地区县域耕地景观多功能性 评价[J].生态学报,2016,36(8): 2274-2285.[Peng Jian,Liu Zhicong,LiuYanxu,et al.Assessment of farmland landscape multifunctionality at county level in Beijing-Tianjin-Hebei area[J].Acta Ecologica Sinica,2016,36(8): 2274-2285.]   
[34] 詹璇,林爱文,孙铖,等.武汉市公共交通网络中心性及其与银 行网点的空间耦合性研究[J].地理科学进展,2016,35(9): 1155-1166.[Zhan Xuan,Lin Aiwen, Sun Cheng,et al. Centrality ofpublic transportation network and its coupling with bank branches distribution in Wuhan City[J].Progress in Geography, 2016,35(9): 1155-1166.]   
[35]Anselin L. Local indicators of spatial association: LISA[J]. Geographical Analysis,1995,27(2): 93-115.   
[36]Anselin L,Syabri I, Smirnov O.Visualizing multivariate spatial correlation with dynamically linked windows[C]//AnselinL,Rey S. New Tools for Spatial Data Analysis:Proceedings of the Specialist Meeting.Santa Barbara: University of California,2002.   
[37] 徐磊,董捷,李璐,等.基于功能分区视角的长江中游城市群国 土空间特征及优化[J].经济地理,2017,37(6):76-83.[Xu Lei, Dong Jie,Li Lu,et al. Characteristics and optimization of geographical space in urban agglomeration in the middle reaches of the Yangtze River based on the function zoning[J]. Economic Geography,2017,37(6): 76-83.]   
[38] 杨发鹏,张雪唱,李宗阳.城市旅游"三生"竞争力空间分异- 以西北五省为例[J].干旱区地理,2019,42(3):664-672.[Yang Fapeng,Zhang Xuechang,Li Zongyang. Spatial differentiation of the “production-life-ecology”competitiveness in urban tourism: A case study of five provinces in northwest China[J].Arid Land Geography,2019,42(3): 664-672.]   
[39] 赵领娣,李莎莎,赵志博,等.干旱半干旱区城市生态效率时空 演变及区域差异分析[J].干旱区地理,2020,43(2):449-457. [Zhao Lingdi,Li Shasha, Zhao Zhibo,et al. Temporal and spatial evolution and regional difference analysis of urban ecological efficiency in arid and semiarid areas[J].Arid Land Geography,2020, 43(2): 449-457.]   
[40]白海江.耕地多功能评价及权衡与协同关系分析——以张掖市 为例[J].西部大开发(土地开发工程研究),2020,5(3):1-5.[Bai Haijiang. Multi-function evaluation and trade-ofs and synergy analysis of cultivated land: A case study of Zhangye City[J]. Land Develop ment and Engineering Research,2020,5(3): 1-5.]

# Spatial-temporal pattern and trade-offs of land multi-function in the middle reaches of the Heihe River based on multi-source geographic data fussion

CHENG Haoran'， MENG Jijun’， ZHU Likai² (1.KeyLaboratoryofEarthSurfaceProcessesofMinistryofEducation,CoegeofUrbanandEnvironmentalSciences,Peking UniversityBeinga；.leofsoudEiontnyUveityini,doga)

Abstract: Multifunctional land use is an important way to improve land-use eficiency,alleviate the contradiction between people and land,and promote regional sustainable development.The Heihe River's middle reaches in the middle of the Hexi Corridor, Gansu Province,China is the most densely populated and economically developed area,characterized by the most intense conflict between humans and land in the Heihe River Basin. However, the lack of knowledge about multifunctional land-use conditions hinders sustainable land-use planning and management in this area.In this study,we developed a land multi-function evaluation index system based on the production-life-ecology framework. We then applied a projection pursuit model based on a genetic algorithm to make a grid-based land multifunctional assessment at a $3 \ \mathrm { k m } \times 3 \ \mathrm { k m }$ resolution by assimilating geographical datasets from multiple sources,including remote sensing,socio-economic statistics,and point-of-interest (POI) data.To reveal the trade-offs and synergies of land multi-functions,we performed Spearman’s correlation and bivariate local spatial autocorrelation analysis. We also conducted a functional land zoning using RGB composite and clustering analysis. We found the following results: (1)The land functions in the study area varied with landuse patterns.The primary land function was for production,and the secondary land functions were for living and ecological functions.The land functions also showed spatial variability,characterized by the dominant production functions in the oasis agricultural lands,the useful living functions in the densely populated areas such as cities and towns with bettr facilities,and the most important ecological functions in Qilian Mountain and Longshou Mountain. (2)Land multi-functionality was enhanced during the study period.The spatial patern of land multifunctionality and the dominant functions were stable,and the coordination among multiple functions was universally enhanced, indicating that various functions were more overlapped spatially. (3)On the basis of the principle of dominant use direction,the land in the Heihe River's middle reaches can be divided into six zones: key development zones,optimizing development zones, moderate development zones，ecological barier zones, ecological buffer zones，and ecological restoration Zzones.The former three zoneswere mainly used for agricultural production and urban space functions,whereas the latter three zones acted as ecological spaces. (4) There was still some room for improvement in land multi-functionality.Attention should be paid to non-dominant functions and the coordination of the inherent contradictions among functions.Efforts should be made to collaboratively promote ecological restoration and appreciation of natural capitalsand discover new growth points byconstructing the regional pattern of lucid waters and lush mountains.This study highlights the POI data acquired from the Internet map open platforms.Compared with the conventional indicators,POI data can be updated more readily and can reflect the locations and types of facilities more accurately,capturing the levels of each land function more effectively. When making functional land zoning,this study also emphasizes using the RGB composite method to obtain dominant land functional patterns while simultaneously considering the cold and hot spots of land function and the trade-offs and synergies among functions.This approach reflected the current spatial patern of land function clustering and the internal relationships among functions simultaneously, improving the classified zones’accuracy and operationality.

Key words: land multi-function；multi-source geographic data;spatial-temporal patern； trade-offs and synergies；land functional zoning; the middle reaches of the Heihe River