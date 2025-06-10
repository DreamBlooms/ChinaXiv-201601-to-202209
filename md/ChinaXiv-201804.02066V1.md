# 动态学习混沌映射的粒子群算法

董丽凤，陈阳，巫光福(江西理工大学 信息工程学院，江西 赣州 341000)

摘要：传统粒子群优化算法（PSO）对社会认知部分与自我认知部分都采用恒定学习常数，一定程度上限制种群全局协调能力。在算法收敛后期种群多样性丧失而导致全部个体收敛于搜索空间中的某一点，这易诱发早熟现象。针对这种缺陷提出一种动态学习混沌映射的粒子群优化算法(VLCMPSO)。在算法初期迭代中应多考虑自身记录的最佳点，在算法后期应快速向种群最佳点收敛，因而设计一种进行协调的动态学习因子。为克服早熟现象，判断种群多样性方差低于设定阈值时，以混沌映射的方式将该代最优个体位置更新且以新的方式进行优化操作。经实验证明新算法在收敛速度与精度上都具有更好的性能。

关键词：粒子群优化；动态学习因子；混沌映射；全局优化 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.11.0737

# Chaotic mapping particle swarm optimization algorithm based on variable learning factors

Dong Lifeng, Chen Yang†, Wu Guangfu (Schoolof Information Engineering Jiangxi UniversityofScience&Technology,Ganzhou Jiangxi3410o,China)

Abstract:The traditionalparticle swarm optimizationalgorithmuses constantlearningconstants forsocialandself-cognition tolimit thepopulation'sglobalcordinationability.Inthelateconvergenceof thealgorithm,thediversityofthepopulationis lostandallteindividualsconverge toonepointinsearchspace,whichcantrigger theprecociousconvergence.Inviewofthis defect,this paper proposed a chaotic map particle swarm optimization algorithm based on variable learing factor.In the early stageof thealgorithm,theemphases should focusonthebestlocationofself-recording.Atthe laterperiodof thealgorithm,it should design acoordinated dynamic learning factorto converge on the best position ofpopulation.In order toovercome the premature phenomenon and determine the variance ofpopulationdiversity below the set value,using chaotic mapping updated theoptimalindividuallocationofthegenerationandutilizinganewwaytooptimized.Theexperimentalshow thenewalgorithm has better performance in convergence speed and precision.

Key words: particle swarm optimization; variable learning factor; chaotic mapping; global optimization

# 0 引言

优化问题涉及当今世界各个工程科学、自然科学领域。伴随着各领域研究发展，研究内容愈发复杂化，计算优化难度也越来越高。面对非线性、高维度、不可微问题，传统优化方法效果不理想从而导致效率低下资源浪费等现象出现。粒子群优化算法（particle swarm optimization,PSO）是一种全局优化的群智能算法 $\cdot ^ { [ 1 ^ { \sim } 4 ] }$ ，其实现简单，算法本身具有的自组织并行寻优的特征保证了求解问题的高效性，提出至今已成功应用到复杂函数求解[5]、神经网络分类[6]、机器人定位[7]、太阳能光电系统[8]等问题上。

粒子群算法极快的收敛速度在处理低纬度问题时效果极佳，然而在复杂多峰谷问题上易出现早熟现象。在算法进行迭代优化后期，全部种群聚在一点即种群多样性丢失，算法停滞。为提高粒子群求解复杂问题精度，国内外学者多采取与其他智能算法优势互补的策略或从自身模型改进提高粒子群算法性能。利用人工免疫算法的浓度调节机制控制粒子群搜索范围，对优化性能较低的部分粒子个体进行疫苗接种可以有效控制粒子群多样性衰减[9]。吴晓军等人[10]以粒子搜索中心的概率密度出发提出均匀搜索的粒子群算法。文献[11]中利用柯西变异限制局部最优，可以使算法有效地逼近全局最优。生物进化过程中具有遗传变异的模式，粒子群算法在迭代进化过程中也会发生变异。赵新超等人[12]引入非均匀变异思想对粒子群进行改进调整文献[13]中增加全局学习项，文献[14]中将粒子随机分为多个维度，都增加种群多样性，在性能方面都取得较好的效果。

