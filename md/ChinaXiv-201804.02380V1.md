# 基于二分图的两级动态异构网络选择方案

王文兵，于永生

(兰州交通大学 电子与信息工程学院，兰州 730070)

摘要：通信技术的发展，使多种接入技术并存的异构网络成为未来通信网络的发展趋势，随着用户业务QoS需求的提高和传输带宽的增加，现有的网络选择算法已经不能满足用户高质量的通信需求。针对异构无线网络频谱资源日益紧缺的问题，提出了由用户端和网络端共同参与的两级动态网络选择方案。该方案包括灰度关联分析法和二分图联合优化匹配算法，通过用户端和网络端的共同决策，算法在有效满足移动用户业务服务质量需求的前提下，优化了系统吞吐量，均衡了网络负载。仿真实验表明，相对传统算法，该方案极大地提高了异构网络频谱资源利用率并降低了用户在无线网络间的切换概率，实现了用户需求和网络资源的合理配置。

关键词：异构网络；灰度关联分析；优化匹配；吞吐量；网络负载；网络资源中图分类号：TP393.02 doi:10.3969/j.issn.1001-3695.2018.01.0104

# Two-level dynamic heterogeneous network selection scheme based on bipartite graph

Wang Wenbing, Yu Yongsheng (School ofElectronic &Information Engineering,Lanzhou Jiaotong University,Lanzhou 73oo70,China)

Abstract:Withthedevelopmentofcommunication technologies,heterogeneous networkswith multipleaccesstechnologies have becomethetrendof futurecommunication networks.With the increaseof QoS requirements foruser services and the increaseof transmission bandwidth，existing network selection algorithms canno longersatisfyusers'high quality communication needs.Inviewofte increasing shortage ofspectrumresources inheterogeneous wireless networks,his paper proposedatwo-level dynamic network selection scheme that involves both the user and the network.The scheme includes gray correlationanalysis method and bipartite graph joint optimization matching algorithm.Through the joint decisionof theuser andthe network,thealgorithm optimizes the systemthroughput and equalizes the network loadonthe premiseof efectively satisfying thequalityof servicerequirements of mobile users.Simulation resultsshow thatcompared with the traditional algorithm,the scheme greatly improves theutilizationratioof spectrum resources in heterogeneous network,reduces the handoverprobabilityof users switching between wireless networks,and realizes therational alocationof users'needs and network resources.

Key words: heterogeneous network;correlationanalysisof graydegree；optimize match; throughput;network load;network resources

# 0 引言

随着移动通信技术的进步，未来的通信网络将是多种接入技术相互融合而形成的异构网络。基于不同接入技术的有效融合，用户可以获得更多个性化网络业务[1]，得到更好的服务质量（qualityof service,QoS）[2]。网络选择不仅影响用户业务的通信质量，而且会对网络资源的利用和负载均衡产生影响[3]。因此，网络选择成为异构无线网络融合领域研究的热点问题之一。

异构网络选择需要考虑用户偏好和多种网络属性的影响，对此已经有了许多研究成果。文献[4]提出了以接收信号强度为判决指标的网络选择算法，判决因素简单，可靠性低。文献[5]提出了负载均衡算法(MLB)，考虑了接入网络的负载均衡，但判决因素单一，网络资源利用率不高。文献[6]提出了基于多目标的层次分析法（AHP）均衡网络指标的权重，再引入与理想值近似度排序法（TOPSIS)[7]对备选网络进行排序。文献[7]中结合用户QoS需求及网络特性评判了这种接入选择机制的优越性。文献[8]中引入了灰度关联分析法（GRA)，在备选网络排序的基础上选择与理想网络灰色关联度最大的网络接入，在文献[4]的基础上，全网资源得到了合理分配，提高了异构网络频谱资源利用率。但是该算法与实际场景存在匹配性差异，影响判决的准确性。文献[9]提出了一种基于加权二分图的网络选择算法，将用户偏好和网络参数进行匹配度计算，以权值最大化为匹配目标建立加权二分图模型并求取最优的网络选择结果，优化了异构网络中的资源分配。但未考虑业务优先级调度、网络负载超额的情况。以上算法较偏向于用户侧，没有考虑如何利用有限的网络频谱资源实现用户和网络双方的利益最大化。

