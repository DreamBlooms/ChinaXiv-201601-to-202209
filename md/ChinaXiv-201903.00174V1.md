# 新型城镇化视角下县域城镇化时空格局及聚集特征-以浙江省为例

王彦霞²，王培安1,2

（1兰州交通大学测绘与地理信息学院,甘肃兰州730070；2兰州交通大学,甘肃省地理国情监测工程实验室,甘肃兰州 730070)

摘要：基于新型城镇化特征及内涵，选取人口、经济、社会、空间、居民生活质量、城乡统筹发展和创新发展7个因素26项指标构建浙江省县域新型城镇化水平评价体系，运用模糊综合评价法计算了该省70个县域行政单元2007—2016年新型城镇化水平。在此基础上，采用ArcGIS 对计算结果进行可视化表达和分析，并采用系统聚类法进行了验证。结果表明：(1）浙江省县域新型城镇化水平在时间上总体呈缓慢上升趋势，在空间上总体呈现“倒三角”特征。（2)形成三个高水平区域中心和两个低水平区域中心，高水平区域中心对周边区域带动辐射效应明显;传统城镇化指标对新型城镇化水平贡献较大，但城乡统筹发展和创新发展的贡献逐年上升。（3)新型城镇化水平较高区域得益于其创新发展，其城乡统筹发展和社会城镇化相较其他区域表现突出。

关键词：新型城镇化；时空格局；层级分析法；主成分分析法；模糊综合评价；系统聚类法文章编号： 1000 -6060(2019)02 -0423-10(0423\~0432)

自改革开放至今，我国城镇化的水平保持了年均 $1 \%$ 的增长速率，从最初的 $1 7 . 9 2 \%$ 到2016年的$5 7 . 3 5 \% ^ { [ 1 - 2 ] }$ 。推进新型城镇化是我国“十三五”规划的重大战略之一，快速的城镇化发展为统筹区域协调发展、扩大内需、促进产业升级和提升我国整体经济水平起到了强有力的支撑作用，

针对我国城镇化快速发展的特点，既有文献从城镇化综合水平评估[3-4]、空间发展特征[5-7]、时空特性分析和影响城镇化发展的主要因素等方面进行了研究[8-11],对区域城镇化的发展提供了具有借鉴意义的分析总结。研究表明，我国城镇化的总体特征呈东高西低的态势：京、沪、江、浙等东南沿海地区不仅发展水平较高，而且保持着较高的城镇化增速，而中西部地区整体发展水平较为落后[12-14]。经济水平、产业结构、城乡发展、教育水平、基础设施投资、市场化程度差异、交通条件以及政府干预作用是造成这一现状的主要因素[15-16]。我国城镇化的快速发展在很大程度上推动了经济的高速增长和社会变迁，但同时也面临如综合发展水平低、经济增长方式粗放、生态环境恶化、城镇功能和集聚能力较低、结构性矛盾突出等问题[17-19] 。

与传统城镇化相比，新型城镇化是对传统城镇化的提升与发展，强调城乡统筹，注重以人为本、以工促农、以城带乡，统筹兼顾。基于以上方面，部分研究采用复合指标法，强调城镇化建设规模与质量并重,如胡际权[20]提出从经济集约、社会和谐、政治文明、生态环境建设等方面构建新型城镇化评价体系;杨帆[21]构建的新型城镇化评价体系包括经济集约、社会和谐、环境友好、功能优化、城乡统筹五大类多项指标;牛晓春等[22]在此基础上进行了补充,提出采用人口城镇化水平、经济城镇化水平、居民生活质量、基础设施建设、生态环境建设水平和城乡统筹发展水平6个方面构建出新型城镇化评价指标体系;刘超等[23-24]同样从人口、经济、社会、生态、土地、文化及基础设施等方面对贵州省的新型城镇化空间格局进行了研究。

然而，此类研究中存在两方面的不足：一方面，部分研究选取的评价指标不够全面，使得实证分析力度不足，造成城镇化评价结果可靠度有限；另一方面，此类研究选取的最小行政单位大多为省份和直辖市，区域跨度广，研究结果缺乏更为精细的区域特征。

对于我国中西部地区，新型城镇化更是统筹城乡协调发展、推动社会进步、实现跨越式发展的着力点。浙江省作为我国城镇化改革发展的典型地区，其城镇化具有专业化分工、区域产业聚集等特点，城乡发展水平平衡,已形成典型的“浙江模式”[]截止2017年初，浙江省城镇化率已达到 $67 \%$ ，远高于全国平均水平。为此，本文旨在分析和阐明新型城镇化背景下浙江省县域城镇化发展时空演变特征，为我国中西部地区新型城镇化发展提供参考。

# 1新型城镇化内涵及特征

新型城镇化的目标是实现经济、社会、环境、文化全面转变的城乡一体化的发展，是在尊重经济社会发展的客观规律的基础上，通过统筹城乡发展、经济社会发展、区域发展，构建大、中、小城市和小城镇协调发展的城镇体系，其发展过程具有科学性和协调性[25-26] ○

与传统城镇化相比，新型城镇化除体现在人口城镇化外，更体现在产业结构的优化转型、社会和生态环境的协调发展和城乡一体化的发展。新型城镇化是社会经济协调发展的必由之路，与工业化、信息化和农业现代化互生共进，对于缩小城乡差距、助推城乡转型发展具有显著的正向影响。

新型城镇化是对城镇化内涵的重新界定和升华,注重以人为本，强调差异性目标与同一性目标的整合性建构，注重政府、市场、社会、公众之间的互动,坚持全面、协调、可持续的科学发展观[25]。因此,在新型城镇化水平测算过程中,既要包括传统城镇化过程中人口、经济和空间的城镇化，还应重点突出人口素质、生活品质和城乡统筹发展，以及创新驱动在可持续发展过程中的重要作用。

