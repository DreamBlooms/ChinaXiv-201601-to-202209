# 结合基因遗传和贪婪搜索的布谷鸟社区检测算法

王小刚，闫光辉，周宁(兰州交通大学 电子与信息工程学院，兰州 730070)

摘要：为了提高复杂网络社区结构挖掘的精度，结合基因遗传和贪婪搜索提出一种面向模块度优化的布谷鸟社区检测算法(GGCSCA)。布谷鸟种群在有序邻居表上逐维随机游走，并采用优质基因遗传策略，使得种群高效优化，同时应用局部模块度增量最大化的贪婪偏好搜索算法快速提升种群质量，以取得好的社区划分结果。GGCSCA在基准网络和经典网络上进行了实验，并与一些典型算法进行对比，结果说明了本社区发现算法的有效性、准确性和快速收敛性，具有较强的社区识别能力，能够精细地检测出网络社区结构。

关键词：复杂网络；网络社区；布谷鸟搜索算法；贪婪搜索；基因遗传中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2017.08.0871

# Cuckoo search algorithm combining gene inheritance and greedy search for community detection

Wang Xiaogang, Yan Guanghui, Zhou Ning (School ofElectronic&Information Engineering,Lanzhou Jiaotong University,Lanzhou 73o7o,China)

Abstract: Inorder to improve the acuracyofcommunity detectionforcomplex networks,this paper proposed analgorithm based oncuckoo search algorithm combining gene inheritance and greedy search (GGCSCA)to optimize modularity for communitydetection.Cuckoos walkedrandomlyonorderedadjacent table and employed gene inheritancestrategy,whichaim to optimize population eficiently.The algorithm improved population quality quicklyby gredy preference searchof local modularity increment maximum for the purpose of geting good result ofcommunity partition. GGCSCA has been tested on both benchmarknetworksandsome typicalcomplex networks,andcompared with sometypicalcommunitydetectionalgorithms. Experimental results show the efectiveness,accuracyand fast convergence of this algorithm for discovering community structure.It has strong capability of community identification and can detect the structure of community finely. Key Words: complex network; network community; cuckoo search algorithm; greedy search; gene inheritance

# 0 引言

复杂网络是对复杂系统重要特征的抽象概括，其核心思想是将现实系统中所有实体及实体间的关系转换为网络的节点和边，以网络的形式来描述系统中各部分之间的关系，便于深入分析系统结构的拓扑特性，揭示现实系统的本质规律。很多现实系统可以表示为复杂网络或转换为复杂网络，如社交网络、生物网络、计算机网络、交通网络等，复杂网络已经是重要的多学科交叉研究领域。

复杂网络由若干社区组成，社区内部的连接比较紧密，而社区之间的连接比较松散[1]。社区发现探测复杂网络中固有的社区结构，是当前复杂网络领域的一个研究热点。社区发现有助于分析复杂网络功能、内在规律和拓扑结构特性，提供复杂网络演化研究的中观视角，其研究成果已被成功应用于蛋白质功能预测、恐怖组织识别、舆情分析、客户关系聚类、搜索引擎等多方面[2-3]。

