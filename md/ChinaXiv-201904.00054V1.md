# 利用改进蚁群算法的重叠社团检测分析方法

许英

(新疆财经大学 应用数学学院，乌鲁木齐 830012)

摘要：针对重叠社团检测准确率提升问题，提出了一种基于改进蚁群算法的新型重叠社团检测算法。该算法包含位置初始化、运动和后处理三个阶段，分别通过初始位置识别与标签列表存储、基于节点间相似度的启发式信息重定义、合作保持标签列表等方式，使算法在合成数据集与现实世界数据集中的重叠社团与节点检测方面具有更好的性能。实验结果表明，在合成网络与现实世界网络平台上使用不同检测算法，所提出的方法对重叠社团与重叠节点的检测准确率较传统检测方法来说更高，因而对重叠社区检测问题求解与理解网络功能结构具有重要的参考与借鉴意义。

关键词：重叠社团与节点检测；改进蚁群算法；启发式信息重定义；标签列表迭代更新中图分类号：TP311.1 doi:10.19734/j.issn.1001-3695.2018.10.0803

# Novel algorithm of overlapping community detection and analysis with improved ant colony algorithm

Xu Ying (School ofApplied Mathematics,Xinjiang University ofFinance&Economics,Urumqi83o012,China)

Abstract: This paper proposes a new detection algorithm for overlappng communities based on ant colony algorithm to improvethe detection acuracyof overlapping communities.Thealgorithm consists of three stages: position initialization, motionand post-processing.The algorithmachieves beter performance through initial position identification and tag list storage,heuristic information redefinition basedon similarity between nodes,and cooperative tag list preservation in synthetic datasetsand real-world datasetsof overlapping communitiesand overlapping nodes detection.The detection performance of diferent detection algorithms onsynthetic and real world network platforms shows that the proposed overlapping community detection and analysis method based on improved ant colony algorithm has good accuracy and analysis performance.The method can be used for reference in solving the current overlapping community detection problem and understanding the functional structure of the network.

Key Words:overlappingcommunityand nodedetection; improvedantcolonyalgorithm;heuristic informationredefinition; tag list iteratively update

# 0 引言

社团定义为网络结构中依据具备共享属性的顶点[1]。类似于社会网络中一个人具有不同角色，在标准化网络分区中，分区中每个顶点被分配给一个社团[2]，且被社团之间共享。此外，由于不同节点在网络结构和功能上具有不同作用，所以检测网络中的重叠社团可更深入地了解网络的功能与结构。因此，近年来重叠社团检测研究已引起学术界极大关注。众多具备良好分析性能的算法相继提出，并广泛应用于延迟容忍网络[3,4]、推荐系统[5]等领域。

当前社团检测算法大致可分为五类[6]，即派系过滤算法（cliquepercolationmethod，CPM）、局部扩展和优化算法、链接分区算法、模糊检测算法和基于代理的算法。文献[7]将索引局部邻接表示法引入社团检测时的个体表示中，将社团结构分析转换为整数优化问题，并据此提出基于差分进化的社团检测算法。文献[8]基于群体智能思想提出一种自组织的重叠社团结构分析算法，但智能体间收敛精度对检测性能影响较大。文献[9]从有效融合两类不同的异质信息研究出发提出了一种基于交互行为和连接分析的社交网络社团检测方法，但检测性能很大程度依赖于数据属性。文献[10]提出一种局部优先的动态网络重叠社团演化分析方法，但其全局最优性有待验证。文献[11]提出了一种使用最优特征向量的谱二分社团检测方法，在上述重叠社团检测算法中，虽然可以一定程度上很好地解决重叠社区检测分析问题，但均忽略了迭代过程中节点标签变更对检测性能的影响。

因此，借鉴蚁群算法中信息素更新与运动路径选择策略，本文提出一种基于改进蚁群算法的重叠社区检测算法(antcolonybasedalgorithm，AntCBO)。在建立基于蚁群算法的重叠社团检测框架基础上，通过基于节点间相似度的启发式信息重定义与基于标签列表更新存储的蚁群路径选择两个环节实现重叠社团检测，基于合成数据集和现实世界数据集平台开展检测算法性能分析。

# 1 AntCBO重叠社区检测算法基本架构