总结前人的改进策略的基础上，本文对粒子群恒定的学习因子进行动态调整，使其粒子群优化前后期有相对的着重点。使用混沌映射的方式改良种群多样性低的问题，使陷入局部最优的个体按照新的方式快速收敛于更优的解。最后通过数值实验对其性能进行仿真测试。

# 1 粒子群算法描述

粒子群优化算法模型来源于模拟鸟群自组织觅食行为的启发。鸟群之间具有信息共享的某种方式，其他个体可以记住自身找到离食物源最近的位置，同时又可向种群中最好的那个个体靠拢。经典的粒子群搜索方式如式（1）与（2）所示。其中：$\nu$ 表示粒子飞行的速度； $w$ 表示下一次该粒子进化的惯性权重；pbest、gbest分别表示某个粒子自身搜索过程中的最佳位置和整个种群进化中的最佳位置； $^ { r I }$ 、 $^ { r 2 }$ 为满足均匀分布的随机数；c1、 $c 2$ 分别表示对个体最佳的学习因子与全局最佳的学习因子。下一代更新位置为上一代该个体的位置加上所求出的速度。

$$
\nu _ { i } ( t + 1 ) = w \nu _ { i } ( t ) + c _ { 1 } r _ { 1 } ( p b e s t _ { i } - x _ { i } ) + c _ { 2 } r _ { 2 } ( g b e s t - x _ { i } )
$$

$$
x _ { i } ( t + 1 ) = x _ { i } ( t ) + \nu _ { i } ( t + 1 )
$$

经过研究上述经典的粒子群算法的恒定惯性权重影响算法搜索设为效率和精度。针对粒子群的权重，学者们提出有随机权重法、线性权重法以及自适应权重。这里简单介绍自适应权重。本文的改进研究也是基于自适应权重的粒子群算法[15]展开的。权重选取如式（3）所示。其中：fiti表示第 $i$ 个个体的适应度，其小于该代平均适应度 $f _ { a \nu e }$ 时利用适应度获取该个体的权重； $w _ { \mathrm { m i n } }$ 、 $w _ { \mathrm { m a x } }$ 分别取0.6、0.8。

$$
\left\{ w = w _ { \operatorname* { m i n } } + \frac { ( f i t _ { i } - { f _ { \operatorname* { m i n } } } ) \cdot ( w _ { \operatorname* { m a x } } - w _ { \operatorname* { m i n } } ) } { { f _ { a \nu e } } - { f _ { \operatorname* { m i n } } } } , f i t _ { i } < { f _ { a \nu e } } \right.
$$

# 2 动态学习混沌映射的粒子群算法

# 2.1算法分析

第1章中提到的自适应权重粒子群和传统粒子群都采用恒定的学习因子影响自身认知部分与历史种群最佳部分。粒子群的搜索过程应该是一个对全局与局部平衡的搜索过程，搜索初期如果种群过多向全局最优解的位置收敛便容易出现早熟现象，这个问题在多峰复杂函数优化上表现得更为明显。迭代初期更高程度学习自身个体的经验，即在自身个体最佳位置附近领域搜索，可以更好地开发局部勘探能力，增加粒子活性。因此，为了在算法迭代过程中更好开发个体搜索能力，避免过早陷入局部早熟，采用式（4)与（5)动态调整学习因子。其中：cmax、cmin分别表示学习因子的上限与下限；maxgen为算法最大迭代数；t表示执行过程中的当前迭代数。文献[1]里表明基本粒子群算法学习因子取值为2。基于此，为避免无效率搜索，本文中控制学习因子上下限的Cmax、Cmin取2和1。粒子群体的自我认知部分由c1控制，社会认知部分由 $^ { c 2 }$ 控制，种群在迭代初期可以更多地依靠个体保存的先验知识，进化后期减少自身知识依赖同时以更高概率获取社会认知部分的知识，进而

更快收敛于全局极值点。

$$
c _ { 1 } = c _ { \operatorname* { m a x } } - c _ { \operatorname* { m a x } } \cdot \left( t - 1 \right) / \operatorname* { m a x } g e n
$$

