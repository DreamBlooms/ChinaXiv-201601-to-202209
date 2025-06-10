# 基于连续时间商品模型的电力市场理论

陈皓勇 韩励佳²(华南理工大学电力经济与电力市场研究所广州510641)（华北电力大学数理学院北京102206)

# 摘要

实时电价理论是许多国家电力现货市场设计的理论基础，但在电力市场实践中也出现了不少问题。实时电价有两个重大缺陷：一是仍然基于传统的分时调度模型，忽略了电能生产和消费的时间连续性这个十分重要的特征，没有认真处理跨时段约束；二是假设同一时段的电能商品都是同质的，无法区别基荷、腰荷和峰荷机组区别明显的技术特征及成本构成。为克服这些缺陷，本文提出连续时间电能商品模型，包括实时电价下和按负荷持续时间定价方式下的电能商品模型，并将两种定价方式下的市场优化问题与数学上的Riemann 积分和Lebesgue积分相对应，建立泛函极值优化模型，并基于Euler-Lagrange 方程求得市场均衡解，通过严格的数学推导证明了按负荷持续时间定价的可行性。算例计算表明，按负荷持续时间定价能减少市场总购电费用，而且电厂利润分配较为公平。本文所提的理论和方法可为国内外电力市场建设提供全新的思路和理论基础。

关键词：电力市场实时电价泛函优化分类号：TM73；F045.32

# Electricity Market Theory Based on Continuous Time Commodity

# Model

Chen Haoyong'， Han Lijia² 1(Institute of Power Economics and Electricity Markets,South China University of Technology, Guangzhou 510641, China) 2(Mathematical & Physical Science School, North China Electric Power University, Beijing 102206,China)

# Abstract

The theory of spot pricing is the basis of power market design in many countries,but there are many problems in the practice of spot electricity market. Spot electricity price has two major drawbacks:one is that it is still based on the traditional hourly scheduling/dispatch model, ignores the crucial time continuity in electric power production and consumption and does not handle the intertemporal constraints seriously; the second is that it assumes that the electricity products are homogeneous in the same dispatch period and cannot distinguish the base， shoulder and peak load power with obviously diferent technical and economic characteristics.To overcome the shortcomings,this paper presents a continuous time commodity model of electricity, including spot pricing model and the model priced according to load duration.The market optimization models under the two pricing methods are established with the Riemann and Lebesgue integrals respectively and the functional optimization problem are solved by the Euler-Lagrange equation to obtain the market equilibria. The feasibility of pricing according to load duration is proved by strict mathematical derivation. The theory and methods proposed in this paper wil provide new ideas and theoretical foundation for the development of electric power markets in China and all over the world.

Keyword: Electricity markets, Spot pricing, Functional optimization

# 1引言

《关于进一步深化电力体制改革的若干意见》（中发（2015）9号文）印发以来，电力市场改革成了业界热议的话题，围绕我国电力市场建设的目标模式及实施路径也有诸多争论。国家发展改革委、国家能源局2015年11月26日印发的电力体制改革配套文件2《关于推进电力市场建设的实施意见》对电力市场模式、交易机制等进行了一些规定和说明。2016年12月29日，国家发改委、国家能源局印发了《电力中长期交易基本规则（暂行)》（以下简称"基本规则")，是一个覆盖不同交易周期（多年、年、季、月、周等日以上）和省内及跨省跨区中长期电量交易品种的相对完善的市场规则，也是新一轮电改中从国家层面出台的第一个可执行性较强的市场规则。目前，随着电力市场改革的深化，加快建设现货市场已成为有关部门推动电力体制改革的重要举措。

无论采用何种电力市场模式及交易机制，电能商品模型的定义、成本构成及价格形成机制都是最基本的问题。由于电能商品物理上的无差异性（所有电厂的电一旦上网，就无法分开)，以及复杂物理网络（电力系统）的存在，成为世界上最复杂的商品之一，因此电能商品的定义及电价理论并不是那么显而易见的事。美国麻省理工学院（MIT）的FC.Schweppe 教授等在1988 年出版的 Spot Pricing of Electricity 成为实时电价理论的经典文献，并成为多国电力现货市场设计的理论基础。电价理论的研究应分为两个部分，即电能成本分析（即什么是合理电价）及电力市场中的电价形成机制。电能成本分析是衡量电价是否合理的基础，但电价最终要通过市场机制形成。在理想电力市场中，出清电价应与电力系统中的电能边际生产成本（以及电力用户的电能边际效用）相等。

实时电价（spot pricing）理论数学上十分精致，但笔者认为并不符合电力生产和消费的物理特征。在实际中，基于实时电价理论设计的现货市场或多或少都出了一些问题：实时市场价格变化剧烈，给市场主体带来很大的财务风险，需要另外引入金融交易等避险措施；大多数电力用户并无能力（或无意愿）对快速变化的实时电价作出响应，需要倚赖售电公司将批发市场的实时电价转化为简单的购电套餐，未达到通过实时电价增强供需方互动的理论设计目标，也导致电改红利被售电公司等中间商截留，传导不到用户侧，违背了电改的初衷；实时电价不能完全覆盖固定成本，导致发电投资容量不足，需要另设容量市场，等等。

# 2实时电价定价原理

实时电价取决于某一小时的电力供需情况，特别是：

负荷（总负荷及分区负荷）；  
发电的充裕度及成本（包括从其它公司购电)；

： 输、配电网的充裕度及损耗。

实时电价的定义为各用户在各时段（ $\cdot 1 \mathrm { h } / 0 . 5 \mathrm { h } / 0 . 2 5 \mathrm { h } / . . . )$ 的电价，包括以下分量：发电边际燃料成本、发电边际维护成本、发电供电质量费用、发电收支平衡费用、网络边际损耗成本、网络供电质量费用、网络收支平衡费用。

在不考虑收支平衡费用时，实时电价由边际成本决定，即

$$
\rho _ { k } \left( t \right) = \frac { \partial } { \partial d _ { k } \left( t \right) } [ \stackrel { \underbrace { \mathrm { x } \vec { F } } } { = } \vec { \mathrm { H } } \vec { \mathrm { H } } \vec { \Sigma } \vec { \Sigma } \mathrm { I } ] \vec { \mathcal { H } } \vec { \mathcal { H } } \cdot \vec { \mathcal { L } } \langle \mathrm { H } \cdot \mathcal { L } _ { \boxdot { \Xi } } \vec { \mathrm { H } } \vec { \Gamma } \vec { \mathcal { H } } \rvert \vec { \mathcal { H } } \rvert \tilde { \Xi } \mathrm { H } \sharp \sharp \breve { \mathrm { H } } \sharp \breve { \Sigma } _ { \boxdot { \Xi } } \frac { \nu _ { \mathrm { m } } ^ { \prime } \nu _ { \mathrm { m } } ^ { \prime } \nu _ { \mathrm { m } } ^ { \prime } \nu _ { \mathrm { m } } ^ { \prime } } { \mathcal { H } } \rangle \mathrm { H }
$$

