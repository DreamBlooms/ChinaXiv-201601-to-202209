# 圈图超平面配置的导模及其自由解

# 吴军

摘要：本文利用代数和组合的相关理论对超平面配置理论的自由性做出了相关研究，给出圈图所对应的图配置的生成元和导模的具体形式，并以图论的形式对圈图配置的导模及其自由解做出相关的组合解释.

关键词：超平面配置；导模；圈图；自由解中图分类号: 0151, 0157

# 一、引言

在代数几何中，奇点问题一直是重要研究对象之一，在对代数簇的孤立奇点(isolated singularity)进行局部化以后，过孤立奇点的所有切超平面就构成一个超平面配置(arrangement of hyperplanes)．一方面，人们可以通过超平面配置来研究代数簇，另一方面，由于超平面配置的组合对象几何格(geometric lattice)或与之等价的对象单拟阵(simplematroid)属于组合学家或格论学家之前就关心的内容.因此对超平面配置的研究自然就包括了几何，代数，拓扑和组合等方面[1,2].

在1970 年，K.Saito 为研究孤立奇点的Gauss-Manin 连接，引入了自由除子(free divisor)的概念[3]，几乎与此同时，超平面的自由配置(free arrangement)概念也由H.Terao 开始建立．后来，Silvotti 和Schenck[4-6]等人指出超平面配置的自由性问题等价于在射影空间中的自反层(reflexive sheaf)分裂成一维线丛(line bundle)代数和的问题，即分裂问题(splitting problem)．几乎同期，H.Terao 提出一个至今未解决的著名猜想：超平面配置的自由性是组合决定的[1.2].这一猜想已成为目前超平面配置自由性研究的中心问题，本文也是对一类由圈图这种组合对象所决定的配置的自由性展开研究

# 二、超平面配置的交格与导模

对 $l$ 维实向量空间 $V = R ^ { l }$ ，设 $\{ x _ { 1 } , x _ { 2 } , . . . , x _ { l } \}$ 为一组基，对于$\boldsymbol { V } ^ { * } = \boldsymbol { V } \backslash \left\{ \begin{array} { r l r l } \end{array} \right.$ 原点0}，再设 ${ \boldsymbol { S } } = { \boldsymbol { S } } ( { \boldsymbol { V } } ^ { * } )$ 为 $\boldsymbol { V } ^ { * }$ 上的分次对称代数，即（204号 $S = \bigoplus _ { k \geq 0 } S _ { k }$ ，其中 $S _ { k }$ 为 $k$ 次子模，且 $R = S _ { \mathrm { 0 } }$ ，对任意一个次(齐次)多项式 $\alpha \in S _ { 1 }$ ，称 $H = \ker ( \alpha )$ 为一个超平面，即 $H$ 是一个 $l - 1$ 维过坐标原点的子空间，我们此时也记 $\alpha = \alpha _ { { \scriptscriptstyle H } }$ ．一个超平面配置(hyperplanearrangement） 或简称配置(arrangement)是指由有限个超平面构成的全体

$$
A = \{ \ker ( \alpha _ { H } ) | \alpha _ { H } \in S _ { 1 } \} .
$$

对于配置 $A , A$ 中各个超平面所有可能的交子空间族构成一个按子空间反包含关系下的偏序集 $L = L ( A )$ ．在 $L$ 中，我们定义任意两个 $A$ 中的超平面 $H _ { i }$ 和 $H _ { _ j }$ 的并和交运算分别为

$$
H _ { i } \times H _ { _ { j } } = H _ { i } \cap H _ { _ { j } } , H _ { i } \wedge H _ { _ { j } } = s p a n \{ H _ { _ { i } } , H _ { _ { j } } \} \ ,
$$

并且 $V$ 和 $\bigcap _ { H \in A } H$ 分别为 $L$ 的最小元和最大元，于是 $L$ 构成一个几何格（204号(geometric lattice)，称之为配置的交格(intersection lattice).交格即是超平面配置理论中的组合对象，这一对象一方面与配置的几何，代数和复配置的拓扑有着非常紧密的关联，另一方面几何格范畴等价于单拟阵（simplematroid）范畴，是一个广泛而有趣的研究领域，Terao猜想至今难以解决也和我们对几何格的了解不充分有关，仍吸引着相关学者的不懈研究[7-10].

同时对于交换环 $S$ ，我们引入一阶导子(derivation)

$$
D _ { i } = \frac { \partial } { \partial x _ { i } } , i = 1 , 2 , . . . , l
$$

满足牛顿-莱布尼兹公式 $D _ { i } ( f g ) = g D _ { i } ( f ) + f D _ { i } ( g ) , ( \forall f , g \in S )$ ，于是得到一个 $S$ 分次 $S$ 导模(derivation module) $D = \bigoplus _ { i = 1 } ^ { l } S D _ { i }$ ，将该导模与配置 $A$ 作如下结合

$$
D ( A ) = \{ \theta \in D | \theta ( \alpha _ { { \scriptscriptstyle H } } ) \in S \alpha _ { { \scriptscriptstyle H } } , { \cal H } \in A \} ,
$$

所得到的S分次子模D(A)称为配置A的导模．若记Q(A)=II $Q ( A ) = \prod _ { H \in { \cal A } } \alpha _ { H }$ 则熟知 $\theta \in D ( A )$ 等价于 $\theta ( \mathcal { Q } ( A ) ) \in S \cdot Q ( A )$ ．若 $D ( A )$ 是一个自由(分次) $S$ 模，则称 $A$ 为自由配置．从有限反射群的根系理论中引入的反射配置及它们的某些变形，以及超可解配置（supersolvablearrangement)都为自由配置的例子．自由配置的导模和某些陈类也有着紧密联系［3-6].

