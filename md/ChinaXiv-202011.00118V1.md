# A necessary and sufficient condition of positive definiteness for 4th order symmetric tensors defined in particle physics

Yisheng Song\* Liqun Qit

Abstract. In this paper，we mainly discuss analytical expressions of positive definiteness for a special 4th order 3-dimensional symmetric tensor defined by the constructed model for a physical phenomenon. Firstly,an analytically necessary and sufficient conditions of 4th order 2-dimensional symmetric tensors are given to test its positive definiteness.Furthermore, by means of such a result,a necessary and sufficient condition of positive definiteness is obtained for a special 4th order 3-dimensional symmetric tensor. Such an analytical conditions can be used for verifying the vacuum stability of general scalar potentials of two real singlet scalar fields and the Higgs boson. The positive semi-definiteness conclusions are presented too.

Key Words and Phrases: 4th order Tensors,Positive definiteness, Homogeneous polynomial, Analytical expression.

2010 AMS Subject Classification: 70S20，15A72，15A63,  
90C20,90C30，81T60

# 1 Introduction

In particle physics, the scalar potential is written as a polynomial in scalar fields. The polynomial degree of the potential is 4 when one keeps the scalar interactions renormalizable [28]. Then the condition for the potential of $n$ （204 real scalar fields $\phi _ { i }$ $( i = 1 , 2 , \cdots , n )$ to be bounded from below in the strong sense is equivalent to the requirement that for all vectors $\phi = ( \phi _ { 1 } , \cdot \cdot \cdot , \phi _ { n } ) \in$ $\mathbb { R } ^ { n } \setminus \{ 0 \}$ ，

$$
V ( \phi ) = \sum _ { i , j , k , l = 1 } ^ { n } v _ { i j k l } \phi _ { i } \phi _ { j } \phi _ { k } \phi _ { l } > 0 .
$$

Let $\mathcal { V } = \left( v _ { i j k l } \right)$ . Then $\nu$ is a 4th order symmetrical tensor,and hence, the above requirement (1.1) is the positive definiteness of the tensor $\nu$ . Qi [46,47] first introduced positive definiteness and copositivity of tensors. An $m$ th order $n$ dimensional real tensor $\mathcal { V } = ( v _ { i _ { 1 } i _ { 2 } \cdots i _ { m } } )$ is said to be

(i) positive semi-definite if $\mathcal { V } x ^ { m } = \sum _ { i _ { 1 } , i _ { 2 } , \cdots , i _ { m } = 1 } ^ { n } v _ { i _ { 1 } i _ { 2 } \cdots i _ { m } } x _ { i _ { 1 } } x _ { i _ { 2 } } \cdots x _ { i _ { m } } \geq 0$ for all $x \in \mathbb { R } ^ { n }$ and even number $m$ ，   
(ii) positive definite if $\nu x ^ { m } > 0$ for all $x \in \mathbb { R } ^ { n } \setminus \{ 0 \}$ and even number $m$ ，   
(iii) copositive if $\nu x ^ { m } \geq 0$ for all $x \geq 0$ ：，   
(iv) strictly copositive if $\nu x ^ { m } > 0$ for all $x \geq 0$ and $x \neq 0$

Kannike [30-32] presented the vacuum stability conditions of general scalar potentials of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 2 }$ and the Higgs doublet $\mathbf { H }$ , and studied the sufficient condition of boundedness from below for scalar potential of the SM Higgs $\mathbf { H } _ { 1 }$ ，an inert doublet $\mathbf { H } _ { 2 }$ and a complex singlet S. In fact, such two problems solved by Kannike [30] are to respectively require positive definiteness and copositivity for the corresponding 4th order 3- dimensional symmetric tensors. Also see Faro-Ivanov [15], Belanger-KannikePukhov-Raidal [3,4], Ivanov- Kopke-Mühlleitner [28] for more details. In Refs. [24-27,39], one can construct only one quadratic term and five quartic terms for the Higgs potential with the help of three Higgs doublets with equal electroweak quantum numbers, which is a quartic polynomial with real coefficients defined on complex field. Toorop-Bazzocchi-Merlo-Paris [1,2land Degee-Ivanov-Keus [12] turned such a polynomial from complex field to real field. In fact, they are trying to look for the analytical condition of such a polynomial to be positive.

Recently, Song-Qi [58] and Liu-Song [38] have respectively gave the differently sufficient condition of copositivity for 4th order 3-dimensional symmetric tensors to find the vacuum stability conditions of scalar potential of the SM Higgs $\mathbf { H } _ { 1 }$ ，an inert doublet $\mathbf { H } _ { 2 }$ and a complex singlet S. Very recently, Qi-Song-Zhang [43] showed a necessary and sufficient condition of copositivity for such a tensor given by the above particle physical model.

In the past decades,many numerical algorithms were established to find some H-(Z-)eigenvalues of a tensor $[ 6 , 8 , 1 1 , 2 0 - 2 3 , 4 0 - 4 2 , 4 6 , 4 8 , 4 9 , 6 1 ]$ ，and then, they may be applied to test the positive definiteness of such an even order tensor by means of the sign of the smallest H-(Z-)eigenvalue. On the other hand, some classes of even order tensors with special structures may determine directly their positive definiteness. For example,Hilbert tensors [51], diagonal dominant tensors [46], B-tensors [13,37,50,53,60], M-tensors [14,62], strong Hankel tensors [9,45], generalized anti-circular tensor [36], symmetric Cauchy tensor [5],are in this category. For more structured properties of tensors, see [48,49,53-57].

However, the practical matters such as the vacuum stability of general scalar potentials of a few fields require analytical expressions. The most general scalar potential of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 2 }$ and the Higgs doublet $\mathbf { H }$ (Kannike [30-32]） is

$$
\begin{array} { r l } & { V ( \phi _ { 1 } , \phi _ { 2 } , | H | ) = \lambda _ { H } | H | ^ { 4 } + \lambda _ { H 2 0 } | H | ^ { 2 } \phi _ { 1 } ^ { 2 } + \lambda _ { H 1 1 } | H | ^ { 2 } \phi _ { 1 } \phi _ { 2 } + \lambda _ { H 0 2 } | H | ^ { 2 } \phi _ { 2 } ^ { 2 } } \\ & { \qquad + \lambda _ { 4 0 } \phi _ { 1 } ^ { 4 } + \lambda _ { 3 1 } \phi _ { 1 } ^ { 3 } \phi _ { 2 } + \lambda _ { 2 2 } \phi _ { 1 } ^ { 2 } \phi _ { 2 } ^ { 2 } + \lambda _ { 1 3 } \phi _ { 1 } \phi _ { 2 } ^ { 3 } + \lambda _ { 0 4 } \phi _ { 2 } ^ { 4 } . } \end{array}
$$

Clearly, such a polynomial of the degree 4 can define a 4th order 3-dimensional symmetric tensor,and hence, the vacuum stability of such a scalar potential is equivalent to the positive definiteness of such a tensor. So this requires an analytically necessary and sufficient condition of positive definiteness. For a 4th order 2 dimensional symmetric tensor, the analytical condition of its positive definiteness traced back to ones of the Refs. Gadem-Li [17], Ku [33] and Jury-Mansour [29]. Wang-Qi [59] improved their proof and conclusions. However, the above result depend on the discriminant of such a polynomial. Recently, Guo [18] showed a new necessary and sufficient condition without the discriminant. Very recently, Qi-Song-Zhang [44] gave a new necessary and sufficient condition other than the above results. Hasan-Hasan [19] claimed that a necessary and sufficient condition of positive definiteness of 4th order

3-dimensional symmetric tensor was proved without the discriminant. However, there is a problem in their process of argumentation. In 1998, Fu [16] pointed out that Hasan-Hasan's results are all suffcient only. Until now, we don't know the analytically necessary and sufficient condition of positive definiteness for a 4th order 3-dimensional symmetric tensor.

In this paper, we mainly concentration on the analytical expressions of positive definiteness for a special 4th order tensor given by (1.2). More precisely, by means of Qi-Song-Zhang's result, we first show an analytically necessary and sufficient condition of positive definiteness of 4th order 2 dimensional symmetric tensors. Secondly, with the help of this conclusion, we discuss positive definiteness of a 4th order 3-dimension symmetric tensor defined by (1.2). Then these analytical conditions are the vacuum stability conditions for the potential (1.2) of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 1 }$ and the Higgs doublet $\mathbf { H }$ ：

# 2 Preliminaries and Basic facts

A 4th order 3-dimensional real tensor $\mathbf { V }$ consists of 81 entries in the real field （204 $\mathbb { R }$ ,i.e.,

$$
{ \bf V } = ( v _ { i j k l } ) , \quad \quad v _ { i j k l } \in \mathbb { R } , i , j , k , l = 1 , 2 , 3 .
$$

A tensor $\mathbf { V }$ is said to be symmetric if its entries $v _ { i j k l }$ are invariant for any permutation of its indices. It is known that a 4th order 3-dimensional symmetric tensor $\mathbf { V }$ is composed of 15 independent entries only,

$$
\begin{array} { r l } & { v _ { 1 1 1 1 } , v _ { 2 2 2 2 } , v _ { 3 3 3 3 } , v _ { 1 2 2 2 } , v _ { 1 3 3 3 } , v _ { 1 1 1 2 } , v _ { 1 1 1 3 } , v _ { 2 3 3 3 } , } \\ & { v _ { 2 2 2 3 } , v _ { 1 1 2 2 } , v _ { 1 1 3 3 } , v _ { 2 2 3 3 } , v _ { 1 2 2 3 } , v _ { 1 1 2 3 } , v _ { 1 2 3 3 } . } \end{array}
$$

It is obvious that there is a consistent one-to-one match between a 4th order 3-dimensional symmetric tensor and a homogeneous polynomial of degree 4 with 3 variables. Such a homogeneous polynomial, denoted as $\mathbf { V } x ^ { 4 }$ ,i.e.,

$$
\mathbf { V } x ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 3 } v _ { i j k l } x _ { i } x _ { j } x _ { k } x _ { l } .
$$