其中： $\rho _ { k } \left( t \right)$ 为第 $k$ 个用户在第 $t$ 小时的实时电价， $\$ 123,456$ ； $d _ { k } \left( t \right)$ 为第 $k$ 个用户在第 $t$ 小时的电量需求， $\mathbf { k W h }$ 。

上式在求导时应满足以下约束：

电能平衡：总发电量等于总负荷加损耗；  
发电限制：第 $t$ 小时的总需求不能超过该小时所有发电厂的可用容量之和;  
基尔霍夫定律：电力潮流及损耗应满足电路定律；  
线路潮流极限：任何线路潮流不得超过其功率传输极限。

实时电价是基于经典微观经济学中的社会福利最大化原理形成的，在其原始理论中综合考虑了短期与长期、运行与规划，而在实际电力市场中，实时电价往往由安全约束机组组合（Security Constrained Unit Commitment，SCUC）、安全约束经济调度（Security ConstrainedEconomic Dispatch，SCED）等短期运行优化模型求出。但实时电价的计算模型仍采用传统经济调度的分时段功率平衡模型，将整个考察区间分成一系列的周期（cycle)，每个周期又分为若干时段（period)，然后分时段按能量（电量）平衡模型进行计算，由于每个时段的功率（电力）假设为常数，所以能量平衡模型也就是功率平衡模型。如图1所示，在这个过程中，电能商品模型实际上是按如下方式定义的：

将整个负荷曲线下的面积按时段切分成若干"条”，然后每条又分为若干"段”。在1个时段中，成交的发电商各取1"段”（即1个商品)，而按边际价格出清方式，同一时段的各段负荷（所有商品）的结算价是相同的（即该时段成交机组的最高价格)。

![](images/26e20848b6fd81685a4637cc6f4e5bec4cdc8e187153ac6b5881b0be75a24964.jpg)  
图1实时电价理论中的电能商品模型

限于篇幅，本文不对实时电价理论作详细介绍，有兴趣的读者可参考文献[1-3]。

# 3基于实时电价的电力现货市场缺陷与连续时间电能商品模型

基于实时电价理论设计的电力现货市场有以下缺陷：

1）实时电价基于传统的分时调度（或分时功率平衡）模型计算，没有认真处理跨时段(inter-temporal）约束（文献[1]中已提到这个约束，但未进行深入探讨)，因此也忽略了电能生产和消费的时间连续性这个十分重要的特征，在当前风、光等新能源大规模接入和对电力系统灵活性需求急剧升高的情况下，这个问题尤其严重；  
2）假设同一时段的电能商品都是同质的，由于未考虑不同类型发电机组功率的时间动态特征，无法区别基荷、腰荷和峰荷机组区别明显的技术特征及成本构成;  
3）虽然实时电价理论模型包括了从运行到规划的长时间尺度的资源优化[2]，但这样的超大规模优化问题在实际中是无法应用的。实际市场往往采用SCUC（安全约束机组组合）或SCED（安全约束经济调度）模型计算出清电价，并不包括长期发电容量投资的经济信号，无法保证发电容量的充裕性；  
4）电能的生产和用都具有时间连续利性，无论对于发电商还是电力负荷，销售或购买的商品都是具有一定持续时间的"能量块”（energy block)。能量（电量）是发电厂商和电力用户所关注的主要对象，而功率（电力）平衡主要作为电力系统运行的物理约束（主要体现在潮流方程中)。在实时电价理论中，由于未将时间因素纳入商品模型，功率平衡与能量平衡成为等同的，物理约束直接作为市场供需平衡条件，这并不合适；  
5）电量（能量型）型商品（特别是中长期交易的商品）与电力（功率）型商品的特性不同，电量型商品与普通商品更相近，在较长时期内达到供需动态平衡即可；在中长期交易中电量型商品其实是可存储的，主要以煤（或其他燃料）、水库储水等形式存储，这与不能存储的电力型商品形成鲜明对比；  
6）电能作为基础性产品与生产资料的一部分（在我国尤其如此)，保证持续稳定供应是最关键的考虑，不需要片面追求电力市场本身的"最高效率”（特别是短期现货市场的绝对的最高效率）。

为强调时间因素在电能商品中的作用，本文重新定义由（功率，时间）对组成的连续时间电能商品模型 $\left( P , t \right) \left( t _ { 1 } \leq t \leq t _ { 2 } \right)$ ，功率曲线下的面积即为电量，如图2所示。当 $t _ { 2 } = t _ { 1 } + 1$ 并且 $P = { \mathrm { c o n s t } } \left( t _ { 1 } \leq t \leq t _ { 2 } \right)$ 时，即退化为实时电价理论中的分时电能商品模型。由于功率可看成时间的函数，所以该连续时间电能商品模型也可写成 $\begin{array} { r } { \big ( P \big ( t \big ) , t \big ) \big ( t _ { 1 } \leq t \leq t _ { 2 } \big ) } \end{array}$ 的形式，在实时电价定义中的电量（功率）点变成定义于 $\left( t _ { 1 } , t _ { 2 } \right)$ 时间区间的一个函数，需要用无穷维空间上的数学理论（如泛函分析、变分法等）进行分析。引入连续时间电能商品模型后，市场出清的社会福利最大化问题从多阶段静态优化问题变为连续时间的泛函优化问题，求解方法也从Lagrange 方法变为Euler-Lagrange方程的求解。

值得指出的是，实际上麻省理工学院研究团队已经意识到电能生产和利用的时间连续性问题，文献[2]的第4章的附录部分（pp.247\~257）采用时间连续模型研究电力用户的最优用电行为问题，并推导了基于哈密尔顿函数（Hamiltonian）的最优性条件。国内外也有不少其他学者提出了考虑电能商品时间连续性的竞价模型，如文献[5]提出的水平拍卖机制（horizontalauction）、文献[6]提出的分段竞价机制，但均未对基于连续时间商品模型的电力市场基础理论进行深入研究。

![](images/217a3f87e0fe012a78a71246efc64ae1530191b66f0f1b602bcc1781afb0fa00.jpg)  
图2连续时间电能商品模型

# 4基于连续时间商品模型的电力市场建模

仍采用文献[3]中基于社会福利最大化的微观经济学模型来定义电力市场，为便于参照，借鉴该文的变量符号与表达方式，因为本文目的主要是原理性说明，市场模型在该文的基础上进行一定的简化。

# 市场参与者

Bj(j∈φ)为市场参与者j在一个市场周期内的可变成本（效益），其成本（效益）函数为：

$$
B _ { j } = B _ { j } \left( P _ { j } \left( t \right) \right) \ \left( j \in \phi , 0 \leq t \leq \mathrm { T } \right)
$$

其中： $\phi$ 为市场中所有参与者的集合； $B _ { j }$ 为一个关于市场参与者 $j$ 功率曲线 $P _ { j } \left( t \right)$ (t)的泛函。当 $j$ 为发电厂时， $B _ { j } \leq 0$ （即表示发电成本），当 $j$ 为电力用户时， $B _ { j } \geq 0$ 为正值（即表示用电效益)； $\mathrm { \Delta T }$ 为交易期间时长。

# 目标函数

