# 智能电网互补能源供用电实时定价算法研究

李军祥，潘婷婷，高岩(上海理工大学 管理学院，上海 200093)

摘要：在智能电网背景下，针对化石能源短缺、峰时供电压力大的现状，提出了由光伏和化石燃料互补供电的方式，并建立了社会福利最大化用户侧微电网实时定价模型。该模型中，电力供应商通过制定实时电价来协调用户对两种类型能源所发电能的使用量，并设计了实时定价算法来求解模型。仿真结果表明，相比仅靠化石能源供电的大电网，互补供电方式能有效降低化石能源峰时供电量和价格，提升社会福利。这为以后智能电网的有效管理提供了参考。

关键词：智能电网；用户侧微电网；互补供电；实时定价；社会福利 中图分类号：TP391.9 doi:10.19734/j.issn.1001-3695.2018.09.0761

Real-time pricing algorithm for supply and demand of complementary energy on smart grid

Li Junxiang†, Pan Tingting, Gao Yan (Business School,University ofShanghai for Science&Technology,Shanghai 20oo93,China)

Abstract:Inthebackgroundofsmart grid,inconnectionoftheshortageoffosil energyandthehighpressureofpeak-time power supply, this paper developed amethod ofcomplementary power suplyof photovoltaic and fossil fuel.Itconstructed a real-time pricing model of user-side microgrid based on social welfare maximization.Inthe model,the power supplier coordinated thetwo types ofenergy sources byreal-time pricing. Besides,this paper designedareal-time pricing algorithm to solve the model.The simulation results show thatcompared with the large power grid using fosil energy alone,the complementary power supply mode can effectively reduce the power supply offosil energy and electricity price in peak time slots,and enhances the social welfare.The method offers areference forthe efective managementof smart grid in future.

Key words: smart grid; user-side microgrid; complementary power supply; Real-time pricing; social welfare

# 0 引言

随着智能电网的飞速发展以及城镇化的全面推进，人们对电能的需求量越来越大，现有的仅靠化石能源(煤炭等)发电的供电方式，不仅资源有限、环境污染严重且遇到用电高峰情况时易断电的问题。为此，各地大力支持发展可再生能源。太阳能资源在中国储量丰富，已成为可再生能源发电的主要能源之一。据国家能源局统计，截至2018年6月，全国新增光伏装机2430.6万千瓦，其中，光伏电站新增1206.2万千瓦，同比减少 $30 \%$ ；分布式光伏新增1224.4万千瓦，同比增长 $72 \%$ 。可见分布式光伏发电的发展迅速，其具有清洁高效、灵活分布的优势，但也面临难以实时消纳的问题，而在智能电网背景下，用户侧微电网的出现为分布式光伏发电系统提供了集成应用的平台[1\~3]。

智能电网就是电网的智能化，它具有坚强、自愈、互动、经济、优质、环保等特点[4]。用户侧微电网是智能电网的有机组成部分，是对智能电网的有力补充。结构上，用户侧微电网是指由分布式电源、负荷、储能装置、变流器以及监控保护装置有机整合在一起的小型发配电系统，其中分布式电源根据所使用能源类型可分为化石能源发电与可再生能源发电两种类型；形式上，用户侧微电网是指在居民小区、商业大楼、工业厂区用电上发展而来的微电网形式，它直接面向未来城镇用户，可以促进光伏发电就地消纳利用、提高电力系统能效[56]，但是如果用户不能实时消纳光伏所发的电能，将会增加用户侧微电网的储能成本甚至导致“弃光”现象。为了促进光伏电的实时消纳，对用户侧微电网采用需求侧管理技术，鼓励人们在适当的时候增加或减少电能消费，其中，基于价格的需求响应机制是最有效的一种需求侧管理技术[7].它是指电力用户根据电力市场价格信号（分时电价响应、尖峰电价响应、实时电价响应）主动改变固有电力消费模式的行为，当前最理想的电价需求响应方式是实时电价[8]。

实时电价概念最早由美国Schweppe 教授提出来的[8]，它指在考虑电力系统运行和满足基本投资条件下，在给定的极短的时间内向用户提供电能的边际成本。实时电价具有兼顾电力供应商侧和用户侧利益的优势，电力供应商通过制定合理的电价调整用户的用电行为，同时用户根据自身利益及时改变用电模式。通过不断更新实时电价最终形成电力供应商侧和用户侧良好的互惠互利模式，并满足电力供需平衡要求。然而，在制定实时电价过程中，如何实现电力供应商和用户之间的电力信息交流是关键，智能电表的出现为此问题提供了解决方案。结合大数据技术，智能电表设备除了有传统电表的电能计量功能之外，它还有实现用户和电力公司、用户和用户之间数据交换的功能。智能电表的应用为用户侧微电网实时定价提供了供需双向信息沟通的基础[9]。

