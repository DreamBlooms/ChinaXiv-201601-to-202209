# 一种集成本体和BN的跑道侵入态势评估方法

王洁宁ab，庾睿a,b

(中国民航大学 a.空中交通管理学院,b.天津市空管运行规划与安全技术重点实验室，天津 300300)

摘要：为预测机场场面运行安全态势，提出一种本体和贝叶斯网络（Bayesian network，BN）集成建模方法评估跑道侵入严重度值，并进行最优风险把控措施决策。首先，基于威胁与差错管理（threat and error management，TEM）模型构建跑道侵入态势评估领域本体并完成BN转换；然后，利用融合本体语义信息的BN模型学习历史数据，提出跑道侵入事故征候严重度值评价指标；最后，分析实际案例并进行最优风险把控决策。结果表明，跑道侵入态势评估系统能够有效描述事故征候形成进而演化为跑道侵入事故的动态过程，并为最优风险控制决策提供客观依据。

关键词：跑道侵入；领域本体；模型转换；威胁与差错管理；贝叶斯网络中图分类号：TP391.7 doi:10.3969/j.issn.1001-3695.2018.06.0398

Situation assessment method of runway incursion based on combination of ontology and BN

Wang Jieninga, b, Yu Ruia, b (a.CollegeofAirTraffcManagement,b.TianjinKeyLaboratoryofOperationProgramming&SafetyTechnologyofAirTraffic Management, Civil Aviation University of China, Tianjin 30030o, China)

Abstract: Inorder topredicttheoperationalsecuritysituationofairportsurface,thispaperproposedarunwayincursioneverity assessment method based onan ensemble ofontologyand Bayesiannetwork(BN),to makeoptimal riskcontrol measures.In this way,firstofall,itbuiltedomainontologyfounwayincursionsituatioassessmentontheasisofthethreataderr management model(TEM)andrealized thetransformationofBN.Then,itconstructed theconditionalprobabilitytable forthe BN merge with semantic information embedded inontology bylearning historical data,and putforward theevaluation index forthe severity measurement of runway incursion.Finally,itanalyzeda practicalcaseand made theoptimal riskcontrol measures.Theresults showthatthe runway incursion situation assessment system can efectively describe the formation and dynamic evolution process of symptoms and provide an objective basis for the optimal risk control decision.

Keywords:runway incursion；domain ontology；modeltransformation;threatand eror management(TEM);Bayesian network (BN)

# 0 引言

中国民航相关统计资料显示，近年来民航运输机场各类跑道侵入事故征候的发生，严重影响了场面运行安全。跑道侵入态势感知是机场场面运行安全管理的重要环节，从系统动态上把控场面运行当前的安全水平、预测风险发展趋势。场面运行安全保障部门可依据风险态势评估结果采取应对措施，实现跑道侵入风险把控。

