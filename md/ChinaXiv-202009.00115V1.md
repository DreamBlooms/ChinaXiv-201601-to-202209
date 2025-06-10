# 基于最大信息传递熵的ICS因果关系建模

张仁斌a,b,c，曹宗泽a，吴克伟a

(合肥工业大学a.计算机与信息学院;b.大数据知识工程教育部重点实验室;c.工业安全与应急技术安徽省重点实验室，合肥 230601)

摘要：针对传统因果关系算法难以准确分析含大量噪声的非线性数据的问题进行了研究，提出基于最大信息传递熵的因果关系建模算法。首先，利用最大信息系数对非线性数据的时序趋势间的关联度进行检测，弱化噪声对变量间相关性的影响；然后根据筛选因子剔除弱相关变量，并通过随机经验估值计算强关联变量间的传递熵，以减少传递熵的计算量；最后，传递熵确定因果关系方向，形成支持链路溯源的单向因果网络。利用经典化工过程数据集对该算法进行测试分析，实验结果表明，相比于现有因果关系建模算法，该算法可定位异常变量，对12维以上的高维数据建模的稳定性高于 $8 5 \%$ ，因果关系的准确率可达 $8 3 . 3 3 \%$ ，实际建模效果优于对比算法，可用于工业控制系统异常检测定位。

关键词：工业控制系统；因果关系建模；最大信息传递熵；链路溯源；异常定位中图分类号：TP391.4 doi:10.19734/j.issn.1001-3695.2020.01.0033

Ics causality modeling based on maximum information transfer entropy

Zhang Renbina,b,ct, Cao Zongzea, Wu Keweia (a.SchoolofComputer Science&Information Engineering,b.KeyLaboratoryofKnowledge Engineering with Big Data,c. Anhui ProvinceKeyLaboratoryofIndustrySafety&Emergency Technology,Hefei UniversityofTechnology,HefeiAnhui 230601, China)

Abstract: This paper developedacausality modeling algorithm based on maximum informationtransfer entropyto solve the problemthat traditionalcausalityalgorithms were dificult toaccuratelyanalyze non-lineardata withalotofnoise.First,used themaximum informationcoeficienttodetectthecorrelationbetweentime series trendsofnon-lineardata.Weakentheeffect of noise on thecorrelation between variables.Secondly,eliminated weakly related variables based on sreening factors. Calculated the transfer entropy between strong corelations using stochastic empirical valuation.Thereby reducing the calculation amount of transfer entropy.Finally,transfer entropy determined causal direction.Formed aone-way causal network that supports link traceability.Testanalysisofthe algorithm using classic chemical processdata sets.Test esults showthat,comparedtoexistingalgorithms,this algorithmcanlocateabnormal variables.The stabilityofthisalgorithm for modeling high-dimensional data of more than 12 dimensions is higher than $8 5 \%$ ,and the accuracy rate of causality can reach （204号 $8 3 . 3 3 \%$ .The actual modeling efectof this algorithm is beter than thecomparison algorithms,and itcan detect and locate industrial control system abnormalities.

Key words: industrialcontrolsystem; causalitymodeling;maximum information transferentropy;ink traceability;anomaly location

# 0 引言

