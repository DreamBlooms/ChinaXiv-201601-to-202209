# 基于住房代理数据的城市社会阶层空间异构性研究-以兰州市为例

陈龙，张志斌，常飞，薛彩霞（西北师范大学地理与环境科学学院，甘肃兰州730070)

摘要：随着城镇化的深入发展，收入差距造成的社会阶层分化在城市空间上的分异程度亟需从地理学视角进行检视。通过网络爬虫工具获取兰州市商品住房数据，运用Reardon空间分异方法，研究居住一社会阶层的地理分布特征及其空间分异程度。结果表明：居住一社会阶层的地理分布方面,城关区和七里河区呈现出由中心到外围依次为精英阶层、富裕阶层、中产阶层、低产阶层、贫困阶层的圈层式分布，但存在精英区“侵入”低档住宅圈的现象；安宁区和西固区呈现出以中产、低产阶层为主的混合分布模式。居住一社会阶层的空间分异方面，分异趋势较为显著，七里河区、安宁区和西固区的居住一社会阶层分异明显高于城关区；富裕阶层居住区更倾向于融合，低产阶层居住区则有分异趋势；居住一社会阶层的空间分异随研究尺度的降低变得更为显著。

关 键 词：居住一社会阶层；社会分异；空间熵指数；兰州市

城市社会阶层分化是城市社会地理学经典的研究话题。住房作为刚性需求商品，对消费者的“分选”作用导致同一社会阶层趋向同质空间居住，不同社会阶层形成异质居住空间的现象。居住空间是城市社会空间的重要组成部分，是城市最基本的功能单元。居住空间分布合理与否，不仅关系到宜居型城市的建设目标和社会的和谐稳定，还深刻影响着城市职住分离程度、城市运行效率和交通出行状况。我国正处在新型城镇化转型发展阶段，经济社会体制不断改革、城镇化进程不断加快，城市内部空间经历着剧烈的解组与重构[1]。目前学术界对城市空间的研究大多集中于物质实体空间，对城市空间的构成主体——社会群体的研究还较为薄弱[2],对由此造成的社会阶级固化、社会阶层的代际“遗传”、低阶层人群的资源剥夺等一系列社会问题的关注还远远不够[3]

西方学者对于城市社会群体与居住空间分化的研究起步较早[4],有相对成熟的理论体系和科学的研究方法。在理论体系方面产生了诸如生态学派、新古典主义学派、行为学派、新马克思主义学派等，提出了同心圆、扇形、多核心等经典理论模型[5],并对居住空间分异的现象、过程以及后果进行了大量的实证研究，认为社会等级、家庭类型和种族构成是影响空间分异的主导因素[6],一度成为西方城市社会地理学的主流观点。然而与国外相比，我国社会群体与居住空间分异的形成则具有显著的中国特色。计划经济时期，住房作为社会福利由政府或单位分配，个人选择住房的权利有限，形成典型的职住一体化居住模式[7]，职业地位、权利因素和历史惯性的作用更为突出[8]。改革开放以来,随着经济体制改革和商品房制度的根本性转变，城市居住空间分异出现了新的范式和驱动机制[9]，土地财政、资本市场和社会阶层成为最重要的影响力量[10]。

目前，国内对社会群体与居住空间分异的研究主要集中在四个方面：（1）居住空间分异及影响因素。吴启焰等运用六普数据从社区尺度刻画了南京市八类职业人口的居住空间分异特征，发现呈同心圆式分布,越向郊区分异程度越高[11]。（2）居住空间分异演化过程。陶海燕等[12]借助自下而上的多智能体模型模拟了城市居住空间的演变，发现居住空间分异现象在我国大城市发展中已相当普遍，并认为收入差距的扩大使中低收入阶层在居住空间的区位选择上处于被动地位。（3）特殊群体（城市流动人口)的居住空间分异。如具有“半城市化”性质的城市边缘化群体—农民工[13],因受城市户籍门槛限制，得不到应有的社会保障，无形中成为城市中“无根性”的居住群体，被市场经济无情地推向了城市边缘地带[14],形成特殊的“外乡人”居住空间。（4）居住空间分异与资源公平性配置。罗若愚等从居住分异视角探讨了成都市公共服务设施的不均衡分布，发现不同群体获取公共服务的机会差异十分明显[15],社会资源的公平性配置问题相当突出[16]。

综上所述，我国对居住空间分异现象已有大量的探索，不过，由于对社会群体类型的划分还比较模糊，大多研究往往只重视居住空间本身的分异，而弱化了对空间分异主体一一社会群体的关注，且鲜有文献揭示收入差距造成的居住空间分异现象。因此，本文以兰州市住宅数据为基础，分析城市社会阶层的空间异构性特征，即从居住一社会视角出发，探讨收入差距带来的城市社会阶层分化，以及映射在居住空间上的分异程度，旨在为国内城市居住空间分异的比较研究提供借鉴。

