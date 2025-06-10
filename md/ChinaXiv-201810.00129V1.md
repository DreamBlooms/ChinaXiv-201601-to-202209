# 中国地级及以上城市对外开放度时空分异格局

张永年，潘竟虎

(西北师范大学地理与环境科学学院，甘肃兰州730070)

摘要：对外开放是推动中国经济改革与发展的重要机制和动力，是国家繁荣发展的必由之路。以中国343个地级及以上行政单元为研究对象，通过构建熵值一突变系统模型从3个维度测算对外开放度;运用探索性空间数据分析、三维插值拟合分析及重心迁移、空间变差函数等方法，分析中国地级单元对外开放度的时空分异格局及演化的内在机理。结果显示：(1)中国地级单元对外开放度表现出明显的行政指向性、空间地带性和开放区域性等多重分异特征。对外开放度整体呈现东部 $>$ 中部 $>$ 东北 $>$ 西部，南方 $>$ 北方的特征；直辖市、副省级城市、省会城市、经济特区及沿海开放城市整体对外开放水平较高,地级市间差异较大;10a间，对外开放度总体差异逐渐减小。（2)对外开放度存在明显的空间依赖性，表现为“小分散大集聚”的空间俱乐部趋同特征;10a间，开放型纹理分散程度趋于提升，闭塞型纹理集聚程度趋于收敛，高原型整体呈破碎化分布。(3)中国对外开放度格局变异的随机成分在逐渐减小，空间自组织性和连续性较为显著，东北—西南方向均质性最好,东南一西北方向空间差异明显。科学剖析地级单元对外开放度时空格局分异及演化机理，对制定合理的对外开放战略和促进外向型经济与区域经济双轨融合发展具有重要的意义。

关键词：对外开放度；突变级数法；ESDA-GIS；时空分异；中国中图分类号： 文献标识码：A 文章编号：

对外开放是中国的一项基本国策。1978年一至今，中国的对外开放经历了以下4个时期：探索期（1978一1992）：放权、让利、减税，培育市场经济；发展期(1992—2001）：建设中国特色社会主义市场经济体制;加速期（2001—2015）：加入WTO，向国际市场规则接轨;变革期（2015一至今）：全方位开放进入新阶段，“开放发展”成为新时期国家五大发展理念之一。4个时期持续发展，加之“引进来"到"走出去”、自贸区、“一带一路"3大对外开放发展战略的实施，促使中国逐渐形成全方位、多层次、宽领域的对外开放格局。据国家统计局及海关总署发布的年度数据显示，2016年底，中国进出口贸易总额已达$2 4 . 3 3 \times 1 0 ^ { 1 2 }$ 元,比2000 年增长了6.2倍,外商直接投资总额 $1 2 6 0 \times 1 0 ^ { 8 } \ \mathrm { U S D }$ 。国家“十三五"规划明确指出：“开放是国家繁荣发展的必由之路，必须顺应我国经济深度融人世界经济的趋势，奉行互利共赢的开放战略。”

对外开放度又称对外依存度，是衡量一个国家或地区在国际经济活动交往中的发展水平、规模以及对国际经济依赖程度的重要指标。针对如何测度对外开放度水平，国内外学术界开展了大量研究。由于对外开放与国家间经济相互关联包含非常复杂的机制，并不是单一指标的对向关联，因此，至今没有形成一套成熟的测度体系。BALASSA在研究跨国经济中将对外贸易依存度和出口增长率两个指标用于直接体现对外开放度[1]。HOEFFLER和CUADROS等认为在全球经济与资本的快速流动与配置环境下，需要考虑对外贸易与投资两个方面的因素来综合测度对外开放[2-3]。世界经济论坛（WEF)则选取进出口商品和服务、外商直接投资、保护主义倾向等8种统计指标和调查指标来综合反映国家的对外开放度[4]。我国学者对对外开放度也进行了深入研究，研究内容主要集中于对外开放度与经济增长的关系[5-6],大多认为对外开放与经济增长呈正向相关性。研究尺度上，多将地理学与经济学紧密联系，研究对比在不同区域、不同尺度层面的对外开放度。宏观尺度包括全国[]和省域[8-9]层面,中观尺度主要涉及经济带[0]等综合区域,也有少数研究市域等小尺度区域对外开放度[11]。研究方法主要包括多因子主观赋权法[12]、因子分析法[13] $\mathrm { V A R } ^ { [ 1 4 ] }$ 模型等。梳理现有研究发现,不同学者的测算指标体系有所差异，时空间耦合分析研究深度不够，研究方法上指标权重的确定主观性较强，研究尺度上主要以国家、经济带、省域等大尺度区域为主，且多偏重于单一尺度变化趋势的研究，全国范围内的市县等中小尺度的研究关注较少，研究方法上鲜见GIS空间分析手段与方法的应用。我国实行“市辖县”的行政管理体制，地级市具有承上启下的重要作用，且其行政范围相对稳定，统计数据相对健全，因此，研究中国地级及以上城市的对外开放度具有很强的代表性，对于中国区域对外开放时空格局的判别具有明显的指示作用。基于此，本文在构建对外开放度综合评价体系的基础上，运用突变理论与GIS空间计量测度方法，分析地级及以上行政单元（下文简称地级单元)对外开放度的空间格局演变特征，并对其格局演化的内在机理进行探究，以期为政府在经济新常态形势下制定合理的对外开放战略和区域协调发展政策提供科学参考。

