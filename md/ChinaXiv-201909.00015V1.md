# Analytical expressions of copositivity for 4th order symmetric tensors and applications

Yisheng Song\* Liqun Qit August 30, 2019

Abstract. In particle physics, scalar potentials have to be bounded from below in order for the physics to make sense. The precise expressions of checking lower bound of scalar potentials are essential, which is an analytical expression of checking copositivity and positive definiteness of tensors given by such scalar potentials. Because the tensors given by general scalar potential are 4th order and symmetric, our work mainly focuses on finding precise expressions to test copositivity and positive definiteness of 4th order tensors in this paper. First of all,an analytically sufficient and necessary condition of positive definiteness is provided for 4th order 2 dimensional symmetric tensors. For 4th order 3 dimensional symmetric tensors, we give two analytically sufficient conditions of (strictly) cpositivity by using proof technique of reducing orders or dimensions of such a tensor. Furthermore,an analytically sufficient and necessary condition of copositivity is showed for 4th order 2 dimensional symmetric tensors. We also give several distinctly analytically sufficient conditions of (strict） copositivity for 4th order 2 dimensional symmetric tensors. Finally, we apply these results to check lower bound of scalar po tentials, and to present analytical vacuum stability conditions for potentials of two real scalar fields and the Higgs boson.

Key Words and Phrases: Copositive Tensors， Positive definiteness, Homogeneous polynomial, Analytical expression.

2010 AMS Subject Classification: 15A18， 15A69， 90C20,   
90C30

# 1 Introduction

Recently, Kannike [25,26] studied the vacuum stability of general scalar potentials of a few fields. The most general scalar potential of $n$ real singlet scalar fields $\phi _ { i }$ 0 $\langle i = 1 , 2 , \cdots , n \rangle$ can be expressed as

$$
V ( \phi ) = \sum _ { i , j , k , l = 1 } ^ { n } \lambda _ { i j k l } \phi _ { i } \phi _ { j } \phi _ { k } \phi _ { l } = \Lambda \phi ^ { 4 } ,
$$

where $\boldsymbol { \Lambda } \ = \ \left( \lambda _ { i j k l } \right)$ is the symmetric tensor of scalar couplings and $\phi \ =$ $( \phi _ { 1 } , \phi _ { 2 } , \cdots , \phi _ { n } ) ^ { \top }$ is the vector of fields. So，the vacuum stability of such a system is equivalent to the positivity of the polynomial (1.1) [25], i.e., the positive definiteness of the tensor $\boldsymbol { \Lambda } = \left( \lambda _ { i j k l } \right)$ . However, it is NP-hard to determine the non-negativity of a given polynomial if the degree of such a polynomial is larger than or equal to 4 [18,31]. A significant special case [27], the quartic potentials of quadratic scalar fields $\phi _ { i } ^ { 2 }$ （ $i = 1 , 2 , \cdots , n ,$ ispresented by

$$
V ( \phi ) = \sum _ { i , j = 1 } ^ { n } \lambda _ { i j } \phi _ { i } ^ { 2 } \phi _ { j } ^ { 2 } = ( \phi _ { 1 } ^ { 2 } , \phi _ { 2 } ^ { 2 } , \cdots , \phi _ { n } ^ { 2 } ) ^ { \top } A ( \phi _ { 1 } ^ { 2 } , \phi _ { 2 } ^ { 2 } , \cdots , \phi _ { n } ^ { 2 } ) ,
$$

where $A = ( \lambda _ { i j } )$ is a symmetric matrix. Then the positivity of the polynomial (1.2) become the strict copositivity of matrix $A$ . In 2012, Kannike [27] first obtained the vacuum stability conditions of such a special case by means of testing copositivity of matrix. The vacuum stability conditions of the general potential of two real scalars (without or with the Higgs boson included in the potential) were obtained in [25,26] with the help of the copositivity of matrix and the positivity of the polynomial.

The concept of copositive matrix was introduced by Motzkin [33] in 1952. A real symmetric matrix $A$ is said to be (i) copositive if $x ^ { T } A x \geq 0$ for all vector $x \geq 0$ in the non-negative orthant $\mathbb { R } _ { + } ^ { n }$ ( $x \geq 0$ implies that $x _ { i } \geq 0$ for each $i = 1 , 2 , \cdots , n )$ ; (ii) strictly copositive if $x ^ { T } A x > 0$ for all nonzero vector $x \geq 0$ . Hadeler [20] and Nadler [34] showed the copositive conditions of an $2 \times 2$ matrix $A$ (also see Andersson-Chang-Elfving [1]). A real symmetric $2 \times 2$ matrix $A = \left( a _ { i j } \right)$ is(strictly） copositive if and only if

$$
a _ { 1 1 } \geq 0 ( > 0 ) , a _ { 2 2 } \geq 0 ( > 0 ) , a _ { 1 2 } + \sqrt { a _ { 1 1 } a _ { 2 2 } } \geq 0 ( > 0 ) .
$$

The copositive conditions of an $3 \times 3$ matrix $A$ were obtained by Hadeler [20] and Chang-Sederberg [8]. A real symmetric $3 \times 3$ matrix $A = \left( a _ { i j } \right)$ is copositive if and only if

$$
\begin{array} { r l r } & { } & { a _ { 1 1 } \geq 0 , a _ { 2 2 } \geq 0 , a _ { 3 3 } \geq 0 , } \\ & { } & { \alpha = a _ { 1 2 } + \sqrt { a _ { 1 1 } a _ { 2 2 } } \geq 0 , \beta = a _ { 1 3 } + \sqrt { a _ { 1 1 } a _ { 3 3 } } \geq 0 , \gamma = a _ { 2 3 } + \sqrt { a _ { 3 3 } a _ { 2 2 } } \geq 0 , } \\ & { } & { a _ { 1 2 } \sqrt { a _ { 3 3 } } + a _ { 1 3 } \sqrt { a _ { 2 2 } } + a _ { 2 3 } \sqrt { a _ { 1 1 } } + \sqrt { a _ { 1 1 } a _ { 2 2 } a _ { 3 3 } } + \sqrt { 2 \alpha \beta \gamma } \geq 0 . } \end{array}
$$

Ping-Yu [36] gave the criteria of $4 \times 4$ copositive matrices, which expression is not simpler than the above. At the same time, they proved an equivalent condition of $n \times n$ copositive matrices. Cottle-Habetler-Lemke [7] presented analytical conditions of copositive matrix by means of the determinant and the adjugate of such a matrix. Väliaho [50] discussed the criteria of (strictly) copositive matrices with the help of some behaviors of its principal submatrices. Kaplan [24] proved a way to test copositivity of a matrix by using eigenvalues and eigenvectors of its principal submatrices. HaynsworthHoffman [21] showed the Perron properties of a class of copositive matrices. Johnson-Reams [22] dicussed spectral theory of copositive matrices. For more copositive properties and their applications such as copositive programs, see [2-4,32] and the relevant literature on this topic.

Recently, Kannike [25,26] gave another physical example defined by scalar dark matter stable under a $\mathbb { Z } _ { 3 }$ discrete group. The most general scalar quartic potential of the SM Higgs $\mathbf { H } _ { 1 }$ ，an inert doublet $\mathbf { H } _ { 2 }$ and a complex singlet $\mathbf { S }$

is

$$
V ( h _ { 1 } , h _ { 2 } , s ) = V ( \phi ) = \mathcal V \phi ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 3 } v _ { i j k l } \phi _ { i } \phi _ { j } \phi _ { k } \phi _ { l } ,
$$

where $\phi ~ = ~ ( \phi _ { 1 } , \phi _ { 2 } , \phi _ { 3 } ) ^ { \top } ~ = ~ ( h _ { 1 } , h _ { 2 } , s ) ^ { \top }$ ， $h _ { 1 } ~ = ~ | H _ { 1 } |$ ， $h _ { 2 } \ = \ | H _ { 2 } | , H _ { 2 } ^ { \dagger } H _ { 1 } \ =$ $h _ { 1 } h _ { 2 } \rho e ^ { i \phi } , S = s e ^ { i \phi _ { S } }$ ， $\mathcal { V } = \left( v _ { i j k l } \right)$ is an 4th order 3 dimensional real symmetric tensor with its entries: $v _ { 1 1 1 1 } = \lambda _ { 1 } , ~ v _ { 2 2 2 2 } = \lambda _ { 2 } , ~ v _ { 3 3 3 3 } = \lambda _ { S } , v _ { 1 1 2 2 } = \textstyle { \frac { 1 } { 6 } } ( \lambda _ { 3 } +$ $\lambda _ { 4 } \rho ^ { 2 } )$ ，1 $\begin{array} { r } { v _ { 1 1 3 3 } = \frac { 1 } { 6 } \lambda _ { S 1 } } \end{array}$ ， $\begin{array} { r } { v _ { 2 2 3 3 } = \frac { 1 } { 6 } \lambda _ { S 2 } , v _ { 1 2 3 3 } = - \frac { 1 } { 1 2 } | \lambda _ { S 1 2 } | \rho } \end{array}$ ： $v _ { i j k l } = 0$ for the others. Clearly, $h _ { 1 } \geq 0 , h _ { 2 } \geq 0 , s \geq 0$ . So, the vacuum stability of for $\mathbb { Z } _ { 3 }$ scalar dark matter $V ( h _ { 1 } , h _ { 2 } , s )$ is really equivalent to the (strict) copositivity of the tensor （204号 $\mathcal { V } = \left( v _ { i j k l } \right)$ ([25,26]).

An $m$ th order $n$ dimensional real symmetric tensor $\mathcal { A }$ is said to be

(i) copositive if ${ \mathcal A } x ^ { m } = x ^ { T } ( { \mathcal A } x ^ { m - 1 } ) = \sum _ { i _ { 1 } , i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } a _ { i _ { 1 } i _ { 2 } \cdots i _ { m } } x _ { i _ { 1 } } x _ { i _ { 2 } } \cdots x _ { i _ { m } } \ge 0$ for all $x \in \mathbb { R } _ { + } ^ { n }$ ，   
(ii) strictly copositive if $A x ^ { m } > 0$ for all $x \in \mathbb { R } _ { + } ^ { n } \setminus \{ 0 \}$   
(iii) semipositive definite if $\mathcal { A } x ^ { m } \geq 0$ for all $x \in \mathbb { R } ^ { n }$ and even number $m$ ，   
(iv) positive definite if $\mathcal { A } x ^ { m } > 0$ for all $x \in \mathbb { R } ^ { n } \setminus \{ 0 \}$ and even number $m$ ：

These concepts were first introduced by Qi [37,38] for higher order symmetric tensors. Qi [37] showed a even order symmetric tensor is positive defnitive if and only if its all H-(Z-)eigenvalues are positive. Qi [38] proved a symmetric tensor is strictly copositive if its each sum of the main diagonal element and negative elements in the same row is positive. Song-Qi [41] extended Kaplan's test way of copositive matrix 24| to copositive tensors, and presented some structured properties of such a class of tensors. Recently, checking copositivity of tensors has attracted the attention of mathematical workers. For example, Chen-Huang-Qi [11] studied some basic theory of copositivity detection of symmetric tensors and gave corresponding numerical algorithms of testing copositivity based on the standard simplex and simplicial partitions; Chen-Huang-Qi [12] revised algorithm with a proper convex subcone of the copositive tensor cone; Nie-Yang-Zhang [35] proposed a complete semidefinite relaxation algorithm for detecting the copositivity of a symmetric tensor and showed such a detection can be done by solving a finite number of semidefinite relaxations for all tensors; Li-Zhang-Huang-Qi [28] presented an SDP relaxation algorithm to test the copositivity of higher order tensors. For more structured properties and numerical algorithms of copositive tensors, see [13,39,40].

On the other hand, some structured tensors are closely tied to strictly copositive tensors. Song-Qi [45] analyzed qualitatively the relationship between the constrained minimization problem on the unit sphere and (strict） copositvity of corresponding tensors. Song-Qi [44] proved that a symmetric tensor is (strictly） copositive if and only if it is (strictly） semipositive. A tensor is called (strictly） semipositive if for each nonzero vector $x = ( x _ { 1 } , x _ { 2 } , \cdot \cdot \cdot , x _ { n } ) ^ { \top } \geq 0$ , there exists an index $k \in \{ 1 , 2 , \cdots , n \}$ such that

$$
x _ { k } > 0 { \mathrm { ~ a n d ~ } } \left( { \mathcal { A } } x ^ { m - 1 } \right) _ { k } = \sum _ { i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } a _ { k i _ { 2 } \cdots i _ { m } } x _ { i _ { 2 } } \cdots x _ { i _ { m } } \geq 0 ( > 0 ) .
$$

This notion is firstly used by Song-Qi [42]. In particular, this class of tensors assure the solvability of the corresponding tensor complementarity problems (for short，TCP). So，we may probe into checking copositivity of tensors and its applications by means of studying this class of semipositive tensors. For its more properties and applications in TCP, see [5,6,9,10,14,15,17,19,30,46-48,51-53] and references cited therein.

Until now, there is no an analytical expression of checking copositivity and positive definitieness of tensors like ones of $2 \times 2$ and $3 \times 3$ matrices. However, the practical matters such as the vacuum stability of general scalar potentials of a few fields require precise expressions.

Motivated by these works above, we study the analytical expressions of certifying a symmetric tensor to be copositive and positive definitive in this paper. At the same time, we confine our work to 4th order tensor in this paper since the tensor given by general scalar potential is 4th order. More precisely, we provide respectively analytical expressions of testing copositivity and positive definiteness for 4th order 3 (or 2) dimensional symmetric tensors. In particular, we will employ argumentation technique of reducing orders or dimensions of such a tensor to establish the desired conclusions,which may be a very important method of analysing higher order tensors in future. Furthermore, these results can be applied to check the vacuum stability of general scalar potentials of two real singlet scalar fields and vacuum stability for $\mathbb { Z } _ { 3 }$ scalar dark matter.

# 2 Preliminaries and Basic facts

An 4th order 3 dimensional real tensor $\mathcal { A }$ consists of 81 entries in the real field $\mathbb { R }$ ,i.e.,

$$
\begin{array} { r } { \mathcal { A } = ( a _ { i j k l } ) , \qquad a _ { i j k l } \in \mathbb { R } , ~ i , j , k , l = 1 , 2 , 3 . } \end{array}
$$

Let the transposition of a vector $x$ be denoted by $x ^ { \mid }$ .For $x = ( x _ { 1 } , x _ { 2 } , x _ { 3 } ) ^ { \top } \in$ （20 $\mathbb { R } ^ { 3 }$ ， $\boldsymbol { A x ^ { 3 } }$ is a vector in $\mathbb { R } ^ { 3 }$ ，

$$
\mathcal { A } \boldsymbol { x } ^ { 3 } = \left( \sum _ { j , k , l = 1 } ^ { 3 } a _ { 1 j k l } x _ { j } x _ { k } x _ { l } , \sum _ { j , k , l = 1 } ^ { 3 } a _ { 2 j k l } x _ { j } x _ { k } x _ { l } , \sum _ { j , k , l = 1 } ^ { 3 } a _ { 3 j k l } x _ { j } x _ { k } x _ { l } \right) ^ { \top } .
$$

Then $x ^ { \top } ( \mathcal { A } x ^ { 3 } )$ is a homogeneous polynomial, denoted as $\boldsymbol { \mathcal { A } } \boldsymbol { x } ^ { 4 }$ ,i.e.,

$$
\mathcal { A } x ^ { 4 } = x ^ { \top } ( \mathcal { A } x ^ { 3 } ) = \sum _ { i , j , k , l = 1 } ^ { 3 } a _ { i j k l } x _ { i } x _ { j } x _ { k } x _ { l } .
$$

Similarly,an 4th order 2 dimensional real tensor $\mathcal { A }$ consists of 16 entries in the real field $\mathbb { R }$ and for $x = ( x _ { 1 } , x _ { 2 } ) ^ { \top } \in \mathbb { R } ^ { 2 }$ 5

$$
\mathcal { A } x ^ { 4 } = x ^ { \top } ( \mathcal { A } x ^ { 3 } ) = \sum _ { i , j , k , l = 1 } ^ { 2 } a _ { i j k l } x _ { i } x _ { j } x _ { k } x _ { l } .
$$

A tensor $A$ is said to be symmetric if its entries $a _ { i j k l }$ are invariant for any permutation of its indices. Obviously, each 4th order 2 dimensional symmetric tensor $\mathcal { A }$ determines a homogeneous polynomial $\boldsymbol { \mathcal { A } } \boldsymbol { x } ^ { 4 }$ of degree 4 with 2 variables and vice versa.

Let $\| \cdot \|$ denote any norm on $\mathbb { R } ^ { n }$ . Then the equivalent definition of (strict) copositivity and semipositive (positive) definiteness of a symmetric tensor in the sense of any norm on $\mathbb { R } ^ { n }$ [37,39-41].

Lemma 2.1.( $[ { \mathcal { 3 } } \gamma , \langle \partial _ { { \boldsymbol { \cdot } } } 1 / )$ Let $\mathcal { A }$ be a symmetric tensor of order 4. Then

(i） $A$ is copositive if and only if $A x ^ { 4 } \geq 0$ for all $x \in \mathbb { R } _ { + } ^ { n }$ with $\| x \| = 1$ ：，   
(ii) $\mathcal { A }$ is strictly copositive if and only if $\mathcal { A } \mathcal { x } ^ { 4 } > 0$ for all $x \in \mathbb { R } _ { + } ^ { n }$ with $\| x \| = 1$ ：，   
(iii) $\mathcal { A }$ is semipositive definite if and only if $\mathcal { A } \mathcal { x } ^ { 4 } \geq 0$ for all $x \in \mathbb { R } ^ { n }$ with $\| x \| = 1$ ：，

(iu) $A$ is positive definite if and only if $\mathcal { A } \mathcal { x } ^ { 4 } > 0$ for all $x \in \mathbb { R } ^ { n }$ with $\| x \| = 1$

A quadratic Bernstein-Bezier polynomial $p ( t )$ on the interval $[ 0 , 1 ]$ is given by

$$
p ( t ) = a t ^ { 2 } + 2 b ( 1 - t ) t + c ( 1 - t ) ^ { 2 } , t \in [ 0 , 1 ] ,
$$

Nadler [34] and Andersson-Chang-Elfving [1] showed the following famous conclusion, independently.

Lemma 2.2. ( [34, Lemma 1], [1， Lemma 2.1]) Let a quadratic BernsteinBezier polynomial $p ( t )$ be defned by (2.4). Then $p ( t ) \geq 0$ $( > ~ 0 )$ for all （20 $t \in [ 0 , 1 ]$ if and only if the inequalities

$$
a \geq 0 ( > 0 ) , \ c \geq 0 ( > 0 ) , \ b + \sqrt { a c } \geq 0 ( > 0 )
$$

hold simultaneously

For a quartic and univariate polynomial $f ( t )$ with real coefficients,

$$
f ( t ) = a _ { 0 } t ^ { 4 } + 4 a _ { 1 } t ^ { 3 } + 6 a _ { 2 } t ^ { 2 } + 4 a _ { 3 } t + a _ { 4 } ,
$$

Gadenz-Li [16], Ku [23], Jury-Mansor [29] obtained independently its positive conditions.

Lemma 2.3. （ [16,23,29]) Let $f ( t )$ be a quartic and univariate polynomial defined by (2.6) with $a _ { 0 } > 0$ and $a _ { 4 } > 0$ . Define

$$
\begin{array} { l } { F = 9 a _ { 0 } ^ { 2 } a _ { 2 } ^ { 2 } - 2 4 a _ { 0 } a _ { 1 } ^ { 2 } a _ { 2 } + 1 2 a _ { 1 } ^ { 4 } - a _ { 0 } ^ { 3 } a _ { 4 } + 4 a _ { 0 } ^ { 2 } a _ { 1 } a _ { 3 } , } \\ { G = a _ { 0 } ^ { 2 } a _ { 3 } - 3 a _ { 0 } a _ { 1 } a _ { 2 } + 2 a _ { 1 } ^ { 3 } , } \\ { H = a _ { 0 } a _ { 2 } - a _ { 1 } ^ { 2 } , } \\ { I = a _ { 0 } a _ { 4 } - 4 a _ { 1 } a _ { 3 } + 3 a _ { 2 } ^ { 2 } , } \\ { J = a _ { 0 } a _ { 2 } a _ { 4 } + 2 a _ { 1 } a _ { 2 } a _ { 3 } - a _ { 2 } ^ { 3 } - a _ { 0 } a _ { 3 } ^ { 2 } - a _ { 1 } ^ { 2 } a _ { 4 } , } \\ { \Delta = I ^ { 3 } - 2 7 J ^ { 2 } . } \end{array}
$$

Then $f ( t ) > 0$ for all $0 < | t | < \infty$ if and only if

$$
\begin{array} { l l } { \Delta > 0 , } & { H \geq 0 ; } \\ { \Delta > 0 , } & { H < 0 , F < 0 ; } \\ { \Delta = 0 , } & { H > 0 , \quad F = 0 , G = 0 . } \end{array}
$$

For a quartic and univariate polynomial $g ( t )$ with real coefficients,

$$
g ( t ) = a t ^ { 4 } + b t ^ { 3 } + c t ^ { 2 } + d t + e ,
$$

Ulrich-Watson [49] proved its nonnegative conditions for $t > 0$

Lemma 2.4.（ [49，Theorem ${ \mathcal { Z } } ] _ { \cdot }$ ）Let $g ( t )$ be a quartic and univariate poly nomial defined by (2.7) with $a > 0$ and $e > 0$ . Define

$$
\begin{array} { l } { \alpha = b a ^ { - \frac { 3 } { 4 } } e ^ { - \frac { 1 } { 4 } } , \ \beta = c a ^ { - \frac { 1 } { 2 } } e ^ { - \frac { 1 } { 2 } } , \ \gamma = d a ^ { - \frac { 1 } { 4 } } e ^ { - \frac { 3 } { 4 } } , } \\ { \Delta = 4 ( \beta ^ { 2 } - 3 \alpha \gamma + 1 2 ) ^ { 3 } - ( 7 2 \beta + 9 \alpha \beta \gamma - 2 \beta ^ { 3 } - 2 7 \alpha ^ { 2 } - 2 7 \gamma ^ { 2 } ) ^ { 2 } , } \\ { \mu = ( \alpha - \gamma ) ^ { 2 } - 1 6 ( \alpha + \beta + \gamma + 2 ) , } \\ { \eta = ( \alpha - \gamma ) ^ { 2 } - \frac { 4 ( \beta + 2 ) } { \sqrt { \beta - 2 } } ( \alpha + \gamma + 4 \sqrt { \beta - 2 } ) . } \end{array}
$$

Then (i) $g ( t ) \geq 0$ for all $t > 0$ if and only if

$$
- 2 \leq \beta \leq 6 a n d \left\{ \begin{array} { l l } { { \Delta \leq 0 } } & { { \quad a n d \alpha + \gamma > 0 } } \\ { { } } & { { o r } } \\ { { \Delta \geq 0 } } & { { \quad a n d \mu \leq 0 } } \end{array} \right.
$$

$$
\beta > 6 a n d \left\{ \begin{array} { l l } { \Delta \leq 0 } & { \ a n d \ a + \gamma > 0 } \\ { \qquad } & { \ o r } \\ { \alpha > 0 } & { \ a n d \ \gamma > 0 } \\ { \qquad } & { \ o r } \\ { \Delta \geq 0 } & { \ a n d \ \eta \leq 0 . } \end{array} \right.
$$

(ii) $g ( t ) \geq 0$ for all $t > 0$ if

$$
\begin{array} { r l } & { \alpha > - \frac { \beta + 2 } { 2 } \ a n d \gamma > - \frac { \beta + 2 } { 2 } \ f o r \ \beta \le 6 ; } \\ & { } \\ & { \alpha > - 2 \sqrt { \beta - 2 } \ a n d \gamma > - 2 \sqrt { \beta - 2 } \ f o r \ \beta > 6 . } \end{array}
$$

A quadratic and multivariate polynomial $F ( 1 - t , t v , t w )$ is difined by

$$
\begin{array} { r l } & { F ( 1 - t , t v , t w ) = A ( 1 - t ) ^ { 2 } + 2 ( b w + c v ) t ( 1 - t ) } \\ & { \qquad + ( B v ^ { 2 } + 2 a w v + C w ^ { 2 } ) t ^ { 2 } , \ t , v \in [ 0 , 1 ] , } \end{array}
$$

where $w = 1 - v$ . Chang-Sederberg [8] provided the following famous conclusion. Also see Nadler [34].

Lemma 2.5.（[8, Theorem $1 \jmath _ { \cdot }$ ) Let a quadratic form $F ( 1 - t , t v , t w )$ be defined by (2.8). Then $F ( 1 - t , t v , t w ) \geq 0 \ ( > \ 0 )$ for all $t \in [ 0 , 1 ]$ and all $v \in [ 0 , 1 ]$ and $w = 1 - v$ if and only if the inequalities

$$
\begin{array} { r l } & { A \geq 0 ( > 0 ) , \ B \geq 0 ( > 0 ) , \ C \geq 0 ( > 0 ) , } \\ & { a + \sqrt { B C } \geq 0 ( > 0 ) , \ b + \sqrt { A C } \geq 0 ( > 0 ) , \ c + \sqrt { A B } \geq 0 ( > 0 ) , } \\ & { \sqrt { A B C } + a \sqrt { A } + b \sqrt { B } + c \sqrt { C } } \\ & { \quad + \sqrt { 2 ( a + \sqrt { B C } ) ( b + \sqrt { A C } ) ( c + \sqrt { A B } ) } \geq 0 ( > 0 ) . } \end{array}
$$

hold simultaneously

# 3 Copositivity of 4th order symmetric tensors

Let $\mathcal { A }$ be an 4th order 2 dimensional symmetric tensor. Then for a vector （202 $\boldsymbol { x } = ( x _ { 1 } , x _ { 2 } ) ^ { \top }$ ，

$$
\begin{array} { l } { \displaystyle { \mathcal { A } x ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 2 } a _ { i j k l } x _ { i } x _ { j } x _ { k } x _ { l } } } \\ { \displaystyle { \quad = a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 4 a _ { 1 2 1 1 } x _ { 1 } ^ { 3 } x _ { 2 } + 6 a _ { 1 2 2 1 } x _ { 1 } ^ { 2 } x _ { 2 } ^ { 2 } + 4 a _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 3 } + a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } . } } \end{array}
$$

Take $y = ( 1 , 0 ) ^ { \top }$ and $z = ( 0 , 1 ) ^ { \top }$ . Then $\mathcal { A } y ^ { 4 } = a _ { 1 1 1 1 }$ and $\mathcal { A } z ^ { 4 } = a _ { 2 2 2 2 }$ .So, it is obvious that $a _ { 1 1 1 1 } > 0$ and $a _ { 2 2 2 2 } > 0$ are necessary condition of positive definiteness of $\mathcal { A }$

Theorem 3.1. Let $\mathcal { A }$ be a symmetric tensor of order 4 and dimension 2 with （204号 $a _ { 1 1 1 1 } > 0$ and $a _ { 2 2 2 2 } > 0$ . Then $\mathcal { A }$ is positive definite if and only if

1 $\begin{array} { r l } & { \quad a _ { 1 1 1 1 } a _ { 1 2 2 1 } \geq a _ { 1 2 1 1 } ^ { 2 } , } \\ & { \quad ( a _ { 1 1 1 1 } a _ { 2 2 2 2 } - 4 a _ { 1 2 1 1 } a _ { 1 2 2 2 } + 3 a _ { 1 2 2 1 } ^ { 2 } ) ^ { 3 } > 2 7 ( a _ { 1 1 1 1 } a _ { 1 2 2 1 } a _ { 2 2 2 2 } + 2 a _ { 1 2 1 1 } a _ { 1 2 2 1 } a _ { 1 2 2 2 } - 6 a _ { 1 2 1 1 } a _ { 1 1 1 1 } a _ { 1 2 2 2 } - 6 a _ { 1 2 1 1 } a _ { 1 1 1 1 } ) } \\ & { \quad a _ { 1 2 2 1 } ^ { 3 } - a _ { 1 1 1 1 } a _ { 1 2 2 2 } ^ { 2 } - a _ { 1 2 1 1 } ^ { 2 } a _ { 2 2 2 2 } ) ^ { 2 } ; } \end{array}$ （20 $\begin{array} { r l } & { \quad a _ { 1 1 1 1 } a _ { 1 2 2 1 } < a _ { 1 2 1 1 } ^ { 2 } , } \\ & { \big ( a _ { 1 1 1 1 } a _ { 2 2 2 2 } - 4 a _ { 1 2 1 1 } a _ { 1 2 2 2 } + 3 a _ { 1 2 2 1 } ^ { 2 } \big ) ^ { 3 } > 2 7 \big ( a _ { 1 1 1 1 } a _ { 1 2 2 1 } a _ { 2 2 2 2 } + 2 a _ { 1 2 1 1 } a _ { 1 2 2 1 } a _ { 1 2 2 2 } - } \\ & { a _ { 1 2 2 1 } ^ { 3 } - a _ { 1 1 1 1 } a _ { 1 2 2 2 } ^ { 2 } - a _ { 1 2 1 1 } ^ { 2 } a _ { 2 2 2 2 } \big ) ^ { 2 } , } \\ & { 9 a _ { 1 1 1 1 } ^ { 2 } a _ { 1 2 2 1 } ^ { 2 } + 1 2 a _ { 1 2 1 1 } ^ { 4 } + 4 a _ { 1 1 1 1 } ^ { 2 } a _ { 1 2 1 1 } a _ { 1 2 2 2 } < a _ { 1 1 1 1 } ^ { 3 } a _ { 2 2 2 2 } + 2 4 a _ { 1 1 1 1 } a _ { 1 2 1 1 } ^ { 2 } a _ { 1 2 2 1 } ; } \end{array}$ （204号

$$
\begin{array} { r l } & { a _ { 1 1 1 1 } a _ { 1 2 2 1 } > a _ { 1 2 1 1 } ^ { 2 } , } \\ & { \big ( a _ { 1 1 1 1 } a _ { 2 2 2 2 } - 4 a _ { 1 2 1 1 } a _ { 1 2 2 2 } + 3 a _ { 1 2 2 2 } ^ { 2 } \big ) ^ { 3 } = 2 7 \big ( a _ { 1 1 1 1 } a _ { 1 2 2 1 } a _ { 2 2 2 2 } + 2 a _ { 1 2 1 1 } a _ { 1 2 2 1 } a _ { 1 2 2 2 } - } \\ & { a _ { 1 2 2 1 } ^ { 3 } - a _ { 1 1 1 1 } a _ { 1 2 2 2 } ^ { 2 } - a _ { 1 2 1 1 } ^ { 2 } a _ { 2 2 2 2 } \big ) ^ { 2 } , } \\ & { 9 a _ { 1 1 1 1 } ^ { 2 } a _ { 1 2 2 1 } ^ { 2 } + 1 2 a _ { 1 2 1 1 } ^ { 4 } + 4 a _ { 1 1 1 1 } ^ { 2 } a _ { 1 2 1 1 } a _ { 1 2 2 2 } = a _ { 1 1 1 1 } ^ { 3 } a _ { 2 2 2 2 } + 2 4 a _ { 1 1 1 1 } a _ { 1 2 1 1 } ^ { 2 } a _ { 1 2 2 1 } , } \\ & { a _ { 1 1 1 1 } ^ { 2 } a _ { 1 2 2 2 } + 2 a _ { 1 2 1 1 } ^ { 3 } = 3 a _ { 1 1 1 1 } a _ { 1 2 1 1 } a _ { 1 2 2 1 } . } \end{array}
$$

Proof. It follows from Lemma 2.1 that we can restrict $x$ to

$$
\| x \| = | x _ { 1 } | + | x _ { 2 } | = 1 .
$$

Consider the homogeneous polynomial $\boldsymbol { \mathcal { A } } \boldsymbol { x } ^ { 4 }$ with $a _ { 1 1 1 1 } > 0$ and $a _ { 2 2 2 2 } > 0$ in three cases.

Case 1. $x _ { 1 } = 0$ and $x _ { 2 } \neq 0$ . Then $| x _ { 2 } | = 1$ , and hence, $\mathcal { A } { x } ^ { 4 } = a _ { 2 2 2 2 } > 0$

Case 2. $x _ { 1 } \neq 0$ and $x _ { 2 } = 0$ . Then $| x _ { 1 } | = 1$ , and hence, $\mathcal { A } { x } ^ { 4 } = a _ { 1 1 1 1 } > 0$

Case 3. $x _ { 1 } \neq 0$ and $x _ { 2 } \neq 0$ . Then the homogeneous polynomial $\boldsymbol { \mathcal { A } } \boldsymbol { x } ^ { 4 }$ can be divided by $x _ { 2 } ^ { 4 }$ to yield

$$
\frac { A x ^ { 4 } } { x _ { 2 } ^ { 4 } } = a _ { 1 1 1 1 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) ^ { 4 } + 4 a _ { 1 2 1 1 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) ^ { 3 } + 6 a _ { 1 2 2 1 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) ^ { 2 } + 4 a _ { 1 2 2 2 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) + a _ { 2 2 2 2 } .
$$

Let $\begin{array} { r } { t = \frac { x _ { 1 } } { x _ { 2 } } } \end{array}$ and f(t)=4 e

$$
f ( t ) = a _ { 1 1 1 1 } t ^ { 4 } + 4 a _ { 1 2 1 1 } t ^ { 3 } + 6 a _ { 1 2 2 1 } t ^ { 2 } + 4 a _ { 1 2 2 2 } t + a _ { 2 2 2 2 } .
$$

Clearly, $f ( t ) > 0$ if and only if $A x ^ { 4 } > 0$ . Assume that

$$
\begin{array} { r l } & { F = 9 a _ { 1 1 1 1 } ^ { 2 } a _ { 1 2 2 1 } ^ { 2 } - 2 4 a _ { 1 1 1 1 } a _ { 1 2 1 1 } ^ { 2 } a _ { 1 2 2 1 } + 1 2 a _ { 1 2 1 1 } ^ { 4 } - a _ { 1 1 1 1 } ^ { 3 } a _ { 2 2 2 2 } + 4 a _ { 1 1 1 1 } a _ { 1 2 1 1 } a _ { 1 2 2 2 } , } \\ & { G = a _ { 1 1 1 1 } ^ { 2 } a _ { 1 2 2 2 } - 3 a _ { 1 1 1 1 } a _ { 1 2 1 1 } a _ { 1 2 2 1 } + 2 a _ { 1 2 1 1 } ^ { 3 } , } \\ & { H = a _ { 1 1 1 1 } a _ { 1 2 2 1 } - a _ { 1 2 1 1 } ^ { 2 } , } \\ & { I = a _ { 1 1 1 1 } a _ { 2 2 2 2 } - 4 a _ { 1 2 1 1 } a _ { 1 2 2 2 } + 3 a _ { 1 2 2 1 } ^ { 2 } , } \\ & { J = a _ { 1 1 1 1 } a _ { 1 2 2 1 } a _ { 2 2 2 2 } + 2 a _ { 1 2 1 1 } a _ { 1 2 2 1 } a _ { 1 2 2 2 } - a _ { 1 2 2 1 } ^ { 3 } - a _ { 1 1 1 1 } a _ { 1 2 2 2 } ^ { 2 } - a _ { 1 2 1 1 } ^ { 2 } a _ { 2 2 2 2 } , } \\ & { \Delta = I ^ { 3 } - 2 7 J ^ { 2 } . } \end{array}
$$

Therefore, the conclusions directly follow from Lemma 2.3 with $a _ { 0 } = a _ { 1 1 1 1 }$ ， （204号 $a _ { 1 } = a _ { 1 2 1 1 }$ ， $a _ { 2 } = a _ { 1 2 2 1 }$ ， $a _ { 3 } = a _ { 1 2 2 2 }$ and $a _ { 4 } = a _ { 2 2 2 2 }$ ， as required. □

Remark 3.1. It follows from the proof of Theorem 3.1 that $\boldsymbol { \mathcal { A } } \boldsymbol { x } ^ { 4 }$ may be divided by $x _ { 1 } ^ { 4 }$ ，then

$$
f ( t ) = \frac { \mathcal { A } x ^ { 4 } } { x _ { 1 } ^ { 4 } } = a _ { 1 1 1 1 } + 4 a _ { 1 2 1 1 } t + 6 a _ { 1 2 2 1 } t ^ { 2 } + 4 a _ { 1 2 2 2 } t ^ { 3 } + a _ { 2 2 2 2 } t ^ { 4 } ,
$$

where $\begin{array} { r } { t = \frac { x _ { 2 } } { x _ { 1 } } } \end{array}$ . So the conclusions still hold if a22 and a111 are replaced each other on the assumptions of Theorem 3.1.

Theorem 3.2.Let $\mathcal { A }$ be a symmetric tensor of order 4 and dimension 3. Assume that

$$
\begin{array} { r l } & { a _ { 1 1 1 1 } \geq 0 , a _ { 2 2 2 2 } \geq 0 , a _ { 3 3 3 3 } \geq 0 , a _ { 1 1 2 2 } \geq 0 , a _ { 1 1 3 3 } \geq 0 , a _ { 2 2 3 3 } \geq 0 , } \\ & { \alpha _ { 1 } = 6 a _ { 1 2 3 1 } + 3 \sqrt { a _ { 1 1 2 2 } a _ { 1 1 3 3 } } \geq 0 , \beta _ { 1 } = 2 a _ { 1 1 1 3 } + \sqrt { 3 a _ { 1 1 1 } a _ { 1 1 3 3 } } \geq 0 , } \\ & { \gamma _ { 1 } = 2 a _ { 2 1 1 1 } + \sqrt { 3 a _ { 1 1 1 1 } a _ { 1 1 2 2 } } \geq 0 , \alpha _ { 2 } = 2 a _ { 3 2 2 2 } + \sqrt { 3 a _ { 2 2 2 2 } a _ { 2 2 3 3 } } \geq 0 , } \\ & { \beta _ { 2 } = 6 a _ { 1 2 2 3 } + 3 \sqrt { a _ { 1 1 2 2 } a _ { 2 2 3 3 } } \geq 0 , \gamma _ { 2 } = 2 a _ { 1 2 2 2 } + \sqrt { 3 a _ { 1 1 2 2 } a _ { 2 2 2 2 } } \geq 0 , } \\ & { \alpha _ { 3 } = 2 a _ { 2 3 3 3 } + \sqrt { 3 a _ { 3 3 3 } a _ { 2 2 3 3 } } \geq 0 , \beta _ { 3 } = 2 a _ { 1 3 3 3 } + \sqrt { 3 a _ { 1 1 3 3 } a _ { 3 3 3 3 } } \geq 0 , } \\ & { \gamma _ { 3 } = 6 a _ { 1 2 3 3 } + 3 \sqrt { 2 a _ { 1 1 3 3 } a _ { 2 2 3 3 } } \geq 0 , } \end{array}
$$

$$
\begin{array} { r l } & { \tau _ { 1 } = 3 \sqrt { a _ { 1 1 1 1 } a _ { 1 1 2 2 } a _ { 1 1 3 3 } } + 6 a _ { 1 2 3 1 } \sqrt { a _ { 1 1 1 1 } } + 2 a _ { 1 1 1 3 } \sqrt { 3 a _ { 1 1 2 2 } } + 2 a _ { 2 1 1 1 } \sqrt { 3 a _ { 1 1 3 3 } } } \\ & { \qquad + \sqrt { 2 \alpha _ { 1 } \beta _ { 1 } \gamma _ { 1 } } \geq 0 , } \\ & { \tau _ { 2 } = 3 \sqrt { a _ { 1 1 2 2 } a _ { 2 2 2 2 } a _ { 2 2 3 3 } } + 2 a _ { 3 2 2 2 } \sqrt { 3 a _ { 1 1 2 2 } } + 6 a _ { 1 2 2 3 } \sqrt { a _ { 2 2 2 2 } } + 2 a _ { 1 2 2 2 } \sqrt { 3 a _ { 2 2 3 3 } } } \\ & { \qquad + \sqrt { 2 \alpha _ { 2 } \beta _ { 2 } \gamma _ { 2 } } \geq 0 , } \\ & { \tau _ { 3 } = 3 \sqrt { a _ { 1 1 3 3 } a _ { 3 3 3 } a _ { 2 2 3 3 } } + 2 a _ { 2 3 3 3 } \sqrt { 3 a _ { 1 1 3 3 } } + 2 a _ { 1 3 3 3 } \sqrt { 3 a _ { 2 2 3 3 } } + 6 a _ { 1 2 3 3 } \sqrt { a _ { 3 3 3 3 } } } \\ & { \qquad + \sqrt { 2 \alpha _ { 3 } \beta _ { 3 } \gamma _ { 3 } } \geq 0 . } \end{array}
$$

Then $\mathcal { A }$ is copositive.

Proof. It follows from Lemma 2.1 that we can restrict $x$ to

Without loss of generality, let $x _ { 1 } = 1 - t$ and $x _ { 2 } \ = \ t v$ and $x _ { 3 } ~ = ~ t w$ for $t , v \in [ 0 , 1 ]$ and $w = 1 - v$ . Clearly, we have

$$
\begin{array} { r l } {  { A x ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 3 } a _ { i j k l } x _ { 3 } x _ { j } x _ { k } x _ { l } } } \\ & { = a _ { 1 1 1 1 } ( 1 - t ) ^ { 4 } + a _ { 2 2 2 2 } ( t v ) ^ { 4 } + a _ { 3 3 3 } ( t w ) ^ { 4 } } \\ & { \quad + 4 a _ { 1 2 2 2 } ( 1 - t ) ( t w ) ^ { 3 } + 4 a _ { 1 1 3 3 } ( 1 - t ) ( t w ) ^ { 3 } + 4 a _ { 2 1 1 1 } ( 1 - t ) ^ { 3 } ( t w ) } \\ & { \quad + 4 a _ { 2 3 3 3 } ( t v ) ( t w ) ^ { 3 } + 4 a _ { 3 1 1 1 } ( 1 - t ) ^ { 3 } ( t w ) + 4 a _ { 3 2 2 2 } ( t v ) ^ { 3 } ( t w ) } \\ & { \quad + 6 a _ { 1 1 2 2 } ( 1 - t ) ^ { 2 } ( t v ) ^ { 2 } + 6 a _ { 1 3 3 } ( 1 - t ) ^ { 2 } ( t w ) ^ { 2 } + 6 a _ { 2 2 3 3 } ( t v ) ^ { 2 } ( t w ) ^ { 2 } } \\ & { \quad + 1 2 a _ { 1 2 3 1 } ( 1 - t ) ^ { 2 } ( t v ) ( t w ) + 1 2 a _ { 1 2 3 2 } ( 1 - t ) ( t w ) ^ { 2 } ( t w ) } \\ & { \quad + 1 2 a _ { 1 2 3 3 } ( 1 - t ) ( t w ) ( t w ) ^ { 2 } . } \end{array}
$$

Then through simple calculation to yield

$$
\begin{array} { r l } {  { \mathcal { A } x ^ { 4 } = [ a _ { 1 1 1 1 } ( 1 - t ) ^ { 2 } + 2 ( 2 a _ { 3 1 1 1 } w + 2 a _ { 2 1 1 1 } v ) t ( 1 - t )  } } \\ & {  \qquad + ( 3 a _ { 1 1 2 2 } v ^ { 2 } + 1 2 a _ { 1 2 3 1 } v w + 3 a _ { 1 1 3 3 } w ^ { 2 } ) t ^ { 2 } ] ( 1 - t ) ^ { 2 } } \\ & { + [ 3 a _ { 1 1 2 2 } ( 1 - t ) ^ { 2 } + 2 ( 6 a _ { 1 2 3 2 } w + 2 a _ { 1 2 2 2 } v ) t ( 1 - t )  } \\ & { +  ( a _ { 2 2 2 2 } v ^ { 2 } + 4 a _ { 3 2 2 2 } v w + 3 a _ { 2 2 3 3 } w ^ { 2 } ) t ^ { 2 } ] ( t v ) ^ { 2 } } \\ & { + [ 3 a _ { 1 1 3 3 } ( 1 - t ) ^ { 2 } + 2 ( 2 a _ { 1 3 3 3 } w + 6 a _ { 1 2 3 3 } v ) t ( 1 - t )  } \\ & { +  ( 3 a _ { 2 2 3 3 } v ^ { 2 } + 4 a _ { 2 3 3 3 } v w + a _ { 3 3 3 3 } w ^ { 2 } ) t ^ { 2 } ] ( t w ) ^ { 2 } . } \end{array}
$$

Let

$$
\begin{array} { r l } & { F _ { 1 } ( 1 - t , t v , t w ) = a _ { 1 1 1 1 } ( 1 - t ) ^ { 2 } + 2 ( 2 a _ { 3 1 1 1 } w + 2 a _ { 2 1 1 1 } v ) t ( 1 - t ) } \\ & { \qquad + ( 3 a _ { 1 1 2 2 } v ^ { 2 } + 1 2 a _ { 1 2 3 1 } v w + 3 a _ { 1 1 3 3 } w ^ { 2 } ) t ^ { 2 } ; } \\ & { F _ { 2 } ( 1 - t , t v , t w ) = 3 a _ { 1 1 2 2 } ( 1 - t ) ^ { 2 } + 2 ( 6 a _ { 1 2 3 2 } w + 2 a _ { 1 2 2 2 } v ) t ( 1 - t ) } \\ & { \qquad + ( a _ { 2 2 2 2 } v ^ { 2 } + 4 a _ { 3 2 2 2 } v w + 3 a _ { 2 2 3 3 } w ^ { 2 } ) t ^ { 2 } ; } \\ & { F _ { 3 } ( 1 - t , t v , t w ) = 3 a _ { 1 1 3 3 } ( 1 - t ) ^ { 2 } + 2 ( 2 a _ { 1 3 3 3 } w + 6 a _ { 1 2 3 3 } v ) t ( 1 - t ) } \\ & { \qquad + ( 3 a _ { 2 2 3 3 } v ^ { 2 } + 4 a _ { 2 3 3 3 } v w + a _ { 3 3 3 3 } w ^ { 2 } ) t ^ { 2 } . } \end{array}
$$

For the function $F _ { 1 } ( 1 - t , t v , t w )$ with the assumptions that

$$
a _ { 1 1 1 1 } \geq 0 , a _ { 1 1 2 2 } \geq 0 , a _ { 1 1 3 3 } \geq 0 , \alpha _ { 1 } \geq 0 , \beta _ { 1 } \geq 0 , \gamma _ { 1 } \geq 0 , \tau _ { 1 } \geq 0 ,
$$

it follows from Lemma 2.5 that $F _ { 1 } ( 1 - t , t v , t w ) \geq 0$ for all $t , v \in [ 0 , 1 ]$ and （204号 $w = 1 - v$ . Similarly, we also have $F _ { 2 } ( 1 - t , t v , t w ) \geq 0$ and $F _ { 3 } ( 1 - t , t v , t w ) \geq 0$ for all $t , v \in [ 0 , 1 ]$ and $w = 1 - v$ . So,

$$
\begin{array} { r } { \mathcal { A } { x ^ { 4 } } = F _ { 1 } ( 1 - t , t v , t w ) ( 1 - t ) ^ { 2 } + F _ { 2 } ( 1 - t , t v , t w ) ( t v ) ^ { 2 } + F _ { 3 } ( 1 - t , t v , t w ) ( t w ) ^ { 2 } \geq 0 . } \end{array}
$$

Therefore, $\mathcal { A } \mathcal { x } ^ { 4 } \geq 0$ for all $x \geq 0$ and $\| x \| = 1$ . Namely, the tensor $\mathcal { A }$ is copositive， as required.

Obviously, if $\stackrel { \scriptscriptstyle 6 6 } { = }$ ”’is replaced by‘ $>$ ” in all conditions of Theorem 3.2, then the strict copositivity of $\mathcal { A }$ can be showed easily.

Theorem 3.3. Let $\mathcal { A }$ be a symmetric tensor of order 4 and dimension 3.

Assumethat

$$
\begin{array} { r l } & { a _ { 1 1 1 1 } > 0 , a _ { 2 2 2 2 } > 0 , a _ { 3 3 3 3 } > 0 , a _ { 1 1 2 2 } > 0 , a _ { 1 1 3 3 } > 0 , a _ { 2 2 3 3 } > 0 , } \\ & { \alpha _ { 1 } = 6 a _ { 1 2 3 1 } + 3 \sqrt { a _ { 1 1 2 2 } a _ { 1 1 3 3 } } > 0 , \beta _ { 1 } = 2 a _ { 1 1 1 3 } + \sqrt { 3 a _ { 1 1 1 } a _ { 1 1 3 3 } } > 0 , } \\ & { \gamma _ { 1 } = 2 a _ { 2 1 1 1 } + \sqrt { 3 a _ { 1 1 1 1 } a _ { 1 1 2 2 } } > 0 , \alpha _ { 2 } = 2 a _ { 3 2 2 2 } + \sqrt { 3 a _ { 2 2 2 } a _ { 2 2 3 3 } } > 0 , } \\ & { \beta _ { 2 } = 6 a _ { 1 2 2 3 } + 3 \sqrt { a _ { 1 1 2 2 } a _ { 2 2 3 3 } } > 0 , \gamma _ { 2 } = 2 a _ { 1 2 2 2 } + \sqrt { 3 a _ { 1 1 2 2 } a _ { 2 2 2 2 } } > 0 , } \\ & { \alpha _ { 3 } = 2 a _ { 2 3 3 3 } + \sqrt { 3 a _ { 3 3 3 } a _ { 2 2 3 3 } } > 0 , \beta _ { 3 } = 2 a _ { 1 3 3 3 } + \sqrt { 3 a _ { 1 1 3 3 } a _ { 3 3 3 3 } } > 0 , } \\ & { \gamma _ { 3 } = 6 a _ { 1 2 3 3 } + 3 \sqrt { 2 a _ { 1 1 3 3 } a _ { 2 2 3 3 } } > 0 , } \end{array}
$$

$$
\begin{array} { r l } & { \tau _ { 1 } = 3 \sqrt { a _ { 1 1 1 1 } a _ { 1 1 2 2 } a _ { 1 1 3 3 } } + 6 a _ { 1 2 3 1 } \sqrt { a _ { 1 1 1 1 } } + 2 a _ { 1 1 1 3 } \sqrt { 3 a _ { 1 1 2 2 } } + 2 a _ { 2 1 1 1 } \sqrt { 3 a _ { 1 1 3 3 } } } \\ & { \qquad + \sqrt { 2 \alpha _ { 1 } \beta _ { 1 } \gamma _ { 1 } } > 0 , } \\ & { \tau _ { 2 } = 3 \sqrt { a _ { 1 1 2 2 } a _ { 2 2 2 2 } a _ { 2 2 3 3 } } + 2 a _ { 3 2 2 2 } \sqrt { 3 a _ { 1 1 2 2 } } + 6 a _ { 1 2 2 3 } \sqrt { a _ { 2 2 2 2 } } + 2 a _ { 1 2 2 2 } \sqrt { 3 a _ { 2 2 3 3 } } } \\ & { \qquad + \sqrt { 2 \alpha _ { 2 } \beta _ { 2 } \gamma _ { 2 } } > 0 , } \\ & { \tau _ { 3 } = 3 \sqrt { a _ { 1 1 3 3 } a _ { 3 3 3 } a _ { 2 2 3 3 } } + 2 a _ { 2 3 3 3 } \sqrt { 3 a _ { 1 1 3 3 } } + 2 a _ { 1 3 3 3 } \sqrt { 3 a _ { 2 2 3 3 } } + 6 a _ { 1 2 3 3 } \sqrt { a _ { 3 3 3 3 } } } \\ & { \qquad + \sqrt { 2 \alpha _ { 3 } \beta _ { 3 } \gamma _ { 3 } } > 0 . } \end{array}
$$

Then $\mathcal { A }$ is strictly copositive

Remark 3.2. From the proof of Theorems 3.2 and 3.3, it is easily seen to prove the desired results by reducing orders of tensor. That is， an 4th order 3 dimensional tensor is decomposed three 2nd order 3 dimensional tensors, and then， analysing the copositivity of these 2nd order tensors to obtain the desired suffcient conditions. This may be a very important way to studying higher tensors in future.

Theorem 3.4. Let $\mathcal { A }$ be a symmetric tensor of order 4 and dimension 2 with （204号 $a _ { 1 1 1 1 } > 0$ and $a _ { 2 2 2 2 } > 0$ . Assume that

$$
\begin{array} { r l } { a _ { 1 2 2 1 } \leq \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } , } & { 4 a _ { 1 2 1 1 } \sqrt { a _ { 2 2 2 2 } } + \sqrt [ 4 ] { a _ { 1 1 1 1 } } ( 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) > 0 \mathrm { ~ o ~ } a } \\ & { 4 a _ { 1 2 2 2 } \sqrt [ 4 ] { a _ { 1 1 1 1 } } + \sqrt [ 4 ] { a _ { 2 2 2 2 } } ( 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) > 0 ; } \\ { a _ { 1 2 2 1 } > \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } , } & { 2 a _ { 1 2 1 1 } + \sqrt { 6 a _ { 1 2 2 1 } a _ { 1 1 1 1 } - 2 a _ { 1 1 1 1 } \sqrt { a _ { 1 1 1 1 1 } a _ { 2 2 2 2 } } } > 0 \mathrm { ~ } a n } \\ & { 2 a _ { 1 2 2 2 } + \sqrt { 6 a _ { 1 2 2 1 } a _ { 2 2 2 2 } - 2 a _ { 2 2 2 2 } \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } } > 0 . } \end{array}
$$

