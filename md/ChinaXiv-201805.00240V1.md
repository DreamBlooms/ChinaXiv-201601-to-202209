# 系统功能结构最简式分析方法

崔铁军 la,²，李莎莎la，王来贵 1b

(1.辽宁工程技术大学a.安全科学与工程学院;b.力学与工程学院，辽宁 阜新 123000;2.大连交通大学 辽宁省隧道与地下结构工程技术研究中心，辽宁 大连 116028)

摘要：为使空间故障树理论具有分析离散可靠性数据的能力，基于因素空间理论提出了一种分析系统功能结构最简式的方法，主要用于了解系统功能与元件功能之间的因果关系和内涵。给出了系统功能结构最简式方法的步骤和相关定义；使用一个系统的32条故障状态组成背景空间，分析其中蕴涵的系统功能与元件功能关系。同时随机选择 23条故障状态组成了一个背景空间子集，得到蕴涵的功能关系。对比两种功能关系的最简结构式差异，根据布尔代数，得到元件之间的隐含功能关系为：元件Z3的功能与Z1或Z2或 $Z 1 { + } Z 2$ 的功能相同。从而得到关于系统可靠性的元件等效和替换关系。同时背景空间的两个子集最简结构式的和不等于原背景空间最简结构式，给出了两者相等的条件。

关键词：安全科学；因素空间；空间故障树；功能结构分析；背景空间子集；最简结构式中图分类号：TP302.7 doi:10.3969/j.issn.1001-3695.2017.06.0644

# Simplest formula analysis method of system function structure

Cui Tiejunla,2, Li Shashala, Wang Laigui1b (1.a.CollgeofSafetyScience&Enginering,b.SchoolofMechanics &EngineeringLiaoning Technical UniversityFuxin Liaoningl230o0,China;2 Tunnel& Underground Structure EngineeringCenterofLiaoning,Dalian Jiaotong University Dalian Liaoning116028,China)

Abstract: Inorderto make thespace fault ree theoryhavetheabilitytoanalyze thediscretereliabilitydata,asimplest formula analysis methodof thesystem functionstructurebasedonthe factor space theoryis proposed.The method is mainlyused to understandthecausal relationship betweenthe system functionandthecomponent function.Thesteps ofthe simplest formula analysis methodof the system function structure and related definitionsare given.The system iscomposedof32 fault states, which canbeusedtoanalzetherelationship betweensystemfunctionandcomponentfunction.Atthesame time,23faultstates arerandom chosen to forman background relationsubset,andthe functionrelation isobtained.Bycomparing thediference between thetwo kinds offunctionrelations,ccording totheBooleanalgebra,wecangettheimplicitfunctionrelationbetween components: the function of component Z3 is the same as that of Zl or Z2 or $Z 1 + Z 2$ . Thus, the component equivalence and substitutionrelationofsystemreliabilityareobtained.At the same time,the sumofthe minimal extraction paradigms of thetwo background relation subsets is not equal to thatoforiginal background relation,and the conditionof equalityis given.

Key Words:safety science;factor space; spacefault tree;functional structure analysis; background relation subset; minimal analytic paradigm

# 0 引言

一般系统设计是正向的，由系统整体功能出发，通过一定的功能分解，最终落实到元件或子系统。正向设计容易满足系统的设计目的，从而完成某项确定功能。但根据功能所设计的系统是否为结构最优却很难确定。该问题一方面从系统功能考虑，另一方面则从经济上考虑。另外，如果已知某个系统可能由一些特定的元件或子系统组成，且知道其系统功能随元件功能的变化规律，但系统无法打开或根本得不到，那么该系统将无法被仿制。这些问题可概括为系统功能结构分析问题。即知道系统组成的基本单元功能特征和系统所表现出的功能特征，研究系统功能结构与元件的组成关系。当然该内部组成结构可能是一个等效的功能结构，不是真正的物理结构。

系统功能结构分析是识别和认识系统的有效工具，一些学者也进行了这方面研究[I\~10]。这些研究虽然在各领域取得了良好效果，但终究是正向地研究系统功能结构。对于前文提出的问题难以解决。另一方面，系统功能结构分析是一种复杂的推理过程。相关研究较少是由于技术工程学者对于制定一套严谨可行的逻辑数学推理系统是难以实现的。作者早些提出的系统结构反分析方法也存在推理不严谨和逻辑性差的缺点。所以急需专业学者与数学家合作来完成这项工作，这是本文的主要目的。

任何一个系统都有其特定的结构、环境与功能，结构和环境是内外因，功能是果。为改善功能而调整结构，从功能来探索结构是一种复杂得科学问题。因素空间理论为系统的功能结构分析提供了一个简捷的平台。因素空间理论只需确立论域及对条件、结果等因素的观测手段，得到一组样本点，形成一张因素分析表，就可进行功能结构分析。

作者将因素空间理论引入空间故障树分析中。用因素空间的思想帮助空间故障树分析离散可靠性数据蕴涵的系统功能与元件功能之间的关系。提出一种系统功能结构最简式分析方法来完成上述任务。并举例分析背景空间和两个背景空间子集的最简结构式，及隐含的元件功能关系。给出背景空间的两个子集最简结构式的和等于原背景空间最简结构式的条件。

# 1 空间故障树与因素空间介绍

为了解系统工作环境因素对系统可靠性的影响，作者提出了一套空间故障树（Space Fault Tree，SFT）理论[1I]，该理论认为系统工作于环境之中，由于组成系统的基本事件或物理元件的性质决定了其在不同条件下工作的故障发生概率不同。SFT有三个分支：连续型空间故障树（continuous space fault tree，CSFT)，离散型空间故障树（discrete space fault tree，DSFT）和系统结构反分析（inward analysis of structural systems，IASS）。

CSFT是一种知道系统内部构造和元件性质，再研究系统在外界作用下响应行为的一种“白盒”方法。提出了SFT基本思想[12]，参照经典故障树给出了概念和方法。研究了SFT的径集域与割集域[13]，因素重要度分布[14]。同时利用上述基本概念完成了一些研究，包括：维持系统可靠性方法[15]，系统可靠性决策规则发掘方法[16]，系统可靠性评估方法优化[17]等。

