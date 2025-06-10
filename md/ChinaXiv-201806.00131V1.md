# 基于遗传算法的B样条曲线拟合改进算法\*

高茂庭，冯莉

(上海海事大学 信息工程学院，上海 201306)

摘要：B样条曲线拟合应用于绘制离散数据点的变化趋势，一般采用数据逼近或者迭代的方法得到，是图像处理和逆向工程中的重要内容。针对待拟合曲线存在多峰值、尖点、间断等问题，提出一种基于遗传算法的B样条曲线拟合算法。首先利用惩罚函数将带约束的曲线优化问题转换为无约束问题，然后利用改进的遗传算法来选择合适的适应度函数，再结合模拟退火算法自适应调整节点的数量和位置，在寻优的过程中找到最优的节点向量，持续迭代直到产生最终的优良重建曲线为止。实验结果表明，算法有效地提高了精度并加快了收敛速度。

关键词：曲线拟合；惩罚函数；遗传算法；节点向量 中图分类号：TP3 doi:10.3969/j.issn.1001-3695.2018.03.0194

# Improved B-spline curve fitting algorithm based on genetic algorithm

Gao Maoting, Feng Li (College ofInformation Engineering,Shanghai Maritime University,Shanghai 20l306,China)

Abstract: B-spline curve fiting isapplied todrawthechanging trendof discrete data points,whichusuallobtains by data approximationor iterative method.It plays an important part in image processing and reverse enginering.Aiming at the situations wheremultipeak,cuspidalpointordiscontinuityexistsinthecurve toft,thispaperproposedaB-splinecurefiting algorithmbasedongeneticalgorithm.Firstlyitusedthe penalty function to transform theconstrainedoptimizationprobleminto an unconstrained problem.Then it usedanimproved geneticalgorithmtoselectanadaptive fitnessfunction,ndadjusted the number andpositions ofnodes adaptivelybycombining thesimulatedannealing algorithmtofindtheoptimalnode vector.The iterationscontinueduntil generating thefinal goodreconstructioncurve.Experimentalresultsshowthat thealgorithmimproves accuracy and speeds up convergence effectively.

Key words:curve fitting; penalty function; genetic algorithm; node vector

# 0 引言

曲线拟合是用连续曲线近似地刻画或比拟一组离散点坐标之间函数关系的一种数据处理方法，已经广泛地应用于逆向工程和图像处理等相关领域。曲线拟合算法主要分为两大类：一类是参数拟合，将因变量和自变量通过参数方程表示出来，常用的最小二乘法[1]是以误差的平方和最小为准则，根据测量数据估计线性模型中未知参数的一种基本参数估计方法，在理论研究和工程应用中都具有重要的作用，同时又是许多其他更复杂方法的基础；另一类是非参数拟合，其直接找出因变量和自变量之间的函数关系，一般采用插值法。常用的有牛顿插值多项式法、差商与牛顿插值法、分段低次插值法等。

Bezier曲线是工程上较为常用的一种拟合曲线，具有对称性、端点性、凸包性、几何不变性、变差缩减性等很多优良性质，并且针对多项式基函数的整体性效果较好。在实际应用中，通常采用分段的低次Bezier曲线段进行拼接，但是它缺乏灵活性，曲线的次数严格依赖于确定该曲线的数据点的个数，而且局部性能很差，若要改变一段曲线，则需要调整所有的控制点位置。而B样条曲线作为Bezier曲线的一般化，既保留了Bezier曲线的优点，又增强了可局部修改的特性，可容易地解决连续性的拼接问题，实现曲线的重建。

节点向量3和数据参数4是决定拟合效果好坏的重要因素。针对B样条曲线拟合中的多峰值、非线性问题，以及待拟合的曲线有尖点、间断的情况，提出基于改进的遗传算法的B样条曲线拟合算法，依据最小二乘模型控制误差，并通过遗传算法选择最优的节点向量。在遗传优化中，结合模拟退火算法5和改进的遗传算子克服早熟、收敛慢和精度不高问题。

# 1 相关研究

B 样条理论最早由 Schoenberg 在1946 年提出，之后Boor、

Cox在1972年分别独立定义出B样条的标准算法，接着Gordon和Riesenfeld把B样条运用于描述形状，进而就提出了B样条方法，将B样条基函数取代Bernstain基函数，生成B样条曲线。