# 研究方法和数据

# 1.1评价指标的选取与数据来源

本文主要是从经济对外开放的角度出发来考虑各地级及以上城市的对外开放度。综合相关学者[7-10]的研究,指标的选取基于数据易于搜集、量化及与突变级数系统模型相适应性等原则，从对外开放度的内涵出发，建立对外开放度的测度指标体系。具体包含： $\textcircled{1}$ 外贸依存度，侧重于衡量地级单元国民经济外向程度的大小; $\textcircled{2}$ 外资依存度，主要体现地级单元资本开放程度及对外经济发展前景潜力的大小； $\textcircled{3}$ 对外旅游开放度，主要反映地级单元接待国际游客的规模和水平。以2012年中国343个地级单元为评价单元，香港、澳门、台湾由于数据缺失未包括在分析之列。为保持行政单元的空间完整，将4个直辖市及部分省直辖的县级行政区（湖北省潜江市、仙桃市、天门市和神农架林区，河南省济源市，新疆石河子市等)亦纳入分析范围。此外，海南省只有海口市、三亚市属于地级市，因此将其余16 个省直辖行政单元合并为一个单元，其对外开放度用除去2市以外的全省平均值代替。

研究时点为2005年和2015年，2005年原始数据主要来源于《中国区域经济统计年鉴》，2015年原始数据主要来源于各省的统计年鉴。个别地区在个别指标上数据不完整，从相应年份的《中国城市统计年鉴》、各地级单元对应年份的《经济和社会发展统计公报》上获取，或通过相邻年份的统计数据进行插值补充。人民币兑美元汇率采用相应年份的年平均价，源于《中国统计年鉴》（2016）。各行界线、城市位置等获取自国家地理基础地理信息中心1:400万数据库和基于国家测绘地理信息局标准地图服务网站下载的审图号为GS(2016)2890号标准地图制作，底图无修改。

# 1.2 研究方法

1.2.1熵值—突变系统模型突变理论通过归一公式对评价目标进行综合量化运算，不需要对各指标赋予权重，同时兼顾考虑到指标的相对重要性，避免了主观性且不失科学性和合理性[15]。本文在利用熵值法对各控制变量重要性大小进行排序的基础上（外贸依存度 $>$ 外资依存度 $>$ 对外旅游开放度），构建熵值一突变系统模型，对各地级单元经济对外开放度进行综合测度。 $\mathrm { T H O M } ^ { [ 1 6 ] }$ 证明,当控制变量不超过4个，则势函数最多只有7种突变形式。一般应用较多且常见的突变系统类型主要包括尖点突变系统、燕尾突变系统、蝴蝶突变系统，篇幅所限，各系统的特点及计算公式详见文献[17]。本文主要采用了燕尾突变系统，计算式为：

$$
f ( x ) = \frac { 1 } { 5 } x ^ { 5 } + \frac { 1 } { 3 } a x ^ { 3 } + \frac { 1 } { 2 } b x ^ { 2 } + c x
$$

式中： $x$ 为势函数 $f ( x )$ 的状态变量； $\scriptstyle a , b , c , d$ 为该状态变量的控制变量，对应评价指标体系指标层中的子指标。

1.2.2探索性数据分析（ESDA） ESDA（Explora-torySpatialDataAnalysis）是一种较理想的“数据驱动”分析方法，以空间关联测度为核心，描述地理事物的空间集聚与区域差异[18-19]。本文首先采用全局Moran's $I$ 指数衡量分析要素在整个区域的空间特征，判断对外开放度的分布是否存在潜在的相互依赖性,计算式见文献[18]。其次,引入局域 Moran'sI(LISA)来反映区域与周边区域对外开放度差异的趋势,公式详见文献[19] 。

1.2.3三维插值拟合分析及重心迁移三维插值拟合分析是将离散点的测度数据转换为连续的数据曲面，以地理坐标为基准位置，通过三维技术进行可视化拟合，直观形象地反映描述对象在空间区域上变化的总体分异特征。重心即加权平均中心，通过赋予空间对象几何坐标以不同权重，计算属性值的平均中心并加以比较,分析对外开放度在空间方向上的差异性和均衡性。计算式详见文献[20-21] O

1.2.4空间变差函数空间变差函数又称为半变异函数（semi-variograms），文中用来描述对外开放度在区域上的变异性和结构性。计算式见参考文献[22]。半变异函数在理论上是未知,通常用球形模型、线性模型、指数模型、高斯模型等模型拟合半变异函数[23-24] O

# 2对外开放度时空分异特征及格局 演变

# 2.1 总体分异特征