# 1研究区概况与研究方法

# 1.1 研究区概况

兰州市是甘肃省省会，“一带一路”沿线上的重要节点城市。受特定自然环境、历史沿革和城市形态等因素的综合影响，其居住一生产分离和阶层分化与发达城市和平原型城市相比更具特殊性。从居民收入5等分分组来看，兰州市居民收入分配呈典型的“底部大、中间少、顶端小”的金字塔结构[17]2017 年高收入户（ $20 \%$ )的人均可支配收入是低收入户（ $20 \%$ )的3.84倍[18]。可见，居民内部收入差距较大，居住空间分异明显，由此引起的社会阶层分化具有代表性。研究范围为位于河谷盆地的中心城区（图1），即城关区、七里河区、西固区和安宁区，下辖49个街道办和1个高新区。

# 1. 2 数据来源

兰州市商业居住区数据，于2018年10月爬取自房天下（http://lz.esf.fang.com/housing/）,其字段包括居住区名称、9月转让均价、建筑结构、建成年代、建筑面积、绿化率、容积率、物业费、占地面积、卫生服务。居住区坐标信息与部分面积信息来源于高德开放平台（https://lbs.amap.com/），其中对非商品房(单位房、政府房、商品房和安置房等)进行剔除，共获得1463个商业居住区信息；“城中村"数据在2018年10月的谷歌影像中通过目视解译[19]获取。具体操作方法：采用均值漂移分割算法对谷歌影像实现分割，然后利用决策树分类算法实现土地利用类型分类，再基于 $0 . 1 ~ \mathrm { k m } \times 0 . 1 ~ \mathrm { k m }$ 窗口统计中心城区不同类型居住区标准差信息，共获得101个“城中村”。对各类数据进行整理如表1所示，其中住宅分类标准在研究方法中予以说明。

![](images/b095c69c6518a0bb9c6f068876f8928e0ce5e6934bc8a9916addcbf06478ee7b.jpg)  
图1兰州市中心城区区位图  
Fig.1Location map of central urban area of Lanzhou

# 1.3 研究方法

1.3.1居住一社会阶层划分方法房地产价格对城市居住空间分化起到重要的“分选”与“过滤”作用，城市住房的类型和档次与居住群体存在紧密联系[20-21]。城市不同区域的房价差异,既是社会空间分异的结构化表征与市场化反应，也是推动社会空间再分化的重要驱动机制[22]。因此,依据住房均价、容积率、绿化率、物业费、建成年代、卫生服务6类指标对居住区进行分层聚类，考虑到别墅区与城中村的特殊性，在聚类时暂不考虑。具体聚类方法为Q聚类的组间联接方法，用Z-scores方法将数据进行无量纲化处理，度量标准采用欧氏距离平方，将兰州市商业居住区划分为高中低3个档次。同时，参考吴启焰等[23]和蒋亮等[2]的社会一空间划分标准，依据居住空间上的映射关系，将社会阶层划分为：别墅一精英阶层、高档住宅一富裕阶层、中档住宅一中产阶层、低档住宅一低产阶层和城中村一贫困阶层5个类型。

表1居住区数据分布表  
Tab.1Distribution table of residential space data   

<html><body><table><tr><td>住宅分类</td><td>数量/个</td><td>数量占比/%</td><td>面积/km²</td><td>面积占比/%</td></tr><tr><td>别墅</td><td>2</td><td>0.13</td><td>11. 72</td><td>1.38</td></tr><tr><td>高档住宅</td><td>86</td><td>5.50</td><td>19.43</td><td>2.29</td></tr><tr><td>中档住宅</td><td>1 124</td><td>71.87</td><td>32.06</td><td>37.81</td></tr><tr><td>低档住宅</td><td>251</td><td>16.05</td><td>29.27</td><td>34.52</td></tr><tr><td>城中村</td><td>101</td><td>6.46</td><td>20.35</td><td>24.00</td></tr><tr><td>合计</td><td>1 564</td><td>100</td><td>112.83</td><td>100</td></tr></table></body></html>

# 1.3.2 Reardon 分异指数方法 （1）空间熵指数