目标函数即为微观经济学中的标准社会福利最大化模型：Max社会福利 $\mathbf { \sigma } = \mathbf { \sigma }$ 电能的使用价值-电能的生产成本

目标函数可写为

$$
\operatorname* { m a x } _ { \mathbf { \gamma } } \ W ( P _ { 1 } , P _ { 2 } \cdots P _ { n } ) = \sum _ { j \in \phi } B _ { j } ( P _ { j } ( t ) ) d t
$$

# 约束条件

只考虑能量平衡约束，即：$\begin{array} { r l } { 0 } & { { } = } \end{array}$ 发电量-网损电量-用电量

能量平衡约束可写为：

$$
0 = e { \left( t \right) } = \sum _ { j } { P _ { j } \left( t \right) } - L { \left( t \right) } \ \left( { j \in { \phi , 0 \leq t \leq \mathrm { T } , L \left( t \right) > 0 } } \right)
$$

注意此式中，时间 $t$ 为连续变量，不再离散化，当 $j$ 为发电厂时， $P _ { j } \left( t \right)$ 为正值，否则为负值， $L ( t )$ 为有功损耗。

参与者行为

采用连续时间电能商品模型后，市场参与者利润最大化模型变为积分（或功率曲线的泛函）形式。实时电价下的利润最大化模型对应于数学上的Riemann（黎曼）积分，而本文引入按负荷持续时间（数学上称为"测度"）定价的利润最大化模型，对应于数学上的Lebesgue（勒贝格)积分。注意按负荷持续时间定价的基本思想在文献[5,6]中已有描述。关于Riemann积分与Lebesgue积分的基础知识参见附录。

1）实时电价下的参与者利润最大化模型（Riemann积分）

假设参与者 $j$ 按随时间变化的实时电价 元;(t)(0≤t≤T)获得收入（对于发电厂）或购买电能（对于电力用户)，参与者的目标即在生产（消费）能力约束下最大化净收入：

$$
\operatorname* { m a x } \ N _ { j } ^ { R } \left( P _ { j } ( t ) \right) = \int _ { t = 0 } ^ { T } [ B _ { j } \left( P _ { j } \left( t \right) \right) + \tilde { \pi } _ { j } \left( t \right) P _ { j } \left( t \right) ] d t
$$

$$
s . t . \ P _ { j } ^ { \operatorname* { m i n } } \left( t \right) \leq P _ { j } \left( t \right) \leq P _ { j } ^ { \operatorname* { m a x } } \left( t \right)
$$

对一个具体的参与者，pmin(t),Pmax(t) 往往是常数(不随时间变化)。

2）按负荷持续时间定价的参与者利润最大化模型（Lebesgue 积分）

假设参与者 $j$ 按由负荷持续时间（测度）决定的价格函数 $\tilde { \pi } _ { j } \left( y \right) \left( P _ { _ j } ^ { \mathrm { { m i n } } } \leq y \leq P _ { _ j } ^ { \mathrm { { m a x } } } \right)$ （本文假设负荷曲线是单调增长的，因此该价格函数也能写为负荷的函数，参见算例）获得收入（对于发电厂）或购买电能（对于电力用户)，参与者的目标即在生产（消费）能力约束下最大化净收入：

$$
\operatorname* { m a x } \ N _ { j } ^ { L } \Big ( m _ { j } ( y ) \Big ) = \int _ { P _ { j } ^ { \operatorname* { m i n } } } ^ { P _ { j } ^ { \operatorname* { m a x } } } [ B _ { j } \left( y \right) \pm \tilde { \pi } _ { j } \left( m _ { j } ( y ) \right) m _ { j } ( y ) ] d y
$$

$$
s . t . \ P _ { j } ^ { \operatorname* { m i n } } \left( t \right) \leq P _ { j } \left( t \right) \leq P _ { j } ^ { \operatorname* { m a x } } \left( t \right)
$$

式中 $m _ { j } ( y ) = m \big \{ t : P _ { j } ( t ) > y \big \}$ y为函数值为y时对应的测度，当j为发电厂时，元(m(y))前取加号，否则取减号。

# 商品模型

在两种不同的定价方式下，电能商品模型也有所区别。实时电价下，一段时间$t \left( t _ { 1 } \leq t \leq t _ { 2 } \right)$ 内参与者 $j$ 的功率曲线 $P _ { j } \left( t \right) \left( j \in \phi , t _ { 1 } \leq t \leq t _ { 2 } \right)$ 被视为其所销售（或购买）的"一个"商品，其总价格为 $\int _ { \tau = t _ { 1 } } ^ { t _ { 2 } } \tilde { \pi } _ { j } \left( \tau \right) P _ { j } \left( \tau \right) d \tau$ ，而我们可以进一步定义该商品的单位电

能量价格：

$$
\begin{array} { c } { { \displaystyle \displaystyle \displaystyle \displaystyle \int _ { j } ^ { t _ { j } } \tilde { \pi } _ { j } \left( \tau \right) P _ { j } \left( \tau \right) d \tau } } \\ { { \displaystyle \tilde { \pi } _ { j } = \frac { \tau - t _ { 1 } } { \displaystyle \int _ { \tau = t _ { 1 } } ^ { t _ { 2 } } P _ { j } \left( \tau \right) d \tau } } } \end{array}
$$

