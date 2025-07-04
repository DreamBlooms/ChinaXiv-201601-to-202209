# 多最小效用阈值的频繁高效用项集快速挖掘算法

王斌，吕瑞瑞，房新秀，马俊杰(青岛理工大学 信息与控制工程学院，山东 青岛 266033)

摘要：针对多最小效用阈值高效用项集挖掘算法(MHUI)中出现的重复计算、挖掘的结果项集不是频繁的问题，提出两个新的快速挖掘算法FMHUI和SFMHUI。FMHUI算法在计算项集的最小效用阈值时利用前一次计算结果，避免了项之间的重复比较。另外定义了项的扩展项的最小效用阈值表 EMMU-table快速计算出扩展项的最小效用阈值，提高了运行效率。SFMHUI算法在FMHUI的基础上增加了支持度约束，使挖掘的项集既是高效用的也是频繁的。通过仿真实验验证了所提出算法的高效性和可行性。

关键词：频繁项集；高效用项集；支持度；多最小效用阈值中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2018.06.0403

# Fast mining algorithm for frequent and high utility itemsets with multiple minimum utility thresholds

Wang Bin,Lyu Ruirui, Fang Xinxiu, Ma Junjie (SchoolofInformation&Control Engineering,Qingdao Technological University,Qingdao Shandong 266033,China)

Abstract: In miningalgorithmforhigh utility itemsets with multiple minimumutilitythreshold(MHUI),calculationisoften repeatedand miningresult itemsets arenot frequent.This paperdeveloped two newfast mining algorithm SFMHUIandFMHUI. TheFMHUI algorithmusedthe previouscalculationresult inthecalculationofthe minimum utilitythresholdoftheitemsets, avoidingduplicatecomparisonsbetwee items;inaddition,theFMHUIalgorithmdefinedthe minimumutilitythresholdtable EMMU-tableofextensions ofitems toquicklycalculate the minimumutilitythresholdofextensions,improvingtheeffciency. The SFMHUIalgorithmadded thesupportconstraints onthebasisofFMHUI,making the mining itemsetsboth high-utilityand frequent.The result from simulation experiments shows that the proposed algorithms are eficient and feasible.

Key Words: frequent itemsets; high utility itemsets;support; multiple minimum utility thresholds

# 0 引言

