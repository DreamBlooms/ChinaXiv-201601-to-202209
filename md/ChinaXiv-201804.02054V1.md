# 不同链接下非对称相依网络的级联失效研究

完颜娟，韩华(武汉理工大学 理学院，武汉 430070)

摘要：现实中存在对称性和非对称性的相依网络，目前在研究相依网络级联失效时选择的对象主要为对称相依网络，为了综合分析相依网络的鲁棒性，针对非对称相依网络的级联失效问题进行了研究，首先利用典型BA无标度网络和WS 小世界网络构建了非对称双层相依网络的级联失效模型，之后在随机攻击和蓄意攻击条件下，分别研究构建的网络模型的相依程度、相依模式以及子网络的拓扑结构对网络故障的影响。仿真结果表明，无论是何种程度相依的非对称相依网络，在随机攻击下，度正相关相依网络都表现出弱鲁棒性，而在蓄意攻击下，度负相关相依网络表现出弱鲁棒性，且网络的拓扑结构对网络的级联失效有影响。

关键词：非对称；相依网络鲁棒性；级联失效 中图分类号：TP393.02 doi:10.3969/j.issn.1001-3695.2017.11.0785

# Cascading failures of asymmetric dependent networks under different links

WanyanJuan,HanHua (CollegeofScience,WuhanUniversityof Technology Hubei 43oo70,China)

Abstract: In reality, therearesymmetry interdependent network and asymmetry interdependent network.At present,the cascading failuresofsymmetricinterdependent networks are mainlystudied.Inordertomakeacomprehensiveanalysis ofthe robustnessof the interdependent networks,this paper studied thecascading failure ofasymmetric interdependent networks. Firstly,itconstructedacascaded failure modelofasymmetricdouble layer interdependent networks usingatypicalBAscalefree networkanda WSsmallworld network.Then,undertheconditionofrandomattckanddeliberateattack,itstudied the dependence of network models,dependency paterns and the topologyof sub networks on network failures.The simulation resultsshowthattheasymmetricdependentnetworkisdpendentregadlessoftheextenttohich,inarandomattck,positively relatedtodegreeofdependencynetworks exhibit strongrobustess,whileindeliberateattack,treediferentcorrelationshows thesame robustness ofinterdependent networks.Moreover,the topologyoftheatack network affectscascading failures ofthe network.

Key words:asymmetry; dependent network robustness;cascading failure

# 0 引言

