# 考虑客户价值的卡车与无人机联合配送时变路径优化方法研究

温廷新，吕艳华

(辽宁工程技术大学 工商管理学院，辽宁 葫芦岛 125000)

摘要：针对车辆拥有量的增加和拥堵情况的日益严重导致的物流业配送时效不高、客户价值低等问题，综合考虑客户价值和成本等因素，提出了一种卡车与无人机联合配送时变路径的优化方法。考虑到配送过程中不同时段的拥堵情况，采用速度分布函数刻画车辆的行驶速度，同时考虑客户的时间窗、车辆的载重和无人机的载重等约束条件，建立了成本最小的数学模型。根据模型的特点，引入 $\mathbf { k }$ -means对客户的位置进行聚类，设计混合的粒子群算法对模型进行求解。最后通过 Solomom 数据进行模拟仿真实验，对模型和算法的有效性进行验证。实验结果表明，与未考虑客户价值静态路网模型相比，该模型在降低 $9 . 3 2 \%$ 成本的情况下，同时提高了 $1 6 . 8 3 \%$ 的客户价值和 $2 1 . 2 8 \%$ 的客户满意度，所提算法在降低配送成本和提高企业经济效益方面具有一定的有效性。

关键词：车载无人机；客户价值；时变路网；k-means聚类；联合配送；混合粒子群算法 中图分类号：TP301.6;U126 doi:10.19734/j.issn.1001-3695.2022.03.0100

Research on time-varying route optimization method for truck and UAV joint delivery considering customer value

Wen Tingxin, Lyu Yanhua+ (Schoolof BusinessAdministration,Liaoning Technical University,Huludao Liaoning25ooo,China)

Abstract: Aiming at the problems oflow timelessness and low customer valuecaused bythe increase of vehicle ownership andcongestion,the paperproposesatme-varyingrouteoptimizationmethodoftruckandUAVjointdeliveryafterconsidering thefactors ofcustomervalueandcost.Considering thecongestionindifferent time periodsinthedeliveryprocess,ituses the sped distributionfunction todescribe thevehicle speedandtheconstraintssuchascustomertime windowand it takes vehicle loadand UAVload intoaccounttoestablishamathematicalmodel withminimumcost.According tothecharacteristicsofthe model, it introduces $\mathbf { k }$ -means to cluster customers'locations and designes a hybrid particle swarm optimization algorithm to solvethe model.Finally,the paperuses Solomomdatatoconduct simulation experiments to verifythe validityofthe model and algorithm.The experimental results show that compared with static network model without considering customer value, the model can reduce $9 . 3 2 \%$ cost, improve $1 6 . 8 3 \%$ customer value and $2 1 . 2 8 \%$ customer satisfaction,and the algorithm proposed in this paper hascertain effectiveness inreducing distributioncostand improving enterprise economic benefits.

Keywords:vehicle UAV; customer value; time-varying road network; $\mathbf { k } -$ means clustering; joint distribution;hybrid particle swarm optimization

# 0 引言

随着电子商务的发展，如何提高商品配送效率、降低物流成本，成为整个物流行业面临的关键问题。在此背景下，技术的发展和需求的更迭，将高效率、低成本的无人机用于物流配送成为物流行业内研究的热点。然而，无人机存在负载小、飞行距离短等局限，导致无人机无法独立完成大规模的物流配送任务，因此卡车与无人机联合配送模式成为物流行业降本增效的必然选择。

近年来，国内外关于卡车与无人机联合配送路径问题的研究主要针对模型的建立和求解算法的设计两方面。从模型的建立方面，Murray等[1]首次将卡车和无人机结合，建立了卡车与无人机联合的旅行商问题的混合整数规划数学模型。在此基础上，Semiz等2将客户时间窗作为约束条件，建立了带时间窗的卡车与无人机的路径模型。朱晓宁等[3]根据车辆限行和空域禁飞的情况，将区域限制因素嵌入到模型的构建当中。彭勇等[4在疫情背景下，以配送商品时间最短为优化目标，设计混合邻域搜索算法求解无人机为多个客户无接触配送的路径问题。张得志等5从低碳与随机需求两方面出发，建立了多目标模型。杜茂康等[6在实际物流配送要求的前提下，将多车场作为配送的场景因素。

为进一步求解数学模型，多数学者采用改进的启发式智能优化算法进行求解。Salama等7为优化卡车与无人机的配送路线，提出了一种基于无监督机器学习的启发式算法来加快求解速度。王新等[8]为提高客户的满意度，综合考虑无人机站点和客户时间窗要求，建立以总成本最小化为目标的问题模型，并设计自适应大规模邻域搜索算法进行求解。邓永龚[9]等在自然灾害情境下建立卡车与无人机联合配送冷链物流优化模型，采用进化逆转操作，并设计改进的遗传算法。唐立等[10]利用泰森多边物理概念，改进蚁群算法，对考虑路径安全的山区无人机路径模型进行求解。李妍峰等[改进变邻域搜索算法求解需求可拆分的路径问题。曹英英等[12]利用遗传模拟退火两阶段算法求解集群下的卡车与无人机联合配送问题。熊兴隆等[13]以配送时间最短为目标，分为两步，提出新型优化迭代算法进行路线的规划。Han等[14]采用一种改进的人工蜂群算法来最小化系统的整体运行成本。Phan 等[15]将问题扩展到一辆卡车与多架无人机结合的情形，采用贪婪随机自适应搜索程序(GRASP)和自适应大邻域搜索(ALNS)启发式算法来解决这一问题。以上研究从成本最低和距离最短目标出发，但均未考虑客户价值因素，同时，上述研究都是在静态路网环境下对路径优化的探索，一定程度上忽略了时变路网对物流配送优化的影响，建立的模型鲁棒性较差，会增加物流运输企业的配送成本。

基于此，本文在满足车辆载重、客户时间窗、无人机飞行距离和无人机载重的约束条件下，将客户价值作和时变路网作为为衡量因素建立了卡车与无人机联合配送的路径优化模型，引入k-means聚类，设计混合粒子群算法对算例进行仿真分析。

# 1 问题描述与模型建立

# 1.1问题描述

本文研究的问题具体可描述为某物流企业有一个配送中心，为节约配送成本和提高配送效率，采用卡车与无人机作为配送工具，为所属企业的客户进行配送。卡车从配送中心搭载足够数量的无人机出发，完成所属卡车和无人机客户的配送任务后返回配送中心。无人机必须从客户点或者配送中心完成起飞和降落。根据客户的位置信息，采用k-means 聚类形成卡车的初始配送路径，最后根据无人机的载重和飞行距离的限制，进行无人机客户的安排。无人机在单次飞行中可以完成多个客户的配送，超出无人机载重距离限制的客户由卡车完成，同一路径的客户由卡车和无人机协同完成，示意图如图1所示。

![](images/96d292bdf7acf8db00734dcda2dc41a47ad266af7735467c5aad62c84578202f.jpg)  
图1卡车与无人机联合配送路径示意图

# 1.2模型假设及符号说明

基本假设：

a)配送中心和客户点的位置和需求量已知，配送中心的需求量为0;

b)卡车每次只携带一架无人机，以及所属卡车和无人机客户的包裹;

c)无人机的最大续航里程和最大载重已知；

