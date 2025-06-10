# 基于Givens变换和二阶振荡W-C-PSO优化的盲源分离算法

张华伟，张天骐，刘董华(重庆邮电大学 信号与信息处理重庆市重点实验室，重庆 400065)

摘要：针对智能算法在实现盲源分离时容易陷入局部最优，且收敛速度缓慢的问题，提出了一种基于Givens 变换和二阶振荡粒子群优化的盲源分离算法。该算法首先将惯性权重与学习因子两个参数构造函数关系，使之共同调节算法迭代，来提高算法的整体性与全局搜索能力；再引入二阶振荡环节增加种群的多样性，这样算法不易陷入局部最优；此外，采用Givens 变换将分离矩阵转换成旋转角度表示形式，来降低算法的复杂度。仿真表明，该算法能有效实现机械振动信号和语音信号的盲分离，并且相比较其他算法具有更快的收敛速度和更好的分离性能。

关键词：盲源分离；粒子群算法；二阶振荡；Givens变换 中图分类号：TN911.7 doi: 10.19734/j.issn.1001-3695.2018.05.0447

# Blind separation method based on based on Givens transformation and second-order oscillatory W-C-PSO

Zhang Huawei, Zhang Tianqi, Liu Donghua (Chongqing KeyLaboratoryof Signal& Information Processing,Chongqing Universityof Posts&Telecommunications, Chongqing 400065,China)

Abstract:Fortheintellgentalgorithm,it iseasytofallintolocaloptimum when implementing blindsourceseparation,nd the convergence speed is slow,this paper proposes a blind source separation algorithm basedon Givens transform and second-orderoscilator particle swarmoptimization.Thisalgorithmconstructs the functional relationship betwee theinertia weightandthelearningfactor,andadjuststhealgorithmtogethertoimprovethealgorithm'soveralland global searchability. The second-orderoscillation increases the diversityof thepopulation，sothealgorithm isnoteasy tofallintothelocal optimum.Inaddition,thealgorithmuses Givens transformation toconvert the separationmatrix into arotation angle representationtoreduce thecomplexityandacelerate theconvergence speed.Simulationresults show that thealgorithmcan effectivelyachieve theblind separationof mechanical vibrationsignals and speech signals,and has fasterconvergence speed and better separation performance than other algorithms

Key words:blind source separation；particle swarm optimization；second-order oscillatory particle swarm；givens transformation

# 0 引言

盲源分离是指在源信号和传输信道未知的条件下，从混合信号中分离出各路待估计信源的过程，在参数估计、各类信号分析、故障检测等领域均具有重要应用[2]。当前传统的盲源分离算法研究的较为成熟，如快速独立分量分析法、自然梯度法、等变自适应算法等。此类算法使用自适应变步长改进了算法的收敛速度[3]，增加动量项提高了算法的稳态误差[4]，但考虑到根据信源统计特性选取非线性函数的问题，影响因素较多，并与源信号信息未知相矛盾。

当前更多的研究者将智能算法应用到盲源分离中来解决上述问题[5.6]。文献[7]提出了基本粒子群（particle swarmoptimization,PSO）算法，较蚁群算法、蜂群算法等智能算法，PSO算法的收敛速度更快，全局搜索能力更强，迭代过程更简单一些。文献[8]提出了基于自适应调整惯性权重的PSO算法，虽然解决了非线性函数选取问题，但该算法的收敛性并没有很大改善且容易陷入局部极值；文献[9]采用自适应遗传变异环节增加粒子群的多样性，提高了算法的分离性能，但是由于要计算变异概率和子代的关系，算法的复杂度也急速上升。

针对上述算法的缺点，本文提出了一种基于Givens变换和二阶振荡W-C-PSO 优化的盲源分离算法。该方法采用粒子群算法对目标函数进行优化，将惯性权重与学习因子非线性函数结合，共同调节粒子的迭代，这样既可以提高算法的整体性，又可以增强全局收敛能力；其次，引入二阶振荡环节增强粒子的多样性，使粒子极易跳出局部最优；并采用Givens变换将分离矩阵使用旋转角度表示，来降低算法的复杂度，提高算法的收敛速度。最后，采用本文算法对振动信号和语音信号进行盲分离，实验证明该算法较其他算法具有较好的收敛速度和全局搜索能力，并有效解决易陷入局部极值的问题。

# 1 盲源分离模型

该模型可以描述为：假设有 $n$ 个信号源和 $m$ 个传感器，则观察信号与源信号呈现的表达式为

$$
\mathbf { x } ( t ) = \mathbf { A } \mathbf { s } ( t ) + \mathbf { n } ( t )
$$