针对上述不足，本文在二分图算法的基础上提出了由用户端和网络端共同参与决策的两级网络选择方案。在用户端，为了满足用户QoS需求，本文提出了一种基于多目标决策（multi-objectivedecisionmaking.MODM）[l0]的灰度关联分析（GRA）算法；在网络端，为了实现用户与网络最优匹配，在二分图匹配算法的基础上提出了联合优化匹配算法（jointoptimizationmatchingalgorithm,JOM),通过MATLAB仿真软件验证比较。

# 1 系统建模和接入选择模型

# 1.1 网络模型

本文研究的异构无线网络场景是由一个UMTS 网络、一个WLAN网络和一个WiMAX网络构成的网络研究模型，研究范围包含蜂窝小区UMTS、无线局域网络小区WLAN和无线城域网络小区WiMAX，如图1所示。

![](images/82872369457b3705a40cfbf2805d24263ec4fa1347cc41ac98d67a848ac48c5a.jpg)  
图1异构无线网络拓扑图

图1中，WLAN网络和WiMAX网络都处在UMTS网络的覆盖范围之内，g点和 $h$ 点表示用户处在UMTS 网络的覆盖范围， $a$ 点表示用户处于UMTS网络和WLAN网络的覆盖范围， $c$ 点表示用户处于UMTS网络和WiMAX网络的覆盖范围， $b$ 点表示用户处在三个网络的覆盖范围之内。

# 1.2接入选择模型

1.2.1构造判断矩阵

首先建立多指标接入模型，用户作为决策者，可选网络为备选方案，接入判决参数作为判决准则。具体的数学建模过程如下：

$X = \left\{ x _ { 1 } , x _ { 2 } , x _ { 3 } , \cdots , x _ { m } \right\}$ 表示 $m$ 个备选方案(可选网络)的集合。

$Y = \left\{ { y _ { 1 } , y _ { 2 } , y _ { 3 } , \cdots , y _ { n } } \right\}$ 表示 $n$ 个判决指标或准则（判决指标参数）的集合。

备选网络集合和网络判决指标参数集合构成一个 $m { \times } n$ 阶的决策矩阵 $A = \left[ \boldsymbol { a } _ { i , j } \right] _ { m \times n }$ ，记为

$$
A = { \left[ \begin{array} { l l l l } { a _ { 1 1 } } & { a _ { 1 2 } } & { \cdots } & { a _ { 1 n } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } & { \cdots } & { a _ { 2 n } } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { a _ { m 1 } } & { a _ { m 2 } } & { \cdots } & { a _ { m n } } \end{array} \right] }
$$

其中： $a _ { i j }$ 为备选网络集合 $x _ { i }$ 对于判决指标参数 $y _ { j }$ 的结果。

# 1.2.2权重的确定

用根值法来计算权重，设

$$
A w = \lambda _ { \operatorname* { m a x } } w
$$

其中: $\lambda _ { \operatorname* { m a x } }$ 是矩阵 $A$ 的最大特征根， $w$ 是对应的特征向量，将特征向量归一化之后得到权重向量 $W = \left\{ w _ { 1 } , w _ { 2 } , \cdots , w _ { n } \right\}$ 计算步骤如下所示：

a）计算决策矩阵每一行元素的乘积，记为

$$
W _ { i } = \prod _ { j = 1 } ^ { n } a _ { i j }
$$

其中 $i = 1 , 2 , \cdots , n$ ，其中 $a _ { i j }$ 表示矩阵 $A$ 的第 $i$ 行第 $j$ 列的元素；

b）对 $W _ { i }$ 进行 $n$ 次方根的计算，记为

$$
Z _ { \scriptscriptstyle i } = \sqrt [ n ] { W _ { \scriptscriptstyle i } }
$$

再对向量 $Z _ { i }$ 进行归一化计算，则得到 $w _ { i }$ 为

$$
w _ { i } = Z _ { i } { \Bigg / } \sum _ { i = 1 } ^ { n } Z _ { i }
$$

其中： $0 \leq w _ { i } \leq 1$ ，且 $\sum _ { i = 1 } ^ { n } w _ { i } = 1 , i = 1 , 2 , \cdots , n _ { \circ }$

