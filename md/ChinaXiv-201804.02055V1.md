# 一种基于动态惯性权重的鸟群优化算法

高宏进，王力

(贵州大学 大数据与信息工程学院，贵阳 550025)

摘要：鸟群算法（BSA）作为一种新型的元启发式群智能算法，存在易陷入局部最优、收敛速度慢和求解精度低等问题。针对原鸟群算法在求解最优化问题中的不足，提出一种基于动态惯性权重的鸟群优化算法(DBSA)。该算法通过引入非线性动态惯性权重修正鸟群飞行间隔，平衡种群全局搜索与局部搜索能力；在模拟鸟群生产者觅食的过程中引入莱维飞行，替换原算法中生产者的觅食策略提高算法活力和有效性。实验表明改进后的鸟群算法有效提高了算法的收敛速度和寻优精度。

关键词：鸟群算法；函数优化；动态惯性权重；莱维飞行 中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2017.11.0784

# Bird swarm alogrithm based on dynamic inertia weight

Gao Hongjin, Wang Li (School ofBigDate&Information Engineering Guizhou University,Guiyang 55o025,China)

Abstract: Asanew kindofheuristicswarm intellgence algorithm,theBird SwarmAlgorithm (BSA)easilyfals into problems about local optimal,slow convergence speedand lowresolution accuracy.Consideringthefactthattheoriginal Bird Swarm Algorithmisotsuicient tosolvetheissue intermsofoptimization,thispaperproposesanoptimizationalgorithm,Dyamic Inertia Weight-BirdSwarmAlgorithm(DBSA).Thealgorithmcorrcts birds flying intervalbyintroducing nonlineardynamic inertia weight,balancingtheabilitiesofpopulation globalsearchandlocalsearch;this paperintroduces theparameteroflevy flightinthe processofsimulatiooftheforaging birdsproducer,advancingalgorithm'svitalityandefectiveness viareplacing the riginalalgorithmproducers foraging strategies.Asaresult,experiments showthatthe modifiedalgorithmimproves the convergence speed and optimization accuracy effectively.

Key Words: birds swarm algorithm; Function optimization; dynamic inertia weight; Levy flight

# 0 引言

鸟群算法[1]（bird swarmalogrithm，BSA）是由Meng等人于 2015年提出的一种基于鸟群行为的群智能优化算法，其思想源于鸟群的三个主要群体行为，即飞行行为、觅食行为和警戒行为[2],BSA算法依赖飞行行为跳出局部最优进行全局搜索，通过觅食行为记录个体和群体最好的解，通过觅食行为和警戒行为的随机切换搜索当前局部的最优解，而通过飞行间隔 FQ来平衡算法全局搜索和局部搜索的能力[3]。BSA算法不仅具有运算速度快、鲁棒性好等优点，而且在解决多邻域最优化问题时具有明显优势[4'5]。此外改进算法提高算法性能也成为一个重要的研究领域，本文针对BSA算法在求解复杂函数时易陷入局部最优、收敛速度慢和寻优精度低等问题，提出一种基于动态惯性权重的鸟群优化算法（birdswarmalgorithmbasedondynamic inertiaweight，DBSA），通过引入非线性动态惯性权重修正鸟群飞行间隔，从而平衡算法局部搜索与全局搜索之间关系；通过引入莱维飞行提高算法活力及有效性，克服早熟。实验结果表明，DBSA算法能够有效提高算法的收敛速度和寻优精。

# 1 经典鸟群算法

鸟群算法是对鸟群群体行为和群体互动的简化，它模仿的是鸟群的飞行行为、觅食行为和警戒行为，并用这种群体智慧解决最优化问题[6-7]。鸟群算法可以被如下规则简化描述[8]：

a）鸟群中的每只鸟可以在觅食行为和警戒行为之间随机切换。b）觅食期间，每只鸟可以迅速记录和更新个体和群体之间最好的觅食经验，这个经验将用于觅食，群体信息将即刻共享于整个鸟群。

c）保持警戒的时候，每只鸟都试图向群体中心靠近，而具有较高食物储量的鸟类更倾向于向群体中心靠近。

d）鸟类可以周期性地向其他位置移动。当移动到另一个位置时，鸟类一般要在生产者和乞讨者之间作出选择，具有最高食物储量的鸟将成为生产者，而具有最低食物储量的鸟将成为乞讨者，其他鸟将随机选择成为生产者和乞讨者。

e)生产者积极寻觅食物，乞讨者随机跟随一个生产者寻找食物。

