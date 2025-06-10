# 基于树宽的警示传播算法收敛性分析

谢志新ä，王晓峰a,b，于卓²，曹泽轩a，吴宇翔ä，莫淳惠ä(北方民族大学 a.计算机科学与工程学院;b.图像图形智能处理国家民委重点实验室，银川 750021)

摘要：警示传播算法作为一种基本的信息传播算法，其收敛时求解可满足性问题十分有效，但因子图结构较为复杂时，算法往往不收敛导致求解失败。为了对这种现象给予理论解释，同时对警示传播算法收敛性进行有效分析，利用树分解方法构造了命题公式对应因子图的树宽度量模型，计算可满足随机实例的树宽。建立树宽与警示传播算法收敛性之间的关系，给出了基于树宽的警示传播算法收敛性判定条件。通过实验分析，结果表明该方法有效，对于分析其他信息传播算法收敛性分析研究具有十分重要的意义。

关键词：警示传播算法；收敛性；树宽；命题公式；可满足性问题 中图分类号：TP301 doi:10.19734/j.issn.1001-3695.2022.03.0098

Convergence analysis of warning propagation algorithm for based on tree width

Xie Zhixina, Wang Xiaofenga,b†, Yu Zhuoa, Cao Zexuana, Wu Yuxianga, Mo Chunhuia (a.CountryDeptofComputerScience,b.TheKeyLaboratoryofImages&Graphics IntelligentProcessingofState Ethnic Affairs Commission,NorthMinzu University,Yinchuan750021,China)

Abstract: The warning propagationalgorithm,asabasic information propagationalgorithm,is very efectiveinsolving the satisfiabilityproblem when itconverges.However,whenthe structureoffactor graph is morecomplex,thealgorithmoften does notconvergeresulting insolvingfailure.Inordertogiveatheoreticalexplanationforthisphenomenon,andtoectively analyzetheconvergence of warning propagationalgorithm,which using tree decomposition methodto constructed the tree width measurement modeloffactor graph correspondingto propositionalformula,andcalculated thetre width satisfying the randominstance.Therelationship betwee tree width and convergenceof warning propagation algorithm is established,and the convergence judgmentconditionof warning propagationalgorithmbasedontree width is given.The experimental results show that this method is efective,and it isvery importantto analyze theconvergenceof other informationtransmission algorithms.

Key words: warning propagation algorithm; convergence; tree width; propositional formula;satisfiability problem

# 0 引言

约束满足问题(constraint satisfaction problem,CSP)在人工智能研究领域中有着深远影响[1-3]，并受到领域专家的广泛关注。现实是世界中许多问题可以归约到CSP问题，如图着色问题，旅行商问题(TSP)，调度问题等。可满足性判定问题(satisfiability，简称SAT)是典型的CSP问题，已经被证明是NP 完全的[4]，其NP完全性广泛扩展应用于其他领域NP完全问题研究。SAT问题是研究对于给定命题公式，是否存在一组布尔变量赋值，使该命题公式为真。由于SAT问题地广泛应用和核心地位，受到了学者们普遍关注。

物理学家提出一种基于统计物理学的警示传播算法(WarningPropagation，WP)[5]，是一种最基础的信息传播算法，主要是基于因子图上进行警示信息的传递和迭代。当算法收敛时，对部分变元进行固定取值并对公式进行化简，以实现SAT问题求解。但随着因子图结构逐渐复杂，信息在出现的环路中无限循环传播，使得警示信息无法收敛到一个固定值，最终导致WP算法求解失败，该现象称为算法不收敛[6]。WP 算法收问题是问题有效求解的保证，因此，研究WP算法的收敛性对WP算法的应用有着重要的意义。