从以上两步可求得备选网络判决指标的权重向量为$\left\{ w _ { 1 } , w _ { 2 } , \cdots , w _ { n } \right\}$ ，由于考虑到网络条件、用户偏好的动态变化，决策矩阵的取值也是动态变化的，所以必须综合考虑各种情况下权重的动态变化。

通过上文的求解可知判决指标属性集的权重向量为$\left\{ w _ { 1 } , w _ { 2 } , \cdots , w _ { n } \right\}$ ，设判决属性 $w _ { k }$ 的调整权重为 $\lambda _ { k }$ ，其中，

$0 \leq \lambda _ { k } \leq 1$ ，且 $\sum _ { k = 1 } ^ { n } \lambda _ { k } = 1 , k = 1 , 2 , \cdots , n$ =1，k=1,2,…,n。则得到综合权重为

$$
\alpha _ { k } = \lambda _ { k } w _ { k }
$$

其中： $k = 1 , 2 , \cdots , n$ 。对综合权重采用根值法进行归一化处理。

# 2 两级动态网络选择算法

# 2.1基于灰度关联的网络加权排序

在用户端，本文提出了灰度关联网络排序选择算法。灰度关联分析就是将备选方案分为不同的等级，使备选网络接近最优方案的同时远离最劣方案，以此对备选网络接入方案进行优先级的排序，从而选出最优方案。分析步骤如下：

a）根据实际情况，选取判决指标，创建评估矩阵。

基于前文的分析，选择带宽、时延、抖动、丢包率、资费等判决指标，然后根据每个网络的属性指标建立评估矩阵。

b)根据成本型和效益型的指标类型对判决指标参数进行合理化，确定理想标准序列。

对于成本性指标，属性值越小越好，可以表示为

$$
x _ { i j } = \frac { \left( X _ { i j } \right) _ { \operatorname* { m a x } } - X _ { i j } } { \left( X _ { i j } \right) _ { \operatorname* { m a x } } - \left( X _ { i j } \right) _ { \operatorname* { m i n } } }
$$

对于效益型指标，属性值越大越好，可以表示为

$$
x _ { i j } = \frac { X _ { i j } - \left( X _ { i j } \right) _ { \operatorname* { m i n } } } { \left( X _ { i j } \right) _ { \operatorname* { m a x } } - \left( X _ { i j } \right) _ { \operatorname* { m i n } } }
$$

在以上参数指标里，带宽属于效益型指标，时延、抖动、丢包率、资费都属于成本型指标。

c）比较序列 $X _ { i }$ 与理想序列 $X _ { 0 }$ 的关联系数

$$
\begin{array} { c } { \gamma \big ( x _ { 0 } \big ( k \big ) , x _ { i } \big ( k \big ) \big ) = } \\ { \frac { \displaystyle \operatorname* { m i n } _ { i } \operatorname* { m i n } _ { k } \left| x _ { 0 } \big ( k \big ) - x _ { i } \big ( k \big ) \right| + \rho \operatorname* { m a x } _ { i } \operatorname* { m a x } _ { k } \left| x _ { 0 } \big ( k \big ) - x _ { i } \big ( k \big ) \right| } { \big | x _ { 0 } \big ( k \big ) - x _ { i } \big ( k \big ) \big | + \rho \operatorname* { m a x } _ { i } \operatorname* { m a x } _ { k } \left| x _ { 0 } \big ( k \big ) - x _ { i } \big ( k \big ) \right| } } \end{array}
$$

其中： $\rho$ 为分辨系数，且 $\rho \in \left[ 0 , 1 \right]$

d）比较序列 $X _ { i }$ 与理想序列 $X _ { 0 }$ 的加权关联度

$$
\Gamma \big ( x _ { 0 } , x _ { i } \big ) = \sum _ { k = 1 } ^ { n } \beta _ { k } \gamma \big ( x _ { 0 } \big ( k \big ) , x _ { i } \big ( k \big ) \big )
$$

最后，依据加权关联度 $\Gamma \big ( x _ { 0 } , x _ { i } \big )$ 的大小对备选网络进行排序并确立优先级。

# 2.2基于二分图的改进联合优化匹配算法

