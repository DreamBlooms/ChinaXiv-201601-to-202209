# 呼和浩特市生活性服务业空间布局特征及评价

李小璨，阿荣，佟宝全(内蒙古师范大学地理科学学院，内蒙古 呼和浩特010022)

摘要：通过以呼和浩特市为例，采用多源城市大数据，基于核密度估计法、局域Getis-OrdG\*指数、标准差椭圆、Ripley's $K$ 函数分析生活性服务业空间布局特征，运用双变量莫兰指数对各类生活性服务业的供给与需求进行评价并提出优化布局建议。研究表明：(1）生活性服务业集聚中心的密度值随着距城市中心距离的增加而降低;各类生活性服务业分布重心大致相同，东西方向上发展较快。(2）生活性服务业分布存在显著的冷热点集聚区；各类生活性服务业在不同尺度上的空间集聚表现不同，居民与家庭服务、医疗健康服务、住宿餐饮服务在较大空间范围内表现出集聚特征，区位选择的尺度范围较大。(3)各类生活性服务业的供给与需求均呈空间正相关关系，但存在显著差异;在供需平衡的原则下，昭乌达路、鄂尔多斯大街、新华大街等几条主要道路上的生活性服务业空间布局存在明显不合理之处。

关键词：生活性服务业；POI数据；空间布局；双变量莫兰指数；呼和浩特市

# 文章编号：

当服务业经济进入全球化时代，其产生的经济效益逐步超过工业、农业，成为了城市发展的核心动力[]。服务业分为生产性服务业和生活性服务业，其中生活性服务业是关乎人民生活的行业，与人们的日常生活息息相关，了解其空间布局非常重要[2]。在中国,随着城市的快速发展,全国城镇化率从1992年的 $2 6 . 4 \%$ 上升到了2017年的 $5 8 . 5 2 \% ^ { [ 3 ] }$ 当城镇化质量受到越来越多的关注，一个城市生活性服务业的空间布局随之成为了广大学者的研究重点[4]。在一些发达国家的都市区中,生活性服务业的研究已逐渐偏郊区化，Lee等5对1980—1990年间美国12个大城市的零售商业分析研究得出，除休斯顿以外的其他城市，在郊区从事零售商业就业人数的比重均超过总就业人数的 $6 0 \%$ ，个别城市郊区的从业人员达到了 $8 0 \%$ ,且年均增长速度非常显著。Dong[以波特兰为研究区域,研究得出在城市规划重点集中在中心城区的前提下，零售商业、小餐饮业等却在快速向郊区分散布局，并逐渐出现多中心化的集聚特征。与国外生活性服务业研究偏郊区化不同，中国城镇化起步相对较晚，发展还不尽完善，国内学者的研究大多集中在城市内部的生产性服务业与生活性服务业的空间聚集特征及形成机理[7-]。其中杨吾扬[12]采用中心地理论系统地对北京市零售商业和服务业形成机制、空间结构进行讨论，并对未来北京市商服业的空间布局进行了合理预测，此项调研研究对我国大城市区的城市经济地理研究具有深远影响。

随着城市地理学研究的逐渐深人，越来越多的城市研究基于大数据(遥感卫星数据、手机数据、GPS导航数据、出租车轨迹数据等)来完成。城市各行业网点信息(Pointofinterest,POI)作为1种新的空间数据源，其分布模式、分布密度在基础设施布局研究以及城市空间规划中具有重要的意义[13],被广泛的应用于城市功能区识别、城市空间结构研究、商业空间布局研究、零售商业中心的识别、城市休闲空间格局分析、城市生活性服务业设施的空间布局等研究[14-20]。近年来,越来越多的研究运用POI数据探讨商业网点在选择区位布局时的影响因素[21-22],以及与街道布局、小区位置的关系特征[23-24],以期为城市商业区布局提供更为有用的指导意见。

呼和浩特市作为内蒙古自治区首府城市，其生活性服务业布局是否合理，对呼和浩特市以及整个内蒙古自治区的城市发展举足轻重。本文采用高德地图POI数据、道路数据、综合安居客、房天下、贝壳网等房产网站的小区数据，分析生活性服务业空间布局特征，从供需角度对其空间布局进行评价，并提出相应的优化建议。鉴于此，本研究可为呼和浩特市中心城区生活性服务业空间结构调整和空间优化布局提供参考依据。

# 1材料与方法

# 1.1 研究区概况

呼和浩特市是内蒙古自治区的首府城市，市辖回民区、玉泉区、赛罕区、新城区。2018年全市常住人口为 $3 1 2 . 6 4 \times 1 0 ^ { 4 }$ 人，其中城镇人口 $2 1 8 . 3 2 \times 1 0 ^ { 4 }$ 人，同年城镇化率达到 $6 9 . 8 3 \%$ ，远超同期全国平均$5 9 . 5 8 \%$ 的城镇化率。呼和浩特市中心城区位于大青山以南，大黑河以北，主要集中在二环路以内，结合POI数据的分布格局与呼和浩特市（2011—2020年)城市总体规划所划定的中心城区范围，确定呼和浩特市北二环路以及110国道以南，西二环路以东，科尔沁快速路以西，正在修建的三环路以北的区域为研究区域。此研究区包括回民区、玉泉区、赛罕区、新城区4个市辖区的部分区域，是市民普遍认同的中心城区域(图1)。

# 1.2数据来源

在高德地图网站申请账号、web服务的密钥，通过python软件爬取获得2019年5月高德地图的呼和浩特市区P0I数据，共计143677个兴趣点。经过去重、筛选，以及坐标纠偏得到研究区范围内的生活性服务业POI数据98822个，并对获取的POI数据随机取样进行验证，除少量数据的位置有偏移外，超过 $9 5 \%$ 的数据均能通过验证，因此数据有效。根据《国民经济行业分类与代码(GB/4754-2011)》、生活性服务业统计分类(2019)以及为居民和家庭提供生活性服务为原则，本文将所提取的研究区范围内生活性服务业POI数据分为9类(表1)。