DSFT不需要了解系统内部构造和元件性质，研究基础是系统对外界环境变化的响应特征，相当于“黑盒”方法。给出了DSFT的定义和性质[18]，然后在此定义下研究了DSFT的建立及故障概率空间分布[19]。使用模糊结构元方法改造了特征函数，包括模糊结构元特征函数构建[20]和模糊结构元的 SFT 概念重构等。

IASS在不清楚系统内部具体构造情况下，通过系统对外界环境因素变化的响应来剖析和窥探系统内部结构。形成一种等效的伪结构。研究了二值的01型SFT的表示和分析方法。包括逐条分析法和分类推理法[21]。

为了适应信息革命和大数据时代的需要，要更多地切入智能数据领域。在这方面，中国早期学者汪培庄教授于1983年提出了因素空间（Factor Space，FS）的数学理论[22]为大数据的分析和处理奠定了数学基础。目前FS得到了广泛的研究和承认，相关研究如下：背景空间的信息压缩、FS 处理非结构化数据[23]、因素粒化空间的嵌套结构与数据认知生态系统[24]、评价与决策理论[25,26]、FS 与公共安全[27]、代数、拓扑、微分几何、范畴理论的综合研究等。

FS 理论在智能科学和大数据领域中取得了较大突破，但并未融入到具体科学技术中，SFT与FS的结合为后者在安全科学的可靠性及故障分析领域提供了发展空间。结合SFT与FS理论完成了一些研究。包括：FS的属性圆定义及其在对象分类中的应用[28]，考虑范围属性的系统安全分类决策规则研究[29],基于FS的煤矿安全情况区分方法研究[30]，同时也进行了一些系统可靠性分析研究[3I]。这些研究证明了FS与SFT结合的可行性。

# 2 系统功能结构最简式方法

给定因素功能结构分析表，要求出指定功能类的最简结构式，其步骤如下：

因素功能结构分析表中的功能类分为两种，即成功类T和失效类F，表中最后一行功能因素 $g$ 的相即表示功能T或F。功能因素 $g$ 表示对象结构因素在取不同相时的对象功能。

设因素功能分析表中有 $M$ 个对象 $u _ { m }$ $, m { = } 1 , 2 , \cdots , M$ ；有 $N$ 个结构因素 $f _ { n }$ ， $\mathfrak { n } { = } 1 , 2 , \cdots , N$ ，和一个功能因素 $g$ ，所以表中因素可统一表示为 $f _ { n + 1 }$ ；对象 $u _ { m }$ 在因素 $f _ { n + 1 }$ 下的相 $x _ { n + 1 }$ 的数量与因素相同。对象 $u _ { m }$ 的相集为 $\{ x _ { n + 1 } \} _ { m } = \{ x _ { n + 1 } | f _ { n + 1 } ( u _ { m } ) { = } x _ { n + 1 } , n { = } 1 , 2 , \cdots , N \}$ $f _ { n + 1 } ( u _ { m } )$ 表示对象 $u _ { m }$ 在因素 $f _ { n + 1 }$ 下的相。为表现方便，相集可改写为相的串 $\scriptstyle x _ { n \mid m } = x _ { 1 } x _ { 2 } \cdots x _ { N }$ ，用以相集按照 $\mathrm { ~ T ~ }$ 或F分类后进行表示。因素功能分析表可作为因素空间分析中的背景空间 $B$ ，则$B { = } \cup x _ { n + 1 \mid 1 { - } m , n { = } 1 , 2 , \cdots , N }$ 且 $\scriptstyle m = 1 , 2 , \cdots , M _ { \circ }$ 设对象相集中相的个数为相集长度 $\lambda$ 。

a）对因素功能结构分析表中的对象 $u _ { m }$ 与因素 $f _ { n + 1 }$ 对应的相 $x _ { n + 1 }$ 进行组合，将同一对象 $u _ { m }$ 对不同因素 $f _ { n + 1 }$ 的相 $x _ { n + 1 }$ ，即因素功能结构分析表的一列组成相集 $x _ { n + 1 | m }$ 表示该对象 $u _ { m }$ 。

b)在因素结构分析表中的所有列，即所有对象的相集 $x _ { n + 1 | m }$ 再组成集合，作为背景空间 $B$ ， $B { = } \cup _ { { \boldsymbol { x } } _ { n + 1 | 1 { \sim } m } }$ + $\boldsymbol { n } { = } 1 , 2 , \cdots , { } _ { N }$ 且$\scriptstyle m = 1 , 2 , \cdots , M _ { \circ }$

c）根据背景空间 $B$ 中所有相集 $x _ { n + 1 | 1 \sim m }$ 的功能因素 $g$ 对对象 $u _ { m }$ 进行T或F分类。

d）将背景空间所有相集中的相拆分为长度 $\scriptstyle \lambda = 1$ 的相，所有的背景空间中出现的无重复相组成筛选相集 $\boldsymbol { \varGamma }$ 。分别使用筛选相集 $\boldsymbol { { \Gamma } }$ 中的相 $\boldsymbol { \mathscr { A } }$ （当 $\lambda { > } 1$ 时， $\boldsymbol { \mathscr { A } }$ 为相集）遍历F类中所有相集，如果这些相集均不包含相 $\mathbf { \Omega } _ { A }$ 且T类中相集包含，那么相 $\boldsymbol { \mathscr { A } }$ 为 T 类的一个结构式 $\xi ( \mathrm { T } )$ ，从T类相集中删除包含相 $\boldsymbol { \mathscr { A } }$ 的相集。

e)设 $\lambda = \lambda + 1$ ，这是在筛选相集 $\boldsymbol { \Gamma }$ 中任意取 $\lambda + 1$ 个相组成的相集 $\boldsymbol { \mathscr { A } }$ 。分别使用相集 $\boldsymbol { \mathscr { A } }$ 遍历 $F$ 类中所有相集，如果均不包含相集 $\boldsymbol { \mathscr { A } }$ 且T类中相集包含，那么相集 $\boldsymbol { \mathscr { A } }$ 为 $T$ 类的一个结构式$\xi ( \mathrm { T } )$ ，从T类相集中删除包含相集 $\boldsymbol { \mathscr { A } }$ 的相集。