对于B样条曲线拟合问题，国内外的学者已经进行了很多相应的研究，同时提出了各种不同的方法。比如Piegl等人提出点-切约束限制的B样条曲线插值算法；Lin等提出依据切线的曲率条件的三次B样条曲线几何算法；肖秩军等人"提出采用迭代最近点来优化修正数据点的参数的方法；李继云等人[8]提出在给定的误差下，基于最少数据点的B样条曲线拟合算法;段振云等人结合曲线插值与B样条曲线拟合，增加型值点以保证曲线局部性的算法。除了传统的由方程推导或者几何方法来求解曲线拟合外，也出现了多种结合人工智能算法来进行优化的算法。Yoshimoto等人利用遗传算法的实数编码求解无约束的拟合算法；孙越泓等人[10]提出将数据参数和节点向量建立联系，提高遗传算法适应度，优化种群进化的方法；徐善健等人[1]提出针对不连续的曲线，结合混沌蚂蚁群优化算法，调整自由节点位置的思想；Galvez 等人[12在遗传算法拟合的基础上运用粒子群优化动态确定向量长度和节点个数来优化曲线等。上述算法在一定程度上都进行了优化，但精度、收敛速度和遗传算法的“早熟”问题还需要进一步地改进。这些方法大都以算法的拟合精度作为优化目标，又综合考虑收敛速度和人工智能算法本身局限性，从而将所求问题最终转换成多约束的非线性优化问题。

拟合曲线的逼近效果很大程度上取决于节点向量的选择，合适的节点向量对于曲线的逼近有着关键的作用。本文利用遗传算法确定节点向量，由最小二乘法将数据参数和节点向量联系起来，控制曲线拟合精度，最终完成曲线的重建。针对曲线拟合中局部收敛速度过慢、容易出现早熟现象的问题，重新定义适应度函数，再结合模拟退火算子，最后改变遗传算法的交叉[13]、变异算子来增加种群的多样性，保证最后的全局收敛。曲线拟合算法的思路流程如图1所示。

# 2 B样条拟合问题描述及模型建立

# 2.1 最小二乘模型

给定一组非递减序列 $U : u _ { 0 } \leq u _ { 1 } \leq \cdots \leq u _ { n + k + 1 }$ ， $U$ 代表节点向量，那么B样条函数的基函数如式(1)(2)所示。

$$
N _ { i , 0 } ( t ) = \Big \{ { 1 \} \begin{array} { r l } { ( u _ { i } \leq t \leq u _ { i + 1 } ) } \\ { 0 } \end{array} }
$$

$$
N _ { i , k } ( t ) = \frac { t - u _ { i } } { u _ { i + k } - u _ { i } } N _ { i , k - 1 } ( t ) + \frac { u _ { i + k + 1 } - t } { u _ { i + k + 1 } - u _ { i } } N _ { i + 1 , k - 1 } ( t )
$$

式(2)中： $k$ 表示指向曲线的阶数。B样条的参数方程为

$$
p ( t ) = \sum _ { i = 0 } ^ { n } d _ { i } N _ { i , k } ( t ) s s
$$

式(3)中： $d _ { i }$ 表示 $\mathrm { ~ B ~ }$ 样条曲线的控制点坐标向量，如果数据点集$P = \left\{ p _ { j } \colon j = 1 , 2 , \cdots , r \right\}$ 就在这条曲线上，那么点 $p _ { j }$ 满足

$$
p ( t _ { j } ) = \sum _ { i = 0 } ^ { n } d _ { i } N _ { i , k } ( t _ { j } )
$$

将式(4)改写成矩阵形式得到

$$
P = N * D
$$

式(5)中： $P$ 表示 $\cdot _ { r }$ 个数据的 $r \times 3$ 的矩阵； $N$ 表示 $\cdot r \times n$ 的B样条基函数系数矩阵； $d$ 表示含有 $\mathrm { n } \times 3$ 个控制点的控制点矩阵。当$k < n < r$ 时，式(5)可以用最小二乘求出近似解，如式(6)所示。

$$
D = ( N ^ { T } N ) ^ { - 1 } N ^ { T } P
$$

由此得到曲线的误差为

$$
E = \sum _ { j = 1 } ^ { n - 1 } ( D \big ( t _ { j } \big ) - p _ { j } ) ^ { 2 }
$$

![](images/dcf239977ce0cf9ba2f33969de7ab1abeec3ce7380af4991bc58eb7b01b791b5.jpg)  
图1曲线拟合思路流程

