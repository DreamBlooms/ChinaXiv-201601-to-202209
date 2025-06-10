# 根生群优化算法

吴正军1，冯翔1²，虞慧群1

(1．华东理工大学 信息科学与工程学院，上海 200237;2.上海交通大学 智慧城市协同创新中心，上海 200240)

摘要：针对全局优化问题，基于一类支持向量数据描述（SVDD)和已有的根系生长算法提出一种新的智能优化算法—根生群优化算法，将根系划分为主根群体和侧根群体。基于SVDD描述主根群体的生长行为，将土壤中养分浓度最高的位置作为全局优化的目标，构建了根系生长模型；分析了RGSO 的数学模型，从理论上证明了RGSO 的收敛性。在实验中，与当前最先进的其他三个算法进行综合比较，并观察了不同参数对优化效果的影响。实验结果验证了RGSO 的收敛性和有效性，表明RGSO是一种解决全局优化问题的有效算法。

关键词：根生算法；分群机制；SVDD；优化问题 中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2017.06.0656

# Root growth swarm optimization algorithm

Wu Zhengjun1, Feng Xiang1, ², Yu Huiqun1 (1.Schoolof InformationScience&Engineeing,EastChina UniversityofScience&Technology,Shanghai20237China;2. Smart City Collaborative Innovation Center,Shanghai JiaoTong University,Shanghai 200240, China)

Abstract: Aimingat the global optimization problem,this paper proposed anew intelligent algorithmcalled RGSO,based on SVDDandtherootalgorithmexisted.Therootsystem differentiatedintothetaprootandthelateralroot group.Inspired bythis growth behavior,this paper describedthe growth behaviorofthe taproot tipsbased on SVDD.The algorithmconstructed the root growth model,andused thepointof thehighestconcentrationofnutrientsinthesoilasthetargetof globaloptimization. This paper analyzed the mathematicalmodelofRGSO,and proved itsconvergencetheoretically.Inthe experiment,this paper compared RGSO with the other three advanced algorithms,and tested theoptimization effect with diferent parameters.The resultoftheexperimentverifiedtheconvergenceandeffectivenessofRGSO,anditidicates thatRGSOisanefectivealgorithm to solve global optimization problem.

Key Words: root algorithm; clustering mechanism; SVDD; optimization problem

# 0 引言