Then $\mathcal { A }$ is copositive.

Proof. It follows from Lemma 2.1 that we can restrict $\boldsymbol { x } = ( x _ { 1 } , x _ { 2 } ) ^ { \top }$ to

$$
x _ { 1 } \geq 0 , \ x _ { 2 } \geq 0 , \ \| x \| = x _ { 1 } + x _ { 2 } = 1 .
$$

Consider the homogeneous polynomial $\mathcal { A } { x } ^ { 4 }$ with $a _ { 1 1 1 1 } > 0$ and $a _ { 2 2 2 2 } > 0$ in three cases.

Case 1. $x _ { 1 } = 0$ and $x _ { 2 } \neq 0$ . Then $x _ { 2 } = 1$ ，and hence, $\mathcal { A } { x } ^ { 4 } = a _ { 2 2 2 2 } > 0$ Case 2. $x _ { 1 } \neq 0$ and $x _ { 2 } = 0$ . Then $x _ { 1 } = 1$ ， and hence, $\mathcal { A } { x } ^ { 4 } = a _ { 1 1 1 1 } > 0$

Case 3. $x _ { 1 } \neq 0$ and $x _ { 2 } \neq 0$ . Then the homogeneous polynomial $\boldsymbol { \mathcal { A } } \boldsymbol { x } ^ { 4 }$ can be divided by $x _ { 2 } ^ { 4 }$ to yield

