# 基于改进退化隐马尔可夫模型的设备健康诊断与寿命预测研究

刘文溢，刘勤明，叶春明，李冠林(上海理工大学 管理学院，上海 200093)

摘要：针对隐马尔可夫模型在进行设备健康诊断时与实际存在较大偏差的问题，提出了一种以似幂关系加速退化为核心的改进退化隐马尔可夫模型(DGHMM)。首先，引入退化因子描述设备衰退过程，提出的似幂关系加速退化较常规指数式加速退化而言，能更好地描述设备服役期间随着役龄增加性能的逐步下降。其次，以全局搜索能力相对较强的改进遗传算法代替常规EM算法进行参数估计，克服了EM算法易陷入局部最优的局限性。同时，针对隐马尔可夫模型时间上须服从指数分布而不能直接用以寿命预测的局限性问题，提出了一种以近似算法与Viterbi算法为基础的贪婪近似法，以寻求最大概率剩余观测为目的，动态地寻求最大概率剩余状态路径，对设备剩余寿命进行预测。最后，通过美国卡特彼勒公司液压泵数据集对所提出的方法进行验证评价。结果表明，基于改进退化隐马尔科模型的设备健康诊断与寿命预测方法在描绘设备退化、设备状态诊断准确率方面更加有效，在剩余寿命预测上亦为可行。

关键词：隐马尔可夫模型；设备退化；健康诊断；剩余寿命预测；遗传算法；近似算法 中图分类号：TP306 doi:10.19734/j.issn.1001-3695.2020.02.0067

Equipment health diagnostics and prognostics method based on improved degenerated HMM

Liu Wenyi, Liu Qinming, Ye Chunming, Li Guanlin (Business School,University ofShanghai for Science&Technology,Shanghai 20oo93,China)

Abstract: Inorder to solve the problem of large deviation between Hidden Markov Model and actual equipment health diagnosis,this paper developed an improved Degenerated Hidden Markov Model (DGHMM)withacoreof thequasi power relation.First,the modeladoptedthedegradation factors,modelingthe process ofrecesion fortheequipment'scontiuous decrease in performance.Compared with the conventional exponential acelerated degradation,the quasi power relation accelerated degradation canbeter describe the process thatthe performance of the equipment decreases gradually with the increaseof service age.Then,the improved genetic algorithmcan replace theconventional EMalgorithm for parameters' estimation,whichovercomes thelimitationthattheEMalgorithm iseasytofalintolocaloptimization.Atthesame time,in terms ofthe limitationoflifeprediction problemas aresult ofthe Hidden MarkovModel mustobey exponential distribution, an algorithm named greed &approximation based onapproximation algorithmand Viterbialgorithmcameout,and to seek maximum probabilityremaining observation,forthe purpose ofseking maximumprobabilitydynamicallysurplus state path, to predictheresidualifeofequipment.Finally,te proposedmethodisvalidatedandevaluatedwiththedatasetofcaterpilar hydraulic pumps.Theresults show that the method ofequipment health diagnosis andlife predictionbased on the improved degraded hidden Markovmodel is more effective in describing equipment's degeneration and the accuracy ofequipment state diagnosis,and is also feasible in the prediction of residual life.

Key words: hiddenMarkovmodel; degradationhealth diagnostics;residual useful lifetime; geneticalgorithm; approximation algorithm

# 0 引言

隐马尔可夫模型(hiddenMarkovmodel，HMM)作为一种统计学方法，从概率角度描述系统外在表现与隐含状态之间的关系，既能反映对象的随机性，又能反映其潜在结构，适用于处理复杂系统的建模问题，不仅在语音识别及分词方面取得了应用[,2]，在模式识别与健康诊断方面也取得了良好的效果。

Carey[3]等通过分析机械设备的振动信号首次将HMM成功应用于故障诊断领域；Wang[4等建立了包含耦合的离散时变时滞和耦合的分布时变时滞的模型运用有效技术约束不确定项，并通过数值仿真验证了方法有效性。Ma[5]等阐述了HMM在时间上存在必须强制符合指数分布的不合理性而不能直接用以剩余寿命预测。总体而言，现阶段HMM模型的研究因其自身限制也仅停留在设备健康诊断方面。

为了克服HMM模型的局限性，学者们提出了隐半马尔可夫模型(hidden semi Markov model,HSMM)，Dong[6等运用HSMM的状态驻留对设备进行了健康诊断与剩余寿命预测；Liu[7运用K-means算法及交叉验证算法确定电网退化阶段，并用HSMM对电网进行诊断及寿命预测；除此之外对基于多传感器，多输入的模型，学者们也提出了一系列方法整合传感器信号，使得模型能够更准确地进行系统的状态识别及寿命预测[8,9]。上述研究有着一个共同点，即HSMM本身依赖于先验分布，从而不可避免地存在一定程度的主观性特征。

随着对HMM及HSMM的研究逐渐深入，研究者们发现马尔可夫类模型对于状态的识别与实际依然存在较大的差异，为了得到更符合设备实际情况的模型，设备退化理论应运而生。Chen[10]等指出传统模型状态转移概率是固定的，但实际上随着设备工作时间的增加，设备损耗逐渐积累，设备的状态转移必然发生变化；Peng[1设计了三类退化因子加入到 HSMM模型当中，并对加入退化因子的模型的算法进行了重新推导，对参数进行了重估；He[2]等将三类退化因子运用到HSMM模型，并搭建柱塞泵实验台，通过实例验证了退化的有效性。上述对于设备退化的研究，大多是将退化应用到模型中并假设不同的先验分布，而对于退化因子本身的改进优化的研究还暂时空缺。

极大似然估计作为参数估计的常用方法，通过寻找使实验数据出现似然值最大的参数，来对一些复杂模型中的未知参数进行合理估计。相应地，EM算法以其相对简单，效率高的特点而被广泛应用于参数估计，但EM算法本身却具有易陷入局部最优的缺点。为了寻求拓展，越来越多的研究者将智能算法应用到参数估计领域。Yuan[13]等人用改进PSO 算法对Baum-Welch算法进行修正，获得了更加精确的参数；$\mathrm { Y u } ^ { [ 1 4 ] }$ 等将遗传算法运用到灰色模型中进行参数估计，数值结果显示，采用GA可大大提高模型预测精度；Krause[15]等采用基于遗传算法的函数逼近器估计感应电机的参数，并取得了较其他方法更好的效果；Zhang[16]等运用人工免疫算法对HMM模型进行优化，得到了辨识度最高的初始观测矩阵；Zhang[17]等运用自适应基因粒子群算法优化隐马尔可夫模型(CHMM)，得到了比传统HSMM更精确的结果。遗传算法作为全局搜索能力较强的智能寻优算法，尚未应用到马尔可夫类模型中，存在着可延展开拓的领域。

基于上述问题，首先引入退化因子，对设备衰退进行建模，得到设备退化过程的描述，并提出了一种以似幂关系加速退化为核心的DGHMM，较常规指数式加速退化而言，能更加准确地描述设备性能随役龄增加而逐渐加速下降的过程。以改进遗传算法代替常规EM算法对整个模型进行参数估计；同时，针对HMM模型不能直接用以寿命预测的局限性问题，提出了一种基于近似算法与Viterbi算法的贪婪近似法，以设备退化时状态转移概率矩阵的变化为载体去预测设备剩余寿命。最后，以美国卡特彼勒公司液压泵数据集对模型进行验证评价，结果显示，本文方法是可行的和有效的。

# 1 HMM模型

HMM模型的表达式可描述为 $\lambda = ( \pi , A , B )$ ，模型参数描述如下：a) $N$ ：状态数，状态所构成的集合为 $\{ S _ { 1 } , S _ { 2 } , S _ { 3 } \cdots S _ { N - 1 } , S _ { N } \}$ ，在任一时刻 $t$ 所处的状态为 $S _ { \mathbf { \Phi } _ { t } }$ ， $S _ { t } \in ( s _ { 1 } , s _ { 2 } , s _ { 3 } \cdots s _ { N - 1 } , s _ { N } )$ 。b) $M$ ：观测数，观测所构成的集合为 $\{ \theta _ { 1 } , \theta _ { 2 } , \theta _ { 3 } \cdots \theta _ { M - 1 } , \theta _ { M } \}$ ，任一时刻 $t$ 状态 $i _ { t }$ 产生的观测为 $o _ { t } \in ( \theta _ { 1 } , \theta _ { 2 } , \theta _ { 3 } \cdots \theta _ { M - 1 } , \theta _ { M } )$ 。c) $\pi$ ：初始状态概率分布， $\pi = ( \pi _ { 1 } , \pi _ { 2 } , \pi _ { 3 } \cdots \pi _ { N - 1 } , \pi _ { N } )$ ，其中所有概率之和为1，初始概率向量的意义为HMM开始时，即$t = 1$ 时，模型处于第 $n ( n \in ( 1 , 2 , 3 \cdots N - 1 , N ) )$ 个状态的概率。d) $A$ ：状态转移矩阵。 $A$ 是一个 $N \times N$ 的矩阵， $A = [ \alpha _ { i j } ] _ { N \times N }$ ，$\alpha _ { _ { i j } }$ 为从状态 $i$ 转移到状态 $j$ 的概率，即 $\alpha _ { _ i j } = P ( S _ { _ { t + 1 } } = j | S _ { _ t } = i )$ 且$\sum _ { j = 1 } ^ { N } \alpha _ { i j } = 1 ( i \in ( 1 , 2 , 3 \cdots N - 1 , N ) ) ~ , ~ \sum _ { i = 1 } ^ { N } \alpha _ { i j } = 1 ( j \in ( 1 , 2 , 3 \cdots N - 1 , N ) ) ~ \alpha _ { i j } = 1 - ( 3 , 1 , 2 \cdots N - 1 , N - 1 , N ) ~ .$ e） $B$ ：观测概率分布。 $B = [ b _ { j } ( K ) ] _ { N \times M }$ ，其中$b _ { j } ( K ) = P ( o _ { \iota } = \theta _ { \kappa } \mid S _ { \iota } = j ) ( j \in ( 1 , 2 , 3 \cdots N ) , K \in ( 1 , 2 , 3 \cdots M ) )$ ，且 $\sum _ { k = 1 } ^ { M } b ( k ) = 1$ 0

