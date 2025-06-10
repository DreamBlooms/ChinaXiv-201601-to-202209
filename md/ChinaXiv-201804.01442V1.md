# 基于多子群的社会群体优化算法\*

刘亚军，陈得宝，邹锋，李峥，王苏霞(淮北师范大学 物理与电子信息学院，安徽 淮北 235000)

摘要：社会群体优化算法(social group optimization，SGO)是一种基于社会群体学习而提出的一种新型优化算法。针对社会群体优化算法易于陷入局部最优问题，提出了一种多群社会群体学习算法（MPSGO)。本算法采用多子群学习方法，对算法两个阶段的个体学习方法进行改进，在维持群体收敛性能的前提下提高群体多样性，同时对部分个体中引入量子学习，使个体学习的有用信息得以增强；此外，每隔一定代数对子群进行随机重组，既能保证各子群个体充分进化，又维持了子群多样性。在设计算法的基础上，分析了其收敛性和多样性；通过与其他四种算法进行对比实验，验证了改进后算法性能更优。

关键词：社会群体优化算法；多子群；量子学习 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.12.0805

# Multiple subgroups based social group optimization algorithm

Liu Yajun, Chen Debao†, Zou Feng, Li Zheng,Wang Suxia (SchoolofPhysics&Electronic Information,Huaibei Normal University,HuaibeiAnhui235000,Chi

Abstract: Social groupoptimization (SGO) is anoveloptimization algorithm which is based on social group learning.This paper proposed a multi-group social group learning algorithm(MPSGO)to solve the problem that the social group optimization algorithm was easy convergent to local optima.This algorithm adopted the multi-subgroup learning method,and the improvementofthe individuallarning methodinthe twostagesofthealgorithm.The diversityofthepopulation was improved with maintaining theconvergenceof the population.At the same time,it introduced quantum-behaved learning method into MPSGO for partsof individuals to enhance the useful information of individual learning.In addition,the population was randomlyregrouped to generate new subgroups afteracertain generation.The diversityof subgroups wais maintained and the individuals in every subgroup were fully evolved.Basedon the designing of algorithm,this paper analyzed the algorithmof convergenceand diversityCompared withtheother 4algorithms,itis proved thatthe performance ofthe improved algorithm is better.

Key words: social group optimization; multiple subgroups; quantum-behaved learning

# 0 引言

优化问题是现实生活中经常遇到的问题，如何设计算法快速准确地得到问题的最优解，是解决优化问题的关键一环。传统的优化算法往往依赖系统的精确数学模型和系统参数，对一些模型难以建立的系统，传统优化方法难以解决。自然计算方法模拟生物的自然或社会特性，其不依赖系统的精确模型，已得到广泛应用。经典的自然计算方法，如遗传算法(GA)[1]、粒子群算法(PSO)[2]、差分进化算法(DE)[3]、进化策略(ES)[4]等都已成功应用于函数优化、工程设计、自动控制、信号处理等领域。

这些算法都利用个体间信息的交换或产生部分新信息实现对问题的优化，算法自身参数对算法性能影响较大，且最优化的参数往往难以确定，一定程度上影响了算法的应用。

近年来，为减少算法自身待确定参数数量，充分利用群体信息，研究者设计了一些新的优化算法。例如教学优化算法(TLBO)[5]，模拟班级教师的授课和学生学习过程，教师在班级分享自己的知识，提高班级的平均成绩，学生除向教师学习外，还向班级的其他学生学习，以进一步提高自己的成绩。此方法中由于引入教师的信息，算法收敛速度较快，但由于个体每次学习都保留最好的解，群体多样性丢失较快，算法易于陷入局部最优解。为进一步提高TLBO 算法的性能，研究者提出了一些改进算法。例如基于邻域搜索的教学优化算法(NSTLBO)[在教学过程中引入个体的邻域信息，以增加个体学习方法的多样性，提高了TLBO 算法的性能。精英教学算法(ETLBO)[在优化过程中保留多个精英个体，利用精英个体的引导作用，改变个体的跟踪行为，进一步提高算法的收敛精度。

为进一步提高算法的收敛速度，充分发挥个体的学习能力，Satapathy 等人[8]于2016 年提出的一种基于社会群体学习的新型优化算法（SGO)。此算法操作简单，易于实现，在一些问题优化中取得了良好的效果[9]。此算法将个体的优化过程分为两个阶段，即提高阶段和获得阶段。在提高阶段，个体以群体当前最好解作为学习向导；在获得阶段，个体以群体中任意一个个体和当前代群体最好解作为指导进行学习，算法的收敛速度较快。一些典型数据集上的测试结果显示了SGO 算法的有效性[8.9]。虽然 SGO 算法的收敛速度较快，但其至少存在两方面的不足：首先，SGO 算法在学习的两个阶段中均以群体最好个体作为向导，算法的收敛速度较快，但群体多样性容易丢失，导致算法易于陷入局部最优解；其次，由于算法学习方法单一，一旦陷入局部最优解，个体逃离局部最优解的能力不足。因此，在保持SGO 算法收敛速度的前提下提高群体的多样性，成为提高算法整体性能的关键。本文在对个体更新方程改进的基础上，利用多群算法具有维持群体多样性的优点，结合量子学习强化所需解的能力，设计了一种多群社会优化算法。本文的贡献主要有三点：a)引入多子群学习提高群体的多样性；b)对每个子群中的个体，在获得阶段随机引入其他子群最优解，并将其与全局最优解和本群中其他个体信息相结合，增加子群个体学习方法的多样性；c采用简单的子群生成方法，既保证了子群个体的充分进化，又达到子群间信息交换和改善子群多样性的目的。

# 1 SGO 算法

复杂问题的解决需要多方面因素的参与，当某个个体不足以解决复杂问题时，需要向周围或拥有此项能力的个体学习，以便提高自身解决问题的能力。SGO算法是基于此种思想而提出的一种新型优化算法。SGO 算法实现过程主要包含初始化、提高、获得阶段三个步骤。描述如下：

# 1.1种群初始化

随机初始化种群 $P$ ，如式(1)所示。

