# 基于时间延迟的多类型维修与经济生产批量联合优化研究

刘勤明，吕文元，叶春明(上海理工大学 管理学院，上海 200093)

摘要：针对目前未能较好的综合考虑多维修类型与经济生产批量联合优化的问题，首先考虑多类型维修关系，基于时间延迟理论求出故障和缺陷次数的表达式；其次，在此基础上，综合考虑生产费用和维修费用的基础上，构建了多类型维修和经济生产批量联合优化模型，以单位时间内总费用最小为优化目标，获得最优检查间隔期和经济生产批量；最后，通过算例分析验证了模型的有效性，说明了第一类缺陷检查次数的多少对费用和经济生产批量影响不大。

关键词：多类型维修；经济生产批量；检查间隔期；时间延迟；联合优化中图分类号：F273

# Joint optimization of multiple maintenance type and economic operation quantity with time delay

Liu Qinming, Lyu Wenyuan, Ye Chunming (Business School,University ofShanghai forScienceand Technology,Shanghai2ooo93,China)

Abstract: Currently,te jointoptimization problemofmultiple maintenance typesand economic operation quantity hasn'tbeen beter considered.First,byconsideringmultipletypemaintenancerelationship,basedontimedelaytheory,theexpressionsof thenumberoffaultsanddefectscanbeobtained.Then,productioncostand maintenancecost arecomprehensivelyconsidered. Anda joint optimization modelofmultiple maintenance typesand economic production quantity is proposed inorder to obtain theoptimal inspectionintervalandeconomic productionquantity.Theminimumtotalcostperunit timecanbe describedasthe optimizationobjective.Fiall,theefectiveness ofthe modelisverifiedbyacasestudy,andtheinflueneofinspectiontimes on thecostand economic productionquantityare analyzed,andit shows thatthe numberoffirst typeofdefect inspection has little effect on the cost and the economic production lot.

Key Words: Multiple maintenance type; Economic production quantity; Inspection interval; Time delay; Joint optimization

# 0 引言

维修计划和生产计划的制订是制造企业两个重要的内容。生产计划认为设备在计划期内是正常运行的，维修计划保持设备的正常运行，但是维修会耗费设备的实际生产时间，导致设备的实际有效产能时间比预期低。而维修计划制订的不合理，生产计划将无法正常顺利进行，影响企业交货，导致客户订单延迟，降低了顾客满意度。