本体和BN集成建模技术在复杂系统风险评估及预测、信息挖掘等领域已有不少成功实践，满足了机场场面运行安全向信息智能化发展的需求。国外，本体和 BN集成建模技术提高了通信系统自动化决策能力[和多媒体资源管理系统故障诊断效率[2]。国内，学者们结合本体和BN，在不确定性信息处理[3]、

Web 服务可靠性评估[4等方面开展了相关研究。采用BN研究跑道侵入问题已是成熟范式，罗军等人[5基于高斯BN构建跑道侵入因果联系图，挖掘隐含在事故表层现象中的潜在致因；Goodheart等人l发挥BN概率推理机制，纳入人因、技术和组织方面的信息对于跑道侵入进行系统化研究；但缺乏语义关联的BN还不能充分进行不确定语义关系的定量化描述，难以深入挖掘风险评估知识。基于本体的智能诊断技术在场面安全风险评估方面已有前期研究[78]，在此基础上融合本体语义和 BN概率推理，将本体作为BN模型结构数据库，可以推演跑道侵入威胁与差错风险演化机理，为防正跑道侵入提供科学依据。

鉴于此，本文提出本体和BN集成建模方法，通过分析TEM模型[9]，明确跑道侵入事故严重度、人的工作行为动态表现以及场面运行环境变化之间的内在逻辑关系，构建领域本体模型并转换为BN，通过案例学习获取跑道侵入态势评估信息，对比分析跑道侵入风险态势变化，进行最优风险把控措施决策。

# 1 系统架构

机场场面运行过程中，跑道侵入发生与管制员、飞行员、地面车辆驾驶员的工作行为表现、场面运行环境变化等不确定性特征信息有关。本文提出构建跑道侵入态势评估系统，系统架构参见图1。主要划分为知识应用层和语义描述逻辑控制层，分别对应从领域本体创建到BN推理的概率信息加工环节，涵盖知识集成、模型转换、模型参数调整等过程。将领域知识形式化定义，抽取本体概念及关系转换为BN，通过BN学习跑道侵入实际案例数据得出跑道侵入威胁、差错及严重度的客观概率，开展风险态势评估和制定最优决策。

![](images/4cc009a8bb5f7b8993de5e2c6329664dfca1b9afd5f27517d49e8d8dd63d5b7f.jpg)  
图1跑道侵入态势评估系统架构  
图2跑道侵入威胁与差错本体的核心类和实例

# 2 本体建模及BN转换

# 2.1本体模型

威胁与差错管理模型（TEM）有助于从运行角度理解在动态变化的运行环境中安全态势以及人的表现。领域本体是指特定领域概念及概念间关系、属性的集合。本文通过TEM模型建立参照术语集，结合中国民航空管防止跑道侵入指导材料[10]以及国内场面运行安全现状，使用OWL2DL语言并参照自上而下法，在本体编辑平台Protége4.2构建领域本体。跑道侵入威胁与差错领域本体包含38个类，51条关系（42则对象关系，9则数据关系)，30个实例。跑道侵入威胁与差错本体模型核心概念及关系如图2所示。

严重度（RI_severity）类包含四个实例，其中实例LevelA严重度等级最高，实例LeveIB严重度次之，其余实例按顺序表示严重度依次减小。严重度是跑道侵入态势评估的重要指标，中国民航对跑道侵入事故严重度划分与国际民航组织(ICAO)一致，按A、B、C、D、E五个等级进行设置，但E类事故由于信息不足或证据矛盾一般不予考虑。

Class Subclass Instance IOsS Absent RI_S:Attribute ErrorAttribute instanceOf Dat:hasAttribute + Present 00::tt SeverityAttribute instanceOf ↓ RI_S:RI_Severity Dat:hasSeverityAttribute LevelA、B、C、D -Obj:hasError Obj:hasError isComponentOf ET:Operationnal Dat:hasErrprAttribute subClassOf ET:Primary Error (ErrorType) HumanError   
Obj:hasCollisionScenarios RIL_S:ErrorCasS (ErrorFactors) EF:FlightCrewIssues EFs EF:SurfaceIssues lialrriagrsgn connssoeenetrctss VI Dat:instanceOf EvasiveAction   
RI_S:CollisionScenarios ReactionTime Dat:instanceOf ProximityDistance Obj:hasErrorFactors_] Weather JO2om Obj:hasEncounter EncounterGeometry Arrival Geometry

导致跑道侵入发生的差错类（error）可划分为差错类型类（ErrorType，ET）和差错致因类（ErrorFactors，EF）。其中，ET类包括主要人为差错类（PrimaryHumanError，PHE）和运行差错类（OperationalError，OE）。PHE类包含空管威胁类（ATCIssues）、机组威胁类（FlightCrewIssues）和地面车辆驾驶员威胁类（DriverIssues），OE类的子类由双向沟通类（TwoPartyCommIssues）和机场道面类（SurfaceIssues）组成。

冲突场景类（CollisionScenarios）描述跑道侵入发生时航空器与航空器、地面车辆之间的冲突场景，属性类（attribute）用于设定RI_severity类和error类的子类数据属性。

# 2.2本体 BN 转换

本体从结构上概括为 $o$ ： $\mathit { \Omega } ^ { \prime } C \setminus R \setminus A \setminus T \setminus I )$ ，依次表示领域概念、概念间的关系集合、类的特征、类的特征集和实例。BN是一个有向无环图，可表示为 $B { = } { < } { < } V , E { > } { , } P { > }$ ，其中$V { = } \{ V _ { 1 } , V _ { 2 } , \cdots , V _ { \mathrm { n } } \}$ 为变量集合； $E$ 为有向边集合； $P$ 表示节点的条件概率表的集合。本体转换为BN主要包含以下内容转换：

