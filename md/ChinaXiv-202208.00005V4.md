# 分次预胞腔代数

苏志荣’\*，赵丽云²1,2（广东工业大学数学与统计学院 广州 510520)

摘要：胞腔代数是近年来备受关注的一种代数结构，而分次代数在表示论之中起着非常重要的作用。基于王涛对预胞腔代数的研究，给出分次预胞腔代数的定义，并且讨论了分次预胞腔代数的表示理论，最后还研究了正则半群代数的分次预胞腔性。

关键词：预胞腔代数，分次代数，正则半群

分类号：0152

# Graded Precellular Algebra

Su Zhirong\*， Zhao Liyun² 1,2 (College of Mathematics and Statistics， Guangdong University of Technology, Guangzhou 510520， China)

Abstract: Cellular algebra is an algebraic structure received considerable attention in recent years， and graded algebra plays an important role in the theory of representation. Based on Wang Tao's research on precellular algebra, the definition of graded precellular algebra is given， and the representation theory of graded precellular algebra is discussed. Finally， the graded precellularity of the regular semigroup algebra is studied.

Keywords: precellular algebra, graded algebra, regular semigroup

# 1引言

设 $R$ 是整环（无零因子交换幺环），本文中的分次 $R -$ 模指的是 $R -$ 模 $M \colon M =$ $\oplus _ { d \in Z } M _ { d }$ 。如果 $m \in M _ { d }$ ， $d \in Z$ ，则 $m$ 是 $d$ 齐次的，并且记作 $d e g m = d$ 。如果 $M$ 是分次 $R -$ 模，设 $M$ 是 $M$ 忘记分次得到的非分次 $R -$ 模。如果 $M$ 是分次 $R$ -模, $s \in Z$ ，设 $M \langle s \rangle$ 是通过 $M$ 提升了次数 $s$ 所得到的分次 $R$ 一模，也就是说， ${ M \langle s \rangle } _ { d } = M _ { d - s }$ ，其中 $d \in Z$ 。

分次 $R -$ 代数指的是一个含幺结合 $\cdot R -$ 代数 $A = \oplus _ { d \in Z } A _ { d }$ ，它是一个满足对所有的 $d , e \in Z$ ， $A _ { d } A _ { e } \subseteq A _ { d + e }$ 的分次 $R -$ 模。显然 $1 \in A _ { 0 }$ 且为A的分次A－代数。一个分次(右) $A$ -模 $M$ 指的是 $M$ 是一个 $\underline { { \boldsymbol { A } } } -$ 模且对所有的 $d , e \in Z$ ， $M _ { d } A _ { e } \subseteq M _ { d + e }$ 。分次子模、分次左 $A -$ 模等概念都可以用这个显然的方式来定义。设 $A - M o d$ 是所有有限分次A一模和保次数的同态的范畴，即就是说，对 $M , N \in A - M o d$ $H o m _ { A } ( M , N ) = \{ f \in H o m _ { A } \bigl ( \underline { { M } } , \underline { { N } } \bigr ) | f ( M _ { d } ) \subseteq N _ { d } , \forall d \in Z \}$ ， $H o m _ { A } ( M , N )$ 中是次数为0的映射。如果 $f \in H o m _ { A } ( M \langle d \rangle , N ) \cong H o m _ { A } ( M , N \langle d \rangle )$ ，则称 $f$ 是 $M$ 到 $N$ 的次数为 $d$ 的同态，并记为 $d e g f = d$ 。设对所有 $M , N \in A - M o d$ ，有

$$
H o m _ { A } ^ { Z } ( M , N ) = \oplus _ { \tiny \ d \in Z } H o m _ { \cal A } ( M \langle d \rangle , N ) \cong \oplus _ { \tiny \ d \in Z } H o m _ { \cal A } ( M , N \langle d \rangle ) ,
$$

胞腔代数的出现完美地解答了表示论中的一个最基本的问题一一确定不可约表示的参数集。Graham和Lehrer在文献[1]中首次引入了胞腔代数的概念； $X i$ 和Konig在文献[2]中给出了胞腔代数的一种全新等价定义；芮和兵在文献[3]中提出了标准基代数，推广了胞腔代数的定义；在标准基代数的基础上，王涛在文献[4]中给出了预胞腔代数的概念； $H u$ 和Mathas在文献［5]中给出了分次胞腔代数的概念，推广了胞腔代数的定义。由于分次代数在表示论之中起着非常重要的作用，因此本文将给出分次预胞腔代数的定义，并且讨论了分次预胞腔代数的表示理论。又由于正则半群是一类重要的半群，是半群代数理论的主要研究领域之一，所以最后还研究了正则半群代数的分次预胞腔性。

# 2预备知识

在这一节中，我们给出本文需要的一些关于半群的基本概念和定义。本文的$R$ 将表示一个整环，自然数集 $N$ 包括0。本节未提及的概念和定义请见参考文献 $[ 6 -$ 8]。

我们首先回顾一下关于半群的一些定义和结论。

设S是一个半群， $E ( S )$ 是S的全部幂等元所组成的集合，如果半群S没有单位元，则用 $S ^ { 1 }$ 表示半群S并上一个单位元，否则 $S ^ { 1 } = S _ { \circ } S$ 上的格林关系 $\mathcal { R }$ ， $\mathcal { L }$ ， $\mathcal { J }$ ，H和 $\mathcal { D }$ 在半群理论中起着十分重要的作用[9]，对于 $a , b \in S$ ，有：

$$
\begin{array} { r l } & { a \mathcal { R } b \Leftrightarrow a S ^ { 1 } = b S ^ { 1 } ; } \\ & { a \mathcal { L } b \Leftrightarrow S ^ { 1 } a = S ^ { 1 } b ; } \\ & { a \mathcal { J } b \Leftrightarrow S ^ { 1 } a S ^ { 1 } = S ^ { 1 } b S ^ { 1 } ; } \\ & { \mathcal { H } = \mathcal { L } \cap \mathcal { R } ; } \\ & { \mathcal { D } = \mathcal { L } \vee \mathcal { R } _ { \circ } } \end{array}
$$

当S是一个有限半群时，格林关系 $\mathcal { D } = \mathcal { J }$ 。设 $\mathcal { K }$ 是 $s$ 的格林关系之一，取 ${ \cal K } _ { a }$ 为S的K-类并且包括 $a$ ， $S / \mathcal { K }$ 为S的全部的 $\mathcal { K }$ 类所组成的集合。我们定义：

$$
a S ^ { 1 } \subseteq b S ^ { 1 } \Longrightarrow R _ { a } \leq R _ { b } ;
$$

$$
S ^ { 1 } a \subseteq S ^ { 1 } b \Longrightarrow L _ { a } \leq L _ { b } ;
$$

$$
S ^ { 1 } a S ^ { 1 } \subseteq S ^ { 1 } b S ^ { 1 } \Longrightarrow J _ { a } \leq J _ { b } \circ
$$

因此，可得集合 $s / \mathcal { R }$ ， $s / \mathcal { L }$ 和 $s / \mathcal { J }$ 上的偏序集。

设S是一个半群，如果对任意 $a \in S$ ，存在 $b \in S$ ，使得 $a b a = a$ ，则称 $s$ 为正则半群。

设S是一个不含零元0的半群，若S没有真理想，则称半群S是单的。含零元0的半群S叫做0－单半群，若满足：

1）除{0}和本身之外不再有其他的理想;  
2） $S ^ { 2 } \neq \{ 0 \}$ 。  
0－单半群S称为完全0－单半群，如果S含有一个本原幂等元。

设 $G$ 是一个群，I和 $\Lambda$ 是非空的集合， $P = ( p _ { \lambda k } )$ 是 $G ^ { 0 } : = G \cup \{ 0 \}$ 上的一个正则$\Lambda \times { \mathrm I }$ 矩阵，即 $P$ 的每一行和每一列都至少包含一个 $G ^ { 0 }$ 中的非零元素。设 $S =$ $( G \times \mathrm { I } \times \Lambda ) \cup \{ 0 \}$ ，定义S上的乘法，任意 $a , b \in G$ ， $k , l \in { \mathrm { I } } , \ \lambda , \mu \in \Lambda$ ，有：

$$
( a , k , \lambda ) ( b , l , \mu ) = \left\{ \begin{array} { c c } { { ( a p _ { \lambda l } b , k , \mu ) } } & { { p _ { \lambda l } \neq 0 ; } } \\ { { 0 } } & { { p _ { \lambda l } = 0 _ { \circ } } } \end{array} \right.
$$

并且 $( a , k , \lambda ) 0 = 0 ( a , k , \lambda ) = 0 0 = 0 \ :$ 。如上定义的S是一个完全0－单半群，我们将用 $\mathcal { M } ^ { 0 } ( G , 1 , \Lambda ; P )$ 来表示。在 $\mathcal { M } ^ { 0 } ( G , 1 , \Lambda ; P )$ 中，我们可以假设I $\cap \Lambda = \{ 0 \}$ ， $G =$

$( G , 0 , 0 )$ ， $p _ { 0 , 0 } = e$ ，其中 $e$ 是 $G$ 的单位元。此外对于 $\mathcal { M } ^ { 0 } ( G , \mathrm { I } , \Lambda ; \mathrm { P } )$ 的任意非零极大子群 $G ^ { \prime }$ ，我们有 ${ \mathcal { M } } ^ { 0 } ( G , \mathrm { I } , \Lambda ; \mathrm { P } ) \cong { \mathcal { M } } ^ { 0 } ( G ^ { \prime } , \mathrm { I } , \Lambda ; \mathrm { P } ) ,$ 。本文的 $\mathcal { M } ^ { 0 } ( G , 1 , \Lambda ; P )$ 总是满足上述假设。

设S是一个含有零元的半群且 $a \in S \setminus \{ 0 \}$ 。令 $S _ { a } = J _ { a } \cup \{ 0 \} , ~ 0 \notin J _ { a }$ ，则在 $S _ { a }$ 上定义运算。，任意 $x , y \in J _ { a }$ ，有：

$$
x \circ y = { \left\{ \begin{array} { l l } { x y } & { x y \in J _ { a } ; } \\ { 0 } & { x y \notin J _ { a } \circ } \end{array} \right. }
$$

其中 $x y$ 是 $x$ 和 $y$ 在S上的乘积。显然， $\textstyle { \bigl ( } S _ { a } , \circ { \bigr ) }$ 是一个具有零元0的半群。称$S _ { a }$ 为s的由 $a$ 决定的主因子。将此乘法 $R$ -线性扩展到整个 $R$ -模 $R [ J _ { a } ]$ ，我们称$R [ J _ { a } ]$ 关于乘法·是一个 $R$ 一代数。注意，有限正则半群S的每一个主因子都是一个完全0－单半群。

任意 $a \in S$ ，则 $I ( a ) : = \{ b \in S ^ { 1 } a S ^ { 1 } | S ^ { 1 } b S ^ { 1 } \subset S ^ { 1 } a S ^ { 1 } \}$ 是 $S ^ { 1 } a S ^ { 1 }$ 的一个理想，显然，$S ^ { 1 } a S ^ { 1 } = J _ { a } \dot { \cup } I ( a )$ 。

半群S的每一个含有幂等元 $e$ 的 $\mathcal { H }$ 一类 $H _ { e }$ 是 $s$ 的一个极大子群；反之， $s$ 的每一个极大子群都可以用含幂等元 $e$ 的 $\mathcal { H }$ -类 $H _ { e }$ 来得到。任取 $a \in S$ ，若 $e \in J _ { a }$ ，则 $H _ { e } \subseteq$ $J _ { a } \subseteq S _ { a }$ 。由于 $H _ { e }$ 是S的一个极大子群，所以 $H _ { e }$ 也是 $S _ { a }$ 的一个极大子群。

如果 $( S , \cdot )$ 是一个具有零元 $\theta$ 的半群， $R [ S ]$ 是域 $R$ 上的向量空间，并且对于任意 $r \in R$ ， $u , v \in R [ S ]$ ，有 $r ( u \cdot v ) = ( r u ) \cdot v = u \cdot ( r v )$ ，则 $R [ S ]$ 是半群代数。定义$R _ { 0 } [ S ] = R [ S ] / R [ \theta ]$ 。我们称 $R ^ { - }$ 代数 $R _ { 0 } [ S ]$ 是 $R$ 上的 $s$ 的压缩半群代数。若S没有零元，则 $R _ { 0 } [ S ] = R [ S ]$ 。设 $a \in R _ { 0 } [ S ]$ ，即 $\begin{array} { r } { a = \sum _ { s \in S \backslash \{ \theta \} } r _ { s } s . } \end{array}$ 。定义 $a$ 的支撑集为：

$$
s u p p ( a ) = \{ s \in S \backslash \{ \theta \} | r _ { s } \neq 0 \}
$$

引理 $2 . 1 ^ { [ 8 ] }$ 设S是一个半群：

1）若 $a , x \in S$ ，则 $x a \in J _ { a }$ 或 $x a \in I ( a )$ 。同理， $a x \in J _ { a }$ 或 $a x \in I ( a )$ ：   
2）取 $a , e = e ^ { 2 } \in S$ 。若 $a \mathcal { R } e$ ，则 $a = e a$ 。同理，若 $a \mathcal { L } e$ ，则 $a = a e$ 。

引理 $2 . 2 ^ { [ 8 ] }$ 任意 $\mathbf { \Psi } _ { k } , \lambda ) , \mathbf { \Psi } ( b , l , \mu ) \in \mathcal { M } ^ { 0 } ( G , \mathrm { I } , \Lambda ; P )$ ，有如下三个等价论述：

1) $( a , k , \lambda ) \mathcal { R } ( b , l , \mu ) \Leftrightarrow k = l ;$   
2) （204号 $( a , k , \lambda ) { \mathcal { L } } ( b , l , \mu ) \Leftrightarrow \lambda = \mu ;$   
3) $( a , k , \lambda ) \mathcal { H } ( b , l , \mu ) \Leftrightarrow k = l , \lambda = \mu _ { \mathrm { { c } } }$ 号

