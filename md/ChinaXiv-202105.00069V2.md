# Copositivity for a class of fourth order symmetric tensors given by scalar dark matter

Yisheng Song\* Xudong Lit June 11,2021

Abstract. In this paper, we mainly discuss the copositivity of 4th order symmetric tensor defined by scalar dark matter stable under a $\mathbb { Z } _ { 3 }$ discrete group，and obtain an analytically necessary and sufficient condition of the copositivity of such a class of tensors. Furthermore, this analytic expression may be used to verify the vacuum stability for $\mathbb { Z } _ { 3 }$ scalar dark matter.

Key Words and Phrases: Homogeneous polynomial, Copositive tensors,symmetric,4th order Tensors.

2010 AMS Subject Classification: 90C23，15A63， 81T32,  
70S20，15A72

# 1 Introduction

In particle physics, the standard model of multiple real scalar fields or multiple microscopic particles potentials is fourth-degree homogeneous polynomial. It is well-known that a 4th-degree homogeneous polynomial has a one-to-one correspondence with a 4th order symmetric tensor. A physical example is given by scalar dark matter stable under a $\mathbb { Z } _ { 3 }$ discrete group ([2,3,23-25]). That is, the most general scalar potential of a Higgs $H _ { 1 }$ ，an inert doublet $H _ { 2 }$ and a complex singlet $S$ is

$$
V ( h _ { 1 } , h _ { 2 } , s ) = V ( \phi ) = \mathcal V \phi ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 3 } v _ { i j k l } \phi _ { i } \phi _ { j } \phi _ { k } \phi _ { l }
$$

