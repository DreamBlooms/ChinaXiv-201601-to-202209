# Copositivity for 3rd order symmetric tensors and applications

Jiarui Liu, Yisheng Song

November 23, 2019

Abstract.The strict copositivity of 4th order symmetric tensor may apply to detect vacuum stability of general scalar potential. For finding analytical expressions of (strict） copositivity of 4th order symmetric tensor, we may reduce its order to 3rd order to better deal with it. So, it is provided that several analytically sufficient conditions for the copositivity of 3rd order 2 dimensional (3 dimensional) symmetric tensors. Subsequently, applying these conclusions to 4th order tensors, the analytically sufficient conditions of copositivity are proved for 4th order 2 dimensional and 3 dimensional symmetric tensors. Finally, we apply these results to present analytical vacuum stability conditions for vacuum stability for $\mathbb { Z } _ { 3 }$ scalar dark matter.

Key Words and Phrases: Copositive Tensors, Symmetric tensor, Homogeneous polynomial, Analytical expression.

2010 AMS Subject Classification: 15A18， 15A69，90C20,  
90C30

# 1 Introduction

Recently, Kannike [12-14] studied the vacuum stability of general scalar potentials of a few fields. The most general scalar quartic potential of the SM Higgs $\mathbf { H } _ { 1 }$ ， an inert doublet $\mathbf { H } _ { 2 }$ and a complex singlet $\mathbf { S }$ is

$$
V ( h _ { 1 } , h _ { 2 } , s ) = { \Gamma } { \phi } ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 3 } { \gamma } _ { i j k l } z _ { i } z _ { j } z _ { k } z _ { l } ,
$$

where $z \ = \ ( z _ { 1 } , z _ { 2 } , z _ { 3 } ) ^ { \top } \ = \ ( h _ { 1 } , h _ { 2 } , s ) ^ { \top }$ ， $\begin{array} { r } { \begin{array} { r c l } { h _ { 1 } } & { = } & { | H _ { 1 } | } \end{array} } \end{array}$ ， $h _ { 2 } ~ = ~ | H _ { 2 } | , H _ { 2 } ^ { \dagger } H _ { 1 } ~ =$ $h _ { 1 } h _ { 2 } \rho e ^ { i \phi } , S = s e ^ { i \phi _ { S } }$ ， $\mathbf { \nabla } \Gamma = \left( \gamma _ { i j k l } \right)$ is coupling tensor,an 4th order 3 dimensional real symmetric tensor. Clearly, $h _ { 1 } \geq 0 , h _ { 2 } \geq 0 , s \geq 0$ . So, the vacuum stability of $\mathbb { Z } _ { 3 }$ scalar dark matter $V ( h _ { 1 } , h _ { 2 } , s )$ is equivalent to the strict copositivity of the coupling tensor $\mathbf { \vec { r } } = \left( \gamma _ { i j k l } \right)$ . The concept of (strict） copositivity of symmetric tensors was introduced by Qi [20] in 2013. A symmetric tensor （204号 $\mathbf { r }$ with order $m$ and dimension $n$ is called

n (i) copositive if Txm = £ Yiiz.imXiXiz :.· Xim ≥ O for all nonnegi1,i2,.,im=1 ative vector $x = ( x _ { 1 } , \cdots , x _ { n } ) ^ { \mid }$ ： (ii) strictly copositive if $\Gamma x ^ { m } > 0$ for all nonnegative and nonzero vector （20 $\boldsymbol { x } = ( x _ { 1 } , \cdots , x _ { n } ) ^ { \top }$ ：

Since the practical matters such as the vacuum stability of general scalar potentials of a few fields require precise expressions, it is necessery to find the analytical expressions of the strict copositivity of a symmetric tensor. Qi [20] showed a symmetric tensor is strictly copositive if for all $i = 1 , 2 , \cdots , n$ ，

$$
\gamma _ { i i \cdots i } + \sum \{ \gamma _ { i _ { 1 } i _ { 2 } \cdots i _ { m } } < 0 , ( i _ { 1 } , i _ { 2 } , \cdots , i _ { m } ) \neq ( i , i , \cdots , i ) \} > 0 .
$$

Song-Qi [23] gave a necessary and sufficient sondition of strictly copositive tensors with the help of its H-eigenvalue and Z-eigenvalue. Song-Qi [28] studied the (strict) copositvity of symmetric tensors by means of the constrained minimization problem on the unit sphere. Song-Qi [26] showed that the (strict) copositivity of a symmetric tensor is equivalent to its (strict） semipositiveness. A tensor $\mathbf { \Gamma }$ is said to be (strictly） semipositive (Song-Qi [24]) if for each nonzero and nonnegative vector $x = ( x _ { 1 } , x _ { 2 } , \cdot \cdot \cdot , x _ { n } ) ^ { \top }$ ，there is

（204号 $k \in \{ 1 , 2 , \cdots , n \}$ such that

$$
x _ { k } > 0 { \mathrm { ~ a n d ~ } } \left( \mathbf { r } x ^ { m - 1 } \right) _ { k } = \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } \gamma _ { k i _ { 2 } \cdots i _ { m } } x _ { i _ { 2 } } \cdots x _ { i _ { m } } \geq 0 ( > 0 ) .
$$

This class of tensors has close relationships with the tensor complementarity problems (for short， TCP)( [29-31]). For more details about TCP, also see [1-4,8-11,16,33-35] and references cited therein.

Recently, on the base of the main results of Song-Qi [26],an analytical expression of detecting the strict copositivity of a symmetric tensor was obtained by summarizing conclusions of Qi-Song [18]， Song-Qi [25]， SongMei [31], Yuan-You [36]. That is, a symmetric tensor $\mathbf { r }$ is strictly copositive if it satisfies

(i) $\sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } \gamma _ { i i _ { 2 } i _ { 3 } \cdots i _ { m } } > 0 { \mathrm { ~ f o r ~ a l l ~ } } i \in \{ 1 , 2 , \cdots , n \} ,$ (ii) $\frac { 1 } { n ^ { m - 1 } } \big ( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } \gamma _ { i i _ { 2 } i _ { 3 } \cdots i _ { m } } \big ) > \gamma _ { i j _ { 2 } j _ { 3 } \cdots j _ { m } } \mathrm { ~ f o r ~ a l l ~ } ( j _ { 2 } , j _ { 3 } , \cdots , j _ { m } ) \not = ( i , i , \cdots , i ) .$ （204

The numerical algorithms of copositivity of a tensor also were presented by Chen-Huang-Qi [5], Chen-Huang-Qi [6], Nie-Yang-Zhang [17], Li-ZhangHuang-Qi [15], also see [7,21,22]. Very recently, Song-Qi [27] provided several analytically suffcient conditions of checking (strict） copositivity of 4th order 3 dimensional symmetric tensors by reducing orders or dimensions of tensor.

In this paper, we will study the analytical expressions of certifying copositivity of a 3rd order 3 (or 2) dimensional symmetric tensor. Then applying them to show suffcient conditions of copositivity of 4th order 3 dimensional tensors,which are differ from ones of Song-Qi [27]. Furthermore,we use these conclusions to check vacuum stability for $\mathbb { Z } _ { 3 }$ scalar dark matter.

# 2 Preliminaries and Basic facts

Let $\| \cdot \|$ denote any norm on $\mathbb { R } ^ { n }$ . Then the equivalent definition of (strict) copositivity and semipositive (positive) definiteness of a symmetric tensor was presented in the sense of any norm on $\mathbb { R } ^ { 2 }$ [19-23].

Lemma 2.1. （[23]) Let $\mathbf { r }$ be a symmetric tensor of order m and dimension （204号 $n$ . Then

