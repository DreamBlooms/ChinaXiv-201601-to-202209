# 面向生态系统多对象保护与修复的水库优化调度

刘哲杰'，白涛²，高凡¹，杨鹏年¹，王光焰³(1.新疆农业大学水利与土木工程学院,新疆 乌鲁木齐830052；2.省部共建西北旱区生态水利国家重点实验室(西安理工大学),陕西 西安710048；3.新疆塔里木河流域管理局,新疆 库尔勒841000)

摘要：近20a来,随着塔里木河(简称"塔河")流域水资源综合规划与调度的实施,已基本实现"水流到台特玛湖、大西海子水库多年平均下泄 $3 . 5 0 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 } \mathrm { w }$ 的生态输水目标。但是，塔河下游其文阔尔河与老塔里木河之间的两河区域内植被稀少、生态环境脆弱,多年的生态恢复效果并不显著。鉴于此，本文以大西海子水库为调控主体，以大西海子下泄生态水量、河道内生态基流、台特玛湖生态输水、河道外生态供水等为生态保护对象,建立了水库中长期生态优化调度模型，采用粒子群算法进行求解。结果表明：（1）优化调度后大西海子水库多年平均下泄水量为$5 . 2 3 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,满足塔河一期规划 $3 . 5 0 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 水量要求，且下游河道常流水时间显著延长；(2)优化调度后多年平均入台特玛湖水量为 $0 . 1 8 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,相较于实测数据，增加了 $2 0 . 0 \%$ ,且入湖过程更加平稳，有利于巩固已初步形成的尾闾湖泊生态系统;(3）优化调度后塔河下游河道生态基流保证率为 $5 0 . 0 \%$ ,不断流的保证率达 $6 4 . 6 \%$ ，对受人类活动影响巨大的我国最长内陆河——塔里木河下游河道生态系统具有重要积极影响;(4）优化调度后塔河下游河道外多年平均生态供水量 $1 . 6 7 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，为下游两河区域的荒漠河岸植被林生态恢复奠定了水量基础。研究成果对于塔河下游两河区域的荒漠河岸植被林修复与保护、维持河道和尾阁湖泊的生态健康、构建地下生态水银行具有重要的应用价值，也对于构建塔河生态流域具有重要的现实和推广意义。

关键词：中长期生态调度；多保护对象；河道外生态供水；人湖水量；生态基流；塔里木河

水资源是人类社会经济和生态向前发展不可缺少的基础资源。水库在水资源开发利用中担任着极其重要的角色。因此，研究水库调度问题，对水资源的统一管理和高效利用具有十分重要的意义[1]。

传统的水库调度以发电、灌溉和防洪等为目标建立调度模型，基于系统科学的思想对模型进行求解，然后制定调度方案指导水库运行。国外相比国内面向生态的水库调度研究开始较早。2014年Steinschneider等[2]提出了一种大尺度优化调度模型，在大流域水库群多目标调度问题上探讨水库协调管理措施对生态效益的贡献。2017年Sabo等[3]发表了湄公河生态调度研究成果，通过调度模型耦合了河流径流情势的结构差异性，设计了满足河流生态完整性、保证人类经济需求的径流模式。2019年Xia等4为克服传统算法的早熟收敛问题，提出了一种单纯形粒子群算法，并成功应用在了梯级水库生态调度中。2020年Wang等[5]以清江梯级水库群为研究对象，建立了考虑生态基流量和最小生态流量变化的多目标优化模型，并采用基于群体合作的协同粒子群优化算法进行求解。2021年Zhong等[6]提出了引力搜索算法，成功应用在吴江水库群生态调度中，比其他常规优化算法可以获得更好的调度方案，有效减少了不适宜的生态水量。我国针对塔里木河流域生态调度研究起步较晚。2013年邓晓雅等7基于流域水资源合理配置对塔里木河流域生态调度进行了研究，分析了生态调度与水资源合理配置的关系以及流域生态调度关键问题，制定了塔里木河流域生态调度的目标和措施以及生态调度方案。2018年王光焰等8对塔里木河水资源合理配置研究进展进行了阐述，指出生态调度、水权配置与生态补偿、跨流域调水等是塔里木河水资源研究的重点方向。徐俏等针对塔里木河下游生态输水对植被群落组成、多样性和稳定性的影响也进行了研究，结果表明自生态输水以来，植物群落的稳定性逐渐提高，但目前仍处于不稳定状态。2020年王希义等"对塔里木河下游输水工程的生态效益与社会经济效益进行了评价，结果表明自生态输水以来，塔里木河下游地区的未利用地面积变化不大，水域面积增加最显著，耕地和建筑用地面积有所增加，林地和草地的面积有所减少。