经济生产批量的提出前提是设备在计划期内是正常运行的，不能正确反映企业设备实际的运行情况，从而确定的经济生产批量不够精确。针对这个不足，有很多文献研究考虑设备运行状况对经济生产批量的影响问题。Da等人[I将预测维修整合到经济生产批量模型中，并采用自回归积分移动平均模型预测系统健康指标。Chen等人[2]提出了一个改进的经济生产批量模型，在该研究中，最优生产和产品参数的确定是基于最大限度地减少社会预期的总损失，包括生产者的制造成本和顾客受损失情况下的使用成本。陈杰等人[3提出了柔性生产下马氏需求的经济生产批量模型，主要考虑了设备生产率和单位生产成本不变的情形。Xu等人4提出了一个在有限计划期内最大生产运行时间和最小预防性维护时间的经济批量生产问题，并基于松弛问题的最优性质提出了两种启发式算法。Jafari 等人[5提出了一个新的模型来找到复杂生产设备的最优经济生产数量和预防性维护策略。郭彩云和胡劲松等人[7,8]考虑了产品缺陷率和废品率不是固定值情况下的经济生产批量模型。胡劲松等人[9在此基础上，进一步基于生产缺陷随机发生的情况，研究了允许缺货的经济生产批量问题。郑睿等人[10]基于时间延迟理论，建立了缺乏维修检查数据情况下的设备维修间隔期优化模型。金圭等人[1进行了设备预防维修与经济生产批量的联合研究，但是只考虑了设备的可靠性，缺陷和故障维修时间都没有考虑。Chakraborty等人[2]在设备存在缺陷和发生随机故障的情形下，综合考虑了生产、库存、维修模型。翟勇洪和马慧民等人[13,14]研究了大规模生产和协同生产的情况。综上所述，目前大多数研究建立的模型都是单一缺陷类型单一产品的生产系统，虽然有些研究考虑了多类型缺陷维修问题[15\~18]，但是没有综合考虑生产计划。由于企业维修计划与生产计划都是重要环节，因此，本文将综合考虑多缺陷维修类型与经济生产批量的联合优化。

针对以上问题，综合分析了生产设备的缺陷和故障情况，结合经济生产批量，提出了以单位时间总费用期望值最小为优化目标、以维修间隔期和经济生产批量为自变量的设备多维修类型和经济生产批量联合优化决策模型。在模型中，基于时间延迟理论，获得设备故障次数和缺陷次数的表达式。在此基础上，综合考虑了生产费用和维修费用，包括生产准备费用、库存费用、检查费用、故障维修费用和缺陷维修费用。并且，利用各检查间隔期间的嵌套性质以及枚举法，确定了生产设备的最优检查间隔期，并求出了相应的最优经济生产批量，还进一步分析了检查次数对费用和经济生产批量的影响。帮助企业管理层制定有效可靠的生产计划以及维修计划。

# 1 问题描述

本文主要研究生产过程中设备如何确定维修类型的检查周期和相应的经济生产批量，使得设备停机时间最少并可以生产单位时间内总费用最少的经济生产批量。其中维修类型的检查活动和生产过程如图1所示： $P$ 为产品生产率， $D$ 为产品需求率， $T$ 为设备生产运行时间， $T _ { p }$ 为生产周期，各维修类型的检查活动在设备运行期间进行，第 $N$ 类维修类型的检查周期恰好等于设备运行时间,显然,都小于生产周期,即TN= T<Tp‘

![](images/08648c557677dd679f2046aca553bde38b05621fce137e82c5ca5d3ae685ee7a.jpg)  
图1检查维修与生产批量关系图

该模型利用时间延迟理论，综合考虑了每类检查下的缺陷及故障状况，另外，故障造成的停机时间忽略不计，所包含的费用主要为检查费用、缺陷维修费用、故障维修费用、生产准备费用、库存费用等，优化目标是单位时间内总费用的期望值最小，通过求解目标函数，得出两个最优的决策变量：每类缺陷的最优检查维修间隔期T\*和经济批量 $Q ^ { * }$ 。

# 2 假设条件

a)产品生产率 $P$ 和需求率 $D$ 是常量，且 $P { > } D$

b）设备有 $N$ 中维修类型，记为 $\scriptstyle i = 1 , 2 , 3 , \dotsc , N _ { \circ }$ 即如果 $k { > } i$ ，则第 $k$ 类检查包括第 $i$ 类检查，且包含的第 $i$ 类检查与单独进行 $i$ 类检查所需要的费用、发现的故障次数以及故障维修所需要的费用期望值皆相同；

c）设备缺陷分为 $N { + } 1$ 类，第 $i$ 类检查识别出第 $\mathbf { \delta } _ { 1 , 2 , \dots , i }$ 类缺陷 $( i \leq N )$ ，而第 $N$ 类检查可以识别出第1至 $N$ 类缺陷。假设存在第 $N { + } 1$ 类缺陷，该类缺陷没有时间延迟，一旦发生即为故障，显然任何检查都不能识别。这类缺陷只在最后一类检查中存在且后续只有维修费用；

d)维修类型的检查间隔期都在设备运行时间内且小于设备的生产周期;e)每类型缺陷的维修检查不影响生产。

# 3 模型符号

基本符号如表1所示。

表1基本符号  

<html><body><table><tr><td>符号 说明</td><td></td></tr><tr><td>P</td><td>产品生产率</td></tr><tr><td>Tp</td><td>生产周期</td></tr><tr><td>K</td><td>生产准备费用</td></tr><tr><td>t</td><td>基本的工作日，如1天或者1年</td></tr><tr><td>Cfi</td><td>第i类故障的维修费用均值</td></tr><tr><td>Cpi</td><td>第i类缺陷的检查费用均值</td></tr><tr><td>Cri</td><td>第i类缺陷的维修费用均值</td></tr><tr><td></td><td>设备的缺陷发生率</td></tr><tr><td>αi</td><td>N 第i类缺陷占总缺陷的比率， ∑α=1</td></tr><tr><td></td><td>i=1 第i类检查的检查周期，T=nt，T=niTi-1,</td></tr><tr><td>Ti</td><td>T² =I[nj𝑡,i = 1,2,...,N</td></tr><tr><td>ni</td><td>第i类检查周期与第i-1类检查周期的比值</td></tr><tr><td></td><td>第i类检查的检查次数，在TN时，设备只进行1次第N</td></tr><tr><td>mi</td><td>类检查，即mN ＝1，mN=nNmN =nN，</td></tr><tr><td></td><td>m；= Inj,i = 1,2,...,N -1</td></tr><tr><td></td><td>j=i+1</td></tr><tr><td>FO</td><td>第i类缺陷的时间延迟概率分布函数</td></tr><tr><td>fiO</td><td>第i类缺陷的时间延迟概率密度函数</td></tr><tr><td>ENf(Ti)</td><td>第i类缺陷在Ti检查周期间劣化成为故障次数的期望值</td></tr><tr><td>ENr(Ti)</td><td>在Ti检查周期间的i类检查时所检查出缺陷次数的期望值</td></tr><tr><td>EC(n)</td><td>在TN期间总费用的期望值</td></tr><tr><td></td><td></td></tr><tr><td>ECT(n)</td><td>单位时间内总费用的期望值</td></tr></table></body></html>

# 4 模型建立

# 4.1生产准备费用和库存费用

由图1可知，生产周期公式如下：

$$
T _ { \rho } ~ = ~ { \frac { { \mathcal { P } } ~ \times ~ T } { D } }
$$

库存费用表达式如下：

$$
I \ = \ { \frac { \left( P \ - \ D \right) \times T \times H \times T _ { p } } { 2 } }
$$

生产准备总费用 $\scriptstyle = K$

# 4.2检查费用期望值

在 $T _ { N }$ 期间，设备只进行1次第 $N$ 类检查，即 $m _ { N } \ = 1$ ，由于嵌套关系，该过程也包含 $N { - } 1$ 类检查，例如，在这个过程中,所包含的第N-1类检查的次数为mN-1 = nNmN = nN'依此类推，其余检查的次数可以用$m _ { i } \ = \ \prod _ { j = i + 1 } ^ { N } n _ { j } , i \ = \ o { 1 } { , 2 } , \dots , N - 1$ 表示。又因为每次检查的费用是已知的，则 $T _ { N }$ 期间总的检查费用期望值为

$$
\begin{array} { l } { { \displaystyle E C ( p ) = C _ { p N } + \sum _ { i = 1 } ^ { N - 1 } m _ { i } C _ { p i } = C _ { p N } + \sum _ { i = 1 } ^ { N - 1 } \prod _ { j = i + 1 } ^ { N } n _ { j } C _ { p i } } } \end{array}
$$

# 4.3故障维修费用期望值

在 $T _ { N }$ 期间，有 $\dot { n } _ { N }$ 次第 $N { - } 1$ 类检查，每进行第 $N { - } 1$ 类检查所遇到的故障次数是 $E N _ { f } \big ( T _ { N - 1 } \big )$ ，则第 $N { - } 1$ 类检查时的故障维修费用期望值为 $E N _ { _ { f } } ( T _ { N - 1 } ) C _ { f ( N - 1 ) }$ ，则在整个 $T _ { N }$ 期间，第 $N { - } 1$ 类检查总的故障维修费用期望值为：

$$
n _ { \scriptscriptstyle N } E N _ { \scriptscriptstyle f } \big ( T _ { _ { N - 1 } } \big ) C _ { _ { f } ( _ { N - 1 } ) }
$$

因为所包含的第 N-2类检查的次数为mN-2 = nNnN-1'则第 $N { - } 2$ 类检查总的故障维修费用期望值为

$$
n _ { N - 1 } n _ { N } E N _ { f } ( T _ { N - 2 } ) C _ { f ( N - 2 ) }
$$

同理，第 $N { - } 3$ 类检查总的故障维修费用期望值为

$$
n _ { N - 2 } n _ { N - 1 } n _ { N } E N _ { _ { F } } ( T _ { N - 3 } ) C _ { _ { F } ( N - 3 ) }
$$

因此，在 $T _ { N }$ 期间，总的故障维修费用期望值为：

$$
E C \left( f \right) = \sum _ { i = 1 } ^ { N - 1 } \prod _ { j = i + 1 } ^ { N } \left[ n _ { j } E N _ { f } \left( T _ { i } \right) C _ { f i } \right] +
$$

$$
E N _ { _ f } \left( T _ { _ N } \right) C _ { f N } + \lambda \alpha _ { _ { N + 1 } } T _ { _ N } C _ { _ { f \left( N + 1 \right) } }
$$

式(7)中的最后一项是由服从零时间延迟的缺陷引起的故障，表示该类故障维修费用的期望值。

# 4.4缺陷维修费用期望值

参考4.3节，可同理获得缺陷维修费用期望值：

$$
E C \big ( r \big ) = \sum _ { i = 1 } ^ { N - 1 } \prod _ { j = i + 1 } ^ { N } \big [ n _ { j } E N _ { r } \big ( T _ { i } \big ) C _ { r i } \big ] + E N _ { r } \big ( T _ { N } \big ) C _ { r N }
$$

# 4.5联合优化模型

基于式(1)-(3)(7)和(8)，设备在 $T _ { N }$ 总费用期望值为

$$
\begin{array} { l } { E C \displaystyle \left( n \right) = \sum _ { i = 1 } ^ { N - 1 } \Biggl [ \prod _ { j = i + 1 } ^ { N } n _ { j } \bigl ( C _ { p i } + E N _ { f } \left( T _ { i } \right) C _ { f i } + E N _ { r } \left( T _ { i } \right) C _ { r i } \bigr ) \Biggr ] + } \\ { C _ { p N } + E N _ { f } \left( T _ { N } \right) C _ { f N } + \lambda \alpha _ { N + 1 } T _ { N } C _ { f \left( N + 1 \right) } + } \\ { E N _ { r } \left( T _ { N } \right) C _ { r N } + K + \frac { \left( P - D \right) \times T \times H \times T _ { p } } { 2 } } \end{array}
$$

$h$ 表示从发生缺陷到形成故障的时间间隔，其概率分布函数表示为 $F ( h ) _ { \circ }$ 对于第 $i$ 类缺陷，其时间延迟分布函数为 $F _ { i } ( h )$ ，由假设可知其发生率为 $\lambda \alpha _ { i }$ ，其对应的故障发生次数的期望值和发现并排除缺陷次数的期望值为：

$$
E N _ { { t } } ( T _ { i } ) = \alpha _ { i } \int _ { 0 } ^ { T _ { i } } \lambda F _ { { i } } ( T _ { i } - u ) d u
$$

$$
\begin{array} { r } { E N _ { r } \big ( T _ { i } \big ) = \alpha _ { i } \int _ { 0 } ^ { T _ { i } } \lambda \big [ 1 - F _ { i } \big ( T _ { i } - u \big ) \big ] d u } \end{array}
$$

因此

$$
\begin{array} { l } { \displaystyle E C \left( n \right) = \sum _ { i = 1 } ^ { N - 1 } \Biggl [ \prod _ { j = i + 1 } ^ { N } n _ { j } \left( C _ { p i } + \lambda \alpha _ { i } \left( C _ { f i } - C _ { n } \right) \int _ { 0 } ^ { T _ { i } } F _ { i } \left( u \right) d u \right) + \lambda \alpha _ { i } T _ { i } C _ { n } \Biggr ] + } \\ { \displaystyle C _ { p N } + \lambda \alpha _ { N } \left( C _ { f N } - C _ { r N } \right) \int _ { 0 } ^ { T _ { N } } F _ { N } \left( u \right) d u + \lambda \alpha _ { N + 1 } T _ { N } C _ { f \left( N + 1 \right) } + } \\ { \displaystyle \lambda \alpha _ { N } T _ { N } C _ { r N } + K + \frac { \left( P - D \right) \times T \times H \times T _ { p } } { 2 } } \end{array}
$$

同时，

$$
E C T ( n ) = \frac { E C \bigl ( n \bigr ) } { T _ { p } } = \frac { E C \bigl ( n \bigr ) \times D } { P \times T }
$$

由各类型检查间的检查间隔期的关系可知，$T _ { \scriptscriptstyle N } \ = \ \prod _ { j = i + 1 } ^ { \cal N } n _ { j } T _ { i } \ , \ { \mathcal { H } } \wedge { \vec { \mathrm { x } } } { \vec { \mathrm { x } } } ( 1 1 ) { \overline { { \mathrm { u j } } } } { \tilde { \mathrm { \not { q } } } }$

$$
\begin{array} { l } { E C T ( n ) = \displaystyle \frac { D } { P } \left\{ \sum _ { i = 1 } ^ { N } \left\{ \frac { 1 } { T _ { i } } \left[ C _ { p i } + \lambda \alpha _ { i } \left( C _ { i i } - C _ { r i } \right) \int _ { 0 } ^ { T _ { i } } F _ { i } \left( u \right) d u \right] + \lambda \alpha _ { i } C _ { r i } \right\} + \lambda \alpha _ { N + 1 } C _ { r ( N + 1 ) } \right\} + } \\ { \displaystyle \frac { K \times D } { P \times \prod _ { j = i + 1 } ^ { N } n _ { j } T _ { i } } + \frac { \left( P - D \right) \times \prod _ { j = i + 1 } ^ { N } n _ { j } T _ { i } \times H } { 2 } } \end{array}
$$

# 5 模型求解

模型优化的目标是求出每类检查的最优维修间隔期和相应的经济生产批量，由于模型中有多个检查的未知检查间隔期变量，直接求解过于复杂，为了说明该模型的正确性以及适用性，本文为了优化求解过程，仅考虑两类型检查的预防维修与经济生产批量模型研究，因为 $T _ { \mathrm { 2 } } ~ = ~ n _ { \mathrm { 2 } } T _ { \mathrm { 1 } }$ ，据此，可以简化式(12)得

$$
\begin{array} { l } { \displaystyle E C T \big ( n \big ) = \frac { D } { P } \Bigg \{ \frac { 1 } { T _ { _ { _ { _ { _ { _ { _ { _ { _ { 2 } } } } } } } } } } \Bigg [ C _ { _ { p 1 } } + \lambda \alpha _ { _ { 1 } } \big ( C _ { _ { f 1 } } - C _ { _ { r 1 } } \big ) \int _ { 0 } ^ { T _ { _ { 1 } } } F _ { _ { 1 } } \big ( u \big ) d u \Bigg ] + \lambda \alpha _ { _ { 1 } } C _ { _ { r 1 } } + \frac { 1 } { n _ { _ { 2 } } T _ { _ { 1 } } } } \\ { \displaystyle \Bigg [ C _ { p 2 } + \lambda \alpha _ { _ { 2 } } \big ( C _ { _ { f 2 } } - C _ { _ { r 2 } } \big ) \int _ { 0 } ^ { n _ { _ { 2 } } \mathcal { A } _ { 1 } } F _ { _ { 2 } } \big ( u \big ) d u \Bigg ] + \lambda \alpha _ { _ { 2 } } C _ { _ { r 2 } } + \lambda \alpha _ { _ { 3 } } C _ { _ { r 3 } } \Bigg \} ^ { + } } \\ { \displaystyle \frac { K \times D } { P \times n _ { _ { 2 } } \times T _ { _ { 1 } } } + \frac { \big ( P - D \big ) \times n _ { _ { 2 } } \times T _ { 1 } \times H } { 2 } } \end{array}
$$

具体求解思路如下：

${ \mathrm { a } ) n _ { 2 } }$ 是第二类维修检查间隔期与第一类维修检查间隔期的比值，且该比值是整数，由于两类检查的间隔期显然是不相等的，所以本文假定 $n _ { 2 }$ 的取值范围是2\~10包括端点值的整数，通过枚举法，赋予 $n _ { 2 }$ 依次取相应的值， $n _ { 2 }$ 值确定后，式(13)可以简化为给定 $n _ { 2 }$ 值后只含单个未知变量 $T _ { 1 }$ 的最优解求解问题。

b)通过构造线性函数，可以求出每个相应 $\mathbf { \delta } _ { n _ { 2 } }$ 值下的最优解$T _ { 1 }$ 。

c)求出各个最优解后，通过对比分析每类情形下的最优值，最后求出每类维修类型的最优维修间隔期 $T ^ { * }$ 和经济批量 $Q ^ { * }$ 。

