# 基于用户满意度的智能用电能量调度方法研究

纪姝彦 李冬伟

（合肥工业大学电气工程学院合肥 230009)

![](images/e664136eee3b8a9c80ff8191ebeaf091b602d38b36c4fae6687f6881a53fac2c.jpg)

纪姝彦 女 1990年生，硕士研究生，主要研究方向为智能需求侧响应。

摘要：提出一种家庭能量调度管理优化方法。从用户侧角度出发，利用光蓄互补的发电模型并采用余电上网的出售方式，建立实时电价环境下的智能家居负荷运行、储能模型，综合考虑以减少用户用电成本和兼顾用户舒适性为目标进行优化。在可延迟负荷和可中断负荷的舒适性研究基础上，本文建立了面向用户舒适性的智能用电调度管理目标函数，在相关约束条件下创新性地利用粒子群算法获得优化参数，指导用电侧能量调度管理。在满足价格激励型需求响应的同时，尽可能顾及用户的舒适性，并建立用户满意度模型，综合考虑花费满意度和舒适性满意度。最后，验证了基于用户满意度的智能用电研究的正确性。

关键词：智能用电家庭能量管理用户满意度中图分类号：TM734

![](images/012a97d8212b219d14dac18e966148d3908191a356cf128f6f1d22b54ed2bb74.jpg)

# Research on Intelligent Electricity Energy Scheduling Method Based on User's Satisfaction

Ji Shuyan Li Dongwei (HefeiUniversity of TechnologyHefei 230009 China)

李冬伟男 1990年生，硕士研究生，主要研究方向为智能需求侧响应。

Abstract: A kind of optimization method is applied to household energy scheduling management. From the perspective of the user side, the optical storage complementary power generation model and the surplus electricity online sale way are used,a real-time intelligent household electricity environment load operation and energy storage model are established.It should optimize the goal by considering to reduce the power cost and satisfy the user's comfort. In deferrable load based on the study and comfort of interruptible load,a user-oriented comfort of intelligent power dispatching management objective function is established in the paper, and the particle swarm algorithm is used to optimize parameters under the relevant constraints innovative.It can guide the energy scheduling management in electricity side.This way can satisfy the user's comfortableness,establish user satisfaction model and consider cost satisfaction and comfort degree satisfaction in response to meet the demand of price incentive model of at the same time.Finally, the correctness of the smart electricity research is verified based on customer satisfaction in the paper.

Keywords: Smart power utilization, home energy management, user's satisfaction

# 1 引言

随着经济社会的发展，电力需求量越来越大，能源危机的问题日益引起重视。能源日益短缺和环境污染，都会给人类社会的发展带来重大挑战。因此新能源发电所起到的作用愈发重要，但新能源具有随机性及波动性的特点，传统的电力系统结构没有办法满足新能源的大量接入。其次，负荷快速增长及其环境污染等原因，需要大力发展智能电网。智能用电技术的发展，已经成为电网发展的新方向。智能用电利用通信技术，信息得以在电网和用户间传递。同传统电网能量的单一流动方向相比，智能电网的能量流动是双向的。用户可以更加合理地用电，并提高用电效率。

随着智能电网的大规模发展，智能家居作为能源使用的末端单元也纳入到智能电网的体系中，同传统方式相比，居民更加积极主动地参与能量管理。从电力用户的角度来看，用户积极主动地参与电网运行，响应电价调节模式，调整家庭负荷的运行时间，将负荷从峰时段转移到谷时段运行，以获得自身利益最大化。但这种利益最大化获得的前提条件是通过改变负荷的运行情况。鉴于用户本身的收入、家用负荷运行情况的改变引起居民适应性能的差别，不同用户对这种家用负荷运行情况的改变所持态度也大不相同。

家庭能量管理（HomeEnergyManagementSystem，HEMS）是目前广泛使用的一种技术手段[1]。HEMS 根据分布式电源的输出功率及实时电价，改变负荷运行情况，调整各个家用负荷及储能设备在不同时间段的开关状态，从而影响各个时间段的家用负荷用电功率，进而降低了用户全天的用电费用。但这种用电费用的减少，实际上影响了用户的舒适性。文献[2]提出了基于用户满意度的决策模型；文献[3]根据家电实时状态的舒适性和动态优先级进行负荷控制；文献[4]考虑可延迟负荷的允许时间的变化，进而提出用电成本及舒适性的综合调度，但这里将空调、热水器等温控性负荷进行了简化，仅考虑运行时间的改变；文献[5]综合考虑了可延迟负荷和可中断负荷所带来的不舒适性，可中断负荷仅考虑切除比例范围，未考虑温度变化；文献[6]提出在光照充足的条件下，空调系统尽可能多地在光伏电源出力充足的情况下使用光伏出力来降低温度以减少花费，但也需要考虑空调运行的温度范围在人体可接受的范围内。基于上述文献仅考虑单一类型负荷研究的不足，本文提出了综合考虑可延迟负荷和可中断负荷舒适性的智能家电能量管理，更合理地考虑用户舒适性的要求。文献[3-4]所提出的用户舒适性均按照偏离设定值呈线性变化，但对所有家用负荷执行一个评价指标；文献[5]则根据花费的降低等效表示舒适性的改变，并未准确表现时间及运行温度改变的情形；文献[7]通过问卷调查受访者对智能家电运行舒适性的感知，并建立模型来量化这种感知。由上述文献可以看出，随着智能家居的实施，舒适性也越发受到重视。从生物学的角度出发，人类主动积极参与环境变化的特点，舒适性实际是环境和心理状态的综合反映[8-9]。根据不同家用负荷运行状况的改变对居民舒适性造成的不同影响，本文建立新的舒适性模型，并给出了舒适性的评价函数。所提模型以综合考虑花费满意度和舒适性满意度为目标进行优化，最后验证了基于用户满意度的正确性。