当前对WP算法收敛性研究已经取得了一些成果。2001年，WeissY[7等人得出当因子图只有一个环时，算法收敛且得到的值为变量边缘分布的有效近似。2007年，ManevaE[8]等人对植入指派的随机指派的可满足实例产生模型给出一个收敛性条件，但其应用仅局限于该型实例产生模型，欠缺在3-SAT实例产生模型上判定应用。植入指派中，当概率 $p$ 足够大时，产生的实例高概率有一组满足赋值。2013年，王晓峰[9]等人对两个变量不属于一个子句的特殊 SAT结构进行研究，给出一个基于高斯模型算法收敛的充分必要条件，但只证明 $p$ 取值很小的一部分植入指派实例，应用受限。2014年，Su Qinliang[10,11]等人利用半定规划检查基于高斯模型算法的收敛性，对算法的收敛性进行了分析研究，对于半定规划问题求解的瓶颈在于计算，当SAT问题规模增大即因子图规模增加且变得复杂时，半定规模检查效率较低且非常困难。2016年，王晓峰[12]等人对消息矩阵为半正定矩阵的算法进行了收敛性分析，给出了收敛的充分必要条件。2018年，余光伟[13]等人基于(3,4)-SAT问题研究了修正WP算法的收敛性，得出修正WP算法在正则问题上收敛，但在过程中需要将3-SAT问题转换为(3,4)-SAT特殊结构，且WP算法在转换后的实例上对可满足性判定失效。2020年，崔立[14]等人研究了WP可

收稿日期：2022-03-18；修回日期：202-05-03基金项目：国家自然科学基金资助项目(62062001，61762019，61862051，61962002)；宁夏自然科学基金资助项目(2020AAC03214，2020AAC03219，2019AAC03120，2019AAC0319)；北方民族大学重大专项资助项目(ZDZX201901)；北方民族大学研究生创新项目(YCX22197)

作者简介：谢志新(197-)，男，陕西渭南人，硕士研究生，主要研究方向为算法分析与设计；王晓峰(1980-)，男(通信作者)，甘肃会宁人，副教授，硕导,博士，主要研究方向为人工智能(xfwang@nmu.edu.cn);于卓(197-)，,男，宁夏银川人，硕士研究生，主要研究方向为算法分析与设计；曹泽车轩(998-)，男，宁夏银川人，硕士研究生，主要研究方向为算法分析与设计；吴宇翔（197-)，男，宁夏银川人，硕士研究生，主要研究方向为算法分析与设计；莫淳惠(1994-)，女，重庆人，硕士研究生，主要研究方向为算法分析与设计.

解公式上警示传播算法的收敛性，给出了WP-可解公式上警示传播算法收敛的一个充分条件。2021年，牛进[15]等人利用结构熵概念对WP算法收敛性进行了分析并给出一个收敛阈值，但社区划分准确性欠缺评价指标，影响因子图结构熵的准确计算。2022年，梁晨[16]等人利用K维结构熵对调查传播算法(SurveyPropagation，SP)收敛性进行分析，给出一个收敛的充分条件，但其中所要求的结构信息最小化满足条件较难达到。以上对WP算法收敛性研究基本基于特殊模型或应用于某种具体情况，对于非特殊结构因子图算法研究缺失。因此，对于WP算法收敛性分析研究仍需要大量工作去完成。

因子图结构对WP算法收敛性影响巨大，随着问题规模增大，因子图中节点和边数增加，导致WP算法信息传递变得十分复杂。1991年，RobetsonN[17]等人在文章中提出树分解技术，该技术的目标在于将图分解为一棵树，利用树上的结构信息反映原图的一些性质。图的树宽(Treewidth)和树分解(Treedecomposition)对问题的求解提供了一条新途径，对图进行树分解，将难解问题的图模型限制在有限树宽中，问题可以求解。从计算角度出发，树宽与可处理性有着重要联系，限制树宽参数可用于限制组合爆炸，低树宽意味着计算的快速完成。研究发现，CNF公式因子图为一棵树时，其可满足性可以在多项时间内判定。文献[18]利用树宽参数对约束满足问题中的QCSP(QuantifiedConstraintSatisfaction)问题进行限制，得到一个多项式时间复杂度的求解算法。利用一种特殊的树型结构，文献[19]将正则公式对应的因子图转换为树型结构，并给出了随机正则(3,r)-SAT的可能相变点。文献[20]利用树分解技术求解了受约束的可满足性问题，雷莹等人利用树分解对SAT问题进行了分析，并给出了求解难度与树宽之间的关系。WP算法的收敛性与其因子图结构密切相关，引入树宽度量因子图的结构特性，同时树宽还可以反映分解后小问题的规模，更好反映问题的复杂程度，相较于以往的信息传播算法那收敛性分析，没有条件限制，适用范围广，同时从因子图结构分析更好地反映命题公式结构特征与其收敛性之间联系，进而在因子图结构性质上完善对WP算法收敛性质研究。

综上所述，本文对WP算法求解SAT问题时收敛性进行分析研究。利用树宽的概念，在 $G ( n , 3 , m )$ 模型产生不同的规模的SAT实例上，使用树分解算法求得树宽，对命题公式因子图结构信息进行了分析，提出了SAT实例的树宽模型，通过WP算法的收敛情况，分析WP算法的收敛性和树宽之间关系，给出基于树宽的WP算法收敛判定条件。

# 1 相关知识

# 1.1因子图

