# 基于改进匈牙利算法的机场航班时刻优化研究

胡明华，裔田园，任禹蒙(南京航空航天大学 民航学院，南京 211100)

摘要：航班时刻是我国治理航班延误、管理空中交通流量最为重要的基础数据之一。针对我国枢纽机场运营高峰时段时刻资源紧张、超负荷运行、放行顺序不合理等情况，分析机场航班运行规律和存在问题，在保证正班航班运输需求的基础上，提出基于历史数据的航班时刻优化模型，并改进匈牙利算法求解，以达到航空公司申请时刻调整量和航班地面等待时间整体最小的目标。结合杭州萧山国际机场历史运行数据,验证了航班时刻优化模型的可行性和适用性，对减少地面延误、提高放行正常率、增加机场容量具有重要作用。

关键词：航班时刻；历史数据；优化模型；匈牙利算法 中图分类号：V355 doi: 10.3969/j.issn.1001-3695.2018.01.0073

# Optimization of airport slot based on improved Hungarian algorithm

Hu Minghua, Yi Tianyuan†, Ren Yumeng (College ofCivil Aviation,Nanjing University ofAeronautics&Astronautics,Nanjing 211oo,China)

Abstract: Airport slotisoneofthemostimportantbasicdatafor managing flightdelayandairtrafficflowinourcountry.With theanalysisofairportflightoperationrulesand existing problems,this paper proposedanairportslotoptimizationmodelbased onhistoricaldataandsuggestsanimproved Hungarianalgorithmtosolveit,inorder tominimizeairlines’slotadjustmentand ground-holding timeof theflightsasa whole.Combining the historical dataof Hangzhou Xiaoshan International Airport,it conformedthe feasibilityandapplicabilityof the model.Italsopointedout theimportant rolethemodelplayed inreducing ground delay, improving the normal rate of release and increasing the capacity of airports.

Key words:flight schedule; historical data; optimization model; Hungarian algorithm

# 0 引言

近年来，中国民航运输业高速发展，随之而来的航班时刻资源短缺、放行正常率得不到保证、机场大面积延误等问题日益凸显。恶劣天气和流量控制等因素是造成航班延误的直接原因，但究其根本是机场高峰运营时段旺盛的时刻需求与有限容量之间的矛盾。我国许多枢纽机场高峰时段已处于容量饱和甚至过饱和状态，无法通过自身调节消化天气和流控带来的影响，进一步加剧了延误波及现象。因此，为从根本上解决航班延误问题，需处理航班时刻资源的供需矛盾，特别是机场容量一定、放行流量受控条件下如何合理编排航班时刻。

