# ARIMA和ANN模型的于旱预测适用性研究

杨慧荣}，张玉虎²，崔恒建'，高峰²，陈秋华1（1首都师范大学数学科学学院,北京100048；2 首都师范大学资源环境与旅游学院,北京100048）

摘要：开展干旱预测是有效应对干旱风险的前提基础，根据1960—2016年三江平原7个站点逐日降水和气温数据，利用ARIMA和ANN模型对不同时间尺度标准化降水蒸散指数(SPEI)序列进行分析建模预测。借助相关系数 $R$ 、纳什效率系数NSE、Kendall秩相关系数 $\boldsymbol { \tau }$ 、均方误差MSE和Kolmogorov-Smirmov（K-S）检验对模型的有效性进行了判定，然后分别用ARIMA和ANN模型进行12步预测,并将预测值与实际值进行比较。结果表明：（1）ARIMA模型和ANN模型对 SPEI的预测能力都随时间尺度的增加而逐渐提高。（2）两种模型对3、6个月尺度SPEI的预测精度偏低，9、12、24个月的SPEI的预测精度在 $70 \%$ 以上；（3）SPEI-9、SPEI-12、SPEI-24三个时间尺度ANN模型的预测精度优于ARIMA模型。

关键词：干旱；ARIMA模型；ANN模型； $S P E I \mathrm { s }$ ；三江平原中图分类号：X4 文献标识码：A 文章编号：

干旱是人类面临的主要自然灾害之一，而我国几乎每年都会发生，平均2～3a就会发生一次严重的干旱灾害[1-2]。加强干旱监测、预测方面的研究对相关部门预防干旱灾害、减少干旱灾害损失具有重要的意义[3-5]。目前用以预测干旱的方法有很多，如人工神经网络（ANN)模型、差分自回归移动平均（ARIMA)模型、支持向量机（SVM)等。其中，ARIMA模型作为传统的时间序列模型,应用最普遍,应用范围比较广泛，如韩萍等[通过对关中地区多尺度标准化降水指数的ARIMA建模，指出该模型在干旱预测方面具有良好的效果，ZHANGY和LIW[7]利用ARIMA等模型对中国海河北系的干旱情况进行了预测分析，说明了ARIMA模型具有较为优良的预测精度。ANN模型作为处理非线性问题的典型模型，受到了众多学者的青睐，也越来越多的被运用到各领域的预测中[8-1]。其中在干旱预测领域,BARUA等[12]为提高水资源管理效率，利用ANN神经网络对干旱进行了预测，BELAYNEH等[13]利用ANN模型在阿瓦什河流域对 SPI指数进行了分析建模，二者都证明了ANN模型预测精度的优良性，罗明美[14 利用ANN人工神经网络对淮河流域土壤水分进行反演研究，指出该模型对淮河流域的干旱监测具有良好的使用价值与应用前景

干旱程度常利用干旱指数进行定量评价[15]国内外常用的分析指数有：Palmer干旱指数（PD-SI)、标准化降水指数（SPI）、综合气象干旱指数(CI)、标准化降水蒸散指数（SPEI)等。SPEI融合了SPI计算简单及多时间尺度的特性和PDSI对蒸散需求变化的灵敏性等方面的优点，是表征干旱程度的理想工具[16-17]。SPEI具有多个时间尺度属性，如3个月时间尺度的SPEI和季节降水估计相关性较高;12个月时间尺度的SPEI对于下层土壤水分和河流径流量等有较好的反映;24个月时间尺度的SPEI可以更深入地涉及到地下水位、水库蓄水量及民生问题[17]。SPEI多时间尺度的特征使其在干旱分析、评估等领域被广泛使用[18-19] ○

目前的文献大多以年或某一月份时间尺度的SPEI为研究对象，而关于模型对不同时间尺度SPEI的适用性研究却鲜见。鉴于此,本文应用三江平原1960一2016年7个气象台站的常规气象观测资料，以不同时间尺度(3个月、6个月、12个月、24个月）的SPEI为基础，研究比较ARIMA和ANN模型在干旱预测中的适用性，并对预测能力进行了评价分析，以期能为三江平原的抗旱减灾工作提供一定的依据。

# 1 研究方法

# 1.1 ARIMA模型

ARIMA模型于1976年由BOX 等提出，是处理时间序列的最普遍、最直接的建模方法，也是对时间序列进行预测的科学方法。它将预测对象随时间变化形成的序列看作是一个随机序列，即时间序列依赖于时间 $\mathbf { \chi } _ { t }$ 的一组随机变量。其中，单个序列值出现具有不确定性，但整个序列的变化则呈现出一定的规律性，可以用相应的数学模型加以近似描述，这就是 ARMA 模型的基本思想[20]。ARMA 模型有三种类型：自回归（AR)模型、移动平均(MA)模型以及自回归移动平均(ARMA)模型。只有平稳的时间序列才能够直接建立ARMA模型，现实中常见的时间序列多具有某种趋势，但往往通过差分可使其满足平稳性要求。然后则可以建立ARMA模型，即ARIMA模型。通常，经过 $d$ 次差分后的ARMA模型方程由下式表示：

$$
\begin{array} { c } { { Y _ { \iota } = \varphi _ { 1 } Y _ { \iota - 1 } + \varphi _ { 2 } Y _ { \iota - 2 } + { \cdots } { \varphi _ { p } } Y _ { \iota - p } + e _ { \iota } - \theta _ { 1 } e _ { \iota - 1 } - } } \\ { { { } } } \\ { { \theta _ { 2 } e _ { \iota - 2 } - { \cdots } \theta _ { q } e _ { \iota - q } } } \end{array}
$$

记作ARIMA $( p , d , q )$ 。

若引进延迟算子 $B$ ,则ARIMA $( p , d , q )$ 方程可简记为

$$
\varphi _ { p } ( B ) \ \nabla ^ { d } Y _ { t } = \theta _ { q } ( B ) e _ { t }
$$

其中，

$$
\varphi _ { p } ( B ) = 1 - \varphi _ { 1 } B - \varphi _ { 2 } B ^ { 2 } - \cdots \varphi _ { p } B ^ { p }
$$

$$
\theta _ { q } ( B ) = 1 - \theta _ { 1 } B - \theta _ { 2 } B ^ { 2 } - \cdots \theta _ { q } B ^ { q }
$$

$Y _ { _ t }$ 为时间序列值; $\varphi _ { i } ( i = 1 , 2 , \cdots , p )$ 和 $\theta _ { j } \left( j = 1 , 2 \right.$ $\cdots , q )$ 分别为自回归系数和滑动平均系数； $\boldsymbol { e } _ { t }$ 为白噪声序列,且 $e _ { t } \sim N ( 0 , \sigma ^ { 2 } )$ 。

