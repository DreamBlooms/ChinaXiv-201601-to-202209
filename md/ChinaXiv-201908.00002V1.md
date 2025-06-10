# 基于POI的城市休闲空间格局分析以乌鲁木齐市为例

贾晓婷²，雷军},²，武荣伟1²，王伯礼

(1中国科学院新疆生态与地理研究所,荒漠与绿洲生态国家重点实验室,新疆乌鲁木齐,830011;，中国科学院大学资源与环境学院,北京100049；3中国科学院地理科学与资源研究所，北京100101摘要：基于百度POI数据，运用Ripley's $K$ 函数、最近邻层次聚类、空间自相关等方法，对乌鲁木齐市公共休闲设施空间布局进行研究，总结城市休闲空间的格局特征，进而探讨休闲空间的影响因素。结果表明：(1)乌鲁木齐休闲设施空间分布表现出明显的向心集聚性。(2)各类休闲设施热点区分布表现出不同的集聚倾向，娱乐类、购物类、健身类三类休闲设施热点区主要布局在主城区以内重要交通枢纽和商业中心附近，餐饮类休闲设施热点区表现出明显的人口导向特征，旅游类休闲设施热点区均分布在热门旅游景区附近，文化类休闲设施热点区分布于科教文化基地或多民族混居区。 (3)乌鲁木齐市休闲空间格局为“圈层 $^ +$ 扇形 $^ +$ 组团”模式，核心为面状综合型休闲中心，外围为扇形的休闲设施稀少区、组团式多功能休闲区和组团式餐饮休闲区，最外围是休闲设施极少的郊区和组团式旅游休闲区。（4)乌鲁木齐休闲空间与人口空间分布存在较强的空间正相关关系。

关键 词：休闲空间；POI点数据；休闲设施；热点区；乌鲁木齐文章编号： 1000-6060(2019)04-0943-10(0943\~0952)

休闲是城市的基本功能之一。城市居民休闲和娱乐服务已成为城市的重要标志和社会经济发展的驱动力[1],休闲生活质量的高低成为城市居民衡量其居住环境和幸福感的重要指标[2]。城市休闲功能和休闲产业发展，城市休闲环境及休闲公共管理和服务机制建设，都是未来城市发展的必要考虑因素。城市休闲空间作为城市休闲功能的载体，为城市居民提供各种休闲设施。城市休闲空间的分布既影响着居住在城市不同区域的居民所能够获得的休闲机会和休闲质量，又是城市生态环境本底、景观特色及文化脉络等在城市休闲系统的空间映射[3]因此，城市休闲空间的建设与优化逐渐成为学者的研究焦点[2-4] 。

20 世纪70年代以来，学者开始以休闲商务区（RBD)[5-6]、旅游商务区（TBD）[7]等为对象对城市休闲空间展开初步研究。20世纪90年代以后，学者转向以某种休闲服务设施,如博物馆[8]、大型综合性购物中心[9]、剧院[10]、城市建筑雕塑[1]$\mathrm { K T V } ^ { [ 1 ] }$ 等为对象,对城市休闲空间展开定量研究。21世纪以来，对城市休闲空间整体的研究逐渐兴起,主要的案例城市有苏州[12]、丽江[13]、北京[14]上海[15]等。在已有研究中,部分从宏观整体的角度对城市休闲空间进行论述[14],概述了城市中休闲设施的空间分布情况，但由于资料有限，缺乏深度的空间计量分析，另一部分以城市中某类休闲设施或典型的游憩场点为研究对象进行定量分析[3,16-18],详述了该类休闲设施的空间集聚程度、热点区域、空间分布的影响因素等，但缺少对城市休闲空间总体的把握。本文致力于结合两者的优点，聚焦于城市中各类休闲设施的位置信息，使用GIS空间统计方法进行定量研究，能够真实有效地反映城市休闲空间总体发展状况，为研究休闲空间提供一种新的思路和技术途径。目前，对城市休闲空间的形成机制研究尚处于探索阶段，人口特征影响城市休闲空间的配置需求[19],本文分析了休闲空间与人口密度的空间相关关系。

基于百度POI(PointofInterest)数据，本文对乌鲁木齐市各类休闲设施的空间分布特征进行研究，进而探索城市休闲空间的总体格局及其与人口分布的相关关系，丰富城市休闲空间研究的案例，并对今后城市休闲设施规划与建设方面提供了建议。

# 研究视角与方法

# 1.1基于休闲资源供给视角的休闲空间

从休闲资源供给视角来看，休闲空间是为人们提供可供娱乐、运动、休息、观赏、游玩以及交往等活动的公共空间，为人们在自由时间里自发自足的休闲活动提供基本场所，并使人能产生愉悦感、安全感和归属感[20]。考虑到休闲设施具有明显的伴生特征，因此基于不同休闲方式，将具有空间较高关联性的休闲设施作为同种类型，构建休闲空间体系（表1），确定了6大类48种休闲设施作为研究对象[21]

# 1.2 研究方法

1.2.1 Ripley's $\pmb { K }$ 函数Ripley's $K$ 函数可用来分析休闲设施点集聚或分散的程度。以休闲设施 $i$ 为中心，以半径 $\boldsymbol { r }$ 的搜索圆范围来统计休闲设施点数量，表示研究区内距离 $\boldsymbol { r }$ 内的休闲设施点平均数和区域内休闲设施点密度的比值,计算公式如下[22]：