$$
c _ { 2 } = c _ { \mathrm { m i n } } + ( t - 1 ) / \operatorname* { m a x } g e n
$$

为抑制算法陷入局部极值位置，以适应度方差为种群多样性的判断条件。当某代适应度方差小于设定值时引入混沌映射，将陷入局部最优解的那一代的全局最佳个体位置变换。此处采用常用的Logisitic 映射系统，式（6） ${ \sim } ( 8 )$ 为映射公式。其中代入混沌映射变量 $C X$ 属于[0,1],并且取值不等于0.25、0.5、0.75时产生混沌过程。式（7）中： $a$ 为混沌系统的控制变量， $\scriptstyle \mathbf { a } = 4$ 时混沌生成的数属于一种伪随机状态，效果最好； $X$ 为待优化变量属于[randmin,randmax]； $X$ 为混沌映射后的变量。

$$
C X = ( X - r a n d _ { \mathrm { m i n } } ) / \left( r a n d _ { \mathrm { m a x } } - r a n d _ { \mathrm { m i n } } \right)
$$

$$
C X ^ { \prime } { = } a \cdot C X \cdot ( 1 { - } C X )
$$

$$
X ^ { \prime } { = } r a n d _ { \operatorname* { m i n } } + C X ^ { \prime } \cdot ( r a n d _ { \operatorname* { m a x } } - r a n d _ { \operatorname* { m i n } } )
$$

经过上述混沌映射陷入早熟现象的全局最优位置将成为下一次迭代的全局最优学习位置，这种方式与遗传算法中变异思想类似，通过这种方式旨在扩大粒子群的搜索范围，激活粒子勘探能力遏制粒子聚拢的现象。映射完成的粒子位置采用式(9)进行更新。取消了个体认知部分，粒子只向上一代继承部分知识，向此时的种群最优位置急速收敛。种群不需要考虑某个体的历史最佳位置，已经陷入聚拢的局部位置最重要的是扩展其种群的搜索空间，摆脱当前位置，因此利用式（9）进行更新，既可以保证正确的寻优方向，亦可以保持较高的速度。需要说明的是，混沌映射完成后的粒子利用式（9）更新后要与历史最优解相比较，若其解不如历史最优解，则要利用上一代全局最佳位置进行进化搜索，放弃混沌映射后的位置。

$$
x ( t + 1 ) = w x ( t ) + c 2 r 2 ( g b e s t - x ( t ) )
$$

# 2.2算法描述

经以上描述新算法（VLCMPSO）执行步骤如下：

a)初始化种群数目、最大迭代次数、问题空间维度等相关参数。

b)初始化粒子群种群位置以及各个个体的飞行速度。

c)计算适应度函数值，比较种群所有个体，保存个体最佳位置与目前全局最佳位置。

d)进入迭代寻优，执行式（4）（5）求出当代的学习因子，以式（3）求出自适应权重，利用式（1）（2）更新粒子速度、位置，比较个体适应度，保存相应的个体历史最佳位置与全局最佳位置。

e)计算目前种群平均适应度方差，若小于设定阈值，执行步骤 f)，否则执行步骤 g)。

f)执行式 $( 6 ) \sim ( 9 )$ 。判断新的适应值是否优于之前的的适应值，若优于则利用新的位置更新；否则忽略这一步，利用之前位置跳转到步骤g)。

g)保存全局最优位置及最佳适应值。若迭代达到设定的最大迭代次数或满足目标精度则终止循环，否则重复执行步骤$\mathbf { d } ) { \sim } \mathbf { g } )$ 。

# 3 实验仿真

# 3.1 实验设计说明

为验证本文提出算法的正确性以及高效性，设计6个经典测试函数进行测试，函数具体信息如表1所示。其中F1、F2是单峰函数， ${ \mathrm { F } } 3 { \sim } { \mathrm { F } } 6$ 是多峰函数。实验规定迭代次数Maxgen为1000、种群数目Sizepop为30。由于问题维度越高，问题越复杂越难以优化，所以本次实验统一设定维度为30。粒子群优化算法为随机优化算法。为避免随机性影响实验结果，对比算法结果都采用独立运行50次的平均值。为便于观察，对理论最优解为0的 $\mathrm { F } 1 { \sim } \mathrm { F } 5$ 函数进化曲线适应值取Log10。