2.1.1空间分异格局利用突变级数法的燕尾突变系统模型，计算出2005年和2015年中国343个地级单元的对外开放水平。以343个地级单元对外开放度得分的平均值为依据，将对外开放度得分按照 $\pm 1$ 标准差或者 $\pm 0 . 5$ 标准差为临界值分为5类，绘制空间分布图（图1）。结果表明，在所有测度单元中，2005年对外开放度高 $( 0 . 4 4 6 \sim 0 . 9 9 4 )$ 和较高（ $0 . 2 9 3 \sim 0 . 4 4 5 )$ 的单元共141个，占地级单元总数的 $4 1 . 1 \%$ ;对外开放度较低及以下 $( 0 . 0 6 1 \sim 0 . 2 1 5 )$ ！的单元共113个，占总数的 $3 2 . 9 \%$ ，其中，有38个单元的对外开放度极低 $( 0 . 0 6 1 \sim 0 . 1 3 9 )$ ，占单元总数的 $1 1 . 1 \%$ 。对外开放度最高的单元是珠海，其次是深圳、惠州和厦门；对外开放度最低的是七台河，其次是达州和平凉。2015年对外开度较高及以上（ $0 . 2 3 2 \sim 0 . 9 9 6 \$ )的单元共157个，占地级单元总数的 $4 5 . 8 \%$ ,较2005年增加 $4 . 7 \%$ ,其中珠海、东莞、上海综合得分最高；对外开度较低及以下 $( 0 . 0 4 3 \sim$ 0.178)的单元共109个，占总数的 $3 1 . 7 \%$ ,其中玉树州的综合得分最低，其次是临夏州和果洛州。

将343个单元按照行政级别属性分为直辖市、副省级城市及省会城市和地级市(表1)；按照地域区划属性分为东、中、西、东北四大区域①（表2)；按照我国对外开放的层次分为经济特区、沿海开放城市与沿江和内陆开放城市（表3）。发现其总体分异特征如下：(1)直辖市、副省级城市及省会城市普遍对外开放度较高，地级市间相对差异缩小。随着行政等级由高到低，整体对外开放水平呈递减趋势。直辖市、副省级城市及省会城市的对外开放水平都位于一般及以上区间，其中，深圳、厦门、北京、上海等城市对外开放度最高，兰州、西宁、贵阳等城市最低。在307个地级市中，2015年对外开放度较高及以上水平的城市有126个，约占总数的 $41 \%$ ，较2005年地级单元同水平对外开放程度的数量上升了 $5 . 9 \%$ ；一般及以下水平城市的数量较多，整体数量较前期缓慢下降。同时，地级市对外开放度变异系数呈下降趋势，地级市间相对差异逐渐缩小，一般及以下水平的地级市城市对外开放潜力较大，仍有提升空间。

![](images/af95b27ea5ecfaffd686bbb43a76afdfd60937fc29ca1b73a29c8ced8a799106.jpg)  
审图号GS(2016)2890号标准地图制作，底图无修改  
图12005—2015 年中国地级单元对外开放度分布  
Fig.1Distribution of prefecture-level cities with economic opening rate during 2Oo5—2015