# 2 设备退化过程

# 2.1退化因子设计

传统HMM假定在设备整个寿命周期内，其状态转移发生的概率是不变的，而这个假设限制了HMM实际建模分析中的能力。对此，国内外学者提出了时变HMM。典型的设备退化规律可由图1所示。整个退化过程可分为A、B、C三个阶段，其中A段为平稳退化阶段，此阶段设备性能指数基本呈现稳定态势；B段为均匀退化阶段，设备性能指数呈现均匀变化；C段为加速阶段，设备性能随着寿命的推移呈现加速下降的趋势，健康状况急剧恶化，直至设备性能指标达到完全失效阈值。

![](images/81d8086bfac5a11307384fa7055587da18c48a735034a426d5e630fa9195e9c8.jpg)  
图1典型设备退化曲线

在现有大多数研究中，国内外学者们普遍将A、B、C三阶段退化过程的退化因子分别定义为常数，线性函数以及指数函数。对于指数退化阶段，普遍将相邻两时段 $t$ 与 $t + \triangle t$ 的状态内转移概率表示为

$$
\alpha _ { i i } ( t + 1 ) = \alpha _ { i i } ( t ) ^ { \phi } \quad i \in ( 1 , 2 , 3 \cdots N )
$$

其中 $\phi$ 为待估计参数，为定值。基于Peng[1对退化因子的定义，整个设备加速退化为一递归过程，对于离散时间的状态转移，定义状态退化关系式为 $f$ ，递归 $X$ 次后的内转移概率值为 $\boldsymbol { f } ^ { x }$ ，则退化函数应满足：

$$
f ^ { \scriptscriptstyle 0 } ( i ) = a _ { i i } ( t _ { e n d } )
$$

$$
f ^ { X } - f ^ { X - 1 } > f ^ { X - 1 } - f ^ { X - 2 } ( X \geq 2 )
$$

式(1)表示刚从均匀退化状态结束时设备状态内转移概率，即递归的初值，式(2)表示加速退化过程中加速的概念，即越靠近最终寿命时，设备停留在当前状态的概率下降越快。

针对加速退化关系式的定义，在分析指数递归关系式结构的基础上，提出了一种新的似幂关系式加速退化关系：

$$
\alpha _ { i i } ( t + 1 ) = \phi ^ { \alpha _ { i i } ( t ) } - 1 \qquad i \in ( 1 , 2 , 3 \cdots N )
$$

其中 $\phi$ 为待估计参数，可由历史数据估计得出，由于状态转移概率 $\alpha _ { i i } ( t )$ 恒小于1， $\phi ^ { 0 }$ 为1，则需要减去边界值得到适应后的状态转移概率。

对于选取满足递归加速退化要求的相适应参数进行指数关系与似幂关系比较，发现合理参数下的似幂关系与指数关系有着相似的递归加速退化效果，如图2所示。

![](images/2bf17cac1488510e365cb2c88e26cfe18160d28733fcbffd4e9bde5e1c5c456a.jpg)  
Fig.1Typical equipment degradation curve   
图2关系式加速退化递归示意图  
Fig.2Schematic diagram of relational accelerated degradation recursion

其中子图(a)(b)分别为满足加速退化过程且在合理参数下的指数关系及似幂关系退化示意图，粗实线为关系式的连续函数图，粗虚线为对应关系式的反函数图，点线为递归过程中状态转移概率，由图可知两种关系式具有一定程度的作用相似性。子图(c)(d)分别为当前示例合理参数下的指数关系退化过程以及似幂关系退化过程，实线表示各个单时点状态概率，虚线表示当前关系式下概率的部分退化过程。由图看出，似幂关系在表达加速退化过程中，程度优于指数关系。

# 2.2退化转移概率推算

a）平稳退化阶段，相邻两时点 $t$ 与 $t + \triangle t$ 设备保持当前状态概率的变化为定值，即

$$
\alpha _ { i i } ( t + 1 ) - \alpha _ { i i } ( t ) = \phi _ { 1 } \quad i \in ( 1 , 2 , 3 \cdots N )
$$

其中 $\phi _ { \mathrm { 1 } } \leq 0$ ，保持当前状态概率 $\alpha _ { i i } ( t )$ 减小，则由当前状态转移至其他状态的概率会随之增大，且根据比例分配给各$\alpha _ { i j } ( t )$ $( j = i + 1 , i + 2 \cdots N )$ 。则平稳退化状态下一时刻状态转移概率为

$$
\left\{ \begin{array} { l } { \displaystyle \alpha _ { i i } ( t + 1 ) = \alpha _ { i i } ( t ) + \phi _ { 1 } } \\ { \displaystyle \alpha _ { i j } ( t + 1 ) = \alpha _ { i j } ( t ) - \frac { \alpha _ { i j } ( t ) \phi _ { 1 } } { \displaystyle \sum _ { j = 1 + 1 } ^ { N } \alpha _ { i j } ( t ) } } \end{array} \right.
$$

则整个平稳退化过程某一时点的状态转移概率可由初始时刻递推得到：

$$
\left\{ \begin{array} { l l } { \displaystyle \alpha _ { i i } \left( k \triangle t \right) = \alpha _ { i i } \left( 0 \right) + k \phi _ { 1 } } \\ { \displaystyle \alpha _ { i j } \left( t + 1 \right) = \alpha _ { i j } \left( t \right) + \frac { \alpha _ { i j } \left( 0 \right) k \phi _ { 1 } } { \displaystyle \sum _ { j = 1 + 1 } ^ { N } \alpha _ { i j } \left( 0 \right) } } \end{array} \right.
$$

b)均匀退化阶段，相邻两时段 $t$ 与 $t + \triangle t$ 设备保持当前状态的概率的变化为 $\textit { t }$ 时段概率的线性值，即

$$
\begin{array} { r l } { \alpha _ { i i } ( t + 1 ) - \alpha _ { i i } ( t ) = \phi _ { 2 } \ \alpha _ { i i } ( t ) } & { { } i \in ( 1 , 2 , 3 \cdots N ) } \end{array}
$$

其中 $\phi _ { 2 } \leq 0$ ， $\alpha _ { i i } ( t )$ 减少的值同样分配给 $\alpha _ { i j } ( t )$ ：

$$
\left\{ \begin{array} { l } { \displaystyle \alpha _ { i i } ( t + 1 ) = ( \phi _ { 2 } + 1 ) \alpha _ { i i } ( t ) } \\ { \displaystyle \alpha _ { i j } ( t + 1 ) = \alpha _ { i j } ( t ) + \frac { \alpha _ { i j } ( t ) \phi _ { 2 } \alpha _ { i i } ( t ) } { \displaystyle \sum _ { j = 1 + 1 } ^ { N } \alpha _ { i j } ( t ) } } \end{array} \right.
$$

若定义平稳退化阶段结束时的时点为 $t _ { e 1 }$ ，则处于均匀退化时的某一时点的状态转移概率可描述为

$$
\left\{ \begin{array} { l l } { \alpha _ { i i } ( t _ { e 1 } + k \triangle t ) = ( \phi _ { 2 } + 1 ) ^ { k } \alpha _ { i i } ( t _ { e 1 } ) } \\ { \alpha _ { i j } ( t _ { e 1 } + k \triangle t ) = \alpha _ { i j } ( t _ { e 1 } ) + \displaystyle \frac { \alpha _ { i j } ( t _ { e 1 } ) ( ( \phi _ { 2 } + 1 ) ^ { k } - 1 ) \alpha _ { i i } ( t _ { e 1 } ) } { \displaystyle \sum _ { j = 1 + 1 } ^ { N } \alpha _ { i j } ( t _ { e 1 } ) } } \end{array} \right.
$$

c）对于本文提出的基于幂函数的加速退化阶段，相邻两时点 $t$ 与 $t + \triangle t$ 设备保持当前状态的概率的变化为 $t$ 的似幂关系

$$
\alpha _ { i i } ( t + 1 ) = \phi _ { 3 } { } ^ { \alpha _ { i i } ( t ) } - 1 \qquad i \in ( 1 , 2 , 3 \cdots N )
$$

其中 $\phi _ { 2 } > 0$ ， $\alpha _ { i i } ( t )$ 减少的值分配给 $\alpha _ { i j } ( t )$ ，则下一时刻的状态转移概率为

$$
\left\{ \begin{array} { l } { \displaystyle \alpha _ { i i } ( t + 1 ) = \phi _ { 2 } ^ { \alpha _ { i i } ( t ) } - 1 } \\ { \displaystyle \alpha _ { i j } ( t + 1 ) = \alpha _ { i j } ( t ) + \frac { \alpha _ { i j } ( t ) ( \phi _ { 2 } ^ { \alpha _ { i i } ( t ) } - 1 - \alpha _ { i i } ( t ) ) } { \displaystyle \sum _ { j = 1 + 1 } ^ { N } \alpha _ { i j } ( t ) } } \end{array} \right.
$$

同样定义均匀退化阶段结束时点为 $t _ { e 2 }$ 由于似幂关系特殊的递推形式，引用递归关系符号 $f ^ { x } ( x )$ ，其中 $X$ 表示递归次数， $x$ 表示递归概率初值，则在此加速退化阶段某一时点状态转移概率为

$$
\left\{ \begin{array} { l } { \displaystyle \alpha _ { i i } ( t + k \triangle t ) = f ^ { k } ( \alpha _ { i i } ( t _ { e 2 } ) ) } \\ { \displaystyle \alpha _ { i j } ( t + k \triangle t ) = \alpha _ { i j } ( t _ { e 2 } ) + \frac { \alpha _ { i j } ( t _ { e 2 } ) ( f ^ { k } ( \alpha _ { i i } ( t _ { e 2 } ) ) - \alpha _ { i i } ( t _ { e 2 } ) ) } { \displaystyle \sum _ { j = 1 + 1 } ^ { N } \alpha _ { i j } ( t _ { e 2 } ) } } \end{array} \right.
$$

通过设备历史数据训练后得到初始状态转移概率矩阵

$A$ ，因设备的运转退化过程在无人工干预的自然状态下是不可逆的过程，即设备状态只由停留在当前状态及由当前状态退化到更差状态，因此初始状态转移概率矩阵 $A$ 可描述为

$$
A = \left| \begin{array} { c c c c c c } { \alpha _ { 1 1 } } & { \alpha _ { 1 2 } } & { \cdots } & { \alpha _ { 1 N - 1 } } & { \alpha _ { 1 N } } \\ { 0 } & { \alpha _ { 2 2 } } & { \cdots } & { \alpha _ { 2 N - 1 } } & { \alpha _ { 2 N } } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } & { \vdots } \\ { 0 } & { 0 } & { \cdots } & { \alpha _ { N - 1 N - 1 } } & { \alpha _ { N - 1 N } } \\ { 0 } & { 0 } & { \cdots } & { 0 } & { 1 } \end{array} \right|
$$

结合上述三种退化递推式及转移概率矩阵则可推算出三个不同退化阶段中经历 $k \triangle t$ 后的状态转移概率矩阵为

$$
\begin{array} { r } { A _ { \scriptscriptstyle { k \wedge t } } = \left| \begin{array} { c c c c c } { \displaystyle \alpha _ { 1 1 } ( 0 ) + k \phi _ { \| } } & { \displaystyle \alpha _ { 1 2 } ( 0 ) + \frac { \alpha _ { 1 2 } ( 0 ) k \phi _ { \| } } { \hslash \alpha } } & { \displaystyle \ldots } & { \alpha _ { \scriptscriptstyle { 1 N } } ( 0 ) + \frac { \alpha _ { \scriptscriptstyle { 1 N } } ( 0 ) k \phi _ { \| } } { \hslash \alpha } } \\ { \displaystyle \sum _ { j = 1 + 1 } ^ { N } \alpha _ { 1 j } ( 0 ) } & & & & \\ { 0 } & { \displaystyle \alpha _ { 2 2 } ( 0 ) + k \phi _ { \| } } & { \hdots } & { \alpha _ { 2 N } ( 0 ) + \frac { \alpha _ { \scriptscriptstyle { 1 N } } ( 0 ) k \phi _ { \| } } { \hslash \alpha } } \\ { \displaystyle } & & & & { \ddots } & { \displaystyle \sum _ { j = 1 + 1 } ^ { N } \alpha _ { 1 j } ( 0 ) } \\ { 0 } & { 0 } & { \hdots } & { \vdots } & { \vdots } \\ { 0 } & { 0 } & { \hdots } & { \hdots } & { 1 } \end{array} \right| } \end{array}
$$

$$
( 0 \leq k \leq \frac { t _ { e 1 } } { \Delta x } )
$$

$$
\dot { A } _ { k , n } = \left( \begin{array} { c c c c c c c } { \displaystyle ( \phi _ { 2 } + 1 ) ^ { \frac { \kappa + \frac { 2 \kappa } { \kappa } } { \kappa } } \alpha _ { n } ^ { * } } & { \alpha _ { n } ^ { * } + \frac { \alpha _ { n } ^ { * } ( ( ( \phi _ { 2 } + 1 ) ^ { \frac { k - \kappa } { \kappa } } - 1 ) \alpha _ { n } ^ { * \kappa } } { \kappa ^ { 2 } } } & { \cdots } & { \alpha _ { \nu } ^ { * } + \frac { \alpha _ { n } ^ { * } ( ( \phi _ { 2 } + 1 ) ^ { \frac { \kappa - \frac { \kappa } { \kappa } } { \kappa } } - 1 ) \alpha _ { n } ^ { * \kappa } } { \kappa ^ { 2 } } } \\ { \vdots } & { \vdots } & { } & { } & { \vdots } \\ { \displaystyle } & { } & { } & { } & { \ddots } & { \vdots } \\ { \displaystyle } & { 0 } & { ( \phi _ { 2 } + 1 ) ^ { \frac { \kappa + \frac { \kappa } { \kappa } } { \kappa } } \alpha _ { n } ^ { * \kappa } } & { \cdots } & { \alpha _ { \nu \kappa } ^ { * } + \frac { \alpha _ { n } ^ { * } ( ( \phi _ { 2 } + 1 ) ^ { \frac { \kappa + \frac { \kappa } { \kappa } } { \kappa } } - 1 ) \alpha _ { n } ^ { * \kappa } } { \kappa ^ { 2 } } } \\ { \vdots } & { } & { } & { } & { } & { \vdots } \\ { \displaystyle } & { 0 } & { \ddots } & { \vdots } & { \vdots } \\ { \displaystyle } & { 0 } & { \cdots } & { \cdots } & { \kappa } \end{array} \right)
$$

$$
( \frac { t _ { e 1 } } { \Delta x } \leq k \leq \frac { t _ { e 2 } } { \Delta x } )
$$

$$
\begin{array} { r } { A _ { k , n } = | | \begin{array} { c c c c c c c c } { \displaystyle { f ^ { \downarrow } \xrightarrow { t _ { \mathrm { i n } } } ( \alpha _ { 1 1 } ^ { \prime \prime } ) } } & { \displaystyle { G _ { 1 2 } ^ { \prime \prime } + \frac { \alpha _ { 1 2 } ^ { \prime \prime } ( f ^ { \downarrow } ( \alpha _ { 1 2 } ^ { \prime \prime } ) - \alpha _ { 1 2 } ^ { \prime \prime } ) } { \displaystyle { \sum _ { j = 2 } ^ { \infty } \alpha _ { 1 j } ^ { \prime } } } } } & { \cdots } & { \displaystyle { G _ { 1 N } ^ { \prime \prime } + \frac { \alpha _ { 1 N } ^ { \prime \prime } ( f ^ { \downarrow } ( \alpha _ { 1 N } ^ { \prime \prime } ) - \alpha _ { 1 N } ^ { \prime \prime } ) } { \displaystyle { \sum _ { j = 2 } ^ { \infty } \alpha _ { 1 j } ^ { \prime } } } } } \\ { \displaystyle { } } & { \displaystyle { \sum _ { j = 2 } ^ { \infty } \alpha _ { 1 j } ^ { \prime \prime } } } & { \cdots } & { \displaystyle { G _ { 1 N } ^ { \prime \prime } + \frac { \alpha _ { 1 N } ^ { \prime \prime } ( f ^ { \downarrow } ( \alpha _ { 2 N } ^ { \prime \prime } ) - \alpha _ { 2 N } ^ { \prime \prime } ) } { \displaystyle { \sum _ { j = 3 } ^ { \infty } \alpha _ { 1 j } ^ { \prime } } } } } \\ { 0 } & { f ^ { \downarrow \downarrow } \xrightarrow { t _ { \mathrm { i n } } ( \alpha _ { 2 2 } ^ { \prime \prime } ) } } & { \cdots } & { \displaystyle { G _ { 2 N } ^ { \prime \prime } + \frac { \alpha _ { 2 N } ^ { \prime \prime } ( f ^ { \downarrow } ( \alpha _ { 2 N } ^ { \prime \prime } ) - \alpha _ { 2 N } ^ { \prime \prime } ) } { \displaystyle { \sum _ { j = 3 } ^ { \infty } \alpha _ { 2 j } ^ { \prime } } } } } \\ { 0 } & { 0 } & { \ddots } & { \vdots } \\ { 0 } & { 0 } & { \cdots } & { \cdots } & { 1 } \end{array} | } \end{array}
$$

$$
( \frac { t _ { e 2 } } { \Delta x } < k )
$$

上述式(10)表示从初始时点至 $t _ { e \mathrm { l } }$ 时点设备系统处于平稳退化阶段，经过 $k _ { \Delta } t$ （ $( 0 \leq k \leq \frac { t _ { e 1 } } { \Delta x } )$ 时的状态转移概率矩阵，描述为 $A _ { k \mathrm { a } t }$ 。将当 $k = \frac { t _ { e 1 } } { \Delta x }$ 时的状态转移概率矩阵记作 $A _ { t _ { e 1 } }$ ，描述为$A _ { t _ { e 1 } } = ( \alpha _ { i j } ^ { e 1 } ) _ { N \times N }$ ，其中 $\alpha _ { i j } ^ { e 1 }$ 为平稳退化阶段结束时状态转移概率矩阵的第 $i$ 行，第 $j$ 列的元素。则根据描述，可得式(11)所示设备处于均匀退化状态，且经历 $k \triangle t$ （204号 $( \frac { t _ { e 1 } } { \Delta x } < k \leq \frac { t _ { e 2 } } { \Delta x } )$ 时的状态转移概率矩阵。同样的，将当 $k = \frac { t _ { e 2 } } { \Delta x }$ 时的状态转移概率矩阵记作 $A _ { t _ { e 2 } }$ ，描述为 $A _ { t _ { e 1 } } = ( \alpha _ { i j } ^ { e 2 } ) _ { N \times N }$ ，其中 $\alpha _ { i j } ^ { e 2 }$ 为均匀退化阶段结束时状态转移概率矩阵第 $i$ 行，第 $j$ 列的元素，由此得式(12)所示系统设备处于似幂关系加速退化状态并经历了 $k \Delta t ( \frac { t _ { e 2 } } { \Delta x } < k )$ 的状态转移概率矩阵。

# 3 基于改进遗传算法的参数估计

对于极大似然估计常用的EM算法容易陷入局部最优的缺陷，本文采用了全局搜索能力更强的遗传算法进行DGHMM的参数估计，建立对数似然函数

$$
\log ( L ( \lambda , \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 } ) ) = \log ( \operatorname * { P r } ( \theta _ { 1 } , \theta _ { 2 } \cdots \theta _ { T } \mid \lambda , \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 } ) )
$$

将每组用以迭代的参数组计算而出的似然值作为单个解决方案的适应度，则每一次种群迭代的最优个体便可表示为

$$
\overline { { { \lambda } } } , \overline { { { \phi } } } _ { 1 } , \overline { { { \phi _ { 2 } } } } , \overline { { { \phi _ { 3 } } } } = \arg \operatorname* { m a x } _ { \lambda , \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 } } \log ( L ( \lambda , \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 } ) )
$$

$$
= \arg \operatorname* { m a x } _ { \lambda , \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 } } \log ( \mathrm { P r } ( \theta _ { 1 } , \theta _ { 2 } \cdots \theta _ { r } \mid \lambda , \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 } ) )
$$