f）重复步骤e）直到T类中的相集全部删除为止。

g）将所有结构式 $\xi ( \mathrm { T } )$ 用逻辑并“ $\mathrm { \Phi } + \mathrm { \Phi } ^ { , , , }$ 连接，即为背景空间$B$ 所表示的成功类T的最简结构式 $ { \zeta } (  { \mathrm { T } } )$ 。

相关定义因素空间、相集、功能结构分析表、背景空间等见文献[32,33]。

# 3 系统功能结构分析

用空间故障树中系统结构分析实例进行分析。该例为开关系统Z，它由5种元器件 $\scriptstyle { Z _ { 1 } , \ldots , Z _ { 5 } }$ 组成，他们的功能情况由5个功能因素 $F { = } ( f _ { 1 } , f _ { 2 } , f _ { 3 } , f _ { 4 } , f _ { 5 } )$ 表示，每个功能因素具有相空间$X ( f _ { j } ) { = } \{ x _ { 1 j } , x 0 _ { j } \} { = } \{ x _ { j } , { \underline { { x _ { j } } } } \}$ ， $j { = } 1 , . . . , 5$ ， $x _ { 1 j }$ 表示 $Z _ { j }$ 通， $x _ { 0 \underline { { i } } }$ 表示器件 $Z _ { j }$ 断；功能因素 $g$ 具有相空间 $X ( g ) { = } \{ T , F \}$ ， $T$ 表示系统Z通， $F$ 表示系统Z断。字的集合由十个字组成 $\{ x _ { 1 } , \underline { { { x } } } _ { 1 } , x _ { 2 } , \underline { { { x } } } _ { 2 } , x _ { 3 } , \underline { { { x } } } _ { 3 } , x _ { 4 } , \underline { { { x } } } _ { 4 }$ $\mathbf { \sigma } _ { x 5 , \underline { { x } } 5 } \mathbf { \rangle } _ { }$ 。每个元件的功能有两种状态 $( F , T )$ ，共32条相组成论域$U$ ，也组成了背景空间 $B$ ，如表1所示。

表1中背景空间为 $B { = } \cup \substack { x _ { 6 | 1 \sim 3 2 } }$ ，根据功能结构最简式方法对系统取功能类T的功能结构进行分析。

表132条相集的功能结构分析表  

<html><body><table><tr><td>Uu1</td><td></td><td></td><td>u2 u3 U4 u5 u6 u7 u8</td><td></td><td></td><td></td><td></td><td></td><td>u9 u10u11 u12</td><td></td><td>u13</td><td>U14</td><td>u15 u16</td><td>U17</td><td>u18</td><td>U19</td><td>u20</td><td>U21</td><td>U22U23</td><td>u24</td><td>U25</td><td>u26</td><td>u27 U28</td><td>u29</td><td>u30</td><td>U31</td><td>u32</td></tr><tr><td>fi</td><td>x1</td><td>x1</td><td>X</td><td>x1x1</td><td>x1</td><td>X1 X1</td><td>X1</td><td>X1</td><td></td><td>X1 X1</td><td>x1</td><td>x1</td><td>x1</td><td>x1</td><td>x1</td><td>x1</td><td>x1</td><td>X1 X1</td><td>x1</td><td>X1</td><td>X1</td><td>X1 x1</td><td>x1</td><td>x1</td><td>X1</td><td>x1</td><td>x1</td></tr><tr><td>f</td><td>x2</td><td>x2</td><td>X2</td><td>x2x2</td><td>x2</td><td>X2 x2</td><td>X</td><td>X2</td><td>x2 X2</td><td>X2</td><td>x2</td><td>X2</td><td>x2</td><td>X2</td><td>X2</td><td>x2</td><td>X2 X2</td><td>X2</td><td>x2</td><td>x2</td><td>X2 X2</td><td>x2</td><td>x2</td><td>x2</td><td>X2</td><td>X2</td><td>x2</td></tr><tr><td>f x3</td><td></td><td>x3</td><td>X x3</td><td>x3</td><td>x3</td><td>X x3</td><td>X3</td><td>X</td><td>x3 x3</td><td>X</td><td>x3</td><td>x3</td><td>x3</td><td>x3</td><td>x3</td><td>x3</td><td>x3 X</td><td>X</td><td>x3</td><td>X3</td><td>x X3</td><td>x3</td><td>x3</td><td>x3</td><td>X3</td><td>x3</td><td>x3</td></tr><tr><td>f</td><td>X4</td><td>x4</td><td>X4X4</td><td>X4</td><td>X4 X4</td><td>X4</td><td>X4</td><td>X4</td><td>X4 X4</td><td>X4</td><td>X4</td><td>X4</td><td>X4</td><td>X4</td><td>X4</td><td>X4 X4</td><td>X4</td><td>X4</td><td>X4</td><td>X4 X4</td><td>X4</td><td>X4</td><td>X4</td><td>X4</td><td>X4</td><td>X4</td><td>X4</td></tr><tr><td>fs</td><td>x5</td><td>X5</td><td>x5</td><td>x5</td><td>x5 X5</td><td>x5</td><td>X5</td><td>X5</td><td>X5</td><td>X5</td><td>X5</td><td>x5</td><td>X5</td><td>x5</td><td>X5</td><td>X5 x5</td><td>X5</td><td>X5</td><td>X5</td><td>X5 X5</td><td>X5</td><td>x5</td><td>x5</td><td>X5</td><td>X</td><td>X5</td><td>x5</td></tr><tr><td>g</td><td>F</td><td>F</td><td>F</td><td>F</td><td>F F</td><td>F</td><td>T</td><td>F</td><td>F F</td><td>F</td><td>F</td><td>T</td><td>F</td><td>T</td><td>t</td><td>t F</td><td>F</td><td>F</td><td>T</td><td>T T</td><td>T</td><td>T</td><td>t</td><td>t</td><td>T</td><td>T</td><td>T</td></tr></table></body></html>

a)32个对象构成背景空间 $B$ ，将这32个相集 $x \ s \vert 1 { \sim } 3 2$ 分成功能类T与F两类：