（ $\smash { \widetilde { H } _ { \mathrm { o } } }$ 空间熵指数又称为空间信息理论分异指数(spatial information theorysegregation index），是REARDON和O'SULLIVAN于2004年推出的衡量空间均衡性的指标[24]。 $\widetilde { H }$ 指数对于处理空间邻近关系和地理尺度变化具有较大的优势，其本质是通过空间均匀性维度计算局部区域内空间权重族群的构成[25]

$$
\widetilde { H } \ = \ 1 \ - \frac { 1 } { T E } \int _ { p \ f e R } T _ { p } \widetilde { E } _ { p } \ \mathrm { d } p
$$

$$
\widetilde { E } _ { p } = - \sum _ { m } ^ { M } \ ( \widetilde { Y } _ { p m } ) \log _ { m } ( \widetilde { Y } _ { p m } )
$$

$$
\widetilde { Y } _ { p m } \ = \ \frac { \displaystyle { \int _ { q \in R } T _ { q m } \varphi ( p , q ) \mathrm { d } p } } { \displaystyle { \int _ { q \in R } T _ { q } \varphi ( p , q ) \mathrm { d } p } }
$$

$$
\varphi ( p , q ) = \left\{ \begin{array} { c c } { \displaystyle { \Big [ 1 - \Big ( \frac { d ( p , q ) } { r } \Big ) ^ { 2 } \Big ] ^ { 2 } } } & { \mathrm { i f ~ } d ( p , q ) < r } \\ { \displaystyle { 0 } } & { \mathrm { o t h e r w i s e } } \end{array} \right.
$$

式中： $\widetilde { H }$ 为空间熵指数，表示分异程度大小; $R$ 表示全区域; $T$ 表示 $R$ 区域内的居住区总面积; $E$ 是研究区内所有居住区整体的熵; $T _ { _ { p } }$ 表示 $p$ 区域内的面积； $\widetilde E _ { { p } }$ 表示局部空间 $p$ 内的熵,如果在区域 $p$ 中，周围所有的居住区都是来自于同一个阶层，那么所有的 $\widetilde { E } _ { p } = 0$ ，则 $\stackrel { \sim } { \cal H } = 1$ ,表示不同阶层完全分异,反之，$\widetilde E _ { _ p } = 1 , \widetilde H = 0$ ，表示完全融合; $M$ 表示居住一社会阶层数量， $\widetilde { Y } _ { p m }$ 表示 $p$ 区域中 $m$ 阶层内出现其它阶层的比例； $\varphi ( p , q )$ 是二元加权邻近性函数, $d ( p , q )$ 是两点 $p$ 和 $q$ 之间的欧式几何距离， $r$ 是距离半径。

（2）空间相对多样性指数 $( \stackrel { \sim } { R } )$ ,公式为：

$$
\widetilde { R } = 1 - \int _ { p \in R } \frac { T _ { p } \tilde { I } _ { p } } { T I } \mathrm { d } p
$$

（3）空间分异指数 $\smash { \widetilde { D } _ { \circ } }$ 公式为：

$$
\widetilde { D } = \sum _ { m = 1 } ^ { M } \int _ { p \in R } \frac { T p } { 2 T I } \mid \widetilde { Y } _ { p m } - Y _ { m } \mid \mathrm { d } p
$$

式(5)和(6)中: $\tilde { I } _ { { p } }$ 为空间加权交互指数,其他符号与上文相同。

$\widetilde { R }$ 指数与 $\widetilde { D }$ 指数为衡量局部区域居住阶层的构成与全局居住阶层构成的平均差异。Reardon与O'Sullivan建立衡量空间均匀性与空间接触性的指标体系，致力于解决居住分异中棋盘问题和MAUP问题（指分异指数的计算结果因所选分区的规模及特定边界造成的差异)[26-27]。为了行文简洁,下文中将 $\widetilde { \cal H } , \widetilde { \cal D } , \widetilde { \cal R }$ 分别写为 $H , D , R$ 。

# 2居住一社会阶层的地理分布

# 2.1城关区和七里河区呈圈层式分布

运用ArcGIS软件做不同社会阶层居住区的核密度(图2），以此审视居住一社会阶层的空间分布特征。可以看出，城关区与七里河区居住一社会阶层总体呈圈层式分布，并且存在精英区“侵入”低档住宅圈的现象。城关区内部从圈层核心向外依次是高档一富裕阶层、中档一中产阶层、低档一低产阶层与别墅一精英阶层混合分布、城中村一贫困阶层，表明社会地位越高的社会群体越倾向于在城市中心分布，而低产阶层和贫困阶层被边缘化。七里河区居住一社会阶层圈层式结构不如城关区明显，靠近七里河区政府附近有一定数量的高档一富裕阶层分布；中档一中产阶层主要分布在七里河区西北与安宁区交界处，低档一低产阶层与之相反，主要分布在与城关区交界偏南部区域,包括华林坪、五星坪和龚家湾等。其中，别墅住宅区仅有两处且都处于城关区的雁滩，包括位于雁北黄河大桥以南的鸿运润园居住区别墅区和雁北黄河大桥以北的银河国际居住区别墅区，该区域主要是中、低、贫困三类阶层交叉分布地带。

![](images/4bb6c72f4f18463c68d6df13225e951328b5832bd307865dc62fea503d141a3d.jpg)  
干吴区地理  
图2各类社会群体居住区核密度图

# 2.2安宁区和西固区呈混合分布

安宁区与西固区居住一社会阶层分布情况较为复杂，以中档一中产阶层、低档一低产阶层和城中村一贫困阶层为主，趋向于混合分布，且城中村的边缘化特点显著。安宁区作为科教文化区和高新技术工业区，近儿年城镇化速度较快，开发了大量的居住用地，吸引部分较高收入者入住，中档一中产阶层不断集聚。但受历史因素影响，原有居民多为农民，使得安宁区中心区域内仍存在大量的城中村，因而呈中、低、贫困阶层的混合分布；如兰天公寓（西北师大学生公寓)附近，以北为属于城中村的水挂庄，以西为属于中档住宅区的安宁科教城，以南为低档住宅区的康居小区，混合分布特征明显。西固区与安宁区分布特征类似，但居住一社会阶层结构相对较为单一，呈现出以低档一低产阶层为主、中档一中产阶层和城中村一贫困阶层为辅的混合分布特征。究其原因，西固区位于中心城区西郊，是中国西部最大的石油化工基地和兰州市的核心工业区，城区功能结构较为单一，城市居民以面广量大的各企业普通员工为主，受企业改制及宏观经济环境的影响，收入整体不高。

# 3居住一社会阶层的空间分异

# 3.1全局分异程度：居住一社会阶层空间分异较为显著

基于R语言开发的seg包（空间分异测量的方法集成模块）中的spseg包装函数（wrapperfunction）[28],以街道尺度为研究的基本单元,统计街道辖区内各社会阶层居住区的面积，以此度量空间分异状况。计算得到 $D$ 指数为 $0 . 6 9 9 \ 6 , R$ 指数为$0 . 5 1 6 7 , H$ 指数为0.5218，根据西方城市的经验，指数在0.5以上居住分异比较高[27],表明兰州市居住一社会阶层分异程度较高。为了进一步考察各个阶层的具体分异情况，计算所有阶层两两之间的 $H$ 指数，并将每个阶层居住区面积与其余阶层的居住区面积之和作为两个单独变量，计算其Reardon指数（图3）。从分布特征可以看出，Reardon指数呈明显的倒"N"型结构，相对于 $H$ 和 $D$ 指数, $H$ 指数的表现更为平稳。因此以 $H$ 指数为主讨论社会一阶层分异状况， $R$ 指数和 $D$ 指数作为参考指标。

从具体的 $H$ 指数的数值来看，富裕阶层居住区更倾向于融合，低产阶层居住区则有分异趋势。别墅一精英阶层、中档住宅一中产阶级与城中村一贫困阶层的 $H$ 指数均接近于0.5，表明其分异水平相近，不过不应忽略别墅住宅区仅有两处而城中村多达上百个，数量上的差异可能会在一定程度上掩盖其分异水平；低档住宅一低产阶层的H指数达到

![](images/e3492f3750b3facb1e5d61c6c7864c84b5929ea4ed1c14d6b58d7af35e7a560c.jpg)  
Fig.2Kernel density of residential space of various social groups   
图3不同居住一社会阶层分异指数Fig.3Index of residential-social segregation

0.6，说明其社会阶层与其它阶层之间的分异程度最为显著;高档住宅一富裕阶层的 $H$ 指数最低，仅为0.189，反映出高档一富裕阶层与其他阶层的融合度较高。综上，兰州市阶层之间的分异呈现出孤立的精英阶层、融合的富裕阶层与中产阶层、趋于分离的低产与贫困阶层的特征。

# 3.2局部空间分异：居住一社会阶层分异呈不连续的圈层结构

为了测度各行政区内居住一社会阶层分异程度，计算其各自的分异指数(图4)。结果表明，城市中心区的分异度低于城市边缘区，反映出与各阶层的地理分布特征相近。城关区分异较低。城关区是兰州市发展较早的老城区，是政治、经济和文化中心，集中了全市优质的公共服务设施，同时旧城改造和“出城入园”的力度最大，中心区域空间的品质提升也最为显著，在房地产价格“分选”机制下，中档一中产阶层与高档一富裕阶层相互“嵌套”，消费能力较低的低档一低产阶层和贫困阶层逐渐被推向外围地区，但部分低档一低产阶层零星点缀其中，形成了城关区的居住一社会阶层分异相对较低的现象。

城市边缘区分异偏高。七里河区、安宁区和西固区的居住一社会阶层分异明显高于城关区。原因在于安宁区与西固区距离城市中心区较远，受地理条件限制，其独立性较强;在城市化快速推进过程中，七里河区是最先承接中心区商业功能外溢的区域，导致其内部建设往往良莠不齐,新开发的较高档次的商业居住区逐渐“侵入”原有的农村居住区，形成半城市化的村庄式社区与各类档次的新型居住社区并存的现象。

为了进一步探析居住一社会阶层分异的区域差异，将研究区划分为 $2 \ \mathrm { k m } \times 2 \ \mathrm { k m }$ 的格网（共60个），作为计算分异指数的基本单元，以期更为细致地揭示其空间分异状态。具体操作过程为：首先，将研究区域划分为 $0 . 5 ~ \mathrm { k m } \times 0 . 5 ~ \mathrm { k m }$ 方格网（假设居住区都为正方形，则其平均边长为 $2 4 6 \mathrm { ~ m ~ }$ ，以 $0 . 5 \ \mathrm { k m }$ 为边长可以避免跨越格网带来的归属误差);其次，为了更好的归属位于格网边界处的居住区，在ArcGIS中做每个居住区的缓冲区（缓冲半径 $\mathbf { \Sigma } = \mathbf { \Sigma }$ √居住区平均面积 $\overline { { \pi } }$ );最后，将居住区的面状缓冲区与方格网求交集。其中，城中村本身为面状数据，只需进行最后一步（图5）。