其中： ${ \bf s } ( t ) = \left[ \mathrm { s } _ { 1 } , \mathrm { s } _ { 2 } , . . . , \mathrm { s } _ { \mathrm { n } } \right] ^ { T }$ 为 $n \times 1$ 维源信号向量；$\mathbf { x } ( t ) = \left[ x _ { 1 } , x _ { 2 } , . . . , x _ { m } \right] ^ { T }$ 为 $m \times 1$ 维观测数据向量; $\mathbf { A }$ 为 $m \times n$ 维混合矩阵， ${ \bf n } ( t )$ 为背景噪声，在这里本文不予考虑。在信道性质和源信号均不知时，仅由观测数据 ${ \bf x } \big ( t \big )$ 和相应的学习算法得到最佳分离矩阵 $\mathbf { W }$ ，使得算法输出的 $\mathbf { y } \left( t \right)$ 是源信号的最佳估计。

$$
\mathbf { y } \left( t \right) = \mathbf { W } \mathbf { x } \left( t \right)
$$

其中： $\mathbf { y } ( t ) = \left[ y _ { 1 } , y _ { 2 } , . . . , y _ { n } \right] ^ { T }$ 。所以，盲源分离过程转换成了在某一个独立性判据意义下，通过相应的算法对分离矩阵 $\mathbf { W }$ 进行寻优的过程，使各分量实现相互独立。本文采用负熵[0作为分离出的估计信号相互独立的依据来建立目标函数。

$$
f \left( y \right) = \sum _ { i = 1 } ^ { n } { \frac { 1 } { 4 8 } } { k _ { 4 } } ^ { 2 } \left( y _ { i } \right)
$$

其中：信号的峭度 $k _ { 4 } \left( \mathrm { y _ { i } } \right) { = } \frac { E \left( \mathrm { y _ { i } } ^ { 4 } \right) } { E \left( \mathrm { y _ { i } } ^ { 2 } \right) ^ { 2 } } - 3$ 。在 $E \big ( \mathbf { y } \mathbf { y } ^ { T } \big ) = I$ 条件下,目标函数 $f ( \mathbf { y } )$ 越大，则各分离信号 $y _ { i }$ 之间的统计独立性越高，也就是分离结果越好。

# 2 基于二阶振荡改进的W-C-PSO算法

# 2.1基本粒子群算法

PSO 算法根据目标函数计算适应度值，使粒子不断地更新速度和位置，最终找到全局最优位置。其速度和位置的更新公式如下：

$$
\begin{array} { r } { V _ { i , j } \left( t + 1 \right) = V _ { i , j } \left( t \right) + c _ { 1 } r _ { 1 } \Big [ p _ { i , j } - X _ { i , j } \left( t \right) \Big ] + } \\ { c _ { 2 } r _ { 2 } \Big [ p _ { \mathrm { g } , j } - X _ { i , j } \left( t \right) \Big ] \qquad } \end{array}
$$

$$
X _ { i , j } \left( t + 1 \right) = X _ { i , j } \left( t \right) + V \left( t + 1 \right) , j = 1 , 2 , \cdots , D
$$

其中： $c _ { 1 }$ 和 $c _ { 2 }$ 分别为认知学习因子和社会学习因子； $r _ { 1 }$ 和 $r _ { 2 }$ 是分布于[0,1]的随机数； $D$ 为粒子搜索空间维度；  
$\mathbf { X } _ { i } = \left( X _ { i , 1 } , X _ { i , 2 } , \cdots , X _ { i , D } \right)$ 为第 $i$ 个粒子位置； $V _ { i } = \left( V _ { i , 1 } , V _ { i , 2 } , \cdots , V _ { i , D } \right)$   
为第 $i$ 个粒子速度； $\mathbf { P } _ { i } = \left( p _ { i , 1 } , p _ { i , 2 } , \cdots , p _ { i , D } \right)$ 为粒子个体最优位置；  
$\mathbf { P } _ { g } = \left( p _ { \mathrm { g } , 1 } , p _ { \mathrm { g } , 2 } , \cdots , p _ { \mathrm { g } , D } \right)$ 为当前种群全局最优位置。

传统PSO算法中令学习因子 $c _ { 1 }$ 和 $c _ { 2 }$ 为常数；文献[11]将惯性权重 $\omega$ 应用到PSO算法中，有效平衡了算法的收敛速度和搜索能力。

$$
\begin{array} { r l } & { V _ { i , j } \left( t + 1 \right) = \omega \big ( t \big ) V _ { i , j } \left( t \right) + c _ { 1 } r _ { 1 } \Big [ p _ { i , j } - X _ { i , j } \left( t \right) \Big ] } \\ & { \qquad + c _ { 2 } r _ { 2 } \Big [ p _ { \mathrm { g } , j } - X _ { i , j } \left( t \right) \Big ] } \end{array}
$$

其中： $\omega$ 采用下式线性递减的形式，即在[0.95,0.4]内变化。 $\omega$   
由大变小，使算法在前期扩大搜索范围，全局搜索能力较好;  
而在后期集中局部搜索，提高准确性。

$$
\omega \big ( t \big ) = \omega _ { \mathrm { m a x } } - \big ( \omega _ { \mathrm { m a x } } - \omega _ { \mathrm { m i n } } \big ) \times \frac { t } { N }
$$

其中： $t$ 为迭代次数； $N$ 为最大迭代次数； $\omega _ { \mathrm { m a x } }$ 为惯性权重最大值； $\omega _ { \mathrm { { m i n } } }$ 惯性权重最小值。

# 2.2改进粒子群算法

可知惯性权重可有效改善搜索能力，而由式（4）可知学习因子 $c _ { 1 }$ 、 $\boldsymbol { c } _ { 2 }$ 分别为调节粒子向自身最优方向、全局最优位置的前进步长，因此调节学习因子可以有效避免粒子陷入局部极值，改善算法搜索性能。但在以往的算法改进中，这两个参数互不关联，这在某种角度上说降低了PSO算法的整体性，不利于粒子的全局搜索，因此本文提出将这两个参数非线性结合来增强算法的整体性能。

$$
\left\{ \begin{array} { l } { c _ { 1 } \left( t \right) = \gamma \omega ^ { 2 } \left( t \right) + \eta \omega \left( t \right) + \varepsilon } \\ { c _ { 2 } \left( t \right) = 2 . 5 - c _ { 1 } \left( t \right) } \end{array} \right.
$$

其中：γ、、ε为常系数。通过测试本文惯性权重采用下式指数递减形式：

$$
\omega \big ( t \big ) = \omega _ { \mathrm { m i n } } + \big ( \omega _ { \mathrm { m a x } } - \omega _ { \mathrm { m i n } } \big ) * \exp \Big [ - 2 0 \big ( t / T \big ) ^ { 6 } \Big ]
$$

这就是本文所说的W-C-PSO算法。

在粒子群算法中，随着粒子的不断搜索，粒子的种群多样性在不断减小，这将不利于继续搜索。因此本文在W-C-PSO算法的基础上引入二阶振荡环节，可以使粒子在下一次迭代中向着较优的位置移动，即增强粒子的多样性；当搜索范围扩大时，二阶振荡有助于粒子跳出局部，改善算法的全局搜索能力。改进后粒子群速度迭代可表示为

$$
\begin{array} { r l } & { V _ { i , j } \left( t + 1 \right) = \omega \big ( t \big ) V _ { i , j } \left( t \right) + } \\ & { \quad c _ { 1 } \left( t \right) r _ { 1 } \Big [ p _ { i , j } - \left( 1 + \xi _ { 1 } \right) X _ { i , j } \left( t \right) + \xi _ { 1 } X _ { i , j } \left( t - 1 \right) \Big ] + } \\ & { \quad c _ { 2 } \left( t \right) r _ { 2 } \Big [ p _ { _ { g , j } } - \left( 1 + \xi _ { 2 } \right) X _ { i , j } \left( t \right) + \xi _ { 2 } X _ { i , j } \left( t - 1 \right) \Big ] } \end{array}
$$

其中： $\xi _ { 1 }$ ， $\xi _ { 2 }$ 为随机数。在该算法迭代前期（小于最大迭代次数的 $1 / 2$ ）选取 $\xi _ { 1 } < \frac { 2 \sqrt { c _ { 1 } r _ { 1 } } - 1 } { c _ { 1 } r _ { 1 } }$ （204号 $\xi _ { 2 } < \frac { 2 \sqrt { c _ { 2 } r _ { 2 } } - 1 } { c _ { 2 } r _ { 2 } }$ （204号 可提高算法的全局搜索能力；在迭代后期（大于等于最大迭代次数的 $1 / 2$ ）选取 $\xi _ { 1 } \ge \frac { 2 \sqrt { c _ { 1 } r _ { 1 } } - 1 } { c _ { 1 } r _ { 1 } }$ $\xi _ { 2 } \ge \frac { 2 \sqrt { c _ { 2 } r _ { 2 } } - 1 } { c _ { 2 } r _ { 2 } }$ 可加快算法的收敛速度。

# 3基于Givens 变换和二阶振荡W-C-PSO 优化的盲 源分离

# 3.1Givens 变换

由式(3)可知，处理 $n$ 阶矩阵时需求解 $n ^ { 2 }$ 个未知数，计算量较大。为此，对混合矩阵采取QR分解。令白化矩阵为

$$
\mathbf { z } ( t ) = \mathbf { P } \mathbf { x } ( t ) = \mathbf { P } \mathbf { A } \mathbf { s } ( t ) = \mathbf { U } \mathbf { s } ( t )
$$

利用QR分解，则 $\mathbf { z } \left( t \right) = \mathbf { U s } \left( t \right) = \mathbf { Q } \mathbf { R } \mathbf { s } \left( t \right)$ 。其中， $\mathrm { ~ \bf ~ P ~ }$ 为白化矩阵，Q为酉矩阵， $\mathtt { R }$ 为上三角阵。经过白化后有

$$
\begin{array} { r l } & { E \Big [ { \bf z } \big ( t \big ) { \bf z } \big ( t \big ) ^ { T } \Big ] = E \Big [ \Big ( { \bf Q } { \bf R } s \big ( t \big ) \Big ) \big ( { \bf Q } { \bf R } s \big ( t \big ) \big ) ^ { T } \Big ] } \\ & { \qquad = E \Big [ { \bf Q } { \bf R } s \big ( t \big ) { \bf s } \big ( t \big ) ^ { T } { \bf R } ^ { T } { \bf Q } ^ { T } \Big ] } \\ & { \qquad = { \bf Q } { \bf R } E \Big [ { \bf s } \big ( t \big ) { \bf s } \big ( t \big ) ^ { T } \Big ] { \bf R } ^ { T } { \bf Q } ^ { T } = { \bf I } } \end{array}
$$

由源信号之间不相关可知， $E { \biggl [ } \mathbf { s } { \bigl ( } t { \bigr ) } \mathbf { s } { \bigl ( } t { \bigr ) } ^ { T } { \biggr ] } = I$ ，得到 $\mathtt { R }$ 为酉矩阵，且为对角阵。上式可表示为：

$$
{ \mathbf { Q } } ^ { T } { \mathbf { z } } ( t ) = { \mathbf { R s } } ( t )
$$

分离信号与源信号之间成比例关系，则 $\mathbf { R s } ( t )$ 可看作对源信号的估计，即分离信号。则 $\mathbf { Q } ^ { T }$ 可看作分离矩阵的估计，即分离矩阵为正交矩阵。任何一个行列式不等于1的 $n$ 阶正交矩阵均可以转换成Givens 旋转矩阵的乘积形式，记为 $\mathbf { G } ^ { [ 1 2 ] }$ ，如式（14）所示。

$$
\begin{array} { r } { G _ { i j } = \left[ \begin{array} { c c c c c c c c } { 1 } & { \ldots } & { 0 } & { \ldots } & { 0 } & { \ldots } & { 0 } \\ { \vdots } & { \ddots } & { \vdots } & & { \vdots } & & { \vdots } \\ { 0 } & { \ldots } & { \cos \theta _ { i j } } & { \ldots } & { \sin \theta _ { i j } } & { \ldots } & { 0 } \\ { \vdots } & & { \vdots } & { \ddots } & { \vdots } & & { \vdots } \\ { 0 } & { \ldots } & { - \sin \theta _ { i j } } & { \ldots } & { \cos \theta _ { i j } } & { \ldots } & { 0 } \\ { \vdots } & & { \vdots } & & & { \vdots } & { \ddots } & { \vdots } \\ { 0 } & { \ldots } & { 0 } & { \ldots } & { 0 } & { \ldots } & { 1 } \end{array} \right] } \end{array}
$$

则分离矩阵 $\mathbf { W } \big ( t \big )$ 可表示为

$$
\begin{array} { c } { { { \bf W } ( t ) = G _ { n - 1 } ( t ) G _ { n - 2 } ( t ) \cdots G _ { 1 } ( t ) } } \\ { { G _ { 1 } ( t ) = G _ { 1 , n } ( t ) G _ { 1 , n - 1 } ( t ) \cdots G _ { 1 , 2 } ( t ) } } \\ { { G _ { 2 } ( t ) = G _ { 2 , n } ( t ) G _ { 2 , n - 1 } ( t ) \cdots G _ { 2 , 3 } ( t ) } } \end{array}
$$

$$
G _ { n - 1 } \left( t \right) = G _ { n - 1 , n } \left( t \right)
$$

其中： $\theta \in \left[ 0 , 2 \pi \right]$ 。Givens 变换后，每个Givens 矩阵中有1个待求参数， $G _ { 1 }$ 有 $n - 1$ 个， $G _ { 2 }$ 有 $n - 2$ 个，依次类推， $G _ { n - 1 }$ 有1个，所以分离矩阵 $\mathbf { W } ( t )$ 中的求解参数有：

$$
\Big ( 1 + 2 + \cdots + \big ( n - 2 \big ) + \big ( n - 1 \big ) \Big ) \times 1 = \frac { n \big ( n - 1 \big ) } { 2 }
$$

若不采用Givens 变换， $\mathbf { W } \big ( t \big )$ 中的求解参数有 $\scriptstyle n ^ { 2 }$ 个，所以

求解的参数个数减少了：

$$
n ^ { 2 } - { \frac { n \left( n - 1 \right) } { 2 } } = { \frac { n \left( n + 1 \right) } { 2 } }
$$

这样不仅保证了 $\mathbf { W } \left( t \right)$ 的正交性，而且使其求解的未知参数减半，降低了复杂度。

# 3.2基于二阶振荡W-C-PSO优化的盲源分离

基于二阶振荡W-C-PSO 算法用粒子位置表示正交分离矩阵，Givens 变换后其参数表示使粒子搜索维度 $D$ 从 $n ^ { 2 }$ 降到了$n ( n - 1 ) / 2$ ，提高了算法效率；惯性权重与学习因子两个参数的结合提高了算法全局搜索能力；引入二阶振荡环节提高了种群多样性，使其不易陷入局部极值。算法可分别有效实现对动态信号和语音信号的盲分离，具体流程如图1所示。

![](images/d57f9f5140d5a34637318a9070b18bfb261406086497d9dd5bb14985b1045093.jpg)  
图1基于Givens变换和二阶振荡W-C-PSO算法流程图  
Fig.1Flow of W-C-PSO algorithm based on givens transform and 2- order oscillation

a)对观测到的动态混合信号 $\mathbf { x } { \big ( } t { \big ) }$ 中心化和白化操作。

b)初始化学习因子 $c _ { 1 }$ 、 $c _ { 2 }$ 以及惯性权重 $\omega$ ，并设置最大值$\omega _ { \mathrm { m a x } }$ 和最小值 $\omega _ { \mathrm { m i n } }$ ，随机设置一些数量的分离矩阵作为各粒子的初始位置，并采用Givens变换后的参数表示。