复杂网络社区挖掘已经获得了广泛的研究，涌现了很多社区检测算法。常见典型算法主要有基于图分解、分裂的算法，如Kernighan-Lin 算法[2]，谱分法[4]，GN 算法[1]；基于凝聚的算法，如FastNewman 算法[5]，CNM算法[]；基于随机游走的方法，如WalkTrap[7算法；基于优化的算法，这种方法通过对某种社区评价函数进行优化得到划分结果，常见的是基于模块度指标的优化算法。Newman和Girvan定义了模块度函数[8]，用于评价社区划分。基于模块度优化的算法如模拟退火算法[9]、BGLL算法[10]、极值优化[1]等。虽然有了很多的社区探测算法，但是社区识别的准确性、效率、易用性甚至通用性等方面还需改善。

# 1 相关工作

近些年，通过智能进化算法进行社区检测已经成为热点。选择合适的社区划分评价函数，可以将复杂网络社区发现问题转换为优化问题，但是实现最优化目标往往是NP难的问题。利用智能进化算法，选择合适的启发式规则可以取得较好的近似优化结果。

智能进化社区发现算法主要分为多目标优化和单目标优化多目标优化方法如：MOCD-PSO[12]，MDCL[13]。单目标方法一般针对模块度进行优化，基本的思想是通过迭代进化追求模块度的最大化。智能进化算法用于社团检测出现较早的是模拟退火算法，Guimera等人提出了以模块度为优化函数基于模拟退火算法的复杂网络社区检测算法GA[9]，该成果于2005 年被《Nature》报道。

黄发良提出一种基于粒子群优化的网络社区发现算法(CDPSO)[14]，该方法基于节点邻居有序表的编码进行全局搜索,一定程度上缓解了基于二值编码的迭代二划分策略导致的局部最优划分问题，这种基于节点邻居有序的方式在很多进化社区检测算法中得以使用。邱晓辉面向社区发现的改进粒子群优化算法[15]，在上述方法的基础上，使用最多邻居从属的变异策略，即节点以一定概率变异为邻居最多从属的社区。Tasgin等人设计了适合字符串编码的单路交叉操作，通过利用GA(geneticalgorithm)算法优化社区模块度Q函数来实现网络最优划分的近似[16]。邓琨等人给出一种基于遗传框架的社团检测算法[17],根据节点评价值实施有指向性的变异策略以克服随机变异的盲目性。金弟等人分析了模块性函数的局部梯度特性，结合遗传算法，提出快速有效地局部搜索变异策略，可用于大规模网络社区检测[18]。Gach 和Hao 提出的社区检测算法[19]将遗传方法中的交叉算子和Memetic 算法结合在一起，用BGLL算法产生初始解，基于优先级由两个父聚类的社区交叉产生新的社区结果。金弟等人从仿生学角度出发，以蚁群算法为框架，基于随机游走，给出一种社区发现算法[20]，将蚂蚁的局部解集成为全局解，通过"强化簇内连接，弱化簇外连接"使社区结构呈现出来

近两年涌现出一些比较新颖的进化社区检测算法。如Chopade提出了一种基于博弈论的复杂网络社区发现方法[21],基于纳什均衡将网络划分为紧密的社区。通过重新定义的针对权重网络的节点相似性、拉普拉斯矩阵和模块度，在进化博弈中寻找针对适应度的纳什均衡点。网络中每个节点作为博弈者按照最大化收益决定将自己划分到哪个社区，直到每个节点收益不再增加，从而得到社区划分结果；段震提出基于商空间的多层粒化社区发现方法[22]，该方法对复杂网络进行多层次粒化操作，形成逐层粒化和抽象的多粒度商空间，并选择最佳粒层作为划分结果。金志刚提出基于密度峰值聚类的自适应社区发现算法（KDED）[23]，算法将节点关系量化为基于信任度的距离矩阵，根据距离矩阵核密度估计和节点影响力大小统计分析，结合热扩散模型改进计算流程，使其自适应不同规模的数据集以提高计算精度。根据密度峰值聚类原理和社区属性确定社区中心节点，然后根据节点间的距离得到社区内部层次结构和社区外部的自然结构，最后将剩余节点按距离分配到相应的社区中，得到社区划分结果。

与粒子群、蚁群等算法比较，布谷鸟算法是一种新颖的智能进化算法，具有很强的搜索能力，算法只需要一个参数，易于实现，效率高。目前，应用于模块度优化的布谷鸟算法很少见到，本文提出结合基因遗传和贪婪搜索的布谷鸟社区检测算法(cuckoo search algorithm combining gene inheritance and greedysearch forcommunitydetection,GGCSCA），基于布谷鸟算法的框架和搜索能力，构造一种基于邻接表随机游走的全局搜索算法，并融合了全局基因保留和局部贪心算法，目的是基于智能进化获得更好的复杂网络社区识别和检测能力。实验结果说明算法有效可用，并且相对具有较好的收敛性、准确性。

# 2 布谷鸟算法

布谷鸟算法是YangXin-she 提出的一种群智能搜索算法[24],该算法搜索速度快，精度高，已被广泛应用于科学研究和工程实践的优化问题。该算法灵感来自于布谷鸟的寄生巢行为。每个鸟巢代表一个候选解，通过基于 $L e \nu y$ 飞行的随机游走方式搜索新的解，具有很强的全局搜索能力。

设 $X _ { i } = \{ x _ { _ { i 1 } } , x _ { _ { i 2 } } , \cdots , x _ { i n } \}$ 是某 $n$ 维鸟巢当前解，通过式(1)产生新的解。

$$
X _ { i } ^ { t + 1 } = X _ { i } ^ { t } + \alpha \oplus L e \nu y
$$

$\alpha$ 是步长, $L e \nu y ^ { \mathrm { ~ \tiny ~ \textnormal ~ { ~ \chi ~ } ~ } }$ 行随机游走公式为

$$
L { \big ( } s { \big ) } \sim s ^ { - \lambda } { \big ( } 1 < \lambda \leq 3 { \big ) }
$$

其中： $s$ 是游走步长, $\lambda$ 是步长规模参数,按照Mantegna 的算法，

$$
s = \frac { \mu } { \left| \nu \right| ^ { 1 / \beta } }
$$

$\mu \sim N \left( 0 , \sigma _ { \mu } ^ { 2 } \right) , \nu \sim N \left( 0 , \sigma _ { \nu } ^ { 2 } \right) \triangleleft$ 是正态分布, $\sigma _ { \nu } = 1$ ，

$$
\sigma _ { u } = \left\{ \frac { \Gamma \left( 1 + \beta \right) \sin \left( \pi \beta / 2 \right) } { \Gamma \left[ \left( 1 + \beta \right) / 2 \right] \beta 2 ^ { \left( \beta - 1 \right) / 2 } } \right\} ^ { 1 / \beta }
$$

布谷鸟算法在当前解的基础上通过Levy飞行随机游走产生新的解，评价并保留较好的解；然后以概率 $p a$ 丢弃部分解，用偏好搜索重新生成与丢弃解相同数量的解，再次评价并保留较好的解。

以上是基本的布谷鸟算法，适用于连续空间的函数优化问题，难以直接用于复杂网络空间的社区检测问题，本文借助于该算法的基本思想和基本框架，针对求解的问题，设计和实现了一种适合复杂网络离散空间的布谷鸟社区检测算法。

# 3 布谷鸟社区检测算法

# 3.1评价函数

评价函数使用Newman的模块度函数[8.10]：

$$
Q = \frac { 1 } { 2 m } \sum _ { i j } \Biggl ( A _ { i j } - \frac { k _ { i } k _ { j } } { 2 m } \Biggr ) \delta ( C _ { i } , C _ { j } )
$$

$m$ 是网络的总边数， $A _ { i j }$ 是网络的邻接矩阵， $k _ { i }$ 是节点 $i$ 的度， $C _ { i }$ 表示 $i$ 所属的社区，当 $i , j$ 属于同一社区时 $\delta ( C _ { i } , C _ { j } ) { = } 1$ 否则等于0。公式的含义是：社区内总边数和网络总边数的比值减去一个期望值，该期望值假设网络是随机网络时同样的社区分配所形成的社区内总边数和网络总边数的比值大小。这是一种数学方式刻化的社区划分评价，它的取值范围是-0.5到1。很多社区发现算法基于模块度优化，目标是尽可能最大化模块度，但是优化Q是NP难问题，所以都是近似优化。模块度方法缺点是难以发现小于一定规模 $\delta$ 的小社团， $\boldsymbol { \delta }$ 与具体的网络规模相关。尽管有这样的模块度限制[25]，模块度优化方法依然不失为一种有效地通用方法。式(5)的模块度函数针对无向无权网络，有向网络和带权网络有对应的类似模块度函数，从模块度函数优化的角度出发，本文基于无向无权网络，不失一般性。

# 3.2信息编码

布谷鸟巢穴编码采用基于节点标号的编码方式，设网络为$G = ( V , E )$ ，节点数为 $n$ ，对于一个巢穴解 $X _ { i } = \{ x _ { _ { i 1 } } , x _ { _ { i 2 } } , \cdots , x _ { i n } \}$ ，若 $x _ { i m } = k ~ , ~ m = 1 { \cdots } n$ ，则表示节点 $\mathbf { \Sigma } _ { m }$ 和 $k$ 处于同一个社区中，最后通过归并可以得到社区的划分结果。本文以邻居有序表[14]为基础，巢穴逐维在网络上进行随机游走，即 $x _ { i m }$ 的值在节点 $m$ 的邻居节点序列上随机游走取得，保障不会产生非法解。初始化时， $x _ { i m }$ 随机取得节点 $\mathbf { \Sigma } _ { m }$ 邻居节点序列中的某个节点标号。图1(a)是简单网络示例，图1(b)是该网络划分的两个社区，该网络邻居有序表如表1所示，图1(c)中的向量表示了布谷鸟巢穴编码。

表1邻居有序表  

<html><body><table><tr><td colspan="7"></td><td rowspan="2">节点编号 各</td></tr><tr><td>L</td><td>9</td><td>S</td><td>4</td><td></td><td>乙</td><td></td></tr><tr><td></td><td></td><td>4</td><td></td><td></td><td></td><td>乙</td><td></td></tr><tr><td>9</td><td>S</td><td>9</td><td>S</td><td>乙</td><td></td><td></td><td>居节</td></tr><tr><td></td><td>L</td><td>L</td><td>9</td><td></td><td></td><td>1</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>：</td><td></td></tr></table></body></html>

![](images/af3621f943fb3f7022c560de616fae07096559b0e8cf25a30cdc35f150f8755b.jpg)  
图1网络社区、鸟巢编码及网络上的随机游走

# 3.3算法框架和实现

3.3.1基于邻居表的逐维随机游走和基因遗传

布谷鸟搜索算法全局搜索基于随机游走。本文设计的随机游走是基于邻接有序表的逐维随机游走。某鸟巢解t1时刻为$X _ { i } ^ { t _ { 1 } } = \{ x _ { i _ { 1 } } ^ { t _ { 1 } } , x _ { i _ { 2 } } ^ { t _ { 1 } } , \cdots , x _ { i _ { n } } ^ { t _ { 1 } } \}$ ，下一时刻变成 $X _ { i } ^ { t _ { 2 } } = \{ x _ { i _ { 1 } } ^ { t _ { 2 } } , x _ { i _ { 2 } } ^ { t _ { 2 } } , \cdots , x _ { i _ { n } } ^ { t _ { 2 } } \}$ ，从 $\boldsymbol { x } _ { i j } ^ { t _ { 1 } }$ 到 $X _ { i j } ^ { t _ { 2 } }$ 是以概率 $p$ 在邻接表上随机游走而得到，如图1(c)所示。对于节点 $j$ ，概率 $p = \frac { 1 } { d _ { j } }$ d，d是节点j的度。

对于每个巢穴 $X _ { i }$ ，除了用随机游走保证解的灵活性和全局性，每一代较大程度上还要在上一代的基础上进化，以保证求解的效率和收敛。为此每一代除全局最优解外，再取前 $s$ 个较优鸟巢解保存在精英库 $H = \left\{ h _ { 1 } , h _ { 2 } , \cdots , h _ { s } \right\}$ 。 $X _ { i }$ 的每一位xu(j=1n)可看做是一个基因，引入基因遗传策略：分别按概率 $p _ { c }$ 和 $p _ { g }$ 保留某精英基因( $h _ { { \scriptscriptstyle m } }$ )和全局最优解 $\ \cdot g b e s t$ )基因。每次迭代得到 $x _ { i }$ 的公式为：

$$
x _ { i j } = \left\{ \begin{array} { l l } { k } & { r a n d < p _ { c } } \\ { h _ { m j } } & { p _ { c } \leq r a n d < p _ { g } } \\ { g b e s t _ { j } } & { r a n d \geq p _ { g } } \end{array} \right.
$$

$$
h _ { m } = H { \bigl ( } c e i l ( r a n d o m \times s ) { \bigr ) }
$$

$k$ 由随机游走得到。式(7)表示随机抽取精英库中的某个解,ceil表示向最近大整数取整。

下面给出布谷鸟社区搜索算法框架：

算法1布谷鸟社区搜索算法

Input:复杂网络 $G = ( V , E )$ ，鸟巢规模 $l$ ，偏好搜索概率 $p a$ ，迭代次数iter。

Output:社区划分 $C = \left\{ C _ { 1 } , C _ { 2 } , \cdots , C _ { k } \right\}$

begin:

根据网络构建邻居有序表 $A d T a b l e$ ；构建规模为 $s$ 的精英库 $H = \left\{ h _ { 1 } , h _ { 2 } , \cdots , h _ { s } \right\}$ ，元素初始值为空； $t = 0$ ；

定义目标函数为模块度函数 $\boldsymbol { \mathrm { \ell } }$ ：

初始化布谷鸟巢穴种群，每个巢穴 $X _ { i }$ 各维随机取得邻居有序表中的值；计算目标函数值，得到初始 $\boldsymbol { \mathrm { \ell } }$ 值；

更新精英库 $H = \{ h _ { 1 } , h _ { 2 } , \cdots , h _ { s } \}$

按式(6)更新巢穴，每个巢穴 $X _ { i }$ 部分继承优秀基因，部分在邻接表上随机游走一次，得到新的巢穴 $X _ { i } ^ { ' }$ ·

根据 $X _ { i } ^ { ' }$ ,计算目标函数值，若 $Q ( X _ { i } ^ { \prime } ) > Q { \bigl ( } X _ { i } { \bigr ) }$ ，则 $X _ { i } \gets X _ { i } ^ { \prime }$ ：

将 $Q \big ( X _ { i } \big )$ ， $i = 1 , 2 , \cdots l$ 中的最大值best 与当前整体最优gbest比较，若 $b e s t > g b e s t$ ，则 $g b e s t \gets b e s t$ ;

执行局部贪婪搜索算法GreedyLocal $( X , p a )$ （见算法2），得到新的巢穴 $X _ { i } ^ { ' }$ ，依次执行第6步，第7步；然后执行第9步；

$t = t + 1$ ，若迭代次数 $t < i t e r$ ,转第4步执行;否则执行第10步；

退出迭代，对最优解gbest解码，获得社区划分$C = \left\{ C _ { 1 } , C _ { 2 } , \cdots , C _ { k } \right\} \mathrm { ~ c ~ }$ （20号

# 3.3.2局部偏好搜索

局部偏好搜索的目的是提高种群质量，加速搜索过程。本局部搜索方法使用贪婪算法[10]，利用模块度公式计算节点 $i$ 离开当前所在社区进入其他邻接社区时产生的模块度增量 $\Delta Q$ ，找到使得 $\Delta Q$ 最大的那个社区作为该节点的移入社区。这主要分两步，1）使节点 $i$ 离开原社区成为独立节点产生的 $\Delta Q _ { 1 }$ ，见式(8);2)使该独立节点 $i$ 移入新社区产生的增量 $\Delta Q _ { 2 }$ ，见式(9)。$\Delta Q { = } \Delta Q _ { 1 } { + } \Delta Q _ { 2 }$ 。在式(8)和(9）中 $\textstyle \sum _ { i n }$ 代表节点 $i$ 待加入（离开）的社区内部连接权重和， $\textstyle \sum _ { t o t }$ 代表与节点 $i$ 待加入（离开）的社区内各点连边(包括社区内连接和社区外连接)的权重之和。$k _ { i }$ 代表节点 $i$ 的度， $k _ { i , i n }$ 代表在待加入（离开）社区内节点 $i$ 与该社区内节点连边权重和。

$$
\Delta Q _ { \mathrm { l } } = \left[ { \frac { \sum _ { i n } - k _ { i , i n } } { 2 m } } - \left( { \frac { \sum _ { t o t } - k _ { i } } { 2 m } } \right) ^ { 2 } - \left( { \frac { k _ { i } } { 2 m } } \right) ^ { 2 } \right]
$$

$$
- \Bigg [ \frac { \sum _ { i n } } { 2 m } - \Bigg ( \frac { \sum _ { t o t } } { 2 m } \Bigg ) ^ { 2 } \Bigg ]
$$

$$
\Delta Q _ { 2 } = \left[ \frac { \sum _ { i n } + k _ { i , i n } } { 2 m } - \left( \frac { \sum _ { t o t } + k _ { i } } { 2 m } \right) ^ { 2 } \right] -
$$

$$
\Bigg [ \frac { \sum _ { i n } } { 2 m } - \Bigg ( \frac { \sum _ { t o t } } { 2 m } \Bigg ) ^ { 2 } - \Bigg ( \frac { k _ { i } } { 2 m } \Bigg ) ^ { 2 } \Bigg ]
$$

若 $K _ { i } = \left\{ k _ { 1 } , k _ { 2 } , \cdots , k _ { d } \right\}$ 是节点 $i$ 的邻居，则对节点 $i$

$$
{ x _ { i } ^ { \prime } = \mathrm { a r g } \operatorname* { m a x } _ { j } \Delta Q \big ( x _ { i } , j | j \in K \big ) }
$$

即取使得 $\Delta Q$ 最大的邻接点作为更新位置。下面给出局部偏好搜索步骤：

算法2局部贪婪搜索算法

Input:布谷鸟巢穴 $X = \left\{ X _ { 1 } , X _ { 2 } , \cdots , X _ { l } \right\}$ ，邻居有序表AdTable，概率 $p a$

Output:偏好搜索优化后的布谷鸟巢穴$X ^ { \prime } { = } \{ X _ { 1 } ^ { \prime } , X _ { 2 } ^ { \prime } , { \cdots } , X _ { l } ^ { \prime } \}$ decode $( X )$ ,对各候选巢穴 $X _ { i } \left( i = 1 \cdots l \right)$ 进行解码归并,得到对应社区划分。

以概率 $p a$ 确定巢穴 $X _ { i } \left( i = 1 \cdots l \right)$ 的部分候选基因x(j=1n)，计算当节点j离开所在社区加入其他邻居社区时的 $\Delta Q$ ， $\Delta Q { = } \Delta Q _ { 1 } { + } \Delta Q _ { 2 }$ 计算见式(8)、(9)。

找到使 $\Delta Q$ 最大的社区，使 $j$ 加入该社区。

获得新的巢穴 $X ^ { \prime } { = } \{ X _ { 1 } ^ { \prime } , X _ { 2 } ^ { \prime } , { \cdots } , X _ { l } ^ { \prime } \}$

# 3.4算法时间复杂度分析

设节点数为 $n$ ，边数为 $\mathbf { \Sigma } _ { m }$ ，鸟巢数为 $\mathbf { \Phi } _ { l }$ ，循环迭代次数为iter，平均度数为 $d = { \frac { m } { n } }$

算法最主要的步骤及复杂度是：a)构建邻居有序表时间复杂度为 $O ( m ) : { \mathfrak { b } } )$ 初始化鸟巢，复杂度为 $O { \big ( } l \times n { \big ) }$ ；c)逐维随机游走选择一个邻居节点或基因保留运算，复杂度为$O ( i t e r \times l \times n ) \mathrel { \mathop : } \mathfrak { c }$ 1)解码归并社区复杂度为 $O ( i t e r \times l \times n ) : \epsilon$ )设社区数是 $\mathbf { \Psi } _ { c }$ ，计算模块度复杂性为： $O \left( i t e r \times l \times c \times \left( \frac { n } { c } \right) ^ { 2 } \right)$ ：f)局部贪婪搜索中计算 $\Delta Q$ 只需要局部信息，所以其复杂度为$O \big ( i t e r \times l \times d \big )$ 。复杂性最高的是 $O \left( i t e r \times l \times c \times \left( \frac { n } { c } \right) ^ { 2 } \right)$ ，而iter，$\mathbf { \xi } _ { l }$ 为常数，所以复杂度为 $O \Bigg ( \frac { n ^ { 2 } } { c } \Bigg ) = O \Big ( n s \Big )$ =O(ns)，其中s=是社区规C模，一般远小于 $\mathbf { \Sigma } _ { n }$ 。