# 2新型城镇化水平评价体系与方法

# 2.1 评价指标体系

根据上述新型城镇化的特点，本文根据浙江省经济社会发展特点，并参考同类研究中指标选取原则[22-25],在传统人口城镇化、经济城镇化和空间城镇化的基础上，同时考虑社会城镇化、居民生活质量、城乡统筹发展和创新发展，构建了涵盖以上7个方面、共26项指标组成的多层次、全方位新型城镇化综合水平评价指标体系（表1）。本文在浙江省新型城镇化指标的选取过程中，主要基于以下两方面的考虑：

（1）为体现传统城镇化特点，在人口城镇化方面，考虑人口由乡村向城镇聚集、农业人口转化为非农人口、第二、三产业从业人员增加等方面的因素；在经济城镇化方面，强调城镇化是促进经济发展的重要作用，体现出城镇化过程也是生产要素在城镇的集聚并强调"集约发展”这一特征;在空间城镇化方面,突出其本质是城镇化地域和景观的发展变化过程，除人均城镇住房面积和人均道路面积外，进一步考虑以建成区人均公园绿化面积和建成区绿化覆盖率衡量空间城镇化水平；在社会城镇化方面，强调基本公共服务均等化，在于使更多的居民广泛地享受社会资源与经济发展带来的福利，使农村转移人口真正融入城镇，从居民生活水平、医疗、教育、社会保障等方面进行展现

（2）为体现新型城镇化特点，尤其是浙江省居民生活质量提升速度快、城乡统筹发展与创新发展突出的特点，在居民生活质量方面，本文注重居民生活质量的提升，包括民用汽车拥有量、每万人医疗机构床位数、万人拥有互联网用户数和基本医疗保险参保人数。而城乡统筹发展则从城乡居民储蓄存款年末余额、城乡居民生活用电和城镇/农村居民纯收入比进行衡量。在创新发展方面，本文从创新人才与创新成果两个方面，选取万人高校师生数和每万人拥有申请专利授权数衡量创新发展。

# 2.2评价指标权系数确定

在城镇化水平计算过程中，各个评价因子权重决定了最终评估结果是否合理。主观赋权法能够反映专家经验，但通常具有很大的主观随意性。客观赋权法具有较强的数学理论依据，可以避免评价结果的主观随意性，但忽略了评估过程中的专家经验和随机性。因此，本文基于最优化理论，根据状态矩阵动态给定评价因子的权值。

2.2.1常权重系数的确定假设由主、客观赋权法得到的属性集权向量分别为 $w ^ { \mathrm { s } }$ 和 $w ^ { \mathrm { { ^ { o } } } }$ ，用 $\alpha \mathcal { \beta }$ 分别表示主观权重 $w ^ { \mathrm { s } }$ 和客观权重 $w ^ { \mathrm { { ^ { o } } } }$ 的重要程度，客观赋权法采用主成分分析法[27]，主观赋权采用层次分析法对各指标进行赋权[28],最终得到：

表1新型城镇化发展水平评价指标体系  
Tab.1Evaluation index system of the new-type urbanization development level   

<html><body><table><tr><td>准则层</td><td>变权值</td><td>指标层(单位)</td><td>变权值</td></tr><tr><td>人口城镇化</td><td>0.149 7</td><td>非农人口占总人口的比重／% 第二/三产业从业人数占全社会从业人员数的比重／%</td><td>0.0511 0.0367</td></tr><tr><td rowspan="6">经济城镇化</td><td rowspan="6"></td><td>年末城镇从业人员数占全社会从业人员数的比重／%</td><td>0.034 0</td></tr><tr><td></td><td></td></tr><tr><td>城镇人口密度／人·km²</td><td>0.0280</td></tr><tr><td>人均GDP／元</td><td>0.043 0</td></tr><tr><td>第二/三产业产值比重／%</td><td>0.035 6</td></tr><tr><td>规模以上工业总产值／10元</td><td>0.042 7</td></tr><tr><td rowspan="5">空间城镇化</td><td rowspan="5">0.126 4</td><td>第三产业占GDP的比重／% 全社会固定资产投资占GDP比重／%</td><td>0.0300 0.0233</td></tr><tr><td></td><td>0.0448</td></tr><tr><td>人均城镇住房面积／m 人均道路面积／m</td><td>0.028 7</td></tr><tr><td>城镇人均公园绿地面积／m</td><td>0.0317</td></tr><tr><td>城镇建成区绿化覆盖率／%</td><td>0.0211</td></tr><tr><td rowspan="3">社会城镇化</td><td rowspan="3">0.164 6</td><td>城镇居民人均可支配收入／元</td><td>0.032 5</td></tr><tr><td>人均社会消费品零售总额／元·人-1</td><td>0.0380</td></tr><tr><td>教育事业费占预算内财政支出的比重／%</td><td>0.0339</td></tr><tr><td rowspan="5">居民生活质量</td><td rowspan="5">0.210 7</td><td>每万人拥有卫生技术人员数／人</td><td>0.0322</td></tr><tr><td>民用汽车拥有量／辆</td><td>0.0371</td></tr><tr><td>每万人拥有医疗机构床位数／张</td><td>0.0328</td></tr><tr><td>万人拥有国际互联网户数／户</td><td>0.027 6</td></tr><tr><td>基本医疗保险参保人数／104人</td><td>0.044 5</td></tr><tr><td rowspan="3">城乡统筹发展</td><td rowspan="3">0.158 3</td><td></td><td>0.049 5</td></tr><tr><td>城乡居民储蓄存款年末余额／10元 城乡居民生活用电／104kW·h</td><td>0.050 4</td></tr><tr><td>城镇/农村居民人均可支配收入比</td><td>0.0542</td></tr><tr><td rowspan="2">创新发展</td><td rowspan="2">0.0863</td><td>每万人拥有申请专利授权数／项</td><td>0.0451</td></tr><tr><td>万人高校在校学生数数／人</td><td>0.040 7</td></tr></table></body></html>