Let $\| \cdot \|$ denote any norm on $\mathbb { R } ^ { n }$ . Then the following conclusions on unit sphere are known [46,48,49, 52].

Lemma 2.1.（[46]) Let $\mathbf { V }$ be a 4th order symmetric tensor and let $S$ be the unit sphere on $\mathbb { R } ^ { n }$ ， $S = \{ x \in \mathbb { R } ^ { n } : \ \| x \| = 1 \}$ . Then

(i) V is positive semi-definite if and only if $\mathbf { V } x ^ { 4 } \geq 0$ for all $x \in S$ (ii) V is positive definite if and only if $\mathbf { V } x ^ { 4 } > 0$ for all $x \in S$ ：

The following results should be well-known,which is showed hundreds of years ago. Also see Qi-Song-Zhang [44].

Lemma 2.2. Let $P ( t )$ be a quadratic polynomial,

$$
P ( t ) = a t ^ { 2 } + b t + c ,
$$

with $a > 0$ . Then $P ( t ) > 0 \ ( \geq 0 )$ for all $t \geq 0$ if and only if

(1) $b \geq 0$ and $c > 0 ~ ( \geq 0 )$ (2） $b < 0$ and $4 a c - b ^ { 2 } > 0 ( \geq 0 ) .$ （204号

In the proof of main results, we will use the following lemma, which were proved by Qi-Song-Zhang [44], recently.

Lemma 2.3. Let $P ( t )$ be a quartic polynomial,

$$
P ( t ) = a t ^ { 4 } + b t ^ { 3 } + c t ^ { 2 } + d t + e ,
$$

where $a \ > \ 0$ and $\textit { e } > 0$ .Then $P ( t ) \geq 0$ for all $t$ if and only if $\Delta \ge$ 0， $| b { \sqrt { e } } - d { \sqrt { a } } | \leq 4 { \sqrt { a c e + 2 a e { \sqrt { a e } } } }$ and either (i) $- 2 { \sqrt { a e } } \leq c \leq 6 { \sqrt { a e } }$ ；or (ii) $c > 6 { \sqrt { a e } }$ and $| b { \sqrt { e } } + d { \sqrt { a } } | \leq 4 { \sqrt { a c e - 2 a e { \sqrt { a e } } } }$ ，where

$$
\Delta = 4 ( 1 2 a e - 3 b d + c ^ { 2 } ) ^ { 3 } - ( 7 2 a c e + 9 b c d - 2 c ^ { 3 } - 2 7 a d ^ { 2 } - 2 7 b ^ { 2 } e ) ^ { 2 } .
$$

Furthermore, $P ( t ) > 0$ for all $t$ if and only if

$$
\Delta = 0 , b { \sqrt { e } } = d { \sqrt { a } } , b ^ { 2 } + 8 a { \sqrt { a e } } = 4 a c < 2 4 a { \sqrt { a e } } ;
$$

# 3 Positive definiteness of 4th order symmetric tensors

In this section, we mainly discuss analytical expressions of positive definiteness of 4th order tensors. Furthermore, we present a necessary and sufficient condition of positive definiteness for a special 4th order 3-dimension symmetric tensor defined by mathematical models in particle physics.

# 3.1 4th order 2 dimensional symmetric tensors

Theorem 3.1. Let $\mathcal { V } = \left( v _ { i j k l } \right)$ be a 4th order 2 dimensional symmetric tensor and let

$$
\begin{array} { r l } & { I = v _ { 1 1 1 1 } v _ { 2 2 2 2 } - 4 v _ { 1 1 1 2 } v _ { 1 2 2 2 } + 3 v _ { 1 2 2 1 } ^ { 2 } , } \\ & { J = v _ { 1 1 1 1 } v _ { 1 1 2 2 } v _ { 2 2 2 2 } + 2 v _ { 1 1 1 2 } v _ { 1 1 2 2 } v _ { 1 2 2 2 } - v _ { 1 1 2 2 } ^ { 3 } - v _ { 1 1 1 1 } v _ { 1 2 2 2 } ^ { 2 } - v _ { 1 1 1 2 } ^ { 2 } v _ { 2 2 2 2 } . } \end{array}
$$

Then $\nu$ is positive definite if and only if $v _ { 1 1 1 1 } > 0$ ， $v _ { 2 2 2 2 } > 0$ and

$$
\begin{array} { r l } & { ~ j ^ { 3 } - 2 7 J ^ { 2 } = 0 , ~ v _ { 1 1 1 2 } \sqrt { v _ { 2 2 2 2 } } = v _ { 1 2 2 2 } \sqrt { v _ { 1 1 1 1 } } , } \\ & { ~ v _ { 1 1 2 } ^ { 2 } + 2 v _ { 1 1 1 1 } \sqrt { v _ { 1 1 1 1 } v _ { 2 2 2 2 } } = 6 v _ { 1 1 1 1 } v _ { 1 1 2 2 } < 6 v _ { 1 1 1 1 } \sqrt { v _ { 1 1 1 1 } v _ { 2 2 2 2 } } ; } \end{array}
$$

$$
\begin{array} { r l } & { | v _ { 1 1 1 2 } \sqrt { v _ { 2 2 2 2 } } - v _ { 1 2 2 2 } \sqrt { v _ { 1 1 1 1 } } | \leq \sqrt { 6 v _ { 1 1 1 1 } v _ { 1 2 2 1 } v _ { 2 2 2 2 } + 2 \sqrt { ( v _ { 1 1 1 1 } v _ { 2 2 2 2 } ) ^ { 3 } } } , } \\ & { ( i ) - \sqrt { v _ { 1 1 1 1 } v _ { 2 2 2 2 } } \leq 3 v _ { 1 2 2 2 } \leq 3 \sqrt { v _ { 1 1 1 1 } v _ { 2 2 2 2 } } ; } \\ & { ( i i ) ~ v _ { 1 2 2 1 } > \sqrt { v _ { 1 1 1 1 } v _ { 2 2 2 2 } } \ a n d } \\ & { | v _ { 1 1 1 2 } \sqrt { v _ { 2 2 2 2 } } + v _ { 1 2 2 2 } \sqrt { v _ { 1 1 1 1 } } | \leq \sqrt { 6 v _ { 1 1 1 1 } v _ { 1 2 2 1 } v _ { 2 2 2 2 } - 2 \sqrt { ( v _ { 1 1 1 1 } v _ { 2 2 2 2 } ) ^ { 3 } } } . } \end{array}
$$

Proof. Let a vector $\boldsymbol { x } = ( x _ { 1 } , x _ { 2 } ) ^ { \top }$ be on the unit sphere,

$$
\| x \| = { \sqrt { x _ { 1 } ^ { 2 } + x _ { 2 } ^ { 2 } } } = 1 { \mathrm { ~ a n d ~ } } x _ { i } \in \mathbb { R } { \mathrm { ~ f o r ~ } } i = 1 , 2 .
$$

Without loss of generality, we may assume $x _ { 2 } \neq 0$ . For a vector $\boldsymbol { x } = ( x _ { 1 } , x _ { 2 } ) ^ { \top }$ ， we have

$$
\begin{array} { r l } {  { \mathcal { V } x ^ { 4 } = \sum _ { i , j , k , l = 1 } ^ { 2 } v _ { i j k l } x _ { i } x _ { j } x _ { k } x _ { l } } } \\ & { = v _ { 1 1 1 1 } x _ { 1 } ^ { 4 } + 4 v _ { 1 1 1 2 } x _ { 1 } ^ { 3 } x _ { 2 } + 6 v _ { 1 1 2 2 } x _ { 1 } ^ { 2 } x _ { 2 } ^ { 2 } + 4 v _ { 1 2 2 2 } x _ { 1 } x _ { 2 } ^ { 3 } + v _ { 2 2 2 2 } x _ { 2 } ^ { 4 } , } \end{array}
$$

and hence,

$$
\frac { \gamma _ { X } ^ { 4 } } { x _ { 2 } ^ { 4 } } = v _ { 1 1 1 1 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) ^ { 4 } + 4 v _ { 1 1 1 2 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) ^ { 3 } + 6 v _ { 1 1 2 2 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) ^ { 2 } + 4 v _ { 1 2 2 2 } \left( \frac { x _ { 1 } } { x _ { 2 } } \right) + v _ { 2 2 2 2 } .
$$

Clearly, $\mathbf { V } x ^ { 4 } > 0$ if and only if

$$
P ( t ) = a t ^ { 4 } + b t ^ { 3 } + c t ^ { 2 } + d t + e > 0
$$

with

$$
a = v _ { 1 1 1 1 } , \ b = 4 v _ { 1 1 1 2 } , \ c = 6 v _ { 1 1 2 2 } , \ d = 4 v _ { 1 2 2 2 } , \ e = v _ { 2 2 2 2 } .
$$

Then

$$
\begin{array} { r l } & { \Delta = 4 ( 1 2 a e - 3 b d + c ^ { 2 } ) ^ { 3 } - ( 7 2 a c e + 9 b c d - 2 c ^ { 3 } - 2 7 a d ^ { 2 } - 2 7 b ^ { 2 } e ) ^ { 2 } } \\ & { \quad = 4 ( 1 2 v _ { 1 1 1 1 } v _ { 2 2 2 2 } - 4 8 v _ { 1 1 1 2 } v _ { 1 2 2 2 } + 3 6 v _ { 1 1 2 2 } ^ { 2 } ) ^ { 3 } - ( 7 2 \times 6 v _ { 1 1 1 1 } v _ { 1 1 2 2 } v _ { 2 2 2 2 } } \\ & { \quad \quad + 7 2 \times 1 2 v _ { 1 1 1 2 } v _ { 1 1 2 2 } v _ { 1 2 2 2 } - 7 2 \times 6 v _ { 1 1 2 2 } ^ { 3 } - 7 2 \times 6 v _ { 1 1 1 1 } v _ { 1 2 2 2 } ^ { 2 } } \\ & { \quad \quad - 7 2 \times 6 v _ { 1 1 1 2 } ^ { 2 } v _ { 2 2 2 2 } ) ^ { 2 } } \\ & { \quad = 4 \times 1 2 ^ { 3 } ( I ^ { 3 } - 2 7 J ^ { 2 } ) , } \end{array}
$$

and hence, the sign of $\Delta$ is the same as one of $( I ^ { 3 } - 2 7 J ^ { 2 } )$ . So, it follows from Lemma 2.3 that the expected conclusions are obtained by simply calculating

Using similar proof technique, the following result is easy to be showed by Lemma 2.3. This is a repetitive work, we omit its proof.

Theorem 3.2. $A$ 4th order 2 dimensional symmetric tensor $\mathcal { V } = \left( v _ { i j k l } \right)$ with （20 $v _ { 1 1 1 1 } > 0$ and $v _ { 2 2 2 2 } > 0$ is positive semi-definite if and only if $I ^ { 3 } - 2 7 J ^ { 2 } \ge 0$ ， $\begin{array} { r l } & { | v _ { 1 1 1 2 } \sqrt { v _ { 2 2 2 2 } } - v _ { 1 2 2 2 } \sqrt { v _ { 1 1 1 1 } } | \leq \sqrt { 6 v _ { 1 1 1 1 } v _ { 1 2 2 1 } v _ { 2 2 2 2 } + 2 \sqrt { ( v _ { 1 1 1 1 } v _ { 2 2 2 2 2 } ) ^ { 3 } } } , } \\ & { ( i ) - \sqrt { v _ { 1 1 1 1 } v _ { 2 2 2 2 } } \leq 3 v _ { 1 2 2 2 } \leq 3 \sqrt { v _ { 1 1 1 1 } v _ { 2 2 2 2 } } ; } \\ & { ( i i ) ~ v _ { 1 2 2 1 } > \sqrt { v _ { 1 1 1 1 } v _ { 2 2 2 2 } } ~ a n d } \\ & { | v _ { 1 1 1 2 } \sqrt { v _ { 2 2 2 2 } } + v _ { 1 2 2 2 } \sqrt { v _ { 1 1 1 1 } } | \leq \sqrt { 6 v _ { 1 1 1 1 } v _ { 1 2 2 1 } v _ { 2 2 2 2 } - 2 \sqrt { ( v _ { 1 1 1 1 } v _ { 2 2 2 2 } ) ^ { 3 } } } . } \end{array}$

Next we give an analytically necessary and sufficient condition of the vacuum stability of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 2 }$ in particle physics. The most general scalar potential of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 2 }$ can be written as

