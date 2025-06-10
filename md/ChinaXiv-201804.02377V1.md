# 负荷作用下的相依网络鲁棒性研究\*

李甍娜，郭进利(上海理工大学 管理学院，上海 200093)

摘要：提高相依网络的鲁棒性对网络的可靠性和安全性建设具有重要意义。针对所构建的三种耦合方式下的无标度相依网络，引入节点负荷作用，通过计算机仿真对相依网络的鲁棒性问题进行研究。研究发现，相比随机耦合和异配耦合，相依网络在同配耦合方式下具有最强鲁棒性。节点容忍系数和子网络同配性系数对相依网络的鲁棒性具有显著影响，为使相依网络更加鲁棒，应适当增大节点容忍系数或减小子网络同配性系数。另外，耦合强度的增加也能在一定程度上提高相依网络的鲁棒性，且随机耦合方式下的相依网络对耦合强度的变化更加敏感。

关键词：相依网络；负荷作用；级联失效；鲁棒性中图分类号：TP393 doi:10.3969/j.issn.1001-3695.2018.02.0107

# Study on load-induced robustness of interdependent networks

Li Mengna, Guo Jinli (BusinessSchool,UniversityofShanghai forScience&Technology,Shanghai 2Oo093,China)

Abstract: Itisvery important forreliabilityandsecurityof networks toimprove therobustnessof interdependent networks. This paperconstructedascale-free interdependent networks with threecoupling modes,and introduced theloadofthe nodes. And therobustness ofthe interdependent networks was studied bycomputer simulation.The study found that,compared with randomcouplingand disassortativecoupling,the interdependence networks have thestrongest robustness in theassortative coupling.Nodes tolerancecoeficientandsub-networksassortativecoeficienthaveasignificantimpactontherobustnesofthe interdependentnetworks.Inordertomakethe interdependentnetworks more robust,thenodes tolerancecoeffcientshouldbe increasedandthesub-networksasortativecoeficient shouldbereduced.Inadition,the increaseofthecouplingstrengthcan also improve therobustness,andthe interdependence networksunder therandomcoupling is more sensitivetothechangeof the coupling strength.

Key words:interdependent networks; load-induced; cascade failure;robustness

# 0 引言

随着科学技术和社会的发展，现实生活中的许多网络不再是单一存在的复杂网络，而是由两个或两个以上的子网络所构成的在结构和功能上都有所联系的相依网络。尽管相依网络在各子网络的协同工作下能使工作系统更加高效地运行，但面对节点攻击和节点故障却比单一复杂网络显得更加脆弱[1\~3]。如2003年的意大利停电事故，其中电力网与计算机信息网构成一个相依网络，一方面电力网为计算机信息网提供所需要的电力，另一方面计算机信息网控制着电力网的各项数据和运行情况。该事故因电力网的一个节点故障引起了整个网络中的大部分节点故障，最终导致大范围停电[4,5]。所以对于单一复杂网络鲁棒性的研究不再能满足现实生活对安全性的要求，相依网络的鲁棒性问题得到了更全面的关注与研究。

