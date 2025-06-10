# 移动群智感知中的空间任务分配机制

邢倩，孙学梅，苑春苗(天津工业大学 计算机科学与软件学院，天津 300387)

摘要：在移动群智感知的空间任务分配问题中用户与任务的空间距离直接影响完成任务所需的成本，而现有的研究在这方面却考虑不足，因此以最小化感知成本为目标设计了移动群智感知中的空间任务分配机制。首先，以感知成本最小为目标，基于遗传算法和贪心算法设计了一种高效的任务分配方法；其次，针对用户感知质量的随机性，基于用户的历史感知情况和当前任务的执行情况设计了用户感知质量的更新机制。为验证所提机制的效果，通过仿真实验与两种基准的任务分配方法作比较。实验结果表明，所提机制在感知总成本和用户执行任务所移动的总距离等方面均有更好的效果，因此该空间任务分配机制具有很好的应用前景。

关键词：移动群智感知；空间任务；任务分配；成本最小 中图分类号：TP393.06 doi:10.3969/j.issn.1001-3695.2018.09.0644

Assignment mechanism for spatial tasks in mobile crowd sensing

Xing Qian, Sun Xuemei, Yuan Chunmiao (SchoolofComputer Science &Software Engineering,Tianjin Polytechnic University,Tianjin 3Oooo,China）

Abstract:For the allcationof spatialtasks inmobile crowd sensing,thespatial distancebetween users andtasks directly affects thecostrequired tocompletethetasks,while theexistingresearchabout this isconsidered inadequate.Inorderto minimize cost,the paper proposed a spatial task allocation mechanism.Firstly,basedon genetic algorithm and greedy algorithm,it designedan eficienttask allcation method to minimize thecost required tocomplete the tasks.Secondly, considering therandomnessof user sensing quality,it designed a mechanismof user sensingqualityupdating based on the historical qualityandthequalityof thecurrenttask.To verifytheeffectiveness of the proposed mechanism,itconducted simulations compared with the twobenchmarks.Theresults show that for spatial task allcationthe proposed mechanism has beterresults in terms of total costandspatial distance thattheuser needs to move toperform thetask.Therefore,the allocation mechanism proposed has better foreground.

Key words:mobile crowd sensing; spatial tasks; task allocation; minimize cost

# 0 引言

如今，智能手机逐渐成为移动通信设备的主流，这些智能手机通常配有功能强大的传感器[1]，如GPS，相机和数字式罗盘等。在此背景下，借助智能手机收集感知数据的新兴感知模式—移动群智感知(mobile crowd sensing，MCS)正逐渐成为学术界研究的热点课题[2]。MCS通常由三部分组成：任务所有者、云端平台和感知用户[3]，其中任务所有者将感知任务提交到云端平台；云端平台通过智能分配算法将感知任务分配给感知用户；感知用户按要求完成感知任务并上传数据。如何选择合适的感知用户是MCS的关键问题之一，合理的任务分配方案是感知任务高效执行的前提[4]。

目前，MCS的应用中大部分都是空间任务，如交通规划[5]、环境监测[6和公共安全[7]等，这对MCS 的任务分配方法提出了更高的要求。目前，有关MCS中任务分配问题的研究有很多，但是MCS的发展处于初期阶段，很多方法和理论仍需完善。文献[8]考虑到感知用户收集数据质量的不确定性，设计出BLISS任务分配框架不断重组感知用户集合。文献[9]考虑基于连续时间窗口的任务分配问题，并利用动态规划算法解决该问题。文献[10]将任务分配问题抽象成整数规划问题，然后采用贪心技术实现用户与任务之间的高效匹配。

但是上述研究都不适用于空间任务的分配问题。文献[11]将空间任务的分配问题描述成多条件的背包问题，并使用贪心策略解决该问题。文献[12]针对具有时间限制和位置限制的任务提出一种多任务的分配框架，并引入排队机制、信誉机制和委托人机制以得到高效的任务分配方案。在空间任务的分配问题中，用户到任务的空间距离直接影响着感知成本，而文献[11,12]所提出的任务分配方法均是以数据收益为优化目标，并未考虑用户与任务的空间距离对感知成本的影响。文献[13]主要针对多任务分发问题提出了MultiTasker方法，目标是使用户完成任务所移动的总距离最短，并且完成任务的用户数最少以优化用户资源，但是该方法没有考虑任务对感知数据质量的要求。

本文在总结现有任务分配方法的基础上，针对空间任务的分配问题，以感知成本最小为优化目标，设计了一种空间任务的分配机制。通过仿真实验将本文的分配算法GGA-TA与两种基准的分配方法做比较，并对实验结果进行了分析。

# 1 问题模型

假设多个任务发布者在云端平台发布了不同地点的 $N$ 个感知任务，用集合 $T = \{ 1 , 2 . . . N \}$ 表示。 $L _ { i } = \{ l _ { i , 1 } , l _ { i , 2 } \}$ 表示任务 $i$ 的空间位置，其中 $l _ { i , 1 }$ 和 $l _ { i , 2 }$ 分别表示2D空间内一点的横纵坐标。

在MCS中，感知任务除了具有感知地点的限制以外，对感知数据的质量也有一定的要求，任务所有者通常要求用户采集到的感知数据质量不低于某临界值[14。将感知数据质量定义为合格数据的总量，同时满足清晰度要求、感知时间要求和感知地点要求的数据为合格数据。任务 $i$ 的感知数据质量要求用 $q ^ { i }$ 表示。假设平台中共有 $M$ 个注册用户，这些用户等待平台为其分配感知任务，用集合 $U = \{ 1 , 2 . . . M \}$ 表示用户集合。MCS中的感知用户不再是专业人员而是普通群众，所以用户感知质量的高低各不相同。定义用户的感知质量为执行一次任务所采集的合格数据的总量， $\lambda _ { i }$ 表示用户 $i$ 的感知质量； $f _ { i }$ 表示平台需要支付给用户 $i$ 的固定激励，由于用户执行感知任务需要消耗设备电量，承担泄露个人隐私的风险，所以用户 $i$ 每执行一个感知任务就需要平台支付一次固定激励 $f _ { i }$ ·$p _ { i }$ 表示用户 $i$ 移动单位距离的成本；受设备能量的限制，用户 $i$ 能够执行的任务个数是有限的[15]，用 $n _ { i }$ 表示用户i的最大执行能力，即本次任务分配中最多能执行的任务数。任务发布者发布空间任务后，平台获取任务信息和用户信息并根据智能分配算法合理的分配任务。为降低感知成本，每个任务由一个感知用户执行，但用户的感知质量必须大于或等于任务的感知质量要求以保证任务被成功执行，并且每个用户执行的任务数不得超过该用户的最大执行能力。

在MCS中，云端平台往往希望感知成本达到最小，这里所说的感知成本主要包括支付给被选用户的固定激励和动态激励(移动单位距离的动态成本与移动总距离的乘积)。本文目标是站在平台的角度设计一种空间任务的分配机制，同时考虑任务的质量要求、用户的感知质量、最大执行能力和用户与任务的空间距离等因素，力求在满足任务质量要求的同时最小化感知所需的成本。本文目标函数如式(1)所示。

$$
\begin{array} { r } { \mathrm { m i n } ~ z = \sum _ { k = 1 } ^ { M } \sum _ { i = 0 } ^ { N } \sum _ { j = 0 } ^ { N } p _ { _ k } X _ { i , j , k } d _ { i , j } + \sum _ { k = 1 } ^ { M } \sum _ { i = 0 } ^ { N } \sum _ { j = 0 } ^ { N } f _ { _ k } X _ { i , j , k } d _ { i , j } } \end{array}
$$

其中： $X _ { i , j , k }$ 为二进制变量，表示用户 $k$ 是否执行空间任务 $i$ 后前往执行任务 $j$ ，如果是， $X _ { i , j , k }$ 的值为1，反之为0。为表述方便，本文假设用户从同一地点出发，完成所分配的任务后返回出发点。加入虚拟任务点0作为用户的出发点，设$T ^ { \prime } { = } \{ 1 , 2 , \cdots , N \}$ 。式(1)中第一部分表示支付给被选用户的动态激励。 $d _ { i , j }$ 表示任务 $i$ 和任务 $j$ 之间的欧几里德距离。式(1)第二部分表示平台支付给用户的固定激励。

目标式(1)需要遵循以下几个限制条件：

配方法(greedy and genetic algorithm for tasks allocation,GGA-TA)；b)用户感知质量的更新机制。

# 2.1空间任务分配方法GGA-TA

移动群智感知中的空间任务分配问题属于典型的NP 难问题，遗传算法是根据自然界中生物进化规律衍化而来的一种搜索启发式算法，可以用来解决复杂的优化问题。因此使用遗传算法解决上述空间任务分配问题。但是移动群智感知中的任务分配问题规模较大，传统的遗传算法很难得到满意的分配方案，所以设计了遗传算法和贪心算法混合的空间任务分配方法GGA-TA。

1)染色体编码及适应度函数

GGA-TA采用自然数编码方式，0,1,2...M表示 $M$ 个用户，用户所在的位置下标对应任务。如图1所示，假设平台中有8个任务，3个用户，图1染色体表示用户1执行任务1、4、6；用户2执行任务3、5、8；用户3执行任务2、7。

1 3 2 1 2 1 3 2 $$ 染色体   
1 2 3 4 5 6 7 8 →下标

上述编码方式产生的分配方案能够保证每个任务被执行一次，但不能保证分配给每个任务的用户的感知质量符合任务的质量要求，也不能保证分配给用户的任务数量在其最大执行能力的范围内。为了处理式(2)(3)所示的约束条件，GGA-TA 方法在计算染色体评价值时引入惩罚系数 $p _ { _ w }$ ，染色体的评价值的具体计算过程如算法1所示。为提高算法的效率，GGA-TA方法在基本遗传算法的基础上加入贪心算法用于规划单个感知用户的路径，用户首先完成距离当前位置最近的任务，如算法1中步骤c）d）所示。

算法1计算染色体的评价值

输入：染色体 $c$ ， $Q = ( q ^ { 1 } , q ^ { 2 } . . . q ^ { N } )$ ， $\boldsymbol { \Gamma } = ( \lambda _ { 1 } , \lambda _ { 2 } . . . \lambda _ { M } )$ ， $\boldsymbol { F } = ( f _ { \mathrm { \ell } } , f _ { \mathrm { \ell } } . . . f _ { \mathrm { \ell } _ { M } } )$ ，$P = ( p _ { 1 } , p _ { 2 } . . . p _ { M } ) \ , N = ( n _ { 1 } , n _ { 2 } . . . n _ { M } ) \ , D e s = ( d e s _ { 1 } , d e s _ { 2 } . . . d e s _ { M } ) \ ,$

输出： $E$ 。

a)确定染色体 $c$ 中被选用户的集合 $S = \{ 1 , 2 . . . s \}$ ，令 $k = 1$ 、 $E = 0 .$ 0