(i） $\mathbf { \delta T }$ is copositive if and only if $\Gamma x ^ { m } \geq 0$ for all nonnegative vectors $x \in \mathbb { R } ^ { n }$ with $\| x \| = 1$ ：，   
(ii) $\mathbf { \delta T }$ is strictly copositive if and only if $\mathbf { \Gamma } \mathbf { r } ^ { m } > 0$ for all nonnegative vectors （204号 $x \in \mathbb { R } ^ { n }$ with $\| x \| = 1$ ：

For a cubic and univariate polynomial $P ( t )$ with real coefficients,

$$
P ( t ) = a t ^ { 3 } + b t ^ { 2 } + c t + d ,
$$

Schmidt-He $\beta$ [32] proved its nonnegative conditions.

Lemma 2.2. （[32, Proposition ${ \it 2 ] } _ { , }$ ）Let $P ( t )$ be a cubic and univariate polynomial given by (2.1). Then (i) $P ( t ) \geq 0$ for all $t \geq 0$ if and only if the inequalities systems $( 1 )$ or(2） hold,

$$
\begin{array} { r l } & { a \geq 0 , \ b \geq 0 , \ c \geq 0 , \ d \geq 0 , } \\ & { \operatorname* { m a x } \{ a , d \} > 0 , \ a \geq 0 , \ d \geq 0 , \ 4 a c ^ { 3 } + 4 b ^ { 3 } d + 2 7 a ^ { 2 } d ^ { 2 } - 1 8 a b c d - b ^ { 2 } c ^ { 2 } \geq 0 . } \end{array}
$$

(ii) $P ( t ) \geq 0$ for all $t \geq 0$ if the inequalities

$$
a \geq 0 , \ d \geq 0 , \ b \geq a - 2 { \sqrt { a d } } , c \geq d - 2 { \sqrt { a d } }
$$

hold simultaneously

Lemma 2.3. ( [32, Proposition 3]) Let a quadratic and univariate polynomial $p ( t )$ be given by

$$
p ( t ) = \alpha t ^ { 2 } + \beta t + \gamma .
$$

Then $p ( t ) \geq 0$ for all $t \geq 0$ if and only if the inequalities

$$
\alpha \ge 0 , ~ \gamma \ge 0 , ~ \beta + 2 \sqrt { \alpha \gamma } \ge 0
$$

hold simultaneously

# 3 Copositivity of 3rd order tensors

Let $\mathbf { \Gamma } \mathbf { { T } } = \left( \gamma _ { i j k } \right)$ be a 3rd order 2 dimensional symmetric tensor. Then for a vector $\boldsymbol { x } = ( x _ { 1 } , x _ { 2 } ) ^ { \top }$ ，

$$
\begin{array} { r l r } {  { \Gamma x ^ { 3 } = \sum _ { i , j , k = 1 } ^ { 2 } \gamma _ { i j k } x _ { i } x _ { j } x _ { k } } } \\ & { } & { = \gamma _ { 1 1 1 } x _ { 1 } ^ { 3 } + 3 \gamma _ { 1 1 2 } x _ { 1 } ^ { 2 } x _ { 2 } + 3 \gamma _ { 1 2 2 } x _ { 1 } x _ { 2 } ^ { 2 } + \gamma _ { 2 2 2 } x _ { 2 } ^ { 3 } . } \end{array}
$$

Theorem 3.1. A 3rd order 2 dimensional symmetric tensor is copositive if and only if the following inequalities systems (1) or (2) hold,

$$
\begin{array} { r l } & { \gamma _ { 1 1 1 } \geq 0 , \ \gamma _ { 2 2 2 } \geq 0 , \ \gamma _ { 1 1 2 } \geq 0 , \ \gamma _ { 1 2 2 } \geq 0 ; } \\ & { \operatorname* { m a x } \{ \gamma _ { 1 1 1 } , \gamma _ { 2 2 2 } \} > 0 , \ \gamma _ { 1 1 1 } \geq 0 , \ \gamma _ { 2 2 2 } \geq 0 , } \\ & { 4 \gamma _ { 1 1 1 } \gamma _ { 1 2 2 } ^ { 3 } + 4 \gamma _ { 1 1 2 } ^ { 3 } \gamma _ { 2 2 2 } + \gamma _ { 1 1 1 } ^ { 2 } \gamma _ { 2 2 2 } ^ { 2 } - 6 \gamma _ { 1 1 1 } \gamma _ { 1 1 2 } \gamma _ { 1 2 2 } \gamma _ { 2 2 2 } - 3 \gamma _ { 1 1 2 } ^ { 2 } \gamma _ { 1 2 2 } ^ { 2 } \geq 0 . } \end{array}
$$

Proof. It follows from Lemma 2.1 that we can restrict $\boldsymbol { x } = ( x _ { 1 } , x _ { 2 } ) ^ { \top }$ to

$$
\| x \| = | x _ { 1 } | + | x _ { 2 } | = 1 { \mathrm { ~ f o r ~ a l l ~ } } x { \mathrm { ~ w i t h ~ } } x _ { 1 } \geq 0 , \ x _ { 2 } \geq 0
$$

Clearly, $\Gamma x ^ { 3 } = \gamma _ { 1 1 1 } x _ { 1 } \geq 0$ for $\boldsymbol { x } = ( x _ { 1 } , 0 )$ and $\Gamma x ^ { 3 } = \gamma _ { 2 2 2 } x _ { 2 } \geq 0$ for $x =$ $( 0 , x _ { 2 } )$ . Now both $x _ { 1 }$ and $x _ { 2 }$ are not $0$ . Then the homogeneous polynomial $\boldsymbol { \mathcal { A } } \boldsymbol { x } ^ { 3 }$ can be divided by $x _ { 2 } ^ { 3 }$ to yield

$$
\frac { \Gamma x ^ { 3 } } { x _ { 2 } ^ { 3 } } = \gamma _ { 1 1 1 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) ^ { 3 } + 3 \gamma _ { 1 1 2 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) ^ { 2 } + 3 \gamma _ { 1 2 2 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) + \gamma _ { 2 2 2 } .
$$

Let P(t)=， .e.

$$
P ( t ) = \gamma _ { 1 1 1 } t ^ { 3 } + 3 \gamma _ { 1 1 2 } t ^ { 2 } + 3 \gamma _ { 1 2 2 } t + \gamma _ { 2 2 2 } .
$$

Clearly, $P ( t ) \geq 0$ if and only if $\mathbf { \Gamma } \mathbf { T } x ^ { 3 } \geq 0$ . An application of Lemma $2 . 2 ( \mathrm { i } )$ to the polynomial $P ( t )$ with $( a , b , c , d ) ^ { \top } = ( \gamma _ { 1 1 1 } , 3 \gamma _ { 1 1 2 } , 3 \gamma _ { 1 2 2 } , \gamma _ { 2 2 2 } ) ^ { \top }$ ，we obtain that $P ( t ) \geq 0$ for all $t \geq 0$ if and only if the inequalities systems

$$
a = \gamma _ { 1 1 1 } \geq 0 , \ d = \gamma _ { 2 2 2 } \geq 0 , \ b = 3 \gamma _ { 1 1 2 } \geq 0 , \ c = 3 \gamma _ { 2 2 1 } \geq 0
$$

or

$$
\begin{array} { r l } & { \operatorname* { m a x } \{ \gamma _ { 1 1 1 } , \gamma _ { 2 2 2 } \} > 0 , \ \gamma _ { 1 1 1 } \geq 0 , \ \gamma _ { 2 2 2 } \geq 0 , } \\ & { 4 \gamma _ { 1 1 1 } ( 3 \gamma _ { 1 2 2 } ) ^ { 3 } + 4 ( 3 \gamma _ { 1 1 2 } ) ^ { 3 } \gamma _ { 2 2 2 } + 2 7 \gamma _ { 1 1 1 } ^ { 2 } \gamma _ { 2 2 2 } ^ { 2 } - 1 8 \gamma _ { 1 1 1 } ( 3 \gamma _ { 1 1 2 } ) ( 3 \gamma _ { 1 2 2 } ) \gamma _ { 2 2 2 } } \\ & { - \left( 3 \gamma _ { 1 1 2 } \right) ^ { 2 } ( 3 \gamma _ { 1 2 2 } ) ^ { 2 } \geq 0 . } \end{array}
$$

Namely,

$$
\begin{array} { r l } & { \gamma _ { 1 1 1 } \geq 0 , \gamma _ { 2 2 2 } \geq 0 , \gamma _ { 1 1 2 } \geq 0 , \gamma _ { 1 2 2 } \geq 0 ; } \\ & { \operatorname* { m a x } \{ \gamma _ { 1 1 1 } , \gamma _ { 2 2 2 } \} > 0 , \gamma _ { 1 1 1 } \geq 0 , \gamma _ { 2 2 2 } \geq 0 , } \\ & { 4 \gamma _ { 1 1 1 } \gamma _ { 1 2 2 } ^ { 3 } + 4 \gamma _ { 1 1 2 } ^ { 3 } \gamma _ { 2 2 2 } + \gamma _ { 1 1 1 } ^ { 2 } \gamma _ { 2 2 2 } ^ { 2 } - 6 \gamma _ { 1 1 1 } \gamma _ { 1 1 2 } \gamma _ { 1 2 2 } \gamma _ { 2 2 2 } - 3 \gamma _ { 1 1 2 } ^ { 2 } \gamma _ { 1 2 2 } ^ { 2 } \geq 0 . } \end{array}
$$

Therefore, the desired conclusions are obtained.

Remark 3.1. It follows from the proof of Theorem 3.1 that $\mathbf { \Gamma } \Gamma x ^ { 3 }$ may be divided by $x _ { 1 } ^ { 3 }$ （ $\mathbf { \bar { \boldsymbol { x } } } _ { 1 } \neq 0$ )，then

$$
P ( t ) = \frac { \Gamma x ^ { 3 } } { x _ { 1 } ^ { 3 } } = \gamma _ { 1 1 1 } + 3 \gamma _ { 1 1 2 } t + 3 \gamma _ { 1 2 2 } t ^ { 2 } + \gamma _ { 2 2 2 } t ^ { 3 } ,
$$

where $\begin{array} { r } { t = \frac { x _ { 2 } } { x _ { 1 } } } \end{array}$ . The conclusions are same.

Theorem 3.2. Let $\mathbf { \delta T }$ be a 3rd order $\mathcal { Z }$ dimensional and symmetric tensor. Assume that

$$
\begin{array} { r l } & { \gamma _ { 1 1 1 } \geq 0 , \gamma _ { 2 2 2 } \geq 0 , } \\ & { \gamma _ { 1 1 2 } \geq \frac { \gamma _ { 1 1 1 } - 2 \sqrt { \gamma _ { 1 1 1 } \gamma _ { 2 2 2 } } } { 3 } , \ \gamma _ { 1 2 2 } \geq \frac { \gamma _ { 2 2 2 } - 2 \sqrt { \gamma _ { 1 1 1 } \gamma _ { 2 2 2 } } } { 3 } . } \end{array}
$$

Then $\mathbf { \delta T }$ is copositive.

Proof. Using the proof technique of Theorem 3.1, we only need to show the nonnegativity of the polynomial $P ( t )$ given by (3.2) for all $t \geq 0$ ，where

$$
P ( t ) = a t ^ { 3 } + b t ^ { 2 } + c t + d , \ a = \gamma _ { 1 1 1 } , \ b = 3 \gamma _ { 1 1 2 } , \ c = 3 \gamma _ { 1 2 2 } , \ d = \gamma _ { 2 2 2 }
$$

The assumptions mean that $a = \gamma _ { 1 1 1 } \geq 0$ ， $d = \gamma _ { 2 2 2 } \geq 0$ ，

$$
b = 3 \gamma _ { 1 1 2 } \geq \gamma _ { 1 1 1 } - 2 \sqrt { \gamma _ { 1 1 1 } \gamma _ { 2 2 2 } } , c = 3 \gamma _ { 1 2 2 } \geq \gamma _ { 2 2 2 } - 2 \sqrt { \gamma _ { 1 1 1 } \gamma _ { 2 2 2 } } .
$$

From Lemma 2.2(ii), it follows that $P ( t ) \geq 0$ for all $t \geq 0$ ,and so,the tensor （204号 $\mathbf { \delta T }$ is copositive,as required. □

Theorem 3.3. Let $\mathbf { \delta T }$ be a 3rd order 2 dimensional and symmetric tensor. Assume that one of the inequalities systems (1) and (2) holds,

$$
\begin{array} { r } { \gamma _ { 1 1 1 } \geq 0 , \ \gamma _ { 2 2 2 } \geq 0 , \ \gamma _ { 1 2 2 } \geq 0 , \ \gamma _ { 1 1 2 } \geq - \frac { 2 } { 3 } \sqrt { 3 \gamma _ { 1 2 2 } \gamma _ { 1 1 1 } } ; } \\ { \gamma _ { 1 1 1 } \geq 0 , \ \gamma _ { 2 2 2 } \geq 0 , \ \gamma _ { 1 1 2 } \geq 0 , \ \gamma _ { 1 2 2 } \geq - \frac { 2 } { 3 } \sqrt { 3 \gamma _ { 1 1 2 } \gamma _ { 2 2 2 } } . } \end{array}
$$

Then $\mathbf { \delta T }$ is copositive.

Proof. Using the proof technique of Theorem 3.1, it is known that the copositivity of $\mathbf { r }$ is equivalent to the nonnegativity of the polynomial $P ( t )$ for all （20 $t \geq 0$ ，where

$$
P ( t ) = \gamma _ { 1 1 1 } t ^ { 3 } + 3 \gamma _ { 1 1 2 } t ^ { 2 } + 3 \gamma _ { 1 2 2 } t + \gamma _ { 2 2 2 } .
$$

Now we show the nonnegativity of $P ( t )$ . In fact,

$$
\begin{array} { r l r } & { } & { P ( t ) = \gamma _ { 1 1 1 } t ^ { 3 } + ( 3 \gamma _ { 1 1 2 } t ^ { 2 } + 3 \gamma _ { 1 2 2 } t + \gamma _ { 2 2 2 } ) , ~ } \\ & { } & { ~ = t ( \gamma _ { 1 1 1 } t ^ { 2 } + 3 \gamma _ { 1 1 2 } t + 3 \gamma _ { 1 2 2 } ) + \gamma _ { 2 2 2 } . ~ } \end{array}
$$

Let $f ( t ) = 3 \gamma _ { 1 1 2 } t ^ { 2 } + 3 \gamma _ { 1 2 2 } t + \gamma _ { 2 2 2 }$ and $g ( t ) = \gamma _ { 1 1 1 } t ^ { 2 } + 3 \gamma _ { 1 1 2 } t + 3 \gamma _ { 1 2 2 }$ . Then from Lemma 2.3, it follows that the nonnegativity of $f ( t )$ is equivalent to the inequalities system,

$$
\gamma _ { 2 2 2 } \geq 0 , \ \gamma _ { 1 1 2 } \geq 0 , \ 3 \gamma _ { 1 2 2 } + 2 \sqrt { 3 \gamma _ { 1 1 2 } \gamma _ { 2 2 2 } } \geq 0 .
$$

So, the inequality $\gamma _ { 1 1 1 } \geq 0$ along with the above inequalities system (3.3) imply the polynomial $P ( t ) = \gamma _ { 1 1 1 } t ^ { 3 } + f ( t ) \geq 0$ for all $t \geq 0$ ，that is, $\mathbf { \Gamma }$ is copositive.

For the aussumption (1), the same technique is applied to $g ( t )$ to yield the desired conclusion. $\sqcup$

For an 3rd order 3 dimensional symmetric tensor $\mathbf { \delta T }$ and a vector $x =$ $( x _ { 1 } , x _ { 2 } , x _ { 3 } ) ^ { \top }$ ，

$$
\begin{array} { l } { { \displaystyle { \Gamma x ^ { 3 } = \sum _ { i , j , k = 1 } ^ { 3 } \gamma _ { i j k } x _ { i } x _ { j } x _ { k } } } } \\ { { \displaystyle ~ = \gamma _ { 1 1 1 } x _ { 1 } ^ { 3 } + \gamma _ { 2 2 2 } x _ { 2 } ^ { 3 } + \gamma _ { 3 3 3 } x _ { 3 } ^ { 3 } + 3 \gamma _ { 1 1 2 } x _ { 1 } ^ { 2 } x _ { 2 } + 3 \gamma _ { 1 2 2 } x _ { 1 } x _ { 2 } ^ { 2 } + 3 \gamma _ { 1 1 3 } x _ { 1 } ^ { 2 } x _ { 3 } } } \\ { { \displaystyle ~ + 3 \gamma _ { 1 3 3 } x _ { 1 } x _ { 3 } ^ { 2 } + 3 \gamma _ { 2 2 3 } x _ { 2 } ^ { 2 } x _ { 3 } + 3 \gamma _ { 2 3 3 } x _ { 2 } x _ { 3 } ^ { 3 } + 6 \gamma _ { 1 2 3 } x _ { 1 } x _ { 2 } x _ { 3 } . } } \end{array}
$$

Theorem 3.4. An 3rd order 3 dimensional symmetric tensor $\mathbf { \delta T }$ is copositive if the following inequalities systems hold,

$$
\begin{array} { r l r } & { } & { \gamma _ { 1 1 1 } \geq 0 , \ \gamma _ { 2 2 2 } \geq 0 , \ \gamma _ { 3 3 3 } \geq 0 , \ \gamma _ { 1 2 3 } \geq 0 , } \\ & { } & { 3 2 \gamma _ { 1 1 1 } \gamma _ { 1 2 2 } ^ { 3 } + 3 2 \gamma _ { 1 1 2 } ^ { 3 } \gamma _ { 2 2 2 } + \gamma _ { 1 1 1 } ^ { 2 } \gamma _ { 2 2 2 } ^ { 2 } - 2 4 \gamma _ { 1 1 1 } \gamma _ { 1 1 2 } \gamma _ { 1 2 2 } \gamma _ { 2 2 2 } - 4 8 \gamma _ { 1 1 2 } ^ { 2 } \gamma _ { 1 2 2 } ^ { 2 } \geq 0 , } \\ & { } & { 3 2 \gamma _ { 1 1 1 } \gamma _ { 1 3 3 } ^ { 3 } + 3 2 \gamma _ { 1 1 3 } ^ { 3 } \gamma _ { 3 3 3 } + \gamma _ { 1 1 1 } ^ { 2 } \gamma _ { 3 3 3 } ^ { 2 } - 2 4 \gamma _ { 1 1 1 } \gamma _ { 1 3 3 } \gamma _ { 1 3 3 } \gamma _ { 3 3 3 } - 4 8 \gamma _ { 1 1 3 } ^ { 2 } \gamma _ { 1 3 3 } ^ { 2 } \geq 0 , } \\ & { } & { 3 2 \gamma _ { 2 2 2 } \gamma _ { 2 3 3 } ^ { 3 } + 3 2 \gamma _ { 2 2 3 } ^ { 3 } \gamma _ { 3 3 3 } + \gamma _ { 2 2 2 } ^ { 2 } \gamma _ { 3 3 3 } ^ { 2 } - 2 4 \gamma _ { 2 2 2 } \gamma _ { 2 2 3 } \gamma _ { 2 3 3 } \gamma _ { 3 3 3 } - 4 8 \gamma _ { 2 2 3 } ^ { 2 } \gamma _ { 2 3 3 } ^ { 2 } \geq 0 . } \end{array}
$$

Proof. Rewritten $\mathbf { T } x ^ { 3 }$ as follows

$$
\begin{array} { r l } & { \Gamma x ^ { 3 } = \displaystyle ( \frac { 1 } { 2 } \gamma _ { 1 1 1 } x _ { 1 } ^ { 3 } + 3 \gamma _ { 1 1 2 } x _ { 1 } ^ { 2 } x _ { 2 } + 3 \gamma _ { 1 2 2 } x _ { 1 } x _ { 2 } ^ { 2 } + \frac { 1 } { 2 } \gamma _ { 2 2 2 } x _ { 2 } ^ { 3 } ) } \\ & { \qquad + \displaystyle ( \frac { 1 } { 2 } \gamma _ { 1 1 1 } x _ { 1 } ^ { 3 } + 3 \gamma _ { 1 1 3 } x _ { 1 } ^ { 2 } x _ { 3 } + 3 \gamma _ { 1 3 3 } x _ { 1 } x _ { 3 } ^ { 2 } + \frac { 1 } { 2 } \gamma _ { 3 3 3 } x _ { 3 } ^ { 3 } ) } \\ & { \qquad + \displaystyle ( \frac { 1 } { 2 } \gamma _ { 2 2 2 } x _ { 2 } ^ { 3 } + 3 \gamma _ { 2 2 3 } x _ { 2 } ^ { 2 } x _ { 3 } + 3 \gamma _ { 2 3 3 } x _ { 2 } x _ { 3 } ^ { 3 } + \frac { 1 } { 2 } \gamma _ { 3 3 3 } x _ { 3 } ^ { 3 } ) } \\ & { \qquad + 6 \gamma _ { 1 2 3 } x _ { 1 } x _ { 2 } x _ { 3 } } \\ & { \qquad = 4 y ^ { 3 } + { \mathcal { B } } z ^ { 3 } + { \mathcal { C } } w ^ { 3 } + 6 \gamma _ { 1 2 3 } x _ { 1 } x _ { 2 } x _ { 3 } , } \end{array}
$$

where $y = ( x _ { 1 } , x _ { 2 } ) ^ { \top }$ ， $z = ( x _ { 1 } , x _ { 3 } ) ^ { \top }$ ， $\boldsymbol { w } = ( x _ { 2 } , x _ { 3 } ) ^ { \top }$ ， $\mathcal { A } = \left( a _ { i j k } \right)$ and $\boldsymbol { B } = \left( b _ { i j k } \right)$ （204号 and $\mathcal { C } = \left( c _ { i j k } \right)$ are three 3rd order 2 dimensional symmetric tensors with their entries

$$
{ \begin{array} { r l } & { a _ { 1 1 1 } = { \cfrac { 1 } { 2 } } \gamma _ { 1 1 1 } , ~ a _ { 1 1 2 } = \gamma _ { 1 1 2 } , ~ a _ { 1 2 2 } = \gamma _ { 1 2 2 } , ~ a _ { 2 2 2 } = { \cfrac { 1 } { 2 } } \gamma _ { 2 2 2 } ; } \\ & { ~ b _ { 1 1 1 } = { \cfrac { 1 } { 2 } } \gamma _ { 1 1 1 } , ~ b _ { 1 1 2 } = \gamma _ { 1 1 3 } , ~ b _ { 1 2 2 } = \gamma _ { 1 3 3 } , ~ b _ { 2 2 2 } = { \cfrac { 1 } { 2 } } \gamma _ { 3 3 3 } ; } \\ & { c _ { 1 1 1 } = { \cfrac { 1 } { 2 } } \gamma _ { 2 2 2 } , ~ c _ { 1 1 2 } = \gamma _ { 2 2 3 } , ~ c _ { 1 2 2 } = \gamma _ { 2 3 3 } , ~ c _ { 2 2 2 } = { \cfrac { 1 } { 2 } } \gamma _ { 3 3 3 } . } \end{array} }
$$

For the polynomial $\begin{array} { r } { A y ^ { 3 } = \frac 1 2 \gamma _ { 1 1 1 } x _ { 1 } ^ { 3 } + 3 \gamma _ { 1 1 2 } x _ { 1 } ^ { 2 } x _ { 2 } + 3 \gamma _ { 1 2 2 } x _ { 1 } x _ { 2 } ^ { 2 } + \frac 1 2 \gamma _ { 2 2 2 } x _ { 2 } ^ { 3 } } \end{array}$ ，the assumptions imply that

$$
\begin{array} { l } { { a _ { 1 1 1 } = \displaystyle \frac { 1 } { 2 } \gamma _ { 1 1 1 } \geq 0 , ~ a _ { 2 2 2 } = \displaystyle \frac { 1 } { 2 } \gamma _ { 2 2 2 } \geq 0 , } } \\ { { \displaystyle 4 a _ { 1 1 1 } a _ { 1 2 2 } ^ { 3 } + 4 a _ { 1 1 2 } ^ { 3 } a _ { 2 2 2 } + a _ { 1 1 1 } a _ { 2 2 2 } ^ { 2 } - 6 a _ { 1 1 1 } a _ { 1 1 2 } a _ { 2 2 2 } - 3 a _ { 1 1 2 } ^ { 2 } a _ { 1 2 2 } ^ { 2 } } } \\ { { \displaystyle ~ = \displaystyle \frac { 1 } { 1 6 } ( 3 2 \gamma _ { 1 1 1 } \gamma _ { 1 2 2 } ^ { 3 } + 3 2 \gamma _ { 1 1 2 } ^ { 3 } \gamma _ { 2 2 2 } + \gamma _ { 1 1 1 } ^ { 2 } \gamma _ { 2 2 2 } ^ { 2 } - 2 4 \gamma _ { 1 1 1 } \gamma _ { 1 1 2 } \gamma _ { 1 2 2 } \gamma _ { 2 2 2 } } } \\ { { - 4 8 \gamma _ { 1 1 2 } ^ { 2 } \gamma _ { 1 2 2 } ^ { 2 } ) \geq 0 . } } \end{array}
$$

From Theorem 3.1, it follows that the tensor $\mathcal { A }$ is copositive, i.e., $\boldsymbol { \mathcal { A } } \boldsymbol { y } ^ { 3 } \geq 0$ for all $y \geq 0$

Similarly, we also have $B z ^ { 3 } \geq 0$ for all $z \geq 0$ and $\mathcal { C } w ^ { 3 } \geq 0$ for all $w \geq 0$ ： So,

The desired conclusions are proved.

Using the similar proof technique of Theorem 3.4, we may apply Theorem 3.2 to three tensors $\mathcal { A } = \left( a _ { i j k } \right)$ and $B = \left( b _ { i j k } \right)$ and $\mathcal { C } = \left( c _ { i j k } \right)$ ,and then the following conclusions are showed easily.

Theorem 3.5. Let $\mathbf { r }$ be a 3rd order 3 dimensional and symmetric tensor. Assume that

$$
\begin{array} { r l } & { \gamma _ { 1 1 1 } \geq 0 , \gamma _ { 2 2 2 } \geq 0 , \ \gamma _ { 3 3 3 } \geq 0 , \ \gamma _ { 1 2 3 } \geq 0 , } \\ & { \gamma _ { 1 1 2 } \geq \frac { \gamma _ { 1 1 1 } - 2 \sqrt { \gamma _ { 1 1 1 } \gamma _ { 2 2 2 } } } { 6 } , \ \gamma _ { 1 2 2 } \geq \frac { \gamma _ { 2 2 2 } - 2 \sqrt { \gamma _ { 1 1 1 } \gamma _ { 2 2 2 } } } { 6 } , } \\ & { \gamma _ { 1 1 3 } \geq \frac { \gamma _ { 1 1 1 } - 2 \sqrt { \gamma _ { 1 1 1 } \gamma _ { 3 3 3 } } } { 6 } , \ \gamma _ { 1 3 3 } \geq \frac { \gamma _ { 3 3 3 } - 2 \sqrt { \gamma _ { 1 1 1 } \gamma _ { 3 3 3 } } } { 6 } } \\ & { \gamma _ { 2 2 3 } \geq \frac { \gamma _ { 2 2 2 } - 2 \sqrt { \gamma _ { 2 2 2 } \gamma _ { 3 3 3 } } } { 6 } , \ \gamma _ { 2 3 3 } \geq \frac { \gamma _ { 3 3 3 } - 2 \sqrt { \gamma _ { 2 2 2 } \gamma _ { 3 3 3 } } } { 6 } . } \end{array}
$$

Then $\mathbf { \Gamma }$ is copositive

# 4Copositivity of 4th order tensors

Let $\mathcal { A }$ be an 4th order 2 dimensional symmetric tensor. Then for a vector （204号 $\boldsymbol { x } = ( x _ { 1 } , x _ { 2 } ) ^ { \top }$ ，

$$
\begin{array} { l } { \displaystyle { \mathcal { A } x ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 2 } a _ { i j k l } x _ { i } x _ { j } x _ { k } x _ { l } } } \\ { \displaystyle { \quad = a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 4 a _ { 1 2 1 1 } x _ { 1 } ^ { 3 } x _ { 2 } + 6 a _ { 1 2 2 1 } x _ { 1 } ^ { 2 } x _ { 2 } ^ { 2 } + 4 a _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 3 } + a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } . } } \end{array}
$$