Buldyrev等人[在2010年提出了相依网络面对级联失效的鲁棒性模型。在此之后，学者们从各个角度对相依网络的鲁棒性进行了研究。刘润然等人[7研究了相依网络在几种蓄意攻击策略下，考虑单侧网络节点和相依节点度的特性的级联失效过程。Chen等人[8]研究了耦合偏好对相依网络鲁棒性的影响。陈世明、高彦丽等人[9,10]研究了相依网络的相依比例与相依冗余度对鲁棒性的影响，并提出了一种全局同质化相依网络耦合模式，有效改善了相依网络的鲁棒性。Cheng 等人[11,12]对无标度相依网络与ER随机相依网络的级联失效过程，以及节点破坏数量的临界值问题进行了分析。这些研究主要关注相依网络的自身结构，但没有考虑节点负荷的作用与分配。Wang 等人13\~15]研究了负荷作用下，耦合强度与节点容量对相依网络鲁棒性的影响，以及考虑故障概率的无标度相依网络的失效过程。Dong、Peng 等人[16\~18]根据K-核结构、节点的度值和介数特性，以及连接边和相依边对负荷的贡献比对相依网络的鲁棒性变化进行了分析。王竣德等人[19]研究发现提高部分节点的负载容忍度也能提高相依网络的鲁棒性。

为进一步对相依网络进行研究，探究各因素对其鲁棒性的影响，本文建立了无标度相依网络，并考虑节点负荷作用。针对节点过载失效和相依失效两种失效形式建立了相依网络的级联失效模型，并通过仿真实验分析了节点初始负荷和容量、子网络度相关性以及耦合强度等因素与相依网络鲁棒性的关系。

# 1 相依网络级联失效模型

# 1.1相依网络负载容量模型

本文采用两个无标度网络作为相依网络的子网络，分别记为网络A和网络B，节点总数分别为 $N _ { \mathrm { A } }$ 和 $N _ { \mathrm { B } }$ 。每个子网络中节点的内部连接定义为连接边，网络A与网络B之间的节点连接定义为相依边。子网络间的耦合方式根据各自的节点度值分为同配耦合、异配耦合和随机耦合三种，其中同配耦合为在网络A中度值大（小）的节点与网络B中度值大（小）的节点间建立相依边，而异配耦合为在网络A中度值大（小）的节点与网络B中度值小（大）的节点间建立相依边，随机耦合为在网络A与网络B中各自随机选择一个节点进行连接。

在已有关于复杂网络的研究中发现现实中的许多网络为无标度网络，但对不同现实网络节点负荷的定义却不同。所以为增加文章的普适性，本文不以某一个特定网络的绝对负荷和容量作为各节点的初始负荷和容量，而是衡量网络各节点初始负荷及容量的相对大小。由于网络中的节点度不仅能在一定程度上表征网络中不同节点的重要性，还能体现节点的繁忙程度和负荷大小，度值大的节点往往承受着更多的物质信息和能量流动。所以本文参考文献[13][15]，定义节点 $i$ 的初始负荷 $L _ { 0 i }$ 为

$$
L _ { 0 i } = k _ { i } ^ { \alpha }
$$

其中： $k _ { i }$ 为节点 $i$ 在相应子网络中的度值， $\alpha$ 为可调参数。

节点容量衡量了每个节点可承受负荷的大小，本文规定节点 $i$ 的容量 $C _ { i }$ 与其初始负荷成正比关系，即

$$
C _ { i } = ( 1 + \beta ) L _ { 0 i }
$$

其中： $\beta$ 为容忍系数， $\beta$ 越大，节点容量就越大，越能更好地抵御级联故障。

# 1.2相依网络级联失效模式

负荷作用下相依网络中的节点存在两种失效形式，即失去所有相依边而引起的相依失效和所承受负荷超过容量而引起的过载失效。假设网络A中的节点 $i$ 因故障或攻击而失效，一方面连接着节点 $i$ 的连接边和相依边将全部断裂，如果节点 $i$ 在网络B中的相依节点 $k$ 失去了所有相依边，则节点 $k$ 失效。另一方面，失效节点 $i$ 上的负荷将通过一定比例重新分配到它在网络A中的邻居节点上，其中邻居节点 $j$ 从节点 $i$ 中接收到的负荷为

$$
\Delta L _ { j } = L _ { i } \times \frac { C _ { j } } { \underset { n \in \Gamma _ { i } } { \sum } C _ { n } }
$$

其中： $\Gamma _ { i }$ 为节点 $i$ 所有邻居节点的集合。如果节点 $j$ 在接收到负荷 $\Delta L _ { j }$ 后其承受负荷超过了容量 $C _ { j }$ ，则节点 $j$ 失效。此过程不断循环，级联失效产生。

级联失效的具体过程如图1所示，相依网络初始状态如图1（a）所示，网络A与网络B一对一耦合，每个节点只存在一条相依边。在第一阶段失效过程中，网络A中的节点A5遭受攻击，移除节点A5的所有连接边和相依边，网络B中的节点B5失去所有相依边，所以B5也失效。将节点A5与B5的负荷按照虚线箭头方向以及式（3）的负荷分配规则分别分配到各自的邻居节点中，如图1（b）所示。假如经过第一阶段后只有节点A6过载失效，则在第二阶段失效过程中，节点B6因失去节点A6的相依边而失效。由于节点A6无邻居节点，所以该节点无负荷重分配，节点B6的负荷分配到唯一的邻居节点B1，如图1（c）所示。最后，所有节点均有相依边，且承受负荷均小于容量，级联失效停止，相依网络达到稳定状态，如图1（d)所示。

![](images/1b13ae29a042e36e6fd33f92db1f3e1589c8296e76195fb65dc35243fb6496fa.jpg)  
图1负荷作用下相依网络级联失效模式