d)无人机每次携带多个包裹，可以服务多个客户，每架无人机可以进行多次交付；

e)无人机和卡车保持匀速行驶，无人机的速度快于卡车；

f)无人机的续航时间不变，不考虑无人机飞行速度和载重对无人机续航时间的影响;

g)不考虑客户点服务时间和无人机取货、电池更换时间；

h)卡车上有足够的无人机电池；

i)卡车和无人机不能重新访问任何客户，每个客户只能被服务一次;

j)卡车和无人机均为同一种型号。

模型参数及相关变量如下：

1)集合

![](images/47f085949a3114d525bd291def1e4bf8eaced8dcf95772280e8b7a4d04e08af1.jpg)  
Fig.1Schematic diagram of truck and UAV joint distribution route

$N _ { m } = \{ 1 , 2 , . . . , m \}$ 表示所有客户点的集合； $N = N _ { m } \cup \{ 0 \}$ 表示所有路网节点的集合，0表示配送中心；N表示所有卡车集合； $\mathbf { \xi } _ { N _ { R } }$ 表示所有无人机集合。

# 2)模型参数

$Q { \boldsymbol { r } } $ ：卡车的最大载重； $Q _ { D }$ ：无人机的最大载重； $L _ { D }$ ：无人机的最远飞行距离； $f _ { 1 }$ ：卡车单位固定成本； $f _ { 2 }$ ：无人机单位机身使用成本； $b _ { 1 }$ ：卡车单位运输成本； $b _ { 2 }$ ：无人机单位运输成本； $l _ { i j }$ ：卡车从客户 $i$ 到客户 $j$ 的行驶距离； $d _ { i j }$ ：无人机从客户 $i$ 飞行到客户 $j$ 的飞行距离； $t _ { i }$ ：到达客户点 $i$ 的时间； $t i ^ { h }$ ： $h$ 卡车到达客户点 $i$ 的时间； $t i ^ { k }$ ： $k$ 无人机到达客户点 $i$ 的时间； $S _ { T }$ :卡车服务客户点集合； $S _ { D }$ ：无人机服务客户点集合； $S s$ ：无人机站点的集合： $d _ { i }$ ：客户 $i$ 的货物需求； $V _ { T }$ ：卡车的行驶速度； $\lambda _ { 1 }$ ：单位产品的价值； $\lambda _ { 2 }$ ：单位产品的利润； $S _ { i }$ ：客户点 $i$ 的总价值； $V _ { i }$ ：客户点 $i$ 带来的潜在价值； $g _ { i }$ ：客户点 $i$ 带来的当前价值； $\eta _ { i }$ ：潜在客户数量； $\varsigma _ { ^ { 0 } }$ ：信息扩散强度； $\varsigma { _ { 1 } }$ ：信息扩散深度； $\iota$ ：影响规模； $\left[ a i , b _ { i } \right]$ ：客户的时间窗范围； $\mathbf { \alpha } _ { \alpha , \beta }$ ：配送时间窗的提前惩罚成本系数及延迟惩罚成本系数； $_ { \varepsilon , \theta }$ ：分别为卡车和无人机的等待成本系数。

3)决策变量

# 1.3客户价值及时变路网因素分析

1.3.1客户价值分析

客户价值包括当前价值和潜在价值，当前价值与客户的需求量相关，计算方法为

$$
g _ { j } = \frac { q _ { j } } { \displaystyle \sum _ { j \in N _ { m } } q _ { j } } q _ { j } \lambda _ { 2 }
$$

其中， $q _ { j }$ 为客户 $j$ 的需求量； $\lambda _ { 2 }$ 为单位产品的利润； $\sqrt [ q ] { \sum _ { r = s } q }$ 为客户需求量的比例系数。

客户的潜在价值主要与经营能力、企业声誉和科技创新能力等因素相关。配送的效率及配送方案的优劣对企业的声誉产生影响，此外当客户的满意度高时，潜在客户的概率增大，潜在客户数量增多，客户的潜在价值也随之增大，客户的潜在价值计算公式为