经典鸟群算法流程图如图1所示。

![](images/92f0f1ab3cae5c9886be65f623ffee26bb551d21415a06f26d9279ea5517b5eb.jpg)  
图1经典鸟群算法流程图

假设有 $N$ 只鸟在 $D$ 维空间中飞行觅食，第i只鸟在 $t$ 时刻的位置描述为

$$
\boldsymbol { x } _ { i } ^ { t } \big ( i \in [ 1 , 2 , 3 , \cdots , N ] \big )
$$

基于规则a)，每只鸟的决策依赖于一个[0,1]的随机数，同时设定一个常量P，当随机数小于 $\mathrm { ~ \bf ~ P ~ }$ 时，该鸟将进行觅食，否则，保持警戒[8]。

基于规则b)，鸟群的觅食行为遵从每只鸟自身的经验以及种群经验，觅食行为的位置更新公式为

$$
\begin{array} { c } { { x _ { i , j } ^ { t + 1 } = x _ { i , j } ^ { t } + \left( p _ { i , j } - x _ { i , j } ^ { t } \right) \times C \times r a n d \left( 0 , 1 \right) + } } \\ { { \left( g _ { i } - x _ { i , j } ^ { t } \right) \times S \times r a n d \left( 0 , 1 \right) } } \end{array}
$$

其中： $j \in [ 1 , \cdots , D ] ,$ rand(0.1)表示在[0,1]均匀分布的随机数， $c$ （204号和 $s$ 是两个正数，分别称为感知系数和社会加速系数。 $p _ { i , j }$ 表示第 $i$ 只鸟早先的最佳位置， $g _ { i }$ 表示群体共享的早先最佳位置[9]。

基于规则c)，鸟群保持警戒时尝试向种群中心移动，并伴随着与同类的竞争，因而不能直接向种群中心移动，警戒行为的位置更新公式为

$$
\begin{array} { c } { { x _ { i , j } ^ { t + 1 } = x _ { i , j } ^ { t } + A _ { 1 } \left( m e a n _ { j } - x _ { i , j } ^ { t } \right) \times r \mathrm { a n d } \left( 0 , 1 \right) + } } \\ { { A _ { 2 1 } \left( p _ { i , j } ^ { t } - x _ { i , j } ^ { t } \right) \times r \mathrm { a n d } \left( - 1 , 1 \right) } } \end{array}
$$

$$
A _ { 1 } = a _ { 1 } \times \exp \left( - \frac { p F i t _ { i } } { s u m F i t + \varepsilon } \times N \right)
$$

$$
A _ { 2 } = a _ { 2 } \times \exp \left( - \frac { p F i t _ { i } - p F i t _ { k } } { \left| p F i t _ { k } - p F i t _ { i } \right| + \varepsilon } \times N \times \frac { p F i t _ { k } } { s u m F i t + \varepsilon } \right)
$$

其中， $k \big ( k \neq i \big )$ 是一个[1，N]之间的随机正整数。 $a _ { 1 }$ 和 $a _ { 2 }$ 是两个[0,2]的常量， $p F i t _ { i }$ 表示第 $i$ 只鸟的最佳适应度值，sumFit表示整个种群的最佳适应度值之和。 $\varepsilon$ 是为了避免零因子错误而由计算机产生的最小常量。 $m e a n _ { j }$ 表示整个种群平均位置的第$j$ 个元素。 $A _ { 1 }$ 描述的是一只鸟向鸟群中心移动时由环境引发的间接作用， $A _ { 2 }$ 描述的则是由某个具体冲突引发的直接作用。

