# 基于改进的萤火虫优化算法的混合语音盲分离

李著成1,²，黄祥林 1†

(1．中国传媒大学 理工学部，北京 100024;2.北京联合大学 商务学院，北京 100025)

摘要：萤火虫优化算法是模拟自然界萤火虫彼此之间通过荧光素进行信息交流的特性发展而来的，在搜索复杂函数全局极值点方面非常有效。针对传统盲源分离优化算法对分离性能影响较大的局限性，提出了一种基于改进的萤火虫优化的混合语音盲分离算法。新算法将萤火虫的飞行跨度由固定取值变为由新构造的函数自适应调整，在加快收敛速度的同时，避免算法早熟现象的发生。实验结果表明，与基于梯度、标准萤火虫和粒子群优化的盲分离算法相比，新算法对混合语音信号的分离效果较好，在收敛速度和分离精度方面都有所提升。

关键词：萤火虫优化算法；盲源分离；语音盲分离；飞行跨度 中图分类号：TP391.42 doi:10.3969/j.issn.1001-3695.2018.03.0202

Blind separation of speech mixtures based on improved glowworm swarm optimization

Li Zhucheng1, 2, Huang Xianglin1 (1.FacultyofScience&Technology,CommunicationUniversityofChina,Beijing24,China;2.BusinessColege,Beiing Union University,Beijing 100025,China)

Abstract: Glowworm Swarm Optimization (GSO)is a population-based metaheuristic that a glowworm caries luciferin along with itself to exchange information with itscompanions.GSOis very efective in searching for the global extremes of a complex function.Aiming at the limitation of traditional optimization algorithms for Blind Source Separation (BSS）,this paper proposes a blind speech separation algorithm based on an improved GSO(IGSO).The new algorithm constructs aright function toadjustadaptivelythe flight span,so itcannotonlyaccelerate theconvergencespeedbutalsoavoidthepremature convergence.The mixed speech separation experiments showthatthe proposed algorithm performs beter thanBSS based on Gradient, GSO or Particle Swarm Optimization (PSO),and improves both convergence rate and separation accuracy. Key words: glowworm swarm optimization; blind source separation; blind speech separation; flight span

# 0 引言

盲源分离（blind source separation，BSS）是指在不知源信号和传输通道特性的情况下，仅由观测信号恢复出源信号各个独立成分的技术，是当前信号处理领域的研究热点，其研究成果已广泛应用于语音识别、图像处理、生物医学和机械故障检测等诸多领域[I-4]。一般说来，BSS 算法有两个重要组成部分：目标函数和和优化算法。目标函数用来规定或描述恢复信号的统计独立性，而优化算法的任务则是在目标函数空间寻找到最优解（分离矩阵)。BSS 算法性能之收敛速度和分离精度主要依赖后者，因此如何选择合适的优化算法是BSS技术的关键挑战。传统BSS优化算法基于梯度（Gradient)，除非初始参数值选取恰当，否则使用这类算法求得的解不会太理想。然而，由于盲假设，获取合理的参数值是非常困难的。特别地，当目标函数空间不连续或不可微时，这类算法甚至无法使用。

