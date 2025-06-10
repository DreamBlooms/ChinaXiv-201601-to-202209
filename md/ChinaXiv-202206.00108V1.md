# 基于AlphaShape算法的分散式乡村聚落形状划分及其形成研究以米脂县龙镇为例

王天宇，惠怡安，芮盼盼，师莹(西北大学城市与环境学院，陕西 西安710127)

摘要：为了定量划分分散式乡村聚落的形状类型并探究其形成原因，以陕北黄土丘陵沟壑区米脂县龙镇为例，尝试使用Alpha Shape算法对聚落形状进行提取，通过Boyce-Clark指数计算并划分聚落形状类型，最后结合多元线性回归和回归树的方法探究影响聚落形状的因素。结果表明： $1 0 0 \mathrm { m }$ 滚动半径下，AlphaShape算法能够提取 $7 6 . 1 \%$ 聚落的精确轮廓；研究区乡村聚落形状类型可以分为块状矩形及其变种、延伸形、哑铃形和串珠形、带状矩形及其组合、线形5种,Boyce-Clark指数依次增加；高程和Boyce-Clark指数呈显著正相关，水资源可获取性与Boyce-Clark指数在高海拔地区呈负相关，聚落面积与Boyce-Clark指数先呈负相关后呈正相关。研究结果可为分散式聚落生活空间边界的划定提供参考，增进对黄土丘陵沟壑区分散式聚落形态的认识。

关键词：乡村聚落；形状类型；Alpha Shape算法；Boyce-Clark指数；黄土丘陵沟壑区文章编号：

黄土丘陵沟壑区是典型的半干旱区，也是实现黄河流域生态保护与高质量发展的重要地区。该区域沟壑纵横、地形破碎,分散式乡村聚落众多[1]。识别乡村聚落形态的特征及其影响因素对于理解乡村聚落的形成，规划乡村聚落物质空间，合理配置基础设施、公共服务设施具有重要作用。集中式聚落由于其形态较为完整，相关研究已经较为成熟，而分散式聚落由于聚落轮廓难以识别其形态亦鲜有研究涉及。

目前识别乡村聚落形态主要有2种方法：人工识别和机器识别。人工识别一般依据特定的规则，对聚落形状或边界进行手动提取，比如浦欣成以建筑斑块的顶点生成连接线，通过设定 $1 0 0 ~ \mathrm { m } , 3 0$ $ { \mathrm { ~ m ~ } } , 7  { \mathrm { ~ m ~ } }$ 的长度得到不同精度下的聚落边界，谢丹等[3-4]基于这一方法分别对海南省北部和贵州喀斯特山区乡村形态进行了研究。这种方法需要基于村庄地形图人工提取村落边界，且对于散点式的聚落并不适用。机器识别是指人工设定识别规则，利用计算机对聚落形状进行提取，该类方法能够克服人工提取工作量较大的问题。董一帆通过Delaunay三角网计算建筑物之间影响距离，叠加建筑物之间的凸包来提取村落轮廓[5]，该研究同样需要聚落CAD平面图，对数据精度要求较高。

对于乡村聚落形状类型划分及其影响因素研究，早期研究一般使用定性方法对聚落形态类型进行人为划分，且划分标准较多涉及聚落环境、人口规模等非形态特征,金其铭根据聚落的规模、密度、耕作半径将江苏省农村聚落形态分为团聚状和条带状。定量研究一般综合聚落经济环境、空间格局等指标，通过聚类分析等方法对聚落类型进行划分[8-10],如马晓冬等[8]使用系统聚类对聚落7种景观格局指数进行分析，从而划分团簇、宽带、条带等8种形态类型。此类研究虽然定量程度有所提高，但是聚类分析的结果往往难以对形态类型进行直接判断。对于聚落形态影响因素，已有研究表明自然环境因素是聚落形态形成的基础因素，其中高程、坡度对于聚落形态影响较大[1I-12],水资源对于干旱区聚落形态有较强的约束作用[13-14]。此外,社会因素如风水、宗族、政策、经济水平等也对聚落形态存在一定程度影响[15-16],如王浩锋[17]基于空间句法研究了聚落空间形态和经济、社会组织之间的规律性。整体来看，对于影响因素的研究主要通过线形回归等方法分析地形、交通等因素和聚落形态特征间的相关性[12.15.18],然而聚落形态和各类影响因素之间并非完全线性相关，对于非线性关系的研究较为缺乏。

综上，目前对于分散式聚落形态识别的方法较为欠缺，已有方法存在计算量较大、数据要求较高等问题，此外对于形态类型的划分定量程度不高，且针对形态的非线性影响因素探讨较少。因此，本文以黄土丘陵沟壑区的米脂县龙镇为例，尝试使用AlphaShape算法提取分散式聚落的聚落边界，在此基础上将城市形态研究中的Boyce-Clark(BC)指数引人乡村研究，提高形状类型划分的科学性，最后结合多元线性回归和回归树，探讨并分析聚落形状与影响因素之间线性、非线性关系，以期补充该区域乡村聚落形态研究。

# 1研究区、数据与方法

# 1.1 研究区概况