where $\phi ~ = ~ ( \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 } ) ^ { T } ~ = ~ ( h _ { 1 } , h _ { 2 } , s ) ^ { T }$ ， $h _ { 1 } ~ = ~ | H _ { 1 } |$ ， $h _ { 2 } ~ = ~ | H _ { 2 } |$ ， $H _ { 2 } ^ { \dagger } H _ { 1 } \ =$ $h _ { 1 } h _ { 2 } \rho e ^ { i \phi }$ ， $S = s e ^ { i \phi _ { S } }$ ， $\mathcal { V } = \left( v _ { i j k l } \right)$ is a 4th order 3-dimensional real symmetric tensor. It is obvious that the vacuum stability for $\mathbb { Z } _ { 3 }$ scalar dark matter (that is, $V ( h _ { 1 } , h _ { 2 } , s ) \geq 0 )$ is really equivalent to the (strict） copositivity of the tensor $\boldsymbol { \nu } = \left( v _ { i j k l } \right)$ . The concepts of copositivity and positive definiteness of symmetric tensor were first introduced by Qi [32,33]. An $m$ th order （204号 $n$ -dimensional real tensor $\mathcal { A } = ( a _ { i _ { 1 } i _ { 2 } \dots i _ { m } } )$ is said to be

(i)(strictly） copositive if for all non-negative vector $x \in \mathbb { R } ^ { n }$ with $\| x \| = 1$ ，

$$
\mathcal { A } x ^ { m } = \sum _ { i _ { 1 } , \cdots , i _ { m } = 1 } ^ { n } a _ { i _ { 1 } i _ { 2 } \cdots i _ { m } } x _ { i _ { 1 } } x _ { i _ { 2 } } \cdot \cdot \cdot x _ { i _ { m } } \geq 0 \ ( > 0 ) ;
$$

(ii) semipositive (positive) definite if $A x ^ { m } \geq 0$ ( $> 0$ ）for all vector $x \in \mathbb { R } ^ { n }$ with $\| x \| = 1$ and an even number $m$ ：

Qi [33] proved a symmetric tensor is (strictly) copositive if each sum of a diagonal element and all the negative off-diagonal elements in the same row is (positive） nonegative. Subsequently， many good properties are studied for this class of tensors. Song-Qi [37] proposed a method to test the (strict) copositivity of symmetric tensors by using principal sub-tensors. Song-Qi [42] introduced the concepts of Pareto $H$ -eigenvalue and Pareto $Z$ -eigenvalue by means of Lagrange multipliers,and gave the relation between the Pareto $H$ -eigenvalue ( $Z$ -eigenvalue） and the (strict） copositivity of corresponding tensor. Song-Qi [4O] presented that a symmetric tensor is (strictly) copositive if and only if it is (strictly） semipositive. An mth order $n$ -dimensional real tensor $\mathcal { A } = ( a _ { i _ { 1 } i _ { 2 } \dots i _ { m } } )$ is called (strictly） semipositive if for each non-negative and non-zero vector $x$ ， there exists an index $k \in { 1 , 2 , \dots , n }$ such that

$$
x _ { k } > 0 \mathrm { ~ a n d ~ } ( \mathcal { A } x ^ { m - 1 } ) _ { k } \geq 0 \mathrm { ~ ( > 0 ) }
$$

This notion is firstly used by Song-Qi [38]. This kind of tensors has good properties and applications in the study of tensor complementary problem. Song-Qi [38] proved every strictly semi-positive tensor is a $Q$ -tensor. Furthermore,we can use it to explore the copositivity of tensors and its applicationS [39,43,45,47]. More details may be find in refs. [4-7,11,14,15,18,28,49-51] and others.

Besides, some alternative numerical algorithms for copositivity of tensors have been proposed. Chen-Huang-Qi [8] studied some basic theories of copositivity detection of symmetric tensor and presented corresponding numerical algorithms. Li-Zhang-Huang-Qi [26] proposed an SDP relaxation algorithm to test the copositivity of higher order tensors. The more numerical algorithms for checking copositivity of high order tensors were presented by Chen-Huang-Qi [9], Chen-Wang [1O]. For more details about copositivity algorithms, also see [30,34,36]. But these conclusions are not really specially designed for the 4th order symmetric tensor, and may not attain the analytic conditions required by the physical problems.

Recently, Song-Qi [41] and Liu-Song [27] respectively presented different sufficient conditions of copositivity. Song [46] presented the positive definiteness of 4th order symmetric tensor. Guo [16] showed a necessary and sufficient condition of a binary quartic form. Very recently, Qi-Song-Zhang [35] showed new necessary and sufficient conditions for quartic polynomial to be positive for all positive reals. Song-Qi [44] gave an analytic necessary and sufficient condition of positive definiteness of 4th order symmetric tensors defined in particle physics. However, the analytic necessary and sufficient conditions have not been obtained for copositivity.

In this paper，we work on seeking analytically checable necessary and sufficient condition for copositivity of 4th order symmetric tensor. Firstly, motivated by Qi-Song-Zhang's [35] result, we show a simple analytical expression of copositivity of 4th order 2-dimensional symmetric tensor. Furthermore，with the help of these conclusions, we discuss copositivity of a 4th order 3-dimensional symmetric tensor defined by vacuum stability for $\mathbb { Z } _ { 3 }$ （204号 scalar dark matter.

# 2 Preliminaries and Basic facts

It is well-known that both 2 $\times$ 2 matrix (Andersson-Chang-Elfving [1], Hadeler [17], Nadler [31]) and $3 \times 3$ matrix (Hadeler [17] and Chang-Sederberg [12])

have analytically copositive condition.

Lemma 2.1. $A$ real symmetric $2 \times 2$ matrix $A = \left( a _ { i j } \right)$ is (strictly） copositive if and only if

$$
a _ { 1 1 } \geq 0 ~ ( > 0 ) , a _ { 2 2 } \geq 0 ~ ( > 0 ) , a _ { 1 2 } + \sqrt { a _ { 1 1 } a _ { 2 2 } } \geq 0 ~ ( > 0 ) .
$$

$A$ real symmetric $3 \times 3$ matrix $A = \left( a _ { i j } \right)$ is (strictly） copositive if and only if

$$
\begin{array} { r l r } & { } & { a _ { 1 1 } \geq 0 \ ( > 0 ) , a _ { 2 2 } \geq 0 \ ( > 0 ) , a _ { 3 3 } \geq 0 \ ( > 0 ) , \alpha = a _ { 1 2 } + \sqrt { a _ { 1 1 } a _ { 2 2 } } \geq 0 \ ( > 0 ) , } \\ & { } & { \beta = a _ { 1 3 } + \sqrt { a _ { 1 1 } a _ { 3 3 } } \geq 0 \ ( > 0 ) , \gamma = a _ { 2 3 } + \sqrt { a _ { 3 3 } a _ { 2 2 } } \geq 0 \ ( > 0 ) , } \\ & { } & { a _ { 1 2 } \sqrt { a _ { 3 3 } } + a _ { 1 3 } \sqrt { a _ { 2 2 } } + a _ { 2 3 } \sqrt { a _ { 1 1 } } + \sqrt { a _ { 1 1 } a _ { 2 2 } a _ { 3 3 } } + \sqrt { 2 \alpha \beta \gamma } \geq 0 \ ( > 0 ) . } \end{array}
$$

The non-negativity of a quadratic polynomial with one variable are wellknown (also see Qi-Song-Zhang [35] for more details).

Lemma 2.2. Let $f ( t )$ be a quadratic polynomial with one variable and $a > 0$

$$
f ( t ) = a t ^ { 2 } + b t + c .
$$

Then $f ( t ) > 0 \ ( \geq 0 )$ for all $t \geq 0$ if and only if

$$
\left\{ \begin{array} { l l } { c > 0 \ ( \geq 0 ) , \quad } & { i f b \geq 0 } \\ { 4 a c - b ^ { 2 } > 0 \ ( \geq 0 ) , \quad } & { i f b < 0 . } \end{array} \right.
$$

The non-negativity of a quartic polynomial with one variable is showed by Ulrich-Watson [48] for all positive real numbers. Recently, Qi-Song-Zhang [35] reexpressed their conclusions.

Lemma 2.3. Let $f ( t )$ be a quartic polynomial with $a > 0$ and $e > 0$

$$
f ( t ) = a t ^ { 4 } + b t ^ { 3 } + c t ^ { 2 } + d t + e .
$$

Then $f ( t ) \geq 0$ for all $t > 0$ if and only if

# 3 Main Results

Let $\mathcal { A }$ be a 4th order 2-dimensional symmetric tensor. Then for a vector （20 $\boldsymbol { x } = ( x _ { 1 } , x _ { 2 } ) ^ { \top }$ ，

$$
\begin{array} { l } { { \displaystyle { \mathcal A } x ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 2 } a _ { i j k l } x _ { i } x _ { j } x _ { k } x _ { l } } } \\ { { \displaystyle \quad = a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 4 a _ { 1 1 1 2 } x _ { 1 } ^ { 3 } x _ { 2 } + 6 a _ { 1 1 2 2 } x _ { 1 } ^ { 2 } x _ { 2 } ^ { 2 } + 4 a _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 3 } + a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } } } \end{array}
$$

Next， we give the analytical expression of the copositivity of a 4th order 2-dimensional symmetric tensor.

Theorem 3.1. Let $\mathcal { A } = \left( a _ { i j k l } \right)$ be a 4th order 2-dimensional symmetric tensor with $a _ { 1 1 1 1 } > 0$ and $a _ { 2 2 2 2 } > 0$ . Then $\mathcal { A }$ is copositive if and only if

$$
I ^ { 3 } - 2 7 J ^ { 2 } \leq 0 , a _ { 1 2 2 2 } { \sqrt { a _ { 1 1 1 1 } } } + a _ { 1 1 1 2 } { \sqrt { a _ { 2 2 2 2 } } } > 0 ; o r
$$

$$
a _ { 1 2 2 2 } \geq 0 , a _ { 1 1 1 2 } \geq 0 , 3 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } \geq 0 ; o r
$$

$$
\begin{array} { r l } & { | a _ { 1 1 1 2 } \sqrt { a _ { 2 2 2 2 } } - a _ { 1 2 2 2 } \sqrt { a _ { 1 1 1 1 } } | \leq \sqrt { 6 a _ { 1 1 1 1 } a _ { 1 1 2 2 } a _ { 2 2 2 2 } + 2 a _ { 1 1 1 1 } a _ { 2 2 2 2 } \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } } } \\ & { ( i ) - \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } \leq 3 a _ { 1 1 2 2 } \leq 3 \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ; } \end{array}
$$

$$
a _ { 1 1 1 2 } \sqrt { a _ { 2 2 2 2 } } + a _ { 1 2 2 2 } \sqrt { a _ { 1 1 1 1 } } \ge - \sqrt { 6 a _ { 1 1 1 1 } a _ { 1 1 2 2 } a _ { 2 2 2 2 } - 2 a _ { 1 1 1 1 } a _ { 2 2 2 2 } \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } } ,
$$

$$
\begin{array} { r l } & { \mathrm { ~ \iota _ { - } ~ } \lnot _ { 1 1 1 1 } \mathrm { e } _ { 2 2 2 2 } \mathrm { ~ \iota _ { - } ~ } \ l _ { 1 1 1 2 } \mathrm { e } _ { 1 2 2 2 } \mathrm { ~ \iota _ { - } ~ } \ l _ { 1 } \circ \iota _ { 1 2 2 1 } , } \\ & { J = a _ { 1 1 1 1 } a _ { 1 1 2 2 } a _ { 2 2 2 2 } + 2 a _ { 1 1 1 2 } a _ { 1 1 2 2 } a _ { 1 2 2 2 } - a _ { 1 1 2 2 } ^ { 3 } - a _ { 1 1 1 1 } a _ { 1 2 2 2 } ^ { 2 } - a _ { 1 1 1 2 } ^ { 2 } a _ { 2 2 2 2 } . } \end{array}
$$

Proof. For $\boldsymbol { x } = ( x _ { 1 } , x _ { 2 } ) ^ { \top }$ with $x _ { i } \geq 0 ~ ( i = 1 , 2 )$ and $\| x \| = 1$ ， we have

$$
\mathcal { A } \ = x ^ { 4 } = a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 4 a _ { 1 1 1 2 } x _ { 1 } ^ { 3 } x _ { 2 } + 6 a _ { 1 1 2 2 } x _ { 1 } ^ { 2 } x _ { 2 } ^ { 2 } + 4 a _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 3 } + a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } .
$$

Obviously, $\mathcal { A } x ^ { 4 } = a _ { 2 2 2 2 } > 0$ if $x _ { 1 } = 0$ and $x _ { 2 } \neq 0$ ，and $\mathcal { A } x ^ { 4 } = a _ { 1 1 1 1 } > 0$ （20 if $x _ { 1 } \neq 0$ and $x _ { 2 } = 0$ . Suppose $x _ { 1 } \neq 0$ and $x _ { 2 } \neq 0$ ，we may rewritten the homogeneous polynomial $\boldsymbol { \mathcal { A } } \boldsymbol { x } ^ { 4 }$ ，

$$
\mathcal { A } \displaystyle x ^ { 4 } = x _ { 1 } ^ { 4 } ( a _ { 1 1 1 1 } + 4 a _ { 1 1 1 2 } \frac { x _ { 2 } } { x _ { 1 } } + 6 a _ { 1 1 2 2 } ( \frac { x _ { 2 } } { x _ { 1 } } ) ^ { 2 } + 4 a _ { 1 2 2 2 } ( \frac { x _ { 2 } } { x _ { 1 } } ) ^ { 3 } + a _ { 2 2 2 2 } ( \frac { x _ { 2 } } { x _ { 1 } } ) ^ { 4 } ) .
$$

Clearly, $A x ^ { 4 } \geq 0$ if and only if

$$
f ( t ) = a t ^ { 4 } + b t ^ { 3 } + c t ^ { 2 } + d t + e \geq 0 ,
$$

where $a = a _ { 2 2 2 2 }$ ， $b = 4 a _ { 1 2 2 2 }$ ， $c = 6 a _ { 1 1 2 2 }$ ， $d = 4 a _ { 1 1 1 2 }$ ， $e = a _ { 1 1 1 1 }$ ， $t = \frac { x _ { 2 } } { x _ { 1 } } > 0$ Then we have

$$
\begin{array} { r l } & { \Delta = 4 ( 1 2 a e - 3 b d + c ^ { 2 } ) ^ { 3 } - ( 7 2 a c e + 9 b c d - 2 c ^ { 3 } - 2 7 a d ^ { 2 } - 2 7 b ^ { 2 } e ) ^ { 2 } } \\ & { \quad = 4 ( 1 2 a _ { 1 1 1 1 } a _ { 2 2 2 2 } - 1 2 \times 4 a _ { 1 1 1 2 } a _ { 1 1 2 2 } + 1 2 \times 3 a _ { 1 2 2 2 } ^ { 2 } ) ^ { 3 } } \\ & { \quad \quad - ( 7 2 \times 6 a _ { 1 1 1 1 } a _ { 1 2 2 } a _ { 2 2 2 2 } + 7 2 \times 1 2 a _ { 1 1 2 } a _ { 1 1 2 2 } a _ { 1 2 2 2 } - 7 2 \times 6 a _ { 1 1 2 2 } ^ { 3 } } \\ & { \quad \quad - 7 2 \times 6 a _ { 1 1 2 1 } ^ { 2 } a _ { 2 2 2 2 } - 7 2 \times 6 a _ { 1 1 1 } a _ { 1 1 2 2 } ^ { 2 } ) ^ { 2 } } \\ & { \quad = 4 \times 1 2 ^ { 3 } ( a _ { 1 1 1 1 } a _ { 2 2 2 2 } - 4 a _ { 1 1 1 2 } a _ { 1 1 2 2 } + 3 a _ { 1 2 2 2 } ^ { 2 } ) ^ { 3 } } \\ & { \quad \quad - 7 2 ^ { 2 } \times 6 ^ { 2 } ( a _ { 1 1 1 1 } a _ { 1 1 2 2 } a _ { 2 2 2 2 } + 2 a _ { 1 1 1 2 } a _ { 1 1 2 2 } a _ { 1 2 2 2 } - a _ { 1 1 2 2 } ^ { 3 } - a _ { 1 1 1 2 } ^ { 2 } a _ { 2 2 2 2 } - a _ { 1 1 1 } a _ { 1 1 2 } ^ { 2 } . } \\ & { \quad = 4 \times 1 2 ^ { 3 } ( I ^ { 3 } - 2 7 J ^ { 2 } ) , } \end{array}
$$

and so, the discriminant $\Delta$ and $I ^ { 3 } - 2 7 J ^ { 3 }$ have the same sign. Then the conclusion may be obtained by Lemma 2.3 □

Now we consider the copositivity of 4th order 3-dimensional symmetric tensor given by scalar dark matter stable under a $\mathbb { Z } _ { 3 }$ discrete group（ [2,3, 23-25]). The most general scalar quartic potential of the SM Higgs $H _ { 1 }$ ，an inert doublet $H _ { 2 }$ ，and a complex singlet $S$ can be written as

$$
\begin{array} { l } { { V ( h _ { 1 } , h _ { 2 } , s ) = \lambda _ { 1 } | H _ { 1 } | ^ { 4 } + \lambda _ { 2 } | H _ { 2 } | ^ { 4 } + \lambda _ { 3 } | H _ { 1 } | ^ { 2 } | H _ { 2 } | ^ { 2 } + \lambda _ { 4 } ( H _ { 1 } ^ { \dagger } H _ { 2 } ) ( H _ { 2 } ^ { \dagger } H _ { 1 } ) } } \\ { { \ + \lambda _ { S } | S | ^ { 4 } + \lambda _ { S 1 } | S | ^ { 2 } | H _ { 1 } | ^ { 2 } + \lambda _ { S 2 } | S | ^ { 2 } | H _ { 2 } | ^ { 2 } } } \\ { { \ \ \qquad + { \frac { 1 } { 2 } } ( \lambda _ { S 1 2 } S ^ { 2 } H _ { 1 } ^ { \dagger } H _ { 2 } + \lambda _ { S 1 2 } ^ { * } S ^ { \dagger 2 } H _ { 2 } ^ { \dagger } H _ { 1 } ) } } \\ { { \ = \lambda _ { 1 } h _ { 1 } ^ { 4 } + \lambda _ { 2 } h _ { 2 } ^ { 4 } + \lambda _ { 3 } h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } + \lambda _ { 4 } \rho ^ { 2 } h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } } } \\ { { \ \qquad + \lambda _ { S } s ^ { 4 } + \lambda _ { S 1 } s ^ { 2 } h _ { 1 } ^ { 2 } + \lambda _ { S 2 } s ^ { 2 } h _ { 2 } ^ { 2 } - | \lambda _ { S 1 2 } | \rho s ^ { 2 } h _ { 1 } h _ { 2 } , } } \end{array}
$$