$$
\bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) = \lambda _ { 4 0 } \phi _ { 1 } ^ { 4 } + \lambda _ { 3 1 } \phi _ { 1 } ^ { 3 } \phi _ { 1 } + \lambda _ { 2 2 } \phi _ { 1 } ^ { 2 } \phi _ { 2 } ^ { 2 } + \lambda _ { 1 3 } \phi _ { 1 } \phi _ { 2 } ^ { 3 } + \lambda _ { 0 4 } \phi _ { 2 } ^ { 4 } = \mathcal { V } \phi ^ { 4 } ,
$$

where $\boldsymbol { \nu } _ { } ~ = ~ ( v _ { i j k l } )$ is the coupling tensor and $\phi ~ = ~ ( \phi _ { 1 } , \phi _ { 2 } ) ^ { \top }$ is the vector of fields (Kannike [30-32]). In fact, the vacuum stability of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 2 }$ is equivalent to the positive definitnness of the coupling tensor $\mathcal { V } = \left( v _ { i j k l } \right)$ with its entries

$$
v _ { 1 1 1 1 } = \lambda _ { 4 0 } , ~ v _ { 2 2 2 2 } = \lambda _ { 0 4 } , ~ v _ { 1 1 1 2 } = \frac 1 4 \lambda _ { 3 1 } , ~ v _ { 1 1 2 2 } = \frac 1 6 \lambda _ { 2 2 } , ~ v _ { 1 2 2 2 } = \frac 1 4 \lambda _ { 1 3 } .
$$

