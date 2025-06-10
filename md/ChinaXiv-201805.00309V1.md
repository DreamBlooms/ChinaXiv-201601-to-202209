# Singular three-body integrals for Hylleraas wave functions

Xiao-Qiu Qi $^ { 1 , 2 }$ ， Zhen-Xiang Zhong $^ 1$ ,\* and Pei-Pei Zhang $^ { - 1 }$ （204号 $^ { 1 }$ Division of Theoretical and Interdisciplinary Research, State Key Laboratory of Magnetic Resonance and Atomic and Molecular Physics, Wuhan Institute of Physics and Mathematics, Chinese Academy of Sciences， Wuhan 430071， China and （20 $^ 2$ University of Chinese Academy of Sciences， Beijing 100049, China (Dated: February 10, 2018)

Abstract

In this paper, we study singular integrals that appear in calculations of relativistic and quantum electrodynamic corrections for three-body Coulomb systems using Hyllraas coordinates. A general scheme is developed to separate the divergent part of a singular integral involving Hylleraas basis functions of type $r _ { 1 } ^ { i } r _ { 2 } ^ { j } r _ { 1 2 } ^ { l } \exp ( - \alpha r _ { 1 } - \beta r _ { 2 } )$ . The integrals of type $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ with $a \geq - 1$ ， （204号 $b \geq - 1$ ,and $n = 1 , 2 , 3$ are considered and matched with $\Gamma _ { l , m , n } ( \alpha , \beta , \gamma )$ for both singular and regular parts. Moreover, we also consider the singular integrals of type $I _ { q } ( a , b , c ; \alpha , \beta )$ where $c \geq - 1$ and at least one of $a$ and $b$ is negative.

# I. INTRODUCTION

Few-body atomic and molecular systems are basic grounds for testing physical laws, such as quantum electrodynamics (QED), as well as are one of the sources of determining fundamental constants of nature by combining precision measurements and precision theoretical calculations. Important examples include the atomic helium whose $2 ^ { 3 } P _ { J }$ fine structure holds potential for deriving the fine structure constant $\alpha$ [1, 2], the hydrogen molecular ions $\mathrm { H _ { 2 } ^ { + } }$ and HD $^ +$ from which one can determine the electron to nuclear mass ratios [3,4],and the antiprotonic helium $\bar { p } \mathrm { H e } ^ { + }$ that can be use to test the CPT theorem [4] in relativistic quantum field theory.

From theoretical side, the eigenvalue problems for the nonrelativistic Hamiltonians of these Coulomb three-body systems can be solved very precisely using variationally constructed wave functions in Hylleraas coordinates, which lays a foundation for further evaluating relativistic and QED corrections to a required precision. The matrix elements of many singular relativistic and QED operators can be divergent individually; however, the divergent parts of these singular integrals should be cancelled with other counterparts, resulting in a finite value. In general, rotational degrees of freedom in a matrix element can first be isolated analytically and treated using angular momentum theory, and the remaining part of the matrix element becomes an integral that involves only radial coordinates, such as $r _ { 1 }$ ， （20 $r _ { 2 }$ ，and $r _ { 1 2 } = \left| r _ { 1 } - r _ { 2 } \right|$ for a two-electron system [5]. Of course, the basic type of radial integrals depends on the variational basis functions chosen.

One of the most popular variational basis sets used for three-body Coulombic systems is [6]

$$
\{ \mathcal { V } _ { L M } ^ { \ell _ { 1 } \ell _ { 2 } } ( \hat { \pmb { r } } _ { 1 } , \hat { \pmb { r } } _ { 2 } ) e ^ { - \alpha r _ { 1 } - \beta r _ { 2 } - \gamma r _ { 1 2 } } \} ,
$$

where $\mathcal { V } _ { L M } ^ { \ell _ { 1 } \ell _ { 2 } } ( \hat { { \pmb r } } _ { 1 } , \hat { { \pmb r } } _ { 2 } )$ is the angular momentum eigenfunction formed by $\ell _ { 1 }$ and $\ell _ { 2 }$ ，and $\alpha$ ， $\beta$ ， and $\gamma$ are three nonlinear variational parameters. This type of basis set has been successfully applied to the calculations of relativistic and QED effects for systems like the antiprotonic helium [7] and the hydrogen molecular ions [8]. The radial integrals for this type of basis functions are of the form

$$
\Gamma _ { l , m , n } ( \alpha , \beta , \gamma ) = \int _ { 0 } ^ { \infty } d r _ { 1 } \int _ { 0 } ^ { \infty } d r _ { 2 } \int _ { | r _ { 1 } - r _ { 2 } | } ^ { r _ { 1 } + r _ { 2 } } d r _ { 1 2 } r _ { 1 } ^ { l } r _ { 2 } ^ { m } r _ { 1 2 } ^ { n } e ^ { - \alpha r _ { 1 } - \beta r _ { 2 } - \gamma r _ { 1 2 } } .
$$

The above integral is invariant under the simultaneous permutation of $l$ ， $m$ ， $n$ and $\alpha$ ， $\beta$ ， $\gamma$ ， and its range of integration covers all possible values of $r _ { 1 }$ ， $r _ { 2 }$ ，and $r _ { 1 2 }$ with $( r _ { 1 } , \ r _ { 2 }$ ， （204号 $r _ { 1 2 }$ ） forming a triangle. This integral can be evaluated recursively [9],and the analytical expressions for the singular integrals $\Gamma _ { - p , 0 , 0 } ( \alpha , \beta , \gamma )$ and $\Gamma _ { - p , - 1 , 0 } ( \alpha , \beta , \gamma )$ with integer $p > 0$ （204号 have been derived by Harris et al.[10]. Korobov [11] has recently worked out the singular integrals of the type $\Gamma _ { - 2 , - 2 , 0 } ( \alpha , \beta , \gamma )$ . It should be mentioned that the following recursion relation will be used frequently in dealing with singular integrals:

$$
\Gamma _ { l + 1 , m , n } ( \alpha , \beta , \gamma ) = - \frac { \partial } { \partial \alpha } \Gamma _ { l , m , n } ( \alpha , \beta , \gamma ) .
$$

Another widely used basis set is based on the correlated Hylleraas functions

$$
\{ \mathcal { V } _ { L M } ^ { \ell _ { 1 } \ell _ { 2 } } ( \hat { \pmb { r } } _ { 1 } , \hat { \pmb { r } } _ { 2 } ) r _ { 1 } ^ { a } r _ { 2 } ^ { b } r _ { 1 2 } ^ { c } e ^ { - \alpha r _ { 1 } - \beta r _ { 2 } } \} ,
$$

which has been applied to high-precision calculations for two-electron atomic systems [12, 13], the hydrogen molecular ions [14-18],and the antiprotonic helium [19]. After averaging the rotational degrees of freedom, the radial integral can be reduced to [5]

$$
I _ { q } ( a , b , c ; \alpha , \beta ) = \int _ { 0 } ^ { \infty } r _ { 1 } d r _ { 1 } \int _ { 0 } ^ { \infty } r _ { 2 } d r _ { 2 } \int _ { | r _ { 1 } - r _ { 2 } | } ^ { r _ { 1 } + r _ { 2 } } r _ { 1 2 } d r _ { 1 2 } ~ r _ { 1 } ^ { a } r _ { 2 } ^ { b } r _ { 1 2 } ^ { c } e ^ { - \alpha r _ { 1 } - \beta r _ { 2 } } P _ { q } ( \cos \theta ) ~ .
$$

where $\cos \theta = ( r _ { 1 } ^ { 2 } + r _ { 2 } ^ { 2 } - r _ { 1 2 } ^ { 2 } ) / ( 2 r _ { 1 } r _ { 2 } )$ and $P _ { q } ( \cos \theta )$ is the Legendre polynomial. By using one of the recurrence relations for $P _ { q } ( \cos \theta )$ ， $I _ { q } ( a , b , c ; \alpha , \beta )$ can be expressed in terms of various $I _ { 0 } ( a , b , c ; \alpha , \beta )$ [5]. The analytical expression for $I _ { q }$ has been worked out by Yan and Drake [2O] for the case where $a , b , c \geq - 2$ and $a + b + c + 5 \geq 0$ .An analytical expression for singular integral $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ with $n \geq 1$ was obtained in [12] together with some examples for analytical cancellation of some singularities, where the singular parts are written in terms of some subsidiary divergent integrals. The analytical expression for $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ has been derived by Drake [13] applying the differential chain rule on the generation integral $I _ { 0 } ( - 1 , - 1 , - 2 - n ; \alpha , \beta )$ ，where the generation integral was treated by replacing the lower limit of the integral by $\epsilon$ and studying the behavior as $\epsilon \to 0 ^ { + }$ . This ideal was adopted by Harris et al. [1O] who studied the singular integrals of type $\Gamma _ { l , m , n } ( \alpha , \beta , \gamma )$ .For evaluating high-order relativistic and QED effects, more singular integrals than $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ are required, such as $I _ { q } ( - 2 - n , b , c ; \alpha , \beta )$ 2 （204号 $I _ { q } ( - 2 - m , - 2 - n , c ; \alpha , \beta )$ ，and $I _ { q } ( - 2 - m , b , - 2 - n ; \alpha , \beta )$ with $m , n = 0 , 1 , 2 , \ldots$

Comparing Eqs. (2) and (5),one can establish the following relation

$$
I _ { 0 } ( a , b , c ; \alpha , \beta ) = \Gamma _ { a + 1 , b + 1 , c + 1 } ( \alpha , \beta , 0 ) .
$$

Most singular integrals $I _ { q } ( a , b , c ; \alpha , \beta )$ can be evaluated through $\Gamma _ { l , m , n } ( \alpha , \beta , 0 )$ except the integrals of type $I _ { q } ( - 2 - m , - 2 - n , c ; \alpha , \beta )$ with $m , n \geq 0$ . For the case of $m = n = 0$ ，let us evaluate $I _ { 0 } ( - 2 , - 2 , c ; \alpha , \beta )$ through the generation function $\Gamma _ { - 1 , - 1 , 0 } ( \alpha , \beta , 0 )$ that can be obtained from the following formula (see Appendix $\mathrm { F }$ of Ref. [10])

$$
\Gamma _ { - 1 , - 1 , 0 } ( \alpha , \beta , \gamma ) = \frac { 1 } { \gamma } \left[ \frac { 1 } { 2 } \ln ^ { 2 } \left( \frac { \alpha + \gamma } { \beta + \gamma } \right) + \mathrm { d i l o g } \left( \frac { \alpha + \beta } { \alpha + \gamma } \right) + \mathrm { d i l o g } \left( \frac { \alpha + \beta } { \beta + \gamma } \right) + \frac { \pi ^ { 2 } } { 6 } \right] ,
$$

by taking the limit $\gamma \to 0$ ，where dilog is the dilogarithm function. It is,however,impossible to evaluate $I _ { 0 } ( - 2 , - 2 , c ; \alpha , \beta )$ with $c \geq 0$ by differentiating $I _ { 0 } ( - 2 , - 2 , - 1 ; \alpha , \beta )$ with respect to $\gamma$ which equals zero.

The purpose of this paper is to study two types of singular integrals arising from $I _ { q } ( a , b , c ; \alpha , \beta )$ ，including $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ in Sec. I and $I _ { q } ( - 2 \mathrm { ~ - ~ } m , - 2 \mathrm { ~ - ~ } n , c ; \alpha , \beta )$ with $c \geq - 1$ in Sec. III. The singular parts of these integrals will be given explicitly. The verification of our results will be presented in Sec. IV together with a conclusion.

# II. SINGULAR INTEGRALS $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$

The derivation of $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ with integer $n \geq 1$ has been performed in Ref. [12]. Here we quote the final result:

$$
I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta ) = O _ { 1 } + O _ { 2 } + O _ { 3 } ,
$$