T={X1X2X3X4X5， X1X2X3X4X5， X1X2X3X4X5, X1X2X3X4X5, X1X2X3X4X5,X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5,X1X2X3X4X5,X1X2X3X4X5,X1X2X3X4X5,X1X2X3X4X5}；

$\mathrm { F } =$ {x1X2X3X4X5， x1X2X3X4X5， X1X2X3X4X5， X1X2X3X4X5， X1X2X3X4X5,X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5,X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5,X1X2X3X4X5,X1X2X3X4X5,X1X2X3X4X5,X1X2X3X4X5,X1X2X3X4X5,X1X2X3X4X5}。

对功能类T的相集进行并运算得T的逻辑表达式：T=X1X2X3X4X5+X1X2X3X4X5+X1X2X3X4X5+X1X2X3X4X5+X1X2X3X4X5+X1x2X3X4X5+X1X2X3X4X5+X1X2X3X4X5+X1X2X3X4X5+X1X2X3X4X5+X1X2X3X4X5+X1X2X3X4$x _ { 5 } + x _ { 1 } x _ { 2 } \underline { { { x } } } _ { 3 } x _ { 4 } x _ { 5 } + x _ { 1 } x _ { 2 } x _ { 3 } \underline { { { x } } } _ { 4 } x _ { 5 } + x _ { 1 } x _ { 2 } x _ { 3 } x _ { 4 } x _ { 5 }$ ，其中： $^ +$ 号表示并联；$x _ { 1 } x _ { 2 } x _ { 3 } x _ { 4 } x _ { 5 }$ 表示串联，该逻辑公式就是系统Z的功能结构表达式。

b) $\scriptstyle \lambda = 1$ ，在 $F$ 类相集中， $X _ { 5 | 1 } { = } \underline { { { x } } } _ { 1 } { \underline { { { x } } } } _ { 2 } { \underline { { { x } } } } _ { 3 } { \underline { { { x } } } } _ { 4 } { \underline { { { x } } } } _ { 5 }$ ，它包含 $\underline { { x } } _ { 1 }$ x2.x3,x4, $\underline { { x } } \underline { { s } }$ 的 $\scriptstyle \lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ ： $X _ { 5 \mid 2 } { = } x _ { 1 } { \underline { { x } } } _ { 2 } { \underline { { x } } } _ { 3 } { \underline { { x } } } _ { 4 } { \underline { { x } } } _ { 5 }$ ，它包含 $x _ { 1 }$ ,x2.x3.x4.x5的$\scriptstyle \lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ 。将 $X _ { 5 | 1 }$ 和 $X _ { 5 \mid 2 }$ 相集拆解，将 $\scriptstyle \lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ 无重复的组成筛选相集 $\scriptstyle { \Gamma = \{ x _ { 1 } , \ \underline { { { x } } } _ { 1 } , \ \underline { { { x } } } _ { 2 } , \ \underline { { { x } } } _ { 3 } , \ \underline { { { x } } } _ { 4 } , \ \underline { { { x } } } _ { 5 } \} }$ 。同理，将F中的所有相集拆解，将 $\lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ 无重复的组成筛选相集 $\boldsymbol { { \cal T } }$ $= \{ \ x _ { 1 } , x _ { 2 } , x _ { 3 } , x _ { 4 } , x _ { 5 } , \underline { { x } } _ { 1 } , \underline { { x } } _ { 2 } , \underline { { x } } _ { 3 } , \underline { { x } } _ { 4 } , \underline { { x } } _ { 5 } \} \ ,$ 0

c) $\lambda = \lambda + 1 = 2$ ，在筛选相集 $\scriptstyle { \Gamma = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , x _ { 4 } , x _ { 5 } , \underline { { x } } _ { 1 } , \underline { { x } } _ { 2 } , \underline { { x } } _ { 3 } , \underline { { x } } _ { 4 } , \underline { { x } } _ { 5 } \} }$ 中：任意选取两个相组成 $\scriptstyle \lambda = 2$ 的相集 $\boldsymbol { \mathscr { A } }$ ，这些相集无重复的组成 $\lambda$ $^ { = 2 }$ 时的筛选集合 $\boldsymbol { \Gamma }$ 。根据步骤5）和 $\boldsymbol { \varGamma }$ 对 $F$ 类相集进行筛选。$\boldsymbol { { \cal T } }$ 中 $\scriptstyle \lambda = 2$ 的 $\scriptstyle \varLambda = x _ { 1 } x _ { 4 }$ ,其不在 $F$ 类相集中出现而在T类中出现，那么相 $\boldsymbol { \mathscr { A } }$ 为 $\mathrm { ~ T ~ }$ 类的一个结构式 $\xi ( \mathrm { T } )$ ， $\xi ( \mathrm { T } ) { = } x _ { 1 } x _ { 4 }$ 。去掉T类中包含 $\varLambda = x _ { 1 } x _ { 4 }$ 的相集，得到 $\mathrm { T } = \{ \underline { { x } } 1 \underline { { x } } 2 x 3 \underline { { x } } 4 x \underline { { s } }$ , x1X2X3X4X5,x1X2X3X4X5,X1X2X3X4X5,x1X2X3X4X5,x1X2X3X4X5,x1X2X3X4X5}。另外， $\boldsymbol { \vert \varGamma }$ 中 $\scriptstyle \lambda = 2$ 的$\varLambda = x _ { 3 } x _ { 5 }$ 也不在 $F$ 类相集中出现而在 $\mathrm { \Delta T }$ 类中出现，那么相 $\varLambda$ 为T类的另一个结构式 $\xi \left( \mathrm { T } \right) = x _ { 3 } x _ { 5 }$ 。去掉T类中包含 $\scriptstyle { \mathcal { A } } = x _ { 3 } x _ { 5 }$ 的相

集，则 $\scriptstyle \mathrm { T = \{ \ }  x _ { 1 } x _ { 2 } x _ { 3 } { \underline { { x } } } _ { 4 } { \underline { { x } } } _ { 5 } \}$ 。

