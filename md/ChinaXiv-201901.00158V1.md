# 一种优化的硬阈值追踪算法的研究\*

陈暄1，潘春平¹，龙丹²(1．浙江工业职业技术学院，浙江 绍兴 312000;2.浙江大学，杭州 310058)

摘要：硬阈值追踪算法是压缩感知中一种重要的重构算法，该算法的本质是一个最小二乘问题，存在复杂度高，收敛性差、运行时间长等缺点。引入Nesterov方法用以优化稀疏解的凸松弛现象，引入逐次松弛迭代法优化传统硬阈值线性方程组，理论证明优化结果具有良好的收敛性，仿真实验说明优化后的算法有效降低算法复杂度，降低了运行时间。

关键词：硬阈值；追踪；Nesterov；逐次超松弛迭代法 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2018.10.0769

Research on optimization hard threshold tracking algorithm

Chen Xuan1,Pan Chun ${ \mathrm { P i n } } ^ { 1 }$ ,Long Dan² (1.ZhejiangIndustryPolytechnicCollge,ShaoxingZhejiang32oo0,China;2.Zhejiang University,Hangzhou310058, China)

Abstract:Thehard threshold trackingalgorithm is an important reconstruction algorithm in compressed sensing,which is essentially aleast squares problemand has the disadvantages ofhigh complexity,poor convergence and long running time. This paper introduced the Nesterov method to optimize the convex relaxation phenomenon of sparse solutions，and introduced thesuccesiverelaxation iterative methodtooptimizethetraditionalhard thresholdlinear equations.The theory provesthatthe optimization results have good convergence.Simulation experiments show that the optimized algorithm effectively reduces the complexity of the algorithm and the running time.

:ey words:hard threshold; tracking; nesterov; successive over relaxation methoc

# 0 引言