# 4 实验及分析

数值实验在Inteli5 处理器、4G内存和win7操作系统的电脑上运行，MATLAB2011环境下编程计算。参数设置：布谷鸟算法中，按一般性设置，种群规模 $l$ 为25，偏好搜索概率 $p a$ 为0.25；精英规模 $s$ 为4。

参数分析

$p _ { c }$ 和 $p _ { g }$ 分别是继承某精英基因( $\cdot h _ { { \scriptscriptstyle m } }$ )和全局最优解（gbest）基因的概率阈值。以 $p _ { g }$ 为例，假设种群只继承最优基因，通过独立运行20次的平均值，得出 $p _ { g }$ 对模块度值的影响如图2所示。图中四个网络分别是Karate（空手道俱乐部网络)，Dolphin(海豚网络)，Football(足球联盟网络)[18]和 500个节点的人工生成网络Lfr500。可以看出，在不考虑继承其他精英基因的情况下， $p _ { g }$ 取0.1时效果最好，说明在保持一定灵活性和随机性的基础上尽量继承最优( $g b e s t$ )基因效果最佳，所以按式(6)，$p _ { g }$ 和 $p _ { c }$ 应当在0.1-0.3 之间，且 $p _ { c }$ 不应该超过 $p _ { g }$ 。综合以上分析，在本实验中 $p _ { c }$ 设为0.1， $p _ { g }$ 取0.2。

