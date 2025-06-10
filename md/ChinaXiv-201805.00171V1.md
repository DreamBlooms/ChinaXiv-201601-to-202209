# Lyapunov-type inequalities for $\psi$ -Laplacian equations

Jun Zheng1, Xu Guo²

1 School of Mathematics,Southwest Jiaotong University Chengdu,Sichuan,P.R.ofChina 611756 2 School of Information Science & Technology,Southwest Jiaotong University Chengdu611756,Sichuan,China

# Abstract

In this work,we present several Lyapunov-type inequalities for a class of $\psi$ -Laplacian equations of the form

$$
( \psi ( u ^ { \prime } ( x ) ) ) ^ { \prime } + r ( x ) f ( u ( x ) ) = 0 ,
$$

with Dirichlet boundary conditions,where $\psi$ and $f$ satisfies certain structural conditions with general nonlinearities.We do not require anysub-multiplicativepropertyof $\psi$ ， and any convexity of $\textstyle { \frac { 1 } { \psi ( t ) } }$ u $\psi ( t ) t$ in the establishment ofLyapunov-type inequalities.The obtained inequalities can be seen as extensions and complements of the existing results in the literature.

Key words:Lyapunov inequality, $\psi$ -Laplacian, nonlinear equation.

# 1 Introduction

Consider the Hill's equation

$$
\begin{array} { l } { { u ^ { \prime \prime } ( x ) + r ( x ) u ( x ) = 0 , \quad x \in ( a , b ) , } } \\ { { u ( a ) = u ( b ) = 0 , } } \end{array}
$$

where $r$ is a continuous and nonnegative function defined in $[ a , b ]$ with $a , b \in \mathbb { R }$ and $a < b$ . If there exists a nontrivial solution $u$ of (1), then the inequality

$$
\int _ { a } ^ { b } r ( x ) \mathrm { d } x \geq { \frac { 4 } { b - a } } ,
$$

holds.This result is dueoriginally toLyapunov[11],andisknownas“Lyapunov inequality".TheLyapunov inequalityand many of its generalizations haveproved tobeuseful tols inoscilltiontheorydisconjugacy,eigenvalue problems,nd numerousotherapplications forthetheoriesofdiferentialanddifferenceequations,andalsoin timescales.Inthelastfew years independent works appeared generalizing Lyapunovs inequality for the $p$ -Laplacian, by using Holder, Jensen or CauchySchwarz inequalities.Athorough literature reviewofLyapunov-type inequalities andtheirapplications can be found in the surveyarticles by Brown and Hinton[3],Cheng[6]and Tiryaki[18].Some other related topicscanbe found in theresent articles [1,2,4,5,7-9,13-15,17,19] and the references therein.