c)根据式(3)求解适应度

d)对比每个粒子的适应度值与个体极值 $\mathbf { P _ { i } }$ 和全局极值 ${ \bf P } _ { g }$ ，取优更新 $\mathbf { P _ { i } }$ 、 ${ \bf P } _ { g }$

e)当 $t \geq 2$ 时，根据式(8)(9)分别调节 $\omega$ 和 $c _ { \scriptscriptstyle 1 }$ 、 $\boldsymbol { c } _ { 2 }$

f)引入二阶振荡，根据式(10)(5)分别更新粒子的速度和位置。

g)进入迭代循环，满足终止条件输出分离结果；否则返回 步骤c)继续搜索

# 4 仿真实验

为验证本文提出的基于Givens变换和二阶振荡W-C-PSO算法的有效性，对机械振动信号和语音信号分别进行盲分离实验。本文采用时变混合矩阵，表示为$\pmb { A } = \pmb { A _ { \theta } } + \alpha \big \{ r a n d n \big [ s i z e \big ( \pmb { A _ { \theta } } \big ) \big ] \big \}$ ，设初始 $A _ { \pmb { \theta } } = \left[ \begin{array} { l l } { 1 . 0 } & { 0 . 5 } \\ { - 0 . 6 } & { 0 . 4 } \end{array} \right]$ $\alpha = 0 . 0 0 3$ ，randnsize $( A _ { \theta } ) ]$ 为与 $A _ { \theta }$ 同维的随机矩阵，也就是混合信号是随机动态变化的。