群智能优化算法是人工智能一个新的研究分支，不要求目标函数和约束的连续性与凸性，在复杂问题求解方面具有独特的优势，具有成本低、速度快和鲁棒性好的特点，已经在多个领域获得了应用，如计算数学、航空航天、交通、计算机科学、电子通信、电力、材料力学和生态系统等[5]。为了解决传统BSS优化算法的不足，群智能优化算法在最近几年逐渐被应用于BSS，如遗传算法[6]，粒子群优化算法[6,7和蚁群算法[8]等。群智能优化算法属于启发式算法，是模拟自然界蚂蚁，鱼，蜜蜂，青蛙和细菌等生物种群生存或觅食的方式，算法粒子彼此之间通过相互竞争和合作来完成寻优任务。

萤火虫优化算法是一种新颖的群智能优化算法，是受自然界萤火虫通过荧光素进行信息交流这种群体行为的启发而构造的，在多峰函数寻优方面有较好表现。标准萤火虫算法有两个版本：一是由印度学者Krishnanand 等人提出，被称为glowwormswarm optimization（GSO）[9-11]；二是由剑桥学者 Yang 提出,被称为Firefly Algorithm（FA）[12,i3]。两种算法的仿生原理相同，但在具体实现方面有一定差异，其中以GSO较为常见，下面的研究基于GSO展开。

为了克服传统优化算法的局限性和发挥群智能优化方法的优势，本文研究利用一种改进的萤火虫优化算法来解决混合语音盲分离问题。

# 1 盲源分离基本算法

# 1.1数学模型

设 $\mathbf { \boldsymbol { s } } \left( t \right) = \left[ s _ { 1 } \left( t \right) , s _ { 2 } \left( t \right) , . . . , s _ { N } \left( t \right) \right] ^ { T } \in \mathbf { \boldsymbol { R } } ^ { N }$ 是一组 $N$ 维的源信号，$\mathbf { A } = \left[ \boldsymbol { a } _ { 1 } , \boldsymbol { a } _ { 2 } , . . . , \boldsymbol { a } _ { M } \right] \in \mathbf { R } ^ { M \times N }$ 为 $M \times N$ 维混合矩阵，$\mathbf { x } ( t ) = \left[ x _ { 1 } \left( t \right) , x _ { 2 } \left( t \right) , . . . , x _ { M } \left( t \right) \right] ^ { T } \in \mathbf { R } ^ { M }$ 是一组 $M$ 维的观测信号，${ \bf n } \left( t \right) = \left[ n _ { 1 } \left( t \right) , n _ { 2 } \left( t \right) , . . . , n _ { M } \left( t \right) \right] ^ { T } \in { \bf R } ^ { M }$ 为噪声，一般情况下不予考虑，那么观测信号 $\mathbf { x } { \big ( } t { \big ) }$ 由 $N$ 维未知的独立源信号 $\mathbf { s } ( t )$ 和混合矩阵A线性瞬时混合而成的模型可以表示为

$$
\mathbf { x } ( t ) = \mathbf { A s } ( t ) + \mathbf { n } ( t )
$$

盲源分离的任务就是通过某种方法求出分离矩阵 $\mathbf { w }$ ，从而通过观测信号恢复出源信号，这个过程的数学模型为

$$
\mathbf { y } \left( t \right) = \mathbf { W } \mathbf { x } \left( t \right)
$$

其中： $\mathbf { y } \left( t \right) = \left[ y _ { 1 } \left( t \right) , y _ { 2 } \left( t \right) , . . . , y _ { N } \left( t \right) \right] ^ { T } \in \mathbf { R } ^ { N }$ 被称为分离信号，为源信号的估计矢量。当 $N = M$ 时被称为正定盲源分离；当 $N < M$ 时被称为超定盲源分离；当 $N > M$ 时被称为欠定盲源分离。

# 1.2信号的预处理

通常情况下，为了简化算法的复杂性和提高计算效率，在混合信号分离前一般需要对观测信号 $\mathbf { x } { \big ( } t { \big ) }$ 进行预处理。

a）均值化（centering）,也即是对观测信号 $\textbf { x }$ 进行中心化处理，从而保证是零均值的矢量，最直接的方法是 $\textbf { x }$ 减去的其均值矢量 $E { \big [ } \mathbf { x } { \big ] }$ 。

b）白化处理（whiting），也叫球面化处理，通过白化矩阵V使得观测信号球面化，使 $\mathbf { v } = \mathbf { V } \mathbf { x }$ 去相关，也就是使 $\textbf { v }$ 的协方差矩阵为单位矩阵，即 $E \left[ \mathbf { v } \mathbf { v } ^ { T } \right] = \mathbf { I }$ ，从而 $E { \left[ { \bf { y y } } ^ { T } \right] } { = } E { \left[ { \bf { W v v } } ^ { T } { \bf { W } } \right] } { = } { \bf { I } }$ 。对源信号预白化的方法有多种，如主成分分量分析法（principalcomponentanalysis，PCA）、奇异值分解法（singularvaluedecomposition,SVD）和利用信号的自相关函数等，经过白化处理使算法计算量接近原来的一半，效率大大被提高。

c）目标函数选取。负熵和峭度是信号处理领域常见的信号统计独立性度量方法，但在实际应用中，峭度对野值(outliers)极其敏感，容易导致判定结果不稳定，因此负熵应用更为广泛些。但是负熵不易被准确计算，于是文献[14]提出了一种负熵的替代公式：

$$
J \left( y _ { i } \right) \cong \frac { 1 } { 1 2 } k _ { 3 } ^ { ^ 2 } \left( y _ { i } \right) + \frac { 1 } { 4 8 } k _ { 4 } ^ { ^ 2 } \left( y _ { i } \right) + \frac { 7 } { 4 8 } k _ { 3 } ^ { ^ 4 } \left( y _ { i } \right) - \frac { 1 } { 8 } k _ { 3 } ^ { ^ 2 } \left( y _ { i } \right) k _ { 4 } \left( y _ { i } \right)
$$

其中： $y _ { i }$ 是分离信号 $\textbf { y }$ 的第 $i$ 个分量信号， $k _ { j }$ 是 $y _ { i }$ 的第 $j$ 阶累积量。假如 $y _ { i }$ 的概率分布对称，那么 $k _ { 3 } = 0$ ，这时负熵为

$$
J \left( y _ { i } \right) \cong \frac { 1 } { 4 8 } k _ { 4 } ^ { 2 } \left( y _ { i } \right)
$$

其中: $k _ { 4 }$ 就被称为 $y _ { i }$ 的峭度。分析可见，在一定条件下，负熵和峭度存在映射关系。 $k _ { 4 }$ 的表达式为

$$
k _ { 4 } \left( y _ { i } \right) = E \left( y _ { i } ^ { 4 } \right) - 3 E ^ { 2 } \left( y _ { i } ^ { 2 } \right)
$$

# 2 萤火虫优化算法

# 2.1算法原理

首先在问题解空间中随机分布若干萤火虫个体，每个萤火虫个体代表目标函数空间内的一个解且在某一时刻具有对应的萤光素值，荧光素值的大小用来衡量个体所处的位置好坏，即荧光素值与解的适应度相关。

每个萤火虫个体在某一时刻拥有自己对应的感知范围，而感知范围的大小由决策半径确定。萤火虫个体在感知范围内，寻找比自己萤光素值大的所有个体组成邻居，然后沿移动概率大的方向朝比自己萤光素值大的邻居移动，最后更新决策半径，不断重复这一过程直到达到一定的迭代次数或精度要求，这时所有的萤火虫个体聚集到较亮的萤火虫周围，即搜寻到了目标函数的多个局部极值点或全局极值点，以此来达到在解空间内寻优的目的。

萤火虫优化算法总体可分为：萤光素值更新、邻居选择、移动概率计算、位置更新、决策半径更新五个步骤。

# 2.2数学描述

# 2.2.1萤光素值更新

萤火虫个体的荧光素值越高，那么它的吸引力就越强，其他个体向其移动的概率就越大。萤光素值与适应度函数Fitness相关，其数学表达式为

$$
l _ { i } \left( t + 1 \right) = \left( 1 - \rho \right) l _ { i } \left( t \right) + \gamma F i t n e s s \left( x _ { i } \left( t + 1 \right) \right)
$$

其中： $l _ { i }$ 表示萤火虫个体 $i$ 的荧光素值， $\rho$ 表示荧光素值的衰退因子，γ表示荧光素的增强系数， $x  { \textit { i } } \in R ^ { M }$ 表示萤火虫 $i$ 在 $\tt { M }$ 维实数空间的位置， $F i t n e s s ( x _ { i } )$ 表示个体 $i$ 在所处位置对应的适应度值。

# 2.2.2邻居选择

萤火虫个体 $i$ 在其感知范围内寻找荧光素值较高的其它萤火虫组成邻居集合 $N _ { i }$ （领域)，如式（7）所示。