$$
X _ { i , j } = x _ { \operatorname* { m i n } } + r * \left( 1 , D \right) * \left( x _ { \operatorname* { m a x } } - x _ { \operatorname* { m i n } } \right)
$$

其中： $i = 1 , 2 , 3 , . . . N$ ， $j = 1 , 2 , 3 , . . . D$ ； $N$ 为种群的规模； $D$ 为变量的维数； $\boldsymbol { r }$ 为0到1之间的随机数； $x _ { \mathrm { m a x } }$ 与 $x _ { \operatorname* { m i n } }$ 分别为变量的上下限； $P$ 为进化种群；X为个体位置。

# 1.2提高阶段

SGO算法在此阶段采用的学习策略如式(2)所示。

$$
X n e w _ { i , j } = c ^ { * } X o l d _ { i , j } + r ^ { * } \big ( g b e s t _ { j } - X o l d _ { i , j } \big )
$$

其中： $\mid c \mid$ 为自我反省参数，其取值通常在0\~1间，其经验值[8]为0.2； $\boldsymbol { r }$ 为0\~1间的随机数；gbest;为当前代最优个体的第j维基因； $X n e w _ { i , j }$ 与 $X o l d _ { i , j }$ 分别为第i个个体更新前后的第j维基因。

# 1.3获得阶段

在获得阶段，每个个体从种群中随机选择一个个体作为学习对象，并结合当前代群体的最优个体信息进行学习。具体学习方法如式（3）（4）所示。

if $f ( X _ { i } )$ is better than $f ( X _ { k } )$

$$
X n e w _ { i , j } = X o l d _ { i , j } + r _ { 1 } * \left( X _ { i , j } - X _ { k , j } \right) + r _ { 2 } * \left( g b e s t _ { j } - X _ { i , j } \right)
$$

$$
X n e w _ { i , j } = X o l d _ { i , j } + r _ { 1 } \ast \left( X _ { k , j } - X _ { i , j } \right) + r _ { 2 } \ast \left( g b e s t _ { j } - X _ { i , j } \right) \nonumber
$$

其中： $X _ { i , j }$ 与 $X _ { k , j }$ 分别为个体 $i$ 和个体 $k$ 的第 $j$ 维基因； $X n e w _ { i , j }$ 与 $X o l d _ { i , j }$ 分别为第i个个体更新前后的第j维基因； $g b e s t _ { j }$ 为当前代最优个体的第j维基因； $r _ { \mathrm { i } }$ 、 $r _ { 2 }$ 都为0\~1间的随机数。

# 2 多子群SGO 算法（MPSGO）

在基本 SGO 算法的两个阶段中，个体均以当前代群体的最优个体为参考进行位置更新。实践表明，以最优个体引导进化能加快算法的收敛速度，但不利于维持群体的多样性，易导致算法陷入早熟收敛。多群操作是一种改善群体多样性的有效方法[10]，子群间信息的交互能为个体学习提供更多的信息。多群 SGO对基本SGO算法的个体位置更新方法进行改进，充分利用子群的最优个体信息和整个群体的最优信息，引入量子学习方法，随机选择部分个体进行更新，以提高算法的收敛精度和增加群体多样性，减小算法陷入局部最优的可能。

# 2.1提高阶段的改进

由式（2）可知，基本SGO算法的提高阶段，个体向群体的最优个体学习，目的是提高算法的收敛速度，而快速的收敛易导致群体多样性丢失，算法易于陷入局部最优。此外，从知识的学习难易程度看，个体更容易从其较近的邻域个体获得知识。基于这样的思想，在MPSGO 算法中的提高阶段，以子群最优个体的信息对个体进行引导，利用就近获取知识方法使个体在其局部区域增长知识，增加个体学习知识的多样性。具体操作如下：首先将所有个体随机分成个体数量相等的若干个子群，再求取每个子群的最好个体，按照式（5）对各子群个体位置进行更新。

$$
X n e w _ { i , j } = \mathrm { c } ^ { * } X o l d _ { i , j } + \mathrm { r } ^ { * } \big ( a g b e s t ( a , j ) - X o l d _ { i , j } \big )
$$

其中： $\boldsymbol { \mathbf { \mathit { c } } }$ 的取值与基本 SGO 算法相同； $\boldsymbol { r }$ 为0\~1间的随机数;a表示第a个子群； $X n e w _ { i , j }$ 与 $X o l d _ { i , j }$ 分别为第i个个体更新前后的第 $\mathrm { j }$ 维基因； $a g b e s t ( a , j )$ 为第a个子群中最好个体的第j维基因。

# 2.2 获得阶段的改进

由式（3）（4）可知，在SGO 算法的获得阶段，个体向群体中的其他个体及群体中的最好个体学习以获得新知识，但并未考虑个体学习能力的局限性和学习方法的多样性，不利于群体多样性的维持。基于这样的分析，在MPSGO算法的获得阶段，被选择用于学习的随机个体限制在子群内部，个体除了向子群内其他个体和种群最优个体学习外，还增加了个体向其他随机选择子群的最好个体学习，以提高个体学习方法的多样性。改进的获得阶段个体更新方程如式（6）（7）所示。

对某子群中的个体i，在其所在的子群中随机选择个体k作为其学习的第一部分；在所有子群中，随机选择一个子群的最优解作为其学习的第二部分；种群的当前最优解作为其学习的第三部分，新的学习机制如下。

If $X _ { i }$ is better than $X _ { k }$

$$
\begin{array} { c } { { X n e w _ { i , j } = X _ { i , j } + r _ { 1 } * \left( X _ { i , j } - X _ { k , j } \right) + r _ { 2 } * \left( g b e s t _ { j } - X _ { i , j } \right) + \nonumber } } \\ { { r _ { 3 } * \left( a g b e s t ( a a , j ) - X _ { i , j } \right) \nonumber } } \end{array}
$$

else