此外，完全0－单半群的任意非零元素都在同一个 $\mathcal { D }$ 一类之中，以及任意两个含于完全0－单半群的极大子群是同构的。

# 3分次预胞腔代数

根据王涛对预胞腔代数的研究[4]，我们现在给出分次预胞腔代数的定义。

定义3.1（分次预胞腔代数）设A是一个 $R$ 上有限自由Z－分次 $R$ 一代数。称A是一个具有分次预胞腔结构 $( \Lambda , M , C , d e g )$ 的分次预胞腔代数，其中 $( \Lambda , < )$ 是偏序集，任意 $\lambda \in \Lambda$ ， $M ( \lambda )$ 都是一个有限集，且

$$
\begin{array} { l } { C \colon \displaystyle \prod _ { \lambda \in \Lambda } M ( \lambda ) \times M ( \lambda ) \longrightarrow A ; ( S , T ) \longrightarrow C _ { S , T } ^ { \lambda } ; } \\ { d e g \colon \displaystyle \prod _ { \lambda \in \Lambda } M ( \lambda ) \longrightarrow Z } \end{array}
$$

是两个映射，其中 $C$ 是单射。且

(GP1) （20 $\{ C _ { S , T } ^ { \lambda } | S , T \in M ( \lambda ) , \lambda \in \Lambda \}$ 是A的一组 $R -$ 基。  
(GP2) $S , T \in M ( \lambda ) , \lambda \in \Lambda$ ，基元素 $C _ { S , T } ^ { \lambda }$ 的次数 $d e g \big ( C _ { S , T } ^ { \lambda } \big ) = d e g S + d e g T \mathop { }$ (GP3) 任意 $a \in A$ 且S $. T \in M ( \lambda )$ ， $\lambda \in \Lambda$ ，有

$$
C _ { S , T } ^ { \lambda } a \equiv R _ { a } ( T ^ { \prime } , T ) C _ { S , T ^ { \prime } } ^ { \lambda }
$$

其中系数 ${ \cal R } _ { a } ( T ^ { \prime } , T ) \in { \cal R }$ 且不依赖于s, $A ( < \lambda )$ 是由 $\left\{ C _ { U , V } ^ { \mu } \middle | \mu < \lambda , U , V \in M ( \mu ) \right\}$ 中的元素 $R$ -线性张成的 $A$ 的 $R -$ 子模。

(GP4）任意 $a \in \mathrm { A }$ 且S $. T \in M ( \lambda )$ ， $\lambda \in \Lambda$ ，有

其中系数 $L _ { a } ( S ^ { \prime } , S ) \in R$ 且不依赖于 $T$ ， $A ( < \lambda )$ 是由 $\left\{ C _ { U , V } ^ { \mu } \middle | \mu < \lambda , U , V \in M ( \mu ) \right\}$ 中的元素 $R$ -线性张成的 $A$ 的 $R -$ 子模。

分次预胞腔代数指的是一个具有分次预胞腔结构的分次代数，基 $\{ C _ { S , T } ^ { \lambda } | S , T \in$ $M ( \lambda ) , \lambda \in \Lambda \}$ 为A的一个分次预胞腔基。

定义3.2（分次预胞腔模）设A是一个具有分次预胞腔结构 $( \Lambda , M , C , d e g )$ 的分次预胞腔代数，固定 $\lambda \in \Lambda$ ，则右分次预胞腔模指的是分次右 $A -$ 模 $C ^ { \lambda } =$ $\textstyle \bigoplus _ { d \in Z } C _ { d } ^ { \lambda }$ ，其中 $C _ { d } ^ { \lambda }$ 是具有基 $\left\{ C _ { S } ^ { \lambda } \middle | S \in M ( \lambda ) , d e g S = d \right\}$ 的自由 $R -$ 模， $A$ 在 $C ^ { \lambda }$ 上的作用为 $\begin{array} { r } { C _ { S } ^ { \lambda } a = \sum _ { T ^ { \prime } \in M ( \lambda ) } R _ { a } ( T ^ { \prime } , T ) C _ { T ^ { \prime } } ^ { \lambda } } \end{array}$ ，这里的系数 $R _ { a } ( T ^ { \prime } , T )$ 就是(GP3)中出现的系数。类似地, $C ^ { \lambda }$ 也是左分次预胞腔模，通过A在 $C ^ { \lambda }$ 上的作用 $\begin{array} { r } { a C _ { S } ^ { \lambda } = \sum _ { S ^ { \prime } \in M ( \lambda ) } L _ { a } ( S ^ { \prime } , S ) C _ { S ^ { \prime } } ^ { \lambda } } \end{array}$ 号这里的系数 $L _ { a } ( S ^ { \prime } , S )$ 就是(GP4)中出现的系数。

根据定义3.2，为了更好地区分右分次A-模以及左分次A－模，我们使用符号 $C ^ { \lambda }$ 和 $C ^ { \lambda \prime }$ 来分别表示。设 $A ( \leq \lambda )$ 是由 $\{ C _ { S , T } ^ { \mu } | \mu < \lambda$ 或 $\mu = \lambda$ 且S $, T \in M ( \mu ) \big \}$ 中的元素$R$ -线性张成的 $R -$ 模，根据定义3.1知， $A ( \leq \lambda )$ 是A的双边理想且

$$
A ( \leq \lambda ) / A ( < \lambda ) \cong C ^ { \lambda ^ { \prime } } \otimes _ { R } C ^ { \lambda } \cong \bigoplus _ { T \in M ( \lambda ) } C ^ { \lambda } \langle d e g T \rangle ,
$$

其中第一个同构是作为 $A - A -$ 双模同构，第二个同构是作为分次右A－模同构。

设 $t$ 是 $N$ 上的不定数，如果 $M = \oplus _ { k \in Z } M _ { k }$ 是一个分次A-模且使得每个 $M _ { k }$ 在 $R$ 上是自由有限秩的，那么它的分次维数是一个Laurent多项式

$$
D i m _ { t } M = \sum _ { k \in Z } ( d i m _ { R } M _ { k } ) t ^ { k } \ _ { \circ }
$$

推论3.3设 $A$ 是一个具有分次预胞腔结构 $( \Lambda , M , C , d e g )$ 的分次预胞腔代数且$\lambda \in \Lambda$ ，那么

$$
D i m _ { t } C ^ { \lambda } = \sum _ { S \in M \left( \lambda \right) } t ^ { d e g S } \ _ { \circ }
$$

因此，可得

$$
D i m _ { t } A = \sum _ { \lambda \in \Lambda } \sum _ { S , T \in M ( \lambda ) } t ^ { d e g S + d e g T } = \sum _ { \lambda \in \Lambda } \bigl ( D i m _ { t } C ^ { \lambda } \bigr ) ^ { 2 } \ \mathrm { { c } }
$$

设 $\lambda \in \Lambda$ ，根据定义3.1以及[4]的定义3.2.3 知，在 $C ^ { \lambda }$ 上有一个双线性型$\phi _ { \lambda }$ ，它是由以下等式所决定

$$
C _ { S _ { 1 } , T _ { 1 } } ^ { \lambda } C _ { S _ { 2 } , T _ { 2 } } ^ { \lambda } \equiv \phi _ { \lambda } \bigl ( C _ { T _ { 1 } } ^ { \lambda } , C _ { S _ { 2 } } ^ { \lambda } \bigr ) C _ { S _ { 1 } , T _ { 2 } } ^ { \lambda } \bigl ( m o d A ( < \lambda ) \bigr ) ,
$$

其中 $S _ { 1 } , S _ { 2 } , T _ { 1 } , T _ { 2 } \in M ( \lambda )$ 。与[4]的命题3.2.4类似，根据定义，可以直接得到引理3.4。

引理3.4设 $\lambda \in \Lambda$ ， $a \in A$ ， $x , y \in C ^ { \lambda }$ ，则

1） $\phi _ { \lambda } ( x a , y ) = \phi _ { \lambda } ( x , a y ) ;$   
2） $x C _ { S , T } ^ { \lambda } = \phi _ { \lambda } \big ( x , C _ { S } ^ { \lambda } \big ) C _ { T } ^ { \lambda }$ ，其中 $S , T \in M ( \lambda )$ 。

现在，我们将环 $R$ 视为一个具有平凡分次的分次 $R$ -模，则 $R = R _ { 0 }$ 。可以发现 $C ^ { \lambda } \otimes _ { R } C ^ { \lambda }$ 是一个分次A－模，其中 $d e g ( x \otimes y ) = d e g x + d e g y { \mathrm { { c } } }$

引理3.5设 $\lambda \in \Lambda$ ，则映射

$$
f \colon C ^ { \lambda } \otimes _ { R } C ^ { \lambda } \longrightarrow R ; x \otimes y \mapsto \phi _ { \lambda } ( x , y ) ,
$$

是一个零次的齐次映射，特别地， $r a d C ^ { \lambda } = \{ x \in C ^ { \lambda } | \phi _ { \lambda } ( x , y ) = 0 , \forall y \in C ^ { \lambda } \}$ 是 $C ^ { \lambda }$ 的一个分次子模。

证明：根据引理3.4的1）可知radc^是 $C ^ { \lambda }$ 的一个子模。因此我们只需要证明双线性型定义了一个零次的齐次映射即可。任意 $x , y \in C ^ { \lambda }$ ，设 $f ( x \otimes y ) \neq 0$ ，令

$$
x = \sum _ { i } x _ { i } , y = \sum _ { j } y _ { j } ,
$$

这里的 $x _ { i }$ 以及 $y _ { i }$ 都是i齐次的。存在 $i , j$ 使 $\phi _ { \lambda } { \left( x _ { i } , y _ { j } \right) } \neq 0$ 。令 $\begin{array} { r } { x _ { i } = \sum _ { S } a _ { S } C _ { S } ^ { \lambda } } \end{array}$ 以及 $y _ { j } =$ $\sum _ { T } b _ { T } C _ { T } ^ { \lambda }$ ，其中 $a _ { S } , b _ { T } \in R$ ，而且仅当 $d e g S = i$ 时， $a _ { S } \neq 0$ 以及仅当 $d e g T = j$ 时，$b _ { T } \neq 0$ 。

选定 $e \in M ( \lambda )$ ，根据引理3.4，有

$$
\phi _ { \lambda } \bigl ( x _ { i } , y _ { j } \bigr ) C _ { e , e } ^ { \lambda } = \sum _ { S , T } a _ { S } b _ { T } \phi _ { \lambda } \bigl ( C _ { S } ^ { \lambda } , C _ { T } ^ { \lambda } \bigr ) C _ { e , e } ^ { \lambda } \equiv \sum _ { S , T } a _ { S } b _ { T } C _ { e , S } ^ { \lambda } C _ { T , e } ^ { \lambda } \bigl ( m o d A ( < \lambda ) \bigr ) ,
$$

比较两边的次数可知，只有当 $i + j = 0$ 时，才有 $\phi _ { \lambda } { \left( x _ { i } , y _ { j } \right) } \neq 0$ 。即仅当$d e g ( x \otimes y ) = 0$ 时，有 $\phi _ { \lambda } ( x , y ) \neq 0$ ，这就是我们想要证明的东西。最后，由于 $x =$ $\begin{array} { r } { \sum _ { i } x _ { i } \in r a d C ^ { \lambda } } \end{array}$ 且 $\phi _ { \lambda }$ 是齐次的，那么对于全部i，有 $x _ { i } \in r a d C ^ { \lambda }$ ，因此 $r a d C ^ { \lambda }$ 是 $C ^ { \lambda }$ 的一个分次子模。证毕。

这个引理将允许我们定义 $C ^ { \lambda }$ 的一个分次商，其中 $\lambda \in \Lambda$ 。

定义3.6设 $\lambda \in \Lambda$ ，令 $D ^ { \lambda } = C ^ { \lambda } / r a d C ^ { \lambda }$ 0

根据定义， $D ^ { \lambda }$ 是一个分次右A－模。从现在开始，设 $R = K$ 是一个域， $A =$ $\oplus _ { z \in Z } A _ { z }$ 是一个分次预胞腔 $K$ 一代数。以下结果可以根据未分次的情况进行证明。

引理3.7设 $K$ 是一个域且 $D ^ { \lambda } \neq 0$ ， $\lambda \in \Lambda$ ，那么

1）右 $A -$ 模 $D ^ { \lambda }$ 是绝对不可约的分次 $A -$ 模；  
2） $C ^ { \lambda }$ 的（分次）Jacobson根基是 $r a d C ^ { \lambda }$ ：  
3）若 $\mu \in \Lambda$ ， $M$ 是 $C ^ { \mu }$ 的分次A－子模，有 $H o m _ { A } ^ { \mathbb { Z } } \left( C ^ { \lambda } , C ^ { \mu } / M \right) \neq 0$ ，则 $\lambda \leq \mu$ 。此外，若 $\lambda = \mu$ ，则 $H o m _ { A } ^ { \mathbb { Z } } { \big ( } C ^ { \lambda } , C ^ { \lambda } / M { \big ) } = H o m _ { A } { \big ( } C ^ { \lambda } , C ^ { \lambda } / M { \big ) } \cong K$ 。

证明：任意 $x \in C ^ { \lambda } \backslash r a d C ^ { \lambda }$ 且 $x$ 是非零元，故存在 $y \in C ^ { \lambda }$ ，使 $\phi _ { \lambda } ( x , y ) \neq 0$ 。由于 $K$ 是一个域，则设 $\phi _ { \lambda } ( x , y ) = 1$ 。设 $\begin{array} { r } { y = \sum _ { S \in M \left( \lambda \right) } r _ { S } C _ { S } ^ { \lambda } } \end{array}$ ，其中 $r _ { S } \in K$ 。任意 $T \in M ( \lambda )$ ，设 $\begin{array} { r } { y _ { T } = \sum _ { S \in M \left( \lambda \right) } r _ { S } C _ { S , T } ^ { \lambda } } \end{array}$ ，则 $y _ { T } \in A$ 。

根据引理3.4可知

$$
x y _ { T } = x \sum _ { S \in M ( \lambda ) } r _ { S } C _ { S , T } ^ { \lambda } = \sum _ { S \in M ( \lambda ) } r _ { S } \phi _ { \lambda } \bigl ( x , C _ { S } ^ { \lambda } \bigr ) C _ { T } ^ { \lambda } = \phi _ { \lambda } ( x , y ) C _ { T } ^ { \lambda } = C _ { T } ^ { \lambda } ,
$$

因此， $x$ 生成 $C ^ { \lambda }$ 。这个论点适用于 $C ^ { \lambda }$ 中任何不属于根的元素，故 $D ^ { \lambda }$ 是不可约的且$r a d C ^ { \lambda }$ 是 $C ^ { \lambda }$ 的唯一极大子模，因此证明了引理3.7的2）。同理可证，对于 $K$ 的任意扩域， $D ^ { \lambda }$ 是不可约的，所以右A－模 $D ^ { \lambda }$ 是一个绝对不可约的分次A－模。

设 $\theta \colon C ^ { \lambda } \longrightarrow C ^ { \mu } / M$ 是一个A－模同态，则存在 $a _ { \theta } \in C ^ { \mu }$ ，使得 $\boldsymbol { \theta } ( \boldsymbol { x } ) = \boldsymbol { M } + \boldsymbol { a } _ { \theta }$ 。所以，任意 $T \in M ( \lambda )$ ，有 $\ddot { \theta } \big ( C _ { T } ^ { \lambda } \big ) = \theta ( x y _ { T } ) = \theta ( x ) y _ { T } = M + a _ { \theta } y _ { T }$ 。又因为当 $\lambda > \mu$ ，$x \in A ( \leq \lambda )$ 时，对于任意 $a \in A ( \leq \mu )$ 都有 $a x , x a \in A ( < \lambda )$ 以及 $C ^ { \lambda }$ 是一个A－模。因此，当 $\lambda > \mu$ 时，对于任意 $T \in M ( \lambda )$ ，都有 $a _ { \theta } y _ { T } = 0$ ，则 $\begin{array} { r } { \theta \big ( C _ { T } ^ { \lambda } \big ) = 0 } \end{array}$ 。故可得，若

$H o m _ { A } ^ { \mathbb { Z } } \big ( C ^ { \lambda } , C ^ { \mu } / M \big ) \neq 0$ ，则 $\lambda \leq \mu$ 。假设 $\lambda = \mu$ ，根据引理3.4的2)，我们可以发现

