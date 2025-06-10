# 改进狼群算法求解旅行商问题

黄海松，任竹鹏，魏建安(贵州大学 现代制造技术教育部重点实验室，贵阳 550025)

摘要：为了找到一条最短路径，并克服传统算法在路径规划中不适合离散域求解以及收敛速度慢等问题，提出一种改进的狼群算法。通过在初始化阶段引入位置-次序编码的方法，研究了离散域的路径优化；同时在迭代过程中引入二次搜索来提高算法求解速度与精度，以实现在达到最大迭代次数前出现最优解。结果表明，改进的狼群算法相比已有的算法求解精度更高，收敛速度更快，更加有效地避免陷入局部最优。可见改进狼群算法可以很好的应用于求解最优路径规划问题。

关键词：改进狼群算法；离散域；二次搜索；路径规划 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.07.0370

# Improved wolf group algorithm for solving traveling salesman problem

Huang Haisong, Ren Zhupeng,Wei Jian'an (KeylaboratoryofAdvancedManufacturingTechnologyofMinistryofEducationGuizhou UniversityGuiyang55o5,China)

Abstract:Inorder tofindashortest pathandovercome the problems that traditional algorithms are not suitablefordiscrete domain solution and slowconvergence in path planing,This Paper proposed an improved wolf group algorithm.Byintroducing theposition-ordercoding methodintheinitializationphase,thispaperstudiedthepathoptimizationproblemofdiscretedomains. Atthesame time,it introducedasecondarysearch intheiterative processto improve the speedandaccuracyofthealgorithm totheoptimal solutionthatis before the maximumnumberofiterations.Theresultsshowthat theimproved wolf groupalgorithm has higheraccuracyand fasterconvergence thantheexisting algorithms,anditis more efective toavoid falling into local optimum.

Key words: IWPA; discrete domain; second search; path planning

# 0 引言

旅行商问题 (traveling salesman problem，TSP)[1]是一种常见的路径优化问题，其目的是为了求得一条经过所有城市的最短路径。现实生活中，很多问题都被抽象为TSP问题进行求解。例如机器人控制[2]、车间调度、无人机航迹规划[3]、计算机联网、网络路由器布设等。虽然 TSP 属于NP-hard[4的组合优化问题，求解困难，但是其研究具有实际价值和重要的理论意义。

理论上，较小规模的TSP可以用传统算法获得最优解，较大规模的TSP一般采用启发式算法,但启发算法也存在着有限时间内无法取得最优解的局限。而由自然界生物群体演化而来的群体智能算法（遗传算法、粒子群优化算法、蚁群算法[5]、人工蜂群算法、萤火虫群优化算法、生物地理迁移算法、帝国主义竞争算法等），为求解复杂路径优化问题提供了不同的方法。新兴的群体智能仿生算法[提高了在有限时间内获得最优解的概率，并且缩小了解空间。但很多算法也存在容易陷入局部极值和收敛速度慢等不足。因此，路径规划问题[依然是具有难度跟研究价值的问题之一,

基于狼群算法，国内外很多学者提出了不同的改进方法。文献[8]通过设计新的猛狼位置更新公式，优化传统狼群算法步长的方法进行改进。文献[9]通过引入差分进化中的交叉、变异、选择等操作，提高了算法的寻优性能。但是他们都存在这收敛速度慢，易陷入局部最优的缺点，尤其是未考虑到狼群算法在离散域求解的问题。因此为实现离散域的路径优化,采用一种引入位置-次序编码的方法。为了提高狼群算法求解的速度与精度，在迭代过程中采用引入随机单点插入算子、多点插入算子的方法，通过二次搜索来实现在达到最大迭代次数时出现最优解。

# 1 狼群算法的概述

探狼游走、召唤头狼、猛狼围攻这3种智能行为构成了狼群算法[8的主体。其规则是“优胜劣汰”的狼群更新规则以及“胜者为王”的头狼角逐规则。其步骤如下：

a)狼群的空间坐标在解空间中随机初始化,头狼即为最优目标函数值的人工狼。

b)在搜索猎物时，探狼开始游走。如果探狼发现的气味浓度比头狼发现的浓度大，则探狼处于主导地位，同时更新头狼位置。反之，探狼需要继续游走，直到发现的猎物气味浓度大于头狼或者是达到最大的游走次数，那么狼头将在现有的位置进行召唤。

c)在头狼发出召唤以后，猛狼开始以最大步长向头狼移动。在这个过程中，如果发现猛狼的目标值优于头狼，那么将更新头狼。反之，猛狼将不断移动，直到进入围攻范围。

d)联合探狼以后，靠近头狼的猛狼将围捕猎物(把头狼位置视为猎物)。如果在实施围攻以后，发现人工狼的目标值优于头狼，则更新头狼位置，继续进行捕获。反之,则不变。

