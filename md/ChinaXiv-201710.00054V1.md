# 热力学碳泵循环构建：以变温吸附碳捕集为例

赵睿恺 邓帅 赵力李双俊 张月 刘博文(中低温热能高效利用教育部重点实验室，天津大学，天津300350)

摘要：制约碳捕集技术实用化的重要瓶颈在于捕集能耗过高，而热力学是能源系统效能分析的有力工具。基于将热力学研究方法应用到碳捕集技术效能分析的思想，本文以变温吸附碳捕集为例，按照“物性-过程-冷热源-循环”顺序，完成热力学碳泵循环(TCPC)的构建，进而考察循环参数对总能耗和第二定律效率的影响。结果显示：循环能耗主要受循环温度、吸附剂和吸附相等影响，吸附相显热大约占循环总能耗的 $2 \%$ ；第二定律效率区间为$1 3 . 9 1 \% - 2 1 . 2 1 \%$ ，具有较高节能潜力；TCPC作为一种基于热力学思想的“量化规尺”，可对碳捕集技术展开效能分析，进而对影响循环总能耗的主要因素进行归纳，并可通过第二定律效率对技术成熟度进行判断，有效挖掘碳捕集技术的节能潜力。

关键词：热力学碳泵；碳捕集；碳泵循环；变温吸附；第二定律效率中图分类号：TK123 文献标识码：A

# Construction of Thermodynamic Carbon Pump Cycle: A Case Study on Temperature Swing Adsorption for $\mathbf { C O } _ { 2 }$ Capture

ZHAO Rui—Kai DENG Shuai ZHAO Li LI Shuang—Jun ZHANG Yue LIU Bo—Wen (KeyLaboratoryofEfcient UtilizationofLowandMedium Grade Energy,Tianjin UniversityTianjin30o350,China)

