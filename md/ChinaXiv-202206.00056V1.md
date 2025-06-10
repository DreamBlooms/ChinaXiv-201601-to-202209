# 融合差分变异和切线飞行的天鹰优化器

徐亦凤，刘升，刘宇淞，张伟康(上海工程技术大学 管理学院，上海 201620)

摘要：针对天鹰优化器(aquila optimizer，AO)虽然拥有强大的全局勘探能力，但局部开发能力不足的问题，提出融合差分变异和切线飞行的天鹰优化器(diffrential evolution mutation and tangent flight aquila optimizer，DEtanAO)。首先，根据差分进化算法中的变异操作能使算法具有较强的开发能力弥补了AO算法的不足，然后，利用切线搜索算法中切线飞行策略具有较强的探索搜索空间的能力并能使算法跳出局部最优解的优势，用其替换了AO算法中的莱维飞行。这两种策略的结合有效地平衡了DEtanAO算法的勘探和开发阶段。最后，为验证DEtanAO算法的优化性能，在12个标准基准函数、高维函数、Wilcoxon 秩和检验和工程优化问题上来测试所改进算法的寻优能力。实验结果表明，相比其他新提出的智能算法，DEtanAO算法具有更强的寻优能力和更快的收敛速度。

关键词：天鹰优化器；差分变异；切线飞行；勘探与开发 中图分类号：TP301.6 doi:10.19734/j.issn.1001-3695.2022.03.0129

Aquila optimizer integrating differential mutation and tangent flight

Xu Yifeng,Liu Sheng†,Liu Yusong, Zhang Weikang (School ofManagement,Shanghai University ofEngineering Science,Shanghai 20l62o,China)

Abstract:TheAquilaoptimizer(AO),although capableof robust global exploration,had problems with inadequate local development.In the study,a diferential evolution mutation and tangent flight Aquilaoptimizer (DEtanAO) was proposed. Firstly,themutationoperationinthedifferentialevolutionalgorithmca makethealgorithmhave strongdevelopmentability and makeupfortheshortcomingsoftheAOalgorithm.Then,the tangent flightstrategyinthetangentsearchalgorithmhasa strong abilitytoexplore the search spaceand can make thealgorithmjump outofthe local optimal solution,which is usedto replace theLevyflight intheAOalgorithm.Thecombinationofthese twostrategies effectivelybalancedtheexplorationand exploitation stageof the DEtanAO algorithm.Finally,inorder to verify the optimizationperformanceof the DEtanAO algorithm，theoptimizationabilityof the improvedalgorithmwastested in12standard benchmark functions,highdimensional functions，Wilcoxonrank-sum test，and engineeringoptimization problems.Theresults showed that the optimization abilityand convergence speed of the DEtanAO algorithm was better,compared with other newly proposed intelligent algorithms.

Key words: aquila optimizer; diferential evolution mutation; tangent flight; exploration and exploitation

# 0 引言

随着现实世界中离散、无约束性质的优化问题越来越复杂，传统的基于数学的优化算法很难找到最优解，并且存在一定的缺点和局限性，例如收敛至局部最优和未知的搜索空间并且对于优化问题的解决方案单一等。为解决上述问题，近年来，基于仿生学的元启发式优化算法不断被提出和改进，并以其操作简便、参数调整简单等特点大受学者青睐，如：加入自适应权重模拟鸟群觅食行为的混沌粒子群算法[1](Chaotic-Particle Swarm Optimization，CPSO)，受麻雀觅食和反哺行为启发提出的麻雀搜索算法[2](Sparrow SearchAlgorithm,SSA)，受海洋适者生存理论启发提出的海洋捕食者算法[3](Marine Predators Algorithm,MPA)，融合了精英反向和黄金正弦策略的鲸鱼优化算法[4](Elite Opposition Based Golden-SineWhale OptimizationAlgorithm，EGolden-SWOA)等等。这些算法的提出为解决复杂的优化问题提供了更多的思路。

