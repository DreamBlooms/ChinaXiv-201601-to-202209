# 1 HOLDER CONTINUITY OF SOLUTIONS TO THE $G$ -LAPLACE EQUATION INVOLVING MEASURES

JUN ZHENG，YAN ZHANG

School of Mathematics,Southwest Jiaotong University, Chengdu, Sichuan 611756,China

ABSTRACT.We establish regularity of solutions to the $G$ -Laplace equation $-$ div $\begin{array} { r } { \left( \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u \right) = \mu } \end{array}$ ，where $\mu$ is a nonnegative Radon measure satisfying $\mu ( B _ { r } ( x _ { 0 } ) ) ~ \leq ~ C r ^ { m }$ for any ball $B _ { r } ( x _ { 0 } ) \subset \joinrel \subset \Omega$ with $r ~ \leq ~ 1$ and $m \ >$ （20 $n - 1 - \delta \geq 0$ ．The function $g ( t )$ is supposed to be nonnegative and $C ^ { 1 }$ continuous in $[ 0 , + \infty )$ ，satisfying $g ( 0 ) = 0$ ，and for some positive constants $\delta$ （20 and $g _ { 0 }$ ， $\begin{array} { r } { \delta \le \frac { t g ^ { \prime } ( t ) } { g ( t ) } \le g _ { 0 } , \forall t > 0 } \end{array}$ ,that generalisthestructuralcditiof Ladyzhenskaya-Ural'tseva for an elliptic operator.

# 31.Introduction.

4

Let $\Omega$ be an open bounded domain of $\mathbb { R } ^ { n } ( n \geq 2 )$ ，and $\mu$ a nonnegative Radon measure in $\Omega$ with $\mu ( B _ { r } ( x _ { 0 } ) ) \leq C r ^ { m }$ for some constant $C > 0$ whenever $B _ { r } ( x _ { 0 } ) \subset \joinrel \subset$ $\Omega$ . We consider the equation

$$
- \Delta _ { G } u = - \mathrm { d i v } \left( \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u \right) = \mu \mathrm { i n } \mathcal { D } ^ { \prime } ( \Omega ) ,
$$

where $\begin{array} { r } { G ( t ) = \int _ { 0 } ^ { t } g ( s ) \mathrm { d } s } \end{array}$ ， $g ( t )$ is a nonnegative $C ^ { 1 }$ function in $[ 0 , + \infty )$ ， satisfying $g ( 0 ) = 0$ and the following structural condition

$$
0 < \delta \leq \frac { t g ^ { \prime } ( t ) } { g ( t ) } \leq g _ { 0 } , \quad \forall t > 0 , \ \delta , g _ { 0 } \ \mathrm { a r e \ p o s i t i v e \ c o n s t a n t s } .
$$

The structural conditions on $g$ was introduced by Lieberman in 1991,which is a natural generalization of the natural conditions of Ladyzhenskaya and Ural'tseva for elliptic equations (see [1O]). The conditions of $g$ imply that the operator $\Delta _ { G }$ （204号 includes not only the $p -$ Laplace operator $\Delta _ { p }$ where $g ( t ) = t ^ { p - 1 }$ and $\delta = g _ { 0 } = p - 1$ ， but also the case of a variable exponent $p = p ( t ) > 0$

$$
- \Delta _ { G } u = - \mathrm { d i v } \ ( | \nabla u | ^ { p ( | \nabla u | ) - 2 } \nabla u ) ,
$$

5 corresponding to set $g ( t ) = t ^ { p ( t ) - 1 }$ , for which (2) holds if $\delta \leq t ( \ln t ) p ^ { \prime } ( t ) + p ( t ) - 1$ （204   
6 （20 $\le g _ { 0 }$ for all $t > 0$ . Another typical example of $g$ is $g ( t ) = t ^ { p } \log ( a t + b )$ with $p , a , b > 0$ （204号   
7 where in this case $\delta = p$ and $g _ { 0 } = p + 1$ . Many other examples can be found in   
8 [2, 3, 6] etc.

Under assumption (2), $G$ is an increasing $C ^ { 2 }$ convex function，which is an $N$ function satisfying the so called $\Delta _ { 2 }$ -condition.Thus our class of operators will be considered in the setting of Orlicz spaces. We recall the definitions of Orlicz and Orlicz-Sobolev spaces together with their respective norms (see [1])

$$
\begin{array} { l } { \displaystyle L ^ { G } ( \Omega ) = \{ u \in L ^ { 1 } ( \Omega ) ; \int _ { \Omega } G ( | u ( x ) | ) \mathrm { d } x < + \infty \} , } \\ { \displaystyle \| u \| _ { L ^ { G } ( \Omega ) } = \operatorname* { i n f } \bigg \{ k > 0 ; \int _ { \Omega } G \left( \frac { | u ( x ) | } { k } \right) \mathrm { d } x \leq 1 \bigg \} , } \\ { \displaystyle W ^ { 1 , G } ( \Omega ) = \{ u \in L ^ { G } ( \Omega ) ; \nabla u \in L ^ { G } ( \Omega ) \} , } \\ { \displaystyle \| u \| _ { W ^ { 1 , G } ( \Omega ) } = \| u \| _ { L ^ { G } ( \Omega ) } + \| \nabla u \| _ { L ^ { G } ( \Omega ) } . } \end{array}
$$