Then we have

$$
\begin{array} { r l r } {  { \Delta = 4 \big ( 1 2 \lambda _ { 4 0 } \lambda _ { 0 4 } - 3 \lambda _ { 3 1 } \lambda _ { 1 3 } + \lambda _ { 2 2 } ^ { 2 } \big ) ^ { 3 } } } \\ & { } & { - \big ( 7 2 \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } + 9 \lambda _ { 3 1 } \lambda _ { 2 2 } \lambda _ { 3 1 } - 2 \lambda _ { 2 2 } ^ { 3 } - 2 7 \lambda _ { 4 0 } \lambda _ { 1 3 } ^ { 2 } - 2 7 \lambda _ { 3 1 } ^ { 2 } \lambda _ { 0 4 } \big ) ^ { 2 } \mathrm { . } } \end{array}
$$

Then from Theorem 3.1 (or Lemma 2.3), the following result is easy to obtain.

Theorem 3.3. $\bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) = \mathcal { V } \phi ^ { 4 } > 0$ for all $\phi = ( \phi _ { 1 } , \phi _ { 2 } ) ^ { \top } \in \mathbb { R } ^ { 2 } / \{ 0 \}$ if and only if $\lambda _ { 4 0 } > 0 , \ \lambda _ { 0 4 } > 0$ and

$$
\begin{array} { r l } & { \Delta = 0 , \ \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } = \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } , } \\ & { \lambda _ { 3 1 } ^ { 2 } + 8 \lambda _ { 4 0 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } = 4 \lambda _ { 4 0 } \lambda _ { 2 2 } < 2 4 \lambda _ { 4 0 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } ; } \\ & { \Delta > 0 , \ \left| \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } - \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } \right| \leq 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } + 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } , } \\ & { \left( i \right) - 2 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } \leq \lambda _ { 2 2 } \leq 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } ; } \\ & { \left( i \right) \lambda _ { 2 2 } > 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } \ a n d \ } \\ & { \left| \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } + \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } \right| \leq 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } - 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } . } \end{array}
$$

In fact, these analytical conditions are the vacuum stability conditions for the potential (3.1) of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 1 }$ ：

# 3.2 4th order 3 dimensional symmetric tensors

The most general scalar potential of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 2 }$ and the Higgs doublet $\mathbf { H }$ (Kannike [30-32]） is

$$
\begin{array} { c } { { V ( \phi _ { 1 } , \phi _ { 2 } , | H | ) = \lambda _ { H } | H | ^ { 4 } + \lambda _ { H 2 0 } | H | ^ { 2 } \phi _ { 1 } ^ { 2 } + \lambda _ { H 1 1 } | H | ^ { 2 } \phi _ { 1 } \phi _ { 2 } + \lambda _ { H 0 2 } | H | ^ { 2 } \phi _ { 2 } ^ { 2 } } } \\ { { + \lambda _ { 4 0 } \phi _ { 1 } ^ { 4 } + \lambda _ { 3 1 } \phi _ { 1 } ^ { 3 } \phi _ { 2 } + \lambda _ { 2 2 } \phi _ { 1 } ^ { 2 } \phi _ { 2 } ^ { 2 } + \lambda _ { 1 3 } \phi _ { 1 } \phi _ { 2 } ^ { 3 } + \lambda _ { 0 4 } \phi _ { 2 } ^ { 4 } , } } \\ { { = \lambda _ { H } | H | ^ { 4 } + M ( \phi _ { 1 } , \phi _ { 2 } ) | H | ^ { 2 } + \bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) , } } \end{array}
$$

where

$$
M ( \phi _ { 1 } , \phi _ { 2 } ) = \lambda _ { H 2 0 } \phi _ { 1 } ^ { 2 } + \lambda _ { H 1 1 } \phi _ { 1 } \phi _ { 2 } + \lambda _ { H 0 2 } \phi _ { 2 } ^ { 2 }
$$

and

$$
\bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) = V ( \phi _ { 1 } , \phi _ { 2 } , 0 ) = \lambda _ { 4 0 } \phi _ { 1 } ^ { 4 } + \lambda _ { 3 1 } \phi _ { 1 } ^ { 3 } \phi _ { 2 } + \lambda _ { 2 2 } \phi _ { 1 } ^ { 2 } \phi _ { 2 } ^ { 2 } + \lambda _ { 1 3 } \phi _ { 1 } \phi _ { 2 } ^ { 3 } + \lambda _ { 0 4 } \phi _ { 2 } ^ { 4 } .
$$

Recently, Kannike [30,31] studied the positive definiteness of $V ( \phi _ { 1 } , \phi _ { 2 } , | H | )$ and gave a sufficient condition of $V ( \phi _ { 1 } , \phi _ { 2 } , | H | ) > 0$ ：

In this subsection, we will present a necessary and sufficient condition of positive definiteness for the particle physical models (3.3).

Let $x = ( \phi _ { 1 } , \phi _ { 2 } , | H | ) ^ { \top }$ . Then $V ( \phi _ { 1 } , \phi _ { 2 } , | H | ) = \mathcal { V } x ^ { 4 }$ ，where $\mathcal { V } = \left( v _ { i j k l } \right)$ isa 4th order 3 dimensional symmetric tensor with its entries