$$
\nu _ { j } = p _ { j } \eta _ { j } q _ { j } \lambda _ { 2 }
$$

其中， $p _ { j }$ 为客户 $j$ 的满意度， $\eta _ { j }$ 为客户 $j$ 激发的潜在客户数量， $\eta _ { j } = \varsigma _ { } { } _ { 0 } \varpi _ { j } \psi$ ，其中 $\varpi _ { j } = p r _ { j \varsigma 1 }$ ， ${ p r } _ { j }$ 是客户的重要程度，所以式(2)可以改写为式(3)。

$$
\nu _ { j } = p _ { j \zeta ^ { 0 } } p r _ { j } \varpi _ { 1 } \psi q _ { j } \lambda _ { 2 }
$$

客户价值为当前的价值与客户的潜在价值之和，计算公式为

$$
S _ { j } = \sum _ { j \in \mathbb { N } _ { \mathrm { } } } W _ { j } ( g _ { j } + \nu _ { j } )
$$

其中， $W _ { j }$ 为客户的权重，客户的重要度越高，权重越高，这样可以提高客户的价值，推动企业的可持续发展。

# 1.3.2时变路网分析

时变路网下，卡车的行驶速度随交通流变化，卡车运输成本会随着拥堵状况的增加而大幅度提高，卡车在拥堵状况下运输时间增加导致无法满足配送客户时间窗的需要。交通拥堵主要包含常发性拥堵和偶发性拥堵，常发性拥堵具有规律性，可预测，在路径配送中可优化配送时间段和配送路径。

交通流的变化一般用明确的速度分布函数表示，本文在前人研究的基础之上，假设在松散时间段时，速度分布符合对数正态分布 $\ln \nu ( t ) - N ( \mu , \sigma ^ { 2 } )$ ，在交通流较大时即一般时间段和高峰时间段，速度分布符合正态分布 $\nu ( t ) - N ( \mu , \sigma ^ { 2 } )$ 。函数表达式为

$$
f ( \nu ( t ) ) = \left\{ \begin{array} { l l } { \displaystyle { \frac { 1 } { \sqrt { 2 \pi } \nu ( t ) \sigma } } e ^ { \frac { - ( \ln \nu ( t ) - \mu ) ^ { 2 } } { 2 \sigma ^ { 2 } } } , \nu \in \big [ \nu _ { \mathrm { m i n } , } \nu _ { \mathrm { m a x } } \big ] , t \in t w _ { 1 } } \\ { \displaystyle { \frac { 1 } { \sqrt { 2 \pi } } } e ^ { \frac { - ( \nu ( t ) - \mu ) ^ { 2 } } { 2 \sigma ^ { 2 } } } , \nu \in \big [ \nu \mathrm { m i n } , \nu \mathrm { m a x } \big ] , t \in t w _ { 2 } , t w _ { 3 } } \end{array} \right.
$$

$$
\begin{array} { r } { \mu = \left\{ \begin{array} { l l } { \varphi _ { 1 } , t \in t w _ { 1 } } \\ { \varphi _ { 2 } , t \in t w _ { 2 } } \\ { \varphi _ { 3 , t } \in t w _ { 3 } } \end{array} \right. , \quad \sigma _ { \nu } = \left\{ \begin{array} { l l } { \sigma _ { \nu 1 , t } \in t w _ { 1 } } \\ { \sigma _ { \nu 2 , t } \in t w _ { 2 } } \\ { \sigma _ { \nu 3 , t } \in t w _ { 3 } } \end{array} \right. } \end{array}
$$

其中， $t w _ { 1 } , t w _ { 2 } , t w _ { 3 }$ 分别表示三个交通流时间段， $\varphi _ { 1 } , \varphi _ { 2 , } \varphi _ { 3 }$ 表示三个时间段的速度期望值， $\sigma _ { \nu 1 , } \sigma _ { \nu 2 , } \sigma _ { \nu 3 }$ 表示速度标准差。

# 1.4目标函数

本文考虑客户价值的卡车与无人机联合配送时变路径目标函数为：总成本最小。

# 1.4.1成本函数的构成

本文目标函数中的总成本的构成如下：

1)运输成本

车辆在行驶的过程中会产生运输成本，无人机在飞行的过程中会产生飞行成本，此部分成本的计算公式为

$$
Z 1 = b \vert \sum _ { i = 0 } ^ { n } \sum _ { j = 0 } ^ { n } \sum _ { h = 1 } ^ { H } x _ { i j h } \times l _ { i j } + b \vert \sum _ { i = 0 } ^ { n } \sum _ { j = 0 } ^ { n } \sum _ { r = 1 } ^ { R } y _ { i j r } \times d _ { i j }
$$

2)固定成本

企业在物流配送中，会产生车辆的发车成本和无人机的机身使用成本。计算公式为

$$
Z 2 = f _ { 1 } \underset { j = 0 } { \overset { n } { \sum } } \underset { h = 1 } { \overset { H } { \sum } } x _ { 0 j h } + f _ { 2 } \underset { j = 0 } { \overset { n } { \sum } } \underset { h = 1 } { \overset { H } { \sum } } y _ { i j r }
$$

3)配送时间窗的提前惩罚成本和延迟惩罚成本

在时变路网的约束条件下，为提高客户的满意度和客户价值，会出现因提前配送而出现的提前惩罚成本，因交通影响而延迟配送的惩罚成本。计算公式为