在经过若干次迭代后发现 $L ( \lambda , \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 } )$ 值变化不大或达到预定迭代次数后，便输出目前较优的参数组 $\lambda , \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 }$ 。

# 3.1改进编码

本文采用混合编码策略：对于转移概率矩阵 $A ( N \times N )$ 以及观测矩阵 $B ( N \times M )$ ，首先对矩阵进行打平，由于转移概率矩阵自身的特性，则其矩阵中实际有价值的数值仅有N'+N-2个。考虑到概率值均小于1，且大部分为多位数的小数，采用十进制浮点数编码，且保留三位小数。打平后的转移概率矩阵去零去一后便是一个参数组中转移概率染色体，打平后的观测概率矩阵便是参数组中观测染色体。初始状态分布 $\pi$ 同样使用 $M$ 个位点的十进制浮点数编码染色体表示(保留三位小数)。

对于 $\phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 }$ ，考虑到整个模型对退化因子极为敏感，采用二进制的整数编码且保留五位小数。以伪18个位点的二进制整数染色体对 $\phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 }$ 的绝对值进行转换，其中第一个位点表示参数整数部分，且该位点不参与二进制与十进制的相互转换。相应地，余下的十七位在解码过程中需要缩小十万倍，然后加上首位编码数值，便得到解码后的参数。各变量编码后的染色体如图3所示。