$$
\begin{array} { l } { { v _ { 1 1 1 1 } = \lambda _ { 4 0 } , v _ { 2 2 2 2 } = \lambda _ { 0 4 } , v _ { 3 3 3 3 } = \lambda _ { H } , v _ { 1 1 1 2 } = \displaystyle \frac { 1 } { 4 } \lambda _ { 3 1 } , v _ { 1 2 2 2 } = \frac { 1 } { 4 } \lambda _ { 1 3 } , } } \\ { { v _ { 1 1 3 3 } = \displaystyle \frac { 1 } { 6 } \lambda _ { H 2 0 } , v _ { 1 1 2 2 } = \displaystyle \frac { 1 } { 6 } \lambda _ { 2 2 } , v _ { 2 2 3 3 } = \displaystyle \frac { 1 } { 6 } \lambda _ { H 0 2 } , } } \\ { { v _ { 1 2 3 3 } = \displaystyle \frac { 1 } { 1 2 } \lambda _ { H 1 1 } , v _ { i j k l } = 0 \mathrm { ~ f o r ~ t h e ~ o t h e r s } . } } \end{array}
$$

Clearly, the tensor given by $\bar { V } ( \phi _ { 1 } , \phi _ { 2 } )$ is a 4th order 2 dimensional principal sub-tensor of $\nu$

Theorem 3.4. Let $\mathcal { V } = \left( v _ { i j k l } \right)$ be a 4th order 3 dimensional symmetric tensor given by (3.6) with $\lambda _ { H } > 0$ . Then $\nu$ is positive (semi-)definite if and only if for all $\phi = ( \phi _ { 1 } , \phi _ { 2 } ) ^ { \top } \in \mathbb { R } ^ { 2 } / \{ 0 \}$

(1） $M ( \phi _ { 1 } , \phi _ { 2 } ) \geq 0$ and $\bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) > 0 \ ( \ge 0 )$ (2) $M ( \phi _ { 1 } , \phi _ { 2 } ) < 0 \ a n d \ 4 \lambda _ { H } \bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) - ( M ( \phi _ { 1 } , \phi _ { 2 } ) ) ^ { 2 } > 0 \ ( \geq 0 ) ,$

where $M ( \phi _ { 1 } , \phi _ { 2 } )$ and $\bar { V } ( \phi _ { 1 } , \phi _ { 2 } )$ are respectively defined dy (3.4) and (3.5).

Proof. Let $x = ( x _ { 1 } , x _ { 2 } , x _ { 3 } ) ^ { \top } = ( \phi _ { 1 } , \phi _ { 2 } , | H | ) ^ { \top }$ . It follows from the equations (3.3) and (3.6) that

$$
\mathcal V x ^ { 4 } = \lambda _ { H } | H | ^ { 4 } + M ( \phi _ { 1 } , \phi _ { 2 } ) | H | ^ { 2 } + \bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) .
$$

Which may be regarded as a quadratic polynomial with respect to $| H | ^ { 2 }$ with

$$
a = \lambda _ { H } , \ b = M ( \phi _ { 1 } , \phi _ { 2 } ) , \ c = \bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) , \ t = | H | ^ { 2 } .
$$

So the expected conclusions are yielded by Lemma 2.2.

It is obvious that $M ( \phi _ { 1 } , \phi _ { 2 } )$ is a quadric form with respect to two variables $\phi _ { 1 } , \phi _ { 2 }$ ,and hence, the inequality $M ( \phi _ { 1 } , \phi _ { 2 } ) \ge 0$ is equivalent to positive semidefiniteness of its coefficient matrix. That is,

$$
\lambda _ { H 2 0 } \geq 0 , \ \lambda _ { H 0 2 } \geq 0 , \ \lambda _ { H 2 0 } \lambda _ { H 0 2 } - \frac { 1 } { 4 } \lambda _ { H 1 1 } ^ { 2 } \geq 0 .
$$

Similarly, the inequality $M ( \phi _ { 1 } , \phi _ { 2 } ) < 0$ is equivalent to negative definiteness of its coeffcient matrix, i.e.,

$$
\lambda _ { H 2 0 } < 0 , \lambda _ { H 0 2 } < 0 , \lambda _ { H 2 0 } \lambda _ { H 0 2 } - \frac { 1 } { 4 } \lambda _ { H 1 1 } ^ { 2 } < 0 .
$$

At the same time, the inequality $\bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) > 0$ can be obtained by Theorem 3.3. Let

$$
\begin{array} { r l } & { \lambda _ { 4 0 } ^ { \prime } = 4 \lambda _ { 4 0 } \lambda _ { H } - \lambda _ { H 2 0 } ^ { 2 } , \ \lambda _ { 0 4 } ^ { \prime } = 4 \lambda _ { 0 4 } \lambda _ { H } - \lambda _ { H 0 2 } ^ { 2 } , } \\ & { \lambda _ { 3 1 } ^ { \prime } = 4 \lambda _ { H } \lambda _ { 3 1 } - 2 \lambda _ { H 2 0 } \lambda _ { H 1 1 } , \ \lambda _ { 1 3 } ^ { \prime } = 4 \lambda _ { H } \lambda _ { 1 3 } - 2 \lambda _ { H 0 2 } \lambda _ { H 1 1 } , } \\ & { \lambda _ { 2 2 } ^ { \prime } = 4 \lambda _ { H } \lambda _ { 2 2 } - 2 \lambda _ { H 2 0 } \lambda _ { H 0 2 } - \lambda _ { H 1 1 } ^ { 2 } , } \\ & { \Delta ^ { \prime } = 4 \big ( 1 2 \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } - 3 \lambda _ { 3 1 } ^ { \prime } \lambda _ { 1 3 } ^ { \prime } + \lambda _ { 2 2 } ^ { \prime 2 } \big ) ^ { 3 } } \\ & { \phantom { \lambda _ { 2 2 } ^ { \prime } = } - \big ( 7 2 \lambda _ { 4 0 } ^ { \prime } \lambda _ { 2 2 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } + 9 \lambda _ { 3 1 } ^ { \prime } \lambda _ { 2 2 } ^ { \prime } \lambda _ { 3 1 } ^ { \prime } - 2 \lambda _ { 2 2 } ^ { \prime 3 } - 2 7 \lambda _ { 4 0 } ^ { \prime } \lambda _ { 1 3 } ^ { \prime 2 } - 2 7 \lambda _ { 3 1 } ^ { \prime 2 } \lambda _ { 0 4 } ^ { \prime } \big ) ^ { 2 } . } \end{array}
$$

Now we present a necessary and sufficient condition of the inquality

$$
4 \lambda _ { H } \bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) - ( M ( \phi _ { 1 } , \phi _ { 2 } ) ) ^ { 2 } > 0 .
$$

Proposition 3.5. $\bar { \cal V } ^ { \prime } ( \phi _ { 1 } , \phi _ { 2 } ) \ = \ 4 \lambda _ { H } \bar { \cal V } ( \phi _ { 1 } , \phi _ { 2 } ) \ : - \ : ( M ( \phi _ { 1 } , \phi _ { 2 } ) ) ^ { 2 } \ > \ 0$ for all （204号 $\phi = ( \phi _ { 1 } , \phi _ { 2 } ) ^ { \top } \in \mathbb { R } ^ { 2 } / \{ 0 \}$ if and only if $\lambda _ { 4 0 } ^ { \prime } > 0 , \ \lambda _ { 0 4 } ^ { \prime } > 0$ and

