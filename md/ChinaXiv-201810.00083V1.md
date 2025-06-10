# 基于多指标模糊综合评价的交通拥堵预测与评估

晏雨婵，白璘，武奇生，叶珍(长安大学 电子与控制工程学院，西安 710064)

摘要：针对各交通时段对交通拥堵的不同影响、单因素无法准确表征交通拥堵状态的问题，提出了一种采用多指标模糊综合评价的交通拥堵评价预测方法。该方法利用粒子群算法优化支持向量回归机对道路平均速度和交通流量进行预测，得到三个因素指标平均速度V、交通流密度D、道路饱和度S的预测值。将三个因素指标输入到多指标模糊综合评价模型中，即首先建立交通拥堵状态的因素集和评价集，通过熵值法确定早高峰、晚高峰、其他时段下三个因素指标的权重系数，再通过梯形隶属度函数确定各指标在各时段的隶属度，最终将交通拥堵状态划分为六个级别。通过对美国PeMS 数据库中I405高速路的交通数据进行预测评价实验证明，采用该方法预测的交通拥堵状态基本与实际状态吻合，具有较高的预测精度，正确率可达 $9 4 . 7 9 \%$ 。

关键词：交通拥堵；多指标模糊综合评价；因素指标；熵值法；梯形隶属度函数中图分类号：TP181 doi:10.3969/j.issn.1001-3695.2018.07.0425

# Traffic congestion prediction and assessment based on multi-index fuzzy comprehensive evaluation

Yan Yuchan†, Bai Lin, Wu Qisheng, Ye Zhen (School of Electronics& Control Engineering,Chang'an University,Xi'an 71o064,China)

Abstract:Inviewofthedifferent impactsofdifferent trafic periodsontraffccongestionandsinglefactorfail toaccurately characterizethetrafficcongestionstate,thispaperproposedamulti-index fuzzycomprehensiveevaluationmethodfortraffic congestionstate evaluation.The method used the particle swarm optimization algorithm tooptimize the support vector regression topredict te averageroad speedandtraffc flow,obtained the predicted values ofthe average sped v,trafc flow densityD,androadsaturationS,andinput thethreefactorindexes toMulti-index fuzzycomprehensiveevaluationmodelthat establishthesetoffactorsand evaluation(level)fortraficcongestion.Itdeterminedtheweightcoeficientsof thre factors underthe morning peak and the evening peak and other periodsbytheentropy method,then determined the degree of membershipofeach index ineachperiodbythe trapezoidal membershipfunction.Finally,itdivided the traficcongestion stateintosix levels.TheresultsofpredictiveevaluationatthetraficdataoftheI405highwayinPeMSshowthatthe trafic congestionstateevaluated bytheproposed method is basicallyconsistent with theactual stateand hasahigh prediction accuracy, the correct rate can reach $9 4 . 7 9 \%$

Keywords:trafficcongestion;multi-index fuzzycomprehensive evaluation；factor index；entropy method；trapezoidal membership function

# 0 引言

交通拥堵状态级别是综合反映道路网交通运行状况的指标，根据美国发行的《道路通行能力手册》HCM（highwaytransportationmanual）[1]中的“道路服务水平”将交通拥堵状态分为六个级别（1非常畅通、2畅通、3轻度拥堵、4中度拥堵、5严重拥堵、6锁死)，数值越高表明交通拥堵状况越严重。

日益严重的交通拥堵已经严重影响市民正常工作学习的出行时间。根据北京交通发展研究中心[2]的历年数据分析，得出了居民出行花费时间和交通拥堵状态的大致对应关系，北京将拥堵状态分为五个级别，如图1所示。

当交通状态为非常畅通时，说明道路上基本没有出现拥堵，可以按照道路的限速标准行驶；当交通状态为基本畅通时，居民出行时间需要多花费0.3\~0.5倍时间；当交通状态为轻度拥堵时，居民出行时间需要多花费 $\phantom { - } 0 . 5 { \sim } 0 . 8$ 倍时间；当交通状态级别为中度拥堵时，居民出行时间需要多花费0.8-1.0倍时间；当交通状态级别为严重拥堵时，居民出行时间需要多花费1.0倍以上时间，可见当交通状况越严重时，对居民的工作影响越严重。通过观测交通拥堵状态级别的变化，居民可以了解到整个道路的拥堵状况，对自己出行的时间有大致的预期，从而可以选择其他的方式或道路出行，可以有效地避免交通拥堵带来的影响。

