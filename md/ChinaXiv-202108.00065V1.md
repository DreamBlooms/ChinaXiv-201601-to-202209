# 基于FLUS模型的汾河流域生态空间多情景模拟预测

苏迎庆¹，刘庚¹，赵景波²，牛俊杰'，张恩月¹，郭利刚³，林菲¹（1.太原师范学院汾河流域科学发展研究中心,山西 晋中030619；2.陕西师范大学地理科学与旅游学院，陕西西安710119；3.太原师范学院管理系，山西 晋中030619)

摘要：选取汾河流域为研究区,基于2015年、2018年土地利用类型数据，并采用EES模型筛选了对应基准年的20项驱动因子数据，利用FLUS模型,在验证模型精度有效性的基础上，模拟预测了2024年、2030年生产空间优先、生活空间优先、生态空间优先以及三生空间协调4种情景下汾河流域生态空间的时空演化特征及成因。结果表明：(1）2018—2030年汾河流域生态空间呈现两类演变趋势,在生态空间优先、三生空间协调情景下呈现线性增长，分别增长 $5 . 9 2 \% . 5 . 1 3 \%$ ;生产空间优先、生活空间优先情景下呈现线性下降，分别下降 $9 . 4 0 \% . 2 . 2 0 \%$ ;生产、生活、生态空间用地结构比例维持4:1:5。（2）时空格局上,生态空间位于流域边缘山区,生产、生活空间位于核心盆地，生态、生产、生活空间整体呈现依次嵌套的格局特征;生态空间核心区变化幅度较小,边缘区变化显著。（3）2024年、2030年三生空间协调情景、生态空间优先情景下生态空间的演变趋势近似,受流域自然-社会发展趋势及国家政策影响，未来可利用后备土地资源有限,流域生态空间变化较小但也存在胁迫隐患。基于此，本文建议严格遵循"三线”（永久基本农田保护红线、生态保护红线、城镇开发边界线)基本原则，合理规划三生空间后备土地资源,对生态空间边缘区(生态敏感区)积极治理保育，核心区限制开发，促进流域科学发展。

关键词：生态空间；多情景模拟；FLUS模型；汾河流域；山西

土地是人地耦合系统的核心载体，并以不同功能的土地空间状态为人类社会提供各类产品与服务[1]。为促进土地空间功能的合理开发与利用，解决长期以来社会经济发展负效应下国土空间功能冲突，生态系统退化等问题2]，国家提出三生空间功能规划，强调构建“生产空间集约高效，生活空间宜居适度，生态空间山清水秀"的"三生空间”[3]。其中，生态空间是指具有自然属性，以提供生态服务或生态产品为主体功能的国土空间，以其保持与调整生态系统协调的功能成为解决人地关系问题的核心要素[4]。目前,生态空间研究仍处于探索阶段[5],生态空间基础理论与核心概念的界定主要基于生态要素、生态功能以及土地利用或空间主体功能3种视角，现有研究涉及生态空间现状分析，关键性生态空间的分类、识别及区域生态空间的划定等方面[7-8],研究尺度以行政单元(省域/县域/村域)[9-I]重点流域[12-13]及生态敏感脆弱区[14-15]（山区/喀斯特地区)为主，研究方法已从定性分析的清单法逐渐向定量分析的叠置分析法过渡[1]。近年来生态空间理论与应用研究进展较快，为进一步研究奠定了基础。由于生态空间的演变是三生空间之间以及生态空间内部诸要素间的各用地类型的动态演变[17],并具有时空异质性及多维性特征,导致未来生态空间的演变存在很大不确定性，基于生态空间的现状分析不能充分反映生态空间演化机制，而通过多情景模式下生态空间的预测能为生态空间现状评价提供补充与证明，从长时序尺度揭示生态空间演化的完整规律。因此，进行多情景生态空间的模拟预测研究具有迫切性与必要性。

汾河流域是黄河流域的第二大流域单元，也是山西省人口经济高度集聚区，其占有全省 $2 6 \%$ 的水资源却承载着全省约 $4 0 . 1 \%$ 的人口， $4 6 \%$ 工业产值及 $6 4 \%$ 农业产值的生产生活用水[8],多年来流域内地下水超采、煤炭资源过度开发及土地资源的高强度利用，造成流域水土流失、生态环境恶化等生态空间胁迫问题[19],限制了流域社会经济的可持续发展。为探明流域生态空间问题的发生原理，有效识别汾河流域生态空间脆弱区及生态修复重点区，揭示流域生态空间演化规律，亟需开展流域多情景模拟研究，而预测的实现取决于模型的应用。近年来新兴混合模型FLUS(FutureLandUseSimulation)集成了多个传统模型的优势[20-21],既简化了SD模型系统机制的构建程序，又克服了CA模型模拟非线性系统时的局限，还弥补了Markov模型、GM模型不能兼容驱动因子的问题[22]。尤其在反馈人地耦合系统多要素驱动因子相互作用机制及不同地类转化的复杂原理，提供较高模拟精度的空间用地变化结果方面效果显著[23-25]。因此,本文采用FLUS模型，以2015年、2018年汾河流域土地利用数据为源，在验证模型精度的基础上模拟流域未来土地利用，其中，依据2016年山西省人民政府发布的《汾河流域生态修复规划(2015—2030年)》，选取该规划远期建设阶段2024年与完成阶段2030年为关键预测节点，对流域生态空间进行阶段性多情景模拟预测，以期实现对生态空间的科学布局，为流域三生空间的协调可持续发展提供借鉴与指导。

# 1研究区概况及研究方法

# 1.1 研究区概况