$$
\begin{array} { r l } & { \Delta ^ { \prime } > 0 , \ | \lambda _ { 3 1 } ^ { \prime } \sqrt { \lambda _ { 0 4 } ^ { \prime } } - \lambda _ { 1 3 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } } | \leq 4 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 2 2 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } + 2 \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } } , } \\ & { ( i ) - 2 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } \leq \lambda _ { 2 2 } ^ { \prime } \leq 6 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } ; } \\ & { ( i i ) \ \lambda _ { 2 2 } ^ { \prime } > 6 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } \ a n d } \\ & { | \lambda _ { 3 1 } ^ { \prime } \sqrt { \lambda _ { 0 4 } ^ { \prime } } + \lambda _ { 1 3 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } } | \leq 4 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 2 2 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } - 2 \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } } . } \end{array}
$$

Proof. We may expand the polynomial $V ^ { \prime } ( \phi _ { 1 } , \phi _ { 2 } )$ as follow,

$$
\begin{array} { r l } & { \bar { V } ^ { \prime } ( \phi _ { 1 } , \phi _ { 2 } ) = 4 \lambda _ { H } \bar { V } ( \phi _ { 1 } , \phi _ { 2 } ) - ( M ( \phi _ { 1 } , \phi _ { 2 } ) ) ^ { 2 } } \\ & { \quad \quad \quad \quad = ( 4 \lambda _ { 4 0 } \lambda _ { H } - \lambda _ { H 2 0 } ^ { 2 } ) \phi _ { 1 } ^ { 4 } + ( 4 \lambda _ { H } \lambda _ { 3 1 } - 2 \lambda _ { H 2 0 } \lambda _ { H 1 1 } ) \phi _ { 1 } ^ { 3 } \phi _ { 2 } } \\ & { \quad \quad \quad \quad + ( 4 \lambda _ { H } \lambda _ { 2 2 } - 2 \lambda _ { H 2 0 } \lambda _ { H 0 2 } - \lambda _ { H 1 1 } ^ { 2 } ) \phi _ { 1 } ^ { 2 } \phi _ { 2 } ^ { 2 } } \\ & { \quad \quad \quad \quad \quad + ( 4 \lambda _ { H } \lambda _ { 1 3 } - 2 \lambda _ { H 0 2 } \lambda _ { H 1 1 } ) \phi _ { 1 } \phi _ { 2 } ^ { 3 } + ( 4 \lambda _ { 0 4 } \lambda _ { H } - \lambda _ { H 0 2 } ^ { 2 } ) \phi _ { 2 } ^ { 4 } } \\ & { \quad \quad \quad = \lambda _ { 4 0 } ^ { \prime } \phi _ { 1 } ^ { 4 } + \lambda _ { 3 1 } ^ { \prime } \phi _ { 1 } ^ { 3 } \phi _ { 2 } + \lambda _ { 2 2 } ^ { \prime } \phi _ { 1 } ^ { 2 } \phi _ { 2 } ^ { 2 } + \lambda _ { 1 3 } ^ { \prime } \phi _ { 1 } \phi _ { 2 } ^ { 3 } + \lambda _ { 0 4 } ^ { \prime } \phi _ { 2 } ^ { 4 } . } \end{array}
$$

So this definite a 4th order 2 dimensional symmetric tensor $\mathcal { V } = \left( v _ { i j k l } \right)$ with its entries

$$
v _ { 1 1 1 1 } = \lambda _ { 4 0 } ^ { \prime } , ~ v _ { 2 2 2 2 } = \lambda _ { 0 4 } ^ { \prime } , ~ v _ { 1 1 1 2 } = \frac 1 4 \lambda _ { 3 1 } ^ { \prime } , ~ v _ { 1 1 2 2 } = \frac 1 6 \lambda _ { 2 2 } ^ { \prime } , ~ v _ { 1 2 2 2 } = \frac 1 4 \lambda _ { 1 3 } ^ { \prime } .
$$

From Theorem 3.1 or 3.3, the expected conclusions follow.

Altogether, we obtain a necessary and sufficient condition of positive definiteness for a special 4th order 3-dimension symmetric tensor defined by mathematical models in particle physics.

Theorem 3.6. A tensor $\mathcal { V } = \left( v _ { i j k l } \right)$ given by (3.6) is positive definite if and only if $\lambda _ { H } > 0$ and

(1) $\lambda _ { H 2 0 } \ge 0 , \ \lambda _ { H 0 2 } \ge 0 , \ 4 \lambda _ { H 2 0 } \lambda _ { H 0 2 } - \lambda _ { H 1 1 } ^ { 2 } \ge 0 , \ \lambda _ { 4 0 } > 0 , \ \lambda _ { 0 4 } > 0 \ d$ nd

$$
\begin{array} { r l } & { \cdot \sqrt { \pi \omega ^ { \circ } } = \textrm { - } \textrm { s } , \ \gamma \cdot \sigma , \ \cdot \sigma , \cdot \ \sigma , \cdot \ \pi \omega ^ { \circ } \cdot \ \pi \omega ^ { \circ } \cdot \pi \omega ^ { \circ } \ \cdot \sqrt { \hdots } \ \textrm { s } \mu _ { 1 } = \textrm { - } \textrm { s } , \ \gamma \cdot \ q \circ \textrm { - } \textrm { s } , \ \gamma \circ \textrm { s } \omega } \\ & { \textcircled { 1 } \ \Delta = 0 , \ \ \wedge \ \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } = \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } , } \\ & { \lambda _ { 3 1 } ^ { 2 } + 8 \lambda _ { 4 0 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } = 4 \lambda _ { 4 0 } \lambda _ { 2 2 } < 2 4 \lambda _ { 4 0 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } ; } \\ & { \textcircled { 2 } \ \Delta > 0 , \ \left| \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } - \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } \right| \leq 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } + 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } , } \\ & { \left( i \right) - 2 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } \leq \lambda _ { 2 2 } \leq 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } ; } \\ & { \left( i i \right) \lambda _ { 2 2 } > 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } a n d } \\ & { \left| \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } + \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } \right| \leq 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } - 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } . } \end{array}
$$

(2） $\lambda _ { H 2 0 } < 0 , \lambda _ { H 0 2 } < 0 , 4 \lambda _ { H 2 0 } \lambda _ { H 0 2 } - \lambda _ { H 1 1 } ^ { 2 } < 0 ,$ （204号 $\lambda _ { 4 0 } ^ { \prime } = 4 \lambda _ { 4 0 } \lambda _ { H } - \lambda _ { H 2 0 } ^ { 2 } > 0 , \ \lambda _ { 0 4 } ^ { \prime } = 4 \lambda _ { 0 4 } \lambda _ { H } - \lambda _ { H 0 2 } ^ { 2 } > 0$ and

$$
\begin{array} { r l } & { \begin{array} { r l } { \textcircled { 3 } } & { \Delta ^ { \prime } = 0 , \ \lambda _ { 3 1 } ^ { \prime } \sqrt { \lambda _ { 0 4 } ^ { \prime } } = \lambda _ { 1 3 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } } , } \\ & { \lambda _ { 3 1 } ^ { \prime 2 } + 8 \lambda _ { 4 0 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } = 4 \lambda _ { 4 0 } ^ { \prime } \lambda _ { 2 2 } ^ { \prime } < 2 4 \lambda _ { 4 0 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } ; } \end{array} } \\ & { \begin{array} { r l } { \textcircled { 4 } } & { \Delta ^ { \prime } > 0 , \ | \lambda _ { 3 1 } ^ { \prime } \sqrt { \lambda _ { 0 4 } ^ { \prime } } - \lambda _ { 1 3 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } } | \leq 4 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 2 2 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } + 2 \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } } , } \\ & { ( i ) - 2 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } \leq \lambda _ { 2 2 } ^ { \prime } \leq 6 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } ; } \end{array} } \\ &  \begin{array} { r l } { ( i i ) \ \lambda _ { 2 2 } ^ { \prime } > 6 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } a n d } & { \lambda _ { 3 1 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 2 2 } ^ { \prime } } < 2 4 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 2 4 } ^ { \prime } } - 2 \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } . } \end{array} \end{array}
$$

