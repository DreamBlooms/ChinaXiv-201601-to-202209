# B tensors and tensor complementarity problems

Yisheng Song! Wei Mei‡

# Abstract

In this paper, one of our main purposes is to prove the boundedness of solution set of tensor complementarity problem with B tensor such that the specific bounds only depend on the structural properties of tensor. To achieve this purpose, firstly, we present that each B tensor is strictly semi-positive and each B $_ 0$ tensor is semi-positive. Subsequencely， the strictly lower and upper bounds of different operator norms are given for two positively homogeneous operators defined by B tensor. Finally, with the help of the upper bounds of different operator norms,we show the strcitly lower bound of solution set of tensor complementarity problem with B tensor. Furthermore, the upper bounds of spectral radius and $E$ -spectral radius of B（ $\scriptstyle \mathrm { \mathrm { ~ B _ { 0 } ~ } }$ ）tensor are obtained,respectively, which achieves our another objective. In particular， such the upper bounds only depend on the principal diagonal entries of tensors.

Key words: $B$ tensor， Tensor complementarity problem，Spectral radius,Norm, Upper and lower bounds.

AMS subject classifications (2010): 47H15, 47H12, 34B10, 47A52, 47J10, 47H09, 15A48,47H07

# 1 Introduction

As a natural extension of linear complementarity problem, the tensor complementarity problem is a new topic emerged from the tensor community. Meanwhile, such a problem is a special type of nonlinear complementarity problems. So the tensor complementarity problem seems to have similar properties to the linear complementarity problem,and to have its particular properties other than ones of the classcal nonlinear complementarity problem, and to have some nice properites that depended on itself special structure. The notion of the tensor complementarity problem was used firstly by Song and Qi [1,2]. Recently, Huang and Qi [3] formulated an $n -$ person noncooperative game as a tensor complementarity problem and showed that a Nash equilibrium point of the multilinear game is equivalent to a solution of the tensor complementarity problem. By using specially structured properities of tensors, the properities of the tensor complementarity problem have been well studied in the literatures.For example, see Song, Yu [4] and Song, Qi [5] for strictly semi-positive tensors,Gowda, Luo, Qi and Xiu [6] and Luo, Qi and Xiu [7] for Z-tensors, Ding, Luo and Qi [8] for P-tensors, Wang, Huang，Bai [9] for exceptionally regular tensors, Bai, Huang and Wang [10] for strong P-tensors, Che, Qi, Wei [11] for some special tensors, Huang, Suo, Wang [12] for Q-tensors. Song and Qi [13],Ling, He, Qi [14,15], Chen, Yang, Ye [16] studied the tensor eigenvalue complementarity problem.

In past several decades, numerous mathematical works concerned with error bound analysis for the solution of linear complementarity problem by means of the special structure of the matrix $A$ . For more details,see [17-22]. Recently, motivated by the study on error bounds for linear complementarity problem， Song, Yu [4] and Song, Qi [23] extended the error bounds results of the linear complementarity problem to the tensor complementarity problem with strictly semi-positive tensors. However, there are relatively few works in the specific upper or lower bounds of the tensor complementarity problem, which is a weak link in this topics.

In this paper， we will give the boundedness of solution set of tensor complementarity problem with B tensor. Moreover， we will present the specifc lower bounds of such a problem, that only depend upon the structural property of B tensor.

To achieve the above goal, we need study the structured properities of tensor. Nowadays, miscellaneous structured tensors have been widely studied (Qi and Luo [24]), which is one of hot research topic. For more detail, see Zhang et al. [25] and Ding et al. [26] for M-tensors, Song, Qi[1] for $P$ ( $P _ { 0 }$ ) tensors and $B$ ( $B _ { 0 }$ ) tensors, Li and Li [27] for double $B$ tensors, Song, Qi [28,29] and Mei, Song [30] for Hilbert tensors.Recently, the concept of B tensor was first used by Song and Qi [1]. They gave many nice structured properties that is similar to ones of B matrices. For more nice properties and applications of B matrices, see Pena [31,32]. It is well known that each B matrix is a P matrix. However, the same conclusion only holds for even order symmetric B tensor [33]. Qi and Song [34] showed taht an even order symmetric $B$ tensor is positive definite. Yuan and You [33] proved that a non-symmetric $B$ tensor is not $P$ tensor in general. So there are many special properities of B tensors for further and serious consideration.

In section 3, we prove that each B tensor is strictly semi-positive and each $\mathrm { B } _ { 0 }$ tensor is semi-positive. So, the solution set of tensor complementarity problem with B tensor is bounded. In order to presenting the specific lower bounds of such a problem, in section 4, we give the strictly lower and upper bounds of different operator norms for two positively homogeneous operators defined by B tensor. By means of such the upper bounds,we establish the strcitly lower bound of solution set of tensor complementarity problem with B tensor. Furthermore, we achieve our another objective with the help of upper bounds of operator norms. That is, we obtain the upper bounds of spectral radius and $E$ -spectral radius of B ( $\mathrm { B } _ { 0 }$ ） tensor，which only depend on the principal diagonal entries of tensors.

# 2 Preliminaries and basic facts

An $m$ -order $n$ -dimensional tensor (hypermatrix) $\mathcal { A } = ( a _ { i _ { 1 } \cdots i _ { m } } )$ is a multi-array of real entries $a _ { i _ { 1 } \cdots i _ { m } } \in \mathbb { R }$ ，where $i _ { j } \in [ n ] = \{ 1 , 2 , \cdots , n \}$ for $j \in [ m ] = \{ 1 , 2 , \cdots , m \}$ .The set of all $m$ -order $n$ -dimensional tensor is denoted by $T _ { m , n }$ . If the entries $a _ { i _ { 1 } \cdots i _ { m } }$ are invariant under any permutation of their indices, then we call $\mathcal { A }$ a symmetric tensor, denoted by $S _ { m , n }$ .Let $\ b { \mathcal { A } } = ( a _ { i _ { 1 } \cdots i _ { m } } ) \in T _ { m , n }$ and a vector $x = ( x _ { 1 } , x _ { 2 } , \cdot \cdot \cdot , x _ { n } ) ^ { \top } \in \mathbb { R } ^ { n }$ . Then $A x ^ { m - 1 }$ is a vector with its $i$ th component defined by

$$
( \boldsymbol { A } \boldsymbol { x } ^ { m - 1 } ) _ { i } : = \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } a _ { i i _ { 2 } \cdots i _ { m } } \boldsymbol { x } _ { i _ { 2 } } \cdot \cdot \cdot \boldsymbol { x } _ { i _ { m } } , \forall i \in [ n ]
$$

and $A x ^ { m }$ is a homogeneous polynomial of degree $m$ ， defined by

$$
\mathcal { A } \boldsymbol { x } ^ { m } : = \boldsymbol { x } ^ { T } ( \mathcal { A } \boldsymbol { x } ^ { m - 1 } ) = \sum _ { i _ { 1 } , i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } a _ { i _ { 1 } i _ { 2 } \cdots i _ { m } } x _ { i _ { 1 } } \boldsymbol { x } _ { i _ { 2 } } \cdot \cdot \cdot \boldsymbol { x } _ { i _ { m } } .
$$

For any $q \in \mathbb { R } ^ { n }$ , the tensor complementarity problem, denoted by $T C P ( { \cal A } , q )$ , is to find $x \in \mathbb { R } ^ { n }$ such that

$$
x \geq 0 , q + { \mathcal { A } } x ^ { m - 1 } \geq 0 { \mathrm { ~ a n d ~ } } x ^ { T } ( q + { \mathcal { A } } x ^ { m - 1 } ) = 0 ,
$$

or to show that no such vector exists.

An n-dimensional $B$ matrix $B = ( b _ { i j } )$ is a square real matrix with its entries satisfying that for all $i \in [ n ]$ （204号

$$
\sum _ { j = 1 } ^ { n } b _ { i j } > 0 { \mathrm { ~ a n d ~ } } { \frac { 1 } { n } } \sum _ { j = 1 } ^ { n } b _ { i j } > b _ { i k } , i \neq k
$$

As a natural extension of $B$ matrices. Song and Qi [1] gave the definition of $B$ and $B _ { 0 }$ （20 tensor.

Definition 2.1. Let $B = ( b _ { i _ { 1 } \cdots i _ { m } } ) \in T _ { m , n }$ . Then $\boldsymbol { B }$ is said to be