$$
w _ { j } = \alpha w _ { j } ^ { \mathrm { s } } + \beta w _ { j } ^ { \mathrm { s } }
$$

式中： $\alpha , \beta$ 分别表示客观权重与主观权重的相对重要程度， $0 \leqslant \alpha , \beta \leqslant 1 , \alpha + \beta = 1$

根据多属性决策的加权法则，可得决策方案的评价目标值为：

$$
d _ { i } \ = \ \sum _ { j = 1 } ^ { n } b _ { i j } w _ { j } \ = \ \sum _ { j = 1 } ^ { n } b _ { i j } ( \alpha w _ { j } ^ { \mathrm { s } } \ + \beta w _ { j } ^ { \mathrm { o } } )
$$

式中： $b _ { i j }$ 为规范化决策矩阵 $\boldsymbol { B } = \left( \boldsymbol { b } _ { i j } \right) _ { m \times n }$ 的元素。

对于城镇化水平而言， $d _ { i }$ 越大表示城镇化水平越高,如果 $d _ { i } > d _ { j }$ ,则方案 $S _ { i }$ 优于 $S _ { j }$ ○

$$
\mathrm { m a x } Z = \ : \sum _ { i = 1 } ^ { m } d _ { i } \ : = \ : \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } b _ { i j } ( \alpha w _ { j } ^ { \mathrm { s } } + \beta w _ { j } ^ { \mathrm { o } } )
$$

$$
\alpha ^ { 2 } + \beta ^ { 2 } = 1 , \alpha , \beta \geq 0
$$