# 4.1振动信号的盲源分离实验

本实验将模拟机械振动信号作为盲分离实验的源信号。依据振动信号模型[13]构造的两路源信号为

$$
\left\{ \begin{array} { l } { { s _ { 1 } \left( t \right) = 3 \big ( 1 . 5 + t \big ) \cos \big ( 2 5 0 \pi t - 2 \big ) } } \\ { { s _ { 2 } \left( t \right) = \sin \big ( 1 5 0 \pi t \big ) \big [ 1 + \sin \big ( 2 0 \pi t \big ) \big ] } } \end{array} \right.
$$

本文算法参数设置如下：粒子种群规模为20，惯性权重最大值 $\omega _ { \mathrm { m a x } } = 0 . 9$ ，惯性权重最小值 $\omega _ { \mathrm { m i n } } = 0 . 4$ ，学习因子迭代参数 $\gamma = 0 . 5$ ， $\mathfrak { \eta } = 1$ ， $\mathtt { \varepsilon } = 0 . 5$ ，迭代进化次数为300。实验结果如图2\~4所示。

![](images/f3bd31a4ff65eb734d7918e9bbe7fd686441c588b3547ced1bdada5086d995db.jpg)  
图2源信号时域波形和频谱

Fig.2 Time domain waveform and spectrum of source signal

![](images/00f79108acef9bdf270fdcc191e9d3c66cd100262c9ce097c15dd5bd8617c7e2.jpg)  
图3混合信号时域波形和频谱

比较图2源信号和图4分离信号，从时域中可以看出两个信号的波形基本一致，从频域中也可以看到信号在同样频率点具有最大峰值，说明本文算法可有效实现对机械振动信号的盲分离。

![](images/80d630fc07af8bc157e5d9c5ec8f6067fcb783dff0d73ae0805452fbedfabc99.jpg)  
图4分离信号时域波形和频谱

Fig.4 Time domain waveform and spectrum of discrete signal

# 4.2语音信号的盲源分离实验

为验证本文算法在实际应用中的效果，将对两路语音信号进行盲源分离，其参数设置如4.1节。实验结果如图5\~8所示。

![](images/4c3849f0b78b6a20dc2ad88b03f59e6d67627ce7f19db804e179d80610419a01.jpg)  
图5源信号波形

![](images/7fed1227188e293cd0c4b142d33fdd2758dce306d4388165c0b1187ddf5cbcc9.jpg)  
Fig.5 Waveform of source signal   
图6混合信号

![](images/561c970e2d9605dffa89851d377a122d68e1622b0687a7df24af84cd7273a11e.jpg)  
Fig.3 Time domain waveform and spectrum of composite signal   
Fig.6Waveform of composite signal   
图7解混信号Fig.7 Mixed signal

+ 1

比较图5和7，从波形中可以看出信号成功分离出来。并且依据真实听到的音效，幅度的模糊可以忽略。图8为分离信号的分组散点图，图中两条直线说明了源信号和分离信号有很高的相似性。

# 4.3算法对比

1)收敛性与搜索能力