(i) a $B$ tensor if for all $i \in [ n ] , \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } i _ { 3 } \cdots i _ { m } } > 0$ and

$$
{ \frac { 1 } { n ^ { m - 1 } } } \big ( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } i _ { 3 } \cdots i _ { m } } \big ) > b _ { i j _ { 2 } j _ { 3 } \cdots j _ { m } } \mathrm { ~ f o r ~ a l l ~ } ( j _ { 2 } , j _ { 3 } , \cdots , j _ { m } ) \not = ( i , i , \cdots , i ) ;
$$

(ii) a $B _ { 0 }$ tensor if for all $i \in [ n ] , \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } i _ { 3 } \cdots i _ { m } } \geq 0 \ { \mathrm { a n c } }$ 1

$$
{ \frac { 1 } { n ^ { m - 1 } } } \big ( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } i _ { 3 } \cdots i _ { m } } \big ) \geq b _ { i j _ { 2 } j _ { 3 } \cdots j _ { m } } \mathrm { ~ f o r ~ a l l ~ } ( j _ { 2 } , j _ { 3 } , \cdots , j _ { m } ) \not = ( i , i , \cdots , i ) .
$$

For each $i \in [ n ]$ ,let

$$
\beta _ { i } ( \mathcal { B } ) = \operatorname* { m a x } \{ 0 , b _ { i j _ { 2 } j _ { 3 } \cdots j _ { m } } ; ( j _ { 2 } , j _ { 3 } , \cdots , j _ { m } ) \neq ( i , i , \cdots , i ) , j _ { 2 } , j _ { 3 } , \cdots , j _ { m } \in [ n ] \} .
$$

Lemma 2.1. (Song and Qi [1, Theorem 5.1, 5.2, 5.3]) Let $B = ( b _ { i _ { 1 } \cdots i _ { m } } ) \in T _ { m , n }$ .If $\boldsymbol { B }$ isa $B$ （204号 tensor, then for each $i \in [ n ]$

$$
\vdots ) \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } i _ { 3 } \cdots i _ { m } } > n ^ { m - 1 } \beta _ { i } ( { \cal B } ) ;
$$

If $\boldsymbol { B }$ isa $B _ { 0 }$ tensor, then the above two inequalities hold with “>” being replaced by “≥”.

The concepts of tensor eigenvalues were introduced by Qi [35,36] to the higher order symmetric tensors,and the existence of the eigenvalues and some applications were studied there. Lim [37] independently introduced real tensor eigenvalues and obtained some existence results using a variational approach.

Definition 2.2. Let $\mathcal { A } = ( a _ { i _ { 1 } \cdots i _ { m } } ) \in T _ { m , n }$

(i) A number $\lambda \in \mathbb { C }$ is called an eigenvalue of $\mathcal { A }$ if there is a nonzero vector $x$ such that

$$
\begin{array} { r } { \mathcal { A } \mathcal { x } ^ { m - 1 } = \lambda \mathcal { x } ^ { [ m - 1 ] } . } \end{array}
$$

and $x$ is called an eigenvector of $\mathcal { A }$ associated with $\lambda$ .We call such an eigenvalue $H$ -eigenvalue if it is real and has a real eigenvector $x$ , and call such a real eigenvector （20 $x$ H-eigenvector.

(ii) A number $\mu \in \mathbb { C }$ is said to be an $E$ -eigenvalue of $A$ if there exists a nonzero vector $x$ （204号 such that

$$
A x ^ { m - 1 } = \mu x ( x ^ { T } x ) ^ { \frac { m - 2 } { 2 } } ,
$$

and $x$ is called an $E$ -eigenvector of $\mathcal { A }$ associated with $\mu$ . It is clear that if $x$ is real, then $x$ is also real. In this case, $\mu$ and $x$ are called a $Z$ -eigenvalue of $A$ and a $Z$ -eigenvector of $\mathcal { A }$ , respectively.

