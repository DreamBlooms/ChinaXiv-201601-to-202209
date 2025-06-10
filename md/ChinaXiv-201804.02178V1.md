# 流计算模式下概率粗糙集三支决策的快速计算

徐健锋1,2,3，王喜秋1,3，刘斓1,2,3†，汤涛1,3(1．南昌大学 软件学院，南昌 330047;2.南昌大学 信息工程学院，南昌 330031;3.江西省经济犯罪侦查与防控技术协同创新中心，南昌 330031)

摘要：在流计算模式下进行三支决策的快速计算研究是一项具有挑战性的新议题。针对流计算模式中的动态对象增量与减量同步发生的现象，提出了一种概率粗糙集三支决策的快速流计算方法。首先讨论了流计算模式中决策信息系统的单对象增减更新模式的数据模式，然后基于流计算数据变化模式分别提出了数据增量与数据减量时三支决策域的变化推理，最后基于上述理论给出了一种流计算模式下的三支决策动态增减快速学习算法。通过八种UCI数据集的对比实验，证明了该算法不但在时间消耗上明显优于经典三支决策算法，而且对于三支决策阈值具有较强的稳定性。

关键词：三支决策；流计算模式；动态学习；概率粗糙集 中图分类号：TP301.5 doi:10.3969/j.issn.1001-3695.2017.12.0855

# Fast computing of probabilistic rough set three-way decision in stream computing mode

Xu Jianfeng1,2,3, Wang Xiqiu1,3,Liu Lan1,2,3†, Tang Tao1, 3 (1.Collge ofSoftware,Nanchang University,Nanchang 33047,China;2.Collgeof Information Engineering,Nanchang University,Nanchang 33o031，China;3.Jiangxi CollborativeInnovation CenterforEconomic CrimeInvestigation& Prevention& Control,Nanchang 330031,China)

Abstract:It is achalenging topic tocarryout fastcomputing for three-waydecision in streamcomputing mode.Aimatthe phenomenon that the increment and decrement ofdynamic objects occur synchronouslyin the stream computing mode,this paper proposedafaststreamcomputing method forprobabilisticroughset tree-waydecision.Firstlyytdiscussdthedatamode of single-objectincrementand decrement updating mode in streamcomputing.Then,proposed thereasoningofthe three-way decisiondomains indataincrementanddatadecrementdynamic moderespectivelybasedonthe patternofdatavariation.Finaly, proposeda three-waydecision dynamic incrementaland decremental learning algorithm based on the above theory.The comparison experimentsof eight UCIdatasets show thatthealgorithm notonlyoutperforms theclasical thre-decision algorithm in time consumption,but also has strong stability for the three-way decision thresholds.

Key Words: three-way decision; stream computing mode; dynamic learning; probabilistic rough set

# 0 引言

