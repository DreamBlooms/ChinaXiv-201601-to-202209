# 蒙古高原草原火灾风险评价研究

杨晓颖¹，玉山¹²，都瓦拉³，红梅1l.内蒙古师范大学地理科学学院,内蒙古 呼和浩特010022；2.内蒙古自治区遥感与地理信息系统重点实验室,内蒙古 呼和浩特010022；3.中国农业科学院草原研究所,内蒙古 呼和浩特010010)

摘要：草原火灾是牧区主要自然灾害之一，严重影响社会经济和生命安全。针对蒙古高原草原的特点及成灾机理，以蒙古高原的草原区作为研究区，获取了2000—2016年各盟市的指标层数据，依据自然灾害风险分析原理，从危险性、暴露性、脆弱性和防灾减灾能力4个方面选取23个评价指标,建立了蒙古高原草原火灾风险评价指标体系，并采用主成分分析方法确定指标权重，结合地理信息系统空间分析功能制作了蒙古高原草原火灾风险分布图。结果表明：(1)通过主成分分析得到7个主成分，缩减了指标个数，准确指出草原火灾风险要素来源。(2)蒙古高原草原火灾的高危险区分布在蒙古国中部，呈向四周递减的趋势；高暴露区分布在内蒙古东北部地区;高脆弱区分布在内蒙古北部以及蒙古国肯特省；高防灾减灾区主要分布在内蒙古呼伦贝尔市、兴安盟和鄂尔多斯市。(3)蒙古高原草原火灾风险从整体来看，内蒙古东北部风险高于西部地区，呈现自东向西递减趋势；蒙古国呈现由中间向四周递减趋势。低风险、次低风险、中风险、次高风险和高风险区面积占蒙古高原草原区面积比例分别为 $4 . 8 8 \% , 3 6 . 2 0 \% , 2 8 . 3 7 \% , 1 1 . 5 6 \%$ 和 $1 8 . 9 9 \%$ 。根据中蒙各盟市地理环境特征和经济发展水平来制定防火策略，可以降低草原火灾风险性，为草原畜牧业可持续发展规划提供参考。

关键词：草原火灾；风险评价；主成分分析；地理信息系统；蒙古高原文章编号：

草原作为生态系统的重要组成部分，极易受到自然灾害的干扰[]。近几年由于经济的快速发展,草原火灾在世界范围内变得尤为严重[2]。由自然或人为因素引起的草原火灾对人类社会有直接或间接的破坏性影响[3]。在整个蒙古高原，大片地区被草原覆盖,几乎每年都有草原火灾发生[4]。在单一地区频繁发生的草原火灾通常会抑制草的生长，并且会对土地资源造成破坏[5],导致生态系统结构和功能的紊乱，极大地改变环境，甚至威胁到人们的生命财产和国家生态资源[6]。因此，研究草原火灾的风险性有助于降低火灾发生频率和减少火灾损失[7]

随着牧区牲畜数量的增加和草原质量的下降，在蒙古高原地区的首要任务是防火[8]。火灾风险评价是在特定的时空范围内对可能发生的火灾进行估计，影响因子的选择至关重要，且影响着火险等级划分的准确性，对火灾预防具有重要意义[9-10]。现在遥感技术实时动态监测、覆盖面积非常广，在灾害应急调查方面发挥了重要作用"，再加上地理信息系统强大的空间分析与制图功能，这已经成为研究火灾普遍使用的技术[12]。最早Maselli等[13]基于春季和夏季不同时期获取的Landsat陆地卫星数据对地中海植被覆盖类型进行了分类，将获得的火灾风险图像与过去 $1 0 \mathrm { a }$ 发生的火灾进行评估。在过去的几十年里，利用GIS、RS等技术，相关学者已经提出了几种火灾风险指数，用于火灾风险评估和绘图[14-15]。Adab等[16]基于遥感数据结合火灾致因变量，建立了火灾风险指数和预警指数，利用GIS技术预测了伊朗东北部的森林火灾风险。在我国关于草原火灾风险评价的研究相对较少，张继权等[17]最早提出了草原火灾风险这一概念,根据自然灾害风险的形成机理提出了由危险性、暴露性、脆弱性以及防灾减灾能力综合作用的四因子理论，并利用此原理计算草原火灾风险因子值进行风险区划。迄今为止，大多数火灾风险评估都集中在火源上，一些研究中还考虑了大气条件、人为影响、可燃物载量和湿度状况等影响因素[18]。Bian等[19]利用地理信息系统和遥感技术提供了内蒙古呼伦贝尔的草原火灾风险图，结合研究区的相关情况将11个变量分为可燃物、火险气象指数、交通可达性以及人文和社会因素综合到一个模型中，来计算草原火灾风险指数。目前，国内在草原火灾风险评价、预警、区划等方面的研究相对国外比较滞后，且大多数研究区都集中在我国东北森林资源丰富、火灾发生频繁的地区[20],对草原火灾的研究较少。

在我国东北地区与蒙古国的交界地带，草原广布，且大都为草甸草原。我国北方地区正处于西风和西北风方向的下风头，若蒙古国发生火灾必然影响我国，因此境外火源是严重威胁我国北方森林草原地区安全的重要因素之一[21]。据统计，自2000年以来蒙古国的境外火越境频繁，对我国造成严重的威胁[22]。几乎每年中蒙边境地区都会发生火灾，近几年较大的火灾有2次，2016年4月22日，内蒙古自治区兴安盟遭遇蒙古国境外草原大火的侵袭，大火延续4d蔓延了 $2 0 0 \mathrm { k m } ^ { 2 } ; 2 0 1 7$ 年6月29日，位于蒙古国境内的大火持续蔓延至中蒙边境的中国呼伦贝尔地区，直接威胁着我国北方森林草原资源，因此对蒙古高原草原火灾风险评价是非常必要的。

本文通过对大尺度区域蒙古高原草原火灾风险评价的研究，拟尝试对草原火灾风险预警的可行性提出一些依据和建议。鉴于此，本文以蒙古高原草原为研究区，结合研究区的实际情况从危险性、暴露性、脆弱性、防灾减灾能力4个方面选取指标因子，运用主成分分析法以及综合加权评价法构建草原火灾评价模型进行草原火灾评价研究，编制一份有效的草原火灾风险区划图。这是火灾管理规划和决策过程中经济有效的第一步，旨在减少或预防草原火灾的发生。

# 1研究区概况与研究方法

# 1.1 研究区概况

蒙古高原位于 $3 7 ^ { \circ } 4 6 ^ { \prime } { \sim } 5 3 ^ { \circ } 0 8 ^ { \prime } \mathrm { N } , 8 7 ^ { \circ } 4 0 ^ { \prime } { \sim } 1 2 2 ^ { \circ } 1 5 ^ { \prime } \mathrm { E }$ 之间，地处欧亚大陆腹地。研究区为蒙古高原的草原区，行政区划上包括蒙古国的21个省市和内蒙古的12个盟市(图1)。其地势整体上呈现西高东低，