按负荷持续时间定价的方式下，一定功率范围 P,(t)(P≤t≤P2）内参与者j的“能

量块"被视为其所销售（或购买）的"一个"商品，即

$$
\overline { { P } } _ { j } ( t ) = \{ { P } _ { j } ( t ) : P _ { 1 } \leq P _ { j } ( t ) \leq P _ { 2 } \atop P _ { 2 } : P _ { j } ( t ) > P _ { 2 }  ( j \in \phi , t \in \{ t : P _ { j } ( t ) \geq P _ { 1 } \} )
$$

其总价格为 $\int _ { P _ { 1 } } ^ { P _ { 2 } } \tilde { \pi } _ { j } \left( y \right) m _ { j } ( y ) d y$ 而该商品的单位电能量价格为：

$$
\tilde { \pi } _ { j } = \frac { \displaystyle \int _ { P _ { 1 } } ^ { P _ { 2 } } \tilde { \pi } _ { j } \left( y \right) m _ { j } \left( y \right) d y } { \displaystyle \int _ { P _ { 1 } } ^ { P _ { 2 } } m _ { j } \left( y \right) d y }
$$

# 市场机制

整个市场优化的目标即在式(2)表示的约束条件下使式(1)表示的社会福利最大化，很显然该问题是一个关于 $P _ { j } \left( t \right) \left( j \in \phi , 0 \leq t \leq \mathrm { T } \right)$ 的变分问题，根据其最优性条件将得到其对偶变量（影子价格）λ(t)°

在基于实时电价的市场机制中，直接将 $\lambda ( t )$ 作为参与者 $j$ 的市场价格 $\tilde { \pi } _ { j } ( t )$ ，使得元,(t)=λ(t)，此即市场均衡价格，此时参与者的个体最优(3)与市场总体最优(1)是一致的。

在按负荷持续时间定价的市场机制中，需要另外寻求参与者 $j$ 的市场价格$\tilde { \pi } _ { j } \big ( m _ { j } ( y ) \big )$ ，并且使得所有 $\tilde { \pi } _ { j } \big ( m _ { j } ( y ) \big ) \big ( j \in \phi \big )$ 相等，即为市场均衡价格，此时参与者的个体最优(4)与市场总体最优(1)是一致的。下面将以具体模型的求解和算例分析来说明。

# 5基于连续时间商品模型的电力市场模型求解

为求解和分析方便，本文暂考虑发电侧单边竞价模型，假设发电厂成本函数取为二次函数形式，并且忽略网损，此时(1)、(2)的社会福利最大问题变为以下发电成本最小的问题，即：

$$
\begin{array} { l } { \displaystyle \operatorname* { m i n } \ C ( P _ { 1 } , P _ { 2 } \cdots P _ { n } ) = \sum _ { j = 1 } ^ { n } \int _ { 0 } ^ { T } C _ { j } ( P _ { j } ( t ) ) d t } \\ { \displaystyle \quad \quad = \sum _ { j = 1 } ^ { n } \int _ { 0 } ^ { T } \Big ( a _ { j } P _ { j } \left( t \right) ^ { 2 } + b _ { j } P _ { j } \left( t \right) + c _ { j } \Big ) d t } \\ { \displaystyle \quad \quad s . t . \sum _ { j = 1 } ^ { n } P _ { j } \left( t \right) = P _ { d } \left( t \right) \left( 0 \le t \le \mathrm { T } \right) } \end{array}
$$

式中P $P _ { d } \left( t \right)$ 为 $t$ 时刻的系统负荷。

首先求解带一个约束条件的变分问题(7)，列出Euler-Lagrange方程为

$$
\{ \begin{array} { l l } { C _ { 1 } ( P _ { 1 } ( t ) ) - \lambda ( t ) = 0 } \\ { C _ { 2 } ( P _ { 2 } ( t ) ) - \lambda ( t ) = 0 } \\ { \qquad \vdots } \\ { C _ { n } ( P _ { n } ( t ) ) - \lambda ( t ) = 0 } \\ { \qquad \displaystyle \lfloor \sum _ { j = 1 } ^ { n } P _ { j } ( t ) - P _ { d } ( t ) = 0 } \end{array} 
$$

从上式第 $j$ 个方程中我们能通过 $\lambda ( t )$ 来表示 $P _ { j } ( t ) \ { \big ( } j { = } 1 , \cdots , n { \big ) }$ 将諾 $P _ { 1 } ( t )$ 到發 $P _ { n } ( t )$ 的表达式代入最后功率平衡方程，即可求出λ(t)，继而求出所有的P(t)到Pn(t)。

其次求解Riemann 积分意义下的变分问题(3)，暂不考虑功率约束条件限制，把变分问题(3)看成无约束变分问题来求解，并写出其 Euler-Lagrange 方程为

$$
C _ { j } ^ { \prime } \big ( P _ { j } \left( t \right) \big ) - \tilde { \pi } _ { j } \left( t \right) = 0
$$

比较(8)和(9)，得到

$$
\tilde { \pi } _ { j } \left( t \right) = \lambda ( t )
$$

$\lambda ( t )$ 即市场均衡价格。

在成本函数取为二次函数形式时，可以求得

$$
\lambda ( t ) = C _ { j } \cdot \left( P _ { j } \left( t \right) \right) = 2 a _ { j } P _ { j } \left( t \right) + b _ { j } = \frac { P _ { d } \left( t \right) } { \displaystyle \sum _ { j = 1 } ^ { n } \frac { 1 } { 2 a _ { j } } } + \frac { \displaystyle \sum _ { j = 1 } ^ { n } \frac { b _ { j } } { 2 a _ { j } } } { \displaystyle \sum _ { j = 1 } ^ { n } \frac { 1 } { 2 a _ { j } } }
$$

体现出实时电价 $\lambda ( t )$ 与负荷曲线 $P _ { d } ( t )$ 一致。

最后，我们来考虑Lebesgue 积分意义下的变分问题(4)，在负荷曲线单调增长和发电侧单边竞价的假设条件下，(4)可以写为如下形式：

$$
\mathrm { m i n } N _ { j } ^ { L } \left( P _ { j } \right) = \int _ { P _ { \mathrm { m i n } } } ^ { P _ { \mathrm { m a x } } } [ ( \mathrm { T } - P _ { j } ^ { - 1 } \left( y \right) ) C _ { j } ^ { \prime } \left( y \right) - \tilde { \pi } _ { j } \left( \mathrm { T } - P _ { j } ^ { - 1 } ( y ) \right) m _ { j } ( y ) ] d y
$$

$m _ { j } ( y ) = m \big \{ t : P _ { j } ( t ) > y \big \}$ 为函数值为 $y$ 时对应的测度，式中

$$
P _ { \operatorname* { m a x } } = \operatorname* { m a x } _ { t \in [ 0 , \tau ] } \{ P ( t ) \} ^ { } \qquad P _ { \operatorname* { m i n } } = \underset { t \in [ 0 , \mathrm { ~ \tau ~ r ~ } ] } { \operatorname* { m i n } } \mathcal { \boldsymbol { R } } ^ { } \enspace \dot { \boldsymbol { \mathcal { t } } } ^ { }
$$

这里

$$
\begin{array} { l } { { \displaystyle \int _ { P _ { \mathrm { m i n } } } ^ { P _ { \mathrm { m a x } } } [ \mathrm { T } { - } P _ { j } ^ { - 1 } \left( y \right) ] C _ { j } ^ { \prime } \left( y \right) d y + C _ { j } ( P _ { \mathrm { m i n } } ) T \begin{array} { r l } { { } } & { { } } \\ { { = \displaystyle \int _ { C _ { j } ( P _ { \mathrm { m a x } } ) } ^ { C _ { j } ( P _ { \mathrm { m a x } } ) } [ \mathrm { T } { - } P _ { j } ^ { - 1 } C _ { j } ^ { - 1 } \left( h \right) ] d h + C _ { j } ( P _ { \mathrm { m i n } } ) T } } \\ { { } } & { { } } \\ { { = \displaystyle \int _ { t = 0 } ^ { T } C _ { j } \left( P _ { j } \left( t \right) \right) d t } } \end{array} } } \end{array}
$$

为成本。

在成本函数取为二次函数形式时，由(11)可知， $P _ { j } ( t )$ 为严格单调递增函数，此时$m _ { j } ( P _ { j } ( t ) ) = \mathrm { T } - t$ 。我们可以做变量替换 $P _ { j } \left( t \right) = y$ ，则(12)转化为如下变分问题：

$$
\begin{array} { r l r } & { } & { \mathrm { m a x } ~ N _ { j } ^ { L } \left( P _ { j } \right) = { \displaystyle \int _ { 0 } ^ { \mathrm { T } } } [ ( \mathrm { T } - t ) C _ { j } ^ { \prime } \left( P _ { j } \left( t \right) \right) - \tilde { \pi } _ { j } \left( t \right) m _ { j } ( P _ { j } \left( t \right) ) ] P ^ { \prime } { } _ { j } \left( t \right) d t } \\ & { } & { = { \displaystyle \int _ { 0 } ^ { \mathrm { T } } } [ ( \mathrm { T } - t ) ( 2 a _ { j } P _ { j } \left( t \right) + b _ { j } ) - \tilde { \pi } _ { j } \left( t \right) ( \mathrm { T } - { \sf t } ) ] P ^ { \prime } { } _ { j } \left( t \right) d t } \end{array}
$$

写出其Euler-Lagrange方程为

$$
2 { \bf a } _ { j } P ^ { \prime } _ { j } \left( t \right) ( T - t ) + \frac { d } { d t } [ ( \mathrm { T } - t ) ( 2 a _ { j } P _ { j } \left( t \right) + b _ { j } ) - \tilde { \pi } _ { j } \left( t \right) \left( T - t \right) ] = 0
$$

解关于 $\tilde { \pi } _ { j } \left( t \right)$ 的一阶线性常微分方程(14)，即可得到价格函数 $\tilde { \pi } _ { j } \left( t \right) ^ { \circ }$ （204号

另一方面，由(11)可知，

$$
P _ { j } \left( t \right) = \frac { 1 } { 2 a _ { j } } ( \frac { P _ { d } \left( t \right) } { \displaystyle \sum _ { j = 1 } ^ { n } \frac { 1 } { 2 a _ { j } } } + \frac { \displaystyle \sum _ { j = 1 } ^ { n } \frac { b _ { j } } { 2 a _ { j } } } { \displaystyle \sum _ { j = 1 } ^ { n } \frac { 1 } { 2 a _ { j } } } - b _ { j } ) ,
$$

故可知(14)的系数和非线性项

$$
2 a _ { j } P _ { j } ^ { ' } \left( t \right) = \frac { P _ { d } ^ { ' } \left( t \right) } { \displaystyle \sum _ { j = 1 } ^ { n } \frac { 1 } { 2 a _ { j } } } , 2 a _ { j } P _ { j } \left( t \right) + b _ { j } = \lambda ( t )
$$

均与 $j$ 无关，由此可以得到(14)的解与 $j$ 无关，则所有电厂的价格是相同的，即

$$
\tilde { \pi } _ { j } \left( t \right) = \pi \left( t \right)
$$

此即按负荷持续时间定价的市场均衡价格。

# 6算例分析

假设负荷单调增长，考虑负荷曲线如下

$$
P _ { d } ( t ) = 3 5 0 \times ( 1 + 2 t ) \ \left( t \in [ 0 , 1 ] \right)
$$

假设市场中有3个电厂，成本依次相差2倍，分别代表低、中、高成本（基荷、腰荷、峰荷）电厂，成本函数如下（取 $a = 0 . 0 0 1 , b = 0 . 0 7$ $c = 0 . 2$ ）

$$
\begin{array} { l } { \displaystyle { C _ { 1 } \big ( P _ { 1 } \big ( t \big ) \big ) = \frac { a } { 2 } P _ { 1 } \big ( t \big ) ^ { 2 } + b P _ { 1 } \big ( t \big ) + c } } \\ { \displaystyle { C _ { 2 } \big ( P _ { 2 } \big ( t \big ) \big ) = a P _ { 2 } \big ( t \big ) ^ { 2 } + 2 b P _ { 2 } \big ( t \big ) + 2 c } } \\ { \displaystyle { C _ { 3 } \big ( P _ { 3 } \big ( t \big ) \big ) = 2 a P _ { 3 } \big ( t \big ) ^ { 2 } + 4 b P _ { 3 } \big ( t \big ) + 4 c } } \end{array}
$$

由(8)式解得，实时电价 $\lambda ( t )$ 与各电厂的负荷 $P _ { i } ( t )$ 为

$$
\begin{array} { l l } { { \lambda ( t ) = C _ { 1 } ^ { \ast } \big ( P _ { 1 } \big ( t \big ) \big ) = a P _ { 1 } \big ( t \big ) + b , } } & { { \quad P _ { 1 } \big ( t \big ) = \frac { \mathtt { r } } { 7 } P _ { d } ( t ) + \frac { \mathtt { s } \nu } { 7 a } = 2 5 0 + 4 0 0 t , } } \\ { { \lambda ( t ) = C _ { 2 } ^ { \ast } \big ( P _ { 2 } \big ( t \big ) \big ) = 2 a P _ { 2 } \big ( t \big ) + 2 b , } } & { { \quad P _ { 2 } \big ( t \big ) = \frac { 2 } { 7 } P _ { d } ( t ) - \frac { b } { 7 a } = 9 0 + 2 0 0 1 , } } \\ { { \lambda ( t ) = C _ { 3 } ^ { \ast } \big ( P _ { 3 } \big ( t \big ) \big ) = 4 a P _ { 3 } \big ( t \big ) + 4 b , } } & { { \quad P _ { 3 } \big ( t \big ) = \frac { 1 } { 7 } P _ { d } ( t ) - \frac { 4 b } { 7 a } = 1 0 + 1 0 0 t , } } \end{array}
$$

可求得3个电厂的发电成本分别为：

$$
\begin{array} { r l } & { C _ { 1 } = \int _ { 0 } ^ { 1 } \Bigg ( \frac { a } { 2 } P _ { 1 } \big ( t \big ) ^ { 2 } + b P _ { 2 } \big ( t \big ) + c \Bigg ) d t } \\ & { = \int _ { 0 } ^ { 1 } \Bigg ( \frac { a } { 2 } \big ( 2 5 0 + 4 0 0 t \big ) ^ { 2 } + b \big ( 2 5 0 + 4 0 0 t \big ) + c \Bigg ) d t } \\ & { = 1 0 7 . 9 2 + 4 5 0 b + c = 1 3 9 . 6 3 } \\ & { C _ { 2 } = \int _ { 0 } ^ { 1 } \Bigg ( a P _ { 2 } \big ( t \big ) ^ { 2 } + 2 b P _ { 2 } \big ( t \big ) + 2 c \bigg ) d t } \\ & { = \int _ { 0 } ^ { 1 } \Bigg ( a \big ( 9 0 + 2 0 0 t \big ) ^ { 2 } + 2 b \big ( 9 0 + 2 0 0 t \big ) + 2 c \bigg ) d t } \\ & { = 3 9 . 4 3 + 3 8 0 b + 2 c = 6 6 . 4 6 } \end{array}
$$

$$
C _ { 3 } = \int _ { 0 } ^ { 1 } \Bigl ( 2 a P _ { 3 } \left( t \right) ^ { 2 } + 4 b P _ { 3 } \left( t \right) + 4 c \Bigr ) d t
$$

$$
= \int _ { 0 } ^ { 1 } \Bigl ( 2 a \bigl ( 1 0 + 1 0 0 t \bigr ) ^ { 2 } + 4 b \bigl ( 1 0 + 1 0 0 t \bigr ) + 4 c \Bigr ) d t
$$

$$
= 8 . 8 6 + 2 4 0 b + 4 c = 2 6 . 4 4
$$

1）实时电价下的收入及利润分析

另外可计算得实时电价下3个电厂售电收入分别为

$$
N _ { 1 } ^ { R } \left( P _ { 1 } \right) = \int _ { t = 0 } ^ { 1 } \lambda \left( t \right) P _ { 1 } \left( t \right) d t = \int _ { t = 0 } ^ { 1 } [ 0 . 3 2 + 0 . 4 t ] ( 2 5 0 + 4 0 0 { \mathrm t } ) d t = 2 4 7 . 3 2
$$

$$
N _ { 2 } ^ { R } \left( P _ { 2 } \right) = \int _ { t = 0 } ^ { 1 } \lambda \left( t \right) P _ { 2 } \left( t \right) d t = \int _ { t = 0 } ^ { 1 } \left[ 0 . 3 2 + 0 . 4 t \right] \left( 9 0 + 2 0 0 { \mathrm { t } } \right) d t = 1 0 5 . 5 2
$$

$$
N _ { 3 } ^ { R } \left( P _ { 3 } \right) = \intop _ { t = 0 } ^ { 1 } \lambda \left( t \right) P _ { 3 } \left( t \right) d t = \intop _ { t = 0 } ^ { 1 } \left[ 0 . 3 2 + 0 . 4 t \right] \left( 1 0 + 1 0 0 \mathrm { t } \right) d t = 3 4 . 4 8
$$

计算得各电厂利润分别如下：107.69、39.06、8.04，利润率分别为 $7 7 \%$ 、 $5 9 \%$ 、 $30 \%$

（利润/成本 $. \times 1 0 0 \%$ )。而市场总购电费用为387.32，3个电厂总发电成本为232.53，3个电厂总利润为154.79，市场总利润率为 $67 \%$ （总利润/总成本 $. \times 1 0 0 \%$ ）。

2）按负荷持续时间定价方式下的市场价格、收入及利润分析由于 $m _ { j } ( P _ { j } \left( t \right) ) = 1 - t , { \mathrm {  ~ a ~ } } _ { j } { P ^ { \prime } } _ { j } \left( t \right) = 0 . 2 \left( j = 1 , 2 , 3 \right)$ 将数据代入相应的 Euler-Lagrange 方程(14)，有：$2 { \bf a } _ { j } ( 1 - t ) { \cal P } _ { \ j } ^ { \prime } \left( t \right) + \frac { d } { d t } [ ( 1 - t ) ( 2 a _ { j } P _ { j } \left( t \right) + b _ { j } ) - \tilde { \pi } _ { j } \left( t \right) \left( 1 - t \right) ] = 0$ 整理得常微分方程

$$
\tilde { \pi } _ { j } ^ { \prime } \left( t \right) \left( 1 - t \right) - \tilde { \pi } _ { j } \left( t \right) + 1 . 2 t - 0 . 4 8 = 0 \left( j = 1 , 2 , 3 \right)
$$

可解得

$$
\begin{array} { l } { { \displaystyle \tilde { \pi } _ { j } \left( t \right) = \mathbf { C } e ^ { \int _ { } ^ { 1 } \frac { 1 } { 1 - t } } + e ^ { \int _ { } ^ { 1 } \frac { 1 } { 1 - t } } \int ( 1 . 2 - \frac { 0 . 7 2 } { 1 - t } ) e ^ { - \int _ { } ^ { 1 } \frac { 1 } { 1 - t } } d t } \ ~ } \\ { { \displaystyle \qquad = \mathbf { C } ( 1 - t ) ^ { - 1 } + ( 1 - t ) ^ { - 1 } \int [ 1 . 2 ( 1 - t ) - 0 . 7 2 ] d t } \ ~ } \\ { { \displaystyle \qquad = \mathbf { C } ( 1 - t ) ^ { - 1 } + ( 1 - t ) ^ { - 1 } ( 0 . 4 8 t - 0 . 6 t ^ { 2 } ) } } \\ { { \displaystyle \qquad \left( t \in [ 0 , 1 ) , j = 1 , 2 , 3 \right) } } \end{array}
$$

$\tilde { \pi } _ { j } \left( 0 \right) { = } \lambda ( 0 )$ 则 $C \ = 0 . 3 2$ 。即

$$
\pi \left( t \right) = \tilde { \pi } _ { j } \left( t \right) = 0 . 3 2 ( 1 - t ) ^ { - 1 } + \left( 1 - t \right) ^ { - 1 } ( 0 . 4 8 t - 0 . 6 t ^ { 2 } ) \left( t \in [ 0 , 1 ) , \ j = 1 , 2 , 3 \right)
$$

由于测度 $m = 1 - t$ ，则

$$
\pi _ { j } \left( m \right) = \tilde { \pi } _ { j } \left( 1 - t \right) = 0 . 3 2 m ^ { - 1 } + m ^ { - 1 } ( 0 . 4 8 ( 1 - m ) - 0 . 6 ( 1 - m ) ^ { 2 } ) \left( m \in ( 0 , 1 ] , j = 1 , 2 , 3 \right)
$$

将算例数据代入(12)式，得到对应的测度函数为：

$$
\begin{array} { l } { { m _ { 1 } ( y ) = \displaystyle \frac { 6 5 0 - y } { 4 0 0 } , ~ \mathrm { y } \in [ 2 5 0 , 6 5 0 ] } } \\ { { } } \\ { { m _ { 2 } ( y ) = \displaystyle \frac { 2 9 0 - y } { 2 0 0 } , ~ \mathrm { y } \in [ 9 0 , 2 9 0 ] } } \\ { { } } \\ { { m _ { 3 } ( y ) = \displaystyle \frac { 1 1 0 - y } { 1 0 0 } , ~ \mathrm { y } \in [ 1 0 , 1 1 0 ] } } \end{array}
$$

因此按负荷持续时间定价时3个电厂售电收入分别为：

$$
\begin{array} { l } { { N _ { 1 } ^ { L } \left( P _ { 1 } \right) = \displaystyle \int _ { 2 5 0 } ^ { 6 5 0 } \pi _ { 1 } ( m _ { 1 } ( y ) ) m _ { 1 } ( y ) d y + 0 . 3 2 \times 2 5 0 } } \\ { { \ \quad \ } } \\ { { \quad \ = \displaystyle \int _ { 2 5 0 } ^ { 6 5 0 } \left[ 0 . 3 2 + ( 0 . 4 8 ( 1 - m _ { 1 } ( y ) ) - 0 . 6 ( 1 - m _ { 1 } ( y ) ) ^ { 2 } ) \ \right] d y + 0 . 3 2 \times 2 5 0 } } \\ { { \ \ \quad \ } } \\ { { \quad \ = \displaystyle \int _ { 2 5 0 } ^ { 6 5 0 } \left[ 0 . 2 + 0 . 7 2 m _ { 1 } ( y ) - 0 . 6 m _ { 1 } ( y ) ^ { 2 } \ \right] d y + 8 0 } } \\ { { \ \quad \ = 2 2 4 } } \end{array}
$$

$$
\begin{array} { l } { { \displaystyle N _ { 2 } ^ { L } \left( P _ { 2 } \right) = \int _ { 9 0 } ^ { 2 9 0 } \pi _ { 2 } ( m _ { 2 } ( y ) ) m _ { 2 } ( y ) d y + 0 . 3 2 \times 9 0 } } \\ { { \displaystyle \qquad = \int _ { 9 0 } ^ { 2 9 0 } [ 0 . 4 + 0 . 7 2 m _ { 2 } ( y ) - 0 . 8 m _ { 2 } ( y ) ^ { 2 } \ ] \ d y + 9 8 . 8 } } \\ { { \displaystyle \qquad = 1 0 0 . 8 4 } } \end{array}
$$

$$
\begin{array} { l } { { \displaystyle N _ { 3 } ^ { L } \left( P _ { 3 } \right) = \int _ { 1 0 } ^ { 1 1 0 } \pi _ { 3 } ( m _ { 3 } ( y ) ) m _ { 3 } ( y ) d y + 0 . 3 2 \times 1 0 } } \\ { { \displaystyle ~ } } \\ { { \displaystyle ~ = \int _ { 1 0 } ^ { 1 1 0 } [ 0 . 4 + 0 . 7 2 m _ { 3 } ( y ) - 0 . 8 m _ { 3 } ( y ) ^ { 2 } ~ ] ~ d y + 3 . 2 } } \\ { { \displaystyle ~ } } \\ { { \displaystyle ~ = 3 9 . 1 6 } } \end{array}
$$

此处

$$
{ \begin{array} { l } { \int _ { 2 \leq 0 } ^ { \infty } m _ { 1 } ( y ) d y = { \int _ { 2 \leq 0 } ^ { \infty } { \frac { ( y - 0 ) - y } { 4 ( 0 0 ) } } d y } = 2 0 0 } \\ { \int _ { 2 \leq 0 } ^ { \infty } m _ { 1 } ( y ) ^ { 2 } d y = 1 3 3 . 3 3 3 } \\ { } \\ { \int _ { 9 0 } ^ { \infty } m _ { 2 } ( y ) d y = \int _ { \infty } ^ { \infty } { \frac { 2 9 0 - y } { 2 0 ( 0 ) } } d y = 1 0 0 } \\ { \int _ { 9 0 } ^ { \infty } m _ { 2 } ( y ) ^ { 2 } d y = 6 6 . 6 7 } \\ { \int _ { 1 0 } ^ { 1 0 } m _ { 1 } ( y ) d y = \int _ { 1 0 } ^ { 1 1 } { \frac { 1 1 0 - y } { 1 0 0 } } d y = 5 0 } \\ { \int _ { 1 0 } ^ { 1 1 } m _ { 1 } ( y ) ^ { 2 } d y = 3 3 . 3 3 3 } \end{array} }
$$

计算得3个电厂利润分别为：84.37、34.38、12.72，利润率分别为 $60 \%$ 、 $5 2 \%$ 、 $48 \%$ 。而市场总购电费用为364，3个电厂总发电成本为232.53，3个电厂总利润为131.47，市场总利润率为 $57 \%$ 。

从上述算例可以看出，由于无法区分基荷、腰荷和峰荷不同的电能，在实时电价下，3个电厂利润相差悬殊，基荷电厂分配得过多的利润。按负荷持续时间定价能减少市场总购电费用，而且电厂利润分配较为公平，与实时电价机制相比，减少了基荷电厂的利润，增加了峰荷电厂的利润。由于两种定价方式各有优缺点，以后的研究中将考虑两者定价方式相结合的市场机制。

# 7 结论

当前的电力市场改革急需电能商品及市场交易的基础理论研究。本文在分析国外基于实时电价（spotpricing）理论的电力现货市场缺陷的基础上，提出连续时间电能商品模型，包括实时电价下和按负荷持续时间定价的方式下的电能商品模型，并建立了基于社会福利最大化的电力市场模型；进一步将实时电价下和按负荷持续时间定价的市场优化模型与数学上的Riemann 积分和Lebesgue 积分相对应，基于各自的 Euler-Lagrange 方程求得市场均衡解，特别通过严格的数学推导证明了按负荷持续时间定价的可行性；最后以一个算例验证了所提理论和方法的合理性。本文所提的理论和方法有望为国内外电力市场建设提供全新的思路和理论基础。

# 参考文献：

[1]F.C.Schweppe,M.C.Caramanis,R.D.Tabors,R.E.Bohn. Spot Pricing of Electricity. Boston: Kluwer Academic Publishers,1988.   
[2] R.E. Bohn. Spot Pricing of Public Utility Services. Doctoral thesis,Massachusets Institute of Technology, 1982.   
[3] M.C. Caramanis,R.E. Bohn,F C. Schweppe. Optimal Spot Pricing: Practice and Theory. IEEE Transactions on Power Apparatus and Systems, Vol. PAS-101,No. 9,1982, pp. 3234-3245.   
[5]W.Elmaghrabyand S.S.Oren.TheEfficiencyof Multi-Unit Electricity Auctions.The EnergyJournal,Vol.20, No. 4,1999,pp.89-116.   
[6] 王锡凡．分段竞价的电力市场．中国电机工程学报.Vol.21，No.12，2001，pp.1-6.

(通讯作者：陈皓勇E-mail:eehychen@scut.edu.cn)

# 作者贡献声明

陈皓勇：提出基于连续时间商品模型的电力市场理论及研究思路，建立市场优化模型，论文起草和最终版本修订；韩励佳：基于连续时间商品模型的电力市场模型求解，公式推导与算例验证。

# 附录：黎曼积分与勒贝格积分的基本概念

# 1、黎曼（Riemann）积分

高等数学和微积分中介绍的常规积分即Riemann 积分，Riemann 的定积分定义如下：函数 $f ( x ) ^ { \overleftrightarrow { \mathbb { E } } \boxed { \times } \boxed { \boxplus } } \left[ a , b \right]$ 上有定义，任意用分点

$$
a = x _ { 0 } < x _ { 1 } < x _ { 2 } < \dots < x _ { \ n - 1 } < x _ { n } = b
$$

将区间 $\left[ a , b \right]$ 划分成 $n$ 个小区间 $\left[ x _ { i - 1 } , x _ { i } \right]$ ]，且每个小区间的长度为△x²=x－χi-1’ ，，在每个小区间上任取一点 $\xi _ { i }$ ，且 $\left( x _ { i - 1 } \leq \xi _ { i } \leq x _ { i } \right) ^ { \prime } \ \left( i = 1 , 2 , \cdots , n \right)$ ，作和式