where $h _ { 1 } = | H _ { 1 } |$ ， $h _ { 2 } = | H _ { 2 } |$ ， $H _ { 1 } ^ { \dagger } H _ { 2 } = h _ { 1 } h _ { 2 } \rho e ^ { i \phi }$ ， $S = s e ^ { i \phi _ { S } }$ ， $\lambda _ { S 1 2 } = - | \lambda _ { S 1 2 } |$ ， $| \rho | \in [ 0 , 1 ]$ is the orbit space parameter. Without loss of generality, assuming that $h _ { 1 } ^ { 2 } + h _ { 2 } ^ { 2 } + s ^ { 2 } = 1$ in the sequel.

Theorem 3.2. Let ${ { \lambda } _ { 1 } } ~ > ~ 0$ ， ${ \lambda } _ { 2 } ~ > ~ 0$ ， $\lambda _ { S } ~ > ~ 0$ and $\begin{array} { r } { \rho _ { 0 } ~ = ~ \frac { | \lambda _ { S 1 2 } | s ^ { 2 } } { 2 \lambda _ { 4 } h _ { 1 } h _ { 2 } } } \end{array}$ Then $V ( h _ { 1 } , h _ { 2 } , s ) ~ \geq ~ 0 ~ ( > ~ 0 )$ for all $h _ { 1 } \ \geq \ 0$ ， $h _ { 2 } ~ \geq ~ 0$ ， $s \geq 0$ if and only if $\lambda _ { S 2 } + 2 \sqrt { \lambda _ { 2 } \lambda _ { S } } \ge 0 \ ( > 0 )$ ， $\lambda _ { S 1 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { S } } \ge 0 \ ( > 0 )$ and