$$
E = D ^ { T } ( I - N N ^ { - } ) D
$$

从式(7) (8)中明显可以看出误差的大小与参数 $t _ { j }$ 的数值直接相关。

# 2.2问题提出及基本解决思路

事先确定好数据参数或节点向量的方法并不是最佳的拟合方法，选择把这两个量作为变量，才是寻求最好的拟合效果的办法。考虑到两者之间的联系，根据最小二乘模型来动态设置节点向量，改变B样条曲线的大小和逼近效果。由于所设置的节点是不断变化的，再经过遗传算法的迭代之后并不能保证式(6)中的 $N ^ { T } N$ 保持正定，并且最小二乘法求出来的是极值，不能确保一定是最值，而且采用基于函数的方法求导也不能保证每个函数都存在导数，所以选择损失函数14的概念来改进传统的最小二乘解法。

根据B样条曲线的参数函数，假使控制顶点 $\{ P _ { i } \} , i =$ $0 , 1 , \cdots , n$ 和节点向量 $\{ u _ { j } \} , j = 0 , 1 , \cdots , n + p + 1$ 都是未知的变量，那么B样条曲线逼近问题就可以转换成一个非线性的最小值优化问题[15]，如式(9)(10)所示。

$$
Q = \operatorname* { m i n } \left( \sum _ { i = 0 } ^ { m } \lVert d _ { i } - p ( t _ { i } ) \rVert ^ { 2 } \right)
$$

$$
Q = \operatorname* { m i n } \left( \sum _ { i = 0 } ^ { m } \left\| d _ { i } - \sum _ { j = 0 } ^ { n } N _ { j , p } ( t _ { i } ) P _ { j } \right\| ^ { 2 } \right)
$$

使用传统的方法来求解上述的最小值优化问题比较困难，从而对传统方法进行改进，通过遗传算法结合惩罚函数，将有约束的优化问题转换成无约束的问题。在遗传算法优化中，选择一个合适的适应度函数，改变三个基本算子，加上模拟退火算子，得到节点向量，接着带入最小二乘模型中得到最优控制点，最终生成最优的曲线拟合。

# 3 改进的B样条曲线拟合算法

针对曲线拟合对于光滑、尖点和非连续问题的处理不足，改进遗传算法的算子，提出改进的拟合算法。算法的处理步骤如下：

(a)输入待拟合的数据 $d _ { i }$ (b)数据点的参数化设置，以及相应的适应度函数的建立；(c)遗传算法的参数初始化，包括种群大小popsize、交叉概率 $p _ { c }$ 、变异概率 ${ \cdot } p _ { m }$ 、最大迭代次数；(d)根据格雷码的编码方式初始化种群8(t);(e)由最小二乘法得出曲线控制点，并计算每一个个体的适应度函数值；(f)迭代计算，最终输出最优的节点向量和控制点，重建曲线，否则转到 $( \mathrm { g ) }$ ：$( \mathrm { g ) }$ 对8(t)由上文的选择算子执行选择操作得 $\delta ^ { 1 } ( \mathfrak { t } )$ (h)对81(t)由上文的交叉算子执行交叉操作得 $\delta ^ { 2 } ( \mathrm { t } )$ (i)对 $\delta ^ { 2 } ( \mathfrak { t } )$ 由上文的变异算子执行变异操作得 $\delta ^ { 3 } ( \mathrm { t } )$ ，然后转(e)。

依据上述的算法步骤，重点改进最小二乘法和遗传算子得 到最优的节点向量，接下来详细介绍具体过程。

# 3.1传统最小二乘解法的改进

在最小二乘法中，可以将最终的误差表达式理解成损失函数，需要使用梯度向量和雅可比向量(Jacobian matrix)表示。定义雅可比矩阵是以误差对参数的偏导数为元素，如式(11)所示。

$$
J _ { i , j } f ( w ) = \frac { d e _ { i } } { d w _ { j } } ( i = 1 , 2 , \cdots , m & { j } = 1 , 2 , \cdots , n )
$$

式(11)中： $\mid m$ 表示数据点的数量； $n$ 表示神经网络的参数数量，那么雅可比矩阵就是 $m \times n$ 阶矩阵。损失函数的梯度向量就如式(12)所示。

$$
\boldsymbol { \nabla } f = 2 J ^ { T } * e
$$