Theorem 4.1. Let $\mathcal { A }$ be an 4th order 2 dimensional symmetric tensor with $a _ { 1 1 1 1 } > 0$ and $a _ { 2 2 2 2 } > 0$ . Assume that one of the following conditions (1） and (2) holds,

$$
\begin{array} { r l } & { \left( I \right) \ a _ { 1 2 2 2 } \geq 0 , \ 5 4 a _ { 1 1 1 1 } a _ { 1 2 2 1 } ^ { 3 } + 6 4 a _ { 1 1 2 1 } ^ { 3 } a _ { 1 2 2 2 } + 2 7 a _ { 1 1 1 1 } ^ { 2 } a _ { 1 2 2 2 } ^ { 2 } - 1 0 8 a _ { 1 1 1 1 } a _ { 1 1 2 1 } a _ { 1 2 2 1 } a _ { 1 2 2 2 } } \\ & { \qquad - 3 6 a _ { 1 1 2 1 } ^ { 2 } a _ { 1 2 2 2 } ^ { 2 } \geq 0 ; } \\ & { \left( 2 \right) \ a _ { 1 1 1 2 } \geq 0 , \ 6 4 a _ { 1 2 1 1 } a _ { 1 2 2 2 } ^ { 3 } + 5 4 a _ { 1 2 2 1 } ^ { 3 } a _ { 2 2 2 2 } + 2 7 a _ { 1 2 1 1 } a _ { 2 2 2 2 } ^ { 2 } - 1 0 8 a _ { 1 2 1 1 } a _ { 1 2 2 1 } a _ { 1 2 2 2 } a _ { 2 2 2 2 } } \\ & { \qquad - 3 6 a _ { 1 2 2 1 } ^ { 2 } a _ { 1 2 2 2 } ^ { 2 } \geq 0 . } \end{array}
$$

Then $\mathcal { A }$ is copositive.

Proof. Rewritten $\boldsymbol { \mathcal { A } } \boldsymbol { x } ^ { 4 }$ as follows,

$$
\begin{array} { r } { A x ^ { 4 } = x _ { 1 } ( a _ { 1 1 1 1 } x _ { 1 } ^ { 3 } + 4 a _ { 1 2 1 1 } x _ { 1 } ^ { 2 } x _ { 2 } + 6 a _ { 1 2 2 1 } x _ { 1 } x _ { 2 } ^ { 2 } + 4 a _ { 1 2 2 2 } x _ { 2 } ^ { 3 } ) + a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } } \\ { = a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + x _ { 2 } ( 4 a _ { 1 2 1 1 } x _ { 1 } ^ { 3 } + 6 a _ { 1 2 2 1 } x _ { 1 } ^ { 2 } x _ { 2 } + 4 a _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 2 } + a _ { 2 2 2 2 } x _ { 2 } ^ { 3 } ) . } \end{array}
$$