由加拿大贾纳大学姚一豫教授提出的三支决策[是在粗糙集的基础上发展出的一种不确定性问题求解的重要理论。近年来，三支决策理论在垃圾邮件过滤[2]、文本情感[3]、图像识别[4]等应用领域都取得了一系列的研究成果，这些成功的应用实例证明了三支决策在复杂背景环境中实施问题求解的重要价值。

随着大数据时代[5的到来，新型的数据环境和计算模式不断涌现，例如流计算模式就是近年出现的一种新型动态计算形式。支持流计算模式的系统平台不断涌现和发展（如Twitter、

LinkedIn等公司的Storm、Kafka、YahooS4及诞生于伯克利大学AMPLab的Spark平台等流计算平台)，流计算模式的重要性愈加凸显。

流计算模式的主要动态特点可以总结为：数据源不经过外部存储器缓存，直接以滑动窗口的方式快速通过内存，而CPU直接对内存数据进行计算，并且实时反馈计算结果。从内存的角度观察流计算模式，可以发现流计算模式的本质是CPU在有限的内存空间内同时实施增量学习与减量学习（可以看做是负增量学习）的计算任务[6，如图1所示。

增量学习是指一个学习系统能不断地从来自环境的新样本中学习新的知识，并能保留大部分以前已经学习到的知识，不必重新学习全部数据。降低了对时间和空间的需求,更能适应实际要求。增量学习在粗糙集及三支决策领域已经具有多年的研究历史，当前的增量学习在各类粗糙集模型[7,8]上均有相关的研究，其主要研究内容涉及上下近似[9,10]、属性约简[11,12]和决策规则[13,14]等诸多方面。但是，流计算模式的这种具有增量和减量同时实施的新型动态学习方法，尚需要进一步展开研究。所以，如何在新型的流计算模式下实施快速三支决策，是在新型计算模式下进行不确定问题求解的重要课题。

![](images/03024e1842ec635c559d6d92d2e8de4f146cfdfccb51690b7273cbbc7912d8fa.jpg)  
内存计算过程  
图1流计算模式示意图[6]

# 1 概率粗糙集三支决策的基本理论

概率粗糙集是构造三支决策的基础原型[15,16]。其模型基础:决策信息系统 $I S$ 是一个四元组、 $I S = ( U , A , V , f )$ 。其中 $U$ 代表论域中对象 $x$ 的集合; $A = R \cup D$ 代表属性集合，其中 $R$ 为条件属性集合，( $U / R = \{ R _ { 1 } , R _ { 2 } { \therefore } , R _ { m } \}$ 为 $R$ 属性确定的不可区分关系形成的等价类集合); $D$ 为决策属性集合( $U / D = \{ D _ { 1 } , D _ { 2 } \cdots , D _ { n } \}$ 为 $D$ 属性确定的不可区分关系形成的等价类集合); $V$ 代表 $A$ 中各属性的取值范围; $f$ 代表从对象到属性取值的信息函数，即$f : U \times A \to V$ 。

概率粗糙集三支决策的相关定义为[]。

定义1等价关系。给定信息系统 $I S$ 上的属性子集 $B$ ，满足条件 $B \subseteq A$ ，则基于属性 $B$ 的某一等价类可以表示为：

$$
I N D ( B ) = \{ ( x , y ) \in U \times U \mid \forall a \in B , f ( x , a ) = f ( y , a ) \}
$$

不同的二元关系下概率粗糙集具有不同的表达，等价关系刻画对象之间的关系。

定义2条件概率。给定 $I S$ ，基于条件属性 $R$ 的任一对象集合 $R _ { i }$ ${ \bf \Gamma } _ { i } ^ { \prime } \left( \begin{array} { l } { R _ { i } \in { U } / R } \\ { \rule { 0 ex } { 5 ex } } \end{array} \right. .$ )对基于决策属性 $D$ 的任一对象集合 $D _ { j }$ （ ${ D _ { j } } \in \boldsymbol { U } / D$ )的条件概率定义如下：

$$
P ( D _ { j } \mid R _ { i } ) = \frac { \mid D _ { j } \cap R _ { i } \mid } { \mid R _ { i } \mid }
$$

定义3三支决策域。给定一组阈值 $\alpha$ 和 $\beta$ ，其正域、边界域和负域可以分别表示为

$$
P O S _ { ( \alpha , \bullet ) } ( D _ { j } ) = \{ x \in U \mid ( x \in R _ { i } ) \land ( P ( D _ { j } \mid R _ { i } ) \geq \alpha ) \} ;
$$

$$
B N D _ { ( \alpha , \beta ) } ( D _ { j } ) = \{ x \in U \mid ( x \in R _ { i } ) \land ( \beta < P ( D _ { j } \mid R _ { i } ) < \alpha ) \} ;
$$

$$
N E G _ { ( \bullet , \beta ) } ( D _ { j } ) = \{ x \in U \mid ( x \in R _ { i } ) \land ( P ( D _ { j } \mid R _ { i } ) \leq \beta ) \} ;
$$

注： $0 \leq \beta < \alpha \leq 1$

正域、边界域和负域对应的三支决策可分别解释为接收、延迟和拒绝，表示如下：

$$
D E S _ { A c c e p t } ( R _ { i } \to D _ { j } ) , f o r ~ R _ { i } \subseteq P O S _ { ( \alpha , \bullet ) } ( D _ { j } ) ,
$$

$$
( i = 1 , 2 \cdots , m ; j = 1 , 2 \cdots , n ) ;
$$

$$
D E S _ { D e f e r } ( R _ { i } \to D _ { j } ) , f o r ~ R _ { i } \subseteq B N D _ { ( \alpha , \beta ) } ( D _ { j } ) ,
$$

$$
( i = 1 , 2 \cdots , m ; j = 1 , 2 \cdots , n ) ;
$$

$$
\begin{array} { r } { D E S _ { \scriptscriptstyle \mathrm { R e } \ j e c t } ( R _ { i } \to D _ { j } ) , f o r ~ R _ { i } \subseteq N E G _ { ( \bullet , \beta ) } ( D _ { j } ) , } \end{array}
$$

$$
( i = 1 , 2 \cdots , m ; j = 1 , 2 \cdots , n ) ;
$$

其中 $\mid U \mid R \mid = m$ 为 $R$ 属性集所确定的等价关系商集的基数。  
$\mid U \mid D \mid = n$ 为 $D$ 属性集所确定的等价关系商集的基数。

# 2 流计算模式下三支决策的增量与减量学习

# 2.1决策信息系统的单对象增量与减量更新模型

流计算模式下，数据在内存计算中同时实现了数据的实时流入和实时流出。为了便于讨论，可以将流计算模式分解为对决策信息系统的执行增量更新和减量更新两个步骤的动态过程。

1)决策信息系统的单对象增量更新模型

当一个对象 $x$ 加入到内存中的信息系统中，该新增对象记为 $x _ { + }$ 。该信息系统在增加 $x _ { + }$ 后各条件属性等价类和各决策属性等价类的变化可由下列公式更新。

$$
\begin{array} { r } { R _ { i } ^ { t + 1 } = \left\{ \begin{array} { c c c } { R _ { i } ^ { t } \bigcup \{ x _ { + } \} } & { x _ { + } \in R _ { i } ^ { t } } & { 1 \leq i \leq m } \\ { \{ x _ { + } \} } & { x _ { + } \in R _ { i } ^ { t + 1 } } & { i = m + 1 } \end{array} \right. } \\ { D _ { j } ^ { t + 1 } = \left\{ \begin{array} { c c c } { D _ { j } ^ { t } \bigcup \{ x _ { + } \} } & { x _ { + } \in D _ { j } ^ { t } } & { 1 \leq j \leq n } \\ { \{ x _ { + } \} } & { x _ { + } \in D _ { j } ^ { t + 1 } } & { j = n + 1 } \end{array} \right. } \end{array}
$$

其中上标 $t$ 表示初始时刻，上标 $t + 1$ 表示增加新对象后的时刻。

上述对象增量将导致条件属性等价类 $R _ { i } ^ { t + 1 }$ 和决策属性等价类 $D _ { j } ^ { t + 1 }$ 出现以下4种可能的数据变化情况：

情况1 $x _ { + } \in D _ { j } ^ { t + 1 } \land x _ { + } \in R _ { i } ^ { t + 1 }$

情况2 $x _ { + } \notin D _ { j } ^ { t + 1 } \land x _ { + } \in R _ { i } ^ { t + 1 }$

情况3 $\boldsymbol { x } _ { + } \in D _ { j } ^ { t + 1 } \wedge \boldsymbol { x } _ { + } \not \in R _ { i } ^ { t + 1 }$

情况4 $\boldsymbol { x } _ { + } \notin D _ { j } ^ { t + 1 } \land \boldsymbol { x } _ { + } \notin R _ { j } ^ { t + 1 }$

注：其中 $1 \leq j \leq n$ 或 $1 \leq j \leq n + 1$ ， $1 \leq i \leq m$ 或 $1 \leq i \leq m + 1$ 。

性质1决策信息系统的单对象增量更新模型中列举的数据变化情况3和4，决策规则 $R _ { i } ^ { t + 1 } \to D _ { j } ^ { t + 1 }$ 所属的三支决策域保持不变。

证明上述情况3和4中由于 $x _ { - } \notin R _ { i } ^ { t + 1 }$ 的情况下$R _ { i } ^ { t + 1 } \to D _ { j } ^ { t + 1 }$ 的条件概率 $P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } )$ 保持不变，所以$R _ { i } ^ { t + 1 } \to D _ { j } ^ { t + 1 }$ 的决策域也保持不变。

