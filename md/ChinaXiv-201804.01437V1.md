# 低碳背景下考虑批发价格契约供需网企业决策

房宏扬，陈荔(上海理工大学 管理学院，上海 200093)

摘要：在全球绿色低碳的视角下，构建高效、可循环的绿色供需体系，基于报贩模型针对低碳供需网系统进行研究。在低碳背景下分别建立不考虑碳排放、碳税、碳配额、碳配额与交易下的供需网批发价格契约模型，并运用 Stackelberg博弈进行求解，探讨不同的碳排放政策对低碳供需网契约协调以及收益的影响。通过模型求解验证了无论在何种政策下传统的批发价格契约均无法实现低碳供需网系统协调；且通过数值仿真分析了四种不同的碳减排政策下不同参数的变化对供需网系统的影响。研究发现：各方收益随着碳税价格的升高而降低；当企业的碳排放量超额时，收益随着碳配额的减少而减少；而碳配额与交易下，制造商的收益随着碳交易价格的增加呈现先增后降的趋势。

关键词：低碳供需网；碳减排；批发价格契约；Stackelberg 博弈 中图分类号：TP271.9 doi: 10.3969/j.issn.1001-3695.2017.12.0810

# SDN business decision-making considering wholesale price contract underlow carbon environment

Fang Hongyang, Chen Li (Business School,University ofShanghai for Science&Technology,Shanghai 2Ooo93,China)

Abstract: Fromtheperspectiveofaglobal greenandlow-carbon environment,aneficient greensupplyanddemandsystem is constructed; andthis paper studied alow-carbon supply and demand network system based on newsvendor model.Under the low-carbonbackground,LCSDNmodelwithwholesalepricecontractisestablishedandsolvedbyStackelberggameconsidering nocarbonemisson,carbontax,mandatorycarbonemisionscapacity,cap&tradeRegulation.Through numericalsimulation, it is verifiedthat the traditional wholesale pricecontractcannotachievethecordinationofLCSDNunderlowcarbon policy., itis foundthattheprofitsdecreaseas thecarbontaxpriceincreases.Whenthecarbonemissons ofenterprises exceedthequota ofcarbon,theprofitofmanufacturers decreases withthereductionofcarbonquotas.Inthecaseofcarbonquotasandtransactions, the optimal order quantity of retailers will increase as the price of carbon trading increases lower.

Key Words: low-carbonization SDN; carbon emisson reduction; wholesale price contract; Stackelberg game

# 0 引言

随着全球经济的快速发展及现代化工业生产规模的扩大，人类对自然资源的利用达到了一个前所未有的地步，自然环境的破坏程度也日益提升，以低消耗、低污染和可持续发展为理念的低碳经济成为关注的重点，同时也对供需网管理的研究提出了挑战。多功能开放型企业供需网（supply anddemandnetwork ofenterpriseswithmulti-functionand openingcharacteristic,SDN）是由徐福缘教授于2007年提出的以全球资源获取、全球制造、全球销售和提高企业综合能力为目标，相关企业之间由于供需流的交互作用而形成的多功能开放式的供需一体化动态网络模式[1]。

当今世界，大多数企业过于注重经济效益，盲目追求利润最大化，企业是最重要的社会主体之一，在某种程度上，应充分考虑其给环境带来的影响。随着环境问题的出现以及国家相关政策的提出，低碳化的发展受到学术界和工业界的密切关注。Dekker等[2结合了运筹学及运营管理相关理论研究了在低碳经济的背景下绿色物流的设计、规划与控制。Mutingi 等人[3]探索了现有关于绿色供应链和环境管理的相关研究，提出了绿色绩效管理体系的结构化方法。Barbarossa等人[4]分别在绿色和非绿色消费者之间探讨了环保产品在采购模式上的显著差异，并对其具体前因进行了具体分析。He等人[5]研究了多样化的碳排放规定在供应链中的应用以及通过何种方式找到供应链运作的协调机制和最优策略。因此，论文在绿色低碳背景下，参照供需网及绿色供应链[6-9]的相关文献及理论，首次提出低碳供需网的概念。低碳供需网（low-carbonSDN，LCSDN）是一种创新型动态网络模式，以最小消耗、最低排放、最优绩效为原则，充分发挥市场的导向作用，引导企业朝向低碳化发展，实现整体产业的绿色升级和可持续发展。常见政府制定的低碳环境保护政策主要有三种：碳税机制、碳配额机制和碳配额与交易机制。

SDN系统是由不同决策主体组成的复杂网络，他们之间是相互独立，并在个体理性的基础上以自身利益最大化来进行决策。由于系统中存在"双重边际化"的问题，使得SDN系统的整体效率降低，不能达到帕累托最优[10]。因此，在低碳化的背景下，讨论SDN系统的契约协调和企业决策问题是未来研究的一个重要方向[1]。在查阅相关文献的基础上，对过往 SDN 管理与企业决策的相关研究进行了总结：何建佳[2]在非对称信息的背景下，引入收入共享契约，探讨了两层SDN系统协调和效率的问题。胡伟[13]建立了SDN 两节点之间完全合作与非合作的决策模型。何伟[I4则在随机需求情形下，针对SDN系统中的一个节点，研究了零售商主导的SDN契约协调问题。鲁力等[15]在不同碳排放政策的基础上，引入回购合同，研究了采取减排措施后的供应链协调问题。刘名武等[16]在碳交易制度下，建立了受消费者低碳偏好影响的供应商主导投资减排的低碳供应链协调模型。刘超[17]在政府低碳减排价格补贴的政策下，研究了由供应商主导的两级供应链企业决策问题。代应[18]则在线性市场需求的情况下，引入消费者低碳偏好，研究了零售商利他偏好因素对批发价格契约的相关决策及协调的影响。支帮东等[19]将经济订货批量库存模型引入到供应链成员企业碳减排博弈模型中,并通过计算分析得出了最优碳减排策略。张玉忠[20]在碳税政策下研究了由一个供应商和一个零售组成的二级供应链协调问题。

通过上述文献综述可知，传统的大部分LCSDN协调研究仅在单一碳排放政策下进行研究，缺少在不同政策下的LCSDN的对比研究。由于不同国家及地区采取的碳减排政策不同，因此，为了更好的分析不同的碳减排政策对企业减排决策的影响，本文基于碳税、碳配额、碳配额与交易三种政府碳减排政策下，并且对比在不考虑碳排放政策下，引入批发价格契约，探讨不同的碳排放政策对制造商的最优决策以及LCSDN系统各方收益的影响。

# 1 问题描述与符号设定

在低碳的背景下，研究不同碳排放政策下的LCSDN系统协调问题，为了便于描述，首先对模型所涉及的参数符号进行如下说明，如表1所示，其中 $\mathbf { i } = 1 , 2 , 3 , 4$ ；1代表不考虑碳排放政策；2代表碳税；3代表碳配额；4代表碳配额与交易。

为了便于建立数学模型和进一步分析，现作出如下假设：

a）考虑由一个制造商和一个零售商组成的单一产品两层LCSDN系统，该产品为短周期销售产品，在一定时间内产品的销售价格是不变的，且LCSDN系统的碳排放绝大部分来自于制造商的生产制造过程，不考虑零售商的碳排放。制造商每单位产品的生产制造成本 $\mathbf { c } _ { 1 }$ 、零售商批发价格 $\mathbf { w } _ { i }$ 及零售价格 ${ \tt p } _ { i }$ 之间满足条件 $\mathbf { p } _ { i } > \mathbf { w } _ { i } > \mathbf { C } _ { 1 } + \bigl ( 1 - \xi \bigr ) t e > \mathbf { C } _ { 1 } > 0$ ，即零售商与制造商均有利可图。

表1模型参数设定  

<html><body><table><tr><td>变量</td><td>含义</td><td>变量</td><td>含义</td></tr><tr><td>C</td><td>制造商生产制造成本</td><td>t</td><td>碳税价格</td></tr><tr><td>C2</td><td>单位碳产品的交易价格</td><td>e</td><td>单位产品的碳排放量</td></tr><tr><td>C</td><td>制造商减排研发成本</td><td>E</td><td>免费碳排放额度</td></tr><tr><td>Wi</td><td>制造商的批发价格</td><td>qi</td><td>零售商订货量</td></tr><tr><td>Pi</td><td>零售商的零售价格</td><td>qri</td><td>分散决策最优订货量</td></tr><tr><td>g</td><td>超过碳配额缴纳的罚款</td><td>q</td><td>集中决策最优订货量</td></tr><tr><td>a</td><td>市场容量</td><td>w</td><td>最优批发价格</td></tr><tr><td>b</td><td>消费者的价格敏感系数</td><td>S</td><td>单位产品的碳减排率</td></tr><tr><td>入</td><td>消费者对低碳敏感系数</td><td>π</td><td>LCSDN系统利润函数</td></tr><tr><td>Si</td><td>单位产品的碳减排率</td><td>π</td><td>零售商的利润函数</td></tr><tr><td>h</td><td>投资减排成本系数</td><td>πmi</td><td>制造商的利润函数</td></tr></table></body></html>

b）随着低碳经济的发展，消费者低碳意识逐渐增强，产品的低碳属性也会影响消费者的心理和行为选择，消费者对产品的低碳偏好也会表现的越来越明显。为了模型建立与求解方便，论文在此引用鲁力[15]所引入的线性市场需求函数，假设消费者的市场需求是受产品价格以及消费者低碳偏好影响的，则市场需求函数可表示为产品价格和碳减排率的线性函数，即${ \mathfrak { q } } _ { \mathrm { i } } = a - b { \mathfrak { p } } _ { i } + \lambda \xi _ { i }$ 。并假设消费者对产品的需求量与零售商向制造商订购商品的数量相等，不考虑缺货及残值。

c）在政府实施低碳减排的背景下，假设制造商的投资减排研发成本C与碳减排率 $\xi$ 成二次关系，即 $\displaystyle \mathbf { C } = \frac { 1 } { 2 } \mathbf { h } \boldsymbol { \xi } ^ { 2 }$ 。在不考虑政府碳排放限制的情况下，假设单位产品的碳减排率为 $\xi$ 为常量。在碳税机制下，每单位碳产品需要缴纳的碳税金额为t。在碳配额政策下，政府为了规制制造商的排放行为，在期初会根据产业性质不同以及上一期的碳排放量免费分配一定数量的碳配额E，假设E且为外生变量，当制造商的碳排放量超出碳排放额度时，政府会收取每单位碳排放量罚款g。在碳配额与交易政策下，政府给制造商的免费碳配额为E，当制造商碳排放量不足或剩余时，可通过碳交易市场进行碳配额买卖。

d)假设在一个订货周期内，LCSDN系统的运作过程均为两阶段博弈过程：制造商首先确定给零售商的批发价格 $\mathbf { w } _ { i }$ 和碳减排率 $\xi _ { i }$ 使自身利益最大；然后零售商根据制造商所提供的批发价格、碳减排率及市场需求预测来制定其最优订货量。因此，LCSDN系统的博弈过程为典型的 Stackelberg 博弈，在整个博弈过程中制造商占据主导地位，可以采用逆向归纳法求解该博弈的子博弈精炼纳什均衡。若想实现LCSDN 协调需满足${ \bf q } _ { \mathrm { n } } ^ { * } = { \bf q } _ { \mathrm { i } } ^ { * }$ ，若无法满足，则无法实现LCSDN系统的协调。

e）假设LCSDN系统中的制造商和零售商均为风险中性和完全理性的，不考虑行为因素影响，且LCSDN系统中上下游企业相互之间信息是共享且对称的，相互知晓方便作出订购决策，并且基于自身利润最大化的原则进行决策。

# 2 模型构建与求解

# 2.1不考虑碳排放下的SDN批发价格契约模型

在低碳背景下，首先建立不受政府碳排放政策约束的基础LCSDN 模型，零售商企业将按照利润最大化原则向制造商购买产品。产品的需求量为价格与碳减排率的线性函数，其表达式为

$$
\begin{array} { r } { \ P _ { 1 } = a - b \mathsf { p } _ { 1 } + \lambda \xi _ { 1 } } \end{array}
$$

则产品的价格可表示为需求量与碳排放率的函数：

$$
{ \mathfrak { p } } _ { 1 } = { \frac { 1 } { b } } { \big ( } a + \lambda \xi _ { 1 } - \mathbf { q } _ { 1 } { \big ) }
$$

零售商的收益为其实际的销售收入与进货成本的差值，当然受市场各种因素的影响，销售量要根据当前情况而定，为了保证不出现缺货或库存剩余的情况，零售商一般都会根据历史的进货量及销售量进行评估，并向制造商订购一定的产品。此时，零售商的利润 $\pi _ { \mathrm { r 1 } }$ 可用公式表示为

$$
\boldsymbol { \pi } _ { \mathrm { r 1 } } = \left( \mathbf { p } _ { 1 } - \mathbf { w } _ { 1 } \right) \mathbf { q } _ { 1 } = \left[ \frac { 1 } { \mathbf { b } } \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 1 } - \mathbf { q } _ { 1 } \big ) - \mathbf { w } _ { 1 } \right] \mathbf { q } _ { 1 }
$$

