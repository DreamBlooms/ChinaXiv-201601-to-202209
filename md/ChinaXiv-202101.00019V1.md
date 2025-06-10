# 风电场风速规律分析及风电功率预报方法研究

王丹¹，高红燕¹，杨艳超¹，李博²，张黎3（1陕西省气象服务中心,陕西 西安 710014；2国华投资陕西分公司,陕西 榆林719000;3陕西省气象台，陕西 西安710014)

摘要：利用陕西省某一风电场区域内的观测资料,分析了该风电场的风速规律,并引入最优训练期方案，研究利用线性回归方法建立风电功率预报模型的可行性。结果表明：该风电场区域，不同高度的风速及其高度间的风速差异均表现出最大值出现在夜间，最小值出现在白天，从低层到高层的风速日变化趋势一致的特征。一日中，风速与风电功率在 $0 9 { : } 0 0 \sim 1 7 { : } 0 0$ 时段的相关系数明显小于其它时段。按照风速是否大于 $5 \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 将训练期观测样本分为2组，可以明显改善风速与风电功率的回归关系。以风机轮毂高度处的风速作为预报因子，并引入风电功率与风速之间相关系数的日变化规律、以及不同风速量级下风速与风电功率之间回归关系的差异性，采用最优训练期方案和一元线性回归方法建立的风电功率预报方程，具有预报误差小和最优训练期短的特点，满足实际业务需求。

关键词：风电场；风电功率预报；线性回归方法；最优训练期

# 文章编号：

随着全球气候变暖和能源紧张等问题的日益严峻,针对风能等可再生能源的研究越来越受到重视。大容量的风电并入电网会影响电力系统的稳定运行，对风电合理调配利用、风电市场管理及商业运营等带来严峻挑战[1-2],因此对风电功率的预测研究提出了迫切需求。

欧洲一些国家的风能预报工作起步较早，目前已经有不少比较成熟的风能预报系统，如丹麦的PREDIKTOR和WPPT、美国的EWIND、加拿大的WEST、德国的PREVIENTO、西班牙的LOCALPRED和REGIOPRED等[3]。我国风电场风能预报工作开展较晚，科研单位主要有中国电力科学研究院、中国气象局国家气候中心、华北电力大学和清华大学等[4]。风电功率预测的方法有两种，一种是利用实况资料，通过外推的方法进行预报，如自回归滑动平均法[5]、时间序列法[6、卡尔曼滤波法[]、以及人工神经网络方法[8等，但是这种方法计算结果的准确率和时效性较低。另一种是依靠数值天气预报制作风电功率预报[1,9-11],预测时间可以达到 $2 4 \sim 7 2 \mathrm { ~ h ~ }$ 或者更长，但是预报精度会随着预报时效的增加而降低。为了提高预测精度，也有研究者提出了组合预测方法，该方法减少了较大误差点，但是模型复杂、成本较高[12]

在众多的统计分析方法中，线性回归方法是最常用的方法之一，具有所需资料少、计算过程简便的特点。利用气温预报值与观测值之间的一元线性回归关系建立的误差订正方程，可以改善模式的气温预报质量，并被气象部门广泛应用于气温预报业务[13-14]。基于一元线性回归方法，吴启树等[15]设计了最优训练期方案对ECMWF模式的日最高（低）气温进行预报，显著提高了气温预报质量。那么，利用风速与风电功率输出之间的统计关系，通过线

# 干旱区地理

性回归方法建立的风电功率预报模型是否也具有业务应用价值？另外，风速是影响风能资源开发利用的重要因子，研究不同区域风速的变化规律，对提高风电场的功率预测水平和做好风能资源评估具有重要意义[16-18]。本文将利用风电场的观测资料，分析风电场区域内的风速变化规律，并引人最优训练期方案，研究利用线性回归方法建立风电功率预报模型的可行性。

# 1资料和处理

研究资料来自2016年1月1日 $\sim 2 0 1 8$ 年12月31日陕西省某一风电场区域内1台测风塔和33台风机的逐 $5 \mathrm { m i n }$ 观测，由于资料保密原因，省略该风电场的具体地理位置信息。测风塔的观测要素包括风速、风向、温度和气压，其中，风速和风向的测量高度分别是 $8 0 \mathrm { m } \ 、 5 0 \mathrm { m } \ 、 3 0 \mathrm { m }$ 和 $1 0 \mathrm { m }$ ，温度和气压的测量高度均为 $1 0 \mathrm { ~ m ~ }$ 。风机的观测要素包括风速和有功功率，风机轮毂高度为 $8 0 \mathrm { m }$ 。

由于天气或机器故障等原因，测风塔和风机的观测数据会有不合理值出现，为了保证研究结论的可靠性,有必要剔除异常值[4]。对测风塔观测资料的质量控制包括以下方面：(1)风速和风向的观测值范围分别在 $0 \sim 4 0 ~ \mathrm { m \cdot s ^ { - 1 } }$ 和 $0 ^ { \circ } \sim 3 6 0 ^ { \circ }$ 之间。(2)风速大于 $5 \mathrm { m \cdot s ^ { - 1 } }$ 且风速和风向连续 $6 \mathrm { { h } }$ 无变化的情况视为缺测，风速小于 $0 . 4 \ \mathrm { m \cdot s ^ { - 1 } }$ 且连续 $3 \mathrm { { h } }$ 以上无变化的情况视为缺测。(3)相隔高度在 $1 \sim 2 0 \mathrm { ~ m ~ }$ 和 $2 1 \sim$ $4 0 \mathrm { m }$ 条件下的风速差值分别小于 $5 \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 和 $1 0 \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 }$ 。(4)当风速大于 $5 \ \mathrm { m \cdot s ^ { - 1 } }$ 时，风速的标准偏差小于$1 0 \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 } \circ ( 5 )$ 高度风向差小于 $2 2 . 5 ^ { \circ }$ 。(6)小时平均风速(温度)变化小于 $1 0 \ \mathrm { m \cdot s ^ { - 1 } } ( 5 \ \mathrm { ^ { \circ } C } ) , 3 \ \mathrm { h }$ 变压小于1$\mathrm { { h P a } }$ 。对风机观测资料的质量控制包括以下方面：(1)风速大于 $5 \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 而有功功率小于 $5 0 \mathrm { k W }$ 的记录值予以剔除。(2)风速和有功功率分别大于切出风速$2 0 \mathrm { m \cdot s ^ { - 1 } }$ 和额定功率 $1 5 0 0 \mathrm { k W }$ 的记录值予以剔除。