工业控制系统(industrialcontrol system，ICS)在工业生产控制中的广泛应用，加快了生产自动化与智能化的发展进程，也引发了很多安全问题[I。ICS中各器件普遍存在交错复杂的依赖关系，使得其物理过程中设备节点之间的相互影响变得难以分析，导致难以准确定位异常。由因果关系形成的因果图[2]可以代表信息的传播方向，允许分析人员遵循关系链路追踪异常源头[3]，因此可以使用因果图反映ICS物理层设备间的依赖关系并为高效的安防提供理论指导。

目前，一种典型的因果关系研究方法是格兰杰因果关系(grangercausality)。MaL等人[4]提出了一种基于神经网络架构的格兰杰因果分析方法，用于KPI(keyperformanceindicator)定向故障的传播路径识别。KathariS等人[5]针对多变量平稳线性动态过程提出了一种有效重构加权格兰杰因果网络的系统方法。然而，传统的格兰杰因果关系是基于系统过程的自回归模型[，适用于线性多变量过程，对于非线性因果关系不敏感。

贝叶斯网络是研究非线性数据间因果关系的经典方法之一。ZhangQ等人[7提出了一种用于动态风险评估的模糊概率贝叶斯网络，并嵌入了噪声证据过滤器，以减少噪声数据对算法的影响，但过滤噪声也造成了一定的信息损失，并且传统贝叶斯网络更适用于离散数据。为处理连续数据，YANGJing 等人[8]提出了基于PCB (partialcorrelation-based)算法的连续贝叶斯网络模型，但该模型对非线性结构数据的因果分析效果不佳。为将离散数据建模扩展为连续数据建模并且能够挖掘非线性数据中的潜在关系，曾千千等人[9]利用最大信息系数(maximum information coefficient,MIC)搭建基础关系网络框架，通过贪婪算法对MIC构造的贝叶斯网络结构进行局部优化，通过整合局部最优解生成最终的网络结构。但该方法受限于贪婪算法的局部最优特性，无法保证每次结果均为全局最优，导致建模结果不稳定。

相较于格兰杰因果性，传递熵(transfer entropy，TE)更加精确，从中得出的因果关系图在视觉上更易于解释[10]。ShiD 等人[1]针对传感器测量序列引入了基于传递熵TE的因果对策，以数据驱动的方式对其进行评估而无须依赖基础动态系统的模型。但传递熵TE的计算复杂度高，存在效率不高的问题。SuJ等人[12]通过比较连续变量的相应阈值生成离散报警序列，降低了传递熵TE的计算代价，提出了一种基于传递熵TE和修正互信息的混合方法检测变量之间直接和间接因果关系，但其算法所得结果是双向因果关系，不能完成有限长度的链路溯源及异常定位；同时将连续数据离散化为报警序列也会损失一定的原始信息。

综上所述，目前，在工业控制系统中进行因果关系建模时，主要存在以下几个问题：

a)实际生产数据往往为连续非线性且伴随大量噪声，离散化数据或滤波处理等预处理常以损失信息为代价从而影响后续精准分析。既能分析连续非线性数据又无须过滤噪声成为因果关系分析的关键问题。

b)含有回路或结果不稳定的因果关系网络，不适用于异常点排查，对同一对象多次建模的结果差异较大将给后续分析带来干扰、影响结果准确性。因此需要建模后的因果网络能够形成单向稳定链路的算法。

针对上述问题，本文提出了基于最大信息传递熵的因果关系建模算法，即 MITE-CM(maximum information transferentropycausalmodeling)。本文算法利用MIC建立相关性网络框架，以获取在时序趋势上具有强相关性的连续非线性数据，减少噪声对计算信息熵的影响；通过传递熵TE反映强相关变量间的信息传递方向，形成有利于链路溯源的单向无回路网络，并解决因果网络结构不稳定的问题。算法通过筛选机制过滤弱相关关系，减少传递熵TE部分的计算量。

# 1基于最大信息传递熵的因果关系建模算法

# 1.1MITE-CM算法

工业控制系统中的复杂关系非单一的函数关系且数据中包含大量噪声，需要普适性强、鲁棒性高的算法。受文献[13]启发，本文综合两种相关性分析方法，同时解决问题a)和问题b)。MITE-CM利用MIC指标衡量两个变量 $X$ 和Y之间线性或非线性的关联程度。MIC的普适性决定算法在样本量足够大时能够捕获多种关联，而非限定于单一的函数类型。MIC的公平性保证其在样本量足够大时，能为噪声程度相似的不同种相关关系给出相近的系数。例如，对于充满相同噪声的线性关系和正弦关系，MIC能给出相近的相关系数。因此无须对全体数据集特别进行滤波等除噪预处理，可直接计算原始数据。相比于 FPBN[7](fuzzy probability Bayesian network)等贝叶斯网络方法，MITE-CM算法允许直接处理连续数据，同时对正常噪声有良好的鲁棒性，可直接分析ICS数据间复杂多样的关联情况，可以解决问题a)。

但由于MIC的对称性，仅由MIC形成的相关性网络不具备方向性。为形成有向图，MIC-GA 算法[利用贪婪搜索将MIC网络扩展为有向因果图，却未证明其局部最优解即为系统实际因果关系，并且无法保证局部最优即为全局最优，使得准确性相对较弱。传递熵根据其不对称性建立驱动和响应间的因果关系，不需要系统模型机理的先验知识。MITE-CM算法将传递熵TE与MIC网络融合得到相对稳定准确的因果关系。首先对序列 $X$ 、Y进行网格化以此得出 $X$ 、Y之间的最大互信息，并将其归一化进而分析两序列整体趋势间的相关性；随后计算MIC 网络中的强相关关系( $m i c _ { i , j } \ge t h$ )间的传递熵，将具有较大传递熵的方向视为信息流动方向，使不具备方向性的相关性关系转换为单向的因果关系，如图1所示。

![](images/521b23d9bb50b1e545929c2b7f2c5e82255633f243a52992aab33eff134a0f39.jpg)  
图1相关性关系转换为因果关系  
Fig.1 Correlation turns into causation

对于前文归纳问题b)，MITE-CM算法以变量间的时序趋势相关性为关键特征，保留了具有强时序相关性的MIC关系，使得因果图的基本框架不易变动。此外，MITE-CM以传递熵的规则判定因果关系的方向，仅在双方信息熵大小极为接近时其所得方向才有可能改变，确保系统正常情况下建模结果差异性小。换而言之，若MITE-CM的两次建模结果出现框架差异，则系统出现异常，细节将在实验与分析中详述。而MIC-GA算法中的贪婪策略常因局部最优解不同而变更网络框架，使得多次实验结果的差异程度较大，为后续的进一步分析带来诸多干扰。与MIC-GA算法的随机性对比将在稳定性实验中做进一步说明。MITE-CM算法伪码如下所示。

算法1 MITE-CM算法

