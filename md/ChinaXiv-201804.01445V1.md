# 混合加噪声模型与条件独立性检测的因果方向推断算法

麦桂珍la，彭世国la，洪英汉』b,2†，陈平华²，彭昱忠(1．广东工业大学a.自动化学院;b.计算机学院，广州 5100;2.韩山师范学院 物理与电子工程学院，广东 潮州521041;3．广西师范学院 科学计算与智能信息处理广西高校重点实验室，南宁 530001)

摘要：从可观测的变量中推导出潜在的因果关系是人工智能领域的热点研究之一。传统的基于独立性检测的方法是通过检测V结构来确定一组马尔科夫等价类而非最终的因果关系；而加噪声模型算法却只能适应于低维度的因果网络结构。为此，提出一种采取分治策略的混合加噪声模型与条件独立性检测的因果方向推断方法。首先是将一个n维因果网络分解成n个诱导子网络，分别归入三种基本结构（单度结构、非三角结构和存在三角的结构）中的一种，从理论上分别证明其有效性；其次对每个诱导子网络进行基于加噪声模型算法与条件独立性检测相结合的方向推断；最后把所有子网络合并起来构建成完整的因果关系网络。实验表明，该方法比传统的因果关系推断方法更加有效。

关键词：因果网络；加噪声模型；马尔可夫等价类 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.12.0802

# Causation inference based on combining additive noise model and conditional independence

Mai Guizhenla, Peng Shiguola, Hong Yinghan1b,2†, Chen Pinghua², Peng Yuzhong (la.SchoolofAutomation;b.SchoolofComputerScience&Technology Guangdong UniversityofTechnology,Guangzhou 51006,China;2.SchoolofPhysice&Electronic Engineering,HanshanNormal University,ChaozhouGuangdong521041, China;3.KeyLaboratoryofScientificComputing&Intellgent InformationProcessing Guangxi Teachers Education University Nanning 530001, China）

Abstract: Inferringcausal directions fromobservedvariables isoneofthe fundamentalproblems inartificialinteligence (Al) field.Traditionalconditional independence based methodsusualllearncausaldirectionsbydetecting V-structuresandreturn Markov equivalence classs,instead of truecausal structures；Most other direction learning methods can distinguish the equivalececlasses,but areeffective onlyinthe bivariate (ortwo-dimensional)cases.This paper proposedanew approach for causal direction inference from general networks,based on a split-and-merge strategy.The method first decomposes an ndimensionalnetwork intoninducedsubnetworks,eachofwhichcorrsponds toanodeinthenetwork.Each inducedsubnetwork can be subsumed tooneof thethree substructures:one-degree,non-triangle andtriangle-existence structures.Three ffective algorithms are developed to infercausalities fromthe threesubstructures,and learning these induced subnetworksorderlyto achieved the wholecausal structureofthe multi-dimensional network.Experiments showthatthe method is more general and effective than traditional methods.

Key words: causal networks; additive noise model; Markov equivalence classes

# 0 引言

的联合分布情况，如变量相关性。事实上，研究因果关系和相关性之间最重要的区别恰好就在于事物之间的因果先后顺序（即因果方向）的推断。事实证明，理解因果关系的方向对于预测任何可干预的结果和许多应用都是至关重要的，例如经济模型预测，基因分析。

从可观测的变量推断出事物中蕴含的因果关系是人工智能领域的研究热点之一。因果推断与主流的统计学习方法不同，它旨在研究数据的内在生成机制，而不是简单地研究观察变量

从计算的角度来看，因果推断通常是采用一种概率图模型，模型中变量间的有向边表示因果方向[10]。由于对实验样本进行因果干扰是比较困难的，通常会采用条件独立（CI）测试来检测变量之间的局部因果关系[10,15]。通过条件独立测试来检测数据间蕴涵的V结构，就可以得到关于这些数据的一部分因果关系，这种方法是马尔可夫等价类方法[2]。尽管目前研究也利用一致性传播的算法[3将给定组在马尔可夫等价类的基础上进行因果关系推断，但是数据不完整就会导致结果不准。以上方法能够找到的因果关系的准确性受制于从目标数据中检测到的V结构数量。如果给定数据不蕴涵V结构，这些方法则不能确定任何因果方向，仅能返回一个因果骨架，即无环图。

为了解决上述方法在因果推断中遇到的瓶颈，近十年来研究人员主要在下述这几种假设下并利用因果变量之间的不对称性对因果方向进行推断。其中有一种方法是Shimizu等人提出的线性非高斯加噪声模型（LINGAM）[13,14]，具体为：给定两个变量 $x$ 和 $y$ ，首先假设它们之间的因果关系的方程为（204号 $y ~ = f ( x ) + ~ \varepsilon$ ，其中 $f$ 是一个线性函数， $\boldsymbol { \varepsilon }$ 是一个噪声项并统计独立于 $x$ 。其原理是在假定数据生成过程 $f$ 是线性,且噪声 $\boldsymbol { \varepsilon }$ 是非高斯分布的情况下因果变量存在不对称性：a) $\varepsilon$ 独立于 $x$ b）由于实际上还不知道 $x$ 与 $y$ 之间的因果方向，所以同时也得考虑相反的模型 $x = g \ ( y ) \ + e$ ，此时 $e$ 不独立于 $y$ 。因此，通过对两个模型，自变量与噪声之间的独立性可以推断出 $x$ 与 $y$ 之间的因果方向。依据这一性质就可以对马尔可夫等价类进行因果方向推断。另一种方法是非线性加噪声模型(ANM)，适用于连续数据[6.18]和离散数据[11,12]。类似地，ANM的原理如下：给定两个变量 $x$ 和 $y$ ，用来表达他们之间的因果关系的方程y= f(x)+ε，其中f(\*)是一个非线性函数，ε是一个噪声项并统计独立于 $x$ 。其最核心的理论在于 $P ( x , y )$ 在绝大部分情况下只允许 $x \to y$ ，也就是正方向的ANM，当考虑反方向的ANM, $x = g ( y ) + e$ ，会发现残差项 $e ^ { \prime } \ = \ x - E ( x | y )$ 与自变量 $y$ 是不独立的，因此 $x \gets y$ 不成立。总的来说，基于加噪声模型是通过检测联合分布 $P ( x , y )$ 在正反ANM间的不对称性来推断出因果关系。PostNonLinear(PNL)模型[15]进一步泛化了ANM在数据生成过程中的假设,它允许一个额外的双射转换数据，具体地说,该模型具有形式 $y = g ( f ( x ) ) + e$ ，其中 $g : R  R$ 是双射。

近年来，一些因果方向推断方法也通过信息几何模型来挖掘因果变量之间的不对称性[4][7][8]。这些方法主要是：在因果方程 $y ~ = f ( x ) + ~ \varepsilon$ 中，在自变量 $x$ 与生成机制 $f ( x )$ 是独立的假设下进行因果方向的推断。虽然这些方法能以不同的方式检测数据之间不对称的原因和影响,但它们仅在二维的情况下有效。类似的，ANM和PNL在绝大部分情况下也仅在二维有效[16,18]。另外，现有的一些混合模型算法，如CDHD[5]，在某种程度上可以从多维网络中发现因果关系。然而有研究表明，CDHD方法并不十分准确，因为它直接使用了一个双变量因果学习方法IGC[7,8]，在方向学习阶段直接对目标节点的诱导子图进行方向推断，从理论上这是一种错误的做法，因为如果诱导子图的维度总大于3，理论上此方法的准确率就会趋向于 $50 \%$ ，也就是等同于随机判别。

综上所述，传统的基于V结构的方法、加噪声模型、信息几何模型等都无法有效地从高维观测数据中推断出因果关系。本文提出了一种采取分治策略的混合加噪声模型与条件独立性检测的因果方向推断方法。该方法首先是将一个 $n$ 维因果网络分解成 $n$ 个诱导子网络，每个子网络对应于网络中的一个节点。其中诱导子网络都可以被归入三个基本结构（单度结构、非三角结构和存在三角的结构）中的一个，理论上证明了三种基本结构的有效性；其次对每个诱导子网络进行基于加噪声模型算法与条件独立性检测相结合的方向推断；最后把所有子网络合并起来构建成完整的因果关系网络。实验表明，本文提出的方法在因果关系推断中比传统的方法更加有效，适应性更强。

本文的贡献如下：a)在含有三角结构的因果网络中，提出了一种新的因果关系推断方法可以大大缩小时间复杂度的算法；b)将因果网络分割成三个基本的子网络进行因果关系推断。并且进行了大量实验来评估该方法，实验结果表明，本文提出的方法（ $\mathrm { V E + A N M }$ ）性能优于现有的经典方法。