基于规则d)e)，鸟类会因逃避捕食等原因变动飞行中的位置，每当其飞行到一个新的位置，将在生产者和乞讨者之间作出选择，自行觅食或者跟随生产者获取食物，飞行行为中生产者和乞讨者的位置更新公式分别为

$$
{ x _ { i , j } ^ { t + 1 } = x _ { i , j } ^ { t } + x _ { i , j } ^ { t } \times \mathrm { r a n d } n \big ( 0 , 1 \big ) }
$$

$$
{ \boldsymbol { x } } _ { i , j } ^ { t + 1 } = { \boldsymbol { x } } _ { i , j } ^ { t } + \left( { \boldsymbol { x } } _ { k , j } ^ { t } - { \boldsymbol { x } } _ { i , j } ^ { t } \right) \times { \cal F L } \times \mathrm { r a n d } \left( 0 , 1 \right)
$$

其中：rand $n \big ( 0 , 1 \big )$ 表示均值为0、标准差为1的高斯随机分布，$F L \in \left[ 0 , 2 \right]$ 代表乞讨者跟随生产者寻找食物。 $F Q$ 表示鸟群的飞行间隔，其值是一个正整数。

# 2 基于动态惯性权重的鸟群优化算法

# 2.1 动态惯性权重

动态惯性权重是一种控制种群搜索能力和开发能力的机制，能够有效平衡局部搜索与全局搜索之间的关系，提高算法搜索速度与精度避免陷入局部最优[9]。Shi和Eberhart将惯性权重引入例子群算法，有效提高了算法的局部和全局寻优能力[10]。

在BSA算法中飞行移动间隔 $F Q$ 直接决定算法能否跳出局部最优点寻找到全局最优， $F Q$ 越大，全搜索能力越强，越易跳出入局部最优； $F Q$ 越小，局部搜索能力越强，越易陷入局部最优。在迭代前期，算法需要较强的全局搜索能力， $F Q$ 较大为宜；随着迭代次数的增加，算法需要更强的局部搜索能力， $F Q$ 较小为宜。

在BSA算法中 $F Q$ 设置为常数不能较好的平衡两者之间的关系，为更好地提高算法的搜索性能，本文引入动态惯性权重来设定 $F Q$ 的数值。经测试发现使用非线性惯性权重效果最好、效率最高，满足BSA算法前期需要较强的全局搜索能力，后期需要较强的局部搜索能力的要求，较好地平衡了搜索速度和精度。引入非线性惯性权重的FQ更新模式如式（8）所示。

$$
F Q ( i ) =
$$

$$
\mathrm { f l o o r } \left( \big ( F Q _ { \mathrm { m a x } } - F Q _ { \mathrm { m i n } } \big ) \times \mathrm { e x p } ^ { 3 } \left( - 2 \times \left( \frac { i } { M } \right) \right) + F Q _ { \mathrm { m i n } } \right)
$$

$$
F Q _ { \mathrm { m a x } } > F Q _ { \mathrm { m i n } }
$$