$$
Z 3 = \sum _ { i = 0 } ^ { m } \sum _ { h = 1 } ^ { H } \left[ \alpha \times \operatorname* { m a x } \left( a _ { i } - \operatorname* { m a x } \left( t _ { i } ^ { h } , t _ { i } ^ { r } \right) , 0 \right) + \beta \times \operatorname* { m a x } \left( \operatorname* { m a x } \left( t _ { i } ^ { h } , t _ { i } ^ { r } \right) - b _ { i } , 0 \right) \right]
$$

4)等待成本

由于配送速度及路况因素的不同，在配送的过程中会发生卡车的等待成本和无人机的等待成本。计算公式为

$$
Z 4 = \varepsilon \sum _ { i = 0 } ^ { m } \sum _ { h = 1 } ^ { H } \operatorname* { m a x } \left( 0 , w i ^ { h } \right) + \theta \sum _ { i = 0 } ^ { m } \sum _ { r = 1 } ^ { R } \operatorname* { m a x } \left( 0 , w i ^ { r } \right)
$$

其中， $w i ^ { h } = t i ^ { h } - t i ^ { r }$ 表示卡车 $h$ 在 $i$ 点等待无人机的时间，$w i ^ { r } = t i ^ { { h } } - t i ^ { { r } }$ 表示 $r$ 无人机在 $i$ 等待卡车的时间。

1.4.2数学模型

$$
\scriptstyle \operatorname* { m i n } Z = Z 1 + Z 2 + Z 3 + Z 4
$$

$$
s . t . \sum _ { i \in m } d i \times S \tau + \sum _ { i \in } d i \times S _ { D } \leq Q \tau
$$

$$
\sum _ { i \in m } \sum _ { h \in H } x _ { i j h } \le \sum _ { i \in m } \sum _ { r \in R } y i j r , \forall j { \in } S s
$$

$$
\sum _ { i \in m } \sum _ { h \in H } x _ { i j h } + \sum _ { i \in m } \sum _ { r \in R } y _ { i j r } = 1 , \forall j \in S _ { D }
$$

$$
d i \times S _ { D } \leq Q _ { D } , \forall i \in N _ { m }
$$

$$
\sum _ { i \in m } \sum _ { h \in H } x _ { i j h } = 1 , \forall j \in S _ { T }
$$

$$
{ \sum _ { i \in m } { y i j r } } = { \sum _ { i \in m } { y j i r } } = 0 , \forall j \in S r , \forall r \in R
$$

$$
a i \leq t i \leq b i
$$

$$
x _ { i j h } { \in } \{ 0 , 1 \} , { \forall } i , j { \in } N _ { m , h \in \mathrm { H } }
$$

$$
y _ { i j r } \in \{ 0 , 1 \} , \forall i , j \in N _ { m , } r \in R
$$

其中，式(9)为目标函数，表示成本最小化，第一部分为运输成本，第二部分为固定成本，第三部分为配送时间窗的提前惩罚成本和延迟惩罚成本，第四部分为等待成本；约束式(10)表示卡车和无人机服务的所有客户的需求量不超过卡车的最大载重；约束式(11)表示卡车完成无人机起飞的客户点后，无人机才可以进行配送；约束式(12)表示每个客户只能被无人机或卡车服务一次；约束式(13)表示无人机配送客户需求量在无人机载重约束范围内；约束式(14)表示无人机无法访问的客户由卡车进行访问；约束式(15)表示超出无人机距离约束的无人机无法访问；约束式(16)表示客户的时间窗约束；约束式(17)(18)为决策变量。

# 2 基于改进k-means聚类的混合粒子群算法

# 2.1改进 $\boldsymbol { \mathsf { k } }$ -means聚类算法

传统的 $\mathbf { k }$ -means聚类算法，在进行聚类之前须事先指定类别数目k，在配送车辆未知的情况下，无法事先确定具体的用车数量。本文采用改进的 $\mathbf { k }$ -means聚类算法，对客户点进行聚类，采用距离作为相似性评估，用 $d i s t ( \delta i , \delta _ { j } )$ 表示两个数据对象 $\delta _ { i }$ 与 $\delta _ { j }$ 之间的欧氏距离，计算公式为

$$
d i s t ( \delta _ { i } , \delta _ { j } ) = \sqrt { \left( \delta _ { i 1 } - \delta _ { j 1 } \right) ^ { 2 } + \cdots + ( \delta _ { i p } - \delta _ { j p } ) ^ { 2 } }
$$

其中， $p$ 为数据对象总个数。

# 2.2k-means 聚类中心的确定

传统的聚类中心是随机生成的，本文采用位置编码的方式对聚类中心进行选取[16]。假设样本的数据规模为 $m$ ，每个数据对象有 $p$ 个特征属性，聚类个数为 $k$ ，聚类中心为$e j ( j = 1 , 2 , \cdots , k )$ ，共生成 $M$ 个粒子，每一个粒子的位置是由 $k$ 个聚类中心组成，其位置编码结构为

$$
p a r t i c l e ( i ) \cdot l o c a t i o n [ ] = [ \overline { { x } } _ { e 1 } , \overline { { x } } _ { e 2 } , \cdot \cdot \cdot , \overline { { x } } _ { e k } ]
$$

其中， $\overline { { \lambda } } \overline { { e } } j$ 为第 $j$ 类数据的聚类中心，是一个 $p$ 维向量。

# 2.3算法设计

根据以上的聚类算法，可以初步得出车辆的使用数量和车辆所服务的客户，为进一步优化车辆的配送路线，引进遗传算法中的交叉和变异概念，设计混合粒子群优化算法对模型进行求解。

# 2.3.1混合粒子群优化算法

粒子群算法是一种启发式优化算法，模拟鸟群随机寻找食物，通过经验和交流，调整自己搜寻的方向和速度，从而找到最优解[17]。