目前，塔河流域经过50多年大规模的水土开发等人类活动影响，水环境发生了很大改变，主要表现为各源流用水量增加，汇入干流的水量不断减少；干流上中游耗水量增加，达到下游的水量大幅减少；尤其在1972年大西海子水库建成后，造成下游 $3 5 7 \mathrm { k m }$ 河道长期断流，以胡杨为主要建群植物的荒漠河岸林全面衰败。针对该问题，从2000年实施了《塔里木河流域近期综合治理规划》,疏通了大西海子水库至台特玛湖间长期断流的河道，通过20多次的生态输水，缓解了沿河两岸荒漠植被的衰败趋势[1]。由于以往的研究较为单一且受时限等因素影响，只是针对已有生态措施或效果进行分析评价。鉴于此，本文利用近20a下游来水资料，以大西海子水库为调控主体，构建面向生态系统多对象保护的水库中长期生态优化调度模型，旨在充分挖掘水库生态调度潜力，保障两河(其文阔尔河-老塔里木河)区域的河道外生态供水量，以解决塔河下游流域生态水的合理分配问题，为下游流域水资源的科学管理，尤其是为干旱区内陆河流域的生态恢复提供水量支撑，对塔河下游的生态保护与修复具有重要理论意义和应用价值。

# 1大西海子水库生态调度

# 1.1 研究区概况

塔里木河(简称"塔河")是我国最长的内陆河，从源流叶尔羌河算起，全长 $2 4 8 6 \mathrm { k m }$ ,其流域平均海拔 $1 0 0 0 \mathrm { m }$ 左右，属典型的大陆性气候区，是我国乃至世界范围内生态系统最为脆弱的流域之一[12]由于受气候变化和人类活动的强烈干扰，塔里木河水资源时空分布格局发生了明显变化，特别是1972年大西海子水库建成后，导致其下游河道断流，天然植被大面积衰退，尾闾台特玛湖干涸[13]。以胡杨、怪柳灌丛为主的荒漠河岸植被是极端干旱环境下的生态廊道，在防风固沙、维持干旱区生态系统等方面具有积极影响[14]。为保护塔里木河下游流域的生态安全，拯救濒临合拢的“绿色走廊”，20世纪90年代成立了塔里木河流域管理委员会和塔里木河流域管理局。自2001年起，流域管理局根据《塔里木河流域近期综合治理规划报告》,启动了塔河流域近期综合治理工程[15]。组织实施了下游生态应急输水，期间大西海子水库积极发挥生态功能，累计输水 $8 1 . 6 1 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,平均年下泄水量 $4 . 1 3 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,超额完成了年均下泄水量 $3 . 5 0 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 的预期目标，重现了台特玛湖昔日的自然景观[16]。目前已经实现《塔里木河流域近期综合治理规划》年均下游河道下泄$3 . 5 0 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 的预期目标，但即使采用其文阔尔河、老塔里木河双河道线状同时输水，河道的自然耗水仅为 $2 . 2 6 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，入湖水量可达到 $1 . 2 4 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，远超$0 . 1 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 的入湖要求[17]。导致尾闾台特玛湖水域面积过大，无效蒸发十分严重。因此，为更好实现生态输水效果，如何在人为条件下使间歇性输水起到替代自然漫溢的功能，最大程度修复沿河两岸生态环境，是目前亟待探索解决的现实问题。

塔河下游指大西海子水库至台特玛湖区间河段，位于塔克拉玛干沙漠和库姆塔格沙漠之间，总长约 $3 5 0 \mathrm { k m }$ 。其中大西海子水库位于塔里木河干流下游沙漠平原区，坝址距第二师34团 $1 5 \mathrm { k m }$ ,距尉犁县 $1 5 5 \mathrm { k m }$ ,距库尔勒市 $2 1 0 \mathrm { k m }$ 。该区域属典型大陆性干旱气候，年降水量仅 $1 7 . 4 { \sim } 4 2 . 0 \ \mathrm { m m }$ ,蒸发量高达 $2 5 0 0 { \sim } 3 0 0 0 \ \mathrm { m m }$ ,抗逆性差,生态环境极为脆弱[18]。塔里木河下游研究区示意图如图1所示。

大西海子水库位于塔里木河干流下游沙漠平原区，始建于1958年，1972年投入运行，原为一座以农业、灌溉、防洪、生态供水为主，兼有养殖等综合利用的大(2)型水库，但2004年该水库功能调整为一座专门用于塔里木河下游生态供水的平原区中型水库，并在2012年底完成了“退出农业灌溉工程”改造[19]。由于上游输水距离遥远,地表来水不稳定、间歇性输水特征明显等特点。因此，本文将该水库定位为只有生态功能的水库，且利用该水库储水，集中调控下游河道输水，发挥其生态调蓄功能，提高输水的生态效益，实现以植被修复为目的的中长期生态调度。水库特征水位及库容见表1。

![](images/38d024e937eea3345430467c717c726cc74593281ffdfa6decf538c3f207dd4c.jpg)  
图1研究区示意图  
Fig.1 Schematic diagram of the study area

表1水库特征水位及库容  
Tab.1 Reservoir characteristic water level and capacity   