其中： $F Q ( t )$ 代表当前代的 $F Q$ 值， $F Q _ { \operatorname* { m a x } }$ 为最大惯性权重，本文取值为15， $F Q _ { \mathrm { m i n } }$ 为最小惯性权重，本文取值为4，M为最大迭代次数，floor(为取整函数，保证所得FQ为整数。

# 2.2莱维飞行

莱维分布是法国数学家PaulLevy提出，Benoist-Madelbrot进行描述的一种稳定分布[1]，这是一种短距离游走与小概率长距离搜索相间的随机游走模式[12]。研究表明莱维飞行现象在自然界中十分普遍，许多生物的行为都符合莱维飞行轨迹。莱维飞行在搜索过程中大部分时间会在某一范围内活动，小部分时间会进行大范围的跳跃，并且运动方向随机化[13]，这样就能保证算法跳出局部最优点，避免早熟。

本文将莱维飞行引入鸟群算法，对鸟群生产者觅食行为进行改进，提高算法活力及有效性，引入莱维飞行对生产者觅食更新模式如式（9）所示。

$$
\boldsymbol { x } _ { i , j } ^ { t + 1 } = \boldsymbol { x } _ { i , j } ^ { t } + \boldsymbol { x } _ { i , j } ^ { t } \times L e \nu y ( \boldsymbol { \lambda } )
$$

其中： $\boldsymbol { x } _ { i , j } ^ { t + 1 }$ 表示第 $t + 1$ 代鸟群第 $i$ 只鸟第 $j$ 维的值， $\boldsymbol { x } _ { i , j } ^ { t }$ 表示 $t$ 代鸟群第 $i$ 只鸟第 $j$ 维的值， $L e \nu y ( \lambda )$ 是步长服从莱维分布的随机搜索向量， $\lambda$ 为莱维飞行步长，取值范围为[1，3]，一般取值为1.5.

# 2.3改进的BSA算法流程图

改进的鸟群算法流程如图2所示。

![](images/1d3fd2b78c41aa23a8ab8551b759e5a1bcb32a545728bdcfd3041750e9400f2d.jpg)  
图2DBSA算法流程图

# 3 实验结果与分析

为验证改进后的DBSA算法性能，本文特选取下列七个标准测试函数对BSA、DBSA和PSO 算法进行对比实验。BSA、DBSA和PSO算法相关参数设置如表1所示，标准测试函数如表2所示，实验对每种函数独立运行30次，记录实验结果如表3所示。

本文所选的测试函数中，除f1、f2函数是单峰函数外，其余 f3\~f8 都是非线性的多峰函数。函数 Sphere 是一个碗状的单极值函数；函数Trid的搜索空间、最优解以及极值点都与搜索维度有关；Ackley是指数函数叠加放大而得到的一个连续性实验函数，四周呈现起伏不平，中间急剧下降的状态，极为考验算法的搜索能力；函数Dixon-Price最优取值点与其搜索维度有关；Hartman3-D和Hartman 6-D是具有复杂系数且有多个局部最小值的函数；函数Shekel具有m个局部最小值且函数系数复杂，导致算法搜索十困难。

表1实验参数设置   

<html><body><table><tr><td>算法</td><td>参数取值</td></tr><tr><td rowspan="2">BSA</td><td>M=100，pop=50,FQ=10</td></tr><tr><td>c1=c2=1.5,a1=a2=1</td></tr><tr><td rowspan="2">DBSA</td><td>M=100，pop=50,FQ=[15,4]</td></tr><tr><td>c1=c2=1.5,a1=a2=1</td></tr><tr><td>PSO</td><td>ω =0.78,h1=h2=1.5</td></tr></table></body></html>

# 3.1 寻优结果比较

表3给出了BSA、DBSA和PSO算法的寻优结果，结果表明对于单峰函数f1而言，BSA算法的寻优精度远高于PSO算法，DBSA算法在BSA算法基础上进一步改善了解的质量，搜索结果更为准确；对于f2函数无论是 $\mathrm { d } { = } 6$ 还是 $\scriptstyle \mathbf { d } = 1 0$ ，BSA和PSO算法都无法有效找到最优点，而DBSA算法则很好地获得了函数的全局最优解；对于多峰函数f3而言，BSA算法寻优精度远高于PSO 算法，DBSA算法与BSA 算法相比寻优精度提高约10个数量级；对于f4函数BSA算法寻优精度与PSO算法相当，DBSA 算法与BSA 算法相比寻优精度提高约20 个数量级；f5f6函数是系数为矩阵形式的测试函数，对于这类函数，BSA算法寻优误差最大，PSO 算法次之，DBSA 算法寻优精度最高；f7函数不仅系数复杂而且最优解与m有关，BSA算法在 $\mathbf { m }$ 不同的三种情况下都不能找到最优解；PSO的寻优结果略优于BSA算法；DBSA算法在三种情况下都能较好的找到最优解，寻优结果较BSA算法有显著提高。根据表3的统计结果显示，DBSA算法在这7个函数上的搜索能力显著优于BSA算法和PSO 算法。

# 3.2 收敛性能比较

图3\~12给出了BSA、DBSA和PSO三种算法函数适应度随迭代次数的变化曲线，从图3可以看出，对于函数f1DSA算法和BSA算法都能有较好的收敛趋势，但DBSA算法较BSA算法收敛速度更快，PSO 算法收敛最慢；从图4\~7可以看出，PSO 和BSA 算法对于f2\~f4 函数均不能有良好的收敛态势，BSA 算法的收敛状态优于PSO 算法，改进后的DBSA算法无论在收敛速度和收敛稳定性较BSA 算法都有显著提高且显著优于PSO 算法；从图8\~12可以看出BSA对于函数f5\~f7均没有较好的收敛态势，不仅前期收敛速度满而且后期不能保持稳定，图10虽能保持稳定但不能找到全局最优解，收敛状态显著劣于PSO 和DBSA 算法，相较与PSO 算法，DBSA显然有更好的收敛速度和稳定状态。综上所述，本文所提的DBSA算法收敛稳定性及收敛速度都显著优于BSA算法和PSO 算法。

表2标准测试函数  

<html><body><table><tr><td colspan="6">长2 标准测试函数 函数名 函数表达式</td><td colspan="2">维度 理论最优解</td></tr><tr><td>Sphere</td><td colspan="4">f(x)= i= x</td><td>[-5.12,5.12]</td><td>d=20</td><td>f(x)=0</td></tr><tr><td>Trid</td><td colspan="4">∑xxi- f(x）=</td><td></td><td colspan="2">d=6</td></tr><tr><td></td><td colspan="4"></td><td>[-d²,d²]</td><td colspan="2">d=10</td></tr><tr><td>Ackley</td><td colspan="4">f（</td><td>[-32.768,32.768]</td><td colspan="2">d=20</td></tr><tr><td>Dixon-Price</td><td colspan="4">f(x)=(x-1）²+∑i(2x²-xi）²</td><td>[-10,10]</td><td>d=20</td><td>f(x*)=0 f(x*)=0</td></tr><tr><td>Hartman 3-D A=</td><td colspan="6">fs（x）=-∑exp{-∑A(x-）² α =(1.0,1.2,3.0,3.2) （36891170 2673) (0,1)</td><td></td></tr><tr><td colspan="2" rowspan="4"></td><td colspan="5">(3.01030)</td><td rowspan="2">d=3</td><td rowspan="2">f(X*)=-3.86278</td></tr><tr><td>0.1 10 35 3.0 10 30</td><td>P=104</td><td></td><td>4699 4387 7470 1091 8732 5547</td><td></td></tr><tr><td>(0.110 35)</td><td></td><td>381</td><td>5743 8828</td><td></td><td></td><td></td></tr><tr><td></td><td>f6(x)=-∑a,expl</td><td>α =(1.0, 1.2, 3.0, 3.2)T A（</td><td></td><td></td><td></td><td></td><td>f(X*)= -3.32237</td></tr><tr><td rowspan="8">Hartman 6-D</td><td></td><td></td><td>3 17</td><td>3.5 17 8</td><td>8）</td><td></td><td rowspan="2">d=6</td><td rowspan="2"></td></tr><tr><td>10 0.05</td><td>10</td><td>17</td><td>0.1</td><td>14</td><td></td></tr><tr><td>A=</td><td>3 3.5</td><td>1.7</td><td>10 17</td><td>8</td><td>(0,1)</td><td rowspan="5"></td></tr><tr><td></td><td>17</td><td>8 0.05</td><td>10</td><td>0.1 14)</td><td></td></tr><tr><td>(1312</td><td>1696</td><td>5569 8307</td><td>124 3736</td><td>8283 5886) 9991</td><td></td></tr><tr><td>P=10-4 2348</td><td>2329 4135</td><td>3522</td><td>2883</td><td>1004 3047</td><td></td></tr><tr><td>（4047</td><td>1451 8828</td><td>8732</td><td>5743</td><td>6650 1091 381</td><td></td></tr><tr><td></td><td>f(x)</td><td></td><td></td><td></td><td></td></tr><tr><td rowspan="5">Shekel</td><td>2, 2, 4,4, 6,3, 7, 5, 5)T β=1</td><td></td><td></td><td></td><td>+β</td><td></td><td rowspan="2"></td><td rowspan="2">m=5 = -10.15</td></tr><tr><td></td><td></td><td>J=</td><td></td><td></td><td></td></tr><tr><td>(4.0 1.0</td><td>10(1, 8.0</td><td>6.0 3.0</td><td>2.0</td><td>5.0 8.0</td><td>6.07.0)</td><td rowspan="2">[0,10] d=4</td><td rowspan="2">f(x*)=-10.40</td></tr><tr><td>4.0 1.0 8.0</td><td></td><td>6.0</td><td>7.0 9.0</td><td>3.01.0</td><td>2.03.6</td><td></td></tr><tr><td colspan="2">C： 4.0 1.0 4.01.0 8.0 6.0</td><td>8.0 6.0</td><td>3.0 2.0 7.0</td><td>5.0 9.0 3.0</td><td>8.0 6.0 1.0</td><td>7.0 2.03.6)</td><td colspan="2">m=10</td></tr></table></body></html>

# 3.3 时间性比较

表4给出了BSA、DBSA和PSO 算法迭代100次的运行时间对比，每种算法迭代100代，可以看出DBSA算法和BSA算法在运行时间上并无较大差别，较PSO少用时约0.1s，这是因为DBSA算法虽因引入莱维飞行，计算复杂度大幅增加，但由于本文同时引入了动态惯性权重的飞行间隔更新策略，有效减少了莱维飞行次数，所以DBSA算法在运行时间上较BSA算法的增加并不明显，这说明在大幅提高BSA 算法活力和准确性，显著提高算法收敛速度的前提下，这种改进策略是可取的。

# 4 结束语

针对鸟群算法在求解最优化函数中存在易陷入局部最优、收敛速度慢、求解精度低等问题，本文提出一种基于动态惯性权重的鸟群优化算法，通过引入非线性动态权重更新飞行间隔，以此分配算法局部搜索与全局搜索资源，平衡算法搜索精度与速度；引入莱维飞行来对生产者觅食策略进行修正，提高算法活力。通过对七个标准测试函数实验表明，与传统BSA算法相比，DBSA算法可以有效提高搜索精度，，增强收敛速度，与BSA算法相比，本文所提算法在求解多维复杂函数最优化的问题上是具有竞争力的。

表3BSA与LWBSA算法的比较结果  

<html><body><table><tr><td rowspan="2">函数</td><td rowspan="2">算法</td><td colspan="3">寻优结果</td></tr><tr><td>最佳寻优值</td><td>平均寻优值</td><td>最差寻优值</td></tr><tr><td rowspan="3">f(x)</td><td>BSA</td><td>5.2034e-137</td><td>4.3752e-136</td><td>1.1528e-134</td></tr><tr><td>DBSA</td><td>0</td><td>1.2931e-143</td><td>2.3754e-142</td></tr><tr><td>PSO</td><td>0.0032</td><td>0.0584</td><td>0.2486</td></tr><tr><td rowspan="6"></td><td>BSA</td><td>-48.3533</td><td>-30.4774</td><td>-2.4395</td></tr><tr><td>DBSA</td><td>-50</td><td>-50</td><td>-50</td></tr><tr><td>PSO</td><td>-47.6951</td><td>-20.1855</td><td>20.3340</td></tr><tr><td></td><td>-107.6532</td><td>-83.5703</td><td>6.6080</td></tr><tr><td>BSA DBSA</td><td>-210</td><td>-209.9992</td><td>-209.9946</td></tr><tr><td>PSO</td><td>178</td><td>571.2</td><td>1214</td></tr><tr><td rowspan="3">f(x）</td><td></td><td></td><td></td><td></td></tr><tr><td>BSA</td><td>8.8816e-16</td><td>4.7533e-4</td><td>0.2746</td></tr><tr><td>DBSA</td><td>1.5099e-25</td><td>6.5027e-19</td><td>2.8031e-17</td></tr><tr><td rowspan="3">f4（x)</td><td>PSO</td><td>0.0082</td><td>1.9633</td><td>3.1267</td></tr><tr><td>BSA</td><td>0.0169e-2 1.06e-27</td><td>0.0079</td><td>0.0732</td></tr><tr><td>DBSA</td><td>9.2372e-2</td><td>9.9781e-24 6.6929e-1</td><td>9.9435e-20 6.6667e-1</td></tr><tr><td rowspan="3">f(x)</td><td>PSO</td><td></td><td></td><td></td></tr><tr><td>BSA</td><td>-3.85145</td><td>-2.97580</td><td>-2.76660</td></tr><tr><td>DBSA</td><td>-3.86278</td><td>-3.86278</td><td>-3.86278</td></tr><tr><td rowspan="3">f(x)</td><td>PSO</td><td>-3.86278</td><td>-3.86275</td><td>-3.86217</td></tr><tr><td>BSA</td><td>-3.06774</td><td>-2.50341</td><td>-1.05732</td></tr><tr><td>DBSA</td><td>-3.32237</td><td>-3.32237</td><td>-3.32235</td></tr><tr><td rowspan="9"></td><td>PSO BSA</td><td>-3.32237</td><td>-3.23892</td><td>-3.20316</td></tr><tr><td>m=5 DBSA</td><td>-9.7781 -10.1532</td><td>-5.4377</td><td>-2.6304</td></tr><tr><td>PSO</td><td></td><td>-10.1532</td><td>-10.1532</td></tr><tr><td></td><td>-10.1532</td><td>-6.6767</td><td>-3.2868</td></tr><tr><td>m=7</td><td>BSA -10.3100</td><td>-5.2786</td><td>-2.7345</td></tr><tr><td>DBSA</td><td>-10.4029</td><td>-10.4029</td><td>-10.4029</td></tr><tr><td>PSO</td><td>-10.4029</td><td>-7.5916</td><td>-2.7519</td></tr><tr><td>BSA</td><td>-9.8062</td><td>-4.4226</td><td>-2.4261</td></tr><tr><td>m=10 DBSA</td><td>-10.5364</td><td>-10.5364</td><td>-10.5364</td></tr><tr><td></td><td>PSO</td><td>-10.5364</td><td>-5.9940</td><td>-2.4217</td></tr></table></body></html>

![](images/4e13c53f2bae975991f58dcfc6182da3798bc260516ca19385073c0d39470688.jpg)  
图3算法收敛对比图（f1)

![](images/608a463f0435f0940cdbfb6334f61d94449bf2aaab233618aed19694a41bdd7d.jpg)  
图4算法收敛对比图（f2 $\scriptstyle \mathbf { d } = 6$ ）

![](images/365e632b087cf5571d6203bb77cbe7e6a43ca043f887b33590cc66fd04839a54.jpg)  
图5算法收敛对比图（f2 $\scriptstyle \mathbf { d } = 1 0$ ）

![](images/e2d128b143a937ab78606887fb4dccc48aa173af52132f7c2d11c61df3066a67.jpg)  
图6算法收敛对比图（f3）

![](images/f998d9c1cd696f6f2f20cfe322126930db1701c5cbc513af6a83db30400927e3.jpg)  
图7算法收敛对比图（f4)

![](images/685714c547d7491b49ebbbb4efccb798be6716528cf18aa85a30646ed1614732.jpg)  
图8算法收敛对比图（f5)