# 6 算例分析

某生产企业有一设备，该设备缺陷发生率服从齐次泊松分布过程， $\lambda = 0 . 5$ ，其时间延迟分布为指数分布，尺度参数为 $\beta$ $\scriptstyle i = 1 , 2 , \ldots , N$ ，表达式： $F _ { _ { i } } ( u ) = 1 - \exp ( - \beta _ { _ i } u )$ ，该设备的生产率 $P { = } 1 0 0 0$ ，生产的产品需求率 $D { = } 5 0 0$ ，每次生产准备费用$K = 2 0 0$ ，库存费用 $\scriptstyle H = 0 . 5$ ，假设设备只有两类检查，即每类检查对应一种缺陷类型，由于该案例中有一种缺陷是服从零时间延迟的，所以解决的是两类型检查、三种缺陷的经济生产批量决策问题，其他参数值如表2所示。

表2相关参数值  

<html><body><table><tr><td>i=1</td><td>i=2</td><td>i=3</td></tr><tr><td>Cf1 =80</td><td>Cf2 = 120</td><td>Cf3 =80</td></tr><tr><td>Cp1 = 15</td><td>Cp2 = 45</td><td></td></tr><tr><td>Cr1 = 27</td><td>Cr2 =40</td><td></td></tr><tr><td>α =0.6</td><td>α= 0.3</td><td>α= 0.1</td></tr><tr><td>β=0.15</td><td>β=0.02</td><td></td></tr></table></body></html>