Let

$$
f ( x _ { 1 } , x _ { 2 } ) = a _ { 1 1 1 1 } x _ { 1 } ^ { 3 } + 4 a _ { 1 2 1 1 } x _ { 1 } ^ { 2 } x _ { 2 } + 6 a _ { 1 2 2 1 } x _ { 1 } x _ { 2 } ^ { 2 } + 4 a _ { 1 2 2 2 } x _ { 2 } ^ { 3 } .
$$

Then $f ( x _ { 1 } , x _ { 2 } )$ can be a homogeneous polynomial defined by a 3rd order 2 dimensional and symmetric tensor $\Gamma = \left( \gamma _ { i j k } \right)$ with its entries

$$
\gamma _ { 1 1 1 } = a _ { 1 1 1 1 } , \gamma _ { 1 1 2 } = \frac { 4 } { 3 } a _ { 1 2 1 1 } , \gamma _ { 1 2 2 } = 2 a _ { 1 2 2 1 } , \gamma _ { 2 2 2 } = 4 a _ { 1 2 2 2 } .
$$

From the assumption (1), it follows that

$$
\begin{array} { r l } & { 4 \gamma _ { 1 1 1 } \gamma _ { 1 2 2 } ^ { 3 } + 4 \gamma _ { 1 1 2 } ^ { 3 } \gamma _ { 2 2 2 } + \gamma _ { 1 1 1 } ^ { 2 } \gamma _ { 2 2 2 } ^ { 2 } - 6 \gamma _ { 1 1 1 } \gamma _ { 1 1 2 } \gamma _ { 1 2 2 } - 3 \gamma _ { 1 2 1 } ^ { 2 } \gamma _ { 1 2 2 } ^ { 2 } } \\ & { = 4 a _ { 1 1 1 1 } \left( 2 a _ { 1 2 2 1 } \right) ^ { 3 } + 4 \big ( \frac { 4 } { 3 } a _ { 1 2 1 1 } \big ) ^ { 3 } 4 a _ { 1 2 2 2 } + a _ { 1 1 1 } ^ { 2 } ( 4 a _ { 1 2 2 2 } ) ^ { 2 } } \\ & { \phantom { = } - 6 a _ { 1 1 1 1 } \big ( \frac { 4 } { 3 } a _ { 1 2 1 1 } \big ) \big ( 2 a _ { 1 2 2 1 } \big ) \big ( 4 a _ { 1 2 2 2 } \big ) - 3 \big ( \frac { 4 } { 3 } a _ { 1 2 1 1 } \big ) ^ { 2 } \big ( 2 a _ { 1 2 2 1 } \big ) ^ { 2 } } \\ & { = \cfrac { 1 6 } { 9 } \big ( 5 4 a _ { 1 1 1 1 } a _ { 1 2 2 1 } ^ { 3 } + 6 4 a _ { 1 1 2 1 } ^ { 3 } a _ { 1 2 2 2 } + 2 7 a _ { 1 1 1 } ^ { 2 } a _ { 1 2 2 2 } ^ { 2 } } \\ & { \phantom { = } - 1 0 8 a _ { 1 1 1 1 } a _ { 1 2 1 } a _ { 1 2 2 1 } a _ { 1 2 2 } - 3 6 a _ { 1 1 2 1 } ^ { 2 } a _ { 1 2 2 1 } \big ) } \\ & { \geq 0 . } \end{array}
$$

By Theorem 3.1, we have $f ( x _ { 1 } , x _ { 2 } ) \geq 0$ for all $x \geq 0$ ， and hence,

That is, $\mathcal { A }$ is copositive.

Let

$$
g ( x _ { 1 } , x _ { 2 } ) = 4 a _ { 1 2 1 1 } x _ { 1 } ^ { 3 } + 6 a _ { 1 2 2 1 } x _ { 1 } ^ { 2 } x _ { 2 } + 4 a _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 2 } + a _ { 2 2 2 2 } x _ { 2 } ^ { 3 } .
$$

In the same way, we also have $g ( x _ { 1 } , x _ { 2 } ) \geq 0$ for all $x \geq 0$ by the assumption (2). So, $\mathcal { A } { { x } ^ { 4 } } = a _ { 1 1 1 1 } { x } _ { 1 } ^ { 4 } + x _ { 2 } g ( x _ { 1 } , x _ { 2 } ) \geq 0$ for all $x = ( x _ { 1 } , x _ { 2 } ) ^ { \top } \geq 0$ , and hence, the copositivity of $\mathcal { A }$ is proved, as required. □

Similarly, using Theorem 3.2 (for the tensor $\Gamma \ : = \ : ( \gamma _ { i j k } )$ in the above proof),the following theorem is obtained easily.

Theorem 4.2.Let $\mathcal { A }$ be an 4th order 2 dimensional symmetric tensor with （204 $a _ { 1 1 1 1 } \geq 0$ and $a _ { 2 2 2 2 } \geq 0$ . Assume that one of the following conditions (1） and (2) holds,

$$
\begin{array} { r l r } & { } & { a _ { 1 2 2 2 } \geq 0 , \ a _ { 1 1 1 2 } \geq \displaystyle \frac { 1 } { 4 } a _ { 1 1 1 1 } - \sqrt { a _ { 1 1 1 1 } a _ { 1 2 2 2 } } , \ a _ { 1 2 2 1 } \geq \displaystyle \frac { 2 } { 3 } \big ( a _ { 1 2 2 2 } - 2 \sqrt { a _ { 1 1 1 1 } a _ { 1 2 2 2 } } \big ) ; } \\ & { } & { a _ { 1 1 1 2 } \geq 0 , \ a _ { 1 2 2 2 } \geq \displaystyle \frac { 1 } { 4 } a _ { 2 2 2 2 } - \sqrt { a _ { 1 1 1 2 } a _ { 2 2 2 2 } } , \ a _ { 1 2 2 1 } \geq \displaystyle \frac { 2 } { 3 } \big ( a _ { 1 1 1 2 } - 2 \sqrt { a _ { 1 1 1 2 } a _ { 2 2 2 2 } } \big ) . } \end{array}
$$

Then $\mathcal { A }$ is copositive.

Let $\mathcal { A }$ be an 4th order 3 dimensional symmetric tensor. Then for a vector $\boldsymbol { x } = ( x _ { 1 } , x _ { 2 } , x _ { 3 } ) ^ { \top }$ ，

$$
\begin{array} { r l r } {  { \mathcal { A } x ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 3 } a _ { i j k l } x _ { i } x _ { j } x _ { k } x _ { l } } } \\ & { } & { = a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } + a _ { 3 3 3 3 } x _ { 3 } ^ { 4 } + 4 a _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 3 } + 4 a _ { 1 3 3 3 } x _ { 1 } x _ { 3 } ^ { 3 } } \\ & { } & { + 4 a _ { 2 1 1 1 } x _ { 1 } ^ { 3 } x _ { 2 } + 4 a _ { 2 3 3 3 } x _ { 2 } x _ { 3 } ^ { 3 } + 4 a _ { 3 1 1 1 } x _ { 1 } ^ { 3 } x _ { 3 } + 4 a _ { 3 2 2 2 } x _ { 2 } ^ { 3 } x _ { 3 } } \\ & { } & { + 6 a _ { 1 1 2 2 } x _ { 1 } ^ { 2 } x _ { 2 } ^ { 2 } + 6 a _ { 1 1 3 3 } x _ { 1 } ^ { 2 } x _ { 3 } ^ { 2 } + 6 a _ { 2 2 3 3 } x _ { 2 } ^ { 2 } x _ { 3 } ^ { 2 } } \\ & { } & { + 1 2 a _ { 1 2 3 1 } x _ { 1 } ^ { 2 } x _ { 2 } x _ { 3 } + 1 2 a _ { 1 2 3 2 } x _ { 1 } x _ { 2 } ^ { 2 } x _ { 3 } + 1 2 a _ { 1 2 3 3 } x _ { 1 } x _ { 2 } x _ { 3 } ^ { 2 } . } \end{array}
$$

Now we give several suffcient conditions of 4th order copositive tensors with the help of ones of 3rd order copositive tensors in Section 3.

Theorem 4.3. Let $\mathcal { A }$ be an 4th order 3 dimensional symmetric tensor. Assume that