制造商的收益要根据零售商的订货量和单位产品的收益来确定，单位产品的收益为出场价格减去其制造成本，则制造商的利润 $\pi _ { \mathrm { m l } }$ 为

$$
\boldsymbol { \pi } _ { \mathrm { m } 1 } = \Big ( \mathbf { w } _ { 1 } - \mathbf { c } _ { 1 } \Big ) \mathbf { q } _ { 1 } - \frac { 1 } { 2 } \mathbf { h } \xi _ { 1 } ^ { 2 }
$$

LCSDN系统的利润 $\pi _ { 1 } = \pi _ { \mathrm { r 1 } } + \pi _ { \mathrm { m l } }$ 可表示为

$$
\boldsymbol { \pi } _ { 1 } = \left[ \frac { 1 } { \mathsf { b } } \big ( \mathrm { a } + \lambda \boldsymbol { \xi } _ { 1 } - \mathrm { q } _ { 1 } \big ) - \mathrm { c } _ { 1 } \right] \mathbf { q } _ { 1 } - \frac { 1 } { 2 } \mathrm { h } \boldsymbol { \xi } _ { 1 } ^ { 2 }
$$

命题1在不考虑碳排放政策下，传统的批发价合同无法实现LCSDN系统的协调，且分散决策的零售商最优订货量始终大于集中决策中LCSDN系统的最优订货量。

证明根据上述可知LCSDN 系统的协调是在两种情况下的最优订货量应满足 ${ \bf q } _ { \mathrm { r } 1 } ^ { * } = { \bf q } _ { 1 } ^ { * }$ ，首先计算分散决策下零售商的最优订货量，此时LCSDN系统的制造商与零售商均以个人收益最大化作为决策目标，采用Stackelberg博弈模型的逆向归纳法对该模型进行求解，首先零售商将产品的批发价格 $\mathbf { W } _ { 1 }$ 作为已知量，考虑零售商为了获取最大收益，确定使利润 $\pi _ { \mathrm { r 1 } }$ 达到最大值时的最优订货量，则 $\pi _ { \mathrm { r l } }$ 对 ${ \sf q } _ { 1 }$ 分别求一阶、二阶偏导可得：

$$
\frac { \partial \pi _ { \mathrm { r 1 } } } { \partial { \bf q } _ { 1 } } = \frac { 1 } { b } \big ( a + \lambda \xi _ { 1 } - 2 { \bf q } _ { 1 } \big ) - { \bf w } _ { 1 }
$$

$$
\frac { \partial ^ { 2 } \pi _ { \mathrm { r 1 } } } { \partial { \bf q } _ { 1 } ^ { 2 } } = - \frac { 2 } { \bf b } < 0
$$

由式（7）可知 $\pi _ { \mathrm { r l } }$ 是关于 ${ \bf q } _ { 1 }$ 的严格凸函数，即对于任意$\pi _ { \mathrm { r l } } > 0$ ，存在唯一的最优订货量。则在不考虑零售商和制造商具有公平偏好的情况下，求解 =0可得零售商最优订货量

$\boldsymbol { \mathbf { q } } _ { r 1 } ^ { * }$ 存在且唯一，且 $\boldsymbol { \mathbf { q } } _ { r 1 } ^ { * }$ 满足：

$$
\mathbf { q } _ { \mathrm { r 1 } } ^ { * } = \frac { 1 } { 2 } \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 1 } - \mathbf { b w } _ { 1 } \big )
$$

根据Stackelberg博弈的逆向求解法，将 $\boldsymbol { \mathbf { q } } _ { r 1 } ^ { * }$ 代入式(4)中，$\pi _ { \mathrm { m l } }$ 表示为：

$$
\pi _ { \mathrm { m l } } = \frac { 1 } { 2 } \big ( { \mathbf w } _ { 1 } - { \mathbf c } _ { 1 } \big ) \big ( { \mathbf a } + \lambda { \boldsymbol \xi } _ { 1 } - { \mathbf b } { \mathbf w } _ { 1 } \big ) - \frac { 1 } { 2 } { \mathbf h } { \boldsymbol \xi } _ { 1 } ^ { 2 }
$$

求解使制造商利润最大化的批发价格 $w _ { 1 } ^ { * }$ ，通过 $\pi _ { \mathrm { m l } }$ 分别对$\mathbf { W } _ { 1 }$ 求一阶、二阶偏导可得：

$$
\frac { \partial \pi _ { \mathrm { m 1 } } } { \partial \mathbf { w } _ { 1 } } = \frac { 1 } { 2 } \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 1 } - \mathbf { b w } _ { 1 } \big ) - \frac { \mathbf { b } } { 2 } \big ( \mathbf { w } _ { 1 } - \mathbf { c } _ { 1 } \big )
$$

$$
\frac { \partial ^ { 2 } \pi _ { \mathrm { m l } } } { \partial \mathbf { w } _ { 1 } ^ { 2 } } = - \mathbf { b } < 0
$$

由式（11）可知 $\pi _ { \mathrm { m l } }$ 是关于 $\mathbf { W } _ { 1 }$ 的严格凸函数，即对于任意$\pi _ { \mathrm { m l } } > 0$ ，存在唯一的最优批发价格。通过求解 πml=0可得零aw1售商最优订货量 $\boldsymbol { w } _ { r 1 } ^ { * }$ 存在且唯一且满足：

$$
\mathbf { w } _ { { \mathrm { r } } 1 } ^ { * } = { \frac { \mathbf { a } + \lambda \boldsymbol { \xi } _ { 1 } - \mathbf { b } \mathbf { c } _ { 1 } } { 2 \mathbf { b } } }
$$

在集中决策下，将整个LCSDN系统看成一个整体，即各个企业不是为了追求自身利益最大化，而是着眼于整个LCSDN系统整体利润的最大化。根据Stackelberg博弈的逆向求解法，考虑为了使LCSDN系统获取最大收益，需要确定使利润 $\pi _ { \mathfrak { i } }$ 达到最大值时的最优订货量 $\mathbf { q } _ { 1 } ^ { * }$ ，根据式(4)，求解 $\pi _ { 1 }$ 对 ${ \bf q } _ { 1 }$ 的一阶、二阶偏导可得：

$$
\frac { \hat { o } \pi _ { 1 } } { \hat { o } { \bf q } _ { 1 } } = \frac { 1 } { b } \big ( a + \lambda \xi _ { 1 } - 2 { \bf q } _ { 1 } \big ) - { \bf c } _ { 1 }
$$

$$
\frac { \hat { \sigma } ^ { 2 } \pi _ { 1 } } { \hat { \sigma } { \bf q } _ { 1 } ^ { 2 } } = - \frac { 2 } { \bf b } < 0
$$

由式（14）可知 $\pi _ { 1 }$ 是关于 ${ \bf q } _ { 1 }$ 的严格凸函数，即对于任意$\pi _ { \mathrm { 1 } } > 0$ ，存在唯一的最优订货量 $\mathbf { q } _ { 1 } ^ { * }$ 。则在不考虑零售商和制造商具有公平偏好的情况下，通过求解可得零售商最优订货量 $\mathbf { q } _ { 1 } ^ { * }$ 存在且唯一，满足：

$$
\mathbf { q } _ { 1 } ^ { * } = \frac { 1 } { 2 } \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 1 } - \mathbf { b } \mathbf { c } _ { 1 } \big )
$$

比较式（8)和（15）可知，由于 $\mathbf { W } _ { 1 } - \mathbf { c } _ { 1 } > 0$ ，所以 $\mathbf { q } _ { \mathrm { r } 1 } ^ { * } > \mathbf { q } _ { 1 } ^ { * }$ 。说明在无碳排放约束的情况下，分散决策的零售商最优订货量始终大于集中决策中LCSDN系统的最优订货量。因此，传统的无碳排放约束的批发价合同无法实现LCSDN系统的协调。

# 2.2碳税下SDN批发价格契约协调模型

由于制造企业的碳排放会对环境造成危害，不利于人类的健康，政府为了控制企业的碳排放，会对企业按照碳排放量进行碳税的征收。为了便于研究及模型创建，假设碳税与单位产品碳排放呈线性关系，线性关系易构建模型，且具有代表性，也是低碳研究中使用普遍的模型。则制造商每生产单位产品商品都需要缴纳碳税te，对制造商和LCSDN系统而言，均增加了运营成本。此时，零售商、制造商以及LCSDN系统的利润函数可表示为

$$
\boldsymbol { \pi } _ { \mathrm { r } 2 } = \left( \mathbf { p } _ { 2 } - \mathbf { w } _ { 2 } \right) \mathbf { q } _ { 2 } = \left[ \frac { 1 } { \mathbf { b } } \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 2 } - \mathbf { q } _ { 2 } \big ) - \mathbf { w } _ { 2 } \right] \mathbf { q } _ { 2 }
$$