We now give the definitions of (strictly） semi-positive tensors (Song and Qi [2,5]).

Definition 2.3. Let $\mathcal { A } = ( a _ { i _ { 1 } \cdots i _ { m } } ) \in T _ { m , n }$ ： $A$ is said to be

(i） semi-positive iff for each $x \geq 0$ and $x \neq 0$ , there exists an index $k \in [ n ]$ such that

$$
x _ { k } > 0 \mathrm { ~ a n d ~ } \left( A x ^ { m - 1 } \right) _ { k } \geq 0 ;
$$

(ii） strictly semi-positive iff for each $x \geq 0$ and $x \neq 0$ , there exists an index $k \in [ n ]$ such that

$$
x _ { k } > 0 { \mathrm { ~ a n d ~ } } \left( A x ^ { m - 1 } \right) _ { k } > 0 .
$$

For $x \in \mathbb { R } ^ { n }$ ,it is well known that

$$
\| x \| _ { \infty } : = \operatorname* { m a x } \{ | x _ { i } | ; i \in [ n ] \} \ \mathrm { a n d } \ \| x \| _ { p } : = ( \sum _ { i = 1 } ^ { n } | x _ { i } | ^ { p } ) ^ { \frac { 1 } { p } } ( p \geq 1 )
$$

are two main norms defined on $\mathbb { R } ^ { n }$ . Then for a continuous, positively homogeneous operator （20 $T : \mathbb { R } ^ { n }  \mathbb { R } ^ { n }$ , it is obvious that

$$
\| T \| _ { p } : = \operatorname* { m a x } _ { \| x \| _ { p } = 1 } \| T ( x ) \| _ { p } { \mathrm { ~ a n d ~ } } \| T \| _ { \infty } : = \operatorname* { m a x } _ { \| x \| _ { \infty } = 1 } \| T ( x ) \| _ { \infty }
$$

are two operator norms of T. For $A \in T _ { m , n }$ ， we may define a continuous, positively homogeneous operator $T _ { \mathcal { A } } : \mathbb { R } ^ { n } \to \mathbb { R } ^ { n }$ by

$$
T _ { \mathcal { A } } ( x ) : = \left\{ \begin{array} { l l } { \| x \| _ { 2 } ^ { 2 - m } \mathcal { A } x ^ { m - 1 } } & { x \neq 0 . } \\ { 0 } & { x = 0 . } \end{array} \right.
$$

When $m$ is even,we may define another continuous, positively homogeneous operator $F _ { A } :$ $\mathbb { R } ^ { n } \to \mathbb { R } ^ { n }$ by for any $x \in \mathbb { R } ^ { n }$ ，

$$
F _ { A } ( x ) : = \left( A x ^ { m - 1 } \right) ^ { \left[ { \frac { 1 } { m - 1 } } \right] } .
$$

The following upper bounds and properities of the operator norm were established by Song and Qi [23,38].

Lemma 2.2. (Song and Qi [38,Theorem 4.3] and [23,Lemma 3,Lemma 4]） Let ${ \mathcal { A } } =$ $( a _ { i _ { 1 } \cdots i _ { m } } ) \in T _ { m , n }$ ， Then

$$
\begin{array} { r l } & { | | T _ { A } | | _ { \infty } \le \displaystyle \operatorname* { m a x } _ { i \in [ s , \ t _ { i } , \ t _ { j - \tau } , i = 1 ] } | \alpha _ { i j _ { \tau } , i _ { \tau } , i _ { \tau } , i _ { \tau } } | , } \\ & { | | F _ { A } | | _ { \infty } \le \displaystyle \operatorname* { m a x } _ { i \in [ s , \ t _ { i } ] } \left( \underbrace { \frac { \pi } { 2 } } _ { i _ { \tau } , i _ { \tau } , i _ { \tau } = 1 } | \alpha _ { i i _ { 2 } \to i _ { \tau } } | \right) ^ { \frac { 1 } { m - 1 } } \xi ^ { \eta } m ~ i s ~ e v e n ; } \\ & { | | T _ { A } | | _ { \varepsilon } \le n ^ { \frac { \kappa + 2 } { \gamma } } \left( \displaystyle \sum _ { i = 1 } ^ { n } \left( \underbrace { \frac { \pi } { 2 } } _ { i _ { \tau } , i _ { \tau } , i _ { \tau } = 1 } | \alpha _ { i i _ { 2 } \to i _ { \tau } } | \right) ^ { \eta } \right) ^ { \frac { 1 } { \eta } } ; } \\ & { | | F _ { A } | | _ { \infty } \le \left( \displaystyle \sum _ { i = 1 } ^ { n } \left( \underbrace { \frac { \pi } { 2 } } _ { i _ { \tau } , i _ { \tau } , i _ { \tau } = 1 } | \alpha _ { i i _ { 2 } \to i _ { \tau } } | \right) ^ { \frac { \eta } { m - 1 } } \right) ^ { \frac { 1 } { \eta } } ~ i ^ { \eta } ~ i s ~ e v e n ; } \end{array}
$$

# 3B tensor is strictly semi-positive

Theorem 3.1. Let $\boldsymbol { B }$ be an $m$ -order $n$ -dimensional $B$ tensor. Then $\boldsymbol { B }$ is strictly semipositive.

Proof. Suppose that $\boldsymbol { B }$ is not strictly semi-positive. Then there exists $x \geq 0$ and $x \neq 0$ ，for all $k \in [ n ]$ with $x _ { k } > 0$ such that

$$
\left( B x ^ { m - 1 } \right) _ { k } \leq 0 .
$$

Choose $x _ { i } > 0$ with $x _ { i } \geq x _ { k }$ for all $k \in [ n ]$ . Clearly, $( B x ^ { m - 1 } ) _ { i } \leq 0$ . Then we have

$$
\begin{array} { r c l } { { \displaystyle \mathbb { D } \geq \left( B _ { 2 } \times ^ { m - 1 } \right) _ { i = } + \sum _ { j _ { 1 } \leq j _ { 2 } < i \leq n - 1 } ^ { N } b _ { i , j _ { 1 } , j _ { 2 } , k _ { 1 } } , \forall _ { i \leq n - 1 } C _ { j _ { 1 } , i \leq n - 1 } } } \\ { { } } & { { } } & { { } } \\ { { } } & { { = b _ { i , j _ { 1 } , j _ { 2 } , k _ { 1 } } + \sum _ { j _ { 1 } \leq i \leq n - 1 } b _ { j _ { 2 } , j _ { 2 } , k _ { 1 } } , \forall _ { i \leq n - 1 } C _ { j _ { 1 } , j _ { 2 } , k _ { 1 } } , } } \\ { { } } & { { } } & { { } } \\ { { } } & { { + \displaystyle \sum _ { \mathrm { ~ A _ { i , j _ { k - 1 } , j _ { k } } ~ \geq ~ 0 ~ } , \mathrm { ~ B _ { i , j _ { k - 1 } , j _ { k } } ~ \leq ~ - ~ B _ { i , j _ { k } } ~ } } } } \\ { { } } & { { } } & { { } } \\ { { } } & { { \displaystyle \geq \bar { b } _ { i , j _ { k - 1 } , j _ { 2 } , k _ { 1 } } + \sum _ { \mathrm { ~ B _ { i , j _ { k - 1 } , j _ { k } } ~ \geq ~ 0 ~ } , \mathrm { ~ B _ { i , j _ { k - 1 } , j _ { k } } ~ \geq ~ 0 ~ } , \mathrm { ~ B _ { i , j _ { k - 1 } } ~ } } } } \\ { { } } & { { } } & { { } } \\ { { } } & { { + \displaystyle \sum _ { \mathrm { ~ A _ { i , j _ { k - 1 } , j _ { k } } ~ \leq ~ n ~ } } b _ { i , j _ { k - 1 } , j _ { k } } , \forall _ { i \leq n - 1 } C _ { j _ { 1 } , j _ { k } } , \forall i , } } \\ { { } } & { { } } & { { } } \\ { { } } & { { \displaystyle \geq \left( b _ { i , j _ { k - 1 } } + \sum _ { j _ { k - 1 } , j _ { k } \geq i \leq n - 1 } b _ { j _ { k - 1 } , j _ { k } } \right) \sum _ { j _ { 1 } \leq i \leq n - 1 } ^ { N } b _ { i , j _ { k } } , } } \end{array}
$$

By Lemma 2.1 (ii),we obtain

$$
0 < \left( b _ { i i \cdots i } + \sum _ { b _ { i i _ { 2 } \cdots i _ { m } } < 0 } b _ { i i _ { 2 } \cdots i _ { m } } \right) x _ { i } ^ { m - 1 } \leq \left( \mathcal { B } x ^ { m - 1 } \right) _ { i } \leq 0 ,
$$

a contradiction. Consequently, $\boldsymbol { B }$ must be strictly semi-positive.

Using the similar proof technique, it is easy to prove the following conclusion.

Theorem 3.2. Let $\boldsymbol { B }$ be an $m$ -order $n$ -dimensional $B _ { 0 }$ tensor. Then $\boldsymbol { B }$ is semi-positive.

Clearly, by Theorem 3.2 of Song and Yu [4] and Corollary 3.3 of Song and Qi [2]，we easily obtain the following.

Corollary 3.3. Let $\boldsymbol { B }$ be an m-order $n$ -dimensional $B$ tensor. Then for each $q \in \mathbb { R } ^ { n }$ ，the tensor complementarity problem $T C P ( B , q )$ has always a solution. Furthermore, the solution set of the $T C P ( B , q )$ is bounded for each $q \in \mathbb { R } ^ { n }$ ：

# 4 Boundedness about B tensors

By means of the special structure of B tensor, now we present its upper bounds of the operator norm.

Theorem 4.1. Let $\boldsymbol { B }$ be an m-order n-dimensional $B$ tensor. Then

$$
 n ^ { \frac { m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } \beta _ { i } ( B ) < n ^ { \frac { 2 - m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } \sum _ { i _ { 2 } , \ldots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } } \leq \| T _ { B } \| _ { \infty } < n ^ { \frac { m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } b _ { i i \cdots i } ;
$$

$$
\ L _ { l } ^ { \frac { m p - 2 } { 2 p } } \left( \sum _ { i = 1 } ^ { n } { \left( \beta _ { i } ( \beta ) \right) ^ { p } } \right) ^ { \frac { 1 } { p } } <  { n } ^ { \frac { 2 p - p m - 2 } { 2 p } } \left( \sum _ { i = 1 } ^ { n } { \left( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } { b _ { i i _ { 2 } } } \cdots i _ { m } \right) ^ { p } } \right) ^ { \frac { 1 } { p } } \le \| T _ { B } \| _ { p } <  { n } ^ { \frac { m p - 2 } { 2 p } } \bigl ( \sum _ { i = 1 } ^ { n } { b _ { i i _ { 2 } } ^ { i i _ { 2 } } } \cdots i _ { m - 1 } \bigr ) ^ { \frac { 1 } { p } }
$$

where $\beta _ { i } ( \mathcal { B } ) = \operatorname* { m a x } \{ 0 , b _ { i j _ { 2 } j _ { 3 } \cdots j _ { m } } ; ( j _ { 2 } , j _ { 3 } , \cdot \cdot \cdot , j _ { m } ) \neq ( i , i , \cdot \cdot \cdot , i ) , j _ { 2 } , j _ { 3 } , \cdot \cdot \cdot , j _ { m } \in [ n ] \} .$

Proof. (i) Choose $e = ( 1 , 1 , \cdots , 1 ) ^ { \top }$ . Then $\| e \| _ { \infty } = 1$ and $\| e \| _ { 2 } = n ^ { \frac { 1 } { 2 } }$ ，and hence by Lemma 2.1 (ii), we have

$$
\begin{array} { l } { \displaystyle | | T _ { B } ( \epsilon ) | | _ { \infty } = \operatorname* { m a x } _ { i \in [ n ] } \left| | \epsilon | | _ { 2 } ^ { 2 - m } \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } } \right| } \\ { = n ^ { \frac { 2 - m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } } } \\ { > n ^ { \frac { 2 - m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } n ^ { m - 1 } \beta _ { i } ( B ) } \\ { = n ^ { \frac { m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } \beta _ { i } ( B ) . } \end{array}
$$

Consequently,

$$
n ^ { \frac { m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } \beta _ { i } ( { \mathcal { B } } ) < n ^ { \frac { 2 - m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } } \leq \| T _ { \mathcal { B } } \| _ { \infty } .
$$

Now we show the right inequality. It follows from Lemma 2.1 (i) together with the fact that $\| x \| _ { 1 } \leq n \| x \| _ { \infty }$ and $\| x \| _ { 2 } \leq { \sqrt { n } } \| x \| _ { \infty }$ that

$$
\begin{array} { r l } & { \| \Gamma _ { 2 } \| _ { \infty } - \underset { 1 , 1 , \ldots , 1 } { \operatorname* { m a x } } \ | \Gamma _ { \mathrm { e f f } } \| _ { \infty } - \underset { 1 , 1 , \ldots , 1 } { \operatorname* { m a x } } \ \underset { 1 \leq m \leq n } { \operatorname* { m a x } } \ \bigg \| \alpha \underset { 1 , \ldots , 1 , \ldots , 1 } { \overset { \mathbf { x } \operatorname* { m a x } } { \operatorname* { m a x } } } \bigg \| \alpha \underset { 1 , \ldots , 1 , \ldots , 1 } { \overset { \mathbf { x } \operatorname* { m a x } } { \operatorname* { m a x } } } \ \underset { 1 \leq m \leq n - 1 , \ldots , 1 } { \overset { \mathbf { x } \operatorname* { m a x } } { \operatorname* { m a x } } } \bigg \| } \\ & { \leq \underset { 1 , 1 , \ldots , 1 } { \overset { \operatorname* { m a x } } { \operatorname* { m a x } } } \ \underset { 1 \leq m \leq n } { \overset { \mathbf { x } \to \infty } { \operatorname* { m a x } } } \ \underset { 1 \leq m \leq n } { \overset { \mathbf { x } \to \infty } { \operatorname* { m a x } } } \ \underset { 1 \leq m \leq n - 1 } { \overset { \mathbf { x } \operatorname* { m a x } } { \operatorname* { m a x } } } \ \underset { 1 \leq m \leq n - 1 } { \overset { \mathbf { x } \operatorname* { m a x } } { \operatorname* { m a x } } } \underset { 1 \leq m \leq n - 1 } { \operatorname* { m a x } } \ \underset { 1 \leq m \leq n } { \operatorname* { m a x } } \bigg \} } \\ & { \leq \underset { 1 , \ldots , 1 } { \overset { \operatorname* { m a x } } { \operatorname* { m a x } } } \ \underset { 1 \leq m \leq n } { \overset { \mathrm { \alpha } \operatorname* { m a x } } { \operatorname* { m a x } } } \ \underset { 1 \leq m \leq n } { \overset { \operatorname* { m a x } } { \operatorname* { m a x } } } \ \bigg ( \underset { 1 \leq m \leq n - 1 } { \overset { \mathbf { x } \operatorname* { m a x } } { \operatorname* { m a x } } } \ \underset { 1 \leq m \leq n - 1 } { \operatorname* { m a x } } \underset { 1 \leq m \leq n - 1 } { \operatorname* { m a x } } \ \underset { 1 \leq m \leq n } { \operatorname* { m a x } } \bigg ) } \\ &  - \underset { 1 , 2 , \ldots , 1 } { \overset { \mathrm { a b s s u m } } { \operatorname* { m a x } } } \ \underset { 1 \leq m \leq n } { \operatorname* { m a x } } \ \Big \| \alpha \underset { 1 , \ldots , 1 } { \overset { \mathbf { x } \operatorname* { m a x } } { \operatorname* { m a x } } } \ \bigg ( \underset { 1 \leq m \leq n - 1 } { \overset { \mathbf { x } \operatorname* { m a x } } { \operatorname* { m a x } } } \ \underset { 1 \leq m \leq n - 1 } { \operatorname* { m a x } } \ \underset { 1 \leq m \leq n - 1 }  \operatorname*  m a x  \end{array}
$$

(ii) Choose $y = ( n ^ { - \frac { 1 } { p } } , n ^ { - \frac { 1 } { p } } , \cdot \cdot \cdot , n ^ { - \frac { 1 } { p } } ) ^ { \top }$ . Then $\| y \| _ { p } = 1$ and $\lVert y \rVert _ { 2 } = n ^ { \frac { p - 2 } { 2 p } }$ ， and hence by Lemma 2.1 (ii), we have

$$
\begin{array} { r l } { \displaystyle | | T _ { B } ( y ) | | _ { p } ^ { p } = \sum _ { i = 1 } ^ { n } \left| | y | | _ { 2 } ^ { 2 - m } \sum _ { i _ { 1 } , \ldots , i _ { m - 1 } = 1 } ^ { n } b _ { i _ { 2 } \cdots i _ { m } } ( n ^ { - \frac { 1 } { p } } ) ^ { m - 1 } \right| ^ { p } } & { } \\ { \displaystyle = n ^ { ( p - 2 ) ( 2 - m ) } \sum _ { i _ { 1 } = 1 } ^ { n } n ^ { 1 - m } \left( \sum _ { j _ { 2 } , \ldots , j _ { m } = 1 } ^ { n } b _ { i _ { 2 } \cdots i _ { m } } \right) ^ { p } } & { } \\ { \displaystyle > n ^ { ( \frac { p - 2 ) ( 2 - m ) } { 2 } } \sum _ { i = 1 } ^ { n } n ^ { 1 - m } \left( n ^ { m - 1 } \beta _ { i } ( B ) \right) ^ { p } } & { } \\ { \displaystyle = n ^ { \frac { m - 2 } { 2 } } \sum _ { i = 1 } ^ { n } \left( \beta _ { i } ( B ) \right) ^ { p } . } \end{array}
$$

Consequently,

$$
n ^ { \frac { m p - 2 } { 2 p } } \left( \sum _ { i = 1 } ^ { n } \left( \beta _ { i } ( \boldsymbol { \mathcal { B } } ) \right) ^ { p } \right) ^ { \frac { 1 } { p } } < n ^ { \frac { 2 p - p m - 2 } { 2 p } } \left( \sum _ { i = 1 } ^ { n } \left( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } } \right) ^ { p } \right) ^ { \frac { 1 } { p } } \leq \| T _ { B } \| _ { p } .
$$

Next we show the right inequality. By Lemma 2.1 (i) together with the fact that $\Vert x \Vert _ { q } \leq$ $\| x \| _ { p } \leq n ^ { { \frac { 1 } { p } } - { \frac { 1 } { q } } } \| x \| _ { q }$ for $q > p$ ， we obtain

$$
\begin{array} { r l } { \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } & { = \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { = \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad - \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { = \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad + \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad \le \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad \le \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad \le \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad - \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad - \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad - \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad - \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad - \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad - \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| ^ { 2 } } \\ & { \quad \le \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| _ { \mathrm { K } } \| \Gamma ( \mathbf { E } ) \| _ { \mathrm { K } } ^ { 2 } } \\ & { \quad \le \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| _ { \mathrm { K } } ^ { 2 } } \\ & { \quad \le \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| _ { \mathrm { K } } ^ { 2 } } \\ &  \quad \le \frac { 1 } { M _ { \mathrm { K } } ^ { 2 } } \| \Gamma ( \mathbf { E } ) \| _ { \mathrm { K } } ^ { 2 }  \end{array}
$$

The desired conclusions follow.

Theorem 4.2. Let $\boldsymbol { B }$ be an m-order $n$ -dimensional $B$ tensor. If m is even, then

$$
\begin{array} { r l r } {  { ( i ) \ n ( \beta _ { i } ( \mathscr { B } ) ) ^ { \frac { 1 } { m - 1 } } < \operatorname* { m a x } _ { i \in [ n ] } ( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } } ) ^ { \frac { 1 } { m - 1 } } \leq \| F _ { B } \| _ { \infty } \leq \operatorname* { m a x } _ { i \in [ n ] } ( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } | b _ { i i _ { 2 } \cdots i _ { m } } | ) } } \\ & { } & { < n \operatorname* { m a x } _ { i \in [ n ] } b _ { i i \cdots i } ^ { \frac { 1 } { m - 1 } } ; } \end{array}
$$

$$
\mathbb { \Lambda } ^ { \frac { p - 1 } { p } } \left( \sum _ { i = 1 } ^ { n } \left( \beta _ { i } ( B ) \right) ^ { \frac { p } { m - 1 } } \right) ^ { \frac { 1 } { p } } < \frac { 1 } { \sqrt { \eta } } \left( \sum _ { i = 1 } ^ { n } \left( \sum _ { i _ { 2 } , \ldots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } } \right) ^ { \frac { p } { m - 1 } } \right) ^ { \frac { 1 } { p } } \le \| F _ { B } \| _ { p } < n ^ { \frac { p - 1 } { p } } \left( \sum _ { i = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } + 1 } ^ { \frac { p - 1 } { p } } \right) ^ { \frac { 1 } { p } }
$$

Proof. (i) Choose $e = ( 1 , 1 , \cdots , 1 ) ^ { \top }$ . Then $\| e \| _ { \infty } = 1$ , and hence by Lemma 2.1 (ii), we have

$$
\begin{array} { l } { \displaystyle | | F _ { \mathcal { B } } ( e ) | | _ { \infty } = \operatorname* { m a x } _ { i \in [ n ] } \left. \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } } \right. ^ { \frac { 1 } { m - 1 } } } \\ { = \displaystyle \operatorname* { m a x } _ { i \in [ n ] } \left( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } } \right) ^ { \frac { 1 } { m - 1 } } } \\ { > \displaystyle n \operatorname* { m a x } _ { i \in [ n ] } \left( \beta _ { i } ( \mathcal { B } ) \right) ^ { \frac { 1 } { m - 1 } } . } \end{array}
$$