# 1.3鲁棒性测度

本文只对网络A中的节点进行攻击，相依失效会使节点失效蔓延到网络B中。攻击节点i，将级联失效后相依网络达到稳定状态时幸存网络规模记为 $s _ { i }$ ， $s _ { i }$ 为网络A和网络B幸存节点数的总和。为衡量不同因素对相依网络的总体影响程度，本文对网络A中的每一个节点分别进行攻击，并将平均幸存网络规模与原始网络规模的比 $s$ 作为相依网络鲁棒性的衡量指标，即

$$
S = \frac { \underset { i \in \mathbb { A } } { \sum } s _ { i } } { N _ { \mathrm { A } } ( N _ { \mathrm { A } } + N _ { \mathrm { B } } ) }
$$

$s$ 的大小衡量了相依网络被破坏的平均程度， $s$ 越大表示相依网络失效的节点越少，即网络具有越好的鲁棒性。

# 2 仿真分析

本文构建的相依网络的两个子网络均为节点规模为1000的无标度网络，即 $N _ { \mathrm { A } } { = } N _ { \mathrm { B } } { = } 1 0 0 0$ ，网络A与网络B的网络特性如表1所示。

表1网络A与网络B的网络特性  

<html><body><table><tr><td>网络名称 节点数</td><td></td><td>边数</td><td></td><td>平均度 聚类系数</td><td>平均路径 长度</td><td>同配系数</td></tr><tr><td>网络A</td><td>1000</td><td>2000</td><td>4</td><td>0.02</td><td>4.32</td><td>0.049</td></tr><tr><td>网络B</td><td>1000</td><td>2000</td><td>4</td><td>0.019</td><td>4.55</td><td>0.043</td></tr></table></body></html>

调节控制节点初始负荷和容量的参数 $\alpha$ 和 $\beta$ ，通过MATLAB仿真试验对相依网络鲁棒性进行研究。本文根据在上一节中所构造的相依网络级联失效模型，考虑节点负荷重分配原则，以及相依失效和过载失效两种失效模式，制定了模拟相依网络级联失效过程的算法如下：

a）攻击网络A中的节点 $i$ 使其失效，删除与节点 $i$ 连接的  
所有边，并找出该节点在网络B中的所有相依节点；b)如果相依网络中的节点都只有一个相依节点，则对节点  
i和其相依节点的负荷进行重分配；如果相依网络中的节点有  
两个及以上的相依节点，则只对节点 $i$ 的负荷进行重分配;c）找出网络A与网络B中的过载节点，分别记为 $\mathsf { W } _ { 1 }$ 、  
$\mathsf { W } _ { 2 }$ 。删除与 $\mathsf { W } _ { 1 }$ 、 $\mathrm { W } _ { 2 }$ 中节点连接的所有边；d)找出 $\mathsf { W } _ { 1 }$ 、 $\mathrm { W } _ { 2 }$ 中各节点的相依节点，分别记为WI、W2。  
找出网络A与网络B中无相依边的节点，分别记为wi'、 ${ \bf w } _ { 2 } ^ { \prime }$ ，，  
并取 $\mathbf { w } _ { 1 }$ 与 $\mathbf { w } _ { 2 }$ 的交集，记为 $\mathsf { W } _ { 3 }$ ； $\mathbf { w } _ { 2 }$ 与 $\mathbf { w } _ { 1 }$ 的交集，记为 $\mathrm { w } _ { 4 }$ e）更新失效节点，统计下一阶段失效过程中需进行负荷重  
分配的节点。网络A与网络B的失效节点集合分别为 $\mathrm { W } _ { 1 } \cup \mathrm { W } _ { 3 }$ ，  
$\mathrm { W } _ { 2 } \cup \mathrm { W } _ { 4 }$ f)找出失效节点的邻居节点，进行负荷重分配，其中已失  
效的节点不再接受外来负荷；g）重复步骤c）\~f），直到无过载节点为止；h）计算相依网络幸存节点规模 $s$ i）重复步骤a) $\mathord { \sim } \mathrm { h }$ ），直到完成对网络A中的每一个节点  
都进行了一次攻击。计算相依网络鲁棒性指标 $S .$ 0

# 2.1容忍系数对相依网络鲁棒性的影响