采用PI曲线作为性能指标[13]，其定义为：

$$
P I \left( k \right) = \sum _ { i } \left\{ \left[ \sum _ { j } \frac { \left| G _ { k } \left( i , j \right) \right| } { \operatorname* { m a x } \left| G _ { k } \left( i , \bullet \right) \right| } - 1 \right] + \left[ \sum _ { j } \frac { \left| G _ { k } \left( j , i \right) \right| } { \operatorname* { m a x } \left| G _ { k } \left( \bullet , i \right) \right| } - 1 \right] \right\} \cap
$$

其中: $k$ 为迭代次数， $G _ { k } \left( i , j \right)$ 为 $k$ 次迭代时全局矩阵的第 $\left( i , j \right)$ 个元素。本实验将对比传统基本PSO 算法、W-C-PSO 算法以及引入二阶振荡的本文算法的收敛性及全局搜索能力，如图9所示。

![](images/4bf201a0a27f2ad13dd7510aee020cc2352d9ece15921203004fa0e52e49f049.jpg)  
Fig.8 Block scatter plot   
图9各算法收敛曲线1  
Fig.9Convergencecurvesofalgorithms

从图中可以看到，基本PSO算法的曲线没有达到最优值就收敛了，导致算法陷入局部极值；采用惯性权重与学习因子结合后，虽然收敛速度有所下降，但明显提高了全局搜索能力；而本文算法采用Givens 变换并引入二阶振荡环节，即提高了收敛速度，又增强了全局搜索能力，并且极易跳出局部极值，算法性能越来越好。

