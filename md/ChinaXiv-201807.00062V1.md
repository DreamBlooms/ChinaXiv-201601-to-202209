# 基于改进的遗传算法在函数优化中的应用\*

闫春，厉美璇，周潇(山东科技大学 数学与系统科学学院，山东 青岛 266590)

摘要：针对传统遗传算法在函数优化过程中容易陷入局部最优解、收敛慢等缺点，提出了一种新的自适应遗传算法NAGA。该算法考虑了种群适应度的多种集中分散程度，并且非线性地自适应调节遗传算法的交叉概率与变异概率。为了加快寻优效率，在选择算子方面将引进的选择算子与最优保存策略相结合；为了使遗传操作过程中种群数量恒定，又提出了保留亲本的策略。通过仿真实验发现，与经典遗传算法GA和IAGA算法相比，改进的自适应遗传算法在收敛速度与精准度等方面都有较大的进步。

关键词：函数优化；遗传算法；全局寻优 中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2018.03.0242

# Application of improved genetic algorithm in function optimization

Yan Chun,Li Meixuan, Zhou Xiao (SchoolofMathematics&Systems ScienceShandong UniversityofScience&Technology,Qingdao Shandong266590,China)

Abstract:Absrtact:In viewof thetraditional geneticalgorithm inthe processoffunctionoptimizationeaily into the local optimal value,slowconvergene eficiencyand other shortcomings.This paper proposes an adaptive genetic algorithm,which takes intoaccountthediversityofpopulationfitness,andadaptivelyadjuststhecrosoverprobabilityand mutationprobability of the geneticalgorithm.To speedupconvergence rates，in the aspect of selection operator,this papercombines the introduced selectionoperator with theoptimal preservation strategy.Inordertokeepthepopulation sizeconstant during the geneticoperation,this paper puts forward a strategyof keping parents.Finalycompare the improved adaptive genetic algorithm with clasical genetic algorithm GAand the IAGA,the improved adaptive genetic algorithm hasbeen a great improvement in the convergence rate and optimal solution .

Key words:function optimization;genetic algorithm;global optimization

# 0 引言