在网络端，本文基于二分图[12]提出了一种联合优化匹配算法（JOM)。该算法以联合优化空闲网络频谱资源利用率和用户在网络间切换率为目标，解决用户和备选网络资源之间的分配选择问题。假设 $U S = \left\{ u _ { 1 } , u _ { 2 } , \cdots , u _ { k } \right\}$ 为用户集合， $k$ 为用户的数量； $N E T = N e t _ { 1 } \bigcup N e t _ { 2 } \bigcup \cdots \bigcup N e t _ { k } = \left\{ x _ { 1 } , x _ { 2 } , \cdots , x _ { m } \right\}$ 为备选网络集合，其中 $N e t _ { i }$ 为可以使用的网络资源集合， $m$ 为备选网络的数量。网络选择可以表示为在用户集合 $U S$ 和网络集合NET之间寻找一个优化匹配关系满足以下目标函数：

$$
\operatorname* { m i n } _ { 1 \le i \le N } \operatorname* { m a x } _ { 1 \le j \le N } U _ { i , j } \times \Gamma _ { i , j } \times W _ { i , j }
$$

$$
\operatorname* { m i n } { \sum O _ { i , j } \times W _ { i , j } }
$$

$$
\mathrm { s . t . } U _ { i , j } = \frac { u _ { i , r e } } { x _ { i , c a } }
$$

$$
\begin{array} { l } { { \displaystyle \sum _ { i } O _ { i , j } = \sum _ { i } W _ { i , j } = 1 } } \\ { { \displaystyle \sum _ { j } O _ { i , j } = \sum _ { j } W _ { i , j } = 1 } } \end{array}
$$

其中，目标函数1表示最小最大化异构网络的资源利用率；目标函数2表示最小化用户在异构网络间的切换概率，即在保持业务传输质量服务需求的情况下，下一周期用户的网络切换决策应该尽可能的维持原有的用户网络选择规律。 $U _ { i , j }$ 表示用户 $i$ 占用网络资源 $j$ 的资源利用率； $\Gamma _ { i , j }$ 表示用户 $i$ 根据自己的需求对所选网络 $j$ 的偏好程度，由加权关联度的计算过程可以求得；假设用户从接入一个网络开始到切换到下一个网络为止为一个周期，则矩阵 $O = \left[ o _ { i , j } \right] _ { N \times N }$ 和W=[Wi,jNxN 分别记录了上一轮网络分配周期和下一轮网络选择周期，用户与备选网络的匹配关系，其中 $N = \operatorname* { m a x } \left\{ k , m \right\}$ 。

根据上式可以把网络选择问题建模成一个基于二分图的优化匹配问题。这是一个多目标的0-1规划问题，使用传统算法计算的复杂度为 $O \big ( n ! \big )$ ，为了降低复杂度，本文提出了JOM算法，在不影响用户传输性能的前提下，使算法的复杂度降低至 $O \big ( n ^ { 3 } \big )$ ，方便了用户对网络的选择。

在每一轮网络分配决策周期内，JOM算法将根据闲置的异构网络频谱资源的资源利用率以及 $U S / N E T$ 否为原匹配关系，为用户和网络之间映射构成的二部图 $G$ 的每条边赋予一个新的权值Super-weight，如图2所示，权值的分配规则如下：

a)对满足最低网络频谱资源利用率要求的边，如果用户与异构网络闲置频谱资源映射满足原有的匹配关系，设置$S u p e r - w e i g h t = N + 1 \ :$ 0

b)对二分图匹配过程中不能够满足新一轮异构网络分配周期内最低频谱资源利用率要求的边，设置Super-weight $= 0$ ，其余情况则设置Super-weight $\mathrel { \mathop : } = N$ 。

通过以上分析，可以把异构网络环境中的网络选择问题构建为基于二分图的优化匹配问题。JOM算法通过引入新的二部图权值，将异构网络的频谱资源利用率和用户在所选网络之间的切换概率的双目标优化问题，转换为单一目标二部图 $G$ 的最大权值完美匹配问题，该问题的解决可以借助匈牙利算法求解[13]。

![](images/fa6ae6cc913e1e9321d01a104a0f59e61e68242ba243d8408a1f299ece5b8a8e.jpg)  
图2二部图权值的设定

由于标准化的二部图才存在完美匹配，所以构造一个标准化的二部图成为JOM算法实现的关键。

如果用户的数量 $k$ 大于备选网络的数量m，则增加$k - m$ 个数目的备选网络至集合并设定其相应的权值为0，如图3所示。