b)如果 $k > s$ 跳转到步骤5；否则根据染色体 $c$ 确定用户 $k$ 要执行的任务集合 $R _ { k } = \{ 1 , 2 . . . r \}$ ，令 $\boldsymbol { E } = \boldsymbol { E } + \boldsymbol { f } _ { \mathrm { \scriptsize ~ k } } \times \vert \boldsymbol { R } _ { \boldsymbol { k } } \vert$ ，如果 $R _ { k }$ 中元素的个数IR|大于用户k的执行能力nk，令E=E+P。

$$
\lambda _ { \scriptscriptstyle k } \geq y _ { \scriptscriptstyle i , k } q ^ { i } u _ { \scriptscriptstyle k } \in U t _ { i } \in T
$$

$$
\textstyle \sum _ { i = 1 } ^ { N } y _ { _ { i , k } } \leq n _ { k } \quad u _ { _ { k } } \in U
$$

$$
\textstyle \sum _ { k = 1 } ^ { M } y _ { _ { i , k } } = 1 \ t _ { i } \in T
$$

$y _ { _ { i , k } }$ 为二进制变量，表示用户 $k$ 是否执行了任务 $i$ ，如果是， $y _ { _ { i , k } }$ 的值为1，反之为0。约束条件式(2)确保执行每个任务的用户的感知质量都满足该任务的质量要求。约束条件式(3)确保每个用户执行的任务数不超过用户的最大执行能力。约束条件式(4)表示每个任务i被执行一次。