$$
\boldsymbol { \pi } _ { \mathrm { m } 2 } = \Big [ \mathbf { W } _ { 2 } - \mathbf { c } _ { 1 } - \Big ( 1 - \boldsymbol { \xi } _ { 2 } \Big ) \mathrm { e t } \Big ] \mathbf { q } _ { 2 } - \frac { 1 } { 2 } \mathbf { h } \boldsymbol { \xi } _ { 2 } ^ { 2 }
$$

$$
\boldsymbol { \pi } _ { 2 } = \left[ \frac { 1 } { \mathsf { b } } \big ( \mathrm { a } + \lambda \boldsymbol { \xi } _ { 2 } - \mathrm { q } _ { 2 } \big ) - \mathrm { c } _ { 1 } - \big ( 1 - \xi _ { 2 } \big ) \mathrm { e t } \right] \mathbf { q } _ { 2 } - \frac { 1 } { 2 } \mathrm { h } \boldsymbol { \xi } _ { 2 } ^ { 2 }
$$

命题2碳税情形下，批发价合同仍无法实现LCSDN 系统的协调，且随着碳税价格的升高，制造商的利润会随之降低。

证明在分散决策下，制造商和零售商都根据自身利益最大化进行决策，对式（16）求 ${ \bf q } _ { 2 }$ 的倒数，同式（6）（7)，可得分散决策时，零售商的最优订货的为

$$
\mathbf { q } _ { \mathrm { r } 2 } ^ { * } = \frac { 1 } { 2 } \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 2 } - \mathbf { b w } _ { 2 } \big )
$$

根据Stackelberg 博弈的逆向求解法，将 $\mathbf { q } _ { \mathrm { r } 2 } ^ { * }$ 代入式（19），$\pi _ { { \mathrm m } 2 }$ 可表示为

$$
\pi _ { \mathrm { m } 2 } = \frac { \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 2 } - \mathbf { b w } _ { 2 } \big ) } { 2 } \Big [ \mathbf { w } _ { 2 } - \mathbf { c } _ { 1 } - \big ( 1 - \boldsymbol { \xi } _ { 2 } \big ) \mathrm { e t } \Big ] - \frac { 1 } { 2 } \mathbf { h } \boldsymbol { \xi } _ { 2 } ^ { 2 }
$$

对式（20）分别对 $\mathbf { W } _ { 2 }$ 求一阶、二阶偏导可得

$$
\frac { \hat { \sigma } \pi _ { \mathrm { m 2 } } } { \hat { \sigma } \mathbf { w } _ { 2 } } = \frac { \left( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 2 } - \mathbf { b w } _ { 2 } \right) } { 2 } - \frac { \mathbf { b } } { 2 } \Big [ \mathbf { w } _ { 2 } - \mathbf { c } _ { 1 } - \left( 1 - \boldsymbol { \xi } _ { 2 } \right) \mathbf { e t } \Big ]
$$

$$
\frac { \hat { \sigma } ^ { 2 } \pi _ { \mathrm { m } 2 } } { \hat { \sigma } \mathrm { w } _ { 2 } ^ { 2 } } = - \mathbf { b } < 0
$$

可知， $\pi _ { _ { \mathrm { m } 2 } }$ 是关于 $\mathbf { W } _ { 2 }$ 的严格凸函数，即对于任意 $\pi _ { \mathrm { m } 2 } > 0$ ，存在唯一的最优批发价格量 $\mathbf { W } _ { \mathrm { r } 2 } ^ { * }$ 满足：

$$
\mathbf { W } _ { \mathrm { r } 2 } ^ { * } = \frac { \mathbf { a } + \mathbf { b } \mathbf { c } _ { 1 } + \lambda \boldsymbol { \xi } _ { 2 } + \left( 1 - \boldsymbol { \xi } _ { 2 } \right) \mathbf { b } \mathrm { e t } } { 2 \mathbf { b } }
$$

由式（23）可知，因 $1 - \xi _ { 2 } > 0$ ，则制造商制定的批发价格与碳税之间呈线性且为正相关关系，当消费者对价格的敏感性以及制造商的碳减排量保持不变时，政府对于制造商征收的碳税越高，制造商的成本越高，则会通过提高批发价格来获取更多的利润。因此，政府在制定碳税的同时，要考虑价格的合理性。再将制造商的利润函数 $\pi _ { { \mathrm m } 2 }$ 对碳减排量 $\boldsymbol { \xi } _ { 2 }$ 求导可得：

$$
\frac { \hat { \sigma } \pi _ { \mathrm { m 2 } } } { \hat { \sigma } \xi _ { 2 } } = \frac { 1 } { 2 } \mathrm { e t } \left( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 2 } - \mathbf { b w } _ { 2 } \right) + \frac { \lambda } { 2 } \Big [ \mathbf { w } _ { 2 } - \mathbf { c } _ { 1 } - \left( 1 - \xi _ { 2 } \right) \mathrm { e t } \Big ] - \mathbf { h } \xi _ { 2 }
$$

经计算，其Hessian 矩阵为

$$
\mathbf { H } = \left[ \begin{array} { c c } { \hat { \frac { \partial } { \partial \mathbf { w } _ { 2 } } } \mathbf { \bar { \phi } } _ { \hat { \partial } \mathbf { w } _ { 2 } } } & { \hat { \frac { \partial } { \partial \mathbf { w } _ { 2 } \partial \boldsymbol { \xi } _ { 2 } } } } \\ { \hat { \frac { \partial } { \partial \mathbf { w } _ { 2 } \partial \boldsymbol { \xi } _ { 2 } } } } & { \hat { \frac { \partial } { \partial \boldsymbol { \xi } _ { 2 } ^ { 2 } } } } \end{array} \right] = \left[ \begin{array} { c c } { \mathbf { \bar { \phi } } - \mathbf { b } } & { \frac { 1 } { 2 } \big ( \lambda - \mathbf { b e t } \big ) } \\ { \frac { 1 } { 2 } \big ( \lambda - \mathbf { b e t } \big ) } & { \mathrm { e t } \lambda - \mathbf { h } } \end{array} \right]
$$

由式（23）计算可得，当 $\mathbf { b h } - \frac { 1 } { 4 } \big ( \lambda + \mathbf { b e t } \big ) ^ { 2 } < 0$ (λ+bet)²<0时，Hessian矩阵为负定矩阵，制造商的利润函数 $\pi _ { { \mathrm m } 2 }$ 存在最大值，令式（21)（22）为零，求解可得

$$
\xi _ { \mathrm { r } 2 } ^ { * } = \frac { \big ( \lambda + \mathrm { e t b } \big ) \Big [ \mathrm { a } - \mathrm { b } \big ( \mathrm { c } _ { 1 } + \mathrm { e t } \big ) \Big ] } { 4 \mathrm { b h } - \big ( \lambda + \mathrm { e t b } \big ) ^ { 2 } }
$$

在集中决策情况下，分别计算 ${ \frac { \hat { \sigma } \pi _ { 2 } } { \hat { \sigma } \mathbf { q } _ { 2 } } } , \ { \frac { \hat { \sigma } ^ { 2 } \pi _ { 2 } } { \hat { \sigma } \mathbf { q } _ { 2 } ^ { 2 } } }$ 可得：

$$
\frac { \partial \pi _ { 2 } } { \partial { \bf q } _ { 2 } } = \frac { 1 } { \bf b } \big ( { \bf a } + \lambda \xi _ { 2 } - 2 { \bf q } _ { 2 } \big ) - { \bf c } _ { 1 } - \big ( 1 - \xi _ { 2 } \big ) \mathrm { e t }
$$

$$
\frac { \hat { \sigma } ^ { 2 } \pi _ { 2 } } { \hat { \sigma } \mathbf { q } _ { 2 } ^ { 2 } } = - \frac { 2 } { \mathbf { b } } < 0
$$

经计算可知， $\pi _ { 2 }$ 为 $\mathbf { q } _ { 2 }$ 的凸函数，存在唯一最大值满足：

$$
\mathbf { q } _ { 2 } ^ { * } = \frac { 1 } { 2 } \mathopen { } \mathclose \bgroup \left[ \mathbf { a } + \lambda \xi _ { 2 } - \mathbf { b } \mathbf { c } _ { 1 } - \left( 1 - \xi _ { 2 } \right) \mathbf { e } \mathbf { b } \mathbf { t } \aftergroup \egroup \right]
$$

比较 $\mathbf { q } _ { \mathrm { r } 2 } ^ { * }$ 与 $\mathbf { q } _ { 2 } ^ { * }$ 可知，由于 $\mathbf { w } _ { 2 } > \mathbf { C } _ { 1 } + \left( 1 - \xi _ { 2 } \right) \mathbf { t }$ e，因此由${ \bf q } _ { 1 } ^ { * } < { \bf q } _ { 2 } ^ { * }$ ，即在碳税政策的限制下，分散决策时零售商的最优利润始终小于集中决策下的最优利润，且该情形下，批发价合同仍无法实现LCSDN系统的协调。

# 2.3碳配额下SDN批发价格契约协调模型

碳配额是指企业需按规定必须完成的碳减排指标。碳配额交易的实质，就是在一个原本是自由排放的领域，通过对排放上限的封顶，从而把不受约束的排放权，人为地改造成一种稀缺的配额的过程。当碳排放配额不足或剩余时，企业不可去碳交易市场购买或销售碳排放额，当碳排放量超过政府所规定的配额时，企业需按照所超出的部分交付一定的罚款金额。因此，碳配额政策对于企业而言也是一种强制性约束政策。

在接下来的部分，将分两种情况讨论：一种情况为制造商的碳排放量小于政府规定的碳配额，另外一种情况为制造商的碳排放量大于政府规定的碳配额。由于仅考虑制造商在生产制造过程中的碳排放，因此不论在何种情况下，零售商的利润函数是不变的：

$$
\boldsymbol { \pi } _ { \mathrm { r 3 } } = \left( \mathbf { p } _ { 3 } - \mathbf { w } _ { 3 } \right) \mathbf { q } _ { 3 } = \left[ \frac { 1 } { b } \big ( a + \lambda \xi _ { 3 } - \mathbf { q } _ { 3 } \big ) - \mathbf { w } _ { 3 } \right] \mathbf { q } _ { 3 }
$$

a)当碳排放配额剩余时，即 $E - \big ( 1 - \xi _ { 3 } \big ) e \mathbf { q } _ { 3 } \geq 0$ ，制造商不需要交罚款，此时制造商与LCSDN系统的利润分别为

$$
\boldsymbol { \pi } _ { \mathrm { m } 3 } = \big ( \mathbf { w } _ { 3 } - \mathbf { c } _ { 1 } \big ) \mathbf { q } _ { 3 } - \frac { 1 } { 2 } h \xi _ { 3 } ^ { 2 }
$$

$$
\boldsymbol { \pi } _ { 3 } = \left[ \frac { 1 } { b } \big ( a + \lambda \xi _ { 3 } - { \bf q } _ { 3 } \big ) - { \bf c } _ { 1 } \right] { \bf q } _ { 3 } - \frac { 1 } { 2 } h \xi _ { 3 } ^ { 2 }
$$

