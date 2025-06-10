# 基于图聚类与蚁群算法的社交网络聚类算法

叶小莺1，万 梅²，唐 蓉，谢 云¹，陈桂宏4，李强‘(1．广东东软学院 计算机科学与技术系，广东 佛山 528225；2.广州工商学院 计算机科学与工程系，广州 510850:3．重庆市九龙坡区精神卫生中心，重庆 400052;4．中山大学 电子与信息工程学院，广州 510006)

摘要：针对社交网络中社交关系的有向性与多样性，提出了一种基于图聚类与蚁群算法的社交网络聚类算法。首先，在网络覆盖率的约束下为社交网络建立有向、非全连接的二维图模型；然后，采用K-medoids算法搜索用户分组的中心用户，采用人工蚁群算法在2D 图中搜索各个用户与中心用户的相似性，将满足相似性阈值的用户分为同一个用户组。设计了低活跃用户的预测机制解决网络的稀疏性问题与冷启动问题。此外，通过网络覆盖率的约束条件权衡聚类准确率与覆盖率两个指标。仿真实验结果表明，该算法实现了较好的社交网络聚类性能，并且有效地缓解了稀疏性问题与冷启动问题。

关键词：社交网络；数据挖掘；聚类处理；人工蚁群优化；图聚类；信任信息中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2018.12.0881

# Clustering algorithm of social networks based on graph clustering and ant colony optimization algorithm

Ye Xiaoying1, Wan Mei², Tang Rong³, Xie Yun1, Chen Guihong4,Li Qiang1 (1.Dept.ofComputer Science&Technology,Neusoft InstituteofGuangdong,Foshan Guangdong 528225,China;2.Dept. ofComputer Science& Engineering,Guangzhou Collge of Technology&Business,Guangzhou 510850，China;3. Jiulongpo District Mental Health Center,Chongqing 40oo52,China;4.SchoolofElectronics &InformationTechnology, Sun Yat-sen University, Guangzhou 510006, China)

Abstract: Aiming at the properties of direction and diversityof social relationships in the social networks,this paper proposeda clustering algorithmof social networks based on graph clustering and ant colony optimization algorithm.Firstly, it constructed a directed and non fullyconnected complete graph for the social networks underconstraintcondition of network coverage;then,it adopted K-medoids algorithm to search the center users ofalluser groups,and itadopted ant colony ptimizationto search the similarities ofeach user andcenter users inthe graph,it grouped theusers satisfied the threshold condition into the same group.This paper also designed a prediction mechanism of low active degree users to resolve the sparsity problemand cold-startproblem,besides,the network coverageconstraint condition was setto balance theindexes of accuracy and coverage.Simulation experimentalresults indicate thatthe proposed algorithmrealizes a good clustering performance of social networks,and it reduces the problems of sparsity and cold-start effectively.

Key words: social networks; data mining;clustering proces;antcolony optimization;graphclustering;trust information

# 0 引言

随着微博、微信、豆瓣电影以及网易云音乐等各种应用的普及，导致不同领域的社交网络飞速地发展。目前的社交网络中存在多种社交关系，如好友关系、关注关系、具有相同喜好等[1]。社交网络的节点与连接也存在多样化的属性，传统的网络聚类方法主要考虑链接的稠密度，并未考虑社交网络的多样性。此外，社交网络中低活跃度用户的存在也为社交网络聚类效果带来了不利的影响[2]。

除了基于链接稠密度的社交网络聚类算法[3.4]，目前也出现了考虑节点多样性、强弱社交关系以及各种隐藏信息的聚类算法。文献[5]主要考虑用户的兴趣相似度，基于贝叶斯概率模型计算用户兴趣的相似度。在目前多样化的社交网络中，兴趣已经成为了一种弱关联信息，此外还应当考虑信任传播、评论信息、评分信息等。文献[6]提出了一种基于结构相似度的有向网络聚类算法，针对社交网络的有向交互性，该算法考虑了节点的到达邻居，并且采用有向边定义直接结构可达性。文献[7]采用粒子群优化算法对社交网络进行寻优处理，将网络结构作为粒子群的目标函数，通过贪婪策略引导粒子群的演化过程。文献[6,7]均将社交网络结构作为聚类的依据，但是在网络构建过程中仅考虑了直接的社交关系。

当前的社交网络中存在多样化的关联性，除了强关系，还应当考虑各种弱关系，包括关注关系、信任传播[8]、评论信息、评分信息等。此外，社交网络中存在活跃用户与低活跃度用户，而低活跃度用户会导致稀疏性问题，进而影响聚类的准确率与覆盖率[9]。为了解决上述问题，提出一种基于图聚类与蚁群算法的社交网络聚类算法(graphclustering andant colony optimization social networks clustering algorithm,GC-ACO)。在覆盖率的约束下建立二维图，从而保证覆盖率与聚类准确率两者之间的平衡。在图的构建过程中，考虑了直接信任关系、信任传播、评论信息等多样化信息。结合皮尔森相似性与多样化的社交关系，以期解决稀疏性问题，设计了低活跃度用户的预测机制，以期解决冷启动问题。在聚类阶段，通过ACO算法搜索与中心用户相似性最高的用户，提高聚类的准确率。

# 1 二维图模型

在覆盖率约束下建立二维图能够有效地缓解社交网络的稀疏性问题。相似性度量的效果高度依赖用户的评论信息，因此提高相似性度量的可靠性，能够提高聚类的可靠性与精度。