自从小世界网络[1和无标度网络[2]在二十世纪末被提出以来，针对复杂网络的研究正在逐渐深入，这些研究包括网络的构建[3.4]、网络的级联失效[5.6]以及网络的优化[7\~II]。其中，网络的级联失效是复杂网络的一个核心问题，通过研究网络的级联失效能够揭示系统崩溃的条件及规律、找出预防的方法，进而使生活中的网络系统更加稳定。

考虑到实际网络的复杂性以及为了理论的简单，目前在研究实际网络或模拟网络时选择的对象大都是孤立的系统，但现实中不同基础网络之间的相互作用不容忽视，比如，在2003 年意大利电网的一个事故中，一个发电站的毁坏导致一部分计算机网络发生瘫痪，导致计算机网络失去了对电网的控制能力，进一步导致部分发电站停止工作，最终对城市的正常运行产生了较大的损害[I]。由这个案例可以看出，现实生活中许多系统之间都不是孤立的，而是相互依存的。Buldyrew 等人[12]在2010年理论性地提出了双层节点一对一相依网络级联故障模型，由此人们开始真正关注到两个或两个以上相互依存网络的级联故障。相互依存网络的一个基本特征是一个网络中的节点或者边发生故障时可能会导致其他与之相依的网络中的节点或边发生故障，这种过程会循环递归地发生，并导致一连串的失败，即一个网络中很小一部分节点的故障可能导致多个相互依存的网络系统的完全碎片化。

目前在研究相依网络的级联失效问题时，研究手段主要为通过对比分析在不同攻击模式下构建的相依网络级联失效过程，研究相依网络的鲁棒性。文献[13]研究了不同拓扑构建的相依网络的鲁棒性，发现两个或者两个以上网络之间的相互依存关系会随着相依复杂性增加使得这种失效的风险增加，因此，研究不同拓扑构建下的相依网络系统的鲁棒性是必要的；文献[12]运用渗流理论研究了不同攻击模式下相依网络的鲁棒性，探讨了拥有集团化的耦合网络的鲁棒性，发现在遭受随机攻击时，与没有集团化的耦合网络相比，拥有集团化的耦合网络更容易表现出网络的脆弱性，但现实中的网络系统也会遭遇恶意袭击，如恐怖活动、计算机病毒入侵等，因此，为了解现实中网络的鲁棒性，有必要研究不同攻击策略下相依网络的级联故障，进而可以提出相应的防护措施，以提高网络的鲁棒性；文献[13]引入一个数学框架研究了不同蓄意攻击下相依网络的鲁棒性，分别对双层一对一相依网络模型在度大节点的蓄意攻击以及度小节点的蓄意攻击下的级联失效，发现对于两个无标度网络构成的相依网络很难制定合适的保护策略，因此研究由不同类型子网络构成的相依网络的鲁棒性是有必要的。文献[14]对不同子网络构成的相依网络的鲁棒性进行了研究，对无标度网络和小世界网络组成的不同类型相依网络在同配、异配、随机三种不同的耦合方式下添加负载，研究了负载容量以及失效后容量的重分配情况，发现网络间不同耦合模式对网络关键阈值没有影响，但是不同的网络结构以及网络间不同的耦合模式对网络的鲁棒性有一定的影响。文献[15]研究了相依网络的鲁棒性能与相依节点比例和相依冗余度的关系，发现网络的鲁棒性随着相依节点比例增加而减弱，随着相依冗余度的增加而增强。为了简化模型，大多数的学者忽略了相依节点比例和相依冗余度的不同对网络的鲁棒性产生的影响。

可以看出，目前在研究相依网络级联失效时选择的对象主要为对称相依网络，但现实生活中存在具有非对称性的相依网络。目前的研究主要集中在随机相依模式的非对称相依网络：文献[16]基于BA、WS、ER等三种基本网络模型，建立了随机非对称的相依网络模型，研究了非对称相依网络的鲁棒性与耦合强度之间的关系。文献[17]根据复杂网络理论构建了军事系统中的C2网和传感器网络的随机非对称相依作战网络模型，对连边受到蓄意攻击时的级联抗毁性进行分析。然而，上述文献均没有综合考虑不同攻击策略下不同的相依模式以及子网络异构对网络鲁棒性的影响。为了综合分析相依网络的鲁棒性，文中构建了不同类型的非对称相依网络，通过分析蓄意攻击和随机攻击下构建的不同网络的级联失效过程，研究了非对称相依网络鲁棒性。结果表明，蓄意攻击方式下，同配网络表现出弱鲁棒性，随机攻击方式下，异配网络则表现出弱鲁棒性。

# 1 非对称相依网络的构建及级联失效模型

自从2003年意大利发生电站事故，人们开始意识到两个及两个以上网络构成的相依网络的重要性。如基础设施中的电力通信网，军事系统中的指挥控制网等网络均因为子网络节点不同、相依比例不同或者子网络拓扑结构不同造成相依的不对称。在构建相依网络时，首先建立多个分别独立代表某种拓扑结构系统的网络，之后通过边体现各独立网络之间的相依关系，其中，将一个网络里的节点和另外一个网络中的节点用边联系起来。

相依网络系统可以定义为一个二元组 $G = \left\{ V , E \right\}$ 。集合$V = \{ V _ { 1 } , V _ { 2 } , \cdots , V _ { n } \}$ 是各个独立网络的节点集的集合，其中，$V _ { k } = \{ V _ { k 1 } , V _ { k 2 } , \cdots , V _ { k n } \}$ 表示第 $\mathbf { k }$ 个独立系统中的节点集。集合$E = \{ E _ { 1 , 1 } , E _ { 1 , 2 } , \cdots , E _ { k , l } , \cdots , E _ { n , n } \}$ 为边集的集合，其中, $E _ { k , k }$ 表示一个孤立的网络节点之间的边，称为连接边。当 $k \neq l$ 时， $E _ { k , 1 }$ 表示两个网络之间具有相依关系的边，把两个网络之间对应的节点连接起来，称为相依边。

从相依模式上相依关系可以分为两种，一种是与节点之间的度相关的，另一种是与节点之间的度不相关的，其中度相关关系又可以分为正相关和负相关。另一方面，从相依程度上相依关系也可以分为两种，一种是节点一对一相依，另一种是节点一对多的多重相依。考虑到上述多种相依关系，分别构建与节点度相关的一对一和一对多非对称相依网络以及与节点度无关的一对一和一对多相依网络。

# 1.1非对称相依网络模型

目前在研究相依网络鲁棒性时，研究对象多为随机相依方式构成的一对一对称相依网络，较少研究其他建网方式构成的相依网络，文中在前人的基础上构建了同配、异配、随机[12]三种建网方式下的一对一和一对多的非对称相依网络模型。

假设在具有 $N$ 个节点数的网络A和具有RN个节点数的网络B之间建立 $r N ( r \leq R )$ 条相依边，非对称比例记为 $R$ 。相依网络的构建过程如下：

a)计算 $A$ 网络中每个节点的内部度，并将其从小到大依次排序,记为一个 $\mathrm { ~ N ~ }$ 维向量 $\boldsymbol { A 1 }$ ，其中 $k _ { \scriptscriptstyle A 1 1 } \leq k _ { \scriptscriptstyle A 1 2 } \leq , \cdots , \leq k _ { \scriptscriptstyle A 1 N - 1 } \leq k _ { \scriptscriptstyle A 1 N }$ 其中 $k _ { A 1 i }$ 表示 $\boldsymbol { A 1 }$ 中节点Ali 的度，如果 $k _ { _ { A 1 i } } = k _ { _ { A 1 j } }$ ，即节点Ali和节点 $A 1 j$ 有相同的度，则两个节点随机进行排序。