$$
N _ { i } \left( t \right) = \left\{ j : d _ { i j } \left( t \right) < r _ { d } ^ { i } \left( t \right) ; l _ { i } \left( t \right) < l _ { j } \left( t \right) \right\}
$$

其中： $d _ { i j }$ 是萤火虫个体 $i$ 和 $j$ 之间的距离， $r _ { d } ^ { i }$ 代表个体 $i$ 的决策半径。

# 2.2.3移动概率计算

根据确定的邻居集合 $N _ { _ i }$ 计算轮盘概率 $p _ { i j }$ ，比较每个 $p _ { i j }$ ，选择大的作为目标对象 $j \colon$

$$
p _ { i j } = { l _ { j } } \left( t \right) - { l _ { i } } \left( t \right) \Biggl / \sum _ { k \in { N _ { i } } \left( t \right) } { l _ { k } } \left( t \right) - { l _ { i } } \left( t \right)
$$

# 2.2.4位置更新

依据移动概率 $p _ { i j }$ ，萤火虫个体 $i$ 进行位置更新：

$$
x \ _ { i } \left( t + 1 \right) = x \ _ { i } \left( t \right) + s p n \left( \frac { x \ _ { j } \left( t \right) - x \ _ { i } \left( t \right) } { \left\| x \ _ { j } \left( t \right) - x \ _ { i } \left( t \right) \right\| } \right)
$$