![](images/36e9a81386c644c5a850561fb8d4a3e6085521374304dbd3403af2f756bf529c.jpg)  
图2参数 $p _ { g }$ 对模块度值的影响

# 4.1人工网络

通过Lancichinetti提出的基准测试网络[26]考察算法对社区的识别能力，该网络有128个节点，分成4个社区，每个社区 32个点，节点平均度16。生成网络时的混合参数 $\mu$ ，显著影响社区结构，其作用是：以概率 $\mu$ 连接社区外部节点，以概率 $1 - \mu$ 连接社区内部节点。 $\mu$ 从0.1到0.5社区结构从清晰变模糊， $\mu { < } 0 . 5$ 时一个节点的邻居属于同一个社区的概率大于社区外，社区结构应该能够识别出来；当取0.5时，每个节点平均有一半的连接指向了社区外的节点，此时社区结构就比较模糊。

本实验采用规范化互信息(NMI)[27来评价社区识别效果，如式(10)所示。

$$
{ \cal N } M I ( A , B ) = \frac { - 2 { \displaystyle \sum _ { i = 1 } ^ { C _ { A } } \sum _ { j = 1 } ^ { C _ { B } } C _ { i j } \log ( \frac { n C _ { i j } } { C _ { i } C _ { j } } ) } } { { \displaystyle \sum _ { i = 1 } ^ { C _ { A } } C _ { i } \log \left( \frac { C _ { i } } { n } \right) + \sum _ { j = 1 } ^ { C _ { B } } C _ { j } \log \left( \frac { C _ { j } } { n } \right) } }
$$

$A$ 与 $B$ 是两种社区划分， $c$ 是混合矩阵， $C _ { A }$ 与 $C _ { B }$ 分别是$A$ 和 $B$ 中社区的个数。 $C _ { i j }$ 是划分 $A$ 中的社区 $i$ 与划分 $B$ 中的社区 $j$ 中重合的节点个数， $C _ { i }$ 表示 $c$ 中 $i$ 行元素之和， $C _ { j }$ 表示 $c$ 中 $j$ 列元素之和。NMI取值范围在[0,1]区间，1表示两社区划分完全一致，0表示完全不同。

将算法生成的社区结构与真实社区结构进行规范化互信息评价，并与igraph 软件中内置的5种社区发现经典算法比较：InfoMap，FastGreedy，LeadingEigenvector，BGLL，LPA。

![](images/a664e1676e1d6dcac05730380c378191ac66b4880e3fe6781f3b8d39972e3433.jpg)  
图3几种算法在人工网络上的NMI值比较

分别以混合参数0.1-0.5产生5个网络，每个算法独立运行50 次，求得NMI平均值。根据图3可以看出，对 $\mu$ 为0.1和0.2 两个网络，各个算法都能正确或基本正确地识别， $\mu$ 为0.3时结果产生分化，LPA和LeadingEigenvector 的结果分别降到了0.9和0.86，到第4个网络只有BGLL和本算法GGCSCA能够完全正确识别，其他几个算法识别最好的LeadingEigenvector其NMI值也仅是0.89。对前四个网络BGLL算法和本文算法GGCSCA都能准确识别，明显优于其他几种算法；对于第5种网络，本文算法NMI为0.41优于BGLL算法的0.32。这充分证明了本算法的社区探测识别能力。

# 4.2 经典网络

用3个经典数据集[18]进行实验，分别是Karate(空手道俱乐部网络)，Dolphin(海豚网络)，Football(足球联盟网络)。

# 4.2.1收敛情况

由图4可以看出算法很快就收敛。空手道俱乐部仅用2次迭代（一次迭代指种群的一次全局搜索和一次局部偏好搜索）就收敛到全局最优值0.4198，迭代次数最多的Footbal1迭代次数也没有超过25次。

![](images/2013fb568e35102c1c4679f75916fbdf3339e2a19862ba0f3e0c28eb6655734a.jpg)  
图4GGCSCA算法收敛图

# 4.2.2社区划分及评价

表2是各种算法对3个网络分别计算模块度50次得到的平均值。算法中包含两种典型智能进化算法：粒子群算法(PSO)和遗传算法CCGA[18,28]。

表2各算法在经典网络上的模块度值比较  

<html><body><table><tr><td>算法</td><td>Karate</td><td>Dophin</td><td>Football</td></tr><tr><td>BGLL</td><td>0.4176</td><td>0.5222</td><td>0.6037</td></tr><tr><td>CNM</td><td>0.3807</td><td>0.4955</td><td>0.5497</td></tr><tr><td>PSO</td><td>0.409</td><td>0.511</td><td>0.598</td></tr><tr><td>GN</td><td>0.4013</td><td>0.4706</td><td>0.5996</td></tr><tr><td>LPA</td><td>0.3805</td><td>0.4963</td><td>0.5915</td></tr><tr><td>CCGA</td><td>0.4198</td><td>0.5273</td><td>0.6005</td></tr><tr><td>infomap</td><td>0.4020</td><td>0.5236</td><td>0.6005</td></tr><tr><td>KDED</td><td>0.402</td><td>0.447</td><td>0.585</td></tr><tr><td>GGCSCA</td><td>0.4198</td><td>0.5275</td><td>0.6037</td></tr></table></body></html>

对karate 网络，本算法GGCSCA模块度Q取得了0.4198的值，优于其他算法（仅有CCGA也取得0.4198)，高于Karate真实社区网络社区结构对应的Q值0.3715，从模块度优化的角度来说本方法取得了很好的结果。从另外一点来看，对有些网络，数学方法衡量的模块度相对于人为划定的真实网络社区结构是有偏差的，karate网络真实的社区结构为2个社区，对应于局部Q最大值而非全局最大值[3]，但按文献[18]说法这也是合理的，本算法将网络划分为4个社区，而这4个社区真好是2个真实社区的更紧凑细分。GGCSCA算法产生的社区划分情况如图5与表3所示。