表1实验函数  

<html><body><table><tr><td>函数名</td><td>搜索空间</td><td>理论最优解</td><td>维度</td><td>峰值</td></tr><tr><td>F1 Sphere</td><td>[-100,100]</td><td>0</td><td>30</td><td>单峰</td></tr><tr><td>F2 Rosenbrock</td><td>[-100,100]</td><td>0</td><td>30</td><td>单峰</td></tr><tr><td>F3 Griewank</td><td>[-600,600]</td><td>0</td><td>30</td><td>多峰</td></tr><tr><td>F4 Ackley</td><td>[-100,100]</td><td>0</td><td>30</td><td>多峰</td></tr><tr><td>F5 Rastrigin</td><td>[-100,100]</td><td>0</td><td>30</td><td>多峰</td></tr><tr><td>F6 Schaffer</td><td>[-100,100]</td><td>-1</td><td>2</td><td>多峰</td></tr></table></body></html>

# 3.2 实验结果比较

图 $1 { \sim } 6$ 给出两种算法优化过程的迭代曲线。首先在相同的迭代次数中进行分析比较。

Sphere函数是一种较为容易优化的单峰函数，一般的优化算法都可以在有限的时间找到全局最优解。但随着函数维数逐渐变高，探索解的环境变复杂，求解精度会有所降低，尤其是寻优的速度会大打折扣。此类函数实验的重点应是验证改进算法对收敛速度以及局部勘探能力的提升程度。由图1可知，算法VLCMPSO在1000次迭代中5次跳出局部限制，具有更好的抑制早熟现象的能力。从收敛精度以及速度方面验证该算法的正确性以及高效性。图2中VLCMPSO虽然在第200次迭代后也出现停滞，但是前200次迭代中保持种群多样性可具有强的全局优化能力，从速度方面优于PSO精度也略有提升。

![](images/4acf7aa54bf118621514ce8213cbd37a4df5857e9df14d50dd2404119be05b14.jpg)  
图1Sphere 函数迭代进化曲线

![](images/1b8c2f613b550c866e3753e28c1e16a8fb07274f0516ada0cd7a67b89ed97039.jpg)  
图2Rosenbrock函数迭代进化曲线

函数F3是具有无数局部极值点的多峰函数，VLCMPSO的动态学习能力以及逃离聚拢位置能力可以更好地体现出来。在整个迭代过程种群至少4次逃离局部限制，其快速向混沌映射后的理论全局最佳位置收敛的特点，可以使其在较少的迭代中尽可能更多的进行空间搜索。如图3所示，进化在870代左右达到理论最优点。图4中针对Ackley函数表现来看，PSO从初始进化阶段就陷入停滞，VLCMPSO在40代后摆脱限制，在所设定的迭代次数中持续搜索。改进后算法在收敛速度以及保持种群多样性提升搜索能力方面都有明显提升。

![](images/a85ac40273eb33ad5e5057a5cd00d2eb3c57f6ed71b7f9fd757e1e880604988d.jpg)  
图3Griewank函数迭代进化曲线

![](images/171b8127a053948a5a9fa6863ed76a08308a71f2ae0dc6b8e41010bb1c7380c7.jpg)  
图4Ackley函数迭代进化曲线

函数F5本身具有无数局部极值点，其三维空间图形形状如同林立的山峰一般，每一个峰值表示一个局部极值点。由图5可知，基本粒子群算法无法摆脱早熟现象，其最终得到的近似解也是必然是局部解。VLCMPSO是针对摆脱局部位置搜索全局最优设计的，动态的学习能力可有效保持种群活性。针对这种类型的问题一定程度上缓解早熟现象。算法设置的混沌映射最佳位置可以在陷入早熟现象时有效跳离局部位置。从图5中明显看出，两种算法在前200次迭代时都处于停滞状态，在200代后VLCMPSO至少有4次跳出局部限制搜索最优解。