λ三参的编码中，染色体一个位点代表了矩阵中的一个概率值，每个位点由四个部分组成。灰色部分为矩阵中单个值的整数部分，白色部分分别为该值的十分位、百分位以及千分位的值。在整个改进遗传算法流程中，单个参数组里的参数总是同时参与计算，一个参数组即为一个完整的解决方案。

![](images/b45a894a10889df6358e30a8f503046a633fab44e801c685235ca8e455edf70f.jpg)  
图3编码示意图  
Fig.3Coding diagram

# 3.2 改进交叉

对于上述改进过后的混合编码策略，相应地对交叉与变异方式进行改进。针对编码方式相似的λ三参数，设计两种不同的交叉方式1与交叉方式2。交叉方式1是交换随机两个染色体相同位点上千、百分位数和十分、整数位数，并对产生的两条新的染色体各自进行自适应归一化；交叉方式 2是交换随机两条染色体各自一部分位点，并对产生的新染色体进行自适应归一化，交叉方式1、2分别如图4、5所示。

![](images/a535d1929ea83971d296ea968034e9f543bc159a03bf2987c09eb4d594ec5da8.jpg)  
图4交叉方式1

![](images/1c49040bc7f9ff4288b7175897698709edda0cd6cdcf10588a85e88e4d4dd3a7.jpg)  
Fig.4Crossover mode 1   
图5交叉方式2  
Fig.5Crossover mode 2