在本节中相依网络为一对一耦合，即每一个节点有且仅有一个相依节点。初始负荷的可调参数 $\alpha$ 取6个不同的取值，分别为0.2、0.6、0.8、1.1、1.5、1.8。通过MATLAB仿真试验，分析不同 $\alpha$ 值下容忍系数 $\beta$ 对相依网络鲁棒性的影响。由图2可知，随着 $\beta$ 的增大，相依网络的鲁棒性逐渐增强，当 $\beta$ 达到一定值时能使攻击任何节点都不产生级联失效，即 $S { = } 1$ 。另外，由图2（a）（b）可知，当 $\alpha$ 较小时，相依网络子网间的耦合方式对其鲁棒性有显著的影响，其中同配耦合的鲁棒性最强，随机耦合次之，异配耦合的鲁棒性最差。 $\alpha$ 增大后，耦合方式对相依网络鲁棒性的影响大幅度减弱。 $\alpha = 1 . 1$ 时，三种耦合方式基本无差异。随着 $\alpha$ 的继续增大，尽管三种耦合方式对相依网络鲁棒性的影响差别不大，但同配耦合的优势仍然逐步显现。

![](images/56a6ca6d78e2784eee7b145051b4165a6298a0a38ca9433dfa91a608f8f414a0.jpg)  
图2不同 $\alpha$ 值下容忍系数对相依网络鲁棒性的影响

比较图2中的六个子图发现，随着 $\alpha$ 的增大，相依网络的鲁棒性越来越强。为更加清楚的展现 $\alpha$ 对相依网络鲁棒性的影响，本文绘制了在所取的六个 $\alpha$ 值下 $s$ 超过0.98时所需的 $\beta$ 值，如图3所示。图3进一步证实了 $\alpha$ 的增大能提高相依鲁棒性的结论，所以在容量与初始负荷成正比关系的情况下，初始负荷越大，相依网络鲁棒性越强。但是随着 $\alpha$ 的增大，图中三条折线下降速度越来越慢，最后趋于平缓，所以并不能通过不断增加节点初始负荷和容量的方式使相依网络的鲁棒性达到更好的效果，应根据网络的具体类型和初始负荷与容量的关系确定合适的 $\alpha$ 值。

![](images/8b00dc3e5da3c114597cb07843383206b19f93903a175bbdbd16d62376e238f6.jpg)  
图3相依网络 $s$ 超过0.98时所需的 $\beta$ 值

# 2.2子网络度相关性对相依网络鲁棒性的影响

为进一步分析不同节点失效对相依网络破坏程度的差异，本文将一个节点失效不产生级联失效所需的 $\beta$ 值记为 $\beta _ { p }$ 。图4

5分别展示了相依网络耦合方式为同配耦合和异配耦合时网络A所有节点的度与 $\beta _ { p }$ 的关系，其中 $\alpha$ 取0.2和1.5。由图4可知，同配耦合方式下当 $\alpha = 0 . 2$ 时，度值越小的节点对应的 $\beta _ { p }$ 越大，两者成负相关，这说明度值小的节点失效对相依网络的破坏程度更大。当 $\alpha = 1 . 5$ 时，尽管度值较小的节点对应的 $\beta _ { p }$ 大小不一，但度值大的节点对应的 $\beta _ { p }$ 均较小。如图5所示，与同配耦合方式相反， $\alpha$ 较小时节点度与 $\beta _ { p }$ 的负相关关系并不明显，但当 $\alpha$ 较大时 $\beta _ { p }$ 大的节点均集中在度值小的节点上，而度值大的节点的 $\beta _ { p }$ 均较小。通过表1中的数据可知，网络A与网络B的同配系数分别为0.049、0.043，即在子网络中，度值大的节点偏向与度值大的节点连接，度值小的节点偏向与度值小的节点连接。这意味着对于度值小的节点来说其邻居节点个数较少，自身负荷只能分配到几个甚至一个节点上，所以邻居节点接收的负荷相对较多。由于在子网络中度值小的节点偏向与度值小的节点连接，所以一旦这些邻居节点失效，其负荷也只能被少部分节点接收，从而更容易造成网络的进一步失效。

![](images/3493cc9e4d999333833f7957c7190f2586faa3359f1eb9b61b50b89cbe25ca57.jpg)  
图4同配耦合相依网络节点度与 $\beta _ { p }$ 的关系

![](images/dcd6b8cab42ed5384a87eecca3de9090be4f7e61d3a10d6dad16de54ebba691a.jpg)  
图5异配耦合相依网络节点度与 $\beta _ { p }$ 的关系