2)决策信息系统的单对象减量更新模型

当一个对象 $x$ 从内存中的决策信息系统中删除后，被删除对象记为 $x _ { _ - }$ 。该信息系统在删除 $x _ { _ - }$ 后各条件属性等价类和各决策属性等价类的变化可由下列公式更新。

$$
\begin{array} { r } { \left\{ \begin{array} { l l l } { R _ { i } ^ { t + 1 } = R _ { i } ^ { t } - \{ x _ { - } \} } & { x _ { - } \in R _ { i } ^ { t } } & { 1 \leq i \leq m } \\ { D _ { j } ^ { t + 1 } = D _ { j } ^ { t } - \{ x _ { - } \} } & { x _ { - } \in D _ { j } ^ { t } } & { 1 \leq j \leq n } \end{array} \right. } \end{array}
$$

其中上标 $t$ 表示初始时刻，上标 $t + 1$ 表示删除对象后的时刻。

上述对象减量将导致条件属性等价类 $R _ { i } ^ { t + 1 }$ 和决策属性等价类 $D _ { j } ^ { t + 1 }$ 出现以下4种可能的数据变化情况：

情况1 $\boldsymbol { x } _ { - } \in D _ { j } ^ { t + 1 } \wedge \boldsymbol { x } _ { - } \in R _ { i } ^ { t + 1 }$ ；

情况2 （204 $\boldsymbol { x } _ { - } \notin D _ { j } ^ { t + 1 } \land \boldsymbol { x } _ { - } \in R _ { i } ^ { t + 1 }$ ;

情况3 $\boldsymbol { x } _ { - } \in D _ { j } ^ { t + 1 } \wedge \boldsymbol { x } _ { - } \not \in R _ { i } ^ { t + 1 }$ ；

情况4 $x _ { - } \notin { D _ { j } } ^ { t + 1 } \land x _ { - } \notin { R _ { i } ^ { t + 1 } }$

注：其中 $1 \leq j \leq n$ ， $1 \leq i \leq m$ □

性质2决策信息系统的单对象减量更新模型中列举的数据变化情况3和4，决策规则 $R _ { i } ^ { t + 1 } \to D _ { j } ^ { t + 1 }$ 所属三支的决策域保持不变。

# 2.2三支决策的单对象增量学习策略

对于一个给定的决策等价类 $D _ { j } ^ { t }$ ，新增一个对象 $x _ { + }$ ，其正域、负域和边界域变化如下：

定理1在 $I S$ 中，当 $D _ { j } ^ { t + 1 } = D _ { j } ^ { t } \cup \{ x _ { + } \}$ 并且 $R _ { i } ^ { t + 1 } = R _ { i } ^ { t } \cup \{ x _ { + } \}$ 时,a)若 $R _ { i } ^ { t } \subseteq P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } )$ ，则有：

$$
P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t + 1 } ) = P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } ) \cup \{ x _ { + } \}
$$

b)若 $R _ { i } ^ { t } \subseteq B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } )$ ，则有：

如果 $P ( D _ { j } ^ { t + 1 } | R _ { i } ^ { t + 1 } ) \geq \alpha$ ，那么

$$
\left\{ P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t + 1 } ) = P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } ) \bigcup _ { i } { \cal R } _ { i } ^ { t + 1 } \right.
$$

如果 $P ( D _ { j } ^ { t + 1 } | R _ { i } ^ { t + 1 } ) < \alpha$ ，那么

$$
B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 1 } ) = B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } ) \cup \{ x _ { + } \}
$$

c)若 $R _ { i } ^ { t } \subseteq N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } )$ ，则有：·

如果 $P ( D _ { j } ^ { t + 1 } | R _ { i } ^ { t + 1 } ) \geq \alpha$ ，那么

$$
\left\{ { P O S } _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t + 1 } ) = P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } ) \bigcup _ { i } R _ { i } ^ { t + 1 } \right.
$$

如果 $\beta < P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } ) < \alpha$ ，那么

$$
\left\{ B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 1 } ) = B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } ) \bigcup _ { i } { \cal R } _ { i } ^ { t + 1 } \right.
$$

如果 $P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } ) \leq \beta$ ,那么

$$
N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t + 1 } ) = N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } ) \mathsf { U } \{ x _ { + } \}
$$

证明a)当 $D _ { j } ^ { t + 1 } = D _ { j } ^ { t } \cup \{ x _ { + } \}$ 并且 $R _ { i } ^ { t + 1 } = R _ { i } ^ { t } \cup \{ x _ { + } \}$ 时，根据集合的基本概念知 $\mid R _ { i } ^ { t + 1 } \mid > \mid R _ { i } ^ { t } \mid$ 并且 $\mid D _ { j } ^ { t + 1 } \mid > \mid D _ { j } ^ { t } \mid$ 。结合定义2可以得出 $P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } ) > P ( D _ { j } ^ { t } \mid R _ { i } ^ { t } )$ 。又因为 $x _ { + }$ 的条件等价类$R _ { i } ^ { t } \subseteq P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } )$ ，所以可得到 $P ( D _ { j } ^ { t } \mid R _ { i } ^ { t } ) \geq a$ 。综合上述条件可得出 $P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } ) > P ( D _ { j } ^ { t } \mid R _ { i } ^ { t } ) \geq \alpha$ 。根据定义4知 $x _ { + }$ 所属的决策区域为正域，所以 $P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t + 1 } ) = P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } ) \cup \{ x _ { + } \}$ ，证毕。

$\mathbf { b } ) \mathbf { c }$ )的证明类似，略。