式(12)中： $e$ 表示所有的误差的向量值。对于权值函数的更新和优化如式(13)所示。

$$
w _ { i + 1 } = w _ { i } - ( J _ { i } ^ { T } * J _ { i } + \varepsilon _ { i } I ) ^ { - 1 } * ( 2 J _ { i } ^ { T } * e _ { i } )
$$

式(13)中： $\varepsilon$ 表示衰减因子，用来保证矩阵的正定。

# 3.2数据点参数化的设置

以最小二乘为拟合的基础，那么影响曲线形状的因素有两个：a)数据点参数化的分布；b)节点向量的选取。不同的数据点的参数和节点向量对曲线形状有着关键的作用，不合理的选取会导致逼近效果很差。

到目前为止，数据点参数化的确定方法很多，比较常用的是均匀参数化、累加弦长参数法、向心弦长参数化法等。相较于其他方法，向心弦长参数化[16可以很好地体现数据点的分布特点，并且当数据出现突然变化时，拟合效果比较准确。根据参数 $t _ { i }$ 确定数据点之间的位置关系，公式如式(14)所示。

$$
\left\{ { { t } _ { i + 1 } } = { { t } _ { i } } + \frac { \sqrt { \| { { d } _ { i + 1 } } - { { d } _ { i } } \| } } { \sum _ { j = 0 } ^ { M } { \sqrt { \left\| { { d } _ { j + 1 } } - { { d } _ { j } } \right\| } } } \right.
$$

# 3.3节点向量的设置

到目前为止，对于节点向量的设置已经提出了很多方法，主要有均匀节点向量、平均节点向量和皮格尔逼近节点向量等。第一种方法完全没有考虑数据点的分布情况，效果较差；第二种虽然考虑了数据点，但是平均选择过于简单，考虑的情况较少；第三种皮格尔提出的逼近方法，解决数量较少的问题还可以，但一旦数据量增大，计算量增加，算法效率不高。针对这种情况，本文提出新的选择方式，具体步骤如下：

a)对端点的控制点进行插值。一个非递减的节点向量 $u _ { 0 } \leq$ $u _ { 1 } \leq \cdots \leq u _ { n + p + 1 }$ ，端点节点的重复度设置成B样条的阶数为$p + 1 { : } u _ { 0 } = u _ { 1 } = \cdots = u _ { p } = 0 , u _ { n + 1 } = u _ { n + 2 } = \cdots = u _ { n + p + 1 } = 1$ b)把首尾位置的数据点作为重建的B样条曲线的首尾控制点，即 $d _ { 0 } = P _ { 0 }$ $d _ { m } = P _ { n }$ c)除了首尾外剩下了 $n + p$ 个内部的节点，这些对于拟合之前都是未知数，运用遗传算法迭代进行自适应设置，最终生成最优节点向量为止。

# 3.4遗传算法原理及相应改进

# 3.4.1遗传算法原理

遗传算法[]是借鉴大自然的“适者生存”“优胜劣汰”的思想，最早由美国人Holland教授在他的《自然界和人工系统的适应性》中提出，是一种全局优化的自适应概率搜索算法。遗传算法以个体的适应度函数值为依据，再在进化过程中进行选择、交叉和变异操作，完成寻找问题的最优解的过程。它提供了一种求解复杂系统优化问题的通用框架，在生物技术、化学工程、计算机辅助设计、医学工程等方面都有着重要的应用。

# 3.4.2算子改进以及参数设置

简单遗传算法主要包括初始种群的选取、染色体的编码、适应度函数的选取、遗传操作的设计和算法控制参数的设定五个部分。接下来进行具体描述。

a)初始种群的选取。

常用的方式都是随机生成初始种群，但考虑到初始种群的设置对于结果和算法效率都是相当重要的，而随机会使得个体分布在可行解的空间是不均匀的，因此选择均匀设计。首先将解空间分成Z个区间；然后用均匀数组来选择P个染色体；最后从 $Z \times P$ 中选择适应度值较高的Q个个体作为初始种群，从而确保个体在解空间中尽量分散。

b)染色体的编码。

遗传算法常用的的染色体编码方式是二进制或十进制编码。在进行数值优化时，具有稳定性高、种群多样性大的优点；但其随机性使得局部搜索能力较差。比如对于一些高精度的问题，当解接近于最优解后，由于其变异后表现型变化很大，不连续，所以会远离最优解，达不到稳定。由此本文选取格雷码，其连续两个整数所对应的编码值之间仅仅只有一个码位是不同的。