# 1 准备知识

考虑一个可以表示为无向图 $G _ { \scriptscriptstyle N } = \{ V _ { \scriptscriptstyle N } , E _ { \scriptscriptstyle N } \}$ 的网络，其中$V _ { \scriptscriptstyle N } \ = \ \{ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } \}$ 和 $E _ { \scriptscriptstyle N } = \{ e _ { 1 } , e _ { 2 } , \cdots , e _ { n } \}$ 表示网络中的节点和边缘。对于任何节点 $y \in V _ { \scriptscriptstyle N } ( y = x _ { k } )$ ，方向学习的目标是发现$y$ 和邻点之间的因果关系的方向集合。所有的边都是面向的，得到一个有向无环图形(DAG) $G _ { D } = \{ V _ { D } , E _ { D } \}$ 的位置在 $E _ { \scriptscriptstyle D }$ 中，$V _ { D } = V _ { N }$ 和每一个有向边对应于 $E _ { \scriptscriptstyle N }$ 的一个唯一的无向边。本文称 $G _ { \scriptscriptstyle D }$ 为 $G _ { _ { N } }$ 的推导网络。对于任何 $N$ 中的节点 $y$ ，可以得到一个诱导子图 $G _ { \mathrm { y } } ~ = ~ \{ V _ { \mathrm { y } } , E _ { \mathrm { y } } \}$ ，其中 $V _ { _ { y } }$ 由 $y$ 和它的邻居集合$N _ { y }$ 组成。 $V _ { _ { y } }$ 可以根据下面的方式分为两个子集 $N T _ { y }$ 和 $T _ { y }$ ，对于任意节点 $\boldsymbol { x } \in V _ { y }$ ，如果 $x$ 的度大于1，则将 $x$ 移到 $T _ { _ { y } }$ ，否则将 $x$ 移到 $N T _ { y }$ 。这样本文可以将 $V _ { y }$ 纳入以下三个子结构中的一个：

定义1如果 $\left| N _ { y } \right| = 1$ ，则称 $G _ { \mathrm { y } }$ 是单度结构,简称 ODS。

定义2如果 $\left. N _ { y } \right. > 1$ 而且 $\left. T _ { y } \right. \ = \ 0$ ，则称 $G _ { y }$ 是非三角结构，简称NTS。

定义3如果 $\left. N _ { y } \right. > 1$ 而且 $\left. T _ { y } \right. > 0$ ，则称 $G _ { y }$ 是存在三角的结构，简称TES。

定义4V 结构和三角结构。对于 $G _ { \scriptscriptstyle D }$ 中的三个节点 $x$ ，$y$ 和 $z$ ，如果 $x$ 和 $z$ 是 $y$ 的父亲节点，而且 $x$ 和 $z$ 之间不存在边，则可以说 $\boldsymbol { x } \cdot \boldsymbol { y }$ 、 $z$ 构成一个 $\mathrm { \Delta V }$ 结构；反之，如果 $x$ 和$z$ 之间存在一条边，则说 $x$ 、y、 $z$ 构成一个三角结构。