<html><body><table><tr><td>项目</td><td>特征指标/m</td><td>项目</td><td>特征指标/10m</td></tr><tr><td>死水位</td><td>846.61</td><td>死库容</td><td>600.00</td></tr><tr><td>正常蓄水位</td><td>849.25</td><td>防洪库容</td><td>3826.46</td></tr><tr><td>汛限水位</td><td>848.76</td><td>兴利库容</td><td>7431.12</td></tr><tr><td>设计洪水位</td><td>849.57</td><td>总库容</td><td>9870.00</td></tr><tr><td>校核洪水位</td><td>849.60</td><td></td><td></td></tr></table></body></html>

研究区下游河道按河流特征可分为上下两段。上段：大西海子至阿拉干段(两河区域)水系较为复杂，支汊众多，主河道在水库以下 $4 . 2 \mathrm { k m }$ 处分为东西两支，东支为其文阔尔河，河长 $2 0 4 . 5 ~ \mathrm { k m }$ ，曲直比2.48;西支为老塔里木河，河长 $1 4 3 . 8 ~ \mathrm { k m }$ ，曲直比1.74,在阿拉干汇合后折向南；下段：阿拉干至台特玛湖，河长 $1 5 3 . 1 ~ \mathrm { k m }$ ，曲直比2.17，呈南北向狭长带状分布[20]

# 1.2径流资料的处理

大西海子水库生态调度采用的基本资料有工程资料和径流资料等。工程资料包括大西海子水库特征参数(特征水位、水位-库容关系曲线等)；径流资料有大西海子水库上游距离 $1 0 0 \mathrm { k m }$ 处恰拉站的实测径流资料，中长期调度以2000年4月—2020

年3月共20a为调度期。

由于大西海子水库人库径流资料较少，因此借用阿拉尔水文站至恰拉水文站区间的单位长度河道衰减率，将已收集到的恰拉水文站径流数据推算至大西海子水库人库断面。具体计算公式为：

$$
W = W ^ { \prime } \times ( 1 - \eta \times L )
$$