网络抽象可建模为无向图 $G = ( V , \ E )$ ，其中：V、 $E$ 分别为节点与边集合。设每个节点 $\nu$ 都具有唯一标签（identification,ID） $l _ { \nu }$ ，并记 $N ( \nu )$ 为节点 $\nu$ 的邻域。重叠社团检测目的为，寻求某种方法，将抽象得到的无向图 $G$ 分割为一系列小集群 $( C _ { 1 } , C _ { 2 } , . . . , C _ { m } )$ ，使每个集群中具有相同的节点。数学描述为

$$
\cup _ { 1 \leq i \leq m } C _ { i } = G \mathrm { H } . \exists i , j \in m , C _ { i } \cap C _ { j } \neq \emptyset
$$

# 1.1算法框架

提出的AntCBO算法框架如算法1所示，包含四个模块，即参数初始化、蚂蚁位置初始化、运动路径决策与后处理。基本流程为：a）初始化参数，视每个节点为蚂蚁个体，并基于信息素和提出的启发式信息计算转移概率矩阵；b)初始化蚂蚁位置并确定对应的ID列表；c）所有蚂蚁基于转移概率模型移动位置，此过程中每个蚂蚁将节点标签从一个节点传递到另一个节点并更新信息素；d)满足终止条件时，保存蚂蚁个体当前标签列表，得到各节点标签序列；e）采用后处理机制将网络划分为重叠社区。

算法1 AntCBO 算法框架

输入：复杂网络 $G = \left( V , E \right)$ 。输出：一组重叠社团C。  
1参数初始化：迭代次数最大值T；蚂蚁数量 $\boldsymbol { n }$ ；初始信息素值 $\tau$ ；信息素挥发率 $\rho$ ；阈值9；信息素增加量 $x$ ；信息素阈值b。根据式（1） $\sim$ 式（3）计算转移概率矩阵。  
2蚂蚁位置初始化  
3 蚂蚁移动：for $\scriptstyle t = 1$ TO T DOfor $\scriptstyle { i = 1 }$ to n do每个蚂蚁i按照转移概率矩阵移动信息素扩散和更新end forend for  
4后处理

# 1.2AntCBO算法的改进

对 AntCBO 来说， $\tau _ { i j } ( t )$ ， $( i , j { = } 1 , 2 , . . . , n$ 且 $i \neq j )$ 之间的相对大小会直接影响蚁群位置之间的转移概率，从而直接影响可行解的质量。这是由于搜索算法进行过程中，早起分散分布的信息素将逐渐集中至部分边上，从而不断强化搜索方向。当某些边的信息强度明显高出其他边时会导致可行解构造时选择的边过于接近导致解结构过于相似，从而算法陷入局部最优解。而避免算法陷入局部最优解的根本方法是增加可行解的多样性。其核心是使信息素在边上的分布不至过于集中，从而使得更多的边能够以较高的概率参与构造可行集过程。即既充分利用蚁群算法的正反馈机制加快搜索进程，又必须尽可能地过大算法可行解的搜索区域，使用更多边形成新的可行解。遵循这一思路，本文提出直接交换部分变上信息素的方法改变 $\tau _ { i j } ( t )$ 在不同边上的分布，从而避免算法后期陷入局部最优解。具体过程为：每个节点设定交换概率 $p _ { i } , i { = } 1 , 2 , . . . ,$ $n$ ，并生成随机数 $r _ { i } \sim U ( 0 , 1 )$ 。若 $r _ { i } { \leqslant } p _ { i }$ ，则在节点 $i$ 与其他节点可以形成的 $^ { n - 1 }$ 条边中，随机选择一定数量的边，两两互换对应的信息素值；若 $r _ { i } { > } p _ { i }$ ，则不作上述处理。

此外，信息素的挥发率也会影响信息素分布。传统蚁群算法中信息素挥发率 $\rho$ 往往被设置为常数，且每条边的挥发率相同。此种操作会导致部分边用于构造可行解的概率过大，不利于其他边参与构造新可行解。因此，本文采用变参挥发率来避免最优路径上的某些边由于信息素强度过低而失去选择机会，其计算公式如下：

$$
\rho _ { i j } \left( t \right) = 1 \qquad t \leq t _ { e a r l y }
$$