将数据代入式(13)得

$$
\begin{array} { l } { \displaystyle { E C T \big ( n \big ) = \frac { - 9 1 } { 2 T _ { 1 } } + \frac { 5 3 } { T _ { 1 } } e ^ { \frac { - 3 } { 2 0 } T _ { 1 } } - } } \\ { \displaystyle { \frac { 3 5 5 } { 2 \times n _ { 2 } T _ { 1 } } + \frac { 3 0 0 } { n _ { 2 } T _ { 1 } } e ^ { \frac { - n _ { 2 } } { 5 0 } T _ { 1 } } + 1 2 5 n _ { 2 } T _ { 1 } + 2 3 } } \end{array}
$$

利用 MATLAB求出相对比较接近的几种固定 $n _ { 2 }$ 值下的 $T _ { 1 }$ 和 $E C T ( n )$ 的最优值，如图2所示。

![](images/7ad744734d54ce033e0829e0c3456b081d007a5b3b49aa6e1f75224c70dacf7b.jpg)  
图2不同 $n _ { 2 }$ 值下的单位时间内的总费用期望值

相应的最优维修间隔期和经济生产批量如表3所示。由表3可知，最优的取值如下： $n _ { 2 } ^ { * } = 2$ ， $T _ { 1 } ^ { * } = 1 8 9 \mathrm { d }$ ， $T _ { 2 } ^ { * } =$