$$
K _ { _ { ( r ) } } \ = \ { \frac { 1 } { \lambda } } \sum _ { i \neq j } I _ { ( d _ { i j } < r ) } \bigg / n
$$

式中， $\lambda$ 表示研究区内休闲设施点的平均密度，$I _ { ( d _ { i j } < r ) }$ 表示距第 $i$ 个点距离不超过 $\boldsymbol { r }$ 的休闲设施点数量， $n$ 表示研究区内休闲设施点数量。在完全空间随机假设条件下， $K _ { \scriptscriptstyle ( r ) }$ 等于 $\pi r ^ { 2 }$ 。为简化, $K$ 函数

表1乌鲁木齐市休闲空间体系  
Tab.1 Leisure space system in Urumqi City   

<html><body><table><tr><td>编号类型</td><td></td><td>休闲设施</td></tr><tr><td></td><td></td><td>a娱乐类电影院、KTV、棋牌室、桌游室、密室、舞厅、音乐 厅、游乐场、网吧</td></tr><tr><td></td><td></td><td>b健身类公园、广场、活动中心、健身中心、武术馆、舞蹈 会所、运动场馆、桑拿汗蒸、高尔夫球场、溜冰 场、滑雪场</td></tr><tr><td>C</td><td>餐饮类</td><td>酒吧、茶馆、咖啡厅、餐馆、糕饼店</td></tr><tr><td>d</td><td>购物类</td><td>综合商场、大中型超市、花鸟市场、商业步行街</td></tr><tr><td>e</td><td>旅游类</td><td>度假村、国家级景点、农家乐、采摘地、农业观光 园、露营地</td></tr><tr><td></td><td></td><td>f文化类博物馆、图书馆、科技馆、寺、庙、道观、教堂、少 年宫、纪念馆、美术馆、天文馆、文化宫、展览馆</td></tr></table></body></html>

被转变为 $L$ 函数，如下：

$$
L _ { \left( r \right) } = \sqrt { \frac { K _ { \left( r \right) } } { n } } - r
$$

如果 $L _ { \left( r \right) } > 0$ ,则研究区内休闲设施为集聚分布模式，反之，研究区内休闲设施呈分散分布模式。

1.2.2最近邻层次聚类最近邻层次聚类分析是一种探索点数据空间分布热点区的分析方法，其原理是通过定义一个“聚集单元”的“极限距离或阈值”，然后将其与每个空间点对的距离进行比较，当某一点与其他点的距离小于该极限距离时,该点被计人聚集单元，据此将原始点数据聚类为若干区域，称为一阶热点区；对一阶热点区利用同样的方法，聚类得到二阶热点区，依次类推，可以得到更高阶的热点区域[23-24]。采用 Crimestat3.3软件对各类休闲设施布的热点区进行分析。

1.2.3空间自相关分析采用空间自相关分析法，探讨休闲空间与人口分布的空间相关关系。首先构建双变量全局空间自相关模型，通过Moran's $I$ 指数探讨休闲设施密度与人口密度在整个研究区上的相关性。公式如下[25-26]：

$$
I = \frac { ^ { n } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } C _ { i j } ( X _ { i } ^ { a } - \overline { { X } } _ { a } ) ( X _ { j } ^ { b } - \overline { { X } } _ { b } ) } { \sum _ { j = 1 } ^ { n } \sum _ { j = 1 } ^ { n } C _ { i j } \sum _ { i = 1 } ^ { n } ( X _ { i } ^ { a } - \overline { { X } } _ { A } ) ( X _ { j } ^ { b } - \overline { { X } } _ { b } ) }
$$

式中： $n$ 为空间单元总数； $C _ { i j }$ 是衡量空间单元 $i , j$ 之间邻接关系的权重矩阵； $X _ { i } ^ { a } \setminus X _ { j } ^ { b }$ 分别为空间单元 $\mathbf { \chi } _ { i }$ 属性 $\mathbf { \Delta } _ { a }$ 的值和空间单元 $j$ 属性 $b$ 的值； $\bar { X } _ { a } \ : , \ : \bar { X } _ { b }$ 分别为属性 $\boldsymbol { a } , \boldsymbol { b }$ 的平均值。 $I$ 取值在 $\pm 1$ 之间， $> 0$ 表示空间正相关，越接近1，则正相关性越强； $< 0$ 表示空间负相关，越接近-1，则负相关性越强;等于0表示空间无关。

其次，运用局部双变量空间自相关模型，以更好地分析不同空间单元休闲设施与人口分布的关系。公式如下：