b)当 $E - \big ( 1 - \xi _ { 3 } \big ) e \mathbf { q } _ { 3 } < 0$ 时，制造商需要给超出碳配额的部分提交一定的罚金，此时制造商利润 $\dot { \pi } _ { \mathrm { m } 3 }$ 与LCSDN 系统的利润 $\dot { \pi } _ { 3 }$ 分别为：

$$
\overset { \triangledown } { \pi _ { \mathrm { m } 3 } } = \left( \mathbf { w } _ { 3 } - \mathbf { c } _ { 1 } \right) \mathbf { q } _ { 3 } - g \left[ \left( 1 - \xi _ { 3 } \right) e \mathbf { q } _ { 3 } - E \right] - \frac { 1 } { 2 } h \xi _ { 3 } ^ { 2 }
$$

$$
\begin{array} { c } { { \displaystyle { \dot { \pi } _ { 3 } = \left[ \frac { 1 } { b } \big ( a + \lambda \xi _ { 3 } - { \bf q } _ { 3 } \big ) - c _ { 1 } \right] { \bf q } _ { 3 } - } } } \\ { { \displaystyle { g \left[ \big ( 1 - \xi _ { 3 } \big ) e { \bf q } _ { 3 } - E \right] - \frac { 1 } { 2 } h \xi _ { 3 } ^ { 2 } } } } \end{array}
$$

命题3碳配额政策下，当企业的碳排放量小于碳配额时，批发价合同无法实现LCSDN系统的协调，制造商的最优订货量和最大期望利润不变，都等于无碳排放约束情形的最优订货量和最大期望利润。

证明在分散决策下，当 $E - \big ( 1 - \xi _ { 3 } \big ) e \mathbf { q } _ { 3 } \geq 0$ 时，制造商和零售商都根据自身利益最大化进行决策，该问题转换为线性规划问题。对式（16）求 ${ \bf q } _ { 2 }$ 的偏导，同式（6）（7)，可得分散决策时，零售商的最优订货量为

$$
\mathbf { q } _ { r 3 } = \frac { 1 } { 2 } \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 3 } - \mathbf { b w } _ { 3 } \big )
$$

根据Stackelberg博弈的逆向求解法，将 ${ \bf q } _ { \mathrm { r 3 } } ^ { * }$ 代入式(31)中，$\pi _ { \mathrm { m } 3 }$ 表示为

$$
\pi _ { \mathrm { m } 3 } = \frac { 1 } { 2 } \big ( \mathbf { w } _ { 3 } - \mathbf { c } _ { 1 } \big ) \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 3 } - \mathbf { b } \mathbf { w } _ { 3 } \big ) - \frac { 1 } { 2 } h \xi _ { 3 } ^ { 2 }
$$

对式（36）分别求 $\pi _ { \mathrm { m } 3 }$ 对 $\mathbf { W } _ { 3 }$ 的一阶、二阶偏导可得

$$
\frac { \hat { \sigma } \pi _ { \mathrm { m 3 } } } { \hat { \sigma } \mathrm { w } _ { 3 } } = \frac { 1 } { 2 } \big ( \mathrm { a } + \lambda \xi _ { 3 } - \mathrm { b w } _ { 3 } \big ) - \frac { \mathrm { b } } { 2 } \big ( \mathrm { w } _ { 3 } - \mathrm { c } _ { 1 } \big )
$$

$$
\frac { \hat { \sigma } ^ { 2 } \pi _ { \mathrm { m } 3 } } { \hat { \sigma } \mathrm { w } _ { 3 } ^ { 2 } } = - \mathbf { b } < 0
$$

经计算，可求得如下 ${ \bf W } _ { 3 }$ 关于的 $\boldsymbol { \xi } _ { 3 }$ 的表达式：

$$
\mathbf { w } _ { r 3 } ^ { * } = \frac { a + b \mathbf { c } _ { 1 } + \lambda \boldsymbol { \xi } _ { 3 } } { 2 b }
$$

将所得 $\mathbf { W } _ { r 3 } ^ { * }$ 关于的 $\boldsymbol { \xi } _ { 3 }$ 的表达式代入（36）中，此时的 $\pi _ { \mathrm { m } 3 }$ 可表示为

$$
\pi _ { \mathrm { m 3 } } = \frac { 1 } { 8 b } \big ( { \mathrm { a } + \lambda \xi _ { 3 } - b { \mathrm { c } _ { 1 } } \big ) ^ { 2 } - \frac { 1 } { 2 } h \xi _ { 3 } ^ { 2 } \mathrm { : } }
$$

对式（36）分别求 $\pi _ { \mathrm { m } 3 }$ 对 $\boldsymbol { \xi } _ { 3 }$ 的偏导可得：

$$
\frac { \hat { \sigma } \pi _ { \mathrm { m 3 } } } { \hat { \sigma } \xi _ { 3 } } = \frac { \lambda } { 4 \mathrm { b } } \big ( \mathrm { a } + \lambda \xi _ { 3 } - b \mathrm { c } _ { 1 } \big ) - h \xi _ { 3 }
$$

$$
\frac { \hat { \sigma } ^ { 2 } \pi _ { \mathrm { m 3 } } } { \hat { \sigma } \xi _ { 3 } ^ { 2 } } = \frac { \lambda ^ { 2 } } { 4 { \bf b } } - { \bf h }
$$

当且仅当 $\lambda ^ { 2 } - 4 \mathrm { b h } < 0$ 时，制造商的利润函数 $\pi _ { \mathrm { m } 3 }$ 存在最大值，令式（41）等于0，通过求解可得制造商的碳排放量小于政府规定的碳配额情况下，最优的碳排放量为

$$
\xi _ { r 3 } ^ { * } = \frac { \lambda \big ( \mathrm { a } - b \mathrm { c } _ { 1 } \big ) } { 4 b h - { \lambda } ^ { 2 } }
$$

由于 $\pi _ { \mathrm { m } 3 }$ 为 ${ \sf q } _ { 3 }$ 的凸函数，当 ${ \bf q } _ { r 3 } > \frac { E } { \left( 1 - \xi _ { 3 } \right) e }$ 时，此时最优订货量应为 $\frac { E } { \left( 1 - \xi _ { 3 } \right) e }$ 当 ${ \bf q } _ { r 3 } \le \frac { E } { \left( 1 - \xi _ { 3 } \right) e }$ 时，此时的最优解 ${ \bf q } _ { r 3 } = { \bf q } _ { \mathrm { r } 3 } ^ { * }$ 。而在集中决策下，当制造商的碳排放量不超过政府规定的碳配额时，LCSDN系统的利润及其所满足的约束条件可表示为

$$
\operatorname* { m a x } \pi _ { 3 } = \left[ \frac { 1 } { b } \big ( a + \lambda \xi _ { 3 } - \mathbf { q } _ { 3 } \big ) - \mathbf { c } _ { 1 } \right] \mathbf { q } _ { 3 } - \frac { 1 } { 2 } h \xi _ { 3 } ^ { 2 }
$$

s.t.

$$
E - \big ( 1 - \xi _ { 3 } \big ) e \mathbf { q } _ { 3 } \geq 0
$$

式（45）说明制造商的碳排放量小于国家的碳配额，因此

在该情况下，LCSDN系统的最优利润并不受该政策限制的影响，则 $\pi _ { 3 }$ 对 ${ \sf q } _ { 3 }$ 分别求一阶、二阶偏导可得

$$
\frac { \hat { \sigma } \pi _ { 3 } } { \hat { \sigma } \mathbf { q } _ { 3 } } = \frac { 1 } { \mathbf { b } } \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 3 } - 2 \mathbf { q } _ { 3 } \big ) - \mathbf { c } _ { 1 }
$$

$$
\frac { \hat { \sigma } ^ { 2 } \pi _ { 3 } } { \hat { \sigma } \mathbf { q } _ { 3 } ^ { 2 } } = - \frac { 2 } { b } < 0
$$

可知，在该情况下，LCSDN系统的利润为订货量的凸函数，有唯一最优解满足：

$$
q _ { 3 } ^ { * } = \frac { 1 } { 2 } \mathopen { } \mathclose \bgroup \left( \mathrm { a } + \lambda \xi _ { 3 } - \mathrm { b c } _ { 1 } \aftergroup \egroup \right)
$$

比较 ${ \bf q } _ { \mathrm { r } 3 } ^ { * }$ 与 $\mathbf { q } _ { 3 } ^ { * }$ 可知，由于 $\mathbf { q } _ { \mathrm { r } 3 } ^ { * } > \mathbf { q } _ { 3 } ^ { * }$ ，即在配额政策的限制下，当制造商的碳排放量不超过政府规定的碳配额时，分散决策时零售商的最优利润始终小于集中决策下的最优利润，因此，该情况下的批发价合同仍无法实现LCSDN系统的协调。

命题4碳配额情形下，当企业的碳排放量大于碳配额时，批发价合同无法实现LCSDN系统的协调，且制造商的利润随着碳配额的减少而减少。

证明在分散决策下，根据 Stackelberg 博弈的逆向求解法，将 ${ \sf q } _ { r 3 }$ 代入式（33）中， $\dot { \pi } _ { \mathrm { m } 3 }$ 可表示为

$$
\pi _ { \mathrm { m } 3 } = \frac { \displaystyle { \left( \mathbf { a } + \lambda \dot { \xi } _ { 3 } - \mathbf { b w } _ { 3 } \right) \left[ \mathbf { w } _ { 3 } - \mathbf { c } _ { 1 } - e g \left( 1 - \dot { \xi } _ { 3 } \right) \right] } } { 2 } + g E - \frac { 1 } { 2 } h \xi _ { 3 } ^ { 2 }
$$

对式（49）分别求 $\dot { \pi } _ { \mathfrak { m } 3 }$ 对 $\dot { w } _ { 3 }$ 的一阶、二阶偏导可得：

$$
\frac { \partial \dot { \pi } _ { m 3 } } { \partial \dot { w } _ { 3 } } = \frac { ( a + \lambda \dot { \xi } _ { 3 } - b \dot { w } _ { 3 } ) - b [ \dot { w } _ { 3 } - c _ { 1 } - e g ( 1 - \dot { \xi } _ { 3 } ) ] } { 2 }
$$

$$
\frac { \hat { \varrho } ^ { 2 } \pi _ { \mathrm { m 3 } } } { \hat { \varrho } \mathrm { w } _ { 3 } ^ { 2 } } = - \mathbf { b } < 0
$$

可求得如下 $\dot { w } _ { 3 }$ 关于的 $\dot { \xi } _ { 3 }$ 的表达式：

$$
\overset { \cdot } { \mathbf { w } } _ { 3 } = \frac { a + b \mathbf { c } _ { 1 } + \lambda \overset { \cdot } { \xi _ { 3 } } + e g \left( 1 - \overset { \cdot } { \xi _ { 3 } } \right) } { 2 b }
$$

