# The obstacle problem for non-coercive equations with lower order term and $L ^ { 1 }$ -data

Jun Zheng

SchoolofMathematics,SouthwestJiaotongUniversity,Chengdu61l756,China

# Abstract

Theaimof thispaperistosudyteostacleproblemasociatedwithanelipticoperatoravingegenerateorcivityandwithalow order term and $L ^ { \mathrm { \hat { 1 } } }$ -data. We prove the existence of an entropy solution to the obstacle problem and show its continuous dependence on the $L ^ { 1 } -$ data in $W ^ { 1 , q } ( \Omega )$ with some $q > 1$ ：

Key words: obstacle problem; non-coercive equation; entropy solution; $L ^ { 1 }$ -data; lower order term.

# 1 Introduction

# 1.1Problem setting and main result

Let $\Omega$ be a bounded domain in $\mathbb { R } ^ { N } ( N \geq 2 ) , 1 < p < + \infty$ and $\theta \geq 0$ .Given functions $g$ $\psi \in W ^ { 1 , p } ( \Omega ) \cap L ^ { \infty } ( \Omega )$ and data $f \in L ^ { 1 } ( \Omega )$ ,the aim of this paper is to study the obstacle problem for nonlinear non-coercive eliptic equations with lower order term, governed by the operator

$$
A u = - \mathrm { d i v } \frac { a ( x , \nabla u ) } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } + b | u | ^ { r - 2 } u ,
$$

where $b > 0$ is a constant, and $a : \Omega \times \mathbb { R } ^ { N } \to \mathbb { R } ^ { N }$ is a Carathéodory function,satisfying the following conditions:

$$
\begin{array} { r l r } & { a ( x , \xi ) \cdot \xi \ge \alpha | \xi | ^ { p } , } & \\ & { | a ( x , \xi ) | \le \beta ( j ( x ) + | \xi | ^ { p - 1 } ) , } & \\ & { ( a ( x , \xi ) - a ( x , \eta ) ) ( \xi - \eta ) > 0 , } & \\ & { | a ( x , \xi ) - a ( x , \zeta ) | \le \gamma \left\{ | \xi - \zeta | ^ { p - 1 } , } & { \mathrm { i f ~ } 1 < p < 2 \right\} , } & \\ & { | a ( x , \xi ) - a ( x , \zeta ) | \le \gamma \left\{ | 1 + | \xi | + | \zeta | \right\} ^ { p - 2 } | \xi - \zeta | , \mathrm { ~ i f ~ } p \ge 2 } & \end{array} ,
$$

for almost every $x$ in $\Omega$ , and for every $\xi , \eta , \zeta$ in $\mathbb { R } ^ { N }$ with $\xi \neq \eta$ ，where $\alpha , \beta , \gamma > 0$ are constants, and $j$ is a nonnegative function in $L ^ { p ^ { \prime } } ( \Omega )$

旺 $f$ has a fine regularity, i.e., $f \in W ^ { - 1 , p ^ { \prime } } ( \Omega )$ , the obstacle problem corresponding to $( f , \psi , g )$ can be formulated in terms of the inequality

$$
\int _ { \Omega } \frac { a ( x , \nabla u ) } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } \cdot \nabla ( u - v ) \mathrm { d } x + \int _ { \Omega } b | u | ^ { r - 2 } u ( u - v ) \mathrm { d } x \leq \int _ { \Omega } f ( u - v ) \mathrm { d } x , \forall v \in K _ { g , \psi } \cap L ^ { \infty } ( \Omega ) ,
$$

Email address: zhengjun@ swjtu.edu.cn (Jun Zheng).

whenever $1 \leq r < p$ and the convex subset

$$
K _ { g , \psi } = \{ v \in W ^ { 1 , p } ( \Omega ) ; \ v - g \ \in W _ { 0 } ^ { 1 , p } ( \Omega ) , \ v \geq \psi , \ \mathrm { a . e . \ i n } \ \Omega \}
$$

is nonempty. However, if $f \in L ^ { 1 } ( \Omega )$ ,(6) is not well-defined,and following[1,3,6] etc., we are led to the more general definition of a solution to the obstacle problem,using the truncation function

$$
T _ { s } ( t ) = \operatorname* { m a x } \{ - s , \operatorname* { m i n } \{ s , t \} \} , \ s , t \in \mathbb { R } .
$$

Definition 1 An entropy solution of the obstacle problem associated corresponding to operator $A$ and functions $( f , \psi , g )$ with $f \in L ^ { 1 } ( \Omega )$ is measurablefunctionusuchthat $u \geq \psi$ a.e.in $\Omega$ $\begin{array} { r } { \frac { a ( x , \nabla u ) } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } \in ( L ^ { 1 } ( \Omega ) ) ^ { N } } \end{array}$ （ $| u | ^ { r - 1 } \in L ^ { 1 } ( \Omega )$ and for every $s > 0$ $. T _ { s } ( u ) - T _ { s } ( g ) \in W _ { 0 } ^ { 1 , p } ( \Omega )$ and

$$
\int _ { \Omega } \frac { a ( x , \nabla u ) } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } \cdot \nabla ( T _ { s } ( u - v ) ) d x + \int _ { \Omega } b | u | ^ { p - 2 } u T _ { s } ( u - v ) d x \leq \int _ { \Omega } f T _ { s } ( u - v ) d x , \forall v \in K _ { g , \psi } \cap L ^ { \infty }
$$

Observe that no global integrability condition is required on $u$ nor on its gradient in the definition.As pointed out in [3,9], if $T _ { s } ( u ) \in W ^ { 1 , \bar { p ( } \bar { \Omega } ) }$ for all $s > 0$ ,then there exists a unique measurable vector field $U : \Omega \to \mathbb { R } ^ { N }$ such that $\nabla ( T _ { s } ( u ) ) =$ （204号 $\chi _ { \{ | u | < s \} } U$ a.e. in $\Omega$ $s > 0$ ,which, in fact, coincides with the standard distributional gradient of $\nabla \boldsymbol { u }$ whenever $u \in W ^ { 1 , 1 } ( \Omega )$ ：

Before stating the main result, we make some basic assumptions throughout this paper,ie., without special statements,we always assume that

$$
2 - \frac { 1 } { N } < p < N , 1 \leq r < p , 0 \leq \theta < \operatorname* { m i n } \bigg \{ \frac { N } { N - 1 } - \frac { 1 } { p - 1 } , \frac { p - r } { p - 1 } \bigg \} , b > 0 ,
$$

and $\psi , g \in W ^ { 1 , p } ( \Omega ) \cap L ^ { \infty } ( \Omega )$ with $( \psi - g ) ^ { + } \in W _ { 0 } ^ { 1 , p } ( \Omega )$ such that $K _ { g , \psi } \neq \varnothing$ . The following theorem is the main result obtained in this paper.

Theorem 1 Let $f \in L ^ { 1 } ( \Omega )$ . Then there exists at least one entropy solution u of the obstacle problem associated with $( f , \psi , g )$ In addition, u depends continuously on $f$ i.e.,if $f _ { n } \to f$ in $L ^ { 1 } ( { \bar { \Omega } } )$ and $u _ { n }$ is a solution to the obstacle problem associated with （204号 $( f _ { n } , \psi , g )$ ，then

$$
u _ { n } \to u i n W ^ { 1 , q } ( \Omega ) , \forall q \in \left\{ \begin{array} { l l } { \big ( \frac { N ( r - 1 ) } { N + r - 1 } , \frac { N ( p - 1 ) ( 1 - \theta ) } { N - 1 - \theta ( p - 1 ) } \big ) , i f \ \frac { 2 N - 1 } { N - 1 } \leq r < p , } \\ { ( 1 , \frac { N ( p - 1 ) ( 1 - \theta ) } { N - 1 - \theta ( p - 1 ) } ) , i f \ 1 \leq r < \operatorname* { m i n } \{ \frac { 2 N - 1 } { N - 1 } , p \} . } \end{array} \right.
$$

# 1.2 Some comments and remarks

Consider the Dirichlet boundary value problem having a form

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { - \mathrm { d i v } \frac { | \nabla u | ^ { p - 2 } \nabla u } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } + b u = f , \mathrm { i n } \Omega , } \\ { u = 0 , \qquad \mathrm { o n } \partial \Omega , } \end{array} \right. } \end{array}
$$

with $p > 1 , \theta \in ( 0 , 1 ] , b \geq 0 , f \in L ^ { 1 } ( \Omega )$ . The item $\frac { | \nabla u | ^ { p - 2 } \nabla u } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } }$ is not coercive f $u$ isveree sa $f$ is regtae oree $\frac { | \nabla u | ^ { p - 2 } \nabla u } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } }$ $u$ $f$ are gly i $L ^ { 1 } ( \Omega )$ snoein $W ^ { - 1 , p ^ { \prime } } ( \Omega )$ Al tledese $b = 0$ sad hgegea employing the duality argument [18] or nonlinear monotone operator theory [19] directly.

To overcome these dificulties,cuting the noncoercivity termandusing the technique of approximation,a pseudomonotone and coercive differential operator on $\bar { W } _ { 0 } ^ { 1 , p } ( \Omega )$ can be applied to establish $a$ priori estimates on approximating solutions. As

a result, existence of solutions, or entropy solutions,can be obtained by taking limitation for $f \in L ^ { m } ( \Omega ) , m \geq 1$ and $b > 0$ due to the almost everywhereconvergenceforthegradients ofteapproximatingsolutions,se.g.,[4,71O-12,16]（seealso [1,2,8,13,14,17] for $b = 0$ ）

Motivatedbythe studyon the non-coercive elipticequations (9),weconsider inthis papertheobstacle problem governed by (1) and functions $( f , \psi , g )$ with $f \in L ^ { 1 } ( \Omega )$ . We prove the existence of an entropy solution and show its continuous dependence on the $L ^ { 1 }$ -data in $W ^ { 1 , q } ( \Omega )$ with some ${ \dot { q } } \in ( 1 , p )$

In the following,we give some remarks onour mainresult and inequalities that willbe needed in the proofs.Somenotations are provided in the end of this subsection.

Remark 1 (i) $\begin{array} { r } { 0 \leq \theta < \operatorname* { m i n } \left\{ \frac { N } { N - 1 } - \frac { 1 } { p - 1 } , \frac { p - r } { p - 1 } \right\} \Rightarrow r - 1 < ( 1 - \theta ) ( p - 1 ) < \frac { N ( p - 1 ) ( 1 - \theta ) } { N - 1 - \theta ( p - 1 ) } } \end{array}$ Theefore herem guarates $| u | ^ { r - 1 } \in L ^ { 1 } ( \Omega )$ , and the second integration in (7) makes sense.