全球大多数繁忙机场都存在严重的航班延误问题，航班时刻优化作为需求管理的一种，因其可在现有资源的基础上实现容量利用率的快速持续提升，有望解决机场中短期内出现的拥堵问题[1\~3]。2011年，Bertsimas 等人[4]在公平性原则的基础上，提出了航班时刻优化分配网络模型。同年，Bennell等人[5]归纳总结了战术阶段单机场时刻分配问题的约束和优化技术。2012年，Clarke等人[6给出了枢纽机场进离场协调概念的调研、建模和分析建议，针对终端区内航空器时刻编排和飞行路径的实时性问题。2014年，Sama等人[7]为繁忙终端管制区研制开发了管制监视指挥决策支持工具，执行并比较了集中控制和滚动时域控制两种模式，采用分支界定算法、禁忌搜索算法、混合整数线性规划等方法同步调配航班时刻和飞行路径。2015年，Jacquillat等人[8]研究了缓解繁忙机场拥堵问题的时刻调配手段和运行管理方法；同年，Pyrgiotis等人[9]以纽瓦克国际机场为例研究了时刻受限对机场的影响。2017年，Bolic"等人[10]将峰值负荷价格扩展应用到欧洲ATM系统中；同年，周璐等人[11]根据方向约束提出了一种动态航迹规划方法，可适应动态环境变化。

上述文献一部分以航空公司计划排班为研究对象，考虑因素多为机组管理、航线结构、班期频率、运营成本等；另一部分从空中交通流量管理的角度出发，优化方法大多借鉴战术阶段的地面等待策略和路径规划。航班时刻管理是一个涉及多方利益的复杂过程，优化目标仅仅考虑经济效益或安全效益是不科学也不切实的。从航空公司角度出发，虽然可以增强航空公司的盈利能力，但会导致较大的运行延误；而从空中交通流量管理的角度研究，虽然可以降低机场总体延误水平，但会增大航空公司的运营成本。为了对机场航班时刻进行科学合理地规划，给管理者提供量化辅助决策方案，本文从航空公司和空中交通流量管理部门两者综合考虑，在对空域结构和航班数据分析研判的基础上提出了基于历史数据的机场航班时刻优化模型。针对经典匈牙利算法不能解决具有并联情况的时刻分配问题的不足，通过增加虚拟航班的方式改进算法，将问题转换为标准指派问题，迭代搜索得到最优解。实例验证表明，该方法可实现机场高峰运营时段容量受限下的排班优化，降低管制工作负荷的同时提高机场运行效率。

# 1基于历史数据的机场航班时刻优化模型

# 1.1相关概念

1）航班时刻

从实际应用角度来说，航班时刻并不是一个具体的时刻，而是以 $5 ~ \mathrm { m i n }$ 为最小时间单元在指定日期指定机场为航班预留的一个特定时隙。时隙由起始时间和长度两个特征来表示。比如，某个机场的时隙长度为 $5 \mathrm { \ m i n }$ ，则可用时隙序列为00:00.00:05，...，23:55，如果将开始时间为9:00的时隙分配给某架航班，则该航班在9:00\~9:05间拥有起飞或着陆的权利。

# 2）机场时刻容量

中国民航局《机场时刻容量评估技术规范》（AP-93-TM-2017-01）将机场时刻容量定义为：根据航空器性能、机场和空管运行规则、限制因素和可接受的延误水平，确定的机场单位时间计划起降架次。单位时间通常为 $5 ~ \mathrm { m i n }$ 、 $1 5 ~ \mathrm { m i n }$ 、 $6 0 ~ \mathrm { { m i n } }$ 。

# 3）机场走廊□

机场走廊口是航空器进出该机场终端区的一个重要航路点。如图1所示，杭州萧山机场的航班流经由GS、TOL、AND三个方向走廊口进出机场。

![](images/9b85a7ead6336af75ebcb2c6a9b0674b1758ff744e48edd5c9579435908845de.jpg)  
图1杭州萧山机场进离场走廊口示意图

4）航班过站时间

航班过站时间指从航空器滑行至停机位开启机门至航空器准备工作就绪关机门之间的时间，也称为中转航班衔接时间。

根据2015年民航局修订的《民航航班正常统计办法》，对我国繁忙机场机型最少过站时间的要求如表1所示。

表1各型航空器最少过站时间规定  

<html><body><table><tr><td>过站时间/min</td><td>代表机型 座位数/座</td></tr><tr><td>40</td><td>CRJ200、EMB145、ATR72 60以下</td></tr><tr><td>55</td><td>CRJ700、E190、A319、B737（700以下） 61~150</td></tr><tr><td>65</td><td>B737（700型及以上）、B757-200、 151~250</td></tr><tr><td>75</td><td>A310、A320、A321 B747、B777、A300、A330、A340、 251~500</td></tr><tr><td></td><td>MD11</td></tr><tr><td>120</td><td>A380 500以上</td></tr></table></body></html>

# 1.2模型的假设

假设1：我国大型枢纽机场终端区基本完成进离场航线分离，假定同一走廊口进离场航班之间不受影响，分别设立走廊□流量限制；

假设2：在实际中同方向航班连续排班易出现放行困难，将机场放行间隔转换为离场航班走廊口时刻流量限制;

假设3：根据航空器飞行速度，将机场终端区移交点进场移交间隔转换为进场航班走廊口时刻容量限制；

假设4：将航季时刻表中公布的航班时刻作为航空公司的期望时刻，仅对正班航班时刻进行优化调整；

假设5：假定所有航空公司可接受的航班时刻最大调整量（即期望时刻与优化后时刻之差）相同；

假设6：出于安全考虑，通常情况下机场都会优先保障进场航班，以航空器地面延误取代空中等待，因此本文仅对机场离场航班进行时刻优化。

# 1.3模型的构建

模型所用参数定义如表2所示。

表2模型所用参数定义  

<html><body><table><tr><td>参数</td><td>含义</td></tr><tr><td>T</td><td>时刻集合，∀t∈T</td></tr><tr><td>F</td><td>航班集合，∀f∈F</td></tr><tr><td>t</td><td>换季航班时刻表中公布的航班f的起降时刻</td></tr><tr><td>N,</td><td>历史运行中航班f实际执行的次数</td></tr><tr><td>t(n)</td><td>航班f第n次执行过程中的实际起降时间</td></tr><tr><td>tf max</td><td>航班f可接受的最大时刻调整量</td></tr><tr><td>F</td><td>过站航班对集合，过站航班对(𝑓a,fd)∈FP</td></tr><tr><td>Tda</td><td>航空器最小过站时间集合</td></tr><tr><td>M</td><td>航空器类型集合</td></tr><tr><td></td><td>第m类航空器的航班集合</td></tr><tr><td>tm</td><td>第m类航空器的最小过站时间，m∈M</td></tr></table></body></html>

<html><body><table><tr><td>R</td><td>机场走廊口集合</td></tr><tr><td>Fd</td><td>走廊口r的离场航班集合</td></tr><tr><td>Fa</td><td>走廊口r的进场航班集合</td></tr><tr><td>q</td><td>走廊口r的离场流量限制，时间为5分钟</td></tr><tr><td></td><td>走廊口r的进场流量限制，时间为5分钟</td></tr><tr><td>tc</td><td>机场i在时间t内的时刻容量</td></tr><tr><td>T</td><td>容量限制时段，T={t∈T|s≤t<s+tc}</td></tr></table></body></html>

$X _ { t } ^ { f } = \left\{ \begin{array} { l l } { { 1 , } } \\ { { 0 , } } \end{array} \right.$ 如果航班f在时隙t执行决策变量：其他

目标函数：

$$
\mathrm { M i n ~ } \sum _ { \forall f \in \boldsymbol { F } } \sum _ { \forall t \in \boldsymbol { T } } \left\{ \sum _ { n = 1 } ^ { N _ { f } } \Bigl | t - t _ { e } ^ { f } \Bigr | \right\} X _ { t } ^ { f } + \sum _ { \forall f \in \boldsymbol { F } } \sum _ { \forall t \in \boldsymbol { T } } \left\{ \sum _ { n = 1 } ^ { N _ { f } } \Bigl | t - t _ { a } ^ { f } \left( n \right) \Bigr | \right\} X _ { t } ^ { f }
$$

其中：第一部分 $\sum _ { \forall f \in F } \sum _ { \forall t \in T } \left\{ \sum _ { n = 1 } ^ { N _ { f } } \Bigl | t - t _ { e } ^ { f } \Bigr | \right\} X _ { t } ^ { f }$ 表示历史运行中总的计划偏移成本，即计划起降时间与换季航班时刻表中公布的起降时刻之差；第二部分 $\sum _ { \forall f \in F } \sum _ { \forall t \in T } \left\{ \sum _ { n = 1 } ^ { N _ { f } } \Bigl | t - t _ { a } ^ { f } \left( n \right) \Bigr | \right\} X _ { t } ^ { f }$ 表示历史运行中总的实际延误成本，即计划起降时间与历史运行统计表中实际起降时间之差。

约束条件：

a)时刻分配唯一性约束。  
每个航班在同一天同一机场只能分配一个时刻。

$$
\sum _ { t \in T } X _ { t } ^ { f } = 1 , \ f \in F
$$

b)时刻搜索范围约束。