a)本体中某个类Ci对应转换为BN中的节点 $\mathrm { \Delta V i }$ 0

b)若本体中Ci类和 $\mathrm { C i } { + } 1$ 类存在关系（对象属性）Rj，则BN 中联系节点Vi和节点 $\mathrm { V i } { + } 1$ 的有向边Ej即为Rj的转换对应项。

c)本体Ci类的特征（数据属性）ACi控制BN节点Vi的数据类型，Ci类包含的实例ICi转换成节点Vi状态变量。

跑道侵入场景中天气、冲突位置等均为外界不可抗力因素，因此本文不考虑冲突场景类的转换。抽取上述本体的结构化语义要素，使用模型转换控制单元FaCT $^ { + + }$ 推理机验证抽取模型的语义一致性。若该模型符合语义要求，则通过BNTab1.1.3插件及Netica_J4.18转换成BN模型；否则，需完善语义重新进行模型转换。图3为模型转换插件工作界面。生成跑道侵入态势评估BN的部分预编译代码如下：

RI_Severity;Type I Class;Single Class;SeverityAttriute; hasSeverityAttribute;

OperationalError;Type I Class;Single Class; ErrorAttributes;hasErrorAttribute;

PrimaryHumanError;Type I Class;Single Class; ErrorAttributes；hasErrorAttribute; hasOperationalError;Type I Property;false;false; hasPrimaryHumanError;Type I Property;false;false。

RI_Severity类转换为BN节点，数据属性hasSeverityAttriute与SeverityAttriute类转换为BN节点状态空间，对象属性hasOperationalError 和hasPrimaryHumanError 转换为BN 有向边。

BNiew 8NB Step tnteNeicaLiceseey D Step4Seecs SectedEetle Typet R_Sereety Step 2a:SectTyp Cas? γ-hasError 对象属性→BN Typet OperatonaEeror γ-hasErrorFactors ATChassurfacefa节点有向边 三 Tye tPrinaryHumenEeror 跑道侵入后果预测 BN节点集 0 模型转化内容 naSUTFIIgntCrewFactors hasDriverFacters hasDTSurfaceFactors BN节点数据 hasFlightCrewFactors Renove SectedErt 类型 ss D H 一 4 N有向边重 三 BN节点 川 有向 □ H hasSeverityAttribute □ Tyge CtassSinge Claes □ Remove SelectedProperfe Type IProperty Surarize NodesReverse Link Load ProjetFfle AdClaes AdProperty 5.GenerateBayesianletwork

# 2.3 跑道侵入态势评估BN

# 2.3.1BN节点分析

BN 中主要节点属性包括后果、差错和威胁。表1为各节点变量赋值及详细划分。其中，子节点RI_severity包含 $\scriptstyle \mathbf { A } \sim \mathbf { D }$ 级四种状态空间，父节点PrimaryHumanError和OperationalError均为布尔型节点，三者之间因果机制独立且具有明显的多态系统特征[11]。

表1BN节点属性及状态空间  

