# 全局优化的改进鸡群算法

韩斐斐1，赵齐辉1，杜兆宏²，刘升1†(1．上海工程技术大学 管理学院，上海 201620;2.浙江工业大学 教育科学与技术学院，杭州 310023)

摘要：鸡群算法是一种新颖的群智能算法，模拟鸡群中的等级制度以及觅食行为，相比于传统的智能算法，其展现出了良好的寻优性能。在基本鸡群算法的基础之上，提出了一种改进版鸡群算法 (ECSO)，在公鸡位置的更新过程中引入自适应变异策略用于平衡算法迭代后期下降的种群多样性，提升收敛速度；在母鸡移动过程引入偏好随机游动策略来平衡了算法的“开发”与“探索”阶段，增强算法的稳定性；在小鸡位置更新时引入“领导者”策略，减少算法搜索的盲目性。最后，通过测试多组函数，并与基本蝙蝠算法和鸡群算法以及已有改进的鸡群算法进行对比，验证了改进算法的有效性。

关键词：鸡群算法；种群多样性；偏好随机游动；定向变异 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.12.0964

# Enhanced chicken swarm algorithm for global optimization

Han Feifei1, Zhao Qihui1,Du Zhaohong²,Liu Sheng1† (1.SchoolofManagement,ShanghaiUniversityofEngneeringScience,Shanghai62,China;IntituteofducationScience &Technology Zhejiang University of Technology,Hangzhou 310023,China)

Abstract: Thechickenswarmalgorithmis anovelswarm intelligencealgorithm,which imitating therank system and foraging behavior inthechicken groupandshowingacertainadvantageoverthe traditional inteligentalgorithm.Basedonthechicken swarmalgorithm,this paperproposedanimproved versionofthechickenswarmalgorithm (ECSO),which introducingadaptive mutation strategy forbalancing algorithm later decreased diversityofthe populationand improving the speed ofconvergence process and introducing random walk strategy preference into hen mobile update processto balance "development"and "exploration"stage toenhancethestabilityofthealgorithm,and which introducing"leader"strategyofupdating positionof chickens toreduce the blindnessofte search algorithm.Finall,the efectivenessof the improved algorithm is verified by comparing the testbenchmark functions with the basic bat algorithmand thechicken swarm algorithmand other improved chicken swarm algorithm .

Key Words: chicken swarm optimization; population diversity; bias random walk; target mutation

# 0 引言

智能算法分为两种，一种是群体智能算法（swarmintelligencealgorithm)，该算法大多模拟自然界中动植物的特有行为，并将其表达成数学语言，从而进行迭代寻优，如模拟蝙蝠回声定位行为而提出的蝙蝠算法（batalgorithm，BA）[1]和模拟大杜鹃巢寄卵生特性的布谷鸟搜索算法（cuckoo searchalgorithm，CS）[2]；另一种是进化算法，如差分进化算法（differentialevolution，DE）[3]是一种基于群体差异性的寻优算法，通过变异、交叉、选择的操作来进行迭代寻优。这些算法促进了计算科学的发展。根据“NFL”定理，不存在某种算法在全部优化领域都存在优势，因此，近些年来便有多种智能算法被提出，用于弥补已有算法的不足。

