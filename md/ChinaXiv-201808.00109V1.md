# PMC模型下网络故障的节点可诊断研究

刘峰1,²，梁家荣1,²，郭杨1,²，谢敏1，莫海淼1,2(1．广西大学 计算机与电子信息学院，南宁 530004;2.广西多媒体通信与网络技术重点实验室，南宁 530004)

摘要：故障诊断在保证系统稳定性方面十分重要。传统故障诊断研究大多忽略了系统局部特征。PMC模型下，针对于这一问题，引入了节点可诊断的概念，并通过节点可诊断方法的研究得到了节点可诊断度的充分条件和t-可诊断新算法STFDA。最后，对n维超立方网络和n维星状网络从节点可诊断的角度进行了分析，验证了所得充分条件的正确性，并将算法应用到这两种网络中进行了故障诊断。其中，充分条件和STFDA算法的实现借助了新的结构ST。STFDA算法的时间复杂度为O(N8)，δ为网络中节点的最大度。相比于其他算法，算法的时间复杂度得到显著降低。

关键词：系统级故障诊断；PMC模型；节点可诊断；ST结构；t-可诊断算法 中图分类号：TP206.3 doi:10.3969/j.issn.1001-3695.2018.04.0278

# Research on node diagnosis of network fault under PMC model

Liu Feng1,², Liang Jiarong1,², Guo Yang1,², Xie Min1, Mo Haimiao1, 2 (1.SchoolofComputer&ElectronicsInformation,Nannng 530o04，China;2.Guangxi Key LaboratoryofMultimedia Communications&Network Technology,Nanning 53ooo4,China)

Abstract:Fault diagnosis isveryimportantinensuringsystemstability.Mostoftraditional fault diagnosisresearch ignored characteristicsoflocal structure.For that problem underPMC model,thedefinitionofnode diagnosis was introduced.And throughthestudybynodes diagnosis,obtained thesuffcientconditionof thenode diagnosiabilityand gotanewt-diagnosis algorithmcaled STFDA.Finall,ananalysis from the angleof node diagnosis of n-dimensional hypercube network andndimensional star network wasperformed inorder to test thevalidityof thesuffcientconditions.Algorithm performed a fault diagnosistothetwokindsofnetworkatlast.Indeed,theimplementationofthesuficientconditionandalgorithmgotthehelp ofanewstructurecaled ST.And algorithm's timecomplexity was proved tobe O(N δ),withSequal tothe maximum degree of node in network, which was significantly reduced compared with others algorithm.

Key Words: system diagnosis; PMC model; node diagnosis; ST structure; t-diagnosis algorithm

# 0 引言