定理2在 $I S$ 中，当 $D _ { j } ^ { t + 1 } = D _ { j } ^ { t }$ 并且 $R _ { i } ^ { t + 1 } = R _ { i } ^ { t } \cup \{ x _ { + } \}$ 时,a)若 $R _ { i } ^ { t } \subseteq P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } )$ ，则有：

如果 $P ( D _ { j } ^ { t + 1 } | R _ { i } ^ { t + 1 } ) \geq \alpha$ ，那么

$$
P O S _ { _ { ( \alpha , \bullet ) } } ( D _ { j } ^ { t + 1 } ) = P O S _ { _ { ( \alpha , \bullet ) } } ( D _ { j } ^ { t } ) \cup \{ x _ { + } \}
$$

如果 $\beta < P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } ) < \alpha$ ，那么

$$
\left\{ B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 1 } ) = B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } ) \bigcup _ { \mathbf { \alpha } } R _ { i } ^ { t + 1 } \right.
$$

如果 $P ( D _ { j } ^ { t + 1 } \vert R _ { i } ^ { t + 1 } ) \leq \beta$ ,那么

$$
\left\{ N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t + 1 } ) = N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } ) \bigcup _ { i } R _ { i } ^ { t + 1 } \right.
$$

b)若 $R _ { i } ^ { t } \subseteq B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } )$ ，则有：

如果 $P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } ) > \beta$ ，那么

$$
B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 1 } ) = B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } ) \cup \{ x _ { + } \}
$$

如果 $P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } ) \leq \beta$ ，那么

$$
\left\{ \begin{array} { l } { N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t + 1 } ) = N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } ) \bigcup R _ { i } ^ { t + 1 } } \\ { B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 1 } ) = B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } ) - R _ { i } ^ { t } } \end{array} \right.
$$

c）若 $R _ { i } ^ { t } \subseteq N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } )$ ，则有：

$$
N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t + 1 } ) = N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } ) \cup \{ x _ { + } \}
$$

定理2的证明和定理1的证明类似，略。

注：定理1对应2.1节第一小节中的单对象增量数据变化情况情况1，定理2对应单对象数据增量变化情况2。

当 $\scriptstyle j = n + 1$ 或 $\scriptstyle i = m + 1$ 时，其语义为增加了新的决策等价类或者条件等价类。所以这种情况可以预设 $P ( D _ { j } ^ { t } | R _ { i } ^ { t } ) { = } 0$ ，然后运用上述定理进行决策域的变换即可。

而由2.1节的性质1所述情况3和4，由于结论是决策规则 $R _ { i } ^ { t + 1 } \to D _ { j } ^ { t + 1 }$ 所属的三支决策域保持不变，所以可以直接获得结论，不需要额外计算。

# 2.3三支决策的单对象减量学习策略

对于一个给定的决策等价类 $D _ { j } ^ { t }$ ，删除一个对象 $\mathbf { \nabla } x _ { - }$ ，其正域、负域和边界域变化如下：

定理3在 $I S$ 中，当 $D _ { j } ^ { t + 1 } = D _ { j } ^ { t } - \{ x _ { - } \}$ 并且 $R _ { i } ^ { t + 1 } = R _ { i } ^ { t } - \{ x _ { - } \}$ 时,a)若 $R _ { i } ^ { t } \subseteq P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } )$ ，则有：

如果 $P ( D _ { j } ^ { t + 1 } | R _ { i } ^ { t + 1 } ) \geq \alpha$ ，那么

$$
P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t + 1 } ) = P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } ) - \{ x _ { - } \}
$$

如果 $\beta < P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } ) < \alpha$ ，那么

$$
\left\{ \begin{array} { c } { B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 1 } ) = B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } ) \bigcup R _ { i } ^ { t + 1 } } \\ { P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t + 1 } ) = P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } ) - R _ { i } ^ { t } } \end{array} \right.
$$

如果 $P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } ) \leq \beta$ ，那么

$$
\left\{ \begin{array} { l } { N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t + 1 } ) = N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } ) \bigcup R _ { i } ^ { t + 1 } } \\ { P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t + 1 } ) = P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } ) - R _ { i } ^ { t } } \end{array} \right.
$$

b)若 $R _ { i } ^ { t } \subseteq B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } )$ ，则有：

如果 $P ( D _ { j } ^ { t + 1 } \vert { R } _ { i } ^ { t + 1 } ) > \beta$ ，那么

$$
B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 1 } ) = B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } ) - \{ x \_ \}
$$

如果 $P ( D _ { j } ^ { t + 1 } \vert { R } _ { i } ^ { t + 1 } ) \leq \beta$ ，那么

$$
\left\{ \begin{array} { l } { N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t + 1 } ) = N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } ) \bigcup R _ { i } ^ { t + 1 } } \\ { B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 1 } ) = B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } ) - R _ { i } ^ { t } } \end{array} \right.
$$

c)若 $R _ { i } ^ { t } \subseteq N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } )$ ，则有：

$$
N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t + 1 } ) = N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } ) - \{ x _ { - } \}
$$

定理3的证明和定理1的证明类似，略。

定理4在 $I S$ 中，当 $D _ { j } ^ { t + 1 } = D _ { j } ^ { t }$ 并且 $R _ { i } ^ { t + 1 } = R _ { i } ^ { t } - \{ x _ { - } \}$ 时,a)若 $R _ { i } ^ { t } \subseteq P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } )$ ，则有：

$$
P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t + 1 } ) = P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } ) - \{ x _ { - } \}
$$

b)若 $R _ { i } ^ { t } \subseteq B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } )$ ，则有： 如果 $P ( D _ { j } ^ { t + 1 } | R _ { i } ^ { t + 1 } ) \geq \alpha$ ，那么

$$
\left\{ P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t + 1 } ) = P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } ) \bigcup _ { i } { } R _ { i } ^ { t + 1 } \right.
$$

如果 $P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } ) > \beta$ ，那么

$$
B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 1 } ) = B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } ) - \{ x _ { - } \}
$$