本文将1960一2005 年的数据作为训练数据，由数据序列的自相关图和偏自相关图确定阶数 $p$ 和 $q$ 的取值范围，然后根据AIC准则对 $p$ 和 $q$ 进行优选，即在不同 $p$ 和 $q$ 组合的模型中，选择最小的AIC 值所对应的参数，从而得到最优ARIMA模型。然后利用2006一2015年的数据对选定的最优模型进行预测验证，最后向前预测了2016 年的 SPEI值并将其与实际值进行比较。这一过程在R语言平台实现。

# 1.2 ANN模型

ANN人工神经网络是一种模仿动物神经网络行为特征进行分布式并行信息处理的算法，按是否含有延迟或反馈环节可以分为静态神经网络和动态神经网络。静态神经网络是无反馈、无记忆的，输出仅依赖于当前的输入，例如BP神经网络和RBF神经网络;动态神经网络[21]是带有反馈的,其输出不仅依赖当前的输入，而且依赖之前的输入，通过反馈，神经网络能将前一时刻的数据保留，使其加入到下一时刻数据的计算，使网络不仅具有动态性，而且保留的系统信息也更加完整。动态神经网络具有很强的学习能力和逼近任意函数的特点，在计算效率和预测精度等方面都优于静态神经网络。自20世纪80年代末以来，动态神经网络作为一种崭新的非线性模型被广泛地用于变形预报、模式识别、最优化决策等方面[22]。因此，本文选择动态神经网络（NAR回归神经网络)进行SPEI时间序列预测。

NAR神经网络模型可以表示为：

$$
y ( t ) = f ( y ( t - 1 ) , y ( t - 2 ) , \cdots , y ( t - d ) )
$$

式中： $d$ 为延时阶数； $f ( \mathbf { \partial } \cdot \mathbf { \partial } )$ 为神经网络模型，可以看出 $y ( t )$ 值是由 $y ( t - 1 ) , y ( t - 2 ) , \cdots , y ( t - d )$ 的值所决定的。表明该模型用历史的数据值来推断当前及未来的数据值，具有动态性和延展性。

NAR动态神经网络模型的训练方法通常使用Levenberg-Marquardt算法,因其训练速度极快，对于中小型网络而言，此训练算法是最好的算法。LM算法的计算公式为：

$$
X _ { k + 1 } = X _ { k } - ( J ^ { T } J + u I ) \ ^ { - 1 } J ^ { T } e
$$

式中： $X _ { k } \setminus X _ { k + 1 }$ 分别是第 $k , k + 1$ 次迭代的网络权值;$J$ 为雅可比矩阵； $I$ 为单位矩阵； $u$ 为神经网络学习率； $e$ 为随机误差。

本部分将1960—2015年数据划分为三类：训练数据、验证数据和测试数据，比例设置为： $70 \%$ 、$1 5 \%$ ） $1 5 \%$ ，之后设置神经元个数、延迟阶数等参数，并通过调节参数判断误差，使得Autocorrelation在满意值范围内，筛选出相对最优的网络模型，然后利用训练成功后的模型，预测2016年的12个值。这一过程通过Matlab软件实现。

# 1.3标准化降水蒸散指数(SPEI)

采用具有多时间尺度特征的SPEI作为气候干

湿状况的表征。该指数计算原理简单易行，即通过衡量降水量和潜在蒸散量差值偏离平均状态的程度来判定干湿状况[18,23]。具体计算步骤如下：

（1）计算潜在蒸散（PET），本文采用的是Thormthwaite 方法[24]

$$
P E T = 1 6 K \times { \bigg ( } { \frac { 1 0 T _ { i } } { H } } { \bigg ) } ^ { A }
$$

式中： $K$ 为根据纬度计算的修正系数； $T$ 为月平均温度； $H$ 为年热量指数； $A$ 为以 $H$ 为基础的系数。

（2）计算逐月降水与蒸散的差值：

$$
D _ { i } = P _ { i } - P E T _ { i }
$$

式中： $\boldsymbol { P } _ { i }$ 为逐月降水量; $\mathit { P E T } _ { i }$ 为月潜在蒸散发量（204 $\left( { \bf m m } \right)$ 。

（3）采用3个参数的log-logistic 概率分布拟合所构建的数据序列 $D _ { i }$ ：

$$
F ( x ) = { \biggl [ } 1 + { \biggl ( } { \frac { \alpha } { x - \gamma } } { \biggr ) } ^ { \beta } { \biggr ] } ^ { - 1 }
$$

其中,参数 $\alpha \mathcal { \beta } _ { \setminus } \gamma$ 采用L—矩估计方法获得：

$$
\alpha = \frac { ( \omega _ { 0 } - 2 \omega _ { 1 } ) \beta } { \Gamma ( 1 + 1 / \beta ) \Gamma ( 1 + 1 / \beta ) }
$$

$$
\beta = \frac { 2 \omega _ { 1 } - \omega _ { 0 } } { 6 \omega _ { 1 } - \omega _ { 0 } - 6 \omega _ { 2 } }
$$

$$
\gamma = \omega _ { 0 } - \alpha \Gamma ( 1 + 1 / \beta ) \Gamma ( 1 - 1 / \beta )
$$

其中， $\Gamma$ 为阶乘函数， $\omega _ { 0 } \lrcorner \omega _ { 1 } \lrcorner \omega _ { 2 }$ 为数据序列 $D _ { i }$ 的概率加权矩，计算方法如下：

$$
\omega _ { s } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \bigg ( 1 - \frac { i - 0 . 3 5 } { N } \bigg ) ^ { s } D _ { t }
$$

式中： $N$ 为参与计算的月份个数。

（4）对累积概率密度进行标准化，获取相应的SPEI值:

$$
P = 1 - F { \bigl ( } x { \bigr ) }
$$

当 $P { \leqslant } 0 . 5$ 时，

$$
W = \sqrt { - 2 \mathrm { l n } P }
$$

$$
S P E I = W - \frac { c _ { 0 } + c _ { 1 } W + c _ { 2 } W ^ { 2 } } { 1 + d _ { 1 } W + d _ { 2 } W ^ { 2 } + d _ { 3 } W ^ { 3 } }
$$

式中： $\cdot c _ { 0 } = 2 . 5 1 5 5 1 7 , c _ { 1 } = 0 . 8 0 2 8 5 3 , c _ { 2 } = 0 . 0 1 0 3 2 8$ $d _ { 1 } = 1 . 4 3 2 \ 7 8 8 , d _ { 2 } = 0 . \ 1 8 9 \ 2 6 9 , d _ { 3 } = 0 . \ 0 0 1 \ 3 0 8 ,$ 。当$P > 0 . 5$ 时，本文通过划分 $S P E I$ 的等级来表征干旱情况[25],如表1。