$$
\left\{ \begin{array} { l l } { \lambda _ { 3 } + \lambda _ { 4 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } } \geq 0 ( > 0 ) , } & { V _ { \rho = 1 } ( h _ { 1 } , h _ { 2 } , s ) \geq 0 ( > 0 ) , \ i f \lambda _ { 4 } \leq 0 } \\ { \lambda _ { 3 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } } \geq 0 ( > 0 ) , } & { V _ { \rho = \rho _ { 0 } } ( h _ { 1 } , h _ { 2 } , s ) \geq 0 ( > 0 ) , \ i f \lambda _ { 4 } > 0 . } \end{array} \right.
$$

Proof. It is obvious that $V ( h _ { 1 } , 0 , 0 ) = \lambda _ { 1 } > 0$ ， $V ( 0 , h _ { 2 } , 0 ) = \lambda _ { 2 } > 0 , V ( 0 , 0 , s ) =$ （204号 $\lambda _ { S } > 0$ and

$$
V ( 0 , h _ { 2 } , s ) = \lambda _ { 2 } h _ { 2 } ^ { 4 } + \lambda _ { S } s ^ { 4 } + \lambda _ { S 2 } h _ { 2 } ^ { 2 } s ^ { 2 } = \left( h _ { 2 } ^ { 2 } s ^ { 2 } \right) \left( \begin{array} { c c } { { \lambda _ { 2 } } } & { { \frac 1 2 \lambda _ { S 2 } } } \\ { { \frac 1 2 \lambda _ { S 2 } } } & { { \lambda _ { S } } } \end{array} \right) \left( { h _ { 2 } ^ { 2 } } \right) .
$$

It follows from Lemma 2.1 that

$$
V ( 0 , h _ { 2 } , s ) \geq 0 \ ( > 0 ) \ \mathrm { i f \ a n d \ o n l y \ i f \ } \lambda _ { S 2 } + 2 \sqrt { \lambda _ { 2 } \lambda _ { S } } \geq 0 \ ( > 0 ) .
$$

Similarly, we also have

$$
V ( h _ { 1 } , 0 , s ) \geq 0 \ ( > 0 ) \ \mathrm { i f ~ a n d ~ o n l y ~ i f ~ } \lambda _ { S 1 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { S } } \geq 0 \ ( > 0 ) ,
$$

$$
V ( h _ { 1 } , h _ { 2 } , 0 ) \geq 0 \ ( > 0 ) \ \mathrm { i f ~ a n d ~ o n l y ~ i f ~ } \lambda _ { 3 } + \lambda _ { 4 } \rho ^ { 2 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } } \geq 0 \ ( > 0 ) .
$$

Since $| \rho | \in [ 0 , 1 ]$ , the function $f ( \rho ) = \lambda _ { 3 } + \lambda _ { 4 } \rho ^ { 2 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } }$ reaches its minimum value at $\rho = 0$ (if $\lambda _ { 4 } > 0$ )， $\rho = 1$ (if $\lambda _ { 4 } \leq 0$ )，and hence,

$$
\begin{array} { r } { V ( h _ { 1 } , h _ { 2 } , 0 ) \geq 0 \ ( > 0 ) \ \mathrm { i f ~ a n d ~ o n l y ~ i f ~ } \lambda _ { 3 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } } \geq 0 \ ( > 0 ) \ } \\ { \lambda _ { 3 } + \lambda _ { 4 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } } \geq 0 \ ( > 0 ) . \ } \end{array}
$$

For $h _ { 1 } > 0$ ， $h _ { 2 } > 0$ ， $s > 0$ ，we consider the function $g ( \rho ) = V ( h _ { 1 } , h _ { 2 } , s )$ about one variable $\rho$ ， which is a quadratic function. Clearly,

$$
\frac { d g ( \rho ) } { d \rho } = 2 \lambda _ { 4 } \rho h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } - | \lambda _ { S 1 2 } | s ^ { 2 } h _ { 1 } h _ { 2 } ,
$$

and so, the function $g ( \rho )$ has a unique extremum value at $\begin{array} { r } { \rho _ { 0 } = \frac { | \lambda _ { S 1 2 } | s ^ { 2 } } { 2 \lambda _ { 4 } h _ { 1 } h _ { 2 } } } \end{array}$

If $\lambda _ { 4 } > 0$ , then $g ( \rho )$ reaches its minimum value at 2Ahih2,and hence, $V ( h _ { 1 } , h _ { 2 } , s ) \geq 0$ is now equivalent to $g ( \rho _ { 0 } ) \ge 0$ . When $\lambda _ { 4 } \leq 0$ ， $g ( \rho )$ reaches its minimum value at $\rho = 1$ ,and by that time, $V ( h _ { 1 } , h _ { 2 } , s ) \geq 0$ if and only if （204号 $g ( 1 ) \geq 0$ . This completes the proof.

Let $x = ( x _ { 1 } , x _ { 2 } , x _ { 3 } ) ^ { \prime } = ( h _ { 1 } , h _ { 2 } , s ) ^ { \prime } $ and

$$
\begin{array} { r l } & { v _ { 1 1 1 1 } = \lambda _ { 1 } , v _ { 2 2 2 2 } = \lambda _ { 2 } , v _ { 3 3 3 3 } = \lambda _ { S } , v _ { 1 1 2 2 } = \cfrac { 1 } { 6 } ( \lambda _ { 3 } + \lambda _ { 4 } ) , v _ { 1 1 3 3 } = \cfrac { 1 } { 6 } \lambda _ { S 1 } , } \\ & { v _ { 2 2 3 3 } = \cfrac { 1 } { 6 } \lambda _ { S 2 } , v _ { 1 2 3 3 } = - \cfrac { 1 } { 1 2 } | \lambda _ { S 1 2 } | , v _ { i j k l } = 0 \mathrm { ~ f o r ~ o t h e r s } . } \end{array}
$$

Then $\mathcal { V } = \left( v _ { i j k l } \right)$ is a 4th order 3-dimensional symmetric tensor and $g ( 1 ) =$ $V _ { \rho = 1 } ( h _ { 1 } , h _ { 2 } , s ) = \mathcal { V } x ^ { 4 }$ , and so, the inequality $V _ { \rho = 1 } ( h _ { 1 } , h _ { 2 } , s ) \geq 0$ is equivalent to the copositivity of $\nu$ . By the special structure of $\nu$ , we now give a necessary and suffcient condition for its copositivity. Let

$$
\begin{array} { r l } & { \lambda _ { 4 0 } = 4 \lambda _ { S } \lambda _ { 1 } - \lambda _ { S 1 } ^ { 2 } , ~ \lambda _ { 0 4 } = 4 \lambda _ { S } \lambda _ { 2 } - \lambda _ { S 2 } ^ { 2 } , } \\ & { \lambda _ { 1 3 } = 2 \lambda _ { S 2 } | \lambda _ { S 1 2 } | , ~ \lambda _ { 3 1 } = 2 \lambda _ { S 1 } | \lambda _ { S 1 2 } | , } \\ & { \lambda _ { 2 2 } = 4 \lambda _ { S } \lambda _ { 3 } + 4 \lambda _ { S } \lambda _ { 4 } - | \lambda _ { S 1 2 } | ^ { 2 } - 2 \lambda _ { S 1 } \lambda _ { S 2 } , } \\ & { ~ \Delta = 4 ( 1 2 \lambda _ { 4 0 } \lambda _ { 0 4 } - 3 \lambda _ { 3 1 } \lambda _ { 1 3 } + \lambda _ { 2 2 } ) ^ { 3 } } \\ & { ~ - \left( 7 2 \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } + 9 \lambda _ { 3 1 } \lambda _ { 2 2 } \lambda _ { 1 3 } - 2 \lambda _ { 2 2 } ^ { 3 } - 2 7 \lambda _ { 4 0 } \lambda _ { 1 3 } ^ { 2 } - 2 7 \lambda _ { 3 1 } ^ { 2 } \lambda _ { 0 4 } \right) ^ { 2 } . } \end{array}
$$