自然生物现象遵循着某些内在规律[1。几个世纪以来，科学家们试图识别和记录自然现象背后的物理定律[2]。受各种自然生物现象的启发，计算机工作者们以自然界生物的行为[3]为基础，抽取出用于求解大规模复杂问题的计算技术和方法。最优化问题[4是一个极其古老的课题。目前，优化问题在工程技术、经济管理、交通运输、系统控制、人工智能、模式识别等领域得到了成功的推广和应用。

最优化问题的数学描述如下：

求解

$$
\operatorname* { m i n } f ( x ) , s . t . \quad g ( x ) \geq 0 ;
$$

其中： $x$ 为 $n$ 维向量， $f$ 为目标函数， $h$ 和 $g$ 为约束条件。

生物智能算法是一种新兴的演化计算技术，其研究对象包括生物自身的行为[51以及生物所处的自然环境，目的是找出其中的数学规律。智能优化算法要解决的一般是最优化问题。传统的智能算法都具有自适应的特点，如遗传算法[6]、免疫算法[7]、粒子群算法[8]等。

粒子群优化算法(PSO)是一种源于对鸟群捕食行为的研究而发明的进化计算技术，最先由Barnhart 博士和Kennedy 博士提出[9]。2014年，Zhang等人[10]提出了原始的根生算法，模拟了植物根系的生长，将寻找土壤中养分浓度最高的点作为寻优的目标。支持向量数据描述(SVDD)是用于一类分类问题的分类技术。2013年，Niazmardi等人[1]提出了一个改进的聚类框架

基金项目：国家自然科学基金资助项目（61472139，61462073）；上海市经信委“信息化发展”专项资金资助项目（201602008）；上海交通大学智慧城市协同创新中心开放基金资助项目

作为在聚类时缺乏足够高的高品质的训练数据的解决方案。

一些基于传统算法的改进算法也被不断提出。文献[12]基于前馈神经网络的反向传播学习，用于优化FPGA芯片。文献[13]提出带干扰抵消的协同传输的蚁群算法。文献[14]基于多目标的模拟退火和遗传算法，用于优化三相高温超导变压器。文献[15]使用精英非支配排序遗传算法解决多目标路径规划问题。文献[16]提出了一个能够在动态环境中解决时变非线性问题的人工免疫算法。文献[17]通过强化单个粒子的搜索能力提出了一个自主学习粒子群优化算法。文献[18]对粒子群算法的邻居结构进行了改进，从而提出了一个具有综合学习能力的粒子群优化算法。近年来，新提出的智能算法不断地涌现。文献[19]基于改进的社会蜘蛛优化算法应用于电磁优化，文献[20]提出绒胞菌算法用于解决斯坦纳树问题，文献[21]提出蚊子追踪算法等。

基于以上相关工作，本文所设计根生优化模型，规定了算法的自适应学习方式。通过自适应学习的特性，算法达到了全局优化的目的。大多数自然启发算法都有着一定程度的有效性，但是也有着相同的缺点，即收敛速度较慢，容易陷入早熟和局部最优。本文所提出的基于SVDD的根生群优化算法，即是基于已提出的根生算法，针对上述的缺点，对原算法的改进。RGSO刻画了根系群体的生长方式以及个体间的相互作用，与其他算法相比，具有更高的自适应和自我学习能力。因此RGSO在求解大规模复杂问题时，具有更高的有效性。

# 1 根系群体和生长行为

# 1.1根系群体

植物根系是由一系列的根尖构成，根尖是根中生命活动最活跃的部分，也是根的生长、延长及吸收水分的主要部分，因此根的生长依赖于根尖部位的生长。根尖的生长过程与其生长环境息息相关，最主要的影响因素即是土壤中养分的浓度。事实证明，植物的根尖总是向着土壤中养分浓度最高的地方生长，如图1所示。

# 1.2根系初始状态

植物的根系是由一粒种子发育而来，即根系群体在初始状态下根尖的个体数为1。

# 1.3主根子群和侧根子群

在RGSO中，根生群体被划分为两个子群体，即主根子群和侧根子群。以下是两个子群的定义。

定义1主根子群。胚根细胞分裂和伸长向下垂直生长的根,是植物体最早出现的根,也称直根或初生根。大多数裸子植物和双子叶植物主根继续生长，明显而发达。植物主要依靠主根的不断向下生长，寻找土壤中养分浓度最高的位置。

定义2侧根子群。土壤中的主根不断地生长，长到一定的程度便伸出侧支，形成庞大的根系。形成侧支的主要动因是为了更大范围地搜索土壤中浓度较高的位置，一旦发现养分浓度更高的位置，就会将这一情况反馈给根系，整个根系也随之

向着这个更好的位置生长。

由于种群的多样性，每个根尖所处的位置不同，其相应的适应度也不相同。依据种群中根尖的适应度，根尖的生长策略分为：主根根尖生长策略和侧根根尖生长策略。划分主根与侧根的依据是个体适应度的大小，计算出所有个体的适应度平均值，个体适应度高于该平均值的根尖，将被作为主根根尖，个体适应度低于该平均值的生长点，将被作为侧根生长点。

![](images/67b01922638b7ad4f60c857ae3e548755df1ebf8f46a269803469437520f0d53.jpg)  
图1植物根系生长形态

# 1.4生长素因子

植物根系在正常的生长状态下，会产生一种生长激素以便促进根尖的生长。生长素的大小反映了当前根尖在当前群体中的适应值水平。当前根尖所处位置的适应值相较于其他个体越优秀（越小），则生长素因子相较于其他个体越大。

# 1.5土壤养分区域分布模型

实际上，土壤中养分的分布不是均匀的，总体上呈现出区域集中的分布。一般的，如果土壤中多个位置的养分浓度较高，那么即认为由这多个位置所确定的空间区域养分浓度较高。为了确定这一区域的位置，引入一类支持向量数据描述（SVDD)，建立土壤向量空间模型，即建立一个尽可能小的向量空间球，将待定区域的多个向量包裹，得到其球心位置，以该球心表征这一区域。

# 1.6生长行为

根系的生长行为主要包括根尖的分支和生长，现将根系的生长行为作以下的限定：

假设1根尖的生长方向主要依靠自身对土壤中养分浓度的感知。

假设2根尖在生长的过程中，如果群体根尖总数未达到阈值，则主根会进行分支。

假设3不同的根尖个体之间的行为会相互影响，优秀个体能够指引落后个体的生长。

假设4当根尖总数达到一定的阈值后，淘汰一些适应度较差的根尖。

# 1.6.1主根的分支

根系由一粒种子（一个根尖）发育而来，根系的生长即为群体中根尖数目的不断扩充。在根系的生长过程中，优秀的个体会在其生长空间周围进行分支，根尖的分支会造成群体根尖总数的增加。在本文中，限定只有主根根尖个体才能进行分支，且每次分支的数目恒定。

# 1.6.2主根的生长

主根根尖的生长较慢，受两个因素影响：

a)角度因素。由于主根总是向着土壤中养分浓度较高的位置生长，因此，角度的朝向是当前养分浓度较高的区域的位置，该区域是由所有优于当前个体的根尖所确定的空间构成，该空间可以利用SVDD确定，并且求出其球心位置，则当前根尖应该朝着该球心生长。

b)长度因素。该长度由种群所有个体位置的均值点到当前个体位置的距离和当前个体的生长素因子决定。

# 1.6.3侧根的生长

侧根根尖的生长较快，一般认为，侧根根尖的生长较散乱，生长角度与方向都较为随机。

# 1.7淘汰机制

事实上，根系群体的根尖数目是有上限的，这个上限，也被称作种群个体数目的平衡点。当总群个体数目超过这个平衡点后，种群会淘汰那些落后的个体，以达到整体个数的平衡。淘汰的准则是剔除那些适应值最差的个体，直到整体个数重新达到平衡点。

# 2 根生群优化数学模型和算法

根据根系的形成过程、根系的分群过程以及根尖的分支和生长行为，得到流程图（图2）。

图2根生群优化生长流程  
![](images/0334bb92eb2e20630b2e9d9f312d1cbd79011e0120d02275515ba2a45fe8d27a.jpg)  
输出：新产生的根尖位置

# 2.1根系群体的数学模型

