# Relations of endograph metric and I-convergence on fuzzy sets ☆

Huan Huang Departmentof Mathematics,Jimei University，Xiamen 361021,China

# Abstract

This paper shows that the endograph metric and the $\Gamma$ -convergence are compatible on a large class of fuzzy set in $\mathbb { R } ^ { m }$

Keywords: Endograph metric; $\Gamma$ -convergence; Hausdorff metric; compatible

# 1．Introduction

We show that the endograph metric and the $\Gamma$ -convergence are compatible on a large class of fuzzy set in $\mathbb { R } ^ { m }$ . The results in this paper improves the corresponding results in [5, 6]

# 2.Preliminaries

In this section, we recall and give some basic notions and fundamental results related to fuzzy sets and convergence structures on them. Readers can refer to [1-4] for related contents.

Throughout this paper,we suppose that $X$ is a nonempty set and d is the metric on $X$ . For simplicity, we also use $X$ to denote the metric space $( X , d )$ ：

The metric $\bar { d }$ on $X \times [ 0 , 1 ]$ is defined as follows: for $( x , \alpha ) , ( y , \beta ) \in X \times$ （204号 $[ 0 , 1 ]$ ，

$$
\overline { { d } } ( ( x , \alpha ) , ( y , \beta ) ) = d ( x , y ) + \lvert \alpha - \beta \rvert .
$$

Throughout this paper, we suppose that the metric on $X \times [ 0 , 1 ]$ is $\overline { { d } }$ .For simplicity, we also use $X \times [ 0 , 1 ]$ to denote the metric space $( X \times [ 0 , 1 ] , { \overline { { d } } } )$

A fuzzy set $u$ in $X$ can be seen as a function $u : X \to \lfloor 0 , 1 \rfloor$ . A subset $S$ （204 of $X$ can be seen as a fuzzy set in $X$ . If there is no confusion, the fuzzy set corresponding to $S$ is often denoted by $\chi _ { S }$ ; that is,