压缩感知理论[l\~5]突破传统的 Nyquist 定理的严格限制,实现了对信号的采样能够在较低的采样率下进行，并同时完成对信号的压缩,在重构一端通过非线性化的方式进行信号的重构。压缩感知理论的提出使得信号在采样过程中不再主要依赖信号的宽度,这样能够有效的降低了信号传输和存储过程中所需要的代价。因此研究如何能够高效的恢复原始信号成为了重构算法的主要方向,目前在压缩感知中的重构算法有凸松弛算法,贪婪追踪算法和组合优化算法。凸松弛算法具有观测次数少,复杂度偏高的特点,其代表有基追踪算法[6](basicpursuit，BP),梯度投影稀疏重建算法[7](gradientprojection for sparse，GPSR),最小角度回归法[8](least angleregreesion，LARS);贪婪追踪算法具有算法具有节点,速度快,复杂度低的特点,其代表有正交匹配追踪算法[9](orthogonalmatchingpursuit,OMP),正则化正交匹配算法[lo](regularizedorthogonal matchingpursuit，ROMP),分段正交匹配追踪算法[11](stagewise orthogonal matching pursuit, STOMP)等;组合优化算法主要是稀疏傅里叶变换算法[12](sparseFouriertransform，SFFT)。迭代硬阈值[13](iterative hard thresholding,IHT)是一种凸松弛算法,优点是适合大规模高维数据处理和实时数据处理,缺点是测量矩阵在有限等距特性条件下需要满足最大奇异值小于1的限制条件,因此导致了算法对对测量矩阵的尺度要求高,运算运行时间长，复杂度高。学者从不同的角度其进行了研究,取得了一些成果。文献[14]提出S-闭包的分块相干性和约束等距特性(RIP)概念;根据冗余字典分块相干性的特点，对更新支撑集部分对算法进行改进，仿真实验说明有效的降低了算法的收敛性;文献[15]提出一种基于SHTP算法的联合重构算法来求解分布式压缩感知问题,仿真结果表明该算法具有较大的信号重构噪声比和较小的平均支撑势误差,可实现信号值的精确重构;文献[16提出一种压缩采样硬阈值的重构算法,该算法在去除原子时结合硬阈值思想,保证了每次迭代更加的精确,仿真实验说明算法具有更好的重构性和抗躁能力;文献[17]提出了一种新的部分硬阈值(PHT)算子,它类似于硬阈值算子,限制了支持集在一次迭代中可以改变的量,仿真实验说明该算法提高算法效率;文献[18]提出了一种扩展的稀疏恢复理论并通过在硬阈值算法中使用取得了较好的效果,能够有效的恢复信号;文献[19]提出了一种复杂的洛伦兹迭代硬阈值算法，仿真实验说明该算法能够有效的恢复信号，具有较好的效果;文献[20]将硬阈值算法用于从少量线性测量中最优地恢复稀疏信号，然后对CS进行去噪和传统去噪处理的比较研究,该方法能够有效的降低噪声对信号的影响;文献[21]提出在硬阈值算法中将黎曼优化算法用于低秩矩阵恢复的思想,保证共轭梯度算法线性收敛到基础秩矩阵。经验评估表明,算法能够从几乎所需的最小测量数量中恢复低秩矩阵;文献[22]提出了一种基于广义期望最大化(GEM)噪声稀疏重构的降噪硬阈值方法,取得了较好的效果。

本文在文献[23]关于硬阈值算法研究的基础上,引入Nesterov和逐次超松弛替代法来进行改进，并证明了改进后的算法具有良好的收敛性,在仿真实验的指标测评中取得了较好的效果。

# 1 硬阈值追踪算法

所有的压缩重构算法都必须遵守限制自同构性质(RIP)[4]。设 $A \in R ^ { M \times N }$ 的 $s$ 阶的自同构系数 $\delta _ { s } = \delta _ { s } ( A )$ 定义为满足式(1)的最小的 $\delta$ 。

$$
( 1 - \delta ) \| x \| _ { 2 } ^ { 2 } \leq \| A x \| _ { 2 } ^ { 2 } \leq ( 1 + \delta ) \| x \| _ { 2 } ^ { 2 }
$$

对于任意的 $s$ 稀疏的向量 $\boldsymbol { x } \in R ^ { N }$ 。文献[20,21]证明了当 $A$ 满足了RIP条件后，这些算法都是收敛的。

硬阈值追踪算法结合了IHT的硬阈值策略和CoSaMP的投影算法,迭代公式如下：

$$
S _ { n + 1 } = L _ { s } ( x _ { n } + A ^ { * } ( y - A x _ { n } ) )
$$

$$
x _ { n + 1 } = \arg \operatorname* { m i n } _ { z } \| y - A z \| _ { 2 } , s u p p ( z ) \subseteq S _ { n + 1 }
$$

式(3)中的 $s u p p ( x ^ { n } )$ 表示 $x ^ { n }$ 的支撑集合。 $L _ { s } ( x )$ 表示 $x$ 绝对值中最大的 $s$ 个元素的支撑。硬阈值的迭代步骤(即式(3))的本质形式是一个最小二乘问题。随着压缩感知中的信号重构的问题规模逐渐增大，采用直接解决最小二乘的问题就会非常的耗时，因此,文献[20]中提出的一种快速硬阈值的算法能够有效的解决大规模下的稀疏恢复的问题，它采用的梯度法来解决迭代中的最小二乘问题,当使用梯度法的时候,取步长为1,得到:

$$
\| x _ { n + 1 } - x \| _ { 2 } \leq \sqrt { \frac { 2 \delta _ { 3 s } ^ { 2 } + \delta _ { 3 s } ^ { 2 k + 2 } ( 1 - 3 \delta _ { 3 s } ^ { 2 } ) } { 1 - \delta _ { 2 s } ^ { 2 } } } \| x _ { n } - x \| _ { 2 }
$$

其中: $x$ 是任意 $s$ 稀疏的满足 $A x = y$ 的向量， $\{ x _ { n } \} _ { n = 0 , 1 , 2 \ldots }$ 是快速硬阈值的算法产生的迭代序列。从上面的研究中发现,式(3)一方面是一个待优化问题,采用优化效果更好的Nesterov可以提高优化的效果，从另一个方面来看式(3)也是一个正定的线性方程组，需要使用线性解决办法更好的逐次松弛替代法解决问题,本文阐述并证明了式(3)通过以上两种算法的改进得到的算法仍然是收敛的。

# 2 改进的硬阈值追踪算法

# 2.1Nesterov 方法

该方法是一种用以求解加速求解光滑优化问题的算法，其表达式为

$$
\operatorname* { m i n } { f ( x ) }
$$

其中: $f$ 是Lipschitz梯度 $L = L ( f )$ ,即满足

$$
\begin{array} { r } { \left\| \nabla f ( x _ { 1 } ) - \nabla f ( x _ { 2 } ) \right\| _ { 2 } \leq L \left\| x _ { 1 } - x _ { 2 } \right\| _ { 2 } , x _ { 1 } , x _ { 2 } \in d o m ( f ) } \end{array}
$$

算法步骤如下所示。

算法1：Nesterov 算法

1：初始化： $y ^ { 0 } = x ^ { 0 } , \theta _ { 0 } = 1$

2:while"notconverage",do

$$
\begin{array} { r l } & { x ^ { k + 1 } = y ^ { k } - h _ { k } \nabla f ( y ^ { k } ) } \\ & { } \\ & { \beta _ { k + 1 } = \cfrac { 1 } { 2 } ( 1 - \theta _ { k } ) ( \sqrt { \theta _ { k } ^ { 2 } + 4 } - \theta _ { k } ) } \\ & { } \\ & { y ^ { k + 1 } = x ^ { k } + \beta _ { k } ( x ^ { k + 1 } - x ^ { k } ) } \\ & { } \\ & { \theta _ { k + 1 } = \cfrac { 1 } { 2 } \theta _ { k } ( \sqrt { \theta _ { k } ^ { 2 } + 4 } - \theta _ { k } ) } \\ & { } \\ & { k = k + 1 } \end{array}
$$

3：输出最终的迭代结果 $x ^ { k }$

算法中的 $h _ { k }$ 是步长参数,设定 $h _ { k } = \frac { 1 } { L }$ ,文献[12]证明存在如下的关系

$$
f ^ { * } - f ( y ^ { k } ) \geq { \frac { 2 L \| y ^ { 0 } - y ^ { * } \| _ { 2 } ^ { 2 } } { ( k + 1 ) ^ { 2 } } }
$$

其中的 $y ^ { * }$ 就是问题(5)的解且满足 $f ^ { * } = f ( y ^ { * } )$ 。当式(3)使用算法1 求解的时候,目标函数为 $f ( x ) = \parallel y - A _ { n } x$ I， $A _ { n } = A ( ; , S _ { n } ) \in R ^ { M \times s }$ ,根据 $A$ 具有限制自同构性质得到：

$$
\| A _ { n } x \| _ { 2 } ^ { 2 } { \leq } ( 1 + \delta _ { s } ) \| x \| _ { 2 } ^ { 2 } { < } 2 , \forall x \in R ^ { s }
$$

因此，从式(8)中发现 $\| A _ { n } x \| _ { 2 } ^ { 2 } < 2$ ,即 $\| A _ { n } x \| _ { 2 } < 2$ ，因此有

$$
\| \nabla f ( x _ { 1 } ) - \nabla f ( x _ { 2 } ) \| _ { 2 } = \| A _ { n } ^ { * } A _ { n } ( x _ { 1 } - x _ { 2 } ) \| _ { 2 } < 2 \| x _ { 1 } - x _ { 2 } \| _ { 2 } 
$$

# 2.2逐次超松弛迭代法

式(3)其本质也是求解下列线性方程

$$
A _ { n } ^ { * } A _ { n } x = A _ { n } ^ { * } y
$$

$A _ { n } = A ( ; , S _ { n } ) \in R ^ { M \times s }$ ,因为 $A$ 具有限制自同构性质,所以， $A _ { n } ^ { * } A _ { n }$ 是正定矩阵,把矩阵 $A _ { n } ^ { * } A _ { n }$ 分裂成 $A _ { n } ^ { * } A _ { n } = D - ( D - A _ { n } ^ { * } A _ { n } ) = D - L - L ^ { * }$ ，其中, $D = d i a g ( d _ { 1 } , d _ { 2 } , \cdots d _ { n } )$ ， $d _ { i } > 0$ 是对称正定矩阵 $A ^ { * } A$ 的对角部分， $- L$ 是 $A ^ { * } A$ 的严格下三角部分。令 $A ^ { * } A = M - N$

$$
\begin{array} { l } { { \displaystyle M = \frac { 1 } { w } ( D - w L ) } } \\ { { \displaystyle N = \frac { 1 } { w } ( ( 1 - w ) D + w L ^ { * } ) , w \neq 0 } } \end{array}
$$

则得到逐次超松弛迭代法

$$
x ^ { ( k ) } = w D ^ { - 1 } ( L x ^ { ( k ) } + L ^ { * } x ^ { ( k - 1 ) } + A ^ { * } y ) + ( 1 - w ) x ^ { ( k - 1 ) }
$$

即

$$
x ^ { ( k ) } = ( D - W L ) ^ { - 1 } ( ( 1 - w ) D + W L ^ { * } ) x ^ { ( k - 1 ) } + w ( D - W L ) ^ { - 1 } A _ { n } ^ { * } y
$$

其中： $w$ 是松弛因子，因此迭代法式(12)的迭代矩阵$G _ { w } = ( D - w L ) ^ { - 1 } ( ( 1 - w ) D + w L ^ { * } )$ ,上述迭代需要显示计算 $A ^ { * } A$ ,若在第 $k$ 步,令 $Z ^ { ( 1 ) } = x ^ { ( k - 1 ) }$ ， $r ^ { ( 1 ) } = b - A x ^ { ( k - 1 ) }$ ,则可得不需要显示计算 $A ^ { * } A$ 。算法步骤如下所示。

算法2逐次超松弛迭代法算法

$$
\displaystyle 1 \colon Z ^ { ( 1 ) } = x ^ { ( k - 1 ) } \ , \ r ^ { ( 1 ) } = A _ { n } ^ { * } y - A _ { n } x ^ { ( k - 1 ) }
$$

$$
r ^ { ( j + 1 ) } = r ^ { ( j ) } - \delta _ { j } a _ { j }
$$

$$
\delta _ { j } = w a _ { j } ^ { * } r ^ { ( j ) } / d _ { j } , j = 1 , \cdots n
$$

$$
\chi ^ { ( k ) } = Z ^ { ( n + 1 ) }
$$

3:输出迭代结果 $x ^ { k }$

# 2.3本文算法的收敛性分析

本文算法步骤如下所示。

算法3本文算法

1:初始化： $x ^ { 0 }$

2:while "not converage", $d o$

$$
S _ { n + 1 } = L _ { s } ( x _ { n } + A ^ { * } ( y - A x _ { n } ) )
$$

$$
x _ { n + 1 } ^ { 0 } = ( x _ { n } + A ^ { * } ( y - A x _ { n } ) ) S _ { n + 1 }
$$

$$
\begin{array} { c } { { x _ { n + 1 } ^ { ( k ) } = ( D - W L ) ^ { - 1 } ( ( 1 - W ) D + W L ^ { * } ) x _ { n + 1 } ^ { k - 1 } } } \\ { { + w ( 0 - W L ) ^ { - 1 } A _ { n } ^ { * } y } } \end{array} _ { x _ { n + 1 } } = x _ { n + 1 } ^ { ( k ) }
$$

$$
k = k + 1
$$

3:输出结果 $x ^ { k }$

下面的过程就来证明算法3是具有收敛性的

定理1设 $A _ { n } \in R ^ { M \times S } , x \in R ^ { S } , y \in R ^ { M }$ 5 $A _ { n } ^ { * }$ 是 $A _ { n }$ 的共轭转置矩阵，则当 $0 < W < 2$ 的时候,迭代方法3是收敛的。

证明设 $\lambda$ 是逐次超松弛迭代法方法的迭代矩阵 $G _ { \scriptscriptstyle { w } }$ 的任意一个特征值， $X \in R ^ { s }$ 为其相对应的特征向量,则有等式$( ( 1 - w ) D + w L ^ { * } ) x = \lambda ( D - W L ) x$ ,因此

$( 1 - W ) x ^ { * } D x + W x ^ { * } L ^ { * } x = \lambda ( x ^ { * } D x - W x ^ { * } L x )$ ，因为 $A _ { n } ^ { * } A _ { n }$ 对称正定

所以 $x ^ { * } D x = q > 0$ （204号

$$
x ^ { * } L x = \alpha + \beta i
$$

$$
x ^ { * } L ^ { * } x = ( x ^ { * } L x ) ^ { * } = \alpha - \beta i
$$

$$
x ^ { * } A _ { n } ^ { * } A _ { n } x = x ^ { * } ( D - L - L ^ { * } ) x = q - 2 \alpha
$$

其中, $\alpha , \beta \in R$

$\lambda = \frac { q - w q + w \alpha - w \beta i } { q - w \alpha - w \beta i }$

$\mid \lambda \mid ^ { 2 } = \frac { [ q - w ( q - \alpha ) ] ^ { 2 } + w ^ { 2 } \beta ^ { 2 } } { ( q - w \alpha ) ^ { 2 } + w ^ { 2 } }$

当 $0 < w < 2$ 的时候,有

即有 $\rho ( G w ) < 1$

因此，迭代方法是收敛的

因此接下来证明算法3具有的收敛性

引理1根据文献[20]中的假设 $A$ 具有限制自同构性质，$U$ 是指标集。因此对于任意的向量 $\nu$ 来说,存在

$$
\| \left( ( I - A ^ { * } A ) \nu \right) _ { U } \| _ { 2 } \leq \delta _ { t } \| \nu \| _ { 2 }
$$

其中, $| U \cup \cup { s u p p } ( \nu ) | { \le t }$ （20

引理2在算法3中,定义 $\scriptstyle \operatorname* { l i m } _ { l \to \infty } x _ { n } ^ { l } = x _ { n } ^ { * }$ 。因此对于任意的 $s$ 稀疏满足 $s u p p ( z ) \mathop { \subseteq } S _ { n }$ ，向量 $z$ 和任意 $s$ 稀疏的满足 $y = A x$ 的向量 $x$ ,有

$$
\left. x - x _ { n } ^ { \ast } , z \right. \leq \delta _ { 2 s } \parallel x - x _ { n } ^ { \ast } \parallel _ { 2 } \parallel z \parallel _ { 2 }
$$

证明由于 $A x _ { n } ^ { * }$ 是 $\{ A z , s u p p ( z ) \subseteq S _ { n } \}$ 上的 $y$ 近似最佳,因此有

$$
\left. y - A x _ { n } ^ { * } , A z \right. = 0 , i f \ s u p p ( z ) \subseteq S _ { n }
$$

因为 $y = A x$ ,式(15)重写为

$$
\langle A x - x _ { n } ^ { * } , A z \rangle = 0 , i f \ s u p p ( z ) \subseteq S _ { n }
$$

将式(16)和引理1代入式(15),定义 $U _ { n } = s u p p ( x - x _ { n } )$

$$
\left. x - x _ { n } ^ { * } , z \right. = \left. x - x _ { n } ^ { * } , ( I - A _ { n } ^ { * } A ) z \right.
$$

$$
\left. x - x _ { n } ^ { \ast } , [ ( I - A _ { n } ^ { \ast } A ) z ] _ { U _ { n } } \right. \leq \delta _ { 2 s } \left\| x - x _ { n } ^ { \ast } \right\| _ { 2 } \left\| z \right\| _ { 2 }
$$

引理3在算法3中,对于任意稀疏 $s$ 的满足 $y = A x$ 的向量 $x \ , \{ x _ { n } \} _ { n = 1 , 2 , 3 , \ldots }$ 满足

$$
\Vert \left( x _ { n + 1 } - x \right) _ { S _ { n + 1 } } \Vert _ { 2 } \leq \delta _ { 2 s } \Vert x _ { n } - x \Vert _ { 2 }
$$

$\begin{array} { c } { { \parallel ( x _ { n } + A ^ { * } ( y - A x _ { n } ) ) _ { S } \mid } } \\ { { \parallel ( x _ { n } + A ^ { * } ( y - A x _ { n } ) ) _ { S _ { n + } } } } \end{array}$ |≤证明设 $S = s u p p ( x )$ ,得到在两边同时减去 $\Vert \left( x _ { n } + A ^ { * } ( y - A x _ { n } ) \right) _ { S _ { n } , S _ { n + 1 } }$ ,得到

$$
\begin{array} { r l } & { \parallel ( x _ { n } + A ^ { * } ( y - A x _ { n } ) ) _ { S _ { n } , S _ { n + 1 } } \parallel _ { 2 } } \\ & { { \triangleleft \parallel ( ( I - A ^ { * } A ) ( x _ { n } - x ) _ { S _ { n } , S _ { n + 1 } } \parallel _ { 2 } } } \end{array}
$$

A $\parallel ( x - x _ { n + 1 } ) _ { S _ { n + 1 } } \parallel _ { 2 } - \parallel ( I - A ^ { * } A ) ( x _ { n } - x ) ) _ { S _ { n } , S _ { n + 1 } } \parallel$ 2因此,得到

$$
\begin{array} { r } { \big \| \left( x - x _ { n + 1 } \right) _ { S _ { n + 1 } } \big \| _ { 2 } \leq \big \| \left( ( I - A ^ { * } A ) ( x _ { n } - x ) \right) _ { S _ { n } , S _ { n + 1 } } \big \| _ { 2 } } \end{array}
$$

引理4设 $x _ { n + 1 } ^ { ( k ) }$ 是由逐次迭代方法产生的序列,则$\parallel x _ { n } ^ { ( k ) } - x _ { n } ^ { * } \parallel \leq \frac { \parallel G _ { w } \parallel ^ { k } } { 1 - \parallel G _ { w } \parallel _ { 2 } } \parallel x _ { n } ^ { ( 0 ) } - x _ { n } ^ { * } \parallel$

定理2设定算法3中产生的序列 $\boldsymbol { x } _ { n + 1 } ^ { i }$ 满足$\| { \boldsymbol { x } } _ { n } ^ { i } - { \boldsymbol { x } } _ { n } ^ { * }$ 云 $\gamma ( i ) \| { \boldsymbol { x } } _ { n } ^ { 0 } - { \boldsymbol { x } } _ { n } ^ { * } \|$ ,因此,对于任意 $s$ 稀疏的满足 $y = A x$ 的向量 $x$ ,因此算法3中的产生的 $x _ { n }$ 满足

$$
\left\| x _ { n } - x \right\| _ { 2 } \leq \rho ^ { n } \left\| x _ { 0 } - x \right\| _ { 2 }
$$

$$
\rho = ( 1 + \delta _ { s } ) ( \delta _ { 2 s } + \gamma ( l ) ) \sqrt { \frac { 1 + \delta _ { 2 s } } { 1 - \delta _ { 2 s } } }
$$

$$
+ \delta _ { 2 s } \gamma ( l ) + \delta _ { 2 s }
$$

证明 本文可以得到

$$
\begin{array} { c } { { \parallel \left( x _ { n + 1 } - x \right) _ { S _ { n + 1 } } \parallel _ { 2 } ^ { 2 } = \left. x _ { n + 1 } - x , \left( x _ { n + 1 } - x \right) _ { S _ { n + 1 } } \right. = } } \\ { { \left. x _ { n + 1 } - x _ { n } ^ { * } , \left( x _ { n + 1 } - x _ { n } \right) _ { S _ { n + 1 } } \right. + \left. x _ { n + 1 } ^ { * } - x , \left( x _ { n + 1 } - x _ { n } \right) _ { S _ { n + 1 } } \right. } } \end{array}
$$

注意到 $x _ { n + 1 } = x _ { n + 1 } ^ { l }$ ，因此,

$$
x _ { n + 1 } - x _ { n } ^ { * } , \left( x _ { n + 1 } - x _ { n } \right) _ { S _ { n + 1 } } < \gamma ( l ) \left. x _ { n + 1 } ^ { 0 } - x _ { n + 1 } ^ { * } \right. _ { 2 } \times \left. \left( x _ { n + 1 } - x _ { n } \right) _ { S _ { n + 1 } } \right. _ { 2 }
$$

通过引理4

$$
x _ { n + 1 } ^ { * } - x , ( x _ { n + 1 } - x _ { n } ) _ { S _ { n + 1 } } < \delta _ { 2 s } \parallel x _ { n + 1 } ^ { * } - x \parallel _ { 2 } \times \parallel ( x _ { n + 1 } - x _ { n } ) _ { S _ { n + 1 } } \parallel _ { 2 }
$$

化简得到

$$
\| \left( x _ { n + 1 } - x \right) _ { S _ { n + 1 } } \| _ { 2 }
$$

$$
\begin{array} { r l } {  { \le \delta _ { 2 s } \| x _ { n + 1 } ^ { * } - x \| _ { 2 } + \gamma ( l ) \| x _ { n + 1 } ^ { 0 } - x _ { n + 1 } ^ { * } \| _ { 2 } } } \end{array}
$$

$$
\begin{array} { r l } {  { \le ( \delta _ { 2 s } + \gamma ( l ) ) \bigl \| x _ { n + 1 } ^ { * } - x \bigr \| _ { 2 } + \gamma ( l ) \bigl \| x _ { n + 1 } ^ { 0 } - x \bigr \| _ { 2 } } \qquad } & { { } } \end{array}
$$

根据 $A$ 的限制自同构性质，可以得到

$$
\Vert \mathrm { \ b { ~ x } } _ { n + 1 } ^ { * } - \boldsymbol { x } \Vert _ { 2 } ^ { 2 } \leq \frac { 1 } { 1 - \delta _ { 2 s } } \Vert \mathrm { \ b { ~ A x } } _ { n + 1 } ^ { * } - \boldsymbol { y } \Vert _ { 2 } ^ { 2 }
$$

$$
\begin{array} { c } { \displaystyle \leq \frac { 1 } { 1 - \delta _ { 2 s } } \| ( D - W L ) ^ { - 1 } ( ( 1 - W ) D + W L ^ { * } ) x _ { n + 1 } ^ { k - 1 } } \\ { \displaystyle + w ( 0 - W L ) ^ { - 1 } A _ { n } ^ { * } y - y \| _ { 2 } ^ { 2 } \leq \frac { 1 + \delta _ { 2 s } } { 1 - \delta _ { 2 s } } \| ( x _ { n } ) _ { S _ { n + 1 } } - x \| _ { 2 } ^ { 2 } } \end{array}
$$

$$
\begin{array} { c } { { \displaystyle = \frac { 1 + \delta _ { 2 s } } { 1 - \delta _ { 2 s } } \big \| ( ( D - W L ) ^ { - 1 } ( ( 1 - W ) D + W L ^ { * } ) x _ { n + 1 } ^ { k - 1 } } } \\ { { \displaystyle \qquad + w ( 0 - W L ) ^ { - 1 } A _ { n } ^ { * } y - x ) _ { S _ { n + 1 } } \big \| _ { 2 } ^ { 2 } + \frac { 1 + \delta _ { 2 s } } { 1 - \delta _ { 2 s } } \big \| ( x ) _ { S _ { n + 1 } } \big \| _ { 2 } ^ { 2 } } } \end{array}
$$

$$
\leq \frac { 1 + \delta _ { 2 s } } { 1 - \delta _ { 2 s } } \Vert \left( x _ { n } - x \right) \Vert _ { 2 } ^ { 2 } + \frac { 1 + \delta _ { 2 s } } { 1 - \delta _ { 2 s } } \Vert \left( x _ { n + 1 } - x \right) _ { S _ { n + 1 } } \Vert _ { 2 } ^ { 2 }
$$

由算法3的格式,有 $x _ { n + 1 } ^ { 0 } = ( x _ { n } + A ^ { * } ( y - A x _ { n } ) ) _ { S _ { n + 1 } }$ ,根据引理1得到

$$
\parallel x _ { n + 1 } ^ { 0 } - x \parallel _ { 2 } ^ { 2 } = \parallel ( x _ { n } + A ^ { * } ( y - A x _ { n } ) ) _ { S _ { n + 1 } } - x \parallel _ { 2 } ^ { 2 }
$$

|(xn-x+A\*(y-Axn))sn,I²+|xsn+,I=||[(I-A\*A)(x-xn)]sn, $+ \| x _ { S _ { n + 1 } }$ 1

$$
\leq \delta _ { 2 s } ^ { 2 } \parallel x - x _ { n } \parallel _ { 2 } ^ { 2 } + \parallel ( x _ { n + 1 } - x ) _ { S _ { n + 1 } } \mid
$$

两边开方得到

$$
\begin{array} { r } { \Vert \left. x _ { n + 1 } ^ { 0 } - x \right. _ { 2 } \leq \delta _ { 2 s } \left. x - x _ { n } \right. _ { 2 } + \Vert \left( x _ { n + 1 } - x \right) _ { S _ { n + 1 } } \Vert _ { 2 } } \end{array}
$$

因此,将该结果和式(20)代入式(19)得到

$$
\| \left( x _ { n + 1 } - x \right) _ { S _ { n + 1 } } \| _ { 2 }
$$

$$
\begin{array} { r l r } {  { \le [ ( \delta _ { s } + \gamma ( l ) ) \sqrt { \frac { 1 + \delta _ { s } } { 1 - \delta _ { s } } } + \delta _ { 2 s } \gamma ( l ) ] \| x _ { n } - x \| _ { 2 } + } } \\ & { } & { [ ( \delta _ { s } + \gamma ( l ) ) \sqrt { \frac { 1 + \delta _ { s } } { 1 - \delta _ { s } } } + \delta _ { 2 s } \gamma ( l ) ] \| ( x _ { n + 1 } - x ) _ { S _ { n + 1 } } \| _ { 2 } } \end{array}
$$

由引理3得到将式(18)代入上式中得到

$$
\begin{array} { r l } {  { \big \| ( x _ { n + 1 } - x ) _ { S _ { n + 1 } } \big \| _ { 2 } } \quad } & { } \\ & { \leq [ ( 1 + \delta _ { 2 s } ) ( \delta _ { 2 s } + \gamma ( l ) ) \sqrt { \frac { 1 + \delta _ { 2 s } } { 1 - \delta _ { 2 s } } } } \\ & { \quad \quad + \delta _ { 2 s } \gamma ( l ) ] \big \| x _ { n } - x \big \| _ { 2 } } \end{array}
$$

最后可以得到

$$
\begin{array} { c } { { \| x _ { n + 1 } - x \| _ { 2 } { \leq } \| \left( x _ { n + 1 } - x \right) _ { S _ { n + 1 } } \| _ { 2 } + } } \\ { { \| \left( x _ { n + 1 } - x \right) _ { S _ { n } } \| _ { 2 } { \leq } \rho \| x _ { n } - x \| _ { 2 } } } \end{array}
$$

因此得到： $\left\| { \boldsymbol { x } } _ { n + 1 } - { \boldsymbol { x } } \right\| _ { 2 } \leq \rho \left\| { \boldsymbol { x } } _ { n } - { \boldsymbol { x } } \right\| _ { 2 }$ ，因此本文算法证明成立。

# 3 实验仿真

# 3.1算法重构性能对比

为了进一步说明本文算法重构性能,选择信号长度 $N$ 为256,稀疏度为 $K$ 的随机信号 $x$ ，设定 $\Phi$ 为 $M \times N$ 为随机高斯矩阵,测量值为 $y = \Phi x$ ,实验信号的稀疏度比值设定为[0.05,0.3]之间，重构精度以误差率 $f = \left\| { \boldsymbol { x } } ^ { \prime } - { \boldsymbol { x } } \right\|$ /xI作为判定比较标准，设定当误差率小于1e-004的时候，说明信号重构成功，当误差率大于等于1,则说明信号重构失败,将OMP,SP,CoSamp,IHT与本文算法在重构性能和运算复杂度两个指标上进行对比。设定实验运行300次,对这5种算法的实验数据结果按照取平均值进行计算。图1和2显示了这5种算法在不同的稀疏度下的重构精度以及算法所需要的时间。

![](images/7a961019202af633898cfda82e5285c04529fd8d8ada93b24c81b53c4de819d4.jpg)  
图1不同算法下的重构精确率对比

![](images/6b0e3a4b6e734607576633f1fbea1ae7c81d93178db1c9796d371feb81bf4272.jpg)  
Fig.1Comparison of the Reconstructing Accuracy under Different   
Fig.2Average Operation Time under Different Algorithms

图1显示了在不同的稀疏度数值下的5种算法重构精度的对比,从图中发现随着稀疏度数值不断增大，5种算法的重构精度都在不断的减少,从图中的曲线中发现本文算法是在稀疏度值接近0.2位置才开始下降,是所有曲线下降最晚的，这说明本文算法在重构精度方面具有一定优势。图2显示了各种算法平均运行时间,伴随着 $\kappa$ 的不断增大,本文算法的运行时间相比于其他算法是最短的。

# 3.2算法抗躁性能对比

为了进一步说明该算法具有的抗躁效果,本文选取了选取稀疏度 $K$ 值为30的上述信号，设定 $e$ 为干扰噪声,观测向量表达式为 $y = \Phi x + e$ ，干扰噪声设定分别为0.01,0.05,0.1,0.15,分别对OMP,SP,CoSamp,IHT以及本文算法进行抗噪性对比,实验结果如表1所示。

表1算法抗躁性性能比较  
Table 1Comparison of the Algorithms’Anti-manic performance   
表2不同算法下的重构性能和时间对比  

<html><body><table><tr><td>算法</td><td>e=0.01</td><td>e=0.05</td><td>e=0.1</td><td>e=0.15</td></tr><tr><td>OMP</td><td>0.015</td><td>0.25</td><td>0.62</td><td>0.97</td></tr><tr><td>SP</td><td>0.017</td><td>0.1</td><td>0.22</td><td>0.65</td></tr><tr><td>CoSamp</td><td>0.019</td><td>0.15</td><td>0.26</td><td>0.46</td></tr><tr><td>IHT</td><td>0.013</td><td>0.09</td><td>0.21</td><td>0.29</td></tr><tr><td>本文算法</td><td>0.011</td><td>0.06</td><td>0.16</td><td>0.19</td></tr></table></body></html>

从表1中发现本文算法的抗躁效果要优于OMP,SP等传统的重构算法,特别是随着干扰噪声数值逐渐增大,本文算法的噪声数值增长最小,说明具有良好的抗躁性。

# 3.3 图像对比

对图像进行实验，选取 $2 5 6 \times 2 5 6$ 的Lena图像,采用高斯矩阵为观测矩阵,稀疏基选择小波变换矩阵,设置观测次数为[100,200],进行500次实验后的平均数据。表2显示了5种算法的重构图像的PSNR值,从表2中可以发现,本文算法的重构图像的PSNR 值相比CoSamp 和IHT 提高了0.2-0.6dB,比OMP和SP提高了 $0 . 8 { \sim } 0 . 9 \mathrm { d B }$

Table 2 Comparison of Reconstructing Performance and Time under   

<html><body><table><tr><td colspan="5">DifferentAlgorithms</td></tr><tr><td rowspan="2">算法</td><td colspan="2">M=100</td><td colspan="2">M=200</td></tr><tr><td>PSNR</td><td>时间</td><td>PSNR</td><td>时间</td></tr><tr><td>OMP</td><td>28.94</td><td>6.99</td><td>31.07</td><td>9.76</td></tr><tr><td>SP</td><td>29.13</td><td>7.73</td><td>31.23</td><td>21.58</td></tr><tr><td>CoSaMP</td><td>29.71</td><td>16.52</td><td>31.29</td><td>42.95</td></tr><tr><td>IHT</td><td>29.82</td><td>4.48</td><td>31.24</td><td>4.57</td></tr><tr><td>本文算法</td><td>29.98</td><td>16.75</td><td>31.86</td><td>44.07</td></tr></table></body></html>

为了测试该算法在确定型观测矩阵下精够重构图像，观测矩阵部分选取部分哈达玛矩阵,实验结果如图3所示。

![](images/140961a3ceea437d48af1e3bb2cfd2fba9b915e132cb93cc989d4e74f7eaa2ff.jpg)  
图2不同算法下的平均运行时间  
图3不同算法下的哈达玛矩阵下的PSNR 值对比Fig.3Comparison of PSNR Values under Hadamard Matrix underDifferent Algorithms

图3中显示了随着观测数目不断增加,五种算法的重构图像的PSNR数值也不断提高,从整体上看本文算法均好于其他几种算法，采用部分哈达玛矩阵也能精确地重构图像。因此本文算法能够有效地重构信号。

# 4 结束语

重构算法一直都是压缩感知中的重要研究方向,本文针对硬阈值追踪算法自身存在的不足,提出了引入Nesterov和逐次超松弛进行改进，仿真实验说明本文算法能够有效的提高收敛性,降低运行时间，提高了重构效果。

# 参考文献：

[1]Donoho D L.Compressed sensing [J].IEEE Trans on Information Theroy,2006,52 (4):1289-1306.   
[2]Baraniuk R.Compressed sensing[J].IEEE Signal Processing Magazine, 2007,24 (4): 118-121.   
[3]Candes E J,Romberg J,Tao T.Robust uncertainty principles:exact signal reconstruction from highly incomplete frequency information [J]. IEEE Trans on Information Theroy,2006,52 (2):489-509.   
[4]Candes E J,Tao T.Decoding by linear programming[J].IEEE Trans on Information Theroy,2005,51(12):4203-4215.   
[5] Bruckstein A M,Donoho D L,Elad M.From sparse solutions of systems of equations to sparse modeling of Signals and images [J]. SIAM Review,2009,51 (1): 34-81.   
[6]Chen Shaobing S,Donoho DL, Saunders MA..Atomic decomposition by basis pursuit [J]. SIAM Journal of Science Computing,1988,20（1):   
33-01. [7]Kim S J,Koh K,Lustig M.An interior-point method for large-scale $\mathrm { L } _ { 1 }$ -regularized least squares [J].IEEE Journal of Selected Topics in Signal Processing,207,1(4): 606-617. [8]Mehrotra S. On the implementation of a primal-dual interior point method [J].Society for Industrial and Applied Mathematics,1992,2(4):   
575-601 [9]Tropp JA.Gilbert A C. Signal recovery from random measurements via orthogonal matching pursuit [J].IEEE Trans on Information Theroy,   
2007,53 (12): 4655-4666 [10] Needell D,Vershynin R. Signal recovery from incompleteand inaccurate measurements via regularized orthogonal matching pursuit [J].IEEE Journal of Selected Topics in Signal Processing,2010,4 (2):   
310-316 [11] Donoho DL,Tsagi Y,DroriI,et al. Sparse solution of underdetermined systems of linear equations by stagewise orthogonal matching pursuit [J].IEEE Trans on Information Theroy,2012,58 (2):1094-1121 [12] Hassanieh H, Indyk P,Katabi D,et al.Nearly optimal sparse fourier transform [C]// Proc of Annual ACM Symposium on Theory of Computing.New York:ACM Press2012:563-578. [13] Blumensath T,Davies ME. Iterative hard thresholding for compressed sensing [J].Applied and Computational Harmonic Analysis,2009,27,   
265-274. [14]陈鹏，孟晨，王成．基于冗余字典的联合稀疏同步迭代硬阈值算法 [J]．计算机应用,2015,35(9):2508-2512(Chen Peng，Meng Chen, Wang Cheng. Simultaneous iterative hard thresholding for joint sparse recovery based on redundant dictionaries [J] .Journal of Computer Applications,2015,35 (9):2508-2512) [15]唐文娟，赵生妹，郑宝玉．一种混合支撑集模型的联合半迭代硬阀 值追踪重构算法[J]．信号处理，2015,31(8)：924-931.（Tang Wenjuan, Zhao Shengmei, Zheng Baoyu. Study on joint semi-iterative hard thresholding pursuit algorithm in mixed support-set model [J]. Signal Processing,2015,31 (8): 924-931)   
[16]牛亚坤，王振明，李陶深．一种压缩采样硬阈值追踪压缩感知重构 算法[J].计算机应用研究,2015,32(8):2286-2288.(Niu Yakun,Yu Zhenming,Li Taoshen.Compressed sampling hard threshold pursuit algorithm with compressive sensing [J]，Application Research of Computers,2015,32 (8):2286-2288)   
[17] JainP,Tewari A,Dhillon IS.Partial hard thresholding [J],IEEE Trans on Information Theory,2017,63 (5),3029-3038   
[18] Baraniuk RG,Foucart S,Needell D,et al. One-bit compressive sensing of dictionary-sparse signals [EB/OL].(2016-06-24).http://www.math. tamu.edu/\~foucart/publi/Dict1Bit_v11.pdf.   
[19]Hu Rui,Fu Yuli,Chen Zhen,et al.A lorentzian IHT for complex-valued sparse signal recovery [J]. Circuits Systems and Signal Processing, 2018,37 (2): 862-872.   
[20] ShalabyWA,Saad W,Shokair M,et al.Efficient parameters for compressed sensing recovery algorithms [J].WirelessPersonal Communications,2017,94(3):1715-1736.   
[21] Wei Ke,Cai JianFeng,Chan TF,et al.Guarantees of Riemannian optimization for low rank matrix recovery[J]. SIAM Journal on Matrix Analysis and Applications,2016,37 (3): 1198-1222.   
[22] Sabarinath G,Jose B R.A noise reduced hard thresholding method for noisy sparse reconstruction [J].IOP Conference Series:Materials Science and Engineering,2018,396(1): 1-8   
[23]孙涛．快速稀疏恢复算法研究[D]，长沙：国防科技大学，2014 (Sun Tao.Fast sparse recovery algorithms [D].Changsha: National University of Defense Technology,2014)   
[24] Foucart S.Hard thresholding pursuit:an algorithm for compressive sensing [J]. SIAM Journal on Numerical Analysis,2011,49,2543-2563.   
[25] Foucart S.Sparse recovery algorithms: sufficient conditions in terms of restricted isometry constants [C]//Approximation Theory XII.New York: Springer,2010,