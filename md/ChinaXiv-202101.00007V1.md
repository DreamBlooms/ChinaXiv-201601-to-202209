# 基于POI的住宿业时空格局演化及与旅游景点的空间关联研究

陈洪星}²，杨德刚¹，徐红涛¹²，霍金炜1(1中国科学院新疆生态与地理研究所,荒漠与绿洲生态国家重点实验室,新疆乌鲁木齐830011;2中国科学院大学，北京101408)

摘要：以乌鲁木齐市住宿类P0I(2012年、2018年)为研究对象，利用核密度法和标准差椭圆法探究住宿设施时空演变特征，在此基础上从旅游地域系统角度出发，利用分形维数模型和相关数据统计分析方法测度住宿设施与旅游吸引物的空间耦合情况，旨在为城市住宿和旅游空间优化提供科学参考。结果显示：(1)主城区住宿设施总体沿河滩路、阿勒泰路等重要交通路线分布，数量明显增长，米东新区等地有演变为外围集聚中心的趋势。(2)住宿设施总体向东北方向移动，轴向集聚转为离散分布,2012年各类型空间分布方向和范围差异较大,2018年三星级和经济型空间离散化趋势最为明显。(3)普通型住宿设施由孤立核模式演变为带状多核模式，呈现明显的中心集聚一外围扩散趋势；经济型酒店由点状集聚转变为带状集聚。(4)住宿设施与旅游景点的空间耦合性较高，在主要道路缓冲区内具备较强的空间协调性，旅游地域系统处于单中心集聚发展的初级阶段，分形结构有待优化。

关键词：POI；住宿业；旅游景点；聚集分形；乌鲁木齐市 文章编号：