$$
\theta \big ( C _ { T } ^ { \lambda } \big ) = M + a _ { \theta } y _ { T } = M + \sum _ { S \in M ( \lambda ) } r _ { S } a _ { \theta } C _ { S , T } ^ { \lambda } = M + C _ { T } ^ { \lambda } \phi _ { \lambda } ( a _ { \theta } , y ) \circ
$$

因此， $\theta \colon C ^ { \lambda } \to C ^ { \lambda } / M$ 是一个乘以 $\phi _ { \lambda } ( a _ { \theta } , y )$ 所构成的自然投影。则引理3.7的3)得证。特别地，如果 $M$ 是 $C ^ { \lambda }$ 的分次A－子模，则任意非零态射 $\theta \colon C ^ { \lambda } \to C ^ { \lambda } / M$ 都是保持次数的。证毕。

定理3.8假设 $\Lambda _ { 0 } = \big \{ \lambda \in \Lambda \big | D ^ { \lambda } \neq 0 \big \}$ ， $K$ 是一个域, $A$ 是一个分次预胞腔代数，则

1）如果 $\lambda \in \Lambda _ { 0 }$ ，那么右 $A -$ 模 $D ^ { \lambda }$ 是一个绝对不可约的分次A－模；

2）假设λ, $\mu \in \Lambda _ { 0 }$ 。存在 $k \in Z$ 使得 $D ^ { \lambda } \cong D ^ { \mu } \langle k \rangle$ 当且仅当 $\lambda = \mu , k = 0$

3） $\{ D ^ { \mu } \langle k \rangle | \mu \in \Lambda _ { 0 } , k \in Z \}$ 是两两之间互不同构的分次单A一模的完全集。

证明：根据引理3.7，直接可证1）和2）。对于3），可以发现通过提升次数，每一个分次单A－模都同构于A的一个极大分次右理想的商，并且A的分次预胞腔基诱导了 $A$ 的分次滤链，其所有商模都同构于分次预胞腔模次数提升后的直和，因此只需证明每一个 $C ^ { \lambda }$ 的合成因子都同构于 $D ^ { \mu } \langle k \rangle$ 即可，其中 $\mu \in \Lambda _ { 0 } , k \in Z$ 。证明部分完全按照未分次的情形进行论证即可，具体可以参看文献[4」的定理3.3.4。证毕。

推论3.9假设 $K$ 是一个域， $A$ 是 $K$ 上的分次预胞腔代数。那么 $\left\{ \underline { { { D } } } ^ { \mu } | \mu \in \Lambda _ { 0 } \right\}$ 是两两之间互不同构的未分次单 $A -$ 模的全集。

证明：根据引理3.5可知，对于每个 $\lambda \in \Lambda$ ，子模 $r a d C ^ { \lambda }$ 与分次无关。因此，未分次模 ${ \underline { { D } } } ^ { \mu }$ 恰好是使用忘记分次而得到的A的预胞腔基所构造的模。所以，通过定理3.7在忘记分次的情况下，每个（未分次）单模都同构于 ${ \underline { { D } } } ^ { \mu }$ 。证毕。

在给出分次分解矩阵的定义之前，我们首先回顾一下， $t$ 是N上的不定数。假设 $M$ 是一个分次A－模， $D$ 是一个分次单模。存在 $k \in Z$ ，使 $D \langle k \rangle$ 为 $M$ 的分次合成因子，设 $\left[ M \colon D \langle k \rangle \right]$ 为单模 $D \langle k \rangle$ 的重数。类似地，当 $\underline { { D } }$ 为 $\underline { { M } }$ 的合成因子，设 $\left[ \underline { { M } } : \underline { { D } } \right]$ 为$\underline { { \boldsymbol { D } } }$ 的重数。

定义3.10（分次分解矩阵）设A是一个域上的分次预胞腔代数，则 $A$ 的分次分解矩阵为 $\mathsf { \Pi } ^ { } [ D _ { A } ( t ) = \left( d _ { \lambda \mu } ( t ) \right)$ ，其中

$$
\dot { d _ { \lambda \mu } } ( t ) = \sum _ { k \in \mathbb { Z } } \bigl [ C ^ { \lambda } { : } D ^ { \mu } \langle k \rangle \bigr ] t ^ { k } , \lambda \in \Lambda , \mu \in \Lambda _ { 0 } \circ
$$

根据引理3.7，我们可以得到以下的结果。

引理3.11设 $\lambda \in \Lambda , \mu \in \Lambda _ { 0 }$ ，则

1) （204号 $d _ { \lambda \mu } ( 1 ) = \bigl [ \underline { { { C } } } ^ { \lambda } { : } \underline { { { D } } } ^ { \mu } \bigr ] ;$   
2) （204号 $d _ { \mu \mu } ( t ) = 1 , d _ { \lambda \mu } ( t ) \neq 0$ 当且仅当 $\lambda \leq \mu$ 。

假如分次A－模 $M$ 满足条件：存在一条滤链

$$
0 = M _ { 0 } \subset M _ { 1 } \subset M _ { 2 } \subset \cdots \subset M _ { k } = M
$$

$M _ { i } ( 1 \leq i \leq k )$ 是 $M$ 的分次子模且存在 $\lambda \in \Lambda$ ， $k \in \mathbb { Z }$ ，使得 $M _ { i } / M _ { i - 1 } \cong C ^ { \lambda } \langle k \rangle$ 。则称$M$ 具有一条分次预胞腔模滤链。通过文献[10]的定理3.2以及定理3.3，我们可以知道每一个投射 $A -$ 模都是可分次的。

定义3.12设 $R$ 是一个具有单位元的交换环，令S是一个半群，则半群代数$R [ S ]$ 是一个具有分次预胞腔结构 $( \Lambda , M , C , d e g )$ 的 $\mathcal { J }$ 型分次预胞腔代数，如果它满

足定义3.1，且满足条件：每一个 $\lambda \in \Lambda$ ，任意s $\mathfrak { d } , T \in M ( \lambda )$ ，存在S的一个 $\mathcal { J } -$ 类J，使得 $s u p p ( C _ { S , T } ^ { \lambda } ) \subseteq J$ 。注意 $J$ 可能依赖于所取的λ。

定义3.13半群代数 $R [ S ]$ 是一个具有分次预胞腔结构 $( \Lambda , M , C , d e g )$ 的 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数，如果它既满足定义3.12，又满足条件：每一个 $\lambda \in I$ 以及 $S , T \in$ $M ( \lambda )$ ，存在S的一个 $\mathcal { H }$ 一类 $H$ ，使得 $s u p p ( C _ { S , T } ^ { \lambda } ) \subseteq H$ 。

# 4正则半群代数的分次预胞腔性

定理4.1设 $R$ 是一个整环， $\mathfrak { S }$ 是一个半群，若 $R [ \mathfrak { S } ]$ 是一个具有分次预胞腔结构 $( \Lambda , M , C , d e g )$ 的 $\mathcal { J }$ 型分次预胞腔代数，则任意 $a \in { \mathfrak { S } }$ ， $R$ 一代数 $R [ J _ { a } ]$ 都是一个具有分次预胞腔结构 $( \Lambda _ { a } , M _ { a } , C _ { a } , d e g _ { a } )$ 的分次预胞腔代数，其中

$\Lambda _ { a } = \left\{ \lambda \in \varLambda \right|$ 存在 $S , T \in M ( \lambda ) , s u p p \bigl ( C _ { S , T } ^ { \lambda } \bigr ) \subseteq J _ { a } , \bigr \}$ $\bullet$ $M _ { a } = \cup _ { \lambda \in \varLambda _ { a } } M ( \lambda )$ ；$\bullet$ （20 $C _ { a } = \cup _ { \lambda \in { \cal { A } } _ { a } } \{ C _ { S , T } ^ { \lambda } \big | S , T \in { \cal { M } } ( \lambda ) \} ;$ $\bullet$ $d e g _ { a } = d e g$ 。