where

$$
\begin{array} { l } { { \displaystyle O _ { 1 } = - \frac { 1 } { n } \frac { ( a + 1 ) ! ( b + 1 ) ! ( a + b + 3 - n ) ! } { ( a + b + 3 ) ! a ^ { \alpha ( 1 2 - n \beta ) ! 2 } } F _ { 1 } ( b + 2 , n ; a + b + 4 ; \frac { \beta - \alpha } { \beta } ) , ~ \beta \ge } } \\ { { \displaystyle \quad = - \frac { 1 } { n } \frac { ( a + 1 ) ! ( b + 1 ) ! ( a + b + 3 - n ) ! } { ( a + b + 3 ) ! \beta ^ { k + 2 - n } \alpha ^ { \alpha + 2 } } \mathrm { { } } _ { 2 } ^ { 1 } F _ { 1 } ( a + 2 , n ; a + b + 4 ; \frac { \alpha - \beta } { \alpha } ) } , ~ \beta \le }  \\ { { \displaystyle O _ { 2 } = \frac { 1 } { n } \sum _ { j = 0 } ^ { b + 1 } \frac { ( b + 1 ) ! } { j ! ( b + 1 - j ) ! } \frac { ( a + b + 2 - j ) ! } { ( \alpha + \beta ) ^ { \alpha + b + 3 - j } } X _ { n - j } ( \beta ) , } } \\ { { \displaystyle O _ { 3 } = \frac { 1 } { n } \sum _ { j = 0 } ^ { a + 1 } \frac { ( a + 1 ) ! } { j ! ( a + 1 - j ) ! } \frac { ( a + b + 2 - j ) ! } { ( \alpha + \beta ) ^ { \alpha + b + 3 - j } } X _ { n - j } ( \alpha ) . } } \end{array}
$$

In the above, $X _ { p } ( x )$ is defined as

$$
X _ { p } ( x ) = \int _ { 0 } ^ { \infty } t ^ { - p } e ^ { - x t } d t ,
$$

which has different analytical forms for different $n$ . Equation (8) is valid for $a , b \geq - 1$ and $a + b + 3 \geq n \geq 1$ . The divergent part of the integral is identified as the uncalculated subsidiary integrals $X _ { p } ( x )$ . In order to simplify singularity cancellation procedure so that some matrix elements involving singular operators like $1 / r _ { 1 2 } ^ { 3 }$ and $1 / r _ { 1 2 } ^ { 4 }$ can be evaluated more easily, it is desirable to find out the explicit form of $X _ { p } ( x )$

In Ref. [13], Drake presented a different derivation for $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ , in which the integral is evaluated by differentiating $I _ { 0 } ( - 1 , - 2 , - 2 - n ; \alpha , \beta )$ according to

$$
I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta ) = \left( - \frac { \partial } { \partial \alpha } \right) ^ { a + 1 } \left( - \frac { \partial } { \partial \beta } \right) ^ { b + 1 } I _ { 0 } ( - 1 , - 1 , - 2 - n ; \alpha , \beta ) ,
$$

where

$$
I _ { 0 } ( - 1 , - 1 , - 2 - n ; \alpha , \beta ) = \int _ { 0 } ^ { \infty } d r _ { 1 2 } \int _ { 0 } ^ { \infty } d r _ { 2 } \int _ { | r _ { 1 2 } - r _ { 2 } | } ^ { r _ { 1 2 } + r _ { 2 } } d r _ { 1 } { \frac { e ^ { - \alpha r _ { 1 } - \beta r _ { 2 } } } { r _ { 1 2 } ^ { n + 1 } } } .
$$

The above integral can further be simplified to the following form after performing integrations over $r _ { 1 }$ and $r _ { 2 }$ （204号

$$
I _ { 0 } ( - 1 , - 1 , - 2 - n ; \alpha , \beta ) = - \frac { 2 } { \alpha ^ { 2 } - \beta ^ { 2 } } \int _ { \epsilon } ^ { \infty } \frac { d r _ { 1 2 } } { r _ { 1 2 } ^ { n + 1 } } ( e ^ { - \alpha r _ { 1 2 } } - e ^ { - \beta r _ { 1 2 } } ) ,
$$

where the lower limit of the integral has been replaced by an infinitesimally small positive quantity $\epsilon$ . One then considers the behavior of the integral as $\epsilon  0$ , where the regular part of the integral does not depend on $\epsilon$ and the singular part depends on $\epsilon$ in the form of either （204号 $\ln \epsilon$ or $1 / \epsilon$ ：

In order to evaluate Eq. (12), it would be convenient to introduce an auxiliary function $L _ { p } ( x )$ defined by

$$
L _ { p } ( x ) = \int _ { \epsilon } ^ { \infty } t ^ { - p } e ^ { - x t } d t .
$$

For positive integer $p$ ， $L _ { p } ( x )$ can be recast to the form listed below as $\epsilon  0$ (see Eq. (9) of Ref. [10] and Appendix A)

$$
L _ { p } ( x ) = ( - x ) ^ { p - 1 } \biggl [ \frac { \psi ( p ) - \ln ( x \epsilon ) } { ( p - 1 ) ! } + \sum _ { j = 1 } ^ { p - 1 } \frac { ( - x \epsilon ) ^ { - j } } { j ( p - j - 1 ) ! } \biggr ] , p > 0
$$

where $\psi ( p )$ is the digamma function defined by $\begin{array} { l } { \psi ( p ) = - \gamma _ { E } + \sum _ { m = 1 } ^ { p - 1 } m ^ { - 1 } } \end{array}$ with $\gamma _ { E } ~ =$ 0.57721... being the Euler's constant. For $p \leq 0$ ， we have

$$
L _ { p } ( x ) = \frac { \Gamma ( - p + 1 ) } { x ^ { 1 - p } } , p \leq 0 .
$$

Using $L _ { p } ( x )$ , the integral in Eq. (12) becomes

$$
I _ { 0 } ( - 1 , - 1 , - 2 - n ; \alpha , \beta ) = \frac { 2 } { \alpha ^ { 2 } - \beta ^ { 2 } } [ L _ { n + 1 } ( \beta ) - L _ { n + 1 } ( \alpha ) ] , \quad n \ge 0 ,
$$

which is the same as Eq. (11） of Ref. [1O] by taking $\gamma$ as zero. Thus, the expressions for $I _ { 0 } ( - 1 , - 1 , - 2 - n ; \alpha , \beta )$ for the first few values of $n$ can be obtained from Eqs. (13)-(16) of Ref. [10] by setting $\gamma = 0$ . Therefore, $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ can be calculated according to

$$
I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta ) = \left( - \frac { \partial } { \partial \alpha } \right) ^ { a + 1 } \left( - \frac { \partial } { \partial \beta } \right) ^ { b + 1 } \frac { 2 } { \alpha ^ { 2 } - \beta ^ { 2 } } [ L _ { n + 1 } ( \beta ) - L _ { n + 1 } ( \alpha ) ] .
$$

It should be mentioned, however, that the integral $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ can also be evaluated recursively using the scheme of Korobov [9].