# 2智能家居模型

本文在考虑价格激励型需求响应和居民舒适性的基础上提出了智能家居模型。电力公司通过网络的方式，提前把第二天的电价发送给居民，HEMS根据电价确定第二天家用负荷的运行情况，进而优化各家用负荷的调度情况，以实现优化目的[10-11]。

HEMS通过有线或者无线的形式，将家用负荷的用电信息传递给电力部门。家用负荷的所有设备都与HEMS进行连接，用户则需要提前对各个家用电器的运行时间段进行设置，电力公司会根据居民的用电情况，更加合理地安排电力生产情况。

# 2.1光伏电源模型

光伏发电输出功率为[12]

$$
P ( t ) = P _ { \mathrm { s t c } } \frac { G ( t ) } { G _ { \mathrm { s t c } } } \Big [ 1 + k ( T ( t ) - T _ { \mathrm { s t c } } ) \Big ]
$$

式中， $P _ { \mathrm { s t c } }$ 为标准测试条件下的最大测试功率。标准测试条件为：光照强度 $G _ { \mathrm { s t c } } = 1 ~ 0 0 0 \mathrm { W / m } ^ { 2 }$ ；环境温度$T _ { \mathrm { s t c } } = 2 5 \mathrm { ~ \textdegree ~ }$ ； $k$ 为温度系数，取 $k = - 0 . 0 0 5 / \mathrm { ~ \textdegree ~ }$ ； $G ( t )$ 为 $t$ 时刻的光照强度； $\mathit { T } ( t )$ 为 $\mathbf { \chi } _ { t }$ 时刻的室外温度。

# 2.2储能系统模型

储能系统增加了居民用电的灵活性，居民可以将分布式电源产生的多余电能储存起来。合理地加入储能在家庭能量管理中起到十分重要的作用。储能模型主要用来表示充放电中荷电状态的变化[13]。

储能充电为

