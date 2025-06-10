# 基于交叉迁移和共享调整的改进蝴蝶优化算法

孙林1,2†，陈岁岁1，徐久成1²，王振华1(1.河南师范大学 计算机与信息工程学院，河南 新乡 453007；2.河南省高校计算智能与数据挖掘工程技术研究中心，河南 新乡 453007)

摘要：针对蝴蝶优化（monarch buterfly optimization，MBO）算法易陷入局部最优和收敛速度慢等问题，提出了一种基于改进的交叉迁移和共享调整的蝴蝶优化（MBO with cross migration and sharing adjustment，CSMBO）算法。首先，利用基于维度的垂直交叉操作来替换标准 MBO算法的迁移算子，形成交叉迁移算子，有效提升其搜索能力；其次，将原始调整算子改为具有信息分享功能的共享调整算子，以加快算法的收敛速度；最后，采用贪婪选择策略取代标准MBO算法中的精英保留策略，减少一次排序操作进而提高其计算效率。为了验证CSMBO 算法的优化能力，测试了其在30维和50维的函数优化，并与三种优化算法进行比较，其实验结果表明CSMBO算法具有良好的优化性能。

关键词：智能优化；蝴蝶优化；交叉迁移；共享调整 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.07.0611

Improved monarch butterfly optimization algorithm based on cross migration and sharing adjustment

Sun Lin1,2t, Chen Suisui1, Xu Jiucheng1,2, Wang Zhenhual (1. College of Computer & Information Engineeing,Henan Normal University， Xinxiang Henan 45307,China;2. EngineeringTechnologyResearch CenterforComputing Intelligence&Data Miningof Henan Province,Xinxiang Henan 453007, China)

Abstract:Inorder tosolve the problems ofthemonarchbutterflyoptimization(MBO)algorithm,such as it is easytofal intolocaloptimumandtheconvergence speed islow,thisstudy proposedan improved MBO algorithm with cross migration and sharng adjustment (CSMBO).Firstly，this paper introduced a dimension-based vertical crosover operation to substitute theoriginal migrationoperationof MBO,and thengeneratedacrossmigrationoperator.Thus,thisoperation could improve search abilityof MBO algorithm effectively.Secondly,in order to speed up the convergence of MBO algorithm,the sharing adjustmentoperator with informationsharingreplacedtheoriginaladjustmentoperator.Finaly,this paper utilized the greedy strategy to instead ofthe elite strategyof MBO,which could reduce one sorting operation and improve thecalculation eficiencyof MBO algorithm.To evaluate theoptimization abilityofour CSMBO algorithm,this paper made some experiments on asetof common benchmark functions with 30-dimensions and 50-dimensions,and the results showed that the proposed CSMBO algorithm had good optimization performance,and outperformed currently available three optimization approaches with which it is compared.

Key Words: intelligent optimization; monarch buttrfly optimization; cross migration; sharing adjustment

# 0 引言

优化是在某些约束条件下搜索和找到给定问题的最佳解的过程[1。对于优化算法，它们可以分为确定性算法和随机算法两大类[2]。近年来，许多可以转换成优化问题的现实问题变得越来越复杂，并且很难通过确定性算法来解决[3-5]。因此，在实际应用中对随机算法的研究已成为一个很有前景的热点课题[6,7]。如今，群智能优化算法作为随机算法的一个重要分支，已展示出解决复杂优化问题的强大而有效的能力[8]。其中比较著名的有：粒子群优化算法（particleswarmoptimization,PSO）[9-12]、烟花算法[13]、生物地理学优化算法[14]、蝴蝶优化（MBO）算法[15]、萤火虫优化算法[16\~18]等。而在这其中，蝴蝶优化算法因其优化性能优异而得到广泛关注。

蝴蝶优化算法是2015年由Wang等人[15]受自然界黑脉金斑蝶迁徙行为启发而提出的。MBO算法有两个重要的算子即迁移算子和调整算子。前者提供一定的局部搜索能力，后者提供一定的全局搜索能力。在MBO 算法中，蝴蝶的搜索方向由迁移算子和调整算子确定，而这两个算子可以同时执行，因此，MBO算法很适合用于并行处理，并且能够很好

收稿日期：2018-07-16；修回日期：2018-10-31基金项目：国家自然科学基金资助项目（61772176，61402153，160130)；中国博士后科学基金资助项目（2016M602247)；河南省科技创新人才项目（18410051003）；河南省科技攻关项目（1821020362，182102210078）；河南省高校青年骨干教师培养计划项目（2017GGJS041)；河南省自然科学基金资助项目（182300410130，182300410368)；新乡市科技攻关计划项目（CXGG17002）；河南省高等学校重点科研计划项目（1A520069，17A520038，16A520015)；河南师范大学博士科研启动费支持课题（qd15132)；河南师范大学青年科学基金项目(2015QK23)；国家教育部产学合作协同育人项目 (201702115008)

作者简介：孙林(1979-)，男(通信作者),河南南阳人，副教授,硕导，博士，主要研究方向为粒计算、智能优化算法、大数据挖掘等(sunlin@htu.edu.cn)；陈岁岁（1993-)，女，河南商丘人，硕士研究生，主要研究方向为智能优化算法、数据挖掘等；徐久成（1964-)，男，河南洛阳人，教授，博导，博士，主要研究方向为粒计算、大数据挖掘等；王振华（1978-)，男，河南新乡人，讲师，硕士，主要研究方向为智能优化算法.