Moreover, these analytical conditions are the vacuum stability conditions for the potential (3.3) of two real scalar fields $\phi _ { 1 }$ and $\phi _ { 1 }$ and the Higgs doublet H also.

Theorem 3.7. A tensor $\mathcal { V } = \left( v _ { i j k l } \right)$ given by (3.6) with $\lambda _ { H } > 0$ ， $\lambda _ { 4 0 } > 0$ and $\lambda _ { 0 4 } > 0$ is positive semi-definite if and only if

$$
\begin{array} { r l } & { \lambda _ { H 2 0 } \geq 0 , \ \lambda _ { H 0 2 } \geq 0 , \ 4 \lambda _ { H 2 0 } \lambda _ { H 0 2 } - \lambda _ { H 1 1 } ^ { 2 } \geq 0 \ a n d } \\ & { \Delta \geq 0 , \ | \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } - \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } | \leq 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } + 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } , } \\ & { ( i ) - 2 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } \leq \lambda _ { 2 2 } \leq 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } ; } \\ & { ( i i ) \ \lambda _ { 2 2 } > 6 \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } \ a n d \ } \\ & { | \lambda _ { 3 1 } \sqrt { \lambda _ { 0 4 } } + \lambda _ { 1 3 } \sqrt { \lambda _ { 4 0 } } | \leq 4 \sqrt { \lambda _ { 4 0 } \lambda _ { 2 2 } \lambda _ { 0 4 } - 2 \lambda _ { 4 0 } \lambda _ { 0 4 } \sqrt { \lambda _ { 4 0 } \lambda _ { 0 4 } } } . } \end{array}
$$

$$
\begin{array} { r l } & { \lambda _ { H 2 0 } < 0 , \lambda _ { H 0 2 } < 0 , 4 \lambda _ { H 2 0 } \lambda _ { H 0 2 } - \lambda _ { H 1 1 } ^ { 2 } < 0 , \lambda _ { 4 0 } ^ { \prime } > 0 , \lambda _ { 0 4 } ^ { \prime } > 0 \mathrm { ~ } ] } \\ & { \Delta ^ { \prime } \geq 0 , | \lambda _ { 3 1 } ^ { \prime } \sqrt { \lambda _ { 0 4 } ^ { \prime } } - \lambda _ { 1 3 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } } | \leq 4 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 2 2 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } + 2 \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } } , } \\ & { ( i ) - 2 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } \leq \lambda _ { 2 2 } ^ { \prime } \leq 6 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } ; } \\ & { ( i i ) \lambda _ { 2 2 } ^ { \prime } > 6 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } a n d } \\ & { | \lambda _ { 3 1 } ^ { \prime } \sqrt { \lambda _ { 0 4 } ^ { \prime } } + \lambda _ { 1 3 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } } | \leq 4 \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 2 2 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } - 2 \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } \sqrt { \lambda _ { 4 0 } ^ { \prime } \lambda _ { 0 4 } ^ { \prime } } } . } \end{array}
$$

Remark 3.1. In this paper， we showed an analytically necessary and sufficient condition of positive definiteness for a special 4th order 3-dimension symmetric tensor defined by mathematical models in particle physics with the help of the analytical expressions of positive definiteness for 4th order 2-dimension symmetric tensors. However, we do not still know how to solve an analytical expressions of positive definiteness for a general 4th order 3- dimension symmetric real tensor or higher dimensional tensor.

# References