b)将子网络 $B$ 中的每个节点进行排序并分为 $N$ 层，记为$B 2$ 。首先将 $B$ 网络中的每个节点按照内部度从小到大的顺序进行排序，并记为一个 $2 N$ 维向量 $B 1$ ，$k _ { _ { B 1 1 } } \leq k _ { _ { B 1 2 } } \leq , \cdots , k _ { _ { B 1 2 N - 1 } } \leq k _ { _ { B 1 2 N } }$ ，其中， $k _ { B 1 i }$ 代表 $B 1$ 中的节点Bli 的度，如果 $k _ { _ { B 1 i } } = k _ { _ { B 1 j } }$ ，则将 $B 1 i$ 和 $B 1 j$ 随机进行排序。然后$R$ 个节点分为一组将 $B$ 网络分为 $N$ 组分别为 $B 2 1 , B 2 2 , \cdots , B 2 N$ 。

c)将 $A$ 网络中的 $\mathbf { \nabla } _ { A 1 i }$ 节点和 $B$ 网络中 $B 2 j$ 节点进行一对一相依或者一对多相依，采用的相依方式有如下三种：

(a)基于度的正相关相依模式(AL)。 $A$ 网络中度大的节点和$B$ 网络中度大的节点之间建立相依关系， $A$ 网络中度小的节点和 $B$ 网络中度小的节点之间建立相依关系，即$A 1 1  B 2 1 , A 1 2  B 2 2 , \cdots ,  A 1 N  B 2 N$ ：