$$
\sum _ { i = 1 } ^ { n } f ( \xi _ { i } ) \Delta x _ { i }
$$

记

$$
\lambda = \operatorname* { m a x } _ { 1 \leq i \leq n } \left\{ \Delta x _ { i } \right\} ^ { \prime }
$$

如果当 $\lambda \to 0$ 时，上述和式的极限存在，则称函数 $f ( x )$ 在区间 $\left[ a , b \right]$ 上可积，并称此极限值为函数 $f ( x )$ （204号在区间 $\left[ a , b \right]$ 上的定积分，记作 $\int _ { a } ^ { b } f ( x ) d x$ 即

$$
\int _ { a } ^ { b } f ( x ) d x { = } \operatorname* { l i m } _ { \lambda  0 } \sum _ { i { = 1 } } ^ { n } f ( x ) \Delta x _ { i }
$$

费 $f ( x )$ 称为被积函数， $f ( x ) d x$ 称为被积表达式， $x$ 称为积分变量，记号"f"称为积分号，区间 $\left[ a , b \right]$

称为积分区间， $a$ 与 $b$ 分别称为积分下限和积分上限，和式 $\sum _ { i = 1 } ^ { n } f ( \xi _ { i } ) \Delta x _ { i }$ 称为 $f ( x )$ 的积分和。