$$
\frac { A x ^ { 4 } } { x _ { 2 } ^ { 4 } } = a _ { 1 1 1 1 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) ^ { 4 } + 4 a _ { 1 2 1 1 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) ^ { 3 } + 6 a _ { 1 2 2 1 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) ^ { 2 } + 4 a _ { 1 2 2 2 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) + a _ { 2 2 2 2 } .
$$

Let $\begin{array} { r } { t = \frac { x _ { 1 } } { x _ { 2 } } } \end{array}$ and $\begin{array} { r } { g ( t ) = \frac { \mathcal { A } x ^ { 4 } } { x _ { 2 } ^ { 4 } } } \end{array}$ e.

$$
g ( t ) = a _ { 1 1 1 1 } t ^ { 4 } + 4 a _ { 1 2 1 1 } t ^ { 3 } + 6 a _ { 1 2 2 1 } t ^ { 2 } + 4 a _ { 1 2 2 2 } t + a _ { 2 2 2 2 } .
$$

Clearly, $g ( t ) \geq 0$ if and only if $A x ^ { 4 } \geq 0$ .Let

$$
\alpha = 4 a _ { 1 2 1 1 } a _ { 1 1 1 1 } ^ { - \frac { 3 } { 4 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 4 } } , \beta = 6 a _ { 1 2 2 1 } a _ { 1 1 1 1 } ^ { - \frac { 1 } { 2 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 2 } } , \gamma = 4 a _ { 1 2 2 2 } a _ { 1 1 1 1 } ^ { - \frac { 1 } { 4 } } a _ { 2 2 2 2 } ^ { - \frac { 3 } { 4 } } .
$$