e)将目标函数值较小的人工狼进行淘汰，并且新的人工狼将在解空间中随机生成，不断实现狼群的更新。

f)最后头狼的目标值需要根据是否收敛于全局最优解或者迭代次数是否达到最大来判断。如果没有达到，则需要继续迭代，直到满足条件。在达到要求以后，输出的目标函数值就是最优解，被求函数的最佳位置即为头狼的空间坐标[9]。

# 2 改进狼群算法求解路径规划

狼群算法虽然可以处理简单的路径规划问题，但不能实现离散域的路径规划，且迭代速度较慢。因此提出一种改进狼群算法，该算法通过引入位置-次序编码的方法，来实现离散域的路径优化；通过二次搜索来提高狼群算法求解的速度与精度，具体过程如下。

# 2.1改进狼群算法求解路径规划原理

狼群算法与路径规划问题的对应关系如下：a)狼群算法—路径规划；  
b)狼个体—可行路径;  
c)狼位置变动 —路径顺序变动;  
d)狼适应度- -路径长度。

在搜索模式时，狼群定义了三个参数：个体改变的基因的个数CDC；放置变异状态的记忆池SMP；个体上每个基因的改变范围SDR.具体的搜索模式是：a）狼群中当前状态的狼个体置于SMP并复制；b）将变异发生后的记忆池中复制的副本改变,并更新到新的位置；c）计算副本的适应度值,狼最终的更新状态就是其中的一个最优的状态。

