# 基于云环境下新产品开发团队优选研究

陈友玲，王龙，左丽丹，牛禹霏(重庆大学 机械传动国家重点实验室，重庆 400044)

摘要：针对云环境下新产品开发团队优选问题，充分考虑团队的研发能力、协调能力和服务质量，建立了包含知识相似度评价模型、协同效应评价模型和服务质量评价模型的综合评价模型；对算法的适应度函数和搜索方式加以改进，提出了改进的人工蜂群算法，对所建立的模型进行求解，为服务需求方选择出最优团队组合；最后，以自动引导运输车（AGV）的新产品开发为例，通过模型求解和算法对比，验证了所提方法的可行性和有效性。

关键词：团队选择；知识相似度；协同效应；服务质量；人工蜂群算法中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2018.04.0442

Research on team optimal selection based on cloud environment for new product development

Chen Youling,Wang Long†, Zuo Lidan, Niu Yufei (The State Key Laboratory of mechanical Transmission,Chongqing University,Chongqing 40o044,China)

Abstract:Forthenew product developmentteamoptimal selection problems incloudenvironment,the team'sresearchand developmentcapabilities,coordinationcapabilities,andqualityofservice were fullyconsidered.An integrated evaluation model was established,which includes knowledge similarityevaluation model,collaborativeeect evaluation modeland quality of service evaluation model.The fitness function and search mechanism were improvedand a modified artificial bee colony algorithm was proposed to solve the established model and findan optimal teamcombination for theservice demanding party.Finally,akinganewproductdevelopmentoftheautomatic guidedvehicleasanexample,te feasibilityand effectiveness of the proposed method are verified through the solution of model and the comparison of algorithm.

Keywords:teamoptimal selection;knowledge similarity;collaborativeeffect;qualityof service；artificial beecolony algorithm

# 0 引言

随着云计算和大数据技术的飞速发展，其应运而生的云平台也得到了广泛应用。它是利用互联网信息技术实现资源的虚拟化和共享化，充分利用资源，降低其因闲置而造成的浪费，从而达到"分散的资源集中使用，集中资源分散服务"的状态[]。而人力资源作为云平台资源的重要组成部分，其跨区域实现能力的共享与协同，是协同完成云环境下新产品开发任务的基础。

以人力资源为对象，云平台通过跨地域、跨专业、跨行业的进行成员选择，组成临时团队，通过相互协作和知识共享完成设计任务[2]。但是对于复杂任务的设计和开发，仅仅通过成员选择已略显复杂，且无法满足任务对人力资源的需求，而以团队为选择单元进行团队组合是一个突破点。