定义3根系群体的初始状态是一颗种子，即算法在初始状态，只有一个根尖。这个根尖的位置是在可行域中随机生成的，整个根系的生成都依赖于这个根尖。

$$
x _ { 0 } = l + \lambda \cdot ( u - l )
$$

其中 $\mathbf { \dot { \sigma } } _ { : u }$ 和 $\iota$ 分别表示 $n$ 维的可行域上下界向量， $\lambda$ 是一个[0,1]

的随机变量。

根据根系子群的划分，根系群体被分为主根子群和侧根子群。

定义4对于任意的根尖个体 ${ \pmb R } _ { i }$ ， $R _ { i } \epsilon S$ ， $\pmb { S } = \{ \pmb { M } , \pmb { L } \}$ ，其中， $s$ 为根尖群体集合， $\pmb { M }$ 为主根子群集合， $\textbf { \em L }$ 为侧根子群集合。

# 算法1根系子群分类

输入：适应度函数 $\_ f { \ i } t ( { \pmb x } )$ 以及各参数  
1:计算所有根尖的适应度 $f i t ( { \pmb x } _ { i } )$ （20  
2:计算适应度平均值 $a \nu e r = { \sum } _ { i = 1 } ^ { n } f i t ( x _ { i } )$   
3:for each root tips  
4: iffit(xi)≥aver  
5: 该根尖属于主根  
6: else  
7: 该根尖属于侧根  
8: end if  
9:end for  
输出：根尖个体分类

# 2.2群生长算法

# 2.2.1新的根尖位置

群生长包括新的根尖位置的形成，根尖分支以及根尖的生长。

定义5新的根尖的形成位置与原根尖位置相关，新生长点的形成位置定义如下：

$$
x _ { n e w } = x _ { o l d } + \Delta x
$$

其中 $: \boldsymbol { x } _ { o l d }$ 表示旧的根尖的位置， ${ \Delta } x$ 是一个服从 $N ( 0 , 1 )$ 的正态分布变量。

2.2.2主根分支

定义6只有主根才进行分支，侧根不进行分支。

# 算法2.根尖分支算法

输人：根尖个体的位置

1:for each root tip Xi  
2: if Xi∈M  
3: 根据式(2)产生新的根尖位置  
4: end if  
3:end for

2.2.3基于SVDD的土壤区域分布

定义7优于当前根尖的所有根尖个体所确定的区域由包裹这些个体向量的空间超球确定，该超球的球心设为 $\mathbf { \delta } _ { o }$ ，半径为 $R$ 。

$$
\begin{array} { c } { { f ( R , O , \xi _ { i } ) = R ^ { 2 } + C \cdot \displaystyle \sum _ { i } \xi _ { i } } } \\ { { ( x _ { i } - O ) ^ { T } ( x _ { i } - O ) \leq R ^ { 2 } + \xi _ { i } } } \end{array}
$$

其中 $\mathbf { \sigma } _ { : x _ { i } \in A , \ A }$ 是所有优于当前个体的根尖集合， $\mathbf { \delta } _ { o }$ 是超球的球心， $R$ 是超球的半径， $\xi _ { i }$ 是松弛变量， $C$ 是惩罚因子。基于SVDD,

可以根据 $\textbf {  { A } }$ 计算出 $\mathbf { \delta } _ { o }$ 和 $R$ 。

# 2.2.4主根和侧根生长策略

在RGSO中，根系群体分为主根子群和侧根子群，两种子群分别拥有不同的生长方式。

对于主根子群，其生长较为缓慢，每次生长都要将根系群体中较为优秀的个体的信息作为参考，调整自身的生长幅度。较为优秀的个体，即为适应值小于当前个体的所有其他个体。对于侧根子群，其生长较为迅速，侧根的生长依照随机游走的原则。

定义8主根个体每次生长的角度由其他优于当前个体的根尖决定。

$$
\theta = \frac { O _ { i } - x _ { i } } { \left| O _ { i } - x _ { i } \right| }
$$

其中 $\mathbf { \sigma } _ { i }$ 是所有优于 $\mathbf { \lambda } _ { \pmb { x } _ { i } }$ 的个体所确定的超球球心。

定义9生长素反映了根尖个体当前的适应值水平，适应值越小，生长素值越大。

$$
E = \exp ( - \frac { f ( x _ { i } ) } { \displaystyle \sum _ { j \in S } f ( x _ { j } ) } )
$$

其中： $s$ 表示当前群体的所有根尖个体集合。

定义10主根根尖每次生长长度 $\gamma$ 与当前的生长素值相关，生长素值越大，则需要生长的长度越小，反之，则越大。

$$
\gamma = ( 1 - E ) \cdot r a n d \cdot \left| { \frac { 1 } { n } } \cdot \sum _ { j \in S } x _ { j } - x _ { i } \right|
$$

其中， $n$ 是当前个体总数， $E$ 是生长素因子，rand 是一个[0,1]的随机数。

定义11缩放算子 $\omega$ 与当前根尖的适应值相关，适应值越小，说明当前根尖越优秀，则保留本来位置的可能越大。

$$
\omega = { \frac { \displaystyle Y _ { f ( x _ { i } ) } } { \displaystyle \sum _ { j \in S } \nu _ { f ( x _ { j } ) } } }
$$

定义12主根根尖的位置更新，定义如下：

$$
x _ { i } ( t + 1 ) = \omega \cdot x _ { i } ( t ) + \alpha \cdot \theta \cdot \gamma
$$