汾河流域（ $3 5 ^ { \circ } 2 2 ^ { \prime } 6 ^ { \prime \prime } { \sim } 3 8 ^ { \circ } 4 9 ^ { \prime } 2 4 ^ { \prime \prime } \mathrm { N } , 1 1 0 ^ { \circ } 3 0 ^ { \prime } 3 ^ { \prime \prime } { \sim }$ $1 1 2 ^ { \circ } 5 0 ^ { \prime } 2 4 ^ { \prime \prime } \mathrm { E }$ )位于山西省中部，黄土高原东翼，地势自北向南倾斜，海拔高度介于 $2 4 0 { \sim } 2 7 8 6 \mathrm { ~ m }$ ，地貌以盆地、平川、丘陵为主，且由地堑型纵谷串联太原、临汾等盆地构成(图1)。汾河发源宁武县管涔山，于万荣县注入黄河，全长约 $7 1 3 \ \mathrm { k m }$ ,属温带大陆性季风气候,年均气温 $1 1 ~ \mathrm { { ^ { \circ } C } }$ ,年均降水量 $3 9 2 . 8 ~ \mathrm { m m }$ 。土壤类型含潮土、褐土、棕壤、粗骨土、红黏土等，以褐土为主，流域总面积约 $3 . 9 5 \times 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ ,涉及忻州、太原、晋中、吕梁、运城、临汾6市40县/区，集中全省约$4 0 . 1 \%$ 的人口， $4 2 . 6 \%$ 的GDP，城镇化水平达 $6 0 . 3 \%$ 。

# 1.2数据来源及处理

数据主要包括山西省行政区划，土地利用等基础数据及驱动因子数据(表1)。考虑土地利用变化与环境社会经济密切相关，引人EES(ecological-eco-

山西省宁武县 NA静乐县岚县@阳曲县娄烦县古交市太原市区 寿阳县交城县 榆次区清县孝义市 平遥县@ 介休市交口县汾西县石县 @ 县河 霍州市 汾河洪澜县古县 公路尧都区 铁路襄汾县 浮山县 海拔/m稷山县新绛县 翼城县 2786河津市 侯马市 绛县万荣县 1 2400 100 kmL

nomic-social)概念模型，该模型是包括环境、经济、社会的综合型体系，能有效反馈研究区经济社会与环境系统交互机制[26]，以此筛选20项驱动因子，所有数据经空间栅格化后并采取均匀采样法按 $1  { \mathrm { k m } } \times$ $1 \mathrm { k m }$ 归一化处理。

# 1.3 研究方法

FLUS模型是基于传统元胞自动机(CA)模型改良的集成模型，其原理是通过融合人工神经网络(BP-ANN)算法，对设定研究区的基准期土地利用数据及驱动因子计算可得到各类用地转化的适宜性概率；再结合模型中集成的自适应惯性竞争机制(邻域影响因子、惯性系数和转换成本)测算未来土地利用变化结果的综合概率；最后，利用轮盘赌机制得到模拟结果[27-28]

1.3.1流域用地需求规模预测为提高模拟精度且克服Markov模型在长时序尺度上模拟可能存在的误差[4],本文以3a为时间间隔,依次模拟各用地类型的需求规模，选取2015年、2018年2期用地数据调试参数检验模型精度，并预测间隔年用地状况及生态空间演变趋势，公式如下：

$$
\boldsymbol { S } _ { t + 1 } = \boldsymbol { P } _ { i j } \times \boldsymbol { S } _ { t }
$$

式中： $S _ { t }$ 和 $S _ { t + 1 }$ 分别表示 $\mathbf { \Phi } _ { t }$ 时刻和 $_ { t + 1 }$ 时刻土地的状态， $\mathbf { \Phi } _ { t }$ 为年; $P _ { i j }$ 是状态转移概率矩阵，表示 $i$ 用地类型转移为 $j$ 用地类型的概率。

# 表1数据类型及来源

Tab.1 Data type and source   