挖掘高效用项集是Chan 等人 $[ 1 ^ { \sim } 4 ]$ 在 2003 年首次提出的，近几年来挖掘高效用项集在现实生活中应用非常广泛，如市场购物篮分析[4,5]、网站点击流分析[6、零售商店中的交叉营销、医疗保健和生物医学应用等[5,7,8]。

最初，高效用项集挖掘算法都是采用单一效用阈值，如HUC-Prune[9]、UP-Growth $+ [ 1 0 ]$ 、MU-Growth[11]、HUI-Miner[12],FHM[13]、HUP-Miner[14]、EFIM[15]算法等。但是采用单一效用阈值没有考虑项的多样性，这在现实生活中是不适当的和不公平的。因此采用多最小效用阈值挖掘高效用项集应运而生，它考虑了项之间的差异，对每一个项都赋一个最小效用阈值，解决了单一效用阈值的不足。多最小效用阈值挖掘算法主要有文献[16]中基于 Apriori[17]算法的 HUI-MMU、HUI-MMUTID、

HUI-MMUrE，它们与Apriori算法一样产生了过多的候选项集和需要多次扫描数据库；文献[18]基于多最小项效用集合枚举树MIU-tree(multiple itemutility Set-enumeration tree)和效用列表的HIMU、HIMU-EUCP算法，避免了额外的数据库扫描和候选项集产生。以上两类算法都有一个共同的特点，项的处理顺序是按照项最小效用阈值递增排序，避免了在求项集的最小效用阈值时项最小阈值之间的比较。后来，Krishnamoorthy[19]提出多最小效用阈值挖掘算法 MHUI (highutility itemsets withmultipleminimumutilitythresholds)，它采用效用列表结构并通过四种剪枝策略来提高挖掘效率，但是MHUI算法的项的处理顺序是按照事务权重效用 $\mathrm { T W U } ^ { [ 1 8 ^ { \sim } 2 0 ] }$ (transaction weighted utility)递增排序的,并且验证了采用TWU进行排序处理比采用项的最小效用阈值进行排序效率更高（因为采用项最小效用阈值排序虽然避免了项最小阈值之间的比较，但是会导致候选项集数量的增加，而按TWU进行排序产生更少的候选项集，从而使效率更高）。然而MHUI算法在求每个项集的最小效用阈值和扩展项的最小效用阈值时，项集及其扩展项的最小效用阈值都要重新比较，进行了多次重复计算，降低了挖掘效率。针对MHUI算法的这个问题，本文提出w多最小效用阈值的高效用项集快速挖掘算法 FMHUI( fast mining high utility itemsets with multipleminimumutilitythresholds），并结合四个剪枝性质加以改进。

以上的这些算法只能保证挖掘的项集是高效用的，对项集是不是频繁的并不能确定。众所周知，高效用项集挖掘和频繁项集挖掘在数据挖掘领域都有着非常重要的意义[17,21]。但是大多数的研究要么使用支持度约束来挖掘频繁项集，要么使用效用约束来挖掘高效用项集。然而单独考虑这两种约束都有各自的局限性，比如支持度很高的项集其效用不一定高，同样效用很高的项集其支持度也不一定高。由表1和2知(设最小支持度阈值2/6),项集af,其效用值 $\mathrm { U } ( \mathrm { a f } ) { = } 1 8 { > } 1 5$ 是高效用项集，但是其支持度 $\operatorname* { s u p } ( { \mathrm { a f } } ) { = } 1 / 6 { < } 2 / 6$ 不是频繁项集，而项集 ad 其支持度$\mathrm { s u p } ( \mathrm { a d } ) { = } 2 / 6 { = } 2 / 6$ 是频繁项集，但是其效用值 $U ( { \mathrm { a d } } ) { = } 2 4 { < } 2 5$ 不是高效用项集。针对这个问题，本文提出加上支持度约束，并在改进的FMHUI算法的基础上提出有支持度约束的多最小效用阈值高效用项集快速挖掘算法 SFMHUI（FMHUIwith supportconstraints），解决了MHUI算法的重复计算和挖掘的结果不是频繁项集的问题。

# 1 相关定义及问题陈述

给定 $I = \{ i _ { 1 } , i _ { 2 } , . . . , i _ { m } \}$ 是一个含有 $\mathbf { \nabla } m$ 个不同项的集合，任意事务 $T _ { j } = \{ x _ { l } | l = 1 , 2 , . . . , N _ { l } , x _ { l } \in I \} ( 1 \leq N _ { j } \leq m )$ 是 $I$ 的一个子集。对$T _ { j }$ 中任意 $x _ { i } \in T _ { j }$ ，都由外部效用 $E U ( x _ { i } )$ 和内部效用 $I U ( x _ { i } , T _ { j } )$ 表征；数据库 $D = \{ T _ { 1 } , T _ { 2 } , . . . , T _ { n } \}$ (n 是事务的总数)是所有事务的集合；项集 $X = \{ x _ { 1 } , x _ { 2 } , . . . , x _ { k } \} \subseteq I$ 被称为 $K \cdot$ -项集。一个样本数据库 $D$ 如表1所示，每个项的外部效用 $\mathrm { E U } ( x _ { i } )$ 、最小效用 $\mathrm { \ M U ( x _ { i } ) }$ 和事务权重效用(TWU)如表2所示。

定义1项 $x _ { i }$ 在 $T _ { j }$ 中的效用用 $U ( x _ { i } , T _ { j } )$ 表示，定义为

$$
\mathrm { U } ( \mathrm { x } _ { \mathrm { i } } , \mathrm { T } _ { \mathrm { j } } ) { = } \mathrm { E U } ( \mathrm { x } _ { \mathrm { i } } ) { * } \mathrm { I U } ( \mathrm { x } _ { \mathrm { i } } , \mathrm { T } _ { \mathrm { j } } )
$$

定义2项集 $\mathrm { \Delta } \mathrm { X }$ 在事务 $\mathrm { T j }$ 中的效用用U(X,Tj)表示，定义为

$$
U ( { \mathrm { X } } , { \mathrm { T } } _ { \mathrm { j } } ) = \sum _ { \mathrm { x } _ { \mathrm { i } } \in { \mathrm { X } } } \mathrm { U } ( \mathrm { x } _ { \mathrm { i } } , \mathrm { T } _ { \mathrm { j } } )
$$

定义3项集X在数据库 $D$ 的效用用U(X)表示，定义为

$$
U ( X ) = \sum _ { X \subseteq T _ { j } \in D } U ( X , T _ { j } )
$$

定义4事务 $\mathrm { T j }$ 的效用用TU(Tj)表示，即

$$
T U ( T _ { j } ) = \sum _ { X \subseteq T _ { j } \land x _ { i } \in X } U ( x _ { i } , T _ { j } )
$$

定义5项集X的事务权重效用用TWU(X)表示,定义为

$$
T W U ( X ) = \sum _ { X \subseteq T _ { j } \in D } T U ( T _ { j } )
$$

定义6所有项的最小效用阈值用MMU(multiple minimumutility)表示，定义为

$$
M M U = \{ M U ( x _ { 1 } ) , M U ( x _ { 2 } ) , . . . , M U ( x _ { m } ) \}
$$

其中： $m$ 为不同项的个数。如数据库D的$\mathrm { M M U } { = } \{ 2 5 , 3 0 , 1 7 , 2 8 , 2 2 , 1 5 \}$

表1样本数据库D  

<html><body><table><tr><td>Tid</td><td>项 (item)</td><td>内部效用 (IU)</td><td>效用 (U)</td><td>事务效用 (TU)</td></tr><tr><td>T1</td><td>a,c,d, f</td><td>3,2,3,2</td><td>12,6,3,6</td><td>27</td></tr><tr><td>T2</td><td>a,d,e</td><td>2,1,2</td><td>8,1,18</td><td>27</td></tr><tr><td>T3</td><td>a,b,c,e</td><td>1,2,2,1</td><td>4,16,6,9</td><td>35</td></tr><tr><td>T4</td><td>b,d,e</td><td>1,3,2</td><td>8,3,18</td><td>29</td></tr><tr><td>T5</td><td>b,c,d</td><td>3,5,2</td><td>24,15,2</td><td>41</td></tr><tr><td>T6</td><td>b,c,d,e</td><td>3,2,4,1</td><td>24,6,4,9</td><td>43</td></tr></table></body></html>

定义7用LMU(least minimum utility threshold)表示所有项的最小最小效用阈值，定义为

$$
L M U = \operatorname* { m i n } \{ M U ( x _ { 1 } ) , M U ( x _ { 2 } ) , . . . , M U ( x _ { m } ) \}
$$

定义8 $\mathbf { k } .$ 项集 $X { = } \{ x _ { l } , ~ x _ { 2 } , ~ . ~ . ~ . ~ , ~ x _ { k } \}$ 的最小效用阈值用$\mathrm { M I U ( X _ { k } ) }$ 表示，定义为

$$
M I U ( X _ { k } ) = \operatorname* { m i n } \{ M I U ( X _ { k - 1 } ) , M U ( x _ { k } ) \}
$$

定义9项的排序。把所有项按项的事务权重效用进行递增排序，通过表2可以看出 $f \prec a \prec e \prec c \prec b \prec d$ 。数据库D项的重新排序见表3(因 $\operatorname { s u p } ( { \mathrm { f } } ) { = } 1 / 6 { < } 2 / 6 .$ 所以接下来在使用数据库 $D$ 时f已被删除，即表3)。

定义10在 $\mathrm { T _ { j } }$ 中项集 $X$ 之后的项，用 $\mathrm { T _ { j } / X }$ 表示，其效用称为 $\mathrm { \Delta } \mathrm { X }$ 的剩余效用用 $\mathrm { R U ( T j / X ) }$ 表示，定义为

$$
R U ( T _ { j } / X ) = \sum _ { x _ { i } \in ( T _ { j } / X ) } U ( x _ { i } , T _ { j } )
$$

例如 $\scriptstyle \mathrm { , R U ( T _ { 6 } / e c ) = U ( b , T _ { 6 } ) + U ( d , T _ { 6 } ) = 2 8 }$

表2项的效用信息  

<html><body><table><tr><td>item</td><td>a</td><td>b</td><td>c</td><td>d</td><td>e</td><td>f</td></tr><tr><td>EU</td><td>4</td><td>8</td><td>3</td><td>1</td><td>9</td><td>3</td></tr><tr><td>MU</td><td>25</td><td>30</td><td>17</td><td>28</td><td>22</td><td>15</td></tr><tr><td>TWU</td><td>89</td><td>148</td><td>146</td><td>166</td><td>134</td><td>27</td></tr></table></body></html>

定义11数据库中的项按定义9排序后，定义排在项 $x _ { i }$ 之后的所有项称为项 $x _ { i }$ 的扩展。项 $x _ { i }$ 及 $x _ { i }$ 的扩展所对应的最小效用阈值用 $E M U ( x _ { i } )$ 表示，数据库中所有项的扩展项最小效用阈值EMU(extended minimumutility thresholdof items)用扩展项的多最小效用阈值表 EMMU-table(extended multiple minimumutilitythresholdtableforitems)表示,定义为

$$
E M M U - t a b l e = \{ E M U ( x _ { 1 } ) , E M U ( x _ { 2 } ) , . . . , E M U ( x _ { m } ) \}
$$

需要特别指出的是，求EMMU-table时是按照排序后的项倒序求每个项的EMU。例如项的排序是 $ { \boldsymbol { a } } \prec  { \boldsymbol { e } } \prec  { \boldsymbol { c } } \prec  { \boldsymbol { b } } \prec  { \boldsymbol { d } }$ ，先求 $\mathrm { E M U ( d ) } { = } 2 8$ ，然后 $\scriptstyle \mathrm { E M U ( b ) = m i n } \{ \mathrm { E M U ( d ) , M U ( b ) } \} = 2 8$ ；同理，EMU(c)=min{EMU(b),MU(c)}=17,EMU(e)=17,EMU(a)=17,因此表1的 EMMU-table={17,17,17,20,20} 。

定义12利用项集的扩展，引入一个全局最小效用阈值

GMU（global minimumutility threshold），定义为

$$
G M U ( X ) = \operatorname* { m i n } \{ M I U ( X ) , E M U ( x _ { k } ) \}
$$

其中： $x _ { k }$ 为项集 $X$ 的最后一项。例如：

$$
\mathrm { G M U ( a c ) } = \operatorname* { m i n } \left\{ \mathrm { M I U ( a c ) } , \mathrm { E M U ( c ) } \right\} = \operatorname* { m i n } \left\{ 1 7 , 1 7 \right\} = 1 7
$$

表3排序处理后的数据库D  

<html><body><table><tr><td>Tid</td><td>项 (item)</td><td>效用 (U)</td><td>事务效用 (TU)</td></tr><tr><td>T1</td><td>a,c,d</td><td>12,6,3</td><td>21</td></tr><tr><td>T2</td><td>a,e,d</td><td>8,18,1</td><td>27</td></tr><tr><td>T3</td><td>a,e,c,b</td><td>4,9,6,16</td><td>35</td></tr><tr><td>T4</td><td>e,b,d</td><td>18,8,3</td><td>29</td></tr><tr><td>T5</td><td>c,b,d</td><td>15,24,2</td><td>41</td></tr><tr><td>T6</td><td>e,c,b,d</td><td>9,6,24,4</td><td>43</td></tr></table></body></html>

定义13项集X在数据库中出现的事务数占总事务数的比率，称为项集X的支持度，用 $s u p ( \boldsymbol { X } )$ 表示。

性质1 如果项集X 的支持度 sup(X)<minsup，那么X的所有超集的支持度都小于minsup,该性质称为项集的反单调性[17]。

定义14数据库中所有项组成的2-项集支持度矩阵用预估支持度共现结构ESCS（estimated support co-occurrencestructure）表示，定义为

$$
E S C S ( X = \{ x _ { i } , x _ { j } \} ) = \operatorname* { s u p } ( X = \{ x _ { i } , x _ { j } \} )
$$

这是个三角阵用来存储数据库中所有2-项集的支持度，可参照预估效用共现结构 EUCS(estimated utility co-occurrencestructure )[13,14]。

问题陈述：本文目的就是在数据库中挖掘所有频繁高效用项集FHUIs（frequent and high utility itemsets），即

$$
\begin{array} { r l } & { F H U I s = \{ X : U ( X ) : \operatorname* { s u p } ( X ) \big | X \subseteq I , U ( X ) \geq M I U ( X ) , } \\ & { \operatorname* { s u p } ( X ) \geq \operatorname* { m i n } \operatorname* { s u p } \} } \end{array}
$$

# 2 SFMHUI算法

因为SFMHUI算法是FMHUI算法加上支持度的改进，所以本章主要介绍SFMHUI算法的搜索空间、剪枝性质以及算法的主要流程。在此之前先介绍算法的数据存储结构，可参照文献 $[ 1 2 ^ { \sim } 1 4 , 1 9 ]$ 所介绍的效用列表结构来存储项集信息,并在此基础上加上支持度相关的统计信息，即每个项集的Tid的总数。其初始（即1-项集）效用列表如图1所示。

a(25) e(22) c(17) b(30) d(28)   
3 24 59 4 54 75 4 33 73 4 72 9 5 20 0   
1 12 9 2 18 8 1 6 3 3 16 0 1 3 0   
2 8 19 3 9 22 3 6 16 4 8 3 2 8 0   
3 4 31 4 18 11 4 3 0   
6 9 34 5 15 26 5 24 2 5 2 0   
6 6 28 6 24 4 6 4 0

所示。SFMHUI算法挖掘时采用深度优先搜索，因此 $\mathbf { k } { + } \mathbf { l }$ 项集11) 的最小效用阈值可以用 $\operatorname* { m i n } \{ M U ( x _ { k + 1 } ) , M I U ( X _ { k } ) \}$ ，而不是每次都重新比较项集中所有项的最小效用阈值（20 $( \operatorname* { m i n } \{ M U ( x _ { 1 } ) , M U ( x _ { 2 } ) . . . M U ( x _ { k + 1 } ) \}$ 其中 $\mathbf { k } { = } 1 , 2 , 3 . . . . )$ ，从而减少了重复计算，提高了算法的运行效率。

![](images/42a8a6f8458c560549d923e3bbdb9a76f686514cc72fba4776c6b6c270fcaf2b.jpg)  
图2集合枚举树  
图1初始效用列表

# 2.2 主要的剪枝策略

SFMHUI算法挖掘的项集是频繁高效用项集，即挖掘出的项集其支持度和效用值都必须满足最小的约束条件。因此可参照高效用项集挖掘和频繁项集挖掘中的一些剪枝性质 $[ 1 3 , 1 6 ^ { \sim }$ 19,21,22]，但是它们有的并不能直接使用，需要转换成适合SFMHUI算法的剪枝性质。下面是主要的剪枝性质：

性质2Item-Prune。如果有项 $x _ { i }$ 其 $T W U ( x _ { i } ) < L M U$ 或者$\operatorname* { s u p } ( x _ { i } ) < \operatorname* { m i n } \operatorname* { s u p }$ ，那么由项 $x _ { i }$ 组成的所有项集都不可能是频繁高效用项集。

性质3 SU-Prune。如果一个项集X，其$U ( X ) + R U ( X ) < G M U ( X )$ 或者 $\operatorname* { s u p } ( X ) < \operatorname* { m i n } \operatorname* { s u p }$ 那么有$\forall X \beth X , X ^ { \setminus } \notin F H U I s$ 。

证明 $U ( X ^ { \setminus } ) = \sum _ { T _ { j } \in D } U ( X ^ { \setminus } , T _ { j } )$

$$
\leq \sum _ { T _ { j } \in D } U ( X ) + R U ( X )
$$

$$
\begin{array} { l } { \leq U ( X ) + R U ( X ) } \\ { < G M U ( X ) } \\ { < M I U ( X ) } \end{array}
$$

其支持度约束根据性质1可证。因此，X及 $\mathrm { \Delta } \mathrm { X }$ 的超集都不是频繁高效用项集。

性质4EC-Prune。如果 $E U C S ( X ) < G M U ( X )$ 或者$E S C S ( X ) < \mathrm { m i n s u p }$ ，那么没有 $\mathrm { \Delta } \mathrm { X }$ 的超集是频繁高效用项集。

性质5 给定两个项集 $\mathrm { \Delta } \mathrm { X }$ 和 $\mathrm { \Delta Y }$ ，如果$U ( X ) + R U ( X )$ ${ \sum U ( X , T _ { j } ) + R U ( X , T _ { j } ) < G M U ( X ) }$ 那么$\forall T _ { j } { \in } D , X ^ { ^ { * } } { \subseteq } T _ { j } ^ { ^ { * } } { \wedge } Y { \not \subset } T _ { j }$ （20$\forall Y \overset { \cdot } { \underset { } { = } } Y \wedge X ^ { \cdot } \supseteq X , X ^ { \cdot } Y ^ { \cdot } \notin F H U I s$

# 2.1搜索空间

高效用项集挖掘问题的搜索空间都可以用一个集合枚举树表示。以数据库 D(表 3)为例，其项 $x _ { i } \in I = \{ a , b , c , d , e \}$ 且$\mathbf { a } \prec \mathbf { e } \prec \mathbf { c } \prec \mathbf { b } \prec \mathbf { d }$ ，则I的所有项集用集合枚举树表示，如图2

证明参照文献[19]。

在算法运行过程，通过使用上面四种剪枝策略，可以有效地提高频繁高效用项集挖掘的效率。接下来介绍SFMHUI算法。

# 2.3 SFMHUI算法介绍

SFMHUI算法重新定义了最小效用阈值的计算方法，即利用前一次计算的结果，避免前面已经计算的项集的最小效用阈值再重复计算的问题。并且利用求出的EMMU-table 快速得到项的扩展项的最小效用阈值，提高了求项集的全局效用GMU的效率，从而提高了算法的运行效率。加上支持度约束使挖掘的项集是频繁高效用项集。下面介绍详细算法：

算法1以事务数据库D、最小支持度阈值minsup 和所有项的最小效用阈值MMU作为输入。算法总共扫描数据库两次，第一次扫描后计算出所有1-项集的事务权重效用TWU和支持度值sup；第二次扫描时（算法5、6步）做的工作主要有：a)利用Item-Prune 剪枝没有希望的1-项集(性质2剪掉的项)并重新计算所有事务的事务效用TU（transactionutility）；b）为所有有希望(即 $I ^ { * }$ 中的项）的1-项集构建EUCS、ESCS结构以及1-项集效用列表（图1）。然后，产生的1-项集效用列表用于产生项集搜索树并挖掘频繁高效用项集.

算法1SFMHUI算法：main

输入：数据库D,所有项的最小效用阈值MMU，最小支持度阈值minsup。   
输出：频繁高效用项集FHUIs。   
1 Scan D and compute TwU and sup for all 1-itemsets   
2 $\tau ^ { * } \gets$ each and item $x ^ { \mathrm { i } }$ such that $T W U ( x _ { i } ) \geq L M U$ and   
$\operatorname* { s u p } ( x _ { i } ) \geq$ min sup $/ { ^ * }$ 性质 $2 * 1$   
3Let $\succ \mathsf { b } \mathsf { e }$ the total order of TwU ascending values on $\tau ^ { * }$   
and caculate EMMU -table   
4 For each $T _ { j } \in D$ sort $x _ { i } ^ { \prime } s$ in $\tau _ { j }$ as per TwU ascending   
order and recompute TU   
5Iteratively construct 1-itemset( $x _ { i } \in I ^ { * }$ ）ULs and EUCS   
structure and EScS structure   
6 FHUIS $\mathbf { \sigma } _ { : = } ^ { : }$ Explore-Search-Tree({},ULs,MMU,minsup)

/\*算法 $2 ^ { * / }$

算法2和3主要是项集搜索树的挖掘过程和项集效用列表的构建过程。其中，算法2主要利用剪枝性质3、4进行剪枝搜索空间，算法3主要介绍项集列表的构建过程[12,14,18]和剪枝策略5的应用。

#

算法2 SFMHUI：Explore-Search-Iree输入：以项集P为前缀的的效用列表P，所有P的1-扩展效用列表集ULs(utility-lists)，MMU，minsup，EMMU-table。输出：以P为前缀的所有频繁高效用项集FHUIs。1 for each utility list $\mathsf { x }$ in ULs do2 if $U ( X ) \geq M I U ( X )$ （204号 and （204号 $\operatorname* { s u p } ( X ) \geq \operatorname* { m i n s u p }$ then$F H U I s = \{ F H U I s \cup X \}$ 3 if $U ( X ) + R U ( X ) \geq G M U ( X )$ and $\operatorname* { s u p } ( X ) \geq \operatorname* { m i n } \operatorname* { s u p }$ then（204号 $/ { ^ * }$ 性质 $3 ^ { * } /$ 4 $e x U L s \gets \{ \}$ 5 for each utility list $\textsf { \textsf { Y } }$ after $\mathsf { x }$ in ULs do6 if $E U C S ( X - P , Y - P ) \ge G M U ( X )$ and$E S C S ( X - P , Y - P ) \ge 1$ minsup then

7 $/ { ^ * }$ 性质 $4 ^ { * } /$ （20   
8 $U L ( X Y ) =$ Construct-Utility-List $( \mathsf { P } , \mathsf { X } , \mathsf { Y } )$ （204号   
9 /\*算法3\*/   
10 if UL(XY) $\neq$ NULL then   
11 $e x U L s = \{ e x U L s \cup U L ( X Y ) \}$   
12 end if   
13 end if   
14 end for   
15 Explore-Search-Tree(X,exULs,MMU,minsup，EMMU   
table)

16. end if

17. end for

算法3SFMHUI: Construct-Utility-List  
输入：项集P, $\mathsf { P x }$ ，Py 的效用列表。  
输出：项集Pxy 的效用列表。  
1 ${ \mathsf { U L } } \left( { \mathsf { P x y } } \right) ~ = ~ { \mathsf { N U L L } }$   
2 set TUTIL $( \mathsf { P } \mathsf { x } ) { = } \mathsf { U } ( \mathsf { P } \mathsf { x } ) { + } \mathsf { R } \mathsf { U } ( \mathsf { P } \mathsf { x } )$ $/ { ^ * }$ 性质 $5 * /$   
3 for each $e x \in P x$ do  
4 if $\exists e y \in P y$ and ex.tid $\scriptstyle = =$ ey.tid then  
5 if P is not empty then  
6 Search element $e \in P$ such that e.tid $= =$ ex.tid  
6 exy=<ex.tid,U(ex,ex.tid) $+ \mathsf { U }$ (ey,ey.tid)-U(e,e.tid),  
RU(ey,ey.tid)>  
7 else  
8 exy=<ex.tid,U(ex,ex.tid) $+ \mathsf { U }$ (ey，ey.tid)，Ru(ey,ey.tid)>  
9 end if  
11 UL(Pxy)={UL(Pxy）Uexy}  
12 创建或者更新 UL(Pxy)  
13 else $/ { * }$ 重新计算TUTIL，并利用性质 $5 ^ { * }$ /  
14 TUTIL(PX) $\mathbf { \sigma } = \mathbf { \sigma }$ TUTIL $\langle \mathsf { P } \mathsf { X } .$ )-U(PX,ex.tid)-RU(Px,E.tid)  
15 if TUTIL(Px)<GMU(Px） then return NULL  
16 end if  
17 end for  
18 return UL(Pxy)

# 3 实验分析

为了验证提出算法的高效性和可行性，本文进行两组仿真实验：MHUI和FMHUI算法。SFMHUI和SMHUI算法(SMHUI算法是在MHUI算法的基础上加上与SFMHUI算法相同的支持度约束条件以及相关的频繁项集剪枝策略)。这两组对比实验的目的：一是验证在相同的条件下改进后的算法效率更高；二是验证算法加上支持度约束后算法是可行的。实验环境如下：操作系统Windows7(64位),开发工具eclipse,编程语言为Java,4 GB 内存容量，英特尔i5 处理器。

表4数据集特征  

<html><body><table><tr><td>数据集</td><td>事务数量</td><td>项数(I)</td><td>平均长度(A)</td><td>密度(A/I）%</td></tr><tr><td>Mushroom</td><td>8124</td><td>119</td><td>23</td><td>19.3</td></tr><tr><td>Accidents</td><td>340183</td><td>468</td><td>33.8</td><td>7.2</td></tr></table></body></html>

# 3.1实验设计

通过在Accidents 和Mushroom上进行评估实验。这两个数据集都是从SPMF[23]文库中下载的。这两个数据集的特征如表4所示。

项的内部效用在 $_ { 1 \sim 1 0 }$ 整数之间随机产生，外部效用使用对数正态分布在 $0 . 0 1 { \sim } 1 0$ 之间随机产生，可参照文献 $[ 1 2 ^ { - } 1 4 ]$ 。每个项赋最小阈值，参照文献[16,18,19]中的赋值方式，即

$$
M U ( x _ { i } ) = \operatorname* { m a x } ( \beta \ast \mathrm { E U } ( x _ { i } ) , G L M U )
$$

其中：GLMU（global least minimum utility thresholds）是一个用户设定的全局最小效用阈值； $\beta$ 是一个恒定的值来设定每个项的最小效用阈值，当β为0时，每个项的效用阈值都是GLMU，就变成人们最常见的单一效用阈值了。

# 3.2 实验结果分析

本文提出的算法主要验证加上支持度约束时挖掘频繁高效用项集算法的可行性以及算法效率的提高。因为在内存使用方面并没有明显的减少，所以这里就不做分析了。首先分析FMHUI与MHUI算法，其仿真结果如图3和4所示。其中图3是β为常量，在Accidents和Mushroom中，β分别为500万和10万。与MHUI算法相比，FMHUI算法的时间效率平均提高 $2 5 . 4 \%$ 和 $30 . 6 \%$ 。图4是以GLMU为常量，在Accidents和Mushroom中，GLMU分别为1200万和10万，其时间效率分别提高 $14 \%$ 和 $14 . 8 \%$ 。这是因为FMHUI利用定义8、11减少了重复计算，提高了运行效率。

![](images/5c5cef793098fd166ff5e62c06e751039335ef57100a4e9a90ce85bc147d514c.jpg)  
图3不同GLMU下算法的运行时间

![](images/849edb2a08fc6787119dbf12d4317ea47e80da1f2ccbd1c98cb7353c200d6321.jpg)  
图4不同β下算法的运行时间

图5和6是SFMHUI算法和SMHUI算法的实验结果。因为这里主要是验证加上支持度约束时两种算法的实验结果，所以为了方便只考虑β和GLMU 两个中的一个，这里只考虑了GLMU。把Accidents和Mushroom的β分别设为500万和5万。图5是在GLMU分别为1400万和10万时，SFMHUI和SMHUI算法以最小支持度(minsup)为变量的情况下的运行时间。图6是在相同支持度时，改变GLMU值算法的运行时间。此时Accidents和Mushroom的支持度分别为0.46和0.1。从这两个图可以看出，SFMHUI比SMHUI算法更高效，提出的改进算法进一步得到验证。

![](images/ec70466fdecbc3b71ec6b67ca614a852047bba1dfb36b47f642f575999b28647.jpg)  
图5不同minsup下算法的运行时间

![](images/aaaa487fd68e6727d8cfbd703c52d92325fa47b8ddda69192880496bf1e6eb70.jpg)  
图6不同GLMU下算法的运行时间

图7和8分析了在两个数据库中不同支持度下频繁高效用项集的数量。当minsup $_ { \cdot = 0 }$ 时，相当于没有支持度约束，然后随着支持度阈值约束minsup的增加，频繁高效用项集的数量在不断减少，验证了SFMHUI算法的可行性。有了支持度约束，挖掘的高效用项集对决策者来说更有参考价值。

![](images/63d0b1614ae275f5117ae6ee45e1767481e7d6adbad92e6841598c271f88ba08.jpg)  
图7在Accidents中不同支持度下FHUIs数量

![](images/21e1da1108d534f8c62b5ad9f9340e8b16924e2ab6702dc41f49cada99320aab.jpg)  
图8在Mushroom数据库中不同支持度下FHUIs数量

# 4 结束语

本文提出的FMHUI算法解决了多最小效用阈值挖掘算法MHUI存在的重复计算、重复比较问题；提出的SFMHUI算法在 FMHUI 算法的基础上增加支持度约束，进一步解决了挖掘的项集不是频繁项集的问题。两种算法都通过四个剪枝性质来提高挖掘效率，最后通过仿真实验进行了验证。但是本文在内存占用方面没有得到明显的改进，未来可以进一步结合并行计算减少内存消耗、提高算法运行效率；还可以考虑结合前缀效用树的节点列表PUN-list（(prefixutility tree-node list）结构来提高挖掘效率，这些将是笔者下一步研究的方向和重点。

# 参考文献：

[1]Chan R, Yang Qiang,Shen Yidong.Mining high utility itemsets [C]//Proc of IEEE International Conference on Data Mining.Washington DC:IEEE Computer Society,2003:19-29.   
[2]Duong QH,Liao Bo,Fournier-Viger P,et al.An efficient algorithm for mining the top-k, high utility itemsets,using novel threshold raising and pruning strategies [J].Knowledge-Based Systems,2016,104:106-122.   
[3]Lin Chunwei,Gan Wensheng,Fournier-Viger P,et al.High utility-itemset mining and privacy-preserving utility mining [J].Perspectives in Science, 2016,7: 74-80.   
[4]Tseng VS,Wu Chengwei,ShieBE,et al. UP-Growth:an efficient algorithm for high utility itemset mining [C]//Proc of ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.Washington DC: IEEE Computer Society,2010:253-262.   
[5]Zida S,Fournier-Viger P,Lin Chunwei,et al.EFIM:a fast and memory efficient algorithm for high-utility itemset mining [J].Knowledge& Information Systems,2017,51(2): 595-625.   
[6]Thilagu M,Nadarajan R.Efficiently mining of effective Web traversal patterns with average utility [J].Procedia Technology,2012,6(4): 444-451.   
[7]Lee D,Park S H,Moon S.Utility-based association rule mining: a marketing solution for cross-selling[J]. Expert Systems with Applications,2013,40 (7): 2715-2725.   
[8]Lin Chunwei,Fournier-Viger P,Gan Wensheng.FHN:an efficient algorithm for mining high-utility itemsets with negative unit profits [J].Knowledge

Based Systems,2016,111:283-298.

[9]Ahmed CF,Tanbeer SK,Jeong B S,et al.HUC-Prune:an efficient candidate pruning technique to mine high utility patterns [J].Applied Intelligence,2011,34 (2): 181-198.

[10] Tseng V S,Shie BE,Wu Chengwei,et al. Efficient algorithms for mining high utility itemsets from transactional databases [J].IEEE Trans on Knowledge & Data Engineering,2013,25(8): 1772-1786.   
[11] Yun U, Ryang H, Ryu K H. High utility itemset mining with techniques for reducing overestimated utilities and pruning candidates [J].Expert Systems With Applications,2014,41 (8): 3861-3878.   
[12] Liu Mengchi, Qu Junfeng. Mining high utility itemsets without candidate generation [C]// Proc of ACM International Conference on Information and Knowledge Management. New York: ACM Press, 2012: 55-64.   
[13]Fournier-VigerP,Wu Chengwei,Zida S,et al.FHM: faster high-utility itemset mining using estimated utility co-occurrence pruning [C]//Proc of International Symposium on Methodologies for Intelligent Systems: Foundations of Intelligent Systems. Switzerland: Springer International Publishing,2014: 83-92.   
[14] Krishnamoorthy S.Pruning strategies for mining high utility itemsets [J]. Expert Systems with Applications,2015,42 (5): 2371-2381.   
[15] Zida S,Fournier-Viger P,Lin Chunwei,et al.EFIM: a highlyeficient algorithm for high-utility itemset mining[C]//Proc ofMexican International ConferenceonrtiialIteligence: Advans inArtifialIntelligee Soft Computing. Switzerland: Springer International Publishing,2015: 530- 546.   
[16] Lin Chunwei, Gan Wensheng,Fournier-Viger P,et al. Efficient mining of high-utility itemsets using multiple minimum utility thresholds [J]. Knowledge-Based Systems,2016,113:100-115.   
[17] Han Jiawei,KamberM,Pei Jian．数据挖掘概念与技术 [M].范明，孟小 峰，译.3版．北京：机械工业出版社，2007:157-170.(HanJiawei, Kamber M, Pei Jian. Data mining concepts and techniques [M]. Ming Fan, Xiaofeng Meng,Trans.3rd Edi.Beijing: China Machine Pres,2007: 157- 170.)   
[18] Gan Wensheng,Lin Chunwei,Fournier-VigerP,etal.More efficien algorithms for mining high-utility itemsets with multiple minimum utility thresholds [C]//Proc of the 27th International Conference on Database and ExpertSystemsApplications.Switzerland:SpringerInternational Publishing,2016: 71-87.   
[19] Krishnamoorthy S.Efficient mining of high utility itemsets with multiple minimum utility thresholds [J].Engineering Applicationsof Artificial Intelligence,2018,69: 112-126.   
[20]茹蓓，贺新征．减少候选项集的数据流高效用项集挖掘算法[J].计算 机应用研究,2017,34(11):3379-3383.(Ru Bei,He Xinzheng.High utility itemsets mining algorithm of data stream with reducing candidate itemsets [J].Application Research of Computers,2017,34 (11): 3379-3383)

[211 Sahnn I Dac △ KGncwami △ An efrient annrnach for mining association rules from high utility itemsets [J].Expert System with Applications,2015,42(13):5754-5778.

[22] Lin Chunwei, Gan Weisheng,Fournier-Viger P,et al.Efficient algorithms for mining high-utility itemsets in uncertain databases [J].Knowledge

Based Systems,2016,96:171-187.

[23]Fournier-Viger P,Gomariz A,Soltani A,etal.2014a. SPMF:OpenSource data miningplatform [EB/OL].http://www.philippe-fournier-viger. com/spmf.