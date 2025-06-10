# 基于PLUS和InVEST模型的渭河流域土地利用与生境质量时空变化及预测

胡丰」，张艳²，郭宇1，张盼盼'，吕帅¹，张长春¹(1.河北农业大学国土资源学院,河北 保定071000；2.长安大学土地工程学院,陕西 西安71000)

摘要：生境质量是关系人类福祉和实现可持续发展的重要基础，对区域生态保护和土地资源可持续利用具有重大意义。以渭河流域为研究对象，基于2000、2010年和2020年的土地利用数据，应用斑块生成土地利用变化模拟(Patch-generating land use simulation,PLUS)模型、生态系统服务和权衡的综合评估(Integrated valuation of ecosystem services and trade-offs,InVEST)模型预测并评价了土地利用与生境质量时空变化特征。结果表明：(1)2000—2020年渭河流域建设用地和草地面积逐年增加，林地面积略微增长，耕地面积持续减少；2020—2050年土地利用变化趋势同2000—2020年基本一致但剧烈程度显著下降，建设用地扩张趋势减缓，耕地减少幅度下降，草地面积占比超过耕地跃居流域第一。(2)2000—2020年流域内生境质量两极分化趋势明显，低生境质量和高生境质量区域面积有所增加，中等生境质量的面积减少，整体生境质量水平呈上升趋势;2020—2050年生境质量水平继续保持逐年上升趋势但增幅放缓，生境质量变化强度下降，低生境质量区域面积逐渐减少，中等生境质量面积保持稳定，高生境质量面积有所增长。研究结果可为渭河流域土地资源可持续利用和高质量发展提供相应科学依据和决策参考。

关键词：土地利用；生境质量；PLUS模型；InVEST模型；渭河流域文章编号：

土地利用变化作为联系人类社会经济活动与自然环境演变的重要纽带，能够直观反映人类活动对地表系统的改造过程，是全球环境变化研究的核心内容[1-2]。生境质量指特定时空条件下生态系统为个体和种群提供生存繁衍所需资源的能力，是维护生物多样性和区域可持续发展的重要因素[3-4]。通常土地利用状况能够体现生境质量水平，两者关系密切，分析土地利用时空变化特征可进一步探究生境质量变化规律及原因[5-6]。随着土地利用变化动态建模技术的快速发展，众多学者结合地理学、生态学等理论，预测土地利用变化并对未来生境质量进行评价[7-8]

土地利用预测可通过多种模型实现，其中元胞自动机(Cellularautomata,CA)作为诸多模型构建的基础，经过不断发展形成了Logistic-CA[9]、CLUE-$\mathrm { S } ^ { [ 1 0 ] }$ 、FLUS[1等模型，在生态红线划定、地貌演变分析和国土空间优化等方面应用广泛，但这些模型在大尺度和多地类综合模拟方面表现较弱[12]。而斑块生成土地利用变化模拟(Patch-generating land usesimulation，PLUS)模型通过引入用地扩张分析策略和多类型随机斑块种子生成机制有效解决了上述问题，同时具有模拟精度高、数据处理快等优势，能有效地模拟多地类复杂演变的过程[13-15]。如Li等[15]耦合灰色多目标优化模型(GMOP)和PLUS模型分析了2026年自然增长、生态优先和生态-经济平衡3种模式下中国川滇地区的生态系统服务价值时空演变特征;喇露梦等[13]采用生存可能性边界(PPF)并结合PLUS模型探讨了不同情景下秭归县各生态系统服务之间的权衡特征；陆羽等[16]利用PLUS模型预测了2025年常州市武进区生态空间格局并进行了生态功能分区，以上研究表明PLUS模型具有良好的适用性。

土地利用变化影响着物质流、信息流在生境各斑块间的循环流动，进而影响区域生境质量水平，而生境质量变化的研究能够直观反映区域生态系统服务功能状态和变化趋势，对区域生态环境保护和可持续发展意义重大[6.17]。目前,评估区域生境质量常采用的模型有生态系统服务和权衡的综合评估（Integrated valuation of ecosystem services andtrade-offs，InVEST)模型、生态系统服务人工智能(Artificial intelligence for eco-system services,ARIES)模型和生态系统服务社会价值评估（Socialvaluesforecosystemservices,SolVES)模型,其中InVEST模型由于具有操作便捷、可视化能力强且理论体系较为完善等优势,应用广泛[18-19]。如冯舒等[20]运用In-VEST模型的生境质量评价模块评估了2000—2015年北京市的生境质量退化程度和生境质量变化情况;黄木易等[21]借助地形位和InVEST模型等进行了大别山地区生境质量时空格局演变与景观格局互动分析;冯琰玮等[22]在评价呼和浩特城市扩展和生境质量演变的基础上，探讨了生境质量对城市用地扩展的时空响应机制。以往研究借助InVEST模型开展了不同尺度的生境质量测算与评估工作,有力论证了模型的科学性和适用性。

上述两者模型应用广泛且效果良好，但耦合PLUS模型和InVEST模型来预测未来土地利用时空格局并探究区域生境质量发展趋势的研究较少。因此，本研究通过集成PLUS和InVEST模型，以渭河流域为研究区，对2000—2020年渭河流域土地利用和生境质量的演变过程进行分析，并对未来的生境质量时空格局进行预测，旨在探究渭河流域土地利用与生境质量的演变机制，为流域内生态环境治理、保护以及推动地区高质量发展提供有效科学的参考依据。

![](images/ecf76c7335986681e1fc7ac073e5eedf7414fd1621d92826de1c22a1f878b044.jpg)  
图1渭河流域示意图  
Fig.1 Schematic diagramofWeihe River Basin

水量为 $6 8 3 . 6 \mathrm { m m }$ ,年平均气温 $7 . 8 { \sim } 1 3 . 5 ~ \mathrm { ^ { \circ } C }$ ,地形地貌复杂，地势西高东低，土壤和植被类型丰富。流域内自然条件差异明显，西部、北部自然条件恶劣，生态环境脆弱且经济发展水平较低，含有六盘山集中连片特困地区，随着脱贫攻坚和生态治理实施推进，区域经济发展水平和生态环境稳步向好，但生态稳定性仍需提高；中部是地势平坦、区位优越的平原地带，人口集中且经济发展较快，人地矛盾突出；南部是秦岭山区，植被覆盖率高，生态环境状况良好。

# 1.2数据来源及处理

在考虑模型精确性和现实性的基础上，综合自然和社会经济条件对土地利用的影响[23],依据驱动因子可获取性、时效性和显著性原则，选取高程、人口等14个因子作为影响土地利用变化的驱动因子。因此，本文使用的数据主要包括行政界限、土地利用数据、社会经济统计数据以及土地利用驱动因子空间数据构成(表1)。同时为保证数据空间精度的一致性，利用ArcGIS10.2的裁剪和重采样工具对驱动因子、土地利用数据进行处理，统一转换为$9 0 \mathrm { m } \times 9 0 \mathrm { m }$ 精度的栅格文件。

# 研究区与数据源

# 1.1 研究区概况