$$
\chi _ { S } ( x ) = { \left\{ \begin{array} { l l } { 1 , } & { x \in S , } \\ { 0 , } & { x \in X \setminus S . } \end{array} \right. }
$$

For simplicity, for $x \in X$ ， we will use $\widehat { x }$ to denote the fuzzy set $\chi \{ x \}$ in $X$ In this paper, if we want to emphasize a specific metric space $X$ ，we will write the fuzzy set corresponding to $S$ in $X$ as $S _ { F ( X ) }$ ，and the fuzzy set corresponding to $\{ x \}$ in $X$ as ${ \widehat { x } } _ { F ( X ) }$

The symbol $F ( X )$ is used to denote the set of all fuzzy sets in $X$ .For $u \in F ( X )$ and $\alpha \in [ 0 , 1 ]$ ，let $\{ u > \alpha \}$ denote the set $\{ x \in X : u ( x ) > \alpha \}$ ， and let $[ u ] _ { \alpha }$ denote the $\alpha$ -cut of $u$ ,i.e.

$$
[ u ] _ { \alpha } = \left\{ \{ x \in X : u ( x ) \geq \alpha \} , \quad \alpha \in ( 0 , 1 ] , \right.
$$

where $\overline { S }$ denotes the topological closure of $S$ in $( X , d )$

The symbol $K ( X )$ and $C ( X )$ are used to denote the set of all nonempty compact subsets of $X$ and the set of all nonempty closed subsets of $X$ ， respectively.

Let $F _ { U S C } ( X )$ denote the set of all upper semi-continuous fuzzy sets $u$ ： $X  [ 0 , 1 ]$ ,i.e.,

Define

$$
\begin{array} { r } { F _ { U S C B } ( X ) : = \{ u \in F _ { U S C } ( X ) : [ u ] _ { 0 } \in K ( X ) \cup } \\ { F _ { U S C G } ( X ) : = \{ u \in F _ { U S C } ( X ) : [ u ] _ { \alpha } \in K ( X ) \cup \{ \varnothing \} \mathrm { ~ f o r ~ } } \end{array}
$$

Clearly,

$$
F _ { U S C B } ( X ) \subseteq F _ { U S C G } ( X ) \subseteq F _ { U S C } ( X ) .
$$

Define

$$
{ \cal F } _ { C O N } ( X ) : = \{ u \in { \cal F } ( X ) : \mathrm { f o r ~ a l l } \alpha \in ( 0 , 1 ] , \ [ u ] _ { \alpha } \mathrm { ~ i s ~ c o n n e c t e d ~ i n ~ } X \} ,
$$

$$
\begin{array} { r l } & { F _ { U S C C O N } ( X ) : = F _ { U S C } ( X ) \cap F _ { C O N } ( X ) , } \\ & { F _ { U S C G C O N } ( X ) : = F _ { U S C G } ( X ) \cap F _ { C O N } ( X ) . } \end{array}
$$

Let $u \in F _ { C O N } ( X )$ . Then $[ u ] _ { 0 } = \overline { { \cup _ { \alpha > 0 } [ u ] _ { \alpha } } }$ is connected in $X$

If $u = \chi _ { \emptyset }$ ，then $[ u ] _ { 0 } = \emptyset$ is connected in $X$ If $u \ne \chi _ { \emptyset }$ ， then there is an $\alpha \in ( 0 , 1 ]$ such that $[ u ] _ { \alpha } \neq \emptyset$ . Note that $[ u ] _ { \beta } \supseteq [ u ] _ { \alpha }$ when $\beta \in [ 0 , \alpha ]$ . Hence $\cup _ { 0 < \beta < \alpha } [ u ] _ { \beta }$ is connected, and thus $[ u ] _ { 0 } = \cup _ { 0 < \beta < \alpha } [ u ] _ { \beta }$ is connected.

So

$$
{ \mathit { F } } _ { C O N } ( X ) = \{ u \in { \mathit { F } } ( X ) : { \mathrm { f o r ~ a l l ~ } } \alpha \in [ 0 , 1 ] , \ [ u ] _ { \alpha } { \mathrm { ~ i s ~ c o n n e c t e d ~ i n ~ } } X \} .
$$

Let $F _ { U S C } ^ { 1 } ( X )$ denote the set of all normal and upper semi-continuous fuzzy sets $u : X \to [ 0 , 1 ]$ ,i.e.,

$$
{ \cal F } _ { U S C } ^ { 1 } ( X ) : = \{ u \in { \cal F } ( X ) : [ u ] _ { \alpha } \in { \cal C } ( X ) \ \mathrm { f o r ~ a l l } \ \alpha \in [ 0 , 1 ] \} .
$$

We introduce some subclasses of $F _ { U S C } ^ { 1 } ( X )$ ,which will be discussed in this paper.Define

$$
\begin{array} { r l } & { F _ { U S C B } ^ { 1 } ( X ) : = F _ { U S C } ^ { 1 } ( X ) \cap F _ { U S C B } ( X ) , } \\ & { F _ { U S C G } ^ { 1 } ( X ) : = F _ { U S C } ^ { 1 } ( X ) \cap F _ { U S C G } ( X ) , } \\ & { F _ { U S C C O N } ^ { 1 } ( X ) : = F _ { U S C } ^ { 1 } ( X ) \cap F _ { C O N } ( X ) , } \\ & { F _ { U S C G C O N } ^ { 1 } ( X ) : = F _ { U S C G } ^ { 1 } ( X ) \cap F _ { C O N } ( X ) . } \end{array}
$$

Clearly,

$$
\begin{array} { r l } & { F _ { U S C B } ^ { 1 } ( X ) \subseteq F _ { U S C G } ^ { 1 } ( X ) \subseteq F _ { U S C } ^ { 1 } ( X ) , } \\ & { \quad F _ { U S C G C O N } ^ { 1 } ( X ) \subseteq F _ { U S C C O N } ^ { 1 } ( X ) . } \end{array}
$$

Let $( X , d )$ be a metric space. We use $\pmb { H }$ to denote the Hausdorff distance on $C ( X )$ induced by $d$ ,i.e.,

$$
H ( U , V ) = \operatorname* { m a x } \{ H ^ { * } ( U , V ) , \ H ^ { * } ( V , U ) \}
$$

for arbitrary $U , V \in C ( X )$ ，where

$$
H ^ { * } ( U , V ) = \operatorname* { s u p } _ { u \in U } d ( u , V ) = \operatorname* { s u p } _ { u \in U } \operatorname* { i n f } _ { v \in V } d ( u , v ) .
$$

If there is no confusion, we also use $H$ to denote the Hausdorff distance on $C ( X \times [ 0 , 1 ] )$ induced by $\bar { d }$ ：

Remark 2.1. $\rho$ is said to be a metric on $Y$ if $\rho$ is a function from $Y \times Y$ into $\mathbb { R }$ satisfying positivity, symmetry and triangle inequality. At this time, $( Y , \rho )$ is said to be a metric space.

$\rho$ is said to be an extended metric on $Y$ if $\rho$ is a function from $Y \times Y$ into $\mathbb { R } \cup \{ + \infty \}$ satisfying positivity, symmetry and triangle inequality. At this time, $( Y , \rho )$ is said to be an extended metric space.

We can see that for arbitrary metric space $( X , d )$ , the Hausdorff distance $H$ on $K ( X )$ induced by $d$ is a metric. So the Hausdorff distance $H$ on $K ( X \times [ 0 , 1 ] )$ induced by $\bar { d }$ on $X \times [ 0 , 1 ]$ is a metric. In these cases,we call the Hausdorff distance the Hausdorff metric.

The Hausdorff distance $H$ on $C ( X )$ induced by $d$ on $X$ is an extended metric, but probably not a metric, because $H ( A , B )$ could be equal to $+ \infty$ （20 for certain metric space $X$ and $A , B \in C ( X )$ . Clearly, if $H$ on $C ( X )$ induced by $d$ is not a metric,then $H$ on $C ( X \times [ 0 , 1 ] )$ induced by $\bar { d }$ is also not a metric. So the Hausdorff distance $H$ on $C ( X \times [ 0 , 1 ] )$ induced by $\bar { d }$ on $X \times [ 0 , 1 ]$ is an extended metric but probably not a metric. In the cases that the Hausdorff distance $H$ is an extended metric,we call the Hausdorff distance the Hausdorff extended metric.

We can see that $H$ on $C ( \mathbb { R } ^ { m } )$ is an extended metric but not a metric,and then the same is $H$ on $C ( \mathbb { R } ^ { m } \times [ 0 , 1 ] )$ ：

In this paper, for simplicity， we refer to both the Hausdorff extended metric and the Hausdorff metric as the Hausdorff metric.

For $u \in F ( X )$ ，define

$$
\begin{array} { r l } & { \mathrm { ~ e n d ~ } u : = \{ ( x , t ) \in X \times [ 0 , 1 ] : u ( x ) \geq t \} , } \\ & { \mathrm { ~ s e n d ~ } u : = \{ ( x , t ) \in X \times [ 0 , 1 ] : u ( x ) \geq t \} \cap ( [ u ] _ { 0 } \times [ 0 , 1 ] ) . } \end{array}
$$

end $u$ and send $u$ are called the endograph and the sendograph of $u$ ， respectively.

We can define the endograph metric $H _ { \mathrm { e n d } }$ on $F _ { U S C } ( X )$ as usual. For （204号 $u , v \in F _ { U S C } ( X )$ ，

$$
H _ { \mathrm { e n d } } ( u , v ) : = H ( { \mathrm { e n d } } u , { \mathrm { e n d } } v ) ,
$$

where $H$ is the Hausdorff metric on $C ( X \times [ 0 , 1 ] )$ induced by $\overline { { d } }$ on $X \times [ 0 , 1 ]$ Rojas-Medar and Roman-Flores 4] introduced the Kuratowski convergence of a sequence of sets in a metric space.

Let $( X , d )$ be a metric space. Let $C$ be a set in $X$ and $\left\{ C _ { n } \right\}$ a sequence of sets in $X$ ： $\{ C _ { n } \}$ is said to Kuratowski converge to $C$ according to $( X , d )$ ， if

$$
C = \operatorname* { l i m } _ { n \to \infty } \operatorname* { i n f } C _ { n } = \operatorname* { l i m } _ { n \to \infty } \operatorname* { s u p } C _ { n } ,
$$

where

$$
\begin{array} { c } { \displaystyle \operatorname* { l i m i n f } _ { n \to \infty } C _ { n } = \{ x \in X : \ x = \displaystyle \operatorname* { l i m } _ { n \to \infty } x _ { n } , x _ { n } \in C _ { n } \} , } \\ { \displaystyle \operatorname* { l i m } _ { n \to \infty } \operatorname* { l i m } _ { C _ { n } = \{ x \in X : \ x = \displaystyle \operatorname* { l i m } _ { j \to \infty } x _ { n _ { j } } , x _ { n _ { j } } \in C _ { n _ { j } } \} } \frac { \infty } { { n = 1 } \bigcup _ { m \geq n } C _ { m } } . } \end{array}
$$

In this case,， we'll write $C = \operatorname* { l i m } _ { n \to \infty } ^ { ( K ) } C _ { n }$ according to $( X , d )$ If there is no confusion,we will not emphasize the metric space $( X , d )$ and write $\left\{ C _ { n } \right\}$ Kuratowski converges to $C$ or $C = \dim _ { n \to \infty } ^ { ( K ) } C _ { n }$ for simplicity.

We can define the $\Gamma$ -convergence of a sequence of fuzzy sets on $F _ { U S C } ( X )$ 1 as usual.

converge Let ， $u _ { n }$ ， ， $u$ $n = 1 , 2 , \ldots$ denoted by ,be fuzzy sets in $\boldsymbol { u } = \operatorname* { l i m } _ { n \to \infty } ^ { ( \Gamma ) } u _ { n }$ $F _ { U S C } ( X )$ if ${ \mathrm { e n d } } u = \operatorname* { l i m } _ { n \to \infty } ^ { ( K ) } { \mathrm { e n d } } u _ { n }$ ： $\{ u _ { n } \}$ is said to $\mathbf { \delta T }$ according to $( X \times [ 0 , 1 ] , { \overline { { d } } } )$ ：

# 3.Main results

We need the following conclusions.

Theorem 3.1. [5] Suppose that $C$ ， $C _ { n }$ are sets in $C ( X )$ ， $n = 1 , 2 , \ldots$ . Then $H ( C _ { n } , C ) \to 0$ implies that $\operatorname* { l i m } _ { n \to \infty } ^ { ( K ) } C _ { n } = C$ ：

Lemma 3.2. (Lemma 2.1 in $[ 5 ] )$ Let $( X , d )$ be a metric space， and $C _ { n }$ （204 $n = 1 , 2 , \ldots$ ， be a sequence of sets in $X$ . Suppose that $x \in X$ . Then (） $x \in \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } C _ { n }$ if and only if $\begin{array} { r } { \operatorname* { l i m } _ { n  \infty } d ( x , C _ { n } ) = 0 } \end{array}$ ， (ii) $x \in \operatorname* { l i m } \operatorname* { s u p } _ { n \to \infty } C _ { n }$ if and only if there is a subsequence $\big \{ C _ { n _ { k } } \big \}$ of $\left\{ C _ { n } \right\}$ such that $\begin{array} { r } { \operatorname* { l i m } _ { k \to \infty } d ( x , C _ { n _ { k } } ) = 0 } \end{array}$ ：

Proof. Here we give a detailed proof. Readers who think that this conclusion is obvious can skip this proof.

(i) Assume that $x \in \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } C _ { n }$ . Then there is a sequence $\{ x _ { n } , n =$ $1 , 2 , \ldots \}$ in $X$ such that $x _ { n } \in C _ { n }$ for $n = 1 , 2 , \ldots$ and $\begin{array} { r } { \operatorname* { l i m } _ { n \to \infty } d ( x , x _ { n } ) = 0 } \end{array}$ Since $d ( x , C _ { n } ) \leq d ( x , x _ { n } )$ ， thus $\begin{array} { r } { \operatorname* { l i m } _ { n  \infty } d ( x , C _ { n } ) = 0 } \end{array}$ ：

Conversely， assume that $\begin{array} { r } { \operatorname* { l i m } _ { n \to \infty } d ( x , C _ { n } ) \ = \ 0 } \end{array}$ .For each $n = 1 , 2 , \ldots$ we can choose an $x _ { n }$ in $C _ { n }$ such that $d ( x , x _ { n } ) \leq d ( x , C _ { n } ) + 1 / n$ .Hence $\begin{array} { r } { \operatorname* { l i m } _ { n \to \infty } d ( x , x _ { n } ) = 0 } \end{array}$ . So $x \in \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } C _ { n }$

(ii) Assume that $x \in \operatorname* { l i m } \operatorname* { s u p } _ { n \to \infty } C _ { n }$ . Then there is a subsequence $\big \{ C _ { n _ { k } } \big \}$ of $\left\{ C _ { n } \right\}$ and $x _ { n _ { k } } \in C _ { n _ { k } }$ for $k = 1 , 2 , \ldots$ such that $\begin{array} { r } { \operatorname* { l i m } _ { k \to \infty } d ( x , x _ { n _ { k } } ) = 0 } \end{array}$ . Since $d ( x , C _ { n _ { k } } ) \leq d ( x , x _ { n _ { k } } )$ ， thus $\begin{array} { r } { \operatorname* { l i m } _ { k \to \infty } d ( x , C _ { n _ { k } } ) = 0 } \end{array}$ ：

Conversely, assume that there is a subsequence $\big \{ C _ { n _ { k } } \big \}$ of $\left\{ C _ { n } \right\}$ such that $\begin{array} { r } { \operatorname* { l i m } _ { k \to \infty } d ( x , C _ { n _ { k } } ) = 0 } \end{array}$ .For each $k = 1 , 2 , \ldots$ ， we can choose an $x _ { n _ { k } }$ in $C _ { n _ { k } }$ such that $d ( x , x _ { n _ { k } } ) \leq d ( x , C _ { n _ { k } } ) + 1 / k$ .Hence $\begin{array} { r } { \operatorname* { l i m } _ { k \to \infty } d ( x , x _ { n _ { k } } ) = 0 } \end{array}$ So $x \in \operatorname* { l i m } \operatorname* { s u p } _ { n \to \infty } C _ { n }$ ．

Theorem 3.3. (Theorem 5.19 in [6]) Let u be a fuzzy set in $F _ { U S C G } ^ { 1 } ( X )$ and let $u _ { n }$ ， $n = 1 , 2 , \ldots$ ， be fuzzy sets in $F _ { U S C } ^ { 1 } ( X )$ . Then the following are equivalent:

(i) $H _ { \mathrm { e n d } } ( u _ { n } , u )  0$ ：   
(ii) ${ \cal H } ( [ u _ { n } ] _ { \alpha } , [ u ] _ { \alpha } )  0$ holds a.e. on $\alpha \in ( 0 , 1 )$ ：，   
(iii) ${ \cal H } ( [ u _ { n } ] _ { \alpha } , [ u ] _ { \alpha } )  0$ for all $\alpha \in ( 0 , 1 ) \setminus P _ { 0 } ( u )$ ：，   
(iv) There is a dense subset $P$ of $( 0 , 1 ) \backslash P _ { 0 } ( u )$ such that ${ \cal H } ( [ u _ { n } ] _ { \alpha } , [ u ] _ { \alpha } )  0$ for $\alpha \in P$ ：，   
(v) There is a countable dense subset $P$ of $( 0 , 1 ) \backslash P _ { 0 } ( u )$ such that $H ( [ u _ { n } ] _ { \alpha } , [ u ] _ { \alpha } ) $ 0 for $\alpha \in P$ ：

Theorem 3.4. (Theorem 6.2 in $[ 5 ] \big >$ Let $u$ ， $u _ { n }$ ， $n = 1 , 2 , \ldots$ . be fuzzy sets in $F _ { U S C } ( \mathbb { R } ^ { m } )$ . Then the following are equivalent:

$\begin{array} { r } { \operatorname* { l i m } _ { n  \infty } ^ { ( \Gamma ) } u _ { n } = u ; } \end{array}$ .   
(i) $\mathrm { l i m } _ { n  \infty } ^ { ( K ) } [ u _ { n } ] _ { \alpha } = [ u ] _ { \alpha }$ holds a.e. on $\alpha \in ( 0 , 1 )$ ，   
(ii) $\begin{array} { r } { \operatorname* { l i m } _ { n  \infty } ^ { ( K ) } [ u _ { n } ] _ { \alpha } = [ u ] _ { \alpha } } \end{array}$ holds for all $\alpha \in ( 0 , 1 ) \setminus P ( u )$ ：，   
(iv) There is a dense subset $P$ of $( 0 , 1 ) \backslash P ( u )$ such that $\mathrm { l i m } _ { n  \infty } ^ { ( K ) } [ u _ { n } ] _ { \alpha } = [ u ] _ { \alpha }$ （20 holds for $\alpha \in P$ ：，   
(v) There is a countable dense subset $P$ of $( 0 , 1 ) \backslash P ( u )$ such that $\begin{array} { r } { \operatorname* { l i m } _ { n \to \infty } [ u _ { n } ] _ { \alpha } = } \end{array}$ $[ u ] _ { \alpha }$ holds for $\alpha \in P$

Proposition 3.5. Let $C$ be a nonempty compact set in $\mathbb { R } ^ { m }$ and for $n =$ $1 , 2 , \ldots$ let $C _ { n }$ be a nonempty connected and closed set in $\mathbb { R } ^ { m }$ . Then $H ( C _ { n } , C ) \to$ O if and only if $\operatorname* { l i m } _ { n \to \infty } ^ { ( K ) } C _ { n } = C$ ：

Proof. From Theorem 3.1, we have that $H ( C _ { n } , C ) \to 0 \Rightarrow \operatorname* { l i m } _ { n \to \infty } ^ { ( K ) } C _ { n } = C$ Now we show that $\mathrm { l i m } _ { n \to \infty } ^ { ( K ) } C _ { n } = C \Rightarrow H ( C _ { n } , C ) \to 0$ .We prove by contradiction. Assume that $\begin{array} { r } { \operatorname* { l i m } _ { n \to \infty } ^ { ( K ) } C _ { n } ~ = ~ C } \end{array}$ but $H ( C _ { n } , C ) \ \not \to \ 0$ Then $H ^ { * } ( C , C _ { n } ) \not \to 0$ or $H ^ { * } ( C _ { n } , C ) \not \to 0$ . We split the proof into two cases.

Case (i) $H ^ { * } ( C , C _ { n } ) \not \to 0$

In this case, there is an $\varepsilon > 0$ and a subsequence $\big \{ C _ { n _ { k } } \big \}$ of $\{ C _ { n } \}$ such that $H ^ { * } ( C , C _ { n _ { k } } ) > \varepsilon$ . Thus for each $k = 1 , 2 , \ldots$ there exists $x _ { k } \in C$ such that （204号 $d ( x _ { k } , C _ { n _ { k } } ) > \varepsilon$ .Since $C$ is compact，there is a subsequence $\{ x _ { k _ { l } } \}$ of $\{ x _ { k } \}$ （204号 which converges to $x \in C$ . Then there is a $L ( \varepsilon )$ such that $d ( x , x _ { k _ { l } } ) < \varepsilon / 2$ for all $l \geq L$ .Hence $d ( x , C _ { n _ { k _ { l } } } ) \geq d ( x _ { k _ { l } } , C _ { n _ { k _ { l } } } ) - d ( x , x _ { k _ { l } } ) > \varepsilon / 2$ .By Lemma 3.2 (i), this contradicts $x \in C = \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } C _ { n }$ ：

Case (ii) $H ^ { * } ( C _ { n } , C ) \not \to 0$

In this case, there is an $\varepsilon > 0$ and a subsequence $\big \{ C _ { n _ { k } } \big \}$ of $\{ C _ { n } \}$ such that $H ^ { * } ( C _ { n _ { k } } , C ) > \varepsilon$ . Thus we have the following:

(a) for each $k = 1 , 2 , \ldots$ there exists $x _ { n _ { k } } \in C _ { n _ { k } }$ such that $d ( x _ { n _ { k } } , C ) > \varepsilon$ ：

Pick $y \in C$ ， since $C = \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } C _ { n }$ , we can find a sequence $\left\{ y _ { n } \right\}$ satisfying that $y _ { n } \in C _ { n }$ for $n = 1 , 2 , \ldots$ and $\left\{ y _ { n } \right\}$ converges to $y$ . Hence there is a $N ( \varepsilon )$ such that for all $n \geq N$ ， $d ( y _ { n } , y ) < \varepsilon$ . Since $d ( y _ { n } , C ) \leq d ( y _ { n } , y )$ ，we have the following:

(b) for all $n \geq N$ ， $d ( y _ { n } , C ) < \varepsilon$

Let $k \in \mathbb N$ with $n _ { k } \ \geq \ N$ . Define a function $f _ { k }$ from $C _ { n _ { k } }$ to $\mathbb { R }$ given by $f _ { k } ( z ) = d ( z , C )$ for each $z \in C _ { n _ { k } }$ . Then $f _ { k }$ is a continuous function on $C _ { n _ { k } }$ .Since $C _ { n _ { k } }$ is a connected set in $\mathbb { R } ^ { m }$ ， $f _ { k } ( C _ { n _ { k } } )$ is a connected set in $\mathbb { R }$ ： Combined this fact with the above clauses (a) and (b),we obtain that there exists $z _ { n _ { k } } \in C _ { n _ { k } }$ such that

$$
d ( z _ { n _ { k } } , C ) = \varepsilon .
$$

From (1) and the compactness of $C$ , the set $\{ z _ { n _ { k } } , n _ { k } \geq N \}$ is bounded in $\mathbb { R } ^ { m }$ and thus $\{ z _ { n _ { k } } , n _ { k } \geq N \}$ has a cluster point $z$ .By (1), $d ( z , C ) = \varepsilon$ ，which contradicts $z \in \operatorname* { l i m } \operatorname* { s u p } _ { n \to \infty } C _ { n } = C$ ：

Remark 3.6. Proposition 3.5 may be known， however we can't find this conclusion in the references that we can obtain. So we give a proof here.

Let $A$ be a nonempty compact set in $\mathbb { R } ^ { m }$ and $B$ a nonempty closed set in （204号 $\mathbb { R } ^ { m }$ .If $H ( A , B ) < + \infty$ ， then $B$ is bounded and hence a compact set in $\mathbb { R } ^ { m }$ ： Clearly, if $B$ is compact in $\mathbb { R } ^ { m }$ ，then $H ( A , B ) < + \infty$ . So $H ( A , B ) < + \infty$ if and only if $B$ is a compact set in $\mathbb { R } ^ { m }$ ：

From the above fact we know that for $C$ and $C _ { n }$ ， $n = 1 , 2 , \ldots$ ， satisfying the assumptions of Proposition 3.5，if $H ( C _ { n } , C ) \to 0$ (by Proposition 3.5 $H ( C _ { n } , C ) \to 0$ if and only if $\operatorname* { l i m } _ { n \to \infty } ^ { ( K ) } C _ { n } = C )$ , then clearly there is an $N \in \mathbb N$ such that for all $n \geq N$ ， $H ( C _ { n } , C ) < + \infty$ and thus for all $n \geq N$ ， $C _ { n }$ is compact.

The following Proposition 3.7 is an immediate consequence of Proposition 3.5, Theorem 3.3, and Corollary 3.4.

Theorem 3.7. Let u be a fuzzy set in $F _ { U S C G } ^ { 1 } ( \mathbb { R } ^ { m } )$ and for $n = 1 , 2 , \ldots$ ,let $u _ { n }$ be a fuzzy set in $F _ { U S C C O N } ^ { 1 } ( \mathbb { R } ^ { m } )$ . Then $H _ { \mathrm { e n d } } ( u _ { n } , u )  0$ as $n \to \infty$ if and only if $\begin{array} { r } { \operatorname* { l i m } _ { n  \infty } ^ { ( \Gamma ) } u _ { n } = u } \end{array}$ .

Proof. The proof is routine.

By let $X = \mathbb { R } ^ { m }$ in Theorem 3.3 we have the following: (i) $H _ { \mathrm { e n d } } ( u _ { n } , u )  0$ if and only if ${ \cal H } ( [ u _ { n } ] _ { \alpha } , [ u ] _ { \alpha } )  0$ holds a.e. on $\alpha \in ( 0 , 1 )$ By Theorem 3.4, we have the following: (ii) lim(T) $\operatorname* { l i m } _ { n \to \infty } ^ { ( \Gamma ) } u _ { n } = u$ if and only if $[ u ] _ { \alpha } = \operatorname* { l i m } _ { n \to \infty } ^ { ( K ) } [ u _ { n } ] _ { \alpha }$ holds a.e. on $\alpha \in ( 0 , 1 )$ ： Since for each $\alpha \in ( 0 , 1 ]$ and $n \in \mathbb { N }$ ， $[ u ] _ { \alpha } \in \ K ( \mathbb { R } ^ { m } )$ ， $[ u _ { n } ] _ { \alpha } \in \ C ( \mathbb { R } ^ { m } )$ and $[ u _ { n } ] _ { \alpha }$ is connected in $\mathbb { R } ^ { m }$ . Thus by Proposition 3.5, for each $\alpha \in ( 0 , 1 ]$ ， （204号 $H ( [ u _ { n } ] _ { \alpha } , [ u ] _ { \alpha } )  0$ if and only if $[ u ] _ { \alpha } = \operatorname* { l i m } _ { n \to \infty } ^ { ( K ) } [ u _ { n } ] _ { \alpha }$ .Combined this fact with the above clauses (i) and (ii),we have that $H _ { \mathrm { e n d } } ( u _ { n } , u )  0$ if and only if lim𝑛 n = u.