(ii)Wewill show that 1(f(

$$
\begin{array} { r l } & { \frac { \tau ( r - 1 ) } { \tau + r - 1 } , \frac { N ( p - 1 ) ( 1 - \theta ) } { N - 1 - \theta ( p - 1 ) } \bigg ) \subset ( 1 , \frac { N ( p - 1 ) ( 1 - \theta ) } { N - 1 - \theta ( p - 1 ) } ) i f \frac { 2 N - 1 } { N - 1 } \leq r < p , I n d e e d , \theta < \frac { p - r } { p - 1 } + \frac { p ( r - 1 ) } { N ( p - 1 ) } \Leftrightarrow \frac { N ( p - 1 ) ( 1 - \theta ) } { N - 1 - \theta ( p - 1 ) } \ : ; } \\ & { \frac { \ell - 1 } { - 1 } \leq r g i v e s \frac { N ( r - 1 ) } { N + r - 1 } \geq 1 , T h u s u _ { n }  u i n W ^ { 1 , q } ( \Omega ) f o r a l l q \in \big ( 1 , \frac { N ( p - 1 ) ( 1 - \theta ) } { N - 1 - \theta ( p - 1 ) } \big ) . } \end{array}
$$

(i) $\begin{array} { r } { r \mathrm { ~ - ~ } 1 \mathrm { ~ < ~ } \frac { N q } { N - q } } \end{array}$ Indeed by $\textstyle 1 \leq r < { \frac { 2 N - 1 } { N - 1 } }$ the hlds $\begin{array} { r } { r \mathrm { ~ - ~ } 1 \mathrm { ~ < ~ } \frac { N } { N - 1 } \mathrm { ~ < ~ } \frac { N q } { N - q } } \end{array}$ for any $q > 1$ particalarly fr $\begin{array} { r } { q \in ( 1 , \frac { N ( p - 1 ) ( 1 - \theta ) } { N - 1 - \theta ( p - 1 ) } \overset { - } { ) } } \end{array}$ $\begin{array} { r } { r \ge \frac { 2 N - 1 } { N - 1 } } \end{array}$ sufes tes $\begin{array} { r } { q > \frac { N ( r - 1 ) } { N + r - 1 } \Leftrightarrow r - 1 < \frac { N q } { N - q } } \end{array}$ 1

Remark 2 Checking proofs of this paper, one may find that, for $b = 0 ;$ (8) holds with

$$
u _ { n }  u i n W ^ { 1 , q } ( \Omega ) , \forall q \in \bigg ( 1 , \frac { N ( p - 1 ) ( 1 - \theta ) } { N - 1 - \theta ( p - 1 ) } \bigg ) .
$$

Indeed,itsufficestoset $r = 1$ in theproofs

# Notations

$\| u \| _ { p } = \| u \| _ { L ^ { p } ( \Omega ) }$ is the norm of $L ^ { p } ( \Omega )$ , where $1 \le p \le \infty$ $\| u \| _ { 1 , p } = \| u \| _ { W ^ { 1 , p } ( \Omega ) }$ is the norm of $W ^ { 1 , p } ( \Omega )$ , where $1 < p < \infty$ $\begin{array} { r } { p ^ { \prime } = \frac { p } { p - 1 } } \end{array}$ with $1 < p < \infty$ ： $u ^ { + } = \operatorname* { m a x } \{ u , 0 \}$ ， $u ^ { - } = ( - u ) ^ { + }$ ,if $u$ is a real-valued function. $C$ is a constant, which may be different from each other. $\{ u \ > \ s \} = \{ x \in \Omega ; u ( x ) > s \}$ ： $\{ u \le s \} = \Omega \backslash \{ u > s \}$ ： $\{ u < \mathit { s } \} = \{ x \in \Omega ; u ( x ) < s \}$ $\{ u \ge s \} = \Omega \setminus \{ u < s \}$ ： $\{ u = s \} = \{ x \in \Omega ; u ( x ) = s \}$ $\{ t \leq u < s \} = \{ u \geq t \} \cap \{ u < s \}$ ： $\mathcal { L } ^ { N }$ is the Lebesgue measure of $\mathbb { R } ^ { N }$ $| E | = \mathcal { L } ^ { N } ( E )$ for a measurable set $E$ ：

# 2Lemmas on entropy solutions

It is worthy to note that, for any smooth function $f _ { n }$ ,there exists at least one solution to the obstacle problem (6).Indeed,one can proceed exactly as in [1,12] to obtain $W ^ { 1 , p } -$ solutions due to the assumptions (2)-(4) on $a$ and $r - 1 < p$ .These solutions, in particular,arealsoentropysolutions.Inthissectionweestablish severalauxiliaryresultsonconvergenceofsequencesof entropy solutions when $f _ { n } \to f$ in $L ^ { 1 } ( \Omega )$

Lemma 2 Let $v _ { 0 } \in K _ { g , \psi } \cap L ^ { \infty } ( \Omega ) ,$ and let u be an entropy solution of the obstacle problem associated with $( f , \psi , g )$ . Then we have

$$
\int _ { \{ | u | < t \} } \frac { | \nabla u | ^ { p } } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } d x \leq C ( 1 + t ^ { r } ) , \forall t > 0 ,
$$

where $C$ is a positive constant depending only on $\alpha , \beta , p , r , b , \| j \| _ { p ^ { \prime } } , \| \nabla v _ { 0 } \| _ { p } , \| v _ { 0 } \| _ { \infty } ,$ and $\| f \| _ { 1 }$

ProofTake $\scriptstyle v _ { 0 }$ as a test function in (7).For $t$ large enough such that $t - \| v _ { 0 } \| _ { \infty } > 0$ , we get

$$
\int _ { \{ | v _ { 0 } - u | < t \} } \frac { a ( x , \nabla u ) \cdot \nabla u } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x \le \int _ { \{ | v _ { 0 } - u | < t \} } \frac { a ( x , \nabla u ) \cdot \nabla v _ { 0 } } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x + \int _ { \Omega } ( f - b | u | ^ { r - 2 } u ) T _ { t } ( u - v _ { 0 } ) \mathrm { d } x .
$$

We estimate each integration in the right-hand side of (11). It follows from (3) and Young's inequality with $\varepsilon > 0$ that

$$
\begin{array} { r l } { \displaystyle \int _ { \{ | v _ { 0 } - u | < t \} } \frac { a ( x , \nabla u ) \cdot \nabla v _ { 0 } } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x \leq \int _ { \{ | v _ { 0 } - u | < t \} } \frac { \beta ( | j | + | \nabla u | ^ { p - 1 } ) \cdot | \nabla v _ { 0 } | } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x } & { } \\ { \leq \int _ { \{ | v _ { 0 } - u | < t \} } \frac { \beta \varepsilon ( | j | ^ { p ^ { \prime } } + | \nabla u | ^ { p } ) } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x + \int _ { \{ | v _ { 0 } - u | < t \} } \frac { \beta C ( \varepsilon ) | \nabla v _ { 0 } | ^ { p } } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x } & { } \\ { \leq \varepsilon \int _ { \{ | v _ { 0 } - u | < t \} } \frac { | \nabla u | ^ { p } } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x + C ( \| j \| _ { p ^ { \prime } } ^ { p ^ { \prime } } + \| \nabla v _ { 0 } \| _ { p } ^ { p } ) . } & { } \end{array}
$$

$$
- \int _ { \Omega } b | u | ^ { r - 2 } u T _ { t } ( u - v _ { 0 } ) \mathrm { d } x = - \int _ { \{ | u - v _ { 0 } | \leq t \} } b | u | ^ { r - 2 } u T _ { t } ( u - v _ { 0 } ) \mathrm { d } x - \int _ { \{ | u - v _ { 0 } | > t \} } b | u | ^ { r - 2 } u T _ { t } ( u - v _ { 0 } ) \mathrm { d } x
$$

Note that on the set $\{ | u - v _ { 0 } | \leq t \}$

$$
| | u | ^ { r - 2 } u T _ { t } ( u - v _ { 0 } ) | \leq t | t + \| v _ { 0 } \| _ { \infty } | ^ { r - 1 } \leq C ( 1 + t ^ { r } ) ,
$$

where $C$ is a constant depending only on $r$ $\| v _ { 0 } \| _ { \infty }$

On the set $\{ | u - v _ { 0 } | > t \bar  \}$ , we have $| u | \geq t - \| v _ { 0 } \| _ { \infty } > 0$ ,thus $u$ and $T _ { t } ( u - v _ { 0 } )$ have the same sign. It fllows

$$
- \int _ { \{ | u - v _ { 0 } | > t \} } b | u | ^ { r - 2 } u T _ { t } ( u - v _ { 0 } ) \mathrm { d } x \leq 0 .
$$

Combining (13)-(15),we get

$$
- \int _ { \Omega } b | u | ^ { r - 2 } u T _ { t } ( u - v _ { 0 } ) \mathrm { d } x \leq C ( 1 + t ^ { r } ) .
$$

$$
\begin{array} { r l } & { \displaystyle \int _ { \{ | v _ { 0 } - u | < t \} } \frac { | \nabla u | ^ { p } } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x \le C ( \| j \| _ { p ^ { \prime } } ^ { p ^ { \prime } } + \| \nabla v _ { 0 } \| _ { p } ^ { p } + t \| f \| _ { 1 } + 1 + t ^ { r } ) } \\ & { \qquad \le C ( 1 + t ^ { r } ) . } \end{array}
$$

Replacing $t$ with $t + \| v _ { 0 } \| _ { \infty }$ in (17) and noting that $\{ | u | < t \} \subset \{ | v _ { 0 } - u | < t + \| v _ { 0 } \| _ { \infty } \}$ ,one may obtain the desired result.■

In the rest of this section, let $\left\{ u _ { n } \right\}$ be a sequence of entropy solutions of the obstacle problem associated with $( f _ { n } , \psi , g )$ and assumethat

$$
f _ { n } \to f \mathrm { ~ } \mathrm { i n ~ } L ^ { 1 } ( \Omega ) \mathrm { ~ a n d ~ } \| f _ { n } \| _ { 1 } \leq \| f \| _ { 1 } + 1 .
$$

Lemma 3 There exists a measurable function u such that $u _ { n } \to u$ in measure, and $T _ { k } ( u _ { n } )  T _ { k } ( u )$ weakly in $W ^ { 1 , p } ( \Omega )$ for any $k > 0$ Thus $T _ { k } ( u _ { n } )  T _ { k } ( u )$ strongly in $L ^ { p } ( \Omega )$ and a.e. in $\Omega$

Proof Let $s , t$ and $\varepsilon$ be positive numbers. One may verify that for every $m , n \geq 1$

$$
\mathcal { L } ^ { N } ( \{ \left| u _ { n } - u _ { m } \right| > s \} ) \leq \mathcal { L } ^ { N } ( \{ \left| u _ { n } \right| > t \} ) + \mathcal { L } ^ { N } ( \{ \left| u _ { m } \right| > t \} ) + \mathcal { L } ^ { N } ( \{ \left| T _ { k } ( u _ { n } ) - T _ { k } ( u _ { m } ) \right| > s \} ) ,
$$

and

$$
\mathcal { L } ^ { N } ( \{ | u _ { n } | > t \} ) = \frac { 1 } { t ^ { p } } \int _ { \{ | u _ { n } | > t \} } t ^ { p } \mathrm { d } x \leq \frac { 1 } { t ^ { p } } \int _ { \Omega } | T _ { t } ( u _ { n } ) | ^ { p } \mathrm { d } x .
$$

Due to $v _ { 0 } = g + ( \psi - g ) ^ { + } \in K _ { g , \psi } \cap L ^ { \infty } ( \Omega )$ ,by Lemma 2,one has

$$
\int _ { \Omega } | \nabla T _ { t } ( u _ { n } ) | ^ { p } \mathrm { d } x = \int _ { \{ | u _ { n } | < t \} } | \nabla u _ { n } | ^ { p } \mathrm { d } x \leq C ( 1 + t ) ^ { \theta ( p - 1 ) } ( 1 + t ^ { r } ) .
$$