Then for the aussumption (1),the inquality $a _ { 1 2 2 1 } \leq \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } }$ means that

Multiply the inquality $4 a _ { 1 2 1 1 } \sqrt [ 4 ] { a _ { 2 2 2 2 } } + \sqrt [ 4 ] { a _ { 1 1 1 1 } } ( 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) > 0$ by $a _ { 1 1 1 1 } ^ { - \frac { 3 } { 4 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 2 } }$ to yield

$$
4 a _ { 1 2 1 1 } a _ { 1 1 1 1 } ^ { - \frac { 3 } { 4 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 4 } } + a _ { 1 1 1 1 } ^ { - \frac { 1 } { 2 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 2 } } ( 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) > 0 .
$$

Namely,

$$
\alpha = 4 a _ { 1 2 1 1 } a _ { 1 1 1 1 } ^ { - \frac { 3 } { 4 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 4 } } > - ( 3 a _ { 1 2 2 1 } a _ { 1 1 1 1 } ^ { - \frac { 1 } { 2 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 2 } } + 1 ) = - \frac { \beta + 2 } { 2 } .
$$

Similarly, multiply the inquality $4 a _ { 1 2 2 2 } \sqrt [ 4 ] { a _ { 1 1 1 1 } } + \sqrt [ 4 ] { a _ { 2 2 2 2 } } ( 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) >$ $0$ by $a _ { 1 1 1 1 } ^ { - \frac { 1 } { 2 } } a _ { 2 2 2 2 } ^ { - \frac { 3 } { 4 } }$ to yield

$$
\gamma = 4 a _ { 1 2 2 2 } a _ { 1 1 1 1 } ^ { - \frac { 1 } { 4 } } a _ { 2 2 2 2 } ^ { - \frac { 3 } { 4 } } > - ( 3 a _ { 1 2 2 1 } a _ { 1 1 1 1 } ^ { - \frac { 1 } { 2 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 2 } } + 1 ) = - \frac { \beta + 2 } { 2 } .
$$

This means that

$$
\alpha > - { \frac { \beta + 2 } { 2 } } { \mathrm { ~ a n d ~ } } \gamma > - { \frac { \beta + 2 } { 2 } } { \mathrm { ~ f o r ~ } } \beta \leq 6 .
$$

Likewise, the assumptions (2) imply that

$$
\alpha > - 2 \sqrt { \beta - 2 } ~ \mathrm { a n d } ~ \gamma > - 2 \sqrt { \beta - 2 } ~ \mathrm { f o r } ~ \beta > 6 .
$$

So the conclusions directly follow from Lemma 2.4 (ii),as required.

Similarly, using Lemma 2.4 (i), the following conclusion is obtained easily.

Theorem 3.5. Let $A$ be a symmetric tensor of order 4 and dimension 2 with $a _ { 1 1 1 1 } > 0$ and $a _ { 2 2 2 2 } > 0$ . Then $\mathcal { A }$ is copositive if and only if

$$
\begin{array} { r l } & { a _ { 1 2 2 1 } < - \frac { 1 } { 3 } \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } , \ a _ { 1 2 1 1 } \sqrt { a _ { 2 2 2 2 } } + a _ { 1 2 2 2 } \sqrt { a _ { 1 1 1 1 } } > 0 , } \\ & { \left( 3 a _ { 1 2 2 1 } ^ { 2 } - 4 a _ { 1 2 1 1 } a _ { 1 2 2 2 } + a _ { 1 1 1 1 } a _ { 2 2 2 2 } \right) ^ { 3 } \leq 2 7 \big ( a _ { 1 1 1 1 } a _ { 1 2 2 1 } a _ { 2 2 2 2 } + 2 a _ { 1 2 1 1 } a _ { 1 2 2 1 } a _ { 1 2 2 2 } - } \\ & { a _ { 1 2 2 1 } ^ { 3 } - a _ { 1 1 1 1 } a _ { 1 2 2 2 } ^ { 2 } - a _ { 1 2 1 1 } ^ { 2 } a _ { 2 2 2 2 } \big ) ^ { 2 } ; } \end{array}
$$