d) $\lambda = \lambda + 1 = 3$ ， $\boldsymbol { \varGamma }$ 中 $\scriptstyle \lambda = 3$ 的 $\varLambda = x _ { 1 } x _ { 2 } x _ { 3 }$ ，其不在F类相集中出现而在 $\mathrm { \Delta T }$ 类中出现，那么相 $\boldsymbol { \mathscr { A } }$ 为 $\mathrm { \Delta T }$ 类的一个结构式 $\xi ( \mathrm { T } )$ ， $\xi$ $\left( \mathrm { T } \right) { = } x _ { 1 } x _ { 2 } x _ { 3 }$ 。去掉 $\mathrm { \Delta T }$ 类中包含 $\varLambda = x _ { 1 } x _ { 2 } x _ { 3 }$ 的相集，得到 $\scriptstyle { T = \emptyset }$ 。

$\scriptstyle { T = \emptyset }$ 为算法停止条件。根据步骤7）将得到的 $\mathrm { ~ T ~ }$ 的结构式加在一起，得到T的最简结构式是 $\scriptstyle \zeta ( \mathrm { T } ) _ { \mathrm { B } } = x _ { 1 } x _ { 4 } + x _ { 3 } x _ { 5 } + x _ { 1 } x _ { 2 } x _ { 3 }$ ，那么系统功能结构为 $Z = Z _ { 1 } Z _ { 4 } + Z _ { 3 } Z _ { 5 } + Z _ { 1 } Z _ { 2 } Z _ { 3 }$ 0

取背景空间中 23个相集组成另一个背景空间 $B _ { 1 } = \cup _ { \scriptstyle x _ { 6 | 1 \sim 2 3 } }$ 这 23个相集如表1中深色部分。

a)背景空间 $B _ { 1 } \in B$ 共有23个相集，将这 23个相集 x5|1\~23分成功能类 $T$ 与 $F$ 两类：

T={X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5, X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5， $x _ { 1 } x _ { 2 } x _ { 3 } x _ { 4 } x _ { 5 } \}$

$\mathrm { F } =$ {x1X2X3X4X5， X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5， x1X2X3X4X5,X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5,X1X2X3X4X5，X1X2X3X4X5}。

b) $\scriptstyle \lambda = 1$ ，在 $F$ 类相集中， $X _ { 5 | 1 } { = } \underline { { { x } } } _ { 1 } { \underline { { { x } } } } _ { 2 } { \underline { { { x } } } } _ { 3 } { \underline { { { x } } } } _ { 4 } { \underline { { { x } } } } _ { 5 }$ ，它包含 $\underline { { x } } _ { 1 }$ x2.x3,x4, x5的 $\scriptstyle \lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ ： $X _ { 5 \mid 2 } { = } x _ { 1 } { \underline { { x } } } _ { 2 } { \underline { { x } } } _ { 3 } { \underline { { x } } } _ { 4 } { \underline { { x } } } _ { 5 }$ ，它包含x1,x2.x3.x4.x5的$\scriptstyle \lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ 。将 $X _ { 5 | 1 }$ 和 $X _ { 5 \mid 2 }$ 相集拆解，将 $\scriptstyle \lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ 无重复的组成筛选相集 $\scriptstyle { \Gamma = \{ x _ { 1 } , \underline { { { x } } } _ { 1 } , \underline { { { x } } } _ { 2 } , x _ { 3 } , \underline { { { x } } } _ { 3 } , \underline { { { x } } } _ { 4 } , \underline { { { x } } } _ { 5 } \} }$ 。同理，将F中的所有相集拆解，将 $\lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ 无重复的组成筛选相集 $\boldsymbol { \vert } \varGamma$ $= \{ \ x _ { 1 } , x _ { 2 } , x _ { 3 } , x _ { 4 } , x _ { 5 } , \underline { { x } } _ { 1 } , \underline { { x } } _ { 2 } , \underline { { x } } _ { 3 } , \underline { { x } } _ { 4 } , \underline { { x } } _ { 5 } \} \ ,$

c) $\lambda = \lambda + 1 = 2$ ，在筛选相集 $\scriptstyle { \Gamma = \{ x _ { 1 } , x _ { 2 } , x _ { 3 } , x _ { 4 } , x _ { 5 } , \underline { { x } } _ { 1 } , \underline { { x } } _ { 2 } , \underline { { x } } _ { 3 } , \underline { { x } } _ { 4 } , \underline { { x } } _ { 5 } \} }$ 中，任意选取两个相组成 $\scriptstyle \lambda = 2$ 的相集 $\boldsymbol { \mathscr { A } }$ ，这些相集无重复的组成 $\lambda$ $^ { = 2 }$ 时的筛选集合 $\boldsymbol { \varGamma }$ 。根据步骤5）和 $\boldsymbol { { \Gamma } }$ 对 $F$ 类相集进行筛选。$\boldsymbol { { \Gamma } }$ 中 $\scriptstyle \lambda = 2$ 的 $\scriptstyle \lambda = x _ { 1 } x _ { 4 }$ ,其不在 $F$ 类相集中出现而在T类中出现，那么相基 $\boldsymbol { \mathscr { A } }$ 为 $\mathrm { \Delta T }$ 类的一个结构式 $\xi ( \mathrm { T } )$ ， $\xi ( \mathrm { T } ) { = } x _ { 1 } x _ { 4 }$ 。去掉 $\mathrm { ~ T ~ }$ 类中包含A=xIX4的相集，得到T={xIx2X3X4X5，XIX2X3X4X5，xIx2X3X4X5,

X1X2X3X4X5，X1X2X3X4X5， $\underline { { x } } _ { 1 } x _ { 2 } x _ { 3 } x _ { 4 } x _ { 5 }$ ， $x _ { 1 } x _ { 2 } x _ { 3 } \underline { { x } } _ { 4 } x _ { 5 } \}$ 。另外， $\boldsymbol { { \Gamma } }$ 中 $\scriptstyle \lambda = 2$ 的 $\varLambda = x _ { 3 } x _ { 5 }$ 也不在 $F$ 类相集中出现而在 $\mathrm { ~ T ~ }$ 类中出现，那么相集$\varLambda$ 为 $\mathrm { ~ T ~ }$ 类的另一个结构式 $\xi \left( \mathrm { T } \right) = x _ { 3 } x _ { 5 }$ 。去掉T类中包含 $\scriptstyle { \mathcal { A } } = x _ { 3 } x _ { 5 }$ 的相集，则 $\scriptstyle { T = \emptyset }$ 。