So,by the definition of the operator norm,we have

$$
n \operatorname* { m a x } _ { i \in [ n ] } \left( \beta _ { i } ( \boldsymbol { \mathcal { B } } ) \right) ^ { \frac { 1 } { m - 1 } } < \operatorname* { m a x } _ { i \in [ n ] } \left( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } } \right) ^ { \frac { 1 } { m - 1 } } \leq \| F _ { \boldsymbol { \mathcal { B } } } \| _ { \infty } .
$$

From Lemma 2.2 (ii) and 2.1 (i),it follows that

$$
\| F _ { B } \| _ { \infty } \leq \operatorname* { m a x } _ { i \in [ n ] } \left( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } | b _ { i i _ { 2 } \cdots i _ { m } } | \right) ^ { \frac { 1 } { m - 1 } } < \operatorname* { m a x } _ { i \in [ n ] } \left( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i \cdots i } \right) ^ { \frac { 1 } { m - 1 } } = n \operatorname* { m a x } _ { i \in [ n ] } b _ { i i \cdots i } ^ { \frac { 1 } { m - 1 } } .
$$

(ii) Choose $y = ( n ^ { - \frac { 1 } { p } } , n ^ { - \frac { 1 } { p } } , \cdot \cdot \cdot , n ^ { - \frac { 1 } { p } } ) ^ { \top }$ . Then $\| y \| _ { p } = 1$ ,and hence by Lemma 2.1 (ii), we have