定义5若 $G _ { \mathrm { y } }$ 中存在V结构，则称 $G _ { y }$ 为VES。

定义6若 $G _ { \mathrm { y } }$ 中不存在 $\mathrm { \Delta V }$ 结构，则称 $G _ { y }$ 为NVS。

定义7三个变量(或节点） $x \setminus y$ 和 $z$ ，如果 $x$ 和 $y$ 满足结构方程 $y = f ( x ) + \varepsilon$ ，其中 $\mathbf { \sigma } _ { \varepsilon }$ 是一个噪声项，可称 $x$ 和 $y$ 构成一个确定性的情况。如果 $y \ = f ( x , z ) \ + \varepsilon$ ，则称 $x$ 和 $y$ 构成一个不确定性的情况。

定义8D分离。设 $P$ 是变量 $x _ { i }$ 到变量 $\boldsymbol { x } _ { j }$ 的路径， $P$ 被一组变量 $Z ( Z \subseteq V _ { D } )$ 阻断，当且仅当符合以下其中一个情况：a)$P$ 包含一个链， $x _ { i } \gets x _ { k } \gets x _ { j }$ ，且 $x _ { k } \in Z$ ； b) $P$ 包含一个分叉， $x _ { i } \gets x _ { k } \to x _ { j }$ ，且 $x _ { k } \in Z : { \mathsf { c } } ) P$ 包含一个对撞， $x _ { i } \to x _ { k } \gets x _ { j }$ ，$x _ { k } \notin Z$ 且 $x _ { k }$ 没有任何后裔存在于 $z$ 中。

# 2 方法

# 2.1V结构搜索算法

给定一个无向图 $G _ { \scriptscriptstyle N } = \{ V _ { \scriptscriptstyle N } , E _ { \scriptscriptstyle N } \}$ ,其中包含一个诱导子图$G _ { y } : G _ { y } = \{ V _ { y } , E _ { y } \} \ : ( \ : V$ $V _ { _ { y } }$ 由 $y$ 和它的邻居节点集合 $N _ { \mathrm { y } }$ 组成)。如果 $G _ { y }$ 属于NTS，则 $\forall x \in N _ { y }$ 只与 $y$ 直接相连。

本文提出的方法采用 $\mathrm { ~ v ~ }$ 结构搜索和ANM相结合的方法，发现 $y$ 与 $N _ { y }$ 之间的方向。注意到，大多数基于V结构的方法在CI测试中具有指数复杂度，在考虑小图形时，很难避免产生大量冗余的计算。还有一些V型结构的识别方法更有效率，如SVS[I]，它根据下面的定理来确定 $\mathrm { \Delta V }$ 型结构：

定理1给定三个变量 $x _ { 1 } \cdot \ x _ { 2 }$ 和y， $x _ { 1 } \right. y \left. x _ { 2 }$ 是一个V 结构，当且仅当存在变量集 $Z \subseteq G _ { _ { N } } \setminus ( x _ { 1 } , x _ { 2 } )$ 使得1)$x _ { 1 } \perp x _ { 2 } \vert Z ~ ; ~ 2 ) ~ x _ { 1 } \chi Z x _ { 2 } \vert ( y , Z )$ 。

上面的定理说明了如何普遍地找到V结构。然而很难从数百个变量中找到一个可能的条件集合 $z$ (或更多，如高维网络)。因此，这些方法用在本文提出的方法中是无效的或不适用的。在节中首先提出了一种有效的方法，从 $G _ { y } ( N T S )$ 中寻找 $\mathrm { \Delta V }$ 型结构，如以下推论所示。

推论1给定一个有向无环图GD={V,ED}，x,y,z∈V，如果 $x , y , z$ 形成一个 $\mathrm { ~ v ~ }$ 结构 $x \to y \gets z$ ，则 $\exists N _ { x z }$ ，$N _ { _ { x z } } \subset ( N _ { _ { x } } \cup N _ { _ { z } } )$ ，使得 $x \perp z \big | N _ { x z }$ 和 $x \nearrow z \lvert ( N _ { x z } \cup y )$ 。

证明1）如果 $x$ 和 $z$ 都是根。令 $N _ { _ { x z } } = \emptyset$ ，则有 $x \perp z$ 和$x \mathcal { L } z | y \circ 2 )$ 如果 $x$ 或 $z$ 是多度的，则在 $x$ 和 $z$ 之间可能存在三种路径：1, $x  \cdots  z$ （或者 $x  \cdots  z$ ）；2, $x \left. \cdots \right. z$ ；3， $x \right. \cdots \left. z$ 。令 $\mathbf { \Psi } _ { a }$ 为 $x$ （ $a \in N _ { x }$ ）的一个邻居节点，一条途径 $P$ 覆盖 $\{ x , a , z \}$ ，如果 $\mathrm { ~ \bf ~ P ~ }$ 属于第一种路径或者第二种路径，必须有 $P$ 被 $\mathbf { \Omega } _ { a }$ 挡住；如果 $P$ 属于第三种路径，则一定有一个对撞 $b$ ，且 $P$ 也被 $\varnothing$ 或者 $\mathbf { \Psi } _ { a }$ （ $a \in N x \ \rangle$ ）挡住， $\mathbf { \Psi } _ { a }$ 不是 $b$ 的后代。总的来说，本文可以找到这样的一组 $\mathbf { \Omega } _ { a }$ （记为 $N _ { _ { x z } }$ ，NNN）来阻止x到z或者z到x的任何路径，即$x \perp z \vert N _ { x z }$ 。又由于 $y$ 是 $x$ 和 $z$ 之间的一个对撞，则对于任意的D 分离的集合 $N _ { _ { x z } }$ 有 $y \notin N _ { _ { x z } }$ 。因此, $x$ 和 $z$ 不能被 $N _ { _ { x z } } \cup y$ D分离。