Note that $T _ { t } ( u _ { n } ) - T _ { t } ( g ) \in W _ { 0 } ^ { 1 , p } ( \Omega )$ .By (19),(2O)and Poincaré's inequality,forevery $t > \| g \| _ { \infty }$ and for some positive constant $C$ independent of $n$ and $t$ , there holds

$$
\begin{array} { r l } { \mathcal { L } ^ { N } ( \{ | u _ { n } | > t \} ) \leq \displaystyle \frac { 1 } { t ^ { p } } \int _ { \Omega } | T _ { t } ( u _ { n } ) | ^ { p } \mathrm { d } x } \\ & { \leq \frac { 2 ^ { p - 1 } } { t ^ { p } } \int _ { \Omega } | T _ { t } ( u _ { n } ) - T _ { t } ( g ) | ^ { p } \mathrm { d } x + \frac { 2 ^ { p - 1 } } { t ^ { p } } \| g \| _ { p } ^ { p } } \\ & { \leq \frac { C } { t ^ { p } } \int _ { \Omega } | \nabla T _ { t } ( u _ { n } ) - \nabla T _ { t } ( g ) | ^ { p } \mathrm { d } x + \frac { 2 ^ { p - 1 } } { t ^ { p } } \| g \| _ { p } ^ { p } } \\ & { \leq \frac { C } { t ^ { p } } \int _ { \Omega } | \nabla T _ { t } ( u _ { n } ) | ^ { p } \mathrm { d } x + \frac { C } { t ^ { p } } \| g \| _ { 1 , p } ^ { p } } \\ & { \leq \frac { C ( 1 + t ^ { r + \theta ( p - 1 ) } ) } { t ^ { p } } . } \end{array}
$$

Since $\textstyle { 0 \leq \theta < { \frac { p - r } { p - 1 } } }$ , there exists $t _ { \varepsilon } > 0$ such that

$$
\mathcal { L } ^ { N } ( \{ | u _ { n } | > t \} ) < \frac { \varepsilon } { 3 } , \forall t \ge t _ { \varepsilon } , \forall n \ge 1 .
$$

Now we have as in (19)

$$
\mathcal { L } ^ { N } \big ( \{ | T _ { t _ { c } } ( u _ { n } ) - T _ { t _ { c } } ( u _ { m } ) | > s \} \big ) = \frac { 1 } { s ^ { p } } \int _ { \left\{ | T _ { t _ { c } } ( u _ { n } ) - T _ { t _ { c } } ( u _ { m } ) | > s \right\} } s ^ { p } \mathrm { d } x \leq \frac { 1 } { s ^ { p } } \int _ { \Omega } | T _ { t _ { c } } ( u _ { n } ) - T _ { t _ { c } } ( u _ { m } ) | ^ { p } \mathrm { d } x .
$$

Using (20) and the fact that $T _ { t } ( u _ { n } ) - T _ { t } ( g ) \in W _ { 0 } ^ { 1 , p } ( \Omega )$ again, we see that $\{ T _ { t _ { \varepsilon } } ( u _ { n } ) \}$ is a bounded sequence in $W ^ { 1 , p } ( \Omega )$ . Thus, up to a subsequence, $\{ T _ { t _ { \varepsilon } } ( u _ { n } ) \}$ converges strongly in $L ^ { p } ( \Omega )$ . Taking into account (22), there exists $n _ { 0 } = n _ { 0 } ( t _ { \varepsilon } , s ) \geq 1$ such that

$$
\mathcal { L } ^ { N } ( \{ \left| T _ { t _ { \varepsilon } } ( u _ { n } ) - T _ { t _ { \varepsilon } } ( u _ { m } ) \right| > s \} ) < \frac { \varepsilon } { 3 } , ~ \forall ~ n , m \ge n _ { 0 } .
$$

Combining (18),(21) and (23),we obtain

$$
\mathcal { L } ^ { N } ( \{ | u _ { n } - u _ { m } | > s \} ) < \varepsilon , \ \forall \ n , m \geq n _ { 0 } .
$$

Hence $\left\{ u _ { n } \right\}$ is a Cauchy sequence in measure, and therefore there exists a measurable function $u$ such that $u _ { n } \to u$ in measure The remainder of the lemma is a consequence of the fact that $\{ T _ { k } ( u _ { n } ) \}$ is a bounded sequence in $W ^ { 1 , p } ( \Omega )$ ■

Proposition 4 There exists a subsequence of $\left\{ u _ { n } \right\}$ and a measurable function u such that for each $q$ given in (8), we have

$u _ { n } \to u$ strongly in $W ^ { 1 , q } ( \Omega )$

$\begin{array} { r } { 0 \le \theta < \operatorname* { m i n } \{ \frac { 1 } { N - p + 1 } , \frac { N } { N - 1 } - \frac { 1 } { p - 1 } , \frac { p - r } { p - 1 } \} . } \end{array}$ ，then

$$
\frac { a ( x , \nabla u _ { n } ) } { ( 1 + | u _ { n } | ) ^ { \theta ( p - 1 ) } } \to \frac { a ( x , \nabla u ) } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } s t r o n g l y i n \left( L ^ { 1 } ( \Omega ) \right) ^ { N } .
$$

To prove Proposition 4,we need two preliminary lemmas.

Lemma 5 There exists a subsequence of $\left\{ u _ { n } \right\}$ and a measurable function u such that for each q given in (8), we have $u _ { n }$ 1 u weakly in $W ^ { 1 , q } ( \Omega )$ , and $u _ { n } \to u$ strongly in $L ^ { q } ( \Omega )$

Proof Let $k > 0$ and $n \geq 1$ . Define $D _ { k } = \left\{ | u _ { n } | \leq k \right\}$ and $B _ { k } = \{ k \leq | u _ { n } | < k { + } 1 \}$ . Using Lemma 2 with $v _ { 0 } = g + ( \psi - g ) ^ { + }$ we get