# 2 空间任务分配机制

为解决第二部分所提出的空间任务的分配问题，设计了一种空间任务分配机制，主要内容包括两部分：a)以感知成本最小为目标，基于遗传算法和贪心算法混合的空间任务分c)如果 $R _ { k }$ 为空，令 $E = E +$ distance( ${ { k , d e s } _ { k } } ) \ast p _ { _ k }$ ， $k = k + 1$ 重复步骤b)；选择 $R _ { k }$ 中距离用户 $k$ 当前位置最近的任务 $j$ ，令$E = E +$ distance $( k , j ) * p _ { \mathbf { \Phi } _ { k } }$ ，并将任务 $j$ 的位置作为用户 $k$ 的当前位置。如果任务j的质量要求q'大于用户k的感知能力，令E=E+P。

d)从集合 $R _ { k }$ 中移除任务 $j$ ，跳转到步骤c)

e)输出染色体 $c$ 的评价值 $E$ 0

算法1中 $D e s = ( d e s _ { 1 } , d e s _ { 2 } . . . d e s _ { M } )$ 表示用户执行任务后返回的地点，其中 $d e s _ { k } = ( d e s _ { k , i } , d e s _ { k , j } )$ 。第一节中为表述方便假设所有用户从同一地点出发，执行任务后返回出发点，但从算法1中可知，GGA-TA算法在用户从不同地点出发，执行任务后不返回出点的情景中依然可行。