由于染色体是概率矩阵打平后的产物，矩阵同行元素和为1决定了自适应归一化需要满足一定范围限制，具体的自适应归一化规则如表1所示，染色体位点从1开始计数。

表1自适应归一规则  
Tab.1 Adaptive normalization rule   

<html><body><table><tr><td rowspan="2">染色体类别</td><td colspan="2">归一化</td></tr><tr><td>组别</td><td>归一范围</td></tr><tr><td rowspan="5">转移染色体(N*N)</td><td>1</td><td>1-N</td></tr><tr><td>2</td><td>N+1—2N-1</td></tr><tr><td></td><td></td></tr><tr><td rowspan="2">N-1</td><td>N²+N-4 N²+N-2</td></tr><tr><td>2 2</td></tr><tr><td rowspan="5">观测染色体(N*M)</td><td>1</td><td>1-M</td></tr><tr><td>2</td><td>M+1—2M</td></tr><tr><td></td><td></td></tr><tr><td>N</td><td>(N-1)M+1—NM</td></tr><tr><td>1</td><td>1-N</td></tr></table></body></html>

λ三参的变异以及退化因子的交叉变异均同常规GA算法，变异操作后的归一化同样遵从表1规则。

改进后的交叉操作，利用两种不同的交叉方式，通过随机选择交叉方式，极大程度地增加了种群的多样性，增强了算法的全局搜索能力，同时在一定程度上保留了算子精度，有利于产生全局最优参数。

在算法完整运行后，使得似然函数取值最大的参数组$\lambda , \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 }$ 便是历史数据条件下，HMM 模型最优的估计参数。

# 4基于DGHMM的设备剩余寿命预测

# 4.1贪婪近似法

对于常规HMM模型的预测问题，一般存在近似算法以及Viterbi算法。现阶段研究中，普遍在得到HMM模型参数以及观测序列后运用后者计算此观测序列下概率最大的状态序列，即

$$
\overline { { I } } = \arg \operatorname* { m a x } \operatorname* { P r } ( \theta _ { 1 } , \theta _ { 2 } \cdots \theta _ { r } \mid \lambda , I )
$$

实际应用中，在需要预测设备系统剩余寿命时，往往设备还处于服役中，即此时是得不到设备从服役初期开始至失效的整个过程的观测值。为了解决这一问题，研究者们一般用同种设备历史数据加以代替并建立模型，输入服役设备的某一时点之前的观测值序列，预测其隐状态，再通过役龄时间分布来确定剩余寿命，但这与HMM模型必须服从指数分布的局限性冲突；且设备之间存在的固有差异以及设备状态的随机性，使得预测在一定程度上损失设备适应性。

因此本文在近似算法以及Viterbi 算法基础上提出一种预测剩余状态的新方法(下称贪婪近似法)。

贪婪近似法将近似算法寻求状态的思想，运用到寻找剩余观测上，即在已知HMM参数 $\lambda$ 的前提下，寻求下一时刻最有可能出现的观测值。

定义设备在第 $t$ 时刻产生观测 $\theta _ { \boldsymbol { k } }$ 的前提下，第 $t + 1$ 时刻产生观测 $\theta _ { _ { g } }$ 的概率为 $\nu _ { _ { k g } } ( t ) = P ( o _ { _ { t + 1 } } = \theta _ { _ { g } } \mid o _ { _ { t } } = \theta _ { _ { k } } , \lambda )$ $( k , g = 1 , 2 \cdots M )$ ，则 $\nu$ 的数学描述为

$$
\nu _ { k g } \left( t \right) = \sum _ { j = 1 } ^ { N } \left( b _ { j } ( g ) \sum _ { i = 1 } ^ { N } \left( \frac { b _ { i } ( k ) \alpha _ { i j } ^ { t } } { \displaystyle \sum _ { i = 1 } ^ { N } b _ { i } ( k ) } \right) \right) \ ( k , g = 1 , 2 \cdots M )
$$

其中 $\alpha _ { i j } ^ { \prime }$ 为 $t$ 时刻设备系统的状态转移概率，其如上述所说符合三阶段退化代入不同的 $k , g$ 值便能计算出从 $t$ 时刻的 $k$ 观测转移到 $_ { t + 1 }$ 时刻的 $g$ 观测的概率，由此得出间接观测转移概率矩阵为