因子图(FactorGraph)是一个二部图，表示许多变量的"全局”函数分解成“局部”函数的乘积[20]。图中包含两类节点，变元与子句节点。圆形表示变元节点，方框表示子句节点，实线表示变元在子句以正文字出现，虚线表示变元在子句中以负文字出现出现。例：对于一个CNF公式：

$$
\begin{array} { c } { F = ( - x _ { 1 } \vee x _ { 2 } \vee x _ { 3 } ) \wedge ( - x _ { 1 } \vee x _ { 2 } \vee - x _ { 4 } ) \wedge ( - x _ { 2 } \vee x _ { 3 } \vee - x _ { 5 } ) \wedge } \\ { ( x _ { 2 } \vee - x _ { 4 } \vee x _ { 5 } ) = a _ { 1 } , a _ { 2 } , a _ { 3 } , a _ { 4 } } \end{array}
$$

其因子图如图1所示。

![](images/1f2266db7e0bfe8792c1e6f52412e3a0a15dbf801a86f6d83bbbe2fd70a28961.jpg)  
图1因子图  
Fig.1Factor graph

警示传播算法迭代过程在因子图上进行，已经证明当因子图为树型结构时，信息传播算法可以有效收敛，对于因子图含有多个回路的图形结构的实例，信息传播算法不总有效，常表现为不收敛[22]。

# 1.2警示传播算法

WP 算法中子句节点传递给变元节点的消息为警示信息，记作 $u _ { a  i }$ 。其值为1时表示子句a的可满足性由变元的取值决定，值为0时，则表示变元的取值无法对子句 $\mathbf { \Delta } _ { a }$ 的可满足性起到决定性作用。WP算法的信息更新迭代方程一般写为警示信息之差形式，如下：

$$
u _ { a  i } ( t ) = \prod _ { j \in V ( a ) \backslash i } \theta \Bigg ( - J _ { j } ^ { a } \Bigg ( \sum _ { b \in V ^ { + } ( j ) \backslash a } J _ { j } ^ { b } u _ { b  j } ( t - 1 ) - \sum _ { b \in V ^ { - } ( j ) \backslash a } J _ { j } ^ { b } u _ { b  j } ( t - 1 ) \Bigg ) \Bigg )
$$

若子句a中仅包含变元 $x _ { i }$ 时，说明子句a的可满足性由变元 $x _ { i }$ 决定，则将 $u _ { a  i }$ 的值记为1。在WP算法收敛的情况下，可以根据警示信息来固定变元 $x _ { i }$ 的值：

$$
H _ { i } = - \sum _ { b \in V ( i ) } J _ { i } ^ { b } u _ { b  i } ^ { * }
$$

$$
\mathrm { h } _ { j \to a } = \sum _ { b \in V ^ { + } ( j ) \backslash a } u _ { b \to j } ( t - 1 ) - \sum _ { b \in V ^ { - } ( j ) \backslash a } u _ { b \to j } ( t - 1 )
$$

$H _ { \mathrm { i } } < 0$ 时，赋值为 $\mathbf { \mathrm { ~ 0 ~ } }$ ， $H _ { \mathrm { i } } > 0$ 时，赋值记为1，否则暂时不对 $x _ { i }$ 进行赋值。 $\mathtt { h } _ { \mathtt { j } \to \mathtt { a } }$ ：腔域，当 $x _ { j }$ 变元只出现在子句a中，赋值为1。

算法1 WP算法输入：CNF 公式，迭代终止步数 tmax。

输出：收敛时输出警示信息或未收敛。

a）构造相应因子图。

b）初始化迭代次数 $\scriptstyle \mathbf { t } = \theta$ ，对因子图上每条边对 $u _ { a  i }$ 以均等概率从{0,1}随机选择一个进行赋值。

c）for $\scriptstyle { \mathrm { t } } = 1$ to tmaxo

对因子图的边进行随机排列，根据随机排列的顺序，利用式(1)对警示信息 $u _ { a  i } ^ { * }$ 进行更新。

d)if ua-i(t)=ua-i(t-1)$u _ { a  i } ^ { * } = u _ { a  i } ( t )$ 返回ua。退出循环。  
e）if t $\mathsf { \Pi } = = \mathtt { t } _ { \mathtt { m a x } }$ 返回未收敛。

