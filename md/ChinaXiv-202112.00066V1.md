# 基于时频分析的LSTM组合模型径流预测

蔡文静1，陈伏龙¹，何朝飞¹，骆成彦¹，龙爱华1.2（1.石河子大学水利建筑工程学院,新疆 石河子832000；2.中国水利水电科学研究院，流域水循环模拟与调控国家重点实验室，北京100038)

摘要：针对变化环境下径流时间序列复杂的非线性、非平稳性特征，为提高中长期径流预测的准确性，运用多种时频分析方法构建组合预报模型以探究适用性。以干旱区典型内陆河玛纳斯河为例，利用经验模态分解(EMD)、变分模态分解(VMD）、离散小波变换(DWT)时频分析方法对径流时间序列进行多尺度分解，得到不同频率和特征的子序列。以前期径流、降水量、气温、大气环流因子等作为长短期记忆神经网络模型(LSTM)的输入变量，采用随机森林法和Pearson相关系数法确定各子序列的最佳预报因子，基于时频分析方法分别构建EMD-LSTM、VMD-LSTM、DWT-LSTM组合预报模型,通过LSTM模型对各子序列进行预测,加和重构获得最终预测结果,并与单一的误差反向传播神经网络(BP)、极限学习机(ELM)、LSTM模型的预测结果进行对比分析。结果表明：组合模型VMD-LSTM预报误差最小、精度最高,纳什系数保持在0.9以上，有效避免了过拟合等问题，其径流极值预测误差在 $1 5 \%$ 以内，对径流总体趋势预测和极值的追踪均有良好效果。研究结果可为流域水资源规划与调度提供参考。

关键词：径流预测；组合模型；时频分析；长短期记忆神经网络文章编号：

受气候变化、人类活动等多因素影响，河川径流表现出较强的随机性、灰色性、非线性等特征[1-2]。玛纳斯河位于西北干旱区,径流补给主要依靠冰川融水，其径流时间序列具有更强的随机性和非平稳性，且融雪性径流的异常对流域产生不利影响，因此，提高径流预报模型的精度是西北干旱区水资源规划调度工作中的难点[3]。过程驱动和数据驱动是河川径流主要预测方法[4]。过程驱动是以模拟或反映降雨径流过程中流域产汇流机理的概念性或集总式水文模型为主，需要考虑不同时空尺度下的水文规律和参数的不确定性，在数据缺测地区的预测能力受到限制5，而数据驱动模型无须考虑水文过程的物理机制，随着时间序列处理技术的发展，水文水资源学科和人工智能逐渐存在交叉，较为广泛地运用于径流研究中并取得良好的效果[6-7],如传统时序建模方法(ARIMA)、人工神经网络模型(ANN）、支持向量机(SVM)等。

基于深度学习的快速发展，长短期记忆神经网络模型被逐渐运用于水文预测之中，其可挖掘输出与相关输入变量之间空间和时序性的关联，在递归结构中加入门控运算，同时在复杂时间序列预测领域也有较多应用[8-9]。深度学习在挖掘数据特征方面，相较于目前的径流预测方法，在一定程度上可弥补其不足，提高模型拟合效果。Kratzert等[]利用大量数据探索长短期记忆神经网络模型(LSTM)对流量预测情况，通过预测结果与实际流量进行对比，得出LSTM在处理长时间序列有较好的效果；顾逸[]构建Simple-LSTM模型，与前向型神经网络(FNN)和SVM相比可获得更高的预报精度;冯锐[12]提出LSTM-BP耦合径流预测改进模型，较误差反向传播神经网络(BP)和LSTM的预报速度更快、精度更高。

径流时间序列是含有多种频率和趋势成分的非线性非平稳序列，其非平稳性和非线性增加了直接预测的难度[13-14]。因此基于时频分析的数据预处理方法已逐渐运用于水文分析之中[15-16]。通过将原始径流序列分解为不同频率的子序列，使径流序列趋于平稳化，将各子序列分别带入模型预测以提高预测的精度。Giulia等[17]建立EMD-ANN分解-集成模型，预测结果有明显的提高，验证了模型的有效性;Tayyab等[18]应用小波变换将各子序列与BP、径向基函数神经网络(RBF)模型组合，构建DWT-BP和DWT-RBF组合模型，与单一模型相比预测结果得到了明显的提升；刘艳等[19]将玛纳斯河的局部信息运用集合经验模态分解(EEMD)预处理，构建传统时序建模方法(ARIMA)组合模型，可有效提高预测准确性;赵力学等[20]运用VMD-BP模型来处理水位流量的非线性拟合，取得较好的结果。目前研究发现分解技术能够有效提高径流预测精度，但大多数研究未考虑预报因子对子序列的影响。

本文结合不同时频分析方法和LSTM模型的优点，构建基于经验模态分解(EMD）、变分模态分解(VMD）、离散小波变换(DWT)的LSTM组合预报模型，运用随机森林法和Pearson相关系数法优选历史径流、降水量、大气环流因子等水文气象要素作为输人项，比较不同时频分析方法对提高玛纳斯河径流预报精度的贡献程度，对比分析组合模型和单一模型在本研究区的适用性，并探究分解技术下大气环流因子对径流子序列的影响，结果可为流域水资源开发利用与调配提供技术支持。

# 1研究区概况

玛纳斯河发源于天山北麓的依连哈比尔尕山，为准噶尔盆地南缘最大的一条融雪型河流，流域地处欧亚大陆腹地[21]，流域范围为 $4 3 ^ { \circ } 2 1 ^ { \prime } { \sim } 4 5 ^ { \circ } 2 0 ^ { \prime } \mathrm { N }$ $8 4 ^ { \circ } 4 3 ^ { \prime } { \sim } 8 6 ^ { \circ } 3 5 ^ { \prime } \mathrm { E }$ ，面积约为 $2 . 4 3 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 。玛纳斯河流域深居内陆远离海洋，年平均气温 $6 . 0 { \sim } 6 . 9 \mathrm { ~ \% }$ ，年降水量 $1 1 0 { \sim } 3 0 0 ~ \mathrm { m m }$ ,时空分布不均，年蒸发量 $1 5 0 0 \sim$ $2 0 0 0 \mathrm { m m }$ ,属于典型温带大陆性干旱半干旱气候[22]肯斯瓦特水文站海拔 $9 1 0 \mathrm { m }$ ,控制面积 $4 6 3 7 \mathrm { k m } ^ { 2 }$ 是玛纳斯河干支流汇合后的出山口控制站(图1)。

![](images/ca87ee5a172ce42cbd253b593adc98d75dcd8bbb5faf46f676d31fef2da48648.jpg)  
图1肯斯瓦特站控制区域   
Fig.1 Control area of Kenswart station

# 2数据与方法

# 2.1数据资料

本文采用的数据为肯斯瓦特水文站1956—2014年径流、降水量、气温、74项大气环流因子的月尺度数据。由于各数据量级相差过大,将其归一化处理。其中1956年1月至2010年12月数据用于模型训练，2010年1月至2014年12月数据用于模型验证。水文数据来源于石河子水文局，大气环流因子数据来源于http://www.esrl.noaa.gov/。

# 2.2 研究方法

2.2.1经验模态分解（EMD）EMD[23]依据特定条件将信号分解为多个具有物理意义的固有模态函数(IMF)。计算步骤如下：

（1）确定原序列 $x ( t )$ 所有局部极值点，利用三次样条插值函数进行拟合其上包络线 $x _ { \mathrm { m a x } } ( t )$ 和下包络线 $x _ { \mathrm { m i n } } ( t )$ 。

（2）上下包络线的平均包络线记作 $m ( t )$ ：计算原序列 $x ( t )$ 与 $m ( t )$ 的差值序列 $h ( t ) : h ( t ) = x ( t ) -$ $m ( t )$ 。

(3)若 $h ( t )$ 满足以下2个条件：在任意时刻，由极端值定义的上包络线和下包络线均值为0;各个瞬间平均值为0。若不满足条件,则让 $h ( t )$ 重复以上步骤,直到满足条件为止;若 $h ( t )$ 满足上述条件，则 $h ( t )$ 成为第一个固有模态函数 $I _ { 1 } ( t )$ 。

（4）将原序列减去 $I _ { 1 } ( t )$ ,计算得到剩余项 $r _ { 1 } ( t )$ ：$r _ { 1 } ( t ) = x ( t ) - I _ { 1 } ( t )$ ，把 $r _ { 1 } ( t )$ 视为新的原序列,重复上述步骤，分解出全部的固有模态函数，直至单调的残余项出现才结束。

2.2.2变分模态分解（VMD）VMD是在EMD的基础上提出的一种自适应的信号处理方法[24]。通过搜索和求解过程确定最优的中心频率和有限带宽，完成信号的频域剖分及各分量的分离。

原始信号分解为 $k$ 个分量，保证各模态估计带宽之和最小。约束条件是分解出的全部模态之和与原始信号相同，变分约束表达式为：$\operatorname* { m i n } _ { \{ u _ { k } \} , \{ \omega _ { k } \} } \left\{ \sum _ { k } \left\| \partial _ { t } \bigg [ \Big ( \delta ( t ) + \frac { j } { \pi t } \Big ) \ast u _ { k } ( t ) \bigg ] \mathrm { e } ^ { - j \omega _ { k } t } \right\| _ { 2 } ^ { 2 } \right\} \mathrm { s . t . } \sum _ { k = 1 } ^ { K } u _ { k } = f ( t )$ (1)式中： $\left\{ u _ { k } \right\} \mathrm { ~ , ~ } \left\{ \omega _ { k } \right\}$ 分别对应分解后第 $k$ 个模态分量和中心频率； $k$ 为模式数； $\partial _ { { } _ { t } }$ 为梯度运算； $\delta ( t )$ 为狄克拉函数 $; j$ 为虚数单位; $\mathbf { \Phi } _ { t }$ 为时间;\*为卷积符号； $u _ { k } ( t )$ 为第 $k$ 个分解模态下的第 $\mathbf { \Phi } _ { t }$ 个数据; $\mathrm { ~ e ~ } ^ { - j \omega _ { k } t }$ 为预估中心频率; $\omega _ { k } = \left\{ \omega _ { 1 } , \omega _ { 2 } , \cdots , \omega _ { k } \right\}$ 为各中心频率集;s.t.为约束条件; $K$ 为需要分解的模态个数; $u _ { k } = \{ u _ { 1 } , u _ { 2 } , \cdots , u _ { k } \}$ 为各模态函数集； $f ( t )$ 为原始信号

求解式(1)并引入Lagrange乘法算子,将约束变分问题转换为非约束问题，得到扩展Lagrange表达式：

$$
\begin{array} { l } { \displaystyle { L = \left( \{ u _ { k } \} , \{ \omega _ { k } \} , \lambda \right) = \alpha \sum _ { k } \Big \| \partial _ { \boldsymbol { \nu } } \Big [ \big ( \delta ( t ) + j / \pi t \big ) \ast u _ { k } ( t ) \Big ] \mathrm { e } ^ { - j \omega _ { k } t } \Big \| _ { 2 } ^ { 2 } + } } \\ { \displaystyle \Big \| f ( t ) - \sum _ { k } u _ { k } ( t ) \Big \| _ { 2 } ^ { 2 } + \Bigg [ \lambda ( t ) , f ( t ) - \sum _ { k } u _ { k } ( t ) \Bigg ] }  \end{array}
$$

式中： $\lambda$ 和 $\alpha$ 分别为拉格朗日乘数和二次惩罚参数。

运用交替方向乘子（ADMM)[2算法迭代搜索，迭代后的 $u _ { k } \setminus \omega _ { k }$ 和 $\lambda$ 的表达式如下：

$$
\widehat { u } _ { k } ^ { n + 1 } ( \omega ) \longleftarrow \frac { \widehat { f } ( \omega ) - \sum _ { i \neq k } \widehat { u } _ { i } ( \omega ) + \widehat { \lambda } ( \omega ) / 2 } { 1 + 2 \alpha \big ( \omega - \omega _ { k } \big ) ^ { 2 } }
$$

$$
{ \boldsymbol { \omega } } _ { k } ^ { n + 1 } \longleftarrow { \frac { \displaystyle \int _ { 0 } ^ { \infty } { \boldsymbol { \omega } } \biggl | \hat { \boldsymbol { u } } _ { k } ^ { n + 1 } \bigl ( { \boldsymbol { \omega } } \bigr ) \biggr | ^ { 2 } \mathrm { d } { \boldsymbol { \omega } } } { \displaystyle \int _ { 0 } ^ { \infty } \biggl | \hat { \boldsymbol { u } } _ { k } ^ { n + 1 } \bigl ( { \boldsymbol { \omega } } \bigr ) \biggr | ^ { 2 } \mathrm { d } { \boldsymbol { \omega } } } }
$$

$$
\widehat { \lambda } ^ { n + 1 } ( \omega ) \longleftarrow \widehat { \lambda } ^ { n } ( \omega ) + \gamma \Biggl [ \widehat { f } ( \omega ) - \sum _ { k } \widehat { u } _ { k } ^ { n + 1 } ( \omega ) \Biggr ]
$$

式中：^为傅里叶变换; $\widehat { \boldsymbol { u } } _ { k } ^ { n + 1 } \big ( \omega \big ) \mathrm { ~ , ~ } \widehat { \boldsymbol { u } } _ { i } \big ( \omega \big ) \mathrm { ~ , ~ } \widehat { \boldsymbol { f } } \big ( \omega \big ) \mathrm { ~ , ~ } \widehat { \boldsymbol { \lambda } } \big ( \omega \big )$   
分别对应 $u _ { k } ^ { n + 1 } ( t ) \setminus u _ { i } ( t ) \setminus f ( t ) \setminus \lambda ( t )$ 的傅里叶变换;  
$\omega$ 为频率; $\gamma$ 为噪声容忍度。

VMD主要迭代求解过程如下：

(1)初始化 $u _ { k } ^ { 1 } \setminus \omega _ { k } ^ { 1 } \setminus \lambda ^ { 1 }$ 和最大迭代次数 $N , n {  } 0$ (2）根据公式(3)和(4)更新 $\boldsymbol { u } _ { k }$ 和 $\boldsymbol { \omega } _ { k }$ ;

(3）根据公式(5)更新 $\lambda$ ;

（4）精度收敛判断依据 $\varepsilon > 0$ ，如果不满足$\sum _ { k } \left\| \widehat { \boldsymbol { u } } _ { k } ^ { n + 1 } - \widehat { \boldsymbol { u } } _ { k } ^ { n } \right\| _ { 2 } ^ { 2 } / \left\| \widehat { \boldsymbol { u } } _ { k } ^ { n } \right\| _ { 2 } ^ { 2 } < \varepsilon$ 且 $n { < } N$ ，则回到第二步,否则完成迭代,输出最终的 $\boldsymbol { u } _ { k }$ 和 $\boldsymbol { \omega } _ { k }$ 0

2.2.3离散小波变换（DWT）DWT逐层将信号分解到不同频率通道上，获取更加单一、平滑的各子序列[26]。基于Mallat算法实现信号的分解与重构，其表达式为：

$$
\left\{ \begin{array} { l l } { c _ { j + 1 } = H c _ { j } } \\ { d _ { j + 1 } = G c _ { j } } \end{array} , \right. \ j = 0 , 1 , \cdots J
$$

$$
c _ { j } = \tilde { H } c _ { j + 1 } + \tilde { G } d _ { j + 1 } , \ j = J - 1 , J - 2 , \cdots , 0
$$

式中： $c _ { j + 1 }$ 为分解尺度 $j { + } 1$ 下的低频信号; $H$ 为低通滤波器; $c _ { j }$ 为分解尺度数为 $j$ 时的低频信号; $d _ { j + 1 }$ 为分解尺度 $j { + } 1$ 下的高频信号； $G$ 为高通滤波器; $J$ 为分解尺度数； $\tilde { H }$ 为重构低通滤波器； $\tilde { G }$ 为重构高通滤波器。

通过公式(6)将原始信号 $c _ { 0 }$ 分解，得到1组合并后的低频子信号 $\boldsymbol { c } _ { j }$ 和 $J$ 组高频子信号 $d _ { j } , d _ { j - 1 } , \cdots , d _ { 1 }$ ，采用公式(7)对 $c _ { j }$ 和 $d _ { j } , d _ { j - 1 } , \cdots , d _ { 1 }$ 序列重构,有效地实现信号的特征分离。

2.2.4长短期记忆神经网络（LSTM）LSTM可以避免长依赖问题[27],适用于处理有较长时间间隔和延迟的事件，结构如图2所示。将不同的序列作为LSTM的输入项，通过门控单元读取与调整隐含状态向量和记忆状态向量，以此实现各序列的预测。其相关计算方法如下：

注： $\sigma$ 为 Sigmoid函数; $\operatorname { t a n } h$ 为双曲余弦函数; $c _ { t - 1 } \setminus h _ { t - 1 }$ 分别为第$_ { t - 1 }$ 时刻记忆单元状态变量和隐藏层状态； $\smash { c _ { t } \searrow h _ { t } }$ 分别为第 $\mathbf { \Phi } _ { t }$ 时刻记忆单元状态变量和隐藏层状态； $X$ 为输入信息；Y为输出信息。

![](images/d2dcbc146a22e144e1f08a943e16ad9dbd89c10c6a560640e8c89bb2609e297b.jpg)  
图2长短期记忆神经网络神经元结构示意图  
Fig.2Diagram of neuron structure of long-short term memory

$$
f _ { t } = \sigma \big ( W _ { f } x _ { t } + U _ { f } h _ { t - 1 } + b _ { f } \big )
$$

$$
i _ { t } = \sigma \big ( W _ { i } x _ { t } + U _ { i } h _ { t - 1 } + b _ { i } \big )
$$

$$
\tilde { c } _ { t } = \mathrm { t a n } h \big ( W _ { \tilde { c } } x _ { t } + U _ { \tilde { c } } h _ { t - 1 } + b _ { \tilde { c } } \big )
$$

$$
\boldsymbol { c } _ { t } = \boldsymbol { f } _ { t } \left( \widetilde { \boldsymbol { \mathbf { \xi } } } \right) \boldsymbol { c } _ { t - 1 } + i _ { t } \left( \widetilde { \boldsymbol { \mathbf { \xi } } } \right) \widetilde { \boldsymbol { c } } _ { t }
$$

$$
o _ { \ i } = \sigma \big ( W _ { o } x _ { \ i } + U _ { o } h _ { \ i - 1 } + b _ { o } \big )
$$

$$
h _ { \iota } = \mathrm { t a n } h ( c _ { \iota } ) \bigotimes c _ { \iota }
$$

式中： $\boldsymbol { \mathscr { f } } _ { t }$ 为 $\mathbf { \Phi } _ { t }$ 时刻的遗忘门; $\sigma$ 为Sigmoid函数; $W , U$ 为权重矩阵; $\boldsymbol { x } _ { t }$ 为 $\mathbf { \chi } _ { t }$ 时刻的输入； $h _ { t - 1 }$ 为 $t { - } 1$ 时刻的隐含层状态； $b$ 为偏置向量; $\boldsymbol { i } _ { t }$ 为 $\mathbf { \chi } _ { t }$ 时刻输入门； $\tilde { c } _ { t }$ 为记忆更新向量； $\mathrm { t a n } h$ 为双曲余弦函数； $\boldsymbol { c } _ { t }$ 为 $\mathbf { \Phi } _ { t }$ 时刻的记忆单元状态变量； $\textcircled{8}$ 为向量标量积; $\boldsymbol { c } _ { t - 1 }$ 为 $t { - } 1$ 时刻记忆单元状态变量； $\boldsymbol { o } _ { t }$ 为 $\mathbf { \chi } _ { t }$ 时刻的输出门; $h _ { \scriptscriptstyle t }$ 为 $\mathbf { \Phi } _ { t }$ 时刻隐含层状态。

# 2.3模型性能评价

模型精度评价指标采用均方根误差(Rootmeansquare error,RMSE）、纳什系数（Nash sutcliffe error,NSE)和决定系数(Coefficientofdetermination, $R ^ { 2 }$ ）。具体公式如下：

$$
\mathrm { R M S E } = \sqrt { \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \bigl [ Q _ { f } ( i ) - Q _ { 0 } ( i ) \bigr ] ^ { 2 } }
$$

$$
\mathrm { N S E } = 1 - \frac { \displaystyle \sum _ { i = 1 } ^ { N } \bigl [ Q _ { \circ } ( i ) - Q _ { f } ( i ) \bigr ] ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { N } \bigl [ Q _ { \circ } ( i ) - \overline { { Q _ { \circ } } } \bigr ] ^ { 2 } }
$$

$$
R ^ { 2 } = \frac { \biggl \{ \displaystyle \sum _ { i = 1 } ^ { N } \bigl [ Q _ { \circ } ( i ) - \overline { { Q _ { \circ } } } \bigr ] \bigl [ Q _ { f } ( i ) - \overline { { Q _ { f } } } \bigr ] \biggr \} ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { N } \bigl [ Q _ { \circ } ( i ) - \overline { { Q _ { \circ } } } \bigr ] ^ { 2 } \sum _ { i = 1 } ^ { N } \bigl [ Q _ { f } ( i ) - \overline { { Q _ { f } } } \bigr ] ^ { 2 } }
$$

式中： $N$ 为预测月数; $Q _ { f } ( i )$ 为预测径流量; $Q _ { \mathfrak { o } } ( i )$ 为 实测径流量； $\overline { { Q _ { \mathrm { 0 } } } }$ 为实测径流量均值; $\overline { { Q _ { f } } }$ 为预测径流 量均值。

# 3结果与分析

# 3.1基于EMD的时间序列分解

利用EMD对肯斯瓦特水文站1956年1月至2014年12月径流时间序列进行分解，结果如图3所示，EMD将原始序列自适应地分解为高频到低频的6个固有模态分量函数(IMF)和1个趋势项分量$( R )$ ,IMF1不规则是由径流序列的非线性和噪声成分所导致，进一步验证径流序列的非线性和非平稳性。分解后IMF1频率最高，振幅最大，包含了原始序列的主要信息，分量IMF2\~IMF6频率依次降低，振幅依次减小，显示出原始序列的局部特征，趋势项表明肯斯瓦特水文站的径流量呈现上升趋势

![](images/9730e54b1bcdd8c08cb271ff538099f6eca627839f0073cf7cfc04818ea72485.jpg)  
图3基于经验模态分解(EMD)的径流分解结果

# 3.2基于VMD的时间序列分解

利用VMD对时间序列分解结果如图4所示，原始径流序列分解为从低频到高频的多尺度子序列，充分分离了模态分量，避免混频现象以获得平稳的径流序列分量，使用传统的EMD方法确定子序列的数量，剩余参数 $\cdot y \cdot \alpha$ 分别设置为0、2000。

![](images/1323bf9372e97a42085c0e178d3a8cf781771b483a67ff7949a436ddaf4cdcbd.jpg)  
Fig.3 Runoff decomposition results based on empirical mode decomposition (EMD)   
图4基于变分模态分解(VMD)的径流分解结果  
Fig.4 Runoff decomposition results based on variational mode decomposition (VMD)

# 3.3基于DWT的时间序列分解

由于径流是离散的，故采用DWT分解径流，通过比较选用小波函数db3进行分解，DWT层数为3层，从图5可以看出，子序列由1个逼近信号(A3)和3个细节信号(D1、D2、D3)组成。逼近信号保留了原始序列中规律性较好的趋势项、周期等特征，而

# 干旱区地理

![](images/c4079e2c0cafabbaec30df2ef51b4b074f91f6f534e52ecdae1bd5c0ccf9495d.jpg)  
注：A3为逼近信号序列；D1\~D3为细节信号序列。 图5基于离散小波变换(DWT)的径流分解结果 Fig.5Runoff decomposition results based on discrete wavelet transform (DWT)

细节信号包含了更多随机信息和噪声。

结合图3、图4、图5可观察出，VMD表现出更好的噪声鲁棒性，一定程度上有效降低了EMD方法分解中模态混叠的程度，在时间序列分解上更有优势，同时改善了数据的分析效果。DWT具有良好的时频局域化特性，但高频分量的频率越高其数据规律性越差，拟合及预测精度随之越低。因此，分解方法均可提取原始序列中具有不同频率的固有信息，降低原有信号的波动性。

# 3.4预报因子优选结果

以前期径流、降水量、气温、大气环流因子等作为输入变量，利用Pearson相关系数法计算气温、降水量、径流与各序列在不同滞时下的相关性（图6)。基于相关系数优选预报因子，相关性高于0.1满足 $9 5 \%$ 置信度检验，将相关性高于0.1的序列当作预选输人项。由图6可知，各序列通过相关性检验较多，但径流预报模型输入项需要强相关性因子，部分因子相关性较高但作用重复，可能降低预测精度，故须进一步筛选[28,在相关性结果基础上再运用随机森林法获取最佳输入项。如单一模型的最佳输入项有滞时为0、1个月的降水，滞时为1个月的径流以及滞时为0、1个月的气温。同理优选各子序列的最佳输入项，构建组合模型。

运用随机森林法对各序列在不同滞时下进行大气环流因子重要性排序，选取重要性前5项的因子，时频分析方法的子序列对应的大气环流因子选取结果见表1。其中A\~S分别表示：A为大西洋副高北界 $( 5 5 ^ { \circ } { \sim } 2 5 ^ { \circ } \mathrm { W }$ ),B为北半球极涡强度指数（5区，

$0 { \sim } 3 6 0 ^ { \circ }$ ),C为西藏高原 $( 2 5 ^ { \circ } \sim 3 5 ^ { \circ } \mathrm { N } , 8 0 ^ { \circ } \sim 1 0 0 ^ { \circ } \mathrm { E } )$ ，D为太平洋区涡强度指数(2区， $1 5 0 ^ { \circ } \mathrm { E } { \sim } 1 2 0 ^ { \circ } \mathrm { W } .$ )，E为亚洲区极涡强度指数（1区， $6 0 ^ { \circ } { \sim } 1 5 0 ^ { \circ } \mathrm { E }$ )，F为东亚槽强度(CQ），G为东亚槽位置(CW），H为大西洋欧洲环流型C，I为北美区极涡强度指数(3区， $1 2 0 ^ { \circ } { \sim } 3 0 ^ { \circ }$ W),J为北半球极涡面积指数（5区， $0 { \sim } 3 6 0 ^ { \circ }$ ),K为北半球极涡中心强度(JQ)，L为北半球极涡面积指数（5区， $0 { \sim } 3 6 0 ^ { \circ }$ ),M为北半球极涡中心位置(JW），N为南方涛动指数，O为西太平洋副高西伸脊点，P为太阳黑子，Q为北美大西洋副高北界( $\mathring { ( } 1 1 0 ^ { \circ } \sim 2 0 ^ { \circ } \mathrm { W } \big )$ ，R为亚洲区极涡面积指数（1区， $6 0 ^ { \circ } { \sim } 1 5 0 ^ { \circ } \mathrm { E }$ )，S为欧亚经向环流指数 $( \mathrm { I M } , 0 { \sim } 1 5 0 ^ { \circ } \mathrm { E }$ )。综上结果选取影响中亚地区的大气环流结果部分与杨莲梅等29的研究有较好的一致性。

# 3.5预测结果

基于不同时频方法分别与LSTM建立组合预测模型，考虑预报因子与各子序列的滞后性，将优选后的预报因子作为模型的输入项，分别对各子序列预测模拟，最终预测结果为各子序列的预测值累加。为了定量分析预测的结果，采用均方根误差（RMSE）、纳什系数(NSE)和决定系数 $( R ^ { 2 } )$ 等指标来判别预测精度，并与单一BP、ELM、LSTM以及未融合大气环流因子的组合模型的预测结果进行对比分析。

3.5.1基于单一模型径流预测不同模型的评价指标见表2,对比单一模型的预报结果可知,BP、ELM、LSTM模型NSE和 $R ^ { 2 }$ 均大于0.80,但其RMSE均大于0.40。在验证期中LSTM模型NSE为0.879，相较BP、ELM模拟结果分别提高了 $8 . 7 9 \% . 4 . 2 7 \% ; R$ 为0.884，分别提高了 $2 . 2 0 \% . 1 . 3 8 \%$ ；相应的RMSE为0.505，分别降低了 $2 0 . 7 2 \% . 1 2 . 3 3 \%$ ，表明LSTM模型在径流预测中效果更佳。通过模型原理可知，BP、ELM模型存在易陷入局部最优且没有时序概念等问题，而LSTM模型通过门结构设计在处理长时间序列更具有优势，极大保留水文气象要素的完整度，其模拟预测结果更为理想。表2所示ELM模型预测结果略优于BP模型，因BP模型容易出现过拟合。图7为单一模型月径流预测结果,根据变化趋势看出，单一模型追踪月径流的动态变化有较好的结果，但是在时间序列变化极值点的预测效果均不理想，单一模型的预测能力受到径流序列波动性的影响，尤其BP模型更容易出现极值偏差，极值预测精度有限。

![](images/2525264d70fe83790470e7e2febd3ad94268cda776d5c593646603006ecd5906.jpg)  
蔡文静等：基于时频分析的LSTM组合模型径流预测  
注：VMD为变分模态分解;DWT为离散小波变换;EMD为经验模态分解。下同。   
图6基于Pearson相关系数的输入因子优选  
Fig.6 Optimization of input factor based on Pearson correlation coefficient

3.5.2基于组合模型径流预测由表2预测结果可看出采用不同分解数据预处理的LSTM组合模型，当子序列通过预测合成后的结果对比单一模型表现出较大预测性能的提升。组合模型中NSE和 $R ^ { 2 }$ 均大于0.85,且RMSE均小于0.50。EMD-LSTM模型预测精度与DWT-LSTM模型相差很小，VMD-LSTM模型分解预测精度普遍高于EMD-LSTM、

DWT-LSTM的分解预测精度，其预测效果最佳、误差最小;VMD-LSTM模型相较EMD-LSTM模型，其在验证期的NSE、 $R ^ { 2 }$ 提高幅度为 $3 . 2 2 \% , 3 . 7 5 \%$ ，RMSE降低 $1 5 . 7 5 \%$ ;运用VMD-LSTM模型进行分解预报相较DWT-LSTM模型其验证期的NSE $\cdot R ^ { 2 }$ 提高幅度为 $3 . 5 6 \% \ 、 4 . 3 3 \%$ ,RMSE降低 $1 6 . 8 5 \%$ 。说明VMD方法能有效识别并滤除原始径流序列的噪声，具有良好的非线性处理能力，改进了EMD方法存在的模态混叠问题，从而提高径流序列的平稳性及可

# 干吴区地理

# 表1原始径流序列和EMD、VMD、DWT分解子序列的大气环流因子优选结果

Tab.1 Optimization results of atmospheric circulation factors for original runoff and empirical mode decomposition,variational mode decomposition, discretewavelettransformation   

<html><body><table><tr><td>分解方法</td><td>时间序列</td><td>大气环流因子(滞时月数)</td></tr><tr><td rowspan="4">EMD</td><td>原始径流序列</td><td>G(O)、Q(O)、R(O)、D(O)、K(1)</td></tr><tr><td>IMF1</td><td>F(0)、F(3)、K(3)、C(10)C(9)</td></tr><tr><td>IMF2</td><td>K(1)、J(O)、J(6)、B(0)、L(6)</td></tr><tr><td>IMF3</td><td>E(2)、M(6)、M(7)、E(1)、N(1)</td></tr><tr><td rowspan="8">VMD</td><td>IMF4</td><td>0(0)、O(1)、P(0)、P(1)、N(O)</td></tr><tr><td>IMF5</td><td>P(0)、P(1)、P(2)、P(3)、P(5)</td></tr><tr><td>IMF6</td><td>P(O)、P(1)、N(10)、N(O)、N(1)</td></tr><tr><td>R</td><td>F(0)、F(1)、F(6)、F(7)、Q(0)</td></tr><tr><td>IMF1</td><td>A(0)、A(1)、A(2)、A(6)、A(7)</td></tr><tr><td>IMF2</td><td>B(2)、B(8)、C(1)、D(7)、E(8)</td></tr><tr><td>IMF3</td><td>F(0)、F(3)、F(6)F(9)、G(0)</td></tr><tr><td>IMF4</td><td>F(O)、F(4)、F(6)、F(8)、F(10)</td></tr><tr><td rowspan="8">DWT</td><td></td><td></td></tr><tr><td>IMF5</td><td>F(0)、F(3)、F(6)、F(9)、B(5)</td></tr><tr><td>IMF6</td><td>F(0)、F(1)、F(6)、F(7)、B(8)</td></tr><tr><td>IMF7</td><td>H(3)、I(0)、J(2)D(0)、E(6)</td></tr><tr><td>A3</td><td>L(0)、S(10)、S(7)、C(10)、O(10)</td></tr><tr><td>D1</td><td>J(1)、F(0)、F(9)Q(0)、D(1)</td></tr><tr><td>D2</td><td>F(0)、F(10)、F(9)、F(7)、Q(9)</td></tr><tr><td>D3</td><td>J(0)、J(1)、K(6)、C(0)、E(0)</td></tr></table></body></html>

注：EMD为经验模态分解；VMD为变分模态分解；DWT为离散小波变换；IMF1\~IMF7为固有模态分量；R为趋势项；A3为逼近信号序列；D1\~D3为细节信号序列；A为大西洋副高北界；B为北半球极涡强度指数；C为西藏高原；D为太平洋区涡强度指数；E为亚洲区极涡强度指数；F为东亚槽强度；G为东亚槽位置；H为大西洋欧洲环流型C；I为北美区极涡强度指数；J为北半球极涡面积指数；K为北半球极涡中心强度；L为北半球极涡面积指数；M为北半球极涡中心位置;N为南方涛动指数；O为西太平洋副高西伸脊点；P为太阳黑子；Q为北美大西洋副高北界；R为亚洲区极涡面积指数；S为欧亚经向环流指数。

预报性。

考虑预报因子对分解子序列的影响，为了对照方便，构建以气温、降水量以及前期径流为输入项的组合模型，并对比分析增加大气环流因子前后组合径流预测精度，具体评价指标见表3。增加大气环流因子前后的径流预测与原始径流对比最终模拟结果如图8所示。由表3可得，在组合模型的输入项中增加大气环流因子对径流的预测效果均有提升。EMD-LSTM模型预测验证期中NSE、 $R ^ { 2 }$ 提高了 $1 . 2 4 \% , 1 . 1 2 \%$ ,RMSE降低 $5 . 3 8 \%$ ;VMD-LSTM模型预测中NSE、 $R ^ { 2 }$ 分别提高了 $2 . 7 6 \%$ ） $3 . 6 4 \%$ ,RMSE降低 $1 4 . 0 6 \%$ ;DWT-LSTM模型预测验证期中NSE $\ 、 R ^ { 2 }$ 分别提高 $1 . 5 8 \% . 0 . 2 2 \%$ ,RMSE降低 $7 . 2 1 \%$ 。从图8中可看出，组合模型的整体趋势接近原始径流，具有较好的一致性，融入大气环流因子的组合模型在极值点预测误差较小，其中VMD-LSTM模型表现更明显。结果表明基于分解技术下大气环流因子对子序列在过程拟合与提高组合模型精度上具有较好的优越性，尤其在极值点预测中，一定程度上改善了径流模拟效果。

3.5.3预测结果对比分析不同分解方法的各子序列通过LSTM预测合成后径流精度与单一模型预测精度有差异，预测结果普遍高于单一模型，避免了单一模型预测误差过大和不稳定的缺点。不同模型径流预测值与实际值对比如图9所示，丰富预报因子的分解方法下的组合模型更接近实际值的拟合曲线，所有模型对比趋势预测研究极值表现相对较差，其原因是人类活动、气候变化等因素对径流的影响愈发强烈，导致不确定性升高，进一步增大注：BP为误差反向传播神经网络模型;ELM为极限学习机模型;LSTM为长短期记忆神经网络模型。

表2不同模型的预测性能比较  
Tab.2Comparision of prediction performances of different models   

<html><body><table><tr><td rowspan="2">模型名称</td><td colspan="3">训练期</td><td colspan="3">验证期</td></tr><tr><td>RMSE</td><td>NSE</td><td>R²</td><td>RMSE</td><td>NSE</td><td>R²</td></tr><tr><td>BP</td><td>0.514</td><td>0.833</td><td>0.845</td><td>0.637</td><td>0.808</td><td>0.865</td></tr><tr><td>ELM</td><td>0.486</td><td>0.851</td><td>0.856</td><td>0.576</td><td>0.843</td><td>0.872</td></tr><tr><td>LSTM</td><td>0.406</td><td>0.896</td><td>0.902</td><td>0.505</td><td>0.879</td><td>0.884</td></tr><tr><td>EMD-LSTM</td><td>0.307</td><td>0.940</td><td>0.941</td><td>0.457</td><td>0.901</td><td>0.906</td></tr><tr><td>VMD-LSTM</td><td>0.328</td><td>0.932</td><td>0.935</td><td>0.385</td><td>0.930</td><td>0.940</td></tr><tr><td>DWT-LSTM</td><td>0.444</td><td>0.876</td><td>0.900</td><td>0.463</td><td>0.898</td><td>0.901</td></tr></table></body></html>

注：BP为误差反向传播神经网络模型;ELM为极限学习机模型;LSTM为长短期记忆神经网络模型；EMD-LSTM为基于经验模态分解的长短期记忆神经网络组合模型;VMD-LSTM为基于变分模态分解的长短期记忆神经网络组合模型;DWT-LSTM为基于离散小波变换的长短期记忆神经网络组合模型；RMSE为均方根误差；NSE为纳什系数； $R ^ { 2 }$ 为决定系数。下同。

![](images/7800d564c34ee79703b3e7a1478e8847e5f81f76345c91e75a5f918518d1f2b2.jpg)  
图7单一模型月径流预测结果  
Fig.7Monthly runoff forecast results of single model

表3不同组合模型融合大气环流因子前后的径流预测  
Tab.3Runof predictionsbeforeandafter theatmosphericcireulationfactorsarecombinedwithdifferentcombinationmodel   

<html><body><table><tr><td rowspan="2">组合模型</td><td colspan="3">训练期</td><td colspan="3">验证期</td></tr><tr><td>RMSE</td><td>NSE</td><td>R</td><td>RMSE</td><td>NSE</td><td>R</td></tr><tr><td>EMD-LSTM</td><td>0.353→0.307</td><td>0.923→0.940</td><td>0.925→0.941</td><td>0.483→0.457</td><td>0.890→0.901</td><td>0.896→0.906</td></tr><tr><td>VMD-LSTM</td><td>0.337→0.328</td><td>0.929→0.932</td><td>0.923→0.935</td><td>0.448→0.385</td><td>0.905→0.930</td><td>0.907→0.940</td></tr><tr><td>DWT-LSTM</td><td>0.484→0.444</td><td>0.853→0.876</td><td>0.862→0.900</td><td>0.499→0.463</td><td>0.884→0.898</td><td>0.899→0.901</td></tr></table></body></html>

注：EMD-LSTM为基于经验模态分解的长短期记忆神经网络组合模型;VMD-LSTM为基于变分模态分解的长短期记忆神经 网络组合模型;DWT-LSTM为基于离散小波变换的长短期记忆神经网络组合模型。下同。

![](images/a04cd669fd64ed81eb51e3282d45ff96a4d4a4d24b199e4560b2fac3431de202.jpg)  
图8不同组合模型融合大气环流因子前后的月径流预测  
ig.8Predictionofmonthlyrunofbeforeandaftertheintegrationofdiferentcombinationmodelswithatmosphericcirulationf

了预测难度。

综上分析，组合模型的输入项中增加大气环流因子后其预测精度均高于 $8 8 \%$ ,可更深入捕获径流内在特性。其他学者也做了有关玛纳斯河径流预测的研究，刘艳等基于EEMD-ARIMA模型得到玛纳斯河年径流预测相关系数为0.956。根据单一模型与组合模型预测结果及其他研究结果对比可得，结合分解方法来提升模拟效果的有效性，且增加大气环流因子可进一步提高模型预测精度，为变化环境下非平稳序列预测提供可靠结果

![](images/192366127bb5ff84a9572af82e7dbfeff63d9e91a4fe4e348c30a2d5aa5b7fea.jpg)  
图9不同模型径流量预测值与实际值对比  
Fig.9 Comparison between predicted and measured runoff values of different models

# 4结论

本文运用时频分析、预报因子筛选和深度学习模型组合的预测方法，建立月径流预测模型，以肯斯瓦特水文站径流预测为例，对不同模型效果进行分析比较，得出以下结论：

（1）采用EMD、VMD、DWT3种分解方法均可提取原始序列中具有不同频率的固有信息，削弱了原始径流序列的非平稳性，降低了预测难度。

（2）充分利用不同频率的子序列，构建的基于时频分析的LSTM组合模型，其径流时间序列被分解为多个时间尺度分量，相对于直接将原始径流序列带入模型预测，基于分解的组合模型预测效果更理想，分解-预测-重构的方法更适用于趋势变化明显的非平稳时间序列。

（3）在EMD-LSTM、VMD-LSTM、DWT-LSTM 3个组合模型中，输入项中增加大气环流因子，使得各组合模型的预测精度均有提升，其验证期径流的NSE分别为0.901、0.930、0.898。说明筛选预报因子对子序列过程拟合优化有促进作用。其中VMD-LSTM模型在径流总体趋势和极值预测中均有良好效果，具有较强的泛化能力，其可为优化水文预报提供有效的数据驱动模型建模方法。

在深度学习神经网络模型中加入具有物理意义的大气环流因子可以有效提高模型精度，在后续的研究中可对数据进行更深层次的挖掘，实现数据的有效辨别;进一步运用优化算法调整模型参数，提高径流预测精度，获得更理想的预测结果。

# 参考文献(References)

[1]王昶.改进遗传神经网络在时间序列预测中的研究与应用[D]. 成都：四川师范大学,2O10.[Wang Chang.The research and application of improved genetic neural networks on time series prediction[D]. Chengdu: Sichuan Normal University,2010.]   
[2]程鹏,孔祥伟,罗汉,等.近60a以来祁连山中部气候变化及其 径流响应研究[J].干旱区地理,2020,43(5):1192-1201.[Cheng Peng,Kong Xiangwei, Luo Han, et al. Climate change and its runoff response in the middle section of the Qilian Mountains in the past 60O years[J]. Arid Land Geography,2020,43(5): 1192-1201.]   
[3]王晓杰,刘海隆,包安明.气候变化对玛纳斯河的径流量影响预 测模拟分析[J].冰川冻土,2012,34(5):1220-1228.[Wang Xiaojie,Liu Hailong,Bao Anming.A simulation analysis of the impact of climate change on runof in the Manas River[J]. Journal of Glaciology and Geocryology,2012,34(5): 1220-1228.]   
[4]王文,马骏.若干水文预报方法综述[J].水利水电科技进展, 2005,25(1): 56-60.[Wang Wen,Ma Jun.Review on some methods for hydrological forecasting[J]. Advances in Science and Technology of Water Resources,2005,25(1): 56-60.]   
[5]Deng Z M, Zhang X,Li D,et al. Simulation of land use/land cover change and its efects on the hydrological characteristics of the upper reaches of the Hanjiang Basin[J]. Environmental Earth Sciences,2015,73(3): 1119-1132.   
[6]Xu D M, Wang W C, Chau K W,et al. Discussion of comparison of three global optimization algorithms forcalibration of the Xinanjiang model parameters[J]. Journal of Hydroinformatics,2O13,15(1): 174-193.   
[7]孙栋元,齐广平,马彦麟,等.疏勒河干流径流变化特征研究[J] 干旱区地理,2020,43(3): 557-567.[Sun Dongyuan,Qi Guangping,Ma Yanlin,et al.Variation characteristics of runoff in the mainstream of Shule River[J].Arid Land Geography,2020,43(3): 557-567.]   
[8]张建海,张棋,许德合,等.ARIMA-LSTM组合模型在基于 SPI 干旱预测中的应用——以青海省为例[J].干旱区地理,2020, 43(4): 1004-1013.[Zhang Jianhai, Zhang Qi,Xu Dehe,et al. Application of a combined ARIMA-LSTM model based on SPI for the forecast of drought:A case study in Qinghai Province[J].Arid Land Geography,2020, 43(4): 1004-1013.]   
[9]Bojang PO, Yang TC,Pham Q B,et al. Linking singular spectrum analysisand machine learning for monthly rainfall forecasting[J]. Applied Sciences,2020,10(9): 3224,doi: 10.3390/app10093224.   
[10]Kratzert F,Klotz D,Brener C,etal. Rainfall-runoff modelling using long short-term memory (LSTM) networks[J]. Hydrology and Earth System Sciences,2018,22(11): 6005-6022.   
[11] 顾逸.基于长短期记忆循环神经网络及其结构约减变体的中长 期径流预报研究[D].武汉:华中科技大学,2018.[Gu Yi.Research on mid-long-term runofforecasting based on long-short-term memory recurrent networksand itsstructural reduction variant[D]. Wuhan: Huazhong University of Science and Technology,2018.]   
[12]冯锐.基于LSTM模型的九龙江流域径流序列预测研究[D].西 安：长安大学,2019.[Feng Rui.Predictionof series in Jiulong River Basin based on LSTM model[D].Xi'an: Chang'an University,2019.]   
[13]Peng T, Zhou JZ, Zhang C,et al. Streamflow forecasting using empirical wavelet transformand artificial neural networks[J].Water, 2017,9(6): 406,doi: 10.3390/w9060406.   
[14] Zhou JZ, Peng T, Zhang C,et al. Data pre-analysis and ensemble of various artificial neural networks for monthly streamflow forecasting[J]. Water,2018,10(5): 628,doi: 10.3390/w10050628.   
[15] Tan Q F,Lei X H, Wang X,et al.An adaptive middle and longterm runof forecast model using EEMD-ANN hybrid approach[J]. Journal of Hydrology,2018,567: 767-780.   
[16] YangW D, Wang JZ,Lu HY,et al. Hybrid wind energy forecasting and analysis system based on divide and conquer scheme: A case study in China[J]. Journal of Cleaner Production,2O19,222, doi: 10.1016/j.jclepro.2019.03.036.   
[17] Giulia N,Francesco S,Linda S. Impact of EMD decomposition and random initialisation of weights in ANN hindcasting of daily stream flow series: An empirical examination[J]. Journal of Hydrology,2011,406(3-4): 199-214.   
[18] Tayab M, Zhou JZ, Dong X H, et al. Rainfall-runoff modeling at Jinsha River Basin by integrated neural network with discrete wavelet transform[J].Meteorology and Atmospheric Physics,2019, 131(1),doi: 10.1007/s00703-017-0546-5.   
[19] 刘艳,杨耘,聂磊,等.玛纳斯河出山口径流 EEMD-ARIMA预测 [J].水土保持研究,2017,24(6):273-280,285.[Liu Yan,Yang Yun,Nie Lei, etal.The EMD-ARIA predictionofrunoffat ountain pass of Manas River[J].Research of Soil and Water Conservation,2017,24(6): 273-280,285.]   
[20] 赵力学,黄解军,程学军,等.基于VMD-BP模型的河流流量预 测方法[J].长江科学院院报,2020,37(7):47-52.[Zhao Lixue, Huang Jiejun, Cheng Xuejun, et al.A method of river flow prediction based on VMD-BP model[J].Journal of Yangtze River Scientific Research Institute,2020,37(7): 47-52.]   
[21] 柳梅英,包安明,陈曦,等.近30年玛纳斯河流域土地利用/覆 被变化对植被碳储量的影响[J].自然资源学报,2010,25(6): 926-938.[Liu Meiying,Bao Anming,Chen Xi,et al.Impact of land use/cover change on the vegetation carbon storage in the Manas River Basin between 1976 and 2O07[J]. Journal of Natural Resources,2010, 25(6): 926-938.]   
[22] 李义玲,乔木,杨小林,等.干旱区典型流域近30 a土地利用/覆 被变化和景观破碎化分析——以玛纳斯河流域为例[J].中国 沙漠,2008,28(6):1050-1057,1213.[Li Yiling,Qiao Mu,Yang Xiaolin,etal. Analysis on land use/cover change and landscape fragmentation in typical watersheds of arid zone in the last 30 years:A case of Manasi River Watershed,Xinjiang[J]. Journal of Desert Research,2008,28(6): 1050-1057,1213.]   
[23]He FF, Zhou JZ,Feng ZK,et al.A hybrid short-term load forecasting model based on variational mode decomposition and long short-term memory networks considering relevant factors with Bayesian optimization algorithm[J].Applied Energy,2019,237: 103-116.   
[24]Jegadeeshwaran R, Sugumaran V, Soman K P. Vibration based fault diagnosis of a hydraulic brake system using variational mode decomposition (VMD)[J]. Structural Durability& Health Monitoring,2014,10(1): 81-97.   
[25]Norden E H, Zheng S,Steven RL,et al. The empirical mode decomposition and the Hilbert spectrum for nonlinear and non- sta

# 干吴区地理

tionary time series analysis[J].Proceedings of the Royal Society A: Mathematical,Physical and Engineering Sciences，1998,454 (1971): 903-995.

[26] 张洪波,俞奇骏,陈克宇,等.基于小波变换的径流周期与ENSO事件响应关系研究[J].华北水利水电大学学报(自然科学 版),2016,37(4): 59-66.[Zhang Hongbo,Yu Qijun,Chen Keyu,et al.Analysis on the responding relationship between runoff period and ENSO events based on cross-wavelet transform[J]. Journal of North China University of Water Resources and Electric Power (Natural Science Edition),2016,37(4): 59-66.]

[27]Hochreiter S,Schmidhuber J.Long short-term memory[J]. Neural

Computation,1997,9(8): 1735-1780.

[28]王丽萍,李宁宁,马皓宇，等.MIC-PCA耦合算法在径流预报因 子筛选中的应用[J].中国农村水利水电，2018(9):36-41,51. [Wang Liping,Li Ningning,Ma Haoyu, et al.Research on the applicationofMIC-PCA algorithm inscreening runoff forecast factors [J]. China Rural Water and Hydropower,2O18(9): 36-41,51.]   
[29]杨莲梅,关学锋,张迎新.亚洲中部干旱区降水异常的大气环流 特征[J].干旱区研究,2018,35(2):249-259.[YangLianmei, Guan Xuefeng,Zhang Yingxin.Atmospheric circulation characteristics of precipitation anomaly in arid regions in Central Asia[J]. Arid Zone Research,2018,35(2): 249-259.]

# Runoff prediction withLSTM-based combination model on time-frequency analysis

CAI Wenjing'， CHEN Fulong'， HE Chaofei'， LUO Chengyan'， LONG Aihua $\mathbf { \Phi } _ { . } ^ { 1 , 2 }$   
(1.Collegeof WaterConservancy&ArchitecturalEngineering,Shihezi University,Sihezi832ooo,Xinjiang,Cina; 2.State Key Laboratory of Simulationand Regulationof Water Cycle in River Basin,China Instituteof Water Resources and Hydropower Research,Beijing 1OOo38,China)

Abstract: This study investigated the complex nonlinear and nonstationary characteristics of runof time series in a changing environment. We obtained accurate and reliable runoff prediction results by constructing long-short term memory (LSTM) combination models on the basis of time frequency analysis methods.The combination models were then applied to the Manas River, Xinjiang,China,a typical inland river in an arid area.Empirical mode decomposition (EMD),variational mode decomposition (VMD),and discrete wavelet transform (DWT) were first applied to decompose the original runoff series into several subsequences with diferent frequencies and characteristics. Second,we used the previous runoff, precipitation,temperature,and atmospheric circulation factors as the input variables of the LSTM model.At the same time,the optimal predictor of each subsequence was determined according to random forest clasification and the Pearson correlation coefficient.Finally,the combined models were based on a combination of VMD,EMD,and DWT with LSTM. Accordingly, they were called VMD-LSTM,EMD-LSTM,and DWT-LSTM and are proposed and applied for runofforecasting.The total output of all submodules was treated as the final forecasting result for the original runoff.A single back propagation neural network,a single extreme learning machine,and a single LSTM were adopted as comparative forecast models.The results indicated that the VMD-LSTM model had the best forecasting performance among all the models in terms of its Nash-Sutcliffe error( $\mathrm { N S E } { = } 0 . 9 3 0 \$ ，root mean square error $\mathrm { R M S E } { = } 0 . 3 8 5$ ，and coefficient of determination（ $R ^ { 2 } { = } 0 . 9 4 0 ^ { \cdot }$ ). The extreme value prediction error for the runoff of the VMD-LSTM model was within $1 5 \%$ ，and it had a good effect on the overall trend prediction and extreme value tracking regarding the runoff.This result further verified the accuracy and stability of the VMD-LSTM model. On the basis of the above results,the accuracy and stability of the VMD-LSTMmodel were further verified.Thus,on the basis of sequence decomposition，considering the influence of predictors on subsequences can help promote accurate and stable prediction results. These research results will provide a reference for river basin water resource planning and dispatching.

Key words: runof prediction; combination model; time-frequency analysis； long short-term memory