$$
S _ { \mathrm { s o c } } ( t + 1 ) = \left\{ \begin{array} { l l } { S _ { \mathrm { s o c } } ( t ) + \frac { \eta _ { \mathrm { c h } } P _ { \mathrm { c h } } ( t ) \Delta t } { C _ { \mathrm { b a t } } } } \\ { \qquad \quad \displaystyle { S _ { \mathrm { s o c } } ( t ) - \frac { P _ { \mathrm { d i s } } ( t ) \Delta t } { \eta _ { \mathrm { d i s } } C _ { \mathrm { b a t } } } } } \end{array} \right.
$$

式中， $S _ { \mathrm { S O C } }$ 表示储能的荷电状态； $C _ { \mathrm { b a t } }$ 表示储能容量； $P _ { \mathrm { c h } } ( t )$ 表示充电功率； $\eta _ { \mathrm { c h } }$ 表示充电效率； $P _ { \mathrm { d i s } } ( t )$ 表示放电功率； $\eta _ { \mathrm { d i s } }$ 表示放电效率； $\Delta t$ 为 $1 5 \mathrm { m i n }$ 。

# 2.3负荷模型

智能家居的负荷模型可分为三类： $\textcircled{1}$ 刚性负荷：基本照明、电视机、计算机等，一般同用户的生活作息联系紧密，不可更改； $\textcircled{2}$ 可延迟负荷：电饭锅、洗碗机、洗衣机等，一经运行不能停止； $\textcircled{3}$ 可中断负荷：空调、热水器等温控器负荷，随着温度范围确定开关状态。用户在保证正常生活的情况下，通过HEMS重新调整家用负荷的使用情况，以达到费用降低的目标。

(1)可延迟负荷。工作时间连续，在工作时间内不能停止，其数学模型为[14]

$$
\begin{array} { r l } & { \{ \alpha _ { \mathrm { a } } \leqslant t _ { \mathrm { a } } ^ { \mathrm { s t a r t } } \leqslant h _ { \mathrm { a } } \leqslant t _ { \mathrm { a } } ^ { \mathrm { e n d } } \leqslant \beta _ { \mathrm { a } }  } \\ & {  \{ t _ { \mathrm { a } } ^ { \mathrm { e n d } } = t _ { \mathrm { a } } ^ { \mathrm { s t a r t } } + d _ { \mathrm { a } } - 1   } \\ & {   | x _ { \mathrm { a } } ^ { h } = 1 , h _ { \mathrm { a } } \in [ t _ { \mathrm { a } } ^ { \mathrm { s t a r t } } , t _ { \mathrm { a } } ^ { \mathrm { e n d } } ]   } \\ & {    x _ { \mathrm { a } } ^ { h } = 0 , h _ { \mathrm { a } } \notin [ t _ { \mathrm { a } } ^ { \mathrm { s t a r t } } , t _ { \mathrm { a } } ^ { \mathrm { e n d } } ]   } \end{array}
$$

式中， $[ \alpha _ { \mathrm { a } } , \beta _ { \mathrm { a } } ]$ 是负荷允许工作的时间段； $t _ { \mathrm { a } } ^ { \mathrm { s t a r t } }$ 是负荷运行的开始时刻； $t _ { \mathrm { a } } ^ { \mathrm { e n d } }$ 是负荷运行的结束时刻； $h _ { \mathrm { a } }$ 是负荷可能运行的时间点； $d _ { \mathrm { a } }$ 是负荷运行时长； $x _ { \mathrm { a } } ^ { h }$ 是负荷的状态， ${ x _ { \mathrm { a } } ^ { h } } = 1$ 表示负荷运行， ${ x _ { \mathrm { a } } ^ { h } } = 0$ 表示负荷停止。

(2）可中断负荷。本文主要考虑温控负荷，如空调，热水器。

1）空调。本文空调处于制冷模式下运行，空调的开关状态由室内温度决定。若室内温度高于最高设定温度，则空调启动；若室内温度低于最低设定温度，则空调关闭；若室内温度在设定温度范围之间，则空调保持之前的运行状态[15]，即

$$
U _ { \mathrm { { A C } , \it { t } } } = \left\{ \begin{array} { c c } { 1 } & { T _ { \mathrm { { A C } , \it { t } } } > T _ { \mathrm { { A C } , \mathrm { m a x } } } } \\ { 0 } & { T _ { \mathrm { { A C } , \it { t } } } < T _ { \mathrm { { A C } , \mathrm { m i n } } } } \\ { U _ { \mathrm { { A C } , \it { t } - 1 } } } & { T _ { \mathrm { { A C } , \mathrm { m i n } } } \leqslant T _ { \mathrm { { A C } , \it { t } } } \leqslant T _ { \mathrm { { A C } , \mathrm { m a x } } } } \end{array} \right.
$$

式中， $T _ { \mathrm { A C } , t }$ 为 $t$ 时刻的室内温度值； $T _ { \mathrm { A C , m a x } }$ 为室内

设定温度最高值； $T _ { \mathrm { A C , m i n } }$ 为室内设定温度最低值；  
$U _ { \mathrm { A C } , t }$ 为 $t$ 时刻的空调运行状态。

2）热水器。热水器的开关状态由水温决定。若水温高于最高设定温度，则热水器停止加热；若水温低于最低设定温度，则热水器开始加热；若水温在设定温度范围之间，则热水器保持之前的运行状态[16]，即

$$
U _ { \mathrm { E W H } , t } = \left\{ \begin{array} { c c } { 0 } & { T _ { \mathrm { E W H } , t } > T _ { \mathrm { E W H } , \mathrm { m a x } } } \\ { 1 } & { T _ { \mathrm { E W H } , t } < T _ { \mathrm { E W H } , \mathrm { m i n } } } \\ { U _ { \mathrm { E W H } , t - 1 } } & { T _ { \mathrm { E W H } , \mathrm { m i n } } \leqslant T _ { \mathrm { E W H } , t } \leqslant T _ { \mathrm { E W H } , \mathrm { m a x } } } \end{array} \right.
$$

式中， $T _ { \mathrm { E W H } , t }$ 为 $t$ 时刻的水温值； $T _ { \mathrm { E W H , m a x } }$ 为设定水温最高值； $T _ { \mathrm { E W H , m i n } }$ 为设定水温最低值； $U _ { \mathrm { E W H } , t }$ 为 $t$ 时刻的热水器工作状态。

温控型负荷每分钟检测一次温度，根据温控性负荷的运行情况，可求出 $1 5 \mathrm { m i n }$ 的平均运行功率。

# 3 居民舒适性模型

本文将舒适性分为等待时间舒适性和温度舒适性。等待时间舒适性要求负荷尽可能在允许运行的时间段内靠前运行。负荷如果能在最开始时刻运行，舒适性越高，反之如果延迟负荷的运行时间越长，则舒适性降低；温度舒适性要求温度越靠近设定温度，舒适性越高，反之，越低。舒适性在 $0 \sim 1$ 范围内变化。

# 3.1可延迟负荷舒适性评价指标

本文采用可延迟负荷在时间上向后推移而带来的等待时间增加，等价描述用户舒适性的下降，等待时间越长，说明用户的舒适性越差。即

$$
l = \frac { t _ { \mathrm { s t a r t } } - \alpha _ { \mathrm { a } } } { \beta _ { \mathrm { a } } - \alpha _ { \mathrm { a } } } \quad t \in [ \alpha _ { \mathrm { a } } , \beta _ { \mathrm { a } } ]
$$

式中， $l$ 为偏离设定值百分比； $t _ { \mathrm { s t a r t } }$ 为可延迟负荷实际开始运行的时间； $\alpha _ { \mathrm { a } }$ 为设备允许运行的开始时刻； $\beta _ { \mathrm { a } }$ 为设备允许运行的结束时刻。

文献[17]调查报告提出了三种运行模式研究柔性负荷： $\textcircled{1}$ 家用负荷在某个时间点最迟完成工作；$\textcircled{2}$ 家用负荷在某个时间段更适合运行； $\textcircled{3}$ 可中断负荷因发生中断操作而造成的运行时间延长。不同类型负荷采取不同的运行方式，可延迟负荷分为两种模式运行。根据国外调查报告可以看出舒适性愈发引起关注。因此，本文按照设备运行时间改变对居民影响程度的重要性建立舒适度函数。

若设备运行情况的改变对居民生活影响较大，则较小的偏离设定值百分比会较大地降低用户的舒适性。负荷模型如电饭锅，在饭点时间段的推迟造成居民舒适性的剧烈降低，则舒适性函数为

$$
u = 1 - \log _ { b } [ l ( b - 1 ) + 1 ]
$$

其中， $b = 5$ 。

若设备运行情况的改变对居民生活影响不是很大，同居民生活的没那么密切相关，则舒适性函数随运行时间的推迟呈线性变化，则舒适性函数为

$$
u = 1 - l
$$

# 3.2可中断负荷舒适性评价指标

本文主要考虑的是温控型负荷，如空调，热水器。空调负荷的运行功率与设定温控性负荷温度范围的上下界限、光照强度和室外温度有关。如图1所示。

![](images/61585b40b8c23f044d9f697b7f9a55cccbdaed1610305ef3252fdf16b03b4fa7.jpg)  
图1夏季空调开关及室内温度变化曲线 Fig.1Curve of room temperature and switching statues of air conditioner in summer

本文通过调整温控性负荷的上下界限来调整温控性负荷功率，假设在变化过程中，温控性负荷上下界限偏离设定值百分比相同，并且认为上下界限越靠近设定的温度，舒适性越高，即

$$
l = \frac { T _ { \mathrm { m a x } } - T _ { \mathrm { m a x , s e t } } } { \Delta T } = \frac { T _ { \mathrm { m i n , s e t } } - T _ { \mathrm { m i n } } } { \Delta T }
$$

式中， $l$ 为偏离设定值百分比； $T _ { \mathrm { m a x , s e t } }$ 为舒适性最佳时温度的上限； $T _ { \mathrm { m a x } }$ 为设定温度范围的上边界；$T _ { \mathrm { m i n , s e t } }$ 为舒适性最佳时温度的下边界； $T _ { \mathrm { m i n } }$ 为设定温度范围的下限； $\Delta T$ 为空调温度上下界限的变化范围。

由式（9）可得此时温控性负荷的运行上下界限

温度为

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { T _ { \mathrm { m a x } } = T _ { \mathrm { m a x , s e t } } + l \Delta T } \\ { T _ { \mathrm { m i n } } = T _ { \mathrm { m i n , s e t } } - l \Delta T } \end{array} \right. } \end{array}
$$

人体的适应性能由生理适应和心理适应组成。在芬兰的调查报告中显示，室内温度在越接近人体舒适的情况下，人体对温度变化的灵敏度比其他情况下要低[17]。鉴于人体对温度变化感觉的灵敏度，偏离温度较小，温度感受反映不是很灵敏。在本文温度的变化范围内，偏离设定百分比越大，人体舒适性降低越快，由PMV-PPD方程曲线可以得出人体舒适性和偏离设定值百分比呈幂函数变化[18]，偏离设定值越多，用户的舒适性降低越快。同时，从用户的心理角度出发，对于大功率设备，偏离设定百分比在较小的范围内，用户花费减少，尽管此时出现了小幅度的设定值偏离百分比，用户舒适性还是处于较高水平。水温舒适性近似按照空气温度舒适性建模，则温控性负荷舒适性评价指标为

$$
u = 1 - \frac { e ^ { l } - 1 } { e - 1 }
$$

因此，整个家居系统的舒适性总和为

$$
S _ { \mathrm { c o m } } = \sum _ { i = 1 } ^ { m } u _ { i }
$$

式中， $m$ 为可中断负荷设备与可延迟负荷设备的总数。

# 4智能用电的管理模型

# 4.1优化目标

（1）基于居民花费的优化模型。HEMS 通过预测可再生能源的输出功率，收集可延迟负荷运行时间和可中断负荷运行温度范围以及实时电价等信息，合理调配负荷的运行情况和储能的充放电功率，尽可能多地使用分布式电源的输出功率，减少居民的花费[19-20]。目标函数为

$$
c o s t = \operatorname* { m i n } \sum _ { t } ( P _ { t } ^ { \mathrm { g r i d } } \lambda _ { t } ^ { \mathrm { b u y } } - P _ { t } ^ { \mathrm { P V , s o l d } } \lambda _ { t } ^ { \mathrm { s e l l } } ) \Delta t
$$

式中， $P _ { t } ^ { \mathrm { g r i d } }$ 表示从电网购电； $\lambda _ { t } ^ { \mathrm { \ b u y } }$ 表示实时电价；  
$P _ { t } ^ { \mathrm { { \tiny ~ P V , s o l d } } }$ 表示光伏馈电； $\lambda _ { t } ^ { \mathrm { s e l l } }$ 表示光伏馈电价格； $\Delta t$   
为 $1 5 \mathrm { m i n }$ 。

(2）基于满意度的智能用电模型。此外，考虑到居民侧期望改变生活方式所带来的花费减少的优势，同时兼顾自身舒适性的要求，目标函数为

$$
\mathrm { o b j } = \operatorname* { m i n } \sum _ { t } ( P _ { t } ^ { \mathrm { g r i d } } \lambda _ { t } ^ { \mathrm { b u y } } - P _ { t } ^ { \mathrm { P V , s o l d } } \lambda _ { t } ^ { \mathrm { s e l l } } ) \Delta t - \sigma S _ { \mathrm { c o m } }
$$

式中， $\sigma$ 为居民舒适性的负荷权重，可根据居民的个体需要灵活变化。

# 4.2约束条件

（1）电能平衡约束条件为

$$
\sum _ { i = 1 } ^ { m } P _ { i } \left( t \right) = P _ { \mathrm { { p v } } } \left( t \right) + P _ { \mathrm { { B } } } \left( t \right) + P _ { \mathrm { { G } } } \left( t \right)
$$

式中， $P _ { \mathrm { P V } } ( t )$ 表示光伏发电有功功率； $P _ { \mathrm { B } } ( t )$ 表示储能有功功率； $P _ { \mathrm { G } } ( t )$ 表示市电功率。且

$$
\left\{ \begin{array} { l l } { P _ { t } ^ { \mathrm { g r i d } } = \Big | P _ { \mathrm { G } } ( t ) \Big | , } & { P _ { \mathrm { G } } ( t ) > 0 } \\ { \qquad \Big | P _ { t } ^ { \mathrm { P V , s o l d } } = \Big | P _ { \mathrm { G } } ( t ) \Big | , } & { P _ { \mathrm { G } } ( t ) < 0 } \end{array} \right.
$$

(2）储能荷电状态约束条件为

$$
\begin{array} { r } { \left\{ S _ { \mathrm { s o c , m i n } } \leqslant S _ { \mathrm { s o c } } \left( t \right) \leqslant S _ { \mathrm { s o c , m a x } } \right. } \\ { \left\{ \left. P _ { \mathrm { B } } ( t ) \right| \leqslant P _ { \mathrm { d i s m a x } } , \quad P _ { \mathrm { B } } ( t ) > 0 \right. } \\ { \left\| P _ { \mathrm { B } } ( t ) \right| \leqslant P _ { \mathrm { c h m a x } } , \quad P _ { \mathrm { B } } ( t ) < 0 } \end{array}
$$

式中， $P _ { \mathrm { B } } ( t ) > 0$ 表示储能放电； $P _ { \mathrm { B } } ( t ) < 0$ 表示储能充电； $S _ { \mathrm { { S o C , m a x } } }$ 和 $S _ { \mathrm { { S O C } , \mathrm { { m i n } } } }$ 分别为剩余容量的上下界限； $P _ { \mathrm { d i s m a x } }$ 为最大放电功率。

# 4.3优化算法

本文采用粒子群算法进行求解，通过优化方法，指导粒子群的运动。这里优化的是家用负荷的设定值偏离百分比，通过设定值偏离百分比可以确定可延迟负荷的开始运行时间、温控负荷的温度上下界限以及舒适性函数。首先随机化一群初始粒子，并根据第二天光照强度及温度，预测出第二天的光伏发电功率，HEMS根据以上信息，并结合实时电价、居民舒适性问题，合理安排储能的充放电及家居负荷的运行状况。其中， $X _ { i }$ 是粒子的位置； $V _ { i }$ 是粒子的速度，位置和速度更新计算式为

$$
\left\{ \begin{array} { l } { { V _ { i } ( k ) = \omega V _ { i } ( k - 1 ) + c _ { 1 } r a n d _ { 1 } \Big [ p _ { i } - X _ { i } ( k - 1 ) \Big ] + } } \\ { { \qquad \quad } } \\ { { c _ { 2 } r a n d _ { 2 } \Big [ p _ { g } - X _ { i } ( k - 1 ) \Big ] } } \\ { { \qquad \quad } } \\ { { X _ { i } ( k ) = X _ { i } ( k - 1 ) + V _ { i } ( k ) } } \end{array} \right.
$$

式中， $\omega$ 是加权系数，取 $( 0 , 1 )$ 之间的随机数； $c _ { 1 }$   
和 $c _ { 2 }$ 为学习因子。

求解流程图如图2所示。

![](images/741cba4fcf2c2b151eaa9747a05d3e336a8eb44eb95fffe107a7d2aeb906fee1.jpg)  
图2粒子群算法流程图  
Fig.2Flow chart of the PSO algotithm

# 5 案例分析

# 5.1调度基本信息

本文的调度周期为一天，即 $2 4 \mathrm { h }$ ，结合光伏发电周期和负荷调控，仿真步长为 $1 5 \mathrm { m i n }$ 。本文的铅酸蓄电池容量为 $2 0 0 \mathrm { A h }$ ，额定电压为 $1 2 \mathrm { V }$ 。蓄电池的充电效率为 $92 \%$ ，放电效率 $\eta _ { \mathrm { d i s } } = 9 3 \%$ 。智能家居中可延迟负荷包括洗干一体机、电饭锅、吸尘器、空调和热水器。照明灯和笔记本计算机为刚性负荷，不参加调度。具体负荷参数见表1。光伏发电功率、室外温度数据如图3所示[21]，实时电价如图4所示[22]，余量上网电价为0.34元 $/ \mathrm { k W } \cdot \mathrm { h }$ 。空调 $T _ { \mathrm { m a x , s e t } } = 2 7 ^ { \circ } \mathrm { C }$ ，$T _ { \mathrm { m i n , s e t } } = 2 5 \mathrm { ~ \textdegree ~ }$ ， $\Delta T = 1 \ \mathrm { ~ \textbar { ~ C ~ } ~ }$ ；热水器 $T _ { \mathrm { m a x , s e t } } { = } 5 7 \mathrm { ~ \textdegree ~ }$ ，$T _ { \mathrm { m i n , s e t } } { = } 5 3 ^ { \circ } \mathrm { C }$ ， $\Delta t = 3 ^ { \circ } \mathrm { C }$ 。

# 5.2优化结果

以用户花费最少为目标进行优化，通过粒子群算法优化得到结果见表2。同时和初始运行场景的负荷运行情况进行对比。

# 表1家用电器运行情况

Tab.1Operation of household appliances   

<html><body><table><tr><td>负荷名称</td><td>功率/kW</td><td>允许工作时间段</td><td>工作时间 /h</td></tr><tr><td>洗干一体机</td><td>2</td><td>8：00～18:00</td><td>2</td></tr><tr><td>电饭锅</td><td>1.2</td><td>10：00～13：00</td><td>0.75</td></tr><tr><td>吸尘器</td><td>1.2</td><td>9:00～18:00</td><td>0.5</td></tr><tr><td>空调</td><td>2.2</td><td>全天</td><td>1</td></tr><tr><td>热水器</td><td>3/1.5</td><td>19：15～23：00</td><td>1</td></tr><tr><td>照明灯</td><td>0.12</td><td>18:00～24：00</td><td>6</td></tr><tr><td>笔记本</td><td>0.1</td><td>18：00～24：00</td><td>6</td></tr></table></body></html>

![](images/3135a870dd3330f3bca5df0ea46b043083ceda5d6e806c5d09067fa3e10a3b11.jpg)  
图3光伏出力及温度曲线图

![](images/40b965fd2102caf821451c94eeb62802f85961fdde427fdd2e9b785f7075d577.jpg)  
Fig.3Curve of the photovoltaic output and temperature   
图4实时电价阶梯图Fig.4Curve of real-time price

由表2负荷运行情况可知，可延迟负荷的运行时间和温控性负荷的运行温度上下界限都发生了改变。新的调度执行后，可延迟负荷移动到光伏出力较高或从电费较高移动到电费较低时间段运行。图5和图6分别表示调度前和调度后的负荷运行状况，更加直观地体现负荷的运行情况。

![](images/56928a8106825a8a8cd70a270cd4fa06a30a92a44dde9479b62f930e0092ba99.jpg)  
图5调度前家用电器运行图

![](images/9aa8e67cf96bd1abdc548a06ac373f19c1aaaed156075e656503b7dfc035a594.jpg)  
Fig.5Curve of the operation about household appliances   
图6调度后家用电器运行图  
Fig.6Curve of the operation about household appliances after scheduling

# 表2家用电器运行对比表

Tab.2Comparison table about operation of household appliances   

<html><body><table><tr><td>负荷名称</td><td>调度前</td><td>调度后</td></tr><tr><td>洗干一体机</td><td>8：00～10:00</td><td>12：00～14：00</td></tr><tr><td>电饭锅</td><td>10：00～10：45</td><td>10：15~11：00</td></tr><tr><td>吸尘器</td><td>9：00～9:30</td><td>14：00～14：30</td></tr><tr><td>空调</td><td>25~27℃</td><td>24.22~ 27.78℃</td></tr><tr><td>热水器</td><td>53~57℃</td><td>51.35~ 58.65℃</td></tr></table></body></html>

用户花费由调度前的6.74元，降低为优化后的5.57元，但此时可延迟负荷和温控性负荷的舒适性也降低，特别是空调的舒适性，降为0.3，而夏天用户本身对空调的需求还是挺高的。

# 5.3考虑用户舒适性的调度结果

由式（14）可知，调节居民舒适性的负荷权重，可以使用考虑居民舒适性的家庭能量管理方法。本文从以下三个场景进行分析： $\textcircled{1}$ 场景1：不使用调度； $\textcircled{2}$ 场景2：基于居民花费的优化模型； $\textcircled{3}$ 场景

3：基于满意度的智能用电模型，居民舒适性的权重系数为1。三种场景的仿真结果见表3。此时，场景3的调度情况见表4。

# 表3多场景分析

Tab.3Analysis of multi scenario   
表4场景3运行情况  

<html><body><table><tr><td>场景</td><td>舒适性</td><td>用户花费/元</td></tr><tr><td>场景1</td><td>5</td><td>6.74</td></tr><tr><td>场景2</td><td>2.58</td><td>5.57</td></tr><tr><td>场景3</td><td>4.47</td><td>6.11</td></tr></table></body></html>

Tab.4The operation of scenario 3   

<html><body><table><tr><td>负荷名称</td><td>运行情况</td></tr><tr><td>洗干一体机</td><td>11：15～13：15</td></tr><tr><td>电饭锅</td><td>10：15～11：00</td></tr><tr><td>吸尘器</td><td>9:00～9:30</td></tr><tr><td>空调</td><td>24.98~ 27.02℃</td></tr><tr><td>热水器</td><td>52.59~ 57.41℃</td></tr><tr><td>照明灯</td><td>18：00～24：00</td></tr><tr><td>笔记本</td><td>18：00～24:00</td></tr></table></body></html>

由表3所示，在场景1情况下，不使用调度，用户的花费虽然最高，但此时用户的舒适性也是最高的。在场景2情况下，可延迟负荷转移到电费较低或光伏出力较多的时间段，温控性负荷的温度运行范围增大，虽然用户花费最低，但此时用户的舒适性影响较大，舒适性为2.58。在场景3情况下，考虑用户花费减少的同时，兼顾用户舒适性的要求。由表3可知，此时可延迟负荷和温控性负荷舒适性都较高，总共为4.47。

# 6 结束语

本文针对家用负荷的运行特点，建立家用负荷舒适性函数，HEMS能够很好地完成家用负荷的调度。算例表明家庭能量管理系统将家用负荷连接在一起，进行统一管理。合理安排所有家用负荷的运行，使用户花费较少的同时，又能保证用户的舒适性。本文最后验证了所提模型的正确性。实际上。用户还可以根据自身的需求，灵活地调整居民舒适性的负荷权重大小，以达到用户花费和舒适性的一个动态平衡。

用户对于电器的用电需求，存在较强的随机性。若用户在用电当天的实际用电行为，与提前一天的预设用电计划出现不一致，用户可以通过手机等其

他智能用电交互终端进行实时调整，改变家用负荷运行状态，使家用负荷按照当天的实际用电行为运行。HEMS根据智能用电终端以更改用电计划的时刻为起点，按照实际用电行为对前一天的用电计划进行更改，重新进行优化，各家用负荷按照新的优化结果调度。这些终端设备可以通过软件，人机交互界面形式[23-25]参与家庭能量管理，此实时调整需要通信及计算机技术的支持。应用软件与互动设备的研究，是未来研究的热点。

# 参考文献

[1] Amir Hamed Mohsenian Rad,Alberto Leon Garcia. Optimal residential load control with price prediction in real-time electricity pricing environments[J]. IEEE Trans.on Smart Grid,2010,1(2): 120-133.   
[2] 丁伟，袁家海，胡兆光．基于用户价格响应和满 意度的峰谷分时电价决策模型[J]．电力系统自动 化，2005，29(20)：14-18. Ding Wei, Yuan Jiahai, Hu Zhaoguang. Time-of-use price decision model considering users reaction and satisfaction index[J].Automation of Electric Power Syetems,2005,29(20):14-18.   
[3] 汤奕，鲁针针，宁佳，等．基于电力需求响应的智 能家电管理控制方案[J]．电力系统自动化，2014, 38(9): 93-99. Tang Yi,Lu Zhenzhen,Ning Jia,et al. Management and control scheme for intelligent home appliances based on electricity demand response[J]. Automation of Electric Power Syetems,2014,38(9): 93-99.   
[4] Taiju Mikoshi,Kouki Soeda,Koudai Takahashi, et al.Improvement of consumer satisfaction level by energy storage system in smart houses[J]. The 20th Asia-Pacific Conference on Communication (APCC2014), 2014: 260-265.   
[5] 张彦，张涛，刘亚杰，等．基于模型预测控制的 家庭能源局域网最优能量管理研究[J]．中国电机 工程学报，2015，35(14)：3656-3666. Zhang Yan, Zhang Tao,Liu Yajie,et al. Optimal energy management of a residential local energy network based on model predictive control[J]. Proceedings of the CSEE,2015,35(14): 3656-3666.   
[6] Ana K Cabrera,Hasan Ul Banna,Cosmin KochCiobotarus.Optimization of an air conditioning unit according to renewable energy availability and user's comfort[J].2014 5th IEEE PES Innovative Smart Grid Technologies Europe (ISGT Europe), Istanbul, 2014: 1-7.   
[7] Jeroen Stragier, Laurence Hauttekeete, Lieven De Marez. Introducing smart grids in residential contexts: consumers' perception of smart household appliances[J]. 2010 IEEE Conference on Innovative Technologies for an Efficient and Reliable Electricity Supply (CITRES), 2010: 135-142.   
[8] 冯家亮．某商场热舒适性研究及空调末端节能控 制优化[D]．广州：华南理工大学，2014.   
[9] 蔡强新．既有居住区室外环境热舒适性研究[D]. 杭州：浙江大学，2010.   
[10] AH Mohsenian Rad,A Leon Garcia. Optimal residential load control with price prediction in realtime electricity pricing environments[J]. IEEE Trans. on Smart Grid,2010,1(2): 120-133.   
[11]张延宇，曾鹏，臧传治．智能电网环境下家庭能 源管理系统优化调度算法[J]．电力系统保护与控 制，2016，44(2):18-26. Zhang Yanyu,Zeng Peng, Zang Chuanzhi. A scheduling algorithm for home energy management system in smart grid[J].Power System Protection and Comtrol, 2016, 44(2): 18-26.   
[12]郭佳欢．微网经济运行优化的研究[D]．北京：华 北电力大学，2010.   
[13]王守相，孙智卿，刘喆．面向智能用电的家庭 能量协同调度策略[J]．电力系统自动化，2015, 39(17): 108-113. Wang Shouxiang,Sun Zhiqing,Liu Zhe.Coscheduling strategy of home energy for smart power utilization[J]. Automation of Electric Power Syetems,2015,39(17): 108-113.   
[14]阮冰洁．计及实时电价的家居混合供电系统能量 优化调度方法[D]．杭州：浙江大学，2015.   
[15]Ning Lu.An evaluation of the HVAC load potential for providing load balancing service[J]. IEEE Trans. on Smart Grid,2012,3(3): 1263-1270.   
[16]魏懿．基于需求响应的智能家庭能量管理研究[D]. 秦皇岛：燕山大学，2015.   
[17]Salla Annala, Satu Viljainen, Jussi Tuunanen. Demand response from residential customers' perspective[C]. 2012 9th International Conference on the European Energy Market, 2012: 1-7.   
[18]Fanger P O. Thermal comfort[M]. Copenhagen: Danish Technical Press,1970.   
[19]邢龙，张沛超，方陈，等．基于广义需求侧资 源的微网运行优化[J]．电力系统自动化，2013, 37(12): 127-133. Xing Long, Zhang Peichao, Fang Chen,et al. Optimal operation for microgrid using generalized demand side resources[J]. Automation of Electric Power Syetems,2013,37(12): 127-133.   
[20]周磊，李扬．分时电价环境下基于家居能量管理 系统的家居负荷建模与优化运行[J]．电网技术, 2015，39(2): 367-374. Zhou Lei, Li Yang. Modeling and optimal dispatch for residential load based on home energy management system under time-of-use pricing[J]. Power System Technology,2015,39(2): 367-374.   
[21]中国城市气象数据[EB/OL]．https://energyplus. net/weather-region/asia_wmo_region_2/CHN%20 （204号 $\% 2 0$ ：   
[22]王彦，王凯，温晓强．实时电价下计及转移成本 的负荷优化[J]．陕西电力，2015，43(6)：55-58. Wang Yan, Wang Kai, Wen Xiaoqiang. Load optimization considering transfer cost under realtime power price[J]. Shannxi Electric Power, 2015, 43(6): 55-58.   
[23]林弘宇，张晶，徐鲲鹏，等．智能用电互动服务平 台的设计[J]．电网技术，2012，36(7)：255-259. Lin Hongyu, Zhang Jing, Xu Kunpeng, et al. Design of interactive service platform for smart power consumption[J]. Power System Technology, 2012, 36(7): 255-259.   
[24]田纪法，焦润海，冯德品，等．含环配电网的网 络重构统一框架研究与实现[J]．电气应用，2016, 35(12): 18-23.   
[25]崔晓飞，许中，朱明星，等．低电压治理装置的适 用性分析[J]．电气应用，2016，35(23)：61-65.