函数F6不是高维函数，但是属于多峰问题，其函数形如一个茶壶，亦具有很多局部极值点。其全局最优解是-0.5。由表1、2可知，粒子群在解决这种2维函数时效果相对比较理想，但在多次独立测试里不是每次都可以达到理论最优值，VLCMPSO则在其基础上进一步保证了求解的稳定性。

![](images/30abc3b1f2a2150b98301b871f8504b2283f4b0848b9d13402e04b09515df1c1.jpg)  
图5Rastrigin函数迭代进化曲线

![](images/5f2d6cf6bd1569a5a46af09767ad6ea6733e00b99dc453ed302ebb881cee96e4.jpg)  
图6Schaffer函数迭代进化曲线

单峰问题旨在测试算法优化方向的正确性以及收敛速度的提升。多峰问题上旨在测试摆脱局部极值解的限制，以保证好的求解精度。表2中给出6种测试函数在50次独立运行下的求解均值、最大最大值以及标准差。新算法在F3、F5、F6优化测试中都可以保证迭代完成收敛到理论最优解。在F1、F4优化均值相比粒子群算法分别提高20和13个精度点。其中F4在

50次独立优化中最小值达到过理论最优值。F2函数优化均值相对提升较弱，VLCMPSO相比粒子群亦提升了1个精度。总体而言VLCMPSO的改进方向是正确的，且一定程度提高了优化性能。同时，表2中给出两种算法分别独立运行50次后的平均搜索时间，可以看出VLCMPSO比PSO搜索时间增加0.2s到 $0 . 3 \mathrm { ~ s ~ }$ ，增加的消耗时间处于同一数量级。

表3中给出本文提出的算法与部分参考文献中算法的优化均值比较。符号“一”表示该算法未给出相应数据。在函数F1上，本文提出的VLCMPSO比PSO提升25个精度,相对优化效果较差与文献[4,11]，优于其他文献中算法。文献[4]提出的参数调节方法在单峰函数上具有良好的性能，多峰函数优化能较弱。F2上VLCMPS的优化均值与文献[11]大致相同，优于原算法，从表3可知F2这类问题各算法的优化解基本在同一水平，文献[5]采用的动态空间搜索方式通过不断收缩粒子的搜索空间使其逼近最优解，这种方式求解F2的表现最好。在优化F3函数上VLCMPSO可以达到理论极值0，效果优于其他对比算法。F4 函数上本文算法相比PSO提高13个精度点，且均值优于对比参考文献算法。F5中本文算法与文献[11]中的CCMPSO都可以达到该函数的理论最优值，文献[5]中算法相比文献[3,4,12]具有一定的优势，不如本文提出的算法。

表2两种算法性能比较  

<html><body><table><tr><td>函数</td><td>算法</td><td>均值</td><td>最小值</td><td>最大值</td><td>标准差</td><td>优化时间</td></tr><tr><td rowspan="2">F1</td><td>PSO</td><td>8.58e-01</td><td>3.41e-01</td><td>1.69e+00</td><td>3.78e+01</td><td>0.444s</td></tr><tr><td>VLCMPSO</td><td>8.49e-21</td><td>1.24e-30</td><td>1.52e-19</td><td>3.39e-20</td><td>0.6136</td></tr><tr><td rowspan="2">F2</td><td>PSO</td><td>1.10e+02</td><td>5.40e+01</td><td>1.94e+02 3.34e+01</td><td></td><td>0.463</td></tr><tr><td>VLCMPSO</td><td>2.87e+01</td><td>2.86e+01</td><td>2.89e+01</td><td>6.79e-02</td><td>0.609</td></tr><tr><td rowspan="2">F3</td><td>PSO</td><td>3.62e-02</td><td>2.11e-02</td><td>5.60e-02</td><td>1.07e-02</td><td>1.177</td></tr><tr><td>VLCMPSO</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1.517</td></tr><tr><td rowspan="2">F4</td><td>PSO</td><td>1.56e-00</td><td>9.01e-01</td><td>2.23e-00</td><td>9.01e-01</td><td>1.080</td></tr><tr><td>VLCMPSO</td><td>9.708e-13</td><td>0</td><td>9.74e-12</td><td>2.20e-12</td><td>1.335</td></tr><tr><td rowspan="2">F5</td><td>PSO</td><td>8.74e+01</td><td>3.37e+01</td><td>1.45e+02</td><td>2.43e+01</td><td>0.710</td></tr><tr><td>VLCMPSO</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0.922</td></tr><tr><td rowspan="2">F6</td><td>PSO</td><td>-0.4985</td><td>-0.5</td><td>-0.4903</td><td>3.56e-03</td><td>0.583</td></tr><tr><td>VLCMPSO</td><td>-0.5</td><td>-0.5</td><td>-0.5</td><td>0</td><td>0.852</td></tr></table></body></html>