$$
\begin{array} { c } { { X n e w _ { i , j } = X _ { i , j } + r _ { 1 } * \bigl ( X _ { k , j } - X _ { i , j } \bigr ) + r _ { 2 } * \bigl ( g b e s t _ { j } - X _ { i , j } \bigr ) + \nonumber } } \\ { { r _ { 3 } * \bigl ( a g b e s t \bigl ( a a , j \bigr ) - X _ { i , j } \bigr ) } } \end{array}
$$

其中：aa 为随机选择子群； $X _ { i , j }$ 与 $X _ { k , j }$ 分别为个体i和个体 $\mathbf { k }$ 的第j维基因； $g b e s t _ { j }$ 为所有子群中最优个体的第 $\mathrm { ~ j ~ }$ 维基因;agbest(aa,j)为子群 aa 中最优个体的第j维基因； $X n e w _ { i , j }$ 为$X _ { i , j }$ 为个体i更新前后第j维基因的位置。

式（6）（7）表明，在MPSGO算法的获得阶段，个体不仅从其所在子群中获得知识，同时也从全体子群的最优解和其他子群的最优解中获得知识，既兼顾了个体学习范围的局限性，又考虑到了个体学习方法的多样性。

# 2.3量子学习策略

Grover在1996年提出了一种高效的量子算法[11]，即量子搜索算法。随后，研究者把量子计算与机器学习结合起来，形成了量子学习[12\~14]。量子算法特点就是利用量子态的干涉作用,使所需的结果增强，不需要的结果减弱，这样在检测时所需的结果就会以较高的概率出现[15]。MPSGO 算法中，在子群更新过程中引入量子学习，目的是提高较优解的出现概率。本方法中，以子群最优解（agbest）及个体与群体平均值之差（20 $\left( \ X _ { i } - a M e a n ( a ) \right.$ )作为个体学习的向导。为减少适应度函数的评价次数，本文仅对子群中随机选择的部分个体进行操作。方法如下。

$$
\begin{array} { c } { { X n e w _ { i , j } = t e m p + ( ( - 1 ) * c e i l ( 0 . 2 + r a n d ( 1 , j ) ) ) * } } \\ { { b * \bigl ( - \log \bigl ( u \bigr ) \bigr ) } } \end{array}
$$

$$
t e m p = \left( p . * X _ { i , j } + m . * a g b e s t { \bigl ( } a , j { \bigr ) } \right) / \left( p + m \right)
$$

$$
b = r a n d \left( 1 \right) * \left( a M e a n X \left( a , j \right) - X _ { i , j } \right)
$$

其中： $_ { p , m , u }$ 均为0\~1间的随机数；aMean(.)为子群 $a$ 中所有个体的位置平均解。

# 2.4子群信息交换

子群间信息交换是保持各子群多样性的一个重要方法。由于子群规模往往较小，当迭代到一定代数时，子群中的个体易于趋同，导致子群多样性减小，不利于算法的收敛。此外，为给子群中的个体充分的进化时间，各子群必须进化一定的代数。为不增加算法的复杂性，在MPSGO算法中，采用一种简单的分群方法，当群体进化一定代数后，所有子群的个体随机重新组合，形成新的子群。具体操作方法为：如果进化代数能被给定的子群进化周期整除，则所有群体的个体重新混合，随机形成新的子群（ $\scriptstyle { \mathrm { I f } } { \mathrm { m o d } } ( g e n , T ) = 0$ then regroup the population）。gen为当前的优化代数。 $T$ 为设定的整数值， $T$ 越大越有利于子群充分进化， $T$ 越小越有利于维持子群多样性。

# 2.5 算法收敛性分析

最小值优化问题如下：

$$
\operatorname* { m i n } { \left\{ { f \left( X \right) } | \forall X \in \Omega , 0 < f \left( X \right) < + \infty \right\} }
$$

其中 $\Omega$ 是可行搜索空间且是非空有限集。

假设1搜索空间是范围为 $\Omega$ 的 $D$ 维空间，其中有 $\mathrm { ~  ~ N ~ }$ 个局部最优解，相对应的区域范围记是 $S _ { \nu }$ ， $S _ { \scriptscriptstyle 2 } , . . . . , S _ { \scriptscriptstyle N }$ ,记 $X ^ { * }$ 为局部区域 $\mathbf { S } ^ { \ast }$ 的最好解。

假设2　存在 $N$ 个子群，搜索区域为 $\Omega$ ， $\Omega _ { _ { 2 } } , . . . . , \Omega _ { _ { N } }$ ,每个子群可以同时搜索相对应的区域。

定理1如果前两个假设满足，则多子群算法比全群体算法具有更高找到全局最优解的概率。

证明对于全群算法，令 $p \{ X \in S ^ { * } \}$ 为找到最优解的概率，$p \{ X \in S ^ { * } \}$ 定义如下：

$$
p \{ X \in S ^ { * } \} = \prod _ { n = 1 } ^ { N } p \big \{ X \in S _ { n } \big \} = \prod _ { n = 1 } ^ { N } \frac { S _ { n } } { \Omega }
$$

对多子群算法，令 $p _ { N } \{ X \in S ^ { * } \}$ 为找到最优解的概率，$p _ { N } \{ X \in S ^ { * } \}$ 定义如下：

$$
p _ { N } \{ X \in S ^ { * } \} = \prod _ { n = 1 } ^ { N } p \left\{ X \in S _ { n } \right\} = \prod _ { n = 1 } ^ { N } { \frac { S _ { n } } { \Omega _ { n } } }
$$

则

$$
{ \frac { p _ { N } \{ X \in S ^ { * } \} } { p \{ X \in S ^ { * } \} } } = { \frac { \prod _ { n = 1 } ^ { N } { \frac { S _ { n } } { \Omega } } } { \prod _ { n = 1 } ^ { N } { \frac { S _ { n } } { \Omega _ { n } } } } } = \prod _ { n = 1 } ^ { N } { \frac { \Omega } { \Omega _ { n } } }
$$

因 $\Omega _ { n } < \Omega$ $( \mathrm { n { = } 1 } , 2 , \ \mathrm { . . . , N } )$ ，则

$$
p _ { N } \{ X \in S ^ { * } \} > p \{ X \in S ^ { * } \}
$$