根据上面提到的,当考虑结构 $x \to y \to z$ 或 $x \gets y \gets z$ 时很容易获得以下推论，如下：

推论2 给定一个有向无环图GD={V,ED}，x,y,z∈VD，如果 $x , y , z$ 形成一个结构 $x \to y \to z$ 或 $x \gets y \gets z$ ，则 $\exists N _ { x z }$ ，$N _ { x z } \subset ( N _ { x } \cup N _ { z } )$ ，使得 $x \perp z \big | N _ { x z }$ ·

推论3给定一个无向图 $G _ { \scriptscriptstyle N } = \{ V _ { \scriptscriptstyle N } , E _ { \scriptscriptstyle N } \}$ ,一个结构 $x - y - z$ （204号 $( \mathbf { \sigma } _ { x , y , z } \in V _ { \scriptscriptstyle N }$ $x$ 到 $z$ 不是直接相连的);如果 $\exists N _ { x z } \subseteq ( N _ { x } \cup N _ { z } )$ ，使得 $x \perp z \big | N _ { x z }$ 和 $x \mathcal { L } z \big | ( N _ { x z } \cup y ) \mid \langle y \notin N _ { x z }$ ），则那么 $x - y - z$ （20在联合密度 $P ( V _ { N } )$ 下对应于一个 $\mathrm { \Delta V }$ 结构。

证明 根据推论1和 2， $\exists N _ { x z } \subseteq ( N _ { x } \cup N _ { z } )$ 且 $x \perp z \big | N _ { x z }$ ，如果 $x - y - z$ 并不对应于联合密度 $P ( V _ { N } )$ 下的 $\mathrm { ~ v ~ }$ 结构，即（204号 $x \to y \to z$ 或 $x \gets y \gets z$ ，则有 $y \notin N _ { x z }$ 满足D分离条件（阻断路径 $x - y - z ^ { } )$ 。即 $y$ 必须包含在 $\mathrm { ~ D ~ }$ 分离集合 $N _ { _ { x z } }$ 中，这与$y \notin N _ { x z }$ 矛盾。因此 $x - y - z$ 只能构成一个 $\mathrm { \Delta V }$ 结构。

可以看到，推论1和3说明了如何在 $\left\{ x , y , z , N _ { x } , N _ { y } \right\}$ 中发现一个V结构，并可以归纳为如下推论4。

推论4给定一个无向图 $G _ { \scriptscriptstyle N } = \left\{ V _ { \scriptscriptstyle N } , E _ { \scriptscriptstyle N } \right\}$ ，且包含子图$G _ { y } = \left\{ V _ { y } , E _ { y } \right\}$ ，一个结构 $x - y - z$ 在联合密度 $P \big ( { V } _ { N } \big )$ 下对应于一个V结构，当且仅当满足以下两个条件：a）（20 $\exists N _ { x z }$ ， $N _ { { x z } } \subset ( N _ { x } \cup N _ { z } )$ ，使得 $x \perp z \big | N _ { x z }$ ；b）$\exists N _ { x z }$ ， $N _ { x z } \subset ( N _ { x } \cup N _ { z } )$ ，使得 $x \ne z \lvert ( N _ { x z } \cup y )$ 。

可以看到推论4显著缩小了定理1中描述的条件集 $z$ 的搜索范围。因此，能更高效地识别V型结构，尤其是在高维网络中。而V结构通常广泛存在于高维网络中,通过使用推论4，可以检验在目标 $G _ { y }$ 中给定的一个结构 $x - y - z$ 0 $\dot { \boldsymbol { x } }$ 和 $z$ 不是直接连接)是否满足推论中的两个条件，如果是就可以推断出$x \to y \gets z$ 。

然而仍然有一个问题，底层的CI 测试方法在最坏的情况下必须运行 $2 ^ { \left| { N _ { x } \cup N _ { z } } \right| }$ 次。直观上，两个节点通常不会被大量的共同邻居节点 $\mathrm { ~ D ~ }$ 分离，从计算方面来说，当条件集足够大时，CI测试方法很难保障其准确率。因此，在CI测试中，本文设置了一个阈值 $k$ 来限制 $N _ { _ { x z } }$ 的数量，可以根据先验信息或实验结果通过CI测试方法和数据分布类型来选择 $k$ 。对V型结构的搜索算法总结在算法1中。

算法1

Algorithm 1 Searching $\mathsf { v }$ -structure

Input: $G _ { y } = \{ V _ { y } , E _ { y } \}$ ,threshold $k$

Output:V-structures

1:for $\forall$ node pair $x \ , \ z \ ( \ x , z \in N _ { y }$ ， $x$ and $z$ are not directly connected）do

2:Remove $\forall n o d e \in ( N _ { x } , N _ { z } )$ beside the adjacency paths between $x$ and $z$ 1

3:for $\forall N _ { x z } \subset ( N _ { x } \cup N _ { z } ) \ , \left| N _ { x z } \right| < k$ do

4:if $x \perp z \big | N _ { x z }$ and $x \nearrow z \lvert ( N _ { x z } \cup y )$ then

5:let $x \ , \ z$ be the parents of $y$ （ $\mathsf { v } \cdot$ structures)

6: end if

7: end for

# 8:end for

# 2.2 NTS、ODS、TES 学习算法

考虑NTS结构的实现过程：