![](images/c3a183b512eefe1f80776779c11e1f1d05170a1192430524b2a1f486a3a865a0.jpg)  
图4各个行政区居住分异 $H$ 指数

由图5可知，兰州市居住一社会阶层空间分异程度整体上表现出中心低、外围高的圈层特征，既与区级尺度的研究结果相同，即城市中心区居住一社会阶层分异较低，越到边缘区分异程度越高，也与经典的城市地价曲线的变化趋势相同，表明社会群体的支付能力是造成居住一社会阶层圈层式分异的主要诱因。但这一分异特征并不是连续的，原因在于受广泛分布的城中村和相对独立的区级中心的阻隔。如空间信息熵指数 $H$ 高于0.8的区域几乎全都指向了城中村连片分布区域，进一步表明城中村是影响社会阶层空间异构性的主要因素。

# 3.3尺度效应：空间分异随研究尺度的扩大而下降

在人文地理学研究中，不同的研究尺度会导致不同的结果，居住一社会阶层空间分异也不例外。为此，本文由小到大分别从 $0 . 5 \ \mathrm { k m } \times 0 . 5 \ \mathrm { k m }$ 格网、$1 \ \mathrm { k m } \times 1 \ \mathrm { k m }$ 格网、街道尺度(平均面积为 $4 . 2 6 ~ \mathrm { k m } ^ { 2 }$ ）、区级尺度（平均面积为 $5 3 . 2 6 ~ \mathrm { k m } ^ { 2 }$ )四个层面进行分析(图6）。

通过图6比对 $0 . 5 \ \mathrm { k m } \times 0 . 5 \ \mathrm { k m }$ 尺度( $H =$ 0.687 8) $\ 、 1 \ \mathrm { k m } \times 1 \ \mathrm { k m }$ 尺度( $\ : H = 0 . 5 5 2 \mathrm { ~ 9 ~ }$ ）、街道尺度（ $\scriptstyle H = 0 . 5 2 1 \ 8 \ \rangle$ 和区级尺度（ $\left. H = 0 . 0 8 9 \ 3 \right)$ 后，发现兰州市中心城区居住一社会阶层空间分异水平在前三个尺度上分异不大，而在区级层面下降明显。表明宏观尺度下空间分异具有显著弱化现象，微观尺度更能反映出空间分异的客观现实，印证了在研究阶层分化时对MAUP问题的影响不容忽视，即运算过程中会因不同的测度尺度而导致不同的研究结果，必须重视微观尺度的研究。

![](images/5dff1a2a59df0d70f7c541660564890a4c84f2b95fe1dd1fb2b5aa367c89331b.jpg)  
Fig.4 $H$ index of residential segregation by districts   
图5居住一社会阶层的局部空间分异  
Fig.5Local spatial differentiation of residential-social stratum

![](images/56240357b0e168b788854f9073662097731c91cf17e7897905b7aff64b36044f.jpg)  
图6不同尺度下居住一社会阶层分异指数Fig.6Segregation index of residential-social rankon different scales

# 4结论与讨论

# 4.1结论

本文基于住房档次和社会阶层相互锁定的假设，利用互联网获取居住区属性数据，并计算空间分异指数，据此分析了兰州市中心城区社会阶层空间异构性的特征。结果表明：（1）地理分布方面，城关区和七里河区的居住一社会阶层分布以城市中心区的高档一富裕阶层为核心，并按社会阶层等级依次向外递减，但精英区有“侵人”低档住宅圈的现象。安宁区和西固区的居住一社会阶层以中低阶层为主，不同阶层混合分布特征更为明显。（2）空间分异方面，全局视角下居住一社会阶层的空间分异呈现出孤立的精英阶层、融合的富裕阶层与中产阶层、趋于分离的低产与贫困阶层的特征；局部视角下，居住一社会阶层空间分异在城市中心区较低，而在城市边缘区较高，且受分布广泛的城中村影响，呈不连续的圈层结构特征。（3）尺度效应方面，在$0 . 5 ~ \mathrm { k m } \times 0 . 5 ~ \mathrm { k m }$ 格网 $\ 、 1 \ \mathrm { k m } \times 1 \ \mathrm { k m }$ 格网、街道尺度、区级尺度四个层面上，居住一社会阶层的空间分异水平随着研究尺度的扩大而下降，且在区级层面上下降尤为明显。

# 4.2讨论

文章利用居住区属性数据，分析了兰州市不同社会阶层的地理分布特征、整体分异水平和局部分异状况，一方面是对城市居住空间研究的补充，另一方面也从居住分异的社会关系与实体空间的互动模式中印证了“社会一空间辩证法（Social-spatialDia-lectics)”理论，即社会的空间化与空间的社会化是相互促进的。市场经济促使社会结构发生转变，住房的市场化又催生了社会群体空间的分化，形成居住一社会阶层的空间分异。需要指出的是，这种分异会产生对阶层本身的固化效应和对迁入群体的排挤效应，随着社会阶层差距逐渐拉大，居住隔离逐渐会演化成社会隔离，形成“代际遗传”，导致社会问题越来越严重，急需引起社会各界的关注。