目前，国内外关于实时定价的研究主要有：Samadi等人构建了以社会福利最大化为目标的实时电价模型，设计了实时定价算法求解模型，并验证了该模型对用户和电能供应商均有益[10]；随后，以社会福利最大化为目标的实时定价模型被广泛应用[\~13]。Song 等人[14]以改进效用函数的形式给出新的系统模型，并验证了该模型的有效性；Asadi等人[15]考虑了两类用户的效用函数，并采用粒子群算法求解模型；刘博等人[16将现实中的典型的电力用户归为三类，讨论了不同用户的效用函数，并验证了模型的有效性；金颖丰等人[4采用了光滑化方法对现有实时定价中常用的二次分段效用函数进行光滑处理，并仿真得到用户效用。在关于实时定价的研究中，以社会福利值最大化为目标的实时定价模型被广泛应用，并通过仿真验证了模型的有效性。但是，现有的实时定价模型并没有考虑构建用户侧微电网，没有将可再生能源作为发电单元之一。

本文在上述文献的研究基础上，针对智能电网中的用户侧微电网提出了采用光伏和化石燃料两种类型能源互补供电的方式，构建了社会福利最大化实时定价模型，并设计了一种适用于该模型的实时定价算法，最后，仿真结果验证了用户侧微电网实时定价模型的合理性和有效性。

# 1 系统模型

考虑一个用户侧微电网系统，其参与者包含一个电力供应商、多个居民用户，结构上包含屋顶光伏发电系统和燃料发电系统、储能设备、智能电表等。对用户侧微电网采用发供一体的运营模式[17,18],即由电力供应商投资并运营微电网。用户侧微电网中包含光伏和化石燃料两种类型能源互补供电：其中光伏属于清洁可再生能源，其发电成本低但发电具有间歇性、不稳定性，电力供应商只能通过气象预测光伏各时段的发电量，不能控制光伏发电量，如果用户不能及时消纳光伏电，则需将余电储存，同时也将产生储电成本；而化石燃料属于不可再生能源，其发电成本高且资源有限，但电力供应商可控制其发电量，故通过两种类型能源互补供电的方式来满足用户用电需求。如何通过实时电价协调用户对两种类型能源产生的电能的消耗量使电力供应商和用户均获得最大福利是本文研究的重点。通过智能电表可监控用户使用电能情况，并方便电力供应商和用户信息沟通，故在电力供应商端和每个用户端均装载了智能电表，为电力供应商制定实时电价提供了信息交流基础。

现假设：用户侧微电网中有 $n$ 个居民用户，用$N = \{ 1 , 2 , 3 , \cdots , n \}$ 表示居民用户的集合。将电能类型划分为光伏电和化石燃料电，分别用 $J _ { \mathrm { 1 } }$ 、 $J _ { 2 }$ 表示，用 $J = \{ J _ { 1 } , J _ { 2 } \}$ 表示用户使用的电能类型集合。将用户的一个用电周期划分为 $s$ 个细小的时段，令 $K = \{ 1 , 2 , 3 , \cdots , s \}$ 表示这些时段的集合。将每个用户 $i$ 在 $k$ 时段消耗的光伏电量和化石燃料电量分别表示为$x _ { J _ { 1 } , i } ^ { k }$ 、 $x _ { J _ { 2 } , i } ^ { k }$ ，则每个居民用户在 $k$ 时段消耗的用户侧微电网总电量为 $\textstyle \sum _ { J _ { j } \in J } x _ { J _ { j } , i } ^ { k }$ 。每个用户在 $k$ 时段使用的光伏电和化石燃料电的电量是有范围的，故将用户在 $k$ 时段使用光伏电最小、最大电量分别表示为 $P _ { i , \operatorname* { m i n } } ^ { k }$ 、 $P _ { i , \operatorname* { m a x } } ^ { k }$ ，即有 $x _ { J _ { 1 } , i } ^ { k } \in \left[ P _ { i , \operatorname* { m i n } } ^ { k } , P _ { i , \operatorname* { m a x } } ^ { k } \right]$ ；而将用户在 $k$ 时段使用化石燃料电的最小、最大用电量分别表示为 $m _ { i } ^ { k }$ 、 $M _ { i } ^ { k }$ ，即有 $x _ { J _ { 2 } , i } ^ { k } \in \left[ m _ { i } ^ { k } , M _ { i } ^ { k } \right]$ 。电力供应商在 $k$ 时段供应光伏电和化石燃料电总量可分别表示为 $L _ { J _ { 1 } } ^ { k }$ 、 $L _ { J _ { 2 } } ^ { k }$ ，则电力供应商在 $k$ 时段供电总量为 $\sum _ { J _ { j } \in J } { L _ { J _ { j } } ^ { k } }$ ，电力供应商在 $k$ 时段供应每种类型电能的电量也是有范围的，故将电力供应商在 $k$ 时段光伏电最小、最大发电量分别表示为 $L _ { J _ { 1 } , \mathrm { m i n } } ^ { k }$ 、 $L _ { J _ { \mathrm { 1 } } , \operatorname* { m a x } } ^ { k }$ ，即有$L _ { J _ { 1 } } ^ { k } \in \left[ L _ { J _ { 1 } , \operatorname* { m i n } } ^ { k } , L _ { J _ { 1 } , \operatorname* { m a x } } ^ { k } \right]$ ；将电力供应商在 $k$ 时段化石燃料电最小、最大发电量分别表示为 $L _ { J _ { 2 } , \mathrm { m i n } } ^ { k }$ 、 $L _ { J _ { 2 } , \operatorname* { m a x } } ^ { k }$ ，即有 $L _ { J _ { 2 } } ^ { k } \in \left[ L _ { J _ { 2 } , \operatorname* { m i n } } ^ { k } , L _ { J _ { 2 } , \operatorname* { m a x } } ^ { k } \right]$ 。如果要达到各时段电能供需平衡，则 $k$ 时段所有用户使用的总电量和电力供应商实际供电总量需满足：

$$
\textstyle \sum _ { i \in N } \sum _ { J _ { j } \in J } x _ { J _ { j } , i } ^ { k } = \sum _ { J _ { j } \in J } L _ { J _ { j } } ^ { k } , \quad \forall k \in K
$$

从电力供应商角度考虑，用户侧微电网的光伏发电清洁且成本非常小，可忽略不计。当用户实时消纳光伏电时，电力供应商供电成本最小，否则，当光伏电有余电时，电力供应商需要储电，即增加储能成本。所以在光伏发电时刻，电力供应商鼓励用户多使用光伏电，以达到减少用户侧微电网储能成本和化石燃料发电成本目的。假设化石燃料发电成本函数是其实际供电量的二次函数[10]，储能设备储电维护成本是其储电量的一次函数，建立电力供应商在 $k$ 时段的供电成本函数，如下所示：

$$
C \left( L _ { J _ { j } } ^ { k } \right) = a \left( L _ { J _ { 2 } } ^ { k } \right) ^ { 2 } + b L _ { J _ { 2 } } ^ { k } + c + d \left( L _ { J _ { 1 } , \operatorname* { m a x } } ^ { k } - L _ { J _ { 1 } } ^ { k } \right)
$$

其中: ${ } _ { a , b , c , d }$ 均为常数。

对电力供应商来说，通过售电给用户获得收益，假设 $k$ 时段实时电价为 $p ^ { k }$ ，则电力供应商 $k$ 时段获得的福利(净收益)为供电收益减去供电成本，即

$$
W _ { 1 } ^ { k } = L _ { J _ { j } } ^ { k } p ^ { k } - C \left( L _ { J _ { j } } ^ { k } \right) , j = 1 , 2
$$

从居民用户角度，不同的居民用户在同一时段消费相同类型的电能时，用户获得满足的程度不同。根据微观经济学可知，效用函数是用来衡量消费者在既定商品组合中获得满足的程度，故采用效用函数来衡量用户消费一定类型电能时获得的满足程度。参考文献[10,16]，建立居民用户在 $k$ 时段的效用函数如下所示：

$$
B \Big ( x _ { { J } _ { j } , i } ^ { k } , \omega _ { { J } _ { j } , i } ^ { k } \Big ) = \left\{ \begin{array} { l l } { \displaystyle \sum _ { J _ { j } \in J } x _ { J _ { j } , i } ^ { k } \omega _ { J _ { j } , i } ^ { k } - \frac { \alpha } { 2 } \Big ( x _ { J _ { j } , i } ^ { k } \Big ) ^ { 2 } , 0 \leq x _ { J _ { j } , i } ^ { k } \leq \frac { \omega _ { J _ { j } , i } ^ { k } } { \alpha } } \\ { \displaystyle \sum _ { J _ { j } \in J } \frac { \Big ( \omega _ { J _ { j } , i } ^ { k } \Big ) ^ { 2 } } { 2 \alpha } , \ ~ } & { x _ { J _ { j } , i } ^ { k } > \frac { \omega _ { J _ { j } , i } ^ { k } } { \alpha } } \end{array} \right.
$$

其中: $\alpha$ 为给定的参数，取值范围为 $0 \leq \alpha < 1$ ； $\omega _ { J _ { j } , i } ^ { k }$ 表示用户的用电意愿，因为不同时段不同用户消费不同类型电能的用电意愿不同，所以 $\omega _ { J _ { j } , i } ^ { k }$ 是在一定范围内不断变化的，并且两种类型电能的 $\omega _ { J _ { j } , i } ^ { k }$ 的取值范围是不同的，因光伏电具有清洁环保优势，假设用户使用光伏电的用电意愿范围边界值稍大于化石燃料电。为了显示用户用电意愿大小对效用的影响，假设有一位用户使用了光伏所发的电能，设置用电意愿分别为$\omega _ { J _ { 1 } , 1 } ^ { k } = 3 . 5$ 和 $\omega _ { J _ { 1 } , 1 } ^ { k } = 3$ ，参数 $\alpha = 0 . 5$ ，绘制居民用户在两个用电意愿下的效用函数示例图，如图1所示。由图1可以看出，当 $\omega _ { J _ { 1 } , 1 } ^ { k }$ 较大时，同一电量水平下的效用也较大；随着用户用电量增大，效用值也将会达到饱和，不再增加。

对用户来说，希望以较低的电价购入电能，并在使用电能过程中获得较高的满足程度，则单个用户 $k$ 时段获得的福利可表示为用户效用值减去购电费用，即

$$
\begin{array} { r } { W _ { 2 } ^ { k } = B \Big ( x _ { J _ { j } , i } ^ { k } , \omega _ { J _ { j } , i } ^ { k } \Big ) - \sum _ { J _ { j } \in J } x _ { J _ { j } , i } ^ { k } p ^ { k } } \end{array}
$$

综合考虑电力供应商和用户两方福利，以用户总效用减去电力供应商供电成本的最大化建立如下优化模型，并将之称为社会福利最大化模型[19]，即对每个时段 $k \in K$ ，

![](images/11a0a65ad139ca8ae6b51f465260b632f462191f383a141e8e0c2985117b8105.jpg)  
图1光伏用户在两种不同用电意愿下的效用函数 Fig.1Utility function of photovoltaic users under two different power consumption intentions

尽管式(6)是一个多变量、有约束条件的最优化问题，但直接求解并不能确定实时电价。而通过采用拉格朗日对偶法求解该模型，可将对偶的问题分解成几个有可行解子问题，最后解得的拉格朗日乘子刚好是电力供应商需要制定的实时电价[10]，因此关于社会福利最大化实时电价模型的求解目前常采用对偶法[16,19,20]。

采用拉格朗日对偶法求解时，首先引入拉格朗日乘子 $\lambda ^ { k }$ 。将式(6)看做原问题，其拉格朗日函数为

$$
\begin{array} { r l } & { \zeta \left( x _ { J _ { j } , i } ^ { k } , L _ { J _ { j } } ^ { k } , \lambda ^ { k } \right) } \\ & { = \sum _ { i \in N } B \left( x _ { J _ { j } , i } ^ { k } , \omega _ { J _ { j } , i } ^ { k } \right) - C \left( L _ { J _ { j } } ^ { k } \right) - \lambda ^ { k } \sum _ { J _ { j } \in J } \left( \sum _ { i \in N } x _ { J _ { j } , i } ^ { k } - L _ { J _ { j } } ^ { k } \right) } \\ & { = \sum _ { i \in N } \biggl [ B \left( x _ { J _ { j } , i } ^ { k } , \omega _ { J _ { j } , i } ^ { k } \right) - \lambda ^ { k } \sum _ { J _ { j } \in J } x _ { J _ { j } , i } ^ { k } \biggr ] + \biggl [ \lambda ^ { k } \sum _ { J _ { j } \in J } L _ { J _ { j } } ^ { k } - C \left( L _ { J _ { j } } ^ { k } \right) \biggr ] } \end{array}
$$

则式(6)的对偶问题可表示为

$$
\begin{array} { c } { { \displaystyle { \operatorname* { m i n } _ { P _ { i , \mathrm { m i n } } \leq x _ { J _ { 1 } , i } ^ { k } \leq P _ { i , \mathrm { m a x } } ^ { k } , m _ { i } ^ { k } \leq x _ { J _ { 2 } , i } ^ { k } \leq M _ { i } ^ { k } } } } } \\ { { L _ { J _ { 1 } , \mathrm { m i n } } ^ { k } \leq L _ { J _ { 1 } } ^ { k } \leq L _ { J _ { 1 } , \mathrm { m a x } } ^ { k } , L _ { J _ { 2 } , \mathrm { m i n } } ^ { k } \leq L _ { J _ { 2 } } ^ { k } \leq L _ { J _ { 2 } , \mathrm { m a x } } ^ { k } } } \end{array} ~ D ( \lambda ^ { k } )
$$

$$
s . t . \qquad \lambda ^ { k } \geq 0
$$

其中：

$$
D \big ( \lambda ^ { k } \big ) = \operatorname* { m a x } _ { \substack { P _ { i , \mathrm { m i n } } ^ { k } \le x _ { J _ { 1 } , i } ^ { k } \le P _ { i , \mathrm { m a x } } ^ { k } , m _ { i } ^ { k } \le x _ { J _ { 2 } , i } ^ { k } \le M _ { i } ^ { k } } }  \quad \zeta \big ( x _ { J _ { j } , i } ^ { k } , L ^ { k } , \lambda ^ { k } \big )
$$

$$
= \sum _ { i \in N } G { \bigl ( } \lambda ^ { k } { \bigr ) } + H { \bigl ( } \lambda ^ { k } { \bigr ) }
$$

$$
\begin{array} { r } { G \left( \lambda ^ { k } \right) = \underset { { P _ { i , \mathrm { m i n } } ^ { k } \leq x _ { j _ { 1 } , i } ^ { k } \leq P _ { i , \mathrm { m a x } } ^ { k } } } { \operatorname* { m a x } } B \left( x _ { J _ { j } , i } ^ { k } , \omega _ { J _ { j } , i } ^ { k } \right) - \lambda ^ { k } { \sum _ { J _ { j } \in J } x _ { J _ { j } , i } ^ { k } } } \end{array}
$$

$$
H \big ( \lambda ^ { k } \big ) = \operatorname* { m a x } _ { L _ { J _ { 1 } , \operatorname* { m i n } } ^ { k } \leq L _ { J _ { 1 } } ^ { k } \leq L _ { J _ { 1 } , \operatorname* { m a x } } ^ { k } } \lambda ^ { k } \sum _ { J _ { j } \in J } L _ { J _ { j } } ^ { k } - C \big ( L _ { J _ { j } } ^ { k } \big )
$$

用式(8)的对偶问题替代式(6)中的原问题，可以解得对偶问题的结果 $\lambda ^ { k ^ { * } }$ 。前面已提到，此时的 $\lambda ^ { k ^ { * } }$ 刚好是电力供应商需要制定的实时电价 $p ^ { k }$ 。关于 $\lambda ^ { k * }$ 的求解过程将在下一节中介绍。将式(8)表示的求解用户最优用电量和供应商最优供应量的对偶问题分解成式(10)(11)两个子问题求解，这样用户端和电力供应端的福利最大化问题都可以解决。在每一次电价更新后，用户通过式(10)可以求得最优用电总量 $\textstyle \sum _ { J _ { j } \in J } x _ { J _ { j } , i } ^ { k ^ { * } }$ ，它包含光伏电最优用电量 $x _ { J _ { 1 } , i } ^ { k ^ { * } }$ 和化石燃料电最优用电量 $x _ { J _ { 2 } , i } ^ { k ^ { * } }$ ；电力供应商通过式(11)可以求得最优供电总量 $\sum _ { J _ { j } \in J } { L _ { J _ { j } } ^ { k ^ { * } } }$ ，它包含光伏电最优供电量 $L _ { J _ { 1 } } ^ { k ^ { * } }$ 和化石燃料最优供电量 $\begin{array} { r } { L _ { J _ { 2 } } ^ { k ^ { * } } } \end{array}$ 。

# 2 电价选代过程

本文采用梯度投影法求解式(8)中的最优拉格朗日乘子$\lambda ^ { k ^ { * } }$ 。梯度投影法迭代公式如下：

$$
\begin{array} { r l r } {  { \lambda _ { t + 1 } ^ { k } = [ \lambda _ { t } ^ { k } - \gamma \frac { \hat { \partial } D ( \lambda _ { t } ^ { k } ) } { \hat { \partial } \lambda } ] ^ { + } } } \\ & { } & { = [ \lambda _ { t } ^ { k } + \gamma ( \sum _ { i \in N } \sum _ { J _ { j } \in J } x _ { J _ { j } , i } ^ { k } - \sum _ { J _ { j } \in J } L _ { J _ { j } , t } ^ { k } ) ] ^ { + } } \end{array}
$$

其中： $\left[ \varepsilon \right] ^ { + } = \operatorname* { m a x } \left\{ \varepsilon , 0 \right\}$ 表示 $\varepsilon$ 与0相比较大的数。 $t \in T$ ， $T$ 表示$\lambda ^ { k }$ 在 $k$ 时段内更新的时间序列集合； $\gamma$ 表示步长。

# 3 实时定价算法

实时定价是用户和电力供应商互动的过程，当实时电价更新后，用户和电力供应商分别通过式(10)(11)更新电量，使双方各自获得的福利最大。将整个实时定价算法过程分为用户侧实时电价算法和电力供应商侧实时电价算法两部分，具体算法步骤和用户与电力供应商之间的互动如算法1、2和图2所示。

算法1用户侧实时电价算法过程

S0:数据初始化；  
S1:如果 $t \in T$ ：  
S11:接收电力供应商提供的电价 $\lambda ^ { k }$ ：  
S12:通过式(10)更新用户光伏用电量 $x _ { J _ { 1 } , i } ^ { k ^ { * } } ( \lambda ^ { k } )$ 和化石燃料用电量$x _ { J _ { 2 } , i } ^ { k ^ { * } } ( \lambda ^ { k } )$ ：  
S13：向电力供应商发送更新后的光伏用电量、化石燃料用电量等信息；S2:结束。  
算法2电力供应商侧实时电价算法过程  
S0:数据初始化；  
S1:开始循环；  
S2:如果 $t \in T$ ：  
S21:通过式(12)更新电价；  
S22:对用户发布新的电价 $\lambda ^ { k }$ 。  
S3:否则  
S31:根据式(11)更新供电量;  
S32:接收用户用电量信息（光伏用电量 $x _ { J _ { 1 } , i } ^ { k ^ { * } } ( \lambda ^ { k } )$ （204  
和化石燃料用电量 $x _ { J _ { 2 } , i } ^ { k ^ { * } } ( \lambda ^ { k } )$ ）；  
S33:更新所有用户的用电量信息。  
S4:结束;  
S5：直到供需平衡结束循环。

![](images/4fd217cd8e37427a8bc82d43dc1b2da5735a100bfede878523bc91e9b2f549b3.jpg)  
图2用户与电力供应商之间的互动流程图  
Fig.2Flow chart of interaction between users and power suppliers

# 4 数值实验

# 4.1参数设置

在求解该模型的过程中，假设有 $n = 1 0 0$ 个居民用户，通过100个居民用户的用电行为来验证模型的合理性。在参数设置方面，本文参考文献[13,19]，预先设置部分模型中涉及的参数。其中，设置居民用户的一个用电周期为一天，并将一天划分为24个时段，每个时段时长为1小时，即有 $s = 2 4$ 。设置式(2)中参数 $\scriptstyle a = 0 . 0 1$ 、 $b = 0$ 、 $c = 0$ 、 $\scriptstyle d = 0 . 0 2$ 。设置式(4)中参数 $\alpha = 0 . 5$ ，对用电意愿 $\omega _ { J _ { j } , i } ^ { k }$ ，设置居民用户对光伏电和化石燃料电的用电意愿 $\omega _ { J _ { 1 } , i } ^ { k }$ 、 $\omega _ { J _ { 2 } , i } ^ { k }$ 取值范围分别为[1.5,4.5]和[1,4]，即居民用户对光伏电和化石燃料电的用电意愿分别取这两个区间上的随机值，并且每个用电意愿在每个时段优化求解的过程中保持不变。最后，设置式(12)中参数 $\gamma = 0 . 0 1$ 。

另外，将智能电网中只考虑化石燃料供电方式的大电网的社会福利最大化实时定价模型，与本文中的智能电网中考虑了光伏和化石能源互补供电的用户侧微电网的社会福利最大化模型优化结果作比较，以区分化石燃料单一供电方式和化石燃料与光伏互补供电方式的优劣。

# 4.2结果分析

采用matlab2016软件对用户侧微电网的社会福利最大化实时定价模型进行仿真求解。首先，通过实时定价算法求解模型得出用户侧微电网的用户最优用电总量 $\textstyle \sum _ { J _ { j } \in J } x _ { J _ { j } , i } ^ { k ^ { * } }$ 和电力供应商最优供电总量 $\sum _ { J _ { j } \in J } { L _ { J _ { j } } ^ { k ^ { * } } }$ ，如图3所示。

![](images/41aa55fb3c213dfec8216af2caa424665589c63debe3569c297f7fed266ee6cc.jpg)  
图3用户侧微电网最优用电和供电总量

接下来，分别看一下总电量中包含的光伏电和化石燃料电的使用和供给情况分别如图4和5所示。由图4可以看出，光伏最优用电量线、光伏最优供电量线均与光伏电最高电量需求线重合，这是因为电力供应商鼓励用户实时消纳光伏电，以降低储电成本和化石能源发电成本，故当光伏电最优供电量达到最高电量需求时，电力供应商会通过降低实时电价，促进用户实时消纳光伏电，使得用户最优用电量与电力供应商最优供电量平衡，满足电力供应侧最大化的利用光伏电，降低供电成本，同时用户侧以低电价购入电能并提高用电效用的要求。

由图5可以看出,化石燃料最优用电量线与化石燃料最优供电量线重合，均满足在化石燃料最低电量需求和化石燃料最高电量需求之间，并且化石燃料最优供电量和最优用电量波动较小、峰谷电量差也较小，使化石燃料电量需求处于相对平稳的状态。

以上是根据用户侧微电网的社会福利最大化实时定价模型求解的供、用电量情况。为了解互补能源供用电的优势，现将大电网中仅考虑化石燃料供电的社会福利最大化实时定价模型，与本文中包含光伏和化石两种类型能源供电的用户侧微电网的社会福利最大化实时定价模型求解结果作一下比较，如图6和7所示。图6是两者使用化石燃料的供用电量的对比，图7是两者的实时电价（单位：元）的对比。

![](images/04a6feb70ffc85d8db7d76f03b17b034521eefccb35007ecb46e7b7711f35c9d.jpg)  
图4用户侧微电网中光伏电的最优用电和供电总量

![](images/f31821c06e0a0f591dfa75984e4823546f16b6a8a3a5a7fdf3b99465c1946349.jpg)  
Fig.4Optimal total power consumption and supply of photovoltaic power inuser-side microgrid   
图5用户侧微电网中化石燃料电的最优用电和供电总量

![](images/7abfb48bf6150fab01feb8a3899743f0553036c6541743f0543cba8fbd71facf.jpg)  
Fig.3Optimal total power consumption and supply in user-side microgrid   
图6用户侧微电网与大电网中化石燃料的最优供用电量对比

![](images/487917211daf5520d53ffd8fa03b0723461d4e0e6de2dfb332cd88223dbaafe2.jpg)  
Fig.5Optimal total power consumption and supply of fossil fuel power in user-side microgrid   
Fig.6Comparison of optimal power supply and consumption of fossil fuel between user-side microgrid and large power grid   
图7用户侧微电网和大电网的实时电价对比 Fig.7Comparison of real-time electricity price between user-side microgrid and large power grid

由图6可以看出,在最大、最小用电总量相同的情况下，用户侧微电网峰时段的化石燃料最优用电量远低于大电网，表现出更好的削峰效果，说明用户侧微电网互补供电的方式有利于降低仅靠化石燃料供电带来的供电压力，并减少化石燃料供电成本。由图7可以看出,用户侧微电网实时电价普遍低于大电网，尤其是峰时段，在光伏电发电量较充足时，用户侧微电网通过降低电价来促进用户实时消纳光伏电，既满足了用户低电价购入电能同时也降低了电力供应商供电成本：构成了用户端和电能供应端的互惠互利模式。

最后是用户侧微电网和大电网的社会福利对比，如图8所示。由图8可以看出，用户侧微电网的社会福利普遍高于大电网，尤其是在峰时段。这也验证了用户侧微电网的社会福利最大化实时电价模型的合理性和有效性。

![](images/f61d1e812fce050a8f4ce5e978d2251675edd3fdbc9364a61d041f7d5f6ec7b8.jpg)  
图8用户侧微电网和大电网的社会福利对比  
Fig.8Comparison of social welfare between user-side microgrid and large power grid

# 5 结束语

随着智能电网建设的不断扩大以及大数据技术的发展，将来可以在各地建立符合当地能源结构的用户侧微电网，既能保证用户的用电需求，也能减少化石能源的需求、降低供电成本。

本文在智能电网背景下，提出了一个针对用户侧微电网的社会福利最大化实时定价模型，考虑了多能互补的供电方式，即包含光伏和化石燃料两种类型能源供电，并设计了实时定价算法求解模型。将结果与智能电网中仅靠化石能源供电的大电网进行比较，得出以下结论：a）用户侧微电网中光伏和化石燃料互补供电的方式，可以减少化石燃料供电量、降低化石燃料发电成本，并且可以缓解仅靠化石燃料供电的峰时供电压力；b）用户侧微电网的实时电价更低。这是由于在光伏电发电量较充足时，微电网通过降低电价来促进光伏电实时消纳，既满足了用户低电价用电需求，也降低了电力供应商的供电成本，构成了用户端和电能供应端的互惠互利模式；c）用户侧微电网的社会福利值更高，说明了用户侧微电网多能互补供电方式带来的社会福利更大。以上结论充分说明了用户侧微电网多能互补供电方式的优越性，以及社会福利最大化模型的合理性和有效性。

# 参考文献：

[1]刘敦楠，徐尔丰，许小峰．面向园区微网的“源—网一荷—储”一体 化运营模式[J]．电网技术，2018,42(3):681-689.(Liu Dunnan,Xu Erfeng，Xu Xiaofeng.“ Source-Network-Load-Storage ” integrated operation model for microgrid in park [J].Power System Technology, 2018,42 (3):681-689.)

[2]许志荣，杨苹，郑成立，等．用户侧光储型微电网中央控制器研制

[J].电网技术,2017,41(2): 426-433.(Xu Zhirong, Yang Ping,Zheng Chengli,et al. Control device development of user-side PV-ESS microgrid[J].Power System Technology,2017,41(2): 426-433.)   
[3]李鹏，郭晓斌，许爱东，等．用户侧微电网的特征及关键技术[J]. 南方电网技术,2015,9(4):1-6.(Li Peng,Guo Xiaobin, Xu Aidong,et al. Characteristics and key technologies of user-side microgrid [J]. Southerm Power System Technology, 2015,9 (4): 1-6. )   
[4]金颖丰，高岩．智能电网分段实时定价优化策略研究[J].计算机仿 真,2016,33 (4): 171-175.(Jin Yingfeng,Gao Yan. Optimal piecewise real-time pricing strategy for smart grid [J].Computer Simulation,2016, 33 (4): 171-175.)   
[5] 田兵，雷金勇，喻磊，等．用户侧微电网能量优化策略与工程实践 [J]．南方电网技术,2018,12(3):66-73.(Tian Bing,Lei Jinyong,Yu Lei,et al. Energy optimization strategy and engineering practice of user-side microgrid [J]. Southern Power System Technology, 2018,12 (3): 66-73.)   
[6] Tian Bin,Lei Jinyong,Guo Xiaobin,et al.Design of MGCC for user-side microgrid [C]//Proc of International Conference on Power Electronics Systems and Applications.2016:1-6.   
[7] 代业明，高岩，高红伟，等．基于需求响应的智能电网实时电价谈判 模型[J]．中国管理科学,2017,25(3):102-110.(Dai Yeming,Gao Yan, Gao Hongwei, et al. Real-time pricing contract bargaining based on demand response in smart grid [J].China Journal of Management Science,2017,25 (3):102-110.)   
[8]朱红波，高岩，代业明.考虑风险的智能电网实时电价定价策略[J]. 系统仿真学报,2018,30(4):1376-1383.(Zhu Hongbo,Gao Yan,Dai Yeming.Real-time pricing strategy considering the risk of smart grid [J]. Journal of System Simulation,2018,30(4):1376-1383.)   
[9] 申展，胡辉勇，雷金勇，等.分布式电源接入用户及用户侧微电网双 向电能计量问题[J]．南方电网技术,2015,9(4):14-21.(Shen Zhan, Hu Huiyong,Lei Jinyong，et al.Bidirectional metering issues of user-side microgrid and user with distributed generation [J]. Southern Power System Technology,2015,9 (4): 14-21. )   
[10] Samadi P,Mohsenian-Rad A H, Schober R,et al. Optimal real-time pricing algorithm based on utility maximization for smart grid [C]// Proc of IEEE International Conference on Smart Grid Communications. 2010: 415-420.   
[11] Samadi P, Schober R, Wong V W S. Optimal energy consumption scheduling using mechanism design for the future smart grid [Cl//Proc of IEEE International Conference on Smart Grid Communications. 2011: 369-374.   
[12] Samadi P, Mohsenian-Rad H, Wong V W S,et al. Real-time pricing for demand response based on stochastic approximation [J]. IEEE Trans on Smart Grid,2017,5 (2): 789-798.   
[13] Samadi P,Mohsenian-RadH,WongVWS,et al.Utilizing renewable energy resources by adopting DSM techniques and storage facilities [C]/Proc of IEEE International Conference on Communications. 2014: 4221-4226.   
[14] Song Xin, Qu Jiayu. An improved real-time pricing algorithm based on utilitymaximization for smart grid [C]//Intelligent Control and Automation. IEEE,2015: 2509-2513.   
[15] Asadi G, Gitizadeh M, Roosta A. Welfare maximization under real-time pricing in smart grid using PSO algorithm [C]//Electrical Enginering. IEEE,2013: 1-7.   
[16] 刘博，李军祥，高岩．智能电网分类用户实时电价算法研究[J].计 算机应用研究,2017,34(9):2605-2609.(Liu Bo,Li Junxiang,Gao

Yan.Research on real-time pricing algorithm for classified subscribers on smart grid [J].Application Research of Computers,2017,34(9): 2605-2609.)

[17]田兵，喻磊，雷金勇，等．工业型用户侧微电网储能运行方式与微电 网的运营模式[J].南方电网技术,2016,10(8):48-55.(Tian Bing,Yu Lei,Lei Jinyong,et al.Energy storage operation mode and business mode of industrial type user-side microgrid [J]. Southern Power System Technology,2016,10(8): 48-55.)

[18]郑宇，田兵，雷金勇，等．能源互联网环境下用户侧微电网的形态及 优化运行[J]．南方电网技术，2016,10(8):40-47.(Zheng Yu,Tian Bing,Lei Jinyong,et al.Configuration and optimal operation of

user-side microgrids in energy internet environment [J].Southern Power System Technology,2016,10 (8):40-47.)   
[19]高岩．带有边际效用非递减用户的智能电网实时电价定价方法[J]. 工业工程与管理,2018,23(1):10-13.(Gao Yan.Real-time pricing strategy for smart grid with users of non-decreasing marginal benefit [J]. Industrial Engineering and Management,2018,23(1):10-13.)   
[20]胡美璇，周洪，胡文山，等．一种面向微电网多自主体系统的实时电 价算法[J]．电力建设,2016,37(3):8-16.(Hu Meixuan,Zhou Hong, Hu Wenshan,et al.A real-time price algorithm based on multi-agent systems in microgrid [J]. Electric Power Construction,2016,37(3): 8-16)