# 2风电场风速规律研究

利用测风塔和风机的逐 $5 \mathrm { m i n }$ 观测资料，统计得到风机有功功率与风机风速、测风塔的 $8 0 \mathrm { ~ m ~ } . 5 0 \mathrm { ~ m ~ }$ 、$3 0 \mathrm { ~ m ~ }$ 和 $1 0 \mathrm { ~ m ~ }$ 风速的相关系数依次为 $0 . 8 8 , 0 . 8 4$ 、0.83、0.81和0.75(均通过了 $\alpha = 0 . 0 1$ 的显著性水平检验），有明显的正相关关系，与 $1 0 \mathrm { m }$ 气温和 $1 0 \mathrm { m }$ 气压的相关系数分别为 $- 0 . 1 2$ 和 $- 0 . 0 6$ ,相关性不明显，可见，风速是影响风电功率的最主要因子。为了了解风电场所在区域内的风速变化和风廓线特征，下面对测风塔不同高度的风速观测结果进行分析。

图1为2016年1月1日 $\sim 2 0 1 8$ 年12月31日测风塔的 $8 0 \mathrm { m } \ 、 5 0 \mathrm { m } \ 、 3 0 \mathrm { m }$ 和 $1 0 \mathrm { m }$ 不同高度各季节平均风速的日变化。从图1来看，春季、秋季和冬季的风速日变化特征相近，各高度的平均风速从凌晨开始逐渐减少，在 $0 9 { : } 0 0 \sim 1 0 { : } 0 0$ 左右达到极小值，然后开始增大，到14:00左右达到极大值，然后再次逐渐减小，在19:00左右再次达到极小值，之后又逐渐增大，直至凌晨 $2 3 { : } 0 0 \sim$ 次日01:00左右达到极大值。夏季， $8 0 \mathrm { ~ m ~ } . 5 0 \mathrm { ~ m ~ }$ 和 $3 0 \mathrm { ~ m ~ }$ 各高度的平均风速从凌晨开始逐渐减少，在 $0 8 { : } 0 0 \sim 0 9 { : } 0 0$ 左右达到极小值，然后开始逐渐增大，直至凌晨02：00左右达到极大值，而 $1 0 \mathrm { ~ m ~ }$ 平均风速的日变化特征与其它季节相似。整体上讲，夜间的风速大于白天，风速极小值出现在上午和傍晚，极大值出现在凌晨和下午，袁莹莹等[19]研究了我国风蚀区的风速日变化特征,发现部分山区的站点日最大风速出现在夜间，与本文的研究结论一致。另外，风机有功功率的最小值出现在上午，最大值出现在凌晨，与图1给出的测风塔观测到的风速的日变化特征有一些差异（如，在下午14:00左右没有出现有功功率的极大值），但是与风机站观测到的风速的日变化特征一致(图略)。

风速的垂直分布会影响风电功率输出，如果能将风速廓线随时间的变化规律引入风速和风电功率预报模型,将有利于减少预报误差[13]。图2给出了各季节不同高度间风速差异的日变化曲线。从图2来看，各季节不同高度间的风速差异均表现出由夜间到白天逐渐减小，由白天到夜间逐渐增大的趋势，最小值出现在上午 $1 0 { : } 0 0 \sim 1 1 { : } 0 0$ 左右。白天的不同高度间的风速差异小于夜间，这与白天大气层结处于不稳定或中性状态，大气湍流混合较强，有利于减小各层间的风速差异，而夜间大气层结稳定，湍流微弱，动量不宜下传，使得各层间的风速差异较大有关[13]。 $8 0 \mathrm { ~ m ~ }$ 与 $1 0 \mathrm { m }$ 高度间的风速差异全年始终保持最大， $5 0 \mathrm { m }$ 与 $1 0 \mathrm { m }$ 高度间的风速差异次之。但是不同高度间的风速差异与它们之间的高度差并不完全成正比，如， $3 0 \mathrm { m }$ 与 $1 0 \mathrm { m }$ 高度间的风速差异大于与 $8 0 \mathrm { ~ m ~ }$ 高度间的风速差异，即，近地面到 $3 0 \mathrm { m }$ 高度的风速减小幅度大于 $3 0 \mathrm { m }$ 到 $8 0 \mathrm { m }$ 高度的风速减小幅度，这与该风电场区域内下垫面条件对风速垂直变化的影响较大有关[23]。

![](images/23f2513a131178eda5afbe754bc9c551f65c5622d05c59d3d47f00bfe6dd9f91.jpg)  
图1测风塔各季节不同高度平均风速的日变化  
Fig.1Diurnal variation of seasonal average wind speed at different heights of wind tower

文献[13]研究的张北和吉林两个地区风电场的风速廓线分布形式与本文研究的陕西地区风电场相似，但是各高度的风速日变化特征与本文的研究结果有一些差异，这与各风电场的下垫面条件和低层大气层结状态有一定差异有关。

# 3风电功率预报

# 3.1 方法

由于风电功率输出与风速的相关性较好，与温度和气压场的相关性较弱，并且孙川永[3的研究也已证明温度场和气压场的引入并不能改进风电功率的预报结果，风向的引入理论上虽然对风电功率预报有重要意义，但是预报结果并不理想。本节将以风速作为预报因子，研究利用线性回归方法建立风电功率预报模型的可行性，以及如何选取预报因子和设计训练期方案，预报时效为 $2 4 \mathrm { ~ h ~ }$ 内逐1h预报，起报时间为08：00(北京时间）。

3.1.1线性回归方法在一个给定的风机站上，对于某一预报时效的有功功率，建立方程：

$$
C _ { \phantom { } _ { t } } = \sum _ { i = 1 } ^ { m } a _ { i } F _ { \phantom { } _ { i , t } } + b ,
$$

式中： $C _ { t }$ 为预报值, $\boldsymbol { F } _ { i , t }$ 为第 $i$ 个预报因子， $a _ { i }$ 为第 $i$ 个预报因子的回归系数权重，b为常数项， $m$ 为参与集成的因子总数， $\mathbf { \chi } _ { t }$ 为预报时效， $t { = } 1 , 2 , \cdots , 2 4 \mathrm { ~ h ~ }$ ，式中 $a _ { i }$ 和 $b$ 通过最小二乘法原理计算得到。

3.1.2最优训练期方案采用滑动训练期,训练样本为预报日之前 $N$ 日的历史资料，分别取， $N { = } 4$ $5 , \cdots , 3 6 5 \mathrm { ~ d ~ }$ ,逐日滑动建立风电功率预报模型，再假设预报日的风速观测值为预报值，代人该预报模型制作风电功率预报，最后计算2017年1月1日\~2018年12月31日风电功率预报的平均绝对误差(MAE)，平均绝对误差最小值对应的 $N$ 即为最优训练期。 $M A E$ 的计算公式为：

$$
M A E = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \lvert \ y _ { i } - x _ { i } \rvert \ ,
$$

式中： $y _ { i }$ 和 $x _ { i }$ 分别为第 $i$ 次预报的预报值和观测值， $n$ 为参与检验的总预报次数。

3.1.3建模方案I利用风机的风速和有功功率观测资料，基于一元线性回归方法和最优训练期方案，设计了方案 $1 . 1 \sim 1 . 4$ (表1)，先对每台风机站进行功率预报，然后累加后除以风机台数得到整个风电场的平均功率，其中，方案1.3和1.4按照风速是否大于5$\mathbf { m \cdot s ^ { - 1 } }$ 将训练期样本分为2组后分别建立预报方程。当风电功率预报值 ${ < } 0 \mathrm { ~ k W }$ 或者 ${ \mathrm { > } } 1 5 0 0 { \mathrm { ~ k W } }$ 时，分别令风电功率预报值为 $0 \mathrm { k W }$ 或者 $1 5 0 0 \mathrm { k W }$ 。

![](images/cbb7bdee25131c842525698b1cb2510d9632e13e6e17649d1228717fd9c6bdd2.jpg)  
  
图2风电场区域内风廓线的李节平均日变化特征 $\Delta \mathrm { u } 8 0 { \sim } 5 0$ 为 $8 0 \mathrm { m }$ 与 $5 0 \mathrm { m }$ 高度间的平均风速差异， $\Delta \mathrm { u } 8 0 { \sim } 3 0$ 为 $8 0 \mathrm { m }$ 与 $3 0 \mathrm { m }$ 高度间的平均风速差异， 依此类推， $\Delta \mathrm { u } 8 0 { \sim } 1 0 \ 、 \Delta \mathrm { u } 5 0 { \sim } 3 0 \ 、 \Delta \mathrm { u } 5 0 { \sim } 1 0 \ 、 \Delta \mathrm { u } 3 0 { \sim } 1 0 \$ 分别为相应高度间的平均风速差异 Fig.2 Diurnal variation of seasonal average wind profile in wind farm area ${ \Delta } { \mathrm { u } } 8 0 { \mathrm { - u } } 5 0$ is the average difference of wind speed between height of 80 meters and 5O meters , ${ \Delta } { \mathrm { u } } 8 0 { - } { \mathrm { u } } 3 0$ is the average difference of nd speed between height of 8O meters and 3O meters,in the same way, $\Delta \mathrm { u } 8 0 \mathrm { - u } 1 0 \mathrm { , } \Delta \mathrm { u } 5 0 \mathrm { - u } 3 0 \mathrm { , } \Delta \mathrm { u } 5 0 \mathrm { - u } 1 0$ and ${ \Delta } { \mathrm { u } } 3 0 { - } { \mathrm { u } } 1 0 \$ are the average difference of wind speed between corresponding heights

Tab.1 First scheme designs of wind power prediction   

<html><body><table><tr><td>方案设计</td><td>方案1.1</td><td>方案1.2</td><td>方案1.3方案1.4</td><td></td></tr><tr><td>是否分预报时次建模</td><td>是</td><td>香</td><td>是</td><td>香</td></tr><tr><td>是否按照风速量级对训练 期样本进行分组后建模</td><td>否</td><td>否</td><td>是</td><td>是</td></tr></table></body></html>

3.1.4 建模方案II增加了其他高度风速作为预报因子，采取多元线性回归方法和最优训练期方案建立风电功率预报模型。虽然风电功率与风机站风速的相关系数必然大于与测风塔不同高度处风速的相关系数，但是风机站与测风塔的风速观测不在同一地点，因此，建模方案Ⅱ没有将风机站的风速作为预报因子，而是利用33个风机站的平均功率和测风塔的 $8 0 \mathrm { m } . 5 0 \mathrm { m } . 3 0 \mathrm { m } . 1 0 \mathrm { m }$ 高度风速的观测资料，将整个风电场的平均功率作为一个整体进行预报。在方案1.1的基础上，建模方案Ⅱ根据预报因子的不同，设计了方案 $2 . 1 \sim 2 . 4$ (表2)。同样，当风电功率预报值 $< 0 \mathrm { \ k W }$ 或者 $> 1 5 0 0 \mathrm { k W }$ 时，分别令风电功率预报值为 $0 \mathrm { k W }$ 或者 $1 5 0 0 \mathrm { k W }$ ○

表1建模方案I的方案设计  
表2建模方案I的方案设计  
Tab.2 Second scheme designs of wind power prediction   

<html><body><table><tr><td>方案设计 预报因子</td><td>80m 风速</td><td>50m 风速</td><td>30m 风速</td><td>10 m 风速</td></tr><tr><td>方案2.1</td><td>√</td><td></td><td></td><td></td></tr><tr><td>方案2.2</td><td>√</td><td>√</td><td></td><td></td></tr><tr><td>方案2.3</td><td>√</td><td>√</td><td>√</td><td></td></tr><tr><td>方案2.4</td><td>√</td><td>√</td><td>√</td><td>√</td></tr></table></body></html>

# 3.2 结果分析

3.2.1 建模方案I的检验对于线性回归方程,样本量的大小直接影响着线性回归系数的计算结果，但是样本量既不是越大越好，也不是越小越好。最优训练期日数的研究是为了在预报日之前的历史观测资料中选取最合适的样本，以建立风电功率与风速的最优线性回归方程，从而最大限度地降低风电功率的预报误差。从方案 $1 . 1 \sim 1 . 4$ 的最优训练期日数来看(表3)，方案1.1和1.3的最优训练期日数分别大于方案1.2和1.4，这是因为在训练期日数相同的情况下，方案1.2和1.4的训练样本数分别比方案1.1和1.3多一些，由于有24个预报时次，前者最多可以达到后者的24倍，有利于方案1.2和1.4在训练期日数较小时有较多的训练样本建立线性回归方程。方案1.3和1.4的最优训练期日数分别小于方案1.1和1.2，这是因为方案1.3和1.4按照风速是否

# 表3建模方案1的风电功率预报结果检验

Tab.3 Test of wind power prediction made by the first scheme designs   

<html><body><table><tr><td>统计量</td><td>方案1.1</td><td>方案1.2</td><td>方案1.3</td><td>方案1.4</td></tr><tr><td>最优训练期日数/d</td><td>86</td><td>64</td><td>70</td><td>7</td></tr><tr><td>平均绝无误差/kW</td><td>82</td><td>88</td><td>48</td><td>66</td></tr></table></body></html>

大于 $5 \mathrm { m \cdot s ^ { - 1 } }$ 对样本进行分组，分组后风电功率和风速之间的相关关系更明显，从而有利于用较少的训练样本就能建立拟合效果较好的线性回归方程。

从方案 $1 . 1 \sim 1 . 4$ 的风电功率预报的平均绝对误差来看(表3)，方案1.1和1.3的平均绝对误差分别小于方案1.2和1.4，这是因为一日中风电功率与风速在 $0 9 { : } 0 0 \sim 1 7 { : } 0 0$ 时段的相关系数小于其它时段，方案1.1和1.3是逐预报时次建立预报方程的，在各时刻的预报误差都比较小，而方案1.2和1.4是不分预报时次建立预报方程的，在 $0 9 { : } 0 0 \sim 1 7 { : } 0 0$ 的预报误差明显偏大(图3)。方案1.3和1.4的平均绝对误

![](images/ea9708c7f48c755f3ae0308e1c451d9e3d0f80912afa9b3878888a8531775a38.jpg)  
图3建模方案I的风电功率预报值与观测值的逐时次对比 $( \mathbf { a } \sim \mathbf { d } )$ 以及风电功率观测值与风速观测值的相关系数(e)  
Fig.3Hourly comparison between observation and prediction of wind power made by the first scheme designs $( \mathbf { a } \sim \mathbf { d } )$ and correlation coefficient between observations of wind power and wind speed (e)

# 干旱区地理

![](images/b6581b8971c54d1c6be0d2e9140c094f1b32dba4011aba7d81bf8d7efcbe314d.jpg)  
图4风速一风电功率的散点图及线性回归曲线效果示意图 Fig.4 Scatter plot and linear regression curve between wind speed and wind power

差分别小于方案1.1和1.2，可见按照风速等级分组后建立的预报方程优于不分组，可用图4来解释。图4任选100次风电功率和风速的观测资料作为样本绘制风速-风电功率散点图，并按照风速是否大于 $5 \ \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 将样本分为2组，分别绘制分组前、后风速-风电功率的线性回归曲线，结果表明，按照风速大小对样本进行分组之后，风速一风电功率的散点更紧密地分布在线性回归曲线两侧，明显改善了风速与风电功率的回归关系。

图5是对方案 $1 . 1 \sim 1 . 4$ 的风电功率预报的平均绝对误差的逐日对比。从图5来看，方案1.3的平均绝对误差最小，可见，利用一元线性回归方法建立风电功率预报方程时，引入风电功率与风速之间相关程度的日变化特征，以及不同风速量级下风电功率与风速之间回归关系的差异性，有利于减小预报误差。另外，本文将风速观测值假定为预报值来检验方案 $1 . 1 \sim 1 . 4$ 的风电功率预报效果，不必考虑风速预报质量随预报时效的变化，因此不必检验较长预报时效的风电功率预报结果，而取 $1 { \sim } 2 4 \mathrm { h }$ 预报时效是为了考虑风电功率与风速之间相关程度的日变化特征。

方案1.3和文献[13]计算的 $2 4 \mathrm { h }$ 内的风电功率预报的均方根误差分别在 $5 0 \sim 1 6 0 ~ \mathrm { k W }$ 和 $2 0 0 \sim 4 0 0$ $\operatorname { k W }$ 之间，前者是在假定风速的观测值为预报值的基础上进行预报实验的，后者则引入数值模式的风速预报进行预报实验，因此，不能直接对二者的预报结果进行对比。要将方案1.3投入业务应用，还需要引入风机轮毂高度(约 $8 0 \mathrm { m }$ )处的风速预报产品。 $8 0 \mathrm { m }$ 风速预报不属于常规预报，例如，著名的ECMWF模式不输出 $8 0 \mathrm { m }$ 风速预报，但是输出 $1 0 0 \mathrm { m }$ 风速预报，可以先将该模式的 $1 0 0 \mathrm { m }$ 风速预报订正到风机轮毂高度上，再代入方案1.3进行风电功率预报

3.2.2建模方案I的检验与建模方案I相比，建模方案Ⅱ的最优训练期日数和风电功率预报的平均绝对误差都明显偏大，这与风电功率与测风塔风速的相关性弱于与风机站风速的相关性有一定关系。由于建模方案I和Ⅱ的研究资料不同，因此，不再对建模方案I与Ⅱ的风电功率预报结果

![](images/4cc8497db5f53a48ee36ac19cdeb96eeca0169ef38bb23233d8e872103720f29.jpg)  
图5方案 $1 . 1 \sim 1 . 4$ 的风电功率预报的平均绝对误差的逐日分布  
Fig.5Daily variation of mean absolute errors of wind power prediction from scheme 1.1 to 1.4

# 表4建模方案II的风电功率预报结果检验

Tab.4 Test of wind power prediction made by the second scheme designs   

<html><body><table><tr><td>统计量</td><td>方案2.1</td><td>方案2.2</td><td>方案2.3</td><td>方案2.4</td></tr><tr><td>最优训练期日数/d</td><td>365</td><td>341</td><td>319</td><td>320</td></tr><tr><td>平均绝无误差/kW</td><td>103.58</td><td>261.81</td><td>261.92</td><td>263.2</td></tr></table></body></html>

进行比较。

从建模方案Ⅱ的风电功率预报检验结果(表4)来看，方案 $2 . 2 \sim 2 . 4 \$ 的平均绝对误差是方案2.1的2倍以上，即，与仅以 $8 0 \mathrm { ~ m ~ }$ 高度的风速作为预报因子的建模方案相比，增加其它高度的风速作为预报因子后，风电功率预报的平均绝对误差明显增大。从方案 $2 . 1 \sim 2 . 4$ 的风电功率预报值与观测值的逐日(图6)和逐小时(图略)对比来看，方案2.1的预报值与观测值的吻合程度较好，而方案2.2～2.3的吻合程度较差，预报结果更像是对观测值的平均。

文献[13通过神经网络方法进行风电功率预报研究，发现利用不同高度风速作为预报因子比只利用风机轮毂高度风速作为预报因子的预报误差要小一些，与本文利用多元线性回归方法进行风电功率预报研究的结论相反。这可能因为风机功率输出与除观测高度以外的其它高度的风速可能不是简单的线性关系，利用多元线性回归方法研究风廓线对风电功率预报的影响有一定局限性。

# 4结论

本文利用2016年1月1日 $\sim 2 0 1 8$ 年12月31日陕西省某一风电场区域内的观测资料，分析了风电场区域的风速规律，并将分析结果融人风电功率预报的方案设计中，引进最优训练期方案，研究利用线性回归方法建立风电功率预报模型的可行性。主要结论如下：

（1）不同高度的风速及高度间的风速差异均表现出最大值出现在夜间，最小值出现在白天，从低层到高层的日变化趋势一致的特征。该风电场区域各高度的风速日变化特征与前人研究的其它地区的风电场有一些差异，这与各风电场的下垫面条件和低层大气层结状态有一定差异有关。

（2）风电功率与风速有显著的正相关关系，一日中，二者在 $0 9 { : } 0 0 \sim 1 7 { : } 0 0$ 时段的相关系数明显小于其它时段。按照风速是否大于 $5 \mathrm { m } \cdot \mathrm { s } ^ { - 1 }$ 将训练期观测样本分为2组，可以明显改善风速与风电功率的回归关系。

（3）以风机轮毂高度处的风速作为预报因子，并引入风电功率与风速之间相关程度的日变化规律、以及不同风速量级下风速与风电功率之间回归关系的差异性，采用最优训练期方案和一元线性回归方法建立的风电功率预报方程，具有预报误差小和最优训练期短的特点，可以投入业务应用。但是

![](images/c4ea4cd2888da21f4de9e0c2110cd081ec1247238716bcb0d4ef0127c28eca12.jpg)  
图6方案 $2 . 1 \sim 2 . 4$ 的风电功率预报值与观测值的逐日比较   
Fig.6Daily comparison between observation and prediction of wind power from scheme 2.1 to 2.4

# 干旱区地理

增加其它高度风速作为预报因子，采用多元线性回归方法建立的风电功率预报方程，预报误差较大，不满足业务需求。

# 参考文献(References)

[1董广涛,穆海振,周伟东,等.基于气象数值模式的风电功率预测 系统[J].太阳能学报,2012,3(5):776-781.[DONG Guangtao, MU Haizhen, ZHOU Weidong,et al.A wind-power forecast system based on the meteorological model[J].Acta Energlae Solaris Sinica,2012,33(5): 776-781.]   
[2]ALEXIADIS M, DOKOPOULOS P, SAHSAMANOGLOU H, et al. Short term forecasting of wind speed and related electrical power [J]. Solar Energy,1998,63(1): 61-68.   
[3]王勇,李照荣,李晓霞,等.风电功率预报方法研究进展[J].干旱 气象,2011,29(2): 156-160.[WANG Yong,LI Zhaorong,LI Xiaoxia,et al.Forecast method advanceson wind electricity[J]. Journal of Arid Meteorology,2011,29(2): 156-160.]   
[4]刘兴杰.风电输出功率预测方法与系统[D].北京:华北电力大 学,2011.[LIU Xingjie. Wind power prediction approach and system[D]. Beijing: North China Electric Power University,2011.]   
[5]MILLIGAN M,SCHWARTZ M,WAN Y. Statistical wind power forecasting for U.S.wind farms[R].Preprint of the conference “WIND-POWER2003”,Austin, May 18-21,2003.   
[6]杨秀媛,肖洋,陈树勇.风电场风速和发电功率预测研究[J].中 国电机工程学报,2005,25(11):1-5.[YANG Xiuyuan,XIAO Yang, CHEN Shuyong. Wind speed and generated power forecasting in wind farm[J]. Proceedings of the CSEE,2005,25(11): 1-5.]   
[7]BOSSANYI E A.Short-term wind prediction using kalman filters [J]. Wind Engineering,1985,9(1): 1-8.   
[8]ATA R.Artificial neural networks applications in wind energy systems:A review [J]. Renewable and Sustainable Energy Reviews, 2015,49: 534-562.   
[9]王建成,杨苹,杨曦.基于数值天气预报的风电功率预测建模研 究[J].可再生能源,2013,31(2):34-38.[WANG Jiancheng, YANG Ping, YANG Xi. Research on wind power prediction modeling based on numerical weather prediction[J]. Renewable Energy Resources,2013,31(2): 34-38.]   
[10] 冯芝祥,朱同生,曹书涛,等.数值天气预报在风电场发电量预 报中的应用[J].风能,2010,(4):58-61.[FENG Zhixiang, ZHU Tongsheng, CAO Shutao, et al. Application of numerical weather forecast in electric power generation forecast of wind farm[J]. Wind Energy,2010,(4): 58-61.]   
[11]孙川永.风电场风电功率短期预报技术研究[D].兰州:兰州大

学,2009.[SUN Chuanyong.A study on the technique of shortterm forecast of wind power at wind farm[D]. Lanzhou: Lanzhou University,2009.]   
[12] 符金伟,马进,周榆晓,等.风电功率预测研究方法综述[J].华东 电力,2012,(5): 888-892.[FU Jinwei, MA Jin,ZHOU Yuxiao,et al. Review on wind power prediction methods[J]. East China Electric Power,2012,(5): 888-891.]   
[13] 王丹,王建鹏,白庆梅,等.递减平均法与一元线性回归法对 ECMWF温度预报订正能力对比[J].气象,2019,45(9):1310- 1321.[WANG Dan,WANG Jianpeng,BAI Qingmei,et al.Comparative correction of air temperature forecast from ECMWF Model by the decaying averaging and the simple linear regression methods[J]. Meteorological Monthly,2019,45(9): 1310-1321.]   
[14]王丹,王建鹏,娄盼星,等．ECMWF高分辨率模式对陕西2017 年7月高温预报的检验及订正[J].干旱区地理,2019,42(1): 38-46.[WANG Dan, WANG Jianpeng, LOU Panxing, et al.Evaluation and correction of high temperature weather forecast in Shaanxi Province in July 2O17 using ECMWF high-resolution model[J]. Arid Land Geography,2019,42(1): 38-46.]   
[15] 吴启树,韩美,郭弘,等．MOS 温度预报中最优训练期方案[J]. 应用气象学报,2016,27(4):426-434.[WU Qishu,HAN Mei, GUO Hong,et al.The optimal training period scheme of MOS temperature forecast[J]. Journal of applied meteorological science, 2016,27(4): 426-434.]   
[16] 李雁,梁海河,王曙东,等.基于中国风能资源专业观测网的近 地层风切变日变化特征[J].自然资源学报,2012,27(8):1362- 1372.[LI Yan,LIANG Haihe,WANG Shudong,et al. Study of the near surface wind shear daily variation characteristics based on China’s wind power resources professional observation network [J]. Journal of Natural Resources,2012,27(8): 1362-1372.]   
[17]李京龙,武胜利,葛欢欢,等.1962-2016年阿勒泰地区风速变 化分析[J].干旱区地理,2018,41(3): 499-507.[LIJinglong,WU Shengli,GE Huanhuan,et al. Wind speed change in Altay Prefecture from 1962 to 2016[J].Arid Land Geography，2018,41(3): 499-507.]   
[18] 曹永强,郭明,刘思然,等.近55a辽宁省风速时空变化特征分 析[J].干旱区地理,2018,41(1):1-8.[CAO Yongqiang,GUO Ming,LIU Siran, et al.Temporal and spatial variation characteristics of wind speed in Liaoning Province in recent 55 years[J].Arid Land Geography,2018,41(1): 1-8.]   
[19] 袁莹莹,殷水清,谢云,等.我国风蚀区风速日变率时空变化特 征[J].干旱区地理,2018,41(3):480-487.[YUAN Yingying,YIN Shuiqing, XIE Yun, et al. Temporal and spatial characteristics of diurnal variations of wind speed in wind erosion areas over China [J]. Arid Land Geography,2018,41(3): 480-487.]

# Temporal and spatial changes of extreme temperature and its influencing factors in northern China in recent 58 years

WANG Dan'， GAO Hong-yan'， YANG Yan-chao'，LI Bo²， ZHANG Li³ (1ShaanxiMeteologicalServiceCenter,Xi'an4,hani,China；2GuohuaEnergyIvestmentCo.,td(ani Branch),Yulin790o,haanxi,China；3haanxiMeteologicalObservatoryXi'an014,Shaani,Cina)

Abstract:Under the background of global warming,disasters caused by extreme temperature changes such as drought, heat waves,andcold snaps arebecoming moreand more frequent,which poses aserious threat to industrial and agricultural production,human lifeand property.Thus,extreme temperature changes have graduallybecome awidespread concern.Thus studyanalyzes temporal and spatialchangesof extreme temperatures and explores factors influencing temperature indices using daily maximum and minimumtemperature datafrom 404 stations in northern China for the period 1960-2017.The study calculated 16 extreme temperature indices using the RclimDex1.O function of $R$ and investigated spatial-temporal variation characteristics of extreme temperature events and influence factors using linear regression,the Mann-Kendal test,the sliding t-test,and cumulativeanomalyandcorrelationanalysis.Theresultsof theanalysisfound the following. (1)There was anupward trend in warm extremes and extremal indicesand a downward trend in cold extremes anddiurnal temperaturerange;the magnitudesof changes incold extremes are obviously higher than thoseof warm extremes andthe magnitudes of changes in night extremes are higher than those of day extremes.Warming in the northwestregion is themost obvious,whereaswarming inthe northeastregion is notobvious.(2)The mutation timeof the extreme temperature indices mainly occured inthe 198Osand 199Os,andthecold extremes and minimum values of daily maximum (minimum)temperature mutated earlier than those of the warm extremes and maximum values of daily maximum (minimum) temperature.After mutation,extreme warm events and extreme value events tended to occur frequently, whereas extreme cold events gradually decreased in frequency.The extreme temperature indices in the northeast region showed theearliest mutationtimeand the northwestregion showedthe latest mutation time.(3) Changes inthe extreme temperature indices also respond to the global warming hiatus of 1988-2012.(4) Most of the extreme temperature ndices showaclose corelation with longitude,latitude,and elevation. (5)The Arctic Oscillation index has the greatest impact on extreme temperatures and the most significant efect on thecold index.(6) During 2007-2O16,there was a downward trend inaerosoloptical depth (AOD),and extreme high temperature events increasedand extremelowtemperature events decreased.Mostcold indices were negativelycorrelated with AODand most warm indexes were positivelycorrelated with AOD.This study analyzes extreme temperature variation characteristics in northern China,aims to deplyunderstand extreme temperature change trends tohelp carryoutmeteorological disaster prediction,conduct early warning research,reduce the adverse impacts of extreme temperature events onlocal productionand life,and ensure the safetyof agricultural production.

Key words:wind farm; wind power prediction; linear regression method; optimal training period