Now we have two sets of expressions for the same singular integral $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ The first set Eq. (8) can be evaluated directly without use of any recurrence relations; however,it is complicated to deal with singularities. On the contrary, the second set Eq. (17) can be evaluated recursively because of the derivative nature of the expression， and the regular part can be obtained by simply dropping singular terms involving $\ln \epsilon$ and $1 / \epsilon$ .We can unify these two approaches by choosing the following expressions for $X _ { p } ( x )$ that matches Eq. (8) with Eq. (17)

$$
X _ { p } ( x ) = { \left\{ \begin{array} { l l } { L _ { p } ( x ) } & { p \leq 0 } \\ { L _ { p } ( x ) + { \frac { ( - x ) ^ { p - 1 } } { p ! } } } & { n = 1 { \mathrm { ~ a n d ~ } } p > 0 } \\ { L _ { p } ( x ) + { \frac { 2 } { \alpha + \beta + 2 } } { \frac { 1 } { \epsilon } } } & { n = 2 { \mathrm { ~ a n d ~ } } p > 0 } \\ { L _ { p } ( x ) + { \frac { 1 } { 3 } } { \frac { ( - x ) ^ { p - 1 } } { ( p - 1 ) ! } } + { \frac { 2 } { \alpha + \beta + 2 } } { \frac { 1 } { \epsilon ^ { 2 } } } ( 1 - \delta _ { p , 1 } ) } & { n = 3 { \mathrm { ~ a n d ~ } } p > 0 } \end{array} \right. }
$$

The equivalence of Eq. (8) and Eq. (17) can thus be verified explicitly by using a symbolic software such as Mathematica.

It is noted that Eq. (8) will not be applicable for $a + b + 3 < n$ due to the existence of $( a + b + 3 - n ) !$ ！ that appears in $O _ { 1 }$ . In this case, $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ can be evaluated according to Eq. (17), for example,

$$
1 , - 1 , - 4 ; \alpha , \beta ) = \left\{ \begin{array} { l } { \frac { 1 } { \alpha + \beta } \left\{ \frac { 2 } { \epsilon } - ( \alpha + \beta ) [ \psi ( 3 ) - \ln \epsilon ] \right\} + \frac { 1 } { \beta ^ { 2 } - \alpha ^ { 2 } } ( \beta ^ { 2 } \ln \beta - \alpha ^ { 2 } \ln \alpha ) , } \\ { \frac { 1 } { \alpha } \left\{ \frac { 1 } { \epsilon } - \alpha [ \psi ( 3 ) - \ln \epsilon ] \right\} + \ln \alpha + \frac { 1 } { 2 } , } \end{array} \right.
$$

$$
\begin{array}{c} \begin{array} { r } { 1 , - 1 , - 5 ; \alpha , \beta ) = \left\{ \frac { 1 } { \alpha + \beta } \left\{ \frac { 1 } { \epsilon ^ { 2 } } - \frac { \alpha + \beta } { \epsilon } + \frac { \alpha ^ { 2 } + \beta ^ { 2 } + \alpha \beta } { 3 } [ \psi ( 4 ) - \ln \epsilon ] \right\} + \frac { 1 } { 3 ( \alpha ^ { 2 } - \beta ^ { 2 } ) } \bigl ( \beta ^ { 3 } \ln \beta - \mathscr { O } _ { \alpha } ( \cdot ) \bigr ) ^ { - 1 } , \right.} \\ { \frac { 1 } { 2 \alpha } \left\{ \frac { 2 } { \epsilon ^ { 2 } } - \frac { \alpha } { \epsilon } + \alpha ^ { 2 } [ \psi ( 4 ) - \ln \epsilon ] \right\} - \frac { 1 } { 6 } \alpha ( 3 \ln \alpha + 1 ) , \qquad i = 1 , 2 , 3 , \dots , } \end{array}   \end{array}
$$

Other integrals $I _ { 0 } ( a , b , - 5 ; \alpha , \beta )$ with $a \geq - 1$ and $b \geq - 1$ can easily be evaluated by differentiating $I _ { 0 } ( - 1 , - 1 , - 5 ; \alpha , \beta )$ with respect to $\alpha$ and $\beta$ repeatedly.

# III. SINGULAR INTEGRALS $I _ { q } ( a , b , c ; \alpha , \beta )$ WITH $c \geq - 1$

The integral $I _ { q } ( a , b , c ; \alpha , \beta )$ may be calculated directly using the method developed by Yan and Drake in Ref. [20], in which $I _ { q } ( a , b , c ; \alpha , \beta )$ can be reduced to the following form

$$
I _ { q } ( a , b , c ; \alpha , \beta ) = \frac { 2 } { 2 q + 1 } \sum _ { k = 0 } ^ { \mathcal { L } _ { 2 } } C _ { c q k } I _ { R } ( a , b , c ; \alpha , \beta ; q , k ) ,
$$

where $C _ { c q k }$ and $\mathcal { L } _ { 2 }$ are respectively

$$
C _ { c q k } = \frac { 2 q + 1 } { c + 2 } \left( \begin{array} { l } { { c + 2 } } \\ { { 2 k + 1 } } \end{array} \right) ^ { \operatorname* { m i n } [ q - 1 , ( c + 1 ) / 2 ] } \frac { 2 k + 2 t - c } { t = 0 }
$$

and

$$
\begin{array} { r } { \mathcal { L } _ { 2 } = \left\{ \begin{array} { l l } { \frac { 1 } { 2 } c - q } & { c \mathrm { i s ~ e v e n } } \\ { \frac { 1 } { 2 } ( c + 1 ) } & { c \mathrm { i s ~ o d d } , } \end{array} \right. } \end{array}
$$

and $I _ { R }$ is defined as

$$
I _ { R } ( a , b , c ; \alpha , \beta ; q , k ) = \int _ { 0 } ^ { \infty } d r _ { 1 } \int _ { 0 } ^ { \infty } d r _ { 2 } r _ { 1 } ^ { a + 2 } r _ { 2 } ^ { b + 2 } r _ { < } ^ { q + 2 k } r _ { > } ^ { c - q - 2 k } e ^ { - \alpha r _ { 1 } - \beta r _ { 2 } } ,
$$

with $r _ { < } = \operatorname* { m i n } ( r _ { 1 } , r _ { 2 } )$ and $r _ { > } = \operatorname* { m a x } ( r _ { 1 } , r _ { 2 } )$ . As usual, the integral can be broken into two segments at $r _ { 1 } = r _ { 2 }$ （204号

$$
I _ { R } ( a , b , c ; \alpha , \beta ; q , k ) = I _ { R } ^ { 1 } ( v , u ) + I _ { R } ^ { 2 } ( v ^ { \prime } , u ^ { \prime } ) ,
$$

where $I _ { R } ^ { 1 }$ and $I _ { R } ^ { 2 }$ are

$$
\begin{array} { l } { { \displaystyle I _ { R } ^ { 1 } ( v , u ) = \int _ { 0 } ^ { \infty } d r _ { 1 } \int _ { 0 } ^ { r _ { 1 } } d r _ { 2 } ~ r _ { 1 } ^ { v } r _ { 2 } ^ { u } e ^ { - \alpha r _ { 1 } - \beta r _ { 2 } } \ : , } } \\ { { \displaystyle I _ { R } ^ { 2 } ( v ^ { \prime } , u ^ { \prime } ) = \int _ { 0 } ^ { \infty } d r _ { 1 } \int _ { r _ { 1 } } ^ { \infty } d r _ { 2 } ~ r _ { 1 } ^ { v ^ { \prime } } r _ { 2 } ^ { u ^ { \prime } } e ^ { - \alpha r _ { 1 } - \beta r _ { 2 } } \ : , } } \end{array}
$$

and

$$
\begin{array} { r l } & { v = a + 2 + c - q - 2 k , } \\ & { u = b + 2 + q + 2 k , } \\ & { v ^ { \prime } = a + 2 + q + 2 k , } \\ & { u ^ { \prime } = b + 2 + c - q - 2 k . } \end{array}
$$

It will be convenient to define the parameter $s$ （204号

$$
s = v + u + 1 = v ^ { \prime } + u ^ { \prime } + 1 = a + b + c + 5 .
$$

A.Integral $I _ { R } ^ { 1 } ( v , u )$

For the case of $v \geq - 1$ and $u \geq 0$ , the regular integral $I _ { R } ^ { 1 } ( v , u )$ can be expressed in terms of the hypergeometric function

$$
\begin{array} { c } { { I _ { R } ^ { 1 } ( v , u ) = \displaystyle \frac { 1 } { u + 1 } \int _ { 0 } ^ { \infty } d r _ { 1 } r _ { 1 } ^ { s } e ^ { - \alpha r _ { 1 } - \beta r _ { 2 } } { } _ { 1 } F _ { 1 } ( 1 , u + 2 ; \beta r _ { 1 } ) } } \\ { { = \displaystyle \frac { 1 } { u + 1 } \frac { s ! } { ( \alpha + \beta ) ^ { s + 1 } } { } _ { 2 } F _ { 1 } ( 1 , s + 1 ; u + 2 ; \displaystyle \frac { \beta } { \alpha + \beta } ) . } } \end{array}
$$

If the conditions $v \geq - 1$ and $u \geq 0$ are not satisfied, $I _ { R } ^ { 1 }$ is singular that can be recast to

$$
\begin{array} { l } { { \displaystyle I _ { R } ^ { 1 } ( v , u ) = \int _ { 0 } ^ { \infty } d r _ { 1 } \int _ { 0 } ^ { \infty } d r _ { 2 } \ r _ { 1 } ^ { v } r _ { 2 } ^ { u } e ^ { - \alpha r _ { 1 } - \beta r _ { 2 } } - \int _ { 0 } ^ { \infty } d r _ { 1 } \int _ { r _ { 1 } } ^ { \infty } d r _ { 2 } \ r _ { 1 } ^ { v } r _ { 2 } ^ { u } e ^ { - \alpha r _ { 1 } - \beta r _ { 2 } } } } \\ { { \displaystyle \ = L _ { - v } ( \alpha ) L _ { - u } ( \beta ) - I _ { R } ^ { 2 } ( v , u ) . } } \end{array}
$$

When both $\boldsymbol { v }$ and $u$ are negative integers, we should examine the behavior of $L _ { - v } ( \alpha ) L _ { - u } ( \beta )$ as $\epsilon _ { \alpha } \to 0$ and $\epsilon _ { \beta }  0$ . A detail analysis is given in Appendix A.

# B.Integral $I _ { R } ^ { 2 } ( v , u )$

For the case of $v \geq 0$ and $u \geq - 1$ , the integral $I _ { R } ^ { 2 } ( v , u )$ is regular and thus the order of the integration can be exchanged, yielding

$$
I _ { R } ^ { 2 } ( v , u ) = \frac 1 { v + 1 } \frac { s ! } { ( \alpha + \beta ) ^ { s + 1 } } { _ 2 F _ { 1 } } ( 1 , s + 1 ; v + 2 ; \frac \alpha { \alpha + \beta } ) .
$$

For other cases, see Appendix B for details. One can see from Eq. (B5) that Eq. (35) is valid for $s \geq 0$ and $u < 0$ . Also Eq.(35) is valid for any integer $u$ ， provided $v \geq 0$ and $s \geq 0$

For the case of $s < 0$ and $u \geq 0$ , the singular integral $I _ { R } ^ { 2 }$ can be expressed in the form

$$
I _ { R } ^ { 2 } ( v , u ) = \frac { u ! } { \beta ^ { u + 1 } } \sum _ { k = 0 } ^ { u } \frac { \beta ^ { k } } { k ! } L _ { - ( v + k ) } ( \alpha + \beta ) , \quad s < 0 \mathrm { ~ a n d ~ } u \geq 0 .
$$

When $v \ < \ 0$ ， $u \ < \ 0$ ，and $s \ < \ 0$ ，we need to consider the singular integrals for some special values of $( \boldsymbol { v } , \boldsymbol { u } )$ . The following recursion relation can be established, see Eqs. (B7) and (B12):

$$
\begin{array} { l } { { I _ { R } ^ { 2 } ( v , - 1 ) = I _ { - v } ( \alpha , \beta ) , \quad u = - 1 } } \\ { { I _ { R } ^ { 2 } ( v , u ) = \displaystyle \frac { 1 } { - u - 1 } [ L _ { - s } ( \alpha + \beta ) - \beta I _ { R } ^ { 2 } ( v , u + 1 ) ] , \quad u \le - 2 } } \end{array}
$$

where $I _ { p } ( x , y )$ is the auxiliary function introduced by Harris et al. [1O] that is given in Appendix B.

# IV. DISCUSSION AND CONCLUSION

Using Mathematica, $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ can be calculated analytically according to Eqs. (8) and (18). Examples are given in Eqs. (C4)， (C8)， and (C12) of Appendix C for $I _ { 0 } ( - 1 , - 1 , - 3 ; \alpha , \beta ) , \ I _ { 0 } ( 0 , 0 , - 4 ; \alpha , \beta )$ and $I _ { 0 } ( 0 , 0 , - 5 ; \alpha , \beta )$ ， respectively. Let us consider （204号 $\Gamma _ { - 2 , 0 , 0 } ( 0 , \alpha , \beta ) , \Gamma _ { - 3 , 1 , 1 } ( 0 , \alpha , \beta )$ ,and $\Gamma _ { - 4 , 1 , 1 } ( 0 , \alpha , \beta )$ ： $\Gamma _ { - 2 , 0 , 0 } ( 0 , \alpha , \beta )$ and $\Gamma _ { - 3 , 1 , 1 } ( 0 , \alpha , \beta )$ can be directly obtained using Eqs. (13) and (23) of Ref. [10]. After taking differentiation using Eq. (15) of Ref. [10],we obtain

$$
{ \begin{array} { l } { \displaystyle _ { \perp } ( \alpha , \beta , \gamma ) = { \frac { 2 } { ( \beta + \gamma ) ^ { 3 } } } \left\{ { \frac { 1 } { \epsilon ^ { 2 } } } - { \frac { 2 \alpha } { \epsilon } } + { \frac { 3 \alpha ^ { 2 } - \beta \gamma } { 3 } } [ \psi ( 4 ) - \ln \epsilon ] \right\} + { \frac { 2 ( \alpha ^ { 2 } \beta + \alpha ^ { 2 } \gamma + \beta ^ { 2 } \gamma ) } { 3 ( \beta - \gamma ) ^ { 2 } ( \beta - \gamma ) ^ { 2 } } } = { \frac { \sqrt { ( \alpha + \beta ) ^ { 2 } + ( \alpha + \gamma ) ^ { 2 } } } { ( \beta - \gamma ) ^ { 2 } } } = { \frac { \sqrt { ( \alpha + \beta ) ^ { 2 } + ( \alpha + \gamma ) ^ { 2 } } } { ( \beta - \gamma ) ^ { 2 } } } = { \frac { \sqrt { ( \alpha + \beta ) ^ { 2 } + ( \alpha + \gamma ) ^ { 2 } } } { ( \beta - \gamma ) ^ { 2 } } } , } \\ { \displaystyle { \frac { 2 } { ( \beta - \gamma ) ^ { 3 } ( \beta + \gamma ) ^ { 3 } } } { \biggl [ } ( \alpha + \beta ) ^ { 2 } ( 4 \alpha \beta + \beta ^ { 2 } + 3 \gamma ^ { 2 } ) \gamma \ln ( \alpha + \beta ) - ( \alpha + \gamma ) ^ { 2 } ( 4 \alpha \gamma + \gamma ^ { 2 } + 1 ) { \biggr ] } = 0 } \end{array} }
$$

We thus have

$$
\begin{array} { r l r } & { } & { I _ { 0 } ( - 1 , - 1 , - 3 ; \alpha , \beta ) = \Gamma _ { - 2 , 0 , 0 } ( 0 , \alpha , \beta ) , } \\ & { } & { I _ { 0 } ( 0 , 0 , - 4 ; \alpha , \beta ) = \Gamma _ { - 3 , 1 , 1 } ( 0 , \alpha , \beta ) , } \\ & { } & { I _ { 0 } ( 0 , 0 , - 5 ; \alpha , \beta ) = \Gamma _ { - 4 , 1 , 1 } ( 0 , \alpha , \beta ) . } \end{array}
$$

For arbitrary integers $a$ and $b$ ， we can use the following formula

$$
\dot { \bf \Phi } _ { q } ( a , b , - 2 - n ; \alpha , \beta ) = \Gamma _ { - 1 - n , a + 1 , b + 1 } ( 0 , \alpha , \beta ) = ( - \frac { \partial } { \partial \alpha } ) ^ { a + 1 } ( - \frac { \partial } { \partial \beta } ) ^ { b + 1 } \Gamma _ { - 1 - n , 0 , 0 } ( 1 - \beta , \beta - 1 ) \mathrm { R e } ( 0 , \alpha , \beta ) 
$$

which can be evaluated analytically by using Mathematica. It is noted that the above expression is valid for both regular and singular integrals.

The formulas for singular integral $I _ { q } ( a , b , c ; \alpha , \beta )$ with $c \geq - 1$ have been presented in Sec. II. In order to compare with the formulas for $\Gamma _ { l , m , n } ( \alpha , \beta , 0 )$ ， we have derived $I _ { 0 } ( - 2 \mathrm { ~ - ~ }$ （204号 $n , - 1 , - 1 ; \alpha , \beta )$ ， $I _ { 0 } ( - 3 , - 2 , - 1 ; \alpha , \beta )$ ，and $I _ { 0 } ( - 3 , - 3 , - 1 ; \alpha , \beta )$ in Appendix C2. Results of $I _ { 0 } ( - 2 - n , - 1 , - 1 ; \alpha , \beta )$ with $n = 1 , 2 , 3$ are listed in Eqs. (C21)-(C23). It is easy to see the equivalence between $I _ { 0 } ( - 2 - n , - 1 , - 1 ; \alpha , \beta )$ and $\Gamma _ { - 1 - n , 0 , 0 } ( \alpha , \beta , 0 )$ . It is, however， not so obvious to find the equivalence between $\Gamma _ { - 2 , - 1 , 0 } ( \alpha , \beta , 0 )$ and $I _ { 0 } ( - 3 , - 2 , - 1 ; \alpha , \beta )$ ，as listed in Eq. (C27). Let us first use Eq. (35) of Ref. [10]

$$
\begin{array} { r l } & { \Gamma _ { - 2 , - 1 , 0 } ( \alpha , \beta , \gamma ) = [ \ln ( \beta + \gamma ) \epsilon - \psi ( 2 ) ] ^ { 2 } + 1 - \displaystyle \frac { \alpha - \gamma } { \gamma } \mathrm { d i l o g } \left( \displaystyle \frac { \alpha + \beta } { \beta + \gamma } \right) - \frac { \pi ^ { 2 } } { 6 } \frac { \alpha } { \gamma } } \\ & { \qquad - \displaystyle \frac { \alpha + \gamma } { \gamma } \left[ \frac { 1 } { 2 } \ln ^ { 2 } \left( \displaystyle \frac { \alpha + \gamma } { \beta + \gamma } \right) + \mathrm { d i l o g } \left( \displaystyle \frac { \alpha + \beta } { \alpha + \gamma } \right) \right] . } \end{array}
$$

After taking the limit of $\gamma  0$ ， we obtain

$$
\begin{array} { l } { { \displaystyle \Gamma _ { - 2 , - 1 , 0 } ( \alpha , \beta , 0 ) = 1 + ( 1 - \gamma _ { E } ) ^ { 2 } + \frac { 2 \alpha } { \beta } \ln \frac \alpha { \alpha + \beta } + \frac 1 2 ( \ln \alpha + \ln \beta ) ^ { 2 } - \ln ^ { 2 } \alpha } } \\ { { \displaystyle ~ + ~ 2 \gamma _ { E } \ln \beta - \mathrm { d i l o g } \left( \frac { \alpha + \beta } { \alpha } \right) + \mathrm { d i l o g } \left( \frac { \alpha + \beta } { \beta } \right) + 2 [ - \psi ( 2 ) + \ln \beta ] \ln \epsilon + \ln ^ { 2 } \epsilon . } } \end{array}
$$

The above equation is the same as Eq. (C27) showing the equivalence of $\Gamma _ { - 2 , - 1 , 0 } ( \alpha , \beta , 0 )$ and $I _ { 0 } ( - 3 , - 2 , - 1 ; \alpha , \beta )$ ：

In the derivation of $I _ { 0 } ( - 3 , - 3 , - 1 ; \alpha , \beta )$ , we encounter an unexpected factor $\epsilon _ { \beta } / \epsilon _ { \alpha }$ ， see the last term of Eq. (C29). This factor comes from the function $L _ { - v } ( \alpha ) L _ { - u } ( \beta )$ where $v$ and $u$ are both negative, see Appendix A. The integral $I _ { 0 } ( - 3 , - 3 , - 1 ; \alpha , \beta )$ may have different results due to the fact that the expression of $\epsilon _ { \beta } / \epsilon _ { \alpha }$ can be randomly chosen as $\epsilon _ { \beta }$ and $\epsilon _ { \alpha }$ approach zero independently. However, $I _ { 0 } ( - 3 , - 3 , - 1 ; \alpha , \beta )$ should obey the following relation

$$
I _ { 0 } ( - 3 , - 2 , - 1 ; \alpha , \beta ) = - \frac { \partial } { \partial \beta } I _ { 0 } ( - 3 , - 3 , - 1 ; \alpha , \beta ) .
$$

Moreover, we can determine the expression of $\epsilon _ { \beta } / \epsilon _ { \alpha }$ from the equivalent relation of $I _ { 0 } ( - 3 , - 3 , - 1 ; \alpha , \beta )$ and $\Gamma _ { - 2 , - 2 , 0 } ( \alpha , \beta , 0 )$ . Letting $\gamma$ be zero in $\Gamma _ { - 2 , - 2 , 0 } ( \alpha , \beta , \gamma )$ of Eq. (B3) of Ref.[11], we have

$$
\begin{array} { l } { \displaystyle _ { 2 , 0 } ( \alpha , \beta , 0 ) = - ( \alpha + \beta ) [ \gamma _ { E } ^ { 2 } - 4 \gamma _ { E } + 6 + \ln \alpha \ln \beta - 4 \ln ( \alpha + \beta ) ] - 2 ( \alpha \ln \alpha + \beta \ln \alpha + \beta \ln \alpha ) } \\ { \displaystyle + ( \beta - \alpha ) \bigg [ \frac { 1 } { 2 } \ln ^ { 2 } \alpha + \mathrm { d i l o g } \left( \frac { \alpha + \beta } { \alpha } \right) \bigg ] + ( \alpha - \beta ) \bigg [ \frac { 1 } { 2 } \ln ^ { 2 } \beta + \mathrm { d i l o g } \left( \frac { \alpha + \beta } { \alpha } \right) \bigg ] } \\ { \displaystyle + \frac { 4 } { \epsilon } + 2 [ ( 2 - \gamma _ { E } ) ( \alpha + \beta ) - \alpha \ln \alpha - \beta \ln \beta ] \ln \epsilon - ( \alpha + \beta ) \ln ^ { 2 } \epsilon . } \end{array}
$$

Comparing Eq. (C29) and Eq. (47)，one can see that

$$
\frac { \epsilon _ { \beta } } { \epsilon _ { \alpha } } = - \frac { \alpha } { \beta } ,
$$

which can be applied to other singular integrals involving $L _ { - v } ( \alpha ) L _ { - u } ( \beta )$ ， see Eq. (34),with both $v$ and $u$ negative integers.

In conclusion, we have developed a general scheme of dealing with the singular integrals that appear in variational calculation of three-body Coulomb systems using Hylleraas coordinates. In this scheme, we first replace the lower limit of an integral by $\epsilon > 0$ and then check the behavior of the integral as $\epsilon  0$ . The regular part of the integral does not depend on $\epsilon$ and the singular part depends on $\epsilon$ . We then extend the formulas of $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ （204 from [12] to coincide with $\Gamma _ { l , m , n } ( \alpha , \beta , 0 )$ for both the singular and regular parts. Moreover, the singular integrals $I _ { q } ( a , b , c ; \alpha , \beta )$ with $c \geq - 1$ can be evaluated in the framework of Yan and Drake [2O]. It should be pointed out that the singular integrals $I _ { q } ( a , b , c ; \alpha , \beta )$ （204 with $c \geq - 1$ cannot be calculated through $\Gamma _ { l , m , n } ( \alpha , \beta , 0 )$ recursively. We have also verified Eq. (6) for $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta ) , I _ { 0 } ( - 2 - n , - 1 , - 1 ; \alpha , \beta ) , I _ { 0 } ( - 3 , - 2 , - 1 ; \alpha , \beta )$ ，and （204号 $I _ { 0 } ( - 3 , - 3 , - 1 ; \alpha , \beta )$ . In our scheme, all divergent terms that are proportional to either $\ln \epsilon$ （20 or $1 / \epsilon$ can simply be dropped, without using a singularity cancellation procedure. It is noted, however, there are some singular integrals that should be evaluated using $\Gamma _ { l , m , n } ( \alpha , \beta , 0 )$ , such as $I _ { 0 } ( - 3 , - 1 , - 2 ; \alpha , \beta )$ and $I _ { 0 } ( - 2 , - 1 , - 3 ; \alpha , \beta )$

# ACKNOWLEDGMENTS

The authors would like to thank Z.-C. Yan for helpful discussion and manuscript reading. This work has been supported by the National Natural Science Foundation of China (Grants Nos. 11474316 and 91636216) and the Strategic Priority Research Programme of the Chinese Academy of Sciences (Grant No. XDB21020200). Z.-X. Zhong is also supported by the YIPA program of Chinese Academy of Sciences.

# Appendix A: Function $L _ { p } ( x )$

The general definition of $L _ { p } ( x )$ is given by Eq. (13). For $p \leq 0$ ， it can be calculated according to Eq. (15). For positive integer $p$ , it can be recast to the form

$$
L _ { p } ( x ) = \frac { E _ { p } ( x \epsilon ) } { \epsilon ^ { p - 1 } } ,
$$

where $E _ { n } ( z )$ is the generalized exponential function (see 5.1.12 of Ref. [21]):

$$
E _ { n } ( z ) = ( - z ) ^ { n - 1 } { \frac { \psi ( n ) - \ln z } { ( n - 1 ) ! } } - \sum _ { m = 0 , m \neq n - 1 } ^ { \infty } { \frac { ( - z ) ^ { m } } { ( m - n + 1 ) m ! } } , \quad \arg z < \pi .
$$

Thus $L _ { p } ( x )$ can be written as

$$
L _ { p } ( x ) = ( - x ) ^ { p - 1 } \biggl [ \frac { \psi ( p ) - \ln ( x \epsilon ) } { ( p - 1 ) ! } + \sum _ { j = 1 } ^ { p - 1 } \frac { ( - x \epsilon ) ^ { - j } } { j ( p - j - 1 ) ! } - \sum _ { j = 1 } ^ { \infty } \frac { ( - x \epsilon ) ^ { j } } { j ( j + p - 1 ) ! } \biggr ] , \quad p > 1
$$

After taking the limit $\epsilon \to 0 ^ { + }$ , we can obtain Eq. (14).

Let us consider $L _ { m } ( x ) L _ { n } ( y )$ which may appear in the evaluation of $I _ { R } ^ { 1 } ( v , u )$ , see Eq. (34). It is easy to obtain an analytical result when at least one of $m , n$ is negative. When both （204号 $m$ and $n$ are positive integers, some special terms appear in $L _ { m } ( x ) L _ { n } ( y )$ such as $\epsilon _ { x } \ln \epsilon _ { y }$ and （204 $\epsilon _ { x } / \epsilon _ { y }$ . In our study, we found that the ratio $\epsilon _ { x } / \epsilon _ { y } = g ( x , y )$ where $g ( x , y )$ is a function of （20 $x$ and $y$ . Therefore,special terms of the type $\epsilon _ { x } \ln \epsilon _ { y } = g ( x , y ) \epsilon _ { y } \ln \epsilon _ { y }$ are deduced to be zero as $\epsilon _ { x }  0$ and $\epsilon _ { y }  0$ . On the other hand, the expression of $\epsilon _ { x } / \epsilon _ { y }$ remains unclear for $L _ { m } ( x ) L _ { n } ( y )$ itself and it can only be determined by properties of referred singular integrals （204号 $I _ { q } ( a , b , c ; \alpha , \beta )$ . Subsequently, the explicit formula of $\epsilon _ { y } / \epsilon _ { x }$ is determined as $- x / y$ as $\epsilon _ { x }$ and （20 $\epsilon _ { y }$ independently approach zero, see Eq. (48). When $m = n = 1$ ， we have

$$
( x ) L _ { 1 } ( y ) = \left[ \psi ( 1 ) - \ln x - \ln \epsilon _ { x } - \sum _ { k = 1 } ^ { \infty } { \frac { ( - x \epsilon _ { x } ) ^ { k } } { k ( k ) ! } } \right] \left[ \psi ( 1 ) - \ln y - \ln \epsilon _ { y } - \sum _ { k = 1 } ^ { \infty } { \frac { ( - y \epsilon _ { y } ) ^ { k - 1 } } { k ( k ) } } \right] \left[ \psi ( 1 ) - \ln \psi _ { k } \right] ,
$$

After taking the limit $\epsilon  0$ and keeping nonvanishing terms,we obtain

$$
L _ { 1 } ( x ) L _ { 1 } ( y ) = [ \psi ( 1 ) - \ln x - \ln \epsilon _ { x } ] [ \psi ( 1 ) - \ln y - \ln \epsilon _ { y } ] .
$$

When $m = 2$ and $n = 1$ ， we have

$$
\begin{array} { l } { \displaystyle ( y ) = ( - x ) \bigg [ \psi ( 2 ) - \ln x - \ln \epsilon _ { x } - \frac { 1 } { x \epsilon _ { x } } - \sum _ { k = 1 } ^ { \infty } \frac { ( - x \epsilon _ { x } ) ^ { k } } { k ( k ) ! } \bigg ] \bigg [ \psi ( 1 ) - \ln y - \ln \epsilon _ { y } - \sum _ { k = 1 } ^ { \infty } \frac { ( - x \epsilon _ { x } ) ^ { k } } { k ( k ) ! } \bigg ] } \\ { = ( - x ) [ \psi ( 2 ) - \ln x - \ln \epsilon _ { x } ] [ \psi ( 1 ) - \ln y - \ln \epsilon _ { y } ] + \frac { \epsilon _ { y } } { \epsilon _ { x } } y + \frac { 1 } { \epsilon _ { x } } [ \psi ( 1 ) - \ln y ] . } \end{array}
$$

For arbitrary $m$ and $n$ ， we can evaluate $L _ { m } ( x ) L _ { n } ( y )$ in a similar way.

# Appendix B: Integral $I _ { R } ^ { 2 } ( v , u )$

We can perform the integration over $r _ { 2 }$ first for Eq. (27). When $u \geq 0$ ， let us consider the integral

$$
I _ { u } = \int _ { r _ { 1 } } ^ { \infty } r _ { 2 } ^ { u } e ^ { - \beta r _ { 2 } } d r _ { 2 } = \frac { \Gamma ( u + 1 , \beta r _ { 1 } ) } { \beta ^ { u + 1 } } = \frac { u ! } { \beta ^ { u + 1 } } e ^ { - \beta r _ { 1 } } \sum _ { k = 0 } ^ { u } \frac { ( \beta r _ { 1 } ) ^ { k } } { k ! } , \quad u \geq 0
$$

where we have used the incomplete gamma function, see 8.4.8 of Ref. [22]. Now $I _ { R } ^ { 2 }$ with $u \geq 0$ can be expressed as

$$
\begin{array} { l } { { \displaystyle I _ { R } ^ { 2 } ( v , u ) = \frac { u ! } { \beta ^ { u + 1 } } \int _ { \epsilon } ^ { \infty } r _ { 1 } ^ { v } \sum _ { k = 0 } ^ { u } \frac { ( \beta r _ { 1 } ) ^ { k } } { k ! } e ^ { - ( \alpha + \beta ) r _ { 1 } } d r _ { 1 } } } \\ { { \displaystyle ~ = \frac { u ! } { \beta ^ { u + 1 } } \sum _ { k = 0 } ^ { u } \frac { \beta ^ { k } } { k ! } L _ { - ( v + k ) } ( \alpha + \beta ) , \quad u \ge 0 . } } \end{array}
$$

For $u < 0$ , the integral $I _ { u }$ is finite and can be expressed in the form

$$
I _ { u } = r _ { 1 } ^ { u + 1 } E _ { - u } ( \beta r _ { 1 } ) , \quad u < 0 .
$$

Inserting $I _ { u }$ into Eq. (27) yields

$$
I _ { R } ^ { 2 } ( v , u ) = \int _ { 0 } ^ { \infty } r _ { 1 } ^ { s } e ^ { - \alpha r _ { 1 } } E _ { - u } ( \beta r _ { 1 } ) d r _ { 1 } , \quad u < 0
$$

with $s = v + u + 1$ . For the case of $s \geq 0$ , the integral can be reduced to

$$
I _ { R } ^ { 2 } ( v , u ) = \frac { 1 } { v + 1 } \frac { s ! } { ( \alpha + \beta ) ^ { s + 1 } } { } _ { } ^ { 2 } F _ { 1 } ( 1 , s + 1 ; v + 2 ; \frac { \alpha } { \alpha + \beta } ) , \quad s \geq 0 \mathrm { ~ a n d ~ } u < 0 .
$$

When $s < 0$ and $u < 0$ ， the integral $I _ { R } ^ { 2 }$ becomes singular. In practical applications, we only need to consider a few values of $( \boldsymbol { v } , \boldsymbol { u } )$ . Using the following recursion for $E _ { n }$ (see 5.1.14 of Ref. [21])

$$
E _ { n + 1 } ( z ) = \frac { 1 } { n } [ e ^ { - z } - z E _ { n } ( z ) ] , \quad n = 1 , 2 , 3 , \ldots
$$

and inserting it into Eq. (B4), we can derive the following formulas for $I _ { R } ^ { 2 }$ （204号

1. $v = - n , u = - 1$ （204号

In this case, $s = - n = - 1 , - 2 , - 3 , . . .$ and the integral has been considered in Ref. [10], i.e.,

$$
I _ { R } ^ { 2 } ( - n , - 1 ) = I _ { n } ( \alpha , \beta ) , \quad n = 1 , 2 , 3 , . . .
$$

where

$$
I _ { p } ( x , y ) = \int _ { \epsilon } ^ { \infty } { \frac { e ^ { - x t } } { t ^ { p } } } E _ { 1 } ( y t ) d t ,
$$

and it can be evaluated recursively according to

$$
I _ { 1 } ( x , y ) = \frac { 1 } { 2 } \biggl ( \gamma _ { E } ^ { 2 } - \frac { \pi ^ { 2 } } { 6 } + \ln ^ { 2 } \epsilon - \ln ^ { 2 } x \biggr ) + \gamma _ { E } ( \ln y + \ln \epsilon ) + ( \ln x + \ln \epsilon ) \ln y - \mathrm { d i l o } ,
$$

$$
I _ { p } ( x , y ) = \frac { e ^ { - x \epsilon } E _ { 1 } ( y \epsilon ) } { ( p - 1 ) \epsilon ^ { p - 1 } } - \frac { x } { p - 1 } I _ { p - 1 } ( x , y ) - \frac { 1 } { p - 1 } L _ { p } ( x + y ) .
$$

2. （ $v = - n , u \leq - 2$ （204号

When $u = - 2$ ， $I _ { R } ^ { 2 }$ can be expressed using Eq. (B6)

$$
\begin{array} { l l l } { \displaystyle I _ { R } ^ { 2 } ( - n , - 2 ) = \int _ { 0 } ^ { \infty } r _ { 1 } ^ { s } e ^ { - \alpha r _ { 1 } } [ e ^ { - \beta r _ { 1 } } - \beta r _ { 1 } E _ { 1 } ( \beta r _ { 1 } ) ] d r _ { 1 } } \\ { \displaystyle \qquad = L _ { - s } ( \alpha + \beta ) - \beta I _ { R } ^ { 2 } ( - n , - 1 ) , \quad n \ge 0 . } \end{array}
$$

Applying the recursion relation for $E _ { n } ( z )$ ， we can build a recursion relation for $I _ { R } ^ { 2 }$ ，i.e.,

$$
I _ { R } ^ { 2 } ( - n , - m - 1 ) = \frac { 1 } { m } [ L _ { - s } ( \alpha + \beta ) - \beta I _ { R } ^ { 2 } ( - n , - m ) ] , \quad m , n = 1 , 2 , 3 , \dots
$$

Appendix C:Analytical expressions for some special singular integrals

1． $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$

In this subsection， we will consider $I _ { 0 } ( a , b , - 2 - n ; \alpha , \beta )$ for some special values of $a$ ， $b$ ， and $n$ . For $a = b = - 1$ and $n = 1$ ， $O _ { 1 }$ ， $O _ { 2 }$ ,and $O _ { 3 }$ in Eq. (8) are

$$
\begin{array} { l } { \displaystyle { { \cal O } _ { 1 } = - \frac { \ln \alpha - \ln \beta } { \alpha - \beta } \mathrm { , } } } \\ { \displaystyle { { \cal O } _ { 2 } = - \frac { \ln \beta + \ln \epsilon - \psi ( 2 ) } { \alpha + \beta } \mathrm { , } } } \\ { \displaystyle { { \cal O } _ { 3 } = - \frac { \ln \alpha + \ln \epsilon - \psi ( 2 ) } { \alpha + \beta } \mathrm { , } } } \end{array}
$$

and thus we have

$$
I _ { 0 } ( - 1 , - 1 , - 3 ; \alpha , \beta ) = \frac 2 { \alpha + \beta } [ \psi ( 2 ) - \ln \epsilon ] + \frac 2 { \alpha ^ { 2 } - \beta ^ { 2 } } ( \beta \ln \beta - \alpha \ln \alpha ) .
$$

For $a = b = 0$ and $n = 2$ ， $O _ { 1 }$ ， $O _ { 2 }$ ，and $O _ { 3 }$ are

$$
\begin{array} { l } { \displaystyle { { \cal O } _ { 1 } = \frac { 1 } { ( \alpha - \beta ) ^ { 2 } } - \frac { ( \alpha + \beta ) ( \ln \alpha - \ln \beta ) } { 2 ( \alpha - \beta ) ^ { 3 } } \ : , } } \\ { \displaystyle { { \cal O } _ { 2 } = \frac { \psi ( 1 ) - \ln \beta - \ln \epsilon } { 2 ( \alpha + \beta ) ^ { 2 } } - \frac { \beta [ \psi ( 2 ) - \ln \beta - \ln \epsilon ] } { ( \alpha + \beta ) ^ { 3 } } + \frac { 1 } { ( \alpha + \beta ) ^ { 3 } } \frac { 2 } { \epsilon } , } } \\ { \displaystyle { { \cal O } _ { 3 } = \frac { \psi ( 1 ) - \ln \alpha - \ln \epsilon } { 2 ( \alpha + \beta ) ^ { 2 } } - \frac { \alpha [ \psi ( 2 ) - \ln \alpha - \ln \epsilon ] } { ( \alpha + \beta ) ^ { 3 } } + \frac { 1 } { ( \alpha + \beta ) ^ { 3 } } \frac { 2 } { \epsilon } , } } \end{array}
$$

and thus we have

$$
{ } _ { 0 } ( 0 , 0 , - 4 ; \alpha , \beta ) = \frac { 4 } { ( \alpha + \beta ) ^ { 3 } \epsilon } + \frac { 4 \alpha \beta } { ( \alpha + \beta ) ^ { 2 } ( \alpha - \beta ) ^ { 2 } } + \frac { 4 \alpha \beta ( \alpha ^ { 2 } + \beta ^ { 2 } ) } { ( \alpha ^ { 2 } - \beta ^ { 2 } ) ^ { 2 } } ( \ln \beta - \ln \alpha ) .
$$

Finally, consider the case of $a = b = 0$ and $n = 3$ , the corresponding $O _ { 1 }$ ， $O _ { 2 }$ ，and $O _ { 3 }$ are

$$
\begin{array} { l } { \displaystyle { { \cal O } _ { 1 } = \frac { \beta ^ { 2 } - \alpha ^ { 2 } + 2 \alpha \beta ( \ln \alpha - \ln \beta ) } { 6 ( \alpha - \beta ) ^ { 3 } } , } } \\ { \displaystyle { { \cal O } _ { 2 } = \frac { \beta } { 6 ( \alpha + \beta ) ^ { 2 } } + \frac { \alpha \beta } { 3 ( \alpha + \beta ) ^ { 3 } } [ \ln \beta + \ln \epsilon - \psi ( 4 ) ] + \frac { \alpha - \beta } { 3 ( \alpha + \beta ) ^ { 3 } \epsilon } + \frac { 1 } { ( \alpha + \beta ) ^ { 3 } \epsilon ^ { 2 } } , } } \\ { \displaystyle { { \cal O } _ { 3 } = \frac { \alpha } { 6 ( \alpha + \beta ) ^ { 2 } } + \frac { \alpha \beta } { 3 ( \alpha + \beta ) ^ { 3 } } [ \ln \alpha + \ln \epsilon - \psi ( 4 ) ] + \frac { \beta - \alpha } { 3 ( \alpha + \beta ) ^ { 3 } \epsilon } + \frac { 1 } { ( \alpha + \beta ) ^ { 3 } \epsilon ^ { 2 } } , } } \end{array}
$$

and thus we have

$$
\begin{array} { c } { { \tiny { \widehat { \mathfrak { \iota } } } ( 0 , 0 , - 5 ; \alpha , \beta ) = \displaystyle \frac { 2 \alpha \beta } { 3 ( \alpha ^ { 2 } - \beta ^ { 2 } ) ^ { 3 } } \bigg [ ( \alpha ^ { 3 } + 3 \alpha \beta ^ { 2 } ) \ln \alpha - ( \beta ^ { 3 } + 3 \alpha ^ { 2 } \beta ) \ln \beta + ( \alpha - \beta ) ^ { 3 } \ln \beta \ln \beta \bigg ] , } } \\ { { - \displaystyle \frac { 2 \alpha \beta } { 3 ( \alpha - \beta ) ^ { 2 } ( \alpha + \beta ) } - \displaystyle \frac { 2 \alpha \beta } { 3 ( \alpha + \beta ) ^ { 3 } } \psi ( 4 ) + \displaystyle \frac { 2 } { ( \alpha + \beta ) ^ { 3 } \epsilon ^ { 2 } } . } } \end{array}
$$

2. $I _ { 0 } ( - 2 - n , b , c ; \alpha , \beta )$ ， $I _ { 0 } ( - 3 , - 2 , - 1 ; \alpha , \beta )$ ，and $I _ { 0 } ( - 3 , - 3 , - 1 ; \alpha , \beta )$

Let us consider $I _ { 0 } ( - 2 \mathrm { ~ - ~ } n , b , c ; \alpha , \beta )$ for $b = c = - 1$ and $n = 1 , 2 , 3$ .One can find that $\mathcal { L } _ { 2 } = 0$ and subsequently $k = 0$ . Furthermore, the coefficient $C _ { c q k }$ is thus reduced to （204号 $C _ { - 1 0 0 } = 1$ . The integral $I _ { 0 }$ of Eq. (21) can be expressed as

$$
I _ { 0 } ( - 2 - n , - 1 , - 1 ; \alpha , \beta ) = 2 I _ { R } ( - 2 - n , - 1 , - 1 ; \alpha , \beta ; 0 , 0 ) .
$$

Here we list $I _ { R } ^ { 2 } ( v , u )$ for some special values of $( \boldsymbol { v } , \boldsymbol { u } )$ according to Eq. (36):

$$
\begin{array} { r l } & { \mathcal { L } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( - 1 , 1 ) - \frac { 1 } { 2 } | \mathcal { S } | \mathcal { S } | \mathcal { S } - \mathrm { h } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( \phi ) - \mathrm { h } _ { \mathrm { Q } } ^ { \mathrm { i n } } | , } \\ & { \mathcal { L } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( - 2 , 1 ) = \frac { 1 } { 3 } - \frac { \alpha - \beta } { 2 } \left( \phi ^ { 2 } \right) - \mathrm { h } _ { \mathrm { Q } } \left( \phi ^ { 2 } \right) - \mathcal { L } _ { \mathrm { Q } } \left( - \phi \right) - \mathrm { h } _ { \mathrm { Q } } | , } \\ & { \mathcal { L } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( \frac { 1 } { 3 } , 1 ) - \frac { 1 } { 2 } \frac { \alpha - \beta } { 2 } \left( \frac { \alpha - \beta } { 2 } + \frac { \beta } { 2 } \right) ^ { 2 } , } \\ & { \mathcal { L } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( \frac { 1 } { 3 } , 1 ) - \frac { 1 } { 2 } \frac { \alpha - \beta } { 2 } \frac { \beta + 2 } { 3 } \left( \mathrm { h } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( \phi ) - \mathrm { h } _ { \mathrm { Q } } ^ { \mathrm { i n } } \right) , \quad \mathrm { h e t } \quad \frac { \mathrm { Q } } { \mathrm { Q } } ^ { \mathrm { i n } } , \quad \mathrm { h e t } \quad \mathrm { Q } } \\ & { \mathcal { L } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( - 1 , 1 ) - \frac { 1 } { 2 } \frac { \alpha + \beta } { 2 } \frac { \beta + 2 } { 3 } \left( \mathrm { h } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( \phi ) - \mathrm { h } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( \phi ) - \mathrm { h } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( \phi ) - \mathrm { h } _ { \mathrm { Q } } \right) } \\ & { \qquad + \frac { ( \alpha + \beta ) ^ { 2 } } { 2 } \left( \mathrm { h } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( \phi ) - \mathrm { h } _ { \mathrm { Q } } \right) - \mathrm { h } _ { \mathrm { Q } } \left( - \frac { \beta } { 2 } \right) - \mathrm { h } _ { \mathrm { Q } } \left( \mathrm { h } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( \phi ) - \mathrm { h } _ { \mathrm { Q } } \right) } \\ &  \mathcal { L } _ { \mathrm { Q } } ^ { \mathrm { i n } } ( - 4 , 1 ) = \frac { 1 } { 2 } \frac { \beta + 2 }  \end{array}
$$

Inserting Eq.(34) into Eq. (25), the integral $I _ { R }$ can be written as

$$
I _ { R } ( a , b , c ; \alpha , \beta ; q , k ) = L _ { - v } ( \alpha ) L _ { - u } ( \beta ) - I _ { R } ^ { 2 } ( v , u ) + I _ { R } ^ { 2 } ( v ^ { \prime } , u ^ { \prime } ) .
$$

Using the explicit formulas of $I _ { R } ^ { 2 } ( v , u )$ and $L _ { p } ( x )$ from Eqs. (15） and (14)，we obtain the following expressions:

$$
\begin{array} { l } { { \displaystyle { \cal I } _ { 0 } ( - 3 , - 1 , - 1 ; \alpha , \beta ) = \displaystyle \frac { 2 } { \beta } [ \psi ( 2 ) - \ln \epsilon ] + \displaystyle \frac { 2 } { \beta ^ { 2 } } [ \alpha \ln \alpha - ( \alpha + \beta ) \ln ( \alpha + \beta ) ] \ : , } } \\ { { \displaystyle { \cal I } _ { 0 } ( - 4 , - 1 , - 1 ; \alpha , \beta ) = \displaystyle \frac { 1 } { \beta } \left\{ \displaystyle \frac { 2 } { \epsilon } - ( 2 \alpha + \beta ) [ \psi ( 3 ) - \ln \epsilon ] \right\} } } \\ { { \displaystyle ~ + \displaystyle \frac { 1 } { \beta ^ { 2 } } [ ( \alpha + \beta ) ^ { 2 } \ln ( \alpha + \beta ) - \alpha ^ { 2 } \ln \alpha ] \ : , } } \\ { { \displaystyle { \cal I } _ { 0 } ( - 5 , - 1 , - 1 ; \alpha , \beta ) = \displaystyle \frac { 1 } { \beta } \left\{ \displaystyle \frac { 1 } { \epsilon ^ { 2 } } - \frac { 2 \alpha + \beta } { \epsilon } + \left( \alpha ^ { 2 } + \alpha \beta + \displaystyle \frac { \beta ^ { 2 } } { 3 } \right) [ \psi ( 4 ) - \ln \epsilon ] \right\} } } \\ { { \displaystyle ~ + \displaystyle \frac { 1 } { 3 \beta ^ { 2 } } [ \alpha ^ { 3 } \ln \alpha - ( \alpha + \beta ) ^ { 3 } \ln ( \alpha + \beta ) ] \ : . } } \end{array}
$$

For $I _ { 0 } ( - 3 , - 2 , - 1 ; \alpha , \beta )$ where $s = - 1$ , it can be written as

$$
I _ { 0 } ( - 3 , - 2 , - 1 ; \alpha , \beta ) = 2 [ I _ { R } ^ { 1 } ( - 2 , 0 ) + I _ { R } ^ { 2 } ( - 1 , - 1 ) ]
$$

with

$$
\begin{array} { l } { { \displaystyle I _ { R } ^ { 1 } ( - 2 , 0 ) = L _ { 2 } ( \alpha ) L _ { 0 } ( \beta ) - I _ { R } ^ { 2 } ( - 2 , 0 ) = \frac 1 \beta [ L _ { 2 } ( \alpha ) - L _ { 2 } ( \alpha + \beta ) ] , } } \\ { { \displaystyle I _ { R } ^ { 2 } ( - 1 , - 2 ) = I _ { 1 } ( \alpha , \beta ) . } } \end{array}
$$

By using Eqs. (A3) and (B9)，we finally obtain the following expression

$$
{ \begin{array} { r l } & { 3 , - 2 , - 1 ; \alpha , \beta ) = 1 + ( 1 - \gamma _ { E } ) ^ { 2 } + { \frac { 2 \alpha } { \beta } } \ln { \frac { \alpha } { \alpha + \beta } } + { \frac { 1 } { 2 } } ( \ln \alpha + \ln \beta ) ^ { 2 } - \ln ^ { 2 } \alpha } \\ & { \qquad + \ 2 \gamma _ { E } \ln \beta - \operatorname { d i l o g } \left( { \frac { \alpha + \beta } { \alpha } } \right) + \operatorname { d i l o g } \left( { \frac { \alpha + \beta } { \beta } } \right) + 2 [ - \psi ( 2 ) + \ln \beta ] . } \end{array} }
$$

Finally we consider $I _ { 0 } ( - 3 , - 3 , - 1 ; \alpha , \beta )$ where $s = - 2$ . This integral can be expressed in terms of $L _ { p } ( x )$ and $I _ { p } ( x , y )$

$$
I _ { 0 } ( - 3 , - 3 , - 1 ) = 2 [ L _ { 2 } ( \alpha ) L _ { 1 } ( \beta ) - I _ { 2 } ( \alpha , \beta ) + L _ { 2 } ( \alpha + \beta ) - \beta I _ { 1 } ( \alpha , \beta ) ] .
$$

By using Eqs. (A3), (A6), (B9), and (B10), $I _ { 0 } ( - 3 , - 3 , - 1 ; \alpha , \beta )$ can be simplified to

$$
\begin{array} { l } { { 3 , - 3 , - 1 ; \alpha , \beta ) = - ( \alpha + \beta ) [ \gamma _ { E } ^ { 2 } - 4 \gamma _ { E } + 6 + \ln \alpha \ln \beta - 4 \ln ( \alpha + \beta ) ] - 2 ( \alpha \ln \alpha + \beta ) , } } \\ { { \phantom { 3 , - 3 , - 1 ; \alpha , \beta } } } \\ { { \phantom { 3 , - 3 , - 1 ; \alpha , \beta } + ( \beta - \alpha ) \biggl [ \displaystyle \frac { 1 } { 2 } \ln ^ { 2 } \alpha + \mathrm { d i l o g } \left( \displaystyle \frac { \alpha + \beta } { \alpha } \right) \biggr ] + ( \alpha - \beta ) \biggl [ \displaystyle \frac { 1 } { 2 } \ln ^ { 2 } \beta + \mathrm { d i l o g } \left( \displaystyle \frac { \alpha + \beta } { \alpha } \right) \biggr ] - \beta ( \beta - \beta ) \biggr [ \displaystyle \frac { 1 } { 2 } \ln ^ { 2 } \beta + \mathrm { d i l o g } \left( \displaystyle \frac { \alpha + \beta } { \alpha } \right) \biggr ] , } } \\ { { \phantom { 3 , - 3 , - 1 } + \displaystyle \frac { 4 } { \epsilon } + 2 [ ( 2 - \gamma _ { E } ) ( \alpha + \beta ) - \alpha \ln \alpha - \beta \ln \beta ] \ln \epsilon - ( \alpha + \beta ) \ln ^ { 2 } \epsilon , } } \\ { { \phantom { 3 , - 3 , - 1 } + 2 \alpha + 2 \displaystyle \frac { \epsilon _ { \beta } } { \epsilon _ { \alpha } } \beta , } } \end{array}
$$