Abstract: The main bottleneck of carbon capture technologies is the energy-intensive consumption, while thermodynamics can be considered as an effective tool for energy system analysis.By the ideology of application of thermodynamics into analysis on carbon capture system, the construction of thermodynamic carbonpumpcycle(TCPC）iscompletedbasedontheresearchsequenceof "property-process-source-cycle". The effect of cyclic parameters on the energy efficiency performance of temperature swing adsorption (TSA) is evaluated in terms of the total heat consumption and second-law efficiency.The results show that the heat consumption of TSA depends on the cycle temperature, physical property of adsorbent and adsorbed phase. However, the sensible heat of adsorbed phase accounts for about $2 \%$ of the total heat consumption. The range of the second-law efficiency for TCPCs is from $1 3 . 9 1 \%$ to $2 1 . 2 1 \%$ , and it means that TCPCs have high energy saving potentials. As a quantitative rule of thermodynamics， TCPC can address the energy-efficiency analysison $\mathrm { C O } _ { 2 }$ capture technologies. Furthermore,according to the judgment of technical maturity based on the second-law eficiencies, the cyclic factors on energy consumption can be summarized and the energy-saving potentialities of $\mathrm { C O } _ { 2 }$ capture technologies can also be exploited.

Key words: thermodynamic carbon pump; carbon capture； carbon pump cycle; temperature swing adsorption; second-law efficiency

# 0引言

气候变化问题逐渐成为全球关注的焦点之一，而主要负面贡献就是二氧化碳的温室效应。众多缓解气候变化技术中，碳捕集与封存技术被认为是一种积极有效的技术举措[1]。目前碳捕集技术的主要瓶颈在于捕集能耗过高，以吸收法捕集技术为例，再沸器捕集耗热量大约是 $3 \mathrm { - } 4 \mathrm { G J } ^ { [ 2 ] }$ ；另一方面，现有碳捕集技术的种类繁多，有吸收法/吸附法、膜分离法和生物法等。

目前，在碳捕集能效分析方面，有针对性的工具或模型研究仍处于探索阶段。学界主要存在四类模型：(1)气体分离模型，麻省理工学院的House 等[3]利用该模型，考察了浓缩比与分离二次效率的经验关系。缅因大学的Ruthven[4利用分离模型提出了值函数模型并评价分离过程的成本。气体分离模型是一种集总模型，普适性较好，但是过于简化。(2)过程分析模型,如Sanpasertparnich等[5]利用ASPEN软件模拟一座800MW燃煤电厂的吸收碳捕集分离过程。Moullec[则是从燃烧后、燃烧前和富氧燃烧的角度分析了碳捕集技术能耗对燃煤电厂的热力学限制。此类模型的特色是对案例的针对性强，缺点是普适性差，“一事一议”，缺乏共性规律把握。(3)全生命周期(LCA)或能值(emergy)分析模型，此类模型源自对产品大时间尺度下的环境排放分析，对过程中的能质转化特征细节把握不足。(4)碳泵模型，Zhao 等人[基于热力学观点，提出热力学碳泵这一概念，并对其基础理论进行了初步介绍，并以5种碳捕集技术为案例进行了第二定律的性能比较分析，归纳了代表性技术的成熟度。

相对吸收碳捕集技术的高能耗问题，吸附碳捕集技术具有自身技术优势，比如再生耗热量低、热能品位要求低、单位捕捉能力大和系统所需设备少等优点。根据脱附过程吸附量变化方式的不同，吸附碳捕集技术被分成变温吸附和变压吸附两种方式。近些年来，众多学者在二氧化碳吸附材料[8-10]和吸附过程[,12]领域进行了研究。Ben-Mansour 等人[13]从吸附材料、数值模拟和实验总结了二氧化碳物理吸附的相关研究，并指出吸附碳捕集技术应关注吸附技术的第一定律和第二定律的热力学分析。

综上可以看出，碳捕集的效能分析的模型有待具化至循环层面以深入分析，并且从事吸附碳捕集技术的研究人员已经意识到热力学研究的重要性，这两方面的交汇迫使我们深入思考一个问题：如何以吸附碳捕集为例展开热力学碳泵循环的构建工作。有鉴于此，本文针对一种简单的四步间接换热的变温吸附碳捕集技术，在吸附平衡线图中进行详细的循环构建，并基于热力学碳泵基础理论分析了脱附温度、脱附分压、床层未利用率和吸附分压四种因素对循环的总能耗和第二定律分离效率的影响。

# 1循环构建

# 1.1 方法论

热力学是物理学的一个重要分支，主要考察热功转换关系，近年来分析对象向广义能源系统展开。热力学具有成熟、自恰的理论体系(诸热力学定律)和精确有力的分析工具(火用、熵等)。当考察碳捕集过程中的效能问题时，仍是基于如图1所示的经典研究框架展开分析，以吸附碳捕集技术为例，热力学碳泵(TCP)循环构建的基础是物性，主要有吸附材料和气体吸附相等物性。其后，在吸附等温平衡线和比热等物性数据基础上，设计合理的热力过程，并配合冷热源进行“定位”。然后，串接多个过程构建成循环。其中，典型热力过程有吸热和放热、吸附和脱附过程，而典型热源有太阳能中低温热源和电厂抽汽等。最终，循环的构建服务于核心目标一一能效分析，这与热机、热泵等热力学经典概念提出时的诉求是一致的，即考察过程或循环的效率。

![](images/17cf43605446a95242940473965004b9de4c831579d1841132a7a2ed78778411.jpg)  
图1热力学碳泵循环构建方法论  
Fig.1Methodology diagramofTCPcycle construction

# 1.2物性

本文变温吸附碳捕集技术采用的吸附剂是一种胺基化学改性吸附材料，其吸附等温线来自Wurzbacher 等人的实验数据[14]。采用 Toth 模型对二氧化碳吸附量 $q$ 的实验数据进行拟合，详细公式如下所示：

$$
q ~ = ~ { \frac { N B P _ { C O 2 } } { \left( \left( I ~ + ~ B P _ { C O 2 } \right) ^ { t } \right) ^ { \frac { I } { t } } } }
$$

$$
N = n _ { o } \mathbf { e } ^ { \displaystyle A \left( I - { \frac { T _ { o } } { T } } \right) }
$$

$$
B \ = \ B _ { o } { \tt e } ^ { \frac { H } { R T _ { o } } \left( \frac { T _ { o } } { T } - I \right) }
$$

$$
t = t _ { o } + D \Bigg ( I - \frac { T _ { o } } { T } \Bigg )
$$

其中， $P _ { C O 2 }$ 是吸附过程二氧化碳的分压力， $T$ 是吸附过程的温度， $H$ 是吸附热量， $\mathrm { ~ \cal ~ C ~ } _ { \ }$ 是比热，而$B _ { \theta }$ ， $t _ { 0 }$ ， $D$ ， $n _ { \theta }$ 和 $A$ 为拟合参数。Toth模型的其他拟合参数和吸附剂物性参数总结在表1中。

表1吸附剂物性参数和模型参数  
Table1ParametersofToth model andadsorbent   

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>To/K</td><td>296</td></tr><tr><td>B0/1/kPa</td><td>2.25</td></tr><tr><td>H /kJ/mol</td><td>60</td></tr><tr><td>t0</td><td>0.422</td></tr><tr><td>D</td><td>0.949</td></tr><tr><td>no / mol/kg</td><td>1.97</td></tr><tr><td>A</td><td>2.37</td></tr><tr><td>Cad / kJ/kgK</td><td>2.07</td></tr><tr><td>Cco2 / kJ/kgK</td><td>0.86</td></tr></table></body></html>

# 1.3过程

本文的研究对象为四步间接换热的变温吸附碳捕集技术，四步过程如图2所示。四步过程分别是吸附(AD)、预热(PH)、脱附(DE)和预冷(PC)。电厂待处理的烟气主要由氮气和二氧化碳组成，在吸附过程中低温的烟气通入吸附腔体，烟气中的二氧化碳被吸附；预热过程中，吸附床层被高温热源加热；脱附过程，吸附床中的二氧化碳在高温条件下释放出来；预冷过程，吸附床被低温冷源冷却到环境温度。通过一系列吸附和再生过程的串联，最终实现烟气中二氧化碳气体的分离。

![](images/4f4b16bf2ee1b9c5234ebb69321cd06ec13bc73e596fb880c2e59b8d1a71aeb5.jpg)  
图2四步间接换热的变温吸附碳捕集过程示意图 Fig.2Process schematic for the indirect 4-step TSAcycle

# 1.4 冷热源

吸附等温平衡线决定了吸附碳捕集吸附和脱附能力的上下限，但同时也受到外界冷热源温度的制约。其中，预热和预冷采用间接换热方式实现吸附床的温度变化。如图3所示。由于脱附的能耗较高，高温热源可用太阳能中低温热源代替燃煤电厂汽轮机抽汽，则温度被限制为343K；吸附过程的温度为常温，如图3中吸附等温平衡线温度为296K。

![](images/bf6dad4fdb55253faa54371bf4672bc89310df6bfc5e7e455ecc5560b27cd48e.jpg)  
图3在吸附等温线图中循环各步图示 Fig.3 Demonstration of 4-step processes in the adsorption isotherm diagram

# 1.5 循环

与图3所示的状态点一一对应，图4为热力学参数坐标系下的热力学碳泵循环图，为了便于显示，参考吸附制冷、吸附蓄能的习惯性表达，采用对数坐标表示。该循环的构建首先需要满足以下假设：

(1)循环各步骤中吸附剂材料内部的温度被认为是均匀一致;

(2)烟气中的氮气吸附量被忽略，且二氧化碳的吸附相的比热按照气体二氧化碳的比热计算；

(3)吸附材料和吸附腔体内的二氧化碳浓度在各循环中被认为达到平衡；包括吸附腔体的几何尺寸、吸附过程的压降和烟气在腔体内流速等因素被忽略。

图2给出了具体的间接换热的变温吸附碳捕集各过程。图3展现了在吸附等温平衡线上下限中变温吸附技术的4个步骤。图4是在热力学参数对数坐标下的显示情况，循环的具体四步过程的详细介绍如下：

(1)吸附过程1-2：如图4中循环起始点为点1,电厂烟气在总压力0.1MPa、二氧化碳体积分数为$10 \%$ 和温度296K的情况下通入吸附腔，腔内的吸附材料选择性的吸附二氧化碳气体，并使得富含氮气的气体从腔体另一侧流出，该过程被假设瞬间完成。此外吸附过程在恒定温度下完成，吸附过程释放的吸附热被冷却水带走。如图3所示，循环在温度为296K和343K之间完成，理论上循环捕集二氧化碳的工作容量为点5和点1之间吸附量差值。但是由于床层利用差异性，实际循环在等温条件下未必能达到平衡的饱和吸附量(饱和点在点5，实际吸附过程的终点假设在点2)。该过程的工作容量WC和床层未利用率 $\eta _ { u n u s e d }$ 的定义如下所示：

$$
W C _ { i d } \ = \ q _ { s t a , 5 } \ - \ q _ { m i n , I }
$$

$$
W C _ { a c } \ = \ q _ { m a x , 2 } \ - \ q _ { m i n , I }
$$

$$
\eta _ { _ { u n u s e d } } \ = \ I - \frac { q _ { { m a x , 2 } } } { q _ { { s t a , 5 } } }
$$

![](images/812b7fe4c2a309a2217a466b6e06922926525f8fd2e282ac0d0fe2e2e5a56f45.jpg)  
图4基于Clapeyron 图示的 TCP 循环Fig.4 TCP Cycle in the Clapeyron diagram

(2)预热过程2-3：在吸附床内换热管道通入蒸汽加热吸附床层，同时加入氮气吹扫床层，此时床层内的二氧化碳分压逐渐从 $P _ { C O 2 }$ ， $_ { a d } ($ 点 2)上升到$P _ { C O 2 }$ $d e$ (点3)。在预热过程中，该分压下的吸附量随着温度升高而下降。当温度升高到 $T _ { 3 }$ 时，此时吸附床的实际吸附量等于相应温度的平衡吸附量。这意味着该阶段吸附床的实际吸附量没有发生变化。

(3)脱附过程3-4：当吸附床层温度继续升高(大于 $T _ { 3 }$ )，实际吸附量逐渐大于对应温度下的平衡吸附量，被吸附的二氧化碳开始从吸附床中释放出来，实现了二氧化碳的分离。受高温热源的限制，脱附过程到达最高温度 $T _ { 4 }$ 。此脱附过程依然进行吹扫，并且脱附分压保持不变。

(4)预冷过程4-1：当吸附床层温度达到高温

$T _ { 4 } ( 3 4 3 \mathrm { K } )$ 后，吸附床的产品气管路关闭。冷却水进入换热管路，吸附床温度开始下降，逐渐降低到环境温度 $T _ { I } ( 2 9 6 \mathrm { K } )$ 。此过程没有发生二氧化碳的吸附和脱附，即床层的实际吸附量保持不变。循环从点4回到最初开始的点1，新的循环可以重新开始。

# 2热力学碳泵评价参数

一般来说，二氧化碳分离性能的评价指标是二氧化碳回收率 $R _ { C O 2 }$ 和回收气体中二氧化碳纯度。由于本文不考虑氮气的吸附量，因此二氧化碳纯度不作为本文评价指标。在本文中吸附过程的烟气进气量按照理想工作容量 $W C _ { i d }$ 进行设计，则实际过程回收率只与床层未利用率有关，其定义如下所示：

$$
R _ { _ { C O 2 } } = \frac { W C _ { _ { a c } } } { W C _ { _ { i d } } } = \frac { q _ { s t a , 5 } - q _ { m i n , l } } { q _ { m a x , 2 } - q _ { m i n , l } }
$$

Zhao 等人[7详细介绍了热力学碳泵基础理论，其中最小分离功 $W _ { m i n }$ 是理想气体混合物在等温等压条件下无化学反应的用于可逆分离过程的功耗，其物理意义是混合气体实现指定分离的难易程度。最小分离功与分离过程的路径无关，只与分离过程的初末状态有关，即在碳捕集过程中的最小分离功只与三个过程参数有关，分别是分离温度，初始二氧化碳浓度和分离过程回收率。此外，第二定律分离效率 $\eta _ { 2 n d }$ 是理想过程最小分离功与实际过程的系统输入有效能的净量之间的比值。因此，最小分离功和第二定律分离效率的公式如下所示：

$$
W _ { m i n } \ = \ G \left( T _ { \scriptscriptstyle I } , y _ { \scriptscriptstyle C O 2 } , R _ { \scriptscriptstyle C O 2 } \right)
$$

$$
\eta _ { _ { 2 n d } } \ = \frac { W _ { _ { m i n } } } { W _ { _ { S } } \ + Q _ { H } \left( l \ - \displaystyle \frac { T _ { o } } { T _ { H } } \right) - Q _ { L } \left( l \ - \displaystyle \frac { T _ { o } } { T _ { L } } \right) }
$$

在本文四步间接变温吸附碳捕集的评价中，主要耗能是分离过程的总热耗。因此，用于输送气体的风机和泵等功耗被忽略；此外冷却水的温度按环境温度计，忽略冷热源与吸附床的温差。所以四步间接换热的变温吸附碳捕集过程的总能耗 $Q _ { H }$ 包括吸附相显热、吸附剂显热和吸附潜热，其公式按如下计算：

$$
{ \cal Q } _ { H } \ = \ { \cal Q } _ { s , c o 2 } \ + \ { \cal Q } _ { s , a d } \ + \ { \cal Q } _ { L }
$$

# 3结果与讨论

本文利用热力学碳泵基础理论，分析了脱附温度、脱附分压、床层未利用率和吸附分压四种因素对间接换热变温吸附碳捕集技术的分离能耗和第二定律分离效率的影响。

# 3.1 脱附温度

脱附温度对于变温吸附碳捕集技术的分离效果具有重要影响。一般来说，当脱附温度升高，二氧化碳的吸附量随之下降。如图4的循环描述，本小节分析了四种不同脱附温度的TCP循环，脱附温度分别是343K、348K、353K和358K。循环的其余状态参数则是相同的，吸附温度为296K，吸附二氧化碳分压为 $1 0 \mathrm { { k P a } }$ ，脱附二氧化碳分压为 $4 0 \mathrm { { k P a } }$ 和床层未利用率为 $5 \%$ 。

图5给出了TCPC在四种不同脱附温度情况下的总能耗和第二定律分离效率的变化趋势。当脱附温度从343K上升到358K时，循环的理想和实际的工作容量都在增加，因此循环的碳回收率相应的增加，从 $8 3 . 4 8 \%$ 上升到 $8 7 . 3 2 \%$ 。根据最小分离功的计算公式，在分离温度和初始浓度不变的情况下，相应的最小分离功数值分别是 $1 6 2 . 3 9 \mathrm { k J / k g }$ ，163.58$\mathbf { k J } / \mathbf { k g }$ ， $1 6 4 . 5 8 \mathrm { k J / k g }$ 和 $1 6 5 . 4 4 \mathrm { k J / k g }$ 号

![](images/271f16b7feca6fc118c03849188ee8d9e7b30980a54794c15c5046318ba7e45e.jpg)  
图5当脱附温度改变时总能耗和第二定律效率的变化 Fig.5 Characteristics of the total heat consumption and second-law efficiencies when desorption temperature is varied

由于本文将二氧化碳的吸附热平均值作为循环的潜热，故不同脱附温度的循环潜热数值相等，都是 $1 3 6 3 . 6 3 \ \mathrm { k J / k g }$ 。由于实际循环工作容量的增加趋势大于温差带来热量的增长收益，吸附剂和吸附相的显热都呈现减少的趋势。具体来说，吸附剂显热从 $4 8 5 8 . 4 0 \mathrm { \ k J / k g }$ 降低到 $4 7 0 0 . 9 4 ~ \mathrm { k J / k g }$ ，降低了$3 . 3 5 \%$ ；吸附相显热则是从 $1 2 1 . 2 8 ~ \mathrm { { k J / k g } }$ 降低到$1 0 3 . 4 5 \mathrm { k J / k g }$ ，降低了 $1 7 . 3 4 \%$ 。因此循环的总能耗呈现下降趋势，从 $6 3 4 3 . 3 1 \mathrm { k J / k g }$ 降低到 $6 1 6 8 . 0 3 \mathrm { k J / k g }$ 0其中，按气相计算的吸附相显热占总能耗的$1 . 6 8 \% - 1 . 9 1 \%$ 。随着脱附温度的增加，总能耗呈现下降趋势，但是有效能计算的卡诺因子在增加。所以循环的第二定律分离效率按公式计算呈现下降趋势，具体从 $1 8 . 6 8 \%$ 降低到 $1 5 . 4 9 \%$ 。

# 3.2 脱附分压

一般来说，影响脱附过程二氧化碳分压的主要因素是吹扫气(氮气)流量和温度等。如图4的循环描述，本小节分析了四种不同脱附分压的TCP循环，脱附二氧化碳分压依次是 $3 5 \mathrm { { k P a } , 4 0 \mathrm { { k P a } , 4 5 \mathrm { { k P a } } } }$ 和 $5 0 \mathrm { k P a }$ 。循环的其余状态参数则是相同的，吸附温度为296K，吸附二氧化碳分压为 $1 0 \mathrm { { k P a } }$ ，脱附温度为343K和床层未利用率为 $5 \%$ 。

图6给出了在四种不同脱附分压情况下的总能耗和第二定律分离效率的变化趋势。当脱附分压从$3 5 \mathrm { { k P a } }$ 上升到 $5 0 \mathrm { k P a }$ ，循环的理想和实际的工作容量都在减少，因此循环的碳回收率稍微减少，从$8 3 . 6 8 \%$ 降低到 $8 3 . 1 5 \%$ 。根据最小分离功的计算公式，在分离温度和初始浓度不变的情况下，相应的最小分离功数值从 $1 6 2 . 5 5 ~ \mathrm { { ‰ } }$ 降低到162.15kJ/kg。

![](images/3dae233947a27916c490264e2770b10d9c81986a9a5ab499e1a0c101c96acbe1.jpg)  
图6当脱附分压改变时总能耗和第二定律效率的变化 Fig.6 Characteristics of the total heat consumption and second-law efficiencies when $\mathrm { C O } _ { 2 }$ partial pressure for desorption is varied

由于本文将二氧化碳的吸附热平均值作为循环的潜热，故不同脱附温度的循环潜热数值相等，都是 $1 3 6 3 . 6 3 \mathrm { k J / k g }$ 。随着脱附分压的增加， $\mathrm { T } _ { 2 }$ 也在相应增长。故吸附相显热也在增加，具体从118.66$\mathrm { k J / k g }$ 上涨到 $1 2 5 . 4 1 ~ \mathrm { k J / k g }$ 。由于脱附分压增加带来实际循环的工作容量相应减少，所以吸附剂显热呈现增长趋势，具体从 $4 7 8 5 . 7 7 ~ \mathrm { k J / k g }$ 增加到4974$\mathbf { k J } / \mathbf { k g }$ 。其中，按气相计算的吸附相显热占总能耗的$1 . 8 9 \% - 1 . 9 4 \%$ 。随着脱附分压的增加，总能耗呈现上升趋势，但是脱附温度不变，所以分离循环的能耗有效能呈现上升趋势。根据第二定律公式，分离最小功呈现减少趋势，故第二定律分离效率从 $1 8 . 9 3 \%$ 降低到 $1 8 . 8 1 \%$ 。

# 3.3 床层未利用率

实际吸附过程的流速差异、吸附时间不充分和系统内存在死区体积等因素会影响吸附床使用情况。按照图4的循环描述，本小节分析了四种不同床层未利用率的TCP循环，床层未利用率分别是$5 \%$ ， $7 \%$ ， $9 \%$ 和 $1 1 \%$ 。循环的其余状态参数则是相同的，具体为吸附温度是296K，吸附二氧化碳分压为 $1 0 \mathrm { { k P a } }$ ，脱附温度为343K和脱附二氧化碳分压为$4 0 \mathrm { { k P a } }$ 。

图7给出了在四种不同床层未利用率情况下的总能耗和第二定律分离效率的变化趋势。当床层未利用率从 $5 \%$ 上升到 $1 1 \%$ 时，循环的理想工作容量保持不变，而实际工作容量却在下降，因此循环的二氧化碳回收率持续下降。具体的二氧化碳回收率依次是 $8 3 . 4 8 \%$ ， $7 6 . 8 7 \%$ ， $70 . 2 6 \%$ 和 $6 3 . 6 5 \%$ 。根据最小分离功的计算公式，在分离温度和初始浓度不变的情况下，对应的最小分离功数值从 $1 6 2 . 3 9 \mathrm { k J / k g }$ 降低到 $1 5 0 . 5 8 \mathrm { k J / k g }$ 。

![](images/0e3981154a626e696e0a51c44c66cdc6416e722101ca09cf25299ad0a9403322.jpg)  
图7当床层未利用率改变时总能耗和第二定律效率的变化 Fig.7 Characteristics of the total heat consumption and second-law efficiencies when the percentage of unused bed is

varied

由于本文将二氧化碳的吸附热平均值作为循环的潜热，故不同脱附温度的循环潜热数值相等，都是 $1 3 6 3 . 6 3 \mathrm { k J / k g }$ 。随着床层未利用率的增加， $\mathrm { T } _ { 2 }$ 也相应增长，但实际工作容量却下降。因此吸附相显热相应的增加，具体从 $1 2 1 . 2 8 \mathrm { k J / k g }$ 增加到$1 6 2 . 6 5 \mathrm { k J / k g }$ 。由于床层未利用率增加带来实际循环的工作容量持续减少，而循环温差保持不变，所以吸附剂显热呈现增长趋势，具体从 $4 8 5 8 . 4 0 \mathrm { k J / k g }$ 上升到 $6 3 4 1 . 7 9 \mathrm { k J / k g }$ 。其中，按气相计算的吸附相显热占总能耗的 $1 . 9 1 \% - 2 . 0 6 \%$ 。随着床层未利用率的增加，总能耗呈现上升趋势，但是脱附温度不变，所以分离循环的能耗有效能呈现上升趋势。根据第二定律公式，最小分离功呈现减少趋势，故第二定律分离效率从 $1 8 . 6 8 \%$ 降低到 $1 3 . 9 1 \%$ 。

# 3.4 吸附分压

初始烟气压力和烟气二氧化碳浓度会决定吸附过程的二氧化碳分压。按照图4的循环描述，本小节分析了四种不同吸附分压的TCP循环，吸附分压依次是5kPa，10kPa， $1 5 \mathrm { { k P a } }$ 和 $2 0 \mathrm { { k P a } }$ 。本小节初始烟气的压力保持在 $0 . 1 \mathrm { M P a }$ ，二氧化碳体积分数分别是 $5 \%$ ， $10 \%$ ， $1 5 \%$ 和 $20 \%$ ，基本处于燃烧后碳捕集技术处理烟气浓度范围。循环的其余状态参数则是相同的，具体为吸附温度是296K，床层未利用率为$5 \%$ ，脱附温度为343K和脱附二氧化碳分压为$4 0 \mathrm { { k P a } }$ 。

图8给出了在四种不同吸附压力情况下的总能耗和第二定律分离效率的变化趋势。当吸附压力从5kPa上升到 $2 0 \mathrm { { k P a } }$ 时，循环的理想和实际的工作容量都在增加，因此循环的二氧化碳回收率有少量的增长，从 $8 2 . 2 5 \%$ 上升到 $8 4 . 2 8 \%$ 。根据最小分离功的计算公式，在分离温度保持不变、初始浓度和回收率都增长的情况下，最小分离功数值依次是$2 0 1 . 4 6 \mathrm { k J / k g }$ ， $1 6 2 . 3 9 \mathrm { \ k J / k g }$ ， $1 3 8 . 8 3 \mathrm { ~ k J / k g }$ 和121.65$\mathrm { k J / k g }$ 。

由于本文将二氧化碳的吸附热平均值作为循环的潜热，故不同脱附温度的循环潜热数值相等，都是 $1 3 6 3 . 6 3 \mathrm { k J / k g }$ 。随着吸附分压的增加， $\mathbf { T } _ { 2 }$ 却在减小，而循环的实际工作容量保持增长。因此吸附相显热相应的减少，具体从 $1 3 8 . 0 6 \mathrm { k J / k g }$ 减少到$1 1 0 . 2 6 \mathrm { k J / k g }$ 。由于脱附分压增加带来实际循环的工作容量持续增长，而循环温差保持不变，吸附剂显热呈现减小趋势，具体从 $5 4 5 8 . 1 4 \mathrm { k J / k g }$ 减小到$4 4 7 7 . 3 6 \mathrm { k J / k g }$ 。其中，按气相计算的吸附相显热占总能耗的 $1 . 8 5 \% { - 1 . 9 8 \% }$ 。随着吸附分压的增加，总能耗呈现下降趋势，但是脱附温度不变，所以分离循环的能耗有效能呈现下降趋势。根据第二定律公式，分离最小功呈现增长趋势，故第二定律分离效率从

$2 1 . 2 1 \%$ 降低到 $1 4 . 9 2 \%$ 。

![](images/bcf6cf740060b9e5c3203ae5ef9d32e790c11eb7b9ff4fd7c94a602cc709c9e3.jpg)  
图8当吸附分压改变时总能耗和第二定律效率的变化 Fig.8 Characteristics of the total heat consumption and second-law efficiencies when $\mathrm { C O } _ { 2 }$ partial pressure for adsorption is varied

图9给出了不同吸附碳捕集技术的碳泵循环能效分析。其中，变压吸附(PSA)技术和变电吸附(ESA技术的主要能耗是来自外界的功(电)，而变温吸附(TSA)技术的能耗是热耗。由图9中发现：除ESA技术外，现有吸附碳捕集技术的第二定律分离效率在 $10 \%$ 到 $2 5 \%$ 之间，但是能耗量却不同，这是由于能量品位和吸附材料等差异造成的。以TSA为例，本文的改性吸附材料适合较低的脱附温度，故适合与中低温太阳能、余热等结合，具有节能潜力，尽管其热耗量较大、效率与其他研究结果接近。然而，ESA技术使用电耗产生热量来分离二氧化碳，本质属于一种特殊的TSA技术，故能耗总量与TSA技术接近，但是由于品位差异，其效率则远低于其他技术的效率。该图说明，有别于化工等学科的研究方法，通过TCP循环的构建，可以快速、准确勾勒出一类碳捕集技术在能效方面的效率，既可以在单一技术领域内进行纵向比较，也可以像文献[中所得的结论一样，对代表性碳捕集技术进行横向比较。与热机、热泵等前人工作的意义接近，此类工作的贡献，在于充分发挥热力学作为能源系统“量化规尺”的作用，有效指导工程实践，合理量化技术路线图，杜绝技术发展的盲目性，为工业技术的高效发展保驾护航。

![](images/786bf4f1e28f88857ab042095f48436eea503a6043b27c45b58bba4d8ebd5608.jpg)  
图9不同吸附技术的循环能效分析Fig.9Energy-efficiency analysis ofcycles for differentadsorption technologies

# 4结论

本文针对一种四步间接换热的变温吸附碳捕集技术，提出了在吸附等温平衡线图中进行循环构建的方法，并利用热力学碳泵基础理论评价了脱附温度、脱附分压、床层未利用率和吸附分压四种因素对吸附技术的总能耗和第二定律分离效率的影响，得出如下结论：

(1)TCPC作为一种热力学分析手段或工具，可以对碳捕集过程中的能效问题进行准确把握，相对于传统气体分离模型更加具化，相对于过程分析模型更加普适，具有明确的能源系统“量化规尺”特征。

(2)基于经典热力学“物性-过程-冷热源-循环”的渐进研究方法，可以得出：二氧化碳的吸附相按气体物性计算，吸附相的显热量约占循环总能耗的$2 \%$ 。

(3)吸附技术的总能耗主要取决于循环构建、吸附剂物性和吸附相物性；能耗主要是吸附剂显热和脱附潜热，且吸附剂显热大于脱附潜热。

(4)基于TCP循环分析，可以得出：间接换热变温吸附技术采用胺基改性吸附剂实现二氧化碳的分离，利用热力学碳泵基础理论得出其第二定律分离效率在 $1 3 . 9 1 \%$ 到 $2 1 . 2 1 \%$ 之间；当脱附温度、脱附分压、床层未利用率和吸附分压四种因素增加时，第二定律分离效率相应的在减小。

# 参考文献

[1] Zhao L,Zhao R,Deng S,et al. Integrating Solar Organic

Rankine Cycle into a Coal-fired Power Plant with Amine-based Chemical Absorption for $\mathrm { C O } _ { 2 }$ Capture [J]. International Journal of Greenhouse Gas Control, 2014,31: 77-86.   
[2] 赵睿恺，赵力，邓帅．太阳能辅助燃煤电厂碳减排的技 术经济性比较[J]．工程热物理学报，2015，36(12): 2547-2550. ZHAO Ruikai, ZHAO Li, DENG Shuai. Techno-economic Comparison of Solar-assisted Power Plant for Emission Reduction [J]. Journal of Engineering Thermophysics, 2015,36(12): 2547-2550.   
[3] House K Z, Harvey C F, Aziz MJ, et al. The Energy Penalty of Post-combustion $\mathrm { C O } _ { 2 }$ Capture & Storage and Its Implications for Retrofitting the US Installed Base [J]. Energy & Environmental Science,2009,2(2): 193-205.   
[4] Ruthven D M. $\mathrm { C O } _ { 2 }$ Capture: Value Functions, Separative Work and Process Economics [J]. Chemical Engineering Science,2014,114: 128-133.   
[5] Sanpasertparnich T, Idem R, Bolea I, et al. Integration of Post-combustion Capture and Storage Into a Pulverized Coal-fired Power Plant [J]．International Journal of Greenhouse Gas Control, 2010,4(3): 499-510.   
[6]MoullecL Y. Assessmentof Carbon Capture Thermodynamic Limitation on Coal-fired Power Plant Effciency [J]. International Journal of Greenhouse Gas Control,2012, 7: 192-201.   
[7] Zhao R, Deng S,Liu Y, et al. Carbon Pump: Fundamental Theory and Applications[J]. Energy，2017,119: 1131-1143.   
[8] Sjostrom S,Krutka H. Evaluation of Solid Sorbents as a Retrofit Technology for $\mathrm { C O } _ { 2 }$ Capture[J].Fuel,2010, 89(6): 1298-1306.   
[9] Veneman R, Frigka N, Zhao W, et al. Adsorption of $\mathrm { H } _ { 2 } \mathrm { O }$ and $\mathrm { C O } _ { 2 }$ on Supported Amine Sorbents [J]. International journal of greenhouse gas control, 2015,41: 268-275.   
[10] Lee S Y,Park S J.A Review on Solid Adsorbents for Carbon Dioxide Capture [J]．Journal of Industrial and Engineering Chemistry,2015,23: 1-11.   
[11] Zhang W, Liu H, Sun Y, et al. Parametric Study on the Regeneration Heat Requirement of an Amine-based Solid Adsorbent Process for Post-combustion Carbon Capture [J].Applied Energy,2016,168: 394-405.   
[12] Song C， Kansha Y,Fu Q，et al. Reducing Energy Consumption of Advanced PTSA $\mathrm { C O } _ { 2 }$ Capture Process—Experimental and Numerical Study [J]. Journal of the Taiwan Institute of Chemical Engineers,2O16,64: 69-78.   
[13] Ben-Mansour R,Habib MA,Bamidele OE,et al.Carbon Capture by Physical Adsorption:Materials,Experimental Investigations and Numerical Modeling and Simulations-a Review[J].Applied Energy,2016,161: 225-255.   
[14] Wurzbacher JA,Gebald C,Brunner S,et al.Heat and Mass Transfer of Temperature-vacuum Swing Desorption for $\mathrm { C O } _ { 2 }$ Capture from Air [J]. Chemical Engineering Journal,2016,283:1329-1338.