由上述分析可得，多子群MPSGO算法找到最优解的概率优于单一群体的SGO算法。

对于MPSGO算法而言，群体中个体学习可以认为是变异操作算子(MO)，子代学习者与父代学习者的比较可以看做是选择操作算子 $( \mathrm { S O } ^ { ) [ 1 6 ] }$ 。在每次迭代中，MPSGO 算法优化过程依次由MO与SO实现，故利用随机泛函理论可以将一次迭代抽象为由MO和SO合成的随机映射。

定义1变异算子（MO）是一种以一定概率对个体向量的各维度分量进行重组变换的过程。它是解空间上的一种随机映射 $T _ { \scriptscriptstyle M } : \textbf {  { M } } \times \Omega  \Omega ^ { \scriptscriptstyle M }$ 。在MPSGO中，这变异操作定义为

$$
\begin{array} { r l } & { p \left\{ \omega \left| T _ { m } \left( \omega , X _ { i } \right) = n e w X _ { i } \right. \right\} } \\ & { { = } p \{ n e w X _ { i } = { \mathrm { c } } ^ { * } X o l d _ { i } } \\ & { \left. + { \mathrm { r } } ^ { * } \Big ( a g b e s t \big ( a , j \big ) - X o l d _ { i } \Big ) \right\} } \end{array}
$$

其中： $\omega$ 表示基本事件；其他参数含义与式（5）相同。

定义2选择算子（SO）是基于优胜劣汰的贪心策略思想来选择子代学习者的过程，它是解空间 $\Omega ^ { M }$ 与解空间 $\Omega$ 之间的映射关系，可以表达为 $T _ { s }$ 。 ${ \Omega } ^ { M } \to { \Omega }$ 。

对于MPSGO算法，其选择算子定义为

$$
\begin{array} { r l } & { T _ { s } \left( X _ { i } , n e w X _ { i } \right) } \\ & { = Z \wedge Z \in \left\{ X _ { i } , n e w X _ { i } \right\} \wedge f \left( Z \right) } \\ & { = \operatorname* { m i n } \left\{ f \left( X _ { i } \right) , f \left( n e w X _ { i } \right) \right\} } \end{array}
$$

由于变异算子和选择算子都是随机生成的，所以产生的学习者也是随机的，使算法具有跳出局部最优的能力，不易陷入局部最优。在MPSGO的一次迭代中，相当于将映射 $T$ 作用于当前群体 $P$ ， $T$ 表达式如下所示：

$$
T = T _ { s } \cdot T _ { M } : M \times \Omega  \Omega
$$

令 $X _ { i } ( t )$ 为第 $t$ 次迭代时群体中的第 $i$ 个个体， $X _ { i } ( t + 1 )$ 为第$t + 1$ 次迭代时群体中的第 $i$ 个个体，那么

$$
X _ { _ { i } } ( t + 1 ) = T { \left( \omega , X _ { _ { i } } ( t ) \right) } = T _ { s } \left( T _ { _ { M } } \left( \omega , X _ { _ { i } } ( t ) \right) \right)
$$

在 $T$ 作用下，MPSGO每次迭代所产生的子代个体并不差于其相应的父代个体，因此，各代群体中最优学习者对应的适应值形成一个单调非增序列，即

$$
\dots f \left( X _ { b e s t } \left( t - 1 \right) \right) \geq f \left( X _ { b e s t } \left( t \right) \right) \geq f \left( X _ { b e s t } \left( t + 1 \right) \right) \dots
$$

引理 $\mathbf { 1 } ^ { [ 1 7 ] }$ 设 $d$ 是距离函数 $d { \big ( } X _ { i } , Y _ { j } { \big ) } = \mid f { \big ( } X _ { i } { \big ) } - f { \big ( } Y _ { j } { \big ) } \mid$ ，$\forall X _ { _ { i } } , Y _ { _ { j } } \in \Omega$ 定义一个从 $\boldsymbol { \Omega \times } \boldsymbol { \Omega }$ 到 $R$ 的映射，那么， $\left( \Omega , d \right)$ 是一个完整的赋范空间。

定义3令 $\Omega$ 和 $R$ 是两个赋范空间。定义 $X _ { t } = T \big ( \omega , X _ { t - 1 } \big )$ ，如存在一个随机变量 $K ( \omega ) < 1$ 使得

$$
\begin{array} { r } { \begin{array} { l } { p \{ \omega | d \bigl ( T \bigl ( \omega , X _ { _ { t } } \bigr ) , T \bigl ( \omega , X _ { _ { t + 1 } } \bigr ) \bigr ) } \\ { \leq K \bigl ( \omega \bigr ) d \bigl ( T \bigl ( \omega , X _ { _ { t - 1 } } \bigr ) , T \bigl ( \omega , X _ { _ { t } } \bigr ) \bigr ) \} = 1 } \end{array} } \end{array}
$$

称映射 $T : \Omega \to R$ 是一个随机压缩映射。

定理2MPSGO 的一次迭代所形成的随机映射 $T$ 是一个随机压缩算子。

证明据MO 算子与SO算子的定义及式（18）可知，MPSGO在每次迭代过程中，子代最好个体可能优于父代最好个体。因而存在一个随机变量 $K ( \omega ) < 1$ ，使得

所以,

$$
\begin{array} { r l } & { d ( T ( \omega , X _ { \cdot \cdot \cdot } ) , T ( \omega , X _ { \cdot \cdot } ) ) = d ( X _ { \cdot } , X _ { \cdot + 1 } ) = \rfloor f ( X _ { \cdot } ) - f ( X _ { \cdot + 1 } )  \leq } \\ & { \qquad \kappa ( \omega ) \vert f ( X _ { \cdot \cdot \cdot } ) - f ( X _ { \cdot } ) \vert = K ( \omega ) d ( X _ { \cdot \cdot \cdot } , X _ { \cdot } ) } \\ & { \qquad \quad \Omega ^ { ' } = \{ \omega \vert d ( T ( \omega , X _ { \cdot } ) , T ( \omega , X _ { \cdot + 1 } ) ) } \\ & { \qquad \leq K ( \omega ) d ( X _ { \cdot \cdot \cdot } , X _ { \cdot } ) \} \subseteq \Omega } \\ & { \qquad \quad p ( \Omega ^ { ' } ) = 1 } \end{array}
$$