Remark 3.8. Theorem 3.7 would be false if $\mathbb { R } ^ { m }$ were replaced by a general metric space $X$ ：

Here we mention that for $u \in F _ { U S C G } ^ { 1 } ( \mathbb { R } )$ and a sequence $\{ u _ { n } \}$ m $F _ { U S C C O N } ^ { 1 } ( \mathbb { R } )$ $H ( u _ { n } , u ) \to 0$ does not imply that there is an $N$ satisfying that for all $n \geq N$ $u _ { n } \in F _ { U S C G C O N } ^ { 1 } ( \mathbb { R } )$ ：

The following Example 3.9 is a such example,which shows that there exists a $u \in F _ { U S C G } ^ { 1 } ( \mathbb { R } )$ and a sequence $\{ u _ { n } \}$ in $F _ { U S C C O N } ^ { 1 } ( \mathbb { R } )$ such that (i) $H ( u _ { n } , u )  0$ ， (ii) for each $n = 1 , 2 , \ldots$ ， $u _ { n } \notin F _ { U S C G C O N } ^ { 1 } ( \mathbb { R } ) .$ （204号

Example 3.9. Let $u = \widehat { 1 } _ { F ( \mathbb { R } ) } \in F _ { U C C G } ^ { 1 } ( \mathbb { R } )$ For $n = 1 , 2 , \ldots$ ， define $u _ { n } \in$ $F _ { U S C } ^ { 1 } ( \mathbb { R } )$ as follows:

$$
u _ { n } ( t ) = { \left\{ \begin{array} { l l } { 1 , } & { t = 1 , } \\ { 1 / n , } & { t \neq 1 . } \end{array} \right. }
$$

Then for $n = 1 , 2 , \ldots$

$$
[ u _ { n } ] _ { \alpha } = \left\{ \begin{array} { l l } { \{ 1 \} , } & { \alpha \in ( 1 / n , 1 ] , } \\ { \mathbb { R } , } & { \alpha \in [ 0 , 1 / n ] . } \end{array} \right.
$$

So for each $n = 1 , 2 , \ldots$ ， $u _ { n } \in F _ { U S C C O N } ^ { 1 } ( \mathbb { R } )$ but $u _ { n } \notin F _ { U S C G C O N } ^ { 1 } ( \mathbb { R } )$ . It can be seen that $H _ { \mathrm { e n d } } ( u , u _ { n } ) = 1 / n \to 0$ ：

Theorem 9.2 in [5] discusses the compatibility of the endograph metric $H _ { \mathrm { e n d } }$ and the $\Gamma$ -convergence.

Theorem 3.10. (Theorem 9.2 in $[ 5 ] )$ Let u be a fuzzy set in $F _ { U S C G } ( \mathbb { R } ^ { m } ) \backslash$ $\left\{ \varnothing _ { F ( \mathbb { R } ^ { m } ) } \right\}$ and for $n = 1 , 2 , \ldots$ ，let $u _ { n }$ be a fuzzy set in $F _ { U S C G C O N } ( \mathbb { R } ^ { m } )$ . Then $H _ { \mathrm { e n d } } ( u _ { n } , u )  0$ as $n \to \infty$ if and only if $\operatorname* { l i m } _ { n \to \infty } ^ { ( \Gamma ) } u _ { n } = u$

The following Corollary 3.11 is an immediate corollary of Theorem 9.2 in [5].

Corollary 3.11. Let u be a fuzzy set in $F _ { U S C G } ^ { 1 } ( \mathbb { R } ^ { m } )$ and for $n = 1 , 2 , \ldots$ $u _ { n }$ me f $F _ { U S C G C O N } ^ { 1 } ( \mathbb { R } ^ { m } )$ Then $H _ { \mathrm { e n d } } ( u _ { n } , u )  0$ 18s $n \to \infty$ 诉祎 $\operatorname* { l i m } _ { n \to \infty } ^ { ( \Gamma ) } u _ { n } = u$

We can see that Theorem 3.7 is an improvement of Corollary 3.11.

Corollary 3.11 is the normal fuzzy set case of Theorem 9.2 in [5], which is an important special case of Theorem 9.2 in [5].

In the following,we give an improvement of Theorem 9.2 in [5].

For a subset $S$ in $( X \times [ 0 , 1 ] , { \overline { { d } } } )$ , we still use $\overline { { d } }$ to denote the induced metric on $S$ by $\overline { { d } }$ ：

For a set $S$ in $X$ ， we use $\overline { S }$ to denote the topological closure of $S$ in $( X , d )$ for a set $S$ in $X \times [ 0 , 1 ]$ ，we use $\overline { S }$ to denote the topological closure of $S$ in （204号 $( X \times [ 0 , 1 ] , { \overline { { d } } } )$ . The readers can judge the meaning of $\overline { { S } }$ according to the context.

For $D \subseteq X \times [ 0 , 1 ]$ and $\alpha \in \lfloor 0 , 1 \rfloor$ ， define $D _ { \alpha } : = \{ x \in X : ( x , \alpha ) \in D \}$ For a nonempty set $D$ in $X \times \lfloor 0 , 1 \rfloor$ ， define $f _ { D } : = \operatorname* { i n f } \{ \alpha : ( x , \alpha ) \in D \}$ and$S _ { D } : = \operatorname* { s u p } \{ \alpha : ( x , \alpha ) \in D \}$

Proposition 3.12. Let $D$ be a nonempty set in $X \times [ 0 , 1 ]$ with $D _ { r } \subseteq D _ { t }$ for $f _ { D } \leq t \leq r \leq 1$ . Then $D _ { f _ { D } }$ is connected in $( X , d )$ if and only if $D$ is connected in $( X \times [ 0 , 1 ] , { \overline { { d } } } )$ ：

Proof. Sufficiency. We proceed by contradiction. Assume that $D _ { f _ { D } }$ is connected in $X$ .If $D$ is not connected in $X \times \lfloor 0 , 1 \rfloor$ ， then there exists two nonempty sets $A$ and $B$ in $X \times [ 0 , 1 ]$ such that $A \cup B = D$ ， $A \cap { \overline { { B } } } = \varnothing$ and $B \cap { \overline { { A } } } = \varnothing$

Note that $D _ { f _ { D } } \times \{ f _ { D } \} \subseteq D$ and $D _ { f _ { D } } \times \{ f _ { D } \}$ is connected. Hence $D _ { f _ { D } } \times$ $\{ f _ { D } \} \subseteq A$ or $D _ { f _ { D } } \times \{ f _ { D } \} \subseteq B$ . Without loss of generality, we suppose that $D _ { f _ { D } } \times \{ f _ { D } \} \subseteq A$ ：

Pick $( x , \alpha ) \in B$ . Set $\gamma = \operatorname* { i n f } \{ \beta : ( x , \beta ) \in B \}$ 4

If $( x , \gamma ) \in B$ , we affirm that $\gamma > f _ { D }$ . Otherwise $\gamma = f _ { D }$ and $( x , f _ { D } ) \in B$ Note that $( x , f _ { D } ) \in A$ . Thus $A \cap B \neq \emptyset$ ，which is a contradiction. Hence $( x , \xi ) \in A$ for $\xi \in [ f _ { D } , \gamma )$ ，and therefore $\begin{array} { r } { ( x , \gamma ) = \operatorname* { l i m } _ { \xi  \gamma - } ( x , \xi ) \in \overline { { A } } } \end{array}$ So $\overline { { A } } \cap B \neq \varnothing$ . This is a contradiction.

班 $( x , \gamma ) \in A$ , then there is a sequence $\{ ( x , \gamma _ { n } ) \}$ in $B$ such that $\scriptstyle \operatorname* { l i m } _ { n \to \infty } \gamma _ { n } =$ $\gamma$ . Hence $\begin{array} { r } { ( x , \gamma ) = \operatorname* { l i m } _ { n  \infty } ( x , \gamma _ { n } ) \in \overline { { B } } } \end{array}$ . Thus $A \cap { \overline { { B } } } \neq \emptyset$ . This is a contradiction.

Necessity. Assume that $D$ is connected in $X \times [ 0 , 1 ]$ . Define a function $f : ( D , \overline { { d } } )  ( D _ { f _ { D } } , d )$ given by $f ( x , \alpha ) = x$ for each $( x , \alpha ) \in D$ .Clearly for $( x , \alpha ) , ( y , \beta ) \in X \times [ 0 , 1 ]$ ， $d ( f ( x , \alpha ) , f ( y , \beta ) ) = d ( x , y ) \leq \bar { d } ( ( x , \alpha ) , ( y , \beta ) )$ （ Then $f$ is continuous and hence $D _ { f _ { D } } = f ( D )$ is connected in $X$ ：

Corollary 3.13. Let $E$ be a nonempty set in $X \times [ 0 , 1 ]$ with $E _ { r } \supseteq E _ { t }$ for （204号 $0 \leq t \leq r \leq S _ { E }$ . Then $E _ { S _ { E } }$ is connected in $( X , d )$ if and only if $E$ is connected in $( X \times [ 0 , 1 ] , { \overline { { d } } } )$

Proof. Let $D = \{ ( x , 1 - \alpha ) : ( x , \alpha ) \in E \}$ . Then $D$ is a nonempty set in $X \times [ 0 , 1 ]$ with $D _ { r } \subseteq D _ { t }$ for $f _ { D } \leq t \leq r \leq 1$ . Hence by Proposition 3.12, $D _ { f _ { D } }$ is connected in $( X , d )$ if and only if $D$ is connected in $( X \times [ 0 , 1 ] , { \overline { { d } } } )$

Define $f : ( E , d )  ( D , d )$ as follows: $f ( x , \alpha ) = ( x , 1 - \alpha )$ for $( x , \alpha ) \in E$

Observe that $E _ { S _ { E } } = D _ { f _ { D } }$ ， so to verify the desired result it suffices to show that $D$ is connected in $( X \times [ 0 , 1 ] , { \overline { { d } } } )$ if and only if $E$ is connected in $( X \times [ 0 , 1 ] , { \overline { { d } } } )$ ，which follows from that $f$ is an isometry and $f ( E ) = D$

The desired conclusion can also be proved in a similar manner as that of Proposition 3.12.

We use $d _ { m }$ to denote the Euclidean metric on $\mathbb { R } ^ { m }$ . We also use $\mathbb { R } ^ { m } \times [ 0 , 1 ]$ to denote the metric space ( $\mathbb { R } ^ { m } \times [ 0 , 1 ] , \overline { { d _ { m } } } )$ ： $\mathbb { R } ^ { 1 }$ is written as $\mathbb { R }$

Remark 3.14. Here we mention that $D _ { S _ { D } } = \varnothing$ is possible when $D$ is connected in $X \times [ 0 , 1 ]$ and satisfies the assumption in Proposition 3.12. Let $X = \mathbb { R }$ and define $D \subset \mathbb { R } \times [ 0 , 1 ]$ by putting

$$
D _ { \alpha } = \left\{ \begin{array} { l l } { \varnothing , } & { \alpha = 1 , } \\ { ( 0 , 1 - \alpha ] , } & { \alpha \in [ 0 , 1 ) . } \end{array} \right.
$$

Then $D$ is a such example

Similarly, $E _ { f _ { E } } ~ = ~ \emptyset$ is possible when $E$ is connected in $X \times \lfloor 0 , 1 \rfloor$ and satisfies the assumption in Corollary 3.13.

Let $u \in F ( X )$ and $0 \leq r \leq t \leq 1$ . Define $\operatorname { e n d } _ { r } ^ { t } u$ given by

$$
\operatorname { e n d } _ { r } ^ { t } u : = \operatorname { e n d } u \cap ( [ u ] _ { r } \times [ r , t ] ) .
$$

For simplicity, we write $\operatorname { e n d } _ { r } ^ { 1 } u$ as $\operatorname { e n d } _ { r } u$ . We can see that $\operatorname { e n d } _ { 0 } u = \operatorname { s e n d } u$

Clearly, for $u \in F _ { U S C G } ( X )$ and $r \in \mathbf { \Sigma } ( 0 , 1 ]$ ， $\operatorname { e n d } _ { r } u$ is a compact set in$X \times [ 0 , 1 ]$ ：

Corollary 3.15. Let $u \in F ( X )$

(i) For $r , t$ with $0 \leq r \leq t \leq 1$ ， $\operatorname { e n d } _ { r } ^ { t } u$ is connected in $X \times [ 0 , 1 ]$ if and only if $[ u ] _ { r }$ is connected in $X$ ： (ii) $X$ is connected if and only if end $u$ is connected in $X \times \lfloor 0 , 1 \rfloor$

Proof. If $\mathrm { e n d } _ { r } ^ { t } u \neq \varnothing$ , then, by Proposition 3.12, the conclusion in (i) is true. Thus it suffices to consider the case when $\operatorname { e n d } _ { r } ^ { t } u = \varnothing$ . In this case, $[ u ] _ { r } = \emptyset$ ， and so clearly the conclusion in (i) is true.

Note that $f _ { \mathrm { e n d } u } = 0$ and $( \mathrm { e n d } u ) _ { 0 } = X$ . So (ii) follows immediately from Proposition 3.12.

The following Examples 3.16 and 3.17 give some connected sets in $\mathbb { R } \times$ $\lfloor 0 , 1 \rfloor$ . Proposition 3.12, Corollary 3.13 and Corollary 3.15 are used to show the connectedness of these sets.

Example 3.16. Let $D \subset \mathbb { R } \times [ 0 , 1 ]$ be defined by putting

$$
D _ { \alpha } = \left\{ \begin{array} { l l } { [ 1 - \alpha ^ { 2 } , 1 ] \cup [ 3 , 4 - \alpha ^ { 2 } ] , } & { \alpha \in ( 0 . 5 , 1 ] , } \\ { [ 0 , 4 ] , } & { \alpha \in [ 0 , 0 . 5 ] . } \end{array} \right.
$$

We can see that $D = A \cup B \cup C$ ，where

$$
\begin{array} { c } { { A = [ 0 , 4 ] \times [ 0 , 0 . 5 ] , } } \\ { { B = \displaystyle { \bigcup _ { \alpha \in [ 0 . 5 , 1 ] } [ 1 - \alpha ^ { 2 } , 1 ] \times \{ \alpha \} } , } } \\ { { C = \displaystyle { \bigcup _ { \alpha \in [ 0 . 5 , 1 ] } [ 3 , 4 - \alpha ^ { 2 } ] \times \{ \alpha \} } . } } \end{array}
$$

Clearly $A$ is connected in $\mathbb { R } \times [ 0 , 1 ]$ .By Corollary 3.13, $B$ is connected in （204号 $\mathbb { R } \times [ 0 , 1 ]$ . By Proposition 3.12, $C$ is connected in $\mathbb { R } \times [ 0 , 1 ]$ ： $A \cap B =$ $[ 1 - 0 . 5 ^ { 2 } , 1 ] \times \{ 0 . 5 \} \ne \emptyset$ ， $A \cap C = [ 3 , 4 - 0 . 5 ^ { 2 } ] \times \{ 0 . 5 \} \neq \emptyset$ . Thus $D$ is connected in $\mathbb { R } \times [ 0 , 1 ]$

Here we mention that there is no $u \in F ( \mathbb { R } )$ satisfying $D = \mathrm { s e n d } u$ because $D _ { 1 } \nsubseteq D _ { 0 . 9 }$

Example 3.17. Let $u \in F _ { U S C } ^ { 1 } ( \mathbb { R } )$ be defined by putting:

$$
[ u ] _ { \alpha } = \left\{ \begin{array} { l l } { [ 0 , 1 ] \cup [ 3 , 4 ] , } & { \alpha \in ( 0 . 6 , 1 ] , } \\ { [ 0 , 4 ] , } & { \alpha \in [ 0 , 0 . 6 ] . } \end{array} \right.
$$

We can see that $[ 0 , 1 ] \cup [ 3 , 4 ]$ is not connected, [0,4] and $\mathbb { R }$ are connected. So $u \in F _ { U S C } ^ { 1 } ( \mathbb { R } ) \setminus F _ { U S C C O N } ( \mathbb { R } )$ .By Corollary 3.15, $\mathrm { e n d } u$ is connected in $\mathbb { R } \times [ 0 , 1 ]$ ：， $\operatorname { e n d } _ { r } u$ is connected in $\mathbb { R } \times [ 0 , 1 ]$ if and only if $r \in [ 0 , 0 . 6 ]$ ：

We say that a sequence $\{ u _ { n } , n = 1 , 2 , . . . \}$ in $F _ { U S C } ( \mathbb { R } ^ { m } )$ satisfies connectedness condition if for each $\varepsilon > 0$ ，there is a $\delta \in ( 0 , \varepsilon ]$ and $N ( \varepsilon ) \in \mathbb { N }$ such that for all $n \geq N$ ， $\mathrm { e n d } _ { \delta } u _ { n }$ is connected in $\mathbb { R } ^ { m } \times [ 0 , 1 ]$ ：

We will use the following conclusion

Let $( Y , \rho )$ be a metric space, $x , y \in Y$ and $W \subseteq Y$ . Then

$$
\begin{array} { l } { \rho ( x , W ) = \displaystyle \operatorname* { i n f } _ { z \in W } \rho ( x , z ) } \\ { \displaystyle \quad \leq \displaystyle \operatorname* { i n f } _ { z \in W } \{ \rho ( x , y ) + \rho ( y , z ) \} } \\ { \displaystyle = \rho ( x , y ) + \rho ( y , W ) . } \end{array}
$$

Theorem 3.18. Let $u \in F _ { U S C G } ( \mathbb { R } ^ { m } ) \backslash \left\{ \emptyset _ { F ( \mathbb { R } ^ { m } ) } \right\}$ ，and let $\{ u _ { n } , n = 1 , 2 , . . . \}$ be a fuzzy set sequence in $F _ { U S C } ( \mathbb { R } ^ { m } )$ which satisfies the connectedness condition. Then $H _ { \mathrm { e n d } } ( u _ { n } , u )  0$ as $n \to \infty$ if and only if $\operatorname* { l i m } _ { n \to \infty } ^ { ( \Gamma ) } u _ { n } = u$

Proof. From Theorem 3.1, $H _ { \mathrm { e n d } } ( u _ { n } , u )  0 \Rightarrow \operatorname* { l i m } _ { n  \infty } ^ { ( \Gamma ) } u _ { n } = u .$ （204号

Now we show that $\mathrm { l i m } _ { n \to \infty } ^ { ( \Gamma ) } u _ { n } = u \Rightarrow H _ { \mathrm { e n d } } ( u _ { n } , u ) \to 0$ We prove by contradiction. Assume that ∞Un = u but Hend(un,u) A O. Then $H ^ { * } ( \mathrm { e n d } u , \mathrm { e n d } u _ { n } ) \not \to 0$ or $H ^ { * } ( \mathrm { e n d } u _ { n } , \mathrm { e n d } u ) \not \to 0$ . We split the proof into two cases.

Case (i) $H ^ { * } ( \mathrm { e n d } u , \mathrm { e n d } u _ { n } ) \not \to 0$

In this case, there is an $\varepsilon > 0$ and a subsequence $\{ u _ { n _ { k } } \}$ of $\{ u _ { n } \}$ such that $H ^ { * } ( \mathrm { e n d } u , \mathrm { e n d } u _ { n _ { k } } ) > \varepsilon$ .Thus for each $k = 1 , 2 , \ldots$ there exists $( x _ { k } , \alpha _ { k } ) \in$ $\operatorname { e n d } u$ such that $\overline { { d _ { m } } } ( ( x _ { k } , \alpha _ { k } ) , \mathrm { e n d } u _ { n _ { k } } ) > \varepsilon$ . Note that for each $k = 1 , 2 , \ldots$ （204号 （204号 $\alpha _ { k } > \varepsilon$ . So $\{ ( x _ { k } , \alpha _ { k } ) , \ k = 1 , 2 , \ldots \} \subseteq { \mathrm { e n d } } _ { \varepsilon } u$

Since $\operatorname { e n d } _ { \varepsilon } u$ is compact, there is a subsequence $\{ ( x _ { k _ { l } } , \alpha _ { k _ { l } } ) \}$ of $\{ ( x _ { k } , \alpha _ { k } ) \}$ which converges to $( x , \alpha ) \in { \mathrm { e n d } } _ { \varepsilon } u \subset { \mathrm { e n d } } u$ . Then there is a $L ( \varepsilon )$ such that （20 $\overline { { d _ { m } } } ( ( x , \alpha ) , ( x _ { k _ { l } } , \alpha _ { k _ { l } } ) ) < \varepsilon / 2$ for all $l \geq L$ . Hence,by (2), $\overline { { d _ { m } } } ( ( x , \alpha ) , \mathrm { e n d } u _ { n _ { k _ { l } } } ) \geq$ $\overline { { d _ { m } } } ( ( x _ { k _ { l } } , \alpha _ { k _ { l } } ) , \mathrm { e n d } u _ { n _ { k _ { l } } } ) - \overline { { d _ { m } } } ( ( x , \alpha ) , ( x _ { k _ { l } } , \alpha _ { k _ { l } } ) ) > \varepsilon / 2$ . By Lemma 3.2 (i), this contradicts $( x , \alpha ) \in { \mathrm { e n d } } u = \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } { \mathrm { e n d } } u _ { n } .$

Case (ii) $H ^ { * } ( \mathrm { e n d } u _ { n } , \mathrm { e n d } u ) \not \to 0$

In this case, there is an $\varepsilon > 0$ and a subsequence $\{ u _ { n _ { k } } \}$ of $\{ u _ { n } \}$ such that

$$
H ^ { * } ( \mathrm { e n d } u _ { n _ { k } } , \mathrm { e n d } u ) > \varepsilon .
$$

Take $y \in \mathbb { R } ^ { m }$ with $u ( y ) > 0$ ．Set $\mu = u ( y )$ .Since $\left\{ u _ { n } \right\}$ satisfies the connectedness condition, there is a $\xi \in ( 0 , \operatorname* { m i n } \{ \mu , \varepsilon \} )$ and $N _ { 1 } \in \mathbb { N }$ such that $\mathrm { e n d } _ { \xi } u _ { n }$ is connected in $\mathbb { R } ^ { m } \times [ 0 , 1 ]$ for all $n \geq N _ { 1 }$ ：

Firstly we show the conclusions in the following clauses (I),(II) and (III).

(I) For each $n _ { k }$ ， $k = 1 , 2 , \ldots$ , there exists $( x _ { n _ { k } } , \alpha _ { n _ { k } } ) \in { \mathrm { e n d } } _ { \xi } u _ { n _ { k } }$ with $\overline { { d _ { m } } } ( ( x _ { n _ { k } } , \alpha _ { n _ { k } } ) , \mathrm { e n d } _ { \xi } u ) >$ （204号 $\xi$ ：   
(II) There is an $N _ { 2 } \in \mathbb { N }$ such that for each $n \geq N _ { 2 }$ ， there exists $( y _ { n } , \beta _ { n } ) \in$ （20 $\operatorname { e n d } _ { \xi } u _ { n }$ with $d _ { m } ( ( y _ { n } , \beta _ { n } ) , { \mathrm { e n d } } _ { \xi } u ) < \xi$ .   
(III) Set $N _ { 3 } : = \operatorname* { m a x } \{ N _ { 1 } , N _ { 2 } \}$ . For each $n _ { k } \ge N _ { 3 }$ , there exists $( z _ { n _ { k } } , \gamma _ { n _ { k } } ) \in$ （204号 （204号 $\operatorname { e n d } _ { \xi } u _ { n _ { k } }$ such that

$$
\overline { { d _ { m } } } ( ( z _ { n _ { k } } , \gamma _ { n _ { k } } ) , \mathrm { e n d } _ { \xi } u ) = \xi .
$$

To show (I), let $k \in \mathbb N$ . From (3), there exists $( x _ { n _ { k } } , \alpha _ { n _ { k } } ) \in { \mathrm { e n d } } u _ { n _ { k } }$ such that

$$
\overline { { d _ { m } } } ( ( x _ { n _ { k } } , \alpha _ { n _ { k } } ) , \mathrm { e n d } _ { \xi } u ) \geq \overline { { d _ { m } } } ( ( x _ { n _ { k } } , \alpha _ { n _ { k } } ) , \mathrm { e n d } u ) > \varepsilon > \xi .
$$

Clearly $\alpha _ { n _ { k } } > \varepsilon$ , and then $( x _ { n _ { k } } , \alpha _ { n _ { k } } ) \in \mathrm { e n d } _ { \varepsilon } u _ { n _ { k } } \subset \mathrm { e n d } _ { \xi } u _ { n _ { k } }$ . Thus (I) is true.

As $( y , \mu ) \in \mathrm { e n d } u$ and end $u = \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty }$ end $u _ { n }$ ， we can find a sequence $\left\{ \left( y _ { n } , \beta _ { n } \right) \right\}$ satisfying that $( y _ { n } , \beta _ { n } ) \in { \mathrm { ~ e n d } } u _ { n }$ for $n = 1 , 2 , \ldots$ and $\left\{ \left( y _ { n } , \beta _ { n } \right) \right\}$ converges to $( y , \mu )$

Hence there is a $N _ { 2 }$ such that for all $n \geq N _ { 2 }$ ， $\overline { { { d _ { m } } } } ( ( y _ { n } , \beta _ { n } ) , ( y , \mu ) ) ~ <$ $\operatorname* { m i n } \{ \mu - \xi , \xi \}$ ．Let $n \in \mathbb { N }$ with $n \geq N _ { 2 }$ .Then $\beta _ { n } ~ > ~ \xi$ ，and therefore $( y _ { n } , \beta _ { n } ) \ \in \ \mathrm { e n d } _ { \xi } u _ { n }$ .Note that $( y , \mu ) \in \mathrm { e n d } _ { \xi } u$ So $\overline { { d _ { m } } } ( ( y _ { n } , \beta _ { n } ) , \mathrm { e n d } _ { \xi } u ) \ \leq$ $d _ { m } ( ( y _ { n } , \beta _ { n } ) , ( y , \mu ) ) < \xi$ . Thus (II) is true.

To show (III)， let $k \in \mathbb { N }$ with $n _ { k } \ \ge \ N _ { 3 }$ .Define a function $f _ { k }$ from$( \mathrm { e n d } _ { \xi } u _ { n _ { k } } , \overline { { d _ { m } } } )$ to $\mathbb { R }$ as follows:

$$
f _ { k } ( z , \zeta ) = \overline { { d _ { m } } } ( ( z , \zeta ) , \mathrm { e n d } _ { \xi } u ) \mathrm { f o r } ( z , \zeta ) \in \mathrm { e n d } _ { \xi } u _ { n _ { k } } .
$$

By (2), $| f _ { k } ( z , \zeta ) - f _ { k } ( z ^ { \prime } , \zeta ^ { \prime } ) | \leq \overline { { d _ { m } } } ( ( z , \zeta ) , ( z ^ { \prime } , \zeta ^ { \prime } ) )$ for $( z , \zeta ) , ( z ^ { \prime } , \zeta ^ { \prime } )$ in endg $u _ { n _ { k } }$ Thus $f _ { k }$ is a continuous function on $\mathrm { e n d } _ { \xi } u _ { n _ { k } }$

Note that $\mathrm { e n d } _ { \xi } u _ { n _ { k } }$ is a connected set in $\mathbb { R } ^ { m }$ .Thus $f _ { k } ( \mathrm { e n d } _ { \xi } u _ { n _ { k } } )$ isa connected set in $\mathbb { R }$ ； that is, $f _ { k } ( \mathrm { e n d } _ { \xi } u _ { n _ { k } } )$ is an interval. Combined this fact with the above clauses (I) and (II),we obtain that there exists $( z _ { n _ { k } } , \gamma _ { n _ { k } } ) \in$ $\mathrm { e n d } _ { \xi } u _ { n _ { k } }$ with $\overline { { d _ { m } } } ( ( z _ { n _ { k } } , \gamma _ { n _ { k } } ) , \mathrm { e n d } _ { \xi } u ) = \xi$ . Thus (III) is true.

Now using (II)，we can obtain a contradiction. From (4) and the compactness of $\operatorname { e n d } _ { \xi } u$ , the set $\{ ( z _ { n _ { k } } , \gamma _ { n _ { k } } ) , n _ { k } \geq N _ { 3 } \}$ is bounded in $\mathbb { R } ^ { m } \times [ 0 , 1 ]$ ,and thus $\{ ( z _ { n _ { k } } , \gamma _ { n _ { k } } ) , n _ { k } \geq N _ { 3 } \}$ has a cluster point $( z , \gamma )$ . So $( z , \gamma ) \in \operatorname* { l i m } \operatorname* { s u p } _ { n \to \infty } { \mathrm { e n d } } u _ { n } =$ end $u$ As $( z _ { n _ { k } } , \gamma _ { n _ { k } } ) \in \mathrm { e n d } _ { \xi } u _ { n _ { k } }$ ， we have that $\gamma _ { n _ { k } } \geq \xi$ and therefore $\gamma \geq \xi$ ： Thus $( z , \gamma ) \in$ end $u \cap ( X \times [ \xi , 1 ] ) = { \mathrm { e n d } } _ { \xi } u$ . But, by (4), ${ \overline { { d _ { m } } } } ( ( z , \gamma ) , { \mathrm { e n d } } _ { \xi } u ) = \xi$ ， which is a contradiction.

Corollary 3.19. Let u be a fuzzy set in $F _ { U S C G } ( \mathbb { R } ^ { m } ) \setminus \{ \emptyset _ { F ( \mathbb { R } ^ { m } ) } \}$ and for s $n = 1 , 2 , \ldots$ $n \to \infty$ if and only if ，let be a fuzzy set in $\operatorname* { l i m } _ { n \to \infty } ^ { ( \Gamma ) } u _ { n } = u$ $F _ { U S C C O N } ( \mathbb { R } ^ { m } )$ S. . Then $H _ { \mathrm { e n d } } ( u _ { n } , u )  0$ （20

Proof. Let $\{ u _ { n } : n \in \mathbb { N } \}$ is a sequence in $F _ { U S C C O N } ( \mathbb { R } ^ { m } )$ . Then，by clause (i) of Corollary 3.15, for each $n \in \mathbb { N }$ and $r \in ( 0 , 1 ]$ ， $\operatorname { e n d } _ { r } u _ { n }$ is a connected set in $\mathbb { R } ^ { m } \times [ 0 , 1 ]$ . Hence $\{ u _ { n } : n \in \mathbb { N } \}$ satisfies the connectedness condition. Thus the desired result follows immediately from Theorem 3.18.

Here we mention that for $u \in F _ { U S C G } ^ { 1 } ( \mathbb { R } )$ and a sequence $\{ u _ { n } \}$ in $F _ { U S C } ^ { 1 } ( \mathbb { R } )$ which satisfies the connectedness condition, $H ( u _ { n } , u )  0$ does not imply that there is an $N$ such that for each $n \geq N$ ， $u _ { n } \in F _ { U S C C O N } ( \mathbb { R } )$

The following Example 3.2O is a such example,which shows that there exists a $u \in F _ { U S C G } ^ { 1 } ( \mathbb { R } )$ and a sequence $\{ u _ { n } \}$ in $F _ { U S C } ^ { 1 } ( \mathbb { R } )$ such that (i) $H ( u _ { n } , u )  0$ ， (ii) $\{ u _ { n } \}$ satisfies the connectedness condition,and (iii) for each $n = 1 , 2 , \ldots$ ， $u _ { n } \notin F _ { U S C C O N } ( \mathbb { R } )$

Example 3.20. For $n = 1 , 2 , \ldots$ ，let $u _ { n }$ be the fuzzy set $u$ given in Example 3.17; that is, $u _ { n } = u$ is a fuzzy set in $F _ { U S C G } ^ { 1 } ( \mathbb { R } )$ defined by putting:

$$
[ u ] _ { \alpha } = \left\{ \begin{array} { l l } { [ 0 , 1 ] \cup [ 3 , 4 ] , } & { \alpha \in ( 0 . 6 , 1 ] , } \\ { [ 0 , 4 ] , } & { \alpha \in [ 0 , 0 . 6 ] . } \end{array} \right.
$$

We have the following conclusions:

(i) $H ( u _ { n } , u )  0$ since $u _ { n } = u$ for $n = 1 , 2 , \ldots$   
(ii) $\{ u _ { n } \}$ satisfies the connectedness condition because $\mathrm { e n d } _ { r }$ （20 $u$ is connected in $\mathbb { R } \times [ 0 , 1 ]$ when $r \in [ 0 , 0 . 6 ]$ (see Example 3.17);   
(iii) for each $n = 1 , 2 , \ldots$ ， $u _ { n } \notin \ F _ { U S C C O N } ( \mathbb { R } )$ ，as $u \notin \ F _ { U S C C O N } ( \mathbb { R } )$ (see Example 3.17).

Remark 3.21. Theorem 9.2 in [5], which is Theorem 3.10 in this paper, is a corollary of Corollary 3.19 since $F _ { U S C G C O N } ( \mathbb { R } ^ { m } ) \subseteq F _ { U S C C O N } ( \mathbb { R } ^ { m } )$

Theorem 3.7 is a corollary of Corollary 3.19, as $F _ { U S C G } ^ { 1 } ( \mathbb { R } ^ { m } ) \subseteq F _ { U S C G } ( \mathbb { R } ^ { m } ) \backslash$ $\left\{ \varnothing _ { F ( \mathbb { R } ^ { m } ) } \right\}$ and $F _ { U S C C O N } ^ { 1 } ( \mathbb { R } ^ { m } ) \subseteq F _ { U S C C O N } ( \mathbb { R } ^ { m } )$ ：

Corollary 3.19 is a corollary of Theorem 3.18.

Theorem 3.18 improves Theorem 9.2 in [5] and Theorem 3.7.

Now we give an improvement of Theorem 3.18.

Let $u \in F ( X )$ . Define $S ( u ) : = \operatorname* { s u p } \{ u ( x ) : x \in X \}$ . Clearly $[ u ] _ { S _ { u } } = \emptyset$ is possible.

Let $\{ u _ { n } \}$ be a fuzzy set sequence in $F _ { U S C } ( \mathbb { R } ^ { m } )$ and $\{ u _ { n _ { k } } \}$ a subsequence of $\{ u _ { n } \}$ . If there is a $u \in F _ { U S C G } ( \mathbb { R } ^ { m } ) \setminus \{ \emptyset _ { F ( \mathbb { R } ^ { m } ) } \}$ such that $u = \mathrm { l i m } _ { n  \infty } ^ { ( \Gamma ) } u _ { n }$ then we can define

$$
\begin{array} { r } { A _ { n _ { k } } ^ { 1 } : = \{ \xi > 0 : \mathrm { ~ f o r ~ e a c h ~ } n _ { k } , ~ H ^ { * } ( \mathrm { e n d } u , \mathrm { e n d } u _ { n _ { k } } ) > \xi \} , } \\ { A _ { n _ { k } } ^ { 2 } : = \{ \xi > 0 : \mathrm { ~ f o r ~ e a c h ~ } n _ { k } , ~ H ^ { * } ( \mathrm { e n d } u _ { n _ { k } } , \mathrm { e n d } u ) > \xi \} . } \end{array}
$$

Let $\{ u _ { n } \}$ be a fuzzy set sequence in $F _ { U S C } ( \mathbb { R } ^ { m } )$ and let $u$ be a fuzzy set in $F _ { U S C } ( \mathbb { R } ^ { m } ) \setminus \{ \emptyset _ { F ( \mathbb { R } ^ { m } ) } \}$ . We call the pair $\{ u _ { n } \}$ ， $u$ is a weak connectedness compact pair if one of the following (i) and (ii) holds: ? $\mathrm { l i m } _ { n \to \infty } ^ { ( \Gamma ) } u _ { n }$ does not exist, or $\mathrm { l i m } _ { n \to \infty } ^ { ( \Gamma ) } u _ { n }$ exists but $u = \mathrm { l i m } _ { n  \infty } ^ { ( \Gamma ) } u _ { n }$ does not hold; (ii) $u = \mathrm { l i m } _ { n  \infty } ^ { ( \Gamma ) } u _ { n }$ and (ii-1) and (ii-2)are true. (ii-1)for each $\{ u _ { n _ { k } } \}$ with $A _ { n _ { k } } ^ { 1 } \neq \varnothing$ ， there exists a $\xi \in A _ { n _ { k } } ^ { 1 }$ such that $\operatorname { e n d } _ { \xi } u$ is compact. (ii-2) for each $\{ u _ { n _ { k } } \}$ with $A _ { n _ { k } } ^ { 2 } ~ \neq ~ \varnothing$ ， there exists a $\xi \in \ A _ { n _ { k } } ^ { 2 }$ and an $N ( \xi ) \in \mathbb { N }$ such that $\xi < S ( u )$ ， $\operatorname { e n d } _ { \xi } u$ is compact， and $\mathrm { e n d } _ { \xi } u _ { n _ { k } }$ is connected in $\mathbb { R } ^ { m } \times [ 0 , 1 ]$ for all $n _ { k } \geq N$ ：

Theorem 3.22. Let $u \in F _ { U S C G } ( \mathbb { R } ^ { m } ) \backslash \left\{ \emptyset _ { F ( \mathbb { R } ^ { m } ) } \right\}$ ， and let $\{ u _ { n } , n = 1 , 2 , . . . \}$ be a fuzzy set sequence in $F _ { U S C } ( \mathbb { R } ^ { m } )$ . If the pair $\{ u _ { n } \}$ ， $u$ is a weak connectedness compact pair, then $H _ { \mathrm { e n d } } ( u _ { n } , u )  0$ as $n \to \infty$ if and only if $\operatorname* { l i m } _ { n \to \infty } ^ { ( \Gamma ) } u _ { n } = u$ ：

Proof. The proof is similar to that of Theorem 3.18.

From Theorem 3.1, $H _ { \mathrm { e n d } } ( u _ { n } , u )  0 \Rightarrow \operatorname* { l i m } _ { n  \infty } ^ { ( \Gamma ) } u _ { n } = u$

Now we show that $\mathrm { l i m } _ { n \to \infty } ^ { ( 1 ) } u _ { n } = u \Rightarrow H _ { \mathrm { e n d } } ( u _ { n } , u ) \to 0$ We prove by contradiction. Assume that T∞ Un = u but Hend(un,u) A 0. Then $H ^ { * } ( \mathrm { e n d } u , \mathrm { e n d } u _ { n } ) \not \to 0$ or $H ^ { * } ( \mathrm { e n d } u _ { n } , \mathrm { e n d } u ) \not \to 0$ . We split the proof into two cases.

Case (i) $H ^ { * } ( \mathrm { e n d } u , \mathrm { e n d } u _ { n } ) \not \to 0$

In this case, $A _ { n _ { k } } ^ { 1 } \neq \varnothing$ . Since the pair $\left\{ u _ { n } \right\}$ ， $u$ is a weak connectedness compact pair, then there is a $\xi \in A _ { n _ { k } } ^ { 1 }$ with $\operatorname { e n d } _ { \xi } u$ is compact. So we can prove that there is a contradiction in a similar manner to that in the case (i) of the proof of Theorem 3.18.

Case (ii) $H ^ { * } ( \mathrm { e n d } u _ { n } , \mathrm { e n d } u ) \not \to 0$

In this case, $A _ { n _ { k } } ^ { 2 } \neq \varnothing$ . Since the pair $\left\{ u _ { n } \right\}$ ， $u$ is a weak connectedness compact pair, there is a $\xi \in A _ { n _ { k } } ^ { 2 }$ and $N _ { 1 } \in \mathbb { N }$ such that $\xi < S ( u )$ ， $\operatorname { e n d } _ { \xi } u$ is compact,and for all $n _ { k } \geq N _ { 1 }$ ， $\mathrm { e n d } _ { \xi } u _ { n _ { k } }$ is connected in $\mathbb { R } ^ { m } \times [ 0 , 1 ]$ ：

Firstly we show the conclusions in the following clauses (I), (II) and (III).

(I) For each $n _ { k }$ ， $k = 1 , 2 , \ldots$ , there exists $( x _ { n _ { k } } , \alpha _ { n _ { k } } ) \in \mathrm { e n d } _ { \xi } u _ { n _ { k } }$ with $\overline { { d _ { m } } } ( ( x _ { n _ { k } } , \alpha _ { n _ { k } } ) , \mathrm { e n d } _ { \xi } u ) >$ （204号 $\xi$ ：   
(II) There is an $N _ { 2 } \in \mathbb { N }$ such that for each $n \geq N _ { 2 }$ , there exists $( y _ { n } , \beta _ { n } ) \in$ （20 $\operatorname { e n d } _ { \xi } u _ { n }$ with $\overline { { d _ { m } } } ( ( y _ { n } , \beta _ { n } ) , \mathrm { e n d } _ { \xi } u ) < \xi$

(III) Set $N _ { 3 } : = \operatorname* { m a x } \{ N _ { 1 } , N _ { 2 } \}$ . For each $n _ { k } \ge N _ { 3 }$ ， there exists $( z _ { n _ { k } } , \gamma _ { n _ { k } } ) \in$ （204号 $\mathrm { e n d } _ { \xi } u _ { n _ { k } }$ such that

$$
\overline { { d _ { m } } } ( ( z _ { n _ { k } } , \gamma _ { n _ { k } } ) , \mathrm { e n d } _ { \xi } u ) = \xi .
$$

Note that $\xi \in A _ { n _ { k } } ^ { 2 }$ ; that is, for each $u _ { n _ { k } }$ ， $k = 1 , 2 , \ldots$

$$
H ^ { * } ( \mathrm { e n d } u _ { n _ { k } } , \mathrm { e n d } u ) > \xi .
$$

Let $k \in \mathbb N$ . From (6), there exists $( x _ { n _ { k } } , \alpha _ { n _ { k } } ) \in { \mathrm { e n d } } u _ { n _ { k } }$ such that

$$
\overline { { d _ { m } } } ( ( x _ { n _ { k } } , \alpha _ { n _ { k } } ) , \mathrm { e n d } _ { \xi } u ) \ge \overline { { d _ { m } } } ( ( x _ { n _ { k } } , \alpha _ { n _ { k } } ) , \mathrm { e n d } u ) > \xi .
$$

Clearly $\alpha _ { n _ { k } } > \xi$ ,and then $( x _ { n _ { k } } , \alpha _ { n _ { k } } ) \in { \mathrm { e n d } } _ { \xi } u _ { n _ { k } }$ . Thus (I) is true.

Since $\xi < S ( u )$ ， we can take $y \in \mathbb { R } ^ { m }$ with $u ( y ) > \xi > 0$ . Set $u ( y ) = \mu$ As $( y , \mu ) \in \mathrm { e n d } u$ and $\mathrm { e n d } u = \operatorname* { l i m } \operatorname* { i n f } _ { n \to \infty } \mathrm { e n d } u _ { n }$ ， we can find a sequence $\left\{ \left( y _ { n } , \beta _ { n } \right) \right\}$ satisfying that $( y _ { n } , \beta _ { n } ) \in { \mathrm { ~ e n d } } u _ { n }$ for $n = 1 , 2 , \ldots$ and $\left\{ \left( y _ { n } , \beta _ { n } \right) \right\}$ converges to $( y , \mu )$ ：

Hence there is a $N _ { 2 }$ such that for all $n \geq N _ { 2 }$ ， $\overline { { { d _ { m } } } } ( ( y _ { n } , \beta _ { n } ) , ( y , \mu ) ) ~ <$ $\operatorname* { m i n } \{ \mu - \xi , \xi \}$ .Let $n \in \mathbb { N }$ with $n \ \geq \ N _ { 2 }$ .Then $\beta _ { n } ~ > ~ \xi$ ，and therefore $( y _ { n } , \beta _ { n } ) \ \in \ \mathrm { e n d } _ { \xi } u _ { n }$ .Note that $( y , \mu ) \in \mathrm { e n d } _ { \xi } u$ So $\overline { { d _ { m } } } ( ( y _ { n } , \beta _ { n } ) , \mathrm { e n d } _ { \xi } u ) \ \leq$ $d _ { m } ( ( y _ { n } , \beta _ { n } ) , ( y , \mu ) ) < \xi$ . Thus (II) is true.

(III) follows from (I), (II) and the connectedness of $\mathrm { e n d } _ { \xi } u _ { n _ { k } }$ when $n _ { k } \ge$ $N _ { 3 }$ . The proof of (III) is the same as that of the clause (III) in the proof of Theorem 3.18.

Now using (III) and the compactness of $\operatorname { e n d } _ { \xi } u$ ， we can have a contradiction. The proof is the same as the counterpart in the proof of Theorem 3.18.

Example 3.23.Let $u$ be a fuzzy set in $F _ { U S C } ^ { 1 } ( \mathbb { R } ) \setminus \{ \emptyset _ { F ( \mathbb { R } ^ { m } ) } \}$ defined by putting:

$$
[ u ] _ { \alpha } = \left\{ \begin{array} { l l } { \{ 1 \} , } & { \alpha \in ( 0 . 6 , 1 ] , } \\ { ( - \infty , - 1 ] \cup [ 1 , + \infty ) } & { \alpha \in [ 0 , 0 . 6 ] . } \end{array} \right.
$$

For $n = 1 , 2 , \ldots$ ,let $u _ { n } = u$ . We have the following conclusions:

(i) $H ( u _ { n } , u )  0$ since $u _ { n } = u$ for $n = 1 , 2 , \ldots$ ：   
(ii) the pair $\{ u _ { n } \}$ ， $u$ is a weak connectedness compact pair;   
(iii) $\{ u _ { n } \}$ does not satisfy the connectedness condition because $\operatorname { e n d } _ { r } u$ is not connected in $\mathbb { R } \times [ 0 , 1 ]$ when $r \in [ 0 , 0 . 6 ]$ . Clearly each subsequence $\{ u _ { n _ { k } } \}$ of $\{ u _ { n } \}$ does not satisfy the connectedness condition;   
(iv) $u \not \in F _ { U S C G } ( \mathbb { R } )$ ：

Remark 3.24. Let $\{ u _ { n } \}$ be a fuzzy set sequence in $F _ { U S C } ( \mathbb { R } ^ { m } )$ satisfying the connectedness condition and let $u$ be a fuzzy set in $F _ { U S C G } ( \mathbb { R } ^ { m } ) \setminus \{ \emptyset _ { F ( \mathbb { R } ^ { m } ) } \}$ Then clearly the pair $\{ u _ { n } \}$ ， $u$ is a weak connectedness compact pair. So Theorem 3.18 is a corollary of Theorem 3.22. Theorem 3.22 is an improvement of Theorem 3.18.

[1] C.Wu, M. Ma, The Basic of Fuzzy Analysis (in Chinese)，National Defence Industry press,Beijing, 1991.   
[2] P.Diamond, P. Kloeden, Metric Spaces of Fuzzy Sets, World Scientific, Singapore, 1994.   
[3] D.Dubois, H. Prade (Eds.), Fundamentals of Fuzzy Sets, vol 1 of the Handbooks of Fuzzy Sets,Kluwer,Boston，Mass,2000.   
[4] M. Rojas-Medar, H. Roman-Flores, On the equivalence of convergences of fuzzy sets, Fuzzy Sets Syst. 80 (1996) 217-224.   
[5] H.Huang，Characterizations of endograph metric and I-convergence on fuzzy sets, Fuzzy Sets Syst. 350 (2018) 55-84.   
[6] Huan Huang， Propertiesofseveral fuzzysetspaces， arXiv:submit/4419682 [math.GM] 25 Jul 2022.