Theorem 3.3. Let $\mathcal { V } = \left( v _ { i j k l } \right)$ given by (7) with $\lambda _ { 1 } > 0$ ， $\lambda _ { 2 } > 0$ ， $\lambda _ { S } > 0$ ： Then $\nu$ is copositive if and only if

$$
\begin{array} { r } { ( I ) ~ \lambda _ { S 1 } \geq 0 , ~ \lambda _ { S 2 } \geq 0 , ~ 2 \sqrt { \lambda _ { S 1 } \lambda _ { S 2 } } \geq | \lambda _ { S 1 2 } | , ~ \lambda _ { 3 } + \lambda _ { 4 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } } \geq 0 . } \end{array}
$$

①△≤ $0 , \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } + \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } > 0$ ，or

$$
\begin{array} { r l } & { \textcircled { 2 } \Delta \geq 0 , | \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } - \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } | \leq 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } + 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } , } \\ & { \quad ( i ) - 2 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } \leq \lambda _ { 2 2 } \leq 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } ; } \\ & { \quad ( i i ) \lambda _ { 2 2 } > 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } , } \\ & { \quad \quad \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } + \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } \geq - 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } - 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } . } \end{array}
$$

Proof. Rewritten the equation as follows,

$$
\mathcal { V } x ^ { 4 } = V ( h _ { 1 } , h _ { 2 } , s ) = \lambda _ { S } t ^ { 2 } + M ( h _ { 1 } , h _ { 2 } ) t + \widetilde { V } ( h _ { 1 } , h _ { 2 } ) ,
$$

where t = s²,

$$
\begin{array} { r l r } & { } & { M ( h _ { 1 } , h _ { 2 } ) = \lambda _ { S 1 } h _ { 1 } ^ { 2 } + \lambda _ { S 2 } h _ { 2 } ^ { 2 } - \vert \lambda _ { S 1 2 } \vert h _ { 1 } h _ { 2 } , } \\ & { } & { \widetilde { V } ( h _ { 1 } , h _ { 2 } ) = \lambda _ { 1 } h _ { 1 } ^ { 4 } + \lambda _ { 2 } h _ { 2 } ^ { 4 } + ( \lambda _ { 3 } + \lambda _ { 4 } ) h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } . } \end{array}
$$

Then $\nu x ^ { 4 }$ can be seen as a one-variable quadratic polynomial about $t$ ，and hence, it follows from Lemma 2.2 that $\nu$ is copositive if and only if

$$
M ( h _ { 1 } , h _ { 2 } ) \geq 0 , \widetilde { V } ( h _ { 1 } , h _ { 2 } ) \geq 0 ,
$$

$$
M ( h _ { 1 } , h _ { 2 } ) < 0 , 4 \lambda _ { S } \widetilde { V } ( h _ { 1 } , h _ { 2 } ) - ( M ( h _ { 1 } , h _ { 2 } ) ) ^ { 2 } \geq 0 .
$$

Case(1). Clearly, both $M ( h _ { 1 } , h _ { 2 } )$ and $\widetilde { V } ( h _ { 1 } , h _ { 2 } )$ are two quadratic form with coefficient matrices

$$
\left( \begin{array} { c c } { { \lambda _ { S 1 } } } & { { - \frac { 1 } { 2 } | \lambda _ { S 1 2 } | } } \\ { { - \frac { 1 } { 2 } | \lambda _ { S 1 2 } | } } & { { \lambda _ { S 2 } } } \end{array} \right) \mathrm { ~ a n d ~ } \left( \begin{array} { c c } { { \lambda _ { 1 } } } & { { \frac { 1 } { 2 } ( \lambda _ { 3 } + \lambda _ { 4 } ) } } \\ { { \frac { 1 } { 2 } ( \lambda _ { 3 } + \lambda _ { 4 } ) } } & { { \lambda _ { 2 } } } \end{array} \right) ,
$$

and so, it follows from Lemma 2.1 that $M ( h _ { 1 } , h _ { 2 } ) \geq 0$ and $\widetilde { V } ( h _ { 1 } , h _ { 2 } ) \geq 0$ are respectively equivalent to

$$
\lambda _ { S 1 } \geq 0 , \ \lambda _ { S 2 } \geq 0 , \ - | \lambda _ { S 1 2 } | + 2 \sqrt { \lambda _ { S 1 } \lambda _ { S 2 } } \geq 0 \ \mathrm { a n d } \ \lambda _ { 3 } + \lambda _ { 4 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } } \geq 0 .
$$

Case (2). Obviously, $M ( h _ { 1 } , h _ { 2 } ) < 0$ is equivalent to the strict copositivity of $- M ( h _ { 1 } , h _ { 2 } )$ ,and then, $M ( h _ { 1 } , h _ { 2 } ) < 0$ if and only if

$$
\lambda _ { S 1 } < 0 , \ \lambda _ { S 2 } < 0 , \ | \lambda _ { S 1 2 } | + 2 \sqrt { \lambda _ { S 1 } \lambda _ { S 2 } } > 0 .
$$

It is always tenable that $| \lambda _ { S 1 2 } | + 2 \sqrt { \lambda _ { S 1 } \lambda _ { S 2 } } > 0$ ,and hence, $M ( h _ { 1 } , h _ { 2 } ) < 0$ if and only if

$$
\lambda _ { S 1 } < 0 , \lambda _ { S 2 } < 0 .
$$

Now we prove $4 \lambda _ { S } \widetilde { V } ( h _ { 1 } , h _ { 2 } ) - ( M ( h _ { 1 } , h _ { 2 } ) ) ^ { 2 } \ge 0$ ，which is rewritten as follow,

$$
\begin{array} { r l } & { 4 \lambda _ { S } \widetilde { V } ( h _ { 1 } , h _ { 2 } ) - ( M ( h _ { 1 } , h _ { 2 } ) ) ^ { 2 } = 4 \lambda _ { S } ( \lambda _ { 1 } h _ { 1 } ^ { 4 } + \lambda _ { 2 } h _ { 2 } ^ { 4 } + ( \lambda _ { 3 } + \lambda _ { 4 } ) h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } ) } \\ & { \quad \quad \quad - ( \lambda _ { S 1 } h _ { 1 } ^ { 2 } + \lambda _ { S 2 } h _ { 2 } ^ { 2 } - | \lambda _ { S 1 2 } | h _ { 1 } h _ { 2 } ) ^ { 2 } } \\ & { \quad \quad \quad = ( 4 \lambda _ { S } \lambda _ { 1 } - \lambda _ { S 1 } ^ { 2 } ) h _ { 1 } ^ { 4 } + 2 \lambda _ { S 1 } | \lambda _ { S 1 2 } | h _ { 1 } ^ { 3 } h _ { 2 } } \\ & { \quad \quad \quad \quad + ( 4 \lambda _ { S } \lambda _ { 3 } + 4 \lambda _ { S } \lambda _ { 4 } - | \lambda _ { S 1 2 } | ^ { 2 } - 2 \lambda _ { S 1 } \lambda _ { S 2 } ) h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } } \\ & { \quad \quad \quad \quad + 2 \lambda _ { S 2 } | \lambda _ { S 1 2 } | h _ { 1 } h _ { 2 } ^ { 3 } + ( 4 \lambda _ { S } \lambda _ { 2 } - \lambda _ { S 2 } ^ { 2 } ) h _ { 2 } ^ { 4 } } \\ & { \quad \quad \quad = \lambda _ { 4 0 } h _ { 1 } ^ { 4 } + \lambda _ { 3 1 } h _ { 1 } ^ { 3 } h _ { 2 } + \lambda _ { 2 2 } h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } + \lambda _ { 1 3 } h _ { 1 } h _ { 2 } ^ { 3 } + \lambda _ { 0 4 } h _ { 2 } ^ { 4 } . } \end{array}
$$