<html><body><table><tr><td>变量名称</td><td>属性</td><td>状态空间</td></tr><tr><td>RI_Severity</td><td>后果</td><td>LevelA（A级)；LevelB（B级）</td></tr><tr><td>(严重度） OperationalError</td><td></td><td>LevelC（C级)；LevelD（D级）</td></tr><tr><td>（运行）</td><td>差错</td><td>Absent（无）；Present（有）</td></tr><tr><td rowspan="3">FlightCrewIssues （机组）</td><td rowspan="3">威胁</td><td>CrewLostSA（机组丧失情景意识）</td></tr><tr><td>FlightCrewNormal（机组表现正常）</td></tr><tr><td>ViolateClearence（机组违背空管指令）</td></tr><tr><td rowspan="4">SurfaceIssues (机场道面)</td><td rowspan="4">威胁</td><td>Layout（机场布局);</td></tr><tr><td>SurfaceNormal（道面正常）</td></tr><tr><td>LightingAndSigns</td></tr><tr><td>(机场灯光及标识不清)</td></tr><tr><td rowspan="4">TwoPartyCommIssues (双向沟通)</td><td></td><td>CommContentIssues（通信内容问题）</td></tr><tr><td rowspan="3">威胁</td><td></td></tr><tr><td>CommHardwareIssues（通信设备问题）</td></tr><tr><td>TwoPartyCommNormal（双向正常沟通）</td></tr></table></body></html>

# 2.3.2BN模型改进

Noisy-Or模型是一种典型的因果机制独立模型，但节点类型必须为布尔型变量，导致适用性受限。Noisy-MAX模型扩展了Noisy-Or模型变量的状态空间，为构建处理复杂多态系统问题的BN 模型提供了一种新的解决方案[12]。对于Noisy-MAX 模型，子节点集 $Y$ 的第 $i$ 种可能性值 $Z _ { i }$ ， $P a ( Y ) { = } \{ X _ { I } , . . . , X _ { n } \}$ 表示子节点Y的父节点（致因）集。 $c _ { z _ { i } } ^ { x _ { i } }$ 表示父节点 $X _ { i }$ 取值 $x _ { i }$ 时子节点 $Y { = } Z _ { i }$ 的概率，还可表示为

$$
c _ { z _ { i } } ^ { x _ { i } } = c _ { y } ^ { x _ { i } } = P \big ( Z _ { i } = y \mid x _ { i } \big )
$$

Noisy-MAX模型变量概率计算公式为

$$
P \big ( Y \leq y \mid X \big ) = \sum _ { z \mid f _ { M A X } } \prod _ { i } \big ( c _ { z _ { i } } ^ { x _ { i } } \big ) = \prod _ { i } \left( \sum _ { z _ { i } \leq y } c _ { z _ { i } } ^ { x _ { i } } \right)
$$

其中： $f _ { _ { M A X } } \left( z \right) = m a x ( z _ { _ { I } } , . . . , z _ { _ { n } } )$ 。Noisy-MAX 模型概率分布为

$$
P { \big ( } y \mid X { \big ) } = \left\{ { \begin{array} { l l } { P { \big ( } Y \leq y \mid X { \big ) } - P { \big ( } Y \leq y - I \mid X { \big ) } } & { \ y \not = y _ { m i n } } \\ { P { \big ( } Y \leq y \mid X { \big ) } } & { \ y = y _ { m i n } } \end{array} } \right\}
$$

知识建模方法可能存在未知致因的干扰，导致Noisy-MAX模型进行概率评估过程中出现置信偏差[13],引入泄露变量 $Z _ { L }$ 将Noisy-MAX 模型改进为LeakyNoisy-MAX 模型，变量泄露参数 $c _ { y } ^ { L } = P { \left( Z _ { L } = y \right) }$ 和累积向量参数 $C _ { y } ^ { L } = \sum _ { Z _ { L } \leq y } c _ { z _ { L } } ^ { L }$ ，则式（1）可改进为

$$
P \left( Y \leq y \mid X \right) = C _ { y } ^ { L } \prod _ { i } C _ { y } ^ { x _ { i } }
$$