住宿设施的空间分布格局是住宿产业在城市社会空间上的投影，研究住宿业的时空演化可以揭示住宿产业的空间分布特征、规律，进而优化住宿产业格局，合理规划住宿产业规模，指导城市住宿空间有序发展[1]。相关研究源于20世纪70年代，国外研究者从酒店的宏微观选址[2-3]、住宿业时空演化[4]、住宿设施分布的影响因素[5-6等方面给出科学理论和研究范式。国内学者对酒店住宿业布局研究稍晚，主要集中在经济类、星级酒店等区位选择以及影响因素的分析[7-10]等方面，也有学者探究酒店的空间格局演化与区位预测["]、区域差异特征[12]、空间可达性研究[13]等方面。然而以上研究均基于单一要素一即住宿设施本身被视作考察对象，事实上住宿业除了代表区域进步和投资机会外[14],更是旅游产业的重要环节[15]。如根据龙飞等人对长三角地区民宿设施的研究，影响住宿业分布格局的诸多要素中，A级旅游景区数量对住宿设施集聚具有显著影响；再如GUTIERRE等人对巴塞罗那的研究发现，当地酒店布局更多地利用了靠近城市主要旅游景点这一区位优势，而非集聚在相似酒店周围[4。但在以往研究中无论是传统的区域旅游竞争力测评抑或是住宿产业分布影响因子体系构建，二者均被作为影响对方的一个评价因子，缺乏对二者空间分布关系的实证研究及分布规律的归纳总结，即如何阐释区域住宿设施与旅游景点之间的空间关系？旅游地域系统是由旅游吸引物和服务设施共同构成的开放性、自组织的复杂系统[17],因此可以从系统的角度考虑，将住宿设施与旅游景点视为旅游地域系统的子系统，二者的空间布局关系及耦合情况决定了旅游地域系统的结构和功能，进而影响区域旅游发展水平和服务水平。

目前有关旅游景区的文献往往以A级景点[18-19]作为考察对象，缺乏对普通景点的关注，这显然不利于政府和企业决策者在宏观层面上把握城市的旅游结构。普通景点为市民及游客提供了更多休闲、游憩的选择，应当被纳入旅游子系统。而且当前基于地理位置的大数据(POI)可以便捷地获取,这也进一步加深了对旅游地域系统宏观格局的把握。另一方面现有案例多集中于东、中部城市或都市圈，对于西部大城市乌鲁木齐的住宿业时空格局演化以及旅游地域系统的分析鲜有涉及，因此本文以乌鲁木齐市作为案例进行研究。以往不少学者认为乌鲁木齐在整个新疆旅游地域系统内常被视作外地游客赴疆旅游的集散地,其内部旅游景点及相关服务设施的分布往往被忽略[20-21]。近年来，乌鲁木齐作为首府城市，不断挖掘特色旅游产品，完善旅游服务功能，加之政府政策导向，其“集散地”的功能不断被削弱，“目的地”的功能不断被加强，城市内部独具特色的旅游景点、相关服务设施持续吸引外地来乌游客，2018年全年接待各地游客$4 6 . 2 4 \times 1 0 ^ { 6 }$ 人次，比上年增长 $4 0 \%$ ,旅游总收入 $6 9 4 \times$ $1 0 ^ { 8 }$ 元，比上年增长 $54 \%$ ,占新疆旅游总收入的 $5 2 \%$ ，旅游业俨然成为乌鲁木齐市战略支柱产业。因此，本文选取住宿类P0I(2012年、2018年)以及旅游景点类POI(2018年)为基础数据，将城市住宿设施与旅游景点分别作为旅游地域系统的两大要素，本文首次系统梳理乌鲁木齐市住宿设施时空格局演化及在现状背景下的旅游地域系统内部协调耦合情况，旨在为旅游服务业合理布局和城市有序发展提供科学参考。

# 1研究区概况与研究方法

# 1.1研究区概况与数据来源

乌鲁木齐市是新疆维吾尔自治区的政治、经济、文化中心，各类型住宿设施达4000多个，涵盖低端至高端各种类型，包括旅馆、招待所、快捷酒店、各类连锁酒店、各等级星级酒店等。由于市郊仍处于农村向城市过渡地带，且农田沙漠等广布，故本文选择乌鲁木齐市主城区做为研究案例，主城区涵盖绕城高速以内的区域，包括新市区、头屯河区、天山区、沙依巴克区、水磨沟区、米东区等，下辖100个街道，人口 $1 8 8 . 3 6 \times 1 0 ^ { 4 }$ 人①,是乌鲁木齐人口密度最大、各项经济活动最活跃的地带。

本文旅游景点和酒店住宿POI数据来源于高德电子地图，原始数据经过一系列去重、纠偏等操作，得到含有名称、分类以及坐标信息等属性的各类兴趣点数据，从而运用ArcGIS10.2平台建立旅游地域子系统空间属性数据库，包含各类型住宿业设施3825个；各类型旅游景点数量584个，包含公园、度假村、游园、清真寺、生态园及其他等各种景区。参考前人研究[22],并结合美团、去哪儿网的分类标准，将旅馆、招待所、社会宾馆、家庭宾馆等定为普通型，将如家、7天、格林豪泰、百时快捷、汉庭、锦江之星、速8酒店等连锁酒店定义为经济型，各类星级酒店的评判档级以官方认定或者历史参评数据为准，分为三星级和四星级及以上。

# 1.2研究方法

1.2.1标准差椭圆标准差椭圆(Standarddeviation-alellipse,SDE)是定量描述地理要素分布特征的一种空间统计方法，主要度量要素包括椭圆中心、长轴、短轴、方位角等各参数。中心点代表地理要素空间分布的相对位置，长轴表示数据的分布方向，短轴代表数据的分布范围，扁率越大代表其方向性越明显，在ArcGIS10.2中采用标准差椭圆法来衡量2012年和2018年各类住宿设施的空间演化方向。

1.2.2核密度分析核密度分析是运用地理学第一定律和空间差值原理对要素分布进行空间统计，距离样本中心近的要素被赋予权重较高，距离较远则权重较低，从而呈现出要素的聚集程度。其计算方程式如下：

$$
\int h ( x ) = \frac { 1 } { n h ^ { d } } \sum _ { i = 1 } ^ { n } K \Bigg ( \frac { x - x _ { i } } { h } \Bigg )
$$

式中： $x _ { i }$ 代表空间内某一点， $K { \Bigg ( } { \frac { x - x _ { i } } { h } } { \Bigg ) }$ 表示核函数;$h$ 为带宽，用以定义半径范围； $d$ 为数据维度， $n$ 代表带宽范围内点的个数，本文利用核密度估计方法测度主城区范围内住宿业空间分布的集聚中心。

1.2.3聚集分形维数测算旅游吸引物和住宿设施是在自然环境、人为选择以及社会经济等一系列内外部要素共同作用下形成的[23]，该过程从无序到有序再演化到新秩序，具备无穷嵌套及自相似性特征，因此分形理论是刻画旅游地域系统耦合状态的有效方法[24]。假设旅游地域系统中各个要素系统（住宿设施、旅游景点)为聚集分形系统，则旅游地域系统的聚集分形维数为各个要素聚集维数的几何平均值：

$$
D _ { \scriptscriptstyle d } = \sqrt [ n ] { D _ { \scriptscriptstyle 1 } \times D _ { \scriptscriptstyle 2 } \times D _ { \scriptscriptstyle 3 } , . . . D _ { \scriptscriptstyle N } }
$$

式中： $D _ { 1 } , D , \times D _ { 3 } , . . . D _ { _ N }$ 代表旅游地域系统中各个要素系统的聚集维数； $D _ { d }$ 代表旅游地域系统的聚集维数，表征旅游地域系统围绕旅游极核的集聚效应。就本研究而言， $D _ { 1 } \setminus D _ { 2 } \setminus D _ { d }$ 分别为住宿、旅游、旅游地域系统聚集维数，各子系统聚集维数的计算方法主要参考宋涛等人的研究[25]

# 2结果与分析

# 2.1住宿设施总体格局变化

住宿设施数量明显增多(图1)。其由2012年的915处增加到2018年的3123处，增长3.4倍，各类住宿业的数量在6a间亦均呈现增长趋势，表现为随等级升高而降低，普通型升幅最大，这期间增加了1325家，四星级及以上升幅最小，仅增加128家。

![](images/bc1a6efb1cffe33ea1b50dd0c789f9baa4fb823b4813b850fc1bca0ffd6f9c2d.jpg)  
图12012年及2018年住宿POI类别及数量Fig.1Type and quantity of lodging POIs in 2O12 and 2018

住宿设施空间分布结构出现变化(图2)。从标准差椭圆来看，2012年住宿业设施总体分布趋势呈现南北方向，即沿阿勒泰路、河滩路分布，乌鲁木齐市属于干旱区绿洲河谷城市，城市发展空间受地形、水源、交通干线影响较大，因此住宿设施总体呈现南北分布。然而2018年住宿空间格局的标准差椭圆明显北移，且涵盖的地理空间范围明显增大，开始向外围地区蔓延扩散。椭圆方位角向东北方向偏移 $1 0 ^ { \circ }$ 且住宿设施重心向东北方向偏移，可见米东新区城市组团的住宿业设施增幅远超其他城市组团;标准差椭圆的短轴增加了 $1 0 \mathrm { k m }$ ，表现为向东、西部外扩，表明高铁站片区、八钢片区等城市外围地区的住宿设施数量也在增加，拉大了短轴长度。尽管住宿业依然沿城市重要交通线分布，但已出现离散趋势加剧的特征，

![](images/29e735a47a2e1ceaee68392187f26f0f5f9ec9b1e0d46f94fc96bcce9535444b.jpg)  
图22012年和2018年住宿设施总体分布及标准差椭圆.2SDE and overall distribution of accommodaticin 2012 and 2018

# 2.2各类型住宿设施空间结构演变

主城区内各类型住宿设施分布及演化趋势各异(图3)。2012年经济型、四星及以上的酒店主要沿河滩路分布，轴向布局十分明显，而三星级和普通型呈现离散状态，在空间分布上相较均衡。2018年除普通型外，其余各类的分布方向、离散趋势均出现了明显变化。三星级和经济型离散扩张加剧，轴向趋势弱化，前者由东北-西南分布转变为西北一东南分布，归因于西北部高铁片区交通运输业发展带动了酒店住宿相关行业的发展；后者的椭圆空间范围增大，代表离散分布态势加强，而轴向趋势弱化,主要由于经济类酒店体量较小,且具备“连锁经营”的理念，因而空间扩张较具市场理性，同时也可避免盲目过度集聚和恶性市场竞争。

# 2.3集聚特征分析

为探究各类住宿设施的空间集聚特征，对四类住宿设施(a普通、b经济、c三星、d四星及以上)进行核密度分析(图4)。普通型由原来的多个孤立核演变为分布较为集中的带状多核，核密度等级明显提高。2012年主要聚集在南部长江路、南湖街道，以及北部二工片区、古牧地西路街道。2018年该类型分布集聚特征更加明显，核密度高值区新增二道桥片区、平顶山片区、迎宾路片区、七道湾片区等。同时外围地区形成孤岛状中心，扩散趋势明显，呈现明显的中心集聚一外围扩散趋势。

![](images/2084ea80d30676a67812ec084f17f4cb6ba30c64a7caf5ae4184467410c7320c.jpg)  
图32012年和2018年各类型住宿业标准差椭圆Fig.3SDE of various lodging facilities in 2O12 and 2018

![](images/b29c84c236407ea1b91ac8b6ed509c99b187ee4ba9d36f15fc5b7d0c29dd51f3.jpg)  
图42012和2018年各类住宿设施核密度分析结果  
Fig.4KDE analysis of various accommodation in 2O12 and 2018

经济型酒店由点状集聚转变为带状集聚。2012年3个独立的小型集聚中心均位于南部老城区火车站附近，主要街道包括火车南站片区、新民路街道、长江路片区、大小西门片区，而北部核密度等级均较低，未形成较为明显的集聚区。2018年南部和田街、大小西门、长江路三个街道片区形成一个较为集聚的整体，且在南湖南路片区出现了新的集聚区，有向北部延伸的趋势，北部仍未形成明显聚集区，然而核密度等级普遍升高，涵盖的空间范围也明显增大，未来存在集聚态势倾向。就三星级和四星及以上酒店而言，其空间集聚效应明显不如前两者，是因为住宿设施等级越高，相应数量越少，考虑到市场盈利及潜在客源，区位选择上不再倾向于集聚分布，满足空间集聚的条件越来越严苛，导致其空间集聚特征越来越不明显。三星级集聚区位由2012年的大小西门片区，扩大到市区中部街道，而四星及以上酒店空间集聚特征变化不明显。

# 干旱区地理

# 2.4住宿设施与旅游景点空间关联分析

2.4.1 旅游地域系统空间聚集分形结构特征本文将南航明珠国际酒店和乌鲁木齐国际大巴扎分别作为旅游服务设施重心和旅游吸引物重心。基于以下考虑：南航明珠国际酒店为五星级酒店，规格较高，建设较早；国际大巴扎集文化、建筑、民族商贸、娱乐、餐饮于一体，是新疆旅游业产品的汇集地和展示中心。二者所在区域在历史上属于河谷地带（现在的河滩路沿线），该区域开发较早，且地处乌鲁木齐市重要的商业、文化和购物中心地带，至今仍是城市发展极核。

通过计算得到乌鲁木齐旅游、住宿系统空间结构聚集维数双对数图(图5)。可以看出前者的无标度区间较为宽阔，聚集分形维数为 $1 . 0 3 < 2$ ，判定系数 $R ^ { 2 }$ 为0.93，且满足置信区间( $F _ { \ l }$ -test, $p < 0 . 0 1$ ），拟合效果较好。表明国际大巴扎对于其他旅游吸引物的空间分布具有一定的吸附作用，该体系空间结构是从中心旅游吸引物点向周围地区密度衰减，呈现紧凑型聚集格局，已经形成以国际大巴扎为核心的自组织演化系统。

后者呈现3个无标度区间，自组织能力较差。区间1对应 $R s$ 范围为 $0 . 1 3 \sim 0 . 4 3 \mathrm { ~ k m } , R ^ { 2 }$ 为0.97，聚集维数为 $1 . 3 2 < 2$ ,该区间主要以高端酒店为主，数量较少，住宿设施空间结构较松散，中心酒店对地物吸附作用仅仅局限在其周围，以集聚为主。在该半径范围外开始分化，无标度区间2对应 $R s$ 范围为$0 . 4 4 \sim 3 . 3 8 ~ \mathrm { k m }$ ，判定系数 $R ^ { 2 }$ 为0.99，聚集维数为$2 . 2 3 > 2$ ，子系统空间集聚性明显下降，住宿设施在该半径内的空间分布由集聚转为离散态势。无标度区间3相应 $R s$ 范围为 $3 . 3 8 \sim 8 . 1 6 ~ \mathrm { k m }$ ，拟合方程显示判定系数 $R ^ { 2 }$ 为0.96，聚集维数为 $0 . 8 5 < 2$ 。住宿网点再次回到集聚状态，然而区间1、3的分形维数所代表的含义有所差别：对区间1而言，有限的土地及高昂的地价决定了该半径内部的住宿设施以高档酒店或者连锁酒店为主，南航明珠国际酒店作为系统重心的控制性十分有限；对区间3，住宿设施多以社会宾馆、招待所为主，且由于体量小，地价成本较低，加之缺少人为管控，表现出天然的自组织集聚分布，呈现明显的“中心一外围"现象，沿系统重心高度集聚。

![](images/4efcc5d6ab85a16ce3782b4c98e88831c0d4a92b1981f183abf7a8fafba5bc37.jpg)  
图5乌鲁木齐市旅游、住宿系统聚集维数双对数图 Fig 5log-log plot for the aggregation dimension of tourisim and lodging system in Urumqi

旅游设施表现出的单分形特征和住宿设施表现的多分形结构整体趋势相近，为衡量二者的分形耦合程度，首先将住宿设施3个子系统的聚集维数进行集成，计算得到 $D _ { \scriptscriptstyle 1 } = 1 . 3 6$ ，然后该数值与旅游景点聚集维数 $D _ { \scriptscriptstyle 2 }$ 集成,最后计算得到旅游地域系统的空间分形维数 $D _ { \scriptscriptstyle d } = 1 . 1 8 < 2$ ，介于1和2之间。表明乌鲁木齐市主城区旅游景区与住宿设施系统的空间耦合性较强，旅游地域系统具有明显的中心性，以单中心分布为主。住宿设施与旅游景点均呈现出由中心向周围地域密度衰减的特征，旅游地域系统的空间结构紧凑度高。根据旅游地域系统“点状发展一集聚发展一多中心发展一一体化发展"的演化过程[26],判断目前该系统处于单中心集聚发展的初级阶段，自组织优化能力相对较弱。根据外围米东、高铁片区组团的发展趋势，判断未来有向多中心模式演化的趋势，但从图5可看出二者的无标度区间并未明显覆盖全局，而且系统的空间吸纳半径并未达到最大，而旅游地域系统一体化的最终状态必然是呈现出单一标度区间且无标度区间覆盖全局，表明目前尽管二者的耦合协调度较好，然而二者的分布尚未达到理想最优结构，分形结构仍有待调整和优化。

2.4.2旅游地域系统空间耦合实证分析分形聚集维数是基于旅游设施和住宿设施在空间上具备分形特征的假设进行测算的，本节基于实证分析探究二者空间关联关系。基于ArcGIS平台，分别从全局和局部分布角度出发测算二者的耦合情况，在主城区范围内建立渔网空间并计算每个网格内的两类POI的数量，将二者的数量矩阵进行Pearson相关性分析，得到Pearson相关系数为 $0 . 7 7 ( S i g = 0 . 0 1 )$ ，表明二者的分布在空间上存在显著的协同性，即二者互相伴随出现的概率较高，这也进一步验证了上述结论;另外，从局部布局角度出发，鉴于阿勒泰路、北京路、河滩快速路沿线是二者分布的主要区域，以这三条主要轴线建立道路缓冲区，分别设置五级缓冲范围 $( 5 0 0 \mathrm { m } , 1 0 0 0 \mathrm { m } , 1 5 0 0 \mathrm { m } , 2 0 0 0 \mathrm { m } , 2 5 0 0 \mathrm { m } ,$ $3 \ 0 0 0 \ \mathrm { m } .$ )，缓冲区内的旅游与住宿设施占比达到$8 6 \%$ ，认为可以较好地代表该研究区的旅游地域系统。统计各级缓冲区内部的两种设施的数量，结果如图6。可发现以道路为主轴线的缓冲区内， $R ^ { 2 }$ 达到0.926,表明二者具有较强的相关关系，地理分布具有协同性。这是因为旅游业的发展往往能够带动住宿设施数量增加，而住宿设施的增加也为游客提供了更多了选择性，二者在产业职能方面相互促进，共同促进旅游地域系统成长和演进。

![](images/043175cecd8b58f0a7fc0a1165866262952a94dcd522f3bdf928ae9947d8e27c.jpg)  
图6主要道路五级缓冲区内住宿及旅游景点设施分布 Fig.6Distribution of tourist and accommodation facilities withinthe thefivelevelofbuffer zone of themainroad

![](images/58e02edb28522cc9e5d89705be369b92b1f151750b802e92bcfc82553786e377.jpg)  
图7缓冲区范围内旅游设施与住宿设施数量散点拟合图 Fig.7Scatter plot of the number of tourist and accommodation facilities within buffer zone

# 3结论

本文在测度乌鲁木齐住宿业时空变化格局基础上，阐述了住宿设施与旅游景点的空间关系，得出如下结论：

(1)2012—2018年间，乌鲁木齐市主城区各类型住宿设施数量明显增长，总体沿河滩路、阿勒泰路等重要交通路线分布，会展中心商圈、高铁站商圈以及米东新区等地有望成长为外围地区的住宿设施集聚中心。

(2)住宿设施总体格局向东北方向偏移，其空间分布由依托轴向集聚转向离散分布；四类住宿设施的空间集聚特征各异，普通型由孤立核模式演变为带状多核模式，呈现明显的中心集聚-外围扩散趋势，经济型酒店由点状集聚转变为带状集聚，在城区形成集中连片分布态势，三星级及以上的酒店主要在大小西门一带形成集聚中心，空间集聚变化特征并不明显，建议未来在城北新区一带增加布局高级酒店数目以满足城市北扩需求。

(3)住宿设施与旅游景点的空间耦合性较强，旅游地域系统为单中心发展模式，空间结构紧凑度较高，但未达到理想最优结构，分形结构仍有待调整和优化。全局网格矩阵和局部道路缓冲区内的两类地物分布均呈现较强的空间相关性，二者产业职能的相关性决定了二者在空间分布上具备较强关联性，然而某些片区存在不协调的情况，建议在城市新区附近如米东新区、高铁站片区新增旅游景点服务设施以满足游客需求，进而与住宿设施达到协调。

由于数据获取有限，本文只对2012和2018年进行了住宿业演化分析，且未考虑旅游市场及其他旅游节点对旅游地域系统的影响，难免会出现分析不到位、机理解释不够细致等问题，未来可以尝试从更长时间尺度探寻住宿业时空演化特征，或对旅游地域系统空间提出调控优化的方法及策略。

# 参考文献(References)

[1]王朝辉,陆林,方婷,等.世博建设期上海市旅游住宿产业空间格局演化[J].地理学报,2012,67(10):1423-1437.[WANG Chao

# 干旱区地理

hui,LU Lin,FANG Ting, et al. Spatial patern evolutionof Shanghai tourist lodging industry during the world expo construction period[J]. Acta Geographica Sinica, 2012,67(10): 1423-1437.]   
[2]YANG Y,LUO H, LAW R. Theoretical, empirical,andoperatioal models in hotel location research[J]. International Journal of Hospitality Management, 2014,36: 209-220.   
[3] CRO S,MARTINS A M.Hotel and hostel location in Lisbon: Looking for their determinants[J]. Tourism Geographies,2018,20(3): 504-523.   
[4] URTASUN A,GUTIERREZ I. Hotel location in tourism cities Madrid 1936-1998[J]. Annals of Tourism Research,2006,3(2): 382-402.   
[5] KERVANKIRAN I,AKTURK M. Spatial analysis of accommodation statisticsby province in Turkey[J]. Marmara Geographical Review,2017,(36): 83-96.   
[6] SAINAGHI R.Price determinants of individual hotels: evidence from Milan[J]. Tourism Review,2011,66(4): 18-29.   
[7] 闫丽英,韩会然,陈婉婧,等.北京市住宿业空间分布格局及影 响因素研究[J].经济地理,2014,34(1): 94-101.[YAN Liying, HAN Huiran,CHEN Wanjing,et al. Distribution and influence factorsof lodging industryinBeijing city[J].EconomicGeography, 2014, 34(1): 94-101.]   
[8]查爱苹,徐娜,后智钢.经济型酒店微观选址适宜性研究——以 上海中心城区锦江之星为例[J].人文地理,2017,32(1):152- 160.[ ZHA Aiping,XU Na,HOU Zhigang. A study on the suitability of the micro location of Eco Hotel[J]. Human Geography,2017, 32(1): 152-160.]   
[9]刘嘉毅,赵磊.中国五星级酒店区位布局:特征与影响因素[J]. 旅游学刊,2013,28(8):87-93.[LIU Jiayi,ZHAO Lei.Location layout of Chinese five- star hotel: characteristics and influencing factors[J]. Tourism Tribune,2013,28(8): 87-93.]   
[10] 梅林,韩蕾.中国星级酒店空间分布与影响因子分析[J].经济地 理,2011,31(9): 1580-1584. [MEI Lin, HAN Lei.A study into the factors influencing the spatial distribution of star-rated hotels in China[J]. Economic Geography,2011,31(9): 1580-1584.]   
[11] 童昀,马勇,刘军,等.大数据支持下的酒店业空间格局演进与 预测:武汉案例[J].旅游学刊,2018,33(12):76-87.[TONG Yun, MA Yong,LIU Jun,et al.Evolution and prediction of the spatial pattern of hotel industry supported by big data: A case study of Wuhan[J]. Tourism Tribune,2018,33(12):76-87.]   
[12] 孙景荣,张捷,章锦河,等.基于泰尔系数的中国酒店业的区域 差异特征分析[J].经济问题探索,2013,(3):101-106.[SUN Jingrong,ZHANG Jie, ZHANG Jinhe,et al.Analysis of regional difference characteristics of Chinese hotel industry based on Theil coefficient[J].Inquiry into Economic Issues,2013, (3): 101-106.]   
[13] 姜海宁,谷人旭,李广斌,等.南京市星级酒店空间可达性格局 研究[J].地域研究与开发,2012,31(2):129-134.[JIANG Haining,GU Renxu,LI Guangbin,et al.Research on spatial pattern of accessibility about star-rated hotels in Nanjing City[J].Areal Research and Development, 2012,31(2): 129-134,140.]   
[14] 王娟,李亚娟,吕丽,等.基于互联网数据的住宿业竞争力及其 空间格局——以武汉主城区高端酒店为例[J].地理科学进展, 2018,37(10): 105-115.[WANG Juan, Li Yajuan,LV Li, et al. Hotel competitiveness evaluation and spatial patern based on Internet data: A case study of high-end hotels of Wuhan urban area [J]. Progress in Geography,2018,37(10): 105-115.]   
[15] 霍云霈,杨新军,张兴国.我国高档旅游宾馆空间分布特征与配 置研究—以五星级宾馆为例[J].人文地理,2006,21(2):28- 31.[HUO Yunpei, YANG Xinjun, ZHANG Xingguo. A study on spatial characteristicsand dispositionof topgrade tourist hotel: A case study of five-start hotel[J]. Human Geography,20O6,21(2): 28- 31.]   
[16]龙飞,刘家明,朱鹤,等.长三角地区民宿的空间分布及影响因 素[J].地理研究,2019,38(4):950-960.[LONGFei,LIU Jiaming, ZHU He,etal.Spatialdistributionofhomestayanditsinfluencng factors in the Yangtze River Delta of China[J]. Geographical Research,2019,38(4): 950-960.]   
[17] 陈睿,吕斌.区域旅游地空间自组织网络模型及其应用[J].地理 与地理信息科学,2004,(6): 81-86.[CHEN Rui,LV Bin. Spatial self-organizing network model of regional tourism and its application[J. Geography and Geographic Information Science,2004,20 (6): 81-86.]   
[18] 贺晓慧,白凯,卫海燕,等.西安特殊时段旅游流规模分形结构 特征研究——以"十一"黄金周为例[J].干旱区地理,2011,34 (5): 858-865.[HE Xiaohui,BAI Kai,WEI Haiyan,et al.Fractal structure characteristics of the tourist flow scale in special session of Xi'an: A case study of National Day[J].Arid Land Geography, 2011, 34(5): 858-865. ]   
[19] 李东,杨兆萍,时卉,等.新疆区域旅游关联与景区系统分形结 构的关系[J].干旱区地理,2014,37(5):1074-1082.[LI Dong, YANG Zhaoping,SHI Hui,et al. Relationship between regional tourism interrelation and fractal structure of scenic spots in Xinjiang[J]. Arid Land Geography,2014,37(5): 1074-1082.]   
[20] 朱怡婷,熊黑钢,白洋,等.边疆旅游地县域旅游经济时空变迁 及驱动机制研究—新疆案例[J].干旱区地理,2019,42(2): 392-403.[ZHU Yiting, XIONG Heigang,BAI Yang, et al. Spatial and temporal changes and driving mechanism of county-scale tourism infrontiertourismdestinations[J].AridLand Geography, 2019, 42(2): 392-403.]   
[21] 谢大伟,张诺.丝绸之路经济带新疆生态旅游业发展探析[J].干 旱区地理,2018,41(4): 844-850.[XIE Dawei, ZHANG Nuo. Development of eco-tourism in Xinjiang in Silk Road Economic Belt [J]. Arid Land Geography, 2018,41(4): 844-850.]   
[22] 赵艳楠,杨德刚,张新焕,等.乌鲁木齐住宿业空间分布及热点 区模式研究[J].干旱区地理,2016,39(5):1143-1152.[ZHAO Yannan, YANG Degang,ZHANG Xinhuan, et al. Spatial distribu tion characteristics and hot zone patterns of lodging industry in Urumqi[J]. Arid Land Geography,2016,39(5): 1143-1152.]   
[23] 李功,刘家明,宋涛,等.基于聚集分形维数的旅游吸引物空间

结构特征研究——以北京市为例[J].干旱区资源与环境, 2016,30(5): 197-202. [LI Le,LIU Jiaming, SONG Tao, et al. The spatial structure of tourism attractions based on the theory of fractal aggregatio[J].Arid Land Geography,2016,30(5): 197-202.]

[24]THOMAS I, FRANKHAUSERP, BIERNACKI C. The morphology of built-up landscapes in Wallonia (Belgium):A classification using fractal indices[J],2008,84(2): 0-115.

[25]宋涛,陈雪婷,陈才.基于聚集分形维数的旅游地域系统空间优 化研究[J].干旱区资源与环境,2017,31(4):189-194.[SONG Tao, CHEN Xueting,Chen Cai. Spatial structure of tourism destination system based on the aggregation fractal-A case of Heilongjiang Province[J]. Journal of Arid Land Resources and Environment,2017,31(4): 189-194.]

[26]刘大均,谢双玉，陈君子,等.基于分形理论的区域旅游景区系 统空间结构演化模式研究——以武汉市为例[J].经济地理, 2013,33(4):155-160.[LIUDajun,XIEShuangyu,CHENJunzi, etal.Evolution models for the spatial structure of regional tourist scenic spots system based on fractal theory:A case study of Wuhan [J.Economic Geography,2013,33(4):155-160.]

# Spatial and temporal evolution of the accommodation industry and spatial association with tourist spots based on POI

CHEN Hong-xing1,²， YANG De-gang'， XU Hong-tao1²， HUO Jin-wei' (1StateKeyLaboratoryofDesertandOasis Ecology,Xinjiang InstituteofEcologyandGeography,ChineseAcademyof Sciences,Urumqi 830ol1,Xinjiang,China;2UniversityofChineseAcademyofSciences,Beijing10oo49,China)

Abstract:The urban An urban tourism regional system consists of tourism service facilities and tourist attractions. Accommodation facilities,which are the part of tourism service facilities,represent regional progress and investment opportunities.Spatial distribution patterns have an important efect onthe development of the urban accommodation industryandurban spatial structure.Inadition,it is crucial to exploretherelationship between accommodationfacilities and tourist attractions forregional tourism systems as thespatial couplingand coordination of these two parts determine the structure,function,and level of a tourism regional system. Urumqi,alarge city in western China,has seen an increasing number of tourist receptions and resources in recent years.Tourism has become a strategic pillar industry in Urumqi; however,the temporal and spatial variation of accommodation has notbeen explored and the coupling relationship between the city and the tourism area system has hardly been studied.Therefore,this paper utilizes the kerneldensityestimationand standard deviational elipse model to explore the spatial changes of accommodation facilities using Urumqi as acase.Then,the spatial coordination relationship between accommodation facilities and tourist atractions in Urumqi is explored basedon fractal dimension theoryand spatial datastatistics methods.We found that the overallpattrn of accommodationfacilities in Urumqi changedsignificantly,increasing from915 to3,123between 2012and 2018.The accommodation facilities are basicalldistributed in the axial direction along important transportation lines suchas Hetan highway and Altay road.Additionaly,the number of accommodation facilities inthe Midong New Area increased significantly,forming aconcentration there. In 2018,accommodation facilities were shifting to the northeast significantlyandaxialaggregation model evolved into paternsof increasing trendsof discretedistribution,withthe mostobvious trendbeing thedispersalof three-star and economic accommodations.The ordinary type of accommodation facilities in the main urban area has transferred from isolated cores to a belt multi $\scriptscriptstyle -$ core model. Additionally, budget hotels have changed from point aggregation toabeltaggregation model.Theaggregate fractal dimensionresultsshowthattourismatractions,with the International Grand Bazaaras thecore,have evolved into aself-organizing fractal system.However,the fractal structure of the tourismservice facility,whichhas the SouthernAirlines Pearl International Hotelas itscore,isatalowlevel.

# 干旱区地理

The integrated aggegation dimension of tourist facilities and tourist atractions is1.18,demonstrating thatthe spatialcoupling of thesetwo parts is high.However,the fractal structureof touristattractionsandtouristservicefacilities has not reached an ideal state and must be optimized and adjusted.To further measure the spatial relationship between these two parts,this study establishinga fishnet gridbycalculating the numberof thetwo parts in each grid.These results yielded a Pearson correlation coeffcientofO.77,showing asignificantly strong correlation.A linearregression equation isobtained bycounting the numberof thetwo parts inafive-level bufferof the main road, and the R2 value obtained was O.926.This demonstrates that the accommodation facilities and tourist attractions in Urumqi's tourism regional system have strong spatial coupling and coordination,and the relevance of industrial functions determines their proximity in spatial distribution.

Key Words: POI; accommodation industry； tourist attractions; aggregation fractal; Urumqi

# 第五届干旱区生态水文过程与环境协调发展学术研讨会召开

2020年10月19～22日，由中国科学院新疆生态与地理研究所荒漠与绿洲生态国家重点实验室主办的第五届干旱区生态水文过程与环境协调发展学术研讨会顺利召开。来自中国科学院地理科学与资源研究所、中国科学院西北生态环境资源研究院、中国科学院遗传与发育生物学研究所、中科院新疆生地所、北京师范大学、兰州大学、中山大学、华东师范大学、河北师范大学、塔里木大学等单位的300多位专家参加会议。会议围绕丝绸之路经济带建设需求，重点研讨了在气候变化背景下，干旱区水循环与水资源系统、流域生态水文过程以及生态系统可持续管理等问题。

在中国科学院新疆生态与地理研究所举办的研讨会上，中国科学院院士邵明安、中国科学院院士于贵瑞分别作了题为“黄土高原绿水青山提质增效”和“自然保护和生态恢复的生态学原理”的大会主题报告。兰州大学教授黄宁、新疆生地所研究员陈亚宁、北京师范大学教授李小雁、中科院西北生态环境资源研究院研究员冯起、北京林业大学教授余新晓分别作了题为“高寒山区积雪水资源的多尺度、多物理过程定量评估与预测”、“美丽新疆建设面临的机遇与挑战”、“How dryland shrub asecosystem engineer to modulate ecohydrological and hydropedological processes at different scales”、“河 西地区气候环境与社会发展耦合机制”“干旱区水资源变化与植被响应”的学术报告。

在塔里木大学举行的研讨会上，塔里木大学党委常委、副校长赵峰华教授和新疆生地所副所长孙福宝研究员分别致辞。中科院地理科学与资源研究所研究员张永强、中山大学陈洋波教授、陈晓宏教授、北京师范大学教授何斌、兰州大学教授张宝庆、中科院空天信息创新研究院副研究员曾红伟以及塔里木大学白铁成教授、李发永教授、孙三民副教授分别作了重要学术报告。会后，全体人员参观了塔里木大学校史馆和“三五九旅展览馆”;考察了塔里木河三源流汇河口；调研了新疆生地所阿克苏农田生态系统国家野外科学观测研究站，阿克苏站副站长(执行站长)郝兴明研究员对阿克苏站的历史沿革、功能定位、研究方向、科研能力与技术平台等做了详细介绍。

干旱区生态水文过程与环境协调发展学术研讨会的成功举办，使得参会学者充分分享和交流了相关专业领域的新理念、新实践、新成果、新预见，增进了院校间的深度交流与合作，形成了协同创新长效机制。

![](images/2bad6eabc5663c66c5771281fd853bcad93bf396b03e4744f1aca56aa25d0dd8.jpg)  
会议开幕