$$
\rho _ { i j } ( t ) = \left\{ \begin{array} { l l } { k _ { 1 } } & { \tau _ { i j } ( t ) \leq C } \\ { k _ { 2 } } & { e l s e } \end{array} \right. \quad t > t _ { e a r l y }
$$

其中： $\rho _ { i j } ( t )$ 表示 $\mathbf { \Psi } _ { t }$ 时刻边 $i j$ 上信息素挥发率； $t e a r l y$ 是早期搜索时间； $k _ { 1 }$ $k _ { 2 } \in ( 0 , 1 )$ 且 $k _ { 1 } { > } k _ { 2 }$ ；此外 $k _ { 1 } , k _ { 2 }$ 两者数值不宜差别过大，否则会导致交换后信息素挥发过快或过慢影响前述交换边效果； $\mathrm { ~ \cal ~ C ~ } _ { }$ 为介于 $\tau _ { i j } ( t )$ 均值与最大值之间的常数。

# 1.3转移概率矩阵计算方法

由于直接模拟蚂蚁觅食行为进行社团相似节点聚类，算法核心为设计合理的启发信息与信息素更新策略计算转移概率矩阵，为蚁群移动路径提供决策依据。结合应用背景，首先采用任意节点 $i$ 与 $j$ 间相似性度值来更新启发信息，如式(4)5)所示。

$$
c o m m ( i , j ) = n e i b o u r ( i ) \cap n e i b o u r ( j )
$$

$$
\eta _ { i j } = \gamma \times \frac { \left| c o m m ( i , j ) \right| } { \left| n e i b o u r ( i ) \cup n e i b o u r ( j ) \right| } +
$$

$$
( 1 - \gamma ) { \times } \frac { 2 { \times } | E ( c o m m ( i , j ) ) | } { ( | c o m m ( i , j ) | ) ( | c o m m ( i , j ) - 1 | ) }
$$

其中： $\left| c o m m ( i , j ) \right|$ 表示节点 $i$ 和 $j$ 共同邻居的数量；neibour $( i )$ 表示节点 $i$ 的邻居； $n e i b o u r ( j )$ 表示节点 $j$ 的邻居； $\vert E ( c o m m ( i , j ) ) \vert$ 表示连接每个共同邻居节点的边的数量。从式(3)可知，启发式信息更新策略由两项组成，并通过权重系数 $\gamma$ 控制两者在启发信息中的重要程度。其中，第一项为顶点 $i$ 和 $j$ 的公共邻居数量除以两个顶点邻居的并集数，它度量了两节点间平均公共邻居节点数；第二项是公共邻居之间的连边数量除以它们之间可能存在的连边数量，并且它量化了公共邻居彼此之间的连接距离。其实际物理意义为，若两邻居节点具有很多公共邻居且公共邻居连接距离较近，其属于同一社团概率更高。计及信息素与启发信息更新策略的状态转移概率矩阵如式(4)所示。