航空公司的期望时刻存在最大可接受的调整幅度，将时刻调整范围限定在某一范围之内，不但符合实际情况，且可提高模型的求解效率。

d)走廊口进离场流量限制约束。

e)航班最少过站时间约束。

$$
\sum _ { t \in \left[ 0 , k \right) } X _ { f _ { d } } ^ { t } + \sum _ { t \in \left[ k - t _ { m } , h \right) } X _ { f _ { a } } ^ { t } \leq 1 , \ : \ : \ : \left( f _ { a } , f _ { d } \right) \in F _ { m } ^ { p } , k \in \left[ t _ { f } , h \right)
$$

c)机场时刻容量约束。

$$
\begin{array} { r l } & { \displaystyle \sum _ { f \in { \cal F } _ { r } ^ { d } } X _ { t } ^ { f } \leq c _ { r } ^ { d } , t \in T , r \in R } \\ & { } \\ & { \displaystyle \sum _ { f \in { \cal F } _ { r } ^ { d } } X _ { t } ^ { f } \leq c _ { r } ^ { a } , t \in T , r \in R } \end{array}
$$

$$
\left| t - t _ { e } ^ { f } \right| \leq t _ { \operatorname* { m a x } } ^ { f } , \ f \in F
$$

如图2所示，机场航班时刻编排时若仅考虑整点时段航班量（如 $0 7 { : } 0 0 { \sim } 0 8 { : } 0 0 \ \cdot$ )，会导致航班密集的时刻连续出现，易造成非整点时段（如07:30\~08:30）实际排班量超出高峰小时航班时刻容量标准。因此，本文同时对 $5 ~ \mathrm { m i n }$ 、 $1 5 ~ \mathrm { m i n }$ 以及 $6 0 ~ \mathrm { { m i n } }$ 容量进行限制。