(b)基于度的负相关相依模式(DL)。 $A$ 网络中度大的节点和B 网络中度小的节点之间建立相依关系， $A$ 网络中度小的节点和B网络中度大的节点之间建立相依关系即$A 1 1  B 1 N , A 1 2  B 1 N - 1 , \cdots ,  A 1 N  B 1 1$

(c)随机模式(RL)。随机选择 $A$ 网络中的一个节点和 $B$ 网络中的一个节点建立相依关系。

按照相依程度构建相依网络又分为完全相依和不完全相依。其中完全相依是 $A$ 网络的一个节点和 $B$ 网络对应层次中 $R$ 个节点相依，不完全相依是 $A$ 网络的中的一个节点和 $B$ 网络中 $\boldsymbol { r }$ $\left( r < R \right)$ 个节点相依，随机选取 $B$ 网络对应层次中的 $\boldsymbol { r }$ 个节点相依。

# 1.2非对称相依网络级联失效模型

图1中的网络模型是具有不同节点数的子网络 $A$ 和子网络$B$ 构成的相依网络，其中子网络 $A$ 的节点用 $\{ A 1 , A 2 , \cdots , A 5 \}$ 表示，子网络 $B$ 的节点用 $\{ B 1 , B 2 , \cdots , B 1 0 \}$ 表示。节点的失效在单个网络内的表现为当一个节点受到攻击而失效时，与之相连的边全部都失效。将这个网络分为多个独立连通块，由渗流理论可以得到属于最大连通块的节点保持正常的功能，不属于最大连通图的节点失效。级联失效在网络间的表现为子网络 $A$ 中的节点失效，如果网络 $B$ 中部分与之相依的节点失去了全部的相依节点，则网络 $B$ 中此节点失效，同时 $B$ 网络被分为多个独立连通块，同理，根据渗流理论， $B$ 中不属于极大连通图中的节点失效，由于存在的相依关系的作用又将导致相依边的失效，造成 $A$ 网络的相依节点减少， $A$ 网络中部分节点因为失去全部的相依边，又将 $A$ 网络分为多个独立块，级联在 $A$ 网络和 $B$ 网络之间循环，经过一定的失效过程， $A$ 网络和 $B$ 网络之间没有节点再失效则整个级联失效结束，网络达到一定的稳定状态。

![](images/572ae31b58137c3619cb2121ee2915b80c86909426dafed0a15cbfb14fb3d46d.jpg)  
图1相依网络级联失效模型

在图1中，子网络 $A$ 中的节点A5受到攻击被移除，A5失效，此时，无论是内部边或者相依边均会发生失效。第一阶段， $A$ 网络内部边的失效导致 $A$ 网络分为两个连通块 $a _ { 1 1 } 、 a _ { 1 2 }$ ，而相依边的失效导致B9、 $B 1 0$ 失效；第二阶段， $B$ 网

络由于部分节点的失效分为五个连通块 $b _ { 2 1 }$ 、 $b _ { 2 2 } \ 、 b _ { 2 3 } 、 b _ { 2 4 }$ 、$b _ { 2 5 }$ 。根据渗流理论，不属于最大联通块 $b _ { 2 1 }$ 、 $b _ { 2 2 }$ 、 $b _ { 2 3 }$ 、 $b _ { 2 4 }$ 的节点B4、B5、B6、B7、B8由于脱离最大连通片而失效，B5、B6的失效又导致A3失效，至此整个相依网络剩余的节点不会发生失效，达到一个稳定的状态。

代数学角度来看，当攻击 $A$ 网络比例为的节点时 $P _ { \mathrm { { A } } }$ 和 $P _ { \scriptscriptstyle B }$ 代表存在的节点属于最大连通图的概率则级联失效具体过程如下：