其中： $\left. . \right.$ 表示欧氏距离， $s p n > 0$ 表示萤火虫的飞行跨度。

# 2.2.5决策半径更新

萤火虫个体 $i$ 根据邻居集合 $N _ { i }$ 更新决策半径 $r _ { d } ^ { i }$ ：

$$
r _ { d } ^ { i } \left( t + 1 \right) = \operatorname* { m i n } \left. r _ { s } , \operatorname* { m a x } \left. 0 , r _ { d } ^ { i } \left( t \right) + \beta \left( n _ { t } - \left| N _ { i } \left( t \right) \right| \right) \right. \right.
$$

其中： $\beta$ 是调节因子， $r _ { s }$ 表示萤火虫 $i$ 的常规感知半径， $n _ { t }$ 表示领域阈值。

# 2.3飞行跨度函数化策略

标准萤火虫算法尽管引入了对决策半径的考虑，决策半径的大小与感知范围内荧光素值较高的个体数量有关，如果数量多那么决策半径小，反之决策半径大，这样可以有效地避免算法陷入局部最优，但仍然无法解决飞行跨度取值固定带来的算法收敛速度与分离精度之间的矛盾。所以，本文对飞行跨度进行函数化构造，使其能够实时自适应取值：在算法运行初始阶段飞行跨度取值较大来增强全局寻优能力，加速收敛；在算法运行后期飞行跨度取值变小以此保证局部寻优能力，增加分离精度，飞行跨度函数表达式为

$$
s p n ( t + 1 ) = \mu \mathrm { e } ^ { - \psi t } + \xi
$$

其中： $1 > \mu > 0$ 、 $1 > \psi > 0$ 均为正常数， $\xi$ 表示飞行跨度阈值。

# 3基于改进的萤火虫优化算法的盲分离

# 3.1算法流程图

![](images/6b2c619bdd2648c6b23e1c07914d105faa61127ccff857b18618416fefe8b27f.jpg)  
图1为采用改进的萤火虫优化算法的盲分离流程图。  
图1算法流程图

# 3.2算法实现步骤

根据图1得出算法的实现步骤：

a)读取观测信号 $\mathbf { x } { \big ( } t { \big ) }$ ，对其中心化、白化处理;

b)初始化参数 $\rho , \ \gamma , \ \beta .$ ， $n _ { t }$ ， $l _ { 0 }$ 和 $s$ ，随机产生 $n$ 个分离矩阵作为萤火虫群，在搜索空间内随机初始化萤火虫个体 $i$ 的初始位置 $x _ { i } \left( t _ { 0 } \right)$ 和初始决策半径 $r _ { d } ^ { i } \left( t _ { 0 } \right)$ ；以此计算该萤火虫的初始适应度 $F i t n e s s \left[ x _ { i } \left( t _ { 0 } \right) \right]$ （将某一常数比例化的负熵作为适应度函数)；

c)依据上面的结果计算萤火虫群的最优位置 $x _ { o p t }$ 和最佳适应度 $F i t n e s s \Bigl ( x _ { o p t } \Bigr )$ ：

d)式(6) (7)更新萤火虫 $i$ 的荧光素值 $l _ { i }$ ，计算萤火虫 $i$ 的邻居集合 $N _ { _ i }$ ；根据式（8）计算萤火虫 $i$ 向 $N _ { i }$ 中的萤火虫 $j$ 的移动概率 $P _ { i j }$ ;

e)根据式 $\left( 9 \right) ^ { \sim } \left( 1 1 \right)$ 分别更新萤火虫 $i$ 下一时刻的位置 $x _ { i }$ 、决策半径 $r _ { d } ^ { i }$ 和飞行跨度 spn ；

