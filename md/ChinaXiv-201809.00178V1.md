# Regularity for a minimum problem with free boundary in Orlicz spaces

Jun Zheng 1,Leandro S. Tavares², Claudianor O. Alves’

1 School of Mathematics, Southwest Jiaotong University Chengdu 611756, SichuanChina 2CentrodeCeasiaiddedealdoridnteid84Jte CE, Brazil 3 Unidade Académicade Matematica, UniversidadeFederaldeCampina Grande,CEP58429-90o,Campina Grande,PB,Brazil

# Abstract

The aim of this paper is to study the heterogeneous optimization problem

$$
\mathcal { I } ( u ) = \int _ { \Omega } ( G ( | \nabla u | ) + q F ( u ^ { + } ) + h u + \lambda _ { + } \chi _ { \{ u > 0 \} } ) \mathrm { d } x \to \operatorname* { m i n } ,
$$

in the class of functions $W ^ { 1 , G } ( \Omega )$ with $u - \varphi \in W _ { 0 } ^ { 1 , G } ( \Omega )$ , for a given function $\varphi$ ，where $W ^ { 1 , G } ( \Omega )$ is the class of weakly differentiable functions with $\begin{array} { r } { \int _ { \Omega } G ( | \nabla u | ) \mathrm { d } x < \infty } \end{array}$ .The functions $G$ and $F$ satisfy structural conditions of Lieberman's type that allow for a different behavior at O and at $\infty$ .Given functions $q , h$ and constant $\lambda _ { + } \geq 0$ ,we address several regularities for minimizers of $\mathcal { I } ( u )$ ,including local $C ^ { 1 , \alpha } -$ ,and local Log-Lipschitz continuities for minimizers of $\mathcal { I } ( u )$ with $\lambda _ { + } = 0$ ,and $\lambda _ { + } > 0$ respectively. We also establish growth rate near the free boundary for each non-negative minimizer of $\mathcal { I } ( u )$ with $\lambda _ { + } = 0$ ,and $\lambda _ { + } > 0$ respectively.Furthermore,under additional assumption that $F \in \dot { C } ^ { 1 } ( [ 0 , + \infty ) ; [ 0 , + \infty ) )$ ,local Lipschitz regularity is carried out for non-negative minimizers of $\mathcal { I } ( u )$ with $\lambda _ { + } > 0$

Key words:free boundary problem; minimum problem; regularity; growth rate; Orlicz space.

# 1 Introduction

Let $\Omega$ be a smooth bounded domain in $\mathbb { R } ^ { n } ( n \geq 2 )$ . Let $g , f \in C ( [ 0 , \infty ) ; [ 0 , \infty ) ) \cap C ^ { 1 } ( ( 0 , \infty ) ; ( 0 , \infty ) )$ with $g ( 0 ) = F ( 0 ) = 0$ （20 satisfytheLieberman'sconditions,whichwereintroduced in[16]foralargeclassof degenerate/singular elipticequations, i.e.,

$$
0 < \delta _ { 0 } \leq \frac { t g ^ { \prime } ( t ) } { g ( t ) } \leq g _ { 0 } , \forall t > 0 ,
$$

with $\delta _ { 0 } < n - 1$ ，and

$$
1 + \theta _ { 0 } \leq \frac { F ^ { \prime } ( t ) t } { F ( t ) } \leq 1 + f _ { 0 } , \forall t > 0 .
$$

with $\theta _ { 0 } , f _ { 0 }$ satisfying $- 1 < \theta _ { 0 } \le f _ { 0 } < \delta _ { 0 }$

Theaimofthis paperistoderive interiorregularityestimates foralargeclass ofheterogeneousnon-differentiablefunctionals

$$
\mathcal { I } ( u ) = \int _ { \Omega } ( G ( | \nabla u | ) + q F ( u ^ { + } ) + h u + \lambda _ { + } \chi _ { \{ u > 0 \} } ) \mathrm { d } x \to \operatorname* { m i n } ,
$$

among competing functions $\begin{array} { r } { u \in \{ u \in L ^ { 1 } ( \Omega ) : \int _ { \Omega } G ( | \nabla u | ) \mathrm { d } x < \infty , u = \varphi } \end{array}$ on $\partial \Omega \}$ , where $\begin{array} { r } { G ( t ) = \int _ { 0 } ^ { t } g ( s ) \mathrm { d } s } \end{array}$ ， $\varphi \in L ^ { \infty } ( \Omega )$ （204号 with $\begin{array} { r } { \int _ { \Omega } G ( | \nabla \varphi | ) \mathrm { d } x < \infty , h , q \in L ^ { \infty } ( \Omega ) } \end{array}$ with $q \not \equiv 0$ ， $u ^ { + } = \operatorname* { m a x } \{ u , 0 \}$ , and $\lambda _ { + } \geq 0$ is a constant. Note that if no restriction is made on the sign of $h$ ， problem (3) has a minimizer that may change its sign near the free boundary $\partial \{ u > 0 \}$ .Therefore problem (3) is not in the one-phase case in the strict sense.

A typical form of(3) is the free boundary problem of $p$ -Laplacian,i.e.,

$$
\int _ { \Omega } ( | \nabla u | ^ { p } + q ( u ^ { + } ) ^ { \gamma } + h u + \lambda _ { + } \chi _ { \{ u > 0 \} } ) \mathrm { d } x \to \operatorname* { m i n } ,
$$

over the set $\{ u ~ \in ~ W ^ { 1 , p } ( \Omega ) , u - \varphi ~ \in ~ W _ { 0 } ^ { 1 , p } ( \Omega ) \}$ ， corresponding to set $g ( t ) \ = \ p t ^ { p - 1 } , \delta _ { 0 } \ = \ g _ { 0 } \ = \ p - 1 , p \ > \ 1$ and $F ( t ) = t ^ { \gamma } , \theta _ { 0 } = f _ { 0 } = \gamma - 1 , 0 < \gamma < p$ in (1),and (2) respectively. More examples of functions satisfying (1) (or (2)) is given in Remark 2.

A numberof important mathematical physics problems,coming from several diferentcontexts,are modeled byoptimization setups,for which (4） serves as an emblematic,leading prototype.The case of $\gamma = 1 , q \not \equiv 0$ and $\lambda _ { + } = 0$ represents the obstacle type problems. The general case of $\boldsymbol { 0 } < \boldsymbol { \gamma } < p , q \neq \boldsymbol { 0 }$ and $\lambda _ { + } = 0$ is usually used to model the density of certain chemical specie in reaction with a porous catalyst pellet. The case of $q \equiv 0$ and $\lambda _ { + } \neq 0$ relates to jets flow and cavities problems.The minimization problem (4),particularly homogeneous one-phase problem (i.e., $h \equiv 0$ ,and minimizers of which do notchangesign),has indeedreceivedoverwhelmingatentionataspects ofbothregularityofsolutionsandregularityoffree boundariesineastdecades,e.g,justtoitefew,,]fortheomogeneousone-phaseobstacleproblems,[3,19] for the homogeneous one-phase chemical reaction problems with $\gamma \in ( 0 , \bar { 1 } )$ ,[2,9] for the homogeneous one-phase jets flow and cavities problems with $q \equiv 0$ and $\lambda _ { + } \neq 0$ ,and[15] for a large class of homogeneous one-phase free boundary problems of $p$ -Laplacian type corresponding to (4) with $h \equiv 0 , 1 \leq \gamma < p$ . A rather complete description of regularity theory in the heterogeneous two-phase free boundary problems,which contain (4) with $\gamma \in [ 0 , 1 ]$ ,and one-phase problems as special cases, was provided in [14].