因此,

在 MPSGO中由MO和SO合成的映射 $T$ 是一个随机压缩映射。

引理 $\pmb { 2 } ^ { [ 1 7 ] }$ 设 $\Omega$ 是一个巴拿赫空间。若 $T : \Omega \to \Omega$ 是一个压缩映射，则 $T$ 在 $\Omega$ 内有唯一不动点。

定理3设 $T : M \times \Omega  \Omega$ 是 MPSGO中的压缩映射，那么，在 $\Omega$ 中 $T$ 有唯一不动点，也即，MPSGO是渐近收敛。

# 2.6 SGO与MPSGO的多样性分析

本文选取不同类型的函数F2、F4、F6和F8来检验算法的多样性。测量多样性的方法很多，如基于所有个体平均汉明距离的方法；所有个体的位置与群体中心的距离方法以及熵方法[18]。为了简单直观分析 SGO 和 MPSGO 算法的多样性，本文采用基于平均距离来衡量群体多样性。为了公平比较 SGO 和MPSGO 算法的多样性，两个个体之间的距离被归一化到[0,1]内。群体多样性定义如下：

定义4 群体中个体 ${ \boldsymbol { p } } _ { i }$ 与 ${ { p } _ { l } }$ 之间的距离为

$$
H \left( p _ { i } , p _ { i } \right) = \sum _ { j = 1 } ^ { D } \lvert p _ { i , j } - p _ { l , j } \rvert
$$

定义5群体中个体 ${ \boldsymbol { p } } _ { i }$ 与 ${ { p } _ { l } }$ 之间的归一化距离为

$$
\begin{array} { r } { H ^ { ^ { * } } ( \boldsymbol { p } _ { i } , \boldsymbol { p } _ { i } ) = H ( \boldsymbol { p } _ { i } , \boldsymbol { p } _ { i } ) / \operatorname* { m a x } \{ H ( \boldsymbol { p } _ { m } , \boldsymbol { p } _ { n } ) ,  } \\ { m = 1 , 2 , . . . N - 1 ; n = m + 1 , m + 2 , . . . , N \} } \end{array}
$$

定义6每次群体迭代中的平均距离为

$$
\overset { \^ } { H } \left( T \right) = \frac { 2 \sum _ { i = 1 } ^ { N - 1 } \sum _ { j = i + 1 } ^ { N } H ^ { ^ { * } } \left( p _ { i } , p _ { i } \right) } { N ^ { * } \left( N - 1 \right) }
$$

在本次测试中，SGO和MPSGO算法的参数设置如下：两算法的种群大小均为50，以算法最大迭代次数作为终止条件，算法代数为4000，函数维数为50，两种算法的多样性变化如图1所示。

![](images/279a548ed2392a6afde13499302d38028a0d775b6a20dc4b3ce139ef188eedc2.jpg)  
图1SGO和MPSGO的多样性变化图

图1结果显示，对选取的四个函数，MPSGO的多样性优于基本SGO。F2函数图像表明在初始化阶段，MPSGO的多样性差于基本SGO,但在中后期,MPSGO的多样性优于基本 SGO;F8 函数图像显示，在迭代1200\~1500代时，MPSGO的多样性差于基本SGO，但在1500 代后，MPSGO的多样性明显优于基本SGO。F4和F6函数图像表明，MPSGO的多样性始终优于基本 SGO 算法。

# 2.7改进算法流程

由以上分析，MPSGO算法流程如下图2所示：

![](images/7952ed66e198cf7fefc84dccce89b3789c6d7416b625305eb334a04a98d06598.jpg)  
图2MPSGO算法流程

# 3 仿真实验

为验证MPSGO算法的性能，本文对8个基准函数进行仿真实验，结果与 NSTLBO 算法[19]、ETLBO 算法[20]、PSOFDR算法[2I]、SGO 算法进行比较。

# 3.1参数设置