So,this obtain a 4th order 2-dimensional symmetric tensor $\mathcal { A } = \left( a _ { i j k l } \right)$ with

$$
a _ { 1 1 1 1 } = \lambda _ { 4 0 } , ~ a _ { 2 2 2 2 } = \lambda _ { 0 4 } , ~ a _ { 1 1 1 2 } = \frac { 1 } { 4 } \lambda _ { 3 1 } , ~ a _ { 1 1 2 2 } = \frac { 1 } { 6 } \lambda _ { 2 2 } , ~ a _ { 1 2 2 2 } = \frac { 1 } { 4 } \lambda _ { 1 3 } ,
$$

and then, by Theorem 3.1, we have,

②入13≥0, $\lambda _ { 3 1 } \geq 0$ ， $\lambda _ { 2 2 } + 2 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } \geq 0$ ，or

$$
\begin{array} { r l r } {  { \textcircled { 3 } \Delta \geq 0 , | \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } - \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } | \leq 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } + 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } , } } \\ & { } & { \mathrm { ( i ) } - 2 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } \leq \lambda _ { 2 2 } \leq 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } ; } \\ & { } & { \mathrm { ( i i ) } \lambda _ { 2 2 } > 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } , } \\ & { } & { \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } + \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } \geq - 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } - 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } . } \end{array}
$$

As $\lambda _ { S 1 } < 0$ and $\lambda _ { S 2 } < 0$ , there will be no the inequalities $\lambda _ { 1 3 } = 2 \lambda _ { S 1 } | \lambda _ { S 1 2 } | \geq 0$ and $\lambda _ { 3 1 } = 2 \lambda _ { S 2 } | \lambda _ { S 1 2 } | \geq 0$ , and then, the above conditions $\textcircled{1}$ and $\textcircled{3}$ guarantee that $4 \lambda _ { S } \widetilde { V } ( h _ { 1 } , h _ { 2 } ) - ( M ( h _ { 1 } , h _ { 2 } ) ) ^ { 2 } \geq 0$ . This complete the proof. □

Now we show the necessary and sufficient conditions of $V _ { \rho = \rho _ { 0 } } ( h _ { 1 } , h _ { 2 } , s ) =$ （20 $g ( \rho _ { 0 } ) \ge 0$ ：

Theorem 3.4.Let λ1 >0,λ2 >0,λs>0,λ4 >0 and p=s12 Then $V _ { \rho = \rho _ { 0 } } ( h _ { 1 } , h _ { 2 } , s ) \geq 0$ if and only if

$$
\begin{array} { r l } & { 4 \lambda _ { 4 } \lambda _ { S } - | \lambda _ { S 1 2 } | ^ { 2 } \geq 0 , \alpha = \lambda _ { 3 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } } \geq 0 , } \\ & { \beta = \lambda _ { S 1 } + 2 \sqrt { \lambda _ { 1 } ( \lambda _ { S } - \frac { | \lambda _ { S 1 2 } | ^ { 2 } } { 4 \lambda _ { 4 } } ) } \geq 0 , \gamma = \lambda _ { S 2 } + 2 \sqrt { \lambda _ { 2 } ( \lambda _ { S } - \frac { | \lambda _ { S 1 2 } | ^ { 2 } } { 4 \lambda _ { 4 } } ) } \geq 0 , } \\ & { \lambda _ { 3 } \sqrt { \lambda _ { S } - \frac { | \lambda _ { S 1 2 } | ^ { 2 } } { 4 \lambda _ { 4 } } } + \lambda _ { S 1 } \sqrt { \lambda _ { 2 } } + \lambda _ { S 2 } \sqrt { \lambda _ { 1 } } + \sqrt { \alpha \beta \gamma } \geq 0 . } \end{array}
$$

Proof. We plug $\rho _ { 0 } = \frac { | \lambda _ { S 1 2 } | s ^ { 2 } } { 2 \lambda _ { 4 } h _ { 1 } h _ { 2 } }$ into the equation (3)

$$
\begin{array} { l } { { V _ { \rho = \rho _ { 0 } } ( h _ { 1 } , h _ { 2 } , s ) = \lambda _ { 1 } h _ { 1 } ^ { 4 } + \lambda _ { 2 } h _ { 2 } ^ { 4 } + \lambda _ { S } s ^ { 4 } + \displaystyle \frac { | \lambda _ { S 1 2 } | ^ { 2 } } { 4 \lambda _ { 4 } } s ^ { 4 } - \displaystyle \frac { | \lambda _ { S 1 2 } | ^ { 2 } } { 2 \lambda _ { 4 } } s ^ { 4 } } } \\ { { \displaystyle ~ + \lambda _ { 3 } h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } + \lambda _ { S 1 } s ^ { 2 } h _ { 1 } ^ { 2 } + \lambda _ { S 2 } s ^ { 2 } h _ { 2 } ^ { 2 } } } \\ { { \displaystyle ~ = \lambda _ { 1 } h _ { 1 } ^ { 4 } + \lambda _ { 2 } h _ { 2 } ^ { 4 } + ( \lambda _ { S } - \frac { | \lambda _ { S 1 2 } | ^ { 2 } } { 4 \lambda _ { 4 } } ) s ^ { 4 } } } \\ { { \displaystyle ~ + \lambda _ { 3 } h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } + \lambda _ { S 1 } s ^ { 2 } h _ { 1 } ^ { 2 } + \lambda _ { S 2 } s ^ { 2 } h _ { 2 } ^ { 2 } } . } \end{array}
$$

Then $V _ { \rho = \rho _ { 0 } } ( h _ { 1 } , h _ { 2 } , s )$ may be seen as a quadratic form about $( h _ { 1 } ^ { 2 } , h _ { 2 } ^ { 2 } , s ^ { 2 } )$ with the coefficient matrix

$$
\left( \begin{array} { c c c } { { \lambda _ { 1 } } } & { { \frac { 1 } { 2 } \lambda _ { 3 } } } & { { \frac { 1 } { 2 } \lambda _ { S 1 } } } \\ { { \frac { 1 } { 2 } \lambda _ { 3 } } } & { { \lambda _ { 2 } } } & { { \frac { 1 } { 2 } \lambda _ { S 2 } } } \\ { { \frac { 1 } { 2 } \lambda _ { S 1 } } } & { { \frac { 1 } { 2 } \lambda _ { S 2 } } } & { { \lambda _ { S } - \frac { | \lambda _ { S 1 2 } | ^ { 2 } } { 4 \lambda _ { 4 } } } } \end{array} \right) .
$$

Therefore, $V _ { \rho = \rho _ { 0 } } ( h _ { 1 } , h _ { 2 } , s ) \geq 0$ is equivalent to the copositivity of the above coefficient matrix, and hence,after making simple calculations, the desired conclusions directly follow from Lemma 2.1. □

In summary, we obtain an analytical necessary and sufficient condition of copositivity for a special 4th order 3-dimensional symmetric tensor defined by vacuum stability for $\mathbb { Z } _ { 3 }$ scalar dark matter.