基于此，本文提出以下调控建议：（1）加强住房的市场化运行和行政化监管的双轨制共同管理模式。为了避免收入扩大引起的阶层分化演变为西方式的种族隔离现象，一方面应充分发挥市场机制的杠杆作用，最大限度地激发房地产业的发展活力；另一方面，建立健全国土空间规划体系，合理确定各类土地的年度利用计划,加强土地使用的监管执法，保障房地产业的健康持续发展。（2）倡导不同社会阶层混合居住模式。各阶层混合居住是解决目前居住分异的一种有效途径，可以为低收入人群提供与中高收入阶层相同的居住空间，享受均等的公共服务，有助于增加不同阶层群体的交往机会，促进社会的和谐发展。（3）拓宽低收入阶层群体的就业机会[29]。积极开展职业技能培训工作,提升低收入阶层的整体素质；同时，大力发展服务业，构建多层次的消费服务，增加低收入阶层的就业机会。

此外，文章还存在一些不足之处：社会阶层分化更多的是表现在个人与群体之间，由于缺乏对个人日常行为轨迹数据的实地调研，导致无法从更微观的尺度进行阶层分化特征的测度；由于制度因素难于量化，也缺乏有效的评估方法，使得难以检测制度因素和市场化因素对社会阶层分异的影响；数据处理过程中对于住房价格的炒作虚假信息无法有效剔除。