遗传算法是一种进化算法，其基本原理就是效仿物种选择学说和达尔文进化论的法则对种群进行选择，从而实现随机搜索和优化。近年来遗传算法广泛应用于各个领域：Moussa等人[1提出了一种遗传算法和DCT-PCA 组合的人脸识别系统，利用遗传算法进行人脸特征提取；Moeini等人[2]利用遗传算法对气膜侧向扩散孔进行形状的优化，以此来提高旋转叶片气膜冷却效率；Abdelsalam等人[3]利用二元实数编码遗传算法进行局部搜索，实现风电场选址的优化;李树江等人[4利用遗传算法优化PID 控制器参数，从而实现环境测试舱温湿度的优化控制。遗传算法虽然常用来作为优化的手段，但是针对一些较为复杂的优化问题时传统的遗传算法容易陷入到一些局部的极值点[5，多次求解结果不稳定，精准度不高，实践表明传统的遗传算法很难收敛到全局最优状态。近年来，许多学者对遗传算法的各个流程进行了各种方法的改进，以此来提高遗传算法的性能。

对交叉概率与变异概率值的研究：传统的遗传算法在遗传进化的过程中使用固定的遗传算子，但是种群进化到后期优良个体增多,如果不改变遗传算子将会对较优解的破坏更大，从而使得遗传算法的收敛速度变慢，甚至会出现早熟收敛的现象[6]。冯磊华等人[7采用自适应调节公式，认为在进化初期种群差异比较大，采用较小的变异率和较大的交叉率，后期种群差异小故采用较大的变异率和较小的交叉率，有助于防止陷入局部最优。但是却忽略了种群进化是具有波动性的，不能只是根据种群进化代数来判断种群差异度；Srinivas等人[8提出了自适应调节变异率和交叉率的遗传算法，虽然当个体适应度高于平均适应度时采用自适应调节Pc、Pm值，但是当个体适应度低于平均适应度时却采用了较大的固定的Pc、 $ { \mathrm { P m } }$ 值，这样会使得一些劣质个体所携带的优质个体遭到破坏；杨从锐等人[提出了一种改进的自适应遗传算法(IAGA)，通过考虑种群的平均适应度与最高适应度差距，来判断种群的差异度大小，以此来非线性的自适应调节交叉概率与变异概率值。但是却忽略了种群适应度集中较小而最大适应度却较大的这种情况，虽然这种情况平均适应度与最大适应度间差距较大，但是种群间的差异性却不大，所以此种改进方法有待改进。

对选择策略的研究：由于选择操作对适应度高的个体有较大的复制作用，并且对适应度低的个体有一定的淘汰作用，所以可以通过改进选择策略来提高算法的全局收敛能力[10]。最具有代表性的为Holland提出的轮盘赌选择算子，其主要思想是根据个体适应度的比重来确定个体的保存概率与淘汰概率。由于其选择随机，所以可能出现“退化”现象，即优良个体没有被选中[]。李晨等人[10]提出了一种基于排序的多轮轮盘赌选择算子，这种算子是在传统的轮盘赌选择算子的基础上加入多轮盘排序。但是多轮轮盘赌选择算子在运行时速度较慢，只适应于小规模问题的解决。陈有青等人[12]提出了一种以组为单位进行轮盘赌选择的选择算子，根据选出的一组个体的特点进行高斯搜索形成新的群体，并且为了防止历史优良个体被破坏掉而提出了精英策略。郝国生等人[13]提出了一种基于三角函数的选择算子,并分析了此种选择算子的可行性，最后通过实验与其他选择算子进行性能的比较。Furtuna等人[14]利用神经网络改进精英非支配排序遗传算法。高航等人[15]提出了一种排序选择方法，该方法直接淘汰适应度低的1/4个体，保留适应度高的1/4个体，然后将中间的1/2个体进行轮盘赌选择，保证了GA 的收敛效率，但是在交叉运算后进行变异操作，变异概率是根据迭代次数变化的（最高适应度的变异概率不为0），如果不进行历史优良个体保留，那么优良的个体很有可能会在变异中丢失，并且此算法直接去除了适应度差的1/4个体，无法均衡的种群多样性。针对以上多种选择算子的思想，本文提出了一种将排序选择方法与最优和最差保存策略结合的选择方法，这样既保存了优良个体，淘汰了较差个体，又均衡了种群多样性，也保证了收敛的速度。

在算法执行策略上的研究，即为了提高遗传算法的收敛速度和求解精准度，将遗传算法和其他寻优方法（如模拟退火算法、蚁群算法等）相结合[16]。Xia 等人[17]提出了一种 K-means基因重组的遗传算法。刘露等人[18提出了一种新型混合智能优化算法一粒子群改进遗传算法，该算法主要是在传统粒子群与遗传算法的基础上,与模拟退火等常用算法相结合,经检验新算法相对于传统单一优化算法具有一定的先进性。Zhang 等人[19]在遗传算法的基础上提出了一种并行框架以提高遗传算法的效率。矫德强等人[20]用遗传算法与非线性寻优来优化蚁群算法，通过改进达到解决单纯使用蚁群算法与单独使用遗传算法收敛速度慢及容易陷入最优解的问题。

基于以上方面的研究，考虑到原始遗传算法交叉概率与变异概率恒定不变的缺点，本文提出一种新的改进的自适应遗传算法。主要通过分析种群进化过程中适应度的离散程度来非线性的自适应调节遗传算法的交叉概率与变异概率值，并在此基础之上更加全面的考虑了多种适应度的分布，同时又在中间段加入保留父本的策略，这样不仅防止错失在中间操作过程中产生的具有更高适应度的个体，而且保持了种群数目的恒定。选择操作上将排序选择策略与最优和最差保存策略相结合，利用最优保存策略可以更好地将父本较高适应度个体保留下来，利用最差保存策略可以将种群中最差的个体保留下来，以此来平衡种群的多样性。这样既保证了优良个体的保存，也保证了算法的收敛效率以及种群多样性的均衡性。

# 1 改进的自适应遗传算法

# 1.1改进的自适应遗传算法流程

基本遗传算法流程主要包括交叉运算、变异运算与选择运算。交叉算子主要是通过种群之间的基因交换来实现的，从而完成种群中优良基因的保存，如果种群中所有个体都缺失某一个优良基因，这时候就需要变异算子发挥作用了，变异算子通过对个体的基因突变来实现对缺失优良基因的获得。传统的遗传操作都是先进行交叉操作，可是当种群适应度较小且较为集中的时候，进行交叉操作不利于优良个体的快速产生，并且到了进化后期种群适应度较大且较为集中的时候再利用恒定的变异率进行变异操作会严重破坏到优良个体，降低了收敛效率。鉴于上述分析，本文提出了一种新的的自适应遗传算法（newadaptive genetic algorithm，NAGA）的执行流程。改进自适应算法NAGA的流程：

a)编码初始群体（L），设置各个参数;b)设置适应度函数，计算各个体的适应度值，保留最大适  
应度个体T1;c)判断是否满足收敛条件，如果满足收敛条件，则输出结  
果，否则进入步c）；d)判断π／12≤arcsin $( f _ { _ { a V e } } ~ / ~ f _ { _ { \mathrm { m a x } } } ) < \pi ~ / ~ 3$ 是否成立，  
如果成立，先执行变异操作（L)，然后进行交叉操作（此操作  
保留父代）；反之先执行交叉操作；e）回到步骤b）。求解流程图如图1所示。

# 1.2改进自适应算法的选择算子

将个体按适应度从小到大进行排序，淘汰掉排序位于后1/4适应度小的（记录下最小的适应度个体），复制前1/4适应度大的做父本，保留中间1/2继续操作。这样既淘汰掉了不良的个体又保存了优良的父本，保证了遗传算法的收敛效率，从而使算法可以较快的找到最优解。

然后，将上一步中保留下来的1/2种群计算出个体的选择概率：

$$
\left\{ \begin{array} { c } { { p _ { k } ^ { N } = Q ^ { N } ( 1 - q ^ { N } ) ^ { k - 1 } } } \\ { { } } \\ { { Q ^ { N } = \displaystyle \frac { q ^ { N } } { 1 - ( 1 - q ^ { N } ) ^ { L / 2 } } } } \end{array} \right.
$$

其中： $p$ 是个体的选择概率， $k$ 是个体在种群中的排列序号， $q$ 是最佳个体的选择概率， $k = 1 , 2 , 3 . . . . . , L / 2$ ， $\_ L$ 为种群个数， $N$ 为当前迭代次数。对于 $q$ 值来说，在种群进化初期，个体之间差异比较大，为了保证选择更多的优良个体，所以适应度大的个体应该同样具有较大的选择概率。随着种群的不断进化，种群之间的差异越来越小，相应的最佳个体的选择概率应该适当减小。因此提出一种按照迭代次数变化的 $q$ 值：

$$
q ^ { N } = q _ { \mathrm { _ { m a x } } } - ( q _ { \mathrm { _ { m a x } } } - q _ { \mathrm { _ { m i n } } } ) \times \frac { N - 1 } { M - 1 } ,
$$

其中： $q _ { \operatorname* { m a x } }$ 、 $q _ { \mathrm { m i n } }$ 分别是最初定义的最佳个体和最差个体的选择概率，M是总迭代次数。

![](images/626d197e274b669465e9b35321f509949cade97c9c27f2f67d1cb1e74c581f3a.jpg)  
图1改进的算法的运算流程图

从保留下来的个体组成的新种群中按照以上概率选择方式选择一半个体作为父代的一部分，与第一步中复制下来的前1/4部分一起组成一个个体数量为L/2的父代种群。为了保持种群数目恒定加入了一次父代保留操作，同时防止了中间过程中产生或者错过更优良的个体，本文又采用了最优保存策略[5]，即把每个种群都进行适应度的计算，最后将前一代的最高适应度T1与子代中的最高适应值比较，如果T1高于子代的最高适应度，就随机淘汰掉子代中的一个个体，把前一代中最高适应度个体加入到新一代中产生一个新的种群，此种保存策略保证了前一代的优良个体不会被交叉变异等遗传操作破坏。同时为了均衡种群多样性，本文又采用了最差保存策略，即把记录下来的最差适应度个体与新产生的种群最差适应度个体进行比较，如果低于新种群的最差适应度，就随机淘汰掉新种群中的一个个体，把前一代中最低适应度个体加入到新一代中产生一个新的种群，此种方法即不大规模的影响种群进化的方向，又能够均衡种群的多样性。

# 1.3自适应调节交叉概率 $P _ { c }$ 与变异概率 $P _ { \mathit { m } }$ 的值

为了更充分地利用交叉概率 $P _ { c }$ 和变异概率 $P _ { { _ m } }$ 在遗传操作

中发挥作用，本文提出交叉概率 $P _ { c }$ 和变异概率 $P _ { { _ m } }$ 的值的自适应公式，如式(3)(4)所示。

$$
P _ { c } = \left\{ \begin{array} { l l } { \displaystyle \arcsin ( \frac { f _ { a v e } } { \pi \mathrm { ~ a r ~ } } ) } & {  \displaystyle \arcsin ( \frac { f _ { a v e } } { f _ { \mathrm { { n a x } } } } ) } \\ { \displaystyle \arctan ( \frac { f _ { a v e } } { \pi \mathrm { ~ a r ~ } } ) } & {  \displaystyle \arcsin ( \frac { f _ { a v e } } { f _ { \mathrm { n a x } } } ) \ge \pi / 6 } \\ { \displaystyle \operatorname* { l i m } _ { \pi / 2 } } & {  \displaystyle \arcsin ( \frac { f _ { a v e } } { f _ { \mathrm { n a x } } } ) } \end{array} \right.
$$

$$
P _ { \mu } = \left\{ \begin{array} { l l } { \displaystyle \arcsin ( \frac { f _ { a v e } } { f _ { \mathrm { m a x } } } ) } & { \displaystyle \arcsin ( \frac { f _ { a v e } } { f _ { \mathrm { m a x } } } ) < \pi / 6 } \\ { \displaystyle \arctan ( \frac { f _ { a v e } } { f _ { \mathrm { m a x } } } ) } & { \displaystyle \arcsin ( \frac { f _ { a v e } } { f _ { \mathrm { m a x } } } ) < \pi / 6 } \end{array} \right.
$$

之所以用arcsin $( \ v { f } _ { a v e } ^ { } \ / \ \ v { f } _ { \mathrm { m a x } } ^ { } )$ 作为判断原是因为随着$\boldsymbol { f } _ { a v e }$ 的变化，arcsin $( \boldsymbol { f } _ { a v e } ^ { } \mathrm { ~ / ~ } \boldsymbol { f } _ { \mathrm { { n a x } } } ^ { } )$ 的变化会更快，这样便能更好地判断种群适应度之间的集中分散程度。之所以用是否大于等于 $\pi / 6$ 来判断是因为 $\sin \left( \pi \mathrm { ~  ~ { ~ \ / ~ } ~ } / 6 \right) = 1 / 2$ ，所以当arcsin $( f _ { _ { a v e } } \mathrm { ~ / ~ } f _ { _ { \mathrm { m a x } } } ) \ge \pi / 6$ 时 $f _ { _ { a v e } } \mathrm { ~ / ~ } f _ { _ { \mathrm { m a x } } } \ge 1 / 2$ ，这说明适应度平均值接近适应度最大值，即种群适应度接近最大适应度集中分布，然后在式(3)(4)的基础上再利用条件：$\pi ~ / ~ 1 2 \leq \arcsin { ( f _ { _ { a v e } } ~ / ~ f _ { _ { \mathrm { m a x } } } ) } < \pi ~ / ~ 3$ 来判断是否先进行交叉，如果符合条件则先进行交叉，否则先进行变异操作。因为在种群中容易出现除最高适应度之外其余适应度都集中很小的情况，此时的 $f _ { a v e }$ / $f _ { \mathrm { m a x } } { \langle 1 / 2 }$ ，如果根据IAGA 算法思想则将此种情况列为种群处于分散状态，将先进行交叉操作，但是此种情况下种群集中在较小适应度下，种群差异度较小种群不丰富，如果先进行交叉会使得种群进化速度加慢，导致收敛慢或不易收敛，正是考虑到此种情况文中创新性的改变了条件公式，使得改进算法考虑更加全面。

# 2 改进遗传算法在函数优化中的验证

# 2.1仿真实验与性能分析

为了验证改进的遗传算法NAGA的优化效果，本文选取了两个不同的一维连续函数，通过测试这两个函数的最优值、收敛次数、迭代次数等因素与经典遗传算法GA和杨从锐等人提出的 IAGA 算法进行比较。函数$f _ { 1 } ( \boldsymbol { x } ) = 2 ^ { ( - 2 ( \boldsymbol { x } - 0 . 1 ) / 0 . 9 ) ^ { 2 } } \mathrm { s i n } ^ { 6 } ( 5 \pi \boldsymbol { x } ) + 7 \cos { ( 4 \boldsymbol { x } ) } + 7$ ，其中$X \in [ 0 , 2 ]$ ：函数 ${ \mathit { f } } _ { 2 } ( { \mathit { x } } ) \ = 1 - { \frac { \sin \left( \mathrm { { 1 0 } } \pi x \right) } { \displaystyle { \mathit { x } } } }$ ，其中 $X ~ \in ~ \left[ 1 , 2 \right]$ ；$f _ { 3 } ( x ) { = } 2 1 . 5 { + } \mathrm { x s i n } \left( { 4 } \pi \mathrm { x } \right) { + } \mathrm { y s i n } \left( 2 0 \pi \mathrm { y } \right)$ ，其中 $- 3 . 0 \leq x \leq 1 2 . 1$ ，

$4 . 1 \leq y \leq 5 . 8$ 。求 $f _ { 1 } ( \boldsymbol { x } )$ 、 $f _ { 2 } ( \boldsymbol { \boldsymbol { x } } )$ 、 $f _ { 3 } ( \boldsymbol { x } )$ 的最大值。

GA、IAGA、和NAGA三种算法都采用的是二进制编码，测试试验中所用参数设置：函数 $f _ { 1 } ^ { - } ( \boldsymbol { x } )$ 中染色体长度为32位，迭代次数为450代，种群大小为100，GA算法的交叉概率为0.6，变异概率为0.01；在函数 $f _ { 2 } ( \boldsymbol { x } )$ 中染色体长度为20，种群大小为40，迭代次数为20，GA算法的交叉概率为0.7，变异概率为0.01。IAGA与NAGA 算法中 $k _ { 1 }$ 和 $k _ { 2 }$ 分别取1.0和0.5。

# 2.2函数 $f _ { 1 } ( \boldsymbol { x } )$ 在多种遗传算法下的计算结果比较

通过计算函数 $f _ { 1 } ^ { ( } ( \boldsymbol { x } )$ 在 $X \in [ 0 , 2 ]$ 的情况下最大值，将本文提出的改进的遗传算法与GA算法、IAGA算法进行结果比较。从图2(a)、(b)两张图可以看出没有经过改进的GA算法，其种群的适应度平均值是比较接近种群的最大适应度，这样极容易使得产生的新的个体难以摆脱局部极值，而经过改进的自适应遗传算法NAGA产生种群的适应度平均值是相对波动较大，这样保证了平均值不至于全部集中在较大值附近，这样有利于新产生的个体摆脱局部极值点。所以自适应的改变遗传算法的交叉率、变异率有利于种群更好地摆脱局部极值点。当种群的平均适应度值接近最大适应度值时，自适应的增加变异概率，减小交叉概率，可以使种群跳出局部极值点，从而加强算法的寻优能力。

为了观察方便将图2(c)(d)两张图放大，可以看出IAGA算法的收敛速度明显小于本文改进的NAGA算法的收敛速度。由于IAGA算法只用了最优保存策略，对于优良个体的保存较少，而NAGA算法不仅运用了排序选择算法保留适应度大的1/4个体，而且还与最优和最差保存策略相结合，这样不仅提高了种群进化的速度，而且还均衡了种群多样性。为了更直接观察到各遗传算法的求解能力，把3种算法以总迭代次数为450次重复30次后，从搜索到最优解的迭代次数、最优值、收敛概率以及重复30次其中收敛的次数这几个因素将这3种算法进行对比，结果如表1所示，表中为重复次数为30次的平均值。

表1函数fi(x)的计算结果  

<html><body><table><tr><td>算法</td><td>最优解</td><td>迭代次数</td><td>收敛次数</td><td>收敛率</td></tr><tr><td>GA</td><td>6.899940357765080e+04</td><td>417</td><td>14</td><td>0.447</td></tr><tr><td>IAGA</td><td>6.899941720268676e+04</td><td>248</td><td>25</td><td>0.833</td></tr><tr><td>NAGA</td><td>6.899941721750828e+04</td><td>110</td><td>30</td><td>1</td></tr></table></body></html>

![](images/ef25706a9cca1d1d597b5dc2027378cbfbc2fd18e829d7a409407c52bd649baa.jpg)  
(a)GA迭代450次平均值结果图

![](images/3295ec542ccac66fcd4f7c4e143f7e8821f905dcfb157b45762c57f042ac35d0.jpg)  
(b)NAGA迭代450次平均值结果图

![](images/8a3b08596ef4f60855719d3df440058ffbca4b038ed9b1aa35a79d21bdf1d542.jpg)  
(c)IAGA迭代450次最优值进化结果图

![](images/7ca0eedf6a33e1b198afb29b93cddbd0a063a5ac37f1c4bdb2aa5547f6b6bb5f.jpg)  
(d)NAGA迭代450次最优值进化结果图   
图2基于函数 $\operatorname { f } _ { 1 } ( \mathbf { x } )$ 的仿真结果图

由于是求最大值，所以从表1可以容易看出NAGA算法所得到的最优解较GA、IAGA大，并且更接近理论最优值，因此文中改进算法求解的精确度更高，并且迭代次数由417(GA)、248(IAGA)减小到了124(NAGA)。因此可以看出文中改进算法收敛速度更快，除此之外在重复30次之后函数 $f _ { 1 } ^ { \prime } ( x )$ 的收敛次数由14(GA)、25(IAGA)到30(NAGA)，说明本文改进的遗传算法稳定性更好。

# 2.3函数 $f _ { 2 } ( x )$ 在多种遗传算法下的计算结果

通过计算函数 $f _ { 2 } ( \boldsymbol { \boldsymbol { x } } )$ 在 $X \in [ 1 , 2 ]$ 的情况下最大值，将文中提出的改进的遗传算法与GA 算法、IAGA 算法进行结果比较。本文把三种算法以总迭代次数为20次重复30次后，从最优值、搜索到最优解的迭代次数以及重复30次其中收敛的次数和收敛概率这几个因素将这三种算法进行对比，结果如表2所示，表中为重复次数为30次的平均值。

表2函数 $\mathrm { f } _ { 2 } ( \mathrm { x } )$ 的计算结果  

<html><body><table><tr><td>算法</td><td>最优解</td><td>迭代次数</td><td>收敛次数</td><td>收敛概率</td></tr><tr><td>GA</td><td>1.869852651967255</td><td>19</td><td>9</td><td>0.300</td></tr><tr><td>IAGA</td><td>1.869894686000132</td><td>13</td><td>9</td><td>0.300</td></tr><tr><td>NAGA</td><td>1.869898595769486</td><td>9</td><td>30</td><td>1</td></tr></table></body></html>

由于是求最大值，所以从表1可以容易看出NAGA算法所得到的最优解较GA、IAGA大并且更接近理论最优值，因此文中改进算法求解的精确度更高。图3是三种算法对于函数$f _ { 2 } ( \boldsymbol { \boldsymbol { \chi } } )$ 的仿真图像，由图3可以看出文中改进算法收敛速度更快，并且迭代次数由18(GA)、13(IAGA)减小到了9(NAGA),同样证明了文中改进算法收敛速度更快，除此之外在重复 30次之后函数 $f _ { 2 } ( \boldsymbol { x } )$ 的收敛次数由8(IAGA)、9(GA)、到15(NAGA)，说明本论文改进的遗传算法稳定性更好。

![](images/94d0e0abb1176fb3e0cc7317d2f9594d651cfde221f285803b848a6b1fe4beb1.jpg)  
图3基于函数 $\mathrm { f } _ { 2 } ( \mathbf { x } )$ 的三种算法仿真结果对比图

# 2.4函数 $f _ { 3 } ( x )$ 在多种遗传算法下的计算结果

通过计算二元函数 $f _ { 3 } ( \boldsymbol { \chi } )$ 在 $X \in [ - 3 , 1 2 . 1 ]$ ， $y \in \left[ 4 . 1 , 5 . 8 \right]$ 情况下的最大值，经理论计算得出函数 $f _ { 3 } ( \boldsymbol { x } )$ 的理论值为38.8503。将文中提出的改进的遗传算法与GA算法、IAGA算法进行结果比较。本文把三种算法以总迭代次数为500次重复5次后，将这三种算法进行对比，结果如表3\~5所示。

表3GA优化函数 $\mathrm { f } _ { 3 } ( \mathrm { x } )$ 的结果  

<html><body><table><tr><td>第i次</td><td>X</td><td>y</td><td>最优值</td><td>收敛次数</td></tr><tr><td>1</td><td>11.6422</td><td>5.52577</td><td>38.392</td><td>449</td></tr><tr><td>2</td><td>11.6341</td><td>5.41918</td><td>38.1179</td><td>412</td></tr><tr><td>3</td><td>12.0988</td><td>5.42093</td><td>38.1959</td><td>475</td></tr><tr><td>4</td><td>11.6388</td><td>4.93109</td><td>37.5396</td><td>414</td></tr><tr><td>5</td><td>11.6124</td><td>5.32964</td><td>38.0718</td><td>391</td></tr><tr><td></td><td>表4</td><td>IAGA优化函数f3(x)的结果</td><td></td><td></td></tr><tr><td>第i次</td><td>X</td><td>y</td><td>最优值</td><td>收敛次数</td></tr><tr><td>1</td><td>11.6255</td><td>5.72506</td><td>38.8503</td><td>465</td></tr><tr><td>2</td><td>11.6276</td><td>5.42639</td><td>38.5273</td><td>381</td></tr><tr><td>3</td><td>11.6262</td><td>5.42484</td><td>38.5495</td><td>364</td></tr><tr><td>4</td><td>11.625</td><td>5.42509</td><td>38.55</td><td>323</td></tr><tr><td>5</td><td>11.6287</td><td>5.42504</td><td>38.5412</td><td>362</td></tr></table></body></html>

表5NAGA优化函数 $\mathrm { f } _ { 3 } ( \mathrm { x } )$ 的结果

<html><body><table><tr><td>第i次</td><td>X</td><td>y</td><td>最优值</td><td>收敛次数</td></tr><tr><td>1</td><td>11.6245</td><td>5.72493</td><td>38.8492</td><td>380</td></tr><tr><td>2</td><td>11.6255</td><td>5.72506</td><td>38.8503</td><td>289</td></tr><tr><td>3</td><td>11.6258</td><td>5.72507</td><td>38.8502</td><td>279</td></tr><tr><td>4</td><td>11.6255</td><td>5.72506</td><td>38.8503</td><td>292</td></tr><tr><td>5</td><td>11.6255</td><td>5.72506</td><td>38.8503</td><td>302</td></tr></table></body></html>

从表3\~5可以看出GA、IAGA、NAGA算法在求解二元函数时，GA算法所求结果波动明显，并且距离理论值有一定的距离，IAGA算法虽然有收敛到理论值，但是收敛次数较大，且收敛到理论值次数较少。NAGA所求的函数最优值结果较为稳定，并且接近理论最优值，而且相对于IAGA和GA算法NAGA在收敛速度上也略显优势。因此可以说明改进的NAGA算法在函数求解收敛程度上有一定的提高。

# 3 结束语

本文提出的NAGA算法有效地把握了总体的进化方向，同时采用了IAGA算法自适应地调整交叉概率 $P _ { c }$ 和变异概率 $\boldsymbol { P } _ { \boldsymbol { m } }$ 的值来克服GA算法全局搜索能力差、未成熟收敛的缺点。并且本文改进IAGA算法的流程条件，充分考虑到适应度分布的多种可能情况，并在此基础上引进选择算子，将适应度高的个体记录下来，然后在选择操作后加入最优保存策略，这样保证了中间过程中的优良基因不会被接下来的遗传操作给破坏，同时将适应度低的个体及时淘汰，同时加入了最差保存策略，保存历史最差个体，从而平衡种群的多样性，提高收敛效率，而且在中间过程保留一次父本这样可以始终保证种群数量的稳定性。在一元、二元函数求解优化过程中与经典遗传算法GA和IAGA算法相比，本文的算法在收敛速度与精准度等方面都有较大的进步。

# 参考文献：

[1]Moussa M,Hmila M,Douik A.A novel face recognition approach based on genetic algorithm optimization [J]. Studies in Informatics & Control, 2018,27(1): 127-134.   
[2]Moeini A,Zargarabadi\* M R.Genetic algorithm optimization of film cooling effectiveness over a rotating blade [J]. International Journal of Thermal Sciences,2018,125:248-255.   
[3]Abdelsalam A M,El-Shorbagy M A.Optimization of wind turbines siting in a wind farm using genetic algorithm based local search [J].Renewable Energy,2018,123.748-755.   
[4]李树江，赵晨，苏锡辉，王向东．基于遗传算法优化PID控制器参数的 环境测试舱温湿度控制[J].南京理工大学学报，2017(4):511-518.(Li Shujiang,Zhao Chen，Su Xihui,Wang Xiangdong.Temperature and humidity Control of Environmental Test Cabin based on genetic algorithm to optimize parameters of PID Controller [J]. Journal of Nanjing University of Science and Technology. 2017 (4): 511-518.)

[5] 海冉冉．基于云自适应遗传算法的优化问题研究[D].吉林：东北电力 大学，2O13.(Han Ranran.Research on Optimization problem based on Cloud Adaptive genetic algorithm [D].Jilin:Northeast Electric Power University. 2013)

[6]曲志坚，张先伟，曹雁锋，等．基于自适应机制的遗传算法研究[J].计算机应用研究，2015，32(11): $3 2 2 2 - 3 2 2 5 + 3 2 2 9$ .(Qu Zhijian, ZhangXianwei,Cao Yanfeng，et al.Genetic algorithm based on adaptivemechanism [J].Computer Application Researches，2015,32 (11):$3 2 2 2 - 3 2 2 5 + 3 2 2 9 .$ ）

[7]冯磊华，杨锋.基于改进遗传算法优化的气动盾形闸门模糊 PID 控制 研究[J].水利规划与设计,2017(12):98-101.(FengLeihua,Yang Feng. Fuzzy PID Control of Pneumatic Shield Gate based on improved genetic algorithm [J].Water Conservancy Planning and Design，2O17(12): 98-101. )

[8]Srinivas M.PatnaikLM.Adaptive probabilities of crossover and mutation in genetic algorithms [J].IEEE Trans on System,Man,and Cybernetics, 1994,24 (4): 656-667.

[9]杨从锐，钱谦，王锋，孙铭会.改进的自适应遗传算法在函数优化中的应用[J].计算机应用研究，2018，35(4):1042-1045.（YangCongrui,Qian Qian,Wang Feng,Sun Minghui.Application of improved adaptivegenetic algorithm in function optimization [J]. Computer ApplicationResearch,2018,35(4): 1042-1045.)

[10]李晨，宁红云．改进的遗传算法选择算子[J].天津理工大学学报， 2008,24 (O6):1-4.(Li Chen, Ning Hongyun. Improved genetic algorithm selection operator [J].Journal of Tianjin University of Technology,2008, 24 (06): 1-4. )

[11]蒋艳，黎向锋，左敦稳，焦光明，薛善良．多种改进选择算子的遗传算 法性能比较与应用研究[J].中国制造业信息化，2010,39(11):46-50. (Jiang Yan,Li Xiangfeng,Zuo Dunwen,et al.Performance comparison and Application of genetic algorithms with improved selection operators [J].China's manufacturing information,2010,39 (11): 46-50.)

[12]陈有青，徐蔡星，钟文亮，等．一种改进选择算子的遗传算法[J].计 算机工程与应用,2008,44(2):44-49.(Chen Youqing,Xu Caixing,Zhong Wen Liang,Zhang Jun.An improved selection operator genetic algorithm

[J].computer engineering and Application,2008,44 (2): 44-49.)   
[13]郝国生，严玉若，黄永青，等．基于三角函数的遗传算法选择算子[J]. 江南大学学报：自然科学版，2010,9(2):162-165.(Hao Guosheng,Yan Yurou,Huang Yongqing，et al. Selection operator of genetic algorithm based on trigonometric function [J].Journal of Jiangnan University: Natural Science Edition,2010,9(2): 162-165.)   
[14] Furtuna R,Curteanu S,Leon F. An elitist non-dominated sorting genetic algorithm enhanced with a neural network applied to the multi-objective optimization ofa polysiloxane synthesis process [J].Engineering Applications of Artificial Intelligence,2011,24(5): 772-785.   
[15]高航，薛凌云．基于改进遗传算法的反向传播神经网络拟合LED 光谱 模型[J].激光与光电子学进展,2017,54(7):294-302.(Gao Hang, Xue Lingyun.Back Propagation Neural Network based on improved genetic algorithmto fit LED Spectral Model [J].Progressin laserand optoelectronics,2017,54(7): 294-302.)   
[16]郎敏峰．遗传算法的改进及其在组合优化中的应用 [D].上海：华东师 范大学,2Oo5.(Lang Minfeng.The improvement of genetic algorithm and its application in combinatorial optimization [D]. Shanghai: East China normal University. 2005.）   
[17] Xia Changdong,Zhang Xiada,Zheng Changwang.A genetic algorithm with gene rearrangement for K-means clustering [J].Pattern Recognition, 2009,42(7): 1210-1222.   
[18]刘露，陈赞，刘世劫，等．一种新型粒子群改进遗传算法[J].微型机 与应用,2017,36 (23):17-20.(Liu Lu,Chen Zan,Liu Shijie,et al.A new particleswarmoptimizationimprovedgeneticalgorithm[J]. Microcomputer and its Application,2017,36 (23): 17-20. )   
[19] Zhang Xin, Zhang Qinglian, Zhang Xiu. Nonuniform antenna array design byparallelizing three-parent crossover genetic algorithm [J].Eurasip Journal on Wireless Communications & Networking,2017,2017 (1):106.   
[20]矫德强，常淮阳．一种改进蚁群算法 TSP 问题上的应用[J].科技与创 新,2018 (1):145-146.(Jiao Deqiang,Chang Huaiyang.Application of an improved ant colony algorithm TSP problem [J]. Science,Technology and Innovation,2018(1): 145-146.)