![](images/8c89792d44de4dbbaffc9998e1ddd0cafd3b09438af54a7e9f83876c5d2711bf.jpg)  
图1居民出行花费时间

目前，用于衡量交通拥堵状态的参数主要包括交通流参数、驾驶员体感参数、车辆排队长度等。交通流参数主要指交通流量、平均速度、交通流密度或占有率等反映交通流特性的参数。交通拥堵状态评估分为单因素评判和多因素评判。单因素评价就是仅仅使用一个参数来对交通拥堵状态进行评估。对于单因素评价，Shi等人[3提出了空间平均速度估计方法，并对其指数平滑处理，实现实时交通拥堵状况评估。Castro等人[4通过出租车轨迹提取的历史交通流密度和速度数据计算每个路段的容量，以路段容量来划分拥堵密度等级，从而进行拥堵评估。杨俊瑛[5]应用加权改进的GM(1,1)-马尔可夫预测模型进行速度预测，将预测结果与决策阈值比较判定交通拥堵状况。

由于交通道路的复杂情况，单个交通流参数往往不足以表征整个道路系统的拥堵状态。为了提高交通拥堵状态的评估准确度，学者们又提出了多参数表征交通拥堵状态。龙小强等人[6在交通数据中提取路段平均行程速度，单位里程平均延误和路段饱和度三个交通参数，运用模糊综合评价模型进行交通拥堵评估。谭娟等人[从交通流参数、环境状态、时段等基础数据来构建交通流特征向量，最后使用Softmax回归对交通拥堵状态进行多态预测。黎符忠[8结合信息熵赋权法与灰色系统理论，构建了交叉口指标、路段指标以及区域指标等因素的城市道路交通拥堵评价体系。黄大荣等人9基于多元集对分析建立一种新的路网交通拥堵状态刻画模型，通过D-S证据理论实现交通信息融合,并推导出当前交通拥堵状态。

考虑到早高峰、晚高峰和其他时段下交通流参数的不同时间特性和单因素指标无法准确表征交通拥堵状态的问题，本文首先利用PSO 优化 SVR预测模型[10-14]预测出所需要的三种因素指标预测值，通过多指标模糊综合评价方法对三个不同时段进行交通拥堵分析，其中熵值法确定评价中所需要的各个时段各个指标的权重系数，最后将交通状况划分为6个等级。

# 1 交通拥堵评价因素指标的选取

对于交通拥堵状态预测评估，首先要选取能够准确有效地表征交通拥堵状态的因素指标，选取的原则是具有整体完备性、客观性、可操作性、可比性[15]。但不能只通过某一项交通流参数对交通拥堵状况进行评估。车辆平均速度可以很直观地表征交通拥堵状态，但当车辆在十字路口等待红灯时，虽然速度很小，却并不能说明此刻的道路是拥堵的。因此，本文选取了交通流平均速度、交通流密度、路段饱和度三个交通流参数作为因素指标。

交通流平均速度指的是单位时间内一条道路中所有车辆行驶距离的平均值。该指标能够直观地反映出当前道路的交通拥堵状况，一般来说，速度越大，道路越畅通；速度越小，道路越堵塞。计算公式如下：

$$
\overline { { \nu _ { i } } } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \nu _ { i }
$$

其中： $\overline { { \nu _ { i } } }$ 为交通流平均速度（ $\mathrm { { K m / h } }$ ； $N$ 为该道路单位时间内所有车辆数； $\nu _ { i }$ 为第 $i$ 辆车的瞬时速度。

交通流密度指在单位时间内一条道路上单位长度上的车辆总数，当道路拥堵时，车辆停滞不前，交通流的变化几乎为零，但是交通密度却非常大，所以对交通拥堵状态有着决定性作用。计算方法如下：

$$
D = { \frac { f } { \nu } }
$$

其中： $D$ 为所求的交通流密度（辆 $/ \mathrm { k m }$ )； $f$ 为每小时监测到的车流量； $\nu$ 为平均速度。

路段饱和度指的是该路段的实际交通流量与最大通行能力的比值，能够反映该道路的实际负荷能力。计算方法如下：

$$
S = { \frac { V } { C } }
$$

其中：S为所求道路饱和度（无量纲)； $V$ 为该道路当前采集的交通流； $C$ 为道路最大通行能力。

# 2 多指标模糊综合评价模型

本文将交通拥堵状态划分为六个等级：1非常畅通、2 畅通、3轻度拥堵、4中度拥堵、5严重拥堵、6锁死。在进行交通拥堵状态分析时，多因素指标下交通拥堵状态等级并没有一个明确的划分界限，是一个模糊的概念，多指标模糊综合评价法可以有效地解决这一问题。

根据美国发行的《道路通行能力手册》中道路服务水平等级的相关研究，结合本文所研究的道路数据，明确了本文采用的三个因素指标对应交通拥堵状况的取值范围，如表1所示。

表1三个因素指标划分交通拥堵等级的取值范围  

<html><body><table><tr><td rowspan="2">各项指标</td><td colspan="5">拥堵等级</td></tr><tr><td>非常畅通</td><td>畅通</td><td>轻度拥堵中度拥堵严重拥堵</td><td></td><td>锁死</td></tr><tr><td></td><td>1</td><td>2</td><td>3 4</td><td>5</td><td>6</td></tr></table></body></html>

<html><body><table><tr><td>平均速度 /km/h</td><td>(60,+oo)</td><td></td><td>(50,60](40,50](30,40](20,30]</td><td></td><td></td><td>[0,20]</td></tr><tr><td>密度/辆/km</td><td>(0,10]</td><td></td><td>(10,20](20,30](30,40](40,50]</td><td></td><td></td><td>(50,+∞)</td></tr><tr><td>路段饱和度</td><td></td><td></td><td></td><td></td><td>(0,0.25] (0.25,0.4](0.4,0.55](0.55,0.7](0.7,0.85] (0.85,1]</td><td></td></tr></table></body></html>

# 2.1建立并确定交通拥堵状态的因素集和评价集

建立交通拥堵状态的因素集 $U = \left\{ u _ { 1 } , u _ { 2 } , \cdots , u _ { i } \right\}$ ， $u _ { i }$ 表示第i个因素指标( $i = 3$ )。本文选取交通流平均速度、交通流密度、道路饱和度三个因素；确定交通拥堵状态的评价（等级）集$V = \left\{ \nu _ { 1 } , \nu _ { 2 } , \cdots , \nu _ { j } \right\}$ ， $\boldsymbol { \nu } _ { j }$ 表示第 $j$ 个等级值。本文将交通拥堵状况划分为六个等级。

# 2.2基于熵值法确定权重系数

熵值法是通过计算熵值来确定各个指标的离散程度。熵值越大，说明该指标的离散程度越小，而对综合分析的作用越小，熵值越小；反之。本文通过对美国加利福尼亚PeMS数据库中各个交通流参数数据进行分析，在每天早上 $6 { : } 0 0 { \sim } 8 { : } 0 0$ 、晚上$1 7 { : } 0 0 { \sim } 1 9 { : } 0 0$ 的这一段时间车流量会随着时间出现明显递增的情况，过了这段时间车流量又会恢复稳定，而平均速度则会出现骤然下降的情况，如图2所示。可以看出交通拥堵状态基本发生在早高峰和晚高峰时段。所以本文采用三个权重系数来对整个道路的交通拥堵状况进行分析，即早高峰、晚高峰和平常时段。

![](images/0d8031f0b8c818752198619eb133a12d9fc518d8c66510bd00bcf8cee7487ccd.jpg)  
2018年3月车辆平均速度和交通流量  
图2车辆平均速度与交通流量

熵值法求权重的步骤如下，首先计算早高峰的因素指标权重系数：

a)选取6:00到8:00时段 $n$ 个表示不同拥堵指数的样本， $m$ 个影响指标，形成原始因素数据矩阵， $x _ { i j }$ 表示的是第 $i$ 个样本的第 $j$ 个影响因素 $( i = 1 , 2 , \cdots , n ; j = 1 , 2 , \cdots , m )$ 。

b）对影响因素进行归一化。

影响因素包含正向因素和负向因素两种。比如速度因素为负向因素，速度越大，拥堵指数越小；速度越小，拥堵指数越大。对于不同的影响因素采取不同的算法进行归一化处理。若不采取归一化，负向因素所求的权重会较小，不能体现出该因素对综合分析的影响。

正向影响因素：

$$
 \dot { x _ { i j } } = \frac { x _ { i j } - \operatorname* { m i n } \left\{ x _ { 1 j } , \cdots , x _ { n j } \right\} } { \operatorname* { m a x } \left\{ x _ { 1 j } , \cdots , x _ { n j } \right\} - \operatorname* { m i n } \left\{ x _ { 1 j } , \cdots , x _ { n j } \right\} }
$$

负向影响因素：

$$
\overset { \cdot } { x _ { i j } } = \frac { \operatorname* { m a x } \left\{ x _ { 1 j } , \cdots , x _ { n j } \right\} - x _ { i j } } { \operatorname* { m a x } \left\{ x _ { 1 j } , \cdots , x _ { n j } \right\} - \operatorname* { m i n } \left\{ x _ { 1 j } , \cdots , x _ { n j } \right\} }
$$

其中： $\dot { \boldsymbol x _ { \dot { i } \dot { j } } }$ 为归一化后的数值。

c）计算第 $i$ 个交通样本的第 $j$ 个因素占该项因素的比重：

$$
p _ { i j } = \frac { x _ { i j } } { \displaystyle \sum _ { i = 1 } ^ { n } x _ { i j } ^ { ' } }
$$

d）计算第 $j$ 项因素的熵值：

$$
e _ { j } = - k \sum _ { i = 1 } ^ { n } p _ { i j } \ln ( p _ { i j } )
$$

其中： $k$ 一般与样本数 $n$ 有关，令 n(n)>0；ln为自然数对数，且 $e _ { j } \geq 0$ 。

e）计算第 $j$ 项因素的差异系数：差异系数越大，说明该因素值对综合分析的作用越大。

$$
g _ { j } = 1 - e _ { j }
$$

f）计算各项因素的权重：

$$
w _ { j } = \frac { g _ { j } } { \displaystyle \sum _ { j } ^ { m } g _ { j } }
$$

同理，可以计算出晚高峰以及其他时段各项因素指标对交通拥堵状态的权重系数，且权重之和 $w _ { 1 } + w _ { 2 } + \cdots + w _ { i } = 1$ 。

# 2.3确定因素指标隶属度

通过隶属函数求得单因素评价矩阵，即对每个因素 $i$ 求得第 $j$ 个等级值的隶属度 $r _ { i j }$ ，这一步是模糊综合评价方法的关键。矩阵如下：

$$
R = { \left( \begin{array} { l } { R _ { 1 } } \\ { R _ { 2 } } \\ { \vdots } \\ { R _ { i } } \end{array} \right) } = { \left( \begin{array} { l l l l } { r _ { 1 1 } } & { r _ { 1 2 } } & { \cdots } & { r _ { 1 j } } \\ { r _ { 2 1 } } & { r _ { 2 2 } } & { \cdots } & { r _ { 2 j } } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { r _ { i 1 } } & { r _ { i 2 } } & { \cdots } & { r _ { i j } } \end{array} \right) }
$$

因为交通拥堵状态对应于每个因素来说，都是在某一区间范围内，并且越靠近范围的临界值，越能说明样本是否属于该状态，所以为了减少主观性，本文采取梯形隶属度函数，对于非常畅通和锁死两种状态非别采用降半梯形隶属度函数和升半隶属度函数。隶属函数图形如图3所示。

隶属度函数的横轴表示的每个交通样本各个因素指标的值，$a , b , . . . , e$ 表示每个因素指标的阈值范围， $k _ { 1 } , k _ { 2 } , . . . , k _ { 1 0 }$ 表示每个因素指标的临近阈值线性取值，纵坐标的0表示因素指标不属于所求拥堵状态，1表示属于。对于交通流密度、道路饱和度两种正向因素指标来说，函数从左到右依次为状态非常畅通、畅通到锁死。由于平均速度是负向指标，从左到右的状态依次为锁死、严重拥堵到非常畅通。

![](images/6cf2b566240026b167993b41c8601d3c2fee891a79b50a3d8756879528cb19b9.jpg)  
图3交通拥堵状态梯形隶属度函数  
图4交通拥堵状态预测系统框图

每个状态的计算公式如下：

状态1:

$$
f _ { 1 } = \left\{ \begin{array} { c } { 0 \quad x \leq k _ { 1 } } \\ { k _ { 2 } - x } \\ { k _ { 2 } - k _ { 1 } } \\ { 1 \quad x \geq k _ { 2 } } \end{array} \right.
$$

状态2、3、4、5：

$$
f _ { i } = \left\{ \begin{array} { l l } { 0 \quad x \leq k _ { i } \ o r \ x \geq k _ { i + 3 } } \\ { \frac { x - k _ { i } } { k _ { i + 1 } - k _ { i } } \quad k _ { i } \times x < k _ { i + 1 } } \\ { 1 \qquad k _ { i + 1 } \leq x \leq k _ { i + 2 } } \\ { \frac { k _ { i + 3 } - x } { k _ { i + 3 } - k _ { i + 2 } } \ k _ { i + 2 } \times x < k _ { i + 3 } } \end{array} \right. ( i = 2 , 3 , 4 , 5 )
$$

状态6:

$$
f _ { 6 } = \left\{ \frac { 0 \quad x \leq k _ { 9 } } { k _ { 1 0 } - k _ { 9 } } \ k _ { 9 } < x < k _ { 1 0 } \right.
$$

# 2.4确定多因素指标下的拥堵级别

通过模糊合成运算求模糊综合评价矩阵：

$$
B = W \circ R = \left\{ \begin{array} { l l } { W _ { \mathfrak { a } } \circ R \quad 6 { : } 0 0 \leq \mathfrak { t } \leq 8 { : } 0 0 } \\ { W _ { \mathfrak { b } } \circ R \ 1 7 { : } 0 0 \leq \mathfrak { t } \leq 1 9 { : } 0 0 = ( \mathfrak { b } _ { 1 } , \mathfrak { b } _ { 2 } , { \cdots } , \mathfrak { b } _ { j } ) } \\ { W _ { \mathfrak { c } } \circ R } \end{array} \right.
$$

其中： ${ \mathbf { } } W _ { a }$ 、 $W _ { b }$ 、 $W _ { c }$ 分别表示一天中早高峰、晚高峰以及其他时间对应于每个因素指标的权重系数。

根据最大隶属度原则，选择模糊综合评价矩阵中隶属度最大值所在的级别为最终的拥堵级别，即 $b = \operatorname* { m a x } \left( b _ { 1 } , b _ { 2 } , \cdots , b _ { j } \right)$ 假如终隶属度最大值为 $b _ { j }$ ，那么该时刻的交通样本所属于的交通级别为 $j$ 0

# 3基于多指标模糊综合评价交通拥堵状态预测

基于模糊综合评价交通拥堵预测系统包括数据参数获取部分、交通拥堵预测部分、交通拥堵指数评价部分三个部分。数据参数获取部分主要是 $t$ 时刻和 $t - i$ 时刻的交通流（ $F ( t )$ 、$F ( t - i ) )$ ； $t$ 时刻和 $t - i$ 时刻的平均速度 $\left( V ( \operatorname { t } ) , \ V ( t - i ) \right)$ 的获得；交通拥堵预测部分主要包括交通流参数的预测。本文选取粒子群优算法（PSO）优化支持向量机（SVR）的方法对交通流、平均速度两个参数进行预测。该方法主要是利用已有的当前时刻 $t$ 以及历史时刻 $t - i$ 的数据来预测未来时刻 $t + i$ 的数据。根据文中提到的公式，通过预测出的交通流参数计算出本文模糊综合评价法中所需要的密度D和道路饱和度S两种因素指标；交通拥堵指数评价部分则是通过熵值法和模糊综合评价法来获得最终的交通拥堵状态。系统框架如图4所示。

交通数据获取参数提取 数据提取部分F(t) F(t-i) V(t-i) V(t)PSO-SVR预测 交通拥堵预测部分F(t+i) V(t+i)S(t+i) D(t+i) V(t+i)  
交通多因素指标模糊综合评价别划分 非常畅 轻度拥 中度拥 严 交通拥堵指数评价部分畅 重 锁通 拥 死  
通 堵 堵 堵2 3 4 5 6

# 4 实验分析

# 4.1交通流参数预测部分

本文选取美国加利福尼亚PeMS系统数据库中标号为I405这条高速路的交通流数据进行实验分析，选取的时间为2018年3月1日一2018年3月4日，数据采样周期为 $5 \mathrm { m i n }$ ，共1152个数据点。

首先对本文模糊综合评价中所需要的平均速度和交通流量进行预测。根据PSO-SVR预测模型的要求，需要两类样本集，第一类是训练样本，用来训练SVR模型，通过PSO不断地对其参数寻优，训练出最优的预测模型；第二类是测试样本，用来检验训练完成的模型是否有较高的预测能力。其中前三天的交通流作为PSO-SVR预测模型的训练数据，最后一天的交通流作为PSO-SVR模型的测试数据。总共有864个训练数据，288个测试数据。在进行预测之前，需要对数据进行归一化，将数据归一化在[0,1]间,预测之后再进行反归一化。这样可以有效地缩短运算时间，且提高了规范度。本文采用的是基于极值的归一化，公式如下：

$$
X ^ { \prime } = \frac { X - X _ { \operatorname* { m i n } } } { X _ { \operatorname* { m a x } } - X _ { \operatorname* { m i n } } }
$$

其中： $X _ { \operatorname* { m i n } }$ 、 $X _ { \mathrm { m a x } }$ 为训练样本的最小值、最大值。

对于PSO-SVR交通流量预测模型的建立，确定当前t时刻，将训练样本中t、t-1、t-2时刻的交通流与平均速度即 $F ( t )$ 、

$F ( t - 1 )$ 、 $F ( t - 2 )$ 、V(t)、 $V ( t - 1 )$ 、 $V ( t - 2 )$ 作为模型训练集输入，将 $t + 1$ 时刻的交通流 $F ( t + 1 )$ 作为模型训练集输出。通过PSO优化算法获得SVR中惩罚因子c和核函数参数g的最优值，从而找到支持向量并得到预测函数。最后将测试集t、t-1、$t - 2$ 时刻的交通流与平均速度作为测试集的输入，通过预测函数去预测 $_ { t + 1 }$ 时刻的交通流。

同理，平均速度的预测，只需将模型输出改为平均速度即可。

通过PSO-SVR预测得到的交通流和平均速度结果如图5(a)和6(a)所示。

![](images/5874903c194a0e891e2b495f45f1b0f994cd620d32a0c534d799629d7cafdd37.jpg)  
图5PSO-SVR的交通流量预测结果

![](images/6d813172457449a78d112589a1ee345eadadd41d3fce00432bb671b0268b7a12.jpg)  
图6PSO-SVR的平均速度预测结果

由图5(a)和6(a)可以看出，无论在训练集还是测试集上，预测的交通流参数都基本与实际值吻合，为了更直观地体现预测结果的准确性，本文选取了评价指标均方误差（mean squareerror,MSE)和平均绝对百分比误差（mean absolute percent error,MAPE）来进行预测结果的分析。相应的公式如下：

$$
M S E = m e a n ( e _ { t } ^ { \ 2 } )
$$

$$
M A P E = m e a n ( \left| p _ { t } \right| )
$$

其中： $e _ { t } = y _ { t } - y _ { t }$ 为模型的误差； $y _ { t }$ 实际值； $y _ { t }$ 为预测值;$p _ { t } = { \displaystyle \sqrt [ 1 0 0 e _ { t } ] { \xi _ { y _ { t } } } }$ 对应的MSE误差直方图如图5(b)和6(b)所示，且交通流和平均速度的MSE和MAPE分别为36.8951、 $1 4 . 4 8 8 ~ 2 \%$ 和21.6691、 $9 . 7 3 8 ~ 7 \%$ 。

根据美国《道路通行能力手册》，车辆的设计速度在 $7 5 \mathrm { k m / h }$ 的多车道高速公路最大道路通行能力是 $2 2 0 0 \mathrm { p c u / h / \Omega }$ 车道。由于数据的采样周期为 $5 \mathrm { m i n }$ ，所以单车道最大通行能力为 $1 8 0 \mathrm { P C U }$ 。因此根据交通流和平均速度的预测值通过式(2)(3)可计算出模糊综合评价所需要的因素指标交通流密度D和道路饱和度S。

# 4.2交通拥堵级别评价部分

根据文中提到模糊综合评价法的步骤，首先建立交通拥堵指数的因素集和评价（等级）集，通过熵值法确定三个因素指标对应的早高峰、晚高峰和其他时段的权重系数，通过计算得出早高峰 $W _ { a } = [ 0 . 2 2 7 3 , 0 . 5 7 8 8 , 0 . 1 9 3 8 ]$ ，晚高峰

Wb =[0.2926,0.5351,0.1723] ，其他时段$W _ { c } = [ 0 . 1 6 7 6 , 0 . 4 5 3 0 , 0 . 3 7 9 4 ]$ ,通过表1所示的三个交通因素指标的取值范围划分确定梯形隶属度函数，得出每个因素指标的隶属度；最后根据隶属度最大原则确定交通拥堵级别，从而得到预测的交通拥堵状态。交通拥堵级别预测值与实际值的对比如图7所示。

![](images/19921c7bdefaecb635cca562c285213692de2c80dc5182665408380a6ade2996.jpg)  
图7交通拥堵状态预测值与实际值的对比

图中各个等级分别为1非常畅通、2畅通、3轻度拥堵、4中度拥堵、5严重拥堵、6锁死。由图可得，本文提出的多指标模糊综合评价法可以准确地根据多个指标对交通拥堵状态的不同影响计算出最终的拥堵级别，根据预测值分析的交通拥堵级别基本与实际拥堵级别相吻合，大致走势相同，可以看出在早高峰时段，拥堵级别明显上升，出现锁死的情况；在早高峰过后有明显缓和；晚高峰整体的拥堵情况比早高峰稍轻一些。所预测的数据点为288个，仅有15个时间点的拥堵级别不相符，准确率可达 $9 4 . 7 9 \%$ 。

# 5 结束语

本文提出了一种多指标模糊综合评价对交通拥堵状态预测与评估的方法，该方法考虑到早高峰、晚高峰以及其他时段下交通流参数对交通拥堵状态的不同影响和单因素指标无法准确表征交通拥堵状态的问题，通过熵值法确定不同时段下各个因素指标的权重系数，并将三个因素指标输入到多指标模糊综合评价模型中，使得模糊综合评价的结果更加准确。预测部分使用PSO来优化SVR，使得两个交通流参数的预测值与实际值误差更小。通过对美国加州交通数据进行预测评价实验，将预测出的平均速度与交通流量用于多指标模糊综合评价方法来进行交通拥堵级别预测，可以看出本文提出的方法预测出的交通拥堵状态与实际状态吻合较好，准确率可达 $9 4 . 7 9 \%$ 。

# 参考文献：

[1]美国交通研究委员会.道路通行能力手册[M].任福田，刘小明，荣建, 等译．北京：人民交通出版社，2007:116-189.(Transportation Research Board.Highway capacity manual [M]. Trans.Ren Futian,Liu Xiaoming, Rong Jian,et al. Beijing: China Communication Press,20o7: 116-189.)   
[2]北京交通发展研究院[EB/OL].[2018-06-01].htp://www.bjtrc.org. cn/S IndexPage.aspx. (Beijing Transport Institute [EB/OL].[2018-06-01]. http://www.bjtrc.org.cn/S IndexPage.aspx.)   
[3]Shi W,Liu Y. Real-time urban trafic monitoring with global positioning system-equipped vehicles [J].IET Intelligent Transport Systems,2010,4 (2): 113-120.   
[4]Castro P S,Zhang Daqing,Li Shijian.Urban traffic modeling and prediction using large scale taxi GPS traces [C]// Proc of the 10 th International Conference on Pervasive Computing.Newcastle,UK: [s. n.], 2012:57-72.   
[5]杨俊瑛．城市道路交通拥挤状态判别及预测[D].成都：西南交通大学, 2014.(Yang Junying. Study on the identification and prediction of the traffic congestion state for urban road [D]. Chengtu: Southwest Jiaotong University,2014.)   
[6]龙小强，谭云龙．基于模糊综合评价的城市道路交通拥堵评价研究[J]. 交通标准化,201l(11):114-117.(Long Xiaoqiang,Tan Yunlong.Urban traffic congestion evaluation based on fuzzy comprehensive evaluation [J]. Transport Standardize,201l (11): 114-117.) [7]谭娟，王胜春．基于深度学习的交通拥堵预测模型研究[J].计算机应 用研究,2015 (10): 2951-2954.(Tan Juan,Wang Shengchun.Research on prediction model for traffic congestion based on deep learning [J]. Application Research of Computers,2015 (10):2951-2954.) [8]黎符忠．基于灰色关联模型的城市道路交通拥堵评价研究[J].重庆建 筑，2018 (17):38-40.(Li Fuzhong.Urban road traffic congestion evaluation based on grey correlation model [J]. Chongqing Architecture,   
2018(17):38-40.) [9] 黄大荣，柴彦冲，赵玲，等.考虑多源不确定信息的路网交通拥堵状态 辨识方法 [J]．自动化学报,2018,44(3):533-544.(Huang Darong,Chai Yanchong,Zhao Ling,et al. Traffic congestion status identification method forroad network with multi-source uncertain information [J].Acta Automatica Sinica,2018,44(3): 533-544.) [10] Sun Zhanquan，Geoffrey Fox. Traffic flow forecasting based on combination of multidimensional scaling and SVM [J]. International Journal of Intelligent Transportation Systems Research,2014,12 (1):   
20-25. [11]田瑞杰，张维石，翟华伟．基于时间序列与BP-ANN的短时交通流速度 预测模型研究[J/OL].计算机应用研究，2019,36(11）．[2018-08-10]. http://www.arocmag.com/article/O2.(Tian Ruijie,Zhang Weishi,Zhai Huawei. Short-term traffic flow velocity prediction model based on time series and BP-ANN[J/OL].Application Research of Computers,2019,36 (11).[2018-08-10]. http://www.arocmag.com/article/02.)   
[12] Hong W C,Dong Yucheng, Zheng Feifeng,et al. Forecasting urban trafic flow by SVR with continuous ACO [J]. Applied Mathematical Modelling, 2011,35 (3):1282-1291.   
[13]罗向龙，焦琴琴，朱力瑶，等．基于深度学习的短时交通流预测[J]. 计算机应用研究,2017,34(1):91-97.(Luo Xianglong,Jiao Qinqin,Zhu Liyao,et al. Short-term trafic flow prediction based on deep learning [J]. Application Research ofComputers,2017,34(1):91-97.)   
[14] Chen Xiaobo,Yang Jian,Liang Jun.A flexible support vector machine for regression [J]. Neural Computing and Applications，2012,21 (8): 2005-2013.   
[15]祝付玲．城市道路交通拥堵评价指标体系研究[D].南京：东南大学, 2007.(Zhu Fuling. Study on the evaluation index system of urban road traffic congestion [D]. Nanjing: Southeast University,2007.)