应用Lagrange条件极值原理，可得到式（3）的最优解 $\alpha ^ { * }$ 和 $\beta ^ { * }$ ,并作归一化处理, $\alpha _ { N } ^ { * } = \alpha ^ { * } / ( \alpha ^ { * } +$

$\boldsymbol { \beta } ^ { * }$ ） $\beta _ { \mathrm { { N } } } ^ { * } = \beta ^ { * } / ( \alpha ^ { * } + \beta ^ { * } )$ ，由此得到最优综合权重Wjo

2.2.2变权重系数的确定由于仅采用常权重系数还不能准确地反映城镇化水平的真实状态。为此,本文引人变权公式对权系数进行调整[28]：

$$
w _ { j } ^ { ( v ) } = w _ { j } s \big ( x _ { j } \big ) \Bigg / \ \sum _ { p = 1 } ^ { n } w _ { p } s \big ( x _ { j } \big )
$$

式中： $s ( x )$ 为均衡函数，专指效益型指标，如规模以上工业总产值等。

$$
s ( x _ { j } ) = \left\{ \begin{array} { l l } { \mathrm { e } ^ { - \varepsilon \big ( \frac { x _ { j } - \lambda _ { j } } { \mid \gamma _ { j } + \gamma _ { j } - \ \rvert } \big ) } , \ x _ { j } < \lambda _ { j } } \\ { \ 1 \ \qquad \ , \ \sharp _ { \sf N } / \ \mathrm { i } \mathtt { j } . } \end{array} \right.
$$

式中： $x _ { j }$ 为第 $j$ 项指标状态值， $\lambda _ { j }$ 为指标 $j$ 的惩罚阀值；若第 $j$ 项指标为定量指标，则 $\lambda _ { j }$ 为某项指标全省平均水平; $\varepsilon$ 为惩罚水平， $\varepsilon > 0$ 且 $\boldsymbol { \varepsilon }$ 越大，惩罚效果越明显。 $\gamma _ { j } ^ { + } \cdot \gamma _ { j } ^ { - }$ 分别为第 $j$ 项指标的合格区间上、下界，本文选取全省平均水平 $\pm 1 0 \%$ 区间。

基于上述指标权重确定方法，得到表1所示准则层和指标层的各指标的权重。

# 2.3城镇化水平模糊综合评价方法

2.3.1评估指标的规范化处理新型城镇化水平评估涉及到众多评价因素，且评价因素之间一般存在着不可度量性，即不同因素有不同的度量标准。本文采用极大极小值法确定各指标对于城镇化水平的隶属度，即：

$$
\quad 0 \qquad 0 \leqslant x _ { i } \leqslant x _ { \mathrm { m i n } }
$$

$$
\mu ( x _ { i } ) = r _ { j } = \begin{array} { r l } { \displaystyle x _ { i } - x _ { \mathrm { m i n } } } & { { } \quad x _ { \mathrm { m i n } } \leqslant x _ { i } \leqslant x _ { \mathrm { m a x } } } \end{array}
$$

其他

式中： ${ \bf \nabla } \cdot \mu ( x _ { i } )$ 表示 $x _ { i }$ 的城镇化隶度; $x _ { i }$ 为评价指标 $i$ 的原始数据； $x _ { \operatorname* { m a x } { } } \mathbf { \Lambda } \mathbf { { \Lambda } } _ { \operatorname* { m i n } { } }$ 为该指标序列的最大、小值。

2.3.2模糊综合评价过程基于模糊综合评价的城镇化水平计算方法如式(6)所示，其中 $C$ 表示城镇化水平, $C$ 值越大表示城镇化水平越高[28] ○

$$
C = \big ( w _ { 1 } ^ { ( 1 ) } , w _ { 2 } ^ { ( 1 ) } , \cdots , w _ { j } ^ { ( 1 ) } \big ) \big ( C _ { 1 } C _ { 2 } , \cdots , C _ { j } ) ^ { T } , j = 6
$$

式中： $w _ { j } ^ { ( 1 ) }$ 为通过式(1)或式(4)得到的准则层 级指标权重值； $C _ { j }$ 为准则层第 $j$ 个指标的模糊评价向量，可由式(7)计算得到：

$$
C _ { j } = w _ { j } ^ { ( 2 ) } \times R _ { j } = \big ( w _ { j 1 } , w _ { j 2 } , \cdots , w _ { j k } \big ) \times
$$

$$
( R _ { j 1 } ^ { } , R _ { j 2 } ^ { } , \cdots , R _ { j k } ^ { } ) ^ { T }
$$

式中： $w _ { j k }$ 和 $R _ { j k }$ 分别为第 $j$ 个准则层指标下第 $k$ 个指标的二级权重和模糊向量; $R _ { j k }$ 由式(5)计算得到。

# 3浙江省县域新型城镇化水平分析

# 3.1研究区概况与数据来源

浙江省地处长江三角洲南翼，东临东海，南接福建，西与江西、安徽接壤，北与上海、江苏相连。陆域面积 $1 0 . 5 5 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,海域面积 $2 6 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,海岸线总长约 $6 ~ 4 0 0 ~ \mathrm { k m }$ ，沿海岛屿3000多个，至2016年底,全省总人口约 $5 5 9 0 \times 1 0 ^ { 4 }$ 人。浙江省的经济活力和发展速度以及城镇化进程均位居全国前列，其充分发挥了国有经济和民营经济的共同作用，是我国经济发展的典范之一。

研究数据来源于2007—2016年《浙江省统计年鉴》《中国城市统计年鉴》及各地市、县、区历年统计年鉴、国民经济和社会发展统计公报。研究对象为浙江省的22个县级市、35个县、11个市辖区、1个市区(鄞州区)和1个自治县，共70个县级行政单元。另外，2013年绍兴县设立为绍兴市柯桥区，2014年富阳市撤市设区,2015年洞头县撤县设区，为方便计算，按原来的绍兴县、富阳市、洞头县统计。考虑到数据的连续性，基于最新调整后的县域单元数量，对数据来源中未进行调整的县级数据进行了相应处理。

# 3.2浙江省县域新型城镇化时空格局

3.2.1时间分布特性基于以上数据,采用模糊综合评价法，计算得到了浙江省70个县级行政单元从2007—2016年共10a的新型城镇化水平。为了便于分析，本文将研究的70个县级行政单元进行了区域划分，共划分为5个区域(图1）。在此基础上，分别计算了所划分5个区域的新型城镇化平均水平。图2给出了浙江省2007一2016年间全省新型城镇化平均水平和分区域的新型城镇化平均水平。

由图2可知,2007—2016 年间，浙江省新型城镇化平均水平总体呈上升趋势，年均增速约为$0 . 2 6 \%$ 。在图1所示5个区域中，浙江北具有最高的新型城镇化水平，2007年为0.282，到2016年已发展至0.322，年均增速为 $0 . 3 6 \%$ ,其次为浙东北区域。相比之下，浙西南新型城镇化水平最低,2007年仅为0.166，到2016年才发展至0.183，年均增速不足 $0 . 1 5 5 \%$ ,2016年的新型城镇化水平远低于全省平均水平。浙江中部和浙东南略低于全省平均水平，其中浙江中部新型城镇化水平在部分年份略高于浙东南区域。

![](images/96d8fef559317982812473214e77f239c826c87a67f46e6250f5556d05a98477.jpg)  
图1依浙江省新型城镇化水平划分的空间区域 Fig.1Divided spatial region according to the new-type county urbanization level of Zhejiang Province

![](images/79428343d236bbbac548b44e39b587661f1c89649d0b4652814856c496dffbf9.jpg)  
图22007—2016 年浙江省新型城镇化发展趋势 Fig.2Development trend of the new-type urbanization in Zhejiang Province from 2OO7 to 2016

3.2.2空间分布特性依据浙江省70个县级行政单元的新型城镇化综合水平计算结果，用ArcGIS10.2软件平台，采用自然断裂法，将2007年浙江省新型城镇化水平进行定级。然后，基于2007年的等级划分阈值，对此后2007—2016年的新型城镇化水平进行了定级，划分阈值如表2所示。

为研究其空间分布特性，以每3a为研究步长，特选取2007年和2016年为时间断面，得到如图3所示的浙江省县域新型城镇化空间分布。

# 表2新型城镇化发展水平等级划分

Tab.2Divided standard level of the new-type countyurbanization   

<html><body><table><tr><td>等级划分</td><td>阈值</td><td>等级划分</td><td>阈值</td></tr><tr><td>较高水平（I)</td><td>>0.40</td><td>中等偏低水平（IV）0.18~0.24</td><td></td></tr><tr><td>相对较高水平（Ⅱ)</td><td>0.29~0.40</td><td>较低水平（V）</td><td><0.18</td></tr><tr><td>中等水平(Ⅱ)</td><td>0.24~0.29</td><td>1</td><td>1</td></tr></table></body></html>

![](images/ec987af1157ea2cf63e87662c69a62a2184a4a242c1631976bae749b97b647ba.jpg)  
图3浙江省县域新型城镇化水平空间分布  
Fig.3Spatial distribution of the new-type county urbanization level of Zhejiang

从图3可知，浙江省县域新型城镇化水平在空间上总体呈：（1）从浙江北向浙西南逐步递减。(2）以杭州市市辖区、宁波市市辖区、温州市市辖区等三个区域带动周边发展的特性。（3）以杭州为中心带动周边及中部发展，进而由中部影响到西南部。（4）从2007一2016年，新型城镇化水平较高区域从北部逐渐向中部和西南延伸；浙北部和浙东北辐射带动周边区域新型城镇化发展水平作用明显。根据表2划分的5个等级，结合图3对2016年浙江省新型城镇化水平的空间分布差异进行了总结分析，如表3所示。

表3新型城镇化水平空间分布  
Tab.3Spatial distribution of new-type county urbanizatior   

<html><body><table><tr><td>类型</td><td>区位空间</td><td>代表地区</td></tr><tr><td>I</td><td>浙东北、浙江 北、浙东南</td><td>杭州市辖区、宁波市辖区、温州市辖区、 越城区</td></tr><tr><td>Ⅱ</td><td>浙北部区域、 浙江中部、浙 东北、浙东南</td><td>绍兴县、上虞市、嘉兴市辖区、湖州市辖 区、金华市辖区、舟山市辖区、平湖市、 鄞州区、台州市辖区、义乌市等</td></tr><tr><td>ⅢI</td><td>浙西北、浙中 部、浙东南</td><td>长兴县、德清县、富阳市、东阳市、余姚 市、上虞市、永康市、温岭市、乐清市、玉 环县、苍南县、丽水市辖区、嵊州市等</td></tr><tr><td>V</td><td>浙西北至浙西 南、浙江东至 东南</td><td>安吉县、临安市、桐庐县、浦江县、龙游 县、奉化市、新昌县、宁海县、象山县、磐 安县、仙居县、武义县、永康市、永嘉县、 平阳县、建德市、遂昌县等</td></tr><tr><td>V</td><td>浙江东、浙江南</td><td>衢州市辖区、淳安县、开化县、常山县、 江山市、庆元县、景宁县、文成县等</td></tr></table></body></html>

从表3可知，I类区域主要集中在杭州市辖区、宁波市辖区、温州市辖区以及绍兴市辖区越城区；II类区域主要集中在嘉兴市辖区、湖州市辖区、台州市辖区、舟山市辖区、金华市辖区及义乌市等。IⅢI类区域主要集中在长兴县、德清县、富阳市、东阳市、嘉兴市辖区的周边区域、丽水市辖区以及嵊州市等。IV 类区域主要集中在浙西北安吉县、临安市、桐庐县、建德市、兰溪市、金华市辖区的南部以及浙东南大部分区域。V类区域主要分布在浙江西的淳安县、开化县、常山县、江山市、衢州市辖区以及丽水市辖区的南部区域。因此，从整体上看，中等水平以上分布在浙江北及中部,呈“倒三角”分布，此外，还有浙东南的小部分区域。中等水平以下区域主要分布在浙江西南、西北及浙东南，及“倒三角”之外的几乎所有区域。

# 3.3县域新型城镇化空间集聚特征

为进一步研究浙江省县域新型城镇化的空间分布特征，采用系统聚类法对浙江省分县域城镇化水平进行聚类分析[29]。系统聚类法的思想是通过某种相似性测度计算节点之间的相似性，并按相似度由高到低排序，逐步重新连接个节点。因此聚类结果中各类所含指标具有相似性。考虑到城镇化水平指标较多，首先采用PCA进行降维处理，得到了反映城镇化水平的5个主成分（累积贡献率 $> 8 0 \%$ ）。在此基础上，选用最邻近元素法，在SPSS22.0软件平台上进行聚类分析，得到了如图4所示谱系图。

![](images/159af27b4c56e28974bf0bd34c4a127d974b3c63265aa6d84da700ceabe0764b.jpg)  
图4浙江省县域新型城镇化聚集特征 Fig.4Cluster feature of the new-type county urbanization of Zhejiang

由图4可以看出，在组间距离为6时，所研究的70个县级行政单元可分为6类，其中杭州市辖区和舟山市辖区各为一类，宁波市辖区及下属奉化市形成一类，这和图3所示的空间格局基本一致，主要是这几个区域的新型城镇化水平在所研究的所有县级单元中处于中等偏高或较高水平。此外,东阳市、绍兴县、诸暨市、松阳县、武义县、安吉县等（中等水平)以及青田县、淳安县(较低水平)等区域形成一类;温州市辖区周围的永嘉县、瑞安市、平阳县等形成一类;嘉兴市辖区和金华市辖区等地区形成一类

（中等偏高）。

这种空间集聚特征的形成原因总结为：（1）从区位空间特征来看，浙江北部紧邻上海、江苏，南部靠近福建。这些邻近省市的经济水平均为全国领先，可充分发挥空间集聚效应、相互促进、共同发展。（2）从自然空间特征来看，浙江省的主要城市分布在东南沿海地区、长三角平原沿江沿湖地区，便利的水陆交通、港口等，这种优越的地理位置使得浙江既有利于对外交往又有利于向内扩张。

图4所示聚类结果具有明显的地域聚集特征，即较高城镇化水平区域形成单独分类,其周边中等偏高水平，篇高水平区域形成环绕较高水平区域分布状态或者为同一类区域较低水平区域为一类。聚类结果和图3所示空间格局具有较好的一致性。

# 3.4 评价因素分析

为了分析评价指标对新型城镇化水平的影响，选取2007、2010、2013年和2016年为时间断面，分别计算了表1准则层中反映新型城镇化水平的7个主要指标对新型城镇化水平的贡献程度，结果如图5所示。

![](images/83443873af03b84a674528b1ab21808893f603c1cc43ee7f95c3a5ec3b588a2e.jpg)  
图5不同城镇化指标对新型城镇化水平的贡献情况 Fig.5Contribution of different indexes to the new-type urbanization

从图5可以看出，人口城镇化、经济城镇化和社会城镇化对新型城镇化水平的贡献程度最大，其次为空间城镇化、居民生活质量和城乡统筹发展,创新发展对于新型城镇化的贡献程度有限。在2016年，除城乡统筹发展和创新发展两个方面外，其他5个方面相较往年均有所提升或基本保持一致(2012年的人口城镇化）。从2007—2016年，经济城镇化呈递减趋势；人口城镇化、空间城镇化、社会城镇化和居民生活质量4个指标保持平稳。相比之下，城乡统筹发展和创新发展呈逐年递增趋势，尤其在2013—2016年间发展较快。这主要是由于城乡居民人均收入差距倍数、城乡居民人均消费支出差异度两大指标得分增长较快，城乡差距分别从2013年的2.35、1.98 缩小至 $2 . 0 9 , 1 . 8 8 ^ { [ 3 0 ] }$ 。这一状况既表明着浙江省各县域农村居民收入增长快于城市居民，居民收入分配格局不断优化；也反映了全省消费潜力的提升和收支结构持续优化，

图6给出了2007年和2016年由图1划分的不同区域新型城镇化准则层各指标得分比重，可以看出：在创新发展、居民生活质量、经济城镇化和人口城镇化方面，浙江北和浙东北得分情况好于其他三个区域。在城乡统筹发展和社会城镇化方面，浙江北处于全省前列，其他四个区域水平相当。而在空间城镇化方面，浙西南则略高于其他四个区域，这主要由于浙西南地区在城镇化建设方面主要体现在空间城镇化，具体表现为人均住房面积、人均道路面积和人均公园绿地面积等方面的增长。

![](images/8a8ca15ff0949a524a85eeb06c68f4b1d12c30c5c632b65188be85e21d5f9614.jpg)  
图6不同区域新型城镇化准则层各指标得分比重 Fig.6Proportion of each index in the new-type urbanization standard layer in different regions

# 4结论

本文根据新型城镇化内涵及特征，构建了新型城镇化水平综合评价体系，运用模糊综合评价法计算了浙江省各县域行政单元2007—2016 年新型城镇化水平;在ArcGIS平台上进行了可视化分析，分析总结了浙江省县域新型城镇化水平时空格局演变特征，结论如下：

（1）浙江省县域新型城镇化水平在时间上总体呈缓慢上升趋势，在空间上总体呈现北高南低、东西部发展水平不均衡的特征。新型城镇化水平从浙江北向浙西南、浙东北向浙东南逐步递减，北部、东北地区水平相对较高，中部次之，东部、南部及西部水平较低，从高到低呈“倒三角"特征。

（2）浙江省县域城镇化发展呈空间集聚态势，北部杭州、东北部宁波和东南部温州为三个高水平区域中心，西部开化、衢江和南部景宁等地为两个典型低水平区域中心。新型城镇化水平较高的杭州、嘉兴、绍兴等地对周边区域发展具有十分明显的辐射带动作用，宁波、舟山带动周边发展能力较明显，而温州、台州等地对周边地区的带动作用不明显。

（3）传统城镇化指标对新型城镇化水平贡献较大，居民生活质量、城乡统筹发展和创新发展对于新型城镇化贡献度有限，但城乡统筹发展和创新发展的贡献呈逐年上升趋势，反应了城乡居民收入分配格局的不断优化以及创新驱动在新型城镇化建设中的重要性在逐步凸显。

（4）浙江北和浙东北新型城镇化水平较高得益于其创新发展、居民生活质量、经济和人口城镇化情况好于其他区域，尤其在城乡统筹发展和社会城镇化方面，浙江北处于全省前列。发展水平较低的浙西南仅在空间城镇化方面略高于其他区域。

# 5讨论

本文采用人口城镇化、经济城镇化、空间城镇化、社会城镇化、居民生活质量、城乡统筹发展和创新发展7个主要指标来评价浙江省县域新型城镇化水平。新型城镇化强调以人为核心，以绿色发展、智慧发展、环境友好及生态宜居等为建设理念。在本文研究过程中，由于生态环境类指标如生活污水处理、垃圾处理量等数据不全，目前无法系统的计算这一指标。因此,将反映生态环境发展的因素如建成区人均公园绿地面积、建成区绿化覆盖率等指标暂且归入空间城镇化。此外，各准则层指标所包含的具体指标仍有待完善，如创新发展方面，不同地区的科研经费投入、创新人才数量等数据难以获得，以上方面仍有待加强。

从本文分析结果可以看出，浙江省县域新型城镇化的发展具有明显的地域带动效应和空间辐射特性。浙江省并不是一个孤立的省份，周边省份的经济发展对浙江省的综合城镇化水平也产生着较深的影响，尤其是对于边缘县域,这也是未来需进一步研究解决的问题。

# 参考文献(References）

[1]杨振,雷军,英成龙,等.新疆县域城镇化的综合测度及空间分异格局分析[J].干旱区地理，2017，40（1）：230-237.［YANGZhen,LEI Jun,YING Chenglong,et al. Comprehensive measure-ment and spatial differentiation pattern analysis of the county ur-banization in Xinjiang[J].Arid Land Geography,2O17,40（1）：230 -237.]

[2］李祺.城市基础设施建设融资模式存在的问题及对策[J].中国市场,2017，（29）:41-42.［LIQi.Problems and solutions inthe financing mode of urban infrastructure construction[J].Chi-neseMarket,2017，（29):41-42.]