信任感知的社交网络通过预测低活跃用户的信息以提高聚类的准确率。基本思想是假设用户容易被其信任度高的用户所影响，但是该机制容易导致覆盖率降低。许多研究人员发现，用户不仅受直接信任用户影响，而且也会受间接用户的影响，但其影响力随着两个用户的距离增加而减少，该理论也称为信任传播。

设计了基于信任与相似性的图模型，该模型的建立算法如算法1所示。图的节点表示用户；边表示用户之间的连接；连接为双权重连接，表示为元组 $( W 1 , W 2 ) { = } ( p c c ( u , \nu ) , T ( u , \nu ) )$ 其中pcc表示相似性度量， $T$ 表示信任传播。算法的输入为直接信任信息、间接信任信息、皮尔逊相关系数(Pearsoncorrelationcoefficient,PCC)以及信任传播最大距离 $( M P )$ ，输出为社交网络的图。采用邻接矩阵表示社交图。根据用户之间的最短路径计算信任传播，setdif(函数取消已存在的新连接。第6行的系数1/i表示两个用户距离越长，其信任值越低。

算法1：社交网络的图建立算法

输入：PCC图，信任图，MP / $\ast _ { M P }$ 为信任传播最大距离\*/。  
输出： $w _ { - ^ { \sharp } }$ 0  
1.uers $\mathrel { \mathop : } =$ 用户数量；  
2.tmp=Iusersxusers; /\*初始化临时用户矩阵\*/  
3.mt=Ousersxusers; /\*初始化用户矩阵\*/  
4.foreach $\scriptstyle { i = 1 }$ to $M P$ do $\{$   
5. $t m p \ = \ t m p \ ^ { \ast } \ T ;$   
6. mt $\mathbf { \tau } = \mathbf { \tau }$ mt $+ ( 1 / { i } )$ setdiff(mt，tmp); /\*计算信任用户之  
间的差异\*/  
7.}  
8.foreach $( u _ { i } , \ u _ { j } )$ do $\{$ //遍历每对用户  
9. if $P C C ( u _ { i } , \ u _ { j } )$ 与 $M T ( u _ { i } , \ u _ { j } )$ 两者均存在 $\{ { \bf { \Phi } } / { ^ * }$ 同时存在PCC  
图与MT值\*/  
10. $\left( W _ { s } , \ W _ { m t } \right) \ = \ \left( \mathsf { P C C } ( u _ { i } , \ u _ { j } ) , \ \theta \right) ;$ （20  
11. $\}$ else if存在 $P C C ( u _ { i } , \ u _ { j } )$ {  
12. $\left( W _ { s } , W _ { m t } \right) = \left( P C C ( u _ { i } , u _ { j } ) , \Theta \right) ;$ （204号  
13. $\}$ else if存在 $M T ( u _ { i } , \ u _ { j } )$ {  
14. $( W _ { s } , W _ { m t } ) = ( \theta , M T ( u _ { i } , u _ { j } ) ) ;$   
15. ）  
16. ${ \cal W } _ { _ { - } \perp } ( u _ { i } , \ u _ { j } ) = ( W _ { s } , \ W _ { m t } ) ;$ （20  
17.}

图1所示是包含八个用户的社交网络实例。其中图 1(a)是PCC 相似性图；(b)是社交网络的直接信任关系图；(c)是社交网络的信任传播图；(d)是最终建立的图模型。从图1可看出，社交网络图可能不是一个全连接图，根据六度空间理论[10]，两个连接用户之间最长距离为六跳。将图1(a)、(b)、(c)三者组成图1(d)的图，该集成程序可能为孤立的分区建立连接，该程序有助于提高覆盖率。图中 $\mathrm { ~  ~ u ~ }$ 表示用户，图1(b)、(c)中边的值为两个用户之间的pcc值。图中 $u _ { 1 }$ 信任 $u _ { 3 }$ ， $u _ { 3 }$ 不信任 $\mathbf { \delta } _ { u 1 }$ ， $u _ { 1 } \to u _ { 3 }$ 的权重为 $( p c c ( u 1 , u 3 ) , T ( u 1 , u 3 ) ) { = } ( p c c ( u 1 , u 3 ) , 1 ) .$ 而 $u _ { 3 } \substack {  u _ { 1 } }$ 的权重为 $( p c c ~ ( u 3 , u 1 ) , 0 )$ ，因此图为有向图。

![](images/6995f6b9dddb26359512dd15cbee12d5100b5c8439c8f7a7c6e43475cd2f5c33.jpg)

(b)Direct trust relationship graph of social networks

![](images/4999e176d58890bdf95c59e5cd6745601ac097429c18a2baad272071794b076b.jpg)  
(b)社交网络的直接信任关系图  
图1包含八个用户的社交网络实例  
Fig.1Social networks example including eight users

# 2 蚁群算法的背景知识

人工蚁群算法(antcolony optimization,ACO)[l]是一种多agent系统，能够分布式地求解问题，并且具有较强的全局搜索能力与局部开发能力。蚁群算法首先将问题建模为一个加权图，然后搜索图中的最优路径。人工蚂蚁通过游走产生可行解，蚂蚁间互相交换信息，并且在边或者节点释放信息素。ACO中蚂蚁 $k$ 释放信息素的过程可定义为

$$
\tau _ { a b } = \left\{ { ( 1 - \rho ) \tau _ { a b } + \frac { Q } { L _ { k } } } , \right.
$$

其中： $\tau _ { a b }$ 为蚂蚁在边 $e _ { a b }$ 上释放的信息素； $\rho$ 为信息素的挥发系数； $L _ { k }$ 为蚂蚁 $k$ 搜索解的成本； $\varrho$ 为一个常量。为了防止ACO陷入局部最优，信息素应当随着时间挥发，从而提高探索新解的可能性。人工蚂蚁在游走过程中选择信息素较高的路径，蚂蚁 $k$ 从状态 $\mathbf { \Delta } _ { a }$ 变为状态 $b$ 的概率为

$$
p _ { a b } ^ { k } = \frac { \tau _ { a b } ^ { \alpha } \eta _ { a b } ^ { \beta } } { \sum _ { z \in a l l o w e d _ { \alpha } } \tau _ { a z } ^ { \alpha } \eta _ { a z } ^ { \beta } }
$$

其中： $\scriptstyle a$ 为控制 $\tau _ { a b }$ 影响力的参数； $\eta _ { a b }$ 为状态 $a$ 变为状态 $b$ 的可能性； $\beta$ 为控制 $\eta _ { a b }$ 影响力的参数。

# 3 本文的算法设计

# 3.1产生合适的用户分组数量

社交网络的覆盖率与分组数量没有相关性，因此，可将搜索出的第一个分组数量作为聚类算法的分组数。

# 3.2确定用户分组的中心用户

采用K-medoids算法[2]搜索用户分组的中心用户。K-medoids算法的目标函数 $( F )$ 定义为

$$
F { = } \operatorname* { m i n } \sum _ { c _ { E } \in C } \sum _ { m , n \in C _ { E } } d i s t ( m , n )
$$

其中： $C$ 为类的集合； $\boldsymbol { d i s t } ( \boldsymbol { m } , \boldsymbol { n } )$ 表示二维图中用户 $m$ 与 $n$ 的距离。因为图中每条边为双权重，所以用户间的距离计算为

$$
d i s t ^ { 2 } ( u , \nu ) = d _ { S } ^ { 2 } ( u , \nu ) + d _ { T } ^ { 2 } ( u , \nu )
$$

其中： $\boldsymbol { u }$ 与 $\nu$ 为两个目标用户； $d _ { S }$ 为相似性距离，计算方法为

$$
d _ { s } \left( u , \nu \right) = 1 - W _ { s } ^ { 2 D - G r a p h } \left( u , \nu \right)
$$

$d _ { T }$ 为信任距离，计算方法为

$$
d _ { T } ( u , \nu ) = 1 - W _ { M T } ^ { 2 D \_ G r a p h } ( u , \nu )
$$

# 3.3基于ACO 的社交网络聚类

3.2节选出了用户分组的中心用户，然后寻找与中心用户相似性高的用户组。该过程主要包括排列处理、加权处理、预测处理三个步骤。

# 3.3.1初始化排列处理

该步骤的目标是基于信任信息与评论信息计算各个用户与目标用户(中心用户)之间的相似性值，提取出top $\cdot n$ 的相似用户。如果用户之间存在直接信任关系，如好友关系、关注关系等，那么直接计算信任值；如果用户之间不存在直接信任关系，那么根据提取隐藏的信任关系，如评论信息、评分信息等。如果用户 $u$ 与目标用户 $\mathbf { \Delta } _ { a }$ 之间不存在直接的信任关系，使用PCC根据评论信息或者评分信息计算 $\boldsymbol { u }$ 与 $a$ 的信任值，网络的节点表示用户，边的权重表示用户之间的相似性。基于信任的用户相似性计算[13]为

$$
W _ { a , u } = \left\{ \begin{array} { l l } { \displaystyle \frac { 2 \times s i m ( a , u ) \times T _ { a , u } } { s i m ( a , u ) + T _ { a , u } } , ~ s i m ( a , u ) + T _ { a , u } \neq 0 } \\ { \quad } \\ { T _ { a , u } , \quad } \\ { s i m ( a , u ) , \quad } \end{array} \right.
$$

其中： $T _ { a , u }$ 为目标用户 $\mathbf { \Delta } _ { a }$ 与用户 $u$ 之间的信任值，计算式为

$$
T _ { a , u } = \frac { d _ { m a x } - d _ { a , u } + 1 } { d _ { m a x } }
$$

其中： $d _ { a , u }$ 表示 $\mathbf { \Delta } _ { a }$ 与 $u$ 之间的信任传播距离； $d _ { m a x }$ 为最大的信任传播距离， $d _ { m a x }$ 设为图中的平均路径长度。

$$
d _ { m a x } = { \frac { \ln ( n ) } { \ln ( k ) } }
$$

其中： $n$ 为网络中的用户数量; $k$ 为网络的平均度。假设 $s i m ( a ,$ $u )$ 表示 $a$ 与 $\boldsymbol { u }$ 的相似性，基于PCC的相似性计算为

$$
s i m ( a , u ) = \frac { \sum _ { i \in A _ { a , u } } \Bigl ( r _ { i } ( a ) - \overline { { r } } ( a ) \Bigr ) \Bigl ( r _ { i } ( u ) - \overline { { r } } ( u ) \Bigr ) } { \sqrt { \sum _ { i \in A _ { a , u } } \Bigl ( r _ { i } ( a ) - \overline { { r } } ( a ) \Bigr ) ^ { 2 } } \sqrt { \sum _ { i \in A _ { a , u } } \Bigl ( r _ { i } ( u ) - \overline { { r } } ( u ) \Bigr ) ^ { 2 } } }
$$

其中： $r _ { i } ( u )$ 为用户 $\boldsymbol { u }$ 对于项目 $i$ 的评分值； $\mathbf { \bar { \rho } } _ { r ( u ) } ^ { - }$ 为用户 $u$ 的平均评分值； $\mathbf { \nabla } _ { A _ { a , u } }$ 为用户 $\mathbf { \Omega } _ { a }$ 与 $\boldsymbol { u }$ 评分的项目集合。最终，将相似性高于阈值 $\theta$ 的分为一个用户组。

# 3.3.2二维图模型的加权处理

采用ACO处理top $\cdot n$ 用户，分析他们的重要性。首先，建立用户的二维图；然后，蚁群在图中游走以调节各个用户与目标用户的相似性。

# 1）建立用户二维图

首先，选择与目标用户top $\cdot n$ 相似的用户；然后，为社交网络建立第1章的二维图，其中节点表示用户，边与权重表示用户之间的相似性(式(7)计算)，权重的取值为[0.1]。图2(a)所示是一个社交网络的二维图例子；(b)所示是目标用户3的子图。启发式信息与期望信息是ACO算法的两个主要元素，启发式信息定义为反权重值。

![](images/faa13cf9de3d30b659ab192fc48c0faa3aab50676d52f6f8c22e40df62018266.jpg)  
(a）社交网络的二维图例子

(a) Two dimensional graph example of social networks

![](images/22d5e6bfffd93190c727143dc79164c22e462c0b199c824dca5d40f8d4ff6cad.jpg)  
Fig.2Example of sub-network of center user abstraction

2）蚁群游走策略

初始化阶段，将蚁群随机置于图中，然后蚁群在游走过程中更新信息素。蚂蚁根据用户与目标用户的相似性释放合适的信息素量，蚂蚁基于一个路由表在图中游走。蚂蚁 $k$ 从节点 $i$ 移至节点 $j$ 的概率定义为

$$
P _ { k } ( i , j ) = \left\{ \begin{array} { l l } { \left[ \tau _ { j } \right] ^ { \alpha } \left[ \eta _ { i j } \right] ^ { \beta } } & { i f ~ j \in N _ { i } ^ { k } \land \eta _ { i j } \le \Omega } \\ { \sum _ { m \in N _ { i } ^ { k } \land u n v i s t e d ( m ) } \left[ \tau _ { m } \right] ^ { \alpha } \left[ \eta _ { i m } \right] ^ { \beta } } & { i f ~ j \in N _ { i } ^ { k } \land \eta _ { i j } \le \Omega } \\ { 0 , } & { i f ~ j \not \in N _ { i } ^ { k } } \end{array} \right.
$$

其中： $N _ { i } ^ { k }$ 为节点 $i$ 的邻居集； $\boldsymbol { \tau }$ 为信息素量； $\eta$ 为启发值； $\alpha$ 与 $\beta$ 分别为控制 $\boldsymbol { \tau }$ 与 $\eta$ 权重的参数； $\eta _ { i j } { = } 1 / s i m ( u _ { i } , u _ { j } )$ ； $m$ 为尚未访问的用户。式(11)的概率函数能够防止算法陷入局部最

优，在社交网络中该函数能够选择与目标用户兴趣相似、冗余度低的用户集。

# 3）信息素更新方法

ACO中信息素反映了蚂蚁求解一个问题的经历，信息素的更新反映了蚂蚁的解质量。文中节点的信息素表示用户与目标用户的相关性，用户 $u _ { i }$ 信息素的更新方法为

$$
\tau _ { u _ { i } } = \tau _ { u _ { i } } + \sum _ { k } \Delta \tau _ { u _ { i } } ^ { k }
$$

其中： $\tau _ { u _ { i } }$ 为用户 $u _ { i }$ 的信息素； $\Delta \tau _ { u _ { i } } ^ { k }$ 表示蚂蚁 $k$ 在用户 $i$ 释放的信息素量。 $\Delta \tau _ { u _ { i } } ^ { k }$ 反映了解的质量，计算方法为

$$
\Delta \tau _ { u _ { i } } ^ { k } = \left\{ \begin{array} { l l } { \displaystyle { \frac { Q } { c o s t ( U ^ { k } ) } } , } & { u _ { i } \in U ^ { k } } \\ { 0 , } & { u _ { i } \notin U ^ { k } } \end{array} \right.
$$

其中： $\varrho$ 为常量； $U _ { k }$ 为蚂蚁 $k$ 经历的用户集； $c o s t ( U ^ { k } )$ 为蚂蚁$k$ 发现解的质量。每次迭代结束，更新所有节点的信息素：

$$
\tau _ { u _ { i } } = \tau _ { u _ { i } } ( 1 - \rho )
$$

其中： $\rho$ 为信息素的挥发速率。采用平均误差指标计算每个解的质量，每个解由一个用户集及其权重组成。

3.3.3低活跃用户的预测处理

对于缺少评论信息的用户，根据与其最相似的用户评论预测其对目标用户的评论。预测方法为

$$
\hat { r } _ { u , i } = \frac { \sum _ { \nu \in U } w _ { \nu } r _ { \nu , i } } { \sum _ { \nu \in U } w _ { \nu } }
$$

其中： $\hat { \boldsymbol { r } } _ { u , i }$ 为目标用户 $\mathbf { \Omega } _ { u }$ 对于项目 $i$ 的预测评论； $U$ 为蚂蚁 $k$ 选择的用户集； $r _ { \nu , i }$ 为 $\nu$ 对项目 $i$ 的真实评分； $w _ { \nu }$ 为 $\nu$ 的信息素。每个解的成本计算为预测值与真实值之间的误差。

$$
f i t n e s s ( u ) = \frac { \sum _ { i = 1 } ^ { I _ { u } } \left| \hat { \boldsymbol r } _ { u , i } - \boldsymbol r _ { u , i } \right| } { \left| I _ { u } \right| }
$$

其中： $I _ { u }$ 为预测的项目数量。

该处理的目标是根据活跃用户的信息预测低活跃用户的信息，该处理有助于缓解社交网络中普遍存在的冷启动问题、稀疏性问题等。

# 3.4算法总体设计

初始化阶段，每个节点的信息素设为常量 $\mathbf { \Psi } _ { c }$ ，蚁群随机置于图中各节点的位置。每个蚂蚁基于式(11)在图中游走，蚂蚁可能选择不同数量的用户集。蚂蚁根据(12)式更新各个用户的信息素。考虑信息素的挥发，在每次迭代的结束阶段根据式(14)进行信息素的全局更新。重复上述步骤，直至达到结束条件。将用户按重要性降序排列，选择top $\cdot k$ 的用户作为最终的子集。

算法2所示是GC-ACO算法的伪代码。算法的输入变量R、T、 $m$ 、 $N _ { a n t }$ 、NI分别表示评论信息(评分)、信任信息、用户数量、目标用户、蚁群规模、迭代次数。算法步骤如下：a)计算目标用户与其他用户的相似性，选择相似性高于 $\theta$ 的用户输入ACO算法处理；b)采用ACO为用户分配权重，ACO的每次迭代中，蚂蚁在图中游走，选择目标用户的一个相似用户集，步骤b)的输出是一个包含信息素值的用户集；c)通过预测程序提高低活跃用户的聚类效果与覆盖率。

算法2基于二维图与ACO的社交网络聚类算法输入：R，T，m，Nant，NI。输出：与目标用户相似的用户集。/\*基于评论信息与信任信息初步筛选用户\*/1.计算目标用户a与其他用户的相似性；//(1)式2.SU=选择相似性高于阈值0的用户集；

/\*采用ACO 计算用户的权重\*/  
3.建立用户的二维图；  
4.初始化图中节点的信息素；  
5.foreach $\textbf { i } = \textbf { 1 }$ to NI $\{$   
6. 随机分布蚁群；  
7. foreach ${ \dot { \textbf { j } } } = { \textbf { 1 } }$ to Nant{  
8. ${ \sf U } _ { \sf k } = [ ] ;$ （20  
9. while（如果当前用户的启发值低于阈值）{  
10. 选择下一个未访问的用户 $\mu$ ：//式(11)  
11. 将u加入向量 ${ \sf U } _ { \sf k }$ 中；  
12. }  
13. 计算适应度；//式(16)  
14. 更新信息素；//式(12)  
15. }  
16. 更新全局信息素；//式(14)  
17.}  
/\*低活跃用户的预测\*/  
18.基于信息素将用户降序排列;  
19.选择 top-k用户；  
20.预测a的未知评价；

# 3.5GC-ACO 算法的复杂度分析

算法2的步骤a)，因为每对用户之间的相似性依赖用户的总数量，所以计算复杂度为 ${ \mathrm { O } } ( n ^ { 2 } )$ ，第二行选择相似性高于$\theta$ 的用户，设为 $\scriptstyle { l = | S U | }$ ，建立包含 $l$ 个用户的二维图。步骤b），该步骤的迭代次数为 $N I$ ，其计算复杂度为 $\mathrm { O } ( N I \cdot N _ { a n t } \cdot l ^ { 2 } )$ ，如果采用分布式处理，那么该步骤的复杂度可降为 $\mathrm { O } ( N I ^ { \bullet } l ^ { 2 } )$ 。步骤c)，该步骤的计算复杂度为 $\mathrm { O } ( l \log { l } )$ 。最终，本算法的总体计算复杂度为 $\mathrm { O } ( n ^ { 2 } { + } N I \bullet l ^ { 2 } { + } l \log l )$ 。

# 4 实验与结果分析

推荐系统是社交网络聚类技术的一个重要应用场景，采用文献[5,14]的实验方案，将聚类技术与协同过滤推荐系统结合，通过推荐系统的效果评估社交网络推荐技术的效果。采用三个数据集测试GC-ACO算法的聚类性能。实验环境为PC 机，PC机的配置为8GB内存，i78700处理器。采用五折交叉检验的实验方案，将每个数据集分为五个子集，每次迭代中随机选择四个子集作为训练集，另外一个子集作为测试集。

# 4.1性能评价指标

采用三个经典的推荐系统性能指标，即均方误差(MAE)、根均方误差(RMSE)、覆盖率(RC)。MAE用于评估预测的准确率。MAE计算预测评分值与真实评分值之间的差异。

$$
\ M A E { = } \frac { 1 } { Z } \sum _ { ( u , j ) } \left| \hat { \boldsymbol { r } } _ { u j } - \boldsymbol { r } _ { u j } \right|
$$

其中：Z、 $\hat { r } _ { u j }$ 与 $r _ { u j }$ 分别为用户 $\boldsymbol { u }$ 对于项目 $j$ 的评分数量、估计评分数量以及真实评分数量。RMSE也是评估推荐系统性能的一个指标，该指标度量了预测评分与真实评分的绝对误差。

$$
R M S E { = } \sqrt { \frac { 1 } { Z } \sum _ { ( u , j ) } \left( \hat { r } _ { u j } - r _ { u j } \right) ^ { 2 } }
$$

RC从另一个角度评估推荐系统的性能，评估了推荐系统对长尾商品的挖掘能力。RC的计算方法为

$$
R C = \frac { \mathrm { \# } \mathbb { M } \mathrm { \# } [ \mathrm { \# } \mathrm { \Im } ] \mathrm { \# } \mathbb { F } _ { \mathrm { \# } } \mathbb { F } _ { \mathrm { \# } } \mathbb { F } _ { \mathrm { \# } } } { \mathrm { \# } \mathrm { \# } \mathrm { \# } \mathrm { \# } \mathrm { \# } \mathrm { \Im } ] \mathrm { \# } \mathrm { \# } }
$$

# 4.2实验数据集

采用三个数据集作为benchmarks数据集，分别为FilmTrust、Epinions、Ciao 数据集。FilmTrust是一个电影推荐网站的真实数据集，该网站的用户对电影进行评论与评分，用户之间也可添加好友并分享观点。FilmTrust数据集的评分为实数，范围为0.5\~4。Epinions 数据集包括多种社交关系，包括对项目的评论与评分以及用户之间的信任关系，评分为整数，范围为1\~5；信任关系为两个值：“1”表示信任，“0”表示不信任。Ciao数据集的评分为整数，范围为1\~5。三个benchmark数据集的相关信息如表1所示。

表1benchmark数据集的相关信息  

<html><body><table><tr><td>特征</td><td>FilmTrust</td><td>Epinions</td><td>Ciao</td></tr><tr><td>用户</td><td>1508</td><td>40163</td><td>30444</td></tr><tr><td>项目</td><td>2071</td><td>139738</td><td>72665</td></tr><tr><td>评分</td><td>35497</td><td>664824</td><td>1625480</td></tr><tr><td>信任者</td><td>609</td><td>33960</td><td>6792</td></tr><tr><td>受信任者</td><td>732</td><td>49288</td><td>7297</td></tr><tr><td>信任量</td><td>1853</td><td>487183</td><td>111781</td></tr></table></body></html>

为了测试本算法对稀疏性问题、冷启动问题的效果，按照两种条件进一步划分数据集，划分条件为：a)冷启动用户，提取评分数量少于5的用户集；b)稀疏性项目，提取评分数量少于5的项目；c全部用户集。表2所示是划分子数据集的相关信息。

表2划分子数据集的相关信息  
Table2 Related information of datasets division   

<html><body><table><tr><td>划分条件</td><td>数据集</td><td>实例数量</td><td>评分数量</td></tr><tr><td>冷启动</td><td>FilmTrust</td><td>281</td><td>608</td></tr><tr><td rowspan="5">稀疏性</td><td>Epinions</td><td>16910</td><td>33632</td></tr><tr><td>Ciao</td><td>12006</td><td>20985</td></tr><tr><td>FilmTrust</td><td>1653</td><td>3162</td></tr><tr><td>Epinions</td><td>116152</td><td>175906</td></tr><tr><td>Ciao</td><td>9423</td><td>24722</td></tr></table></body></html>

# 4.3参数设置

通过多组预处理实验选择出最优的参数配置：最大循环次数设为70，初始化信息素与信息素挥发系数分别设为0.02与0.2。参数 $\scriptstyle a$ 、 $\beta$ 、 $\Omega$ 分别设为 $\scriptstyle { a = 0 . 6 }$ 0 $\beta { = } 0 . 4$ + $\Omega { = } 1 . 6 6$ ，用户的邻居数量设为2\~30。蚁群的蚂蚁数量等于各个数据集的用户数量。

# 4.4实验结果

选择近期两个基于社交网络的推荐系统与一个基于智能优化的推荐系统作为对比算法，分别为：a)基于信任与用户评分的推荐系统TrustSVD[15]；b)基于信任与矩阵分解的推荐系统TrustMF[16]；c)基于遗传算法的推荐系统Yilmaz[17]。

