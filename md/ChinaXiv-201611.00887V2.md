# Infinite and finite dimensional generalized Hilbert tensors \*

Wei Mei $\dagger$ ， Yisheng Song†

# Abstract

In this paper, we introduce the concept of an $m$ -order $n$ -dimensional generalized Hilbert tensor $\mathcal { H } _ { n } = ( \mathcal { H } _ { i _ { 1 } i _ { 2 } \cdots i _ { m } } )$ ，

$$
\mathcal { H } _ { i _ { 1 } i _ { 2 } \cdots i _ { m } } = \frac { 1 } { i _ { 1 } + i _ { 2 } + \cdots i _ { m } - m + a } , a \in \mathbb { R } \setminus \mathbb { Z } ^ { - } ; i _ { 1 } , i _ { 2 } , \cdots , i _ { m } = 1 , 2 , \cdots , n ,
$$

and show that its $H$ -spectral radius and its $Z$ -spectral radius are smaller than or equal to $M ( a ) n ^ { m - 1 }$ and $M ( a ) n ^ { \frac { m } { 2 } }$ , respectively, here $M ( a )$ is a constant only dependent on $a$ ： Moreover, both infnite and finite dimensional generalized Hilbert tensors are positive definite for $a \geq 1$ . For an $m$ -order infinite dimensional generalized Hilbert tensor $\mathcal { H } _ { \infty }$ with $a > 0$ ，we prove that $\mathcal { H } _ { \infty }$ defines a bounded and positively $( m - 1 )$ -homogeneous operator from $l ^ { 1 }$ into $l ^ { p }$ ( $1 < p < \infty$ ). The upper bounds of norm of corresponding positively homogeneous operators are obtained.

Key words:Generalized Hilbert tensor, Spectral radius, Norm, Upper bounds

AMS subject classifications (2010): 47H15, 47H12, 34B10, 47A52, 47J10, 47H09, 15A48,47H07

# 1 Introduction

Let $\mathbb { R }$ denote the set of all real numbers,and let $\mathbb { Z }$ be the set of all integers. We write $\mathbb { Z } ^ { - }$ stands for the set of all non-positive integers, i.e.,

$$
\mathbb { Z } ^ { - } = \left\{ k \in \mathbb { Z } : k \leq 0 \right\} { \mathrm { ~ a n d ~ } } \mathbb { Z } ^ { -- } = \left\{ k \in \mathbb { Z } : k < 0 \right\}
$$

An $m$ -order $n$ -dimensional tensor (hypermatrix) $\mathcal { A } = ( a _ { i _ { 1 } \cdots i _ { m } } )$ is a multi-array of real entries $a _ { i _ { 1 } \cdots i _ { m } } \in \mathbb { R }$ ，where $i _ { j } \in I _ { n } = \{ 1 , 2 , \cdots , n \}$ for $j \in I _ { m } = \{ 1 , 2 , \cdot \cdot \cdot , m \}$ ： $\mathcal { A }$ is called a symmetric tensor if the entries $a _ { i _ { 1 } \cdots i _ { m } }$ are invariant under any permutation of their indices.

Qi [16,17] introduced the concepts of eigenvalues of the higher order symmetric tensors, and showed the existence of the eigenvalues and some applications. The concepts of real eigenvalue was introduced by Lim [14] independently using a variational approach. Subsequently, many mathematical workers studied the spectral properties of various structured tensors under different conditions. The spectral properties of nonnegative matrices had been generalized to $n$ -dimensional nonnegative tensors under various conditions by Chang et al. [1,2],He and Huang [8], He [9],He et al. [10], Li et al. [13],Qi [18],Song and Qi [21, 22], Wang et al. [25], Yang and Yang [27, 28] and references therein.

For infinite dimensional tensors, the corresponding studies have only just begun, and the conclusions are fewer. Song and Qi [2Ol introduced the concept of infinite dimensional Hilbert tensor and showed that such a Hilbert tensor defines a bounded, continuous and positively $( m - 1 )$ -homogeneous operator from $l ^ { 1 }$ into $l ^ { p }$ ( $1 < p < \infty$ ）and the norms of corresponding positively homogeneous operators are not larger than $\frac { \pi } { \sqrt { 6 } }$ . They also proved that the spectral radius and $E$ -spectral radius of finite dimensional Hilbert tensor are smaller than or equal to $n ^ { m - 1 } \sin { \frac { \pi } { n } }$ and $n ^ { \frac { m } { 2 } } \sin { \frac { \pi } { n } }$ , respectively. Clearly, an $m$ -order $n$ -dimensional HilberttensorisaHankeltensorwith $v = ( 1 , \frac { 1 } { 2 } , \frac { 1 } { 3 } , \cdots , \frac { 1 } { n m } )$ ,introducedbyQi[19].Asosee Chen and Qi [3], Xu [26] for more details of Hankel tensors.Hilbert tensor (hypermatrix) is a natural extension of Hilbert matrix, which was introduced by Hilbert [7]. For more details of Hilbert matrix, see Frazer[5] and Taussky [24] for $n$ -dimensional Hilbert matrix, Choi [4]) and Ingham [11] for an infinite dimensional Hilbert matrix,Magnus [15] and Kato [12] for the spectral properties of infinite dimensional Hilbert matrix.

In this paper, we study more general Hilbert tensor, which is referred to as “generalized Hilbert tensor”. The entries of an $m$ -order infinite dimensional generalized Hilbert tensor （204号 $\mathcal { H } _ { \infty } = ( \mathcal { H } _ { i _ { 1 } i _ { 2 } \cdots i _ { m } } )$ are defined by

$$
{ \mathcal { H } } _ { i _ { 1 } i _ { 2 } \cdots , i _ { m } } = { \frac { 1 } { i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + a } } , a \in \mathbb { R } \setminus \mathbb { Z } ^ { - } , i _ { 1 } , i _ { 2 } , \cdots i _ { m } \in \mathbb { Z } ^ { + + } = - \mathbb { Z } ^ { -- } .
$$

The entries of an $m$ -order $n$ -dimensional generalized Hilbert tensor $\mathcal { H } _ { n } = ( \mathcal { H } _ { i _ { 1 } i _ { 2 } \cdots i _ { m } } )$ are to choose $i _ { 1 } , i _ { 2 } , \cdots , i _ { m } \in \{ 1 , 2 , \cdots , n \}$ in (1.1). Clearly,both ${ \mathcal { H } } _ { n }$ and $\mathcal { H } _ { \infty }$ are symmetric and the entries of the generalized Hilbert tensor with $a \geq 1$ can be written as the integral form as follow

$$
\mathcal { H } _ { i _ { 1 } i _ { 2 } \cdots i _ { m } } = \int _ { 0 } ^ { 1 } t ^ { i _ { 1 } + i _ { 2 } + \cdots i _ { m } - m + a - 1 } d t .
$$

For a vector $x = ( x _ { 1 } , x _ { 2 } , \cdot \cdot \cdot , x _ { n } ) ^ { \top } \in \mathbb { R } ^ { n }$ ， $\mathcal { H } _ { n } x ^ { m - 1 }$ is a vector with its ith component defined by

$$
( \mathcal { H } _ { n } x ^ { m - 1 } ) _ { i } = \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } \frac { x _ { i _ { 2 } } \cdots x _ { i _ { m } } } { i + i _ { 2 } + \cdots + i _ { m } - m + a } , \ a \in \mathbb { R } \setminus \mathbb { Z } ^ { - } , \ i = 1 , 2 , \cdots , n .
$$

Accordingly, $\mathcal { H } _ { n } x ^ { m }$ is given by

$$
{ \mathcal { H } } _ { n } x ^ { m } = x ^ { \top } ( { \mathcal { H } } _ { n } x ^ { m - 1 } ) = \sum _ { i _ { 1 } , i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } { \frac { x _ { i _ { 1 } } x _ { i _ { 2 } } \cdots x _ { i _ { m } } } { i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + a } } , a \in \mathbb { R } \setminus \mathbb { Z } ^ { - } .
$$