$$
\begin{array} { l } { \displaystyle \| F _ { B } ( y ) \| _ { p } ^ { p } = \sum _ { i = 1 } ^ { n } \left| \displaystyle \sum _ { i , j , \cdots , i _ { m } = 1 } ^ { n } b _ { i _ { i 2 } \cdots i _ { m } } ( n ^ { - \frac { 1 } { p } } ) ^ { m - 1 } \right| ^ { \frac { 1 } { m - 1 } } } \\ { = \displaystyle \sum _ { i = 1 } ^ { n } \frac { 1 } { n } \left( \displaystyle \sum _ { j _ { 1 2 } , \ldots , i _ { m } = 1 } ^ { n } b _ { i _ { i 2 } \cdots i _ { m } } \right) ^ { \frac { n } { m - 1 } } } \\ { > \frac { 1 } { n } \displaystyle \sum _ { i = 1 } ^ { n } ( n ^ { m - 1 } \beta _ { i } ( B ) ) ^ { \frac { n } { m - 1 } } } \\ { = n ^ { p - 1 } \displaystyle \sum _ { i = 1 } ^ { n } ( \beta _ { i } ( B ) ) ^ { \frac { n } { m - 1 } } . } \end{array}
$$

Consequently,

$$
n ^ { \frac { p - 1 } { p } } \left( \sum _ { i = 1 } ^ { n } \left( \beta _ { i } ( \boldsymbol { \mathcal { B } } ) \right) ^ { \frac { p } { m - 1 } } \right) ^ { \frac { 1 } { p } } < \frac { 1 } { \sqrt [ ] { n } } \left( \sum _ { i = 1 } ^ { n } \left( \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } b _ { i i _ { 2 } \cdots i _ { m } } \right) ^ { \frac { p } { m - 1 } } \right) ^ { \frac { 1 } { p } } \leq \| F _ { B } \| _ { p } .
$$

Next we show the right inequality. By Lemma 2.1 (i) together with the fact that $\| x \| _ { 1 } \leq$

（204号 $n ^ { 1 - \frac { 1 } { p } } \| x \| _ { p }$ for $p > 1$ ， we obtain

$$
\begin{array} { r l } & { \| F _ { k } \| _ { \ell } ^ { \infty } = \underset { \mathrm { I } ^ { \infty } \times \mathrm { I } } { \operatorname* { m a x } } \| F _ { k } \| _ { \ell } ^ { \infty } \| _ { \infty } ^ { 2 } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname* { m a x } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \overset { \boldsymbol { \kappa } } { \operatorname { m } } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \overset { \boldsymbol { \kappa } } { \operatorname { m } } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \overset { \boldsymbol { \kappa } } { \operatorname { m } } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname { m a x } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \overset { \boldsymbol { \kappa } } { \operatorname { m } } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname { m a x } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname { m a x } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname { m a x } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname { m a x } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname { m a x } } } \\ &  \qquad \times \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname* { m a x } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \overset { \boldsymbol { \kappa } } { \operatorname { m } } } \bigg ( \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname* { m a x } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \overset { \boldsymbol { \kappa } } { \operatorname { m } } } \bigg ) \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname* { m a x } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname { m a x } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname { m a x } } \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname { m a x } } \bigg ( \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname* { m a x } } \bigg ( \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname* { m a x } } \bigg ( \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname* { m a x } } \bigg ) \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname* { m a x } } \bigg ( \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname* { m a x } } \bigg ( \underset { \mathrm { I } ^ { 1 } \times \mathrm { I } } { \operatorname* { m a x } } \bigg )  \end{array}
$$

The desired conclusions follow.

Theorem 4.3. Let $\boldsymbol { B }$ be an m-order $n$ -dimensional $B _ { 0 }$ tensor. Then

认 $\begin{array} { r } { n ^ { \frac { m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } \beta _ { i } ( \pmb { \mathscr { B } } ) \leq \| T _ { \pmb { \mathscr { B } } } \| _ { \infty } \leq n ^ { \frac { m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } b _ { i i \cdots i } ; } \end{array}$ （20   
ii $n ^ { \frac { m p - 2 } { 2 p } } \left( \sum _ { i = 1 } ^ { n } { \left( \beta _ { i } ( \mathcal { B } ) \right) ^ { p } } \right) ^ { \frac { 1 } { p } } \leq \| T _ { \mathcal { B } } \| _ { p } \leq n ^ { \frac { m p - 2 } { 2 p } } \left( \sum _ { i = 1 } ^ { n } { b _ { i i \cdots i } ^ { p } } \right) ^ { \frac { 1 } { p } } \ i f p \geq 1 ;$ （204号   
(iii) $n \left( \beta _ { i } ( \mathcal { B } ) \right) ^ { \frac { 1 } { m - 1 } } \leq \| F _ { \mathcal { B } } \| _ { \infty } \leq n \operatorname* { m a x } _ { i \in [ n ] } b _ { i i \cdots i } ^ { \frac { 1 } { m - 1 } }$ if m is even;   
(iu) $n ^ { \frac { p - 1 } { p } } \left( \sum _ { i = 1 } ^ { n } ( \beta _ { i } ( \mathcal { B } ) ) ^ { \frac { p } { m - 1 } } \right) ^ { \frac { 1 } { p } } \leq \| F _ { \mathcal { B } } \| _ { p } \leq n ^ { \frac { p - 1 } { p } } \left( \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } ^ { \frac { p } { m - 1 } } \right) ^ { \frac { 1 } { p } } ~ i f ~ m ~ i s ~ e v e n ~ a n d ~ p \geq 1 .$

For a $B$ tensor $\boldsymbol { B }$ , it is obvious that its upper bounds of the operator norm are simpler in form than ones of Lemma 2.2, but we cannot compare their size relationship. By constructing following two examples, we show that there exists $B$ tensors such that the above upper bounds of $\| T _ { B } \|$ and $\| F _ { B } \|$ are smaller than the ones of Lemma 2.2.

Example 4.1. Let $B = ( b _ { i _ { 1 } i _ { 2 } i _ { 3 } i _ { 4 } } ) \in S _ { 4 , 3 }$ ， where $b _ { 1 1 1 1 } = b _ { 3 3 3 3 } = 6$ ， $b _ { 2 2 2 2 } = 5$ ， $b _ { 1 3 3 3 } = b _ { 3 1 3 3 } =$ （204 $b _ { 3 3 1 3 } = b _ { 3 3 3 1 } = 1$ ， $b _ { 2 3 2 2 } = b _ { 2 2 3 2 } = b _ { 2 2 2 3 } = b _ { 3 2 2 2 } = 1 . 5$ and all other $b _ { i _ { 1 } i _ { 2 } i _ { 3 } i _ { 4 } } = 2$ . Then $\boldsymbol { B }$ is $a$ $B$ tensor.

Proof. It is obvious that $\sum _ { 2 , i _ { 3 } , i _ { 4 } = 1 } ^ { 3 } b _ { i i _ { 2 } i _ { 3 } i _ { 4 } } > 0 { \mathrm { ~ f o r ~ } } i = 1 , 2 , 3 .$ （20 2 For $i = 1$ ，we have

$$
\frac { 1 } { n ^ { m - 1 } } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { 3 } b _ { 1 i _ { 2 } i _ { 3 } i _ { 4 } } \right) = \frac { 1 } { 3 ^ { 4 - 1 } } \times 5 7 = \frac { 5 7 } { 2 7 } > 2 ,
$$