随着函数维度增高，对问题的优化难度便越大。图7中给出了VLCMPSO与PSO两种算法分别在更高维度（50、100、150）下的优化效果。图例中VLCM表示本文算法，算法名称后面的数字表示问题维度。图7(a) $\sim$ (f)分别对应表1中的6个测试函数。由图7(a)可知，随着维度增加优化效果起伏不大，但是VLCMPSO在100维与150维的优化曲线基本重合；图（b）中，维度增加后算法优化效果明显变弱，在100维与150维上VLCMPSO优化曲线也基本重合，这种现象说明在150维下，算法优化效果已经停滞。图（c) $\sim$ （f）中的进化曲线都符合正确的优化理论，维度变高的情况下，算法的优化精度略微降低。图7整体说明了在进化寻优总体方向稳定的前提下，随着问题维度逐步提高，依然保持着较高的优化精度，其降低的 幅度在可接受范围之内。

![](images/274820f4c98974bd5488df61469039fe86198a4273bc0f07afda2ed2843bed83.jpg)  
图7不同维度算法相互比较

表3与参考文献算法优化均值比较   

<html><body><table><tr><td>算法</td><td>F1</td><td>F2</td><td>F3</td><td>F4</td><td>F5</td></tr><tr><td>VLCMPSO</td><td>8.49e-21</td><td>28.7</td><td>0</td><td>9.708e-13</td><td>0</td></tr><tr><td>LBL-PSO[3]</td><td>5.42e-04</td><td>35.65</td><td>1</td><td>2.268e-02</td><td>6.98e-04</td></tr><tr><td>SAIW[4]</td><td>3.84e-147</td><td>9.886</td><td>2.2e-03</td><td>2.27e+01</td><td>2.98e+01</td></tr><tr><td>DSPSO[5]</td><td>1</td><td>1.8</td><td>1</td><td>1.4e-04</td><td>2.2e-07</td></tr><tr><td>CCMPSO[11]</td><td>3.11e-28</td><td>28.9</td><td>2.59e+1</td><td>1</td><td>0</td></tr><tr><td>NmP3PSO[12]</td><td>2.12e-11</td><td>29.6</td><td>7.87e-03</td><td>2.52</td><td>8.34e+01</td></tr><tr><td>GIPSO[13]</td><td>4.04e-12</td><td>25.27</td><td>9.51e-03</td><td>1.98e-7</td><td>2.79e+01</td></tr></table></body></html>

工程科学领域的相关应用中，针对某一个优化问题会规定一个目标精度，即该解在提前设定的可接受域内就可采用。由表2可知PSO算法的精度较低一般难以达到目标要求，因此只对算法VLCMPSO，规定其不同的目标精度，独立运行100次，测试其平均达到目标精度的终止代数以及达标的成功率。其中成功率等于达到精度的次数除总的测试次数。表4中记录VLCMPSO分别在目标精度1e-05和1e-10下对F1、F3、F4、F5 测试的最小终止迭代、平均迭代及成功率。从所记录的数据可明确得出在迭代进程中VLCMPSO可以保证百分之百达到目标精度。

表4新算法在不同收敛精度下的优化进程  