随着计算机技术的不断发展，多处理器系统的处理器规模达到数以千计。由于多处理器系统规模增大，处理器之间数据的交换高度频繁，其中的处理单元发生故障难以避免。为了保证系统的可靠性，能快速、有效、准确的寻找出系统中的故障处理器，系统应具有自我故障诊断的能力。事实上，在网络的故障诊断中，主要有两种诊断策略：a）电路级诊断，这种诊断方式需借助外部进行诊断，这会使得诊断过程过于复杂，实用性不足;b)系统级诊断，这种诊断方式主张利用系统内处理器自身的处理能力，让处理器互相检测，通过对这些检测结果的分析完成故障诊断的目标。在对系统级诊断的研究中，Preparata等人[I提出了PMC模型。在该模型下，多处理器系统被抽象为无向的连接图 $G \big ( V , E \big )$ ， $V$ 代表处理器的集合， $E$ 代表处理器间的线路连接。 $( \nu _ { i } , \nu _ { j } ) \in E$ ， $\nu _ { i }$ 向 $\boldsymbol { \nu } _ { j }$ 发送测试信号， $\boldsymbol { \nu } _ { j }$ 发送反馈信号给 $\boldsymbol { \nu } _ { i }$ ， $\nu _ { i }$ 通过对反馈信号的检测判断 $\boldsymbol { \nu } _ { j }$ 的状态。PMC 模型中，在系统的故障节点个数不超过 $t$ 的条件下，如果系统能诊断出所有的故障处理器，则称系统是 $t -$ 可诊断的。此后，人们对PMC模型下的故障诊断问题进行了广泛研究，例如，文献[2]给出了t-可诊断系统的刻画条件；文献[3]研究了PMC 下的条件故障诊断；文献[4研究了拓展超立方网络的 $( t , k ) -$ 诊断度；文献[5]讨论了t-故障诊断算法；文献[6]给出了哈密顿网络中的五轮自适应诊断算法等等。

值得一提的是，上述研究成果主要是从全局的角度考虑，并没有注意到系统的局部特征。然而，有时候忽略局部特征，会使我们丢失很多重要的信息，从而导致诊断结果的不理想。比如系统 $S _ { 1 }$ 是 $t _ { 1 }$ -可诊断的，系统 $S _ { 2 }$ 是 $t _ { 2 }$ -可诊断的。当 $t _ { 1 } < < t _ { 2 }$ ，通过极少的链路将 $S _ { \mathrm { { l } } }$ 和 $S _ { 2 }$ 连接，考虑这样的复合系统 $S _ { 3 }$ 。从整体角度考虑， $S _ { 3 }$ 很大可能系统可诊断度只有 $t _ { \mathrm { { l } } }$ 。也就是说，只有在故障处理器个数不超过 $t _ { 1 }$ 时， $S _ { 3 }$ 才能够保证诊断出所有故障处理器。但实际上， $S _ { 3 }$ 是可以保证准确无误的诊断出这$t _ { 1 } + t _ { 2 }$ 个故障处理器的。之所以如此，是因为 $S _ { \mathrm { r } }$ 是 $t _ { \mathrm { l } }$ -可诊断的局部特征被忽略了，致使整体性能下降。

另外，工业生产中也存在着对局部诊断的需求。依照这些需求，我们只需保证某个指定子系统中所有故障处理器能被准确诊断，而系统其他部分的处理器状态无须人们关心。这种对局部诊断的需求在大规模集成系统和超大规模集成系统中是常见的。

本文主要工作在于利用节点可诊断的方法对系统局部的节点可诊断度和网络故障算法进行研究。节点可诊断与系统可诊断相似，它可以看做是局部结构上的系统可诊断。但不同于系统可诊断，节点可诊断更关心单个节点的故障与否，侧重于检测出这一节点的状态。本文利用节点可诊断的方法，得到PMC模型下判定节点可诊断度的充分条件。为了满足该条件，进一步提出了ST结构。借助于ST结构，本文设计了网络系统的t-可诊断的算法STFDA，其时间复杂度为O(Nδ)。另外，许多规则网络拓扑可以用来模拟多处理器系统，其中超立方网络[8]和星型网络[9]是两个经典的规则网络。这两种网络具有高并发、松耦合的特性，对于它们的研究成果十分丰富[10-13]。为了验证所得结论的正确性，最后对这两种经典网络进行分析并将算法运用其中。

# 1 预备知识

在PMC模型下，处理器的故障被假设是永久的（不会时好时坏)。故障集代表所有故障处理器的集合。多处理器系统$G \big ( V , E \big ) \ , \ ( \nu _ { i } , \nu _ { j } ) \in E$ ， $\boldsymbol { \nu } _ { i }$ 测试 $\boldsymbol { \nu } _ { j }$ ，测试结果用 $a _ { i j }$ 表示( $a _ { i j } \in \{ 0 , 1 \} \ )$ 。若 $\boldsymbol { \nu } _ { i }$ 测试 $\boldsymbol { \nu } _ { j }$ 故障， $a _ { i j } = 1$ ; $\boldsymbol { \nu } _ { i }$ 测试 $\boldsymbol { \nu } _ { j }$ 正确， $a _ { _ { i j } } = 0$ ；若 $\boldsymbol { \nu } _ { i }$ 是故障的,$a _ { i j }$ 的结果随机。将 $a _ { i j }$ 的值赋给有向边 $< \nu _ { i } , \nu _ { j } >$ ，得到有向带权的诊断图 $G ( V , C )$ 。称所有 $a _ { i j }$ 的集合为系统的症状s(syndrome)。系统故障诊断问题即为：利用 $s$ 和 $G ( V , C )$ 寻找系统的故障集。图1给出了一个PMC下故障集为 $\{ \mathrm { P } _ { 0 } , \mathrm { P } _ { 2 } , \mathrm { P } _ { 3 } , \mathrm { P } _ { 5 } \}$ 的4-立方。

P2 0010 P10 1010 P111011 p3 0011   
Po 0000 P1 1000 p81000 pg1001 Ps0110 p7011 P14 1110 P15 1111   
P4 0100 Ps 0101 P12 1100 P13 1101 诊断结果用(i， $\mathrm { j , a _ { i j } , a _ { j i } ) }$ 表示，结果如下： (0, 1,0, 1) (0,2, 1,0) (2,3,0, 1) (3,1,0, 1) (4,5,1,0) (4,6,0, 0) (6, 7,0,0) (7,5, 1, 1) (8, 9 ,1,0) (8, 10,0,0) (10, 11,0,0) (11,9,1, 1) (12, 13,0,0) (12, 14,0,0) (14,15,0,0) (15,13, 0, 0)(0,4, 1,1) (1,5,1, 1) (2,6, 1,1) (3,7,0, 1) (8, 12,0, 0)(9, 13,1,1) (10, 14, 0,0) (11, 15,0,0)(0, 8,1, 1)(1,9, 1,0)(2,10,0,1)(3,11,0, 1)(4,12,0,0)(5, 13,0,1) (6, 14,0, 0)(7, 15,0, 0)

图1故障集为{P0,P2,P3,P5}的4-立方示例

对于症状 $s$ ，若存在节点集 $\boldsymbol { F } ^ { \prime }$ ， $\forall x , y \notin F ^ { \prime } , a _ { x y } = 0$ ;$\forall x \notin F ^ { \prime } , y \in F ^ { \prime } , a _ { x y } = 1$ ， $\mid F$ t。则称 $\boldsymbol { F }$ 与 $s$ 相容， $\boldsymbol { F }$ 是 $s$ 的容许故障集(AFS)，图2(a)给出了相关示例。由于故障节点诊断结果的随机性， $s$ 的AFS可能有多个。当 $s$ 对应的AFS有且只有一个时，系统是 $t$ -可诊断的，该AFS为所求故障集。

系统 $G ( V , C )$ ，称不同的集合 $F _ { 1 }$ 和 $F _ { 2 }$ 可区分，当且仅当：存在 $< x , y > \in C$ ，其中， $x \notin F _ { 1 } , x \notin F _ { 2 }$ ， ${ \boldsymbol { y } } \in F _ { 1 } \oplus F _ { 2 }$ （即 $( F _ { 1 } - F _ { 2 } ) \cup ( F _ { 2 } - F _ { 1 } )$ ）。可知，若系统 $s$ 的任意两个AFS 都可区分，则系统是 $t$ -可诊断的，图2(b)给出 $F _ { 1 }$ 和 $F _ { _ 2 }$ 可区分的示例。

![](images/c70775b85496c62c587d8fd21c70fb70475082cf09ff30daa02ba722414cff1f.jpg)  
图2相容故障集 $F$ 及 $F _ { \mathrm { l } }$ 和 $F _ { ? }$ 可区分

本文用 $\deg ( \nu _ { i } )$ 表示诊断图 $G ( V , C )$ 中节点 $\nu _ { i }$ 的入度。对于节点集 ${ \mathit { S } } \subseteq V$ ， $G ( S )$ 表示S的诱导子图， $G - S = G ( V - S )$ 。节点 $x \notin S$ ，$L _ { s , x }$ 表示 $G - S$ 中通过节点 $x$ 的最大连通分支， $\mid L _ { s , x }$ |表示连通分支包含的节点个数。

接下来，本文将根据节点可诊断的定义得到判定节点可诊断度的充分条件，为了满足该条件，进一步提出了ST结构，利用ST结构可以得到系统的 $t$ -可诊断度和诊断算法。

# 2 节点可诊断

正如引言所说，从整体角度出发的故障诊断研究可能会忽略一些系统局部的特征。本章采用节点可诊断的方法对系统局部进行研究。不同于系统可诊断，节点可诊断更关注于单个节点的可诊断性，即：若节点 $x$ 是故障的，无论其他节点状态能否被检测出， $x$ 一定能被检测出是故障的。据此得到节点可诊断的定义。

定义1对于系统S，在 $x$ 是故障的情况下，若S的每一个AFS都包含节点 $x$ ，则称节点 $x$ 是节点可诊断的[7]。

可知，若故障节点 $x$ 是节点可诊断的，则 $x$ 一定处于S所有AFS的交集中。由此，可以得到以下推理。

推理1对于系统S，节点 $x$ 是节点可诊断的，则对于V的任意两个不同子集 $F _ { 1 } , F _ { 2 }$ ， $\mid F _ { 1 } \mid , \mid F _ { 2 } \mid \leq t$ ，若存在 $x \in F _ { 1 } \oplus F _ { 2 }$ ，则 $F _ { 1 }$ 与 $F _ { 2 }$ 可区分。

节点可诊断可以看做是局部结构的系统可诊断，两者之间存在着相似性。与系统可诊断度相对应，称使节点满足节点可诊断条件的最大 $\textbf { \textit { t } }$ 为该节点的节点可诊断度。

定理1PMC 模型下，系统 $G ( V , E )$ 是 $t$ -可诊断的，当且仅当系统中所有节点的节点可诊断度大于等于 $t$ 。

证明必要性。用反证法，假设系统不是 $t$ -可诊断的，则$V$ 必然存在着两个不同的 AFS， $\mid F _ { 1 } \mid \leq t , \mid F _ { 2 } \mid \leq t$ ， $F _ { 1 }$ 和 $F _ { 2 }$ 不可区分。取 $F _ { 1 } \oplus F _ { 2 }$ 中任意一节点，则该节点不是节点可诊断的，与题设矛盾。

充分性。用反证法，假设存在节点 $x \in F _ { 1 } \oplus F _ { 2 }$ ， $x$ 不是节点可诊断的。那么， $F _ { 1 }$ 与 $F _ { 2 }$ 不可区分，这与系统是 $t$ -可诊断相矛盾。

由定理1知，可以通过判断系统中节点的节点可诊断度获得系统的 $t$ -可诊断度。这对一些对称性强的网络的 $t$ -可诊断度研究十分有利。因为这些网络中的大部分节点是等同的，只需诊断几个甚至是一个节点的节点可诊断度即可。

定理2系统 $G ( V , E )$ ，任意的整数 $p$ ， $0 \leq p \leq t - 1$ ， $s$ 为V中基数为 $p$ 的任意子集， $x$ 为 $V - S$ 中节点，若 $\mid L _ { s , x } \mid \geq 2 ( { \sf t } - { \tt p } ) + 1$ ，则 $x$ 的节点可诊断度大于等于 $t$ 。

证明用反证法，假设 $x$ 的节点可诊断度小于 $\textbf { \textit { t } }$ 。由推理1 知，存在不等的 $F _ { 1 }$ 和 $F _ { 2 }$ ， $\mid F _ { 1 } \mid \leq t , \mid F _ { 2 } \mid \leq t$ ， $x \in F _ { 1 } \oplus F _ { 2 }$ ， $F _ { 1 }$ 与 $F _ { 2 }$ （20不可区分。令 $S = F _ { 1 } \cap F _ { 2 }$ ， $\mid S \mid = p$ ，则 $0 \triangleleft S \vert \leq t - 1 , \vert F _ { 1 } @ F _ { 2 } \vert \leq 2 ( t - p )$ 。由题意知 $\mid L _ { s , x }$ √ $2 ( { \mathsf { t } } { - } { \mathsf { p } } ) { + } 1$ ，所以 $F _ { 1 } \oplus F _ { 2 }$ 不可能是包含 $x$ 的最大连通分支。换言之，若 $F _ { 1 } \oplus F _ { 2 }$ 属于包含 $x$ 的最大连通分支，则必存在一点 $y \not \in ( \mathrm { F } _ { 1 } \cup \mathrm { F } _ { 2 } )$ ， $y \in L _ { s , x }$ 。又 $L _ { s , x }$ 是连通的，所以存在着一条从 $y$ 到 $x$ 的链路， $F _ { 1 }$ 与 $F _ { 2 }$ 可区分，与假设矛盾。图3给出了$F _ { 1 } \oplus F _ { 2 } \subseteq L _ { s , x } , y \in L _ { s , x }$ 的两种情况。

![](images/ea31fedc6bce24b1170317109ff109663bf52e541e5f3e0716e20b760bbae341.jpg)  
图3 $F _ { 1 } \oplus F _ { 2 } \subseteq L _ { s , x } , y \in L _ { s , x }$ 的两种情况

为了使定理2得以满足，给出一种特殊结构ST。

定义2对于 $H ( V , E )$ ， $V = \{ x \} \cup \{ \nu _ { 1 i } \} \cup \{ \nu _ { 2 i } \}$ ， $\deg ( x ) \geq t$ ，$E = \{ ( \nu _ { _ { 1 i } } , \mathrm { x } ) , ( \nu _ { _ { 2 i } } , \nu _ { _ { 1 i } } ) \}$ ， $1 \leq i \leq t$ 。称这种结构为ST。图4 给出了$d e g \left( x \right) = t$ 的 ST结构示意图。

![](images/95bafa1021423bf27fe6b7e443d74e9e109e425d3ecb6eef9f72e0abeff1c790.jpg)  
图4 $d e g \left( x \right) = t$ 的 ST结构示意图

定理3系统 $G ( V , E )$ ， $x \in V$ ， $\deg ( x ) \geq t$ ，若 $x$ 上存在着结构ST，则 $x$ 的节点可诊断度大于等于 $t$ 0

证明在 ST 中任意取除 $x$ 外的 $p$ （ $0 \leq p \leq t - 1$ ）个节点构成集合S。由ST的结构可知， $S T - S$ 中必然存在着 $t - p$ 条完整的 $( \nu _ { 2 i } , \nu _ { 1 i } , x )$ 链路， $1 \leq i \leq t$ 。 $| L _ { s , x } \geq S T - S \mid \geq 2 ( t - p ) + 1$ 。由定理2知， $x$ 的节点可诊断度大于等于 $\textit { t }$ 。图5给出了 $S T - S$ 可能形成的两种子图示例。

![](images/e3252edff791fa196ead0e07bb9e6b234b5b245041c9d298139de2345b921231.jpg)  
图5可能形成的子图示例

根据定理1\~3可以得到系统 $\textit { t }$ -可诊断一个充分条件：

推理2对于 $G ( V , E )$ ， $\mid V \mid = N$ 。系统是 $t$ -可诊断的，当且仅当a) $\mid N \mid \geq 2 t + 1$ ；b) $\nu \in V , \deg ( \nu ) \geq \mathfrak { t }$ ；c)V中任意节点上存在ST结构。