378 d(一年 $3 6 0 \mathrm { d } )$ 0 $Q ^ { * } = 1 0 5 1$ ， $E C T ( n ) ^ { * } = 2 7 1 . 6$ ；从表3中可以看出， $n _ { 2 }$ 取值的增大对 $T _ { 2 }$ 、Q、 $E C T ( n )$ 的影响呈现相同方向，且影响大致相同，但在 $n _ { 2 }$ 增加的情形下时， $T _ { 1 }$ 在减小。随着 $n _ { 2 }$ 值的逐渐增加，第一类维修类型的检查间隔期在逐渐缩短；相反第二类的在逐渐增加。另外，随着 ${ \bf \ddot { \sigma } } n _ { 2 }$ 取值的逐渐增加，单位时间内总费用的期望值在逐渐增加，所以可以看出当 $n _ { 2 } = 2$ 时，此时费用最低。从表3还可以看出，经济生产批量大体上在增加，单位时间内的维修费用期望值在平稳增加，说明第一类缺陷检查次数的多少对费用和经济生产批量影响不太大。因此，通过联合优化模型，可以获得每种维修类型的最优检查间隔期，制定合理的经济生产批量。

表3取不同值的各相关值  

<html><body><table><tr><td>n2</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td></tr><tr><td>T1</td><td>0.5253</td><td>0.3535</td><td>0.2727</td><td>0.2222</td><td>0.1919</td><td>0.1717</td></tr><tr><td>T</td><td>1.0506</td><td>1.0605</td><td>1.1908</td><td>1.111</td><td>1.1514</td><td>1.2019</td></tr><tr><td>Q*</td><td>1051</td><td>1061</td><td>1191</td><td>1111</td><td>1151</td><td>1202</td></tr><tr><td>ECT(n)*</td><td>271.6</td><td>278.6</td><td>285.4</td><td>292.1</td><td>298.6</td><td>305.1</td></tr></table></body></html>