$$
\sum _ { f \in F } \sum _ { t \in T _ { c } ^ { s } } X _ { t } ^ { f } \leq c _ { _ { t _ { c } } } ^ { i }
$$

![](images/425d585832b47d23108df8b2a19f267db6d5b502729391993759edda69daff04.jpg)  
图2国内某机场高峰时段时刻容量与累积排班量对比

# 2 改进匈牙利算法

模型的目标是在尽可能满足航空公司期望时刻的前提下，给每个航班分配一个可用时刻，降低总成本。分配不同时刻给同一航班产生的计划偏移成本和运行延误成本不同，所以可将该问题理解为最优指派问题。

解决指派问题的方法主要有两类：一类是确定性解析算法，如匈牙利算法；另一类是启发式智能算法，如遗传算法、禁忌搜索算法、模拟退火算法等。虽然启发式算法对于大规模的指派问题具有速度较快的优势，但不能保证得到最优解，而且算法相对复杂，在工程实际中应用并不多。匈牙利算法具有步骤简单、能得到最优解且无须验证的特点，被广泛用于解决中小规模的指派问题[12\~14]。

# 2.1 经典匈牙利算法

匈牙利算法是美国数学家库恩提出的用来解决极小型指派问题的经典算法。康尼格定理是匈牙利算法主要的理论基础，其具体内容是：系数矩阵中能覆盖所有0元素的最小直线数与独立0元素的最多个数相等[15]。利用匈牙利算法求解需要满足以下三个条件：a)目标函数为极小型；b)系数矩阵为方阵；c)系数矩阵元素值非负。指派问题的最优解具有如下特征：用系数矩阵中行（列）的元素中减去行（列）的最小元素获得一个新的矩阵，通过新矩阵作为系数求得的最优解与原矩阵求得的相同。使用该属性，可以将原始系数矩阵转换为包含许多0元素的新矩阵，并且最优解保持不变[16]。

# 2.2算法改进的基本思路

在航班时刻分配问题中，时刻可容纳航班总量大于需分配航班量，且多个航班可分配同一时刻，是一个非标准的指派问题，通过添加虚拟航班的方式，使两者一一对应，变成纯串联系统。为消除虚拟航班对分配结果的影响，将虚拟航班成本系数设置为0；同时，若某航班分配的时刻不符合约束，则将其成本系数设为一个很大的值。针对机场时刻容量约束和走廊口进离场流量约束无法同步实现的问题，采取先优化分配后判断调整的方式分整体优化和局部优化两步进行。在解决实际问题中，需要对系数矩阵加以限制，转换为标准指派问题再利用匈牙利算法进行计算。

# 2.3改进算法的求解步骤

基于以上思路，针对航班时刻分配问题，改进匈牙利算法的求解流程如图3所示。