除了POI数据外，街道道路图来源于开源道路数据网（OpenStreetMap），综合安居客（https://huhe-haote.anjuke.com/）、房天下（https://nm.fang.com/）、贝壳网(https://hhht.ke.com/)等房产网站2019年的小区数据。其中道路数据根据其属性删除了居住区道路、步行道路、过境铁路和未分级道路，仅保留一级、二级与三级道路(图2)。

# 1.3研究方法

1.3.1核密度估计法核密度估计是用来估计数据位置的密度函数，由Rosenblatt和EmanuelParzen提出，借助一个移动的单元格对点或线分布格局的密

![](images/4eca10289873ffb6a21da03cadb7359558c9df80377751e1ce21320717ba286d.jpg)  
图1研究区域地理位置图  
Fig.1 Location of the study area

# 干吴区地理

# 表1呼和浩特市POI数据生活性服务业行业分类

Tab.1 POI data of life service industry classification in Hohhot City   

<html><body><table><tr><td>ID</td><td>行业分类</td><td>POI数据内容</td><td>数量/个</td><td>比例/%</td></tr><tr><td>1</td><td>居民和家庭服务</td><td>汽车维修、美容美发店、中介机构、洗衣店、人才市场、丧葬、广告装 饰等</td><td>22878</td><td>23.15</td></tr><tr><td>2</td><td>医疗健康服务</td><td>医院、医药保健销售店、医疗保健服务场所、诊所等</td><td>4181</td><td>4.23</td></tr><tr><td>3</td><td>批发与零售服务</td><td>加油站、综合市场、便利店、家居建材市场、花鸟鱼虫市场、特色商 业街、汽车销售等</td><td>38494</td><td>38.96</td></tr><tr><td>4</td><td>住宿餐饮服务</td><td>快餐厅、中餐厅、糕饼店、外国餐厅、咖啡厅、宾馆酒店、甜品店等</td><td>23536</td><td>23.82</td></tr><tr><td>5</td><td>教育培训服务</td><td>学校、培训机构、图书馆、文化宫、科技馆、博物馆、展览馆等</td><td>3863</td><td>3.91</td></tr><tr><td>6</td><td>金融保险服务</td><td>银行、自动提款机、保险公司、证券公司、财务公司等</td><td>1665</td><td>1.68</td></tr><tr><td>7</td><td>文化体育休闲娱乐</td><td>游泳馆、运动场馆、娱乐场所、度假疗养场所、影剧院、传媒机构等</td><td>2206</td><td>2.23</td></tr><tr><td>8</td><td>城市休憩服务</td><td>公园广场、风景名胜、公厕等</td><td>1111</td><td>1.12</td></tr><tr><td>9</td><td>生活网络信息传输服务</td><td>邮局、物流速递、电讯营业厅等</td><td>888</td><td>0.90</td></tr><tr><td>总计</td><td>一</td><td></td><td>98822</td><td>100.00</td></tr></table></body></html>

![](images/698315c3627d9a96305554e859b36d7930de4983baebc6e5c132befc6d4bc67f.jpg)  
图2生活性服务业POI和小区数据分布

Fig.2Distribution about POI of life service industry and residential area

度进行估计[25]。核密度估计公式如下：

$$
f _ { h } \big ( x \big ) = \frac { 1 } { n h } \sum _ { i = 1 } ^ { n } K \Bigg ( \frac { x - x _ { i } } { h } \Bigg )
$$

式中： $\mathbf { \Omega } _ { n }$ 为距离 $x$ 为 $h$ 范围内的点数; $h > 0$ ,称为带宽； $K$ 为核函数; $x - x _ { i }$ 为点 $x$ 到点 $x _ { i }$ 之间的距离。本研究以生活性服务业设施网点的平均影响范围与其空间分布的离散程度为参考依据[26],选择400$\mathrm { m } \cdot 6 0 0 \ \mathrm { m } \cdot 8 0 0 \ \mathrm { m } \cdot 1 0 0 0 \ \mathrm { m }$ 作为带宽进行模拟试验。实验结果显示 $6 0 0 \mathrm { m }$ 带宽距离能够较好地识别生活性服务业网点分布的局部热点信息，整体分布特征也能得到较好反映。

1.3.2 局域Getis-Ord $\boldsymbol { G } ^ { * }$ 指数法 $\boldsymbol { G } ^ { * }$ 统计指数是统计意义上的 $Z$ 得分，其计算公式为：

$$
G _ { i } ^ { * } = \frac { \displaystyle \sum _ { j = 1 } ^ { n } W _ { i j } ( d ) X _ { j } } { \displaystyle \sum _ { j = 1 } ^ { n } X _ { j } }
$$

式中： $X _ { j }$ 是第 $j$ 个空间单元的要素属性值； $n$ 是要素总数； $W _ { i j } ( d )$ 代表空间权重矩阵，若第 $i$ 和第 $j$ 个要素之间的距离在给定临界距离 $d$ 之内，空间权重矩阵中的元素为1;否则为0。局域Getis-Ord $G ^ { * }$ 统计量的检验可以通过标准化形式的 $[ Z \left( \boldsymbol { G } _ { i } ^ { * } \right)$ 值]来检验,如式(3)所示。如果 $Z { > } 0$ ,则为高值空间集聚;相反,则为低值空间集聚。通常情况下，选取 $Z$ 得分在置信度为 $9 5 \%$ 时大于1.96的区域为空间点要素聚集

的热点区域。

$$
Z \big ( G _ { i } ^ { * } \big ) = \frac { G _ { i } ^ { * } ( d ) - E \big ( G _ { i } ^ { * } \big ) } { \sqrt { \operatorname { V A R } \big ( G _ { i } ^ { * } \big ) } }
$$

其中方差和均值分别为

$$
\operatorname { V A R } \left( G _ { i } ^ { * } \right) = \frac { S _ { i } ^ { * _ { 2 } } \bigl [ W _ { i } ^ { * } \bigl ( n - 1 - W _ { i } ^ { * } \bigr ) \bigr ] } { \bigl ( n - 2 \bigr ) \biggl ( \displaystyle \sum _ { j = 1 } ^ { n } X _ { j } \biggr ) ^ { 2 } } , E \bigl ( G _ { i } ^ { * } \bigr ) = \frac { W _ { i } ^ { * } } { n }
$$