运用算法1在目标节点 $y$ 及其邻居节点集 $N _ { y }$ 之间进行搜索，例如如果算法1判断 $x - y - z$ 为一个V 结构，则判断 $x$ $z$ 为 $y$ 的父亲节点。根据定义2，NTS结构中不包含三角结构，通过算法1可以找到NTS中所有的V结构，从而关于 $y$ 的所有父亲节点可以得到识别。类似的方法在很多其他的文献中已经有很广泛的运用[19]。

考虑ODS结构的实现过程：

根据定义1，ODS 结构只包含两个节点，因为叶子节点与其父亲必然构成确定性关系，也就是 $x = f ( y ) + e$ ，它满足ANM条件 $y \to x$ 。因此，利用ANM中回归残差与自变量独立的特性，也就是 $\mathbf { \Psi } _ { e }$ 独立于 $y$ ，可以很容易推断出目标节点的儿子为$x$ ；反之，则 $x$ 为 $y$ 的父亲节点。

考虑TES结构的实现过程：

TES是因果方向推断中的难题，在以往的文献中[20],需要遍历所有节点找出符合ANM的 $y$ 及其一组父亲节点，也就是（204号 $y = f ( P A _ { y } ) + e$ ，其中 $e$ 独立于节点集 $P A _ { y }$ 中的每一个变量。这种方法有两大问题：一是满足ANM的父亲节点集有可能不是唯一的，找到的 $P A _ { y }$ 仅仅是 $y$ 的一部分父亲节点；二是枚举法在 $| N _ { y } |$ 较大时，计算机无法在可接受的时间内返回结果。本文的工作要克服的最重要一个难题就是如何在TES中快速寻找 $y$ 的所有父亲节点。本文提出定理2：

定理2若 $G _ { y }$ 至少存在一个 $\mathrm { ~ v ~ }$ 结构，即VES 结构，则1)$y$ 的所有父亲节点均包含在V结构中；或2）如果存在 $y$ 的一个父亲节点 $P a _ { y } I$ 不包含在任何 $\mathrm { ~ v ~ }$ 结构中，比如V结构$P a _ { \mathrm { y } } 2 \right. \mathrm { y } \left. P a _ { \mathrm { y } } 3$ ，若 $P a _ { y } I$ 包含在 $P a _ { y } 2$ ， $P a _ { y } 3$ 的条件独立集中，则边方向为Pa,1 →y。

证明根据定义1、2、3,知道 $G _ { y }$ 必为ODS、NTS、TES中的一个。如果存在 $\mathrm { \Delta V }$ 结构，则 $G _ { y }$ 只能是NTS 或者TES。若 $G _ { y }$ 属于NTS，则根据 $\mathrm { \Delta V }$ 结构定义4，可以直接推断出 $y$ 的所有父亲节点均包含在 $\mathrm { \Delta V }$ 结构中。若 $G _ { y }$ 属于TES，用反证法，假设存在 $y$ 的一个父亲节点 $P a _ { y } I$ 不包含在关于 $y$ 的 $V$ 结构中，由于 $G _ { y }$ 最少包含一个V 结构，假设其为 $P a _ { y } 2 \right. y \left. P a _ { y } 3$ ，则$P a _ { y } I$ 与 $P a _ { y } 2$ 必然存在一条直接相连的边，否则$P a _ { \mathrm { y } } 1 \right. \mathrm { y } \left. P a _ { \mathrm { y } } 2$ 形成了一个 $\mathrm { \Delta V }$ 结构，矛盾。同理可以知道$P a _ { y } I$ 与 $P a _ { y } 3$ 同时存在一条直接相连的边。由于$P a _ { \mathrm { y } } 2 \right. \mathrm { y } \left. P a _ { \mathrm { y } } 3$ 是一个 $\mathrm { \Delta V }$ 结构，因此 $P a _ { y } I$ 、 $P a _ { y } 2$ 之间不存在直接相连的边，若 $P a _ { y } I$ 包含在 $P a _ { y } 2 , P a _ { y } 3$ 的条件独立集中，则若 $P a _ { y } I \ 、 \ P a _ { y } 2 \ 、 \ P a _ { y } 3$ 三者关系为： $P a _ { y } 2  P a _ { y } 1  P a _ { y } 3$ ，$P a _ { y } 2 \gets P a _ { y } 1 \to P a _ { y } 3$ 或 $P a _ { y } 2 \gets P a _ { y } 1 \gets P a _ { y } 3$ 。根据因果网络推断的一致性传播特性，可以知道 $P a _ { y } I$ 与 $y$ 的因果关系为$P a _ { \mathrm { y } } 1  y$ ，否则存在局部环结构。

定理2指出，如果一个TES存在 $\mathrm { \Delta V }$ 结构，也就是一个VES，则在大部分情况下，关于 $y$ 的父亲节点都可以根据条件独立性检测得到的。因为根据定理2的证明，仅在 $P a _ { y } 2 \right. P a _ { y } 1 \left. P a _ { y } 3$ 的情况， $P a _ { y } I$ 与 $y$ 的因果关系无法区分，其余所有情况，TES里的因果关系都是可以通过V结构蕴涵的条件独立性得到识别的。另一方面，如果TES不存在V结构，则这种情况只能是根据ANM进行识别。在大量数据集中，完全不包含V结构的TES在真实网络中是很少见的，也就是说在一般的真实网络中，TES都可以得到有效的识别。根据上述对NTS、ODS、TES三个结构的讨论，本文给出一个有效的对高维因果网络进行方向学习的算法。

a)将 $n$ 维网络 $G _ { n }$ 分解为 $n$ 个关于每一个节点的诱导子图$G _ { y }$ ，将 $G _ { y }$ 集分类，分别为NTS，TES和ODS。