$$
p _ { i , j } = \left\{ \begin{array} { c c } { \tau ( i , j ) ^ { \alpha } \eta ( i , j ) ^ { \beta } } & { j \in n e i b o u r ( i ) } \\ { \sum _ { q \in n e i b o u r ( i ) } \tau ( i , j ) ^ { \alpha } \eta ( i , j ) ^ { \beta } } & { j \in n e i b o u r ( i ) } \\ { 0 } & { \mathrm { e l s e } } \end{array} \right.
$$

其中： $\alpha$ 和 $\beta$ 表征信息素与启发信息在迭代过程中强化程度。

# 2 所提AntCBO算法步骤

# 2.1蚂蚁位置初始化

此步骤首先进行蚂蚁（即节点）位置与对应的标签列表的初始化过程。即网络 $G$ 按各节点的度[12]降序排列后计算各节点间的公共邻居并划分为初始社团 $s g$ ，根据初始社团各节点ID生成相应的标签列表，并将蚂蚁个体放置在初始集群的节点中。具体步骤如下所示。

算法2步骤一：蚂蚁位置初始化输入：一个复杂网络 $G ( V , \ E )$ 。

输出：蚂蚁的位置Cnode以及存储在每个节点 $\boldsymbol { v }$ 的标签列表l(v.)  
1令Cnode、CN、v.L为空集  
2 每个节点 $\boldsymbol { v }$ 具有一个ID  
3 $\forall \nu \in V$ :v.available=true  
4 根据节点的度对所有节点进行降序排序得到列表 $\iota$   
5 for each $v _ { i } \in { L }$ DO  
6 $s g \gets \emptyset$   
7if $\nu _ { i }$ .available且 $d ( \nu _ { i } ) \geq 3$ then  
8找到 $\nu _ { i }$ 的邻居中度最大对的节点 $\boldsymbol { \nu } _ { j }$ 并令 $\nu _ { j } . a \nu a i l a b e \gets t r u e$   
9 $s g  s g \cup \{ \nu _ { i } , \nu _ { j } \}$   
10计算 $\nu _ { i }$ 和 $\boldsymbol { \nu } _ { j }$ 的共同邻居comNei  
11 while $_ { c o m N e i \neq \emptyset }$ do  
12 for each $\nu _ { m }$ in comNei do  
13 $s g  s g \cup \{ \nu _ { m } \}$   
14 $Z = n e i b o u r ( \nu _ { m } ) \cap c o m N e$ i并用 $z$ 代替comNei  
15 end for  
16 end while  
17 end if  
18 $C N \gets C N \cup s g$   
19 for each $\nu _ { x }$ in sg do  
（202 $2 \Theta \nu _ { x } . l \gets \nu _ { j } . I D$   
21end for  
22end for  
23Cnode是 $\mathsf { \Lambda } _ { C N }$ 中节点，不在Cnode 中的节点使用其本身ID 初始化

# 2.2蚂蚁的移动

每个蚂蚁都会根据转移概率将 ID 在两节点间转移。为提高蚂蚁遍历整个网络抽象图 $G$ 的几率，中蚂蚁移动规则设为：如果随机数 $\boldsymbol { r }$ 小于0.1，则蚂蚁将选择具有最大概率的邻居作为下一个要访问的节点；否则蚂蚁随机选择除具有最大转移概率的邻居节点作为访问节点。而蚂蚁需访问多个具有相同转移概率的ID时，将随机选择其一。

迭代结束时，蚂蚁从当前节点移动至下一节点。此外，每个蚂蚁从当前节点的标签列表中选择其一存放至下一节点标签列表中。信息素则存放与蚂蚁在不同节点转移的路径之上。信息素挥发过程则在每次迭代过程结束之时。蚂蚁运动策略如算法3所示。

算法3步骤二：蚂蚁的移动

1while不满足终止条件do  
2for 每只蚂蚁 DO  
3蚂蚁基于转移概率矩阵从节点i移动到节点 $j$   
4 蚂蚁从一个节点移动到下一节点，并从当前节点到下一个节点获得  
一个标签，将这一标签保留在下一节点标签列表  
5该边的信息素量增加 $x$   
6if信息素值超过阈值bthen  
7将信息素的值设置为b

8end if

9 所有的蚂蚁移动后，所有边的信息素按 $\rho$ 挥发， $\tau _ { n e w } = ( 1 - \rho ) \times \tau$   
10end for

11重新计算转移概率矩阵

12end while

此外，为避免算法过早收敛到非全局最优解，规定：当信息素超出预定值 $b$ 时，应将边缘信息素限制到最大值。通过这种方式，可以有效地避免一条路径上的信息量远远大于其他路径上的信息量，并且可消除所有蚂蚁集中在同一条路径的情况。

# 2.3 后处理

迭代终止后，统计各节点中标签列表各从属值出现的频率。若某一值出现频率在整个标签列表中取值较大，则该节点属于该标签的概率更高。为提高重叠社团检测准确率，可采用算法对待检测网络进行多次扫描，以确定最终的社团划分。后处理步骤如算法4所示。其中： $\big | N ^ { l ( \nu ) } \big |$ 表示具有标签 $\mathbf { \xi } _ { l }$ 的节点 $\nu$ 的邻居节点的数量；sum表示节点 $ { \boldsymbol \nu }$ 的邻居节点中的所有可能的标签的数量。

算法4步骤三：后处理  
输入：节点及其标签列表。  
输出：重叠社团的集合 $c$ 。  
1首先根据标签列表中频率从最大的标签获得每个节点的标签2for each 节点 $\boldsymbol { v }$ do  
3找到节点 $\boldsymbol { v }$ 邻居节点 $N ( \nu )$ 并记录其邻居的标签集合L  
4for each 标签 $\iota$ in $\iota$ do  
5if $\mid N ^ { l } ( \nu ) \mid / s u m > \theta$ then  
6L是节点 $\boldsymbol { v }$ 所从属的一个社团  
7end if  
8end for  
9end for  
10 删除所有包含在大社团中的小社团  
11返回重叠社团集合 $c$

# 3 实验结果与分析

为验证AntCBO算法在求解重叠社区检测问题的准确度和分析性能，分别在合成网络和现实世界网络环境下进行对比实验实验，实验中以派系过滤算法（clusterpercolationmethod，CPM）和社区重叠传播算法（communityoverlappropagation algorithm，COPRA）作为AntCBO 的对比算法，通过实验对比算法在重叠社区检测准确度的优劣性。

对上述三种算法进行实验时，需要对算法参数进行设置，实验参数设置如下：CPM算法中，对于合成网络数据集， $k { = } 3$ ，对于真实世界数据集， $k$ 从3到10变化；COPRA算法中，对于合成网络数据集， $\scriptstyle \nu = 8$ ，对于真实世界数据集， $\nu$ 在1到9之间变化；而AntCBO的实验参数如表1所示。

Table1Parameters of antcbo algorithm   

<html><body><table><tr><td>描述</td><td>参数表示</td><td>值</td></tr><tr><td>最大迭代次数</td><td>T</td><td>500</td></tr><tr><td>初始化信息素值</td><td>T</td><td>8</td></tr><tr><td>信息素衰减</td><td>p</td><td>0.12</td></tr><tr><td>阈值</td><td>0</td><td>(0.08,0.5)</td></tr><tr><td>信息素增加</td><td>X</td><td>0.15</td></tr><tr><td>信息素阈值</td><td>b</td><td>20</td></tr></table></body></html>

# 3.1合成网络实验

合成网络实验通过广泛采用局部最大化（localfitnessraximization,LFR）基准来生成，可更好地实现节点数量和节点满足幂律分布，因此LFR更接近真实的社交网络。在实验中，本文通过LFR基准生成四个数据集，这些数据集的参数如表2所示。

表1AntCBO 算法的参数  
表2合成网络的参数  
Table 2Parameters of synthetic network   

<html><body><table><tr><td>数据集</td><td>节点数量</td><td>社团尺寸范围</td><td>μ</td><td>On</td><td>0m</td></tr><tr><td>1</td><td>1500</td><td>10~50</td><td>0.08</td><td>100</td><td>2~6</td></tr><tr><td>2</td><td>1500</td><td>10~50</td><td>0.32</td><td>100</td><td>2~6</td></tr><tr><td>3</td><td>4500</td><td>10~50</td><td>0.08</td><td>500</td><td>2~6</td></tr><tr><td>4</td><td>4500</td><td>10~50</td><td>0.32</td><td>500</td><td>2~6</td></tr></table></body></html>

# 3.2重叠社团识别准确度分析

合成网络实验中，采用扩展归一化互信息（normalizedmutualinformation，NMI）来对比三种方法对重叠社团识别的准确性。NMI可以表征检测到的分区和真实分区之间的相似性，其值在0\~1之间变化，且NMI值越高，分区结果越好。三个合成数据集上的三种算法的最佳NMI值如图1所示。对于分区 $C ^ { \prime }$ 和 $\boldsymbol { C ^ { \prime \prime } }$ ，NMI值由式(7)和(8)确定。

$$
N M I = 1 - { \frac { 1 } { 2 } } [ H ( X \mid Y ) + H ( Y \mid X ) ]
$$

$$
H ( X \mid Y ) = { \frac { 1 } { \left| C ^ { \prime } \right| } } \sum _ { k } { \frac { H ( X _ { k } \mid Y ) } { H ( X _ { k } ) } }
$$

其中： $X$ 、 $Y$ 表示分区 $C ^ { \prime }$ 和 $C ^ { \prime \prime }$ 相关联的随机变量； $H ( X | Y )$ 是节点属于 $Y$ 的前提下还属于 $X$ 的归一化条件熵，也可以以同样的方式定义为节点属于 $X$ 的前提下还属于 $Y$ 的归一化条件熵。

为验证算法的普适性，首先对比分析同一数据集下不同算法的重叠社团检测性能。从图1(a)\~(d)可以看出，对于不同的网络规模和不同的社区范围大小，成员数量 $O _ { m }$ 从2\~6变化时，本文所提AntCBO算法在LFR1、LFR2和LFR4数据集中的NMI值始终高于其他两种算法，而对于LFR3数据集而言，虽然在成员数量较小时NMI值低于CPM算法，但成员数量增大后其NMI值同样高于另外两种算法。这说明本文所提AntCBO算法对于成员数量较高时具有很强的检测性能，而低成员数量时虽性能有所下降但仍具有较高的辨识能力。

![](images/8f50c8731df601b5deb102be9a67e0165dc6f5b86c74c2bea7316882f216def1.jpg)

sets

为验证算法的健壮性并分析网络规模对重叠社团检测性能的影响，对比同一算法随网络规模增大时的检测性能。图$2 ( \mathrm { a } ) \mathrm { \sim } \mathrm { c } )$ 示出了三种算法在数据集LFR1\~LFR4下的NMI值变化情况。可以看出，随着成员数量的增多和网络规模的扩大，上述三种算法的NMI值均出现了不同程度的下降。从下降趋势来看，虽然AntCBO算法与COPRA算法的下降幅度相近（均在0.2左右)，但本文所提AntCBO算法在网络规模较大（即LFR4， $O _ { m } { = } 6$ 时其NMI指标仍比COPRA算法核CPM算法分别高 $3 0 . 9 \%$ 和 $8 3 . 3 \%$ ，从而说明本文所提AntCBO算法对于网络规模大、成员数量多的重叠社团检测具有更高的准确度。