![](images/5bbaab5ef65a116bf4dfd5baa75ba5ccb150f672d3696b69b58f7edf6c1ecc15.jpg)  
图5karate网络社区图

表3karate 网络社区划分  

<html><body><table><tr><td colspan="2">真实社区</td><td colspan="2">算法产生社区 （细分）</td></tr><tr><td>社区 编号</td><td>节点编号</td><td>社区 编号</td><td>节点编号</td></tr><tr><td rowspan="3">0</td><td>123456781112</td><td>0</td><td>123481213141820</td></tr><tr><td>13141718 20 22</td><td></td><td>22</td></tr><tr><td>910151619 2123 24</td><td>1</td><td>5671117 91015161921232730</td></tr><tr><td rowspan="2">1</td><td>25 26 27 28 29 30 31</td><td>2</td><td>31 33 34</td></tr><tr><td>32 33 34</td><td>3</td><td>24252628 29 32</td></tr></table></body></html>

与空手道网络类似，海豚网络的真实网络对应于Q值0.3722，也是收敛于局部最优。本算法得到平均值0.5278，优于其他几个算法，模块度优化取得了好的结果。真实网络划分为2个社区，本方法所得是5个更紧凑划分的社区，一个社区完全对应，另一个社区细分为4个社区，划分社区情况如图6与表4所示。