关于 $t$ -可诊断度的研究成果十分丰富[14]。如：当 $n \geq 5$ ， $n$ 维超立方网络（ $Q _ { n }$ ）的 $t$ -可诊断度为 $n$ ；当 $n \geq 4$ ， $n$ 维星形网络$( ~ S _ { n } ~ )$ 的 $\textit { t }$ -可诊断度为 $^ { n - 1 }$ [15];当 $n { \geq } 6$ ， $n$ 维增强超立方网络 $t$ -可诊断度为 $n { + } 1$ 等等[12],[16,17]。

由推理2知，若系统的每个节点上都存在着 ST结构，则系统可诊断度大于等于t。所以，节点可诊断问题转换为寻找节点上ST结构的问题，显然这要简单得多。大部分网络系统，尤其是一些规律性强的网络，如交叉立方网络、扭立方网络，增强立方网络以及星状网[等，只要它们的维度足够大，是很容易在其节点上找到ST结构的。本文接下来将利用ST结构得到系统 $t$ -可诊断新算法 $S T F D A$ ，并将该算法运用到 $Q _ { n }$ 和 $S _ { n }$ 中，以验证其有效性。

# 3 算法

在给出算法之前，给出一些需要用到的定义。ST结构中，存在有向诊断边 $< \nu _ { { } _ { 1 i } } , x >$ 和 $< \nu _ { 2 i } , \nu _ { 1 i } >$ ， $1 \leq i \leq t$ ，诊断结果为$a _ { \nu _ { 1 i , x } } \mathcal { \bar { K } } \mathbb { H } a _ { \nu _ { 2 i , \nu _ { 1 i } } } \in \{ 0 , 1 \}$ 。取向量 $R = ( a _ { \nu _ { 2 i , \nu _ { 1 i } } } , a _ { \nu _ { 1 i , x } } )$ ， $R$ 的取值有 $R ( 0 ) = ( 0 , 0 )$ ，

$R ( 1 ) = ( 0 , 1 )$ ， $R ( 2 ) = ( 1 , 0 )$ ， $R ( 3 ) = ( 1 , 1 )$ ，如图6。 $\vert R ( i ) \vert$ 表示 ST 中$R ( i )$ 的出现次数，显然有 $\textstyle \sum _ { i = 0 } ^ { 3 } \left| R ( i ) \right| = t$ 。

定理4对于 $G ( V , C )$ ，故障节点个数不超过 $t$ 。 $x \in V$ ， $x$ 上存在 ST 结构。ST结构上相应诊断结果用 $R ( i )$ 和 $| R ( i ) |$ 表示，$1 \leq i \leq 3$ 。那么

a)若 $\mid R ( 0 )$ 亚 $R ( 1 ) \vert$ ，则 $x$ 必然是正确的;