式(5)为计算染色体的适应度函数。其中 $E$ 表示某一染色体的评价值；fitness表示该染色体的适应度值； $\operatorname* { m a x } E$ 表示当前种群中的最大评价值； $\operatorname* { m i n } E$ 表示当前种群中的最小评价值。本文中染色体的评价值越小，fitmess 越大，染色体的适应度越高。

$$
\frac { 1 } { \mathrm { \it f i t } n e s s } = \frac { E - \operatorname* { m i n } E } { \operatorname* { m a x } E - \operatorname* { m i n } E }
$$

# 2）种群初始化

在遗传算法中初始种群极大的影响着算法结果的好坏，移动群智感知中空间任务分配问题的规模较大，因此随机产生初始种群不利于快速收敛到最优结果。GGA-TA算法中根据任务的质量要求生成初始种群如算法2所示。

算法2生成初始种群

输入： $N$ ， $\textbf { \textit { M } }$ ， $Q = ( q ^ { 1 } , q ^ { 2 } . . . q ^ { N } )$ ， $\boldsymbol { \Gamma } = ( \lambda _ { 1 } , \lambda _ { 2 } . . . \lambda _ { M } )$ ，Size。输出： $I N = \left[ \begin{array} { l } { c _ { 1 , 1 } c _ { 1 , 2 } . . . . c _ { i , N } } \\ { } \\ { . . . } \\ { c _ { S i z e , 1 } c _ { S i z e , 2 } . . . c _ { S i z e , N } } \end{array} \right] \mathrm { ~ o ~ }$ a)令 $k = 1$ ·b)如果 $k > S i z e$ ，输出 $I N$ ；否则令 $i = 1$ 。c)如果 $i > N$ ，令 $k = k + 1$ ，跳转到步骤a)。d)确定任务 $i$ 的质量要求 $q ^ { i }$ ，从用户集中查找所有感知质量大于或等于 $q ^ { i }$ 的用户子集 $S _ { i } = \{ 1 , 2 . . . s \}$ ，从用户子集中随机选择一个用户标志赋值给 $c _ { k , i }$ ，令 $\scriptstyle i = i + 1$ ，跳转到步骤c)。

# 3)选择算子

遗传算法中的选择算子用于将适应度高的优秀个体保存到下一代，将适应度低的个体淘汰。GGA-TA算法的选择算子将种群中的所有的个体按适应度值从大到小降序排列，保留种群中前一半数量的染色体，将后一半数量的染色体淘汰。

# 4)交叉算子

GGA-TA算法采用部分匹配交叉，即随机选择两个染色体并随机设置两个交叉点，交换两个染色体所设定的两个交叉点之间的染色体片段。

# 5)变异算子

变异算子是为了避免算法结果陷入局部最优，GGA-TA算法的变异算子采用单点变异，即随机产生选择变异点。变异点对应任务i，i的质量要求为 $q ^ { i }$ ，为加快算法的收敛速度，随机选择感知质量大于或等于 $\boldsymbol { q } ^ { i }$ 的用户赋值给变异点。

# 6)终止条件

GGA-TA算法达到最大进化代数时终止运行。GGA-TA具体内容如算法3所示。

算法3 GGA-TA算法

输入： $N$ ， $M$ ， $\lambda = ( q ^ { 1 } , q ^ { 2 } . . . q ^ { N } ) \ , \ \Gamma = ( \lambda _ { 1 } , \lambda _ { 2 } . . . . \lambda _ { M } ) \ , \ F = ( f _ { 1 } , f _ { 2 } . . . f _ { _ M } )$ $P = ( p _ { 1 } , p _ { 2 } . . . p _ { { \scriptscriptstyle M } } )$ ， $\pmb { N } = ( \boldsymbol { n } _ { 1 } , \boldsymbol { n } _ { 2 } . . . . \boldsymbol { n } _ { M } )$ ， $S i z e$ ， $G$ ， $\boldsymbol { p } _ { c }$ ， $\boldsymbol { p } _ { \boldsymbol { m } }$ 。