云平台运营方拥有海量虚拟化的人力资源信息，其中包含大量服务相同或相近但服务质量和能力不同的服务团队[3]。如何快速地从海量组合方案中挑选出满足服务需求方的最佳团队组合，已成为云环境下团队组合优选的关键问题。现有的文献通过建立优选指标体系和选择优选方法对人力资源进行调用。陈友玲等人[4基于成员知识相似度和学习能力，分阶段构建成员选择模型，并进行成员指派。姜艳萍等人[5基于成员综合素质和专业技能指标期望，构建出交叉功能团队成员选择优化模型，完成团队成员选择。王娟茹等人[结合层次分析法和模糊优先规划法，求解虚拟团队成员优选问题。Zhang 等人[]考虑成员的综合能力和人际关系，建立人际关系模型，采用多目标粒子群算法进行求解。刘敬等人[2基于成员个人能力和协同合作能力信息，构建出优选指标体系和多目标优化模型，采用SPEA2算法进行求解。冯博等人[8基于伙伴间协调关系和协同效应，建立团队伙伴选择的数学模型，通过GRASP启发式算法进行求解。Feng等人[9基于成员个人表现和成员间协作表现，建立团队成员优选模型，采用改进的非支配排序遗传算法进行

求解。

以上文献主要从人力资源组合优选模型和求解方法进行了研究，并取得了大量的研究成果，在很大程度上解决了人力资源组合优选问题，促进了最优的人力资源组合方案选取。然而上述文献[4\~7]是通过构建成员评价体系进行团队成员选取，但未考虑成员之间协同效应，可能造成实际选取结果不佳。文献[8.9]同时考虑团队成员信息以及成员间的协同关系进行虚拟团队组建，但在处理复杂任务时，单个成员选取已无法满足任务的人力资源需求。此外，上述文献采用了多目标粒子群优化算法、SPEA2算法、GRASP启发式算法和非支配排序遗传算法等，但在实际运行过程中，仍存在收敛速度不稳定、收敛效果差、易收敛于局部最优解等问题。

基于以上分析，本文以团队为选择对象，分析了云环境下团队组合特点，充分考虑团队的研发能力、协调能力和服务质量，建立了包含知识相似度评价模型、协同效应评价模型和服务质量评价模型的综合评价模型。通过改进人工蜂群算法，提高算法收敛速度和效果，为服务需求方求解出最优团队组合，完成服务需求方任务。

# 1 团队组合优选与知识转移过程描述

# 1.1云平台团队组合与优选过程描述

云平台的团队选择过程如图1所示。在云平台上存在三个主体，可以划分为服务需求方、云平台运营方和资源提供方。针对云平台新产品开发各团队优选过程，其中服务需求方为新产品开发任务发布者，而资源提供方为各个设计研发团队，即服务需求方需要的为人力资源，而资源提供方供给的正是人力资源。从提交新产品开发任务请求至云平台到获得任务执行结果，要经历四个阶段，即任务分解阶段、子任务分析与搜索匹配阶段、团队组合优选阶段、执行和反馈阶段。在任务分解阶段，新产品开发任务Task提交到云平台，云平台根据服务需求方提供的相关信息和新产品开发的复杂性，将新产品开发任务分解为N个子开发任务 $\left( S u b t a s k , S T \right)$ ，且每个 $S T _ { i }$ 能够被单个服务团队完成， $T a s k = \left\{ S T _ { 1 } , S T _ { 2 } , \cdots , S T _ { i } , \cdots S T _ { \scriptscriptstyle N } \right\}$ 。在子任务分析与搜索匹配阶段，云平台分析每个 $S T _ { i }$ 的要求和特点，为其搜索匹配，得到满足 $S T _ { i }$ 的候选团队集合$\scriptstyle { C T S _ { i } = \left\{ C T _ { i } ^ { 1 } , C T _ { i } ^ { 2 } , \cdots , C T _ { i } ^ { j } , \cdots C T _ { i } ^ { M } \right\} }$ 。在团队组合优选阶段，需要从每个 $S T _ { i }$ 的候选团队集合 $C T S _ { i }$ 中选取一个团队来执行总开发任务Task，可以得到团队优选组合$T P C S = \left\{ C T _ { 1 } ^ { j _ { 1 } } , C T _ { 2 } ^ { j _ { 2 } } , \cdots , C T _ { i } ^ { j _ { i } } , \cdots C T _ { N } ^ { j _ { N } } \right\}$ ，其中 $C T _ { i } ^ { j _ { i } } \in C T S _ { i }$ ，该团队组合也就是在团队组合优选阶段所要得到的团队组合执行路径。在执行和反馈阶段，由服务需求方确认后，将调用该团队组合来执行新产品开发任务，整个开发过程将由云平台进行监控和反馈。

本文主要注重团队组合优选阶段的有效解决方案。云平台通过多方考虑和全局优化，从每个候选团队集合中选择出一个团队，然后依次调用所选择的团队，构建合并出团队组合执行路径。

![](images/14cc59624c5333f4d473eaf0b409538d292b94170f5c003d07280aacb626372a.jpg)  
图1团队组合优选过程示意图  
Fig.1Team combination optimization process diagram

# 1.2并行新产品开发与团队知识转移过程描述

通过相关文献查阅，对新产品开发过程中各子开发任务间的执行顺序进行研究。根据子任务执行的时间先后顺序，将开发过程中的设计活动分为串行模式、重叠模式和并行模式三种基本模式[10]。在串行模式中，任务B在任务A全部完成后再根据任务A传递的信息开始执行；在重叠模式中，任务A还未完成时，任务B根据任务A预发布信息，提前执行任务B；在并行模式中，任务A和B同时开始执行，并进行信息交流传递。上述三种模式在完成任务的周期和成本各不相同，串行模式的产品开发周期长，信息交流次数少，开发成本低，返工可能性高；重叠模式的产品开发周期适中，存在关联任务间的信息交流、开发成本和返工可能性中等；并行模式的产品开发时间短，信息交流次数多，开发成本高，返工概率随交流次数增多而减少。这几种开发模式间接地反映了开发时间和开发成本间的权衡，而本文研究对象为并行模式的新产品开发。新产品开发模式如图2所示。

![](images/69fbdb1e69b8e47dd6f19c59d7cf85ccba6843e778fdb7ce15f4e6c8e5512885.jpg)  
图2新产品开发模式

新产品开发过程实质上是一个知识创造、知识积累和知识转移的过程[1]，而产品开发团队正是知识的提供者，知识转移过程是通过团队间的信息交流完成的。以两个开发任务并行开发为例，知识转移过程如图3所示。团队a和b分别完成任务A与B，在任务开发周期内，团队a、b间共进行了n次知识转移。在团队a与b进行第一次知识转移之前，由其原始积累知识进行知识作业；在第一次知识转移后，团队a和b根据获取的初始知识进行知识作业；在第二次知识转移后，由于在上一次知识转移过程中获取错误知识或者不完备知识，需在本次知识转移过程中更新错误知识或完善知识，从而进行知识返工[12]，另外团队a、b会根据更新的知识进行新的知识作业；之后进行第三次知识转移，以此类推，直至完成任务开发。子开发任务的时间主要由知识作业时间、知识返工时间和交流时间构成。知识作业时间为知识转移前后知识作业所耗费的时间，它主要由任务本身决定，不受外界因素影响，用 ${ } ^ { e } T _ { i }$ 表示子任务$i$ 的总共的知识作业时间；知识返工时间为知识返工所消耗的时间，用 ${ ^ r T _ { i j } ^ { k } }$ 表示在子任务 $i$ 与 $j$ 的负责团队间第 $k$ （ $k \neq 1$ 次知识转移中子任务 $j$ 所产生的知识返工时间；沟通时间为两团队间知识转移所耗费的时间，用 ${ ^ { c } T _ { i j } ^ { k } }$ 表示子任务 $i$ 与 $j$ 的负责团队间第 $k$ 次知识转移中的交流时间。此外，产品开发团队的研发能力、学习能力、沟通交流能力和协同能力等均是影响知识转移次数和作业时间、返工时间的主要因素。

![](images/cf9a699af87b39d68d93386a0e1b112e5478653f9fe00fbcf48beb83293ed356.jpg)  
图3知识转移示意图  
Fig.3Schema diagram of knowledge transfer

# 2 模型构建

为了全面评价团队优选组合，本文从研发能力、协同效应和服务质量三个方面分别构建出知识相似度评价模型、协同效应评价模型和服务质量评价模型，并综合三个模型的优势进行有效结合，构建出综合评价模型，对团队优选组合进行全面、准确的评价，为服务需求方选择合适的团队组合提供依据。模型结构示意图如图4所示。

![](images/6ca53cffc8322e24c0b22125c4c45a1c677f434663aa989be7bae00f843e99cc.jpg)  
Fig.2New product development model   
图4模型结构框架示意图  
Fig.4Schematic diagram of model structure

# 2.1知识相似度评价模型

为了更好地衡量开发团队对于新产品开发任务的研发能力，本文提出知识相似度(knowledge similarity,KS)，指开发团队知识结构与开发任务知识需求之间的相似程度。知识相似度越大，表明开发团队越适合该开发任务，对此任务的开发能力越强，反之亦然。

本文参考文献[13]相关概念对知识相似度进行计算，给出以下相关概念。知识点(knowledge point,KP)，是新产品开发子任务中最小的数据单元，且无法再进一步划分。开发任务的知识集合中包含多个相关知识点，并根据相关知识点绘制知识结构树。知识模块(knowledge module,KM)，是上述知识点组成的集合。新产品开发任务的知识需求模块可表示为$K M R = \left. \left( k p r _ { 1 } , \alpha _ { 1 } \right) , \left( k p r _ { 2 } , \alpha _ { 2 } \right) , \cdots , \left( k p r _ { i } , \alpha _ { i } \right) \right.$ ，其中： $k p r _ { i }$ 为新产品开发任务所需要的知识点； $\alpha _ { i }$ 为各知识点的需求程度。各候选团队知识掌握模块可表示为

$K M G = \left\{ ( k p g _ { 1 } , \beta _ { 1 } ) , ( k p g _ { 2 } , \beta _ { 2 } ) , \cdots , \left( k p g _ { j } , \beta _ { j } \right) \right\}$ ，其中：kpgj为开发团队掌握的相关知识点； $\beta _ { i }$ 表示团队对各知识点的掌握程度。根据新产品开发任务的知识需求模块KMR和候选团队知识掌握模块KMG，定义新产品开发任务的知识需求向量空间为$V _ { r } = \left( \alpha _ { 1 } , \alpha _ { 2 } , \cdots , \alpha _ { i } \right)$ ，候选团队知识掌握程度向量空间$V _ { g } = \left( \beta _ { 1 } , \beta _ { 2 } , \cdots , \beta _ { j } \right) \circ$ （20

知识相似度包括语义相似度和距离相似度[4]，其中语义相似度根据 $K M R$ 和KMG知识模块中相关知识点在知识结构树中的位置决定，其计算公式如(1)所示；距离相似度由 $V _ { r }$ 和 $V _ { g }$ 两个向量空间的欧几里德距离大小决定，计算公式如(2)所示。为了更好的描述知识相似度，将语义相似度和距离相似度归约到区间(0,1]，其结果如式(3)(4)所示。

$$
\begin{array} { r } { S _ { s } \left( k p r _ { i } , k p g _ { j } \right) = \frac { \lambda \times \left| C _ { s u b } ( k p r _ { i } , R ) \cap C _ { s u b } ( k p g _ { j } , R ) \right| } { \left| C _ { s u b } ( k p r _ { i } , R ) \cup C _ { s u b } ( k p g _ { j } , R ) \right| } } \\ { + \frac { ( 1 - \lambda ) \times \left| C _ { s \operatorname* { u p } e r } ( k p r _ { i } , R ) \cap C _ { \operatorname* { s u p } e r } ( k p g _ { j } , R ) \right| } { \left| C _ { s u p e r } ( k p r _ { i } , R ) \cup C _ { s u p e r } ( k p g _ { j } , R ) \right| } } \end{array}
$$

$$
d \left( V _ { r } , V _ { g } \right) = \left\{ \begin{array} { l l } { \displaystyle { \sqrt { \sum _ { i = 1 } ^ { k } \left( \alpha _ { i } - \beta _ { i } \right) ^ { 2 } } } , } & { \quad \alpha _ { i } > \beta _ { i } ; } \\ { 0 , } & { \quad \alpha _ { i } \le \beta _ { i } \circ } \end{array} \right.
$$

其中： $\lambda$ 为知识结构树中父类与子类的相对程度；$\left| C _ { s u b } ( k p r _ { i } , R ) \cap C _ { s u b } ( k p g _ { j } , R ) \right|$ 为知识结构树下同属于kpr 和 $k p g _ { j }$ 的子类层级数； $\left| C _ { s u b } ( k p r _ { i } , R ) \cup C _ { s u b } ( k p g _ { j } , R ) \right|$ 为树下下同属于$k p r _ { i }$ 或 $k p g _ { j }$ 的子类层级数； $\left| C _ { \mathrm { s u p } e r } ( k p r _ { i } , R ) \cap C _ { \mathrm { s u p } e r } ( k p g _ { j } , R ) \right|$ 为树下包括 $k p r _ { i }$ 和 $k p g _ { j }$ 父类层级数； $\left| C _ { \mathrm s u p e r } ( k p r _ { i } , R ) \cup C _ { \mathrm s u p e r } ( k p g _ { j } , R ) \right|$ 树下包括 $k p r _ { i }$ 或 $k p g _ { j }$ 父类层级数； $k$ 表示 $\alpha _ { i } > \beta _ { i }$ 的元素个数；当 $a \neq b$ 时， $\alpha _ { i }$ 或 $\beta _ { i }$ 用0表示。

$$
S _ { s } = \frac { \displaystyle \sum _ { i = 1 } ^ { a } \sum _ { j = 1 } ^ { b } S _ { s } \left( k p r _ { i } , k p g _ { j } \right) } { 1 + \displaystyle \sum _ { i = 1 } ^ { a } \sum _ { j = 1 } ^ { b } S _ { s } \left( k p r _ { i } , k p g _ { j } \right) }
$$

$$
\boldsymbol { S _ { d } } = \frac { 1 } { 1 + d \left( \boldsymbol { V _ { r } } , \boldsymbol { V _ { g } } \right) }
$$

由上述语义相似度式(3)和距离相似度式(4)可获得知识相似度，如式(5)所示。其中为语义相似度和距离相似度的相对权重。

$$
S _ { k } = \gamma \times S _ { s } + \left( 1 - \gamma \right) \times S _ { d }
$$

通过计算新开发产品任务与服务团队间知识相似度，衡量团队与开发任务间的匹配程度。而团队优选组合的知识相似度

如式(6)所示。其中 $S _ { k , i }$ 表示候选团队 $C T _ { i }$ 与第 $i$ 子开发任务的知识相似度。

$$
S \left( T P C S \right) = \sum _ { i = 1 } ^ { n } S _ { k , i }
$$

# 2.2协同效应评价模型

团队知识相似度衡量团队的研发能力，而团队的协同效应则是衡量交互协调能力。团队协同效应通常指多个团队协调合作的效益大于其单个团队效益的总和[14]。在并行新产品开发团队组合中，只注重团队在处理各自任务的能力，往往忽略团队间的内在联系，导致开发的新产品无法达到预期要求。因此，本文将团队协同效应应用到并行新产品开发的团队选择中，追求团队组合的整体协同效应最佳。

本文对协同效应影响因素进行分析，结合并行情况下新产品开发团队组合的特性，归纳总结出团队组合协同效应的评价指标，如表1所示。

表1团队组合协同效应评价指标  
Table 1Team combination synergy evaluation index   

<html><body><table><tr><td>评价指标</td><td>定义</td></tr><tr><td>组织云协同</td><td>组合内团队间工作流程和组织结构的协同程度</td></tr><tr><td>技术云协同</td><td>组合内团队间相关技术的协同程度</td></tr><tr><td>历史交互云协同</td><td>组合内团队间历史交互记录中的协同程度</td></tr><tr><td>时间云协同</td><td>组合内团队间响应时间和交流时间的协同程度</td></tr></table></body></html>

1)组织云协同(D1）服务组合中各团队按照各自的工作流程和组织结构进行产品开发作业，流程同步性和组织一致性能够保证各阶段团队间的信息沟通和问题的及时调整。

2)技术云协同(D2）在产品过程中需要各种专业技术和相关软件的支持，如果团队使用的相关软件不一致或者版本有差异，甚至专业技术不统一，会极大地阻碍团队间的信息传递和数据交换。

3)历史交互云协同(D3）如果团队间拥有过合作的经历，每次合作完成后会对合作团队进行相应的评价，尤其是在云环境下，云平台会记录下历史交互的数据和信息。若双方有过合作历史记录，则根据历史交互数据进行协同效应评价；若无历史交互，则该项协同效应为0。

4)时间云协同(D4）团队的响应时间以及团队间交流时间节点是否一致，决定了团队间的契合度以及相关信息数据的及时更新和问题的及时发现，后续相关开发工作也会受到影响。

云平台储存了大量多方面的用户数据，并且具备及时更新和数据分析的能力，因此云平台专家可以利用大数据和数据挖掘技术结合云平台用户的历史交互数据进行协同效应分析，从而对上述的各协同效应评价指标值作出准确评估。

设上表中各评价指标的权重向量为 $W _ { c } = \left( w _ { 1 } , w _ { 2 } , \cdots , w _ { 4 } \right) ^ { T }$ ，且满足 $\sum _ { i = 1 } ^ { 4 } w _ { i } = 1$ ， $0 \leq w _ { i } \leq 1$ 。通过加权法则，可计算出团队组合中各团队之间的协同效应值CcT.cT $C _ { C T _ { i } , C T _ { j } } = \sum _ { i = 1 } ^ { 4 } w _ { i } \times D _ { i }$ 。其中：$C _ { { C T } _ { i } , { C T } _ { j } }$ 为团队组合中候选团队 $C T _ { i }$ 与子团队 $C T _ { j }$ 之间的协同效应值； $D _ { i }$ 表示第 $i$ 个协同效应评价指标。式(7)表示候选团队 $C T _ { i }$ 与组合内候选团队的平均协同效应值；式(8)表示团队组合的协同效应值。

$$
C _ { C T _ { i } } = \frac { \displaystyle \sum _ { j = 1 } ^ { n } C _ { C T _ { i } , C T _ { j } } } { n - 1 } , \left( i \neq j \right)
$$

$$
C ( T P C S ) = \Biggl ( \sum _ { i = 1 } ^ { n } C _ { C T _ { i } } \Biggr ) \Biggl / n
$$

# 2.3服务质量评价模型

在团队组合中，需考虑整体组合的服务质量，即团队组合在完成并行新产品开发任务所预估花费的时间、成本以及团队自身的信誉度等指标。

根据1.2节中，两团队间的知识转移会产生知识返工时间、知识交流时间以及其相应产生的成本。针对并行新产品开发任务，根据文献[11]中所建立的模型，规定各团队的学习能力指数、知识发出方的发布错误知识概率和各子开发任务的开发难度以及任务间相对依赖程度，在追求全局收益最大化原则下建立知识转移时间数学模型，并求解团队间交流次数。根据知识返工函数求解出每次交流后的知识返工时间，并对知识交流和知识返工的成本进行计算。

开发时间 $T$ 为各团队开始进行各自任务设计至完成总开发任务所耗费的时间。单个团队所花费的开发时间 $T _ { i }$ 包括知识作业时间 ${ ^ { e } T } _ { i }$ 、知识返工时间 $^ { r } T _ { i }$ ，交流时间 $^ c T _ { i }$ 。$T _ { i } { = } T _ { m o d i f i e d } \times \left( { } ^ { e } T _ { i } + { } ^ { r } T _ { i } + { } ^ { c } T _ { i } \right)$ 。其中时间修正系数 $T _ { m o d i f i e d }$ 表示实际时间与预期时间之间的偏离程度，用于对开发时间计算的修正。$T _ { m o d i f i e d } { = } \prod _ { i = 1 } ^ { n } \Bigl ( 1 { + } \left( T _ { a c t u a l } - T _ { e x p e c t e d } \right) \Bigl / T _ { e x p e c t e d } \Bigr )$ ，其中： $T _ { a c t u a l }$ 指实际完成任务的时间； $T _ { e x p e c t e d }$ 指预计完成任务的时间； $n$ 指该团队完成服务需求方提交任务的总个数。开发成本 $c$ 为各团队开始进行各自任务设计至完成总开发任务所产生的费用。单个团队的开发成本 $C _ { i }$ 包括知识作业成本 ${ } ^ { e } C _ { i }$ 、知识返工成本 ${ } ^ { r } C _ { i }$ 和交流成本 ${ } ^ { c } C _ { i }$ ， $C _ { i } { = } ^ { e } C _ { i } { + } ^ { r } C _ { i } { + } ^ { c } C _ { i }$ 。信誉度 $M$ 是指云平台对于服务团队的一种评价指标，反映团队的一种信誉程度。信誉度越高，服务需求方的合作意愿越强烈。云平台根据服务团队的历史匹配记录、履约状况等给出的一个综合性指标，且 $M \in \left[ 0 , 1 \right]$ 。以上评价指标的选取、数据的采集和量化等方面已经进行了相关深入的研究，本文限于篇幅，不再赘述。

本文将服务质量信息组定义为 $Q = \left\{ T , C , M \right\}$ ，在并行新产品开发团队组合的指标计算公式如表2所示。

表2团队组合指标计算公式  
Table 2Team combination indicator calculation formula   

<html><body><table><tr><td rowspan="2">模式</td><td colspan="3">参数</td></tr><tr><td>T</td><td>C</td><td>M</td></tr><tr><td>并行</td><td>Max(Ti)</td><td>Mc i=1</td><td>(M./</td></tr></table></body></html>

本文根据云平台专家组对服务质量的各个指标进行权重赋值， $W _ { q } = \left( w _ { 1 } , w _ { 2 } , w _ { 3 } \right) ^ { T }$ ，且满足 $\sum _ { i = 1 } ^ { 3 } w _ { i } = 1$ ， $0 \leq w _ { i } \leq 1$ 。式(9)为团队优选组合的服务质量评价值，其中 $T _ { _ { N } } , C _ { _ { N } } , M _ { _ { N } }$ 分别表示团队优选组合时间指标、成本指标和信誉度指标归一化结果。

$$
Q ( T P C S ) = w _ { 1 } \times T _ { N } + w _ { 2 } \times C _ { N } + w _ { 3 } \times M _ { N }
$$

# 2.4综合评价模型

团队优选组合的评价模型可以定义为一个三元组合$G = \left\{ S { \big ( } T P C S { \big ) } , C ( T P C S ) , Q ( T P C S ) \right\}$ ，其中： $S ( T P C S )$ 表示团队组合的知识相似度； $C ( T P C S )$ 表示团队组合的协同效应值，$C ( T P C S )$ 表示团队组合服务质量评价值；TPCS表示团队优选组合。本文从以上三个方面去全面衡量团队组合的综合开发实力，充分考虑三者之间的关系，通过相关专家赋值，通过层次分析法计算，得到权重 $W _ { \jmath } = \left( w _ { 1 } , w _ { 2 } , w _ { 3 } \right) ^ { \cal T }$ ，且满足 $\sum _ { i = 1 } ^ { 3 } w _ { i } = 1$ ，$0 \leq w _ { i } \leq 1$ 。构建出综合评价模型，根据式(10)计算出团队组合的综合评价值。

$$
I ( T P C S ) = w _ { 1 } \times S \left( T P C S \right) + w _ { 2 } \times C \left( T P C S \right) + w _ { 3 } \times Q \left( T P C S \right)
$$

# 3 改进人工蜂群算法

人工蜂群（artificialbeecolony，ABC）算法自提出之后，相关专家和研究人员在原有算法基础上加以改进，提高了算法的求解速度、稳定性和模型求解的适用性。而人工蜂群算法改进主要体现在适应度函数计算和蜜源搜索机制上。本文结合云环境下团队组合优选问题特性和所建立的求解模型特点，对ABC 算法的适应度函数计算方式和蜜源位置更新方式进行改进，提出一种改进的人工蜂群（modified artificial bee colony，MABC）算法。

标准ABC算法中，蜜蜂拥有雇佣蜂、侦查蜂和跟随蜂三种角色。由雇佣蜂确定蜜源 $X _ { i }$ ，并对其进行访问；跟随蜂根据雇佣蜂分享的蜜源信息，以概率值 $P _ { i }$ 选择跟随的雇佣蜂；在蜜源被抛弃后，由侦查蜂发现新蜜源[15]。以上为 ABC 算法中三种角色的简单介绍，下面将对标准ABC算法进行改进。

# 3.1适应度函数

适应度函数引导群体进化的方向，影响算法迭代的次数和解的质量，不同的适应度函数会得出不同优劣程度的解。标准ABC算法使用文献[15]中复杂的适应度值计算函数，本文结合综合评价模型特点，直接用综合评价模型的目标函数的值来代替适应度值。因为综合评价模型中三个维度中知识相似度、协同效应值和服务质量评价值的取值均在[0,1]内，且最终的综合评价值也类同于适应度值，能够判断蜜源的优劣，方便概率值$P _ { i }$ 的计算。适应度函数计算方式如式(11)所示。

$$
\begin{array} { r } { f i t _ { i } = f _ { i } = W _ { I } \bullet X _ { i } } \end{array}
$$

$$
{ { P } _ { i } } \mathrm { { = } } { \mathrm { { \it f i t } } _ { i } } \bigg / \sum _ { i = 1 } ^ { S N } { \mathrm { { \it f i t } } _ { i } }
$$

其中： $f i t _ { i }$ 表示适应度函数； $W _ { I }$ 为综合评价模型中的权重值； $X _ { i }$ 表示蜜源 $i$ ，为问题的一个可行解，也就是团队组合产生的三维度量指标值； $f _ { i }$ 为目标函数在 $X _ { i }$ 上所取得的函数值； $\mathit { S N }$ 为蜜源数量， $P _ { i }$ 为跟随蜂选择雇佣蜂的概率。

# 3.2搜索方式

雇佣蜂和侦查蜂的搜索方式决定着蜜蜂找到蜜源的速度和准确性。标准ABC算法通过在蜜源附近随机选取另外的蜜源，体现了算法的随机性，但算法的求解精度和收敛速度收到了限制。为提高算法的各项性能，本文改进了新蜜源位置的搜素方式[16]，如式(13)所示。

$$
\nu _ { i j } = x _ { i j } + c _ { 1 } \left( t \right) \varphi _ { i j } \left( x _ { i j } - x _ { k j } \right) + c _ { 2 } \left( t \right) \phi _ { i j } \left( x _ { b j } - x _ { i j } \right)
$$

其中： $\nu _ { i j }$ 为代替 $x _ { i j }$ 的新蜜源； $\varphi _ { i j }$ 为[-1,1]间的随机数； $\phi _ { i j }$ 为[0,1]间的随机数； $t$ 为当前迭代次数； $k$ 为[1,SN]间的随机整数； $x _ { b j }$ 为当前最优蜜源 $X _ { b }$ 的第 $j$ 个参数； $c _ { 1 } \big ( t \big )$ 和 $c _ { 2 } \big ( t \big )$ 为两个自适应控制参数，用于平衡算法不同阶段的搜索。在算法早期， $c _ { 1 } \big ( t \big )$ 应为一个较大值， $c _ { 2 } \big ( t \big )$ 应为一个较小的值；随着迭代次数增加，$c _ { 1 } \big ( t \big )$ 逐渐减小， $c _ { 2 } \big ( t \big )$ 逐渐增大。在算法运行过程中，通过 $c _ { 1 } \big ( t \big )$ 和 $c _ { 2 } \big ( t \big )$ 的相互协作，实现算法运行过程的自我调节，并且由$c _ { 1 } \big ( t \big )$ 和 $c _ { 2 } \big ( t \big )$ 的变化来调整搜索过程，克服人工蜂群算法易陷入局部最优等缺陷[7]。 $c _ { 1 } \big ( t \big )$ 和 $c _ { 2 } \big ( t \big )$ 的计算如式(14)所示。

$$
c _ { 1 } \left( t \right) = c _ { 1 } ^ { m a x } \left( \frac { c _ { 1 } ^ { m i n } } { c _ { 1 } ^ { m a x } } \right) ^ { \frac { t } { M C N } } , c _ { 2 } \left( t \right) = c _ { 2 } ^ { m a x } \left( \frac { c _ { 2 } ^ { m a x } } { c _ { 2 } ^ { m i n } } \right) ^ { \frac { t } { M C N } }
$$

其中： $t$ 为当前迭代次数；MCN 为最大迭代次数； ${ c _ { i } } ^ { m i n }$ 和 ${ c _ { i } } ^ { m a x }$ 为函数 $c _ { i } \left( t \right)$ 的最小和最大值。

此外，根据上述所建立的综合评价模型，分析了团队组合优选问题特点，发现所求解模型的搜索空间具有较小的可行区域，很难随机产生可行解和靠近可行区域的非可行解。在一个蜜源被访问次数超过阈值limit，侦查蜂会随机寻找新蜜源。为了改善这种随机情况，本文在改进其更新方式，如式(15)所示。

$$
x _ { i j } = x _ { i j } + \varphi _ { i j } \left( x _ { k j } - x _ { i j } \right) + \left( 1 - \varphi _ { i j } \right) \left( x _ { b j } - x _ { i j } \right)
$$

其中： $\varphi _ { i j }$ 为[-1,1]间的随机数； $k$ 为[1,SN]间的随机整数； $\boldsymbol { x } _ { b j }$ 为当前最优蜜源 $X _ { b }$ 的第 $j$ 个参数。

# 3.3算法流程

根据以上改进之处对算法进行修改，基于改进人工蜂群算法的云环境下新产品开发团队组合优选流程如图5所示。

![](images/019c731f699a55d1528661e92d28742f037cca85ca0dadb29816c5cfd06338b5.jpg)  
图5团队组合优选算法流程

# 4 实验结果与分析

为了验证MABC算法和综合评价模型在解决云环境下新产品开发团队组合优选问题上的可行性和有效性，本文通过有效数据采集和相关数据模拟，构建出实验算例。实验环境为MATLABR2015a，Windows10， $2 . 6 0 \ : \mathrm { G H z }$ ，8GBRAM。

# 4.1实验背景及相关数据求解

实验以AGV小车设计为背景，服务需求方向云平台提交AGV小车的新产品开发设计任务需求，云平台根据新产品开发任务要求和条件等相关信息，将设计任务分解成如图6所示的八个子开发任务，其子任务间的相互依赖程度如表3所示。同时，云平台进行搜索匹配，为每个子开发任务找到相关候选开发团队集合，其相关信息如表4所示。表中包括知识相似度模型处理后的各团队对子任务的知识相似度，知识相似度评价模型中取 $\scriptstyle \gamma = 0 . 5$ 。通过算法和模型进行求解，为服务需求方需找到最优团队组合，并由这些团队负责AGV小车的开发工作。

![](images/dd31c57ad866c64607e104b669705cf5a107d47d57858ea768ed16b984c3962d.jpg)  
Fig.5Team combination optimization algorithm flow   
图6子开发任务示意图  
Fig.6Sub-development task diagram

Table 3Degree of interdependence between subtasks   
表4候选团队集相关参数  

<html><body><table><tr><td>依赖程度</td><td>ST1</td><td>ST2</td><td>ST</td><td>ST4</td><td>ST5</td><td>ST6</td><td>ST7</td><td>ST8</td></tr><tr><td>ST1</td><td>1</td><td>0.35</td><td>0.28</td><td>0.15</td><td>0.12</td><td>0.20</td><td>0.55</td><td>0.68</td></tr><tr><td>ST2</td><td>0.22</td><td>1</td><td>0.56</td><td>0.18</td><td>0.10</td><td>0.12</td><td>0.64</td><td>0.16</td></tr><tr><td>ST3</td><td>0.24</td><td>0.48</td><td>1</td><td>0.14</td><td>0.15</td><td>0.20</td><td>0.44</td><td>0.08</td></tr><tr><td>ST4</td><td>0.18</td><td>0.30</td><td>0.20</td><td>1</td><td>0.28</td><td>0.35</td><td>0.25</td><td>0.15</td></tr><tr><td>ST5</td><td>0.10</td><td>0.22</td><td>0.25</td><td>0.16</td><td>1</td><td>0.58</td><td>0.10</td><td>0.05</td></tr><tr><td>ST6</td><td>0.10</td><td>0.15</td><td>0.24</td><td>0.12</td><td>0.62</td><td>1</td><td>0.28</td><td>0.08</td></tr><tr><td>ST7</td><td>0.35</td><td>0.52</td><td>0.32</td><td>0.15</td><td>0.05</td><td>0.06</td><td>1</td><td>0.18</td></tr><tr><td>STs</td><td>0.44</td><td>0.15</td><td>0.10</td><td>0.10</td><td>0.12</td><td>0.10</td><td>0.32</td><td>1</td></tr></table></body></html>

表3子任务间相互依赖程度  

<html><body><table><tr><td colspan="2">候选团队</td><td>知识</td><td colspan="2">开发时间T</td><td rowspan="2">知识作业成本C</td><td rowspan="2">信誉度M</td></tr><tr><td colspan="2"></td><td>相似度Sk</td><td>T</td><td>Tmodifed</td></tr><tr><td rowspan="3">CTS</td><td>CT1</td><td>0.82</td><td>282</td><td>1.04</td><td>675</td><td>0.88</td></tr><tr><td>CT²</td><td>0.77</td><td>294</td><td>1.01</td><td>690</td><td>0.86</td></tr><tr><td>CT</td><td>0.85</td><td>409</td><td>0.98</td><td>815</td><td>0.89</td></tr><tr><td>CTS2</td><td>CT²</td><td>0.72</td><td>386</td><td>1.11</td><td>800</td><td>0.92</td></tr><tr><td rowspan="3">CTS3</td><td>CT</td><td>0.83</td><td>415</td><td>0.96</td><td>790</td><td>0.91</td></tr><tr><td>CT</td><td>0.84</td><td>400</td><td>0.95</td><td>975</td><td>0.84</td></tr><tr><td>CT²</td><td>0.89</td><td>410</td><td>0.92</td><td>950</td><td>0.92</td></tr><tr><td rowspan="2">CTS4</td><td>CT</td><td>0.90</td><td>423</td><td>0.93</td><td>980</td><td>0.93</td></tr><tr><td>CT4</td><td>0.76</td><td>260</td><td>1.06</td><td>720</td><td>0.93</td></tr><tr><td rowspan="2">CTS5</td><td>CT</td><td>0.74</td><td>273</td><td>1.08</td><td>740</td><td>0.90</td></tr><tr><td>CT</td><td>0.79</td><td>308</td><td>0.99</td><td>830</td><td>0.88</td></tr><tr><td rowspan="2">CTS6</td><td>CT²</td><td>0.78</td><td>320</td><td>1.02</td><td>800</td><td>0.91</td></tr><tr><td>CT</td><td>0.80</td><td>296</td><td>1.04</td><td>895</td><td>0.87</td></tr><tr><td rowspan="2">CTS,</td><td>CT²</td><td>0.82</td><td>304</td><td>0.98</td><td>870</td><td>0.89</td></tr><tr><td>CT</td><td>0.85</td><td>251</td><td>0.95</td><td>555</td><td>0.92</td></tr><tr><td rowspan="2"></td><td>CT²</td><td>0.88</td><td>230</td><td>1.08</td><td>530</td><td>0.94</td></tr><tr><td>CT</td><td>0.79</td><td>225</td><td>1.12</td><td>595</td><td>0.95</td></tr><tr><td rowspan="2">CTSs</td><td>CT²</td><td>0.77</td><td>256</td><td>1.07</td><td>610</td><td>0.96</td></tr></table></body></html>

为了方便MABC算法对模型进行求解，对协同效应评价模型相关数据进行计算和预处理。在协同效应评价模型中，取权重向量 $W _ { c } = \left( 0 . 2 5 , 0 . 2 5 , 0 . 2 5 , 0 . 2 5 \right) ^ { T }$ ，得到团队间协同效应值矩阵表，如表5所示。其中同一团队集合中各团队不进行协同效应评估，用“一”表示。此外，也需对服务质量评价模型中相关数据进行处理。利用文献[11]中所建立模型，根据表3和4相关信息，求解出在完成并行新产品开发任务后各团队间所进行团队交流和知识作业所耗费的时间和成本，其相关信息如表6所示，为团队组合优选提供数据支持。表中“3/7/12/14”分别表示“交流时间 $^ c T$ /交流成本 $^ c C$ /知识返工时间 $^ { r } T$ /知识返工成本 $^ r c$ ”。

表5团队间协同效应值矩阵表

Table 4 Candidate team set related parameters   
Table 5Inter-team synergy value matrix   

<html><body><table><tr><td></td><td>CT</td><td>CT²</td><td>CT</td><td>CT2²</td><td>CT</td><td>CT</td><td>CT²</td><td>CT</td><td>CTA</td><td>CT</td><td>CT</td><td>CT²</td><td>CT</td><td>CT²</td><td>CT</td><td>CT</td><td>CT</td><td>CT&²</td></tr><tr><td>CT</td><td>1</td><td>1</td><td>0.43</td><td>0.52</td><td>0.64</td><td>0.51</td><td>0.73</td><td>0.41</td><td>0.58</td><td>0.53</td><td>0.57</td><td>0.68</td><td>0.47</td><td>0.57</td><td>0.56</td><td>0.63</td><td>0.65</td><td>0.48</td></tr><tr><td>CT²</td><td>一</td><td>一</td><td>0.55</td><td>0.49</td><td>0.52</td><td>0.64</td><td>0.59</td><td>0.62</td><td>0.52</td><td>0.55</td><td>0.47</td><td>0.59</td><td>0.62</td><td>0.66</td><td>0.58</td><td>0.60</td><td>0.59</td><td>0.55</td></tr></table></body></html>

<html><body><table><tr><td>CT</td><td>0.43</td><td>0.55</td><td>1</td><td>1</td><td>1</td><td>0.60</td><td>0.59</td><td>0.62</td><td>0.61</td><td>0.49</td><td>0.59</td><td>0.65</td><td>0.52</td><td>0.49</td><td>0.57</td><td>0.62</td><td>0.66</td><td>0.62</td></tr><tr><td>CT²</td><td>0.52</td><td>0.49</td><td>1</td><td>1</td><td>1</td><td>0.58</td><td>0.66</td><td>0.62</td><td>0.52</td><td>0.58</td><td>0.63</td><td>0.62</td><td>0.56</td><td>0.60</td><td>0.52</td><td>0.69</td><td>0.55</td><td>0.59</td></tr><tr><td>CT</td><td>0.64</td><td>0.52</td><td>一</td><td>1</td><td></td><td>0.64</td><td>0.69</td><td>0.60</td><td>0.59</td><td>0.55</td><td>0.61</td><td>0.66</td><td>0.55</td><td>0.58</td><td>0.63</td><td>0.71</td><td>0.70</td><td>0.60</td></tr><tr><td>CT</td><td>0.51</td><td>0.64</td><td>0.60</td><td>0.58</td><td>0.64</td><td></td><td>1</td><td>1</td><td>0.62</td><td>0.67</td><td>0.66</td><td>0.61</td><td>0.60</td><td>0.59</td><td>0.65</td><td>0.67</td><td>0.62</td><td>0.64</td></tr><tr><td>CT²</td><td>0.73</td><td>0.59</td><td>0.59</td><td>0.66</td><td>0.69</td><td>1</td><td>1</td><td>1</td><td>0.70</td><td>0.66</td><td>0.65</td><td>0.68</td><td>0.58</td><td>0.62</td><td>0.67</td><td>0.69</td><td>0.63</td><td>0.59</td></tr><tr><td>CT</td><td>0.66</td><td>0.62</td><td>0.62</td><td>0.62</td><td>0.60</td><td>1</td><td>1</td><td></td><td>0.68</td><td>0.65</td><td>0.61</td><td>0.66</td><td>0.62</td><td>0.65</td><td>0.68</td><td>0.71</td><td>0.64</td><td>0.62</td></tr><tr><td>CT</td><td>0.58</td><td>0.52</td><td>0.61</td><td>0.52</td><td>0.59</td><td>0.62</td><td>0.70</td><td>0.68</td><td>1</td><td>1</td><td>0.65</td><td>0.68</td><td>0.63</td><td>0.69</td><td>0.58</td><td>0.64</td><td>0.68</td><td>0.60</td></tr><tr><td>CT</td><td>0.53</td><td>0.55</td><td>0.49</td><td>0.58</td><td>0.55</td><td>0.67</td><td>0.66</td><td>0.65</td><td>1</td><td>1</td><td>0.59</td><td>0.67</td><td>0.66</td><td>0.65</td><td>0.61</td><td>0.63</td><td>0.66</td><td>0.63</td></tr><tr><td>CT</td><td>0.57</td><td>0.47</td><td>0.59</td><td>0.63</td><td>0.61</td><td>0.66</td><td>0.65</td><td>0.61</td><td>0.65</td><td>0.59</td><td>1</td><td>1</td><td>0.60</td><td>0.62</td><td>0.52</td><td>0.53</td><td>0.62</td><td>0.60</td></tr><tr><td>CT²</td><td>0.68</td><td>0.59</td><td>0.65</td><td>0.62</td><td>0.66</td><td>0.61</td><td>0.68</td><td>0.66</td><td>0.68</td><td>0.67</td><td></td><td>1</td><td>0.58</td><td>0.65</td><td>0.50</td><td>0.56</td><td>0.65</td><td>0.57</td></tr><tr><td>CT</td><td>0.47</td><td>0.62</td><td>0.52</td><td>0.56</td><td>0.55</td><td>0.60</td><td>0.58</td><td>0.62</td><td>0.63</td><td>0.66</td><td>0.60</td><td>0.58</td><td>1</td><td>1</td><td>0.67</td><td>0.68</td><td>0.69</td><td>0.72</td></tr><tr><td>CT²</td><td>0.57</td><td>0.66</td><td>0.49</td><td>0.60</td><td>0.58</td><td>0.59</td><td>0.62</td><td>0.65</td><td>0.69</td><td>0.65</td><td>0.62</td><td>0.65</td><td>1</td><td>1</td><td>0.66</td><td>0.71</td><td>0.70</td><td>0.71</td></tr><tr><td>CT1</td><td>0.56</td><td>0.58</td><td>0.57</td><td>0.52</td><td>0.63</td><td>0.65</td><td>0.67</td><td>0.68</td><td>0.58</td><td>061</td><td>0.52</td><td>0.50</td><td>0.67</td><td>0.66</td><td>1</td><td>1</td><td>0.58</td><td>0.49</td></tr><tr><td>CT</td><td>0.63</td><td>0.60</td><td>0.62</td><td>0.69</td><td>0.71</td><td>0.67</td><td>0.69</td><td>0.71</td><td>0.64</td><td>0.63</td><td>0.53</td><td>0.56</td><td>0.68</td><td>0.71</td><td></td><td>1</td><td>0.62</td><td>0.57</td></tr><tr><td>CTs</td><td>0.65</td><td>0.59</td><td>0.66</td><td>0.55</td><td>0.70</td><td>0.62</td><td>0.63</td><td>0.64</td><td>0.68</td><td>0.66</td><td>0.62</td><td>0.65</td><td>0.69</td><td>0.70</td><td>0.58</td><td>0.62</td><td></td><td>1</td></tr><tr><td>CT²</td><td>0.48</td><td>0.55</td><td>0.62</td><td>0.59</td><td>0.60</td><td>0.64</td><td>0.59</td><td>0.62</td><td>0.60</td><td>0.63</td><td>0.60</td><td>0.57</td><td>0.72</td><td>0.71</td><td>0.49</td><td>0.57</td><td></td><td>1</td></tr></table></body></html>

# 4.2算法求解

根据上述相关数据初始化结果，通过MABC算法对团队组合优选的组合评价评价模型进行求解，并在相同参数设置和环境下重复进行100 次实验。MABC 算法的相关数据设置如下：$S N { = } 1 0 0$ ， $M C N = 5 0 0$ ， $l i m i t { = } 1 0 0$ ， ${ c _ { 1 } } ^ { m i n } = 0 . 8$ ， ${ c _ { 1 } } ^ { m a x } { = } 1 . 2$ ，${ c _ { 2 } } ^ { m i n } { = } 0 . 2$ ， ${ c _ { 2 } } ^ { m a x } { = } 1 . 2$ 。新产品开发团队选择的综合评价模型相关参数补充如下：Wq= $W _ { q } = \left( \frac { 1 } { 2 } , \frac { 1 } { 3 } , \frac { 1 } { 6 } \right) ^ { T }$ ， $W _ { I } = \left( \frac { 1 } { 3 } , \frac { 1 } { 3 } , \frac { 1 } { 3 } \right) ^ { T }$ ：服务质量评价模型中约束信息为：开发时间不超过500，开发成本不超过8000，团队组合的信誉度不低于0.88。

根据子开发任务的候选团队集合，实验案例总共有576种团队组合方式，不同组合方式的综合评价值不同，通过本文模型和算法求解出综合评价值最高的团队组合。以团队组合的知识相似度、协同效应值和服务质量为三维坐标，绘制出案例模型的解空间，如图7所示。由于服务质量评价模型中存在相关约束条件，使得团队组合存在非可行解。

根据求解的综合评价结果，优选团队组合为$T P C S = \left\{ C T _ { 1 } ^ { 1 } , C T _ { 2 } ^ { 3 } , C T _ { 3 } ^ { 2 } , C T _ { 4 } ^ { 1 } , C T _ { 5 } ^ { 2 } , C T _ { 6 } ^ { 2 } , C T _ { 7 } ^ { 2 } , C T _ { 8 } ^ { 1 } \right\}$ ，该优选团队组合综合评价值为 $I ( T P C S ) { = } 0 . 7 8 5$ ，其中知识相似度评价值$S \big ( T P C S \big ) { = } 0 . 8 2 1$ ，协同效应评价值 $C ( T P C S ) { = } 0 . 6 5 3$ ，服务质量评价值为 $Q \big ( T P C S \big ) { = } 0 . 8 8 1$ ，各评价值符合实际状况。根据以上评价结果，发现改进人蜂群算法和综合评价模型在解决团队组合优选问题上是可行的。

![](images/20e354c654eed0768a2d1d11a8be14c497a8bc42e41f750e58a89fbca41f0eec.jpg)  
图7 团队组合解空间  
Fig.7Team combination solution space

表6知识交流/返工时间成本矩阵表  
Table 6Knowledge exchange/rework time cost matrix   

<html><body><table><tr><td></td><td>CT</td><td>CT1²</td><td>CT</td><td>CT²</td><td>CT</td><td>CT</td><td>CT²</td><td>CT</td><td>CT</td><td>CT</td><td>CT</td><td>CT²</td><td>CT</td><td>CT</td><td>CT</td><td>CT²</td><td>CT</td><td>CT²</td></tr><tr><td>CT1</td><td>1</td><td></td><td>3/7</td><td>4/8/</td><td>3/6/</td><td>3/5/</td><td>2/3/</td><td>3/6/</td><td>1/2/</td><td>2/2/</td><td>1/2/</td><td>1/1/</td><td>2/3/</td><td>1/2/</td><td>5/9/</td><td>4/8/</td><td>7/14/</td><td>6/13/</td></tr><tr><td></td><td></td><td></td><td>12/14</td><td>9/15</td><td>9/13</td><td>13/18</td><td>11/12</td><td>15/27</td><td>12/15</td><td>20/18</td><td>10/16</td><td>8/19</td><td>11/19</td><td>9/16</td><td>13/26</td><td>10/17</td><td>12/20</td><td>16/25</td></tr><tr><td>CT²</td><td></td><td></td><td>4/9/</td><td>4/7/</td><td>3/7/</td><td>4/7/</td><td>3/5/</td><td>3/6/</td><td>2/4/</td><td>3/5/</td><td>2/3/</td><td>1/2/</td><td>2/4/</td><td>2/3/</td><td>6/11/</td><td>5/10/</td><td>8/15/</td><td>7/13/</td></tr><tr><td></td><td></td><td></td><td>11/18</td><td>12/15</td><td>12/16</td><td>20/13</td><td>18/27</td><td>14/21</td><td>9/19</td><td>22/15</td><td>15/19</td><td>11/22</td><td>18/22</td><td>17/29</td><td>17/20</td><td>16/20</td><td>17/25</td><td>19/23</td></tr><tr><td>CT</td><td>3/71</td><td>4/9/</td><td></td><td></td><td></td><td>5/10/</td><td>6/12/</td><td>5/9/</td><td>2/4/</td><td>3/5/</td><td>2/4/</td><td>2/5/</td><td>2/3/</td><td>1/2/</td><td>5/10/</td><td>4/9/</td><td>2/4/</td><td>2/5/</td></tr><tr><td></td><td>12/14</td><td>11/18</td><td></td><td>一</td><td></td><td>12/17</td><td>13/14</td><td>14/20</td><td>13/29</td><td>15/22</td><td>13/19</td><td>15/19</td><td>13/17</td><td>14/19</td><td>14/21</td><td>12/17</td><td>8/12</td><td>8/15</td></tr><tr><td>CT²</td><td>4/8/</td><td>4/7</td><td></td><td></td><td></td><td>5/10/</td><td>4/9/</td><td>6/11/</td><td>3/5/</td><td>3/6/</td><td>2/5/</td><td>1/3/</td><td>2/3/</td><td>2/4/</td><td>6/10/</td><td>5/9/</td><td>2/3/</td><td>2/4/</td></tr><tr><td></td><td>9/15</td><td>12/15</td><td></td><td></td><td></td><td>17/15</td><td>19/30</td><td>16/18</td><td>12/26</td><td>15/21</td><td>12/17</td><td>10/23</td><td>16/22</td><td>13/25</td><td>18/23</td><td>18/24</td><td>7/15</td><td>10/16</td></tr></table></body></html>

<html><body><table><tr><td></td><td>3/6/</td><td>3/71</td><td></td><td></td><td></td><td>6/10/</td><td>4/8/</td><td>5/9/</td><td>2/3/</td><td>2/4/</td><td>2/3/</td><td>1/2/</td><td>2/4/</td><td>1/1/</td><td>5/9/</td><td>4/8/</td><td></td><td>1/3/ 1/2/</td></tr><tr><td>CT</td><td>9/13</td><td>12/16</td><td></td><td></td><td></td><td>14/20</td><td>10/12</td><td>11/14</td><td>16/17</td><td>17/29</td><td>17/23</td><td>9/14</td><td>11/22</td><td>8/15</td><td>15/16</td><td>9/17</td><td>5/12</td><td>11/17</td></tr><tr><td></td><td>3/5/</td><td>4/7/</td><td>5/10/</td><td>5/10/</td><td>6/10/</td><td></td><td></td><td></td><td>2/3/</td><td>2/4/</td><td>2/4/</td><td>3/5/</td><td>3/5/</td><td>2/5/</td><td>3/6/</td><td>4/8/</td><td>1/2/</td><td>1/2/</td></tr><tr><td>CT</td><td>13/18</td><td>20/13</td><td>12/17</td><td>17/15</td><td>14/20</td><td></td><td></td><td></td><td>12/17</td><td>17/15</td><td>10/15</td><td>15/16</td><td>12/16</td><td>8/19</td><td>9/19</td><td>15/22</td><td>11/12</td><td>9/14</td></tr><tr><td></td><td>2/3/</td><td>3/5/</td><td>6/12/</td><td>4/9/</td><td>4/8/</td><td></td><td></td><td></td><td>1/2/</td><td>2/3/</td><td>2/3/</td><td>1/3/</td><td>2/4/</td><td>2/3/</td><td>4/7/</td><td>3/5/</td><td>2/3/</td><td>1/1/</td></tr><tr><td>CT²</td><td>11/12</td><td>18/27</td><td>13/14</td><td>19/30</td><td>10/12</td><td></td><td></td><td></td><td>8/14</td><td>14/15</td><td>9/15</td><td>6/11</td><td>12/19</td><td>8/14</td><td>13/25</td><td>11/17</td><td>5/10</td><td>6/14</td></tr><tr><td></td><td>3/6/</td><td>3/6/</td><td>5/9/</td><td>6/11/</td><td>5/9/</td><td></td><td></td><td></td><td>2/4/</td><td>2/3/</td><td>1/3/</td><td>2/5/</td><td>2/3/</td><td>2/4/</td><td>4/8/</td><td>4/7/</td><td>1/2/</td><td>2/3/</td></tr><tr><td>CT</td><td>15/27</td><td>14/21</td><td>14/20</td><td>16/18</td><td>11/14</td><td></td><td>一</td><td></td><td>7/19</td><td>9/18</td><td>11/16</td><td>8/14</td><td>13/24</td><td>14/19</td><td>14/22</td><td>10/19</td><td>8/14</td><td>7/15</td></tr><tr><td></td><td>1/2/</td><td>2/4/</td><td>2/4/</td><td>3/5/</td><td>2/3/</td><td>2/3/</td><td>1/2/</td><td>2/4/</td><td></td><td></td><td>3/6/</td><td>3/5/</td><td>3/5/</td><td>2/3/</td><td>3/5/</td><td>2/3/</td><td>1/2/</td><td>2/4/</td></tr><tr><td>CT</td><td>12/15</td><td>9/19</td><td>13/29</td><td>12/26</td><td>16/17</td><td>12/17</td><td>8/14</td><td>7/19</td><td></td><td>一</td><td>9/16</td><td>8/14</td><td>13/18</td><td>15/13</td><td>12/22</td><td>11/20</td><td>8/15</td><td>12/15</td></tr><tr><td></td><td>2/2/</td><td>3/5/</td><td>3/5/</td><td>3/6/</td><td>2/4/</td><td>2/4/</td><td>2/3/</td><td>2/3/</td><td></td><td></td><td>4/7/</td><td>4/8/</td><td>2/4/</td><td>3/6/</td><td>2/4/</td><td>3/6/</td><td>1/2/</td><td>2/3/</td></tr><tr><td>CT²</td><td>20/18</td><td>22/15</td><td>15/22</td><td>15/21</td><td>17/29</td><td>17/15</td><td>14/15</td><td>9/18</td><td></td><td></td><td>10/21</td><td>11/18</td><td>16/21</td><td>14/19</td><td>12/24</td><td>14/15</td><td>10/19</td><td>13/21</td></tr><tr><td></td><td>1/2/</td><td>2/3/</td><td>2/4/</td><td>2/5/</td><td>2/3/</td><td>2/4/</td><td>2/3/</td><td>1/3/</td><td>3/6/</td><td>4/7/</td><td></td><td></td><td>6/12/</td><td>5/10/</td><td>2/3/</td><td>1/2/</td><td>1/1/</td><td>1/1/</td></tr><tr><td>CT</td><td>10/16</td><td>15/19</td><td>13/19</td><td>12/17</td><td>17/23</td><td>10/15</td><td>9/15</td><td>11/16</td><td>9/16</td><td>10/21</td><td></td><td></td><td>15/29</td><td>14/27</td><td>13/25</td><td>14/27</td><td>12/20</td><td>9/21</td></tr><tr><td></td><td>1/1/</td><td>1/2/</td><td>2/5/</td><td>1/3/</td><td>1/2/</td><td>3/5/</td><td>1/3/</td><td>2/5/</td><td>3/5/</td><td>4/8/</td><td></td><td></td><td>5/11/</td><td>5/9/</td><td>1/2/</td><td>1/1/</td><td>1/1/</td><td>1/2/</td></tr><tr><td>CT²</td><td>8/19</td><td>11/22</td><td>15/19</td><td>10/23</td><td>9/14</td><td>15/16</td><td>6/11</td><td>8/14</td><td>8/14</td><td>11/18</td><td></td><td></td><td>12/24</td><td>11/23</td><td>17/25</td><td>15/19</td><td>10/18</td><td>14/25</td></tr><tr><td></td><td>2/3/</td><td>2/4/</td><td>2/3/</td><td>2/3/</td><td>2/4/</td><td>3/5/</td><td>2/4/</td><td>2/3/</td><td>3/5/</td><td>2/4/</td><td>6/12/</td><td>5/11/</td><td></td><td></td><td>2/4/</td><td>3/5/</td><td>1/1/</td><td>1/1/</td></tr><tr><td>CT</td><td>11/19</td><td>18/22</td><td>13/17</td><td>16/22</td><td>11/22</td><td>12/16</td><td>12/19</td><td>13/24</td><td>13/18</td><td>16/21</td><td>15/29</td><td>12/24</td><td></td><td>一</td><td>10/21</td><td>12/25</td><td>9/18</td><td>9/17</td></tr><tr><td></td><td>1/2/</td><td>2/3/</td><td>1/2/</td><td>2/4/</td><td>1/1/</td><td>2/5/</td><td>2/3/</td><td>2/4/</td><td>2/3/</td><td>3/6/</td><td>5/10/</td><td>5/9/</td><td></td><td></td><td>3/4/</td><td>2/3/</td><td>1/1/</td><td>1/2/</td></tr><tr><td>CT²</td><td>9/16</td><td>17/29</td><td>14/19</td><td>13/25</td><td>8/15</td><td>8/19</td><td>8/14</td><td>14/19</td><td>15/13</td><td>14/19</td><td>14/27</td><td>11/23</td><td></td><td>1</td><td>13/24</td><td>12/21</td><td>8/15</td><td>10/21</td></tr><tr><td>CT1</td><td>5/9/</td><td>6/11/</td><td>5/10</td><td>6/10/</td><td>5/9/</td><td>3/6/</td><td>4/71</td><td>4/8/</td><td>3/5/</td><td>2/4/</td><td>2/3/</td><td>1/2/</td><td>2/4/</td><td>3/4/</td><td></td><td></td><td>2/3/</td><td>2/4/</td></tr><tr><td></td><td>13/26</td><td>17/20</td><td>14/21</td><td>18/23</td><td>15/16</td><td>9/19</td><td>13/25</td><td>14/22</td><td>12/22</td><td>12/24</td><td>13/25</td><td>17/25</td><td>10/21</td><td>13/24</td><td></td><td></td><td>7/13</td><td>7/14</td></tr><tr><td>CT²</td><td>4/8/</td><td>5/10/</td><td>4/9/</td><td>5/9/</td><td>4/8/</td><td>4/8/</td><td>3/5/</td><td>4/7/</td><td>2/3/</td><td>3/6/</td><td>1/2/</td><td>1/1/</td><td>3/5/</td><td>2/3/</td><td></td><td></td><td>1/2/</td><td>2/3/</td></tr><tr><td></td><td>10/17</td><td>16/20</td><td>12/17</td><td>18/24</td><td>9/17</td><td>15/22</td><td>11/17</td><td>10/19</td><td>11/20</td><td>14/15</td><td>14/27</td><td>15/19</td><td>12/25</td></table></body></html>

# 4.3有效性验证和算法对比

在算法构建初期，本文算法直接用综合评价模型的目标函数的值来代替适应度值；随着迭代次数增加，适应度值会逐渐增加到最大适应度值。本文通过对改进前后人工蜂群算法的适应度函数值进行对比分析，进一步分析MABC算法在处理团队组合优选问题上的有效性，其实验结果如图8所示。

图8在一定程度上反映了改进之处对人工蜂群算法的影响，在相同的迭代次数下，MABC算法具有更高的适应度值；在达到相同的适应度值时，MABC算法耗时更短。因为改进了人工蜂群算法的搜索方式，在一定程度上加快了算法的收敛速度，避免陷入局部最优解。

为了进一步分析MABC 算法在处理团队组合优选问题上的可行性和高效性，调用MATLAB 算法工具箱，引入蚁群算法（ant colony optimization algorithm,ACO）[18]、遗传算法(geneticalgorithm,GA)。在相同的实验环境下，保持同类型参数设置相同，其中ACO 算法中信息启发因子、期望启发因子和蒸发系数分别设为1、2和0.8；GA算法中交叉算子和变异算子分别设置为0.7和0.1。分别进行100次实验，得到四种算法处理云环境下新产品开发团队组合优选问题的各项数据，如表7所示。通过四种算法的运行结果（均值±标准差)对比，MABC算法具有求解性能好、求解稳定性好和求解速度快等优势。

![](images/6b21477054064a4c5e99732ebe3c3e53f2d42960a7359f4e75634006ee010fb4.jpg)  
图8适应度对比曲线Fig.8Fitness curve

表7算法运行结果比较  
Table 7Comparison of algorithm operation results   

<html><body><table><tr><td rowspan="2">评价指标</td><td colspan="4">算法</td></tr><tr><td>MABC</td><td>ABC</td><td>ACO</td><td>GA</td></tr><tr><td rowspan="2">综合评价值</td><td>0.7850±</td><td>0.7841±</td><td>0.7844±</td><td>0.7838±</td></tr><tr><td>0.0004</td><td>0.0023</td><td>0.0019</td><td>0.0026</td></tr><tr><td rowspan="2">知识相似度</td><td>0.8210±</td><td>0.8201±</td><td>0.8205±</td><td>0.8199±</td></tr><tr><td>0.0002</td><td>0.0028</td><td>0.0022</td><td>0.0031</td></tr><tr><td rowspan="2">协同效应值</td><td>0.6530±</td><td>0.6528±</td><td>0.6529±</td><td>0.6527±</td></tr><tr><td>0.0003</td><td>0.0008</td><td>0.0006</td><td>0.0011</td></tr><tr><td rowspan="2">服务质量评价值</td><td>0.8809±</td><td>0.8792±</td><td>0.8798±</td><td>0.8788±</td></tr><tr><td>0.0011</td><td>0.0041</td><td>0.0035</td><td>0.0045</td></tr><tr><td rowspan="2">完成时间(s)</td><td>16.1±</td><td>20.3±</td><td>18.2±</td><td>21.9±</td></tr><tr><td>0.8911</td><td>1.4484</td><td>1.0996</td><td>1.7453</td></tr></table></body></html>

# 5 结束语

本文通过分析云环境下新产品开发团队组合优选全过程，针对团队组合优选问题，建立了包含知识相似度评价模型、协同效应评价模型和服务质量评价模型的综合评价模型；为了保证算法的求解效果和求解速度，本文引入了人工蜂群算法，并对其适应度函数和搜索方式加以改进。在团队组合优选模型构建过程中，本文既考虑团队自身研发实力，又考虑到团队间的协同效应，也考虑到任务的约束信息。此外，本文通过案例实验与分析，验证了本文的优选方法和模型在解决团队组合优选问题上可行性；通过算法对比，验证了改进算法处理本文模型的有效性。

本文在通过知识相似度来衡量团队与任务之间匹配度，衡量团队研发实力，后续需完善团队实力评价指标，更加精确衡量团队实力；此外，本文采用团队间两两信息交流模式，后续研究中可尝试多团队信息交流，让其更加符合实际。

# 参考文献：

[1]李伯虎，张霖，王时龙，等．云制造一面向服务的网络化制造新模[J]. 计算机集成制造系统，2010,16(1):1-8.(Li Bohu，Zhang lin，Wang Shilong,et al.Cloud manufacturing:a new service-oriented networked manufacturing model [J].Computer Integrated Manufacturing Systems, 2010,16 (1): 1-8. )

[2]刘敬，余隋怀，初建杰，等．设计云服务平台下网络团队成员优选决策 研究[J].计算机集成制造系统，2017,23(6):1205-1215.(Liu Jing,Yu Suihuai,Chu Jianjie,et al.Research on member optimal selection of network team[J].Computer Integrated Manufacturing Systems,2017,23 (6):1205-1215.)

[3]赵金辉，王学慧．基于服务质量的云制造服务双向匹配模型[J].计算 机集成制造系统，2016,22(1):104-112.(Zhao Jinhui，Wang Xuehui. Two-sided matching model of cloud service based on QoS in cloud manufacturing environment [J]. Computer Integrated Manufacturing

Systems,2016,22(1):104-112.)

[4] 陈友玲，阳玮琦，刘传彪，等．基于知识相似度和学习能力的产品设计 人员指派方法[J].计算机集成制造系统，2017，23(8):1700-1710. (Chen Youling,Yang Weiqi,Liu Chuanbiao,et al.Personnel assignment method of product design based on knowledge similarity and learning ability [J].Computer Integrated Manufacturing Systems,2O17,23(8): 1700-1710.)

[5]姜艳萍，潘恩，梁海明.考虑指标期望的新产品开发交叉功能团队成员 选择方法 [J].运筹与管理，2013,22(4):204-211.(Jiang Yanping,Pan En,Liang Haiming.Method for member selection of cross-functional teams in new product development considering index aspiration [J]. Operations Research And Management Science,2013,22 (4): 204-211.)

[6]王娟茹，赵嵩正．层次分析法和模糊优先规划法相结合选择虚拟团队 成员[J].工业工程,2007(6):105-108.(Wang Juanru,Zhao Songzheng On selection of partners using AHP and FPP in virtual team [J].Industrial Engineering Journal,2007(6):105-108.)

[7]LianyingZhang， XiangZhang.Multi-objectiveteamformation optimization for new product development [J].Computers & Industrial Engineering,2013,64: 804-811.

[8]冯博，樊治平．基于协同效应的知识创新团队伙伴选择方法[J].管理 学报,2012,9 (2):258-261.(Feng Bo,Fan Zhiping.A partner selection method for knowledge creation team based on collaborative effect [J]. Chinese Journal of Management,2012,9(2): 258-261.)

[9]Feng Bo,Jiang Zhongzhong,Fan Zhiping,et al.A method for member selection of cross-functional teams using the individual and collaborative performances [J].European Journal of Operational Research,2O1o,203: 652-661.

[10]徐廷．基于Simio 的产品设计过程重叠模式仿真优化研究[D].济南： 山东大学,2O16.(Xu Ting.Research on simulation and optimization of over lapping design process based on Simio [D]. Jinan: Shan dong University,2016.)

[11]陈友玲，兰桂花，梁佩馨．基于知识欧姆定律的上下游活动重叠时间估 算[J].计算机集成制造系统，2016,22(12):2759-2766.(Chen Youling, Lan Guihua,Liang Peixin.Estimation of overlapping time between upstream and downstream activities based on knowledge ohm’s law [J]. Computer Integrated Manufacturing Systems,2016,22(12): 2759-2766.)

[12]马文建，刘伟，李传昭．并行产品开发中设计活动间重叠与信息交流 [J].计算机集成制造系统,2008(4):630-636.(Ma Wenjian,Liu Wei,Li Chuanzhao. Overlapping and communication frequency between activities within concurrentproduct development[J].Computer Integrated Manufacturing Systems,2008 (4): 630-636.)

[13]吕炎杰，赵罡，于勇．基于模糊集理论和知识相似度的复杂产品设计任 务分配方法[J].计算机集成制造系统，2015，21(4):904-913.(Lyu Yanjie,Zhao Gang,Yu Yong. Task assignment method of complex product design based on fuzzy set theory and knowledge similarity [J]. Computer Integrated Manufacturing Systems,2015,21(4): 904-913.)

[14]李靖，张永安．基于ISM 的物流网络协同效应影响因素分析——以苏 宁电器为核心的物流网络为例[J].北京交通大学学报：社会科学版， 2011(4): 45-52.(Li Jing,Zhang Yongan.An analysis of the affecting factors of collaborative effect of the logistics networks:a case study of Suning’s core logistics networks [J]. Journal of Beijing Jiaotong University: Social Sciences Edition,2011(4):45-52.)

[15]任子武，王振华，孙立宁．基于改进人工蜂群算法的并联机器人正运动 学解[J]．机械工程学报，2013，49(13):48-55.(Ren Ziwu，Wang Zhenhua,Sun Lining.Forward kinematicssolution forparallel manipulators based on improved artificial bee colony algorithm [J]. Journal of Mechanical Engineering,2013,49 (13): 48-55.)

[16]Liang Yaosheng,Wan Zhongping,Fang Debin.An improved artificial bee colony algorithm for solving constrained optimization problems [J]. International Journal of Machine Learning and Cybernetics,2O17,3(8): 739-754.

[17]李彦苍，彭扬．基于信息熵的改进人工蜂群算法[J].控制与决策， 2015,30(6):1121-1125.(Li Yancang,Peng Yang. Improved artificial bee colony algorithm based on information entropy [J].Control and Decision, 2015,30 (6):1121-1125.)

[18]夏亚梅，程渤，陈俊亮，等．基于改进蚁群算法的服务组合优化[J]. 计算机学报，2012，35 (2):2270-2281.(Xia Yamei,Chen Bo,Chen Junliang,et al. Optimizing services composition based on improved ant colony algorithm [J].Chinese Journal of Computers，2012，35 (2): 2270-2281. )