$$
\begin{array} { r l } & { a _ { 1 1 1 1 } \geq 0 , \ a _ { 2 2 2 2 } \geq 0 , \ a _ { 3 3 3 3 } \geq 0 , } \\ & { a _ { 1 1 1 2 } \geq 0 , \ a _ { 1 1 1 3 } \geq 0 , \ a _ { 1 2 2 2 } \geq 0 , \ a _ { 2 2 2 3 } \geq 0 , \ a _ { 1 3 3 3 } \geq 0 , \ a _ { 2 3 3 3 } \geq 0 , \ a _ { 2 3 3 3 } \geq 0 , } \\ & { \operatorname* { m a x } \{ a _ { 1 2 2 2 , \ a _ { 1 3 3 3 } } \} > 0 , \operatorname* { m a x } \{ a _ { 1 1 1 2 , \ a _ { 2 3 3 3 3 } } \} > 0 , \operatorname* { m a x } \{ a _ { 1 1 3 , \ a _ { 2 2 2 3 } } \} > 0 , } \\ & { 6 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } \geq 0 , \ 6 a _ { 1 1 3 3 } + \sqrt { a _ { 1 1 1 1 } a _ { 3 3 3 3 } } \geq 0 , \ 6 a _ { 2 2 3 3 } + \sqrt { a _ { 3 3 3 3 } a _ { 2 2 2 2 } } \geq 0 , } \\ & { 8 a _ { 1 2 2 2 } a _ { 1 3 3 } ^ { 3 } + 8 a _ { 1 2 2 3 } ^ { 3 } a _ { 1 3 3 3 } + 1 6 a _ { 1 2 2 2 } ^ { 2 } a _ { 1 3 3 3 } ^ { 2 } - 2 4 a _ { 1 2 2 2 } a _ { 1 2 2 3 } a _ { 1 3 3 3 } - 3 a _ { 1 2 2 3 } ^ { 2 } a _ { 1 2 3 3 } ^ { 2 } \geq ( 1 - a _ { 2 2 2 3 } ) , } \\ & { 8 a _ { 2 1 1 1 } a _ { 1 2 3 3 } ^ { 3 } + 8 a _ { 1 1 2 3 } ^ { 3 } a _ { 2 3 3 3 } + 1 6 a _ { 2 1 1 } a _ { 2 3 3 3 } ^ { 2 } - 2 4 a _ { 2 1 1 } a _ { 1 1 2 3 } a _ { 2 3 3 } a _ { 2 3 3 3 } - 3 a _ { 1 2 1 3 } ^ { 2 } a _ { 1 2 3 3 } ^ { 2 } \geq ( 1 - a _ { 2 2 3 } ) , } \\ & { 8 a _ { 3 1 1 1 } a _ { 1 2 2 3 } ^ { 3 } + 8 a _ { 1 1 2 3 } ^ { 3 } a _ { 2 2 2 } > ( 1 - a _ { 3 1 1 } a _ { 3 2 2 } ^ { 2 } - 2 4 a _ { 3 1 1 } a _ { 1 1 2 3 } a _ { 1 2 2 3 } + 2 a _ { 1 1 2 3 } a _ { 1 2 2 3 } ^ { 2 } \geq ( 1 - a _ { 2 2 3 } ) , } \\ &  8 a _ { 3 1 1 1 } a _ { 1 2 2 3 } ^ { 4 } + 8 a _ { 1 1 1 } ^ { 3 } a _ { 2 2 2 } ^ { 2 } \geq ( 1 - a _   \end{array}
$$

Then $\mathcal { A }$ is copositive.

Proof. Rewritten the homogeneous polynomial $\boldsymbol { \mathcal { A } } \boldsymbol { x } ^ { 4 }$ (4.2) as follows,

$$
\begin{array} { l } { \displaystyle \mathcal { A } \displaystyle x ^ { 4 } = \big ( \frac 1 2 a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 6 a _ { 1 1 2 2 } x _ { 1 } ^ { 2 } x _ { 2 } ^ { 2 } + \frac 1 2 a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } \big ) } \\ { \displaystyle \qquad + \big ( \frac 1 2 a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } + 6 a _ { 2 2 3 3 } x _ { 2 } ^ { 2 } x _ { 3 } ^ { 2 } + \frac 1 2 a _ { 3 3 3 3 } x _ { 3 } ^ { 4 } \big ) } \\ { \displaystyle \qquad + \big ( \frac 1 2 a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 6 a _ { 1 1 3 3 } x _ { 1 } ^ { 2 } x _ { 3 } ^ { 2 } + \frac 1 2 a _ { 3 3 3 3 } x _ { 3 } ^ { 4 } \big ) } \\ { \displaystyle \qquad + x _ { 1 } \big ( 4 a _ { 1 2 2 2 } x _ { 2 } ^ { 3 } + 6 a _ { 1 2 2 3 } x _ { 2 } ^ { 2 } x _ { 3 } + 6 a _ { 1 2 3 3 } x _ { 2 } x _ { 3 } ^ { 2 } + 4 a _ { 1 3 3 3 } x _ { 3 } ^ { 3 } \big ) } \\ { \displaystyle \qquad + x _ { 2 } \big ( 4 a _ { 2 1 1 1 } x _ { 3 } ^ { 3 } + 6 a _ { 1 1 2 3 } x _ { 1 } ^ { 2 } x _ { 3 } + 6 a _ { 1 2 3 3 } x _ { 1 } x _ { 3 } ^ { 2 } + 4 a _ { 2 3 3 3 } x _ { 3 } ^ { 3 } \big ) } \\ { \displaystyle \qquad + x _ { 3 } \big ( 4 a _ { 3 1 1 1 } x _ { 1 } ^ { 3 } + 6 a _ { 1 1 2 3 } x _ { 1 } ^ { 2 } x _ { 2 } + 6 a _ { 1 2 3 3 } x _ { 1 } x _ { 2 } ^ { 2 } + 4 a _ { 3 2 2 } x _ { 2 } ^ { 3 } \big ) . } \end{array}
$$

Let

$$
p _ { 1 } ( x _ { 1 } , x _ { 2 } ) = \frac { 1 } { 2 } a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 6 a _ { 1 1 2 2 } x _ { 1 } ^ { 2 } x _ { 2 } ^ { 2 } + \frac { 1 } { 2 } a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } .
$$

It follows from Lemma 2.1 that we can restrict $x$ to

Clearly, $\begin{array} { r } { p _ { 1 } ( 0 , 0 ) = 0 , ~ p _ { 1 } ( x _ { 1 } , 0 ) = \frac 1 2 a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } \geq 0 , ~ p _ { 1 } ( 0 , x _ { 2 } ) = \frac 1 2 a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } \geq 0 } \end{array}$ .Let we assume that both $x _ { 2 } > 0$ and $\begin{array} { r } { t = \frac { x _ { 1 } ^ { 2 } } { x _ { 2 } ^ { 2 } } } \end{array}$ S $x _ { 1 }$ and ose $x _ { 2 }$ are not zero. Without loss of generality, let

$$
p ( t ) = \frac { p _ { 1 } ( x _ { 1 } , x _ { 2 } ) } { x _ { 2 } ^ { 4 } } = \alpha t ^ { 2 } + \beta t + \gamma \ \mathrm { w i t h } \ \alpha = \frac { 1 } { 2 } a _ { 1 1 1 1 } , \ \beta = 6 a _ { 1 1 2 2 } , \ \gamma = \frac { 1 } { 2 } a _ { 2 2 2 2 } .
$$

It follows from Lemma 2.3 that the assumptions $a _ { 1 1 1 1 } \geq 0$ and $a _ { 2 2 2 2 } \geq 0$ together with the inequality $6 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } \geq 0$ mean $p ( t ) \geq 0$ for all $t \geq 0$ , and hence, $p _ { 1 } ( x _ { 1 } , x _ { 2 } ) \geq 0$ for all $x = ( x _ { 1 } , x _ { 2 } ) ^ { \top } \geq 0$ ：

Similarly, we also have

$$
p _ { 2 } ( x _ { 2 } , x _ { 3 } ) = \frac { 1 } { 2 } a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } + 6 a _ { 2 2 3 3 } x _ { 2 } ^ { 2 } x _ { 3 } ^ { 2 } + \frac { 1 } { 2 } a _ { 3 3 3 3 } x _ { 3 } ^ { 4 } \geq 0
$$

and

$$
p _ { 3 } ( x _ { 1 } , x _ { 3 } ) = \frac { 1 } { 2 } a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 6 a _ { 1 1 3 3 } x _ { 1 } ^ { 2 } x _ { 3 } ^ { 2 } + \frac { 1 } { 2 } a _ { 3 3 3 3 } x _ { 3 } ^ { 4 } \geq 0 .
$$

Let

$$
F _ { 1 } ( x _ { 2 } , x _ { 3 } ) = 4 a _ { 1 2 2 2 } x _ { 2 } ^ { 3 } + 6 a _ { 1 2 2 3 } x _ { 2 } ^ { 2 } x _ { 3 } + 6 a _ { 1 2 3 3 } x _ { 2 } x _ { 3 } ^ { 2 } + 4 a _ { 1 3 3 3 } x _ { 3 } ^ { 3 } .
$$

Then the homogeneous polynomial $F _ { 1 } ( x _ { 2 } , x _ { 3 } )$ may be written as

$$
F _ { 1 } ( x _ { 2 } , x _ { 3 } ) = \Gamma y ^ { 3 } = \sum _ { i , j , k = 1 } ^ { 2 } \gamma _ { i j k } y _ { i } y _ { j } y _ { k } { \mathrm { ~ f o r ~ } } y = ( x _ { 2 } , x _ { 3 } ) ^ { \top } ,
$$

where $\Gamma = \left( \gamma _ { i j k } \right)$ is 3rd order 2 dimensional symmetric tensor with its entries

$$
\gamma _ { 1 1 1 } = 4 a _ { 1 2 2 2 } , \gamma _ { 1 1 2 } = 2 a _ { 1 2 2 3 } , \gamma _ { 1 2 2 } = 2 a _ { 1 2 3 3 } , \gamma _ { 2 2 2 } = 4 a _ { 1 3 3 3 } .
$$

Then by assumptions, we have

$$
\begin{array} { r l } & { \quad 4 \gamma _ { 1 1 1 } \gamma _ { 1 2 2 } ^ { 3 } + 4 \gamma _ { 1 1 2 } ^ { 3 } \gamma _ { 2 2 2 } + \gamma _ { 1 1 1 } ^ { 2 } \gamma _ { 2 2 2 } ^ { 2 } - 6 \gamma _ { 1 1 1 } \gamma _ { 1 1 2 } \gamma _ { 1 2 2 } \gamma _ { 2 2 2 } - 3 \gamma _ { 1 1 2 } ^ { 2 } \gamma _ { 1 2 2 } ^ { 2 } } \\ & { = 1 6 \big ( 8 a _ { 1 2 2 2 } a _ { 1 2 3 3 } ^ { 3 } + 8 a _ { 1 2 2 3 } ^ { 3 } a _ { 1 3 3 3 } + 1 6 a _ { 1 2 2 2 } ^ { 2 } a _ { 1 3 3 3 } ^ { 2 } - 2 4 a _ { 1 2 2 2 } a _ { 1 2 3 3 } a _ { 1 3 3 3 } } \\ & { \quad \quad - 3 a _ { 1 2 2 3 } ^ { 2 } a _ { 1 2 3 3 } ^ { 2 } \big ) \geq 0 . } \end{array}
$$

From Theorem 3.1, it follows that $\Gamma$ is copositive, i.e.,

$$
F _ { 1 } ( x _ { 2 } , x _ { 3 } ) = \Gamma y ^ { 3 } \geq 0 { \mathrm { ~ f o r ~ a l l ~ } } y = ( x _ { 2 } , x _ { 3 } ) ^ { \top } \geq 0
$$

Similarly, we must have

$$
F _ { 2 } ( x _ { 1 } , x _ { 3 } ) = 4 a _ { 2 1 1 1 } x _ { 1 } ^ { 3 } + 6 a _ { 1 1 2 3 } x _ { 1 } ^ { 2 } x _ { 3 } + 6 a _ { 1 2 3 3 } x _ { 1 } x _ { 3 } ^ { 2 } + 4 a _ { 2 3 3 3 } x _ { 3 } ^ { 3 } \geq 0
$$