证明：根据我们对 $( \varLambda _ { a } , M _ { a } , C _ { a } , d e g _ { a } )$ 的定义，我们只需要证明如下四个问题：1） $\left\{ C _ { S , T } ^ { \alpha } \middle | \alpha \in \varLambda _ { a } , S , T \in M ( \alpha ) \right\}$ 是 $R [ J _ { a } ]$ 的一组 $R$ -基。

根据题目假设可知， $\mathsf { U } _ { \alpha \in \Lambda } \{ C _ { S , T } ^ { \alpha } \bigl | S , T \in M ( \lambda ) \bigr \}$ 构成了 $R [ \mathfrak { S } ]$ 的一组 $R$ -基。任意$x \in J _ { a }$ ，有 $\begin{array} { r } { x = \sum _ { i \in I } \sum _ { S , T \in N ( i ) } r _ { S , T } ^ { i } C _ { S , T } ^ { i } } \end{array}$ ，其中 $r _ { S , T } ^ { i } \in R$ ， $I \subseteq \Lambda$ 和 $N ( i ) \subseteq M ( i )$ 。根据假设， $R [ \mathfrak { S } ]$ 是一个 $\mathcal { J }$ 型分次预胞腔代数，因此 $\mathsf { U } _ { S , T \in M ( i ) } s u p p \bigl ( C _ { S , T } ^ { i } \bigr )$ 含于的某一个 $\mathcal { J }$ 类之中。则 $\begin{array} { r } { \sum _ { i \in I \cap ( \Lambda \backslash \Lambda _ { a } ) } \sum _ { S , T \in N ( i ) } r _ { S , T } ^ { i } C _ { S , T } ^ { i } = 0 } \end{array}$ ，因此 $\begin{array} { r } { x = \sum _ { i \in I \cap \Lambda _ { a } } \sum _ { S , T \in N ( i ) } r _ { S , T } ^ { i } C _ { S , T } ^ { i } \in } \end{array}$ （204号（204号 $R [ J _ { a } ]$ 。由此， $R [ J _ { a } ]$ 可以由 $\left\{ C _ { S , T } ^ { \alpha } \middle | \alpha \in \varLambda _ { a } , S , T \in M ( \alpha ) \right\}$ 中的元素 $R$ -线性表出，即问题（1）得证。

2) 如果 $\alpha \in { \cal { A } } _ { a }$ ， $S , T \in M ( \alpha )$ 和 $x \in J _ { a }$ ，那么

$$
\begin{array} { r } { C _ { S , T } ^ { \alpha } \circ x \equiv \sum _ { T ^ { \prime } \in M ( \alpha ) } R _ { x } ( T ^ { \prime } , T ) C _ { S , T ^ { \prime } } ^ { \alpha } \ \big ( m o d R [ J _ { a } ] ( < \lambda ) \big ) , } \end{array}
$$

其中系数 $R _ { x } ( T ^ { \prime } , T ) \in R$ 不依赖于S。

根据 $\mathcal { J }$ 型分次预胞腔代数的定义可知， $\begin{array} { r } { C _ { S , T } ^ { \alpha } x = \sum _ { T ^ { \prime } \in M \left( \alpha \right) } R _ { x } ( T ^ { \prime } , T ) C _ { S , T ^ { \prime } } ^ { \alpha } + x ^ { \prime \prime } } \end{array}$ ，其中 $x ^ { \prime \prime } \in R [ \mathfrak { S } ] ( < \alpha )$ ，系数 $R _ { x } ( T ^ { \prime } , T ) \in R$ 不依赖于 $s$ 。取 $x ^ { \prime \prime } =$ $\begin{array} { r l } { \sum _ { w \in W } \sum _ { P , Q \in M ( w ) } R _ { x ^ { \prime \prime } } ( P , Q ) C _ { P , Q } ^ { w } } \end{array}$ ，其中 $R _ { x ^ { \prime \prime } } ( P , Q ) \in R$ ， $W = \{ w \in \Lambda | w < \alpha \}$ 。由于（20 $R [ \mathfrak { S } ]$ 是一个 $J$ 型分次预胞腔代数，设 $\begin{array} { r } { x _ { 1 } ^ { \prime \prime } = \sum _ { w \in W \cap \Lambda _ { a } } \sum _ { P , Q \in M ( w ) } R _ { x ^ { \prime \prime } } ( P , Q ) C _ { P , Q } ^ { w } \in } \end{array}$ （204号 $R [ J _ { a } ]$ ， $\begin{array} { r } { x _ { 2 } ^ { \prime \prime } = \sum _ { w \in W \cap ( \Lambda \backslash \Lambda _ { a } ) } \sum _ { P , Q \in M ( w ) } R _ { x ^ { \prime \prime } } ( P , Q ) C _ { P , Q } ^ { w } \notin R [ J _ { a } ] } \end{array}$ ，则 $x ^ { \prime \prime } = x _ { 1 } ^ { \prime \prime } + x _ { 2 } ^ { \prime \prime }$ 。因此

$$
C _ { S , T } ^ { \alpha } \circ x = \sum _ { T ^ { \prime } \in M ( \alpha ) } R _ { x } ( T ^ { \prime } , T ) C _ { S , T ^ { \prime } } ^ { \alpha } + \sum _ { w \in W \cap \Lambda _ { a } } \sum _ { P , Q \in M ( w ) } R _ { x ^ { \prime \prime } } ( P , Q ) C _ { P , Q } ^ { w } \in R [ J _ { a } ] \circ
$$

即问题（2）得证。

3）如果 $\alpha \in { \cal { A } } _ { a }$ ， $S , T \in M ( \alpha )$ 和 $x \in J _ { a }$ ，那么

$$
\begin{array} { r } { x \circ C _ { S , T } ^ { \alpha } \equiv \sum _ { S ^ { \prime } \in M ( \alpha ) } L _ { x } ( S ^ { \prime } , S ) C _ { S ^ { \prime } , T } ^ { \alpha } \ \big ( m o d R [ J _ { a } ] ( < \lambda ) \big ) , } \end{array}
$$

其中系数 $L _ { x } ( S ^ { \prime } , S ) \in R$ 不依赖于 $T$ 。

根据J型分次预胞腔代数的定义可知， $\begin{array} { r } { x C _ { S , T } ^ { \alpha } = \sum _ { S ^ { \prime } \in M \left( \alpha \right) } L _ { x } ( S ^ { \prime } , S ) C _ { S ^ { \prime } , T } ^ { \alpha } + x ^ { \prime } } \end{array}$ ，其中 $x ^ { \prime } \in R [ \mathfrak { S } ] ( < \alpha )$ ，系数 $L _ { x } ( S ^ { \prime } , S ) \in R$ 不依赖于 $T$ 。取 $x ^ { \prime } =$ $\begin{array} { r l } { \sum _ { i \in I } \sum _ { U , V \in M ( i ) } L _ { x ^ { \prime } } ( U , V ) C _ { U , V } ^ { i } } & { { } } \end{array}$ ，其中 $L _ { x ^ { \prime } } ( U , V ) \in R$ ， $I = \{ i \in \Lambda | i < \alpha \}$ 。由于 $R [ \mathfrak { S } ]$ 是一个 $J$ 型分次预胞腔代数，设 $\begin{array} { r } { x _ { 1 } ^ { \prime } = \sum _ { i \in I \cap \Lambda _ { a } } \sum _ { U , V \in M ( i ) } L _ { x ^ { \prime } } ( U , V ) C _ { S , T } ^ { i } \in R [ J _ { a } ] } \end{array}$ ， $x _ { 2 } ^ { \prime } =$ $\begin{array} { r l } { \mathrm { ~ } } & { { } \sum _ { i \in I \cap ( \Lambda \backslash \Lambda _ { a } ) } \sum _ { U , V \in M ( i ) } L _ { x ^ { \prime } } ( U , V ) C _ { S , T } ^ { i } \notin R [ J _ { a } ] } \end{array}$ ，则 $x ^ { \prime } = x _ { 1 } ^ { \prime } + x _ { 2 } ^ { \prime }$ 。因此

$$
\chi \circ C _ { S , T } ^ { \alpha } = \sum _ { S ^ { \prime } \in M ( \alpha ) } L _ { x } ( S ^ { \prime } , S ) C _ { S ^ { \prime } , T } ^ { \alpha } + \sum _ { i \in I \cap \Lambda _ { a } } \sum _ { U , V \in M ( i ) } L _ { x ^ { \prime } } ( \overline { { U } } , V ) C _ { S , T } ^ { i } \in R [ J _ { a } ] \circ
$$

即问题（3）得证。

4）如此构造的 $R$ 一代数 $R [ J _ { a } ]$ 是一个分次代数。

由于 $R [ \mathfrak { S } ]$ 是一个分次 $R$ -代数且 $d e g _ { a } = d e g$ ，则设 $R [ S ] = \oplus _ { d \in Z } A _ { d }$ ，其中 $A _ { d }$ 是由 $\left\{ C _ { S , T } ^ { \lambda } | \lambda \in \Lambda , S , T \in M ( \lambda ) , d e g { \left( C _ { S , T } ^ { \lambda } \right) } = d \right\}$ 所生成的 $R -$ 模。因此，取 $A _ { d } ^ { \prime }$ 是由$\{ C _ { S , T } ^ { \lambda } | \lambda \in \Lambda _ { a } , S , T \in M ( \lambda ) , d e g _ { a } { \left( C _ { S , T } ^ { \lambda } \right) } = d e g { \left( C _ { S , T } ^ { \lambda } \right) } = d \}$ 所生成的 $R$ -模。显然，$R [ J _ { a } ] = \oplus _ { d \in Z } A _ { d } ^ { \prime }$ 。由于任意 $d , e \in Z$ 都有 $A _ { d } A _ { e } \subseteq A _ { d + e }$ ，则可根据二元运算·的定义，可得 $A _ { d } ^ { \prime } \circ A _ { e } ^ { \prime } \subseteq A _ { d + e }$ ，又因为 $\textstyle { \bigl ( } \mathfrak { S } _ { a } , \circ \Bigr )$ 是一个半群，则可得 $A _ { d } ^ { \prime } \circ A _ { e } ^ { \prime } \subseteq A _ { d + e } ^ { \prime }$ 。故问题（4）得证。

综上所述，对于每一个 $a \in { \mathfrak { S } }$ ， $R$ 一代数 $R [ J _ { a } ]$ 是一个具有分次预胞腔结构$( \varLambda _ { a } , M _ { a } , C _ { a } , d e g _ { a } )$ 的分次预胞腔代数。

证毕。

定理4.2设 $R$ 是一个整环，完全 $0 -$ 单半群 $\mathfrak { S } = \mathcal { M } ^ { 0 } ( G , \Lambda , \Lambda ; P )$ ，其中 $p _ { 0 , 0 } =$ $e$ ，映射 $f \colon \Lambda \to \mathrm { Z }$ 。若 $R _ { 0 } [ \mathfrak { S } ]$ 是一个 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数，则 $R [ G ]$ 也是一个分次预胞腔代数，其中 $G$ 是 $\mathfrak { S }$ 关于单位元 $e$ 的极大子群。相反，若 $R [ G ]$ 是一个分次预胞腔代数，且完全0－单半群 $\mathfrak { S } = \mathcal { M } ^ { 0 } ( G , \Lambda , \Lambda ; P )$ 中的正则矩阵 $P$ 的元素 $p _ { i j } \in G ^ { 0 }$ 的次数为 $f ( i ) + f ( j )$ ，则 $R -$ 代数 $R _ { 0 } [ \mathfrak { S } ]$ 是一个 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数。

证明：假设 $R _ { 0 } [ \mathfrak { S } ]$ 是一个具有分次预胞腔结构 $( I , M , C , d e g )$ 的 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数。首先定义

$\bullet$ $K = \left\{ \lambda \in I \right|$ 存在 $S , T \in M ( \lambda ) , s u p p \bigl ( C _ { S , T } ^ { \lambda } \bigr ) \subseteq G \}$ ，偏序集 $K$ 可以由 $( I , \leq )$ 推导而出;$\bullet$ $N ( \lambda ) = \{ S \in M ( \lambda ) | \lambda \in K ,$ 存在 $T \in M ( \lambda ) , s u p p \big ( C _ { S , T } ^ { \lambda } \big ) \subseteq G \}$   
$\bullet$ 当 $\lambda \in K$ ， $S , T \in N ( \lambda )$ 时，取 $D _ { S , T } ^ { \lambda } = C _ { S , T } ^ { \lambda }$ ；  
$\bullet$ （204号 $d e g _ { g } = d e g$ 。