b)在NTS中，根据定理2首先在 $N _ { y }$ 中搜索关于 $y$ 的所有V结构；然后考虑剩余非 $\mathrm { \Delta V }$ 结构节点 $x _ { k }$ ，如果 $x _ { k }$ 存在于任意一个V结构（不包含 $y$ ）的条件独立集中，则将 $x _ { k }$ 归类到 $y$ 的父亲节点集；最后利用ANM找出关于 $y$ 的其他可能的父亲节点。

c)在 TES中，根据定义3，判断 $x _ { i } - y - x _ { j }$ 是否为一个V结构，则判断 $x _ { i }$ ， $x _ { j }$ 为 $y$ 的父亲节点。

d)在ODS中，根据ANM的性质，因为ODS 结构只包含两个节点，叶子节点与其父亲必然构成确定性关系，也就是$x = f ( y ) + e$ ，满足ANM条件 $y \to x$ 。因此可利用ANM中回归残差与自变量独立的特性，也就是 $e$ 独立于 $y$ ，可以很容易推断出目标节点的儿子为 $x$ ；反之，则 $x$ 为 $y$ 的父亲节点。

e)将所有判明方向（关于 $y$ 父亲节点已经被识别的）的诱导子图合并，得到一个完整的有向无环图 $G _ { D }$ 。

# 2.3提出方法（ $\mathsf { V E } + \mathsf { A N M } ,$ ）的框架

算法2 （ $\mathbf { V E } { + } \mathbf { A N M }$ ）框架

Algorithm 2 The framework of $( V E + A N M )$ 0   
Input:undirected graph GN ={VN,EN}   
Output: DAG $G _ { \scriptscriptstyle D } = \big \{ { V } _ { \scriptscriptstyle D } , E _ { \scriptscriptstyle D } \big \}$ （20   
1: Divide $G _ { \scriptscriptstyle N }$ into $\left| V _ { N } \right|$ induced subgraphs，one of which corresponds to one and only one of the substructures ODS, NTS or TES   
2:for each induced subgraph $G _ { y } = \left\{ V _ { y } , E _ { y } \right\}$ do   
3: if $G _ { y }$ : TES then   
4: for $\forall x _ { i } , x _ { j } \in N _ { y }$ do   
5: search V-structure:x →y← xj   
6: if such $x _ { i } \ \right. \ y \ \left. \ x _ { j }$ does exist then   
7: let $x _ { i }$ and $\boldsymbol { x } _ { j }$ be $P A _ { y }$ ，others be $C H _ { \mathrm { y } }$ ；   
8: else $\mathbf { i } \textsf { f } \ x _ { k }$ in $N _ { y }$ is contained in the separated set of $x _ { i }$ and $x _ { j }$

# Let $x _ { h }$ be the $P A _ { y }$

# else

9: employs ANM to find $P A _ { y }$ ;   
10: if $P A _ { y } \neq \emptyset$ then   
11: let $N _ { \mathrm { y } } \setminus P A _ { \mathrm { y } }$ be $C H _ { \mathrm { y } }$ （204号   
12: else   
13: let $N _ { _ { y } } \mathrm { ~ } \backslash \mathrm { ~ } T _ { y }$ be $C H _ { \mathrm { { y } } }$   
14: end if   
15: end if   
16: end for   
17:end if   
18:if $G _ { y } \ : \mathsf { N T S }$ then   
19: the same to line 4-16 $\left( T _ { y } = \emptyset \right)$   
20:end if   
21:if $G _ { y } \mathrm { ~  ~ { ~ : ~ } ~ } 0 0 5$ then   
22: employs ANM to infer the direction.   
23: end if   
24:end for   
25: Merging all the partial results (plus   
step if exists any un-oriented edge)，out p

# 3 实验

在本章实验中将采用由12个真实的因果网络生成的数据集来对本文提出的方法进行评估。这些真实网络涉及各个领域，包括生物与医学(Cancer、Asia,Spiegel-HalterDLC93、Alarm、Diabetes、Mildew)、车辆诊断(Car-diagnosis)、石油勘探(Oil-wildcatter)、场景分析(Boerlage92)、天气预报(Hailfinder)、打印机故障排除(Win95pts)和基因网络(Link)，数据集由这些真实网络基于因果推断领域的经典方法[12]生成的。

在本节实验中，将 $\mathrm { V E + A N M } ,$ 方法与4种主流的因果推断  
算法进行比较，其中包括基于V结构的因果推断算法SVS、基  
于V结构与一致性传播结合的因果推断算法POE、加噪声模型  
因果推断算法ANM和信息几何模型因果推断算法IGCI。本文  
以实验报告的准确率为评价标准，并定义准确率为：  
准确率=推断的方向实际的方向实际的方向

# 3.1 与 SVS、POE、ANM 和IGCI比较：

如表1所示，在12个网络中 $\left( { \mathrm { V E + A N M } } \right)$ 方法的准确率明显优于其他对比方法。 $\left( { \mathrm { V E } } { + } \mathbf { A N M } \right)$ 方法在小网络(如 Asia)上的准确性已经达到了 $94 \%$ ，在大网络的准确率也达到了 $80 \%$ 和 $78 \%$ 这表明本文提出的方法在不同维度网络都具有良好的鲁棒性。特别地，注意到 $\mathrm { ( V E + A N M ) }$ 方法在网络Link的性能是最差的(只有 $78 \%$ )。这是因为该网络有 $40 \%$ 的边包含在三角形结构中，这使得该网络的结构比其他网络结构更加复杂。注意到，在本实验中样本量都达到2000，大部分算法都接近了最理想的实验环境，因此这些准确率代表的是这些方法在准确率上的峰值。