式中： $W$ 为大西海子水库入库断面来水量， $1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ;W为恰拉断面来水量， $1 0 ^ { 8 } \mathrm { m } ^ { 3 } ; \eta$ 为阿拉尔水文站至恰拉水文站区间河道单位长度衰减率， $( 0 . 1 8 \%$ ； $L$ 为恰拉水文站至大西海子水库区间河道长度， $\mathrm { k m }$ 。

# 1.3优化调度模型节点图

依据塔河下游流域水资源开发利用现状，绘制涵盖水库、水文站、重要控制断面和湖泊等节点在内的水库调度网络节点图，塔里木河下游大西海子水库生态调度节点如图2所示

# 2生态调度模型的建立与求解

# 2.1调度模型的建立

在塔河流域一期综合治理规划中，提出了“大西海子水库多年平均下泄 $3 . 5 0 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,有水到达台特玛湖”的生态输水目标。可见，塔河下游的生态保护对象包括河道内生态基流、多年平均下泄生态水量。除此以外，两河区域的河道外生态水量是保障该区域生态环境恢复的关键水源。因此，在塔河下游的生态系统中，生态调度的主要对象有下泄生态总水量、河道内生态基流、河道外生境需水和入台特玛湖水量等，属于多对象保护的生态调度问题。

![](images/56b1b5d4a4219448be10235a80c488816908c4012cd9d0ed188457f0a16b9451.jpg)  
图2塔里木河下游大西海子水库生态调度节点  
Fig.2Ecological dispatch node of Daxihaizi reservoir in the lower reaches of Tarim River

本文建立的生态调度模型将下泄生态总水量、入台特玛湖水量、河道内生态基流量3个保护对象转换为约束条件：（1）大西海子水库多年平均下泄生态总水量不小于 $3 . 5 0 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ;(2）考虑到塔河一期综合治理规划中，只规定有水流到台特玛湖，但经过20多年的生态输水，水头到达台特玛湖越来越快。而台特玛湖是各种鸟类、鱼类的栖息地，保障周边生态环境的稳定，将湖面面积保持在一定范围内对当地生态环境有极大积极影响。根据樊自立等[17]对台特玛湖水域面积的研究，将提出的多年平均入湖水量不小于 $0 . 1 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 设置为模型约束条件；（3）塔河为一条内陆耗散型河流，下游来水过程极不稳定，在大西海子水库建成后河道断流近 $3 0 \mathrm { a }$ 因此只在模型中设定河道生态基流保证率为$5 0 \%$ 。对于塔河下游河道外需水而言，选择河道外生态保护与修复的关键生态期至关重要，由于塔河下游两河区域的保护性植被为胡杨，其落种、漂种与萌发的最佳时期是每年10月，因此，将10月作为关键生态期。综上所述，在满足上述(1）、(2）、(3)约束条件下，以大西海子水库下游多年平均河道外生态供水量最大为目标函数，其表达式如公式(2)所示。

$$
\operatorname* { m a x } F = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } W _ { i } , 1 \leqslant i \leqslant N
$$

式中：i为调度期内某年份； $N$ 为调度期总年份； $F$ 为多年平均河道外生态供水量， $1 0 ^ { 8 } \mathrm m ^ { 3 }$ · $W$ 为调度期内

第 $i$ 年的河道外生态供水量， $1 0 ^ { 8 } \mathrm m ^ { 3 }$

# 2.2 约束条件

（1）水量平衡约束：

$$
V _ { { \ L } _ { t } } = V _ { { \ L } _ { t - 1 } } + \frac { I _ { t } + I _ { { \ L } _ { t - 1 } } } { 2 } \Delta t - \frac { q _ { t } + q _ { t - 1 } } { 2 } \Delta t
$$

式中： $V _ { t }$ 为 $\mathbf { \Phi } _ { t }$ 时刻水库库容， $1 0 ^ { 4 } \mathrm { m } ^ { 3 } ; V _ { t - 1 }$ 为 $t { - } 1$ 时刻初水库库容， $1 0 ^ { 4 } \mathrm { m } ^ { 3 }$ ;I为 $\mathbf { \Phi } _ { t }$ 时刻的入库流量， $\mathbf { m } ^ { 3 } \cdot \mathbf { s } ^ { - 1 } ; I _ { t - 1 }$ 为$t { - } 1$ 时刻入库流量， $\mathbf { m } ^ { 3 } \cdot \mathbf { s } ^ { - 1 } \mathbf { : } \Delta t$ 为 $t \setminus t - 1$ 相邻时刻的时段长； $q _ { t }$ 为 $\mathbf { \Phi } _ { t }$ 时刻下泄流量， $\mathbf { m } ^ { 3 } { \cdot } \mathbf { s } ^ { - 1 }$ $q _ { t - 1 }$ 为 $_ { t - 1 }$ 时刻下泄流量， $\mathbf { m } ^ { 3 } { \cdot } \mathbf { s } ^ { - 1 }$ 。

(2）库容约束：

$$
V _ { \operatorname* { m i n } , t } \leqslant V _ { t } \leqslant V _ { \operatorname* { m a x } , t }
$$

式中： $V _ { \mathrm { m i n } , t }$ 为 $\mathbf { \Phi } _ { t }$ 时刻允许的最小库容， $1 0 ^ { 4 } \mathrm m ^ { 3 }$ $V _ { \mathrm { m a x } , t }$ 为 $\mathbf { \Phi } _ { t }$ 时刻水库允许的最大库容， $1 0 ^ { 4 } \mathrm m ^ { 3 }$ 。

（3）水位约束：

$$
Z _ { \mathrm { m i n } , t } \leqslant Z _ { t } \leqslant Z _ { \mathrm { m a x } , t }
$$

式中： $Z _ { \mathrm { m i n } , t }$ 为 $\mathbf { \Phi } _ { t }$ 时刻水库允许的最低水位， $\mathrm { m } ; Z _ { \mathrm { m a x } , t }$ 为 $\mathbf { \chi } _ { t }$ 时刻水库允许的最高水位， $\mathrm { m }$ 。

(4）泄流能力约束：

$$
q _ { t } \leqslant q _ { \mathrm { m a x } , t }
$$

式中： $q _ { \operatorname* { m a x } , t }$ 为 $\mathbf { \Phi } _ { t }$ 时刻水库允许的最大下泄流量， $\mathbf { m } ^ { 3 } { \cdot } \mathbf { s } ^ { - 1 }$ 。（5）下泄生态总水量约束：

$$
\frac { 1 } { N T } \underset { i = 1 } { \overset { N } { \sum } } \underset { j = 1 } { \overset { T } { \sum } } ( q _ { i , j } \Delta t ) \geqslant W _ { e }
$$

式中 $\cdot j$ 为调度期内某月份; $T$ 为一年内总月份； $q _ { i , j }$ 为调度期内第 $i$ 年第 $\cdot j$ 月下泄生态流量， $\mathbf { m } ^ { 3 } \cdot \mathbf { s } ^ { - 1 } \colon W _ { e }$ 为允许的最小多年平均下泄生态总水量， $\mathbf { m } ^ { 3 }$ 。

(6)河道内生态基流约束：

$$
\frac { 1 } { N } \sum _ { i = 1 } ^ { N } P _ { i } \hat > P
$$

式中： $P _ { i }$ 为调度期内第 $i$ 年的河道内生态基流保证率， $\% { ; } P$ 为允许的最小河道内生态基流保证率， $\%$ O

(7)入台特玛湖水量约束：

$$
\frac { 1 } { N T } { \sum _ { i = 1 } ^ { N } } { \sum _ { j = 1 } ^ { T } } { \left( { q ^ { \prime } } _ { i , j } \Delta t \right) } \geqslant { W _ { l } }
$$

式中： $q ^ { \prime } { } _ { i , j }$ 为调度期内第 $i$ 年第 $j$ 月入台特玛湖流量，$\mathbf { m } ^ { 3 } \cdot \mathbf { s } ^ { - 1 }$ $\textstyle \boldsymbol { W _ { l } }$ 为允许的最小多年平均入台特玛湖水量，$\mathbf { m } ^ { 3 }$ 0

（8）初始条件约束：

$$
\ b { Z } _ { 1 } = \ b { Z } ^ { 0 }
$$

式中： $\boldsymbol { Z } ^ { \mathrm { 0 } }$ 为调度期初始库水位， $\mathrm { m }$ ○

(9)非负变量

各变量必须为非负值。

# 2.3模型求解

本文研究的河道外最大生态水量问题为单目标优化问题，采取收敛速度快且技术成熟的粒子群算法进行求解。粒子群优化算法(ParticleSwarmOptimization，PSO)的基本思想是将群体中的鸟抽象为没有质量和体积的“粒子”，通过这些“粒子"间的相互协作和信息共享，使其运动速度受到自身和群体的历史运动状态信息的影响。对粒子群优化算法的数学描述如下：

设在 $n$ 维解搜索空间中，有 $\mathbf { \nabla } _ { m }$ 个粒子组成一个粒子群，第 $k$ 次迭代的 $m$ 个粒子在解空间中的位置表示为式(11）、飞翔的速度表示为式(12)：

$$
X _ { i } ^ { k } = ( X _ { i 1 } ^ { k } , X _ { i 2 } ^ { k } , \cdots , X _ { i n } ^ { k } ) ^ { T } , i = 1 , \cdots , m
$$

$$
V _ { i } ^ { k } = ( V _ { i 1 } ^ { k } , V _ { i 2 } ^ { k } , \cdots , V _ { i n } ^ { k } ) ^ { T } , i = 1 , \cdots , m
$$

每个粒子至第 $k$ 次迭代之前的历代搜索过程中，迄今为止自身搜索到的个体最优解表示为式(13):

$$
X p _ { i } ^ { k } = ( X p _ { i 1 } ^ { k } , X p _ { i 2 } ^ { k } , \cdots , X p _ { i n } ^ { k } ) ^ { T } , i = 1 , \cdots , m
$$

整个粒子群至第 $k$ 次迭代之前的历代搜索过程中，迄今为止搜索找到的整体最优解(这里的整体是针对 $m$ 个粒子而言，而不是针对解空间而言)表示为式(14)：

$$
X g ^ { k } = ( X g _ { 1 } ^ { k } , X g _ { 2 } ^ { k } , \cdots , X g _ { n } ^ { k } ) ^ { T }
$$

粒子群优化算法采用式(15)和式(16)对第 $i$ 个粒子进行速度更新和位置更新：

$$
V _ { i j } ^ { k + 1 } = W \cdot V _ { i j } ^ { k } + c _ { 1 } \bullet r _ { 1 } \bullet ( X p _ { i j } ^ { k } - X _ { i j } ^ { k } ) +
$$

$$
c _ { 2 } { \bullet r _ { 2 } } { \bullet ( X g _ { i j } ^ { k } - X _ { i j } ^ { k } ) } , j = 1 , \cdots , n
$$

$$
X _ { i j } ^ { k + 1 } = X _ { i j } ^ { k } + V _ { i j } ^ { k + 1 } , j = 1 , \cdots , n
$$

式中： $W$ 为惯性权重系数； $r _ { 1 } , r _ { 2 }$ 为 $( 0 , 1 )$ 上均匀分布的随机数； $c _ { 1 } \setminus c _ { 2 }$ 为学习因子。

调度期为2000—2020年，以大西海子水库下泄流量为决策变量，共240个计算时段(月尺度)，设置粒子维数为240，故粒子位置和速度维数都是240，粒子位置对应每一时刻水库下泄流量，粒子速度对应迭代一次后同一时段水库下泄流量的变化量。参数设置：粒子种群规模为100，最大迭代次数为150次，惯性权重W为1.05,个体和种群学习因子都为2.0。

# 3结果与分析

# 3.1水库下泄生态总水量分析

采用本文建立的大西海子水库优化调度下泄水量过程如图3所示。基于式(1)对径流资料进行处理后，大西海子断面的多年平均来水量为 $5 . 2 5 \times$ $1 0 ^ { 8 } \mathrm m ^ { 3 }$ ,经优化调度后，多年平均下泄水量为 $5 . 2 3 \times$ $1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，二者之间满足水量平衡，验证了中长期水库调度方案的可行性和可靠性。

![](images/8ad2d041435139853062d736acfd38b9dabf598ee16b5fa20e7d5992717d6318.jpg)  
图3大西海子水库多年月平均水量变化过程 Fig.3Variation process of monthly average water amountin Daxihaizi Reservoir

下泄水量实测与优化过程如图4所示，在选取的2015—2016年和2016—2017年中，实测水库下泄水量分别为 $4 . 6 1 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } . 6 . 7 6 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，有水下泄月份分别占全年的 $3 3 . 3 \% . 2 5 . 0 \%$ ;优化后水库下泄水量分别可达 $6 . 4 9 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 } . 8 . 0 7 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，有水下泄月份占全年的 $4 1 . 7 \% . 5 0 . 0 \%$ 。经中长期优化调度后，大西海子水库多年平均下泄水量为 $5 . 2 3 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，满足下泄 $3 . 5 0 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 目标;在下泄水量时间上，优化结果比实测分别增加了1个月和3个月，这更加有利于下游两河区域的植被生态修复工程，为其奠定坚实的水量基础。

# 3.2入台特玛湖水量分析

就入湖过程来讲，在塔河一期治理过程中，采取多种输水方式控制入湖水量，但入湖过程极不稳定且仍有大量水流人台特玛湖，使水域面积陡增，造成无效蒸发严重。2017年入湖水量达到 $3 . 5 9 \times 1 0 ^ { 8 }$ $\mathbf { m } ^ { 3 }$ ，水域面积达到自2001年以来的最大值513.2$ { \mathrm { k m } } ^ { 2 }$ 。这样极不稳定且陡增陡落的入湖水量对尾闾台特玛湖及周边生态环境并无显著积极影响。经优化调度后，将 $0 . 1 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 水量作为模型约束条件，入台特玛湖水量优化过程如图5所示。多年平均入湖水量为 $0 . 1 8 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ;优化后的最大入湖水量出现在2017—2018年，最大值为 $0 . 5 5 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ;最小入湖水量出现在2009—2010年，最小值为0,造成该现象的原因是塔河各源流来水量变少，下游河道全年基本处于干涸状态;将入湖水量控制在 $0 { \sim } 0 . 5 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ，较实测值变化区间更小，人湖水量更稳定，更加有利于塔河下游河道尤其是台特玛湖生态环境的良性发展。

![](images/a8e0c8b7c2ea07773255f56ef3316846915ea83f07de36fd413e465040328cbc.jpg)  
图4下泄水量实测与优化过程  
Fig.4 Measurement and optimization process of discharge   
图5人台特玛湖水量优化过程  
Fig.5Optimization process of water inflow into Taitema Lake

# 3.3河道内生态基流分析

依据塔河一期综合治理规划，并无下游河道生态基流的相关要求。下泄流量与生态基流量如图6所示，满足该生态基流量的月份占比 $5 0 . 0 \%$ ,生态基流量不为0的月份占比 $1 4 . 6 \%$ ,即优化大西海子水库运行后，下游河道不发生断流的月份高达 $6 4 . 6 \%$ 这将极大促进下游沿河两岸荒漠河岸林植被尤其是胡杨等建群物种的生长，遏止下游生态退化的趋势，也将提高植被群落稳定性。

# 3.4河道外生态供水量分析

面对大量水流入台特玛湖的情况，从塔河下游生态输水高效利用的角度看，并不符合该要求。因此应当对台特玛湖入湖水量加以控制，使水域面积维持到合理区间，结余水量用于两河区域的荒漠河岸林植被恢复。2000—2020年10月水库向河道外供水量如图7所示，2010—2011年出现最大供水量为 $2 . 9 5 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ;除去各源流来水极少，下游无水的2009—2010年，在2000—2001年出现最小供水量为$0 . 2 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,多年平均向两河区域供水 $1 . 6 7 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 。就多年平均值 $1 . 6 7 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 水量而言，可进一步扩大两河区域荒漠河岸林植被的受水面积，促使地下水位的拾升，提高植物多样性和群落稳定性，为该区域胡杨等主要建群物种的生长提供有效保障，生态效益十分显著。

3000 600001/善Y 2500 1500 (a)入额水最月变化数 趋势线 0/ 5000 3000 (b)人湖水量年变化过量1000 2000500 10000 聘 040 80 120 160 200 240 1121304050 2303 0 0 02222222 2 20002 0 00 2 6 00 7 180 0 0 0 23 0 0 0 0 5 二 二 8 0 一2222222222222222 2222月数 时段/年

![](images/f1771899f0dcd0763409a41d0a7b229148569307718d877e8d1a8cc82afc53cd.jpg)  
图6下泄流量与生态基流量  
Fig.6 Down discharge and ecological base discharge   
图7调度期内每年10月水库向河道外供水量 Fig.7During the operation period, the reservoir will supply water to the outside of the river every October

3.5  
3.0  
2.5  
2.0  
1.5  
1.0  
0.5  
0.0 1110 1002000 2001 10 9007 000 6000 10 33 9005 300时段/年

# 4结论

（1）大西海子水库优化后多年平均下泄水量为$5 . 2 3 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,满足塔河一期治理规划中要求的 $3 . 5 0 \times$ $1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ;以2015—2016年、2016—2017年下泄水量实测与优化过程为例，水库调度过程经优化后下游河道流水时间延长，表明塔河下游荒漠河岸林生态恢复工程仍具有一定提升空间。

(2）大西海子水库中长期生态优化调度后的多年平均入湖水量为 $0 . 1 8 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,相较于入湖水量要求，入湖水量增加了 $2 0 . 0 \%$ ,并将入湖水量控制在$0 . 5 5 { \times } 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ 以内。对于巩固台特玛湖已经形成的生态景观、相对稳定的河湖结构，以及保障野生动植物和候鸟的重要栖息地，具有重要的生态保护意义。

（3）优化调度方案的塔河下游河道生态基流保证率为 $5 0 . 0 \%$ ,不断流的保证率可达 $6 4 . 6 \%$ ;多年平均向河道外荒漠河岸林植被生态修复供水量为$1 . 6 7 \times 1 0 ^ { 8 } \mathrm { m } ^ { 3 }$ ,在实现下游河道基本畅通、入湖水量处于合理区间的情况下，可最大限度修复两河区间的荒漠河岸林植被，对于两河区域的荒漠河岸植被林修复与保护、构建地下生态水银行具有重要的现实意义。

（4）由于塔河为内陆河，受人类活动因素影响，下游来水过程极不稳定。本文仅研究了向两河区间的可供最大生态水量，未考虑两河区间荒漠河岸植被林的需水过程，下一步将主要针对关键生态期的需水过程进行实时生态优化调度，让塔河下游有限的生态水资源发挥出最大的生态效益，从而切实巩固下游"绿色走廊"的生态系统安全。

# 参考文献(References):

[1]黄强,赵梦龙,李瑛.水库生态调度研究新进展[J].水力发电学 报,2017,36(3):1-11.[Huang Qiang, Zhao Menglong,Li Ying. Advancements in studies on reservoir ecological operation[J]. Journal of Hydroelectric Engineering,2017,36(3): 1-11.]   
[2] Steinschneider S, Bernstein A,Palmer R,et al. Reservior management optimization for basin-wide ecological restoration in the Connecticut River[J]. Journal of Water Resources Planning and Management,2014,140(9): 401-423.   
[3]Sabo JL,Ruhi A, Holtgrieve G W,et al. Designing river flows to improve food security futures in the Lower Mekong Basin[J]. Science,2017,358:eaao1053.   
[4]Xia Y,Feng Z K,Niu W J, et al. Simplex quantum-behaved particle swarm optimization algorithm with application to ecological operation of cascade hydropower reservoirs[J].Applied Soft Computing,2019,84: 105-115.   
[5]Wang T,Mo L,Shen Q,et al.Multi-objective ecological operation of cascade reservoirs based on MGCL-PSO algorithm[J]. IOP Conference Series Earth and Environmental Science,2O20,612:12- 25.   
[6]Zhong K F, Shuai L, Wen JN,et al. Ecological operation of cascade hydropower reservoirs by elite-guide gravitational search algorithm with Levy flight local search and mutation[J]. Journal of Hydrology,2020,581: 124455.   
[7]邓晓雅,杨志峰,龙爱华.基于流域水资源合理配置的塔里木河 流域生态调度研究[J].冰川冻土,2013,35(6):1600-1609. [Deng Xiaoya, Yang Zhifeng,Long Aihua. Ecological operation in the Tarim River Basin based on rational allocation of water resources[J]. Journal of Glaciology and Geocryology，2013,35(6): 1600-1609.]   
[8]王光焰,王远见,桂东伟.塔里木河流域水资源研究进展[J].干 旱区地理,2018,41(6): 1151-1159.[Wang Guangyan,Wang Yuanjian,Gui Dongwei.A review on water resources research in Tarim River Basin[J].Arid Land Geography,2018,41(6): 1151- 1159.]   
[9]徐俏,叶茂,徐海量,等.塔里木河下游生态输水对植物群落组 成、多样性和稳定性的影响[J].生态学杂志,2018,37(9):2603- 2610.[Xu Qiao,Ye Mao,Xu Hailiang,etal.Effects of ecological water conveyance on the composition,diversity and stability of plant community in the lower reaches of Tarim River[J]. Chinese Journal of Ecology,2018,37(9): 2603-2610.]   
[10] 王希义,彭淑贞,徐海量,等.大型输水工程的生态效益与社会 经济效益评价—以塔里木河下游为例[J].地理科学,2020, 40(2):3O8-314.[Wang Xiyi,Peng Shuzhen,Xu Hailiang,et al. Evaluation of ecological and social-economic benefits of large water conveyance projects:A case study on the lower reaches of the Tarim River[J]. Scientia Geographica Sinica, 2020,40(2): 308- 314.]   
[11]邓铭江,杨鹏年,周海鹰,等.塔里木河下游水量转化特征及其 生态输水策略[J].干旱区研究,2017,34(4):717-726.[Deng Mingjiang, Yang Pengnian, Zhou Haiying, et al.Water conversion and strategy of ecological water conveyance in the lower reaches of the Tarim River[J].Arid Zone Research,2017,34(4): 717-726.]   
[12] Chen Y,Li W, Xu C,et al. Desert riparian vegetation and groundwater in the lower reaches of the Tarim River basin[J]. Environmental Earth Sciences,2014,73(2): 547-558.   
[13]邓铭江.塔里木河下游环境监测与生态修复研究[J].水利规划 与设计,2005(2):31-35.[Deng Mingjiang.Environmental monitoring and ecological restoration in the lower reaches of Tarim River[J].Water Resources Planning and Design,2005(2): 31-35.]   
[14] 李均力,肖昊,沈占锋,等.2013—2018年塔里木河下游植被动 态变化及其对生态输水的响应[J].干旱区研究,2020,37(4): 985-992.[Li Junli, Xiao Hao, Shen Zhanfeng,et al.Vegetation changes during the 2O13-2O18 period and its response to ecological water transport in the lower reaches of the Tarim River[J].Arid Zone Research,2020,37(4): 985-992.]   
[15] 李丽君,张小清,陈长清,等.近20a塔里木河下游输水对生态 环境的影响[J].干旱区地理,2018,41(2):238-247.[Li Lijun, Zhang Xiaoqing, Chen Changqing,et al. Ecological effects of water conveyance on the lower reaches of Tarim River in recent twenty years[J]. Arid Land Geography,2018,41(2): 238-247.]   
[16] 邓铭江,黄强,畅建霞,等.大尺度生态调度研究与实践[J].水利 学报,2020,51(7):757-773.[Deng Mingjiang,Huang Qiang, Chang Jianxia, et al. Large-scale ecological operation research and pratice[J]. Journal of Hydraulic Engineering,2020,51(7):757- 773.]   
[17] 樊自立,徐海量,傅仪,等.台特玛湖湿地保护研究[J].第四纪 研究,2013,33(3): 594-602.[Fan Zili,Xu Hailiang,Fu Jinyi,et al.Study on wetland protection of TaiTeMa Lake[J]. Quaternary Sciences,2013,33(3): 594-602.]   
[18] 邓铭江,周海鹰,徐海量,等.塔里木河下游生态输水与生态调 度研究[J].中国科学:技术科学,2016,46(8):864-876.[Deng Mingjiang, Zhou Haiying,Xu Hailiang,et al. Research on the ecological operation in the lower reaches of Tarim River based on water conveyance[J]. Scientia Sinica(Technologica)，2O16,46(8): 864-876.]   
[19] 魏召才.塔里木河流域大西海子水库年径流分析[J].黑龙江水 利科技,2019,47(7): 37.[Wei Zhaocai.Annual runoff analysis of Daxihaizi reservoir in Tarim River Basin[J]. Heilongjiang Hydraulic Science and Technology,2019,47(7): 37.]   
[20] 王延贵,胡春宏,周文浩,等.塔里木河干流河道的河型及其成 因[J].泥沙研究,2002(6):19-25.[Wang Yangui,Hu Chunhong, Zhou Wenhao,et al. Study on river patterns of the Tarim River[J]. Journal of Sediment Research,2002(6): 19-25.]

# Optimization of reservoir operation for multi-object protection and ecosystem restoration

LIU Zhejie'， BAI Tao²， GAO Fan'， YANG Pengnian'， WANG Guangyan   
(1. College of Hydraulicand Civil Engieering,Xinjiang Agricultural University,Urumqi830o52,Xinjiang,China;   
2.State KeyLaboratory of Eco-Hydraulics in Northwest Arid Regionof China (Xi'an Universityof Technology), Xi'an 710048,Shaanxi, China; 3. Xinjiang Tarim River Basin Authority, Korla 8410o0,Xinjiang, China)

Abstract: Over the past 20 years,the implementation of a comprehensive plan for water resources of the Tarim River basin has resulted in ecological water delivery to Taitema Lakeand Daxihaizi Reservoir of an average 350 million $\mathrm { m } ^ { 3 }$ .However, two areas between the Wenkuer River and Old Tarim River, in the lower reaches of the Tarim River,have sparse vegetation and fragile ecological environments.Ecological restoration eforts over many years have not had a significant effect. In view of this,the study atempted to establish the medium-and long-term ecological optimization of the reservoir. A model was developed based on the Daxihaizi Reservoir as the main water body for regulation,the ecological water discharged from Daxihaizi,the ecological base flow in the river, the ecological water delivery of Taitema Lake,and the ecological water supply outside the river as ecological protection objects. The scheduling model was solved using particle swarm optimization.(1） Under optimal operation conditions,the Daxihaizi Reservoir had an average annual discharge volume of 523 million $\mathrm { m } ^ { 3 }$ ，which meets the 350 million $\mathbf { m } ^ { 3 }$ water requirement of the first phase of the Tarim River,and the downstream river channel had a significantly longer constant flow time.(2)With optimized discharge, the average volume of water entering Taitema Lake was 18 million $\mathrm { m } ^ { 3 }$ ,which is an increase of $20 . 0 \%$ compared with the measured data. The processfor water entering the lake was more stable,which is conducive to consolidating the initially formed lake ecosystem. (3)With optimized discharge,the guaranteed rate of ecological base flow in the lower reaches of the Tarim River was $50 . 0 \%$ ，and the guaranteed rate of continuous flow reached $6 4 . 6 \%$ . The improved ecological flows had an important positive efect on the ecosystem of the lower reaches ofthe Tarim River, which is greatly affected by human activities.(4)After the optimized operation,the average ecological water supply outside the lower reaches of the Tarim River was 167 million $\mathrm { m } ^ { 3 }$ ,laying a foundation for ecological restoration of the forests on the banks of the lower two rivers. These results have important application value for the restoration and protection of desert riparian vegetation in the lower reaches of the Tarim River. Such efforts could help to maintain the ecological health of river courses and tail lakes,and develop ecological groundwater banks.

Keywords: medium-and long-term ecological scheduling；multiple protection objects； ecological water supply outside the river; the amount of water entering the lake; ecological base flow； Tarim River