为了证明 $R [ G ]$ 是一个具有分次预胞腔结构 $( K , N , D , d e g _ { g } )$ 的分次预胞腔代数：我们只需要证明如下四个问题：

1） $D : = \{ D _ { S , T } ^ { \lambda } | \lambda \in K , S , T \in N ( \lambda ) \}$ 是 $R [ G ]$ 的一组 $R -$ 基。

先证 $D \subseteq R [ G ]$ 。设 $S \in N ( \lambda )$ ，则存在 $T \in M ( \lambda )$ ，使得 $C _ { S , T } ^ { \lambda } \in R [ G ]$ 。由于 $e$ 是 $R [ G ]$ 的左单位元，则我们有 $e C _ { S , T } ^ { \lambda } = C _ { S , T } ^ { \lambda }$ 。任取 ${ \cal T } ^ { \prime } \in { \cal M } ( \lambda )$ ，根据定义3.1的(GP4)可知，$L _ { e } ( S ^ { \prime } , S ) \in R$ 是一个与 $T$ 无关的常数，因此

$$
e C _ { S , T ^ { \prime } } ^ { \lambda } = C _ { S , T ^ { \prime } } ^ { \lambda } + r ^ { \prime } ,
$$

其中 $\begin{array} { r } { r ^ { \prime } = \sum _ { i \in I \atop i < \lambda } \sum _ { U , V \in M ( i ) } L _ { r ^ { \prime } } ( U , V ) C _ { U , V } ^ { i } , ~ L _ { r ^ { \prime } } ( U , V ) \in R } \end{array}$ 。由于 $s u p p \big ( e C _ { S , T ^ { \prime } } ^ { \lambda } \big ) \subseteq R _ { e }$ ，且等式(1)右边的每一个基元素的支撑都含于某个 $\mathcal { H }$ -类之中，因此等式(1)右边的任意非0系数的基元素都含于 $R [ R _ { e } ]$ ，则 $C _ { S , T ^ { \prime } } ^ { \lambda } \in R [ R _ { e } ]$ 。同理，设 $T \in N ( \lambda )$ ，则存在（204号 $S \in M ( \lambda )$ ，使得 $C _ { S , T } ^ { \lambda } \in R [ G ]$ 。由于 $e$ 是 $R [ G ]$ 的右单位元，则我们有 $C _ { S , T } ^ { \lambda } e = C _ { S , T } ^ { \lambda }$ 。任取 $S ^ { \prime } \in M ( \lambda )$ ，根据定义3.1的(GP3)可知， ${ \cal R } _ { e } ( T ^ { \prime } , T ) \in { \cal R }$ 是一个与S无关的常数，因此

$$
C _ { S ^ { \prime } , T } ^ { \lambda } e = C _ { S ^ { \prime } , T } ^ { \lambda } + r ^ { \prime \prime } ,
$$

其中 $\begin{array} { r } { r ^ { \prime \prime } = \sum _ { i \in I } \sum _ { P , Q \in M ( i ) } R _ { r ^ { \prime \prime } } ( P , Q ) C _ { P , Q } ^ { i } } \end{array}$ ， $R _ { r ^ { \prime \prime } } ( P , Q ) \in R$ 。由于 $s u p p \big ( C _ { S ^ { \prime } , T } ^ { \lambda } e \big ) \subseteq L _ { e }$ 且等式(2)右边的每一个基元素的支撑都含于某个 $\mathcal { H }$ -类之中，因此等式(2)右边的任意非0系数的基元素都含于 $R [ L _ { e } ]$ ，则 $C _ { S ^ { \prime } , T } ^ { \lambda } \in R [ L _ { e } ]$ 。任取 $S , T \in N ( \lambda )$ ，有

$$
C _ { S , T } ^ { \lambda } \in R [ R _ { e } ] \cap R [ L _ { e } ] = R [ G ] \ : \mathrm { , }
$$

再证 $R [ G ]$ 可由 $D$ 中的元素 $R$ -线性生成。设 $a \in R [ G ]$ ，则 $a = a _ { 1 } + a _ { 2 }$ ，其中 $a _ { 1 }$ 是由 $D$ 中的元素 $R -$ 线性生成， $a _ { 2 }$ 是由 $D ^ { \prime } : = \bigl \{ C _ { S , T } ^ { \lambda } \big | \lambda \in I ; S , T \in M ( \lambda ) \bigr \} \backslash D$ 中的元素$R$ -线性生成。当 $C _ { S , T } ^ { \lambda } \in D ^ { \prime }$ ，有 $s u p p \big ( C _ { S , T } ^ { \lambda } \big ) \subseteq \mathfrak { S } \backslash \mathrm { G } .$ ，则 $a _ { 2 } \in R [ \mathfrak { S } \backslash G ]$ ，又因为 $a _ { 2 } =$ $a - a _ { 1 } \in R [ G ]$ ，因此我们可得 $a _ { 2 } = 0$ 。所以 $R [ G ]$ 可由 $D$ 中的元素 $R -$ 线性生成。

综上，问题(1)得证。

2）如果 $g \in G$ ， $\lambda \in K$ ， $D _ { S , T } ^ { \lambda } \in D ( \lambda ) : = \{ D _ { S , T } ^ { \lambda } | S , T \in N ( \lambda ) \}$ ，那么

其中 $\begin{array} { r } { g ^ { \prime } = \sum _ { \stackrel { k \in K } { k < \lambda } } \sum _ { U , V \in N ( k ) } L _ { g ^ { \prime } } ( U , V ) C _ { U , V } ^ { k } } \end{array}$ ，系数 $L _ { g } ( S ^ { \prime } , S ) \in R$ 且不依赖于 $T$ 。

由于 $R _ { 0 } [ \mathfrak { S } ]$ 是一个 $\mathcal { J }$ 型分次预胞腔代数，因此有

$$
g D _ { S , T } ^ { \lambda } = g C _ { S , T } ^ { \lambda } = \sum _ { S ^ { \prime } \in N ( \lambda ) } L _ { g } ( S ^ { \prime } , S ) C _ { S ^ { \prime } , T } ^ { \lambda } + \sum _ { S ^ { \prime } \in M ( \lambda ) \backslash N ( \lambda ) } L _ { g } ( S ^ { \prime } , S ) C _ { S ^ { \prime } , T } ^ { \lambda } + g _ { 0 } ,
$$

其中 $\begin{array} { r } { g _ { 0 } = \sum _ { k \in I } \sum _ { U , V \in M ( k ) } L _ { g _ { 0 } } ( U , V ) C _ { U , V } ^ { k } } \end{array}$ ，系数 $L _ { g } ( S ^ { \prime } , S )$ 不依赖于 $T$ 。注意，由于（204号 $s u p p \bigl ( C _ { S , T } ^ { \lambda } \bigr ) \subseteq G$ 和 $s u p p \big ( g C _ { S , T } ^ { \lambda } \big ) \subseteq G$ ，可得 $\begin{array} { r } { \sum _ { S ^ { \prime } \in M ( \lambda ) \backslash N ( \lambda ) } L _ { g } ( S ^ { \prime } , S ) C _ { S ^ { \prime } , T } ^ { \lambda } + g _ { 0 } \subseteq G } \end{array}$ 又因为 $g _ { 0 }$ 的线性表达式中各个基元素的上索引值都严格小于 $\lambda$ ，则（20 $\begin{array} { r } { \sum _ { S ^ { \prime } \in M ( \lambda ) \backslash N ( \lambda ) } L _ { g } ( S ^ { \prime } , S ) C _ { S ^ { \prime } , T } ^ { \lambda } = 0 } \end{array}$ ， $g _ { 0 } \in R [ G ]$ 。根据问题(1)可知， $g _ { 0 }$ 可以由 $D$ 中的元素 $R$ -线性表示，并且 $g _ { 0 }$ 的线性表达式中各个基元素的上索引值都严格小于λ,问题(2)得证。

3）如果 $g \in G$ ， $\lambda \in K$ ， $D _ { S , T } ^ { \lambda } \in D ( \lambda ) : = \{ D _ { S , T } ^ { \lambda } | S , T \in N ( \lambda ) \}$ ，那么

$$
D _ { S , T } ^ { \lambda } g = \sum _ { T ^ { \prime } \in N ( \lambda ) } R _ { g } ( T ^ { \prime } , T ) D _ { S , T ^ { \prime } } ^ { \lambda } + g ^ { \prime \prime } ,
$$

其中 $\begin{array} { r } { g ^ { \prime \prime } = \sum _ { k \in K } \sum _ { U , V \in N ( k ) } R _ { g ^ { \prime \prime } } ( U , V ) C _ { U , V } ^ { k } } \end{array}$ ，系数 $R _ { g } ( T ^ { \prime } , T ) \in R$ 且不依赖于 $s$ 。k<λ

同理，由于 $R _ { 0 } [ \mathfrak { S } ]$ 是一个J型分次预胞腔代数，因此有

$$
D _ { S , T } ^ { \lambda } g = C _ { S , T } ^ { \lambda } g = \sum _ { T ^ { \prime } \in N ( \lambda ) } R _ { g } ( T ^ { \prime } , T ) C _ { S , T ^ { \prime } } ^ { \lambda } + \sum _ { T ^ { \prime } \in M ( \lambda ) \setminus N ( \lambda ) } R _ { g } ( T ^ { \prime } , T ) C _ { S , T ^ { \prime } } ^ { \lambda } + g _ { 1 } ,
$$

其中 $\begin{array} { r } { g _ { 1 } = \sum _ { \stackrel { k \in I } { k < \lambda } } \sum _ { U , V \in M ( k ) } R _ { g _ { 1 } } ( U , V ) C _ { U , V } ^ { k } } \end{array}$ ，系数 $R _ { g } ( T ^ { \prime } , T )$ 不依赖于 $s$ 。注意，由于$s u p p \bigl ( C _ { S , T } ^ { \lambda } \bigr ) \subseteq G$ 和 $s u p p \bigl ( C _ { S , T } ^ { \lambda } g \bigr ) \subseteq G$ ，可得 $\begin{array} { r } { \sum _ { T ^ { \prime } \in M ( \lambda ) \backslash N ( \lambda ) } R _ { g } ( T ^ { \prime } , T ) C _ { S , T ^ { \prime } } ^ { \lambda } + g _ { 1 } \subseteq G } \end{array}$ 又因为 $g _ { 1 }$ 的线性表达式中各个基元素的上索引值都严格小于 $\lambda$ ，则$\begin{array} { r } { \sum _ { T ^ { \prime } \in M ( \lambda ) \backslash N ( \lambda ) } R _ { g } ( T ^ { \prime } , T ) C _ { S , T ^ { \prime } } ^ { \lambda } = 0 } \end{array}$ ， $g _ { 1 } \in R [ G ]$ 。根据问题(1)可知， $g _ { 0 }$ 可以由 $D$ 中的元素 $R$ －线性表示，并且 $g _ { 1 }$ 的线性表达式中各个基元素的上索引值都严格小于λ,问题(3)得证。

4）如此构造的 $R$ 一代数 $R [ G ]$ 是一个分次代数。

由于 $R [ \mathfrak { S } ]$ 是一个分次 $R$ -代数且 $d e g _ { g } = d e g$ ，则设 $R [ \mathfrak { S } ] = \oplus _ { d \in Z } A _ { d }$ ，其中 $A _ { d }$ 是由 $\left\{ C _ { S , T } ^ { \lambda } | \lambda \in \Lambda , S , T \in M ( \lambda ) , d e g { \left( C _ { S , T } ^ { \lambda } \right) } = d \right\}$ 所生成的 $R -$ 模。因此，取 $A _ { d } ^ { \prime }$ 是由$\left\{ C _ { S , T } ^ { \lambda } | \lambda \in K , S , T \in N ( \lambda ) , d e g _ { g } { \left( D _ { S , T } ^ { \lambda } \right) } = d e g { \left( C _ { S , T } ^ { \lambda } \right) } = d \right\}$ 所生成的R－模。显然，$R [ G ] = \oplus _ { d \in Z } A _ { d } ^ { \prime }$ 。由于任意 $d , e \in Z$ 都有 $A _ { d } A _ { e } \subseteq A _ { d + e }$ ，可得 $A _ { d } ^ { \prime } A _ { e } ^ { \prime } \subseteq A _ { d + e }$ ，又因为$G$ 是 $\mathfrak { S }$ 关于单位元 $e$ 的极大子群，则可得 $A _ { d } ^ { \prime } A _ { e } ^ { \prime } \subseteq A _ { d + e } ^ { \prime }$ 。故问题(4)得证。