# 3 严重度值评估及最优决策

# 3.1 BN 初始化

将Netica5.18作为BN概率分析工具识别模型转换文件，学习案例数据并完成概率修正，评估跑道侵入态势并开展最优决策。搜集2015一2016年国内发生的53起各类跑道侵入案例为样本，部分BN节点变量状态模糊导致信息缺失，样本数据预处理之后采用最大期望化（expectationmaximization，EM）算法[14进行数据学习，得出初始先验概率。在此基础上，根据式（4）修正多态BN节点RI_Severity。改进后得到ICI节点间概率关系如表2所示。

表2节点RI_Severity 的条件概率分布  

<html><body><table><tr><td>A级</td><td>B级</td><td>C级</td><td>D级</td><td>运行差错</td><td>主要人为差错</td></tr><tr><td>0.001</td><td>0.089</td><td>0.288</td><td>0.622</td><td>Absent</td><td>Absent</td></tr><tr><td>0.005</td><td>0.117</td><td>0.423</td><td>0.455</td><td>Absent</td><td>Present</td></tr><tr><td>0.003</td><td>0.105</td><td>0.291</td><td>0.601</td><td>Present</td><td>Absent</td></tr><tr><td>0.01</td><td>0.136</td><td>0.429</td><td>0.425</td><td>Present</td><td>Present</td></tr></table></body></html>

基于改进后的初始先验BN，提出跑道侵入事故严重度值评价指标ASI（accident severity index），评估跑道侵入态势，有

$$
A S I _ { { _ j } } = \sum _ { i = 1 } ^ { N } V _ { i } P _ { i }
$$

其中： $V _ { i }$ 表示为对应严重度特征为 $i$ 级事故造成的损失； $P _ { i }$ 为某特定事故 $j$ 下 $i$ 级严重度特征事故概率； $N$ 为事故特征数量。

依据现有跑道侵入严重等级数学模型[15]，将跑道侵入A、B、C、D四个严重度特征进行量化得到 $V _ { A } { = } 4$ ， $V _ { B } { = } 3$ ， $V _ { C } { = } 2$ ，$V _ { D } { = } 1$ ；严重度描述特征A、B的 $A S I _ { j }$ 量化区间为$\left[ \boldsymbol { 0 . 2 5 \times V _ { A } } + \boldsymbol { 0 . 2 5 \times V _ { B } } + \boldsymbol { 0 . 2 5 \times V _ { C } } + \boldsymbol { 0 . 2 5 \times V _ { D } } , \boldsymbol { { \it l . 0 \times V _ { A } } } \right]$ ，定义为严重风险态势；严重度描述特征C、D的 $A S I _ { j }$ 量化区间为$\left[ \boldsymbol { I } . 0 \times \boldsymbol { V } _ { A } , 0 . 2 5 \times \boldsymbol { V } _ { A } + 0 . 2 5 \times \boldsymbol { V } _ { B } + 0 . 2 5 \times \boldsymbol { V } _ { C } + 0 . 2 5 \times \boldsymbol { V } _ { D } \right)$ ，表示一般风险态势，得出各严重度等级对应的ASI指标离散化分级标准如表3所示。

表3ASI指标离散化分级标准  

<html><body><table><tr><td>风险态势</td><td>ASI</td></tr><tr><td>严重</td><td>[2.50，4.0]</td></tr><tr><td>一般</td><td>[1，2.50)</td></tr></table></body></html>

# 3.2无策略态势评估

以“上海虹桥10.11”跑道侵入事故为例，由于塔台管制员遗忘飞机动态（丧失情景意识)，MU5106机组关闭应答机（通信设备问题）、违背空管原地等待指令并加速穿越正在被MU5643航班占用的36L-18R跑道，MU5643航班飞行员紧急操纵飞机起飞避免事故发生，该起事件中地面车辆驾驶员、机场道面均无构成威胁。