Let $l ^ { 1 }$ is a space consisting of all real number sequences $\boldsymbol { x } = ( x _ { i } ) _ { i = 1 } ^ { \infty }$ satisfying

$$
\sum _ { i = 1 } ^ { \infty } | x _ { i _ { i } } | < \infty .
$$

For a real vector $x = ( x _ { 1 } , x _ { 2 } , \cdot \cdot \cdot , x _ { n } , x _ { n + 1 } , \cdot \cdot \cdot ) \in l ^ { 1 }$ ， $\mathcal { H } _ { \infty } x ^ { m - 1 }$ is an infinite dimensional vector with its ith component defined by

$$
( \mathcal { H } _ { \infty } x ^ { m - 1 } ) _ { i } = \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { \infty } \frac { x _ { i _ { 2 } } \cdots x _ { i _ { m } } } { i + i _ { 2 } + \cdots + i _ { m } - m + a } , a \in \mathbb { R } \setminus \mathbb { Z } ^ { - } ; i \in \{ 1 , 2 , \cdots , n , \cdots \} .
$$

Accordingly, $\mathcal { H } _ { \infty } x ^ { m }$ is given by

$$
{ \mathcal { H } } _ { \infty } x ^ { m } = \sum _ { i _ { 1 } , i _ { 2 } , \cdots , i _ { m } = 1 } ^ { \infty } { \frac { x _ { i _ { 1 } } x _ { i _ { 2 } } \cdots x _ { i _ { m } } } { i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + a } } , \ a \in \mathbb { R } \backslash \mathbb { Z } ^ { - } .
$$

Now we show that both $\mathcal { H } _ { \infty } x ^ { m }$ and $\mathcal { H } _ { \infty } x ^ { m - 1 }$ are well-defined for all $x \in l ^ { 1 }$

Proposition 1.1. Let $\mathcal { H } _ { \infty }$ be an $m$ -order infinite dimensional generalized Hilbert tensor. Then for all $x \in l ^ { 1 }$ ，