综上所述， $R$ 一代数 $R [ G ]$ 是一个具有分次预胞腔结构 $( K , N , D , d e g _ { g } )$ 的分次预胞腔代数，其中 $G$ 是 $\mathfrak { S }$ 关于单位元 $\mathbf { \Psi } _ { \cdot } e$ 的极大子群。

相反，假设 $G$ 的群代数 $R [ G ]$ 是一个具有分次预胞腔结构 $( K , M , C , d e g )$ 的分次预胞腔代数， $\mathfrak { S } = \mathcal { M } ^ { 0 } ( G , \Lambda , \Lambda ; P )$ 。对于 $\lambda \in K$ ，定义 $N ( \lambda ) = \Lambda \times M ( \lambda )$ 以及$( x , S ) , ( y , T ) \in N ( \lambda )$ ，有 $D _ { ( x , S ) , ( y , T ) } ^ { \lambda } = \left( C _ { S , T } ^ { \lambda } , x , y \right)$ ， $d e g _ { \mathfrak { S } } \big ( D _ { ( x , S ) , ( y , T ) } ^ { \lambda } \big ) = d e g _ { \mathfrak { S } } ( x , S ) +$ $d e g _ { \odot } ( y , T ) = d e g S + f ( x ) + d e g T + f ( y ) \in Z$ 。接下来我们将开始证明 $R _ { 0 } [ \mathfrak { S } ]$ 是一个具有分次预胞腔结构 $( K , N , D , d e g _ { \odot } )$ 的分次预胞腔代数。

根据假设可知， $\{ C _ { S , T } ^ { \lambda } | \lambda \in K ; S , T \in M ( \lambda ) \}$ 是 $R [ G ]$ 的一组 $R -$ 基，对于任意元素$( a , x , y ) \in ( R [ G ] , x , y )$ 都能被 $B : = \{ D _ { ( x , S ) , ( y , T ) } ^ { \lambda } | \lambda \in K ; ( x , S ) , ( y , T ) \in N ( \lambda ) \}$ 中的元素 $R$ -线性表示，因此可证 $B$ 是 $R _ { 0 } [ \mathfrak { S } ]$ 的一组 $R$ 一基。

任取 $g \in G$ ， $u , v \in \Lambda$ ，有 $( g , u , v ) \in \mathfrak { S } .$ 。再取基元素 $D _ { ( x , S ) , ( y , T ) } ^ { \alpha } \in B$ ，有

$$
\begin{array} { r } { D _ { ( x , S ) , ( y , T ) } ^ { \alpha } ( g , u , v ) = \big ( C _ { S , T } ^ { \alpha } , x , y \big ) ( g , u , v ) = \big ( C _ { S , T } ^ { \alpha } p _ { y , u } g , x , v \big ) , } \end{array}
$$

于 $R [ G ]$ 是一个具有分次预胞腔结构 $( K , N , D , d e g _ { g } )$ 的分次预胞腔代数，有

$$
C _ { S , T } ^ { \alpha } p _ { y , u } g = \sum _ { T ^ { \prime } \in M ( \alpha ) } R _ { p _ { y , u } g } ( T ^ { \prime } , T ) C _ { S , T ^ { \prime } } ^ { \alpha } + \sum _ { \lambda < \alpha ; \lambda \in K ; U , V \in M ( \lambda ) } R ( \lambda , U , V ) C _ { U , V } ^ { \lambda } \ ,
$$

其中上述等式系数 $R _ { p _ { y , u } g } ( T ^ { \prime } , T ) \in R$ 但不依赖于 $s$ 。由于元素 $C _ { S , T } ^ { \alpha } p _ { y , u } g$ 可由 $R [ G ]$ 中的 $R$ -基 $\{ C _ { S , T } ^ { \lambda } | \lambda \in K ; S , T \in M ( \lambda ) \}$ 线性表示，可写成

$$
C _ { S , T } ^ { \alpha } p _ { y , u } g = \sum _ { \lambda \in K ; U , V \in M ( \lambda ) } R ( \alpha , S , T , y , u , g ; \lambda , U , V ) C _ { U , V } ^ { \lambda } \circ
$$

对比等式(3)和(4)，可以发现,对于任意 $T ^ { \prime } \in M ( \alpha ) , \lambda < \alpha , U , V \in M ( \lambda )$ 都有$R ( \alpha , S , T , y , u , g ; \lambda , T ^ { \prime } , T ) = R _ { p _ { y , u } g } ( T ^ { \prime } , T )$ 以及 $R ( \alpha , S , T , y , u , g ; \lambda , U , V ) = R ( \lambda , U , V )$ ，显然也可以发现 $R ( \alpha , S , T , y , u , g ; \lambda , T ^ { \prime } , T )$ 不依赖于 $x$ ，又因为 $R _ { p _ { y , u } g } ( T ^ { \prime } , T )$ 也不依赖于S，因此我们可以得到 $\vert R ( \alpha , S , T , y , u , g ; \lambda , T ^ { \prime } , T )$ 不依赖于 $x$ 和S。有

$$
\equiv \sum _ { ( v , T ^ { \prime } ) \in N ( \lambda ) } ^ { a } R ( \alpha , S , T , y , u , g ; \lambda , T ^ { \prime } , T ) D _ { ( x , S ) , ( v , T ^ { \prime } ) } ^ { \alpha } \pmod { R _ { 0 } [ \mathfrak { S } ] ( < \alpha ) } \circ
$$

因此，定义3.1的(GP3)得证。

同理，任取 $g \in G$ ， $u , v \in \Lambda$ ，有 $( g , u , v ) \in \mathfrak { S }$ 。再取基元素 $D _ { ( x , S ) , ( y , T ) } ^ { \alpha } \in B$ ，有$\begin{array} { r } { ( g , u , v ) D _ { ( x , S ) , ( y , T ) } ^ { \alpha } = ( g , u , v ) \big ( C _ { S , T } ^ { \alpha } , x , y \big ) = \big ( g p _ { v , x } C _ { S , T } ^ { \alpha } , u , y \big ) , } \end{array}$ （2号

由于 $R [ G ]$ 是一个具有分次预胞腔结构 $( K , N , D , d e g _ { g } )$ 的分次预胞腔代数，有

$$
g p _ { v , x } C _ { S , T } ^ { \alpha } = \sum _ { s ^ { \prime } \in M ( \alpha ) } L _ { g p _ { v , x } } ( S ^ { \prime } , S ) C _ { S ^ { \prime } , T } ^ { \alpha } + \sum _ { \lambda < \alpha ; \lambda \in K ; U , V \in M ( \lambda ) } L ( \lambda , U , V ) C _ { U , V } ^ { \lambda } \ ,
$$

其中上述等式系数 $L _ { g p _ { v , x } } ( S ^ { \prime } , S ) \in R$ 但不依赖于 $T$ 。由于元素 $g p _ { v , x } C _ { S , T } ^ { \lambda }$ 可由 $R [ G ]$ 中的 $R$ -基 $\{ C _ { S , T } ^ { \lambda } | \lambda \in K ; S , T \in M ( \lambda ) \}$ 线性表示，可写成

$$
g p _ { v , x } C _ { S , T } ^ { \alpha } = \sum _ { \lambda \in K ; U , V \in M ( \lambda ) } L ( \alpha , S , T , v , x , g ; \lambda , U , V ) C _ { U , V } ^ { \lambda } \circ
$$

对比等式(5)和 (6)，可以发现，对于任意 $S ^ { \prime } \in M ( \alpha ) , \lambda < \alpha , U , V \in M ( \lambda )$ 都有$L ( \alpha , S , T , v , x , g ; \lambda , S ^ { \prime } , S ) = L _ { g p _ { v , x } } ( S ^ { \prime } , S )$ 以及 $L ( \alpha , S , T , v , x , g ; \lambda , U , V ) = L ( \lambda , U , V )$ ，显然也可以发现 $L ( \alpha , S , T , v , x , g ; \lambda , S ^ { \prime } , S )$ 不依赖于 $y$ ，又因为 $L _ { g p _ { v , x } } ( S ^ { \prime } , S )$ 也不依赖于 $T$ ，因此我们可以得到 $L ( \alpha , S , T , v , x , g ; \lambda , S ^ { \prime } , S )$ 不依赖于y和 $T$ 。有

$$
\begin{array} { r l } & { ( g , u , v ) D _ { ( x , S ) , ( y , T ) } ^ { \alpha } } \\ & { \equiv \displaystyle \sum _ { ( u , S ^ { \prime } ) \in N ( \lambda ) } L ( \alpha , S , T , v , x , g ; \alpha , S ^ { \prime } , S ) D _ { ( u , S ^ { \prime } ) , ( y , T ) } ^ { \alpha } \quad \big ( m o d R _ { 0 } [ \mathfrak { S } ] ( < \alpha ) \big ) \circ } \end{array}
$$

因此，定义3.1的(GP4)得证。

设 $A _ { d }$ 是由 $\left\{ D _ { ( x , S ) , ( y , T ) } ^ { \lambda } \vert d e g _ { \Xi } \bigl ( D _ { ( x , S ) , ( y , T ) } ^ { \lambda } \bigr ) = d \in Z ; \lambda \in K ; ( x , S ) , ( y , T ) \in N ( \lambda ) \right\}$ 中元素R-线性生成的，则Ro[G]=dezAd取Ds)(y,T）EAd,DU）(qv) ∈A即 $d e g S + f ( x ) + d e g T + f ( y ) = d$ ， $d e g U + f ( w ) + d e g V + f ( q ) = l$ ，考虑$D _ { ( x , S ) , ( y , T ) } ^ { \lambda } D _ { ( w , U ) , ( q , V ) } ^ { \mu }$ 的次数。根据 $R [ G ]$ 是一个分次预胞腔代数，设 $A _ { d } ^ { \prime }$ 是由$\left\{ C _ { S , T } ^ { \lambda } | d e g \big ( C _ { S , T } ^ { \lambda } \big ) = d \in Z , \lambda \in K , S , T \in M ( \lambda ) \right\}$ 中元素 $R -$ 线性生成的，则 $R [ G ] =$ $\oplus _ { d \in Z } A _ { d } ^ { \prime }$ ， $A _ { d } ^ { \prime } A _ { l } ^ { \prime } \subseteq A _ { d + l } ^ { \prime }$ 。

（204 $D _ { ( x , S ) , ( y , T ) } ^ { \lambda } D _ { ( w , U ) , ( q , V ) } ^ { \mu } = \bigl ( C _ { S , T } ^ { \lambda } , x , y \bigr ) \bigl ( C _ { U , V } ^ { \mu } , w , q \bigr ) = \bigl ( C _ { S , T } ^ { \lambda } p _ { y w } C _ { U , V } ^ { \mu } , x , q \bigr )$ ，其中$d e g \big ( C _ { S , T } ^ { \alpha } p _ { y w } C _ { U , V } ^ { \mu } \big ) = d e g S + d e g T + f ( y ) + f ( w ) + d e g U + d e g V ,$ 则有$d e g _ { \wp } \left( D _ { ( x , S ) , ( y , T ) } ^ { \lambda } D _ { ( w , U ) , ( q , V ) } ^ { \mu } \right) = d e g _ { \wp } \left( C _ { S , T } ^ { \lambda } p _ { y w } C _ { U , V } ^ { \mu } , x , q \right) = d e g S + d e g T + f ( y ) + d e .$ $f ( w ) + d e g U + d e g V + f ( x ) + f ( q ) = d + l _ { c }$ ，因此， $A _ { d } A _ { l } \subseteq A _ { d + l }$ 。则 $R _ { 0 } [ \mathfrak { S } ]$ 是一个具有分次预胞腔结构 $( K , N , D , d e g _ { \odot } )$ 的 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数。

证毕。

定理4.3设 $R$ 是一个整环， $\mathfrak { S }$ 是一个主因子为 $\mathcal { M } ^ { 0 } = ( G _ { \alpha } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } )$ 的有限正则半群且 $\mathfrak { S }$ 是完全0－单半群的0－直并,其中 $\alpha$ 取遍 $Y = \mathfrak { S } / \mathcal { J }$ 。设映射 $f _ { \alpha } \colon \Lambda _ { \alpha } \to \mathrm { Z }$ ，$E = \{ e \in \mathfrak { S } | 0 \neq e = e ^ { 2 } \}$ 。取 $e \in E$ ，令 $G _ { e }$ 为 $\mathfrak { S }$ 关于单位元 $e$ 的极大子群。如果对于（20 $\alpha \in Y$ ，都有 $E _ { \alpha } : = E \cap E \big ( \mathcal { M } ^ { 0 } = ( G _ { \alpha } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } ) \big ) \not = \emptyset$ ，若 $R [ \mathfrak { S } ]$ 是一个 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数，则任意 $\alpha \in Y$ ，存在 $e \in E _ { \alpha }$ ，使得 $R [ G _ { e } ]$ 也是一个分次预胞腔代数。相反，若任意 $\alpha \in Y$ ，存在 $e \in E _ { \alpha }$ ， $R [ G _ { e } ]$ 是一个分次预胞腔代数，且完全0－单半群$\mathscr { M } ^ { 0 } ( G _ { \alpha } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } ) \cong \mathscr { M } ^ { 0 } ( G _ { e } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } )$ 中的正则矩阵 $P _ { \alpha }$ 的元素 $p _ { i j } \in { G _ { e } } ^ { 0 }$ 的次数为 $f _ { \alpha } ( i ) + f _ { \alpha } ( j )$ ，则 $\mathfrak { S }$ 的主因子的 $R$ 一代数以及 $R [ \mathfrak { S } ]$ 都是 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数。