![](images/53f3a9fffad066bc7db82f703de26149f1831de9d250003adf16cb50a405ca46.jpg)  
图6Dolphin 网络社区图

表4Dolphin 网络社区划分  

<html><body><table><tr><td colspan="2">真实社区</td><td colspan="2">算法产生社区 （细分）</td></tr><tr><td>社区 编号</td><td>节点编号</td><td>社区 编号</td><td>节点编号</td></tr><tr><td rowspan="4">0</td><td>15679131719 22</td><td>1</td><td>1567913171922 25</td></tr><tr><td>2526 2731324148</td><td></td><td>26 273132 41485456</td></tr><tr><td>54 56 57 60</td><td></td><td>57 60</td></tr><tr><td>0234810111214</td><td>4</td><td>0210 2028 3042 4447</td></tr><tr><td rowspan="5">1</td><td>15 16 18 20 2123 24</td><td>2</td><td>4111518 2123 24 29 35</td></tr><tr><td>28 29 3033 3435 36</td><td></td><td>45 51 55</td></tr><tr><td>37 38 394042 4344</td><td>0</td><td>38 3639 59</td></tr><tr><td>45 464749 50 51 52</td><td>3</td><td>12 141633 3437 38 40</td></tr><tr><td>53 55 58 59 61</td><td></td><td>4346495052535861</td></tr></table></body></html>