c)若 $R _ { i } ^ { t } \subseteq N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } )$ ，则有：

如果 $P ( D _ { j } ^ { t + 1 } | R _ { i } ^ { t + 1 } ) \geq \alpha$ ，那么

$$
\left\{ { P O S } _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t + 1 } ) = P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } ) \bigcup _ { i } R _ { i } ^ { t + 1 } \right.
$$

如果 $\beta < P ( D _ { j } ^ { t + 1 } \mid R _ { i } ^ { t + 1 } ) < \alpha$ ，那么

$$
\left\{ B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 1 } ) = B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } ) \bigcup _ { i } ^ { t + 1 } \right.
$$

如果 $P ( D _ { j } ^ { t + 1 } | R _ { i } ^ { t + 1 } ) \leq \beta$ ，那么

$$
N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t + 1 } ) = N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } ) - \{ x _ { - } \}
$$

定理4的证明和定理1的证明类似，略。

注：定理3对应2.1节第二小节中的情况1，定理4对应2.1节第二小节的情况2。本节默认 $1 \leq i \leq m$ 且 $1 \leq j \leq n$ 。

而由2.1节的性质2所述情况3和情况4，由于结论是决策规则 $R _ { i } ^ { t + 1 } \to D _ { j } ^ { t + 1 }$ 所属的三支决策域保持不变，所以可以直接获得结论，不需要额外计算。

# 3 流计算模式下三支决策动态增减学习算法

# 3.1三支决策动态增减学习算法

流计算模式下，数据在内存计算中同时实现了数据的在 $\mathbf { \Phi } _ { t }$ 时刻后的实时流入和实时流出。借鉴时分复用的思想，将流计算模式中的一次流计算分解 $^ { t + 1 }$ 时刻和 $_ { t + 2 }$ 时刻二个计算步骤：即先在 $^ { t + 1 }$ 时刻执行减量学习，然后在 $t { + } 2$ 时刻执行增量学习。根据上述思想提出以下处理流计算问题的三支决策动态增减学习算法。

算法1：三支决策动态增减学习算法

算法输入：

$t$ 时刻 $I S$ 各条件等价类 $U / R$ 及决策等价类 $U / D$ 信息。

$t$ 时刻每个决策等价类 ${ D } _ { j } ^ { t }$ 的三支决策信息： $P O S _ { ( \alpha , \bullet ) } ( D _ { j } ^ { t } )$ （20、 $B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t } )$ 、 $N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t } )$ 及阈值 $( \alpha , \beta )$ 。

$t + 1$ 时刻减少的对象 $\mathbf { \nabla } x _ { - }$ 及 $t + 2$ 增加的对象 $x _ { + }$ 。

算法输出：

$t { + } 2$ 时刻 $I S$ 各条件等价类 $U / R$ 及决策等价类 $U / D$ 信息。

$t { + } 2$ 时刻每个决策等价类 $D _ { j } ^ { t + 2 }$ 的三支区域 $P O S _ { _ { ( \alpha , \bullet ) } } ( D _ { j } ^ { t + 2 } )$ 、$B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 2 } )$ 、 $N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t + 2 } )$ 信息。

步骤1： $t + 1$ 时刻移除数据 $x _ { _ { - } }$ 并更新每个 $D _ { j } ^ { t } \in U / D$ 的三支决策区域。

步骤1.1：判断被删除对象 $x _ { . }$ 的条件部分属于 $^ { t + 1 }$ 时刻 $I S$ 中的哪个条件等价类。

步骤1.2：判断被删除对象 $x _ { _ { - } }$ 的决策部分属于 $^ { t + 1 }$ 时刻 $I S$ 中的哪个决策等价类。

步骤1.3：对步骤2.1和步骤2.2获得的相关条件等价类与决策等价类的每个决策规则（记为 $R _ { i } ^ { t + 1 } \to D _ { j } ^ { t + 1 }$ )执行如下判断：

(a)如果 $t + 1$ 时刻移除数据 $x _ { _ { - } }$ 符合 $\boldsymbol { x } _ { - } \in D _ { j } ^ { t + 1 } \wedge \boldsymbol { x } _ { - } \notin R _ { i } ^ { t + 1 }$ 和（20 $x _ { - } \notin { D _ { j } } ^ { t + 1 } \land x _ { - } \notin R _ { i } ^ { t + 1 }$ ，根据性质2 则决策规则 $R _ { i } ^ { t + 1 } \to D _ { j } ^ { t + 1 }$ 所属的三支决策域保持不变。

（b）如果 $t + 1$ 时刻移除数据 $x _ { . }$ 符合 $\ v x _ { - } \in D _ { j } ^ { t + 1 } \land \ v x _ { - } \in R _ { i } ^ { t + 1 }$ ，则根据定理3直接判断出决策规则 $R _ { i } ^ { t + 1 } \to D _ { j } ^ { t + 1 }$ 所属的三支决策域。

(c)如果 $t + 1$ 时刻移除数据 $x _ { . }$ 符合 $\boldsymbol { x } _ { - } \notin D _ { j } ^ { t + 1 } \land \boldsymbol { x } _ { - } \in R _ { i } ^ { t + 1 }$ ，则根据定理4直接判断出决策规则 $R _ { i } ^ { t + 1 } \to D _ { j } ^ { t + 1 }$ 所属的三支决策域。

步骤2： $t + 2$ 时刻添加数据 $x _ { + }$ 并更新每个 ${ D _ { j } } ^ { t + 1 } \in U / D$ 的三支决策区域。

步骤2.1：判断添加数据 $x _ { + }$ 的条件部分属于 $t { + } 2$ 时刻 $I S$ 中的哪个条件等价类。

步骤2.2：判断被添加数据 $x _ { + }$ 的决策部分属于 $t { + } 2$ 时刻 $I S$ 中的哪个决策等价类。

步骤2.3：对步骤2.1和步骤2.2获得的相关条件等价类与决策等价类有关的每个决策规则（记为 $R _ { i } ^ { t + 2 } \to D _ { j } ^ { \ t + 2 }$ )执行如下判断：