输出：。

a)令 $t = 1$ ，调用算法2生成初始种群 $I N _ { 1 }$ 。

b)令 $_ { t = t + 1 }$ ，如果 $t { > } G$ ,跳转到步骤6；否则调用算法1计算 $I N _ { t - 1 }$ 中所有染色体的评价值，根据式(5)计算 $I N _ { t - 1 }$ 中所有染色体的适应度。

c) $I N _ { t - 1 }$ 中的染色体按照适应度值降序排列，将前 $\left\lceil { \frac { S i z e } { 2 } } \right\rceil$ 个染色体赋 值给 $I N _ { t }$ ，令 $i = 1$ 。

d)如果 $i > \left\lceil { \frac { S i z e } { 2 } } \right\rceil - 1$ ，令 $j = 1$ 跳转到步骤e）；否则在 $I N _ { t }$ 前 $\left\lceil \frac { S i z e } { 2 } \right\rceil$ 个染色体中随机选择两个染色体 $I n _ { 1 }$ 和 $I n _ { 2 }$ ，生成[0,1]的随机数 $\boldsymbol { r }$ ，如果$r \geq c$ ，令 $I n _ { 3 } = I n _ { 1 }$ ， $I n _ { 2 } = I n _ { 4 }$ 。否则随机生成两个交叉点，交换 $I n _ { 1 } , I n _ { 2 }$ 在两个交叉点之间的部分染色体得到两个新的染色体 $I n _ { 3 }$ 和 $I n _ { 4 }$ 。

e)将 $I n _ { 3 }$ ， $I n _ { 4 }$ 加入到 $I N _ { t }$ 中，令 $i = i + 2$ ，跳转到步骤d)。

f)如果 $j > S i z e$ ，令 $t = t + 1$ ，跳转到步骤b);否则生成[0,1]的随机数 $r$ ，如果 $r \geq m$ ，令 $j = j + 1$ ，重复步骤e)；否则在 $I N _ { t }$ 中随机选择一个染色体 $C _ { l }$ ，随机生成一个变异点，变异点位置对应任务 $k$ ，从集合 $U$ 中选择感知质量大于或等于 $q ^ { k }$ 的用户标志，赋值给 $c _ { l , k }$ 令 $j = j + 1$ 。

g)将 $I N _ { t - 1 }$ 中适应度最小的染色体赋值给 $\Theta$ 。

GGA-TA算法的选择算子将适应度值高的一半数量的染色体保留如算法3中的步骤c)所示，然后以被保留的一半数量的染色体作为父代生成另一半数量的染色体共同构成一个种群如算法3中的步骤d)e)所示。对选择算子和交叉算子构成种群执行单点变异操作构成新一代种群，如算法3中的步骤f)所示。当GGA-TA算法达到终止条件时，输出最后一个种群中适应度最高的染色体作为任务分配方案。表1中对常用的参数进行描述。

表1常用参数Table1Common parameters  