对于Football网络，本算法GGCSCA计算的Q平均值取得0.6037，与BGLL算法的值相同，优于其他算法。足球俱乐部的真实网络划分为12个社区，本算法运行过程中最好的划分结果为11个社区，有6个社区完全正常匹配，5个社区的节点基本被正确识别，1个真实社区节点被分配到其他社区，如图7和表5所示（上标代表该节点在对方社区的编号）。

![](images/c42349fd77df10b3a15b0b2ee8a3c67f70c3d4af1af170498b1f6d19bf2d6dee.jpg)  
图7Football网络社区图

表5Football网络社区划分  

<html><body><table><tr><td colspan="2">真实社区</td><td colspan="2">算法产生社区 （匹配）</td></tr><tr><td>社区 编号</td><td>节点编号</td><td>社区 编号</td><td>节点编号</td></tr><tr><td>0</td><td>12533374589103</td><td>4</td><td>12533374589103105 109</td></tr><tr><td>1</td><td>105 109 19 29 30 35 55 79 94 101</td><td>3</td><td>19 29 30 35 55 79 (80 82)1 94101</td></tr><tr><td>2</td><td>2 613 15 32 39 47 60 64 100 106</td><td>0</td><td>2 613 15 32 39 47 60 64 100 106</td></tr><tr><td>3</td><td>3 5 10 40 527274 81 84 98102 107</td><td>9</td><td>3 510 40 52 72 74 81 84 98 102 107</td></tr><tr><td>4</td><td>44 48 57 6675 86 91 92 110112</td><td>8</td><td>44 48 57 5810 (59 63)66 75 86 91 92 979112</td></tr><tr><td>5</td><td>12 14 18 26 31 34 38 43 54 6171 85 99</td><td>1</td><td>12 1418 263134 36 38 42 43 54 61 71 85 99</td></tr><tr><td>6</td><td>0 4916 234193104</td><td>2</td><td>04916 234193104 78 21 22 5168 77 78 108</td></tr><tr><td>7</td><td>78 21 22 5168 77 78 108 111</td><td>7</td><td>111</td></tr><tr><td>8</td><td>17 20 27 56 62 65 70 76 87 95 96 113</td><td>5</td><td>17 20 27 56 62 65 7076 87 95 96 113</td></tr><tr><td>9</td><td>11 24 50 (59 63) 69 978</td><td>10</td><td>11 24 2810 50 69 9011</td></tr><tr><td>10 11</td><td>2810 4649 53 58867 73 83 88 114 (36 42) (80 82) 9010</td><td>6</td><td>49 53 67 73 83 88 1104114</td></tr></table></body></html>

# 5 结束语

