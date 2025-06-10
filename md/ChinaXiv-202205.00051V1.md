# 融入教育心理学的 SBO 算法\*

张雨婷，刘勇(上海理工大学 管理学院，上海 200093)

摘要：针对 SBO(SchoolBasedOptimization)算法搜索性能差、易陷入局部最优等缺陷，提出融入教育心理学的 SBO算法(SBO based on Educational Psychology，SBO-EP)。在教阶段，引入“最近发展区"理论，对学生进行分组动态教学，提高算法的探索能力；引用"成就动机"理论加入自学阶段，针对每组学生的成就动机设计动态自学方式，提高算法的开发能力；在每轮学习过程结束后参考“同伴效应"设置班级重组操作，增加解的多样性。采用40个CEC2021测试函数和20个其他类型测试函数进行数值实验，并将 SBO-EP算法与蚁群优化算法、基于球形矢量的粒子群优化算法、阿基米德优化算法、灰狼优化算法、教与学优化算法、融合认知心理学的教与学优化算法、学生心理学优化算法进行对比分析。结果表明 SBO-EP 算法在收敛速度、寻优精度及稳定性上优势明显。最后，对3种策略的组合进行对比实验，验证了改进策略的有效性。

关键词：SBO算法；最近发展区理论；成就动机理论；同伴效应 中图分类号：TP18 doi:10.19734/j.issn.1001-3695.2022.02.0080

# SBO algorithm integrated into educational psychology

Zhang Yuting, Liu Yong† (Business School,University ofShanghai for Science&Technology,Shanghai 20o93,China)

Abstract: Absrtact: Aiming at the shortcomings of SBO(Schol Based on Optimization)algorithm,such as poor search performance and local optimization,this paper proposed SBO algorithm integrated with educational psychology(SBO based Educational Psychology,SBO-EP).The teaching stage used the theoryof "zoneof proximal development" tocarryout dynamic teaching for students in groups to improve theexplorationabilityof algorithms; It introduced the theoryof "achievement motivation" into the self-study stage,and designed dynamic self-study methods according to theachievement motivation ofeach groupof students to improve the development abilityof algorithms; After each round oflearningprocess, refer to the "peer efect" theory,tosetuptheclassreorganizationoperationtoincrease the diversityofsolutions.This paper used 40 CEC2021 test functionsand20 other typesof test functions for numerical experiments,and compared SBO-EP algorithm with antcolony optimization algorithm，spherical vector-based particle swarm optimization,Archimedes optimization algorithm,gray wolf optimization algorithm,teachingand learning algorithm,cognitive psychology teachinglearning-based optimizationand student psychologybased optimization algorithm.Theresults show that SBO-EPalgorithm has obviousadvantages in convergence speed，optimizationaccuracyand stabity.Finalyconducted a comparative experiment on the combination of the three strategies, verify the effectiveness of the improved strategy.

Key words: SBO algorithm; zone of proximal development theory; achievement motivation theory; peer effect

# 0 引言

SBO 算法[1](School Based Optimization Algorithm, SBO)是Farshchin等于2018年提出的一种新型元启发式算法。目前存在的元启发式算法主要包括受生物群体社会性或自然现象规律启发而开发的优化算法，如遗传算法[2](Geneticalgorithm,GA)、模拟退火算法[3](Simulated Annealing,SA)等。此外，人类群体具备有意识改造自身行为的能力，相对普通生物更加智能，因此，模拟人类群体智能行为而发展的元启发式优化算法也逐渐成为当前研究重点，如教与学优化 算 法[4](Teaching Learning-Based Optimization,TLBO)、头脑风暴优化算法[5](Brain StormOptimization,BSO)等。

SBO算法便是基于人类群体智能行为开发的元启发式算法。该算法受学校内多班级教学模式的启发，拓展了教与学优化算法中的单一课堂教学模式，提出多班级协作教学的优化模式。在多班级协作教与学的模式下，各班级教师可以被分配到其他班级进行教学活动，从而在整个学校分享并传播知识。