$$
\begin{array} { r l } & { \quad - \frac { 1 } { 3 } \sqrt { a _ { 1 1 1 } a _ { 2 2 2 } } \leq a _ { 1 2 2 1 } \leq \sqrt { a _ { 1 1 1 } a _ { 2 2 2 } } \quad \alpha n d } \\ & { \quad \left\{ ( 3 a _ { 1 2 2 1 } ^ { 2 } - 4 a _ { 1 2 1 } a _ { 1 2 2 } + a _ { 1 1 1 } a _ { 2 2 2 } ) ^ { 3 } \leq 2 7 ( a _ { 1 1 1 } a _ { 1 2 1 } a _ { 2 2 2 } } \\ & { \quad + 2 a _ { 1 2 1 } a _ { 1 2 2 } a _ { 1 2 2 } - a _ { 1 2 2 1 } ^ { 3 } - a _ { 1 1 1 1 } a _ { 1 2 2 2 } ^ { 3 } - a _ { 1 2 1 1 } a _ { 2 2 2 2 } ^ { 3 } \right\} , } \\ & { \quad \quad \quad \quad \quad \quad \sigma a _ { 1 2 1 1 } \sqrt { a _ { 2 2 2 2 } } + a _ { 1 2 2 2 } \sqrt { a _ { 1 1 1 } } > 0 , } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \sigma ^ { o _ { T } } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ &  \quad \quad \quad \quad \quad \quad \end{array}
$$

a1221 >√@1111a2222 and

$$
\begin{array} { r }  ( \begin{array} { l l l } { ( 3 \mathfrak { a } _ { 1 2 2 , 1 } ^ { 2 } - 4 \mathfrak { a } _ { 2 2 1 , 1 1 } \mathfrak { a } _ { 1 2 2 } + \mathfrak { a } _ { \mathrm { i n } 1 1 } \partial _ { 2 2 , 2 } ) ^ { 3 } \le 2 7 ( \mathfrak { a } _ { 1 1 1 } \mathfrak { a } _ { 1 2 2 , 4 \varpi 2 2 } ) } & & \\ { ( 1 2 \mathfrak { a } _ { 2 1 2 1 } \mathfrak { a } _ { 1 2 2 1 } \mathfrak { a } _ { 1 2 2 } - \mathfrak { a } _ { 1 2 2 , 1 1 } ^ { 3 } - \mathfrak { a } _ { 1 1 1 } \mathfrak { a } _ { 1 2 1 } ^ { 2 } - \mathfrak { a } _ { 1 2 1 } ^ { 2 } \mathfrak { a } _ { 2 2 2 } ) ^ { 5 } , } & & \\ { \omega _ { 1 2 1 , 1 1 } \sqrt { \mathfrak { a } _ { 2 2 2 } + \mathfrak { a } _ { 1 2 2 } \gamma \bar { a } _ { 1 1 } \mathfrak { a } _ { 1 1 } } > 0 , } & & \\ { \omega _ { 1 2 1 } \qquad \alpha _ { 1 } ^ { \circ } } & & \\ { \alpha _ { 1 2 1 1 } \qquad \alpha _ { 1 } \mathfrak { a } _ { 1 2 2 } > 0 , } & & \\ { ( 3 \mathfrak { a } _ { 1 2 2 , 1 } - 4 \mathfrak { a } _ { 1 1 1 } \partial _ { 1 2 2 } ) ^ { 3 } \le 0 , } & & \\ { ( 2 3 \mathfrak { a } _ { 1 2 1 , 1 1 } \mathfrak { a } _ { 1 2 2 } ) ^ { 3 } \qquad \frac { 1 } { \mathfrak { a } _ { 1 1 1 1 } \partial _ { 1 2 2 } \partial _ { 2 1 } } > 2 7 ( \mathfrak { a } _ { 1 1 1 } \mathfrak { a } _ { 1 2 2 } ) ^ { 3 } \le 2 7 ( \mathfrak { a } _ { 1 1 1 } \mathfrak { a } _ { 1 2 2 } \mathfrak { a } _ { 2 2 2 } ) } & \\ { + 2 \mathfrak { a } _ { 2 1 2 1 } \mathfrak { a } _ { 1 2 2 1 } \mathfrak { a } _ { 1 2 2 } - \mathfrak { a } _ { 1 2 1 } ^ { 3 } \mathfrak { a } _ { 1 1 1 } \mathfrak { a } _ { 1 2 1 } ^ { 3 } - \mathfrak { a } _ { 1 2 1 } ^ { 2 } \mathfrak { a } _ { 2 2 } \mathfrak { a } _ { 2 2 } \mathfrak { a } _ { 2 2 } \mathfrak { a } _ { 2 2 } \mathfrak { a } _ { 2 2 } } & \\  ( 4 \mathfrak { a } _ { 1 2 1 } \sqrt { \mathfrak { a } _ { 2 2 2 } } - \mathfrak { a } _ { 1 2 2 } \sqrt { \mathfrak { a } _ { 1 1 } \mathfrak { a } _ { 2 2 } } ) ^ { 3 } \sqrt { 6 \mathfrak { a } _ { 1 2 1 } \mathfrak { a } _ { 2 2 2 } } & \\  \le 6 \mathfrak  \end{array} \end{array}
$$

Proof. Using the similar proof technique of Theorem 3.4, we only need consider the nonnegativity of the polynomial,

$$
g ( t ) = a _ { 1 1 1 1 } t ^ { 4 } + 4 a _ { 1 2 1 1 } t ^ { 3 } + 6 a _ { 1 2 2 1 } t ^ { 2 } + 4 a _ { 1 2 2 2 } t + a _ { 2 2 2 2 }
$$

where t= 1. Let

$$
\alpha = 4 a _ { 1 2 1 1 } a _ { 1 1 1 1 } ^ { - \frac { 3 } { 4 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 4 } } , \beta = 6 a _ { 1 2 2 1 } a _ { 1 1 1 1 } ^ { - \frac { 1 } { 2 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 2 } } , \gamma = 4 a _ { 1 2 2 2 } a _ { 1 1 1 1 } ^ { - \frac { 1 } { 4 } } a _ { 2 2 2 2 } ^ { - \frac { 3 } { 4 } } .
$$

Then

$$
\begin{array} { r l } & { \quad \Delta = 4 ( \hat { l } ^ { 2 } - 8 \alpha ^ { \prime } + 1 2 \hat { l } ^ { 3 } ) ^ { \frac { 1 } { 3 } } - ( \hat { l } ^ { 2 } \hat { l } ^ { 3 } \hat { l } ^ { 3 } + 9 6 \hat { a } _ { 2 } ^ { 3 \dagger } \hat { l } ^ { - } - 2 \hat { l } ^ { 3 } \hat { l } ^ { 3 } - 2 7 \hat { l } ^ { 2 } \hat { l } ^ { 2 } , } \\ & { \quad \quad - \frac { 4 } { 4 \pi \hat { l } ^ { 2 } } \operatorname { l } ^ { 2 } \hat { l } ^ { 3 } \frac { \hat { l } ^ { 3 } } { 2 } [ ( 3 \hat { l } _ { 1 1 2 2 } ^ { 2 } - 4 \hat { l } _ { 1 2 1 1 } \hat { l } _ { 1 2 2 2 } ^ { 4 } + \hat { l } _ { 1 1 1 1 } \hat { l } _ { 2 2 2 2 } ^ { 4 } ) ] ^ { \frac { 1 } { 3 } } - 2 \hat { l } ^ { 3 } \hat { l } ^ { 2 } \hat { l } ( \hat { a } _ { 1 1 1 1 1 } \hat { l } _ { 2 2 2 } \hat { l } _ { 1 2 1 } ^ { 3 } } \\ & { \quad \quad \quad + 2 \hat { l } _ { 1 2 1 1 } \hat { a } _ { 1 2 1 2 } \hat { l } _ { 1 3 2 } - \hat { a } _ { 1 2 1 1 } ^ { 3 } \hat { l } _ { 1 2 1 } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 6 } \hat { l } ^ { 6 } \hat { l } ^ { 2 } \hat { l } ^ { 2 } \hat { 2 } \hat { 2 } ^ { 3 } \hat { 2 } \hat { 2 } ^ { 3 } \hat { 2 } \hat { 2 } ^ { 3 } \hat { 2 } \hat { 2 } ^ { 3 } \hat { 2 } \hat { 2 } ^ { 3 } \hat { 2 } \hat { l } ^ { 3 } \hat { 2 } ^ { 4 } } \\ & { \quad \quad \quad \quad + 2 \hat { l } _ { 1 2 1 2 } \hat { l } _ { 1 3 2 } \hat { l } _ { 1 3 2 } ^ { 4 } \hat { l } _ { 1 3 2 } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 5 } \hat { l } ^ { 6 } \hat { l } ^ { 6 } \hat { l } ^ { 6 } \hat { l } ^ { 6 } \hat { l } ^ { 7 } \hat { l } ^ { 7 } } \\ &  \quad \quad \quad - \frac { 1 }  ( \hat { l } _  1 \end{array}
$$

$$
\begin{array} { l } { \eta = ( \alpha - \gamma ) ^ { 2 } - \frac { 4 ( \beta + 2 ) } { \sqrt { \beta - 2 } } ( \alpha + \gamma + 4 \sqrt { \beta - 2 } ) } \\ { \quad = \frac { 1 6 } { \left( a _ { 1 1 1 1 } a _ { 2 2 2 2 } \right) ^ { \frac { 7 } { 4 } } \sqrt { \beta - 2 } } [ ( a _ { 1 2 1 1 } \sqrt { a _ { 2 2 2 2 } } - a _ { 1 2 2 2 } \sqrt { a _ { 1 1 1 1 } } ) ^ { 2 } \sqrt { 6 a _ { 1 2 2 1 } - 2 \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } } } \\ { \quad \quad - \left( 6 a _ { 1 2 2 1 } + 2 \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 } } \right) ( a _ { 1 2 1 1 } a _ { 2 2 2 2 } \sqrt { a _ { 1 1 1 1 } } + a _ { 1 2 2 2 } a _ { 1 1 1 1 } \sqrt { a _ { 2 2 2 2 } } } \\ { \quad \quad + a _ { 2 2 2 2 } a _ { 1 1 1 1 } \sqrt { 6 a _ { 1 2 2 1 } - 2 \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } } ] . } \end{array}
$$

Thus, the assumption (1) means that (using the inequality $\begin{array} { r } { a _ { 1 2 2 1 } \leq - \frac { 1 } { 3 } \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) } \end{array}$

$$
\beta = 6 a _ { 1 2 2 1 } a _ { 1 1 1 1 } ^ { - \frac { 1 } { 2 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 2 } } \leq 6 \times ( - \frac { 1 } { 3 } \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) a _ { 1 1 1 1 } ^ { - \frac { 1 } { 2 } } a _ { 2 2 2 2 } ^ { - \frac { 1 } { 2 } } = - 2 ,
$$

$\Delta \le 0$ and

$$
\alpha + \gamma = \frac { 4 } { ( a _ { 1 1 1 1 } a _ { 2 2 2 2 } ) ^ { \frac { 3 } { 4 } } } ( a _ { 1 2 1 1 } \sqrt { a _ { 2 2 2 2 } } + a _ { 1 2 2 2 } \sqrt { a _ { 1 1 1 1 } } ) > 0 .
$$

Similarly, by using a simple calculation,we also have

$$
- 2 \leq \beta \leq 6 \mathrm { a n d } \left\{ \begin{array} { l l } { { \Delta \leq 0 } } & { { \mathrm { a n d } \alpha + \gamma > 0 } } \\ { { \begin{array} { l } { { o r } } \\ { { \Delta \geq 0 } } \end{array} } } \end{array} \right.
$$

$$
\beta > 6 \mathrm { ~ a n d ~ } \left\{ \begin{array} { l l } { \Delta \leq 0 } & { \mathrm { ~ a n d ~ } \alpha + \gamma > 0 } \\ & { o r } \\ { \alpha > 0 } & { \mathrm { ~ a n d ~ } \gamma > 0 } \\ & { o r } \\ { \Delta \geq 0 } & { \mathrm { ~ a n d ~ } \eta \leq 0 . } \end{array} \right.
$$

Thus, the conclusions directly follow from Lemma 2.4 (i),as required.

Now we give several simpler sufficient conditions of (strictly） copositive tensors

Theorem 3.6. Let $\mathcal { A }$ be a symmetric tensor of order 4 and dimension 2. Assume that

$$
\begin{array} { r l } & { a _ { 1 1 1 1 } \geq 0 \ ( > 0 ) , a _ { 2 2 2 2 } \geq 0 \ ( > 0 ) , a _ { 1 1 1 2 } \geq 0 \ ( > 0 ) , \ a _ { 2 2 2 1 } \geq 0 ( > 0 ) , } \\ & { 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } + 4 \sqrt { a _ { 2 1 1 1 } a _ { 1 2 2 2 } } \geq 0 \ ( > 0 ) . } \end{array}
$$

Then $\mathcal { A }$ is (strictly） copositive.

Proof. It follows from Lemma 2.1 that we can restrict $\boldsymbol { x } = ( x _ { 1 } , x _ { 2 } ) ^ { \top }$ to

$$
x _ { 1 } \geq 0 , \ x _ { 2 } \geq 0 , \ \| x \| = x _ { 1 } + x _ { 2 } = 1 .
$$

Without loss of generality, we may assume $x _ { 1 } = t$ and $x _ { 2 } = 1 - t$ for all （204号 $t \in [ 0 , 1 ]$ . Then

$$
\begin{array} { l } { \displaystyle \mathcal { A } x ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 2 } a _ { i j k l } x _ { i } x _ { j } x _ { k } x _ { l } } \\ { \displaystyle = a _ { 1 1 1 1 } t ^ { 4 } + 4 a _ { 1 1 1 2 } t ^ { 3 } ( 1 - t ) + 6 a _ { 1 2 2 1 } t ^ { 2 } ( 1 - t ) ^ { 2 } } \\ { \displaystyle \quad + 4 a _ { 2 2 2 1 } t ( 1 - t ) ^ { 3 } + a _ { 2 2 2 2 } ( 1 - t ) ^ { 4 } . } \end{array}
$$

For $t \in ( 0 , 1 )$ , rewritten (3.5) as follow,

$$
\begin{array} { r l } & { A x ^ { 4 } = \left( \sqrt { a _ { 1 1 1 1 } } t ^ { 2 } - \sqrt { a _ { 2 2 2 2 } } ( 1 - t ) ^ { 2 } \right) ^ { 2 } } \\ & { \qquad + 2 t ( 1 - t ) \left( 2 a _ { 1 1 1 2 } t ^ { 2 } + ( 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 } a _ { 2 2 2 2 } } ) t ( 1 - t ) + 2 a _ { 2 2 2 1 } ( 1 - t ) ^ { 2 } \right) . } \end{array}
$$

Let

$$
p ( t ) = 2 a _ { 1 1 1 2 } t ^ { 2 } + ( 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) t ( 1 - t ) + 2 a _ { 2 2 2 1 } ( 1 - t ) ^ { 2 } .
$$

Since the inquality $3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } + 4 \sqrt { a _ { 2 1 1 1 } a _ { 1 2 2 2 } } \geq 0 \ ( >$ O）means that

$$
\frac { 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } } { 2 } + 2 \sqrt { a _ { 1 1 1 2 } a _ { 2 2 2 1 } } \geq 0 \ ( > 0 )
$$

It follows from Lemma 2.2 that $p ( t ) \geq 0 ~ ( > 0 )$ , and hence,

$$
\mathcal { A } x ^ { 4 } = \left( \sqrt { a _ { 1 1 1 1 } } t ^ { 2 } - \sqrt { a _ { 2 2 2 2 } } ( 1 - t ) ^ { 2 } \right) ^ { 2 } + 2 t ( 1 - t ) p ( t ) \geq 0 \ ( > 0 ) .
$$

Clearly, if $t = 0$ or $t = 1$ ， $\mathcal { A } x ^ { 4 } = a _ { 2 2 2 2 }$ or $a _ { 1 1 1 1 }$ . Thus,

$$
\mathcal { A } \ = x ^ { 4 } \geq 0 \ ( > 0 ) \ \mathrm { f o r \ a l l } \ x \geq 0 \ \mathrm { \ w i t h } \ \| x \| = 1 .
$$

So, the conclusions directly follow from Lemma 2.1,as required.

Theorem 3.7. Let $\mathcal { A }$ be a symmetric tensor of order 4 and dimension 2. Assume that

$$
\begin{array} { r l } & { a _ { 1 1 1 1 } \geq 0 \ ( > 0 ) , a _ { 2 2 2 2 } \geq 0 \ ( > 0 ) , } \\ & { a _ { 1 1 1 2 } + \sqrt [ 4 ] { a _ { 1 1 1 } ^ { 3 } a _ { 2 2 2 2 } } \geq 0 \ ( > 0 ) , \ a _ { 2 2 2 1 } + \sqrt [ 4 ] { a _ { 1 1 1 1 } a _ { 2 2 2 2 } ^ { 3 } } \geq 0 \ ( > 0 ) , } \\ & { 3 ( a _ { 1 2 2 1 } - \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) } \\ & { \quad + \ 4 \sqrt { \left( a _ { 1 1 1 2 } + \sqrt [ 4 ] { a _ { 1 1 1 1 } ^ { 3 } a _ { 2 2 2 2 } } \right) \left( a _ { 2 2 2 1 } + \sqrt [ 4 ] { a _ { 1 1 1 1 } a _ { 2 2 2 2 } ^ { 3 } } \right) } \geq 0 \ ( > 0 ) . } \end{array}
$$

Then $\mathcal { A }$ is (strictly） copositive.

Proof.Using the same argumentation technique, For $t \in ( 0 , 1 )$ ，rewritten (3.5) as follow,

$$
\begin{array} { r l } & { \mathcal { A } \displaystyle { x ^ { 4 } = ( \sqrt [ 4 ] { a _ { 1 1 1 1 } } t - \sqrt [ 4 ] { a _ { 2 2 2 2 } } ( 1 - t ) ) ^ { 4 } + 4 \left( a _ { 1 1 1 2 } + \sqrt [ 4 ] { a _ { 1 1 1 1 } ^ { 3 } a _ { 2 2 2 2 } } \right) t ^ { 3 } ( 1 - t ) } } \\ & { \qquad + 6 \left( a _ { 1 2 2 1 } - \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } \right) t ^ { 2 } ( 1 - t ) ^ { 2 } + 4 \left( a _ { 2 2 2 1 } + \sqrt [ 4 ] { a _ { 1 1 1 1 } a _ { 2 2 2 2 } ^ { 3 } } \right) t ( 1 - t ) ^ { 3 } } \\ & { \qquad = ( \sqrt [ 4 ] { a _ { 1 1 1 1 } } t - \sqrt [ 4 ] { a _ { 2 2 2 2 } } ( 1 - t ) ) ^ { 4 } + t ( 1 - t ) p ( t ) , } \end{array}
$$

where