渭河流域 $( 1 0 4 ^ { \circ } 0 0 ^ { \prime } { \sim } 1 1 0 ^ { \circ } 2 0 ^ { \prime } \mathrm { E } , 3 3 ^ { \circ } 5 0 ^ { \prime } { \sim } 3 7 ^ { \circ } 1 8 ^ { \prime } \mathrm { N } )$ 是黄河流域的第一大子流域,地处我国西北地区，面积 $1 . 3 4 \times 1 0 ^ { 5 } ~ \mathrm { k m } ^ { 2 }$ ，涉及陕西甘肃宁夏3省13市（图1)。全域位于干旱半干旱地带，雨热同期,年均降

# 2 研究方法

# 2.1 PLUS模型

PLUS模型是一个以元胞自动机为基础构建的新模型[14]。模型通过分析两期土地利用数据间各类用地扩张部分及驱动因子空间特征，采用随机森林算法对土地利用扩张部分进行采样计算逐一获

# 表1数据来源信息表

Tab.1 Data source information table  

<html><body><table><tr><td></td><td>数据类型</td><td>数据名称</td><td>初始数据来源</td></tr><tr><td rowspan="2">基础数据</td><td>行政界限</td><td>陕甘宁地区省、市级行政边界</td><td>中国科学院资源环境与数据中心</td></tr><tr><td>土地利用数据</td><td>2000—2020年3期土地利用数据</td><td>(http://www.resdc.cn/DOI)</td></tr><tr><td rowspan="9">驱动因子</td><td>社会经济统计数据</td><td>2020年地区生产总值、人口数据统计汇总</td><td>政府工作报告</td></tr><tr><td>自然环境条件</td><td>高程</td><td>中国科学院资源环境与数据中心 (http://www.resdc.cn/DOI)</td></tr><tr><td></td><td>坡度</td><td></td></tr><tr><td></td><td>距最近河流距离</td><td></td></tr><tr><td></td><td>年平均降水量</td><td></td></tr><tr><td></td><td>年平均气温</td><td></td></tr><tr><td></td><td>土壤侵蚀程度</td><td>地理国情监测平台</td></tr><tr><td>社会经济条件</td><td>地均GDP</td><td></td></tr><tr><td></td><td>人口</td><td>(http://www.dsac.cn/)</td></tr><tr><td></td><td>距最近铁路距离</td><td></td></tr><tr><td></td><td>距最近道路(省道、国道、县道)距离</td><td></td></tr><tr><td></td><td>距最近高速距离</td><td></td></tr><tr><td></td><td>距最近区县中心距离</td><td></td></tr><tr><td></td><td>距最近地市中心距离</td><td></td></tr><tr><td></td><td></td><td>距城市建成区距离</td></tr></table></body></html>

取各类用地发展概率；再基于轮盘赌的自适应惯性竞争机制获取土地利用变化综合概率;最后结合随机斑块生成、过渡转移矩阵和阈值递减机制实现优化，确定最终用地方式[12]

2.1.1 适宜性概率计算在PLUS模型用地扩张分析策略模块下，使用随机采样机制减少模型计算量的同时运用能处理高维数据和解决驱动因子共线性的随机森林算法挖掘土地利用转移过渡规律，获取各土地利用类型发展概率[24],公式如下：

$$
\mathop { P _ { i , k ( X ) } ^ { d } } = \frac { \displaystyle \sum _ { n = 1 } ^ { M } I [ h _ { \scriptscriptstyle n } ( X ) = d ] } { M }
$$

式中： $X$ 为由驱动因子组成的向量; $h _ { n } ( X )$ 为在决策树为 $\mathbf { \Omega } _ { n }$ 时计算得到的土地利用预测类型; $I [ \cdot ]$ 决策树的指示函数； $M$ 为决策树数量； $d$ 取值为0或1，值为1表示其他土地利用类型转变为土地利用类型$k$ ,而0表示不涉及向地类 $k$ 的转变; $P _ { i , k ( X ) } ^ { d }$ 为在 $d$ 值取值为0或1条件下，空间单元 $i$ 处 $k$ 类土地利用类型增长的概率[25]。

2.1.2领域权重设定领域权重主要用于反映不同土地利用类型之间相互转换的难易程度[26],公式如下：

$$
\Omega _ { i , k } ^ { t } = \frac { \mathrm { c o n } ( c _ { i } ^ { t - 1 } = k ) } { n \times n - 1 } \times w _ { k }
$$

式中： $n \times n$ 为元胞单元,研究设定 $\scriptstyle n = 3$ $\mathrm { c o n } ( c _ { i } ^ { t - 1 } = k )$ 为 $\boldsymbol { n } \times \boldsymbol { n }$ 元胞迭代至最后阶段时地类 $k$ 所占网格单元总数； $\varOmega _ { i , k } ^ { t }$ 为 $\mathbf { \chi } _ { t }$ 时刻地类 $k$ 在空间单元 $i$ 处的领域权重； $\boldsymbol { w } _ { k }$ 为地类 $k$ 的领域权重参数，介于[0,1]之间，在参考已有研究成果并结合渭河流域实际情况下[26-27],设定领域权重参数(表2)。

表2领域权重参数  
Tab.2 Realm weight parameters  

<html><body><table><tr><td>参数</td><td>耕地</td><td>林地</td><td>草地</td><td>水域</td><td>建设用地</td><td>未利用地</td></tr><tr><td>领域权重</td><td>0.00</td><td>0.66</td><td>1.00</td><td>0.68</td><td>0.96</td><td>0.69</td></tr></table></body></html>

2.1.3自适应惯性系数计算自适应惯性可根据土地数量预期需求和现有实际情况的差异在迭代过程进行自适应调整，使土地利用数量朝着预期目标发展，从而实现空间用地类型变化的模拟，公式如下：

$$
D _ { k } ^ { t } = \left\{ \begin{array} { c c } { { D _ { k } ^ { t - 1 } } } & { { \displaystyle \left( \left| G _ { k } ^ { t - 1 } \right| \leqslant \left| G _ { k } ^ { t - 2 } \right| \right) } } \\ { { \displaystyle D _ { k } ^ { t - 1 } \times \frac { G _ { k } ^ { t - 2 } } { G _ { k } ^ { t - 1 } } } } & { { \displaystyle \left( 0 > G _ { k } ^ { t - 2 } > G _ { k } ^ { t - 1 } \right) } } \\ { { \displaystyle D _ { k } ^ { t - 1 } \times \frac { G _ { k } ^ { t - 1 } } { G _ { k } ^ { t - 2 } } } } & { { \displaystyle \left( G _ { k } ^ { t - 1 } > G _ { k } ^ { t - 2 } > 0 \right) } } \end{array} \right.
$$

式中： $D _ { k } ^ { t }$ 分别为 $\mathbf { \chi } _ { t }$ 时刻用地类型 $k$ 的惯性系数; $G _ { k } ^ { t - 1 }$ 、 $G _ { k } ^ { t - 2 }$ 分别为t-1、t-2时刻用地需求与实际数 量之间的差异。

# 干辛区地理

2.1.4随机斑块生成参数设定随机斑块生成机制能更好模拟现实土地利用变化过程中各土地利用类型的自然增长，同时为控制多类型土地利用斑块的生成，该模型提出使用竞争过程的阈值下降规则,用以限制各土地利用类型的自发增长[12.24],公式如下：

$$
\mathrm { O P } _ { i , k } ^ { d = 1 , t } = P _ { i , k } ^ { d } \times \varOmega _ { i , k } ^ { t } \times D _ { k } ^ { t }
$$

$$
\mathrm { T P } _ { i , k } ^ { d = 1 , t } = \left\{ \begin{array} { l l } { P _ { i , k } ^ { d = 1 } \times \left( r \times \mu _ { k } \right) \times D _ { k } ^ { t } } \\ { P _ { i , k } ^ { d = 1 } \times \varOmega _ { i , k } ^ { t } \times D _ { k } ^ { t } } \end{array} \right. ( \varOmega _ { i , k } ^ { t } = 0 , r < P _ { i , k } ^ { d = 1 } )
$$

式中： $\mathrm { O P } _ { i , k } ^ { d = 1 , t }$ 为空间单元 $i$ 处在 $\mathbf { \chi } _ { t }$ 时刻向用地类型 $k$ 转变的综合概率； $P _ { i , k } ^ { d }$ 为空间单元 $i$ 处土地利用类型向 $k$ 发展的适宜性概率； $D _ { k } ^ { t }$ 为自适应驱动系数；$\mathrm { T P } _ { i , k } ^ { d = 1 , t }$ 为引入随机斑块生成机制后,空间单元 $i$ 处在 $\mathbf { \chi } _ { t }$ 时刻向用地类型 $k$ 转变的综合概率; $P _ { i , k } ^ { d = 1 }$ 为空间单元 $i$ 处土地利用类型向土地类型 $k$ 转化的概率； $\boldsymbol { r }$ 为0\~1之间的随机值; $\boldsymbol { \mu } _ { k }$ 为新的土地利用斑块生成阈值。

2.1.5过渡矩阵及最终用地发展概率计算过渡矩阵用于定义地类之间是否可以转换，能够有效约束地类之间不合理的转化，同时设定斑块生成阈值衰减系数用以约束土地利用类型的自发增长过程，确定最终用地方式[12],公式如下：

$$
\sum _ { k = 1 } ^ { N } |  G _ { k } ^ { t - 1 } | - \sum _ { k = 1 } ^ { N } G _ { k } ^ { t } < \mathrm { s t e p } ,  \operatorname { \mathbb { M } } \{ { \big \} } l = l + 1
$$

$\int P _ { i , k } ^ { d = 1 } > \tau , \mathrm { T M } _ { c , k } = 1$ 用地类型转变τ=δ²×R（7$\Big ) P _ { i , k } ^ { d = 1 } \leqslant \tau , \mathrm { T M } _ { c , k } = 0$ 用地类型恒定

式中： $N$ 为土地利用类型总数;step为PLUS模型拟合土地利用需求需要的步长； $l$ 为阈值衰减步骤数;$\tau$ 为土地利用增长阈值; $\delta$ 为衰减阈值 $\tau$ 的衰减系数，介于0\~1之间; $R _ { 1 }$ 为均值为1的正态分布; $\mathrm { T M } _ { c , k }$ 为过渡转移矩阵，定义用地类型 $\mid c \mid$ 是否可以向 $k$ 转变，取值为1表示允许转变，取值为0表示限制转变，结合渭河流域土地利用变化特征及生态环境政策，设定过渡转移矩阵(表3)。

# 2.2生境质量模型

本文利用InVEST模型的HabitatQuality模块进行生境质量的评估。生境质量是反映环境提供给个体或种群生存发展所需的各类资源和条件状况，当生境质量较好时，资源和条件得到满足，生物多样性发展得到保障[28]。在此基础上，该模块将人类活动干扰引入到对生境质量评价当中，当人类活动

# 表3过渡转移矩阵

Tab.3Transitionmatrix   

<html><body><table><tr><td>土地利用类型</td><td>耕地</td><td>林地</td><td>草地</td><td>水域</td><td>建设用地</td><td>未利用地</td></tr><tr><td>耕地</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>林地</td><td>1</td><td>1</td><td>1</td><td>0</td><td>1</td><td>1</td></tr><tr><td>草地</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr><tr><td>水域</td><td>0</td><td>0</td><td>0</td><td>1</td><td>0</td><td>0</td></tr><tr><td>建设用地</td><td>1</td><td>1</td><td>1</td><td>0</td><td>1</td><td>1</td></tr><tr><td>未利用地</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr></table></body></html>

强度加大时生境质量水平明显下降，其原理为结合外界威胁因子及强度和各土地利用类型对威胁因子的敏感度计算出生境质量分值[29],公式如下：

$$
Q _ { i k } ^ { \phantom { } } = H _ { k } ^ { \phantom { } } \left( 1 - \frac { M _ { i k } ^ { z } } { M _ { i k } ^ { z } + K ^ { z } } \right)
$$

$$
M _ { i k } = \sum _ { r = 1 } ^ { R } \sum _ { y = 1 } ^ { Y _ { r } } \left( \sum _ { \displaystyle r } w _ { r } \right) r _ { y } i _ { r x y } \beta _ { x } S _ { k r }
$$

式中： $Q _ { i k }$ 为地类 $k$ 在空间单元 $i$ 处的生境质量，介于0\~1之间，值越高生境质量越好； $\boldsymbol { H } _ { k }$ 为地类 $k$ 的生境适宜度; $M _ { i k }$ 为空间单元 $i$ 处生境退化度； $z$ 为模型默认参数，值为2.5; $K$ 为半饱和系数,通常取生境退化度最大值的1/2; $R$ 为威胁因子个数； $Y _ { r }$ 为威胁层在地类图层中的单元个数； $\boldsymbol { w } _ { r }$ 为威胁因子权重; $r _ { _ { y } }$ 为威胁因子强度; $i _ { _ { r x y } }$ 为威胁因子对生境的威胁水平； $\beta _ { x }$ 为法律保护程度； $S _ { k r }$ 为地类 $k$ 对威胁因子的敏感程度。

在上述公式中，除需要土地利用数据之外，还需结合研究地区实际情况和已有研究成果对胁迫因子、土地利用类型生境适宜性和对胁迫因子的敏感度进行设定。在参考现有研究成果和软件使用手册后[3.30-31],将耕地、建设用地和未利用地作为威胁因子，设定其权重、最大影响距离和退化类型(表4);并进一步设定各土地类型的生境适宜性及对威胁因子的相对敏感性(表5)。

# 表4胁迫因子最大影响距离及权重

Tab.4 Maximum influence distance and weight of stress factor   

<html><body><table><tr><td>威胁因子</td><td>耕地</td><td>建设用地</td><td>未利用地</td></tr><tr><td>最大胁迫距离/km</td><td>4</td><td>8</td><td>6</td></tr><tr><td>权重</td><td>0.6</td><td>0.4</td><td>0.5</td></tr><tr><td>空间衰退类型</td><td>线性</td><td>指数</td><td>线性</td></tr></table></body></html>

# 表5各土地利用类型对生境威胁因子的敏感度

Tab.5Sensitivity of land use types to habitat threatfactors   

<html><body><table><tr><td rowspan="2">土地利用类型</td><td rowspan="2">生境 适宜度</td><td colspan="2">胁迫因子</td></tr><tr><td>耕地</td><td>建设用地 未利用地</td></tr><tr><td>耕地</td><td>0.3</td><td>0.0</td><td>0.8 0.4</td></tr><tr><td>林地</td><td>1.0</td><td>0.6</td><td>0.4 0.2</td></tr><tr><td>草地</td><td>0.9</td><td>0.8</td><td>0.6 0.6</td></tr><tr><td>水域</td><td>0.7</td><td>0.5</td><td>0.4 0.3</td></tr><tr><td>建设用地</td><td>0.0</td><td>0.0</td><td>0.0 0.1</td></tr><tr><td>未利用地</td><td>0.5</td><td>0.6</td><td>0.4 0.0</td></tr></table></body></html>

# 3结果与分析

# 3.1土地利用变化

渭河流域土地利用以耕地、草地和林地为主，面积占比超 $9 0 \%$ ,其中耕地占比超 $4 0 \%$ （图2）。2000一2020年土地利用变化明显，流域西部、北部破碎化程度较高的耕地逐渐转为草地；子午岭、六盘山地区林地面积略微提升;关中平原建设用地向外扩张现象突出，泾河谷地建设用地略微增长。

耕地是流域内面积占比最高的地类，但20a间面积持续下降，由2000年的 $5 . 8 9 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 减少到2020年的 $5 . 4 4 \times 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ ,耕地保护形势严峻。林地面积先增后减，总体呈上升趋势，面积增加993.38$ { \mathrm { k m } } ^ { 2 }$ 。草地、建设用地、水域和未利用地面积持续增长，面积增加量依次为 $1 6 8 2 . 6 8 \ \mathrm { k m } ^ { 2 } \setminus 1 7 2 9 . 6 2 \ \mathrm { k m } ^ { 2 } .$ $4 9 . 0 1 ~ \mathrm { k m } ^ { 2 }$ 和 $4 3 . 7 8 ~ \mathrm { k m } ^ { 2 }$ ,其中建设用地增长幅度达$4 8 \%$ ,是涨幅最高的土地类型。总体来看，流域内土地利用变化呈现“一减多增"的变化趋势，即耕地面积减少，其他用地类型面积增加(图3)。

![](images/89281148c7c62c357b47d2bfff5a9d5087f58b988bd6f6bd01d5dc04940b110c.jpg)  
Fig.2Spatial distributions of land use in Weihe River Basin from 2OoO to 2020

# 3.2土地利用预测

利用预测的2020年土地利用数据与实际情况进行对比，通过计算总体精度和Kappa系数来评价模型精度。结果表明，总体精度为0.893,Kappa系数为0.819，模拟结果空间一致性程度高，PLUS模型在本研究中具有较好的适用性。

以2020年土地利用数据为基础，逐一预测2030一2050年土地利用空间格局(图4)。分析预测结果可知，渭河流域未来土地利用空间格局将延续现有土地利用变化特征，体现生态退耕和经济发展两大主题，西部、北部地区耕地继续向草地发展，林地、水域和未利用地相对稳定，关中平原地区的建设用地呈集聚性扩张。随着时间推移，渭河流域生态脆弱区的稳定性将进一步提高，以西安为核心形成的关中城市群发展格局将进一步显化。

2020一2050年耕地面积继续减少，虽减少速度降低，但未来耕地保护形势依然严峻；林地面积略微下降;草地面积增长速度降低，新增面积趋于稳定，其超过耕地成为流域内面积占比最大的土地利用类型，下一步需要重视对草地生态的保护工作，充分发挥生态系统自恢复力的作用；水域面积稳定增长,趋势向好;建设用地继续保持增长,但增长幅度逐年降低，不过城市扩张占用耕地问题依然严重；未利用地得到充分开发和利用，面积持续减少。总体来看，2020一2050年渭河流域土地利用变化情况同2000—2020年基本一致，但土地利用变化强度明显减弱，土地利用结构趋于稳定(图5)。

![](images/f2bb75a868b1937c5d0da06a2e8c3b67b083dd0a6020cdc774c0dc2650a61602.jpg)  
图22000—2020年渭河流域土地利用空间分布  
图32000—2020年渭河流域各类型土地利用面积Fig.3Land use area of various types in WeiheRiver Basin from 2000 to 2020

![](images/498a8036485775abd09faa3f64a0795b779a4047bcd7c8b2dc64f7a999b06b84.jpg)  
干旱区地理  
图42030—2050年渭河流域土地利用空间分布预测  
Fig.4 Spatial distribution prediction of land use in Weihe River Basin from 2O3O to 2050   
图52000—2050年渭河流域各土地利用类型面积变化  
Fig.5Area changes of land use types in Weihe River Basin from 2OoO to 2050

(a)耕地 (b)林地0 -1 1250 654321023 %/率平 107050 .面积变化率 %/率平  
-2000 . 面积变化率 4 250 □新增/减少面积  
-2500 □新增/减少面积 -5 0-3000 -6 -250 -12010 2020 2030 -2040 2050 2010 2020 20302030-2040 2040-20502000 2010 2020 2030 2040 2000 2010 2020-年份 年份(c)草地 (d)水域1000 ...面积变化率 3 100 ..面积变化率5800 □新增/减少面积 80 □新增/减少面积 4 %/率平2600 60 3400 1 40 2200 20 10 0 0 □ 0-2020 -2030 2040 2050 -2010 -2020 -2030 -20402000-2010 2040-20502010- 2020- 2030- 2040- 2000 2010- 2020- 2030年份 年份(e)建设用地 (f)未利用地1200 30 80 60100060 面变积 2520 %/率亚 604020 面变化面积 家400 1510 20 /0 5 -40 -20-2020 2030 2040 2050 -2010 2020 -2030 -2040 20502000-20102010 2020- 2030 2040 2000 2010 2020- 2030 2040-年份 年份

# 3.3生境质量变化

结合渭河流域生境质量整体情况，利用自然断点法，将渭河流域生境质量划分为5个等级：低(0.0\~0.3）、较低（0.3\~0.5）；中等（0.5\~0.7）、较高(0.7\~0.9）高(0.9\~1.0)。从面积占比变化情况来看(表6)，不同生境质量等级的面积变化明显且差异显著，两极化发展趋势明显。低生境质量区域面积占比最高且持续增长,20a面积共增加 $1 7 9 9 . 7 1 \mathrm { k m } ^ { 2 }$ 占比上升 $1 . 3 4 \%$ 。较低生境质量区域面积变化剧烈,共减少面积 $4 6 8 8 . 6 3 \mathrm { ~ k m } ^ { 2 }$ ,占比下降 $3 . 4 9 \%$ 。中等生境质量区域面积占比不足 $1 \%$ ，面积小幅度增加。较高生境质量区域面积上涨 $1 7 8 5 . 4 1 ~ \mathrm { k m } ^ { 2 }$ ，占比提升至 $3 7 . 9 4 \%$ 。高生境质量区域面积总体上涨，增加$1 0 5 1 . 7 6 ~ \mathrm { k m } ^ { 2 }$ ，占比提高 $0 . 7 8 \%$ 。 $2 0 0 0 , 2 0 1 0 , 2 0 2 0$ 年渭河流域生境质量平均分值分别为0.6113、0.6206、0.6225，生境质量整体属于中等偏上水平且呈现不断提升的趋势，流域内生态环境治理成效显著。

从空间分布来看(图6)，高生境质量的区域主要集中在秦岭北麓、六盘山和子午岭等山区，土地利用类型以林地为主，自然生态环境稳定且受人类活动干扰较小。较高生境质量的区域主要集中在山脚缓冲带。中等生境质量等级的区域主要分布在流域北部和关中平原内部河道周围，以草地和水域为主。较低生境质量等级区域破碎化程度高，集中在流域西部、西北部区域。低生境质量区域高度集中在关中平原内部，地类以耕地和建设用地为主。总体来看，流域内部主要以低生境质量和高生境质量区域为主，区域差异明显，地形、气候、土壤等自然条件不适合人类进行生产生活的区域，常以较高生境质量为主；而自然和区位条件较好的区域，人类活动强度较大，以较低生境质量为主。

为进一步分析生境质量空间变化情况，将生境质量进行叠加分析，得到渭河流域生境质量变化(图7)。根据生境质量变化幅度进行如下划分：生境质量明显改善( $> 0 . 2 \AA ^ { \prime }$ 、生境质量微幅上涨 $( 0 . 0 \sim$ 0.2）、生境质量保持稳定（0.0）、生境质量轻微下降$\left( - 0 . 2 \mathrm { \sim } 0 . 0 \right)$ 、生境质量退化严重( $\left( < - 0 . 2 \right)$ ，在此基础上统计不同变化程度的生境质量面积及占比(表7)。

2000一2010年生境质量总体以上升为主，稳定区域面积占比超 $5 0 \%$ ,主要位于秦岭北麓、子午岭和关中平原地区，用地类型稳定；微幅上涨区域面积 $3 1 0 8 1 . 5 9 \mathrm { k m } ^ { 2 }$ ，集中在东部、北部的黄土高原丘壑

表62000—2020年渭河流域各生境质量等级面积及占比  
Tab.6Area and proportion of habitat quality grades in Weihe River Basin from 2ooo to 2020   

<html><body><table><tr><td rowspan="2">生境 质量等级</td><td colspan="2">2000年</td><td colspan="2">2010年</td><td colspan="2">2020年</td><td colspan="2">2000—2020年</td></tr><tr><td>面积/km²</td><td>占比/%</td><td>面积/km²</td><td>占比/%</td><td>面积/km²</td><td>占比/%</td><td>面积/km²</td><td>占比/%</td></tr><tr><td>低</td><td>53778.75</td><td>40.07</td><td>54387.77</td><td>40.52</td><td>55578.46</td><td>41.41</td><td>1799.71</td><td>1.34</td></tr><tr><td>较低</td><td>9079.96</td><td>6.77</td><td>6409.66</td><td>4.78</td><td>4391.33</td><td>3.27</td><td>-4688.63</td><td>-3.49</td></tr><tr><td>中等</td><td>833.02</td><td>0.62</td><td>846.70</td><td>0.63</td><td>884.77</td><td>0.66</td><td>51.75</td><td>0.04</td></tr><tr><td>较高</td><td>49138.88</td><td>36.61</td><td>50124.56</td><td>37.35</td><td>50924.29</td><td>37.94</td><td>1785.41</td><td>1.33</td></tr><tr><td>高</td><td>21386.36</td><td>15.93</td><td>22448.28</td><td>16.73</td><td>22438.12</td><td>16.72</td><td>1051.76</td><td>0.78</td></tr></table></body></html>

![](images/5743ffc29340f03c0f2f7ff52091b617dd5ffb634eb919db55da623ac0fd282c.jpg)  
图62000—2020年渭河流域生境质量空间分布  
Fig.6Spatial distributions of habitat quality in Weihe River Basin from 2OoO to 2020

![](images/fffad5bae893fc83b9a73e931074ca704ab4afe00a284b06766d62250df4deb4.jpg)  
干旱区地理

Fig.7Spatial variation of habitat quality in Weihe River Basin from 2OoO to 2020区；明显改善区域面积 $3 8 1 4 . 3 7 ~ \mathrm { k m } ^ { 2 }$ ,分布较为分散，与退耕还草区域高度契合；轻微下降区域面积$2 4 0 9 6 . 2 8 \ \mathrm { k m } ^ { 2 }$ ，主要集中城市建成区外围；退化严重区域主要为建设用地扩张而直接影响的区域，面积为 $2 8 2 3 . 5 4 ~ \mathrm { k m } ^ { 2 }$ 。2010—2020年生境质量稳定区域面积略微降低，但占比依旧第一，空间布局变化微弱；生境质量微幅上涨区域面积略微增加，达$3 2 6 7 6 . 0 6 \ \mathrm { k m } ^ { 2 }$ ;生境质量轻微下降区域破碎化程度明显提升，在西部、西北部均有分布，与生境质量微幅上涨、明显改善区域相互交织、联系紧密，其面积占比下降至 $1 1 . 8 9 \%$ 。退化严重区域面积急剧增加，达 $8 1 0 0 . 2 3 ~ \mathrm { k m } ^ { 2 }$ ，亟需采取有效措施改善生境质量。结合土地利用变化可知，2000—2020年流域西部、北部生态脆弱区在开展生态退耕的同时，高度重视已退耕区域的生态保护和植被恢复，生境质量日益好转；但受耕地后备资源开发、农田整治等工作影响，部分区域的生境质量略微下降。

表72000—2020年渭河流域生境质量变化面积及占比Tab.7 Change area and proportion of habitat quality inWeiheRiver Basin from 20oo to 2020  

<html><body><table><tr><td rowspan="2">生境质量 变化情况</td><td colspan="2">2000—2010年</td><td colspan="2">2010—2020年</td></tr><tr><td>面积/km²</td><td>占比/%</td><td>面积/km²</td><td>占比/%</td></tr><tr><td>明显改善</td><td>3814.37</td><td>2.84</td><td>8275.41</td><td>6.17</td></tr><tr><td>微幅上涨</td><td>31081.59</td><td>23.16</td><td>32676.06</td><td>24.35</td></tr><tr><td>保持稳定</td><td>72401.19</td><td>53.94</td><td>69205.00</td><td>51.56</td></tr><tr><td>轻微下降</td><td>24096.28</td><td>17.95</td><td>15960.28</td><td>11.89</td></tr><tr><td>退化严重</td><td>2823.54</td><td>2.10</td><td>8100.23</td><td>6.04</td></tr></table></body></html>

# 3.4生境质量模拟

基于土地利用预测结果，利用InVEST模型处理得到2030—2050年渭河流域生境质量等级分布（图8)。2030—2050年生境质量空间格局相对稳定，生境质量总体水平不断上升但增长幅度逐渐减缓，2030、2040年和2050年生境质量平均分值分别为0.6237、0.6251和0.6265，相较于2020年提升0.0033。

![](images/a041a6071ba9a2613292941b8499355bfca84dbdb8237cccfe330af0901b336b.jpg)  
图72000—2020年渭河流域生境质量空间变化  
图82030—2050年渭河流域生境质量空间分布预测  
Fig.8Spatial distribution prediction of habitat quality in Weihe River Basin from 2O30 to 2050

2030一2050年各生境质量等级面积变化幅度降低(图9)。低生境质量区域在2030—2050年内面积持续减少，但减少幅度逐渐下降，30a面积减少$9 1 5 . 9 9 ~ \mathrm { k m } ^ { 2 }$ ,占比降至 $4 0 . 9 8 \%$ 。较低生境质量区域扩张趋势也得以转变，变化剧烈程度显著下降，2030一2050年面积先增后减，总体面积减少138.72$ { \mathrm { k m } } ^ { 2 }$ 。中等生境质量区域面积继续保持微幅增长趋势，面积微弱上涨 $3 8 . 0 1 \ \mathrm { k m } ^ { 2 }$ 。较高生境质量区域面积增加 $1 0 2 6 . 9 7 { \mathrm { ~ k m } } ^ { 2 }$ ,但增长幅度放缓。高生境质量区域面积减少 $1 0 . 2 7 \mathrm { k m } ^ { 2 }$ ,变化微弱。

![](images/92531d16f0ac5f198e27c2d1ea640fda5733a689177bec9f3ab68c1cd5e29ee5.jpg)  
图92030—2050年渭河流域生境质量面积Fig.9Habitat quality area ofWeihe River Basinfrom 2030 to 2050

# 4讨论

# 4.1土地利用变化原因

渭河流域土地利用变化是诸多因素共同作用的结果。从土地利用变化分析来看，耕地面积持续减少，这与我国推行的退耕还林还草政策密切相关；另外各城市经济社会的快速发展对建设用地的需求明显上升，大量城郊耕地被占用，该现象在自然和区位条件较好的平原地区极为突出；同时值得注意是，脱贫攻坚时期积极的土地政策拓宽了补充耕地的渠道，耕地减少趋势有所减缓。林地和草地作为重要的生态用地，对流域内生态脆弱区的水土流失、土地沙化治理具有重要作用，在退耕还林还草政策积极施行的同时，政府通过设立自然保护区和森林公园、引导发展生态经济等举措推动着对林地和草地资源的合理开发与保护，草地和林地面积有所上升。随着建设用地节约集约利用意识的提升以及空间规划的刚性约束，以及地方政府推动着对废弃、闲置建设用地的二次开发与利用，建设用地扩张速度得以有效控制。水域对维护区域水生态平衡意义重大，在地方政府开展河道、滩区治理并建立河长制等措施下，形成了以渭河湿地走廊、泾河湿地公园为代表的各类水域湿地，有效保障了水域面积。

# 4.2生境质量变化原因

渭河流域生境质量与土地利用格局密切相关。生境质量水平的不断提高得益于渭河流域秦岭、六盘山等地高覆盖度的林地支撑和近些年积极开展的生态退耕、封山育林、种草固沙等重大生态修复及治理措施。流域南端的秦岭地区作为我国重要的生态安全屏障，生境质量水平较高且比较稳定；流域西部、北部的黄土高原丘陵沟壑区作为生态治理和修复的重点对象，生态环境日益好转，生境质量逐渐提升；而中间海拔较低、区位优越的平原地带，是我国关中一天水经济区的位置所在，城市数量众多且经济发展速度较快，区域人为扰动剧烈，生境质量水平较差，这是导致流域生境质量空间格局呈现两边高中间低、西部高东部低的主要原因。流域中部平原地区社会经济的发展和城市规模的扩张推动着用地类型的转变，其中建设用地的发展导致了低生境质量区域面积的上涨；但整体来看，在生态补偿策略和生态治理措施推动下，西部、北部的耕地向高生态适宜度的草地、林地转化，生态环境逐渐好转，生境质量总体呈上升趋势。

# 4.3对策建议及展望

渭河流域作为我国西部大开发的战略节点，在统筹推进社会经济发展和地区生态环境建设等方面具有重要意义，从土地利用和生境质量变化的分析来看，还存在一些需要关注的问题。在土地利用上，建设用地扩张占用优质耕地和城市发展不均衡问题突出，需要进一步推行节约集约的用地政策和挖掘现有建设用地内涵，明确城市定位和分工，科学引导城市扩张和区域协调发展。在生境质量上，经济发展水平较高且人口集中的平原地区生境质量水平较差且退化趋势严重，需要引起高度重视，可通过建设生态景观廊道、增加城市绿化面积等改善生境质量。

从预测结果来看，2020—2050年渭河流域土地

# 干吴区地理

利用变化趋势稳定，生境质量水平稳定上升。结合《黄河流域生态保护和高质量发展规划纲要》《陕西省秦岭生态环境保护条例》等政策来看，生态环境治理和保护依旧是渭河流域实现可持续发展的时代主题。继续推进流域内黄土高原丘陵沟壑区、秦岭南麓和子午岭等地区的生态治理和保护，在筑牢生态本底和增强生态屏障质量效能上的同时，为构建西部大开发新格局、“一带一路"经济带及乡村振兴提供良好的生态安全保障。

本研究在分析渭河流域土地利用及生境质量现状的基础上，综合利用PLUS模型和InVEST模型预测未来土地利用和生境质量时空格局，为渭河流域生态环境保护和可持续发展提供依据和参考。同时，研究过程为渭河流域生态环境持续向好的形势提供了有力证据，流域内生态脆弱区、秦岭水土涵养区生境质量发展向好，与前人研究结论高度契合[28]。但由于土地利用变化受多种因素影响,一些影响因子由于受数据获取难度大、难以计量的原因未被考虑在内，未来将继续深化研究以提高PLUS模型预测精度。另外，在利用InVEST模型进行生境质量测算时，缺乏科学准确、统一的参数设置体系，在接下来的工作中可重点探究优化参数设置的有效途径。

# 5结论

（1）2000一2020年渭河流域建设用地和草地面积逐年增加，林地面积略微增长，耕地面积持续减少。建设用地发展迅速,20a面积增加接近一倍。耕地流失严重，主要向草地和建设用地转化。林地面积先增后减但总体呈增长趋势，减少部分主要转变为草地。

(2）PLUS模型预测结果表明,2020—2050年土地利用变化情况同2000—2020年基本一致，但土地利用变化剧烈程度明显降低。建设用地扩张趋势有所减缓，耕地减少幅度下降，草地面积持续增长，面积占比超过耕地跃居第一。

（3）生境质量计算结果表明，2000—2020年流域内生境质量两极分化趋势明显，低生境质量和高生境质量区域面积有所增加，中等生境质量的面积减少，整体生境质量水平呈上升趋势。从生境质量变化来看，生境质量上升区域主要集中在西部和北部的黄土高原丘陵沟壑区，生境质量下降区域则集

聚在西安都市圈周围。

（4）2020—2050年生境质量水平逐年上升但增幅放缓，生境质量变化强度下降，生境质量空间格局变化微弱。低生境质量区域面积逐渐减少，中等生境质量面积保持稳定，高生境质量面积有所增长。

# 参考文献(References)

[1]万炜,魏伟,钱大文,等.土地利用/覆被变化的环境效应研究进 展[J].福建农林大学学报(自然科学版),2017,46(4):361-372. [Wan Wei,Wei Wei, Qian Dawen,etal.Progress on the environmental effects of land use and land cover change[J]. Journal of Fujian Agriculture and Forestry University (Natural Science Edition),   
2017,46(4): 361-372.] [2]李亚丽,杨粉莉,杨联安,等.近40a榆林市土地利用空间格局 变化及影响因素分析[J].干旱区地理,2021,44(4):1011-1021. [Li Yali, Yang Fenli, Yang Lian'an, et al. Spatial patern changes and influencing factors of land use in Yulin City in the past 40 years[J]. Arid Land Geography,2021,44(4): 1011-1021.] [3]刘春芳,王川.基于土地利用变化的黄土丘陵区生境质量时空 演变特征—以榆中县为例[J].生态学报,2018,38(20):7300-   
7311.[Liu Chunfang,Wang Chuan. Spatio-temporal evolution characteristics of habitat quality in the Loess Hilly Region based on land use change: A case study in Yuzhong County[J]. Acta Ecologica Sinica,2018,38(20): 7300-7311.] [4]Hall L S, Krausman PR, Morrison M L. The habita concept and a plea for standard terminology[J].Wildlife Society Bulletin,1997,   
25(1): 173-182. [5]欧阳志云,郑华.生态系统服务的生态学机制研究进展[J].生态 学报,2009,29(1): 6183-6188.[Ouyang Zhiyun, Zheng Hua. Ecological mechanisms of ecosystem services[J]. Acta Ecologica Sinica,2009,29(11): 6183-6188.] [6]杨志鹏,许嘉巍,冯兴华,等.基于InVEST模型的东北地区土地 利用变化对生境的影响研究[J].生态科学,2018,37(6):139-   
147.[Yang Zhipeng,Xu Jiawei,Feng Xinghua,et al.Effects of land use change on habitat based on InVEST model in northeast China[J]. Ecological Science,2018,37(6): 139-147.] [7]王军,严有龙,王金满,等.闽江流域生境质量时空演变特征与 预测研究[J].生态学报,2021,41(14):5837-5848.[Wang Jun, Yan Youlong,Wang Jinman,et al.Temporal-spatial variation characteristics and prediction of habitat quality in Min River Basin[J]. Acta Ecologica Sinica,2021,41(14): 5837-5848.] [8]褚琳,张欣然,王天巍,等.基于CA-Markov 和InVEST模型的城 市景观格局与生境质量时空演变及预测[JJ.应用生态学报,   
2018,29(12): 4106-4118.[Chu Lin, Zhang Xinran,Wang Tianwei,et al. Spatial-temporal evolution and prediction of urban landscape pattern and habitat quality based on CA-Markov and InVEST model[J]. Chinese Journal of Applied Ecology，2018,29 (12): 4106-4118.]

[9]Dessel WV,RompaeyAV,SzilassiP.Sensitivityanalysis of logis tic regression parameterization for land use and land cover probability estimation[J]. International Journal of Geographical Information Science,2011,25(3): 489-508.

[10]Verburg P H, Soepboer W,Veldkamp A,et al. Modeling the spatial dynamics of regional land use: The CLUE-S model[J]. Environmental Management,2002,30(3): 391-405.   
[11]Liu X, Liang X, Li X,et al. A future land use simulation model (FLUS) for simulating multiple land use scenarios by coupling human and natural effects[J]. Landscape and Urban Planning, 2017, 168: 94-116.   
[12]Liang X,Guan Q, Clarke K C,et al. Understanding the drivers of sustainable land expansion using a patch-generating land use simulation (PLUS) model: A case study in Wuhan,China[J]. Computers,Environment and Urban Systems,Pergamon,2021,85:101569, doi: 10.1016/j.compenvurbsys.2020.101569.   
[13]喇露梦,勾蒙蒙,李乐,等.三峡库区生态系统服务权衡时空动 态与情景模拟——以秭归县为例[J].生态与农村环境学报, 2021,37(11): 1368-1377.[La Lumeng,Gou Mengmeng,Li Le,et al. Spatiotemporal dynamics and scenarios analysis on trade-offs between ecosystem service in Three Gorges Reservoir Area: A case study of Zigui County[J].Journal of Ecology and Rural Environment,2021,37(11): 1368-1377.]   
[14] 李琛,高彬嫔,吴映梅,等.基于PLUS模型的山区城镇景观生 态风险动态模拟[J].浙江农林大学学报,2022,39(1):84-94. [Li Chen,Gao Binpin,Wu Yingmei,et al.Dynamic simulation of landscape ecological risk in mountain towns based on PLUS model [J]. Journal of Zhejiang A& FUniversity,2022,39(1): 84-94.]   
[15]Li C,Wu Y,Gao B,et al. Multi-scenario simulation of ecosystem service value for optimization of land use in the Sichuan- Yunnan ecological barrier,China[J].Ecological Indicators,2O21,132: 108328,doi: 10.1016/j.ecolind.2021.108328.   
[16] 陆羽,黄秋昊,赵琪琪,等.基于InVEST与CARS 的生态空间分 区与未来预测研究[J].地理信息世界,2021,28(3):15-19.[Lu Yu,Huang Qiuhao, Zhao Qiqi,et al. Research on ecological spatial division and future prediction based on InVESTand CARS[J]. Geomatics World,2021,28(3): 15-19.]   
[17] 吴健生,曹祺文,石淑芹,等.基于土地利用变化的京津冀生境 质量时空演变[J].应用生态学报,2015,26(11):3457-3466. [Wu Jiansheng, Cao Qiwen, Shi Shuqin,et al. Spatiotemporal variability of habitat quality in Beijing-Tianjin-Hebei area based on land use change[J]. Chinese Journal of Applied Ecology,2015,26 (11): 3457-3466.]   
[18] 刘孟竹,张红娟,王彦芳,等.基于土地利用的北方农牧交错带 生境质量研究[J].水土保持研究,2021,28(3):156-162.[Liu Mengzhu, Zhang Hongjuan,Wang Yanfang,et al. Characteristics of habitat quality in the agro- pastoral ecotone of northern China based on land uses[J]. Research of Soil and Water Conservation, 2021,28(3): 156-162.]   
[19]Bhagabati N K, Ricketts T, Sulistyawan TB S,et al. Ecosystem services reinforce Sumatran tiger conservation in land use plans [J]. Biological Conservation,2014,169: 147-156.   
[20] 冯舒,孙然好,陈利顶.基于土地利用格局变化的北京市生境质 量时空演变研究[J].生态学报,2018,38(12):4167-4179.[Feng Shu, Sun Ranhao, Chen Liding.Spatio-temporal variability of habitat quality based on land use patern change in Beijing[J]. Acta Ecologica Sinica, 2018,38(12): 4167-4179.]   
[21] 黄木易,岳文泽,冯少茹,等.基于InVEST模型的皖西大别山区 生境质量时空演化及景观格局分析[J].生态学报,2020,40(9): 2895-2906.[Huang Muyi, Yue Wenze,Feng Shaoru,et al.Spatialtemporal evolution of habitat quality and analysis of landscape patterns in Dabie Mountain area of west Anhui Province based on InVEST model[J].Acta Ecologica Sinica,2020,40(9): 2895-2906.]   
[22] 冯琰玮,甄江红,马晨阳.呼和浩特市生境质量对城市用地扩展 的时空响应[J].干旱区地理,2020,43(4):1014-1022.[Feng Yanwei, Zhen Jianghong,Ma Chenyang. Spatiotemporal response of habitatqualitytourban expansion in HohhotCity[J].AridLand Geography,2020,43(4): 1014-1022.]   
[23] 庞家泰,段金亮,张瑞,等.2000—2019年渭河流域植被覆盖度 时空演变特征及气候响应[J].水土保持研究,2021,28(5):230- 237.[Pang Jiatai,Duan Jinliang,Zhang Rui,et al. Characteristics of spatiotemporal evolution and climate response of vegetation cover in the Wei River Basin from 20OO to 2O19[J].Research of Soil and Water Conservation, 2021,28(5): 230-237.]   
[24] 张大川,刘小平,姚尧,等.基于随机森林CA的东莞市多类土 地利用变化模拟[J].地理与地理信息科学,2016,32(5):29-36. [Zhang Dachuan,Liu Xiaoping,Yao Yao,et al. Simulating spatiotemporal change of multiple land use types in Dongguan by using random forest based on Cellular Automata[J]. Geography and GeoInformation Science,2016,32(5): 29-36.]   
[25] 陈凯,刘凯,柳林,等.基于随机森林的元胞自动机城市扩展模 拟——以佛山市为例[J].地理科学进展,2015,34(8):937-946. [Chen Kai,Liu Kai,Liu Lin,etal. Urban expansion simulation by random-forest-based cellular automata: A case study of Foshan City [J]. Progress in Geography,2015,34(8): 937-946.]   
[26] 王旭,马伯文,李丹,等.基于FLUS 模型的湖北省生态空间多 情景模拟预测[J].自然资源学报,2020,35(1):230-242.[Wang Xu, Ma Bowen,Li Dan, et al. Multi-scenario simulationand prediction of ecological space in Hubei Province based on FLUS model[J]. JournalofNaturalResources,2020,35(1): 23-242.]   
[27] Liang X,Liu XP,Li D,et al. Urban growth simulation byincorporating planning policies into a CA-based future land-use simulation model[J]. International Journal of Geographical Information Science,2018,32(11): 2294-2316.   
[28] 张学儒,周杰,李梦梅.基于土地利用格局重建的区域生境质量 时空变化分析[J].地理学报,2020,75(1):160-178.[Zhang Xueru, Zhou Jie,Li Mengmei. Analysis on spatial and temporal changes of regional habitat quality based on the spatial pattern reconstruction of land use[J].Acta Geographica Sinica,2020,75(1):160- 178.]

# 干吴区地理

[29] 刘春艳,朱康文,刘吉平.三峡库区重庆段土地覆盖和生物多样 性功能演化及预测[J].农业工程学报,2017,33(19):258-267. [Liu Chunyan, Zhu Kangwen,Liu Jiping. Evolution and prediction of land cover and biodiversity function in Chongqing section of Three Gorges Reservoir area[J]. Transactions of the Chinese Society of Agricultural Engineering,2017,33(19): 258-267.]

[30]许宝荣,刘一川,董莹,等.基于InVEST模型的兰州地区生境质量评价[J].中国沙漠,2021,41(5):120-129.[Xu Baorong,Liu

Yichuan,Dong Ying,et al. Evaluation of habitat quality in Lanzhou region based on InVEST model[J]. Journal of Desert Research,2021,41(5): 120-129.]

[31]Sharp R,Tallis HT,Ricketts T,et al. InVEST 3.2.O user's guide. The natural capital project,stanford university,University of Minnesota,The Nature Conservancy,and World Wildlife Fund[EB/ OL]. [2017-10-8]. https://naturalcapitalproject.stanford.edu/software/invest.

# Spatial and temporal changes in land use and habitat quality in the Weihe River Basin based on the PLUS and InVEST models and predictions

HU Feng'， ZHANG Yan²， GUO $\mathrm { Y u } ^ { 1 }$ ，ZHANG Panpan', LYU Shuai'， ZHANG Changchun' (1.Department of Land and Resources,Hebei Agricultural University,Baoding O71Ooo,Heibei, China; 2.Department of Land Engineering,Chang'an University,Xi'an 71Oooo,Shaanxi, China)

Abstract: Habitat quality is an important foundation for human well-being and sustainable development.It is of great significance for regional ecological conservation and sustainable land resource use.Therefore,this paper explores the changes in the spatial paterns of habitat quality in the Weihe River Basin,northwest China from the perspective of land-use change by analyzing three periods of land use data from 20o0 to 2020 and coupling the PLUS and InVEST models to predict and evaluate future land use and habitat quality.In our analysis,we found that from 2Oo0 to 2O20,the areas of construction land and grassland in the Weihe River Basin increased year by year,the area of forest land rose slightly,and the area of cultivated land continuously decreased.However, we predict that the drastic land-use changes in the Weihe River Basin willdecrease significantly and land-use changes will stabilize from 2020 to 2050.In addition,we further explored the spatial distribution and changes in habitat qualityin the basin on the basis of the analysis of land-use changes.We found that the overallevel of habitat qualityin the basin was moderately high from 2000 to 2O20,with a clear trend of habitat quality polarization, gradually increasing areas of low and high habitat quality,and gradually decreasing areas of moderate habitat quality.However,the overalllevel of habitat quality in the basin gradually increased,consistent with the increasing ecological improvement in the Weihe River Basin in recent years.From 2020 to 2050,the overall habitat quality in the basin will continue to increase,but the growth rate willslow down and the intensityof habitat quality changes willdecrease.After analyzing land use and habitat quality,we explored the main reasons for their change. We found that regional ecological compensation policies and socioeconomic development were the main reasons for land-use changes.Meanwhile,habitat quality was closely related to the spatial patern of land use, with higher and more stable habitat quality levels in areas with high concentrations of forested land and low disturbance of human activities,whereas the habitat quality tended to be poorer in plain areas where human activities are more intensive and urban development is more concentrated.However, it is worth acknowledging that the management and restoration of the ecologically fragile areas of the Loess Plateau in the watershed have led to a gradual improvement in habitat management，which is also an important reason for the overall improvement in the habitat quality in the watershed as a whole.

Key Words:land use；habitat quality；patch-generating land use simulation model； integrated valuation of ecosystem services and trade-offs model; Weihe River Basin