由二进制编码转格雷码的转换公式为

$$
g _ { m } = b _ { m }
$$

$$
g _ { i } = b _ { i } + 1 \oplus b _ { i } ( i = m - 1 , m - 2 , \cdots , 1 )
$$

c)适应度函数的选取。

适应度函数是遗传算法中其他关键步骤的依赖基础，选择一个合适的适应度函数是遗传算法优化的关键。依据前文提出的最小二乘模型，要得到优良的曲线拟合结果，就要控制误差值，并且要减少控制点个数。为此，可以设计适应度函数如式(17)所示。

$$
f i t n e s s = { \frac { 1 } { Q * \varphi + \mu } }
$$

式(17)中： $\varphi$ 表示控制因子； $\mu$ 表示修正因子。再考虑遗传算法的迭代并不能保证节点的顺序，而无序的节点是无法生成B样条曲线的，可以设计一个函数体。具体如下：(a)先对所有的个体按照大小顺序排序；(b)然后对以上的数据点采取最小二乘法求解控制点；(c)然后根据适应度函数确定个体的适应度值。通过函数体的思想，将每次迭代的结果放在一起，保证节点向量的有序性。

d)遗传算子的设计。

选择算子：主要体现适者生存的原理。由适应度函数值大小确定，保留适应度值较大的优秀个体，丢弃适应度值较小的个体。简单遗传算法中，轮盘赌选择应用较广，但随机性太大，为此，采用基于竞争指数的模拟退火选择算子[18]。采用竞争指数J综合考虑个体的适应度值fitness，简单记为 $F$ 和编码的差异度值 $c$ ，如式(18)所示。

$$
J = m _ { 1 } F + m _ { 2 } C
$$

式(18)中： $m _ { 1 }$ 和 $m _ { 2 }$ 表示比例参数，和为1。将个体按照竞争指数的大小排序，选择的先后顺序与位置先后一致，合理保持群体优良性。

交叉算子：好的交叉操作可以使个体之间的优良基因进行信息交换。在进行交叉操作时，适应度函数值高于平均适应度值的个体被定义为优良个体，需要以较高的概率交叉，以保证保留优良基因。但如果仅依靠平均适应度值，易陷入局部优化，因此考虑加入方差和熵来设计概率。

假设种群的规模大小是 $N$ ，个体适应度值是 $f _ { i }$ ，平均值是$\_ f$ ，方差表达如式(19)所示。

$$
G _ { i } = \sum _ { i = 1 } ^ { N } [ ( f _ { i } - \mathcal { I } ) ^ { 2 } / N ]
$$

方差代表群体中个体的分布情况，当方差较大即个体较为分散时，减小交叉概率，反之增加。

熵是将问题的可行解分为 $A _ { i }$ 个范围，那么种群落在 $A _ { i }$ 的个体数目为 $\lvert A _ { i } \rvert$ ，熵如式(20)所示。

$$
H _ { i } = - \sum _ { i = 1 } ^ { L } ( p l o g p _ { i } )
$$

其中： $\begin{array} { r } { p _ { i } = \frac { | A _ { i } | } { N } } \end{array}$ ，如果熵数值较大表示种群的种类较多，进化能力较强，交叉概率就需要取较小数值，反之取较大数值。最后交叉概率如式(21)所示。

$$
p _ { c } = e ^ { - ( \frac { G _ { i } } { m a x \{ G _ { i } \} + 1 } + \frac { H _ { i } } { m a x \{ H _ { i } \} + 1 } ) }
$$

由于初始的数值都是按照递增的顺序，再考虑到编码方式，所以采用算术交叉。设两个个体分别为 $x _ { 1 }$ 和 $x _ { 2 }$ ，那么交叉公式为

$$
\begin{array} { l } { { x _ { 1 } ^ { ' } = \omega _ { 1 } x _ { 1 } + \omega _ { 2 } x _ { 2 } } } \\ { { \nonumber } } \\ { { x _ { 2 } ^ { ' } = \omega _ { 1 } x _ { 2 } + \omega _ { 2 } x _ { 1 } } } \end{array}
$$