（a)如果 $t + 2$ 时刻添加数据 $x _ { + }$ 符合 $\ v x _ { + } \in D _ { j } ^ { t + 2 } \land \ v x _ { + } \notin R _ { j } ^ { t + 2 }$ 或$x _ { + } \notin D _ { j } ^ { t + 2 } \land x _ { + } \notin R _ { j } ^ { t + 2 }$ ，根据性质2决策规则 $R _ { i } ^ { t + 2 } \to D _ { j } ^ { { t + 2 } }$ 所属的三支决策域保持不变。

（b）如果 $t + 2$ 时刻添加数据符合 $x _ { + } \in D _ { j } ^ { t + 2 } \land x _ { + } \in R _ { j } ^ { t + 2 }$ ，则根据定理1直接判断出决策规则 $R _ { i } ^ { t + 2 } \to D _ { j } ^ { { t + 2 } }$ 所属的三支决策域。

（c）如果 $t + 2$ 时刻添加数据符合 $x _ { + } \notin D _ { j } ^ { t + 2 } \land x _ { + } \in R _ { j } ^ { t + 2 }$ ，则根据定理2直接判断出决策规则 $R _ { i } ^ { t + 2 } \to D _ { j } ^ { \ t + 2 }$ 所属的三支决策域。

三支决策动态增减学习算法可以是先执行增量学习再执行减量学习，也可以先执行减量学习后执行增量学习，两者等价。本文采用的是先执行减量学习再执行增量学习的策略，其三支决策动态增减学习算法时间复杂度分析如下。

步骤1.1和1.2主要确定 $\mathbf { \nabla } x _ { - }$ 对象属于哪个决策等价类和哪个条件等价类，其计算频度为 $m + n$ 。

步骤1.3中最好情况为子步骤（a）计算频度为1。最坏情况为子步骤（b）和（c)，其主要步骤为条件概率 $P \Big ( \boldsymbol { D } _ { j } ^ { \ t + 1 } \Big | \boldsymbol { R } _ { i } ^ { t + 1 } \Big )$ 的计算，其计算频度为 $K \times \left| { D _ { j } } ^ { t + 1 } \right| \times \left| { R _ { i } ^ { t + 1 } } \right|$

步骤2.1和2.2主要确定 $x _ { + }$ 对象属于哪个决策等价类和哪个条件等价类，其计算频度为 $m + n$ 。

步骤2.3中最好情况为子步骤（a）计算频度为1。最坏情况为子步骤（b）和（c)，其计算频度为 $L \times \left| { D _ { j } } ^ { t + 2 } \right| \times \left| { R _ { i } ^ { t + 2 } } \right|$ 。

注： $K$ 与 $L$ 分别是为与 $x _ { _ - }$ 、 $x _ { + }$ 相关的决策等价类和条件等价类数量， $\scriptstyle \left| U / R \right| = m$ ， $\left| U / D \right| = n$ 。

为便于分析，可约定 $\left| \boldsymbol { D } _ { j } ^ { t + 2 } \right| \times \left| \boldsymbol { R } _ { i } ^ { t + 2 } \right| \approx \left| \boldsymbol { D } _ { j } ^ { t + 1 } \right| \times \left| \boldsymbol { R } _ { i } ^ { t + 1 } \right|$ ，所以三支决策动态增减学习算法时间复杂度为：

$$
O ( \left( \mathrm { K + L } \right) \times ( \left| D _ { j } ^ { \ t + 1 } \right| \times \left| R _ { i } ^ { \ t + 1 } \right| ) + 2 \times ( m + n ) )
$$

# 3.2三支决策经典非增量学习算法

为了便于对比讨论，本文给出流计算模式下三支决策经典非增量学习算法。即数据在内存计算 $t$ 时刻开始实现了数据实时流入和实时流出后 $t + 1$ 时刻的三支决策更新。

算法2：三支决策经典非增量学习算法

算法输入：

$t$ 时刻 $I S$ 与 $t + 1$ 时刻减少的对象 $\mathbf { \nabla } x _ { - }$ 及增加的对象 $x _ { + }$ 及阈值 $( \alpha , \beta )$ 。

算法输出：

$^ { t + 1 }$ 时刻 $I S$ 各条件等价类 $U / R$ 及决策等价类 $U / D$ 信息。

$^ { t + 1 }$ 时刻每个决策等价类 $D _ { j } ^ { t + 1 }$ 的三支区域 $P O S _ { _ { ( \alpha , \bullet ) } } ( D _ { j } ^ { t + 1 } )$ 1$B N D _ { ( \alpha , \beta ) } ( D _ { j } ^ { t + 1 } )$ 、 $N E G _ { ( \bullet , \beta ) } ( D _ { j } ^ { t + 1 } )$ 信息。

步骤1：计算 $t + 1$ 时刻 $I S$ 各条件等价类 $U / R$ 及决策等价类 $U / D$ 信息。

步骤2：计算所有条件等价类与决策等价类之间的条件概率 $P \Big ( \boldsymbol { D } _ { j } ^ { \ t + 1 } \Big | \boldsymbol { R } _ { i } ^ { t + 1 } \Big )$ 。

步骤3：根据所有条件等价类与决策等价类之间的条件概率和阈值 $( \alpha , \beta )$ 进行匹配，完成 $t + 1$ 时刻的三支区域划分。

算法2的算法时间复杂度分析如下。

步骤1计算各个等价类所需计算频度为 $2 | U |$ 。

步骤2所有决策规则的条件概率所需最坏情况的计算频度为 $m \times n \times \left| \boldsymbol { D } _ { j } ^ { \ t + 1 } \right| \times \left| \boldsymbol { R } _ { i } ^ { t + 1 } \right| ,$

步骤3所需计算频度为 $m \times n$ □

注： $\scriptstyle \left| U / R \right| = m , \left| U / D \right| = n$ 。

所以算法2的时间复杂度为：