![](images/e2d2a799a357d6b1e19f699a10d436418c0d1be8f77df6fa04856301e338f816.jpg)  
图9算法收敛对比图（f6)

![](images/6bae0ca9d19cddb46e4b9ba468324f80063079808d71f800fa278b057abd8bc9.jpg)  
图10算法收敛对比图（ $\mathrm { f } 7 \mathrm { m } { = } 5$ ）

![](images/595084abd5754364e34656198e58c8f5f231bc3eeedc825a91988061a532d85f.jpg)  
图11算法收敛对比图（ $\mathrm { f } 7 \mathrm { m } { = } 7$ ）

![](images/855c5b6459fd73a17ae11c6ca820957f707081debc0f294d5540231d47d394cf.jpg)  
图12算法收敛对比图（f7 $\mathrm { m } { = } 1 0$ ）

表4BSA、DBSA与PSO 时间对比  

<html><body><table><tr><td rowspan="3">算法</td><td colspan="5">函数</td></tr><tr><td rowspan="2">f</td><td>f f f4𝑓</td><td rowspan="2">f</td><td>f</td><td></td></tr><tr><td>d=6 d=10</td><td>m=5</td><td>m=7m=10</td></tr><tr><td>BSA</td><td></td><td>0.447s 0.449s 0.496s 0.463s 0.366s 0.506s 0.493s 0.527s 0.544s 0.573s</td><td></td><td></td><td></td></tr><tr><td>DBSA</td><td></td><td>0.439s 0.512s 0.494s 0.569s 0.317s 0.572s 0.474s 0.458s 0.500s 0.600s</td><td></td><td></td><td></td></tr><tr><td>PSO</td><td></td><td>0.573s 0.603s 0.605s 0.636s 0.603s 0.719s 0.751s 0.707s 0.693s 0.696s</td><td></td><td></td><td></td></tr></table></body></html>