证明：假设 $R _ { 0 } [ \mathfrak { S } ]$ 是一个具有分次预胞腔结构 $( I , M , C , d e g )$ 的 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数，根据定理4.1可知，任意 $a \in { \mathfrak { S } }$ ，都有 $\cdot \boldsymbol { R } [ J _ { a } ]$ 是一个具有分次预胞腔结构$( I _ { a } , M _ { a } , C _ { a } , d e g _ { a } )$ 的分次预胞腔代数。选定 $\alpha \in Y$ ，令 $\cdot J _ { a } = \mathcal { M } ^ { 0 } ( G _ { \alpha } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } ) \backslash \{ 0 \}$ 则有 $\mathfrak { S } _ { a } \cong \mathcal { M } ^ { 0 } ( G _ { \alpha } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } )$ 。又因为 $E _ { \alpha } \neq \emptyset$ ，则存在 $e \in E _ { \alpha }$ ，使得 $\mathfrak { S } _ { a } =$ （204号 $\mathcal { M } ^ { 0 } ( G _ { e } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } )$ 。定义单位元 $\boldsymbol { e } = ( e , 0 , 0 )$ ，根据定理4.2，我们可证得 $R [ G _ { e } ]$ 也是一个分次预胞腔代数。

相反，假设任意 $\alpha \in Y$ ，存在 $e \in E _ { \alpha }$ ，使得 $R [ G _ { e } ]$ 是一个分次预胞腔代数。任取$a \in S$ ，先证 $R [ J _ { a } ]$ 是一个 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数。因为 $\mathfrak { S }$ 是一个主因子为 $\mathcal { M } ^ { 0 } =$ $( G _ { \alpha } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } )$ 的有限正则半群，因此存在 $\alpha \in Y$ ，使得 $a$ 决定的主因子 $( \mathfrak { S } _ { a } : = J _ { a } \cup$ $\{ 0 \} , \circ )$ 为 $\mathcal { M } ^ { 0 } ( G _ { \alpha } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } )$ 。选定 $e \in E _ { \alpha }$ ，使得 $R [ G _ { e } ]$ 是一个具有分次预胞腔结构$( K , M , C , d e g )$ 的分次预胞腔代数，根据定理4.2的证明可知， $R [ J _ { a } ]$ 是一个具有分次预胞腔结构 $( K _ { a } , M _ { a } , D _ { a } , d e g _ { a } )$ 的 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数，其中 $K _ { a } : = K$ ， $M _ { a } ( \lambda )$ $\mathrel { \mathop : } = \Lambda _ { \alpha } \times M ( \lambda )$ ，任意 $( x , S ) , ( y , T ) \in M _ { a } ( \lambda )$ ，有 $D _ { a ; ( x , S ) , ( y , T ) } ^ { \lambda } : = \left( C _ { a ; S , T } ^ { \lambda } , x , y \right)$ 且$d e g _ { a } \bigl ( D _ { a ; ( x , S ) , ( y , T ) } ^ { \lambda } \bigr ) = d e g _ { a } ( x , S ) + d e g _ { a } ( y , T ) = d e g S + f _ { \alpha } ( x ) + d e g T + f _ { \alpha } ( y ) .$

现在我们要证 $R _ { 0 } [ \mathfrak { S } ]$ 是一个具有分次预胞腔结构 $( { \mathfrak { T } } , N , D , d e g _ { \mathfrak { S } } )$ 的 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数，其中 $\mathfrak { T } = \mathsf { U } _ { a \in \mathfrak { I } } ( a , K _ { a } )$ ，定义偏序 $\leq$ ：任意 $a , b \in { \mathfrak { I } }$ ， $\lambda \in K _ { a }$ ， $\mu \in K _ { b }$ 以及 $\lambda \neq \mu$ ，则 $( a , \lambda ) < ( b , \mu ) \Longleftrightarrow J _ { a } < J _ { b }$ 或者当 $J _ { a } = J _ { b }$ 时， $\lambda < \mu$ 且 ${ \boldsymbol { \mu } } \in K _ { a }$ 。任取$( a , \lambda ) \in ( a , K _ { a } )$ ，定义 $N ( a , \lambda ) = M _ { a } ( \lambda )$ ，任意 $U , V \in N ( a , \lambda )$ ，有 $D _ { U , V } ^ { ( a , \lambda ) } = D _ { a ; U , V } ^ { \lambda }$ 且$d e g _ { \wp } { \Bigl ( } D _ { U , V } ^ { ( a , \lambda ) } { \Bigr ) } = d e g _ { \wp } U + d e g _ { \wp } V = d e g _ { a } U + d e g _ { a } V { \circ }$ （20

设 $\Im$ 为的 $\mathcal { J } -$ 类的所有代表元所构成的集合。根据假设， $\mathfrak { S } = \cup _ { i \in \mathfrak { I } } \mathfrak { S } _ { i }$ ，任意$a , b \in { \mathfrak { I } }$ 且 $a \neq b$ ，有 $\mathfrak { S } _ { a } \mathfrak { S } _ { b } = \{ 0 \}$ 。由于 $R [ J _ { a } ]$ 是一个具有分次预胞腔结构$( K _ { a } , M _ { a } , D _ { a } , d e g _ { a } )$ 的 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数，则 $\mathsf { U } _ { ( a , \lambda ) \in ( a , K _ { a } ) } \Bigl \{ D _ { U , V } ^ { ( a , \lambda ) } \Bigl | U , V \in N ( a , \lambda ) \Bigr \}$ 构成 $R [ J _ { a } ]$ 的一组 $R$ -基。则可以证得 $\begin{array} { r } { \cdot H : = \bigcup _ { a \in \mathfrak { I } ; ( a , \lambda ) \in ( a , K _ { a } ) } \Bigl \{ D _ { U , V } ^ { ( a , \lambda ) } \Bigl | U , V \in N ( a , \lambda ) \Bigr \} } \end{array}$ 构成 $R _ { 0 } [ \mathfrak { S } ]$ 的一组 $R -$ 基，定义3.1的(GP1)得证。

假设 $a , b \in { \mathfrak { I } }$ ，若 $b \in I ( a )$ ， $\boldsymbol { \mu } \in \boldsymbol { K } _ { b }$ 以及 $\alpha \in K _ { a }$ ，有 $( b , \mu ) < ( a , \alpha )$ 。事实上

$$
b \in I ( a ) \Leftrightarrow { \mathfrak { S } } ^ { 1 } b { \mathfrak { S } } ^ { 1 } \subset { \mathfrak { S } } ^ { 1 } a { \mathfrak { S } } ^ { 1 } \Longleftrightarrow J _ { b } < J _ { a } \qquad 
$$

如果 $b \in I ( a )$ ，那么对于任意 $\boldsymbol { \mu } \in \boldsymbol { K } _ { b }$ 以及 $\lambda \in K _ { a }$ ，都有 $( b , \mu ) < ( a , \lambda )$ 。现在我们可以假设 $\lambda \in K _ { a }$ 公， $( x , S ) , ( y , T ) \in M _ { a } ( \lambda )$ 以及 $c \in \mathfrak { S }$ ，考虑 $D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } c =$ $D _ { a ; ( x , S ) , ( y , T ) } ^ { \lambda } c$ ，其中 $D _ { a ; ( x , S ) , ( y , T ) } ^ { \lambda } \in R [ J _ { a } ]$ 。又因为令 $G _ { e } = ( G _ { e } , 0 , 0 )$ ，则根据（204号 $s u p p \big ( C _ { S , T } ^ { \lambda } \big ) \subseteq G _ { e }$ ，有 $s u p p \bigl ( D _ { a ; ( x , S ) , ( y , T ) } ^ { \lambda } \bigr ) \subseteq R [ ( G , x , y ) ]$ 。

根据引理2.1，有 $( e , 0 , y ) c \in J _ { a }$ 或者 $( e , 0 , y ) c \in I ( a )$

假设 $( e , 0 , y ) c \in I ( a )$ 。有

$$
D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } c = D _ { a ; ( x , S ) , ( y , T ) } ^ { \lambda } c = \big ( C _ { a ; S , T } ^ { \lambda } , x , 0 \big ) ( e , 0 , y ) _ { C \circ }
$$

因为 $\boldsymbol { I } ( \boldsymbol { a } )$ 是 ${ \mathfrak { S } } ^ { 1 } a { \mathfrak { S } } ^ { 1 }$ 的一个理想，因此可得 $D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } c \in R \left[ I ( a ) \right] .$ 存在 $\mathfrak { I } _ { 1 } \subset \mathfrak { I }$ ，v使得 ${ \mathfrak { I } } _ { 1 } \subseteq I ( a )$ 吸 $D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } c \in \cup _ { h \in \mathfrak { I } _ { 1 } } R [ J _ { h } ] \mathfrak { c }$ 又由于当 $h \in \mathfrak { I } _ { 1 } , \mu \in K _ { b }$ 吸 $\alpha \in K _ { a }$ 时，有 $( b , \mu ) < ( a , \alpha )$ ，因此可得 $\mathsf { U } _ { h \in \mathfrak { I } _ { 1 } } R [ J _ { h } ] \subset R [ \mathfrak { S } ] \big ( < ( a , \lambda ) \big )$ 即， $D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } c \in$ $R [ \mathfrak { S } ] \bigl ( < ( a , \lambda ) \bigr )$ 0

假设 $( e , 0 , y ) c \in J _ { a }$ ，有

$$
\begin{array} { r l } & { D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } c = D _ { a ; ( x , S ) , ( y , T ) } ^ { \lambda } c } \\ & { = \bigl [ \bigl ( C _ { a ; S , T } ^ { \lambda } , x , 0 \bigr ) ( e , 0 , y ) \bigr ] c } \\ & { = \bigl ( C _ { a ; S , T } ^ { \lambda } , x , 0 \bigr ) [ ( e , 0 , y ) c ] } \\ & { = D _ { ( x , S ) , ( 0 , T ) } ^ { ( a , \lambda ) } [ ( e , 0 , y ) c ] \circ } \end{array}
$$

由于 $R [ J _ { a } ]$ 是一个 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数，有

$D _ { ( x , S ) , ( 0 , T ) } ^ { ( a , \lambda ) } [ ( e , 0 , y ) c ] = \sum _ { ( t , T ^ { \prime } ) \in N ( a , \lambda ) } R _ { ( e , 0 , y ) c } \big ( ( t , T ^ { \prime } ) , ( 0 , T ) \big ) D _ { a ; ( x , S ) , ( t , T ^ { \prime } ) } ^ { \lambda } + w ,$ （20其中 $w \in R [ J _ { a } ] ( < \lambda )$ ，系数 $R _ { ( e , 0 , y ) c } \big ( ( t , T ^ { \prime } ) , ( 0 , T ) \big ) \in R$ 且不依赖 $( x , S )$ 。

由于 $\begin{array} { r } { \cdot \mathbb { Q } : = \bigcup _ { a \in \Im ; ( a , \lambda ) \in ( a , K _ { a } ) } \Bigl \{ D _ { U , V } ^ { ( a , \lambda ) } \Big | U , V \in N ( a , \lambda ) \Bigr \} ; } \end{array}$ 构成 $R [ \mathfrak { S } ]$ 的一组 $R -$ 基。由于Da;(x.S).(v.T)c可以由Q中的元素R-线性表示，有

$$
D _ { a ; ( x , S ) , ( y , T ) } ^ { \lambda } c = \sum R ( \lambda , x , S , t , T ^ { \prime } ) D _ { a ; ( x , S ) , ( t , T ^ { \prime } ) } ^ { \lambda } + w ^ { \prime } ,
$$