# 4.5不同数据集的推荐性能

将TrustSVD、TrustMF、Yilmaz与GC-ACO四种算法对冷启动数据集、稀疏数据集以及完整数据集进行了推荐实验，统计每组实验的MAE与RMSE指标的结果，表3\~5分别是FilmTrust、Epinions与Ciao 数据集的实验结果。GC-ACO算法对于FilmTrust、Epinions 两个数据集的准确率较好，优于其他三个推荐系统。对于Ciao 数据集也取得了较好的结果，但其对完整数据集的推荐准确率略低于TrustMF系统，对稀疏数据集的推荐准确率略低于TrustSVD系统。总体而言，GC-ACO取得了较好的推荐效果，对于冷启动问题与稀疏性问题均实现了加好的缓解效果。

表3推荐系统对于FilmTrust数据集的 MAE与RMSE 结果.able 3 MAE and RMSE results of recommender systems applied to  

<html><body><table><tr><td colspan="6">filmtrust dataset</td></tr><tr><td>数据集</td><td>指标</td><td>TrustSVD</td><td>TrustMF</td><td>Yilmaz</td><td>GC-ACO</td></tr><tr><td>冷启动</td><td>MAE</td><td>0.650</td><td>0.619</td><td>0.722</td><td>0.586</td></tr><tr><td rowspan="3">稀疏集</td><td>RMSE</td><td>0.845</td><td>0.882</td><td>0.931</td><td>0.758</td></tr><tr><td>MAE</td><td>0.829</td><td>0.907</td><td>0.841</td><td>0.793</td></tr><tr><td>RMSE</td><td>1.059</td><td>1.249</td><td>1.084</td><td>1.003</td></tr><tr><td rowspan="2">完整集</td><td>MAE</td><td>0.607</td><td>0.721</td><td>0.685</td><td>0.496</td></tr><tr><td>RMSE</td><td>0.787</td><td>0.919</td><td>0.912</td><td>0.721</td></tr></table></body></html>