其中， ${ \bf \mathcal { x } } _ { i } ( t )$ 表示第 $i$ 个主根根尖在 $t$ 时刻的位置， $\alpha$ 是控制参数，取值为[0,1]， $\pmb \theta$ 表示生长角度， $\gamma$ 表示生长的长度。

定义13侧根根尖的位置更新

$$
x _ { i } ( t + 1 ) = r a n d \cdot \beta \cdot x _ { i } ( t )
$$

其中， ${ \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { \mathbf { } } _ { } { } \mathbf { } _ { } { } { \mathbf { } } _ { } { } _ { } { } \mathbf { } _ { } { } { \mathbf { } } _ { } { } _ { } { } \mathbf { } _ { } { } \mathbf { } _ { } { } { \mathbf { } } _ { } { } \mathbf { } _ { } { } \mathbf { }  _ { } { } _ { } { } \mathbf { } _ { } { } _ { } { } \mathbf { } _ { } { } \mathbf { }  _ { } { } _ { } { } \mathbf { } _ { } { } _ { } { } \mathbf { } _ { } { } \mathbf { } _ { }  _ { } { } _ { } { } \mathbf { } _ { } { } _ { } { } \mathbf { } _ { } { } _ { } \mathbf { } _ { } { } \mathbf { } _ { }  _ { } { } _ { } { } _ { } \mathbf { } _ { } { } _ { } \mathbf { } _ { } _ { } { } _ { } \mathbf { } _ { }  _ { } _ { } { } _ { } _ { } \mathbf { } _ { } _ { } { } _ { } _ { } _ { } \mathbf { } _ { } _ { } _ { }  _ { } _ { } _ { } _ { } _ { } _ { } _ { } _ { } _ { } _ { } _ { } _ { } _ { } _ { } _ { } _ { } _ { } _  _ { } _ { } _ { } _ { } _ { } _ { } _ _ { } _ { } _ { } _ { } _ { } _ _ { } _ { } _ { } _ \mathbf { } _ _ { } _ { } _  _ { } _ { _ } _ { } _ { } _ _ { } _ { } _ _ { } _ { } _ _ { } _ { } _ _ { } _ { } _ _ { } _ \mathbf { } _ _ { } _  _ { _ } _ { } _ _ { } _ { } _ _ { } _ _ { } _ \mathbf { } _ _ { } _ \mathbf \mathbf _ { } _ { } _ _ \mathbf { } _ \mathbf _ { } _ \mathbf \mathbf { } _ _  _ { \mathbf \mathbf _ { } _ } _ { \mathbf \mathbf _ } _ { _ } _ { } _$ 表示第 $i$ 个侧根根尖在 $t$ 时刻的位置，采用随机游走的生长策略， $\beta$ 是控制参数，rand是一个[0,1]的随机数。

# 算法3.根尖生长算法

输入：根尖个体的位置、类别以及各参数

1: for each root tip

2: if $\pmb { x } _ { i }$ EM  
3: 根据式(8)计算主根位置  
4: else  
5: 根据式(9)计算侧根位置

6:end if

7:end for输出：更新后的根尖位置

种群的每一次分支的过程都会使得种群根尖数增加，因此，本文设置了种群个体总数的上限Num。当种群生长点总数超过Num时，则将会依据每个生长点的适应度对种群中处于弱势的个体进行淘汰。淘汰的准则是，每次淘汰种群中适应度处于最差的个体，直到总数小于设定阈值Num。

# 3 根生优化模型的理论分析

# 3.1收敛性证明

引理1在等比数列 $\left\{ { { \pmb a } _ { n } } \right\}$ 中，通项 $\scriptstyle { \pmb { a } } _ { n } = { \pmb { a } } _ { 1 } \cdot { \pmb { q } } ^ { n - 1 }$ ， $\pmb { a } _ { 1 } \neq 0$ ，则 $\left\{ { \pmb a } _ { n } \right\}$ 收敛的充分条件是 $\mid q \mid < 1$ 。

引理2一阶常系数线性非齐次方程：

$$
x ^ { k + 1 } + a x ^ { k } = f { \bigl ( } x { \bigr ) }
$$

解的收敛条件是la<1

证明

上述差分方程对应的特征方程是 $\lambda - a = 0$ ，解得 $\lambda = a$

则该方程对应的齐次方程通解为 $x ( k ) = C \cdot a ^ { k }$

为保证方程的解收敛，必须保证齐次通解的收敛，即limak=0，有la|<1

证毕。

定理1对于向量集合 $\mathbf { \nabla } _ { A }$ ，其中每一个向量都是 $n$ 维，必然能够找到一个 $n$ 维的超球面，将集合 $\textbf { \em A }$ 中的所有向量包裹。

定理2若 $0 < a < 1 , 0 < b < 1$ ，则有

$$
0 < | a - b | < 1
$$

定理3根生群优化算法的主根生长行为是收敛的。

证明

为简化证明过程，对于本文中的 $n$ 维向量，只考察其在1维时的情况，即 $n = 1$ 。

主根的生长表达式为

$$
x _ { i } ( t + 1 ) = \omega \cdot x _ { i } ( t ) + \alpha \cdot \theta \cdot \gamma
$$

将 $\theta$ 展开得

$$
x _ { i } ( t + 1 ) = \omega \cdot x _ { i } ( t ) + \frac { \alpha \cdot \gamma } { \left| O _ { i } ( t ) - x _ { i } ( t ) \right| } ( O _ { i } ( t ) - x _ { i } ( t ) )
$$

将上式转换为差分方程的形式：

$$
x ( t + 1 ) + { \bigl ( } { \frac { \alpha \cdot \gamma } { \left| O ( t ) - x ( t ) \right| } } - \omega { \bigr ) } \cdot x ( t ) = { \frac { \alpha \cdot \gamma \cdot O ( t ) } { \left| O ( t ) - x ( t ) \right| } }
$$

不妨令k= $k = \frac { \alpha \cdot \gamma } { \left| O ( t ) - x ( t ) \right| } - \omega$

重写差分方程得

$$
x ( t + 1 ) + k \cdot x ( t ) = { \frac { \alpha \cdot \gamma \cdot O ( t ) } { \left| O ( t ) - x ( t ) \right| } }
$$

将 $k$ 中的 $\gamma$ 展开得

$$
k = \frac { \boldsymbol { \alpha } \cdot ( 1 - E ) \cdot \boldsymbol { r a n d } \cdot \left| \frac { 1 } { n } \cdot \sum _ { j } x _ { j } ( t ) - x ( t ) \right| } { \left| O ( t ) \cdot x ( t ) \right| } - \boldsymbol { \omega }
$$

$$
p = \left| \frac { \displaystyle \frac { 1 } { n } \cdot \sum _ { j } x _ { j } ( t ) - x ( t ) } { \cal O } ( t ) - x ( t ) \right| ,
$$

则 $k = \alpha \cdot ( 1 - E ) \cdot r a n d \cdot p - \omega$ 当 $t \to \infty$ ，有

$$
\operatorname* { l i m } _ { t \to \infty } p = \operatorname* { l i m } _ { t \to \infty } \left| { \frac { { \frac { 1 } { n } } \cdot \sum _ { j } x _ { j } ( t ) - x ( t ) } { O ( t ) - x ( t ) } } \right| = 1
$$

又 $0 < \alpha < 1$ ， $0 < 1 ~ { \cdot } ~ E < 1$ ， $0 \textless r a n d \textless 1$ ，则有 $0 < \alpha \cdot ( 1 - E ) \cdot r a n d \cdot p < 1$ ·

又 $0 < \omega < 1$ ,根据定理2,可得 $0 < \left| \alpha \cdot ( 1 - E ) \cdot r a n d \cdot p - \omega \right| < 1$ 。即 $0 { < } | k | { < } 1$ ，根据引理2可知，差分方程的解收敛的充要条件即是 $\scriptstyle 0 < | k | < 1$ 。

证毕。

# 3.2有效性分析

由于植物根系的向营养性，植物的根尖总是朝着土壤中养分浓度较高的区域生长，RGSO很好地模拟了这一特性。为了体现种群的多样性，RGSO将生长点分为主根生长点和侧根生长点。根据差分方程的收敛性，可以推导出寻优结果的收敛性。在实验中可以证明，RGSO确实可以快速有效地找到极值点。

# 4 实验及结果分析

实验环境：MATLAB R2014b on the HPCC ofLenovoShenteng6800，该集群拥有8个计算节点和一个总控节点。每一个计算节点是一台高性能服务器，内存为 $2 4 ~ \mathrm { G B }$ ，四核2.4GHz 中央处理器。所有服务器的操作系统是RedHatEnterpriseLinux 7。

# 4.1基准函数

实验中用于测试的基准函数包括10个在智能进化算法中经常用到的基准函数，这些基准函数如表2所示。

# 4.2生长策略与参数分析

实验中的迭代总数设置为1000次，根生优化算法的各参数设置如表1所示，每一个参数的设定都是经过多次实验的测试以确保算法的效果达到最好。

主根的生长是将群体中较为优秀的个体作为参考，即建立一个包含当前所有较优秀个体的超球，以该超球球心作为当前个体追随的目标，目的是最大化利用所有有用信息，起到一定程度跳出局部最优的作用。侧根生长依照随机游走的原则，即使在主根生长陷入局部最优时，期望能够跳出局部最优。

参数 $\scriptstyle a$ 起到调节主根生长步长的作用，不断调整 $\scriptstyle a$ 值，算法的数值寻优结果随 $\scriptstyle a$ 值得变化如图3所示，图中纵轴的数值取以自然常数 $e$ 为底的对数。 $\scriptstyle a$ 在[0.5,0.6]取值时，算法性能达到最好。参数 $b$ 影响算法的收敛速度和精度，若 $b$ 值过小，则算法精度较差， $b$ 值过大，则算法收敛较慢。参数 $\beta$ 起到调节侧根生长步长的作用，经多次实验， $\beta$ 取值为[5,10]时，配合以上参数，算法的效果达到最好。

![](images/4e63993dbe5db783340f47fa219ede4123a4ad55e32ca2104fdb0adda0d3d762.jpg)  
图3在不同 $\alpha$ 值下算法寻优结果(Sphere, ${ \bf D } { = } 6 0$ ）

表1 RGSO参数设定  

<html><body><table><tr><td></td><td>值</td><td>RO50步双改定 意义</td></tr><tr><td>参数</td><td>1</td><td>根尖初始数量</td></tr><tr><td>r Num</td><td>100</td><td>群体规模</td></tr><tr><td>b</td><td>3</td><td>分支数</td></tr><tr><td>α</td><td>[0,1]</td><td>参数</td></tr><tr><td>β</td><td>[5,10]</td><td>参数</td></tr></table></body></html>

# 4.3与其他算法比较及分析

本节中将RGA，SSO，PSO以及RGSO 进行比较测试，分析RGSO的性能。实验中的迭代总数设置为1000次，每种算法分别独立运行30次，计算均值与方差。每次测试当达到最大迭代次数或结果误差值小于 $1 0 ^ { - 1 0 }$ 时，实验将终止。

${ \bf D } { = } 6 0$ 的结果比较如表3所示， $\scriptstyle \mathrm { { D = 1 0 0 } }$ 的结果比较如表4所示。各算法在 ${ \bf D } { = } 6 0$ 上的排名如图4所示，在 $\scriptstyle \mathbf { D = 1 0 0 }$ 上的排名如图5所示。

从表3中可以看到，在 ${ \mathrm { D } } { = } 6 0$ 时，RGSO在f1、f3、f5以及f7下都有十分有效的结果，在其余基准函数下也有较好的结果。从表4中可以看到，在 $\scriptstyle \mathbf { D } = 1 0 0$ 时，RGSO在fl、f3、f5以及f7下都有十分有效的结果，在其余基准函数下也有较好的结果。从图4和图5中可以看到，相较于其他算法，RGSO在f1、f2、f3、f5、f6、f7上有着更加精确的结果。

在大部分基准函数下，RGSO有着良好的效果且算法表现较稳定。但在某些多模函数下，RGSO的表现并不十分出色。经分析，原因如下：a)RGSO 的理论基础是由一颗种子发育为整个种群，因此，初始种子位置的选取一定程度上影响了最终算法的迭代精度与速度；b)分支数的选取对结果也有影响。