假设在一个D维的目标搜索空间中，有 $\boldsymbol { \tau }$ 个粒子组成一个群落，其中第i个粒子的位置表示为一个D维的向量$X _ { i } = \left( X _ { i 1 } , X _ { i 2 } , \cdots , X _ { i D } \right)$ ；第i个粒子的历史最优位置为$P _ { i } = \left( p { \ o _ { i 1 } } , p { i 2 } , \cdots , p { i D } \right)$ ;整个粒子群迄今为止搜索到的最好位置记为 $P _ { g } = ( p _ { g 1 } , p _ { g 2 } , \cdots , p _ { g D } )$ ；第 $\mathrm { ~ i ~ }$ 个粒子的运动速度也是一个D维的向量 $V i = \left( V _ { i 1 , } V _ { i 2 , } . . . , V _ { i D } \right)$ 。对于粒子i，第 $\mathbf { k } { + } \mathbf { l }$ 次迭代时的粒子速度和位置表示为

$$
w = w \mathrm { 0 } - ( w \mathrm { 0 } - w \mathrm { 1 } ) \frac { i } { k }
$$

$$
c _ { 1 } = c _ { 2 } = c _ { \mathrm { { m a x } } } - \frac { i } { k } \left( c _ { \mathrm { { m a x } } } - c _ { \mathrm { { m i n } } } \right)
$$

$$
\boldsymbol { V } _ { i d } ^ { k + 1 } = \boldsymbol { w } \times \boldsymbol { v } _ { i d } ^ { k } + \boldsymbol { c } _ { 1 } \times \boldsymbol { r a n d } ( ) \times ( p _ { i d } ^ { k } - x _ { i d } ^ { k } ) + \boldsymbol { c } _ { 2 } \times \boldsymbol { r a n d } ( ) \times \left( p _ { g d } ^ { k } - x _ { i d } ^ { k } \right)
$$

$$
x _ { i d } ^ { k + 1 } = x _ { i d } ^ { k } + \nu _ { i d } ^ { k + 1 }
$$

其中， $w$ 是惯性权重， $c _ { 1 }$ 和 $c _ { 2 }$ 是两个随机数，分别是个体学习因子和全局学习因子，randO产生一个(0.1)之间的随机数，i表示第 $i$ 个粒子， $k$ 代表迭代的次数， $\textit { d }$ 代表维度。

# 2.3.2算法流程

粒子群优化算法由于本身粒子更新速度的快慢，会影响全局最优解的产生，为使算法尽快跳出局部最优，将引入遗传算法中的交叉和变异概念，防止算法过早的收敛,设计一种混合粒子群算法(hybrid particle swarmalgorithm,HPSA)。本文设计的混合粒子群算法实现的步骤具体如下：

Step1:初始化粒子群(粒子群共有 $m$ 个粒子)。给每个粒子赋予随机的初始位置和速度。

Step2:计算适应度值。根据适应度函数，计算每个粒子的适应值。

Step3:求个体最佳适应值。对每一个粒子，将其当前位置的适应值与其历史最佳位置 $( p _ { b e s t } )$ 对应的适应值比较，更新个体最优粒子。

Step4:求群体最佳适应值。对每一个粒子，将当前位置适应值与其全局最佳位置 $\left( g _ { b e s t } \right)$ 适应值比较，更新全局最优粒子。

Step5:采用OX，对个体粒子和群体粒子进行最优交叉。

Step6:利用一定概率，进行粒子的变异操作。

Step7:更新粒子的位置和速度。

Step8:判断算法是否结束。如果未满足结束条件，返回 step2，若满足结束条件，输出全局最优粒子。

# 2.3.3算法流程图

混合粒子群算法流程如图2所示。

![](images/1034904b86d7c5d578700ef7f546a34a4a7e42335ae26d3cbcb01912dea6e2dc.jpg)  
图2混合粒子群算法流程图  
Fig.2 Flow chart of hybrid particle swarm optimization

# 2.3.4无人机路径的局部搜索

通过改 $\mathbf { k }$ -means聚类混合粒子群算法，将所有的客户分配给卡车，得到了最优的配送方案。完成所有客户的分配任务后，对该客户再进行局部的搜索形成无人机的配送路径。

无人机路径局部搜索步骤如下：首先，从所有卡车的配送路径中，从左至右选择符合无人机配送条件(最大载重和最大续航里程)的客户点，然后在剩余的卡车路径中选择两个离客户最近的两个点，分别为无人机的发射和降落点，如果这个点被其他无人机作为发射点，则从其他客户中选择。在路径中没有被无人机选中的客户点为卡车的服务对象，卡车从左到右为客户进行服务，最后分别形成了卡车和无人机的最优配送路线。

# 3 算例实验及结果分析

# 3.1实验环境及参数

本文的算例测试，在一台Intel(R)Core(TM)i7-1065G7CPU, $1 . 5 0 \ : \mathrm { G H z }$ ，Windows10(64)位的电脑上进行，在MATLABR2018b上实现对混合粒子群算法的编程。卡车的实时速度通过速度分布函数来确定，在求解参数中， $g _ { \ L ^ { 0 } }$ 客户当前价值阈值为120， $\boldsymbol { V } _ { 0 }$ 客户潜在价值阈值为20， $\varsigma _ { ^ { 0 } }$ 信息传播强度为0.1， $\varsigma _ { ^ { 1 } }$ 信息扩散深度为0.125， $\ell$ 影响规模为20，λ单位产品的价值为6元， $\lambda _ { 2 }$ 单位产品的利润为3元，车辆的最大载重为 $1 0 0 k g$ ,无人机的最大载重为 $1 0 k g$ ，本文设定种群 $N = 1 0 0$ ，最大迭代次数为200， $w$ 惯性权重为1， $c _ { 1 }$ 个体学因子为1.5， $c _ { 2 }$ 全局学因子为2。