表4推荐系统对于Epinions 数据集的MAE与RMSE结果

Table 1 Related information of benchmark datasets   
Table 4 MAE and RMSE results of recommender systems applied to   

<html><body><table><tr><td colspan="6">Epinions dataset</td></tr><tr><td>数据集</td><td>指标</td><td>TrustSVD</td><td>TrustMF</td><td>Yilmaz</td><td>GC-ACO</td></tr><tr><td>冷启动</td><td>MAE</td><td>0.861</td><td>0.934</td><td>0.871</td><td>0.795</td></tr><tr><td rowspan="2">稀疏集</td><td>RMSE</td><td>1.117</td><td>1.373</td><td>1.124</td><td>1.026</td></tr><tr><td>MAE</td><td>0.829</td><td>0.856</td><td>0.824</td><td>0.801</td></tr><tr><td rowspan="2">完整集</td><td>RMSE</td><td>1.096</td><td>1.19</td><td>1.082</td><td>1.033</td></tr><tr><td>MAE</td><td>0.834</td><td>0.877</td><td>0.852</td><td>0.769</td></tr><tr><td></td><td>RMSE</td><td>1.094</td><td>1.184</td><td>1.101</td><td>1.021</td></tr></table></body></html>

表5推荐系统对于Ciao数据集的MAE与RMSE结果