and

$$
F _ { 3 } ( x _ { 1 } , x _ { 2 } ) = 4 a _ { 3 1 1 1 } x _ { 1 } ^ { 3 } + 6 a _ { 1 1 2 3 } x _ { 1 } ^ { 2 } x _ { 2 } + 6 a _ { 1 2 2 3 } x _ { 1 } x _ { 2 } ^ { 2 } + 4 a _ { 3 2 2 2 } x _ { 2 } ^ { 3 } \geq 0 .
$$

Thus, for all $x = ( x _ { 1 } , x _ { 2 } , x _ { 3 } ) ^ { \top } \geq 0$ ， we have

$$
\begin{array} { r l } & { A x ^ { 4 } = p _ { 1 } ( x _ { 1 } , x _ { 2 } ) + p _ { 2 } ( x _ { 2 } , x _ { 3 } ) + p _ { 3 } ( x _ { 1 } , x _ { 3 } ) } \\ & { \qquad + x _ { 1 } F _ { 1 } ( x _ { 2 } , x _ { 3 } ) + x _ { 2 } F _ { 2 } ( x _ { 1 } , x _ { 3 } ) + x _ { 3 } F _ { 3 } ( x _ { 1 } , x _ { 2 } ) \geq 0 . } \end{array}
$$

Namely, $\mathcal { A }$ is copositive,as required.

Now we give a simpler sufficient condition of copositive tensors using Theorem 3.2 (for the tensor $\Gamma = \left( \gamma _ { i j k } \right)$ in the above proof).

Theorem 4.4.Let $\mathcal { A }$ be an 4th order 3 dimensional symmetric tensor. Assume that

$$
\begin{array} { l } { { a _ { 1 1 1 } \geq 0 , \ a _ { 2 2 2 2 } \geq 0 , \ a _ { 3 3 3 3 } \geq 0 , } } \\ { { a _ { 1 1 1 2 } \geq 0 , \ a _ { 1 1 1 3 } \geq 0 , \ a _ { 1 2 2 2 } \geq 0 , \ a _ { 2 2 2 3 } \geq 0 , \ a _ { 1 3 3 3 } \geq 0 , \ a _ { 2 3 3 3 } \geq 0 , } } \\ { { a _ { 1 1 2 2 } \geq - \displaystyle \frac { 1 } { 6 } \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 } } , \ a _ { 1 1 3 3 } \geq - \displaystyle \frac { 1 } { 6 } \sqrt { a _ { 1 1 1 1 } a _ { 3 3 3 3 } } , \ a _ { 2 2 3 3 } \geq - \displaystyle \frac { 1 } { 6 } \sqrt { a _ { 3 3 3 3 } a _ { 2 2 2 2 } } , } } \\ { { a _ { 1 2 2 3 } \geq \displaystyle \frac { 2 } { 3 } \operatorname* { m a x } \{ a _ { 1 2 2 2 } - 2 \sqrt { a _ { 1 2 2 2 } a _ { 1 3 3 } } , \ a _ { 2 2 2 3 } - 2 \sqrt { a _ { 1 1 1 2 } a _ { 2 2 2 3 } } \} , } } \\ { { a _ { 1 2 3 3 } \geq \displaystyle \frac { 2 } { 3 } \operatorname* { m a x } \{ a _ { 2 3 3 3 } - 2 \sqrt { a _ { 1 1 1 2 } a _ { 2 3 3 3 } } , \ a _ { 1 3 3 3 } - 2 \sqrt { a _ { 1 2 2 2 } a _ { 1 3 3 } } \} , } } \\ { { a _ { 1 1 2 3 } \geq \displaystyle \frac { 2 } { 3 } \operatorname* { m a x } \{ a _ { 1 1 1 3 } - 2 \sqrt { a _ { 1 1 1 3 } a _ { 2 2 2 3 } } , \ a _ { 1 1 1 2 } - 2 \sqrt { a _ { 1 1 1 2 } a _ { 2 3 3 } } \} . } } \end{array}
$$

Then $\mathcal { A }$ is copositive.

Theorem 4.5.Let $\mathcal { A }$ be an 4th order 3 dimensional symmetric tensor. Assume that

$$
\begin{array} { r l } & { \mathrm { O r t r a n ~ \ " \ " { \sim } ~ } \lambda _ { \mathrm { B } } , \mathrm { a p p . } > 0 , \quad \lambda _ { \mathrm { t r } } , \mathrm { o u p . } > 0 , \quad \lambda _ { \mathrm { t r } } , \mathrm { a n } > 0 , \mathrm { i . . } \mathrm { o u p . } > 0 , \mathrm { i . } \mathrm { , } \mathrm { } \mathrm { , } \mathrm { } \mathrm { } \mathrm { , } \mathrm { } \mathrm { } \mathrm { } \mathrm { , } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { , } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm  { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm   \\ &  \mathrm  O a n . \mathrm  \ a n . \ a n y \to \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm { } \mathrm   \end{array}
$$

Then A is copositive.

Proof. Rewritten the homogeneous polynomial $\boldsymbol { \mathcal { A } } \boldsymbol { x } ^ { 4 }$ (4.2) as follows,

$$
\begin{array} { r l } { 4 \mathbf { r } ^ { 4 } - \frac { 1 } { 3 } ( ( \sqrt { \iota _ { 1 1 1 1 1 2 } } \varepsilon _ { 1 } ^ { 2 } - \sqrt { \iota _ { 2 2 2 2 2 } } \varepsilon _ { 2 } ^ { 2 } ) ^ { \beta } + ( \sqrt { \iota _ { 2 1 1 1 1 } } \varepsilon _ { 1 } ^ { 2 } - \sqrt { \iota _ { 2 1 1 1 3 3 1 } } \varepsilon _ { 3 } ^ { 2 } ) ^ { 2 } + ( \sqrt { \iota _ { 3 2 3 3 3 3 } } \varepsilon _ { 3 } ^ { 2 } - \sqrt { \iota _ { 3 2 } }   } \\ & {   + \frac { 1 } { 9 } \varepsilon _ { 1 } ( 3 \mathrm { a t m } \varepsilon _ { 1 } ^ { 3 } + 3 6 \mathrm { a } _ { 1 1 2 2 } \varepsilon _ { 1 } ^ { 3 } \varepsilon _ { 2 } + 2 ( 9 \mathrm { a } _ { 1 1 2 2 } \varepsilon _ { 1 } ) \varepsilon _ { 3 } ^ { 2 } ) \varepsilon _ { 1 } \varepsilon _ { 2 } ^ { 2 } + 3 6 \mathrm { a } _ { 1 2 2 2 } \varepsilon _ { 2 } ^ { 3 } \varepsilon _ { 2 } ^ { 3 } ) } \\ & { + \frac { 1 } { 9 } \varepsilon _ { 2 } ( 3 \mathrm { a r g r } _ { 2 } \varepsilon _ { 3 } ^ { 2 } + 3 6 \mathrm { a } _ { 2 2 3 } \varepsilon _ { 2 } ^ { 2 } ) \varepsilon _ { 3 } - 2 ( 9 \mathrm { o } _ { 2 2 3 3 3 } \varepsilon _ { 3 } ^ { 2 } ) \varepsilon _ { 3 } ^ { 2 } } \\ & { + \frac { 1 } { 9 } \varepsilon _ { 3 } ( 3 \mathrm { a r g r } _ { 3 } \varepsilon _ { 3 } ^ { 2 } + 3 6 \mathrm { a s s } _ { 3 1 } \varepsilon _ { 3 } ^ { 2 } - 2 ( 9 \mathrm { o } _ { 1 3 1 3 } \varepsilon _ { 1 } ^ { 2 } \varepsilon _ { 3 } + \sqrt { \iota _ { 3 1 1 1 2 } } \varepsilon _ { 1 } ^ { 2 } \varepsilon _ { 3 } + 3 6 \mathrm { a s s } _ { 3 3 } \varepsilon _ { 3 } ^ { 3 } )  } \\ & { + \frac { 1 } { 9 } \varepsilon _ { 1 } ( 3 \mathrm { a r g r } _ { 3 } ^ { 2 } + 3 8 \mathrm { a s s } _ { 1 } \varepsilon _ { 3 } ^ { 2 } + 2 ( 9 \mathrm { a } _ { 1 3 3 } + \sqrt { \iota _ { 1 1 1 2 } } \varepsilon _ { 3 } + 3 6 \mathrm { a s s } _ { 1 } \varepsilon _ { 3 } )  } \\ &  + \frac { 2 } { 9 } \varepsilon _ { 1 } ^ { 2 } ( ( 9 \mathrm { a t m } + \sqrt { \iota _ { 1 1 1 2 2 } } \varepsilon _ { 2 } ) \varepsilon _ { 2 } ^ { 2 } + \frac { 5 }  4 4 \ \end{array}
$$

Let

$$
F _ { 1 } ( x _ { 1 } , x _ { 2 } ) = 3 a _ { 1 1 1 1 } x _ { 1 } ^ { 3 } + 3 6 a _ { 1 1 1 2 } x _ { 1 } ^ { 2 } x _ { 2 } + 2 \left( 9 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } \right) x _ { 1 } x _ { 2 } ^ { 2 } + 3 6 a _ { 1 2 2 2 } x _ { 2 } ^ { 3 } .
$$

Then the homogeneous polynomial $F _ { 1 } ( x _ { 1 } , x _ { 2 } )$ may be written as

$$
F _ { 1 } ( x _ { 1 } , x _ { 2 } ) = \Gamma y ^ { 3 } = \sum _ { i , j , k = 1 } ^ { 2 } \gamma _ { i j k } y _ { i } y _ { j } y _ { k } { \mathrm { ~ f o r ~ } } y = ( x _ { 1 } , x _ { 2 } ) ^ { \top } ,
$$

where $\Gamma = \left( \gamma _ { i j k } \right)$ is 3rd order 2 dimensional symmetric tensor with its entries

$$
\gamma _ { 1 1 1 } = 3 a _ { 1 1 1 1 } , \ \gamma _ { 1 1 2 } = 1 2 a _ { 1 1 1 2 } , \ \gamma _ { 1 2 2 } = \frac { 2 } { 3 } \left( 9 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } \right) , \ \gamma _ { 2 2 2 } = 3 6 a _ { 1 2 2 2 } .
$$

Then by assumptions, we have

$$
\begin{array} { r l } & { \quad 4 \gamma _ { 1 1 1 7 } \gamma _ { 1 2 2 } ^ { 3 } + 4 \gamma _ { 1 1 2 } ^ { 3 } \gamma _ { 2 2 2 } ^ { 5 } + \gamma _ { 1 1 1 } ^ { 2 } \gamma _ { 2 2 2 } ^ { 2 } - 6 \gamma _ { 1 1 1 } \gamma _ { 1 1 2 } \gamma _ { 1 2 2 } \gamma _ { 2 2 2 } - 3 \gamma _ { 1 1 2 } ^ { 2 } \gamma _ { 1 2 2 } ^ { 2 } } \\ & { - 4 ( 3 a _ { 1 1 1 } ) \left( \frac { 2 } { 3 } \left( 9 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 } a _ { 2 2 2 2 } } \right) \right) ^ { 3 } + 4 ( 1 2 a _ { 1 1 1 2 } ) ^ { 3 } ( 3 6 a _ { 1 2 2 2 } ) + ( 3 a _ { 1 1 1 } ) ^ { 2 } ( 3 6 a _ { 1 2 2 } } \\ & { \quad - 6 ( 3 a _ { 1 1 1 } ) ( 1 2 a _ { 1 1 2 } ) ( \frac { 2 } { 3 } \left( 9 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 } a _ { 2 2 2 } } \right) ) \left( 3 6 a _ { 1 2 2 2 } \right) } \\ & { \quad - 3 ( 1 2 a _ { 1 1 1 2 } ) ^ { 2 } \left( \frac { 2 } { 3 } \left( 9 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 } } \right) \right) ^ { 2 } } \\ & { \quad - \frac { 1 6 } { 9 } ( 2 a _ { 1 1 1 } ( 9 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) ) ^ { 3 } + 3 ^ { 7 } \cdot 4 \frac { 3 } { 1 2 2 a _ { 1 2 2 } a _ { 1 1 2 } ^ { 3 } } + 3 ^ { 8 } a _ { 1 1 1 } ^ { 2 } a _ { 1 2 2 2 } ^ { 2 } } \\ & { \quad - \frac { 1 6 } { 9 } ( 2 a _ { 1 1 1 } a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 } } ) ^ { 2 } + \sqrt { a _ { 1 1 1 } a _ { 2 2 2 } } ) - 3 ^ { 3 } \cdot 4 a _ { 1 1 2 } ^ { 2 } ( 9 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 } a _ { 2 2 2 } } ) ^ { 2 } \} } \\ & { \quad - 3 ^ { 6 } \cdot 4 a _ { 1 1 1 } a _ { 1 1 2 2 1 } \gamma _ { 3 2 } ( 9 a _ { 1 2 2 } + \sqrt { a _ { 1 1 1 } a _ { 2 2 2 } } ) - 3 ^ { 3 } \cdot 4 a _ { 1 1 1 } ^ { 2 } ( 9 a _ { 1 2 2 } + \sqrt { a _ { 1 1 1 } a _ { 2 2 2 } } ) ^ { 2 } \} } \end{array}
$$