表1SPEI干旱等级的标准划分表Tab.1Drought classifcation of SPEI  

<html><body><table><tr><td>SPEI数值</td><td>干旱等级</td></tr><tr><td>-0.5<SPEI≤0.5</td><td>无旱</td></tr><tr><td>-1.0<SPEI≤-0.5</td><td>轻微干旱</td></tr><tr><td>-1.5<SPEI≤-1.0</td><td>中度干旱</td></tr><tr><td>-2.0<SPEI≤-1.5</td><td>严重干旱</td></tr><tr><td>SPEI≤-2.0</td><td>极端干旱</td></tr></table></body></html>

$$
W = \sqrt { - 2 \mathrm { l n } ( 1 - P ) }
$$

$$
S P E I = \frac { c _ { 0 } + c _ { 1 } W + c _ { 2 } W ^ { 2 } } { 1 + d _ { 1 } W + d _ { 2 } W ^ { 2 } + d _ { 3 } W ^ { 3 } } - W
$$

# 1.4 评价验证指标

1.4.1 相关系数 $( R )$

$$
R = \frac { \sum _ { i = 1 } ^ { N } \left( y _ { i } - \bar { y } \right) \left( \hat { \gamma } _ { i } - \bar { \hat { y } } \right) } { \sqrt { \sum _ { i = 1 } ^ { N } \left( y _ { i } - \bar { y } \right) ^ { 2 } \sum _ { i = 1 } ^ { N } \left( \hat { \gamma } _ { i } - \bar { \hat { y } } \right) ^ { 2 } } }
$$

其中,

$$
\begin{array} { c } { \displaystyle { \bar { y } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } y _ { i } } } \\ { \displaystyle { \bar { \hat { y } } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \hat { y } _ { i } } } \end{array}
$$

式中： $y _ { i }$ 是观测值； $\hat { \boldsymbol y } _ { i }$ 是预测值, $- 1 \leqslant R \leqslant 1$ 。 $R$ 值越趋近于1，则说明预测值与观测值之间拟合越好。

# 1.4.2 Nash-Sutcliffe 系数（NSE)

$$
N S E = 1 - \frac { \sum _ { i = 1 } ^ { N } ( y _ { i } - \hat { y } _ { i } ) ^ { 2 } } { \sum _ { i = 1 } ^ { N } ( y _ { i } - \bar { y } ) ^ { 2 } }
$$

NSE一般用以验证水文模型模拟结果的好坏，取值为负无穷至1。NSE接近1，表示模拟质量好，模型可信度高；NSE接近0，表示模拟结果接近观测值的平均值水平，即总体结果可信，但过程模拟误差大； $N S E$ 远远小于0，则模型是不可信的。

# 1. 4.3 均方误差（MSE)

$$
M S E = \frac { 1 } { N } { \sum _ { i = 1 } ^ { N } { { { \left( { { y } _ { i } } - { \hat { y } } _ { i } \right)}  } ^ { 2 } } }
$$

MSE越接近于0，表示两样本（预测值与观测值)的接近程度越高。

1.4.4Kendall秩相关系数 $( \pmb { \tau } )$ Kendall秩相关系数是一种非参数检验方法，该方法利用两组样本（观测值与预测值)之间秩的关系反映二者之间的相关程度[7]。假设两组样本为 $X _ { i } \setminus Y _ { i } , 1 \leqslant i \leqslant N$ ，当 $i$

$\neq j$ 时,令