# 3.2算例验证

以某物流运输企业为例（数据从网站Indexof/chairedistributique/data/获取)，要为20个客户配送货物，配送中心和客户的相关信息见表1，编号0为物流配送中心，编号1\~20为客户点，文中假设车辆的平均行驶速度50km/h，车辆的总数为4辆，根据车辆的路线安排，在满足无人机的载重约束条件下，合理安排卡车与无人机的路线安排。

表1客户点相关信息  
Tab.1Related information of customer points   

<html><body><table><tr><td>编号</td><td>位置</td><td>需求量</td><td>时间窗</td><td>重要度</td><td>权重</td><td>影响范围</td></tr><tr><td>0</td><td>[40,50]</td><td>0</td><td>[7,18]</td><td>1.0</td><td>1.0</td><td>0</td></tr><tr><td>1</td><td>[45,68]</td><td>11</td><td>[18,20]</td><td>1.0</td><td>1.0</td><td>7</td></tr><tr><td>2</td><td>[45,70]</td><td>13</td><td>[17,19]</td><td>0.5</td><td>1.0</td><td>2</td></tr><tr><td>3</td><td>[42,66]</td><td>8</td><td>[8,9]</td><td>0.5</td><td>1.0</td><td>5</td></tr><tr><td>4</td><td>[42,68]</td><td>5</td><td>[17,18]</td><td>0.5</td><td>1.0</td><td>11</td></tr><tr><td>5</td><td>[42,65]</td><td>10</td><td>[7,8]</td><td>1.0</td><td>1.0</td><td>3</td></tr><tr><td>6</td><td>[40,69]</td><td>2</td><td>[16,17]</td><td>0.3</td><td>1.0</td><td>15</td></tr><tr><td>7</td><td>[40,66]</td><td>23</td><td>[10,12]</td><td>1.5</td><td>2.0</td><td>5</td></tr><tr><td>8</td><td>[38,68]</td><td>25</td><td>[13,15]</td><td>1.5</td><td>2.0</td><td>9</td></tr><tr><td>9</td><td>[38,70]</td><td>17</td><td>[13,15]</td><td>1.3</td><td>1.5</td><td>14</td></tr><tr><td>10</td><td>[35,66]</td><td>9</td><td>[8,9]</td><td>0.7</td><td>1.0</td><td>11</td></tr><tr><td>11</td><td>[35,69]</td><td>15</td><td>[9,11]</td><td>1.0</td><td>1.0</td><td>3</td></tr><tr><td>12</td><td>[25,85]</td><td>27</td><td>[15,17]</td><td>1.6</td><td>2.5</td><td>13</td></tr><tr><td>13</td><td>[22,75]</td><td>37</td><td>[7,8]</td><td>2.0</td><td>3.2</td><td>7</td></tr><tr><td>14</td><td>[20,85]</td><td>16</td><td>[10,12]</td><td>1.3</td><td>1.2</td><td>11</td></tr><tr><td>15</td><td>[20,80]</td><td>48</td><td>[19,20]</td><td>3.0</td><td>4.0</td><td>2</td></tr><tr><td>16</td><td>[20,85]</td><td>7</td><td>[7,9]</td><td>0.5</td><td>0.5</td><td>4</td></tr><tr><td>17</td><td>[18.75]</td><td>29</td><td>[9,13]</td><td>1.5</td><td>2.8</td><td>5</td></tr><tr><td>18</td><td>[15.75]</td><td>9</td><td>[15,18]</td><td>1.3</td><td>1.5</td><td>13</td></tr><tr><td>19</td><td>[15,80]</td><td>12</td><td>[17,19]</td><td>1.0</td><td>1.0</td><td>7</td></tr><tr><td>20</td><td>[30,50]</td><td>17</td><td>[7,8]</td><td>1.3</td><td>1.5</td><td>4</td></tr></table></body></html>

对该企业配送过程中的交通状况进行调查，一天中具体的交通状况见表2。本文假设卡车的单位固定成本为100元，卡车的单位运输成本为3/元/km，无人机的固定成本为15元，无人机的单位运输成本1元/km，卡车的等待成本为3元/h，无人机的等待成本为1.5元/h，卡车提前惩罚成本系数为1,延迟惩罚成本系数为2。

Tab.2Velocity distribution function   

<html><body><table><tr><td>拥堵情况</td><td>时间段</td><td>速度分布</td></tr><tr><td>畅通时间段</td><td>12：00-14：00 18：00-20:00</td><td>Inv(t)~ N(3.8,0.12²)</td></tr><tr><td>一般时间段</td><td>9：00-12:00 14:00-17:00</td><td>v(t)~ N(32.0.5²)</td></tr><tr><td>拥堵时间段</td><td>7:00-9:00 17:00-18：00</td><td>v(t)~N(15,0.5²)</td></tr></table></body></html>

根据以上的模型，利用MATLAB进行编程，将不同时间段的速度参数加入到混合粒子群算法中，并根据无人机局部搜索得到卡车和无人机的配送路径，见表3,编程优化后，总成本为1257.53元。

表3路径规划结果  

<html><body><table><tr><td>编号</td><td>卡车-无人机配送路径 成本</td></tr><tr><td>1</td><td>16 0 13 14 12 257.85 0</td></tr><tr><td>18 2 0 20 7 19 15</td><td>0 261.85</td></tr><tr><td>3 0 10 11</td><td>159.90</td></tr><tr><td>3 4 0 5 7 8</td><td>0 0 117.92</td></tr></table></body></html>