From Theorem 3.1, it follows that $\Gamma$ is copositive, i.e.,

$$
F _ { 1 } ( x _ { 1 } , x _ { 2 } ) = \Gamma y ^ { 3 } \geq 0 { \mathrm { ~ f o r ~ a l l ~ } } y = ( x _ { 1 } , x _ { 2 } ) ^ { \top } \geq 0
$$

Similarly, we must have

（20 $F _ { 2 } ( x _ { 2 } , x _ { 3 } ) = 3 a _ { 2 2 2 2 } x _ { 2 } ^ { 3 } + 3 6 a _ { 2 2 2 3 } x _ { 2 } ^ { 2 } x _ { 3 } + 2 \left( 9 a _ { 2 2 3 3 } + \sqrt { a _ { 3 3 3 3 } a _ { 2 2 2 2 } } \right) x _ { 2 } x _ { 3 } ^ { 2 } + 3 6 a _ { 2 3 3 3 } x _ { 3 } ^ { 3 } \geq 0$ （204号and

$$
F _ { 3 } ( x _ { 1 } , x _ { 3 } ) = 3 a _ { 3 3 3 3 } x _ { 3 } ^ { 3 } + 3 6 a _ { 1 3 3 3 } x _ { 1 } x _ { 3 } ^ { 2 } + 2 \left( 9 a _ { 1 1 3 3 } + \sqrt { a _ { 1 1 1 1 } a _ { 3 3 3 3 } } \right) x _ { 1 } ^ { 2 } x _ { 3 } + 3 6 a _ { 1 1 1 3 } x _ { 1 } ^ { 3 } \geq 0
$$

Let

$$
p _ { 1 } ( x _ { 2 } , x _ { 3 } ) = \left( 9 a _ { 1 1 2 2 } + { \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } } \right) x _ { 2 } ^ { 2 } + 5 4 a _ { 1 1 2 3 } x _ { 2 } x _ { 3 } + \left( 9 a _ { 1 1 3 3 } + { \sqrt { a _ { 1 1 1 } a _ { 3 3 3 3 } } } \right) x _ { 3 } ^ { 2 } .
$$

It follows from (strict） copositivity of $2 \times 2$ matrix (or Lemma 2.3) that （204号 $p _ { 1 } ( x _ { 2 } , x _ { 3 } ) \ge 0$ for all $( x _ { 2 } , x _ { 3 } ) ^ { \top } \geq 0$ if and only if

$$
\begin{array} { r l } & { 9 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } \geq 0 , ~ 9 a _ { 1 1 3 3 } + \sqrt { a _ { 1 1 1 1 } a _ { 3 3 3 3 } } \geq 0 , } \\ & { 2 7 a _ { 1 1 2 3 } + \sqrt { ( 9 a _ { 1 1 2 2 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) \left( 9 a _ { 1 1 3 3 } + \sqrt { a _ { 1 1 1 1 } a _ { 3 3 3 3 } } \right) } \geq 0 . } \end{array}
$$

Similarly, we also have

$p _ { 2 } ( x _ { 1 } , x _ { 3 } ) = \left( 9 a _ { 1 1 2 2 } + { \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } } \right) x _ { 1 } ^ { 2 } + 5 4 a _ { 1 2 2 3 } x _ { 1 } x _ { 3 } + \left( 9 a _ { 2 2 3 3 } + { \sqrt { a _ { 3 3 3 3 } a _ { 2 2 2 2 } } } \right) x _ { 3 } ^ { 2 } \geq 0 .$ 0 and

$$
p _ { 3 } ( x _ { 1 } , x _ { 2 } ) = ( 9 a _ { 1 1 3 3 } + \sqrt { a _ { 1 1 1 1 } a _ { 3 3 3 3 } } ) x _ { 1 } ^ { 2 } + 5 4 a _ { 1 2 3 3 } x _ { 1 } x _ { 2 } + ( 9 a _ { 2 2 3 3 } + \sqrt { a _ { 3 3 3 3 } a _ { 2 2 2 2 } } ) x _ { 2 } ^ { 2 } \geq 0 ,
$$

Thus, for all $x = ( x _ { 1 } , x _ { 2 } , x _ { 3 } ) ^ { \top } \geq 0$ ， we have

$$
\begin{array} { l } { \displaystyle \mathcal { A } x ^ { 4 } = \frac { 1 } { 3 } \left( \sqrt { a _ { 1 1 1 1 } } x _ { 1 } ^ { 2 } - \sqrt { a _ { 2 2 2 2 } } x _ { 2 } ^ { 2 } \right) ^ { 2 } + \frac { 1 } { 3 } \left( \sqrt { a _ { 1 1 1 1 } } x _ { 1 } ^ { 2 } - \sqrt { a _ { 3 3 3 3 } } x _ { 3 } ^ { 2 } \right) ^ { 2 } } \\ { \displaystyle \quad \quad + \frac { 1 } { 3 } \left( \sqrt { a _ { 3 3 3 3 } } x _ { 3 } ^ { 2 } - \sqrt { a _ { 2 2 2 2 } } x _ { 2 } ^ { 2 } \right) ^ { 2 } } \\ { \displaystyle \quad \quad + \frac { 1 } { 9 } ( x _ { 1 } F _ { 1 } ( x _ { 1 } , x _ { 2 } ) + x _ { 2 } F _ { 2 } ( x _ { 2 } , x _ { 3 } ) + x _ { 3 } F _ { 3 } ( x _ { 1 } , x _ { 3 } ) ) } \\ { \displaystyle \quad \quad + \frac { 2 } { 9 } ( x _ { 1 } ^ { 2 } p _ { 1 } ( x _ { 2 } , x _ { 3 } ) + 2 x _ { 2 } ^ { 2 } p _ { 2 } ( x _ { 1 } , x _ { 3 } ) + 2 x _ { 3 } ^ { 2 } p _ { 3 } ( x _ { 1 } , x _ { 2 } ) ) \geq 0 . } \end{array}
$$

Namely, $\mathcal { A }$ is copositive, as required.

Remark 4.1. In this section, the conclusions are proved by reducing dimensions or orders of tensor. For example, Theorems 4.5 and 4.3， an 4th order 3 dimensional tensor is decomposed into three 3rd order $\mathcal { Z }$ dimensional tensors and three 2nd order $\boldsymbol { \mathcal { Z } }$ dimensional tensors， and then， by studying the copositivity of these lower dimensional and lower order tensors, the desired conclusions are proved. Similarly， we may decompose an 4th order 3 dimensional tensor into three 3rd order 3 dimensional tensors $\mathbf { { { T } } _ { 1 } }$ ， $\mathbf { { { T } } _ { 2 } }$ ， $\mathbf { { { T } _ { 3 } } }$ ，

$$
\begin{array} { r l } & { \mathcal { A } \ b { x } ^ { 4 } = x _ { 1 } ( a _ { 1 1 1 1 } x _ { 1 } ^ { 3 } + 2 a _ { 1 1 1 2 } x _ { 1 } ^ { 2 } x _ { 2 } + 3 a _ { 1 1 2 2 } x _ { 1 } x _ { 2 } ^ { 2 } + 2 a _ { 1 2 2 2 } x _ { 2 } ^ { 3 } + 2 a _ { 1 3 3 3 } x _ { 3 } ^ { 3 } } \\ & { \qquad + 3 a _ { 1 1 3 3 } x _ { 1 } x _ { 3 } ^ { 2 } + 2 a _ { 1 1 1 3 } x _ { 1 } ^ { 2 } x _ { 3 } + 4 a _ { 1 1 2 3 } x _ { 1 } x _ { 2 } x _ { 3 } + 4 a _ { 1 2 2 3 } x _ { 2 } ^ { 2 } x _ { 3 } + 4 a _ { 1 2 3 3 } x _ { 2 } x _ { 3 } ^ { 2 } ) } \\ & { \qquad + x _ { 2 } ( 2 a _ { 1 1 2 } x _ { 1 } ^ { 3 } + 3 a _ { 1 1 2 2 } x _ { 1 } ^ { 2 } x _ { 2 } + 2 a _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 2 } + a _ { 2 2 2 2 } x _ { 2 } ^ { 3 } + 2 a _ { 2 3 3 3 } x _ { 3 } ^ { 3 } } \\ & { \qquad + 4 a _ { 1 2 3 3 } x _ { 1 } x _ { 3 } ^ { 2 } + 4 a _ { 1 1 2 3 } x _ { 1 } ^ { 2 } x _ { 3 } + 4 a _ { 1 2 2 3 } x _ { 1 } x _ { 2 } x _ { 3 } + 2 a _ { 2 2 2 3 } x _ { 2 } ^ { 2 } x _ { 3 } + 3 a _ { 2 2 3 3 } x _ { 2 } x _ { 3 } ^ { 2 } ) } \\ & { \qquad + x _ { 3 } ( 2 a _ { 1 1 1 3 } x _ { 1 } ^ { 3 } + 4 a _ { 1 1 2 3 } x _ { 1 } ^ { 2 } x _ { 2 } + 4 a _ { 1 2 2 3 } x _ { 1 } x _ { 2 } ^ { 2 } + 2 a _ { 2 2 2 3 } x _ { 2 } ^ { 3 } + a _ { 3 3 3 3 } x _ { 3 } ^ { 3 } } \\ & { \qquad + 2 a _ { 1 3 3 } x _ { 1 } x _ { 2 } ^ { 3 } + 3 a _ { 1 3 3 } x _ { 1 } ^ { 2 } x _ { 3 } + 4 a _ { 1 2 3 3 } x _ { 1 } x _ { 2 } x _ { 3 } + 3 a _ { 2 2 3 3 } x _ { 2 } ^ { 2 } x _ { 3 } + 2 a _ { 2 3 3 3 } x _ { 2 } x _ { 3 } ^ { 2 } ) } \\ & { \qquad + x _ { 1 } \Gamma _ { 1 } x ^ { 3 } + x _ { 2 } \Gamma _ { 2 } x ^ { 3 } + x _ { 3 } \Gamma _ { 3 } x ^ { 3 } . } \end{array}
$$

Then we can obtain other sufficient conditions of copositivity of an 4th order 3 dimensional tensor A by Theorems 3.4 and 3.5. Here we omit it. This way to reducing dimensions or orders of tensor may be a very important method of analysing higher order tensors in future.