![](images/b9c23ba63acec83fedb81466e94dda8aa14c26c0ecef41d71f3983d7a47d6ca9.jpg)  
图3匈牙利算法求解流程

具体步骤如下：

a)若需要优化的时刻个数为 $T$ ，每个时刻航班容量为 $n$ ，则可容纳航班总量 $F _ { \circ }$ 若在该时间区间内需要分配的航班数为 $M$ 则需增加 $( n ^ { * } T – M )$ 个虚拟航班。如此将非标准指派问题转换为标准指派问题。

b)计算任一航班分配至每个时刻的计划偏移成本和延误成本，建立系数矩阵。对于中转航班，在给其分配的进场时刻上加最少中转时间得到最早离场时刻，将分配到最早离场时刻前的成本系数设为一个很大的值。同时设定最优航班时刻搜索范围，航班仅可在原航班时刻的前后 $p$ 个时刻内调整，将分配到其他时刻的成本系数设为一个很大的值。

c)匈牙利算法求解。

d)分析优化后航班时刻，判断走廊口流量与约束是否匹配。 若某一时刻容流不匹配，则依次前后寻找空缺时刻。记该时刻 序列为T，范围内航班序列为 $F$ 。

e)以 $T$ 为行、 $F$ 为列建立系数矩阵，再次运用匈牙利算法局部优化。

f)输出最终优化结果。

# 3 实证研究

杭州机场2016年全年旅客吞吐量及起降架次位列全国前十，但航班正常率为 $7 4 . 4 6 \%$ ，航班放行正常率为 $7 3 . 8 5 \%$ ，在全国主要机场中处于较低水平。

本实验数据来源于《2016年夏秋国内公司航班计划》（全国航班计划时刻管理系统）和《2016年杭州萧山国际机场历史运行数据统计》。以MATLAB2014a为程序开发平台，对所提出的时刻优化方法进行分析验证，程序界面如图4、5所示。实证研究内容共分为三个部分：a)实验数据的获取和预处理；b)利用模型算法优化求解，从延误成本角度对比分析优化前后的航班时刻表；c对最大时刻调整量约束和机场容量约束两个关键参数进行灵敏度分析。

班时优化欧件系确V1.0  ×  
文件（F) 统计分析（S） 航班时刻优化处理（P) 工具（T）帮助（H)1 2 3 4 5 6 7 8 9 10 11 131 航建号 机型 起飞机场 起时到 签地时到 落地机场 北房口 A2 3U8386 320 ZPLJ 2250 0155 ZSHC3 3U8406 319 ZuUZ 1835 2105 ZSHC4 3U8536 320 ZUGY 2140 2350 ZSHC 有5 3U8567 319 zuz 2110 2340 2SHC 转声6 3U8582 320 ZYHB 2035 2355 − D X7 3U8586 320 ZYT 2055 23058 3U8876 321 ZBYN 2115 2330 输入时长9 3U8911 320 ZUUU 1435 1720 5]10 3U8919 320 ZUUU 2030 2315 OK Cancel11 3U8936 319 ZUCK 2045 230012 9C85556 320 ZBSJ 0700 0910 ZSHC 水13 9C8712 320 ZSOF 1140 1240 ZSHC 水14 9C8744 320 ZGZJ 1915 2140 ZSHC 有15 9C8520 320 ZYTX 1400 1540 ZSHC 东16 BK2825 737 ZBTJ 0700 855 ZSHC 水17 BK3063 737 ZBTJ 1905 2115 ZSHC 水18 CA1509 321 ZBAA 0745 1000 ZSHC 水19 CA1563 321 ZBAA 1620 1835 ZSHC 水20 CA1565 319 ZBAA 0640 0855 ZSHC21 CA1595 321 ZBAA 0845 1100 ZSHC 水22 CA1673 738 ZBTJ 1610 1805 ZSHC 水23 CA1702 321 ZBAA 1110 1320 ZSHC 水2M 2 球 A

![](images/c29e0036c1f7f2d5009eefc35147ee4f939e99c3058ae2c7f939d0e6694be063.jpg)  
图4航班时刻优化程序界面示意图（一）  
图5航班时刻优化程序界面示意图（二）