$$
\begin{array} { r l } & { p ( t ) = 4 ( a _ { 1 1 1 2 } + \sqrt [ 4 ] { a _ { 1 1 1 1 } ^ { 3 } a _ { 2 2 2 2 } } ) t ^ { 2 } + 6 ( a _ { 1 2 2 1 } - \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) t ( 1 - t ) } \\ & { \qquad +  4 ( a _ { 2 2 2 1 } + \sqrt [ 4 ] { a _ { 1 1 1 1 } a _ { 2 2 2 2 } ^ { 3 } } ) ( 1 - t ) ^ { 2 } . } \end{array}
$$

The aussumptions assure $p ( t ) \geq 0 \ ( > 0 )$ for all $t \in ( 0 , 1 )$ by Lemma 2.2 It is obvious that $\mathcal { A } x ^ { 4 } = a _ { 2 2 2 2 }$ or $a _ { 1 1 1 1 }$ for $t = 0$ or $t = 1$ . Thus,

$$
\mathcal { A } \displaystyle { x ^ { 4 } \geq 0 \mathrm { ~ ( > 0 ) ~ f o r ~ a l l ~ } x \geq 0 \mathrm { w i t h } \| x \| = 1 } .
$$

Therefore, $\mathcal { A }$ is（strictly） copositive.

From the proving process of Theorems 3.6 and 3.7, the following conclusion is proved easily.

Corollary 3.8. Let $\mathcal { A }$ be a symmetric and strictly copositive tensor of order 4 and dimension 2. Then

$$
\begin{array} { r } { 2 a _ { 1 1 1 2 } \sqrt { a _ { 2 2 2 2 } } + ( 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) \sqrt [ 4 ] { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } + 2 a _ { 1 2 2 2 } \sqrt { a _ { 1 1 1 1 } } > 0 . } \end{array}
$$

Proof. It follows from the strict copositivity of $\mathcal { A }$ that $a _ { 1 1 1 1 } > 0$ and $a _ { 2 2 2 2 } > 0$ For $t \in ( 0 , 1 )$ and $\boldsymbol { x } = ( t , 1 - t ) ^ { \top }$ ，we have

$$
\begin{array} { r l } & { \mathcal { A } { x } ^ { 4 } = \left( \sqrt { a _ { 1 1 1 1 } } t ^ { 2 } - \sqrt { a _ { 2 2 2 2 } } ( 1 - t ) ^ { 2 } \right) ^ { 2 } } \\ & { \qquad + 2 t ( 1 - t ) \left( 2 a _ { 1 1 1 2 } t ^ { 2 } + ( 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 } a _ { 2 2 2 2 } } ) t ( 1 - t ) + 2 a _ { 2 2 2 1 } ( 1 - t ) ^ { 2 } \right) . } \end{array}
$$

Take to = Va111+Va22 . Then $\boldsymbol { x } ^ { 0 } = ( t _ { 0 } , 1 - t _ { 0 } ) ^ { \top }$ ,i.e.,

$$
\boldsymbol { x } ^ { 0 } = \left( \frac { \sqrt [ 4 ] { a _ { 2 2 2 2 } } } { \sqrt [ 4 ] { a _ { 1 1 1 1 } } + \sqrt [ 4 ] { a _ { 2 2 2 2 } } } , \frac { \sqrt [ 4 ] { a _ { 1 1 1 1 } } } { \sqrt [ 4 ] { a _ { 1 1 1 1 } } + \sqrt [ 4 ] { a _ { 2 2 2 2 } } } \right) ^ { \top } ,
$$

and hence,

$$
\begin{array} { r l } & { \mathcal { A } ( x ^ { 0 } ) ^ { 4 } = 2 t _ { 0 } ( 1 - t _ { 0 } ) ( 2 a _ { 1 1 1 2 } t _ { 0 } ^ { 2 } + ( 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) t _ { 0 } ( 1 - t _ { 0 } ) } \\ & { \qquad + \ 2 a _ { 2 2 2 1 } ( 1 - t _ { 0 } ) ^ { 2 } ) > 0 . } \end{array}
$$

Namely,

$$
2 a _ { 1 1 1 2 } t _ { 0 } ^ { 2 } + ( 3 a _ { 1 2 2 1 } + \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } ) t _ { 0 } ( 1 - t _ { 0 } ) + 2 a _ { 2 2 2 1 } ( 1 - t _ { 0 } ) ^ { 2 } > 0 .
$$

So, the desired conclusion follows.

Now we give a simpler sufficient conditions of (strict） copositivity of 4th order 3 dimensional tensors by reducing dimensions.

Theorem 3.9. Let $\mathcal { A }$ be a symmetric tensor of order 4 and dimension 3. Assume that

$$
\begin{array} { r l } & { \alpha _ { 1 1 1 1 } \geq 0 \left( > 0 \right) , \ \alpha _ { 2 2 2 2 } \geq 0 \left( > 0 \right) , \ \alpha _ { 3 3 3 } \geq 0 \left( > 0 \right) } \\ & { \alpha _ { 1 1 2 3 } \geq 0 \left( > 0 \right) , \ \alpha _ { 1 2 2 3 } \geq 0 \left( > 0 \right) , \ \alpha _ { 1 2 3 3 } \geq 0 \left( > 0 \right) } \\ & { \eta _ { 1 } - 2 \alpha _ { 1 1 2 1 } + \sqrt [ 4 ] { \alpha _ { 1 1 1 } ^ { 3 } \alpha _ { 2 2 2 } } \geq 0 \left( > 0 \right) , \ \mu _ { 1 } - 2 \alpha _ { 1 2 2 2 } + \sqrt [ 4 ] { \alpha _ { 1 1 1 } a _ { 2 2 2 } ^ { 3 } } \geq 0 \left( > 0 \right) , } \\ & { \eta _ { 2 } = 2 \alpha _ { 1 1 1 3 } + \sqrt [ 4 ] { \alpha _ { 1 1 1 } ^ { 3 } \alpha _ { 3 3 3 } } \geq 0 \left( > 0 \right) , \ \mu _ { 2 } = 2 \alpha _ { 1 3 3 } + \sqrt [ 4 ] { \alpha _ { 1 1 1 } \alpha _ { 3 3 3 } ^ { 3 } } \geq 0 \left( > 0 \right) , } \\ & { \eta _ { 3 } - 2 \alpha _ { 2 2 3 } + \sqrt [ 4 ] { \alpha _ { 2 2 2 2 } \alpha _ { 3 3 3 } } \geq 0 \left( > 0 \right) , \ \mu _ { 3 } - 2 \alpha _ { 2 3 3 } + \sqrt [ 4 ] { \alpha _ { 2 2 2 } \alpha _ { 3 3 3 } ^ { 3 } } \geq 0 \left( > 0 \right) , } \\ & { \theta _ { 1 } = 3 ( 2 a _ { 1 1 2 2 } - \sqrt { a _ { 1 1 1 1 } \alpha _ { 2 2 2 } } ) + 4 \sqrt { \eta _ { 1 } \mu _ { 1 } } \geq 0 \left( > 0 \right) } \\ & { \theta _ { 2 } = 3 ( 2 a _ { 1 1 3 } - \sqrt { a _ { 1 1 1 } \alpha _ { 2 3 3 } } ) + 4 \sqrt { \eta _ { 2 } \mu _ { 2 } } \geq 0 \left( > 0 \right) } \\ & { \beta _ { 3 } = 3 ( 2 a _ { 2 3 3 } - \sqrt { a _ { 2 2 2 } \alpha _ { 3 3 3 } } ) + 4 \sqrt { \eta _ { 3 } \mu _ { 3 } } \geq 0 \left( > 0 \right) . } \end{array}
$$

Then $\mathcal { A }$ is (strictly） copositive.

Proof. For a vector ${ \boldsymbol { x } } = ( x _ { 1 } , x _ { 2 } , x _ { 3 } ) ^ { \top }$ ， we have

$$
 \begin{array} { r l } { A x ^ { 4 } = a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } + a _ { 3 3 3 3 } x _ { 3 } ^ { 4 } + 4 a _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 3 } + 4 a _ { 1 3 3 3 } x _ { 1 } x _ { 3 } ^ { 3 } } & { } \\ { + 4 a _ { 2 1 1 1 } x _ { 3 } ^ { 4 } x _ { 2 } + 4 a _ { 2 3 3 3 } x _ { 2 } x _ { 3 } ^ { 3 } + 4 a _ { 3 1 1 1 } x _ { 3 } ^ { 3 } x _ { 3 } + 4 a _ { 3 2 2 2 } x _ { 2 } ^ { 3 } x _ { 3 } } & { } \\ { + 6 a _ { 1 1 2 2 } x _ { 1 } ^ { 2 } x _ { 2 } ^ { 2 } + 6 a _ { 1 1 3 3 } x _ { 1 } ^ { 2 } x _ { 3 } ^ { 2 } + 6 a _ { 2 2 3 3 } x _ { 2 } ^ { 2 } x _ { 3 } ^ { 2 } } & { } \\ { = ( { \frac { 1 } { 2 } } a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 4 a _ { 1 1 1 2 } x _ { 1 } ^ { 3 } x _ { 2 } + 6 a _ { 1 1 2 2 } x _ { 1 } ^ { 2 } x _ { 2 } ^ { 2 } + 4 a _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 3 } + { \frac { 1 } { 2 } } a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } ) } & { } \\ { + ( { \frac { 1 } { 2 } } a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 4 a _ { 1 1 1 3 } x _ { 1 } ^ { 3 } x _ { 3 } + 6 a _ { 1 1 3 3 } x _ { 1 } ^ { 2 } x _ { 3 } ^ { 3 } + 4 a _ { 1 3 3 3 } x _ { 1 } x _ { 3 } ^ { 3 } + { \frac { 1 } { 2 } } a _ { 3 3 3 } x _ { 3 } ^ { 4 } ) } & { } \\ { + ( { \frac { 1 } { 2 } } a _ { 2 2 2 } x _ { 2 } ^ { 4 } + 4 a _ { 2 2 2 3 } x _ { 2 } ^ { 3 } x _ { 3 } + 6 a _ { 2 2 3 3 } x _ { 2 } ^ { 2 } x _ { 3 } ^ { 2 } + 4 a _ { 2 3 3 3 } x _ { 2 } x _ { 3 } ^ { 3 } + { \frac { 1 } { 2 } } a _ { 3 3 3 } x _ { 3 } ^ { 4 } ) } & { } \\  + 1 2 a _ { 1 1 2 3 } x _ { 1 } ^ { 3 } x _ { 2 } x _ { 3 } + 1 2 a _ { 1 2 3 3 } x _ { 1 } x _ { 2 } x _ { 3 } + 1 2 a _ { 1 2 3 3 } x _ { 1 } x _ { 2 } x _ { 3 }  \end{array}
$$

Let

$$
g _ { 1 } ( x _ { 1 } , x _ { 2 } ) = \frac { 1 } { 2 } a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + + 4 a _ { 1 1 1 2 } x _ { 1 } ^ { 3 } x _ { 2 } + 6 a _ { 1 1 2 2 } x _ { 1 } ^ { 2 } x _ { 2 } ^ { 2 } + 4 a _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 3 } + \frac { 1 } { 2 } a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } .
$$

Then $g _ { 1 } ( x _ { 1 } , x _ { 2 } )$ may be regarded as a homogeneous polynomial defined by a 4th order 2 dimensional symmetric tensor $\boldsymbol { B } = \left( b _ { i j k l } \right)$ with its entries

$$
b _ { 1 1 1 1 } = \frac { 1 } { 2 } a _ { 1 1 1 1 } , b _ { 1 1 1 2 } = a _ { 1 1 1 2 } , b _ { 1 1 2 2 } = a _ { 1 1 2 2 } , b _ { 1 2 2 2 } = a _ { 1 2 2 2 } , b _ { 2 2 2 2 } = \frac { 1 } { 2 } a _ { 2 2 2 2 } .
$$

That is,

$$
g _ { 1 } ( x _ { 1 } , x _ { 2 } ) = { \cal { B } } y ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 2 } b _ { i j k l } x _ { i } x _ { j } x _ { k } x _ { l } , \mathrm { ~ f o r ~ a l l ~ } y = ( x _ { 1 } , x _ { 2 } ) ^ { \top } .
$$

Then the assumptions imply that

$$
\begin{array} { l } { { b _ { 1 1 1 1 } = \displaystyle \frac { 1 } { 2 } a _ { 1 1 1 1 } \geq 0 , ~ b _ { 2 2 2 2 } = \displaystyle \frac { 1 } { 2 } a _ { 2 2 2 2 } \geq 0 , } } \\ { { b _ { 1 1 1 2 } + \sqrt [ 4 ] { b _ { 1 1 1 1 } ^ { 3 } b _ { 2 2 2 2 } } = a _ { 1 1 1 2 } + \displaystyle \frac { 1 } { 2 } \sqrt [ 4 ] { a _ { 1 1 1 1 } ^ { 3 } a _ { 2 2 2 2 } } = \displaystyle \frac { 1 } { 2 } \eta _ { 1 } \geq 0 , } } \\ { { b _ { 1 2 2 2 } + \sqrt [ 4 ] { b _ { 1 1 1 1 } b _ { 2 2 2 2 } ^ { 3 } } = a _ { 1 2 2 2 } + \displaystyle \frac { 1 } { 2 } \sqrt [ 4 ] { a _ { 1 1 1 1 } a _ { 2 2 2 2 } ^ { 3 } } = \displaystyle \frac { 1 } { 2 } \mu _ { 1 } \geq 0 , } } \end{array}
$$

$$
\begin{array} { l } { { 3 ( b _ { 1 1 2 2 } - \sqrt { b _ { 1 1 1 } b _ { 2 2 2 2 } } ) + 4 \sqrt { \biggl ( b _ { 1 1 1 2 } + \sqrt [ 4 ] { b _ { 1 1 1 1 } ^ { 3 } b _ { 2 2 2 2 } } \biggr ) \biggl ( b _ { 2 2 2 1 } + \sqrt [ 4 ] { b _ { 1 1 1 1 } b _ { 2 2 2 2 } ^ { 3 } } \biggr ) } } } \\ { { = 3 \bigl ( a _ { 1 1 2 2 } - \frac { 1 } { 2 } \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } \bigr ) + 4 \sqrt { \frac { 1 } { 4 } \eta _ { 1 } \mu _ { 1 } } } } \\ { { = \displaystyle \frac { 1 } { 2 } \bigl ( 3 \bigl ( 2 a _ { 1 1 2 2 } - \sqrt { a _ { 1 1 1 1 } a _ { 2 2 2 2 } } \bigr ) + 4 \sqrt { \eta _ { 1 } \mu _ { 1 } } \bigr ) } } \\ { { = \displaystyle \frac { 1 } { 2 } \theta _ { 1 } \geq 0 . } } \end{array}
$$

It follows from Theorem 3.7 that the tensor $\boldsymbol { B }$ is copositive, that is,

$$
g _ { 1 } ( x _ { 1 } , x _ { 2 } ) = \mathcal { B } y ^ { 4 } \geq 0 \mathrm { ~ f o r ~ a l l ~ } y = ( x _ { 1 } , x _ { 2 } ) ^ { \top } \geq 0
$$

Similarly, we also have

$$
\begin{array} { l } { \displaystyle { g _ { 2 } ( x _ { 1 } , x _ { 3 } ) = \frac { 1 } { 2 } a _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 4 a _ { 1 1 1 3 } x _ { 1 } ^ { 3 } x _ { 3 } + 6 a _ { 1 1 3 3 } x _ { 1 } ^ { 2 } x _ { 3 } ^ { 2 } + 4 a _ { 1 3 3 3 } x _ { 1 } x _ { 3 } ^ { 3 } + \frac { 1 } { 2 } a _ { 3 3 3 3 } x _ { 3 } ^ { 4 } \geq 0 , } } \\ { \displaystyle { g _ { 3 } ( x _ { 2 } , x _ { 3 } ) = \frac { 1 } { 2 } a _ { 2 2 2 2 } x _ { 2 } ^ { 4 } + 4 a _ { 2 2 2 3 } x _ { 2 } ^ { 3 } x _ { 3 } + 6 a _ { 2 2 3 3 } x _ { 2 } ^ { 2 } x _ { 3 } ^ { 2 } + 4 a _ { 2 3 3 3 } x _ { 2 } x _ { 3 } ^ { 3 } + \frac { 1 } { 2 } a _ { 3 3 3 3 } x _ { 3 } ^ { 4 } \geq 0 . } } \end{array}
$$