and hence, $\begin{array} { r } { \frac { 1 } { n ^ { m - 1 } } \left( \displaystyle \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { 3 } b _ { 1 i _ { 2 } i _ { 3 } i _ { 4 } } \right) > b _ { 1 j _ { 2 } j _ { 3 } j _ { 4 } } \mathrm { ~ f o r ~ a l l ~ } ( j _ { 2 } , j _ { 3 } , j _ { 4 } ) \neq ( 1 , 1 , 1 ) . } \end{array}$ （20 For $i = 2$ ， we have

$$
\frac { 1 } { n ^ { m - 1 } } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { 3 } b _ { 2 i _ { 2 } i _ { 3 } i _ { 4 } } \right) = \frac { 1 } { 3 ^ { 4 - 1 } } \times 5 5 . 5 = \frac { 5 5 . 5 } { 2 7 } > 2 ,
$$

$$
\begin{array} { r } { \frac { 1 } { n ^ { m - 1 } } \left( \displaystyle \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } b _ { 2 i _ { 2 } i _ { 3 } i _ { 4 } } \right) > b _ { 2 j _ { 2 } j _ { 3 } j _ { 4 } } \mathrm { ~ f o r ~ a l l ~ } ( j _ { 2 } , j _ { 3 } , j _ { 4 } ) \neq ( 2 , 2 , 2 ) . } \end{array}
$$

For $i = 3$ , we have

$$
{ \frac { 1 } { n ^ { m - 1 } } } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { 3 } b _ { 3 i _ { 2 } i _ { 3 } i _ { 4 } } \right) = { \frac { 1 } { 3 ^ { 4 - 1 } } } \times 5 4 . 5 = { \frac { 5 4 . 5 } { 2 7 } } > 2 ,
$$

$$
\begin{array} { r } { \frac { 1 } { n ^ { m - 1 } } \left( \displaystyle \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } b _ { 3 i _ { 2 } i _ { 3 } i _ { 4 } } \right) > b _ { 3 j _ { 2 } j _ { 3 } j _ { 4 } } \mathrm { ~ f o r ~ a l l ~ } ( j _ { 2 } , j _ { 3 } , j _ { 4 } ) \neq ( 3 , 3 , 3 ) . } \end{array}
$$

Thus, $\boldsymbol { B }$ isa $B$ tensor.

Clearly, for the upper bounds of $\| T _ { B } \| _ { \infty }$ ， we have

$$
n ^ { \frac { m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } b _ { i i i } = 3 ^ { \frac { 4 } { 2 } } \times 6 = 5 4 \mathrm { ~ a n d ~ } \operatorname* { m a x } _ { i \in [ n ] } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } | b _ { i i _ { 2 } i _ { 3 } i _ { 4 } } | \right) = 5 7 ,
$$

and hence, $n ^ { \frac { m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } b _ { i i i i } < \operatorname* { m a x } _ { i \in [ n ] } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } | b _ { i i _ { 2 } i _ { 3 } i _ { 4 } } | \right) .$

It is obvious that for the upper bounds of $\| F _ { B } \| _ { p }$ and $p = 1$ ，

$$
3 ^ { \frac { p - 1 } { p } } \left( \sum _ { i = 1 } ^ { 3 } b _ { i i i i } ^ { \frac { p } { m - 1 } } \right) ^ { \frac { 1 } { p } } < \left( \sum _ { i = 1 } ^ { 3 } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { 3 } b _ { i i _ { 2 } i _ { 3 } i _ { 4 } } \right) ^ { \frac { p } { m - 1 } } \right) ^ { \frac { 1 } { p } } .
$$

Example 4.2. Let $B = ( b _ { i _ { 1 } i _ { 2 } i _ { 3 } i _ { m } } ) \in S _ { 4 , 4 }$ ，where $b _ { 1 1 1 1 } = b _ { 2 2 2 2 } = b _ { 3 3 3 3 } = b _ { 4 4 4 4 } = 3$ ， $b _ { 1 4 4 4 } =$ （204 $b _ { 4 1 4 4 } = b _ { 4 4 1 4 } = b _ { 4 4 4 1 } = 0 . 7$ ， $b _ { 2 3 3 3 } = b _ { 3 2 3 3 } = b _ { 3 3 2 3 } = b _ { 3 3 3 2 } = 0 . 5$ and all other $b _ { i _ { 1 } i _ { 2 } i _ { 3 } i _ { 4 } } = 1$

Proof.It is obvious that $\sum _ { { \mathrm { ' } } { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { 4 } b _ { i i _ { 2 } i _ { 3 } i _ { 4 } } > 0$ for $i = { 1 , 2 , 3 , 4 }$ . 公

For $i = 1$ ，

$$
{ \frac { 1 } { n ^ { m - 1 } } } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } b _ { 1 i _ { 2 } i _ { 3 } i _ { 4 } } \right) = { \frac { 1 } { 4 ^ { 4 - 1 } } } \times 6 5 . 7 = { \frac { 6 5 . 7 } { 6 4 } } > 1 .
$$

$$
\begin{array} { r } { \frac { 1 } { n ^ { m - 1 } } \left( \displaystyle \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } b _ { 1 i _ { 2 } i _ { 3 } i _ { 4 } } \right) > b _ { 1 j _ { 2 } j _ { 3 } j _ { 4 } } \mathrm { ~ f o r ~ a l l ~ } ( j _ { 2 } , j _ { 3 } , j _ { 4 } ) \neq ( 1 , 1 , 1 ) . } \end{array}
$$

For $i = 2$ ，

$$
{ \frac { 1 } { n ^ { m - 1 } } } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } b _ { 2 i _ { 2 } i _ { 3 } i _ { 4 } } \right) = { \frac { 1 } { 4 ^ { 4 - 1 } } } \times 6 5 . 5 = { \frac { 6 5 . 5 } { 6 4 } } > 1 .
$$

So we have ${ \frac { 1 } { n ^ { m - 1 } } } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } b _ { 2 i _ { 2 } i _ { 3 } i _ { 4 } } \right) > b _ { 2 j _ { 2 } j _ { 3 } j _ { 4 } }$ for all $( j _ { 2 } , j _ { 3 } , j _ { 4 } ) \neq ( 2 , 2 , 2 )$

For $i = 3$ ，

$$
{ \frac { 1 } { n ^ { m - 1 } } } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } b _ { 3 i _ { 2 } i _ { 3 } i _ { 4 } } \right) = { \frac { 1 } { 4 ^ { 4 - 1 } } } \times 6 4 . 5 = { \frac { 6 4 . 5 } { 6 4 } } > 1 .
$$

