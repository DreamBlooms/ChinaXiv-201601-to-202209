# 基于有向含权复杂网络的城市交通路网关键路段识别

尹小庆，莫宇迪，林云，胡攀峰，汪浩(重庆大学 机械工程学院，重庆 400044)

摘要：城市交通路网中的关键路段虽然很少，但对整个交通路网的流通性影响很大。针对目前基于复杂网络识别城市交通路网关键路段缺乏考虑现实影响因素和路段方向性问题，提出了一种基于有向含权复杂网络的关键路段识别方法。第一阶段利用复杂网络理论将城市交通路网构建成有向含权复杂网络模型；第二阶段利用LinkRank算法对复杂网络中边进行重要度排序，以此识别关键边，即城市交通路网关键路段；第三阶段利用变异的易感-感染（susceptible-infective，SI）模型对关键路段进行影响评估。通过对浙江省海宁市城区的城市交通路网分析，验证了方法的实用性和有效性。

关键词：城市交通路网；关键路段；有向含权复杂网络；LinkRank算法；变异SI模型 中图分类号：U491 doi: 10.3969/j.issn.1001-3695.2018.04.0374

# Critical road sections identification of urban traffic road network based on weighted and directed complex networks

Yin Xiaoqing†, Mo Yudi, Lin Yun, Hu Panfeng,Wang Hao (College of Mechanical Engineering,Chongqing University,Chongqing 40oo44, China)