Theorem 3.5. Let $V ( h _ { 1 } , h _ { 2 } , s )$ be given by (3) with $\lambda _ { 1 } > 0$ ， $\lambda _ { 2 } > 0$ ， $\lambda _ { S } > 0$ Then $V ( h _ { 1 } , h _ { 2 } , s ) \geq 0$ if and only if $\lambda _ { S 2 } + 2 \sqrt { \lambda _ { 2 } \lambda _ { S } } \ge 0$ ， $\lambda _ { S 1 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { S } } \ge 0$ （204 and

$$
\begin{array} { r l } & { \textup {  { j } } \lambda _ { 4 } > 0 , ~ 4 \lambda _ { 4 } \lambda _ { S } - | \lambda _ { S 1 2 } | ^ { 2 } \geq 0 , ~ \alpha = \lambda _ { 3 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } } \geq 0 , } \\ & { \beta = \lambda _ { S 1 } + 2 \sqrt { \lambda _ { 1 } ( \lambda _ { S } - \frac { | \lambda _ { S 1 2 } | ^ { 2 } } { 4 \lambda _ { 4 } } ) } \geq 0 , ~ \gamma = \lambda _ { S 2 } + 2 \sqrt { \lambda _ { 2 } ( \lambda _ { S } - \frac { | \lambda _ { S 1 2 } | ^ { 2 } } { 4 \lambda _ { 4 } } ) } \geq 0 , } \\ & { \lambda _ { 3 } \sqrt { \lambda _ { S } - \frac { | \lambda _ { S 1 2 } | ^ { 2 } } { 4 \lambda _ { 4 } } } + \lambda _ { S 1 } \sqrt { \lambda _ { 2 } } + \lambda _ { S 2 } \sqrt { \lambda _ { 1 } } + \sqrt { \alpha \beta \gamma } \geq 0 . } \end{array}
$$

(I) $\lambda _ { 4 } \leq 0$ $\lambda _ { 3 } + \lambda _ { 4 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } } \ge 0$ and

（2） $\lambda _ { S 1 } < 0$ ${ } _ { 1 } < 0 , \lambda _ { S 2 } < 0 , 4 \lambda _ { S } \lambda _ { 2 } - \lambda _ { S 2 } ^ { 2 } > 0 , 4 \lambda _ { S } \lambda _ { 1 } - \lambda _ { S 1 } ^ { 2 } > 0$ and

$$
\begin{array} { r l } & { \mathbb { O } \Delta \leq 0 , \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } + \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } > 0 , } \\ & { \mathbb { Q } \Delta \geq 0 , | \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } - \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } | \leq 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } + 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } , } \\ & { \quad ( i ) - 2 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } \leq \lambda _ { 2 2 } \leq 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } ; } \\ & { \quad ( i i ) \lambda _ { 2 2 } > 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } , } \\ & { \quad \quad \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } + \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } \geq - 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } - 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } . } \end{array}
$$

Remark 3.1. An analytically necessary and sufficient conditions of copositivity for a class of special 4th order 3-dimensional symmetric tensors is proved, but the analytical expression of its strict copositivity doesn't still know. Then for a general 4th order 3-dimension symmetric real tensor, how to obtain its analytical expressions of (strict) copositivity.

Remark 3.2. For three Higgs doublets with equal electroweak quantum numbers $\phi _ { i }$ ， $i = 1 , 2 , 3$ ，the Higgs potential model can construct the following form [13,19-22,29],

$$
\begin{array} { l } { { V = - { \displaystyle \frac { M _ { 0 } } { \sqrt 3 } } ( \phi _ { 1 } ^ { * } \phi _ { 1 } + \phi _ { 2 } ^ { * } \phi _ { 2 } + \phi _ { 3 } ^ { * } \phi _ { 3 } ) + { \displaystyle \frac { \Lambda _ { 0 } } { 3 } } ( \phi _ { 1 } ^ { * } \phi _ { 1 } + \phi _ { 2 } ^ { * } \phi _ { 2 } + \phi _ { 3 } ^ { * } \phi _ { 3 } ) ^ { 2 } } } \\ { { + { \displaystyle \frac { \Lambda _ { 3 } } { 3 } } \left[ ( \phi _ { 1 } ^ { * } \phi _ { 1 } ) ^ { 2 } + ( \phi _ { 2 } ^ { * } \phi _ { 2 } ) ^ { 2 } + ( \phi _ { 3 } ^ { * } \phi _ { 3 } ) ^ { 2 } - ( \phi _ { 1 } ^ { * } \phi _ { 1 } ) ( \phi _ { 2 } ^ { * } \phi _ { 2 } ) - ( \phi _ { 1 } ^ { * } \phi _ { 1 } ) ( \phi _ { 3 } ^ { * } \phi _ { 3 } ) - ( \phi _ { 2 } ^ { * } \phi _ { 2 } ) \right] } } \\  { + { \displaystyle \Lambda _ { 1 } \left[ ( R e \phi _ { 1 } ^ { * } \phi _ { 2 } ) ^ { 2 } + ( R e \phi _ { 2 } ^ { * } \phi _ { 3 } ) ^ { 2 } + ( R e \phi _ { 3 } ^ { * } \phi _ { 1 } ) ^ { 2 } \right] } } \\ { { + { \displaystyle \Lambda _ { 2 } \left[ ( I m \phi _ { 1 } ^ { * } \phi _ { 2 } ) ^ { 2 } + ( I m \phi _ { 2 } ^ { * } \phi _ { 3 } ) ^ { 2 } + ( I m \phi _ { 3 } ^ { * } \phi _ { 1 } ) ^ { 2 } \right] } } } \\  { + { \displaystyle \Lambda _ { 4 } \left[ ( R e \phi _ { 1 } ^ { * } \phi _ { 2 } ) ( I m \phi _ { 1 } ^ { * } \phi _ { 2 } ) + ( R e \phi _ { 2 } ^ { * } \phi _ { 3 } ) ( I m \phi _ { 2 } ^ { * } \phi _ { 3 } ) + ( R e \phi _ { 3 } ^ { * } \phi _ { 1 } ) ( I m \phi _ { 3 } ^ { * } \phi _ { 1 } ) \right] } . } \end{array}
$$