<html><body><table><tr><td colspan="2">数据类型</td><td>指标</td><td>数据来源</td></tr><tr><td>基础数据</td><td>行政边界</td><td>山西省行政边界</td><td>2015年中国科学院资源环境科学数据中心(http://www.resdc.cn)</td></tr><tr><td></td><td>土地利用</td><td>山西省土地利用数据</td><td>2015年、2018年中国科学院资源环境科学数据中心 (http://www.resdc.cn)(Landsat TM/ETM30 m)</td></tr><tr><td>EES驱动因子</td><td>经济因子</td><td>经济密度/(10元·km-2)</td><td>2015年、2018年《山西省统计年鉴》</td></tr><tr><td></td><td></td><td>GDP增长率/% 环保投资占GDP比例/%</td><td></td></tr><tr><td></td><td>环境因子</td><td>高程/m</td><td>中国科学院资源环境科学数据中心(http://www.resdc.cn)</td></tr><tr><td></td><td></td><td>坡度/()</td><td>2000年山西省DEM30m(SRTM30m)</td></tr><tr><td></td><td></td><td>距河流/m</td><td></td></tr><tr><td></td><td></td><td>人均水资源量/(人·m-3)</td><td>2015年、2018年《山西省水资源公报》</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>土壤养分有效性"</td><td>Har monized World Soil Database v 1.2(http://webarchive.iiasa.ac.at/Research)</td></tr><tr><td></td><td></td><td>土壤根系氧利用率*</td><td>2008年</td></tr><tr><td></td><td></td><td>土壤过盐量"</td><td></td></tr><tr><td></td><td></td><td>土壤毒性"</td><td></td></tr><tr><td></td><td></td><td>土壤可利用度"</td><td></td></tr><tr><td></td><td></td><td>年均降水/mm</td><td>WorldClim version 2.0(http://www.worldclim.org/)2000年</td></tr><tr><td></td><td></td><td>年均气温/C</td><td></td></tr><tr><td></td><td></td><td>水土协调度/%</td><td>2015年、2018年《山西省统计年鉴》《山西省水资源公报》</td></tr><tr><td></td><td>社会因子</td><td>人口自然增长率/%0</td><td>2015年、2018年《山西省统计年鉴》</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>人口密度/(人·km-)</td><td></td></tr><tr><td></td><td></td><td>城市化率/%</td><td></td></tr><tr><td></td><td></td><td>距主要交通干线/m</td><td>国家基础地理信息中心(www.ngcc.cn/ngcc/)</td></tr><tr><td></td><td></td><td>距主要居民点/m</td><td>2015年1:1000000中国基础地理信息数据</td></tr></table></body></html>

注：\*为无量纲指标。

# 1.3.2流域生态空间预测

(1)适宜性概率计算

BP-ANN人工神经网络算法由输人层、隐藏层和输出层神经元网络组成，可拟合基准期土地利用类型与多项空间驱动因子的对应关系，并通过元胞转换得到各土地利用类型的适宜性概率[29],公式如下：

$$
P _ { p , k } ^ { t } = \sum _ { j } w _ { j k } \times S N _ { j } \big ( p , q \big )
$$

式中： $P _ { p , k } ^ { t }$ 为元胞 $p$ 在 $\mathbf { \Phi } _ { t }$ 时刻转换为 $k$ 类用地的适宜性概率， $\mathbf { \chi } _ { t }$ 为年； $w _ { j k }$ 为隐藏层与输出层的权重，$\displaystyle S N _ { j } \big ( p , q \big ) = \frac { 1 } { 1 + \mathrm { e } ^ { - N _ { j } \left( p , q \right) } }$ 表示输出层与隐藏层的函数对应关系;其中, $N _ { j } ( p , q ) = \sum _ { i } w _ { i j } \times x _ { i } ( p , q )$ 表示隐藏层神经元j接收输入层信号； $x _ { i } ( p , q )$ 为第 $i$ 个神经元在迭代次数为 $q$ 时元胞 $p$ 的输入值; $w _ { i j }$ 为输入层与隐藏层的权重。

# (2）邻域因子计算

邻域因子表示不同土地利用类型间及邻域范围

内不同土地利用单元间的相互作用[30],公式如下：

$$
\Omega _ { p , k } ^ { t } = \frac { \sum _ { \boldsymbol { N } \times \boldsymbol { N } } \mathrm { c o n } \left( \boldsymbol { c } _ { p } ^ { t - 1 } = k \right) } { \boldsymbol { N } \times \boldsymbol { N } - 1 } \times \boldsymbol { w } _ { k }
$$

式中： $\Omega _ { p , k } ^ { t }$ 为元胞 $p$ 在 $\mathbf { \chi } _ { t }$ 时刻的邻域影响因子;$\sum _ { N \times N } \mathrm { c o n } \Big ( c _ { p } ^ { t - 1 } = k \Big )$ 表示用地类型 $k$ 在最后一次迭代$_ { t - 1 }$ 时，在 $N { \times } N$ 的Moore邻域窗口中所占有的元胞总数量，本文 $N { = } 3 ; w _ { k }$ 表示各类用地类型的邻域因子参数。其中，邻域因子参数介于[0,1」，用地扩展能力与领域因子呈正比；根据国家标准《土地利用现状分类》（GB/T21010-2017），用地类型分为建设用地（包括城乡、工矿及居民用地）未利用土地、水域、草地、耕地、林地。按人为干扰程度影响，各类用地领域因子参数4如表2。

（3）自适应惯性系数计算

自适应惯性系数可反映预期需求与实际数量的用地类型间的差异，并在迭代过程中进行自适应调整，使各用地类型的数量向着预定目标发展，从而实现空间用地类型变化的模拟[31],公式如下：

# 表2邻域因子参数

Tab.2 Neighborhood factorparameters   

<html><body><table><tr><td>土地利用类型</td><td>建设用地</td><td>未利用土地</td><td>水域</td><td>草地</td><td>耕地</td><td>林地</td></tr><tr><td>领域因子参数/wk</td><td>1</td><td>0.5</td><td>0.4</td><td>0.3</td><td>0.2</td><td>0.01</td></tr></table></body></html>

式中： $I _ { k } ^ { t }$ 为用地类型 $k$ 在迭代时间 $\mathbf { \chi } _ { t }$ 时的惯性系数;  
$D _ { k } ^ { t - 1 }$ 表示 $_ { t - 1 }$ 时用地需求和实际数量的面积差。

# （4）情景设置及转换成本

转换成本是指用地类型转换为需求类型的困难度，以矩阵表示，其值介于[0，1」，数值大小与转化难度呈正比[28]。本文以此设置生产空间优先、生活空间优先、生态空间优先、三生空间协调4种情景(表3)。其中，划定生产功能为主的一级用地耕地为生产空间，生活功能为主的一级用地建设用地为生活空间，生态功能为主的一级类用地（林地、草地、水域及未利用土地等)为生态空间[32]

# （5）综合概率计算

综合以上适宜性概率、邻域影响因子、惯性系数及转换成本等因素[29],估算设定用地类型所占用单元的总体转换概率，公式如下：

$$
T { \cal P } _ { p , k } ^ { t } = { \cal P } _ { p , k } ^ { t } \times \Omega _ { p , k } ^ { t } \times I _ { k } ^ { t } \times ( 1 - S C _ { c  k } )
$$

式中： $T P _ { p , k } ^ { t }$ 表示元胞 $P$ 在时间 $\mathbf { \Phi } _ { t }$ 从初始用地类型转变为用地类型 $k$ 的综合概率; $P _ { p , k } ^ { t }$ 表示元胞 $p$ 在 $\mathbf { \chi } _ { t }$ 时刻转换为 $k$ 类用地的适宜性概率; $\Omega _ { p , k } ^ { t }$ 表示邻域影响因子； $I _ { k } ^ { t }$ 表示 $k$ 地类型在 $\mathbf { \chi } _ { t }$ 时间的惯性系数；$S C _ { c  k }$ 表示从用地类型 $\boldsymbol { c }$ 到用地类型 $k$ 的转换成本。1.3.3精度验证以2015年的土地利用数据为基础，通过FLUS模型模拟得到2018年土地利用情形，利用2018年的真实土地利用情形进行验证,共拟合

284083个图斑，误差16438个图斑，得到的Kappa系数为0.823，总体精度为 $8 5 \%$ ，由此可知，FLUS模型的模拟精度较高(图2）。

# 2结果与分析

# 2.1总体变化趋势

2018—2030年汾河流域生态空间呈现两类演变趋势(表4、图3)，生态空间优先、三生空间协调情景下为线性增长，生产空间优先、生活空间优先情景为线性下降。2030年，生态空间在生态空间优先、三生空间协调情景下分别增长 $5 . 9 2 \% . 5 . 1 3 \%$ ，生产空间优先及生活空间优先情景下分别下降$9 . 4 0 \% . 2 . 2 0 \%$ 。生活空间一直处于不同规模型增长，与山西省社会经济及城市化建设增长趋势保持一致。而生产空间除生产空间优先情景下处于平稳增长，其余情景下都处于线性下降趋势，2024年、2030年生产、生活、生态空间用地结构比例仍维持4:1:5。

形成该结果的主因是地形、水系、土壤等环境因素，次因是开发技术及资金成本等社会经济因素。由于生产、生活空间用地均以地形坡度小、破碎度低、开发难度小的地区为标准，而研究区位于黄土高原东翼,适宜生产、生活空间用地的盆地平川区仅占总面积 $2 5 . 8 \%$ ,适宜生态空间用地山地丘陵区占总面积的 $7 4 . 2 \%$ ，且地形结构总体呈现高高程-小坡度(低高程-大坡度)的组合特征，开发技术成本较高，故形成该空间用地结构。

# 2.2多情景模拟结果

空间维度上，生态空间主要位于流域边缘山区，生产、生活空间集中分布于盆地核心区(图4、图5、图6)。生态、生产、生活空间整体呈现依次嵌套的格局特征。时间维度上，4种情景下生态空间核心区(流域边缘山区)变化幅度较小，与生产、生活空间接壤地带(流域山区向盆地过渡区)变化显著。2.2.1生产空间优先此情景下，耕地为其主要的用地类型，成为优先保护及增长的对象。模拟过程中考虑2024年、2030年耕地的用地规模需求，在不破坏生态用地中保护限制开发区及不违背生活用地需求增长的前提下，通过增加耕地向其他用地类型转换的成本并限制耕地向其他用地类型转移实现生产空间优先发展。

表3不同情景用地类型转换成本  
Tab.3 Conversion cost of land use types in different scenarios   

<html><body><table><tr><td>情景类型</td><td>转化成本及原则</td></tr><tr><td>生产空间优先</td><td>除建设用地，其他用地类型均可转换为耕地</td></tr><tr><td>生活空间优先</td><td>根据城市发展需求,按低等级用地到高等级单向转换原则,土地转换等级排序为：建设用地、耕地、林地、草地、水域 及未利用土地</td></tr><tr><td>生态空间优先</td><td>同生活空间优先情景转换原则,各类用地的生态效益等级排序：林地、水域、草地、其他</td></tr><tr><td>三生空间协调</td><td>综合以上3种单一情景的发展需求,土地转换等级排序为:建设、林地、耕地、水域、草地及未利用土地</td></tr></table></body></html>

通过利用FLUS模型，预测2024年、2030年生产、生活、生态空间分别占比为 $4 2 . 5 8 \%$ 、 $8 . 3 6 \%$ 、$4 9 . 0 6 \%$ 及 $4 2 . 9 6 \% . 1 0 . 2 4 \% . 4 6 . 8 0 \%$ 。在时间维度上，2024年，随着生产空间需求提高，生态空间的草地及未利用土地优先转出，使得生产空间规模增长$2 . 0 3 \%$ ,生态空间规模缩小 $1 . 1 2 \%$ ;2030年，生产空间需求进一步加大，生态空间规模在2024年基础上又缩小 $2 . 2 6 \%$ 。为满足经济发展及城市建设指向的生活空间扩展需求，限制生产空间用地的转出，生态

![](images/a814de54e825dc079effadb51e59065faf21302246ade390b7ac1a998dab73f3.jpg)  
图22018年汾河流域现状与模拟土地利用类型Fig.2Status and simulated land use type in Fenhe RiverBasin in 2018  
图32018—2030年4种情景三生空间演变趋势   
Fig.3 Production-living-ecological space evolution trend of the four scenarios from 2O18 to 2030

表42018年、2024年、2030年汾河流域多情景模拟三生空间用地情况  
Tab.4Fenhe River Basin in 2018,2024,2030 multi-scenario simulationof"production-living-ecological space land situation   

<html><body><table><tr><td rowspan="2">年份</td><td rowspan="2">情景</td><td colspan="2">生产空间</td><td colspan="2">生活空间</td><td colspan="6">生态空间</td></tr><tr><td>耕地面积 /km²</td><td>占比/%</td><td>建设用地 面积/km²</td><td>占比/%</td><td>林地面积 /km²</td><td>草地面积 /km²</td><td>水域面积 /km²</td><td>未利用地 面积/km²</td><td>小计/km</td><td>占比/%</td></tr><tr><td>2018</td><td>三生空间现状</td><td>15361.83</td><td>40.55</td><td>3132.99</td><td>8.27</td><td>10039.18</td><td>9042.80</td><td>302.18</td><td>4.81</td><td>19388.97</td><td>51.18</td></tr><tr><td rowspan="4">2024</td><td>生产空间优先</td><td>16126.38</td><td>42.58</td><td>3164.64</td><td>8.36</td><td>10155.47</td><td>8075.53</td><td>347.86</td><td>1.65</td><td>18580.50</td><td>49.06</td></tr><tr><td>生活空间优先</td><td>14431.00</td><td>38.10</td><td>4225.55</td><td>11.16</td><td>10031.08</td><td>8839.96</td><td>342.16</td><td>1.27</td><td>19214.47</td><td>50.74</td></tr><tr><td>生态空间优先</td><td>14371.78</td><td>37.95</td><td>3142.24</td><td>8.30</td><td>10178.88</td><td>9828.74</td><td>348.24</td><td>2.02</td><td>20357.88</td><td>53.75</td></tr><tr><td>三生空间协调</td><td>14372.41</td><td>37.95</td><td>3233.22</td><td>8.54</td><td>9913.02</td><td>10004.89</td><td>346.21</td><td>1.90</td><td>20266.01</td><td>53.51</td></tr><tr><td rowspan="4">2030</td><td>生产空间优先</td><td>16272.16</td><td>42.96</td><td>3879.08</td><td>10.24</td><td>10243.41</td><td>7125.21</td><td>351.15</td><td>2.76</td><td>17722.53</td><td>46.80</td></tr><tr><td>生活空间优先</td><td>13623.93</td><td>35.97</td><td>5276.97</td><td>13.93</td><td>10113.84</td><td>8514.24</td><td>342.16</td><td>1.27</td><td>18971.51</td><td>50.10</td></tr><tr><td>生态空间优先</td><td>13445.25</td><td>35.50</td><td>3898.19</td><td>10.29</td><td>10317.82</td><td>9857.47</td><td>352.16</td><td>1.14</td><td>20528.59</td><td>54.21</td></tr><tr><td>三生空间协调</td><td>13448.42</td><td>35.51</td><td>4045.86</td><td>10.68</td><td>9875.81</td><td>10152.18</td><td>348.74</td><td>0.76</td><td>20377.49</td><td>53.81</td></tr></table></body></html>

(a)生产空间优先 (b)生活空间优先 (c)生态空间优先 (d)三生空间协调5045443302201510 50 50454353025201510 504540353025201510%/早 -生产空间 405 生产空间 %/早 %/早生活空间 点2 生活空间 一生产空间 生产空间生态空间 生态空间 生活态空间 生活态空间1510中年份 年份 年份 年份空间的适宜性用地成为主要转出源，生产、生活空间因用地标准近似，出现竞争性转换，故形成生活、生产空间扩展速度趋缓的态势。在空间维度上，生态空间向流域边缘山地放射状收缩，山区向盆地过渡区变化显著，由于该区域为易开发的草地等，故形成此格局特征。

![](images/7b15b18baef31ec728c52fbd49c9ad5345199a12f52dca8662e8190f59e188ad.jpg)  
图42018年汾河流域土地利用类型及三生空间用地Fig.4 Land use types and production-living-ecological spaceland use in Fenhe River Basin in 2018

2.2.2生活空间优先该情景下，生活空间中重要组成建设用地(包括城乡、工矿及居民用地），按未来经济、人口及城市发展需要及低等级到高等级用地单向转换原则，实现生活空间优先发展。

在时间维度上，2024年，生产、生活、生态空间依次占比为 $3 8 . 1 0 \%$ 、 $1 1 . 1 6 \%$ 及 $5 0 . 7 4 \%$ ;2030年，生产空间、生活空间、生态空间占比变更为 $3 5 . 9 7 \%$ /$1 3 . 9 3 \%$ 及 $5 0 . 1 0 \%$ 。较2018年，2024年生活空间增长 $2 . 8 9 \%$ ,生产及生态空间分别减少 $2 . 4 5 \% . 0 . 4 4 \%$ 2030年，生活空间又增长 $2 . 7 7 \%$ ，生产、生态空间相应减少 $2 . 1 3 \% . 0 . 6 4 \%$ 。生活空间主要通过转移部分生产空间用地及少量生态空间用地实现优先发展。同理生产空间优先情景，当满足生活空间优先增长时，势必造成生产空间用地被优先挤占的结果，为维持生产空间用地需求的平衡，宜耕、宜牧的生态空间转出为生产空间。在空间格局上，生态空间变化幅度较大的是流域山区向盆地过渡区，生产、生活空间主体呈现斑块镶嵌布局。2030年生产空间扩张重心由汾河中游向下游转移，行政区上，表现为太原一榆次同城化发展，建设用地规模增加，城市规模达到阶段性饱和，并向下游等县扩张，造成生态空间胁迫重心下移。

2.2.3生态空间优先此情景下，考虑保证生态保护限制开发区基本规模不变的前提下，积极转移生产、生活空间挤占生态空间用地的面积。响应国家政策号召，退耕还林、还草及治理未利用土地。

在时间维度上，2024年、2030年在保证生活空间用地转移缓慢增长的前提下，实现生态空间的目标增长，2024年，生产、生活、生态空间用地结构比例为 $3 7 . 9 5 \% : 8 . 3 0 \% : 5 3 . 7 5 \%$ ，生态空间同比增长$2 . 5 7 \%$ ,相应的生产空间规模下降 $2 . 6 \%$ ;2030年，生态空间继续增长 $0 . 4 6 \%$ ,但增速降低。在保证永久

![](images/bb5687a89bccb3bd5fbeafc03e76796dbaeabcc19ddc663e56780b7c78410624.jpg)  
图52024年4种情景下汾河流域三生空间模拟结果

Fig.5Production-living-ecological space simulation results ofthe Fenhe River Basin under four scenarios n 202基本农田保护红线的基础上，生态空间的逆向转移源生产空间用地，首先满足生活空间转出需求，其次转出为生态用地(退耕还草、还林)。导致生活、生态空间竞争转移生产空间用地，形成生态、生活空间增长缓慢的态势。在空间格局上，生态空间向盆地河谷过渡带向心状扩张，流域中上游如娄烦县、交城县及寿阳县等退耕显著，实现县域范围内生态空间的扩大。

![](images/45cd033275e8119ce2866044b00f8258a367498018c5254798669f5e3678c3fc.jpg)  
图62030年4种情景下汾河流域三生空间模拟结果  
Fig.6Production-living-ecological space simulation results ofthe Fenhe River Basin under four scenarios n 2030

2.2.4三生空间协调综合以上3种单一情景的发展需求，按照转换成本原则，增加建设用地向其他用地转换成本，且控制生态空间用地类型的转出实现三生空间协调发展。

比较发现，2024年、2030年三生空间协调发展情景近似同期生态空间优先情景。一是限于汾河流域本底特征及社会经济发展趋势影响；二是基于“三线”（永久基本农田保护红线、生态保护红线、城镇开发边界线)原则，导致可用于三生空间相互间用地转移的后备资源有限。使得流域上游及边缘山区集中为生态空间，中下游盆地为生产、生活空间。其中，流域中心城市如太原、普中、临汾等辖区人口集聚、经济增长较快，对建设用地需求较大，生活空间占比较高，需加强在“三线"的原则下生态空间的合理布局。

# 3结论

（1）2018—2030年汾河流域生态空间呈现两类演变趋势，生态空间优先、三生空间协调情景为线性增长，生产空间优先、生活空间优先情景为线性下降；生产、生活、生态空间用地结构比例维持4:1：5。

(2）生态空间位于流域边缘山区，生产、生活空间位于核心盆地区，生态、生产、生活空间整体呈现依次嵌套的格局特征；生态空间核心区变化幅度小，边缘区变化显著。

(3）三生空间协调发展情景近似生态空间优先情景，受流域环境与社会经济影响，2024年、2030年生态空间变化幅度较小，但也存在胁迫隐患。

# 参考文献(References）：

[1]曹小曙.基于人地耦合系统的国土空间重塑[J].自然资源学报， 2019,34(10): 2051-2059.[Cao Xiaoshu.Geogovernance of national land use based on coupled human and natural systems[J]. Journal of Natural Resources,2019,34(10): 2051-2059.]   
[2] 周劲.三线·三生·三控:城乡布局结构的宏观管控机制[J].规划 师,2019,35(5):5-12.[Zhou Jin. Macro control mechanism of urban-rural layout with three lines,three spaces,and three controls [J].Planners,2019,35(5): 5-12.]   
[3] 龚亚男,韩书成,时晓标,等.广东省"三生空间"用地转型的时 空演变及其生态环境效应[J].水土保持研究,2020,27(3):203- 209.[Gong Yanan,Han Shucheng,Shi Xiaobiao,et al. Temporal and spatial evolution and associated eco-environment effects of the land use transformation of ecological-production-living spaces in Guangdong Province[J].Research of Soil and Water Conservation, 2020,27(3): 203-209.]

[4]王旭,马伯文,李丹，等.基于FLUS模型的湖北省生态空间多

情景模拟预测[J].自然资源学报,2020,35(1):230-242.[Wang Xu,Ma Bowen,Li Dan,et al. Multi-scenario simulation and prediction of ecological space in Hubei province based on FLUS model[J]. Journal of Natural Resources,2020,35(1): 230-242.]   
[5]戴文远,江方奇,黄万里,等.基于“三生空间"的土地利用功能 转型及生态服务价值研究——以福州新区为例[J].自然资源 学报,2018,33(12): 2098-2109.[Dai Wenyuan,Jiang Fangqi, Huang Wanli,et al. Study on transition of land use function and ecosystem service value based on the conception of production, living and ecological space: A case study of the Fuzhou new area[J]. Journal of Natural Resources,2018,33(12): 2098-2109.]   
[6]江曼琦,刘勇.“三生"空间内涵与空间范围的辨析[J].城市发展 研究,2020,27(4): 43-48,61.[Jiang Manqi,Liu Yong.Discussion on the concept definition and spatial boundary classification of “Production-Living-Ecological”space[J]. Uban Development Stuies,2020,27(4): 43-48, 61.]   
[7]许尔琪,张红旗.中国核心生态空间的现状、变化及其保护研究 [J].资源科学,2015,37(7):1322-1331.[Xu Erqi,Zhang Hongqi. Land use structure and change of important ecological space in China and protection research[J]. Resources Science,2015,7(7): 1322-1331.]   
[8]于正松,程叶青,李小建,等.工业镇"生产-生活-生态"空间演 化过程、动因与重构一—以河南省曲沟镇为例[J].地理科学， 2020,40(4): 646-656.[Yu Zhengsong, Cheng Yeqing,Li Xiaojian, et al. Spatial evolution process,motivation and reconstruction of “Production-Living-Ecology”in industrial town: A case study on Qugou Town in Henan Province[J]. Scientia Geographica Sinica,2020,40(4): 646-656.]   
[9]张驭航,李玲,王秀丽,等.基于模糊伽马模型的河南省生态空 间辨识与格局优化[J].水土保持研究,2020,27(6):211-217, 225.[Zhang Yuhang,Li Ling,Wang Xiuli, etal. Ecological spatial identification and patern optimization in Henan Province based on fuzzy gamma model[J]. Research of Soil and Water Conserva tion,2020,27(6): 211-217,225.]   
[10]丁乙宸,刘科伟,程永辉,等.县级国土空间规划中"三区三线” 划定研究——以延川县为例[J].城市发展研究,2020,27(5):1- 9.[Ding Yichen,Liu Kewei, Cheng Yonghui,et al. Study on the delimitation of“Three Zones and Three Lines”of county territorial spatial planning:A case study of Yanchuan County[J].Urban Development Studies,2020,27(5): 1-9.]   
[11] 刘彦文,刘成武,何宗宜,等.基于地理加权回归模型的武汉城 市圈生态用地时空演变及影响因素[J].应用生态学报,2020, 31(3): 987-998.[Liu Yanwen,Liu Chengwu,He Zongyi,et al. Spatial-temporal evolution of ecological land and influence factors in Wuhan urban agglomeration based on geographically weighted regression model[J]. Chinese Journal of Applied Ecology,2020,31 (3): 987-998.]   
[12] 陈德超,施祝凯,王祖静,等.苏州环太湖地区生态网络构建与 空间冲突识别[J].生态与农村环境学报,2020,36(6):778-787. [Chen Dechao,Shi Zhukai, Wang Zujing,et al.Ecological network construction and spatial conflict identification around Taihu Lake Area in Suzhou City[J]. Journal of Ecologyand Rural Environment,2020,36(6): 778-787.]   
[13] 王筱春,夏雪,雷轩.基于生态保护红线的滇池流域生态空间管 控[J].经济地理,2020,40(5):191-197.[Wang Xiaochun,Xia Xue,Lei Xuan.Ecological space control of Dianchi Lake Basin based on ecological protection red line[J]. Economic Geography, 2020,40(5): 191-197.]   
[14] 周宇洋,周国富,黄启芬,等.基于洛伦兹曲线和土地利用转型 的喀斯特山区"三生"空间分布研究[J].水土保持通报,2020, 40(3): 297-304,325.[Zhou Yuyang, Zhou Guofu, Huang Qifen, et al.A study on distribution of production,Living and Ecological Space in Karst Areas based on lorenz curves and land use transitions[J].Bulletin of Soil and Water Conservation,2020,40(3): 297-304,325.]   
[15] 杜腾飞,齐伟,朱西存,等.基于生态安全格局的山地丘陵区自 然资源空间精准识别与管制方法[J].自然资源学报,2020,35 (5): 1190-1200.[Du Tengfei, Qi Wei, Zhu Xicun,et al.Precise identification and control method of natural resources space based on ecological security pattern in mountainous hilly area[J]. Journal of Natural Resources,2020,35(5): 1190-1200.]   
[16] 潘方杰,王宏志,宋明洁,等.基于GIS的国家重点生态功能区 生态空间识别研究——以湖北长阳县为例[J].华中师范大学 学报（自然科学版),2020,54(4): 658-669.[Pan Fangjie,Wang Hongzhi, Song Mingjie,et al. Research on spatial identification of ecological space in national key ecological function regions based on GIS:A case study of Changyang Country in Hubei Province, China[J]. Journal of Central China Normal University(Natural Sciences Edition), 2020,54(4): 658-669.]   
[17] 陈爽,刘云霞,彭立华.城市生态空间演变规律及调控机制一 以南京市为例[J].生态学报,2008,28(5):2270-2278.[Chen Shuang,Liu Yunxia,Peng Lihua.Dynamics of urban ecological space evolution and policy responses: A case study of Nanjing City [J]. Acta Ecologica Sinica,2008,28(5): 2270-2278.]   
[18] 李京京,吕哲敏,石小平,等.基于地形梯度的汾河流域土地利 用时空变化分析[J].农业工程学报,2016,32(7):230-236.[Li Jingjing,Lyu Zhemin, Shi Xiaoping,et al. Spatiotemporal variations analysis for land use in Fen River Basin based on terrain gradient[J]. Transactions of the Chinese Society of Agricultural Engineering,2016,32(7): 230-236.]   
[19] 郭利刚,冯珍珍,刘庚,等.基于物元模型的汾河流域土地生态 安全评价[J].生态学杂志,2020,39(6): 2061-2069.[Guo Ligang, Feng Zhenzhen, Liu Geng,et al. Evaluation of land eco-security in Fenhe River Basin based on matter-element model[J]. Chinese Journal of Ecology,2020,39(6): 2061-2069.]   
[20]Liu XP,Liang X,Li X,et al.A future land use simulation model (FLUS) for simulating multiple land use scenarios by coupling human and natural effects[J]. Landscape & Urban Planning,2017, 168: 94-116.   
[21]Lin W B,Sun Y M, Steffen N,et al. Scenario-based flood risk assessment for urbanizing deltas using future land-use simulation (FLUS): Guangzhou Metropolitan Area as a case study[J]. Science of the Total Environment,2020,739:DOI:10.1016/j.scitotenv.2020.139899.   
[22] 杨露,颉耀文,宗乐丽,等.基于多目标遗传算法和FLUS模型 的西北农牧交错带土地利用优化配置[J].地球信息科学学报, 2020,22(3): 568-579.[Yang Lu, Xie Yaowen, Zong Leli,et al. Land use optimization configuration based on multi-objective genetic algorithm and FLUS model of agro-pastoral ecotone in Northwest China[J]. Journal of Geo- information Science,2020,22(3): 568-579.]   
[23] 陈兵飞,廖铁军,张莉坤.生态红线约束下万州区土地利用情景 模拟及生态价值评估[J].水土保持研究,2020,27(5):349-357, 364.[Chen Bingfei, Liao Tiejun, Zhang Likun. Simultion of land use situan and ecological value assessmentin Wanzhou district under the constraints of ecological red line[J].Research of Soil and Water Conservation,2020,27(5): 349-357,364.]   
[24] 赵林峰,刘小平,刘鹏华,等.基于地理分区与FLUS模型的城 市扩张模拟与预警[J].地球信息科学学报,2020,22(3):517- 530.[Zhao Linfeng,Liu Xiaoping,Liu Penghua,et al. Urban expansion simulation and early warning based on geospatial partition and FLUS model[J]. Journal of Geo-information Science,2O20,22 (3): 517-530.]   
[25] 王培俊,孙煌,华宝龙,等.福州市滨海地区生态系统服务价值 评估与动态模拟[J].农业机械学报,2020,51(3):249-257. [Wang Peijun, Sun Huang,Hua Baolong,et al. Evaluation and dynamic simulation of ecosystem service value in coastal area of Fuzhou City[J]. Transactions of the Chinese Society for Agricultural Machinery,2020,51(3): 249-257.]   
[26] 王毅,魏江超,孙启元,等.基于ARIMA-ANN模型的生态安全 评价及预测—以河西走廊城市群为例[J].生态学杂志, 2020,39(1): 326-336.[Wang Yi,Wei Jiangchao,Sun Qiyuan,et al. Ecological security evaluation and prediction based on ARIMAANN model: A case study of Hexi Corridor urban agglomeration [J]. Chinese Journal of Ecology,2020,39(1): 326-336.]

[27]张经度,梅志雄,吕佳慧,等.纳入空间自相关的FLUS模型在 土地利用变化多情景模拟中的应用J.地球信息科学学报, 2020,22(3): 531-542.[Zhang Jingdu,Mei Zhixiong,Lyu Jiahui, et al. Simulating multiple land use scenarios based on the FLUS model considering spatial autocorrelation[J]. Journal of Geo-information Science,2020,22(3): 531-542.]

[28] 秦琦瑞,李雪梅,陈庆伟,等.基于FLUS模型的天山山区未来 土地利用变化预估[J].干旱区研究,2019,36(5):1270-1279. [Qin Qirui,Li Xuemei, Chen Qingwei,et al. Estimation of future land use change in the Tianshan mountainous based on FLUS model[J].Arid Zone Research,2019,36(5): 1270-1279.]   
[29] 王明常,郭鑫,王凤艳,等.基于FLUS的长春市土地利用动态 变化与预测分析[J].吉林大学学报(地球科学版),2019,49(6): 1795-1804.[Wang Mingchang,Guo Xin,Wang Fengyan,et al. Dynamic change and predictive analysis of land use types in Changchun City based on FLUS model[J]. Journal of Jilin Unviersity:Earth Science Edition,2019,49(6): 1795-1804.]   
[30] 张世伟,魏璐瑶,金星星,等.基于FLUS-UGB的县域土地利用 模拟及城镇开发边界划定研究[J].地球信息科学学报,2020, 22(9):1848-1859.[Zhang Shiwei, Wei Luyao,Jin Xingxing,et al. Research on county land use simulation and urban development boundary delineation based on FLUS-UGB[J]. Journal of Geo-information Science,2020,22(9): 1848-1859.]   
[31] 欧阳晓,贺清云,朱翔.多情景下模拟城市群土地利用变化对生 态系统服务价值的影响——以长株潭城市群为例[J].经济地 理,2020,40(1): 93-102.[Ouyang Xiao,He Qingyun, Zhu Xiang. Simulation of impacts of urban agglomeration land use change on ecosystem services value under multi- scenarios:A case study in Changsha-Zhuzhou-Xiangtan urban agglomeration[J]. Economic Geography,2020,40(1): 93-102.]   
[32] 刘顺鑫,黄云.“三生空间"视角下万州区景观生态安全评价及 其耦合特征分析[J].水土保持研究,2020,27(6):308-316.[Liu Shunxin,Huang Yun.Evaluation and coupling coordination analysis of landspace ecological security of Wanzhou district from the

perspective of Production- Life- Ecological Space[J].Research of Soil and Water Conservation,2020,27(6): 308-316.]

# Multi-scenario simulation prediction of ecological space in the Fenhe River Basin using the FLUS model

SU Yingqing'， LIU Geng'， ZHAO Jingbo²， NIU Junjie'， ZHANG Enyue', GUO Ligang²， LIN Fei'   
(1.Research Center for Scientific DevelopmentofFenhe RiverVally,Taiyuan Normal University,Jinzhong 030619,   
Shanxi,China;2.School of Geographyand Tourism,Shaanxi Normal University,Xi'an71O119,Shaanxi,China; 3.Department of Management, Taiyuan Normal University, Jinzhong O3O619,Shanxi, China )

Abstract: Multi-scenario simulation and prediction of watershed ecological space was conducted for the Fenhe River Basin to provide reference and guidance for the coordinated and sustainable development of watershed production-living-ecological space.An ecological-economic-social model was used with land use type data for 2015 and 2O18,and 2O drivers were selected.The accuracy and effectiveness of the future land use simulation model was verified,and the spatiotemporal evolution characteristics and drivers of ecological change in the Fenhe River Basin were simulated and predicted for 2024 and 2030 under four scenarios: production space priority, living space priority,ecological space priority,and production-living-ecological space coordination. We found that the ecological space of the Fenhe River Basin presented two types of evolution trends from 2018 to 2030.It showedlinear growth under the ecological space priority and production-living-ecological space coordination scenarios，with increases of $5 . 9 2 \%$ and $5 . 1 3 \%$ ，respectively，while there was a linear decrease under the production space priority and living space priority scenarios,with decreases of $9 . 4 0 \%$ and $2 . 2 0 \%$ , respectively, and the proportion of production space,living space,and ecological space land structure maintained a ratio of 4:1:5.In the spatiotemporal patern, the ecological space was located in the marginal mountainous area of the watershed,and the production space and living space were located in the core basin. The ecological space, production space,and living space as a whole present successively nested pattern characteristics. The range of change in the core area of the ecological space was small,and the change in the marginal area was significant. The evolution trend of ecological space under the production-living-ecological space coordination scenario and ecological space priority scenario was similar in 2024 and 2030.Afected bythe natural-social development trend of the watershed and national policies,the available reserve land resources are predicted to be limited in the future,and the ecological space changeofthe watershed is predicted to be smal,but there are also hidden threats. Therefore，we suggest strictly folowing the basic principles of three lines，the permanent basic farmland protection red line,ecological protection red line,and urban development boundary line,reasonably planning the reserve land resources ofthe production-living-ecological space,actively governing and conserving the ecological space edge areas (ecologically sensitive areas),restricting the development of core areas,and promoting the scientific development of watersheds.

Keywords: ecological space; multi-scenario simulation; FLUS model; Fenhe River Basin； Shanxi