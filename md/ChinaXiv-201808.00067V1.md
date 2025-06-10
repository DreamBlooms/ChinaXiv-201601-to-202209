# 基于贝塞尔函数的莱斯因子矩估计算法改进

何怡刚，刘楚环，袁莉芬(合肥工业大学 电气与自动化工程学院，合肥 230009)

摘要：针对传统的莱斯K因子一二阶矩估计方法因贝塞尔函数存在计算复杂度大、实用性低的问题，提出一种基于贝塞尔函数阶数的莱斯因子矩估计算法。该算法首先根据原矩估计公式计算K值对应的矩估计值，然后根据不同阶数的贝塞尔近似公式计算矩估计值并求解对应的K值，计算估计准确率，进而确定贝塞尔函数阶数的选择，简化矩估计算法。实验研究表明，所提方法与原方法相比降低了时耗，在K值较小效果更优。

关键词：莱斯因子；矩估计；贝塞尔函数；阶数选取 中图分类号：TN929.5 doi:10.3969/j.issn.1001-3695.2018.04.0320

# Improvement of moments estimation for Rice factor based on Bessel functions

He Yigang,Liu Chuhuan, Yuan Lifen (SchoolofElectricalEngineering&Automation,Hefei UniversityofTechnology,Hefei23o09,China)

Abstract:Aimingat the problemof highcomplexityand low practicabilitycaused bythe Bessel functions inthe traditional first-and second-order moments estimationalgorithm,this paper proposedan improved moments estimation method basedon theorderselectionofBesselfunction.Firstly,thisalgorithmcalculatedthemomentsestimationvaluecorrespondingtodifferent K byusing original estimation formula,thencalculated moments estimation value with Bessel functionof diferentorders, furthersolvedthecorrespondingKvalueanditsstimationaccracy,finallydeterminedtheorderofBesselfunctionacquired andimproved the estimation method.Experimental results show that the improved method obtains good performance in time consuming, especially for small K.

Key words:Rice factor; moments estimation;Bessel functions; order selection

# 0 引言

莱斯信道是无线通信信道常用的一种典型信道模型，用来描述接收信号的统计时变特性[1]。莱斯信道的接收信号包括直视路径分量和散射路径分量[2]。莱斯因子 $K$ 体现了莱斯信道中直视分量功率和散射分量功率的比例关系，是表征信道衰落程度和链路预算的重要参数[3.4]。莱斯因子越大，信道质量越好，因此莱斯因子 $K$ 的提取对分析信道模型具有非常重要的意义。