Then how to solue the analytically necessary and sufficient conditions of the boundedness from below of the above model (or $V \geq 0$ ） is a topic worthy of study and practical significance. It may be seen as a 4th order 3-dimensional symmetric tensors， and so， this problem is converted into a problem that solving positive definiteness (or copositivity) of the corresponding tensor.

# References

[1] Andersson, L.E., Chang, G., Elfving, T.: Criteria for copositive matrices using simplices and barycentric coordinates, Linear Algebra Appl., 220(1995) 9-30   
[2] Belanger, G.， Kannike,K.， Pukhov，A.， Raidal, M.: Impact of semiannihilations on dark matter phenomenology. An example of $\mathbb { Z } _ { N }$ symmetric scalar dark matter, J. Cosmol. Astropart. Phys. 1204, O10 (2012)   
[3] Belanger,G.， Kannike,K.， Pukhov,A.， Raidal， M.: Minimal semiannihilating $\mathbb { Z } _ { N }$ scalar dark matter, J. Cosmol. Astropart. Phys. 1406, 021(2014)   
[4] Balaji, R., Palpandi, K.: Positive definite and Gram tensor complementarity problems. Optim. Lett., 12(3), 639-648(2018)   
[5] Bai, X.L., Huang, Z.H.，Wang,Y.: Global uniqueness and solvability for tensor complementarity problems. J. Optim.Theory Appl.， 170(1), 72-84(2016) [6] Che, M., Qi, L.， Wei, Y.: Stochastic $\mathcal { R } _ { 0 }$ tensors to stochastic tensor complementarity problems, Optim. Lett., 13(2), 261-279(2019)   
[7] Che, M.L., Qi, L.,Wei, Y.M.: Positive-definite tensors to nonlinear complementarity problems, J. Optim. Theory Appl., 168(2), 475-487(2016)   
[8] Chen, H., Huang, Z., Qi, L.: Copositivity Detection of Tensors: Theory and Algorithm, J. Optim. Theory Appl., 174(3), 746-761(2017)   
[9] Chen, H., Huang, Z.H., Qi, L.: Copositive tensor detection and its applications in physics and hypergraphs, Comput. Optim. Appl.， 69(1), 133-158(2018)   
[10] Chen, H., Wang, Y.: High-order copositive tensors and its applications, J. Appl. Anal. Compu., 8(6), 1863-1885(2018)   
[11] Chen, H., Qi, L., Song, Y.: Column suficient tensors and tensor complementarity problems, Front. Math. China,13(2),255-276(2018)   
[12] Chang, G.， Sederberg, T.W.: Nonnegative quadratic Bézier triangular patches, Comput. Aided Geom. D., 11(1)(1994) 113-116   
[13] A. Degee, I. P. Ivanov and V. Keus, Geometric minimization of highly symmetric potentials, Journal of High Energy Physics 1302, 125 (2013)   
[14] Ding, W., Luo, Z., Qi, L.: $\mathcal { P }$ -tensors, $\mathcal { P } _ { 0 }$ -tensors,and their applications. Linear Algebra Appl., 555, 336-354(2018)   
[15] Gowda， M.S.: Polynomial complementarity problems. Pac. J. Optim. 13(2), 227-241(2017)   
[16] Guo, Y.: A necessary and sufficient condition for the positive definite problem of a binary quartic form， arXiv:2009.01033[math.AG] 2 Sep 2020   
[17] Hadeler, K.P.: On copositive matrices. Linear Algebra Appl., 49(1983) 79-89   
[18] Huang, H., Qi, L.: Formulating an $n -$ person noncooperative game as a tensor complementarity problem，Comput. Optim.Appl.，66，557- 576(2017) [19] Igor P. Ivanov, Francisco Vazao, Yet another lesson on the stability conditions in multi-Higgs potentials, arXiv:2006.00036v1 [hep-ph] 29 May   
2020 [20] I. P. Ivanov and E. Vdovin， Discrete symmetries in the three-Higgsdoublet m0del, Phys. Rev. D 86, 095030 (2012) arXiv:1206.7108 [21] I.P. Ivanov and E. Vdovin， Classification of finite reparametrization symmetry groups in the three-Higgs-doublet model, Eur. Phys. J. C 73, no.2, 2309 (2013) [22] H. Ishimori， T. Kobayashi,H. Ohki, Y. Shimizu,H. Okada and M. Tanimoto, Non-Abelian Discrete Symmetries in Particle Physics, Prog. Theor. Phys. Suppl. 183, 1-163 (2010) [23] Kannike, K.: Vacuum stability of a general scalar potential of a few fields, Eur. Phys. J. C, 76,324(2016) [24] Kannike, K.: Erratum to: Vacuum stability of a general scalar potential of a few fields, Eur. Phys. J. C, 78, 355(2018) [25] Kannike, K.: Vacuum stability conditions from copositivity criteria, Eur. Phys. J. C, 72, 2093(2012) [26] Li， L.， Zhang， X.，Huang, Z.，Qi, L.: Test of copositive tensors, J. Industrial Manag. Optim. 15(2), 881-891(2018) [27] Liu, J.， Song，Y.: Copositivity for 3rd order symmetric tensors and applications,arXiv: 1911.10284 ChinaXiv: 201911.00094 23 November   
2019 [28] Luo, Z.， Qi, L.， Xiu, N.: The sparsest solutions to $Z -$ tensor complementarity problems. Optim. Lett., 11(3),471-482(2017) [29] E. Ma and G. Rajasekaran， Softly broken $A _ { 4 }$ symmetry for nearly degenerate neutrino masses, Phys. Rev. D 64, 113012 (2001) [30] Nie, J., Yang, Z., Zhang, X.: A Complete Semidefinte algorithm for Detecting Copositive Matrices and Tensors, SIAM J. Optim.,28(4)， 2902-   
2921(2018) [31] Nadler, E.: Nonnegativity of bivariate quadratic functions on a triangle, Comput. Aided Geom. D., 9(3)(1992) 195-205 [32] Qi, L.: Eigenvalues of a real supersymmetric tensor, J. Symbolic Comput., 40,1302-1324(2014) [33] Qi, L.: Symmetric Nonnegative Tensors and Copositive Tensors, Linear Algebra Appl., 439,228-238(2013) [34] Qi, L., Chen, H., Chen, Y.: Tensor Eigenvalues and Their Applications, Springer Singapore, (2018) [35] Qi, L., Song， Y., Zhang，X.: Positivity Conditions for Cubic, Quartic and Quintic Polynomials,arXiv:2008.10922 [36] Qi, L., Luo, Z.: Tensor Analysis: Spectral Theory and Special Tensors. SLAM, Philadelphia, (2017) [37] Song, Y.， Qi, L.: Necessary and sufficient conditions of copositive tenSors,Linear and Multilinear Algebra, 63(1), 120-131(2015) [38] Song， Y.， Qi, L.: Properties of tensor complementarity problem and some classes of structured tensors， Ann. Appl. Math.， 33(3)，308-   
323(2017) [39] Song，Y.， Qi, L.: Properties of some classes of structured tensors, J. Optim. Theory Appl., 165(3), 854-873(2015) [40] Song，Y.，Qi, L.: Tensor complementarity problem and semi-positive tensors, J. Optim. Theory Appl., 169,1069-1078(2016) [41] Song，Y.， Qi， L.: Analytical expressions of copositivity for 4th order symmetric tensors and applications, Analysis and Applications, DOI:   
10.1142/S0219530520500049 [42] Song, Y., Qi, L.: Eigenvalue analysis of constrained minimization problem for homogeneous polynomial, J. Glob. Optim., 64(3), 563-575(2016) [43] Song, Y.， Yu, G.: Properties of solution set of tensor complementarity problem, J. Optim. Theory Appl.,170, 85-96(2016)   
[44] Song， Y.， Qi, L.: A necessary and sufficient condition of positive definiteness for 4th order symmetric tensors defined in particle physics. arXiv: 2011.11262   
[45] Song, Y.， Qi, L.: Strictly semi-positive tensors and the boundedness of tensor complementarity problems, Optim. Lett.,11, 1407-1426(2017)   
[46] Song,Y.: Positive definiteness for 4th order symmetric tensors and ap plications.Anal. Math. Phys.,11, 10(2021)   
[47] Song，Y.， Mei， W.: Structural Properties of Tensors and Complementarity Problems. J. Optim. Theory Appl., 176(2),289-305(2018)   
[48] Ulrich, G., Watson, L.T.: Positivity conditions for quartic polynomials, SIAM J. Sci. Comput. 15, 528-544(1994)   
[49] Wang, X.， Chen， H. Wang, Y.: Solution structures of tensor complementarity problem.Front. Math. China,13(4),935-945(2018)   
[50] Wang, Y., Huang, Z.H.， Bai, X.L.: Exceptionally regular tensors and tensor complementarity problems. Optim.Method. Softw.， 31(4)，815- 828(2016)   
[51] Wang, J.， Hu, S.， Huang, Z.H.: Solution sets of quadratic complementarity problems. J. Optim. Theory Appl., 176(1),120-136(2018)