<html><body><table><tr><td>N</td><td>任务数量</td></tr><tr><td>M</td><td>用户数量</td></tr><tr><td>Q</td><td>Q=(q，q.q)，q表示任务i的质量要求</td></tr><tr><td>「</td><td>┌=(,)，表示用户i的感知质量</td></tr><tr><td>F</td><td>F=(f,f..fm），f;表示用户i的固定激励</td></tr><tr><td>P</td><td>P=(p,PPM），Pi表示用户i的动态成本</td></tr><tr><td>Ei</td><td>染色体Ci的评价值</td></tr><tr><td>Size</td><td>种群规模</td></tr><tr><td>G</td><td>最大迭代次数</td></tr><tr><td>Pw</td><td>惩罚系数</td></tr><tr><td>Pc</td><td>交叉概率</td></tr><tr><td>Pm</td><td>变异概率</td></tr><tr><td></td><td>任务分配方案</td></tr></table></body></html>

# 2.2用户感知质量的更新机制

MCS中感知用户的非专业性造成用户每次完成任务的感知质量是不可预知的随机值，但是可以通过总结用户历史的感知情况得到用户感知质量的估计值。为得到更接近用户的实际情况的估计值，本文加入用户感知质量的更新机制，每执行完一个任务后，根据用户上传的感知数据更新用户的感知质量，为后续的任务分配做准备。用户感知质量的更新公式如式(6)所示。其中 $\lambda _ { k } ^ { \prime }$ 表示感知用户 $u _ { k }$ 执行完 $\boldsymbol { r }$ 个任务后的感知质量。 $A _ { k } ^ { ^ j }$ 表示用户 $u _ { k }$ 执行任务 $t _ { j }$ 时上传的合格数据的总量。 $\alpha$ 为常量，通过调整 $\alpha$ 的大小，可以调整用户执行当前任务的结果对感知质量更新的影响。为避免用户执行任务时的偶然性，用户感知质量的更新过程中增大历史感知质量的比重，因此设置 $\alpha$ 的取值范围在区间[0.5,1]。

$$
\lambda _ { k } ^ { ^ r } { } ^ { } = \alpha \lambda _ { k } ^ { ^ { r - 1 } } { } ^ { } + ( 1 - \alpha ) A _ { k } ^ { ^ { j } }
$$

# 3 仿真实验

针对MCS空间任务的分配问题，综合考虑了用户到任务的空间距离、任务的质量要求、用户的感知质量及最大执行能力等因素，以感知成本最小为目标，基于遗传算法和贪心算法设计了一种空间任务的分配算法GGA-TA。刘琰等人[13]针对多任务情景，以感知成本最小为目标设计了一种PT-Most算法，但是该算法并未考虑用户的感知质量和任务的质量要求，为了和PT-Most算法进行比较证明GGA-TA算法的高效性，在PT-Most算法第一步中分别优先选择固定激励低的用户和感知质量与固定激励比值高的用户，并用CostFirst和RatioFirst分别表示两种算法，为用户分配任务时，设置约束条件：不满足任务质量要求的用户不能执行该任务。

在MATLAB实验环境中模拟 $N$ 个感知任务，随机分布在 $6 0 0 \times 6 0 0$ （单位： $\cdot \mathrm { k m }$ ）的区域内。每个任务的最低质量要求$q ^ { \mathrm { i } }$ 服从区间[0,30]上的均匀分布。此外，模拟 $M$ 个感知用户，用户的出发点设为(0.0)，每个用户的感知质量 $\lambda _ { k }$ 服从区间[0,30]上的均匀分布。用户的固定激励 $\boldsymbol { f } _ { \scriptscriptstyle k }$ 服从区间[1,30]上的均匀分布，用户的动态成本 ${ \boldsymbol { p } } _ { k }$ 服从区间[0.1,0.3]上的均匀分布。感知用户的最大执行能力服从区间[4.8]上的均匀分布。其他参数设置如表2所示。为保证算法结果近似收敛到最优，仿真实验中设置群体规模(Size)为100，最大进化代数 $( G )$ 为1500。，为处理约束条件，惩罚系数 $\left( \boldsymbol { p } _ { \boldsymbol { w } } \right)$ )取100000。交叉概率和变异概率是影响遗传算法性能的关键所在，为避免实验结果陷入局部最优，本次仿真实验设置交叉概率 $\left( \begin{array} { l } { p _ { c } } \end{array} \right.$ )为0.9，变异概率( $\boldsymbol { p } _ { \scriptscriptstyle m }$ )为0.05。每次仿真实验GGA-TA算法执行10次，分别取10次实验结果的最小值和平均值。

表2参数设置表  
Table 2 Parameter setings   

<html><body><table><tr><td>参数名称</td><td>值</td></tr><tr><td>Size</td><td>100</td></tr><tr><td>G</td><td>1500</td></tr><tr><td>Pw</td><td>1000000</td></tr><tr><td>P</td><td>0.9</td></tr><tr><td>Pm</td><td>0.05</td></tr></table></body></html>

# 3.1用户总量变化对三种算法性能的影响

设置任务数量 $N = 1 0$ 和 $N = 2 0$ ，分别观察任务数量较少和任务数量较多的情况下，用户总量变化对三种算法性能的影响。

a)任务数量 $N = 1 0$ ,结果如图2、3所示。从图2和3中可以看出任务数量为10时，随着用户总量的增加，GGA-TA算法的感知总成本和用户移动的距离先下降后基本保持不变，而CostFirst和RatioFirst 算法的感知成本和用户的移动的距离远远高于GGA-TA算法，这是因为GGA-TA是一种智能算法，能够综合考虑任务的质量要求，用户的感知质量，用户与任务的空间距离等多个因素找到最优解，而CostFirst和RatioFirst仅仅使用贪心算法容易陷入局部最优。