将所得 $\dot { w } _ { 3 }$ 关于的 $\dot { \xi } _ { 3 }$ 的表达式代入式（49）中，此时的 $\dot { \pi } _ { \mathrm { m } 3 }$ 可表示为

$$
\overset { \cdot } { \pi _ { \mathrm { m 3 } } } = \frac { \overset { \cdot } { \left[ \mathbf { a } + \lambda \xi _ { 3 } - b \mathbf { c } _ { 1 } - b e g \left( 1 - \dot { \xi } _ { 3 } \right) \right] ^ { 2 } } } { 8 \mathbf { b } } + g E - \frac { 1 } { 2 } h \overset { \cdot } { \xi } _ { 3 } ^ { 2 }
$$

对式（53）分别求 $\dot { \pi } _ { \mathrm { m } 3 }$ 对 $\dot { \xi } _ { 3 }$ 的一阶、二阶偏导可得

$$
\frac { \partial \pi _ { \mathrm { m 3 } } } { \partial \xi _ { 3 } } = \frac { \lambda \big ( \lambda - \mathrm { b e g } \big ) \Bigg [ \mathrm { a } + \lambda \xi _ { 3 } - b \mathrm { c } _ { 1 } - b e g \Bigg ( 1 - \xi _ { 3 } \Bigg ) \Bigg ] } { 4 \mathfrak { b } } - \mathrm { h } \xi _ { 3 }
$$

$$
\frac { \hat { \sigma } ^ { 2 } \pi _ { \mathrm { m 3 } } } { \hat { \sigma } \zeta _ { 3 } ^ { 2 } } = - \frac { \left( \lambda - b e g \right) ^ { 2 } } { 4 b } - \mathrm { h } < 0
$$

制造商的碳排放量大于政府规定的碳配额时，当且仅当$( \lambda - b e g ) ^ { 2 } - 4 b h < 0$ ，制造商的利润函数 $\dot { \pi } _ { \mathrm { m } 3 }$ 存在最大值，令式（3.54）等于 $0$ ，通过求解可得最优的碳排放量为

$$
\xi _ { 3 } ^ { \dot { \ast } } = \frac { \left( \lambda - b e g \right) \left( a - b c _ { 1 } - b e g \right) } { 4 b h - \left( \lambda - b e g \right) ^ { 2 } }
$$

在集中决策下，即制造商要对超出碳配额的部分交付一定的罚款，则此时制造商的利润函数为

$$
\begin{array} { r } { \operatorname* { m a x } \quad \displaystyle \pi _ { 3 } = \Biggl [ \frac { 1 } { \mathbf { b } } \biggl ( \mathbf { a } + \lambda \boldsymbol { \dot { \xi } } _ { 3 } - \mathbf { q } _ { 3 } \biggr ) - \mathbf { c } _ { 1 } - e g \biggl ( 1 - \boldsymbol { \dot { \xi } } _ { 3 } \biggr ) \Biggr ] \mathbf { q } _ { 3 } + } \\ { \operatorname* { m a x } \qquad \quad g E - \cfrac { 1 } { 2 } h \dot { \xi } _ { 3 } ^ { 2 } \qquad } \end{array}
$$

s.t.

$$
E - \big ( 1 - \xi _ { 3 } \big ) e \mathbf { q } _ { 3 } < 0
$$

由于式（57）和（58）为线性规划求最优解的问题，可先对式（57）求最优解，然后将边界线式（58）代入（57）中，对比两者的结果即可得到该线性规划问题的最优解，首先 $\dot { \pi } _ { 3 }$ 对${ \dot { q } } _ { 3 }$ 的一阶、二阶偏导可得：

$$
\frac { \partial \pi _ { 3 } } { \partial { \bf q } _ { 3 } } = \frac { 1 } { { \bf b } } \Bigg ( { \bf a } + \lambda \dot { \zeta } _ { 3 } - 2 \dot { \bf q } _ { 3 } \Bigg ) - { \bf c } _ { 1 } - e g \Bigg ( 1 - \dot { \xi } _ { 3 } \Bigg )
$$

$$
\frac { \hat { \sigma } ^ { 2 } \pi _ { 3 } } { \hat { \sigma } \mathbf { q } _ { 3 } ^ { 2 } } = - \frac { 2 } { b } < 0
$$

通过计算可知，在该情况下，LCSDN系统的利润为订货量的凸函数，存在最优解满足：

$$
\mathbf { q } _ { 3 } = \frac { 1 } { 2 } \left[ \mathbf { a } + \lambda \boldsymbol { \dot { \xi } } _ { 3 } - b \mathbf { c } _ { 1 } - e g \left( 1 - \boldsymbol { \dot { \xi } } _ { 3 } \right) \right]
$$

比较分散决策式（35）与集中决策式（46）（49）两种情形下的最优订货量，可得出以下结论：当制造商的碳排放量不超过政府规定的碳配额时，由于 $\mathbf { W } _ { 3 } > \mathbf { C } _ { 1 }$ ，因此 $\dot { q } _ { r 3 } > \dot { q } _ { 3 }$ ，此时碳配额政策对制造商企业不起作用，此时LCSDN无法达到协调，且分散决策下的最优订货量始终大于集中决策的情形。

# 2.4碳配额与交易下SDN批发价格契约协调模型

碳配额与交易是指受政府碳排放限制的控制，当碳配额不足或剩余时，企业可在碳交易市场中购买或出售碳排放权。在碳配额与交易机制下，企业减排的动机来自于两个方面：一方面来自于政策的压力以及碳交易市场利益的诱惑，促使企业通过减排改进生产制造过程以增加收益；另一方面，企业的减排动机还来自于消费者低碳意识的增强，部分环保意识较强的消费者，具有一定程度的低碳偏好，愿意支付较高的价格来购买低碳商品，企业针对这些低碳意识较强的消费者推出价格较高的低碳产品，以获取更多的利润。因此，在碳配额与交易机制下，零售商、制造商以及LCSDN系统的利润函数可以表示为

$$
\boldsymbol { \pi } _ { \mathrm { r 4 } } = \left( \mathbf { p } _ { 4 } - \mathbf { w } _ { 4 } \right) \mathbf { q } _ { 4 } = \left[ \frac { 1 } { \mathbf { b } } \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 4 } - \mathbf { q } _ { 4 } \big ) - \mathbf { w } _ { 4 } \right] \mathbf { q } _ { 4 }
$$

$$
\boldsymbol { \pi } _ { \mathrm { m 4 } } = \biggl [ \mathbf { W } _ { 4 } - \mathbf { c } _ { \mathrm { l } } - \bigl ( 1 - \boldsymbol { \xi } _ { 4 } \bigr ) \mathbf { c } _ { 2 } \mathbf { e } \biggr ] \mathbf { q } _ { 4 } + \mathbf { c } _ { 2 } \mathbf { E } - \frac { 1 } { 2 } \mathbf { h } \boldsymbol { \xi } _ { 4 } ^ { 2 }
$$

$$
\pi _ { 4 } = \left[ \frac { 1 } { \mathsf { b } } \big ( \mathrm { a } + \lambda \xi _ { 4 } - \mathrm { q } _ { 4 } \big ) - \mathrm { c } _ { 1 } - \big ( 1 - \xi _ { 4 } \big ) \mathrm { c } _ { 2 } \mathrm { e } \right] \mathsf { q } _ { 4 } + \mathrm { c } _ { 2 } \mathrm { E } - \frac { 1 } { 2 } \mathrm { h } \xi _ { 4 } ^ { 2 }
$$

命题5在碳配额与交易机制政策下，当且仅当在满足$\mathbf { w } _ { 4 } = \mathbf { c } _ { 1 } + \bigl ( 1 - \xi _ { 4 } \bigr ) \mathbf { c } _ { 2 } \mathbf { e }$ 时，LCSDN 系统可实现协调，但此时制造商的批发价格等于单位产品生产成本，相当于制造商只能通过降低碳排放成本来获取更多的利润，而不受零售商订货量的影响

证明在分散决策下，制造商和零售商都根据自身利益最大化进行决策，对式（63）求 ${ \bf q } _ { \mathrm { r 4 } } ^ { * }$ 的倒数，同式（6）（7)，可得分散决策时，零售商的最优订货量为

$$
\mathbf { q } _ { \mathrm { r 4 } } ^ { * } = \frac { 1 } { 2 } \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 4 } - \mathbf { b w } _ { 4 } \big )
$$

根据Stackelberg 博弈的逆向求解法，将 ${ \bf q } _ { \mathrm { r } 4 } ^ { * }$ 代入式（43）中， $\pi _ { \mathrm { m } 4 }$ 可表示为

$$
\pi _ { \mathrm { m 4 } } = \frac { 1 } { 2 } \big ( \mathrm { a } + \lambda \xi _ { \mathrm { 4 } } - \mathrm { b w } _ { \mathrm { 4 } } \big ) \Big [ \mathrm { w } _ { \mathrm { 4 } } - \mathrm { c } _ { \mathrm { 1 } } - \big ( 1 - \xi _ { \mathrm { 4 } } \big ) \mathrm { c } _ { \mathrm { 2 } } \mathrm { e } \Big ] + \mathrm { c } _ { \mathrm { 2 } } \mathrm { E } - \frac { 1 } { 2 } \mathrm { h } \xi _ { \mathrm { 4 } } ^ { 2 } ( \mathrm { f } - \mathrm { c } _ { \mathrm { 2 } } ) \mathrm { c } _ { \mathrm { 2 } } \mathrm { e } ,
$$

对式（67）分别求 $\pi _ { \mathrm { m } 4 }$ 对 $\mathbf { W } _ { 4 }$ 的一阶、二阶偏导可得：

$$
\frac { \partial \pi _ { \mathrm { m 4 } } } { \partial \mathbf { W } _ { 4 } } = \frac { 1 } { 2 } \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \left( \mathrm { a } + \lambda \xi _ { 4 } - \mathrm { b w } _ { 4 } \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \right) - \frac { \mathrm { b } } { 2 } \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \mathopen { } \mathclose \bgroup \left[ \mathrm { \mathbf { W } _ { 4 } } - \mathrm { c } _ { 1 } - \mathopen  \left( 1 - \xi _ { 4 } \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \right] \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \aftergroup \egroup \right]
$$

$$
\frac { \partial ^ { 2 } \pi _ { \mathrm { m 4 } } } { \partial { \bf w q } _ { 4 } ^ { 2 } } = - { \bf b } < 0
$$

可求得如下 $\mathbf { W } _ { \mathrm { r 4 } } ^ { * }$ 关于的 $\xi _ { 4 }$ 的表达式：

$$
\mathbf { W } _ { { \mathrm { r } } 4 } ^ { \ast } = { \frac { \mathbf { a } + \lambda { \boldsymbol { \xi } } _ { 4 } - \mathbf { b } { \mathrm { c } } _ { 1 } - { \bigl ( } 1 - { \boldsymbol { \xi } } _ { 4 } { \bigr ) } \mathbf { b } { \mathrm { c } } _ { 2 } \mathbf { e } } { 2 \mathbf { b } } }
$$