b)若 $\lvert R ( 0 ) \rvert \triangle \lvert R ( 1 ) \rvert$ ，则 $x$ 必然是故障的。

证明a)反证法。假设 $x$ 是故障的，那么：

对于 $R ( 0 ) = ( 0 , 0 )$ ，必然有 $\nu _ { 1 i }$ 和 $\nu _ { 2 i }$ 是故障的，ST 中至少有$2 | R ( 0 ) |$ 个故障节点。

对于 $R ( 1 ) = ( 0 , 1 )$ ， $\nu _ { 1 i }$ 和 $\nu _ { 2 i }$ 可能都是正确的，可能没有故障节点。

对于 $R ( 2 ) = ( 1 , 0 )$ ，必然有 $\nu _ { 1 i }$ 是故障的，ST中至少有 $\left| R ( 2 ) \right|$ 个故障节点。

对于 $R ( 3 ) = ( 1 , 1 )$ ， $\nu _ { 1 i }$ 和 $\nu _ { 2 i }$ 必然有一个是故障的，ST中至少有 $\left| R ( 3 ) \right|$ 个故障节点。

ST中故障节点至少有 $2 | R ( 0 ) | + | R ( 2 ) | + | R ( 3 ) | =$ $\begin{array} { r } { \sum _ { i = 0 } ^ { 3 }  { \vert { R ( i ) } \vert } +  { ( \vert { R ( 0 ) } \vert } -  { \vert { R ( 1 ) } \vert } ) >  { \mathrm { t } } } \end{array}$ ，这与故障节点个数不超过 $t$ 矛盾。因此， $x$ 必然是正确的。