根据WP算法的迭代过程及迭代方程可以看出， $u _ { a  i }$ 的值对固定变元 $x _ { i }$ 的值十分重要，在固定变元规模下，因子图规模趋于复杂时，同一变元出现在不同子句概率迅速增加，并且环路出现且数目急剧上升，式(1)中 $u _ { a  i }$ 的计算与 $u _ { b  j }$ 密切相关， $u _ { b  j }$ 用来计算在子句a中出现的变元在其他子句中的消息值，同一变元出现在不同子句中数目越多，需要计算的信息越多，此时 $u _ { a  i }$ 计算变得更加复杂引起求解时间增加，且每次迭代后的信息值趋于稳定的概率越低，算法收敛概率受到明显影响。算法收敛时，可以得到警示信息的固定点，根据固定点信息进行部分变元赋值，进行CNF公式简化以完成求解。由于问题规模的增加，变元 $x _ { i }$ 出现在更多的子句中，根据式(3)的计算过程，腔域计算随着因子图规模增加计算量迅速增长，增加了计算时间，并且在每一次迭代中计算得到的信息也因复杂图结构导致相邻两次计算不同，最终不收敛，算法失效。当算法不收敛时，迭代至设定最大迭代次数，求解时间达到最大，但此时算法已求解失败，迭代次数不是算法求解时间的主要影响因素。因此，在WP算法迭代过程中，因子图结构对WP算法性能影响重大。

# 1.3树分解与树宽

树宽可以用来度量图的复杂结构，研究人员发现，将规模大的难解问题利用树分解思想，将其分解为规模较小的易解问题，求解十分有效。图 $G \mathrm { = } ( V , E )$ ，对其进行树分解即对其节点集 $V$ 进行划分，使图 $G$ 尽可能地划分为一棵树型结构，使得图中一个节点子集对应树 $\scriptstyle { \mathcal { T } } = ( I , F )$ 结构中的一个节点，其中 $I$ 为分解树节点。树宽描述其树型结构信息，在树型结构上刻画图 $G$ 的结构性质，将图的树宽作为一个参数反映问题的求解复杂度，同时对算法在求解问题时的一些性质可以进行刻画。

图中节点子集构成一个包(bag)，用 $T _ { G } \mathrm { = } ( X , T )$ 表示一个图的树分解， $X { = } \{ X _ { i } : i \in I \}$ 是图 $G$ 节点集的非空子集。其中：

$\mathbf { a } ) X _ { i }$ 的并集为图 $G$ 的节点集。

b)图 $G$ 中的任意两点存在一条边，那么它们必同时属于 某个 $X _ { i }$ 。

c)若 $j , k , l$ 为树中的三个节点，当 $j$ 在 $l$ 到 $k$ 的路径上,则有 $\nu$ 属于 $X _ { l }$ 和 $X _ { k }$ ， $\nu$ 也属于 $X _ { j }$ 。

树分解的宽度等于 $m a x ( | X _ { i } | { - } 1 \colon i \in I )$ ，即分解后最大包中点数目减1。图 $G$ 的树宽为其最小树分解的宽度。

定义1消点序。设图 $G = ( V , E )$ ，令 $\scriptstyle n = \mid V \mid$ ，双射 $f$ ： $\scriptstyle { V _ {  } }$ $[ n ]$ 记为消点序(Elimination ordering)，其中集合 $[ n ] { = } \{ 1 , 2 , 3 , \cdots$ $| n \}$ 。

定义2弦图。对于图 $G$ 中任何大小超过4的环路，存在连接环路中不相邻节点的弦边，使其环路大小不超过3，则此时图 $G$ 为弦图。

图 $G$ 的树宽为其所有超弦图 $H$ 中最小的一个最大团的大小减1。一般使用消点序和割集构造分解树，同时也有利用智能算法构造树分解的一些策略。这里给出利用消点序构造树分解的算法策略：

算法2消点序构造树分解输入：图 $\mathsf { G } = ( \mathsf { V } , \mathsf { E } )$ 。输出：图G的一个树分解 ${ \sf T } = \left( \mathbb { I } , \sf { F } \right)$ 。a）根据消点序对图进行删点。b）每删掉一个点，将该节点邻居节点加边构成一个环并记录。c）重复步骤b)的操作直到所有节点删除完毕，根据消点序，反向生成树节点，将每次有边联系的点放在一个包中。d）对构成的包进行合并包操作，使得包序列中不存在包与包之间真子集情况。

e）连接包集，生成分解树。