Thus, for all $x = ( x _ { 1 } , x _ { 2 } , x _ { 3 } ) ^ { \top } \geq 0$ ， we have

$$
\begin{array} { r l } & { \mathcal { A } \displaystyle x ^ { 4 } = g _ { 1 } ( x _ { 1 } , x _ { 2 } ) + g _ { 2 } ( x _ { 1 } , x _ { 3 } ) + g _ { 3 } ( x _ { 2 } , x _ { 3 } ) } \\ & { \qquad + 1 2 a _ { 1 1 2 3 } x _ { 1 } ^ { 2 } x _ { 2 } x _ { 3 } + 1 2 a _ { 1 2 2 3 } x _ { 1 } x _ { 2 } ^ { 2 } x _ { 3 } + 1 2 a _ { 1 2 3 3 } x _ { 1 } x _ { 2 } x _ { 3 } ^ { 2 } \geq 0 , } \end{array}
$$

that is, $\mathcal { A }$ is copositive. The proof of strict copositivity of $\mathcal { A }$ is same as the above, we omit it. □

Remark 3.3. Theorem 3.9 is proved by reducing dimensions of tensor. That is, an 4th order 3 dimensional tensor is decomposed three 4th order 2 dimensional tensors， and then， analysing the copositivity of these 2 dimensional tensors to obtain the desired suffcient conditions by using Theorem 3.7. So, distinctly sufficient conditions may be established by applying Theorems 3.4, 3.5, 3.6, respectively.

# 4 Checking vacuum stability of scalar potentials

# 4.1 Vacuum stability of the scalar potential of two real scalars and the Higgs boson

Recently, Kannike [25,26] studied the vacuum stability of general scalar potentials of a few fields. The most general scalar potential of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 2 }$ can be expressed as

$$
V ( \phi _ { 1 } , \phi _ { 2 } ) = \lambda _ { 4 0 } \phi _ { 1 } ^ { 4 } + \lambda _ { 3 1 } \phi _ { 1 } ^ { 3 } \phi _ { 1 } + \lambda _ { 2 2 } \phi _ { 1 } ^ { 2 } \phi _ { 2 } ^ { 2 } + \lambda _ { 1 3 } \phi _ { 1 } \phi _ { 2 } ^ { 3 } + \lambda _ { 0 4 } \phi _ { 2 } ^ { 4 } = \Lambda \phi ^ { 4 } ,
$$

where $\boldsymbol { \Lambda } \ = \ \left( \lambda _ { i j k l } \right)$ is the symmetric tensor of scalar couplings and $\phi \ =$ $( \phi _ { 1 } , \phi _ { 2 } ) ^ { \top }$ is the vector of fields. The tensor of the scalar couplings of the potential is defined by

$$
\begin{array} { r } { \Lambda = \left( \begin{array} { c c } { \left( \begin{array} { c c } { \lambda _ { 4 0 } } & { \frac { 1 } { 4 } \lambda _ { 3 1 } } \\ { \frac { 1 } { 4 } \lambda _ { 3 1 } } & { \frac { 1 } { 6 } \lambda _ { 2 2 } } \end{array} \right) \left( \begin{array} { c c } { \frac { 1 } { 4 } \lambda _ { 3 1 } } & { \frac { 1 } { 6 } \lambda _ { 2 2 } } \\ { \frac { 1 } { 6 } \lambda _ { 2 2 } } & { \frac { 1 } { 4 } \lambda _ { 1 3 } } \end{array} \right) } \\ { \left( \begin{array} { c c } { \frac { 1 } { 4 } \lambda _ { 3 1 } } & { \frac { 1 } { 6 } \lambda _ { 2 2 } } \\ { \frac { 1 } { 6 } \lambda _ { 2 2 } } & { \frac { 1 } { 4 } \lambda _ { 1 3 } } \end{array} \right) \left( \begin{array} { c c } { \frac { 1 } { 6 } \lambda _ { 2 2 } } & { \frac { 1 } { 4 } \lambda _ { 1 3 } } \\ { \frac { 1 } { 4 } \lambda _ { 1 3 } } & { \lambda _ { 0 4 } } \end{array} \right) } \end{array} \right) } \end{array}
$$

that is,

$$
\begin{array} { l } { { \lambda _ { 1 1 1 1 } = \lambda _ { 4 0 } , \quad \lambda _ { 2 2 2 2 } = \lambda _ { 0 4 } , } } \\ { { \ } } \\ { { \lambda _ { 1 1 1 2 } = \lambda _ { 1 1 2 1 } = \lambda _ { 1 2 1 1 } = \lambda _ { 2 1 1 1 } = \displaystyle { \frac { 1 } { 4 } } \lambda _ { 3 1 } , } } \\ { { \ } } \\ { { \lambda _ { 1 1 2 2 } = \lambda _ { 1 2 1 2 } = \lambda _ { 1 2 2 1 } = \lambda _ { 2 1 1 2 } = \lambda _ { 2 1 2 1 } = \lambda _ { 2 2 1 1 } = \displaystyle { \frac { 1 } { 6 } } \lambda _ { 2 2 } , } } \\ { { \ } } \\ { { \lambda _ { 1 2 2 2 } = \lambda _ { 2 1 2 2 } = \lambda _ { 2 2 1 2 } = \lambda _ { 2 2 2 1 } = \displaystyle { \frac { 1 } { 4 } } \lambda _ { 1 3 } . } } \end{array}
$$

It is known that the vacuum stability of the general scalar potential of 2 real singlet scalar fields is equivalent to the positivity of the polynomial (4.1)（[25])， i.e.， the positive definiteness of the tensor $\boldsymbol { \Lambda } = \left( \lambda _ { i j k l } \right)$ . Then it follows from Theorem 3.1 that the tensor $\Lambda$ with $\lambda _ { 1 1 1 1 } = \lambda _ { 4 0 } > 0$ and （204号 $\lambda _ { 2 2 2 2 } = \lambda _ { 0 4 } > 0$ is positive definite if and only if (Multiply by common multiple of denominators to make them simpler),

$$
\left\{ \begin{array} { l l } { 8 \lambda _ { 4 0 } \lambda _ { 2 2 } - 3 \lambda _ { 3 1 } ^ { 2 } \geq 0 , } \\ { 4 ( 1 2 \lambda _ { 4 0 } \lambda _ { 0 4 } - 3 \lambda _ { 3 1 } \lambda _ { 1 3 } + \lambda _ { 2 2 } ^ { 2 } ) ^ { 3 } } \\ { > ( 7 2 \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } + 9 \lambda _ { 3 1 } \lambda _ { 2 2 } \lambda _ { 3 1 } - 2 \lambda _ { 2 2 } ^ { 3 } - 2 7 \lambda _ { 4 0 } \lambda _ { 3 1 } ^ { 2 } - 2 7 \lambda _ { 3 1 } ^ { 2 } \lambda _ { 0 4 } ) ^ { 2 } } \end{array} \right.
$$

$$
\begin{array} { r l } & { \left\{ \begin{array} { l l } { 8 \lambda _ { 4 0 } \lambda _ { 2 2 } - 3 \lambda _ { 3 1 } ^ { 2 } < 0 , } \\ { 1 6 \lambda _ { 4 0 } ^ { 2 } \lambda _ { 2 2 } ^ { 2 } + 3 \lambda _ { 3 1 } ^ { 4 } + 1 6 \lambda _ { 4 0 } ^ { 2 } \lambda _ { 3 1 } \lambda _ { 1 3 } < 1 6 \lambda _ { 4 0 } \lambda _ { 3 1 } ^ { 2 } \lambda _ { 2 2 } + 6 4 \lambda _ { 4 0 } ^ { 3 } \lambda _ { 0 4 } , } \\ { 4 ( 1 2 \lambda _ { 4 0 } \lambda _ { 3 4 } - 3 \lambda _ { 3 1 } \lambda _ { 1 3 } + \lambda _ { 2 2 } ^ { 2 } ) ^ { 3 } } \\ { > ( 7 2 \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } + 9 \lambda _ { 8 1 } \lambda _ { 2 2 } \lambda _ { 3 1 } - 2 \lambda _ { 2 2 } ^ { 3 } - 2 7 \lambda _ { 4 0 } \lambda _ { 3 1 } ^ { 2 } - 2 7 \lambda _ { 3 1 } ^ { 2 } \lambda _ { 4 0 } ) ^ { 2 } } \end{array} \right. } \\ & { \left\{ \begin{array} { l l } { 8 \lambda _ { 4 0 } \lambda _ { 2 2 } - 3 \lambda _ { 3 1 } ^ { 2 } > 0 , } \\ { 1 6 \lambda _ { 4 0 } \lambda _ { 2 2 } ^ { 2 } + 3 \lambda _ { 4 1 } ^ { 3 } + 1 6 \lambda _ { 4 0 } ^ { 2 } \lambda _ { 3 1 } \lambda _ { 1 3 } = 1 6 \lambda _ { 4 0 } \lambda _ { 3 1 } ^ { 2 } \lambda _ { 2 2 } + 6 4 \lambda _ { 4 0 } ^ { 3 } \lambda _ { 9 4 } , } \\ { 4 \lambda _ { 4 0 } \lambda _ { 3 1 } \lambda _ { 2 2 } = 8 \lambda _ { 4 0 } ^ { 2 } \lambda _ { 1 3 } + \lambda _ { 2 2 } ^ { 3 } ) ^ { 3 } } \\ { 4 ( 1 2 \lambda _ { 4 0 } \lambda _ { 3 2 } \lambda _ { 4 0 } - 3 \lambda _ { 3 1 } \lambda _ { 1 3 } + \lambda _ { 2 2 } ^ { 2 } ) ^ { 3 } } \\ { = ( 7 2 \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 4 0 } + 9 \lambda _ { 3 1 } \lambda _ { 2 2 } \lambda _ { 3 1 } - 2 \lambda _ { 2 2 } ^ { 3 } - 2 7 \lambda _ { 4 0 } \lambda _ { 3 1 } ^ { 2 } - 2 7 \lambda _ { 3 1 } ^ { 2 } \lambda _ { 9 4 } ) ^ { 2 } } \end{array} \right. } \end{array}
$$

Therefore, one of the above cases (1) and (2) and (3) can guarantee the vacuum stability of the general scalar potential $V ( \phi _ { 1 } , \phi _ { 2 } )$ of 2 real singlet scalar fields.

The most general scalar potential of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 2 }$ and the Higgs doublet $\mathbf { H }$ (Kannike [25,26]） is

$$
\begin{array} { c } { { V ( \phi _ { 1 } , \phi _ { 2 } , | H | ) = \lambda _ { H } | H | ^ { 4 } + \lambda _ { H 2 0 } | H | ^ { 2 } \phi _ { 1 } ^ { 2 } + \lambda _ { H 1 1 } | H | ^ { 2 } \phi _ { 1 } \phi _ { 2 } + \lambda _ { H 0 2 } | H | ^ { 2 } \phi _ { 2 } ^ { 2 } } } \\ { { + \lambda _ { 4 0 } \phi _ { 1 } ^ { 4 } + \lambda _ { 3 1 } \phi _ { 1 } ^ { 3 } \phi _ { 2 } + \lambda _ { 2 2 } \phi _ { 1 } ^ { 2 } \phi _ { 2 } ^ { 2 } + \lambda _ { 1 3 } \phi _ { 1 } \phi _ { 2 } ^ { 3 } + \lambda _ { 0 4 } \phi _ { 2 } ^ { 4 } , } } \\ { { = \lambda _ { H } | H | ^ { 4 } + M ^ { 2 } ( \phi _ { 1 } , \phi _ { 2 } ) | H | ^ { 2 } + \bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) , } } \end{array}
$$

where

$$
M ^ { 2 } ( \phi _ { 1 } , \phi _ { 2 } ) = \lambda _ { H 2 0 } \phi _ { 1 } ^ { 2 } + \lambda _ { H 1 1 } \phi _ { 1 } \phi _ { 2 } + \lambda _ { H 0 2 } \phi _ { 2 } ^ { 2 }
$$

and

$$
\bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) = V ( \phi _ { 1 } , \phi _ { 2 } , 0 ) = \lambda _ { 4 0 } \phi _ { 1 } ^ { 4 } + \lambda _ { 3 1 } \phi _ { 1 } ^ { 3 } \phi _ { 2 } + \lambda _ { 2 2 } \phi _ { 1 } ^ { 2 } \phi _ { 2 } ^ { 2 } + \lambda _ { 1 3 } \phi _ { 1 } \phi _ { 2 } ^ { 3 } + \lambda _ { 0 4 } \phi _ { 2 } ^ { 4 } .
$$

Let $x = ( \phi _ { 1 } , \phi _ { 2 } , | H | ) ^ { \top }$ . Then $V ( \phi _ { 1 } , \phi _ { 2 } , | H | ) = \mathcal { V } x ^ { 4 }$ ， where $\mathcal { V } = \left( v _ { i j k l } \right)$ is a 4th order 3 dimensional symmetric tensor with its entries

$$
\begin{array} { l } { { v _ { 1 1 1 1 } = \lambda _ { 4 0 } , v _ { 2 2 2 2 } = \lambda _ { 0 4 } , v _ { 3 3 3 3 } = \lambda _ { H } , v _ { 1 1 1 2 } = \displaystyle \frac { 1 } { 4 } \lambda _ { 3 1 } , v _ { 1 2 2 2 } = \frac { 1 } { 4 } \lambda _ { 1 3 } , } } \\ { { v _ { 1 1 3 3 } = \displaystyle \frac { 1 } { 6 } \lambda _ { H 2 0 } , v _ { 1 1 2 2 } = \displaystyle \frac { 1 } { 6 } \lambda _ { 2 2 } , v _ { 2 2 3 3 } = \displaystyle \frac { 1 } { 6 } \lambda _ { H 0 2 } , } } \\ { { v _ { 1 2 3 3 } = \displaystyle \frac { 1 } { 1 2 } \lambda _ { H 1 1 } , v _ { i j k l } = 0 \mathrm { ~ f o r ~ t h e ~ o t h e r s } . } } \end{array}
$$

Clearly, $\displaystyle \bar { V } ( \phi _ { 1 } , \phi _ { 2 } )$ is a 4th order 2 dimensional tensor. Let $\phi = ( \phi _ { 1 } , \phi _ { 2 } ) ^ { \top }$ Then $V ( \phi _ { 1 } , \phi _ { 2 } ) = \Lambda \phi ^ { 4 }$ ，where $\Lambda$ is a symmetric tensor given by (4.2),which

is a principal subtensor of $\nu$ . So,the conditions (a) and (b) and (c) exactly ensure the positive definiteness of $\Lambda$ ,i.e., $\bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) = \Lambda \phi ^ { 4 } > 0$ ：

On the other hand, $M ^ { 2 } ( \phi _ { 1 } , \phi _ { 2 } ) = \phi ^ { \mid } M \phi$ ，where $M$ is a symmtric matrix given by

$$
M = \left( \begin{array} { c c } { { \lambda _ { H 2 0 } } } & { { \frac { 1 } { 2 } \lambda _ { H 1 1 } } } \\ { { 1 } } & { { } } \\ { { \frac { 1 } { 2 } \lambda _ { H 1 1 } } } & { { \lambda _ { H 0 2 } } } \end{array} \right)
$$

It is well-known that $M$ is positive definite if and only if

$$
\lambda _ { H 2 0 } > 0 , \ \lambda _ { H 0 2 } > 0 \ \mathrm { a n d } \ 4 \lambda _ { H 2 0 } \lambda _ { H 0 2 } - \lambda _ { H 1 1 } ^ { 2 } > 0 .
$$

So, the positivity of $V ( \phi _ { 1 } , \phi _ { 2 } , | H | )$ is made certain by $\lambda _ { H } > 0$ and Eq.(4.4) together with the conditions (a) or (b) or (c).