(2）中部、西部稳步崛起，东部、东北地区提升幅度较小，地带性差异显著。2005—2015年间，中西部地区高对外开放水平的城市明显增多，由6个增加到14个，中部较其他3个地区提升更为显著;东部、东北地区提升幅度则较小，高水平单元有所减少，由46个下降至29个，珠三角地区及东南沿海是主要减少区域，说明对外开放由快速增长期逐步进入稳定发展期;较高水平单元增加，长三角地区是主要增加的区域，且与山东半岛连接形成我国较高水平对外开放城市的沿海集中分布带。

（3）经济特区、沿海开放城市呈现高水平开放态势，沿江和内陆开放城市稳中有进，差异显著。改革开放以来，我国对外开放基本形成“经济特区一沿海开放城市一沿江和内陆开放城市一沿边开放城市”宽领域、多层次、点线面结合的全方面对外开放格局。由于沿边开放城市多为县级市，数据资料缺失，暂未纳入分析。经济特区、沿海开放城市具有优良的地缘优势条件和较长时间的开放过程，整体对外开放水平较高，在两个时间截面上，经济特区、沿海开放的19个城市中有18个城市处于较高及以上水平；沿江和内陆开放城市作为我国对外开放由沿海向内陆延伸及海陆双向联动的重要节点城市，对外开放水平稳步提升，至2015年，高水平城市增加了4个，一般水平城市基本保持稳定，但不可忽视的是各类型城市变异系数均呈上升趋势，城市间对外开放度的差异显著。

2.1.2三维插值拟合分析及重心迁移特征通过Kriging插值生成3D拟合图（以对外开放度插值得分的标准差为依据，进行颜色分级的界定），直观地反映中国地级单元对外开放度的空间分布格局与变化趋势。可以发现，整体对外开放趋势受空间区域位置梯度引起的递减效应明显，反映出对外开放度东部 $>$ 中部 $>$ 西部，南方 $>$ 北方的趋势及分异格局。具体而言，2005年，主峰分布较独立，次主峰分布较稀疏，广大西部及西南部地区呈现低水平，域面广的特点。随着时间的推移，主峰数量明显增多，呈多核心、多增长极的发展趋势，东中部地区峰面坡度整体趋于低起伏，进一步说明该地区对外开放表现出一定的稳定性与均衡性。西部及东北依托沿边区位优势，对外开放水平逐步提升，形成环状包圈层结构，同时，2015年对外开放度的重心向西北方向迁移$4 0 . 7 ~ \mathrm { k m }$ ，西部地区正在成为新的对外开放经济活动的"桥头堡”。

Tab.1 Economic opening rate by administrative levels in China   
表2中国对外开放度的空间差异  

<html><body><table><tr><td></td><td colspan="6">2005 年对外开放水平</td><td colspan="6">2015 年对外开放水平</td></tr><tr><td></td><td>高</td><td>较高</td><td>一般</td><td>较低</td><td>低</td><td>变异系数</td><td>高</td><td>较高</td><td>一般</td><td>较低</td><td>低</td><td>变异系数</td></tr><tr><td>直辖市</td><td>3</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0.305 1</td><td>3</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0. 226 7</td></tr><tr><td>省会和副省级城市</td><td>13</td><td>16</td><td>3</td><td>0</td><td>0</td><td>0.362 5</td><td>12</td><td>15</td><td>5</td><td>0</td><td>0</td><td>0.298 2</td></tr><tr><td>地级市</td><td>36</td><td>72</td><td>87</td><td>74</td><td>38</td><td>0.514 8</td><td>29</td><td>97</td><td>72</td><td>68</td><td>41</td><td>0.447 6</td></tr><tr><td>全国</td><td>52</td><td>89</td><td>89</td><td>75</td><td>38</td><td>0.524 4</td><td>44</td><td>113</td><td>77</td><td>68</td><td>41</td><td>0.4603</td></tr></table></body></html>

Tab.2Economic opening rate by region in China   
表3对外开放格局组成部分的对外开放水平  

<html><body><table><tr><td rowspan="2"></td><td colspan="6">2005 年对外开放水平</td><td colspan="6">2015 年对外开放水平</td></tr><tr><td>高</td><td>较高</td><td>一般</td><td>较低</td><td>低</td><td>变异系数</td><td>高</td><td>较高</td><td>一般</td><td>较低</td><td>低</td><td>变异系数</td></tr><tr><td>东部地区</td><td>43</td><td>25</td><td>17</td><td>3</td><td>0</td><td>0.396 3</td><td>28</td><td>35</td><td>22</td><td>3</td><td>0</td><td>0.401 3</td></tr><tr><td>中部地区</td><td>3</td><td>28</td><td>34</td><td>21</td><td>1</td><td>0.295 7</td><td>7</td><td>37</td><td>26</td><td>16</td><td>1</td><td>0.277 1</td></tr><tr><td>西部地区</td><td>3</td><td>24</td><td>30</td><td>40</td><td>35</td><td>0.448 4</td><td>7</td><td>21</td><td>23</td><td>41</td><td>40</td><td>0.476 9</td></tr><tr><td>东北地区</td><td>3</td><td>12</td><td>8</td><td>11</td><td>2</td><td>0.4121</td><td>1</td><td>17</td><td>10</td><td>8</td><td>0</td><td>0.266 9</td></tr></table></body></html>

表1各类行政单元内的对外开放水平  
Tab.3 Component of economic opening rate in the structure of the level of opening up   

<html><body><table><tr><td rowspan="2"></td><td colspan="6">2005 年对外开放水平</td><td colspan="6">2015 年对外开放水平</td></tr><tr><td>高</td><td>较高</td><td>一般</td><td>较低</td><td>低</td><td>变异系数</td><td>高</td><td>较高</td><td>一般</td><td>较低</td><td>低</td><td>变异系数</td></tr><tr><td>经济特区</td><td>4</td><td>1</td><td>0</td><td>0</td><td>0</td><td>0.279 0</td><td>3</td><td>2</td><td>0</td><td>0</td><td>0</td><td>0.481 5</td></tr><tr><td>沿海开放城市</td><td>10</td><td>4</td><td>0</td><td>0</td><td>0</td><td>0.237 0</td><td>8</td><td>5</td><td>1</td><td>0</td><td>0</td><td>0.265 6</td></tr><tr><td>沿江、内陆开放城市</td><td>2</td><td>16</td><td>4</td><td>0</td><td>0</td><td>0.1788</td><td>6</td><td>10</td><td>6</td><td>0</td><td>0</td><td>0.2260</td></tr></table></body></html>

![](images/d4eb25ab0a16501c3d5f46ff4a802b584d71ebfff876e4a74e9cae962cd29d1d.jpg)  
图22005—2015年中国地级单元对外开放度3D拟合图 Fig.23D fitting figure of economic opening rate during 2Oo5—2015

# 2.2对外开放度的空间格局及演化机理

2.2.1空间自相关与空间格局纹理利用GeoDa软件，计算得到2005年及2015年对外开放度全局Moran's $I$ 分别为0.586和0.482，表明中国地级单元的对外开放存在明显的空间自相关特征。进一步计算各地级单元的局域空间自相关指数LISA（图3)。在 $5 \%$ 的显著水平下，将空间格局纹理分为：$\textcircled{1}$ 外向型，对应局域自相关中的(HH)，表示该地区与周围相邻地区对外开放度值都高； $\textcircled{2}$ 高原型（HL)，表示该地区比周围地区的值高； $\textcircled{3}$ 洼地型(LH)，表示该地区值较低，而相邻地区值较高; $\textcircled{4}$ 闭塞型(LL)表示该地区与周围相邻地区值都较低。由图3可以看出：

（1）对外开放度在两个时间截面上空间整体呈现外向型（HH)和闭塞型（LL）“小分散大集聚”的俱乐部特征，高原型(HL)和洼地型(LH)聚集区数量较少。外向型聚集区域主要集中分布在珠三角、长三角、山东半岛、京津冀及辽东半岛，这些地区都拥有优良的区位条件，对外开放发育历程久、程度高，技术的扩散和投资引力的空间溢出效应明显。