$$
\mu 1 ^ { \ast } = 1 - p , \mu 1 { = } \mu 1 ^ { \prime } P _ { _ A } ( \mu 1 ^ { \prime } )
$$

$$
\sigma 1 ^ { \prime } = ( 1 - p ) P _ { \scriptscriptstyle A } ( \mu 1 ^ { \prime } ) , \sigma { = } \sigma 1 ^ { \prime } P _ { \scriptscriptstyle B } ( \sigma 1 ^ { \prime } )
$$

$$
\mu 2 ^ { \prime } = ( 1 - p ) P _ { _ B } ( \sigma 1 ^ { \prime } ) , \mu { = } \mu 2 ^ { \prime } P _ { _ A } ( \mu 2 ^ { \prime } )
$$

$$
\sigma 2 ^ { \prime } = ( 1 - p ) P _ { _ { A } } ( \mu 2 ^ { \prime } ) , \sigma { = } \sigma 2 ^ { \prime } P _ { _ B } ( \sigma 2 ^ { \prime } )
$$

$$
\mu n ^ { \prime } = ( 1 - p ) P _ { _ B } ( \sigma ( n - 1 ) ^ { \prime } ) , \mu n = \mu n ^ { \prime } P _ { _ A } ( \mu n ^ { \prime } )
$$

$$
\sigma n ^ { \prime } = ( 1 - p ) P _ { _ A } ( \mu n ^ { \prime } ) , \sigma n = \sigma n ^ { \prime } P _ { _ B } ( \sigma n ^ { \prime } )
$$

网络最终达到的稳定状态时有 $\mu n ^ { \prime } = \mu ( n + 1 ) ^ { \prime }$ ，且$\sigma n ^ { \prime } = \sigma ( n + 1 ) ^ { \prime }$ ，则：

$$
\mu n = \mu ( n + 1 ) \quad \sigma n = \sigma ( n + 1 )
$$

其中稳定状态时，节点个数作为衡量相依网络维持自身功能的常用指标，本文把剩余最大连通图的节点个数的相对大小标记为 $G$ ，则

$$
G = \frac { N _ { A } ^ { ' } + N _ { B } ^ { ' } } { N _ { A } + N _ { B } }
$$

其中： $N _ { _ A }$ 代表子网络 $A$ 在攻击之前的初始网络节点总数， $N _ { _ B }$ 代表是系统子网络 $B$ 在攻击之前的初始节点总数； $\mathbf { \nabla } _ { N _ { A } ^ { \ast } } ^ { \ast }$ 和 $N _ { _ B } ^ { ^ { \prime } }$ 分别是网络在遭受攻击后子网络 $A$ 和子网络 $B$ 中剩余最大连通图的节点总数，即子网络 $A$ 和 $B$ 的幸存节点数。从式（1）可以看出， $G$ 值越大，系统在遭受攻击后子网络 $A$ 和 $B$ 剩余的节点数越多，整个系统表现出更好的鲁棒性。当攻击比例到达一定值时，被攻击的子网络会彻底崩溃，即子网络 $A$ 中所有节点全部失效与之相依的子 $B$ 网络也会达到全部崩溃或者到达一定的稳定状态。本文把此时整个相依网络系统 $G$ 值定义为 $G _ { c }$ ，则