$$
\boldsymbol { W } _ { i } ^ { * } = \sum _ { j = 1 } ^ { n } \boldsymbol { W } _ { i j } , \boldsymbol { S } _ { i } ^ { * _ { 2 } } = \frac { 1 } { n } \sum _ { j = 1 } ^ { n } \biggl ( \boldsymbol { X } _ { j } - \frac { 1 } { n } \sum _ { j = 1 } ^ { n } \boldsymbol { X } _ { j } \biggr ) ^ { 2 }
$$

式中： $\boldsymbol { G } _ { i } ^ { * } ( \boldsymbol { d } )$ 为临界距离 $d$ 之内的 $\boldsymbol { G } _ { i } ^ { * }$ 统计指数;$E \big ( G _ { i } ^ { * } \big )$ 为 $\boldsymbol { G } _ { i } ^ { * }$ 统计指数的均值; $\mathrm { V A R } \big ( G _ { i } ^ { * } \big )$ 为 $\boldsymbol { G } _ { i } ^ { * }$ 统计指数的方差; $\boldsymbol { S } _ { \ i } ^ { * 2 }$ 为 $X _ { j }$ 剩余平方和的均值; $\boldsymbol { W } _ { i j }$ 为权重矩阵； $\boldsymbol { W } _ { i } ^ { * }$ 为权重和; $n$ 为要素总数。

1.3.3 Ripley' s $K$ 函数城市地理相关研究中，空间尺度不同，地理要素的空间分布特征也会出现很大的差异。Ripley's $K$ 函数可以分析空间点要素在不同空间尺度上的分布情况[27]。其公式表示为：

$$
K ( d ) = A \sum _ { i } ^ { n } \sum _ { j } ^ { n } { \frac { W _ { i j } ( d ) } { n ^ { 2 } } }
$$

式中： $A$ 为研究区域的面积； $n$ 为生活性服务业网点数量; $d$ 为2个生活性服务业网点之间的距离阈值;$\boldsymbol { W } _ { i j } ( d )$ 为在距离阈值范围内，2个点之间的距离。

$$
L ( d ) = \sqrt { \frac { K ( d ) } { \pi } } - d
$$

式中： $L ( d )$ 表示在距离范围 $d$ 内,各类生活性服务业的空间分布格局。 $L ( d )$ 为正则表示生活性服务业行业集聚分布，为负表示分散分布，为0表示随机分布。

1.3.4标准差椭圆标准差椭圆 $X , Y$ 轴可以用来表示各空间要素点的空间发展方向分布情况，其覆盖面积可以反映出空间要素点的离散程度[28]。

1.3.5双变量莫兰指数莫兰指数早期运用于生物现象的空间分析，将一维的空间概念系数扩展到了二维空间，双变量莫兰指数是对传统莫兰指数的进一步改进。传统单变量莫兰指数主要表达的是空间某一要素同一指标的空间自相关关系，而双变量莫兰指数主要表达的是某一要素的一个属性与另一个属性的空间相关关系。双变量莫兰指数分为双变量全局莫兰指数与双变量局部莫兰指数，其公式如下：

$$
I = \frac { n \displaystyle \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } W _ { i j } Z _ { x i } Z _ { y j } } { \displaystyle \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } W _ { i j } \sum _ { i = 1 } ^ { n } Z _ { x i } Z _ { y j } }
$$

$$
I _ { i } { = } Z _ { _ { x i } } \sum _ { j { = 1 , j \neq i } } ^ { n } W _ { i j } Z _ { _ { y j } }
$$

式中：1为双变量莫兰指数； $I _ { i }$ 为某一生活性服务业网点的局部莫兰指数; $Z _ { x i }$ 与 $Z _ { y }$ 代表居住小区与生活性服务业网点在某一点的核密度标准化值。双变量局部莫兰指数 $I _ { i }$ 用来绘制莫兰散点图，本研究运用双变量莫兰指数探求不同的生活性服务业网点供给与需求的耦合协调关系。将各类生活性服务业的供给(各类生活性服务业网点分布的密度)与需求(居住小区分布的密度)提取为各类生活性服务业网点的属性，研究便转化为对矢量点属性间的空间耦合性分析，从而转化为目前城市地理中常被用到的空间自相关分析[29-30]

# 2空间格局特征

# 2.1生活性服务业空间布局

