# 一种改进的警示传播算法求解Max-SAT问题

吴宇翔‘，王晓峰a，丁红胜a，于卓ä(北方民族大学a.计算机科学与工程学院;b.图像图形智能处理国家民委重点实验室，银川 750021)

摘要：Max-SAT问题是SAT问题的优化版本，目标是在给定的子句集中，找到一组变元赋值，使得满足子句数最多，该问题是典型的NP-hard问题。随着大数据和人工智能的深度发展，过去原有的算法已不再适用，设计新的求解算法或对已有的求解算法进行优化是目前研究的热点。本文针对警示传播算法求解随机 Max-3-SAT 问题的局限性，提出了一种基于变元权值计算的警示传播算法，结合随机游走算法，给出一种新型算法WWP+WalkSAT，通过改进求解的局限性，更好地得到一组有效的初始解，从而提高算法的局部搜索能力。利用2016年Max-SAT 国际竞赛部分基准实例，将WWP+WalkSAT 算法与8种局部搜索算法进行精度方面的对比实验。实验结果表明WWP+WalkSAT算法有较好的性能。

关键词：可满足性问题；最大可满足性问题；警示传播算法；局部搜索算法 中图分类号：TP301 doi:10.19734/j.issn.1001-3695.2022.01.0023

Improved warning propagation algorithm for solving max-sat problem

Wu Yuxianga,Wang Xiaofenga, b,Ding Hongshenga† ,Yu Zhuoa (a.SchoolofComputerScience&Engineering,b.TheKeyLaboratoryofImages&Graphics IntelligentProcessingofState Ethnic Affairs Commission,North Minzu University, Yinchuan 750021,China)

Abstract: TheMax-SATproblemisanoptimizedversionoftheSATproblem.The goalis tofindaset ofvariableasignments inagivensetofclauses sothat the maximum numberofclauses is satisfied.This problemis a typicalNP-hard problem. With thein-depthdevelopmentofbigdataand artificial intellgence,theoriginal algorithms inthe past areno longerapplicable. Designing anew solution algorithm oroptimizing the existing solution algorithm is the current research hotspot.Aiming at thelimitations ofthe information dissemination algorithmfor solving therandom Max-3-SATproblem,this paperproposes a warning disemination algorithm based on the calculation of variable weights.Combined with the random walk algorithm, newalgorithm WWP+WalkSAT is formed,which is solved by improvement The limitationof,it is better togetasetof effective initialsolutions,therebyimproving the local searchabilityof thealgorithm.Using some benchmark examplesofthe Max-SATInternational Competition in 2016,the WWP+WalkSAT algorithmand8local search algorithms are used for accuracy comparison experiments. The experimental results show that the WWP $^ +$ walksat algorithm has good performance.

Key words: satisfiability problem; max-sat problem; warning propagation algorithm; local search algorithm

# 0 引言

组合优化问题在运筹学、离散数学和计算机科学中都有着非常重要的作用，并在国防、交通、医疗、通信等领域有着广泛的应用，其中常见的组合优化问题包括背包问题(Knapsack)、旅行商问题(Travellingsalesmanproblem,TSP)、车辆路径规划问题(VehicleRoutingProblem,VRP)、最大团问题(Maximum Clique Problem,MCP)、最小顶点覆盖问题(Minimumvertexcover,MVC)、最大可满足性问题(MaximumSatisfiability,Max-SAT)[1\~6]等。而最大可满足性问题是一个典型的 NP 难问题，是可满足性问题(Satisfiability，SAT)[7]的优化版本。给定一个命题合取范式(CNF)，CNF 是由一组子句合取构成，每一个子句由一组变元析取构成，Max-SAT问题是寻找一组赋值使得满足子句数目最多。Max-SAT在组合拍卖、车辆调度、排课安排等现实问题中有着广泛的应用，同时图论中的最大团问题和顶点支配集也可以转换成Max-SAT问题进行求解。

为了解决Max-SAT问题，研究人员提出许多有效算法，主要分为完备性算法和非完备性算法两种。完备性算法是可以找到问题的精确解，但在求解大规模问题时，由于其复杂度是指数级，很难在合理时间找到结果。近年来，人们主要在分支策略、推理规则、下界估计[8\~10]三方面进行改进，进而出现了许多有效的算法，具有代表性的有：WmaxSatz[11]、MiniMaxSat[12]等。相对于完备算法而言，非完备性算法则是能短时间内找到大规模问题的最优解，从而提高了求解效率，但缺点则是不能保证解的准确性。主流的非完备性算法是近似算法、信息传播算法、局部搜索算法[13\~15]。

信息传播算法是一种启发式信息传递算法，起源于统计物理学，该类算法通过边缘概率计算的方法，已应用在许多领域。特别是对于命题公式的可满足性问题，有三种基于因子图的信息传播算法，即警示传播算法(warningpropagation,WP)、信念传播算法(belief propagation,BP)和调查传播算法(surveypropagation,SP)。目前，在求解随机SAT问题上信息传播算法是最为有效的方法，并且在图着色、最大流、LDPC编码等许多组合优化问题中取得了不错的成果。

然而，信息传播算法的收敛性和有效性一直是研究的重点。收敛性是指：信息传播算法两次的信息迭代值不发生变化；有效性是指：信息传播算法能够有效的求解问题。文献[16\~18]分析了信息传播算法的收敛性和有效性,并给出了算法收敛的充分条件。文献[19]则是基于具体的实例产生模型分析了信息传播算法的收敛性，并给出了算法收敛的概率条件。