将上述事故报告中记录的各节点信息作为证据加入BN，得出“上海虹桥10.11”跑道侵入事故的 $A S I { = } 2 . 5 7 1$ （图4)，则该起跑道侵入态势评估结果为严重。其中DriverNormal（驾驶员表现正常）和（SurfaceNormal）机场道面正常的后验概率为$9 9 . 9 \%$ ，概率推理结果与事故调查结论高度吻合。案例分析表明，集成本体和BN的跑道侵入态势评估方法是切实可行的。

![](images/88b5a49ea43a5ff4b3b4567ed1f6963abce7168d6aab41487c7de568fa29c96b.jpg)  
图4跑道侵入态势评估结果

# 3.3不同策略态势评估

# 3.3.1单个管控措施

为分析特定威胁致因对跑道侵入态势的影响，采取管控措施并观察严重度节点风险态势变化，节点输出值ASI作为评价控制方案的效用指标。根据跑道侵入应急处置办法，从空管运行单位、驻场运行单位（军方、航空公司）和机场运行部门的管理、应急指挥等角度出发，针对影响跑道侵入的差错，提出相应的风险控制方案，详细见表4。

依据上述控制方案，基于跑道侵入态势评估BN分别观察加入单个管控措施后整体ASI值的变化。以“上海虹桥10.11”跑道侵入事故为例，该起事故原始输出值 $A S I ^ { 0 }$ 为2.571。若实施1号风险管控措施，即避免管制员出现情景意识丧失的问题，因此在跑道侵入态势评估BN模型中，将“ATCIssues”节点的状态空间由 $P$ (ATCCommFail) $\scriptstyle 1 = 0$ ， $P ( \mathrm { A T C L o s t S A } ) { = } 1 0 0$ ，P(ATCNormal)=0，调 整 为P(ATCCommFail)=0，P(ATCLostSA) $_ { = 0 }$ ， $P ($ ATCNormal)=100，调整后的跑道侵入风险态势如图5所示。可知调整后输出值 $A S I ^ { I }$ 为2.482，占原始输出值的 $9 6 . 5 3 \%$ ，评价公式为

$$
C = \frac { A S I ^ { 1 } } { A S I ^ { 0 } } \times 1 0 0 \% = 9 6 . 5 3 \%
$$

表4跑道侵入风险管控措施  

<html><body><table><tr><td>编号</td><td>风险管控措施 威胁</td><td></td><td>差错</td></tr><tr><td rowspan="2">1</td><td>加强管制员业务技能培训，提高通 信质量，强化管制人员责任意识2、丧失情景意识</td><td>1、通信失效</td><td rowspan="2">管制员</td></tr><tr><td></td><td>1、飞行活动区违</td></tr><tr><td rowspan="2">2</td><td>扩大培训考核覆盖范围和力度，提 高飞行区活动人员规章遵守意识</td><td>规操作</td><td>地面车辆 驾驶员</td></tr><tr><td>提升机组管理质量，强化机组应急1、违背空管指令</td><td>2、丧失情景意识</td><td>飞行机组</td></tr><tr><td rowspan="2"></td><td>处理能力和严格遵守管制指令意识2、丧失情景意识 加大场面飞行区安全隐患排查，明1、机场布局</td><td></td><td></td></tr><tr><td>4确各部门职责划分，提高场面安全2、机场灯光及地机场道面</td><td></td><td></td></tr><tr><td rowspan="2"></td><td>管理能力</td><td>面标志不清</td><td></td></tr><tr><td>规范通话用语，保障通信设备安 5全，完善空管单位与机场管理机</td><td>1、通信设备故障</td><td>双向沟通 2、通话内容偏差</td></tr></table></body></html>

![](images/39ad6cb52e83ebf0fb899133b7f818361736cbf11ace57e88c757fb60fc3d778.jpg)  
图5加入管控措施1后的跑道侵入风险态势变化其他风险控制措施效用计算结果见表5。

表5单个风险管控措施效用排序  