鸡群优化算法（chicken swarm optimization，CSO）[4]是由我国学者孟献兵于2014年提出，其模拟鸡群中的等级区分制度和群体行为。将鸡群种群划分为公鸡、母鸡和小鸡，不同的种群进行不同的移动策略，等级区分下特定种群中依然存在着竞争，这种根据不同的种群而制定不同的寻优策略有利于保持种群的竞争性，这已被证明在函数优化领域优于粒子群算法，并且CSO已经成功应用于工程优化设计问题[4、多分类器系数优化[5]、聚类分析[，这些成功的应用案例表明了CSO拥有较好的应用前景。

鸡群算法与大多数群智能算法一样，存在着求解精度粗糙、后期迭代速度缓慢等不足。针对这些不足，国内外众多专家学者对其进行了有效的改进。2015年，孔飞等人[提出了一种改进的鸡群算法，其参考粒子群算法中对权重因子的分析，在小鸡个体更新位置的过程中引入了自适应权重，解决了由于算法前期搜索空间大而易跳过最优解以及后期搜索空间小而收敛缓慢的问题，并且增加了跟公鸡个体的学习部分，使得小鸡享有全面的学习机制；杨菊蜻等人[8]于2016年用多种混合方法改进鸡群算法，用反方向学习法初始化种群个体以提高种群的质量，并且在边界处理时引入变异思想来增强种群多样性，提高了算法的全局寻优能力，最终用模拟退火的思想以一定的概率接受劣质解，增强了算法跳出局部最优的能力。这些改进的算法有效地改善了算法的寻优性能，并且其函数优化的结果证明了改进算法的有效性。

改进的算法在一定程度上增强了算法的寻优能力，但也存在一定的不足。文献[7]仅仅是改进了三种群体中的小鸡个体，对其他两个群体并没有作出改进，因此只对部分种群进行了优化；文献[8]改进的策略较为复杂，虽然取得了不错的效果，但是破坏了CSO易于实现、结构简单的优势。本文针对鸡群算法在函数优化方面的不足，提出了一种改进的鸡群算法（enhancedchickenswarmoptimization，ECSO)，在公鸡更新的过程引入自适应变异策略，使用一种递增的变异策略，使得算法寻优后期降低的种群多样性得到一定程度的补偿，从而加快算法的收敛速度；母鸡位置更新的过程引入随机偏好游动，较好地平衡了算法的“局部开发”和“整体探索”，增强了算法的稳定性；小鸡位置的更新过程修改为定向变异的过程，更好地借鉴最优个体的信息来进行寻优，降低了搜索的盲目性。测试结果表明，ECSO在函数优化方面要优于蝙蝠算法（BA）和基本鸡群算法(CSO)，是一种在函数优化领域具有强烈竞争力的算法。

# 1 基本鸡群算法介绍

鸡群中公鸡、母鸡、小鸡的职责不同，公鸡主动去寻找食物，并与外来入侵者进行战斗；母鸡陪伴在公鸡左右；小鸡们则跟随鸡妈妈去寻找食物。

为了简化繁杂的觅食过程，文献[4]制定如下规则：

a）每个鸡群体中，存在着多个子种群，每个子种群包括一个公鸡、一群母鸡以及小鸡。

b）将鸡群划分为若干子种群以及确定公鸡、母鸡和小鸡的角色都依赖于个体的适应度值。适应度值最好的若干个体将作为公鸡。每只公鸡都是一个子种群的领导者。适应度值最差的若干个体被指定为小鸡，其他个体将作为母鸡。母鸡随机选择跟随哪一只公鸡，并且母鸡与小鸡之间母子关系也是随机形成的。

c）等级制度、统领关系、母子关系将保持不变，每隔G代重新分群并更新角色。

d）鸡群跟随公鸡去寻找食物，并且保护自己的食物。小鸡在母鸡妈妈身边寻找食物，优势个体在食物竞争中占据优势。将鸡群划分公鸡、母鸡、小鸡三类，其分别执行不同的寻优策略。假设 $\Nu _ { \mathrm { R } }$ 、 $\Nu _ { \mathrm { H } }$ 、 $\mathrm { N _ { c } }$ 和 $\Nu _ { \mathrm { { M } } }$ 分别表示公鸡、母鸡、小鸡和妈妈母鸡的个数。在整个鸡群中，所有的个体数假设为 $\mathrm { ~ \bf ~ N ~ }$ 。数学表达如下：

（a）公鸡个体的位置更新方式为

$$
x _ { i } ^ { j } \left( t + 1 \right) = x _ { i } ^ { j } \left( t \right) \ast \left( 1 + r a n d n { \left( 0 , \sigma ^ { 2 } \right) } \right)
$$

$$
\sigma ^ { 2 } = \left\{ \begin{array} { c } { 1 , i f \mathcal { Y } _ { i } \leq f _ { k } , } \\ { \exp \displaystyle \left( \frac { \left( f _ { k } - f _ { i } \right) } { \left| f _ { i } \right| + \varepsilon } \right) , o t h e r w i s e , } \end{array} \right. k \epsilon [ 1 , N ] , k \neq i
$$

其中： $\mathbf { X } _ { \mathrm { i } } ^ { \mathrm { j } } \big ( \mathrm { t } \big )$ 代表在t次迭代时刻j维空间的第 $\mathbf { i }$ 个个体；randn $\left( 0 , \sigma ^ { 2 } \right)$ 产生均值为0；标准差为 $\sigma$ 的高斯分布随机数；ε是一个极小的整数用以避免分母为0的情况； $\mathbf { f } _ { \mathrm { i } }$ 是个体i的适应度值； $\mathbf { f } _ { \mathrm { k } }$ 是个体 $\mathbf { k }$ 的适应度值；个体 $\mathbf { k }$ 是从公鸡种群中随机选择出来的，且 $\mathbf { k } \neq \mathbf { \dot { i } }$ 。

（b）母鸡个体的位置更新方式为

$$
x _ { i } ^ { j } \left( t + 1 \right) = x _ { i } ^ { j } \left( t \right) + S 1 ^ { * } r a n d ^ { * } \left( x _ { r 1 } ^ { j } \left( t \right) - x _ { i } ^ { j } \left( t \right) \right) +
$$

$$
S 2 ^ { * } r a n d * \bigl ( x _ { r 2 } ^ { j } \left( t \right) - x _ { i } ^ { j } \left( t \right) \bigr )
$$

$$
S 1 = e x p { \Bigg ( } { \frac { f _ { i } - f _ { r 1 } } { | f _ { i } | + \varepsilon } } { \Bigg ) }
$$

$$
S 2 = e x p { \left( f _ { r 2 } - f _ { i } \right) }
$$

其中：rand是产生[0,1]之间的随机数； $\mathrm { \Delta _ { r l } }$ 是第 $\mathrm { i }$ 个母鸡的配偶公鸡个体的索引； $\mathbf { r } 2$ 是鸡群中的所有公鸡和母鸡中的任意一个个体，且 $\mathbf { r } 1 \neq \mathbf { r } 2$ 。

（c）小鸡个体的更新方式为

$$
x _ { i } ^ { j } \left( t + 1 \right) = x _ { i } ^ { j } \left( t \right) + F L ^ { * } \left( x _ { m } ^ { j } \left( t \right) - x _ { i } ^ { j } \left( t \right) \right)
$$

其中： $\mathbf { X } _ { \mathrm { m } } ^ { \mathrm { j } } \left( \mathrm { t } \right)$ 个体是母鸡妈妈的位置；FL是小鸡跟随母鸡的行走步长，具体值为[0,2]之间的随机数。

# 2 全局优化的改进鸡群算法

鸡群优化算法融合了差分进化算法和粒子群算法的优点，公鸡个体的位置更新本质是一个高斯变异的过程，只是标准差的选择略有不同；母鸡个体更新类似于粒子群算法的更新方式，一方面吸收了公鸡个体的位置信息，另一方面S1和S2两个关键系数也控制了算法的搜索方向和距离，因此不易陷入局部最优；小鸡的个体更新过程类似于差分进化算法的DE/rand/1变异过程，因此群体之间信息共享机制较好。但是公鸡位置更新的过程没有考虑到算法迭代后期不断下降的种群多样性；母鸡个体更新过程缺乏对自身个体的学习；小鸡更新的过程只是随机借鉴了母鸡妈妈个体的位置信息，寻优缺乏指向性。针对这些不足，本文分别采用自适应策略、偏好随机游动和定向变异策略对基本鸡群算法进行改进。

# 2.1 自适应策略

公鸡更新过程本质是一个个体变异的过程，高斯变异的过程有助于增强种群的多样性，但是前期和后期的搜索个体变异能力是保持不变的。众所周知，算法迭代的过程种群的多样性是不断下降的，因此后期应当增强种群个体的变异能力，使得变异算子呈现递增的趋势。将公鸡位置更新的方式修改为$\frac { \mathrm { m a x t } } { 2 }$ 之后为柯西变异。柯西变异是一种变异能力强于高斯变异的变异算子，使得后期较强的变异能力，使得原先丢失的种群多样性能够得到一定的弥补。同时，为了增加算法后期的寻优收敛速度，整体采用线性递减策略，具体实现如下：

$$
{ x _ { i } ^ { j } } \left( t + 1 \right) = \left\{ \begin{array} { l l } { \displaystyle \frac { m a x t - t } { m a x t } * { x _ { i } ^ { j } } \left( t \right) ^ { * } \left( 1 + r a n d n { \left( 0 , \sigma ^ { 2 } \right) } \right) , 0 < t \leq \frac { m a x t } { 2 } } \\ { \displaystyle \frac { m a x t - t } { m a x t } * { x _ { i } ^ { j } } \left( t \right) ^ { * } \left( 1 + c a u c h y { \left( 0 , \sigma ^ { 2 } \right) } \right) , \displaystyle \frac { m a x t } { 2 } < t < m a x t } \end{array} \right.
$$

# 2.2 偏好随机游动

偏好随机游动[过程出现在众多算法中，最典型的算法是布谷鸟算法[2。随机偏好游动本质是一种权重因子，本文引入式（9）来增强个体对自身的学习，借鉴自身的个体位置信息使得个体具有记忆性。

$$
\begin{array} { r l } & { x _ { i } ^ { j } \left( t + 1 \right) = \omega ( t ) * x _ { i } ^ { j } \left( t \right) + S 1 * r a n d * \left( x _ { r 1 } ^ { j } \left( t \right) - x _ { i } ^ { j } \left( t \right) \right) + } \\ & { \qquad S 2 * r a n d * \left( x _ { r 2 } ^ { j } \left( t \right) - x _ { i } ^ { j } \left( t \right) \right) } \end{array}
$$

$$
\omega ( t ) = \omega _ { m i n } + \left( \omega _ { m a x } - \omega _ { m i n } \right) { } ^ { * } e x p \Bigg ( - k { } ^ { * } \Bigg ( \frac { t } { m a x t } \Bigg ) ^ { 2 } \Bigg )
$$

大量实验证明，综合考虑算法的各项性能来看， ${ \mathfrak { c } } _ { \mathrm { m a x } } = 0 . 9$ ，${ \mathfrak { o } } _ { \operatorname* { m i n } } = 0 . 4$ ， $\mathbf { k } = 1 0 0 0$ 时改进的算法寻优综合性能最好。线性递减是一种减幅保持不变的递减模式，变化的幅度是固定的无法更好地平衡前后期的“开发”与“探索”。本文设计了一种非线性递减策略，通过式（9）可以看出，寻优的前期保持一个较大的权重值可以拓展寻优空间，保持全局寻优性能良好；后期较小的惯性权重可以增强局部开发能力，使得算法快速收敛，较好地平衡了算法的两个阶段，增加了算法的稳定性。

# 2.3 定向变异策略

差分进化算法中有多种变异策略，在这里简单介绍两种，文中小鸡的更新策略类似于DE/rand/1。2015 年，Zheng 等人

提出了一种定向变异策略（targetmutation)，其在文献[10]中已经说明了定向变异的策略要优于DE/rand/1和DE/best/1，将小鸡的更新方式修改如下：

$$
x _ { i } ^ { j } \left( t + 1 \right) = b e s t + F L ^ { * } \left( x _ { m } ^ { j } \left( t \right) - x _ { i } ^ { j } \left( t \right) \right)
$$

这种改进策略较于基本CS0来说，新的个体位置更新方式充分借鉴了最优个体的位置，也就是说在小鸡寻优时是存在一个“领导者”带领着其他个体进行寻优，这样就大大降低了算法搜索的盲目性。

综合上述三种优化算子，针对公鸡、母鸡和小鸡群体分别进行优化， $\frac { \operatorname* { m a x t } } { 2 }$ 代之后的柯西变异策略可以弥补下降的种群多样性；偏好随机游动策略平衡好算法的前后期的“开发”与“探索”，保持了算法的稳定性；定向变异策略使得群体存在领导者，降低了个体寻优的盲目性。

# 2.4改进算法描述

综合以上分析，可以将ECSO寻优步骤描述如下：a)初始化种群，并将种群按比例进行分割。b)随机给出一个最优位置，并计算其适应度值。c)使用式（7）（8）（10）分别更新公鸡、母鸡、小鸡的位置，并将最优个体保留下来。d)记录鸡群中最优个体的位置和适应度值。e)检测是否满足最优条件，若满足，迭代终止；若不满足，回到步骤c)。