进一步研究发现，在随机3-SAT问题中，子句个数 $\mathbf { \nabla } _ { m }$ 和变元个数 $n$ 的比值称约束密度 $\alpha$ ，即 $\alpha = m / n$ ，它不仅对公式的可满足性产生影响，还对可满足性公式的求解难易程度有着非常重要的影响。随着约束密度 $\alpha$ 的增大，当 $3 . 5 2 < \alpha < 4 . 4 8$ 时，会发生相变。在相变范围以外的可满足性实例均为易解实例，高概率是可满足的；在相变点附近的的实例属于难解实例，高概率是不可满足的。虽然信息传播算法对于求解难解实例十分有效，但在求解相变点以外的易解实例方面，信息传播算法不能收敛。

针对于此问题，文本设计了一种新型变元权值计算的警示传播算法WWP+WalkSAT，通过变元权值计算对警示传播算法进行改进，可以得到一组有效的初始解，再结合随机游走算法进行局部搜索。对该算法的性能表现进行实验分析，在相变点附近实例和相变点以外实例均与其余局部搜索算法进行实验对比。实验结果表明：对于求解任何区域的实例，WWP+WalkSAT在求解精度方面平均优于其他局部搜索算法。

# 1 基础知识

最大可满足性问题是指：给定一组命题变元 $x _ { i } \in X$ ，由这些变元形成一组子句，构成CNF公式，使得CNF公式中满足子句的个数最多，即，使得不满足的子句个数最少。Max-SAT问题的数学模型如式(1)和式(2):

Maximize:

$$
\sum _ { a \in F } w _ { a } \cdot z _ { a }
$$

Subject to: $\forall a \in F \colon \ \sum _ { i \in S _ { a } ^ { + } } x _ { i } + \sum _ { i \in S _ { a } ^ { - } } ( 1 - x _ { i } ) \geq z _ { a }$

$$
z _ { a } \in \{ 0 , 1 \} \ x _ { i } \in \{ 0 , 1 \}
$$

文字的集合(Literal) $X = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . , x _ { n } \}$ ：每一个布尔变元 $x _ { i } \in X$ ，变元 $x _ { i }$ 取正时表示正文字；变元 $x _ { i }$ 取反时表示负文字。

子句的集合(Clause) $C = \{ C _ { 1 } , C _ { 2 } , C _ { 3 } , . . . , C _ { m } \}$ ：对 $m$ 个不同的子句形成一个子句集合，每一个子句由一个或多个文字组成，子句与子句之间通过析取运算连接，且仅当子句中至少有一个文字为1时，该子句满足，反之子句不满足。每一个子句中文字的个数叫做这个子句的长度。当子句中只有一个文字出现时，称该子句为单子句。

合取范式(CNF公式)：由若干个子句合取构成，即${ \cal C } _ { 1 } \wedge { \cal C } _ { 2 } \wedge { \cal C } _ { 3 } \wedge \ldots \wedge { \cal C } _ { m }$ ，当且仅当CNF公式的每一个子句都满足时，称合取范式CNF可满足。

因子图(FactorGraph)：因子图也称二部图，图中包含两类节点：一类是变元节点(图中用圆环表示，记住(1，2，3，4;)),另一类是函数节点(图中中方框表示，记住 $( \mathrm { a } , \mathrm { b } , \mathrm { c } ; \cdots ) ,$ ）给一个CNF公式 $F { = } \{ C _ { 1 } , C _ { 2 } , C _ { 3 } , . . . , C _ { m } \}$ ,公式中由 $x _ { 1 } , x _ { 2 } , x _ { 3 } , . . . , x _ { n }$ 个变元构成，其中所有变元对应的是变元节点，变元析取构成的子句对应的是函数节点。图中出现的虚边和实边代表着CNF公式的两种不同的含义：实边：子句中代表正文字 $x _ { j }$ ，虚边：子句中代表负文字 $\neg { x _ { j } }$ 。

例1： $F = \{ ( x _ { 1 } \lor - x _ { 2 } \lor - x _ { 3 } ) \land ( - x _ { 1 } \lor x _ { 2 } \lor - x _ { 4 } ) \land ( - x _ { 1 } \lor x _ { 3 } \lor x _ { 5 } ) \land ( - x _ { 3 } \lor x _ { 4 } \lor x _ { 5 } ) \} =$ $\{ a \land b \land c \land d \}$ 其对应的因子图如图1所示。

$V ( a ) { = } V ^ { + } ( a ) + V ^ { - } ( a )$ 表示子句 $a$ 中出现的变元集合$V ( a ) { = } V ^ { + } ( a ) { + } V ^ { - } ( a )$ 。其中： $\scriptstyle V ^ { + } ( a )$ 表示子句 $a$ 中变元为正的集合； ${ \cal V } ^ { - } ( a )$ 表示子句a中变元为负的集合； $| V ( a ) \backslash i \$ 表示子句 $\mathbf { \Omega } _ { a }$ 中除变元 $i$ 以外其余变元的集合；在图1中， $V ( a ) = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } \}$ $V ^ { + } ( a ) = \{ x _ { 1 } \}$ ， $V ^ { - } ( a ) = \{ x _ { 2 } , x _ { 3 } \}$ 。

$V ( j )$ 表示含有变元 $x _ { j }$ 的子句集合 $V ( j ) = V ^ { + } ( j ) + V ^ { - } ( j )$ ，其中$V ^ { + } ( j )$ 表示变元 $x _ { j }$ 为正的子句集合； $V ^ { - } ( j )$ 表示变元 $x _ { j }$ 为负的子句集合； $V ( j ) \backslash a$ 表示除了子句 $\boldsymbol { a }$ 以为，其余含有变元 $x _ { j }$ 的子句集合。在图1中， $V ( 1 ) = \{ a , b , c \}$ ， $V ^ { + } ( 1 ) = \{ a \}$ ， $V ^ { - } ( 1 ) = \{ b , c \}$ 。