1 Under the assumption (2), $W ^ { 1 , G } ( \Omega )$ is a reflexive and separable Banach space (see   
²[1]).

We shall call a solution of (1) any function $u \in W _ { l o c } ^ { 1 , G } ( \Omega )$ that satisfies

$$
\int _ { \Omega } \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u \cdot \varphi \mathrm { d } x = \int _ { \Omega } \varphi \mathrm { d } \mu \quad \forall \varphi \in \mathcal { D } ( \Omega ) .
$$

If $\mu \equiv 0$ in a domain $D \subset \Omega$ ，we say that $u$ is $G -$ harmonic in $D$

We now introduce the regularity of the related elliptic equations involving measures.In 1994,Kilpeläinen considered the situation of the $p$ -Laplace operator and proved that if $\mu$ satisfies $\mu ( B _ { r } ) \leq C r ^ { n - p + \alpha ( p - 1 ) }$ for some positive constants $C$ and $\alpha \in ( 0 , 1 ]$ , then any solution of the $p$ -Laplace equation

$$
- \Delta _ { p } \boldsymbol { u } = - \mathrm { d i v } \left( \lvert \boldsymbol { \nabla } \boldsymbol { u } \rvert ^ { p - 2 } \boldsymbol { \nabla } \boldsymbol { u } \right) = \mu ,
$$