$$
V ^ { \prime } = \left| \begin{array} { c c c c c c } { { V _ { 1 1 } ^ { \prime } } } & { { V _ { 1 2 } ^ { \prime } } } & { { \cdots } } & { { V _ { 1 M - 1 } ^ { \prime } } } & { { V _ { 1 M } ^ { \prime } } } \\ { { } } & { { } } & { { } } & { { } } & { { } } \\ { { V _ { 2 1 } ^ { \prime } } } & { { V _ { 2 2 } ^ { \prime } } } & { { \cdots } } & { { V _ { 2 M - 1 } ^ { \prime } } } & { { V _ { 2 M } ^ { \prime } } } \\ { { } } & { { } } & { { } } & { { } } & { { } } \\ { { \vdots } } & { { \vdots } } & { { \ddots } } & { { \vdots } } & { { \vdots } } \\ { { } } & { { } } & { { } } & { { } } & { { } } \\ { { V _ { M - 1 1 } ^ { \prime } } } & { { V _ { M - 1 2 } ^ { \prime } } } & { { \cdots } } & { { V _ { M - 1 M - 1 } ^ { \prime } } } & { { V _ { M - 1 M } ^ { \prime } } } \\ { { } } & { { } } & { { } } & { { } } & { { } } \\ { { V _ { M 1 } ^ { \prime } } } & { { V _ { M 2 } ^ { \prime } } } & { { \cdots } } & { { V _ { M M - 1 } ^ { \prime } } } & { { V _ { M M } ^ { \prime } } } \end{array} \right|
$$

由于状态转移矩阵 $A$ 随着监测时点逐渐退化，则 $V$ 也同样是随着时间变化的。对于某一产生观测 $\theta _ { i } ( i = 1 , 2 \cdots M )$ 的时点 $t$ ，其下一时点 $_ { t + 1 }$ 最有可能出现的观测值概率为

$$
P ( t + 1 ) = \operatorname* { m a x } _ { 1 \leq j \leq M } \nu _ { i j } ^ { t } ( i = 1 , 2 \cdots M )
$$

下一时点最优可能观测则为

$$
o _ { _ { t + 1 } } ( j ) = \arg \operatorname* { m a x } _ { 1 \leq j \leq M } \nu _ { _ { i j } } ^ { t } ( i = 1 , 2 \cdots M )
$$

则此时的观测序列为前 $t$ 个实际观测值 $O _ { o l d } = ( o _ { 1 } , o _ { 2 } \cdots o _ { t } )$ 和一个预测观测值 $o _ { t + 1 } ^ { * }$ 组成，即 $O _ { n e w } = ( o _ { 1 } , o _ { 2 } \cdots o _ { \imath } , o _ { \imath + 1 } ^ { * } )$ 。

详细的剩余状态预测步骤如下：

a)将 $O _ { o l d }$ 代入Viterbi算法求得最大概率状态路径 $R o a d _ { o l d }$ ，并记录最后一个状态值为 $s$ 。b)运用近似法求得下一时点最有可能出现的观测 $\theta ^ { * }$ ，并将其拼接到 $O _ { o l d }$ 之后形成 $O _ { \mathrm { n e w } }$ 。c）将 $\boldsymbol { O } _ { \mathrm { n e w } }$ 代入Viterbi 算法求得新的最大概率状态路径$R o a d _ { n e w }$ ，并记录最后一个状态值为 $s ^ { * }$ 。d）判断 $s$ 与 $s ^ { * }$ ，如果 $s = s ^ { * }$ ，则重复步驟 $\left[ \mathsf { b } \right) \Join \mathop { } \mathrm { d } \ j$ ；如果 $s \neq s ^ { * }$ 则至步驟e)。e）最初的 $O _ { o l d }$ 与最终的 $\boldsymbol { O } _ { n e w }$ 相减便是预测的剩余观测，输出剩余观测。

在求得剩余观测之后，运用标准Viterbi算法，代入加入剩余观测后的观测序列及模型参数，寻求当前子状态下概率最大剩余状态路径Imax 。

# 4.2设备剩余寿命预测

对于4.1节求得的最大剩余状态路径 $I _ { \mathrm { m a x } }$ ，假设当前设备处于状态 $i$ ，则在 $I _ { \mathrm { m a x } }$ 中找到处于状态 $i$ 的最后一个时间节点

$t _ { l a s t }$ ，此时的状态转移概率矩阵中第 $i$ 行的数据可由上述退化因子及初始状态转移概率矩阵推算而知，则设备的剩余寿命可表示为

$$
\mathrm { R U L } = ( t _ { l a s t } - t ) \triangle t + \frac { a _ { i i } ^ { l a s t } \triangle t } { \displaystyle \sum _ { j = i + 1 } ^ { N } a _ { i j } ^ { l a s t } } + \sum _ { j = i + 1 } ^ { N } D _ { j }
$$

式(14)中 $D _ { j }$ 为历史数据中设备处于 $j$ 状态的寿命, $a _ { i i } ^ { l a s t }$ 为当前状态 $i$ 最后一个节点时的由 $i$ 状态转向 $i$ 状态的概率值，$a _ { i j } ^ { l a s t }$ 为当前状态 $i$ 最后一个节点时的由 $i$ 状态转向 $j$ 状态的概率值。即设备总剩余寿命等于当前状态寿命余量以及后续所有状态的寿命之和。

# 5 算例分析

通过美国卡特彼勒公司液压泵的设备健康诊断与寿命预测实例来验证评价本文提出的模型与方法。实验室中设备的振动信号是由安装在与液压泵旋转轴平行位置的液压加速计收集。在应用实例中，分别对液压泵充入20、40、60 与 $8 0 \mathrm { m g }$ 的微尘，并每隔 $1 0 \mathrm { { m i n } }$ 采集一个时间大约为1min 的振动信号样本。随后使用10db的小波将振动信号分为五层，将经过降维后的小波系数作为DGHMM的输入特征序列向量。整个实验过程中，液压泵的状态可分为四种，分别为Baseline、Cont1、Cont2以及Cont3，其中Cont3状态为设备的彻底失效状态。

整个实验分析平台为Python3，平台运行环境为Windows10。

# 5.1 DGHMM数据准备

利用来自36个传感器(Sensor)的振动信号监测数据，对液压泵进行健康状态诊断以及剩余寿命预测。部分经过小波变换后的振动数据(Pump6)如表2所示。

表2Pump6 部分小波变换数据  
Tab.2Partial wavelet transform data of pump6   

<html><body><table><tr><td>时 点</td><td>Sen 1</td><td>Sen 7</td><td>Sen 15</td><td>Sen 23</td><td>Sen 32</td></tr><tr><td>1</td><td>2.62</td><td>19.53</td><td>5.66</td><td>0.06</td><td>0.96</td></tr><tr><td>3</td><td>2.65</td><td>20.24</td><td>6.10</td><td>0.06</td><td>1.04</td></tr><tr><td>5</td><td>2.39</td><td>17.45</td><td>4.92</td><td>0.06</td><td>0.87</td></tr><tr><td>7</td><td>2.07</td><td>16.15</td><td>3.98</td><td>0.06</td><td>0.75</td></tr><tr><td>9</td><td>2.25</td><td>18.53</td><td>4.51</td><td>0.06</td><td>0.81</td></tr><tr><td>11</td><td>2.24</td><td>21.44</td><td>4.38</td><td>0.06</td><td>0.87</td></tr><tr><td>13</td><td>2.41</td><td>5.37</td><td>6.84</td><td>0.08</td><td>1.66</td></tr><tr><td>15</td><td>2.58</td><td>6.16</td><td>7.96</td><td>0.09</td><td>1.84</td></tr><tr><td>17</td><td>2.53</td><td>6.07</td><td>7.63</td><td>0.09</td><td>1.84</td></tr><tr><td>19</td><td>2.44</td><td>6.24</td><td>7.71</td><td>0.10</td><td>1.84</td></tr><tr><td>21</td><td>20.66</td><td>9.68</td><td>8.42</td><td>0.11</td><td>2.17</td></tr><tr><td>23</td><td>5.06</td><td>8.75</td><td>7.20</td><td>0.10</td><td>1.89</td></tr><tr><td>25</td><td>7.53</td><td>8.82</td><td>8.15</td><td>0.10</td><td>2.00</td></tr><tr><td>27</td><td>5.74</td><td>8.37</td><td>7.19</td><td>0.10</td><td>1.89</td></tr><tr><td>29</td><td>3.46</td><td>8.25</td><td>7.16</td><td>0.10</td><td>1.92</td></tr><tr><td>31</td><td>41.78</td><td>7.98</td><td>7.12</td><td>0.15</td><td>1.86</td></tr><tr><td>33</td><td>31.08</td><td>7.90</td><td>6.98</td><td>0.14</td><td>1.84</td></tr><tr><td>35</td><td>60.15</td><td>7.99</td><td>7.03</td><td>0.15</td><td>1.85</td></tr><tr><td>37</td><td>77.27</td><td>7.80</td><td>7.12</td><td>0.17</td><td>1.84</td></tr></table></body></html>