得到 $T$ 的最简结构式是 $\scriptstyle \zeta ( \mathrm { T } ) _ { \mathrm { B l } } = x _ { 1 } x _ { 4 } + x _ { 3 } x _ { 5 } + x _ { 1 } x _ { 2 }$ ，系统功能结构为 $Z { = } Z _ { 1 } Z _ { 4 } { + } Z _ { 3 } Z _ { 5 } { + } Z _ { 1 } Z _ { 2 }$ 。

比较功能结构 $Z = \ Z _ { 1 } Z _ { 4 } + Z _ { 3 } Z _ { 5 } + Z _ { 1 } Z _ { 2 } Z _ { 3 }$ 和功能结构为$Z { = } Z _ { 1 } Z _ { 4 } { + } Z _ { 3 } Z _ { 5 } { + } Z _ { 1 } Z _ { 2 }$ ，背景空间 $B { = } \cup { \boldsymbol { x } } _ { 6 \mid 1 \sim 3 2 }$ 比背景空间 $B _ { 1 } = \cup _ { \scriptstyle x _ { 6 | 1 \sim 2 3 } }$ 得到的系统功能结构更为详尽。即背景空间子集缺乏对系统功能结构的约束。如果 $ { \zeta } (  { \mathrm { T } } ) _ { \mathrm { B } }$ 和 $ { \zeta } (  { \mathrm { T } } ) _ {  { \mathrm { B } } 1 }$ 所表示的系统具有相同的功能变化特征，那么意味着 $x _ { 1 } x _ { 4 } + x _ { 3 } x _ { 5 } + x _ { 1 } x _ { 2 }$ 等价于$x _ { 1 } x _ { 4 } + x _ { 3 } x _ { 5 } + x _ { 1 } x _ { 2 } x _ { 3 }$ 。通过逻辑关系可得到， $x _ { 3 }$ 等价于 $\{ x _ { 1 } , x _ { 2 } , x _ { 1 } \substack { + x _ { 2 } } \}$ ，即元件 $Z _ { 3 }$ 的功能与 $Z _ { 1 }$ 或 $Z _ { 2 }$ 或 $Z _ { 1 } { + } Z _ { 2 }$ 的功能相同。最终，在系统设计和使用过程中，可通过该功能等效关系，进行元件的替换或维修。

分析在表1中除上述23个相集之外的9个相集，组成 $B _ { 1 } =$ $\cup _ { X 6 \mid 1 \sim 9 }$ ，相当于 $B _ { 2 } \in B , B _ { 2 } \cap B _ { 1 } = \emptyset , B _ { 2 } \cup B _ { 1 } = B _ { \circ }$ （20

a)9 个对象构成背景空间 $B$ ，将这9个相集 $\scriptstyle x 5 \mid 1 \sim 9$ 分成功能类 $\mathrm { ~ T ~ }$ 与F两类：

T={X1X2X3X4X5， X1X2X3X4X5， x1X2X3X4X5};

$\mathrm { F } =$ {x1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5，X1X2X3X4X5, $x _ { 1 } x _ { 2 } { \underline { { x } } } _ { 3 } { \underline { { x } } } _ { 4 } x _ { 5 } \}$ 。

b) $\scriptstyle \lambda = 1$ ，在 $F$ 类相集中， $X _ { 5 \mid 1 } =$ 1X2x3x4X5，它包含x1,x2.x3，$\underline { { x } } 4 , \underline { { x } } 5$ 的 $\scriptstyle \lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ ; $X _ { 5 \mid 2 } { = } x _ { 1 } x _ { 2 } { \underline { { x } } } 3 { \underline { { x } } } 4 { \underline { { x } } } 5 $ ，它包含 $x _ { 1 }$ ,x2, x3,x4, $\underline { { x } } \underline { { s } }$ 的$\scriptstyle \lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ 。将 $X _ { 5 | 1 }$ 和 $X _ { 5 \mid 2 }$ 相集拆解，将 $\scriptstyle \lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ 无重复的组成筛选相集 $\scriptstyle { \Gamma = \{ x 1 , \underline { { { x } } } 1 , x 2 , \underline { { { x } } } 3 , \underline { { { x } } } 4 , \underline { { { x } } } 5 \} } .$ 。同理，将F中的所有相集拆解，将 $\lambda = 1$ 的相 $\boldsymbol { \mathscr { A } }$ 无重复的组成筛选相集 $\boldsymbol { { \cal T } }$ （204号$= \{ \boldsymbol { x } _ { 1 } , \boldsymbol { x } _ { 2 } , \boldsymbol { x } _ { 4 } , \boldsymbol { x } _ { 5 } , \underline { { x } } _ { 1 } , \underline { { x } } _ { 2 } , \underline { { x } } _ { 3 } , \underline { { x } } _ { 4 } , \underline { { x } } _ { 5 } \}$ 。相 $x _ { 3 }$ 不在F类出现，也不再T类中出现，所以不是结构式。

c) $\lambda = \lambda + 1 = 2$ ，在筛选相集 $\scriptstyle { \int = \{ x _ { 1 } , x _ { 2 } , x _ { 4 } , x _ { 5 } , \underline { { x } } _ { 1 } , \underline { { x } } _ { 2 } , \underline { { x } } _ { 3 } , \underline { { x } } _ { 4 } , \underline { { x } } _ { 5 } \} } $ 中，任意选取两个相组成 $\scriptstyle \lambda = 2$ 的相集 $\boldsymbol { \mathscr { A } }$ ，这些相集无重复的组成 $\lambda$ $^ { = 2 }$ 时的筛选集合 $\boldsymbol { \varGamma }$ 。根据步骤5）和 $\boldsymbol { \varGamma }$ 对 $F$ 类相集进行筛选。$\boldsymbol { { \cal T } }$ 中 $\scriptstyle \lambda = 2$ 的 $\scriptstyle \lambda = x _ { 1 } x _ { 4 }$ ，其不在F类相集中出现而在T类中出现，那么相 $\boldsymbol { \mathscr { A } }$ 为 $\mathrm { \Delta T }$ 类的一个结构式 $\xi ( \mathrm { T } )$ ， $\xi ( \mathrm { T } ) { = } x _ { 1 } x _ { 4 }$ 。去掉 $\mathrm { ~ T ~ }$ 类中包含 $\scriptstyle \lambda = x _ { 1 } x _ { 4 }$ 的相集，得到 $\scriptstyle \mathrm { T = } \varnothing$ 。