另外，相较与其他PSO改进算法，性能对比结果如图10所示。

文献[8]采用自适应惯性权重PSO 算法，全局搜索能力较差，且易陷入局部最优；文献[9]引入遗传变异环节后全局搜索能力有所提高，但由于其复杂度较高收敛速度较慢；比较之下，本文算法的收敛速度有所提高，同时具有较好的全局搜索能力，不易陷入局部极值。

![](images/89baf2344d1694a6445ef04a1ad74944c63b0e8fe3e71a3d2ec0d87d1927e430.jpg)  
图8分组散点图  
图10各算法收敛曲线2  
Fig.10 Convergence curves of algorithms

2)分离性能

为了进一步体现本文算法的分离性能，使用相似系数作为评价性能指标，即分离信号与源信号的相似性。相似系数[13]为

$$
\xi _ { i j } = \xi { \Big ( } y _ { i } , s _ { j } { \Big ) } = { \frac { \displaystyle { \Bigg | } { \sum _ { t = 1 } ^ { M } } y _ { i } { \big ( } k { \big ) } s _ { j } { \big ( } k { \big ) } { \Bigg | } } { \displaystyle { \sqrt { \sum _ { t = 1 } ^ { M } } } y _ { i } ^ { \circ } { \big ( } k { \big ) } { \sum _ { t = 1 } ^ { M } } s _ { j } ^ { \circ } { \big ( } k { \big ) } } }
$$