注：实线表示卡车运输,虚线表示无人机运输。

# 3.2.1对比实验一

为验证动态路网和客户价值对卡车与无人机的配送路径的合理性，本文将未考虑客户价值的静态模型与本文考虑客户价值的动态模型进行对比实验，将得到的结果进行比较分析，如表4所示。

表4未考虑客户价值静态路网模型与本文模型结果对比

Tab.3Path planning results   
Tab.4Compares the results of static road network model without considering customer value with that of this paper   

<html><body><table><tr><td>参数</td><td>未考虑客户价值静态路网模型</td><td>本文模型</td></tr><tr><td>总成本/元</td><td>1150.27</td><td>1257.53</td></tr><tr><td>总客户价值/元</td><td>2058.473</td><td>2404.989</td></tr><tr><td>客户满意度</td><td>0.7425</td><td>0.9005</td></tr></table></body></html>

根据表4的对比实验实验结果可知，首先，在总成本方面，未考虑客户价值静态网络模型下的卡车与无人机的配送相比于本文的模型降低了 $9 . 3 2 \%$ ，减少了物流公司的支出，提高了经济效益。其次，从总的客户价值和满意度来看，本文模型比考虑客户价值静态网络模型下的卡车与无人机的配送，总客户价值增加了 $1 6 . 8 3 \%$ ，客户的满意度提高了 $2 1 . 2 8 \%$ 。最终，由以上的结果分析可知，考虑客户价值和时变路网因素的模型，可以更符合实际情况，提高公司的竞争力，实现企业的效益最大化，促进企业的可持续发展。

# 3.2.2对比实验二

针对车辆与无人机的联合配送路径问题，不同的学者提出了不同的算法进行求解，如：最短路算法与禁忌搜索算法相结合的混合禁忌搜索算法(hybridtabusearchwithshort-pathalgorithm，SPTS)[3]、自适应大邻域搜索算法(adaptive largeneighborhood search,ALNS)[8]、贪婪随机自适应搜索算法(greedyrandomized adaptive search procedure,GRASP)l15]及混合遗传算法(hybrid genetic algorithm,HGA)[18]等。但以上的算法在不同的方面均存在一定的局限，为验证本文提出算法的有效性和合理性，将以上四种方法对考虑客户价值的卡车与无人机的联合配送时变路径模型进行求解，并将实验的结果进行比较分析，如表5所示。

表5算法性能比较

表2速度分布函数  
Tab.5Performance comparison of algorithms   

<html><body><table><tr><td>算法类别</td><td>平均值</td><td>最优值</td><td>计算时间/s</td><td>收敛迭代次数</td></tr><tr><td>SPTS</td><td>1528.27</td><td>1347.56</td><td>70.891</td><td>160</td></tr><tr><td>ALNS</td><td>1628.53</td><td>1548.39</td><td>57.294</td><td>110</td></tr><tr><td>GRASP</td><td>1490.89</td><td>1298.36</td><td>65.783</td><td>80</td></tr><tr><td>HGA</td><td>1589.73</td><td>1308.61</td><td>80.732</td><td>120</td></tr><tr><td>HPSA</td><td>1473.56</td><td>1257.53</td><td>60.4785</td><td>140</td></tr></table></body></html>

根据表5的实验结果可以直观的看出，a)SPTS在160代完成算法的收敛，ALNS在110代完成算法的收敛，尽管ALNS具有较快的收敛速度，但在配送成本的最优值方面比SPTS 的求解性能差。b)GRASP和HPSA的实验结果相比，GRASP收敛速度较快，但在计算的时间上比HPSA略长，平均值和最优值都高于HPSA的求解结果。c)HPSA和HGA的实验结果相比，在平均值和最优值的结果方面都具有较强的求解精度，求解计算的时间更快，有利于更快的获得最优解。综上，在与其他算法的结果进行比较时，本文的采用混合粒子群算法在求解本文的模型时，具有较高的计算准确度和较快的计算速度，有效的避免了算法在求解问题时出现局部最优的局限性，具有较快的收敛速度和全局搜索最优的性能，节约了物流企业配送的成本，提高了企业的经济效益。

# 4 结束语

本文针对客户价值下的卡车与无人机联合配送的时变路径问题进行了以下的研究。

1)从配送模式方面，本文采取了卡车与无人机联合配送的方式，将客户的价值和路网的时变性作为约束条件，建立了总成本最小的数学模型。将静态未考虑客户价值的模型与动态考虑客户价值的模型进行对比，本文的模型可以更好的增加客户价值和提高客户满意度，从而扩大企业的经济效益。

2)为提高算法的性能，设计了混合粒子群算法对模型进行求解，将不同的算法实验结果与此算法进行对比分析，实验结果可以得出混合粒子群算法在收敛速度、计算时间和最优值的求解方面具有良好的性能，是解决卡车与无人机联合配送运输问题的一种有效的智能优化算法。

3)本文在研究卡车与无人机的路径问题时，只考虑了无人机载重因素的影响，未来的研究可以将配送的时间和能量的消耗进行综合的考虑，同时也可以将天气的不确定性因素进行考虑，结合现实中的具体问题建立更符合的模型。

# 参考文献：