输入：数据集 $\pmb { x }$   
输出：因果关系矩阵 $\pmb { \cal E }$   
a）let $c$ be a new $N ^ { * } N$ matrix.  
b）for $\textit { i } = 1$ to $\textsf { N }$   
c） for $\textit { j } = \textbf { 1 }$ to $\textsf { N }$   
d) if $\ j \ = \ i$ （204号  
e) $c _ { i , j } \gets 0 \ \mathrm { ~ ; ~ }$   
f) else  
g） $c _ { i , j } \gets M I N E ( X _ { \cdot i } , X _ { \cdot j } ) . m i c$ ; $/ { ^ * }$ MIC系数\*/h）let $\pmb { \cal E }$ bea new $\mathsf { N } ^ { * } \mathsf { N }$ matrix.  
i) for $\textit { i } = 1$ to $\textsf { N }$   
j) for $\ j \ = \ i$ to $\textsf { N }$   
k) if $\left. \mathbf { c } _ { i , j } \right. > t h$ /\*筛选阈值 $^ { * } /$   
1) $( t _ { i  j } , t _ { j  i } )  T E ( R \_ E V M ( X _ { \cdot i } , X _ { \cdot j } , l e n ) ) ;$ （204号  
$/ { ^ * }$ 计算传递熵TE，计算传递熵所需的概率密度由R_EVM 算法得出\*/m） if $t _ { i  j } = 0$ and $t _ { j  i } = 0$   
n) ${ \mathsf { c } } _ { \mathrm { { i } } , { \mathrm { ~ j ~ } } } , { \mathsf { c } } _ { \mathrm { { j } } , { \mathrm { i } } } \gets \mathsf { \otimes } ,$ 1  
0） else if $t _ { i  j } - t _ { j  i } \mathrm { ~ } \geqslant \mathfrak { \theta }$   
p) ${ \mathsf { c } } _ { \mathrm { { i , j } } } \gets { \mathsf { 1 } } \ ;$ （  
q） else  
r） ${ \mathfrak { c } } _ { { \mathrm { j } } , { \mathrm { i } } } \gets { \mathbf { 1 } } \ ;$   
s）return E;

# 1.2R_EVM算法

工业控制系统中数据的真实概率分布通常未知，在计算传递熵TE前须近似估计变量的概率分布。相比与传统概率密度估计方法，属于非参数概率密度估计的经验估值法能处理任意形式的概率分布且不需要作出假设。本文利用经验估值法计算简单、与总体分布相关的特点分析数据整体趋势间因果关系。为减少计算量，本文将经验估值法改进为随机经验估值法R_EVM(random empirical valuation method)，首先获取待测序列 $X$ 、Y的长度 $L$ 及值域 $R$ ；其次将值域 $R$ 分割为 $p$ 个子区间；随后分别抽取待测序列 $X , ~ Y$ 的len个数据形成新的序列 $X ^ { \prime }$ ， $Y ^ { \prime }$ ；最后分别统计 $X ^ { \prime }$ 、 $Y$ 中数据落入各个自区间中的个数，以其占比代表该区间的概率密度函数值，并存储于概率密度函数数组 $P$ 中。为保证估值结果准确，确保随机选取的数据遍及待测序列的绝大部分，R_EVM算法设定len取值不小于输入序列长度 $L$ 的一半，即 $\mathrm { l e n } \geq L / 2$ 。基于R_EVM的传递熵TE统计区间分布探查变量宏观趋势间的因果性，对系统噪声不敏感，同样满足前文归纳问题a)中算法无须过滤噪声的要求。REVM算法计算传递熵公式中部分概率密度的伪码如下：

算法2 R_EVM算法 输入：序列 $x$ 和 $y$ ，区间数量 $\mathsf { p }$ ，采样总数len.