得到T 的最简结构式是 $\zeta ( \mathrm { T } ) _ { \mathrm { B } 2 } { = } x _ { 1 } x _ { 4 }$ ，系统功能结构为$\scriptstyle { Z = Z _ { 1 } Z _ { 4 } }$ 。

上述实例分析说明，当 $B _ { 1 } \in B$ ， $B _ { 2 } \in B$ ， $B _ { 2 } \cap B _ { 1 } { = } { } \emptyset$ ， $B _ { 2 } \cup B _ { 1 } { = } B$ 时， $\zeta \ ( \mathrm { T } ) _ { \mathrm { B } } \neq \ \zeta \ ( \mathrm { T } ) _ { \mathrm { B l } } + \ \zeta \ ( \mathrm { T } ) _ { \mathrm { B } 2 }$ ，即 $x _ { 1 } x _ { 4 } + x _ { 3 } x _ { 5 } + x _ { 1 } x _ { 2 } x _ { 3 } \neq$ $x _ { 1 } x _ { 4 } + x _ { 3 } x _ { 5 } + x _ { 1 } x _ { 2 } + x _ { 1 } x _ { 4 }$ 。背景空间的若干个子集得到的最简结构式不一定等于背景空间全集的结构式之和，同时也存在等于的情况。这取决于所有相集或样本的划分情况。背景空间的子集如果包含了多个 $\scriptstyle \lambda = 1$ 的相且不同状态，那么这个背景空间子集就可产生含有加号较多的最简结构式，表示蕴涵信息较多，如 $B _ { 1 }$ 。如果背景空间子集蕴涵 $\scriptstyle \lambda = 1$ 的相的状态单一，那么所表现的最简结构式所含信息较少，如 $B _ { 2 }$ 。根据上述情况，如果背景空间划分为两个子集，那么满足 $B _ { 1 } \in B , B _ { 2 } \in B , B _ { 2 } \cap B _ { 1 } = \emptyset , B _ { 2 } \cup B _ { 1 } = B ,$ 且 $B _ { 1 }$ 和 $B _ { 2 }$ 所含相集相同，且包含所有的 $\scriptstyle \lambda = 1$ 的相状态，此时$\zeta ( \mathrm { T } ) _ { \mathrm { B } } { = } \zeta ( \mathrm { T } ) _ { \mathrm { B } 1 } { + } \zeta ( \mathrm { T } ) _ { \mathrm { B } 2 } ,$ 。这说明背景空间的若干个子集得到的最简结构式等于背景空间全集的最简结构式所需的条件是严格的。

上述方法可分析离散数据中蕴涵的内在关系。可分析元件故障导致系统故障的成因。该方法是因素空间与空间故障树的结合分析方法，扩展了因素空间理论在安全科学中的应用，同时也为空间故障树的离散数据处理增添了有效方法。

# 4 结束语

本文给出了一种关于系统可靠性的系统功能结构最简式分析方法。该方法主要是通过离散的系统可靠性数据来分析元件功能与系统功能之间的关系。得到在不同背景空间条件下最简结构式，即系统功能最简结构。进而寻找不同背景空间下隐含的各元件功能关系。文中给出了方法的步骤和相关定义及定理。为空间故障树的离散数据处理增添了有效方法。

使用32条可靠性数据组成拥有32个相集的背景空间 $B$ ，使用该方法得到最简结构式 $\scriptstyle \zeta ( \mathrm { T } ) _ { \mathrm { B } } = x _ { 1 } x _ { 4 } + x _ { 3 } x _ { 5 } + x _ { 1 } x _ { 2 } x _ { 3 }$ 。同时，随机选取23个相集组成背景空间子集 $\mathbf { B } _ { 1 }$ ，得到最简结构式 $\boldsymbol { \zeta }$ $\scriptstyle ( \mathrm { T } ) _ { \mathrm { B l } } = x _ { 1 } x _ { 4 } + x _ { 3 } x _ { 5 } + x _ { 1 } x _ { 2 }$ 。其余9个相组成背景空间子集 $\mathbf { B } _ { 2 }$ ，得到最简结构式 $\zeta ( \mathrm { T } ) _ { \mathrm { B } 2 } { = } x _ { 1 } x _ { 4 }$ 。这说明背景空间子集缺乏对系统功能结构的约束。对比 $ { \zeta } (  { \mathrm { T } } ) _ { \mathrm { B } }$ 和 $ { \zeta } (  { \mathrm { T } } ) _ {  { \mathrm { B 1 } } }$ 两式，可知 $x _ { 3 }$ 等价于 $\{ x _ { 1 } , x _ { 2 }$ $\left. x _ { 1 } + x _ { 2 } \right\}$ ，即元件 $Z _ { 3 }$ 的功能与 $Z _ { 1 }$ 或 $Z _ { 2 }$ 或 $Z _ { 1 } { + } Z _ { 2 }$ 的功能相同。同时通过两个背景空间子集所得最简结构式说明，当 $B _ { 1 } \in B$ ， $B _ { 2 } \in$ $B$ ， $B _ { 2 } \cap B _ { 1 } = \emptyset$ ， $B _ { 2 } \cup B _ { 1 } { = } B$ 时， $\zeta ( \mathrm { T } ) _ { \mathrm { B } } { \neq } \ \zeta ( \mathrm { T } ) _ { \mathrm { B l } } + \zeta ( \mathrm { T } ) _ { \mathrm { B } 2 }$ ，即$x _ { 1 } x _ { 4 } + x _ { 3 } x _ { 5 } + x _ { 1 } x _ { 2 } x _ { 3 } \neq x _ { 1 } x _ { 4 } + x _ { 3 } x _ { 5 } + x _ { 1 } x _ { 2 } + x _ { 1 } x _ { 4 }$ 。给出了 $\zeta ( \mathrm { T } ) _ { \mathrm { B } } { = } \zeta ( \mathrm { T } ) _ { \mathrm { B } 1 } +$ $ { \zeta } (  { \mathrm { T } } ) _ {  { \mathrm { B } } 2 }$ 时，背景空间划分子集的条件。