# 3 实验分析

为了验证改进算法的有效性，本文选择了多组标准函数对ECSO的寻优性能进行测试，并与基本CSO算法和BA算法进行对比。为了保证结果的公正以及客观性，设置种群规模均为100，最大评价次数1000次。各种算法的设置参数见表1。

# 3.1测试函数

本文选择了多组测试函数，函数具体的形式见表2。函数集里的函数包含单峰、多峰、低维、高维等特征，能够全面地反映算法的寻优性能。对比基本蝙蝠算法和鸡群算法，主要比较收敛的速度和求解的函数精度,其次再与已有的改进鸡群算法进行比较。

表1各个算法参数设置  

<html><body><table><tr><td>算法</td><td>参数</td></tr><tr><td>BA</td><td>α=γ=0.5，fmn=0，fmax=2，A∈[0,2]，r∈[0,1]</td></tr><tr><td>CS0</td><td>NR =0.2*N，NH =0.6*N，Nc=N-NR-NH， Nm =0.1*NH，G=10,FL∈[0.4,1]</td></tr><tr><td>ECS0</td><td>NR=0.2*N，NH =0.6*N，Nc=N-NR-NH,Nm =0.1*NH， G=10, FL∈[0.4,1],@mar=0.9，@min=0.4,k =1000</td></tr></table></body></html>