由于SBO算法的提出时间较新，目前对于该算法的研究较少，主要用于解决实际优化问题。其中，Farshchin 等[1将SBO 算法应用于钢框架设计优化问题，求解几个基准的钢框架优化问题，验证了SBO 算法的鲁棒性和高效性；Degertekin等[应用 SBO 算法进行钢框架的抗震优化设计；Abdelghany等[7]使用SBO算法进行太阳能电池的参数估计。

目前国内外对SBO 算法的研究主要集中于解决优化问题，在改进算法缺陷，提高算法优化性能方面仍需要进一步的研究。本文针对SBO算法搜索能力差及易陷入局部最优等缺陷，引入教育心理学的相关理论，设计教策略、自学策略及班级重组策略，提出了基于教育心理学的SBO算法(SBObased on Educational Psychology,SBO-EP)，进一步提高了该算法的探索和开发能力并优化了算法的求解精度与收敛速度

# 1 SBO 算法

常见的元启发式算法通过随机生成一个潜在解的初始群体，然后在一个系统的优化过程中逐步提高群体的整体适应度，这种方式只允许群体内部协作。更复杂的方法是利用一系列独立的并行群体进行协作，从而扩展算法的探索能力并提高算法的整体效率。这种多种群协作的方法包含两个阶段，第一阶段采用独立的元启发式方法探索不同群体区域的搜索空间，第二阶段探索子区域内最有前途的解方案。

SBO算法便是这种基于多种群协作的两阶段优化算法第一阶段通过教师引导探索各独立班级内部，第二阶段再重点寻找最有前途学生。在一般的多种群协作的两阶段算法中，通常面临第一阶段终止准则选择的问题，需要针对特定参数调优，对参数具有依赖性，并且增加了算法的复杂度。SBO 算法针对这一问题引入多班级协作框架[8]，解决了终止准则中参数复杂性的问题，具有参数少、搜索能力强等优势。

SBO算法中教与学的互动机制为：首先进行各班级教师选拔并组成优秀教师团体，其次使用轮盘赌选择法为各班级分配教师，在班级内部进行教师与学生的互动学习，最后班级内部学生之间进行互动学习。

在SBO算法中，每个候选解表示各班级中的学生个体，解分量分别表示各个科目，一轮迭代表示一次教与学的过程。SBO算法的搜索过程包括教师分配、教阶段和学阶段，算法通过三个过程的联合作用，逐步实现班级水平的提高。

# 1.1教师分配

在 SBO算法的整个教学过程中，联结各班级的关键环节是通过分配教师来完成各个班级教与学的协同。在教师分配过程中，首先比较各个班级内学生个体的适应度值，分别选出班级最优生，构成一支优秀教师团队；其次通过轮盘赌选择机制依次从这批教师中随机选择一名教师分配到各班级中，执行教学任务。使用轮盘赌选择法进行教师分配，在随机分配的基础上，保证团队中的优秀教师能以更大概率进入班级教学。通过优秀教师在多个班级间的知识传授，提高了学生的学习效率，从而增加解的多样性。

# 1.2 教阶段

在所有班级均分配一名教师后，教师在所属的各个班级内独立进行知识传授，学生群体通过学习教师传授内容来完善并提高自身水平。

在每个包含N个学生的独立班级内，学生个体 $X _ { i } / i \in N )$ 在自身已掌握知识的基础上，结合教师传授的知识进行学习，在该学习过程中，学生尽量向教师水平靠拢，学习后的更新方程如式(1)：

$$
X _ { _ { i , n e w } } ^ { D } = X _ { _ { i , o l d } } ^ { D } + \Delta _ { i }
$$

其中， $X _ { _ { i , o l d } } ^ { D }$ 、 $X _ { _ { i , n e w } } ^ { D }$ 分别表示教学前后学生i在科目 $\mathrm { ~ D ~ }$ 的水平，$\Delta _ { i }$ 表示学生i通过课堂教学所汲取的知识，使用教师 $X _ { \mathit { T e a c h e r } }$ 与班级平均值 $M$ 的差值表示，如式(2):

$$
\Delta _ { i } = r \times ( X _ { \mathit { T e a c h e r } } - T F \times M )
$$

其中， $T F$ 为教学因子，用于描述学生从课堂教学中获取知识的程度，取值为1或2，即 $T F = r o u n d [ I + r a n d ( 0 , ~ I ) ]$ r为(0,1)间的随机数。这里，使用学生个体的适应度值 $F _ { i }$ 来描述班级平均水平 $M$ ，这种方式的搜索效率优于传统计算班级水平的加权平均值的方式[9]，见式(3)：

$$
M = { \frac { \displaystyle \sum _ { i = 1 } ^ { N } { \frac { X _ { i } } { F _ { i } } } } { \displaystyle \sum _ { i = 1 } ^ { N } { \frac { 1 } { F _ { i } } } } }
$$

# 1.3 学阶段

学生群体在教阶段学习教师传授的知识后，进入学阶段，这一阶段为学生个体之间的知识交流与分享，通过学习他人以多方面提高自身的水平。

在学阶段，学生i随机选择班级内另外一位学生j进行学习和交流，同时，综合自身已掌握的知识情况，进行学习更新，更新方程如式(4):

$$
X _ { i , n e w } = \{ \begin{array} { l l } { X _ { i , o l d } + r _ { i } ( X _ { i , o l d } - X _ { j , o l d } ) , F ( X _ { i , o l d } ) < F ( X _ { j , o l d } ) } \\ { X _ { i , o l d } + r _ { i } ( X _ { j , o l d } - X _ { i , o l d } ) , F ( X _ { j , o l d } ) < F ( X _ { i , o l d } ) } \end{array} \}
$$

# 2 SBO-EP 算法

SBO算法在复杂函数优化问题上，仍存在开发及探索能力不足，且易陷入局部最优的缺陷，算法的自适应探索能力及全局搜索能力有待提高。因此，如何改进算法的上述缺陷，成为提升算法优化性能的关键问题。

在教育心理学领域，Ausubel在有意义接受学习理论中将学习区分为“接受学习”与“发现学习”两种方式[10]。本文针对SBO算法探索能力不足的缺陷，在“接受学习”方式所对应的教阶段引入“最近发展区”理论，提出分组教学的方法；针对算法开发能力不足，对应“发现学习”方式，引入“成就动机”理论，提出分组自学阶段；同时，在上述两阶段引入习惯化动态学习因子，从而自适应提高算法的搜索能力；最后，针对算法易陷入局部最优的缺陷，参考“同伴效应”理论，采用班级重组操作来增加解的多样性，提高算法全局搜索能力。

# 2.1基于“最近发展区”理论的教阶段

维果茨基提出的“最近发展区”理论认为，学生的发展包括现有水平和可能发展水平，两种水平之间的差异就是“最近发展区”[II]。教学过程应着眼于学生的最近发展区，通过教师引导，逐步消除这种差异，从而进一步提高学生水平。国内学者王文静提出依据“最近发展区”理论建立新型“因材施教”观，教育者应该充分了解学生的实际发展水平与潜在发展水平，通过寻找其最近发展区，引导学生向潜在的最高水平发展[12]。“最近发展区”及相关理论的提出，致力于挖掘学生发展的潜力，为学生创造了提高的区间，能够在教和学的互动中逐步激发学生水平，从而促进学生更好更快地向更高水平发展。

本文受上述理论及其作用的启发，将教师水平与学生现有水平之间的差异定为“最近发展区”，即学生通过接受教师传授知识所能提升的潜力区间，实行“因材施教”方式，以促进不同的学生以各自的学习方式快速向教师水平靠拢。同时参考文献[13]提出的分组教学优化算法(Group Teaching OptimizationAlgorithm，GTOA)，将教阶段的单一教模式改进为分组教模式。以班级平均成绩为标准，采用“组间异质，组内同质”的分组原则，将学生分为优秀生和普通生两组，分别为两组学生的“最近发展区”设计动态差异性教方案，发掘两组学生的潜力，以提高班级整体成绩。其中，优秀生学习水平整体较优，接受知识速度较快，相对“最近发展区”较小，因此，对于优秀生组，教师的教学精力能够兼顾引导优秀生成绩提升与提升班级平均成绩。以最小优化问题为例，优秀生组的动态教学更新方程如式(5)：

$$
\begin{array} { r l } & { X _ { i , n e w } = w ^ { * } X _ { i , o l d } + r ( X _ { T e a c h e r } - T F ^ { * } ( r ^ { * } M + r ^ { * } X _ { i , o l d } ) ) } \\ & { i f F ( X _ { i , o l d } ) \leq F ( M ) } \end{array}
$$

普通生的潜在发展水平较高，“最近发展区”空间相对较大，因此，教师主要倾向于将教学精力放在引导该组学生达到潜在成绩上。普通生组的动态教学更新方程如式(6)：

$$
X _ { i , n e w } = w ^ { * } X _ { i , o l d } + r ^ { * } T F ^ { * } ( X _ { T e a c h e r } - X _ { i , o l d } ) , i f F ( X _ { i , o l d } ) > F ( M )
$$

在教师引导逐步消除“最近发展区”的过程中，需要考虑“习惯化原则”。引导学生个体接受新知识是一个循序渐进的过程，在教初期，学生需要一定的适应期磨合学习节奏，此时的学习状态主要依赖自身的原始水平；随着教过程深入，学生逐渐适应新的学习节奏，此时依赖自身水平的程度逐渐降低，接受新知识的比例逐渐增加。因此，在上述教过程中引入动态学习因子 $w$ 模拟习惯化的过程，$w$ 的定义如式(7):

$$
w = 1 - \frac { 1 } { e ^ { ( 1 - \frac { t } { I t e r \displaylimits _ { - } \mathrm { m a x } + 1 } ) ^ { 2 } } }
$$

其中， $\mathbf { \Psi } _ { t }$ 表示当前迭代次数，Itermax表示最大迭代次数。

引入教育心理学中“最近发展区”理论改进的分组教阶段，模拟了现实班级中不同水平学生通过学习教师所传授的知识从而逐渐消除“最近发展区”差异，向教师水平靠拢，达到自身的潜在最高水平。表现在算法层面，即各个种群中的优解和劣解两组解进行分组优化，逐渐接近种群内的最优解。基于“最近发展区”理论的改进教阶段，对解设计潜在发展空间，并随迭代过程自适应缩小发展空间，相较于SBO算法教阶段的单一整体更新策略，有效扩大了解的搜索范围，提高了算法的探索能力。

# 2.2基于“成就动机”理论的自学阶段

Ausube1提出的“发现学习”强调学习者应该积极主动地建立新旧知识的联系，从而进行新知识的同化。本文基于此在教、学两阶段完成后加入自学阶段，以巩固与强化学生对知识的吸收。

在Atkinson提出的“成就动机”理论中，将个体成就动机分为趋向成功动机与避免失败动机[14]。趋向成功者的期望是获取成就，通常选择较高目标以获得成就感或满足感，在实际教育中，对于趋向成功者，给予难度较高的任务或较难的目标，可以激发该类学生的学习热情；避免失败者的期望是稳中求进，通常选择易达目标或简单任务以维持稳定发展，在实践中，对于该类学生，通过安排竞争性较低的目标，能够维持学生的学习状态。因此，参考成就动机理论，沿用教阶段的分组方法及习惯化原则下的动态学习因子 $w$ ，提出学生自学阶段。文献[15]提出的基于学生心理预期分组的学生心理学优化算法及文献[16]提出的依据心理控制源“内控型”、“外控性”分组的教与学优化算法，结合趋向成功者与避免失败者的期望，分别对两组学生设计更适合自身的学习目标和方式进行自我更新。其中，优秀生类比趋向成功者，期望获取成就，因此选择最优生为目标，衡量自己与最优生的差距，不断学习，以达到最优生的成就水平，更新方程如式(8):

$$
X _ { i , n e w } = w ^ { * } X _ { i , o l d } + r ( X _ { b e s t } - X _ { i , o l d } )
$$

普通生类比避免失败者，期望稳中求进、由浅入深的学习过程，因此选择以班级平均水平为目标，正视自身与平均水平的差距，打好基础，进行查缺补漏，成绩提升后再进一步寻求更高目标，更新方程如式(9):

$$
X _ { i , n e w } = w ^ { * } X _ { i , o l d } + r ( M - X _ { i , o l d } )
$$

# 2.3基于“同伴效应”的班级重组策略

Coleman提出的“同伴效应”理念，是指在一个群体中，个体会受到同伴特征和表现的影响。研究表明，在同伴效应的正面作用下，混合分班策略能够有效提高班级的整体成绩[17]。

SBO算法在学阶段的学习过程中，学生个体主要参考同一班级内其他同学的学习水平，参考样本较少，容易陷入局部最优。因此，为了使学生学习多样化，扩大同伴效应的正面引导，对各班级现有学生加入混合分班策略。在每轮迭代过程结束时，进行班级重组，新班级组成后，再

进入下一轮学习过程。

为验证班级重组操作对解多样性的影响，以Griewangk函数和Salomon函数为例，选取一班50个2维的学生个体迭代前后的对比图作为参考，如图1所示。对于上述两种函数，在首次迭代班级重组前，解的分布较为密集，范围较小，分班后解的分布比较分散，范围广，多样性显著提高，且最终迭代均可找到最优解，没有降低解的搜索效率。通过对比，可见班级重组操作显著增加了解的多样性，提高了算法的全局探索能力。

![](images/a7a06dedccf2cbca60d9b77e6b60bbc2bdbdc1561fad78f11842cc3effd9581c.jpg)  
(a)Griewangk函数一班首次迭代分布图

![](images/35bf45a0adb4890395b4972c0430acf29d8b6fec320a67ed933bdeb26d7cc33c.jpg)  
(b)f4Griewangk函数一班最终迭代分布图

![](images/33542e5728a2701df03f0477ea0297bd7c8b39fd034e5ce3961937679937ac88.jpg)  
(c)Salomon函数一班首次迭代分布图

![](images/79832e59659ab61e4704e04afb2bcbd579a7e0196bea3cd3b1dd54105da203fb.jpg)  
(d) Salomon 函数一班最终迭代分布图   
图1班级重组效果对比  
Fig.1 Comparison of class reorganization effect

# 2.4 SBO-EP 算法步骤

综上所述，本文提出的SBO-EP算法的框架如图2所示，算法具体步骤如下：

Step1:在NC个班级中，分别在搜索空间[LB，UB]内随机产生规模为 $\mathrm { N P ^ { * } D }$ 维的初始学生群体;

Step2:计算并比较各班级学生的适应度值Fitness，选取各班级最优生进入教师团队；

Step3:使用轮盘赌选择法从教师团队中选出NC位教师，分别进入NC个班级中从事教活动；

Step4:教阶段，由式(5)(6)更新学生群体；

Step5:学阶段，由式(4)更新学生群体，；

Step6:自学阶段，由式(8)(9)更新学生群体；

Step7：班级重组，将NC个班级的所有学生进行混合分班分班，重组NC个新的班级；

Step8:更新迭代次数 $\scriptstyle { \mathrm { \mathfrak { t } } } = { \mathrm { \mathfrak { t } } } + 1$ ，若满足终止条件t=Iter_max,则算法终止，输出全局最优解，否则转向Step3。

以得到00类型、01类型、10类型、11类型四种扩展组合，共计40个测试函数。其中，CEC2021的10个基准测试函数的详细信息见表2。

<html><body><table><tr><td>类别</td><td>编号</td><td>函数</td><td>定义域</td><td>最优解</td></tr><tr><td>Unimodal Function</td><td>f1</td><td>Shifted and Rotated Bent Cigar Function</td><td>[-100,10]D</td><td>100</td></tr><tr><td></td><td>f2</td><td>Shifted and Rotated Schwefel's Function</td><td></td><td>1100</td></tr><tr><td>Basic Functions</td><td>f3</td><td>Shifted and RotatedLunacek bi-Rastrigin Function</td><td>[-100,10]D</td><td>700</td></tr><tr><td rowspan="4">Hybrid Functions</td><td>f4</td><td>Expanded Rosenbrock's plus</td><td></td><td>1900</td></tr><tr><td>f5</td><td>Griewangk's Function Hybrid Function 1(N=3)</td><td></td><td>1700</td></tr><tr><td>f6</td><td>Hybrid Function 2(N=4)</td><td>[-100,10]D</td><td>1600</td></tr><tr><td>f7</td><td>Hybrid Function 3(N=5)</td><td></td><td>2100</td></tr><tr><td rowspan="3">Composition Functions</td><td>f8</td><td>Composition Function 1(N=3)</td><td></td><td>2200</td></tr><tr><td>f9</td><td>Composition Function 2 (N=4)[-100,10]D</td><td></td><td>2400</td></tr><tr><td>f10</td><td>Composition Function 3 (N=5)</td><td></td><td>2500</td></tr></table></body></html>

班级/ 多 8 78 曼?8 选择策略 8 曼教师选择 教师分配 教阶段 学阶段 自学阶段 班级重组

# 3 数值实验与分析

# 3.1实验环境与参数设置

为验证SBO-EP算法的优化性能，选取蚁群优化算法[18](AntColonyOptimization,ACO)、基于球形矢量的粒子群优化算法[19](Spherical vector-based Particle Swarm Optimization,SPSO)、阿基米德优化算法[20](ArchimedesOptimizationAlgorithm,AOA)、灰狼优化算法[21,22](Gray Wolf Optimization,GWO)、学生心理学优化算法[15](Student Psychology BasedOptimization,SPBO)、教与学优化算法[4(TLBO)、融合认知心理学理论的新型教与学优化算法[16](Cognitive PsychologyTeaching-Learning Based Optimization,CPTLBO)及 SBO 算法与 SBO-EP算法进行对比实验。分别选取CEC2021的40个函数和20个其他类型函数进行算法测试，以验证改进后算法的优越性。其中，各对比算法的参数设置见表1。

表2 CEC2021测试函数Tab.2 CEC2021 test functions  
表1算法参数设置  
Tab.1Parameter setting of the algorithms   

<html><body><table><tr><td>算法</td><td>参数设置</td></tr><tr><td>ACO</td><td>p=0.9,p=0.2</td></tr><tr><td>SPSO</td><td>n1=1.5,n2=1.5,w=1,wdamp=0.98</td></tr><tr><td>AOA</td><td>c1=2,c2=6,c3=1,c4=2,u=0.9,1=0.1</td></tr><tr><td>TLBO</td><td>TF=2</td></tr><tr><td>CPTLBO</td><td>tf=0.3</td></tr><tr><td>SBO</td><td>TF=2</td></tr><tr><td>SBO-EP</td><td>TF =round(1+rand(0,1))</td></tr></table></body></html>

本实验运行环境为64位Windows10操作系统，CPU为Intel(R)Core(TM)i5-7200U，主频为 $2 . 7 \mathrm { G H z }$ ，内存为8GB。算法采用MATLABR2020b编程实现。

# 3.2 CEC2021函数测试

在2021 年 IEEE 进化计算大会(Congress onEvolutionaryComputation，CEC)单目标参数优化竞赛中，提出了10个在10维、20维上可扩展的复杂测试函数。本文在10个基准测试函数上，扩展bias 及rotation 两种操作，若加入上述操作，记为1，否则记为0，则基准函数可

由于CEC2021的10个函数理论最优值各不相同，因此本文对各算法的寻优结果与理论最优值求差，以差值0作为各函数的最优值，以方便对比分析。此外，为保证公平性，将各算法的最大评价次数均设置为30000。其中SBO算法和SBO-EP算法设置10个班级 $^ { * } 3 0$ 名学生，其余对比算法个体均设为30。各算法分别在10维独立运行30次，通过平均值衡量算法的寻优能力，标准差反映算法的稳定性，所得实验结果如表3所示。

表3的实验结果表明，AOA算法对于10类型和11类型的 $_ { f l }$ 和 $f 9$ 两个函数，平均值和标准差为0，寻优精度和稳定性相对较优；GWO算法对于00类型的f8、10和11类型的 $_ f l$ 两个函数能够稳定地收敛到最优值；CPTLBO算法对10类型和11类型的 $_ { f l }$ 和f9两个函数及四种类型的f4和 $f 8$ 两个函数，平均值和标准差为0，寻优精度和稳定性较优；SBO 算法在10类型的 $_ f l$ 、四种类型的f8函数上，30次独立运行均能找到最优解；SPSO算法、SPBO算法、TLBO算法对所有函数均无法优化到最优解，效果较差。

本文提出的 SBO-EP算法，对于复杂度较高的CEC2021函数，在00类型和01类型的 $f 9$ 和 $f l O$ 函数30次优化平均值的数量级能够达到-300，其求解精度显著优于其他8种算法。除上述6个函数外，对于其他单峰函数、基本函数、混合函数和复合函数，30次独立实验的平均值和标准差均为0，均能收敛到最优解，验证了该算法的寻优能力和稳定性明显高于其他8种算法。

为更全面地验证SBO-EP算法的可靠性和优越性，加入统计学的检验指标。对SBO-EP算法和其他优化算法在CEC2021的40个测试函数上分别进行了显著性水平为 $5 \%$ 的Wilcoxon秩和检验。以SBO-EP算法与SBO算法的检验结果为例，计算所得 $p$ 值见表4。其中，NaN结果表示两种算法均能够收敛到最优解。结果表明，其他计算所得p 值均小于0.05，说明相较于SBO 算法，SBO-EP算法的优越性在统计上是显著的，即SBO-EP算法具有更好的寻优能力。通过统计检验，其他算法也均通过了显著性水平为 $5 \%$ 的秩和检验，由于篇幅限制，本文不再赘述。

为直观比较各算法的性能，以00 类型的 f3、f4、f6、$f 7$ 四个函数为例，绘出各算法的收敛曲线，如图3所示。根据图3的迭代曲线，可以观察到，SBO-EP算法的收敛速度较快，且在100次迭代内均能优化到较高精度，无论 是收敛速度还是收敛精度都明显优于其他算法。

表3CEC2021测试函数优化结果对比  

<html><body><table><tr><td rowspan="2">函数</td><td rowspan="2">算法</td><td colspan="8">Tab.3 Comparison of optimization results of CEC202l test functions</td></tr><tr><td>00类型 平均值</td><td>标准差</td><td>01类型 平均值</td><td>标准差</td><td>10类型 平均值</td><td>标准差</td><td>11类型 平均值</td><td>标准差</td></tr><tr><td rowspan="11">f1</td><td>ACO</td><td>1.34E+10</td><td>2.86E+09</td><td>1.55E+10</td><td>5.14E+09</td><td>1.34E+10</td><td>3.01E+09</td><td>1.53E+10</td><td>4.07E+09</td></tr><tr><td>SPSO</td><td>1.57E+09</td><td>1.13E+09</td><td>1.76E+09</td><td>1.07E+09</td><td>1.50E+09</td><td>5.76E+08</td><td>2.14E+09</td><td>1.18E+09</td></tr><tr><td></td><td>1.99E-207</td><td>0.00E+00</td><td>1.51E-135</td><td>8.25E-135</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>AOA</td><td>1.04E-111</td><td>2.47E-111</td><td>1.45E+05</td><td>2.51E+05</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>GWO</td><td>1.40E+03</td><td>2.49E+03</td><td>1.66E+03</td><td>3.45E+03</td><td>4.33E+02</td><td>6.70E+02</td><td>4.14E+03</td><td>7.54E+03</td></tr><tr><td>SPBO</td><td>2.45E+09</td><td>1.99E+09</td><td>1.81E+09</td><td>1.88E+09</td><td>2.18E+09</td><td>2.15E+09</td><td>1.68E+09</td><td>1.80E+09</td></tr><tr><td>TLBO CPTLBO</td><td>4.78E-288</td><td>0.00E+00</td><td>1.35E-215</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td></td><td>2.18E-24</td><td>9.13E-25</td><td>1.16E+02</td><td>3.73E+02</td><td>0.00E+00</td><td>0.00E+00</td><td>2.46E+02</td><td>4.23E+02</td></tr><tr><td rowspan="14">f2</td><td>SBO SBO-EP</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td></td><td>2.63E+03</td><td>2.48E+02</td><td>2.44E+03</td><td>3.17E+02</td><td>2.54E+03</td><td>3.70E+02</td><td>2.59E+03</td><td>2.46E+02</td></tr><tr><td>ACO SPSO</td><td>1.46E+03</td><td>2.64E+02</td><td>1.51E+03</td><td>3.74E+02</td><td>2.58E+03</td><td>3.50E+02</td><td>2.58E+03</td><td>2.98E+02</td></tr><tr><td>AOA</td><td>3.96E+01</td><td>1.36E+02</td><td>1.13E+02</td><td>2.64E+02</td><td>3.86E+01</td><td>1.23E+02</td><td>9.82E+01</td><td>2.67E+02</td></tr><tr><td>GWO</td><td>4.28E-01</td><td>1.02E+00</td><td>1.26E+02</td><td>1.77E+02</td><td>8.70E+00</td><td>4.09E+01</td><td>8.70E+00</td><td>4.09E+01</td></tr><tr><td>SPBO</td><td>1.10E-03</td><td>2.96E-03</td><td>3.12E-02</td><td>6.00E-02</td><td>9.15E-04</td><td>2.64E-03</td><td>1.06E-01</td><td>3.10E-01</td></tr><tr><td></td><td>1.33E+03</td><td>2.89E+02</td><td>1.47E+03</td><td>1.85E+02</td><td>1.27E+03</td><td>3.08E+02</td><td>1.39E+03</td><td></td></tr><tr><td>TLBO CPTLBO</td><td>4.36E+00</td><td>1.48E+01</td><td>1.43E+02</td><td>3.38E+02</td><td>2.91E+00</td><td>8.03E+00</td><td>1.65E+02</td><td>2.32E+02 4.17E+02</td></tr><tr><td></td><td>7.88E+00</td><td>9.39E+00</td><td>1.20E+02</td><td>8.93E+01</td><td>9.98E+00</td><td>9.30E+00</td><td>1.12E+02</td><td>8.89E+01</td></tr><tr><td rowspan="14">f3</td><td>SBO</td><td></td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>SBO-EP</td><td>0.00E+00 4.57E+02</td><td></td><td>5.33E+02</td><td></td><td>5.11E+02</td><td>9.64E+01</td><td>4.93E+02</td><td>1.00E+02</td></tr><tr><td>ACO</td><td>1.52E+02</td><td>1.16E+02 3.59E+01</td><td>1.48E+02</td><td>1.10E+02 4.23E+01</td><td>8.39E+02</td><td>4.15E+01</td><td>8.39E+02</td><td>3.97E+01</td></tr><tr><td>SPSO</td><td>1.28E+01</td><td>1.79E+01</td><td>1.99E+01</td><td>2.26E+01</td><td>1.12E+01</td><td>2.01E+01</td><td>2.01E+01</td><td>2.31E+01</td></tr><tr><td>AOA</td><td>2.81E+01</td><td>2.05E+01</td><td>3.13E+01</td><td>1.69E+01</td><td>2.64E+01</td><td>1.88E+01</td><td>2.64E+01</td><td>1.88E+01</td></tr><tr><td>GWO SPBO</td><td>1.45E-03</td><td>2.30E-03</td><td>4.33E-03</td><td>1.05E-02</td><td>2.49E-03</td><td>6.49E-03</td><td>7.32E-02</td><td>2.01E-01</td></tr><tr><td></td><td>1.71E+02</td><td>4.33E+01</td><td>1.49E+02</td><td>4.83E+01</td><td>1.68E+02</td><td>4.57E+01</td><td>1.65E+02</td><td>6.31E+01</td></tr><tr><td>TLBO CPTLBO</td><td>3.94E-01</td><td>2.16E+00</td><td>7.00E-01</td><td>2.68E+00</td><td>3.55E-02</td><td>1.94E-01</td><td>7.83E-01</td><td>3.01E+00</td></tr><tr><td></td><td>4.35E+00</td><td>6.20E+00</td><td>1.38E+01</td><td>9.10E+00</td><td>4.05E+00</td><td>5.40E+00</td><td>1.29E+01</td><td>8.60E+00</td></tr><tr><td rowspan="8">f3</td><td>SBO</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>SBO-EP</td><td>1.21E+05</td><td></td><td></td><td></td><td>1.15E+05</td><td>9.38E+04</td><td>3.60E+05</td><td>3.19E+05</td></tr><tr><td>ACO</td><td>1.80E+02</td><td>8.98E+04</td><td>2.79E+05</td><td>3.39E+05</td><td></td><td></td><td>2.26E+03</td><td></td></tr><tr><td>SPSO</td><td>5.08E-01</td><td>3.54E+02</td><td>4.68E+02</td><td>6.86E+02</td><td>2.10E+03</td><td>3.60E+02</td><td></td><td>4.68E+02</td></tr><tr><td>AOA</td><td>3.37E-01</td><td>8.33E-01 4.51E-01</td><td>2.77E-01</td><td>5.76E-01</td><td>3.70E-01 5.78E-01</td><td>6.03E-01</td><td>1.54E-01 5.78E-01</td><td>5.99E-01</td></tr><tr><td>GWO</td><td>1.02E-08</td><td></td><td>8.80E-01</td><td>8.62E-01</td><td></td><td>5.88E-01</td><td></td><td>5.88E-01</td></tr><tr><td>SPBO</td><td></td><td>4.44E-08</td><td>3.95E-06</td><td>1.94E-05</td><td>8.67E-07</td><td>3.09E-06</td><td>6.43E-04</td><td>3.20E-03</td></tr><tr><td>TLBO</td><td>7.28E+02</td><td>1.87E+03 0.00E+00</td><td>1.39E+03</td><td>3.59E+03</td><td>2.84E+02 0.00E+00</td><td>3.00E+02 0.00E+00</td><td>1.07E+03</td><td>1.92E+03</td></tr><tr><td rowspan="14">f5</td><td>CPTLBO</td><td>0.00E+00</td><td></td><td>0.00E+00</td><td>0.00E+00</td><td>1.10E+00</td><td>5.02E-01</td><td>0.00E+00 1.39E+00</td><td>0.00E+00</td></tr><tr><td>SBO SBO-EP</td><td>9.89E-01 0.00E+00</td><td>4.92E-01 0.00E+00</td><td>1.26E+00</td><td>4.87E-01</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>4.12E-01 0.00E+00</td></tr><tr><td>ACO</td><td>3.36E+07</td><td>3.98E+07</td><td>0.00E+00 1.77E+07</td><td>0.00E+00 1.80E+07</td><td>2.56E+07</td><td>2.85E+07</td><td>2.73E+07</td><td>3.00E+07</td></tr><tr><td>SPSO</td><td>9.95E+05</td><td>1.59E+06</td><td>5.93E+05</td><td>9.94E+05</td><td>7.52E+05</td><td>1.26E+06</td><td>1.20E+06</td><td>3.22E+06</td></tr><tr><td>AOA</td><td>6.54E-32</td><td>3.56E-31</td><td>1.45E+02</td><td>3.26E+02</td><td>1.30E-01</td><td>7.13E-01</td><td>7.90E+01</td><td>1.94E+02</td></tr><tr><td>GWO</td><td>4.14E-01</td><td>1.73E+00</td><td>1.75E+03</td><td>3.34E+03</td><td>1.04E-01</td><td>3.71E-01</td><td>1.04E-01</td><td>3.71E-01</td></tr><tr><td>SPBO</td><td>6.89E+01</td><td>1.34E+02</td><td>1.04E+02</td><td>2.52E+02</td><td>1.59E+02</td><td>3.25E+02</td><td>9.63E+01</td><td>2.62E+02</td></tr><tr><td>TLBO</td><td>2.05E+05</td><td>2.42E+05</td><td>1.13E+05</td></table></body></html>

续表3CEC2021测试函数优化结果对比  

<html><body><table><tr><td rowspan="2">函数</td><td rowspan="2">算法</td><td colspan="2">00类型</td><td colspan="2">01类型</td><td colspan="2">10类型</td><td colspan="2">11类型</td></tr><tr><td>平均值</td><td>标准差</td><td>平均值</td><td>标准差</td><td>平均值</td><td>标准差</td><td>平均值</td><td>标准差</td></tr><tr><td rowspan="11">f7</td><td>ACO</td><td>9.71E+06</td><td>1.78E+07</td><td>5.76E+06</td><td>5.78E+06</td><td>1.10E+07</td><td>1.94E+07</td><td>3.35E+06</td><td>4.60E+06</td></tr><tr><td>SPSO</td><td>4.61E+05</td><td>5.66E+05</td><td>3.90E+05</td><td>9.57E+05</td><td>2.70E+05</td><td>6.29E+05</td><td>7.00E+05</td><td>1.43E+06</td></tr><tr><td>AOA</td><td>7.17E-06</td><td>3.00E-05</td><td>4.78E+00</td><td>1.34E+01</td><td>8.04E-02</td><td>4.40E-01</td><td>5.18E+00</td><td>1.83E+01</td></tr><tr><td>GWO</td><td>2.18E-01</td><td>1.02E+00</td><td>8.37E+01</td><td>1.32E+02</td><td>9.69E-02</td><td>2.53E-01</td><td>9.69E-02</td><td>2.53E-01</td></tr><tr><td>SPBO</td><td>2.06E+02</td><td>6.84E+02</td><td>1.91E+02</td><td>3.44E+02</td><td>1.27E+02</td><td>2.61E+02</td><td>2.99E+02</td><td>5.26E+02</td></tr><tr><td>TLBO</td><td>2.08E+05</td><td>8.88E+05</td><td>5.14E+03</td><td>4.23E+03</td><td>1.07E+04</td><td>2.40E+04</td><td>5.46E+04</td><td>2.39E+05</td></tr><tr><td>CPTLBO</td><td>1.49E-01</td><td>4.53E-01</td><td>1.28E+00</td><td>3.90E+00</td><td>5.56E-02</td><td>2.98E-01</td><td>2.20E+00</td><td>3.59E+00</td></tr><tr><td></td><td>SBO 2.91E-02</td><td>5.91E-02</td><td>1.20E+02</td><td>8.09E+01</td><td>7.49E-02</td><td>1.22E-01</td><td>9.80E+01</td><td>6.75E+01</td></tr><tr><td rowspan="6">f8</td><td>SBO-EP</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>ACO</td><td>2.40E+03</td><td>3.08E+02</td><td>2.44E+03</td><td>3.36E+02</td><td>2.55E+03</td><td>2.56E+02</td><td>2.41E+03</td><td>3.09E+02</td></tr><tr><td>SPSO</td><td>1.11E+03</td><td>3.26E+02</td><td>1.09E+03</td><td>2.90E+02</td><td>3.30E+03</td><td>2.60E+02</td><td>3.35E+03</td><td>2.89E+02</td></tr><tr><td>AOA</td><td>5.76E+00</td><td>2.22E+01</td><td>1.33E+01</td><td>4.25E+01</td><td>2.06E+00</td><td>1.13E+01</td><td>1.36E+01</td><td>4.46E+01</td></tr><tr><td>GWO</td><td>0.00E+00</td><td>0.00E+00</td><td>2.92E+01</td><td>5.77E+01</td><td>3.03E-14</td><td>1.15E-13</td><td>3.03E-14</td><td>1.15E-13</td></tr><tr><td>SPBO</td><td>5.76E-03</td><td>1.21E-02</td><td>4.56E-02</td><td>1.46E-01</td><td>4.97E-02</td><td>2.20E-01</td><td>4.00E-01</td><td>9.77E-01</td></tr><tr><td rowspan="6">f8</td><td>TLBO</td><td>1.26E+03</td><td>2.43E+02</td><td>1.23E+03</td><td>2.54E+02</td><td>1.14E+03</td><td>2.64E+02</td><td>1.17E+03</td><td>2.73E+02</td></tr><tr><td>CPTLBO</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>SBO</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>SBO-EP</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>ACO</td><td>6.87E+02</td><td>1.36E+02</td><td>6.94E+02</td><td>9.89E+01</td><td>6.96E+02</td><td>1.01E+02</td><td>6.68E+02</td><td>1.43E+02</td></tr><tr><td>SPSO</td><td>1.33E+02</td><td>3.72E+01</td><td>1.51E+02</td><td>5.38E+01</td><td>2.55E+03</td><td>5.75E+01</td><td>2.56E+03</td><td>4.80E+01</td></tr><tr><td rowspan="10">f9</td><td>AOA</td><td>2.96E-16</td><td>1.62E-15</td><td>2.96E-16</td><td>1.62E-15</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>GWO</td><td>9.18E-15</td><td>2.84E-15</td><td>8.88E-15</td><td>0.00E+00</td><td>5.00E-13</td><td>1.39E-13</td><td>5.00E-13</td><td>1.39E-13</td></tr><tr><td>SPBO</td><td>4.85E-02</td><td>5.61E-02</td><td>1.02E-01</td><td>1.19E-01</td><td>9.92E-01</td><td>2.16E+00</td><td>5.23E-01</td><td>8.03E-01</td></tr><tr><td>TLBO</td><td>1.98E+02</td><td>7.43E+01</td><td>2.12E+02</td><td>7.28E+01</td><td>1.93E+02</td><td>8.03E+01</td><td>1.97E+02</td><td>7.60E+01</td></tr><tr><td>CPTLBO</td><td>2.96E-16</td><td>1.62E-15</td><td>2.23E-48</td><td>1.22E-47</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>SBO</td><td>8.88E-15</td><td>0.00E+00</td><td>8.88E-15</td><td>0.00E+00</td><td>2.73E-13</td><td>2.27E-13</td><td>3.49E-13</td><td>1.96E-13</td></tr><tr><td>SBO-EP</td><td>4.89E-315</td><td>0.00E+00</td><td>1.12E-312</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>ACO</td><td>1.01E+03</td><td>4.60E+02</td><td>9.57E+02</td><td>4.14E+02</td><td>1.04E+03</td><td>4.14E+02</td><td>9.36E+02</td><td>4.12E+02</td></tr><tr><td>SPSO</td><td>1.62E+02</td><td>5.40E+01</td><td>1.52E+02</td><td>4.70E+01</td><td>2.65E+03</td><td>5.76E+01</td><td>2.66E+03</td><td>5.30E+01</td></tr><tr><td>AOA</td><td>9.00E+00</td><td>2.75E+01</td><td>3.23E+01</td><td>4.70E+01</td><td>1.75E+01</td><td>3.59E+01</td><td>3.78E+01</td><td>4.74E+01</td></tr><tr><td>GWO</td><td>5.44E+01</td><td>1.48E+01</td><td>6.96E+01</td><td>8.84E+00</td><td>5.24E+01</td><td>1.40E+01</td><td>5.24E+01</td><td>1.40E+01</td></tr><tr><td>f10</td><td>SPBO</td><td>1.40E-01</td><td>1.53E-01</td><td>9.09E-02</td><td>9.49E-02</td><td>2.25E-01</td><td>2.97E-01</td><td>2.44E-01</td><td>3.84E-01</td></tr><tr><td>TLBO</td><td></td><td>1.32E+02</td><td>7.68E+01</td><td>1.30E+02</td><td>3.62E+01</td><td>1.17E+02</td><td>4.25E+01</td><td>1.28E+02</td><td>3.66E+01</td></tr><tr><td>CPTLBO</td><td></td><td>3.61E+01</td><td>2.40E+01</td><td>6.54E+01</td><td>2.33E+01</td><td>3.58E+01</td><td>2.38E+01</td><td>6.39E+01</td><td>2.31E+01</td></tr><tr><td>SBO</td><td></td><td>4.82E+01</td><td>7.55E+00</td><td>6.71E+01</td><td>8.76E+00</td><td>4.93E+01</td><td>4.41E-01</td><td>6.51E+01</td><td>9.98E+00</td></tr><tr><td>SBO-EP</td><td></td><td>1.44E-315</td><td>0.00E+00</td><td>2.22E-315</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr></table></body></html>

# 3.3 高维函数测试

除了采用40个CEC2021函数外，还选取了20个其他类型的测试函数进行算法测试，以验证该算法在高维测试函数上的寻优效果。其中20个测试函数的具体信息见表5。

用SBO-EP算法与其余6个优化算法分别求解上述20个测试函数，在1000维独立运行30次，各算法的最大评价次数均设置为30000，所得结果的最优值、平均值、最差值、标准差四个性能评估结果如表6所示。

根据表6的实验结果，从算法的寻优精度分析，ACO算法对F15、F20两个函数寻优效果较好，其中F15可以稳定收敛到最优值；SPSO算法对F13和F15能够收敛到最优解，对 $F l 3$ 的优化结果相对稳定；AOA算法对 $_ { F I }$ 、$F 2$ 、F5、F11、F14、F17能够找到最优解，其中对于 $_ { F I }$ 、$F 2$ ， $F I 7$ 三个函数，收敛比较稳定，30次独立运行均能到达最优值，整体的求解精度相对较高；GWO寻优能力差，对20个函数均无法找到最优解，且数量级较大；SPBO算法对于函数 $F I \ 、 F I 2 、 F I 3 、 F I 5 、 F 2 0$ 能够收敛到最优值，但优化 $F I$ 和 $F 2 0$ 时标准差较大，不够稳定；TLBO算法的寻优能力较差，仅对F12有机会收敛到最优值；CPTLBO算法对于 $F I$ 、 $F 2$ 、F15、F17能够稳定收敛到最优解，对F11有机会收敛到最优解，但标准差较大，整体优化效果较好；SBO 算法仅对 $F 2$ 函数能够稳定地找到最优值，整体优化效果处于劣势。

表4Wilcoxon 秩和检验结果Tab.4 Wilcoxon Rank test result  

<html><body><table><tr><td rowspan="2">函数</td><td colspan="4">SBO-EP/SBO</td></tr><tr><td>00类型</td><td>01类型</td><td>10类型</td><td>11类型</td></tr><tr><td>f1</td><td>1.21E-12</td><td>1.21E-12</td><td>NaN</td><td>1.21E-12</td></tr><tr><td>f2</td><td>1.21E-12</td><td>1.21E-12</td><td>1.21E-12</td><td>1.21E-12</td></tr><tr><td>f3</td><td>1.21E-12</td><td>1.21E-12</td><td>1.21E-12</td><td>1.21E-12</td></tr><tr><td>f4</td><td>1.21E-12</td><td>1.2E-12</td><td>1.21E-12</td><td>1.21E-12</td></tr><tr><td>f5</td><td>2.37E-12</td><td>5.22E-12</td><td>5.58E-3</td><td>1.21E-12</td></tr><tr><td>f6</td><td>1.21E-12</td><td>1.21E-12</td><td>1.21E-12</td><td>1.21E-12</td></tr><tr><td>f7</td><td>1.21E-12</td><td>1.72E-12</td><td>1.21E-12</td><td>1.21E-12</td></tr><tr><td>f8</td><td>NaN</td><td>NaN</td><td>NaN</td><td>NaN</td></tr><tr><td>f9</td><td>1.21E-12</td><td>1.21E-12</td><td>5.19E-07</td><td>1.47E-09</td></tr><tr><td>f10</td><td>3.02E-11</td><td>1.21E-12</td><td>1.21E-12</td><td>1.21E-12</td></tr></table></body></html>

![](images/4c36697b8e4f19a64f2bf03699841cd009e13a679969e18288d8445568bcedd5.jpg)  
图3 CEC2021函数收敛曲线  
Fig. 3 CEC2021 function convergence curve

实验结果表明，在30次独立运行中，SBO-EP算法仅对F12、F18两个函数无法收敛到最优解，对F12函数未达到稳定收敛到最优值，但仍可以达到较高的数量级，且明显优于其他8种算法。其中对于 $F 7$ 函数，在AOA、SPBO、TLBO、SBO算法都无法跳出局部最优且初始优化值较大的情况下，SBO-EP算法也能快速收敛到最优解，体现了该算法具有较快的收敛速度和较强的探索能力，且不依赖初始解。除上述2个函数外，其余测试函数的四个评价指标都为0，可见该算法的求解精度及稳定性对比于其他8种优化算法具有显著优势。在20个测试函数上对SBO-EP算法和其他优化算法进行显著性水平为 $5 \%$ 的秩和检验。结果表明，除对比算法和SBO-EP算法均达到最优解时出现N/A外，SBO-EP算法在秩和检验过程中计算的 $p$ 值均小于0.05。说明SBO-EP算法相较其他优化算法的优越性在统计上是显著的。

Tab.5 1000-dimensional test functions   

<html><body><table><tr><td>编号</td><td>函数名</td><td>定义域</td><td>最优值</td></tr><tr><td>F1</td><td>Griewangk</td><td>[-100,100]D</td><td>0</td></tr><tr><td>F2</td><td>Rastrigin</td><td>[-5.12,5.12]D</td><td>0</td></tr><tr><td>F3</td><td>Sum Squares</td><td>[-100,100]D</td><td>0</td></tr><tr><td>F4</td><td>Sphere</td><td>[-100,100]D</td><td>0</td></tr><tr><td>F5</td><td>Quartic</td><td>[-100,100]D</td><td>0</td></tr><tr><td>F6</td><td>RotatedHyper-ElliSPSOid</td><td>[-100,100]D</td><td>0</td></tr><tr><td>F7</td><td>Sum ofDifferent Powers</td><td>[-100,100]D</td><td>0</td></tr><tr><td>F8</td><td>Zakharov</td><td>[-100,100]D</td><td>0</td></tr><tr><td>F9</td><td>Powell</td><td>[-100,100]D</td><td>0</td></tr><tr><td>F10</td><td>Salomon</td><td>[-100,100]D</td><td>0</td></tr><tr><td>F11</td><td>Wavy</td><td>[-10,10]D</td><td>0</td></tr><tr><td>F12</td><td>Xinsheyang02</td><td>[-5,5]D</td><td>0</td></tr><tr><td>F13</td><td>Zero Sum</td><td>[-1,1]D</td><td>0</td></tr><tr><td>F14</td><td>Chung Reynolds</td><td>[-5,5]D</td><td>0</td></tr><tr><td>F15</td><td>AMGM</td><td>[0,10]D</td><td>0</td></tr><tr><td>F16</td><td>Brown</td><td>[-1,4]D</td><td>0</td></tr><tr><td>F17</td><td>Infinity</td><td>[-1,1]D</td><td>0</td></tr><tr><td>F18</td><td>Alpine 1</td><td>[-10,10]D</td><td>0</td></tr><tr><td>F19</td><td>Cigar</td><td>[-10,10]D</td><td>0</td></tr><tr><td>F20</td><td>Drop Wave</td><td>[-5.12,5.12]D</td><td>-1</td></tr></table></body></html>

对于1000维测试函数，本文选取具有代表性的函数F1、F4、F8、F17绘制收敛曲线以直观对比算法的收敛性。各优化算法对4个测试函数在1000维的收敛曲线如图4所示。

根据图4的收敛曲线，从算法的收敛性分析，对 $_ { F I }$ 和F17，AOA、SBO-EP算法均可收敛到最优值，但SBO-EP算法收敛速度明显更快，整体呈现指数级收敛趋势；对 $F 4$ ，$F \delta$ ，仅有SBO-EP算法收敛到最优值，且收敛趋势稳定，没有陷入局部最优。可见收敛速度和稳定性方面，SBO-EP算法相较于其他优化算法具有明显优势。

表51000 维测试函数  
表61000维测试函数优化结果对比  
Tab.6Comparison of optimization results of looo-dimensional test functions   

<html><body><table><tr><td rowspan="2">函数</td><td rowspan="2">算法</td><td colspan="9">D=1000</td></tr><tr><td>ACO</td><td>SPSO</td><td>AOA</td><td>GWO</td><td>SPBO</td><td>TLBO</td><td>CPTLBO</td><td>SBO</td><td>SBO-EP</td></tr><tr><td rowspan="4">F1</td><td>最优值</td><td>7.68E+02</td><td>9.05E+01</td><td>0.00E+00</td><td>6.54E-12</td><td>0.00E+00</td><td>1.97E+02</td><td>0.00E+00</td><td>1.11E-16</td><td>0.00E+00</td></tr><tr><td>最差值</td><td>7.87E+02</td><td>1.83E+02</td><td>0.00E+00</td><td>1.33E-03</td><td>4.40E-03</td><td>3.27E+02</td><td>0.00E+00</td><td>1.48E-16</td><td>0.00E+00</td></tr><tr><td>平均值</td><td>8.09E+02</td><td>2.70E+02</td><td>0.00E+00</td><td>4.00E-02</td><td>4.52E-04</td><td>5.05E+02</td><td>0.00E+00</td><td>2.22E-16</td><td>0.00E+00</td></tr><tr><td>标准差</td><td>9.23E+00</td><td>3.05E+01</td><td>0.00E+00</td><td>7.29E-03</td><td>9.43E-04</td><td>7.51E+01</td><td>0.00E+00</td><td>5.32E-17</td><td>0.00E+00</td></tr><tr><td rowspan="4">F2</td><td>最优值</td><td>1.72E+04</td><td>1.10E+04</td><td>0.00E+00</td><td>2.58E-07</td><td>1.82E-12</td><td>1.13E+04</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>最差值</td><td>1.74E+04</td><td>1.18E+04</td><td>0.00E+00</td><td>1.65E+01</td><td>2.50E-01</td><td>1.28E+04</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>平均值</td><td>1.76E+04</td><td>1.25E+04</td><td>0.00E+00</td><td>3.91E+01</td><td>3.13E-02</td><td>1.38E+04</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr><tr><td>标准差</td><td>1.23E+02</td><td>3.72E+02</td><td>0.00E+00</td><td>1.04E+01</td><td>5.41E-02</td><td>6.10E+02</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td></tr></table></body></html>

续表61000 维测试函数优化结果对比  

<html><body><table><tr><td rowspan="2">函数</td><td rowspan="2">算法</td><td colspan="8">D=1000</td></tr><tr><td>ACO</td><td>SPSO 2.72E+08</td><td>AOA</td><td>GWO</td><td>SPBO</td><td>TLBO 4.00E+08</td><td>CPTLBO 1.69E-123</td><td>SBO SBO-EP</td></tr><tr><td rowspan="4">F3</td><td>最优值 最值</td><td>1.49E+09</td><td>2.54E-198 1.14E-148</td><td>2.22E-06 4.30E-06</td><td>1.48E-14 4.01E+02</td><td></td><td></td><td>8.50E-11 1.27E-10</td><td>0.00E+00 0.00E+00</td></tr><tr><td></td><td>1.56E+09</td><td>3.56E+08</td><td></td><td></td><td></td><td>1.92E+08</td><td>3.84E-116</td><td></td></tr><tr><td>标准差</td><td>3.02E+07</td><td></td><td></td><td></td><td></td><td></td><td></td><td>0.00E+00</td></tr><tr><td></td><td>3.07E+06</td><td>5.71E+07 5.37E+05</td><td>2.60E-147 1.17E-182</td><td>1.68E-06</td><td>8.53E+01 2.04E-15</td><td>1.57E+08 7.77E+05</td><td>7.16E-117 2.38E-125</td><td>2.68E-11 0.00E+00 0.00E+00</td></tr><tr><td rowspan="4">F4</td><td>最优值</td><td></td><td></td><td>4.37E-09</td><td></td><td></td><td></td><td>2.16E-13 2.93E-13</td></tr><tr><td></td><td>7.15E+05</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>最差值</td><td>3.14E+06</td><td>3.79E-159</td><td>9.81E-09</td><td>4.39E-00</td><td>1.37E+06</td><td>2.85E-117 5.19E-118</td><td>0.00E+00 0.00E+00</td></tr><tr><td rowspan="7">F5</td><td>标准差 最优值</td><td>3.23E+04 3.18E+21</td><td>9.13E+04 1.23E-149</td><td>3.97E-09</td><td>1.55E+00</td><td>2.72E+05</td><td></td><td>5.69E-14</td></tr><tr><td></td><td>1.60E+20</td><td>0.00E+00</td><td>1.47E-03</td><td>1.50E-11</td><td>2.04E+20</td><td>9.51E-286</td><td>1.21E-15</td></tr><tr><td>最值</td><td>3.4E+21 2.34E+20</td><td>3.62E-290</td><td>2.28E-02</td><td>6.41E+07</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>8.23E+20</td><td>1.30E-258</td><td>3.23E-15</td></tr><tr><td>标准差</td><td>1.30E+20 6.23E+19</td><td></td><td></td><td></td><td></td><td></td><td>1.31E-15</td></tr><tr><td>最优值 最值</td><td>1.51E+09 2.57E+08</td><td>0.00E+00 2.78E-197</td><td>4.13E-02 1.55E-06</td><td>1.70E+07 5.22E-10</td><td>3.06E+20 4.22E+08</td><td>0.00E+00 4.18E-124</td><td>7.07E-11</td></tr><tr><td>F6</td><td>1.55E+09</td><td>3.68E+08</td><td>29.83E-148</td><td>3.52E-06</td><td>2.81E+02</td><td>6.92E+08</td><td> 3.59E-117</td></tr><tr><td rowspan="7">F7</td><td>标准差 最优值</td><td>1.89E+07</td><td>6.31E+07 Inf</td><td></td><td>5.68E+01</td><td>1.45E+08</td><td>1.23E-117</td><td>1.24E-10 2.57E-11</td></tr><tr><td></td><td>3.83E-17</td><td>4.75E-147 Inf</td><td>1.40E-06 3.26E-168</td><td>Inf</td><td>Inf</td><td>Inf</td><td>Inf</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>m</td></tr><tr><td>最值</td><td>1.66E-0</td><td></td><td>1.73E-11</td><td>nf</td><td></td><td>If</td><td></td></tr><tr><td>标准差 最优值</td><td>5.18E-01</td><td>If NaN NaN</td><td>9.46E-111</td><td>NaN</td><td>NaN</td><td>NaN 4.94E+03</td><td>NaN 5.54E+05</td></tr><tr><td>最值</td><td>3.02E+06 3.15E+06</td><td>1.74E+06</td><td>8.12E+03 1.50E+06</td><td>1.11E+05</td><td></td><td>1.06E+06</td><td>1.02E+06</td></tr><tr><td>F8</td><td>标准差 4.86E+04</td><td>2.4E+06 5.90E+05</td><td>1.05E+06</td><td>1.93E+06</td><td>3.04E+06</td><td>1.64E+06</td><td>2.9E+05</td></tr><tr><td></td><td>最优值 3.11E+11</td><td>1.28E+10</td><td>1.40E+06 2.23E-205</td><td>2.08E+05 2.75E-04</td><td>8.30E+05 5.24E-10</td><td>4.05E+05 4.14E+10</td><td>5.62E+04 2.57E+05 9.00E-125 5.76E-12</td></tr><tr><td>F9</td><td>最值</td><td>2.20E+10</td><td>5.08E-142</td><td>5.91E+00</td><td>1.49E+01</td><td>7.75E+10</td><td>4.26E-119</td></tr><tr><td></td><td>标准差</td><td></td><td>2.78E-141</td><td>2.53E+01</td><td>4.33E+00</td><td>2.64E+10</td><td>8.50E-119</td></tr><tr><td rowspan="7">F10</td><td>最优值</td><td>3.42E+11 1.78E+10</td><td>5.89E+09</td><td></td><td></td><td></td><td></td><td></td><td>1.03E-11 0.00+00 7.41E-12 0.00E+00 0.00E+00 0.00E+00</td></tr><tr><td>最值</td><td>1.73E+02</td><td>7.15E+01</td><td>9.99E-02</td><td>6.00E-01</td><td>4.47E-06</td><td>9.81E+01</td><td>9.99E-02</td><td>3.00E-01</td></tr><tr><td></td><td>1.78E+02</td><td>8.3E+01</td><td>1.03E-01</td><td>7.07E-01</td><td>1.50E-00</td><td>1.19E+02</td><td>9.99E-02</td><td>3.03E-01 0.00E+00</td></tr><tr><td>标准差</td><td>1.45E+00</td><td></td><td></td><td></td><td></td><td></td><td>2.66E-06</td><td>1.83E-02</td></tr><tr><td>最优值</td><td></td><td>5.79E+00</td><td>1.83E-02</td><td>6.40E-02</td><td>3.20E-01</td><td>1.10E+01</td><td></td><td>9.31E-01</td></tr><tr><td>最差值</td><td>9.74E-01</td><td>7.99E-01</td><td>0.00E+00</td><td>1.54E-02</td><td>2.03E-13</td><td>6.58E-01</td><td>0.00E+00</td><td>0.00E+00 9.48E-01</td></tr><tr><td>F11 平均值</td><td>9.81E-01 9.86E-01</td><td>8.74E-01</td><td>6.35E-02 9.54E-01</td><td>2.33E-02 3.98E-02</td><td>9.67E-05 7.83E-06</td><td>7.82E-01 8.57E-01</td><td>9.47E-01 9.74E-02</td><td>0.00E+00 9.55E-01 0.00E+00</td></tr><tr><td></td><td>标准差 3.03E-03</td><td>9.51E-01 4.52E-02 8.42E-158</td><td>2.42E-01</td><td>5.89E-03</td><td>1.96E-05</td><td>4.42E-02</td><td>2.84E-01</td><td>5.23E-03 5.94E-223</td><td>0.00E+00</td></tr><tr><td>F12</td><td>最优值 最差值</td><td>1.24E-109 4.43E-69 2.72E-124</td><td>4.69E-171 2.79E-163</td><td>9.20E-203 4.35E-171</td><td>0.00E+00 0.00E+00</td><td></td><td>0.00E+00 2.56E-177</td><td>5.96E-188 9.10E-169</td><td>1.83E-240 2.54E-207 1.25E-224 6.25E-226</td></tr><tr><td></td><td>平均值</td><td>1.24E-67 5.50E-123</td><td>7.55E-162</td><td>7.39E-170</td><td>0.00E+00</td><td></td><td>7.69E-176</td><td>3.14E-170</td><td>7.44E-206 0.00E+00 0.00E+00</td></tr><tr><td></td><td>标准差</td><td>2.26E-68 1.10E-123</td><td>0.00E+00</td><td>0.00E+00</td><td>0.00E+00</td><td></td><td>0.00E+00</td><td>0.00E+00</td><td>1.10E+00 0.00E+00</td></tr><tr><td>F13</td><td>最优值</td><td>1.20E+00</td><td>0.00E+00</td><td>1.00E+00</td><td>1.14E+00</td><td>0.00E+00</td><td>1.01E+00</td><td>1.05E+00</td><td>0.00E+00</td></tr><tr><td></td><td>最差值</td><td>1.71E+00</td><td>0.00E+00</td><td>1.04E+00</td><td>1.49E+00</td><td>0.00E+00</td><td>1.23E+00</td><td>1.95E+00</td><td>1.87E+00 0.00E+00</td></tr><tr><td></td><td>平均值</td><td>2.74E+00</td><td>0.00E+00</td><td>1.23E+00</td><td>2.33E+00</td><td>0.00E+00</td><td>2.06E+00</td><td>1.44E+00</td><td>2.74E+00</td></tr><tr><td></td><td>标准差</td><td>3.85E-01</td><td>0.00E+00</td><td>4.54E-02</td><td>3.10E-01</td><td>0.00E+00</td><td>2.93E-01</td><td>2.27E-01</td><td>4.14E-01 2.00E-31</td></tr><tr><td>F14</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td>6.12E-305</td><td>0.00E+00</td></tr><tr><td></td><td>最优值</td><td>5.43E+07 6.14E+07</td><td>1.62E+06 3.34E+06</td><td>0.00E+00 1.01E-399</td><td>9.59E-23 7.85E-22</td><td>4.09E-36 8.36E-06</td><td>2.53E+06 1.26E+07</td><td>3.1E-291</td><td>0.00E+00 3.68E-31 0.00E+00</td></tr><tr><td>标准差 最优值</td><td>最值</td></table></body></html>

# 3.4改进策略组合优化效果对比

SBO-EP算法的优化效果是在基于“最近发展区”理论的教阶段、基于“成就动机”理论的自学阶段、基于“同伴效应”的班级重组三种策略的共同作用下实现的。为验证各改进策略的有效性，进行三种改进策略的组合对比实验。将仅采用单一策略1、2或3的算法分别用SBO-EP1、SBO-EP2、SBO-EP3表示，采用两种策略1和2、1和3、2和3的算法分别用SBO-EP4,SBO-EP5，SBO-EP6表示。选取CEC2021中00类型的 $_ { f l }$ 和 $f 7$ 及1000维的F10和F18 四个测试函数，以30000次评价次数为基准，分别独立运行30次，所得最优值、最差值、平均值、标准差四个指标结果如表7所示，各算法第15次运行结果的迭代曲线如图5所示。

实验结果表明，从单一策略角度看，SBO-EP1与SBO-EP2的优化效果优于SBO，可见，加入策略1或策略2能够大幅提高算法的开发和探索能力，改进效果较为明显，其中策略1对 SBO-EP算法贡献度更大，能够显著提高算法的求解精度。而单独加入策略3对四个函数均没有优化；当两种策略结合时，进一步提高了算法的求解精度，在SBO-EP4、SBO-EP5、SBO-EP6中，SBO-EP4 的优化效果最好，即策略1和策略2的结合效果最优。加入策略3的实验结果表明，SBO-EP6优于SBO-EP5，即策略2与策略3的结合对算法贡献度更大，由此验证了策略3的有效性，主要体现在对于协助其他策略提高算法的搜索能力方面以及帮助算法跳出局部最优解方面具有较大贡献；显然，当三种策略结合时，算法的优化能力的到有效提升，求解精度最高，收敛速度也更快。对于函数fl、 $f 7$ 和F10可以找到最优解，对函数 $F l \&$ 也能够优化到较高精度，相较于其他策略结合方式优化精度有明显的提高。

8 种策略组合算法的优化实验结果表明，策略1和2对算法探索能力的提升具有较大的贡献度，策略3能够在策略1、策略2的加持下显著提高算法的全局优化能力。策略组合优化实验比较了3种改进策略的贡献度，成功验证了3种策略结合优化的有效性，即说明SBO-EP算法的优越性。

![](images/e5b0129f8c7415d8c684f21fcb98e62c8275bafb1f1b2b4fcfca525c5ce7ed08.jpg)  
图4CEC2021函数收敛曲线  
Fig.4Convergence curves of 1oo-dimensional test function

对 SBO-EP算法及其他7种策略组合的算法的实验结果同样进行显著性水平为 $5 \%$ 的秩和检验。计算所得 $p$ 值均小于0.05，说明SBO-EP算法的优越性在统计上是显著的，进一步验证了三种改进策略的有效性。

表71000维测试函数优化结果对比  
Tab.7Comparison of optimization results of looo-dimensional test functions   

<html><body><table><tr><td rowspan="2">函数 算法</td><td rowspan="2">1aD./</td><td colspan="8">Colpalison ol optimlzationTesuls ol Tooo-dlmensional test Tunctions</td></tr><tr><td>SBO</td><td>SBO-EP1</td><td>SBO-EP2</td><td>SBO-EP3</td><td>SBO-EP4</td><td>SBO-EP5</td><td>SBO-EP6</td><td>SBO-EP</td></tr><tr><td rowspan="4">fl (CEC00)</td><td>最优值</td><td>7.85E-25</td><td>9.34E-89</td><td>7.01E-80</td><td>1.01E-23</td><td>3.66E-153</td><td>2.92E-99</td><td>2.01E-111</td><td>0.00E+00</td></tr><tr><td>最差值</td><td>2.18E-24</td><td>7.86E-79</td><td>1.44E-76</td><td>4.59E-23</td><td>3.38E-144</td><td>1.92E-93</td><td>4.52E-106</td><td>0.00E+00</td></tr><tr><td>平均值</td><td>4.20E-24</td><td>3.71E-80</td><td>1.46E-77</td><td>2.65E-23</td><td>1.35E-145</td><td>2.88E-94</td><td>3.91E-107</td><td>0.00E+00</td></tr><tr><td>标准差</td><td>9.13E-25</td><td>1.45E-79</td><td>2.96E-77</td><td>1.13E-23</td><td>6.15E-145</td><td>5.55E-94</td><td>9.38E-107</td><td>0.00E+00</td></tr><tr><td rowspan="4">f7 (CEC00)</td><td>最优值</td><td>1.53E-03</td><td>5.50E-39</td><td>5.76E-17</td><td>1.64E-03</td><td>6.15E-137</td><td>5.49E-50</td><td>3.04E-56</td><td>0.00E+00</td></tr><tr><td>最差值</td><td>2.85E-01</td><td>4.30E-08</td><td>5.81E-10</td><td>6.56E-01</td><td>1.06E-115</td><td>4.54E-08</td><td>1.24E-13</td><td>0.00E+00</td></tr><tr><td>平均值</td><td>2.91E-02</td><td>4.28E-09</td><td>1.94E-11</td><td>1.69E-01</td><td>3.72E-117</td><td>4.67E-09</td><td>4.14E-15</td><td>0.00E+00</td></tr><tr><td>标准差</td><td>5.91E-02</td><td>1.30E-08</td><td>1.06E-10</td><td>1.96E-01</td><td>1.94E-116</td><td>1.19E-08</td><td>2.27E-14</td><td>0.00E+00</td></tr><tr><td rowspan="4">F10</td><td>最优值</td><td>3.00E-01</td><td>1.43E-56</td><td>7.91E-98</td><td>3.00E-01</td><td>8.05E-150</td><td>1.11E-63</td><td>7.44E-141</td><td>0.00E+00</td></tr><tr><td>最差值</td><td>4.00E-01</td><td>6.33E-31</td><td>1.58E-96</td><td>5.00E-01</td><td>3.00E-142</td><td>1.05E-37</td><td>9.44E-116</td><td>0.00E+00</td></tr><tr><td>平均值</td><td>3.03E-01</td><td>2.11E-32</td><td>3.03E-97</td><td>3.87E-01</td><td>1.34E-143</td><td>3.49E-39</td><td>3.38E-117</td><td>0.00E+00</td></tr><tr><td>标准差</td><td>1.83E-02</td><td>1.16E-31</td><td>2.86E-97</td><td>4.30E-02</td><td>5.51E-143</td><td>1.91E-38</td><td>1.72E-116</td><td>0.00E+00</td></tr><tr><td rowspan="4">F18</td><td>最优值</td><td>7.56E-08</td><td>1.89E-62</td><td>6.34E-99</td><td>3.33E-07</td><td>5.74E-148</td><td>3.34E-68</td><td>2.53E-150</td><td>1.84E-203</td></tr><tr><td>最差值</td><td>1.17E-07</td><td>2.55E-59</td><td>1.66E-98</td><td>6.76E-04</td><td>5.66E-143</td><td>5.33E-66</td><td>2.27E-119</td><td>3.33E-184</td></tr><tr><td>平均值</td><td>9.11E-08</td><td>3.03E-60</td><td>1.00E-98</td><td>8.11E-05</td><td>6.91E-144</td><td>1.02E-66</td><td>8.14E-121</td><td>9.39E-183</td></tr><tr><td>标准差</td><td>1.06E-08</td><td>5.85E-60</td><td>2.68E-99</td><td>2.10E-04</td><td>1.40E-143</td><td>1.24E-66</td><td>4.14E-120</td><td>0.00E+00</td></tr></table></body></html>

![](images/fed3a1a962d0ca033d736e9f69683f50f48f07672e7bf4ea50194e0d5bb0bb20.jpg)  
图5改进策略组合优化收敛曲线  
Fig.5Improved strategy combination optimization convergence curves

# 4 结束语

SBO算法是一种基于多班级协同教学的元启发式算法，为解决该算法存在的寻优精度低、全局搜索能力弱等缺陷，本文提出了一种融入教育心理学的特征分组动态SBO 算法(SBO-EP)。首先在“最近发展区”理论上依据习惯化原则对学生进行分组教更新，提高算法的探索能力。再基于“成就动机”理论依据习惯化原则提出分组自学阶段，提升算法的开发能力。并在每轮学习过程结束后参考“同伴效应”实行班级重组操作，从而增加解的多样性并提高算法的全局搜索能力。其次，在CEC2021的40个测试函数及20个其他类型的测试函数上对SBO-EP算法进行测试，并与ACO、SPSO、AOA、GWO、SPBO、TLBO、CPTLBO、SBO八种优化算法进行对比分析。实验结果表明，SBO-EP算法的搜索性能更强、收敛速度更快，且具有更高的稳定性，验证了该算法的优越性。最后，通过对三种改进策略的8种组合算法进行测试，验证了SBO-EP算法的有效性。SBO-EP算法在优化方面具有较强的竞争力，将该算法应用于新能源汽车的动力电池回收网络规划是进一步的研究方向。

参考文献：   
[1]Farshchin M, Maniat M,Camp C V,et al. School based optimization algorithm for design of steel frames [J]. Engineering Structures,2018, 171: 326-335.   
[2] Holland JH. Genetic algorithms [J]. Scientific American,1992,267 (1): 66-73.   
[3]Kirkpatrick S, Gelatt C D,Vecchi M P. Optimization by simulated annealing [J]. Science,1983,220 (4598): 671-680.   
[4]Rao R V,Savsani V J,Vakharia D P. Teaching-learning-based optimization: A novel method for constrained mechanical design optimization problems [J].Computer-Aided Design,2010,43 (3): 303-315.   
[5]Shi Yuhui. Brain storm optimization algorithm[C]/ Proc of the 2th International Conference in Swarm Intelligence.Berlin: Springer Press,2011:303-309.   
[6] Degertekin S O,Tutar H,Lamberti L. School-based optimization for performance-based optimum seismic design of steel frames [J]. Engineering with Computers,2021,37 (4): 3283-3297.   
[7] Abdelghany R Y, Kamel S,Ramadan A,et al. Solar cell parameter estimation using school-based optimization algorithm [C]// Proc of the 24th IEEE International Conference on Automation. Chilean: IEEE Press, 2021: 1-6.   
[8] Farshchin M,Camp C V,Maniat M. Optimal design of truss structures for size and shape with frequency constraints using a collaborative optimization strategy [J]. Expert Systemswith Applications,2016,66: 203-218.   
[9] Camp C V,Farshchin M. Design of space trusses using modified teaching-learning based optimization [J]. Engineering Structures, 2014, 62: 87-97.   
[10]王惠来．奥苏伯尔的有意义学习理论对教学的指导意义[J]．天 津师范大学学报：社会科学版,2011,38(2):67-70.(Wang Huilai. Ausubel’s meaningful learning theory to the reform to instruction [J]. Journal of Tianjin Normal University: Social Science,2011,38 (2): 67-70.)   
[11]麻彦坤，叶浩生．维果茨基最近发展区思想的当代发展[J]．心 理发展与教育，2004,20(2):89-93.(Ma Yankun,Ye Haosheng. Contemporary development of Vygotsky’ s“ Zone of Proximal Development ” Theory[J]. Psychological Developmentand Education,2004,20 (2): 89-93.)   
[12]王文静．维果茨基“最近发展区"理论对我国教学改革的启示[J]. 心理学探新,2000,20 (2):17-20.(Wang Wenjing.The inspiration of Vygotsky's" Zone of Proximal Development"Theory to instruntional reform in China[J].Psychological Exploration,200o,20 (2): 17-20.)   
[13] Zhang Yiying,Jin Zhigang. Group teaching optimization algorithm: A novel meta heuristic method for solving global optimization problems [J]. Expert Systems with Applications,2020,148:113246.   
[14]张鼎昆，方俐洛，凌文轻．自我效能感的理论及研究现状[J]．心 理学动态，1999,17(1): 39-43,11.(Zhang Dingkun,Fang Liluo, Ling Wenquan. Theory and research status of self-efficacy [J]. Advances in Psychological Science,1999,17(1):39-43,11.)   
[15] Das B,Mukherjee V,Das D. Student psychology based optimization algorithm: A new population based optimization algorithm for Solving optimization problems [J].Advancesin Engineering Software,2020,146:102804.   
[16]何佩苑，刘勇．融合认知心理学理论的新型教与学优化算法及应 用[J].计算机应用研究,2022,39(03):785-789,796(He Peiyuan, Liu Yong.New teaching-learning-based optimization algorithmwith cognitive psychology theory and its application [J].Application Research of Computers,2022,39 (03):785-789,796.)   
[17]郑磊．教育中的社区效应和同伴效应：方法、证据及政策启示[J]. 教育学报,2015,11(5):99-110.(Zheng Lei.Neighborhood effects and peer effects in education:methods，evidences,and policy implications [J].Journal of Educational Studies,2015,11 (5):99- 110.)   
[18]Dorigo M,Birattari M,Stutzle T.Ant colony optimization[J].IEEE Computational Intelligence Magazine,2006,1(4): 28-39.   
[19]Phung M D,Ha Q P.Safety-enhanced UAV path planning with spherical vector-based particle swarm optimization [J].Applied Soft Computing,2021,107:107376.   
[20]Hashim F A，Hussain K,Houssein E H,et al.Archimedes optimization algorithm:a new metaheuristic algorithm for solving optimization problems [J].Applied Intelligence,2021,51 (3):1531- 1551.   
[21]Mirjalili S,Mirjalili S M,Lewis A.Grey wolf optimizer [J]. Advances in Engineering Software,2014,69(7):46-61   
[22]王勇亮，王挺，姚辰．基于Kent映射和自适应权重的灰狼优化算 法[J]．计算机应用研究，2020,37(S2):37-40.（Wang Yongliang, Wang Ting,Yao Chen.Adaptive weighted grey-wolf optimization algorithm based on Kent map[J].Application Research of Computers, 2020,37(S2): 37-40.).