一般而言，多数配置的导模不是自由模，寻找导模的自由解(freeresolution)成为研究配置导模性质的自然途径．不论Terao猜想是否正确，它都暗示我们研究导模的自由解时也需与配置的组合对象相结合，本文正是利用该思想以研究圈图配置导模的自由解.

# 三、圈图配置的导模及其自由解

设（简单）图 $G$ 的顶点集为 $\{ x _ { 1 } , x _ { 2 } , . . . , x _ { l } \}$ ，若其有向边集为$E ( G ) = \{ e _ { i , i + 1 } \mid x _ { i }$ 与 $x _ { i + 1 }$ 相连， $i = 1 , 2 , \ldots , l - 1 \} \cup \{ e _ { l , 1 } \ : | \ : x _ { l } -$ 与 $x _ { 1 }$ 相连},则称图 $G$ 为圈图．易知此时 $E ( G )$ 总共有 $l$ 条边．记这些边所对应的

一次多项式集为 $\{ \alpha _ { i } = x _ { i } - x _ { j } | e _ { i , j } \in E ( G ) \}$ ．定义 $G$ 的图配置为

$$
A ( G ) = \left\{ \ker ( \alpha _ { i } ) | i = 1 , 2 , \cdots , l \right\} ,
$$

则配置 $A ( G )$ 共含有 $l$ 个超平面且 $\mathrm { d i m } ( \bigcap _ { H \in A ( G ) } H ) = 1$ ．注意到该配置的任意 $l - 1$ 个超平面的法向量是线性无关组，且 $l$ 个超平面的法向量组为唯一的线性相关组，故其交格为 $l$ 个元素的布尔代数的上1-截取(upper 1-truncation).

记配置 $A = A ( G )$ 的导模为 $D ( G )$ 和 $Q = Q ( A ( G ) )$ ．若记

$$
\theta _ { i j } = \alpha _ { i } \alpha _ { j } [ ( D _ { i } - D _ { i + 1 } ) - ( D _ { j } - D _ { j + 1 } ) ] ,
$$

其中 $1 \leq i < j \leq l$ ，则我们有以下结论.

定理1圈图 $G$ 的导模 $D ( G )$ 的极小生成元集为$\{ \theta _ { 0 } , \theta _ { \varepsilon } \} \cup \{ \theta _ { i j } | 1 < i < j \le l \} , \quad \sharp \ \sharp \ \ \theta _ { 0 } = D _ { 1 } + D _ { 2 } + \dots + D _ { l }$ ，而$\theta _ { E } = x _ { 1 } D _ { 1 } + x _ { 2 } D _ { 2 } + \cdots + x _ { l } D _ { l }$ 为欧拉导子.