表2测试函数  

<html><body><table><tr><td colspan="2">测试函数</td><td>搜索空间</td><td>理论最优</td><td>维度</td><td>迭代次数</td></tr><tr><td>Sphere</td><td>N f(x)=） 𝑖=1 Mx</td><td>[-100，100]</td><td>0</td><td>30</td><td>1000</td></tr><tr><td>Schwefel P2.22</td><td>f(x)=∑x1+I xl i=1 i=1</td><td>[-50,50]</td><td>0</td><td>30</td><td>1000</td></tr><tr><td>Schaffer</td><td>f(x)= sin²</td><td>[-100，100]</td><td>0</td><td>2</td><td>1000</td></tr><tr><td>Rosenbrock</td><td>f4（(x)=∑[100(x+-x²）²+(x-1)]</td><td>[-2.048，2.048]</td><td>0</td><td>30</td><td>1000</td></tr><tr><td>Rastrigin</td><td>fs(x)=∑[x²-10cos(2πxi)+10] i=1</td><td>[-5.12，5.12]</td><td>0</td><td>30</td><td>1000</td></tr><tr><td>Griewank</td><td>f(x)= x²-1cos +1 i=1 Ji 1 4000台</td><td>[-600，600]</td><td>0</td><td>30</td><td>1000</td></tr></table></body></html>

# 3.2 实验结果分析

1）三种算法寻优结果对比

表3记录了三种算法进行函数优化的结果。图 $1 { \sim } 6$ 是三种算法寻优的收敛曲线图。 $\mathrm { f } _ { 1 } ( \mathrm { x } )$ 是单峰函数，常用来测试算法的收敛速度，BA的结果较为不理想，而CSO相对BA已经有了较大幅的提升，但是ECSO可以直接搜索到最优值，并且收敛较为迅速；对于SchwefelP2.22，CSO相对BA能提高42个数量级，而ECSO在30次的迭代寻优中每次都可以找到理论最优值，并且不到400代便开始收敛；BA和CSO在优化 $\mathrm { f } _ { 3 } ( \mathrm { x } )$ 时大致表现差不多，并不存在太大的差异，ECSO相对两种算法提升明显；Rosenbrock函数需要穿越狭小的山谷寻找到最优值。以上三种算法的结果都不理想，结果大致停留在101这一数量级，但是ECSO的最优值略优于两者； $\mathrm { f } _ { 5 } ( \mathrm { x } )$ 、 $\mathrm { f } _ { 6 } ( \mathrm { x } )$ 是高峰多维的函数，BA表现不理想，CSO和ECSO均可以直接搜索到最优值，两者的收敛速度也不存在较大的差异，大致表现一致。

# 2）与改进的CSO进行对比

为了进一步证明ECSO的有效性，与文献[7]提出来的改进鸡群算法（improved chicken swarm optimization,ICSO）进行$\mathrm { f } _ { 1 } ( \mathbf { x } )$ 、 $\mathbf { f } _ { 2 } ( \mathbf { x } )$ 、 $\mathrm { f } _ { 3 } ( \mathrm { x } )$ 、 $\mathbf { f } _ { 4 } ( \mathbf { x } )$ 、 $\mathrm { f } _ { 5 } ( \mathrm { x } )$ 、 $\mathrm { f } _ { 6 } ( \mathrm { x } )$ 在100 维情况下的对比。对比结果如表4所示。100 维的情况下，ECSO比ICSO提升明显，f(x)、 $\mathbf { f } _ { 2 } ( \mathbf { x } )$ 、 $\mathrm { f } _ { 3 } ( \mathrm { x } )$ 、 $\mathrm { f } _ { 5 } ( \mathrm { x } )$ 、 $\mathrm { f } _ { 6 } ( \mathrm { x } )$ 在100 维的情况下依然可以直接搜索到理论最优值，但是ICSO 在 $\mathrm { f } _ { 1 } ( \mathbf { x } )$ 、$\mathbf { f } _ { 2 } ( \mathbf { x } ) , ~ \mathbf { f } _ { 5 } ( \mathbf { x } )$ 都存在不同程度的误差；尤其对于 $\mathrm { f } _ { 4 } ( \mathrm { x } )$ 的优化结果，两种算法的表现都不好，在 ${ { 1 0 } ^ { 2 } }$ 这一数量级徘徊，但是ECSO依然优于ICSO。

综上所述，除了Rosenbrock函数，对于其余的函数，ECSO都可以搜索到理论最优值，因此ECSO无论是相对基本蝙蝠算法、鸡群算法还是ICSO,其寻优性能都有很大程度的提升，可以证明改进算法的有效性以及在函数优化方面的优势。

表3与基本BA和CSO对比结果  

<html><body><table><tr><td>函数编号</td><td>算法</td><td>最优值</td><td>平均值</td><td>标准差</td></tr><tr><td>f(x)</td><td>BA</td><td>2591.6019</td><td>4196.5796</td><td>1321.19</td></tr><tr><td></td><td>CSO</td><td>1.0522E-57</td><td>1.2756E-55</td><td>8.76566E-53</td></tr><tr><td></td><td>ECSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td>f(x)</td><td>BA</td><td>9.6189</td><td>58.9444</td><td>108.4457806</td></tr><tr><td></td><td>CSO</td><td>4.3024E-42</td><td>1.1287E-40</td><td>6.33143E-41</td></tr><tr><td></td><td>ECSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td>f(x)</td><td>BA</td><td>0.17822</td><td>0.17822</td><td>0</td></tr><tr><td></td><td>CSO</td><td>0.037224</td><td>0.037224</td><td>0</td></tr><tr><td></td><td>ECSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td>f4(x)</td><td>BA</td><td>15.0554</td><td>16.0554</td><td>0.51504</td></tr><tr><td></td><td>CSO</td><td>26.7884</td><td>26.9484</td><td>0.1355</td></tr><tr><td></td><td>ECSO</td><td>10.5287</td><td>14.2534</td><td>6.81828</td></tr><tr><td>fs(x)</td><td>BA</td><td>35.8209</td><td>49.7496</td><td>8.04187</td></tr><tr><td></td><td>CSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td></td><td>ECSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td>f(x)</td><td>BA</td><td>68.0675</td><td>93.2181</td><td>25.0025</td></tr><tr><td></td><td>CSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td></td><td>ECSO</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

![](images/fbaae5c4c6080294e9d7ee0f533825ce7c0006d4f7dc56094bce1f971075c0e0.jpg)  
图1F1收敛曲线

![](images/fb125789a38f9eec50aa1b48f473fa96b508ef60728325ea09b0f86ed09e6ca6.jpg)  
图2F2收敛曲线

![](images/cf4cb8fbbf8f89bc2a73d3cd8c0dec6909a16a87721bd0f0a205a2069d611d4f.jpg)  
图3F3收敛曲线

![](images/3a244d97ad4576accc5002205e4894d80d7251a6bcdb819b54cf05b3310b0fbe.jpg)  
图4F4收敛曲线

![](images/8134051646a7170e4ab5835bdc17c79c7f98814650199645e7ab529c75618c1b.jpg)  
图5F5收敛曲线

![](images/8e981d36a22d63513a67b36a9c5993ee4379e1ab2e156976a1cc25ebad16e0da.jpg)  
图6F6收敛曲线

表4与ICSO对比结果  

<html><body><table><tr><td>函数编号</td><td>算法</td><td>最优值</td><td>平均值</td><td>标准差</td></tr><tr><td>f(x)</td><td>ICSO</td><td>8.7393E-20</td><td>1.8675</td><td>5.6424</td></tr><tr><td></td><td>ECSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td>f(x)</td><td>ICSO</td><td>2.1992E-26</td><td>1.05845E-25</td><td>5.01305E-26</td></tr><tr><td></td><td>ECSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td>f(x)</td><td>ICSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td></td><td>ECSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td>f4(x)</td><td>ICSO</td><td>104.739</td><td>121.649</td><td>45.1791</td></tr><tr><td></td><td>ECSO</td><td>98.4382</td><td>98.5484</td><td>0.260505</td></tr><tr><td>fs(x)</td><td>ICSO</td><td>0</td><td>2.6053E-15</td><td>1.009E-14</td></tr><tr><td></td><td>ECSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td>f(x)</td><td>ICSO</td><td>0</td><td>0</td><td>0</td></tr><tr><td></td><td>ECSO</td><td>0</td><td>0</td><td>0</td></tr></table></body></html>

# 4 结束语

本文在基本鸡群算法的基础上提出了一种改进的鸡群算法，针对公鸡、母鸡、小鸡的位置更新方式引入相对应的优化算子。自适应变异策略降低了后期种群多样性下降的影响,提升了收敛速度；偏好随机游动策略平衡了算法的“开发”与“探索”，增强了算法的稳定性；定向变异策略加强了领导者在寻优过程的作用，减少了寻优过程的盲目性。最后，将ECSO与基本鸡群算法和蝙蝠算法以及ICSO进行函数寻优的对比证明了ECSO的优势。下一步的研究着重于将鸡群算法离散化，设计离散型的算法应用于求解旅行商问题、无人机航线规划问题、二维排样等组合优化问题中。

# 参考文献：

[1]Yang Xinshe.Nature-inspired metaheuristic algorithms [M].Frome,UK: Luniver Press,2008: 81-96.   
[2]Yang Xinshe,Suash D.Cuckoo search via Levy flight [C]//Proc of World Congress on Nature & Biologically Inspired Computing.Washington:IEEE Publications,2009: 210-214.   
[3]Storn R,Price K.Differential evolution: a simple and efficient heuristic for global optimization over continuous space [J]．Journal of Global Optimization,1997,11: 341-359.   
[4]Meng Xiangbing,Liu Yu,Gao Xiaozhi,et al.A new bio-inspired algorithm: chicken swarm optimization [C]// Proc of International Conference in Swarm Intelligence. Cham: Springer,2014: 86-94.   
[5] 洪杨，于凤芹．改进的鸡群算法并用于多分类器系数优化[J].计算机 工程与应用,2017,53(9):158-161.(Hong Yang,Yu Fengqin.Improved chicken swarm optimization and its application in coefficients optimization of multi-classifier [J].Computer Engineering and Applications,2017,53 (9): 158-161.)   
[6]NursyivaI,RiyadiYIT,Haruna C,et al.A framework of clustering based on chicken swarm optimization [C]//Advances on Soft Computing and Data Mining.[S.1.]: Springer International Publishing,2016.   
[7]孔飞，吴定会．一种改进的鸡群算法[J].江南大学学报：自然科学版, 2015,14(6): 681-688.(Kong Fei,Wu Dinghui.An improved chicken swarm optimization algorithm [J].Journal of Jiangnan University: Natural Science Edition,2015,14 (6): 681-688.)   
[8]杨菊蜻，张达敏，张慕雪，等．一种混合改进的鸡群优化算法[J/OL]. 计算机应用研究，2018,35(11):1-2.(2017-11-15）．http://ns.cnki. net/kcms/detail/51.1196.TP.20171115.1041.006.html.(Yang Juqing, Zhang Damin,Zhang Muxue,et al.Hybrid improved for chicken swarm optimization algorithm [J/OL].Application Research of Computers,2018,   
35(11):1-2.(2017-11-15) .http://kns.cnki. net/kcms/detail/51.1196. TP.   
20171115.1041.006.html.) [9]Shi Yuhui,Russell E.A modified particle swarm optimizer [C]//Advances in Natural Computation.Berlin: Springer, 1998: 439-439. [10] Zheng Weijie,Fu Haohuan,Yang Guangwen.Targeted Mutation:a novel mutation strategy for differential evolution [C]// Proc of the 27th International Conference on Tools with Artificial Intelligence.2O15:286-   
293.