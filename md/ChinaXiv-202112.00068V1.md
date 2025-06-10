# 吉林省西部生态安全格局构建

张萌¹，刘吉平1²，赵丹丹1.2（1.吉林师范大学旅游与地理科学学院,吉林 四平136000;2.吉林师范大学资源保护与利用研究所，吉林 四平136000)

摘要：构建生态安全格局能有效保障区域生态安全，尤其是对生态脆弱区环境改善极为重要。以吉林省西部为研究区，通过生物多样性服务价值、水资源安全、土壤保持、生态需求等4项指标识别生态源地;利用电路理论,结合Linkage Mapper工具和Circuitscape软件识别生态廊道、夹点区、改善区，构建吉林省西部的生态安全格局。结果表明：(1)识别18块生态源地，占研究区面积 $8 . 5 7 \%$ ，主要分布在现有保护区周边的湿地。(2）构建38条关键廊道和7条潜在廊道，主要分布在中部和东部地区,夹点区相对集中于西南部和东部,改善区中建筑用地和盐碱地相对较多。(3)在构建生态源地、廊道、夹点、改善区综合生态安全格局基础上，提出了“一带、两轴、五区、五组团"生态安全格局保护策略。对保障吉林省西部区域安全及经济与生态协调发展提供决策参考。

关键词：生态安全格局；电路理论；生态服务功能；吉林省西部

# 文章编号：

近年来，土地沙化碱化、水污染、生物多样性锐减等生态问题频发，以及人类活动强烈干扰影响，使得生态系统的结构与功能经历了重大改变，影响区域的生态安全质量[1-2]。保障区域生态安全已成为社会可持续发展的一项重要工作，而构建生态安全格局是实现区域生态安全的基本保障和重要途径[3]。

生态安全格局又称生态安全框架，是指景观中存在某种潜在的生态系统空间格局[4]。目前，生态安全格局的构建方法已日趋成熟，通常是“识别源地一构建阻力面一提取廊道"的基本模式[5]。生态源地是指提供重要生态系统服务的斑块[5]。国内外学者们主要根据不同目的利用不同的方法对源地进行识别，直接选取对区域安全有重要意义的斑块、MPSA分析法[、通过多方面因素建立综合评价体系8构建识别源地。生态廊道是物种迁徙的通道,是两源地之间的流动通道和联系途径[5]。当前主要以图论[9]、最小累积阻力模型(MCR)[10-11]、电路理论[12-13]等方法识别生态廊道。当前研究中，主要集中在源地识别方法的创新，但对构建完生态廊道后缺乏进一步分析。而在研究区选取中，对经济发达区或城市化区研究相对较多[4],对生态脆弱区的生态安全格局研究相对较少。

吉林省西部是我国典型的生态脆弱区，也是吉林省重要生态屏障。随着自然环境恶化和人类活动影响，生态环境遭到严重破坏[15],构建合理的生态安全格局对其环境改善极为重要。本文以吉林省西部为研究区，通过生物多样性、水资源安全、土壤保持和居民生态需求等方面来识别生态源地；基于电路理论，利用LinkageMapper工具和Cir-cuitscape 软件(http://www.circuitscape.org/)提取生态廊道和夹点区并建立改善区，从而构建该区综合生态安全格局并提出合理的保护策略，对保障吉林省西部以及吉林省地区的经济与生态协调发展具有

重要意义。

# 1研究区概况及数据来源

# 1.1 研究区概况

吉林省西部地处 $4 3 ^ { \circ } 2 2 ^ { \prime } { \sim } 4 6 ^ { \circ } 1 8 ^ { \prime } \mathrm { N }$ ， $1 2 1 ^ { \circ } 3 8 ^ { \prime } \sim$ $1 2 6 ^ { \circ } \mathrm { 1 1 ^ { \prime } E }$ ，位于松嫩平原西南部，辽河平原北端，总面积为 $4 6 7 9 4 { \mathrm { k m } } ^ { 2 }$ 。从行政区划分，隶属于松原市和白城市，包括宁江、前郭尔罗斯、乾安、长岭、洮北、洮南、通榆、镇费、大安等市(县、区)八(图1)。属于干旱半干旱温带季风气候区，处于我国湿润的东部季风和内陆干旱、半干旱的过渡带，四季变化明显，是我国典型的农牧交错带和生态脆弱带[15]。由于近些年人口剧增和自然资源在不同程度上遭到破坏，受人类活动干扰，生态环境严重恶化，威胁区域生态安全和可持续发展。

![](images/ec339565b1b7b1edbae06bc5f0e9f26865023f4350c9cf81fdd16a2c682e1270.jpg)  
Fig.1 Administrative divisions and land use types in western Jilin Province

注：该图基于国家测绘地理信息局标准地图服务网站下载的审图号为GS(2019)3333号的标准地图制作。下同。图1吉林省西部行政区划及土地利用类型

# 1.2数据来源及处理

2018年土地利用数据源于LandsatOLI遥感数据，在前期合成处理后，利用1:100000地形图纠正并进行目视解译，通过抽样统计精度验证法，并结合高分辨率遥感影像对解译结果验证，解译精度达$9 2 . 4 \%$ （图1），用于生态用地识别和阻力面构建；ND-VI、土壤、夜间灯光数据源自资源环境科学与数据中心（http://www.resdc.cn/）,分别用于生物多样性服务价值修正、土壤保持、生态需求分析计算；DEM数据源于地理空间数据云(http://www.gscloud.cn/)用于坡长坡度等地形因子计算；月均降雨量数据源自国家气象科学数据中心(http://data.cma.cn/),用于降水侵蚀因子计算。

# 2 研究方法

# 2.1生态源地识别

生态源地不仅有很高的生态服务功能，而且对满足人类生态需求方面意义重大[8]。对生态源地的识别，除了需要考虑自然特性以外，还需要考虑它对人们生态需求服务供给能力[6]。本文选取生态系统重要性评价、生态需求分析进行生态源地的综合识别。

# 2.1.1生态系统重要性分析

（1）生物多样性服务价值评价。生物多样性服务价值功能可以反映生境的良好状况，不同的土地利用类型对生物资源的保持能力不同[，服务价值功能越高的地区能提供越好的生境[16]。根据谢高地等制定的生物多样性服务价值当量表进行评价，并采用归一化植被指数(NDVI)修正公式确定不同土地利用类型生物多样性服务当量[16]。计算公式如下：

$$
\mathrm { D L } = { \frac { \mathrm { N D V I } _ { i } } { \mathrm { N D V I } _ { t } } } \times \mathrm { D L } _ { 0 }
$$

式中：DL为栅格 $i$ 修正后的生物多样性服务当量;NDVI为栅格 $i$ 的NDVI年均值;NDVI为栅格i所对应的土地利用类型 $\mathbf { \Phi } _ { t }$ 的NDVI均值; $\mathrm { D L } _ { 0 }$ 为栅格i所对应的土地利用类型 $\mathbf { \chi } _ { t }$ 的生物多样性服务价值当量。

(2）水资源安全评价。水资源是维持区域生态健康的重要生态空间1。从水资源安全角度评价出发，对研究区域洪流安全以及水资源保护2个方面进行评估。两者分别以计算距河流的距离、不同覆被类型对水源涵养能力大小进行评价。参考已有研究[8.18],并根据研究区实际水文情况构建合理的指标体系(表1)。

（3）土壤保持评价。土壤保持可以反映区域侵蚀控制以及生态安全维持的水平，本文采用修正的通用土壤侵蚀方程(RUSLE模型)对土壤保持能力进行评价[19]。计算公式如下：

$$
A = A _ { 0 } - A _ { 1 } = R \times K \times \mathrm { L S } \times \left( 1 - P \times C \right)
$$

式中： $A$ 为预测土壤保持量； $A _ { 0 }$ 为潜在土壤侵蚀量； $. A _ { 1 }$

# 表1水资源安全评价体系

Tab.1 Water resources safety evaluation system   

<html><body><table><tr><td rowspan="3">指标</td><td>最重要</td><td>重要</td><td>次重要</td><td>一般重要</td><td>不重要</td></tr><tr><td>5</td><td>4</td><td>3</td><td>2</td><td>1</td></tr><tr><td rowspan="2">河流湖泊</td><td>200 m</td><td>400 m</td><td>600m</td><td></td><td></td></tr><tr><td>缓冲区</td><td>缓冲区</td><td>缓冲区</td><td></td><td>1</td></tr><tr><td>覆被类型</td><td>湿地</td><td>林地</td><td>草地</td><td>耕地</td><td>其他</td></tr></table></body></html>

为土壤保持量； $R$ 为降雨侵蚀力； $K$ 为土壤可蚀性因 子；LS为坡长坡度因子； $P$ 为土壤保持措施因子; $C$ 为植被覆盖因子[20]

参考已有专家学者的研究[2I-23],按研究区实际情况，对不同土地利用类型赋予相应的 $C$ 值和 $P$ 值(表2)。

表2不同土地利用类型的 $c$ 值和 $P$ 值  

<html><body><table><tr><td>土地类型</td><td>C值</td><td>P值</td></tr><tr><td>水田</td><td>0.18</td><td>0.01</td></tr><tr><td>旱田</td><td>0.24</td><td>0.35</td></tr><tr><td>草地</td><td>0.02</td><td>1.00</td></tr><tr><td>林地</td><td>0.03</td><td>1.00</td></tr><tr><td>水域</td><td>0.00</td><td>0.00</td></tr><tr><td>湿地</td><td>0.00</td><td>0.00</td></tr><tr><td>未利用地</td><td>0.00</td><td>1.00</td></tr><tr><td>建筑用地</td><td>0.00</td><td>0.00</td></tr></table></body></html>

注：C为植被覆盖因子； $P$ 为土壤保持措施因子。

$K$ 值采用师长兴等[24研究成果，LS值采用杨勤科等[25]计算方法。 $R$ 值采用周伏建等[26]计算方法。

2.1.2生态需求分析生态重要性分析不仅要考虑该区域内生态用地本身的重要性，还要考虑生态用地的被需求程度[16]。夜间灯光数据是人类活动强度和范围的良好体现[27],参考蒙吉军等[16]的研究，基于核密度分析计算不同生态用地的生态需求聚集强度。计算公式如下：

$$
R _ { i } = \sum \frac { P _ { i } } { D _ { i } }
$$

式中： $R _ { i }$ 为生态用地栅格 $i$ 对应的生态需求值； $P _ { i }$ 为栅格 $i$ 对应的需求半径的生态需求核密度函数值； $D _ { i }$ 为生态用地栅格 $i$ 与其邻近的有效需求点的最短距离。

结合相关研究[8.28]与研究区实际情况，将上述4个方面的权重分别赋予0.3、0.3、0.2、0.2，各评价结果都采用自然断点法重新分为不重要、一般重要、次重要、重要和最重要5个等级，最后通过加权叠加上述4个因子再分级得到综合评价结果。

# 2.2生态阻力面构建

生态阻力面的建立是生态安全格局构建的核心，也是廊道准确识别的关键。基于土地利用现状类型,采用专家经验及相关研究[7.29],结合研究区实际情况，将各土地利用类型对物种和生态系统的阻力系数拟定在1\~500之间，并将坡度和海拔进行相关赋值(表3)。

# 表3生态阻力值

Tab.2Value $c$ and value $P$ of different landuse types   
Tab.3 Ecological resistance value   

<html><body><table><tr><td>阻力因子</td><td>分级指标</td><td>阻力系数</td><td>权重</td></tr><tr><td>土地利用类型</td><td>林地</td><td>1</td><td>0.65</td></tr><tr><td rowspan="9">坡度/(°)</td><td>草地</td><td>10</td><td></td></tr><tr><td>湿地</td><td>30</td><td></td></tr><tr><td>水域</td><td>50</td><td></td></tr><tr><td>耕地</td><td>100</td><td></td></tr><tr><td>建筑用地</td><td>500</td><td></td></tr><tr><td>居民用地</td><td>500</td><td></td></tr><tr><td><5</td><td>1</td><td>0.29</td></tr><tr><td>5~10</td><td>100</td><td></td></tr><tr><td>10~15</td><td>200</td><td></td></tr><tr><td></td><td>15~20</td><td>300</td><td></td></tr><tr><td>海拔/m</td><td>>20</td><td>500</td><td></td></tr><tr><td rowspan="3"></td><td><200</td><td>10</td><td>0.06</td></tr><tr><td>200~400</td><td>20</td><td></td></tr><tr><td>400~600</td><td>40</td><td></td></tr><tr><td></td><td>>600</td><td>80</td><td></td></tr></table></body></html>

# 2.3生态廊道构建

生态廊道是相邻2个生态源地间生态流的低阻力生态通道，分为关键生态廊道和潜在生态廊道[13]。利用电路理论中常用的连接模型与随机游走相结合的方式来识别[13]。通过LinkageMapper工具来模拟最小成本路径和提取生态廊道。

夹点是生态廊道中电流密度较高的区域，是物种迁徙通过该区域的可能性比较高或者没有其他可以选择的替代路径，如果移除或者改变将会对连接度产生较大影响，是生态格局的关键节点[30]。通过PinchpointMapper工具和Circuitscape软件识别生态廊道中的夹点区。

利用BarrierMapper工具对廊道的障碍性进行分析，来判别阻碍动物在迁徙过程时区域间的连通性及能够改善可能性。参考倪庆琳等[13]研究，利用自然断点法将所得结果分为2个等级，分别为一级、

二级廊道改善区。

# 3结果与分析

# 3.1生态安全格局构建

3.1.1生态源地提取生物多样性评价中，最重要、重要的区域广泛分布在自然保护区周围及东部和西部的林地附近，这些地方大部分是物种栖息地，具有重要的生物多样性保护价值；水资源安全方面，最重要、重要的区域分布在查干湖、月亮泡、莫莫格湿地、向海湿地、东北部的松花江支流等，主要以湖泊湿地、林地构成，地方地势低平，是水资源保护重点区域，对人类生活和居住安全有着重要意义；土壤保持方面，最重要区域主要分布西部坡度较大的低山、丘陵处及零星分布林地附近，这些地方地势高地形起伏大，极易发生强降水等带来一系列土壤侵蚀问题，而且林地对土壤保持具有重要意义；居民生态需求中，最重要区域分布在宁江区、前郭县、洮北区、扶余市等城区中心，该区域人口分布密集，居民生态需求较高(图2)。

根据现有研究[128]并结合该域区的实际情况，提取面积大于 $2 0 \mathrm { k m } ^ { 2 }$ 的最重要、重要生态用地作为生态源地，共18块生态源地，面积 $4 0 0 8 . 8 8 \mathrm { k m } ^ { 2 }$ ，占研究区总面积 $8 . 5 7 \%$ (图3)。其中有 $4 1 . 3 0 \%$ 源地分布在国家(省)级自然保护区内。在生态源地中,以水域为主，占源地斑块面积的 $3 6 . 3 2 \%$ ;其次是湿地、耕地、林地、草地，分别占 $3 2 . 0 2 \% . 1 8 . 7 0 \% . 6 . 7 0 \%$ 、$4 . 8 6 \%$ 。主要分布在查干湖、向海、莫莫格、洮儿河、月亮泡以及其周边的湿地、西部松花江、嫩江流域附近、西南西北部的林地。

3.1.2生态廊道分布将生态源地相连，共得到45条生态廊道，其中关键廊道38条，潜在廊道7条（图3)。中部生态廊道呈现网状聚集分布，东南部呈现散射状分布特点。总长 $2 4 3 0 . 0 3 ~ \mathrm { k m }$ ，关键廊道总长$1 5 4 0 . 6 8 ~ \mathrm { k m }$ ;潜在廊道总长 $8 8 9 . 3 6 ~ \mathrm { k m }$ 。中南部是源地集中分布区，以 $1 0 { \sim } 5 0 ~ \mathrm { k m }$ 的廊道连接，是源地间连接的主要廊道。西部廊道分布较少，以短廊道连接；大于 $8 0 \mathrm { k m }$ 廊道主要分布在西南部和东部，北部和东部源地相距较远，以 $1 0 0 { \sim } 3 0 0 \mathrm { k m }$ 潜在廊道相连。

根据现有研究[131]并结合实际情况，将生态廊道宽度设置为 $1 ~ \mathrm { k m }$ ,其总面积为 $2 4 9 6 . 1 1 ~ \mathrm { k m } ^ { 2 }$ ，占研究区面积的 $5 . 3 3 \%$ 。在构成生态廊道的景观中，耕地景观占比最大，占比 $4 5 . 9 7 \%$ ;其次占比较高的景观构成是草地、林地、湿地，占比分别为 $2 9 . 0 3 \%$ 、$1 0 . 8 2 \% \cdot 4 . 9 0 \%$ 。耕地是研究区的基底景观，在廊道景观构成中的占比较高;草地是研究区的面积较大的景观，集中分布在中部地区，并且中部地区也是源地分布密集地区，所以在生态廊道景观的构成中，草地占比仅次于耕地。研究区分布着众多林带和大小不一的湿地斑块，它们是动物的主要栖息场所，对动物迁徙的阻碍作用较小。其中关键廊道与潜在廊道存在着某些部分的重合，可能是重合区域对动物迁徙的阻碍作用较低。

![](images/ef31853f117109e08539e94354c538b3a73c07ef6a5d61b8b9346a56b1cc920c.jpg)  
图2生态用地评价结果  
Fig.2 Results of the ecological land evaluation

![](images/34db0551c99097fdbdf7be1418dd515e34675b624f6a27ce55bdf3dc0f4b49b7.jpg)  
图3生态源地与生态廊道分布

3.1.3夹点区识别利用电流路径来模拟空间尺度上生态流的走向，构建生态网络电流图。并利用自然断点法对累计电流分级，电流值较大的区域为夹点区。夹点区主要分布在西南部和东部，连通性较好；中部地区夹点分布较少，景观连通性相对较差（图4）。

根据夹点区分布情况，提取49个夹点，由图6可以看出，东南部地区夹点有24个夹点，分布数量较多，该区连接中部主要源地，廊道呈散射状分布且数量较多，夹点相对其他区域较多；西南部有10个夹点，分布较为集中，向海国家自然保护区和包拉温都省级自然保护区相邻位置较近，保护区及其周边区域生态保护体系较为完善，生态质量较好，连接度较高；中部和东北部分别有9个和6个，主要是因为中部盐碱地居多，阻碍连通性；东北部为松原人口和产业的集聚区，在一定程度上破坏了景观

![](images/6cf8872f7d1cfaa0cf9636d498c83ade4861262cceaa427b99460694dd4410c7.jpg)  
图4夹点区空间分布  
Fig.4Distribution of pinchpoint region

连通性。

3.1.4改善区划分改善区是影响动物迁徙和生态恢复的重要地区，通过对改善区的修复和改善，可以提高生态源地之间的景观连通性、减轻动物在迁徙过程中的生态阻力。通过障碍分析，改善区面积为 $1 0 6 4 9 . 2 8 ~ \mathrm { k m } ^ { 2 }$ ，占研究区总面积的 $2 2 . 7 5 \%$ 。改善值较高的区域分布在西南部和东部地区，改善值较低区域分布在中部地区(图5)。

![](images/b56760bde323ac0cdcb916b0a2b9d925e6d7fa9f4e5c6d17142ebec245194d62.jpg)  
Fig.3 Distribution of ecological sources and ecological corridors   
图5改善区范围  
Fig.5Extent of the ecological improvement region

根据自然断点法将改善区的改善系数进行分级，主要分为一级廊道改善区和二级廊道改善区(图6)。一级廊道改善区面积 $2 8 0 3 . 0 6 \mathrm { k m } ^ { 2 }$ ，占改善区的面积 $2 6 . 3 2 \%$ 。该区域是研究区内重点的修复地区，主要分布在源地之间或周边地区，在查干湖、向海湿地和自然保护区均有分布。道路、建设用地和居民点的相互交错，对生态源地间的连接干扰影响较大；盐碱地分布较广，对动物迁徙障碍的影响较大。二级廊道改善区面积为 $7 8 4 6 . 2 2 ~ \mathrm { k m } ^ { 2 }$ ，占比$7 3 . 6 8 \%$ ,可看成是生态源地外围不规则的缓冲区。

# 3.2生态安全格局保护策略

识别生态源地、生态廊道、夹点、改善区后，根据源地在现有保护区内外部的位置关系，进一步划分保护区内生态源地和保护区外生态源地(图6)，前者在现有保护区内，保护相对较好，应在现有保护区政策的基础上进行完善；后者在现有保护区外，应该重点加强生态保护，可对现有保护区进行扩张或建立相应保护公园。生态源地区、夹点区、廊道改善区共同构成了吉林省生态安全格局。

为了确保生态安全工作进行和区域可持续发展，参考《吉林省土地利用总体规划(2006—2020年)》《白城市土地利用总体规划(2006—2020年）》《松原市土地利用总体规划(2006—2020年)》中相关规划,进一步提出“一带、两轴、五区、五组团"的总体生态安全格局保护策略(图6)。

（1）“一带”是指白沙滩一洋沙泡一洮儿河引水工程带，在此引水带分布着白沙滩、五家子、洮儿河等主要灌区，并且“引嫩入白”、“引洮入向"等大型水利工程线途经此处。同时多数西部源地分布在一带两侧,保护一带两侧生态环境对生态安全格局的构建尤为重要。该区属于干旱缺水，水资源严重匮乏的地区，对嫩江、洮儿河的水资源开发，有利于解决该区供水安全问题和加快经济发展。并且开辟新水源，能够改善莫莫格自然保护区泡沼干涸问题。

（2）“两轴”是指洮儿河一大步苏生态廊道轴和通榆一长岭一扶余生态廊道轴。前者是西北一东

![](images/c92286b224c7f110785c23487ac8ceb6d59a2c419f3b5de85479126cf4bd3ef1.jpg)  
图6生态安全格局构建  
Fig.6 Construction of ecological security pattern

# 干旱区地理

南向的重要生态廊道轴线，后者是西南一东北向的重要生态廊道轴线。这两条轴线分布着该研究区主要的生态廊道，保护轴线地区两侧生态稳定，对动物迁徙和生物多样性的保护具有重要意义。

（3）“五区”是指西北生态保护区、西南生态敏感区、中部潜力开发区、东南生态恢复区、东北生态农业区。西北生态保护区位于镇费县和洮北区，该区域水系发达，灌区密布，嫩江、洮儿河是主要的供水区，应重点保护水资源安全；西南生态敏感区位于洮南市、通榆县,该区域是沙地草地的过渡地区，属于半干旱地区，生态环境较为敏感；中部潜力开发区位于大安市和乾安县，它是生态源地密集分布地区，但也是吉林省西部盐碱最严重地区，盐碱地连片分布，严重影响了生态廊道的连通性，应适度开发盐碱地，进行“改碱种稻"工程;东南生态恢复区位于长岭县，该区域水土流失严重；东北生态农业区位于扶余市、前郭县，该区域是基本农田的重点建设地区，应大力发展生态农业，为区域粮食产量提供保障。

（4）“五组团”是在五区的基础上划分的改善区组团。西北部主要以二级廊道改善区为主，生态环境较稳定应加强新廊道的建设，中部、东北部、西南部、东南部的组团一级廊道改善区数量较多，其中分布着建筑用地和居住地等，对生态廊道的建设有着阻碍作用，是生态保护的矛盾区，应在不破坏现有基础设施的基础上进行小范围的生态工程，如建立道路绿化带来改善周边环境。而在改善区组团中耕地是主要的景观类型。不同空间位置上的耕地具有的经济功能不同，在实施生态保护工程的同时，要兼顾对耕地的保护，不破坏现有的基本农田。可在基本农田类的耕地加强农田整治并在周边建立防护林带，既保护基本农田又改善周边生态环境。

# 4讨论

本文基于电路理论构建生态源地间的生态廊道，并在廊道的基础上进行对夹点和改善区的建设，改变了以往研究中只考虑源地的建设而忽略对生态廊道进一步构建，为生态安全格局的构建提供新的参考。并且电路理论把动物迁徙看成是随机游走的电荷，动物对周围景观没有先知性，符合本身特性，识别出生态廊道的结构相对符合实际[32]需要说明的是，在生态源地识别中，生态系统重要性评价的3个指标主要基于土地利用类型判别，故指标间存在一定重复性；并且没有考虑社会经济因素对阻力面建立的影响。因此，在今后构建生态安全格局时，如何降低生态源地识别中指标间的重复性和构建更为完善的阻力面，有待进一步研究。

# 5结论

基于生态系统重要性评价和居民生态需求分析，并结合电路理论，对生态源地、生态廊道、夹点、改善区以及整体的生态安全格局进行识别和构建，并提出“一带、两轴、五区、五组团"保护策略。研究结果表明：

（1）吉林省西部共18块生态源地，以湿地和水域为主，面积 $4 0 0 8 . 8 8 \mathrm { k m } ^ { 2 }$ $4 1 . 3 \%$ 的源地分布在国家(省)级自然保护区内，保护区内源地进一步完善现有保护政策，保护区外源地应重点加强保护；生态廊道包含38条关键廊道和7条潜在廊道，主要分布在中部和东部，中部呈网状分布，东部呈散射状分布，为动物迁徙提供保障；夹点区主要景观构成为耕地、林地、草地，相对集中于西南部和东部，可维持景观连通性;改善值较高的区域分布在西南部和东部地区，并对改善区进行分级保护。

（2）对生态安全格局的构建，要根据所在地区的实际情况和相关政策文件开展因地制宜的保护措施。生态源地、生态廊道、夹点、改善区和“一带、两轴、五区、五组团"的空间格局，共同构建该研究区总体生态安全格局，并为今后的生态建设提供理论依据。

# 参考文献(References)

[1]王玉莹,金晓斌,沈春竹,等.东部发达区生态安全格局构建 一以苏南地区为例[J].生态学报，2019,39(7):2298-2310. [Wang Yuying,Jin Xiaobin,Shen Chunzhu,etal.Establishment of an ecological security pattern in the eastern developed regions: A case study of the Sunan District[J].Acta Ecologica Sinica,2019, 39(7): 2298-2310.]   
[2] 郑岚，张志斌,宣晓军，等.嘉峪关市土地生态安全动态评价及 影响因素分析[J].干旱区地理,2021,44(1):289-298.[Zheng Lan,Zhang Zhibin,Da Xiaojun,et al. Dynamic evaluation and influencing factors of land ecological security in Jiayuguan City[J]. Arid Land Geography,2021,44(1): 289-298.]   
[3]刘洋,蒙吉军,朱利凯.区域生态安全格局研究进展[J].生态学

报,2010,30(24): 6980-6989.[Liu Yang,Meng Jijun, Zhu Likai. Progress in the research on regional ecological security patern[J]. Acta Ecologica Sinica,2010,30(24): 6980-6989.]   
[4]Lee JW,Noh HJ,Lee Y,et al. Spatial paterns,ecological niches, and interspecific competition of avian brood parasites: Inferring from a case study of Korea[J]. Ecology and Evolution,2014,4(18): 3689-3702.   
[5]彭建,李慧蕾,刘焱序,等.雄安新区生态安全格局识别与优化 策略[J].地理学报,2018,73(4):701-710.[Peng Jian,Li Huilei, Liu Yanxu,et al.Identification and optimization of ecological security pattern in Xiong'an New Area[J].Acta Geographica Sinica, 2018, 73(4): 701-710.]   
[6]赵筱青,谭琨,易琦,等.典型高原湖泊流域生态安全格局构建 以杞麓湖流域为例[J].中国环境科学,2019,39(2):768- 777.[Zhao Xiaoqing,Tan Kun, Yi Qi,et al. Constrution of ecological security patern in typical plateau lake basin: A case of the Qilu Lake Basin[J]. China Environmental Science,2019,39(2): 768- 777.]   
[7]杨志广,蒋志云,郭程轩,等.基于形态空间格局分析和最小累 积阻力模型的广州市生态网络构建[J]).应用生态学报,2018, 29(10): 3367-3376.[Yang Zhiguang, Jiang Zhiyun, Guo Chengxuan,et al.Construction of ecological network using morphological spatial pattern analysis and minimal cumulative resistance models in Guangzhou City, China[J].Chinese Journal of Applied Ecology, 2018,29(10): 3367-3376.]   
[8]陈德权,兰泽英,李玮麒.基于最小累积阻力模型的广东省陆域 生态安全格局构建[J].生态与农村环境学报,2019,35():826- 835.[Chen Dequan,Lan Zeying,Li Weiqi. Construction of land ecological security in Guangdong Province from the perspective of ecological demand[J]. Journal of Ecology and Rural Environment, 2019,35(7): 826-835.]   
[9]Loro M, Ortega E,Arce R M.Ecological connectivity analysis to reduce the barrer effectofroads.Aninnovativegraph-theoryapproach to define wildlife corridors with multiple paths and without bottlenecks[J].Landscape and Urban Planning,2015,139: 149-16.   
[10] Cong PF, Chen K X,Qu L M,et al. Determination of landscape ecological network of wetlands in the Yellow River Delta[J]. Wetlands,2020,40: 2729-2739.   
[11] 张玉虎,李义禄,贾海峰.永定河流域门头沟区景观生态安全格 局评价[J].干旱区地理,2013,36(6):1049-1057.[Zhang Yuhu, Li Yilu, Jia Haifeng.Constructing landscape ecological security pattern in Yongding River Watershed: A case of Mengtougou Basin, Beijing[J]. Arid Land Geography,2013,36(6): 1049-1057.]   
[12]Peng J, Yang Y,Liu Y X,et al.Linking ecosystem services and circuit theory to identify ecological security patterns[J]. Science of the Total Environment, 2018,644: 781-790.   
[13] 倪庆琳,丁忠义,侯湖平,等.基于电路理论的生态格局识别与 保护研究——以宁武县为例[J].干旱区资源与环境,2019,33 (5): 67-73.[Ni Qinglin, Ding Zhongyi, Hou Huping,et al. Ecological pattern recognition and protection based on circuit theory[J]. Journal of Arid Land Resources and Environment, 2O19,33(5): 67-73.]   
[14]彭建,赵会娟,刘焱序,等.区域生态安全格局构建研究进展与 展望[J].地理研究,2017,36(3):407-419.[Peng Jian,Zhao Huijuan, Liu Yanxu,et al. Research progressand prospect on regional ecological securitypattern construction[J]. Geographical Research,2017,36(3): 407-419.]   
[15] 汤洁,汪雪格,李昭阳,等.基于CA-Markov模型的吉林省西部 土地利用景观格局变化趋势预测[J].吉林大学学报(地球科学 版),2010,40(2): 405-411.[Tag Jie,Wang Xuege,Li Zhaoyang, et al.The tendency forecast onlanduse landscapepattrn change in western Jilin Province based on CA-Markov model[J]. Journal of Jilin University (Earth Science Edition),2010,40(2): 405-411.]   
[16]蒙吉军,王雅,王晓东,等.基于最小累积阻力模型的贵阳市景 观生态安全格局构建[J].长江流域资源与环境,2016,25(7): 1052-1061.[Meng Jijun,Wang Ya,Wang Xiaodong,et al. Construction of landscape ecological securitypattrn in Guiyang based on MCR model[J]. Resources and Environment in the Yangtze Basin,2016,25(7): 1052-1061.]   
[17] 谢高地,张彩霞,张雷明,等.基于单位面积价值当量因子的生 态系统服务价值化方法改进[J].自然资源学报,2015,30(8): 1243-1254. [Xie Gaodi, Zhang Caixia, Zhang Leiming, et al. Improvement of the evaluation method for ecosystem service value based on per unit area[J]. Journal of Natural Resources,2015,30 (8): 1243-1254.]   
[18] 谢花林,李秀彬.基于GIS的农村住区生态重要性空间评价及 其分区管制—以兴国县长冈乡为例[J].生态学报,2011,31 (1): 230-238.[Xie Hualin, Li Xiubin. Spatial assessment and zoning regulations of ecological importance based on GIS for rural habitation in Changgang Town, Xinguo County[J]. Acta Ecologica Sinica, 2011,31(1): 230-238.]   
[19]Renard K G,Foster G R, Weesies G A,et al. Predicting soil erosion by water: A guide to conservation planning with the Revised Universal Soil Loss Equation (RUSLE)[M]. Washington DC, USA: United States Department of Agriculture (USDA),1997: 1-367.   
[20] 邹雅婧,闫庆武,谭学玲,等.渭北矿区土壤侵蚀评估及驱动因 素分析[J].干旱区地理,2019,42(6):1387-1394.[Zou Yajing, Yan Qingwu,Tan Xueling,et al. Evaluation of soil erosion and driving factors analysis in Weibei mining area[J].Arid Land Geography,2019,42(6): 1387-1394.]   
[21] 李百安.基于USLE模型的吉林梨树县土壤侵蚀现状初步分析 [D]. 长春:东北师范大学,2015.[Li Baian.A preliminary analysis of the current situation of soil erosion in Lishu County of Jilin based on USLE model[D]. Changchun: Northeast Normal University,2015.]   
[22] 柳艺博.东北黑土区土壤侵蚀空间格局研究[D].杨凌:西北农 林科技大学,2009.[Liu Yibo.Spatial distribution of soil erosion in black soil region of northeast China[D]. Yangling: Northwest A

# 干吴区地理

α  UveIsILy,∠UUy.」 [23]王治江,李培军,万忠成,等.辽宁省生态系统服务重要性评价 [J].生态学杂志,2007,26(10): 1606-1610.[Wang Zhijiang,Li Peijun,Wan Zhongcheng,et al.Assessment of ecosystem service importance in Liaoning Province[J].Chinese Journal of Ecology,   
2007,26(10): 1606-1610.] [24]师长兴.砾石对土壤可蚀性的影响及土壤可蚀性值估算方法 [J].土壤通报,2009,40(6): 1398-1401.[Shi Changxing.Effects of gravel content on soil erodibility and the methods of estimating soil erodibility factor K[J].Chinese Journal of Soil Science,2009,   
40(6): 1398-1401.] [25] 杨勤科,郭明航,李智广,等.全国土壤侵蚀地形因子提取与初 步分析[J].中国水土保持,2013(10):17-21.[Yang Qinke,Guo Minghang,Li Zhiguang,et al. Extraction and preliminary analysis of topographic factors of soil erosion in China[J]. Soil and Water Conservation in China,2013(10): 17-21.] [26] 周伏建,陈明华,林福兴,等.福建省降雨侵蚀力指标R值[J].水 土保持学报,1995,9(1):13-18.[Zhou Fujian,Chen Minghua,Lin Fuxing,et al. The rainfall erosivity index in Fujian Province[J]. Journal of Soil and Water Conservation,1995,9(1):13-18.] [27] 梁友嘉,徐中民.基于LUCC 和夜间灯光辐射数据的张掖市甘 州区人口空间分布建模[J].冰川冻土，2012,34(4):999-1006. [Liang Youjia,Xu Zhongmin.Modeling the spatial distribution of population based on night light radiation and LUCC:A case study in Ganzhou District, Zhangye Municipality[J]. Journal of Glaciology and Geocryology,2012,34(4): 999-1006.]   
[28] 张豆,渠丽萍,张桀.基于生态供需视角的生态安全格局构建 与优化—以长三角地区为例[J].生态学报,2019,39(20): 7525-7537.[Zhang Dou,Ju Liping,Zhang Jiehao.Ecological security pattern construction method based on the perspective of ecological supply and demand:A case study of Yangtze River Delta [J].Acta Ecologica Sinica,2019,39(20): 7525-7537.]   
[29] 彭建,郭小楠,胡熠娜,等.基于地质灾害敏感性的山地生态安 全格局构建—以云南省玉溪市为例[J].应用生态学报, 2017,28(2):627-635.[Peng Jian,Guo Xiaonan,Hu Yina,et al. Constructing ecological security patterns in mountain areas based on geological disaster sensitivity:A case study in Yuxi City,Yunnan Province,China[J].Chinese Journal of Applied Ecology, 2017,28(2): 627-635.]   
[30] 宋利利,秦明周.整合电路理论的生态廊道及其重要性识别[J]. 应用生态学报,2016,27(10): 3344-3352.[Song Lili, Qin Mingzhou.Identification of ecological corridors and its importance by integrating circuit theory[J]. Chinese Journal of Applied Ecology, 2016,27(10): 3344-3352.]   
[31]朱强,俞孔坚,李迪华.景观规划中的生态廊道宽度[J].生态学 报,2005,25(9): 2406-2412.[Zhu Qiang,Yu Kongjian,Li Dihua. The width of ecological corridor in landscape planning[J].Acta Ecologica Sinica,2005,25(9): 2406-2412.]   
[32] 黄九明.基于电路理论的济南市生态安全格局构建研究[D].北 京:中国地质大学,2020.[Huang Jiuming.Study on the space demarcation and control measures of Jinan City based on the niche fitness model[D]. Beijing: China University of Geosciences,2020.]

# Construction of ecological security pattern in western Jilin Province

ZHANG Meng'， LIU Jiping1²， ZHAO Dandan1² (1.College of Tourism and Geoscience,Jilin Normal University,Siping 136Ooo,Jilin,China; 2.Institute of Resource Conservationand Utilization,Jilin Normal University,Siping 136o,Jilin,China)

Abstract: The frequency of various ecological problems and the disturbances caused by human activities have brought about significant changes in the structure and function of the ecosystems and affcted the ecological security in western Jilin Province. The construction of ecological security pattrns can effectively guarantee regional ecological security,which is especially important for the environmental improvement of ecologically fragile areas.Western Jilin Province is a typical ecologically fragile area in China and an important ecological barier within Jilin Province.Taking western Jilin Province as the study area,four indicators (biodiversity service value,water security,soil conservation,and ecological demands）were selected to identify ecological sources through ecosystem importance evaluation and ecological demand analysis.We used circuit theory combined with the Linkage Mapper tool and Circuitscape software to identify ecological corridors,pinch point regions,and ecological improvement regions and to construct an ecological security pattern for western Jilin Province. On this basis,we then put forward a reasonable ecological security pattern protection strategy. The research results demonstrated the folowing: (1) There are 18 ecological source areas in the study area. These account for $8 . 5 7 \%$ of the study area, mainly in the wetlands around the existing protected areas.Ecological source areas within nature reserves should focus on further improving existing protection policies,and ecological source areas outside nature reserves should focus on strengthening protection. (2） There are 38 key corridors and seven potential corridors,mainly in the central and eastern regions.The corridors in the middle are distributed in a netlike patern,and those in the east are scatered to provide room for animal migration.The pinch point region is relatively concentrated in the southwest and east to maintain landscape connectivity.The ecological improvement region has relatively high amounts of building land and saline land,and the southwestern and eastern areas have high improvement coeficients.The improvement areas can be divided into primary corridor ecological improvement regions and secondary corridor ecological improvement regions, with graded protection. (3)On the basis of constructing comprehensive ecological security pattrns,such as ecological sources，corridors,pinch point regions,and ecological improvement regions,we put forward a targeted strategy regarding ecological security pattrn called“one belt，two axis，five regions,and five groups”. In previousstudies,only the construction of ecological sources has been considered, whereas the further construction of ecological corridors has been neglected.Still,the construction of ecologicalcorridors based on circuit theory and the identification of pinch points and ecological improvement regions can improve the construction of ecological corridor systems. Circuit theory treats animal migration as a random change that is not predictive to the surrounding environment and is in line with the characteristics of animals themselves,and it identifiesthe structure of ecological corridors relative to reality.It can thus provide a new reference for the construction of ecological security patterns. Constructing a comprehensive ecological security pattern and proposing a reasonable conservation strategy wil provide a reference for decision-making to ensure regional security and coordinated economic and ecological development in western Jilin Province.

Key words: ecological security pattern; circuit theory； ecological service functions； western Jilin Province