[3］曹广忠,边雪,刘涛.基于人口、产业和用地结构的城镇化水平评估与解释——以长三角地区为例[J].地理研究，2011，30（12）:2139-2149.［CAO Guangzhong,BIAN Xue,LIU Tao.Comprehensive evaluation of the urbanization level in Yangtze Riv-er region:An index framework based on the population,economicstructure and land use[J].Geographical Research,2O11,30(12）：2139 -2149.]

[4］刘雅静.城镇化发展水平综合评估指标体系研究[J].中共银 川市委党校学报,2012,14（2）:50-52.[LIUYajing.Research on comprehensive assessment index system of urbanization level [J].Journal of the Yinchuan Municipal Party College of C.P.C, 2012,14(2):50-52.]

[5］李华斌.2000—2010 年中国城镇化空间发展特征及其影响因素研究[D].济南：山东建筑大学，2015.［LIHuabin.Spatial de-velopment characteristics and influencing factors of urbanization inChina during the 2OoO-2O1O［D].Jinan:Shandong Jianzhu Uni-versity,2015.]

[6］宾津佑,李民.长株潭城市群农业现代化与新型城镇化发展的耦合协调分析[J].中南林业科技大学学报（社会科学版），2017,11(4）:34-40.[BIN Jinyou,LI Min.The coordination de-velopment analysis of agricultural modernization and new urbaniza-tion in Chang-Zhu-Tan urban agglomeration[J].Journal of CentralSouth University of Forestry & Technology（Social Sciences）,2017,11(4):34 -40.]

[7]余波,刘松,熊鹰，等.基于主成分分析的西藏自治区城镇化空间分布类型[J].华南师范大学学报（自然科学版），2017，49(4）:1-8.[YU Bo,LIU Song,XIONG Ying,et al. Study on spa-tial distribution pattern of urbanization of Tibet autonomous regionbased on principal analysis[J]. Journal of South China Normal U-niversity（Nature Science Edition）,2017,49(4）:1-8.]

[8］鲍超.中国城镇化与经济增长及用水变化的时空耦合关系 [J].地理学报,2014,69（12）：1799－1809.［BAO Chao.Spatial-temporal coupling relationships among urbanization,economic growth and water use change in China[J].Acta Geographical Sinica,2014,69(12):1799-1809.]

[9］王艳飞,刘彦随,李裕瑞.环渤海地区城镇化与农村协调发展 的时空特征[J].地理研究,2015,34（1）：122-130.［WANG Yanfei,LIU Yansui,LI Yurui. Spatial-temporal patterns of urbanization and rural development and their coordination in Bohai Rim region[J].Geographical Research,2015,34（1）:122-130.]

[10］杨剩富,胡守庚,叶菁,等.中部地区新型城镇化发展协调度时 空变化及形成机制[J].经济地理，2014，34（11)：23－29. [YANG Shengfu,HU Shougeng,YE Jing,et al.Spatial-temporal variation and formation mechanism of neo-urbanization develop ment coordination in central China［J].Economic Geography, 2014,34(11) :23-29.

[11］张立生.县域城镇化时空演变及其影响因素—以浙江省为 例[J].地理研究,2016,35(6）:1151-1163.[ZHANG Lisheng. Spatial-temporal evolution of county urbanization and its influencing factors in Zhejiang Province[J].Geographical Research, 2016,35(6):1151- 1163.]

[12］李爱民，孙久文.我国区域性城镇化发展格局研究[J].区域经 济评论,2015，(2):129-135.[LIAimin,SUNJiuwen.Study on the development pattern of regional urbanization in China[J].Regional Economy Review,2015,(2）:129-135.]

[13］宋华锋.我国城镇化空间格局选择的增长极与差异化[J].商 业时代,2014,（26）:45-46.[SONGHuafeng.Growth pole and differentiation of the choice of the spatial pattern of urbanization in China[J].Commercial Times,2014,（26）:45-46.]

[14］刘彦随，杨忍.中国县域城镇化的空间特征与形成机理[J].地理学报,2012,67（8）：1011-1020.［LIUYansui,YANGRen.The spatial characteristics and formation mechanism of the countyurbanization in China[J].Acta Geographica Sinica,2O12,67（8）：1011 -1020.]

[15］刘兆德,刘强，刘振明，等.中国省域城镇化综合水平的空间特征与影响因素[J].城市发展研究，2017，24(3)：95-101.［LIUZhaode,LIU Qiang,LIU Zhenming,et al. Spatial characteristicsand factors affecting of comprehensive level of urbanization in theProvinces of China[J].Urban Development Studies,2017,24（3）：95 -101.]

[16］霍炳男.中国区域城镇化发展差异的影响因素研究—基于1992—2015 年省际面板数据的经验分析[J].经济问题探索，2017,24(4）:76-82.[HUO Bingnan.Research on the influen-cing factors of regional urbanization development in China:Basedon the empirical analysis of provincial panel data between 1992-2015[J].Inquiry into Economic Issues,2017,24（4） :76 -82.][17］陆大道，姚士谋.中国城镇化进程的科学思辨[J].人文地理,2007,（4）:1-5.[LUDadao,YAO Shimou.A scientific thoughtof urbanization process in China[J].Human Geography,2007,(4):1-5.]

[18」戈大专，龙花楼，屠爽爽，等.新型城镇化与扶贫开发研究进展与展望［J].经济地理,2016,36（4）：22-28.[GEDazhuan,

LONG Hualou,TU Shuangshuang,et al.Research progress and prospect of new-type urbanization and poverty alleviation and development[J].Economic Geography,2016,36(4）:22-28.]

[19］牛文元.中国新型城市化报告2009［M].北京：科学出版社，2009.［NIUWenyuan.China's new urbanization report 2OO9[M].Beijing:Science Press,2009.]

[20］胡际权.中国新型城镇化发展研究[D].重庆：西南农业大学，2005:82-84.［HU Jiquan.Development of the new urbanizationin China[D].Chongqing:Southwest Agricultural University,2005 :82 -84.]

[21］杨帆.新型城市化及其评价指标[J].理论学习,2008，（9）：30, 41.［YANG Fan.New urbanization and the evaluation index[J]. Theoretical Study,2008,（9) :30,41.]

[22］牛晓春,杜忠潮,李同昇.基于新型城镇化视角的区域城镇化 水平评价——以陕西省10个省辖市为例[J].干旱区地理， 2013,36（2）:354-363.［NIUXiaochun，DUZhongchao,LI Tongsheng.Evaluation of regional urbanization level based on new urbanization：A case of1O provincial cities in Shanxi Province[J]. AridLand Geography,2013,36(2）:354-363.]

[23］刘超，克红，丁镭，等.新型城镇化背景下西部欠发达地区城镇 化的空间格局——以贵州省为例[J].江苏农业科学，2017，45 (12）:299-304.[LIU Chao,KE Hong,DING Lei,et al.Spatial pattern of urbanization in less developed areas of Western China under the background of the new-type urbanization:Take Guizhou Province as an example[J]. Jiangsu Agricultural Sciences,2017, 45(12):299-304.]

[24］杨勃，石培基.甘肃省县域城镇化地域差异及形成机理[J].干 旱区地理,2014,37（4）:838-845.[YANGBo,SHIPeiji.Geographical features and formation mechanisms of county level urbanization in Gansu Province[J].Arid Land Geography,2014,37 (4):838 -845.]

[25］王新越,秦素贞，吴宁宁.新型城镇化的内涵、测度及其区域差异研究[J].地域研究与开发，2014,33（4）：69-75.［WANGXinyue,QIN Suzhen,WU Ningning.Connotation,measurement ofnew-type urbanization and the characteristics of its spatial variation[J].Areal Research and Development,2014,33（4）:69-75.][26］徐选国，杨君.人本视角下的新型城镇化建设：本质、特征及其可能路径［J].南京农业大学学报（社会科学版），2014，14(2）：15-2O.[XU Xuanguo,YANGJun.New urbanizationunderhumanistic perspective：Nature，characteristicsand its possiblepaths[J]. Journal of Nanjing Agricultural University（Social Sci-encesEdition）,2014,14(2):15-20.]

[27］赵文英.基于主成分-灰色关联度的黑龙江省城镇化水平综 合评价[J].数学的实践与认识，2014，44（6）：43-50.［ZHAO Wenying.Comprehensive evaluation of the urbanization level in Heilongjiang Province based on the principal component-grey relational analysis[J].Mathematics in Practice & Theory,2014,44 (6):43 -50.]

[28］刘亚臣，常春光，刘宁，等.基于层次分析法的城镇化水平模糊综合评价［J].沈阳建筑大学学报（自然科学版），2008，24(1）:132-136.[LIU Yachen,CHANG Chunguang,LIU Ning,etal.AHP based fuzzy comprehensive evaluation for tonifying level[J].Journal of Shenyang Jianzhu University（Natural Science），2008,24(1):132-136.]

[29］金善女，李娅.基于全局因子分析和聚类分析法的欠发达地区新型城镇化研究——以河北省11个地级市为例[J」.河北工业大学学报（社会科学版）,2015,7（1）：26-33.［JIN Shannv，LI Ya.New type of urbanization of the less developed areas byglobal factor analysis and cluster analysis[J]. Journal of Hebei U-niversity of Technology（Social Science Edition）,2015,7（1）：26-33.]

[30］浙江省发展和改革委员会.浙江省2014年统筹城乡发展水平 评价报告［EB/OL].http://www.zjdpc.gov.cn/art/2016/1/15/ art_809_1631210.html.［Zhejiang Development and Reform Commission.Evaluation report on the overall planning of urban and ru ral development in Zhejiang Province in 2O14［EB/OL].http:// www.zjdpc.gov.cn/art/2016/1/15/art_809_1631210.html.

# Temporal-spatial pattern and accumulation characteristics of county scale urbanization from the perspective of new-type urbanization : A case of Zhejiang Province

WANG Yan-xia1.2， WANG Pei-an1,2 (1Facultyof Geomatics,Lanzhou Jiaotong University,Lanzhou73oo7o,Gansu,China；2Gansu Provincial Engineering Laboratory forNationalGeographicStateMonitoring,LanzhouJiaotong University,Lanzhou 730o7,Gansu,China)

Abstract：Based on thecharacteristics and connotation of the new-type urbanization,the evaluation system forassessing he county regionurbanization level in Zhejiang Province,China is constructed byselecting 7factors,which include the population,theeconomy,thesociety,the space,the lifequalityofresidents,theurbanand ruralcoordinated developmentand innovation development,and 26 indicators outof the selected factors.The new-type urbanization levels of7O administrative units in the province arecalculated byusing afuzzy comprehensiveevaluation method from 2OO7 to 2016.Basedon this,the ArcGIS is used to visualize and analyze thecalculation results,and the systemclustering method is used to verifythe results.The results showedas folows:（1）overall the new-type urbanization level of the county region of Zhejiang Province was slowly increased,and theresults exhibit an“inverted triangle”distribution patern from spatial perspective.（2）three high-level regional centersand two low-levelregional centers are formed,the high-level regional centershave obvious fan-out effctson the surrounding regions.（3）the traditional urbanization indicators make a greater contribution tothe new-type urbanization,whilethecontributionof urban and rural cordinated development and innovation development were increased year by year.（4） the highlevel regions of new-typeurbanization can atribute to their innovation development,and the urban andrural coordinated development and society urbanization in these regions are outstanding if compared with other regions.

Key words:：New-type urbanization；temporal-spatial pattern；analytic hierarchy process；principal component analysis；fuzzy comprehensive evaluation；hierarchical clustering method