证明：设 $Q = \alpha _ { 1 } \alpha _ { 2 } \cdots \alpha _ { l }$ 和

$$
\theta = f _ { 1 } D _ { 1 } + f _ { 2 } D _ { 2 } + \cdots + f _ { l } D _ { l } \in D ( G ) ,
$$

其中 $f _ { i } \in S _ { k } , 1 \le i \le l$ ，即为 $k$ 次齐次多项式，而 $k$ 为非负整数．由于$\theta ( \boldsymbol { Q } ) \in S \boldsymbol { Q }$ ，即 $Q | \theta ( Q )$ ，而

$$
\theta ( Q ) = Q \cdot [ \frac { 1 } { \alpha _ { 1 } } ( f _ { 2 } - f _ { 1 } ) + \frac { 1 } { \alpha _ { 2 } } ( f _ { 3 } - f _ { 2 } ) + \cdots + \frac { 1 } { \alpha _ { l - 1 } } ( f _ { l - 1 } - f _ { l - 2 } ) + \frac { 1 } { \alpha _ { l } } ( f _ { 1 } - f _ { l } ) ] ,
$$

1) 当 $k = 0$ 时，有 $g = 0$ ，可令 $f _ { 1 } = f _ { 2 } = \cdots = f _ { l } = C$ ，（ $C$ 为非零常数)．显然此时 $\theta \in S \theta _ { 0 }$ ：

2) 当 $k = 1$ 时，有 $g = C \mathrm { ~ ( ~ } C$ 为非零常数)，可令 $f _ { i } = - C x _ { i }$ ，

$1 \leq i \leq l$ ．显然此时 $\theta \in S \theta _ { E }$ ：

3 当 $k = 2$ 时，有 $g = C _ { 1 } x _ { 1 } + \cdots + C _ { l } x _ { l } \in S _ { 1 } \ ( \nonumber C _ { 1 } , C _ { 2 } , \cdots C _ { l }$ 为不全为零的常数)，注意到对任意 $i ( 1 \leq i \leq l )$ ，若令 $\alpha _ { i - 1 } / ( f _ { i } - f _ { i - 1 } )$ 和 $\alpha _ { i } | ( f _ { i + 1 } - f _ { i } )$ ，可设 $f _ { j } = \sigma _ { i j } C _ { i } ^ { ' } \alpha _ { i - 1 } \alpha _ { i }$ ，其中 $1 \leq j \leq l$ ， $\sigma _ { i j }$ 为克罗尼克符号， $\boldsymbol { C } _ { j } ^ { ' }$ 为由 $g$ 的表达式所唯一确定．再由$C _ { 1 } , C _ { 2 } , \cdots C _ { l }$ 和 $i$ 的任意性，可知此时 $\theta$ 必属于由$\{ \theta _ { i j } | 1 \le i < j \le l \}$ 所生成的 $S$ 模中；且当 $k \geq 2$ 时 $\theta$ 能被$\{ \theta _ { \scriptscriptstyle 0 } , \theta _ { \scriptscriptstyle E } \} \cup \{ \theta _ { i j } \mid 1 \leq i < j \leq l \}$ 所生成，注意到由 $\theta _ { i j } , 1 \leq i < j \leq l$ ，所生成的子模商掉 $\theta _ { 0 }$ 部分后即得 $\theta _ { { i j } } , 1 < i < j \leq l$ 为商模的最小生成元集.

综上讨论，可知 $D ( G ) = S \theta _ { 0 } \oplus S \theta _ { E } \oplus ( \sum _ { 1 < i < j \leq l } S \theta _ { i j } )$ ，且显然$\{ \theta _ { \scriptscriptstyle 0 } , \theta _ { \scriptscriptstyle E } \} \cup \{ \theta _ { \scriptscriptstyle i j } \mid 1 < i < j \leq l \}$ 是最小生成元集，共 ${ \binom { l - 1 } { 2 } } + 2$ +2个元素. (证毕.)

# 四、导模的自由解