![](images/7128170ca946c93d49d86642fec9e699fd22561a4f33a3d2abe06679ce0c3fc6.jpg)  
图3标准化二部图（ $k > m$ ）

如果备选网络的数量 $m$ 大于用户的数量 $k$ ，则增加$m - k$ 个数目的用户至集合并设定其相应的权值为1，如图4所示。

![](images/7bc8e317a0828a93e2abd5614cd0713ac9a0767bc888822499beaab4f87e0cb1.jpg)  
图4标准化二部图（ $m > k$ ）

在二分图的基础上可以用联合匹配优化算法（JOM）来解决异构网络选择问题。JOM首先构造集合 $U S$ 和NET之间映射的标准化二部图 $G$ ；其次计算新一轮网络分配周期的最低网络频谱资源利用率，并结合用户与备选网络资源映射是否存在于原有匹配关系当中，为每条边设置相应的Super－weight权值；最后根据匈牙利算法计算最大权值完美匹配问题，得到用户与备选网络资源之间的匹配关系。JOM算法还可以通过调整最新一轮网络频谱分配决策周期内的最低频谱资源利用率阀值来平衡网络频谱资源利用率和用户在网络间的切换概率两者之间的优化关系。综上所述，联合匹配优化算法（JOM）的具体描述如下：

a）算法输入。用户 $i$ 在异构网络环境中的备选网络资源集合 $N e t _ { i }$ ;b)算法输出。用户集合 $U S$ 和备选网络资源集合NET映射之间的匹配关系；c）计算阈值。根据网络频谱资源利用率最小最大化为单一优化目标，计算新一轮网络频谱分配决策周期内所应满足的最低网络频谱资源利用率;d）二部图 $G$ 权值设定。若网络频谱资源利用率低于新一轮频谱资源利用率阈值的匹配关系，设定其权值$S u p e r - w e i g h t = 0$ ；若网络频谱资源利用率高于新一轮网络频谱资源利用率阈值并且符合原有用户和网络间匹配关系的，则设定其权值 $S u p e r - w e i g h t = N + 1$ ，其余情况，设定其权值Super-weight=N;

e）最大权值求解。用匈牙利算法求解二部图 $G$ 的最大权值完美匹配问题。

# 3 仿真结果与分析

# 3.1仿真环境

通过MATLAB软件对本文所提出的两级网络选择方案进行了仿真，假设用户到达网络的概率服从泊松分布。由网络拓扑图可以看出，UMTS网络覆盖了整个区域，包括WLAN和WiMAX网络的覆盖区域，假设MS以从左到右的方向从g点匀速运动到 $h$ 点的过程中。各个网络资源的属性如下表所示。

表1备选网络资源各属性特征指标  

<html><body><table><tr><td>网络</td><td>带宽（Kbps)</td><td>时延（ms）</td><td>丢包率 (%)</td><td>抖动 (ms)</td><td>资费</td></tr><tr><td>UMTS</td><td>2000</td><td>35-50</td><td><1</td><td>4</td><td>0.9</td></tr><tr><td>WLAN</td><td>4500</td><td>130-500</td><td><5</td><td>10</td><td>0.2</td></tr><tr><td>WiMAX</td><td>5000</td><td>150-500</td><td><5</td><td>20</td><td>0.5</td></tr></table></body></html>

# 3.2结果分析

移动用户从g点移动到 $^ h$ 点的过程中，用户在异构网络中的接入选择可以基于下面三种场景来分析。

场景1MS 仅仅处在UMTS 的覆盖区域内，如图1中所示的g点和 $h$ 点，用户直接接入UMTS网络进行通信。

场景2如图1所示，当MS 到达UMTS 和WLAN的公共覆盖区域或UMTS和WiMAX的公共覆盖区域时，备选网络增加了WLAN和WiMAX，此时接入选择机制开始工作。

场景3当MS 到达三个网络(UMTS、WLAN、WiMAX)的重叠覆盖区域后，三个网络都成为了备选对象。网络参数的取值情况如表1所示，假设各个指标的权重经过归一化后是相等的，即权重向量为（0.2，0.2，0.2，0.2，0.2)。开启网络的接入选择机制，首先用灰度关联分析法对备选网络进行排序，然后根据网络的优先次序与用户建立完备的优化匹配关系，计算出备选网络与用户之间有最大权值Super-weight的网络作为用户的最佳接入。