$$
O \Big ( \big ( m \times n \big ) \times \Big ( \big | D _ { j } ^ { \ t + 1 } \big | \times \big | R _ { i } ^ { t + 1 } \big | + 1 \big ) + 2 \big | U \big | \Big )
$$

约等于 $O \Big ( \big ( m \times n \big ) \times \Big ( \Big | D _ { j } ^ { \ t + 1 } \Big | \times \Big | R _ { i } ^ { \ t + 1 } \Big | \Big ) + 2 \big | U \big | \Big )$

与算法1的时间复杂度对比：

由3.1的分析知算法1的时间复杂度为$O ( \left( \mathrm { K + L } \right) \times ( \left| D _ { j } ^ { \ t + 1 } \right| \times \left| R _ { i } ^ { \ t + 1 } \right| ) + 2 \times ( m + n ) )$ ，与算法2的时间复杂度对比显然 $\left( m \times n \right) > \left( K + L \right)$ 并且 $\left. U \right. > \left( m + n \right)$ ，所以算法1的时间复杂度明显优于算法2的时间复杂度。

由上述两个算法的时间复杂度分析可知：三支决策动态增减学习算法的最大的优势在于不需要对全部数据计算，而只是需要对被删除和新增的相关决策规则数据进行处理。显然三支决策动态增减学习算法计算效率的优势明显。

# 4 实验与分析

上述研究在理论上已经证明了三支决策动态增减学习算法能够获得经典三支决策算法相同的三支决策规则，所以本实验无须验证本算法提取决策规则的有效性是否优于经典算法，而只需要讨论其计算速度是否优于经典算法。本文提出的新算法的研究价值正是在于是否能够有效提升流计算模式下概率三支决策的计算效率。本章将使用UCI上的八个典型数据集进行实验来验证三支决策动态增减学习算法的有效性，以及相对于经典非增量算法在提取三支决策规则上时间花费上的优势。

操作系统为Windows7，机器配置为酷睿i7-2670QM处理器（主频为 $2 . 2 \mathrm { G H z }$ )，配置的内存为8GB，用于实验的Python版本号为3.5.2，IDE为spyder。