根据上述分析，本文考虑是否可以通过改变子网络节点连接关系从而提高相依网络的鲁棒性。如度值大的节点具有更大的容量，度值小的节点与度值大的节点连接可使度值小的节点失效时负荷能分配到具有较大容量的邻居节点上，从而减小邻居节点失效的可能性。本文在不改变各节点度值的情况下对网络A与网络B进行断边重连，调节两个子网络节点连接的度相关性，其中度相关性用同配性系数衡量，同配性系数 $\boldsymbol { r }$ 计算公式如下

$$
r = \frac { { M ^ { - 1 } \Sigma \ j _ { i } k _ { i } - [ M ^ { - 1 } \Sigma \frac { 1 } { i } ( j _ { i } + k _ { i } ) ] ^ { 2 } } } { { M ^ { - 1 } \Sigma \frac { 1 } { i } ( j _ { i } ^ { 2 } + k _ { i } ^ { 2 } ) - [ M ^ { - 1 } \Sigma \frac { 1 } { i } ( j _ { i } + k _ { i } ) ] ^ { 2 } } }
$$

其中 $j _ { i }$ 和 $k _ { i }$ 分别是子网络中第 $i$ 条边的两个端点的度，M为子网络节点数。当 $r { > } 0$ 时，子网络为节点度正相关连接，当$r { < } 0$ 时，子网络为节点度负相关连接。

图6展示了 $\alpha = 0 . 2$ 时不同子网络同配性系数下相依网络的鲁棒性情况。由图6可知，无论相依网络是同配耦合还是异配耦合，都有同配性系数 $\boldsymbol { r }$ 越小相依网络鲁棒性就越强的结论，这也进一步验证了子网络中度值小的节点与度值大的节点连接能减小级联失效程度的猜想。所以可采用改变子网络节点优先连接机制的方式，通过节点度负相关关系连接优化子网络自身结构，从而提高相依网络的鲁棒性。

![](images/1a47b100c431fa30a578b19c7b5a6745c785dd3a298e25c1fe8fbc4677206c94.jpg)  
图6子网络同配系数对相依网络鲁棒性的影响

# 2.3耦合强度对相依网络鲁棒性的影响

调节节点初始负荷和容量，以及改变相依网络子网络节点度相关性均为通过减轻过载失效从而提高相依网络的鲁棒性。为进一步从减小相依失效的角度对相依网络的鲁棒性进行研究，本文引入耦合强度d，定义为平均每个节点拥有相依边的数目，数目越大，与之耦合的节点数量越多，耦合强度越强。图7展示了 $\alpha$ 取0.2、1.5， $\beta$ 取0.2、0.3时三种耦合方式下耦合强度对相依网络鲁棒性的影响。如图7所示，随着耦合强度的增大，相依网络的鲁棒性逐渐增强，且随机耦合方式下的相依网络对耦合强度的变化更加敏感。但是并不是耦合强度的每一次增加都能带来可观的效益，如图7（a）（b）， $\alpha = 0 . 2$ 时同配耦合和异配耦合方式下的相依网络在耦合强度 $d$ 小于400 时，耦合强度的增加对于相依网络鲁棒性的影响很小，但当 $d$ 大于400时影响却很明显，对于随机耦合方式下的相依网络，鲁棒性随着耦合强度 $d$ 的增大而迅速增大，最后趋于平缓。在 $\alpha = 1 . 5$ 时也有类似的结论。所以需要通过提高耦合强度来增强相依网络鲁棒性时应针对具体网络设定合理的耦合强度。

![](images/c3826085874a138e00f18d4b881756cdb8d1eaa2bc3081ce531ff26c68886dbf.jpg)  
图7耦合强度对相依网络鲁棒性的影响

# 3 结束语

本文构建了同配耦合、异配耦合和随机耦合三种耦合方式下的无标度相依网络，并引入节点负荷作用建立相依网络的级联失效模型。通过计算机仿真对相依网络的鲁棒性问题进行研究。

研究表明，负荷作用下相依网络的鲁棒性在同配耦合方式下最强，异配耦合方式下最差。容忍系数的增加能有效提高相依网络的鲁棒性，且节点初始负荷对容忍系数的取值范围具有重要影响。另外，本文发现子网络自身结构能显著影响相依网络的鲁棒性，子网络同配性系数越低，相依网络的鲁棒性越高。适当增加耦合强度在一定程度上能提高相依网络的鲁棒性，且随机耦合方式下的相依网络对耦合强度的变化更加敏感。本文的研究对相依网络的可靠性和安全性建设具有一定的借鉴意义。