# 5.2 实验参数估计

本文运用改进遗传算法同时对DGHMM与时变HMM进行参数估计。表3与表4分别为泵6估计参数组中初始与失效临界状态转移概率矩阵。算法中种群数量为30，交叉概率为0.7，变异概率为0.3。考虑到不同参数组下实验数据出现的概率似然值可能存在数量级差异较大的情况，通过减少种群数量、增加迭代次数来增强选择力度，相应地通过增加变异概率来保证每代种群多样性。

DGHMM与时变HMM在改进GA算法整个流程中的概率似然值迭代曲线如图6所示(Pump6)。从参数估计的结果来看，实验数据在DGHMM的较优参数组下出现的似然值大于在时变HMM的较优参数组下出现的似然值。这一结果在一定程度上可反映DGHMM较常规基于指数式加速退化的时变HMM而言，能更好地描绘实验数据。

表3Pump6初始状态转移矩阵  

<html><body><table><tr><td>state</td><td>baseline</td><td>cont1</td><td>cont2</td><td>cont3</td></tr><tr><td>baseline</td><td>0.924</td><td>0.064</td><td>0.007</td><td>0.005</td></tr><tr><td>cont1</td><td>0.000</td><td>0.783</td><td>0.128</td><td>0.089</td></tr><tr><td>cont2</td><td>0.000</td><td>0.000</td><td>0.807</td><td>0.193</td></tr><tr><td>cont3</td><td>0.000</td><td>0.000</td><td>0.000</td><td>1.000</td></tr></table></body></html>

表4Pump6失效临界状态转移矩阵

Tab.3Initial state transition matrix of pump6   

<html><body><table><tr><td>state</td><td>baseline</td><td>contl</td><td>cont2</td><td>cont3</td></tr><tr><td>baseline</td><td>0.426</td><td>0.483</td><td>0.053</td><td>0.038</td></tr><tr><td>cont1</td><td>0.000</td><td>0.361</td><td>0.377</td><td>0.262</td></tr><tr><td>cont2</td><td>0.000</td><td>0.000</td><td>0.403</td><td>0.597</td></tr><tr><td>cont3</td><td>0.000</td><td>0.000</td><td>0.000</td><td>1.000</td></tr></table></body></html>

![](images/b1898f898d6e2864dc25d88fba9453bcd58f1e97ab25fe065b010e91540f342f.jpg)  
图6Pump6 似然迭代对比图  
Fig.6Likelihood iteration comparison diagram of pump6

# 5.3 健康状态诊断

分别将泵6与泵82的实验数据向量化后输入HMM、时变HMM以及DGHMM模型，运用Viterbi算法分别求得其在各自实验观测数据和各自较优参数组下设备的最大概率状态路径并加以验证评价，结果如表5所示，泵6与泵82实验数据在不同模型下的最大概率状态路径概率值如表6所示。

表5泵6与泵82健康状态识别结果  
Tab.5Health states identification results of pump6 and pump82   
Tab.6The path probabilities of pump 6 and pump 82 under each mode   

<html><body><table><tr><td rowspan="2">类别</td><td colspan="8">pump6</td><td colspan="4">pump82</td></tr><tr><td>状态 base contl cont2 cont3 准确率</td><td></td><td></td><td></td><td></td><td></td><td>状态 base contl cont2 cont3 准确率</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="4">HMM</td><td>base</td><td>12</td><td>0</td><td>0</td><td>0</td><td>100%</td><td>base</td><td>9</td><td>0</td><td>0</td><td>0</td><td>100%</td></tr><tr><td>cont1</td><td>1</td><td>6</td><td>0 0</td><td>86%</td><td>cont1</td><td>2</td><td>8</td><td></td><td>0</td><td>0</td><td>80%</td></tr><tr><td>cont2</td><td>0</td><td>3</td><td>8</td><td>0</td><td>73%</td><td>cont2</td><td>0</td><td>4</td><td>6</td><td>0</td><td>60%</td></tr><tr><td>cont3</td><td>0</td><td>0</td><td>0</td><td>8</td><td>100%</td><td>cont3</td><td>0</td><td>0</td><td>1</td><td>11</td><td>92%</td></tr><tr><td rowspan="4">时变HMM</td><td>base</td><td>12</td><td>0</td><td>0</td><td>0</td><td>100%</td><td>base</td><td>9</td><td>0</td><td>0</td><td>0</td><td>100%</td></tr><tr><td>cont1</td><td>0</td><td>7</td><td>0</td><td>0</td><td>100%</td><td>cont1</td><td>0</td><td>10</td><td>0</td><td>0</td><td>100%</td></tr><tr><td>cont2</td><td>0</td><td>0</td><td>7</td><td>4</td><td>64%</td><td>cont2</td><td>0</td><td>0</td><td>7</td><td>3</td><td>70%</td></tr><tr><td>cont3</td><td>0</td><td>0</td><td>0</td><td>8</td><td>100%</td><td>cont3</td><td>0</td><td>0</td><td>0</td><td>12</td><td>100%</td></tr><tr><td rowspan="4">DGHMM</td><td>base</td><td>12</td><td>0</td><td>0</td><td>0</td><td>100%</td><td>base</td><td>9</td><td>0</td><td>0</td><td>0</td><td></td><td>100%</td></tr><tr><td>cont1</td><td>0</td><td>7</td><td>0</td><td>0</td><td>100%</td><td>cont1</td><td>0</td><td>10</td><td>0</td><td></td><td>0</td><td>100%</td></tr><tr><td>cont2</td><td>0</td><td>0</td><td>11</td><td>0</td><td>100%</td><td>cont2</td><td>0</td><td>0</td><td></td><td>10</td><td>0</td><td>100%</td></tr><tr><td>cont3</td><td>0</td><td>0</td><td>0</td><td>8</td><td>100%</td><td>cont3</td><td>0</td><td>0</td><td></td><td>0</td><td>12</td><td>100%</td></tr></table></body></html>

Tab.4Failure critical state transition matrix of pump6   
表6泵6与泵82在各模型下路径概率值  

<html><body><table><tr><td>类别</td><td>Pump6</td><td>Pump82</td></tr><tr><td>HMM</td><td>7.32E-11</td><td>8.16E-11</td></tr><tr><td>时变HMM</td><td>5.39E-13</td><td>1.03E-13</td></tr><tr><td>DGHMM</td><td>1.36E-13</td><td>1.77E-12</td></tr></table></body></html>

# 5.4剩余寿命预测