将所得 $\mathbf { W } _ { \mathrm { r 4 } } ^ { * }$ 关于的 $\xi _ { 4 }$ 的表达式代入式（36）中，此时的 $\pi _ { { \mathrm m } 4 }$ 可表示为

$$
\pi _ { \mathrm { m 4 } } = \frac { 1 } { 8 \mathbf { b } } \Big [ \mathbf { a } + \lambda \boldsymbol { \xi } _ { 4 } - \mathbf { b } \mathbf { c } _ { 1 } - \left( 1 - \boldsymbol { \xi } _ { 4 } \right) \mathbf { b } \mathbf { c } _ { 2 } \mathbf { e } \Big ] ^ { 2 } + \mathbf { c } _ { 2 } \mathbf { E } - \frac { 1 } { 2 } \mathbf { h } \boldsymbol { \xi } _ { 4 } ^ { 2 }
$$

对式（36）分别求 $\pi _ { { \mathrm { m } } 4 }$ 对 $\xi _ { 4 }$ 的一阶、二阶偏导可得：

$$
\frac { \partial \pi _ { \mathrm { m 4 } } } { \partial \xi _ { 4 } } = \frac { \lambda } { 4 \mathbf { b } } \Big [ \mathbf { a } + \lambda \xi _ { 4 } - \mathbf { b } \mathbf { c } _ { 1 } - \big ( 1 - \xi _ { 4 } \big ) \mathbf { b } \mathbf { c } _ { 2 } \mathbf { e } \Big ] - \mathbf { h } \xi _ { 4 }
$$

$$
\frac { \hat { \sigma } ^ { 2 } \pi _ { \mathrm { m 4 } } } { \hat { \sigma } \xi _ { 4 } ^ { 2 } } = \frac { \lambda ^ { 2 } } { 4 { \bf b } } - { \bf h } < 0
$$

当且仅当 $\lambda ^ { 2 } - 4 \mathrm { b h } < 0$ 时，制造商的利润函数 $\pi _ { { \mathrm { m } } 4 }$ 存在最大值，令式（81）等于0，通过求解可得制造商的碳排放量小于政府规定的碳配额情况下，最优的碳排放量为

$$
\boldsymbol { \xi } _ { \mathrm { r 4 } } ^ { * } = \frac { \lambda \bigl ( \mathrm { a } - \mathrm { b } \mathbf { c } _ { 1 } - \mathrm { b } \mathbf { c } _ { 2 } \mathbf { e } \bigr ) } { 4 \mathrm { b h } - \lambda \bigl ( \lambda + \mathrm { b } \mathbf { c } _ { 2 } \mathbf { e } \bigr ) }
$$

在集中决策下，将LCSDN系统的利润函数分别对订货量求一阶偏导数及二阶偏导数可得

$$
\frac { \hat { \sigma } \pi _ { 4 } } { \hat { \sigma } \mathbf { q } _ { 4 } } = \left[ \frac { 1 } { \mathbf { b } } \big ( \mathbf { a } + \lambda \boldsymbol { \xi } _ { 4 } - 2 \mathbf { q } _ { 4 } \big ) - \mathbf { c } _ { 1 } \right] - \big ( 1 - \boldsymbol { \xi } _ { 4 } \big ) \mathbf { c } _ { 2 } \mathbf { e }
$$

$$
\frac { \hat { \sigma } ^ { 2 } \pi _ { \mathrm { m 4 } } } { \hat { \sigma } { \bf q } _ { 4 } ^ { 2 } } = - \frac { 2 } { \bf b } < 0
$$

LCSDN系统利润函数对订货量的二次偏导数小于零，原LCSDN系统利润函数为凸函数，存在唯一最优解满足：

$$
\mathbf { q } _ { 4 } ^ { * } = \frac { 1 } { 2 } \left[ \mathbf { a } + \lambda \boldsymbol { \xi } _ { 4 } - \mathbf { b } \mathbf { c } _ { 1 } - \left( 1 - \boldsymbol { \xi } _ { 4 } \right) \mathbf { b } \mathbf { c } _ { 2 } \mathbf { e } \right]
$$

在政府碳排放配额与交易限制下，若使LCSDN 系统实现协调需满足分散决策与集中决策的最优订货量相一致。通过计算可得：当 $\mathbf { W } _ { 4 } > \mathbf { c } _ { 1 } + \bigl ( 1 - \xi _ { 4 } \bigr ) \mathbf { c } _ { 2 } \mathbf { e }$ 时，即 $\mathbf { q } _ { \mathrm { r 4 } } ^ { * } > \mathbf { q } _ { 4 } ^ { * }$ ，则LCSDN系统不能实现协调，且分散决策时的利润要大于集中决策时的利润；当 $\mathbf { w } _ { 4 } < \mathbf { c } _ { 1 } + \bigl ( 1 - \xi _ { 4 } \bigr ) \mathbf { c } _ { 2 } \mathbf { e }$ 时，即 $\mathbf { q } _ { \mathrm { r 4 } } ^ { * } < \mathbf { q } _ { 4 } ^ { * }$ ，则LCSDN系统不能实现协调，且分散决策时的利润要小于集中决策时的利润；当且仅当在满足 $\mathbf { W } _ { 4 } = \mathbf { c } _ { 1 } + \bigl ( 1 - \xi _ { 4 } \bigr ) \mathbf { c } _ { 2 } \mathbf { e }$ 时，LCSDN系统可实现协调，但此时制造商的批发价格等于单位产品生产成本，相当于制造商只能通过降低碳排放成本来获取更多的利润，而不受零售商订货量的影响。

# 3 数值仿真

不同的碳排放政策对制造商以及LCSDN系统的最优订货量和最大期望利润均有不同的影响。碳税主要表现为单位碳排放量碳税价格的变化对LCSDN系统利润的影响；碳配额机制主要表现为政府碳配额的设定对期望利润的影响；而碳配额与交易机制主要表现为碳配额的设定以及碳交易市场中的交易价格对期望利润的影响。不同的碳排放政策之间也由于参数变化的不同导致期望利润的不同。考虑到以上四种模型下的LCSDN契约协调模型的参数众多，公式均具有一定的复杂性，为更好地体现以上四种模型的实际应用价值，本节将采用Mathmetica和MATLAB软件对四种模型进行数值仿真分析，对比分析不同碳排放政策下LCSDN系统协调的影响以及不同的减排系数给LCSDN收益带来的影响。

在不同的碳排放政策下，假设市场需求函数可表示为$\mathbf { q } _ { 1 } = 5 0 0 - \mathbf { p } + 5 \boldsymbol { \xi }$ 。制造商每单位产品的生产制造成本为 $\mathbf { c } _ { 1 } = 2 0$ ，零售商以批发价格W向制造商订购商品。制造商每生产单位产品的原始碳排放量为 $\mathbf { e } = 1$ ，制造商投资减排的成本系数为$\mathrm { h } = 5 0 0$ ，在征收碳税的情况下，政府对单位碳排放量征收t个单位的碳税；在碳配额政策下，在期初会根据产业性质不同以及上一期的碳排放量免费分配一定数量的碳配额E，当制造商的碳排放量超出碳排放额度时，政府会收取一定的罚款 $\mathbf { g } = 3$ ：在碳交易政策下，政府给制造商的免费碳配额为 $\mathrm { E } = 1 5$ ，单位碳排放权的价格 $\mathrm { c } _ { 2 } = 2 0$ 。具体参数的数值如表2所示。

表2相关仿真数值参数表  

<html><body><table><tr><td>a</td><td>b</td><td></td><td>C1</td><td>C2</td><td>e</td><td>g</td><td>h</td></tr><tr><td>100</td><td>1</td><td>5</td><td>20</td><td>20</td><td>1</td><td>3</td><td>500</td></tr></table></body></html>

# 3.1不考虑碳排放下的仿真分析

在不考虑政府碳排放限制的情况下，探讨制造商在生产制造过程中采用不同的碳减排率的变化对LCSDN系统中制造商的最优批发价格、零售商订货量以及对零售商和制造商利润的影响。将上述数值带入公式中，所求结果如表3所示。

表3不同的制造商碳减排率变化对LCSDN系统各参数的影响  

<html><body><table><tr><td></td><td>w1</td><td>q</td><td>π1</td><td>πm1</td><td>π</td><td>q</td></tr><tr><td>0.10</td><td>60.25</td><td>20.13</td><td>405.02</td><td>807.53</td><td>887.91</td><td>40.25</td></tr><tr><td>0.20</td><td>60.50</td><td>20.25</td><td>410.06</td><td>810.13</td><td>1220.19</td><td>40.50</td></tr><tr><td>0.30</td><td>60.75</td><td>20.38</td><td>415.14</td><td>807.78</td><td>1222.92</td><td>40.75</td></tr><tr><td>0.40</td><td>61.00</td><td>20.50</td><td>420.25</td><td>800.50</td><td>1220.75</td><td>41.00</td></tr><tr><td>0.50</td><td>61.25</td><td>20.63</td><td>425.39</td><td>788.28</td><td>1213.67</td><td>41.25</td></tr><tr><td>0.60</td><td>61.50</td><td>20.75</td><td>430.56</td><td>771.13</td><td>1201.69</td><td>41.50</td></tr><tr><td>0.70</td><td>61.75</td><td>20.88</td><td>435.77</td><td>749.03</td><td>1184.80</td><td>41.75</td></tr><tr><td>0.80</td><td>62.00</td><td>21.00</td><td>441.00</td><td>722.00</td><td>1163.00</td><td>42.00</td></tr><tr><td>0.90</td><td>62.25</td><td>21.13</td><td>446.27</td><td>690.03</td><td>1136.30</td><td>42.25</td></tr></table></body></html>

从表3的数值仿真中可看出，在不考虑国家碳减排政策的限制下，制造商提高碳减排的动力主要来着消费者对低碳产品的偏好，但随着碳减排率的升高，制造商则需要付出更多的成本来帮助实现低碳减排，反而零售商的收益会随着碳减排率的升高而升高，这也是受消费者低碳偏好的影响。为了更清楚的分析各参数值的变化，首先通过Matlab绘制二维图形来分析在不考虑国家碳减排政策的限制下，碳减排率的变化对考虑批发价格企业的LCSDN协调的影响，如图1所示为在不考虑碳减排限制下集中决策与分散决策两种情况下的零售商最优订货量，

![](images/31308c93b64bfcbea2436bed04bc8b81e2b4bfcd7a0c3e0da4e8e356228d49e2.jpg)  
图1碳减排率的变化对分散决策与集中决策最优订货量的影响

从图1中可看出，在不考虑碳减排限制下，无论碳减排率如何变化，集中决策下最优订货量一直大于分散决策下的最优订货量，因此在不考虑碳减排政策下考虑批发价格契约的LCSDN系统是无法实现协调的。且在 $\xi _ { { \mathrm { \scriptscriptstyle r 1 } } } \in \left( 0 , 1 \right)$ 时，集中决策与分散决策下的最优订货量均与碳减排率呈正相关。