# 5 Checking vacuum stability of $\mathbb { Z } _ { 3 }$ scalar dark matter

Kannike [12,13] presented a physical example defined by scalar dark matter stable under a $\mathbb { Z } _ { 3 }$ discrete group, that is,the most general scalar quartic potential of the SM Higgs $\mathbf { H } _ { 1 }$ ，an inert doublet $\mathbf { H } _ { 2 }$ and a complex singlet $\mathbf { S }$ which is symmetric under a $\mathbb { Z } _ { 3 }$ group is

$$
\begin{array} { l } { { V ( h _ { 1 } , h _ { 2 } , s ) = \lambda _ { 1 } | H _ { 1 } | ^ { 4 } + \lambda _ { 2 } | H _ { 2 } | ^ { 4 } + \lambda _ { 3 } | H _ { 1 } | ^ { 2 } | H _ { 2 } | ^ { 2 } + \lambda _ { 4 } ( H _ { 1 } ^ { \dagger } H _ { 2 } ) ( H _ { 2 } ^ { \dagger } H _ { 1 } ) } } \\ { { \displaystyle ~ + \lambda _ { 5 } | S | ^ { 4 } + \lambda _ { 3 } | S | ^ { 2 } | H _ { 1 } | ^ { 2 } + \lambda _ { 5 2 } | S | ^ { 2 } | H _ { 2 } | ^ { 2 } } } \\ { { \displaystyle ~ + \frac { 1 } { 2 } ( \lambda _ { 5 1 2 } S ^ { 2 } H _ { 1 } ^ { \dagger } H _ { 2 } + \lambda _ { 5 1 2 } ^ { * } S ^ { \dagger 2 } H _ { 2 } ^ { \dagger } H _ { 1 } ) } } \\ { { \displaystyle ~ = \lambda _ { 1 } h _ { 4 } ^ { 3 } + \lambda _ { 2 } h _ { 2 } ^ { 4 } + \lambda _ { 3 } h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } + \lambda _ { 4 } \rho ^ { 2 } h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } } } \\ { { \displaystyle ~ + \lambda _ { . 5 s ^ { 4 } } + \lambda _ { 3 1 } s ^ { 2 } h _ { 1 } ^ { 2 } + \lambda _ { 5 2 } s ^ { 2 } h _ { 2 } ^ { 2 } - \lambda _ { 5 1 2 } | \rho s ^ { 2 } h _ { 1 } h _ { 2 } } } \\ { { \displaystyle ~ = \Gamma z ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 3 } \gamma _ { i j k } z _ { k } z _ { j } z _ { k } z _ { l } } , } \end{array}
$$

where $z = ( z _ { 1 } , z _ { 2 } , z _ { 3 } ) ^ { \top } = ( h _ { 1 } , h _ { 2 } , s ) ^ { \top }$ ， the orbit space parameter $\rho \in [ 0 , 1 ]$

$$
h _ { 1 } = \vert { H _ { 1 } } \vert  , ~ h _ { 2 } = \vert { H _ { 2 } } \vert , ~ H _ { 2 } ^ { \dagger } H _ { 1 } = h _ { 1 } h _ { 2 } \rho e ^ { i \phi } , S = s e ^ { i \phi s } , \lambda _ { S 1 2 } = - \vert { \lambda _ { S 1 2 } } \vert { , }
$$

（20 $\mathbf { \vec { r } } = \left( \gamma _ { i j k l } \right)$ is an 4th order 3 dimensional real symmetric tensor with

$$
\begin{array} { r l } & { \gamma _ { 1 1 1 1 } = \lambda _ { 1 } , \ \gamma _ { 2 2 2 2 } = \lambda _ { 2 } , \ \gamma _ { 3 3 3 3 } = \lambda _ { S } , } \\ & { \gamma _ { 1 1 2 2 } = \displaystyle \frac { 1 } { 6 } ( \lambda _ { 3 } + \lambda _ { 4 } \rho ^ { 2 } ) , \ \gamma _ { 1 1 3 3 } = \frac { 1 } { 6 } \lambda _ { S 1 } , \ \gamma _ { 2 2 3 3 } = \frac { 1 } { 6 } \lambda _ { S 2 } , } \\ & { \gamma _ { 1 2 3 3 } = - \displaystyle \frac { 1 } { 1 2 } | \lambda _ { S 1 2 } | \rho , \ \gamma _ { i j k l } = 0 \ \mathrm { f o r ~ t h e ~ o t h e r s } . } \end{array}
$$

Clearly, $z \geq 0$ . It follows from Theorem 4.5 that the conditions of (strict copositivity of the tensor $\mathbf { \delta T }$ (that is, $V ( h _ { 1 } , h _ { 2 } , s ) = \Gamma z ^ { 4 } \geq 0 ( > 0 ) )$ are

$$
\begin{array} { r l } & { \lambda _ { 1 } > 0 , \lambda _ { 2 } > 0 , \lambda _ { S } > 0 , } \\ & { 3 \lambda _ { 3 } + 3 \lambda _ { 4 } \rho ^ { 2 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { 2 } } \ge 0 ( > 0 ) , 3 \lambda _ { S 1 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { S } } \ge 0 ( > 0 ) , } \\ & { 3 \lambda _ { S 2 } + 2 \sqrt { \lambda _ { S } \lambda _ { 2 } } \ge 0 ( > 0 ) , } \\ & { - \displaystyle \frac { 9 } { 4 } | \lambda _ { S 1 2 } | \rho + \sqrt { \left( 3 \lambda _ { S 1 } + 2 \sqrt { \lambda _ { 1 } \lambda _ { S } } \right) \left( 3 \lambda _ { S 2 } + 2 \sqrt { \lambda _ { S } \lambda _ { 2 } } \right) } \ge 0 ( > 0 ) } \end{array}
$$

So these conditions assure the potential $V ( h _ { 1 } , h _ { 2 } , s )$ under a $\mathbb { Z } _ { 3 }$ group is bounded from below, and hence, this guarantees the vacuum stability for $\mathbb { Z } _ { 3 }$ scalar dark matter.

# References

[1] Balaji, R., Palpandi, K.: Positive definite and Gram tensor complementarity problems. Optim.Lett. 12(3), 639-648 (2018)   
[2] Bai, X.L., Huang, Z.H.，Wang, Y.: Global uniqueness and solvability for tensor complementarity problems. J. Optim. Theory Appl. 170(1), 72-84 (2016)   
[3] Che， M.， Qi, L.， Wei， Y.: Stochastic $R _ { 0 }$ tensors to stochastic tensor complementarity problems, Optim. Lett. 13(2） 261-279 (2019)   
[4] Che, M.L., Qi, L., Wei, Y.M.: Positive-definite tensors to nonlinear complementarity problems. J. Optim. Theory Appl. 168(2),475-487 (2016)   
[5] Chen, H., Huang, Z., Qi, L.: Copositivity Detection of Tensors: Theory and Algorithm, J. Optim. Theory Appl. 174(3)(2017), 746-761   
[6] Chen, H., Huang, Z., Qi, L.: Copositive tensor detection and its applications in physics and hypergraphs, Compu. Optim. Appl. 69(1)(2018), 133-158   
[7] Chen, H., Wang, Y.: High-order copositive tensors and its applications, J. Appl. Anal. Compu. 8(6)(2018) 1863-1885 [8] Chen， H., Qi,L., Song，Y.: Column suficient tensors and tensor complementarity problems. Front. Math. China 13(2), 255-276 (2018)   
[9] Ding, W., Luo, Z., Qi, L.: $P$ -tensors, $P _ { 0 }$ -tensors,and their applications. Linear Algebra Appl. 555, 336-354 (2018)   
[10] Gowda, M.S.: Polynomial complementarity problems. Pac. J. Optim. 13(2), 227-241 (2017)   
[11] Huang, H., Qi, L.: Formulating an n-person noncooperative game as a tensor complementarity problem, Compu. Optim. Appl., 66:3(2017),557- 576.   
[12] Kannike, K.: Vacuum stability of a general scalar potential of a few fields,Eur. Phys. J.C(2016) 76: 324.   
[13] Kannike, K.: Erratum to: Vacuum stability of a general scalar potential of a few felds, Eur. Phys. J. C (2018) 78: 355.   
[14] Kannike, K.: Vacuum stability conditions from copositivity criteria, Eur. Phys. J. C(2012) 72: 2093   
[15] Li, L.， Zhang，X.， Huang, Z.， Qi， L.: Test of copositive tensors, J. Industrial Manag. Optim. April 2019, 15(2): 881-891   
[16] Luo, Z., Qi, L., Xiu, N.: The sparsest solutions to Z-tensor complementarity problems. Optim. Lett.11(3), 471-482 (2017)   
[17] Nie, J., Yang, Z., Zhang, X,: A Complete Semidefinite Algorithm for Detecting Copositive Matrices and Tensors, SIAM J. Optim., 28(4)(2018), 2902-2921   
[18] Qi, L., Song, Y: An even order symmetric $B$ tensor is positive definite, Linear Algebra Appl. 457 (2014) 303-312.   
[19] Qi, L.: Eigenvalues of a real supersymmetric tensor, J. Symbolic Comput:40(2005） 1302-1324.   
[20] Qi, L.: Symmetric Nonnegative Tensors and Copositive Tensors, Linear Algebra Appl., 439(2013) 228-238. [21] Qi, L.: Chen, H., Chen, Y., Tensor Eigenvalues and Their Applications, Springer Singapore, 2018 [22] Qi, L., Luo, Z.: Tensor Analysis: Spectral Theory and Special Tensors. SIAM, Philadelpia (2017) [23] Song, Y.， Qi, L.: Necessary and sufficient conditions of copositive tensors,Linear Multilinear Algebra. 2015,Vol. 63, No. 1,120-131 [24] Song，Y.， Qi， L.: Properties of tensor complementarity problem and some classes of structured tensors， Ann. Appl. Math. 33(3)，308-   
323(2017) [25] Song，Y.， Qi， L.: Properties of some classes of structured tensors, J. Optim. Theory Appl. 165(3), 854-873(2015) [26] Song，Y.，Qi， L.: Tensor complementarity problem and semi-positive tensors, J. Optim. Theory Appl.169,1069-1078(2016) [27] Song，Y.，Qi， L.: Analytical expressions of copositivity for 4th order symmetric tensors and applications,arXiv: 1909.00880 ChinarXiv:201909.00015 2 Sep 2019 [28] Song, Y., Qi, L.: Eigenvalue analysis of constrained minimization problem for homogeneous polynomial, J. Glob. Optim. 64(3) 563-575 (2016) [29] Song, Y.， Yu, G.: Properties of solution set of tensor complementarity problem, J. Optim. Theory Appl. 170, 85-96(2016) [30] Song， Y.， Qi, L.: Strictly semi-positive tensors and the boundedness of tensor complementarity problems, Optim. Lett. 11, 1407-1426(2017) [31] Song, Y.， Mei, W.: Structural Properties of Tensors and Complementarity Problems. J. Optim. Theory Appl. 176(2), 289-305(2018) [32] Schmidt, J.W.， He $\beta$ ， W.: Positivity of cubic polynomials on intervals and positive spline interpolation, BIT Numerical Mathematics, 28(2),   
340-352(1988) [33] Wang, X.， Chen, H., Wang, Y.: Solution structures of tensor complementarity problem. Front. Math. China 13(4), 935-945 (2018)   
[34] Wang, Y., Huang, Z.H., Bai, X.L.: Exceptionally regular tensors and tensor complementarity problems. Optim. Method. Softw.31(4)，815- 828 (2016)   
[35] Wang, J., Hu, S., Huang, Z.H.: Solution sets of quadratic complementarity problems. J. Optim. Theory Appl. 176(1),120-136 (2018)   
[36] Yuan， P.，You, L.: Some remarks on $P , P _ { 0 } , B$ and $B _ { 0 }$ tensors, Linear Algebra Appl. 459(3) 511-521 (2014)