输出： $p ( x _ { t } , y _ { t } )$ ：  
a） $\Delta 1 = ( X \_ m a x - X \_ m i n ) / ( 2 * p ) ; \Delta 2$ $\bigtriangleup 2 \ =$ (Y_max - Y_min)/ $( 2 \ ^ { * } \ \mathsf { p } )$ ；  
b）pointer[] $$ random(len）;//随机生成len 个下标  
c） $\mathsf { X } _ { \mathsf { t } } [ ] \gets \mathsf { X }$ （pointer）； $\mathsf { Y } _ { \mathsf { t } } [ ] \gets \mathsf { Y }$ (pointer）； $\mathsf { Y } _ { \mathsf { t } + 1 } [ ] \gets$ Y(pointer $^ { + 1 }$ ）； $\mathsf { X } _ { \mathsf { t } + 1 } [ ] \gets \mathsf { X } ( \mathsf { p o i n t e r \ t 1 } ) \mathsf { ; }$   
d）Lx[] $$ X_min+△1 :p :X_max-△1; $\mathsf { L y } [ ] \gets \mathsf { Y } \_ { \mathsf { m i n } + \triangle 2 }$ ：p:Y_max- $\bigtriangleup 2$ : /\*分割区间，每区间间隔为△ $^ * /$   
e）stat $\mathbf { \sigma } = \mathbf { \sigma }$ zeros(p，p，3); /\*三维全零矩阵，统计数据在各区间的分布情况\*/  
f）for $\scriptstyle \mathbf { i } = 1 : { \mathsf { p } }$   
g） for $\scriptstyle \mathbf { j } = 1 : \mathsf { p }$ （204  
h) count $ \theta$ ；  
i) for $\scriptstyle \mathbf { k } = 1$ :len  
j) $\begin{array} { r } { \mathbf { i } \mathbf { f } \left( \lfloor \mathbf { x } ( \mathbf { i } ) - \mathbf { \nabla } \triangle 1 \right) \ \leqslant \ \mathsf { X } _ { \mathsf { t } } ( \mathbf { k } ) \leqslant \left( \lfloor \mathbf { x } ( \mathbf { i } ) + \mathbf { \nabla } \triangle 1 \right) } \end{array}$ （204号and $( \lfloor y ( \mathbf { j } ) - \ \triangle 2 ) \ \leqslant \ \forall _ { \mathrm { t } } ( \mathbf { k } ) \leqslant ( \lfloor y ( \mathbf { j } ) + \ \triangle 2 )$   
k) count $^ { + + }$ ；  
1) $\mathsf { s t a t } ( \mathrm { i } , \mathrm { j } , \mathsf { 3 } ) \gets \mathsf { c o u n t } \$   
m） $\begin{array} { r c l } { p ( x _ { t } , y _ { t } ) } & { = } & { \mathsf { s t a t } ( : , : , 3 ) / \mathsf { s u m } \big ( \mathsf { s u m } \big ( \mathsf { s t a t } ( : , : , 3 ) \big ) \big ) } \end{array}$   
n）return $p ( x _ { t } , y _ { t } )$ ；

由伪码可知，在计算传递熵公式的联合概率 $p ( x _ { t } , y _ { t } )$ 时，其复杂度已经达到 ${ \mathrm { O } } ( n ^ { 3 } )$ 。序列 $X ^ { \prime }$ 、 $Y$ 较短所分区间过多，导致计算效率不高；而序列 $X ^ { \prime }$ 、 $Y$ 较长所分区间较少，易使结果精度下降。因此， $p ^ { 2 }$ 与len应处于相同量级，即p/len $\approx$ 0.05。通常情况下，抽样长度 $l e n \approx 1 0 0 0$ 时，区间数 $p \approx 5 0$ 。此时，相比于传统经验估值法，R_EVM算法理论上可减少L×p²\~1.25x10次计算。相比于 BAS-TE 算法[I]将数据离散化为五类定值并计算传递熵，R_EVM中保留了原始数据的多样性，远多于五种分类的区间数 $p$ 可捕获更多的信息，使计算结果理论上更为精确，算法准确性对比将在精确性实验中讨论。此外，R_EVM存在一定随机性，但在面向整体分布分析数据的目的下该随机性在可接受范围内，具体情况将在稳定性实验中的len/L取值分析中说明。

# 1.3筛选因子

计算变量概率密度分布的复杂度较高，随着网络规模的不断增大，REVM的调用次数也呈现平方式的增长。因此，算法在计算传递熵TE前通过由筛选因子 $\alpha$ 计算出的阈值 $^ { t h }$ 过滤弱相关性的变量，再次减少REVM的计算量。本文将筛选因子 $\alpha$ 设为第二位有效数字的计数单位，筛选阈值 $t h$ 的计算公式如式(1)所示。