表2基准测试函数表  

<html><body><table><tr><td>基准函数</td><td>函数方程</td><td>维度（D)</td><td>取值范围</td><td>最小值</td></tr><tr><td>Sphere</td><td>f（x）=x² i=1</td><td>60&100</td><td>[-100,100]</td><td>0</td></tr><tr><td>Rosenbrock</td><td>f(x)=∑(00(x²-xit1）²+(1-x)²) i=1</td><td>60&100</td><td>[-30,30]</td><td>0</td></tr><tr><td>Schwefel2.22</td><td>f（x）=∑x1+I[x =</td><td>60&100</td><td>[-10,10]</td><td>0</td></tr><tr><td>Rastrigin</td><td>f4(x)=∑(x²-10cos(2πxi)+10) i=1</td><td>60&100</td><td>[-10,10]</td><td>0</td></tr><tr><td>SumSquares</td><td>f（x）)=≥ix² i=</td><td>60&100</td><td>[-10,10]</td><td>0</td></tr><tr><td>Ackley</td><td>f6(x)=20+exp-20exp(-0.2 x D台 exp(- ∑cos(2πx)) D台</td><td>60&100</td><td>[-32,32]</td><td>0</td></tr><tr><td>Griewank</td><td>f7(x)= COs ))+1 4000 = i=1 Vi</td><td>60&100</td><td>[-600,600]</td><td>0</td></tr><tr><td>F4</td><td>f=418.9829n + -xi sin(√x|) 𝑖=1</td><td>60&100</td><td>[-100,100]</td><td>0</td></tr><tr><td>Salomon</td><td>D D f=-cos(2π ∑x²)+0.1 i=1 ∑x²+1</td><td>60&100</td><td>[-100,100]</td><td>0</td></tr><tr><td>Levy</td><td>f0=0.1(sin²(3πx)+∑(-1)²(1+sin²(3πx +1)) +(x -1)²(1+ sin²(2 xD))</td><td>60&100</td><td>[-10,10]</td><td>0</td></tr></table></body></html>

表3RGA，SSO，PSO，RGSO 的结果比较 $\scriptstyle ( \mathrm { D } = 6 0 )$   

<html><body><table><tr><td colspan="2">Function</td><td>RGA</td><td>SSO</td><td>PSO</td><td>RGSO</td></tr><tr><td rowspan="2">Sphere</td><td>Mean</td><td>0.0056</td><td></td><td>1.0565e+003 1.8134e+004 3.2030e-005</td><td></td></tr><tr><td>Std</td><td>0.0023</td><td></td><td>4.4693e+003 1.3196e+004 1.1855e-005</td><td></td></tr><tr><td rowspan="2">Rosenbrock</td><td>Mean</td><td>279.1657</td><td>117.1419</td><td>8.0333e+006</td><td>69.7145</td></tr><tr><td>Std</td><td>111.7336</td><td>41.1482</td><td>2.4626e+007</td><td>28.6350</td></tr><tr><td rowspan="2">Schwefel2.22</td><td>Mean</td><td>132.1208</td><td>374.4894</td><td>604.1314</td><td>0.0579</td></tr><tr><td>Std</td><td>124.1313</td><td>211.5519</td><td>372.3285</td><td>0.0020</td></tr><tr><td rowspan="2">Rastrigin</td><td>Mean</td><td>281.6219</td><td>291.8714</td><td>363.0958</td><td>303.9969</td></tr><tr><td>Std</td><td>43.0766</td><td>55.9090</td><td>62.8330</td><td>27.0229</td></tr><tr><td rowspan="2">SumSquares</td><td>Mean</td><td>0.2279</td><td>0.9511</td><td>8.5148</td><td>4.5992e-005</td></tr><tr><td>Std</td><td>0.1898</td><td>0.8232</td><td>3.5358</td><td>4.0291e-005</td></tr><tr><td rowspan="2">Ackley</td><td>Mean</td><td>4.2865</td><td>4.8903</td><td>3.7933</td><td>2.6506</td></tr><tr><td>Std</td><td>0.4581</td><td>0.8484</td><td>0.4963</td><td></td></tr><tr><td rowspan="2">Griewank</td><td></td><td>Mean 8.7372e-004</td><td>0.3704</td><td>1.0331</td><td>0.5124</td></tr><tr><td>Std</td><td>1.0842e-004</td><td></td><td></td><td>5.8924e-005</td></tr><tr><td rowspan="2">F4</td><td>Mean</td><td>10.5784</td><td>0.0664 50.3823</td><td>0.0306</td><td>2.5941e-005</td></tr><tr><td>Std</td><td>6.7566</td><td>47.8534</td><td>103.0523</td><td>1.0989e-003</td></tr><tr><td rowspan="2">Salomon</td><td>Mean</td><td>941.5325</td><td>1.6509e+003 3.6255e+003</td><td>82.0002</td><td>0.5067e-003 1.9854</td></tr><tr><td>Std</td><td>865.2547</td><td>1.4654e+003 2.1242e+003</td><td></td><td>0.8965</td></tr><tr><td rowspan="2">Levy</td><td></td><td>Mean 8.4367e-003</td><td>0.7243</td><td>10.5673</td><td>3.8652e-004</td></tr><tr><td>Std</td><td>5.9672e-003</td><td>0.1265</td><td>8.1839</td><td>2.9524e-004</td></tr></table></body></html>

表4RGA，SSO，PSO，RGSO 的结果比较 $( \mathrm { D } { = } 1 0 0 )$ （204号  

<html><body><table><tr><td colspan="2">Function</td><td>RGA</td><td>SSO</td><td>PSO</td><td>RGSO</td></tr><tr><td rowspan="2">Sphere</td><td>Mean</td><td>0.5357</td><td>68.9464</td><td>4.8886e+004</td><td>0.0257</td></tr><tr><td>Std</td><td>0.1439</td><td>13.6176</td><td>2.1782e+004</td><td>0.0077</td></tr><tr><td rowspan="2">Rosenbrock</td><td></td><td>Mean 1.0521e+004</td><td>690.8419</td><td>1.4017e+008 136.0489</td><td></td></tr><tr><td>Std</td><td>2.7700e+004</td><td>142.5517</td><td>1.0982e+008</td><td>40.9249</td></tr><tr><td rowspan="2">Schwefel2.22</td><td>Mean</td><td>718.5855</td><td>689.6575</td><td>861.8725</td><td>6.289295</td></tr><tr><td>Std</td><td>164.5298</td><td>210.7466</td><td>109.4321</td><td>2.183518</td></tr><tr><td rowspan="2">Rastrigin</td><td>Mean</td><td>595.8592</td><td>645.8945</td><td>760.3829</td><td>550.0200</td></tr><tr><td>Std</td><td>83.5125</td><td>70.6721</td><td>57.1647</td><td>51.4200</td></tr><tr><td rowspan="2">SumSquares</td><td>Mean</td><td>12.1975</td><td>37.4532</td><td>182.6591</td><td>0.0672</td></tr><tr><td>Std</td><td>4.7167</td><td>15.5354</td><td>83.5327</td><td>0.0209</td></tr><tr><td rowspan="2">Ackley</td><td>Mean</td><td>5.5952</td><td>6.8521</td><td>5.8084</td><td>3.3317</td></tr><tr><td>Std</td><td>0.6533</td><td>0.7191</td><td>0.6568</td><td>0.5793</td></tr><tr><td rowspan="2">Griewank</td><td>Mean</td><td>0.0685</td><td>1.0633</td><td>1.6492</td><td>0.0211</td></tr><tr><td>Std</td><td>0.0166</td><td>0.0386</td><td>0.1578</td><td>0.0077</td></tr><tr><td rowspan="2">F4</td><td>Mean</td><td>862.0364</td><td>6.1934e+003 4.5236e+006</td><td></td><td>1.0998</td></tr><tr><td>Std</td><td>696.8623</td><td>1.1786e+003 2.0902e+006</td><td></td><td>0.7870</td></tr><tr><td rowspan="2">Salomon</td><td></td><td></td><td>Mean 6.1263e+004 3.8265e+006 6.5956e+008 55.5455</td><td></td><td></td></tr><tr><td>Std</td><td></td><td>4.9462e+004 1.9023e+006 3.7548e+008 29.8974</td><td></td><td></td></tr><tr><td rowspan="2">Levy</td><td>Mean</td><td>68.6240</td><td>993.8613</td><td>3.2852e+004</td><td>0.2133</td></tr><tr><td>Std</td><td>55.6724</td><td>530.0251</td><td>2.8090e+004</td><td>0.0954</td></tr></table></body></html>

![](images/0d2e8592ee1b2a98b1ea87fd40aa12a1eda1c390243a473a53e8a4547109afb3.jpg)  
图4各算法在 ${ \bf D } { = } 6 0$ 上的排名

![](images/5c0270fdfe6ca4a5960c32de3a15569c8a0ed23219aa28f7bedaf6e9785e51c2.jpg)  
图5各算法在 $\scriptstyle \mathbf { D = 1 0 0 }$ 上的排名

# 5 结束语

受启发于植物根系的生长过程，本文在已有根生算法的基础上作出改进，提出了根生群优化算法（RGSO），用于解决优化问题。通过构建根系群模型，描述了根系生长过程中根系总体的生长情况以及根尖的分类；通过构建群生长模型和引入SVDD 构建土壤养分分布模型阐述了不同分类的根尖的生长方式,使得种群内部的类别划分更加合理，也加快了算法的收敛速度和精确性。从理论上证明了算法的全局收敛性。在实验中调节参数，确定了使算法达到最佳效果的参数值。与当前最先进的其他算法的对比，如PSO，SSO，RGA等，结果显示RGSO具有较高的有效性以及全局收敛性。

# 参考文献：

[1]De Domenico M, Granell C,Porter M A,et al. The physics of spreading processes in multilayer networks [J]. Nature Physics,2016,12 (1O): 901- 906.   
[2]Schmidt M,Lipson H.Distilling free-form natural laws from experimental data [J]. Science,2009,324 (5923): 81-85.   
[3]Ziebert F,Aranson I S.Computational approaches to substrate-based cell motility [J].Computational Materials,2016,2.   
[4]EchavarraiC E,Ramriez-Orteg6n A.An optimization algorithm inspired by

the States of Matter that improves the balance between exploration and

exploitation [J],Applied Intellgence,2014,40 (2): 256-272.   
[5]Cuevas E,Cienfuegos M,Zaldv ar D,et al.A swarm optimization algorithm inspired in the behavior of the social-spider [J]. Expert Systems with Applications,2014,40 (16): 6374-6384.   
[6]Rashid MA,Khatib F,Md Hoque T,et al.An enhanced genetic algorithm for ab initio protein structure prediction [J]. IEEE Trans on Evolutionary Computation,2016,20 (4): 627-644.   
[7]Zhu Qun, Yin Zhonggang, Zhang Yanqing,et al. Research on two-degreeof-freedom internal model control strategy for induction motor based on immune algorithm [J].IEEE Transon Industrial Electronics,2016,63 (3): 1981-1992.   
[8]Gao Yang,Du Wenbo,Yan Gang. Selectively-informed particle swarm optimization [J]. Scientific Reports,2015.   
[9]Kennedy J,Eberhart R C.Particle swarm optimization [C]/ Proc of, IEEE International Conference on NeuralNetworks.1995: 1942-1948.   
[10] Zhang Hao,Zhu Yunlong, Chen Hanning.Root growth model: a novel approach to numerical function optimization and simulation of plant root system[J].Soft Computing,2014,18 (3): 521-537   
[11] Niazmardi S,Homayouni S,Safari A.An improvedFCM algorithm based on the SVDD for unsupervised hyperspectral data classification [J].IEEE Journal of Selected Topics in Applied Earth Observationsand Remote Sensing,2013,6 (2): 831-839.   
[12] Tisan A,Chin J. An end-user platform for FPGA-based design and rapid prototyping of feedforward artificial neural networks with on-chip backpropagation learning[J].IEEE Trans on Industrial Informatics,2016, 12 (3): 1124-1133.   
[13]Ab Ghani H,Hamzah MH,Syahali S,etal.Ant-colonyalgorithm with interference cancelltion for cooperative transmission [J]. IET Signal Processing,2016,10 (6): 603-610   
[14]Daneshmand S V,Heydari H.A diversified multiobjective simulated annealing and genetic algorithm for optimizing a three-phase HTS transformer[J]. IEEE Trans on Applied Superconductivity,2016,26 (2):1- 10.   
[15] Ahmed F,Deb K.Multi-objective optimal path planning using elitist nondominated sorting genetic algorithms [J],Soft Computing,2013,17（7): 1283-1299.   
[16] Zhang Z, Qian S.Artificial immune system in dynamic environments solving time-varying non-linear constrained multi-objective problems [J]. Soft Computing,2011,15 (7): 133-1349.   
[17]Li Changhe, Yang Shengxiang,Nguyen TT.A self-learning particle swarm optimizer for global optimization problems [J]. IEEE Trans on Systems, Man,and Cybernetics,Part B: Cybermetics,2012,42 (3): 627-646.   
[18] Gong YJ, Zhang J, Chung HS,et al. Anefficient resource allocation scheme using particle swarm optimization[J]. IEEE Trans on Evolutionary Computation,2012,16 (6):801-816.   
[19]KleinCE,Segundo EHV,MarianiVC,etal.Modified social-spider optimization algorithm applied to electromagnetic optimization [J].IEEE Tran on Magnetics,2016,52(3):1-4.   
[20] Liu Liang,Song Yuning,Zhang Haiyang,et al.Physarum optimization: a biology-inspired algorithm for the steiner tree problem in networks [J]. IEEE

Trans on Computers,2015,64(3): 818-831.

[21]Xiang Feng,Lau FCM,Yu Huiqun.A novel bio-inspired approach based on the behavior of mosquitoes [J].Information Sciences,2013,233 (2): 87- 108.