f)比较当前萤火虫群的适应度值，得到最大值。若此值优于 $F i t n e s s \Bigl ( x _ { o p t } \Bigr )$ ，则更新最优位置 $x _ { o p t }$ 和最佳适应度 $F i t n e s s \Bigl ( x _ { o p t } \Bigr )$ ：

g)若输出达到要求的分离精度或程序满足了结束条件，程序停止运行，输出 $x _ { o p t }$ 和 $F i t n e s s \Bigl ( x _ { o p t } \Bigr )$ ，否则令 $t = t + 1$ ，转到步骤d)继续执行。

# 3.3计算机仿真实验

通过MATLAB 实验，本节将新算法与基于梯度、标准萤火虫和粒子群优化的盲源分离算法进行分离性能比较。

# 3.3.1实验环境及参数取值

通过麦克风采集3路语音模拟信号，将其数字化后采样20000个点作为源信号（图2)，其直方图如图3所示。源信号经过随机矩阵混合后产生的混合信号及其直方图分别如图4、5所示。算法各参数取值情况如表1所示。

表1算法参数取值  

<html><body><table><tr><td>参数</td><td>p</td><td>Y</td><td>β</td><td>n</td><td></td><td>y</td><td>μ</td><td>y</td></tr><tr><td>取值</td><td>0.4</td><td>0.6</td><td>0.08</td><td>6</td><td>5</td><td>0.03</td><td>0.06</td><td>0.03</td></tr></table></body></html>

![](images/bf4c8a9d26fa6d49dc004092659ecc426a9c7d0b0819a16ff3dc970cef63a7d1.jpg)  
图2源信号  
图3源信号直方图

T1

![](images/cd4ee5e24f49e7fff0abfe5b081162905a66d11cc9ef9a5ac07f3a1331ca6f74.jpg)  
图4混合信号

ΛΛΛ

![](images/704b4137b2847639f514e6197ed834c74699019725742b78a426b459649be0df.jpg)  
图5混合信号直方图

# 3.3.2实验结果及分析

a）图6是新算法在更新30次时的分离信号（直方图见图7)。将图6与图2进行对比，可以直观地看出源信号已经被较好地恢复，而此时其他几种算法还没有收敛；

b）图8是分离矩阵两个变量W(1,1)和W(2.1)的二维图，可以形象地看出萤火虫群搜索最优解的飞行轨迹;

c）图9是几种算法的适应度曲线比较图，看出新算法比基于梯度、标准萤火虫和粒子群优化的盲源分离算法对语音混合源信号的分离性能要好，在性能上都有所改善：收敛速度方面$s p e e d _ { G r a d i e n t } < s p e e d _ { G S O } < s p e e d _ { P S O } < s p e e d _ { I G S O }$ ， 精度方面$p r e c _ { G r a d i e n t } < p r e c _ { P S O } < p r e c _ { G S O } < p r e c _ { I G S O } \ _ { \circ }$ （204号

d）图10是源信号和恢复信号的散点图，从图中可以看出算法收敛后，分离信号的顺序和相位与源信号相比有的发生了变化，这是由盲分离的不确定性决定的[15]。

e）算法参数分析。表1的这些参考值适用于大部分应用场合。参数 $\rho$ 表示荧光素值的衰退因子，若取值为1，表示萤光素值无记忆。／表示适应度提取比例，反映了算法每次更新荧光素值的增加量。 $\beta$ 也被称为萤火虫邻域变化率，若取值过大，将会导致邻域范围仅在上下限间变化，所以 $\beta$ 取值不宜过大。$s p n > 0$ 表示萤火虫的飞行跨度，不宜固定取值，应该进行函数化处理。 $n _ { t }$ 表示邻居阈值，若取值过小，降低了样本的多样性，则可能使某些优秀个体被误抛弃；若取值过大，则降低算法收敛速度。 $l _ { 0 }$ 表示萤火虫的初始荧光素值，可以任意选取。 $r _ { s }$ 为萤火虫的决策半径，若取值过小，则不能充分感知周围的萤火虫；若取值过大，则邻居过多降低了局部搜索能力，需要根据实际情况选择。算法中种群规模 $n$ 、 $r _ { s }$ 和 $\psi$ 没有相对稳定的参考值，应根据目标函数空间的特点进行合理取值。

T