本文所用的8个函数如表1所示。F1、F2是单峰函数，F3、F4为多峰函数，F5\~F8是旋转函数。所有算法的群体规模为50，以函数值作为算法适应度值，最大函数评价次数(maxFES $\scriptstyle \sum = 5 0 0 0 ^ { * } \mathrm { D } ^ { \prime }$ 作为算法的停止准则， $D$ 为变量的维数。子群数量为10， $_ { c = 0 . 2 }$ 。

其他四种算法参数均来自相对应的参考文献，相关参数如下所示：

PSOFDR 算 法[21]： $\omega \operatorname* { m i n } = 0 . 4 , \omega \operatorname* { m a x } = 0 . 9 , \varphi 1 = 1 , \varphi 2 = 1 ,$ $\varphi 3 = 2 ;$ NSTLBO 算法[19]:N（neighborhood Size） $^ { = 3 }$ ETLBO 算法[20]:elite siz ${ \boldsymbol { \cdot } } = 2$ ，SGO 算法[8]:： $\scriptstyle \mathtt { c } = 0 . 2$ （204

表1测试函数  

<html><body><table><tr><td>问题</td><td>函数</td><td>变量范围</td><td>最优值</td></tr><tr><td>F1</td><td>Zakharov</td><td>[-10,10]</td><td>0</td></tr><tr><td>F2</td><td>Rosenbrock</td><td>[-2.048,2.048]</td><td>0</td></tr><tr><td>F3</td><td>Ackley</td><td>[-32.768,32.768]</td><td>0</td></tr><tr><td>F4</td><td>Schwefel</td><td>[-500,500]</td><td>0</td></tr><tr><td>F5</td><td>Rotated Zakharov</td><td>[-10,10]</td><td>0</td></tr><tr><td>F6</td><td>Rotated Rosenbrock</td><td>[-2.048,2.048]</td><td>0</td></tr><tr><td>F7</td><td>Rotated Ackley</td><td>[-32.768,32.768]</td><td>0</td></tr><tr><td>F8</td><td>Rotated Schwefel</td><td>[-500,500]</td><td>0</td></tr></table></body></html>

# 3.2 实验结果及分析

为验证算法解决不同维优化问题的能力，分别对30、50维函数进行实验。每种算法独立运行30次，对其各种算法所得到的最优解（best）、平均值（mean）、标准差（std）进行统计分析，实验结果如表2、3所示。表2、3中粗体为最好结果。

从表2的结果可以看出，30维函数条件下，对于函数F1、F3、F5、F7，MPSGO与SGO的性能相当，且三项性能都优于其他三种算法；对函数F2、F4、F8，MPSGO的性能优于其他算法；对函数F2、F6，NSTLBO的标准差优于其他四种算法；五种算法在函数F3的标准差相同。统计结果表明，MPSGO的平均性能优于其他算法。

从表3的结果可以看出，在50维函数实验中，对函数F1、F3、F5和F7，MPSGO与SGO的性能相当，且三项性能都优于其他三种算法；对函数F4中，MPSGO 三种性能优于其他算法；在F6、F8 实验结果中，MPSGO 的平均值优于其他算法；在F8函数实验中，NSTLBO算法的标准差优于其他四种算法；在对F3、F7函数实验中，NSTLBO、MPSGO、SGO三种算法标准差相同；在函数F2实验结果中，PSOFDR的最优解、平均值优于其他算法。由表2、3统计分析可看出，MPSGO的平均性能优于其他算法，尤其在高维度问题下，其优势较明显。

为了更直观地显示各算法平均适应度的变化过程，本文给出了不同算法对50维函数实验的优化过程中平均适应度变化，如图3所示。图3显示，对函数F3、F4、F6、F7、F8，MPSGO算法的收敛速度快于其他算法；MPSGO在对函数F2 实验前期收敛速度快于其他算法，后期收敛的精度差于PSOFDR，但比SGO 算法效果好。虽然在个别函数优化实验中，MPSGO的收敛速度不是最快，但对于复杂函数，特别是旋转函数，MPSGO表现出了良好的性能。

表230维函数测试结果  

<html><body><table><tr><td></td><td>函数 性能指标</td><td>PSOFDR</td><td>NSTLBO</td><td>ETLBO</td><td>SGO</td><td>MPSGO</td></tr><tr><td rowspan="3">F1</td><td>best</td><td>1.99E-09</td><td>3.30E-73</td><td>1.93E-36</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>mean</td><td>1.57E-08</td><td>1.03E-70</td><td>2.00E-34</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>std</td><td>1.86E-08</td><td>1.65E-70</td><td>4.41E-34</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td rowspan="3">F2</td><td>best</td><td>1.19E+01</td><td>2.40E+01</td><td>1.55E+01</td><td>2.79E+01</td><td>1.29E+01</td></tr><tr><td>mean</td><td>1.41E+01</td><td>2.45E+01</td><td>1.72E+01</td><td>2.83E+01</td><td>1.34E+01</td></tr><tr><td>std</td><td>2.41E+00</td><td>5.07E-01</td><td>1.19E+00</td><td>2.49E-01</td><td>4.26E-01</td></tr><tr><td rowspan="3">F3</td><td>best</td><td>7.11E-15</td><td>3.55E-15</td><td>3.55E-15</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>mean</td><td>7.11E-15</td><td>3.55E-15</td><td>3.55E-15</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>std</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td rowspan="3">F4</td><td>best</td><td>2.82E+03</td><td>3.07E+03</td><td>3.59E+03</td><td>4.97E+03</td><td>1.78E+03</td></tr><tr><td>mean</td><td>3.36E+03</td><td>4.43E+03</td><td>4.02E+03</td><td>5.61E+03</td><td>2.40E+03</td></tr><tr><td>std</td><td>4.71E+02</td><td>8.11E+02</td><td>4.83E+02</td><td>6.06E+02</td><td>4.35E+02</td></tr><tr><td rowspan="3">F5</td><td>best</td><td>6.12E-10</td><td>2.60E-75</td><td>1.84E-38</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>mean</td><td>5.55E-09</td><td>5.94E-71</td><td>7.80E-36</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>std</td><td>7.19E-09</td><td>1.31E-70</td><td>1.04E-35</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td rowspan="3">F6</td><td>best</td><td>2.45E+01</td><td>3.13E+01</td><td>1.62E+01</td><td>1.29E+02</td><td>1.17E+01</td></tr><tr><td>mean</td><td>6.83E+01</td><td>5.69E+01</td><td>3.63E+01</td><td>4.16E+02</td><td>3.70E+01</td></tr><tr><td>std</td><td>5.46E+01</td><td>2.28E+01</td><td>2.44E+01</td><td>2.29E+02</td><td>2.58E+01</td></tr><tr><td rowspan="3">F7</td><td>best</td><td>7.11E-15</td><td>3.55E-15</td><td>3.55E-15</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>mean</td><td>1.86E-01</td><td>3.55E-15</td><td>3.55E-15</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>std</td><td>4.16E-01</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td rowspan="3">F8</td><td>best</td><td>1.84E+03</td><td>4.15E+03</td><td>3.16E+03</td><td>5.27E+03</td><td>2.01E+03</td></tr><tr><td>mean</td><td>2.68E+03</td><td>4.92E+03</td><td>3.88E+03</td><td>6.47E+03</td><td>2.48E+03</td></tr><tr><td>std</td><td>7.38E+02</td><td>7.98E+02</td><td>4.69E+02</td><td>1.09E+03</td><td>4.33E+02</td></tr></table></body></html>

表350维函数测试结果  

<html><body><table><tr><td>函数 性能指标</td><td></td><td>PSOFDR</td><td>NSTLBO</td><td>ETLBO</td><td>SGO</td><td>MPSGO</td></tr><tr><td rowspan="3">F1</td><td>best</td><td>5.28E-04</td><td>1.08E-70</td><td>2.33E-31</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>mean</td><td>2.64E-02</td><td>4.27E-68</td><td>2.96E-30</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>std</td><td>3.29E-02</td><td>6.14E-68</td><td>3.86E-30</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td rowspan="3">F2</td><td>best</td><td>2.67E+01</td><td>4.33E+01</td><td>3.63E+01</td><td>4.80E+01</td><td>2.75E+01</td></tr><tr><td>mean</td><td>2.90E+01</td><td>4.38E+01</td><td>3.73E+01</td><td>4.85E+01</td><td>2.95E+01</td></tr><tr><td>std</td><td>1.39E+00</td><td>3.33E-01</td><td>6.11E-01</td><td>3.46E-01</td><td>1.29E+00</td></tr><tr><td rowspan="3">F3</td><td>best</td><td>2.13E-14</td><td>3.55E-15</td><td>3.55E-15</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>mean</td><td>3.29E-01</td><td>3.55E-15</td><td>3.55E-15</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>std</td><td>7.36E-01</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td rowspan="3">F4</td><td>best</td><td>4.46E+03</td><td>7.29E+03</td><td>6.40E+03</td><td>9.14E+03</td><td>4.05E+03</td></tr><tr><td>mean</td><td>5.89E+03</td><td>8.01E+03</td><td>7.98E+03</td><td>1.01E+04</td><td>4.67E+03</td></tr><tr><td>std</td><td>1.03E+03</td><td>7.00E+02</td><td>1.07E+03</td><td>7.00E+02</td><td>5.94E+02</td></tr><tr><td rowspan="3">F5</td><td>best</td><td>2.34E-03</td><td>3.75E-74</td><td>9.18E-34</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>mean</td><td>1.40E-02</td><td>4.82E-68</td><td>6.95E-31</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>std</td><td>1.33E-02</td><td>9.86E-68</td><td>1.46E-30</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td rowspan="3">F6</td><td>best</td><td>5.12E+01</td><td>3.83E+01</td><td>4.93E+01</td><td>6.79E+02</td><td>2.23E+01</td></tr><tr><td>mean</td><td>7.26E+01</td><td>1.07E+02</td><td>8.75E+01</td><td>1.66E+03</td><td>5.68E+01</td></tr><tr><td>std</td><td>1.94E+01</td><td>4.83E+01</td><td>2.14E+01</td><td>1.24E+03</td><td>3.06E+01</td></tr><tr><td rowspan="3">F7</td><td>best</td><td>1.03E+00</td><td>3.55E-15</td><td>3.55E-15</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>mean</td><td>1.32E+00</td><td>3.55E-15</td><td>4.26E-15</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>std</td><td>2.07E-01</td><td>0.00E+00</td><td>1.59E-15</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td rowspan="3">F8</td><td>best</td><td>5.68E+03</td><td>8.96E+03</td><td>8.38E+03</td><td>1.16E+04</td><td>3.94E+03</td></tr><tr><td>mean</td><td>6.84E+03</td><td>9.81E+03</td><td>9.61E+03</td><td>1.26E+04</td><td>5.26E+03</td></tr><tr><td>std</td><td>1.20E+03</td><td>8.15E+02</td><td>9.43E+02</td><td>8.88E+02</td><td>8.25E+02</td></tr></table></body></html>

为了进一步证明MPSGO算法与其他算法的差异，采用t-test 方法对各种算法的结果进行测试。本文采用双边检验，显著水平为0.05。在30、50维条件下，MPSGO算法对于其他算法的t值和p值如表4、5所示。表4、5中，‘B，‘S'，‘W分别表示MPSGO 算法性能优于、等于、劣于其他算法的数量。MPSGO与其他算法之间的较好结果以粗体显示。由表4、5果可以看出，在采用双边检验，显著水平0.05情况下，MPSGO算法性能优于大多数算法，解可以被接受。

![](images/ccd6661a6ad86e7aa6eda8070f75b64dda33e4fb3c67330a3cc456eba6e3f541.jpg)  
图38个函数平均适应度值变化图

# 4 结束语

本文针对SGO算法收敛精度低及群体多样性易丢失问题，提出了基于多子群的社会群体算法（MPSGO)。通过引入多子群、量子学习及子群信息交换方法，提高了SGO算法的整体性能。通过与SGO及其他三种算法比较实验，验证了改进方法的有效性。