图2给出一个示例，给出一个图 $G$ ，和其树分解结果。对于图 $G$ ，存在一个大小超过4的环，这里在树分解中删除节点 $\mathbf { \sigma } _ { \nu 2 }$ 时，连接 $\mathbf { \nabla } _ { \nu 3 }$ 和 $\mathbf { \sigma } _ { \nu } 5$ 使其构成一个环，在树分解后的树型结构中，将 $\mathbf { \delta } _ { \nu 3 }$ ， $\mathbf { \sigma } _ { \nu } 5$ ， $\overline { { \nu 6 } }$ 放入一个包，作为一个树节点。根据树宽的定义，其分解后的树宽为 $m a x ( | x _ { i } | { - } 1 ; i \in I )$ ，其树宽为2。

![](images/d00ae4018aac6d2652b957d01c1720b00180175bc511fac8d203758e54eac4a5.jpg)  
图2图及图的树分解  
Fig.2Graph and tree decomposition of graph

# 2 命题公式的树宽

WP 算法在求解3-SAT问题时十分有效，但在难解区域往往不收敛，此时WP算法求解失效。因此，研究WP算法收敛性十分重要。当前对于WP算法在因子图上的收敛性分析，相关系统理论分析仍旧欠缺，本文利用树宽度量因子图的结构复杂性，建立因子图树宽度量模型，对因子图的树宽进行分析和研究，实现对WP算法在因子图上收敛性分析。

# 2.1因子图处理

树分解算法应用于无向图分解，因子图是一种包含两类节点，两类边的图结构。树分解过程中，分解树的构造过程中，需要利用节点的度和节点之间的边关系信息去构造分解树。对于图G树分解后的树宽 $t w ( G )$ 有如下基本性质。

性质1[23]对图G存在 $t w ( G ) \geq \gamma ( G ) \geq \sigma ( G )$ 。其中 $\sigma ( G )$ 为图G 中的小节点度数， $\gamma ( G )$ 由式(4)给出：