生活性服务业空间布局与人们日常生活的方便性与便捷性直接相关。通过核密度估计法对呼和浩特市城区的生活性服务业进行分析，运用Arc-GIS软件自然断点法将核密度分析结果分为5类（图3)，可以识别出：（1）呼和浩特市中心城区生活性服务业出现了明显的集聚区，其中高密度集聚区域有3个，海亮广场、维多利摩尔城、万达广场。总体来看，生活性服务业在空间分布上形成了一种块状聚集、带状延伸、多中心发展的格局。(2）生活性服务业集聚中心呈现出明显的沿交通干线带状分布特征，即沿着新华大街、中山东路及周边区域分布。(3）生活性服务业由集聚中心向外扩散呈现出较明显的圈层体系，即以中山东路、新华大街为最高级集聚中心，向外呈圈层扩散，集聚等级逐渐降低。(4)次级生活性服务业集聚中心主要依傍中心城区内风景名胜、博物院、游乐园分布，呈现分散性的分布特征，主要以大召无量寺、青城公园为中心进行布局。

# 2.2生活性服务业分布的冷热点区域

生活性服务业分布高度集中的区域可视为其分布的热点区域，同时也是城市发展的重要节点区域。基于开源道路数据网提取的三级城市道路，把整个研究区域划分为不同大小的街区单元，采用局

# 干旱区地理

![](images/77204220cb0af423a1ce6004ba08db74b9032f7cb81a72a4f6064b9bc86c04bd.jpg)  
图3生活性服务业密度分布  
Fig.3Density distribution of life service industry   
图4生活性服务业分布的冷热点集聚格局  
Fig.4Cold and hot spots clusters of life service industry

域Getis $. { \mathrm { O r d } } G ^ { * }$ 指数进行分析。结果显示(图4)，呼和浩特市中心城区内，生活性服务业分布存在显著的冷热点集聚区。冷热点区域的分布与生活性服务业的各圈层集聚区域分布较一致，新华大街、中山东路、大召无量寺、维多利摩尔城、万达广场等区域形成了典型的热点区域;北山公园、绿地之窗、金桥广场、百联钢铁仓储市场等区域形成了典型的冷点区域。生活性服务业网点的热点分布区域，与生活性服务业网点高密度区域分布一致，说明各类生活性服务业网点在分布时相互影响，“高热点分布区域-高密度区域"类型的街区单元集聚分布。

图例NA 北山公园 ·地标-研究区街道绿地之窗 □研究区范围维多利摩尔城·万达广场 冷热值新华大街。 -4.71\~-3.17中山东路 新世纪广场 -3.17\~-1.96-1.96\~-0.40大召无量寺 由 □10.40\~1.181.96\~4.68金桥广场 4.68\~6.310 3kmL L

# 2.3各类生活性服务业分布特征

运用核密度分析法对各类生活性服务业分布格局进行分析，运用ArcGIS软件自然断点法将核密度分析结果分为5类，不同类型的生活性服务业空间分布特征明显不同(图5)。(1）各行业的集聚区域存在一定的重叠，与整体生活性服务业集聚中心分布大体一致。作为城市内部人们生活集中的地区，生活性服务业集聚中心在城市人口分布、商业用地供应、交通配套、商业氛围等因素上具有相对显著的区位优势[31]。居民和家庭服务、批发与零售服务、文体休闲娱乐服务、住宿餐饮服务等行业的集聚中心与整体生活性服务业的集聚中心分布较一致。(2）除城市休憩服务、批发与零售服务、文体休闲娱乐服务、住宿餐饮服务外，其他几类生活性服务业均存在显著的多中心密度分布特征。其中教育培训服务、金融保险服务、生活网络信息传输服务、医疗健康服务的密度分布中心规模相对较大，原因归结于它们并不完全是属于商业盈利性部门，为尽可能多的保障居民使用，因此它们分布的密度中心规模也相对较大。通过对整体生活性服务业和各类型生活性服务业的兴趣点绘制标准差椭圆，做方向分布分析，9类生活性服务业的标准差椭圆所覆盖的地域相差不大，均分布在市区二环以内，说明该范围区域是呼和浩特市城区的中心地带；各类型生活性服务业方向分布的标准差椭圆重心均处于新世纪广场、海亮广场周围，长半轴均以东一西、东北一西南方向为主，表明9类生活性服务业分布重心大致相同、发展态势基本为东西走向，这与呼和浩特市中心城区因北部被大青山阻挡，沿东西轴向发展较快的城市发展形态是一致的。

# 2.4各类生活性服务业空间集聚特征

基于Ripley's $K$ 函数分析各类生活性服务业网点不同空间尺度的集聚特征(图6)，通过CrimeStat软件得到分析结果：在 $9 9 \%$ 的置信度下，各类生活性服务业 $L ( t )$ 曲线均位于包络线(包迹线)之上，表明各类生活性服务业的空间分布集聚特征显著； $L ( t )$ 值越高，表明生活性服务业设施网点空间集聚程度越高。从 $L ( t )$ 最高值的数值来看，各类生活性服务业分布的集聚程度为：批发与零售服务 $( 2 . 4 0 4 ) >$ 医疗健康服务 $( 2 . 3 9 2 ) \mathrm { > }$ 居民与家庭服务（2.344） $\mid >$ 住宿餐饮服务 $( 2 . 2 0 2 ) >$ 文体休闲娱乐服务（2.159） $>$ 教育培训服务 $( 2 . 0 9 7 ) >$ 金融保险服务 $( 1 . 8 6 9 ) >$ 城市休憩服务 $( 1 . 4 5 3 ) \mathrm { > }$ 生活网络信息传输服务（1.293）。在观测距离范围内，各类生活性服务业兴趣点 $L ( t )$ 值均呈现出先升后降的单峰值特征。从 $L ( t )$ 峰值出现的距离来看，居民与家庭服务、医疗健康服务和住宿餐饮服务行业集聚范围明显较大，其最高值分别出现在 $4 . 6 \mathrm { k m } \ 、 4 . 4 \mathrm { k m }$ 和 $4 . 4 \mathrm { k m }$ 处，说明这几类生活性服务业的区位选择范围较大。主要原因在于这三类行业属于基础性社会服务行业，为了城市居民使用的便利性，分散分布于整个中心城区，因此网点位置选择的尺度范围较大。而教育培训服务、批发与零售服务、文体休闲娱乐服务、金融保险服务、城市休憩服务以及生活网络信息传输服务行业最大集聚半径出现的范围相对较小，出现在4.05\~4.20$\mathrm { k m }$ 之间，说明这几类生活性服务业的区位选择范围相对较小。主要原因在于这些行业以盈利作为存在的目的，行业集聚，可以带来更大的经济效益，并且人流量的多寡、居民分布的多寡也直接影响其空间布局，因此这几类生活性服务业布局的集聚范围相对较小。

![](images/7a1c1679cbd237477eecdd4420676c0703b7d1d1bfd2c2501e68046257d60df6.jpg)  
图5研究区各类生活性服务业网点分布  
Fig.5Distribution of various service outlets in study area

# 3基于供需平衡的生活性服务业空间布局评价及优化建议

3.1基于供需平衡的生活性服务业空间布局评价运用双变量莫兰指数对呼和浩特市生活性服务业布局评价的过程如下：将各类生活性服务业与居住小区核密度分析结果的密度值分别赋值到各类生活性服务业网点上，成为生活性服务业网点的两类属性，代表其附近区域对生活性服务业的供给与需求，各类生活性服务业核密度分析结果栅格大小不同，因此附近区域的大小各不一样，具体指的是生活性服务业网点所在栅格单元与四周相邻像元的区域。通过GeoDa软件对各类生活性服务业网点进行双变量莫兰指数分析，各类生活性服务业网点的莫兰散点图如图7所示。

莫兰指数值表示各类生活性服务业网点全局的供(给)需(求)耦合关系，各类生活性服务业网点的莫兰数值均大于( $) ( \scriptstyle P = 0 . 0 0 1$ )，表明各类生活性服务业的供给与需求均呈显著正相关关系，其中教育培训服务、金融保险服务与医疗健康服务的莫兰指数相对更高，说明这三类生活性服务业的供给与需求具有强烈的空间正相关关系，其布局比较合理，

1.5 (a)城市休憩服务 2.5 (b)教育培训服务 2.0 (c)金融保险服务2.0 1.51.0 1.5 最大值：2.097最大值：1.453 最小值：-0.822 1.0 最大值:1.8690.5 0.0 最小值：-0.850 四 1.0 0.5 L(t) 最小L(t) 四 0.5 最小值:-0.791L（t) 0.0 最大L(t) 0.0 L(t)-0.5 最小L(t) -0.5 -0.5 最小L(t)-1.0 最大L(t) -1.0 上 上 上 -1.0 最大L( 10 1 2 3 4 5 6 0 1 2 3 4 5 6 0 1 2 3 4 5距离/km 距离/km 距离/km2.5 (d)居民和家庭服务 2.5 (e)批发与零售服务 1.5 (f)生活网络信息传输服务201510 值24 201510 最值.043 105 最大值.93  
()T 四 L(t)0.5 -最小L(t) 0.5 最小L(t) 0.00.0 最大L（t) 0.0 -最大L(t) L(t)-0.5 最小L(t)-0.5 -0.5 -最大L(t)-1.0 -1.0 -1.00 1 2 3 4 5 6 0 1 2 3 4 5 6 0 1 2 3 4 5 6距离/km 距离/km 距离/km2.5 (g)文体休闲娱乐服务 2.5 (h)医疗健康服务 2.5 (i)住宿餐饮服务2015 最大值2.599 2015 最值923 2015 最大值22023  
1.0 L(t) 1.0 L(t) 1.0 L(t)0.5 最小L(t) 0.5 最小L(t) 0.5 最小L(t)0.0 最大L(t) 0.0 最大L(t) 0.0 -最大L(t)-0.5 -0.5 -0.5-1.0 1 1 1 -1.0 -1.00 1 2 3 4 5 6 0 1 2 3 4 5 6 0 1 2 3 4 5 6距离/km 距离/km 距离/km

其中莫兰散点图的横轴(标准化变量)代表的居住小区的核密度的标准化值，纵轴(空间滞后变量)代表各类生活性服务业网点核密度的标准化值。每个点代表的是生活性服务业网点，一、二、三、四象限分别为高-高、低-高、低-低、高-低分类。其中高-高的实际意义为该类生活性服务业网点的需求与供给都要高于平均水平,这说明生活性服务业网站配置是合理的。低-高的实际意义为该类生活性服务业网点区域附近的小区密度低于平均水平，但是生活性服务业网点的密度高于平均水平，说明生活性服务业网点的布局供大于求。低-低的实际意义为该类生活性服务业网点的需求与供给都要低于平均水平，这说明生活性服务业网站配置也是相对合理的。高-低的实际意义为该类生活性服务业网点区域附近的小区密度高于平均水平，但是生活性服务业网点的密度低于平均水平，说明生活性服务业网点的布局供不应求。表2统计了9类生活性服务业在4个象限分布的数量以及占比情况，

根据各类生活性服务业的莫兰散点图绘制了其网点在研究区范围内的聚类分布图(图8)。1）城市休憩服务中，低-高分类的网点主要出现在玉泉一巷与新生街之间,代表此区域城市休憩服务的供给大于求；高-低分类的网点主要出现在兴安南路街道，代表此区域内对城市休憩服务的供不应求。(2）教育培训服务中，低-高分类的网点主要出现在通道北路与气象局西路之间，大学西街、鄂尔多斯大街与昭乌达路之间;高-低分类的网点主要出现在昭乌达路与新希望街区域。(3）金融保险服务中，低-高分类的网点主要出现在新华大街、陶利街与昭乌达路交叉之间；高-低分类的网点主要出现在鄂尔多斯大街与三里营西路上。（4）居民和家庭服务中，低-高分类的网点主要出现在公园东路与中山西路交叉区域以及丁香南路上；高-低分类的网点主要出现在满都海西巷、前进巷与兴安南路上。

![](images/855e8d56e43ef6529065fda43ec64c25264445c56ae5e43cac8c27276e7b9a2f.jpg)  
图7各类生活性服务业的莫兰散点图  
Fig.7Moran scatter plot of various life service industries

表24种类型生活性服务业网点数量与占比  
Tab.2 Number and proportion of the four types of life service outlets   

<html><body><table><tr><td rowspan="2">需求(供给)类型</td><td colspan="2">高-高(第一象限)</td><td colspan="2">低-高(第二象限)</td><td colspan="2">低-低(第三象限)</td><td colspan="2">高-低(第四象限)</td><td rowspan="2">P值</td></tr><tr><td>总和</td><td>占比/%</td><td>总和</td><td>占比/%</td><td>总和</td><td>占比/%</td><td>总和</td><td>占比/%</td></tr><tr><td>居住(城市休憩服务)</td><td>211</td><td>19</td><td>54</td><td>5</td><td>603</td><td>54</td><td>243</td><td>22</td><td>0.001</td></tr><tr><td>居住(教育培训服务)</td><td>1059</td><td>27</td><td>562</td><td>15</td><td>1745</td><td>45</td><td>497</td><td>13</td><td>0.001</td></tr><tr><td>居住(金融保险服务)</td><td>486</td><td>29</td><td>276</td><td>17</td><td>704</td><td>42</td><td>199</td><td>12</td><td>0.001</td></tr><tr><td>居住(居民和家庭服务）</td><td>7043</td><td>31</td><td>1961</td><td>9</td><td>11690</td><td>51</td><td>2184</td><td>10</td><td>0.001</td></tr><tr><td>居住(批发与零售服务)</td><td>8943</td><td>23</td><td>3921</td><td>10</td><td>18117</td><td>47</td><td>7513</td><td>20</td><td>0.001</td></tr><tr><td>居住(生活网络信息传输服务)</td><td>226</td><td>25</td><td>132</td><td>15</td><td>418</td><td>47</td><td>112</td><td>13</td><td>0.001</td></tr><tr><td>居住(文体休闲娱乐服务）</td><td>389</td><td>18</td><td>155</td><td>7</td><td>1083</td><td>49</td><td>579</td><td>26</td><td>0.001</td></tr><tr><td>居住(医疗健康服务)</td><td>1246</td><td>30</td><td>553</td><td>13</td><td>2003</td><td>48</td><td>379</td><td>9</td><td>0.001</td></tr><tr><td>居住(住宿餐饮服务）</td><td>5774</td><td>25</td><td>2222</td><td>9</td><td>11658</td><td>50</td><td>3882</td><td>16</td><td>0.001</td></tr></table></body></html>

![](images/4ec2d462469fcba56cd300da79e788f888066f310a59d671a5e6db7bc889f1af.jpg)  
干辛区地理  
图8各类生活性服务业网点聚类分布  
Fig.8Cluster distribution of various types of life service outlets

(5)批发与零售服务中，低-高分类的网点主要出现在鄂尔多斯大街与文庙街之间，中山西路与健康街之间，哲里木路、兴安北路与北垣东街交叉路口北面，所涉及的区域比较多;高-低分类的网点主要出现在大学西街与大学东街上，北垣东街与北垣西街上，县府街与庆凯街之间大学街道与乌兰察布街道之间，所涉及的区域比较多。(6)生活网络信息传输服务中，低-高分类的网点主要出现在附件厂西路与车站西街上；高-低分类的网点分布区域比较稀疏，区域数量较少。（7）文体休闲娱乐服务中，低-高分类的网点主要出现在公园东路上；高-低分类的网点主要分布在车站西街、兴安北路、鄂尔多斯大街与石羊桥路上。（8）医疗健康服务中，低-高分类的网点主要出现在通道北路、昭乌达路与桥靠西路交叉路口区域上;高-低分类的网点主要分布在兴安北路与兴安南路上。(9）住宿餐饮服务中，低-高分类的网点主要出现在文化宫路与锡林郭勒北路之间，新华东街与乌兰察布东街之间；高-低分类的网点主要分布在车站西街、满都海西巷、兴安北路与兴安南路上。

# 3.2基于供需平衡的生活性服务业空间布局的优化建议

城市生活性服务业的布局是否与居住区相匹配，将直接影响生活在这个城市居民的生活质量，根据上述对各类生活性服务业供给与需求布局匹配性的研究结果，可以得出以下优化布局建议。

（1）从各类生活性服务业的莫兰指数来看，批发与零售服务、文体休闲娱乐服务、住宿餐饮服务的莫兰指数相对较低，因此在即将开始的新一轮城市总体规划中，应该更加注重城市批发与零售服务、住宿餐饮服务与文体休闲娱乐服务的规划布局。

（2）根据各类生活性服务业网点的聚类分布图来看，昭乌达路、鄂尔多斯大街、新华大街、兴安南路以及兴安北路是所有生活性服务业网点布局不合理出现最多的地方，而这几条道路也是呼和浩特市城市中心城区最主要、最重要的几条道路。因此在新一轮的规划布局时，昭乌达路上与鄂尔多斯大街相邻区域的教育培训服务行业、医疗健康服务行业应适当减少，与新希望街道相邻区域的教育培训服务行业应适当增加;鄂尔多斯大街上的教育培训服务行业、批发与零售服务行业应适当减少，金融保险服务行业、文体休闲娱乐服务行业应适当增加；新华大街上的金融保险服务行业、靠近乌兰察布东街的住宿餐饮服务行业应适当减少；兴安南路上的城市休憩服务行业、居民和家庭服务行业、医疗健康服务行业、住宿餐饮服务行业应适当增加;兴安北路上的批发与零售服务行业应适当减少，文体休闲娱乐服务行业、医疗健康服务行业、住宿餐饮服务行业应适当增加。在居住小区布局逐渐向中心城区外围转移的大趋势下，根据各类生活性服务业的供需评价，适当增减这些地区的生活性服务业网点数量，将有助于城市多中心空间结构的形成。

（3）根据各类生活性服务业的特征进行布局，如医疗健康服务、批发与零售服务，这两类生活性服务业都与城市居民的生活息息相关，但是与医疗健康服务的网点相比，批发与零售服务更加基本，因此批发与零售服务网点更应该靠近居民点布局，以服务小区域的居民为主，医疗健康服务网点则更应该布局在交通方便的区位上，以服务更大范围的居民为主。

# 4结果与展望

# 4.1结果

通过对研究区范围内生活性服务业空间布局与集聚特征的研究，以及结合居住小区的分布，基于供需相对匹配的原则评价了研究区范围内的生活性服务业分布现状并提出了优化建议。基本研究结果如下：

（1）从整个研究区范围来看，生活性服务业总体高度集聚，呈现出单中心布局模式，大致以海亮广场为集聚中心。但从街区尺度来看，呈现"多集聚、多核心"的形态：主要分布在中山东路、新华大街、大北街附近街区，生活性服务业核密度值随着与城市中心距离的增加而降低。

(2）呼和浩特市中心城区总体生活性服务业冷热点差异明显且集聚特征显著，生活性服务业热点区在市中心集聚，冷点区则分布在中心城区的外围。通过对各类生活性服务业的方向分布来看，9类生活性服务业的标准差椭圆覆盖范围相差不大，整体都分布在二环以内，且分布重心与长轴方向均大致相同。

（3）各类生活性服务业在不同尺度的空间集聚特征存在明显差异。居民与家庭服务、医疗健康服务、住宿餐饮服务在较大空间范围内表现出集聚特性，区位选择的尺度范围较大，其他几类行业最大集聚范围相对较小。

（4）各类生活性服务业供给与需求呈现显著的空间正相关，教育培训服务、金融保险服务与医疗健康服务的莫兰指数比较大，说明这三类网点布局更加合理。而对于布局区位来说,昭乌达路、鄂尔多斯大街、新华大街等几条重要道路区域的各类生活性服务业网点布局还有很大的改进空间。

# 4.2展望

城市商业、服务业空间布局特征的研究不仅跟城市内部空间结构与形态紧密关联，更与城市居民的日常生活密不可分。本研究运用POI数据、小区数据分析呼和浩特市生活性服务业的空间布局特征并进行供需匹配评价，较客观全面地反映了研究区范围内各类生活性服务业的布局特征以及合理性，能为今后呼和浩特市生活性服务业空间规划布局与结构调整提供一定的参考依据。POI数据中的部分数据是企业以及个体用户在高德地图上进行标注所得到的，因此在进行属性输入时，存在个别误差，且POI数据属于点数据，属性信息中缺少规模信息，因此在后续研究中，需要结合传统统计数据与问卷调查，更加深人的研究其空间分布规律以及与人口分布的耦合协调关系。并在此基础上，探寻影响生活性服务业空间布局特征的人文、自然因素，以及目前城市商业、服务业的空间布局对不同收入阶层日常生活造成的影响会是本文后续的研究重点。

# 参考文献(References)

[1]周麟,沈体雁.大城市内部服务业区位研究进展[J].地理科学进 展,2016,35(4): 409-419.[Zhou Lin, Shen Tiyan.Progress of services location studies in metropolis[J].Progress in Geography,

# 干旱区地理

干半   
2016,35(4): 409-419.] [2]张文忠,大城市服务业区位理论及其实证研究[J].地理研究,   
1999,15(3): 273-281.[Zhang Wenzhong.A study of metropolitan service industry location theory and substantiation[J]. Geographical Research,1999,15(3): 273-281.] [3]王志锋,张维凡,朱中华.中国城镇化70年:基于地方政府治理 视角的回顾和展望[J].经济问题,2019(7):1-8.[Wang Zhifeng， Zhang Weifan,Zhu Zhonghua.7O years of China’s urbanization: Retrospect and prospect from the perspective of local governance [J]. On Economic Problems,2019(7): 1-8.] [4]吴煜,李永浮.居民生活服务业与人口匹配关系研究——基于 上海浦东新区实证研究[J].上海经济研究,2019(2):67-75. [Wu Yu,Li Yongfu.A study on residents life service and population matching relationship:An empirical research of Shanghai Pudong New District[J]. Shanghai Journal of Economics,2019(2):   
67-75.] [5]Lee S,Seo JG,Webster C.The decentralising metropolis: Economic diversity and commuting in the US suburb[J]. Urban Studies,   
2006,43(13): 2525-2549. [6]Dong H W. Concentration or dispersion? Location choice of commercial developers in the Portland metro politan area,20o0—2007 [J]. Urban Geography,2013,34(7): 989-1010. [7]邱灵,申玉铭,任旺兵.北京生产性服务业与制造业的关联及空 间分布[J].地理学报,2008,63(12):1299-1310.[Qiu Ling,Shen Yuming,Ren Wangbing.Industrial relevancy and spatial distribution between producer services and manufacturing in Beijing City [J]. Acta Geographica Sinica,2008,63(12):1299-1310.] [8]申玉铭,邱灵,尚于力.京沪生产性服务业比较研究[J].地理研 究,2009,28(2): 441-450.[Shen Yuming, Qiu Ling, Shang Yuli. A comparative study of Beijing-Shanghai producer service industry [J]. Geographical Research,2009,28(2): 441-450.] [9]薛东前,石宁,公晓晓.西安市生产者服务业空间布局特征与集 聚模式研究[J].地理科学,2011,31(10):1195-1201.[Xue Dongq ian, Shi Ning,Gong Xiaoxiao.Spatial features and agglomeration of producer services in Xi'an City, China[J]. Scientia Geographica Sinica,2011,31(10): 1195-1201.] [10] 李普峰,李同升.西安市生产性服务业空间格局及其机制分析 [J].城市发展研究,2009,16(3):87-91.[Li Pufeng,Li Tongsheng.Spatial patter and mechanism analysis of producer services in Xi'an[J]. Urban Development Studies,2009,16(3): 87-91.] [11] 甄峰,刘慧,郑俊.城市生产性服务业空间分布研究:以南京为 例[J].世界地理研究,2008,17(1):24-31.[Zhen Feng,Liu Hui, Zheng Jun.Spatial distribution of urban producer service:A case study of Nanjing[J]. World Regional Studies,2008,17(1): 24-31.] [12] 杨吾扬.北京市零售商业与服务业中心和网点的过去、现在和 未来[J].地理学报,1994,49(1): 9-17.[Yang Wuyang.The retailing and services center and network of Beijing:Then,now and long before[J]. Acta Geographica Sinica,1994,49(1): 9-17.] [13] 赵向阳,杜洪涛,赵鹏.基于标准化规则的城市 POI数据库建库 研究：以济南市为例[J].城市勘测,2013,8(4):21-24.[Zhao Xiangyang,Du Hongtao, Zhao Peng.Research on building database of urban POI based on normalization rules: Taking Jinan as a casestudy[J]. Urban Geotechnical Investigation& Surveying,   
2013, 8(4): 21-24.] [14] 贾晓婷,雷军,武荣伟,等.基于POI的城市休闲空间格局分析 -以乌鲁木齐市为例[J].干旱区地理,2019,42(4):943-952. [Jia Xiaoting,Lei Jun,Wu Rongwei, et al. Urban recreation space pattern analysis based on POI data: A case study of Urumqi[J]. Arid Land Geography,2019, 42(4): 943-952.] [15]Zhang Xiuyuan,Du Shihong,Wang Qiao.Hierarchical semantic cognition forurban functional zoneswith VHR sateliteimages and POI data[J]. ISPRS Journal of Photogrammetry and Remote Sensing,2017,132: 170-184. [16] Mckenzie G,Janowicz K,Gao S,et al. How where is when? On the regional variability and resolution of geosocial temporal signatures for points of interest[J]. Computers,Environment and Urban Systems,2015,54: 336-346. [17] 陈蔚珊,柳林,梁育填.基于POI数据的广州零售商业中心热点 识别与业态集聚特征分析[J].地理研究,2016,35(4):703-716. [Chen Weishan, Liu Lin, Liang Yutian.Retail center recognition and spatial aggregating feature analysis of retail formats in Guangzhou based on POI data[J]. Geographical Research,2016, 35(4):   
703-716.] [18] 禹文豪,艾廷华,杨敏,等.利用核密度与空间自相关进行城市 设施兴趣点分布热点探测[J].武汉大学学报,2016,41(2):221-   
227.[Yu Wenhao,Ai Tinghua,Yang Min,et al.Detecting“hot spots”of facility POIs based on kernel density estimation and spatial autocorrelation technique[J]. Geomaticsand Information Science of Wuhan University,2016,41(2): 221-227.] [19]冉钊,周国华,吴佳敏,等.基于POI数据的长沙市生活性服务 业空间格局研究[J].世界地理研究,2019,28(3):163-172.[Ran Zhao, Zhou Guohua,Wu Jiamin,et al. Study on spatial pattern of consumer service industry in Changsha based on POI data[J]. World Regional Studies,2019,28(3): 163-172.] [20] 薛冰,肖骁,李京忠,等.基于POI大数据的城市零售业空间热 点分析——以辽宁省沈阳市为例[J].经济地理,2018,38(5):   
36-43.[Xue Bing,Xiao Xiao,Li Jingzhong,et al.POI-based analysis on retail’s spatial hot blocks at a city level: A case study of Shenyang, China[J]. Economic Geography,2018,38(5): 36-43.] [21] 王振坡,牛家威,王丽艳.基于POI大数据的天津市居民居住就 业空间特征及其影响因素研究[J].地域研究与开发,2020,39 (2): 58-63.[Wang Zhenpo,Niu Jiawei,Wang Liyan. Spatial characteristics and influencing factors of residents’residential employment in Tianjin City based on POIdata[J]. Areal Research and Development,2020,39(2): 58-63.] [22] 赵宏波,余涤非,苗长虹,等.基于POI数据的郑州市文化设施 的区位布局特征与影响因素研究[J].地理科学,2018,38(9):   
1525-1534. [Zhao Hongbo,Yu Difei,MiaoChanghong,etal.The location distribution characteristicsand influencing factors of cultural facilities in Zhengzhou based on POI data[J]. Scientia Geographica Sinica,2018,38(9):1525-1534.]   
[23]Lin G,Chen X X,Liang Y T.The location of retail stores and street centrality in Guangzhou China[J].Applied Geography, 2018,100:12-20.   
[24] 李博闻,黄正东,刘稳.基于公交服务需求与供给匹配程度的公 交站点布局评价——以武汉市为例[J].现代城市研究,2019 (5): 99-1O5.[Li Bowun,Huang Zhengdong,Liu Wen. Assessment of the bus stop locations based on the coupling level between demand and supply of bus service:A case study of Wuhan[J].Modern Urban Research,2019(5): 99-105.]   
[25]王法辉.基于GIS 的数量方法与应用[M].北京:商务印书馆, 2009:45-80.[Wang Fahui. Quantitative method and application based on GIS[M]. Beijing: Commercial Press,2009: 45-80.]   
[26]高子轶,张海峰.基于POI数据的西宁市零售业空间格局探究 [J].干旱区地理,2019,42(5): 1195-1204.[Gao Ziyi, Zhang Haifeng.Research on spatial pattern of Xining retail industry based on POI data[J].Arid Land Geography,2019,42(5): 1195-1204.]   
[27] 湛东升,孟斌.基于社会属性的北京市居民居住与就业空间集 聚特征[J].地理学报,2013,68(12):1607-1618.[Zhan Dongsheng,Meng Bin. Spatial clustering analysis of residential and employment distribution in Beijing based on their social characteristics[J].Acta Geographica Sinica,2013,68(12): 1607-1618.] [28]高长春,刘贤赵,李朝奎，等.近20年来中国能源消费碳排放时 空格局动态[J].地理科学进展,2016,35(6):747-757.[Gao Changchun,Liu Xianzhao,Li Chaokui,et al. Spatiotemporal dynamics of carbon emissons by energy consumption in China from   
1995 to 2014[J]. Progress in Geography,2016,35(6): 747-757.] [29] 柳雨杉,董晔.基于指数分析法的乌鲁木齐市居住格局研究[J]. 干旱区地理,2019,42(3): 698-705.[Liu Yushan,Dong Ye.Residential structure of Urumqi City based on index analysis method [J].Arid Land Geography,2019,42(3): 698-705.] [30]马燕飞,沙占江,牛志宁，等.环青海湖区沙漠化土地景观格局 自相关分析[J].干旱区研究,2010,27(6):954-961.[Ma Yanfei, Sha Zhanjiang,Niu Zhining,etal. Spatial autocorrelation analysis on sandy landscape pattern in the peripheral regions of the Qinghai Lake[J].Arid Zone Research,2010,27(6): 954-961.] [31]Christoph T,Tomas R. The evolving concept of retail attractiveness:What makes retail agglomerations attractive when customers shop at them?[J].Journal of Retailing and Consumer Services,   
2008,15(3): 127-143.

# Characteristics and evaluation of the spatial distribution of life service industry in Hohhot City

LI Xiaocan， A Rong， TONG Baoquan (College of Geographical Science,Inner Mongolia Normal University,HohhotOlOO22,Inner Mongolia,China)

Abstract:The urban life service industry is closely relatedto the daily lifeof urban residents.In this study, the central urban area of Hohhot City, Inner Mongolia, China was taken as an example.Multisource urban big data were collcted,and the spatial layout characteristics of the life service industry were analyzed with the kernel density estimation method, local Getis-Ord $G ^ { * }$ index, standard deviation ellipse,and Ripley's $K$ function. Then, bivariate Moran's $I$ was used to evaluate the supply and demand of various life service industries and suggest an optimal layout. The results are as folows.(1) The density of agglomeration centers of the life service industry decreased with increasing distance from the city center.The distribution centers of various life service industries showed roughly the same trend. However, the development was more rapid in east-west directions.(2)There were significant cold and hot clusters in the distribution of the life service industry.Various types of life service industry had different spatial agglomerations at diferent spatial scales.Residential and familyservices,medical health services,and accommodation and catering services showed a large range of space clustering features,and the scale of location selection was relatively large.(3）The supply and demand of all types of life service industries had a positive corelation spatially,but there were significant differences.Under the principle of balance between supply and demand,there were obvious irrational points in the spatial layout of the life service industry on several major roads,such as Zhaowuda Road, Ordos Street,and Xinhua Street.This research can serve as a reference for the future spatial planning and structural adjustment of the service industry in Hohhot City.

Key words: life service industry； POI data; space layout; bivariate Moran's I; Hohhot City