# 参考文献：

[1]Meng XB,Gao X Z,LuL,et al.A new bio-inspired optimisation algorithm: bird swarm algorithm [J]. Journal of Experimental & Theoretical Artificial Intelligence, 2015: 1-15.   
[2] 屈迟文，傅彦铭，罗明山，等．求解柔性作业车间调度问题的鸟群算法 [J/OL].计算机工程与应用，(2017-08-24）．http://kns.cnki. net/kcms/detail/11.2127.TP.20170824.0913.010. html.   
[3]曾增，彭春华，王奎，等．基于鸟群算法的微电网多目标运行优化[J]. 电力系统保护与控制,2016,44(13):117-122.   
[4]肖海军，卢常景，何凡．基于鸟群算法的 SVM参数选择[J].中南民族 大学学报：自然科学版,2017,36(3):90-94.   
[5]Parashar M,Rajput S,Dubey H M,et al. Optimization of benchmark functions using a nature inspired bird swarm algorithm [C]// Proc of International Conference on Computational Intelligence & Communication Technology. 2017.   
[6]Cui D,Jin B,Bureau W W. Improved bird swarm algorithm and its application to reservoir optimal operation[J]. Journalof China Three Gorges University, 2016.   
[7]Cui D,Jin B.Application of the bird swarm algorithm-projection pursuit regression model to prediction of multivariate annual runoff[J].Pearl River, 2016.   
[8]Kn L, Reddy DB R,Kalavathi D M S. Snow finch bird swarm optimization algorithm for solving reactive power problem [J]. International Journal of Mathematical Engineering & Management Sciences, 2016.   
[9]周欢，李煜．具有动态惯性权重的布谷鸟搜索算法[J].智能系统学报, 2015,10 (4): 645-651.   
[10] Shi Y,Eberhart R. Modified particle swarm optimizer [C]// Proc of IEEE International Conference on Evolutionary Computation Proceedings.1997: 69-73.   
[11]刘晓龙，宁芊，赵成萍，等．基于莱维飞行的鸟群优化算法[J].计算 机测量与控制,2016,24(12):194-197.   
[12]王庆喜，郭晓波．基于莱维飞行的粒子群优化算法[J].计算机应用研 究,2016,33 (9): 2588-2591.   
[13]牛海帆，宋卫平，宁爱平．莱维飞行与粒子群的混合搜索算法[J]．太 原科技大学学报,2016,37(1):6-11.