另一方面，可以看到网络从低维到高维，除开ANM会受到维度影响外，其余算法都相对稳定，准确率并没有受到维度的影响。特别地，IGCI在多节点情况下趋向于随机判断，因此准确率几乎就在 $60 \%$ 左右波动。而SVS与POE是基于V结构识别的算法，因此理论上不会受到维度的影响。可见，尽管$\left( { \mathrm { V E } } { + } \mathbf { A N M } \right)$ 方法运用了残差与自变量独立的原理进行识别，但根据本文的理论，此方法也不会被高维影响，在所有网络结构下都保持了较高的准确率。

可以看到，无论SVS还是POE都不能相对准确地发现对应的实际图形，特别是当网络结构很小且只有很少V结构的时候(如Cancer、Asia)，因为总有一些不定向的边未不能被一致性地扩展。以Asia网络为例(图1)，两个V 结构x→x←x4和 $x _ { 6 } \to x _ { 8 }  x _ { 5 }$ 是可以被推断出来的,那么使用一致的扩展可以很容易获得 $x _ { 6 } \to x _ { 7 }$ ，然而其他三条边不能通过任何一致性的扩展来定向。而SVS和POE之间的区别仅仅是识别V结构的方法，它们的性能很大程度上受到V结构数量的影响，由于$\left( { \mathrm { V E } } { + } \mathbf { A N M } \right)$ 方法有更强的适应性所以在多维网络上有更好的表现。

![](images/dbdb641c950e9a0861e7c6f659eccdf77f8fb9030be23ff35236c5d9eb0f3d82.jpg)  
图1Asia 网络

ANM表现得与其他方法截然不同。如表1所示，可以看出 ANM的准确率受复合确定性关系的节点对数影响，其主要原因是ANM在许多不确定的情况下无法得出关于方向的结论，也无法确定这些边的方向。然而这种情况却广泛存在于多维网络中。类似地，IGCI只适用于双变量情况，它的性能也取决于节点对数。特别地，IGCI推断的结果有时会比随机选择差(如SHDLC93、Boerlage92)。这是因为信息几何模型不适用于多维（ $n > 2$ ）网络。

表1在12个网络的运行结果  

<html><body><table><tr><td rowspan="2">网络</td><td colspan="5">准确率</td></tr><tr><td>(VE+ANM)</td><td>SvS</td><td>POE</td><td>ANM</td><td>IGCI</td></tr><tr><td>Cancer</td><td>0.89</td><td>0.55</td><td>0.57</td><td>0.66</td><td>0.66</td></tr><tr><td>Asia</td><td>0.94</td><td>0.74</td><td>0.79</td><td>0.61</td><td>0.64</td></tr><tr><td>Oil-wildcatter</td><td>0.85</td><td>0.82</td><td>0.82</td><td>0.48</td><td>0.69</td></tr><tr><td>Car-diagnosis</td><td>0.92</td><td>0.84</td><td>0.81</td><td>0.42</td><td>0.71</td></tr><tr><td>SHDLC93</td><td>0.84</td><td>0.82</td><td>0.83</td><td>0.48</td><td>0.49</td></tr><tr><td>Boerlage92</td><td>0.83</td><td>0.82</td><td>0.82</td><td>0.45</td><td>0.46</td></tr><tr><td>Mildew</td><td>0.88</td><td>0.83</td><td>0.87</td><td>0.12</td><td>0.63</td></tr><tr><td>Alarm</td><td>0.87</td><td>0.85</td><td>0.83</td><td>0.33</td><td>0.61</td></tr><tr><td>Hailfinder</td><td>0.91</td><td>0.81</td><td>0.84</td><td>0.44</td><td>0.61</td></tr><tr><td>Win95pts</td><td>0.92</td><td>0.85</td><td>0.82</td><td>0.25</td><td>0.70</td></tr><tr><td>Diabetes</td><td>0.80</td><td>0.75</td><td>N.A.</td><td>0.26</td><td>0.52</td></tr><tr><td>Link</td><td>0.78</td><td>0.77</td><td>N.A.</td><td>0.29</td><td>0.61</td></tr></table></body></html>

# 3.2在三种子结构上的效果比较

在本节实验中采用两个结构相对复杂的真实网络结构，Hailfinder网络(其中有 $12 \%$ 的边包含在三角形结构中)和Oil-wildcatter网络(其中有 $48 \%$ 的边包含在三角形结构中)以及$\{ 3 0 , 5 0 , 1 0 0 , 2 0 0 , 5 0 0 , 1 0 0 0 , 5 0 0 0 \}$ 样本下处理三种子结构ODS、NTS、TES来评估 $\mathrm { \Delta V E + A N M ) }$ 方法。

图2所示是在Hailfinder网络下对 $\mathrm { V E + A N M } ,$ 进行评估。其中ODS的性能略优于NTS和TES，当样本容量超过1000时，其准确率能达到 $96 \%$ 。这是因为样本尺寸相对较小时，可能会根据ODS的方向来更新ODS与TES或ODS与NTS之间的冲突。在ODS案例中，本文只测试两个变量之间的依赖关系，不需要任何条件集，且ODS的结构非常简单。虽然NTS和TES的性能受到CI测试方法的显著影响，但CI测试的准确性依赖于给定的(局部)结构。因此，当结构相当复杂时，CI测试总是需要较大的样本量。可以看到，当样本量达到很大的时候ODS、NTS和TES的曲线趋向于重叠。此外，NTS比ODS和TES需要更多的样本，可以看到样本大小从30到5000个，NTS的准确性的变化最明显，从 $52 \%$ 到 $94 \%$ 。

图3所示是在另一个网络Oil-wildcatter评估 $\left( { \mathrm { V E } } { + } \mathbf { A N M } \right)$ 方法。可以看到四个曲线的上升趋势与在Hailfinder 网络的性能相似。但是TES的性能比其他的要差。特别注意到，在该网络下有 $40 \%$ 的边在三角形结构中，且存在一些边不能定向或做任何一致性扩展。