![](images/28ce9b27a0fa5ec875f0503606947cf7e26c5fcb1b0d81b0eca3aea7062f43b3.jpg)  
图1因子图

$J _ { J } ^ { a }$ ：对于子句a中的变元 $x _ { j }$ 的标识符，变元在子句中的取值，由式(3)表示为

$$
J _ { j } ^ { a } = \left\{ { \begin{array} { l l } { - 1 , } & { x _ { j } \in a } \\ { 1 , } & { \lnot x _ { j } \in a } \end{array} } \right.
$$

定义两个一致性集合 $V _ { a } ^ { u } ( j )$ 和 $V _ { a } ^ { s } ( j )$

$V _ { a } ^ { \mu } ( j )$ 表示除子句 $\mathbf { \Delta } _ { a }$ 以外，含有变元 $x _ { j }$ 且变元 $x _ { j }$ 的取值方向与其子句 $\mathbf { \Delta } _ { a }$ 中取值不一致的子句集； $V _ { a } ^ { s } ( j )$ 表示除子句 $\boldsymbol { a }$ 以外，含有变元 $x _ { j }$ 且变元 $x _ { j }$ 的取值方向与其子句 $\mathbf { \Delta } _ { a }$ 中取值一致的子句集；集合 $V _ { a } ^ { u } ( j )$ 和 $V _ { a } ^ { s } ( j )$ 如图2所示。

![](images/2ab041d8ce41e7b5c9dbbb2c2694d313ab971b52c133765f0d261669a413a237.jpg)  
Fig.1Factor graph   
图2局部因子图  
Fig.2Part of factor graph

# 2 基于变元权值计算的警示传播算法

基于变元权值计算的警示传播算法WWP+WalkSAT是在警示传播算法[20]上进行改进，文献[16]分析警示传播算法的收敛性，通过引入参数，将算法中的信息取值从{0.1}松弛为[0.1]，利用向量空间中压缩函数的性质，给出警示传播算法收敛的一个充分条件，并为警示传播算法性能提供了理论依据。WWP+WalkSAT是在此理论基础上，引入了变元权值计算[21]，从中得到一组有效的初始解，其目的是选出权值最高的文字，使得满足子句个数最多，从而减少无效的子句传播，加快搜索过程。原本的警示传播算法在求解难解实例十分有效，但对于易解实例会出现不收敛现象。对于此问题，该算法在迭代次数结束时，计算局部警示信息变化最小时的警示值，再进行变元权值计算。最后对其初始解采用随机游走的局部搜索算法，可得到更优解，提从而高其算法性能。WWP+WalkSAT打破了原先警示传播算法求解Max-SAT问题的局限性，可用于求解任何区域的实例，同时在求解精度上也有所提高。

# 2.1警示传播算法(Warning Propagation)

通过信息传递而设计的信息传播算法，对于求解可满足性问题具有良好的有效性，警示传播算法是一个迭代运算的算法，在每一次迭代过程中，对于因子图的每条边 $( a , i )$ ，都

会获得一个警示信息，表示在因子图中一个函数节点a传递给变元i一个布尔信息，记作 $u _ { a  i } \in \{ 0 , 1 \}$ 。 $u _ { a  i }$ 的迭代方程如式(4)所示。

$$
u _ { a  i } ( t + 1 ) = \prod _ { j \in V ( a ) \backslash i } \theta ( - J _ { j } ^ { a } ( \sum _ { b \in V ( j ) \backslash a } J _ { j } ^ { a } u _ { b  j } ( t ) ) )
$$

其中 $\mathbf { \chi } _ { t } ^ { }$ 是迭代次数， $\theta ( x )$ 是一个截尾函数，定义为：$\theta ( x ) = \left\{ { 1 , \ x > 0 } \atop { - 1 , \ x \leq 0 }  \right.$ {-l,x≤0，由此公式可以说明，当uav =1表示对于子句$a$ 的满足性由变元 $x _ { i }$ 来决定，当 $u _ { a  i } = 0$ 表示子句 $\mathbf { \Delta } _ { a }$ 的满足性不能完全由变元 $x _ { i }$ 决定，即子句 $\mathbf { \Delta } _ { a }$ 的满足性由其余变元的取值来决定。

对于每一个变元 $x _ { i }$ ，需要计算一个局部腔域 $\boldsymbol { H } _ { i }$ 和一个冲突域 $c _ { i } \in \{ 0 , 1 \}$ ，其中局部腔域和冲突域式(5)和式(6)所示。

$$
H _ { i } = - \sum _ { b \in V ( i ) } J _ { i } ^ { b } u _ { b  i } ^ { * } = \sum _ { b \in V ^ { + } ( i ) } u _ { b  i } ^ { * } - \sum _ { b \in V ^ { - } ( i ) } u _ { b  i } ^ { * }
$$

$$
c _ { i } = \{ \begin{array} { l l } { 1 , ~ i f ( \displaystyle \sum _ { b \in V ^ { + } ( i ) } u _ { b  i } ^ { * } ) ( \displaystyle \sum _ { b \in V ^ { - } ( i ) } u _ { b  i } ^ { * } ) > 0 . } \\ { 0 , ~ o t h e r w i s e . } \end{array} 
$$

当冲突域 $c _ { i } = 1$ 时，即 $( \sum _ { b \in V ^ { + } ( i ) } u _ { b  i } ^ { * } ) ( \sum _ { b \in V ^ { - } ( i ) } u _ { b  i } ^ { * } ) > 0$ ，则表示对于变元 $x _ { i }$ ，受到了两个子句的约束，变元 $x _ { i }$ 在两个子句中的取值不一致，因此变元 $x _ { i }$ 的取值发生了冲突。如：子句 $\mathbf { \Omega } _ { a }$ 告诉变元 $x _ { i }$ 取1，子句 $b$ 告诉变元 $x _ { i }$ 取0。当冲突域 $c _ { i } = 0$ 时，即（∑ub）∑u)=0，则表示对于变元x 的取值没有冲突发生，变元 $x _ { i }$ 的具体取值可以通过局部腔域来决定，如式(7)所示。

$$
x _ { i } = \{ \begin{array} { l l } { 1 , \displaystyle \sum _ { b \in V ^ { + } ( i ) } u _ { b  i } ^ { * } > 0 , \displaystyle \sum _ { b \in V ^ { - } ( i ) } u _ { b  i } ^ { * } = 0 } \\ { \{ 0 , 1 \} , \displaystyle \sum _ { b \in V ^ { + } ( i ) } u _ { b  i } ^ { * } = \displaystyle \sum _ { b \in V ^ { - } ( i ) } u _ { b  i } ^ { * } = 0 } \\ { 0 , \displaystyle \sum _ { b \in V ^ { + } ( i ) } u _ { b  i } ^ { * } = 0 , \displaystyle \sum _ { b \in V ^ { - } ( i ) } u _ { b  i } ^ { * } > 0 } \end{array} 
$$

如果 $H _ { i } > 0$ ，变元 $x _ { i } = 1$ ；如果 $H _ { i } < 0$ ，变元 $x _ { i } = 0$ ；否则变 元 $x _ { i }$ 暂时不赋值。

算法1警示传播算法(WP)

输入：CNF因子图G；最大迭代次数 $t _ { \mathrm { m a x } }$ ；精度 $\varepsilon$ 。

输出：未收敛或收敛，输出警示信息值 $\boldsymbol { u } _ { \ a  i } ^ { * }$

Begin

当 $\scriptstyle t = 0$ 时，对于因子图的每个边 $( a , i )$ ，以1/2的概率随机初始化警示信息 $u _ { a  i } ( 0 )  \{ 0 , 1 \}$ //随机初始化

For t=1to tmax

通过字典的顺序，对图中每一条边 $( a , i ) \in E$ 进行遍历，采用警示更新算法UPDATE- ${ \mathsf { M P } }$ 对 $u _ { a  i }$ 进行更新，即 $u _ { a  i } ( t - 1 )  u _ { a  i } ( t )$

当图中所有的边 $( a , i ) \in E$ ，若 $\sum _ { ( a , i ) \in E } \big | u _ { a  i } ( t ) - u _ { a  i } ( t - 1 ) \big | < \varepsilon$ ，说明已收敛， $u _ { a  i } ( t ) = u _ { a  i } ( t - 1 )$ ，停止循环，返回 $u _ { \ a  i } ^ { * } ( t )$

IF $t = t _ { \operatorname* { m a x } }$

寻找t=argmin∑|ua(t)-ua(t-1)l

返回：未收敛，并将 $u _ { \ a  i } ^ { \circ } ( t ) = u _ { a  i } ( t ^ { \ast } )$ ， $/ /$ 把 $t ^ { * }$ 时刻的信息值保留并赋值给警示值

算法2警示信息值更新算法(UPDATE-WP)  
输入：警示信息值集合 $\{ u _ { b  j } : b \in V ( j ) \backslash a \ \}$ ，对所有的 $j \in V ( a ) \backslash i$   
输出：新的 $u _ { a  i }$   
BeginJ $\mathsf { \tilde { F } } \colon V ( a ) \backslash i = \phi$ ，则返回 $u _ { a  i } = 1$ ELSE:for $j \in V ( a ) \backslash i$ IF $V ( j ) \backslash a = \phi$ ，则 $h _ { j  a } = 0$ （204Else $\begin{array} { r } { h _ { j  a } = ( \sum _ { b \in V _ { + } ( j ) \backslash a } u _ { b  j } ) - ( \sum _ { b \in V _ { - } ( j ) \backslash a } u _ { b  j } ) } \end{array}$ 返回 $\begin{array} { r } { u _ { a  i } = \Pi _ { j \in V ( a ) \backslash i } \theta ( J _ { j } ^ { a } h _ { j  a } ) } \end{array}$ （204算法3警示信息赋值指派算法  
输入：CNF 因子图G  
输出：输出一组变元赋值指派 $\{ x _ { 1 } , x _ { 2 } , x _ { 3 } . . . x _ { n } \}$   
Begin运行WP 算法计算所有的局部腔域 $H _ { i }$ 和冲突域 $c _ { i }$ IF $c _ { i } = 0$ ，则对变元进行权值计算IF $c _ { i } = 1$ IF $H _ { i } > 0$ ，则 $x _ { i } = 1$ IF $H _ { i } < 0$ ，则 $x _ { i } = 0$ ELSE $H _ { i } = 0$ ，则对变元进行权值计算返回变元赋值指派

# 2.2变元权值计算

在迭代运算时，基础的警示传播算法只对冲突域 $c _ { i } = 0$ ，且局部腔域 $H _ { i } > 0$ 的变元赋值为1，局部腔域 $H _ { i } < 0$ 的变元赋值为0，而对于冲突域 $c _ { i } = 1$ 的变元和 $c _ { i } = 0$ 且 $H _ { i } = 0$ 的变元无法赋值。在求解最大可满足性问题中，变元赋值的好坏直接影响着整个算法的求解效率，正确的变元赋值可以高效求解。本文提出了一种新的启发式变元权值计算，通过权值计算来确定该变元的赋值。

对于未赋值的每一个变元都有一个正或负的权值，这取决于该变元的正文字和负文字出现的差异，变元的权值代表着变元为正或为负的程度。如果权值为正，则代表变元在整个CNF公式中更多地以正文字的形式出现，而不是负文字的形式出现，反之亦然。权重计算如式(8)：

$$
W _ { \nu a r } = \frac { N u m b e r ( P o s L i t ) - N u m b e r ( N e g L i t ) } { N u m b e r ( C l a u s e _ { \nu a r } ) }
$$

其中Number(PosLit)表示变元正文字出现次数，Number(NegLit)表示变元负文字出现次数， $N u m b e r ( C l a u s e _ { \nu a r } )$ 表示变元在子句中出现的次数。

算法4变元权值算法  
输入：CNF 公式  
输出：变元 $x _ { i }$ 的赋值  
BeginFor 对每一个未赋值的变元i：初始变元权值 $W _ { i } = 0$ ，找到包含变元i的所有子句Clausei并记  
录总子句数NumberiFor对每一个子句Clausei中的变元If $i > 0$ ，PosLit++Else $i < 0$ ， $N e g L i t + +$ $W _ { i } = \frac { P o s L i t - N e g L i t } { N u m b e r _ { i } }$ IF $W _ { i } > 0$ ，则返回 $x _ { i } = 1$ Else 返回 $x _ { i } = 0$

# 2.3 局部搜索算法

在局部搜索算法中，搜索过程占用整个算法的大部分时间，普遍随机搜索算法的初始解都是随机选取，会造成初始解的随机性，好的初始解可以高效的找到结果，不好的初始解会浪费很长时间且降低了算法的性能，同时还会重复地访问一些解，出现循环的现象。本文提出的变元权值的警示传播算法，可以有效得到一组初始解，对后续进行局部搜索有很大帮助。

基于变元权值的警示传播算法得到一组变元的赋值，由此构造了一组初始解。初始解得到的子句数不一定是最优的，需要局部搜素算法进行深一步搜索。对于Max-SAT问题，目的是找到满足子句数最多的一组赋值，将得到的一组变元赋值放入到WalkSAT中进行搜索。

# 3 实验结果与分析

为了准确评估本文提出的新型变元权值计算的警示传播算法能在解决Max-SAT问题时起到很好的效果，本文对算法WWP+WalkSAT、WalkSAT、SA、GA、VNS-GA、CCLS2akms、CCEHC、Optirise6-in 和HS-Greedy进行了测试。其中WalkSAT、SA、GA、VNS-GA为经典的启发式算法，CCLS2-akms、CCEHC、Optirise6-in和HS-Greedy为2016年Max-SATEvalution国际竞赛的求解器。实验结果使用了2016年Max-SATEvalution国际竞赛中随机类的数据集。

表1给出了SA、WalkSAT、WWP $+$ WalkSAT、GA、VNS-GA几种算法之间的统计比较结果。采用s3v70c1000、s3v80c1000两种数据集(3-SAT实例，变元个数70和80，子句个数1000)，对满足最大子句个数的结果进行了对比实验。表中可以看出，在70个子句中的10个实例中，有7个实例都是取得最好的结果，有3个实例略差一些。在 80个子句中，只有4个实例取得最好结果，其余6个效果稍差一些。但是可以明显看出WWP+WalkSAT的效果远远高于WalkSAT，且满足的子句个数也大大提高。

表1 SA、WalkSAT、WWP+WalkSAT、GA和

VNS-GA在易解实例中实例对比

Tab.1 ComparisonofSA,WalkSAT,WWP+WalkSAT,GA and   

<html><body><table><tr><td colspan="5">VNS-GA in easily solved instances</td></tr><tr><td rowspan="2">Instance</td><td colspan="4">The number of satisfy clauses</td></tr><tr><td>SA</td><td>WalkSATWWP+WalkSAT</td><td>GA</td><td>VNS-GA</td></tr><tr><td>s3v70c1000-1</td><td>950</td><td>929 950</td><td>921</td><td>946</td></tr><tr><td>s3v70c1000-2</td><td>948</td><td>924 955</td><td>931</td><td>952</td></tr><tr><td>s3v70c1000-3</td><td>945</td><td>927 950</td><td>922</td><td>949</td></tr><tr><td>s3v70c1000-4</td><td>948</td><td>930 948</td><td>928</td><td>948</td></tr><tr><td>s3v70c1000-5</td><td>951</td><td>926 951</td><td>933</td><td>955</td></tr><tr><td>s3v70c1000-6</td><td>946</td><td>926 948</td><td>929</td><td>945</td></tr><tr><td>s3v70c1000-7</td><td>955</td><td>929 953</td><td>930</td><td>943</td></tr><tr><td>s3v70c1000-8</td><td>947</td><td>931 953</td><td>931</td><td>950</td></tr><tr><td>s3v70c1000-9</td><td>955</td><td>925 956</td><td>930</td><td>958</td></tr><tr><td>s3v70c1000-10</td><td>949</td><td>930 954</td><td>928</td><td>952</td></tr><tr><td>s3v80c1000-1</td><td>953</td><td>926 955</td><td>953</td><td>953</td></tr><tr><td>s3v80c1000-2</td><td>951</td><td>925 942</td><td>953</td><td>953</td></tr><tr><td>s3v80c1000-3</td><td>958</td><td>930 949</td><td>946</td><td>955</td></tr><tr><td>s3v80c1000-4</td><td>942</td><td>929 953</td><td>951</td><td>950</td></tr><tr><td>s3v80c1000-5</td><td>954</td><td>927 953</td><td>955</td><td>955</td></tr><tr><td>s3v80c1000-6</td><td>950</td><td>934 958</td><td>956</td><td>956</td></tr><tr><td>s3v80c1000-7</td><td>948</td><td>927 953</td><td>957</td><td>957</td></tr><tr><td>s3v80c1000-8</td><td>952</td><td>929 950</td><td>955</td><td>955</td></tr><tr><td>s3v80c1000-9</td><td>950</td><td>932 953</td><td>958</td><td>959</td></tr><tr><td>s3v80c1000-10</td><td>947</td><td>931 959</td><td>952</td><td>957</td></tr></table></body></html>

表2\~3是将SA、WalkSAT、WWP+WalkSAT、CCEHC、CCLS2akms、Optirise6-in和HS-Greedy进行了测试。实验结果使用了2016年Max-SATEvalution竞赛中随机类的数据集，其中表2中采用3-SAT实例，变元数70、90、110个，子句数700、800、900、1000、1100的数据集。每一种实例有10组数据。实验结果采用平均精度计算表示，即最大可满足子句数/实例子句数，再对10 组数据求平均值。实验表明：对于WWP+WalkSAT来说，精度达到了 $9 5 \% { \sim } 9 9 \%$ ，而CCEHC的精度在 $9 5 \%$ 到 $9 7 \%$ 。且在15种数据集中，有12个数据集WWP+WalkSAT在求解精度方面排名第一，并且与CCEHC、HS-Greedy结果相差不大，但远高于了SA、WalkSAT、CCLS2akms、Optirise6-in几种算法。说明WWP+WalkSAT算法对于求解易解算例十分有效，而且优于普通的局部搜素算法。表3中，实验采用HG-3SAT-V300-C1000、HG-3SAT-V250-C1200两种数据集(3SAT实例，300个变元，1000和1200个子句， $\alpha = 4$ ）。实验结果表明，算法CCLS2akms是无法求解该类问题的，WWP+WalkSAT的求解精度均达到了 $9 8 { \sim } 9 9 \%$ 左右，而CCEHC的精度稳定在 $9 9 \%$ 左右。WWP+WalkSAT还是略差异CCEHC，但是性能远远好于SA、WalkSAT、Optirise6-in 和HS-Greedy几种算法。在难解算例中，WWP+WalkSAT稍差于CCEHC算法，但在易解实例中，WWP+WalkSAT求解性能好于CCEHC算法。由此可以说明WWP+WalkSAT算法对求解随机Max-3-SAT的问题十分有效。

除此之外，通过5个数据集对算法WWP+WalkSAT和WalkSAT在迭代次数方面进行了对比实验。图3\~7表明，两者均进行1000次迭代，结果表明除了数据集S3v110c1000中初始结果WWP+WalkSAT略差于WalkSAT，其余四个数据集一开始WWP $+$ WalkSAT就优于WalkSAT。这是因为WalkSAT的初始解是随机赋值，当初始解赋值好的时候会优于WWP+WalkSAT，而WWP $+$ WalkSAT的初始解是通过变元权值计算得出的，所以一开始的满足子句个数就会优于WalkSAT。而随着迭代次数的增加，WWP $+$ WalkSAT满足子句的个数远远优于WalkSAT。尽管在数据集 $\mathbf { S } 3 \mathbf { v } 9 0 \mathbf { c } 9 0 0$ 中出现WalkSAT高于WWP+WalkSAT的现象，但是最后WWP+WalkSAT还是取得了不错的结果。虽然在精度上取得了不错的效果，但是WWP+WalkSAT算法的运行时间会差于WalkSAT算法，这也是该算法今后需要改进的地方。

![](images/4d7043dcf9ef3b879bc9aceb2a6b7fa80373326cb974ae87b0875a6f66d502b1.jpg)  
图3数据集：s3v70c700Fig.3Dataset: s3v70c700

![](images/14415aaacc5702c0aa96564b3753538dcfcb0951309a1384fb69fae637ade7b0.jpg)  
图4数据集： $\mathrm { s } 3 \mathrm { v } 9 0 \mathrm { c } 9 0 0$ Fig.4Dataset: s3v90c900

![](images/bcde762c6c2290ba044dfba1b596ddcfbe630e58d600450ca50f3d6e5acd546d.jpg)

![](images/71c5233164195e605358f1d40e682440aed35b0827bc1e8527992eb527990017.jpg)  
图5数据集：s3v110c1000 图6数据集：HG-3SAT-V250-C1000Fig.5Dataset:s3v110c1000 Fig.6 Dataset:HG-3SAT-V250-C100C

![](images/710558b72251cbb78a0f95e367367a1b6eab1672113c3a6f833d428e59e7fefd.jpg)  
图7数据集：HG-3SAT-V300-C1200Fig.7Dataset:HG-3SAT-V300-C1200

# 4 结束语

本文设计基于变元权值计算的警示传播算法WWP+

WalkSAT，对其算法进行了精度分析，实验表明该算法对易解Max-3-SAT问题还是难解Max-3-SAT问题都具有较好的优势，而且也打破了信息传播算法求解的局限性，其结果对于以后的理论研究提供了很大的参考价值。与此同时该算法也可用于解决不同领域的实际问题，在组合拍卖车辆调度、机器人路径规划、资源配置和网络社交分析等方面有广阔的应用前景。但是由于使用了基于变元权值计算的警示传播算法增加了整个计算的复杂度因而消耗了时间，后续的研究将会在算法的变元剪枝策略以及其他减少时间效率的方法入手研究。

<html><body><table><tr><td colspan="9">衣2 SA、 WaikSAl CCLSzakms、 Optirise6-in 和HS-Greedy 往易解实例中实验对比 Comparison ofSA、walksat、WWP+walksat、CCEHC、CCLS2akms、Optirise6-in and HS-Greedyin easily solved instances</td></tr><tr><td rowspan="2">Tab.2 Instance</td><td rowspan="2"></td><td colspan="7">Precision(The number of satisfy clauses /clauses)</td></tr><tr><td>Number SA</td><td>WalkSAT</td><td>WWP+WalkSAT</td><td>CCLS2akms</td><td>CCEHC</td><td>Optirise6-in</td><td>HS-Greedy</td></tr><tr><td>s3v70c700</td><td>10</td><td>95%</td><td>92%</td><td>96%</td><td>93%</td><td>97%</td><td>86%</td><td>96%</td></tr><tr><td>s3v70c800</td><td>10</td><td>95%</td><td>93%</td><td>96%</td><td>93%</td><td>96%</td><td>87%</td><td>96%</td></tr><tr><td>s3v70c900</td><td>10</td><td>95%</td><td>92%</td><td>96%</td><td>93%</td><td>95%</td><td>86%</td><td>95%</td></tr><tr><td>s3v70c1000</td><td>10</td><td>95%</td><td>93%</td><td>95%</td><td>93%</td><td>96%</td><td>88%</td><td>94%</td></tr><tr><td>s3v70c1100</td><td>10</td><td>94%</td><td>93%</td><td>95%</td><td>93%</td><td>94%</td><td>88%</td><td>94%</td></tr><tr><td>s3v90c700</td><td>10</td><td>96%</td><td>94%</td><td>97%</td><td>59%</td><td>97%</td><td>86%</td><td>96%</td></tr><tr><td>s3v90c800</td><td>10</td><td>96%</td><td>94%</td><td>96%</td><td>59%</td><td>97%</td><td>86%</td><td>96%</td></tr><tr><td>s3v90c900</td><td>10</td><td>95%</td><td>93%</td><td>96%</td><td>59%</td><td>96%</td><td>87%</td><td>95%</td></tr><tr><td>s3v90c1000</td><td>10</td><td>95%</td><td>93%</td><td>96%</td><td>59%</td><td>96%</td><td>88%</td><td>96%</td></tr><tr><td>s3v90c1100</td><td>10</td><td>95%</td><td>93%</td><td>96%</td><td>59%</td><td>96%</td><td>90%</td><td>96%</td></tr><tr><td>s3v110c700</td><td></td><td>97%</td><td>95%</td><td>97%</td><td></td><td>97%</td><td>86%</td><td>97%</td></tr><tr><td>s3v110c800</td><td>10</td><td>97%</td><td>95%</td><td>99%</td><td>60%</td><td>97%</td><td>86%</td><td>97%</td></tr><tr><td>s3v110c900</td><td>10</td><td>97%</td><td>95%</td><td>98%</td><td>60%</td><td>97%</td><td></td><td>97%</td></tr><tr><td>s3v110c10O0</td><td>10</td><td>97%</td><td>95%</td><td>97%</td><td>60%</td><td></td><td>88%</td><td>96%</td></tr><tr><td>s3v110c1OO0</td><td>10 10</td><td>97%</td><td>95%</td><td>98%</td><td>60% 60%</td><td>96% 97%</td><td>88% 87%</td><td>97%</td></tr><tr><td colspan="9">表3 SA、WalkSAT、WWP+WalkSAT、CCEHC、CCLS2akms、Optirise6-in 和 HS-Greedy 在难解实例中实验对比</td></tr><tr><td colspan="9">Tab.3 Comparison of SA、walksat、 WWP+walksat、CCEHC、CCLS2akms、 Optirise6-in and HS-Greedyin difficultly solved instances</td></tr><tr><td colspan="3">Instance</td><td>SA WalkSAT</td><td>WWP+WalkSAT</td><td>The number of unsatisfy clauses CCEHC</td><td>CCLS2akms</td><td>Optirise6-in</td><td>HS-Greedy</td></tr><tr><td colspan="3">HG-3SAT-V250-C1000-1</td><td>23 64</td><td>9</td><td>5</td><td>N/A</td><td>138</td><td>12</td></tr><tr><td colspan="3">HG-3SAT-V250-C1000-2</td><td>25 66</td><td>10</td><td>6</td><td>N/A</td><td>122</td><td>13</td></tr><tr><td colspan="3">HG-3SAT-V250-C1000-3</td><td>27 64</td><td>9</td><td>6</td><td>N/A</td><td>129</td><td>10</td></tr><tr><td colspan="3">HG-3SAT-V250-C1000-4</td><td>28</td><td>61 8</td><td>5</td><td>N/A</td><td>115</td><td></td></tr><tr><td colspan="3">HG-3SAT-V250-C1000-5</td><td>24</td><td>69 10</td><td>6</td><td>N/A</td><td>110</td><td>12</td></tr><tr><td colspan="3">HG-3SAT-V250-C1000-6</td><td>27</td><td>60 4</td><td></td><td></td><td></td><td>11</td></tr><tr><td colspan="3">HG-3SAT-V250-C1000-7</td><td>23</td><td>66 6</td><td>6</td><td>N/A</td><td>128</td><td>14</td></tr><tr><td colspan="3">HG-3SAT-V250-C1000-8</td><td>26</td><td>64 10</td><td>6</td><td>N/A</td><td>120</td><td>14</td></tr><tr><td colspan="3">HG-3SAT-V250-C1000-9</td><td>22</td><td>65 9</td><td>5</td><td>N/A</td><td>123</td><td>13</td></tr><tr><td colspan="3">HG-3SAT-V250-C1000-10</td><td>27</td><td>68 5</td><td>7</td><td>N/A</td><td>115</td><td>12 13</td></tr><tr><td colspan="3">HG-3SAT-V300-C1200-1</td><td>29</td><td>68 13</td><td>6</td><td>N/A</td><td>114</td><td>18</td></tr><tr><td colspan="3">HG-3SAT-V300-C1200-2</td><td>28</td><td>67 10</td><td>6 6</td><td>N/A N/A</td><td>156 155</td><td>20</td></tr><tr><td colspan="3">HG-3SAT-V300-C1200-3</td><td>25</td><td>70 13</td><td>7</td><td>N/A</td><td>151</td><td>15</td></tr><tr><td colspan="3">HG-3SAT-V300-C1200-4</td><td>31</td><td>72 4</td><td>6</td><td>N/A</td><td>134</td><td>16</td></tr><tr><td colspan="3">HG-3SAT-V300-C1200-5</td><td>25</td><td>65 4</td><td>6</td><td>N/A</td><td>126</td><td>15</td></tr><tr><td colspan="3">HG-3SAT-V300-C1200-6</td><td>27</td><td>71 3</td><td>7</td><td>N/A</td><td>151</td><td>14</td></tr><tr><td colspan="3">HG-3SAT-V300-C1200-7</td><td>25</td><td>68 6</td><td>6</td><td>N/A</td><td>141</td><td>16</td></tr><tr><td colspan="3"></td><td>28</td><td>60</td><td>7</td><td>N/A</td><td>133</td><td>15</td></tr><tr><td colspan="3">HG-3SAT-V300-C1200-8</td><td>31</td><td>72</td><td>5 5</td><td>N/A</td><td>149</td><td>17</td></tr><tr><td colspan="3">HG-3SAT-V300-C1200-9 HG-3SAT-V300-C1200-10</td><td>26</td><td>69</td><td>7</td><td>7 6 N/A</td><td>155</td><td>18</td></tr><tr><td colspan="3"></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

[1]王熙照，贺毅朝．求解背包问题的演化算法[J].软件学报，2017,28 (1):1-16.(Wang Xizhao,He Yichao.Evolutionary algorithms for knapsack problems [J]. Journal of Software,2017,28(1): 1-16.)   
[2]Gunduz M,Aslan M.DJAYA:A discrete Jaya algorithm for solving traveling salesman problem [J].Applied Soft Computing,2021,105: 107275. Crane Path Planning in Discretized Polar Space [J].Journal of Construction Engineering and Management,2021,147(5): 04021036.   
[4]王晓峰，于卓，赵健，等．基于大规模图的最大团问题算法分析 [J/OL].计算机工程:1-15 [2022-03-11].DOI:10.19678/j.issn.1000- 3428.0063092.   
[5]Masato,Suzuki,Yoshiyuki,et al. Statistical mechanics of the minimum vertex cover problem in stochastic block models.[J].Physical review.E, 2019,100(6-1):62101-62101.   
[6]何琨，郑迥之．最大可满足性问题的算法研究综述[J]．华中科技大 学学报：自然科学版，2022,50(02):82-95.DOI:10.13245/j.hust. 220214.   
[7]Aiello A,Burattini E,Massarotti A.The Complexity of Theorem Proving Procedures [J].Rairo Informat Théor,1977,11(1):75-82.   
[8]刘燕丽，黄飞，张婷．基于环型扩展推理规则的 MaxSAT完备算法 [J]．南京大学学报：自然科学，2015,51(04):762-771.DOI:10. 13232/j.cnki. jnju.2015.04.014.   
[9]Li Chumin,Xu Zhenxing,Coll J,et al. Combining Clause Learning and Branch-and-Bound for MaxSAT [C]// Proc of the International Conference on Principles and Practice of Constraint Programming. Montpellier: Springer, 2021:38:1-38:18   
[10] Morgado A,FHeras,Liffiton M,et al.Iterative and core-guided MaxSAT solving:A survey and assessment[J].Constraints,2013,18 (4): 478-534.   
[11]Li Chumin,Felip Manya,Nouredine Ould Mohamedou N O,et al. Resolution-based lower bounds in MaxSAT[J].Constraints,201o,15(4).   
[12]Heras F,Larrosa J,Oliveras A.MiniMaxSat:a new weighted Max-SAT solver [C]// Springer Berlin Heidelberg. Springer Berlin Heidelberg, 2007.   
[13] Johnson D S.Approximation algorithms for combinatorial problems [J]. Journal of Computer& System Sciences,1974.   
[14] Park S,Shin J.Convergence and correctness of max-product belief propagation for linear programming [J].Siam Journal on Discrete Mathematics,2017,31(3):2228-2246.   
[15] Chu Yi,Luo Chuan,Cai Shaowei,et al.Empirical investigation of stochastic local search for maximum satisfiability[J].中国计算机科学 前沿：英文版,2019,13(1):13.   
[16]王晓峰，许道云．警示传播算法收敛的充分条件[J].软件学报， 2016,27(12):3003-3013.DOI:10.13328/j.cnki. jos.004940.   
[17]王晓峰，许道云，杨德仁，姜久雷，李强，刘欣欣．可满足性问题中 信念传播算法的收敛性分析[J]．软件学报,2021,32(05):1360-1372. DOI:10.13328/j.cnki. jos.005844.   
[18] Shi X, Schonfeld D,Tunineti D.Message error analysis of loopy belief propagation [C]// 2010 IEEE International Conference on Acoustics, Speech and Signal Processing.IEEE,2010:2078-2081.   
[19]王晓峰，许道云，韦立．随机可满足实例集上警示传播算法的收敛 性[J].软件学报,2013,24(01):1-11.   
[20] Braunstein A,Mezard M, Zecchina R. Survey propagation: an algorithm for satisfiability[J].Random Structures& Algorithms,2010,27(2):201- 226.   
[21]Layeb A.A new greedy randomized adaptive search procedure for solving the maximum satisfiability [J].International Journal of Operational Research,2013,17(3):1-17.