is $C _ { l c o } ^ { 0 , \beta } -$ continuous for each $\beta \in \mathsf { \Gamma } ( 0 , \alpha )$ (see [7]). This result was improved by Kilpelainen and Zhong in 2Oo2, showing that if each solution of (3） is in fact Holder continuous with the same exponent $\alpha$ as the one in the assumption $\mu ( B _ { r } ) \leq$ $C r ^ { n - p + \alpha ( p - 1 ) }$ (see[8]). In 2010, the $p -$ Laplace problem (3) was extended by Lyaghfouri to the case with variable exponents,i.e., considering

$$
- \mathrm { d i v } \left( | \nabla u | ^ { p ( x ) - 2 } \nabla u \right) = \mu .
$$

4Under certain assumptions on the function $p ( x )$ and the assumption $\mu ( B _ { r } ) \ \leq$   
5 $C r ^ { n - p ( x ) + \alpha ( p ( x ) - 1 ) }$ for some positive constants $C$ and $\alpha \in ( 0 , 1 ]$ , the author proved   
6that any boundeded solution of (4) is $C _ { l o c } ^ { 0 , \alpha } -$ continuous with the same exponent $\alpha$   
7(see [11]).   
8 When focusing on the problem governed by $G -$ Laplacian,if $\mu ( B _ { r } ( x _ { 0 } ) ) \leq C r ^ { m }$ （2   
9 with $m \in [ n - 1 , n )$ ，Challal and Lyaghfouri proved that any solution of (1） is   
10 （204 $C _ { l o c } ^ { 0 , \alpha } -$ continous with $\begin{array} { r } { \alpha = \frac { m - n + 1 + \delta } { 1 + g _ { 0 } } } \end{array}$ (see[]).Particularly,if $m = n - 1$ ， then any   
11 solution is $C _ { l o c } ^ { 0 , \alpha }$ -continuous for any $\alpha \in ( 0 , \frac { \delta } { g _ { 0 } } )$ (see Theorem 3.3 in [3]).In 2011,   
12 these regularities were improved by Challal and Lyaghfouri in [5], showing that   
13 anylocalboundedsolutionof(is $C _ { l o c } ^ { 0 , \alpha } -$ continous for any $\begin{array} { r } { \alpha \in \ ( 0 , \frac { m - n + 1 + \delta } { g _ { 0 } } ) } \end{array}$ （204号   
14 provided that $m > n - 1 - \delta$ . Note that under the assumption of non-decreasing   
15 monotonicity on $\textstyle { \frac { g ( t ) } { t } }$ ， Zheng, Feng and Zhang obtained local $C ^ { 1 , \alpha } -$ continuity of   
16 solutions for $m \ > \ n$ and local Holder continuity with small exponents for some   
17 （20 $m < n$ in 2015 (see [14]).   
18 In this paper, we continue the work of Challal,Lyaghfouri and Zheng et al. by   
19 improving the regularity of solutions of the equation (1). Particularly, we can prove   
20 the $C _ { l o c } ^ { 0 , \alpha } -$ continuity ofsolutions forany $\alpha \in ( 0 , 1 )$ 证 $m = n - 1$ . More precisely, for   
21 any $m > n - 1 - \delta$ and without any monotonicity assumption on $\textstyle { \frac { g ( t ) } { t } }$ , we have the   
22 following result.   
1 Theorem 1.1.Assume that $\mu$ satisfies (1) with $m > n - 1 - \delta \geq 0$ . Then we have   
2 f $m > n$ ,then $u \in C _ { l o c } ^ { 1 , \alpha } ( \Omega )$ for any $\textstyle \alpha \in ( 0 , \operatorname* { m i n } \{ { \frac { \sigma } { 1 + g _ { 0 } } } , { \frac { m - n } { 2 ( 1 + g _ { 0 } ) } } \} )$ ，where $\sigma$ i5   
3 the same as in Lamma 2.4.   
4 (i） If $m \in [ n - 1 , n )$ ，then $u \in C _ { l o c } ^ { 0 , \alpha } ( \Omega )$ for any $\alpha \in ( 0 , 1 )$ ：   
5 (i） If $n - 1 - \delta < m < n - 1$ ,then $u \in C _ { l o c } ^ { 0 , \alpha } ( \Omega )$ for any $\begin{array} { r } { \alpha \in ( 0 , \frac { m - n + 1 + \delta } { \delta } ) } \end{array}$   
6 Remark 1. In [7],the author proved for the $p -$ Laplacin problem that $u \in C _ { l o c } ^ { 0 , \alpha } ( \Omega )$   
7 for any $\alpha \in ( 0 , 1 )$ provided $m = n - 1$ . In this paper we not only improve the results   
8of [3, 5] and [14],but also extend the problem in [7] to general equations which   
9governed by a large class of degenerate and singular elliptic operators.

# 2. Preliminary.

In this section,we state some auxiliary results which will be used throughout this paper. We begin with some properties of the function $G$

；Lemma 2.1 ([13,Lemma 2.1, Remark 2.1]). Function $G$ has the following properties:

18 (G1） $G$ is convex and $C ^ { 2 }$   
19 (G2) （204号 $\begin{array} { r } { \frac { t g ( t ) } { 1 + g _ { 0 } } \leq G ( t ) \leq t g ( t ) } \end{array}$ for all $t \geq 0$ ，  
20 $\mathrm { ( G _ { 3 } ) }$ ） $\begin{array} { r l } & { \operatorname* { m i n } \\\\\{ s ^ { \delta + 1 } , s ^ { g _ { 0 } + 1 } \} \frac { G ( t ) } { 1 + g _ { 0 } } \leq G ( s t ) \leq ( 1 + g _ { 0 } ) \operatorname* { m a x } \{ s ^ { \delta + 1 } , s ^ { g _ { 0 } + 1 } \} G ( t ) . } \\ & { G ( a + b ) \leq 2 ^ { g _ { 0 } } ( 1 + g _ { 0 } ) ( G ( a ) + G ( b ) ) \quad f o r \ a l l \ a , b > 0 . } \end{array}$   
21 （204号 $\mathrm { ( G _ { 4 } ) }$ ）

For much more properties of $G$ and problems governed by the operator $\Delta _ { G }$ please see [2, 3, 4, 5, 6, 13,14, 15,16] etc.

The following lemmas are some properties of $G -$ harmonic functions.Throughout this paper,without special states,by $B _ { R }$ and $B _ { r }$ we denote the balls contained in $\Omega$ with the same center. Moreover, $B _ { r } \subset \joinrel \subset B _ { R } \subset \joinrel \subset \Omega$ ：

Lemma 2.2 ([13, Theorem 2.3]). Assume $u \in W ^ { 1 , G } ( \Omega )$ .Let $h$ be a weak solution of

$$
\Delta _ { G } h = 0 ~ i n ~ B _ { R } , ~ h - u \in W _ { 0 } ^ { 1 , G } ( B _ { R } ) ,
$$

then

$$
\begin{array} { r l } { \displaystyle \int _ { B _ { R } } \bigl ( G ( | \nabla u | ) - G ( | \nabla h | ) \bigr ) d x \ge C \bigg ( \displaystyle \int _ { A _ { 2 } } G ( | \nabla u - \nabla h | ) d x } & { } \\ { \displaystyle + \int _ { A _ { 1 } } \frac { g ( | \nabla u | ) } { | \nabla u | } | \nabla u - \nabla h | ^ { 2 } d x \bigg ) , } \end{array}
$$

27where $A _ { 1 } = \{ x \in B _ { R } ; | \nabla u - \nabla h | \le 2 | \nabla u | \} , \ A _ { 2 } = \{ x \in B _ { R } ; | \nabla u - \nabla h | > 2 | \nabla u | \}$ and  
28 $C = C ( \delta , g _ { 0 } ) > 0$ ：

Lemma 2.3 ([13, Lemma 2.7]). Let $h \in W ^ { 1 , G } ( \Omega )$ be a weak solution of $\Delta _ { G } h = 0$ Then $h \in C ^ { 1 , \alpha } ( \Omega )$ . Moreover, there exists $C = C ( n , \delta , g _ { 0 } ) > 0$ such that for every ball $B _ { r } \subset \joinrel \subset \Omega$ and every $\lambda \in ( 0 , n )$ , there exists $C = C ( \lambda , n , \delta , g _ { 0 } , \| h \| _ { L ^ { \infty } ( B _ { \frac { 2 } { 3 } r } ( x _ { 0 } ) ) } ) > 0$ （20 such that

$$
\int _ { B _ { r } } G ( | \nabla h | ) d x \leq C r ^ { \lambda } .
$$

Let $\begin{array} { r } { ( u ) _ { r } = \frac { 1 } { | B _ { r } | } \int _ { B _ { r } } u \mathrm { d } x } \end{array}$ be the average value of $u$ on the ball $B _ { r }$ ， we have

Lemma 2.4 (Comparison with $G$ -harmonic functions [14, Lemma 3.1]).Assume （20 $u \in W ^ { 1 , G } ( B _ { R } )$ Let $h \in W ^ { 1 , G } ( B _ { R } )$ be a weak solution of $\Delta _ { G } h = 0$ in $B _ { R }$ . Then there exists $\sigma \in ( 0 , 1 )$ and $C = C ( n , \delta , g _ { 0 } ) > 0$ such that for each $0 < r \le R$ ，there holds

$$
\int _ { B _ { r } } G ( | \nabla u - ( \nabla u ) _ { r } | ) d x \leq C \left( \frac { r } { R } \right) ^ { n + \sigma } \int _ { B _ { R } } G ( | \nabla u - ( \nabla u ) _ { R } | ) d x + C \int _ { B _ { R } } G ( | \nabla u - \nabla h | ) d x .
$$

Lemma 2.5 ([9,Lemma 2.7]). Let $\phi ( s )$ be a non-negative and non-decreasing func tion.Suppose that

$$
\phi ( r ) \leq C _ { 1 } \left( \frac { r } { R } \right) ^ { \alpha } \phi ( R ) + C _ { 1 } R ^ { \beta } ,
$$

for all $r ~ \leq ~ R \leq R _ { 0 }$ ，with $\alpha , \beta$ and $C _ { 1 }$ positive constants. Then， for any $\tau <$ $\operatorname* { m i n } \{ \alpha , \beta \}$ ，there exists a constant $C _ { 2 } = C _ { 2 } ( C _ { 1 } , \alpha , \beta , \tau )$ such that for all $r \leq R \leq R _ { 0 }$ （204号 we have

$$
\phi ( r ) \leq C _ { 2 } r ^ { \tau } .
$$

# 13.Proof of Theorem 1.1.

2 Lemma 3.1. Assume $u \in W ^ { 1 , G } ( \Omega )$ .Let $B _ { R } \subset \joinrel \subset \Omega$ and $h \in W ^ { 1 , G } ( B _ { R } )$ be a weak   
3solution of

$$
\Delta _ { G } h = 0 \quad \mathrm { ~ \it ~ i n ~ B _ { R } , } \quad h - u \in W _ { 0 } ^ { 1 , G } ( B _ { R } ) .
$$

Then for any $\lambda \in ( 0 , n )$ ， there exists $C = C ( \lambda , n , \delta , g _ { 0 } , \| u \| _ { L ^ { \infty } ( B _ { 2 R / 3 } ) } ) > 0$ such that

$$
\int _ { B _ { R } } G ( | \nabla u - \nabla h | ) d x \leq C R ^ { m } + C R ^ { \frac { m + \lambda } { 2 } } ,
$$

4where $\lambda$ is the same as in Lemma 2.3.

Proof. Firstly, convexity of $G$ gives

$$
\begin{array} { r l } { \displaystyle \int _ { B _ { R } } ( G ( | \nabla u | ) - G ( | \nabla h | ) ) \mathrm { d } x \le \int _ { B _ { R } } \frac { g ( | \nabla u | ) } { | \nabla u | } \nabla u ( \nabla u - \nabla h ) \mathrm { d } x } & { } \\ { \displaystyle \qquad = \int _ { B _ { R } } ( u - h ) \mathrm { d } \mu } & { } \\ { \displaystyle \qquad \le C \mu ( B _ { R } ) } & { } \\ { \displaystyle \le C R ^ { m } , } \end{array}
$$

5where we used the boundedness of $u$ which forces $h$ to be bounded too.

6 Let be $A _ { 1 }$ and $A _ { 2 }$ be defined as in Lemma 2.2. By Lemma 2.2, there exists a   
7 constant $C = C ( \delta , g _ { 0 } ) > 0$ such that

$$
\int _ { B _ { R } } ( G ( | \nabla u | ) - G ( | \nabla h | ) ) \mathrm { d } x \geq C \int _ { A _ { 2 } } G ( | \nabla u - \nabla h | ) \mathrm { d } x
$$

8and

$$
\int _ { B _ { R } } ( G ( | \nabla u | ) - G ( | \nabla h | ) ) \mathrm { d } x \geq C \int _ { A _ { 1 } } \frac { g ( | \nabla u | ) } { | \nabla u | } | \nabla u - \nabla h | ^ { 2 } \mathrm { d } x .
$$

By $( G _ { 2 }$ ) $\frac { G ( t ) } { t }$ is increasing in $t > 0$ . It follows from ( $G _ { 2 }$ ）， $G _ { 3 }$ ), (6), (8) and Lemma 2.2 that

$$
\begin{array} { r l } { \int _ { 0 } ^ { \infty } \mathrm { d }  { \mathbb { R } } \exp \mathrm { - } \mathrm {  ~ \lambda ~ } \exp \left( \frac { \displaystyle \int _ { 0 } ^ { \infty } \mathrm { d }  { \mathbb { R } } \log \mathrm {  ~ \lambda ~ } \exp \mathrm { \lambda ~ } \xi } { \displaystyle \int _ { 0 } ^ { \infty } \mathrm { d }  { \mathbb { R } } \log \mathrm {  ~ \lambda ~ } \exp \mathrm { \lambda ~ } \xi } \right) d  { \mathrm { \Lambda } } } & { \leq \exp \left( \frac { \displaystyle \int _ { 0 } ^ { \infty } \mathrm { d }  { \mathbb { R } } \log \mathrm {  ~ \lambda ~ } \exp \mathrm { \lambda ~ } \xi } { \displaystyle \int _ { 0 } ^ { \infty } \mathrm { d }  { \mathbb { R } } \log \mathrm {  ~ \lambda ~ } \exp \mathrm { \lambda ~ } \xi } \right) } \\ & { \leq \exp \left( \frac { \displaystyle \int _ { 0 } ^ { \infty } \mathrm { d }  { \mathbb { R } } \log \mathrm {  ~ \lambda ~ } \exp \mathrm { \lambda ~ } \xi } { \displaystyle \int _ { 0 } ^ { \infty } \mathrm { d }  { \mathbb { R } } \log \mathrm {  ~ \lambda ~ } \exp \mathrm { \lambda ~ } \xi } \right) d  { \mathrm { \Lambda } } } \\ & { \quad - \int _ { 0 } ^ { \infty } \frac { \mathrm { d }  { \mathbb { R } } \pi \mathrm {  { R } } \mathrm {  { R } } \mathrm {  \Lambda } \mathrm {  \xi ~ } \exp \mathrm { \lambda ~ } \exp \mathrm { \lambda ~ } \xi } { \displaystyle \left( \mathrm { d } \mathrm { \Lambda } \xi \right) \xi \displaystyle \sum _ { i = 1 } ^ { N } \mathrm { \it \mathbb { R } } \mathrm {  \Lambda } \mathrm {  ~ \Lambda } \exp \mathrm { \lambda ~ } \xi } } \\ &  \quad - \int _ { 0 } ^ { \infty } \frac { \mathrm { d }  { \mathbb { R } } \pi \mathrm {  { R } } \mathrm {  \Lambda } \mathrm {  \xi ~ } \exp \mathrm { \lambda ~ } \mathrm {  \lambda ~ } \exp \mathrm { \lambda ~ } \xi } { \displaystyle \left( \mathrm { d } \mathrm { \Lambda } \xi \right) \xi \displaystyle \sum _ { i = 1 } ^ { N } \mathrm {  ~ \lambda ~ } \exp \mathrm { \lambda ~ } \left( \mathrm { d } \mathrm { \Lambda } \mathrm {  ~ \lambda ~ } \mathrm {  ~ \lambda ~ } \right) } \\ &  \leq \exp \left( \frac { \displaystyle \int _ { 0 } ^ { \infty } \mathrm { d } \mathrm {  { \mathbb { R } } \mathrm {  ~ \lambda ~ } \cosh \mathrm { \ u ~ } \xi } \right) \left( \mathrm { d } \mathrm { \Lambda } \xi \right) \left( \mathrm { d } \mathrm { \Lambda } \mathrm {  ~ \lambda ~ } \mathrm {  ~ \lambda ~ } \right) } \\ &  \quad - \int _ { 0 }  \end{array}
$$

where in the last inequality but one we used $( a + b ) ^ { \gamma } \leq a ^ { \gamma } + b ^ { \gamma }$ for any $a \geq 0 , b \geq 0$ and $\gamma \in ( 0 , 1 )$ . By (7) and (9),we have

$$
\begin{array} { r l } {  { \int _ { B _ { R } } G ( | \nabla u - \nabla h | ) \mathrm { d } x = \int _ { A _ { 2 } } G ( | \nabla u - \nabla h | ) \mathrm { d } x + \int _ { A _ { 1 } } G ( | \nabla u - \nabla h | ) \mathrm { d } x } } \\ & { \leq C \int _ { B _ { R } } ( G ( | \nabla u | ) - G ( | \nabla h | ) ) \mathrm { d } x + C R ^ { m } + C R ^ { \frac { m + \lambda } { 2 } } } \\ & { \leq C R ^ { m } + C R ^ { \frac { m + \lambda } { 2 } } . } \end{array}
$$

2Proof of Theorem 1.1. Let $h$ bea $G$ -harmonic function in $B _ { R }$ that agrees with $u$   
3on the boundary, i.e.,

$$
\operatorname { d i v } { \frac { g ( | \nabla h | ) } { | \nabla h | } } \nabla h = 0 \ \mathrm { i n } \ B _ { R } \quad { \mathrm { a n d } } \quad h - u \in W _ { 0 } ^ { 1 , G } ( B _ { R } ) .
$$

ByLemma 2.4 andLemma 3.1, for any $r \leq R$ there holds

$$
\begin{array} { r l } {  { \int _ { B _ { r } } G ( | \nabla u - ( \nabla u ) _ { r } | ) \mathrm { d } x } } \\ & { \le C \bigg ( \frac { r } { R } \bigg ) ^ { n + \sigma } \int _ { B _ { R } } G ( | \nabla u - ( \nabla u ) _ { R } | ) \mathrm { d } x + C \int _ { B _ { R } } G ( | \nabla u - \nabla h | ) \mathrm { d } x } \\ & { \le C \bigg ( \frac { r } { R } \bigg ) ^ { n + \sigma } \int _ { B _ { R } } G ( | \nabla u - ( \nabla u ) _ { R } | ) \mathrm { d } x + C R ^ { m } + C R ^ { \frac { m + \lambda } { 2 } } , } \end{array}
$$

1 where $\lambda$ is an arbitrary constant in $( 0 , n )$

(i) If $m > n$ , then we have

$$
\int _ { B _ { r } } G ( | \nabla u - ( \nabla u ) _ { r } | ) \mathrm { d } x \leq C \bigg ( \frac { r } { R } \bigg ) ^ { n + \sigma } \int _ { B _ { R } } G ( | \nabla u - ( \nabla u ) _ { R } | ) \mathrm { d } x + C R ^ { \frac { m + \lambda } { 2 } } .
$$

Since $m > n$ and $\lambda$ is an arbitrary constant in $( 0 , n )$ , one may have choose $\lambda$ satisfying ${ \frac { m + \lambda } { 2 } } > n$ . In view of Lemma 2.5, we conclude that for any $\tau < \operatorname* { m i n } \{ \sigma , { \frac { m + \lambda } { 2 } } - n \}$ there holds

$$
\int _ { B _ { r } } G ( | \nabla u - ( \nabla u ) _ { r } | ) \mathrm { d } x \leq C r ^ { n + \tau } , \quad \forall \ r \leq R .
$$

Now we claim that

$$
\int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | \mathrm { d } x \leq C r ^ { n + \frac { \tau } { 1 + g _ { 0 } } } , \quad \forall r \leq R .
$$

Indeed, for $r$ satisfying $\begin{array} { r } { r ^ { - n } \int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | \mathrm { d } x \leq r ^ { \frac { \tau } { 1 + g _ { 0 } } } } \end{array}$ ,(11） holds with $C = 1$ ： Now for $r$ satisfying $\begin{array} { r } { r ^ { - n } \int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | \mathrm { d } x > r ^ { \frac { 1 } { 1 + g _ { 0 } } } } \end{array}$ ， we infer from the increasing monotonicity of $\textstyle { \frac { G ( t ) } { t } }$ in $t > 0$ ，

$$
\frac { G \big ( r ^ { - n } \int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | \mathrm { d } x \big ) } { r ^ { - n } \int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | \mathrm { d } x } \geq \frac { G \big ( r ^ { \frac { \tau } { 1 + g _ { 0 } } } \big ) } { r ^ { \frac { \tau } { 1 + g _ { 0 } } } } .
$$

It follows from $\left( G _ { 2 } \right)$ and $\left( G _ { 3 } \right)$

$$
\begin{array} { r } { \displaystyle \int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | { \mathrm { d } } x \leq \frac { r ^ { n + \frac { \tau } { 1 + g _ { 0 } } } } { G \left( r ^ { \frac { \tau } { 1 + g _ { 0 } } } \right) } G \Bigg ( r ^ { - n } \displaystyle \int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | { \mathrm { d } } x \Bigg ) } \\ { \leq \frac { C r ^ { n + \frac { \tau } { 1 + g _ { 0 } } } } { r ^ { \tau } G ( 1 ) } G \Bigg ( r ^ { - n } \displaystyle \int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | { \mathrm { d } } x \Bigg ) } \\ { \leq \frac { C r ^ { n + \frac { \tau } { 1 + g _ { 0 } } } } { r ^ { \tau } g ( 1 ) } G \Bigg ( r ^ { - n } \displaystyle \int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | { \mathrm { d } } x \Bigg ) . } \end{array}
$$

Note that convexity of $G$ and（10) implies that

$$
G \bigg ( \frac { 1 } { | B _ { r } | } \int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | \mathrm { d } x \bigg ) \leq \frac { 1 } { | B _ { r } | } \int _ { B _ { r } } G \big ( | \nabla u - ( \nabla u ) _ { r } | \big ) \mathrm { d } x \leq C r ^ { \tau } .
$$

By $\left( G _ { 3 } \right)$ , (12) and (13),one may get

$$
\int _ { B _ { r } } | \nabla u - ( \nabla u ) _ { r } | \mathrm { d } x \leq C r ^ { n + \frac { \tau } { 1 + g _ { 0 } } } ,
$$

3where $C$ depends only on $g ( 1 ) , g _ { 0 }$ and the volume of the unit ball. Now we have   
4proven that (11） holds for any $r ~ \leq ~ R$ Thus $u \in C _ { l o c } ^ { 1 , \frac { 1 } { 1 + g _ { 0 } } } ( \Omega )$ lg (Ω) by Campanato’s

embedding Theorem.Due to the arbitrary of $\lambda \in \mathsf { ( 0 , \it { n } ) }$ ，we can conclude (i） of 2Theorem 1.1 by letting $\lambda  n$ ： (ii) If $m \in [ n - 1 , n ]$ , we only prove for $m = n - 1$ due to the fact $\mu ( B _ { r } ) \leq C r ^ { m } \leq$ （204号 $C r ^ { n - 1 }$ with small $r$ .By ( $G _ { 4 }$ ), Lemma 2.3 and Lemma 3.1, we infer

$$
\begin{array} { r l r } {  { \int _ { B _ { r } } G ( | \nabla u | ) \mathrm { d } x \le C \int _ { B _ { r } } G ( | \nabla u - \nabla h | ) \mathrm { d } x + C \int _ { B _ { r } } G ( | \nabla h | ) \mathrm { d } x } } \\ & { } & { \le C r ^ { m } + C r ^ { \frac { m + \lambda } { 2 } } + C r ^ { \lambda } } \\ & { } & { \le C r ^ { m } , } \end{array}
$$

3where in the last inequality we let $n > \lambda > n - 1 = m$

We claim that for any $r \leq R < 1$ with $B _ { R } \subset \joinrel \subset \Omega$ and some positive constant $C$ （204号 independent of $r$ ,there holds

$$
\int _ { B _ { r } } | \nabla u | \mathrm { d } x \leq C r ^ { n - 1 + \alpha _ { 0 } } ,
$$

4with some $\alpha _ { 0 } \in ( 0 , 1 )$

Indeed, for $r \leq R$ satisfying

$$
r ^ { - n + 1 - \alpha _ { 0 } } \int _ { B _ { r } } | \nabla u | \mathrm { d } x \leq 1 ,
$$

(14) holds with $C = 1$ .For $r \leq R$ satisfying

$$
r ^ { - n + 1 - \alpha _ { 0 } } \int _ { B _ { r } } | \nabla u | \mathrm { d } x \geq 1 ,
$$

due to the increasing monotonicity of $F ( t ) = G ( t ) - G ( 1 ) t$ in $t \geq 1$ ,it follows

$$
G \bigg ( r ^ { - n + 1 - \alpha _ { 0 } } \int _ { B _ { r } } | \nabla u | \mathrm { d } x \bigg ) \geq G ( 1 ) \cdot r ^ { - n + 1 - \alpha _ { 0 } } \int _ { B _ { r } } | \nabla u | \mathrm { d } x .
$$

Then we have

$$
\begin{array} { r l } {  { \int _ { B _ { r } } | \nabla u | \mathrm { d } x \le C r ^ { n - 1 + \alpha _ { 0 } } ( r ^ { 1 - \alpha _ { 0 } } ) ^ { 1 + \delta } G \bigg ( r ^ { - n } \int _ { B _ { r } } | \nabla u | \mathrm { d } x \bigg ) } } \\ & { \le C r ^ { n - 1 + \alpha _ { 0 } } \cdot ( r ^ { 1 - \alpha _ { 0 } } ) ^ { 1 + \delta } \frac { 1 } { | B _ { r } | } \int _ { B _ { r } } G ( | \nabla u | ) \mathrm { d } x } \\ & { \le C r ^ { n - 1 + \alpha _ { 0 } + ( 1 - \alpha _ { 0 } ) ( 1 + \delta ) } \cdot r ^ { - n } \cdot r ^ { m } } \\ & { = C r ^ { n - 1 + \alpha _ { 0 } + ( 1 - \alpha _ { 0 } ) ( 1 + \delta ) + m - n } . } \end{array}
$$

5 Combining(15） and (16),we may choose $\alpha _ { 0 } = \alpha _ { 0 } + ( 1 - \alpha _ { 0 } ) ( 1 + \delta ) + m - n$ ,i.e.,   
6 $\begin{array} { r } { \alpha _ { 0 } = 1 - \frac { n - m } { 1 + \delta } } \end{array}$ n such that (14) holds for allr ≤ R.   
7 For $m = n - 1$ ， we conclude that $u \in C _ { l o c } ^ { 0 , \alpha _ { 0 } } ( \Omega )$ by Morrey Theorem (see page 30,   
8 [12]） with αo = 1δ·

Note that inf u ≤ inf h (see the proof of Theorem 3.3 in [3]). Then by (5) and Lemma 2.3, we have for $\lambda$ larger than $m + \alpha _ { 0 }$ （204号

$$
\begin{array} { r l } {  { \int _ { B _ { r } } G ( | \nabla u | ) \mathrm { d } x \leq \int _ { B _ { r } } ( u - h ) \mathrm { d } \mu + \int _ { B _ { r } } G ( | \nabla h | ) \mathrm { d } x } } \\ & { \leq ( \operatorname* { s u p } u - \operatorname* { i n f } h ) \mu ( B _ { r } ) + \int _ { B _ { r } } G ( | \nabla h | ) \mathrm { d } x } \\ & { \leq ( \operatorname* { s u p } u - \operatorname* { i n f } u ) \mu ( B _ { r } ) + \int _ { B _ { r } } G ( | \nabla h | ) \mathrm { d } x } \\ & { \leq C \operatorname* { s u p } u - \operatorname* { i n f } _ { \bar { B } _ { r } } m ) \mu ( B _ { r } ) + \int _ { B _ { r } } G ( | \nabla h | ) \mathrm { d } x } \\ & { \leq C \operatorname* { s u c } ( u , B _ { r } ) r ^ { m } + C r ^ { \lambda } } \\ & { \leq C r ^ { \alpha + m } + C r ^ { \lambda } } \\ & { \leq C r ^ { m + \alpha } , } \end{array}
$$

where $\displaystyle \csc ( u , B _ { r } ) = \operatorname* { s u p } _ { B _ { r } } u - \operatorname* { i n f } _ { B _ { r } } u$ . Arguing as (14),， we get $u \in C _ { l o c } ^ { 0 , \alpha _ { 1 } } ( \Omega )$ with

$$
\alpha _ { 1 } = 1 - \frac { n - ( m + \alpha _ { 0 } ) } { 1 + \delta } = \frac { \delta } { 1 + \delta } + \frac { \alpha _ { 0 } } { 1 + \delta } .
$$

Repeating this process we get $u \in C _ { l o c } ^ { 0 , \alpha _ { k } } ( \Omega )$ with

$$
\alpha _ { k } = \frac { \delta } { 1 + \delta } + \frac { \alpha _ { k - 1 } } { 1 + \delta } .
$$

Finally we have $\begin{array} { r } { \alpha _ { k } = \frac { \alpha _ { 0 } } { ( 1 + \delta ) ^ { k } } + \delta \Sigma _ { j = 1 } ^ { k } \frac { 1 } { ( 1 + \delta ) ^ { j } } } \end{array}$ =1(1+δ)s,which leads to limk→αk=1,and the   
2 result follows.   
3 (ii) If $n - 1 - \delta < m < n - 1$ ， checking the proof and repeating the process as   
4 above, we may get $\begin{array} { r } { \alpha _ { 0 } = 1 - \frac { n - m } { 1 + \delta } } \end{array}$ 、， $\begin{array} { r } { \alpha _ { 1 } = \frac { 1 + \delta + m - n } { 1 + \delta } + \frac { \alpha _ { 0 } } { 1 + \delta } } \end{array}$ 1+，,.,k=1+δ+m-n+   
5 Finally, one has $u \in C _ { l o c } ^ { 0 , \alpha } ( \Omega )$ for any $\alpha \in ( 0 , \frac { 1 + \delta + m - n } { \delta } )$ ： □

6

# REFERENCES

7 [1] R.A.Adams and J.J.F.Fournier,Sobolev Spaces.Pure and Applied Mathematics.Amster  
8 dam:Acad.Press (140) 2003.   
9 [2] J.E.M. Braga and D.R.Moreira,Uniform Lipschitz regularity for classes of minimizers in   
10 two phase free boundary problems in Orlicz spaces with small density on the negative phase,   
11 Ann.Inst.H.Poincaré Anal. Non Linéare,31 (2014)(4),823-850.   
12 [3] S.Challal and A.Lyaghfouri,Holder continuity of solutions to the $A$ -Laplace equation in  
13 volving measures,Common.Pure Appl.Anal.,8 (2009)(5),1577-1583.   
14 [4] S. Challal and A.Lyaghfouri, Porosity of free boundaries in $A$ -obstacle problems,Nonlinear   
15 Anal.,70 (2009)(7),2772- 2778.   
16 [5] S.Challal and A.Lyaghfouri, Removable Sets for A-Harmonic Functions,Z. Anal.Anwend.,   
17 30(2011)(4),421- 433.   
18 [6] S.Challal,A.Lyaghfouri and J.F.Rodrigues,On the $A$ -obstacle problem and the Hausdorff   
19 measure of its free boundary,Ann.Mat.Pura Appl.(4),191 (2012)(1),113-165.   
20 [7]T.Kilpelainen,Holder continuity of solutions to quasilinear elliptic equations involving mea  
21 sures,Potential Analysis,3(1994)(3),265-272.   
22 [8] T.Kilpelainen,X. Zhong,Removable set for continuous solutions of quasilinear eliptic equa  
23 tions,Proc.Amer.Math.Soc.,130 (2002)(6),1681-1688.   
24 [9] R.Leitao,O. S.de Queiroz and E.V. Teixeira,Regularity for degenerate two-phase free   
25 boundary problems,Ann.Inst.H.Poincaré Anal.Non Linéare,32 (2015)(4),741-762.   
26 [10] G.M.Lieberman,The natural generalization of the natural conditions of Ladyzhensaya and   
27 Ural'tseva for eliptic equations,Comm.Partial Differ.Equ.,16 (1991)(2C3),311-361.   
28 [11]A.Lyaghfouri ，Holder continuity of $p ( x )$ -superharmonic functions，Nonlinear Anal.,73   
29 (2010)(8),2433-2444.   
1 [12] J.Maly and W.P.Ziemer,Fine Regularity of Solutions of Elliptic Partial Differential Equa  
2 tions,Math.Surveys Monogr.51.Providence (RI):Amer.Math.Soc.,1997.   
3 [13] S.Martinez and N.Wolanski,A minimum problem with free boundary in Orlicz spaces,Adu.   
4 Math.,218 (2008)(6),1914-1971.   
5 [14] J. Zheng,B. Feng and Z. Zhang,Regularity of solutions to the $G$ -Laplace equation involving   
6 measures, Z. Anal. Anwend.,34 (2015)(2),165-174.   
7 [15] J.Zheng,B.Feng and P. Zhao,，Regularity of minimizers in the two-phase free boundary   
8 problems in Orlicz-Sobolev spaces,Z.Anal.Anwend.,36(2017)(1),37-47.   
9 [16] J.Zheng,Z. Zhang and P. Zhao,A minimum problem with two-phase free boundary in Orlicz   
10 spaces,Monatsh.Math.,172(2013)(3-4),441-475.   
11 Received xxxx 20xx; revised xxxx 20xx.   
12 E-mail address: zhengjun2014@aliyun.com,zhengjun@swjtu.edu.cn   
13 E-mail address: zhangyan@swjtu.edu.cn