90°E 100E 110E 120°E  
No0s 乌布苏省\~ 库苏古尔省 呼伦贝尔市 No0s巴彦乌列盖省 布尔干省达尔罕鸟拉省 色勒格省HL 后杭爱省 鸟兰市 肯特省东方省 兴安盟\~v 4554  
1504 戈壁苏朱贝尔省苏赫巴托尔省戈壁阿尔泰省 前杭爱省巴彦洪戈尔省 中戈壁省戈壁省 锡林郭勒盟 通辽市图例 赤峰市海拔高度/m 南戈壁省  
N000 高：3789 阿拉善盟 市 N04中蒙国界线 鄂尔多斯市盟市界线 乌海市0 290km审图号:GS(2021)700号 L100E 110E 120E

# 干旱区地理

平均海拔高度 $1 5 8 0 \mathrm { ~ m ~ }$ 。研究区属于温带大陆性气候，气候较为干燥，四季分明且昼夜温差大，多年平均气温最高为 $2 1 . 6 ^ { \circ } \mathrm { C }$ ,最低为 $- 1 5 . 2 \ \mathrm { { ^ { \circ } C ^ { [ 2 3 ] } } }$ 。降水少且分布不均匀，年均降水量为 $2 0 0 ~ \mathrm { m m }$ ,属于干旱半干旱地区，春秋季降水量少且蒸发量大，且在每年5月初左右，草原植被返青期前，枯草量较多，在每年的10月左右植被开始枯萎凋落，可燃物量增多，极易引发草原火灾[24]

# 1.2数据资料来源