$$
G _ { c } = \frac { N _ { _ { A \ - \mathrm { f i n a l } } } ^ { ' } + N _ { _ { B \ - \mathrm { f i n a l } } } ^ { ' } } { N _ { _ A } + N _ { _ B } } = \frac { N _ { _ { B \ - \mathrm { f i n a l } } } ^ { ' } } { N _ { _ A } + N _ { _ B } }
$$

其中： $N _ { B \mathrm { - f i n a l } } ^ { \mathrm { ' } }$ 为子网络A已经完全崩溃后子网络B的幸存节点数 $N _ { _ { B \mathrm { - f i n a l } } } ^ { \prime } \geq 0$ ）

# 2 仿真分析

现实生活中的许多网络，如通信网络、传感器子网、以及电力网络等，都具有无标度的特性和小世界网络的特性，可以采用典型无标度网络BA网络以及典型小世界网络WS网络分别对现实生活中实际简练关系进行模拟建网[12,15,17]。本节主要分析随机攻击和蓄意攻击下非对称相依网络的级联失效问题，之后对三种相依模式下非对称相依网络的鲁棒性进行分析。

# 2.1随机攻击下非对称相依网络的级联失效

采用BA网络的建网模式分别构建平均度为4的500个节点的A1网络和1000个节点的B1网络，采用WS小世界网络建网模式构建一个平均度为4的500个节点的A2网络和1000个节点的B2网络，之后按照1.1节中的三种不同相依模式构建不同类型的BA-BA，BA-WS，WS-BA，WS-WS相依网络，采用度大小随机排序攻击进行仿真处理。

![](images/bc6d37602cc7a0502aba0b4db520fd4677ff1d233d661b51a5cd279c89b1f64a.jpg)  
(a)随机模式下一对一相依随机攻击 (b)同配模式下一对一相依随机攻击

![](images/df345a8f9cf448954e17d20117c9db3f3504b0e5187124cd62b4f52d14c56d10.jpg)

网络，因此， $A$ 网络全部崩溃时 $B$ 网络不会彻底崩溃。图 2(a)为随机攻击模式下四种相依网络的G值变化，可以看出，在G值趋于稳定之前，受攻击的网络是WS小世界网络时的G值较低。例如，当移除比例 $p$ 值为0.5时， $G _ { w S - W S } < G _ { w S - B A }$ （204号$< G _ { \scriptscriptstyle B A - W S } < G _ { \scriptscriptstyle B A - B A }$ 。同理，同配和异配两种相依模式下也能发现这一结论。这是由WS小世界网络的拓扑结构决定的，WS 小世界网络的度分布比较均匀，因此，随机攻击时网络的鲁棒性较差。再比较最终 $B$ 网络的剩余节点比例可以发现，当 $B$ 网络是BA网络时，网络的稳定值0.3左右，而 $B$ 网络是小世界网络时，剩余节点比例趋于0.2。可以看出，无论何种相依模式，随机攻击模式下受攻击网络是WS网络时网络的鲁棒性更差，受攻击网络BA网络时网络的鲁棒性更强。不同类型相依网络的鲁棒性介于同种相依网络鲁棒性之间。同理，再分析一对多的非对称相依网络模型的鲁棒性，仿真结果如图3(a)\~(c)所示，同样可以发现当两个网络节点以及平均度一致时，受攻击的网络是WS网络时，网络的鲁棒性更差。根据以上结论可知，相依网络的鲁棒性与子网络的拓扑结构相关。

![](images/e0945c23832382bedd3d9a8f172d5cb2f6d6014381cce073c77fd3d8eb624402.jpg)  
图2三种模式下一对一相依随机攻击

# 2.2蓄意攻击下非对称相依网络的级联失效

对三种不同类型相依网络在蓄意攻击下的鲁棒性进行仿真分析，同样选取2.1节中的仿真实验生成网络方法，采用BA网络和WS小世界网络进行仿真，首先将节点度由大到小进行排序，之后进行攻击。

![](images/8dc79b6504b1e9ce9cc26f4dcd819ae3cdb4b529fa23612e5a28e7ee7e2e84a0.jpg)  
(a)随机模式下一对多相依随机攻击 (b)同配模式下一对多相依随机攻击

首先，对在随机攻击下的三种相依网络模型的鲁棒性进行分析。第一步，分析一对一非对称相依网络模型的鲁棒性，仿真结果如图2(a)\~(c)所示，可以发现随着攻击比例 $p$ 的增大剩余比例的 $1 - p$ 的减小，无论是何种相依网络模式下，剩余比例G 值都逐渐减小并最终趋于稳定。由于 $B$ 网络不完全相依于 $A$

![](images/0bd3b213eaaa97e7a580c4f4baf9ca458a9f35d92a5952f2e6719deda9e6843f.jpg)  
(a)随机模式下一对一相依蓄意攻击 (b)同配模式下一对一相依蓄意攻击

![](images/f7910674457e639de3d9659cc5cf398abaa82f65a6dd76dade18dc785c37fcf3.jpg)  
图3三种模式下一对多相依随机攻击  
图4三种模式下一对一相依蓄意攻

由图4(a)\~(c)和图5(a)\~(c)中的仿真结果可以明显看出，随着攻击比例 $p$ 的增加， $1 - p$ 减小，G值逐渐变小，当到达一定比例时，网络逐渐稳定。此时，虽然 $A$ 网络已全部崩溃，但是$B$ 网络的部分节点不完全相依于 $A$ 网络， $B$ 网络中仍存在作用的节点。通过分析可以得到与2.1节不同的结论，受攻击的网络是BA网络时的G值较低。例如，当 $\scriptstyle p = 0 . 6 5$ 时，有$G _ { _ { B A - W S } } < G _ { _ { B A - B A } } < G _ { _ { W S - W S } } < G _ { _ { W S - B A } }$ ，同理，在异配和同配相依网络下也能发现这一结论。这是由BA网络的拓扑结构决定的，BA网络的度分度呈现幂律分布，BA网络中的某些节点拥有与其他节点的大量链接，而大部分节点却只有少量的链接，因此，蓄意攻击下由BA网络构成的相依网络的鲁棒性较差。

![](images/185425cb4f8e63d52e7762f43c7bd200b92eb749e13bfe7445aada1fdbac6b62.jpg)  
图5三种模式下一对多相依蓄意攻击

# 2.3三种相依模式下的非对称相依网络鲁棒性分析

对由两个BA网络构成的三种不同模式下的相依网络进行随机攻击和蓄意攻击，通过对度相关相依模式和随机相依模式[16]构成的相依网络进行仿真，分析它们的鲁棒性以及度度相关性对非对称相依网络的影响。考虑到BA网络度的不平均特性，分别构建了两个节点数为1000和3000的平均度为4的BA网络进行仿真。

通过图6(a)(b)中三种一对一不完全相依模式的变化趋势可以看出，蓄意失效下三种不同相依模式的效果相当。对于随机攻击而言， $G _ { _ { A L } } > G _ { _ { R L } } > G _ { _ { D L } }$ 同配模式优于随机模式，随机模式优于异配模式。通过对图6(c)(d)中三种一对三完全相依模式的变化进行分析可以得到相同的结论。而由图6(e)(f)可以看出，蓄意失效下基于度的负相关相依模式的失效表现出弱鲁棒性。这是因为完全相依的模式下，度大的节点和度大的节点相依，蓄意攻击度大的节点，造成的毁坏显然最大，因此同配模式在蓄意攻击下显得更加脆弱。随机攻击下， $G _ { \scriptscriptstyle A L } > G _ { \scriptscriptstyle R L } > G _ { \scriptscriptstyle D L }$ 异配模式优于随机模式，随机模式优于同配模式。且对比图6(a)\~(f)，发现无论是何种相依模式鲁棒性都随着相依边的数量增加而减小，当随机攻击时，无论相依边比例是多少，异配相依网络都表现出弱鲁棒性。

![](images/2eb9acfc7c6e189c51cc9b83c4ec702bd994c59b8e226c7a97f2f6cef404dac5.jpg)  
图6不同攻击下三种相依网络对比

# 3 结束语

网络的鲁棒性是网络的一个重要属性，研究复杂网络的鲁棒性对于现实生活中网络的构建具有一定的指导意义。文中基于现有的相依网络模型，利用BA、WS两种典型的网络构建了相同类型和不同类型的非对称相依网络，分析了两种不同的攻击策略下三种不同的相依方式对同构相依网络和异构相依网络的影响，发现网络的鲁棒性与被攻击网络的拓扑结构有关。面对随机失效，三种相依模式中的同配模式优于随机模式，随机模式优于异配模式，同配相依网络表现出弱鲁棒性；面对蓄意攻击时，同配相依网络、异配相依网络和随机相依网络的鲁棒性相当，只有在个别情况下异配相依网络表现出弱鲁棒性，因此在网络安全研究中，对关键节点的保护和识别，具有重要的研究意义。

综上，本文研究了非对称相依网络在不同的建网方式下的不考虑负载的鲁棒性，对相依网络的设计具有一定的指导意义。另一方面，分析非对称网络在考虑负载的情况下的鲁棒性和识别关键节点是下一步研究的方向。

# 参考文献：

[1]Watts D J, Strogatz S H. Collective dynamics of small-world networks [J]. Nature,1998,393:440-442.   
[2]Barabasi A L,Albert R.Emergence of scaling in random networks [J]. Science,1999,286 (5439):509 (1-3).   
[3]Knoester DB,MckinleyPK,Ofria C.Cooperative network construction using digital germlines [C]// Proc of Conference on Genetic and Evolutionary Computation.2008:217-224.   
[4]Newman ME. Scientific collaboration networks I: network construction and fundamental results [J].Physical Review E,2001,64(64): 016131 (1-8).   
[5]窦炳琳，张世永．复杂网络上级联失效的负载容量模型[J]．系统仿真 学报,2011,23(7):1459-1463.   
[6]谭跃进，吴俊，邓宏钟．复杂网络抗毁性研究综述[J]．系统工程,2006, 24 (10): 1-5.   
[7]Min B,Yi SD,Lee KM,et al. Network robustness of multiplex networks with interlayer degree correlations [J].Physical Review E:Statistical Nonlinear& Soft Matter Physics,2014,89(4): 042811(1-5).   
[8]Li L,Jiao L,Zhao J.Quantum-behaved discrete multi-objective particle swarm optimization for complex network clustering[J].Pattern Recognition, 2017,63: 1-14.   
[9]Niu R W,Pan G J. Self-organized optimization of transport on complex networks[J].Chinese PhysicsLetters,2016,33(06):157-160.   
[10] Valente A X,Sarkar A，Stone H A.Two-peak and three-peak optimal complex networks.[J].Physical Review Letrs,2004,92(11): 118702 (1- 5).   
[11] Tanizawa T,Paul G,Cohen R,et al. Optimization of network robustness to waves of targeted and random attacks [J].Physical Review E Statistical Nonlinear & Soft Matter Physics,2005,71(2): 047101(1-4).   
[12] Buldyrev SV,Parshani R,Paul G,et al. Catastrophic cascade of failures in interdependent networks [J].Nature,2010,464 (7291):1025-1028.   
[13] Parshani R,Buldyrev S V,Havlin S. Interdependent networks: reducing the coupling strength leads to a change from a first to second order percolation transition [J].Physical Review Letters,2010,105 (4): 048701(1-3).   
[14] Wang J,Jiang C,Qian J.Robustness of interdependent networks with different link patterns against cascading failures [J].Physica A:Statistical Mechanics& Its Applications,2014,393 (1): 535-541.   
[15]陈世明，吕辉，徐青刚．基于度的正//负相关相依网络模型及其鲁棒性 研究[J].物理学报,2015,64(4):359-369.   
[16]陈世明，邹小群，吕辉．面向级联失效的相依网络鲁棒性研究[J].物 理学报,2014,63 (2):028902(1-10).   
[17]韩海艳，杨任农，王哲．边攻击下非对称相依作战网络级联失效[J]. 哈尔滨工业大学学报,2017,49(10):120-125.