# 3.1数据预处理

杭州机场夏秋航季周五离场航班计划共342架次，选取有效运营时段07:00\~21:00内航班进行优化，共计287架次。机场容量及走廊口流量限制如表3、4所示。

表3杭州萧山机场离场时刻容量及运行流量统计  

<html><body><table><tr><td>统计时段/min</td><td>公布容量</td><td>实际最大排班量</td><td>实际平均流量</td></tr><tr><td>5</td><td>3</td><td>5</td><td>1</td></tr><tr><td>15</td><td>8</td><td>10</td><td>4</td></tr><tr><td>60</td><td>30</td><td>28</td><td>14</td></tr></table></body></html>

表4杭州终端区走廊口 $5 \mathrm { m i n }$ 离场流量限制  

<html><body><table><tr><td>走廊□</td><td>流量限制</td></tr><tr><td>AND</td><td>1</td></tr><tr><td>GS</td><td>1</td></tr><tr><td>TOL</td><td>2</td></tr></table></body></html>

# 3.2 优化结果分析

以杭州机场2016年4月至9月历史运行数据为基础，优化原航班时刻。第一轮整体优化共有51架航班的时刻发生变动，经过优化后任一时刻离场流量都控制在3架次以内。检测第一轮优化结果，发现仍有27架航班需再次优化，共涉及26个时刻。对不符合走廊口约束的航班，再进行第二轮局部优化。部分航班优化前后时刻如表5所示。

利用2016年11月数据对优化结果进行验证。表6为优化前后延误情况对比。经验证，采用该方法虽然计划偏移成本略有增加，但可有效降低运行延误成本，总成本呈减小趋势。且原航班时刻表中存在6个超机场容量时刻，优化后所有时刻均满足容量限制。原航班时刻表中29个时刻不符合走廊口流量限制，优化后数量减少至8个。进一步证明，航班计划的容量匹配与降低航班运行延误存在一定的因果关系。

表5优化前后离场航班时刻表(部分)  

<html><body><table><tr><td rowspan="2">航班号</td><td rowspan="2">走廊□</td><td colspan="3">执行 延误</td><td rowspan="2">一轮优 化时刻</td><td rowspan="2">二轮优 化时刻</td></tr><tr><td>次数</td><td>次数</td><td>原时刻</td></tr><tr><td>JD5637</td><td>GS</td><td>15</td><td>4</td><td>0705</td><td>0705</td><td>0700</td></tr><tr><td>JD5548</td><td>TOL</td><td>26</td><td>16</td><td>0710</td><td>0720</td><td>0710</td></tr><tr><td>HU7094</td><td>GS</td><td>30</td><td>7</td><td>0720</td><td>0710</td><td>0720</td></tr><tr><td>MF8257</td><td>GS</td><td>27</td><td>12</td><td>0740</td><td>0745</td><td>0740</td></tr><tr><td>HU7398</td><td>TOL</td><td>30</td><td>9</td><td>0745</td><td>0730</td><td>0745</td></tr><tr><td>MF8133</td><td>GS</td><td>21</td><td>7</td><td>0745</td><td>0740</td><td>0745</td></tr><tr><td>CA1915</td><td>TOL</td><td>29</td><td>9</td><td>0750</td><td>0720</td><td>0750</td></tr><tr><td>HU7949</td><td>AND</td><td>29</td><td>16</td><td>0805</td><td>0835</td><td>0805</td></tr><tr><td>MF8077</td><td>AND</td><td>10</td><td>4</td><td>0830</td><td>0805</td><td>0830</td></tr><tr><td>NX121</td><td>TOL</td><td>31</td><td>27</td><td>0855</td><td>0900</td><td>0855</td></tr><tr><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td></tr></table></body></html>

表6优化前后延误情况对比  

<html><body><table><tr><td colspan="4">平均计划 平均运行 平均</td><td rowspan="2">超机场容量 超走廊口流量</td></tr><tr><td colspan="3">偏移成本 延误成本总成本</td></tr><tr><td></td><td></td><td></td><td>时刻数</td><td>限制时刻数</td></tr><tr><td>/min</td><td>/min</td><td>/min</td><td></td><td></td></tr><tr><td>优化前</td><td>10.02 34.28</td><td>44.31</td><td>6</td><td>29</td></tr><tr><td>优化后</td><td>14.87</td><td>18.75 33.63</td><td>0</td><td>8</td></tr></table></body></html>