假设在用户接入的过程中，存在三种类型的用户业务，分别为视频、话音和文件传输业务，这几种业务分别对参数指标有不同的要求，其中话音业务的服务质量需求最为严格（时延${ < } 5 0 \mathrm { m s }$ ，抖动 ${ < } 5 \mathrm { m s }$ ，丢包率 $< 3 \%$ ，带宽占用9.6Kbps)；视频业务次之（时延 ${ < } 2 0 0 \mathrm { m s }$ ，抖动 $< 5 0 \mathrm { m s }$ ，丢包率 $< 5 \%$ ，带宽占用90Kbps)；文件传输业务对各项参数指标没有具体的要求，支持最高传输速率为120Kbps[14]。

![](images/a0f8cb155994cbd7e9e3fc0bdc977877e9b12559981f6286122c5f4328cb3b00.jpg)  
图5备选网络的选择和切换

![](images/8eb1775ad02e3393f2782ed44087ed023bb0aacd922b88a8bba6f4c6155a7132.jpg)  
图6用户在备选网络间切换概率随用户数目的变化关系

图5中频段{1,2}是WLAN 网络频段，频段 $\{ 3 , 4 \}$ 是

WiMAX网络频段，频段 $\{ 5 , 6 \}$ 是蜂窝网络频段。基于蜂窝网络较高的参数指标，所以被用来支持话音业务的通信需求，WLAN网络具有较高的传输带宽，用来支持文件和视频业务的传输。图6描述了用户在网络间的切换频率随用户数目的变化关系，相比传统二分图网络选择算法，本文提出的两级关联选择方案包含一个基于二分法的两级优化匹配算法(JOM)，在网络频谱资源排序的基础上，使不同属性的网络频谱资源服务于不同类型的用户业务。该算法一定程度上减少了用户在网络间的切换次数，当用户数量增加时，切换频率会维持一个稳定状态，可以较好地满足用户通信需求。仿真结果表明，该方案可以平均降低用户在网络间的切换概率 $32 \%$ 。

![](images/9edd47fdf469818c18b0633a991b99063a1ccd3e464c6c81b15336ea6604f8eb.jpg)  
图7网络吞吐量随用户数目的变化关系

![](images/f598858403e35485127c4873aa7cc5948f01efaa207710f737ff5db186dfc977.jpg)  
图8网络阻塞率随用户数目的变化

图7所示是异构网络有效吞吐量随用户数目变化的仿真图。有效吞吐量定义为能够满足用户业务传输需求的吞吐量，即接收端能够成功接收到用户发送的数据包。与传统二分图算法相比，本文方案包含一个灰度关联网络加权排序算法（GRA)，该算法在确定备选网络优先级，合理利用网络频谱资源的同时，兼顾了信道容量，利用网络频谱资源属性（带宽、时延、抖动等）来判别用户的接入，提高了网络吞吐量。该算法收敛速度快，当用户数目达到50左右时到达平衡状态。图8是网络阻塞率变化仿真图，相比传统算法，本文方案在网络排序算法的基础上利用二分图对不同业务类型的用户与备选网络进行完备匹配，通过优化匹配，使不同的网络频谱资源服务于不同类型的用户业务传输，在满足用户通信需求的基础上均衡了网络负载，降低了网络阻塞率。随着用户数目的增加，本文所提方案收敛速度快，网络阻塞率明显低于传统算法，当用户数目增加到40左右时，开始趋于平稳。该算法采用多项网络资源属性指标值对备选网络进行衡量，通过分析可知，本文方案可以很好地满足用户业务的传输需求，提高网络有效吞吐量，从而满足终端用户的数据传输需求。

# 4 结束语

本文所提的两级动态选择方案中GRA算法确立了备选网络的优先级，使用户在可接入网络间做出选择，联合优化匹配算法（JOM）使用户和备选网络根据权值建立完备匹配关系，在提高网络资源利用率的同时，减少了用户在网络间的切换次数，保证了移动用户在异构网络环境下海量的数据传输。但本文所提方案并未考虑到决策过程中网络指标属性随时间的变化以及终端用户变速运动的情况。今后的研究工作首先应考虑用户运动状态改变对网络选择的影响。其次，在满足业务传输需求的同时，应考虑网络指标属性值在不同时间点的变化给算法带来的影响。