本文采用的积雪覆盖面积数据来源于美国国家冰雪数据中心NSIDC(https://nsidc.org/)提供的8 d合成的MOD10A2,空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ 。可燃物量数据（归一化植被指数，NDVI)来自NASA网站(https://ladsweb.modaps.eosdis.nasa.gov/)下载的MOD13A1,该产品是16d合成，空间分辨率为 $5 0 0 \mathrm { m }$ ○

气象数据为研究区108个气象台站2000—2016年的降水、风速、气温数据，中国境内的内蒙古气象站点数据来源于中国气象数据网(https://data.cma$\mathrm { c n / }$ ),蒙古国气象站点数据来源于蒙古国科学院地理科学研究所[25]

社会经济统计数据主要包括人口数量、牲畜数量、幼畜数量、地区生产总值、建筑物数量、非劳动人口数、牧业产值占GDP比值、人均GDP、防火人员数量、设备和资金等数据。其中内蒙古的2000—2016年统计数据来自《内蒙古统计年鉴》，防火数据来源于内蒙古自治区林业和草原局防火处，蒙古国统计数据来自于蒙古国统计网 $\mathrm { ( h t t p { : } / / 1 2 1 2 . m n / }$ ）。

# 1.3研究方法

研究方法主要包括自然灾害风险指数法，主成分分析法以及加权综合评价法。利用张继权等[17]提出的“四因子理论”，建立草原火灾风险评价模型。首先将选取的评价指标进行无量纲化处理，然后利用主成分分析[2计算其各项指标的权重系数。最后用ArcGIS软件的栅格计算功能与自然间断分类法，综合计算研究区草原火灾风险指数[27]，并将其划分为低、次低、中、次高、高5个等级。

# 2结果与分析

# 2.1蒙古高原草原火灾风险评价体系的构建

2.1.1指标构建原则大尺度草原火灾的发生是蒙古高原草原区自然环境和人为因素共同影响的结果。从火灾发生和发展机理的角度出发，考虑了指标的科学性、指标本身的真实性、实用性以及收集数据资料的难易程度等方面。从危险性、暴露性、脆弱性和防灾减灾能力4个方面选取了23个特征指标，选择的指标体现了大尺度区域的草原火灾风险特征。

2.1.2草原火灾风险评价指标建立在研究草原火灾发生的风险性评价中，指标的选取至关重要[7]本研究根据蒙古高原独特的自然地理环境和社会经济状况，建立了蒙古高原草原火灾风险评价指标体系(表1)。

（1）危险性指标选取及处理。草原火灾的危险性即草原火灾发生的可能性。结合草原火的发生机制28，综合考虑火源、可燃物特征、气象条件、地形环境等方面因素，选取了9个影响草原火灾发生的危险性因素。

人口密度：人类活动是火源的主导和不利因素，人口密度越大的地区，人为引起草原火灾的可能性就越大，反之越小。按照人口数量和每个盟市的面积求得人口密度，对每个盟市的人口密度用ArcGIS软件处理为栅格分辨率为 $5 0 0 \mathrm { m }$ 的图层。

可燃物量：可燃物是引起草原火发生的物质基础，秋季随着可燃物量增多，最能影响草原火的发生[29]。本研究选用 $5 0 0 \mathrm { ~ m ~ }$ 分辨率的MOD13A1数据来估算可燃物的量，对7、8、9月的NDVI进行最大值合成，求得多年平均值。

月均最高气温：主要通过影响火发生的周边环境而间接作用于可燃物，气温的快速升高可加速可燃物的干燥程度，进而促使可燃物较容易点燃

月均最大风速：风速能够影响草原火蔓延的速率，在一定范围内，风速越大火蔓延的速度越快。

月降水量：主要影响可燃物的含水量，当可燃物含水量越高，越不易引起草原火发生[30]。利用ArcGIS软件对3个气象要素采用克里金插值法进行插值，处理为 $5 0 0 \mathrm { m }$ 分辨率的栅格图层

积雪面积：在北方，积雪也是影响草原火发生的重要影响因素[31]。春季积雪融化后影响春季可燃物的湿度，抑制草原火的发生，而同时积雪会影响夏季植被的长势，进而影响秋季可燃物量。利用MRT批量处理MOD10A2,提取积雪像元对其进行二值化,有积雪覆盖的像元赋值为1,无积雪的赋值为0，统计赋值为1的像元个数，计算积雪面积。

高程：对植被类型的地带性分布有着重要的影响[32],同时高程还影响温度和湿度。

表1蒙古高原草原火灾风险评价指标体系及权重  
Tab.1 Risk assessment index system and weight of grassland fire on the Mongolian Plateau   

<html><body><table><tr><td>目标层</td><td>因子(权重)</td><td>次因子</td><td>指标</td><td>指标权重</td></tr><tr><td colspan="3"></td><td>人口密度/人·km</td><td>0.0460</td></tr><tr><td rowspan="10"></td><td></td><td>可燃物特征</td><td>可燃物量</td><td>0.0584</td></tr><tr><td></td><td>气象条件</td><td>月均最高气温/C</td><td>0.0431</td></tr><tr><td></td><td></td><td>月均最大风速/m·s-1</td><td>0.0560</td></tr><tr><td></td><td></td><td>月降水量/mm</td><td>0.0730</td></tr><tr><td></td><td></td><td>积雪面积/m</td><td>0.0068</td></tr><tr><td></td><td>地形环境</td><td>高程/m</td><td>0.0225</td></tr><tr><td></td><td></td><td>坡度/()</td><td>0.0193</td></tr><tr><td></td><td></td><td>坡向</td><td>0.0036</td></tr><tr><td>暴露性(0.2224)</td><td>生命暴露性</td><td>人口数量/人</td><td>0.0609</td></tr><tr><td rowspan="6">草原火灾 风险综合指标 脆弱性(0.2548)</td><td></td><td></td><td>牲畜数量/头</td><td>0.0460</td></tr><tr><td></td><td>经济暴露性</td><td>地区生产总值/元</td><td>0.0618</td></tr><tr><td></td><td></td><td>建筑物数量/间</td><td>0.0537</td></tr><tr><td>生命脆弱性</td><td>非劳动人口数/人</td><td></td><td>0.0494</td></tr><tr><td></td><td>幼畜数量/头</td><td></td><td>0.0494</td></tr><tr><td>经济脆弱性</td><td>可燃物类型</td><td></td><td>0.0540</td></tr><tr><td rowspan="6"></td><td>防灾减灾能力(0.1941)</td><td></td><td>牧业产值占GDP比值/%</td><td>0.0540</td></tr><tr><td></td><td></td><td>人均GDP/元·人-</td><td>0.0480</td></tr><tr><td></td><td>防火条件</td><td>防火人员数量/人</td><td>0.0506</td></tr><tr><td></td><td></td><td>防火设备数量/套</td><td>0.0009</td></tr><tr><td></td><td>防火资金投入/元</td><td></td><td>0.0543</td></tr><tr><td></td><td></td><td>防火隔离带/条</td><td>0.0570</td></tr><tr><td></td><td></td><td>交通条件</td><td>道路密度/km·km²</td><td>0.0312</td></tr></table></body></html>

坡度、坡向：反映了不同的地形因素。由于阳面和阴面的日照时间不同，积累的太阳能量也影响草原火蔓延。

（2）暴露性指标选取及处理。草原火灾的暴露性是指受到草原火灾威胁的人、牲畜、房屋和经济收入等。结合蒙古高原的实际情况，选取了4个影响草原火灾发生的暴露性指标，

人口数量：反映一个地区生产的基础和主体，是受草原火灾威胁的直接暴露性指标，也是灾害风险存在的必要条件。

牲畜数量：是一个地区经济收入的直接影响因素，牲畜数量越多，该地区经济收入越多。

地区生产总值：直接反应一个地区的生产生活经济能力。

建筑物数量：反应一个地区房屋建筑的经济暴露性。对每个盟市的暴露性指标用ArcGIS软件将矢量数据转为 $5 0 0 \mathrm { m }$ 分辨率的栅格图层。

（3）脆弱性指标选取及处理。草原火灾脆弱性指研究区火灾承载体的脆弱程度，即当草原火灾发生时研究区最容易受损的社会和经济指标，反映灾前对于研究区灾害发生的敏感程度，主要包括生命脆弱性和经济脆弱性，脆弱性程度越高，研究区草原火灾风险性就越大，造成灾害的损失就越严重[33]因此脆弱性选取了5个指标，

非劳动人口数：指无劳动能力的人口数量，用每个地区总人口数减去劳动力人口数量得到。非劳动人口数越多，反映生命脆弱性越高。

幼畜数量：牲畜在火灾风险中的脆弱性取决于个体的忍耐能力，幼畜忍耐力较弱，表示脆弱性越高，越容易遭受损失。

可燃物类型：表征一个地区可燃物燃烧快慢的因素,对可燃物类型进行量化[17]。

牧业产值占GDP比值：用牧区的牧业产值来衡量牧区的应灾能力，所占比值越大，脆弱性越低

人均GDP：是表征一个地区宏观经济发展的有

# 干吴区地理

效指标，可以用来衡量各盟市人民的生活水平，人均GDP越高，脆弱性越低

（4）防灾减灾能力指标选取及处理。草原火灾的防灾减灾能力指预防或减少灾害发生造成的损失，保证在草原火发生时可以及时采取相应的措施。根据研究区的实际情况及数据的可获取性选取5个指标作为防灾减灾能力指标，即防火人员数量、防火设备数量、防火资金投入、防火隔离带和道路密度。防火隔离带能够防止火势蔓延，公路网密度影响防火人员到达火场的时间。将所选5个防灾减灾指标矢量数据转为 $5 0 0 \mathrm { m }$ 分辨率的栅格图层。

2.1.3指标权重的确定基于上文建立的蒙古高原草原火灾风险评价指标体系，再采用主成分分析法对蒙古高原草原火灾风险进行指标权重的确定。

首先对每个栅格图层进行归一化处理消除量纲的影响，根据指标性质的不同，采用正负向2种类型处理[34]。若指标 $x _ { i }$ 越大，草原火发生的风险性越大，为正项指标，例如可燃物量指标就采用公式(1)处理；若指标 $x _ { i }$ 越大，草原火发生的风险性越小，为负向指标，例如防火人员数量就采用公式(2)处理。表达式如下：

$$
y _ { i } = { \frac { x _ { \operatorname* { m a x } } - x _ { i } } { x _ { \operatorname* { m a x } } - x _ { \operatorname* { m i n } } } }
$$

$$
y _ { i } = { \frac { x _ { i } - x _ { \operatorname* { m i n } } } { x _ { \operatorname* { m a x } } - x _ { \operatorname* { m i n } } } }
$$

式中： $x _ { i }$ 为指标的实际值; $x _ { \mathrm { m a x } }$ 表示指标实际值的最大值; $x _ { \operatorname* { m i n } }$ 表示指标实际值的最小值； $y _ { i }$ 表示标准化值，区间范围为(0,1)。

将标准化后的数据通过GIS分区统计功能计算34个盟市分区图层内各指标的平均值，23个指标共生成782个数据样本，作为主成分分析的原始数据。在SPSS软件中将23个指标进行主成分分析，每个主成分对应的特征值、方差贡献率和累计贡献率如表2所示。可以得知前7个主成分的累计方差贡献率达到 $8 6 . 3 5 \%$ 。根据主成分性质，超过 $8 5 \%$ 前7个主成分已经能够反映全部指标。

通过主成分分析得到的因子载荷矩阵见表3，根据得到的特征根和成分矩阵求指标权重。首先用载荷矩阵的每个主成分除以对应主成分特征根的平方根，得到每个主成分的系数。然后用每个主成分中每个指标的系数乘上所对应的贡献率，再除以7个主成分的贡献率之和，得到综合得分模型的系数。对综合得分模型中每个指标所对应的系数的绝对值进行归一化，即得到每个指标的权重，见表1。

# 2.2蒙古高原草原火灾风险分析

2.2.1危险性分析本文选取了9个指标作为草原火灾发生的危险性指标，利用地理信息系统空间分析的地图代数功能，将9个指标图层根据权重进行加权叠加，再采用自然断点分级法进行重分类，以0.097、0.113、0.128、0.145为界限值，划分为低危险区（0.056\~0.097）、次低危险区（0.097\~0.113）、中危险区（0.113\~0.128）次高危险区(0.128\~0.145）、高危险区(0.145\~0.217)。得到蒙古高原草原火灾危险性区划图(图2)。

从图2可知，蒙古高原草原火灾的危险性在蒙古国的分布呈中间向四周递减的趋势。高危险区主要分布在蒙古国北部乌兰巴托、布尔干省、后杭爱省、鄂尔浑省等附近几个盟市的草甸草原和典型草原区，而零星分布在中国内蒙古的呼伦贝尔市、兴安盟、赤峰市等盟市。对于整个研究区来说，高危险区占研究区总面积的 $1 0 . 2 4 \%$ 。次高危险区分布在蒙古国东方省、肯特省、中央省和内蒙古东北部等地区，面积占比为 $3 3 . 5 2 \%$ 。中危险区在整个研究区呈零散分布，面积占比为 $3 0 . 9 8 \%$ 。次低危险区分布在研究区的中东部地区，面积占比为 $2 3 . 2 4 \%$ ○低危险区范围很小，面积占比仅为 $2 . 0 2 \%$ ○

2.2.2暴露性分析本文选取了4个指标作为草原火灾发生的暴露性指标，利用同样的方法，将代表暴露性各栅格图层根据所求权重进行叠加，采用按自然断点分级法以 $0 . 0 0 3 \ 、 0 . 0 5 0 \ 、 0 . 0 8 9 \ 、 0 . 1 3 5$ 为界限值进行重分类，划分为低暴露区（0.000\~0.003）、次低暴露区（0.003\~0.050）、中暴露区（0.050\~0.089）、次高暴露区（0.089\~0.135）、高暴露区(0.135\~0.176)，因而得到蒙古高原草原火灾暴露性区划图(图3）。

从图3中可以得知，蒙古高原草原火灾暴露性在内蒙古和蒙古国相差很大，高暴露区几乎都分布在内蒙古地区，占研究区总面积的 $2 9 . 4 9 \%$ 。次高暴露区仅在包头市和呼和浩特市分布，面积占比为$0 . 5 8 \%$ 。中暴露区也只分布在蒙古国的乌兰巴托市和南戈壁省中部，面积占比为 $1 . 0 5 \%$ 。次低暴露区分布在蒙古国大部分地区，面积占比为 $4 9 . 6 0 \%$ 。低暴露区分布在研究区中部，面积占比为 $1 9 . 2 8 \%$ 。

# 表2各指标主成分分析

Tab.2 Principal component analysis of each indicator   

<html><body><table><tr><td rowspan="2">主成分</td><td colspan="3">初始特征值</td><td colspan="3">提取平方和载入</td></tr><tr><td>合计</td><td>方差/%</td><td>累积/%</td><td>合计</td><td>方差/%</td><td>累积/%</td></tr><tr><td>1</td><td>9.584</td><td>41.672</td><td>41.672</td><td>9.584</td><td>41.672</td><td>41.672</td></tr><tr><td>2</td><td>3.395</td><td>14.760</td><td>56.432</td><td>3.395</td><td>14.760</td><td>56.432</td></tr><tr><td>3</td><td>2.002</td><td>8.703</td><td>65.135</td><td>2.002</td><td>8.703</td><td>65.135</td></tr><tr><td>4</td><td>1.440</td><td>6.259</td><td>71.394</td><td>1.440</td><td>6.259</td><td>71.394</td></tr><tr><td>5</td><td>1.250</td><td>5.436</td><td>76.830</td><td>1.250</td><td>5.436</td><td>76.830</td></tr><tr><td>6</td><td>1.172</td><td>5.095</td><td>81.925</td><td>1.172</td><td>5.095</td><td>81.925</td></tr><tr><td>7</td><td>1.018</td><td>4.425</td><td>86.350</td><td>1.018</td><td>4.425</td><td>86.350</td></tr><tr><td>8</td><td>0.759</td><td>3.300</td><td>89.650</td><td>1</td><td>1</td><td>一</td></tr><tr><td>9</td><td>0.540</td><td>2.347</td><td>91.996</td><td>1</td><td>1</td><td>一</td></tr><tr><td>10</td><td>0.466</td><td>2.028</td><td>94.024</td><td>1</td><td>一</td><td>一</td></tr><tr><td>11</td><td>0.331</td><td>1.439</td><td>95.463</td><td>1</td><td>一</td><td></td></tr><tr><td>12</td><td>0.283</td><td>1.229</td><td>96.693</td><td>1</td><td>一</td><td>一 一</td></tr><tr><td>13</td><td>0.203</td><td>0.882</td><td>97.574</td><td>1</td><td>一</td><td>一</td></tr><tr><td>14</td><td>0.153</td><td>0.665</td><td>98.240</td><td>1</td><td>一</td><td>1</td></tr><tr><td>15</td><td>0.120</td><td>0.520</td><td>98.760</td><td>1</td><td>一</td><td>一</td></tr><tr><td>16</td><td>0.082</td><td>0.358</td><td>99.118</td><td>1</td><td>1</td><td>1</td></tr><tr><td>17</td><td>0.070</td><td>0.306</td><td>99.424</td><td>1</td><td>一</td><td>一</td></tr><tr><td>18</td><td>0.060</td><td>0.261</td><td>99.686</td><td>1</td><td>一</td><td>1</td></tr><tr><td>19</td><td>0.030</td><td>0.130</td><td>99.816</td><td>1</td><td>一</td><td></td></tr><tr><td>20</td><td>0.024</td><td>0.106</td><td>99.922</td><td>1</td><td>1</td><td>一 1</td></tr><tr><td>21</td><td>0.012</td><td>0.054</td><td>99.976</td><td>1</td><td>一</td><td></td></tr><tr><td>22</td><td>0.006</td><td>0.024</td><td>100.000</td><td>1</td><td>一</td><td>一</td></tr><tr><td>23</td><td>0.000</td><td>0.000</td><td>100.000</td><td>二</td><td>二</td><td>一 二</td></tr></table></body></html>

2.2.3脆弱性分析本文选取了5个指标作为草原火灾发生的脆弱性指标，利用同样的方法，将代表脆弱性各栅格图层根据权重进行加权叠加，采用自然断点分级法分别以0.058、0.071、0.089、0.116为界限值进行重分类，划分为低脆弱区 $\left( 0 . 0 2 0 { \sim } 0 . 0 5 8 \right)$ 、次低脆弱区（0.058\~0.071）、中脆弱区（0.071\~0.089）、次高脆弱区（0.089\~0.116）、高脆弱区(0.116\~0.149），得到蒙古高原草原火灾脆弱性区划图(图4)。

由图4可以得知，高脆弱区主要分布在内蒙古的呼伦贝尔市、通辽市、赤峰市以及包头市和乌兰察布市，占研究区总面积的 $1 0 . 8 4 \%$ 。次高脆弱区分布在内蒙古的锡林郭勒盟、巴彦淖尔市、鄂尔多斯市，以及蒙古国的后杭爱省、布尔干省、中央省、中戈壁省和肯特省的几个盟市，面积占比为 $2 7 . 7 5 \%$ 。中脆弱区主要分布在蒙古国的东方省、东戈壁省、前杭爱省、色勒格省、库苏古尔省、扎布汗省和内蒙古锡林郭勒盟西北部、赤峰市大部分，面积占比为$3 1 . 9 9 \%$ 。其他为低、次低脆弱区，面积占比为$2 9 . 4 2 \%$ 。

2.2.4防灾减灾能力分析本文选取了5个指标作为草原火灾发生的防灾减灾指标，利用同样的方法，将代表防灾减灾各栅格图层按照所求权重进行叠加，将结果按自然断点分级法进行重分类，以$0 . 0 0 7 \ 、 0 . 0 2 5 、 0 . 0 4 7 、 0 . 0 9 4$ 为界限值划分为低防灾减灾区（0.001\~0.007）、次低防灾减灾区（0.007\~0.025）、中防灾减灾区（0.025\~0.047）次高防灾减灾区 $( 0 . 0 4 7 { \sim } 0 . 0 9 4 )$ 、高防灾减灾区 $( 0 . 0 9 4 \mathrm { \sim } 0 . 1 5 1 \$ ，得到蒙古高原草原火灾防灾减灾区划图(图5)。

由图5可知，次高、高防灾减灾区分布在内蒙古呼伦贝尔市、兴安盟和鄂尔多斯市。在蒙古国的东方省和乌兰巴托市防灾减灾能力也较强，占整个研究区总面积的 $2 8 . 7 2 \%$ 。中防灾减灾区分布在内蒙古锡林郭勒盟、乌兰察布市、乌海市和包头市，以及

# 干辛区地理

# 表3各指标初始因子载荷矩阵

Tab.3 Initial factor load matrix of each indicator   

<html><body><table><tr><td rowspan="2">指标</td><td colspan="7">成分矩阵</td></tr><tr><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td></tr><tr><td>人口密度</td><td>0.283</td><td>-0.078</td><td>0.783</td><td>0.193</td><td>-0.088</td><td>-0.084</td><td>0.263</td></tr><tr><td>可燃物量</td><td>0.396</td><td>0.871</td><td>0.025</td><td>-0.056</td><td>-0.101</td><td>-0.089</td><td>0.137</td></tr><tr><td>月均最高气温</td><td>-0.759</td><td>-0.163</td><td>0.211</td><td>0.043</td><td>0.020</td><td>-0.108</td><td>0.379</td></tr><tr><td>月均最大风速</td><td>-0.926</td><td>0.088</td><td>-0.080</td><td>0.149</td><td>-0.065</td><td>0.063</td><td>0.028</td></tr><tr><td>月降水量</td><td>0.596</td><td>0.700</td><td>0.058</td><td>0.027</td><td>0.088</td><td>-0.089</td><td>0.153</td></tr><tr><td>积雪面积</td><td>-0.311</td><td>0.674</td><td>0.214</td><td>-0.173</td><td>-0.281</td><td>0.371</td><td>-0.145</td></tr><tr><td>高程</td><td>-0.622</td><td>-0.092</td><td>-0.026</td><td>0.602</td><td>-0.019</td><td>0.405</td><td>-0.058</td></tr><tr><td>坡度</td><td>-0.330</td><td>0.609</td><td>-0.011</td><td>0.480</td><td>-0.138</td><td>0.381</td><td>-0.019</td></tr><tr><td>坡向</td><td>-0.443</td><td>0.125</td><td>0.338</td><td>-0.065</td><td>0.637</td><td>-0.075</td><td>0.277</td></tr><tr><td>人口数量</td><td>0.898</td><td>-0.011</td><td>-0.109</td><td>0.196</td><td>-0.108</td><td>-0.064</td><td>0.191</td></tr><tr><td>牲畜数量</td><td>0.851</td><td>-0.071</td><td>-0.340</td><td>-0.151</td><td>0.021</td><td>0.181</td><td>0.086</td></tr><tr><td>地区生产总值</td><td>0.804</td><td>-0.250</td><td>0.016</td><td>0.278</td><td>0.132</td><td>0.217</td><td>0.116</td></tr><tr><td>建筑物数量</td><td>0.717</td><td>-0.158</td><td>0.060</td><td>0.501</td><td>-0.065</td><td>-0.099</td><td>0.070</td></tr><tr><td>非劳动人口数</td><td>0.819</td><td>0.013</td><td>-0.212</td><td>0.107</td><td>-0.162</td><td>-0.091</td><td>0.196</td></tr><tr><td>幼畜数量</td><td>0.600</td><td>0.049</td><td>0.188</td><td>0.407</td><td>0.199</td><td>-0.248</td><td>-0.346</td></tr><tr><td>可燃物类型</td><td>0.389</td><td>0.852</td><td>-0.065</td><td>-0.035</td><td>-0.093</td><td>-0.165</td><td>0.163</td></tr><tr><td>牧业产值占GDP 比值</td><td>-0.717</td><td>0.075</td><td>-0.458</td><td>0.154</td><td>0.222</td><td>-0.136</td><td>-0.076</td></tr><tr><td>人均GDP</td><td>0.775</td><td>-0.407</td><td>0.321</td><td>0.036</td><td>-0.004</td><td>0.135</td><td>-0.049</td></tr><tr><td>防火人员数量</td><td>0.623</td><td>-0.113</td><td>-0.252</td><td>-0.143</td><td>0.258</td><td>0.460</td><td>0.381</td></tr><tr><td>防火设备数量</td><td>0.578</td><td>-0.372</td><td>-0.148</td><td>-0.127</td><td>-0.505</td><td>-0.065</td><td>-0.065</td></tr><tr><td>防火资金投入</td><td>0.692</td><td>0.320</td><td>-0.030</td><td>0.101</td><td>0.311</td><td>-0.208</td><td>-0.394</td></tr><tr><td>防火隔离带</td><td>0.721</td><td>0.104</td><td>-0.097</td><td>-0.183</td><td>0.369</td><td>0.379</td><td>-0.226</td></tr><tr><td>道路密度</td><td>0.256</td><td>-0.006</td><td>0.740</td><td>-0.270</td><td>-0.058</td><td>0.225</td><td>-0.223</td></tr></table></body></html>

![](images/c29d699cc89cf1f824996d8b8c495698f189c3b06421d7a52d9947556f9ca18c.jpg)  
图2蒙古高原草原火灾危险性区划图  
Fig.2 Hazard distribution of grassland fire on the Mongolian Plateau

![](images/98e762bb1a4d7772c9a1f4fe4059b17990bda76a8af2bcc471cfef2cb3ef87bd.jpg)  
Fig.3Exposure distribution of grassland fire on the Mongolian Plateau

![](images/008337c5eefca4048d619461d06530e2d27a4f51b8f91e93206f9140b776c214.jpg)  
图3蒙古高原草原火灾暴露性区划图  
图4蒙古高原草原火灾脆弱性区划图  
Fig.4Vulnerability distribution of grassland fire on the Mongolian Plateau

蒙古国的苏赫巴托尔省、中央省、库苏古尔省和戈壁阿尔泰省，面积占比为 $3 3 . 7 0 \%$ 。次低和低防灾减灾区大都分布在蒙古国西北部，面积占比为

$3 7 . 5 8 \%$ 。

2.2.5草原火灾风险综合评价分析根据蒙古高原  
4个一级指标危险性、暴露性、脆弱性、防灾减灾能

# 干吴区地理

![](images/c2d55708474dc17e5ac9d3d8fdc361d81728489abed027ea8c5c4e3f989cd04c.jpg)  
图5蒙古高原草原火灾防灾减灾区划图  
Fig.5Distribution of grassland fire disaster prevention and mitigation on the Mongolian Plateau

力区划图，按照权重0.3287、0.2224、0.2548、0.1941采用加权综合评价法计算草原火灾风险值，并根据自然断点法分为5个等级：低风险区（0.022\~0.050）、次低风险区（0.050\~0.058）、中风险区（ $\phantom { - } 0 . 0 5 8 \sim$ 0.067）、次高风险区 $\left( 0 . 0 6 7 { \sim } 0 . 0 8 3 \right)$ 、高风险区(0.083\~0.110)，得到蒙古高原草原火灾综合性风险区划图(图6)。

由图6可知，高风险区主要分布在内蒙古呼伦贝尔市、通辽市北部、赤峰市西北部、锡林郭勒盟东北部，以及呼和浩特市北部地区，占整个研究区总面积的 $1 8 . 9 9 \%$ 。次高风险区主要分布在锡林郭勒盟西部、包头市南部和鄂尔多斯西部以及兴安盟大部零星分布，面积占比为 $1 1 . 5 6 \%$ 。中风险区大部分分布在蒙古国乌兰巴托市周围的几个盟市，以及内蒙古地区的乌兰察布市和巴彦淖尔市等地区，面积占比为 $2 8 . 3 7 \%$ 。次低和低风险区主要分布在内蒙古的阿拉善盟和乌海市，以及蒙古国的东部草原和西部高山区，面积占比为 $4 1 . 0 8 \%$ ○

# 3讨论

本文运用主成分分析法筛选23个草原火灾评价指标，得到的评价结果基本和其他研究学者[]指标权重结果一致，说明主成分分析法用于评价草原火灾风险是可行的。

从危险性指标权重来看，月降水量和可燃物量权重值较高，对蒙古高原草原火灾危险性影响较大。由图2可知呈现高危险区的地区主要分布在蒙古国北部，可燃物量选择的是7、8、9月NDVI,该地区降水量充足，草原生长条件好[35],可燃物量较多，影响草原火灾的发生。在我国大兴安岭山脉一带草地枯落物更多，因此草原火灾发生危险性也更大。对比暴露性指标权重可知，地区生产总值和人口数量所占权重相对较高，人口较多地区的人类活动和景观破坏也致使火灾风险性较大[36]。蒙古高原草原火灾次高、高暴露区都分布在内蒙古境内，只有阿拉善盟呈中暴露区;蒙古国除了乌兰巴托市和南戈壁省外其他地区都是低暴露区，乌兰巴托市呈中暴露区；这可能是由于内蒙古人口数量较多，地区生产总值远远高于蒙古国，提高了综合值。由脆弱性指标权重可知，可燃物类型和牧业产值占GDP比值权重较高，研究区草原火灾脆弱性受可燃物类型影响呈现零散分布，次高、高脆弱区大多分布在草甸草原和典型草原上。从防灾减灾能力来看，主要是内蒙古省内有防火隔离带，所占权重值较高。另外，一个地区的防灾减灾能力也取决于该地区是否经常发生火灾，内蒙古的呼伦贝尔市、兴安盟处于火灾多发区，防火意识较强，分配在防灾资金投入就比较多。

![](images/1140d74f6d24602ae74ac7723fbb576950c2f6a197995368cb8ccb9b2c0c2fe5.jpg)  
图6蒙古高原草原火灾综合性风险区划图  
Fig.6Comprehensive risk distribution of grassland fire on the Mongolian Plateau

经分析表明，内蒙古的草原火灾风险自东向西呈递减的趋势，这与都瓦拉的研究结果一致。虽然从结果上看蒙古国的东方省和苏赫巴托尔省呈次低风险区，只有靠近兴安盟地区呈中风险，但我国境内呼伦贝尔、锡林郭勒盟等地边境地区都是高风险区，草原可燃物量较高，人口较少，并处于中、高防灾减灾区，只要蒙古国发生起火，蔓延至我国就会引起草原大型火灾，此区域应做好防灾减灾措施。绘制草原火灾风险图可以为消防组织的规划提供决策支持，从而可以确定火灾风险较高的地区，预防火灾可能蔓延的情况，并采取必要的措施[38]。此外，当地相关部门应该在该地区的火灾季节采取措施防止草原火灾，并通过媒体和其他通信手段提高人们的防范意识。

本文还存在一些不足之处。由于草原火灾成因复杂，研究区过大，随着研究的深人还需不断调整评价体系。自然灾害是不可避免的，不可能完全弥补灾害所造成的损失。但在某种程度上，可以通过制定灾害预警措施、执行计划来提供对灾后的复原力和帮助灾后减少损失，从而尽可能减少潜在的火灾风险。

# 4结论

本文以大尺度区域蒙古高原草原作为研究区，构建了蒙古高原草原火灾评价指标体系，结合GIS技术计算研究区草原火灾风险值，得到风险区划图，结论如下：

（1）蒙古高原草原火灾危险性从中部区域向四周逐渐递减，高危险区占研究区总面积的 $1 0 . 2 4 \%$ ·草原火灾暴露性整体上由东北部向西部递减，高暴露区占研究区总面积的 $2 9 . 4 9 \%$ ;草原火灾高脆弱性分布在蒙古高原北部以及中部，高脆弱区占研究区总面积的 $1 0 . 8 4 \%$ ;草原火灾防灾减灾能力从东北部向西部地区递减，次低防灾减灾区占研究区总面积的 $1 6 . 3 6 \%$ 。

(2）蒙古高原草原火灾风险整体上内蒙古东北部风险较高，呈现自东向西递减趋势;蒙古国风险等级由中间向四周递减趋势。高风险区占研究区

# 干吴区地理

总面积的 $1 8 . 9 9 \%$ ，高风险地区应该加强对草原火灾的防范意识和防火能力。

# 参考文献(References)

[1]崔亮.内蒙古呼伦贝尔草原火灾风险预警研究[D].长春:东北 师范大学,2O11.[Cui Liang.A study on early warning of grassland fire disaster risk in Hulunbeierof Inner Mongolia[D]. Changehun: Northeast Normal University,2011.]   
[2]JohnstonL M, Wang X,Erni S,etal.Wildland fire risk research in Canada[J]. Environmental Reviews,2020,28(2): 164-186.   
[3]姜莉,玉山,乌兰图雅,等.草原火研究综述[J].草地学报,2018, 26(4): 4-16.[Jiang Li, Yushan, Wulantuya, et al.Summaryof grassland fire research[J].Acta Agrestia Sinica,2018,26(4):4-16.]   
[4]曲炤鹏,郑淑霞,白永飞,等.蒙古高原草原火行为的时空格局 与影响因子[J].应用生态学报,2010,21(4):807-813.[Qu Chaopeng, Zheng Suxia,Bai Yongfei, et al. Spatiotemporal patterns and driving factorsof grassland fireon Mongolian Plateau[J]. Chinese Journal of Applied Ecology,2010,21(4): 807-813.]   
[5]Rasooli SB,Bonyad A E.Evaluating the efficiency of the Dong model in determining fire vulnerability in Iran's Zagros Forests[J]. Journal of Forestry Research,2019,30(4): 1447-1458.   
[6]萨如拉,张鑫,韩霄,等.1981—2015年内蒙古自治区草原火灾 时空动态研究[J].消防科学与技术,2019,38(3):421-425.[Sarula, Zhang Xin,Han Xiao, et al. Studies on the temporal and spatial dynamics of grassland fires in Inner Mongolia from 1981 to 2015[J].Fire Science and Technology,2019,38(3): 421-425.]   
[7]Liu X P, Zhang G Q,Lu J, et al. Risk assessment using transfer learning for grassland fires[J].Agricultural and Forest Meteorology,2019,269-270: 102-111.   
[8]杨光,腾跃,舒立福,等.“一带一路"沿线区域森林草原防火概 述[J].世界林业研究,2018,31(6):82-88.[Yang Guang,Teng Yue,Shu Lifu, et al.Review of forest and grassland fire prevention along“the Belt and Road"[J]. World Forestry Research,2018,31 (6): 82-88.]   
[9]杨存建,冯凉,杨洪忠,等.四川省林草火险等级评价[J].地理研 究,2010,29(6): 980-988.[Yang Cunjian,Feng Liang, Yang Hongzhong,et al. Study of evaluation of forest and grass fire risk grade in Sichuan Province[J]. Geographical Research, 2010, 29(6): 980- 988.]   
[10] 王卫国,潘竟虎,李俊峰.基于空间Logistic的山西省火灾风险 评价与火险区划[J].草业科学,2016,3(4): 635-644.[Wang Weiguo,Pan Jinghu, Li Junfeng.Assessment and zoning of fire risk in Shanxi Province based on spatial Logistic model[J]. Pratacultural Science,2016,33(4): 635-644.]   
[11]Benguerai A,Benabdeli K,Harizia A. Forest fire risk assessment model using remote sensing and GIS techniques in northwest Algeria[J].Acta Silvatica et Lignaria Hungarica,2O19,15(1): 9-21.   
[12] 慕臣英,徐全辉,张菁,等.RS和GIS技术在沈阳市火灾监测中 的应用研究[J].中国农学通报,2016,32(9):179-182.[Mu Chenying, Xu Quanhui, Zhang Jing,et al.Application of RS and GIS in fire disaster monitoring in Shenyang[J]. Chinese Agricultural Science Bullein,2016,32(9): 179-182.]   
[13]Maselli F,Rodolfi A, Bottai L,et al.Classification of Mediteranean vegetation by TM and ancillary data for the evaluation of fire risk[J].International Journal of Remote Sensing,2000,21(17): 3303-3313.   
[14] Eugenio FC,Santos A R D,Fiedler N C,et al. Applying GIS to develop a model for forest fire risk: A case study in Espirito Santo, Brazil[J]. Journal of Environmental Management,2O16,173(15): 65-71.   
[15]Naderpour M, Rizeei H M, Khakzad N,et al. Forest fire induced Natech risk assessment: A survey of geospatial technologies[J]. Reliability Engineering and System Safety,2019,191: 106558,doi: 10.1016/j.ress.2019.106558.   
[16]Adab H, Kanniah KD,Solaimani K. Modeling forest fire risk in the northeast of Iran using remote sensing and GIS techniques[J]. Natural Hazards,2013,65(3): 1723-1743.   
[17] 张继权,刘兴朋,佟志军,等.草原火灾风险评价与分区——以 吉林省西部草原为例[J].地理研究,2007,26(4):755-762. [Zhang Jiquan,Liu Xingpeng,Tong Zhijun,et al. The study of grassland fire disaster risk assessment and regionalization: A case study in the western Jilin Province[J]. Geographical Research, 2007, 26(4): 755-762.]   
[18]Laxmi K S, Shruti K, Mahendra S N,et al. Fuzzy AHP for forest fire risk modeling[J]. Disaster Prevention and Management, 2012, 21(2): 160-171.   
[19] Bian HF,Zhang HY,Zhou D W,et al.Integrating models to evaluate and map grassand fire risk zones in Hulunbuir of Inner Mongolia, China[J].Fire Safety Journal,2013,61: 207-216.   
[20] 张继权,刘兴朋.基于信息扩散理论的吉林省草原火灾风险评 价[J].干旱区地理,2007,30(4): 590-594.[Zhang Jiquan,Liu Xingpeng.Risk assessment of grassland fire in Jilin Province basedoninformationdifusiontheory[J].AridLandGeography, 2007, 30(4): 590-594.]   
[21] 丽娜,包玉龙,银山,等.中蒙边境地区草原火时空分布特征分 析[J].灾害学,2016,31(3):207-210.[Lina,Bao Yulong,Yinshan,et al. Spatiotemporal characteristics of grassland fire in China-Mongolia border area[J]. Journal of Catastrophology,2016,31 (3): 207-210.]   
[22] 陈鹏宇,赵凤君,舒立福,等.蒙古森林草原火灾状况及林火管 理[J].世界林业研究,2014,27(2):66-69.Chen Pengyu, Zhao Fengjun, Shu Lifu,et al. Firesand fire management on forest steppe in Mongolian[J]. World Forestry Research,2014,27(2): 66- 69.]   
[23] 姜康,包刚,乌兰图雅,等.基于MODIS数据的蒙古高原积雪时 空变化研究[J].干旱区地理,2019,42(4):782-789.[Jiag Kang, Bao Gang, Wulantuya,et al. Spatiotemporal changes of snow cover in Mongolian Plateau based on MODIS data[J]. Arid Land Geogra

phy,2019,42(4): 782-789.]

[24] 张艳珍,王钊齐,杨悦,等.蒙古高原草地退化程度时空分布定 量研究[J].草业科学,2018,35(2):233-243.[Zhang Yanzhen, Wang Zhaoqi, Yang Yue,et al. Research on the quantitative evaluation of grassland degradation and spatial and temporal distribution on the Mongolia Plateau[J].Pratacultural Science,2O18,35 (2): 233-243.]   
[25]包刚,包玉海,覃志豪,等.近10年蒙古高原植被覆盖变化及其 对气候的季节响应[J].地理科学,2013,33(5):613-621.[Bao Gang,Bao Yuhai,Qin Zhihao,et al.Vegetation cover changes in Mongolian Plateau and its responseto seasonal climate changes in recent 10 years[J].Scientia Geographica Sinica,2013,33(5): 613-621.]   
[26] 韩群柱,冯起,高海东,等.基于主成分分析的关中地区农业粮 食生产变化的影响因素研究[J].干旱区地理,2020,43(2):474- 480.[Han Qunzhu,Feng Qi, Gao Haidong,et al. Influencing factors of agricultural production changes in Guanzhong based on PCA[J]. Arid Land Geography,2020,43(2): 474-480.]   
[27] 徐玉霞,许小明,方锋,等.县域尺度下的宝鸡市农业洪水灾害 脆弱性评价及区划[J].干旱区地理,2020,43(3):652-660.[Xu Yuxia,Xu Xiaoming,Fang Feng,et al. Assessment and zoning of vulnerability of agricultural flood diaster in Baoji City based on county scale[J]. Arid Land Geography,2020,43(3): 652-660.]   
[28] 王啟德,闫德民,郭宇,等.内蒙古草原火灾发生规律及影响因 素研究[J].森林防火,2019(3):38-42.[Wang Qide,Yan Demin, Guo Yu,et al. Study on the occurrence law and influencing factors of grassland fire in Inner Mongolia[J].Forest Fire Prevention,2019 (3): 38-42.]   
[29] 陈帅,陶骏骏,王振师,等.火行为对森林地表可燃物燃烧碳转 化的影响[J].燃烧科学与技术,2018,24(2):177-185.[Chen Shuai,Tao Junjun,Wang Zhenshi,et al. Effects of fire behavior on carbon conversion rates of surface fire in wildland[J]. Journal of Combustion Science and Technology,2018,24(2):177-185.]   
[30]刘柯珍.大兴安岭地区夏季火环境及林火发生预报模型研究 [D].北京:中国林业科学研究院,2018.[Liu Kezhen.Fire environment and forecasting models of summer forest fire in Daxing' an Mountain district[D]. Beijing: Chinese Academy of Forestry Sci

ences,2018.]

[31] 红英.积雪对草原火发生的影响研究[D].长春:东北师范大学, 2016.[Hong Ying.Study the effecting of snow distribution on grassland fire occurrence[D]. Changchun: Northeast Normal University,2016.]   
[32] 刘丹,于成龙.气候变化对东北主要地带性植被类型分布的影 响[J].生态学报,2017,37(19):6511-6522.[Liu Dan,Yu Chenglong.Effects of climate change on the distribution of major zonal vegetation types in northeast China[J]. Acta Ecologica Sinica, 2017,37(19): 6511-6522.]   
[33] Paveglio TB,Edgeley C M,Stasiewicz A M.Assessing influences on social vulnerability to wildfire using surveys,spatial data and wildfire simulations[J]. Journal of Environmental Management, 2018,213:425-439.   
[34] 曹丽娟,张小平.基于主成分分析的甘肃省水资源承载力评价 [J].干旱区地理,2017,40(4): 906-912.[Cao Lijuan, Zhang Xiaoping. Assessment of water resources carrying capacity in Gansu Province based on principal component analysis[J].Arid Land Geography,2017,40(4): 906-912.]   
[35] 温都日娜.基于MODIS 数据的蒙古高原植被覆盖变化及其对 水热条件的响应[D].呼和浩特:内蒙古师范大学,2017.[Wendurina.Research on spatiotemporal changes of vegetation cover and its response to hydrothermal conditions in the Mongolian Plateau using MODIS data[D]. Hohhot: Inner Mongolia Normal University,2017.]   
[36]Wu RH, Zhao JJ, Zhang HY,et al.Wildfires on the Mongolian Plateau: Identifying driversand spatial distributions to predict wildfire probability[J].Remote Sensing,2019,11(2O): 2361,doi: 10.3390/rs11202361.   
[37]都瓦拉.内蒙古草原火灾监测预警及评价研究[D].北京：中国 农业科学院,2012.[Duwala.A study of grassland fire monitoring and early warning and assessment Inner Mongolia[D]. Beijing: Chinese Academy of Agricultural Sciences, 2012.]   
[38]Liu X, Zhang J,Cai W,et al. Information diffusion-based spatiotemporal risk analysis of grassland fire disaster in northern China [J]. Knowledge-Based Systems,2010,23(1): 53-60.

# Risk assessment of grassland fire on the Mongolian Plateau

YANG Xiaoying'，Yushanl²，Duwala³，Hongmei' (1.Colleg ofGeograpicience,IerMongoliaNoralUniversityHohhotOO22,InerMongolia,China;2.Ierogoia KeyLaboratoryof RemoteSensingand Geographic InformationSystems,HohhotOloO22,InnerMongolia, China;3.Grsland Research Institute,Chinese Academy of Agricultural Sciences,Hohhot OloolO,Inner Mongolia, China）

Abstract: Grassland fires are a major type of natural disaster in pastoral areas and can seriously aect their socioeconomic securityand physical safety.To assess the risk of grassland fire on the Mongolian Plateau, index layer data of each league and city were obtained from 2000 to 2016.Then,a risk assessment index system for grassland fire on the Mongolian Plateau was screened and constructed according to four risk elements of natural disasters: hazard, exposure,vulnerability,and prevention/mitigation capability.The index weight was determined through principal component analysis,and a fire risk distribution map of Mongolian Plateau grassland was generated by using the spatial analysis function of a geographic information system.The results were as follows. (1)The principal component analysis obtained seven principal components,which reduced the number of indices and accurately identified the risk factors of grassland fire sources. (2)Areas with a high hazard of grassland fire were distributed in the central part of Mongolia,and the hazard decreased in the surrounding areas.Areas with high exposure were distributed in the northeastern part of Inner Mongolia. Areas with high vulnerability were distributed in the northern partof Inner Mongolia and Kent Province of Mongolia.Areas with strong disaster prevention and mitigation capabilities were mainly distributed in Hulunbuir City,the Xing'an League,and Ordos City of Inner Mongolia. (3) Generally,the northeastern part of Inner Mongolia had a higher risk of grassland fire than the western part,and the risk decreased from east to west and from the center of Mongolia to the surrounding areas.Low-risk,semi-low-risk,medium-risk,semi-high-risk,and high-risk areas accounted for $4 . 8 6 \%$ ， $3 6 . 2 0 \%$ $2 8 . 3 7 \%$ ， $1 1 . 5 6 \%$ ,and $1 8 . 9 9 \%$ , respectively, of the grassland area of the Mongolian Plateau. On the basis of the geographical environment characteristics and economic development level of each league and city in China and Mongolia,fire prevention strategies can be devised to reduce the risk of grassand fire and guide the sustainable development of grassland animal husbandry.

Key words: grassland fire disaster; risk assessment; principal component analysis; GIS；Mongolian Plateau