$$
\varphi ( X _ { i } , X _ { j } , Y _ { i } , Y _ { j } ) = \left\{ \begin{array} { l l } { 1 } & { \left( X _ { i } - X _ { j } \right) \left( Y _ { i } - Y _ { j } \right) > 0 } \\ { 0 } & { \left( X _ { i } - X _ { j } \right) \left( Y _ { i } - Y _ { j } \right) = 0 } \\ { - 1 } & { \left( X _ { i } - X _ { j } \right) \left( Y _ { i } - Y _ { j } \right) < 0 } \end{array} \right.
$$

则，

$$
\tau = \frac { { \underset { \substack { 1 \leqslant i < j \leqslant N } } { \sum _ { i \leqslant j \leqslant N } } } \varphi ( X _ { i } , X _ { j } , Y _ { i } , Y _ { j } ) } { N ( N - 1 ) / 2 }
$$

$\cdot$ 越接近1，说明预测值与观测值之间拟合越好，二者之间相关程度越高。

1.4.5Kolmogorov-Smirnov（K-S）检验本文中采用两样本K-S检验，该方法基于累计分布函数，用以检验两个样本的经验分布是否相同，是统计学中一种非常重要的非参数检验方法。K-S统计量的计算方法为：

$$
D _ { \mathfrak { n } , \mathfrak { m } } = \operatorname* { s u p } _ { \mathfrak { x } } \vert \mathrm { F } _ { 1 , \mathfrak { n } } \left( \mathfrak { x } \right) - \mathrm { F } _ { 2 , \mathfrak { m } } \left( \mathfrak { x } \right) \vert
$$

式中： $\operatorname { F } _ { 1 , n }$ 和 $\mathrm { F } _ { 2 , m }$ 分别表示两样本的经验分布函数;sup 为上确界函数。在置信水平 $\propto$ 上,若

$$
D _ { n , m } > c ( \alpha ) { \sqrt { \frac { n + m } { n m } } }
$$

则拒绝原假设。式（26）、（27）中， $m , n$ 分别为两样本的样本容量。表 $2 ^ { [ 2 6 ] }$ 给出了常用的置信水平 $\alpha$ 及其所对应的 $c ( \alpha )$ ：

本文使用R语言实现K-S检验，结果给出D统计量及其相应的 $p$ 值。 $D$ 值是两个经验样本之间的绝对最大距离，称之为K-S距离。 $D$ 值越接近0，说明两个样本来自同一分布的可能性越大。

Tab.2 Value of $\pmb { c } ( \pmb { \alpha } )$ for each level of $\pmb { \alpha }$   

<html><body><table><tr><td>α</td><td>0.10</td><td>0.05</td><td>0.025</td><td>0.01</td><td>0.005</td><td>0.001</td></tr><tr><td>c(α)</td><td>1.22</td><td>1.36</td><td>1.48</td><td>1.63</td><td>1.73</td><td>1.95</td></tr></table></body></html>

# 2 实例应用

# 2.1 研究区概况

三江平原（ $( 4 5 ^ { \circ } 0 1 ^ { \prime } \sim 4 8 ^ { \circ } 2 7 ^ { \prime } 5 6 ^ { \prime \prime } \mathrm { ~ N ~ }$ ， $1 3 0 ^ { \circ } 1 3 ^ { \prime }$ \~$1 3 5 ^ { \circ } 0 5 ^ { \prime } 2 6 ^ { \prime \prime } \mathrm { ~ E ~ }$ ,图1)，即东北平原东北部,位于中国东北角，西起小兴安岭东南端，东至乌苏里江，北自黑龙江畔,南抵兴凯湖,总面积 $5 . 1 3 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 。三

![](images/df3c7897d81a356d0549b9a9d69fbe8dd07e9b28b01d566c48ce5eee064035f0.jpg)  
图1研究区及气象站位置  
Fig.1Study area and the location of meteorological stations

江平原属温带湿润、半湿润大陆性季风气候，全年日照时数 $2 ~ 4 0 0 \sim 2 ~ 5 0 0 ~ \mathrm { h } , 1$ 月均温 $- 2 1 \sim - 1 8 \ \mathrm { ~ \textdegree C } \ , 7$ 月均温 $2 1 \sim 2 2 ~ \mathrm { \textdegree C }$ 。年降水量 $5 0 0 \sim 6 5 0 \ \mathrm { m m } , 7 5 \% \sim$ $8 5 \%$ 集中在6\~9月，雨热同季，适于农业尤其是优质水稻和高油大豆的生长。尽管三江平原水利工程设施不断完善，但水旱灾害却有所加重，特别是自2000 年以来，干旱频发，由于降水量持续减少，已经接近或者突破历史极值，造成了各种农作物的减产[27-28]  
。

# 2.2 数据资料

本文所采用的数据来源于中国气象数据网（http://data.cma.cn），选取了三江平原7个国家基准气象站点（表3)1960—2016年的逐日降水（单位：$0 . 1 \ \mathrm { m m }$ )和气温（单位： $\mathcal { \mathbf { C } }$ )等数据资料，并对数据进行了严格的修订和质量控制，包括采用其相邻站点同期数据插值进行错误数据的订正和遗失数据补漏及筛选并剔除无效数据[29],确保数据的采集时间连续、完整，数据的实有率和正确率均接近 $100 \%$ ，满足研究要求的精度。

表2置信水平 $\pmb { \alpha }$ 及其对应的 $\mathbf { \nabla } _ { c \left( \alpha \right) }$   
表3气象站信息  
Tab.3Information of meteorological stations   

<html><body><table><tr><td>站台 编号</td><td>站名</td><td>经度 /E</td><td>纬度 /N</td><td>海拔 /m</td><td>年平均降 水／mm</td><td>年平均 气温/℃</td></tr><tr><td>50775</td><td>鹤岗</td><td>130.30</td><td>47.33</td><td>227.90</td><td>640.00</td><td>2.80</td></tr><tr><td>50788</td><td>富锦</td><td>132.02</td><td>47.23</td><td>66.40</td><td>339.50</td><td>3.60</td></tr><tr><td>50873</td><td>佳木斯</td><td>130.35</td><td>46.83</td><td>81.20</td><td>527.00</td><td>3.00</td></tr><tr><td>50877</td><td>依兰</td><td>129.55</td><td>46.33</td><td>100.10</td><td>555.60</td><td>3.30</td></tr><tr><td>50888</td><td>宝清</td><td>132.17</td><td>46.33</td><td>83.00</td><td>548.60</td><td>3.20</td></tr><tr><td>50978</td><td>鸡西</td><td>130.97</td><td>45.30</td><td>280.80</td><td>535.00</td><td>3.80</td></tr><tr><td>50983</td><td>虎林</td><td>133.97</td><td>45.75</td><td>100.20</td><td>566.20</td><td>3.50</td></tr></table></body></html>

# 2.3 结果分析

表5ANN模型拟合度评价 Tab.5ANN model fitting evaluation

<html><body><table><tr><td colspan="7">的拟合情况有相似的结果。对于3个月尺度和6个 月尺度,ARIMA和ANN模型拟合的各站点的相关</td><td></td><td>鸡西 虎林 鹤岗 0.756</td><td>0.615 0.617</td><td>0.379 0.380</td><td>0.601 0.605</td><td>0.431 0.418</td><td>0.147 0.159</td></tr><tr><td colspan="7">系数均在0.6附近,NSE则都低于0.5，说明ARIMA 和ANN模型不能有效反映3个月和6个月尺度</td><td></td><td>富锦 佳木斯</td><td>0.769</td><td>0.572 0.591</td><td>0.414 0.396</td><td>0.567 0.114 0.577 0.110</td></tr><tr><td></td><td></td><td>表4ARIMA 模型拟合度评价</td><td></td><td></td><td></td><td>依兰</td><td>0.744 0.742</td><td>0.554 0.551</td><td>0.431</td><td>0.553</td><td>0.103 0.127</td></tr><tr><td></td><td>Tab.4</td><td></td><td></td><td></td><td></td><td>宝清</td><td>0.761</td><td>0.579</td><td></td><td>0.435 0.409</td><td>0.546 0.559 0.102</td></tr><tr><td>尺度 站名</td><td></td><td></td><td></td><td>ARIMA model fitting evaluation</td><td>9</td><td>鸡西 虎林</td><td>0.740 0.756</td><td>0.548 0.571</td><td>0.436 0.417</td><td>0.550 0.559</td><td>0.105</td></tr><tr><td>3</td><td></td><td>R NSE</td><td>MSE</td><td>Kendallr</td><td></td><td>鹤岗</td><td>0.86</td><td>0.699</td><td></td><td>0.69</td><td>0.107</td></tr><tr><td></td><td>鹤岗</td><td>0.633</td><td>0.401</td><td>0.581</td><td>0.449 0.152</td><td></td><td></td><td></td><td></td><td>0.29</td><td>0.081</td></tr><tr><td></td><td>富锦</td><td>0.648</td><td>0.420</td><td>0.564 0.467</td><td>0.131</td><td>佳木斯 依兰</td><td>0.839</td><td>0.703</td><td>0.285</td><td>0.655</td><td>0.092</td></tr><tr><td></td><td>佳木斯</td><td>0.647</td><td>0.418</td><td>0.564 0.462</td><td>0.142</td><td>宝清</td><td>0.861</td><td>0.741</td><td>0.252</td><td>0.685</td><td>0.087</td></tr><tr><td></td><td>依兰</td><td>0.616</td><td>0.380 0.602</td><td>0.430</td><td>0.138</td><td>鸡西</td><td>0.862 0.853</td><td>0.743</td><td>0.251</td><td>0.676</td><td>0.085</td></tr><tr><td></td><td>宝清</td><td>0.631</td><td>0.398 0.584</td><td>0.441</td><td>0.130</td><td>虎林</td><td></td><td>0.723</td><td>0.262</td><td>0.671</td><td>0.093</td></tr><tr><td></td><td>鸡西</td><td>0.615</td><td>0.378 0.601</td><td>0.435</td><td>0.157</td><td>12</td><td>0.850</td><td>0.722</td><td>0.267</td><td>0.669</td><td>0.066</td></tr><tr><td></td><td></td><td>0.626</td><td>0.392 0.592</td><td>0.440</td><td>0.138</td><td>鹤岗</td><td>0.928</td><td>0.862</td><td>0.133</td><td>0.785</td><td>0.059</td></tr><tr><td>虎林</td><td></td><td></td><td>0.408</td><td>0.576</td><td></td><td>富锦 佳木斯</td><td>0.922</td><td>0.851</td><td>0.146</td><td>0.766</td><td>0.070</td></tr><tr><td>鹤岗 富锦</td><td>0.761 0.791</td><td>0.579</td><td>0.626 0.364</td><td>0.602</td><td>0.103 0.082</td><td>依兰</td><td>0.919</td><td>0.844</td><td>0.151</td><td>0.762</td><td>0.061</td></tr><tr><td></td><td>0.759</td><td></td><td></td><td></td><td>0.094</td><td></td><td>0.932</td><td>0.869</td><td>0.127</td><td>0.797</td><td>0.054</td></tr><tr><td rowspan="13">9</td><td>佳木斯</td><td></td><td>0.576</td><td>0.411</td><td>0.566</td><td></td><td>宝清</td><td>0.912</td><td>0.832</td><td>0.166</td><td>0.758</td><td>0.066</td></tr><tr><td>依兰</td><td>0.749</td><td>0.560</td><td>0.426</td><td>0.557</td><td>0.110</td><td>鸡西</td><td>0.920</td><td>0.846</td><td>0.147</td><td>0.771</td><td>0.047</td></tr><tr><td>宝清</td><td>0.775</td><td>0.600</td><td>0.392</td><td>0.583</td><td>0.074</td><td>虎林</td><td>0.907</td><td>0.822</td><td>0.171</td><td>0.754</td><td>0.052</td></tr><tr><td>鸡西</td><td>0.771</td><td>0.594</td><td>0.394</td><td>0.583</td><td>0.082</td><td>24 鹤岗</td><td>0.963</td><td>0.927</td><td>0.072</td><td>0.840</td><td>0.043</td></tr><tr><td>虎林</td><td>0.786</td><td>0.617</td><td>0.371</td><td>0.589</td><td>0.089</td><td>富锦</td><td>0.972</td><td>0.944</td><td>0.055</td><td>0.865</td><td>0.037</td></tr><tr><td>鹤岗</td><td>0.840</td><td>0.707</td><td>0.284</td><td>0.660</td><td>0.066</td><td>佳木斯</td><td>0.961</td><td>0.924</td><td>0.074</td><td>0.840</td><td>0.036</td></tr><tr><td>富锦</td><td>0.867</td><td>0.752</td><td>0.242</td><td>0.696</td><td>0.062</td><td>依兰</td><td>0.965</td><td>0.931</td><td>0.067</td><td>0.850</td><td>0.059</td></tr><tr><td>佳木斯</td><td>0.841</td><td>0.707</td><td>0.285</td><td>0.660</td><td>0.064</td><td>宝清</td><td>0.952</td><td>0.906</td><td>0.094</td><td>0.814</td><td>0.050</td></tr><tr><td>依兰 宝清</td><td>0.855</td><td>0.731</td><td>0.262</td><td>0.685</td><td>0.083</td><td>鸡西</td><td>0.964</td><td>0.929</td><td>0.069</td><td>0.851</td><td>0.043</td></tr><tr><td></td><td>0.867</td><td>0.751</td><td>0.244</td><td>0.676</td><td>0.057</td><td>虎林</td><td>0.953</td><td>0.908</td><td>0.088</td><td>0.826</td><td>0.044</td></tr><tr><td>鸡西 虎林</td><td>0.852</td><td>0.725</td><td>0.266</td><td>0.670</td><td>0.057</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>鹤岗</td><td>0.860 0.934</td><td>0.740 0.872</td><td>0.253</td><td>0.681 0.785</td><td>0.052 0.035</td><td>SPEI序列的波动变化,适用性较差。而对于9、12</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>12 富锦 佳木斯</td><td>0.925</td><td>0.856</td><td>0.124 0.141</td><td>0.768</td><td>0.047</td><td></td><td>和 24个月的 SPEI,特别是对 SPEI-12 和 SPEI-24</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>0.923</td><td>0.852</td><td>0.143</td><td>0.766</td><td>0.040</td><td></td><td>的预测,R均达到O.9以上，NSE达0.8以上;非参</td><td></td><td></td><td></td><td></td></tr><tr><td>依兰 宝清</td><td>0.932</td><td></td><td></td><td></td><td></td><td>数指标中的Kendallr最高为0.865,K-S 距离均小于</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>0.908</td><td>0.870</td><td>0.126</td><td>0.792</td><td>0.052</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>24</td><td>0.925</td><td>0.824</td><td>0.175</td><td>0.755</td><td>0.040</td><td></td><td>0.1,说明ARIMA 和ANN 模型在三江平原长时间尺</td><td></td><td></td><td></td><td></td></tr><tr><td>鸡西</td><td>0.912</td><td>0.856 0.831</td><td>0.140 0.164</td><td>0.770</td><td>0.038</td><td></td><td>度的干旱中适用性更强。图2分别给出ARIMA 和</td><td></td><td></td><td></td><td></td></tr><tr><td>虎林 鹤岗</td><td>0.962</td><td>0.926</td><td>0.073</td><td>0.755 0.837</td><td>0.042 0.035</td><td>ANN 模型对7个站点 SPEI拟合结果各评价指标的</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>富锦</td><td>0.970</td><td>0.941</td><td>0.057</td><td>0.861</td><td>0.027</td><td>平均值。发现,随着时间尺度的增加,R、NSE、Ken-</td><td></td></table></body></html>

10098 (0ARM4A 0.961 10008 (AN 0.852 0.920 0.9610.855 0.753 ×X X店 0.7 -R 业 0.7 一R000504 x a 005544 ☆xu M302000 0.141 0.091 0.063 10-0 32000 0.163 0.110 0.08 1-K-S离3 6 9 12 24 3 6 9 12 24时间尺度／mon 时间尺度／mon

![](images/cec25c70942707aa2743b14116aa1ba6239a56fe4417f15177269fb49e07dc72.jpg)  
图2ARIMA和ANN模型对7个站点拟合度评价的平均值 Fig.2Average of each evaluation index of 7 stations by ARIMA and ANN models

从两模型适用性角度来看，对于同一时间尺度，ARIMA模型的拟合效果比ANN模型略优（图3），但这种优势随着时间尺度的增加而变的更弱。即整体上二者对于三江平原较长时间尺度(9、12、24个月)SPEI的拟合效果都比较好。例如对于12个月尺度，ARIMA对各站点SPEI拟合度评价指标的平均值显示,R、NSE、MSE以及非参数方法中的Kendallr和K-S距离分别为0.923、0.852、0.145、0.770、0.042，ANN模型的对应取值分别为0.920、0.847、0.149、0.770、0.058。

2.3.2模型预测精度分析利用最终确定的 ARI-MA和ANN模型对三江平原7个站点2016年各尺度SPEI进行预测，将预测值与实际值通过精度1-$\Bigg | \frac { \hat { y } _ { i } - y _ { i } } { y _ { i } } \Bigg | \times 1 0 0 \%$ 进行比较,结果见表6\~8。表6\~8中仅列出精度在 $70 \%$ 以上的结果。对于3个月和6个月尺度，ARIMA和ANN模型的预测精度均在$6 0 \%$ 以下，表明在三江平原地区两模型均不适用于短时间尺度的干旱预测。对于9、12、24个月尺度的

Tab.6Forecasting precision for $S P E I - 9 \%$   
表824个月尺度SPEI预测精度／ $\%$   

<html><body><table><tr><td>尺度／mon</td><td>站名</td><td>ARIMA1月</td><td>ANN1月</td></tr><tr><td>9</td><td>鹤岗</td><td>79.18</td><td>89.29</td></tr><tr><td rowspan="5"></td><td>富锦</td><td>76.82</td><td>94.01</td></tr><tr><td>佳木斯</td><td>77.90</td><td>92.64</td></tr><tr><td>依兰</td><td>81.35</td><td>90.36</td></tr><tr><td>宝清</td><td>82.21</td><td>82.25</td></tr><tr><td>鸡西</td><td>84.59</td><td>89.56</td></tr><tr><td></td><td>虎林</td><td>72.19</td><td>81.93</td></tr></table></body></html>

SPEI,随着时间尺度的增加，两模型的预测能力逐渐提高。特别是对于12、24个月SPEI的1步预测，精度达到 $80 \%$ 以上。从模型角度来看，对于所有的时间尺度，相比于ARIMA模型，ANN模型预测精度更高。

表712个月尺度SPEI预测精度／ $\%$   
Tab.7Forecasting precision for $S P E I - 1 2 \ / \ \%$   

<html><body><table><tr><td>尺度</td><td>站名</td><td>ARIMA</td><td>ARIMA</td><td>AR月A</td><td>A</td><td></td><td>N</td></tr><tr><td rowspan="5">12</td><td>鹤岗</td><td>87.36</td><td>80.56</td><td>74.75</td><td>87.73</td><td>87.26</td><td>86.11</td></tr><tr><td>富锦</td><td>90.93</td><td>82.88</td><td>73.22</td><td>88.57</td><td>97.31</td><td>95.66</td></tr><tr><td>佳木斯</td><td>86.89</td><td>84.06</td><td>80.48</td><td>87.35</td><td>84.98</td><td>80.70</td></tr><tr><td>依兰</td><td>86.44</td><td>79.46</td><td>72.32</td><td>86.61</td><td>88.43</td><td>85.94</td></tr><tr><td>宝清</td><td>87.53</td><td>83.23</td><td>73.64</td><td>88.78</td><td>85.01</td><td>81.55</td></tr><tr><td></td><td>鸡西</td><td>88.66</td><td>77.28</td><td>77.92</td><td>90.00</td><td>81.77</td><td>86.07</td></tr><tr><td></td><td>虎林</td><td>83.71</td><td>76.45</td><td>70.93</td><td>85.04</td><td>86.03</td><td>86.75</td></tr></table></body></html>

表69个月尺度SPEI预测精度／%  
Tab.8Forecasting precision for SPEI -24/%   

<html><body><table><tr><td>尺度 /mon</td><td>站名</td><td>ARIMA 1月</td><td>ARIMA 2月</td><td>ARIMA 3月</td><td>ARIMA 4月</td><td>ANN 1月</td><td>ANN 2月</td><td>ANN 3月</td><td>ANN 4月</td></tr><tr><td>24</td><td>鹤岗</td><td>90.23</td><td>85.09</td><td>83.95</td><td>80.19</td><td>93.47</td><td>89.34</td><td>87.69</td><td>83.80</td></tr><tr><td></td><td>富锦</td><td>95.07</td><td>85.32</td><td>96.58</td><td>78.44</td><td>95.36</td><td>92.15</td><td>95.63</td><td>86.12</td></tr><tr><td></td><td>佳木斯</td><td>85.70</td><td>87.83</td><td>82.56</td><td>76.97</td><td>92.98</td><td>89.84</td><td>87.97</td><td>83.02</td></tr><tr><td></td><td>依兰</td><td>96.21</td><td>92.86</td><td>91.80</td><td>92.84</td><td>95.39</td><td>92.23</td><td>96.28</td><td>96.36</td></tr><tr><td></td><td>宝清</td><td>88.00</td><td>84.54</td><td>71.66</td><td>70.98</td><td>89.13</td><td>85.35</td><td>73.05</td><td>70.03</td></tr><tr><td></td><td>鸡西</td><td>90.72</td><td>85.22</td><td>82.37</td><td>82.50</td><td>94.75</td><td>87.74</td><td>89.23</td><td>86.39</td></tr><tr><td></td><td>虎林</td><td>82.69</td><td>74.79</td><td>75.71</td><td>75.43</td><td>85.20</td><td>83.71</td><td>83.96</td><td>77.70</td></tr></table></body></html>

# 3结论

本文引入了综合降水和气温变化共同效应的气候干旱指数SPEI,利用ARIMA和ANN模型对三江平原不同时间尺度的SPEI序列建模拟合预测，并集合参数和非参数方法中的5个评价指标进行对比验证，最后进行了12步预测，得到如下结论：

从时间尺度看，ARIMA模型和ANN模型对SPEI的预测能力都随时间尺度的增加而逐渐提高。对于3个月和6个月尺度，预测精度较低；对9、12、24个月的SPEI值，两模型均可进行精度在 $70 \%$ 以上的1、3、4步预测。即整体上ARIMA模型和ANN模型在三江平原较长时间尺度(9、12、24个月)干旱预测中都显示出良好的效果。根据SPEI的计算公式可知，长时间尺度的SPEI集合了原始数据中更多的信息，使得预测值对观测值的拟合更充分。

对于相同时间尺度，在训练和测试阶段，ARI-MA模型的拟合效果与ANN模型基本持平，但是在预测时，ANN模型则表现出相对更高的精度。说明基于ANN时间序列预测模型具有较强的可操作性，可以有效地进行三江平原较长时间尺度干旱情况的预测。这主要是由于以下两方面原因导致：（1）降雨数据的产生是随机的、不确定的，并且大多数数据都含有白噪声，而ARIMA模型本质上是一种整体线性自回归模型[30],对于由降水数据计算得来的SPEI的变化这种非线性行为的分析、预测存在着较大的不确定性和不足；ANN则具有较强的非线性映射能力和较好的稳健性[11],能够区分有噪声的样本，可以通过对样本学习把隐含的内在规律分布在网络的连接权重上。（2）ARIMA模型的基本思想是首先将非平稳的时间序列通过差分转化为平稳的时间序列,再用ARMA 模型对该平稳序列建模[20]而在差分的过程中不可避免的会损失数值信息；ANN模型则充分发挥了较强的学习能力和逼近任意函数的特点，对原始数据进行了充分的学习。

此外，对于短时间尺度的干旱预测有待在日后的研究中完善。

参考文献（References）   
[1］王利娜,苏静,郑晓东,等.我国农业干旱风险研究进展简述 [J].水科学与工程技术,2011,（2）:3-7.[WANG Lina,SU Jing,ZHENG Xiaodong,et al. Research progress of agricultural drought risk in China[J].Water Sciences and Engineering Technology,2011,(2) :3 -7.]   
[2］张玉虎,刘凯利,陈秋华,等.区域气象干旱特征多变量Copula 分析——以阿克苏河流域为例[J].地理科学,2014,34（12）： 1480 -1487.[ZHANG Yuhu,LIU Kaili,CHEN Qiuhua,et al. Bivariate probability distribution of meteorological drought characteristics in the Aksu Basin using Copula[J]. Scientia Geographica Sinica,2014,34(12) :1480 -1487.]   
[3］谢培,顾艳玲,张玉虎,等.1961—2015 年新疆降水及干旱特征 分析[J].干旱区地理,2017,40(2）:332-339.[XIE Pei,GU Yanling,ZHANG Yuhu,et al.Precipitation and drought characteristics in Xinjiang during 1961—2015[J].Arid Land Geography, 2017,40(2) :332-339.]   
[4］张玉虎,向柳,孙庆,等.贝叶斯框架的 Copula 季节水文干旱预 报模型构建及应用[J].地理科学,2016,36(9）：1437－1444. [ZHANG Yuhu, XIANG Liu,SUN Qing,et al. Construction and application of hydrological drought prediction model for Copula in Bayesian framework[J]. Scientia Geographica Sinica，2016,36 (9):1437 -1444. ]   
[5］吴晶,罗毅,李佳,等.CMIP5 模式对中国西北干旱区模拟能力 评价[J].干旱区地理,2014,37（3）:499-508.[WUJing,LUO Yi,LI Jia,et al.The evaluation of CMIP5 model for simulation ability in China’s northwestarid region[J].Arid Land Geography, 2014,37(3) :499 -508.]   
[6]韩萍,王鹏新,王彦集,等.多尺度标准化降水指数的ARIMA 模型干旱预测研究[J].干旱地区农业研究,2008,26(2）：212 -218.[HAN Ping,WANG Pengxin,WANG Yanji,et al. Drought forecasting based on the standardized precipitation index at different temporal scales using ARIMA models[J].Agricultural Research in the Arid Areas,2008,26(2):212 -218.]   
[7]ZHANG Y,LI W,CHEN Q,et al. Multi-models for SPI drought forecasting in the north of Haihe River Basin,China[J].Stochastic Environmental Research & Risk Assssment,2017,31（10）: 2471 - 2481.   
[8］刘海萍.中国主要股指的分形分析与 BP神经网络预测[D]. 大连：大连理工大学,2013.［LIU Haiping.The fractal analysis of major indexes and BP neural network prediction in China[D]. Dalian:Dalian University of Technology,2013.]   
[9]XIN RB,JIANG Z F,LI N,et al.An air quality predictive model of Licang of Qingdao City based on BP neural network[J].Advanced Materials Research,2013,756 -759:3366 -3371.   
[10］张皓.基于MATLAB动态神经网络进行时间序列预测房地产 价格的研究[J].经济师,2015,（9）:284-286.［ZHANG Hao. Based on MATLAB dynamic neural network time series forecast real estate price research[J]. China Economist,2015,（9）:284 - 286.]   
[11]DJERBOUAI S,SOUAG-GAMANE D. Drought forecasting using neural networks,wavelet neural networks and stochastic models :A case of the Algerois Basin in north Algeria[J].Water Resources Management,2016,30(7）:2445-2464.   
[12] BARUA S,PERERA B J C,NG A W M,et al. Drought forecasting using an aggregated drought index and artificial neural network [J].Journal of Water& Climate Change,2010,1(3）:193.   
[13]BELAYNEH A,ADAMOWSKI J,KHALIL B,et al. Long-term SPI drought forecasting in the Awash River Basin in Ethiopia using wavelet neural network and wavelet support vector regression models[J]. Journal of Hydrology,2014,508(2）:418 -429.   
[14］罗明美.基于AMSR-E和ANN人工神经网络的淮河流域土壤 水分反演研究［D].成都：四川农业大学,2013.［LUO Mingmei.Study on soil water inversion in huai river basin based on AMSR-E and ANN artificial neural network[D].Chengdu: Sichuan Agricultural University,2013.]   
[15］沈国强,郑海峰,雷振锋.SPEI指数在中国东北地区干旱研究 中的适用性分析[J].生态学报,2017,37（11）：3787－3795. [SHEN Guoqiang,ZHENG Haifeng,LEI Zhenfeng.Applicability analysis of SPEI for drought research in northeast China[J].Acta Ecologica Sinica,2017,37(11）:3787 -3795.]   
[16］王媛媛,张勃.基于标准化降水指数的近40 年陇东地区旱涝 时空特征[J]．自然资源学报,2012,27（12）:2135－2144. [WANG Yuanyuan,ZHANG Bo.The spatial and temporal characteristics of drought and waterlogging in Longdong area based on standardized precipitation index in recent 4O years[J].Journal of Natural Resources,2012,27(12）:2135-2144.]   
[17］张岳军,郝智文,王雁,等.基于 SPEI和 SPI指数的太原多尺 度干旱特征与气候指数的关系[J].生态环境学报,2014,23 （9）:1418-1424.[ZHANG Yuejun,HAO Zhiwen,WANG Yan, et al.Multiscale characteristics of drought based on SPEI and SPI in association with climate index in Taiyuan[J].Ecology and Environmental Sciences,2014,23（9）:1418-1424.]   
[18］李伟光,侯美亭,陈汇林,等.基于标准化降水蒸散指数的华南 干旱趋势研究[J].自然灾害学报,2012,21（4)：84-90.［LI Weiguang,HOU Meiting,CHEN Huilin,et al.Study on drought trend in south China based on standardized precipitation evapotranspiration indexJ].Journal of Natural Disasters,2012,21（4）: 84 -90.]   
[19］王林,陈文.近百年西南地区干旱的多时间尺度演变特征[J]. 气象科技进展,2012,2(4）:21-26.[WANG Lin,CHEN Wen. The multi-temporal scale evolution characteristics of drought in southwest China in the past 1OO years[J].Advances in Meteorological Science and Technology,2012,2（4）:21-26.]   
[20]ADAMOWSIKI J,CHAN HF,PRASHER S O,et al. Comparison of multiple linear and nonlinear regression,autoregressive integrated moving average,artificial neural network and wavelet artificial neural network methods for urban water demand forecasting in Montreal,Canada[J].Water Resources Research,2012,48（1):273- 279.   
[21］岳新征,李磊民,孙飞.基于 NAR 动态神经网络的石英挠性加 速度表参数建模与预测［J].西南科技大学学报,2016,31 (1):88-92.[YUE Xinzheng,LI Leimin,SUN Fei.Parametric modeling and prediction of quartz flexible accelerometerbased on NAR dynamic neural network[J]. Journal of Wuhan university, 2016,31(1) :88 -92.]   
[22］邓兴升，王新洲.动态神经网络在变形预报中的应用[J]．武 汉大学学报,2008,33（1）：93-96.［DENGXingsheng，WANG Xinzhou.Application of dynamic neural network in deformation prediction[J]. Journal of Wuhan University,2008,33（1）:93- 96.]   
[23］VICEBTESERRANO S M,BEGUERIA S,LOPEZMORENO JI.A multi-scalar drought index sensitive to global warming:The standardized precipitation evapotranspiration index ［J]. Journal of Climate,2010,23(7):1696-1718.   
[24］刘珂，姜大膀.基于两种潜在蒸散发算法的SPEI对中国干湿 变化的分析[J].大气科学,2015,39（1)：23-36.［LIUKe， JIANG Dabang.Analysis of dryness ／wetness over China using standardized precipitation evapotranspiration index based on two evapotranspiration algorithms[J].Chinese Journal of Atmospheric Sciences,2015,39(1) :23-36.]   
[25］GB/T20481—2006，气象干旱等级［S].北京：中国标准出版 社,2006.[GB/T 20481—2006,Classfication of meteorological drought[S].Beijing:Standards Press of China,2006.]   
[26］PEARSONE S,HARTLEYHO.Biometrika tables for statisticians [M].London:Cambridge University Press,1956.   
[27］李宝林，周成虎.东北平原西部沙地的气候变异与土地荒漠化 [J].自然资源学报,2001,16（3）:234-239.［LIBaolin,ZHOU Chenghu.Climatc variation and desertification in west sandy land of Northeast China Plain[J].Journal of Natural Resources,2001, 16(3):234-239.]   
[28］王春乙,蔡菁菁,张继权.基于自然灾害风险理论的东北地区 玉米干旱、冷害风险评价[J].农业工程学报，2015，31(6)：238 -245.［WANG Chunyi,CAI Jingjing,ZHANG Jiquan．Risk assessment of drought and chilling injury of maize in northeast China [J].Transactions of the Chinese Society of Agricultural Engineering,2015,31(6) :238-245.]   
[29］胡欣欣，张玉虎，向柳.新疆阿克苏地区气象干旱特征研究 [J].安徽农业科学，2015，43（35）： $9 6 - 1 0 0 + 1 0 4$ [HUXinxin,ZHANGYuhu,XIANGLiu.Studyon the characteristics of meteorological drought in Aksu region of Xinjiang[J].Journal of Anhui Agricultural Sciences,2015,43（35） $9 6 - 1 0 0 + 1 0 4$ ]   
[30]MISHRA A K,DESAI V R.Drought forecasting using stochastic models[J].Stochastic Environmental Research and Risk Assessment,2005,19(5):326-339.

# Applicability of ARIMA and ANN models for drought forecasting

YANG Hui-rong'， ZHANG Yu-hu²， CUI Heng-jian1， GAO Feng²， CHEN Qiu-hual (1School of Mathematical Sciences,Capital Normal University,Beijing 1Oo048,China; 2College of Resources Environment & Tourism,Capital Normal University,Beijing 1Ooo48,China)

Abstract:Drought isone of the major natural disasters,whose occurrence is linked to a sustained lack of precipitation.The drought forecast provides vital evidenceand support for preventing losses ofdrought disasters,and therefore it is of great significance.In this study,a series of the standard precipitation evapotranspiration index ( $S P E I$ ）at diffrent time scales werecalculated based on thedaily precipitation and temperature data from7 meteorological stations in Sanjiang Plain,northeast China from l96O to 2O16and were used to forecast the drought using ARIMA and ANN models.In the stage of training and testing,the fiting degrees of the models were evaluated andvalidated and the optimal ARIMA and ANN models were chosen with the helpof6fiting evaluation methods:the correlation coefficient （ $R$ ）,Nash-Sutcliffe efficiency coefficient （NSE）,Kendall,rank correlation coefficient,the mean square error (MSE）and Kolmogorov-Smirnov（K-S）test.Then 12 values for the12 months in 2016 were predicted bythe optimal models and were compared with the corresponding observations.The results are shown as folows:（1）The prediction ability of ARIMA and ANN models basedon SPEI were both increased with the increase of time scale in Sanjiang Plain.（2）The two models had poor prediction accuracy for SPEI3 and SPEI6.For the SPEI value of 9, 12 and 24 months,all models worked well with accuracy more than $70 \%$ .（3）For the SPEI value of 9,12 and 24 months,the prediction accuracy of ANN model is beterthan that of ARIMA model.In particular,the prediction accuracy for one month forecast of SPEI 12 and 24 at all stations were more than $80 \%$ . All these showed that the prediction model of ANN has strong maneuverabilityand can efectively predictthe drought at alarge time scale in Sanjiang Plain.The drought prediction at small time scale(3 and 6 months） needs to be improved in future studies.

Key words:drought；ARIMA model；ANN model;SPEIs；Sanjiang Plain