在 $D ( G )$ 的生成元集中， $\theta _ { E }$ 是对每个配置都出现的一次生成元而零次生成元 $\theta _ { 0 }$ 的出现恰好是因为有 $\mathrm { d i m } ( \bigcap _ { H \in A ( G ) } H ) = 1$ ．此时$D ( G )$ 不是自由 $S$ 模，我们开始讨论其作为 $S$ 模的组合自由解.

定义1．对于一个图 $G$ 配置 $A ( G )$ ，若有图的序列

$$
G { \xrightarrow { i _ { 1 } } } G _ { 1 } { \xrightarrow { } } G _ { 1 } { \xrightarrow { i _ { 2 } } } G _ { 2 } { \xrightarrow { i _ { 3 } } } \cdots { \xrightarrow { i _ { n } } } G _ { n } ,
$$

其中 $G _ { \boldsymbol { k } }$ 为将 $G _ { k - 1 }$ 添加一条边得来，而 $i _ { \bullet }$ 为自然包含关系，且使这些图配置所对应的导模序列

$D ( G _ { n } ) { \xrightarrow { i _ { n } ^ { * } } } \cdots { \xrightarrow { i _ { 3 } ^ { * } } } D ( G _ { 2 } ) { \xrightarrow { i _ { 2 } ^ { * } } } D ( G _ { 1 } ) { \xrightarrow { i _ { 1 } ^ { * } } } D ( G )$ 中的 $D ( G _ { n } )$ 为自由模，其中 $i _ { \bullet } ^ { \ast }$ 为由 $i _ { \bullet }$ 自然诱导出的模映射，则称上面图的序列为 $G$ 的一个自由解(free resolution)，称所有自由解中最小的 $n$ 为 $G$ 的自由解深度(depth).

为研究圈图的自由解，我们还需要引入关于图配置的一些知识，定义2．称一个图 $G$ 为弦图(chordal graph)，如果 $G$ 的圈都由三角形圈所生成.定理2[11]．图 $G$ 的配置是超可解当且仅当图 $G$ 是弦图.定理3[11]．图 $G$ 的配置是自由的当且仅当 $G$ 是超可解的

由定理2和定理3推出图配置的Terao猜想成立．同时也知，若想找到圈图 $G$ 的自由解，等价于找到包含 $G$ 的极小弦图，我们有以下结论.

定理4． $l$ 个顶点的圈图 $G$ 的自由解深度为 $l - 2$ 证明：设 $G$ 的顶点集为 $\{ x _ { 1 } , x _ { 2 } , \cdots , x _ { l } \}$ ，边集为这些点依次首尾相连而得到．将顶点 $x _ { 1 }$ 与其他不相邻的 $l - 2$ 个顶点 $x _ { 2 } , x _ { 3 } , \cdots , x _ { l - 1 }$ 依次相连，逐次所得到 $l - 2$ 个图组成的图序列

$$
G \xrightarrow { \quad i _ { 1 } \quad } G _ { 1 } \xrightarrow { \quad i _ { 2 } \quad } G _ { 2 } \xrightarrow { \quad i _ { 3 } \quad } \cdots \xrightarrow { \quad i _ { l - 2 } \quad } G _ { l - 2 } ,
$$

易验证 $G _ { l - 2 }$ 为一个弦图，且因为 $G _ { l - 2 }$ 中少添加 $l - 2$ 条边中的任一条边都不再是弦图，因而 $l - 2$ 既是最小的，即为圈图 $G$ 的自由解深度.（证毕.）

对于定理4证明中的自由解的 $l - 2$ 个图配置的导模而言，它们对应的如下导模序列的生成元和诱导的模映射都存在，