[1] de Adelhart Toorop, R., Bazzocchi, F., Merlo, L., Paris, A.: Constraining flavour symmetries at the EW scale I: the A4 Higgs potential, J. High Energ. Phys. 1103, 035 (2011)   
[2] de Adelhart Toorop, R., Bazzocchi, F.， Merlo,L.and Paris,A.: Erratum: constraining flavour symmetries at the EW scale I: the A4 Higgs potential. J. High Energ. Phys. 1301, 98 (2013)   
[3] Belanger, G., Kannike, K., Pukhov, A., Raidal, M.: Impact of semi- annihilations on dark matter phenomenology An example of $\mathbb { Z } _ { N }$ symmetric scalar dark matter. J. Cosmol. Astropart. Phys. 1204, O10 (2012)   
[4] Belanger,G.， Kannike, K.， Pukhov,A.， Raidal, M.: Minimal semiannihilating $\mathbb { Z } _ { N }$ scalar dark matter. J. Cosmol. Astropart. Phys. 1406, 021 (2014)   
[5] Chen, H., Qi, L.: Positive definiteness and semidefiniteness of even order symmetric Cauchy tensors. J Ind Manag Optim, 2015,11: 1263-1274   
[6] Chen, H., Wang, Y., High-order copositive tensors and its applications, J. Appl. Anal. Compu. 8(6)(2018) 1863-1885   
[7] Chen, H., Li, G., Qi, L.: SOS Tensor decomposition: Theory and application. Commun Math Sci, 2016,14(8) 2073-2100   
[8] Chen, L., Han, L., Zhou, L.: Computing tensor eigenvalues via homotopy methods. SIAM J. Matrix Anal. Appl., 37(1)(2016), 290-319   
[9] Chen，Y.，Qi, L.， Wang，Q.: Positive semi-definiteness and sum-ofsquares property of fourth order four dimensional Hankel tensors. J Comput Appl Math, 2016,302: 356-368   
[10] Chen, Z.， Qi, L.， Yang, Q.， Yang, Y.: The solution methods for the largest eigenvalue (singular value) of nonnegative tensors and convergence analysis. Linear Algebra Appl, 2013, 439: 3713-3733   
[11] Cui, C.，Dai, Y.， Nie, J.: All real eigenvalues of symmetric tensors. SIAM J Matrix Anal Appl, 2014, 35: 1582-1601   
[12] A. Degee, I. P. Ivanov and V. Keus, Geometric minimization of highly symmetric potentials, J. High Energ. Phys.1302,125 (2013)   
[13] Ding, W., Luo, Z., Qi, L.: P-tensors, P $_ 0$ -tensors,and their applications. Linear Algebra Appl. 555(2018) 336-354   
[14] Ding, W., Qi, L., Wei, Y.: M-tensors and nonsingular M-tensors. Linear Algebra Appl, 2013, 439: 3264-3278   
[15] Faro, F.S., Ivanov, I.P.: Boundedness from below in the $U ( 1 ) \times U ( 1 )$ （204号 three-Higgs-doublet model. Phys.Rev.D. 100, 035-038 (2019)   
[16] Fu, M.: Comments on “A procedure for the positive definiteness of forms of even order", IEEE Trans.Auto. Control, 43(10) 1430（1998)   
[17] Gadem， R.N.， Li, C.C.: On positive definiteness of quartic forms of twovariables, IEEE Trans. Auromat. Conrr., AC-9(1964) 187-188   
[18] Guo,Y.: A necessary and sufficient condition for the positive definite problem of a binary quartic form，arXiv:2009.01033 [math.AG] 2 Sep 2020   
[19] Hasan, M. A., Hasan,A. A.: A procedure for the positive definiteness of forms of even order, IEEE Trans. Auto. Control, 41(4) 615-617 (1996)   
[20] Han,L.: An unconstrained optimization approach for finding real eigenvalues of even order symmetric tensors. Numer Algebra Control Optim, 2013, 3: 583-599   
[21] Hao, C., Cui, C., Dai, Y.: A sequential subspace projection method for extreme Z-eigenvalues of supersymmetric tensors. Numer Linear Algebra Appl, 2015, 22: 283-298   
[22] Hao, C., Cui, C., Dai, Y.: A feasible trust-region method for calculating extreme Z-eigenvalues of symmetric tensors. Pac. J Optim， 2015，11: 291-307   
[23] Hu, S., Li, G., Qi, L., Song, Y.: Finding the maximum eigenvalue of essentially nonnegative symmetric tensors via sum of squares programming. J Optim Theory Appl, 2013, 158: 717-738   
[24] Ishimori,H.，Kobayashi,T.,Ohki,H.,Shimizu,Y., Okada,H., Tanimoto,M.: Non-Abelian Discrete Symmetries in Particle Physics, Prog. Theor. Phys. Suppl. 183, 1-163 (2010)   
[25] Ivanov， Igor P.，Vdovin，E.: Discrete symmetries in the three-Higgsdoublet model, Phys. Rev. D 86, 095030 (2012) arXiv:1206.7108   
[26] Ivanov， Igor P.，Vdovin， E.: Classification of finite reparametrization symmetry groups in the three-Higgs-doublet model, Eur. Phys. J. C 73, no.2, 2309 (2013)   
[27] Ivanov, Igor P., Francisco Vazao, Yet another lesson on the stability conditions in multi-Higgs potentials,arXiv:2006.00036v1 [hep-ph] 29 May 2020   
[28] Ivanov, I.P.， Kopke， M.， Muhlleitner， M.: Algorithmic boundednessfrom-below conditions for generic scalar potentials. Eur. Phys. J. C.(2018) 78: 413   
[29] Jury, E.I., Mansour, M.: Positivity and nonnegativity of a quartic equation and related problems，IEEE Trans. Automat.Control， 26(1981) 444-451   
[30] Kannike, K.: Vacuum stability of a general scalar potential of a few fields, Eur. Phys. J. C(2016) 76: 324   
[31] Kannike, K.: Erratum to: Vacuum stability of a general scalar potential of a few fields, Eur. Phys. J. C(2018) 78: 355   
[32] Kannike, K.: Vacuum stability conditions from copositivity criteria, Eur. Phys. J. C(2012) 72: 2093   
[33] Ku, W.H.: Explicit criterion for the positive definiteness of a general quartic form,IEEE Tram. Automat. Conrr.. AC-IO(3)(1965) 372-373   
[34] Li, L.， Zhang，X.， Huang, Z.， Qi, L.: Test of copositive tensors, J. Industrial Manag. Optim. April 2019, 15(2): 881-891   
[35] Luo, Z. Y., Qi, L. Q.: Positive semidefinite tensors (in Chinese). Sci Sin Math,2016,46:639-654   
[36] Li, G., Qi, L.， Wang, Q.: Positive semi-definiteness of generalized anticircular tensors. Commun Math Sci, 2016,14: 941-952   
[37] Li, C., Qi, L.， Li, Y.: MB-tensors and MB $_ 0$ -tensors. Linear Algebra Appl, 2015, 484: 141-153   
[38] Liu, J.， Song， Y.: Copositivity for 3rd order symmetric tensors and applications,arXiv: 1911.10284 ChinaXiv: 201911.00094 23 November 2019   
[39] E. Ma and G. Rajasekaran, Softly broken $A _ { 4 }$ symmetry for nearly degenerate neutrino masses, Phys. Rev. D 64, 113012 (2001)   
[40] Nie, J., Zhang, X.: Real eigenvalues of nonsymmetric tensors. Comput Optim Appl (2018)   
[41] Ng，M.，Qi, L.， Zhou,G.: Finding the largest eigenvalue of a nonnegative tensor, SIAM J Matrix Anal Appl, 2009,31: 1090-1099   
[42] Ni, Q., Qi, L., Wang, F.: An eigenvalue method for testing the positive definiteness of a multivariate form. IEEE Trans. Auto. Control, 2008, 53:1096-1107   
[43] Qi, L.， Song，Y.， Zhang，X.: Copositivity of Three-Dimensional Symmetric Tensors, arXiv:2008.03998   
[44] Qi, L.， Song, Y., Zhang, X.: Positivity Conditions for Cubic, Quartic and Quintic Polynomials,arXiv:2008.10922   
[45] Qi, L.: Hankel tensors: Associated Hankel matrices and Vandermonde decomposition. Commun Math Sci, 2015,13:113-125   
[46] Qi, L.: Eigenvalues of a real supersymmetric tensor, J. Symbolic Comput. 40(2005) 1302-1324   
[47] Qi, L.: Symmetric Nonnegative Tensors and Copositive Tensors. Linear Algebra Appl. 439 (2013) 228-238   
[48] Qi, L., Chen, H., Chen, Y.: Tensor Eigenvalues and Their Applications, Springer Singapore, 2018   
[49] Qi, L., Luo, Z.: Tensor Analysis: Spectral Theory and Special Tensors. SIAM, Philadelpia 2017   
[50] Qi, L., Song, Y.: An even order symmetric B tensor is positive definite. Linear Algebra Appl, 2014, 457: 303-312   
[51] Song, Y., Qi, L.: Infinite and finite dimensional Hilbert tensors. Linear Algebra Appl, 2014, 451: 1-14   
[52] Song, Y., Qi, L.: Necessary and sufficient conditions of copositive tensors,Linear Multilinear Algebra. 63(1)(2015) 120-131   
[53] Song，Y.，Qi, L.: Properties of some classes of structured tensors, J. Optim. Theory Appl. 165(3)(2015) 854-873   
[54] Song，Y.，Qi,L.: Tensor complementarity problem and semi-positive tensors, J. Optim. Theory Appl. 169(2016) 1069-1078   
[55] Song，Y., Qi, L.: Eigenvalue analysis of constrained minimization problem for homogeneous polynomial, J. Glob. Optim. 64(3)(2016) 563-575   
[56] Song， Y., Yu, G.: Properties of solution set of tensor complementarity problem，J.Optim. Theory Appl. 170(2016) 85-96   
[57] Song, Y., Qi, L.: Strictly semi-positive tensors and the boundedness of tensor complementarity problems,Optim.Lett.11(2017) 1407-1426   
[58] Song，Y.， Qi, L.: Analytical expressions of copositivity for 4th order symmetric tensors and applications. Analysis and Applications, DOI: 10.1142/S0219530520500049   
[59] Wang，F.，Qi, L.: Comments on “Explicit criterion for the positive definiteness of a general quartic form", IEEE Trans. Auto. Control, 50(3) (2005) 416-418   
[60] Yuan, P.， You, L.: Some remarks on P, P $_ 0$ ， B and B $_ 0$ tensors. Linear Algebra Appl, 2014, 459: 511-521   
[61] Zhang, L., Qi, L., Luo, Z., Xu, Y.: The dominant eigenvalue of an essentially nonnegative tensor. Numer Linear Algebra Appl, 2O13, 20: 929-941   
[62] Zhang, L., Qi, L., Zhou, G.: M-tensors and some applications. SIAM J Matrix Anal Appl, 2014, 35: 437-452