![](images/cf9df89f6d3f4993cbd6c5794429ee2ee16125dca8b175939f6de82269dfabb4.jpg)  
图2在Hailfinder 网络各方法的性能

![](images/0eb4c885b84a678e6304aa63efb67ff75a3175f659973b1e0896640a758844c9.jpg)  
图3在Oil-wildcatter 网络各方法的性能

实验表明， $\mathrm { V E + A N M }$ 混合方法比现有的单一方法明显有更高的鲁棒性，更能适用于复杂网络的因果推断问题上。然后受限于TES的高复杂性，VE+ANM在TES上面的表现要远低于另外两种结构，一方面是多次条件独立性测试容易产生连锁的错误传递效应，另一方面是网络结构一旦复杂，很可能有一些子结构会违反因果忠实性与马尔可夫性，导致条件独立性不等价于D分离性，这目前仍然是因果推断领域的难题。

# 4 结束语

本文提出了一种通用的可扩展的方法，即 $\mathrm { ( V E + A N M ) }$ 方法，使用分裂合并策略，支持多维网络的因果方向推断。虽然大多数现有的方法都是建立在V型结构的学习或不对称检测上，但$\left( { \mathrm { V E } } { + } \mathbf { A N M } \right)$ 方法考虑到三种可能的子结构类型，从一个任意的网络中发现了一个更一般的因果方向。较强的理论分析证明了在一般多维网络下 $\mathrm { V E + A N M } )$ 方法的有效性和准确性。虽然有时 $\mathbf { \left( V E { + } A N M \right) }$ 在某些特殊情况下也无法达到完整性，但实验结果验证了本文方法比最先进的方法更为普遍和有效。

# 参考文献：

[1]Cai R,Zhang Z,Hao Z. Causal gene identification using combinatorial vstructure search [J].Neural Networks,2013,43: 63-71.   
[2]Cheng J,Bell D,Liu W.Learning Bayesian networks from data: An efficient approach based on information theory[J/OL].(1998）.http://www.cs. ualberta. $\mathrm { c a / \tilde { \Sigma } }$ jcheng/bnpc.htm.   
[3] Chickering D M.Learning equivalence classes of bayesian-network structures [J].The Journal ofMachine Learning Research,2002,2:445-498.   
[4]Daniusis P,Janzing D,Mooij J,et al. Inferring deterministic causal relations [J].Machine Learning,2012,arXiv: 1203.3475.   
[5]Hao Z,Zhang H, CaiR,et al. Causal discovery on high dimensional data [J]. Applied Intelligence,2014,42 (3): 594-607.   
[6]Hoyer P O,Janzing D,Mooij JM,et al. Nonlinear causal discovery with additive noise models [Cl// Proc of the 21st International Conference on Neural Information Processing Systems.2009: 689-696.   
[7]Janzing D,Mooij J, Zhang K,et al. Information-geometric approach to inferring causal directions [J].Artificial Intelligence,2012,182:1-31.   
[8]Janzing D,Steudel B,Shajarisales N,et al. Justifying information-geometric causal inference [M].[S.1.] : Springer International Publishing,2014: 253- 265.   
[9]Mooij J, Janzing D,Peters J,et al. Regression by dependence minimization and its application to causal inference in additive noise models [C]// Proc of the 26th Annual International Conference on Machine Learning.2oo9: 745- 752.   
[10] Pearl J. Causality: models,reasoning,and inference [M].[S.1.] : Cambridge University Press,2000:639.   
[11] Peters J,Janzing D,Sch"olkopfB.Identifying cause and effect on discrete data using additive noise models [C]//Proc of International Conference on Artificial Intelligence and Statistics.2010:597-604.   
[12] Cai R,Zhang Z,Hao Z.Sada:a general framework to support robust causation discovery [C]// Proc of the 3Oth International Conference on International Conference on Machine Learning.2013:208-216.   
[13] Shimizu S,HoyerP O,Hyv"arinen A,et al.A linear non-gaussian acyclic model for causal discovery[J].Journal of Machine Learning Research,2006, 7(4):2003-2030.   
[14] Shimizu S,Inazumi T, Sogawa Y,et al. Directlingam: a direct method for learning a linear nongaussian structural equation model [J].Journal of Machine Learning Research,2011,12 (2): 1225-1248   
[15] Spirtes P,Glymour CN, Scheines R. Causation, prediction,and search [M]. [S.1.] : Springer New York,1993:272-273.   
[16] ZhangK,Hyv"arinen A.On the identifiability of the post-nonlinear causal model [C]// Proc of the 25th Conference on Uncertainty in Artificial Intelligence.[S.1.] :AUAI Press.2009: 647-655.   
[17] Zhang K,Peters J,Janzing D,et al.Kernel-based conditional independence test and application in causal discovery [J].Computer Science.2O12,6 (8): 895-907.   
[18]Peters J,Mooij JM,Janzing D,et al.Causal discovery with continuous additive noise models [J]. Journal of Machine Learning Research,2O13,15 (1):2009-2053.   
[19]张浩，郝志峰，蔡瑞初，等．一种适用于高维网络的方向推断算法[J]. 小型微型计算机系统,2015,36(6):1358-1362.   
[20] Mai Guizhen,Hong Yinghan,Peng Shiguo,et al. Inferring causal direction from multi-dimensional causal networks for assessing harmful factors in security analysis [J].IEEE Access.2017,5:20009-20019.   
[21] Zhang K,Hyv"arinen A.Distinguishing causes from effects using nonlinear acyclic causal models [J]. Journal of Machine Learning Research,2008,6: 157-164.   
[22] Peters J, Janzing D, Sch"olkopf B.Causal inference on discrete data using additive noise models [J].IEEE Trans on Pattern Analysis & Machine Intelligence,2011,33(12): 2436-2450.