For $i = 4$ （204号

$$
\begin{array} { r } { \frac { 1 } { n ^ { m - 1 } } \left( \displaystyle \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } b _ { 3 i _ { 2 } i _ { 3 } i _ { 4 } } \right) > b _ { 3 j _ { 2 } j _ { 3 } j _ { 4 } } \mathrm { ~ f o r ~ a l l ~ } ( j _ { 2 } , j _ { 3 } , j _ { 4 } ) \neq ( 3 , 3 , 3 ) . } \end{array}
$$

$$
{ \frac { 1 } { n ^ { m - 1 } } } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } b _ { 4 i _ { 2 } i _ { 3 } i _ { 4 } } \right) = { \frac { 1 } { 4 ^ { 4 - 1 } } } \times 6 5 . 1 = { \frac { 6 5 . 1 } { 6 4 } } > 1 .
$$

So we have ${ \frac { 1 } { n ^ { m - 1 } } } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } b _ { 4 i _ { 2 } i _ { 3 } i _ { 4 } } \right) > b _ { 4 j _ { 2 } j _ { 3 } j _ { 4 } }$ for all $( j _ { 2 } , j _ { 3 } , j _ { 4 } ) \neq ( 4 , 4 , 4 )$

Therefore, $\boldsymbol { B }$ isa $B$ tensor. It is obvious that for the upper bounds of $\| T _ { B } \| _ { p }$

$$
n ^ { \frac { m p - 2 } { 2 p } } \left( \sum _ { i = 1 } ^ { n } b _ { i i i i } ^ { p } \right) ^ { \frac { 1 } { p } } = 4 ^ { \frac { 4 p - 2 } { 2 p } } \times ( 3 ^ { p } \times 4 ) ^ { \frac { 1 } { p } } = 4 ^ { \frac { 2 p - 1 } { p } } \times 3 \times 4 ^ { \frac { 1 } { p } } = 4 8
$$

and

$$
\begin{array} { r l } { \displaystyle { n ^ { \frac { m - 2 } { p } } \left( \sum _ { i = 1 } ^ { n } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } \left. b _ { i i _ { 2 } i _ { 3 } i _ { 4 } } \right. \right) ^ { p } \right) ^ { \frac { 1 } { p } } = 4 ^ { \frac { 4 - 2 } { p } } \times ( 6 5 . 7 ^ { p } + 6 5 . 5 ^ { p } + 6 4 . 5 ^ { p } + 6 5 . 1 ^ { p } ) ^ { \frac { 1 } { p } } } } \\ { \displaystyle } & { > 4 ^ { \frac { 4 - 2 } { p } } \times ( 6 4 ^ { p } \times 4 ) ^ { \frac { 1 } { p } } } \\ { \displaystyle } & { = 6 4 \times 4 ^ { \frac { 3 } { p } } . } \end{array}
$$

Since $4 ^ { \frac { 3 } { p } } > 1$ , we have $n ^ { \frac { m p - 2 } { 2 p } } \left( \sum _ { i = 1 } ^ { n } b _ { i i i i } ^ { p } \right) ^ { \frac { 1 } { p } } < n ^ { \frac { m - 2 } { p } } \left( \sum _ { i = 1 } ^ { n } \left( \sum _ { i _ { 2 } , i _ { 3 } , i _ { 4 } = 1 } ^ { n } \left| b _ { i i _ { 2 } i _ { 3 } i _ { 4 } } \right| \right) ^ { p } \right) ^ { \frac { 1 } { p } } .$

Theorem 4.4. Let $\boldsymbol { B }$ bea $B$ tensor. Then

$| \lambda | < \left( \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } ^ { \frac { 1 } { m - 1 } } \right) ^ { m - }$ 1 (i) for all eigenvalues $\lambda$ of $\boldsymbol { B }$ if $m$ is even; (ii) $| \mu | < n ^ { \frac { m } { 2 } } \operatorname* { m i n } \left\{ \operatorname* { m a x } _ { i \in [ n ] } b _ { i i \cdots i } , { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } \right\}$ for all $E$ -eigenvalues μ of $\boldsymbol { B }$

Proof. (i) From the definition of the operator $F _ { B }$ , it follows that $\lambda$ is an eigenvalue of $\boldsymbol { B }$ if and only if $\lambda ^ { \frac { 1 } { m - 1 } }$ is an eigenvalue of $F _ { B }$ . By Theorem 4.2 of Song and Qi [38], we have

$$
| \lambda | ^ { \frac { 1 } { m - 1 } } \leq \| F _ { \mathcal { B } } \| _ { 1 } , \ \mathrm { i . e . , } \ | \lambda | \leq \| F _ { \mathcal { B } } \| _ { 1 } ^ { m - 1 } .
$$

By Theorem 4.2 (ii), we have

$$
\| F _ { \boldsymbol { \mathcal { B } } } \| _ { 1 } < \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } ^ { \frac { 1 } { m - 1 } } .
$$

So we obtain

$$
| \lambda | \leq \| F _ { \mathcal { B } } \| _ { 1 } ^ { m - 1 } < \left( \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } ^ { \frac { 1 } { m - 1 } } \right) ^ { m - 1 } .
$$

(ii) From the definition of the operator $T _ { B }$ , it follows that $\mu$ is an $E$ -eigenvalue of $\boldsymbol { B }$ if and only if $\mu$ is an eigenvalue of $T _ { B }$ . By Theorem 4.2 of Song and Qi [38], we have

$$
| \mu | \leq \| T _ { \mathcal { B } } \| _ { \infty } { \mathrm { ~ a n d ~ } } | \mu | \leq \| T _ { \mathcal { B } } \| _ { 1 } .
$$

By Theorem 4.1, we obtain

$$
\| T _ { \mathcal { B } } \| _ { \infty } < n ^ { \frac { m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } b _ { i i \cdots i } \ \mathrm { a n d } \ \| T _ { \mathcal { B } } \| _ { 1 } < n ^ { \frac { m - 2 } { 2 } } \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } .
$$

Then we have

$$
| \mu | < n ^ { \frac { m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } b _ { i i \cdots i } { \mathrm { ~ a n d ~ } } | \mu | < n ^ { \frac { m - 2 } { 2 } } \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } .
$$

So the desired conclusion follows.

Similarly, we easily show the following.

Theorem 4.5.Let $\boldsymbol { B }$ bea $B _ { 0 }$ tensor. Then

$| \lambda | \leq \left( \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } ^ { \frac { 1 } { m - 1 } } \right) ^ { m }$ -1 (i) for all eigenvalues $\lambda$ of $\boldsymbol { B }$ if m is even; (ii） $| \mu | \leq n ^ { \frac { m } { 2 } } \operatorname* { m i n } \left\{ \operatorname* { m a x } _ { i \in [ n ] } b _ { i i \cdots i } , { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } \right\}$ for all $E$ -eigenvalues $\mu$ of $\boldsymbol { B }$

For the tensor complementarity problem with a $\mathrm { B }$ tensor $\boldsymbol { B }$ ， denoted by $T C P ( B , q )$ ，we may show the bound of solution set of $T C P ( B , q )$

Theorem 4.6.Let $\boldsymbol { B }$ be a $B$ tensor. Assume that $x$ be a non-zero solution of $T C P ( B , q )$ and $y _ { + } = ( \operatorname* { m a x } \{ y _ { 1 } , 0 \} , \operatorname* { m a x } \{ y _ { 2 } , 0 \} , \cdot \cdot \cdot , \operatorname* { m a x } \{ y _ { n } , 0 \} ) ^ { \top }$ . Then

$$
( i ) \ \frac { \| ( - q ) _ { + } \| _ { \infty } } { n ^ { m - 1 } \operatorname* { m a x } _ { i \in [ n ] } b _ { i i \cdots i } } < \| x \| _ { \infty } ^ { m - 1 } ;
$$

$$
( i i ) \ \frac { \| ( - q ) _ { + } \| _ { 2 } } { n ^ { \frac { m - 1 } 2 } \left( \displaystyle \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } ^ { 2 } \right) ^ { \frac 1 2 } } < \| x \| _ { 2 } ^ { m - 1 } ;
$$

Proof. Theorem 3.1 implies that each $B$ tensor is strictly semi-positive. From Theoorem 5 of Song and Qi [23], it follows that