# 参考文献：

[1]李宁．异构网络中的网络选择研究[D].北京：北京邮电大学,2011.(Li Ning.Network selection in heterogeneous networks [D]. Beijing: Beijing University of Posts and Telecommunications,2011.)   
[2]刘际鑫．异构无线网络环境中的网络选择算法研究[D].北京：北京邮 电大学，2015.(Liu Jixin.Research on network selection algorithm in heterogeneous wireless networks [D].Beijing: Beijing University of Posts and Telecommunications,2015.)   
[3] 刘军，李晓楠．基于层次分析法的 WLAN/蜂窝网络切换判决算法[J]. 通信学报,2013,34(2):65-72.(Liu Jun,Li Xiaonan.Handover algorithm for WLAN//cellular networks with analytic hierarchy process [J].Journal on Communications,2013,34 (2):65-72.)   
[4]Song Wei,Jiang Hai,Zhuang Weihua,et al.Call admission control for integrated voice//data services in cellular//WLAN interworking[C]//Proc ofIEEE International Conference on Communications.20o6: 5480-5485.   
[5]李军，房雅丁，宋梅，等．异构网络中一种基于灰度关联的动态接入选 择策略[J].北京邮电大学学报，2006,29(s2):174-177.(Li Jun,Fang Yading,Song Mei,et al.A gray relation analysis-based dynamic access selection strategy in heterogeneous networks [J]. Journal of Beijing University of Posts and Telecommunications,2006,29 (s2): 174-177.)   
[6]刘胜美，孟庆民，潘甦，等．异构无线网络中基于 SINR 和层次分析法 的 SAW垂直切换算法研究[J]．电子与信息学报,2011,33(1):235-239. (Liu Shengmei,Meng Qingmin,Pan Su,et al.A simple additive weighting vertical handoff algorithm based on SINR and AHP for heterogeneous wireless networks [J]. Journal of Electronics $\&$ Information Technology, 2011,33 (1): 235-239.)   
[7]Lahby M, Cherkaoui L,Adib A. Network selection algorithm based on DiffAHP and TOPSIS in heterogeneous wireless networks $[ \mathrm { C } ] / \hbar$ Proc of International Conference on Multimedia Computing and Systems.2012: 485-490.   
[8] Charilas D, Markaki O,Tragos E.A theoretical scheme for applying game theory and network selection mechanisms in access admission control [C]// Proc of International Symposium on Wireless Pervasive Computing. 2008: 303-307.   
[9]鲍楠，夏玮玮，鲍煦．异构网络融合环境下基于加权二分图的网络选择 算法[J].电信科学,2015,31(9): 44-50.(Bao Nan,Xia Weiwei,Bao Xu. Network selection algorithm based on weighted bipartite graph in heterogeneous network environment [J]. Telecommunications Science,2015, 31 (9): 44-50. )   
[10] Deng H, Yeh C H,Wilis R J. Inter-company comparison using modified TOPSIS with objective weights [J]. Computers & Operations Research, 2000,27 (10): 963-973.   
[11]黄涛．基于灰色关联度分析的模糊群决策方法研究[D]．广州：华南理 工大学，2016.(Huang Tao.Research of fuzzy multi-atribute decision making method based on grey correlation analysis [D]. Guangzhou: South China University ofTechnology,2016.)   
[12] Kim T,Dong M.An iterative hungarian method to joint relay selection and resource allocation for D2D communications [J]. Wireless Communications Letters IEEE,2014,3(6):625-628.   
[13] ChithraR,Bestak R,Patra SK.Hungarian method based joint transmission mode and relay selection in device-to-device communication [C]/ Proc of IFIP Wireless and Mobile Networking Conference.2016: 261-268.   
[14]葛雨明，孙毅，蒋海，等．基于认知无线电技术的动态频谱分配方案研 究[J].计算机学报,2012,35(3): 446-453.(Ge Yuming,SunYi,Jiang Hai, et al.Research on dynamic spectrum allocation using cognitive radio technologies [J]. Chinese Journal of Computers,2012,35(3): 446-453.)