运用提出的贪婪近似算法以及常规Viterbi算法的设备剩余寿命预测方法，动态地求得 Pump6 与 Pump82 在DGHMM下的剩余寿命，结果由图7所示。从图中可以看出预测而出的剩余寿命值与实际剩余寿命的误差处于相对合理范围内，且当设备处于失效状态cont3时，设备停止运作，退化相应停止，模型也相应地成功识别并判定设备剩余寿命为0，虽然预测值一定程度上在Baseline与cont1状态转换处存在"滞留现象”，但整体而言，基于DGHMM的贪婪近似法对于Pump6与Pump82剩余寿命的预测是有效可行的。

![](images/cdc0f3c7be0aac976dd843a17c4bc0cf46b7d3c9c5c97b97db77617a3ea6b8a2.jpg)  
图7Pump6与pump82 剩余寿命预测图Fig.7RUL of pump6 and pump82

# 6 结束语

本文提出了一种以新加速退化为核心的设备健康诊断与剩余寿命预测方法。提出的似幂关系更保守，较同为退化因子的指数式关系而言更稳定，且能更好描述设备性能随役龄增加的逐步加速退化的过程，对于设备的状态识别也更精确;基于改进遗传算法的参数估计方法，也取得了相对较好的效果；提出的贪婪近似法一定程度上打破了常规隐马尔可夫模型时间上必须服从指数分布的束缚，能够近似地对设备的剩余寿命进行预测。因此基于改进退化隐马尔可夫模型的设备健康诊断与剩余寿命预测方法在描绘设备退化、设备状态诊断准确率方面更加有效，在剩余寿命预测上亦为可行。

本文仅将似幂关系应用到了HMM模型并验证了结果，未来应将其应用到HMM的拓展—HSMM中，进一步对似幂关系进行验证。为保证寻优效果，文中的改进遗传算法迭代次数较多，时间复杂度较高，未来也应尝试改善；且在贪婪近似法进行过程中若出现无限循环情况，还应设置相应的迭代次数限制才能完成算法相应步骤。

# 参考文献：

[1]刘群，张华平，俞鸿魁，等．基于层叠隐马模型的汉语词法分析 [J] 计算机研究与发展,2004,(08):1421-1429.(Liu Qun, Zhang Huaping, Yu Hongkui,et al.Chinese Lexical Analysis Using Cascaded Hidden Markov Model [J].Journal of Computer Research and Development, 2004,(08): 517-522.)   
[2]曹林，王东峰，刘小军，等．基于Gabor小波和HMM的人像鉴别算 法[J]．控制与决策,2005,(09):1073-1076.(Cao Lin,Wang Dongfeng, Liu Xiaojun,et al.Face Recognition Based on Gabor Wavelets and Hidden Markov Model[J].Control and Decision,2005,(09):1073-1076.)   
[3]Carey B,Dan M,Tarik A.Condition-based maintenance of machines using hidden markov models [J].Mechanic Systems and Signal

Processing,2000,14 (4): 597-612

[4] 王燕锋，李祖欣，全立地，等．具有不确定转移概率的马尔可夫复杂 网络的聚类同步[J].控制与决策,2018,33(04):741-748.(Wang Yanfeng，Li Zuxin,Quan Lidi,et al.Cluster synchronization of Markovian complex networks with uncertain transition probabilities [J]. Control and Decision,2018,33 (04): 741-748)   
[5]马伦，康建设，赵强．基于HMM的设备剩余寿命预测框架及其实现 [J]．计算机仿真,2010,27(05):88-91.(Ma Lun,Kang Jianshe,Zhao Qiang．Implementation of Equipment Residual Life Prediction Framework Based on Hidden Markov Model[J].Computer Simulation, 2010,27 (05): 88-91.)   
[6] 董明．一种基于自回归隐式半Markov链的设备健康管理新方法[J]. 中国科学：信息科学,2008,(12):2185-2198.(Dong Ming,A new device health management method based on autoregressive implicit semi-Markov chain [J]. Science in China: Information Sciences,2008, (12): 2185-2198.)   
[7]刘浅．基于动静态参数检测的高速铁路接触网剩余寿命估计 [D]. 四川：西南交通大学,2017.(Liu Qian.ResidualLife Prediction Based on Dynamic and Static Parameters of High Speed-Railway Catenary [D]. Sichuan: Southwest Jiaotong University,2017.)   
[8]Dong M.Hidden semi-Markov model based method-ology for multisensor equipment health diagnosis and prognosis [J]. European Journal of Operational Research,2007,178 (3): 858-878.   
[9]刘勤明，李亚琴，吕文元，等．基于自适应隐式半马尔可夫模型的设 备健康诊断与寿命预测方法[J].计算机集成制造系统，2016,22 (09):2187-2194.(Liu Qinming，Li Yaqin，Lyu Wenyuan，et al. Equipment health diagnostics and prognostics method based on adaptive HSMM [J]. Computer Integrated Manufacturing Systems,2016,22 (09): 2187-2194.)   
[10] Chen A,Wu G S.Real time health prognosis and dynamic preventive maintenance policy for equipment under aging Markovian deterioration [J].International Journal of Production Research.2007,45(15):3351- 3379.   
[11]彭颖．基于退化隐式半马尔可夫模型的设备健康预测及系统性维护 策略研究[D].上海：上海交通大学,2011.(Peng Ying.A Prognosis Method Using Age-Dependent Hidden Semi-Markov Model and A Systematic Maintenance Policy [D]. Shanghai: Shanghai Jiaotong University, 2011.)   
[12]何兆民，王少萍．基于时变状态转移隐半马尔可夫模型的寿命预测 [J].湖南大学学报：自然科学版,2014,41(08):47-53.(He Zhaoming, Wang Shaoping. Remaining Lifetime Prediction Based on Time-varying State Transition Probabilities of Hidden semi-Markov Model[j]. Journal of Hunan University: Natural Sciences,2014,41 (08): 47-53.)   
[13]原媛，卓东风．隐半马尔可夫模型在剩余寿命预测中的应用[J]．计 算机技术与发展，2014,24(01):184-187+191.(Yuan Yuan,Zhuo Dongfeng.ApplicationofHidden Semi-Markov Model in Prediction of Residual Life[J].Computer Technology and Development,2014,24(01): 184-187+191.)   
[14]邬丽云，吴正鹏，齐英剑．基于遗传算法的灰色区间数的 GM(1,1) 优化模型 [J]．控制与决策，2019,34(02):445-448.(Wu Liyun,Wu Zhengpeng,Qi Yingjian.GM(1,1) Model for Interval Grey Number Based on Genetic Algorithm [J]. Control and Decision,2019,34 (02): 445-448.)   
[15] Krause P,Wasynczuk O,Sudhoff S,et al.Analysis of Electric Machinery and Drive Systems [M].New York:John Wiley&Sons,lnc,2013.   
[16]张小强，朱文辉，康铁宇，等．基于人工免疫算法的离散隐马尔可夫 故障诊断模型优化[J]．装备环境工程,2019,16(01):63-67.(Zhang Xiaoqiang,Zhu Wenhui,Kang Tieyu,et al. Optimization of Discrete Hidden Markov Fault Diagnosis Model Based on Artificial Immune Algorithm [J].Equipment Environmental Engineering,2019,16 (01): 63-67.)   
[17]张西宁，雷威，杨雨薇，等．采用自适应基因粒子群算法优化隐马尔 可夫模型的方法及应用[J]．西安交通大学学报，2018,52(08):1-8. (Zhang Xining,Lei Wei,Yang Yuwei,et al.Adaptive Genetic Particle Swarm Algorithm for Optimization Hidden Markov Models with Applications [J].Journal of Xi'an Jiaotong University,2018,52(O8):1-8.)