本研究选取的区域为榆林市米脂县龙镇，龙镇位于米脂县西北部，距县城 $2 5 \mathrm { k m }$ ,总面积 $1 3 6 \mathrm { k m } ^ { 2 }$ 。该区域属于典型的黄土丘陵沟壑区，5a平均年降水量 $5 5 2 \mathrm { m m }$ 。龙镇位于无定河中游西侧,整体地貌形态为一川两沟(图1)，一川即无定河的川道，两沟即马湖峪沟(当地称龙来沟)和杨正沟(当地称黑石窑沟），两沟均为无定河的支流。交通条件较为便利，榆(林)商(洛)高速从镇区东部边沿经过，出入口亦在本镇，神(木)延(安)铁路穿越镇域东部。研究区经历过大规模迁村并点后行政村数量只有28个，考虑到合并之后的行政村包含自然村过多，分布范围过大，并不适合作为形态分析对象，本文采用合并之前的聚落作为分析对象，共计58个自然村。

# 1.2数据来源

本研究数据包括空间矢量、栅格数据。矢量数据为榆林米脂县龙镇行政边界和米脂县龙镇2019年土地利用数据,该数据由龙镇政府提供,地理坐

![](images/6180908b5628f0282103c5f9a59274f52a4eb2a8f7bcdf288174e7eaee475a41.jpg)  
图1龙镇地形图  
Fig.1 Topographic map ofLong Town

标系为CGCS2000和西安80坐标系。栅格数据为2012年米脂县1弧秒分辨率SRTM数字高程数据，来源于地理空间数据云(http://www.gscloud.cn/）。

# 1.3 研究方法

1.3.1 Alpha Shape算法Alpha Shape是计算散点轮廓的算法。假设空间中有 $s$ 个点，若是求S个点的最小凸包会得到一个包含所有点的封闭平面的交集(图 $2 \mathrm { a }$ )。可以看出，点集的最小凸包并不能较好描述散点的轮廓，因为凹陷处并没有被体现出来。Alpha Shape算法实际上是基于通过任意2点的半径为 $\mathbf { \alpha } _ { a }$ 的圆生成的，在给定半径 $a$ 时，过任意2点能够画出2个圆，算法规定当画出的圆内不包含其他点时这2点可以被看作为边界点，对所有的点进行计算可以得出散点边界。当半径 $a$ 过大时算法得出的轮廓较为粗糙，接近最小凸包，而当 $a$ 足够小时轮廓细节则会更多，甚至包括点集内部的空洞。图2b深色部分是在给定半径 $\mathbf { \Omega } _ { a }$ 的情况下利用AlphaShape算法得到的散点轮廓，可以看出该轮廓明显小于最小凸包,并且对散点凹陷处刻画较好。由于半径 $\mathbf { \alpha } _ { a }$ 为固定值，因此当2点距离过大时在算法中会被舍弃，如果不对 $a$ 进行设定，那么默认情况下 $a$ 为最小值，即平面所有点中距离最近2点间距的一半。在实际应用中需要调整 $a$ 的值以保证大部分居住用地可以被轮廓覆盖

半径 $a$ 可以看为建筑的影响范围，即外部空间的范围。浦欣成根据人与人之间的关系、乡村空间实际情况将距离分为 $1 0 0 \mathrm { m } . 3 0 \mathrm { m } . 7 \mathrm { m }$ ，其中100$\mathrm { ~ m ~ }$ 是社会性视域的最高限。此外,研究比较了 $5 0 \mathrm { m }$ 、$7 0 \mathrm { m } , 1 0 0 \mathrm { m } , 1 5 0 \mathrm { m }$ 半径对聚落形状的提取效果，其中 $5 0 \mathrm { m } \cdot 7 0 \mathrm { m }$ 会导致聚落多轮廓概率提升， $1 5 0 \mathrm { m }$ 和$1 0 0 \mathrm { m }$ 在聚落轮廓数量上差别不大，但提取精度较低，因此本研究采用 $1 0 0 \mathrm { ~ m ~ }$ 作为外部空间的范围。具体计算步骤是，使用ArcGIS中的渔网工具创建点阵，与建筑物斑块相匹配。将点坐标以数值矩阵的格式导人Matlab,利用AlphaShape 函数计算轮廓。通过Matlab的BoundaryFacets函数生成边界坐标矩阵，导入ArcGIS后得到边界点集，当存在多个面时需要手动连接各点。

![](images/b13fd3093dc457945d01b6f7e23bf985ed191ceefa7527a4094fddba309a6f46.jpg)  
图2散点最小凸包和Alpha Shape算法结果对比  
Fig.2 Comparison of minimum convex hull and Alpha Shape results

1.3.2Boyce-Clark指数对于边界形状的测度，目前方法较多，BC指数被认为是一种较好的方法，该指数是将聚落边界形状与基于特定半径生成的标准圆进行对比得出[19]。标准圆圆心的选择对计算结果影响较大，本研究采用面的质心作为标准圆圆心。在计算过程中，从圆心出发的辐射线(半径)可能与边界有多个交点，因此需要对此进行定义，为了保证聚落所有范围均能覆盖，将距离圆心最远的交点定义为半径，具体计算公式如下：

$$
\mathrm { B C } = \sum _ { i = 1 } ^ { n } \left[ \left[ \frac { r _ { i } } { \displaystyle \sum _ { i = 1 } ^ { n } r _ { i } } \right] \times 1 0 0 - \frac { 1 0 0 } { n } \right] \
$$

式中：BC为Boyce-Clark指数; $n$ 为某一轮廓内从质心出发的辐射线数量； $r _ { i }$ 为从面的质心到图形边缘的第 $i$ 条半径长度 $( \mathrm { k m } )$ 。

BC指数精度取决于 $n$ 值的大小， $n$ 值越大表明生成的辐射线间隔角度越小，计算结果越精确。本文参照相关学者研究，将 $n$ 设置为32，辐射线间隔为$1 1 . 5 ^ { \circ [ 2 0 ] }$ 。计算过程在ArcGIS的python界面完成,首先确定各个聚落轮廓面的质心，接着基于质心以$1 1 . 2 5 ^ { \circ }$ 间隔生成辐射线，计算每个辐射线长度代入上述公式中计算，得到每个轮廓面的BC指数。对于拥有2个轮廓面的聚落，根据不同情况采取不同处理方法。当2种轮廓面BC指数较为接近时，采用面积加权的方式计算平均值，当轮廓面BC指数相差较多时，可以将该村落定义为组合形态，并单独分析各个面的BC指数。面积加权方法公式如下：

$$
\mathrm { B C _ { a } } = { \frac { A _ { 1 } } { A } } \mathrm { B C _ { 1 } } + { \frac { A _ { 2 } } { A } } \mathrm { B C _ { 2 } }
$$

式中： $\mathrm { B C _ { a } }$ 为平均BC指数； $A _ { 1 } \setminus A _ { 2 }$ 分别为轮廓面1和2的面积 $( \mathrm { k m } ^ { 2 } ) { \mathrel { \mathop : } } A$ 为总面积 $\left( \operatorname { k m } ^ { 2 } \right)$ ； $\mathrm { B C } _ { 1 }$ 和 $\mathrm { B C } _ { 2 }$ 分别为轮廓面1和2的BC指数。

聚落形状不同，相应的BC指数也不同，根据相关学者研究，聚落形态可以分为15种标准形态[21](表1)。圆形的空间形态最为紧凑，其BC指数为0,随着形态变化BC指数依次上升，直线的BC指数最高达到187.5。

# 2结果与分析

# 2.1AlphaShape算法计算结果

2.1.1乡村聚落边界提取结果从Alpha Shape算法的结果来看，该算法对于居民点分布均匀且相对紧凑的聚落边界提取效果较好(斑块平均间距<135m），图3a是聚落居民点斑块，图3b是边界提取结果。 $1 0 0 \mathrm { m }$ 提取半径下，具有明显轮廓的聚落占总数的 $7 6 . 1 \%$ ，其中具有单一轮廓的聚落占总数的$4 4 . 8 \%$ ，具有2个轮廓的聚落占总数的 $3 1 . 3 \%$ （表2）。

Tab.1 Standard shape corresponding to the BC index   

<html><body><table><tr><td>编号</td><td>形状</td><td>BC指数</td></tr><tr><td>1</td><td>圆形</td><td>0.000</td></tr><tr><td>2</td><td>正八边形1</td><td>1.960</td></tr><tr><td>3</td><td>正八边形2</td><td>2.060</td></tr><tr><td>4</td><td>菱形</td><td>9.656</td></tr><tr><td>5</td><td>正四边形</td><td>9.658</td></tr><tr><td>6</td><td>方状矩形1</td><td>25.286</td></tr><tr><td>7</td><td>方状矩形2</td><td>33.041</td></tr><tr><td>8</td><td>星形</td><td>34.852</td></tr><tr><td>9</td><td>H形</td><td>49.706</td></tr><tr><td>10</td><td>长条矩形</td><td>59.880</td></tr><tr><td>11</td><td>X形</td><td>66.366</td></tr><tr><td>12</td><td>带状矩形</td><td>90.851</td></tr><tr><td>13</td><td>线状矩形1</td><td>94.011</td></tr><tr><td>14</td><td>线状矩形2</td><td>122.404</td></tr><tr><td>15</td><td>直线</td><td>187.500</td></tr></table></body></html>

注：表中数据根据已有研究整理[21]所得;BC为Boyce-Clark指数。

聚落轮廓面数量主要受斑块平均间距标准差影响。单一轮廓聚落其平均斑块间距标准差为60，双轮廓聚落平均斑块间距标准差为69，这2类聚落在斑块平均间距上仅相差 $4 ~ \mathrm { m }$ 。因此，聚落轮廓面的数量在聚落整体间距相似的情况下，主要受间距分布影响，即标准差越大，聚落斑块间距波动越大，聚落轮廓数越多。

此外，由于龙镇地处黄土丘陵沟壑区，地形复杂，因此部分聚落居民点分布极为分散，通过 $1 0 0 \mathrm { m }$ 半径生成的聚落轮廓难以维持单一轮廓，导致多个轮廓面(3个及以上)的形成，此类聚落占 $2 3 . 9 \%$ 。轮廓面较多的情况下，对形状的研究难以展开，因此选择轮廓面较少(少于3)的聚落进行进一步分析，共计41个自然村。这些自然村的空间分布能够覆盖龙镇各个地形区域，包括北部河滩区域以及中部沟道、梁昴区域。

2.1.2聚落形状指数计算及类型划分根据各个面BC指数计算结果，龙峁村、李圪堆村、西高庙山村这

![](images/b04256f747805755ea67681a730ff0d14cc1c36c7bf5ca0f7f032e671eebeead.jpg)  
图3鲍庄村的居民点和 $1 0 0 \mathrm { m }$ 半径下Alpha Shape算法轮廓

Fig.3Residential area in Baozhuang Village and the contour of Alpha Shape algorithm under aradius of $1 0 0 \mathrm { m }$

# 表2聚落轮廓提取结果

表1BC指数对应的标准形状  
Tab.2 Extraction results of settlement contour   

<html><body><table><tr><td>轮廓面数量</td><td>聚落名称</td></tr><tr><td>1</td><td>赵家呱村、沙畔村、山殓楞村、苏家沟村、塔占村、老榆山村、麻地沟村、麻山村、马湖峪村、皮条昴村、东坪嫣村、杜家畔 村、樊兴庄村、丰富嫣村、冯庄村、高庄村、郭家砭村、贺家坡村、黑石窑村、后张兴庄村、艾家焉村、安寨村、白渠村、鲍庄 村、曹山村、常兴庄村</td></tr><tr><td>2</td><td>玉皇阁村、寨山村、张家湾村、张兴庄村、崖窑沟村、新窑沟村、赵兴庄村、前中庄村、西高庙山村、老庄村、李圪堆村、龙 峁村、黄家村、狼后沟村、陈家嫣村</td></tr></table></body></html>

# 干吴区地理

3个村庄2个轮廓面的BC指数较为接近，可以被近似看为单一形状，其采用面积加权的方式计算的平均BC指数分别为52.248、21.362、48.701。从具有单个轮廓面聚落的BC指数数值来看，最小值为皮条峁村（17.032），最大值为黑石窑村（107.030），皮条昴村为矩形和星形过渡形态，黑石窑村为线状矩形。随着BC指数提高其聚落形状逐渐趋于线形或线形组合形状，参考上文的标准形态BC指数，大致可以将研究区单一轮廓特征的聚落形状分为以下几种类型(图4)：

![](images/f591659f557305fec46788aded628380f349027f35b69f7c8f3afc6090d96945.jpg)  
图4研究区聚落标准形状类型  
Fig.4Standard shape types of settlements in the studyarea

（1）块状矩形或块状变种形（星形），BC数值范围为17.032\~33.032。其特征为，随着数值升高聚落形状从块状向外扩展，具体表现为聚落某一部分向外延伸，当向多个方向同时扩展时类似于星形，由于扩展程度不高因此BC指数也不高。这一形状的聚落有皮条昴村、苏家沟村、冯庄村、马湖峪村、李圪堆村。

（2）延伸形，包括2点延伸、3点延伸形等，BC数值范围为37.438\~53.288。该种形状由块状变种形状生成，由于其形状扩展程度较高因此BC指数较高。这一形状的聚落有山殓楞村、贺家坡村、丰富嫣村、沙畔村、樊兴庄村、塔占村、龙昴村、西高庙山村。

（3）串珠形或哑铃形，BC数值范围为 $5 5 . 7 7 5 \sim$ 70.644。其特征为2个或2个以上的延伸形聚落的组合，导致在带状聚落的部分节点处聚落面积突然增大,当由2个部分组成时形如哑铃，由3个及以上部分组成时形如串珠。这一形状的聚落有麻地沟村、高庄村、鲍庄村、赵家呱村、常兴庄村、老榆山村、安寨村、白渠村、曹山村、杜家畔村、麻山村。

（4）带状矩形或带状延伸形，BC数值范围为78.256\~99.868。其特征为单条带状矩形或多条带状矩形相交形成的带状延伸形，相比于多点延伸形和串珠形，其延伸距离更远，且不存在大面积的节点。这一形状的聚落有郭家砭村、艾家嫣村、东坪嫣村、后张兴庄村。

（5）线形，符合该种形状的聚落只有黑石窑村，其BC指数为107.030，如图中所示，其形状为一条线状矩形。

其余具有2个轮廓面的村庄可以被看为不同形状的组合。从数值来看，BC指数范围为15.400\~79.270。参照上文对于单一轮廓形状的分类，可以将具有组合形状的聚落分为以下几种：块状矩形/星形和哑铃形/串珠形的组合，代表性聚落有玉皇阁村、寨山村、崖窑沟村、新窑沟、黄家呱村；块状矩形和2点/3点延伸形组合，包括张家湾村、张兴庄村、前中庄村;2点延伸形和哑铃形/串珠形组合，包括赵兴庄村、老庄村；2点延伸形和带状矩形组合，包括狼后沟村、陈家焉村。

# 2.2聚落形状影响因素

2.2.1 影响因素选择及计算在影响因素选择方面，聚落规模是聚落形态的重要特征之一，一般情况下，当聚落空间规模增加或减少时，其形状也相应发生变化。因此首先选择聚落空间规模作为形状的影响因素之一。其次，研究区属于黄土丘陵沟壑区和半干旱区，地形条件和水资源可获取性在聚落演变过程中可能存在较强的作用。此外，在聚落形态的形成过程中，交通可达性的强弱对于聚落形态也可能存在影响。最后，已有学者研究表明宗族观念能够影响聚落形态[16]，该区域村落姓氏数量分布差异较大，因此宗族观念强弱对于聚落形态也可能存在影响。基于此，本文选取聚落规模、地形因子、水资源可获取性、交通可达性、宗族观念作为影响聚落形状的待选因素。

具体来看，聚落规模主要通过聚落面积表征;地形因子主要包括高程、坡度、坡向几大类，以及与这几类相关的细分地形因子，本研究选取高程、坡度、高程变异系数、地形起伏度、地表切割度、地表粗糙度、剖面曲率这7个地形因子以刻画龙镇地形特征，分析其与聚落形态的相关性；水资源可获取性方面，以水面栅格为源，采用成本距离函数计算居民点斑块到源的累计耗费距离，用以衡量各个栅格点取水的累计耗费成本，累计耗费距离越大可获取性越低；交通可达性使用各居民点斑块到最近公路(不包括村庄内部道路，在研究区主要为乡道)的平均里程表征，聚落平均里程越低表明聚落交通可达性越高；宗族观念使用各村姓氏数衡量，姓氏数量越低表明宗族观念越强。

以聚落BC指数为因变量，先通过多元线性回归的方式大致确定待选因子的重要程度，去除共线性极大的因子为了提高指标代表性，剔除方差膨胀系数(VIF)大于30的因子],再通过回归树的方式对多元线性回归的结果进行验证。采用回归树的原因是该模型对非线性关系有较好的拟合效果，并且不受数据共线性的影响，能够对多元线性回归结果进行补充[22]。影响因子均服从正态分布或接近正态分布的单峰分布，并且通过了方差齐性检验

2.2.2多元线性回归结果从检验结果来看(表3)，调整后决定系数 $\left( R ^ { 2 } \right)$ 为0.344，表示影响因子总共能解释聚落形状指数 $3 4 . 4 \%$ 的变化，模型拟合效果满足研究要求。从影响因子来看(表4)，坡度、高程变异系数、地形起伏度、地表切割深度、VIF值均大于30，且和聚落形状指数不存在显著相关性( $_ { ( P < 0 . 0 5 ) }$ ，因此后续使用回归树进行验证时去除这些因子。与聚落BC指数存在显著相关性的因子有高程和水资源可达性。高程和聚落BC指数存在显著正相关关系，高程越高，聚落BC指数越高，即随着高程增加，聚落形状逐渐从团块状向线状转变；水资源可获取性和聚落BC指数整体呈现正相关，即随着聚落水资源可获取性提高，聚落BC指数有增加趋势，但不明显。

2.2.3回归树计算结果及因子作用机制根据多元线性回归的结果，选取高程、面积、曲率、交通可达性、水资源可获取性、人口、宗族作为影响因子，使用回归树判断影响因子对于BC指数的影响程度。

表3多元线形回归模型摘要  
Tab.3Summaryof multiple linearregression model   

<html><body><table><tr><td>1</td><td>R</td><td>调整后R</td><td>标准估算的误差</td><td>德宾-沃森</td></tr><tr><td>0.735"</td><td>0.541</td><td>0.344</td><td>15.949</td><td>1.350</td></tr></table></body></html>

注： $\boldsymbol { r }$ 为相关系数； $R ^ { 2 }$ 为决定系数，表示自变量对因变量的解释程度： $\mathbf { \nabla } _ { a }$ 为预测变量，包括糙度、曲率、宗族、人口、交通可达性、水资源可达性、面积、高程、高程变异系数、坡度、地表切割深度、地形起伏度。

# 表4影响因子、标准化系数、显著性和VIF

Tab.4 Impact factors,standardized coefficient, significanceand VIF   

<html><body><table><tr><td>影响因子</td><td>标准化系数</td><td>显著性</td><td>VIF</td></tr><tr><td>高程</td><td>1.179</td><td>0.036**</td><td>17.392</td></tr><tr><td>坡度</td><td>-2.037</td><td>0.199</td><td>145.989</td></tr><tr><td>面积</td><td>0.085</td><td>0.676</td><td>2.496</td></tr><tr><td>曲率</td><td>-0.416</td><td>0.180</td><td>5.557</td></tr><tr><td>交通可达性</td><td>-0.235</td><td>0.150</td><td>1.539</td></tr><tr><td>水资源可达性</td><td>0.475</td><td>0.016**</td><td>2.115</td></tr><tr><td>人口</td><td>0.066</td><td>0.692</td><td>1.660</td></tr><tr><td>宗族</td><td>0.021</td><td>0.894</td><td>1.421</td></tr><tr><td>高程变异系数</td><td>2.108</td><td>0.257</td><td>202.626</td></tr><tr><td>地形起伏度</td><td>6.628</td><td>0.104</td><td>950.914</td></tr><tr><td>地表切割深度</td><td>-6.838</td><td>0.075*</td><td>835.207</td></tr><tr><td>粗糙度</td><td>0.298</td><td>0.680</td><td>31.111</td></tr></table></body></html>

注：\*\*\*、\*\*、\*分别表示 $P { < } 0 . 0 0 1 \ : , P { < } 0 . 0 1 \ : , P { < } 0 . 0 5 ,$ 当 $P { < } 0 . 0 5$ 则通过显著性检验;VIF表示方差膨胀系数。

从样本中选取 $2 5 \%$ 作为测试集、 $7 5 \%$ 作为训练集用来建立模型，通过比较均方根误差(RMSE)在RStudio中对回归树进行剪枝(图5)。图中椭圆框内是各影响因子，因子靠前表明对于聚落BC指数影响越大，高程、水资源可获取性对于聚落BC指数影响较高，这与多元线性回归的结果一致。

高程和地形相关性较高，而地形直接影响聚落形状类型，高程越高聚落形状越偏向线形及其组合形状，高程越低聚落形状越偏向于团块状。研究区高程较高的区域一般为梁顶地，位于此处的聚落地形条件较差，缺少大面积开阔区域，因此居民点只能沿道路分布，造成聚落整体BC指数偏高。高程较低的区域除了北部的河滩区域还有2条川道区域。河滩地区地形平坦，水资源可获取性较高，因此其聚落形态倾向于BC指数较低的团块状，并且由于可灌溉农田面积较大，人均收入也较高，成为过去10a聚落规模扩张最大的地区。川道区域是高等级公路分布的区域，相比于梁昴顶地附近的环状乡村道路，其道路线形直线部分更多，因此聚落居民点分布更加紧凑或形成一些大的节点，容易形成带状矩形或哑铃形等形状。

相比于多元线性回归的结果，回归树表明水资源可获取性对聚落BC指数的影响并非是线性的和正相关的。在聚落高程低于 $8 8 3 . 5 7 \mathrm { ~ m ~ }$ 时，水资源可获取性对聚落BC指数的影响较差，水资源可获取性主要影响高海拔的聚落的BC指数，高海拔聚落随着水资源可获取性的提高，其聚落BC指数在降低，表明聚落形状偏向紧凑。研究区水资源分布不均匀，除了雨水，主要水源为河水和水库。河水主要分布在低海拔地区，因此低海拔地区聚落的水资源可获取性差异并不大，导致对于聚落形状的影响程度不高。高海拔区域水源主要为水库，但由于水库分布不均匀导致水资源可获取性差别较大，因此高海拔区域随着水资源可获取性的提高，聚落形状紧凑程度有提高的趋势。

![](images/cb050ac1a79b6f6e5a8acd87e3cdac21ca2e0546e85439bc0c792d96c76ecf25.jpg)  
干吴区地理  
Fig.5Pruning results of regression tree

此外，聚落面积对于聚落BC指数也有影响。结合回归树的节点可以看出，当聚落面积较小时聚落BC指数值也较小，因为小型聚落一般以散点式的团块出现，而当面积开始增大时，聚落BC指数开始提高，因为聚落向外蔓延程度增加。当聚落规模大于 $0 . 0 2 \mathrm { k m } ^ { 2 }$ (为了防止模型过拟合该节点被剪枝)时，随着聚落规模提高，BC指数呈现下降趋势，即形状向团块状转变。当聚落面积达到 $0 . 0 3 6 \mathrm { k m } ^ { 2 }$ 时，随着聚落面积的提高，聚落BC指数重新增加，聚落形状向带状发展。该趋势揭示了该区域乡村聚落的扩张规律，即小规模聚落并非向四周均匀扩张，而是朝一个或多个方向扩张，在这个过程中BC指数提高，扩张到一定程度后，聚落内部的空洞逐渐被填充，BC指数得到降低。由于该区域地形以梁昂顶地为主，这种模式不能持续，因此当聚落向外扩张到一定程度之后只能沿交通线路扩展，造成BC指数重新升高。

# 3讨论

研究使用AlphaShape算法计算了散点的平面轮廓，没有考虑到高程对于聚落形状的影响。在聚落实际分布中，可能存在一些特殊情况，即居民点斑块距离较近，但高程相差较大，此时从外部空间的角度来说，这些居民点不能被划为整体。此外，本文以龙镇作为研究对象，乡村聚落数量有限，对于多元线性回归和回归树来说，样本数不算高，未来希望通过分层抽样的方式在陕北黄土丘陵沟壑区选取乡村聚落，提高样本数量及其代表性。

对于政策制定来说，该研究能够为聚落生活空间布置、建筑红线的划定提供参考。规划聚落生活空间，首先需要确定聚落生活空间的边界，在确定边界的基础上规划居民点空间布局及其面积。以$1 0 0 \mathrm { m }$ 作为半径，既考虑了建筑之间社会性联系，又满足了空间距离的要求，对聚落边界有较好的提取效果。当然，对于其他区域来说，该距离可能要发生变化，比如在平原地区,半径应该远大于 $1 0 0 \mathrm { m }$ ○对于居民点分布较为集中的聚落，确定生活空间边界后，该边界可以作为管控建筑物无序蔓延的依据，引导乡村聚落集约化扩张；对于分布散乱，向心性不强的聚落，通过确定生活空间边界，可以划定发展区域，引导聚落向多组团的“串珠式"聚落发展；对于完全分散的聚落，通过多个聚落轮廓面积能够确定聚落的中心，引导距离中心较远的居民点向中心迁移。

# 4结论

本文以米脂县龙镇乡村为例,使用Alpha Shape算法和BC指数提取了分散式乡村聚落边界、划分了其形状类型，最后结合多元线性回归和回归树分析了聚落形状类型影像因素，结论如下：

（1）AlphaShape算法对于分布距离适中（斑块平均间距 $< 1 3 5 \mathrm { ~ m ~ }$ )的散点式聚落形状提取效果较好，能够概括研究区 $7 6 . 1 \%$ 乡村聚落的形状特征。在不考虑竖向因素影响的情况下，当滚动半径设定为 $1 0 0 \mathrm { ~ m ~ }$ 时，能够提取出明显轮廓(轮廓面 $\stackrel { \cdot } { \leqslant } 2$ 的聚落占总数的 $7 6 . 1 \%$ ,其中单一轮廓的聚落占总数的$4 4 . 8 \%$ ,双轮廓的聚落占总数的 $3 1 . 3 \%$ 。

(2）在整体聚落斑块间距较为接近的情况下，AlphaShape算法提取的聚落轮廓面数量主要受斑块间距标准差影响。斑块间距标准差越大，聚落斑块间距波动越大，聚落轮廓数越多。

(3）研究区聚落形状类型可以划分为块状矩形及其变种、延伸形、串珠形和哑铃形、带状矩形及其组合、线形5种类型，对应的BC指数分别为 $1 7 . 0 3 2 \sim$ 33.032、37.438\~53.288、55.775\~70.644、78.256\~99.868、107.030。双轮廓面聚落的形状主要为这5种形状的组合。

（4）多元线性回归和回归树的结果表明，高程对于聚落形状的影响程度最高，高程与聚落BC指数存在显著正相关的关系，高程越高，聚落BC指数越高，聚落形状紧凑程度越低。水资源可获取性、聚落面积与聚落BC指数呈现非线性相关。当高程低于 $8 8 3 . 5 7 \mathrm { ~ m ~ }$ 时，水资源可获取性对聚落形状没有影响，高程高于这一数值时，水资源可获取性与聚落BC指数呈现负相关，即水资源可获取性越高，聚落BC指数越低，形状越趋于紧凑。聚落面积小于$0 . 0 2 \mathrm { k m } ^ { 2 }$ 时，面积和聚落BC指数呈负相关，当聚落面积达到 $0 . 0 3 6 \mathrm { k m } ^ { 2 }$ 时，聚落面积和BC指数呈正相关。

# 参考文献(References)

[1]李雅丽,陈宗兴.陕北乡村聚落地理的初步研究[J].干旱区地

理,1994,17(1): 46-52.[Li Yali,Chen Zongxing.Preliminary study on the geographical features of rural settlements in north Shaanxi [J].Arid Land Geography,1994,17(1): 46-52.]   
[2]浦欣成.传统乡村聚落二维平面整体形态的量化方法研究[D]. 杭州：浙江大学,2012.[Pu Xincheng.Quantitative research on the integrated form of the two-dimensional plan to traditional rural settlement[D].Hangzhou: Zhejiang University,01.]   
[3]谢丹.琼北乡村聚落空间形态解析[D].海口:海南大学,2015. [Xie Dan. Study on spatial morphology of rural settlement in northern Hainan[D]. Haikou: Hainan University,2015.]   
[4]杜佳.贵州喀斯特山区民族传统乡村聚落形态研究[D].杭州: 浙江大学,2O17.[Du Jia.The study on the ethnic traditional rural settlement form in karst mountainous area of Guizhou Province[D]. Hangzhou: Zhejiang University,2017.]   
[5]董一帆.传统乡村聚落平面边界形态的量化研究[D].杭州：浙 江大学,2O18.[Dong Yifan.Quantitative research on the border formof traditionalrural settements: Case studyof Zhejiang Province[D]. Hangzhou: Zhejiang University,2018.]   
[6]张文芳.陕北无定河下游传统村落空间形态研究[D].西安:西 安建筑科技大学,2020.[Zhang Wenfang.Study on the spatial form of traditional villages in the lower reaches of Wuding River in the Loess Plateau of northern Shaanxi Province[D].Xi'an: Xi' an University of Architecture and Technology,2020.]   
[7]金其铭.农村聚落地理研究——以江苏省为例[J].地理研究, 1982,1(3):11-20.[Jin Qiming.The geographic studyofruralsettlements: Taking Jiangsu Province as an example[J]. Geographical Research,1982, 1(3): 11-20.]   
[8]马晓冬,李全林,沈一.江苏省乡村聚落的形态分异及地域类型 [J].地理学报,2012,67(4): 516-525.[Ma Xiaodong,Li Quanlin, Shen Yi. Morphological differenceand regional types of rural settlements in Jiangsu Province[J].Acta Geographica Sinica,2012,67 (4): 516-525.]   
[9]周亮,朱彦儒,孙东琪.河西走廊城乡居民点空间分异特征及绿 洲孕育度分析[J].干旱区地理,2020,43(1):227-236.[Zhou Liang,Zhu Yanru, Sun Dongqi. Spatial differentiation characteristics and oasis breed degree of urban and rural residents in Hexi Corridor[J].Arid Land Geography,2020,43(1): 227-236.]   
[10] 黄亚平,郑有旭.江汉平原乡村聚落形态类型及空间体系特征 [J].地理科学,2021,41(1): 121-128.[Huang Yaping,Zheng Youxu. The rural settlement morphological types and spatial system characteristics in the Jianghan Plain[J]. Scientia Geographical Sinica, 2021, 41(1): 121-128.]   
[11] 方健,杨兴柱,朱琳.黄山市乡村聚落空间格局特征及其影响因 素[J].热带地理,2017,37(2): 277-285,292.[Fang Jian,Yang Xingzhu, Zhu Lin.Spatial pattern of rural setlements in Huangshan and its influencing factors[J]. Tropical Geography,2017,37 (2): 277-285,292.]   
[12] 杨忍.基于自然主控因子和道路可达性的广东省乡村聚落空间 分布特征及影响因素[J].地理学报,2017,72(10):1859-1871. [Yang Ren.An analysis of rural settlement patterns and their ef

# 干吴区地理

fect mechanisms based on road traffic accessibility of Guangdong [J].Acta Geographica Sinica,2017,72(10): 1859-1871.]   
[13] 王正伟,马利刚,王宏卫,等.干旱内流区绿洲乡村聚落空间格 局及影响因素分析——以塔里木河流域为例[J].长江流域资 源与环境,2020,29(12):2636-2646.[Wang Zhengwei,Ma Ligang,Wang Hongwei, et al. Spatial pattern and influencing factors of oasis rural settlements in inland river basin:A case study in Tarim River Basin[J].Resources and Environment in the Yangtze Basin,2020,29(12): 2636-2646.]   
[14]岳邦瑞,李玥宏,王军.水资源约束下的绿洲乡土聚落形态特征 研究——以吐鲁番麻扎村为例[J].干旱区资源与环境,2011, 25(10): 8O-85.[Yue Bangrui,Li Yuehong,Wang Jun. Features of oasis vernacular settlement patterns under the perspective on water resource constraints: Case study of Turpan Mazar Village in Xinjiang,China[J]. Journal of Arid Land Resources and Environment,2011,25(10): 80-85.]   
[15] 张惠婷,马利刚,王宏卫,等.新疆乡村聚落特征及其区域融合 发展探析[J].干旱区地理,2020,43(6):1667-1678.[Zhang Huiting,Ma Ligang,Wang Hongwei,et al. Characteristics and regional integration development of rural settlements in Xinjiang[J].Arid Land Geography,2020,43(6): 1667-1678.]   
[16] 杜佳,华晨,余压芳.传统乡村聚落空间形态及演变研究——以 黔中屯堡聚落为例[J].城市发展研究,2017,24(2):47-53.[Du Jia,Hua Chen,Yu Yafang.Research on spatial evolution of traditional settlements: The case study of Qianzhong Tunpu[J]. Urban

Development Studies,2017,24(2): 47-53.]

[17]王浩锋.徽州传统村落的空间规划——公共建筑的聚集现象 [J].建筑学报,2008(4):81-84.[Wang Haofeng.The spatial planning of traditional villages in Huizhou: The gathering phenomenon of public buildings[J].Architectural Journal,2Oo8(4): 81-84.]   
[18] 李红波,张小林,吴江国,等.苏南地区乡村聚落空间格局及其 驱动机制[J].地理科学,2014,34(4):438-446.[Li Hongbo, Zhang Xiaolin,Wu Jiangguo,et al. Spatial pattern and its driving mechanism of rural setlements in southern Jiangsu[J]. Scientia Geographical Sinica,2014,34(4): 438-446.]   
[19] 熊皓,郑伯红,贾磊.驱动力与制约力相互作用下我国城市空间 扩张[J].经济地理,2016,36(1):82-88.[Xiong Hao,Zheng Bohong,Jia Lei.Urban space expansion in China under the interaction between the driving force and the restriction[J]. Economic Geography,2016,36(1): 82-88.]   
[20]王志远.低碳城市空间形态规划研究[D].长沙:中南大学, 2012.[Wang Zhiyuan. Study of low-carbon city spatial form planning[D]. Changsha: Central South University, 2012.]   
[21]王新生,刘纪远,庄大方，等.中国城市形状的时空变化[J].资源 科学,2005,27(3):20-25.[Wang Xinsheng,Liu Jiyuan,Zhuang Dafang,et al. Spatial-temporal changes of the shapes of Chinese cities[J]. Resources Science,2005,27(3): 20-25.]   
[22]DeFries RS,Rudel T,Uriarte M,et al.Deforestation driven by urban population growth and agricultural trade in the twenty-first century[J].Nature Geoscience,2010,3:178-181.

# Morphological types division and its formation of dispersed rural settlements based on Alpha Shape: A case of Long Town, Mizhi County

WANG Tianyu, HUI Yi'an， RUI Panpan， SHI YingCollege of Urbanand Enviromental Sciences,Northwest University,Xi'an 71Ol27,Shaanxi,China)

Abstract:To quantitatively classifythe morphological typesof dispersed rural settlementsand explore the reasons for their formation,this study cites Long Town,Mizhi County,loesshilly-gullyregion innorthern Shaanxi of China as an example,attempting to use Alpha Shape algorithm to extract the settlement contour,calculate and clasify the setlement contour type using the Boyce-Clark index,and finally explore the factors that affct the settlement contour by combining numerous linear regression and regresson tree methods.The results show that: with a rolling radius of $1 0 0 \mathrm { ~ m ~ }$ ，the Alpha Shape algorithm can extract $76 . 1 \%$ of the accurate contours of the settlements;the types of rural setlements in the study area can be divided into five types: block rectangle and its variants,extension,dumbbelland bead,ribbon rectangleand its combination,and linear.The Boyce-Clark index increasescontinuously;elevation and shape index are positively connected,water availabilityand shape index are negatively connected in high altitude areas,settement area and shape index are first negatively connected and then positively connected.This study provides a reference for the delineation of the living space boundary of dispersed settlements and enhances the understanding of dispersed settlements in loess hilly-gully areas.

Key words: rural settlement;morphological type；Alpha Shape algorithm;Boyce-Clark index;loess hily-gullyregion