<html><body><table><tr><td>风险管控措施</td><td>态势评价指标ASI</td><td>与原始ASI占比/% 效用排序</td></tr><tr><td>1</td><td>2.482</td><td>96.53 5</td></tr><tr><td>2</td><td>2.405</td><td>93.54 3</td></tr><tr><td>3</td><td>2.363</td><td>91.94 2</td></tr><tr><td>4</td><td>2.420</td><td>94.12 4</td></tr><tr><td>5</td><td>2.254</td><td>87.67 1</td></tr></table></body></html>

# 3.3.2组合风险管控方案

分析效用排序结果：采取单个风险管控措施对跑道侵入态势的改善不够明显，无法满足降低场面运行安全风险的现实需求，因此在单个风险管控措施基础上，制定组合风险管控方案。方案1：同时采用管控措施1和5；方案2：同时采用管控措施3和5；方案3：同时采用管控措施3和4。

分别计算采取组合风险控制方案前提下，观察ASI的变化，结果见表6。

表6组合方案下跑道侵入风险控制效用排序  

<html><body><table><tr><td>组合方案</td><td>态势评价指标ASI</td><td>与原始 ASI占比/%</td><td>效用排序</td></tr><tr><td>1</td><td>2.035</td><td>79.15</td><td>3</td></tr><tr><td>2</td><td>1.857</td><td>72.22</td><td>1</td></tr><tr><td>3</td><td>1.968</td><td>76.55</td><td>2</td></tr></table></body></html>

# 3.4算例分析

从表6中可以发现，组合方案2（提高机组应急处理能力、增强机组遵守管制指令意识和规范通话用语、完善空管单位与机组间沟通协调机制）是最佳控制策略，组合方案3（增强机组遵守管制指令意识和加大场面飞行区安全隐患排查，提高场面安全管理能力）效用次之，最后是组合方案1（加强管制员业务技能培训、提高管制人员安全意识和规范通话用语、完善各单位间沟通协调机制)，三种组合控制方案可分别将ASI值控制在跑道侵入原ASI值的 $7 2 . 2 2 \%$ 、 $76 . 5 5 \%$ 和 $7 9 . 1 5 \%$ ，与单个风险管控措施相比降低跑道侵入风险态势较明显。通过分析飞行机组、空管等差错发生与运行环境威胁的相关性：与管制员相比飞行机组更易受场面运行环境变化的影响，机组与管制员通信威胁是造成飞行机组差错的主要致因，威胁程度高于机场灯光、地面标志等。

# 4 结束语

a）集成本体与BN的跑道侵入态势评估系统，利用本体语义描述优势解决了场面运行安全保障信息异构问题，发挥BN概率推理机制提升了场面运行风险管控能力。b)结合国内多起跑道侵入事故报告数据学习结果，实例分析表明本文构建的系统可为场面运行安全保障单位提供合理的跑道侵入态势评估服务，验证了本文方法的可行性。c）针对当前跑道侵入事故演化过程所涉及的威胁与差错，提出五项风险管控措施及三种风险控制方案，可为场面运行安全保障单位的事故降损决策提供量化参考依据。d)本文所提评估方法主要针对人为因素、管理等方面进行研究，后续将纳入天气、冲突场景等因素进综合分析，拓宽跑道侵入风险评估应用范围。

# 参考文献：

[1]Aguilar J,Torres J,Aguilar K.Autonomic communication system based on cognitive techniques [J]. International Journal of Knowledge-Based and Intelligent Engineering Systems,2018,22(1):17-37.   
[2]Castro A,Sedano AA, Garcia FJ,et al.Application of a multimedia service and resource management architecture for fault diagnosis [J]. Sensors,2018, 18 (1): 68.   
[3]王红，郭笑丹，祝寒．基于贝叶斯网络的民航突发事件因果关系分析方 法研究[J/OL].计算机应用研究，2019,36(3):1-2.[2018-08-30]. http://kns.cnki.net/kcms/detail/51.1196.TP.20180209.1114.044.html. (Wang Hong,Guo Xiaodan,Zhu Han.Research on causal reasoning method of domain ontology based on Bayesian network [J/OL].Application Research of Computers,2019,36 (3):1-2.[2018-08-30].http://kns.cnki. net/kcms/detail/51.1196.TP.20180209.1114.044.html.)