Therefore, the conditions of the vacuum stability for the scalar potential $V ( \phi _ { 1 } , \phi _ { 2 } , | H | )$ of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 2 }$ and the Higgs doublet $\mathbf { H }$ are

$\lambda _ { 4 0 } > 0 , \ \lambda _ { 0 4 } > 0 , \ \lambda _ { H } > 0 , \ \lambda _ { H 2 0 } > 0 , \ \lambda _ { H 0 2 } > 0 , \ 4 \lambda _ { H 2 0 } \lambda _ { H 0 2 } - \lambda _ { H 1 1 } ^ { 2 } > 0$ （204号 and the inequalities systems (a) or (b) or (c).

# 4.2 Vacuum stability for $\mathbb { Z } _ { 3 }$ scalar dark matter

Kannike [25,26] gave another physical example defined by scalar dark matter stable under a $\mathbb { Z } _ { 3 }$ discrete group. The most general scalar quartic potential of the SM Higgs $\mathbf { H } _ { 1 }$ ，an inert doublet $\mathbf { H } _ { 2 }$ and a complex singlet $\mathbf { S }$ which is symmetric under a $\mathbb { Z } _ { 3 }$ group is

$$
\begin{array} { l } { { V ( h _ { 1 } , h _ { 2 } , s ) = \lambda _ { 1 } | H _ { 1 } | ^ { 4 } + \lambda _ { 2 } | H _ { 2 } | ^ { 4 } + \lambda _ { 3 } | H _ { 1 } | ^ { 2 } | H _ { 2 } | ^ { 2 } + \lambda _ { 4 } ( H _ { 1 } ^ { \dagger } H _ { 2 } ) ( H _ { 2 } ^ { \dagger } H _ { 1 } ) } } \\ { { \displaystyle ~ + \lambda _ { S } | S | ^ { 4 } + \lambda _ { S 1 } | S | ^ { 2 } | H _ { 1 } | ^ { 2 } + \lambda _ { S 2 } | S | ^ { 2 } | H _ { 2 } | ^ { 2 } } } \\ { { \displaystyle ~ + \frac { 1 } { 2 } ( \lambda _ { S 1 2 } S ^ { 2 } H _ { 1 } ^ { \dagger } H _ { 2 } + \lambda _ { S 1 2 } ^ { * } S ^ { \dagger 2 } H _ { 2 } ^ { \dagger } H _ { 1 } ) } } \\ { { \displaystyle = \lambda _ { 1 } h _ { 1 } ^ { 4 } + \lambda _ { 2 } h _ { 2 } ^ { 4 } + \lambda _ { 3 } h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } + \lambda _ { 4 } \rho ^ { 2 } h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } } } \\ { { \displaystyle ~ + \lambda _ { S } s ^ { 4 } + \lambda _ { S 1 } s ^ { 2 } h _ { 1 } ^ { 2 } + \lambda _ { S 2 } s ^ { 2 } h _ { 2 } ^ { 2 } - | \lambda _ { S 1 2 } | \rho s ^ { 2 } h _ { 1 } h _ { 2 } } } \\ { { \displaystyle \equiv \lambda _ { S } s ^ { 4 } + M ^ { 2 } ( h _ { 1 } , h _ { 2 } ) s ^ { 2 } + \hat { V } ( h _ { 1 } , h _ { 2 } ) } , } \end{array}
$$

Where

$$
\begin{array} { r l } & { h _ { 1 } = | H _ { 1 } | , ~ h _ { 2 } = | H _ { 2 } | , H _ { 2 } ^ { \dagger } H _ { 1 } = h _ { 1 } h _ { 2 } \rho e ^ { i \phi } , S = s e ^ { i \phi s } , \lambda _ { S 1 2 } = - | \lambda _ { S 1 2 } | , } \\ & { M ^ { 2 } ( h _ { 1 } , h _ { 2 } ) = \lambda _ { S 1 } h _ { 1 } ^ { 2 } + \lambda _ { S 2 } h _ { 2 } ^ { 2 } - | \lambda _ { S 1 2 } | \rho h _ { 1 } h _ { 2 } , } \\ & { \hat { V } ( h _ { 1 } , h _ { 2 } ) = V ( h _ { 1 } , h _ { 2 } , 0 ) = \lambda _ { 1 } h _ { 1 } ^ { 4 } + \lambda _ { 2 } h _ { 2 } ^ { 4 } + \lambda _ { 3 } h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } + \lambda _ { 4 } \rho ^ { 2 } h _ { 1 } ^ { 2 } h _ { 2 } ^ { 2 } . } \end{array}
$$

The orbit space parameter $\rho \in [ 0 , 1 ]$ as implied by the Cauchy inequality $0 \leq | H _ { 1 } ^ { \dagger } H _ { 2 } | \leq | H _ { 1 } | | H _ { 2 } |$ ：

Let $x = ( h _ { 1 } , h _ { 2 } , s ) ^ { \scriptscriptstyle \mid }$ . Then $V ( h _ { 1 } , h _ { 2 } , s ) = \mathcal { V } x ^ { 4 }$ ,where $\mathcal { V } = \left( v _ { i j k l } \right)$ is an 4th order 3 dimensional real symmetric tensor given by

$$
\begin{array} { r l r } & { \displaystyle v _ { 1 1 1 1 } = \lambda _ { 1 } , ~ v _ { 2 2 2 2 } = \lambda _ { 2 } , ~ v _ { 3 3 3 3 } = \lambda _ { S } , } & \\ & { \displaystyle v _ { 1 1 2 2 } = \frac { 1 } { 6 } ( \lambda _ { 3 } + \lambda _ { 4 } \rho ^ { 2 } ) , ~ v _ { 1 1 3 3 } = \frac { 1 } { 6 } \lambda _ { S 1 } , ~ v _ { 2 2 3 3 } = \frac { 1 } { 6 } \lambda _ { S 2 } , } & \\ & { \displaystyle v _ { 1 2 3 3 } = - \frac { 1 } { 1 2 } | \lambda _ { S 1 2 } | \rho , ~ v _ { i j k l } = 0 \mathrm { ~ f o r ~ t h e ~ o t h e r s } . } & \end{array}
$$

It follows from Theorem 3.3 that the conditions of strict copositivity of the tensor $\nu$ (that is, $V ( h _ { 1 } , h _ { 2 } , s ) = \mathcal { V } x ^ { 4 } > 0$ ）are given by

$$
\begin{array} { r l } & { \lambda _ { 1 } > 0 , \ \lambda _ { 2 } > 0 , \ \lambda _ { S } > 0 , } \\ & { \lambda _ { 3 } + \lambda _ { 4 } \rho ^ { 2 } > 0 , \ \lambda _ { S 1 } > 0 , \ \lambda _ { S 2 } > 0 , } \\ & { - \left| \lambda _ { S 1 2 } \right| \rho + \sqrt { 2 \lambda _ { S 1 } \lambda _ { S 2 } } > 0 , } \\ & { \sqrt { \lambda _ { S } \lambda _ { S 1 } \lambda _ { S 2 } } - \left| \lambda _ { S 1 2 } \right| \rho \sqrt { \lambda _ { S } } + \sqrt { 2 \lambda _ { S } \sqrt { \lambda _ { S 1 } \lambda _ { S 2 } } ( - \left| \lambda _ { S 1 2 } \right| \rho + \sqrt { 2 \lambda _ { S 1 } \lambda _ { S 2 } } ) } > 0 . } \end{array}
$$

So the above conditions assure the potential $V ( h _ { 1 } , h _ { 2 } , s )$ symmetric under a $\mathbb { Z } _ { 3 }$ group is bounded from below. These conditions are different from ones of Kannike [25,26] and Chen-Huang-Qi [12].

# Acknowledgments

The authors would like to express their sincere thanks to Professor Yimin Wei, Professor Chen Ling, Professor Gaohang Yu for their constructive comments and valuable suggestions.

# References

[1] Andersson, L.E., Chang, G., Elfving, T.: Criteria for copositive matrices using simplices and barycentric coordinates,Linear Algebra Appl., 220(1995) 9-30   
[2] Burer, S.: On the Copositive Representation of Binary and Continuous Nonconvex Quadratic Programs,Math. Program., Series A, 120(2009) 479-495 [3] Burer, S.: Dong,H., Representing Quadratically Constrained Quadratic Programs as Generalized Copositive Programs， Oper. Res. Lett., 40(2012） 203-206   
[4] Bomze, I.: Copositive optimization-recent developments and applications,Eur. J. Oper.Res., 216(2012) 509-520   
[5] Balaji, R., Palpandi, K.: Positive definite and Gram tensor complementarity problems. Optim. Lett. 12(3)(2018) 639-648   
[6] Bai, X.L., Huang, Z.H., Wang, Y.: Global uniqueness and solvability for tensor complementarity problems. J. Optim. Theory Appl. 170(1)(2016) 72-84   
[7] Cottle, R., Habetler, G., Lemke, C.: On classes of copositive matrices, Linear Algebra Appl. 3(3)(1970) 295-310   
[8] Chang, G., Sederberg, T.W.: Nonnegative quadratic Bézier triangular patches, Comput. Aided Geom. D., 11(1)(1994) 113-116   
[9] Che,M.， Qi, L.， Wei, Y.: Stochastic $R _ { 0 }$ tensors to stochastic tensor complementarity problems, Optim.Lett.13(2)(2019) 261-279   
[10] Che,M.L.，Qi， L.，Wei，Y.M.: Positive-definite tensors to nonlinear complementarity problems,J. Optim. Theory Appl. 168(2)(2016） 475- 487   
[11] Chen, H., Huang, Z., Qi, L.: Copositivity Detection of Tensors: Theory and Algorithm, J. Optim. Theory Appl. 174(3)(2017)， 746-761   
[12] Chen, H., Huang, Z., Qi,L.: Copositive tensor detection and its applications in physics and hypergraphs, Compu. Optim. Appl. 69(1)(2018) 133-158   
[13] Chen, H., Wang, Y., High-order copositive tensors and its applications, J. Appl. Anal. Compu. 8(6)(2018) 1863-1885   
[14] Chen, H.， Qi, L., Song, Y.: Column suficient tensors and tensor complementarity problems. Front. Math. China 13(2)(2018) 255-276   
[15] Ding, W., Luo, Z., Qi, L.: P-tensors,P $_ 0$ -tensors,and their applications. Linear Algebra Appl. 555(2018) 336-354   
[16] Gadem， R.N.， Li, C.C.: On positive definiteness of quartic forms of twovariables, IEEE Trans.Auromat. Conrr., AC-9(1964) 187-188   
[17] Gowda, M.S.: Polynomial complementarity problems. Pac. J. Optim. 13(2)(2017) 227-241   
[18] Hillar, C., Lim, L.: Most tensor problems are NP-hard. JACM, 60(2013) 1-39   
[19] Huang, H., Qi, L.: Formulating an n-person noncooperative game as a tensor complementarity problem, Compu. Optim. Appl., 66:3(2017),557- 576   
[20] Hadeler, K.P.: On copositive matrices. Linear Algebra Appl., 49(1983) 79-89   
[21] Haynsworth, E.: Hoffman， A.J.， Two remarks on copositive matrices, Linear Algebra Appl. 2(1969) 387-392   
[22] Johnson, C.R.: Reams, R., Spectral theory of copositive matrices, Linear Algebra Appl. 395(2005) 275-281   
[23] Ku, W.H.: Explicit criterion for the positive definiteness of a general quartic form, IEEE Tram. Automat. Conrr.. AC-IO(3)(1965) 372-373   
[24] Kaplan，W.: A test for copositive matrices， Linear Algebra Appl. 313(2000） 203-206   
[25] Kannike, K.: Vacuum stability of a general scalar potential of a few fields,Eur.Phys. J. C(2016) 76: 324   
[26] Kannike, K.: Erratum to: Vacuum stability of a general scalar potential of a few fields, Eur. Phys. J. C (2018) 78: 355   
[27] Kannike, K.: Vacuum stability conditions from copositivity criteria, Eur. Phys. J. C(2012) 72: 2093   
[28] Li, L.， Zhang， X.， Huang, Z.， Qi, L.: Test of copositive tensors, J. Industrial Manag. Optim. April 2019, 15(2): 881-891   
[29] Jury, E.I., Mansour, M.: Positivity and nonnegativity of a quartic equation and related problems，IEEE Trans.Automat.Control, 26(1981) 444-451   
[30] Luo, Z., Qi, L., Xiu, N.: The sparsest solutions to Z-tensor complementarity problems. Optim. Lett. 11(3), 471-482 (2017)   
[31] Murty, K.G., Kabadi, S.N.: Some NP-complete problems in quadratic and nonlinear programming, Math. Program. 39(1987) 117-129   
[32] Martin, D.H.: Copositlve matrices and definiteness of quadratic forms subject to homogeneous linear inequality constraints, Linear Algebra Appl., 35(1981) 227-258   
[33] Motzkin， T.S.: quadratic forms, National Bureau of Standards Report,1818（1952) 11-12   
[34] Nadler, E.: Nonnegativity of bivariate quadratic functions on a triangle, Comput. Aided Geom. D., 9(3)(1992) 195-205   
[35] Nie, J., Yang, Z., Zhang, X.: A Complete Semidefinite Algorithm for Detecting Copositive Matrices and Tensors, SIAM J. Optim., 28(4)(2018) 2902-2921   
[36] Ping, L., Yu, F.Y.: Criteria for copositive matrices for order four, Linear Algebra Appl.,194(1993) 109-124   
[37] Qi, L.: Eigenvalues of a real supersymmetric tensor, J. Symbolic Comput. 40(2005)1302-1324   
[38] Qi, L.: Symmetric Nonnegative Tensors and Copositive Tensors, Linear Algebra Appl., 439(2013) 228-238   
[39] Qi, L., Chen, H., Chen, Y.: Tensor Eigenvalues and Their Applications, Springer Singapore, 2018   
[40] Qi, L., Luo, Z.: Tensor Analysis: Spectral Theory and Special Tensors. SIAM, Philadelpia 2017   
[41] Song, Y., Qi, L.: Necessary and sufficient conditions of copositive tensors,Linear Multilinear Algebra. 63(1)(2015) 120-131   
[42] Song，Y.，Qi， L.: Properties of tensor complementarity problem and some classes of structured tensors,Ann. Appl. Math. 33(3)(2017) 308- 323   
[43] Song，Y.， Qi， L.: Properties of some classes of structured tensors, J. Optim. Theory Appl. 165(3)(2015) 854-873   
[44] Song，Y.，Qi， L.: Tensor complementarity problem and semi-positive tensors,J. Optim. Theory Appl. 169(2016) 1069-1078   
[45] Song, Y., Qi, L.: Eigenvalue analysis of constrained minimization problem for homogeneous polynomial, J. Glob. Optim. 64(3)(2016) 563-575   
[46] Song, Y., Yu, G.: Properties of solution set of tensor complementarity problem, J. Optim. Theory Appl. 170(2016) 85-96   
[47] Song,Y., Qi, L.: Strictly semi-positive tensors and the boundedness of tensor complementarity problems,Optim. Lett.11(2017) 1407-1426   
[48] Song， Y.， Mei, W.: Structural Properties of Tensors and Complementarity Problems. J. Optim. Theory Appl. 176(2)(2018) 289-305   
[49] Ulrich, G.,Watson L.T.: Positivity conditions for polynomials, SIAM J. Scx. COMPUT. 15(3)(1994) 528-544   
[50] Valiaho，H.: Criteria for copositive matrices,Linear Algebra Appl. 81(1986) 19-34   
[51] Wang, X.， Chen, H.， Wang, Y.: Solution structures of tensor complementarity problem. Front. Math. China 13(4)(2018) 935-945   
[52] Wang, Y., Huang, Z.H.， Bai, X.L.: Exceptionally regular tensors and tensor complementarity problems. Optim. Method. Softw. 31(4)(2016) 815-828   
[53] Wang, J., Hu, S., Huang, Z.H.: Solution sets of quadratic complementarity problems. J.Optim. Theory Appl.176(1)(2018) 120-136