<html><body><table><tr><td>精度</td><td colspan="3">VLCMPSO：1e-05</td><td colspan="3">VLCMPSO: 1e-10</td></tr><tr><td>函数</td><td>最小代数</td><td>平均代数</td><td>成功率</td><td>最小代数</td><td>平均代数</td><td>成功率</td></tr><tr><td>F1</td><td>5</td><td>8</td><td>1</td><td>349</td><td>489</td><td>1</td></tr><tr><td>F3</td><td>86</td><td>118</td><td>1</td><td>276</td><td>459</td><td>1</td></tr><tr><td>F4</td><td>228</td><td>382</td><td>1</td><td>635</td><td>832</td><td>1</td></tr><tr><td>F5</td><td>276</td><td>336</td><td>1</td><td>313</td><td>463</td><td>1</td></tr></table></body></html>

综上所述，本文提出的VLCMPSO在优化速度，抑制种群多样性丧失从而陷入搜索停滞方面都有极大改善。在单峰问题上性能有所提高且优于大多数算法，其最好的性能是可以有效地在优化多峰问题上避免局部最优解，在多峰函数上本文提出的VLCMPSO求解效果最佳。

# 4 结束语

本文分析了粒子群优化算法的模型，介绍了自适应权重改进策略。在其基础上进一步提出动态学习因子的策略，使得算法搜索过程具有着重点，提高执行效率。判断到种群停滞时，以混沌映射遍历当前位置且以新的更新方式进行寻优搜索。经过仿真实验证明了改进方法的正确性以及优化效果的高效性。本文采用的学习因子动态调整是根据迭代进化过程变化的，下一步工作是如何调整得到更精确的学习因子，然后应用于最新的研究领域。

# 参考文献：

[1]Kennedy J,Eberhart R.Particle swarm optimization [C]// Proc of IEEE International Conference on Neural Networks.1995:1942-1948.   
[2]Shi Y,Eberhart R C.Parameter selection in particle swarm optimization [C]//Proc of International Conference on Evolutionary Programming. Berlin: Springer,1998:591-600.   
[3] 张水平，王碧，陈阳．基于逐层演化的群体智能算法优化[J].工程科 学学报,2017,39(3):462-473.   
[4]TaherkhaniM,Safabakhsh R.Anovel stability-based adaptive inertia weight for particle swarm optimization [J].Applied Soft Computing,2016,38: 281- 295.   
[5]张水平，王碧．动态搜索空间的粒子群算法[J].计算机应用研究,2016, 33(7):2047-2050,2067.   
[6]Hewahi N.Ahybrid approach based on genetic algorithm and particle swarm optimization to improve neural network classification [J].Journal of Information Technology Research,2017,10(3): 48-68.   
[7] 黄开启，陈荣华，丁问司.凿岩机器人钻臂定位控制交叉精英反向粒子 群算法[J].控制理论与应用,2017,34(3):303-311.   
[8]Khare A,Rangnekar S.A review of particle swarm optimization and its applications in Solar Photovoltaic system [J].Applied Soft Computing,2013, 13 (5):2997-3006.   
[9] 张超，李擎，王伟乾，等．基于自适应搜索的免疫粒子群算法[J]．工 程科学学报,2017,39(1):125-132.   
[10]吴晓军，杨战中，赵明．均匀搜索粒子群算法[J]．电子学报,2011,39 (6): 1261-1266.   
[11]吕立国，季伟东．结合质心思想和柯西变异策略的粒子群优化算法[J]. 计算机应用,2017,37(5):1369-1375.   
[12]赵新超，刘国莅，刘虎球，等．基于非均匀变异和多阶段扰动的粒子群 优化算法[J].计算机学报,2014,37(9):2058-2070.   
[13]彭建新，詹志辉．全局信息引导的改进粒子群优化算法[J].小型微型 计算机系统,2016,37(7):1518-1521.   
[14] ZhangQ，Liu W,Meng X,etal.Vector coevolvingparticle swarm optimizationalgorithm [J].Information Sciences,2017,394(7):273-298.   
[15]温正．精通MATLAB 智能算法[M].北京：清华大学出版社，2015: 121-124.