![](images/6d1eef58e3772eff1c1ca1099bc548d594f345e1f2fd76f4b5bfc788a373a17e.jpg)  
图2碳减排率对收益的影响

为了更清楚的观察制造商碳减排率的变化对制造商、零售商以及LCSDN系统收益的影响，以便LCSDN系统按照收益最大化来作出决策，利用Matlab软件绘制图2来观察碳减排的变化对LCSDN的影响。从图2中可看出，随着碳减排率的增加，零售商的利润与碳减排率呈正相关关系，收益随着减排率的增加而增加，这是由于消费者的低碳偏好的影响，随着消费者低碳偏好而产生的变动需求增加，因此零售商的收益也随之增加；而制造商的收益呈现先增后降的趋势，在 $\xi _ { r 1 } = 0 . 2$ 附近达到最高点时，制造商的收益最高，此时为制造商的最优决策。

# 3.2碳税机制下的仿真分析

在政府碳税限制的条件下，通过数值仿真分析碳税价格的变化 $\scriptstyle t \in \left( 0 , 1 0 \right)$ 对LCSDN系统中制造商最优批发价格、分散决策和集中决策下零售商最优订货量以及对零售商和制造商利润的影响。将上述假设的数值代入所求得的公式中，所求结果如表4所示。

表4不同的碳税税率对LCSDN系统各参数的影响  

<html><body><table><tr><td>t</td><td></td><td>W</td><td>q</td><td>π2</td><td>Tm2</td><td>π</td><td></td></tr><tr><td>1</td><td>0.24</td><td>60.98</td><td>20.11</td><td>404.49</td><td>794.42</td><td>1198.92</td><td>40.22</td></tr><tr><td>2</td><td>0.28</td><td>61.42</td><td>19.99</td><td>399.59</td><td>779.60</td><td>1179.19</td><td>39.98</td></tr><tr><td>3</td><td>0.32</td><td>61.82</td><td>19.89</td><td>395.47</td><td>765.63</td><td>1161.09</td><td>39.77</td></tr><tr><td>4</td><td>0.36</td><td>62.18</td><td>19.80</td><td>392.12</td><td>752.48</td><td>1144.59</td><td>39.60</td></tr><tr><td>5</td><td>0.39</td><td>62.50</td><td>19.74</td><td>389.54</td><td>740.13</td><td>1129.67</td><td>39.47</td></tr><tr><td>6</td><td>0.43</td><td>62.78</td><td>19.69</td><td>387.75</td><td>728.58</td><td>1116.33</td><td>39.38</td></tr><tr><td>7</td><td>0.47</td><td>63.03</td><td>19.67</td><td>386.75</td><td>717.81</td><td>1104.56</td><td>39.33</td></tr><tr><td>8</td><td>0.51</td><td>63.23</td><td>19.66</td><td>386.57</td><td>707.81</td><td>1094.38</td><td>39.32</td></tr><tr><td>9</td><td>0.55</td><td>63.4</td><td>19.68</td><td>387.24</td><td>698.59</td><td>1085.83</td><td>39.36</td></tr></table></body></html>

从表4中也可以看出，随着单位碳排放量碳税价格的升高，制造商的压力越来越多，将会支付大量的碳减排费用，其制造商的收益则会随之降低，，对于零售商而言，随着制造商对产品采取减排措施的同时，消费者对商品的购买量会增多，从而增加了零售商的收益，而LCSDN系统的收益也会受到影响而呈现降低的趋势。为了更清楚的分析在碳税政策下，政府所规定的碳税价格的变化对LCSDN系统各参数值变化的影响，通过这样的分析也有利于帮助政府给出合理的碳税价格来降低制造商契约的碳排放量，从而达到缓解温室效应的效果。通过MATLAB绘制二维图形来分析碳税价格的变化对引入批发价格契约的LCSDN协调的影响，如图3所示为在碳税机制情况中集中决策与分散决策两种情况下的零售商最优订货量。

从图3中可看出，在碳税政策下，无论碳税价格如何变化，集中决策下的零售商的最优订货量始终大于分散决策下的零售商最优订货量。因此在碳税政策下，引入批发价格契约的LCSDN系统是无法实现协调的。且在单位碳排放碳税价格$t \in \left( 0 , 2 0 \right)$ 时，集中决策与分散决策下的最优订货量均随着碳税价格的增加呈现先减少再增加的趋势。

![](images/4cebc3c2753a29ae6883b3670b8534b797e9f0881a03c359b3e14c9ae85de1f4.jpg)  
图3碳税机制分散决策与集中决策下的零售商最优订货量

![](images/0267609c87aa9b4124f6c530a8eeb1604b06e8c077b25a7541b02e0a54f14526.jpg)  
图4碳税价格的变化对收益的影响

图4所示为碳税价格的变化对引入批发价格契约的LCSDN系统各决策主体收益的影响。从图中可看出，随着碳税价格的增加，当每单位碳排放量的碳税价格 $t \in \left( 0 , 2 0 \right)$ 时，零售商的利润、制造商的利润以及LCSDN系统的利润均随着碳税价格的升高而降低。这可能是由于政府在实施节能减排的同时，呼吁各企业减少碳排放量以保护环境，越高的碳税的价格会给企业带来更大的压力。

# 3.3碳配额机制下的仿真分析

在政府碳配额政策限制下，假设政府对于超出碳配额的罚款价格是固定不变的，通过数值仿真分析碳配额的变化$E \in \left( 0 , 3 0 \right)$ 对LCSDN系统中制造商的最优批发价格、零售商的最优订货量以及对零售商和制造商利润的影响。将上述假设的的数值代入公式中，所求结果如表5所示。

表5不同的碳配额对LCSDN系统各参数的影响  

<html><body><table><tr><td>E</td><td></td><td>W</td><td>qr</td><td>π3</td><td>πm3</td><td>π</td><td>q</td></tr><tr><td>30</td><td>0.20</td><td>60.51</td><td>20.25</td><td>410.19</td><td>810.13</td><td>1220.32</td><td>40.51</td></tr><tr><td>27</td><td>0.20</td><td>60.51</td><td>20.25</td><td>410.19</td><td>810.13</td><td>1220.32</td><td>40.51</td></tr><tr><td>24</td><td>0.20</td><td>60.51</td><td>20.25</td><td>410.19</td><td>810.13</td><td>1220.32</td><td>40.51</td></tr><tr><td>21</td><td>0.20</td><td>60.51</td><td>20.25</td><td>410.19</td><td>810.13</td><td>1220.32</td><td>40.51</td></tr><tr><td>18</td><td>0.20</td><td>60.51</td><td>20.25</td><td>410.19</td><td>810.13</td><td>1220.32</td><td>40.51</td></tr><tr><td>15</td><td>0.08</td><td>58.81</td><td>20.79</td><td>432.16</td><td>792.73</td><td>1224.90</td><td>41.58</td></tr><tr><td>12</td><td>0.08</td><td>58.81</td><td>20.79</td><td>432.16</td><td>783.73</td><td>1215.90</td><td>41.58</td></tr><tr><td>9</td><td>0.08</td><td>58.81</td><td>20.79</td><td>432.16</td><td>774.73</td><td>1206.90</td><td>41.58</td></tr><tr><td>6</td><td>0.08</td><td>58.81</td><td>20.79</td><td>432.16</td><td>765.73</td><td>1197.90</td><td>41.58</td></tr><tr><td>3</td><td>0.08</td><td>58.81</td><td>20.79</td><td>432.16</td><td>756.73</td><td>1188.90</td><td>41.58</td></tr></table></body></html>

从表5中可看出，在企业碳排放量不超过碳配额的情况下，最优订货量、批发价格以及制造商制定的碳减排率都不会随着碳配额的大小而变化，而当企业碳排放量超过碳配额时，则需要根据政府规定的罚款价格来看LCSDN系统中各方收益的影响。另外对于最优订货量而言，通过MATLAB绘制碳配额机制下的LCSDN契约协调情况对比图。

![](images/e8df5dd127aef1635a7899c00731479ae7ceeb79666b3facee345dddcbdd7bc3.jpg)  
图5碳配额机制分散决策与集中决策下的零售商最优订货量

如图图5所示。从图中可看到碳配额机制分散决策与集中决策下的零售商最优订货量，从图中可看出无论制造商的碳排放额是否超过政府的碳配额，集中决策下的最优订货量一直大于分散决策下的最优订货量，因此该情况下的LCSDN系统并不能达到协调。为了更清楚的分析碳配额的变化对LCSDN系统各参数值变化的影响，通过Matlab绘制二维图形，如图6所示，来分析碳配额的变化对LCSDN各方收益以及协调的影响。

![](images/12c2beae43af4328cdb80401262e215709cc5b18936aec37b3b3d3e2dc14f11e.jpg)  
图6碳配额的变化对收益的影响

从图6中可看出，当碳配额不足时，制造商会想方设法减少产品的碳排放量，从而减少违规的可能，此时受消费者市场低碳偏好的影响，会有更多的消费者选择低碳产品，从而会增加销量，给零售商带来更多的利润，但由于制造商为了降低碳排放量，从而需要投入更多的减排成本，导致利润的降低。当碳排放额充足时，零售商、制造商以及LCSDN系统的收益基本保持稳定，此时LCSDN 系统各主体的决策与不考虑碳排放政策下的决策基本相同，相当于当碳排放额充足时，该政策对LCSDN系统的决策几乎无影响。

# 3.4碳配额与交易机制下的仿真分析

在政府碳配额与交易政策限制下，由于受碳配额与交易价格不同的影响，零售商与制造商的决策也会不同。那么接下来的仿真将分为两部分：一部分为在交易价格不变的情况下，探讨碳配额的大小对LCSDN系统中最优批发价格、订货量以及对零售商和制造商利润的影响；另一部分为在碳配额不变的情况下，探讨交易价格的大小对LCSDN系统中制造商最优批发价格、零售商订货量以及对零售商和制造商利润的影响。

a）在政府碳配额与交易政策限制下，探讨碳交易价格不变碳配额的变化对LCSDN系统中最优批发价格、订货量以及对零售商和制造商及LCSDN系统利润的影响，将上述假设的的数值带入公式中，所求结果如表6所示。

表6不同的碳配额对LCSDN系统各参数的影响  