![](images/75a172a34241b08912c1551d450d0c9f3f5760c695ad4e0eac84c65a1cf3030d.jpg)  
图2三种算法在LFR1\~LFR4上的 NMI值Fig.2NMI values of three algorithms onLFR1\~LFR4

# 3.3重叠社团检测数量分析

进一步分析本文所提AntCBO算法对重叠社团检出数量的性能。图3示出了不同算法下，检测出重叠社团数量与基准测试中标准社团数量的对比示意图。图3(a)\~(d)可以看出，虽然三种算法在网络规模较小且成员数量较少时均能较好地反映出重叠社团数量的真实值；但随着网络规模和成员数量增大时，相较于另外两种算法，本文所提AntCBO算法的结果与基准重叠社团数量更为接近。

![](images/5e4913f9d0edfd51f5b5dc64cdb23ed1d66e63d3da4336479ddefeb555a38b13.jpg)  
Fig.1Comparison of NMI values of three algorithms under 6 data   
图3在四个数据集上通过三种算法检测到的社区数量  
Fig. 3 Number of communities detected by 3 algorithms on four data sets

# 3.4重叠社团检测准确度分析

实验中为了方便地分析算法对网络重叠社团的识别准确度，定义函数Fscore用于测量检测重叠社团算法的准确性，它是准确率（precision）和召回率（recall）的调和平均值，其定义公式如式(9)所示。