![](images/c5da39f3c1ca4902a5211710c7ffb5509aa0a7b21dec9a13038653da29fcfee6.jpg)  
图2 $N { = } 1 0$ 时，用户总量与感知总成本的关系 Fig.2Effect of number of users on the cost of three algorithms when there have ten tasks.

![](images/4dfb8df7f0e7932b4218e27e37d1d9f6c1bbf610ecff0f2520ff3b299332fcc9.jpg)  
图3 $\Nu { = } 1 0$ 时，用户总量与用户移动的总距离的关系 Fig.3Effect of number of users on the distance of three algorithms when there have ten tasks.

b)任务数量 $N = 2 0$ ，结果如图4、5所示。

![](images/38de900540fcd372e5259a9214c8329be3386461c80961c380ab2be96f88862e.jpg)  
图4 $\scriptstyle \mathbf { N = } 2 0$ 时，用户总量与感知总成本的关系 Fig.4Effect of number of users on the cost of three algorithms when there have twenty tasks.

![](images/b5a616e0ac3815a3c5c20ee3d8d780abc2f6787cbb32e4b6b0d293e702ffc938.jpg)  
图5 $\scriptstyle \mathbf { N = } 2 0$ 时，用户总量与用户移动的总距离的关系 Fig.5Effect of the number of users on the distance of three algorithmswhen there have twenty tasks.

从图4、5中可以看出任务数量为20时，随着用户总量的增加，GGA-TA算法感知总成本和用户移动的距离基本保持不变而且远远低于CostFirst和RatioFirst算法。

# 3.2任务总量变化对三种算法性能的影响

为分析任务总量变化对三种方法性能的影响，实验设置用户总量 $\ d { \ b { M } } = 2 0$ ，结果如图6、7所示。

由图6、7可知，用户总量 $\scriptstyle { M = 2 0 }$ 时，随着任务总量的增加，三种算法的感知总成本和用户移动的距离均不断增加。但是当任务总量达到36时，RatioFirst算法无法将所有任务分配出去，当任务总量达到51时，CostFirst算法无法将所有任务分配出去。当任务总量超过48时，GGA-TA算法的一次计算结果存在不能分配失败的情况，但10次计算后依然能将任务成功分配。而且GGA-TA算法在感知总成本和用户移动的总距离方面总是小于前面两种算法。

![](images/a68ad3d80ce69c24d80ab7afd5c1d231cee6916d4d59f58bc86f42cab6265990.jpg)  
图6 $\scriptstyle \mathbf { M } = 2 0$ 时，任务总量与感知总成本的关系 Fig.6Effect of number of tasks on the cost of three algorithms when there have twenty users.

![](images/a73c2f7529b3f9dc5e8d63d69fbdd5e1098fa99cbc127cee160527be0e4057d2.jpg)

为分析任务总量变化对三种算法性能的影响，记录了用户总量 $\ d { \ b { M } } = 2 0$ 任务总量不断增加的情况下三种算法的运行时间，如图8所示。

![](images/bc854b0e32a8a1c9a2c754ca83f619f7e9d5f2300588d29ad44efb1cf2cc8dca.jpg)  
图7 $\scriptstyle \mathbf { M } = 2 0$ 时，任务总量与用户移动的总距离的关系 Fig.7Effect of number of tasks on the distance of three algorithms when there have twenty users.   
图8 $\mathbf { M } { = } 2 0$ 时，任务总量与算法执行时间的关系 Fig.8Effect of the number of tasks on the execution time of three algorithms when there have twenty users.

如图8可知，随着任务总量的增加，GGA-TA的计算量不断增大，算法执行时间也不断增大。由于GGA-TA算法为启发式算法，需要经过不断的迭代计算才能得到最优结果，所以GGA-TA算法的执行时间远高于另外两种算法。

实验证明，相比CostFirst算法和RatioFirst算法，本文基于遗传算法和贪心算法混合提出的GGA-TA算法，能在任务全部被成功分配的前提下实现感知成本最小。在本文所阐述的系统模型中，GGA-TA算法能够综合考虑任务的质量要求、用户的感知质量、用户的最大执行能力和用户到任务的空间距离等多种因素，使得该方法相比另外两种算法在用户执行任务移动的总距离和感知总成本等方面均有较好的表现。