式(22） (23)中： $\omega$ 表示(0,1)之间的随机数； $\omega _ { 1 }$ 和 $\omega _ { 2 }$ 和为1。

变异算子：变异概率是直接影响遗传算法优化结果的重要因子。概率取值不能大范围地破坏优良基因，并且最好可以生成优良个体。在进行变异操作时，适应度值低于平均值的个体被定义为劣质个体，需要以较高的概率进行变异。根据上文的思路，可以加入早熟判断标准，考虑当前个体的最大适应度值与超过平均适应度个体的平均适应度值之差 $\theta$ 。变异概率定义为则如式(24)所示。

$$
p _ { m } = \frac { 1 } { 1 + e ^ { - ( k * \theta ) } }
$$

式(24)中： $k$ 是控制因子，大于0，变异概率与 $\theta$ 同步变化。满足变异条件时，在每个基因 $j _ { i }$ 中产生一个随机数s，如果这个随机数小于变异概率，执行单点变异，如式(25)所示。

$$
\begin{array} { r } { j _ { i } = \left\{ { j _ { i - 1 } + u * j _ { i - 1 } } \right. } \\ { \left. ( j _ { i } + u ) \right. } \end{array}
$$

式(25)中： $u$ 表示 $( 0 , 1 )$ 中的随机数，秉持了最优选择和最差抛弃原则。

如果持续按照上述步骤执行，尽管结果可以尽快向最优解靠近，但是个体之间的相似度会越来越高，种群的多样性也就逐步降低，很容易出现局部收敛的现象。为了解决这个问题，结合上文的早熟判断指标，达到指标时，过滤到相似个体。具体做法如下：

a)将种群个体按照适应度值进行排序；  
b)根据编码方式计算相似度，确定一个β值；  
c)把相似值结果与β进行比较，删除相似的个体。

完成过滤操作后，需要有新的个体来补充，不能用直接随机生成的方式，不利于全局搜索，可以将原本中适应度比较高的个体进行变异，增加优良个体，与其他原本的个体也更易产生有优良的子代。

# 4 实验结果与分析

为了检验本文提出的基于遗传算法的B样条曲线拟合算法的实际应用效果，针对具有平滑、不连续和有尖点特点的测试函数，选择出合适的节点，然后得出拟合结果，并与传统简单遗传算法、结合蚁群算法优化的拟合方法进行比较。

# 4.1实验环境

实验硬件环境是CPUIntel(R)Core(TM)2Duo,内存为4 GB,操作系统环境是Windows7，编程平台和实验环境为MATLAB8.0。

# 4.2 测试函数的选择

考虑到具有平滑、不连续和有尖点特点的测试函数，可以测试出曲线拟合算法的多适应性。采用文献[11]中的三个函数作为测试函数，这也是较多B样条曲线拟合选择的函数，它们的表达式和定义域如表1所示。

表1测试函数  