$$
\frac { \| ( - q ) _ { + } \| _ { \infty } } { n ^ { \frac { m - 2 } { 2 } } \| T _ { A } \| _ { \infty } } \leq \| x \| _ { \infty } ^ { m - 1 } \ \mathrm { a n d } \ \frac { \| ( - q ) _ { + } \| _ { 2 } } { \| T _ { A } \| _ { 2 } } \leq \| x \| _ { 2 } ^ { m - 1 } .
$$

By Theorem 4.1, we have

$$
\| T _ { A } \| _ { \infty } < n ^ { \frac { m } { 2 } } \operatorname* { m a x } _ { i \in [ n ] } b _ { i i \cdots i } \mathrm { ~ a n d ~ } \| T _ { A } \| _ { 2 } < n ^ { \frac { m - 1 } { 2 } } \left( \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } ^ { 2 } \right) ^ { \frac { 1 } { 2 } } .
$$

[hen combining the inequalities (4.1) and (4.2),the conclusions (i) and (ii) are proved.

Similarly, we may show (ii). In fact, if $m$ is even, Theoorem 5 of Song and Qi [23] implies

$$
\frac { \| ( - q ) _ { + } \| _ { m } } { \| F _ { \mathcal { A } } \| _ { m } ^ { m - 1 } } \leq \| x \| _ { m } ^ { m - 1 } .
$$

By Theorem 4.2, we have

$$
\| F _ { A } \| _ { m } < n ^ { \frac { m - 1 } { m } } \left( \sum _ { i = 1 } ^ { n } b _ { i i \cdots i } ^ { \frac { m } { m - 1 } } \right) ^ { \frac { 1 } { m } } .
$$

So the desired conclusion follows by combining the inequalities (4.3) and (4.4).

# References

[1] Y. Song and L. Qi, Properties of some classes of structured tensors, J. Optim. Theory, Appl. 165(3)(2015) 854-873.   
[2] Y. Song, L. Qi, Properties of tensor complementarity problem and some classes of structured tensors, arXiv:1412.0113v1(2014), to appear: Annals of Applied Mathematics.   
[3] Z. Huang, L. Qi, Formulating an n-person noncooperative game as a tensor complementarity problem, Comput. Optim. Appl., 66(3)(2017) 557-576.   
[4] Y. Song, G. Yu, Properties of solution set of tensor complementarity problem, J. Optim. Theory, Appl. 170（2016) 85-96.   
[5] Y. Song, L. Qi, Tensor complementarity problem and semi-positive tensors, J. Optim. Theory,Appl. 169 （2016） 1069-1078.   
[6] M. S. Gowda, Z. Luo, L. Qi and N. Xiu, $Z$ tensors and complementarity problems, arXiv:1510.07933v2(2016).   
[7] Z. Luo, L. Qi, X. Xiu, The sparsest solutions to Z-tensor complementarity problems, Optimization Letters,11(3)(2017) 471-482.   
[8] W. Ding, Z. Luo, L. Qi, $P$ -Tensors, $P _ { 0 }$ -Tensors, and tensor complementarity problem, arXiv:1507.06731v1(2015).   
[9] Y. Wang, Z. Huang, and X. Bai, Exceptionaly regular tensors and tensor complementarity problems, Optimization Methods and Software. 31 (2016) 815-828.   
[10] X. Bai, Z. Huang, and Y. Wang, Global uniqueness and soluability for tensor complementarity problems, J. Optim. Theory, Appl. 170 (2016) 72-84.   
[11] M. Che, L. Qi, Y. Wei, Positive definite tensors to nonlinear complementarity problems, J Optim Theory Appl. 168(2016), 475-487.   
[12] Z. Huang, S. Suo, J. Wang, On Q-tensors, to appear in: Pacific Journal of Optimization, arXiv:1509.03088 （2015)   
[13] Y. Song, L. Qi， Eigenvalue analysis of constrained minimization problem for homogeneous polynomial, J. Global Optim. 64(3)(2016), 563-575.   
[14] C.Ling, H. He,L. Qi, On the cone eigenvalue complementarity problem for higher-order tensors, Compu. Optim. Appl. 63(2016),143-168.   
[15] C.Ling, H. He, L. Qi， Higher-degree eigenvalue complementarity problems for tensors, Compu. Optim. Appl. 64(1)(2016), 149-176.   
[16] Z. Chen, Q. Yang, L. Ye, Generalized eigenvalue complementarity problem for tensors, to appear in: Pacific Journal of Optimization arXiv:1505.02494 (2015)   
[17] T. Chen, W. Li, X. Wu, and S. Vong, Error bounds for linear complementarity problems of MB-matrices, Numer. Algor. 70(2) (2015) 341-356.   
[18] P. F. Dai, Error bounds for linear complementarity problems of DB-matrices, Linear Algebra Appl. 434 (2011) 830-840.   
[19] P. Dai, Y. Li, and C. Lu, Error bounds for linear complementarity problems of SBmatrices, Numer. Algor. 61(1) (2012) 121-139.   
[20] P.Dai, C. Lu and Y. Li， New error bounds for linear complementarity problems with an SB-matrices, Numer. Algor. 64(4) (2013) 741-757.   
[21] M. Garcia-Esnaola, J. M. Pena, Error bounds for linear complementarity problems for B-matrices, Appl. Math. Lett. 22(7)(2009) 1071-1075.   
[22] H. Sun ， Y. Wang, Further Discussion on the Error Bound for Generalized Linear Complementarity Problem over a Polyhedral Cone, J. Optim. Theory, Appl. 159(1)(2013) 93-107.   
[23] Y. Song, L. Qi， Strictly semi-positive tensors and the boundedness of tensor complementarity problems, Optimization Letters DOI: 10.1007/s11590-016-1104-7.   
[24] L. Qi, Z. Luo, Tensor Analysis: Spectral Theory and Special Tensors, Society for Industrial & Applied Mathematics, U.S.A, 2017.   
[25] L. Zhang, L. Qi, and G. Zhou, M-tensors and some applications, SIAM. J. Matrix Anal. & Appl., 34(2)(2014) 437-452.   
[26] W. Ding, L. Qi, and Y. Wei, M-tensors and nonsingular M-tensors, Linear Algebra Appl. 439(2013) 3264-3278.   
[27] C. Li, Y. Li, Double B-tensors and quasi-double $B$ -tensors, Linear Algebra Appl. 466 (2015) 343-356.   
[28] Y. Song, L. Qi, Infinite and finite dimensional Hilbert tensors, Linear Algebra Appl. 451 (2014) 1-14.   
[29] Y. Song, L. Qi, Infinite dimensional Hilbert tensors on spaces of analytic functions, to appear: Communications in Mathematical Sciences, arXiv: 1611.02357 ChinaXiv: 201611.00715   
[30] W. Mei, Y. Song， Infinite and finite dimensional generalized Hilbert tensors, Linear Algebra Appl. 532(1)(2017) 8-24.   
[31] J. M .Pena, A class of $P$ -matrices with applications to the localization of the eigenvalues of a real matrix, SIAM. J. Matrix Anal. & Appl., 22 (2001) 1027-1037.   
[32] J.M . Pena, On an alternative to Gerschgorin circles and ovals of cassini, Numerische Mathematik. 95(2003) 337-345.   
[33] P. Yuan, L. You, Some remarks on $P , P _ { 0 } , B$ and $B _ { 0 }$ tensors, Linear Algebra Appl. 459(3)(2014) 511-521.   
[34] L. Qi, Y. Song, An even order symmetric B tensor is positive definite, Linear Algebra Appl. 457 (2014) 303-312.   
[35] L. Qi, Eigenvalues of a real supersymmetric tensor, J. Symbolic Comput. 40(2005), 1302-1324.   
[36] L. Qi, Rank and eigenvalues of a supersymmetric tensor, the multivariate homogeneous polynomial and the algebraic hypersurface it defines, J. Symbolic Comput. 41(2006), 1309-1327.   
[37] L.H. Lim, Singular values and eigenvalues of tensors: A variational approach, in: Proc. 1st IEEE International workshop on computational advances of multi-tensor adaptive processing,Dec. 13-15,129-132 (2005)   
[38] Y. Song,L. Qi, Spectral properties of positively homogeneous operators induced by higher order tensors, SIAM J. Matrix Anal. Appl. 34(2013), 1581-1595.