(i） $\mathcal { H } _ { \infty } x ^ { m }$ defined by (1.6) absolutely converges, i.e., $| \mathcal { H } _ { \infty } x ^ { m } | < \infty$ ：，   
(ii) $\mathcal { H } _ { \infty } x ^ { m - 1 }$ is well-defined, i.e., for each positive integer $i$ ， its ith component defined by (1.5) absolutely converges.

Proof. Let $[ a ]$ denote the largest integer not exceeding $a$ . Then for all $a \in \mathbb { R } \setminus \mathbb { Z } ^ { - }$ ，it is obvious that for all positive integers $i _ { 1 } , i _ { 2 } , \cdots , i _ { m }$ ，

$$
\operatorname* { m i n } _ { i _ { 1 } , \cdots , i _ { m } } \left| i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + a \right| = a { \mathrm { ~ f o r ~ } } a > 0 .
$$

For $a < 0$ , there exist some positive integers $i _ { 1 } ^ { \prime } , i _ { 2 } ^ { \prime } , \cdots , i _ { m } ^ { \prime }$ and $i _ { 1 } ^ { \prime \prime } , i _ { 2 } ^ { \prime \prime } , \cdots , i _ { m } ^ { \prime \prime }$ such that

$$
i _ { 1 } ^ { \prime } + i _ { 2 } ^ { \prime } + \cdot \cdot \cdot + i _ { m } ^ { \prime } - m = - [ a ] { \mathrm { ~ a n d ~ } } i _ { 1 } ^ { \prime \prime } + i _ { 2 } ^ { \prime \prime } + \cdot \cdot \cdot + i _ { m } ^ { \prime \prime } - m = - [ a ] - 1 ,
$$

and hence,

$$
\operatorname* { m i n } _ { i _ { 1 } , \cdots , i _ { m } } \left| i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + a \right| = \operatorname* { m i n } \{ a - [ a ] , 1 - ( a - [ a ] ) \} \mathrm { ~ f ~ }
$$

In conclusion, we have for $a \in \mathbb { R } \setminus \mathbb { Z } ^ { - }$ ，

$$
\frac { 1 } { \left| i _ { 1 } + i _ { 2 } + \cdot \cdot \cdot + i _ { m } - m + a \right| } \le N ( a ) = \left\{ \begin{array} { l l } { \frac { 1 } { a } , } & { a > 0 ; } \\ { \frac { 1 } { \operatorname* { m i n } \{ a - [ a ] , 1 + [ a ] - a \} } , } & { a < 0 . } \end{array} \right.
$$

Then for $x = ( x _ { 1 } , x _ { 2 } , \cdot \cdot \cdot , x _ { n } , x _ { n + 1 } , \cdot \cdot \cdot ) \in l ^ { 1 }$ ， we obtain

$$
\begin{array} { r l r } {  { | \mathcal { H } _ { \infty , x } { \boldsymbol { x } } ^ { m } | = | \sum _ { i _ { 1 } , i _ { 2 } , \cdots , i _ { m } = 1 } ^ { \infty } \frac { \boldsymbol { x } _ { i _ { 1 } } \boldsymbol { x } _ { i _ { 2 } } \cdots \boldsymbol { x } _ { i _ { m } } } { i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + a } | } } \\ & { } & { \leq \sum _ { i _ { 1 } , i _ { 2 } , \cdots , i _ { m } = 1 } ^ { \infty } \frac { | \boldsymbol { x } _ { i _ { 1 } } \boldsymbol { x } _ { i _ { 2 } } \cdots \boldsymbol { x } _ { i _ { m } } | } { | i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + a | } } \\ & { } & { \leq N ( \boldsymbol { \alpha } ) \underset { i _ { 1 } , i _ { 2 } , \cdots , i _ { m } = 1 } { \overset { \infty } { \sum } } | \boldsymbol { x } _ { i _ { 1 } } | | \boldsymbol { x } _ { i _ { 2 } } | \cdots | \boldsymbol { x } _ { i _ { m } } | } \\ & { } & { = N ( \boldsymbol { \alpha } ) ( \displaystyle \sum _ { i = 1 } ^ { \infty } | \boldsymbol { x } _ { i } | ) ^ { m } < \infty } \end{array}
$$

since $\textstyle \sum _ { i = 1 } ^ { \infty } | x _ { i } | < \infty$ , and hence, $\mathcal { H } _ { \infty } x ^ { m }$ absolutely converges.

Similarly, for each positive integer $i$ ， we also have

$$
\begin{array} { r l r } {  { | | \mathcal { H } _ { \infty } x ^ { m - 1 } ) _ { i } | = | \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { \infty } \frac { x _ { i _ { 2 } } \cdots x _ { i _ { m } } } { i + i _ { 2 } + \cdots + i _ { m } - m + a } | } } \\ & { } & { \leq N ( a ) ( \displaystyle \sum _ { k = 1 } ^ { \infty } | x _ { k } | ) ^ { m - 1 } < \infty . } \end{array}
$$

So $\mathcal { H } _ { \infty } x ^ { m - 1 }$ is well-defined.

In section 2, we present some concepts and basic facts which are used for late. In section 3,we first show that both infinite and finite dimensional generalized Hilbert tensors are positive definite for $a \geq 1$ . Let

$$
F _ { \infty } x = ( \mathcal { H } _ { \infty } x ^ { m - 1 } ) ^ { [ \frac { 1 } { m - 1 } ] } \mathrm { ~ a n d ~ } T _ { \infty } x = \left\{ \begin{array} { l l } { \lVert x \rVert _ { l ^ { 1 } } ^ { 2 - m } \mathcal { H } _ { \infty } x ^ { m - 1 } } & { x \neq \theta } \\ { \theta } & { x = \theta , } \end{array} \right.
$$

where $\theta = ( 0 , 0 , \cdots , 0 , \cdot \cdot \cdot ) ^ { \top }$ . Then we prove that both $F _ { \infty }$ and $T _ { \infty }$ is a bounded, continuous and positively homogeneous operator on $l ^ { 1 }$ . In particular, their upper bounds with respect to opertor norm are obtained as follows:

$$
\| F _ { \infty } \| = \operatorname* { s u p } _ { \| x \| _ { l ^ { 1 } } = 1 } \| F _ { \infty } x \| _ { l ^ { 2 ( m - 1 ) } } \leq K ( a ) \mathrm { ~ a n d ~ } \| T _ { \infty } \| = \operatorname* { s u p } _ { \| x \| _ { l ^ { 1 } } = 1 } \| T _ { \infty } x \| _ { l ^ { 2 } } \leq C ( a ) ,
$$

where

$$
K ( a ) = \left\{ \begin{array} { l l } { \sqrt [ 2 ( m - 1 ) ] { \frac { 1 } { a ^ { 2 } } + \frac { \pi ^ { 2 } } { 6 } } , } & { 0 < a < 1 ; } \\ { \sqrt [ 2 ( m - 1 ) ] { \frac { \pi ^ { 2 } } { 6 } } , } & { a \geq 1 ; } \end{array} \right. \mathrm { ~ a n d ~ } C ( a ) = \left\{ \begin{array} { l l } { \sqrt { \frac { 1 } { a ^ { 2 } } + \frac { \pi ^ { 2 } } { 6 } } , } & { 0 < a < 1 ; } \\ { \frac { \pi } { \sqrt { 6 } } , } & { a \geq 1 . } \end{array} \right.
$$

For a finite dimensional generalized Hilbert tensor ${ \mathcal { H } } _ { n }$ , we show that its $H$ -spectral radius and its $Z$ -spectral radius are smaller than or equal to $M ( a ) n ^ { m - 1 }$ and $M ( a ) n ^ { \frac { m } { 2 } }$ , respectively,

where

$$
M ( a ) = \left\{ \begin{array} { l l } { \frac { 1 } { a } , } & { a > 0 ; } \\ { \frac { 1 } { \operatorname* { m i n } \{ a - [ a ] , 1 + [ a ] - a \} } , } & { - m ( n - 1 ) < a < 0 ; } \\ { \frac { 1 } { - m ( n - 1 ) - a } , } & { a < - m ( n - 1 ) . } \end{array} \right.
$$

In particular, for $a > 0$ ， we obtain that the upper bounds of its spectral radius $\rho ( \mathcal { H } _ { n } )$ and its $E$ -spectral radius $\rho _ { E } ( \mathcal { H } _ { n } )$ ,i.e.,

$$
\rho ( \mathcal { H } _ { n } ) \leq \frac { n ^ { m - 1 } } { a } \ \mathrm { a n d } \ \rho _ { E } ( \mathcal { H } _ { n } ) \leq \frac { n ^ { \frac { m } { 2 } } } { a } .
$$

# 2 Preliminaries and basic facts

Let both $X$ and $Y$ be two real Banach spaces with the norm $\| \cdot \| _ { X }$ and $\| \cdot \| _ { Y }$ , respectively, and let $T : X  Y$ be an operator. Then $T$ is said to be

(i) $t$ -homogeneous if $T ( \lambda x ) = \lambda ^ { t } T ( x )$ for all $\lambda \in \mathbb { R }$ and all $x \in X$ ： (ii） positively homogeneous if $T ( t x ) = t T ( x )$ for all $t > 0$ and all $x \in X$ · (iii) bounded if there exits a real number $M > 0$ such that

$$
\| T x \| _ { Y } \leq M \| x \| _ { X } { \mathrm { ~ f o r ~ a l l ~ } } x \in X .
$$

For a bounded, continuous and positively homogeneous operator $T : X  Y$ , the norm of （204号 $T$ may be defined as follows (see Fucik et al. [6], Song and Qi [22] for more details):

$$
\| T \| = \operatorname* { s u p } \{ \| T x \| _ { Y } : \| x \| _ { X } = 1 \} .
$$

For $0 < p < \infty$ ， $l ^ { p }$ is a space consisting of all real number sequences $\boldsymbol { x } = ( x _ { i } ) _ { i = 1 } ^ { \infty }$ satisfying $\sum _ { i = 1 } ^ { \infty } | x _ { i _ { i } } | ^ { p } < \infty$ .For $p \geq 1$ , it is well known that

$$
\| x \| _ { l ^ { p } } = \left( \sum _ { i = 1 } ^ { \infty } | x _ { i } | ^ { p } \right) ^ { \frac { 1 } { p } }
$$

is the norms defined on the sequences space $l ^ { p }$ .For $p \geq 1$ , it is well known that

$$
\| x \| _ { p } = \left( \sum _ { i = 1 } ^ { n } | x _ { i } | ^ { p } \right) ^ { \frac { 1 } { p } }
$$

is the norms defined on $\mathbb { R } ^ { n }$ . Moreover, the following relationship between the two different norms is obvious,

$$
\| x \| _ { q } \leq \| x \| _ { p } \leq n ^ { \frac { 1 } { p } - \frac { 1 } { q } } \| x \| _ { q } { \mathrm { ~ f o r ~ } } q > p .
$$

Let $\mathcal { A }$ be an $m$ -order $n$ -dimensional symmetric tensor. Then a number $\lambda$ is called an eigenvalue of $\mathcal { A }$ if there exists a nonzero vector $x$ such that

$$
\begin{array} { r } { \mathcal { A } \mathcal { x } ^ { m - 1 } = \lambda \mathcal { x } ^ { [ m - 1 ] } . } \end{array}
$$

where $\boldsymbol { x } ^ { [ m - 1 ] } = ( x _ { 1 } ^ { m - 1 } , x _ { 2 } ^ { m - 1 } , \cdot \cdot \cdot x _ { n } ^ { m - 1 } ) ^ { \top }$ ,and call $x$ an eigenvector of $\mathcal { A }$ associated with the eigenvalue $\lambda$ . We call such an eigenvalue $H$ -eigenvalue if it is real and has a real eigenvector $x$ ，and call such a real eigenvector $x$ an H-eigenvactor. These concepts were first introduced by Qi [16] for the higher order symmetric tensors. Lim [14] independently introduced the notion of eigenvalue for higher order tensors but restricted $x$ to be a real vector and $\lambda$ to be a real number.

Qi[16] introduced another concept of tensor eigenvalue. A number $\mu$ is said to be an （204号 $E$ -eigenvalue of $\mathcal { A }$ if there exists a nonzero vector $x$ such that

$$
A x ^ { m - 1 } = \mu x ( x ^ { T } x ) ^ { \frac { m - 2 } { 2 } } ,
$$

and such a nonzero vector $x$ is called an $E$ -eigenvector of $A$ associated with $\mu$ . It is clear that if $x$ is real, then $\mu$ is also real. In this case, $\mu$ and $x$ are called a $Z$ -eigenvalue of $A$ and a $Z$ -eigenvector of $\mathcal { A }$ , respectively. Qi [16,17] extended some nice properties of symmetric matrices to higher order symmetric tensors. The Perron-Frobenius theorem of nonnegative matrices had been generalized to higher order nonnegative tensors under various conditions by Chang, Pearson and Zhang [1, 2], Qi [18], Song and Qi [21, 22], Yang and Yang [27, 28] and references therein.

# 3 Generalized Hilbert tensors

In this section, we mainly discuss the properties of infinite and finite dimensional generalized Hilbert tensors. It is easy to see that both finite and infinite dimensional generalized Hilbert tensor ${ \mathcal { H } } _ { n }$ and $\mathcal { H } _ { \infty }$ are symmetric but not always positive semi-definite since $a \in \mathbb { R } \setminus \mathbb { Z } ^ { - }$ ： Howerver, for all $a > 0$ ， both finite and infinite dimensional generalized Hilbert tensors are positive, it follows from the definition of strictly copositive tensors that ${ \mathcal { H } } _ { n }$ and $\mathcal { H } _ { \infty }$ are strictly copositive, i.e.,

$\mathcal { H } _ { \infty } x ^ { m } > 0$ for all nonnegative nonzero vector $x \in l ^ { 1 }$

The concept of strictly copositive tensors was introduced by Qi [18]. Also see Song and Qi [23] for more details. Now, we give the positive definitiveness of such two tensors when $a \geq 1$ ：

# 3.1 Positive definitiveness

Theorem 3.1. Let m be even and $a \geq 1$ . Then m-order generalized Hilbert tensors $\mathcal { H } _ { \infty }$ and ${ \mathcal { H } } _ { n }$ are both positive definite, i.e.,

Proof. For each $x = ( x _ { 1 } , x _ { 2 } , \cdot \cdot \cdot , x _ { n } , x _ { n + 1 } , \cdot \cdot \cdot ) \in l ^ { 1 }$ and $t \in [ 0 , 1 ]$ , it is obvious that

$$
| t ^ { i - 1 + \frac { a - 1 } { m } } x _ { i } | = | t | ^ { i - 1 + \frac { a - 1 } { m } } | x _ { i } | \leq | x _ { i } | ,
$$

which implies that the infinite series $\sum _ { i = 1 } ^ { \infty } t ^ { i - 1 + \frac { a - 1 } { m } } x _ { i }$ uniformly converges with respect to $t \in$ （204号 $[ 0 , 1 ]$ . Then it follows from integral form of $\mathcal { H } _ { i _ { 1 } i _ { 2 } \cdots i _ { m } }$ that

$$
\begin{array} { r l } { \mathcal { H } _ { \infty , x } ^ { \infty } = } & { \displaystyle \sum _ { i \geq \frac { 1 } { 2 } , i = 1 } ^ { \infty } \int _ { 0 } ^ { 1 } t ^ { i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + \omega - 1 } x _ { i _ { 1 } } x _ { i _ { 2 } } \cdots x _ { i _ { m } } d t } \\ & { = \displaystyle \sum _ { i _ { 1 } , i _ { 2 } , i _ { 3 } = 1 } ^ { \infty } \int _ { 0 } ^ { 1 } \left( t ^ { i _ { 1 } - 1 + \frac { \omega - 1 } { m } } x _ { i _ { 1 } } \right) \left( t ^ { i _ { 2 } - 1 + \frac { \omega - 1 } { m } } x _ { i _ { 2 } } \right) \cdots \left( t ^ { i _ { m } - 1 + \frac { \omega - 1 } { m } } x _ { i _ { m } } \right) d t } \\ & { = \displaystyle \int _ { 0 } ^ { 1 } \left( \displaystyle \sum _ { i _ { 1 } = 1 } ^ { \infty } t ^ { i _ { 1 } - 1 + \frac { \omega - 1 } { m } } x _ { i _ { 1 } } \right) \left( \displaystyle \sum _ { i _ { 2 } = 1 } ^ { \infty } t ^ { i _ { 2 } - 1 + \frac { \omega - 1 } { m } } x _ { i _ { 2 } } \right) \cdots \left( \displaystyle \sum _ { i _ { m } = 1 } ^ { \infty } t ^ { i _ { m } - 1 + \frac { \omega - 1 } { m } } x _ { i _ { m } } \right) d t } \\ & { = \displaystyle \int _ { 0 } ^ { 1 } \left( \displaystyle \sum _ { i = 1 } ^ { \infty } t ^ { i _ { 1 } - 1 + \frac { \omega - 1 } { m } } x _ { i _ { 1 } } \right) ^ { m } d t \geq 0 \mathrm { ~ ( ~ m ~ i s ~ e v e n ) } . } \end{array}
$$

Now we show $\mathcal { H } _ { \infty } x ^ { m } > 0$ for all nonzero vector $x \in l ^ { 1 }$ . Suppose not, then there exists a nonzero vector $x \in l ^ { 1 }$ such that $\mathcal { H } _ { \infty } x ^ { m } = 0$ ,i.e.,

$$
\int _ { 0 } ^ { 1 } \left( \sum _ { i = 1 } ^ { \infty } t ^ { i - 1 + \frac { a - 1 } { m } } x _ { i } \right) ^ { m } d t = 0 .
$$

Since $m$ is even, $\left( \sum _ { i = 1 } ^ { \infty } t ^ { i - 1 + \frac { a - 1 } { m } } x _ { i } \right) ^ { m } \geq 0$ ，and hence,by the continuity,we have

$$
t ^ { \frac { a - 1 } { m } } \left( x _ { 1 } + \left( \sum _ { i = 2 } ^ { \infty } t ^ { i - 1 } x _ { i } \right) \right) = \sum _ { i = 1 } ^ { \infty } t ^ { i - 1 + { \frac { a - 1 } { m } } } x _ { i } = 0 \mathrm { ~ f o r ~ a l l ~ } t \in [ 0 , 1 ] .
$$

So for all $t \in ( 0 , 1 ]$ ， we have

$$
x _ { 1 } + \left( \sum _ { i = 2 } ^ { \infty } t ^ { i - 1 } x _ { i } \right) = 0 .
$$

Since the polynomial $x _ { 1 } + \left( \sum _ { i = 2 } ^ { \infty } t ^ { i - 1 } x _ { i } \right)$ is continuous at $t = 0$ ，we see that

$$
x _ { 1 } + \left( \sum _ { i = 2 } ^ { \infty } t ^ { i - 1 } x _ { i } \right) = 0 { \mathrm { ~ f o r ~ a l l ~ } } t \in [ 0 , 1 ] .
$$

Let $t = 0$ . Then $x _ { 1 } = 0$ , and so,

$$
t ^ { \frac { a - 1 } { m } + 1 } \left( x _ { 2 } + \sum _ { i = 3 } ^ { \infty } t ^ { i - 2 } x _ { i } \right) = \sum _ { i = 2 } ^ { \infty } t ^ { i - 1 + \frac { a - 1 } { m } } x _ { i } = 0 \mathrm { ~ f o r ~ a l l ~ } t \in [ 0 , 1 ] .
$$

So, for all $t \in ( 0 , 1 ]$ ， we have

$$
x _ { 2 } + \sum _ { i = 3 } ^ { \infty } t ^ { i - 2 } x _ { i } = 0 .
$$

Again by the continuity, we see that

$$
x _ { 2 } + \sum _ { i = 3 } ^ { \infty } t ^ { i - 2 } x _ { i } = 0 { \mathrm { ~ f o r ~ a l l ~ } } t \in [ 0 , 1 ] .
$$

Take $t = 0$ , then we have $x _ { 2 } = 0$

By the mathematical induction， suppose $x _ { 1 } = x _ { 2 } = \cdot \cdot \cdot = x _ { k } = 0$ . Then we only need show $x _ { k + 1 } = 0$ . In fact,

$$
t ^ { \frac { a - 1 } { m } + k } \left( x _ { k + 1 } + \left( \sum _ { i = k + 2 } ^ { \infty } t ^ { i - ( k + 1 ) } x _ { i } \right) \right) = \sum _ { i = k + 1 } ^ { \infty } t ^ { i - 1 + \frac { a - 1 } { m } } x _ { i } = 0 \mathrm { ~ f o r ~ a l l ~ } t \in [ 0 , 1 ] .
$$

So, for all $t \in ( 0 , 1 ]$ ， we have

$$
x _ { k + 1 } + \left( \sum _ { i = k + 2 } ^ { \infty } t ^ { i - ( k + 1 ) } x _ { i } \right) = 0 .
$$

Again by the continuity, we see that

$$
x _ { k + 1 } + \left( \sum _ { i = k + 2 } ^ { \infty } t ^ { i - ( k + 1 ) } x _ { i } \right) = 0 { \mathrm { ~ f o r ~ a l l ~ } } t \in [ 0 , 1 ] .
$$

Take $t = 0$ , then we have $x _ { k + 1 } = 0$ . So we may conclude that

$$
x _ { i } = 0 { \mathrm { ~ f o r ~ a l l ~ } } i = 1 , 2 , \cdots , n , n + 1 , \cdots
$$

and hence, $x = \theta = ( 0 , 0 , \cdots , 0 , 0 , \cdots ) ^ { \top }$ ，which is a contradiction. The desired conclusion follows.

Similarly, we can obtain that ${ \mathcal { H } } _ { n }$ is positive definite.

Remark 3.1. We show the positive definitiveness of infinite and finite dimensional generalized Hilbert tensors with $a \geq 1$ . Then it is unknown whether or not ${ \mathcal { H } } _ { n }$ and $\mathcal { H } _ { \infty }$ have the positive definitiveness for $0 < a < 1$ or $a < 0$ with $a \in \mathbb { R } \backslash \mathbb { Z } ^ { - }$ ：

# 3.2 Infinite dimensional generalized Hilbert tensors

Let

$$
F _ { \infty } x = ( \mathcal { H } _ { \infty } x ^ { m - 1 } ) ^ { [ \frac { 1 } { m - 1 } ] } \ ( m \ \mathrm { i s \ e v e n } )
$$

and

$$
T _ { \infty } x = \left\{ \begin{array} { l l } { \displaystyle \| x \| _ { l ^ { 1 } } ^ { 2 - m } \mathcal { H } _ { \infty } x ^ { m - 1 } } & { x \not = \theta } \\ { \theta } & { x = \theta , } \end{array} \right.
$$

where $x ^ { [ \frac { 1 } { m - 1 } ] } = ( x _ { 1 } ^ { \frac { 1 } { m - 1 } } , x _ { 2 } ^ { \frac { 1 } { m - 1 } } , \cdot \cdot x _ { n } ^ { \frac { 1 } { m - 1 } } , \cdot \cdot \cdot ) ^ { \top }$ and $\boldsymbol { \theta } = ( 0 , 0 , \cdots , 0 , \cdots ) ^ { \top }$ , the zero element of a vector space $l ^ { p }$ . It is easy to see that both operators $F _ { \infty }$ and $T _ { \infty }$ are continuous and positively homogeneous. Therefore our main interests are to study the boundedness of two classes of operators.

Theorem 3.2. Let $F _ { \infty }$ and $T _ { \infty }$ are defined by Eqs. (3.1) and (3.2)，respectively. Assume that $a > 0$ ：

(i）If $x \in l ^ { 1 }$ ， then $F _ { \infty } x \in l ^ { p }$ for $m - 1 < p < \infty$ . Moreover, $F _ { \infty }$ is a bounded, continuous and positively homogeneous operator from $l ^ { 1 }$ into $l ^ { p }$ ( $m - 1 < p < \infty$ ). In particular,

$$
\| F _ { \infty } \| = \operatorname* { s u p } _ { \| x \| _ { l ^ { 1 } } = 1 } \| F _ { \infty } x \| _ { l ^ { 2 ( m - 1 ) } } \leq K ( a ) ,
$$

where

$$
K ( a ) = \left\{ \begin{array} { l l } { 2 ( m - 1 ) \sqrt { \frac { 1 } { a ^ { 2 } } + \frac { \pi ^ { 2 } } { 6 } } , } & { 0 < a < 1 ; } \\ { 2 ( m - 1 ) \sqrt { \frac { \pi ^ { 2 } } { 6 } } , } & { a \geq 1 . } \end{array} \right.
$$

(ii) If $x \in l ^ { 1 }$ ，then $T _ { \infty } x \in l ^ { p }$ for $1 < p < \infty$ . Moreover, $T _ { \infty }$ is a bounded, continuous and positively homogeneous operator from $l ^ { 1 }$ into $l ^ { p }$ ( $1 < p < \infty$ ). In particular,

$$
\begin{array} { r } { \| T _ { \infty } \| = \operatorname* { s u p } _ { \| x \| _ { l ^ { 1 } } = 1 } \| T _ { \infty } x \| _ { l ^ { 2 } } \leq C ( a ) , } \end{array}
$$

where

$$
C ( a ) = \left\{ \begin{array} { l l } { \sqrt { \frac { 1 } { a ^ { 2 } } + \frac { \pi ^ { 2 } } { 6 } } , } & { 0 < a < 1 ; } \\ { \frac { \pi } { \sqrt { 6 } } , } & { a \geq 1 . } \end{array} \right.
$$

Proof. For $x \in l ^ { 1 }$

$$
\begin{array} { r l } { \left( \mathfrak { M } _ { \sigma } \mathfrak { L } ^ { \sigma + 1 } \mathfrak { L } _ { \sigma } \right) } & { = \frac { 1 } { \sigma ^ { 2 } + 1 } \Bigg | _ { \sigma \in \mathcal { L } _ { \sigma } } \frac { 1 } { \sigma ^ { 2 } + 1 } \Bigg | _ { \sigma \in \mathcal { L } _ { \sigma } } \frac { \mathfrak { L } _ { \sigma } \mathfrak { L } _ { \sigma } } { \sigma ^ { 2 } + 1 } - \frac { \mathfrak { L } _ { \sigma } \mathfrak { L } _ { \sigma } } { 1 + \sigma ^ { 2 } + 1 } } \\ & { \leq \frac { 1 } { \sigma ^ { 2 } + 1 } \underset { \sigma \in \mathcal { L } _ { \sigma } } \sum _ { \sigma \in \mathcal { L } _ { \sigma } } \frac { 1 } { \sigma ^ { 2 } + 1 } \underset { \sigma \in \mathcal { L } _ { \sigma } } \sum _ { \sigma \in \mathcal { L } _ { \sigma } } \frac { \mathfrak { L } _ { \sigma } \mathfrak { L } _ { \sigma } - \mathfrak { L } _ { \sigma } } { 1 + \sigma ^ { 2 } + 1 } } \\ & { \leq \frac { 1 } { \sigma ^ { 2 } + 1 } \underset { \sigma \in \mathcal { L } _ { \sigma } } \sum _ { \sigma \in \mathcal { L } _ { \sigma } } \big [ 1 - \frac { \mathfrak { L } _ { \sigma } \mathfrak { L } _ { \sigma } } { 1 + \sigma ^ { 2 } + 1 } - \mathfrak { L } _ { \sigma } \big ] + \frac { 1 } { \sigma ^ { 2 } + 1 } } \\ & { - \frac { 1 } { \sigma ^ { 2 } + 1 } \underset { \sigma \in \mathcal { L } _ { \sigma } } \sum _ { \sigma \in \mathcal { L } _ { \sigma } } \big [ 1 - \frac { \mathfrak { L } _ { \sigma } \mathfrak { L } _ { \sigma } - 1 } { \sigma ^ { 2 } + 1 } - \mathfrak { L } _ { \sigma } \big ] + \frac { 1 } { \sigma ^ { 2 } + 1 } } \\ & { - \frac { 1 } { \sigma ^ { 2 } + 1 } \underset { \sigma \in \mathcal { L } _ { \sigma } } \sum _ { \sigma \in \mathcal { L } _ { \sigma } } \big [ \mathfrak { L } _ { \sigma } \mathfrak { L } _ { \sigma } \big ( \mathfrak { L } _ { \sigma } \mathfrak { L } _ { \sigma } - \mathfrak { L } _ { \sigma } \big ) } \\ & { - \frac { 1 } { \sigma ^ { 2 } + 1 } - \frac { 1 } { \sigma ^ { 2 } + 1 } \underset { \sigma \in \mathcal { L } _ { \sigma } } \sum _ { \sigma \in \mathcal { L } _ { \sigma } } \big [ \mathfrak { L } _ { \sigma } \big ( \mathbf { \sigma } \cdot \mathbf { \sigma } \big ) \big ] } \\ &  - \frac { 1 } { \sigma ^ { 2 } + 1 } - \frac { 1 } { \sigma ^ { 2 } + 1 } \underset  \sigma \in \end{array}
$$

Since $a > 0$ , then for all positive integer $i > 1$ ，we have

$$
{ \frac { 1 } { ( i - 1 + a ) ^ { s } } } \leq { \frac { 1 } { ( i - 1 ) ^ { s } } } .
$$

So the series （204号 $\sum _ { i = 1 } ^ { \infty } { \frac { 1 } { ( i - 1 + a ) ^ { s } } }$ converges whenever $s > 1$ （204号

(i)For $m - 1 < p < \infty$ , it follows from the definition of $F _ { \infty }$ that

$$
\begin{array} { r l } { \displaystyle \sum _ { i = 1 } ^ { \infty } | ( F _ { \infty } x ) _ { i } | ^ { p } = \displaystyle \sum _ { i = 1 } ^ { \infty } | \left( \mathcal { H } _ { \infty } x ^ { m - 1 } \right) _ { i } ^ { \frac { 1 } { m - 1 } } | ^ { p } } & { } \\ { \displaystyle } & { = \displaystyle \sum _ { i = 1 } ^ { \infty } | \left( \mathcal { H } _ { \infty } x ^ { m - 1 } \right) _ { i } | ^ { \frac { p } { m - 1 } } } \\ { \displaystyle } & { \leq \displaystyle \sum _ { i = 1 } ^ { \infty } \left( \frac { 1 } { \left( i - 1 + a \right) } \| x \| _ { n } ^ { m - 1 } \right) ^ { \frac { p } { m - 1 } } } \\ { \displaystyle } & { = \| x \| _ { n } ^ { p } \displaystyle \sum _ { i = 1 } ^ { \infty } \frac { 1 } { \left( i - 1 + a \right) ^ { \frac { p } { m - 1 } } } < \infty } \end{array}
$$

since $\begin{array} { r } { s = \frac { p } { m - 1 } > 1 } \end{array}$ . Thus $F _ { \infty } x \in l ^ { p }$ for all $x \in l ^ { 1 }$ . Furthermore, we have

$$
\| F _ { \infty } x \| _ { l ^ { p } } = \left( \sum _ { i = 1 } ^ { \infty } | ( F _ { \infty } x ) _ { i } | ^ { p } \right) ^ { \frac { 1 } { p } } \leq M \| x \| _ { l ^ { 1 } } ,
$$

where $M = \left( \sum _ { i = 1 } ^ { \infty } \frac { 1 } { ( i - 1 + a ) ^ { \frac { p } { m - 1 } } } \right) ^ { \frac { 1 } { p } }$ Therefore $F _ { \infty }$ is a bounded， continuous and positively homogeneous operator from $l ^ { 1 }$ into $l ^ { p }$ ( $m - 1 < p < \infty$ ). Take $p = 2 ( m - 1 )$ , then for $a \geq 1$ ， we have $a - 1 \geq 0$ ,and hence,

$$
M = \left( \sum _ { i = 1 } ^ { \infty } { \frac { 1 } { ( i - 1 + a ) ^ { 2 } } } \right) ^ { \frac { 1 } { p } } \leq \left( \sum _ { i = 1 } ^ { \infty } { \frac { 1 } { i ^ { 2 } } } \right) ^ { \frac { 1 } { p } } = \mathbf { \Sigma } ^ { 2 ( m - 1 ) } { \sqrt [ { \frac { \pi ^ { 2 } } { 6 } } } .
$$

If $0 < a < 1$ ，then

$$
M = \left( \sum _ { i = 1 } ^ { \infty } \frac { 1 } { ( i - 1 + a ) ^ { 2 } } \right) ^ { \frac { 1 } { p } } \leq \left( \frac { 1 } { ( 1 - 1 + a ) ^ { 2 } } + \sum _ { i = 2 } ^ { \infty } \frac { 1 } { ( i - 1 ) ^ { 2 } } \right) ^ { \frac { 1 } { p } } = \ ^ { 2 ( m - 1 ) } \sqrt { \frac { 1 } { a ^ { 2 } } + \frac { \pi ^ { 2 } } { 6 } } .
$$

It follows from (2.1) and (3.3) that

$$
\| F _ { \infty } \| = \operatorname* { s u p } _ { \| x \| _ { l ^ { 1 } } = 1 } \| F _ { \infty } x \| _ { l ^ { 2 ( m - 1 ) } } \leq M \leq K ( a ) .
$$

(ii)For $1 < p < \infty$ ,it follows from the definition of $T _ { \infty }$ that

$$
\begin{array} { l } { \displaystyle \sum _ { i = 1 } ^ { \infty } | ( T _ { \infty } , x ) _ { i } | ^ { p } = \displaystyle \sum _ { i = 1 } ^ { \infty } | ( \| x \| _ { t } ^ { 2 - m } \mathcal H _ { \infty , x } m ^ { - n - 1 } ) _ { i } | ^ { p } } \\ { \displaystyle \qquad = \| x \| _ { t } ^ { ( 2 - m ) p } \displaystyle \sum _ { i = 1 } ^ { \infty } | ( \mathcal H _ { \infty } x ^ { m - 1 } ) _ { i } | ^ { p } } \\ { \displaystyle \qquad \leq \| x \| _ { t } ^ { ( 2 - m ) p } \displaystyle \sum _ { i = 1 } ^ { \infty } \left( \frac 1 { ( i - 1 + a ) } \| x \| _ { t } ^ { \{ m - 1 } \right)}  ^ { p }  \\ { \displaystyle \qquad = \| x \| _ { t } ^ { p } \displaystyle \sum _ { i = 1 } ^ { \infty } \frac 1 { ( i - 1 + a ) ^ { p } } < \infty } \end{array}
$$

since $s = p > 1$ . Thus, $T _ { \infty } x \in l ^ { p }$ for all $x \in l ^ { 1 }$ ， Furthermore, we have

$$
\| T _ { \infty } x \| _ { l ^ { p } } = ( \sum _ { i = 1 } ^ { \infty } | ( T _ { \infty } x ) _ { i } | ^ { p } ) ^ { \frac { 1 } { p } } \leq C \| x \| _ { l ^ { 1 } } ,
$$

where $C = \left( \sum _ { i = 1 } ^ { \infty } { \frac { 1 } { ( i - 1 + a ) ^ { p } } } \right) ^ { \frac { 1 } { p } } > 0$ . So $T _ { \infty }$ is a bounded, continuous and positively homogeneous operator from $l ^ { 1 }$ into $l ^ { p }$ ( $1 < p < \infty$ ). Similarly, take $p = 2$ , then for $a \geq 1$ ， we have

$$
C = \left( \sum _ { i = 1 } ^ { \infty } { \frac { 1 } { ( i - 1 + a ) ^ { 2 } } } \right) ^ { \frac { 1 } { 2 } } \leq \left( \sum _ { i = 1 } ^ { \infty } { \frac { 1 } { i ^ { 2 } } } \right) ^ { \frac { 1 } { 2 } } \leq { \sqrt { \frac { \pi ^ { 2 } } { 6 } } } .
$$

If $0 < a < 1$ ，then

$$
C = \left( \sum _ { i = 1 } ^ { \infty } \frac { 1 } { ( i - 1 + a ) ^ { 2 } } \right) ^ { \frac { 1 } { 2 } } \le \left( \frac { 1 } { ( 1 - 1 + a ) ^ { 2 } } + \sum _ { i = 2 } ^ { \infty } \frac { 1 } { ( i - 1 ) ^ { 2 } } \right) ^ { \frac { 1 } { 2 } } = \sqrt { \frac { 1 } { a ^ { 2 } } + \frac { \pi ^ { 2 } } { 6 } } .
$$

It follows from (2.1) and(3.4) that

$$
\| T _ { \infty } \| = \operatorname* { s u p } _ { \| x \| _ { l ^ { 1 } } = 1 } \| T _ { \infty } x \| _ { l ^ { 2 } } \leq C \leq C ( a ) .
$$

The desired results follow.

From the proof of Theorem 3.2, it is easy to obtain the following properties of operator defined by infinite dimensional generalized Hilbert tensor $\mathcal { H } _ { \infty }$

Theorem 3.3. For an m-order infnite dimensional generalized Hilbert tensor $\mathcal { H } _ { \infty }$ and $a > 0$ ，let $f ( x ) \ = \ { \mathcal { H } } _ { \infty } x ^ { m - 1 }$ .Then $f$ is a bounded, continuous and positively $( m - 1 )$ homogeneous operator from $l ^ { 1 }$ into $l ^ { p }$ ( $1 < p < \infty$ ）

Remark 3.2.(i) In Theorem 3.3, $\mathcal { H } _ { \infty }$ defines a bounded operator for $a > 0$ . Then it is unknown whether or not $\mathcal { H } _ { \infty }$ is bounded for $a < 0$ with $a \in \mathbb { R } \setminus \mathbb { Z } ^ { - }$ ： (ii) For an m-order infinite dimensional generalized Hilbert tensor， the upper bounds of norm of corresponding positively homogeneous operators are showed for $a > 0$ ，then for $a < 0$ with $a \in \mathbb { R } \setminus \mathbb { Z } ^ { - }$ ， it is unknown whether have similar conclusions or not.   
(iii) Are the upper bounds the best in Theorem 3.2?

# 3.3 Finite dimensional generalized Hilbert tensors

Theorem 3.4. Let ${ \mathcal { H } } _ { n }$ be an m-order $n$ -dimensional generalized Hilbert tensor. Assume that $a \in \mathbb { R } \backslash \mathbb { Z } ^ { - }$ and

$$
M ( a ) = \left\{ \begin{array} { l l } { \frac { 1 } { a } , } & { a > 0 ; } \\ { \frac { 1 } { \operatorname* { m i n } \{ a - [ a ] , 1 + [ a ] - a \} } , } & { - m ( n - 1 ) < a < 0 ; } \\ { \frac { 1 } { - m ( n - 1 ) - a } , } & { a < - m ( n - 1 ) , } \end{array} \right.
$$

where $[ a ]$ denotes the largest integer not exceeding $a$ . Then

(i） $| \lambda | \leq M ( a ) n ^ { m - 1 }$ for all $H$ -eigenvalues $\lambda$ of generalized Hilbert tensor ${ \mathcal { H } } _ { n }$ if m is even; (i) $| \mu | \leq M ( a ) n ^ { \frac { m } { 2 } }$ for all $Z$ -eigenvalues $\mu$ of generalized Hilbert tensor ${ \mathcal { H } } _ { n }$

Proof. Since $a \in \mathbb { R } \backslash \mathbb { Z } ^ { - }$ , Using the proof technique of Proposition 1.1, it is obvious that for all $i _ { 1 } , i _ { 2 } , \cdots , i _ { m } \in \{ 1 , 2 , \cdots , n \}$

$$
\begin{array} { r l } & { | i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + a | \geq a \mathrm { ~ f o r ~ } a > 0 , } \\ & { | i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + a | \geq \operatorname* { m i n } \{ a - [ a ] , 1 - ( a - [ a ] ) \} \mathrm { ~ f o r ~ } - m ( n - 1 ) < a < 0 , } \\ & { | i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + a | \geq - m ( n - 1 ) - a \mathrm { ~ f o r ~ } a < - m ( n - 1 ) . } \end{array}
$$

In conclusion,

$$
{ \frac { 1 } { | i _ { 1 } + i _ { 2 } + \cdots + i _ { m } - m + a | } } \leq M ( a ) .
$$

Then for each nonzero vector $x \in \mathbb { R } ^ { n }$ , we have

$$
\begin{array} { r l } & { \left| \mathcal { H } _ { \alpha } z ^ { \alpha \alpha } \right| = \left| \displaystyle \sum _ { \vec { u } _ { 1 } , \vec { u } _ { 2 } , \dotsc , \dotsc , \dotsc = 1 } ^ { n } \frac { x _ { \vec { u } _ { 1 } } x _ { \vec { u } _ { 2 } } \dotsc x _ { \vec { u } _ { m } } } { \vec { i } _ { 1 } + \vec { i } _ { 2 } + \dotsc + \dotsc + \dotsc + \dotsc + \dotsc } \right| } \\ & { \qquad \leq \displaystyle \sum _ { \vec { u } _ { 1 } , \dotsc , \dotsc , \dotsc , \dotsc = 1 } ^ { n } \frac { | x _ { \vec { u } _ { 1 } } x _ { \vec { u } _ { 2 } } \dotsc x _ { \vec { u } _ { m } } | } { | \vec { i } _ { 1 } + \dotsc + \dotsc + \dotsc + \dotsc + \dotsc + } } \\ & { \qquad \leq \mathcal { M } ( \alpha ) \displaystyle \sum _ { \vec { u } _ { 1 } , \dotsc , \dotsc , \dotsc + \dotsc } ^ { n } | x _ { \vec { u } _ { 1 } } | | x _ { \vec { v } _ { 2 } } | \dotsc , \dotsc , | x _ { \vec { u } _ { m } } | } \\ & { \qquad = \mathcal { M } ( \alpha ) \displaystyle ( \sum _ { \vec { u } = 1 } ^ { n } | x _ { \vec { u } _ { 1 } } | ) ^ { m } } \\ & { \qquad = \mathcal { M } ( \alpha ) | | x | | _ { 1 } ^ { n } . } \end{array}
$$

(i) From the fact that $\| x \| _ { 1 } \leq n ^ { 1 - \frac { 1 } { m } } \| x \| _ { m }$ , it follows that

$$
\begin{array} { c } { | \mathcal { H } _ { n } x ^ { m } | \leq M ( a ) \| x \| _ { 1 } ^ { m } \leq M ( a ) ( n ^ { 1 - \frac { 1 } { m } } \| x \| _ { m } ) ^ { m } } \\ { = M ( a ) n ^ { m - 1 } \| x \| _ { m } ^ { m } , } \end{array}
$$

and hence, for all nonzero vector $x \in \mathbb { R } ^ { n }$ ， we have

$$
\bigg | \mathcal { H } _ { n } \bigg ( \frac { x } { \| x \| _ { m } } \bigg ) ^ { m } \bigg | = \frac { | \mathcal { H } _ { n } x ^ { m } | } { \| x \| _ { m } ^ { m } } \leq M ( a ) n ^ { m - 1 } .
$$

It follows from the definition of eigenvalues of tensor that for each $H$ -eigenvalue $\lambda$ of generalized Hilbert tensor ${ \mathcal { H } } _ { n }$ ， there exists a nonzero vector $y \in \mathbb { R } ^ { n }$ such that

$$
\mathcal { H } _ { n } y ^ { m - 1 } = \lambda y ^ { [ m - 1 ] } ,
$$

and so,

$$
\mathcal { H } _ { n } y ^ { m } = y ^ { \top } ( \mathcal { H } _ { n } y ^ { m - 1 } ) = \lambda y ^ { \top } y ^ { [ m - 1 ] } = \lambda \sum _ { i = 1 } ^ { n } y _ { i } ^ { m } = \lambda \| y \| _ { m } ^ { m }
$$

since $m$ is even. Thus, it follows from (3.5) that

$$
| \lambda | = \frac { | \mathcal { H } _ { n } y ^ { m } | } { \| y \| _ { m } ^ { m } } = \left| \mathcal { H } _ { n } \left( \frac { y } { \| y \| _ { m } } \right) ^ { m } \right| \leq M ( a ) n ^ { m - 1 } .
$$

Since $\lambda$ is arbitrary $H$ -eigenvalue,this obtains the conclusion (i)

(ii) Similarly, from the fact that $\| x \| _ { 1 } \leq { \sqrt { n } } \| x \| _ { 2 }$ , it follows that

$$
\left| \mathcal { H } _ { n } x ^ { m } \right| \leq M ( a ) \| x \| _ { 1 } ^ { m } \leq M ( a ) n ^ { \frac { m } { 2 } } \| x \| _ { 2 } ^ { m } ,
$$

and hence, for all nonzero vector $x \in \mathbb { R } ^ { n }$ ， we have

$$
\left| \mathcal { H } _ { n } \left( \frac { x } { \| x \| _ { 2 } } \right) ^ { m } \right| = \frac { | \mathcal { H } _ { n } x ^ { m } | } { \| x \| _ { 2 } ^ { m } } \leq M ( a ) n ^ { \frac { m } { 2 } } .
$$

It follows from the definition of $Z$ -eigenvalues of tensor that for each $Z$ -eigenvalue $\mu$ of generalized Hilbert tensor ${ \mathcal { H } } _ { n }$ ， there exists a nonzero vector $z \in \mathbb { R } ^ { n }$ such that

$$
\mathcal { H } _ { n } z ^ { m - 1 } = \mu z ( z ^ { \top } z ) ^ { \frac { m - 2 } { 2 } } ,
$$

and so,

$$
\mathcal { H } _ { n } z ^ { m } = z ^ { \top } ( \mathcal { H } _ { n } z ^ { m - 1 } ) = \mu z ^ { \top } z ( z ^ { \top } z ) ^ { \frac { m - 2 } { 2 } } = \mu \left( \sum _ { i = 1 } ^ { n } z _ { i } ^ { 2 } \right) ^ { \frac { m } { 2 } } = \mu \| z \| _ { 2 } ^ { m } .
$$

Thus,by (3.6), we have

$$
| \mu | = \frac { | \mathcal { H } _ { n } z ^ { m } | } { \| z \| _ { 2 } ^ { m } } = \bigg | \mathcal { H } _ { n } \left( \frac { z } { \| z \| _ { 2 } } \right) ^ { m } \bigg | \leq M ( a ) n ^ { \frac { m } { 2 } } .
$$

Since $\mu$ is arbitrary $Z$ -eigenvalue, the desired conclusion follows.

Let $a > 0$ . Then the generalized Hilbert tensor ${ \mathcal { H } } _ { n }$ is positive (all entries are positive) and symmetric, and hence, its spectral radius $\rho ( \mathcal { H } _ { n } )$ and its $E$ -spectral radius $\rho _ { E } ( \mathcal { H } _ { n } )$ isits $H$ -eigenvalue and its $Z$ -eigenvalue, respectively. For more details, see Chang， Pearson and Zhang [1, 2], Qi [18], Song and Qi [21, 22] and Yang and Yang [27, 28]. So the following colusions are easy to obtain by Theorem 3.4.

Corollary 3.5. Let $\mathcal { H } _ { n }$ be an $m$ -order $n$ -dimensional generalized Hilbert tensor. Assume that $a > 0$ . Then

(i $\begin{array} { r } { | \lambda | \leq \rho ( \mathcal { H } _ { n } ) \leq \frac { n ^ { m - 1 } } { a } } \end{array}$ for all eigenvalues X of generalized Hilbert tensor ${ \mathcal { H } } _ { n }$ ifm is even;(i) $\begin{array} { r } { | \mu | \leq \rho _ { E } ( \mathcal { H } _ { n } ) \leq \frac { n ^ { \frac { m } { 2 } } } { a } } \end{array}$ for all $E$ eigenvalues μ of generalized Hilberttensor ${ \mathcal { H } } _ { n }$ ：

Remark 3.3. We prove the upper bounds of spectral radii in the above results. These upper bounds may not be the best, then the following problems deserve us further research: What is the best upper bounds? How compute such an upper bound?

# References

[1] K.C. Chang, K. Pearson, and T. Zhang, Some variational principles for $Z$ -eigenvalues of nonnegative tensors, Linear Algebra Appl. 438(2013) 4166-4182.   
[2] K.C. Chang， K. Pearson， and T. Zhang， Perron-Frobenius theorem for nonnegative tensors, Commun. Math. Sci. 6(2008) 507-520.   
[3] H. Chen， L. Qi， Positive definiteness and semi-definiteness of even order symmetric Cauchy tensors J. Ind. Manag. Optim. 11(4)(2015), 1263-1274.   
[4] Man-Duen Choi， Tricks for Treats with the Hilbert Matrix, Amer. Math. Monthly 90(1983),301-312.   
[5] H. Frazer, Note on Hilbert's Inequality, J. London Math. Soc. (1946) s1-21 (1): 7-9.   
[6] S. Fucik, J. Necas, J. Soucek and V. Soucek, Spectral Analysis of Nonlinear Operators, Lecture Notes in Mathematics 346, Springer-Verlag, Berlin， Heidelberg，New York, 1973.   
[7] D. Hilbert， Ein Beitrag zur Theorie des Legendre'schen Polynoms, Acta Mathematica (Springer Netherlands) 18(1894) 155-159.   
[8] J. He, T. Huang, Upper bound for the largest $Z$ -eigenvalue of positive tensors, Applied Mathematics Letters 38(2014),110-114.   
[9] J. He, Bounds for the largest eigenvalue of nonnegative tensors, Journal of Computational Analysis & Applications 20(7) (2016) 1290-1301.   
[10] J. He, Y. M. Liu, H. Ke, J. K. Tian, X. Li, Bounds for the $Z$ -spectral radius of nonnegative tensors, SpringerPlus, 5(1) (2016)， 1727.   
[11] A. E. Ingham, A Note on Hilbert's Inequality, J. London Math. Soc. (1936) s1-11 (3): 237-240.   
[12] T. Kato, On the Hilbert Matrix, Proc. American Math. Soc. 8(1)(1957) 73-81.   
[13] W. Li, D. Liu, S.W. Vong. $Z$ -eigenpair bounds for an irreducible nonnegative tensor, Linear Algebra Appl. 483 (2015) 182-199.   
[14] L.H. Lim, Singular values and eigenvalues of tensors: A variational approach, in: Proc. 1st IEEE International workshop on computational advances of multi-tensor adaptive processing, Dec. 13-15, 2005,pp.129-132.   
[15] W. Magnus On the Spectrum of Hilbert's Matrix, American Journal of Mathematics, 72(4)(1950) 699-704.   
[16] L. Qi, Eigenvalues of a real supersymmetric tensor, J. Symbolic Comput. 40(2005) 1302-1324.   
[17] L. Qi, Rank and eigenvalues of a supersymmetric tensor, the multivariate homogeneous polynomial and the algebraic hypersurface it defines, J. Symbolic Comput. 41(2006) 1309-1327.   
[18] L. Qi, Symmetric nonnegative tensors and copositive tensors, Linear Algebra Appl, 439(2013) 228-238.   
[19] L. Qi, Hankel Tensors: Associated Hankel Matrices and Vandermonde Decomposition, Commun.Math. Sci. 13(1)(2015) 113-125.   
[20] Y. Song, L. Qi, Infinite and finite dimensional Hilbert tensors, Linear Algebra Appl. 451 (2014) 1-14.   
[21] Y. Song and L. Qi, Positive eigenvalue-eigenvector of nonlinear positive mappings, Frontiers of Mathematics in China, 9(1)(2014) 181-199.   
[22] Y. Song and L. Qi, Spectral properties of positively homogeneous operators induced by higher order tensors, SIAM. J. Matrix Anal. & Appl., 34(4)(2013) 1581-1595.   
[23] Y. Song, L. Qi, Necessary and sufficient conditions for copositive tensors, Linear and Multilinear Algebra 63(1)(2015), 120-131.   
[24] O. Taussky， A remark concerning the characteristic roots of the finite segments of the Hilbert matrix, Quarterly Journal of Mathematies, Oxford ser., vol. 20 (1949) 80-83.   
[25] Y. Wang, K. Zhang, H. Sun, Criteria for strong H-tensors, Frontiers of Mathematics in China 11.3 (2016) 577-592.   
[26] C. Xu, Hankel tensors， Vandermonde tensors and their positivities， Linear Algebra Appl. 491 (2016) 56-72.   
[27] Q. Yang and Y. Yang, Further Results for Perron-Frobenius Theorem for Nonnegative Tensors I, SIAM. J. Matrix Anal. & Appl. 32(4)(2011) 1236-1250.   
[28] Y. Yang and Q. Yang, Further Results for Perron-Frobenius Theorem for Nonnegative Tensors, SIAM. J. Matrix Anal. & Appl., 31(5)(2010) 2517-2530.