$$
F s c o r e = \frac { 2 * p r e c i s i o n * r e c a l l } { p r e c i s i o n + r e c a l l }
$$

其中：precision是正确检测到的重叠节点的数量除以检测到的重叠节点的所有数量；recal被定义为正确检测到的重叠节点的数量除以重叠节点的真实数量所得到的值。

图4示出了同一数据集下不同检测算法对重叠社团的辨识准确度。从图中可以看出，本文所提AntCBO算法在LFR1和LFR2的检测准确度较好（即Fscore函数值更高)，故在网络规模较小时，本文所提AntCBO算法能够较准确地辨识出重叠社团；而当网络规模较大时（如LFR3和LFR4)，CPM算法的Fscore函数值相比于AntCBO算法和COPRA算法更高，说明其对重叠社团的检测更为准确。此外，从图4(a)\~(d)可以看出，本文所提AntCBO算法比COPRA的检测准确度均要好。结合3.1.1和3.1.2节分析，虽然CPM算法在网络规模较大和成员数量较多时的重叠社团检测准确率高，但本文所提AntCBO算法在重叠社团检测数量上更接近真实网络故总体而言，本文所提AntCBO算法性能强于另外两种算法。

# 3.5真实世界社交网络

本节讨论在真实世界社交网络中所提出的AntCBO算法对重叠社团的检测性能。相关参数如表3所示。由于真实世界网络的重叠社区结构未知，所以NMI值不能用于测量算法的性能，实验中采用 $\varrho _ { o \nu }$ 来评估算法性能。 $\varrho _ { o \nu }$ 的定义为重叠社区检测的经典模块性的扩展，它考虑了每个顶点所属的社区数量以及每个社区的成员资格程度， $\varrho _ { o \nu }$ 的值越高，说明算法分区越好。主要公式如式(10)\~(15)所示。