表4各算法对8个基准函数为30维的t-test结果  

<html><body><table><tr><td>函数</td><td>指标</td><td>PSOFDR</td><td>NSTLBO</td><td>ETLBO</td><td>SGO</td></tr><tr><td rowspan="2">F1</td><td>T</td><td>4.6258</td><td>3.4100</td><td>2.4821</td><td>0.0000</td></tr><tr><td>P</td><td>0.0000</td><td>0.0012</td><td>0.0156</td><td>0.0000</td></tr><tr><td rowspan="2">F2</td><td>T</td><td>1.6905</td><td>92.2834</td><td>16.4651</td><td>165.6072</td></tr><tr><td>P</td><td>0.0963</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td rowspan="2">F3</td><td>T</td><td>27.5191</td><td>13.7595</td><td>13.7595</td><td>0.0000</td></tr><tr><td>P</td><td>0.0000</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td rowspan="2">F4</td><td>T</td><td>8.1838</td><td>12.0438</td><td>13.6443</td><td>23.5496</td></tr><tr><td>P</td><td>0.0000</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td rowspan="2">F5</td><td>T</td><td>4.2326</td><td>2.4899</td><td>4.1208</td><td>0.0000</td></tr><tr><td>P</td><td>0.0001</td><td>0.0157</td><td>0.0001</td><td>0.0000</td></tr><tr><td rowspan="2">F6</td><td>T</td><td>2.8442</td><td>3.1724</td><td>-0.1087</td><td>9.0180</td></tr><tr><td>P</td><td>0.0061</td><td>0.0024</td><td>0.9141</td><td>0.0000</td></tr><tr><td rowspan="2">F7</td><td>T</td><td>2.4495</td><td>13.7595</td><td>13.7595</td><td>0.0000</td></tr><tr><td>P</td><td>0.0174</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td rowspan="2">F8</td><td>T</td><td>1.2860</td><td>14.7259</td><td>12.0255</td><td>18.5730</td></tr><tr><td>P</td><td>0.2053</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td rowspan="3"></td><td>B</td><td>6</td><td>8</td><td>7</td><td>4</td></tr><tr><td>S</td><td>2</td><td>0</td><td>1</td><td>4</td></tr><tr><td>W</td><td>0</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