[4]王广正，王喜凤，夏敏．基于本体的Web 服务可靠性动态评估方法[J]. 计算机科学,2012,39(11): 98-101.(Wang Guangzheng,Wang Xifeng, Xia

Min.Ontology-based dynamic reliability evaluation model for Web services

[J]. Computer Science,2012,39 (11): 98-101.)   
[5] 罗军，林雪宁，闫永刚．基于高斯贝叶斯网络模型的跑道侵入影响因素 研究[J].安全与环境学报,2012,12(3):196-199.(Luo Jun,Lin Xuening, Yan Yonggang. Analysis of runway incursion influence factors based on Gaussian Bayesian network model[J]. Journal of Safety and Environment, 2012,12 (3): 196-199. )   
[6]Goodheart B J. Identification of causal paths and prediction of runway incursion risk by means of Bayesian belief networks [J]. Transportation Research Record,2014,2400 (1): 9-20.   
[7]王洁宁，赵晓鹏.i-SE:智能跑道侵入严重度评估本体框架[J].计算机 工程与设计,2017,38(8):222-2226.(Wang Jiening,Zhao Xiaopeng.i-SE: Intelligent severity evaluation ontology framework for runway incursion [J]. Computer Engineering and Design,2017,38(8): 2222-2226.)   
[8]王洁宁，赵晓鹏．机场安全热点本体建模及智能划分研究[J].中国安 全科学学报，2016,26(05):47-52.(Wang Jiening，Zhao Xiaopeng. Research on ontologymodelingand intelligent level ranking of airport safety hotspots [J].China SafetyScience Journal,2016,26(5): 47-52.)   
[9]Intermational Civil Aviation Organization. Threat and error management in air traffic control, Circular 314-AN//178 [R].Montreal: International Civil Aviation Organization,2008.   
[10]中国民用航空局．民航空管防止跑道侵入指导材料[R].北京：中国民 用航空局,2013.(Civil Aviation Administration ofChina.Guide material on theprevention of runway incursions[R]. Beijing:Civil Aviation Administration of China, 2013)   
[11]曹颖赛，刘思峰，方志耕，等．多态系统可靠性分析广义灰色贝叶斯网 络模型[J].系统工程与电子技术,2018,40(1):231-237.(Cao Yingsai, Liu Sifeng,Fang Zhigeng,et al.Generalized grey Bayesian network model for reliability analysis of multistate system [J].Systems Engineering and Electronics,2018,40(1): 231-237.)   
[12]肖蒙，张友鹏．小数据集条件下的多态系统贝叶斯网络参数学习[J]. 计算机科学，2015，42 (4): 253-257.(Xiao Meng,Zhang Youpeng. Parameters learning of Bayesian networks for multistate system with small sample [J]. Computer Science,2015,42 (4): 253-257.)   
[13] Chen Wei, Huang Shuping.Evaluating flight crew performance by a Bayesian network model[J].Entropy,2018,20 (3):178.   
[14]张文，姜祎盼，殷广达，等．基于朴素贝叶斯和 EM 算法的软件工作量 缺失数据处理方法[J]．系统工程理论与实践,2017,37(11):2965-2974 (Zhang Wen, Jiang Yipan, Yin Guangda,et al. Handing missing values in software effort data basedon naive Bayes and EMalgorithm[J].Systms Engineering Theory andPractice,2017,37(11):2965-2974.)   
[15] Claros B,Sun C，Edara P.Enhancing safety risk management with quantitative measures [J].Transportation Research Record,2017 (2603):1- 12.