![](images/ed544c43302e7fa5cd93091493892ac1c5116dc7b7e9e2f56e0cc8c93e77cf33.jpg)  
图32005—2015年中国地级单元对外开放度空间关联及纹理类型  
Fig.3Spatial interaction clustering and texture of economic opening rate during 2Oo5—2015

闭塞型聚集区域主要集中分布在西部、西南内陆腹地及东北零星地区，这些地区大多经济发展薄弱，基础设施建设较落后，技术创新能力较弱，吸引投资空间狭小，与周边城市对外开放水平低值区域形成闭塞型的相关模式。高原型区域被分割成不连续的碎片分布在闭塞型周围，主要为沿边城市及西部部分直辖市及省会城市，凭借沿边区位优势条件及主导社会资源空间流动及分配的优势，在“虹吸作用”影响下，对外开放水平相对周边区域较高，其空间分布也就更为破碎。洼地型区域零散位于开放性型区域附近，2005年为广西贺州市，可能由于本地对外开放的潜能不足且周边城市竞争力强，弱化了自身发展潜能，形成中心低四周高的洼地型关联模式。

（2）对外开放总体格局保持相对稳定，外向型和闭塞型聚集区变化较明显。从各类型纹理的统计数量来看，2005年外向型（58） $>$ 闭塞型（49） $>$ 高原型（3） $>$ 洼地型（1）；2015年则为外向型 $( 5 3 ) >$ 闭塞型（52) $>$ 高原型 $( 4 ) >$ 洼地型(0），数量上整体变化趋势不显著。2005—2015 年，空间格局纹理未发生变化的地级单元有80个，占总数量的 $5 7 . 5 5 \%$ ，其中开放型占 $5 1 . 2 5 \%$ ,闭塞性占 $4 7 . 5 \%$ ；空间格局纹理发生变化的地级单元同样主要集中在外向型和闭塞型，开放型在东南沿海地区趋于缩小和离散，在长三角地区趋于扩大和集聚，这一特点反映出长江经济带作为中国新一轮改革开放转型实施的新区域,有着较强的综合实力及发展潜力；闭塞型由西南地区转移向青陕甘宁集中分布，成都、重庆、昆明市等西部直辖市及省会城市转变为高原型城市。

2.2.2格局演化空间机理“格局一过程—机理”是地理学研究地理现象与规律的基本范式[25]。本文利用空间变差函数来探究对外开放格局演化的空间机理。首先通过SPSS软件对两年的对外开放度数据进行正态分布检验，结果呈偏正态分布，因此需要将样本数据进行对数转换，使其呈近似正态分布。设定步长为 $1 9 0 ~ \mathrm { k m }$ ，步长数为10，确保步长和步长数的乘积约等于城市间最大距离的一半[26],分别计算变差函数，选择球状模型、高斯模型、指数模型和线性模型进行拟合，选择拟合度最高的模型，并计算各方向分维数，结果如表4和表5所示。

从块金值、基台值、块金系数3个参数的变化情况来看，参数整体均减小，说明随着时间的推移，中国对外开放度的空间差异程度在逐渐减小，对外开放度格局受不确定因素影响在减小，由空间自相关引起的结构化分异日益显著;两个时间截面的块金系数均小于0.25，印证了中国对外开放度存在着空间的集聚性，结构化空间梯度引起空间关联效应的作用范围有所增强，具体表现从东部沿海地区向中西部地区转移。利用最小二乘法拟合的空间变差模型均为球状模型，且拟合度系数较高，这说明在不同发展时期，中国对外开放的空间自组织性和连续性都较强。

# 表4中国地级单元对外开放格局变差函数拟合参数

Tab.4Parameters of variogram function on spatial pattern inprefecture-level cities   

<html><body><table><tr><td>年份</td><td>块金值</td><td>基台值</td><td>块金 系数</td><td>变程</td><td>拟合 模型</td><td>决定系数 (R²）</td></tr><tr><td>2005</td><td>0.058</td><td>0.313</td><td>0.185</td><td>1598</td><td>Spherical</td><td>0.976</td></tr><tr><td>2015</td><td>0.044</td><td>0.279</td><td>0.157</td><td>1690</td><td>Spherical</td><td>0.934</td></tr></table></body></html>

全方向分维数值略有下降，表明对外开放度在全方向上空间分布结构的均衡性有降低趋势；从各方向的分维数值来看，东北一西南方向分维数值最高，且拟合系数较高，说明在东北一西南方向对外开放度的均质性较好，空间差异程度较小;东南一西北向分维数较低，对外开放度在该方向上呈现出非均质态势，“东强西弱”的格局表明新时期须实现沿海与内地的开放平衡。

# 3 结论与讨论

# 3.1结论

本文的主要研究结论如下：

（1)时空分异格局特征方面，中国对外开放度表现出明显的行政指向性和空间地带性双重分异。直辖市、副省级城市及省会城市整体对外开放水平较高，形成宽领域、“多极”化的对外开放格局；对外开放度空间分异地带性显著，整体呈现东部 $>$ 中部$>$ 东北 $>$ 西部，南方 $>$ 北方的趋势；对外开放度高值区和低值区形成一定范围的连绵区，随着时间的推移，高值由东南及沿海核心地区向中部、西部城市辐射，对外开放度重心迁移主要向西北方向移动，沿国界边境城市对外开放水平有所上升；各单元对外开放的总体差异程度逐渐减小。

表5中国地级单元对外开放格局变差函数分维数  
Tab.5Fractal of variogram function on spatial pattern in prefecture-level citie:   

<html><body><table><tr><td rowspan="2">年份</td><td colspan="2">全方向</td><td colspan="2">南一北</td><td colspan="2">东北一西南</td><td colspan="2">东一西</td><td colspan="2">东南一西北</td></tr><tr><td>D</td><td>R²</td><td>D</td><td>R²</td><td>D</td><td>R</td><td>D</td><td>R²</td><td>D</td><td>R²</td></tr><tr><td>2005</td><td>1.769</td><td>0.947</td><td>1. 789</td><td>0.946</td><td>1.837</td><td>0.978</td><td>1.743</td><td>0.913</td><td>1.688</td><td>0.922</td></tr><tr><td>2015</td><td>1.756</td><td>0.919</td><td>1.837</td><td>0.895</td><td>1.834</td><td>0.916</td><td>1.703</td><td>0.904</td><td>1.625</td><td>0.899</td></tr></table></body></html>

（2）从空间格局演变趋势看，中国对外开放度存在明显的空间依赖性和“俱乐部”趋同特征。开放型和闭塞型空间纹理表现出显著的局域空间集聚特征，随时间的推移，对外开放总体格局保持相对稳定，外向型和闭塞型聚集区变化较明显，开放型纹理分散程度趋于提升，闭塞型纹理集聚程度趋于收敛，高原型整体呈破碎化分布。

(3）在空间机理上，中国对外开放度格局变异的随机成分在逐渐减小，对外开放度空间关联效应的作用范围有所增强，空间自组织性和连续性较为显著；从各方发展趋势看，不同方向上具有不同的结构特征，东北一西南方向均质性最好，东南一西北方向空间差异明显。

# 3.2讨论

对外开放度作为区域经济与世界经济融合研究的指示器，对其不同时空尺度和格局与过程的研究均有参考价值，对于对外政策的制定及区域外向型经济与区域经济双轨融合发展也有一定的启示意义。同已有研究对比，本文通过构建熵值一突变系统模型，较为客观、系统地对对外开放度进行综合测度，是一次新的尝试,避免了指标权重算法的主观性。地级单元是区域经济发展的组织者、引导者、调控者，具有很强的代表性，而目前鲜有对于地级市对外开放度的研究。如何科学地评价地级单元对外开放度，如何分析地级单元时空视角下对外开放的格局的差异及演化及机理，是本文解答的关键问题。部分学者[7-10]对省域对外开放度时空格局进行评价分析，在宏观空间格局分异上所得结论与本文结论基本相同，但由于空间尺度和时间尺度的不同，所揭示地域的时空变异特征有所不同。地级及以上城市对外开放度存在较强空间关联的事实，提示我们在制定和实施区域对外开放政策的时候，须创新顶层设计，制定共性化区域对外开放统筹发展战略，降低区域合作的制度性壁垒，实现对外开放一体化包容发展。同时，各单元开放度差异巨大的事实，也要求政府在具体实践中，实施差别化的对策措施，促进区域间对外开放水平的协调发展。

由于统计数据获取所限，文中选取的评价指标较为有限，有待进一步完善。对外开放格局的特征及演变是一个非常复杂的系统工程,时效性很强，区域差异的影响因素多元，驱动机制复杂，因此，时空分异的驱动机制及其量化分析将是下一步研究的重点。

# 参考文献(References)

[1]BALASSA B. Exports,policy choices,and economic growth in developing countries after the 1973 oil shock[J].Journal of Development Economics,1985,18(1）:23-35.   
[2]HOEFFLER A. Openness,investment and growth[J]. Journal of African Economies,2001,10(4）:470 -497.   
[3]CUADROS A,ORTS V,ALGUACIL M. Openness and growth : Reexamining foreign direct investment,trade and output linkages in Latin America[J]. The Journal of Development Studies,2004,40 (4):167 -192.   
[4]World economic forum and international management development.The world competitiveness report[R].Lausanne: Institute for Management Development,1994.   
[5］王鹏.广东省经济开放度与经济增长关系的实证研究［J].国 际经贸探索,2007,23（5）:33-38.[WANG Peng.Research on the long-term equilibrium and short-term fluctuation between economic openness and economic growth in Guangdong Province[J]. International Economics and Trade Research,2007,23（5） :33- 38.]   
[6］徐冉.对外开放度与经济增长关系研究——以河南省为例 [J].地域研究与开发,2012,31(1）:35-39.[XURan.A study on the correlation between the degree of opening up and economic growth:A case study of Henan Province[J].Areal Research and Development,2012,31（1） :35-39.]   
[7］谢守红.中国各省区对外开放度比较研究[J].地理科学进展, 2003,22(3）:296-303.[XIE Shouhong.Measurement and comparison of economic opening rate of all provinces of China[J].Progess in Geography,2003,22(3）:296 -303.]   
[8］陈辉,牛叔文.经济开放度评价及对策研究—以甘肃为例 [J].经济问题,2010,（6）:121-124.[CHEN Hui,NIU Shuwen. Study on the economic opening and countermeasures in Gansu Province[J].On Economic Problems,2010,（6）:121-124.]   
[9]赵曦,刘耀林,乔慧,等.湖北省经济对外开放度研究[J].地域 研究与开发,2005,24（3）:24-27.[ZHAO Xi,LIU Yaolin, QIAO Hui,et al. Study on economic opening rate of Hubei Province[J].Areal Research and Development,2005,24（3）:24 - 27.]

[10］郑展鹏.中部六省对外开放度的实证研究：2000—2007[J].国际贸易问题,2009，（12）：70-74.[ZHENGZhanpeng.Empiricalstudy on opening of six central provinces:Dased on data of 2000—2007[J].Journal of International Trade,2009,（12）:70 -74.][11］马章良.长江三角洲两省一市对外开放度的实证研究：2000—2009[J].国际商务：对外经济贸易大学学报，2010，（5）：49-53.[MA Zhangliang.An empirical study on Yangtze Delta's open-ingpolicy:2000—2009[J].International Business,2010,（5）:49-53.]

[12］罗汉，艾燕琳,毛锦云.经济开放度与地区经济发展的相关分析[J].湖南大学学报（社会科学版），2004，18（3）：59－62.[LUOHan,AIYanlin,MAOJinyun.Analysison therelationsbe-tween the degree of economic openness and regional economic de-velopment[J].Journal of Hunan University（Social Sciences），2004,18(3):59 -62.]

[13］陈威,潘润秋，王心怡.中国省域对外开放度时空格局演化与 驱动机制[J].地理与地理信息科学，2016,32（3)：53-60. [CHENWei,PAN Runqiu,WANG Xinyi.Spatial-temporal evolution and its driving mechanism of economic opening rate of provinces in China[J].Geography and Geo-Information Science,2016, 32(3):53-60.]

[14］徐冉.基于VAR的对外开放度与经济增长关系研究——以中国中部地区为例[J].地域研究与开发，2014,33（3）：16－20.[XU Ran.Study on the correlation between the degree of openingup and economic growth of central region［J].Areal Research andDevelopment,2014,33（3）:16-20.]

[15］件凤清，李建侠.基于突变级数法的企业自主创新能力评价及提升路径研究[J].科学学与科学技术管理，2010，31（11）：33-39.［WU Fengqing,LI Jianxia.The study of improving path andevaluation of enterprises‘independent innovation capacity based oncatastrophe progression method[J].Science of Science and Management of S.&T,2010,31（11):33-39.]

[16］赵宏波，马延吉，苗长虹.基于熵值一突变级数法的国家战略 经济区环境承载力综合评价及障碍因子一—以长吉图开发开 放先导区为例[J].地理科学，2015，35（12）：1525-1532. [ZHAO Hongbo,MA Yanji,MIAO Changhong.Integrated assessment and obstacle factors of environmental carrying capacity of national strategic economic zones based on entropy and catastrophe progression methods:A case study in Changchun-Jilin-Tumenjiang development and opening-up pilot area[J].Scientia Geographica Sinica,2015,35(12):1525-1532.]

[17］解佳龙，胡树华,蒋园园.基于突变级数法的国家高新区竞争力空间分异研究[J].科学学与科学技术管理,2011,32（12）：101-1O8.[XIEJialong,HU Shuhua,JIANG Yuanyuan.Researchon the competitiveness spatial differentiation of National Hi-TechZones based on catastrophe progression method[J].Science of Sci-ence and Management of S.& T,2011,32（12）:101-108.][18」潘竟虎.中国地级及以上城市城乡收入差距时空分异格局[J].经济地理,2014,34（6）:60-67.[PANJinghu.Spatiotem-poral pattern of urban-rural income gap of prefecture level cities orabove in China[J].Economic Geography,2014,34(6）:60 -67.][19］潘竟虎，张佳龙，张勇.甘肃省区域经济空间差异的ESDA-GIS分析[J].西北师范大学学报（自然科学版），2006，42（6）：83-87.［PAN Jinghu,ZHANG Jialong,ZHANG Yong.Analysis ofregional economic disparities in Gansu Province based on ESDAand GIS[J].Journal of Northwest Normal University(Natural Sci-ence）,2006,42(6) :83-87.]

[20］叶明确.1978—2008 年中国经济重心迁移的特征与影响因素[J].经济地理,2012,32（4）：12-18.[YEMingque.Character-istics and influence factors analysis of gravity movement for China's economy from 1978 to 2008[J].Economic Geography,2012,32(4) :12 -18.]

[21］刘晓婷，陈闻君.基于ESDA-GIS 的新疆能源碳排放空间差异 动态演化分析[J].干旱区地理，2016,39（3）：678-685.［LIU Xiaoting,CHENWenjun.Dynamic evolution of spatial disparity of energy carbon emissions in Xinjiang based on ESDA-GIS[J].Arid Land Geography,2016,39(3）:678 -685.]

[22］潘竞虎，胡艳兴，董晓峰.丝绸之路经济带经济差异时空格局演变特征［J].经济地理,2016,36（1）：10-17.［PANJinghu，HUYanxing,DONG Xiaofeng. Spatial-temporal evolution of eco-nomic disparity for the Silk Road Economic Zone[J].EconomicGeography,2016,36(1) :10-17.]

[23］尹鹏，李诚固.环渤海"C型"经济区经济格局的空间演变研究 [J].地理科学,2015,35（5）:537-543.[YINPeng,LI Cheng gu.Spatial evolution of economic pattern in"C-typed"economic region along the Bohai Rim［J].Scientia Geographica Sinica,2015, 35(5) :537 -543.]

[24］靳诚，陆玉麒.基于空间变差函数的长江三角洲经济发展差异演变研究［J].地理科学，2011，31（11）：1329-1334.［JINCheng,LU Yuqi.Evolvement of economic development diversity inthe Changjiang River Delta based on spatial variogram[J].ScientiaGeographica Sinica,2011,31（11）:1329-1334.]

[25］张荣天，张小林,李传武.基于县域尺度的江苏省乡村性空间格局演变及其机理研究［J].人文地理,2013，（2）：91-97.[ZHANGRongtian,ZHANGXiaolin,LI Chuanwu.Spatio-temporalchanges of population distribution at sub-district level in JiangsuProvince[J].Human Geography,2013,(2）:91-97.]

[26]申玉铭，邱灵，王茂军,等.中国生产性服务业产业关联效应分 析[J].地理学报,2007,62(8）:821-830.[SHEN Yuming,QIU Ling,WANGMaojun,etal.Industryrelevancy analysisof producer servicesin China[J].Acta Geographica Sinica,20O7,62(8）:821 -830.]

# Spatio-temporal pattern of economic opening rate at prefecture level cities or above in China

ZHANG Yong-nian， PAN Jing-hu (College of Geographicand Environmental Science,NorthwestNormal University,Lanzhou73oo7,Gansu,China)

Abstract：Opening to the outside world isone of the fundamental national policies in China.Since theenact of thereform and opening policy,China has gradualy formed the comprehensive,multi-level,and wide-ranging opening structure to the outside world,which has brought tremendousand impresiveachievements.Since 1978,China has atracted more than1.7trilion USdollarsofforeign investment,and hasreached thecumulativedirectforeign investment of more than1.2 trilion US dollars,which contribute greatly to the development of global economies.In this paper,byanalyzing the economic data from the 343 Chinese administrative region cities of the prefecture-level and theabove,the entropy-mutation model was established based onthe dependence-level of the economic-openingdegree on the foreign trade,investment,tourismandother indicators,leading tothe comprehensive assessmenton the opening degree of these cities.Through the methodsof ESDA,three-dimensional interpolation fiting analyses,barycenter shifting,and space transform function,this paper discussed the overalltrendsof economic-opening-degreeof these aforementioned cities,and the evolutionary characteristics and mechanism of its spatial patern during 2005- 2015 from the perspective of space-time coupling.The results showed as follows:（1）the Chinese economic-opening-degre obviously showed multiple characteristics directed by administration,spatial zone,and regional-opening. Municipalities,sub-provincial citiesand capital cities hadhigh economic-opening-degree to theoutside world.Marginal differences were observed among these prefecture-level cities.The economic-opening-degree decreased from the Eastto the Central,Northeast and the West China respectively.The South China had a higher opening degree than the North.Special economic zones and coastal opening cities showed a high level of opening.Meanwhile,riveralong and inland opening cities steadily increased their opening degree but have significant diffrence.（2）The opening degree was significantly related with spatial zonesand showed theclubcharacteristics of the small cities of scatering and the large citiesof gathering.From 2O05 to 2O15,theeconomic opening maintained arelatively overall stable status with the opening degree improving,closing degree declining,and the overall degree of plateau type distributing sparsely.(（3）The random change of China’s economic opening degree structure is gradually vanishing. The spatial self-organization and continuity of opening degree's structure were more significant.Beter homogeneous structure of the opening degree was observed in the Northeast over the Southwest. Clear spatial differences between the Southeast and the Northwest were showed.As the representatives of regional economic development,the prefecture-level cities areorganizers,directors,ndcontrolers.Through theresearchof economic-opening-degreeof these cities,this paper could provide scientific advises for the government to make reasonable opening strategies to the outside world and promote regional harmony-development in the new economic situation.

Key words:opening rate；catastrophe progresion method；ESDA-GIS；spatial-temporal differentiation； China