![](images/b1fef8f026e47d0eaaa9b464874b9c6dafdb30caa0fda325c7e4be49441187f4.jpg)  
图4基于LFR1\~LFR4 的重叠节点检测评估  
Fig.4Evaluation ofoverlapped node detection and based on LFR1\~LFR4

Table 3Digest ofreal world social networking   

<html><body><table><tr><td>数据集</td><td>节点数量</td><td>边数量</td><td>平均度</td><td>社团数量</td></tr><tr><td>Karate[13]</td><td>33</td><td>78</td><td>4.6</td><td>2</td></tr><tr><td>Dolphins[14]</td><td>60</td><td>160</td><td>5.2</td><td>2</td></tr><tr><td>Football[15]</td><td>116</td><td>615</td><td>10.8</td><td>12</td></tr></table></body></html>

$$
F \big ( \alpha _ { i , c } , \alpha _ { j , c } \big ) = \frac { 1 } { \big ( 1 + \mathbf { e } ^ { f \left( \alpha _ { i , c } \right) } \big ) \big ( 1 + \mathbf { e } ^ { - f \left( \alpha _ { j , c } \right) } \big ) }
$$

$$
\beta _ { l ( i , j ) , c } = F \big ( \alpha _ { i , c } , \alpha _ { j , c } \big )
$$

$$
\beta _ { l ( i , j ) , c } ^ { o u t } = \frac { \displaystyle \sum _ { j \in V } F \big ( \alpha _ { i . c } , \alpha _ { j . c } \big ) } { | V | }
$$

$$
\beta _ { l ( i , j ) , c } ^ { i n } = \frac { \displaystyle \sum _ { i \in V } F \big ( \alpha _ { i , c } , \alpha _ { j , c } \big ) } { | V | }
$$

$$
Q _ { o v } = \frac { 1 } { m } \sum _ { c } \sum _ { i , j \in V } \left[ \beta _ { l ( i , j ) , c } A _ { i j } - \begin{array} { c c c } { l ( i , j ) , c l ( i , j ) , c } & { k } \\ { \beta } & { \beta } & { \frac { o u t ~ i n } { m } } \\ { o u t } & { i n } & { m } \end{array} \right]
$$

根据实验结果， $\varrho _ { o \nu }$ 值的对比数据如表4所示。由表 4分析可得，AntCBO算法在karate、dolphins、football网络上的表现其优于COPRA和CPM。

表3真实世界社交网络参数  
表4真实世界网络中不同算法的 $\mathcal { Q } _ { o \nu }$ 值  
Table 4Values of $Q _ { o \nu }$ with different algorithms in real-world networks   

<html><body><table><tr><td>数据集</td><td>AntCBO</td><td>COPRA</td><td>CPM</td></tr><tr><td>Karate</td><td>0.73</td><td>0.52</td><td>0.53</td></tr><tr><td>Dolphins</td><td>0.73</td><td>0.70</td><td>0.67</td></tr><tr><td>Football</td><td>0.70</td><td>0.68</td><td>0.63</td></tr></table></body></html>

综上所述，对于大多数真实世界网络数据集，AntCBO算法可以获得比COPRA 和CPM更高的 $\varrho _ { o \nu }$ 值，这也说明

AntCBO算法相比于另两种算法具备更好的性能。

# 4 结束语

通过现有对重叠社区检测算法的研究，本文提出了一种基于蚁群的重叠群体检测算法。该算法包括参数初始化、蚂蚁的位置初始化、蚂蚁的移动和后期处理等阶段和步骤。以此同时，通过在合成和现实世界数据集上进行的实验分析，对算法所能实现的性能作了详细验证。实验结果表明，相对于CPM和COPRA，所提出的基于蚁群的重叠群体检测算法在社区检测质量方面具有良好的性能，对当前重叠社区检测问题的求解和网络中功能结构的理解具有重要的参考和借鉴意义。

# 参考文献：