表5各算法对8个基准函数为50维的t-test结果  

<html><body><table><tr><td>函数</td><td>指标</td><td>PSOFDR</td><td>NSTLBO</td><td>ETLBO</td><td>SGO</td></tr><tr><td rowspan="2">F1</td><td>T</td><td>5.6831</td><td>4.9159</td><td>5.4326</td><td>0.0000</td></tr><tr><td>P</td><td>0.0000</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td rowspan="2">F2</td><td>T</td><td>-1.9850</td><td>75.6295</td><td>38.6910</td><td>100.3924</td></tr><tr><td>P</td><td>0.0519</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td rowspan="2">F3</td><td>T</td><td>3.1623</td><td>13.7595</td><td>13.7595</td><td>0.0000</td></tr><tr><td>P</td><td>0.0025</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td rowspan="2">F4</td><td>T</td><td>7.2875</td><td>25.7462</td><td>19.1339</td><td>42.1701</td></tr><tr><td>P</td><td>0.0000</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td rowspan="2">F5</td><td>T</td><td>7.4309</td><td>3.4557</td><td>3.3732</td><td>0.0000</td></tr><tr><td>P</td><td>0.0000</td><td>0.0010</td><td>0.0013</td><td>0.0000</td></tr><tr><td rowspan="2">F6</td><td>T</td><td>3.0693</td><td>6.2383</td><td>5.8008</td><td>9.1123</td></tr><tr><td>P</td><td>0.0033</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td rowspan="2">F7</td><td>T</td><td>45.0210</td><td>13.7595</td><td>18.9741</td><td>0.0000</td></tr><tr><td>P</td><td>0.0000</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td rowspan="2">F8</td><td>T</td><td>7.6633</td><td>27.7548</td><td>24.5591</td><td>42.6334</td></tr><tr><td>P</td><td>0.0000</td><td>0.0000</td><td>0.0000</td><td>0.0000</td></tr><tr><td></td><td>B</td><td>7</td><td>8</td><td>8</td><td>4</td></tr><tr><td></td><td>S</td><td>1</td><td>0</td><td>0</td><td>4</td></tr><tr><td></td><td>W</td><td>0</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

# 参考文献：

[1]GiovanniLD,PezzellaF.An improved genetic algorithm for the distributed and flexible Job-Shop scheduling problem [J].European Journal of Operational Research,2010,200 (2):395-408.   
[2]AlrashidiMR,El-Hawary ME.A survey of particle swarm optimization applications in electric power systems [M].[S.1.] :IEEE Press,20o9:913- 918.   
[3]Das S,Suganthan PN.Differential evolution: a survey of the state-of-theart[J].IEEE Trans on Evolutionary Computation,2011,15(1):4-31.

[4]Mallipeddi R,Mallipeddi S,Suganthan P N.Ensemble strategies with adaptive evolutionary programming[J].Information Sciences,201o,180 (9): 1571-1581.

[5]Rao RV, Savsani VJ,VakhariaDP.Teaching-learning-based optimization: a novel method for constrained mechanical design optimization problems [J]. Computer-Aided Design,2011,43 (3): 303-315.   
[6]Rao R V,RaiDP,Balic J.Multi-objective optimization of machining and micro-machining processes using non-dominated sorting teaching-learningbased optimization algorithm[J]. Journal ofIntelligent Manufacturing,2016: 1-23.   
[7]Rao R V,Patel V.An elitist teaching-learning-based optimization algorithm for solving complex constrained optimization problems [J]. International Journal ofIndustrial Engineering Computations,2012,3(4):535-560.   
[8]Satapathy S, Naik A. Social group optimization (SGO): a new population evolutionaryoptimization technique [J]. Complex & Intelligent Systems, 2016: 1-31.   
[9]Naik A, Satapathy S C,Ashour A S,et al.Social group optimization for global optimization of multimodal functions and data clustering problems [J].Neural Computing & Applications,2016:1-17.   
[10]廖锋，高兴宝．多群体差分演化算法及其应用[J].计算机仿真，2011, 28 (01): 230-233   
[11] Luan L,Wang Z, Liu S.Progress of grover quantum search algorithm [J]. Energy Procedia,2012,16 (16): 1701-1706.   
[12] Meyer D A. Quantum learning seminar lecture 1: introduction [EB/OL]. (2002). htp://math. ucsd.edu/\~dmeyer/.   
[13] Meyer D A.Quantum learning seminar lecture 2:grover's algorithm [EB/OL]. (2002). http://math. ucsd. edu/\~dmeyer/.   
[14] Meyer D A. Quantum learning seminar lecture 3: single query learning [EB/OL]. (2002). htp://math. ucsd. edu/\~dmeyer/.   
[15]张亮．采用量子进化算法学习的贝叶斯网络及其应用研究[D].长沙： 湖南大学,2011.   
[16] Zou F, Chen D,Lu R,et al. Hierarchical multi-swarm cooperative teachinglearning-based optimization for global optimization [J]. Soft Computing, 2016: 1-22.   
[17]李敏强.遗传算法的基本理论与应用[M].北京：科学出版社,2002.   
[18] Chen DB,Zhao C X.Particle swarm optimization with adaptive population size and its application [J]. Applied Soft Computing,2009,9(1): 39-48.   
[19] Wang L,Zou F,Hei X,et al.An improved teaching-learning-based optimization with neighborhood search for applications of ANN[J]. Neurocomputing,2014,143 (16): 231-247.   
[20] Rao R V,Patel V.An elitist teaching-learning-based optimization algorithm for solving complex constrained optimization problems [J]. International Journal ofIndustrial Engineering Computations,2012,3(4):535-560.   
[21] Peram T,Veeramachaneni K,Mohan C K.Fitness-distance-ratio based particle swarm optimization [C]// Proc of IEEE Swarm Intelligence Symposium. 2012: 174-181.