For the setting in Orlicz spaces,regularities of solutions and free boundaries are addressed for $\lambda _ { + } = 0 , h \equiv 0 , q \equiv C$ in[6,7] and for $q \equiv h \equiv 0 , \lambda _ { + } > 0$ in [17], respectively. The homogeneous two-phase jets flow and cavities problems were studied in [5]. It should be mentioned that the heterogeneous two-phase problems related to (3） with ${ \cal F } ( t ) = t ^ { \gamma } ( \gamma \in ( 0 , 1 ] )$ ，and a version of two-phase problems related to (3) with $F ( t ) \leq \mathrm { i n a x } \{ t ^ { \bar { p } } , t ^ { p } \} ( p , q \geq 1 )$ and $h \equiv 0$ ,were studied in [20,22], and [4] respectively.Nevertheless,regularitiesintheproblem(3)foralargeclassofheterogeneousnon-differentiablefunctionalshas been little studied in the literature in Orlicz spaces.

The aim of this paper is to consider the free boundary problem (3)and prove several regularities for minimizers of $\mathcal { I } ( u )$ Comparing with the existing results,the main contribution of this paper include: (i)our problems concern with not only the non-homogeneous case of $h \not \equiv 0$ , but also the case of $F ( t ) \leq \mathrm { m a x } \{ t ^ { p } , t ^ { p } \}$ with positive exponents $p , q$ less or larger than 1, which canbeseenas complementsof[4,5,20,22]; (ii)we establish local Log-Lipschitz continuityfor minimizers of $\mathcal { I } ( u )$ with $\lambda + > 0$ under the assumption that $\delta _ { 0 } > 0$ ， which is weaker than the condition tat $\delta _ { 0 } \geq 1$ (or, equivalently, $\textstyle { \frac { g ( t ) } { t } }$ is increasing in $t$ ) in [4,22]; (ii) we prove the growth rate near the free boundaries for non-negative minimizers of $\mathcal { I } ( u )$ with $h \not \equiv 0$ and $F$ （204号 satisfying (2),which is new even in the problem(4) with one-phase and $\gamma \in ( 0 , \bar { p ) }$ ; (iv)we prove local Lipschitz continuity for non-negative minimizers of $\mathcal { I } ( u )$ with $\bar { h } \not \equiv 0$ ,which is an extension of [4]; (v) the results obtained in this paper are naturally extensions of the existing results of $p$ -Laplican type.

Throughout this paper, without spacial states,we always assume that

$g , f \in C ( [ 0 , \infty ) ; [ 0 , \infty ) ) \cap C ^ { 1 } ( ( 0 , \infty ) ; ( 0 , \infty ) ) , g ( 0 ) = F ( 0 ) = 0 , g , f  \mathrm { ~ s a t i s f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ i s t ~ o f ~ t h e ~ } ,$ y (1) and (2),   
（204号 $h , q \in L ^ { \infty } ( \Omega ) , q \not \equiv 0 , \lambda _ { + } \geq 0$ is a constant,   
（204号 $\varphi \in W ^ { 1 , G } ( \Omega ) \cap L ^ { \infty } ( \Omega ) .$

where the definition of $W ^ { 1 , G } ( \Omega )$ is given in Section 2. For $t > 0$ , denote by $f ( t )$ the derivative of $F ( t )$ ,i.e, $f ( t ) = F ^ { \prime } ( t )$ $\forall t > 0$ .We assume further in Section 4,5 and 6 that

$$
f { \mathrm { ~ i s ~ m o n o t o n e ~ i n ~ } } t > 0 .
$$

Moreover, we always assume in Section 5 and 6 that there exists $\tau \in ( 0 , 1 ]$ such that

$$
\int _ { t } ^ { t + k } | Q ^ { \prime } ( s ) | \mathrm { d } s \leqslant c _ { 0 } \left( \frac { k } { t } \right) ^ { \tau } ,
$$

$t > 0 , k > 0$ $\begin{array} { r } { Q ( s ) = \frac { t g ^ { \prime } ( t ) } { g ( t ) } } \end{array}$ $c _ { 0 } = c _ { 0 } ( \delta _ { 0 } , g _ { 0 } , \tau )$ ${ \mathcal { K } } = \{ v \in W ^ { 1 , G } ( \Omega ) : v - \varphi \in$ $W _ { 0 } ^ { 1 , G } ( \Omega ) \}$ . Denote a ball in $\Omega$ by $B$ ， $B _ { r }$ or $\boldsymbol { B } _ { R }$ without special statements on their radius and centres,and denote by $B _ { r } ( x _ { 0 } )$ （204号 a ball with radius $r$ and centre $x _ { 0 }$ . Without confusion, constants $\varepsilon , \tau , c , C , C _ { 0 } , C _ { 1 } , \ldots$ appearing in this paper may be different from each other.

The rest of the paper is organized as follows.We provide two remarks onthe structural conditions (1)and (2)at theend of Section 1. Some basic properties of functions $g , G$ and $F$ ,definitions of Orlicz spaces, properties of functions in Orlicz spaces, andan iterationlemma forthe establishmentofregularitiesof minimizers are presentedin Section2.Existenceof minimizers (and non-negative minimizers) of $\mathcal { I } ( u )$ and their $L ^ { \infty }$ -boundedness and local $C ^ { 0 , \alpha }$ -continuity are addressed in Section 3. Local $C ^ { 1 , \alpha }$ -continuityandlocalLog-Lipschitzcontinuityof minimizersareestablished inSection4for $\mathcal { I } ( u )$ with $\lambda + = 0$ and $\lambda + > 0$ respectively. Growth rate near the free boundary $\partial \{ u > 0 \}$ of each non-negative minimizer of $\mathcal { I } ( u )$ with $\lambda + = 0$ （204号 and $\lambda + > 0$ are given in Section 5 respectively. As a consequence of the obtained results, we can prove the optimal growth rates of each non-negative minimizer and its gradient in the one-phase free boundary problems for $p$ -Laplacian.Under the further assumption on $F$ ,i.e., ${ \cal F } \in C ^ { 1 } ( [ 0 , + \infty ) ; [ 0 , + \infty ) )$ ,Local Lipschitz continuity of non-negative minimizers of $\mathcal { I } ( u )$ with $\lambda + > 0$ is established in Section 6.

Remark 1 We do not require any $C ^ { 2 } -$ continuity of $F$ to assume that

$$
\theta _ { 0 } \leq \frac { f ^ { \prime } ( t ) t } { f ( t ) } \leq f _ { 0 } , \quad \forall t > 0 ,
$$

provided a $C ^ { 1 }$ -continuos function $f$ satisfying $f ( 0 ) = 0$ and $\begin{array} { r } { F ( t ) = \int _ { 0 } ^ { t } f ( s ) d s } \end{array}$ . Therefore (2) is weaker than the structural condition imposed on $F$ by (6).

Remark 2 In this remark, we present several functions defined on $[ 0 , + \infty )$ and satisfying condition (1), proofs of which and more functions satisfying a slight version of(1) can be found in $\boldsymbol { l } \boldsymbol { 2 } \boldsymbol { l } \boldsymbol { J }$

(i) $g ( t ) = ( 1 + t ) \ln ( 1 + t ) - t$ satisfies(1) with $\delta _ { 0 } = 1$ and $g _ { 0 } = 2$   
(i) $g ( t ) = \ln ( 1 + a t ) + b t$ satisfes(1) with $\textstyle { \delta _ { 0 } = { \frac { b } { a + b } } }$ and $\textstyle g _ { 0 } = { \frac { a + b } { b } }$ ， where $a > 0 , b > 0$ ，   
(i) $g ( t ) = t ^ { a } \log _ { c } ( b t + d )$ satisfies (1) with $\delta _ { 0 } = a$ and $\begin{array} { r } { g _ { 0 } = a + \frac { 1 } { \ln d } } \end{array}$ ,where, $a , b > 0 , c , d > 1$   
(iv) $\begin{array} { r } { g ( t ) = \frac { t ^ { a } } { \log _ { c } ( b t + d ) } } \end{array}$ stisfies (1) with $\begin{array} { r } { \delta _ { 0 } = a - \frac { 1 } { \ln d } } \end{array}$ and $g _ { 0 } = a$ where $\textstyle b > 0 , c , d > 1 , a > { \frac { 1 } { \ln d } }$ (v） $g ( t ) = \left\{ { \begin{array} { l l } { a t ^ { p } , 0 \leq t < t _ { 0 } } \\ { b t ^ { q } + c , t \geq t _ { 0 } } \end{array} } \right.$ （204号 satisfies (1) with $\delta _ { 0 } = \operatorname* { m i n } \{ p , q \} > 0$ and $g _ { 0 } = \operatorname* { m a x } \{ p , q \}$ ， where $a , b , c , p , q , t _ { 0 } > 0$ such that （204号 $a t _ { 0 } ^ { p } = b t _ { 0 } ^ { q } + c$ ,and $a p t _ { 0 } ^ { p - 1 } = b q t _ { 0 } ^ { q - 1 }$

# 2 Some auxiliary results

Lemma 1([5,17]) The functions $g$ and $G$ satisfy the following properties:

$( g _ { 1 } ) \ \operatorname* { m i n } \{ s ^ { \delta _ { 0 } } , s ^ { g _ { 0 } } \} g ( t ) \leq g ( s t ) \leq \operatorname* { m a x } \{ s ^ { \delta _ { 0 } } , s ^ { g _ { 0 } } \} g ( t )$ ， $\forall s , t \geq 0$ $\left( G _ { 1 } \right)$ $G$ is convex on $[ 0 , + \infty )$ and $C ^ { 2 } - { \overset { } { c } }$ ontinuous on $( 0 , + \infty )$ ： $\left( G _ { 2 } \right)$ $\begin{array} { r } { \frac { t g ( t ) } { 1 + g _ { 0 } } \leq G ( t ) \leq t g ( t ) } \end{array}$ ,At≥0. $\begin{array} { r } { ( G _ { 3 } ) \ \operatorname* { m i n } \{ s ^ { \delta _ { 0 } + 1 } , s ^ { g _ { 0 } + 1 } \} \frac { G ( t ) } { 1 + g _ { 0 } } \leq G ( s t ) \leq ( 1 + g _ { 0 } ) \operatorname* { m a x } \{ s ^ { \delta _ { 0 } + 1 } , s ^ { g _ { 0 } + 1 } \} G ( t ) , \forall t \geq 0 . } \end{array}$ $\left( G _ { 4 } \right)$ $G ( a + b ) \leq 2 ^ { g _ { 0 } } ( 1 + g _ { 0 } ) ( G ( a ) + G ( b ) )$ ， $\forall a , b \geq 0$ (G5）d0≤ and $\begin{array} { r } { \frac { 1 } { 1 + g _ { 0 } } \le G _ { s } ( 1 ) \le 1 } \end{array}$ for all $t > 0$ where $\begin{array} { r } { G _ { s } ( t ) = \frac { G ( s t ) } { s g ( s ) } } \end{array}$ and $g _ { s } ( t ) = G _ { s } ^ { \prime } ( t )$ for $s > 0$ ，

Lemma 2 The functions $F$ and $f$ satisfy the following properties:

$$
\begin{array} { r l } & { ( F _ { 1 } ) \operatorname* { m i n } \{ s ^ { 1 + \theta _ { 0 } } , s ^ { 1 + f _ { 0 } } \} F ( t ) \leq F ( s t ) \leq \operatorname* { m a x } \{ s ^ { 1 + \theta _ { 0 } } , s ^ { 1 + f _ { 0 } } \} F ( t ) , \forall s , t \geq 0 . } \\ & { ( F _ { 2 } ) \ F ( s + t ) \leq 2 ^ { 1 + f _ { 0 } } ( F ( s ) + F ( t ) ) , \forall s , t \geq 0 . } \\ & { ( f _ { 1 } ) \ \frac { 1 + \theta _ { 0 } } { 1 + f _ { 0 } } \operatorname* { m i n } \{ s ^ { \theta _ { 0 } } , s ^ { f _ { 0 } } \} f ( t ) \leq f ( s t ) \leq \frac { 1 + f _ { 0 } } { 1 + \theta _ { 0 } } \operatorname* { m a x } \{ s ^ { \theta _ { 0 } } , s ^ { f _ { 0 } } \} f ( t ) , \forall s , t > 0 . } \\ & { ( f _ { 2 } ) \underset { t  + \infty } { \operatorname* { m i n } } \frac { f ( t ) } { g ( t ) } = 0 , a n d \underset { t  + \infty } { \operatorname* { m i n } } \frac { F ( t ) } { G ( t ) } = 0 . } \end{array}
$$

Proof $\left( F _ { 1 } \right)$ is a consequence of (2) and $\left( g _ { 1 } \right)$

For $\left( F _ { 2 } \right)$ , without loss of generality, assume that $s \leq t$ ,then $F ( s + t ) \leq F ( 2 t ) \leq 2 ^ { 1 + f _ { 0 } } F ( t ) \leq 2 ^ { 1 + f _ { 0 } } ( F ( s ) + F ( t ) ) .$

For $\left( f _ { 1 } \right)$ ,we deduce by (2) and $\left( F _ { 1 } \right)$

$$
\begin{array} { r l r } {  { s t f ( s t ) \le ( 1 + f _ { 0 } ) F ( s t ) } } \\ & { } & { \le ( 1 + f _ { 0 } ) \operatorname* { m a x } \{ s ^ { 1 + \theta _ { 0 } } , s ^ { 1 + f _ { 0 } } \} F ( t ) } \\ & { } & { \le \frac { 1 + f _ { 0 } } { 1 + \theta _ { 0 } } \operatorname* { m a x } \{ s ^ { 1 + \theta _ { 0 } } , s ^ { 1 + f _ { 0 } } \} t f ( t ) , } \end{array}
$$

which yields the second inequality in $\left( f _ { 1 } \right)$ . The first inequality in $\left( f _ { 1 } \right)$ can be obtained in a similar way.

For $\left( f _ { 2 } \right)$ ,we infer from $\left( f _ { 1 } \right)$ and $\left( g _ { 1 } \right)$ that for large $t > 1$

$$
f ( t ) t ^ { \delta _ { 0 } - f _ { 0 } } \leq \frac { 1 + f _ { 0 } } { 1 + \theta _ { 0 } } f ( 1 ) t ^ { f _ { 0 } } t ^ { \delta _ { 0 } - f _ { 0 } } \leq \frac { 1 + f _ { 0 } } { 1 + \theta _ { 0 } } \frac { f ( 1 ) } { g ( 1 ) } g ( 1 ) t ^ { \delta _ { 0 } } \leq \frac { 1 + \theta _ { 0 } } { 1 + f _ { 0 } } \frac { f ( 1 ) } { g ( 1 ) } g ( t ) ,
$$

which implies $\operatorname* { l i m } _ { t \to + \infty } { \frac { f ( t ) } { g ( t ) } } = 0$ . The second result can be obtained in a similar way by $\left( F _ { 1 } \right)$ and $\left( G _ { 1 } \right)$ ：

Lemma3 The follows statements hold true.

$\left( F _ { 3 } \right)$ 1f $f ( t )$ is decreasing in $t > 0$ ，then $F ( s ) - F ( t ) \leq F ( s - t )$ ， $\forall s \geq t \geq 0$ $( F _ { 4 } )$ If $f ( t )$ is increasing in $t > 0$ ,then $F ( s ) - F ( t ) \leq f ( M ) ( s - t ) .$ ， $\forall 0 \leq t \leq s \leq M$ with some $M > 0$

Proof We prove $\left( F _ { 3 } \right)$ . Firstly, note that $F ( 0 ) = 0$ due to $\left( F _ { 1 } \right)$ . Now Fix $s \geq 0$ and let $v ( t ) = F ( s + t ) - F ( s ) - F ( t )$ for any $t \geq 0$ .For $t > 0$ ，we have $v ^ { \prime } ( t ) = f ( s + t ) - f ( t ) \leq 0$ ，which yields the nondecreasing monotonicity of $v$ in $t > 0$ .By continuity of $\boldsymbol { v }$ in $t = 0$ , we conclude that $v ( t ) \leq v ( 0 )$ for all $t \geq 0$ ,i.e., $F ( s + t ) \leq F ( s ) \bar { + F } ( t )$ Finally, for $s \geq t \geq 0$ ,we have $F ( { \dot { s } } ) - F ( t ) = F ( s - t + t ) - F ( t ) \leq F ( s - t ) + F ( t ) - F ( t ) = { \dot { F } } ( s - t ) .$

For $( F _ { 4 } )$ ,if $s = t = 0$ , the result is trivial. If $M \geq s \geq t > 0$ ,by Mean Value Theorem, it follows $F ( s ) - F ( t ) = f ( \xi ) ( s - t )$ with some $\xi \in ( t , s ) \subset ( 0 , M ]$ . By the increasing monotonicity of $f ( t )$ in $t > 0$ ,we have $F ( s ) - F ( t ) \leq f ( M ) ( s - t )$ for all $M \geq s \geq t > 0$ Finally, $\left( f _ { 4 } \right)$ has been proved. ■

As $g$ is strictly increasing we can define its inverse function $g ^ { - 1 }$ . Then $g ^ { - 1 }$ satisfes a similar condition to (1.2).

Lemma 4([17])The function $g ^ { - 1 }$ satisfies the following property:

$$
\frac { 1 } { g _ { 0 } } \leq \frac { t ( g ^ { - 1 } ) ^ { \prime } ( t ) } { g ^ { - 1 } ( t ) } \leq \frac { 1 } { \delta _ { 0 } } , \forall t > 0 .
$$

Moreover, $g ^ { - 1 }$ satisfies

$\begin{array} { r l } & { ( \widetilde g _ { 1 } ) \operatorname* { m i n } \\\\lbrace s ^ { \frac { 1 } { \delta _ { 0 } } } , s ^ { \frac { 1 } { g _ { 0 } } } \rbrace g ^ { - 1 } ( t ) \leq g ^ { - 1 } ( s t ) \leq \operatorname* { m a x } \lbrace s ^ { \frac { 1 } { \delta _ { 0 } } } , s ^ { \frac { 1 } { g _ { 0 } } } \rbrace g ^ { - 1 } ( t ) , } \end{array}$ （20 and $i f { \tilde { G } } { }$ is such that $\tilde { G } ^ { \prime } ( t ) = g ^ { - 1 } ( t )$ then

$$
\begin{array} { l l l } { { ( \tilde { G } _ { 1 } ) } } & { { { \displaystyle { \frac { 1 + \delta _ { 0 } } { \delta _ { 0 } } } \operatorname* { m i n } \{ s ^ { 1 + 1 / \delta _ { 0 } } , s ^ { 1 + 1 / g _ { 0 } } \} } \tilde { G } ( t ) \le \tilde { G } ( s t ) \le { \displaystyle { \frac { \delta _ { 0 } } { 1 + \delta _ { 0 } } } \operatorname* { m a x } \{ s ^ { 1 + 1 / \delta _ { 0 } } , s ^ { 1 + 1 / g _ { 0 } } \} } \tilde { G } ( t ) , } }  \\ { { ( \tilde { G } _ { 2 } ) } } & { { a b \le \varepsilon G ( a ) + C ( \varepsilon ) \tilde { G } ( b ) , \ \forall a , b > 0 a n d \varepsilon > 0 , } } \\ { { ( \tilde { G } _ { 3 } ) } } & { { \tilde { G } ( g ( t ) ) \le g _ { 0 } G ( t ) . } } \end{array}
$$

Werecall that the functional

$$
\| u \| _ { L ^ { G } ( \Omega ) } : = \operatorname* { i n f } \left\{ k > 0 ; \int _ { \Omega } G \left( \frac { | u | } { k } \right) \mathrm { d } x \le 1 \right\}
$$

is a norm in the Orlicz space $L ^ { G } ( \Omega )$ which is the linear hull of the Orlicz class

$$
{ \mathcal { K } } _ { G } ( \Omega ) : = \left\{ u \ { \mathrm { m e a s u r a b l e } } ; \int _ { \Omega } G ( | u | ) { \mathrm { d } } x < + \infty \right\} .
$$

Notice that this set is convex, since $G$ is also convex. The Orlicz-Sobolev space $W ^ { 1 , G } ( \Omega )$ is defined as

$$
W ^ { 1 , G } ( \Omega ) : = \{ u \in L ^ { G } ( \Omega ) ; \nabla u \in ( L ^ { G } ( \Omega ) ) ^ { n } \} ,
$$

which is the usual subspace of $W ^ { 1 , 1 } ( \Omega )$ , and associated with the norm

$$
\lVert u \rVert _ { W ^ { 1 , G } ( \Omega ) } = \lVert u \rVert _ { L ^ { G } ( \Omega ) } + \lVert \nabla u \rVert _ { L ^ { G } ( \Omega ) } .
$$

We present some properties of spaces $L ^ { G } ( \Omega )$ and $W ^ { 1 , G } ( \Omega )$ ,and properties of functions in $L ^ { G } ( \Omega )$ and $W ^ { 1 , G } ( \Omega )$

Lemma 5 ([17]) There exists a constant $C = C ( \delta _ { 0 } , g _ { 0 } )$ such that

$$
\| u \| _ { L ^ { G } ( \Omega ) } \le C \operatorname* { m a x } \left\{ \left( \int _ { \Omega } G ( | u | ) d x \right) ^ { \frac { 1 } { 1 + \delta _ { 0 } } } , \left( \int _ { \Omega } G ( | u | ) d x \right) ^ { \frac { 1 } { 1 + g _ { 0 } } } \right\} .
$$

Lemma 6 ([17]) $L ^ { \tilde { G } } ( \Omega )$ is the dual of $L ^ { G } ( \Omega )$ . Moreover, $L ^ { G } ( \Omega )$ and $W ^ { 1 , G } ( \Omega )$ are reflexive.

Lemma 7 ([17]) $L ^ { G } ( \Omega ) \hookrightarrow L ^ { 1 + \delta _ { 0 } } ( \Omega )$ continuously.

Lemma 8([17]) For any $u \in L ^ { G } ( \Omega )$ and any $v \in L ^ { \tilde { G } } ( \Omega )$ , there holds $\begin{array} { r } { \left| \int _ { \Omega } u v d x \right| \leq 2 \| u \| _ { L ^ { G } ( \Omega ) } \| v \| _ { L ^ { \tilde { G } } ( \Omega ) } . } \end{array}$

Lemma 9 ([8]) For any $u \in W _ { 0 } ^ { 1 , G } ( \Omega )$ , which is the closure of $C _ { 0 } ^ { \infty } ( \Omega )$ 讥 $W ^ { 1 , G } ( \Omega )$ , there holds $\begin{array} { r } { \int _ { \Omega } G ( | u | ) d x \leq \int _ { \Omega } G ( c | \nabla u | ) d x } \end{array}$ （号 wheretheconstant $c$ istwice the diameter of $\Omega$

Lemma 10([17]) Let $u \in L ^ { \infty } ( \Omega )$ such that for some $\alpha \in ( 0 , 1 )$ and $r _ { 0 } > 0$

$$
\int _ { B _ { r } } G ( | \nabla u | ) d x \le C _ { 1 } r ^ { n + \alpha - 1 } , \ 0 < r \le r _ { 0 } ,
$$

with $B _ { r _ { 0 } } \Subset \Omega$ Then $u \in C ^ { \alpha } ( \Omega )$ and there exists a constant $C = C ( C _ { 1 } , \alpha , n , g _ { 0 } , G ( 1 ) )$ such that $[ u ] _ { 0 , \alpha , \Omega } \leq C$ 号

Lemma11 Let v beabounded weak solution f div $\begin{array} { r } { \frac { g ( | \nabla v | ) } { | \nabla v | } \nabla v = 0 } \end{array}$ 讥 $\boldsymbol { B } _ { R }$ (see (54)foradefiniion).orevery $\lambda \in ( 0 , n )$ there exists $C = C ( \lambda , n , \delta , g _ { 0 } , \| v \| _ { L ^ { \infty } ( B _ { R } ) } ) > 0$ such that

$$
\int _ { B _ { r } } G ( | \nabla v | ) d x \leq C r ^ { \lambda } , \forall 0 < r \leq R .
$$

Proof See [16,(5.9), page 346],or [17,Lemma 2.7].

Lemma 12 ([20]) Let $u \in W ^ { 1 , G } ( \Omega ) , B _ { R } \subset \Omega .$ If u is a bounded weak solution of

$$
d i \nu \frac { g ( | \nabla \boldsymbol { v } | ) } { | \nabla \boldsymbol { v } | } \nabla \boldsymbol { v } = 0 i n B _ { R } , v - \boldsymbol { u } \in W _ { 0 } ^ { 1 , G } ( B _ { R } ) ,
$$

then for any $\lambda \in ( 0 , n )$ , there exists $C = C ( \lambda , n , \delta _ { 0 } , g _ { 0 } , \| v \| _ { L ^ { \infty } ( B _ { R } ) } ) > 0$ such that

$$
\int _ { B _ { R } } G ( | \nabla u - \nabla v | ) d x \leq C \int _ { B _ { R } } ( G ( | \nabla u | ) - G ( | \nabla v | ) ) d x + C R ^ { \frac { 3 } { 2 } } \Bigg ( \int _ { B _ { R } } ( G ( | \nabla u | ) - G ( | \nabla v | ) ) d x \Bigg ) ^ { \frac { 1 } { 2 } } .
$$

Proof See the proof of Lemma 3.1 in [20].

Let $\begin{array} { r } { ( u ) _ { r } = \frac { 1 } { | B _ { r } | } \int _ { B _ { r } } } \end{array}$ udx be the average value of function $u$ on the ball $B _ { r }$

Lemma 13 ([20])Let $u \in W ^ { 1 , G } ( \Omega ) , B _ { R } \subset \Omega .$ f $v \in W ^ { 1 , G } ( B _ { R } )$ is a weak solution of div $\begin{array} { r } { \frac { g ( | \nabla v | ) } { | \nabla v | } \nabla v = 0 } \end{array}$ 讥 $B _ { R } ,$ then for some positive constant $0 < \sigma < 1$ ,there exists a positive constant $C = C ( n , \delta , g _ { 0 } )$ such that for each $0 < r \leq R ,$ there holds

$$
\int _ { B _ { r } } G ( | \nabla u - ( \nabla u ) _ { r } | ) d x \leq C \left( \frac { r } { R } \right) ^ { n + \sigma } \int _ { B _ { R } } G ( | \nabla u - ( \nabla u ) _ { R } | ) d x + C \int _ { B _ { R } } G ( | \nabla u - \nabla v | ) d x .
$$

The following result is an iteration lemma,which will be used in the establishment ofregularities of minimizers of $\mathcal { I }$

Lemma 14 ([14])Let $\overline { { \phi } } ( s )$ be a non-negative and non-decreasing function. Suppose that

$$
\overline { { { \phi } } } ( r ) \leq C _ { 1 } \bigg ( \bigg ( \frac { r } { R } \bigg ) ^ { \alpha } + \vartheta \bigg ) \overline { { { \phi } } } ( R ) + C _ { 2 } R ^ { \beta } ,
$$

for all $r \leq R \leq R _ { 0 }$ ，with $C _ { 1 } , \alpha , \beta$ positive constants and $C _ { 2 } , \vartheta$ non-negative constants. Then, for any $\tau < \operatorname* { m i n } \{ \alpha , \beta \}$ ,there exists a constant $\vartheta _ { 0 } = \vartheta _ { 0 } ( C _ { 1 } , \alpha , \beta , \tau )$ such that if $\vartheta < C _ { 1 } , \vartheta _ { 0 }$ , then for all $r \leq R \leq R _ { 0 }$ we have

$$
\overline { { { \phi } } } ( r ) \leq C _ { 3 } \bigg ( \frac { r } { R } \bigg ) ^ { \tau } \big ( \overline { { { \phi } } } ( R ) + C _ { 2 } R ^ { \tau } \big ) ,
$$

where $C _ { 3 } = C _ { 3 } ( C _ { 1 } , \tau - \operatorname* { m i n } \{ \alpha , \beta \} )$ is a positive constant. In turn,

$$
\begin{array} { r } { \overline { { \phi } } ( r ) \leq C _ { 4 } r ^ { \tau } , } \end{array}
$$

where $C _ { 4 } = C _ { 4 } ( C _ { 2 } , C _ { 3 } , R _ { 0 } , \overline { { \phi } } , \tau )$ is a positive constant.

# 3Existence, $L ^ { \infty }$ -boundedness and continuity of minimizers over the set $\kappa$

Theorem 15 (Existence and $L ^ { \infty }$ -boundedness) There exists a minimizer u of the functional $\mathcal { I } ( u )$ over the set $\kappa ,$ and there exists a constant $C _ { 0 } > 0$ depending only on $\delta _ { 0 } , g _ { 0 } , \lambda _ { + } , G ( 1 ) , \tilde { G } ( 1 )$ and $\| \varphi \| _ { L ^ { \infty } ( \Omega ) }$ such that

$$
\| u \| _ { L ^ { \infty } ( \Omega ) } \leq C _ { 0 } ,
$$

forall minimizersu of $\mathcal { I } ( u )$ over the set $\kappa$

Proof We will prove that

$$
I _ { 0 } : = \operatorname* { i n f } \{ \mathcal { I } ( v ) ; v \in K \} > - \infty .
$$

For $v \in \mathcal { K }$ ,we have from Lemma 9 that

$$
\int _ { \Omega } G ( | v - \varphi | ) \mathrm { d } x \leq \int _ { \Omega } G ( c | \nabla v - \nabla \varphi | ) \mathrm { d } x , c = 2 \mathrm { d i a m } ( \Omega ) .
$$

Thus, using $( G _ { 3 } ) , ( G _ { 4 } )$ and the nondecreasing monotonicity of $G$ we have

$$
\begin{array} { r l } { \displaystyle \int _ { \Omega } G ( | v | ) { \mathrm { d } } x \leq \int _ { \Omega } G ( | v - \varphi | + | \varphi | ) { \mathrm { d } } x } \\ { \displaystyle } & { \leq C \left( \int _ { \Omega } G ( | v - \varphi | ) { \mathrm { d } } x + \int _ { \Omega } G ( | \varphi | ) { \mathrm { d } } x \right) } \\ { \displaystyle } & { \leq C \left( \int _ { \Omega } G ( | \nabla v - \nabla \varphi | ) { \mathrm { d } } x + \int _ { \Omega } G ( | \varphi | ) { \mathrm { d } } x \right) } \\ { \displaystyle } & { \leq C \left( \int _ { \Omega } G ( | \nabla v | { \mathrm { d } } x + \int _ { \Omega } G ( \nabla \varphi | ) { \mathrm { d } } x + \int _ { \Omega } G ( | \varphi | ) { \mathrm { d } } x \right) , } \end{array}
$$

where $C$ is constant depending only on the diameter of $\Omega$ ,and $\delta _ { 0 }$ and $g _ { 0 }$

$\left( f _ { 2 } \right)$ implies that for given $\tau > 0$ ,there exists a constant $K _ { \tau } > 0$ such that

$$
F ( t ) \leq K _ { \tau } + \tau G ( t ) , \quad \forall t \geq 0 .
$$

By (9),wehave

$$
\left| \int _ { \Omega } q F ( v ^ { + } ) \mathrm { d } x \right| \leq \| q \| _ { L ^ { \infty } ( \Omega ) } \int _ { \Omega } F ( v ^ { + } ) \mathrm { d } x \leq \| q \| _ { L ^ { \infty } ( \Omega ) } K _ { \tau } + \| q \| _ { L ^ { \infty } ( \Omega ) } \tau \int _ { \Omega } G ( | v | ) \mathrm { d } x .
$$

From $\left( \tilde { G } _ { 2 } \right)$ we have for all $\tau > 0$ that

$$
\left| \int _ { \Omega } h v \mathrm { d } x \right| \leq \tau \int _ { \Omega } G ( | v | ) \mathrm { d } x + C _ { \tau } \int _ { \Omega } \tilde { G } ( | h | ) \mathrm { d } x ,
$$

where $C _ { \tau } > 0$ is a constant independent of $v$

Therefore

$$
\left| \int _ { \Omega } q F ( v ^ { + } ) \mathrm { d } x \right| + \left| \int _ { \Omega } h v \mathrm { d } x \right| \leq \tau C \left( \int _ { \Omega } G ( | \nabla v | \mathrm { d } x + G ( | \nabla \varphi | ) + G ( | \varphi | ) \mathrm { d } x \right) + C ,
$$

where $C > 0$ is a constant independent of $v$ . A convenient choice of $\tau > 0$ in (10) implies that

$$
\int _ { \Omega } G ( | \nabla v | ) \mathrm { d } x - \left| \int _ { \Omega } q F ( v ^ { + } ) \mathrm { d } x \right| - \left| \int _ { \Omega } h v \mathrm { d } x \right| + \int _ { \Omega } \lambda \chi _ { \{ v > 0 \} } \geq K \left( 1 + \int _ { \Omega } G ( | \nabla \varphi | ) + G ( | v | ) \mathrm { d } x \right) ,
$$

with some positive constant $K$ ,which implies that $I _ { 0 } > - \infty$

Now consider $v _ { j } ( j \in \mathbb { N } )$ , a minimizing sequence, and $j _ { 0 } \in \mathbb { N }$ ,such that $\mathcal { I } ( v _ { j } ) \leq I _ { 0 } + 1$ for all $j \geq j _ { 0 }$ . We have for $\tau > 0$ that

$$
\begin{array} { l } { \displaystyle \int _ { \Omega } G ( | \nabla v _ { j } | ) \mathrm { d } x = \mathcal { I } ( v _ { j } ) - \int _ { \Omega } q F ( v ^ { + } ) \mathrm { d } x - \lambda _ { + } \chi _ { \{ v > 0 \} } \mathrm { d } x } \\ { \displaystyle \qquad \leq \tau C \left( \int _ { \Omega } G ( | \nabla v _ { j } | ) \mathrm { d } x + G ( | \nabla \varphi | ) + G ( | \varphi | ) \mathrm { d } x \right) + K , } \end{array}
$$

for all $j \geq j _ { 0 }$ ，where $C , K > 0$ are constants independent of $j \in \mathbb { N }$

A convenient choice of $\tau$ in (11) implies that

$$
\int _ { \Omega } G ( | \nabla v _ { j } | ) \mathrm { d } x \leq C + C \left( \int _ { \Omega } G ( | \nabla \varphi | ) + G ( | \varphi | ) \mathrm { d } x \right) , \quad j \geq j _ { 0 } ,
$$

where $C > 0$ is a constant that does not depend on $j \in \mathbb { N }$

From $\left( G _ { 4 } \right)$ ,(12) and Lemma 9, we deduce that $v _ { j } - \varphi$ is a bounded sequence in $W _ { 0 } ^ { 1 , G } ( \Omega )$ . Since $W _ { 0 } ^ { 1 , G } ( \Omega )$ is reflexive, there exists $u \in W ^ { 1 , G } ( \Omega )$ with $u - \varphi \in W _ { 0 } ^ { 1 , G } ( \Omega )$ such that for a subsequence we have

$$
v _ { j }  u \mathrm { i n } W ^ { 1 , G } ( \Omega ) .
$$

Then byLemma7,we find that

$$
\boldsymbol { v } _ { j }  u \mathrm { i n } \boldsymbol { W } ^ { 1 , 1 + \delta _ { 0 } } ( \Omega ) .
$$

Thus, up to a subsequence, we have that

$$
v _ { j }  u \mathrm { i n } \ L ^ { 1 + \delta _ { 0 } } ( \Omega ) , v _ { j }  u \mathrm { a . e \ i n } \ \Omega , \ u = \varphi \mathrm { o n } \ \partial \Omega , \mathrm { \ a n c }
$$

for some $h \in L ^ { 1 + \delta _ { 0 } } ( \Omega )$

Note that

$$
\int _ { \Omega } G ( | \nabla u | ) \mathrm { d } x \leq \operatorname* { l i m i n f } _ { j  \infty } \int _ { \Omega } G ( | \nabla v _ { j } | ) \mathrm { d } x .
$$

In fact,by the convexity of $G$ , it follows

$$
\int _ { \Omega } G ( | \nabla v _ { j } | ) \mathrm { d } x \geq \int _ { \Omega } G ( | \nabla u | ) \mathrm { d } x + \int _ { \Omega } g ( | \nabla u | ) { \frac { \nabla u } { | \nabla u | } } ( \nabla v _ { j } - \nabla u ) \mathrm { d } x .
$$

We have that

$$
\tilde { G } \left( g ( | \nabla u | ) \frac { \partial u } { \partial x _ { i } } \frac { 1 } { | \nabla u | } \right) \leq \tilde { G } ( g ( | \nabla u | ) ) \leq C G ( | \nabla u | ) ,
$$

which implies that $\begin{array} { r } { g ( | \nabla u | ) \frac { \nabla u } { | \nabla u | } \in ( L ^ { \tilde { G } } ( \Omega ) ) ^ { n } } \end{array}$ . Thus,combining the fact that $\nabla v _ { j }  \nabla u$ in $( L ^ { G } ( \Omega ) ) ^ { n }$ with the inequality (15). we get (14). Using Lemma 2, (13) and the Lebesgue's Dominated Convergence Theorem, we have

$$
\int _ { \Omega } F ( ( v _ { j } ) ^ { + } ) \mathrm { d } x \to \int _ { \Omega } q F ( v ^ { + } ) \mathrm { d } x .
$$

Using again the Lebesgue's Dominated Convergence Theorem, we get

$$
\int _ { \Omega } \lambda _ { + } \chi _ { \{ v _ { j } > 0 \} } \mathrm { d } x  \int _ { \Omega } \lambda _ { + } \chi _ { \{ u > 0 \} } \mathrm { d } x .
$$

Since $v _ { j }  u$ in $L ^ { 1 + \delta _ { 0 } } ( \Omega )$ and $h \in L ^ { \infty } ( \Omega )$ , we have

$$
\int _ { \Omega } | h | | v _ { j } - u | \mathrm { d } x \to 0 .
$$

Thus from (14),(16), (17) and (18) we deduce that ${ \mathcal { I } } ( u ) \leq \operatorname* { l i m } _ { j  + \infty } { \mathcal { I } } ( v _ { j } )$ , which implies that $u$ is a minimizer of $\mathcal { I } ( u )$

Now we prove the boundedness of minimizers. Let $j _ { 0 } \in \mathbb { N }$ such that $j _ { 0 } \geq \| \varphi \| _ { L ^ { \infty } ( \Omega ) }$ .For each $j \geq j _ { 0 }$ ,define the functiol $u _ { j } : \Omega \to \mathbb { R }$ by

$$
u _ { j } = { \left\{ \begin{array} { l l } { j \cdot s g n ( u ) } & { \quad { \mathrm { i f ~ } } | u | > j , } \\ { u } & { \quad { \mathrm { i f ~ } } | u | \leq j , } \end{array} \right. }
$$

where $s g n ( u ) = 1$ if $u \geq 0$ ,and $s g n ( u ) = - 1$ if $u < 0$ .Define the set $A _ { j } : = \{ | u | > j \}$ . For each $j \geq j _ { 0 }$ , we have

$$
u = u _ { j } \mathrm { i n } A _ { j } ^ { c } , \mathrm { a n d } u _ { j } = j \cdot s g n ( u ) \mathrm { i n } A _ { j } .
$$

We have $\{ | u _ { j } | > 0 \} = \{ | u | > 0 \}$ for all $j \in \mathbb { N }$ ,and $( | u | - j ) ^ { + } \in W _ { 0 } ^ { 1 , G } ( \Omega )$ for all $j \geq j _ { 0 }$ . Note that

$$
\begin{array} { r l r } {  { \int _ { A _ { j } } G ( | \nabla u | ) \mathrm { d } x = \int _ { \Omega } G ( | \nabla u | ) - G ( | \nabla u _ { j } | ) \mathrm { d } x } } \\ & { } & { \leq \int _ { A _ { j } } q ( F ( u _ { j } ^ { + } ) - F ( u ^ { + } ) ) + \lambda _ { + } ( \chi _ { \{ u _ { j } > 0 \} } - \chi _ { \{ u > 0 \} } ) + h ( u _ { j } - u ) \mathrm { d } x } \\ & { } & { \leq \| q \| _ { L ^ { \infty } ( \Omega ) } \int _ { A _ { j } } | F ( u _ { j } ^ { + } ) - F ( u ^ { + } ) | \mathrm { d } x + \int _ { A _ { j } } h ( u _ { j } - u ) \mathrm { d } x . \quad } \end{array}
$$

By $\left( F _ { 2 } \right)$ ，we have

$$
\begin{array} { r l } { \displaystyle \int _ { A _ { j } } | F ( u _ { j } ^ { + } ) - F ( u ^ { + } ) | \mathrm { d } x = \displaystyle \int _ { A _ { j } \cap \{ u > 0 \} } F ( u ) - F ( j ) \mathrm { d } x } \\ { = \displaystyle \int _ { A _ { j } \cap \{ u > 0 \} } F ( u - j + j ) - F ( j ) \mathrm { d } x } \\ { \le \displaystyle \int _ { A _ { j } \cap \{ u > 0 \} } C ( F ( u - j ) + F ( j ) ) \mathrm { d } x } \\ { \le C \displaystyle \int _ { A _ { j } \cap \{ u > 0 \} } F ( u - j ) \mathrm { d } x + C F ( j ) | A _ { j } | . } \end{array}
$$

In view of (9) and using Lemma 9, we have

$$
\int _ { A _ { j } \cap \{ u > 0 \} } F ( u - j ) \mathrm { d } x \leq C _ { \tau } | A _ { j } | + \tau \int _ { A _ { j } \cap \{ u > 0 \} } G ( u - j ) \mathrm { d } x
$$

$$
\begin{array} { r l } {  { \le C _ { \tau } \vert A _ { j } \vert + \tau \int _ { A _ { j } } G ( ( \vert u \vert - j ) ^ { + } ) \mathrm { d } x } } \\ & { \le C _ { \tau } \vert A _ { j } \vert + \tau C \int _ { A _ { j } } G ( \vert \nabla u \vert ) \mathrm { d } x . } \end{array}
$$

By (19), (2O), (21) and a suitable choice of $\tau > 0$ ,we get

$$
\int _ { A _ { j } } G ( | \nabla u | ) \mathrm { d } x \leq C | A _ { j } | + C F ( j ) | A _ { j } | + \int _ { A _ { j } } h ( u _ { j } - u ) \mathrm { d } x
$$

Arguing as in [22,(3.12),(3.13)], we have for all $\varepsilon > 0$ that

$$
\begin{array} { r l r } {  { \int _ { A _ { j } } h ( u _ { j } - u ) \mathrm { d } x \le 2 \int _ { A _ { j } } \vert h \vert ( \vert u \vert - j ) \mathrm { d } x } } \\ & { } & { \le C ( \varepsilon \int _ { A _ { j } } G ( \vert \nabla u \vert ) \mathrm { d } x + \vert A _ { j } \vert ^ { 1 + \frac { 1 } { n } \frac { 1 + g _ { 0 } } { g _ { 0 } } } ) , } \end{array}
$$

where $C$ is a constant that does not depend on $\varepsilon$ . Using (22) and considering a convenient choice of $\varepsilon$ in (23) we get

$$
\int _ { A _ { j } } G ( | \nabla u | ) \mathrm { d } x \leq C | A _ { j } | + C F ( j ) | A _ { j } | + C | A _ { j } | ^ { 1 + \frac { 1 } { n } \frac { 1 + g _ { 0 } } { g _ { 0 } } } .
$$

Withoutlostofgenealityeoder $| A _ { j } | \le 1$ fr all $j \geq j _ { 0 }$ . Otherwise we may replce $| A _ { j } |$ with $\frac { \vert A _ { j } \vert } { \vert \Omega \vert }$ . Therefore for $j _ { 0 } \in \mathbb { N }$ large enough, we have

$$
\int _ { A _ { j } } G ( | \nabla u | ) \mathrm { d } x \leq C F ( j ) | A _ { j } | , \forall j \geq j _ { 0 } .
$$

By $\left( G _ { 3 } \right)$ ,we have

$$
\begin{array} { r l } & { \displaystyle \int _ { A _ { j } \cap \{ | \nabla u | < 1 \} } | \nabla u | ^ { 1 + g _ { 0 } } \mathrm { d } x \leq \frac { 1 + g _ { 0 } } { G ( 1 ) } \int _ { A _ { j } \cap \{ | \nabla u | < 1 \} } G ( | \nabla u | ) \mathrm { d } x , } \\ & { \displaystyle \int _ { A _ { j } \cap \{ | \nabla u | \geq 1 \} } | \nabla u | ^ { 1 + \delta _ { 0 } } \mathrm { d } x \leq \frac { 1 + g _ { 0 } } { G ( 1 ) } \int _ { A _ { j } \cap \{ | \nabla u | \geq 1 \} } G ( | \nabla u | ) \mathrm { d } x . } \end{array}
$$

ByHolder's inequality, we get

$$
\begin{array} { r l } & { \displaystyle \int _ { A _ { j } \cap \{ | \nabla u | < 1 \} } | \nabla u | ^ { 1 + \delta _ { 0 } } \mathrm { d } x \leq | A _ { j } \cap \{ | \nabla u | < 1 \} | ^ { \frac { g _ { 0 } - \delta _ { 0 } } { 1 + g _ { 0 } } } \left( \displaystyle \int _ { A _ { j } \cap \{ | \nabla u | < 1 \} } | \nabla u | ^ { 1 + g _ { 0 } } \right) ^ { \frac { 1 + \delta _ { 0 } } { 1 + g _ { 0 } } } } \\ & { \qquad \leq | A _ { j } | ^ { \frac { g _ { 0 } - \delta _ { 0 } } { 1 + g _ { 0 } } } \left( \displaystyle \int _ { A _ { j } \cap \{ | \nabla u | < 1 \} } | \nabla u | ^ { 1 + g _ { 0 } } \right) ^ { \frac { 1 + \delta _ { 0 } } { 1 + g _ { 0 } } } . } \end{array}
$$

By(24),(25),(26),(27) andLemma1,we have

$$
\begin{array} { r l } { \displaystyle \int _ { A _ { j } } | \nabla u | ^ { 1 + \delta _ { 0 } } \mathrm { d } x = \int _ { A _ { j } \cap \{ | \nabla u | < 1 \} } | \nabla u | ^ { 1 + \delta _ { 0 } } \mathrm { d } x + \int _ { A _ { j } \cap \{ | \nabla u | \geq 1 \} } | \nabla u | ^ { 1 + \delta _ { 0 } } \mathrm { d } x } & { } \\ { \displaystyle \leq C | A _ { j } | ^ { \frac { g _ { 0 } - \delta _ { 0 } } { 1 + g _ { 0 } } } ( F ( j ) ) | A _ { j } | ) ^ { \frac { 1 + \delta _ { 0 } } { 1 + g _ { 0 } } } + F ( j ) | A _ { j } | } & { } \\ { \displaystyle \leq C ( F ( 1 ) ) ^ { \frac { 1 + \delta _ { 0 } } { 1 + g _ { 0 } } } j ^ { ( 1 + f _ { 0 } ) \frac { 1 + \delta _ { 0 } } { 1 + g _ { 0 } } } | A _ { j } | + C F ( 1 ) j ^ { 1 + f _ { 0 } } | A _ { j } | } & { } \\ { \displaystyle } & { \leq C ( 1 + G ( 1 ) ) ^ { \frac { 1 + \delta _ { 0 } } { 1 + g _ { 0 } } } j ^ { ( 1 + f _ { 0 } ) \frac { 1 + \delta _ { 0 } } { 1 + g _ { 0 } } } | A _ { j } | + C ( 1 + G ( 1 ) ) j ^ { 1 + f _ { 0 } } | A _ { j } | , } \end{array}
$$

where in the last inequality we used $\left( f _ { 2 } \right)$ and the monotonicity of $F$ such that the constant depends on $G ( 1 )$ , rather than $F ( 1 )$ Since $0 < f _ { 0 } < \delta _ { 0 } < g _ { 0 }$ , it follows

$$
\int _ { A _ { j } } | \nabla u | ^ { 1 + \delta _ { 0 } } \mathrm { d } x \le C j ^ { 1 + \delta _ { 0 } } | A _ { j } | = C j ^ { 1 + \delta _ { 0 } } | A _ { j } | ^ { 1 - \frac { 1 + \delta _ { 0 } } { n } + \frac { 1 + \delta _ { 0 } } { n } } .
$$

where $C$ is a constant that is independent of $j \in \mathbb { N }$ . ByLemma 8,we have

$$
\int _ { A _ { j _ { 0 } } } | u | \mathrm { d } x \leq | A _ { j _ { 0 } } | ^ { \frac { \delta _ { 0 } } { 1 + \delta _ { 0 } } } \| u \| _ { L ^ { 1 + \delta _ { 0 } } ( A _ { j _ { 0 } } ) } \leq C .
$$

Then by(28), (29) and [12,Lemma 5.2, Chap.2], we obtain the boundedness of minimizers.

Remark3 Note that from the proof of Theorem 15,we conclude that minimizers of $\mathcal { I } ( u )$ over the set $\kappa$ are bounded in $W ^ { 1 , G } ( \Omega )$ . Indeed, arguing as in (8), we have

$$
\int _ { \Omega } G ( | u | ) d x \leq C \int _ { \Omega } \left( G ( | \nabla u | ) + G ( | \nabla \varphi | ) + G ( | \varphi | ) \right) d x .
$$

For $\varepsilon > 0$ ，wehave

$$
\begin{array} { r l } { \displaystyle \int _ { \Omega } G ( | \nabla u | ) d x = \mathcal { I } ( u ) - \displaystyle \int _ { \Omega } ( q F ( u ^ { + } ) + \lambda _ { + } \chi _ { \{ u > 0 \} } ) d x } \\ { \displaystyle \quad } & { \leq \mathcal { I } ( u ) - \displaystyle \int _ { \Omega } q F ( u ^ { + } ) d x } \\ { \displaystyle } & { \leq \mathcal { I } ( \varphi ) + \| q \| _ { L ^ { \infty } ( \Omega ) } \displaystyle \int _ { \Omega } F ( | u | ) d x } \\ { \displaystyle } & { \leq \mathcal { I } ( \varphi ) + \| q \| _ { L ^ { \infty } ( \Omega ) } \left( C _ { \varepsilon } + \varepsilon \displaystyle \int _ { \Omega } G ( | \nabla u | ) d x \right) , } \end{array}
$$

where $C _ { \varepsilon }$ is a constant that depends only on E. $A$ suitablechoiceof $\varepsilon > 0$ impliesthat

$$
\int _ { \Omega } G ( | \nabla u | ) d x \leq C \mathcal { I } ( \varphi ) + C ,
$$

where $C$ is a constant that is independent of $u$ Then

$$
\int _ { \Omega } G ( | u | ) d x \leq C .
$$

Finally, we conclude that minimizers of $\mathcal { I } ( u )$ are bounded in $W ^ { 1 , G } ( \Omega )$

Theorem 16 (Local $C ^ { 0 , \alpha }$ -continuity) Let u be a minimizerof $\mathcal { I } ( u )$ over the set $\kappa$ Then $u \in C _ { l o c } ^ { 0 , \alpha } ( \Omega )$ for all $\alpha \in ( 0 , 1 )$ ，

Proof For any ball $B _ { R } \Subset \Omega$ ,let $v$ be a weak solution of the following equation

$$
\left\{ \begin{array} { r l } { \mathrm { d i v } \frac { g ( | \nabla v | ) } { | \nabla v | } \nabla v = 0 } & { \mathrm { i n } B _ { R } , } \\ { v = u } & { \mathrm { o n } \partial B _ { R } . } \end{array} \right.
$$

By the minimality of $u$ ,we have

$$
\int _ { B _ { R } } G ( | \nabla u | ) \mathrm { d } x - \int _ { B _ { R } } G ( | \nabla v | ) \mathrm { d } x \le \int _ { B _ { R } } q ( F ( v ^ { + } ) - F ( u ^ { + } ) ) \mathrm { d } x + \lambda _ { + } \int _ { B _ { R } } ( \chi _ { \{ v > 0 \} } - \chi _ { \{ u > 0 \} } ) \mathrm { d } x
$$

$$
\begin{array} { l } { \displaystyle \le \| { q } \| _ { L ^ { \infty } ( B _ { R } ) } \cdot \int _ { B _ { R } } ( | F ( v ^ { + } ) | + | F ( u ^ { + } ) | ) { \mathrm { d } } x + \lambda _ { + } R ^ { n } } \\ { \displaystyle \le \| { q } \| _ { L ^ { \infty } ( \Omega ) } \cdot \int _ { B _ { R } } ( F ( \| v \| _ { L ^ { \infty } ( B _ { R } ) } ) + F ( \| u \| _ { L ^ { \infty } ( B _ { R } ) } ) ) { \mathrm { d } } x + \lambda _ { + } R ^ { n } } \\ { \displaystyle \le C R ^ { n } , } \end{array}
$$

where we used the increasing property of $F$ , and the fact that $\| v \| _ { L ^ { \infty } ( B _ { R } ) } \leq \| v \| _ { L ^ { \infty } ( \partial B _ { R } ) } = \| u \| _ { L ^ { \infty } ( \partial B _ { R } ) } \leq \| u \| _ { L ^ { \infty } ( B _ { R } ) } \leq$ $\| u \| _ { L ^ { \infty } ( \Omega ) } \leq C$ ,which is guaranteed by the maximum principle.By (3O) and Lemma 11,for any $\lambda \in ( 0 , n )$ , there holds

$$
\int _ { B _ { R } } G ( | \nabla u | ) \mathrm { d } x \le C R ^ { n } + \int _ { B _ { R } } G ( | \nabla v | ) \mathrm { d } x \le C R ^ { n } + C R ^ { \lambda } \le C R ^ { \lambda } .
$$

Particulary,we have

$$
\int _ { B _ { R } } G ( | \nabla u | ) \mathrm { d } x \leq C R ^ { n + \alpha - 1 } .
$$

for any $\alpha \in ( 0 , 1 )$ . We conclude the desired result by Lemma 10.

Corollary 17 Assume further that $h \leq 0$ a.e. in $\Omega ,$ and $\varphi \geq 0$ on $\partial \Omega$ in the sense of trace. Then every minimizer of $\mathcal { I } ( u )$ over the set $\kappa$ is non-negative in $\Omega$

Proof Let $\xi = \operatorname* { m i n } \{ u , 0 \} \leq 0$ and $ { \varepsilon } \in ( 0 , 1 )$ . By the minimality of $u$ ,it follows

$$
\int _ { \Omega } \Big ( G ( | \nabla ( u - \varepsilon \xi ) | ) - G ( | \nabla u | ) + q \big ( F ( ( u - \varepsilon \xi ) ^ { + } ) - F ( u ^ { + } ) \big ) - h \varepsilon \xi + \lambda _ { + } \big ( \chi _ { \{ u - \varepsilon \xi > 0 \} } - \chi _ { \{ u > 0 \} } \big ) \Big ) \mathrm { d } x \geq 0
$$

Note that

$$
\begin{array}{c} \displaystyle \int _ { \Omega } q \big ( F ( ( u - \varepsilon \xi ) ^ { + } ) - F ( u ^ { + } ) \big ) \mathrm { d } x = \displaystyle \int _ { \{ u > 0 \} } q \big ( F ( ( u - \varepsilon \xi ) ^ { + } ) - F ( u ^ { + } ) \big ) \mathrm { d } x + \displaystyle \int _ { \{ u \leq 0 \} } q \big ( F ( ( u - \varepsilon \xi ) ^ { + } ) - F ( u ^ { + } ) \big ) \mathrm { d } x  \\ { = \displaystyle \int _ { \{ u > 0 \} } q \big ( F ( u ^ { + } ) - F ( u ^ { + } ) \big ) \mathrm { d } x + \displaystyle \int _ { \{ u \leq 0 \} } q \big ( F ( ( 1 - \varepsilon ) u ^ { + } ) - F ( u ^ { + } ) \big ) \mathrm { d } x } \\ { = 0 , } \end{array}
$$

and

$$
\int _ { \Omega } \lambda _ { + } ( \chi _ { \{ u - e \xi > 0 \} } - \chi _ { \{ u > 0 \} } ) \mathrm { d } x = \int _ { \{ u > 0 \} } \lambda _ { + } ( \chi _ { \{ u > 0 \} } - \chi _ { \{ u > 0 \} } ) \mathrm { d } x + \int _ { \{ u \leq 0 \} } \lambda _ { + } ( \chi _ { \{ ( 1 - e ) u > 0 \} } - \chi _ { \{ u > 0 \} } ) \mathrm { d } x = 0 ,
$$

Therefore

$$
\begin{array} { l } { 0 \le \displaystyle \frac { 1 } { \varepsilon } \int _ { \Omega } \Big ( G ( | \nabla ( u - \varepsilon \xi ) | ) - G ( | \nabla u | ) + q ( F ( ( u - \varepsilon \xi ) ^ { + } ) - F ( u ^ { + } ) ) - h \varepsilon \xi + \lambda _ { + } ( \chi _ { \{ u - \varepsilon \xi > 0 \} } - \chi _ { \{ u > 0 \} } ) \Big ) } \\ { \quad \le - \displaystyle \int _ { \Omega } g ( | \nabla u - \varepsilon \nabla \xi | ) \frac { \nabla u - \varepsilon \nabla \xi } { | \nabla u - \varepsilon \nabla \xi | } \nabla \xi \mathrm { d } x , } \end{array}
$$

where weuse the convxiy sf $G$ u $h \xi \ge 0$ a.e.in $\Omega$ Leting $\varepsilon \to 0 ^ { + }$ we get $\begin{array} { r } { \int _ { \Omega } \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u \nabla \xi \mathrm { d } x \ge 0 } \end{array}$ Itolows

$$
\int _ { \{ u < 0 \} } g ( | \nabla u | ) | \nabla u | \mathrm { d } x \le 0 ,
$$

which implies $u \equiv C$ or $u \geq 0$ a.e. in $\Omega$ . By the fact that $u = \varphi \geq 0$ on $\partial \Omega$ ,and the continuity of $u$ ,we conclude that $u \geq 0$ in $\Omega$ ■

Remark 4 Without restrictions on the sign of $h$ , it is easy to see by checking the proof ofTheorem 15 and 16 that there exists $a$ i $C _ { l o c } ^ { 0 , \alpha }$ $\widetilde { \mathcal { K } } = \{ v \in W ^ { 1 , G } ( \Omega ) :$ $v - \varphi \in W _ { 0 } ^ { 1 , G } ( \Omega ) , v \geq 0 a . e . i n \Omega \}$ provided a non-negative $\varphi$

# 4Local $C ^ { 1 , \alpha _ { - } }$ and Log-Lipschitz regularities of minimizers over the set $\kappa$ （20

In this section,we establish local $C ^ { 1 , \alpha _ { - } }$ and Log-Lipschitz continuities for minimizers of $\mathcal { I }$ with $\lambda _ { + } = 0$ and $\lambda _ { + } > 0$ respectively.

Theorem 18 (Local $C ^ { 1 , \alpha }$ -regularity of minimizers for $\lambda _ { + } = 0$ ） Let u be a minimizer of $\mathcal { I } ( u )$ over the set $\kappa$ with $\lambda _ { + } = 0$ Then $u \in C _ { l o c } ^ { 1 , \alpha } ( \Omega )$ for some $\alpha \in ( 0 , 1 )$ . More precisely,for any $\Omega ^ { \prime } \Subset \Omega$ , there exists a constant $C > 0$ ， depending only on $\begin{array} { r l } { { n , \theta _ { 0 } , f _ { 0 } , \delta _ { 0 } , g _ { 0 } , G ( 1 ) , \frac { 1 } { G ( 1 ) } , } } \end{array}$ $\| u \| _ { L ^ { \infty } ( \Omega ) }$ ， $\| h \| _ { L ^ { \infty } ( \Omega ) }$ ， $\| q \| _ { L ^ { \infty } ( \Omega ) } , \| \varphi \| _ { L ^ { \infty } ( \Omega ) }$ and $\Omega ^ { \prime }$ ， such that

$$
\| u \| _ { C ^ { 1 , \alpha } ( \Omega ^ { \prime } ) } \leq C .
$$

Theorem 19 (Local Log-Lipschitz regularity of minimizers for $\lambda _ { + } > 0$ ）Let u be a minimizer of $\mathcal { I } ( u )$ over the set $\kappa$ with $\lambda _ { + } > 0$ . Then u is locally Log-Lipschitz continuous. More precisely, for any $\Omega ^ { \prime } \Subset \Omega ,$ there exists a constant $C > 0$ ， depending only on $n , \theta _ { 0 } , f _ { 0 } , \delta _ { 0 } , g _ { 0 } , G ( 1 )$ $\frac { \mathbf { f } } { G ( 1 ) }$ $\| u \| _ { L ^ { \infty } ( \Omega ) } , \| h \| _ { L ^ { \infty } ( \Omega ) } , \mathsf { \bar { \Psi } } \| q \| _ { L ^ { \infty } ( \Omega ) } , \| \varphi \| _ { L ^ { \infty } ( \Omega ) }$ and $\Omega ^ { \prime }$ ， such that

$$
| u ( x ) - u ( y ) | \leq C | x - y | | \log | x - y | | ,
$$

for any $x , y \in \Omega ^ { \prime }$ . Therefore, $u \in C _ { l o c } ^ { 0 , \tau } ( \Omega )$ for any $\tau < 1$

Proof of Theorem 18Let $B _ { R } = B _ { R } ( x _ { 0 } )$ for some $R \leq R _ { 0 } \leq 1$ ,where $R _ { 0 }$ will be chosen later. Without loss of generality, assume that $B _ { r } \Subset B _ { R } \Subset \Omega$ ,and $B _ { r }$ and $B _ { R }$ have the same centre.Let $v$ be a $G -$ harmonic function in $B _ { R }$ that agrees with $u$ on the boundary, i.e.,

$$
\begin{array} { r } { \prime \displaystyle \frac { g ( | \nabla v | ) } { | \nabla v | } \nabla v = 0 \mathrm { i n } B _ { R } \mathrm { a n d } v - u \in W _ { 0 } ^ { 1 , G } ( B _ { R } ) . } \end{array}
$$

ByLemma13 andLemma 12,we have

$$
\begin{array} { r l } {  { \int _ { B _ { r } } G ( | \nabla u - ( \nabla u ) _ { r } | ) \mathrm { d } x \le C \bigg ( \frac { r } { R } \bigg ) ^ { n + \sigma } \int _ { B _ { R } } G ( | \nabla u - ( \nabla u ) _ { R } | ) \mathrm { d } x + C \int _ { B _ { R } } G ( | \nabla u - \nabla v | ) \mathrm { d } x } } \\ & { \le C \bigg ( \frac { r } { R } \bigg ) ^ { n + \sigma } \int _ { B _ { R } } G ( | \nabla u - ( \nabla u ) _ { R } | ) \mathrm { d } x + C \int _ { B _ { R } } ( G ( | \nabla u | ) - G ( | \nabla v | ) ) \mathrm { d } x } \\ & { \quad + C R ^ { \frac { 3 } { 2 } } \bigg ( \int _ { B _ { R } } ( G ( | \nabla u | ) - G ( | \nabla v | ) ) \mathrm { d } x \bigg ) ^ { \frac { 1 } { 2 } } , } \end{array}
$$

where $\lambda$ is an arbitrary constant in $( 0 , n )$

The minimality of $u$ and the increasing monotonicity of $F$ imply that

$$
\begin{array} { r l } { \displaystyle \int _ { B _ { R } } ( G ( | \nabla u | ) - G ( | \nabla v | ) ) \mathrm { d } x \le \displaystyle \int _ { B _ { R } } \bigg ( q ( F ( v ^ { + } ) - F ( u ^ { + } ) ) + h ( v - u ) \bigg ) \mathrm { d } x . } & { } \\ { \le \| q \| _ { L ^ { \infty } ( B _ { R } ) } \displaystyle \int _ { B _ { R } } | F ( v ^ { + } ) - F ( u ^ { + } ) | \mathrm { d } x + \| h \| _ { L ^ { \infty } ( B _ { R } ) } \displaystyle \int _ { B _ { R } } | v - u | \mathrm { d } x . } & { } \end{array}
$$

If $f$ in decreasing in $t > 0$ , we infer from $\left( F _ { 3 } \right)$ and $\left( F _ { 1 } \right)$ that

$$
\int _ { B _ { R } } | F ( v ^ { + } ) - F ( u ^ { + } ) | \mathrm { d } x = \int _ { B _ { R } \cap \{ v ^ { + } \geq u ^ { + } \} } ( F ( v ^ { + } ) - F ( u ^ { + } ) ) \mathrm { d } x + \int _ { B _ { R } \cap \{ v ^ { + } < u ^ { + } \} } ( F ( u ^ { + } ) - F ( v ^ { + } ) ) \mathrm { d } x
$$

$$
\begin{array} { r l } {  { \le \int _ { B _ { R } \cap \{ v ^ { + } \ge u ^ { + } \} } F ( v ^ { + } - u ^ { + } ) \mathrm { d } x + \int _ { B _ { R } \cap \{ v ^ { + } < u ^ { + } \} } F ( u ^ { + } - v ^ { + } ) \mathrm { d } x } } \\ { \le F ( 1 ) \operatorname* { m a x } \bigg \{ \int _ { B _ { R } } | v - u | ^ { 1 + \theta _ { 0 } } \mathrm { d } x , \int _ { B _ { R } } | v - u | ^ { 1 + f _ { 0 } } \mathrm { d } x \bigg \} } \\ { } & { = F ( 1 ) \int _ { B _ { R } } | v - u | ^ { 1 + \theta _ { 0 } } \mathrm { d } x } \\ & { \le C ( 1 + G ( 1 ) ) \int _ { B _ { R } } | v - u | ^ { 1 + \theta _ { 0 } } \mathrm { d } x } \end{array}
$$

where without loss of generality we assume that $\| v - u \| _ { L ^ { \infty } ( B _ { R } ) } \leq 1$ due to the boundedness of $v$ and $u$

A similar argument as in [20,(15) on page 44] gives

$$
\int _ { B _ { R } } | v - u | ^ { 1 + \theta _ { 0 } } \mathrm { d } x \leq C ( \varepsilon ) R ^ { n + \alpha _ { 0 } } + \varepsilon R ^ { \beta _ { 0 } } \int _ { B _ { R } } G ( | \nabla v - \nabla u | ) \mathrm { d } x ,
$$

where $\alpha _ { 0 } , \beta _ { 0 } > 0$ are independent of $R , \varepsilon _ { 0 }$ will be chosen later.

If $f$ in increasing in $t > 0$ ,we infer from $( F _ { 4 } ) , ( f _ { 1 } ) , ( f _ { 2 } )$ and the boundedness of $v$ and $u$ that

$$
\begin{array} { r l } { \int _ { \mathbb { R } _ { n } } | F ( y ^ { + } ) - F ( u ^ { + } ) | \mathrm { d } u = \int _ { \mathbb { R } _ { n } \cap \{ v \} = \emptyset } | F ( v ^ { + } ) - F ( u ^ { - } ) | \mathrm { d } u + \int _ { \mathbb { R } _ { n } \cap \{ v \} = \emptyset } | F ( v ^ { + } ) - F ( u ^ { + } ) | \mathrm { d } u } \\ { \le \int _ { \mathbb { R } _ { n } \cap \{ v \} = \emptyset + \emptyset } f ( \xi ) | v ^ { + } - u ^ { + } | \mathrm { d } u } \\ { \le \int _ { \mathbb { R } _ { n } \cap \{ v \} = \emptyset + \emptyset } f ( | \langle \xi | \sum _ { l = \emptyset } \eta _ { l } \rangle | v ^ { + } - u ^ { + } | \mathrm { d } u } \\ { \le \int _ { \mathbb { R } _ { n } \cap \{ v \} = \emptyset + \emptyset } f ( | \langle \eta | \sum _ { l = \emptyset } \eta _ { l } \rangle | v ^ { + } - u ^ { + } | \mathrm { d } u } \\ { \le \int _ { \mathbb { R } _ { n } \cap \{ v \} = \emptyset + \emptyset } f ( | \langle u | \vert \sum _ { l = \emptyset } \eta _ { l } \rangle | v ^ { + } - u ^ { + } | \mathrm { d } u } \\ { \le \int _ { \mathbb { R } _ { n } \cap \{ v \} = \emptyset + \emptyset + \emptyset } 1 + \int _ { \mathbb { R } _ { n } } \frac { 1 } { | \langle u | \vert \sum _ { l = \emptyset } \eta _ { l } \rangle | } | u | _ { \mathbb { R } ^ { n } \to \{ 0 , \} } | f ( | \rangle | v ^ { + } - u ^ { + } | \mathrm { d } u } \\ { \le \mathcal { C } ( | + \langle \xi | \Im \rangle ) \int _ { \mathbb { R } _ { n } } | v - u | \mathrm { d } u } \\ { \le \mathcal { C } ( | + \langle \xi | \Im \rangle ) \int _ { \mathbb { R } _ { n } } | v - u | \mathrm { d } u ; } \end{array}
$$

where $\xi \in ( \operatorname* { m i n } \{ u ^ { + } , v ^ { + } \} , \operatorname* { m a x } \{ u ^ { + } , v ^ { + } \} ) \subset ( 0 , \| u \| _ { L ^ { \infty } ( \Omega ) } )$ and $C$ is independent of $R$

Similarly, we get by [20, (16) on page 44]

$$
\int _ { B _ { R } } | v - u | \mathrm { d } x \leq C ( \varepsilon _ { 1 } ) R ^ { n + \alpha _ { 1 } } + \varepsilon _ { 1 } R ^ { \beta _ { 1 } } \int _ { B _ { R } } G ( | \nabla v - \nabla u | ) \mathrm { d } x ,
$$

where $\alpha _ { 1 } , \beta _ { 1 } > 0$ are independent of $R , \varepsilon _ { 1 }$ will be chosen later.

ByLemma 12,(34),(35),(36),(37) and (38),we always have

$$
\begin{array} { r l r } {  { \int _ { B _ { R } } G ( | \nabla u - \nabla v | ) \mathrm { d } x \le C R ^ { n + \alpha _ { 2 } } + C \varepsilon _ { 2 } R ^ { \beta _ { 2 } } \int _ { B _ { R } } G ( | \nabla u - \nabla v | ) \mathrm { d } x + C R ^ { \frac { \lambda } { 2 } + \frac { n + \alpha _ { 2 } } { 2 } } } } \\ & { } & { \quad + C \varepsilon _ { 2 } ^ { \frac { 1 } { 2 } } R ^ { \frac { \lambda } { 2 } + \frac { \beta _ { 2 } } { 2 } } \bigg ( \int _ { B _ { R } } G ( | \nabla u - \nabla v | ) \mathrm { d } x \bigg ) ^ { \frac { 1 } { 2 } } \qquad } \\ & { } & { \le C R ^ { n + \alpha _ { 2 } } + C \varepsilon _ { 2 } R ^ { \beta _ { 2 } } \int _ { B _ { R } } G ( | \nabla u - \nabla v | ) \mathrm { d } x + C R ^ { \frac { \lambda + n + \alpha _ { 2 } } { 2 } } + C R ^ { \lambda + \beta _ { 2 } } } \end{array}
$$

$$
+ \varepsilon _ { 2 } \int _ { B _ { R } } G ( | \nabla u - \nabla v | ) \mathrm { d } x ,
$$

Choosing $\varepsilon _ { 2 }$ small enough,we get

$$
\int _ { B _ { R } } G ( | \nabla u - \nabla v | ) \mathrm { d } x \leq C R ^ { m } ,
$$

where $\begin{array} { r } { m = \operatorname* { m i n } \{ n + \alpha _ { 2 } , \frac { \lambda + n + \alpha _ { 2 } } { 2 } , \lambda + \beta _ { 2 } \} . } \end{array}$

Finally, we get by (34),(35), (36), (37), (38) and (39)

$$
\int _ { B _ { R } } ( G ( | \nabla u | ) - G ( | \nabla v | ) ) { \mathrm { d } } x \leq C R ^ { n + \alpha _ { 2 } } + C R ^ { \beta _ { 2 } + m } .
$$

Putting (40) into (33), we obtain for all $0 < r \le R$ （204号

$$
\int _ { B _ { r } } G ( | \nabla u - ( \nabla u ) _ { r } | ) \mathrm { d } x \le C \bigg ( \frac { r } { R } \bigg ) ^ { n + \sigma } \int _ { B _ { R } } G ( | \nabla u - ( \nabla u ) _ { R } | ) \mathrm { d } x + C R ^ { n + \alpha _ { 2 } } + C R ^ { \beta _ { 2 } + m } + C R ^ { \frac { \lambda } { 2 } + \frac { n + \alpha _ { 2 } } { 2 } } + C R ^ { \frac { \lambda } { 2 } + \frac { n + \alpha _ { 2 } } { 2 } } .
$$

Due to the arbitrariness of $\lambda \in ( 0 , n )$ , we get $\begin{array} { r } { \operatorname* { m i n } \{ \beta _ { 2 } + m , \frac { \lambda } { 2 } + \frac { n + \alpha _ { 2 } } { 2 } } \end{array}$ ， $\begin{array} { r }  \frac { \lambda } { 2 } + \frac { \beta _ { 2 } + m } { 2 } \} > n \end{array}$ by setting $\operatorname* { m i n } \{ \lambda + \alpha _ { 2 } , \lambda + \beta _ { 2 } \} > n$ We conclude that there exists $\alpha _ { 3 } > 0$ such that

$$
\int _ { B _ { r } } G ( | \nabla u - ( \nabla u ) _ { r } | ) \mathrm { d } x \le C \bigg ( \frac { r } { R } \bigg ) ^ { n + \sigma } \int _ { B _ { R } } G ( | \nabla u - ( \nabla u ) _ { R } | ) \mathrm { d } x + C R ^ { n + \alpha _ { 3 } } .
$$

In view of Lemma 14, we conclude that there is a constant $\alpha _ { 4 } \in ( 0 , 1 )$ such that

$$
\int _ { B _ { r } } G ( | \nabla u - ( \nabla u ) _ { r } | ) \mathrm { d } x \leq C r ^ { n + \alpha _ { 4 } } .
$$

Proceeding exactly as in [2O, (22) on page 46)], we conclude that there is a constant $\alpha \in ( 0 , 1 )$ such that

$$
\int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | \mathrm { d } x \leq C r ^ { n + \alpha } ,
$$

which and Campanato's Embedding Theorem give the Holder continuity of the gradient of $u$ =

Proof of Theorem 19 For any fixed $x _ { 0 } \in \Omega$ ,let $R > 0$ such that $R < \mathrm { d i s t } ( x _ { 0 } , \partial \Omega )$ . As before, we denote $B _ { R } = B _ { R } ( x _ { 0 } )$ . Let $h$ be the $G$ -harmonic function in $B _ { R }$ that agrees with $u$ on the boundary, i.e.,

$$
\cdot \frac { g ( | \nabla h | ) } { | \nabla h | } \nabla h = 0 \mathrm { i n } B _ { R } \mathrm { a n d } h - u \in W _ { 0 } ^ { 1 , G } ( B _ { R } ) .
$$

It suffices to note that $\begin{array} { r } { \int _ { B _ { R } } ( \lambda _ { + } \chi _ { \{ h > 0 \} } - \lambda _ { + } \chi _ { \{ u > 0 \} } ) \mathrm { d } x \le \lambda _ { + } R ^ { n } } \end{array}$ . Proceeding as in the proof of Theorem 18, we have

$$
\int _ { B _ { r } } G ( | \nabla u - ( \nabla u ) _ { r } | ) \mathrm { d } x \leq C \bigg ( \frac { r } { R } \bigg ) ^ { n + \sigma } \int _ { B _ { R } } G ( | \nabla u - ( \nabla u ) _ { R } | ) \mathrm { d } x + C R ^ { n } ,
$$

for all $0 < r \leq R$ . Then Lemma 14 gives

$$
\int _ { B _ { r } } G ( | \nabla u - ( \nabla u ) _ { r } | ) \mathrm { d } x \leq C r ^ { n } .
$$

Finally,

$$
\int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | \mathrm { d } x \leq C r ^ { n } ,
$$

which shows that the gradient of $u$ lies in BMO space and for any fixed subdomain $\Omega ^ { \prime } \Subset \Omega$ ,there holds $\| u \| _ { B M O ( \Omega ^ { \prime } ) } \leq C$ for a universal constant $C > 0$ . The residual argument is the same as in [14,Section 5],and the desired result can be obtained.■

# 5Growth rates near the free boundary for nonnegative minimizers of $\mathcal { I } ( u )$

In view of Corollary_17 or Remark 4, we may consider non-negative minimizers of $\mathcal { I } ( u )$ and establish their growth rates near the free boundary $\partial \{ u > 0 \}$ for $\lambda _ { + } = 0$ and $\lambda _ { + } > 0$ respectively.

Theorem 20 (Growth rates for $\lambda _ { + } = 0$ ） Let u be a non-negative minimizer of $\mathcal { I } ( u )$ with $\lambda _ { + } = 0 .$ Assume taht $x _ { 0 } \in \partial \{ u >$ $0 \}$ and $B _ { r _ { 0 } } ( x _ { 0 } ) \Subset \Omega$ Then there exists universal constants $C _ { 0 } , C _ { 1 }$ , depending only on $n , \theta _ { 0 } , f _ { 0 } , \delta _ { 0 } , g _ { 0 } , G ( 1 )$ （ $\textstyle { \frac { 1 } { G ( 1 ) } }$ ， $\| u \| _ { L ^ { \infty } ( \Omega ) }$ （ $\| h \| _ { L ^ { \infty } ( \Omega ) } , \| q \| _ { L ^ { \infty } ( \Omega ) } , \| \varphi \| _ { L ^ { \infty } ( \Omega ) }$ and $B _ { r _ { 0 } } ( x _ { 0 } )$ ，such that

$$
\begin{array} { r l } & { | u ( x ) | \leq C _ { 0 } \Phi ( | x - x _ { 0 } | ) , \quad \forall x \in B _ { r _ { 0 } } ( x _ { 0 } ) , } \\ & { | \nabla u ( x ) | \leq C _ { 1 } \Phi ^ { \prime } ( | x - x _ { 0 } | ) , \quad \forall x \in B _ { r _ { 0 } } ( x _ { 0 } ) . } \end{array}
$$

Theorem 21 (Growth rates for $\lambda _ { + } > 0$ ） Let u be a non-negative minimizer of $\mathcal { I } ( u )$ with $\lambda _ { + } > 0$ Assume that $x _ { 0 } \in \partial \{ u >$ $0 \}$ and $B _ { r _ { 0 } } ( x _ { 0 } ) \Subset \Omega$ . Then there exists a universal constant $C _ { 2 }$ ,depending only on $n , \theta _ { 0 } , f _ { 0 } , \delta _ { 0 } , g _ { 0 } , G ( 1 )$ $\frac { 1 } { G ( 1 ) }$ ， $\| u \| _ { L ^ { \infty } ( \Omega ) }$ （号 $\| h \| _ { L ^ { \infty } ( \Omega ) } , \| q \| _ { L ^ { \infty } ( \Omega ) } , \| \varphi \| _ { L ^ { \infty } ( \Omega ) }$ and ${ \bf \Gamma } _ { r _ { 0 } } ( x _ { 0 } )$ such that

$$
| u ( x ) | \leq C _ { 2 } | x - x _ { 0 } | , \quad \forall x \in B _ { r _ { 0 } } ( x _ { 0 } ) ,
$$

for all $0 < r < r _ { 0 }$

Proof of Theorem 20 Due to the local property,we may assume that $u$ is a non-negative minimizer of $\mathcal { I } ( u )$ associated with the domain $B _ { 1 } ( x _ { 0 } )$ with $x _ { 0 } = 0$ . Firstly, we prove (43). Let $S ( j , u ) = \operatorname* { s u p } _ { x \in B _ { 2 ^ { - j } } } | u ( \bar { x } ) |$ . It suffices to show that for all $j \in \mathbb N$ （20

there holds

$$
S ( j + 1 , u ) \leq \operatorname* { m a x } \left\{ c \Phi ( 2 ^ { - j } ) , S ( j , u ) \Phi ( 2 ^ { - 1 } ) , . . . , S ( j - m , u ) \Phi ( 2 ^ { - ( m + 1 ) } ) , . . . , S ( 0 , u ) \Phi ( 2 ^ { - j - 1 } ) \right\} ,
$$

with some constant $c > 0$ . We prove by contradiction.Let us suppose (46) fails. Then for any $k \in \mathbb { N }$ ,there exists a sequence of integers $j _ { k } \in \mathbb { N }$ and a sequence of minimizers $u _ { k }$ such that

$$
S ( j _ { k } + 1 , u _ { k } ) > \operatorname* { m a x } \Big \{ k \Phi ( 2 ^ { - j _ { k } } ) , S ( j _ { k } , u _ { k } ) \Phi ( 2 ^ { - 1 } ) , . . . , S ( j _ { k } - m , u _ { k } ) \Phi ( 2 ^ { - ( m + 1 ) } ) , . . . , S ( 0 , u _ { k } ) \Phi ( 2 ^ { - j _ { k } - 1 } ) \Big \}
$$

Notice that by (47) and the boundedness of $u _ { k }$ , it follows that $j _ { k } \to \infty$ as $k  \infty$

Let $\begin{array} { r } { v _ { k } ( x ) \ = \ \frac { u _ { k } ( 2 ^ { - j _ { k } } x ) } { S ( j _ { k } + 1 , u _ { k } ) } } \end{array}$ ， $\sigma _ { k } = 2 ^ { j _ { k } } S ( j _ { k } + 1 , u _ { k } )$ ， $\begin{array} { r } { G _ { k } ( t ) \ = \ \frac { G ( \sigma _ { k } t ) } { \sigma _ { k } g ( \sigma _ { k } ) } } \end{array}$ $\begin{array} { r } { g _ { k } ( t ) = G _ { k } ^ { \prime } ( t ) , F _ { k } ( t ) = \frac { F ( S ( j _ { k } + 1 , u _ { k } ) t ) } { \sigma _ { j } g ( \sigma _ { k } ) } } \end{array}$ win $f _ { k } ( t ) = F _ { k } ^ { \prime } ( t )$ ， $q _ { k } ( x ) = q ( 2 ^ { - j _ { k } } x )$ and $\begin{array} { r } { h _ { k } ( x ) = \frac { S ( j _ { k } + 1 , u _ { k } ) } { \sigma _ { k } g ( \sigma _ { k } ) } h ( 2 ^ { - j _ { k } } x ) } \end{array}$ .By $( G _ { 5 } ) , G _ { k }$ and $F _ { k }$ satisfy (1)and (2) with the same constants $\delta _ { 0 } , g _ { 0 } , \theta _ { 0 } \mathrm { a n d } f _ { 0 }$ . For all $k > 0$ $v _ { k }$ is a minimizerof the functional $\begin{array} { r } { \int _ { B _ { 2 ^ { j _ { k } } } } \big ( G _ { k } ( | \nabla v | ) + q _ { k } F _ { k } ( v ^ { + } ) + h _ { k } v \big ) \mathrm { d } x } \end{array}$ . Indeed, by a simple calculation we have

$$
\int _ { B _ { 2 ^ { j _ { k } } } } \big ( G _ { k } ( | \nabla v _ { k } | ) + q _ { k } F _ { k } ( v _ { j } ^ { + } ) + h _ { k } v _ { k } \big ) \mathrm { d } x = \frac { 2 ^ { j _ { k } n } } { \sigma _ { k } g ( \sigma _ { k } ) } \int _ { B _ { 1 } } \big ( G ( | \nabla u | ) + q F ( u ^ { + } ) + h u \big ) \mathrm { d } x .
$$

Particularly, $v _ { k }$ is a minimizer of the following functional

$$
\mathcal { I } _ { k } = \int _ { B _ { R } } \big ( G _ { k } ( | \nabla v | ) + q _ { k } F _ { k } ( v ^ { + } ) + h _ { k } v \big ) \mathrm { d } x ,
$$

provided $R = 2 ^ { m } < 2 ^ { j _ { k } } , m$ is fixed.

Notice that by (47) and the definition of $\Phi$ ,we have $\operatorname* { s u p } | v _ { k } | \leq C \Phi ( R )$ ,and BR

$$
S ( j _ { k } + 1 , u _ { k } ) \geq k \Phi ( 2 ^ { - j _ { k } } ) = k ( 2 ^ { - j _ { k } } ) ^ { p _ { 0 } } ,
$$

which gives

$$
\begin{array} { r l } & { 2 ^ { ( 1 + \delta _ { 0 } ) j _ { k } } ( S ( j _ { k } + 1 , u _ { k } ) ) ^ { \delta _ { 0 } - \theta _ { 0 } } \geq k ^ { \delta _ { 0 } - \theta _ { 0 } } 2 ^ { ( 1 + \delta _ { 0 } ) j _ { k } } ( 2 ^ { - j _ { k } } ) ^ { p _ { 0 } ( \delta _ { 0 } - \theta _ { 0 } ) } } \\ & { \qquad = ( 2 ^ { j _ { k } } ) ^ { 1 + \delta _ { 0 } - p _ { 0 } ( \delta _ { 0 } - \theta _ { 0 } ) } k ^ { \delta _ { 0 } - \theta _ { 0 } } } \\ & { \qquad \geq k ^ { \delta _ { 0 } - \theta _ { 0 } } , } \end{array}
$$

and

$$
\begin{array} { r l } & { 2 ^ { ( 1 + \delta _ { 0 } ) j _ { k } } ( S ( j _ { k } + 1 , u _ { k } ) ) ^ { g _ { 0 } - \theta _ { 0 } } \geq k ^ { g _ { 0 } - \theta _ { 0 } } 2 ^ { ( 1 + g _ { 0 } ) j _ { k } } ( 2 ^ { - j _ { k } } ) ^ { p _ { 0 } ( g _ { 0 } - \theta _ { 0 } ) } } \\ & { \qquad \geq k ^ { g _ { 0 } - \theta _ { 0 } } , } \end{array}
$$

Then we get by $( F _ { 1 } ) , ( G _ { 2 } ) , ( G _ { 3 } )$ ,(48),(49) and $\operatorname* { s u p } _ { B _ { R } } | v _ { k } | \leq C \Phi ( R )$

$$
\begin{array} { r l } { | q _ { k } F _ { k } ( v _ { k } ^ { + } ) | = | q _ { k } | \frac { F ( S ( j _ { k } + 1 , u _ { k } ) v _ { k } ^ { + } ) } { \sigma _ { k } \mathcal { J } ( \mathcal { J } _ { k } ) } } \\ & { \leq \frac { C | S ( j _ { k } + 1 , u _ { k } ) | ^ { 1 + \theta _ { 0 } } F ( v _ { k } ^ { + } ) } { \sigma _ { k } \mathcal { J } ( \mathcal { J } ( k ) ) } } \\ & { \leq \frac { C | S ( j _ { k } + 1 , u _ { k } ) | ^ { 1 + \theta _ { 0 } } F ( v _ { k } ^ { + } ) } { \operatorname* { m i n } \{ ( 2 ^ { j _ { k } } S ( j _ { k } + 1 , u _ { k } ) ) ^ { 1 + \delta _ { 0 } } , ( 2 ^ { j _ { k } } S ( j _ { k } + 1 , u _ { j } ) ) ^ { 1 - \theta _ { 0 } } \} } } \\ & { \leq \frac { C | S ( j _ { k } , S ( j _ { k } + 1 , u _ { k } ) ) | ^ { \alpha _ { 0 } } - \mathcal { C } } { \operatorname* { m i n } \{ 2 ^ { ( 1 + \delta _ { 0 } ) j _ { k } } ( S ( j _ { k } + 1 , u _ { k } ) ) ^ { \delta _ { 0 } - \theta _ { 0 } } , ( 2 ^ { ( 1 + \delta _ { 0 } ) j _ { k } } ( S ( j _ { k } + 1 , u _ { k } ) ) ^ { \theta _ { 0 } - \theta _ { 0 } } \} } } \\ & { \leq \frac { C } { \operatorname* { m i n } \{ k ^ { \delta _ { 0 } - \theta _ { 0 } } , k ^ { \delta _ { 0 } - \theta _ { 0 } } \} } \to 0 , \ \mathrm { a s } \ k \to \infty . } \end{array}
$$

Similarly, due to that $2 ^ { ( 1 + \delta _ { 0 } ) j _ { k } } ( S ( j _ { k } + 1 , u _ { k } ) ) ^ { \delta _ { 0 } } \geq k ^ { \delta _ { 0 } }$ ,and $2 ^ { ( 1 + \delta _ { 0 } ) j _ { k } } ( S ( j _ { k } + 1 , u _ { k } ) ) ^ { g _ { 0 } } \geq k ^ { g _ { 0 } }$ , we have $| h _ { k } | \to 0$ as $k  \infty$ For $k$ large enough, according to the $C ^ { 1 , \alpha }$ regularity of minimizers, we obtain $\| v _ { k } \| _ { C ^ { 1 , \alpha } ( B _ { R } ) } \leq C$ (see Theorem 18). Note that $C$ depends on $\displaystyle \frac { 1 } { G _ { k } ( 1 ) }$ and $G _ { k } ( 1 )$ . However by $\left( G _ { 5 } \right)$ , we see that $C$ depends on $\frac { 1 } { G ( 1 ) }$ and $G ( 1 )$ essentilly,uisindeen of $k$ . Therefore, up to subsequence, we get $v _ { k } \to v _ { 0 }$ in $C ^ { 1 , \beta } ( B _ { r _ { 0 } } )$ with $0 < \beta < \alpha$ and any $r _ { 0 } < 1$ . We deduce by $v _ { k } ( 0 ) = 0$ and $\operatorname* { s u p } | v _ { k } | = 1$ that

$B _ { \frac { 1 } { 2 } }$

$$
\operatorname* { s u p } _ { B _ { \frac { 1 } { 2 } } } | v _ { 0 } | = 1 , v _ { 0 } ( 0 ) = 0 ,
$$

On the other hand,using the compactcondition (5),we conclude that (see [5,Theorem 6.1]) there exists afunction $G _ { \infty } \in$ $C ^ { 2 } ( 0 , + \infty )$ such that, up to a subsequence,

$G _ { k } \to G _ { \infty } , g _ { k } = G _ { k } ^ { \prime } \to G _ { \infty } ^ { \prime } = g _ { \infty }$ uniformly in compact subsets of $[ 0 , + \infty )$ ， $G _ { k } ^ { \prime \prime } \to G _ { \infty } ^ { \prime \prime }$ uniformly in compact subsets of $( 0 , + \infty )$ ，

and $g _ { \infty }$ satisfies structural condition(1) with the same constants.Furthermore,we infer that $\scriptstyle v _ { 0 }$ isa $G _ { \infty }$ -harmonic function in $B _ { 1 }$ . Since $v _ { k } \geq 0$ in $B _ { 1 }$ ， $v _ { 0 } \geq 0$ in ${ B } _ { r _ { 0 } }$ . Recalling $v _ { 0 } ( 0 ) = 0$ and the Harnack's inequality, we have $v _ { 0 } \equiv 0$ in ${ B } _ { r _ { 0 } }$ . Finally we get $v _ { 0 } \equiv 0$ in $B _ { 1 }$ due to the continuity of $\scriptstyle v _ { 0 }$ and the arbitrariness of $r _ { 0 }$ . which is a contradiction with (51). Therefore have proved (43).

Now, we prove (44). Set $S ( j , | \nabla u | ) = \operatorname* { s u p } _ { x \in B _ { 2 } - j } | \nabla u ( x ) |$ .It suffices to show

$$
\begin{array} { r } { S ( j + 1 , | \nabla u | ) \le \operatorname* { m a x } \bigg \{ c \Phi ^ { \prime } ( 2 ^ { - j } ) , S ( j , | \nabla u | ) \Phi ^ { \prime } ( 2 ^ { - 1 } ) , \ldots , S ( j - m , | \nabla u | ) \Phi ^ { \prime } ( 2 ^ { - ( m + 1 ) } ) , } \\ { \ldots , S ( 0 , | \nabla u | ) \Phi ^ { \prime } ( 2 ^ { - j - 1 } ) \bigg \} . } \end{array}
$$

for some positive constant $c$ .By contradiction, suppose that (52) fails. Then for any $k \in \mathbb { N }$ , there exists a sequence of integers $j _ { k }$ and a sequence of minimizers $u _ { k }$ such that

$$
\begin{array} { r l } & { S ( j _ { k } + 1 , | \nabla u _ { k } | ) > \operatorname* { m a x } \big \{ k \Phi ^ { \prime } ( 2 ^ { - j _ { k } } ) , S ( j _ { k } , | \nabla u _ { k } | ) \Phi ^ { \prime } ( 2 ^ { - 1 } ) , . . . , S ( j _ { k } - m , | \nabla u _ { k } | ) \Phi ^ { \prime } ( 2 ^ { - ( m + 1 ) } ) , } \\ & { ~ \quad \quad \quad \quad \quad \quad \quad . . . , S ( 0 , | \nabla u _ { k } | ) \Phi ^ { \prime } ( 2 ^ { - j _ { k } - 1 } ) \big \} . } \end{array}
$$

Let $\begin{array} { r } { v _ { k } ( x ) \ = \ \frac { u _ { k } ( 2 ^ { - j _ { k } } x ) } { 2 ^ { - j _ { k } } S ( j _ { k } + 1 , u _ { k } ) } } \end{array}$ ， $\varrho _ { k } = S ( j _ { k } + 1 , u _ { k } )$ ， $\begin{array} { r } { G _ { k } ( t ) \ = \ \frac { G ( \varrho _ { k } t ) } { \varrho _ { k } g ( \varrho _ { k } ) } } \end{array}$ with $\begin{array} { r } { g _ { k } ( t ) = G _ { k } ^ { \prime } ( t ) , F _ { k } ( t ) = \frac { F ( S ( j _ { k } + 1 , u _ { k } ) t ) } { \sigma _ { j } g ( \varrho _ { k } ) } } \end{array}$ with $f _ { k } ( t ) = F _ { k } ^ { \prime } ( t )$ 2， $q _ { k } ( x ) = q ( 2 ^ { - j _ { k } } x )$ and $\begin{array} { r } { h _ { k } ( x ) = \frac { S ( j _ { k } + 1 , u _ { k } ) } { \varrho _ { k } g ( \varrho _ { k } ) } h ( 2 ^ { - j _ { k } } x ) } \end{array}$ Then foral $k > 0$ $v _ { k }$ isaminimizer of the unetinal $\begin{array} { r } { \int _ { B _ { 2 ^ { j _ { k } } } } \big ( G _ { k } ( | \nabla v | ) + q _ { k } F _ { k } ( v ^ { + } ) + h _ { k } v \big ) \mathrm { d } x } \end{array}$ .By (43) and (53),we have $\begin{array} { r } { \operatorname* { s u p } _ { B _ { 1 } } | v _ { k } | \le \frac { C } { k } \to 0 } \end{array}$ as $k  \infty$ . Arguing as before, we get $| q _ { k } F _ { k } ( v _ { k } ^ { + } ) |  0$ and $| h _ { k } |  0$ as $k  \infty$ , and we can conclude that there exists a $G _ { \infty }$ -harmonic function $v _ { 0 }$ in $B _ { 1 }$ ， satisfying $v _ { k } \to v _ { 0 }$ i $C ^ { 1 , \beta } ( B _ { r _ { 0 } } )$ with some $\beta \in ( 0 , 1 )$ and any $r _ { 0 } < 1$ . Furthermore, we conclude that $v _ { 0 } \equiv 0$ m $B _ { 1 }$ . However, note that sup $| \nabla v _ { j _ { k } } | = 1$ . Thus sup $| \nabla v _ { 0 } | = 1$ , which gives a contradiction.

Proof of Theorem 21 Let $\Phi ( t ) = t ^ { p _ { 0 } }$ for all $t \geq 0$ ， where $\begin{array} { r } { p _ { 0 } = \operatorname* { m i n } \{ \frac { 1 + g _ { 0 } } { g _ { 0 } - \theta _ { 0 } } , \frac { 1 + \delta _ { 0 } } { \delta _ { 0 } - \theta _ { 0 } } , \frac { 1 + g _ { 0 } } { g _ { 0 } } , 1 \} = 1 . } \end{array}$ Then one can proceed with a slight modification of the proof of Theorem 20 to obtain $| u ( x ) | \leq C _ { 2 } \bar { \Phi } ( | x - x _ { 0 } | )$

Corollary 22 (Optimal growths in the non-homogenous one-phase problems for $p$ -Laplacian） Let $G ( t ) = t ^ { p }$ with $p >$ 1, and $F ( t ) = t ^ { \gamma }$ with $0 < \gamma < p$ .Let u be a nonnegative minimizer of $\mathcal { I } ( u )$ with $\lambda + = 0$ in (3). Assume that $x _ { 0 } \in \partial \{ u > 0 \}$ Then there exists a universal constant $C$ such that

$$
| u ( x ) | \leq C | x - x _ { 0 } | ^ { p _ { 0 } } , | \nabla u ( x ) | \leq C | x - x _ { 0 } | ^ { p _ { 0 } - 1 } , \forall x \in B _ { r _ { 0 } } ( x _ { 0 } ) \Subset \Omega
$$

for all $0 < r < r _ { 0 }$ ,where $\begin{array} { r } { p _ { 0 } = \operatorname* { m i n } \{ \frac { p } { p - \gamma } , \frac { p } { p - 1 } \} > 1 } \end{array}$

Remark5 Checking theproofof Theorem 20,if $h = 0$ and u is a nonnegative minimizer of $\mathcal { I } ( u )$ with $\lambda + = 0$ in (3), then we have

$$
| u ( x ) | \leq C | x - x _ { 0 } | ^ { p _ { 1 } } , | \nabla u ( x ) | \leq C | x - x _ { 0 } | ^ { p _ { 1 } - 1 } , \forall x \in B _ { r _ { 0 } } ( x _ { 0 } ) \Subset \Omega
$$

where $\begin{array} { r } { p _ { 1 } = \operatorname* { m i n } \{ \frac { 1 + g _ { 0 } } { g _ { 0 } - \theta _ { 0 } } , \frac { 1 + \delta _ { 0 } } { \delta _ { 0 } - \theta _ { 0 } } \} } \end{array}$ .Particularly, if $G ( t ) = t ^ { p } , p > 1$ and $F ( t ) = t ^ { \gamma } , 0 < \gamma < p$ we have

$$
| u ( x ) | \leq C | x - x _ { 0 } | ^ { \frac { p } { p - \gamma } } , | \nabla u ( x ) | \leq C | x - x _ { 0 } | ^ { \frac { \gamma } { p - \gamma } } , \forall x \in B _ { r _ { 0 } } ( x _ { 0 } ) \Subset \Omega ,
$$

which are the optimal growth rates of minimizers andtheir gradients in the homogeneous one-phase free boundary problem for $p$ -Laplacian.

Remark 6 Condition (5) is used only for the compactness of $G _ { k }$ by blow-up techniques,see, e.g., [5, Theorem 6.1]. For the case of p-Laplacian, i.e., $G ( t ) = t ^ { p }$ ,(5) becomes trivial due to that $Q ^ { \prime } ( s ) \equiv 0$ ：

# 6Local Lipschitz continuity of non-negative minimizers of $\mathcal { I } ( u )$ with $\lambda _ { + } > 0$

In this section, in order to obtain local Lipschitz continuity of non-negative minimizers of $\mathcal { I } ( u )$ with $\lambda _ { + } > 0$ ,we make further assumptions on $F$ ,i.e., assume that $F \in \overset { \cdot } { C } ^ { 1 } ( [ 0 , + \infty ) ; [ 0 , \overset { \cdot } { + } \infty ) )$ . Note that $f \in C ( [ 0 , + \infty ) ; [ 0 , + \infty ) )$ and there exists positive constants $C _ { 1 }$ and $C _ { 2 }$ such that $f ( t ) \leq C _ { 1 } + \bar { C } _ { 2 } g ( t )$ for all $t \geq 0$

We say that a function $u \in W ^ { 1 , G } ( D )$ is a weak solution of the equation div $\begin{array} { r } { \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u = q f ( u ) ~ \mathrm { i n } ~ D , } \end{array}$ if

$$
\int _ { D } \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u \nabla \xi \mathrm { d } x + \int _ { D } ( q f ( u ) + h ) \xi \mathrm { d } x = 0
$$

holds for all $\xi \in W _ { 0 } ^ { 1 , \tilde { G } } ( D )$ , where $D$ is a domain.

Lemma 23 (Harnack's inequality）Let $u \in W ^ { 1 , G } ( B _ { R } )$ with $0 \leq u \leq M$ is a weak solution of div $\begin{array} { r } { \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u = q f ( u ) + h } \end{array}$ （204号 in $B _ { R }$ . Then, there exists a universal constant $t _ { 0 } > 0$ and a constant $C _ { r } > 0$ depending only on $\delta _ { 0 } , g _ { 0 } , M , t _ { 0 } , \| q \| _ { L ^ { \infty } ( B _ { R } ) }$ and $R - r$ such that

$$
\operatorname* { s u p } _ { B _ { r } } u \leq C _ { r } \biggl ( \operatorname* { i n f } _ { B _ { r } } u + g ^ { - 1 } ( R ) R \biggr ) ,
$$

for all $0 < r \le R$

Proof It is a direct result of [16, Corollary 1.4]. Indeed, we amy set $a _ { 1 } = a _ { 2 } = a _ { 4 } = a _ { 5 } = 0$ and $a _ { 3 } = 1$ in (1.3a) and (1.3b) of[16,Corollry1.4]forourproblem.Weshalverify thatconditions (1.3c)”and(1.4)of[16,Corollry1.4]aresatisfd.By $\left( f _ { 2 } \right)$ , there exits $t _ { 0 } > 0$ such that for all $t > t _ { 0 }$ , there holds

$$
\begin{array} { r l } & { f ( t ) \le g ( t ) = g \bigg ( \displaystyle \frac { t } { R } \cdot R \bigg ) } \\ & { \qquad \le g \bigg ( \displaystyle \frac { t } { R } \bigg ) \displaystyle \frac { t } { R } \frac { R } { t } \operatorname* { m a x } \{ R ^ { \delta _ { 0 } } , R ^ { g _ { 0 } } \} \quad \mathrm { b y ~ } ( g _ { 1 } ) } \\ & { \qquad \le \displaystyle \frac { 1 } { t _ { 0 } } \cdot g \bigg ( \displaystyle \frac { t } { R } \bigg ) \displaystyle \frac { t } { R } , } \end{array}
$$

where without loss of generality we assume that $R \leq 1$ .For $0 \leq t \leq t _ { 0 }$ , due to $F \in C ^ { 1 } ( [ 0 , + \infty ) ; [ 0 , + \infty ) \rangle$ ， $f ( t ) = F ^ { \prime } ( t )$ is continuous in $[ 0 , t _ { 0 } ]$ . Then there exists a constant $M _ { 0 } > 0$ such that $f ( t ) \leq M _ { 0 }$ for all $t \in [ 0 , t _ { 0 } ]$ . Then for all $t \geq 0$ ,we have

$$
f ( t ) \leq \frac { 1 } { t _ { 0 } } \cdot g \left( \frac { t } { R } \right) \frac { t } { R } + M _ { 0 } .
$$

Thus we can choose $\begin{array} { r } { b _ { 0 } = 0 , b _ { 1 } = \frac { 1 } { t _ { 0 } } \cdot \| q \| _ { L ^ { \infty } ( B _ { R } ) } , b _ { 2 } = M _ { 0 } \cdot \| q \| _ { L ^ { \infty } ( B _ { R } ) } + \| h \| _ { L ^ { \infty } ( B _ { R } ) } } \end{array}$ and $\chi = g ^ { - 1 } ( b _ { 2 } R )$ in (1.3c)” and (1.4) of [16,Corollary 1.4]. Finally, by $\left( \tilde { g } _ { 1 } \right)$ and [16, Corollary 1.4], we have

$$
\begin{array} { r } { \underset { B _ { r } } { \operatorname* { s u p } } u \leq C \biggr ( \underset { B _ { r } } { \operatorname* { i n f } } u + g ^ { - 1 } ( b _ { 2 } R ) R \biggr ) \leq C ^ { \prime } \biggr ( \underset { B _ { r } } { \operatorname* { i n f } } u + g ^ { - 1 } ( R ) R \biggr ) . } \end{array}
$$

A consequence of Theorem 16 is the fact that $\{ u > 0 \}$ is an open set. We have the following result.

Lemma 24 Let u be a non-negative minimizer of $\mathcal { I } ( u ) w i t h \lambda _ { + } > 0$ in (3). Then u is a weak solution of the following equatiol

$$
d i \nu \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u = q f ( u ) + h \quad i n \ \{ u > 0 \} .
$$

Proof For any ball $B \subset \{ u \ > \ 0 \}$ ，consider first that $\xi \in C _ { 0 } ^ { \infty } ( B )$ . There exists $0 ~ < ~ \varepsilon _ { 0 } ~ \le ~ 1$ small enough such that $\{ u \pm \varepsilon \xi > 0 \} \cap B = B$ for all $0 < \varepsilon \le \varepsilon _ { 0 }$ . Standard arguments implies that

$$
\operatorname* { l i m } _ { \varepsilon \to 0 ^ { + } } \int _ { B } \frac { F ( ( u + \varepsilon \xi ) ^ { + } ) - F ( u ^ { + } ) } { \varepsilon } \mathrm { d } x = \int _ { B } f ( u ) \xi \mathrm { d } x .
$$

The minimality of $u$ implies that

$$
\begin{array} { r l } & { 0 \le \displaystyle \frac { 1 } { \varepsilon } \int _ { B } \Big ( G ( | \nabla ( u + \varepsilon \xi ) | ) - G ( | \nabla u | ) + q ( F ( ( u + \varepsilon \xi ) ^ { + } ) - F ( u ^ { + } ) ) \Big ) \mathrm { d } x } \\ & { \quad \le \displaystyle \int _ { B } g ( | \nabla u + \varepsilon \nabla \xi | ) \frac { \nabla u + \varepsilon \nabla \xi } { | \nabla u + \varepsilon \nabla \xi | } \nabla \xi \mathrm { d } x + \frac { 1 } { \varepsilon } \left( \displaystyle \int _ { B } q ( F ( ( u + \varepsilon \xi ) ^ { + } ) - F ( u ^ { + } ) ) \mathrm { d } x + \displaystyle \int _ { B } h \varepsilon \xi \mathrm { d } x \right) , } \end{array}
$$

where in the last inequality we used the convexity of $G$

From (55), (56) and letting $\varepsilon \to 0 ^ { + }$ , we get

$$
\int _ { B } \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u \nabla \xi \mathrm { d } x + \int _ { B } ( q f ( u ) + h ) \xi \mathrm { d } x \geq 0 .
$$

Using the function $\phi = u - \varepsilon \xi$ and repeating the previous arguments we get

$$
- \int _ { B } \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u \nabla \xi \mathrm { d } x - \int _ { B } ( q f ( u ) + h ) \xi \mathrm { d } x \ge 0 ,
$$

for all $\xi \in C _ { 0 } ^ { \infty } ( B )$ . By (57)and (58),(54) holdsfor all $\xi \in C _ { 0 } ^ { \infty } ( B )$ . Now for $\xi \in W _ { 0 } ^ { 1 , \tilde { G } } ( B )$ , let $\xi _ { n } \in C _ { 0 } ^ { \infty } ( B )$ with $\xi _ { n } \to \xi$ （20 in $W _ { 0 } ^ { 1 , \tilde { G } } ( B )$ s $n  \infty$ ,then (54) holds with $\xi _ { n } \in C _ { 0 } ^ { \infty } ( B )$ . We conclude thedesiredresult byleting $n  \infty$ and the arbitrariness of $B$

Theorem 25 (Local Lipschitz continuity for $\lambda _ { + } > 0$ ） Given a subdomain $\Omega ^ { \prime } \Subset \Omega$ ，there exists a constant $C > 0$ that depends only on $\Omega ^ { \prime }$ and universal constants, such that for any nonnegative minimizer of $\mathcal { I } ( u )$ with $\lambda _ { + } > 0$ in (3), there holds

$$
\| \nabla u \| _ { L ^ { \infty } ( \Omega ^ { \prime } ) } \leq C .
$$

Proof We proceed as the proof of[15,Theorem 4.1],supposing that (59)fails.Then there exists a sequence of points $X _ { j } \in$ $\Omega ^ { \prime } \cap \left\{ u > \mathrm { { \bar { 0 } } } \right\}$ such that

$$
X _ { j } \to \partial \{ u > 0 \} \quad \mathrm { a n d } \quad { \frac { u ( X _ { j } ) } { \mathrm { d i s t } ( X _ { j } , \partial \{ u > 0 \} ) } } \to + \infty \quad \mathrm { a s } j \to + \infty .
$$

Denote $U _ { j } = u ( X _ { j } )$ and $d _ { j } = \mathrm { d i s t } ( X _ { j } , \partial \{ u > 0 \} )$ . Let $Y _ { j } \in \partial \{ u > 0 \}$ satisfying $d _ { j } = | X _ { j } - Y _ { j } |$ . Note that we have

$$
\mathrm { d i v } \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u = q f ( u ) + h \mathrm { i n } \{ u > 0 \} .
$$

Thus, by Harnack's inequality, $( \tilde { g } _ { 1 } )$ , and the boundedness of $u$ ,there exists a constant $c$ depending only on $\Omega ^ { \prime }$ and universal constants,suchthat

$$
d _ { j } + \operatorname* { i n f } _ { \overline { { B } } _ { \frac { 3 } { 4 } d _ { j } } ( X _ { j } ) } u \geq c U _ { j } .
$$

In turn, we have

$$
{ \tt \tt { \tt { s u p } } } _ { { \tt { d } } _ { j } } u \geq c U _ { j } - d _ { j } .
$$

Consider the set $A _ { j } = \left\{ Z \in B _ { d _ { j } } ( Y _ { j } ) : \operatorname { d i s t } ( Z , \partial \{ u > 0 \} ) \leq \frac { 1 } { 3 } \mathrm { d i s t } ( Z , \partial B _ { d _ { j } } ( Y _ { j } ) ) \right\}$ . Then $B _ { \frac { d _ { j } } { 4 } } ( Y _ { j } ) \subset A _ { j }$ (see the proof of [15,Theorem 4.1]). Thus

$$
\begin{array} { r l } & { \mathrm { d i s t } ( Z _ { j } , \partial B _ { d _ { j } } ( Y _ { j } ) ) u ( Z _ { j } ) : = M _ { j } } \\ & { \quad : = \operatorname* { s u p } \mathrm { d i s t } ( Z , \partial B _ { d _ { j } } ( Y _ { j } ) ) u ( Z ) } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \quad \quad \quad \quad \quad \quad  \\ &  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad  \end{array}
$$

It follows that

$$
u ( Z _ { j } ) \geq \frac { d _ { j } } { \mathrm { d i s t } ( Z _ { j } , \partial B _ { d _ { j } } ( Y _ { j } ) ) } \frac { 3 } { 4 } \operatorname* { s u p } _ { \frac { d _ { j } } { B } _ { \frac { d _ { j } } { 4 } } ( Y _ { j } ) } u \geq \frac { 3 } { 4 } \operatorname* { s u p } _ { \frac { d _ { j } } { B } _ { \frac { d _ { j } } { 4 } } ( Y _ { j } ) } u .
$$

Using (61), we have

$$
u ( Z _ { j } ) \geq { \frac { 3 } { 4 } } ( c U _ { j } - d _ { j } ) .
$$

For each $j$ ,let $W _ { j } \in \partial \{ u > 0 \}$ satisfy

$$
r _ { j } = | Z _ { j } - W _ { j } | = \mathrm { d i s t } ( Z _ { j } , \partial \{ u > 0 \} ) \leq \frac { 1 } { 3 } \mathrm { d i s t } ( Z _ { j } , \partial B _ { d _ { j } } ( Y _ { j } ) ) .
$$

One may get (see (4.7) in [15])

$$
\frac { d _ { j } } { r _ { j } } \geq 4 .
$$

It follows from (62),(63) and (60) that

$$
\frac { u ( Z _ { j } ) } { r _ { j } } \geq \frac { 3 d _ { j } } { 4 r _ { j } } \bigg ( c \frac { U _ { j } } { d _ { j } } - 1 \bigg ) \geq 3 \bigg ( c \frac { U _ { j } } { d _ { j } } - 1 \bigg )  + \infty .
$$

Proceeding as (4.1O),(4.11) in [15],one has (for $j$ large enough)

$$
\operatorname* { s u p } _ { B _ { \frac { r _ { j } } { 2 } } ( W _ { j } ) } u \leq 2 u ( Z _ { j } ) , \quad \operatorname* { s u p } _ { \overline { { B } } _ { \frac { r _ { j } } { 4 } } ( W _ { j } ) } \frac { u } { u ( Z _ { j } ) } \geq \frac { c ^ { \prime } } { 2 } ,
$$

for some universal constant $c ^ { \prime } > 0$ . Now for each $j$ ,define the function $u _ { j } : B _ { 1 } ( 0 ) \to ( 0 , 2 )$ by

$$
u _ { j } ( X ) = \frac { u ( W _ { j } + \frac { r _ { j } } 2 X ) } { u ( Z _ { j } ) } .
$$

It follows from (65) that

$$
\operatorname* { m a x } _ { B _ { 1 } ( 0 ) } u _ { j } \le 2 , \quad \operatorname* { m a x } _ { B _ { 1 } ( 0 ) } u _ { j } \ge \frac { c ^ { \prime } } { 2 } , \quad u _ { j } ( 0 ) = 0 .
$$

Let $\begin{array} { r } { \sigma _ { j } = \frac { 2 u ( Z _ { j } ) } { r _ { j } } } \end{array}$ ，2 $\begin{array} { r } { G _ { j } ( t ) = \frac { G ( \sigma _ { j } t ) } { \sigma _ { j } g ( \sigma _ { j } ) } } \end{array}$ $g _ { j } ( t ) = G _ { j } ^ { \prime } ( t )$ ， $\begin{array} { r } { F _ { j } ( t ) = \frac { F ( u ( Z _ { j } ) t ) } { \sigma _ { j } g ( \sigma _ { j } ) } } \end{array}$ $f _ { j } ( t ) = F _ { j } ^ { \prime } ( t )$ （ $\begin{array} { r } { q _ { j } ( X ) = q ( W _ { j } + \frac { r _ { j } } { 2 } X ) } \end{array}$ （

$$
\delta _ { 0 } \leq \frac { t g _ { j } ^ { \prime } ( t ) } { g _ { j } ( t ) } \leq g _ { 0 } , 1 + \theta _ { 0 } \leq \frac { t F _ { j } ^ { \prime } ( t ) } { F _ { j } ( t ) } \leq 1 + f _ { 0 } .
$$

Let $v$ be the $G -$ harmonic function in $B _ { \frac { r _ { j } } { 2 } } ( W _ { j } )$ with the boundary data $u$ ,i.e.,

$$
\left\{ \begin{array} { r l } { \mathrm { d i v } \frac { g ( | \nabla v | ) } { | \nabla v | } \nabla v = 0 } & { \mathrm { i n } B _ { \frac { r _ { j } } { 2 } } ( W _ { j } ) , } \\ { v } & { = u \quad \mathrm { o n } \partial B _ { \frac { r _ { j } } { 2 } } ( W _ { j } ) . } \end{array} \right.
$$

Let $v _ { j } : B _ { 1 } ( 0 ) \to ( 0 , 2 )$ be defined by $\begin{array} { r } { v _ { j } ( X ) = \frac { v ( W _ { j } + \frac { r _ { j } } { 2 } X ) } { u ( Z _ { j } ) } } \end{array}$ . Then $v _ { j }$ stisfies

$$
\left\{ \begin{array} { r l } { \mathrm { d i v } \frac { g _ { j } ( | \nabla v _ { j } | ) } { | \nabla v _ { j } | } \nabla v _ { j } = 0 } & { \mathrm { i n } B _ { 1 } ( 0 ) , } \\ { v _ { j } = u _ { j } \mathrm { o n } \partial B _ { 1 } ( 0 ) . } \end{array} \right.
$$

Let $\begin{array} { r } { Y = W _ { j } + \frac { r _ { j } } { 2 } X } \end{array}$ ,then

$$
\int _ { B _ { \frac { r _ { j } } { 2 } } ( W _ { j } ) } G ( | \nabla u ( Y ) | ) \mathrm { d } Y = \left( \frac { r _ { j } } { 2 } \right) ^ { n } \int _ { B _ { 1 } ( 0 ) } G ( \sigma _ { j } | \nabla u _ { j } ( X ) | ) \mathrm { d } X .
$$

It follows

$$
\begin{array} { r } { \displaystyle \int _ { B _ { \frac { r _ { j } } { 2 } } ( W _ { j } ) } \frac { G \big ( | \nabla u ( Y ) | \big ) } { \sigma _ { j } g \big ( \sigma _ { j } \big ) } \mathrm { d } Y = \biggr ( \frac { r _ { j } } { 2 } \biggr ) ^ { n } \displaystyle \int _ { B _ { 1 } ( 0 ) } \frac { G \big ( \sigma _ { j } | \nabla u _ { j } ( X ) | \big ) } { \sigma _ { j } g \big ( \sigma _ { j } \big ) } \mathrm { d } X } \\ { \displaystyle = \biggr ( \frac { r _ { j } } { 2 } \biggr ) ^ { n } \displaystyle \int _ { B _ { 1 } ( 0 ) } G _ { j } \big ( | \nabla u _ { j } ( X ) | \big ) \mathrm { d } X , } \end{array}
$$

which gives

$$
\int _ { B _ { 1 } ( 0 ) } G _ { j } ( | \nabla u _ { j } | ) \mathrm { d } x = \left( \frac { r _ { j } } { 2 } \right) ^ { - n } \int _ { B _ { \frac { r _ { j } } { 2 } } ( W _ { j } ) } \frac { G ( | \nabla u | ) } { \sigma _ { j } g ( \sigma _ { j } ) } \mathrm { d } x .
$$

By the minimality of $u$ ,we have

$$
\begin{array} { r l } { \displaystyle \int _ { B _ { \frac { r _ { j } } { 2 } } ( W _ { j } ) } G ( | \nabla u | ) \mathrm { d } x - \displaystyle \int _ { B _ { \frac { r _ { j } } { 2 } } ( W _ { j } ) } G ( | \nabla v | ) \mathrm { d } x \le \displaystyle \int _ { B _ { \frac { r _ { j } } { 2 } } ( W _ { j } ) } \bigg ( q ( F ( v ^ { + } ) - F ( u ^ { + } ) ) + h ( v - u ) \bigg ) \mathrm { d } x } & { } \\ { \displaystyle } & { \qquad + \lambda _ { + } \displaystyle \int _ { B _ { \frac { r _ { j } } { 2 } } ( W _ { j } ) } ( \chi _ { \{ h > 0 \} } - \chi _ { \{ u > 0 \} } ) \mathrm { d } x } \\ { \displaystyle } & { \qquad \le \| q \| _ { L ^ { \infty } ( B _ { \frac { r _ { j } } { 2 } } ) } \displaystyle \int _ { B _ { \frac { r _ { j } } { 2 } } ( W _ { j } ) } ( | F ( h ) | + | F ( u ) | ) \mathrm { d } x + C r _ { j } ^ { n } } \\ { \displaystyle } & { \le C r _ { j } ^ { n } , } \end{array}
$$

where we used the boundedness of $h$ and $u , v$ ,and the increasing property of $F$ in the last inequality.

We infer from (69) and (70)

$$
\int _ { B _ { 1 } ( 0 ) } G _ { j } ( | \nabla u _ { j } | ) \mathrm { d } x - \int _ { B _ { 1 } ( 0 ) } G _ { j } ( | \nabla v _ { j } | ) \mathrm { d } x \leq \frac { C } { \sigma _ { j } g ( \sigma _ { j } ) }  0 \ b \mathrm { y } \ \sigma _ { j }  + \infty .
$$

Then we deduce by Lemma 12 and (71)

$$
\int _ { B _ { 1 } } G _ { j } ( | \nabla u _ { j } - \nabla v _ { j } | ) \mathrm { d } x \le C \Bigg ( \frac { 1 } { \sigma _ { j } g ( \sigma _ { j } ) } + \frac { 1 } { \sqrt { \sigma _ { j } g ( \sigma _ { j } ) } } \Bigg ) \to 0 \mathrm { a s ~ } j \to + \infty ,
$$

where we used the uniform boundedness of $\begin{array} { r } { \int _ { B _ { 1 } } G _ { j } ( | \nabla v _ { j } | ) \mathrm { d } x } \end{array}$ due to the uniform boundedness of $u _ { j }$ and $v _ { j }$ (see, e.g., Lemma 11).

We get by $\left( G _ { 3 } \right)$

$$
\int _ { B _ { 1 } ^ { - } } | \nabla u _ { j } - \nabla v _ { j } | ^ { 1 + g _ { 0 } } \mathrm { d } x + \int _ { B _ { 1 } ^ { + } } | \nabla u _ { j } - \nabla v _ { j } | ^ { 1 + \delta _ { 0 } } \mathrm { d } x \leq C \int _ { B _ { 1 } } G _ { j } ( | \nabla u _ { j } - \nabla v _ { j } | ) \mathrm { d } x ,
$$

where $B _ { 1 } ^ { - } = B _ { 1 } \cap \{ | \nabla u _ { j } - \nabla v _ { j } | < 1 \}$ and $B _ { 1 } ^ { + } = B _ { 1 } \cap \{ | \nabla u _ { j } - \nabla v _ { j } | \geq 1 \}$ .Holder's inequality gives

$$
\int _ { B _ { 1 } ^ { - } } | \nabla u _ { j } - \nabla v _ { j } | ^ { 1 + \delta _ { 0 } } \mathrm { d } x \le C \bigg ( \int _ { B _ { 1 } ^ { - } } | \nabla u _ { j } - \nabla v _ { j } | ^ { 1 + g _ { 0 } } \mathrm { d } x \bigg ) ^ { \frac { 1 + \delta _ { 0 } } { 1 + g _ { 0 } } } .
$$

So we obtain by (73) and (74)

$$
\biggl ( \int _ { B _ { 1 } ^ { - } } | \nabla u _ { j } - \nabla v _ { j } | ^ { 1 + \delta _ { 0 } } \mathrm { d } x \biggr ) ^ { \frac { 1 + g _ { 0 } } { 1 + \delta _ { 0 } } } + \int _ { B _ { 1 } ^ { + } } | \nabla u _ { j } - \nabla v _ { j } | ^ { 1 + \delta _ { 0 } } \mathrm { d } x \leq C \int _ { B _ { 1 } } G _ { j } ( | \nabla u _ { j } - \nabla v _ { j } | ) \mathrm { d } x ,
$$

which and (72) imply that

$$
\int _ { B _ { 1 } } | \nabla u _ { j } - \nabla v _ { j } | ^ { 1 + \delta _ { 0 } } \mathrm { d } x \to 0 \mathrm { ~ } \mathfrak { b } \mathfrak { y } j \to + \infty .
$$

It follows by Poincaré's inequality that

$$
u _ { j } - v _ { j } \to 0 \mathrm { s t r o n g l y i n } W _ { 0 } ^ { 1 , 1 + \delta _ { 0 } } ( B _ { 1 } ) .
$$

Note that the uniform boundedness of $v _ { j }$ guarantees that, for any $r _ { 0 } \in ( 0 , 1 )$ there exists a universal constant $C > 0$ satisfying （204号 $\| v _ { j } \| _ { C ^ { 1 , \alpha } ( B _ { r _ { 0 } } ) } \leq C$ (see, e.g. [20, Theorem 1.2]). Therefore, we can find $\scriptstyle v _ { 0 }$ in ${ B } _ { r _ { 0 } }$ such that, up to a subsequence,

On the other hand, noting that $u _ { j }$ is a minimizer of the following functional

$$
\mathcal { I } _ { j } = \int _ { B _ { 1 } } ( G _ { j } ( | \nabla w | ) + q _ { j } F _ { j } ( w ^ { + } ) + h _ { j } w + \lambda _ { + j } \chi _ { \{ w > 0 \} } ) \mathrm { d } x \to \operatorname* { m i n } ,
$$

and recalling the structural conditions of $g _ { j } ( t ) , F _ { j } ( t )$ ,and $\lambda _ { + j }$ ,and the boundedness of $q _ { j } , h _ { j }$ ,we have the uniform Holder': estimate of $u _ { j }$ ,i.e., $\| u _ { j } \| _ { C ^ { \beta } ( B _ { r _ { 0 } } ) } \leq C$ . So, we conclude that there exists a $u _ { 0 } \in C ^ { \beta } ( B _ { r _ { 0 } } )$ such that

$$
u _ { k }  u _ { 0 } ~ \mathrm { u n i f o r m l y i n } { B _ { r } } _ { 0 } .
$$

We conclude this way that $u _ { 0 } = v _ { 0 }$ in ${ B } _ { r _ { 0 } }$ by (75).

Now using the compact condition (1), we conclude that (see [5,Theorem 6.1]) there exists a function $G _ { \infty } \in C ^ { 2 } ( 0 , + \infty )$ such that, up to a subsequence,

and $g _ { \infty }$ satisfies the same structural condition as (68) with the same constants.

We now claim that $u _ { 0 }$ is a $G _ { \infty }$ -harmonic function in ${ B } _ { r _ { 0 } }$ . Indeed, by the minimality of $u _ { j }$ again, we have for any $\varphi \in$ $C _ { 0 } ^ { \infty } ( B _ { r _ { 0 } } )$ （204号

$$
\begin{array} { r l } & { \displaystyle \int _ { B _ { r _ { 0 } } } G _ { j } ( | \nabla u _ { j } | ) \mathrm { d } x \le \int _ { B _ { r _ { 0 } } } \bigg ( G _ { j } ( | \nabla u _ { j } + \nabla \varphi | ) + q _ { j } F _ { j } ( ( u _ { j } + \varphi ) ^ { + } ) - q _ { j } F _ { j } ( u _ { j } ^ { + } ) + h _ { j } \big ( ( u _ { j } + \varphi ) ^ { + } - u _ { j } ^ { + } \big ) \bigg ) } \\ & { \qquad + \int _ { B _ { r _ { 0 } } } ( \lambda _ { + j } \chi _ { \{ u _ { j } + \varphi > 0 \} } - \lambda _ { + j } \chi _ { \{ u _ { j } > 0 \} } ) \mathrm { d } x . } \end{array}
$$

Note that $q _ { j }$ is uniformly bounded, $\sigma _ { j }  + \infty$ ， $\| h _ { j } \| _ { B _ { 1 } } \to 0$ and $u , \varphi$ are bounded, then

$$
\begin{array} { r l } & { \| h _ { j } ( ( u _ { j } + \varphi ) ^ { + } - u _ { j } ^ { + } ) \| _ { B _ { 1 } } \to 0 , } \\ & { q _ { j } F _ { j } ( u _ { j } ^ { + } ) = \frac { q _ { j } F \left( | u ( W _ { j } + \frac { r _ { j } } { 2 } X ) | \right) } { \sigma _ { j } g ( \sigma _ { j } ) } \le \frac { \| q \| _ { L ^ { \infty } ( B _ { 1 } ) } F \left( \underset { B _ { 1 } } { \operatorname* { s u p } } | u | \right) } { \sigma _ { j } g ( \sigma _ { j } ) } \to 0 , } \end{array}
$$

and

$$
\begin{array} { r l } & { q _ { j } F _ { j } ( ( u _ { j } + \varphi ) ^ { + } ) = \frac { \| q \| _ { L ^ { \infty } ( B _ { 1 } ) } F ( u ( W _ { j } + \frac { r _ { j } } { 2 } X ) + u ( Z _ { j } ) \varphi ) } { \sigma _ { j } g ( \sigma _ { j } ) } } \\ & { \qquad \leq \frac { \| q \| _ { L ^ { \infty } ( B _ { 1 } ) } F ( ( 1 + \underset { B _ { 1 } } { \operatorname* { s u p } } | \varphi | ) \underset { B _ { 1 } } { \operatorname* { s u p } } | u | ) } { \sigma _ { j } g ( \sigma _ { j } ) }  0 . } \end{array}
$$

Note also that

$$
G _ { j } ( | \nabla u _ { j } | ) \leq C ( G _ { j } ( | \nabla u _ { j } - \nabla v _ { j } | ) + G _ { j } ( | \nabla v _ { j } | ) ) ,
$$

which, the $C ^ { 1 }$ -convergence of $v _ { j }$ ,and (72) imply that there exists $\xi \in L ^ { 1 } ( B _ { r _ { 0 } } )$ such that

$$
G _ { j } ( | \nabla u _ { j } | ) \leq \xi \quad \mathrm { a . e . \ i n } \ B _ { B _ { r _ { 0 } } } .
$$

Once $\nabla u _ { j }  \nabla u _ { 0 }$ a.e. in ${ B } _ { r _ { 0 } }$ ,Lebesgue's dominated convergence theorem implies

$$
\int _ { B _ { r _ { 0 } } } G _ { j } ( | \nabla u _ { j } | ) \mathrm { d } x \to \int _ { B _ { r _ { 0 } } } G _ { \infty } ( | \nabla u _ { 0 } | ) \mathrm { d } x ,
$$

and

$$
\int _ { B _ { r _ { 0 } } } G _ { j } ( | \nabla u _ { j } + \nabla \varphi | ) \mathrm { d } x \to \int _ { B _ { r _ { 0 } } } G _ { \infty } ( | \nabla u _ { 0 } + \nabla \varphi | ) \mathrm { d } x .
$$

Then we obtain by (76),(77),(78),(79),and $\lambda _ { + j } \to 0$

$$
\int _ { B _ { r _ { 0 } } } G _ { \infty } ( | \nabla u _ { 0 } ) \mathrm { d } x \leq \int _ { B _ { r _ { 0 } } } G _ { \infty } ( | \nabla u _ { 0 } + \nabla \varphi | ) \mathrm { d } x .
$$

This implies that $u _ { 0 }$ is a $G _ { \infty }$ -harmonic function in ${ B } _ { r _ { 0 } }$

Since $u _ { j } \geq 0$ in $B _ { 1 }$ ， $u _ { 0 } \geq 0$ in ${ B } _ { r _ { 0 } }$ . Note that $u _ { 0 } ( 0 ) = 0$ . The Harnack's inequality implies $u _ { 0 } \equiv 0$ in ${ B } _ { r _ { 0 } }$ . Finally we get $u _ { 0 } \equiv 0$ in $B _ { 1 }$ due to the continuity of $u$ and the arbitrariness of $r _ { 0 }$ , which is a contradiction to (67). ■

# References

[1]Adams,R.A.,Fournier,J.J.F.:Sobolev Spaces.PureandAppliedMathematics.Amsterdam:Acad.Press(140)2003.   
[2]lt 1-44.   
[3]Alt,H.M.,hilips,D.:Afreeboundaryproblemforsemilinearellptcqatios.J.ReineAngew.Math.68(1986),-0.   
[4]Braga,JOiaitotfrdoofoooel Caffarell functionals in Orlicz spaces.Ann. Mat.Pura Appl.,https:/doi.org/10.10O7/s10231-018-0755-7.   
[5]Braga,JE.Uifdbal density on the negative phase.Ann.I.H.Poincaré- AN.,31(4)(2014),823-850.   
[6]Challal, S.,Lyaghfouri,A.: Porosity of free boundaries in $A$ -obstacle problems. Non. Anal.: TMA.,70(7)(2009),2772-2778.   
[7]Challal,S.,Lyaghfouri, A.,Rodrigues,J.F.: On the $A$ -obstacle problem and the Hausdorff measure of its free boundary.Ann. Mat. Pura Appl.,191(2012), 113-165.   
[8]osez,l 163-205.   
[9]Dels 97-124.   
[10]Giaquinta,M.,GustiE.Dierentibilityofminimofo-difreniablefunctioals.Invent.Math,(93),98.   
[p 164(2000),110-117.   
[12]Ladyzheskaya,O.A.,Ura'sevaN.N.LinearadQuasilinearElipticquationvol.46.AcademicPres,Newrk968.   
[13] Lee,K.,Shahgholian,H.: Hausdorff measure and stability for the $p$ -obstacle problem ( $2 < p < 1$ ).J.Differ: Equ.,195(2003),14-24.   
[4Leitaaiebé 32(4)(2015),741- 762.   
[15]Leitaa   
[16]LibeaaltdsddUoaiort 16 (2&3) (1991),311- 361.   
[17] Martinez,S.,Wolanski,N.:Aminimumproblem withfreeboundaryinOrliczspaces.Adv.Math.8(6)(O08),9141971.   
[18]PhllpsodisirUvt   
[19]Philips,D.usdorfeasretiatesoffrearyfoumprobCortalDiferEu8)454.   
[20Zgi 37-47.   
[21] Zheng,J., Guo, X.: Lyapunov-type inequalities for $\psi$ - Laplacian equations.chinaXiv:201805.00171.   
[22]Zheng,J,ag,ZZaoubiseeoudarOccsashat(-)).