其中 $w ^ { \prime }$ 是由 $\{ D _ { b ; U ^ { \prime } , V ^ { \prime } } ^ { \mu } | b \in \Im ; ( b , \mu ) \neq ( a , \lambda ) ; U ^ { \prime } , V ^ { \prime } \in N ( b , \mu ) \}$ 中的元素 $R -$ 线性表示。对比等式（7）和 (8) 可知， $D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } c \equiv$ $\begin{array} { r l } { \sum _ { ( t , T ^ { \prime } ) \in N ( a , \lambda ) } R _ { ( e , 0 , y ) c } \big ( ( t , T ^ { \prime } ) , ( 0 , T ) \big ) D _ { ( x , S ) , ( t , T ^ { \prime } ) } ^ { ( a , \lambda ) } } & { { } \Big ( m o d R [ \mathfrak { S } ] \big ( < ( a , \lambda ) \big ) \Big ) , } \end{array}$ 。则定义3.1的(GP3)得证。

同理，根据引理2.1，有 $c ( e , x , 0 ) \in J _ { a }$ 或者 $c ( e , x , 0 ) \in I ( a )$

假设 $c ( e , x , 0 ) \in I ( a )$ 。有

$$
c D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } = c D _ { a ; ( x , S ) , ( y , T ) } ^ { \lambda } = c ( e , x , 0 ) ( C _ { a ; S , T } ^ { \lambda } , 0 , y ) \circ
$$

因为 $\boldsymbol { I } ( \boldsymbol { a } )$ 是5 $\mathfrak { S } ^ { 1 } a \mathfrak { S } ^ { 1 }$ 的一个理想，因此可得 $c D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } \in R [ I ( a ) ]$ 存在 $\mathfrak { I } _ { 2 } \subset \mathfrak { I }$ ，v使得 ${ \mathfrak { I } } _ { 2 } \subseteq I ( a )$ 吸 $c D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } \in \cup _ { b \in \mathfrak { I } _ { 2 } } R [ J _ { b } ] \circ$ 又由于当 $b \in \mathfrak { I } _ { 2 } , \mu \in K _ { b }$ 吸 $\alpha \in K _ { a }$ 时，有 $( b , \mu ) < ( a , \alpha )$ ，因此可得 $\cup _ { b \in \Im _ { 2 } } R [ J _ { b } ] \subset R _ { 0 } [ \mathfrak { S } ] \big ( < ( a , \lambda ) \big )$ 即 $c D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } \in$ $R _ { 0 } [ \mathfrak { S } ] \bigl ( < ( a , \lambda ) \bigr )$ 。

假设 $c ( e , x , 0 ) \in J _ { a }$ ，有

$$
\begin{array} { r l } & { c D _ { ( x , s ) , ( y , T ) } ^ { ( a , { \lambda } ) } = c D _ { a ; ( x , s ) , ( y , T ) } ^ { \lambda } } \\ & { = c \big [ ( e , x , 0 ) \big ( C _ { a ; S , T } ^ { \lambda } , 0 , y \big ) \big ] } \\ & { = c ( e , x , 0 ) \big ( C _ { a ; S , T } ^ { \lambda } , 0 , y \big ) } \\ & { = c ( e , x , 0 ) D _ { ( 0 , S ) , ( y , T ) } ^ { ( a , \lambda ) } \circ } \end{array}
$$

由于 $R [ J _ { a } ]$ 是一个分次预胞腔代数，有

$$
c ( e , x , 0 ) D _ { ( 0 , S ) , ( y , T ) } ^ { ( a , \lambda ) } = \sum _ { ( s , s ^ { \prime } ) \in N ( a , \lambda ) } L _ { c ( e , x , 0 ) } \big ( ( s , S ^ { \prime } ) , ( 0 , S ) \big ) D _ { a ; ( s , S ^ { \prime } ) , ( y , T ) } ^ { \lambda } + z ,
$$

其中 $z \in R [ J _ { a } ] ( < \lambda )$ ，系数 $L _ { c ( e , x , 0 ) } \big ( ( s , S ^ { \prime } ) , ( 0 , S ) \big ) \in R$ 且不依赖 $( y , T )$ 。

由于 $\begin{array} { r } { \mathbb { Q } : = \bigcup _ { a \in \Im ; ( a , \lambda ) \in ( a , K _ { a } ) } \Bigl \{ D _ { U , V } ^ { ( a , \lambda ) } \Big | U , V \in N ( a , \lambda ) \Bigr \} ; } \end{array}$ 构成 $R [ \mathfrak { S } ]$ 的一组 $R$ -基。由于$c D _ { a ; ( x , S ) , ( y , T ) } ^ { \lambda }$ 可以由 $\mathsf { Q }$ 中的元素 $R$ -线性表示，有

$$
c D _ { a ; ( x , S ) , ( y , T ) } ^ { \lambda } = \sum L ( \lambda , s , S ^ { \prime } , y , T ) D _ { a ; ( s , S ^ { \prime } ) , ( y , T ) } ^ { \lambda } + z ^ { \prime } ,
$$

其中 $z ^ { \prime }$ 是由 $\{ D _ { b ; U ^ { \prime } , V ^ { \prime } } ^ { \mu } | b \in \Im ; ( b , \mu ) \neq ( a , \lambda ) ; U ^ { \prime } , V ^ { \prime } \in N ( b , \mu ) \}$ 中的元素 $R$ -线性表示。可知， $c D _ { ( x , S ) , ( y , T ) } ^ { ( a , \lambda ) } \equiv$ $\begin{array} { r l } { \sum _ { ( s , S ^ { \prime } ) \in N ( a , \lambda ) } L _ { c ( e , x , 0 ) } \big ( ( s , S ^ { \prime } ) , ( 0 , S ) \big ) D _ { ( s , S ^ { \prime } ) , ( y , T ) } ^ { ( a , \lambda ) } } & { { } \Big ( m o d R [ \mathfrak { S } ] \big ( < ( a , \lambda ) \big ) \Big ) , } \end{array}$ ，则定义3.1的(GP4)得证。

$$
\begin{array} { r l } { \check { \iota } \check { \Sigma } \ } & { \ \boldsymbol { A } _ { d } \ } & { \overset {  } { \underset {  } { \Sigma } } \quad \stackrel {  } { \Sigma } \quad \stackrel {  } { \Sigma } \quad \stackrel { \{  } } { \big \{ D }  ( \boldsymbol { a } _ { \langle x , \boldsymbol { S } \rangle , ( \boldsymbol { J } , T ) } ^ { ( a , \lambda ) } )  d e g _ { \mathfrak { S } } \big ( \boldsymbol { D } _ { ( x , \boldsymbol { S } ) , ( \boldsymbol { J } , T ) } ^ { ( a , \lambda ) } \big ) = d \ \in \boldsymbol { Z } ; a \in \mathfrak { I } ; ( a , \lambda ) \ \boldsymbol { \updownarrow }  \\ & { ( a , K _ { a } ) ; ( \boldsymbol { x } , \boldsymbol { S } ) , ( \boldsymbol { y } , T ) \in N ( a , \lambda ) \} \forall \mathrm { i } \gamma \underset {  } { \Sigma } \big \Vert \underset {  } { \Sigma } \big \Vert \underset {  } { \Sigma } { \big \Vert \big { \check { \Sigma } } } \big \Vert \underset {  } { \Sigma } { \big \Vert \big { \check { \Sigma } } } \big \Vert \underset {  } { \Sigma } { \big \Vert \big { \check { \Sigma } } } \big \Vert \underset {  } { \Sigma } { \big \Vert \big { \check { \Sigma } } } \big \Vert \underset {  } { \big } { \big \Vert \big { \check { \Sigma } } } \big \Vert \underset {  } { \big } { \big \Vert \big { \check { \Sigma } } } \big \Vert } = \bigoplus _ { d \in \mathcal { Z } } A _ { d } \circ \ \ \mathbb { \~ \mathbb { R } } ,  \\ & { D _ { ( x , \boldsymbol { S } ) , ( y , T ) } ^ { ( a , \lambda ) } \in \boldsymbol { A } _ { d } \ \ , \ D _ { ( w , \theta ) , ( q , \nu ) } ^ { ( b , \mu ) } \in \boldsymbol { A } _ { l } \ , \quad \mathrm { \forall } \Vert \ d e g _ { a } \boldsymbol { S } + f _ { a } ( \boldsymbol { x } ) + d e g _ { a } T + f _ { a } ( \boldsymbol { y } ) = d \ \ , } \\ &  d e g _ { b } U + f _ { b } ( w ) + d e g _ { b } V + f _ { b } ( q ) = l \ , \ \frac { \ r _ { \ast } } { \mathcal { G } } \underset {  } { \sum _ { j } } \underset {  } { \sum _ { k } } \operatorname { D } _ { ( x , \boldsymbol { S } ) , ( \boldsymbol { g } , \boldsymbol { f } ) } ^ { ( a , \lambda ) } \big ( \boldsymbol { g } _ { b } ^ { ( a , \lambda ) } \big ( \boldsymbol { g } _ { l } \big ) \underset {  } { \operatorname { \Sigma } } \big \Vert \mathcal { H } \underset {  }  \end{array}
$$

综上所述， $R [ \mathfrak { S } ]$ 是一个具有分次预胞腔结构 $( { \mathfrak { T } } , N , D , d e g _ { \mathfrak { S } } )$ 的分次预胞腔代数，显然 $R [ \mathfrak { S } ]$ 也满足 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数的定义，因此 $R [ \mathfrak { S } ]$ 是一个 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数。

证毕。

推论4.4设 $R$ 是一个整环， $\mathfrak { S }$ 是一个主因子为 $\mathcal { M } ^ { 0 } = ( G _ { \alpha } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } )$ 的有限正则半群且 $\mathfrak { S }$ 是完全0－单半群的0－直并，其中 $\alpha$ 取遍 $Y = \odot / \mathcal { J }$ 。设映射 $f _ { \alpha } \colon \Lambda _ { \alpha } \to \mathrm { Z }$ $E$ 是 $\mathfrak { S }$ 的所有幂等元所构成的集合，任取 $e \in E$ ，令 $G _ { e }$ 为 $\mathfrak { S }$ 关于单位元 $e$ 的极大子群。任意 $\alpha \in Y = \mathfrak { S } / \mathcal { J }$ ，有 $E \cap E \big ( \mathcal { M } ^ { 0 } = ( G _ { \alpha } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } ) \big ) \neq \emptyset$ ，若 $R [ \mathfrak { S } ]$ 是一个 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数，则任意 $e \in E$ ，都有群代数 $R [ G _ { e } ]$ 是一个分次预胞腔代数。相反，若 $R [ G _ { e } ]$ 是一个分次预胞腔代数，且完全0－单半群 $\mathcal { M } ^ { 0 } ( G _ { \alpha } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } ) \cong$ $\mathcal { M } ^ { 0 } ( G _ { e } , \Lambda _ { \alpha } , \Lambda _ { \alpha } ; P _ { \alpha } )$ 中的正则矩阵 $P _ { \alpha }$ 的元素 $p _ { i j } \in { G _ { e } } ^ { 0 }$ 的次数为 $f _ { \alpha } ( i ) + f _ { \alpha } ( j )$ ，则 $\mathfrak { S }$ 的主因子的 $R$ 一代数以及 $R [ \mathfrak { S } ]$ 都是 $\mathcal { J } \mathcal { H }$ 型分次预胞腔代数。

# 参考文献：

[1] J.J.Graham， G.I.Lehrer.Cellular algebras[J]．Inventiones Mathematicae，1996,123(1):1- 34.   
[2] S.Konig，C.C. Xi. On the structure of cellular algebras[J]. Proceedings of ICRA VIII, Canadian Mathematical Society Conference Proceedings， Canadian Mathematical Society， Ottawa, 1998，24:365-386.   
[3] H.B. Rui. Based algebras and standard bases for quasi-hereditary algebras[J]. Transactions of the American Mathematical Society，1998，350(8):3207-3235.   
[4]王涛．预胞腔代数[D]．南京：南京大学，2015.   
[5] J.Hu,A. Mathas. Graded cellular bases for the cyclotomic Khovanov-Lauda-Rouquier algebras of type A[J]．Advances in Mathematics，2000，225(2):598-642.   
[6] J.M. Howie. Fundamentals of semigroup theory[M]. Oxford: Oxford University Press，1995. [7] J. Okninski. Semigroup Algebras[M]． New York: Monographs and Textbooks in Pure and Applied Mathematics，Marcel Dekker，Inc.，1991.   
[8] J.M. Howie. An Introduction to Semigroup Theory[M]. London: Academic Press，1976. [9]J.A. Green. On the structure of semigroups[J]． Annals of Mathematics，1951，54(2):163- 172.   
[10]R.Gordon and E. L. Green，Graded Artin algebras［J]． Journal of Algebra，1982，76:111- 137.   
(通讯作者：苏志荣 E-mail:2112014026@mail2.gdut.edu.cn)