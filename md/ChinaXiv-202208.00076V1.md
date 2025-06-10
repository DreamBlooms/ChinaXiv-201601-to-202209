# 基于贝叶斯网络的生态系统服务空间格局优化以泾河流域为例

余玉洋²，李晶¹，周自翔³，唐承延（1.陕西师范大学地理科学与旅游学院,陕西 西安710119；2.河南师范大学旅游学院,河南 新乡453007;3.西安科技大学测绘科学与技术学院，陕西 西安710054)

摘要：城市高速发展引起了区域土地利用格局的改变，不仅影响生态环境质量，而且还对生态系统服务的空间格局产生影响，在此基础上优化生态系统服务显得至关重要。在泾河流域2000—2020年净初级生产力（Net primary productivity,NPP）、农业生产力、土壤保持和产水服务空间评估的基础上，将贝叶斯网络和生态系统服务相结合，在关键变量子集和可视化的最优状态子集的基础上，评估了4种生态系统服务需要优化的区域，为区域经济和生态和谐发展提供参考。结果表明：(1）水文评价模型(Soil and water assessment tool,SWAT)模型能较准确地模拟区域的径流量。通过模拟值和观测值对比分析，该模型具有较高的决定性系数！ $\left( R ^ { 2 } { > } 0 . 6 \right)$ 和纳什效率系数（NSE>0.5),可为进一步评估产水服务提供保障。(2)2000—2020年泾河流域4种生态系统服务的时空差异性较为显著。在时间尺度上，4种生态系统服务均呈现波动中上升的趋势，在空间尺度上呈现较为稳定的变化趋势。(3)通过对4种生态系统服务优化区域进行叠加分析，发现综合优化区域集中在彭阳县的中部和西南部以及环县的零星区域。研究结果对指导优化区域进行生态系统的可持续管理以及改善生态系统的退化状况具有重要意义。

关键词：生态系统服务；贝叶斯网络；时空格局优化；泾河流域

# 文章编号：

生态系统服务是指人们从生态系统中获得的所有受益，包括直接和间接受益[1-2]。由于生态系统服务与人类的生命和生存密切相关，因此研究生态系统服务对于人类的生存和地球发展都非常重要[3-6]。随着科学技术水平的提升,越来越多的学者对生态系统服务研究集中于供需关系、空间权衡与优化、生态福祉、服务流等方面[7-12]。其中生态系统服务空间格局优化受到越来越多的学者关注，学者们开始尝试运用不同模型与方法进行深入探究，但是由于研究时限不长，所以促使该方面研究处于萌芽时期[13-15]。目前多数空间优化研究是以土地利用空间格局为支撑，其目的是实现一定规模的需求和规划的目标[16]。刘慧灵等[17]通过单位面积上不同土地利用的生态系统服务价值来作为变量系数，建立生态效益函数，进而对土地利用进行空间优化;王观湧等[18]、向芸芸等[19]通过土壤有机碳的最大储量为目标，确定生态效益函数，最终达到优化土地利用的目的。李秀霞等2通过设置经济和生态的双重目标，利用系统动力学模型和多目标优化模型，对吉林省的土地利用进行仿真模拟和优化。上述研究大多数是对土地利用进行空间优化，然后在以优化的土地利用为基础，进行生态系统服务的空间制图和分析，不仅忽略影响生态系统服务的其他影响因素，而且没有真正意义上实现生态系统服务的空间优化，即在研究区范围内，如何合理和优化配置自然因素和土地利用等因素，使该区域的生态系统服务能力最强，如何选取不同生态系统服务的影响因素以及量化关键因子对生态系统服务的影响程度，从而达到优化区域生态系统服务的目的，正是该研究所解决的问题。

贝叶斯网络是一种大规模的数据分析工具，具有强大的逻辑分析能力。该网络采用图形化建模的方法，将变量之间的相互作用以网络的形式表达出来，并构建一个系统概率模型[21],将贝叶斯网络和生态系统服务相结合，可以很好地为生态系统服务的优化管理提供决策支持[22]。Fox等[23]研究了贝叶斯网络在水质和自然资源管理中的价值;Landuyt等[24]利用贝叶斯网络评估池塘综合管理的机会和风险；Dang等[25]将生态系统服务和自然环境因子纳入贝叶斯网络模型，通过不同指标设置不同的研究情景，为农业发展提供概率支持。综上看出贝叶斯网络可以很好地和生态系统服务相结合，从而来实现研究目标。

泾河流域位于黄土高原中部，在六盘山和子午岭之间，对于此区域的研究大多集中在生态和自然环境方面。Chen等[26]使用主成分分析和相关分析来分析泾河流域的归一化植被指数(Normalizeddif-ferencevegetationindex,NDVI)和降水量，发现植被的动态变化与气候变化、洪水和人类活动密切相关;Xie等[27]分析了降水-景观-径流变化和相互作用；Guo等28使用滑动偏相关系数法分析降雨和径流关系的变化，并使用双累积曲线法验证其分析；甄霖等[29]通过参与式社区评估法对泾河流域景观管理中存在的相关问题进行深入剖析。从现有研究中看出对于泾河流域生态系统服务的研究还处在初级阶段，并且随着社会经济的快速发展，土地利用格局发生很显著的变化，最终也会导致生态系统服务的格局发生变化，如何通过现有的土地利用格局来优化生态系统服务也显得至关重要，因此，深入研究泾河流域生态系统服务以及空间格局优化会对区域的生态-经济和谐发展奠定基础。本文在生态系统服务空间评价的基础上，引人贝叶斯网络模型，通过筛选关键因子和最优状态子集的方式，来获取4种生态系统服务的空间优化区域，为区域生态健康持续发展奠定基础。

# 1数据与方法

麓，自西北向东南流经固原市、平凉市、庆阳市、咸阳市等38个县市，于咸阳市高陵县陈家滩村汇入渭河。泾河流域地理位置介于 $1 0 6 ^ { \circ } 1 4 ^ { \prime } { \sim } 1 0 8 ^ { \circ } 4 2 ^ { \prime } \mathrm { E } .$ $3 4 ^ { \circ } 4 6 ^ { \prime } { \sim } 3 7 ^ { \circ } 1 9 ^ { \prime } \mathrm { N }$ 之间，地跨陕西省、甘肃省、宁夏回族自治区(图1)，流域面积达 $4 5 4 2 1 ~ \mathrm { k m } ^ { 2 }$ 。区域多年平均气温 $8 \mathrm { { ^ \circ C } }$ ,年降水量 $3 5 0 { \sim } 6 5 0 ~ \mathrm { m m }$ ，降水主要集中在夏季。泾河流域地势较为平坦,耕地面积约占1/3，农业发达；矿藏量较为丰富，经济开发潜力大。泾河流域内黄土高原区域和泾惠渠灌区域，是陕西省主要商品粮油基地。除此之外，还有煤炭、石油、天然气、建筑材料等矿产，如长庆油田。但长期过度开发利用和气候变迁，导致流域内生态环境十分脆弱，其中水资源缺乏已成为研究区社会经济以及生态发展的主要制约因素。

# 1.2数据来源