# 参考文献：

[1]Vespignai A. Complex networks: the fragility of interdependency [J]. Nature, 2010,464 (7291): 984-985.   
[2]Wang Shuai, Liu Jing. Robustness of single and interdependent scale-free interaction networks with various parameters [J].Physica A,2016,460:139- 151.   
[3] Zhao Zhuang, Zhang Peng，Yang Hujiang. Cascading failuresin interconnected networks with dynamical redistribution of loads [J].Physica A,2015,433:204-210.   
[4]Rosato V,Issacharoff L,Tiriticco F,et al.Modelling interdependent infrastructures using interacting dynamical models [J]. Int.J. Critical Infrastructures,2008,4: 63-79.   
[5]王建伟，荣莉莉．基于负荷局域择优重新分配原则的复杂网络上的相 继故障[J].物理学报,2009,58(06):3714-3721.(Wang Jianwei,Rong Lili. Cascading failures on complex networks based the local preferential redistribution rule of the load [J].Acta Physica Sinica,2009,58 (O6):3714- 3721.)   
[6]Sergey V.Buldyrev,Roni Parshani,et al.Catastrophic cascade of failures in interdependent networks [J].Nature,2010,464 (8932): 1025-1028.   
[7] 刘润然，贾春晓，章剑林，等．相依网络在不同攻击策略下的鲁棒性 [J].上海理工大学学报,2012,34(3):235-239.(Liu Runran,Jia Chunxiao, Zhang Jianlin,et al. Robustness of interdependent networks under several intentional attack strategies [J].Journal of University of Shanghai for Science and Technology,2012,34(3):235-239.)   
[8]Chen Zhen，Du WenBo，Cao XianBin，et al.Cascading failure of interdependent networks with different coupling preference under targeted attack[J].Chaos,Solitons& Fractals,2015,80:7-12.   
[9] 陈世明，吕辉，徐青刚，等.基于度的正//负相关相依网络模型及其鲁 棒性研究[J].物理学报,2015,64(04):363-373.(Chen Shiming,Lv Hui, Xu Qinggang，et al.The model of interdependent network based on positive//negative correlation of the degree and its robustness study[J]. Acta Physica Sinica,2015,64(04): 363-373.)   
[10]高彦丽，陈世明．一种全局同质化相依网络耦合模式[J].物理学报, 2016,65(14): 306-313. (Gao Yanli, Chen Shiming.A global homogenizing coupled pattern of interdependent networks [J].Acta Physica Sinica, 2016, 65 (14): 306-313. )   
[11] Cheng Zunshui, Cao Jinde,Tasawar H. Cascade of failures in interdependent networks with different average degree [J]. International Journal of Modern Physics C,2014,25 (5): 167-177.   
[12] Cheng Zunshui,Cao Jinde. Cascade of failures in interdependent networks coupled by different type networks [J].Physica A,2015,430:193-200.   
[13] Wang Jianwei,Li Yun, Zheng Qiaofang. Cascading load model in interdependent networks with coupled strength [J].Physica A,2015,430: 242-253.   
[14] Wang Jianwei, Jiang Chen,Qian Jianfei. Robustness of interdependent networks with different link pattens againstcascading failures [J].Physica A,2014,393: 535-541.   
[15] Wang Jianwei,Rong Lili.A model for cascading failures in scale-free networks with a breakdown probability [J].Physica A,2009,388:1289- 7898.   
[16] Dong Zhengcheng,Fang Yanjun,Tian Meng,et al.Approaches to improve the robustness on interdependent networks against cascading failures with load-based model[J]. Modern Physics Letters B,2015,29 (32):1550210.   
[17] Dong Zhengcheng,Fang Yanjun，Tian Meng.Cascading failuresof interdependent networks with different k-core structures [J].Modern Physics Leters B,2017,31(10): 1750112.   
[18] Peng Xingzhao, Yao Hong,Du Jun,et al Load-induced cascading failures in interconnected networks [J]. Nonlinear Dynamics,2015,82(1): 97-105.   
[19]王竣德，老松杨，阮逸润，等．基于节点负载容忍度的相依网络鲁棒性 研究[J].系统工程与电子技术,2017,39(11):2477-2483.(Wang Junde, Lao Songyang, Ruan Yirun, et al. Research on robustnessof interdependent networks based on load tolerance of nodes [J]. Systems Engineering and Electronics,2017,39 (11): 2477-2483.)