[1]Wang Xiaofeng,Liu Gongshen,Li Jianhua.Overlapping community detection based on structural centrality in complex networks [J].IEEE Access,2017,10(5): 25258-25269.   
[2]Lyzinski V,Tang M,Athreya A,et al. Community detection and classification in hierarchical stochastic blockmodels [J].IEEE Trans on Network Science & Engineering,2017,4(1):13-26.   
[3] 黄宏程，熊忠阳，胡敏，等．节点移动状态感知的社会化延迟容忍网 络路由策略[J].计算机应用研究,2017,34(6):1825-1829.(Huang Hongcheng,Xiong Zhongyang,Hu Min,et al. Routing strategy based on change perception of node mobility characteristic in DTN [J]. Application Research of Computers,2017,34(6): 1825-1829.）   
[4] 侯林清，蔡英，范艳芳，等．移动社交网中基于兴趣社区的消息传输 方案[J].计算机科学,2018,45(6):105-110.(Hou Linqing,Cai Ying, Fan Yanfang,et al. Interest community based message transmission scheme in mobile social networks [J].Computer Science,2018,45 (6): 105-110. )   
[5] 陈东明，严燕斌，黄新宇，等．基于二分网络社团划分的推荐算法 [J]．东北大学学报：自然科学版，2018,39(8):1103-1107.(Chen Dongming，Yan Yanbing,Huang Xinyu，et al.Recommendation algorithm based on community detection in bipartite networks [J]. Journal of Northeastern University :Natural Science ，2018,39 (8): 1103-1107.)   
[6]Xie Jierui, Kelley S, Szymanski B K. Overlapping community detection in networks: the state of the art and comparative study [J].ACM Computing Surveys,2011,45 (4): 1-35.   
[7]孙韩林，马素刚，王忠民．一种基于差分进化的社团检测算法 [J]. 软件工程,2018,21(1):1-6.(Sun Hanlin,Ma Sugang,Wang Zhongmin, A community detection algorithm using differential evolution [J]. Software Engineering,2018,21(1):1-6.)   
[8] 孙韩林，马素刚，王忠民．一种基于群体智能的自组织重叠社团结 构分析算法[J].计算机应用研究,2019,36(5),doi:10.3969//j.issn. 1001-3695.2017.11.0733.(Sun Hanlin,Ma Sugang, Wang Zhongmin. Self-organizing overlapping community structure analysis algorithm based on swarm intelligence [J].Application Research of Computers, 2019,36 (5),doi: 10.3969/j. issn.1001-3695.2017.11.0733.)   
[9] 李鹏，李英乐，王凯，等．基于交互行为和连接分析的社交网络社团 检测[J].计算机科学,2017,44（7):197-202.(Li Peng,Li Yingle, Wang Kai,et al.Community detection based on user interaction and link analysis in social networks [J]. Computer Science,2017,44(7): 197-202.)   
[10]彭焱，溪利亚．局部优先的动态网络重叠社团及其演变模式检测 [J]．计算机工程，2016,42(12):188-195.(Peng Yanm Xi Liya. Local-first detection of overlapping community and its evolution pattern in dynamic networks [J].Computer Engineering,2016,42(12): 188-195.)   
[11]周旸，陈晓云，程建军，等．基于最优特征向量的谱二分社团检测方 法[J].计算机科学与探索，2017,11(12):1897-1906.(Zhou Yang, ChenXiaoyun，ChengJianjun， etal.Bisectionspectral community-detection methods using optimal eigenvectors [J]. Journal of Frontiers of Computer Science & Technology，20l7，11 (12): 1897-1906.)   
[12]邓承刚，李国徽，杨浩，等．基于指引因子蚂蚁算法的仿真资源分配 策略[J].华中科技大学学报:自然科学版，2015,1(9):1-6.(Deng Chenggang,Li Guohui, Yang Hao,et al. Simulation resource allocation strategy based on guidance factor ant algorithms [J].Journal of Huazhong University of Science and Technology :Nature Science Edition,2015,1(9):1-6.)   
[13]陆亿红，张振宁，杨雄．一种基于节点特征向量的复杂网络社团发 现算法[J].计算机科学,2017,44(6):419-423.(Lu Yihong,Zhang Zhenning,Yang Xiong. Community structure detection algorithm based on nodes'eigenvectors [J].Computer Science,2017,44 (6): 419-423.)   
[14]Allen SJ,PollockKH,BouchetPJ,et al.Preliminary estimates of the abundance and fidelity of dolphins associating with a demersal trawl fishery[J]. Scientific Reports,2017,7(1): 4995-5002.   
[15]王玉英，何汶坤，史加荣．基于社团密度的社团发现算法[J].计算 机应用研究,2017,34(7):1975-197.(Wang Yuying,He Wenkun,Shi Jiarong.Community detection algorithm based on community density [J].Application Research of Computers,2017,34(7):1975-197.)