地平衡局部搜索和全局搜索。由于MBO 算法参数少且易于实现，已经被广泛应用到很多领域，如0-1背包问题[19]、自动电压调节[20]、神经网络训练[21]、动态路径问题[22]、骨质疏松症的分类问题[23]等。但MBO算法在解决一些复杂问题时仍存在搜索能力较弱等缺陷。因此，许多学者对其进行了改进研究。Wang 等人[24提出了一种基于自适应交叉算子和贪婪策略的 MBO（monarch butterfly optimization with greedystrategy and self-adaptive crossover operator,GCMBO）算法,提高了MBO算法的优化能力；Feng等人[25]将混沌理论和高斯变异引入MBO算法，增强了MBO算法的全局优化性能；蒙丽萍等人[26]采用将种群动态随机分割成两个子群体的策略，以保持种群搜索的多样性；Feng等人提出了一种多策略的 MBO 算法，以帮助 MBO 算法跳出局部最优点[27]；Feng等人[28将反向学习和高斯扰动引入MBO算法，从而加快MBO 算法的收敛速度；Hu等人[29]提出了一种自适应种群策略的MBO 算法，提高了MBO 算法的探索能力等。此外，MBO 算法也经常和其他优化算法进行结合。Ghanem 等人[30]将MBO算法和人工蜂群优化算法结合，以解决数值优化问题；Ghetas 等人[31将和声搜索算法与MBO 算法进行结合，提高了MBO算法的优化性能。然而，上述一些算法仍存在易陷入局部最优和收敛速度慢等问题，尤其是在解决一些复杂优化问题时，仍存在很大的改进空间。

本文针对 MBO 算法易陷入局部最优和收敛速度慢等问题，提出了一种基于改进的交叉迁移和共享调整的新的MBO（CSMBO）算法。首先，针对MBO算法中的迁移算子，运用基于维度的垂直交叉操作替换原始迁移操作，形成新的交叉迁移算子，以增加种群多样性，提升其搜索能力，这样可以在一定程度上避免MBO算法陷入局部最优的问题；其次，将原始调整算子改为具有信息分享功能的共享调整算子，有效地利用种群的有效信息，进而加快MBO算法的收敛速度；最后，采用贪婪选择策略取代标准MBO算法中的精英保留策略，减少一次排序操作，有效提高了MBO 算法的计算效率。为了验证CSMBO算法的优化能力，在一组不同维度的基准函数上进行测试实验，其结果表明CSMBO算法在解决复杂问题上具有良好的优化性能。

# 1 标准MBO算法

MBO的相关知识可以参见文献[15，24]。在MBO算法中，所有的蝴蝶个体都是理想化的，仅位于美国北部和加拿大南部（区域1）、墨西哥（区域2）两个区域。因此，蝴蝶的位置以迁移算子和调整算子两种方式更新。首先，后代的产生（位置更新）通过迁移算子；其次，其他蝴蝶的位置通过调整算子来更新。所以，蝴蝶个体的搜索方向是通过迁移算子和调整算子确定的，而且迁移算子和调整算子能够同时执行。因此，MBO算法非常适合并行处理，并且能很好地平衡局部搜索能力和全局探索能力。MBO 算法遵循如下理想规则：

a)所有的蝴蝶都只在区域1和2中。即区域1和2中的蝴蝶组成了整个蝴蝶种群。b)每一只蝴蝶后代都是区域1和2中的蝴蝶通过迁移算子产生的。c）为了保持种群数量不变，一旦有后代蝴蝶产生，就会有相应的父代蝴蝶消失。d)具有最好的适应度值的蝴蝶个体自动进入下一代，不对其进行任何操作。这样可以保证蝴蝶种群的质量不会随着迭代次数的增加而下降。

MBO算法的两个位置更新策略如下：

a）迁移算子。其目的是更新蝴蝶在区域1和2之间的迁徙。首先，蝴蝶总数为 $N P$ ，区域1和2中的蝴蝶数分别为$N P 1 = \mathrm { c e i l } ( p \times N P )$ 和 $\begin{array} { r l } { N P 2 } & { { } = N P - N P 1 } \end{array}$ ，其中 $p$ 为蝴蝶比例（迁移率)，MBO 算法设置 $p = \begin{array} { l } { 5 } \\ { 1 2 } \end{array}$ 2；ceil(x)）是舍入到大于或等于 $x$ 的最接近的整数。区域1的子群记为Subpopulation1,区域2的子群记为 Subpopulation2。因此，迁移算子可以表示为