b)反证法。假设 $x$ 是正确的，那么：

对于 $R ( 0 ) = ( 0 , 0 )$ ， $\nu _ { 1 i }$ 和 $\nu _ { 2 i }$ 可能都是正确的，可能没有故障节点。

对于 $R ( 1 ) = ( 0 , 1 )$ ，必然有 $\nu _ { \scriptscriptstyle { 1 i } }$ 和 $\nu _ { 2 i }$ 是故障的，ST 中至少有$2 | R ( 1 ) |$ 个故障节点。

对于 $R ( 2 ) = ( 1 , 0 )$ ，必然有 $\nu _ { 2 i }$ 是故障的，ST中至少有 $\left| R ( 2 ) \right|$ 个故障节点。

对于 $R ( 3 ) = ( 1 , 1 )$ ， $\nu _ { \scriptscriptstyle { 1 i } }$ 和 $\nu _ { 2 i }$ 必然有一个是故障的，ST 中至少有 $\left| R ( 3 ) \right|$ 个故障节点。

ST中故障节点至少有 $2 | R ( 1 ) | + | R ( 2 ) | + | R ( 3 ) | =$ $\begin{array} { r } { \sum _ { i = 0 } ^ { 3 }  { \vert { R ( i ) } \vert } +  { ( \vert { R ( 1 ) } \vert } -  { \vert { R ( 0 ) } \vert } ) >  { \mathrm { t } } } \end{array}$ ，这与故障节点个数不超过 $t$ 矛盾。因此， $x$ 必然是故障的。

![](images/8e2937e6152a55093ec1b57f41b0d1d6f3cb55f8bd40a0247589147833fb6f48.jpg)  
图6 $S T$ 结构上 $R ( i )$ 取值的四种情况

假设 $G ( V , C )$ 表示一个具有 ST 结构的网络，下面给出一个诊断 $G ( V , C )$ 中故障集的诊断算法（STFault Diagnosis Algorithm,简称 STFDA）。

算法：STFDA输入： $G ( V , C )$ 。输出：故障集。

begin:

1.将所有节点从0到 $N { - } 1$ 进行标号；取 $i = 0$ ·  
2.当 $i < N$ ，利用定理4判断 $i$ 的状态并标记， $i$ 若是正确的，标记T，跳转第3步； $i$ 若是故障的，标记F，跳转第4步；  
3.根据i对其邻节点的诊断结果判断这些邻节点的状态并标记，若为0，标记T；若为1，标记F。 $i + +$ ，跳转到第2步；  
4.将所有诊断i结果为0的节点标记为F， $i + +$ ，跳转到第2步；5.当 $i \geq N$ ，将所有标记为F的节点取出记为 $F$ ，若 $\vert F ^ { \prime } \vert { > } \mathrm { t }$ ，系统不是t-可诊断的，退出算法；若 $\big | F ^ { \prime } \big | \le \mathtt { t }$ ， $\mathbf { \boldsymbol { F } } ^ { \prime }$ 为所求故障集，结束，退出算法。  
注意：当节点存在标记冲突，即要对一个节点标记为T(或F）时，该节点已被标记为F(或T)，则系统不是t-可诊断的，直接退出算法。end.

为了查找迅速方便，可以将节点上ST结构的 $\left| R ( 0 ) \right|$ 和 $\vert R ( 1 ) \vert$ 值录入一张诊断表。假定查表时间是可忽略的，则节点的诊断时间为 $2 \delta = O ( \delta )$ ，系统的诊断时间为 $O ( N \delta )$ ， $\delta$ 为节点的度。另外，在正则网络中一般 $\delta = \log N$ ，这些网络的诊断算法时间复杂度为 $O ( N \log N )$ 。

1974年Hakimi和Amin提出了PMC模型下的 $t -$ 可诊断的充要条件[2]，在此基础上，Dahbura和Masson 提出了 $O ( N ^ { 2 . 5 } )$ （20的 $t -$ 可诊断算法[5]；区别于 $t -$ 可诊断, $t / t -$ 可诊断要求系统中所有故障节点能被孤立在一个容量不超过 $t$ 的节点集中。相对于 $t -$ 可诊断，它允许有正确节点被误诊为故障，但保证所有故障节点都能被诊断出。Hakimi和Chwa 提出了PMC 模型下的$t / t -$ 可诊断的充要条件[18]，Yang 和Masson 等人在此基础上提出了 $O ( N ^ { 2 . 5 } )$ 的可诊断算法[19]。另外，在不同于PMC 模型的MM模型下，Sengupta 和Dahbura 提出了 $t -$ 可诊断的充要条件并给出了 $\mathbf { M } \mathbf { M } ^ { * }$ 下的 $O ( N ^ { 5 } )$ 诊断算法，Tang 和Yang改进了该算法使之时间复杂度降至 $O ( N \Delta \delta ^ { 3 } )$ [20]，其中 $\Delta$ 与 $\delta$ 分别代表节点最大度和最小度。各算法时间复杂度比较结果如表1所示。

表1各算法时间复杂度比较  

<html><body><table><tr><td>算法</td><td>时间复杂度</td></tr><tr><td>PMC 传统t算法</td><td>O(N25)</td></tr><tr><td>PMC传统t/t算法</td><td>O(N2.5)</td></tr><tr><td>MM传统t算法</td><td>O(N△δ)</td></tr><tr><td>STFDA算法</td><td>O(N log N)</td></tr></table></body></html>

对比以上算法发现，算法 STFDA时间复杂度仅有 $O ( N \log N )$ ，要远小于其他算法，因此算法的实现成本能够得以减小；另一方面，STFDA更简单实用，易于理解，实现起来要更加简单快捷。

# 4 应用

超立方体网络和星型网两种网络作为多种实际模型的抽象和代表，已被广泛应用，如MIMD系统中的超立方网络和数据中心网络中以超立方结构为基础的的BCube 和MDCube[21]等。另外，超立方网络有着优越的拓扑性质，可以将如环形网、线性网、网格网络等这些具体网络嵌入到超立方网络中[8]。这些网络和超立方网络族（超立方网络及其变种）具有类似的网络拓扑性质。超立方网络作为这些网络的抽象与代表，本文将对其进行研究，并将算法运用其中。星状网情况与之类似，不再详述。

下面先证明这两种网络节点上都有ST结构，进一步得到这两种网络的可诊断度，然后通过检验所得诊断度的正确与否来验证可诊断度充分条件的正确性。最后，运用提出的STFDA算法来诊断这两种网络系统的故障。当然，如何将算法在一些实际网络中实现工程运用需要进一步考虑。

# 4.1 $n$ 维超立方网络( $Q _ { n }$ ）

超立方体及其一些变体有着高并发，松耦合的优秀特性，可以被用于系统的构建[22.23]，对其可诊断性的研究重要且有必要。

超立方可以由低维立方体循环生成，两个 $_ { n - 1 }$ 维立方体节点对应连接即可形成一个 $n$ 维立方体，所以超立方中所有节点是等同的，图1给出了两个3-立方连接形成的4-立方。 $n$ 维立方体中含有 $2 ^ { n }$ 个节点，将这些节点用 $n$ 位2进制数 $a _ { 1 } a _ { 2 } a _ { 3 } . . . a _ { n }$ 进行标号，其中 $a _ { i } \in \{ 0 , 1 \}$ ， $1 \leq i \leq n$ 。若这两节点相邻，则两节点的标号只有一位不同，如：0000代表的节点与0001和1000相邻。$Q _ { n }$ 中任意两节点是连通的，节点之间距离等于其节点标号相差的位数(汉明距离)。

推理3 $Q _ { n }$ 系统可诊断度为 $n$ ， $n \geq 5$ 。

证明对 ST 中的节点进行标号， $x$ 标号为 $a _ { 1 } a _ { 2 } . . a _ { i } . . . a _ { n }$ ( $a _ { i } \in \{ 0 , 1 \} , 1 \le i \le \mathtt { n }$ )， $\nu _ { 1 i }$ 为 $a _ { 1 } a _ { 2 } . . . \underline { { { a } } } _ { i } . . . a _ { n }$ ， $\nu _ { 2 i }$ 为 $a _ { 1 } a _ { 2 } . . . \underline { { { a } } } _ { i } . . \underline { { { a } } } _ { j } . . a _ { n }$ ，其中$j = ( i + 2 ) \bmod { \left( n \right) }$ ， $\underline { { \boldsymbol { a } } } _ { i }$ 表示 $a _ { i }$ 的取反。图7(a)给出了 $\deg ( x ) = n$ 时 $Q _ { n }$ 上 ST 标号示例。

当 $n < 5$ ，存在标号冲突(两节点标号相同)，节点上不存在ST结构；当 $n \geq 5$ ，不存在标号冲突。因此， $Q _ { n }$ 节点上存在着ST结构，节点可诊断度为 $n$ 。又 $Q _ { n }$ 中所有节点是等同的，由推理2知， $Q _ { n }$ 的系统可诊断度为 $n$ ，与已知研究一致[24]。

将算法运用到 $Q _ { n }$ 中。首先对 $Q _ { n }$ 节点进行标号。其次从标号为0的节点开始，通过比较0节点上ST结构的 $\left| R ( 0 ) \right|$ 和 $\left| R ( 1 ) \right|$ 的大小，标记0节点状态。然后根据0节点对其邻节点的诊断结果标记其邻节点状态。移动到下一节点，重复以上操作，直到移动到 $N { - } 1$ 节点为止。诊断过程中，若存在节点标记冲突或标记为F的节点个数大于 $n$ ，则系统故障节点超过 $n$ ，直接退出算法。否则，将所有标记为F的节点取出，即为故障集。

# 4.2 $n$ 维星状网 $\cdot \ : S _ { n }$ ）

$S _ { n }$ 表示 $n$ 维星状网[9]。 $S _ { n }$ 含有 $| n !$ 个节点，用 $1 - n$ 这 $n$ 个整数的一个随机排列对这些节点标号，如：1234，1243等。 $S _ { n }$ 中，节点 $A = a _ { 1 } . . a _ { i } . . a _ { j } . . a _ { n }$ 与节点 $B = a _ { 1 } . . a _ { j } . . a _ { i } . . a _ { n }$ 是相邻的。也就是说，若交换节点A标号的第 $i$ 位和第 $j$ 位能得到标号B， $1 \leq i , j \leq \mathtt { n } , i \neq j$ ，则A和B相邻。 $S _ { n }$ 中所有节点的度都为 $n { - } 1$ ，图8给出了 $S _ { 4 }$ 的结构示意图。

![](images/195fd05d8fa412c01ab9e9c5f32e28be14096383c741d92ab297e9cc8f0c649d.jpg)  
图7 $Q _ { n }$ 和 $S _ { n }$ 上 $\mathit { S T }$ 结构的标号示例

推理4 $S _ { n }$ 系统可诊断度为 $n { - } 1$ ， $n \geq 4$ 。

证明对 ST中节点标号， $x$ 标号为 $a _ { 1 } . . a _ { i } . . a _ { j } . . a _ { n }$ ，交换 $x$ 的第1位和 $( i + 1 ) \bmod { \left( n \right) }$ 位得到新标号并赋值给 $\nu _ { 1 i }$ ，再将 $\nu _ { 1 i }$ 第1位与 $( i + 2 ) \bmod { \left( n \right) }$ 位交换得到标号并赋值给 $\nu _ { 2 i }$ ， $1 \leq i \leq n$ 。图7(b)给出了 $\deg ( x ) = n - 1$ 时 $S _ { n }$ 上ST标号示例。因此， $S _ { n }$ 节点上存在着ST 结构，节点可诊断度为 $n - 1$ 。又 $S _ { n }$ 中所有节点是等同的，由推理2知， $S _ { n }$ 的系统可诊断为 $^ { n - 1 }$ ， $n \geq 4$ 。与已知研究一致[15]。

将算法运用到 $S _ { n }$ 中。第一步先对 $S _ { n }$ 节点进行标号；第二步从标号为0的节点开始，通过比较0节点上ST结构的 $\left| R ( 0 ) \right|$ 和$\vert R ( 1 ) \vert$ 的大小，标记0节点状态；第三步根据0节点对其邻节点的诊断结果标记邻节点状态。移动到下一节点，重复以上操作，直到移动到 $N - 2$ 节点为止。诊断过程中，若存在节点标记冲突或标记为F的节点个数大于 $^ { n - 1 }$ ，则系统故障节点超过 $n { - } 1$ ，直接退出算法。否则将所有标记为F的节点取出，即为故障集。

![](images/3122b15e028829154b40bc06fe4e073e6ea2d7f92e901c85b6ebf605c3b6220a.jpg)  
图8 $S _ { 4 }$ 结构示意图

# 5 结束语

本文从PMC模型下的局部诊断着手，主要研究了网络的节点可诊断问题。这包括节点可诊断度及故障诊断算法。得到了如下结论：a）节点可诊断度与其节点的度有关。若系统节点上存在着与节点度 $t$ 有关的ST结构，则节点可诊断度大于等于t;b）针对于具有ST结构的网络，提出了一种故障诊断的新算法 $S T F D A$ 。 $S T F D A$ 简单、有效、易读懂，且其时间复杂度为$O ( N \delta )$ ， $\delta$ 为网络节点的度。在一些规律性的网络中，时间复杂度为 $O ( N \log N )$ 。

针对于具有ST结构的网络，算法大大减少了故障诊断的成本。但是，对于那些节点上不存在ST结构的网络，算法的实现较为困难，如何在这些网络中利用节点可诊断的方法进行故障诊断是下一步需要研究的问题。本文最后将算法STFDA应用到经典网络 $Q _ { n }$ 和 $S _ { n }$ 中，实现了这两种抽象网络的故障诊断。更进一步，该如何将算法应用到具体的网络系统中，如树型网络、Omega 网络等，以实现工程运用需要继续研究。

# 参考文献：

[1]Preparata FP,Metze G, Chien R T.On the connection assignment problem of diagnosable systems [J]. IEEE Trans on Electronic Computers,1967,16 (6): 848-854.   
[2]Hakimi S L,Amin A T. Characterization of connection assignment of diagnosable systems [J].IEEE Trans on Computers,1974,23(1): 86-88.   
[3] 郭晨，梁家荣，葛志辉，等．基于互测 PMC 模型的条件诊断算法[J]. 电子学报,2015,43(2):255-261.(Guo Chen,Liang Jiarong,Ge Zhihui,etal. A conditional diagnosis algorithm based on Ex-Test PMC model[J].Acta Electronica Sinica,2015,43 (2): 255-261.)   
[4] 梁家荣，陈秒江．基于比较模型的扩展立方体网络的(t,k)-诊断度研 究[J].通信学报,2017,38(8):9-18.(Liang Jiarong,Chen Miaojiang. Research on (t,k) -diagnosability for augmented cube network under the comparison model[J]. Journal on Communications,2017,38 (8): 9-18.)   
[5]Dahbura A T,Masson G M.An O (n2.5) fault identification algorithm for diagnosable systems [J].IEEE Trans on Computers,1984,33(6): 486-492.   
[6]Ye Liangcheng，Liang Jiarong.Five-round adaptivediagnosisin Hamiltonian networks [J].IEEE Trans on Parallel and Distributed Systems, 2015,26 (9):2459-2464.   
[7]Chiang C F,Tan JJM. Using node diagnosability to determine tdiagnosability under the comparison diagnosis model[J].IEEE Trans on Computers,2009,58 (2): 251-259.   
[8]Saad Y,Schultz MH. Topological properties of hypercubes [J].IEEE Trans on Computers,1988,37(7): 867-872.   
[9]Akers S B,Krishnamurthy B.A group-theoretic model for symmetric interconnection networks [J]. IEEE Trans on Computers,1989,38 (4): 555- 566.   
[10] Ye Liangcheng,Liang Jiarong,Lin Haixiang.A fast pessimistic diagnosis algorithm for Hypercube-Like networks under the comparison model [J]. IEEE Trans on Computers,2016,65 (9): 2884-2888.   
[11] Liang Jiarong, Zhou Ning, Yun Long. $\mathbf { t } / / \mathbf { k }$ -fault diagnosis algorithm of ndimensional hypercube network based on the $\mathbf { M M * }$ model [J]. Journal of Systems Engineering and Electronics,2018,29(1): PP216-222   
[12] Liang Jiarong,Zhang Qian,Li Hongyi. Structural properties and $\mathrm { { \ t / / s } }$ （20 diagnosis for star networks based on the PMC model[J]. IEEE Access,2017, 5 (1): 26175-26183.   
[13] Xie Min, Ye Liangcheng,Liang Jiarong.A $\mathbf { t } / / \mathbf { k }$ diagnosis algorithm on hypercube-like networks [J]. Concurrency and Computation Practice and Experience,2017,30 (6): 1682-1690.   
[14] Chwa K Y, Hakimi S L. On fault identification in diagnosable systems [J]. IEEE Trans on Computers,1981,30(6): 414-422.   
[15] Kavianpour A. Sequential diagnosability of star graphs [J]. Computers & Electrical Engineering,1996,22(1): 37-44.   
[16] Armstrong JR,Gray F G. Fault diagnosis in a boolean n cube array of microprocessrs [J]. IEEE Trans on Computers,1981,30 (8): 587-590.   
[17] Liang Jiarong, Huang Ying, Ye Liangcheng. Diagnosabilities of exchanged hypercube networks under the pessimistic one-step diagnosis strategy [J]. Journal of Systems Engineering and Electronics.2015,26 (2): 415-420.   
[18] ChwaKY,Hakimi.On fault identification in diagnosable systems [J]. IEEE Trans on Computers,2006,30(6): 414-422.   
[19] Yang CL, Masson G M,Leoneti R A.On fault isolation and identification in t1//t1-diagnosable systems [J].IEEE Trans on Computers,2006,35(7): 639-643.   
[20] Yang Xiaofan,Tang Yuanyan. Efficient fault identification of diagnosable systems under the comparison model[J].IEEE Trans on Computers,2007, 56 (12) .   
[21]李丹，陈贵海，任丰原，等．数据中心网络的研究进展与趋势[J].计 算机学报,2014,37(2): 259-274.(Li Dan,Chen Guihai,Ren Fengyuan,et al. Data center network research progress and trends [J]. Chinese Journal of Computers.,2014,37(2): 259-274.)   
[22] Hayes JP,Mudge T N,Stout Q F.Architecture of a Hypercube supercomputer [C]// Proc of ICPP.1986: 653-660.   
[23] Hills D. The connection machine [M]// The Use of Super-computers in Stellar Dynamics.Berlin: Springer,1986: 84-85.   
[24] Bhat K V S.An efficient approach for fault diagnosis in a boolean n-cube array of microprocessors [J]. IEEE Trans on Computers,1983,32(11): 1070-1071.