[1]Murray CC,ChuAG.The flying sidekick traveling salesman problem: Optimization of drone-assisted parcel delivery [J].Transportation Research Part C Emerging Technologies,2015,54: 86-109.   
[2]Semiz F,Polat F. Solving the area coverage problem with UAVs:A vehicle routing with time windows variation [J].Roboticsand Autonomous Systems,2020:103435.   
[3]］朱晓宁，陈立双，田昊彤，等．考虑区域限制的卡车搭载无人机车 辆路径问题研究[J/OL].中国管理科：1-12[2022-04-26].(Zhu Xiaoning，Chen Lishuang，Tian Haotong，etal.Research on Route Problem of Truck Carrying UNMANNED aerial vehicle considering Regional Limitation [J/OL].Chinese Journal ofManagement Science:1- 12 [2022-04-26].)   
[4]彭勇，黎元钧．考虑疫情影响的卡车无人机协同配送路径优化[J]. 中国公路 学报，2020,33(11):73-82.(Peng Yong,Li Yuanjun. Collaborative delivery route optimization of truck UAVs considering the impact of the epidemic [J].China Journal of Highway and Transport, 2020,33 (11): 73-82.)   
[5] 张得志，乔馨，肖博文，等．基于低碳与随机需求的多目标车辆路径 优化[J]．铁道科学与工程学报,2021,18(08):2165-2174.(Zhang Dezhi,Qiao Xin,Xiao Bowen,etal. Multi-objective vehicle routing optimization based on low carbon and random demand [J]. Journal of Railway Science and Engineering,2021,18 (08): 2165-2174.)   
[6]杜茂康，罗娟，李博文．基于多车场的车载无人机协同配送路径优 化[J]．系统工程,2021,39 (06):90-98.(Du Maokang,Luo Juan,Li Bowen. Collaborative delivery path optimization of vehicle-mounted UNMANNED aerial vehicles based on multi-depot [J]. System Engineering,2021,39 (06): 90-98.)   
[7]Salama M, Srinivas S.Joint optimization of customer location clustering and drone-based routing for last-mile deliveries [J]. Transportation Research Part C Emerging Technologies,2020,114: 620-642.   
[8]王新，王征，徐伟．面向多个无人机站点的车辆与无人机联合配送 路径问题研究[J].运筹与管理，2021,30(05):31-37.(Wang Xin, Wang Zheng,Xu Wei.Research on Vehicle and UAV Joint Delivery Routing Problem for Multiple UAV Stations [J].Operations Research and Management, 2021,30 (05): 31-37.)   
[9]邓永蕤，徐菱，吴茂婷，等．基于无人机与卡车联合运输下的冷链物 流网络优化[J]．江苏农业科学，2019,47(13):268-272.(Deng Yongrui, Xu Ling,Wu Maoting,etal.Optimization of cold chain logistics network based on uav and truck combined transportation [J].Jiangsu Agricultural sciences,2019,47 (13):268-272.)   
[10]唐立，郝鹏，张学军．基于改进蚁群算法的山区无人机路径规划方 法[J].交通运输系统工程与信息,2019,19 (01):158-164.(Tang Li, Hao Peng,Zhang Xuejun.Unmanned aerial vehicle path planning method in mountainous area based on improved ant colony algorithm [J]. Transportation Systems Engineering and Information Technology,2019, 19 (01): 158-164.)   
[11]李妍峰，李佳，向婷．需求可拆分的无人机与卡车协同路径优化问 题[J].工业工程,2022,25 (01): $5 4 - 6 3 + 1 4 3$ .(LiYanfeng,LiJia,Xiang Ting.A detachable collaborative path optimization problem for uAVs and trucks [J].Industrial Engineering,2022,25(01): $5 4 - 6 3 + 1 4 3 .$ ）   
[12]曹英英，陈淮莉．基于集群的卡车与无人机联合配送调度研究 [J/OL]．计算机工程与应用,2021,1-9（Cao Yingying,Chen Huaili. Research on Truck and UAV Joint Distribution Scheduling Based on Cluster [J/OL].Computer Engineering and Applications,2021,1-9.)   
[13]熊兴隆，刘佳，李猛，等．基于无人机-配送车辆联合配送的优化算 法研究[J].计算机工程与应用，2021,57(19):259-266.(Xiong Xinglong,Liu Jia, Li Meng,etal. Research on optimization algorithm based on uAV-vehicle joint distribution [J]. Computer Engineering and Applications,2021,57 (19): 259-266.)   
[14] Han YQ,Li JQ,Liu Z M,et al. Metaheuristic algorithmfor solving the multi-objective vehicle routing problemwith time window and drones [J]. International Journal ofAdvanced Robotic Systems,2020,17 (2):1-14.   
[15]Lei Deming,Cui Zeng zhi,Li Ming.A dynamical artificial bee colony for vehicle routing problem with drones [J]. Engineering Applications of Artificial Intelligence,2022,107.   
[16] 李玥，穆维松，褚晓泉，等．基于改进量子粒子群的K-means 聚类算 法及其应用[J].控制与决策,2022,37(04):839-850.(Li Yue,Mu Weisong, Chu Xiaoquan,etal.K-means Clustering Algorithm based on Improved Quantum Particle Swarm and its Application [J].Control and Decision,2020,37 (04): 839-850.)   
[17]梁静，葛士磊，瞿博阳，等．求解电力系统经济调度问题的改进粒子 群优化算法[J].控制与决策,2020,35 (08):1813-1822.(Liang Jing, Ge Shilei,QU Boyang,etal.An improved particle swarm optimization algorithm for solving economic scheduling problems in power systems. Control andDecision,2020,35 (08):1813-182.)   
[18] Peng K,Du JLu F,et al.A Hybrid genetic algorithm onrouting and scheduling for vehicle-assisted multi-droneparcel delivery [J].IEEE Access,2019,7:49191-49200.