$$
X _ { i , k } ^ { t + 1 } = \left\{ { \begin{array} { l l } { X _ { r _ { 1 } , k } ^ { t } , r \leq p } \\ { X _ { r _ { 2 } , k } ^ { t } , r > p } \end{array} } \right.
$$

其中： $\boldsymbol { x } _ { i , k } ^ { t + 1 }$ 为 $x _ { i }$ 在 $^ { t + 1 }$ 时刻的第 $k$ 维； $x _ { r _ { 1 } , k } ^ { t }$ 表示 $x _ { \eta _ { 1 } }$ 在 $t$ 时刻的第 $k$ 维； $\boldsymbol { x } _ { r _ { 2 } , k } ^ { t }$ 为 $x _ { r _ { 2 } }$ 在 $t$ 时刻的第 $k$ 维。当前迭代次数由 $t$ 表示。蝴蝶 $\mathbf { \Psi } _ { r 1 }$ 和 $r _ { 2 }$ 分别从 Subpopulation1 和 Subpopulation2 中随机选出。 $r = r a n d \times p e r i$ ，其中peri为迁移期，在MBO 算法中取$p e r i = 1 . 2$ ，rand是[0,1]中的随机数。

b）调整算子。其目的是更新Subpopulation2中蝴蝶的位置。对于蝴蝶 $j$ 的所有维，若rand $\leq p$ ，则该个体进行位置更新的公式如下：

$$
\boldsymbol { x } _ { j , k } ^ { t + 1 } = \boldsymbol { x } _ { b e s t , k } ^ { t }
$$

其中： $\boldsymbol { x } _ { j , \boldsymbol { k } } ^ { t + 1 }$ 为 $x _ { j }$ 在 $t + 1$ 时刻的第 $k$ 维； $\boldsymbol { x } _ { b e s t , k } ^ { t }$ 为Land1与Land2当中最好个体的位置； $\boldsymbol { x } _ { b e s t , k } ^ { t }$ 为 $x _ { b e s t }$ 的第 $k$ 维； $t$ 为当前迭代次数。

若rand $> p$ ，则该个体进行位置更新的公式如下：

$$
\boldsymbol { x } _ { j , k } ^ { t + 1 } = \boldsymbol { x } _ { r _ { 3 } , k } ^ { t }
$$

其中： $x _ { r _ { 3 } , k } ^ { t }$ 为 $x _ { r _ { 3 } }$ 的第 $k$ 维； $x _ { r _ { 3 } }$ 是从Land2中随机选出。在此条件下，若rand $> B A R$ ，则该个体进行位置更新的公式如下：

$$
x _ { j , k } ^ { t + 1 } = x _ { i , k } ^ { t + 1 } + \alpha ( d x _ { k } - 0 . 5 )
$$

其中：BAR为调整率，在MBO 算法中 $B A R \ = \ p$ 。如果BAR小于随机数rand，在 $t + 1$ 时刻的第 $k$ 维就会更新，其中权重因子 $\scriptstyle a$ 的计算方式为 $\alpha = { \frac { S _ { \mathrm { m a x } } } { t ^ { 2 } } }$ ， $S _ { m a x }$ 为蝴蝶的最大步长， $d x$ 为蝴蝶 $j$ 的步长，通过Levy flight计算 $d x = L e \nu y ( \ x _ { j } ^ { t } )$ 。

# 2 基于交叉迁移和共享调整的蝴蝶优化算法

# 2.1改进算法的动机

MBO算法的迁移算子采用式(1)所示的直接取代式迁移操作，虽然提供了一定的局部搜索能力，但迁移方式单一，可搜索位置局限，故将交叉操作与原迁移算子有机融合，形成交叉迁移算子，这样可以有效增加种群的多样性，提升算法的搜索能力。

从式(3)可以看出，第 $\textit { t + 1 }$ 代蝴蝶的信息是直接从第 $t$ 代继承的，于是可知这种直接继承的方法过于简单，没有充分利用种群的有效信息。因此，将共享操作与原调整算子结合来形成新的共享调整算子，这样可以有效地利用种群的优秀信息，有利于引导蝴蝶向最优解的方向靠近，进而加快算法的收敛速度。

标准MBO算法的精英保留策略需要设置参数和排序操作，增加了算法计算的复杂程度。因此，用贪婪选择策略替换精英保留策略，不仅可以避免精英参数的设置，而且还可以减少一次排序操作，进而降低算法的计算复杂度。

# 2.2 交叉迁移算子

鉴于MBO算法的迁移算子搜索能力不足，运用基于维度的垂直交叉操作取代其迁移算子的直接取代式迁移操作，形成新的交叉迁移算子，可以有效弥补原始迁移操作迁移形式简单、方向单一以及在解空间中可搜索到的位置较为局限的不足。下面给出新的交叉迁移算子，其计算公式可以表示为：

$$
\boldsymbol { x } _ { i , k } ^ { t + 1 } = \left\{ \begin{array} { l l } { \boldsymbol { c } \times \boldsymbol { x } _ { n , k } ^ { t } + ( 1 - c ) \times \boldsymbol { x } _ { n , q } ^ { t } , \boldsymbol { r } \le p } \\ { \boldsymbol { c } \times \boldsymbol { x } _ { r _ { 2 } , k } ^ { t } + ( 1 - c ) \times \boldsymbol { x } _ { r _ { 2 } , q } ^ { t } , \boldsymbol { r } > p } \end{array} \right.
$$

其中：垂直交叉缩放因子 $\mathrm { { c } = }$ rand， ${ \bf q } = \mathrm { r a n d } \times { \bf D }$ 。

对式(1)和式(5)的分析可知，在式(5)中，第 $t + 1$ 代蝴蝶的第 $k$ 维会受到第 $t$ 代蝴蝶的第 $k$ 维和第 $q$ 维( $q$ 是随机选择的）两者的共同影响，其具体方式是对两者进行加权交叉计算，这样可以增加种群的多样性，进而增强算法的搜索能力，有效克服式(1)存在的形式简单、方向单一等缺陷。

另外，由于贪婪选择策略具有只接受更优秀个体的优点，接下来可以将原迁移算子中的精英保留策略更换为贪婪选择策略，进而降低交叉迁移算子的计算复杂度。其表示公式如下：

$$
x _ { \mathrm { i , n e w } } ^ { t + 1 } = \left\{ { \begin{array} { l l } { x _ { i } ^ { t + 1 } , f ( x _ { i } ^ { t + 1 } ) < f ( x _ { i } ^ { t } ) } \\ { x _ { i } ^ { t } , { \mathrm { o t h e r w i s e } } } \end{array} } \right.
$$

其中： $\boldsymbol { x } _ { i , \mathrm { n e w } } ^ { t + 1 }$ 是下一代新生成的蝴蝶个体； $f ( \mathbf { X } _ { i } ^ { t + 1 } )$ 和 $f ( \mathbf { X } _ { i } ^ { t } )$ 分别表示蝴蝶 $\mathbf { X } _ { i } ^ { t + 1 }$ 和 $\mathbf { X } _ { i } ^ { t }$ 的适应度值。

下面给出交叉迁移算子的伪代码，如算法1所示。

算法1交叉迁移算子   
for $i = 1$ to $N P 1$ do for $k = 1$ to $D$ do 根据式(5)更新 ${ \boldsymbol { x } } _ { i , \mathrm { k } } ^ { t + 1 }$ end for $k$ （20 根据式(6)计算 $\boldsymbol { x } _ { i , \mathrm { n e w } } ^ { t + 1 }$   
end for i

# 2.3共享调整算子

针对调整算子中式(3)直接继承方式过于简单的缺点，为了充分利用种群中的有效信息，可以将共享操作合并到MBO算法的调整算子中，进而形成新的共享调整算子。其表示公

式如下：

$$
\boldsymbol { x } _ { j , k } ^ { t + 1 } = \boldsymbol { x } _ { b e s t , k } ^ { t } + ( r a n d - 0 . 5 ) \times ( \boldsymbol { x } _ { b e s t , k } ^ { t } - \boldsymbol { x } _ { r _ { 3 } , k } ^ { t } )
$$

其中： $\boldsymbol { x } _ { b e s t , k } ^ { t }$ 为种群中最好的个体 $x _ { b e s t }$ 在 $t$ 时刻的第 $k$ 维；rand是[0,1]中的随机数。

从式(7)可以看出，共享调整算子充分利用种群的有效信息，有利于引导蝴蝶向最优解的方向靠近，加快算法的收敛速度；同时，也将原始调整算子中的精英保留策略改为贪婪选择方案来提高共享调整算子的计算效率，其表示公式如式(6)所示。

下面给出共享调整算子的伪代码，如算法2所示。

算法2 共享调整算子 for $j = 1$ to NP2 do for $k = 1$ to $D$ do 取一个[0,1]区间的随机数rand ifrand $\leq p$ then 根据式(2)计算 ${ x } _ { j , k } ^ { t + 1 }$ else 从子群2（Subpopulation2）中随机选出一只蝴蝶 （记作 $\mathbf { \nabla } _ { r 3 }$ ） 根据式(3)计算 $\boldsymbol { x } _ { i , \mathrm { k } } ^ { t + 1 }$ if rand $>$ BARthen 根据式(4)计算x end if end if end for $k$ 根据式(6)计算 $\boldsymbol { x } _ { i , n \mathrm { e w } } ^ { t + 1 }$ end for j

# 2.4 CSMBO 算法总流程

在提出的交叉迁移算子和共享调整算子的基础上，给出CSMBO算法的流程如图1所示。

![](images/f29dc28bd9aaedcde0b72dc0eb16cb292ddb5f985a81116b0535f9e84107e675.jpg)  
图1 CSMBO算法流程  
Fig.1Main procedure of CSMBO algorithm

# 3 仿真实验

# 3.1测试函数与参数设置

为了测试本文提出的CSMBO算法的有效性，在一组不同维度的基准函数上进行四种算法的优化实验对比。表1中给出了八个测试函数的信息。它们包括单峰函数如 $f _ { 1 } { \sim } f _ { 5 }$ ，多峰函数如f～f。其中，单峰函数只有一个全局最优点，适合用于评估算法的搜索能力；多峰函数有多个局部最优点，适合用于评估算法的探索能力。 $F _ { m i n }$ 是函数的理论最优值。本文所有仿真实验均在操作系统为Windows7、CPU为主频$3 . 1 0 \mathrm { G h z }$ 和内存为4GB的PC上实施，编程语言采用MATLABR2014a。

在实验中，将本文提出的CSMBO算法与其他三种相关的优化算法（PSO[9]、MBO[15]、GCMBO[24]）进行优化性能对比分析。本文用四种算法对不同维度的基准函数进行优化实验，以便验证CSMBO算法的有效性、高优化效率和普适性等。函数的维度选择包括30维和50维。不同的维度选择可以增加寻优难度，以便验证CSMBO算法处理各种复杂优化问题的能力。四种算法的共同参数设置如表2所示。其中，最大迭代次数MaxGen随优化函数的维数增加而增加，其他参数设置均与相关文献的PSO、MBO、GCMBO保持一致。在表2中，选择两个维度（30维和50维）进行算法性能测试，其中30维对应的种群数量和最大迭代次数分别是50和1000，50维对应的种群数量和最大迭代次数分别是50和2000。在实验实施过程中，若种群规模过小，会导致算法收敛速度过慢；若种群规模过大，会增加算法的时间复杂度，浪费不必要的存储空间。在文献[24]提出的结合贪婪策略和自适应交叉算子的MBO算法、文献[26]提出的采用动态分割种群策略的改进MBO算法以及文献[29]提出的基于自适应种群的改进MBO算法中，均将种群规模设置为50，因此，本文在分配种群规模时，考虑到基准函数的维度和MBO算法的特点，也将种群规模设置为50。为了避免随机性对实验结果的影响，在仿真实验中，四种算法对每一个优化问题均独立进行30次实验。

Table 1Information of benchmark functions   
表2四种算法的参数设置  

<html><body><table><tr><td>函数</td><td>公式</td><td>定义域</td><td>Fmin</td></tr><tr><td>Quartic</td><td>f(x)=∑ix† +random[0,1) i=1</td><td>[-1.28,1.28]D</td><td>0</td></tr><tr><td>Schwefel 1.2</td><td>f（x）)=∑x）</td><td>[-100,100]D</td><td>0</td></tr><tr><td>Schwefel 2.21</td><td>f(x)= maxi(|xi|,1≤i≤d)</td><td>[-100,100]D</td><td>0</td></tr><tr><td>Step</td><td>f(x)=∑（x +0.5])² i=1</td><td>[-100,100]D</td><td>0</td></tr><tr><td>Rosenbrock</td><td>fs(x)= ∑(xi-1)² +100(x²-xit1)2) i=1</td><td>[-10,10]D</td><td>0</td></tr><tr><td rowspan="3">Penalized 1</td><td>f(x)=(10sin2()+(y−(10sin2()+(y) d i=l +∑u(x,10,100,4),</td><td></td><td></td></tr><tr><td>i= [k(xi-a)”,xi >a, 其中，yi=1+−(xi+1)，u(xi,a,k,m)={0,-a≤x≤a,</td><td>[-50,50]D</td><td>0</td></tr><tr><td>4 [k(-xi -a)”,xi<-a, d-1</td><td></td><td></td></tr><tr><td>Penalized 2</td><td>f7(x)=0.1(sin²(πx)+∑(x-1)²(1+sin²(3xi+)) i= (x -1)(1 + sin2(2πxd))+∑u(x ,100,4) i=1</td><td>[-50,50]D</td><td>0</td></tr><tr><td>Griewank</td><td>1 fs(x)= cos( )+1 i=l √i 4000台</td><td>[-600,600]D</td><td>0</td></tr></table></body></html>

表1基准函数信息  
Table 2Values of parameters of four algorithms   

<html><body><table><tr><td>种群数量</td><td>维度</td><td>最大迭代次数</td></tr><tr><td>50</td><td>30</td><td>1000</td></tr><tr><td>50</td><td>50</td><td>2000</td></tr></table></body></html>

# 3.2优化性能比较

在8个基准函数上对不同维度（30维和50维）的测试结果如表3和4所示。其中包含30次独立运行寻优结果中的最优值、最差值、平均值和标准差，粗体表示测试结果的最优者。文献[9]、文献[15]和文献[24]均指出平均值和标准差值越小说明算法的搜索能力越好且稳定性越强。

表3给出了四种算法在30维函数上的测试结果。从表3中的数值可以看出，在f和 $f _ { 5 } { \sim } f _ { 7 }$ 上，GCMBO 算法在最优值上是最好的，但是CSMBO算法的最差值、平均值和标准差在四种算法中都是最优的。值得一提的是，在fs和f6上，CSMBO算法的平均值和标准差明显比其他三种算法的结果更好。在 $f _ { 2 }$ 和 $f _ { 3 }$ 上，CSMBO 算法的优化结果均比其他三种算法优秀，特别是在 $f _ { 2 }$ 上，CSMBO 算法的结果大幅领先于其他三种算法。在 $f _ { 4 }$ 和 $f _ { 8 }$ 上，MBO 算法、GCMBO 算法和CSMBO算法在最优值的寻优上均取得了一致的结果，尤其是在f4上，都找到了函数的理论最优值，但是CSMBO算法的最差值、平均值和标准差的结果都是最好的。总之，从30维函数上的实验结果可知，本文提出的CSMBO算法的优化性能相对优异。

表4给出了四种算法在50维函数上的测试结果。从表4中可以看出，对于 $f _ { 1 }$ 和 $f _ { 3 }$ ，CSMBO算法的寻优结果均是最优的。在 $f _ { 2 }$ 上，PSO 算法的最差值和标准差是最好的，而

CSMBO算法的最优值和平均值是最优的。MBO算法、GCMBO算法和CSMBO算法均找到了 $f _ { 4 }$ 的理论最优值，但CSMBO算法的最差值、平均值和标准差结果都大幅优于其他三种算法。对于fs、f6和f，GCMBO 算法的最优值结果是最好的，而CSMBO算法在最差值、平均值和标准差的评价指标上是最优秀的。值得一提的是，在fs和f6上，CSMBO算法的结果都大幅度优于其他三种算法。总之，从50维函数上的实验结果可知，本文提出的CSMBO算法的优化性能是相对优秀的。

Table 3Results of four algorithms on 3O-dimensional functions   

<html><body><table><tr><td>函数</td><td>算法</td><td>最优值</td><td>最差值</td><td>平均值</td><td>标准差</td></tr><tr><td rowspan="4">fi</td><td>PSO</td><td>1.6029</td><td>12.6050</td><td>6.9126</td><td>2.5498</td></tr><tr><td>MBO</td><td>0.0015</td><td>122.1438</td><td>50.5840</td><td>45.3491</td></tr><tr><td>GCMBO</td><td>3.3127e-24</td><td>7.7247</td><td>1.5967</td><td>2.2949</td></tr><tr><td>CSMBO</td><td>4.5748e-20</td><td>1.6384</td><td>0.0629</td><td>0.2998</td></tr><tr><td rowspan="4">f</td><td>PSO</td><td>8.8927e+03</td><td>1.8163e+04</td><td>1.3409e+04</td><td>2.5485e+03</td></tr><tr><td>MBO</td><td>7.1783</td><td>6.5083e+04</td><td>2.4090e+04</td><td>1.8531e+04</td></tr><tr><td>GCMBO</td><td>3.8183</td><td>2.6657e+04</td><td>1.1791e+04</td><td>8.5563e+03</td></tr><tr><td>CSMBO</td><td>4.3512e-08</td><td>0.0015</td><td>6.3360e-05</td><td>2.7170e-04</td></tr><tr><td rowspan="4">f</td><td>PSO</td><td>37.4256</td><td>54.7068</td><td>46.3699</td><td>4.5268</td></tr><tr><td>MBO</td><td>0.0010</td><td>87.6419</td><td>33.0509</td><td>22.3718</td></tr><tr><td>GCMBO</td><td>0.0947</td><td>73.3843</td><td>31.8467</td><td>23.9338</td></tr><tr><td>CSMBO</td><td>6.6164e-05</td><td>12.2039</td><td>2.4087</td><td>3.5827</td></tr><tr><td rowspan="4">f4</td><td></td><td></td><td></td><td></td><td>1.4832e+03</td></tr><tr><td>PSO MBO</td><td>10379</td><td>16015</td><td>1.3538e+04</td><td></td></tr><tr><td></td><td>0</td><td>72991</td><td>2.5781e+04</td><td>2.7767e+04</td></tr><tr><td>GCMBO</td><td>0</td><td>2206</td><td>203.7667</td><td>541.4205</td></tr><tr><td rowspan="4">f5</td><td>CSMBO</td><td>0</td><td>7</td><td>0.2333</td><td>1.2780</td></tr><tr><td>PSO</td><td>2.3207e+06</td><td>2.3380e+07</td><td>9.0459e+06</td><td>5.2705e+06</td></tr><tr><td>MBO</td><td>1.2839e-11</td><td>5.8334e+08</td><td>1.3545e+08</td><td>1.9159e+08</td></tr><tr><td>GCMBO</td><td>2.5213e-16</td><td>8.2390e+06</td><td>5.6040e+05</td><td>2.0417e+06</td></tr><tr><td rowspan="4">f6</td><td>CSMBO PSO</td><td>6.9181e-12</td><td>11.6346 8.1079e+07</td><td>0.8624 4.2706e+07</td><td>2.3041 1.9612e+07</td></tr><tr><td>MBO</td><td>7.5324e+06</td><td>1.0516e+09</td><td></td><td></td></tr><tr><td></td><td>9.8230e-10</td><td></td><td>1.4534e+08</td><td>2.6536e+08</td></tr><tr><td>GCMBO CSMBO</td><td>4.7593e-14</td><td>5.2262e+07 1.2936</td><td>3.4594e+06 0.0914</td><td>1.1075e+07 0.2833</td></tr><tr><td rowspan="4">f</td><td>PSO</td><td>8.1086e-11 412.4324</td><td>1.5276e+03</td><td>963.1479</td><td>230.7740</td></tr><tr><td>MBO</td><td>3.9119e-04</td><td>9.5470e+03</td><td>1.8755e+03</td><td>3.1023e+03</td></tr><tr><td>GCMBO</td><td></td><td>626.1261</td><td>98.7457</td><td>142.3047</td></tr><tr><td>CSMBO</td><td>1.4106e-10 1.7249e-05</td><td>140.8104</td><td>52.2129</td><td>38.1776</td></tr><tr><td rowspan="4">f</td><td>PSO</td><td>91.0693</td><td>142.6368</td><td>114.4050</td><td>12.9686</td></tr><tr><td>MBO</td><td>1.0000</td><td>595.4902</td><td>148.0689</td><td>176.6548</td></tr><tr><td>GCMBO</td><td>1.0000</td><td>130.8612</td><td>42.5119</td><td>45.7053</td></tr><tr><td>CSMBO</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>2.5766e-11</td></tr></table></body></html>

以上在不同维度基准函数上的实验结果证明了CSMBO算法的有效性与可行性，不仅在不同维度单峰函数上有较好的收敛精度，而且在不同维度多峰函数上显示了更好的全局搜索能力，以相对明显的优势优于其他三种对比算法。

# 3.3收敛性分析

为了更直观地看出CSMBO算法的收敛速度、局部搜索能力和全局搜索能力，本文给出了四种算法在求解50维测试函数时的收敛曲线图，如图2所示。

从图2可以看出，CSMBO算法在对八个测试函数进行优化时的收敛速度均优于其他三种对比算法。特别是在 $f _ { 3 }$ 、f6、f和f&上，CSMBO算法的收敛速度大幅度优于对比算法。

总之，从整体情况来看，CSMBO算法在八个测试函数上的收敛性能都是最优的，再一次证明CSMBO算法的改进策略是有效的。其原因是由于CSMBO算法融入了交叉操作，增强了种群的多样性，提升了算法的全局勘探能力；而且在调整算子中加入了共享操作，种群中更优个体的信息得到有效利用，使得CSMBO算法的收敛速度得到了很大幅度的提升。

综上所述，CSMBO算法不管在单模态函数上，还是在多模态函数上，与其他三种算法相比具有更优秀的优化性能，所以本文CSMBO算法的改进是有效和可行的。

表3四种算法在30维函数上的测试结果  
表4四种算法在50维函数上的测试结果  
Table 4 Results of four algorithms on 5O-dimensional functions   

<html><body><table><tr><td>函数</td><td>算法</td><td>最优值</td><td>最差值</td><td>平均值</td><td>标准差</td></tr><tr><td rowspan="4">f</td><td>PSO</td><td>21.1397</td><td>57.5429</td><td>39.4603</td><td>8.8743</td></tr><tr><td>MBO</td><td>0.0034</td><td>415.5476</td><td>153.3220</td><td>142.7727</td></tr><tr><td>GCMBO</td><td>1.9171e-07</td><td>133.2460</td><td>19.750</td><td>29.8177</td></tr><tr><td>CSMBO</td><td>1.8955e-17</td><td>0.6991</td><td>0.0437</td><td>0.1377</td></tr><tr><td rowspan="4">f</td><td>PSO</td><td>2.4468e+04</td><td>4.7567e+04</td><td>3.6691e+04</td><td>5.6002e+03</td></tr><tr><td>MBO</td><td>0.0010</td><td>1.6716e+05</td><td>7.1776e+04</td><td>5.1240e+04</td></tr><tr><td>GCMBO</td><td>2.3034e+03</td><td>7.4799e+04</td><td>2.8123e+04</td><td>1.7575e+04</td></tr><tr><td>CSMBO</td><td>1.2244e-07</td><td>5.7843e+04</td><td>5.2787e+03</td><td>1.5786e+04</td></tr><tr><td rowspan="4">f</td><td>PSO</td><td>56.5356</td><td>94.9000</td><td>87.4604</td><td>11.0036</td></tr><tr><td>MBO</td><td>0.0071</td><td>90.5485</td><td>35.3305</td><td>26.7642</td></tr><tr><td>GCMBO</td><td>0.0299</td><td>85.3000</td><td>33.9794</td><td>21.5405</td></tr><tr><td>CSMBO</td><td>5.2411e-05</td><td>15.5230</td><td>4.1900</td><td>4.9262</td></tr><tr><td rowspan="4">f4</td><td></td><td></td><td>33563</td><td>3.0441e+04</td><td>1.9358e+03</td></tr><tr><td>PSO MBO</td><td>26696</td><td></td><td>5.1815e+04</td><td>5.1859e+04</td></tr><tr><td></td><td>0</td><td>132209</td><td></td><td></td></tr><tr><td>GCMBO</td><td>0</td><td>12346</td><td>1696</td><td>2.9548e+03</td></tr><tr><td rowspan="4">fs</td><td>CSMBO</td><td>0</td><td>19</td><td>0.8333</td><td>3.6016 1.8547e+07</td></tr><tr><td>PSO</td><td>1.9350e+07</td><td>8.9184e+07</td><td>4.9437e+07</td><td></td></tr><tr><td>MBO</td><td>3.4589e-11</td><td>1.1141e+09</td><td>2.4720e+08</td><td>4.0804e+08</td></tr><tr><td>GCMBO CSMBO</td><td>2.0184e-17</td><td>5.4740e+07</td><td>3.2179e+06</td><td>1.0925e+07</td></tr><tr><td rowspan="4">f6</td><td>PSO</td><td>1.0028e-11 8.6540e+07</td><td>41.5839 2.4986e+08</td><td>4.7557 1.5685e+08</td><td>9.4187 4.5239e+07</td></tr><tr><td>MBO</td><td>6.5719e-10</td><td>1.9497e+09</td><td>3.6131e+08</td><td>6.4416e+08</td></tr><tr><td>GCMBO</td><td></td><td></td><td></td><td></td></tr><tr><td>CSMBO</td><td>9.8724e-16 2.3708e-10</td><td>1.4513e+08 194.3978</td><td>1.0977e+07 10.7529</td><td>3.1121e+07 37.6554</td></tr><tr><td rowspan="4">f</td><td>PSO</td><td>1.3892e+03</td><td>3.5147e+03</td><td>2.4754e+03</td><td>478.7173</td></tr><tr><td>MBO</td><td>1.3455e-04</td><td>1.8360e+04</td><td>5.9326e+03</td><td>6.2480e+03</td></tr><tr><td>GCMBO</td><td>3.3925e-09</td><td>1.4881e+03</td><td>243.2459</td><td>353.8553</td></tr><tr><td>CSMBO</td><td>1.4367e-05</td><td>265.6663</td><td>65.0644</td><td>58.8563</td></tr><tr><td rowspan="4">f8</td><td>PSO</td><td>200.9274</td><td>306.9407</td><td>266.5297</td><td>26.2755</td></tr><tr><td>MBO</td><td>1.2936</td><td>1.0722e+03</td><td>419.0091</td><td>381.3554</td></tr><tr><td>GCMBO</td><td>1.0000</td><td>312.7389</td><td>96.2010</td><td>97.1711</td></tr><tr><td>CSMBO</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>2.2857e-11</td></tr></table></body></html>

# 3.4CSMBO 算法的复杂度分析

在软硬件运行环境相同的前提下，优化算法的复杂度计算主要由目标函数的复杂度和算法自身流程的复杂度两部分组成。本文在对比实验中，设置所有算法（PSO、MBO、GCMBO和本文的CSMBO算法）具有相同的种群数量和最大迭代次数，使得它们的最大函数评价次数（MNFE）[32]近似相等，故CSMBO算法的复杂度计算主要取决于自身流程的复杂程度。假设CSMBO算法的最大迭代次数为 $T _ { \ast }$ ，种群规模为 $N _ { \astrosun }$ ，子群1为 $N 1$ ，子群2为 $N \mathrm { ~ - ~ } N 1$ ，维度为 $D$ 。由CSMBO算法流程（图1）可知，该算法的时间复杂度主要由每次迭代循环决定，详细步骤分析如下：a)需要计算蝴蝶的适应度值，时间复杂度为 $O ( N ) ; { \mathsf { b } } )$ 排序，时间复杂度是 $O ( N ^ { 2 } )$ c)分成两个子群，时间复杂度是 $O ( N ) ; { \mathrm { d } } )$ 运行交叉迁移算子，有两个内循环，时间复杂度为 $O ( N 1 \times D )$ ，且在共享调整算子中，也存在两个内循环，时间复杂度为 $O ( ( N - N 1 ) \times D )$ 。所以，CSMBO算法的总时间复杂度是 $T ( n ) = O ( f ( n ) ) = O ( T \times$ $( N + N ^ { 2 } + N + ( N 1 \times D ) + ( ( N - N 1 ) \times D ) ) ) = O ( T \times ( 2 N + N ^ { 2 } +$ $N \times D ) ) = O ( T \times N ^ { 2 } )$ 。在CSMBO算法中，由于可变的储存空间受到种群规模 $N$ 和变量维度 $D$ 的影响，则计算其空间复杂度为 $S ( n ) = O ( f ( n ) ) = O ( N \times D ) ,$ 0

![](images/b546427a8f6a9fe0c4c79a8dcf136c206a2f370a3527a34655a548ef06548adb.jpg)  
图2四种算法在八个基准函数上的收敛曲线

# 4 结束语

Fig.2Convergence curves offour algorithms on eight benchmark functions 搜索能力。

本文针对MBO算法易陷入局部最优和收敛速度慢等问题，提出了一种基于交叉迁移和共享调整的改进MBO（CSMBO）算法。首先，将MBO的迁移算子改为基于维度垂直交叉操作的交叉迁移算子，克服了原始迁移算子方式单一的缺陷，而且增加了种群的多样性，这在一定程度上避免了MBO算法陷入局部最优；其次，用具有信息分享功能的共享调整算子替换原始调整算子，加快了MBO算法的收敛速度；最后，将MBO算法中的精英保留策略改为贪婪选择策略，减少了精英参数的设置。在一组多维度的基准函数上的实验证明，与其他三种对比算法相比，本文提出的CSMBO算法在解决函数优化问题时具有更好的全局探索能力和局部

# 参考文献：

[1]盛四清，陈玉良，张晶晶．基于差分进化人工蜂群算法的光伏最大 功率跟踪策略研究[J]．电力系统保护与控制，2018,46(11)：23-29. (Sheng Siqing,Chen Yuliang,Zhang Jingjing.Research on maximum power point tracking strategy based on differential evolution artificial bee colony algorithm of photovoltaic system [J].Power System Protection and Control,2018,46 (11): 23-29.)   
[2]Rakhshani H,Rahati A.Snap-drift cuckoo search:a novel cuckoo search optimization algorithm [J].Applied Soft Computing,2O17,52 (3): 771-794.   
[3]康健，靳斌，段秀娟，等．基于贝叶斯一粒子群算法的微电网优化运 行[J].电力系统保护与控制，2018,46(12):32-41.(Kang Jian,Jin Bin,Duan Xiujuan,et al. Optimal operation of microgrid based on Bayesian-PSO algorithm [J].Power System Protection and Control, 2018, 46 (12): 32-41. )   
[4] 江岳春，何钟南，刘爱玲．基于改进 BBO 算法的风电一水电互补优 化运行策略[J]．电力系统保护与控制，2018,46 (10):39-47.(Jiang Yuechun，He Zhongnan，Liu Ailing. A complementary optimal operation strategy of wind power-hydropower based on improved biogeography-based optimization algorithm[J]. PowerSystem Protection and Control,2018,46 (10): 39-47.)   
[5]王静，李维德．基于CEEMD 和GWO的超短期风速预测[J].电力 系统保护与控制，2018，46(9):69-74.(Wang Jing，Li Weide. Ultra-short-term forecasting of wind speed based on CEEMD and GWO [J]. Power System Protection and Control,2018,46(9): 69-74.)   
[6]Wang Feng,Zhang Heng,Li Kangshun,et al.A hybrid particle swarm optimization algorithm using adaptive learning strategy [J]. Information Sciences,2018,436: 162-177.   
[7] 刘沛，高岳林，郭伟．一种基于改进的磷虾群和粒子群的混合算法 [J]．河南师范大学学报：自然科学版,2017,45(2):119-124.(Liu Pei, Gao Yuelin,Guo Wei.A hybrid algorithm based on improved krill herd andparticle swarm optimization [J]. Journal of Henan Normal University: Natural Science Edition,2017,45 (2):119-124.)   
[8]袁晗，徐春梅，杨平，等．一种基于子群变异的粒子群优化算法[J]. 计算机应用研究,2017,34(4):1076-1079.(Yuan Han,Xu Chunmei, Yang Ping,et al. New particle swarm optimization based on subswarm mutation [J].Application Research of Computers，2017，34(4): 1076-1079. )   
[9]Kennedy J. Particle swarm optimization [M]// Encyclopedia of Machine Learning. Boston, MA: Springer, 2011: 760-766.   
[10]史旭栋，高岳林，韩俊茹．基于模糊推理的粒子群优化算法[J]．河 南师范大学学报：自然科学版,2017,45(2):108-118.(Shi Xudong, Gao Yuelin,Han Junrun. Particle swarm optimization algorithm based on fuzzy reason [J]. Journal of Henan Normal University: Natural Science Edition,2017,45 (2): 108-118.)   
[11]张新明，王霞，涂强，等．融合榜样学习和反向学习的粒子群优化算 法[J].河南师范大学学报：自然科学版,2017,45(6):91-99. (Zhang Xinming，Wang Xia,Tu Qiang，et al. Particle swarm optimization algorithm based on combining example learning and opposition learning [J]. Journal of Henan Normal University: Natural Science Edition,2017,45 (6): 91-99.)   
[12]张俊武，王德林，陈斌，等．基于PSO-GSA算法的含DFIG互联系统 AGC 优化控制研究[J].电力系统保护与控制,2018,46(13):48-54. (Zhang Junwu,Wang Delin,Chen Bin,et al.Research on PSO-GSA algorithm optimization for interconnected AGC system including DFIG wind turbines [J].Power System Protection and Control, 2018,46 (13): 48-54.)   
[13]刘小垒，张小松，蒋义琪，等．基于分布式烟花算法的 WSN 布局优 化方法[J]．计算机应用研究，2018,35(2):569-572.(Liu Xiaolei, Zhang Xiaosong, Jiang Yiqi,et al. Deployment optimization of wireless sensornetwork based on parallelized fireworksalgorithm [J]. Application Research of Computers,2018,35 (2): 569-572.)   
[14] Zhang Xinming,Kang Qiang,Tu Qiang,et al.Efficient and merged biogeography-based optimization algorithm for global optimization problems [J/OL]. (2018).https://doi.org/10.1007/s00500-018-3113-1.   
[15] Wang Gaige,Deb S,Cui Zhihua.Monarch butterfly optimization [C]// Proc of Neural Computing and Applications. 2015: 1-20.   
[16] 陈小雪，尉永清，任敏，等．基于萤火虫优化的加权 K-means 算法 [J].计算机应用研究，2018，35(2):466-470.(Chen Xiaoxue，Wei Yongqing，Ren Min,et al.Weighted K-means clustering algorithm based on firefly algorithm[J].Application Research of Computers, 2018,35 (2):466-470.)   
[17]胡博，王昕，郑益慧，等．基于萤火虫优化算法的分布式发电设备容 量分配及配电网孤岛划分[J]．电力系统保护与控制，2018,46(13): 21-26. (Hu Bo,Wang Xin,Zheng Yihui,et al. Calculation of isolated island partition and distributed generator capacity based on firefly algorithm [J].Power System Protection and Control,2018,46 (13): 21-26.)   
[18]许喆，潘金生，樊淑娴，等．基于改进萤火虫算法的含DG配电网重 构方法[J].电力系统保护与控制,2018,46(14):26-32.(Xu Zhe,Pan Jinsheng,Fan Shuxian,et al.A distribution network reconfiguration method with distributed generation based on improved firefly algorithm [J].Power System Protection and Control,2018,46 (14): 26-32.)   
[19]Feng Yanhong，Wang Gaige,Deb S，et al. Solving O-1 knapsack problem by a novel binary monarch buttrfly optimization [J].Neural Computing and Applications,2017,28 (7): 1619-1634.   
[20] Yadav V, Ghoshal S P. Optimal power flow for IEEE 30 and 118-bus systems using monarch butterfly optimization [C]// Proc of IEEE International Conference on Technologiesfor Smart-City Energy Security and Power. Piscataway,NJ: IEEE Press,2018:1-6.   
[21] Faris H, Aljarah I, Mirjalili S.Improved monarch butterflyoptimization for unconstrained global search and neural network training [J]. Applied Intelligence,2018,48 (2): 445-464.   
[22] Chen Shifeng,Chen Rong,Gao Jian.A monarch butterfly optimization for the dynamic vehicle routing problem [J].Algorithms,2O17,10 (3): 1-19.   
[23] Devikanniga D,Joshua S R R.Clasification of osteoporosis by artificial neural network based on monarch butterfly optimization algorithm [J].Healthcare Technology Letters,2018,5 (2):70-75.   
[24] Wang Gaige，Zhao Xinchao,Deb S．A novel monarch butterfly optimization with greedy strategy and self-adaptive [C]// Proc of the 2nd IEEE International Conference on Soft Computing and Machine Intelligence.Piscataway,NJ: IEEE Press,2O15: 45-50.   
[25] Feng Yanhong, Yang Juan,Wu Congcong,et al. Solving O-1 knapsack problems by chaotic monarch butterfly optimization algorithm with Gaussian mutation [J]. Memetic Computing,2018,10 (2): 135-150.   
[26]蒙丽萍，王勇，黄华娟．采用动态分割种群策略的改进 MBO[J].计 算机工程与应用,2017,53 (18):149-156.(Meng Liping,Wang Yong, Huang Huajuan. Improved monarch butterfly optimization by using strategy of dynamic-dividing population [J]. Computer Engineering and Applications,2017,53(18): 149-156.)   
[27] Feng Yanhong,Wang Gaige,Li Wenbin,et al.Multi-strategy monarch butterfly optimization algorithm for discounted{O-1}knapsack problem [J]. Neural Computing and Applications,2017,30(10): 3019-3036.   
[28] Feng Yanhong，Wang Gaige,Dong Junyu,et al. Opposition-based learning monarch butterfly optimization with Gaussian perturbation for large-scale O-1 knapsack problem [J]. Computersand Electrical Engineering,2018,67: 454-468.   
[29] Hu Hui,Cai Zhaoquan,Hu Song,et al. Improving monarch butterfly optimization algorithm with self-adaptive population [J].Algorithms, 2018,11 (5): Article ID: 71.   
[30] Ghanem W AH M,Jantan A.Hybridizing artificial bee colony with monarch buterfly optimization for numerical optimization problems [J].

Neural Computing and Applications,2018,30(1):163-181.

[31] Ghetas M,Yong C H,Sumari P.Harmony-based monarch butterfly optimization algorithm [C]//Proc of IEEE International Conference on Control System,Computing and Engineering.Piscataway,NJ:IEEE Press,2015:156-161.

[32]张新明，康强，王霞，等．差分迁移和趋优变异的生物地理学优化算 法[J]．小型微型计算机系统，2018，39(6)：1168-1177.(Zhang Xinming，Kang Qiang，Wang Xia，etal. Biogeography-based optimization with differential migration and global-best mutation [J]. Journal of Chinese Computer Systems,2018,39 (6): 1168-1177.)