$$
{ \mathrm { t h } } = { \left\{ \begin{array} { l l } { \displaystyle { \left[ { \frac { a \nu e } { \alpha } } \right] } \times \alpha , a \nu e \geq 1 } \\ { \displaystyle { \left[ { \frac { a \nu e \times \alpha } { \alpha } } , a \nu e < 1 \right]}  } \end{array} \right. }
$$

其中 $\alpha$ 为筛选因子； $t h$ 为筛选阈值；[]为四舍五入取整运算;

ave为非零 $m i c _ { i , j }$ 的均值，其计算公式如式(2)所示。

$$
a \nu e = \frac { \sum m i c _ { i , j } } { n } , m i c _ { i , j } \ne 0
$$

其中， $n$ 为非零 $m i c _ { i , j }$ 总数。

若随机变量 $\mathrm { \Delta X }$ 和 $\mathrm { \Delta Y }$ 之间的MIC值大于筛选阈值th，则认为这两个变量之间存在一条边，MITE-CM算法随后计算这两个变量之间的传递熵TE。筛选因子使MIC 框架中保留了主要因果关系，同时减少弱相关性对整体网络带来的干扰，进而减少后续传递熵TE部分的计算。

# 2 实验与分析

# 2.1经典化工过程

田纳西-伊斯曼过程[14] (Tennessee-Eastman process,TEP)是经典的化工过程模型，如图2所示，它模拟了连续过程所面临的大多数挑战[15]，被广泛应用于工厂控制策略设计、多变量控制、稳态与动态优化、预测控制、自适应控制、非线性控制等领域的研究[16,17]。本文所使用的 TEP 数据为Kaspersky 仿真的TEP正常数据及其攻击测试后的异常数据[18]。

![](images/6b018f71c384e5b6931d49522658b67a3ef402e4ba72da13effa41b9f2869aa8.jpg)  
图2田纳西一伊斯曼过程图  
Fig.2Tennessee—Eastman process diagram

为充分说明本文算法对ICS物理过程数据的因果分析通用性及异常定位的普适性，本章分别测试TEP中的DDoS攻击异常数据和完整性攻击异常数据。两种异常分别来自TEP过程中的汽提塔模型和反应罐模型，如图1虚线框所示，相关变量如表1所示，实验中的筛选阈值 $t h$ 均为0.1。

表1攻击异常相关变量  
Tab.1 Attacks the exception correlation variable   

<html><body><table><tr><td>符号</td><td>名称</td><td>符号</td><td>名称</td></tr><tr><td>S4</td><td>A+CFeed</td><td>V1</td><td>Stripper Liquid Product Flow</td></tr><tr><td>S10</td><td>Sep Underflow</td><td>V2</td><td>Stripper Steam Flow</td></tr><tr><td>S11</td><td>Stripper Underflow</td><td>RT</td><td>Recator Temperature</td></tr><tr><td>P</td><td>Stripper Pressure</td><td>RF</td><td>RecatorFeed</td></tr><tr><td>T</td><td>StripperTemperature</td><td>RP</td><td>Recator Proseeure</td></tr><tr><td>F</td><td>Steam Flow</td><td>RL</td><td>RecatorLevel</td></tr><tr><td>L</td><td>Stripper Level</td><td>ReF</td><td>Recycle Flow</td></tr></table></body></html>

# 2.2汽提塔因果分析及DDoS攻击检测

通过对汽提塔变量进行计算得到的因果关系网络如图3(a)所示。汽提塔内部的因果关系从控制阀 $\mathit { V I }$ 展开，并且与汽提塔的压力指示器 $P$ 、温度指示器 $T$ 、进料流 $\mathit { s l0 }$ 和液位水平 $L$ 产生了直接因果关系。同时，压力指示器 $P$ 、温度指示器 $T$ 和汽提塔下溢流量计 $F$ 又分别延伸出各自的因果关系，从而形成了许多类似"产量阀 $\mathit { V I } \to$ 汽提塔内压力 $P \to$ 汽提塔内液位水平 $L ^ { ' }$ “的级联因果关系。在系统正常运行时，控制阀 $\scriptstyle { V 2 }$ 、流量 $S 4$ 和 $_ { S I I }$ 与其他节点的数据波形不具备明显相似性 $( m i c \textit { } _ { i , j } < t h )$ ，因此不存在因果关系。其余因果关系均符合模型正常运行时的生产逻辑，算法因果建模具备合理性。

本文算法测试DDoS攻击后一场数据的因果网络如图3(b)所示。对比攻击前后， $_ { S I I }$ 从与其他节点没有因果关系变为与 $\mathit { V I }$ 和 $L$ 存在直接因果关系，新增了因果关系 ${ ^ { \circ } V I } \to S I I { ^ { \circ } } $ 和 ${ } ^ { \ast } L \to S I I { } ^ { , , }$ ，而因果关系“ $\cdot V I \to S I O ^ { , }$ 也随之消失，其余的因果关系保持不变。由此推断，主要异常节点为 $\mathit { V I }$ 、S11和 $L$ ，节点 $\mathit { S l O }$ 为受影响节点，由异常节点溯源可得异常链路Track，分析结果如表2所示。Kaspersky数据集显示，节点S11、 $L$ 和 $\mathit { V I }$ 中包含异常数据，与推测结果一致。说明因果关系的变动可以作为评判异常的标准之一，而本算法对因果关系变动的敏感性使其能够定位异常节点。

![](images/b99f7bb56bb97905075df07bc66c60199f2f32d838b6291c67d557cc2bfbae95.jpg)  
图3汽提塔因果关系Fig.3Stripper causality表2汽提塔异常情况

Tab.2Stripper abnormal condition   

<html><body><table><tr><td>集合</td><td>节点元素</td></tr><tr><td>Abnormal_set</td><td>S11;L;V1</td></tr><tr><td>Impact_set</td><td>S10</td></tr><tr><td rowspan="3">Track</td><td>V1→S11;V1→P→L→S11;</td></tr><tr><td>V1→T→L→SI1;V1→L→S11;</td></tr><tr><td>V1→P→L;V1→T→L;V1→L;V1</td></tr></table></body></html>

# 2.3反应罐因果分析及异常溯源对照

再次对TEP中反应罐变量测试，系统正常运行下反应罐变量存在的因果关系，结果如图4(a)所示。

![](images/250c9bd5bf2b0d664cd506e0611a02f6cac7cf1d450aada798c886daffc0cb4b.jpg)  
图4反应罐因果关系

算法得出以D进料阀为初始异常的因果关系网络，如图4(b)所示。对比攻击前后因果关系，新增因果关系“ $S 4 \to R E F ^ { \prime }$ 中： $R T  R E F ^ {   } R T  R F ^ { , }$ ，缺失因果关系“ $R P  R T ^ { \prime }$ “ $R E F $ RT”" $\cdot _ { R T }  S 4 ^ { \prime }$ ，以新增关系的节点为异常点，以消失关系的上游节点为受影响点，二者交集同样视为异常点。

本次以因果关系的增加与消失(框架差异)作为异常的传播路径new_Track，统计结果如表3所示。生成的新型异常路径与MFM-SDG算法[19]对反应罐异常分析得到的路径“ $R F $ $R T \to R P ^ { \prime \prime }$ 中所含节点一致，但方向相反。这是由于本算法考虑信息的“流动”方向，通常下游节点具有更高的信息熵，而信息熵较高的节点多为工艺流程顺序中的上游节点。因此将路径倒置后，两算法溯源结果相同，再次证实MITE-CM对因果关系异常敏感，算法准确度较高。由于MFM-SDG算法将多个节点(MV1\~MV6设为初始异常，而Kaspersky此次攻击测试的数据中仅将D进料阀节点(MV1)设为异常，因此本算法所得故障路径的逆序集合包含于MFM-SDG算法异常路径集合。

# 表3反应罐异常情况

Tab.3Reaction tank anomaly   

<html><body><table><tr><td>集合</td><td>节点元素</td></tr><tr><td>Abnormal_set</td><td>RT;S4;RF</td></tr><tr><td>Impact_set</td><td>REF;RP</td></tr><tr><td>new_Track</td><td>RT→S4;REF→RT;</td></tr><tr><td></td><td>RP→RT→RF</td></tr></table></body></html>

综上所述，在TEP中使用不同攻击后的异常数据测试算法，实验结果表明，根据MITE-CM算法在不同时刻建立的因果关系模型判断系统中的因果关系变更，可定位工业控制系统多种异常节点。

# 3 算法对比分析

将本文算法实验结果分别与MIC-GA(Maximuminformation coefficient-Greedy Algorithm）算法[9]、BAS-TE(Binary Alarm Sequence - Transfer Entropy)算法[l]和 TE-CMI(Transfer Entropy-Conditional Mutual Information)算法[20]的实验结果进行对比，相关变量如表4所示，MEAS和MV分别表示变量类型为测量变量和控制变量。

表4部分TEP过程变量  
Tab.4Partial TEP process variables   

<html><body><table><tr><td>符号</td><td>名称</td><td>单位</td><td>类别</td></tr><tr><td>Stream 4</td><td>A+C Feed</td><td>kscmh</td><td>MEAS</td></tr><tr><td>Stream 6</td><td>Reactor Feed</td><td>kscmh</td><td>MEAS</td></tr><tr><td>Stream 8</td><td>RecycleFlow</td><td>kscmh</td><td>MEAS</td></tr><tr><td>Stream 10</td><td>Sep Underflow</td><td>m'/h</td><td>MEAS</td></tr><tr><td>Stream 11</td><td>Stripper Underflow</td><td>m'/h</td><td>MEAS</td></tr><tr><td>Valve 1</td><td>AFeedFlow</td><td>%</td><td>MV</td></tr><tr><td>Valve 9</td><td>Purge Flow</td><td>%</td><td>MV</td></tr><tr><td>level</td><td>Stripper Level</td><td>%</td><td>MEAS</td></tr></table></body></html>

# 3.1功能性分析

本文算法与BAS-TE 算法[I的实验结果进行了对比，当本文算法的筛选阈值 $^ { t h }$ 为0.060时，结果与BAS-TE算法结果近似。实验结果如图5所示。

![](images/18d96cbbe5ec76d74b9ec3a11d0f0675dfafce575b728bfc5b47c4a7f139311f.jpg)  
Fig.4Reaction tank causality   
图5因果关系对比图  
Fig.5Causal correlation diagram

由图5(a)可知，BAS-TE算法生成的因果关系网络产生了环状链路。从定位异常节点的角度来看，本文算法生成的无回路因果网络更有利于揭示ICS物理过程数据之间的因果关系，并根据信息的流向进行溯源。当系统的物理过程数据出现异常时，本文算法能够通过单向无回路的因果网络追溯异常源节点，而BAS-TE算法的结果中存在类似"Stream4 $$ $l e \nu e l  S t r e a m { l } \theta  S t r e a m { 4 }$ 的回路致使其溯源陷入死循环。

# 3.2准确性分析

文献[20]将其实验结果与工艺流程进行了对比，而本算法则从信息熵的角度挖掘变量之间的因果控制关系，因此文本将实验结果与各器件间的实际因果逻辑进行对比，分析算法结果真实性。本文将文献[11]的实验节点Stream4、Stream10、Stream11和level作为数据集A，文献[20]的实验节点Stream6、Stream8、Stream10、Stream11、Valve1和Valve9作为数据集B，其真实因果逻辑分别如图6(a)和图7(a)所示。各算法在两数据集合上的因果关系网络如图6、7所示。相对于实际因果关系，虚线为算法求得的间接因果关系。为便于分析，本文采用文献[11]中的对比方式，仅讨论实线所代表的直接因果关系。

![](images/07ed327b1cdc2aa90ea7b7705ed37bb25b4e933a99d094d9cf94069b613d153e.jpg)  
图6基于数据集A的结果对比图

![](images/bc030f937c15629062b20916947e31d188c7c2b990c1656e1c6842cbc0b91f5c.jpg)  
Fig.6Results comparison diagram based on dataset A

性，即

$$
A = { \frac { c } { s } }
$$

其中， $A$ 表示准确率； $\boldsymbol { c }$ 表示与实际因果逻辑中相同的边数；  
$s$ 表示全部可能的边数。

本文根据该真实性评判标准得到各项分类衡量指标，如表5所示，本文算法在准确率上明显优于BAS-TE 算法[I],略低于TE-CMI算法[20]，整体水平较好。本文算法得出的因果关系根据信息流向确定，而MIC-GA算法[9则依据局部最优解确定因果方向，缺乏信息熵依据，准确率低，可靠性相对较差。

表5各项分类衡量指标对比  
Tab.5Comparison of various classification measures   

<html><body><table><tr><td>算法</td><td>准确率</td><td>召回率</td><td>精确率</td><td>F1</td><td>数据</td></tr><tr><td>BAS-TE</td><td>0.4167</td><td>0.6000</td><td>0.3750</td><td>0.4615</td><td>A</td></tr><tr><td>MIC-GA</td><td>0.3000</td><td>0.2000</td><td>0.2000</td><td>0.2000</td><td>A</td></tr><tr><td>TE-CMI</td><td>0.7500</td><td>0.6000</td><td>0.7500</td><td>0.6667</td><td>A</td></tr><tr><td>本算法</td><td>0.8333</td><td>0.8000</td><td>0.8000</td><td>0.8000</td><td>A</td></tr><tr><td>BAS-TE</td><td>0.7333</td><td>0.7500</td><td>0.5000</td><td>0.6000</td><td>B</td></tr><tr><td>MIC-GA</td><td>0.5333</td><td>0.1250</td><td>0.1250</td><td>0.1250</td><td>B</td></tr><tr><td>TE-CMI</td><td>0.9333</td><td>0.7500</td><td>1.0000</td><td>0.8571</td><td>B</td></tr><tr><td>本算法</td><td>0.8333</td><td>0.6250</td><td>0.7143</td><td>0.6667</td><td>B</td></tr></table></body></html>

# 3.3稳定性分析

本算法通过预设预测序列长度len减少计算量，却也带来了一定程度的不稳定性。多次实验表明，预设长度len与输入序列 $X$ 、Y的长度 $L$ 的比值影响算法结果的稳定性。因此，本文设计了稳定性指标 $s$ 以反映算法结果的稳定性，其计算公式为

$$
S { = } 1 { - } \frac { { \displaystyle \sum _ { \mathrm { i } } ^ { M } } \frac { \triangle x } { M } } { E } \times 1 0 0 \%
$$

式(4)中， $s$ 为稳定性比值； $\triangle x _ { i }$ 为第 $i$ 次结果与第一次结果中的不同边数，即变化边数； $M$ 为重复实验的次数； $E$ 为网络中的单向有效边数，即mici $_ j > t h$ 的总数。

当本算法的len/L比值分别近似为 $0 . 5 , 0 . 7 5 , 0 . 8 , 1$ 时，在不同维度(参与计算的节点数)的数据集下的稳定性折线图如图8所示，测试数据为前3万条数据，步长为 $6 0 ( L { = } 1 ; 6 0$ =30000)。

![](images/46cf6ed89ebb2df2ebb9a9e628c4f5e2d61ff92fc0c03316302474322be2fcec.jpg)  
图7基于数据集B的结果对比图 Fig.7Results comparison diagram based on dataset B 文献[20]将算法所得结果的准确率(accuracy)视为其真实   
图8不同len/L取值的稳定性折线图  
Fig.8The stability line graph of different len/L values

随着len/L的增大，算法稳定性趋于恒定。但由于6维数据的有效边较少，稳定性偶尔较差。由于MIC-GA算法[9]的同样是以MIC参数为基础构造因果网络，本文选取该比值的最低限度 $( l e n / L = 0 . 5 )$ 与 MIC-GA 算法进行稳定性对比(MIC阈值均设置为 $t h = 0 . 1$ )，结果如图9所示。测试数据为全部12万条数据，步长为 $6 0 ( L = 1 : 6 0 : 1 2 0 0 0 0 )$ 。

![](images/2e9048ad08f868e2c4199998d8ff83c7703ca296943127b9283f946fde9c5938.jpg)  
图9算法稳定性对比  
Fig.9Algorithm stability comparison

MIC-GA算法结果在维数较低时稳定性极高，但当数据维度增大后，其稳定性大幅降低，后逐渐回升。由于维数为6时的有效边很少(仅3条边)，本算法平均0.8的变化边数占有效边比重相对较大。但随着维数的增加，算法稳定性增强且在24维以后均高于对比算法，总体稳定性更好。

# 4 结束语

考虑到ICS物理过程数据的非线性以及其中包含的大量噪声数据等因素，本文提出了基于最大信息传递熵的因果关系建模算法MITE-CM。算法利用MIC检测系统时序趋势之间的相关性强弱，构造接近于理论逻辑的初始网络结构，并结合传递熵TE判定网络间的信息流动方向形成因果关系网络。实验结果表明，本文算法可敏锐的捕捉到ICS物理过程数据中的异常因果关系，其结果的准确率比BAS-TE 算法结果高出 $3 5 . 7 4 \%$ ，具有较好的真实性；在24维及以上的高维数据中，算法所得模型的稳定性均高于相同数据集下的MIC-GA 算法。但本文算法整体的计算复杂度较高，后期工作将主要针对MIC的算法进行优化，以提高算法整体计算效率。

# 参考文献：

[1]Zhou Wer,Jia Yan,Peng Anni,etal. The effect of iot new features on security and privacy:New threats,existing solutions,and challenges yet to be solved[J].IEEE Internet of Things Journal,2018,6(2):1606-1616.   
[2]Bauer M,Cox JW,Caveness M H,et al.Finding the Direction of Disturbance Propagation in a Chemical Process Using Transfer Entropy [J].IEEE Trans on Control Systems Technology,2007,15(1):12-21.   
[3]Yang F,Xiao D.Progress in Root Cause and Fault Propagation Analysis ofLarge-Scale Industrial Processes [J]. Journal of Control Science and Engineering,2012,2012:1-10.   
[4]Ma Liang,Dong Jie,Peng Kaixiang.A novel key performance indicator oriented hierarchical monitoring and propagation path identification framework for complex industrial processes [J].ISA transactions,2019: 1275-1279.   
[5]Kathari S,Tangirala A K.Efficient Reconstruction of Granger-Causal Networks in Linear Multivariable Dynamical Processes [J].Industrial & Engineering Chemistry Research,2019,58 (26):11275-11294.   
[6]Granger C WJ.Investigating Causal Relations by Econometric Models and Cross-spectral Methods [J]. Econometrica,1969,37 (3): 424-438.   
[7]Zhang Qi, Zhou Chunjie,Tian Yuchu,et al.A fuzzy probability bayesian network approach for dynamic cybersecurity risk assessment in industrial control systems [J].IEEE Trans on Industrial Informatics,2017, 14 (6): 2497-2506.   
[8]Yang Jing,Cao Jiajian.Application of continuous Bayesian network model in cross-sectional survey data.Computer Engineering and Applications,2014,50 (19): 192-198.   
[9]曾千千，曾安，潘丹，等．基于最大信息系数的贝叶斯网络结构学习 算法[J].计算机工程,2017,43(8):225-230.(Zeng Qianqian, Zeng An,Pan Dan,et al. Bayesian network structure learning algorithm based on maximal information coeficient [J]. Computer Engineering,2017,43 (8): 225-230.)   
[10] Lindner B,Auret L,Bauer M,et al. Comparative analysis of Granger causality and transfer entropy to present a decision flow for the applicationofoscilationdiagnosis[J].Journal ofProcess ontrol019, 79: 72-84.   
[11] Shi Dawei,Guo Ziyang,Johansson KH, et al. Causality countermeasures for anomaly detection in cyber-physical systems [J].IEEE Trans on Automatic Control,2017,63 (2): 386-401.   
[12] Su Jianjun,Wang Dezheng, Zhang Yinong,et al. Capturing causality for fault diagnosis based on multi-valued alarm series using transfer entropy [J]. Entropy,2017,19 (12): 663.   
[13]麦桂珍，彭世国，洪英汉，等．混合加噪声模型与条件独立性检测的 因果方向推断算法[J].计算机应用研究,2019,36(06):1688-1692. (Mai Guizhen,Peng Shiguo,Hong YingHan,et al. Causation inference based on combining additive noise model and conditional independence [J].Application Research of Computers,2019,36 (06): 1688-1692.)   
[14] Downs JJ, Vogel E F.A plant-wide industrial process control problem [J]. Computers & chemical engineering,1993,17(3): 245-255.   
[15] CapaciF, Vanhatalo E,Kulahci M,et al.The revised Tennessee Eastman process simulator as testbed for SPC and DoE methods[J].Quality Engineering,2019,31 (2): 212-229.   
[16] Liu Kangling,Fei Zhengshun, Yue Boxuan，et al. Adaptive sparse principal component analysis for enhanced process monitoring and fault isolation [J]. Chemometrics and Intelligent Laboratory Systems,2015, 146: 426-436.   
[17] Vanhatalo E,Kulahci M,Bergquist B.On the structure of dynamic principal component analysis used in statistical process monitoring [J]. Chemometrics and IntelligentLaboratory Systems,2017,167: 1-11.   
[18] Kaspersky.TEP59[EB/OL].[2019-7-12].https://ox.kaspersky. com/d/56ad570fca/   
[19] Reinartz C, Kirchhübel D,Ravn O,et al. Generation of Signed Directed Graphs Using Functional Models [J].IFAC-PapersOnLine,2019,52 (11): 37-42.   
[20] Yu Weijun, Yang Fan. Detection of Causality between Process Variables Based on Industrial Alarm Data Using Transfer Entropy[J].Entropy, 2015,17 (12): 5868-5887.