当 $y _ { i }$ 与 $s _ { j }$ 相互独立时， $\xi _ { i j } = 0$ ；当 $y _ { i } = c s _ { j }$ （c为常数）时，$\xi _ { \scriptscriptstyle i j } = 1$ ，说明 $\mathbf { s } ( t )$ 与 $\mathbf { y } \left( t \right)$ 越相似，即分离效果越好。使用传统EASI算法、文献[8]的自适应惯性权重PSO算法、文献[9]遗传变异算法与本文提出的算法分别进行仿真，其中EASI算法选择非线性函数 $f \left( y \right) = y ^ { 3 }$ ，将得到的平均相似系数进行比较。实验采用机械振动信号进行实验，结果如表1所示。

表1各算法相似系数对比  
Table1 Comparison of similarity coefficients   

<html><body><table><tr><td rowspan="2">算法</td><td colspan="2">信号1平均相似系数</td><td colspan="2">信号2平均相似系数</td></tr><tr><td>最大值</td><td>最小值</td><td>最大值</td><td>最小值</td></tr><tr><td>EASI</td><td>0.9292</td><td>0.4251</td><td>0.9105</td><td>0.0973</td></tr><tr><td>文献[8]</td><td>0.9225</td><td>0.2684</td><td>0.9588</td><td>0.4007</td></tr><tr><td>文献[9]</td><td>0.8642</td><td>0.1132</td><td>0.9754</td><td>0.1433</td></tr><tr><td>本文算法</td><td>0.9999</td><td>0.0865</td><td>0.9855</td><td>0.0009</td></tr></table></body></html>

由表1可以看出，EASI算法、文献[8]算法、文献[9]算法的相关系数最小值都比较大，说明对动态信号分离效果不好。而本文提出的改进算法，即基于Givens 变换和二阶振荡W-C-PSO算法，其相关系数的最大值为0.9999，相比于其他算法更接近1；其相关系数最小值为0.0009。说明本文提出的算法具有更好的分离性能，为处理动态信号提供了新的思路和依据。

3)运行时间

为了多方面比较算法的性能，表2给出了各算法的运行时间。

表2算法运行时间  
Table 2Algorithm run time   

<html><body><table><tr><td>算法</td><td>运行时间/s</td></tr><tr><td>W-C-PSO</td><td>12.565630</td></tr><tr><td>二阶振荡+W-C-PSO</td><td>12.703810</td></tr><tr><td>本文算法</td><td>12.385740</td></tr></table></body></html>

由表2看出，各个算法的运行时间很接近，虽然引入二阶振荡粒子使得算法的收敛速度较W-C-PSO 算法变慢，但是由图9 可知W-C-PSO 算法的性能并不高，所以本文算法在此基础上使用Givens矩阵表示分离矩阵，由3.1节可知，本文算法减少了 $n { \bigl ( } n + 1 { \bigr ) } / 2$ 个参数，使得运行时间有所减少，加快了收敛。

# 5 结束语

本文在传统PSO算法上对惯性权重和学习因子进行结合，增强算法的整体性，提高了算法的全局搜索能力；在此基础上又引入二阶振荡环节，增加了粒子的多样性，使其不易陷入局部极值；并采用Givens变换降低了算法的复杂度，提高了算法收敛速度。仿真表明，对机械振动信号和语音信号盲分离均具有较好的效果；在收敛性、全局搜索能力以及分离性能等方面，本文算法表现更优，并为智能算法的改进也提供了新的依据。

# 参考文献：

[1] 黄宇，刘玉峰，彭志敏，等．基于量子并行粒子群优化算法的分数阶混 沌系统参数估计[J].物理学报，2015,64(3):228-235.(Huang Yu,Liu Yufeng,Peng,Zhimin,et al.Research on particle swarm optimization algorithm with characteristic of quantum parallel and its application in parameter estimation for fractional-order chaotic systems [J].Acta Physica Sinica,2015,64(3):228-235.)