![](images/473e88d7585de74cb38d7662169268d6aa3ac4de6a490d960c0a1aa151bca8a5.jpg)  
图6分离信号  
图8萤火虫飞行轨迹

![](images/fd4b81bd213a600605ecf2bb9aa3f0d26b77c45810059dd15f32f40dd2fb30a0.jpg)  
图9适应度曲线比较

![](images/2634e006f588c7c89c593491adafc508521fa86754cc081c81b050d0616813cc.jpg)  
图7分离信号直方图  
图10源信号与分离信号的散点图

# 4 结束语

为了进一步提高萤火虫优化算法的全局搜索性能，本文首先对原算法中的飞行跨度参数进行了函数化处理，然后针对传统盲源分离优化算法的不足，提出了一种基于改进的萤火虫优化的混合语音盲分离算法。与基于梯度、标准萤火虫和粒子群优化的盲源分离算法的对比实验结果表明，新算法的分离效果较好，在收敛速度和分离精度方面都有所提升。

# 参考文献：

[1] 欧旭东，张天骐，闫振华，等．基于多频段能量相关排序的语音卷积混 合盲源分离[J].计算机应用研究,2016,33(5):1481-1485.(Ou Xudong, Zhang Tianqi，Yan Zhenhua,et al.Blind convolution speech separation based on multi-band ordering [J//OL].Application Research of Computers, 2016,33 (5): 1481-1485.)   
[2]Abbas N A.Image encryption based on independent component analysis and Arnold's cat map [J].Egyptian Informatics Journal,2016,17(1): 139-146.   
[3]Jadhav M S H,Dhang MD N.Extraction of fetal ECG from abdominal recordings combining BSS-ICA & WT Techniques [J]. International Journal of Engineering,2017,10(1): 869-875.   
[4]Farhat M,Gritli Y,Benrejeb M.Fast-ICA for mechanical fault detection and identification in electromechanical systems for wind turbine applications [J]. International Journal of Advanced Computer Science and Applications,2017,8(7):Article ID 080759.   
[5]Shan Rong,Zhao Zengshun,Chen Panfei,et al. Network modeling and assessment of ecosystem health by a multi-population swarm optimized neural network ensemble [J].Applied Sciences,2016,6(6): Article ID175.   
[6]Mavaddaty S,Ebrahimzadeh A.Blind signals separation with genetic algorithm and particle swarm optimization based on mutual information [J]. Radioelectronics and Communications Systems,2011,54(6): 315-324.   
[7]Li Qiaoyan,Quan Haiyan.Analyze gravity tide signal based on ICA with PSO[C]//Proc of IEEE ICSPCC.Piscataway,NJ: IEEE Press,2015:1-4.   
[8]Zhang Nian,Liu Tianyou.The application of ant colony optimization algorithm in linear-combination blind source separation problem [C]//Proc of IEEE CISP.Piscataway,NJ: IEEE Press,2O09:1-4.   
[9]Krishnanand K N, Ghose D. Detection of multiple source locations using a glowworm metaphor with applications to collective robotics [C]// Proc of IEEE SIS.Piscataway,NJ: IEEE Press,2005:84-91   
[10] Krishnanand K N，Ghose D.Glowworm swarm optimizationfor multimodal search spaces [M]//PanigrahiBK,Shi Y,Lim MH.Handbook of Swarm Intelligence.Concepts，Principles and Applications.Berlin: Springer-Verlag,2011: 451-467.   
[11] Kaipa K N, Ghose D. Glowworm swarm optimization: theory,algorithms, and applications [M]. Cham, Switzerland: Springer Nature,2017.   
[12] Yang Xinshe.Firefly algorithms for multimodal optimization [C]// Proc of the 5th International Conference on Stochastic Algorithms:Foundations and Applications.Berlin: Springer-Verlag,20o9:169-178.   
[13] Yang Xinshe.Multiobjective firefly algorithm for continuous optimization [J]．Engineeringwith Computers， 2013， 29(2):ArticleID s00366-012-0254-1.   
[14] Comon P. Independent component analysis,a new concept?[J]. Sinal processing,1994,36(3): 287-314.   
[15]刘琚．盲信号处理理论与应用[M]．北京：科学出版社，2013.(Liu Ju. The theory and application of blind signal processing [M]. Beijing: Science Press,2013.)