基于信号包络的矩估计方法是提取信道莱斯因子的重要方法。这类方法原理简单，不利用相位信息，不需要莱斯信道的先验知识，大大降低了计算复杂度，对算法的健壮性具有很大优势。近年来，很多研究人员都在 $K$ 因子的矩估计方面做了大量贡献和研究。文献[5提出基于包络的二、四阶矩估计方法；文献[6]提出基于包络的一、二阶矩估计方法，这两种方法通过将 $K$ 的函数等价于所测的包络矩的比率来求取 $K$ 值；文献[7]提出基于时间序列数据的 $K$ 因子矩估计方法；文献[8]对文献[7]的方法的有效性进行验证，并研究了环境对 $K$ 因子的影响；文献[9]对文献[7]中的方法深入研究，将背景噪声和干扰功率纳入模型，得到一个改进的矩估计算法，提高了 $K$ 因子的估计精度；文献[10]根据文献[6]中近似方程导出 $K$ 因子的一个显式的矩估计方法；文献[11\~13]提出一种二、四阶矩的 $K$ 因子闭合估计。文献[11，12]仿真表明文献[6]提出的一、二阶包络矩估计方法在归一化偏差和渐进方差性能优于二、四阶矩估计方法；文献[13]比较这两种矩估计方法，存在下面异同：二、四阶矩的估计方法耗时稍少于一、二阶矩的方法，一、二阶矩的估计方法精度要高于二、四阶矩的估计方法。其主要原因在于：一、二阶矩估计方法中含有贝塞尔函数，函数本身阶次高、计算复杂，且不能用初等函数计算 $K$ 因子的解析形式；而二、四阶方法表达式整体阶次较低，能够求解出 $K$ 因子的解析形式，导致二、四阶矩方法耗时小于一、二阶矩；其次一、二阶矩估计是基于对时间序列数据的一阶和二阶矩计算，使得莱斯包络精度很高。因此，如果能够得到一种高效的贝塞尔函数拟合方法，则能在不影响一、二阶矩估计方法的计算精度的前提下降低耗时，提高算法的效率。因此，本文通过对贝塞尔函数进行多项式拟合，提出了改进的基于一、二阶矩估计贝塞尔函数的莱斯 $K$ 因子提取方法。利用莱斯分布信号的一二阶矩与莱斯 $K$ 因子之间的函数关系，结合无线信道莱斯 $K$ 因子的取值范围先验值，以此逼近贝塞尔函数，降低贝塞尔函数阶数，进而降低整个表达式的阶数，提高算法效率。

# 1 矩估计方法

# 1.1莱斯信道

莱斯信道中直视路径的信道系数并不随时间变化，在信号入射波满足各角度均匀入射的条件下，其概率密度函数为

$$
f _ { r , \theta } ( r , \theta ) = \frac { r } { 2 \pi \sigma ^ { 2 } } \exp \Biggl \{ - \frac { r ^ { 2 } + A ^ { 2 } - 2 r A \cos ( \theta - \theta _ { 0 } ) } { 2 \sigma ^ { 2 } } \Biggr \}
$$

其中： ${ r , \theta , \theta _ { 0 } }$ 分别表示信道内信号的衰落幅度、各径的相位和直视路径的相位， $A$ 为视距路径分量的包络，利用上式对相位进行积分可得到信道增益的包络分布函数：

$$
p d f _ { r } ( r ) = \frac { r } { \sigma ^ { 2 } } \exp ( - \frac { r ^ { 2 } + A ^ { 2 } } { 2 \sigma ^ { 2 } } ) I _ { 0 } ( \frac { r A } { \sigma ^ { 2 } } ) , r \geq 0
$$

其中： $I _ { 0 } ( \cdot )$ 为第一类零阶修正贝塞尔函数，莱斯分布随机变量的均方值为 ${ \overline { { r ^ { 2 } } } } = A ^ { 2 } + 2 \sigma ^ { 2 }$ ， $A ^ { 2 }$ 、 $2 \sigma ^ { 2 }$ 分别表示了视距分量功率和漫射分量功率。信道的莱斯因子定义为[14]

$$
K = { A ^ { 2 } } / { 2 \sigma ^ { 2 } }
$$

则式（2）可以改写为

$$
p d f _ { r } ( r ) = \frac { r } { \sigma ^ { 2 } } \exp [ - ( \frac { r ^ { 2 } } { \sigma ^ { 2 } } + K ) ] I _ { 0 } ( \sqrt { 2 K } r / \sigma ) , r \geq 0
$$

# 1.2莱斯因子的矩估计法

莱斯分布变量的各阶矩表示如下[13]：

$$
\mu _ { n } = E [ r ^ { n } ] = ( \sigma ^ { 2 } ) ^ { n / 2 } \Gamma ( n / 2 + 1 ) \exp ( - K ) _ { 1 } F _ { 1 } ( n / 2 + 1 ; 1 ; K )
$$

其中： $\Gamma ( \cdot )$ 是伽玛函数， ${ } _ { 1 } F _ { 1 }$ 为合流超几何函数。可以看出矩估计与参数 $K$ 和 $\sigma$ 有关，因此要确定 $K$ 的值，矩估计的方法要求至少估计出 $r$ 的两个不同的矩，常用的有一阶矩、二阶矩和四阶矩，由式（5）计算可得

$$
\mu _ { 1 } = E [ r ] = \sqrt { \pi } ( \sigma ^ { 2 } ) ^ { 1 / 2 } \exp ( - K ) _ { 1 } F _ { 1 } ( 3 / 2 ; 1 ; K )
$$

$$
\mu _ { 2 } = E [ r ^ { 2 } ] = \sigma ^ { 2 } + A ^ { 2 } = \sigma ^ { 2 } ( K + 1 )
$$

$$
\mu _ { 4 } = E [ r ^ { 4 } ] = 2 \sigma ^ { 4 } + 4 \sigma ^ { 2 } A ^ { 2 } + A ^ { 4 }
$$

利用式(6)(7)可得一、二阶矩与 $K$ 的关系式：

$$
f _ { 1 2 } ( K ) = \frac { \pi e ^ { - K } } { 4 ( K + 1 ) } [ ( K + 1 ) I _ { 0 } ( \frac { K } { 2 } ) + K I _ { 1 } ( \frac { K } { 2 } ) ] ^ { 2 }
$$

基本一、二阶矩估计算法流程如图1所示。

![](images/93a9136b25eb53712fd341b22f567b6e563e800c1ead2c6c1ed8a1b1f78f2117.jpg)  
图1一二阶矩估计算法流程

# 2 贝塞尔函数多项式拟合阶数的选择

# 2.1贝塞尔函数近似公式变量的取值范围

在式（9）中，由于含有贝塞尔函数，不能用初等函数计算$K$ 因子的解析形式，使得一二阶矩估计的计算量大大增加，时效性差，因此在实际应用中较少使用，无法发挥一、二阶矩的估计方法精度优势。若对贝塞尔函数进行多项式拟合，在精度损失很小时，则能够有效降低一、二阶矩估计的复杂度，而损失的精度不影响估计性能。

第一类修正贝塞尔函数表达式为

$$
I _ { 0 } ( x ) = \sum _ { n = 0 } ^ { \infty } { \frac { x ^ { 2 n } } { 2 ^ { 2 n } { ( n ! ) } ^ { 2 } } } = 1 + { \frac { x ^ { 2 } } { 4 } } + { \frac { x ^ { 4 } } { 6 4 } } + \ldots
$$

$$
I _ { 1 } ( x ) = ( \frac { x } { 2 } ) \sum _ { n = 0 } ^ { \infty } \frac { x ^ { 2 n } } { 2 ^ { 2 n } n ! \Gamma ( n + 2 ) } = \frac { x } { 2 } + \frac { x ^ { 3 } } { 1 6 } + \frac { x ^ { 5 } } { 3 8 4 } + . . . .
$$

其中： $\Gamma$ 为伽玛函数。

文献[15，16]提出如下公式近似 $I _ { 0 } ( x )$ 和 $I _ { 1 } ( x )$ ：

$$
I _ { 0 } ( x ) \approx \left\{ \begin{array} { l l } { \displaystyle 1 + \frac { x ^ { 2 } } { 4 } + \frac { x ^ { 4 } } { 6 4 } , 0 \leq x \leq 2 . 5 } \\ { \displaystyle e ^ { 1 . 1 x } / 1 . 9 x , x > 2 . 5 } \end{array} \right.
$$

$$
I _ { 1 } ( x ) \approx \left\{ \begin{array} { l l } { \displaystyle \frac { x } { 2 } + \frac { x ^ { 3 } } { 1 6 } + \frac { x ^ { 5 } } { 3 8 4 } , 0 \leq x \leq 2 . 5 } \\ { \displaystyle \frac { e ^ { x } } { 2 . 5 \sqrt { x } } , x > 2 . 5 } \end{array} \right.
$$

$I _ { 0 } ( x )$ 的近似式和理论值进行了比较，得出 $0 \leq x \leq 2 . 5$ 范围内时，近似值与理论值几乎重合，误差可以忽略， $I _ { 1 } ( x )$ 的近似式和理论值比较，同样在 $0 \leq x \leq 2 . 5$ 时，两者几乎重合。因此，如果变量研究范围为 $0 \leq x \leq 2 . 5$ ，则当贝塞尔近似函数的阶次选取合适的情况下，可以用式（11）和（12）代替贝塞尔函数对莱斯 $K$ 因子进行估计。

$$
I _ { 0 } ( x ) = 1 + \frac { x ^ { 2 } } { 4 } + \frac { x ^ { 4 } } { 6 4 } + . . . , 0 \leq x \leq 2 . 5
$$

$$
I _ { 1 } ( x ) = \frac { x } { 2 } + \frac { x ^ { 3 } } { 1 6 } + . . . , 0 \leq x \leq 2 . 5
$$

将式（11）（12）代入到式（9）中，可得莱斯因子 $K$ 的范围是 $0 \leq K \leq 5$ ，因此，当实际莱斯信道的莱斯 $K$ 因子在$0 \leq K \leq 5$ 范围内时，如果阶次选取合适，则完全可以利用贝塞尔函数的近似函数式取代贝塞尔函数，简化莱斯信道 $K$ 因子的提取。

# 2.2贝塞尔函数近似公式阶数的选择

贝塞尔近似函数的阶次对估计精度存在影响，且通常阶次越高，精度越高，算法也越复杂。为保证莱斯 $\mathrm { ~ k ~ }$ 因子的精度满足信道特征提取性能需求，并尽可能的降低算法的复杂度，如何选出最佳贝塞尔近似函数的阶次显得十分重要。据此，本文的贝塞尔近似函数阶次的选择流程如图2所示。具体表述为：

a）计算基于贝塞尔函数的不同K值时所对应的一、二阶矩估计值;b）计算所选取阶次的贝塞尔近似函数一、二阶矩，并以此计算对应的莱斯因子估R值；c）比较理论 $K$ 值与估R值，计算其相对误差，如果误差在允许范围之内，则选取的阶次可用于估计莱斯因子，否则阶次加1，然后重复步骤b)。

图3和4分别是零阶贝塞尔函数和一阶贝塞尔函数近似式与理论值的比较，由图3可以看出 $K$ 在[0,5]内，2阶近似式误差较大，4阶和6阶能较好跟踪理论值；图4中，3阶近似式与理论值较小，5阶和7阶基本上与理论值重合。

![](images/f83aa086432575ba7053349dca32cf2c1da4dccc4400826027eae029b377df74.jpg)  
图2贝塞尔近似公式阶数选取流程

![](images/316e7842d254ea5860a876389f0bdf47f30bb24a656fab24351018a7541fa369.jpg)  
图3不同零阶贝塞尔函数近似式与理论值曲线

![](images/141239bd6e6087503fecac4268b97d9f9948eefd4d61054343e11f8c575cc795.jpg)  
图4不同一阶贝塞尔函数近似式与理论值曲线

# 3 实验仿真分析

# 3.1 $K$ 有效性评价

为了对贝塞尔函数近似式选取不同阶数计算得到 $K$ 值进行有效性评价，本文主要以准确率作为对 $K$ 的不同取值长度估算的有效性进行评价：

a）准确率 $D : ~ D = \frac { m } { L } { \times } 1 0 0 \%$ ， $L$ 表示莱斯因子 $K$ 的取值长度， $m$ 表示选取阶数分别 $^ { n 1 , n 2 }$ 贝塞尔函数近似公式在 $K$ 长度为 $L$ 内估计的 $\hat { K }$ 值与原一二阶矩估计得到 $K$ 值完全相同的个数。

b)均方根误差RM $\cdot S E \colon _ { R M S E } = { \sqrt { \frac { \sum _ { i = 1 } ^ { N } ( X _ { o , i } - X _ { m , i } ) ^ { 2 } } { N } } }$ ，其中 $N$ 表示取值长度 $L$ 内的样本数， $X _ { o , i }$ 表示第 $i$ 个样本观测值， $X _ { m , i }$ 表示第 $i$ 个理论值。

# 3.2仿真结果

本文第一类零阶修正贝塞尔函数阶数选择为4和6,，第一类一阶修正贝塞尔函数阶数选择3和5，对其进行组合，得到第一类零阶修正贝塞尔函数阶数为4、第一类一阶修正贝塞尔函数阶数为3，第一类零阶修正贝塞尔函数阶数为4、第一类一阶修正贝塞尔函数阶数为5，第一类零阶修正贝塞尔函数阶数为6、第一类一阶修正贝塞尔函数阶数为3和第一类零阶修正贝塞尔函数阶数为6、第一类一阶修正贝塞尔函数阶数为5共4种组合，具体公式如下：

组合1： $\left\{ \begin{array} { l } { \displaystyle { I _ { 0 } ( x ) = 1 + \frac { x ^ { 2 } } { 4 } + \frac { x ^ { 4 } } { 6 4 } } } \\ { \displaystyle { I _ { 1 } ( x ) = \frac { x } { 2 } + \frac { x ^ { 3 } } { 1 6 } } } \end{array} \right. , 0 \leq x \leq 2 . 5$ 组合2： $\begin{array} { l } { \displaystyle { \left\{ I _ { 0 } ( x ) = 1 + \frac { x ^ { 2 } } { 4 } + \frac { x ^ { 4 } } { 6 4 } \right. } } \\ { \displaystyle { \left. I _ { 1 } ( x ) = \frac { x } { 2 } + \frac { x ^ { 3 } } { 1 6 } + \frac { x ^ { 5 } } { 3 8 4 } \right. } } \end{array} , 0 \leq x \leq 2 . 5 \$ 组合3: $\begin{array} { l } { \displaystyle { \left\{ I _ { 0 } ( x ) = 1 + \frac { x ^ { 2 } } { 4 } + \frac { x ^ { 4 } } { 6 4 } + \frac { x ^ { 6 } } { 2 3 0 4 } _ { , 0 \leq x \leq 2 . 5 } \right. } } \\ { \displaystyle { \left. I _ { 1 } ( x ) = \frac { x } { 2 } + \frac { x ^ { 3 } } { 1 6 } \right. } } \end{array}$ 组合4; $\begin{array} { l } { \displaystyle { \left\{ I _ { 0 } ( x ) = 1 + \frac { x ^ { 2 } } { 4 } + \frac { x ^ { 4 } } { 6 4 } + \frac { x ^ { 6 } } { 2 3 0 4 } _ { , 0 \leq x \leq 2 . 5 } \right. } } \\ { \displaystyle { I _ { 1 } ( x ) = \frac { x } { 2 } + \frac { x ^ { 3 } } { 1 6 } + \frac { x ^ { 5 } } { 3 8 4 } } } \end{array}$

分别对组合 $\boldsymbol { 1 } ^ { \sim } \boldsymbol { 4 }$ 得到的贝塞尔近似公式计算出不同值时对应一二阶矩估计值以及原一二阶矩公式计算出不同值时对应的一二阶矩值，,其中 $f _ { 1 2 }$ 表示原始一二阶矩估计公式对应不同 $K$ 时计算值， $f _ { 1 2 4 3 }$ 表示组合1对应不同 $K$ 时的计算值， $f _ { 1 2 4 5 }$ 表示组合2对应不同 $K$ 时的计算值， $f _ { 1 2 6 3 }$ 表示组合3对应不同时$K$ 的计算值， $f _ { 1 2 6 5 }$ 表示组合4对应不同 $K$ 时的计算值，仿真$K$ 值的步长取0.2，仿真结果如图5所示。

由图5可以看出，不同组合的值与原一二阶计算值的精度随着 $K$ 取值范围长度变化而改变，在区间 $0 \leq K \leq 2$ 内，组合1、2、3、4计算值与原一二阶计算值基本相等，在区间 $0 \le K \le 4$ 内，组合4计算值与原一二阶矩计算值一致，组合2、3、1计算精度依次降低，不能满足精度要求。随着 $K$ 取值的增大，组合1、2、3、4曲线偏离理论值，组合1偏离最大，组合4的偏离最小，效果最优。

![](images/b4bfd3bc8bb45672795a8d4423f76a4e3ed66b7dbdf4e6f56ac6743642dff30a.jpg)  
图54组合对应的矩估计值

![](images/667fa0fdc3306910cc893f2448f5d92494f5156658de4bde085ca8788cfc2422.jpg)  
图64种组合求解出的莱斯 $K$ 值

根据求得的近似矩估计值求解对应的莱斯因子 $K$ 值，与原$K$ 值比较，其中 $K _ { _ { 1 2 4 3 } } K _ { _ { 1 2 4 5 } } K _ { 1 2 6 3 } K _ { 1 2 6 5 }$ 分别是组合1、2、3、4对应估计得到的 $K$ 值，表1给出了四种组合 $K$ 不同取值范围的均方根误差。

表14组合对应的不同取值范围的均方根误差  

<html><body><table><tr><td>K</td><td>K1243</td><td>K1245</td><td>K1263</td><td>K1265</td></tr><tr><td>(0,2)</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>(0.4）0.5760</td><td>0.0643</td><td>0.3539</td><td>0</td><td></td></tr><tr><td>(0,5)</td><td>2.7760</td><td>0.6375</td><td>1.8339</td><td>0.0231</td></tr><tr><td>表2</td><td>4种组合对应的不同取值范围的准确率(%)</td><td></td><td></td><td></td></tr><tr><td>K</td><td>K1243</td><td>K1245</td><td>K1263</td><td>K1265</td></tr><tr><td>(0,2)</td><td>100</td><td>100</td><td>100</td><td>100</td></tr><tr><td>(0,4)</td><td>52.38</td><td>66.67</td><td>52.38</td><td>100</td></tr><tr><td>(0,5)</td><td>42.31</td><td>53.85</td><td>42.31</td><td>84.62</td></tr></table></body></html>

由图6、表1和2可以看出，在 $0 \leq K \leq 2$ 区间内，组合1、2、3、4计算得到的 $K$ 均方根误差为0，准确率均为 $1 0 0 \%$ ，在$0 \le K \le 4$ 区间内，组合1均方根误差值最大，组合3均方根根误差次之，这两种方法的准确率相同，组合2估计得到 $K$ 值的均方根误差和准确率优于组合1和3，组合4均方根误差为0,估计准确率为 $1 0 0 \%$ ，在该区间内能够完全准确估计出 $K$ 值，在区间 $0 \leq K \leq 5$ 内，相比前两个区间，均方根误差都相对增大，准确率相对下降，组合4优于其他组合1、2、3。

# 3.3 复杂度分析

组合 $\boldsymbol { 1 } ^ { \sim } \boldsymbol { 4 }$ 的最高阶数分别为4、5、6、6，本文为保证贝塞尔函数的计算精度，选取的阶数为 $1 0 ^ { [ 2 ] }$ ， $K$ 步长为0.2，在$0 \leq K \leq 2$ 区间内，组合 $\boldsymbol { 1 } ^ { \sim } \boldsymbol { 4 }$ 计算得到的均方根误差为0，组合1的阶数最低，在估计效果相同的情况下选择组合1来近似一二阶矩估计公式，最高阶数为4，在很大程度上降低计算复杂度；在 $0 \le K \le 4$ 区间内，组合1和3两种方法的准确率相同，但组合1均方根误差较大，组合2估计得到均方根误差和准确率优于组合1和3， $K$ 值稍大于2时可以选择使用组合4，组合4均方根误差为0，估计准确率为 $1 0 0 \%$ ，在该区间内能够完全准确估计出值，选择组合4作为该区间的一二阶矩估计公式阶数为6阶，降低计算复杂度。4种组合算法及原始算法耗时如表3所示。

表34种组合算法及原始算法耗时(ms)   

<html><body><table><tr><td>K</td><td>K12</td><td>K1243</td><td>K1245</td><td>K1263</td><td>K1265</td></tr><tr><td>(0,2)</td><td>4.0</td><td>0.0794</td><td>0.0862</td><td>0.0929</td><td>0.1013</td></tr><tr><td>(0,4)</td><td>4.2</td><td>0.0964</td><td>0.1014</td><td>0.1087</td><td>0.1212</td></tr><tr><td>(0,5)</td><td>4.3</td><td>0.1023</td><td>0.1073</td><td>0.1228</td><td>0.1269</td></tr></table></body></html>

由表3可以看出，4种组合算法的计算时间明显要小于原一二阶矩估计算法运行时间，根据 $K$ 区间选取贝塞尔函数的阶数，降低矩估计算法的计算复杂度，实现算法的优化改进。

# 4 结束语

针对一二阶矩估计公式中贝塞尔函数阶次较高导致计算复杂度高的问题，提出一种基于贝塞尔函数近似式阶数的选取方法的莱斯 $K$ 因子的一二阶矩估计算法。通过对本文构建的4种不同组合仿真实验，验证了 $K$ 值取值区间在0-4内能够保证K估计准确的前提下贝塞尔近似式阶数选取小于理论选择的阶数，减少了算法的运行时间，提高了算法时效性，实现了算法的改进。

# 参考文献：

[1]Leturc X,Ciblat P,Martret C JL.Estimation of the Ricean K-factor from noisy complex channel coefficients [C]//Proc of Asilomar Conference on Signals,Systems and Computers.2017:1092-1096.   
[2]Salah MBB, Samet A.Moment-based joint estimation of Ricean K-factor and SNR over linearly-modulated wireless SIMO channels [M].Kluwer Academic Publishers,2016.   
[3]Bousnina I,BelliliF, Samet A,et al.Joint estimation of the Ricean K-factor and the SNR for SIMO systems using higher order statistics [C]//Proc of IEEE Global Telecommunications Conference.2011: 1-5.   
[4]Chen Y,Beaulieu N C.Estimation of Ricean K parameter and local average SNR from noisy correlated channel samples [J].IEEE Trans on Wireless Communications,2007,6(2): 640-648.   
[5]Rastogi PK,Holt O.On detecting reflections in presence of scattering from amplitude statistics with application to D,region partial reflections [J]. Radio Science,2016,16(6): 1431-1443.   
[6] Talukdar K K,Lawing W D.Estimation of the parameters of the Rice distribution [J]. Journal of the Acoustical Society of America,1991,89 (3): 1193-1197.   
[7]Greenstein LJ,Michelson D G,Erceg V.Moment-method estimation of the Ricean K-factor[J].IEEE Communications Letters,1999,3(6):175-16.   
[8]Greenstein L J,Ghassemzadeh S S,Erceg V,et al.Ricean K-factors in narrow-band fixed wireless channels:theory,experiments,and statistical models [J].IEEE Trans on Vehicular Technology,2009,58(8): 4000-4012.   
[9]Xing P,Zhang T,Zeng X.A modified algorithm of Ricean factor K estimation forL-DACS1 system [C]//Proc of International Symposium on Microwave,Antenna,Propagation and Emc Technologies for Wireless Communications.2013: 6-10.   
[10] Azemi G,SenadjiB,Boashash B.Estimating the Ricean K-factor for mobile communication applications [C]// Proc of the 7th International Symposium on Signal Processing & Its Applications.2003: 311-314.   
[11] Tepedelenlioglu C,Abdi A, Giannakis G B,et al.Performance analysis of moment-based estimators for the K parameter of the Rice fading distribution [C]// Proc of International Conference on Acoustics,Speech,and Signal Processing. 2001: 2521-2524.   
[12] Tepedelenlioglu C,Abdi A, Giannakis G B.The Ricean K factor: estimation and performance analysis [J]. IEEE Trans on Wireless Communications, 2003,2(4): 799-810.   
[13] Kong Deqiang,Liu Zuoxue,Cui Can,et al.Ricean factor estimation and performance analysis [Cl// Proc of international forum on computer science technology and applications.2009: 27-30.   
[14] Aejaz S MH, Haselmayr W, Springer A. RSSI-based parameter estimation for Rician fading environments on wireless sensor nodes [C]/ Proc of International Workshop on Factory Communication Systems.2017: 1-7.   
[15]庄铭杰．计算机仿真无线 Rice 衰落信道的实现方法[J]．电波科学学报, 2004,19 (5): 632-637.(Zhuang Mingjie.Implementation method of wireless Rice fading channels with computer simulation [J].Chinese Journal ofRadio Science,2004,19(5): 632-637.)   
[16] LeeJSand MillerLE.CDMA系统工程手册[M].北京：人民邮电出版 社,2002.   
[17] Sasaoka N,Adachi Y, Itoh Y.K factor estimation for MIMO multipath chanels [C]// Proc of International Conference on Digital Signal Processing. 2015: 1081-1084.   
[18] Saito K,TakadaJI, Kim M.Dense multipath component characteristics in 11GHz-band Indoor environments [C]// Proc of the 1Oth European Conference on Antennas & Propagation,2016: 1-3.   
[19] Tariq SAM,Despins C,Affes S,et al.Experimental resultsofRician Kfactor and co-polarization ratio of 6O GHz wireless channel in an underground mine gallery [C]// Proc of International Conference on Ubiquitous Wireless Broadband.2015:1-5.