# 7 结束语

本文基于时间延迟理论，综合考虑了生产准备费用、库存费用、检查费用、故障维修费用和缺陷维修费用，以单位时间总费用期望值最小为优化目标建立了多维修类型与经济生产批量联合优化决策模型模型。联合优化模型确定了各维修类型的最优检查间隔期和经济生产批量，同时优化了维修计划和生产计划，弥补了只考虑单一缺陷类型检查的生产计划模型的不足。并且，与单一缺陷类型情形下相比，多缺陷类型情形下，设备的实际有效产能时间变短，可以精确设备的实际有效产能，使模型对生产更有指导意义。未来可以进一步研究维修类型与各类型多产品的经济生产批量的联合优化问题。

# 参考文献：

[1]Da W,Pan E,Wang Y,et al.An economic production quantity model for a deteriorating system integrated with predictive maintenance strategy [J]. Journal of Intelligent Manufacturing,2014,27(6):1-11.   
[2]Chen CH, Chou CY.The joint determination of specification limits,process mean,and economic manufacturing quantity [J].Journal of the Chinese Institute of Industrial Engineers,2017,34(4): 283-288.   
[3] 陈杰，陈崇萍，陈志祥，邢灵博.柔性生产下马氏需求EPQ模型的最优 (P,Q,T）策略[J].数学的实践与认识,2016,46 (02):84-93.   
[4]Xu Q, Xu J. Heuristics for the economic production quantity problem under restrictions on production and maintenance time [J].Mathematical Problems in Engineering,2016,2016: 1-9.   
[5]Jafari L, Makis V. Joint optimization of lot-sizing and maintenance policy fora partially observable two-unit system [J]. International Journal of Advanced Manufacturing Technology,2016,87 (5-8): 1-19.   
[6]Jafari L, Makis V. Optimal lot-sizing and maintenance policy for a partially observable production system [J]. Computers & Industrial Engineering, 2016, 93: 88-98.   
[7] 郭彩云，胡劲松，王磊．模糊环境下含缺陷率且允许缺货的经济生产批 量模型[J].计算机集成制造系统,2008,(11):2161-2166.   
[8]胡劲松，郭彩云．含缺货且缺陷产品可修复的模糊生产库存模型[J] 计算机集成制造系统,2009,15(5):932-938.   
[9]胡劲松，季雅萍，郭彩云，等．考虑缺货的模糊随机缺陷生产系统[J]. 控制与决策,2011,26(2):213-220.   
[10]郑睿，吕文元．基于时间延迟理论的预防维修模型及案例研究[J].中 国管理科学,2010,18 (2): 48-54.   
[11]金垚，潘尔顺，王莹．基于统计过程控制与维护策略的联合经济设计模 型[J]．计算机集成制造系统,2012,18(9):1964-1971.   
[12] Chakraborty T,Giri B C.Lot sizing in a deteriorating production system under inspections, imperfect maintenance and reworks [J]. Operation Research,2014,14(1): 29-50.   
[13]翟勇洪，梁玲，刘宇熹，等．面向大规模定制的再制造集约生产计划模 型[J].上海理工大学学报,2014,36(6):603-613.   
[14]马慧民，叶健飞．企业生产采购协同计划干扰管理研究[J].上海理工 大学学报,2015,37(3):301-306.   
[15] Nobil A H, Sedigh A H A.A multiproduct single machine economic production quantity (EPQ) inventory model with discrete delivery order, joint production policy and budget constraints [J].Annals of Operations Research,2017, (9): 1-37.   
[16]吕文元，郑睿．基于时间延迟的维修类型优化组合模型及案例分析[J]. 系统工程理论与实践,2013,33(07):1654-1660.   
[17]郑睿，吕文元．考虑故障停机的生产控制与维修计划联合决策模型[J]. 中国管理科学,2016,24(8):116-122.   
[18]崔铁军，李莎莎，马云东，等．有限制条件的异类元件构成系统的元件 维修率分布确定[J].计算机应用研究,2017,34(11):1-7.