[able 5 MAE and RMSE results of recommender systems applied tc   

<html><body><table><tr><td colspan="6">Ciaodataset</td></tr><tr><td>数据集</td><td>指标</td><td>TrustSVD</td><td>TrustMF</td><td>Yilmaz</td><td>GC-ACO</td></tr><tr><td>冷启动</td><td>MAE</td><td>0.725</td><td>1.073</td><td>0.747</td><td>0.688</td></tr><tr><td rowspan="2">稀疏集</td><td>RMSE</td><td>0.939</td><td>1.311</td><td>0.932</td><td>0.903</td></tr><tr><td>MAE</td><td>0.503</td><td>1.209</td><td>0.532</td><td>0.516</td></tr><tr><td rowspan="2">完整集</td><td>RMSE</td><td>0.659</td><td>1.493</td><td>0.675</td><td>0.632</td></tr><tr><td>MAE</td><td>0.723</td><td>0.505</td><td>0.491</td><td>0.503</td></tr><tr><td></td><td>RMSE</td><td>0.955</td><td>0.493</td><td>0.670</td><td>0.659</td></tr></table></body></html>

覆盖率指标是推荐系统与社交网络的重要指标，统计了四个推荐系统的覆盖率结果，结果如图3所示。从图中可看出，四种算法均实现了较高的覆盖率，TrustMF、Yilmaz与GC-ACO三个推荐系统的覆盖率均高于0.9，而本算法的覆盖率则略高于TrustMF与Yilmaz 算法。

图3不同推荐系统的覆盖率结果  
![](images/8f685a006f3d0630f1ed00515cb882831337a9d521e270d96f47f6d9db614258.jpg)  
Fig.3Coverage rate results of different recommender systems

# 4.6 收敛性分析

TrustSVD与TrustMF并非基于迭代的算法，Yilmaz系统基于遗传算法算法实现，将本算法与Yilmaz算法比较，观察本算法的收敛性。本算法是一种基于迭代的算法，收敛性是迭代性算法的关键性能。Yilmaz是一种基于遗传算法的推荐系统，将本算法与Yilmaz 算法进行比较，两种算法对于

FilmTrust、Epinions与Ciao数据集的收敛曲线分别如图4(a)\~(c)所示。从图中可看出，本算法的收敛速度与准确率结果均优于Yilmaz算法。本算法的全局搜索能力较强，实现了较好的准确率，局部开发能力较强，实现了较快的收敛速度。式(11)的概率函数防止蚁群算法陷入局部最优，从而实现了较强的全局搜索能力；式(11)未使用贪婪机制，使得低概率用户依然具有被选择的可能性。另外，第一步对用户进行了初步筛选，使得本算法保持了较高的开发能力，并且缩小了解空间。本算法采用了丰富的直接信任关系与间接信任关系建立图中的权重，该机制使蚁群在迭代初期即可快速、高效地在图中游走，因此本算法实现了较好的开发能力与收敛速度。

![](images/4a0b1f7e4b2d15187e0f20bb4d52ef1111b191a955dde404cdb00eb2eea67078.jpg)  
Fig.4Coverage curves of two iteration based recommender systems

# 5 结束语

针对社交网络中社交关系的有向性与多样性，本文提出了一种基于图聚类与蚁群算法的社交网络聚类算法。在覆盖率的约束下建立二维图，从而保证覆盖率与聚类准确率两者之间的平衡。在图的构建过程中，考虑了直接信任关系、信任传播、评论信息等多样化信息。本算法取得了较好的推荐效果，对于冷启动问题与稀疏性问题均实现了较好的缓解效果。本算法采用了丰富的直接信任关系与间接信任关系建立图中的权重，该机制使蚁群在迭代初期即可快速、高效地在图中游走，因此本算法实现了较好的开发能力与收敛速度。未来将考虑引入更多的隐藏社交信息与外部信息以增强社交网络的判断依据，如用户档案、评论上下文以及行为轨迹等信息。

# 参考文献：

[1]胡长军，许文文，胡颖，等．在线社交网络信息传播研究综述[J]. 电子与信息学报,2017,39(4):794-804.(Hu Changjun,Xu Wenwen, Hu Ying，et al.Review of information diffusion in online social networks [J]. Journal of Electronics & Information Technology, 2017, 39 (4): 794-804.)   
[2] 赵妹，刘晓曼，段震，等．社交关系挖掘研究综述[J].计算机学报， 2017,40 (3): 535-555.(Zhao Shu,Liu Xiaoman,Duan Zhen,et al.A survey on social ties mining [J]. Chinese Journal of Computers,2017, 40 (3): 535-555.)   
[3]Stovall T R,Kockara S,Avci R.GPUSCAN:GPU-based parallel structural clustering algorithm for networks[J].IEEE Trans on Parallel & Distributed Systems,2015,26 (12):3381-3393.   
[4] Zhao Weizhong,Chen Gang,Xu Xiaowei. AnySCAN:an efficient anytime framework with active learning for large-scale network clustering [C]//Proc of IEEE International Conference on Data Mining. Washington DC: IEEE Computer Society, 2017: 665-674.   
[5] 汤颖，钟南江，孙康高，等．基于兴趣的社交网络用户聚类及可视化 [J]．计算机科学，2017，44（b11):385-390.（Tang Ying，Zhong Nanjiang,Sun Kanggao,et al. Clustering and visualization of social network based on user interests [J]. Computer Science,2017,44 (b11): 385-390.)   
[6]陈季梦，陈佳俊，刘杰，等．基于结构相似度的大规模社交网络聚类 算法[J]．电子与信息学报，2015,37(2):449-454.(Chen Jimeng, Chen Jiajun,Liu Jie,et al. Clustering algorithms for large-scale social networks based on structural similarity [J].Journal of Electronics & Information Technology,2015,37 (2): 449-454.)   
[7]Cai Qing,Gong Maoguo,Ma Lijia,et al.Greedy discrete particle swarm optimization for large-scale social network clustering [J]. Information Sciences An International Journal,2015,316(9): 503-516.   
[8]Wu Jian,Chiclana Francisco,Fujita Hamido,et al.A visual interaction consensus model for social network group decision making with trust propagation [J].Knowledge-Based Systems,2017,122 (C): 39-50.   
[9]孟祥武，刘树栋，张玉洁，等．社会化推荐系统研究[J].软件学报， 2015,26(6):1356-1372.(Meng Xiangwu,Liu Shudong, Zhang Yujie, et al. Research on social recommender systems [J]. Journal of Software, 2015,26(6):1356-1372.)   
[10]刘宏杰，陆浩，张楠，等．基于微博的六度空间理论研究[J].计算 机应用研究,2012,29(8):2826-2829.(Liu Hongjie,Lu Hao, Zhang Nan,et al. Theory research based on microblog of six degrees space [J]. Application Research of Computers,2012,29 (8): 2826-2829.)   
[11] Eaton Jayne,Yang Shengxiang，Mavrovouniotis M.Ant colony optimization with immigrants schemes for the dynamic railway junction rescheduling problem with multiple delays [J]. Soft Computing,2016, 20 (8):2951-2966.   
[12]韩啸，刘淑芬，徐天琦．基于遗传模拟退火算法的改进K-medoids算 法[J].吉林大学学报：工学版,2015,45(2):619-623.(Han Xiao, Liu Shufen,Xu Tianqi. Improved K-medoids algorithm based on genetic simulated annealing algorithm [J]. Journal of Jilin University ： Engineering and Technology Edition,2015,45(2):619-623.)   
[13]Moradi P,Ahmadian S.A reliability-based recommendation method to improve trust-aware recommender systems [J].Expert Systems with Applications,2015,42 (21): 7386-7398.   
[14]陈克寒，韩盼盼，吴健．基于用户聚类的异构社交网络推荐算法[J]. 计算机学报,2013,36(2):349-359.(Chen Kehan,Han Panpan，Wu Jian.User clustering based social network recommendation[J].Chinese JournalofComputers,2013,36(2):349-359.)   
[15] Guo Ging，Zhang Jie,Yorke-Smith Neil．TrustSVD:collaborative filtering with both the explicit and implicit influence of user trust and of item ratings [C]// Proc of the 29th AAAI Conference on Artificial Intelligence.Palo Alto:AAAIPress,2015:123-129.   
[16] Yang Bo,Lei Yu,Liu Jiming,et al. Social collaborative filtering by trust[J].IEEE Trans on Pattern Analysis& Machine Intelligence,2017, 39 (8): 1633-1647.   
[17] Ar Y,Bostanci E.A genetic algorithm solution to the collaborative filtering problem [J].Expert Systems with Applications,2016,61(1): 122-128.