实验所使用的八个数据集来自UCI(http://archive.ics.uci.edu/ml/datasets)。数据集 breast cancer,contraceptive method choice ， mammographic mass， monk'sproblems，skin segmentation，thoracic surgery data，Balance Scale和IndianLiverPatientDataset 的详细信息如表1所示。

由于上述部分数据集有些是非数值离散型数据，本文将其统一转换为等价的数值离散型数据。上述数据集中存在的少数缺失数据的情况，本文采用了众数填充的方法进行了缺失值填充处理。对于对连续型数据也进行区间离散化预处理。

由于流计算模式的本质特点是CPU在有限的内存空间内同时实施增量与减量的计算任务。所以本文通过以下过程来模拟数据增量和减量动作。将内存中计算的数据量设置为固定大小。然后按照测试数据集合中各个数据对象的序列顺序，在插入新数据对象的同时删除一个内存中序号最前的数据对象。并重复上述流计算仿真过程直至数据集计算结束。

表1数据集信息表  

<html><body><table><tr><td>编号</td><td>数据集名称</td><td>样本数量</td><td>特征数量</td><td>决策属性 取值数</td></tr><tr><td>1</td><td>breast cancer</td><td>699</td><td>10</td><td>2</td></tr><tr><td>2</td><td>contraceptive Method Choice</td><td>1473</td><td>9</td><td>3</td></tr><tr><td>3</td><td>mammographic mass</td><td>961</td><td>6</td><td>2</td></tr><tr><td>4</td><td>monk's problems</td><td>432</td><td>7</td><td>2</td></tr><tr><td>5</td><td>skin segmentation</td><td>245057</td><td>4</td><td>2</td></tr><tr><td>6</td><td>thoracic surgery data</td><td>470</td><td>17</td><td>2</td></tr><tr><td>7</td><td>Balance Scale</td><td>625</td><td>4</td><td>3</td></tr><tr><td>8</td><td>Indian Liver Patient Dataset</td><td>583</td><td>10</td><td>2</td></tr></table></body></html>

# 4.1三支决策动态增减学习算法与经典非增量算法对比实验

在本实验中设定内存中保存的数据量为100条，阈值 $\alpha$ 与$\beta$ 分别设置为0.75与0.35。本文将收集的测试数据集以对象序号为时间的顺序，利用滑动内存窗口更新内存中的数据。三支决策动态增减学习算法及作为对比的经典三支决策学习算法，都以动态流计算模式中每次动态数据更新后完成三支决策规则提取的消耗时间作为考察指标。实验中记录点为更新数据的数量，从0开始，每更新30个数据作为一个记录点，到300为止共10组记录点。实验做10次取平均提取三支决策规则的耗时结果，如图2所示。

非学习 非学习习 非学习 增学习习法法m  
（s） (su) 500 （su）906000 0070504000 8850 100 更新的5量（m） 250 300 sO 1更新的数据量（(item）250 300 350 50 更新的数据量（(tem）250 300 350 10更新的数据量0250300350(a) breast cancer 数据集 (b) contraceptive method choice 数据集 (c) mammographic mass 数据集 (d)monk's problems 数据集  
国家 非学习法 非学习法 5000] 非学习法 8 非学习4000]3000]2000]  
(su) (su) 000 （）  
007080 0805032000 8850 888805481050 100 150 200 250 300 350 50 100 150 200 250 300 350 50 100 150 200 250 300 350 50 100 150 200 250 300 350更新的数据量(item) 更新的数据量(item） 更新的数据量(item） 更新的数据量(item）(e) skin segmentation 数据集 (f) thoracic surgery data 数据集 (g) Balance Scale 数据集 (h) Indian Liver Patient 数据集

从图2中可以看出，两个算法的时间花费随着替换的数据量均呈现线性增长的趋势，且三支决策动态增减学习算法相对于非增量学习算法的时间花费有大幅度的降低。

由算法的时间复杂度可知，随着内存中的数据更新，三支决策经典非增量学习算法需要进行所有数据等价类的重新划分及条件概率的重新计算，此过程每次执行时间复杂度为$O \Big ( \big ( m \times n \big ) \times \Big ( \Big | D _ { j } ^ { \ t + 1 } \Big | \times \Big | R _ { i } ^ { { t + 1 } } \Big | \Big ) + 2 \big | U \big | \Big )$ ，其时间消耗较大，且与内存中的数据量及等价类的划分相关；而三支决策动态增减学习算法由于只需要对当前实时变化的数据对象进行决策域的更新，最多只需执行时间复杂度为$O ( \left( \mathrm { K + L } \right) \times ( \left| D _ { j } ^ { \ t + 1 } \right| \times \left| R _ { i } ^ { \ t + 1 } \right| ) + 2 \times ( m + n ) )$ ，节省了更新时间。

# 4.2不同阈值下的三支决策动态增减学习算法平均时间花费实验

为验证不同阈值对三支决策动态增减学习算法时间效率的影响， $( \alpha , \beta )$ 将分别采取如下5组取值{(0.6,0.4),(0.7,0.3),(0.8,0.2),(0.9,0.1),(1,0)}进行实验，内存中数据量与实验1一致，仍定为100条。实验将计算更新300条数据下三支决策动态增减学习算法的时间花费，每组做10次，取实验结果的均值进行对比，以此判断阈值对三支决策动态增减学习算法时间复杂度的影响。实验结果如图3所示，其中A-H分别为表一中的数据集1-8。

根据3.2小节的时间复杂度分析可知，时间复杂度和内存中数据集的大小等有关，与阈值并无关联。从图3可以看出，在不同的5组阈值下，基于给定的8组数据集，更新同样大小数据的时间花费基本没有太大的变化，与理论分析相符。

另外通过本实验结果也显示在不同阈值下三支决策动态增减学习算法的时间消耗差异不大，也证明了本算法的对于三支决策阈值的设定具有较好的鲁棒性和适用性。

![](images/25f7ae6e4337d93d3ff9c41370653d1b0a9f8ac6d9e555e1bc96ff1f33364553.jpg)  
图2动态增减学习算法与非增量学习算法时间对比  
图3不同阈值下三支决策动态增减学习算法时间花费

# 5 结束语

本文中以概率粗糙集决策信息系统模型为基础，以三支决策单对象增量、减量的流计算模式为研究对象，实施了流计算模式下的三支决策区域变换决策的推理。并且提出了一种流计算模式下快速三支决策的动态增减学习算法。通过与经典三支决策方法的理论与实验对比，证明了本文提出的三支决策动态增减学习算法不但能够获取的等效的三支决策，而且能够流计算模式下极大的提高计算的时间效率。

随着流计算平台的发展，流计算模式在机器学习和大数据分析领域的应用将越来越得到广泛重视。作为不确定问题求解的重要理论，流计算模式中进行三支决策理论研究不但给流计算模式平台提出了一种不确定问题快速求解的新方法，而且丰富了三支决策的理论体系。

# 参考文献：

[1]Yao Yiyu.An outline of a theory of three-way decisions [M]/ Rough Sets and Current Trends in Computing.Berlin: Springer, 2012:1-17.   
[2]Zhou Bing,Yao Yiyu,Luo Jigang. Cost-sensitive three-way email spam filtering [J].Journal of Intelligent Information Systems,2014,42(1):19-45.   
[3]Zhang Zhifei,Miao Duoqian,Nie Jianyun,et al.Sentiment uncertainty measure and classification of negative sentences [J]. Journal of Computer Research & Development,2015,52(8):1806-1816.   
[4]Li Huaxiong,Zhang Libo,Huang Bing,et al. Sequential three-way decision and granulation for cost-sensitive face recognition [J].Knowledge-Based Systems,2016,91(C): 241-251.   
[5]Assuncäo M D,Calheiros R N,Bianchi S,et al. Big data computing and clouds: trends and future directions [J].Journal of Parallel & Distributed Computing,2015,79-80:3-15.   
[6]孙大为，张广艳，郑纬民．大数据流式计算：关键技术及系统实例[J]. 软件学报,2014,25(4):839-862.   
[7]Zhang Junbo,Zhu Yun,Pan Yi,et al.Eficient parallel boolean matrix based algorithms for computing composite rough set approximations☆[J]. Information Sciences,2016,329:287-302.   
[8]Li Shaoyong,Li Tianrui,Hu Jie.Update of approximations in composite information systems [J].Knowledge-Based Systems,2015,83(1):138-148.   
[9]Zeng Anping,Li Tianrui, Hu Jie,et al. Incremental updating fuzzy rough approximations for dynamic hybrid data under the variation of attribute values[J].Information Sciences,2016,378(C):363-388.   
[10]Luo Chuan，Li Tianrui,Chen Hongmei,et al.Efficient updating of probabilistic approximations with incremental objects [J].KnowledgeBased Systems,2016,109:71-83.   
[11] Chen Hongmei,Li Tianrui Luo,Chuan,et al.A decision-theoretic rough set approach for dynamic data mining[J].IEEE Trans on Fuzzy Systems,2015, 23 (6): 1958-1970.   
[12]Li Meizheng,Wang Guoyin.Approximate concept construction with threeway decisions and attribute reduction in incomplete contexts [J]. Knowledge-Based Systems,2016,91:165-178.   
[13]DasRT,Kai KA,Chai Q.ieRSPOP:a novel incremental rough set-based pseudo outer-product with ensemble learning [J].Applied Soft Computing, 2016,46:170-186.   
[14]Azam N,Zhang Yan,Yao JingTao.Evaluation functions and decision conditions of three-way decisions with game-theoretic rough sets [J]. European Journal of Operational Research,2017,261 (2): 704-714.   
[15] Yao Yiyu.Probabilistic rough set approximations [J]. International Journal ofApproximate Reasoning,2008,49 (2):255-271.   
[16] Yao Yiyu.The superiority of three-way decisions in probabilistic rough set models [J].Information Sciences,2011,181(6):1080-1096.