# 4 结束语

针对MCS中的空间任务分配问题，本文站在平台的角度，设计了一种空间任务的分配机制，旨在满足任务质量要求的同时最小化感知成本。实验证明，本文提出的分配机制在小规模的任务分配问题中具有良好的效果。但是GGA-TA算法的执行时间随着任务量的增大不断增加，所以本文所提机制不适用于大规模计算问题。在以后的研究中力求设计一种适应于大规模空间任务分配问题的算法。

# 参考文献：

[1]Yin Xizhe,Shen Weiming,Samarabandu J,et al.Human activity detection based on multiple smart phone sensors and machine learning algorithms [C]//Proc of the 19th IEEE International Conference on Computer Supported Cooperative Work in Design.Piscataway,NJ: IEEE,2015: 582-587.   
[2]Ganti R K,Ye Fan,Lei Hui.Mobile crowd sensing:current state and future challenges [J]. IEEE Communications Magazine,2O11,49(11): 32-39.   
[3]吴垚，曾菊儒，彭辉，等．群智感知激励机制研究综述[J].软件学 报,2016,27(8):2025-2047.(Wu Yao,Zeng Juru,Peng Hui,et al. Survey on Incentive Mechanisms for Crowd Sensing [J]. Journal of Software,2016,27(8):2025-2047)   
[4]Karaliopoulos M,Telelis O,Koutsopoulos I.User recruitment for mobile crowdsensing over opportunistic networks [Cl//Proc of IEEE Conference on Computer Communications.Piscataway,NJ: IEEE,2015: 2254-2262.   
[5] Coric V, Gruteser M. Crowdsensing maps of on-street parking spaces [C]/Proc of IEEE International Conference on Distributed Computing in Sensor Systems.Piscataway,NJ:IEEE,2013:115-122.   
[6] Maisonneuve N, Stevens M,Niessen M,et al. Noisetube: measuring and mapping noise pollution with mobile phones [C]// Proc of the 4th InternationalSymposiumonInformationTechnologies in Environmental Engineering.Piscataway,NJ: IEEE,2009: 215-228.   
[7]Guo Bin,Chen Huihui，Yu Zhiwen,et al.FlierMeet:a mobile crowdsensing system for cross-space public information reposting, tagging,and sharing[J].IEEE Trans on Mobile Computing,2O15,14 (10):2020-2033.   
[8]Han Kai, Zhang Chi,Luo Jun. Taming the uncertainty: budget limited robust crowdsensing through online learning [J]. IEEE/ACM Trans on Networking,2016,24(3): 1462-1475.   
[9]Xu Jia,Xiang Jinxin,Yang Dejun.Incentive mechanisms for time window dependent tasks in mobile crowdsensing [J].IEEE Trans on Wireless Communications,2015,11(14):6353-6364.   
[10]施战，辛煜，孙玉娥，等．基于用户可靠性的众包系统任务分配机制 [J].计算机应用,2017,37(9):2449-2453.(Shi Zhan,Xin Yu,Sun Yu-e, et al.Task allocation mechanism for crowdsourcing system based on reliability of users [J]. Journal of Computer Applications,2017,37(9):

# 2449-2453)

[11]Miao Chunyan,Yu Han,Shen Zhiqi,et al.Balancing quality and budget considerations in mobile crowdsourcing [J].Decision Support Systems, 2016(90):56-64.   
[12] Estrada R,Mizouni R,Otrok H,et al.A crowd-sensing framework for allocation of time-constrained and location-based tasks [J].IEEE Trans on Services Computing,2018,DOI:10.1109//TSC.2017.2725835.   
[13]刘琰，郭斌，吴文乐，等．移动群智感知多任务参与者优选方法研究 [J]．计算机学报，2016.40(8):1872-1877.(Liu Yan，Guo Bin，Wu Wenle,etal.Multitask-Oriented Participant SelectioninMobile Crowd Sensing[J].Chinese Journal of Computers,2016,40(8):1872-1877)   
[14]Wang Jing,Tang Jian,Xue Guoliang，et al.Towards energy-efficient task scheduling on smartphones in mobile crowd sensing systems [J] Computer Networks,2017(115):100-109.   
[15]Liu CH,Zhang B,Su X,et al.Energy-aware participant selection for smartphone-enabled mobile crowd sensing [J]. IEEE Systems Journal, 2017,11(3): 1435-1446.