设狼个体i的当前位置为k,首先对于狼群个体𝑖(t)=(si(),'si().in()),在记忆池中复制其位置；然后在狼群搜索模式下选择 SMP-1个位置进行变异操作，其中每个个体选择CDC个基因位置,变异公式如式（1）所示。最后对应的可行路径编码即为SMP个位置转换而成，并计算适应度，更新个体。在该搜索方式下所有狼个体会逐渐收敛于全局最优解。

$\mathrm { { W o l v e ( n ) . l o c a t i o n ( k + 1 ) = W o l v e ( n ) . l o c a t i o n ( k ) } }$ $+ \mathrm { W o l v e ( n ) . l o c a t i o n ( k ) ^ { * } ( S D R ^ { * } ( r a n d ^ { * } 2 - 1 ) ( 1 ) }$

在跟踪模式下，狼个体的每次迭代都将处于全局最优状态，如此不断逼近全局最优解.在此进程中,每只狼的速度标记为Vi={i,v²,,v},狼个体分别利用式（2）（3）来更新自己的速度与位置。

$$
\nu _ { k } ^ { ( d ) } \left( t + 1 \right) = \mathbf { v } _ { \mathbf { k } } ^ { ( d ) } + c ^ { \ast } r a n d ( s _ { b e s t } ^ { ( d ) } \left( t \right) - s _ { k } ^ { ( d ) } ( t ) \left( 2 \right)
$$

其中： $\mathbf { V } _ { k } ^ { ( d ) } ( t + 1 )$ ,表示第K只狼第d位的速度，且 $\scriptstyle \mathrm { d = 1 , } 2 \cdots , 1 ;$ C为常数; $s _ { b e s t } ^ { ( d ) } ( t )$ 为狼群全局最优解;参考文献[10] $\scriptstyle - 2$ ;rand 为[0,1]的随机数。

$$
s _ { k } ^ { ( d ) } \big ( t + 1 \big ) = \mathbf s _ { \mathrm { k } } ^ { ( d ) } + s _ { k } ^ { ( d ) } ( t + 1 )
$$

其中： $s _ { k } ^ { ( d ) } ( t )$ 表示当前位置;更新后的位置是 $s _ { k } ^ { ( d ) } ( t + 1 )$ 。

记录当前迭代的最优解并且计算狼个体的适应度,继续进行规定的迭代次数。

# 2.2改进狼群算法的描述

2.2.1狼的位置-次序编码过程

在连续域的函数优化中WPA可以应用,但是却不适合在离散域 TSP 求解中直接应用[II]。主要原因是 TSP 往往是由自然数表示，但搜索模式下变异发生在实数域范围，为了克服此问题，引进位置-次序编码。

狼群算法的第t代第i个体狼如式（4）所示，ord( $X _ { i j } ( t )$ ）表示将 $s _ { i 1 } ( t ) , s _ { i 2 } ( t ) , . . . , s _ { i n } ( t )$ 按升序排列后 $s _ { i j } ( t )$ 在所得序列中的次序，则式（5）是其对应的可行路径编码，这个变换过程就是位置-次序编码。

$$
s _ { i } ( t ) = s _ { i 1 } ( t ) , s _ { i 2 } ( t ) , . . . . , s _ { i n } ( t )
$$

$$
\mathbf { W } \mathbf { t } = ( \mathrm { o r d } ( s _ { i 1 } ( \mathbf { t } ) ) , \mathrm { o r d } ( s _ { i 2 } ( \mathbf { t } ) ) , . . . , \mathrm { o r d } ( s _ { i n } ( \mathbf { t } ) )
$$

例如， $S \left( \mathrm { t } \right) = ( 2 . 0 3 3 7 , - 1 . 9 7 2 0 , 4 . 9 9 0 1 , - 4 . 0 0 1 5 ) ^ { \mathrm { T } }$ 则由上述的位置-次序编码变换过程可知，对应的位置一次序编码向量为$W ( { \boldsymbol { \mathrm { t } } } ) = \left( 2 , 3 , 1 , 4 \right) ^ { \mathrm { T } } \circ$

# 2.2.2适应度的确定

设 $\mathbf { p } _ { 1 } , \mathbf { p } _ { 2 } , . . . , \mathbf { p } _ { n }$ (其中 $1 , 2 , \ldots , \bar { 1 }$ 为城市编号)为一条可行访问路径，则式（6）是路径的总长度。在狼群算法中,评估个体是根据路径的长度，d越大,表示个体适应度越差，即路径长度的倒数是个体适应度(fitnes $\mathrm { \Omega _ { \mathrm { { i } = 1 / d } } }$ ）

$$
\mathbf { d } = \sum _ { i = 1 } ^ { n - 1 } d ( p _ { i } , p _ { i + 1 } ) + d ( p _ { n } , p _ { 1 } )
$$

其中： $\mathrm { d } ( p _ { i } , p _ { j } )$ 一表示 $p _ { i }$ 与 ${ p } _ { j }$ 之间的距离。

# 2.2.3二次搜索策略

搜索模式是狼群算法的主要优化过程，但它同时也存在着一些问题，比如变异策略比较单一、收敛性达不到最佳等方面。当我们要优化的种群数目足够大时，因其最大迭代次数有限会使得优化变异后的路径很难出现较优解。当路径没有获得更优解时，在搜索模式优化完成后，为了更好地解决TSP，引入变异算子不同但与狼群搜索模式相似的二次搜索优化策略。如图1所示。

![](images/2b890726bbafd04d5068414b0df13934a6d60a0e56d1799ea0b41b5016ddfbb4.jpg)  
图1改进狼群算法求解路径规划的流程图

二次搜索优化策略的两种方式如下：

1）随机单点插入算子的描述

编码所有的个体狼,设 $\mathbf { c } _ { i } , \mathbf { c } _ { j }$ （ij为随机选择的两个基因位置）为其位置上的城市。在$\Delta \mathsf { d } \gets \mathsf { d } \big ( c _ { i } , c _ { i + 1 } \big ) + \mathsf { d } ( c _ { j } , c _ { j + 1 } ) > \mathsf { d } \big ( c _ { i } , c _ { j } \big ) + \mathsf { d } ( c _ { i + 1 } , c _ { j + 1 } )$ 式中，两座城市 $\left( \mathbf { \Phi } _ { C _ { i } , C _ { j } } \right)$ 的距离为 $\mathbf { d } ( \mathbf { c } _ { \mathrm { i } } , \mathbf { c } _ { \mathrm { j } } )$ 。为了使整个路径的距离得到改善，当 $\Delta \mathrm { d } > 0$ ，就将 $j$ 与 $i + 1$ 两基因位互换。这种方法任意选取其中的两个位点进行基因交换，对于“模式转化”影响较小，计算也并不复杂。通过此方法，在每一次迭代时都可以选择距离自己最近且路径最优的点。如图2所示.

![](images/7f2f712ef331566c70bfb7e52fef132a879a04b3962b151acb32d561aa55c835.jpg)  
图2随机单点插入

2）随机多点插入算子的描述

编码所有的狼个体，不妨设k为城市位置的编号。基因位i是随机选取的，距离k城市最近的t城市是在基因位以后的n-i个位置。其基因位为j，将j基因位以后的 ${ \bf n - j }$ 位整体插入到基因位i后。这种线段算子的插入，可以大大缩减计算时间，以最小的迭代次数找到最优解。如图3所示。

此种插入方法优点为：

![](images/15f5b663e9a3b854134bec1ee95a401331fa4ae874552cd116e47b6259371087.jpg)

a)可以通过选择距离最短的点来改善算法的适应度，使其具有局部优化作用；

b)可以通过随机选取插入点,来丰富可行解的多样性；

c)通过整体插入来避免破坏已经存在的全局最优的部分路径序列。

# 3 改进狼群算法的仿真实验及分析

选取TSPLIB标准库中的几个实例进行实验，验证离散狼群算法的准确性、有效性和可行性。选择参考文献[14\~16]中优化算法的结果进行比较。

![](images/6c700562b0301778de6863ea31fcb2b9d3eeca9c4198fe11dacbaf8f5bc3d591.jpg)  
图3随机多点插入

# 3.1实验结果

3.1.1Dantzig42 问题

针对Dantzig42问题,本文算法优化路径如图4所示，10次优化结果如表第1列所示。

3.1.2Eil51问题

![](images/2b6ef9f255b066eb83ede00de6b05c7ee2269ae9e8057277dca11a618c9fadf2.jpg)  
图4Dantzig42问题优化路径

针对Eil51问题，本文算法优化优化路径如图5所示，10次优化结果如表1第2列所示。

# 3.1.3Berlin52问题

针对Berlin52问题，本文算法优优化路径如图6所示，黑色圆圈为局部放大部分，证明没有出现交叉。10次优化结果如表1第3列所示。

![](images/59ab77ccc50d1d2d4f2915b415baac26c06435d05f712495ebb851914b4981a9.jpg)  
图5Eil51问题优化路径  
图6Berlin52问题优化路径

# 3.2实验分析

由图4\~6可得,上述三个TSPLIB 实例经过本文IWPA算法优化得到的最优路径没有出现路径十字交叉，长度基本都优于其他各文献算法。由表2可得，改进的狼群算法优于未改进的狼群算法以及参考文献的算法，在路径优化方面得到很大的提高。其中Dantzig42、Eil51和Berlin52实例的优化结果优于国际通用网站TSPLIB给出的最优结果。在多次优化实验中，算法可以收敛而且得到全局最优解。由表3与已改进的狼群算法对比分析，经六组实验验证可得，在最优解最差解及其迭代次数方面，取得了显著提高。在平均耗时方面，相较于参考文献[17],采用随机插入算子的方法平均耗时更短，改进的狼群算法优于同类算法。因此本文设计的改进狼群算法能够更加有效地跳出局部最优，在达到迭代次数之前取得最优解.因此离散狼群算法可以很好的应用于路径优化问题。

表1本文算法各TSP问题10次优化结果  

<html><body><table><tr><td>序号</td><td>Dantzig42问题</td><td>Eil51问题</td><td>Berlin52问题</td></tr><tr><td>1</td><td>674.3100</td><td>419.1566</td><td>7534.3700</td></tr><tr><td>2</td><td>674.3100</td><td>419.1566</td><td>7534.3700</td></tr><tr><td>3</td><td>674.3100</td><td>419.1566</td><td>7534.3700</td></tr><tr><td>4</td><td>674.3112</td><td>419.1566</td><td>7536.2342</td></tr><tr><td>5</td><td>674.3100</td><td>422.3268</td><td>7538.4263</td></tr><tr><td>6</td><td>674.3100</td><td>422.2148</td><td>7534.3700</td></tr><tr><td>7</td><td>674.3100</td><td>419.1566</td><td>7534.3700</td></tr><tr><td>8</td><td>674.3100</td><td>419.1566</td><td>7534.3700</td></tr><tr><td>9</td><td>674.3100</td><td>419.1566</td><td>7534.3700</td></tr><tr><td>10</td><td>674.3100</td><td>422.2148</td><td>7534.3700</td></tr></table></body></html>

表2优化效果对比  

<html><body><table><tr><td rowspan="2">序号</td><td rowspan="2">TSP实例</td><td rowspan="2">已知最优解</td><td colspan="5">不同算法优化所得最优解</td></tr><tr><td>WPA</td><td>文献[14]</td><td>文献[15]</td><td>文献[16]</td><td>IWPA</td></tr><tr><td>1</td><td>Dantzig42</td><td>699.0000</td><td>732.4200</td><td></td><td></td><td>679.2019</td><td>674.3101</td></tr><tr><td>2</td><td>Eil51</td><td>426.0000</td><td>653.1566</td><td>429.3800</td><td>466.8750</td><td>428.8717</td><td>420.2081</td></tr><tr><td>3</td><td>Berlin52</td><td>7542.0000</td><td>7791.2648</td><td>7548.3200</td><td>8700.1560</td><td>7544.37</td><td>7534.3700</td></tr></table></body></html>

表3与已改进狼群算法的性能对比分析  

<html><body><table><tr><td rowspan="2"></td><td rowspan="2">TSP 实例已知最优解</td><td rowspan="2"></td><td rowspan="2">算法</td><td rowspan="2">最优解</td><td rowspan="2">最差解</td><td rowspan="2">平均迭代 收敛次数</td><td rowspan="2">平均耗时/S</td></tr><tr><td></td></tr><tr><td rowspan="2">1</td><td>Bays29</td><td>9293.3300</td><td>DWPA</td><td>9074.1000</td><td>9104.4000</td><td>12</td><td>9.9</td></tr><tr><td rowspan="2">Eil51</td><td rowspan="2">426.0000</td><td>IWPA</td><td>9065.3700</td><td>9097.3642</td><td>11</td><td>8.1</td></tr><tr><td>DWPA</td><td>428.8718</td><td>437.2167</td><td>52</td><td>6.9</td></tr><tr><td rowspan="2">3</td><td>Berlin52</td><td>7542.0000</td><td>IWPA DWPA</td><td>419.1566 7545.4000</td><td>422.3268 7598.4000</td><td>43 34</td><td>6.7 9.3</td></tr><tr><td rowspan="2"></td><td rowspan="2"></td><td>IWPA</td><td>7534.3700</td><td>7538.4263</td><td>29</td><td>8.4</td></tr><tr><td>DWPA</td><td>510.8863</td><td>525.8967</td><td>258</td><td>7.5</td></tr><tr><td rowspan="2">4</td><td rowspan="2">Gr96</td><td rowspan="2">512.3094</td><td></td><td>508.3147</td><td>518.4312</td><td>176</td><td>6.9</td></tr><tr><td>IWPA</td><td>58535</td><td>58779</td><td></td><td></td></tr><tr><td rowspan="2">5</td><td rowspan="2">Pr144</td><td rowspan="2">58537</td><td>DWPA</td><td>58302</td><td>58505</td><td>245</td><td>8.7</td></tr><tr><td>IWPA</td><td></td><td></td><td>210</td><td>8.2</td></tr><tr><td rowspan="2">6</td><td rowspan="2">Gr202</td><td rowspan="2">549.9981</td><td>DWPA</td><td>490.0669</td><td>507.5534</td><td>404</td><td>7.3</td></tr><tr><td>IWPA</td><td>489.0322</td><td>490.0837</td><td>391</td><td>7.1</td></tr></table></body></html>

# 4 结束语

本文采用引入位置次序编码的方法，实现了离散域的路径优化。在搜索过程中采用随机插入算子的方法，提高求解速度与精度，实现了在达到最大迭代次数前完成路径优化，避免了陷入局部最优。相较于其他算法以及其他改进的狼群算法，本文在离散域求解方面实现了较大的进步，通过上面的实验也可看出，在求解速度与精度方面也取得了较大领先。此外还需解决的一个难点是在工程实际中，运用在车间AGV小车的运输中出现的实际问题，是本课题组进一步研究和解决的方向。

# 兮义删：

[1]Luo W,Lin D,Feng X.An improved ant colony optimization and its application on TSP problem [C]//Proc of IEEE International Conference on Internet of Things.2017: 136-141.   
[2] 刘洁，赵海芳，周德廉．一种改进量子行为粒子群优化算法的移动机器 人路径规划 [J]．计算机科学,2017,44(Z11):123-128.(Liu Jie,Zhao Haifang,Zhou Delian.Mobile robot path planning based on improved quantum behavior particle swarm optimization algorithm [J].   
[3]Computer Science,2017,44(Z11): 123-128.)   
[4] 郑健，黄敏，张腾，等．求解指路标志指引路径规划问题的改进人工蜂 群算法[J].计算机应用研究，2017,34(8):2355-2359.(Zheng Jian, Huang Min,Zhang Teng,et al. Improved artificial bee colony algorithm for solving path planning problem of directional signs [J].Application Research of Computers,2017,44 (b11): 123-128.)   
[5]Deb S,Fong S,Tian Z,et al. Finding approximate solutions of NP-hard optimization and TSP problems using elephant search algorithm [J].Journal of Supercomputing,2016,72 (10): 1-33.   
[6]方清华，倪丽萍，李一鸣，等．求解物流Web 服务组合问题的两阶段多 目标蚁群算法[J].中国机械工程，2016,27(10):1327-1336.(Fang Qinghua,Ni Liping,Li Yiming,et al. Two-stage multi-objective ant colony algorithm for solving logistics Web service composition problem [J].China Mechanical Engineering,2016,27(10):1327-1336.)   
[7] 元祥波，朱云龙，张丁一．求解 PFSP的双种群协同学习算法[J].控制 与决策,2017,32(1):12-20.(Yan Xiangbo, Zhu Yunlong,Zhang Dingyi. Dual-population collaborative learning algorithm for solving PFSP [J]. Control and Decision,2017,32(1):12-20.)   
[8]荀燕琴．基于群体智能优化的 AGV 路径规划算法研究 [D].长春：吉 林大学,2017.(Yan Yanqin. Research on AGV path planning algorithm based on swarm intelligence optimization [D]. Changchun: Jilin University, 2017.)   
[9]叶勇，张惠珍．多配送中心车辆路径问题的狼群算法[J].计算机应用 研究，2017,34(9): 2590-2593.(Ye Yong,Zhang Huizhen.Wolf group algorithm for multi-distribution center vehicle routing problem [J]. Journal of Computer Applications,2017,34(9): 2590-2593.)   
[10]王盈祥，陈民铀，程庭莉，等．基于差分进化的改进狼群算法研究

[J//OL].计算机应用研究，2019,36(8):1-10.(WangYingxiang,Chen Minyu, Cheng Tingli, Sheng Qi, Dong Longchang,Li Zhe.Research on improved wolf group algorithm based on differential evolution [J//OL]. Journal of Computer Applications,2019 (08):1-10.)

[11]金杉，金志刚．基于量子狼群进化的多目标汇聚节点覆盖算法[J]．电 子与信息学报,2017,39(5):1178-1184.(Jin Shan,Jin Zhigang.Multiobjective convergence node covering algorithm based on quantum wolf group evolution[J].Journal of Electronics & Information Technology,2017, 39 (5): 1178-1184.)

[12]惠晓滨，郭庆，吴娉娉，等．一种改进的狼群算法[J].控制与决策, 2017,32(7):1163-1172.(Hui Xiaobin,Guo Qing,Wu Pingping.An improved wolf group algorithm [J]. Control and Decision,2017,32(7): 1163-1172.)

[13]杨淑莹，张烨．群体智能与仿生计算——MATLAB 技术实现[M]．北 京：电子工业出版社,2012:180-189.(Yang Shuying,Zhang Wei. Group intelligence and bionic computing: matlab technology implementation [M]. Beijing: PublishingHouse of Electronics Industry,2012:180-189.)

[14]宋栓军，杨佩莉，石雯丽．基于人工蜂群算法的柔性工艺与车间调度集 成优化[J].计算机应用,2017,37(2):523-529.(Song Shuanjun,Yang Peili,Shi Wenli.Integrated optimization of flexible process and shop scheduling based on artificial bee colony algorithm[J].Journal ofComputer Applications,2017,37(2): 523-529.)

[15]游晓明，刘升，吕金秋．一种动态搜索策略的蚁群算法及其在机器人路 径规划中的应用[J].控制与决策,2017,32(3):552-556.(You Xiaoming, Liu Sheng,Lyu Jinqiu.An ant colony algorithm for dynamic search strategy and its application in robot path planning [J]. Control and Decision,2017, 32 (3): 552-556.)

[16]葛海明.改进的遗传算法求解TSP问题的应用与研究[D].赣州：江西 理工大学，2016.(Ge Haiming.Application and research of improved genetic algorithm for solving TSP problem [D]. Ganzhou: Jiangxi University of Science and Technology,2016.)

[17]何庆，吴意乐，徐同伟.改进遗传模拟退火算法在TSP优化中的应用 [J].控制与决策，2018(2):219-22 (He Qing,Wu Yile,Xu Tongwei. Application of improved genetic simulated annealing algorithm in TSP optimization [J]. Control and Decision,2018 (2): 219-22)

[18]吴虎胜，张凤鸣，李浩，等．求解TSP问题的离散狼群算法[J].控制与 决策,2015,30 (10): 1861-1867.(Wu Husheng, Zhang Fengming,Li Hao, et al.Discrete wolf group algorithm for solving TSP problem[J].Control and Decision,2015,30 (10):1861-1867.)