# 3.3 参数灵敏度分析

# 3.3.1时刻最大调整量灵敏度分析

在其他参数不变的情况下，仅改变时刻最大调整量，相应变化如表7所示。从结果可以看出，时刻最大调整量设定为某一数值时，调整航班数量达到最大值，超过或低于此数值调整航班数量都会减少。说明随着时刻最大调整量这一约束的放宽，可以调整更少的航班满足时刻容量约束，但会导致部分航班调整后时刻与期望时刻偏差过大，可能造成总偏移量不降反增，且不符合实际需求。反观时刻最大调整量减小，可调整的航班数量有所降低，总偏移量迅速下降，整个时刻表可调整的幅度减小，会出现部分时刻依然超容量。同时，平均计划偏移成本和平均运行延误成本都没有显著变化，说明该参数对目标函数没有显著影响。

表7时刻最大调整量灵敏度分析  

<html><body><table><tr><td rowspan="2">时刻最大 调整量</td><td></td><td>调整总偏移量</td><td>平均计划</td><td>平均运行</td></tr><tr><td>调整航班 数量/个</td><td>/ min</td><td>偏移成本</td><td>延误成本</td></tr><tr><td>/min</td><td></td><td></td><td>/min</td><td>/min</td></tr><tr><td>45</td><td>42</td><td>1440</td><td>14.00</td><td>28.55</td></tr><tr><td>40</td><td>46</td><td>1300</td><td>14.10</td><td>28.59</td></tr><tr><td>35</td><td>48</td><td>1175</td><td>14.23</td><td>28.62</td></tr><tr><td>30</td><td>51</td><td>1050</td><td>14.87</td><td>28.75</td></tr><tr><td>25</td><td>52</td><td>925</td><td>14.61</td><td>28.72</td></tr><tr><td>20</td><td>49</td><td>700</td><td>14.73</td><td>28.61</td></tr><tr><td>15</td><td>45</td><td>530</td><td>14.89</td><td>28.57</td></tr></table></body></html>

# 3.3.2机场容量灵敏度分析

仅改变机场 $5 ~ \mathrm { m i n }$ 容量值，相应变化如表8所示。当容量值增大时，调整的时刻数量和总偏移量均有明显变化；当容量值较小时，原计划表中不满足约束需调整的时刻数量增长，调整总偏移量也随之增加。另一方面，当容量增加时，平均计划偏移成本和平均运行延误成本都有减小的趋势，说明时刻可容纳的航班越多，越容易满足航空公司需求，实际延误也会随之降低。但现实中，往往由于机场基础设施建设不足等一些原因，不能短时间内实现容量的提升。

表8机场容量灵敏度分析  

<html><body><table><tr><td rowspan="2">容量值</td><td rowspan="2">调整时刻数量</td><td rowspan="2">调整总偏移量 /min</td><td>平均计划</td><td>平均运行</td></tr><tr><td>偏移成本 /min</td><td>延误成本 /min</td></tr><tr><td>2</td><td>93</td><td>1770</td><td>26.98</td><td>29.25</td></tr><tr><td>3</td><td>51</td><td>1050</td><td>14.87</td><td>28.75</td></tr><tr><td>4</td><td>44</td><td>1070</td><td>14.30</td><td>27.66</td></tr></table></body></html>

# 4 结束语

本文以机场航班时刻为研究对象，结合实际运行问题和规律，借助MATLAB工具构建了基于历史数据的的航班时刻优化模型，并设计匈牙利算法求解。利用杭州萧山机场历史运行数据，验证了航班优化模型的可行性和适用性。该方法可有效减少超容量时段，降低机场运行延误，并进一步提升机场航班量，缓解管制工作压力。本文数据分析及时刻优化围绕单机场离场航班，下一步可对机场网络航班时刻优化及算法改进加以研究。

# 参考文献：