# 参考文献：

[1]Tao Huanqi,Han Gujing,Zou Min. The system analysis of solar inverterbased on network controlling [C]//Proc of International Conference onChallenges in Environmental Science and Computer Engineering.Wuhan:CPS,2010,2: 243-246.  
[2]Tolone WJ,Wray JE,Lee SW.Enabling system of systems analysis ofcritical infrastructure behaviors [C][C]//Proc of the 3rd InternationalWorkshop on Critical Information Infrastructures Security.[S.1.] $\vdots$ Springer-Verlag,2009:24-35.  
[3]Dang Yanzhong.A transfer expansion method for structural modeling insystems analysis [J]. Trans of System Engineering,1998,13 (1): 66-74.  
[4]Lu Z,Yu Y,Woodman NJ,et al.A theory of structural vulnerability[J]. TheStructural Engineer,1999,77 (18): 17-24.  
[5]Agarwal J,Blockley DI,Woodman N J.Vulnerability of 3D trusses [J].Structural Safety,2001,23 (3):203-220.  
[6]卜文绍，祖从林，路春晓.考虑电流动态的无轴承异步电机解祸控制策略[J/OL].控制理论与应用,http://www.cnki.net/kcms/detail/44.1240.TP.20150115.1603.016.html.  
[7]李叶林，马飞，耿晓光．双缓冲腔环形间隙对凿岩机缓冲系统动态特性的影响[J/OL].北京科技大学学报,htp://www.cnki.net/kcms/detail/j.issn1001-053x.2014.12.015.html.  
[8]李明辉，夏靖波，陈才强，等．一种新的含可达影响因子的系统结构分析算法[J].北京理工大学学报,2012,32(2):135-140.  
[9] 李明辉，夏靖波，陈才强，等．通信网络系统结构分析[J].北京邮电大学学报,2012,35 (3):38-41.  
[10]王辉，肖建．基于多分辨率分析的模糊系统结构辨识算法[J]．系统仿真学报,2004.16(8):1630-1632.  
[11]崔铁军．空间故障树理论研究[D].阜新：辽宁工程技术大学,2015.6.  
[12]崔铁军，马云东．多维空间故障树构建及应用研究[J].中国安全科学学报，2013,23(4):32-37.  
[13]崔铁军，马云东．空间故障树的径集域与割集域的定义与认识[J]．中国安全科学学报,2014,24(4):27-32.  
[14]崔铁军，马云东．连续型空间故障树中因素重要度分布的定义与认知[J]．中国安全科学学报,2015,25(3):24-28.  
[15]崔铁军，马云东．基于多维空间事故树的维持系统可靠性方法研究[J].系统科学与数学,2014,34(6):682-692.  
[16]崔铁军，马云东．系统可靠性决策规则发掘方法研究[J]．系统工程理论与实践,2015,35 (12):3210-3216.  
[17]崔铁军，马云东．基于 SFT 理论的系统可靠性评估方法改造研究[J].模糊系统与数学,2015,29(5):173-182.  
[18]崔铁军，马云东．离散型空间故障树构建及其性质研究[J]．系统科学与数学,2016,36 (10): 1753-1761.  
[19]崔铁军，马云东.DSFT的建立及故障概率空间分布的确定[J]．系统工程理论与实践,2016,36(4):1081-1088.  
[20]崔铁军，马云东.DSFT下模糊结构元特征函数构建及结构元化的意义[J].模糊系统与数学,2016,30(2):144-152.  
[21]崔铁军，汪培庄，马云东.01SFT中的系统因素结构反分析方法研究[J]．系统工程理论与实践,2016,36(8):2152-2160  
[22] Wang P Z,Liu Z L, Shi Y,et al. Factor space,the theoretical base of datascience [J].Ann.Data Science,2014,1(2): 233-251.  
[23]石勇．大数据与科技新挑战[J].科技促进发展,2014,(1):25-30.  
[24] Zeng W Y,Feng S.An improved comprehensive evaluation model and itsapplication [J]. InternationalJournal ofComputational Intelligence Systems,2014, 7 (4): 706-714.  
[25] LiDQ, Zeng W Y,LiJ. New distance and similarity measures on hesitantfuzzy sets and their applications in multiple criteria decision making [J].Engineering Applications of Artificial Intelligence,2015,40 (2):11-16.  
[26] 余高锋，刘文奇，石梦婷．基于局部变权模型的企业质量信用评价[J].管理科学学报.2015,17(2):85-94.  
[27] He Ping.Design of interactive learning system based on intuition conceptspace [J].Journal of computer,2010,21(5): 478-487.  
[28]崔铁军，马云东．因素空间的属性圆定义及其在对象分类中的应用[J].计算机工程与科学,2015,37(11):2170-2174.  
[29]崔铁军，马云东．考虑范围属性的系统安全分类决策规则研究[J]．中国安全生产科学技术,2014,10(11):6-9.  
[30]崔铁军，马云东．基于因素空间的煤矿安全情况区分方法的研究[J].系统工程理论与实践,2015,35(11):2891-2897.  
[31]崔铁军，马云东．基于不完全维修的可修系统平均故障次数研究[J].系统工程理论与实践,2016,36(1):184-188.  
[32] WANG Peizhuang.Factor spaces and Factor Data-bases,Journal ofLiaoning Technical University (Natural Science),2013,32 (10): 1-8.  
[33] Wang P Z, Liu Z L, Shi Y, et al. Factor space,the theoretical base of datascience.Ann.Data Science,2014,1(2): 233-251.