We presentsomeresultsrelateddirectly toourproblem.In2Oo5,DeNapoliandPinascoconsideredLyapunov-typeinequalies for certain nonlinear differential equations ( $\overset { \cdot } { \psi }$ -Laplacian equations） generalizing the $p$ -Laplacian. The main result in [12] is:

Theorem A Suppose that $\psi : \mathbb { R } \to \mathbb { R }$ is an odd nondecreasing function such that $\psi ( t ) = t \psi ( t )$ is a convex function.Moreover, suppose that there exists a constant $k > 0$ such that $\psi ( 2 t ) \leq \bar { k } \psi ( t )$ for any $t \geq 0$ . If $r ( x )$ be a positive integrable function,and the following problem

$$
\begin{array} { r l } & { ( \psi ( u ^ { \prime } ( x ) ) ) ^ { \prime } + r ( x ) \psi ( u ( x ) ) = 0 \mathrm { ~ i n ~ } ( a , b ) , } \\ & { u ( a ) = u ( b ) = 0 . } \end{array}
$$

admitsanontrivial solution, then

$$
2 { \left( \frac { k } { 2 } \right) } ^ { [ 1 - \log _ { 2 } ( b - a ) ] } \leq \int _ { a } ^ { b } r ( x ) \mathrm { d } x ,
$$

where $[ v ]$ is the largest integer less than or equal to $v$

In 2011,Sachez and Vergara extended (3) to equations with a general nonlinear form,considering (see [16])

$$
\begin{array} { r l } & { ( \psi ( u ^ { \prime } ( x ) ) ) ^ { \prime } + \lambda r ( x ) f ( u ( x ) ) = 0 \mathrm { ~ i n ~ } ( a , b ) , } \\ & { u ( a ) = u ( b ) = 0 , } \end{array}
$$

where $\lambda > 0$ is a constant.Under the following assumptions:

$\left( B _ { 1 } \right)$ $f \in C ( \mathbb { R } )$ is odd and satisfies $t f ( t ) > 0$ for $t \neq 0$   
$( B _ { 2 } ) r : [ a , b ]  ( 0 , + \infty )$ is a continuous function.   
$( B _ { 3 } ) \psi$ is $[ 0 , + \infty )$ , and $\textstyle { \frac { 1 } { \psi ( t ) } }$ is convex in $t > 0$   
the authors established a Lyapunov-type inequality for (4),having the following result:   
Theorem B Suppose that conditions $( { \bf \bar { \cal B } } _ { 1 } ) - { \bf \bar { ( } } { \cal B } _ { 3 } )$ are satisfied. If $u$ is a nontrivial solution of problem (4),satisfying $u ( x ) \neq 0$ （204号 for $x \in ( a , b )$ , then the following inequality holds:

$$
{ \frac { 2 } { \psi { \big ( } { \frac { b - a } { 2 } } { \big ) } } } \leq \lambda \int _ { a } ^ { b } { \frac { f ( u ( x ) ) } { \psi ( u ( x ) ) } } \mathrm { d } x ,
$$

when the integral exists.

The convexity of $t \psi ( t )$ (or $\textstyle { \frac { 1 } { \psi ( t ) } }$ andsub-multiplicative propertyof $\psi$ ) playsanessentialoleintheestablishmentofaLyaunov type inequalityin[12](or[16]).Our motivation for this paper comes fromthe papersof[12]and[16].The main noveltyof this paperis toestablishLyapunov-type inequalities foralarge classof nonlinearequations governedby(5)(or(4))without any convexity assumption on $t \psi ( t )$ u $\scriptstyle { \frac { 1 } { \psi ( t ) } }$ , and without anysub-multiplicative assumptionon $\psi$ . The function $\psi$ in this paper permits much more nonlinearities than thatin[12,16] (seee.g.Remark2 inSection1and examples in Section 4).Moreover, under the assumption $( H _ { 4 } )$ , we do not require any odd-even properties of $f$ ,and require less sign conditions of $f$ than that in [16].

Therest of this paper is organized as folows.Section 2 presents theconsidered problemand the main results on Lyapunovtype inequalities.Someremarks onthestructural conditionsarealsoprovidedin thissection.Detailed profs ofLyapunov-type inequalities are given in Section 3.Additional examples satisfying our structuralconditions are provided in Section 4.

# 2Problem setting and main results

In this paper, we establish Lyapunov-type inequalities for the following equation

$$
\begin{array} { r l } & { ( \psi ( u ^ { \prime } ( x ) ) ) ^ { \prime } + r ( x ) f ( u ( x ) ) = 0 \mathrm { ~ i n ~ } ( a , b ) , } \\ & { u ( a ) = u ( b ) = 0 , } \end{array}
$$

where $\psi$ and $f$ satisfy the following structural conditions having general nonlinearities:

$( H _ { 1 } ) \ \psi , f \in C ( ( - \infty , \infty ) ) \cap C ^ { 1 } ( ( 0 , \infty ) )$ with $f \not \equiv 0$ on $( - \infty , \infty )$ $( H _ { 2 } ) \psi$ is odd on $( - \infty , \infty )$ ：

$( H _ { 3 } )$ $f ( t ) \geq 0$ for all $t \in [ 0 , \infty )$ $( H _ { 4 } )$ There exists $k _ { 0 } > 0$ such that $| f ( t ) | \leq k _ { 0 } \psi ( | t | )$ for all $t \in ( - \infty , \infty )$

We make further assumption on $\psi$ or $f$

$( H _ { \psi } )$ There exists constants $\delta _ { 0 } , \delta _ { 1 } \geq 0$ such that

$$
\delta _ { 0 } \psi ( t ) \leq t \psi ^ { \prime } ( t ) \leq \delta _ { 1 } \psi ( t ) , \ \forall t > 0 .
$$

$( H _ { f } )$ There exists constants $\theta _ { 0 } , \theta _ { 1 } \geq 0$ such that

$$
\theta _ { 0 } f ( t ) \leq t f ^ { \prime } ( t ) \leq \theta _ { 1 } f ( t ) , \ \forall t > 0 .
$$

Throughout this paper, we always assume that $r \in L ^ { 1 } ( a , b )$ with $r \not \equiv 0$ on $( a , b )$ , and conditions $\left( H _ { 1 } \right) - \left( H _ { 4 } \right)$ are satisfied. Moreover, we always assume that (5) has a non-trivial solution $u$ in the sense that $u \in C ^ { 1 } ( a , b ) \cap C ( [ a , b ] )$ ， $\psi ( u ^ { \prime } ( x ) )$ is absolutely continuous in $x$ ,and $u$ satisfies the equation in (5) almost everywhere in $( a , b )$

Thefirst mainresult is as follows,whichcanbeseenasacomplementof the workof[12]and[16]in the setingoffunctions satisfying $\left( H _ { \psi } \right)$ or $\left( H _ { f } \right)$ ：

Theorem1(i） If $\psi$ satisfies $\left( H _ { \psi } \right)$ ,then $\begin{array} { r } { \int _ { a } ^ { b } | r ( x ) | d x \geq \frac { 2 } { k _ { 0 } } \cdot \frac { 1 + \delta _ { 0 } } { 1 + \delta _ { 1 } } \cdot \operatorname* { m i n } \big \{ \big ( \frac { 2 } { b - a } \big ) ^ { \delta _ { 0 } } , \big ( \frac { 2 } { b - a } \big ) ^ { \delta _ { 1 } } \big \} . } \end{array}$ (i) If $f$ stisfes $( H _ { f } )$ , then $\begin{array} { r } { \int _ { a } ^ { b } | r ( x ) | d x \ge \frac { 2 } { k _ { 0 } } \cdot \frac { 1 + \theta _ { 0 } } { 1 + \theta _ { 1 } } \cdot \operatorname* { m i n } \left\{ \left( \frac { 2 } { b - a } \right) ^ { \theta _ { 0 } } , \left( \frac { 2 } { b - a } \right) ^ { \theta _ { 1 } } \right\} } \end{array}$

We present some corollaries of Theorem 1.

Corollay2(i) 1f $\psi ( t ) = f ( t ) = | t | ^ { p - 2 } t ( p > 1 )$ then $\begin{array} { r } { \int _ { a } ^ { b } | r ( x ) | d x \geq \frac { 2 ^ { p } } { ( b - a ) ^ { p - 1 } } } \end{array}$ ，whichis oeof ttshtined (i (imi) independently in $\begin{array} { r l } & { H \psi ( t ) = f ( t ) = | t | ^ { a - 1 } t \log _ { c } ( b | t | + d ) , \ a , b > 0 , c , d > 1 , t h e n \int _ { a } ^ { b } | r ( x ) | d x \geq \frac { 2 ( 1 + a ) \ln d } { 1 + ( 1 + a ) \ln d } \cdot \operatorname* { m i n } \left\{ \left( \frac { 2 } { b - a } \right) ^ { a } , ( \frac { 2 } { b - a } ) ^ { b - 1 } , \right. } \\ & { H \psi ( t ) = f ( t ) = \frac { | t | ^ { a - 1 } t } { \log _ { c } ( b | t | + d ) } , \ b > 0 , c , d > 1 , a > \frac { 1 } { \ln d } , t h e n \int _ { a } ^ { b } | r ( x ) | d x \geq \frac { 2 ( 1 + a ) \ln d } { ( 1 + a ) \ln d - 1 } \cdot \operatorname* { m i n } \left\{ \left( \frac { 2 } { b - a } \right) ^ { a } , \left( \frac { 2 } { b - a } \right) ^ { b - 1 } , \right. } \end{array}$ $I ^ { g } , I 3 I$ ) 2a)a-向}.

If we make further assumption that $\psi ( t ) t$ (or $f ( t ) t )$ is convex on $[ 0 + \infty )$ , we get some results stronger than Theorem 1, which canbe seen as extensions of[12].

Theorem3 Assume further that $\psi ( t ) t$ is convex in $t \in [ 0 , + \infty )$

(i) If $\psi$ satisfes $\left( H _ { \psi } \right)$ ,then $\begin{array} { r } { \int _ { a } ^ { b } | r ( x ) | d x \geq \frac { 2 } { k _ { 0 } } \cdot \operatorname* { m i n } \big \{ \left( \frac { 2 } { b - a } \right) ^ { \delta _ { 0 } } , \left( \frac { 2 } { b - a } \right) ^ { \delta _ { 1 } } \big \} . } \end{array}$ (ii)IffsaisfesH）,eni{)

Before the proof of main results, we give some remarks on the structural conditions.

Remark 1(i） We point out $\left( H _ { \psi } \right)$ (or $( H _ { f } ) _ { . }$ ) is a slight version of Lieberman's in [10], where regularity theory was consid- $\begin{array} { r } { 0 < \delta _ { 0 } \le \frac { t \psi ^ { \prime } ( t ) } { \psi ( t ) } \le \delta _ { 1 } } \end{array}$ ，： It should be noticed hat $\textstyle { \frac { t \psi ^ { \prime } ( t ) } { \psi ( t ) } }$ is always requedteposiivein],ileispp $\psi ^ { \prime } ( t )$ (or $f ^ { \prime } ( t ) )$ 证 $\left( H _ { \psi } \right)$ (or H)c $\psi ( t ) = \left\{ \begin{array} { l } { \displaystyle \frac { 7 } { 8 } \cdot ( 2 t ) ^ { \frac { 3 } { 7 } } , 0 < t < \frac { 1 } { 2 } , } \\ { ( t - 1 ) ^ { 3 } + 1 , \frac { 1 } { 2 } \leq t \leq \frac { 3 } { 2 } , } \\ { \displaystyle \frac { 3 } { 4 } t , t > \frac { 3 } { 2 } , } \end{array} \right.$ we have $\psi \in C ^ { 1 } ( ( 0 , + \infty ) )$ and $\begin{array} { r } { 0 \le \frac { t \psi ^ { \prime } ( t ) } { \psi ( t ) } \le \ 3 } \end{array}$ for all $t > 0$ Thelower boudedesscanbeachieved when $\psi ^ { \prime } ( 1 ) = 3 ( t - 1 ) ^ { 2 } \big | _ { t = 1 } = 0$ ： (ii) $B y ~ ( H _ { 1 } ) - ( H _ { 4 } ) , \bar { \psi ( 0 ) } = f ( 0 ) = ($ and $\psi ( t ) \geq 0$ for any $t \geq 0$ Furthermore,if $\psi$ (or $f ,$ satisfies $\left( H _ { \psi } \right)$ (or $( H _ { f } ) _ { , }$ ),then $\psi ^ { \prime } ( t ) \geq 0$ (or $f ^ { \prime } ( t ) \geq 0 ,$ ,which guarantees the increasing monotonicity of $\psi ( t )$ (or $f ( t ) )$ in $t \geq 0$ ：

Remark 2 In this remark,we give two examples of the function $\psi$ (or $f$ ）showing that our assumptions on $\psi$ (or $f )$ are much weaker than that in [12,16] (see Theorem A and $B$ ) in a certain sense. More examples of functions satisfying $\left( H _ { \psi } \right)$ or $\left( H _ { f } \right)$ are provided in Section 4.

(i) Let $\textstyle \psi _ { 0 } ( t ) = t + { \frac { 1 } { t } }$ with $t \in [ \frac { 6 } { 5 } , \sqrt { 3 } ]$ .Due to continuities of $\cdot _ { \psi _ { 0 } }$ and $\psi _ { 0 } ^ { \prime }$ , there exists $\delta _ { 0 } ^ { \prime } , \delta _ { 1 } ^ { \prime } > 0$ such that $\begin{array} { r } { \delta _ { 0 } ^ { \prime } \le \frac { t \psi _ { 0 } ^ { \prime } ( t ) } { \psi _ { 0 } ( t ) } \le \delta _ { 1 } ^ { \prime } f o r } \end{array}$ all $t \in [ \frac { 6 } { 5 } , \sqrt { 3 } ]$ $\begin{array} { r l r } & { } & { \Vert . L e t p = \frac { 1 1 } { 6 1 } , a = \left( \frac { 6 } { 5 } + \frac { 5 } { 6 } \right) \left( \frac { 6 } { 5 } \right) ^ { - p } a n d q = \frac { 1 } { 2 } , b = \left( \sqrt { 3 } + \frac { 1 } { \sqrt { 3 } } \right) ( \sqrt { 3 } ) ^ { - q } . L e t \psi ( t ) = \left\{ \begin{array} { l l } { a t ^ { p } , 0 < t < \frac { 6 } { 5 } } \\ { \psi _ { 0 } ( t ) , \frac { 6 } { 5 } \leq t \leq \sqrt { 3 } } \\ { b t ^ { q } , t > \sqrt { 3 } } \end{array} \right. } \end{array}$ （20 By direct computations,one may verify that $\begin{array} { r } { \left( \frac { 1 } { \psi ( t ) } \right) ^ { \prime \prime } = \left( \frac { 1 } { \psi _ { 0 } ( t ) } \right) ^ { \prime \prime } = \frac { - 2 } { ( t + 1 ) ^ { 3 } } < 0 } \end{array}$ = (t+1)s <Ofort ∈ (g,3).Thus is not convex on $[ 0 , + \infty )$ ，i.e, $\psi$ does not satisfy the condition $( H _ { 3 } )$ in [16]. However, $\psi$ defined as above satisfies $\left( H _ { \psi } \right)$ with $\delta _ { 0 } =$ （20 $\operatorname* { m i n } \{ \delta _ { 0 } ^ { \prime } , p , q \}$ and $\delta _ { 1 } = \operatorname* { m a x } \{ \delta _ { 1 } ^ { \prime } , \overset { . } { p } , q \}$ in this paper.   
(ii) Let $\psi _ { 0 } ( t ) = \sin t$ with $t \in ( 0 , \frac { \pi } { 2 } )$ . Then $\begin{array} { r } { ( \psi _ { 0 } ( t ) t ) ^ { \prime \prime } = - t \sin t + 2 \cos t  - \frac { \pi } { 2 } < 0 } \end{array}$ as $\begin{array} { r } { t  ( \frac { \pi } { 2 } ) ^ { - } } \end{array}$ . Thus there exists $[ t _ { 0 } , t _ { 1 } ] \subset ( 0 , \frac { \pi } { 2 } )$ such that $\left( \psi _ { 0 } ( t ) t \right) ^ { \prime \prime } < 0$ for all $t \in [ t _ { 0 } , t _ { 1 } ]$ Let $\psi ( t ) = \left\{ { \begin{array} { l l } { a t ^ { p } , 0 < t < t _ { 0 } } \\ { \psi _ { 0 } ( t ) , t _ { 0 } \leq t \leq t _ { 1 } } \\ { b t ^ { q } , t > t _ { 1 } } \end{array} } \right.$ ， where $p = t _ { 0 } \cot t _ { 0 } >$ （2 $0 , a = t _ { 0 } ^ { - p } \sin t _ { 0 } > 0$ and $q = t _ { 1 } \cot t _ { 1 } > 0 , b = t _ { 1 } ^ { - q } \sin t _ { 1 } > 0$ . Note that here exists $\delta _ { 0 } ^ { \prime } , \delta _ { 1 } ^ { \prime } > 0$ such that $\begin{array} { r } { \delta _ { 0 } ^ { \prime } \leq \frac { t \psi _ { 0 } ^ { \prime } ( t ) } { \psi _ { 0 } ( t ) } \leq } \end{array}$ （204 $\delta _ { 1 } ^ { \prime }$ for all $t \in [ t _ { 0 } , t _ { 1 } ]$ . One may verify that $\psi$ satisfies $\left( H _ { \psi } \right)$ with $\delta _ { 0 } = \operatorname* { m i n } \{ \delta _ { 0 } ^ { \prime } , p , q \}$ and $\delta _ { 1 } = \operatorname* { m a x } \{ \delta _ { 1 } ^ { \prime } , p , q \}$ However, $\left( \psi ( t ) t \right) ^ { \prime \prime } < 0$ for $t \in [ t _ { 0 } , t _ { 1 } ]$ . That is to say such a $\psi$ does not satisfy the convexity condition in $I I 2 J$ while it still satisfies $\left( H _ { \psi } \right)$ in this paper.

# 3Proof of main results

We present first some auxiliary results needed in the main proof.Let $\begin{array} { r } { \Psi ( t ) = \int _ { 0 } ^ { t } \psi ( s ) \mathrm { d } s } \end{array}$ for $t \geq 0$

Lemma 4 Assume that $\psi$ satisfies $( H _ { 1 } ) – ( H _ { 4 } )$ and $\left( H _ { \psi } \right)$ . The following results hold true.

(i） $\psi ( s t ) \le \operatorname* { m a x } \{ s ^ { \delta _ { 0 } } , s ^ { \delta _ { 1 } } \} \psi ( t )$ ， $\forall s , t \geq 0 .$   
(ii) $\Psi$ is $\dot { C } ^ { 2 } -$ contiuous on $( 0 , + \infty )$ ，and convex on $[ 0 , + \infty )$ =  
(iii) $\begin{array} { r } { \frac { t \psi ( t ) } { 1 + \delta _ { 1 } } \leq \Psi ( t ) \leq \frac { t \psi ( t ) } { 1 + \delta _ { 0 } } } \end{array}$ ， $\forall t \geq 0$ ），

Proof. Let $\begin{array} { r } { h _ { 0 } ( t ) = \frac { \psi ( t ) } { t ^ { \delta _ { 0 } } } , h _ { 1 } ( t ) = \frac { \psi ( t ) } { t ^ { \delta _ { 1 } } } } \end{array}$ for $t > 0$ By $( H _ { \psi } )$ , it follows

$$
h _ { 0 } ^ { \prime } ( t ) = \frac { \psi ^ { \prime } ( t ) t ^ { \delta _ { 0 } } - \psi ( t ) \delta _ { 0 } t ^ { \delta _ { 0 } - 1 } } { t ^ { 2 \delta _ { 0 } } } = \frac { t \psi ^ { \prime } ( t ) - \psi ( t ) \delta _ { 0 } } { t ^ { \delta _ { 0 } + 1 } } \geq 0 ,
$$

which implies that $h _ { 0 } ( t )$ is increasing in $t > 0$ .Therefore $h _ { 0 } ( s t ) \leq h _ { 0 } ( t )$ for $0 \leq s \leq 1$ . It follows that

$$
\psi ( s t ) \le s ^ { \delta _ { 0 } } \psi ( t ) , \forall t > 0 , 0 \le s \le 1 .
$$

Similarly, one may prove that $h _ { 1 } ( t )$ is decreasing in $t > 0$ . Then $h _ { 1 } ( s t ) \leq h _ { 1 } ( t )$ for $s \geq 1$ . It follows that

$$
\psi ( s t ) \leq s ^ { \delta _ { 1 } } \psi ( t ) , \forall t > 0 , s \geq 1 .
$$

By (6) and(7),we have

$$
\psi ( s t ) \leq \operatorname* { m a x } \{ s ^ { \delta _ { 0 } } , s ^ { \delta _ { 1 } } \} \psi ( t ) , \forall t > 0 , s \geq 0 ,
$$

which and the continuity of $\psi$ in $t = 0$ yields (i).

(ii) is obvious since $\Psi ^ { \prime \prime } ( t ) = \psi ^ { \prime } ( t ) \geq 0$ for $t > 0$ (see Remark 1) and $\Psi ( t )$ is continuous in $t = 0$

To conclude (ii), let $\Psi _ { 0 } ( t ) = ( 1 + \delta _ { 0 } ) \Psi ( t ) - t \psi ( t )$ and $\Psi _ { 1 } ( t ) = ( 1 + \delta _ { 1 } ) \Psi ( t ) - t \psi ( t )$ for $t \geq 0$ . It is easy to see that $\Psi _ { 0 } ^ { \prime } ( t ) \leq 0$ and $\Psi _ { 1 } ^ { \prime } ( t ) \geq 0$ for $t > 0$ .Then $\Psi _ { 0 } ( t ) \leq \Psi _ { 0 } ( 0 ) = 0$ and $\Psi _ { 1 } ( t ) \geq \Psi _ { 1 } ( 0 ) = 0$ , which and continuities of $\Psi _ { 0 } , \Psi _ { 1 }$ yield (ii). □

Remark 3 Let $\begin{array} { r } { F ( t ) = \int _ { 0 } ^ { t } f ( s ) d s } \end{array}$ for $t \geq 0$ ，Then the function $f$ satisfying $( H _ { 1 } ) – ( H _ { 4 } )$ and $\left( H _ { f } \right)$ and the function $F$ have similar properties as above.

Proof of Theorem 1. Without loss of generality, assume that $| u ( c ) | = \operatorname* { m a x } _ { x \in [ a , b ] } | u ( x ) | > 0$ with $c \in ( a , b )$ . Note that $| u ( c ) | =$ $\begin{array} { r } { \frac { 1 } { 2 } \bigg ( \big | \int _ { a } ^ { c } u ^ { \prime } ( x ) \mathrm { d } x \big | + \big | \int _ { c } ^ { b } u ^ { \prime } ( x ) \mathrm { d } x \big | \bigg ) \leq \frac { 1 } { 2 } \int _ { a } ^ { b } | u ^ { \prime } ( x ) | \mathrm { d } x . } \end{array}$

Firstly, we prove Theorem 1 (i) under the assumption that $\psi$ satisfies the structural condition $\left( H _ { \psi } \right)$ . Indeed,by the monotonicity of $\psi$ , and Lemma 4 (i) and (ii), we get

$$
\begin{array} { r l } { \psi ( | | \alpha ( c ) | ) | \mathrm { n } ( c ) | \le \frac { 1 } { 2 } \cdot \psi \left( \frac { 1 } { 2 } \int _ { a } ^ { b } | u ^ { \prime } ( x ) | \mathrm { d } x \right) \cdot \int _ { a } ^ { b } | u ^ { \prime } ( x ) | \mathrm { d } x } \\ { = } & { \frac { b - a } { 2 } \cdot \psi \left( \frac { b - a } { 2 } \frac { 1 } { b } - a \int _ { a } ^ { b } | u ^ { \prime } ( x ) | \mathrm { d } x \right) \cdot \frac { 1 } { b - a } \int _ { a } ^ { b } | u ^ { \prime } ( x ) | \mathrm { d } x } \\ { \le \operatorname* { m a x } \left\{ \left( \frac { b - a } { 2 } \right) ^ { 1 + \delta } , \ \left( \frac { b - a } { 2 } \right) ^ { 1 + \delta } \right\} \cdot \psi \left( \frac { 1 } { b - a } \int _ { a } ^ { b } | u ^ { \prime } ( x ) | \mathrm { d } x \right) \cdot \frac { 1 } { b - a } \int _ { a } ^ { b } | u ^ { \prime } ( x ) | \mathrm { d } x } \\ { \le \operatorname* { m a x } \left\{ \left( \frac { b - a } { 2 } \right) ^ { 1 + \delta } , \ \left( \frac { b - a } { 2 } \right) ^ { 1 + \delta } \right\} \cdot ( 1 + \delta _ { 1 } ) \cdot \Psi \left( \frac { 1 } { b - a } \int _ { a } ^ { b } | u ^ { \prime } ( x ) | \mathrm { d } x \right) } \\ { \le \operatorname* { m a x } \left\{ \left( \frac { b - a } { 2 } \right) ^ { 1 + \delta } , \ \left( \frac { b - a } { 2 } \right) ^ { 1 + \delta } \right\} \cdot ( 1 + \delta _ { 1 } ) \cdot \frac { 1 } { b - a } \cdot \int _ { a } ^ { \delta } \Psi ( | u ^ { \prime } ( x ) | ) \mathrm { d } x } \\ { = } & { ( 1 + \delta _ { 1 } ) \cdot \operatorname* { m a x } \left\{ \frac { ( b - a ) ^ { \delta } } { 2 ^ { 1 + \delta } } , \frac { ( b - a ) ^ { \delta } } { \sqrt { 2 + \delta } } \right\} \cdot ( 1 + \delta _ { 1 } ) \cdot \frac { 1 } { b - a } \cdot \int _ { a } ^ { \delta } \Psi ( | u ^ { \prime } ( x ) | ) \mathrm { d } x } \\ { = } & { ( 1 + \delta _ { 1 } ) \cdot \operatorname* { m a x } \left\{ \frac { ( b - a ) ^ { \delta } } { 2 ^ { 1 + \delta } } , \frac { ( b - a ) ^ { \delta } } { \sqrt { 2 + \delta } } \right\} \cdot \int _ { a } ^ { b } \Psi ( | u ^ { \prime } ( x ) | ) \mathrm { d } x } \end{array}
$$

where in the last inequality we used the convexity of $\Psi$ (see Lemma 4 (i)).

Multiplying (5) by $u$ , integrating over $( a , b )$ , and using Lemma 4 (ii), $( H _ { 2 } ) – ( H _ { 4 } )$ , and (8), we get

$$
\begin{array} { r l } { \int _ { \infty } ^ { \infty } \Psi ( | x | ^ { \prime } | ) \mathrm { d } x \leq } & { \displaystyle \frac { 1 } { 1 + \delta _ { n } } \int _ { x } ^ { \infty } \Psi ( | x | ^ { \prime } | ) | x | ^ { \prime } \mathrm { d } x } \\ & { = \displaystyle \frac { 1 } { 1 + \delta _ { n } } \int _ { x } ^ { \infty } \Psi ( x ^ { \prime } ) | x ^ { \prime } \mathrm { d } x } \\ & { = - \displaystyle \frac { 1 } { 1 + \delta _ { n } } \int _ { x } ^ { \infty } \tau ( x ^ { \prime } ) \tilde { f } ( x ) \mathrm { d } x \mathrm { d } x } \\ & { \leq \frac { 1 } { 1 + \delta _ { n } } \frac { \operatorname* { m a x } _ { \alpha } ( x ^ { \prime } ) \left( \tilde { f } ( x ^ { \prime } ) \theta \right) \mathrm { d } x } { 1 + \delta _ { n } - \log ( x ^ { \prime } ) \left( x ^ { \prime } \theta \right) } \int _ { x } ^ { \infty } | x ( x ) | \mathrm { d } x } \\ & { \leq \frac { \kappa _ { 0 } } { 1 + \delta _ { n } - \log ( x ^ { \prime } ) \left( x ^ { \prime } \theta \right) \left( x ^ { \prime } \right) \left( x ^ { \prime } \right) \left( x ^ { \prime } \right) \mathrm { d } x } } \\ & { \leq \frac { \kappa _ { 0 } } { 1 + \delta _ { n } - \log ( x ^ { \prime } ) \left( x ^ { \prime } \right) \left( x ^ { \prime } \right) \left( x ^ { \prime } \right) \left( x ^ { \prime } \right) \left( x ^ { \prime } \right) \mathrm { d } x } } \\ & { \leq \frac { \kappa _ { 0 } } { 1 + \delta _ { n } - \log ( x ^ { \prime } ) \left( x ^ { \prime } \right) \left( x ^ { \prime } \right) \left( x ^ { \prime } \right) \left( x ^ { \prime } \right) \left( x ^ { \prime } \right) \mathrm { d } x } } \\ & { \leq \frac { \kappa _ { 0 } } { 1 + \delta _ { n } } \frac { \kappa _ { 0 } } { 1 + \delta _ { n } - \log ( x ^ { \prime } ) } \left\{ \frac { \left( \tilde { f } _ { x } - \mathrm { a } \right) ^ { \alpha } } { 2 } \nu _ { x } \left( \mathrm { a } \right) x ^ { \prime } \right\} \int _ { x } ^ { \infty } \Psi ( | x | ^ { \prime } ) \mathrm { d } x \cdot \int _ { x } ^ { \infty } | x | \mathrm { d } x \mathrm { d } x . } \end{array}
$$

Note that $\begin{array} { r } { \int _ { a } ^ { b } \Psi ( | u ^ { \prime } | ) \mathrm { d } x > 0 } \end{array}$ ,otherwise, $\begin{array} { r } { \int _ { a } ^ { b } \Psi ( | u ^ { \prime } | ) \mathrm { d } x = 0 } \end{array}$ .By (8) and Lemma 4 (i), we have,

$$
0 \leq \psi ( t ) | u ( c ) | = \psi \bigg ( \frac { t } { u ( c ) } u ( c ) \bigg ) | u ( c ) | \leq \operatorname* { m a x } \bigg \{ \bigg ( \frac { t } { u ( c ) } \bigg ) ^ { \delta _ { 0 } } , \bigg ( \frac { t } { u ( c ) } \bigg ) ^ { \delta _ { 1 } } \bigg \} \psi ( u ( c ) ) | u ( c ) | \leq 0 , \ : \ : \forall t \geq 0 ,
$$

which implies $\psi \equiv 0$ for all $t \in [ 0 , + \infty )$ . Then by the odd property of $\psi$ , we have $\psi \equiv 0$ for all $t \in ( - \infty , + \infty )$ . Due to $( H _ { 4 } )$ $f \equiv 0$ for all $t \in ( - \infty , + \infty )$ , which is a contradiction with the assumption $( H _ { 1 } )$ ：

Then we get

$$
\int _ { a } ^ { b } | r ( x ) | \mathrm { d } x \geq \frac { 1 + \delta _ { 0 } } { k _ { 0 } ( 1 + \delta _ { 1 } ) } \cdot \operatorname* { m i n } \left\{ \frac { 2 ^ { 1 + \delta _ { 0 } } } { ( b - a ) ^ { \delta _ { 0 } } } , \frac { 2 ^ { 1 + \delta _ { 1 } } } { ( b - a ) ^ { \delta _ { 1 } } } \right\} .
$$

Theorem 1 (i) has been proven.

Now for Theorem 1 (ii), we proceed in a similar way as above. Indeed, if $f$ satisfies the structural condition $\left( H _ { f } \right)$ , proceeding as in (8), we get

$$
f ( | u _ { c } | ) | u _ { c } | \leq ( 1 + \theta _ { 1 } ) \cdot \operatorname* { m a x } \left\{ \frac { ( b - a ) ^ { \theta _ { 0 } } } { 2 ^ { 1 + \theta _ { 0 } } } , \frac { ( b - a ) ^ { \theta _ { 1 } } } { 2 ^ { 1 + \theta _ { 1 } } } \right\} \cdot \int _ { a } ^ { b } F ( | u ^ { \prime } ( x ) | ) \mathrm { d } x .
$$

Multiplying (5) by $u$ , integrating over $( a , b )$ , and using Lemma 4 (iii), $( H _ { 2 } ) – ( H _ { 4 } )$ , and (9), we get

$$
\begin{array} { r l } { \int _ { a } ^ { b } F [ v ^ { \varepsilon } ] \mathrm { d } z \leq } & { \frac { 1 } { 1 + \theta _ { 0 } } \int _ { a } ^ { b } \hat { v } [ | v ^ { \varepsilon } | ] \mathrm { d } z = \operatorname { I } } \\ & { \leq \frac { \hat { \nu } _ { 0 } } { 1 + \theta _ { 0 } } \int _ { a } ^ { b } \hat { v } [ | v ^ { \varepsilon } | ] \mathrm { d } z \operatorname { I } } \\ & { = \frac { \hat { \nu } _ { 0 } } { 1 + \theta _ { 0 } } \int _ { a } ^ { b } \hat { v } ( | u ^ { \varepsilon } | ) \mathrm { d } z \operatorname { I } } \\ & { = \frac { \hat { \nu } _ { 0 } } { 1 + \theta _ { 0 } } \int _ { a } ^ { b } \hat { v } ( | u ^ { \varepsilon } | ) \mathrm { d } z \operatorname { I } } \\ & { = \frac { \hat { \nu } _ { 0 } } { 1 + \theta _ { 0 } } \int _ { a } ^ { b } \hat { v } ( z ) \mathrm { d } f ( | u | \mathrm { d } z ) } \\ & { \leq \frac { \hat { \nu } _ { 0 } } { 1 + \theta _ { 0 } - \varepsilon ( \mathrm { a } z ) + 1 } \langle f ( 3 ) u \rangle \int _ { a } ^ { b } | r ( z ) | \mathrm { d } z } \\ & { \leq \frac { \hat { \nu } _ { 0 } } { 1 + \theta _ { 0 } } \frac { \operatorname { I n o t } ( b / \varepsilon ) ) \operatorname { I n o t } ( f ) } { 1 + \theta _ { 0 } } \int _ { a } ^ { b } | r ( z ) | \mathrm { d } z } \\ & { \leq \frac { \hat { \nu } _ { 0 } } { 1 + \theta _ { 0 } } \frac { \hat { \nu } _ { 0 } ( | u ^ { \varepsilon } | ) \operatorname { I n o t } ( f ) } { 1 + \theta _ { 0 } } \int _ { a } ^ { b } | r ( z ) | \mathrm { d } z } \\ &  \leq \frac { \hat { \nu } _ { 0 } ( 1 + \theta _ { 0 } ) } { 1 - \theta _ { 0 } } \cdot \operatorname { I n o t } \left\{ \frac { \hat { \nu } _ { 0 } - \varepsilon ( | u ^ { \varepsilon } | ) \cdot ( \hat { \nu } _ { 0 } - \varepsilon ( \hat { \nu } _ { 0 } + \hat { \nu } _ { 0 } ^ { \varepsilon } ) } { 2 ^ { \varepsilon } ( 1 ) \theta _ { 0 } } \right\} \cdot \int _ { a } ^ { b } F ( | u ^ { \varepsilon } | ) \mathrm { d } z \cdot \int _ { a } ^ { b } | r ( z ) | \mathrm { d } z \cdot \int _ { a } ^ { b } | r ( z ) | \mathrm { d } z \cdot \int _ { a } ^ { b } | r ( z ) | \mathrm { d } z \cdot \int _ { a } ^ { b } | r ( z ) | \mathrm { d } z \cdot \int _ { a }  \end{array}
$$

Note that $\textstyle \int _ { a } ^ { b } F ( | u ^ { \prime } | ) \mathrm { d } x > 0$ , otherwise, we can argue as in the proof of (i) to conclude $f ( t ) \equiv 0$ for any $t \in ( - \infty , + \infty )$ Finally,(1O) implies the desired result. ■

Proof of Theorem 3.The proof of Theorem 3 is aslight modifications of the proof of Theorem 1.Indeed,let $\Phi ( t ) = \psi ( t ) t$ （204号 for $t \geq 0$ ,and let $c , u ( c )$ be defined as in the proof of Theorem 1. If $\psi$ satisfies the structural condition $\left( H _ { \psi } \right)$ , arguing as in (8), we get

$$
\begin{array} { r l } & { \psi ( | u ( c ) | ) | u ( c ) | \le \operatorname* { m a x } \left\{ \left( \displaystyle \frac { b - a } { 2 } \right) ^ { 1 + \delta _ { 0 } } , \left( \displaystyle \frac { b - a } { 2 } \right) ^ { 1 + \delta _ { 1 } } \right\} \cdot \psi \left( \displaystyle \frac { 1 } { b - a } \int _ { a } ^ { b } | u ^ { \prime } | { \mathrm { d } } x \right) \cdot \displaystyle \frac { 1 } { b - a } \int _ { a } ^ { b } | u ^ { \prime } | { \mathrm { d } } x } \\ & { \quad \quad \quad = \operatorname* { m a x } \left\{ \left( \displaystyle \frac { b - a } { 2 } \right) ^ { 1 + \delta _ { 0 } } , \left( \displaystyle \frac { b - a } { 2 } \right) ^ { 1 + \delta _ { 1 } } \right\} \cdot \Phi \left( \displaystyle \frac { 1 } { b - a } \int _ { a } ^ { b } | u ^ { \prime } | { \mathrm { d } } x \right) } \\ & { \quad \quad \le \operatorname* { m a x } \left\{ \left( \displaystyle \frac { b - a } { 2 } \right) ^ { 1 + \delta _ { 0 } } , \left( \displaystyle \frac { b - a } { 2 } \right) ^ { 1 + \delta _ { 1 } } \right\} \cdot \displaystyle \frac { 1 } { b - a } \int _ { a } ^ { b } \Phi ( | u ^ { \prime } | ) { \mathrm { d } } x , } \end{array}
$$

where in the last inequality we used the convexity of $\Phi$ = Concerning with (5) and (11), we have

$$
\int _ { a } ^ { b } \Phi ( | u ^ { \prime } | ) \mathrm { d } x = \int _ { a } ^ { b } \psi ( | u ^ { \prime } | ) | u ^ { \prime } | \mathrm { d } x
$$

$$
\begin{array} { r l } & { \quad = \displaystyle \int _ { a } ^ { b } \psi ( u ^ { \prime } ) u ^ { \prime } \mathrm { d } x } \\ & { \quad = \displaystyle \int _ { a } ^ { b } r ( x ) f ( u ) u \mathrm { d } x } \\ & { \quad \le k _ { 0 } \psi ( | u ( c ) | ) | u ( c ) | \displaystyle \int _ { a } ^ { b } | r ( x ) | \mathrm { d } x } \\ & { \quad \le \displaystyle \frac { k _ { 0 } } { 2 } \operatorname* { m a x } \left\{ \left( \frac { b - a } { 2 } \right) ^ { \delta _ { 0 } } , \left( \frac { b - a } { 2 } \right) ^ { \delta _ { 1 } } \right\} \cdot \displaystyle \int _ { a } ^ { b } \Phi ( | u ^ { \prime } | ) \mathrm { d } x \cdot \displaystyle \int _ { a } ^ { b } | r ( x ) | \mathrm { d } x , } \end{array}
$$

which yields the desired result in Theorem 3(i).The desired result in Theorem 3 (ii) can be proven in asimilar way.

Proof of Corollary 2. For (i), it should be noticed that $\delta _ { 0 } = \theta _ { 0 } = \delta _ { 1 } = \theta _ { 1 } = p - 1$ in $\left( H _ { \psi } \right)$ and $( H _ { f } ) )$

For (ii), it should be noticed that for $t \geq 0$

$$
\psi ( t ) = f ( t ) = t ^ { a } \log _ { c } ( b t + d ) , a , b > 0 , c , d > 1 .
$$

Then we have

$$
a \leq { \frac { t \psi ^ { \prime } ( t ) } { \psi ( t ) } } = a + { \frac { b t } { ( b t + d ) \ln c \cdot \log _ { c } ( b t + d ) } } \leq a + { \frac { b t } { ( b t + d ) \ln c \cdot \log _ { c } d } } = a + { \frac { 1 } { \ln d } } , \forall t > 0 .
$$

Thus $\begin{array} { r } { \delta _ { 0 } = \theta _ { 0 } = a > 0 , \delta _ { 1 } = \theta _ { 1 } = a + \frac { 1 } { \ln d } > 0 } \end{array}$ in $\left( H _ { \psi } \right)$ and $\left( H _ { f } \right)$

For(ii), it should be noticed that for $t \geq 0$

$$
\psi ( t ) = f ( t ) = { \frac { t ^ { a } } { \log _ { c } ( b t + d ) } } , b > 0 , c , d > 1 , a > { \frac { 1 } { \ln d } } .
$$

Then we have

$$
a - { \frac { 1 } { \ln d } } \leq { \frac { t \psi ^ { \prime } ( t ) } { \psi ( t ) } } = a - { \frac { b t } { ( b t + d ) \ln ( b t + d ) } } \leq a , \forall t > 0 .
$$

Thus $\delta _ { 0 } = \theta _ { 0 } = a - \textstyle { \frac { 1 } { \ln d } } > 0 , \delta _ { 1 } = \theta _ { 1 } = a > 0$ m $\left( H _ { \psi } \right)$ and $\left( H _ { f } \right)$

# 4Examples

In this part, we give additional examples of $\psi ( t )$ (or $f ( t ) )$ satisfying $( H _ { \psi } )$ (or $( H _ { f } ) )$ ,and find $\delta _ { 0 } , \delta _ { 1 }$ (or $\theta _ { 0 } , \theta _ { 1 } )$ . For simplicity, we only restrict $\psi ( t )$ (or $f ( t ) )$ to the case $t \in [ 0 , + \infty )$ , since one may construct functions by odd or even extensions to $t \in ( - \infty , + \infty )$ ：

# Example 1

$$
\psi ( t ) = f ( t ) = \ln ( 1 + a t ) + b t , \forall a > 0 , b > 0 .
$$

For (12),we have

$$
\frac { t \psi ^ { \prime } ( t ) } { \psi ( t ) } = \frac { a t } { 1 + a t } \frac { 1 } { \ln ( 1 + a t ) + b t } + \frac { b t } { \ln ( 1 + a t ) + b t } \le \frac { a } { b } + 1 , \forall t > 0 .
$$

Note that $\ln ( 1 + a t ) \leq a t$ for all $t > 0$ ,it follows

$$
\frac { b } { a + b } \leq \frac { t \psi ^ { \prime } ( t ) } { \psi ( t ) } \leq \frac { a } { b } + 1 , \forall t > 0 .
$$

# Example 2

$$
\psi ( t ) = f ( t ) = ( 1 + t ) \ln ( 1 + t ) - t .
$$

For(13),frstly,notetht $\psi ^ { \prime } ( t ) = \ln ( 1 + t ) \geq 0$ for any $t \geq 0$ .Thus $\psi ( t ) \geq \psi ( 0 ) = 0$ By direct computations,we have

$$
{ \frac { t \psi ^ { \prime } ( t ) } { \psi ( t ) } } = { \frac { t \ln ( 1 + t ) } { ( 1 + t ) \ln ( 1 + t ) - t } } = { \frac { t } { ( 1 + t ) - { \frac { t } { \ln ( 1 + t ) } } } } , \forall t > 0 .
$$

Since $\ln ( 1 + t ) \leq t$ for all $t > 0 ;$ it follows

$$
\frac { t } { ( 1 + t ) - \frac { t } { \ln ( 1 + t ) } } \geq \frac { t } { ( 1 + t ) - \frac { t } { t } } = 1 , \forall t > 0 .
$$

In the following,we prove that for any $t > 0$ ，thereholds

$$
\frac { t \ln ( 1 + t ) } { ( 1 + t ) \ln ( 1 + t ) - t } \leq 2 .
$$

Indeed,let $h _ { 1 } ( t ) = t \ln ( 1 + t ) - 2 ( ( 1 + t ) \ln ( 1 + t ) - t ) = 2 t - t \ln ( 1 + t ) - 2 \ln ( 1 + t )$ Then $\begin{array} { r } { h _ { 1 } ^ { \prime } ( t ) = 1 - \ln ( 1 + t ) - \frac { 1 } { 1 + t } } \end{array}$ Let $h _ { 2 } ( t ) = ( 1 + t ) - ( 1 + t ) \ln ( 1 + t ) - 1 = t - ( 1 + t ) \ln ( 1 + t ) .$ It is easy to check that $h _ { 2 } ^ { \prime } ( t ) = - \ln ( 1 + t ) < 0$ for any $t > 0$ .Thus $h _ { 2 } ( t ) \leq h _ { 2 } ( 0 ) = 0$ ，which leads to $h _ { 1 } ^ { \prime } ( t ) \leq 0$ for any $t > 0$ Therefore $h _ { 1 } ( t ) \leq h _ { 1 } ( 0 ) = 0$ As a consequence, (14) holds true for any $t > 0$ Finally $\delta _ { 0 } = \theta _ { 0 } = 1 , \delta _ { 1 } \mathbf { \bar { \phi } } = \theta _ { 1 } = 2$ in $\left( H _ { \psi } \right)$ and $\left( H _ { f } \right)$ ： □

# Example 3

$$
\psi ( t ) = f ( t ) = { \left\{ \begin{array} { l l } { a t ^ { p } , 0 \leq t < t _ { 0 } , } \\ { b t ^ { q } + c , t \geq t _ { 0 } , } \end{array} \right. }
$$

where $a , b , c , p , q , t _ { 0 } > 0$ such that $a t _ { 0 } ^ { p } = b t _ { 0 } ^ { q } + c$ and $a p t _ { 0 } ^ { p - 1 } = b q t _ { 0 } ^ { q - 1 }$

For (15), we have $\psi = f \in C ^ { 1 } ( ( 0 , + \infty ) )$ and

$$
\operatorname* { m i n } \{ p , q \} \leq \frac { t \psi ^ { \prime } ( t ) } { \psi ( t ) } \leq \operatorname* { m a x } \{ p , q \} .
$$

Thus $\delta _ { 0 } = \theta _ { 0 } = \operatorname* { m i n } \{ p , q \} > 0 , \delta _ { 1 } = \theta _ { 1 } = \operatorname* { m a x } \{ p , q \} > 0$ in $\left( H _ { \psi } \right)$ and $\left( H _ { f } \right)$ =

Example4Thefollowingexampleis interestingsince $\psi$ or $f$ iswith a variable exponent:

$$
\psi ( t ) = f ( t ) = { \left\{ \begin{array} { l l } { a t ^ { p } , 0 \leq t < t _ { 0 } , } \\ { b t ^ { g ( t ) - 1 } , t \geq t _ { 0 } , } \end{array} \right. }
$$

where $t _ { 0 } > 1 , a , b , p > 0$ ,and the function $g \in C ^ { 1 } ( [ t _ { 0 } , + \infty )$ satisfy

$$
\left\{ \begin{array} { l l } { c \leq g ^ { \prime } ( t ) t \ln t + g ( t ) - 1 \leq d , \forall t \geq t _ { 0 } , } \\ { p = g ^ { \prime } ( t _ { 0 } ) t _ { 0 } \ln t _ { 0 } + g ( t _ { 0 } ) - 1 , } \\ { a = b t _ { 0 } ^ { g ( t _ { 0 } ) - 1 - p } , } \end{array} \right.
$$

with some constants d ≥c > 0. Note that t(btg(t)-1) $\begin{array} { r } { \frac { t ( b t ^ { g ( t ) - 1 } ) ^ { \prime } } { b t ^ { g ( t ) - 1 } } = t g ^ { \prime } ( t ) \ln t + g ( t ) - 1 . } \end{array}$ By direct computations, one may verify that $\psi = f \in C ^ { 1 } ( ( 0 , + \infty ) )$ and satisfy $\left( H _ { \psi } \right)$ and $( H _ { f } )$ with $\mathfrak { j } _ { 0 } = \theta _ { 0 } = \operatorname* { m i n } \{ p , c \} = c , \delta _ { 1 } = \theta _ { 1 } = \operatorname* { m a x } \{ p , d \} = d .$ （2

Example 5 In [16], the authors provided two examples of $\psi ( t )$ ,i.e, (i) $\psi ( t ) = | t | ^ { a } \varphi _ { p } ( t )$ with $a > 1 - p$ and (i) $\psi ( t ) = ( \ln ( | t | + b ) ) ^ { b } \varphi _ { p } ( t )$ with $a \geq e , b > 0 ,$ （2号

showing that $\textstyle { \frac { 1 } { \psi ( t ) } }$ is convex in $t > 0$ ，where $\varphi _ { p } ( t ) = | t | ^ { p - 2 } t \left( p > 1 \right)$ . We point out that $\psi ( t )$ given by $( i )$ or (ii) also satisfies the structural condition $( H _ { \psi } )$ . Indeed, for $( i )$ ,i is easy to see hat $\begin{array} { r } { \frac { t \psi ^ { \prime } ( t ) } { \psi ( t ) } = a + p - 1 > 0 . } \end{array}$ $t > 0$ Thus $\delta _ { 0 } = \delta _ { 1 } = a + p - 1$ i $t > 0$ .Then $\begin{array} { r } { \delta _ { 0 } = p , \delta _ { 1 } = p + \frac { b } { a \ln a } } \end{array}$ 讥 $( H _ { \psi } ,$ ） □

# References

[1]R.P.AgaralandA.zeklerLyaputyeieaiforoddersubdsupealfnarferetialquatiosDacStes Applications,24(1):211-220,2015.   
[2]PAleddarypuealitfoddedequaioAplthLet,4):.   
[3]R.C.BrodLyaidos:ssscal AcademicPublishers,Dordrecht,The Netherlands,2000.   
[4]Dkaill 108,2013.   
[5]D.CakmakOLyaoteiealitfoassofasliearsElectroicualofQaitivefiferetitio 2014(9):1-10,2014.   
[6]S.Cheng.Lyapunov inequalities for diferential and diference equations.Fasc.Math.,23(23):25-41,1991.   
[7]O.Doslyak.HlfrtialEuats:athd,u.Asted:sevier,rtd,.   
[8]G.GuseodacalanLapuoealifoseealoateomputatApl,5(6)3.   
[9]C.Le,C.Yeh,C.Hong,andR.PAgarwal.Lyapunovand Wirtingerinequalities.Appl.Math.Let,17(7):847-853,2004.   
[10]GLebsslitl Differential Equations,16(2-3):311-361,1991.   
[11]A.LpublbitiUs4 Fac.Sci.Toulouse,9(1907)203-474,Translationofthe originalpaperpublished in Comm.Soc.Math.Kharkow,1892.   
[2]PLi)   
[13] J.P.Pinasco.Lower bounds for eigenvalues of the one-dimensional $p$ -laplacian. Abstr. Appl. Anal.,2004(2):147-153,2004.   
[14] J.P.Pinasco. Comparison of eigenvalues for the $p$ -laplacian with integral inequalities.Appl.Math. Comput.,182(2):1399-1404,2006.   
[15]JPPlb Dordrecht-London,2013.   
[16] J. Sanchez and V. Vergara. A Lyapunov-type inequality for a $\psi$ -laplacian operator. Nonlinear Analysis,74(18):7071-707,2011.   
[17]X.TangdZapuaidablitroJfetlEato):.   
[18]A.Tiryaki. Recent development of Lyapunov-type inequalities.Adv.Dyn. Syst.Appl.,5(2):231-248,2010.   
[19]A.Tiryaki,.Ualnd.kak.Lantyealitiesforlnrte.JthAnal.Appl():49.