[1]Fisher JB.Managing demand to reduce airport congestion and delays [J].

Transportation Research Record,1989 (1218): 1-10.   
[2] Zografos K G,Martinez W. Improving the performance of a port system through service demand reallocation [J].Transportation Research Part B Methodological, 1990,24 (2): 79-97.   
[3]Grekos M.Airports commission: interim report [R/OL].[2014-12-22]. http://www.gov.uk/government/uploads/system/uploads/attachment_data/fi le/271231/airports-commission-interim-report.pdf.   
[4]Bertsimas D, Gupta S.A proposal for network air traffc flow management incorporating fairness and airline collaboration $[ \mathrm { C } ] / \hbar$ Proc of Operations Research.2011.   
[5]Bennell JA,Mesgarpour M,Bennell JA.Airport runway scheduling [J]. 4OR Quarterly Journal of the Belgian,French and Italian Operations Research Societies,9 (2): 115-138.   
[6]Clarke JP B,Brooks J,McClain E,et al. Investigation,modeling,and analysis of integrated metroplex arrival and departure coordination concepts, NASA Technical Reports [R]. 2012: 56-71.   
[7]Sama M,D'Ariano A,D'Ariano P,et al. Optimal aircraft scheduling and routing at a terminal control area during disturbances [J]. Transportation Research Part C Emerging Technologies,2014,47:61-85.   
[8]Jacquillat A, Odoni A R.An Integrated scheduling and operations approach to airport congestion mitigation.[J]. Operations Research,20l7,63 (6): 1390-1410.   
[9]Pyrgiotis N, Odoni A. On the impact of scheduling limits: a case study at newark liberty international airport [J]. Transportation Science,2016,50: 150112072345006.   
[10]Bolic T,Casteli L,Rigonat D.Peak-load pricing for the European air traffic management system using modulation of en-route charges [J]. European Journal of Transport & Infrastructure Research,2017,17 (1):136-152.   
[111固墩李军华一种滋足方向约审的动太该捆划方注「计管却应

用研究，2018(7):1-2.(Zhou Lu,Li Junhua.Dynamic route planning method based on directional constraints [J].Application Research of Computers,2018 (7): 1-2. ) [12]李开红，肖辉,李横，等．基于匈牙利算法的战时运油车前送油料调度 优化模型研究[J]．四川兵工学报,2015,36(6):61-65.(LiKaihong,Xiao Hui,Li Heng,et al.Scheduling optimization model of forward POL transportation byoil tank car on wartime based on hungarian-algorithm[J]. Journal of Sichuan Ordnance,2015,36 (6): 61-65.) [13]张洁，潘聪，孙寅斌，等．基于改进匈牙利算法和模糊逻辑控制的 Interbay 物料运输系统调度方法[J].上海交通大学学报,2016,50 (5):   
647-653,659.(Zhang Jie,Pan Cong,Sun Yinbin,et al.Modified Hungarian algorithm and fuzzy logic control-based scheduling method for interbay material handling system [J]. Journal of Shanghai Jiao Tong University,   
2016,50 (5): 647-653,659.) [14]李廷鹏，钱彦岭，李岳．基于改进匈牙利算法的多技能人员调度方法 [J].国防科技大学学报,2016,38(2):144-149.(LiTingpeng,Qian Yanling, Li Yue.Multi-skilled labor allocating method based on improved hungary algorithm[J]. Journal of National University of Defense Technology,2016,   
38 (2): 144-149. ) [15]张惠珍，马良．几种基于匈牙利算法求解二次分配问题的方法及其分 析比较[J].运筹与管理,2010,19(1): 92-99.(Zhang Huizhen,Ma Liang. Empirical comparative analysis of the solution methods for the quadratic assignment problem based on the Hungarian algorithm [J]. Operations Research and Management Science,2010,19 (1): 92-99.) [16]周莉，张维华，徐射雕．求解指派问题的一次性分配算法[J].计算机 工程与应用,201,47(18):135-138.(Zhou Li, Zhang Weihua, Xu Shediao. One-time assignment algorithm to solve assignment problem [J]. Computer Engineering and Applications,2011,47 (18): 135-138. )