$$
\gamma ( G ) = \left\{ \begin{array} { l l } { \lvert \nu \rvert { - 1 } , \quad \quad \quad \quad \quad i f \ G i s a c l i q u e } \\ { \displaystyle \operatorname* { m i n } _ { u , \nu \in V , ( u , \nu ) \not \in E } \operatorname* { m a x } \{ d ( u ) , d ( \nu ) \} , \quad \quad \quad o t h e r w i s e } \end{array} \right.
$$

由性质1可知，树分解生成的树宽与节点类型和边类型无关，因子图中的变元节点和子句节点，在树分解过程中将视为一类点，根据树分解宽度的定义，因子图中表示变元在子句中以正负文字出现的两种边，不影响树宽计算，视为一种边即可。

根据树分解过程，在进行树分解算法处理时，先将因子图中的变元和子句节点转换为一类节点表示，将表示变元以负文字出现的虚边转换为实边表示，处理过程如图3所示。

![](images/0a2ada6354019df405dc262bd7b70c336090c11c6aaa3f212c4e1f7efafba4b6.jpg)  
图3因子图树分解  
Fig.3Factor graph tree decomposition

根据图3所示处理过程对于因子图转换后进行树分解处理，分解结果得出给定因子图分解树中最大包节点为{2，6，7，8，9}，由树宽定义计算树宽为4。

# 2.2树分解算法及树宽度量

对于给定命题公式 $G ( n , 3 , m )$ 生成相应的因子图，将其按照因子图处理过程先进行转换，随后利用基于消点序的树分解算法生成相应的树分解。实验中使用树分解算法为近似分解算法，即分解得到的树宽近似图本身的宽度。

消点序树分解算法中，消点序影响着树分解的求解质量，好的消点序得到的树宽更加接近其本身树宽，同时在求解时间上大多占优。构造一个好的消点序是困难的，LB算法基于任意消点序进行树分解构造且表现良好。文中在LB算法的基础上，增加在子句节点和因子节点内进行随机排序生成消点序的规则，规则规定对两类节点消点的顺序，在消点填边略下，保证了不在变元节点与子句节点之间增加边，进而不影响WP算法警示信息的传播过程。

消点序规则：每次生成的CNF公式中，对变元和子句节点进行编号，变元编号在变元个数范围内随机生成，子句节点编号在变元节点之后编号数目之后随机生成。根据树分解规则，此时填边不影响WP算法运行。

LB 算法根据消点序进行填边处理，实现图的三角化得到其弦图，对于图中存在的环利用其处理逻辑进行填边操作，保证大小超过四的环存在弦边。LB算法三角化结果如图4所示。

对于LB算法需要初始化序列，这里按照图中点的编号给出序列为 $\{ a , b , c , d , e , f \}$ 。首先对 $a$ 点进行处理， $a$ 的邻接点集有 $\{ a , b , c \}$ (包含自身)，以 $a$ 的邻接点集构造的连通分量有$\{ d , e , f \}$ ，对 $d$ ， $f$ 进行加边，虚线表示添加的边，按照序列重复过程，实现图 $G$ 的LB三角化生成弦图。

![](images/88a166ce4486c63f430b7765b3fdbe301769762830c7a528d1a7989e35a9a478.jpg)  
图4LB三角化Fig.4Lb triangulation

算法3LB的树分解算法输入：图 $\mathsf { G } = ( \mathsf { V } , \mathsf { E } )$ ，序列限制的 $\mathsf { v }$ 序列α。输出：三角化的图H及树宽。

a）初始化： $G \mathrm { - } > H$ $x  F$ 。

b）for $\times$ ina:

计算 $\times$ 的的邻接点集 $\mathsf { N } _ { \mathsf { H } } [ \mathsf { x } ]$ 得到以其为分割符的连通分量，对每个连通分量的邻接点通过加边构成环，加边集记为 ${ \sf f } ^ { \prime }$

$$
F + F ^ { \prime } - > F ; ( \lor , E + F ) - > H _ { \circ }
$$

c）对构成的图H，以消点序反向构成包集，删除其中为其他包的真子集的包，连接生成分解树。

d）分解树中最大的包中节点数目减1为分解树宽。

WP算法在求解kSAT问题时，可以将难解区域变窄，利用分解树的树宽参数对NP-难问题进行分类，由于WP算法在难解区域失效且表现为不收敛，通过树宽对WP算法收敛性进行判定，即对算法有效性给出了判定条件，同时对kSAT问题进行了分类。该算法求解CNF公式的树宽，反映了CNF公式的结构复杂性，分解过程中将因子图分解为树型结构，树型结构体现不同变元和子句的联系以及形成树节点中原图节点之间的相关性，利用树宽参数对因子图的结构信息进行表达。

利用本算法对WP算法收敛性进行分析研究，与其他WP算法收敛性研究中对命题公式和图模型结构限制相比，使用范围不受限制，并且给出的判定条件使用方便。完善了在因子图结构上对WP算法收敛性分析，同时WP算法作为信息传播算法中最为基础的一种，为其他信息传播算法收敛性研究提供新的思路和方向。

# 3 收敛性分析

本文利用模型 $\mathrm { G } ( \mathrm { n } , 3 , \mathrm { m } )$ 产生随机实例，其中 $\mathfrak { n }$ 为变元个数，3表示每个子句的长度， $\mathrm { ~ m ~ }$ 为子句个数，其中 $\mathrm { ~ m ~ }$ 个子句从所有可能的 $2 ^ { 3 } \bullet C _ { n } ^ { 3 }$ 个子句随机均匀选择。本实验选取两组实验数据对比，变元规模分别设置为 $n { = } 1 0 0$ 和 $n { = } 1 5 0$ ，两组实验设置WP算法最大迭代次数都为1000。

这里根据算法3求得其树宽，其中 $m / n$ 用约束密度 $\alpha$ 表示，已经研究得出，约束密度对因子图的结构和WP算法的收敛性有着重要影响。这里取 $\alpha$ 从2到5.5,递增梯度为0.05。由于同一约束密度生成的随机SAT实例会出现极少数异常SAT实例，为消除其影响，对同一约束密度的随机实例取100组，实验所得树宽值为100组实例由算法3求得树宽的均值，对于非整数均值进行取整操作。每组实例对其WP算法运行的收敛情况进行统计，计算其收敛率，SAT实例树宽随实例约束密度变化如图5、6所示。

图5、6分别描述了两组变元规模分别为100和150的SAT实例时，SAT实例因子图的树宽随着约束密度 $\alpha$ 增长的变化趋势，其横坐标为约束密度 $\mathbf { \alpha } _ { \mathrm { ~ \normalfont ~  ~ } } \mathrm { ~  ~ } _ { \mathrm { ~ \normalfont ~  ~ } }$ 。在两组不同规模的SAT实例中，随着约束密度 $\alpha$ 的增长，树宽也逐渐增加，但其增长速度逐渐放缓，说明在树分解过程中，随着规模因子图的结构逐渐复杂，树分解生成树节点包大小增长放缓，说明因子图中环路因子图结构区域稳定。图7、8对比了WP算法收敛率与SAT实例树宽之间的关系，进而给出树宽与收敛性之间的关系。

![](images/cea1252e2228207f973f5a0bc9870af01af1de18cda0eccc34cebcebf5319d04.jpg)  
图5SAT实例的树宽分布 $\scriptstyle ( \mathbf { n } = 1 0 0$ 0

![](images/fda2052fad2eb66fb302716dc0ee67358fc9bab6486a01c7c83e07f18d7ed6b8.jpg)  
Fig.5Tree Width distribution of SAT instance $( \mathrm { n } { = } 1 0 0 )$

![](images/35b825e8d95f12b7a4c0d6761096d4691c2cd0e19d3f548047e8526232be9596.jpg)  
Fig.6Tree Width distribution of SAT instance $\mathrm { \ddot { n } } = 1 5 0 \$ ）  
图7WP 算法收敛概率分布 $\mathrm { ( n { = } 1 0 0 ) }$ 0

![](images/43983066869e0894089994bdf294aebfbfe83b8a94a1e737317f4de53123e3d2.jpg)  
图6SAT实例的树宽分布 $\mathrm { ( n { = } 1 } 5 0$ ）  
Fig.7WP algorithmconverges probability distribution $( \mathrm { n } { = } 1 0 0 )$ ，   
图8WP 算法收敛概率分布 $\mathrm { ( n { = } 1 5 0 ) }$   
‘ig.8WP algorithm converges probability distribution $\mathrm { \hat { n } } { = } 1 5 0 \mathrm { \cdot }$

图7、8分别展示了WP算法收敛概率随树宽 $t w$ 变化的情况，统计WP算法在100组实例上收敛个数，计算得到WP算法收敛概率，当树宽值超过当前规模实例的树宽阈值时，WP算法收敛概率骤然下降至不收敛。当实例变元规模 $n { = } 1 0 0$ 树宽 $t w \leqslant 6 2$ 时，WP算法在随机SAT实例求解上完全收敛，当 $6 3 \leqslant t w \leqslant 6 7$ 时，WP算法在随机SAT实例上的收敛概率从1迅速下降至0。当实例变元规模 $n { = } 1 5 0$ ，树宽 $t w { \leqslant } 9 1$ 时，WP算法在所有实例上完全收敛，当 $9 2 \leqslant t w \leqslant 1 0 0$ 时，WP算法在随机SAT实例上的收敛概率迅速下降到0。从图7、8可以得到WP算法在大多数实例上高概率收敛，但一旦超过某一阈值，WP算法收敛概率骤降，几乎不收敛。

随机SAT实例中，对同一约束密度，实验中会得到不同的树宽，对应因子图中出现环路和某些变元节点度不同。当约束密度增加，树分解算法的求解时间也相应增加，文中树分解算法对与当前节点和其邻居节点构成的连通分量中增加边，因子图约束密度增加，环路相应增多，对应的连通分量增加，故增加了求解时间。同时，约束密度增加，意味着子句节点的增加，树分解的宽度也与图中节点数目相关，当WP算法的收敛概率突然下降，其树宽仍缓慢增加，相比于随机SAT实例的规模，树宽大小与增长速度都远小于随机实例。这对研究信息传播算法在难解实例上因子图的结构信息与算法收敛性提供了一定的基础。

因子图的结构对WP算法性能影响巨大，实验中给出了两个变元规模下的WP算法收敛的充分条件，对于其他规模随机SAT实例WP算法收敛时的树宽阈值也可提供该方法得出。

# 4 结束语

信息传播算法在求解3-SAT问题时十分有效，WP算法作为一种基本的信息传播算法，研究其性质对其他信息传播算法有着重要作用。本文提出了一种度量命题公式结构特征的算法，利用树宽表示因子图的结构信息，在实验中得到了不同规模随机实例的树宽变化和WP算法收敛性变化，给出在不同规模随机实例算法收敛时的树宽充分条件。下一步工作，将树分解算法进行改进以求得更加接近图树宽的分解树树宽，同时将树分解策略应用与其他信息传播算法的收敛性分析，并对树宽与因子图复杂性的关系进行深入的分析和验证。

# 参考文献：

[1]Dyer M,Frieze A,Molloy M.A probabilistic analysis of randomly generated binary constraint satisfaction problems [J].Theoretical Computer Science,2003,290 (3):1815-1828.   
[2]Creignou N,Daudé H.The SAT-UNSAT transition for random constraint satisfaction problems [J].Discrete mathematics,20o9,309 (8):2085- 2099.   
[3]Gaspers S,Papadimitriou C,Sather SH,et al. On satisfiability problems with a linear structure [J].arXiv preprint arXiv:1602.O7876,2016.   
[4]Aiello A,Buratini E,Massarotti A.The Complexity of Theorem Proving Procedures [J].Rairo Informat Théor,1977,11(1):75-82.   
[5]Mézard M,Parisi G,Zecchina R.Analytic and algorithmic solution of random satisfiability problems [J]. Science,2002,297 (5582):812-815.   
[6]Weiss Y.Correctness of Local Probability Propagation in Graphical Models with Loops [J].Neural computation,20oo,12(1):1-41.   
[7]Weiss Y,Freeman W T.Correctness of Belief Propagation in Gaussian Graphical Models of Arbitrary Topology [J].Neural Computation,2001, 13 (10):2173-2200.   
[8]Maneva E,Mossel E,Wainwright M.A new look at survey propagation and its generalizations.[J].ACM,2007,54:1089-1098.   
[9]王晓峰，许道云，韦立．随机可满足实例集上警示传播算法的收敛 性[J]．软件学报,2013,24(01):1-11.(Wang Xiaofeng,Xu Daoyun, Wei Li. Convergence of warning propagation algorithms for random satisfiable instances [J]. Journal of Software,2013,24(1): 1-11.)   
[10] Su Q, Wu Y C.Convergence analysis of the variance in Gausian belief propagation [J]. IEEE Transactions on Signal Processing,2014,62 (19): 5119-5131.   
[11] Su Q，Wu Y C.On convergence conditions of Gaussian belief propagation [J]. IEEE Transactions on Signal Processing,2015,63 (5): 1144-1155.   
[12]王晓峰，许道云．警示传播算法收敛的充分条件[J].软件学报, 2016(12):3003-3013.(Wang Xiaofeng，Xu Daoyun．Sufficient conditions for convergence of the warning propagation algorithm [J]. Journal of Software,2016,27 (12): 3003-3013.)   
[13]余光伟，许道云．用于求解正则(3,4)-SAT实例集的修正警示传播 算法[J].计算机科学,2018,45(11):312-317.(She Guangwei,XU Daoyun. Modified Warning Propagation Algorithm for Solving Regular (3,4)-SAT Instance Sets [J]. Computer Science,2018,45 (11):312-31 7.）   
[14]崔立，王晓峰，牛进.WP 可解公式上警示传播算法收敛的有效条件 [J]．计算机应用研究，2020,37(05):1406-1410.(Cui Li,Wang Xiangfeng，Niu Jin. Efctive conditions for warning propagation algorithm convergence on WP solvable formula [J].Application Research of Computers,2020,37(05): 1406-1410.)   
[15]牛进，王晓峰，林青文．基于结构熵的警示传播算法收敛性分析[J] 计算机应用研究,2021,38 (03): $7 6 0 - 7 6 3 + 7 7 6$ (Niu Jin, Wang Xiaofeng, Lin Qingwen. Convergence analysis of warning propagation algorithm based on structural entropy [J].Application Research of Computers, 2021,38 (03): $7 6 0 - 7 6 3 + 7 7 6 .$ ）   
[16]梁晨，王晓峰，刘子琳，等．基于K维结构熵的调查传播算法收敛性 分析[J/OL]．计算机应用研究：1-6[202-01-15].DOI:10.19734/j. issn.1001-3695.2021.10.0474.(Liang Chen, Wang Xiaofeng,Liu Zilin, et al. Convergence analysis of survey propagation algorithm based on Kdimensional structureentropy [J/OL].Application Researchof Computers,1-6[2022-01-15].   
[17] Robertson N,Seymour P D.Graph minors.X. Obstructions to treedecomposition [J].Journal of Combinatorial Theory, Series B,1991,52: 153-190.   
[18] Chen H. Quantified constraint satisfaction and bounded treewidth [C]// ECAI. 2004,16: 161.   
[19] Krishnamurthy S,Sahoo S.Balanced k-satisfiability and biased random k-satisfiability on trees [J].Physical Review E,2013,87(4): 042130.   
[20]雷莹，许道云．图的树分解算法及其应用[J].计算机科学,2020,47 (05):51-58.(Lei Ying，Xu Daoyun. Algorithm of Graph and Its Application [J],Computer Science,2020,47 (05): 51-58).   
[21] Kschischang FR,Frey B J,Loeliger HA.Factor graphs and the sumproduct algorithm [J].IEEE Transactions on Information Theory,2001, 47 (2): 498-519.   
[22] Braunstein A,Mézard M, Zecchina R. Survey propagation: An algorithm for satisfiability[J].Random Structures & Algorithms,20o5,27(2): 201- 226.   
[23] Hammerl T,Musliu N,Schafhauser W.Metaheuristic algorithms and tree decomposition [M// Springer Handbook of Computational Intelligence. Springer, Berlin, Heidelberg,2015: 1255-1270.