$$
I _ { k l } = \frac { X _ { k } ^ { i } - \bar { X } _ { k } } { \pmb { \sigma } _ { k } } et { } { ' } { \sum } _ { j = 1 } ^ { n } W _ { i j } \frac { ( X _ { l } ^ { j } - \bar { X } _ { l } ) } { \pmb { \sigma } _ { l } }
$$

式中： $I _ { k l }$ 为局部双变量空间自相关系数； $\boldsymbol { X } _ { \mathrm { ~ \boldsymbol { ~ k ~ } ~ } } ^ { \ i }$ 为空间单元 $\mathbf { \chi } _ { i }$ 属性 $k$ 的值; $\textit { X } _ { l } ^ { j }$ 为空间单元 $j$ 属性 $l$ 的值;$\overline { { \boldsymbol X } } _ { k } \setminus \overline { { \boldsymbol X } } _ { l }$ 分别为属性 $\mathbf { \delta } _ { k , l }$ 的平均值; $\sigma _ { k } \setminus \sigma _ { l }$ 分别为属性 $\mathbf { \nabla } _ { k , l }$ 的方差; $\boldsymbol { W } _ { i j }$ 为空间单元 $i , j$ 之间的空间权重矩阵。

此外，本研究还使用了变异系数、核密度分析、基于ArcGIS的空间可视化等分析方法

# 1.3研究区与数据来源

乌鲁木齐市作为新疆的首府城市，地处新疆中部,扼南北疆交通要道，是丝绸之路经济带上的重要节点城市。辖7区1县,面积为 $1 3 ~ 7 8 7 . 9 0 ~ \mathrm { k m } ^ { 2 }$ 2015 年常住人口规模 $3 5 5 \times 1 0 ^ { 4 }$ 人,第三产业占GDP比重达 $6 9 . 4 \%$ ,已成为乌鲁木齐经济发展的重要驱动力。

本研究人口数据来源于2015 年乌鲁木齐市公安人口统计年报和新疆人口与计划生育委员会相关统计资料。休闲设施位置信息来自于2015年百度地图兴趣点(POI)数据。

# 2乌鲁木齐市休闲设施空间分布特征

# 2.1乌鲁木齐市休闲设施数量空间分布特征

通过休闲设施在乌鲁木齐各区县分布数量的对比（表2，图1），可以看出，休闲设施在空间分布极不均衡，主要集中于主城区的天山区、新市区、沙依巴克区、头屯河区和水磨沟区，而处于主城区以外的米东区、达坂城区和乌鲁木齐县数量较少。各类休闲设施变异系数(标准差与平均值的比值)有：（旅游类） $>$ （娱乐类） $>$ （购物类） $>$ （健身类） $>$ （餐饮类） $>$ （文化类）（表2），反映出休闲设施在各区县分布的差异程度有：旅游类 $>$ 娱乐类 $>$ 购物类 $>$ 健身类 $>$ 餐饮类 $>$ 文化类。旅游类休闲设施在旅游资源分布较多的水磨沟区和乌鲁木齐县集中分布；娱乐类、健身类、购物类和餐饮类休闲设施在人口密集的天山区、沙依巴克区、新市区集中分布；文化类休闲设施总量较少，但却是各区县文化发展必不可少的设施，因此其在各区县的数量分布较为均衡。

# 表2乌鲁木齐各区县公共休闲设施的数量对比表

Tab.2Regional comparison of the number of leisure sites in Urumqi City   

<html><body><table><tr><td colspan="8"></td></tr><tr><td>区县</td><td>娱乐 类</td><td>健身 类</td><td>餐饮 类</td><td>购物 类</td><td>旅游 类</td><td>文化 类</td><td>休闲设 施合计</td></tr><tr><td>乌鲁木齐市</td><td>1 776</td><td>973</td><td>20138</td><td>2 648</td><td>822</td><td>373</td><td>26 730</td></tr><tr><td>天山区</td><td>336</td><td>228</td><td>3 891</td><td>622</td><td>37</td><td>84</td><td>5198</td></tr><tr><td>沙依巴克区</td><td>325</td><td>162</td><td>3 821</td><td>555</td><td>58</td><td>64</td><td>4985</td></tr><tr><td>新市区</td><td>526</td><td>247</td><td>5138</td><td>595</td><td>88</td><td>73</td><td>6 667</td></tr><tr><td>水磨沟区</td><td>307</td><td>157</td><td>2995</td><td>420</td><td>143</td><td>33</td><td>4 055</td></tr><tr><td>头屯河区</td><td>125</td><td>71</td><td>1 717</td><td>173</td><td>27</td><td>29</td><td>2 142</td></tr><tr><td>达坂城区</td><td>8</td><td>8</td><td>257</td><td>13</td><td>18</td><td>9</td><td>313</td></tr><tr><td>米东区</td><td>140</td><td>73</td><td>2 094</td><td>260</td><td>72</td><td>58</td><td>2 697</td></tr><tr><td>乌鲁木齐县</td><td>9</td><td>27</td><td>225</td><td>10</td><td>379</td><td>23</td><td>673</td></tr><tr><td>变异系数C</td><td>0.76</td><td>0.69</td><td>0.66</td><td>0.71</td><td>1.08</td><td>0.54</td><td>0.63</td></tr></table></body></html>

![](images/e9bffed04499d909dd798399cd0edd1d19c51237cd092c37465a700523edfa6b.jpg)  
图1乌鲁木齐城市休闲设施分布图 Fig.1Distribution of leisure facilities in Urumqi City

# 2.2乌鲁木齐市休闲设施空间集聚程度

Ripley's $K$ 函数分析结果如图2，图中观测值的 $\boldsymbol { L } _ { ( t ) }$ 曲线位于包络线以上，说明乌鲁木齐市休闲设施总体属于集聚分布。 $\boldsymbol { L } _ { ( t ) }$ 值越高，点数据空间集聚程度越高，在 $0 \sim 1 8 . 4 7 ~ \mathrm { k m }$ 距离尺度范围内，乌鲁木齐市休闲设施的空间集聚程度呈逐渐增大的模式；研究尺度为 $1 8 . 4 7 ~ \mathrm { k m }$ 时，休闲设施空间集聚程度达到峰值；从 $1 8 . 4 7 ~ \mathrm { k m }$ 到更大尺度，集聚程度缓慢下降。

对六类休闲设施进行Ripley's $K$ 函数分析，结果如图3。 $\boldsymbol { L } _ { ( t ) }$ 值最高时，六类休闲设施研究尺度范围在 $1 3 . ~ 1 2 \sim 2 0 . ~ 5 7 ~ \mathrm { k m }$ 之间，则休闲设施在10$\mathrm { k m }$ 距离尺度级别集聚特征最为显著，六类休闲设施分布的集聚程度有：餐饮类 $>$ 娱乐类 $>$ 购物类 $>$ 旅游类 $>$ 健身类 $>$ 文化类。

![](images/30c2cc668bb782abaecf2ee160e5b4fe2df29c04a43e841b706e97c641183e90.jpg)  
图2乌鲁木齐市休闲设施Ripley's $K$ 统计结果 Fig.2Ripley's $K$ result of leisure facilities in Urumqi City

![](images/d63c5bac368311bfd56bed687ff3ea3dcdfe66a1b03648072cbe2d23707e9abc.jpg)  
图3乌鲁木齐市各类休闲设施Ripley's $K$ 统计结果 Fig.3Ripley's $K$ results of six categories leisure facilities in Urumqi City

# 2.3乌鲁木齐市休闲设施热点区

采用ArcGIS10.2软件中的核密度分析工具对乌鲁木齐市各类休闲设施的核密度分布进行分析，并利用最近邻层次聚类方法对乌鲁木齐市各类休闲设施进行热点区探测，生成各类休闲设施热点区分布图(图4）。因娱乐类、健身类、餐饮类、购物类、文化类五类休闲设施热点区均位于主城区内，图4中仅展示其在主城区内的热点区分布情况

2.3.1娱乐类休闲设施空间集聚区娱乐类休闲设施以营业性娱乐场所为主，是（时尚)现代生活方式的空间承载地[16]。核密度分析可得,娱乐类休闲设施在市中心形成南北方向面状的中高密度的集聚区，最近邻层次聚类分析探测得到老城区①、新民路、南湖东路、河南东路和友好北路等8个娱乐类休闲设施热点区(表3，图4a）。热点区域均集中在主城区以内，属于大面积高密度集聚。娱乐类休闲设施如电影院、KTV、游乐场等，布局倾向于市中心各个大型商业中心附近,或高等院校附近，道路可达性好，拥有较大的人口密度和人流量。

2.3.2健身类休闲设施空间集聚区核密度分析可得，健身类休闲设施在市中心形成自南向北面状的中高密度集聚区，最近邻层次聚类法探测得到老城区、友好南路一南湖南路、南纬路一二工街道和友好北路等7个热点区（图4b，表3）。热点区属于大面积低密度集聚。健身类的休闲公园、运动场馆、健身中心、社区活动中心均主要分布于主城区以内人口密度较大的地区，郊区则零散分布滑雪场、赛马场等健身类设施。

2.3.3餐饮类休闲设施空间集聚区基本情况核密度分析可得，餐饮类休闲设施在主城区南部和北部形成面状的中高密度的集聚区，有南北两个高密度核心，最近邻距离层次聚类法探测得到中山路、西虹东路、大、小西门、奇台路和河南东路等13个餐饮类休闲设施热点区（图4c，表3）。餐饮类热点区域均在主城区以内，属于小面积高密度集聚。餐饮类休闲设施热点区数量较多，分布更为密集，热点区内有各种美食街、美食广场等餐饮中心，主要位于城市商业圈或住宅区的附近。

2.3.4购物类休闲设施空间集聚区核密度分析可得，购物类休闲设施以老城区为中心形成中高密度区，最近邻距离层次聚类方法探测得到老城区、钱塘江路一奇台路、南湖南路和友好南路等7个购物类休闲设施热点区（图4d，表3）。购物类热点区均在主城区以内，属于大面积高密度集聚，均是乌鲁木齐较大的零售业中心。

2.3.5旅游类休闲设施空间集聚区核密度分析可得，旅游类休闲设施高密度聚集区分布较为分散，最近邻距离层次聚类法探测得到6个旅游类休闲设施分布热点区（图4e，表3）。旅游类热点区主要分布在郊区，在主城区只有红山一处热点区，属于大面积低密度集聚。水西沟镇南和路、庙尔沟、水西沟镇南华路均位于南山森林草原生态游览区，百泉沟和石仁子沟均位于博格达峰山前游览区。旅游类休闲设施依托良好的山前牧场资源或山地旅游资源等良好的自然资源本底，形成了以农家乐、度假村等为主的乡村旅游集聚区。郊区的旅游类休闲设施主要包括度假村、农家乐等依托传统农牧业产业优势和自然资源本底形成的休闲设施，由于这类休闲设施与主城区距离大多在 $4 0 ~ \mathrm { k m }$ 以上，距离较远，主要吸引城市中高收入自驾游游客以及年轻人群等开展集体休闲活动，重游率较高。主城区内的的旅游设施主要分布在市中心的国家4A级景区中，如红山公园、鲤鱼山公园、植物园等。

2.3.6文化类休闲设施空间集聚区核密度分析可得,文化类休闲设施以老城区为中心形成面状的中高密度区，最近邻距离层次聚类法探测得到2个文化类休闲设施热点区，分别位于解放南路和二工街道(图4f,表3），均在主城区以内，属于大面积低密度的集聚。解放南路集中了大量的清真寺、教堂等宗教设施，同时也是重要的民族混居区，是多民族文化交流的中心地区；二工街道则集中了较多的图书馆、标本馆、博物馆等文化类休闲设施，区内有中国科学院新疆分院、新疆地震局等多家科研单位，是

表3乌鲁木齐市各类休闲设施空间热点区  
Tab.3Hot spots of different categories leisure facilities in Urumqi City   

<html><body><table><tr><td>类型</td><td>编号</td><td>名称</td><td>数量</td><td>（个度-2）</td><td>编号</td><td>名称</td><td>数量</td><td>/（个度-2）</td></tr><tr><td>a娱乐类</td><td>1</td><td>老城区</td><td>149</td><td>29</td><td>5</td><td>友好北路</td><td>56</td><td>19</td></tr><tr><td rowspan="6">b健身类</td><td>2</td><td>新民路</td><td>129</td><td>31</td><td>6</td><td>北京南路</td><td>85</td><td>22</td></tr><tr><td>3</td><td>南湖东路</td><td>75</td><td>17</td><td>7</td><td>古牧地东路</td><td>72</td><td>15</td></tr><tr><td>4</td><td>河南东路</td><td>113</td><td>26</td><td>8</td><td>喀什西路</td><td>54</td><td>11</td></tr><tr><td>1</td><td>老城区</td><td>141</td><td>22</td><td>5</td><td>杭州路</td><td>31</td><td>4</td></tr><tr><td>2</td><td>友好南路—南湖南路</td><td>84</td><td>11</td><td>6</td><td>团结路</td><td>38</td><td>8</td></tr><tr><td>3</td><td>南纬路一二工街道</td><td>91</td><td>11</td><td>7</td><td>古牧地东路</td><td>33</td><td>5</td></tr><tr><td></td><td>4</td><td>友好北路</td><td>51</td><td>7</td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="5">c餐饮类</td><td>1</td><td>中山路</td><td>442</td><td>693</td><td>8</td><td>美居物流园</td><td>268</td><td>553</td></tr><tr><td>2</td><td>西虹东路</td><td>396</td><td>749</td><td>9</td><td>南湖东路</td><td>269</td><td>387</td></tr><tr><td>3</td><td>大、小西门①</td><td>251</td><td>668</td><td>10</td><td>克拉玛依西路</td><td>228</td><td>355</td></tr><tr><td>4</td><td>奇台路</td><td>334</td><td>597</td><td>11</td><td>南湖北路</td><td>225</td><td>465</td></tr><tr><td>5</td><td>河南东路</td><td>322</td><td>477</td><td>12</td><td>友好南路</td><td>223</td><td>514</td></tr><tr><td rowspan="5">d 购物类</td><td>6</td><td>和田街</td><td>208</td><td>373</td><td>13</td><td>友好北路</td><td>215</td><td>399</td></tr><tr><td>7</td><td>长春南路</td><td>285</td><td>471</td><td></td><td></td><td></td><td></td></tr><tr><td>1</td><td>老城区</td><td>149</td><td>1 515</td><td>5</td><td>长春南路</td><td>86</td><td>778</td></tr><tr><td>2</td><td>钱塘江路—奇台路</td><td>130</td><td>1 648</td><td>6</td><td>大湾北路</td><td>85</td><td>917</td></tr><tr><td>3</td><td>南湖南路</td><td>107</td><td>1 209</td><td>7</td><td>古牧地东路</td><td>76</td><td>918</td></tr><tr><td rowspan="4">e旅游类</td><td>4</td><td>友好南路</td><td>92</td><td>1 055</td><td></td><td></td><td></td><td></td></tr><tr><td>1</td><td>南和路</td><td>178</td><td>13</td><td>4</td><td>百泉沟</td><td>41</td><td>3</td></tr><tr><td>2</td><td>庙尔沟</td><td>43</td><td>24</td><td>5</td><td>石仁子沟</td><td>35</td><td>3</td></tr><tr><td>3</td><td>南华路</td><td>38</td><td>30</td><td>6</td><td>红山</td><td>31</td><td>2</td></tr><tr><td>f文化类</td><td>1</td><td>解放南路</td><td>86</td><td>10</td><td>2</td><td>二工街道</td><td>44</td><td>4</td></tr></table></body></html>

$\textcircled{1}$ 大、小西门:大西门位于中山路与新华北路交叉口,小西门位于民主路与新华北路交叉口,大、小西门一带是乌鲁木齐市繁华的商业圈。

![](images/dd9e2a25c754dfe213263df295f6090ebbbc38c80cfe4f39ec95b6a27963d292.jpg)  
图4乌鲁木齐市各类休闲设施热点区  
Fig.4Hot spots of different categories leisure facilities in Urumqi City

重要的科教文化基地。

# 2.4休闲设施密度随到市中心距离变化情况

以市中心的大十字①为中心，对各类休闲设施密度随距离变化的情况进行统计，可得随距离增加，各类休闲设施密度逐渐降低（图5），距离大十字3km 范围内，即老城区范围内，各类休闲设施密度均处于较高水平； $3 \sim 1 0 ~ \mathrm { k m }$ 范围内，即主城区以内，各类休闲设施密度均处于较低水平， $1 0 ~ \mathrm { k m }$ 以外地区，即郊区，旅游类休闲设施在 $3 5 \sim 4 3 ~ \mathrm { k m }$ 距离范围内出现一个新的高峰，其他各类休闲设施均处于极低水平。

![](images/1da519fd1f0a9f66e30d3f22cbbc08aa9c78c937a51870196fc7da24c566245c.jpg)  
图5乌鲁木齐市各类休闲设施密度随距离变化图  
Fig.5Density change of different categories leisure facilities with distance in Urumqi City

# 3乌鲁木齐市休闲空间总体特征

基于 $P O I$ 数据建立的乌鲁木齐市休闲空间体系，将乌鲁木齐市各类休闲设施密度变化和热点区相结合，可以得出乌鲁木齐市休闲空间具有以下特征：

（1）乌鲁木齐市休闲空间集聚程度和分布格局特征存在高度的向心集聚，并形成若干休闲集中区。（2）乌鲁木齐休闲空间格局主要表现为“圈层 $^ +$ 扇形 $^ +$ 组团”模式（图6）。市中心为休闲设施密度最高的核心地区，市中心外围为扇状的休闲设施稀少区和组团式休闲区，郊区为休闲设施极少区。休闲空间组团共有四种类型： $\textcircled{1}$ 面状综合型休闲中心，集娱乐、健身、餐饮、购物、旅游、文化为一体，主要集中在以大十字为中心的老城区。 $\textcircled{2}$ 组团式多功能休闲区，集娱乐、健身、餐饮、购物为一体，主要分布在主城区以内的友好路、铁路局、古牧地东路等商业中心附近； $\textcircled{3}$ 组团式餐饮类休闲区，主要在市中心外围零散分布； $\textcircled{4}$ 组团式旅游类休闲区，主要分布在郊区的南山风景游览区和博格达峰山前游览区。

![](images/259eddefc2244c00b9cdc1fff8650ae81f612d0e3cdb52a109fa9aed396a6e9b.jpg)  
图6乌鲁木齐城市休闲空间结构示意图Fig.6Urban leisure space structure of Urumqi City

（3）从6类休闲设施热点区的区位来看，娱乐类、购物类、健身类三类休闲设施倾向于布局在重要交通枢纽附近或商业中心附近，尤其是在中山路、友好路、华菱市场、美居物流园、明珠花卉市场、铁路局等均是较大的零售商业中心所在地；餐饮类休闲设施表现出明显的人口导向特征；文化类休闲设施主要分布在文化底蕴深厚的老城区和高教科研单位所在地；旅游类休闲设施主要集聚在旅游景区附近。

# 4乌鲁木齐市休闲空间影响因素分析

# 4.1 休闲空间与人口分布

利用Geoda软件对人口密度和休闲设施密度进行双变量的莫兰指数分析，结果如图7。全局莫兰指数计算结果为0.6125（图7a），表明人口和休闲空间分布具有正向相关关系。局部莫兰指数分析结果显示，43个乡镇街道有着正向的空间相关性，其中"High-High"区主要位于市中心的新华北路、解放北路、友好路、北京路等17个街道，人口密度和休闲设施密度均较高，“Low-Low”区主要位于城市郊区的萨尔达坂乡、板房沟乡、水西沟镇、阿克苏乡、柏杨河乡等29个乡镇，人口密度和休闲设施密度均较低（图7b）。

对人口密度和各类休闲设施密度分别进行全局莫兰指数分析，得到Moran'I系数检验结果均呈现出显著性水平( $\textstyle P < 0 . 0 5 ,$ ，则乌鲁木齐市各类休闲设施空间分布均与人口分布具有正向空间相关关系（表4）。其中，人口密度与餐饮类、娱乐类休闲设施在空间上的相关性较强，与健身类休闲设施的空间相关性一般，与旅游类和文化类休闲设施的空间相关性较弱。

![](images/c3b8ff41082d0a283ed7ebef973d2169bc65025a348a7d4d015805352c536566.jpg)  
图7人口密度和休闲设施的空间自相关关系  
Fig.7Spatial correlation between population density and leisure facilities

表4乌鲁木齐市各类休闲设施密度与人口密度的空间相关性 Tab 4Spatial correlation between population density and different leisure facilities density in Urumqi City   

<html><body><table><tr><td>Bivariate Moran's I</td><td></td><td>娱乐健身餐饮购物旅游文化</td><td>类类类类类类</td><td></td><td></td><td></td></tr><tr><td>人口密度</td><td></td><td>0.5970.548</td><td></td><td>0.6060.595 0.350</td><td></td><td>0.450</td></tr></table></body></html>

# 5结论

（1）乌鲁木齐休闲设施分布表现出明显的向心集聚性。从空间集聚程度来看，随着研究距离尺度的增大，集聚程度先增大后减小。从热点区分布看，各类休闲设施热点区分布表现不同的集聚倾向，娱乐类、购物类、健身类三类休闲设施热点区主要布局在重要交通枢纽和商业中心附近，餐饮类休闲设施热点区表现明显的人口导向特征，旅游类休闲设施热点区均分布在热门旅游景区附近，文化类休闲设施热点区分布于科教文化基地或民族混居区。

（2）乌鲁木齐市休闲空间格局为“圈层 $^ +$ 扇形 $^ +$ 组团”模式，核心为面状综合型休闲中心，外围为扇形的休闲设施稀少区、组团式多功能休闲区和组团式餐饮休闲区，最外围是休闲设施极少的郊区和组团式旅游休闲区。城市居民日益增长的休闲空间需求是城市休闲空间发展的主要驱动力，休闲空间发展和休闲设施布局与人口空间分布有着密切联系。

（3）乌鲁木齐在快速的城市扩张过程中，忽视了居民对多类型休闲空间的需求，除旅游类外的各类休闲设施过度集中于市中心地区，而市中心外围地区休闲设施类型较为单一，数量较少；旅游类休闲设施热点区则集中分布在距离市中心40km之外的地区，且交通不便，难以满足城市居民亲近自然的休闲需求。在未来乌鲁木齐城市规划与发展中，需要加强市中心外围地区各类休闲设施的建设，改善城市至郊区旅游类休闲设施的交通条件，整体提高城市居民对休闲空间的可获得性。

本文基于百度POI数据，以乌鲁木齐市为例深入分析了城市休闲空间格局特征，并对休闲空间与人口分布的相关关系进行了探讨，为城市休闲设施规划与建设提供了科学依据，也为开展城市休闲空间研究提供了新的研究视角与方法，具有重要的理论意义和实践意义。由于缺少历史数据，本文未能从长时间尺度对城市休闲空间格局的形成及演变机制进行分析。未来城市休闲空间格局研究的重点应是从时间序列视角，开展城市休闲空间的时间演化特征及其影响机理的研究，掌握城市休闲空间格局的时空演化规律，为城市休闲空间建设与发展提供更为坚实的科学支撑。

参考文献（References）   
[1]CAN C,WANG J,WU Z,et al. The socio-spatial distribution of leisure venues: A case study of Karaoke Bars in Nanjing, China [J].InternationalJouralofGeo-Information,16,5（9）150.   
[2］陈华英.上海市中心城区休闲设施空间分布及其影响因素研 究[D].上海：上海师范大学,2016.［CHEN Huaying.Study on the spatial distribution of leisure facilities in downtown Shanghai and its influencing factors[D]. Shanghai: Shanghai Normal University,2016.]   
[3］李功,刘家明,宋涛,等.北京市绿带游憩空间分布特征及其成 因[J].地理研究,2015,34(8）:1507-1521.[LILe,LIU Jiaming,SONG Tao,et al.Spatial characteristicsand causes of recreational space in the urban green belt of Beijing,China[J]. Geographical Research,2015,34（8）:1507-1521.]   
[4］秦学.城市游憩空间结构系统分析——以宁波市为例[J].经 济地理,2003,23(2）:267-271.[QIN Xue.Systematic study on urban recreational spatial structure: A case study of Ningbo city [J]. Economic Geography,2003,23(2）:267 -271.]   
[5]STANSFIELD C A,RICKERT JE. The recreational business district[J]. Journal of Leisure Research,1970,2(4）:213-225.   
[6]朱鹤,刘家明,陶慧,等.北京城市休闲商务区的时空分布特征 与成因[J].地理学报,2015,70（8）:1215-1228.[ZHU He, LIU Jiaming,TAO Hui,et al. Temporal-spatial pattern and contributing factors of urban RBDs in Beijing[J].Acta Geographica Sinica,2015,70(8):1215 -1228.]   
[7]GETZ D.Planning for tourism business districts[J].Annals of Tourism Rearch,1993,20(3）:583-600.   
[8]PAGE S J. Urban tourism in New Zealand:The National Museum of New Zealand project[J]. Tourism Management,1993,14（3）: 211 -217.   
[9]FINN A,ERDEM T.The economic impact of a mega-multi-mall: estimation issues in the case of West Edmonton Mall[J].Tourism Management,1995,16(95） :367-373.   
[10]HOWARD L H.Theatre in London and the inter-relationship with tourism[J].Tourism Management,1998,(5）:445-452.   
[11]WILLIAM A D,PAULIINA R.The tradition of invention:Conceiving Las Vegas[J].Annals of Tourism Research,2004(1) :7 -23.   
[12］曾琳.明清苏州休闲空间研究［D]．上海：同济大学,2007. [ZENG Lin.The research on the leisure space of Ming and Qing Dynasties[D]. Shanghai:Tongji University,2007.]   
[13］张佳夫.丽江古城休闲空间研究［D].昆明：昆明理工大学, 2007.[ZHANG Jiafu. The Lijiang old city leisure space research [D]. Kunming：Kunming University of Science & Technology, 2007.]   
[14］吴承忠,韩光辉.明清北京休闲空间格局研究[J].地理学报, 2012,67(6）:804 -816.[WU Chengzhong,HAN Guanghui. Research on the leisure space patterns in Beijing during the Ming and Qing Dynasties[J]. Acta Geographica Sinica,2012,67(6）:804 - 816.   
[15］陈龙飞.上海城市公共休闲空间研究[D].上海：上海师范大 学,2016.[CHEN Longfei. Shanghai public recreation space research[D].Shanghai：Shanghai normal University,2016.]   
[16］张波,王兴中.城市(营业性)娱乐场所空间结构研究[J].地理 科学,2007,27(6):853-858.[ZHANG Bo,WANG Xingzhong. The study of spatial structures of the urban commercial entertainment places[J].Scientia Geographica Sinica,2007,27(6）:853- 858.]   
[17］黄泰,保继刚,戴学军.苏州城市游憩场点系统空间结构分形 [J].地理科学进展,2009,28（5）：735-743.［HUANG Tai, BAO Jigang,DAI Xuejun. Fractal study on spatial structure of city recreation sites system:A case study of Suzhou City area[J].Pro gress in Geography,2009,28(5） :735-743.]   
[18］吴必虎.上海城市游憩者流动行为研究[J].地理学报,1994, (2）:117-127.[WU Bihu.A research on urban recreationist's traveling behavior in Shanghai[J]．Acta Geographica Sinica, 1994,(2) :117 -127.]   
[19］孙琨,唐承财,钟林生.基于人口特征的城市生态游憩空间配 置——以常熟市为例[J].地理科学进展,2016,35(6)：714- 723.［SUN Kun,TANG Chengcai,ZHONG Linsheng.Siting of urban recreational eco-space based on population characteristics :A case study of Changshu City,China[J].Progress in Geography, 2016,35(6) :714 -723.]   
[20］郭旭,郭恩章,陈肠.论休闲经济与城市休闲空间的发展[J]. 城市规划,2008,252（12）:79－86.[GUO Xu,GUO Enzhang, CHEN Yang.Leisure economy and development of urban leisure space[J].City Planning Review,2008,252(12）:79-86.]   
[21］宋军继.城镇休闲地规划与建设[M].北京：中国社会出版社, 2006:51-55.[SONG Junji. Urban leisure planning and construction[M].Beijing:China Society Press,2006:51-55.]   
[22］湛东升，孟斌.基于社会属性的北京市居民居住与就业空间集聚 特征［J].地理学报,2013,68（12）:1607-1618.［ZHANDongsheng,MENG Bin.Spatial clustering analysis of residential and employment distribution in Beijing based on their social characteristics [J].Acta Geographica Sinica,2013,68(12）:1607-1618.]   
[23］董丞妍，谭亚玲,罗明良,等.中国"癌症村"的聚集格局[J].地 理研究,2014,33（11）:2115-2124.［DONGChengyan，TAN Yaling,LUO Mingliang,et al. Spatial aggregation pattern of“cancervillage”in China[J].Geographical Research,2014,33（11）： 2115 -2124.]   
[24］程乾，凌素培.中国非物质文化遗产的空间分布特征及影响因 素分析[J].地理科学,2013,33（10）：1166-1172.［CHENG Qian,LING Supei.Geographical distribution and affecting factors of the intangible cultural heritage in China[J].Scientia Geographica Sinica,2013,33（10) :1166-1172.]   
[25］詹璇,林爱文，孙,等.武汉市公共交通网络中心性及其与银 行网点的空间耦合性研究[J].地理科学进展,2016,35（9）： 1155-1166.[ZHAN Xuan,LIN Aiwen,SUN Cheng,et al.Centrality of public transportation network and its coupling with bank branches distribution in Wuhan City[J].Progress in Geography, 2016,35(9):1155 -1166.]   
[26]鲁政.认知地图的空间句法研究[J].地理学报,2013,68（10）： 1401-1410.[LU Zheng.Spatial syntactic analysis of cognitive maps［J]．Acta Geographica Sinica,2013,68（10）：1401-

1410.]

# Urban recreation space pattern based on POI data : A case of Urumqi City

JIA Xiao-ting1,2，LEIJun12WURong-wei12，WANG BO-li (1State Key Laboratoryof DesertandOasis Ecology,Xinjiang Instituteof Ecologyand Geography,ChineseAcademyof Sciences,Urumqi 830l1,Xinjiang,China；2CollegeofResourcesandEnironment,UniversityofChinese AcademyofSciences, Beijing00049,China；3InstituteofGeographicScienceandNatural Resources Research,CAS,BeijingOolo,China)

Abstract：Urban recreation space is an important organic part ofa city,and its development is a reflection of not only the urban socio-economic culture,but also the evolution of urban spatial structure.Based on Baidu POI data,using Ripley's $K$ function,spatial autocorrelation,and the nearest neighbor hierarchical clustering analysis methods, this paper studied the spatial characteristics of public recreationalfacilities in Urumqi City,Xinjiang,China,summarizedthe paterns of urban recreation space,and explored the influencing factors of urban recreation space.The results show as follows:（1）The spatialdistribution ofthe leisure facilities in Urumqi showsa marked centrality and agglomeration.（2）The hot spots ofthe six kinds of recreational facilitiesshow diferent tendencyofagglomeration. The entertainment facilities,shopping facilities and sport facilities tend to cluster near important transport hubsand commercial centers.The hotspots of catering facilities show obvious population orientation.The hot spots of tourism facilitiesare all locatednear hotscenic spots.Thehot spots ofcultural facilities are located in the mixed ethnicareas.(3）The recreation space pattern in Urumqi is displaying a“layer $+$ sector $^ +$ group” mode.The city center is the planar comprehensive leisure center,and the peripheryof the citycenter is the fan-shaped leisure facilities area with lowdensity,grouped multi-functional leisure area and grouped catering leisure area.The suburbs have few leisurefacilities but are grouped tourism leisure areas.（4）It is proved that the recreation space of Urumqi is positively correlated with the spatial distribution of population.

Key words:recreation space；POI data；recreational facilities；hot spots；Urumqi