where we have used the following property of the dialogarithm function:

$$
\mathrm { d i l o g } \left( \frac { x + y } { x } \right) + \mathrm { d i l o g } \left( \frac { x + y } { y } \right) = - \frac { 1 } { 2 } \ln ^ { 2 } \frac { x } { y } - \frac { \pi ^ { 2 } } { 6 } .
$$

[1] K. Pachucki, V. c. v. Patkos, and V. A. Yerokhin, Phys. Rev. A 95,062510 (2017).   
[2] X. Zheng, Y.R. Sun, J.-J. Chen, W. Jiang,K. Pachucki， and S.-M. Hu, Phys. Rev. Lett.   
118, 063001 (2017).   
[3] V. I. Korobov,L. Hilico， and J.-P. Karr,Phys. Rev. Lett.118, 233001 (2017).   
[4] V.I. Korobov, L. Hilico，and J.-P. Karr,Phys. Rev. Lett.112,103003 (014).   
[5] G. W. F. Drake, Phys. Rev. A 18, 820 (1978).   
[6] V. I. Korobov, Phys. Rev. A 61,064503 (2000).   
[7] V. I. Korobov, Phys. Rev. A 77, 042506 (2008).   
[8] V. I. Korobov, Phys. Rev. A 74, 052506 (2006).   
[9] V. I. Korobov, Journal of Physics B: Atomic, Molecular and Optical Physics 35,1959 (2002).   
[10] F.E. Harris,A.M. Frolov， and V.H. Smith, The Journal of Chemical Physics 121,6323 (2004).   
[11] V. I. Korobov, Phys. Rev. A 85, 042514 (2012).   
[12] Z.-C. Yan and G. W. F. Drake, Candian Journal of Physics 72, 822 (1994).   
[13] G. W. Drake, Canadian Journal of Physics 80,1195 (2002), https://doi.org/10.1139/p02-111.   
[14] H. Li, J. Wu, B.-L. Zhou, J.-M. Zhu,and Z.-C. Yan, Phys. Rev. A 75, 012504 (2007).   
[15] Y. Ning and Z.-C. Yan, Phys. Rev. A 90, 032516 (2014).   
[16] Z.-X. Zhong, Z.-C. Yan, and T.-Y. Shi, Phys. Rev. A 79, 064502 (2009).   
[17] Z.-X. Zhong, P.-P. Zhang, Z.-C. Yan, and T.-Y. Shi, Phys. Rev. A 86, 064502 (2012).   
[18] P.-P. Zhang, Z.-X. Zhong, Z.-C. Yan, and T.-Y. Shi, Phys. Rev. A 93, 032507 (2016).   
[19] M.-H. Hu, S.-M. Yao, Y. Wang, W. Li, Y.-Y. Gu, and Z.-X. Zhong, Chemical Physics Letters 654,114 (2016).   
[20] Z.-C. Yan and G. Drake, Chemical Physics Letters 259, 96 (1996).   
[21] M. Abramowitz and I. A. Stegun, eds., Handbook of Mathematical Functions: with Formulas, Graphs,and Mathematical Tables (Dover, New York, 1972).   
[22] F.W. J. Olver, D.W. Lozier，R. F. Bosivert， and C. W. Clark, eds.， NIST Handbook of Mathematical Functions (NIST and Cambridge University Press, 2010).