本文提出的算法以模块度Q为评价函数，以布谷鸟算法为框架，结合邻接表上的随机游走和基因遗传策略，并应用最大模块度增量的局部偏好搜索，在保证全局灵活性的同时加快种群的收敛。在基准网络和真实网络上的实验说明本算法具有较好的社区识别和检测能力。算法无须提供有关社区的先验知识和假设，可以有效揭示网络内在的社区结构。下一步研究将其与其他算法结合，提高搜索效率；用并行化机制实现，应用到银行交易网络等大型实际复杂网络的社区发掘研究上。

# 参考文献：

[1]Girvan M,Newman ME J. Community Structure in Social And Biological Networks [J].Proceedings of National Academy of Sciences of the United States of America,2002,99 (12): 7821-7826.   
[2]Fortunato S. Community Detection in Graphs [J]. Physics Reports,2010, 486 (3-5): 75-174.   
[3]杨博，刘大有，金弟，等．复杂网络聚类方法[J].软件学报,2009,20 (1): 54-58.   
[4]White S,Smyth P.A Spectral Clustering Approach to Finding Communities in Graphs [Cl/ Proc of SIAM International Conference on Data Mining. 2005: 76-84.   
[5] Newman M E J. Fast Algorithm for Detecting Community Structure in Networks [J].Physical Review E.2004,69(6):066133.   
[6]Clauset A,Newman MEJ,Moore C.Finding Community Structure in Very Large Networks [J].Physical Review E Statistical Nonlinear & Soft Matter Physics [J].2004,70 (2):066111.   
[7]Pons P, Latapy M. Computing Communities in Large Networks Using Random Walks [J].Journal ofGraph Algorithms and Applications .2006,10 (2): 191-218.   
[8]Newman ME J, Girvan M. Finding and Evaluating Community Structure in Networks [J].Physical Review E.2004,69 (2):026113.   
[9]Guimera R,Amaral LA N.Functional Cartography of Complex Metabolic Networks [J]. Natrue,2005,433 (7028): 895-900.   
[10] Blondel V D,Guillaume JL,Lambiotte R,et al.Fast Unfolding of Community Hierarchies in Large Networks [J].Journal of Statistical Mechanics: Theory and Experiment,2008,10:10008.   
[11] Duch J, Arenas A. Community Detection in Complex Networks Using Extreme Optimization [J]. Physical Review E,2005,72(2): 027104.   
[12]黄发良，张师超，朱晓峰．基于多目标优化的网络社区发现方法[J]. 软件学报,2013,24(9):2062-2077.   
[13] Zhou X,Liu Y H,Li B.A Multi-Objective Discrete Cuckoo Search Algorithm with Local Search for Community Detection In Complex Networks [J],Modern Physics Letters B,2016,30(7): 1-20.   
[14]黄发良，肖南峰．网络社区发现的粒子群优化算法[J].控制理论与应 用,2011,28 (9): 1135-1139.   
[15]邱晓辉，陈羽中．一种面向社会网络社区发现的改进粒子群优化算法 [J].小型微型计算机系统,2014,35(6):1422-1425.   
[16] Tasgin M,Herdagdelen A,Bingol H. Community Detection in Complex Networks Using Genetic Algorithms [EB/OL]. (2007-11-04) [2017-05-20]. https://arxiv. org/pdf/0711. 0491. pdf.   
[17]邓琨，张健沛，杨静．利用改进遗传算法进行复杂网络社团发现[J]. 哈尔滨工程大学学报,2013,34(11):1438-1443.   
[18]金弟，刘杰，杨博，等．局部搜索与遗传算法结合的大规模复杂网络社 区探测[J]．自动化学报,2011,37(7):873-879.   
[19] Gach O,Hao JK.A Memetic Algorithm for Community Detection in Complex Networks [C]// Proc of International Conference on Parallel Problem Solving From Nature.[S.1.] $:$ Springer-Verlag,2012: 327-336.   
[20]金弟，杨博，刘杰，等．复杂网络簇结构探测—一基于随机游走的蚁群 算法[J].软件学报,2012,23(3):451-456.   
[21] Chopade P.A Framework for community detection in large networks using game-theoretic modeling[J].Iee Transactions On Big Data,2017,3 (3): 276-287.   
[22]段震，闵星，王倩倩，等．基于商空间的多层粒化社区发现方法[J]. 南京大学学报：自然科学版,2017,53(4):764-772.   
[23]金志刚，徐珮轩．密度峰值聚类的自适应社区发现算法[J/OL].哈尔 滨工业大学学报，2018，50(5）．[2017-08-24].http://kns.cnki. net/kcms/detail/23.1235.T.20170824.1116.002.html.   
[24] Yang X S.Nature Inspired Meta heuristic Algorithms [M]. 2nd ed.[S.1.] : Luniver Press,2010.   
[25] Fortunato S,Barthelemy M. Resolution Limit In Community Detection [J]. Proceedings of National Academy of Sciences of the United States of America,2007,104 (1):36-41.   
[26] Lancichineti A,Fortunato S,Radicchi F.Benchmark Graphs for Testing Community Detection Algorithms [J].Physical Review E,2008,78 (4): 046110.   
[27] Danon L,Duch J, Diaz-Guilera A,et al. Comparing Community Structure Identication [J]. Journal of Statistical Mechanics: Theory and Experiment, 2005,78 (9):09008.   
[28]何东晓，周栩，王佐，等．复杂网络社区挖掘——基于聚类融合的遗传 算法[J].自动化学报,2010,36(8):1160-1170.