$\begin{array} { r } { D ( G _ { l - 2 } ) \xrightarrow { i _ { l - 2 } ^ { * } } \cdots \xrightarrow { i _ { 3 } ^ { * } } D ( G _ { 2 } ) \xrightarrow { i _ { 2 } ^ { * } } D ( G _ { 1 } ) \xrightarrow { i _ { 1 } ^ { * } } D ( G ) . } \end{array}$ （204号这些模及其映射可用代数谱序列理论予以列出．从组合可解释为$G _ { l - 2 }$ 的每一个三角形对应 $D ( G _ { l - 2 } )$ 一个基元，且该基元作用于其所对应的三条边中包含 $x _ { 1 }$ 点的两条边结果非零，而作用于 $G _ { l - 2 }$ 的所有其他边的结果为零，上面导模序列中的情形也与之类似，组合上向圈图逐步添加边的过程反映在代数上是在逐步排除导模中不满足这个条件的导子，为简洁这里仅给出自由模 $D ( G _ { l - 2 } ) = S \theta _ { 0 } \oplus S \theta _ { \scriptscriptstyle E } \oplus D ^ { \prime }$ ，其中自由子模 $D ^ { \prime } = \bigoplus _ { j = 2 } ^ { l - 1 } S \theta _ { 1 j }$ ．对于一般的配置，情况则复杂的多，部分如较早的如Yuzvinsky[12]及后续Yoshinaga[13]和较近的如Abe［9]等人所做的进展，

注：本文的圈图属于结构相对简单的图，其在复空间的配置所对应的组合和拓扑对象如特征多项式(等价于其补空间的庞加莱多项式)和同伦群都可以给出组合解释．类似定理4的这类研究对一般的配置也会提供启发和思路，也是目前人们寻找新的自由配置的常用途径之一.

参考文献   
[1] P. Orlik, H.Terao: Arrangements of Hyperplanes, Grundle. der Math.Wiss.,vol. 300. Springer， Berlin (1992).   
[2] D. Cohen, G. Denham,M. Falk etc.: Complex Arrangements: Algebra, Geometry, Topology, Draft of September 4, 2009.   
[3] K. Saito, Theory of logarithmic differential forms and logarithmic vector fields. J. Fac. Sci. Univ. Tokyo Sect. IA Math. 27, no. 2, 265-291,1980.   
[4] R.Silvotti, On the Poincare polynomial of a complement of hyperplanes. Math. Res. Lett. 4 (1997), no.5, 645-661.   
[5] H. Schenck, A rank two vector bundle associated to a three arrangement, and its Chern polynomial. Adv. Math. 149 (2000), no. 2, 214-229.   
[6] M.Mustata and H. Schenck, The module of logarithmic p-forms of a locally free arrangement, J. Algebra 241 (2001), 699-719.   
[7] M. Yoshinaga， Characterization of a free arrangement and conjecture of Edelman and Reiner. Invent. Math. 157(2), 449-454 (2004).   
[8] T.Abe，M. Yoshinaga，Free arrangements and coefficients of characteristic polynomials. Math. Z. 275(3), 911-919 (2013).   
[9] T.Abe: Divisionally free arrangements of hyperplanes, Invent. Math. (2016) 204:317-346.   
[10]G.M. Ziegler， Multiarrangements of hyperplanes and their freeness. Singularities (lowa City， IA,1986), Contemp. Math., vol. 90，pp.345-359. Amer. Math. Soc., Providence, USA (1989).   
[11] T. Jozefiak and B. E. Sagan, Basic Derivations for Subarrangements of Coxeter Arrangements, J. Algebra Comb., 2 (1993), 291-320.   
[12] S. Yuzvinsky， Free and locally free arrangements with a given intersection lattice, Proc Amer. Math. Soc. 118 (1993), 745-752.   
[13] M. Yoshinaga, On the freeness of 3-arrangements. Bul. London Math. Soc. 37 (2005), no. 1, 126-134.

# The derivation module and its free resolution of circuit graph arrangements

# Wu Jun

Abstract:We focus on a circuit graph arrangement and its free resolution from algebraic and combinatorics. We detected the generators of the derivation module and findout a basis for a free resoltion. At last， we offer a combinatorial expression of the free resolution.

Keywords: arrangement of hyperplanes; derivation module; circuit graph; free resolution

作者简介：吴军（1979-），男，湖北蕲春人，闽江学院数学系讲师、计算数学博士.

基金项目：2011年闽江学院科研项目，YKQ1008.

吴军，福建省福州市大学城文贤路1 号闽江学院数学系，邮编 350108，手机18250165360，信箱junwue@gmail.com