Abstract: Althoughthecriticalroadsectionsoftheurbantraficroad networkarefew,theyhaveagreat impactonthecirculation oftheentire traficnetwork.Aimingatthelackofconsiderationofrealisticinfluencingfactorsanddirectionalityofroadsections inthecriticalroad sections ofurban traffcroad network identification basedoncomplex networks,thispaper proposedan identificationmethodofcriticalroadsectionsbasedonweightedanddirectedcomplex networks.Atthefirststage,itemployed thecomplex network theory to constructthe urban traficroad network as a weightedand directed complex network model; At thesecondstage,itemployedtheLinkRankalgorithmtosorteimportanceofedges incomplexnetworks,anditidentifiedthe criticaledgesbysortingresult,thatis,thecriticalsectionsofurbantraficroad network.;Atthethirdstage,itemployedthe variantsusceptible-infective (SI) model toevaluatetheimpactofcriticalroadsectios.Throughtheanalysisoftheurbantraffic road network in Haining City, it verifies the practicability and efectiveness of the method.\`

Keywords: urbantraficroadnetwork;citicalroad sections; weightedanddirectedcomplexnetworks; theLinkRankalgorithm; the variant SI model

# 0 引言

城市交通路网中的关键边虽然很少，但影响着整个网络的流通性。当城市交通路网关键路段失效，即关键路段发生异常（如交通堵塞、事故及施工等)，将导致交通路网整体流通性严重下降，甚至是网络的大规模瘫痪。因此识别城市交通路网中的关键路段具有重要意义，能为城市交通路网中关键路段的日常交通控制管理提供侧重点，也能为城市交通规划和路网改造提供理论依据和技术支撑。

随着小世界特性[1]和无标度特性[2]的提出，复杂网络理论及其应用发展迅速。其中复杂网络中关键边识别问题已有许多国内外学者进行研究，如Bal等人[3]提出通过移除网络中某条边后计算网络最短路径的变化情况判断该条边的重要性；Girvan等人[4在介数中心性的基础上，提出边介数的概念来衡量网络中边的重要性，边介数越大表明边在网络中越重要，边对网络资源的传输能力和控制能力越强；文献[5]采用熵权法评估边介数、生成树数量下降率和平均距离增长率三个边重要性指标后获得各自的权重，并以三个指标的综合权重作为边重要度排序的指标等。目前，已经有许多学者利用复杂网络关键边识别方法识别现实网络中的关键边：在电力网络中，Fang等人[6提出了一种基于最大流量的复杂网络方法识别电网系统中的关键线路；文献[7]结合复杂网络理论中凝聚度指标，提出了一种基于网络凝聚度的关键线路辨识方法；在军事网络中，文献[8,9]通过考虑复杂网络中的边介数和端点对边支撑作用识别作战网络和舰艇编队协同反导网络中的关键边等。也有少部分学者利用复杂网网络理论识别交通路网中的关键路段，如Chinthavali[1o]在复杂路网的对偶拓扑结构的基础上，提出了一种基于信息指数的改进中心性指标，以此识别网络模型中的关键节点，即关键路段；张喜平等人[11,2]提出一种基于对偶图节点重要度评价的道路网自动选取方法，该方法通过引入了 $\mathrm { ~ m ~ }$ 阶邻居节点概念，考虑了对偶图中节点度、介中心及节点间距离等因素，并顾及到节点自身及1到m阶邻居节点的重要度贡献。此外，还有部分文献同样对城市交通路网进行对偶建模后，基于度、 $\mathbf { k }$ -核分解、介数和接近度等复杂网络指标识别路网中的关键路段[13,14]。

综上所述，目前利用复杂网络理论对城市交通路网关键路段识别的方法基本都是在构建城市交通路网的对偶拓扑结构的基础上，利用复杂网络中基于结构的关键节点识别方法[15]识别网络中的关键节点，即路网中的关键路段。这类方法识别关键路段存在着以下不足：a)仅仅考虑城市交通路网中度、介数等结构因素，缺少考虑路段车流量、路段宽度、路段平坦程度和路段街道化程度等影响城市交通路网流通性的现实因素；b)缺少考虑城市交通路网的方向性，因为现实城市交通路网中路段往往具有行驶方向。

鉴于此，提出一种基于有向含权复杂网络的城市交通路网关键路段识别方法。首先，引入复杂网络理论，综合考虑路段车流量、路段宽度、路段平坦程度和路段街道化程度等现实因素，建立有向含权复杂网络模型；其次，利用LinkRank算法对复杂网络模型中的边进行重要度排序，识别城市交通路网关键路段；最后，利用变异SI模型评估识别方法的准确性和有效性。

# 1基于复杂网络的城市交通路网建模

将城市交通路网映射为复杂网络，一般采用原始法[16]和对偶法[17]。其中，原始法将城市交通路网中的交叉路口和路段分别映射为复杂网络中的节点和边，如图1过程a所示；对偶法将城市交通路网中的交叉路口和路段分别映射为复杂网络中的边和节点，如图1过程c所示。本文利用原始法将城市交通路网映射为复杂网络模型，并考虑城市交通路网的方向和权重：a)将城市交通路网中的交叉路口和路段分别映射为复杂网络中的节点（ $\left. { N _ { i } } \right.$ ）和无向边 $( E _ { i j } )$ ，如图1过程a所示；b）将城市交通路网中路段行驶方向映射为复杂网络中边的方向，即路段为双向行使道路时为双向边，单向行驶道路时为单向边；将影响城市交通路网中路段流通性的现实因素的综合评价值映射为有向边的权重（ $W _ { i j } )$ ，如图1过程b所示。影响城市交通路网中路段流通性的现实因素的综合评价见表1。其中路口 $i$ 到路□ $j$ 对应的有向路段的综合评价值 $W _ { i j }$ 计算公式如下：

$$
W _ { i j } = \sum _ { k = 1 } ^ { 4 } f _ { k } \cdot w _ { k }
$$

其中： $f _ { k }$ 表示因素 $k$ 的评分； $w _ { k }$ 表示因素 $k$ 的相对权重，相对权重由专家评分法确定。其中，车流量取早晚高峰 $7 { : } 0 0 { \sim } 9 { : } 0 0$ ，17:00\~19:00的平均值。

![](images/7de301bb766ccbc0e2ba4901c96a9c705515c9d43b202fb8e3ce6cfd2493993d.jpg)  
图1城市交通路网复杂网络建模过程

表1影响城市交通路网中路段流通性的现实因素综合评价  

<html><body><table><tr><td rowspan="2">评分</td><td rowspan="2">宽度W/m</td><td rowspan="2">平坦程度/S</td><td rowspan="2">车流量F /辆/h</td><td rowspan="2">街道化程度D （商店数/100m）</td></tr><tr><td></td></tr><tr><td>3</td><td>W≤15</td><td>颠簸</td><td>F≥2000</td><td>D≥8</td></tr><tr><td>1</td><td>15<W<20</td><td>轻微颠簸</td><td>500<F<2000</td><td>3<D<8</td></tr><tr><td>0</td><td>W≥20</td><td>平坦</td><td>W≤500</td><td>D≤3</td></tr></table></body></html>

# 2 基于LinkRank 算法的城市交通路网路段重要度排序

针对复杂网络关键边识别，Kim等人[18]提出了一种LinkRank算法，能有效地解决无向网络或有向网络中关键边识别问题。

LinkRank算法是在著名Google 搜索引擎算法PageRank算法[19]基础上提出的一种对复杂网络边进行重要度排序的算法。其中PageRank 算法计算公式如下：

$$
\pi ^ { T } { = } \pi ^ { T } G
$$

其中： $\pmb { \pi } ^ { T }$ 表示矩阵 $\pmb { G }$ 的固定行向量，称为PageRank向量， $\pmb { \pi } ^ { T }$ 中每个元素 ${ \pi } _ { i }$ 表示在某个静止状态下，随机步骤停留在节点 $i$ 的概率。在初始状态下，每个 $\pi _ { i }$ 值可以设置为 $1 / n$ ， $n$ 为网络中节点的数量。矩阵 $\textbf { \textit { G } }$ 叫做Google 矩阵，其计算公式如下：

$$
G _ { i j } = \alpha \frac { A _ { i j } } { A _ { i } ^ { o u t } } + \frac { 1 } { N } ( \alpha a _ { i } + 1 - \alpha )
$$

其中： $A _ { i j }$ 表示网络邻接矩阵的元素； $A _ { i } ^ { o u t }$ 表示网络中节点 $i$ 的出度；（ $\cdot 1 { - } a$ ）表示随机步骤不跟随超链接打开一个网页，而是随机打开某个网页的概率；当节点 $i$ 为悬挂节点时， $a _ { i } { = } 1$ ，否则，$a _ { i } { = } 0$ ；当 $A _ { i } ^ { o u t } = 0$ 时， $A _ { i j } / A _ { i } ^ { o u t } = 0$ ; $\scriptstyle a$ 表示跟随超链接打开网页的概率，一般取0.85。基于以上PageRank 算法公式，LinkRank 算法公式如下：

$$
L _ { i j } = \pi _ { i } G _ { i j }
$$

其中： $L _ { i j }$ 表示LinkRank 矩阵中的元素； ${ \boldsymbol { \pi } } _ { i }$ 表示PageRank向量中的元素； $G _ { i j }$ 表示Google 矩阵中的元素。

具体重要度排序过程如图2所示。

![](images/37b66c7111cd20fde83df2be822e30784b464ca7d23c14c1671fad74c63e5064.jpg)  
图2基于LinkRank 算法的交通路网路段重要度排序过程具体步骤如下：

(1)获得含权邻接矩阵 $\boldsymbol { W } _ { \circ }$ 将构建的有向含权复杂网络模型利用含权邻接矩阵表示。

（2）获得Google矩阵 $\textbf { \textit { G } }$ 。将含权邻接矩阵按式（3）转换为 Google矩阵。其中， $A _ { i j }$ 经改进后表示网络含权邻接矩阵元素； $A _ { i } ^ { o u t }$ 经改进后表示所有节点 $i$ 指向邻接节点边的权重和。

（3）确定初始PageRank向量 $\pi ^ { T }$ ：将每个 $\pi _ { i }$ 值设为 $1 / n$ 。

（4）迭代。根据式（2）对Google 矩阵 $\textbf { \textit { G } }$ 和初始PageRank向量 $\pmb { \pi } ^ { T }$ 迭代运算，计算每次PageRank向量迭代前后的差值向量 $\varDelta$ ，差值向量 $\varDelta$ 中有大于等于 $0 . 0 0 0 0 0 0 0 1$ 的值，则继续迭代。

（5）获得结果PageRank向量 $\pi ^ { { \boldsymbol { \pi } } }$ 。迭代过程中差值向量$\varDelta$ 的值都小于 $0 . 0 0 0 0 0 0 0 1$ ，则迭代停止，获得结果PageRank向量。

（6）获得LinkRank矩阵 $\pmb { L }$ 。将获得的结果PageRank向量$\pmb { \pi } ^ { T L }$ 和Google 矩阵 $\textbf { \textit { G } }$ 按照式（4）相乘，得到相应的LinkRank矩阵。

（7）获得排序结果。当节点 $i$ 与 $j$ 间是单向边时，取单向边对应的LinkRank 值为路段 $E _ { i j }$ 的重要度值；当节点 $i$ 与 $j$ 间是双向边时，取LinkRank矩阵中 $L _ { i j }$ 和 $L _ { j i }$ 值平均化后获得路段$E _ { i j }$ 的重要度值，通过对城市交通路网各路段重要度值的排序，获得各路段重要度排序结果。

# 3基于变异SI模型的城市交通路网关键路段影响评估

变异SI模型[20]是在标准SI模型[2I]基础上提出的，其假设每个节点具有相同感染性A，即每个时间步长内，每个节点产生A个接触，其中A是常数，一般取复杂网络的平均度值。从网络结构角度分析，变异SI模型感染过程如图3所示。具体过程如下：某一时刻网络中出现受感染节点（图4中黑色节点）

后，下一时间步长内，受感染节点产生A个接触，当A大于受感染节点的度时，受感染节点和所有邻居节点接触；当A小于受感染节点的度时，受感染节点在其邻居节点中随机选取A个节点进行接触。在感染过程中，受感染节点接触易受感染节点（图3中白色节点）时，易受感染节点会以 $\theta$ 的概率被感染，如图3（a）～（b）所示。以后每个时间步长内，复杂网络中会持续进行感染过程，直至网络中没有易受感染节点，整个感染过程停止，如图3（b）～（c）所示。

![](images/4b5fe31b19025f7858c10ae799c4c5b210e7707d0e245292857dec1ca0286fc2.jpg)  
图3变异SI模型感染过程示例图

城市交通路网中的路段分为正常状态和紊乱状态。处于正常状态的路段，车辆通行顺畅，不影响其邻近路段的流通性；处于紊乱状态的路段，车辆通行受阻，以一定概率影响邻近路段的流通性。城市交通路网路段的两种状态与变异SI模型中节点两种状态十分一致，因此选取变异SI模型对关键路段影响进行评估。

利用对偶法对城市交通路网进行重新建模，获得对偶拓扑构建的复杂路网模型，即将路段映射为节点、路口映射为边。其中为使感染过程更符合现实情况，每条路段对应节点的感染概率 $\theta$ 如下:

$$
\theta = \frac { ( \theta _ { i j } + \theta _ { j i } ) } { 2 }
$$

$$
\theta _ { i j } = \frac { W _ { i j } } { 3 \times \sum _ { k = 1 } ^ { 4 } w _ { k } } { \times } 1 0 0 \%
$$

其中： $\theta _ { i j }$ 为有向路段 $E _ { i j }$ 的感染概率； $W _ { i j }$ 为有向路段 $E _ { i j }$ 的综合权重； $w _ { k }$ 表示因素 $k$ 的相对权重。

主要评估流程如下：

a）分别选择排序前 $10 \%$ 、 $10 \% { \sim } 5 0 \%$ 之间和后 $50 \%$ 的路网路段所代表的网络节点进行病毒感染。b）经过变异SI模型的感染过程后，检测某个网络节点对网络的综合影响力，这种影响力通过该节点在网络中的感染速度表示。c）如果算法求得的排序结果与感染结果相一致，说明识别方法具有准确性和有效性。

相对于基于LinkRank算法识别交通路网中的关键路段能充分考虑路段的现实影响因素和实际方向性，本文利用变异 SI模型进行评估前，对路网进行对偶复杂网络建模，缺少考虑路段的方向性，并且考虑影响拥堵的现实因素时，将其转换为每个路段代表节点的感染概率 $\theta$ ，其会造成该路段对其他邻居路段的影响力具有相同程度，没有结合邻居路段实际情况考虑。但本文在评估验证过程中，利用的是变异SI模型的病毒传染效果，越关键的路段，对路网中邻近路段乃至整个路网影响越大，即体现于病毒在整个网络中的传染速率大小。因此，本文基于变异SI模型评估验证具有合理性。

# 4 城市交通路网关键路段识别应用分析

随着经济开发区的大规模引入和汽车保有量的不断增加，浙江省海宁市城区交通拥堵现象日益繁重，尤其节假日或某些路段发生异常事故时，交通拥堵现象尤为严重，因此识别路网中关键路段至关重要。通过Google地图搜索海宁市城区道路信息，得到海宁市城区实际路网图，如图4所示。根据地图信息选取城区主要道路，分别得到54个路口和86条路段。

![](images/d9e1b8a9a036ae2a6283d76cd073c28c15de68117a81fb95abbac53075080d54.jpg)  
图4海宁市城区实际路网图

# 4.1基于复杂网络的城市交通网络建模

针对海宁市城区交通路网，首先利用原始法分别将交通路网中的路口和路段映射为复杂网络中的节点和边后；再将城市交通路网中各路段行驶方向映射为复杂网络中边的方向；最后通过实地调研确定每条路段各因素的评分后，按式（1）算出各路段的综合重要度，将其映射为边的综合权重，其中影响交通路网中路段流通性的现实因素路段宽度、路段平坦程度、路段车流量和路段街道化程度的相对权重由专家评分法获得，分别为 $w _ { 1 } { = } 1$ ， $w _ { 2 } { = } 1$ ， $w _ { 3 } { = } 2$ ， $w _ { 4 } { = } 1$ 。并且借助复杂网络建模工具一Gephi，建立海宁市城区交通路网的网络模型，如图5所示。

![](images/58d5190751321a18b54e37192cfe4adef67456beb7814a334095d1aaae38ec36.jpg)  
图5海宁市城区交通路网复杂网络模型

# 4.2城市交通路网各路段重要度排序

基于LinkRank算法对复杂网络模型中的各路段进行重要度排序。根据图2的排序流程应用Java编程对路段进行重要度排序，识别出的关键路段如图6所示，每个网络路段的重要度值如表2所示。由于篇幅限制，仅列出前八名（1\~8）、中间4名（41\~44）和后四名（83\~86）路段的排序结果。

![](images/012d325d0058011ce0a19b229adc7a620d13dbeb31918e8f0d02695d2b6454b5.jpg)  
图6城市交通路网路段重要度排序图

表2城市交通路网复杂网络模型路段重要度排序表  

<html><body><table><tr><td>排序</td><td>路段</td><td>重要度</td></tr><tr><td>1</td><td>E (21)(22) (前10%)</td><td>0.009482915</td></tr><tr><td>2</td><td>E(20)(21）(前10%)</td><td>0.008763450</td></tr><tr><td>3</td><td>E (33)(34)(前10%)</td><td>0.008131934</td></tr><tr><td>4</td><td>E(34)(41）(前10%)</td><td>0.008074500</td></tr><tr><td>5</td><td>E(19)(20）(前10%)</td><td>0.007551115</td></tr><tr><td>6</td><td>E(22)(29）(前10%)</td><td>0.007442524</td></tr><tr><td>7</td><td>E (27)(32）(前10%)</td><td>0.006988808</td></tr><tr><td>8</td><td>E (35)(36）(前10%)</td><td>0.006874801</td></tr><tr><td>41</td><td>E (41)(22)</td><td>0.005260422</td></tr><tr><td>42</td><td>E(14)(15)</td><td>0.005213975</td></tr><tr><td>43</td><td>E(40)(41)</td><td>0.005145288</td></tr><tr><td>44</td><td>E (44(51)</td><td>0.005063467</td></tr><tr><td>83</td><td>E (1)(23)</td><td>0.002433527</td></tr><tr><td>84</td><td>E (43)(49)</td><td>0.001906892</td></tr><tr><td>85</td><td>E (23)(36)</td><td>0.001843300</td></tr><tr><td>86</td><td>E (36)(43)</td><td>0.001827296</td></tr></table></body></html>

选取排序前 $10 \%$ 的路段作为交通路网的关键路段，分别为E(21)(22)、E(20)(21)、E(33)(34)、E(34)(41)、E(19)(20)、E(22)(29)、E(27)(32)和E(35)(36)o

# 4.3城市交通路网关键路段影响评估

选取变异SI模型对关键路段的影响力进行评估。针对海宁市城区交通路网，利用对偶法分别将交通路网中的路段和路口映射为复杂网络中的节点和边，建立评估所需的复杂网络模型。具体基于变异SI模型的关键路段影响评估过程通过Java 编程实现。

分别选取排序结果中前 $10 \%$ 路段（路段 $E _ { ( 2 1 ) ( 2 2 ) }$ 、路段 $E$ (20)(21)）、 $10 \% { \sim } 5 0 \%$ 路段（路段 ${ \cal E } _ { ( 1 4 ) ( 1 5 ) }$ 、路段 ${ \cal E } _ { ( 4 0 ) ( 4 1 ) } \dot { }$ ）和后 $50 \%$ 路段（路段 $E _ { ( 2 3 ) ( 3 6 ) }$ 、路段 ${ \cal E } _ { ( 3 6 ) ( 4 3 ) }$ ）进行感染，获得感染效果，如图7所示。

从图中可以发现，路段 $E _ { ( 2 1 ) ( 2 2 ) \setminus } E _ { ( 2 0 ) ( 2 1 ) \setminus } E _ { ( 3 3 ) ( 3 4 ) \setminus } E _ { ( 3 4 ) ( 4 1 ) \setminus }$ $E _ { ( 1 9 ) ( 2 0 ) }$ 、 $E _ { ( 2 2 ) ( 2 9 ) }$ 、 $E _ { ( 2 7 ) ( 3 2 ) }$ 和 ${ \cal E } _ { ( 3 5 ) ( 3 6 ) }$ 的感染速度逐渐减慢，且前$10 \%$ 的路段(路段 $\begin{array} { r } { E _ { ( 2 1 ) ( 2 2 ) \setminus E ( 2 0 ) ( 2 1 ) } . } \end{array}$ 的感染速度明显大于 $1 0 \% { \sim } 5 0 \%$ 的路段（路段 ${ \cal E } _ { ( 1 4 ) ( 1 5 ) }$ 、 ${ E _ { ( 4 0 ) ( 4 1 ) } } )$ ，同样 $10 \% { \sim } 5 0 \%$ 的路段（路段$E _ { ( 1 4 ) ( 1 5 ) } , E _ { ( 4 0 ) ( 4 1 ) } \rangle$ 的感染速度远大于后 $50 \%$ 的路段（路段 ${ \cal E } _ { ( 2 3 ) ( 3 6 ) }$ ${ \cal E } _ { ( 3 6 ) ( 4 3 ) } )$ 。由此表明，利用变异SI模型求得路段的影响力与使用LinkRank算法求得路段的重要度相一致，即网络路段的重要度值越大，该路段的影响力越大。因此，评估结果表明识别出的关键城市交通路段是准确有效的。

![](images/89e7157a9b73df3380a52ba7e0b8cde56d2d8fe95994285e298f7a47afc742fd.jpg)  
图7路段感染效果

从现实角度评估，识别出的关键路段属于城区中心地带，道路狭窄，街道化程度大，在早晚高峰期一直存在堵车现象，因此也表明识别出的关键城市交通路段准确有效。

# 5 结束语

识别城市交通路网中的关键路段有助于路网流通性的改善针对城市交通路网关键路段识别问题，利用复杂网络理论建立了交通路网有向含权复杂网络模型。该模型考虑了路段宽度、路段平坦程度、车流量和路段街道化程度等现实影响因素，且考虑了路段行使方向；在复杂网络模型的基础上，结合LinkRank算法对网络中的路段进行重要度排序，以此识别关键路段，该方法在排序过程中考虑了路网的权重和方向性；针对识别的关键路段，通过对偶法对城市交通路网重新复杂网络建模后，利用变异SI模型对其影响进行了评估。通过对海宁市城区交通路网进行实证分析，表明方法是有效的。由于本文选取影响交通路网拥堵的现实影响因素（宽度、平坦程度、车流量和街道化程度）十分具有代表性和普遍适用性，所以所建模型及其识别方法同样适用于其他具有不同交通特点的城市。此外，由于目前仅考虑城市交通路网路段的影响因素以及现实影响因素的静态性，如何科学合理地将交通路网中路口的影响因素和影响因素的动态性同时考虑需要进一步研究。

# 参考文献：

[1]Watts DJ, Strogatz S H.Collective dynamics of small-world'networks[J]. Nature,1998,393 (6684): 440-442.   
[2]Barabasi A L,Albert R.Emergence of scaling in random networks [J]. Science,1999,286(5439): 509-512.   
[3]Ball M O,Golden BL,Vohra RV.Finding the most vital arcs in a network [J]. Operations Research Letters,1989,8(2): 73-76.

[4]Girvan M,Newman M E.Community structure in social and biological networks [J].Proceedings of the National Academy of Sciences of the United States ofAmerica,2001,99(12):7821-7826.

[5]Lu Zheming,Feng Yapei. Critical nodes and links evaluation with multicriteria based on entropy-weighted method [J].Journal of Information Hiding & Multimedia Signal Processing,2015,6(6):1062-1076.

[6]Fang J,Su C,Chen Z,et al.Power system structural vulnerability assessment based on an improved maximum flow approach[J].IEEE Trans on Smart Grid,2018,9 (2): 777-785.

[7]傅杰，邹艳丽，谢蓉．基于复杂网络理论的电力网络关键线路识别[J]. 复杂系统与复杂性科学,2017,14(3):91-96.(FuJie,Zou Yanli,Xie Rong. The critical lines identification of the power grids based on the complex network theory[J]. Complex Systems& Complexity Science,2017,14 (3): 91-96.)

[8]邱原，邢焕革．基于复杂理论的作战网络关键边评估方法[J].兵工自 动化,2011,30 (8): 22-26.(Qiu Yan,Xing Huange.Evaluation method for critical edge of operation networks based on complex theory[J]. Ordnance IndustryAutomation,2011,30(8):22-26.)

[9]夏昱，滕克难，高飞.舰艇编队协同反导网络关键边评估[J].兵工自 动化,2013,32(7): 52-54.(Xia Yu,Teng Kenan,Gao Fei.Evaluation for critical edge of warship fleet cooperation anti-missile network[J]. Ordnance Industry Automation,2013,32(7): 52-54.)

[10] Chinthavali S.Identifying the critical links in road transportation networks: centrality-based approach utilizing structural properties [R]. Oak Ridge, TN (United States): Oak Ridge NationalLaboratory, 2016.

[11]张喜平，李永树，刘刚．基于对偶拓扑结构的路网路段重要性评估方法 [J].测绘工程,2015,24(3):1-5.(Zhang Xiping,Li Yongshu,Liu Gang. Road section importance evaluation method in complex trafic road network based on dual topology[J].Engineering of Surveying & Mapping,2015,24 (3): 1-5.)

[12]刘刚，李永树，杨骏，等．对偶图节点重要度的道路网自动选取方法 [J].测绘学报,2014,43(1): 97-104.(Liu Gang,Li Yongshu,Yang Jun,et al.Auto-selection method of road networks based on evaluation of node importance for dual graph [J].Acta Geodaetica Et Cartographica Sinica, 2014,43 (1): 97-104.)

[13]赵妍，李华，王方．基于k-shell的城市路网关键路段识别方法[J]．系 统工程,2014,32(5):105-110.(Zhao Yan,LiHua,Wang Fang.Identifying key sections in urban road network based on k-shell [J].Systems Engineering,2014,32(5): 105-110.)

[14]宋海权，郭进，刘刚．基于复杂网络的城市道路重要度评价及路网自动 综合方法 [J].测绘工程,2017,26(1):8-12.(Song Haiquan,Guo Jin,Liu Gang.Auto generalization approach and importance evaluation of urban roads based on complex networks [J]. Engineering of Surveying & Mapping, 2017,26 (1): 8-12. )

[15] Lü Linyuan,Chen Duanbing,Ren Xiaolong,et al.Vital nodes identification in complex networks [J].Physics Reports,2016, 650:1-63.

[16] Barthelemy M. Spatial networks [J].Physics Reports,2011,499 (1-3):1- 101.   
[17]Liu Gang,Li Yongshu, Yang Jun,et al. Gravitational field routing strategy considering the distribution of traffic flow [J]. International Journal of Geographical Information Science,2014,28(1):39-55.   
[18] Kim Y, Son S W, Jeong H. Finding communities in directed networks [J]. PhysicalReviewE StatisticalNonlinear& SoftMatterPhysics,2O10,81(1 Pt 2):Article ID 016103.   
[19] Sergey B,Lawrence P.The anatomy of a large-scale hypertextual Web

search engine[J].Computer Networks& Isdn Systems,1998,30(1-7):107- 117.   
[20] Zhou Tao,Liu Jianguo,Bai Wenjie,et al.Behaviors of susceptible-infected epidemics on scale-free networks with identical infectivity [J].Physical ReviewE StatisticalNonlinear& Soft Matter Physics,2006,74(2):Article ID 056109.   
[21]Barthélemy M,BarratA,PastorsatorrasR,et al.Velocity and hierarchical spread of epidemic outbreaks in scale-free networks [J].Physical Review Letters,2004,92(17):Article ID 178701.