本文主要数据包括遥感数据(土地利用数据)和非遥感数据(地理基础数据、高程数据、气象数据、土壤类型数据和水文数据等），具体信息见表1所示。

# 1.3生态系统服务模型

1.3.1农业生产力服务模拟首先，从2000—2020年地表覆盖数据中获取耕地资源数据作为计算区

# 1.1 研究区概况

泾河发源于泾源县泾源乡，源区地处六盘山东

![](images/ebb364810b57a133510fd203c8483bef52daa4337b83c99456f36c7b58e9bc39.jpg)  
图1研究区概况  
Fig.1 Overview of the study area

# 干旱区地理

# 表1数据来源

Tab.1 Data sources   

<html><body><table><tr><td>数据类型</td><td>数据描述</td><td>数据来源</td></tr><tr><td>基础地理信息数据</td><td>行政区划、河流、道路等</td><td>国家基础地理信息中心(http://www.ngcc.cn/ngcc/)</td></tr><tr><td>高程数据</td><td>来源于地理空间数据云,空间分辨率为30m</td><td>地理空间数据云(http://www.gscloud.cn/)</td></tr><tr><td>土壤数据</td><td>第二次全国土地调查南京土壤研究所提供的1:100000土 壤数据,空间分辨率为1km×1km</td><td>国家青藏高原科学数据中心(https://data.tpdc.ac.cn/zh- hans/)</td></tr><tr><td>土地利用数据</td><td>来源于GlobalLand 30,全球地理信息公共产品,空间分辨 率为30m</td><td>全球地理信息公共产品(http://www.globallandcover. com/)</td></tr><tr><td>气象数据</td><td>2000—2020年逐日数据,指标包括降水量、最高气温、最 低气温、风速、相对湿度数据</td><td>国家气象科学数据中心(http://data.cma.cn/)</td></tr><tr><td>水文数据</td><td>2000—2020年张家山水文站逐日径流数据</td><td>张家山水文站(http://61.163.88.227:8006/hwsq.aspx)</td></tr><tr><td>统计数据</td><td>2000—2020年人口密度以及GDP等统计数据</td><td>统计年鉴</td></tr></table></body></html>

域农业生产潜力的基础；其次是基于气象站点数据，通过ANUSPLIN软件获取2000—2020平均气温和年降水量数据；最后，采用桑斯维特纪念模型[30]，计算区域2000一2020年农业生产力，公式如下：

$$
\mathrm { C P } { = } \mathrm { P v } \times I _ { \mathrm { { z r d } } }
$$

式中：CP为以耕地为基础的农作物生产力 $\left( \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } \right)$ ;$\mathrm { P v }$ 为以年平均蒸散量为自变量计算出的植物干物质总量 $\left( \mathbf { g } \cdot \mathbf { m } ^ { - 2 } \cdot \mathbf { a } ^ { - 1 } \right)$ · $I _ { \mathrm { z r d } }$ 为土地利用水平，是由中国农用地分级规定决定的[31]。 $\mathrm { P v }$ 的计算公式如下：

$$
\mathrm { P v } = 3 0 0 0 0 \times [ 1 - \mathrm { e } ^ { - 0 . 0 0 0 9 6 9 5 \times ( v - 2 0 ) } ]
$$

$$
v = { \frac { 1 . 0 5 p } { \sqrt { 1 + ( 1 . 0 5 p / l ) ^ { 2 } } } }
$$

$$
l = 3 0 0 + 2 5 t + 0 . 0 5 t ^ { 3 }
$$

式中： $\mathbf { \sigma } _ { v }$ 为年平均实际蒸散量 $( \mathbf { m } \mathbf { m }$ ； $p$ 为年降水量$\left( \mathrm { m m } \right)$ ;为年平均最大蒸散量 $\left( \mathbf { m } \mathbf { m } \right) ; t$ 为年平均气温$( \mathcal { C } )$ 。

1.3.2产水服务模拟水文评价模型(Soiland wa-terassessmenttool,SWAT)可以对流域内一系列复杂的物理过程进行模拟，模型中的水量平衡始终是流域内所有过程的驱动力[32]。并且此模型可以基于水量平衡模拟每个水文响应单元的地表径流量和洪峰流量，水量平衡方程如下[33]：

$$
\mathrm { S W } _ { t } = \mathrm { S W } _ { \mathrm { 0 } } + \sum _ { i = 1 } ^ { i } \bigl ( R _ { \mathrm { d a y } } - Q _ { \mathrm { s u r f } } - E _ { \mathrm { a } } - W _ { \mathrm { s e e p } } - Q _ { \mathrm { g y } } \bigr )
$$

式中： $\mathrm { S W } _ { t }$ 为最终土壤含水量 $( \mathbf { m } \mathbf { m } ) : t$ 为时间天数；$\mathrm { S W } _ { 0 }$ 为第 $i$ 天的初始土壤含水量( $\bf \Pi _ { \mathrm { m m } }$ ） $R _ { \mathrm { d a y } }$ 为第 $i$ 天的降水量( $( \mathbf { \bar { \rho } } _ { \mathrm { m m } } )$ ; $Q _ { \mathrm { s u r f } }$ 为第 $i$ 天的地表径流量 $\left( \mathrm { m m } \right) ; E _ { \mathrm { a } }$ 为第 $i$ 天的蒸散发 $( \mathrm { m m }$ ）； $W _ { \mathrm { s e p } }$ 为第 $i$ 天通过土壤剖面进入包气带的水量 $( \mathrm { m m }$ ； $Q _ { \mathrm { g y } }$ 为第 $i$ 天的回归流量（20 $\left( \mathrm { m m } \right)$ 。

1.3.3净初级生产力(NPP)服务模拟参考朱文泉等[34]的遥感估算模型(Carnegie-ames-stanford ap-proach,CASA)计算植被NPP,由植物的光合有效辐射（Absorbed photosynthetic active radiation,APAR）和实际光能利用率 ${ \bf \Xi } ( { \bf \Lambda } _ { \varepsilon } ) { \bf \Lambda } _ { 2 }$ 个因子表示[35]。计算公式如下：

$$
\mathrm { N P P } ( x , t ) = \mathrm { A P A R } ( x , t ) \times \varepsilon ( x , t )
$$

式中： $\mathrm { N P P } ( x , t )$ 为像元 $x$ 在 $\mathbf { \Phi } _ { t }$ 月内所得到的植被净初级生产力( $\cdot \bf { g } C \cdot \bf { m } ^ { - 2 } ,$ ; $\mathrm { A P A R } ( x , t )$ 为像元 $x$ 在 $\mathbf { \Phi } _ { t }$ 月吸收的光合有效辐射 $( \mathrm { M J } \cdot \mathrm { m } ^ { - 2 }$ ； $\boldsymbol { \varepsilon } ( \boldsymbol { x } , t )$ 为像元 $x$ 在 $\mathbf { \Phi } _ { t }$ 月的实际光能利用率( $\cdot \bf { g } \cdot \bf { C } \cdot \bf { M } J ^ { - 1 }$ ）。

1.3.4土壤保持服务模拟采用通用土壤流失方程估算土壤保持量,20世纪50年代由Wischmeier等[36]提出，基于理论以及大量实地观测数据统计分析的基础上，对各因子都有具体解释。通用土壤流失方程的表达如下：

$$
A = R \times K \times L \times S \times ( 1 - C \times P )
$$

式中： $\ O _ { ; A }$ 为土壤保持量( $\mathrm { \Omega } _ { \mathrm { t } } { \cdot } \mathrm { h m } ^ { - 2 }$ ； $R$ 为降雨侵蚀力因子$\left( \mathrm { M J } \cdot \mathrm { m m } \cdot \mathrm { h m } ^ { - 2 } \cdot \mathrm { h } ^ { - 1 } \cdot \mathrm { a } ^ { - 1 } \right) ; K$ 为土壤可蚀性因子 $( \cdot \cdot \mathrm { h }$ $\mathbf { M J } ^ { - 1 } { \cdot } \mathbf { m m } ^ { - 1 }$ ； $L$ 和 $s$ 分别为坡长和坡度因子； $C$ 为地表植被覆盖及经营管理因子； $P$ 为水土保持措施因子。

# 1.4基于BBNs的农田生态系统服务空间格局优化

1.4.1贝叶斯网络模型贝叶斯网络又称信度网络，是Bayes方法的扩展，目前不确定知识表达和推理领域最有效的理论模型之一[37]。1988年Pearl提出后，已经成为近几年来研究的热点。一个贝叶斯网络是一个有向无环图(DAG)，由代表变量节点及连接这些节点有向边构成[38]

其中条件概率表(CPT)表达了父节点 $X$ 与子节点Y之间的关系强度，表中每一行由父节点的状态组合和条件概率 $P ( y | x )$ 组成,即父节点 $X$ 在离散状态$x$ 下，子节点对应状态 $y$ 发生的概率。子节点的概率分布由父节点的概率分布及条件概率表决定，对于没有父节点的节点，其概率分布为先验概率分布 $P$ $( X )$ 。所有节点的条件概率分布相乘得到贝叶斯网络中所有变量的联合概率[式(8)」。贝叶斯网络能够有效计算网络中任意节点概率分布的基础，为本文优化生态系统服务格局提供了理论[39-40]。

$$
P ( X _ { 1 } , X _ { 2 } , \cdots , X _ { n } ) { = } \prod _ { i = 1 } ^ { n } P \big [ X _ { i } | \mathrm { p a r e n t s } ( X _ { i } ) \big ]
$$

式中： $P ( X _ { 1 } , X _ { 2 } , \cdots , X _ { n } )$ 为一个联合离散概率分布，这种分布的随机变量具有 $1 , 2 , \cdots , n$ 个离散值; $n$ 为随机变量的最大值; $( X _ { 1 } , X _ { 2 } , \cdots , X _ { n } )$ 为随机变量。

以4种生态系统服务量化模型为依据，选择与其相关的影响因子作为节点，构建生态系统服务的贝叶斯概念网络(图2)。借助ArcGIS软件，离散节点对应的栅格图层，根据变量的实际分布情况，参考学者对贝叶斯网络栅格分层的方法[9.22],运用Arc-GIS软件的自然间断法将上述每个变量栅格数据分为4个等级：最高、高、中、低，具体离散化分级标准如表2所示。提取离散数据值到属性表并将概率条件输入贝叶斯网络模型，便可得到泾河流域生态系统服务的贝叶斯网络。其他节点的条件概率表可由条件概率公式[式(9）计算获得。

$$
P \big ( \mathrm { B } | \mathrm { A } \big ) { = } P \big ( \mathrm { A B } \big ) / P \big ( \mathrm { A } \big )
$$

式中： $P ( \mathrm { A B } )$ 为事件A与B的联合概率，即2个事件共同发生的概率； $P ( \mathrm { A } )$ 为A的先验概率，即事件A发生的概率;同理， $P ( { \bf B } )$ 为事件B发生的概率。

1.4.2农田生态系统服务格局优化构建出泾河流域生态系统服务贝叶斯网络模型，计算出条件概率表和敏感性因子，确定出关键变量关键状态子集。

(a)数据图层(b)属性表  
图层1 图层1像元点 降水量 植被坡度 蒸散发 土地利 太阳轩  
层2 图层2 /mm 覆盖度 /() 量/mm用水平分级/MJ·r·· 离散化 提取值 输型 1 >584.0 >0.46 >7.0 >5362.0 3 >557  
n 图层n状态分级T 1 T业生 未地0 NPP 保持概率21 最概16. 最高14.5 最高42.9 高9.7 中 35.0 低62.0中43.7 中32.9 低24.3 植被覆盖度低11.3 低40.9 → 概率/%蒸发 气温概率% 降水量概率/% 太阳辐射 最高23.0中35.7(d)条件概率表像元点降水量 植被覆 坡度 蒸散 土地利用 太阳 气温 土壤保持量概率 $1 \%$ 盖度 发量 水平分级 辐射 最高高 中 低1 最高 最高 高 高 高 高 高 3.5 8.9 25.6 62.0

注：NPP为净初级生产力。下同。

# 干吴区地理

# 表2因子状态分级

<html><body><table><tr><td colspan="3">Tab.2 State classification of factors</td></tr><tr><td>因子</td><td>状态名称</td><td>实际值范围</td></tr><tr><td>蒸散发量/mm</td><td>低</td><td>2256~3903</td></tr><tr><td></td><td>中</td><td>3903~5362</td></tr><tr><td></td><td>高</td><td>5362~9827</td></tr><tr><td></td><td>最高</td><td>9827~65534</td></tr><tr><td>土地利用水平分级</td><td>低</td><td>1</td></tr><tr><td></td><td>中</td><td>2</td></tr><tr><td></td><td>高</td><td>3</td></tr><tr><td></td><td>最高</td><td>4</td></tr><tr><td>植被覆盖度</td><td>低</td><td>-0.17~0.14</td></tr><tr><td></td><td>中</td><td>0.14~0.30</td></tr><tr><td></td><td>高</td><td>0.30~0.46</td></tr><tr><td></td><td>最高</td><td>0.46~0.70</td></tr><tr><td>水土保持措施因素</td><td>低</td><td>0.00</td></tr><tr><td></td><td>中</td><td>0.00~0.10</td></tr><tr><td></td><td>高</td><td>0.10~0.35</td></tr><tr><td></td><td>最高</td><td>0.35~1.00</td></tr><tr><td>土壤类型</td><td>低</td><td>1~4</td></tr><tr><td></td><td>中</td><td>4~9</td></tr><tr><td></td><td>高</td><td>9~14</td></tr><tr><td></td><td>最高</td><td>14~20</td></tr><tr><td>太阳辐射/MJ·m²</td><td>低</td><td>4989~5331</td></tr><tr><td></td><td>中</td><td>5331~5576</td></tr><tr><td></td><td>高</td><td>5576~5732</td></tr><tr><td></td><td>最高</td><td>5732~5911</td></tr><tr><td>降水量/mm</td><td>低</td><td>323~422</td></tr><tr><td></td><td>中</td><td>422~506</td></tr><tr><td></td><td>高</td><td>506~584</td></tr><tr><td></td><td>最高</td><td>584~693</td></tr><tr><td>坡度/()</td><td>低</td><td>0.00~3.50</td></tr><tr><td></td><td>中</td><td>3.50~7.00</td></tr><tr><td></td><td>高</td><td>7.00~10.50</td></tr><tr><td>气温/℃</td><td>低</td><td><8</td></tr><tr><td></td><td>中</td><td>8~9</td></tr><tr><td></td><td>高</td><td>9~10</td></tr><tr><td></td><td>最高</td><td>10~12</td></tr><tr><td>土地利用类型</td><td>耕地</td><td></td></tr><tr><td></td><td>林地</td><td>一</td></tr><tr><td></td><td>草地</td><td>-</td></tr><tr><td></td><td>水域</td><td>1</td></tr><tr><td></td><td>建设用地</td><td>1</td></tr><tr><td></td><td></td><td>1</td></tr><tr><td>土壤保持/t·hm²</td><td>未利用地</td><td>0.00~41.30</td></tr><tr><td></td><td>低</td><td></td></tr><tr><td></td><td>中</td><td>41.30~93.60</td></tr><tr><td></td><td>高</td><td>93.60~174.14</td></tr><tr><td>农业生产力/t·hm</td><td>最高</td><td>174.14~555.09</td></tr><tr><td></td><td>低</td><td>28.64~57.75</td></tr><tr><td></td><td>中</td><td>57.75~60.00</td></tr><tr><td></td><td>高</td><td>60.00~90.00</td></tr><tr><td></td><td>最高</td><td>90.00~120.00</td></tr><tr><td>NPP/g C·m²</td><td>低</td><td>0.23~11.97</td></tr><tr><td></td><td>中</td><td>11.97~135.89</td></tr><tr><td></td><td>高</td><td>135.89~204.47</td></tr><tr><td></td><td>最高</td><td>204.47~388.90</td></tr><tr><td>产水量/m</td><td>低</td><td>0.00~408.61</td></tr><tr><td></td><td>中</td><td>408.61~1001.75</td></tr><tr><td></td><td></td><td></td></tr><tr><td></td><td>高 最高</td><td>1001.75~2095.70 2095.70~3361.15</td></tr></table></body></html>

注：NPP为净初级生产力。下同。

以ArcGIS软件为工具，可视化子集分布空间，最终绘制不同等级所对应的关键变量关键状态子集同时发生的区域。筛选关键变量关键状态子集，包括以下步骤：

（1）确定各变量的关键状态

根据节点各状态的概率及两两节点状态组合的联合概率，计算每个影响因子与各服务间的条件概率，选取不同等级对应各个影响因子的条件概率最大状态作为变量的关键状态。当服务处在最高、高、中、低4种不同级别时，将对应4种变量状态集合。

# （2）确定关键变量

为了评价贝叶斯网络节点的相对重要性，Neti-ca提供了敏感性分析[23.41],主要是用于评估生态系统服务节点是否会敏感地感知其他影响因子节点的变化[9.22]。据此确定生态系统服务关键变量关键状态子集，然后选取变量关键状态子集的面积与研究区总面积比值最大的情景作为生态系统服务最优的情景，将该情景下的关键变量关键状态子集选定为最优状态子集，然后结合县区的发展和管理等划分出生态系统服务的优化区。

# 2结果与分析

# 2.1SWAT模型率定与验证

SWAT模型有26个与径流模拟相关的敏感性因子，不同因子影响各异。本文根据SWAT-CUP软件进行模拟率定，通过T检验确定水文参数的敏感性相对显著性, $P$ 值确定其显著性特征[42-43]。进而选取相关参数(表3)，通过调整参数，误差能够控制在一定范围之内。

由于张家山水文站观测数据限制，本文以2000—2010年实测数据和模拟数据进行率定，根据不断调整得到的参数，获得模拟效果最佳的一组数据。如图3a所示，其中决定性系数 $\left( R ^ { 2 } \right)$ 为0.74，纳什效率系数(NSE)为0.73，都大于0.5，表示模拟值与实测值具有较高的相关性，模型的模拟结果是可靠的。模拟2011—2020年泾河流域的月径流量，与张家山水文站数据进行比对进行验证，可以得出 $R ^ { 2 }$ 为0.78(图3b)，径流实测与模拟值具有较高的相关性，模拟结果是可信的，据此模拟2000—2020年泾河流域产水服务。

# 表3参数敏感性分析

Tab.3Sensitivity analysis result of parameters   

<html><body><table><tr><td>参数名称</td><td>相对显著性(T)</td><td>显著性检验(P)</td><td>参数范围</td><td>最优校准值</td></tr><tr><td>土壤饱和导水率</td><td>2.5450</td><td>0.0112</td><td>-0.9~0.9</td><td>-0.8425</td></tr><tr><td>降雪温度</td><td>-2.2385</td><td>0.0256</td><td>-20~20</td><td>7.9700</td></tr><tr><td>主河道水力传导度</td><td>1.8577</td><td>0.0638</td><td>0~150</td><td>58.8517</td></tr><tr><td>地下水滞留系数</td><td>-1.7717</td><td>0.0771</td><td>0~500</td><td>390.1691</td></tr><tr><td>土壤蒸发补偿系数</td><td>-1.2422</td><td>0.2148</td><td>0.01~1.00</td><td>0.0294</td></tr><tr><td>土壤有效含水率</td><td>-1.1148</td><td>0.2655</td><td>-0.5~0.5</td><td>0.3959</td></tr><tr><td>土壤湿密度</td><td>1.0494</td><td>0.2945</td><td>-0.5~0.5</td><td>-0.4496</td></tr><tr><td>基流系数</td><td>0.5965</td><td>0.5512</td><td>0~1</td><td>0.9276</td></tr><tr><td>地下水再蒸发系数</td><td>-0.5050</td><td>0.6138</td><td>0.02~0.20</td><td>0.1400</td></tr><tr><td>浅层地下水径流系数</td><td>0.0329</td><td>0.9737</td><td>0~5000</td><td>2409.2715</td></tr></table></body></html>

![](images/c1624b5483ad75d89d0c58a46f8d6db4433edb388f2087ed7bf15631f317d6f8.jpg)  
注：R为决定性系数;NSE为纳什效率系数。  
图3率定期和验证期逐月径流量模拟值与实测值  
Fig.3Simulated and measured values of monthly runof during the regular period and the verification period

# 2.2生态系统服务时空格局分析

生态系统服务功能之间相互作用与影响，对流域生态格局发展与优化具有显著影响。本研究通过模型模拟了2000—2020年泾河流域产水量、NPP、农业生产力和土壤保持4种生态系统服务量的空间分布(图4)。区域产水量在时间上呈增长趋势，2000年平均产水量为 $4 8 9 . 6 \mathrm { ~ m } ^ { 3 }$ ,而2020年平均产水量为 $7 2 9 . 6 \mathrm { ~ m } ^ { 3 }$ 。在空间上呈现北部和西南部高，中间低的特征，高值区域主要集中在环县、千阳县和凤翔县等区域。此外，低值区主要集中在西部的泾源县以及北部的盐池县。但是2020年产水量高值区域较为分散，主要呈现中间低，四周高的分布格局，主要是因为2020年相较于其他年份降水重心有所转移，并且受季风天气的影响，导致区域降水量年际差异明显，所以在一定程度上影响产水量的空间分布。NPP在年际变化中呈现增长的趋势，2000年NPP的平均值为 $1 8 5 . 1 \ \mathrm { g } \ \mathrm { C } \cdot \mathrm { m } ^ { - 2 }$ ,总量为 $7 . 7 \times$ $1 0 ^ { 6 } \mathrm { t }$ ,而2020年NPP的平均值为 $4 6 1 . 9 \mathrm { g } \mathrm { C } \cdot \mathrm { m } ^ { - 2 }$ ，总量为 $2 . 4 \times 1 0 ^ { 7 } \mathrm { t }$ ，总量相较于2000年大约增加了3倍。NPP在空间上呈现西北向东南逐渐递减的趋势，高值区域集中在流域两侧子午岭山系及西部六盘山地区。低值区主要原因是植被以典型草原为主，并且逐渐东南方向退化，沙漠化问题较严重。农业生产力在时间上从由2000年的 $2 8 0 . 9 \times 1 0 ^ { 7 } \mathrm { t }$ ,增长到至2020年的 $3 6 8 . 3 \times 1 0 ^ { 7 } \mathrm { t }$ ；在空间上自西向东呈增加趋势，南北向呈“马鞍形”分布，空间分布差异较小。高值分布面积有所增加，集中分布在陕西省长武县、淳化县以及宁夏回族自治区泾源县。土壤保持从时间尺度上看，总体呈波动变化趋势，但年际差异较大，土壤保持从2000年的 $3 . 0 { \times } 1 0 ^ { 8 } 1$ 增加到2020年的 $5 . 3 { \times } 1 0 ^ { 8 } \mathrm { t }$ ,土壤保持呈现显著增长趋势。从空间分布特征看出，土壤保持强度空间分布存在一定差异，整体呈现出北部、中部低，西南部和东南部高的分布格局。土壤保持强度低值区主要分布在流域北部和中部，北部为地形起伏变化的黄土丘陵区，加之年降水量低于区域平均值，植被生长水热

(a)2000年产水量 (b)2005年产水量 (c)2010年产水量 (d)2015年产水量 (e)2020年产水量盐池县 盐池县 盐池县 盐池县 盐池县 N定边具 A县 环县 起具 环县 吴起县 环县 吴起县 环县华池县 池 图例原州阳县 原州区 庆城县 原州阳县 庆城县 原州县 庆城县水县 原州区 庆城县合水县 □县域边界合水县 澎阳县 水县 合水县镇原县 西峰区 镇原县西峰区 镇原县 西峰区 镇原县西峰区5 镇原县西峰区 产水量/m  
泾源县 腔峒区泾川县 宁县 泾源县区川县正宁 泾源县腔区泾川县 宁县 1 泾源县皖明区川县县 泾源县川县宁县崇信县 武真旬邑 华亭县 崇信县一长武 旬邑县 华亭县 长武县洵邑县 华亭县崇信县长武县县 华亭县 崇信县\~长武 县旬邑县 3361.2阳县县 凤翔县 化县 县 阳县麟游县永县 凤翔县 台县彬县淳化县 阳县县水寿 凤翔县 县灵台县彬县淳化县 千阳县游县永寿 凤翔县 泾阳县 县县县 凤翔县 0.0乾县 乾县渭城区 100 km  
(f)2000年NPP (g)2005年NPP (h)2010年NPP (i)2015年NPP (j)2020年NPP盐池县 盐池县 盐边 盐地具 N环县 吴起县 华池县 环县 华池 环县 华池县 吴起县 环县 华池县 吴起县 环县 吴起县 华池县 图例原州县 镇原县西峰区 庆城县 2 水县 原州县 华亭县 镇原县西峰区 经川县 庆城县合水县 州 翼 泾源县 原州县 华亭县 皖峒区泾川县 镇原县西峰区 崇信县 庆城县 水 共具 原州区县 镇原县西峰区 庆城县 0 县边界陇县灵 陇县灵台县 县淳化县千阳县游县永寿县 千阳县麟游县永 千阳县麟游县 永寿县凤翔县 泾阳县礼泉县  
(k)2000年农业生产力 (l)2005年农业生产力(m)2010年农业生产力 (n)2015年农业生产力 (o)2020年农业生产力N环县 吴起县 环县 吴起 图例华池 华池 华池 华池 □县域边界原州区 夫城县 水县 原州区县 原州区 原州区 夫城县合水县 原州区县 城县 水县 农业生产力  
泾源县崆峒区 镇原县西峰区 泾源县崆响区泾川县宁县 镇原县西峰区 泾源县岭制镇县 西峰区 1 泾源县蛟铜区 镇原县西峰区 泾源县岭帆区 /t·hm-2华亭县 信 泾川县 真 华豪县 华亭县 华亭具 崇信县 华亭县 120.0县 陇县 县 享化县 陇县 冶 享化县 陇县 1千阳县游县 千国县 千阳县县 永 千阳县游县永 千阳县县 泾阳县 28.6100km凤翔县 凤翔县 原县 乾县城区0  
(p)2000年土壤保持 (q)2005年土壤保持 (r)2010年土壤保持 (s)2015年土壤保持 (t)2020年土壤保持盐池县 盐池县 N定边 定边 A环县 吴起县 环县 起县 环县 吴起县 环县 起具 环县 起具 图例华池县 华池县原州 夫城县 原州 庆城县 原州县 庆城县 原州县 庆城县 原州区 庆城县 界m²水县 合水县 合水县 水县 彭阳县 合水县  
泾源县崆峒区 镇原县西峰区 川县 宁具 泾源县崆峒区 镇原县西峰区 泾川县 宁县 泾源县崆峒区 镇原县西峰区 泾川县 宁县 泾源县崆峒区 镇原县西峰区 泾川县 泾源县崆峒区 镇原县西峰区 泾川县 宁县 555.1华亭！ 陇县 中国 彬县淳化县 华亭县 陇县 千阳县县 县旬 县淳化县 华亭县崇信 陇县 千水 淳化县 华亭县 陇县灵台县 千阳县县 信具 可品 化县 渭城区 华亭县崇信县 陇县 中国县0 武 彬县淳化县 0.0 100 km

条件很差，导致该地区植被覆盖度较低。高值区主要分布在流域西南部和东南部，部分区域大面积为林地，海拔较高，并且规划了森林保护区，人类活动对地表的干扰小。

# 2.3生态系统服务空间格局优化

贝叶斯网络模型以概率相关理论为基础，得到研究区不同生态系统服务关键变量最优状态子集，进而筛选出需要优化的区域。对于泾河流域生态系统来说，人为因素和自然环境的双重作用，对生态系统服务的影响不容小。不同的生态系统服务，筛选不同的关键变量，得到不同生态系统服务的条件概率表，如表4\~7所示。根据表4所示，土地利用水平和蒸散发是影响农业生产的关键变量，当农业生产力出现最高（0.353）、高（0.422）、中等(0.620)和低水平(0.491)概率时，所对应的土地利用水平和蒸散发量分别处于不同程度的水平。对比得到土地利用水平处在高级水平即农业用地水平，蒸散发量处于高值区间 $5 3 6 2 { \sim } 9 8 2 7 ~ \mathrm { m m }$ 时，农业生产力达到最大可能概率(0.620)，处于中值范围L $5 7 . 7 { \sim } 6 0 . 0 \ \mathrm { t } \cdot \mathrm { h m } ^ { - 2 } ,$ ，对其进行空间可视化展示（图

# 表4农业生产力节点条件概率

Tab.4 Conditional probability of the node crop production   

<html><body><table><tr><td rowspan="2">土地利用水平</td><td rowspan="2">蒸散发量</td><td colspan="4">农业生产力</td></tr><tr><td>最高</td><td>高</td><td>中</td><td>低</td></tr><tr><td>最高</td><td>最高</td><td>0.353</td><td>0.002</td><td>0.284</td><td>0.361</td></tr><tr><td>高</td><td>高</td><td>0.229</td><td>0.032</td><td>0.620</td><td>0.119</td></tr><tr><td>中</td><td>高</td><td>0.099</td><td>0.111</td><td>0.299</td><td>0.491</td></tr><tr><td>低</td><td>中</td><td>0.108</td><td>0.422</td><td>0.282</td><td>0.188</td></tr></table></body></html>

5)，优化区域主要分布在环县、华池县、彭阳县、庆阳县以及镇原县等北部黄土区，对这些地区加大农业生产的投资和管理力度，能够较为迅速地提高泾河流域整体的农业生产力。当土地利用类型为草地，土地利用水平处在中级水平，降水量处于最高值 $5 8 4 { \sim } 6 9 3 ~ \mathrm { m m }$ 时，气温小于 $8 ^ { \circ } \mathrm { C }$ 时，产水量达到最大可能概率（0.805），处于高值范围（408.61\~$1 0 0 1 . 7 5 \mathrm { m } ^ { 3 } .$ )，优化区域主要集中在环县的中南部以及彭阳县和镇原县附近，对区域水资源进行高效利用，能在一定程度上增加地表径流量，最终提升区域的产水服务能力。当土地利用类型为未利用地，太阳辐射、气温和植被覆盖度都为最高水平时，NPP服务达到最大可能概率（0.878），处于中值范围（204号 $( 1 1 . 9 7 { \sim } 1 3 5 . 8 9 \mathrm { ~ g ~ C ~ } { \cdot } \mathrm { m } ^ { - 2 } )$ ，优化区域主要集中在彭阳县和华池县、镇原县、环县中部和南部，吴起县南部和合水县北部，提升区域的植被覆盖率对提高NPP服务有深远的影响。通过关键因子的筛选，影响土壤保持的关键因素是降水量、坡度、水土保持措施因素、植被和土壤类型，降水量概率是最重要的因素。当土壤类型、降水量、坡度以及水土保持措施因素位于中级水平，植被覆盖度为最高水平时，所对应的土壤保持出现最高水平的概率最高，达到0.824,该子集主要分布在彭阳县和华池县、庆城县北部和镇原县以及环县南部，对该区域增加植被覆盖，抚育和保护森林资源，加强生态环境的建设和投入，有效控制水土流失带来的损失，会对区域的水土保持服务起到正向的作用。

Tab.5 Conditional probability of the node water yield   
表6NPP节点条件概率  

<html><body><table><tr><td rowspan="2">土地利用水平</td><td rowspan="2">降水量</td><td rowspan="2">气温</td><td rowspan="2">土地利用类型</td><td colspan="4">产水量</td></tr><tr><td>最高</td><td>高</td><td>中</td><td>低</td></tr><tr><td>最高</td><td>最高</td><td>高</td><td>未利用地</td><td>0.159</td><td>0.020</td><td>0.205</td><td>0.616</td></tr><tr><td>中</td><td>最高</td><td>低</td><td>未利用地</td><td>0.065</td><td>0.138</td><td>0.579</td><td>0.217</td></tr><tr><td>中</td><td>最高</td><td>低</td><td>草地</td><td>0.031</td><td>0.805</td><td>0.084</td><td>0.080</td></tr><tr><td>最高</td><td>最高</td><td>最高</td><td>草地</td><td>0.488</td><td>0.124</td><td>0.191</td><td>0.196</td></tr></table></body></html>

Tab.6 Conditional probability of the node NPP   

<html><body><table><tr><td rowspan="2">降水量</td><td rowspan="2">气温</td><td rowspan="2">土地利用类型</td><td rowspan="2">太阳辐射</td><td rowspan="2">植被覆盖度</td><td colspan="4">NPP</td></tr><tr><td>最高</td><td>高</td><td>中</td><td>低</td></tr><tr><td>中</td><td>最高</td><td>未利用地</td><td>最高</td><td>最高</td><td>0.060</td><td>0.024</td><td>0.878</td><td>0.039</td></tr><tr><td>低</td><td>低</td><td>未利用地</td><td>低</td><td>低</td><td>0.072</td><td>0.043</td><td>0.438</td><td>0.446</td></tr><tr><td>中</td><td>最高</td><td>草地</td><td>最高</td><td>最高</td><td>0.149</td><td>0.469</td><td>0.019</td><td>0.363</td></tr><tr><td>最高</td><td>最高</td><td>耕地</td><td>最高</td><td>最高</td><td>0.571</td><td>0.154</td><td>0.160</td><td>0.115</td></tr></table></body></html>

# 表7土壤保持节点条件概率

表5产水节点条件概率  
Tab.7 Conditional probability of the node soil conservation   

<html><body><table><tr><td rowspan="2">土壤类型</td><td rowspan="2">降水量</td><td rowspan="2">植被覆盖度</td><td rowspan="2">坡度</td><td rowspan="2">土壤保持措施因素</td><td colspan="4">土壤保持</td></tr><tr><td>最高</td><td>高</td><td>中</td><td>低</td></tr><tr><td>最高</td><td>最高</td><td>中</td><td>低</td><td>最高</td><td>0.126</td><td>0.056</td><td>0.320</td><td>0.499</td></tr><tr><td>最高</td><td>最高</td><td>最高</td><td>低</td><td>最高</td><td>0.191</td><td>0.135</td><td>0.458</td><td>0.215</td></tr><tr><td>最高</td><td>最高</td><td>最高</td><td>中</td><td>高</td><td>0.108</td><td>0.496</td><td>0.035</td><td>0.362</td></tr><tr><td>中</td><td>中</td><td>最高</td><td>中</td><td>中</td><td>0.824</td><td>0.007</td><td>0.139</td><td>0.029</td></tr></table></body></html>

# 干旱区地理

最后对4种生态系统服务的优化区域进行空间叠加分析，得到综合的优化像元(图5)。优化区域主要集中在彭阳县的中部和西南部以及环县的零星区域，部分区域应该采取相应的生态环境保护措施，加快生态、民生和多功能林业的发展，对于草原生态要坚持保护与建设并举，保护优先的原则，设置一定的惩奖措施，在一定程度上提升居民对于生态环境保护意识，促进区域多种生态系统服务良性发展。

# 3讨论

# 3.1生态系统服务空间差异性分析

生态系统过程是自然和人类活动共同作用的结果，如何构建合理的模型来模拟区域生态系统服务是深刻了解生态过程的关键，本文通过不同的生态系统服务评估模型得到4种生态系统服务的空间格局。为了探究研究结果的准确性，将本文的研究结果和其他学者进行对比。刘宇等[44]通过用Pen-man-Monteith公式计算泾河流域近70a的径流变化，以及黄晨璐等[45]在统计数据的基础上，运用相关的模型来模拟泾河流域径流状况，在时空尺度上和本研究结果具有相似性；在NPP和土壤保持服务的时空分布方面与卞鸿雁等[46]以及Zheng等[47]的结果具有相似性，都在年际间趋于稳定上升的趋势，并且时空差异显著。此外,根据本文研究结果,4种生态系统服务的优化区域都集中在黄土高原和泾河流域北部的山区，制约区域发展的关键因子主要是土壤、植被和降水，而关键因子对于评估区域4种生态系统服务有着至关重要的影响。泾河流域产水服务的空间变化特征和土地利用、蒸散发和植被水分利用系数相关，2000—2020年区域耕地面积减少，森林和草地面积增加，进而增加区域植被水分利用系数，植被类型从禾本科植物向森林植被转化所引起。2020年相较于2000年，降水量增加，而部分区域径流量减少，暗示区域内潜在蒸散发则逐渐增大，表明区域径流量对于降水和潜在蒸散发较为敏感44。产水和降水的空间分布较为一致，主要取决于气候和地形因素相关，西北部属于黄土高原区，受副热带高气压控制，干旱少雨，产水量也较少。泾河流域大多区域经济相对落后，居民的生活需求对区域生态系统服务依赖性很强，农业生产力较强的区域，居民能够满足生活，少数区域粮食供给能力不足[48]。北部区域以草地为主，牧业长期集中与此,长期的粗放经营,会造成土地严重的沙化,进而影响区域的农业生产力以及NPP服务，造成两种生态系统服务在区域上呈现南北差异化明显。而随着退耕还林、封山育林、飞播、人工植树等生态措施的实施，促使区域内林地面积增加，提升区域的NPP和水土保持能力。本研究建议对生态系统服务优化区实施提升肉类的产量以及薪柴供给的手段等生态措施和生态补偿政策[49-50],不仅可以提升居民的收入和生活质量，而且还可以保障原有的土壤保持和NPP等生态系统服务的增强，促进区域生态经济和谐发展。为了深入研究生态系统服务的区域差异性，不仅要定性分析，还要利用模型进行定量的研究，未来应该通过多视角、多指标对生态系统服务驱动因素进行定量分析，促使研究结果更加精准。

![](images/a2ab04e9f16d48db5bc552139e4fd579fa3cebaaf5c4060737b6aa9a85aaf24a.jpg)  
图5综合生态系统服务优化区  
Fig.5Integrated ecosystem service optimization zone

# 3.2生态系统服务空间格局优化

贝叶斯网络可以将多元知识进行图解可视化的概率模型，它不仅包括各个网络节点之间的因果相关性，而且结构还比较灵活，既可以优化现在的空间格局，还可以预测未来的空间格局分布。李婷等通过贝叶斯网络和固碳服务相结合，来探究固碳服务的格局优化问题；曾莉等2通过不同发展情景水源涵养的状态概率分布，最终给出水源涵养服务的空间格局优化策略。但是贝叶斯网络是具有不确定性的，主要包括结构不确定性、输入数据不确定性和参数不确定性[5]。本文将产水量、NPP、土壤保持和农业生产4种生态系统服务和贝叶斯网络相结合，探讨了不同生态系统服务以及综合优化区域，为优化区的保护和生态经济和谐发展奠定基础。目前，对生态系统服务空间格局优化的研究主要集中在围绕土地利用模式的变化设计方案，预测各种方案下的服务变化,并提供优化建议[16-17]。然而，土地利用并不是唯一影响生态系统服务的因素，而各因素对不同生态系统服务的影响程度也是不同的。本文在贝叶斯网络的基础上，提出了关键子集法，对泾河流域生态系统服务的空间格局进行了优化，研究结果为研究区生态环境保护区划提供决策支持，丰富生态系统服务空间格局优化的研究方法。但是自然和人类活动共同影响着区域的生态环境，本文仅考虑降水量、气温、土地利用等因素对生态系统的影响是不够的，未来应该结合更多的影响指标，比如人类活动、生态政策以及社会经济等因素来构建多情景的模式，将情景分析和贝叶斯网络相结合，更加全面的为区域空间格局优化提供依据。

# 4结论

（1）SWAT模型在泾河流域有较好的适用性。校准后的SWAT模型对径流量的模拟结果与实测值相比，具有较高的决定性系数( $R ^ { 2 } { > } 0 . 6 )$ 、纳什效率系数 $\mathrm { \langle N S E { > } 0 . } 5 \rangle$ ，表明该模型能较为准确地模拟流域生态水文过程，为进一步评估产水服务提供保障。

（2）2000一2020年泾河流域4种生态系统服务的时空差异性较为显著。在时间尺度上，随着退耕还林还草以及居民生态环保意识的提升，促使4种生态系统服务都呈现波动中上升的趋势;而在空间尺度上，NPP、农业生产力以及土壤保持服务变化较小，呈现较为稳定的趋势，而产水量和区域气候有着直接的关系，导致产水服务在区域内呈现显著变化。

(3）贝叶斯网络模型是一种强大的神经网络工具，可以很好地与生态系统服务相结合，在生态系统服务空间优化过程中发挥重要作用。本研究通过对4种生态系统服务优化区域进行叠加分析，发现综合优化区域集中在彭阳县的中部和西南部以及环县的零星区域，对区域应该采取相应的生态环境保护措施，要坚持保护与建设并举，保护优先的原则，进而促进区域多种生态系统服务良性发展。

# 参考文献(References)

[1] FuBJ.Trade-off analyses and synthetic integrated method of multiple ecosystem[J]. Resources Science,2016,38(1):5-10. [2] Pedreschi D,Bouch P,Moriary M,et al.Integrated ecosystem anal

# 干旱区地理

ysis in Irish waters: Providing the context for ecosystem-based fisheries management[J].Fisheries Research,2019,209: 218-229.   
[3]Newton A, Brito A C, Icely JD, et al. Assessing,quantifying and valuing the ecosystem services of coastal lagoons[J].Joural for Nature Conservation, 2018,44: 50-65.   
[4]Chen L C,Guan X,Li H M,et al. Spatiotemporal patterns of carbon storage in forest ecosystems in Hunan Province, China[J].Forest Ecology and Management,2019,432: 656-666.   
[5]Luiseti T,Turner R K,Andrews JE,et al. Quantifying and valuing carbon flows and stores in coastal and shelf ecosystems in the UK[J]. Ecosystem Services,2019,35: 67-76.   
[6]Stritih A, BebiP, Gret-Regamey A. Quantifying uncertainties in earth observation-based ecosystem service assessments[J]. Environmental Modelling & Software,2019,111: 300-310.   
[7]戴尔阜,王晓莉,朱建佳,等.生态系统服务权衡:方法、模型与 研究框架[J].地理研究,2016,35(6):1005-1016.[Dai Erfu,Wang Xiaoli, Zhu Jianjia,et al.Methods,tools and research framework of ecosystemservice trade-offs[J]. Geographical Research, 2016,35 (6): 1005-1016.]   
[8] 傅伯杰,于丹丹.生态系统服务权衡与集成方法[J].资源科学, 2016,38(1):1-9.[Fu Bojie,Yu Dandan.Trade-off analyses and synthetic integrated method of multiple ecosystem services[J]. Resources Science,2016,38(1): 1-9.]   
[9]李婷,李晶,王彦泽,等.关中天水经济区生态系统固碳服务空 间流动及格局优化[J].中国农业科学,2017,50(20):3953- 3969.[Li Ting,Li Jing,Wang Yanze,et al. The spatial flow and pattern optimization of carbon sequestration ecosystem service in Guanzhong Tianshui economical region[J]. Scientia Agricultura Sinica,2017,50(20): 3953-3969.]   
[10] 刘维,周忠学,郎睿婷.城市绿色基础设施生态系统服务供需关 系及空间优化——以西安市为例[J].干旱区地理,2021,44(5): 1500-1513.[Liu Wei, Zhou Zhongxue,Lang Ruitig.Supply-demand relations of ecosystem services of urban green infrastructure and its spatial optimization: A case of Xi'an City[J].Arid Land Geography,2021,44(5): 1500-1513.]   
[11]Dai FN, Quinn C, Morari F.A Bayesian belief network framework to predict SOC dynamics of alternative management scenarios[J]. Soil and Tillage Research, 2018,179: 114-124.   
[12]Wu X,Wang S,Fu B J, et al.Land use optimization based on ecosystem service assessment: A case study in the Yanhe watershed [J]. Land Use Policy,2018,72: 303-312.   
[13] 傅伯杰,张立伟.土地利用变化与生态系统服务:概念、方法与 进展[J].地理科学进展,2014,3(4):441-446.[Fu Bojie,Zhang Liwei. Land-use change and ecosystem services: Concepts, methodsand progress[J]. Progress in Geography，2014,33(4):441- 446.]   
[14]谢高地,张彩霞,张昌顺,等.中国生态系统服务的价值[J].资源 科学,2015,37(9): 1740-1746.[Xie Gaodi, Zhang Caixia, Zhang Changshun,et al. The value of ecosystem services in China[J]. Resources Science,2015,37(9): 1740-1746.]   
[15] 肖玉,谢高地,鲁春霞,等.基于供需关系的生态系统服务空间 流动研究进展[J].生态学报,2016,36(10):3096-3102.[Xiao Yu, Xie Gaodi,Lu Chunxia,etal.Involvement of ecosstemser vice flows in human wellbeing based on the relationship between supply and demand[J]. Acta Ecologica Sinica, 2016,36(10): 3096- 3102.]   
[16] 龚建周,刘彦随,张灵.广州市土地利用结构优化配置及其潜力 [J].地理学报,2010,65(11): 1391-1400.[Gong Jianzhou,Liu Yansui, Zhang Ling.The optimal allocation of land use and its potential appraisal in Guangzhou City[J].Acta Geographica Sinica, 2010,65(11): 1391-1400.]   
[17] 刘慧灵,伍世代,韦素琼,等.基于低碳经济导向的土地利用结 构优化研究——以福建省福州市为例[J].水土保持通报, 2017,37(6): 202-208.[Zhang Huiling,Wu Shidai, Wei Suqiong, et al.Optimization research of low-carbon economy oriented land use structure: A case study in Fuzhou City of Fujian Province[J]. Bulletin of Soil and Water Conservation,2017,37(6): 202-208.]   
[18] 王观,张乐,于化龙,等.基于生态安全的土地利用结构优化 研究[J].土壤通报,2015,46(6):1322-1327.[Wang Guanyong, Zhang Le, Yu Hualong,et al. Research on optimization of land use structure in Baoding urban agglomeration based on ecological security[J].Chinese Journal of Soil Science,2015,46(6):1322- 1327.]   
[19] 向芸芸,蒙吉军.基于生态效益的武汉城市圈土地利用结构优 化[J].长江流域资源与环境,2013,22(10):1297-1304.[Xiang Yunyun,Meng Jijun.Research on optimization of land use structure in Wuhan urban agglomeration based on ecological security benefit[J]. Resources and Environment in the Yangtze Basin, 2013,22(10): 1297-1304.]   
[20] 李秀霞,徐龙,江恩赐.基于系统动力学的土地利用结构多目标 优化[J].农业工程学报,2013,29(16):247-254.[Li Xiuxia, Xu Long, Jiang Enci. Multi-objective optimization of land use structure in western Jilin Province based on system dynamics[J]. Transactions of the Chinese Society of Agricultural Engineering,2013, 29(16): 247-254.]   
[21]Landuyt D, Broekx S,Goethals PL M. Bayesian belief networks to analyse trade-offs among ecosystem services at the regional scale [J].Ecological Indicators,2016,71: 327-335.   
[22] 曾莉,李晶,李婷,等.基于贝叶斯网络的水源涵养服务空间格 局优化[J].地理学报,2018,73(9):1809-1822.[Zeng Li,LiJing, Li Ting,et al. Optimizing spatial patterns of water conservation ecosystem service based on Bayesian belief networks[J].Acta Geographica Sinica, 2018,73(9): 1809-1822.]   
[23]Fox WE, Medina-Cetina Z,Angerer J,et al. Water quality& natural resource management on military training lands in central Texas:Improved decision support via Bayesian networks[J]. Sustainability of Water Quality and Ecology,2017,9-10: 39-52.   
[24]Landuyt D, Lemmens P,D'hondt R,et al. An ecosystem service approach to support integrated pond management: A case study using Bayesian belief networks-highlighting opportunities and risks [J]. Journal of Environmental Management,2014,145: 79-87.   
[25]Dang KB,Windhorst W,Burkhard B,et al.A Bayesian belief network: Based approach to link ecosystem functions with rice provisioning ecosystem services[J]. Ecological Indicators, 2019,100: 30-44.   
[26] Chen C, Xie G, Zhen L,et al. Analysis on Jinghe River watershed vegetation dynamics and evaluation on its relation with precipitation[J]. Acta Ecologica Sinica,2008,28(3): 925-938.   
[27] Xie G D, Zhen L, Chen C,et al.The changes and their interactions of precipitation-landscape-runoff in Jinghe Watershed[J]. Resourc es Science,2007,29(2): 156-163.   
[28]Guo A,Chang J,Wang Y,et al.Variation characteristics of rainfall-run relationship and driving factors analysis in Jinghe River Basin in nearly 5O years[J]. Transactions of the Chinese Society of Agricultural Engineering,2015,31(14): 165-171.   
[29] 甄霖,谢高地,杨丽,等.基于参与式社区评估法的泾河流域景 观管理问题分析[J].中国人口·资源与环境,2007,17(3):129- 133.[Zhen Lin,Xie Gaodi, Yang Li,etal. Challenges facing landscape management in the Jinghe watershed of northwest China by using participatory rual apprise[J]. China Population, Resources and Environment, 2007,17(3): 129-133.]   
[30] 麻馨月,杨洋,娄成武.21世纪以来环渤海地区耕地生产潜力 时空动态[J].中国人口·资源与环境,2016,26(增刊1): 226- 231.[Ma Xinyue, Yang Yang,Lou Chengwu. Spatiotemporal dynamics of cultivated land potential productivity in Bohai Rim since the $2 1 ^ { \mathrm { s t } }$ Century[J]. China Population,Resources and Environment, 2016,26(Suppl.1): 226-231.]   
[31] Zheng Z,Fu B J,Hu H,et al.A method to identify the variable ecosystem services relationship across time: A case study on Yanhe Basin,China[J].Landscape Ecology,2014,29(10): 1689-1696.   
[32] Neitsch S L,Arnold JG, Kiniry JR,et al. Soil and water assessment tool,theoretical documentation,Version 2Ooo[M].College Station,Texas: Texas Water Resources Institute,200.   
[33] 杨晓楠,李晶,秦克玉,等.关中天水经济区生态系统服务的权 衡关系[J].地理学报,2015,70(11):1762-1773.[Yang Xiaonan, Li Jing,Qin Keyu,et al. Trade-offs between ecosystem services in Guanzhong Tianshui Economic Region[J]. Acta Geographica Sinica, 2015,70(11): 1762-1773.]   
[34] 朱文泉,潘耀忠,张锦水.中国陆地植被净初级生产力遥感估算 [J].植物生态学报,2007,31(3):413-424.[Zhu Wenquan,Pan Yaozhong,Zhang Jinshui. Estimation of net primary productivity of Chinese terrestrial vegetation based on remote sensing[J]. Chinese Journal of Plant Ecology,2007,31(3): 413-424.]   
[35]Peng H,Jia Y,Niu C,etal.Eco-hydrological simulation of soil and water conservation in the Jinghe River Basin in the Loess Plateau, China[J]. Journal of Hydro-environment Research,20l5,9(3): 452- 464.   
[36] Wischmeier W H,Smith DD.Predicting rainfall-erosion losses: A guide to conservation planning,agricultural handbook No.537[M]. Washington DC: US Department of Agriculture,1978.   
[37] 李硕豪,张军.贝叶斯网络结构学习综述[J].计算机应用研究, 2015,32(3): 641-646.[Li Shuohao,Zhang Jun. Review of Bayesian networks structure learning[J]. Application Research of Computers,2015,32(3): 641-646.]   
[38] Macpherson MP, WebbEB,Raedeke A,et al. Areviewof Bayesian belief network models as decision-support tools for wetland conservation: Are water bird’s potential umbrella taxa[J]? Biological Conservation,2018,226: 215-223.   
[39]Saliou N, Barnaud C, Vialatie A,et al.A participatory Bayesian belief network approach to explore ambiguity among stakeholders about socio-ecological systems[J]. Environmental Modelling&Software,2017,96:199-209.   
[40] Dai W,Fu W,Jiang P,etal. Spatial pattern of carbon stocks in for est ecosystems of a typical subtropical region of southeastern China [J].Forest Ecology and Management,2018,409: 288-297.   
[41] Kleemann J, Celio E,Nyarko B K, etal. Assessing the risk of seasonal food insecurity with an expert-based Bayesian belief network approach in northern Ghana,West Africa[J]. Ecological Complexity, 2017, 32: 53-73.   
[42] 李晶,周自翔.延河流域景观格局与生态水文过程分析[J].地理 学报,2014,69(7): 933-944.[Li Jing, Zhou Zixiang.Landscape pattern and hydrological processes in Yanhe River Basin of China [J].Acta Geographica Sinica,2014,69(7): 933-944.]   
[43] Jiang Y, Wang L, Wei X,et al.Impacts of climate change on runoff of Jinghe River based on SWAT model[J]. Transactions of the Chinese Society for Agricultural Machinery,2017,48(2): 262-270.   
[44] 刘宇,管子隆,田济扬,等.近70a泾河流域径流变化及其驱动 因素研究[J].干旱区地理,2022,45(1):17-26.[Liu Yu,Guan Zilong,Tian Jiyang,et al. Study on runoff change and its driving factors in Jinghe River Basin in recent 7O years[J].Arid Land Geography,2022,45(1): 17-26.]   
[45] 黄晨璐,杨勤科.渭河与泾河流域水沙变化规律及其差异性分 析[J].干旱区地理,2021,4(2):327-336.[Huang Chenlu,Yang Qinke.Runoff and sediment variation rules and differences in Wei River and Jing River Basins[J].Arid Land Geography,2021,44 (2): 327-336.]   
[46] 卞鸿雁,庞奖励,任志远.泾河流域固碳释氧功能的时空动态测 评[J].陕西师范大学学报(自然科学版),2013,41(2):94-99.[Bian Hongyan, Pang Jiangli, Ren Zhiyuan. The spatial and temporal changes of carbon fixation and oxygen release in Jinghe River Basin[J].Journal of Shaanxi Normal University (Natural Science Edition),2013,41(2): 94-99.]   
[47] Zheng T, Zhou Z, Zou Y, et al. Analysis of spatial and temporal characteristics and spatial flow process of soil conservation service in Jinghe Basin of China[J].Sustainability,2021,13(4): 1794,doi: 10.3390/su13041794.

# 干旱区地理

[48]杨莉,甄霖,李芬,等.黄土高原生态系统服务变化对人类福祉 的影响初探[J].资源科学,2010,32(5): 849-855.[Yang Li, Zeng Lin,Li Fen, et al. Impacts of ecosystem services change on human well-being in the Loess Plateau[J].Resources Science,2010, 32 (5): 849-855.]   
[49] Olschewski R,Benitez P C. Optimizing joint production of timber and carbon sequestration of afforestation projects[J]. Journal of Forest Economics,2010,16(1): 1-10.   
[50]Hoover C M,Heath L S.Potential gains in C storage on productive forestlands in the northeastern United States through stocking management[J]. Ecological Applications,2011,21: 1154-1161.   
[51]Chen S H,Pollino C A.Good practice in Bayesian network modelling[J].Environmental Modelling & Software,2012,37(17):134- 145.

# Spatial pattern optimization of ecosystem services based on Bayesian networks: A case of the Jing River Basin

YU Yuyangl²， LI Jing1， ZHOU Zixiang³， TANG Chengyan'   
(1.SchoolofGeographyandTourism,ShaanxiNormal University,Xi'an70l19,Shaanxi,China;2.ScholofTourism,Henan   
NormalUniversityXinxiang453oo7,Henan,China;3.CollgeofGeomatics,Xi'anUniversityofScienceandTechology， Xi'an 710054, Shaanxi, China)

Abstract: Changes in regional land use paterns due to rapid urbanization affect the quality of the ecological environment and the spatial patern of ecosystem services.Therefore,optimizing ecosystem services is crucial. Using the spatial assssment of net primary production,crop production，soil conservation，and water yield services in the Jing River Basin, northwest China from 200 to 202Oas the basis,this study combined Bayesian networks and ecosystem services and employed a subset ofkey variables and a visualized subset of optimal states to determine the areas necesitating the optimization of the aforementioned ecosystem services for regional economic and ecological harmonious development.Results showed that (1） the SWAT model can accurately simulate the regional runoff and generate a high coefficient of determination $( R ^ { 2 } { > } 0 . 6 )$ and a Nash-Sutclife efficiency coefficient ( $\mathrm { N S E } { > } 0 . 5$ ） when comparing simulated and observed values, thus providing a guarantee for the further assessment of water yield services. (2) The spatial and temporal variations of the four ecosystem services in the Jing River Basin from 2000 to 2020 were substantial.All four ecosystem services showed an upward fluctuation trend on the temporal scale and astable trend on the spatial scale.(3)Overlay analysis ofthe optimized areas for the four ecosystem services revealed that the integrated optimized areas were concentrated in the central and southwestern parts of Pengyang County， Ningxia Province and the scatered areas of Huan County， Gansu Province. This study is important for guiding region optimization for the sustainable management and reducing the degradation of ecosystems.

Key words: ecosystem services；Bayesian networks； spatial and temporal pattern optimization; Jing River Basin