$$
\int _ { D _ { k } } \frac { | \nabla u _ { n } | ^ { p } } { ( 1 + | u _ { n } | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x \leq C ( 1 + k ^ { r } ) ,
$$

where $C$ is a positive constant depending only on $\alpha , \beta , b , p , r , \| \boldsymbol { j } \| _ { p ^ { \prime } } , \| \boldsymbol { f } \| _ { 1 } , \| \nabla v _ { 0 } \| _ { p }$ , and $\| v _ { 0 } \| _ { \infty }$ （20

Using the function $T _ { k } ( u _ { n } )$ for $k > \{ \| g \| _ { \infty } , \| \psi \| _ { \infty } \}$ ,as a test function for the problem associated with $( f _ { n } , \psi , g )$ , we obtain

$$
\int _ { \Omega } \frac { a ( x , \nabla u _ { n } ) \cdot \nabla ( T _ { 1 } ( u _ { n } - T _ { k } ( u _ { n } ) ) ) } { ( 1 + | u _ { n } | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x + \int _ { \Omega } b | u _ { n } | ^ { r - 2 } u _ { n } T _ { 1 } ( u _ { n } - T _ { k } ( u _ { n } ) ) \mathrm { d } x \leq \int _ { \Omega } f _ { n } T _ { 1 } ( u _ { n } - T _ { k } ( u _ { n } ) )
$$

which and(2) give

$$
\int _ { B _ { k } } \frac { \alpha | \nabla u _ { n } | ^ { p } } { ( 1 + | u _ { n } | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x + \int _ { \Omega } b | u _ { n } | ^ { r - 2 } u _ { n } T _ { 1 } ( u _ { n } - T _ { k } ( u _ { n } ) ) \mathrm { d } x \leq \| f _ { n } \| _ { 1 } \leq \| f \| _ { 1 } + 1 .
$$

Note that on the set $\{ | u _ { n } | \geq k + 1 \}$ ， $u _ { n }$ and $T _ { 1 } ( u _ { n } - T _ { k } ( u _ { n } ) )$ have the same sign.Then

$$
\begin{array} { l } { \displaystyle \int _ { \Omega } | u _ { n } | ^ { r - 2 } u _ { n } T _ { 1 } ( u _ { n } - T _ { k } ( u _ { n } ) ) \mathrm { d } x = \int _ { D _ { k } } | u _ { n } | ^ { r - 2 } u _ { n } T _ { 1 } ( u _ { n } - T _ { k } ( u _ { n } ) ) \mathrm { d } x + \int _ { B _ { k } } | u _ { n } | ^ { r - 2 } u _ { n } T _ { 1 } ( u _ { n } - T _ { k } ( u _ { n } ) ) \mathrm { d } x } \\ { \displaystyle \qquad + \int _ { \{ | u _ { n } | \geq k + 1 \} } | u _ { n } | ^ { r - 2 } u _ { n } T _ { 1 } ( u _ { n } - T _ { k } ( u _ { n } ) ) \mathrm { d } x } \\ { \displaystyle \qquad \geq \int _ { B _ { k } } | u _ { n } | ^ { r - 2 } u _ { n } T _ { 1 } ( u _ { n } - T _ { k } ( u _ { n } ) ) \mathrm { d } x . } \end{array}
$$

Thus we have

$$
\begin{array} { r l r } {  { \int _ { B _ { k } } \frac { \alpha | \nabla u _ { n } | ^ { p } } { ( 1 + | u _ { n } | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x + \le \| f \| _ { 1 } + 1 - \int _ { B _ { k } } b | u _ { n } | ^ { r - 2 } u _ { n } T _ { 1 } ( u _ { n } - T _ { k } ( u _ { n } ) ) \mathrm { d } x } } \\ & { } & { \le \| f \| _ { 1 } + 1 + \int _ { B _ { k } } b | u _ { n } | ^ { r - 1 } \mathrm { d } x } \\ & { } & { \le C \bigg ( 1 + \bigg ( \int _ { B _ { k } } | u _ { n } | ^ { q ^ { \ast } } \mathrm { d } x \bigg ) ^ { \frac { r - 1 } { q ^ { \ast } } } | B _ { k } | ^ { 1 - \frac { r - 1 } { q ^ { \ast } } } \bigg ) , } \end{array}
$$

$q$ $\begin{array} { r } { q ^ { * } = \frac { N q } { N - q } } \end{array}$

Let s =@(p-1). Note that q<pand p- <q\*.For Vk >O,we estimate SBk |Vunldx as follows

$$
\begin{array} { r l } {  { \int _ { B _ { k } } | \nabla u _ { n } | ^ { q } \mathrm { d } x = \int _ { B _ { k } } \frac { | \nabla u _ { n } | ^ { q } } { ( 1 + | u _ { n } | ) ^ { s } } \cdot ( 1 + | u _ { n } | ) ^ { s } \mathrm { d } x } } \\ & { \le \bigg ( \int _ { B _ { k } } \frac { | \nabla u _ { n } | ^ { p } } { ( 1 + | u _ { n } | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x \bigg ) ^ { \frac { q } { p } } \bigg ( \int _ { B _ { k } } ( 1 + | u _ { n } | ) ^ { \frac { p s } { p - q } } \mathrm { d } x \bigg ) ^ { \frac { p - q } { p } } } \\ & { \le C \bigg ( \int _ { B _ { k } } \frac { | \nabla u _ { n } | ^ { p } } { ( 1 + | u _ { n } | ) ^ { \theta ( p - 1 ) } } \mathrm { d } x \bigg ) ^ { \frac { q } { p } } \bigg ( | B _ { k } | ^ { \frac { p - q } { p } } + \bigg ( \int _ { B _ { k } } | u _ { n } | ^ { \frac { p s } { p - q } } \mathrm { d } x \bigg ) ^ { \frac { p - q } { p } } \bigg ) } \end{array}
$$

$$
\begin{array} { r l } & { \le C \bigg ( \int _ { R _ { k } } \frac { | \nabla u _ { 1 } | ^ { p } } { ( 1 + | u _ { 1 } | ) ^ { \alpha _ { n } } } \big \| ^ { p } \bigg ) ^ { \frac { 1 } { \alpha _ { n } } } \bigg ( \left| \mathcal { B } _ { k } \right| ^ { \frac { p - \alpha _ { n } } { p } } + \bigg ( \int _ { R _ { k } } | u _ { \alpha } | ^ { p } \Phi _ { L } \bigg ) ^ { \frac { 1 } { \alpha _ { n } } } | \mathcal { B } _ { k } | ^ { \frac { 1 - n } { \alpha _ { n } } - \frac { 1 } { \alpha _ { n } } } \bigg ) } \\ & { \le C \bigg ( | \mathcal { B } _ { k } | ^ { \frac { p - \alpha _ { n } } { p } } + | \mathcal { B } _ { k } | ^ { \frac { p - \alpha _ { n } } { p } - \frac { 1 } { \alpha _ { n } } } \bigg ( \int _ { R _ { k } } | u _ { n } | ^ { \alpha _ { n } } \Phi _ { L } ^ { 1 } \bigg ) ^ { \frac { 1 } { \alpha _ { n } } } + | \mathcal { B } _ { k } | ^ { 1 - n } \bigg ( \int _ { \mathcal { B } _ { k } } | u _ { n } | ^ { p } \Phi _ { L } ^ { 1 } \bigg ) ^ { p } } \\ & { \quad + | \mathcal { B } _ { k } | ^ { 1 - p } \bigg ( \int _ { \mathcal { B } _ { k } } | u _ { \alpha } | ^ { p } \Phi _ { L } ^ { 1 } \bigg ) ^ { p } \bigg ) \quad \mathrm { ~ b y ~ } ( 2 S ) } \\ & { = C \bigg ( | \mathcal { B } _ { k } | ^ { \frac { 1 - n } { \alpha _ { n } } } + | \mathcal { B } _ { k } | ^ { \frac { p - \alpha _ { n } } { p } - \alpha _ { n } } \bigg ( \int _ { \mathcal { B } _ { k } } | u _ { \alpha } | ^ { \alpha _ { n } } \Phi _ { L } \bigg ) ^ { \frac { 1 } { \alpha _ { n } } } } \\ & { \quad + | \mathcal { B } _ { k } | ^ { 1 - p - \alpha _ { n } } | \mathcal { B } _ { k } | ^ { \alpha _ { n } } \bigg ( \int _ { \mathcal { B } _ { k } } | u _ { \alpha } | ^ { p } \Phi _ { L } ^ { 1 } \bigg ) ^ { \frac { 1 } { \alpha _ { n } } } } \\ & { \quad + | \mathcal { B } _ { k } | ^ { 1 - p - \alpha _ { n } } | \mathcal { B } _ { k } | ^ { \alpha _ { n } } \bigg ( \int _ { \mathcal { B } _ { k } } | u _ { \alpha } | ^ { p } 4 \Phi _ { L } ^ { 1 - p } \bigg ) ^ { \frac { 1 } { \alpha _ { n } } } \bigg ) . } \end{array}
$$

where p1 = qr-1, $\begin{array} { r } { p _ { 1 } = \frac { q } { p } \frac { r - 1 } { q ^ { * } } , p _ { 2 } = \frac { s } { q ^ { * } } + \frac { q } { p } \frac { r - 1 } { q ^ { * } } } \end{array}$ ， $C _ { 1 }$ and $C _ { 2 }$ are positive constants to be chosen later. Note that $\theta < \textstyle { \frac { p - r } { p - 1 } }$ p-1, it follows

$$
\frac { \theta ( p - 1 ) } { p } + \frac { r - 1 } { p } < \frac { p - 1 } { p } < 1 - \frac { 1 } { N } = 1 - \frac { 1 } { q } + \frac { 1 } { q ^ { * } } .
$$

Thus

$$
\frac { \theta q ( p - 1 ) } { p } + \frac { q ( r - 1 ) } { p } + 1 < q + \frac { q } { q ^ { * } } \Leftrightarrow s + \frac { q ( r - 1 ) } { p } + 1 < q + \frac { q } { q ^ { * } } \Leftrightarrow p _ { 2 } + \frac { 1 - p _ { 2 } } { q ^ { * } + 1 } < \frac { q } { q ^ { * } } .
$$

Note that $p _ { 1 } < p _ { 2 } < 1$ . Then for $i = 1 , 2$ , we always have

$$
p _ { i } + \frac { 1 - p _ { i } } { q ^ { * } + 1 } < \frac { q } { q ^ { * } } < 1 .
$$

From this, we may find positive $C _ { i } ( i = 1 , 2 )$ such that

$$
p _ { i } + \frac { 1 - p _ { i } } { q ^ { * } + 1 } < p _ { i } + C _ { i } < \frac { q } { q ^ { * } } < 1 , \ i = 1 , 2 .
$$

It follows

$$
\frac { 1 - p _ { i } } { q ^ { * } + 1 } < C _ { i } \Leftrightarrow 1 - p _ { i } - C _ { i } < C _ { i } q ^ { * } , \ i = 1 , 2 ,
$$

which implies

$$
C _ { i } \alpha _ { i } q ^ { * } = \frac { C _ { i } q ^ { * } } { 1 - p _ { i } - C _ { i } } > 1 , i = 1 , 2 ,
$$

with $\begin{array} { r } { \alpha _ { i } = \frac { 1 } { 1 - p _ { i } - C _ { i } } > 1 } \end{array}$ ， $i = 1 , 2$ Let $\begin{array} { r } { \beta _ { i } = \frac { 1 } { p _ { i } + C _ { i } } > 1 , i = 1 , 2 } \end{array}$ Then we have $\begin{array} { r } { \frac { 1 } { \alpha _ { i } } + \frac { 1 } { \beta _ { i } } = 1 ( i = 1 , 2 ) } \end{array}$ ， Since $\begin{array} { r } { | B _ { k } | \le \frac { 1 } { k ^ { q ^ { * } } } \int _ { B _ { k } } | u _ { n } | ^ { q ^ { * } } \mathrm { d } x , | B _ { k } | ^ { 1 - p _ { 1 } - C _ { 1 } } \le | \Omega | ^ { 1 - p _ { 1 } - C _ { 1 } } } \end{array}$ and $| B _ { k } | ^ { 1 - p _ { 2 } - C _ { 2 } } \leq | \Omega | ^ { 1 - p _ { 2 } - C _ { 2 } }$ , we have for $k \geq k _ { 0 } \geq 1$ （204号

$$
\int _ { B _ { k } } | \nabla u _ { n } | ^ { q } \mathrm { d } x \le \frac { C } { k ^ { q ^ { * } } \big ( \frac { p - q } { p } - \frac { s } { q ^ { * } } \big ) } \bigg ( \int _ { B _ { k } } | u _ { n } | ^ { q ^ { * } } \mathrm { d } x \bigg ) ^ { \frac { p - q } { p } } + \frac { C } { k ^ { q ^ { * } } C _ { 1 } } \bigg ( \int _ { B _ { k } } | u _ { n } | ^ { q ^ { * } } \mathrm { d } x \bigg ) ^ { p _ { 1 } + C _ { 1 } } + \frac { C } { k ^ { q ^ { * } C _ { 2 } } } \bigg ( \int _ { B _ { k } } | u _ { n } | ^ { q ^ { * } } \mathrm { d } x \bigg ) ^ { p _ { 2 } } ,
$$

Summing up from $k = k _ { 0 }$ to $k = K$ and using Holder's inequality,one has

$$
\begin{array} { r l } { \displaystyle \sum _ { i = \infty } ^ { n } \int _ { B _ { h } } | \nabla \mathbf { u } _ { h } | ^ { - 1 } \mathrm { d } \boldsymbol { \le } C \bigg ( \displaystyle \sum _ { i = \infty } ^ { N } \frac { 1 } { B ^ { \prime } ( h ^ { \prime } \setminus \mathbf { e } ^ { - 1 } ) \Omega } \bigg ) ^ { * } \cdot \bigg ( \displaystyle \sum _ { i = \infty } ^ { N } \int _ { B _ { h } } | \mathbf { u } _ { h } | ^ { - 1 } \mathrm { d } \boldsymbol { \le } \int _ { \Omega } ^ { \infty } } & { \bigg | \mathrm { d } \boldsymbol { \le } \int _ { \Omega } ^ { \infty } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad + C \bigg ( \displaystyle \sum _ { i = \infty } ^ { N } \frac { 1 } { B ^ { \prime } ( h ^ { \prime } \setminus \mathbf { e } ^ { - 1 } ) \omega } \bigg ) ^ { * } \cdot \bigg ( \displaystyle \sum _ { i = \infty } ^ { N } \bigg ( \int _ { B _ { h } } | \mathbf { u } _ { h } | ^ { - 1 } \mathrm { d } \boldsymbol { \le } \int _ { \Omega } ^ { \infty } \bigg ) ^ { * _ { i + \infty } ( 1 + \omega ) } \bigg ) ^ { * _ { i } } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { = C \bigg ( \displaystyle \sum _ { i = \infty } ^ { N } \frac { 1 } { B ^ { \prime } ( h ^ { \prime } \setminus \mathbf { e } ^ { - 1 } ) \omega } \bigg ) ^ { * _ { i } } \cdot \bigg ( \displaystyle \sum _ { i = \infty } ^ { N } \int _ { B _ { h } } | \mathbf { u } _ { h } | ^ { - 1 } \mathrm { d } \boldsymbol { \le } \int _ { \Omega } ^ { \infty } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ &  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \end{array}
$$

Note that

$$
\int _ { \{ | u _ { n } | \leq K \} } | \nabla u _ { n } | ^ { q } \mathrm { d } x = \int _ { D _ { k _ { 0 } } } | \nabla u _ { n } | ^ { q } \mathrm { d } x + \sum _ { k = k _ { 0 } } ^ { K } \int _ { B _ { k } } | \nabla u _ { n } | ^ { q } \mathrm { d } x .
$$

To estimate the first integral inthe right-hand sideof (29), wecompute byusing Holder's inequalityand (24),obtaining

$$
\begin{array}{c} \int _ { { D _ { k _ { 0 } } } } | \nabla u _ { n } | ^ { q } \mathrm d x \leq \left( \int _ { { D _ { k _ { 0 } } } } \frac { | \nabla u _ { n } | ^ { p } } { \left( 1 + | u _ { n } | \right) ^ { \theta ( p - 1 ) } } \mathrm d x \right) ^ { \frac { q } { p } } \Bigg ( \int _ { { D _ { k _ { 0 } } } } ( 1 + | u _ { n } | ) ^ { \frac { p s } { p - q } } \mathrm d x \Bigg ) ^ { \frac { p - q } { p } }  \\ { \leq C , } \end{array}
$$

where $C$ depending only on $\alpha , \beta , b , p , \theta , \| \boldsymbol { j } \| _ { p ^ { \prime } } , \| \boldsymbol { f } \| _ { 1 } , \| \nabla v _ { 0 } \| _ { p } , \| v _ { 0 } \| _ { \infty } \mathrm { a n d }$ ko.

Note that $\sum _ { k = k _ { 0 } } ^ { K } \frac { 1 } { { k ^ { q ^ { * } ( \frac { p - q } { p } - \frac { s } { q ^ { * } } ) \frac { p } { q } } } }$ and $\sum _ { k = k _ { 0 } } ^ { K } \frac { 1 } { k ^ { q ^ { * } C _ { i } \alpha _ { i } } }$ converge due to the fact that $\begin{array} { r } { q ^ { * } ( \frac { p - q } { p } - \frac { s } { q ^ { * } } ) \frac { p } { q } > 1 } \end{array}$ and $q ^ { * } C _ { i } \alpha _ { i } > 1$ by (27), respectively. Combining (28)-(30),we get for $k _ { 0 }$ large enough

$$
\begin{array} { r l } & { \displaystyle \int _ { \{ | u _ { n } | \leq K \} } | \nabla u _ { n } | ^ { q } \mathrm { d } x \leq C + C \biggl ( \displaystyle \int _ { \{ | u _ { n } | \leq K \} } | u _ { n } | ^ { q ^ { \ast } } \mathrm { d } x \biggr ) ^ { \frac { p - q } { p } } + C \biggl ( \displaystyle \int _ { \{ | u _ { n } | \leq K \} } | u _ { n } | ^ { q ^ { \ast } } \mathrm { d } x \biggr ) ^ { \frac { p _ { 1 } + C _ { 1 } } { 1 + C _ { 1 } } } } \\ & { \qquad + C \biggl ( \displaystyle \int _ { \{ | u _ { n } | \leq K \} } | u _ { n } | ^ { q ^ { \ast } } \mathrm { d } x \biggr ) ^ { p _ { 2 } + C _ { 2 } } . } \end{array}
$$

Since $p > q$ $T _ { K } ( u _ { n } ) \in W ^ { 1 , q } ( \Omega )$ $T _ { K } ( g ) = g \in W ^ { 1 , q } ( \Omega )$ for $K > \| g \| _ { \infty }$ .Hence $T _ { K } ( u _ { n } ) - g \in W _ { 0 } ^ { 1 , q } ( \Omega )$ . Using the Sobolev embedding $W _ { 0 } ^ { 1 , q } ( \Omega ) \subset L ^ { q ^ { * } } ( \Omega )$ and Poincaré inequality, we obtain

$$
\begin{array} { r l } { \| T _ { K } ( u _ { n } ) \| _ { q ^ { * } } ^ { q } \leq 2 ^ { q - 1 } ( \| T _ { K } ( u _ { n } ) - g \| _ { q ^ { * } } ^ { q } + \| g \| _ { q ^ { * } } ^ { q } ) } & { } \\ { \ } & { \leq C ( \| \nabla ( T _ { K } ( u _ { n } ) - g ) \| _ { q } ^ { q } + \| g \| _ { q ^ { * } } ^ { q } ) } \\ { \ } & { \leq C ( \| \nabla T _ { K } ( u _ { n } ) \| _ { q } ^ { q } + \| \nabla g \| _ { q } ^ { q } + \| g \| _ { q ^ { * } } ^ { q } ) } \\ { \ } & { \leq C \biggr ( 1 + \displaystyle \int _ { \{ | u _ { n } | \leq K \} } | \nabla u _ { n } | ^ { q } \mathrm { d } x \biggr ) . } \end{array}
$$

Using the fact that

$$
\int _ { \{ | u _ { n } | \leq K \} } { | u _ { n } | ^ { q ^ { * } } } \mathrm { d } x \leq \int _ { \{ | u _ { n } | \leq K \} } { | T _ { K } ( u _ { n } ) | ^ { q ^ { * } } } \mathrm { d } x \leq \| T _ { K } ( u _ { n } ) \| _ { q ^ { * } } ^ { q ^ { * } } ,
$$

we obtain from (31)-(32),

$$
\begin{array} { r l } & { \displaystyle \int _ { \{ | u _ { n } | \le K \} } | \nabla u _ { n } | ^ { q } \mathrm { d } x \le C + C \bigg ( 1 + \displaystyle \int _ { \{ | u _ { n } | \le K \} } | \nabla u _ { n } | ^ { q } \mathrm { d } x \bigg ) ^ { \frac { q ^ { * } } { q } \frac { p - q } { p } } + C \bigg ( 1 + \displaystyle \int _ { \{ | u _ { n } | \le K \} } | \nabla u _ { n } | ^ { q } \mathrm { d } x \bigg ) ^ { ( p _ { 1 } + C _ { 1 } ) } } \\ & { \qquad + C \bigg ( 1 + \displaystyle \int _ { \{ | u _ { n } | \le K \} } | \nabla u _ { n } | ^ { q } \mathrm { d } x \bigg ) ^ { ( p _ { 2 } + C _ { 2 } ) \frac { q ^ { * } } { q } } . } \end{array}
$$

Note that $\begin{array} { r } { p < N \Leftrightarrow \frac { q ^ { * } } { q } \frac { p - q } { p } < 1 } \end{array}$ and $\begin{array} { r } { ( p _ { i } { + } C _ { i } ) \frac { q ^ { * } } { q } < 1 } \end{array}$ by(26).Itff $k _ { 0 }$ large enough, $\begin{array} { r } { \int _ { \{ | u _ { n } | \leq K \} } | \nabla u _ { n } | ^ { q } \mathrm { d } x } \end{array}$ （204 is bounded independently of $n$ and $K$ .Using (32)and(33),wedeucethat $\begin{array} { r } { \int _ { \{ | u _ { n } | \leq K \} } | u _ { n } | ^ { q ^ { * } } \mathrm { d } x } \end{array}$ is also bounded independently of $n$ and $K$ Letting $K  \infty$ , we deduce that $\| \nabla u _ { n } \| _ { q }$ and $\| u _ { n } \| _ { q ^ { * } }$ are uniformly bounded independently of $n$ . Particularly, $u _ { n }$ is bounded in $W ^ { 1 , q } ( \Omega )$ . Therefore, there exists a subsequence of $\left\{ u _ { n } \right\}$ and a function $v \in W ^ { 1 , q } ( \Omega )$ such that $u _ { n } \ \to v$ （20 weakly in $W ^ { 1 , q } ( \Omega )$ $u _ { n } \to v$ strongly in $L ^ { q } ( \Omega )$ and a.e. in $\Omega$ By Lemma 3, $u _ { n } \to u$ in measure in $\Omega$ , we conclude that $u = v$ and $u \in W ^ { 1 , q } ( \Omega )$ ：

Lemma 6 There exists a subsequence of $\{ u _ { n } \}$ and a measurable function u such that $\nabla u _ { n }$ cConverges almost everywhere in $\Omega$ to $\nabla u .$ （20

Proof Theproofisquite similartoTheorem4.1in[1],whichcanbealsofoundin[5].Here we sketchonlythe mainsteps due toslightmodifiatisFor1et1ereqis hesi5.DeieA(xu,)= (for the sake of simplicity,we omit the dependence of $A ( x , u , \xi )$ on $x$ and

$$
I ( \boldsymbol n ) = \int _ { \Omega } ( ( A ( u _ { n } , \nabla u _ { n } ) - A ( u _ { n } , \nabla u ) ) \cdot \nabla ( u _ { n } - u ) ) ^ { \lambda } \mathrm { d } x .
$$

We fix $k > 0$ and split the integral in $I ( n )$ on the sets $\{ | u | > k \}$ and $\{ | u | \leq k \}$ , obtaining

$$
I _ { 1 } ( n , k ) = \int _ { \{ | u | > k \} } ( ( A ( u _ { n } , \nabla u _ { n } ) - A ( u _ { n } , \nabla u ) ) \cdot \nabla ( u _ { n } - u ) ) ^ { \lambda } \mathrm { d } x ,
$$

and

$$
I _ { 2 } ( \boldsymbol n , \boldsymbol k ) = \int _ { \{ | \boldsymbol u | \leq \boldsymbol k \} } ( ( A ( \boldsymbol u _ { n } , \nabla \boldsymbol u _ { n } ) - A ( \boldsymbol u _ { n } , \nabla \boldsymbol u ) ) \cdot \nabla ( \boldsymbol u _ { n } - \boldsymbol u ) ) ^ { \lambda } \mathrm { d } \boldsymbol x .
$$

For $I _ { 2 } ( n , k )$ , one has

$$
I _ { 2 } ( n , k ) \leq I _ { 3 } ( n , k ) = \int _ { \Omega } ( ( A _ { n } ( u _ { n } , \nabla u _ { n } ) - A _ { n } ( u _ { n } , \nabla T _ { k } ( u ) ) ) \cdot \nabla ( u _ { n } - T _ { k } ( u ) ) ) ^ { \lambda } d x .
$$

Fix $h > 0$ and split $I _ { 3 } ( n , k )$ on the sets $\{ | u _ { n } - T _ { k } ( u ) | > h \}$ and $\{ | u _ { n } - T _ { k } ( u ) | \leq h \}$ ,obtaining

$$
I _ { 4 } ( n , k , h ) = \int _ { \{ | u _ { n } - T _ { k } ( u ) | > h \} } \left( \left( A _ { n } ( u _ { n } , \nabla u _ { n } ) - A _ { n } ( u _ { n } , \nabla T _ { k } ( u ) ) \right) \cdot \nabla ( u _ { n } - T _ { k } ( u ) ) \right) ^ { \lambda } \mathrm { d } x ,
$$

and

$$
I _ { 5 } ( n , k , h ) = \int _ { \{ | u _ { n } - T _ { k } ( u ) | \leq h \} } \left( \left( A _ { n } ( u _ { n } , \nabla u _ { n } ) - A _ { n } ( u _ { n } , \nabla T _ { k } ( u ) ) \right) \cdot \nabla ( u _ { n } - T _ { k } ( u ) ) \right) ^ { \lambda } \mathrm { d } x
$$

$$
\begin{array} { l } { \displaystyle = \int _ { \Omega } ( ( A _ { n } \big ( \boldsymbol { u } _ { n } , \nabla \boldsymbol { u } _ { n } \big ) - A _ { n } \big ( \boldsymbol { u } _ { n } , \nabla T _ { k } ( \boldsymbol { u } ) \big ) ) \cdot \nabla T _ { h } \big ( \boldsymbol { u } _ { n } - T _ { k } ( \boldsymbol { u } ) \big ) \big ) ^ { \lambda } \mathrm { d } x } \\ { \displaystyle \le | \Omega | ^ { 1 - \lambda } \bigg ( \int _ { \Omega } ( A _ { n } \big ( \boldsymbol { u } _ { n } , \nabla \boldsymbol { u } _ { n } \big ) - A _ { n } \big ( \boldsymbol { u } _ { n } , \nabla T _ { k } ( \boldsymbol { u } ) \big ) ) \cdot \nabla T _ { h } \big ( \boldsymbol { u } _ { n } - T _ { k } ( \boldsymbol { u } ) \big ) \mathrm { d } x \bigg ) ^ { \lambda } } \\ { \displaystyle = | \Omega | ^ { 1 - \lambda } \big ( I _ { 6 } ( n , k , h ) \big ) ^ { \lambda } . } \end{array}
$$

For $I _ { 6 } ( n , k , h )$ , it can be split as the difference $I _ { 7 } ( n , k , h ) - I _ { 8 } ( n , k , h )$ where

$$
I _ { 7 } ( n , k , h ) = \int _ { \Omega } A ( u _ { n } , \nabla u _ { n } ) \cdot \nabla T _ { h } ( u _ { n } - T _ { k } ( u ) ) \mathrm { d } x ,
$$

and

$$
I _ { 8 } ( n , k , h ) = \int _ { \Omega } A ( u _ { n } , \nabla T _ { k } ( u ) ) \cdot \nabla T _ { h } ( u _ { n } - T _ { k } ( u ) ) \mathrm { d } x .
$$

Note that $\left| \nabla u _ { n } \right|$ is bounded in $L ^ { q } ( \Omega )$ and $\lambda p r _ { 2 } = q$ . Thanks to Lemma 3 and Lemma 5,one may get in the same way as Theorem 4.1 in[1] that

$$
\operatorname* { l i m } _ { k \to \infty } \operatorname* { l i m } _ { n \to \infty } \operatorname* { s u p } _ { 0 } I _ { 1 } ( n , k ) = 0 , \operatorname* { l i m } _ { h \to \infty } \operatorname* { l i m } _ { k \to \infty } \operatorname* { s u p } _ { n \to \infty } I _ { 4 } ( n , k , h ) = 0 , \operatorname* { l i m } _ { n \to \infty } I _ { 8 } ( n , k , h ) = 0 .
$$

For $I _ { 7 } ( n , k , h )$ ,let $k > \operatorname* { m a x } \{ \| g \| _ { \infty } , \| \psi \| _ { \infty } \}$ and $n \geq h + k$ . Take $T _ { k } ( u )$ as a test function for (7), obtaining

$$
I _ { 7 } ( n , k , h ) \leq \int _ { \Omega } f _ { n } T _ { h } \big ( u _ { n } - T _ { k } ( u ) \big ) \mathrm { d } x + \int _ { \Omega } b | u _ { n } | ^ { r - 2 } u _ { n } T _ { h } \big ( u _ { n } - T _ { k } ( u ) \big ) \mathrm { d } x .
$$

Note that $r - 1 < q ^ { * }$ ，and $\begin{array} { r } { \int _ { \Omega } | u _ { n } | ^ { q ^ { * } } \mathrm { d } x } \end{array}$ is uniformly bounded (see the proof of Lemma 5), thus $\left| u _ { n } \right|$ converges strongly in $L ^ { 1 } ( \Omega )$ . Therefore we have

$$
\operatorname* { l i m } _ { n \to \infty } \int _ { \Omega } | u _ { n } | ^ { r - 2 } u _ { n } T _ { h } ( u _ { n } - T _ { k } ( u ) ) \mathrm { d } x = \int _ { \Omega } | u | ^ { r - 2 } u T _ { h } ( u - T _ { k } ( u ) ) \mathrm { d } x .
$$

Then using the strong convergence of $f _ { n }$ in $L ^ { 1 } ( \Omega )$ , one has

$$
\operatorname* { l i m } _ { n \to \infty } I _ { 7 } ( n , k , h ) \leq \int _ { \Omega } - f T _ { h } ( u - T _ { k } ( u ) ) \mathrm { d } x + \int _ { \Omega } b | u | ^ { r - 2 } u T _ { h } ( u - T _ { k } ( u ) ) \mathrm { d } x .
$$

It follows

$$
\operatorname* { l i m } _ { k \to \infty } \operatorname* { l i m } _ { n \to \infty } I _ { 7 } ( n , k , h ) \leq 0 .
$$

Putting together all the limitations and noting that $I ( n ) \geq 0$ ,we have

$$
\operatorname* { l i m } _ { n \to \infty } I ( n ) = 0 .
$$

The same arguments as [1] give that, up to subsequence, $\nabla u _ { n } ( x )  \nabla u ( x )$ a.e..

Proof of Proposition 4We shall prove that $\nabla u _ { n }$ converges strongly to $\nabla u _ { n }$ in $L ^ { q } ( \Omega )$ for each $q$ ,being given by (8). To do that,we will apply Vitali's Theorem, using the fact that by Lemma 5, $\nabla u _ { n }$ is bounded in $L ^ { q } ( \Omega )$ for each $q$ given by (8). So let $\begin{array} { r } { s \in ( q , \frac { N ( p - 1 ) \bar { ( 1 - \theta ) } } { N - 1 - \theta ( p - 1 ) } ) } \end{array}$ and $E \subset \Omega$ be a measurable set. Then, we have by Holder's inequality.

$$
\int _ { E } | \nabla u _ { n } | ^ { q } \mathrm { d } x \leq ( \int _ { E } | \nabla u _ { n } | ^ { r } \mathrm { d } x ) ^ { \frac { q } { s } } \cdot | E | ^ { \frac { s - q } { s } } \leq C | E | ^ { \frac { s - q } { s } }  0
$$

uniformly in $n$ ,as $| E | \to 0$ . From this and Lemma 6, we deduce that $\nabla u _ { n }$ converges strongly to $\nabla \boldsymbol { u }$ in $L ^ { q } ( \Omega )$

Now assume that $\begin{array} { r } { 0 \leq \theta < \operatorname* { m i n } \{ \frac { 1 } { N - p + 1 } , \frac { N } { N - 1 } - \frac { 1 } { p - 1 } , \frac { p - r } { p - 1 } \} } \end{array}$ . Note that since $\nabla u _ { n }$ converges to $\nabla \boldsymbol { u }$ a.e. in $\Omega$ , to prove the convergence

$$
{ \frac { a ( x , \nabla u _ { n } ) } { ( 1 + | u _ { n } | ) ^ { \theta ( p - 1 ) } } } \to { \frac { a ( x , \nabla u ) } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } } \ \mathrm { s t r o n g l y i n } \ ( L ^ { 1 } ( \Omega ) ) ^ { N } ,
$$

$E \subset \Omega$ $\begin{array} { r } { \int _ { E } \Big \lvert \frac { a ( x , \nabla u _ { n } ) } { ( 1 + \lvert u _ { n } \rvert ) ^ { \theta ( p - 1 ) } } \Big \rvert \mathrm { d } x } \end{array}$ $n$ $| E | \to 0$ Note hat $\begin{array} { r } { p - 1 < \frac { N ( p - 1 ) ( 1 - \theta ) } { N - 1 - \theta ( p - 1 ) } ) } \end{array}$ by asumptions.fo a $\begin{array} { r } { q \in ( p - 1 , \frac { N ( p - 1 ) ( 1 - \theta ) } { N - 1 - \theta ( p - 1 ) } ) ) } \end{array}$ . wededce byHolder's inequality

$$
\begin{array} { r l } { \displaystyle \int _ { E } \bigg | \frac { a ( x , \nabla u _ { n } ) } { ( 1 + | u _ { n } | ) ^ { \theta ( p - 1 ) } } \bigg | \mathrm { d } x \le \beta \displaystyle \int _ { E } ( j + | \nabla u _ { n } | ^ { p - 1 } ) \mathrm { d } x } & { } \\ { \le \beta \| j \| _ { p ^ { \prime } } | E | ^ { \frac { 1 } { p } } + \beta \bigg ( \displaystyle \int _ { E } | \nabla u _ { n } | ^ { q } \mathrm { d } x \bigg ) ^ { \frac { q } { p - 1 } } | E | ^ { \frac { q - p + 1 } { q } } } & { } \\ { \to 0 \mathrm { ~ u n i f o r m l y ~ i n ~ } n \mathrm { ~ a s ~ } | E | \to 0 . } \end{array}
$$

Lemma 7 There exists a subsequence of $\{ u _ { n } \}$ such that for all $k > 0$

$$
\frac { a ( x , \nabla T _ { k } ( u _ { n } ) ) } { ( 1 + | T _ { k } ( u _ { n } ) | ) ^ { \theta ( p - 1 ) } } \to \frac { a ( x , \nabla T _ { k } ( u ) ) } { ( 1 + | T _ { k } ( u ) | ) ^ { \theta ( p - 1 ) } } s t r o n g l y i n \left( L ^ { 1 } ( \Omega ) \right) ^ { N } .
$$

Proof Let $k$ be a positive number. It is well known that if a sequence of measurable functions $\{ u _ { n } \}$ with uniformly boundedness in $L ^ { s } ( \Omega ) ( s > 1 )$ converges in measure to $u$ ,then, $u _ { n }$ converges strongly to $u$ in $L ^ { 1 } ( \Omega )$ .First note that the sequence {)sodeinL().Ideed,eb3)

$$
\begin{array} { r l } {  { \int _ { \Omega } \Big | \frac { a ( \boldsymbol { x } , \nabla T _ { k } ( \boldsymbol { u } _ { n } ) ) } { ( 1 + | T _ { k } ( \boldsymbol { u } _ { n } ) | ) ^ { \theta ( p - 1 ) } } \Big | ^ { p ^ { \prime } } \mathrm { d } \boldsymbol { x } \le \beta \| \boldsymbol { j } \| _ { p ^ { \prime } } ^ { p ^ { \prime } } + \beta \int _ { \Omega } \frac { | \nabla T _ { k } ( \boldsymbol { u } _ { n } ) | ^ { p } } { ( 1 + | T _ { k } ( \boldsymbol { u } _ { n } ) | ) ^ { \theta p } } \mathrm { d } \boldsymbol { x } } } \\ & { \le \beta \| \boldsymbol { j } \| _ { p ^ { \prime } } ^ { p ^ { \prime } } + \beta \int _ { \Omega } \frac { | \nabla T _ { k } ( \boldsymbol { u } _ { n } ) | ^ { p } } { ( 1 + | T _ { k } ( \boldsymbol { u } _ { n } ) | ) ^ { \theta ( p - 1 ) } } \mathrm { d } \boldsymbol { x } } \\ & { \le C . } \end{array}
$$

Next, it suffices to show that there exists a subsequence of $\left\{ u _ { n } \right\}$ such that

$$
\frac { a ( x , \nabla T _ { k } ( u _ { n } ) ) } { ( 1 + | T _ { k } ( u _ { n } ) | ) ^ { \theta ( p - 1 ) } } \to \frac { a ( x , \nabla T _ { k } ( u ) ) } { ( 1 + | T _ { k } ( u ) | ) ^ { \theta ( p - 1 ) } } \mathrm { ~ i n ~ m e a s u r e } .
$$

Note that $u _ { n } , u \in \ : W ^ { 1 , q } ( \Omega )$ ， where $q$ is the same as in Proposition 4. The a.e. convergence of $u _ { n }$ t0 $u$ and the fact that $\nabla u _ { n }  \nabla u$ in measure imply that

$$
\nabla T _ { k } ( u _ { n } )  \nabla T _ { k } ( u ) \mathrm { i n } \mathrm { m e a s u r e } .
$$

Let $s , t$ be positive numbers and write $\begin{array} { r } { \nabla _ { A } u = \frac { a ( x , \nabla u ) } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } . } \end{array}$ Define

$$
\begin{array} { r l } & { { E } _ { n } = \{ | \nabla _ { \boldsymbol A } T _ { \boldsymbol k } ( \boldsymbol u _ { n } ) - \nabla _ { \boldsymbol A } T _ { \boldsymbol k } ( \boldsymbol u ) | > s \} , } \\ & { { E } _ { n } ^ { 1 } = \{ | \nabla T _ { \boldsymbol k } ( \boldsymbol u _ { n } ) | > t \} , } \\ & { { E } _ { n } ^ { 2 } = \{ | \nabla T _ { \boldsymbol k } ( \boldsymbol u ) | > t \} , } \end{array}
$$

$$
E _ { n } ^ { 3 } = E _ { n } \cap \{ | \nabla T _ { k } ( u _ { n } ) | \leq t \} \cap \{ | \nabla T _ { k } ( u ) | \leq t \} .
$$

Note that $E _ { n } \subset E _ { n } ^ { 1 } \cup E _ { n } ^ { 2 } \cup E _ { n } ^ { 3 }$ for each $n \geq 1$ . Using the fact by Lemma 5, the sequence $\{ u _ { n } \}$ and the fucntion $u$ are uniformly bounded in $W ^ { 1 , q } ( { \dot { \Omega } } )$ , we obtain

$$
\begin{array} { r l } & { \displaystyle \mathcal { L } ^ { N } ( E _ { n } ^ { 1 } ) \leq \frac { 1 } { t ^ { q } } \int _ { \Omega } | \nabla T _ { k } ( u _ { n } ) | ^ { q } \mathrm { d } x \leq \frac { 1 } { t ^ { q } } \int _ { \Omega } | \nabla u _ { n } | ^ { q } \mathrm { d } x \leq \frac { C } { t ^ { q } } , } \\ & { \displaystyle \mathcal { L } ^ { N } ( E _ { n } ^ { 2 } ) \leq \frac { 1 } { t ^ { q } } \int _ { \Omega } | \nabla T _ { k } ( u ) | ^ { q } \mathrm { d } x \leq \frac { 1 } { t ^ { q } } \int _ { \Omega } | \nabla u | ^ { q } \mathrm { d } x \leq \frac { C } { t ^ { q } } . } \end{array}
$$

We deduce that for any $\varepsilon > 0$ there exists $t _ { \varepsilon } > 0$ such that

$$
\mathcal L ^ { N } ( E _ { n } ^ { 1 } ) + \mathcal L ^ { N } ( E _ { n } ^ { 2 } ) < \frac { \varepsilon } { 3 } , \quad \forall t \geq t _ { \varepsilon } , \forall n \geq 1 .
$$

Note that for $a \geq b \geq 0 , \gamma \geq 0$ ,we have the following inequality

$$
\left| { \frac { 1 } { ( 1 + a ) ^ { \tau } } } - { \frac { 1 } { ( 1 + b ) ^ { \tau } } } \right| = \left| { \frac { \tau ( b - a ) } { ( 1 + c ) ^ { 1 + \tau } } } \right| \leq \tau | b - a | { \mathrm { ~ f o r ~ s o m e ~ } } c \in [ b , a ] .
$$

We deduce from (5) and (3) that in $E _ { n } ^ { 3 }$

$$
\begin{array} { r l } & { s < \lvert \nabla _ { A } T _ { k } ( u _ { n } ) - \nabla _ { A } T _ { k } ( u ) \rvert } \\ & { \quad = \Biggr \lvert a ( \frac { \displaystyle ( a ( x , \nabla T _ { k } ( u _ { n } ) ) - a ( x , \nabla T _ { k } ( u ) ) ) } { \displaystyle ( 1 + \lvert T _ { k } ( u _ { n } ) \rvert ) ^ { \theta ( p - 1 ) } } + \left( \frac { 1 } { ( 1 + \lvert T _ { k } ( u _ { n } ) \rvert ) ^ { \theta ( p - 1 ) } } - \frac { 1 } { ( 1 + \lvert T _ { k } ( u ) \rvert ) ^ { \theta ( p - 1 ) } } \right) a ( x , \nabla T _ { k } ( u ) ) \Biggr \rvert } \\ & { \quad \le \theta ( p - 1 ) \lvert T _ { k } ( u _ { n } ) - T _ { k } ( u ) \rvert \cdot \beta ( j + \lvert \nabla T _ { k } ( u ) \rvert ^ { p - 1 } ) \qquad \mathrm { i f ~ } 1 < p < 2 } \\ & { \qquad + \gamma \left\{ \begin{array} { l l } { | \nabla T _ { k } ( u _ { n } ) - \nabla T _ { k } ( u ) | ^ { p - 1 } , \qquad } \\ { | \nabla T _ { k } ( u _ { n } ) - \nabla T _ { k } ( u ) | ( 1 + \lvert \nabla T _ { k } ( u _ { n } ) \rvert + \lvert \nabla T _ { k } ( u ) \rvert ) ^ { p - 2 } , \mathrm { i f ~ } p \ge 2 } \\ { \le C _ { 0 } j \lvert T _ { k } ( u _ { n } ) - T _ { k } ( u ) \rvert + C _ { 0 } ( 1 + t ^ { p - 1 } + t ^ { p - 2 } ) ( \lvert T _ { k } ( u _ { n } ) - T _ { k } ( u ) \rvert + \lvert \nabla T _ { k } ( u _ { n } ) - \nabla T _ { k } ( u ) \rvert ) , } \end{array} \right. } \end{array}
$$

which leads to $E _ { n } ^ { 3 } \subset F _ { 1 } \cup F _ { 2 }$ ,with

$$
\begin{array} { l } { \displaystyle { F _ { 1 } = \{ j | T _ { k } ( u _ { n } ) - T _ { k } ( u ) | > \frac { s } { 2 C _ { 0 } } \} , } } \\ { \displaystyle { F _ { 2 } = \bigg \{ | T _ { k } ( u _ { n } ) - T _ { k } ( u ) | + | \nabla T _ { k } ( u _ { n } ) - \nabla T _ { k } ( u ) | > \frac { s } { 2 C _ { 0 } ( 1 + t ^ { p - 1 } + t ^ { p - 2 } ) } \bigg \} . } } \end{array}
$$

In $F _ { 1 }$ , we have

$$
\mathcal { L } ^ { N } ( F _ { 1 } ) = \frac { 2 C _ { 0 } } { s } \int _ { F _ { 1 } } \frac { s } { 2 C _ { 0 } } \mathrm { d } x < \frac { 2 C _ { 0 } } { s } \int _ { F _ { 1 } } j | T _ { k } ( u _ { n } ) - T _ { k } ( u ) | \mathrm { d } x .
$$

ByLemma 3,we deduce that there exists $n _ { 0 } = n _ { 0 } ( S , C _ { 0 } , \varepsilon )$ such that

$$
\mathcal { L } ^ { N } ( F _ { 1 } ) \leq \frac { \varepsilon } { 3 } , \ \forall n \geq n _ { 0 } .
$$

For $F _ { 2 }$ , note that $F ^ { 2 } \subset F _ { 3 } \cup F _ { 4 }$ ,with

$$
\begin{array} { l } { F _ { 3 } = \bigg \{ | T _ { k } ( u _ { n } ) - T _ { k } ( u ) | > \frac { s } { 4 C _ { 0 } ( 1 + t ^ { p - 1 } + t ^ { p - 2 } ) } \bigg \} , } \\ { F _ { 4 } = \bigg \{ | \nabla T _ { k } ( u _ { n } ) - \nabla T _ { k } ( u ) | > \frac { s } { 4 C _ { 0 } ( 1 + t ^ { p - 1 } + t ^ { p - 2 } ) } \bigg \} . } \end{array}
$$

Using the convergence in measure of $\nabla T _ { k } ( u _ { n } )$ to $\nabla T _ { k } ( u )$ and $T _ { k } ( u _ { n } )$ to $T _ { k } ( u )$ ，for $t \ = \ t _ { \varepsilon }$ ，we obtain the existence of $n _ { 1 } = \ l _ { n _ { 1 } } ( s , \varepsilon ) \geq \bar { 1 }$ such that

$$
\mathcal { L } ^ { N } ( F _ { 2 } ) \leq \mathcal { L } ^ { N } ( F _ { 3 } ) + \mathcal { L } ^ { N } ( F _ { 4 } ) < \frac { \varepsilon } { 3 } , ~ \forall ~ n \geq n _ { 1 } .
$$

Combining (35),(36) and (37),we obtain

$$
\mathcal { L } ^ { N } ( \{ | \nabla _ { A } T _ { k } ( u _ { n } ) - \nabla _ { A } T _ { k } ( u ) | > s \} ) < \varepsilon , ~ \forall ~ n \geq \operatorname* { m a x } \{ n _ { 0 } , n _ { 1 } \} .
$$

Hence the sequence $\{ \nabla _ { A } T _ { k } ( u _ { n } ) \}$ converges in measure to $\nabla _ { A } T _ { k } ( \boldsymbol { u } )$ and the lemma follows.

# 3Proof of the main result

Now we have gatheredallte lemmas needed toprove theexistence ofan entropysolutiontotheobstacle problem associated with $( f , \psi , g )$ . In this part, let $f _ { n }$ be a sequence of smooth functions converging strongly to $f$ in $L ^ { 1 } ( \Omega )$ , with $\| f _ { n } \| _ { 1 } \leq \| f \| _ { 1 } + 1$ We consider the sequence of approximated obstacle problems associated with $( f _ { n } , \psi , g )$ ：

Proof of Theorem 1 Let $v \in K _ { g , \psi } \cap L ^ { \infty } ( \Omega )$ .Taking $v$ as a test function in (7) associated with $( f _ { n } , \psi , g )$ , we get

$$
\int _ { \Omega } \frac { a ( x , \nabla u _ { n } ) } { ( 1 + | u _ { n } | ) ^ { \theta ( p - 1 ) } } \cdot \nabla ( T _ { t } ( u _ { n } - v ) ) \mathrm { d } x + \int _ { \Omega } b | u _ { n } | ^ { r - 2 } u _ { n } T _ { t } ( u _ { n } - v ) \mathrm { d } x \leq \int _ { \Omega } f _ { n } T _ { t } ( u _ { n } - v ) \mathrm { d } x .
$$

Since $\{ | u _ { n } - v | < t \} \subset \{ | u _ { n } | < s \}$ with $s = t + \| v \| _ { \infty }$ , the previous inequality can be written as

$$
\int _ { \Omega } \chi _ { n } \nabla _ { A } T _ { s } ( u _ { n } ) \cdot \nabla v \mathrm { d } x \ge \int _ { \Omega } - f _ { n } T _ { t } ( u _ { n } - v ) \mathrm { d } x + \int _ { \Omega } b | u _ { n } | ^ { r - 2 } u _ { n } T _ { t } ( u _ { n } - v ) \mathrm { d } x + \int _ { \Omega } \chi _ { n } \nabla _ { A } T _ { s } ( u _ { n } ) \cdot \nabla v _ { n } \mathrm { d } x .
$$

where $\chi _ { n } = \chi _ { \{ | u _ { n } - v | < t \} }$ and $\begin{array} { r } { \nabla _ { A } u = \frac { a ( x , \nabla u ) } { ( 1 + | u | ) ^ { \theta ( p - 1 ) } } } \end{array}$ It is cler hat $\chi _ { n }  \chi$ weakly\* in $L ^ { \infty } ( \Omega )$ . Moreover, $\chi _ { n }$ converges a.e. to $\chi _ { \{ | u - v | < t \} }$ in $\Omega \setminus \{ | u - v | = t \}$ . It follows that

$$
\chi = { \left\{ \begin{array} { l l } { 1 , { \mathrm { ~ i n ~ } } \{ | u - v | < t \} , } \\ { 0 , { \mathrm { ~ i n ~ } } \{ | u - v | > t \} . } \end{array} \right. }
$$

Note that we have ${ \mathcal { L } } ^ { N } ( \{ | u - v | = t \} ) = 0$ for a.e. $t \in ( 0 , \infty )$ . So there exists a measurable set $\mathcal { O } \subset \left( 0 , \infty \right)$ such that $\mathcal { L } ^ { N } ( \{ | u - v | = t \} ) = \dot { 0 }$ for all $t \in ( 0 , \infty ) \backslash \mathcal { O }$ . Assume that $t \in ( 0 , \infty ) \backslash \mathcal { O }$ . Then $\chi _ { n }$ converges weakly\* in $L ^ { \infty } ( \Omega )$ and a.e. in $\Omega$ 0 $\chi = \chi _ { \{ | u - v | < t \} }$ . Since $\nabla T _ { s } ( u _ { n } )$ converges a.e. to $\nabla T _ { s } ( u )$ .m $\Omega$ (Proposition 4), we obtain by Fatou's Lemma

$$
\operatorname* { l i m i n f } _ { n  \infty } \int _ { \Omega } \chi _ { n } \nabla _ { A } T _ { s } ( u _ { n } ) \cdot \nabla T _ { s } ( u _ { n } ) \mathrm { d } x \geq \int _ { \Omega } \chi \nabla _ { A } T _ { s } ( u ) \cdot \nabla T _ { s } ( u ) \mathrm { d } x .
$$

Using the strong convergence of $\nabla _ { A } T _ { s } ( u _ { n } )$ t0 $\nabla _ { A } T _ { s } ( \boldsymbol { u } )$ in $L ^ { 1 } ( \Omega )$ (Lemma 7) and the weak\* convergence of $\chi _ { n }$ t0 $\chi$ in $L ^ { \infty } ( \Omega )$ , we obtain

$$
\operatorname* { l i m } _ { n  \infty } \int _ { \Omega } \chi _ { n } \nabla _ { A } T _ { s } ( u _ { n } ) \cdot \nabla v \mathrm { d } x = \int _ { \Omega } \chi \nabla _ { A } T _ { s } ( u ) \cdot \nabla v \mathrm { d } x .
$$

Moreover, due to the strong convergence of $f _ { n }$ to $f$ and $| u _ { n } | ^ { r - 2 } u _ { n }$ t0 $| u | ^ { r - 2 } u$ (by $r - 1 < q ^ { * }$ and the boundedness of $\| u _ { n } \| _ { q ^ { * } } )$ （20 in $L ^ { 1 } ( \Omega )$ , and the weak\* convergence of $T _ { t } ( u _ { n } - v )$ to $T _ { t } ( u - v )$ in $L ^ { \infty } ( \Omega )$ ,by passing to the limit in (38) and taking into account (39)-(40),we obtain

$$
\int _ { \Omega } \chi \nabla _ { A } T _ { s } ( u ) \cdot \nabla v \mathrm { d } x - \int _ { \Omega } \chi \nabla _ { A } T _ { s } ( u ) \cdot \nabla T _ { s } ( u ) \mathrm { d } x \geq \int _ { \Omega } - f T _ { t } ( u - v ) \mathrm { d } x + \int _ { \Omega } b | u | ^ { r - 2 } u T _ { t } ( u - v ) \mathrm { d } x ,
$$

which can be written as

$$
\int _ { \{ | v - u | \leq t \} } \chi \nabla _ { A } T _ { s } ( u ) \cdot ( \nabla v - \nabla u ) \mathrm { d } x \geq \int _ { \Omega } - f T _ { t } ( u - v ) \mathrm { d } x + \int _ { \Omega } b | u | ^ { r - 2 } u T _ { t } ( u - v ) \mathrm { d } x ,
$$

or since $\chi = \chi _ { \{ | u - v | < t \} }$ and $\nabla ( T _ { t } ( u - v ) ) = \chi _ { \{ | u - v | < t \} } \nabla ( u - v )$

$$
\int _ { \Omega } \nabla _ { A } u \cdot \nabla T _ { t } ( u - v ) \mathrm { d } x + \int _ { \Omega } b | u | ^ { r - 2 } u T _ { t } ( u - v ) \mathrm { d } x \leq \int _ { \Omega } f T _ { t } ( u - v ) \mathrm { d } x , \forall t \in ( 0 , \infty ) \setminus \mathcal { O } .
$$

For $t \in \mathcal { O }$ , we know that there exists a sequence $\{ t _ { k } \}$ of numbers in $( 0 , \infty ) \backslash { \mathcal { O } }$ such that $t _ { k } \to t$ due to $| \mathcal { O } | = 0$ . Therefore, we have

$$
\int _ { \Omega } \nabla _ { A } u \cdot \nabla T _ { t _ { k } } ( u - v ) \mathrm { d } x + \int _ { \Omega } b | u | ^ { r - 2 } u T _ { t _ { k } } ( u - v ) \mathrm { d } x \leq \int _ { \Omega } f T _ { t _ { k } } ( u - v ) \mathrm { d } x .
$$

Since $\nabla ( u - v ) = 0$ a.e. in $\{ | u - v | = t \}$ , the left-hand side of (41) can be written as

$$
\int _ { \Omega } \nabla _ { A } u \cdot \nabla T _ { t _ { k } } ( u - v ) \mathrm { d } x = \int _ { \Omega \backslash \{ | u - v | = t \} } \chi _ { \{ | u - v | < t _ { k } \} } \nabla _ { A } u \cdot \nabla ( u - v ) \mathrm { d } x .
$$

The sequence $\chi \{ | u - v | < t _ { k } \}$ converges to $\chi \{ | u - v | < t \}$ a.e. in $\Omega \setminus \left\{ | u - v | = t \right\}$ and therefore converges weakly\* in $L ^ { \infty } ( \Omega \backslash \{ | u -$ $v | = t \}$ ).Weobtain

$$
\begin{array} { l } { \displaystyle \operatorname* { l i m } _ { k \to \infty } \int _ { \Omega } \nabla _ { A } u \cdot \nabla T _ { t _ { k } } ( u - v ) \mathrm { d } x = \int _ { \Omega \backslash \{ | u - v | = t \} } \chi _ { \{ | u - v | < t \} } \nabla _ { A } u \cdot \nabla ( u - v ) \mathrm { d } x } \\ { = \displaystyle \int _ { \Omega } \chi _ { \{ | u - v | < t \} } \nabla _ { A } u \cdot \nabla ( u - v ) \mathrm { d } x } \\ { = \displaystyle \int _ { \Omega } \nabla _ { A } u \cdot \nabla T _ { t } ( u - v ) \mathrm { d } x . } \end{array}
$$

For the right-hand side of (41),we have

$$
\bigg | \int _ { \Omega } f T _ { t _ { k } } ( u - v ) \mathrm { d } x - \int _ { \Omega } f T _ { t } ( u - v ) \mathrm { d } x \bigg | \leq | t _ { k } - t | \cdot \| f \| _ { 1 } \to 0 \mathrm { ~ a s ~ } k \to \infty .
$$

Similarly, we have

$$
\bigg | \int _ { \Omega } | u | ^ { r - 2 } u T _ { t _ { k } } ( u - v ) \mathrm { d } x - \int _ { \Omega } | u | ^ { r - 2 } u T _ { t } ( u - v ) \mathrm { d } x \bigg | \le | t _ { k } - t | \cdot \| | u | ^ { r - 1 } \| _ { 1 } \to 0 \mathrm { ~ a s ~ } k \to \infty .
$$

It follows from (41)-(44) that we have the inequality

$$
\int _ { \Omega } \nabla _ { A } u \cdot \nabla T _ { t } ( u - v ) \mathrm { d } x + \int _ { \Omega } b | u | ^ { r - 2 } u T _ { t } ( u - v ) \mathrm { d } x \leq \int _ { \Omega } f T _ { t } ( u - v ) \mathrm { d } x , \forall t \in ( 0 , \infty ) .
$$

Hence, $u$ is an entropy solution of the obstacle problem associated with $( f , \psi , g )$ . The dependence of the entropy solution on the data $f \in L ^ { 1 } ( \Omega )$ is guaranteed by Proposition 4. ■

# 4Declarations

# 4.1Availability of data and material

Not applicable.

# 4.2 Competing interests

The author declares that he has no competing interests.

# 4.3 Funding

This researchwaspartiallysupportedbytheFundamentalResearchFunds fortheCentral Universities (No.:1O8lX10096022).

4.4Authors'contributions

This paper was completed by $\scriptstyle { \mathrm { J Z } }$ independently.

# 4.5Acknowledgements

Not applicable.

# References

[]AAl Appl.,182 (1) (2003),53-79.   
[2]A.lvibsstp (1998),381-391.   
[3]P.Bénilan,L.Boccardo,T. Gallouet,R. Gariepy,M.Pierre,J.L. Vazquez, An $L ^ { 1 }$ theory of existence and uniqueness of nonlinear elliptic equations, Ann. Scuola Norm. Sup.Pisa Cl. Sci.,22(2) (1995),240-273.   
[4]LBocadsiti (2003),521-530.   
[5]L. Boccardo,Some nonlinear Dirichlet problems in $L ^ { 1 }$ involving lower order terms in divergence form,Pitman Res.Notes Math.Ser.350 Longman, Harlow (1996),43-57.   
[6]L.Boccardo,G.R.Cirmi,Existence and uniqueness of solution of unilateral problems with $L ^ { 1 }$ data,J. Convex Anal.,6 (1) (1999),195-206.   
[7]L.BoccadoGoceLOrsina,Eisteeoflutiosfoeocoecivelpticpobsiovingriratioflar arXiv:1206.3694,2012.   
8]Lo Modena,46-suppl.(1998),51-81.   
[9]S.Challal,A.Lyaghfouri, J.F.Rodrigues,On the $A$ -obstacle problem and the Hausdorff measure of its free boundary,Ann. Mat.Pura Appl.,191 (1) (2012),113-165.   
[10]G.CenoiearelpticuatioiwrdedgeeatCrciityatematicltes,9(-)()4.   
[1]GCrocelangetsfeowdriipticatoigeeateecityXiv:.   
[2]FDl 79-103.   
[3]D.   
[14]D.Giacaiiateciidtit,)   
[5]JLyl 93 (1965),97-107.   
[16] Z.Li,W.Gao,Existence results to anonlinear $p ( x )$ -Laplace equation with degenerate coercivity and zero-order term: renormalized and entropy solutions, Appl. Anal.,95(2)(2016),373-389.   
[17]A.PoetesoUe 915-936.   
[8]GSt 1 (1965),189-258.   
[19]E.Zeid from the German by the author and F.Leo.