<html><body><table><tr><td>E</td><td>C2</td><td>5</td><td>W</td><td>q4</td><td>π4</td><td>πm4</td><td>π4</td><td>q</td></tr><tr><td>30</td><td>20</td><td>0.16</td><td>68.8</td><td>16</td><td>256</td><td>1105.6</td><td>1361.6</td><td>32</td></tr><tr><td>27</td><td>20</td><td>0.16</td><td>68.8</td><td>16</td><td>256</td><td>1045.6</td><td>1301.6</td><td>32</td></tr><tr><td>24</td><td>20</td><td>0.16</td><td>68.8</td><td>16</td><td>256</td><td>985.6</td><td>1241.6</td><td>32</td></tr><tr><td>21</td><td>20</td><td>0.16</td><td>68.8</td><td>16</td><td>256</td><td>925.6</td><td>1181.6</td><td>32</td></tr><tr><td>18</td><td>20</td><td>0.16</td><td>68.8</td><td>16</td><td>256</td><td>865.6</td><td>1121.6</td><td>32</td></tr><tr><td>15</td><td>20</td><td>0.16</td><td>68.8</td><td>16</td><td>256</td><td>805.6</td><td>1061.6</td><td>32</td></tr><tr><td>12</td><td>20</td><td>0.16</td><td>68.8</td><td>16</td><td>256</td><td>745.6</td><td>1001.6</td><td>32</td></tr><tr><td>9</td><td>20</td><td>0.16</td><td>68.8</td><td>16</td><td>256</td><td>685.6</td><td>941.6</td><td>32</td></tr><tr><td>6</td><td>20</td><td>0.16</td><td>68.8</td><td>16</td><td>256</td><td>625.6</td><td>881.6</td><td>32</td></tr><tr><td>3</td><td>20</td><td>0.16</td><td>68.8</td><td>16</td><td>256</td><td>565.6</td><td>821.6</td><td>32</td></tr></table></body></html>

从表6中可看出，对于最优订货量而言，无论制造商的碳排放额是否超过政府的碳配额，集中决策下的零售商最优订货量一直大于分散决策下的最优订货量，因此该情况下引入批发价格契约的LCSDN系统并不能达到协调。为了更清楚的分析碳交易价格不变的情况下碳配额的变化对LCSDN系统各参数值变化的影响，通过Matlab绘制二维图形来分析碳配额的变化对LCSDN协调的影响，如图7所示。

![](images/4dc38378aabe1b5e69b52962c9c3fb3d006daacc18fed86c9c4b2426d4c26f26.jpg)  
图7碳配额的变化对收益的影响

从图7可看出，当碳交易价格固定时，零售商的收益不受碳配额变化的影响，这也是由于碳减排政策仅考虑的制造商在生产制造过程中的碳排放，而不考虑零售商的碳排放。但制造商与LCSDN系统的利润与碳配额呈正比例线性关系，制造商的利润会随着碳配额的减少而减少。

b)在政府碳配额与交易政策限制下，探讨政府规定的碳配额不变的情况下，考察碳交易价格的变化对LCSDN系统中制造商最优批发价格、零售商订货量以及对零售商和制造商和LCSDN利润的影响。将上述假设的的数值带入公式中，所求结果如表7所示。

表7不同的碳交易价格对LCSDN系统各参数的影响  

<html><body><table><tr><td>C2</td><td>E</td><td>5</td><td></td><td>q4</td><td>πr4</td><td>πm4</td><td>π4</td><td>q</td></tr><tr><td>30</td><td>15</td><td>0.14</td><td>73.29</td><td>13.70</td><td>187.6</td><td>820.6</td><td>1008.2</td><td>27.4</td></tr><tr><td>27</td><td>15</td><td>0.14</td><td>71.92</td><td>14.40</td><td>207.4</td><td>814.6</td><td>1022.0</td><td>28.8</td></tr><tr><td>24</td><td>15</td><td>0.15</td><td>70.57</td><td>15.09</td><td>227.8</td><td>809.9</td><td>1037.8</td><td>30.1</td></tr><tr><td>21</td><td>15</td><td>0.16</td><td>69.24</td><td>15.78</td><td>248.8</td><td>806.5</td><td>1055.3</td><td>31.5</td></tr><tr><td>18</td><td>15</td><td>0.16</td><td>67.93</td><td>16.45</td><td>270.4</td><td>804.1</td><td>1074.6</td><td>32.8</td></tr><tr><td>15</td><td>15</td><td>0.17</td><td>66.64</td><td>17.11</td><td>292.5</td><td>802.8</td><td>1095.4</td><td>34.2</td></tr><tr><td>12</td><td>15</td><td>0.18</td><td>65.38</td><td>17.75</td><td>315.2</td><td>802.5</td><td>1117.7</td><td>35.5</td></tr><tr><td>9</td><td>15</td><td>0.18</td><td>64.13</td><td>18.39</td><td>338.3</td><td>803.2</td><td>1141.5</td><td>36.7</td></tr><tr><td>6</td><td>15</td><td>0.19</td><td>62.90</td><td>19.02</td><td>361.8</td><td>804.7</td><td>1166.5</td><td>38.0</td></tr><tr><td>3</td><td>15</td><td>0.20</td><td>61.70</td><td>19.64</td><td>385.8</td><td>807.0</td><td>1192.8</td><td>39.2</td></tr></table></body></html>

从表7中可看出在政府碳配额与交易政策限制下，对于零售商最优订货量而言，无论制造商的碳排放额是否超过政府的碳配额，集中决策下的最优订货量一直大于分散决策下的最优订货量，因此该情况下引入批发价格契约的LCSDN系统并不能达到协调。为了更清楚的分析碳交易价格的变化对LCSDN系统各参数值变化的影响，通过Matlab绘制二维图形来分析碳交易价格的变化对LCSDN协调的影响，如图8所示。

![](images/4ca5f4fe4feb357fab2b0392fc370827d16e1816f03ded61726b267154ee9f3d.jpg)  
图8碳交易价格的变化对收益的影响

图8中可看出，当碳配额固定时，零售商的最优订货量会随着碳交易价格的升高而降低，而制造商的利润随着碳交易价格的增加而先降后增。随着碳交易价格的升高，零售商的利润呈现下降的趋势，LCSDN系统的利润总体上也呈现下降的趋势。

# 4 结束语

论文在低碳的背景下，分别探讨了无政府碳排放约束、碳税政策、碳配额政策、碳配额与交易政策下分散决策与集中决策的LCSDN企业协调与决策问题。并在此基础上，分析了不同的碳排放政策对零售商、制造商以及SDN系统期望利润的影响。论文的主要结论有：

a）在无政府碳排放约束、碳税政策、碳配额政策以及碳配额与交易政策下，集中决策下的零售商最优订货量始终大于分散决策下的最优订货量，因此无论在何种政策下传统的批发价格契约无法实现SDN系统的协调。

b）在碳税政策下，随着碳税价格的提高，零售商的利润、制造商的利润以及SDN系统的利润均会随着碳税价格的升高而降低。这可能是由于政府在实施节能减排的同时，呼呼各企业减少碳排放量以保护环境，越高的碳税的价格会给企业带来更大的压力。

c）在碳配额政策限制下，当企业的碳排放量小于政府规定的碳配额时，制造商的最优订货量和最大期望利润均不会受碳配额变化的影响，都等于无碳排放约束情形的最优订货量和最大期望利润。而当企业的碳排放量超过碳配额时，制造商的利润随着碳配额的减少而减少。

d）在碳配额与交易情形下，当碳交易价格固定时，零售商的最优订货量及收益不会受碳配额变化的影响，但制造商的利润会随着碳配额的减少而减少；当碳配额固定时，零售商的最优订货量会随着碳交易价格的升高而降低，而制造商的利润随着碳交易价格的增加而先降后增。

另外，论文研究的供需网契约协调问题，并将低碳的相关政策引入到供需网系统中，分析不同的低碳政策对供需网决策、契约协调的影响，是目前较新的研究课题。在实际应用中，低碳环境下的供需网协调问题更复杂、更繁琐。论文的研究内容与模型建立有限，可能与实际情况有一定差距，因此，今后还需要做进一步的研究完善。论文仅考虑在线性市场需求下考虑消费者低碳偏好的情况下进行了研究，未来可以考随机市场需求下不同的低碳政策对供需网企业决策以及协调的影响；论文研究的是供需网系统中最简单的单一制造商和单一零售商组成的双层供需网系统，仅以供需网中的两个节点为研究对象，未来可考虑具有一般性的供需网复杂网络模型。

# 参考文献：

[1]徐福缘，何静，林凤，等．多功能开放型企业供需网及其支持系统研究 国家自然科学基金项目（70072020）回翔[J].管理学报.2007,(4): 379-383.   
[2]Dekker R,Bloemhof J,Mallidis I. Operations Research for green logistics: an overview of aspects,issues,contributions and challenges [J]. European Journal of Operational Research,2011,219 (219): 671-679.   
[3]Mutingi M,Mapfaira H,Monageng R.Developing performance management systems for the green supply chain [J].Journal of Remanufacturing,2014,4(1):6.   
[4]Barbarossa C,Pelsmacker P D.Positive and negative antecedents of purchasing eco-friendly products:a comparison between green and nongreen consumers [J]. Journal of Business Ethics,2016,134(2): 229-247.   
[5]He L,Hu C, Zhao D,et al. Carbon emission mitigation through regulatory policies and operations adaptation in supply chains: theoretic developments and extensions [J]. Natural Hazards,2016,84(1): 1-29.   
[6]Beamon B M.Designing the green supply chain [J].Logistics Information Management,1999,12(4): 332-342.   
[7]Lee K H. Integrating carbon footprint into supply chain management: the case of Hyundai Motor Company (HMC) in the automobile industry [J] JournalofCleanerProduction,2011,19(11):1216-1223.   
[8] 施丽华．低碳供应链管理研究[J].科技资讯,2016,14(20):71-72.   
[9]Yang S,Yu J.Low-carbonization game analysis and optimization in a twoechelon supplychainunder the carbon-tax policy[J].Journalof Chinese Economic and Foreign Trade Studies,2016 (2) .   
[10] Spengler JJ.Vertical integration and antitrust policy[J].Journal of Political Economy,1950,58 (4):347-352.   
[11]李维安，李勇建，石丹.供应链治理理论研究：概念、内涵与规范性分 析框架[J].南开管理评论,2016,19(1):4-15.   
[12]何建佳，徐福缘，马庆国，等．非对称信息下存在逆向回流的供需网协 调[J].系统管理学报,2013,22(1):67-73.   
[13]胡伟，徐福缘，台德艺．基于供需网的企业合作优化决策模型[J]．系 统工程,2013(1):89-95.   
[14]何伟，徐福缘．基于风险的供需网契约协调仿真研究[J].计算机应用 研究,2014,31(2):378-383.   
[15]鲁力，陈旭．不同碳排放政策下基于回购合同的供应链协调策略[J]. 控制与决策,2014(12):2212-2220.   
[16]刘名武，吴开兰，许茂增．面向消费者低碳偏好的供应链减排成本分摊 与协调[J].工业工程与管理,2016,21(4):50-57.   
[17]刘超，慕静.随机需求与政府补贴条件下的低碳供应链协调[J].运筹 与管理,2016,25(4):142-149.   
[18]代应，林金钗，覃燕红，等．利他偏好下低碳供应链批发价格契约协调 机制[J].计算机工程与应用,2017,53(11):252-259.   
[19]支帮东，陈俊霖，刘晓红．碳限额与交易机制下基于成本共担契约的两 级供应链协调策略[J].中国管理科学,2017,25(7):48-56.   
[20]张玉忠，柏庆国．碳税政策下时变需求依赖库存与价格的供应链协调 模型[J].运筹学学报,2017,21(2):1