# 参考文献(References）

[1］刘望保,翁计传.住房制度改革对中国城市居住分异的影响 [J].人文地理,2007,22(1）:49-52.[LIUWangbao,WENGJichuan.The impact of housing system reform on urban residential differentiation in China［J].Human Geography,20O7,22（1）： 49 -52.]   
[2］蒋亮,冯长春.基于社会一空间视角的长沙市居住空间分异研 究[J].经济地理，2015，35（6）：78-86.[JIANGLiang，FENG Changchun.Research on the differentiation of residential space in Changsha City based on social-spatial perspective[J].Economic Geography,2015,35(6) :78-86.]   
[3]GUSTAFSSON B,KATZ K,OSTERBERG T.Residential sgregation from generation to generation： Intergenerational association in socio-spatialcontext among visibleminoritiesandthe majoritypopulation in metropolitan Sweden[J].Population,Space and Place, 2017,23(4) :e2028.   
[4]JOHNSTON R,POULSEN M,FORREST J. The geography of ethnic residential segregation：A comparative study of five countries [J]．Annals of the Association of American Geographers,2007,97 (4) :713 -738.   
[5］韩莉.基于居委会尺度五普数据的南京市新移民居住空间分 异研究［D]．南京:南京师范大学,2016.［HANLi．Studyon the differentiation of living space of new immigrants in Nanjing based on the five-pile data of the neighborhood committee［D]. Nanjing:Nanjing Normal University,2016.]   
[6］陈燕.中外大中城市居住空间分异的动因比较分析[J].现代 城市研究,2008,23（12）:62-66.[CHEN Yan．Comparative analysis of the motivation of differentiation of residential space in Chinese and foreign large and medium cities[J].Modern Urban Research,2008,23(12）:62-66.]   
[7］杨永春,孟彩红.1949 年以来中国城市居住区空间演变与机制 研究——以河谷盆地型城市兰州为例[J].人文地理,2005, （5）:43-49.[YANG Yongchun,MENG Caihong.Study on the spatial evolution and mechanism of urban residential areas in China since 1949:Taking the valley cityof Lanzhou as an example[J]. Human Geography,2005,（5）:43-49.]   
[8］张海东,杨城晨.住房与城市居民的阶层认同—基于北京、 上海、广州的研究［J].社会学研究,2017（5）：39－63. [ZHANG Haidong,YANG Chengchen．The classidentity of housing and urban residents:Based on studies in Beijing,Shanghai and Guangzhou[J].Sociological Studies,2017(5）:39-63.]   
[9］伍俊辉.1949年以来兰州市居住区变迁与发展趋势研究[D]. 兰州：兰州大学,2007.［WU Junhui.Research on the change and development trend of residential areas in Lanzhou since 1949[D]. Lanzhou:Lanzhou University,2007.]   
[10］张庭伟.1990 年代中国城市空间结构的变化及其动力机制 [J].城市规划,2001,25（7）:7-14.[ZHANG Tingwei.Changes and dynamic mechanism of urban spatial structure in China in the $1 9 9 0 \mathrm { s } [ \mathrm { J } ]$ .City Planning Review,2001,25(7）:7-14.]   
[11]WU Q,CHENG J,CHEN G,et al. Social spatial diferentiation and residential segregation in the Chinese city based on the 2000 community level census data:A case study of the inner city of Nanjing [J]. Cities,2014,39:109 - 119.   
[12］陶海燕,黎夏,陈晓翔,等.基于多智能体的地理空间分异现象 模拟——以城市居住空间演变为例[J].地理学报,2007,62 (6):579 - 588.[TAO Haiyan,LI Xia,CHEN Xiaoxiang,et al. Simulation of geospatial differentiation based on multi-agent：Taking the evolution of urban residential space as an example[J].Acta Geographica Sinica,2007,62(6）:579-588.]   
[13]LIU L,HUANG Y,ZHANG W. Residential segregation and perceptions of social integration in Shanghai,China[J]. Urban Studies,2017,55(7) :1484-1503.   
[14］杨菊华,朱格.心仪而行离—流动人口与本地市民居住分异 研究[J].山东社会科学,2016,（1）:78-89.[YANG Juhua, ZHU Ge.Aspirations and differences;A study on the differentiation of floating population and local citizens[J]. Shandong Social Sciences,2016,（1) :78 -89.]   
[15］罗若愚,刘怡,踪家峰.居住分异下成都公共服务设施空间布 局研究[J].西南交通大学学报（社会科学版）,2018,19（2）： 68-77.[LUO Ruoyu,LIU Yi,ZONG Jiafeng. Study on the spatial layout of Chengdu public service facilities under residential differentiation[J].Journal of Southwest Jiaotong University（Social Science Edition）,2018,19(2）:68-77.]   
［16］孙卓.居住与公共服务设施空间分异研究一 一以合肥市滨湖 新区为例[D]．合肥：合肥工业大学,2016.［SUN Zhuo．Study on the spatial differentiation of residential and public service facilities:Taking the new area of Binhu in Hefei as an example[D]. Hefei:Hefei University of Technology,2016.]   
[17］张雪.兰州市扩大中等收入群体比重的对策研究[D].兰州： 兰州大学,2015.[ ZHANG Xue.Research on the countermeasures of expanding the proportion of middle-income groups in Lanzhou City[D].Lanzhou:Lanzhou University,2015.]   
[18］兰州市统计局.兰州统计年鉴(2018)[M].北京:中国统计出 版社,2O18.［Lanzhou Statistics Bureau.Lanzhou statistical yearbook(2018）[M]．Beijing：China Statistical Publishing House, 2018.]   
[19］邓刘洋,沈占锋,柯映明.城市建成区遥感影像边界提取与扩 张分析[J].地球信息科学学报,2018,20（7）：996－1003. [DENG Liuyang,SHEN Zhanfeng,KE Yingming. Boundary extraction and expansion analysis of remote sensing images in urban construction area[J].Journal of Geo-Information Science,2018,20 （7) :996 -1003.]   
[20］王洋,方创琳,盛长元.扬州市住宅价格的空间分异与模式演 变[J].地理学报,2013,68（8）:1082-1096.[WANG Yang, FANG Chuanglin,SHENG Changyuan. Spatial differentiation and model evolution of housing price in Yangzhou City[J].Acta Geographica Sinica,2013,68（8）:1082-1096.]   
[21］黄怡.城市居住隔离的模式—兼析上海居住分异的现状 [J].城市规划学刊,2005,（2）:31-37.[HUANG Yi.The mode of urban residential differentiation:Analysis of the status quo of Shanghai'sresidential diferentiation[J]. Urban Planning Forum, 2005,(2):31-37.]   
[22］宋伟轩,毛宁,陈培阳,等.基于住宅价格视角的居住分异耦合 机制与时空特征一 一以南京为例[J].地理学报,2017,72（4)： 589- 602.[SONG Weixuan,MAO Ning,CHEN Peiyang,et al. The coupling mechanism and spatial and temporal characteristics of residential differentiation based on the perspectiveof residential price:Taking Nanjing as an example[J]. Acta Geographica Sinica, 2017,72(4) :589 -602.]   
[23］吴启焰,崔功豪.南京市居住空间分异特征及其形成机制[J]. 城市规划,1999,（12）:23-26.[WU Qiyan,CUIGonghao.The diferentiation characteristics of residential space in Nanjing and its formation mechanism[J]. City Planning Review,1999,（12）:23- 26.]   
[24]REARDON S F,O'SULLIVAN D. Measures of spatial segregation [J].Sociological Methodology,2004,34（1）:121-162.   
[25］孙秀林,施润华,顾艳霞.居住分异指数回顾：方法、计算、示例 [J].山东社会科学,2017,（12）:98-105.[SUN Xiulin,SHI

[28]HONG S Y,O'SULLIVAN D,SADAHIRO Y. Implementing spatial segregation measures in R[J].PLoS One,2014,9（11）： e113767.

Runhua,GU Yanxia.Review of residential differentiation index: Method,calculation and example[J].Shandong Social Sciences, 2017,(12):98-105.]   
[26]WHITE MJ. The measurement of spatial segregation[J].American Journal of Sociology,1983,88(5） :1008-1018.   
[27]MASSEY DS,DENTON NA.The dimensions of residential segregation[J].Social Forces,1988,67(2）:281-315.

[29］刘争光，张志斌.兰州城市居住空间分异研究[J].干旱区地 理,2014,37（4）:846-856.[LIUZhengguang，ZHANG Zhibin. Study on the differentiation of urban residential space in Lanzhou [J].Arid Land Geography,2014,37(4) :846 -856.]

# Spatial heterogeneity of urban social classes based on housing agency data : Taking Lanzhou City as an example

CHEN Long， ZHANG Zhi-bin， CHANG Fei， XUE Cai-xia(CollegeofGeographyandEnvironmentalScience,NorthwestNormalUniversity,Lanzhou73oo7o,Gansu,China)

Abstract:Since the reform and opening up,China's economy has been continued to grow,the process of urbanization in China keeps being accelerated,andthe income gap of urban residents is widening.Along with the demolition of the original urban housing,the pasive relocation of the urban residents,the pluralistic social groups are reconstructed in the diverseurban space and commodity communities.The role of sorting and filtering on the urban residents leads to the same social stratum tends to live in the same space,the phenomenon of diferent social strata forming heterogeneous living space,resulting in the diferentiation of diffrent social groups in the living space.As a result,the degree of diferentiation of social strata needs tobe examined from theperspective of geography.In order to analyze the spatial diferentiation of urban social strata,taking Lanzhou City,Gansu Province,Chinaasan example,this paper discusses the differentiation of urban social strata brought about by income gap as well asthe degree of differentiation of urban social strata mapped in residential space.The data of commercial housing in Lanzhou were obtained by means of network crawler tools.The geographical distribution characteristicsand spatial differentiation degree of residential strata were studied byusing Reardon spatial diffrentiation method.The results show that：in terms of thegeographical distribution of residential-social strata,Chengguan Districtand Qilihe District showacircular distributionof elite,wealthy,middle,lowand poor groups from thecenter to the periphery.But there is the phenomenonof“invading”low-graderesidential circlein elitearea；thedistributionof residential-social stratum in Anning District and Xigu District is complicated,with mainly middle-middle class,low-midde class and urban village-poorclas,and tends toamixed distribution,andthe marginalized characteristics of the village inthecityare remarkable.In theaspectof spatialdiferentiationofresidential-social strata,therich-classresidential areasare moreinclined to merge,and the low-class residentialareashave the tendencyof differentiation.Theresidential-social class diffrentiation in Qilihe,Anningand Xigu Districts isobviously higher thanthatinthe Chengguan District with thecharacteristics ofthe isolated eliteclas,the fusion ofthe rich and middle clas,the tendency to separate the low-yield and the poor class;The diference between residential and social strata in the urban center is lower, andthe degree of diferentiation from the edge is higher,showing the discontinuous structure of the circle.The spatial differentiationof residential-social strata becomes more significant with thedecrease of theresearch scale,which indicatesthatthespatialdiffrentiationinmacro-scalewillead todiferentresearch resultsdue tothedifrent measure scales,and the spatial diferentiation in macro-scale has asignificant weakening phenomenon.Micro-scale can reflect the objective reality of spatial differentiation.

Key words:residence-social class；social differentiation； spatial entropy index；Lanzhou City