天鹰优化器(AquilaOptimizer，AO)l5是LaithAbualigah等人于2021年提出了一种新的基于种群的优化方法，该方法受到自然界中天鹰在捕获猎物过程中行为的启发，具有强大的全局勘探能力、搜索效率高、收敛速度快等优点，但其局部开发能力不足，容易陷入局部最优。王爽等6提出了一种改进的混合天鹰优化器和哈里斯鹰眼优化器(IHAOHHO)将HHO算法的开发策略集成到AO 算法的探索策略中，并添加反向学习策略(ROBL)以避免局部最优停滞。同时，非线性逃逸能量参数平衡了算法的探索和开发阶段。这些改进使得IHAOHHO 算法的寻优性能得到提升；除此之外，Shubham Mahajan[7]等人将 AO 算法和算数优化算法相结合(AO-AOA)来解决优化问题，并在23个基准函数上验证了所提算法的有效性与优越性；王世成[8等人提出了一种改进的多目标天鹰优化器，并用其设计了一款基于混合固体氧化物燃料电池(SOFC)系统的混合动力系统，从而改善了整体成本和用火效率；EricOfori-Ntow $\mathrm { J n r } ^ { [ 9 ] }$ 等人将离散小波变换(DWT)、混沌理论的相空间重构(PSR)、天鹰优化算法(AOA)和反向传播神经网络(BPNN)混合起来提出了DWT-PSR-AOA-BPNN模型，并将其应用于预测风速，实验结果表明该模型预测精度较高。但是由于天鹰优化器提出的时间较短，国内并没有对AO算法的改进进行充分研究，其性能仍有进一步的提升空间以便应用于更多的实际问题中。本文提出一种融合差分变异和切线飞行的天鹰优化器(DEtanAO)，首先在 AO算法中加入差分变异策略，提高算法的搜索精度，接着利用切线搜索算法[1o](Tangent Search Algorithm，TSA)中的切线飞行策略替代AO算法中的莱维飞行策略，进一步优化AO的寻优性能，使其跳出局部最优解。为证明改进算法的有效性，随后在单模态、多模态和高维测试函数上进行多种算法的对比实验，并进行Wilcoxon秩和检验分析，进一步在工程应用问题上检验所提算法的前沿性，结果表明DEtanAO算法的寻优精度、收敛速度有着显著提升。

# 1 天鹰优化器

天鹰优化器模拟了天鹰对不同猎物的不同捕猎方式。天鹰对于快速移动猎物的狩猎方式反映了算法的全局探索能力，对于慢速移动猎物的狩猎方式反映了算法的局部开发能力。AO 算法具有较强的全局探索能力、较高的搜索效率和较快的收敛速度，但其局部开发能力不足，容易陷入局部最优。AO 算法模拟了天鹰在狩猎期间的行为，其优化过程用四种方法表示：通过垂直弯腰的高翱翔选择搜索空间 $\left( X _ { 1 } \right)$ ；通过短滑翔攻击的等高飞行在搜索空间内探索 $\left( X _ { 2 } \right)$ ；通过慢速下降攻击的低空飞行在收敛搜索空间内探索 $\left( { { X } _ { 3 } } \right)$ ，以及通过行走和抓取猎物进行俯冲 $( X _ { 4 } )$ 。

# 1.1拓展探索 $\left( X _ { 1 } \right)$

在第一种方法 $\left( X _ { 1 } \right)$ 中，天鹰识别猎物区域并通过垂直弯腰的高翱翔来选择最佳狩猎区域。在这里，天鹰从高空翱翔来确定搜索空间的区域即搜索猎物在哪里。图1显示了天鹰高翱翔和垂直弯腰的行为。

![](images/1045c5818ea9404af503aa673123bf418f27fbf8a24946e068368446628ccaf9.jpg)  
图1天鹰高翱翔和垂直弯腰的行为

Fig.1The behavior of the Aquila high soar with the vertical stoop 这种行为用数学式(1)表示为

$$
X _ { 1 } \left( t + 1 \right) = X _ { b e s t } \left( t \right) \times \left( 1 - \frac { t } { T } \right) + \left( X _ { M } \left( t \right) - X _ { b e s t } \left( t \right) \right) \times r a n d
$$

$$
{ X } _ { M } \left( t \right) = \frac { 1 } { N } { \sum _ { i = 1 } ^ { N } { { X } _ { i } \left( t \right) } } , \forall j = 1 , 2 , { { \cdots } , { D i m } }
$$

其中， $X _ { 1 } { \big ( } t + 1 { \big ) }$ 是由第一个搜索方法 $\left( X _ { 1 } \right)$ 生成的t的下一次迭代的解， $X _ { b e s t } \left( t \right)$ 是第t次迭代的最优解，这反映了猎物的大致位置。 $( 1 - t / T )$ 表示通过迭代次数控制探索， $X _ { M } \left( t \right)$ 表示当前解决方案在第t次迭代时的平均值。rand是[0,1]之间的随机数。t和T分别表示当前迭代次数和最大迭代次数。Dim是问题的维度， $\mathrm { ~  ~ N ~ }$ 是候选解的个数。

# 1.2缩小探索范围 $\left( X _ { 2 } \right)$ （20

在第二种方法 $\left( X _ { 2 } \right)$ 中，当天鹰从高空找到猎物区域时，会在目标猎物上方盘旋，准备好发动攻击。这种方法称为短滑翔攻击的等高飞行。此时，天鹰优化器狭窄地探索目标猎物的选定区域，为攻击做准备。图2展示了带有短滑翔攻击的天鹰等高飞行的行为。这种行为用数学式(3)表示为

$$
X _ { 2 } \left( t + 1 \right) = X _ { b e s t } \left( t \right) \times l e \nu y \left( D \right) + X _ { R } \left( t \right) + \left( y - x \right) \times r a n d
$$

$$
l e \nu y ( D ) { = } s \times \frac { u \times \sigma } { | \nu | ^ { \frac { 1 } { \beta } } }
$$

$$
\sigma { = } \left( \frac { \Gamma ( 1 { + } \beta ) \times \sin \left( \frac { \pi \beta } { 2 } \right) } { \Gamma \left( \frac { 1 { + } \beta } { 2 } \right) \times \beta \times 2 ^ { \left( \frac { \beta - 1 } { 2 } \right) } } \right)
$$

其中， $X _ { 2 } \left( t + 1 \right)$ 是由第二个搜索方法 $\left( X _ { 2 } \right)$ 生成的t的下一次迭代的解，D表示维度空间， $l e \nu y ( D )$ 是莱维飞行分布函数，$X _ { \scriptscriptstyle R } ( t )$ 是取值范围在[1,N]的随机解。其中， $s$ 为固定为1.5的常量值， $y$ 和 $x$ 在搜索中呈现螺旋形式，其计算公式如下：

$$
\begin{array} { c } { y = r \times \cos ( \theta ) } \\ { \ } \\ { x = r \times \sin ( \theta ) } \\ { \ } \\ { { \mathrm { r } } { = } { \mathrm { r } } _ { 1 } { + } U \times D _ { 1 } } \\ { \ } \\ { \theta { = } { - } \omega \times D _ { 1 } { + } \theta _ { 1 } } \end{array}
$$

其中， $\theta _ { 1 } = { \left( 3 \times \pi \right) } / { 2 }$ ， $r _ { \mathrm { { l } } }$ 为介于1和20之间的固定周期指数，$U$ 的值为0.00565， $D _ { 1 }$ 是1到搜索空间长度的整数， $\omega$ 的值为0.005。

![](images/0497a3db6f286b605ce7804f877a752c74e879e50e75b4ccff9d79ae57ce70f4.jpg)  
图2天鹰短滑翔攻击的等高飞行的行为

在第三种方法 $\left( { { X } _ { 3 } } \right)$ 中，当天鹰锁定了捕食区域，天鹰准备好着陆和攻击，随后垂直下降并进行初步攻击来试探猎物反映，这种行为称为低空飞行和慢速下降攻击。图3展示了天鹰低空飞行和缓慢下降的攻击行为。

![](images/2464ddaeb0f9b4cd0176d48ad2e5c0fa80fe1a117abfc338ec0cd12d2017a88b.jpg)  
Fig.2The behavior of the Aquila contour flight with short glide attack 1.3扩大开发 $\left( { { X } _ { 3 } } \right)$ （20   
图3天鹰低空飞行和缓慢下降的攻击行为

Fig.3The behavior of the Aquila low flight with slow descent attack 这种行为用数学式(10)表示为

$$
\begin{array} { r } { X _ { 3 } \left( t + 1 \right) = \left( X _ { b e s t } \left( t \right) - X _ { M } \left( t \right) \right) \times \alpha - r a n d } \\ { + \left( \left( U B - L B \right) \times r a n d + L B \right) \times \delta } \end{array}
$$

其中， $X _ { 3 } \left( t + 1 \right)$ 是由第三个搜索方法 $\left( { { X } _ { 3 } } \right)$ 生成的t的下一次迭代的解， $\alpha$ 和 $\delta$ 是开采调整参数，其值较小，在(0,1)的范围内， $L B$ 、 $U B$ 分别代表所给问题的上下限。

# 1.4缩小开发范围 $\left( X _ { 4 } \right)$ （20

在第四种方法 $\left( { { X } _ { 4 } } \right)$ 中，当天鹰接近猎物时，它会根据猎物的随机移动攻击猎物，这种方法称为“行走并抓住猎物”如图4所示。

这种行为用数学式(11)表示为

$$
X _ { 4 } \left( t + 1 \right) = Q F \times X _ { b e s t } \left( t \right) - \left( G _ { 1 } \times X \left( t \right) \times r a n d \right) - G _ { 2 } \times l e \nu y ( D )
$$

$$
Q F ( t ) = t ^ { \frac { 2 \times r a n d - 1 } { \left( 1 - T \right) ^ { 2 } } }
$$

$$
G _ { 1 } { = } 2 \times \mathrm { r a n d - } 1
$$

$$
G _ { 2 } { = } 2 \times { \left( 1 { - } \frac { t } { T } \right) }
$$

其中， $X _ { 4 } \left( t + 1 \right)$ 是由第四个搜索方法 $\left( { { X } _ { 4 } } \right)$ 生成的t的下一次迭代的解，QF表示用于平衡搜索策略的质量函数，其中$F \in ( 0 , 1 )$ ， $G _ { \imath }$ 表示猎物在逃逸过程中天鹰采用的不同方法，$G _ { 2 }$ 表示从2到0的递减值，代表了天鹰在追踪猎物时从第一个位置到最后一个位置时的飞行坡度。 $Q F ( t )$ 是第t次迭代时的质量函数值，rand是(0.1)的随机数，t和T分别表示当前和最大的迭代次数。图5是AO算法流程。

![](images/6ec73cf3fc3d10b3e914c0072752ffb836f017745ad1d733dd69b5561e9dc34b.jpg)  
图4行走并抓住猎物进行俯冲的行为

![](images/5ae94cd8bd9b9d5bc13cd79e6b0ef24ebf9d6a7bdd9a0a283cfadd4329c7c441.jpg)  
Fig.4Behavior of the Aquila walk and grab prey   
图5AO算法流程

在AO算法的两个阶段，都需要添加贪心算法来保证个体的新位置优于其原位置。从AO算法的实现公式来看，四个位置更新公式中，式(1)和(11)会向0收敛，式(10)会收敛到常数，只有式(3)勉强会收敛至最优解，故AO算法易陷入局部最优。

# 2 改进的天鹰优化器(DEtanAO)

# 2.1差分变异策略

差分进化算法[I](DE)是一种基于种群进化的算法。通过对种群采取三种进化操作：变异操作、交叉操作以及选择操作进行迭代使算法趋于全局最优解。DE算法利用差分这种变异操作来产生变异种群作为新的个体；再通过交叉操作，对变异种群和原始种群进行交叉，得到交叉种群；对原始种群和交叉种群利用贪婪选择选取下一代种群。差分变异指的是DE通过两个不同父代向量做差，实现变异个体与差分向量的结合，常用的变异策略如表1所示。

表1中 $F \in ( 0 , 1 )$ 为缩放因子， $r _ { 1 } \neq r _ { 2 } \neq r _ { 3 }$ 且 $r _ { \mathrm { i } }$ 、、 $r _ { 3 }$ 为随机整数， $X _ { b e s t , j } ^ { t }$ 表示第 $j$ 代最优个体， $V _ { i , j } ^ { t }$ 表示变异后的个体， $X _ { i , j } ^ { t }$ 表示第 $j$ 代第i个个体， $X _ { r _ { i } , j } ^ { t }$ 、 $X _ { r _ { 2 } , j } ^ { t }$ 、 $X _ { r _ { 3 } , j } ^ { t }$ 表示当前种群中随机选取的不同个体。

基于“best”的变异策略具有良好的开发能力和快速收敛的性能，以天鹰当前种群中适应度最好的个体作为基矢量，式中 $X _ { r _ { 2 , j } } ^ { t }$ 、 $X _ { r _ { 3 , j } } ^ { t }$ 由天鹰种群随机产生。其中，变异算子 $F$ 随着迭代次数的增加动态随机变化，在算法迭代初期， $F$ 值较小时，缩放因子对变异的影响较小，天鹰的变异受群体中最优天鹰的影响，变异的天鹰会快速朝向群体最优个体靠近；在算法运行后期，F值较大时，缩放因子对变异影响较大，天鹰聚集在最优天鹰个体的周围，使得种群在最优个体周围进行局部细致探索，提高算法的搜索精度。

表1变异策略  
Tab.1 Variation strategy   

<html><body><table><tr><td>变异策略</td><td>数学表达式</td></tr><tr><td>DE/rand/1</td><td>Vi/j=X+F(x-X)</td></tr><tr><td>DE/best/1</td><td>Vij =Xbest,j+F(X,-X,)</td></tr><tr><td>DE/current-to-best/1</td><td>Vj=X+F（Xbestj-Xij）+F（Xj-）</td></tr></table></body></html>

# 2.2切线飞行策略

切线搜索算法[lo](The TangentSearchAlgorithm，TSA)是2021年提出的一种新的基于种群的优化算法。TSA 使用一个基于切线函数的数学模型将给定的解移向更好的解。无论是基于导数还是基于微分的最优化算法都是类似于下式(15)的下降等式：

$$
X ^ { t + 1 } = X ^ { t } + s t e p ^ { * } d
$$

其中 step 是移动的大小，d是移动的方向。最优化算法的区别在于如何计算步长，基于导数的方法使用梯度下降法或海森矩阵；然而基于微分的方法中，例如元启发式算法，它们使用随机步骤收敛到全局最优。比如，遗传算法[12]使用高斯变异作为步长；差分进化算法[13]通过当前种群个体之间的差值来计算步长；布谷鸟搜索算法[14]是通过莱维飞行函数来计算步长。

步长的优化对于算法的优化极为关键，步长的大值有利于探索，小值有利于开发。TSA算法中提出了一种基于切线函数的新的步长，称之为切线飞行，切线函数有助于有效地探索搜索空间。全局和局部游走相结合的探索搜索方程由下式(16)所表示。

$$
X ^ { t + 1 } = X ^ { t } + s t e p ^ { * } \tan ( \theta )
$$

从数学逻辑上讲，越接近 $\pi / 2$ 的 $\theta$ ，切值越大，得到的解离当前解越远；越接近0的 $\theta$ ，切值越小，得到的解越接近当前解。探索搜索方程应用于概率为1/D的每个变量，其中D为问题的维数。

用切线飞行函数替代天鹰优化器中的莱维飞行函数使AO在规避局部开发不足的同时又进一步提高AO算法的全局探索能力，图6、7是用 Mantegna方法[15]模拟1000 次的莱维飞行和切线飞行的随机游走示意图。

![](images/b9084485641fa182bfd5b97bb06136247f2c1bf8fb70730d7b9773653cf02048.jpg)  
Fig.5The flow chart of AO algorithm   
Fig.6A diagram of the Levy Flight random walk

从图6、7可以看出莱维飞行产生的步幅随机性大、步长区间窄，导致传统算法可能出现在迭代前期搜寻距离过小，而在迭代末期搜寻出现搜寻距离过大的问题，使得算法优化迭代周期过长，精度不足；然而切线飞行出现大跨步的频率要比莱维飞行高，弥补了莱维飞行搜寻距离过大过小的问题，切线飞行比莱维飞行更有利于跳出局部最优解并进行大范围的搜索，使得天鹰获得更多的捕食机会。

# 2.3DEtanAO的时间复杂度分析

时间复杂度分析通常依赖于三个规则：种群初始化、计算适应度函数和更新解。假设种群数量为N，O(N)是种群初始化过程的计算复杂性， $\mathrm { O ( T \times N ) 4 O ( T \times N \times D i m ) }$ 是解的更新过程的计算复杂性，其中，总迭代次数称为T，问题维度为Dim。因此，AO的总的时间复杂度为 ${ \mathrm { O } } ( { \mathrm { N } } \times ( { \mathrm { T } } \times { \mathrm { D } } + 1 )$ ）

![](images/cf75484c4ff55ee67e790bc3530a004e4385b138d6d3aae7c987fa43d85ab212.jpg)  
图7切线飞行随机游走示意图  
Fig.7Tangential flight random walk schematic

由标准AO的复杂度可知，DEtanAO仅添加了差分进化算法中的变异策略 $\mathrm { O ( T \times N ) }$ ，并将原来的Levy飞行策略变成tangent飞行策略，不增加计算复杂性。因此，DEtanAO的总的时间复杂度为 $\mathrm { O ( N \times ( T \times ( D + 1 ) + 1 ) ) } ,$ L。

综上分析，DEtanAO算法复杂度与标准AO算法是时间复杂度属于同一级别，并未增加额外的计算阶级。DEtanAO算法的伪代码如下所示。

算法Pseudo-code of the DetanAO 输入： $i , e , \alpha , \delta , e t c$ （204号 输出:best position、best fitness Initialization the population %种群初始化 Define initial parameter( $i , e , \alpha , \delta , e t c$ ）%定义初始参数 while(The end condition is not met） do Calculate the fitness function values and the best obtained solution $X _ { \mathrm { { b e s t } } } ( t )$ ．%计算最佳适应度值 for $( \mathtt { i } \mathtt { = } 1 , 2 , \cdots , \ \mathtt { N } )$ do Update the $X _ { M } \left( t \right) , x , y , G _ { 1 } , G _ { 2 } , L e \nu y ( D ) , e t c$ %更新各参数 Expanded exploration $\left( X _ { 1 } \right)$ ：Update the current solution using Equation(1）%拓展探索：用式(1)更新位置1 Narrowedexploration $\left( X _ { 2 } \right)$ ：Updatethe current solution using Equation(3）%缩小探索范围：用式(3)更新位置2 Expanded exploitation $\left( { { X } _ { 3 } } \right)$ ：Update the current solution using Equation(10）%扩大开发：用式(10)更新位置3 Narrowed exploitation $\left( { { X } _ { 4 } } \right)$ ：Update the current solution using Equation(11）%缩小开发范围：用式(11)更新位置4 end for for Mutation:generate a mutant population %差分变异策略 end for end while function tangent flight %切线飞行策略 end

# 3 仿真实验与结果分析

# 3.1仿真实验环境

本次仿真测试环境为：操作系统版本为Win10、64位操作系统，处理器为Intel?CoreTMi5-10210U CPU $@$

$1 . 6 0 \mathrm { G H z } 2 . 1 1 \mathrm { G H z }$ ，内存16.0GB，主频2.11GHz，仿真软件为MATLAB 2020b。

# 3.2比较对象和参数设置

本文选取基本天鹰优化器(AO)[5]、混沌粒子群算法(CPSO)[1]、麻雀搜索算法(SSA)[2]、海洋捕食者算法(MPA)[3]融合了精英反向和黄金正弦策略的鲸鱼优化算法(EGolden-SWOA)[4]以及用切线飞行策略替换莱维飞行的天鹰优化器(tanAO)，与本文所提的融合差分进化和切线飞行的天鹰优化器(DEtanAO)进行对比。为保证实验的公平有效，所有算法的种群规模设置为30，迭代次数设置为500，其他参数设置如表2所示。

Tab.2Experimental parameters of each algorithm   

<html><body><table><tr><td>算法</td><td>参数</td></tr><tr><td>AO</td><td>α=0.1, δ=0.1, U =0.0056, ω=0.005</td></tr><tr><td>tanAO</td><td>α=0.1, δ=0.1, U =0.0056, ω =0.005</td></tr><tr><td>DEtanAO</td><td>α=0.1, δ=0.1, U=0.0056, @ =0.005</td></tr><tr><td>CPSO</td><td>C=1.5, C=1.5，u=2</td></tr><tr><td>SSA</td><td>ST=0.8，PD=0.2，SD=0.2</td></tr><tr><td>MPA</td><td>P=0.5，FADs=0.2</td></tr><tr><td>EGolden-SWOA</td><td>b=1</td></tr></table></body></html>

# 3.3测试函数

为验证改进算法有更好的寻优性能，本文选取12个基准测试函数进行函数优化对比实验，其中选取单峰测试基准函数( $f _ { 1 } \sim f _ { 6 }$ )用于检查算法的局部开发能力，多峰测试基准函数( $f _ { 7 } \sim f _ { 9 }$ )用于检查算法的全局勘探能力，固定维度多峰函数( $f _ { 1 0 } \sim f _ { 1 2 } ^ { \mathrm { ~ ~ } } ,$ ，具体函数信息见表3。

表2各算法的实验参数  
表3基准测试函数  
Tab.3Benchmark function   

<html><body><table><tr><td>编号</td><td>函数</td><td>维数</td><td>范围</td><td>最优值</td></tr><tr><td></td><td>Sphere</td><td>dim</td><td>[-100,100]</td><td>0</td></tr><tr><td>f</td><td>Schwefel2.22</td><td>dim</td><td>[-30,30]</td><td>0</td></tr><tr><td>f</td><td>Schwefel 1.2</td><td>dim</td><td>[-100,100]</td><td>0</td></tr><tr><td>f4</td><td>Schwefel2.21</td><td>dim</td><td>[-100,100] f</td><td>0</td></tr><tr><td>f</td><td>Rosenbrock</td><td>dim</td><td>[-30,30]</td><td>0</td></tr><tr><td>f</td><td>Quartic</td><td>dim</td><td>[-1.28,1.28]</td><td>0</td></tr><tr><td>f</td><td>Rastrigin</td><td>dim</td><td>[-5.12,5.12]</td><td>0</td></tr><tr><td>f</td><td>Ackley</td><td>dim</td><td>[-32,32]</td><td>0</td></tr><tr><td>f</td><td>Penalized</td><td>dim</td><td>[-50,50]</td><td>0</td></tr><tr><td>f10</td><td>Foxholes</td><td>2</td><td>[-65,65]</td><td>1</td></tr><tr><td>f1</td><td>Branin</td><td>2</td><td>[-5,5]</td><td>0.398</td></tr><tr><td>f12</td><td>Goldstein Price</td><td>2</td><td>[-2,2]</td><td>3</td></tr></table></body></html>

# 3.4 寻优精度分析

将本文所提出的DEtanAO，与AO、tanAO、CPSO、SSA、MPA、EGolden-SWOA分别在12个基准函数上独立运行30次，其中非固定维度函数的维度设置为$\scriptstyle \mathrm { d i m } = 3 0 / 1 0 0 / 5 0 0$ 。表4、5统计了7种算法分别在低维、高维和固定维数时，得到的最优解、平均值和标准差。

表4的测试结果显示，DEtanAO在函数 $f _ { 1 }$ 、 $f _ { 3 }$ 、f10、$f _ { 1 2 }$ 上的寻优效果达到 $100 \%$ ，可以直接搜索到对应函数的最优值。相较于其他对比算法，DEtanAO 在函数 $f _ { 1 }$ 、 $f _ { 2 }$ 、 $f _ { 3 }$ ，$f _ { 4 }$ 、 $f _ { 8 }$ 上的标准差为0，说明DEtanAO具有较强的鲁棒性，差分变异策略保证了种群的多样性。在低维条件下，除了直接能达到最优值的函数，DEtanAO相比其他对比算法至少高出11个数量级、至多高出235个数量级。在高维条件下，DEtanAO相比其他对比算法在求解大规模函数时，仍能保持较高水平，最大程度的接近函数最优值，其中 $f _ { 3 }$ 和 $f _ { 7 }$ 仍能直接找到最优解， $f _ { 8 }$ 保持与低维条件下相同的水平，表明所提算法在求解大规模问题时未陷入“维数灾难”，具有较强的稳定性。根据表5，在固定维数下，MPA虽然表现最好，但是DEtanAO仍可以直接搜寻到最优解，从标准差来看，鲁棒性也较好。综上所述，DEtanAO的稳定性以及精度均较其他算法有大幅度提升。这说明，DEtanAO通过引入差分变异策略改善了原算法过度依赖天鹰根据不同攻击方式的数学公式进行位置更新的状况，利用切线飞行公式，使得算法跳出局部最优，提高了算法的寻优质量。

表4低维、高维函数上的性能比较

Tab.4Performance comparison on low-dimensional and high-dimensional functions   

<html><body><table><tr><td rowspan="2">函数</td><td rowspan="2">算法</td><td rowspan="2"></td><td colspan="2">dim=30</td><td colspan="3">dim=100</td><td colspan="3">dim=500</td></tr><tr><td>最优解 平均值</td><td>标准差</td><td>最优解</td><td>平均值</td><td>标准差</td><td>最优解</td><td>平均值</td><td>标准差</td></tr><tr><td rowspan="8"></td><td>DEtanAO</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>tanAO</td><td>6.34E-174</td><td>1.18E-107</td><td>4.26E-108</td><td>9.01E-167</td><td>1.67E-117</td><td>9.12E-117</td><td>3.47E-163</td><td>4.70E-108</td><td>2.25E-107</td></tr><tr><td>A0</td><td>1.32E-160</td><td>3.45E-105</td><td>1.89E-106</td><td>1.61E-157</td><td>1.15E-98</td><td>6.29E-98</td><td>2.33E-160</td><td>3.88E-103</td><td>2.13E-102</td></tr><tr><td>CPSO</td><td>4.98E-06</td><td>1.0769</td><td>2.7904</td><td>2.24E-06</td><td>0.68775</td><td>2.1899</td><td>1.22E-06</td><td>0.54379</td><td>2.0649</td></tr><tr><td>SSA</td><td>0</td><td>3.15E-58</td><td>1.63E-57</td><td>3.43E-143</td><td>4.45E-56</td><td>2.42E-55</td><td>0</td><td>5.28E-56</td><td>2.85E-55</td></tr><tr><td>MPA</td><td>2.54E-24</td><td>5.38E-23</td><td>7.51E-23</td><td>8.95E-21</td><td>2.54E-19</td><td>2.25E-19</td><td>1.26E-17</td><td>8.00E-17</td><td>4.93E-17</td></tr><tr><td>EGolden-SWOA</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>DEtanAO</td><td>8.86E-234</td><td>1.50E-210</td><td>0</td><td>6.15E-231</td><td>2.19E-201</td><td>0</td><td>1.23E-228</td><td>4.87E-206</td><td>0</td></tr><tr><td rowspan="8">f</td><td>tanAO</td><td>1.46E-81</td><td>2.61E-54</td><td>1.42E-53</td><td>1.04E-80</td><td>3.46E-52</td><td>1.33E-51</td><td>2.60E-78</td><td>1.96E-53</td><td>1.07E-52</td></tr><tr><td>AO</td><td>3.59E-80</td><td>2.09E-74</td><td>4.49E-74</td><td>1.02E-79</td><td>3.24E-51</td><td>1.77E-50</td><td>1.80E-78</td><td>2.43E-55</td><td>1.33E-54</td></tr><tr><td>CPSO</td><td>2.88E-07</td><td>0.28538</td><td>1.5558</td><td>4.08E-05</td><td>0.26831</td><td>1.4591</td><td>2.52E-05</td><td>0.26964</td><td>1.0202</td></tr><tr><td>SSA</td><td>6.66E-177</td><td>7.29E-28</td><td>3.99E-27</td><td>2.66E-88</td><td>8.45E-26</td><td>4.30E-25</td><td>6.99E-78</td><td>7.82E-31</td><td>3.03E-30</td></tr><tr><td>MPA</td><td>1.44E-14</td><td>2.45E-13</td><td>1.95E-13</td><td>1.74E-12</td><td>1.87E-11</td><td>1.87E-11</td><td>4.51E-11</td><td>6.19E-10</td><td>9.86E-10</td></tr><tr><td>EGolden-SWOA</td><td>1.38E-220</td><td>8.98E-174</td><td>0</td><td>1.13E-208</td><td>3.65E-171</td><td>0</td><td>2.52E-204</td><td>4.88E-161</td><td>2.67E-160</td></tr><tr><td>DEtanAO</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>tanAO</td><td>1.76E-159</td><td>1.17E-101</td><td>6.41E-101</td><td>3.27E-160</td><td>1.29E-101</td><td>7.09E-98</td><td>5.14E-101</td><td>5.01E-104</td><td>2.74E-103</td></tr><tr><td rowspan="8">f</td><td>AO</td><td>4.96E-154</td><td>7.05E-103</td><td>3.67E-102</td><td>2.98E-155</td><td>2.08E-98</td><td>1.09E-100</td><td>5.20E-98</td><td>6.21E-98</td><td>3.37E-97</td></tr><tr><td>CPSO</td><td>2.41E-09</td><td>0.52855</td><td>1.7034</td><td>3.61E-05</td><td>0.90048</td><td>2.4076</td><td>6.03E-07</td><td>0.26886</td><td>1.018</td></tr><tr><td>SSA</td><td>1.65E-299</td><td>6.72E-29</td><td>2.94E-28</td><td>0</td><td>4.15E-23</td><td>2.26E-22</td><td>0</td><td>5.22E-23</td><td>2.25E-22</td></tr><tr><td>MPA</td><td>2.54E-08</td><td>0.0001959</td><td>0.0005031</td><td>0.0018476</td><td>13.018711</td><td>36.046243</td><td>165.03471</td><td>5865.8164</td><td>4933.6315</td></tr><tr><td>EGolden-SWOA</td><td>0</td><td>0</td><td>0</td><td>0</td><td>7.47E-286</td><td>0</td><td>0</td><td>2.43E-273</td><td>0</td></tr><tr><td>DEtanAO</td><td>2.75E-235</td><td>1.47E-216</td><td>0</td><td>1.45E-237</td><td>5.05E-217</td><td>0</td><td>1.25E-234</td><td>1.00E-220</td><td>0</td></tr><tr><td>tanAO</td><td>2.89E-81</td><td>5.25E-54</td><td>2.87E-53</td><td>4.08E-81</td><td>4.48E-55</td><td>2.45E-54</td><td>1.69E-80</td><td>2.81E-53</td><td>1.54E-52</td></tr><tr><td>AO</td><td>5.25E-82</td><td>6.87E-55</td><td>3.76E-54</td><td>1.50E-81</td><td>9.32E-57</td><td>5.10E-56</td><td>4.57E-80</td><td>6.24E-62</td><td>3.42E-61</td></tr><tr><td rowspan="8">f4</td><td>CPSO</td><td>1.17E-07</td><td>1.2247</td><td>2.8645</td><td>2.82E-06</td><td>0.51696</td><td>1.6558</td><td>5.44E-07</td><td>0.95575</td><td>2.5679</td></tr><tr><td>SSA</td><td>0</td><td>9.95E-34</td><td>5.15E-33</td><td>5.99E-160</td><td>2.04E-32</td><td>1.11E-31</td><td>1.73E-74</td><td>1.08E-31</td><td></td></tr><tr><td>MPA</td><td>5.24E-10</td><td>3.23E-09</td><td>1.47E-09</td><td>4.65E-08</td><td>2.29E-07</td><td>1.36E-07</td><td>5.83E-06</td><td>2.23E-05</td><td>4.32E-31</td></tr><tr><td>EGolden-SWOA</td><td>4.15E-211</td><td>2.21E-171</td><td>0</td><td>0</td><td>7.47E-286</td><td>0</td><td>1.17E-206</td><td>2.92E-179</td><td>1.32E-05</td></tr><tr><td>DEtanAO</td><td>4.34E-28</td><td>0.0001801</td><td>0.0006804</td><td>6.40E-28</td><td>2.16E-05</td><td>4.89E-05</td><td>1.75E-26</td><td></td><td>0</td></tr><tr><td>tanAO</td><td>1.01E-06</td><td>0.0022965</td><td>0.0038784</td><td>3.81E-06</td><td>0.0016667</td><td>0.0053777</td><td>1.00E-05</td><td>1.01E-06</td><td>2.75E-06</td></tr><tr><td>A0</td><td>1.35E-06</td><td>0.0060161</td><td>0.0108928</td><td>0.0001869</td><td>0.0232199</td><td></td><td>1.05E-06</td><td>0.0051573</td><td>0.0066908</td></tr><tr><td>CPSO</td><td></td><td>0.54473</td><td>2.0528</td><td>7.86E-06</td><td></td><td>0.0363135</td><td></td><td>0.1357954</td><td>0.2335892</td></tr><tr><td rowspan="8">f</td><td></td><td>4.20E-06</td><td></td><td></td><td></td><td>0.27242</td><td>1.4861</td><td>1.11E-05</td><td>0.54892</td><td>1.7798</td></tr><tr><td>SSA</td><td>1.33E-08</td><td>3.46E-05</td><td>9.84E-05</td><td>1.49E-06</td><td>0.0071157</td><td>0.0228404</td><td>6.24E-07</td><td>0.0179906</td><td>0.0352481</td></tr><tr><td>MPA</td><td>24.233312</td><td>25.357126</td><td>0.5291385</td><td>95.903627</td><td>97.181244</td><td>0.6738597</td><td>496.48333</td><td>497.07268</td><td>0.1888052</td></tr><tr><td>EGolden-SWOA</td><td>2.27E-11</td><td>6.69E-06</td><td>3.55E-05</td><td>2.63E-09</td><td>8.95E-07</td><td>1.89E-06</td><td>2.39E-09</td><td>8.36E-05</td><td>0.0004372</td></tr><tr><td>DEtanAO tanAO</td><td>7.78E-06 2.69E-06</td><td>0.0001963 7.40E-05</td><td>0.0001794 5.62E-05</td><td>8.70E-06 1.10E-05</td><td>0.0001509 0.0001021</td><td>0.0001348 9.00E-05</td><td>1.32E-05 1.12E-05</td><td>0.0001044 9.67E-05</td><td>6.30E-05 7.52E-05</td></tr></table></body></html>

续表4低维、高维函数上的性能比较  

<html><body><table><tr><td rowspan="2">函数</td><td rowspan="2">算法</td><td colspan="3">dim=30</td><td colspan="3">dim=100</td><td colspan="3">dim=500</td></tr><tr><td>最优解</td><td>平均值</td><td>标准差</td><td>最优解</td><td>平均值</td><td>标准差</td><td>最优解</td><td>平均值</td><td>标准差</td></tr><tr><td rowspan="2">f</td><td>MPA</td><td>3.53E-13</td><td>1.42E-12</td><td>1.16E-12</td><td>7.10E-12</td><td>4.60E-11</td><td>2.34E-11</td><td>2.22E-10</td><td>4.30E-10</td><td>1.29E-10</td></tr><tr><td>EGolden-SWOA</td><td>8.88E-16</td><td>8.88E-16</td><td>0</td><td>8.88E-16</td><td>8.88E-16</td><td>0</td><td>8.88E-16</td><td>8.88E-16</td><td>0</td></tr><tr><td rowspan="6">f</td><td>DEtanAO</td><td>2.81E-32</td><td>6.72E-08</td><td>2.26E-07</td><td>1.69E-32</td><td>3.17E-09</td><td>1.20E-08</td><td>1.39E-32</td><td>1.33E-10</td><td>5.87E-10</td></tr><tr><td>tanAO</td><td>2.66E-12</td><td>7.58E-07</td><td>1.51E-06</td><td>2.53E-09</td><td>2.95E-07</td><td>4.86E-07</td><td>3.59E-10</td><td>1.89E-07</td><td>4.01E-07</td></tr><tr><td>AO</td><td>6.56E-09</td><td>4.38E-06</td><td>9.48E-06</td><td>3.82E-09</td><td>3.07E-06</td><td>7.42E-06</td><td>1.09E-08</td><td>6.15E-07</td><td>7.44E-07</td></tr><tr><td>CPSO</td><td>1.11E-05</td><td>0.68033</td><td>2.1691</td><td>8.34E-06</td><td>0.6621</td><td>2.1033</td><td>0.0001318</td><td>0.41022</td><td>1.6491</td></tr><tr><td>SSA</td><td>8.60E-18</td><td>3.65E-12</td><td>1.81E-11</td><td>1.37E-10</td><td>7.40E-08</td><td>3.43E-07</td><td>2.49E-12</td><td>5.62E-08</td><td>1.10E-07</td></tr><tr><td>MPA</td><td>1.22E-09</td><td>5.69E-09</td><td>3.34E-09</td><td>0.0236108</td><td>0.0441271</td><td>0.0122656</td><td>0.3516941</td><td>0.4089202</td><td>0.0289135</td></tr><tr><td colspan="2">EGolden-SWOA</td><td>6.15E-14</td><td>4.88E-08</td><td>2.43E-07</td><td>1.24E-14</td><td>8.57E-10</td><td>3.28E-09</td><td>8.56E-14</td><td>3.11E-11</td><td>6.39E-11</td></tr></table></body></html>

表5固定维数函数上的性能比较

Tab.5Performance comparison on fixed dimensional functions   

<html><body><table><tr><td rowspan="2">算法</td><td colspan="3">f0</td><td colspan="3">f</td><td colspan="3">f12</td></tr><tr><td>最优解</td><td>平均值</td><td>标准差</td><td>最优解</td><td>平均值</td><td>标准差</td><td>最优解</td><td>平均值</td><td>标准差</td></tr><tr><td>DEtanAO</td><td>0.9980038</td><td>2.6384379</td><td>2.895985</td><td>0.3978874</td><td>0.3978881</td><td>3.96E-06</td><td>3</td><td>3.0038</td><td>0.018132</td></tr><tr><td>tanAO</td><td>0.9980038</td><td>3.7318068</td><td>4.590161</td><td>0.3979267</td><td>0.4022246</td><td>0.0131830</td><td>3.0003929</td><td>3.3083947</td><td>0.414067</td></tr><tr><td>A0</td><td>0.9980038</td><td>2.7607481</td><td>3.459285</td><td>0.3978936</td><td>0.3980834</td><td>0.0001897</td><td>3.00003146</td><td>3.03204623</td><td>0.033251</td></tr><tr><td>CPSO</td><td>3.29E-05</td><td>0.13484</td><td>0.73388</td><td>2.25E-08</td><td>0.25729</td><td>1.4014</td><td>3.29E-06</td><td>0.7202</td><td>1.8772</td></tr><tr><td>SSA</td><td>0.99800384</td><td>3.0121167</td><td>4.260976</td><td>0.3978874</td><td>0.39788736</td><td>0</td><td>3</td><td>4</td><td>4.929503</td></tr><tr><td>MPA</td><td>0.99800384</td><td>0.9980038</td><td>1.51E-16</td><td>0.3978874</td><td>0.39788736</td><td>1.23E-14</td><td>3</td><td>3</td><td>1.64E-15</td></tr><tr><td>EGolden-SWOA</td><td>0.99800384</td><td>0.9980038</td><td>3.50E-12</td><td>0.3978875</td><td>0.3979736</td><td>0.0001675</td><td>3.00000002</td><td>3.00000887</td><td>1.11E-05</td></tr></table></body></html>

# 3.5 收敛曲线分析

算法的优劣可以通过其收敛曲线直观地表现出来，收敛曲线展示了算法的收敛速度和陷入局部最优值的次数。图8(a)\~(i)列出了DEtanAO、AO、tanAO、CPSO、SSA、MPA、EGolden-SWOA共7种算法在30 维情况下，对上述12个基准函数的收敛曲线对比图。观察上述图中各算法的收敛曲线可以看出DEtanAO的收敛速度在整个迭代过程中都快于其他6种算法，收敛精度也是这7种算法中最好的，这不仅说明DEtanAO对比其他算法有更好的全局探索能力而且不易陷入局部最优解，平衡了全局探索能力和局部开发能力。其中为验证改进策略的有效性，将仅用切线飞行策略替换莱维飞行策略的算法记为tanAO，从收敛曲线图中可知，tanAO 比基本的 AO 算法在收敛速度上有明显提升，观察 $f _ { 8 }$ 收敛曲线图可知tanAO在仅150次迭代就达到了最优值，而基本AO算法在250次迭代才达到最优值，tanAO的寻优精度和速度比AO有较大幅度提升。

![](images/6a21c8679bc33608e44c76d8c0485fda450400587c7098f74276ecfc070cd511.jpg)  
Fig.8Convergence curve

综上所述，本文提出的DEtanAO算法不管在低维、高维还是固定维度的函数下都具有较好的寻优性能，其求解精度、收敛速度和鲁棒性均优于与之对比的其他六种算法，有着明显的求解优势。

# 3.6Wilcoxon 秩和检验

Wilcoxon[1秩和检验是一种非参数统计检验方法，用于判断比较DEtanAO算法与其他算法是否有显著性区别，其结果分析如表6所示，其中“p”表示检验结果，“h”表示显著性判断结果。当 $\mathsf { p } { < } 0 . 0 5$ 时，h显示为“1”，表示

DEtanAO算法的显著性强于其他算法；当 $\mathsf { p } { > } 0 . 0 5$ 时，h显示为“0"，表示DEtanAO算法的显著性弱于其他算法；当P显示为“N/A”时，表示无法进行显著性检验，DEtanAO算法显著性可能与其他算法相同。

将DEtanAO与AO、tanAO、CPSO、SSA、MPA、EGolden-SWOA独立运行30次的平均值进行Wilcoxon秩和检验，从表6中的统计结果可以看出，大部分的p值均小于0.05，表明DEtanAO与其他算法存在显著差异，并且DEtanAO的性能在多个函数上优于对比算法。

Tab.6Wilcoxon rank sum test results of reference functions   

<html><body><table><tr><td rowspan="2">函数</td><td colspan="2">AO</td><td colspan="2">tanAO</td><td colspan="2">EGoldenSWOA</td><td colspan="2">MPA</td><td colspan="3">SSA</td></tr><tr><td>P</td><td>h</td><td>P</td><td>h p</td><td></td><td>h P</td><td>h</td><td>P</td><td>h</td><td>P</td><td>h</td></tr><tr><td>f</td><td>1.21E-12</td><td>1</td><td>1.21E-12</td><td>1</td><td>N/A</td><td>0</td><td>1.21E-12</td><td>1</td><td>1.21E-12 1</td><td>1.21178E-12</td><td>1</td></tr><tr><td>f</td><td>3.02E-11</td><td>1</td><td>3.02E-11</td><td>1</td><td>1.61323E-10</td><td>1</td><td>3.02E-11</td><td>1 3.02E-11</td><td>1</td><td>3.01986E-11</td><td>1</td></tr><tr><td>f</td><td>1.21E-12</td><td>1</td><td>1.21E-12</td><td>1</td><td>N/A</td><td>0</td><td>1.21E-12</td><td>1 1.21E-12</td><td>1</td><td>1.21178E-12</td><td>1</td></tr><tr><td>f4</td><td>3.02E-11</td><td>1</td><td>3.02E-11</td><td>1</td><td>3.01986E-11</td><td>1</td><td>3.02E-11</td><td>1 3.02E-11</td><td>1</td><td>3.01986E-11</td><td>1</td></tr><tr><td>f</td><td>1.41E-09</td><td>1</td><td>1.29E-09</td><td>1</td><td>0.077271976</td><td>0</td><td>3.02E-11</td><td>1 2.13E-05</td><td>1</td><td>2.43863E-09</td><td>1</td></tr><tr><td>f6</td><td>0.099258</td><td>0</td><td>0.145319</td><td>0</td><td>0.016284809</td><td>1</td><td>3.69E-11</td><td>1 8.48E-09</td><td>1</td><td>5.53286E-08</td><td>1</td></tr><tr><td>f</td><td>0.333711</td><td>0</td><td>0.333711</td><td>0</td><td>0.333710696</td><td>0</td><td>0.333711</td><td>0 0.333711</td><td>0</td><td>1.72025E-12</td><td>1</td></tr><tr><td>f</td><td>N/A</td><td>0</td><td>N/A</td><td>0</td><td>N/A</td><td>0</td><td>1.21E-12</td><td>1 N/A</td><td>0</td><td>1.21178E-12</td><td>1</td></tr><tr><td>f</td><td>3.02E-11</td><td>1</td><td>3.02E-11</td><td>1</td><td>2.37591E-07</td><td>1</td><td>8.15E-11</td><td>1 9.51E-06</td><td>1</td><td>3.01797E-11</td><td>1</td></tr><tr><td>f1</td><td>0.501102</td><td>0</td><td>0.841786</td><td>0</td><td>7.18381E-05</td><td>1</td><td>5.78E-08</td><td>1 0.042542</td><td>1</td><td>1.72466E-07</td><td>1</td></tr><tr><td>f1</td><td>3.16E-12</td><td>1</td><td>3.16E-12</td><td>1</td><td>3.15782E-12</td><td>1</td><td>0.024657</td><td>1 0.081493</td><td>0</td><td>3.22767E-07</td><td>1</td></tr><tr><td>f12</td><td>1.36E-08</td><td>1</td><td>1.02E-10</td><td>1</td><td>1.01948E-07</td><td>1</td><td>0.186128</td><td>0 0.509236</td><td>0</td><td>1.01948E-07</td><td>1</td></tr><tr><td>1/0</td><td>8/4</td><td></td><td>8/4</td><td></td><td>7/5</td><td></td><td>10/2</td><td>8/4</td><td></td><td>12/0</td><td></td></tr></table></body></html>

# 3.7工程优化问题应用

为验证DEtanAO算法的前沿性以及在实际工程中的优越性，选取了压力容器设计优化问题，并通过与上述对比算法的改进算法如融合正余弦和柯西变异的麻雀搜索算法(SCSSA)[17]、混合策略改进的麻雀搜索算法(MSSSA)[18]基于分段式随机惯性权重和最优反馈机制的鲸鱼优化算法(FWOA)[19]、高斯量子粒子群算法(G-QPSO)[20]进行验证比较。压力容器设计问题[2I是一个经典工程优化设计问题，目的是通过优化圆柱容器身长 $L$ 、圆柱容器内径R、圆柱体壁厚 $T _ { \phantom { \dagger } _ { \parallel } }$ 和头部壁厚 $T _ { h }$ 变量，使压力容器制作成本达到最小。问题的目标函数、约束条件和自变量取值范围如下所示。

$$
X = [ x _ { 1 } , x _ { 2 } , x _ { 3 } , x _ { 4 } ] = [ \mathrm { T } _ { a } , \mathrm { T } _ { b } , \mathrm { R } , \mathrm { L } ]
$$

$$
\begin{array} { c } { { M i n \mathbf { f } ( x ) = 0 . 6 2 2 4 x _ { 1 } x _ { 2 } x _ { 3 } + 1 . 7 7 8 1 x _ { 2 } x _ { 3 } ^ { 2 } + 3 . 1 6 6 1 x _ { 4 } x _ { 1 } ^ { 2 } + 1 9 . 8 4 x _ { 3 } x _ { 1 } ^ { 2 } } } \\ { { \begin{array} { r l } { { g _ { 1 } ( x ) = - x _ { 1 } + 0 . 0 1 9 3 x _ { 3 } \leq 0 } } \\ { { g _ { 2 } ( x ) = - x _ { 2 } + 0 . 0 0 9 5 4 x _ { 3 } \leq 0 } } \\ { { ( g _ { 3 } ( x ) = - \pi x _ { 3 } ^ { 2 } - \frac { 4 } { 3 } \pi x _ { 3 } ^ { 2 } + 1 2 9 6 0 0 0 \leq 0 } } \\ { { g _ { 4 } ( x ) = - x _ { 4 } - 2 4 0 \leq 0 } } \\ { { 0 \leq x _ { 1 } \leq 1 0 0 , i = 1 , 2 } } \end{array} } } \\ { { 0 \leq x _ { 1 } \leq 2 0 0 , i = 3 , 4 } } \end{array}
$$

求解结果见表7，将四种改进算法的求解结果与DEtanAO算法的求解结果进行比较。从表中可以看出在求解压力容器设计问题时DEtanAO算法的最优解和平均值均小于其他对比算法，说明DEtanAO 算法在此类优化问题上的求解精度较高，稳定性也能达到较好的数值，整体验证了DEtanAO算法的前沿性和优越性。

# 4 结束语

本文提出一种融合差分进化和切线飞行的天鹰优化器，通过差分进化策略，改善了原算法过度依赖天鹰根据不同攻击方式的数学公式进行位置更新的状况，利用切线飞行策略，有利于算法在随机游走的过程中出现更大概率的大跨步，使得算法跳出局部最优，提高了算法的寻优质量。通过12个标准基准函数、高维函数、Wilcoxon秩和检验以及在工程优化问题上的应用的结果显示，DEtanAO具有较强的跳出局部最优的能力、更快的收敛速度以及更高的收敛精度。下一步考虑将DEtanAO 算法应用到其他实际问题的建模中，比如机器学习各种预测分类算法中超参数的优化，并进一步将优化后的机器学习算法用来预测量化投资中股价变动的趋势，以扩展本文所提算法在金融等领域的应用范围。

表6基准函数Wilcoxon秩和检验结果  
表7压力容器设计问题求解结果  
Tab.7Pressure vessel design problem solving results   

<html><body><table><tr><td>算法</td><td>最小值</td><td>平均值</td><td>标准差</td></tr><tr><td>DEtanAO</td><td>5862.69</td><td>6081.35</td><td>2.15E+02</td></tr><tr><td>FWOA</td><td>5886.97</td><td>-</td><td></td></tr><tr><td>SCSSA</td><td>8050.92</td><td>-</td><td></td></tr><tr><td>MSSSA</td><td>5897.15</td><td>6615.81</td><td>5.53E+02</td></tr><tr><td>G-QPSO</td><td>6059.72</td><td>6342.45</td><td>4.48E+02</td></tr></table></body></html>

# 参考文献：

[1]Yu Z,Li Q,Feng Y,et al.Hierarchical economic load dispatch based on chaotic-particleswarmoptimization[C]//NinthInternational Conference on Natural Computation.IEEE,2013:517-521.   
[2]Xue J,Shen B.A novel swarm intelligence optimization approach: sparrow search algorithm [J].Systems Science & Control Engineering An Open Access Journal,2020,8(1): 22-34.   
[3]Faramarzi A,Heidarinejad M,Mirjalili S,et al.Marine predators algorithm:A nature-inspired metaheuristic [J]. Expert Systems with Applications,2020,152:113377.   
[4]肖子雅，刘升．精英反向黄金正弦鲸鱼算法及其工程优化研究[J]. 电子学报,2019,47(10): 2177-2186.(Xiao Ziyao,Liu Sheng.Study on elite opposition-based golden-sine whale optimization algorithm and its application of project optimization[J].Acta Electronica Sinica,2019,47

#

(10): 2177-2186.)   
[5]Abualigah L,Yousri D,Elaziz MA,et al.Matlab Code of Aquila Optimizer: A novel meta-heuristic optimization algorithm [J]. Computers & Industrial Engineering,2021,157:107250.   
[6]Wang S,Jia H,Abualigah L,et al.An Improved Hybrid Aquila Optimizer and Harrs Hawks Algorithm for Solving Industrial Engineering Optimization Problems [J].Processes,2021,9 (9): 1551.   
[7]Mahajan,S.,Abualigah,L.,Pandit,A.K.et al.Hybrid Aquila optimizer with arithmetic optimization algorithm for global optimization tasks [J]. Soft Computing,2022,26,4863-4881.   
[8]Shicheng Wang,Jiawei Ma,Wei Li,et al.An optimal configuration for hybrid SOFC,gas turbine,and Proton Exchange Membrane Electrolyzer using a developed Aquila Optimizer [J]. International Journal of Hydrogen Energy,2022,47 (14) 8943-8955.   
[9]Eric Ofori-Ntow Jnr,Yao Yevenyo Ziggah,Maria Joao Rodrigues,et al. A hybrid chaotic-based discrete wavelet transform and Aquila optimisation tuned-artificial neural network approach for wind speed prediction [J].Results in Engineering,2022,14,2590-1230.   
[10]Layeb,A.Tangent search algorithm for solving optimization problems [J/OL].Neural Comput & Applic，2022，2022(34），8853-8884. https://doi.0rg/10.1007/s00521-022-06908-z.   
[11] Storn R,Price K.Differential Evolution -A Simple and Efficient Heuristic for global Optimization over Continuous Spaces [J].Journal of Global Optimization,1997,11 (4): 341-359.   
[12] Shao X, Chen Z,Lin X.Resolution of multicomponent overlapping chromatogram using an immune algorithm and genetic algorithm [J]. Chemometrics & Intelligent Laboratory Systems,20oo,50(1): 91-99.   
[13] Storn R,Price K.Differential Evolution -A Simple and Efficient Heuristic for global Optimization over Continuous Spaces [J]. Journal of Global Optimization,1997,11 (4): 341-359.   
[14] Reynolds A M,Smith A D,Reynolds DR,et al.Honeybees perform optimal scale-free searching flights when attempting to locate a food ovuic   
[15] Mantegna Rosario Nunzio.Fast,accurate algorithm for numerical simulation ofLévy stable stochastic processes [J].Physical Review,1994, 49 (5):4677-4683.   
[16] Wilcoxon F.Individual comparison by ranking methods [J]. Biometrics, 1945,1: 80-83.   
[17]李爱莲，全凌翔，崔桂梅，解韶峰．融合正余弦和柯西变异的麻雀搜 索算法[J].计算机工程与应用,2022,58(03):91-99.(LiAilian,Quan Linxiang，Cui Guimei,Xie Shaofeng.Sparrow Search Algorithm CombiningSine-Cosineand Cauchy Mutation [J]. Computer Engineering and Applications,2022,58 (03): 91-99.)   
[18]张伟康，刘升，任春慧．混合策略改进的麻雀搜索算法[J].计算机 工程与应用,2021,57(24):74-82.(Zhang Weikang,Liu Sheng,Ren Chunhui. Mixed Strategy Improved Sparrow Search Algorithm [J]. Computer Engineering and Applications,2021,57 (24): 74-82.)   
[19] 刘景森，马义想，李煜．改进鲸鱼算法求解工程设计优化问题[J]. 计算机集成制造系统，2021,27(07):1884-1897.(Liu Jinsen,Ma Yixiang,Li Yu.Improved whale algorithm for solving engineering design optimization problems [J]. Computer integrated manufacturing system,2021,27 (07): 1884-1897.)   
[20] Leandro dos Santos Coelho.Gaussian quantum-behaved particle swarm optimization approaches for constrained engineering design problems [J]. Expert Systems With Applications,2009,37(2):1676-1683.   
[21] Seyedali Mirjalili and Seyed Mohammad Mirjalili and Abdolreza Hatamlou.Multi-Verse Optimizer: a nature-inspired algorithm for global optimization [J].Neural Computing and Applications,2016,27 (2): 495- 513.   
[22]马威强，高永琪，赵苗．基于全局最优和差分变异的头脑风暴优化 算法[J]．系统工程与电子技术,2022,44(1):270-278.(Ma Weiqiang, Gao Yongqi,Zhao Miao.Global-best difference-mutation brain storm optimization algorithm [J]. Systems Engineering and Electronics,2022, 44 (1): 270-278.)