从 Riemann 积分的定义可以看到，求Riemann 积分的时候，采取一种逼近的方法，包括3个步骤：一为分割，二为近似求和，三为取极限。Riemann 的积分思想就是把区间分成一些小区间，然后构造相应的近似和，再取极限就得到定积分的值。

根据Riemann积分的理论，连续函数是可积的，并且Riemann积分的物理意义是连续函数曲线与 $x$ 轴围成的平面图形的面积，所以Riemann 积分也是计算面积的重要工具。

# 2、勒贝格（Lebesgue）积分

由于Riemann积分意义下可积的函数类太小，Lebesgue 积分通过恰当地改造Riemann 积分的定义使更多的函数可积。

首先我们给出Lebesgue 测度的定义[1]：

先约定集合

$$
\left\{ \left( x _ { 1 } , x _ { 2 } , \cdots , x _ { n } \right) \middle | a _ { i } < x _ { i } < b _ { i } , \forall i = 1 , 2 , \cdots , n \right\}
$$

称为 $R ^ { n }$ 中的开区间，记为 $I$ 。规定 $I$ 的"体积"用 $\left| I \right|$ 来表示，满足勒贝格测度公理[1]。

记

$$
E \in R ^ { n , } \ : \ : \ : m ^ { * } E = \operatorname* { i n f } _ { i } \mathbf { \Sigma } ^ { \mathrm { ~ A ~ } } = \operatorname* { i n f } _ { i } \mathbf { \Sigma } ^ { \mathrm { ~ C ~ } } \sum _ { i } \big | I _ { i } \big | , \frac { \Xi \Xi \mathcal { Z } \ : \exists i \exists \ : \mathcal { Z } \cap \Sigma \ : \{ \forall i \ : \ : \Pi \ : \ : } \ : \{ \mathbf { \Sigma } _ { I } \ : \ : \ : ) \ : ,  \\ { \ : \ : \ : } \ : \cup \ : \ : \ : \ : \bigcup _ { i } \ : = E ^ { \mathbf { \Sigma } ^ { \mathrm { ~ Y ~ } } \cdot \ : \ : \mathbf { \Sigma } }
$$

称这个下确界为Lebesgue 外测度，记为 $m ^ { * } E$ ，因此外测度可以说成是包含 $E$ 的那些开集的测度的下确界。同样地，用闭集填 $E$ 的内部，闭集的余集是开集，因此闭集一定也有测度，用内填闭集的测度的上确界值为 $E$ 的内测度 $m _ { * } E$ 当 $m ^ { * } E ^ { = } m _ { * } E$ 时，称 $E$ 是Lebesgue可测的。

接下来，我们来看Lebesgue 积分的定义[1:

对于有限区间 $\left[ a , b \right]$ 上的有界函数的 Riemann 积分，定义首先是对区间 $\left[ a , b \right]$ 进行分割.而 Lebesgue积分的定义的独特之处是对函数的值域进行分割。

设 $E$ 是一可测集， $m E < + \infty$ ， $f ( x )$ 是 $E$ 上的有界函数，将 $y = f ( x )$ 在区间 $\left[ a , b \right]$ 上的值的下确界 $A$ 和上确界 $B$ 之间的线段分成 $n$ 个小区间：

$$
\left[ { { y } _ { 0 } } , { { y } _ { 1 } } \right] ^ { \mathrm { , ~ } } \left[ { { y } _ { 1 } } , { { y } _ { 2 } } \right] ^ { \mathrm { , ~ } } \cdots , \left[ { { y } _ { i - 1 } } , { { y } _ { i } } \right] ^ { \mathrm { , ~ } } \cdots \left[ { { y } _ { n - 1 } } , { { y } _ { n } } \right]
$$

其中：yo=A’ yn =B°

记 $E _ { i } = \left\{ x { \big | } y _ { i - 1 } \leq f { \big ( } x { \big ) } \leq y _ { i } \right\}$ ，任取 $\xi _ { i } \in \left[ y _ { i - 1 } , y _ { i } \right] \left( i = 1 , 2 , \cdots , n \right)$ ，作和式

$$
S { \big ( } f , D { \big ) } = \sum _ { i = 0 } ^ { n } \xi _ { i } m E _ { i }
$$

记

$$
\lambda = \operatorname* { m a x } \Big \{ | y _ { i } - y _ { i - 1 } | \big \| 1 \leq i \leq n \Big \}
$$

若极限 $\operatorname* { l i m } _ { \lambda \to 0 } S \big ( f , D \big )$ 存在，则称 $f ( x )$ 在 $E$ 上 Lebesgue 可积，称其极限值为 $f ( x )$ 在 $E$ 上的Lebesgue 积分。

Lebesgue积分过程可用图A.1来形象地描述：

要求 $y = f \left( x \right)$ ， $y = 0$ $x = a$ ， $x = b$ 围成的曲边形面积，可以用在值域上横向分割方式形成的矩形面积之和近似地加以表示，即：

$$
{ \begin{array} { r } { { \big ( } b - a { \big ) } { \big ( } y _ { 1 } - y _ { 0 } { \big ) } + { \Big [ } { \big ( } x _ { 4 } - x _ { 1 } { \big ) } + { \big ( } b - x _ { 5 } { \big ) } { \Big ] } { \big ( } y _ { 2 } - y _ { 1 } { \big ) } + } \\ { { \Big [ } { \big ( } x _ { 3 } - x _ { 2 } { \big ) } + { \big ( } b - x _ { 6 } { \big ) } { \Big ] } { \big ( } y _ { 3 } - y _ { 2 } { \big ) } + { \big ( } b - x _ { 7 } { \big ) } { \big ( } y _ { 4 } - y _ { 3 } { \big ) } } \end{array} }
$$

当值域划分越来越细，矩形面积之和也越来越接近于曲边形面积，如果矩形面积之和的极限存在，即为函数 $f \left( x \right)$ 的 Lebesgue 积分。这种积分方式和划分定义域的 Riemann 积分形成对照。

![](images/9ea81d2dffaed5f06b8436d0a35d2adb32a2d6bbff771b4bf8dd797d7b7a666f.jpg)  
图A.1勒贝格积分示意图

[1] 程其襄，张奠宙，魏国强等．实变函数与泛函分析基础(第三版)[M].北京：高等教育出版社，2010.