[2]席剑辉，崔健驰，蒋丽英.基于JADE-ICA的滚动轴承多故障信号盲源 分离[J].振动与冲击,2017,36(5):231-237.(Xi Jianhui,Cui Jianchi, Jiang Liying.JADE-ICA-based blind source separation of multi-fault signals of roling bearings [J].Journal of Vibration and Shock,2O17,36 (5): 231-237.)

[3]季策，杨坤，陶奕名，等．一种非平稳环境下的自适应变步长盲源分离 算法[J].控制与决策，2016,31(4):735-739.(JiCe，Yang Kun，Tao Yiming,et al.An adaptive variable step-size blind source separation algorithm in nonstationary environment [J].Control and Decision,2016, 31 (4): 735-739.)

[4]张天骐，马宝泽，强幸子，等．一种引入自适应动量项的变步长混沌信 号盲分离算法[J]．电子与信息学报，2017，39(4):908-914.(Zhang Tianqi，Ma Baoze，Qiang Xingzi,et al.Variable-step blind source separation algorithm with adaptive momentum item for chaotic signals [J]. Journal ofElectronics & Information Technology,2017,39(4): 908-914.)

[5]贾志成，韩大伟，陈雷，等．基于复Givens 矩阵与蝙蝠优化的卷积盲分 离算法 [J].通信学报,2016,37(7):107-117.(Jia Zhicheng,Han Dawei, Chen Lei,et al.Convolutive blind separation algorithm based on complex Givens matrix and bat optimization [J].Journal on Communications,2016, 37 (7):107-117.)

[6]陈雷，甘士忠，张立毅，等．基于样条插值与人工蜂群优化的非线性盲 源分离算法[J].通信学报，2017，38(7):36-46.(Chen Lei,Gan Shizhong,Zhang Liyi,et al.Nonlinear blind source separation algorithm based on spline interpolation and artificial bee colony optimization [J]. Journal on Communications,2017,38(7): 36-46.)

[7]Afshar M H.Extension of the constrained particle swarm optimization algorithm to optimal operation of multi-reservoirs system [J].Electrical Power and Energy Systems,2013,51(2): 71-81.

[8]马宝泽，张天骐，江晓磊，等．基于自适应惯性权重粒子群优化的多跳 频信号盲源分离[J].电讯技术，2016,56(6):675-680.(Ma Baoze, Zhang Tianqi,Jiang Xiaolei,et al.Blind source separationof multi-frequency-hopping signals based on adaptive inertia weight PSO algorithm [J]. Telecommunication Technology,2016,56(6): 675-680.)

[9]陈侃松，阮玉龙，戴磊，等．区域分割的自适应变异粒子群算法[J]. 电子学报,2017,45 (8):1849-1855.(Chen Kansong,Ruan Yulong,Dai Lei, etal. Regional-segmentation self-adapting variation particle swarm optimization [J].Acta Electronica Sinica,2017,45(8): 1849-1855.)

[10] Fu Gengshen,Phlypo R,Anderson M,et al.Blind source separation by entropy rate minimization [J].IEEE Trans on Signal Processing,2014,62 (16): 4245-4255.

[11] Shi Yuhui,Eberhart R C.Parameter selection in particle swarm optimization[C]//Procof the 7th International Conferenceon Evolutionary Programming VII. Berlin: Springer,1998: 591-600.

[12]谢显中，张森林，肖正瑛．一种基于QR分解的稳健干扰对其算法[J]. 电子与信息学报,2015,37(8):1957-1963.(Xie Xianzhong,Zhang Senlin, Xiao Zhengying.Robust interference alignment algorithm based on decomposition [J]. Journal of Electronics & Information Technology,2015, 37 (8): 1957-1963.)

[13]周晓峰，杨世锡．基于负熵最大化的机械振源半盲分离方法[J].浙江 大学学报：工学版,2011,45(5):846-850.(Zhou Xiaofeng，Yang Shixi. Semi-blindsourcesseparation ofmechanical vibrations baseon maximization of negentropy [J].Journal of Zhejiang University: Engineering Science,2011,45 (5): 846-850.)

[14]陈雷，张立毅，郭艳菊，等．基于时间可预测性的差分搜索盲信号分离 算法[J].通信学报,2014,35(6):117-125.(Chen Lei,Zhang Liyi,Guo Yanju，et al.Blind signal separation algorithm based on temporal predictabilityanddifferentialsearchalgorithm[J].Journalon Communications,2014,35 (6): 117-125.)