<html><body><table><tr><td>函数</td><td>表达式</td><td>定义域</td><td>n-k</td></tr><tr><td>fi(x)</td><td>90 1+e-100(x-0.4)</td><td>x ∈ [0,1]</td><td>1~7</td></tr><tr><td>f(x)</td><td>1 0.01+(x-0.3)²</td><td>x ∈[0,0.6)</td><td>1~17</td></tr><tr><td></td><td>1 (0.015+(x-0.65)²</td><td>x ∈[0.6,1]</td><td></td></tr><tr><td>f(x)</td><td>100 (10x-5)5 +</td><td>x ∈[0,1]</td><td>1~17</td></tr></table></body></html>

# 4.3 实验结果及分析

# 4.3.1最优节点数目的选取

通过对测试函数 $f _ { 1 } ( x ) , f _ { 2 } ( x )$ 和 $f _ { 3 } ( x )$ 的节点数目随着迭代次数的增加而发生的演变趋势的分析，从而可以得到最优的节点数目，重建出函数曲线的拟合图。三个测试函数的迭代次数和节点数目的函数关系如图 $( 2 ) \sim ( 4 )$ 所示。

![](images/ce810367f759088b80228440f7f5c4a0e1cd36612964564b9316541ffaf4f3a9.jpg)  
图2测试函数 $f _ { 1 } ( x )$ 的迭代次数与节点数的关系

![](images/a965c376611ba18d8c5860495cd0dc5d3ad70de9f894d722e4ad11f4b1009250.jpg)  
图3测试函数 $f _ { 2 } ( x )$ 的迭代次数与节点数的关系

![](images/9953af6277ef9c01d448487cc377ca744bb1175c85cd9d15254e66d6a0bc0ee7.jpg)  
图4测试函数 $f _ { 3 } ( x )$ 的迭代次数与节点数的关系

通过对图(2） $\sim ( 4 )$ 分析可得， $f _ { 1 } ( x )$ 的最优节点数目为4，$f _ { 2 } ( x )$ 的最优节点数目为8， $f _ { 3 } ( x )$ 的最优节点数目为5。

# 4.3.2测试函数拟合效果

由求出的最优节点，进行曲线拟合，三个测试函数的拟合效果如图(5) ${ \sim } ( 7 )$ 所示。

![](images/0573bff0eb06288e00bc0be366df92c43ffe98f786b4384097cd83732821fac7.jpg)  
图5测试函数 $f _ { 1 } ( x )$ 的拟合效果

![](images/8debaac780279eefc4ab633e529a9ca9aec5b2d9bcf4abc630b2aab5d9e87bff.jpg)  
图6测试函数 $f _ { 2 } ( x )$ 的拟合效果

![](images/011ab63d20d4495323eab8b157bc432084a76393f15a6d291911aad268004a33.jpg)  
图7测试函数 $f _ { 3 } ( x )$ 的拟合效果

图(5) ${ \sim } ( 7 )$ 分别表示运用本文提出的方法对测试函数的拟合效果，图(5)是带有平滑部分的曲线拟合效果，从中可以看出，在平滑位置的拟合效果较好，虽然部分区域存在一定的偏差，但都在可接受范围内；图(6是不连续的曲线拟合情况，由图可以看出在间断点处的处理很好，接近原来的曲线趋势；图(7)是有尖点的曲线，在拟合的图中可以明显有极值的情况，而且基本展示出其原本的特征。通过以上三个测试函数的拟合效果，表明基于改进遗传算法的B样条曲线拟合算法对于平滑、不连续和带尖点三种情况处理良好，拟合效果与实际曲线趋势几乎一致，由此说明算法性能优良。

# 4.3.3与其他拟合算法的比较

为了进一步评估本文提出的算法的合理性，对比分析三种算法按式(8)计算结果。表2给出了本文算法与文献[1]、文献[11]的拟合误差。

表2测试函数的误差比较  

<html><body><table><tr><td>测试函数</td><td>f1(x)的数据点 误差</td><td>f2(x)的数据点 误差</td><td>f(x)的数据点 误差</td></tr><tr><td>本文方法</td><td>1.075e-06</td><td>4.062e-06</td><td>1.773e-02</td></tr><tr><td>文献[1]的方法</td><td>5.967e+00</td><td>9.327e-01</td><td>7.762e+01</td></tr><tr><td>文献[11]的方法</td><td>2.563e-04</td><td>3.743e-04</td><td>5.532e-02</td></tr></table></body></html>

由表(2)的数据可知，三个测试函数在应用本文算法拟合时，误差都相对较小，逼近效果更好。

# 5 结束语

本文从遗传算法的重要算子进行改进，结合最小二乘模型，实验结果表明，采用上述的改进遗传算法对曲线进行逼近效果更好，精度更高。但是对于遗传算法要获得更高的数值精度，就需要提高相应的收敛速度，而且数值的参数化还需要加以提升，最后遗传算法的随机性很大，增加算法的稳定性将是以后值得继续研究的问题。之后还可以继续将目前研究的二维曲线问题拓展到三维曲面上，从而紧跟时代发展的步伐。

# 参考文献：

[1]周明华，汪国昭．基于遗传算法的B样条曲线和Bé zier曲线的最小二 乘拟合[J].计算机研究与发展,2005,42(1):134-143.(Zhou Minghua, Wang Guozhao.Genetic algorithm-based least square fitting ofB-spline and Bé zier curves [J].Journal of Computer Research & Development,2005,42 (1): 134-143.)   
[2]Lin Ao,Xiao Bing,Zhu Yi.An algorithm for Bayesian network structure learning based on simulated annealing with adaptive selection operator [J]. Lecture Notes in Electrical Engineering,2014,277: 525-532.   
[3]胡良臣，寿华好.基于二进制GA的B样条重构曲线节点优化[J].软 件学报，2016,27 (10):2488-2498.(Hu Liangchen，Shou Huahao. Optimization ofB spline reconstruction curve nodes based on binary GA [J] Journal of software,2016,27(10): 2488-2498.)   
[4]Yoshimoto F,Harada T,Yoshimoto Y.Data fitting with a spline using a real

coded genetic algorithm[J].Computer-Aided Design,20o3,35(8): 751-760.

[5] 张聚梅，王洪伦．基于遗传算法和模拟退火算法的B样条曲线拟合[J]. 计算机工程与科学,2011,33(3):191-193.(Zhang Jumei,Wang Honglun. B-spline curve fiting based on genetic algorithms and the simulated annealing algorithm [J].Computer Engineering & Science,2011,33(3): 191-193. )

[6]Piegl LA,Tiller W.Least-squares B-spline curve approximation with arbitary end derivatives [J].Engineering with Computers,20oo,16 (2):109- 116.   
[7]肖轶军，丁明跃，彭嘉雄．基于迭代最近点的B样条曲线拟合方法研究 [J].中国图象图形学报,2000,5(07):585-588.(Xiao Yijun,Ding Mingyue, Peng Jiaxiong. ICP-based B-spline curve fiting [J]. Journal of Image & Graphics,2000,5 (7): 585-588.)   
[8]李继云，耿兆丰．给定误差下最少数据点B 样条曲线拟合的遗传算法 研究[J].计算机辅助设计与图形学学报,2003,15(3):000334-337. (Li Jiyun,Geng Zhaofeng.Astudyofleast point B-spline curve fiting algorithm with given error based on genetic algorithm[J].Journal ofComputer Aided Design& Computer Graphics,2003,15(3):000334-337)   
[9]段振云，王宁，杨旭等．一种改进B 样条曲线拟合算法研究[J].机械 设计与制造,2016 (5):17-19.(Duan Zhenyun,Wang Ning, Yang Xu,et al. Research on an improved B-spline curve fiting algorithm [J]. Mechanical Design& Manufacture,2016 (5): 17-19.)   
[10]孙越泓，魏建香，夏德深．基于自适应遗传算法的B样条曲线拟合的参 数优化[J].计算机应用,2010,30(7):1878-1882.(Sun Yuehong,Wei Jianxiang,Xia Deishen.Parameter optimization for B-spline curve fitting based on adaptive genetic algorithm: parameter optimization for B-spline curve fitting based on adaptive genetic algorithm [J]. Journal of Computer Applications,2010,30(7): 1878-1882.)   
[11]徐善健，郭有强，戚晓明，等．混沌蚂蚁群优化求解自由节点B 样条曲 线拟合[J].计算机工程与应用,2014,50(16):177-182.(Xu Shanjian, Guo Youqiang,Qi Xiaoming,et al.Chaotic ant swarm optimization in solving curve fiting with free knot B-splines [J]. Computer Engineering & Applications,2014,50(16):177-182.)   
[12] Galvez A,IglesiasA.Firefly algorithm for explicit B-spline curve fitting to data points [J].Mathematical Problems in Engineering,2013,2013 (2013): 206-226.   
[13] Picek S,Golub M，Jakobovic D. Evaluation of crossover operator performance in genetic algorithms with binary representation [J]. Lecture Notes in Computer Science,2011,6840: 223-230.   
[14] Jin Wei,Liu Zhijie,Jing Fengxuan.B-spline curve interpolation based on least squares of approximation [J]. Journal of Guizhou Normal University, 2015,33 (1): 98-102.   
[15] Tsuchiya T. Global optimization of polynomial-expressed nonlinear optimal control problems with semidefinite programming relaxation [J].Journal of Global Optimization,2012,54(4): 831-854.   
[16]黄伟贤，王国瑾，金聪健．可弦长参数化的复有理曲线[J].计算机辅

助设计与图形学学报,2011,23(12):1975-1980.(HuangWeixian,Wang Guojn，Jin Congjian.Complex rational curves with chord length parameterization [J].Journal of Computer-Aided Design & Computer Graphics,2011,23(12):1975-1980.)

[17]Deng Chongyang,Lin Hongwei.Progressive and iterative approximation for least squares B-spline curve and surface fiting [J]. Computer-Aided Design,

2014,47(1): 32-44.

[18]陈皓，崔杜武，严太山，等．基于竞争指数的模拟退火排序选择算子 [J].电子学报,2009,37(3):586-59.(Chen Hao,Cui Duwu,Yan Taishan et al.Simulated annealing ranking selection operator based on competition index[J].Electronic Journal,2009,37(3): 586-59.)