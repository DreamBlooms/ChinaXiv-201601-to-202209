# Twisted sectors from plane partitions

Shouvik Datta&,Matthias R.Gaberdielα,Wei $\mathbf { L } \mathbf { \dot { \boldsymbol { \mathsf { I } } } }$ and Cheng Peng@

aInstitut fir Theoretische Physik, ETH Zurich, CH-8093 Zurich, Switzerland   
（20 $b$ Institute of Theoretical Physics, Chinese Academy of Science 100190 Beijing，P.R. China   
E-mail: shouvik@itp.phys.ethz.ch，gaberdiel@itp.phys.ethz.ch,   
weili@itp.ac.cn， pengch@itp.phys.ethz.ch

ABSTRACT: Twisted sectors arise naturally in the bosonic higher spin CFTs at their free points,as well as in the associated symmetric orbifolds. We identify the coset representations of the twisted sector states using the description of $\mathcal { W } _ { \infty }$ representations in terms of plane partitions. We confirm these proposals by a microscopic null-vector analysis,and by matching the excitation spectrum of these representations with the orbifold prediction.

# Contents

1Introduction 1

# 2The twisted sector in the free boson description 3

2.1 Wedge characters and their combinatorial interpretation 5   
2.2 Plane partition viewpoint 7   
2.3 The null-vector analysis 11   
2.4 The ground state conformal dimension and the excitation spectrum 14

# The twisted sector in the free fermion description 16

3.1The plane partition viewpoint 17   
3.2The ground state conformal dimension and the excitation spectrum 19

4Conclusions 21

A The general form of level-1 representations 22   
B The spin 3 charge of some simple representations 25   
C Combinatorial description of wedge characters 27

# 1Introduction

Massless higher spin theories can be constructed consistently on AdS backgrounds [1],and they are believed to describe a consistent subsector of string theory at the tensionless point [2-4]. Via the AdS/CFT duality, the tensionless limit of string theory corresponds, on the dual field theory side, to the limit in which the CFT becomes free, and the higher spin degrees of freedom correspond to those of a vector-like CFT. The AdS/CFT correspondence therefore predicts dualities between higher spin theories and vector-like CFTs, and explicit examples of such relations were first proposed for the case of AdS $^ 4$ /CFT $^ 3$ in [5,6], and more recently in one dimension lower in [7]. These dualities provide a useful approach towards analysing string theory at a very symmetrical point in its moduli space where many of its underlying symmetries are unbroken. They may also allow one to prove the AdS/CFT correspondence since they are weak-weak dualities.

In order to utilize the duality for either of these purposes it is important to understand the embedding of the higher spin AdS/CFT duality into the usual stringy AdS/CFT correspondence in detail. For the 4d/3d case, a proposal was made some time ago in [8], while for the case of AdS $_ 3$ /CFT $^ 2$ a somewhat different picture emerged in [9]. The CFT duals of string theory on Ads $\ S _ { 3 } \times \ S ^ { 3 } \times \mathbb { T } ^ { 4 }$ lie on the moduli space that contains the symmetric orbifold of $ { \mathbb { T } } ^ { 4 }$ , and the orbifold theory itself contains a vectorlike CFT as a closed subsector. In turn, this vector-like CFT was shown to emerge naturally in the CFT dual of the $\mathcal { N } = 4$ version [10] of the higher spin AdS/CFT duality. More specifically, the CFT dual of the higher spin theory is a subsector of the untwisted sector of the symmetric orbifold, and the entire untwisted sector can be understood in terms of a vastly extended higher spin symmetry, the so-called Higher Spin Square (HSS)， as well as its scalar feld excitations [11， 12], see also [13, 14] for related discussions. On the other hand, it has been more difficult to characterize the twisted sector of the symmetric orbifold from a higher spin perspective - see however [12,15,16] for first steps in this direction. This is an important problem if we want to use the higher spin perspective for the description of string theory at its highly symmetrical tensionless point.

The present work revisits the original bosonic duality of [7] in order to analyse the relevant twisted sectors from a higher spin perspective. The bosonic theory is a useful toy model since it exhibits all the essential features of the supersymmetric version. The identification of the twisted sectors in terms of coset representations was done before for the $\mathcal { N } = 2$ and $\mathcal { N } = 4$ cases [9, 17],， partially using the BPS condition as a guide, but the description in the bosonic case has so far not been worked out. In fact,the structure of the bosonic coset is somewhat different from that of the supersymmetric versions, and thus it was not clear how to generalize the results directly.

In this paper we attack this problem using a new tool that was recently discovered for the bosonic $\mathcal { W } _ { \infty }$ algebras. A few years ago it was shown in a series of papers [18-20] that the representation theory of the quantum toroidal algebra of ${ \mathfrak { g l } } _ { 1 }$ can be described in terms of plane partitions,and that the associated characters are,up to an overall $q$ -Pochhammer symbol, identical to those of the bosonic $\mathcal { W } _ { N , k }$ minimal models. More recently, Prochazka [21] realized that this gives rise to a powerful method to analyse the bosonic ${ \mathcal W } _ { \infty }$ representations. In particular, he showed that the triality symmetry of the $\mathcal { W } _ { \infty }$ algebra,which played an important role in establishing the duality [22], is inherent and manifest in the plane partition description. Finally, since quantum toroidal algebras are isomorphic to their corresponding affine Yangian algebras (after suitable completion) [23, 24], plane partitions also describe the representation theory of a Yangian algebra. On the other hand, Yangian algebras are one of the hallmarks of integrability,and hence this viewpoint may help us establish the precise connection between higher spin theories and integrable field theories proposed for AdS $^ 3$ in [25-27] (see [28] for a review).

The $\mathcal { N } = 4$ construction of [9] relates the Wolf space cosets to the symmetric orbifold (and hence to string theory) for the case where the cosets can be described in terms of free fields ( $\lambda = 0$ ). The free field constructions of the bosonic ${ \mathcal W } _ { \infty } [ \lambda ]$ algebras arise for $\lambda = 0$ and $\lambda = 1$ ，where they can be realized in terms of free fermions and bosons, respectively [29-33]. For the case of $\lambda = 0$ ，the free field realization of the coset model was already made fairly explicit in [34]，where the $k  \infty$ (i.e. $\lambda  0$ ） limit was described as a continuous orbifold. However, the precise description of the twisted sectors was not understood at the time - in general, the twisted sector of the orbifold is not directly accessible, even if one has a good understanding of the untwisted sector. In this paper we find the coset description of the twisted sectors both at the free fermion ( $\lambda = 0$ ）and the free boson point ( $\lambda = 1$ ).It is important to have both of these cases simultaneously under control since the extended higher spin symmetry algebra that is believed to arise in string theory, the Higher Spin Square (HSS),is in some sense a combination of both of these constructions [11]. The main technical advance of our analysis is the systematic use of the plane partition viewpoint advocated in [21], which enabled us to find the correct twisted sector representations. We also test our proposals using the techniques of [17].

The paper is organized as follows. We begin in Section 2 with a discussion of the bosonic theory corresponding to $\lambda = 1$ ，i.e. $N  \infty$ at fixed $k$ .We first find closed form expressions for the wedge characters of the twisted sectors，and then use the plane partition viewpoint to propose the form of the corresponding coset representations. This proposal is then tested in some detail: in Sections 2.3 the null-vector structure of the corresponding $\mathrm { { h s } } [ \lambda ]$ representations are studied from a microscopic viewpoint, i.e. by calculating the relevant Kac determinants, and in Section 2.4 the conformal dimension and excitation spectrum is computed in the coset and found to agree with the orbifold predictions; this also fixes the precise identification with the coset representations. In Section 3 the corresponding analysis is performed for the fermionic theory corresponding to $\lambda ~ = ~ 0$ .We end with a discussion on future directions in Section 4. There are three appendices where aspects of the null-vector analysis (Appendix A), the determination of the higher spin charges using the Drinfeld-Sokolov approach (Appendix B),and combinatorial identities that arise in the plane partition analysis (Appendix C) are explained in more detail.

# 2 The twisted sector in the free boson description

Weare interested in the cosets

$$
{ \frac { \mathfrak { s u } ( N ) _ { k } \oplus \mathfrak { s u } ( N ) _ { 1 } } { \mathfrak { s u } ( N ) _ { k + 1 } } } \ ,
$$

and we shall mainly be considering the ’t Hooft limit, where we take $N$ and $k$ to infinity, while keeping the ratio

$$
\lambda = \frac { N } { N + k }
$$

fixed. The case where we take $N  \infty$ first then corresponds to the theory at $\lambda = 1$ This limit theory can be described by a free boson construction, see e.g. [32, 33]. More specifically, for $k$ complex bosons $\phi ^ { i }$ and $\phi ^ { i }$ that transform in the fundamental and anti-fundamental representation of $\mathrm { U } ( k )$ ，respectively， we consider the chiral $\mathrm { U } ( k )$ singlets that are of the form

$$
W ^ { s } ( z ) = m ( s ) \sum _ { l = 1 } ^ { s - 1 } \frac { ( - 1 ) ^ { l } } { ( s - 1 ) } { \binom { s - 1 } { l } } { \binom { s - 1 } { s - l } } \partial ^ { l } \phi ^ { j } \partial ^ { s - l } \bar { \phi } ^ { j } ,
$$

where $m ( s )$ is an $s$ -dependent normalization constant. These currents then generate the $\mathcal { W } _ { \infty } [ 1 ]$ algebra with $c = 2 k$ . Formally, the $\lambda = 1$ theory can therefore be thought of as a continuous orbifold, where we divide the free boson theory by the orbifold group $\mathrm { U } ( k )$ ， see [34]. The theory should then also contain twisted sectors where the different complex bosons are twisted.

Note that some of these twisted sectors also appear in the symmetric orbifold where we divide the theory by the symmetric group $S _ { k + 1 } \subset \operatorname { U } ( k )$ ,under which the above currents are also invariant. (The full chiral algebra of the symmetric orbifold is then much bigger - it gives rise to the stringy extension of the $\mathcal { W } _ { \infty }$ [1] algebra that is associated to the so-called Higher Spin Square [11].） The analysis of the twisted sectors is therefore in particular relevant for the stringy embedding of the bosonic duality of [7].

In general, the coset interpretation of the twisted sectors cannot be deduced directly from the identification in the untwisted sector,and we shall therefore proceed indirectly. Let us first concentrate on the case where only one complex boson is twisted by $\nu$ with $0 < \nu < 1$ ; the twisted sector is then generated by

$$
\alpha _ { n - \nu } \qquad \mathrm { a n d } \qquad \bar { \alpha } _ { n + \nu } \qquad \mathrm { w i t h } \quad n \in \mathbb { Z } \ .
$$

The wedge character of the corresponding representation is given by [12]

$$
\chi _ { [ \nu ] } ( q , y ) = q ^ { h } \prod _ { n = 1 } ^ { \infty } ( 1 - y q ^ { n - 1 + \nu } ) ^ { - 1 } ( 1 - y ^ { - 1 } q ^ { n - \nu } ) ^ { - 1 } ,
$$

where the conformal dimension is $h = { \textstyle \frac { 1 } { 2 } } \nu ( 1 - \nu )$ . In the full orbifold theory, this chiral representation comes together with a corresponding anti-chiral representation， and on the full space (involving both chiral and anti-chiral twisted states) the invariance under the orbifold group is to be imposed. In particular, not just those states survive this orbifold projection that are separately invariant under the orbifold action; instead the correct condition is that the left-moving states transform in the conjugate representation to that of the right-moving states. The powers of $y$ keep track of the action under the cyclic group corresponding to the twist itself, and hence the states corresponding to a given fixed power of $y$ correspond to different representations of the hs[1] algebra,

$$
\chi _ { [ \nu ] } ^ { ( \ell ) } ( q ) \equiv \left. \chi _ { [ \nu ] } ( q , y ) \right| _ { y ^ { \ell } } ~ .
$$

In the following we shall identify the coset representations that describe these twisted sector states. We shall first use character considerations to make a proposal for the corresponding coset representation, see Sections 2.1 and 2.2. In Section 2.3 we study the representation corresponding to $\ell = 0$ using the commutation relations of the hs $[ \lambda ]$ algebra,and confirm in particular, that the representation we have identified in Section 2.1 leads to the correct eigenvalues for arbitrary $\lambda$ . (As will become clear in the following, these representations can also be defined for general $\lambda$ ； however， we do not have a direct interpretation in terms of an orbifold unless $\lambda = 1$ .)Finally, in Section 2.4， we confirm that the representations have the correct ground state conformal dimension and excitation spectrum.

# 2.1 Wedge characters and their combinatorial interpretation

In order to use the characters for determining the corresponding coset representations,we first compute the wedge characters defined in eq. (2.6). In particular, we want to find closed form expressions whose combinatorial interpretation can help us identify their corresponding plane partition configurations.

There are two factors in the wedge character (2.5)，corresponding to modes associated to $\phi$ and $\phi$ , respectively. Both of them resemble the refined version of the generating function of partition numbers defined by

$$
Z ( q , y ) = \prod _ { n = 1 } ^ { \infty } { \frac { 1 } { ( 1 - y q ^ { n } ) } } = \sum _ { m = 0 } ^ { \infty } y ^ { m } \sum _ { n = m } ^ { \infty } p ( n , m ) q ^ { n } ,
$$

where $p ( n , m )$ counts the number of Young diagrams which have $n$ boxes and whose height is $m$ . Summing over all Young diagrams with the same fixed height $m$ we have

$$
\sum _ { n = m } ^ { \infty } p ( n , m ) q ^ { n } = q ^ { m } \prod _ { n = 1 } ^ { m } \frac { 1 } { ( 1 - q ^ { n } ) } ~ .
$$

Expanding both factors in the wedge character $\chi _ { \left[ \nu \right] } ( q , y )$ as in (2.7) and (2.8) and collecting the coefficient of $y ^ { \ell }$ term, we obtain the expression for the wedge charactrs

$$
\chi _ { [ \nu ] } ^ { ( \ell ) } ( q ) = q ^ { h + \delta h ( \ell , \nu ) } \sum _ { m = 0 } ^ { \infty } q ^ { m } \prod _ { n = 1 } ^ { m + | \ell | } \frac { 1 } { ( 1 - q ^ { n } ) } \prod _ { n = 1 } ^ { m } \frac { 1 } { ( 1 - q ^ { n } ) } ,
$$

where

$$
\delta h ( \ell , \nu ) = \left\{ \begin{array} { c l } { { \ell \nu } } & { { \qquad \ell \ge 0 } } \\ { { \ell ( \nu - 1 ) } } & { { \qquad \ell < 0 \ . } } \end{array} \right.
$$

corresponds to the excitation spectrum，and $\ell$ enters the combinatorial part of the character only as $| \ell |$ . The explicit $q$ -expansions of the first few values of $| \ell |$ are

$$
\begin{array} { l } { { \chi _ { [ \nu ] } ^ { ( 0 ) } ( q ) = q ^ { h } \bigl ( 1 + q + 3 q ^ { 2 } + 6 q ^ { 3 } + 1 2 q ^ { 4 } + 2 1 q ^ { 5 } + 3 8 q ^ { 6 } + 6 3 q ^ { 7 } + \cdots \bigr ) } } \\ { { \chi _ { [ \nu ] } ^ { ( 1 ) } ( q ) = q ^ { h + \nu } \bigl ( 1 + 2 q + 4 q ^ { 2 } + 8 q ^ { 3 } + 1 5 q ^ { 4 } + 2 7 q ^ { 5 } + 4 7 q ^ { 6 } + 7 9 q ^ { 7 } + \cdots \bigr ) } } \\ { { \chi _ { [ \nu ] } ^ { ( 2 ) } ( q ) = q ^ { h + 2 \nu } \bigl ( 1 + 2 q + 5 q ^ { 2 } + 9 q ^ { 3 } + 1 8 q ^ { 4 } + 3 1 q ^ { 5 } + 5 5 q ^ { 6 } + 9 1 q ^ { 7 } + \cdots \bigr ) } } \\ { { \chi _ { [ \nu ] } ^ { ( 3 ) } ( q ) = q ^ { h + 3 \nu } \bigl ( 1 + 2 q + 5 q ^ { 2 } + 1 0 q ^ { 3 } + 1 9 q ^ { 4 } + 3 4 q ^ { 5 } + 6 0 q ^ { 6 } + 1 0 0 q ^ { 7 } + \cdots \bigr ) \ . } } \end{array}
$$

For the $\ell = 0$ representation, there is one descendant at level one,while for $\ell \neq 0$ the representation has two descendants at level one. This property is also directly visible in (2.9) since the first product only contributes a state at level $^ { 1 }$ if $| \ell | > 0$ ：

Analogous to the counting in eq. (2.8),the wedge character $\chi _ { [ \nu ] } ^ { ( \ell ) } ( q )$ has a combinatorial interpretation

$$
\chi _ { [ \nu ] } ^ { ( \ell ) } ( q ) = q ^ { h + \delta h ( \ell , \nu ) } \sum _ { n = 0 } ^ { \infty } p _ { 2 } ( n , \ell ) q ^ { n } ,
$$

where $p _ { 2 } ( n , \ell )$ counts pairs of Young diagrams $\Gamma ^ { \pm }$ whose height difference is $\ell$ ，i.e. $c _ { 1 } ^ { + } - c _ { 1 } ^ { - } = \ell$ .Here $c _ { i } ^ { \pm }$ are the number of boxes in the $i$ 'th row of $\Gamma ^ { \pm }$ ，and $n$ is the combined number of boxes in the two Young diagrams except that, for the first column of each of the two Young diagrams, only the boxes of the shorter diagram are counted, i.e.

$$
n = \operatorname* { m i n } ( c _ { 1 } ^ { + } , c _ { 1 } ^ { - } ) + \sum _ { i = 2 } ( c _ { i } ^ { + } + c _ { i } ^ { - } ) \ .
$$

The reason for this unusual condition is that in the first factor of $\chi _ { \left[ \nu \right] } ( q , y )$ the prefactor is $y q ^ { - 1 }$ (instead of $y$ ). A useful way to visualise this configuration is by first raising the shorter Young diagram (with height $m$ ） to the same height as that of the taller one (with height $m + | \ell | )$ ， then gluing the two Young diagrams together along their first columns,and finally removing the $| \ell |$ boxes in the first column of the taller Young diagram that are not covered by the shorter diagram, see Figure $1$

![](images/31c97d5a9d3b49e880b67370cfcea7479f5f1c253b205511ffcedbcbcca23f92.jpg)  
Figure 1. Gluing two Young diagrams along their first columns: the diference in height is $\ell = 1$ and the total number of visible boxes after gluing is $n = 1 7$ ：

There is an alternative formula for the wedge character that makes the connection to the original complex boson more transparent,

$$
\chi _ { [ \nu ] } ^ { ( \ell ) } ( q ) = q ^ { h + \delta h ( \ell , \nu ) } \left( \sum _ { m = 0 } ^ { \infty } ( - 1 ) ^ { m } q ^ { \sum _ { k = | \ell | + 1 } ^ { | \ell | + m } k } \right) \cdot \prod _ { n = 1 } ^ { \infty } \frac { 1 } { ( 1 - q ^ { n } ) ^ { 2 } } \ .
$$

This can be obtained from eq. (2.12),using the combinatorial identity

$$
p _ { 2 } ( n , \ell ) = \sum _ { m = 0 } ^ { \infty } ( - 1 ) ^ { m } p _ { 2 } \biggl ( n - \sum _ { k = | \ell | + 1 } ^ { | \ell | + m } k \biggr ) \ ,
$$

where $p _ { 2 } ( n )$ counts pairs of Young diagrams whose total number of boxes is $n$ via the generating function of the complex boson

$$
\begin{array} { l } { { \displaystyle Z _ { \mathrm { c p l x b o s } } ( q ) = \prod _ { n = 1 } ^ { \infty } \frac { 1 } { ( 1 - q ^ { n } ) ^ { 2 } } = \sum _ { n = 0 } ^ { \infty } p _ { 2 } ( n ) q ^ { n } } } \\ { { \displaystyle \qquad = 1 + 2 q + 5 q ^ { 2 } + 1 0 q ^ { 3 } + 2 0 q ^ { 4 } + 3 6 q ^ { 5 } + 6 5 q ^ { 6 } + 1 1 0 q ^ { 7 } + \cdots ~ . } } \end{array}
$$

A proof of (2.15) for $\ell = 0$ is given in [35]; we give the generalization of the proof to arbitrary $\ell$ in Appendix C. In this formula the property that the wedge character only has a single descendant at level one for $\ell = 0$ comes from the fact that the first factor starts with $1 - q ^ { | \ell | + 1 } + \cdot \cdot \cdot$ , i.e. it removes a state at level one for $\ell = 0$ but not otherwise.

As an aside we also mention that the asymptotics of the two-partition function （20 $p _ { 2 } ( n )$ is [36]

$$
p _ { 2 } ( n ) \sim { \frac { 3 ^ { \frac { 1 } { 4 } } } { 1 2 } } \cdot n ^ { - { \frac { 5 } { 4 } } } \cdot \exp \left( { \frac { 2 } { \sqrt { 3 } } } \pi { \sqrt { n } } \right) ,
$$

whereas $p _ { 2 } ( n , \ell )$ with $\ell = 0 , 1$ — we expect that the same is true for general $\ell$ 1 grows half as fast:

$$
p _ { 2 } ( n , \ell ) \sim { \frac { 1 } { 2 } } p _ { 2 } ( n ) \ .
$$

Neither of them grows much faster than the ordinary partition numbers [37]

$$
p ( n ) \sim \frac { 1 } { 4 \sqrt { 3 } } \cdot \frac { 1 } { n } \cdot \exp \left( \sqrt { \frac { 2 } { 3 } } \pi \sqrt { n } \right) ,
$$

since the exponential in both cases is proportional to $\sqrt { n }$

# 2.2 Plane partition viewpoint

We have seen in the previous section that the wedge characters of the twisted sector eq.(2.6) can be interpreted as counting the configurations of two Young diagrams that are glued together along their first columns. This viewpoint now allows us to determine the corresponding coset representation，using the description of the （204号 ${ \mathcal W } _ { \infty }$ representations in terms of plane partitions,which we shall now review.

Just as the partition of $n$ counts the number of ways of drawing Young diagrams with $n$ boxes, the plane partition of $n$ counts the number of ways of stacking $n$ boxes in the corner of a room (such that the number of boxes is non-increasing along all three directions, i.e. the projections onto the $x y$ ， $y z$ ， $z x$ planes all have the shape of a Young diagram). The generating function of the plane partitions is the MacMahon function

$$
\begin{array} { l } { { \displaystyle M ( q ) \equiv \prod _ { s = 1 } ^ { \infty } \prod _ { n = s } ^ { \infty } \frac 1 { ( 1 - q ^ { n } ) } = \prod _ { n = 1 } ^ { \infty } \frac 1 { ( 1 - q ^ { n } ) ^ { n } } = \sum _ { n = 0 } ^ { \infty } M ( n ) q ^ { n } } } \\ { { \displaystyle \qquad = 1 + q + 3 q ^ { 2 } + 6 q ^ { 3 } + 1 3 q ^ { 4 } + 2 4 q ^ { 5 } + 4 8 q ^ { 6 } + 8 6 q ^ { 7 } + \cdots ~ . } } \end{array}
$$

From the definition of the MacMahon function, it is immediate that it is identical to the vacuum character of the $\mathcal { W } _ { 1 + \infty }$ algebra - for each spin $s = 1 , 2 , . . .$ , the modes that contribute to the vacuum Verma module are those with $n = - s , - s - 1 , . . . .$ It has the asymptotic behaviour [38]

$$
M ( n ) \sim \frac { \zeta ( 3 ) ^ { \frac { 7 } { 3 6 } } 2 ^ { \frac { 2 5 } { 3 6 } } } { \sqrt { 1 2 \pi } } e ^ { \zeta ^ { \prime } ( - 1 ) } \cdot n ^ { - \frac { 2 5 } { 3 6 } } \cdot \exp \left( \frac { 3 \zeta ( 3 ) ^ { \frac { 1 } { 3 } } } { 2 ^ { \frac { 2 } { 3 } } } n ^ { \frac { 2 } { 3 } } \right) .
$$

Because of the $\cdot _ { n ^ { \frac { 2 } { 3 } } } ,$ in the exponent, it grows much faster than the ordinary partition (2.19) or the two-partition (2.18), whose exponents are propotional to $\sqrt { n }$

What is more interesting is that we can also consider the set of plane partitions that share a given asymptotic behaviour described by $( \Lambda _ { x } , \Lambda _ { y } , \Lambda _ { z } )$ ，where $\Lambda _ { a }$ with $a = x , y , z$ is the Young diagram to which the plane partition asymptotes in the limit $a  \infty$ . For a given asymptotic $( \Lambda _ { x } , \Lambda _ { y } , \Lambda _ { z } )$ , there exists a unique plane partition configuration that has the least number of boxes — let's call it the minimal configuration with this boundary condition. The character of plane partitions $\mathcal { N } _ { \Lambda _ { x } , \Lambda _ { y } , \Lambda _ { z } } ( \boldsymbol { q } )$ counts the number of ways of stacking boxes starting from this minimal configuration.

Wealltl $\mathcal { N } _ { \Lambda _ { x } , \Lambda _ { y } , \Lambda _ { z } } ^ { \mathrm { p u r e } } ( q )$ reduces to the MacMahon function - the vacuum character of the $\mathcal { W } _ { 1 + \infty }$ algebra. When at least one of the three Young diagrams is trivial - without loss of generality we may take $\Lambda _ { z } ~ = ~ 0$ — the generating function of the plane partition reproduces precisely the （20 $\mathcal { W } _ { 1 + \infty }$ character for the coset representation $( \Lambda _ { x } , \Lambda _ { y } )$ [18-21]

$$
\mathcal { N } _ { \Lambda _ { x } , \Lambda _ { y } , 0 } ^ { \mathrm { p l a n e } } ( q ) = \chi _ { ( \Lambda _ { x } ; \Lambda _ { y } ) } ^ { \mathcal { W } _ { 1 + \infty } } ( q ) ~ .
$$

Here the representations of the coset (2.1) are labelled by the pairs $( \Lambda _ { + } ; \Lambda _ { - } )$ ，where $\Lambda _ { + }$ denotes a representation of ${ \mathfrak { s u } } ( N ) _ { k }$ in the numerator, while $\Lambda _ { - }$ denotes a representation of ${ \mathfrak { s u } } ( N ) _ { k + 1 }$ in the denominator.1 (The representation of the ${ \mathfrak { s u } } ( N ) _ { 1 }$ is then uniquely fixed by the selection rules.） The interpretation of the representations with three non-trivial Young diagrams is not yet entirely clear, although [21] has argued that the exchange of the three asymptotic directions reflects precisely the ‘triality symmetry of [22].

We will now use the map between the generating function of the plane partitions and the $\mathcal { W } _ { 1 + \infty }$ characters (2.22） to identify the coset representations which correspond to the twisted sector states. First of all, the configurations of two glued Young diagrams that are counted by $p _ { 2 } ( n , \ell )$ ， see eq. (2.12) above, can be described, in the plane partition language, as the plane partitions with a pit dug at $( x , y ) = ( 2 , 2 )$ [39]. Here, the presence of a‘pit’ means that one cannot place a box at that position. But since a plane partition has to give Young diagrams upon the projection along all three directions,a‘pit’at $( x , y ) = ( 2 , 2 )$ means that we cannot place any box at a position with $x \geq 2$ or $y \geq 2$ . The plane partitions with this ‘pit’ condition therefore reduce to a pair of Young diagrams that are glued along their first columns, where the two Young diagrams sit in the $z x$ and $y z$ planes, respectively, and the shared first column is along the $z$ -direction.

Next we recall that eq. (2.12), i.e. the plane partition with the ‘pit’ condition, only counts the wedge character. The full character is obtained by multiplying the wedge character with the vacuum character. Since the first one is given by the ‘pit’ partition function,whereas the second equals the MacMahon function - the plane partition starting from an empty corner - the full coset character is then described by the window sill configuration of Figure 2 in the limit in which the height of the walls are taken to infinity. Indeed, in this limit,there is a natural separation between the confgurations that involve boxes being stacked on the ‘floor' - these are counted by the MacMahon function,and hence describe the contribution of the $\mathcal { W } _ { 1 + \infty }$ modes outside the wedge - and those that are stacked on the high‘window-sill',and which are counted by the plane partition with pit at $( x , y ) = ( 2 , 2 )$ ：

![](images/02b9d743d2548de0f3ef673d3352cd4f3c773631480a031edd9cba7c3b487f5f.jpg)  
Figure 2. The minimal configuration of plane partitions that describes (a) the terms with $y ^ { 0 }$ in eq. (2.5); and (b) the terms with $y ^ { 3 }$ in eq. (2.5). The corresponding coset representations are described by (2.23).

It remains to relate the height $b$ of the window sill to the twist of the corresponding bosonic representation. By comparing conformal dimensions, see Section 2.4, we find that the relevant coset representations are

$$
( \Lambda _ { + } ; \Lambda _ { - } ) = \left( [ 0 ^ { b - 1 } , 1 , 0 , \ldots , 0 ] ; [ 0 ^ { b + \ell - 1 } , 1 , 0 , \ldots , 0 ] \right) ,
$$

where

$$
b = \nu N \ .
$$

Furthermore, the case where more than one boson is twisted is described by putting the relevant window-sills together, see Figure 3 for an example where two bosons are twisted. The generalization to the situation where some or all bosons are twisted is then straightforward, where the height of each window-sill should be identified with $\nu _ { i } N$ ，where $\nu _ { i }$ is the twist parameter of the corresponding boson. In particular, there is then a natural separation for the different box configurations into the boxes on the‘floor’ - again these configurations describe the contributions of the outside-the-wedge modes - and the boxes stacked on the individual windowsills.2 The wedge character in the multi-twist case is therefore just the product of the individual wedge characters (2.14).

![](images/7c68f09efbcc8bfe126934b0d6d89a48268ab03f22d2886e08a804b53616b222.jpg)  
Figure 3. The minimal configuration of plane partitions that captures the situation where two complex bosons are twisted. Case (a) describes the ground state representation, while (b) describes the representation appearing at some excited level.

These considerations therefore suggest that the coset representation $( \Lambda _ { + } ; \Lambda _ { - } )$ that corresponds to the ground state of the multi-twisted sector associated to the twist $( \nu _ { 1 } , \ldots , \nu _ { k } )$ with $\nu _ { 1 } \geq \nu _ { 2 } \geq \cdot \cdot \cdot \geq \nu _ { k }$ is of the form $( \Lambda _ { + } ; \Lambda _ { - } )$ ，where

$$
\Lambda _ { + } = \Lambda _ { - } = \Lambda \qquad \mathrm { w i t h } \quad c _ { i } = \nu _ { i } N \mathrm { b o x e s ~ i n ~ t h e ~ } i ^ { \prime } \mathrm { t h ~ c o l u m n } .
$$

Furthermore, the various twisted excitations (corresponding to the non-trivial powers of $y _ { i } ^ { \ell _ { i } }$ ）are described by the coset representations for which a finite number of boxes (corresponding to the number of twisted excitation modes) are added to or removed from $\Lambda _ { - }$ (but not $\Lambda _ { + }$ ). Namely, the column heights of $\Lambda _ { + }$ and $\Lambda _ { - }$ are

$$
c _ { i } ^ { + } = \nu _ { i } N ~ , \qquad c _ { i } ^ { - } = \nu _ { i } N + \ell _ { i } ~ ,
$$

where $\ell _ { i }$ is finite (and does not scale with $N$ ). These predictions will be tested below, see Section 2.4, following the techniques of [17].

# 2.3 The null-vector analysis

One of the key results of the previous two subsections is that the coset representation corresponding to the ground state of the single-twist sector is of the form (2.23), i.e. given by two totally anti-symmetric Young diagrams both with $b$ boxes，where $b  \infty$ in the 't Hooft limit. This was based on a character analysis and used the description of the coset representations in terms of plane partition. In this subsection, we approach this problem from a ‘microscopic' viewpoint, by studying the null-vector structure of the relevant family of representations. As we shall see, this will nicely confirm the above results. We shall concentrate on the ground state representations, i.e. the representations of the form (2.23) with $\ell = 0$ ，since for them the analysis is simplest; the excitation spectrum will be studied in more detail in the following subsection (albeit from a slightly different viewpoint).

Since our considerations are only valid in the 't Hooft limit we can decouple the outside-the-wedge modes and think of these representations as representations of the wedge algebra hs[1]. We are therefore looking for the hs[1] representation, whose character is the wedge character $\chi _ { [ \nu ] } ^ { ( \ell ) }$ with $\ell = 0$ ，where

$$
\begin{array} { l } { { \displaystyle \chi _ { [ \nu ] } ^ { ( 0 ) } ( q ) = q ^ { h } \prod _ { n = 1 } ^ { \infty } ( 1 - y q ^ { n - 1 + \nu } ) ^ { - 1 } ( 1 - y ^ { - 1 } q ^ { n - \nu } ) ^ { - 1 } \Bigg \vert _ { y ^ { 0 } } } } \\ { { = q ^ { h } \left( 1 + q + 3 q ^ { 2 } + 6 q ^ { 3 } + 1 2 q ^ { 4 } + 2 1 q ^ { 5 } + 3 8 q ^ { 6 } + 6 3 q ^ { 7 } + \cdots \right) . } } \end{array}
$$

Although the wedge character X[ was computed using the free boson viewpoint which corresponds to hs[1], we shall see below that an $\mathrm { { h s } } [ \lambda ]$ representation with this character can be constructed for any value of $\lambda$ ， not just for $\lambda = 1$ . One way to do this is to start with an arbitrary highest weight state $\phi$ , and determine the structure of the null-vectors it must possess in order to lead to a character of the form (2.27).

Let us denote the modes of the $\mathrm { { h s } } [ \lambda ]$ algebra by $V _ { m } ^ { ( s ) }$ ，where $s = 2 , 3 , \ldots .$ and $| m | \leq s - 1$ . Furthermore, we denote by $w ^ { ( s ) }$ the eigenvalue of $V _ { 0 } ^ { ( s ) }$ acting on a highest weight state $\phi$ . A generic highest weight representation of $\mathrm { { h s } } [ \lambda ]$ can be specified by its charges $w ^ { ( s ) }$ for all $s \geq 2$ . However, the representation given by (2.27) is very special: it has only a single descendant at level one - this type of representations was named level-one representation' in [12]. For a level-one representation, the condition that it has only a single state at level $1$ is so strong that it fixes all $w ^ { ( s ) }$ with $s \geq 4$ （204号 in terms of its conformal dimension $w ^ { ( 2 ) } \equiv h$ and its spin-3 charge $w ^ { ( 3 ) }$ ：

In order to see this, we first note that having only a single state at level 1 means that all $V _ { - 1 } ^ { ( s ) } \phi$ must be proportional to one another,and in particular, to $V _ { - 1 } ^ { ( 2 ) } \phi$

$$
V _ { - 1 } ^ { ( s ) } \phi = { \frac { s w ^ { ( s ) } } { 2 h } } V _ { - 1 } ^ { ( 2 ) } \phi ~ ,
$$

where the proportionality factor is fixed by the requirement that these relations hold upon applying $V _ { 1 } ^ { ( 2 ) } \equiv L _ { 1 }$ to both sides. Then, by taking the commutator with $V _ { 0 } ^ { ( 3 ) }$ ， we can recursively determine the various $w ^ { ( s ) }$ eigenvalues in terms of $h$ and $w ^ { ( 3 ) }$ .It is more convenient to use $h$ and the ratio

$$
\alpha \equiv \frac { 3 w ^ { ( 3 ) } } { 2 h }
$$

to express the result, and for the first few spins we find explicitly

$$
\begin{array} { l } { { w ^ { ( 3 ) } = \displaystyle \frac { 2 h } { 3 } \alpha } } \\ { { w ^ { ( 4 ) } = \displaystyle \frac { h } { 2 } \left[ \alpha ^ { 2 } + \frac { 4 - \lambda ^ { 2 } } { 2 0 } \right] } } \\ { { w ^ { ( 5 ) } = \displaystyle \frac { 2 h } { 5 } \alpha \left[ \alpha ^ { 2 } + \frac { 2 0 - 3 \lambda ^ { 2 } } { 2 8 } \right] } } \\ { { w ^ { ( 6 ) } = \displaystyle \frac { h } { 3 } \left[ \alpha ^ { 4 } + \alpha ^ { 2 } \left( \frac { 1 0 - \lambda ^ { 2 } } { 6 } \right) + \frac { \lambda ^ { 4 } - 2 0 \lambda ^ { 2 } + 6 4 } { 3 3 6 } \right] \ . } } \end{array}
$$

The expressions agree with those for the free boson obtained in eqs. (B.5) -(B.7) of [12] upon setting $\lambda = 1$ 3

The level-one condition not only fixes all higher charges in terms of $( h , \alpha )$ ，together with the structure of $\mathrm { { h s } } [ \lambda ]$ it also imposes very strong constraints on the number of descendants for every level. It has been shown recursively in [12] that the wedge character of a generic level-one representation is precisely the MacMahon function (2.2O). More specifically, the full representation is generated by the modes （204号 $V _ { - n } ^ { ( s ) } \phi$ ，where $s = n + 1 , \ldots , 2 n$ ,and this matches then with another form of the MacMahon function, M(q) = IIn=1 (1-qn)n .

Comparing now the $q$ expansion of the wedge character (2.27) with the MacMahon function (i.e. the $\mathrm { { h s } } [ \lambda ]$ character of a generic level-one representation)， we see that the ground state of the twisted sector does not lead to a generic level-one representation: it has a first additional null-vector at level 4 — this was already noted in [12]. This property can now be used to determine constraints on the parameters $( h , \alpha )$ . To do this, we study the structure of the null vectors systematically, from level 2 up to level 5. Here we only give a brief summary of the results; the details can be found in Appendix A.

At each level, we have worked out the inner product matrix of the corresponding basis states and determined its determinant. If this vanishes, this signals the appearance of a null-vector at that level. Any null-vector at level $l$ will also give rise to descendant nul-vectors at higher level; it is therefore of primary interest to describe the new null-vectors that appear at each level. Up to level 5, these new null-vectors arise for the following values of $( h , \alpha )$

$$
{ \begin{array} { r l } & { { \mathrm { L e v e l ~ 2 : } } \qquad \alpha = \pm { \left( 1 \pm { \frac { \lambda } { 2 } } \right) } , \quad \alpha = \pm { \frac { 1 } { 2 } } { \sqrt { 8 h + \lambda ^ { 2 } } } ; } \\ & { { \mathrm { L e v e l ~ 3 : } } \qquad \alpha = \pm { \left( 2 \pm { \frac { \lambda } { 2 } } \right) } , \quad \alpha = \pm { \frac { 1 } { 2 } } { \sqrt { 4 h + \lambda ^ { 2 } } } ; } \\ & { { \mathrm { L e v e l ~ 4 : } } \qquad \alpha = \pm { \left( 3 \pm { \frac { \lambda } { 2 } } \right) } , \quad \alpha = \pm { \frac { 1 } { 2 } } { \sqrt { \frac { 8 } { 3 } h + \lambda ^ { 2 } } } , } \\ & { \qquad \alpha = \pm { \frac { 1 } { 2 } } { \sqrt { \lambda ^ { 2 } - 8 h } } ; } \\ & { { \mathrm { I e v e l ~ 5 : } } \qquad \alpha = \pm { \left( 4 \pm { \frac { \lambda } { 2 } } \right) } , \quad \alpha = \pm { \frac { 1 } { 2 } } { \sqrt { 2 h + \lambda ^ { 2 } } } . } \end{array} }
$$

For the case at hand, we are interested in the three new roots (not counting multiplicities and conjugations) at level 4; as we have explained before, the ground state of the twisted sector has to satisfy (at least） one of these relations.

All the roots, except for the third pair of roots at level 4, follow a simple pattern, and as is explained in Appendix A, all of these ‘standard' roots are attained by finite tensor powers of the minimal representation. It is thus very suggestive that the additional null-vector that appears in the twisted sector representation corresponds to this ‘special’ root.

To confirm this, we have computed the value of $( h , \alpha )$ for the representation of the form

$$
\left( \Lambda _ { + } ; \Lambda _ { - } \right) = \left( [ 0 ^ { b - 1 } , 1 , 0 , \ldots , 0 ] ; [ 0 ^ { b - 1 } , 1 , 0 , \ldots , 0 ] \right) ,
$$

using the Drinfeld-Sokolov approach, see Appendix B for details. In particular, it follows from eqs. (B.15) and (B.16), that the eigenvalues take the form

$$
\begin{array} { l } { { \displaystyle h = \frac { \lambda ^ { 2 } b ( N + 1 ) ( N - b ) } { 2 N ^ { 2 } ( N + \lambda ) } \stackrel { * } { \approx } \stackrel { \mathrm { t } } { \approx } \stackrel { \mathrm { h o o f t } } { \longrightarrow } \left( 1 - \frac { b } { N } \right) \frac { b } { N } } } \\ { { \displaystyle \alpha = \frac { \lambda ( N + 2 ) ( N - 2 b ) } { 2 N \sqrt { N ( N + \lambda ) } } \stackrel { * } { \approx } \stackrel { \mathrm { t } } { \approx } \stackrel { \mathrm { h o o f t } } { \longrightarrow } \frac { \lambda } { 2 } \left( 1 - 2 \frac { b } { N } \right) , } } \end{array}
$$

where we have first replaced $k$ in terms of $\lambda$ ，using (2.2)，and then considered the ’t Hooft limit. Using $0 \leq \lambda \leq 1$ and demanding $0 < b < N$ — only Young diagrams of height at most $N$ are allowed — we see that neither of the first two roots can be

solved by representations of this type,whereas the last one

$$
\alpha = \pm \frac { 1 } { 2 } \sqrt { \lambda ^ { 2 } - 8 h } \ .
$$

is solved for any $0 < b < N$ . If we further demand that $h > 0$ in the ’t Hooft limit (i.e. that they are not light states) then we conclude that4

$$
b = \nu N \qquad \mathrm { w i t h } \qquad \nu < 1 \ .
$$

It only remains to understand the meaning of $\nu$ , for which we go back to the special case of $\lambda = 1$ (i.e. the free boson） from where we started. At $\lambda = 1$ ， (2.33） with (2.35) reduces to

$$
h = \frac { 1 } { 2 } \nu ( 1 - \nu ) \qquad \mathrm { a n d } \qquad \alpha = \frac { 1 } { 2 } ( 1 - 2 \nu ) \ ,
$$

which agrees with the result for the twisted sector representation of the free boson from [7], see its eq. (4.4) and (4.5).5 Thus we conclude that $\nu$ can indeed be identifed with the twist parameter.

# 2.4 The ground state conformal dimension and the excitation spectrum

In this section we confirm the identification between the coset representations and the twisted sector states given in eq. (2.25) (for the ground state) and (2.26) (for the excited states） by matching their conformal dimensions in the large $N$ limit.The analysis follows the same strategy as what was done for the ${ \mathcal N } = 2$ case in [17].

The conformal dimension of the ground state of the coset representation $( \Lambda _ { + } , \Lambda _ { - } )$ is

$$
h ( \Lambda _ { + } ; \Lambda _ { - } ) = { \frac { C _ { 2 } ( \Lambda _ { + } ) } { N + k } } + { \frac { C _ { 2 } ( \mu ) } { N + 1 } } - { \frac { C _ { 2 } ( \Lambda _ { - } ) } { N + k + 1 } } + n \ ,
$$

where $C _ { 2 }$ is the quadratic Casimir, $\mu$ is the ${ \mathfrak { s u } } ( N ) _ { 1 }$ weight that is uniquely determined by the condition that $\Lambda _ { + } + \mu - \Lambda _ { - }$ lies in the root lattice,and $n$ denotes the first descendant level where $\Lambda _ { - }$ appears in the affine representation of the numerator. The Casimir can be written in terms of the number of boxes in rows $r _ { i }$ and columns Cj as

$$
C _ { 2 } ( \Lambda ) = \frac 1 2 B N + \frac 1 2 \left( \sum _ { i } r _ { i } ^ { 2 } - \sum _ { j } c _ { j } ^ { 2 } \right) - \frac { B ^ { 2 } } { 2 N } \ ,
$$

where $\begin{array} { r } { B = \sum _ { i } r _ { i } = \sum _ { j } c _ { j } } \end{array}$ is the total number of boxes.

Let us start with analysing the conformal dimension of the ground state of the twisted sector. In this case, since $\Lambda _ { + } = \Lambda _ { - } = \Lambda$ ，the ${ \mathfrak { s u } } ( N ) _ { 1 }$ representation $\mu$ is trivial and $n = 0$ , and therefore the ground state conformal dimension equals

$$
h = \frac { C _ { 2 } ( \Lambda ) } { ( N + k ) ( N + k + 1 ) } \ .
$$

We are interested in the large $N$ behaviour at fixed $k$ ； since $r _ { i } \leq k$ ，the $r _ { i } ^ { 2 }$ term is subleading at large $N$ ，and since the total number of boxes scales linearly with $N$ ， the same is true for the $B ^ { 2 } / 2 N$ term.Thus,to leading order in the $N  \infty$ limit, we have

$$
C _ { 2 } \cong \frac { 1 } { 2 } B N - \frac { 1 } { 2 } \sum _ { j } c _ { j } ^ { 2 } = \frac { N ^ { 2 } } { 2 } \sum _ { j } \nu _ { j } ( 1 - \nu _ { j } ) \ .
$$

Dividing by the denominator in (2.39) then leads to

$$
h = \frac { 1 } { 2 } \sum _ { j } \nu _ { j } ( 1 - \nu _ { j } ) \ ,
$$

which agrees precisely with the usual ground state energy of a multi-twist sector associated to the twist $( \nu _ { 1 } , \ldots , \nu _ { k } )$ with $\nu _ { 1 } \geq \nu _ { 2 } \geq \cdot \cdot \cdot \geq \nu _ { k }$ ：

Having checked that the large $N$ limit of the coset representation $( \Lambda , \Lambda )$ of the form (2.25) agrees with the ground state energy of the twisted sector, we now compute the excitation spectrum above this ground state. For a generic twisted sector corresponding to $\nu _ { 1 } \geq \nu _ { 2 } \geq \cdot \cdot \cdot \geq \nu _ { k }$ , the different bosonic generators will have mode numbers $- \nu _ { j } + m$ ，where $j = 1 , \dots , k$ and $m \in \mathbb { Z }$ . Thus the lowest excitations raise the conformal dimension by $\nu _ { j }$ . These different excitations should now correspond to the different ways in which we can add a single box to $\Lambda _ { - }$ , without modifying $\Lambda _ { + }$

To compute the difference in conformal dimension of the coset representation $( \Lambda ; \Lambda ^ { ( i ) } )$ ，where $\Lambda ^ { ( i ) }$ differs from $\Lambda$ by adding a single box to the $i$ 'th column, and that of the ground state $( \Lambda ; \Lambda )$ ， we now use eq. (2.37). For $( \Lambda ; \Lambda ^ { ( i ) } )$ ，the ${ \mathfrak { s u } } ( N ) _ { 1 }$ representation $\mu$ equals the fundamental representation while $n$ remains $n = 0$ . Thus the difference in conformal dimension equals

$$
h ( \Lambda ; \Lambda ^ { ( i ) } ) - h ( \Lambda ; \Lambda ) = { \frac { C _ { 2 } ( \square ) } { N + 1 } } - { \frac { C _ { 2 } ( \Lambda ^ { ( i ) } ) - C _ { 2 } ( \Lambda ) } { N + k + 1 } } \ .
$$

The Casimir of the fundamental is $\begin{array} { r } { C _ { 2 } ( \bigsqcup ) \ = \ \frac { N ^ { 2 } - 1 } { 2 N } } \end{array}$ ， and the difference of the two Casimirs, to leading order in $N$ , can be computed using (2.40)

$$
C _ { 2 } ( \Lambda ^ { ( i ) } ) - C _ { 2 } ( \Lambda ) \cong { \frac { N } { 2 } } - c _ { i } ,
$$

where $c _ { i } = \nu _ { i } N$ is the number of boxes in the $i$ 'th column of $\Lambda$ . Hence,in the $N \to \infty$ （204号 limit the excitation energy above the ground state takes the form

$$
h ( \Lambda ; \Lambda ^ { ( i ) } ) - h ( \Lambda ; \Lambda ) \cong \nu _ { i }
$$

as expected.

We should also note that if we remove a box from the $i$ 'th column of $\Lambda _ { - }$ 5 then the whole contribution from (2.43) changes sign, and the excitation energy is $\delta h = ( 1 - \nu _ { i } )$ . This describes the action of the complex conjugate mode. These results thus reproduce the excitation spectrum in the twisted sector, see, in particular, eq. (2.10)，where $\ell > 0$ and $\ell < 0$ corresponds to the excitation by the boson and its complex conjugate, respectively. In terms of plane partitions, $\ell$ is the difference in height of the window sills of $\Lambda _ { - }$ relative to $\Lambda _ { + }$ ; thus the action of the boson and its conjugate can be thought of as adding a box to $\Lambda _ { - }$ and $\Lambda _ { + }$ ， respectively.6 This identification is,however, only valid in the large $N$ limit, where we have a‘Fermi sea' of boxes and where the action of the anti-boxes can be described as creating a hole. In general, the plane partition viewpoint only describes the representations that are made from boxes,and anti-boxes do not appear directly in this language.

# 3The twisted sector in the free fermion description

The bosonic coset theories also have a free field description for $\lambda = 0$ ，where free fermions emerge. More precisely, $\lambda = 0$ corresponds to taking $k  \infty$ at fixed $N$ ， see eq. (2.2)，and the resulting theory can be identified with the $\mathrm { u ( 1 ) }$ coset of the theory of $N$ complex fermions,see [33]. These fermions give rise to bilinear currents of the form

$$
W ^ { s } ( z ) = n ( s ) \sum _ { l = 0 } ^ { s - 1 } ( - 1 ) ^ { l } { \binom { s - 1 } { l } } ^ { 2 } \partial ^ { s - 1 - l } \psi ^ { * j } \partial ^ { l } \psi ^ { j } \ ,
$$

where $n ( s )$ is an $s$ -dependent normalization constant. The modes of these fields generate the linear $\mathcal { W } _ { 1 + \infty }$ algebra [29-31].

The bilinear currents are invariant under a $\mathrm { S U } ( N )$ subgroup,and one can therefore think of the resulting theory as a continuous orbifold by this group [34]. There are therefore again twisted sectors that should admit a coset description. In the following we shall work out the details of this correspondence.

For the case of a single twisted complex fermion with modes

$$
\psi _ { r - \nu } \qquad \mathrm { a n d } \qquad \psi _ { r + \nu } ^ { * } \qquad \mathrm { w i t h } \quad r \in \mathbb { Z } + { \frac { 1 } { 2 } } \ ,
$$

the wedge character is given by the fermionic analogue of (2.5)

$$
\phi _ { [ \nu ] } ( q , y ) = q ^ { h } \prod _ { n = 1 } ^ { \infty } ( 1 + y q ^ { n - 1 / 2 + \nu } ) ( 1 + y ^ { - 1 } q ^ { n - 1 / 2 - \nu } ) ~ ,
$$

where the twist is taken to lie in the interval $\begin{array} { r } { - \frac { 1 } { 2 } < \nu \leq \frac { 1 } { 2 } } \end{array}$ . As for the bosonic case, the power of $y$ keeps track of the action under the cyclic group,and thus the states with a given power of $y$ furnish a representation of the hs[O] algebra,with character

$$
\phi _ { [ \nu ] } ^ { ( m ) } ( q ) \equiv \phi _ { [ \nu ] } ( q , y ) \big | _ { y ^ { m } } ~ .
$$

In contrast to the bosonic case, the fermionic wedge character $\phi ^ { ( \ell ) } ( q )$ is much easier to compute. Using the Jacobi triple product identity,

$$
\prod _ { n = 1 } ^ { \infty } ( 1 - q ^ { n } ) ( 1 + y q ^ { n - 1 / 2 } ) ( 1 + y ^ { - 1 } q ^ { n - 1 / 2 } ) = \sum _ { n = - \infty } ^ { \infty } y ^ { n } q ^ { n ^ { 2 } / 2 } \ ,
$$

weimmediatelyhave

$$
\begin{array} { l } { { \displaystyle \phi _ { [ \nu ] } ^ { ( m ) } ( q ) = q ^ { h + m \nu + m ^ { 2 } / 2 } \prod _ { n = 1 } ^ { \infty } \frac { 1 } { ( 1 - q ^ { n } ) } } } \\ { { = q ^ { h + m \nu + m ^ { 2 } / 2 } \big ( 1 + q + 2 q ^ { 2 } + 3 q ^ { 3 } + 5 q ^ { 4 } + 7 q ^ { 5 } + 1 1 q ^ { 6 } + 1 5 q ^ { 7 } + . . . \big ) ~ . } } \end{array}
$$

In the following we shall use the plane partition viewpoint to identify the corresponding coset representations.

# 3.1 The plane partition viewpoint

Recall from the bosonic analysis of Section 2.2 that， from the plane partition perspective, the coset character factorizes into two pieces: one corresponding to stacking boxes on the window sill - this accounts precisely for the wedge character — and one corresponding to staking boxes on the empty floor - this gives the MacMahon function that counts the outside-the-wedge modes. In the present situation we expect to find a similar situation, except that now the wedge character $\phi ^ { ( m ) } ( q )$ is the generating function of the partition number, i.e. it counts the number of Young diagrams with $n$ boxes.(This is in fact true for all $m$ —— the only $m$ -dependence of (3.6) appears in the overall exponent of $q$ ）

The most naive guess for the correct plane partition configuration seems to be a single layer window sill along the $x$ -direction,say. In this scenario,stacking boxes on top of this window sill, which is equivalent to drawing usual two-dimensional Young diagrams, gives rise to the wedge character (3.6)； whereas stacking boxes on the floor gives the MacMahon function， counting the outside-the-wedge modes of $\mathcal { W } _ { 1 + \infty }$ . However， this guess turns out to be wrong since the coset representation corresponding to this plane partition, i.e. $( [ 0 ^ { b - 1 } , 1 , 0 , \dots , 0 ] ; 0 )$ with $b  \infty$ ，has conformal dimension (see eq. (B.8))

$$
h ( [ 0 ^ { b - 1 } , 1 , 0 , \dots , 0 ] ; 0 ) = \frac { b ( N - b ) } { 2 N } \cdot \frac { 2 N + k + 1 } { N + k } \ ,
$$

which diverges in the 't Hooft limit.7

However, we can also reverse the roles of the window sill and the floor,i.e. we can let the floor count the wedge character, and the window sill the outside-the-wedge modes. Then if we take the window sill to be only one box high, it can restrict the box-stacking on the floor to be a counting of Young diagrams. This leads us to the choice of plane partitions with a window-sill that is only one box high,but has a fat ‘L' shape,whose widths $b$ and $b + m$ are taken to be large, see Figure 4. In particular, since the widths are large, the boxes that are placed on top of the window-sill, near the origin,are again counted by the MacMahon function (and hence describe the outsidethe-wedge modes of $\mathcal { W } _ { 1 + \infty }$ ). On the other hand, the configurations involving only boxes on the floor are counted again by plane partitions that satisfy a (generalized) ‘pit’condition,where the pit is now located at $( x , y , z ) = ( 1 , 1 , 2 )$ and prevents any boxes from being stacked vertically.

![](images/8198c44bca99dd5e1fc0b3da4ed54152a4cb7793014ce1a37a85abe325cd19bc.jpg)  
Figure 4. The minimal configuration of plane partitions that describes the single-twist case for complex fermions. Case (a) corresponds to the ground state representation, while (b) corresponds to the representation appearing at some excited level.

The coset representations corresponding to this type of plane partition asymptotics are

$$
\big ( [ b , 0 , \dots , 0 ] ; [ b + m , 0 , \dots , 0 ] \big )
$$

for suffciently large $b$ The neutral sector, whose wedge character is $\phi _ { [ \nu ] } ^ { ( 0 ) } ( q )$ ,corresponds to $m = 0$ , see Figure 4 (a); the higher representations with $m > 0$ are shown in Figure 4 (b).

In all of these cases, the relevant representations are level-one representations that have one nul-vector at level 2, i.e. there are only 2 rather than 3 states at the second descendant level. In fact, all of these representations have $\begin{array} { r } { \alpha = \frac { 1 } { 2 } \sqrt { 8 h + \lambda ^ { 2 } } } \end{array}$ in the 't Hooft limit, as follows from the analysis of appendix B, see e.g. eq. (B.20).

It is also not diffcult to guess which plane partition asymptotics describe now the case where more than one fermion is twisted: as in the bosonic case,we simply put different such diagrams together, see Figure 5 for the case where two fermions are twisted.

![](images/cb65b89f43ef00e32b86a754df2f1e5679ea7a980ee537ab7ea3c92a7372b34f.jpg)  
Figure 5. The minimal configuration of plane partitions that corresponds to the ground state of the twisted sector where two complex fermions are twisted.

The coset representation describing the ground state of a generic twist is then of the form

$$
\left( [ b _ { 1 } , b _ { 2 } , b _ { 3 } , . . . , b _ { N - 1 } ] ; [ b _ { 1 } , b _ { 2 } , b _ { 3 } , . . . , b _ { N - 1 } ] \right) ,
$$

where the associated twists are

$$
k \nu _ { i } = \frac { B } { N } - r _ { i } \ ,
$$

and $r _ { i }$ is the number of boxes in the $i$ 'th row, $i = 1 , \ldots , N$ ，while $B = \textstyle \sum _ { i } r _ { i }$ is the total number of boxes. This identification implies that the sum of all $N$ twists is zero，as has to be the case for a group element in $\mathrm { S U } ( N )$ .We also note that by applying a field identification transformation, if necessary, we may assume that all $\begin{array} { r } { r _ { i } \le \frac { k } { 2 } } \end{array}$ , thus implying that $- \frac 1 2 < \nu _ { 1 } \leq \nu _ { 2 } \dots \leq \nu _ { N } \leq \frac 1 2$

# 3.2 The ground state conformal dimension and the excitation spectrum

As in the bosonic case, we can confirm these claims by direct CFT calculations. We begin with showing that the coset representation (3.9) has the correct conformal dimension,namely

$$
h = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N } \nu _ { i } ^ { 2 }
$$

in the $k  \infty$ limit. Note that there are $N$ complex fermions,and each $\nu$ -twisted fermion contributes $\nu ^ { 2 } / 2$ to the ground state conformal dimension. In relating the free fermion theory to the coset at $\lambda = 0$ ， we need to take the $\mathfrak { u } ( 1 )$ orbifold, i.e. we need to subtract from the conformal dimension of the numerator $- u ^ { 2 } / 2 N$ ，where $u$ （204号 is the $\mathfrak { u } ( 1 )$ -charge of the state, see eq. (3.15) below. Since $\sum _ { i } \nu _ { i } = 0$ ,the $\mathfrak { u } ( 1 )$ -charge is however $u = 0$ , and hence we arrive at (3.11).

In order to derive this formula from the coset viewpoint,we note that the coset representation of the ground state is of the form $( \Lambda ; \Lambda )$ ，where the row lengths $r _ { i }$ of $\Lambda$ satisfy (3.1O). In the orthogonal basis of appendix B, see in particular eq. (B.1), the quadratic Casimir of $\Lambda$ is

$$
C ( \Lambda ) = { \frac { 1 } { 2 } } \sum _ { i = 1 } ^ { N } \Bigl ( r _ { i } - { \frac { B } { N } } \Bigr ) \Bigl ( r _ { i } - { \frac { B } { N } } + N + 1 - 2 i \Bigr ) \cong { \frac { 1 } { 2 } } \sum _ { i = 1 } ^ { N } \Bigl ( r _ { i } - { \frac { B } { N } } \Bigr ) ^ { 2 } = { \frac { k ^ { 2 } } { 2 } } \sum _ { i = 1 } ^ { N } \nu _ { i } ^ { 2 } \ .
$$

Alternatively, this can also be seen from (2.38) since the $r _ { i } ^ { 2 }$ and the $- B ^ { 2 } / 2 N$ terms are the only expressions proportional to $k ^ { 2 }$ . Dividing by $( N + k ) ( N + k + 1 ) \cong k ^ { 2 }$ in the large $k$ limit, then leads to the desired expression for the conformal dimension, eq. (3.11).

Next， we study the excitation spectrum, following the same logic as above for the bosonic case, i.e. eq. (2.42). From the diference of Casimirs we now find, to leading order in $k$ ，

$$
C _ { 2 } ( \Lambda ^ { ( i ) } ) - C _ { 2 } ( \Lambda ) \cong \frac { 1 } { 2 } \left( ( r _ { i } + 1 ) ^ { 2 } - r _ { i } ^ { 2 } \right) - \frac { ( B + 1 ) ^ { 2 } - B ^ { 2 } } { 2 N } \cong r _ { i } - \frac { B } { N } = - k \nu _ { i } ,
$$

where $\Lambda ^ { ( i ) }$ is now the representation that has an additional box in the $i$ 'th row. Thus the excitation spectrum is

$$
h ( \Lambda ; \Lambda ^ { ( i ) } ) - h ( \Lambda ; \Lambda ) \cong \nu _ { i } + { \frac { N - 1 } { 2 N } } \ .
$$

For the free fermion theory one would have expected the answer to be $\begin{array} { r } { \nu _ { i } + \frac { 1 } { 2 } } \end{array}$ ； the reason for the discrepancy is that in order to obtain the $\mathcal { W } _ { \infty } \vert 0 \vert$ theory that is described by the coset in the $k  \infty$ limit, one has to divide out a $\mathfrak { u } ( 1 )$ algebra- this was explained in detail in [33]. In particular, the decoupled stress energy tensor is

$$
{ \tilde { T } } = T - { \frac { 1 } { 2 N } } : J J : \ ,
$$

and since the individual fermions carry unit $\mathfrak { u } ( 1 )$ charge, they define primary fields of conformal dimension

$$
\tilde { h } = \frac { 1 } { 2 } - \frac { 1 } { 2 N } = \frac { N - 1 } { 2 N }
$$

in the decoupled theory. (Another way of reaching the same conclusion is by observing that the conformal dimension of the $( 0 ; \boxed { \mathbf { \overline { { \mathbf { U } } } } } )$ representation equals

$$
h ( 0 ; \boldsymbol { \Theta } ) = \frac { ( N - 1 ) } { 2 N } \Big ( 1 - \frac { N + 1 } { N + k + 1 } \Big ) \cong \frac { ( N - 1 ) } { 2 N }
$$

in the large $k$ limit.） In either case, this then accounts precisely for the additional term in (3.14). Finally, we also note that removing a box from the $i$ 'th row changes simply the sign in (3.13), and thus leads to $\textstyle - \nu _ { i } + { \frac { N - 1 } { 2 N } }$ instead of (3.14). This then describes the action of the conjugate fermionic mode, see eq. (3.3).

# 4 Conclusions

In this paper we have identified the twisted sector states of the bosonic higher spin CFTs in terms of coset representations. The main idea was to use the description of $\mathcal { W } _ { \infty }$ representations in terms of plane partitions [18-21]. Our analysis demonstrates that this method provides a very powerful approach for the characterization of these representations,and this perspective is likely to have other important applications.

The plane partition configurations that are crucial to this analysis allow for a natural separation into the contribution associated to the wedge modes on the one hand, and those coming from the outside-the-wedge modes on the other, see e.g. the discussion in Section 2.2. In particular, the former had a nice combinatorial description in terms of plane partitions with a (generalized) pit condition. It would be interesting to see whether this observation generalizes, and whether the representation theory of the wedge algebra hs $[ \lambda ]$ can in general be captured by plane partitions with suitable‘pit’ conditions.

At present, the plane partition viewpoint has only been developed for the $\mathcal { W } _ { \infty }$ algebra that appears in the duality to bosonic higher spin theory; it would be very interesting to generalize this technique to the supersymmetric cases. In particular, the ${ \mathcal { N } } = 2$ case where Young super tableaux [45, 46] naturally appear (see e.g. [47]) should allow for a nice generalization.

Given that the plane partitions also describe the representation theory of the affine Yangian algebra of ${ \mathfrak { g l } } _ { 1 }$ ，which is believed to contain $\mathcal { W } _ { \infty }$ as a subalgebra [21], this viewpoint relates higher spin symmetries to Yangian symmetries that typically arise in integrable systems. This approach may therefore pave the way towards understanding the relation between higher spin symmetries and integrability. As with the embedding into string theory, it is likely that the sharpest results will be possible in the maximally supersymmetric ${ \mathcal N } = 4$ case,and hence it would be very interesting to find the appropriate ${ \mathcal N } = 4$ supersymmetric generalization of the affine Yangian.

The coset representations we have found exist for generic values of $N$ and $k$ ,while a direct twisted sector interpretation is only possible for the free field cases which correspond to $\lambda = 0$ (free fermions） and $\lambda = 1$ (free bosons). It would be interesting to understand whether these representations also have a natural interpretation away from these points, for example in terms of parafermions. Finally, it is intriguing that the structure of the coset representations is very similar in both cases to those representations that appear in the extension from the higher spin algebra to the Higher Spin Square, see eqs. (3.1) and (3.1O) in [11]. It would be very interesting to understand the reason underlying this.

# Acknowledgement

We thank Kevin Ferreira, Rajesh Gopakumar, Maximilian Kelm, Tomas Prochäzka, and Huafeng Zhang for helpful discussions. The research of SD is supported by a grant from the NCCR SwissMAP, funded by the Swiss National Science Foundation. We thank ICTP, Trieste and MIAPP, Munich for hospitality while part of this work was done. MRG and CP thank ITP of Chinese Academy of Science for hospitality, while WL thanks the ITP of ETH Zurich for hospitality.

# A The general form of level-1 representations

In this appendix we study the structure of a generic level-1 representation at arbitrary $\lambda$ . This can be done level by level from their Kac determinants. In the following, （20 $V _ { m } ^ { ( s ) }$ denotes the $\mathrm { { h s } } [ \lambda ]$ generator of spin $s$ and mode $m$ ：

# Level 2

At level 2,a general level-1 representation has three $\mathrm { { h s } } [ \lambda ]$ descendants,namely

$$
V _ { - 2 } ^ { ( 3 ) } \phi \quad , \quad V _ { - 2 } ^ { ( 4 ) } \phi \quad , \quad V _ { - 1 } ^ { ( 2 ) ^ { 2 } } \phi ~ .
$$

[It is not difficult to show that any other $\mathrm { { h s } } [ \lambda ]$ descendant can be written as a linear combination of these,using the commutation relations of the $\mathrm { { h s } } [ \lambda ]$ algebra,as well as the fact that there is only a single state at level-1.] We have worked out the inner product matrix of these states,and its determinant is of the form

$$
\begin{array} { r } { \mathrm { l e t } ( M _ { 2 } ) = 1 6 h ^ { 3 } \left( \alpha - 1 - \frac { \lambda } { 2 } \right) \left( \alpha - 1 + \frac { \lambda } { 2 } \right) \left( \alpha + 1 - \frac { \lambda } { 2 } \right) \left( \alpha + 1 + \frac { \lambda } { 2 } \right) \left( 2 h - \alpha ^ { 2 } + \frac { \lambda ^ { 2 } } { 4 } \right) \ . } \end{array}
$$

Thus the zeros appear at

$$
\mathrm { L e v e l \ 2 : } \qquad \alpha = \pm \biggl ( 1 \pm \frac { \lambda } { 2 } \biggr ) \ , \quad \alpha = \pm \frac { 1 } { 2 } \sqrt { 8 h + \lambda ^ { 2 } } \ ,
$$

where each root has a single multiplicity (and for the first expression the two minus signs are uncorrelated, i.e. this describes 4 different roots). The overall sign of $\alpha$ （204号 relates conjugate representations to one another (since the eigenvalue of $V _ { 0 } ^ { ( 3 ) }$ has opposite sign for conjugate representations, while the conformal dimension remains the same).

These roots have a simple interpretation in terms of familiar coset representations. It follows from the analysis of [40] that the minimal representations $( \boxed { \cdot } 0 )$ and $( 0 ; \boxed { \mathbf { \overline { { \mathbf { U } } } } } )$ (as well as their conjugates） have the eigenvalues

$$
\begin{array} { l } { { \displaystyle h \big ( ( \mit { \mit \Omega } ; 0 ) \big ) = \frac { 1 } { 2 } ( 1 + \lambda ) \ , \qquad w ^ { ( 3 ) } \big ( ( \mit { \Omega } ; 0 ) \big ) = - \frac { 1 } { 6 } ( 1 + \lambda ) ( 2 + \lambda ) \ , } } \\ { { \displaystyle h \big ( ( 0 ; \mit { \Omega } ) \big ) = \frac { 1 } { 2 } ( 1 - \lambda ) \ , \qquad w ^ { ( 3 ) } \big ( ( 0 ; \mit { \Omega } ) \big ) = \frac { 1 } { 6 } ( 1 - \lambda ) ( 2 - \lambda ) \ . } } \end{array}
$$

The corresponding $\alpha$ values are then

$$
\alpha \big ( ( \boldsymbol { \Sigma } ; 0 ) \big ) = - \Big ( 1 + \frac { \lambda } { 2 } \Big ) \ , \qquad \alpha ( \big ( 0 ; \boldsymbol { \Pi } \big ) \big ) = \Big ( 1 - \frac { \lambda } { 2 } \Big ) \ .
$$

These therefore account for the first four zeros of (A.3), including the corresponding conjugate representations. However, they actually also solve the last two equations of (A.3） since for $h = { \textstyle \frac { 1 } { 2 } } ( 1 \pm \lambda )$ ，

$$
{ \frac { 1 } { 2 } } \sqrt { 8 h + \lambda ^ { 2 } } = { \frac { 1 } { 2 } } \sqrt { 4 \pm 4 \lambda + \lambda ^ { 2 } } = \pm { \frac { 1 } { 2 } } ( 2 \pm \lambda ) \ .
$$

This reflects the fact that the minimal representations $( \boxed { \cdot } 0 )$ and $( 0 ; \boxed { \mathbf { \overline { { \mathbf { U } } } } } )$ (or their conjugates) have two null-vectors at level 2 - they only have a single wedge descendant at this level.

In order to identify the representations that have only a single null-vector (corresponding to a single zero) at level 2, we note that the symmetric tensor powers of the minimal $\mathrm { { h s } } [ \lambda ]$ representations8 satisfy

$$
\begin{array} { l } { { \displaystyle h \big ( ( [ 0 ^ { m - 1 } , 1 , 0 , \dots , 0 ] ; 0 ) \big ) = \frac { m } { 2 } ( 1 + \lambda ) ~ , } } \\ { { \displaystyle w ^ { ( 3 ) } \big ( ( [ 0 ^ { m - 1 } , 1 , 0 , \dots , 0 ] ; 0 ) \big ) = - \frac { m } { 6 } ( 1 + \lambda ) ( 2 + \lambda ) ~ , } } \\ { { \displaystyle h \big ( ( 0 ; [ 0 ^ { m - 1 } , 1 , 0 , \dots , 0 ] ) \big ) = \frac { m } { 2 } ( 1 - \lambda ) ~ , } } \\ { { \displaystyle w ^ { ( 3 ) } \big ( ( 0 ; [ 0 ^ { m - 1 } , 1 , 0 , \dots , 0 ] ) \big ) = \frac { m } { 6 } ( 1 - \lambda ) ( 2 - \lambda ) ~ . } } \end{array}
$$

These representations therefore account for one of the first four zeros of (A.3), including also the corresponding conjugate representations. However, for $m \geq 2$ ， they do not satisfy the last two zeros any longer. This is compatible with the fact that the corresponding wedge representations have two states at level 2, i.e. only have a single null-vector at that level.

On the other hand,a representation for which only one of the last two zeros is satisfied is given by the two-fold anti-symmetric tensor power of the minimal representation. Indeed, it follows from appendix B.3 of [41] that for example

$$
h \big ( ( [ 2 , 0 , \ldots , 0 ] ; 0 ) \big ) = 2 + \lambda , \qquad w ^ { ( 3 ) } \big ( ( [ 2 , 0 , \ldots , 0 ] ; 0 ) \big ) = - \frac { 1 } { 3 } ( 2 + \lambda ) ( 4 + \lambda ) ,
$$

where we have noted that the normalisation of $W ^ { ( 3 ) }$ in [41] differs by a factor of $\frac { 1 } { 6 }$ （204号 from the conventions of [40], see in particular eq. (5.8) of [41]. Thus $\alpha$ takes the value

$$
\alpha \big ( ( [ 0 , 1 , 0 , \dots , 0 ] ; 0 ) \big ) = - \frac { 1 } { 2 } \left( 4 + \lambda \right) = - \frac { 1 } { 2 } \sqrt { 8 ( 2 + \lambda ) + \lambda ^ { 2 } } \ .
$$

# Level 3

We have similarly determined the Kac-determinant (and in particular its zeros) at higher levels. At level 3, there are generically 6 independent vectors, for which a basis is given by

$$
V _ { - 3 } ^ { ( 4 ) } \phi ~ , ~ V _ { - 3 } ^ { ( 5 ) } \phi ~ , ~ V _ { - 3 } ^ { ( 6 ) } \phi ~ , ~ V _ { - 1 } ^ { ( 2 ) } V _ { - 2 } ^ { ( 3 ) } \phi ~ , ~ V _ { - 1 } ^ { ( 2 ) } V _ { - 2 } ^ { ( 4 ) } \phi ~ , ~ V _ { - 1 } ^ { ( 2 ) } V _ { - 1 } ^ { ( 2 ) } V _ { - 1 } ^ { ( 2 ) } \phi ~ .
$$

The corresponding Kac determinant is then

$$
\begin{array} { c } { { \mathrm { 1 e t } ( M _ { 3 } ) = \displaystyle \frac { 3 h ^ { 6 } } { 1 6 3 8 4 } ( 2 \alpha - \lambda - 4 ) ( 2 \alpha - \lambda - 2 ) ^ { 3 } ( 2 \alpha - \lambda + 2 ) ^ { 3 } ( 2 \alpha - \lambda + 4 ) ( 2 \alpha + \lambda - 4 ) } } \\ { { ( 2 \alpha + \lambda - 2 ) ^ { 3 } ( 2 \alpha + \lambda + 2 ) ^ { 3 } ( 2 \alpha + \lambda + 4 ) \left( - 4 \alpha ^ { 2 } + 4 h + \lambda ^ { 2 } \right) } } \\ { { \left( - 4 \alpha ^ { 2 } + 8 h + \lambda ^ { 2 } \right) ^ { 3 } ~ , } } \end{array}
$$

and its 24 zeros arise for

$$
\begin{array} { r } { \alpha = \pm \left( 1 \pm \frac { \lambda } { 2 } \right) , \quad \pm \frac { 1 } { 2 } \sqrt { 8 h + \lambda ^ { 2 } } , } \\ { \pm \left( 2 \pm \frac { \lambda } { 2 } \right) , \quad \pm \frac { 1 } { 2 } \sqrt { 4 h + \lambda ^ { 2 } } . } \end{array}
$$

Here each of the zeros that appeared already at level 2 - these are the zeros of the first line — has multiplicity 3, while the new zeros have multiplicity one. The new roots are satisfied for the anti-symmetric two-fold tensor product of the minimal representation, see e.g. eq. (A.11） - together with the representation associated to the other minimal representation as well as their conjugates, this accounts for the first four new roots. The last two new roots are attained for the 2-fold symmetric tensor power of the minimal representation, see eqs. (A.8） and (A.9) with $m = 2$

# Level 4

At level 4, there are generically 13 states, and the 78 roots of the corresponding Kac determinant (including multiplicities) are

$$
\begin{array} { l } { { \alpha = \pm \left( 1 \pm \displaystyle \frac { \lambda } { 2 } \right) ~ , ~ \pm \displaystyle \frac { 1 } { 2 } \sqrt { 8 h + \lambda ^ { 2 } } ~ , } } \\ { { \pm \left( 2 \pm \displaystyle \frac { \lambda } { 2 } \right) ~ , ~ \pm \displaystyle \frac { 1 } { 2 } \sqrt { \frac { 8 } { 2 } h + \lambda ^ { 2 } } ~ , } } \\ { { \pm \left( 3 \pm \displaystyle \frac { \lambda } { 2 } \right) ~ , ~ \pm \displaystyle \frac { 1 } { 2 } \sqrt { \frac { 8 } { 3 } h + \lambda ^ { 2 } } ~ , } } \\ { { \pm \displaystyle \frac { 1 } { 2 } \sqrt { \lambda ^ { 2 } - 8 h } ~ . } } \end{array}
$$

The roots in (A.15) appear already at level 2, while those in (A.15) and (A.16) appear at level 3; these roots therefore each have higher multiplicity.9 The new roots (that appear with multiplicity one) are therefore associated to the solutions in (A.17) and (A.18). The roots in (A.17) are associated to the totally anti-symmetric three-fold tensor product of the minimal representation — this accounts for the first four roots of (A.17) - and the totally symmetric three-fold tensor product of the minimal representation — this accounts for the last two roots of (A.17). On the other hand, the roots in line (A.18) are of a different form,and they are the ones that are relevant for the bosonic twisted representation, see eqs. (B.15) -(B.16).

# Level 5

We have also performed the corresponding analysis at level 5, where the generic level-one representation has 24 states,and where the Kac determinant has 192 roots (including multiplicities). In addition to the roots that appeared already at level 4, see eqs. (A.15) - (A.18), the new roots that appear at level 5 are of the form

$$
\pm \left( 4 \pm { \frac { \lambda } { 2 } } \right) , \qquad \pm { \frac { 1 } { 2 } } \sqrt { { \frac { 8 } { 4 } } h + \lambda ^ { 2 } } ,
$$

and are hence of the same structural form as in (A.15) -(A.17). In particular, they correspond to the totally symmetric and anti-symmetric four-fold tensor product of the minimal representation.

# BThe spin 3 charge of some simple representations

In order to identify the appropriate representations that realize these roots, we need to calculate both the conformal dimension as well as the $w ^ { ( 3 ) }$ eigenvalue of level-one representations. In this section we recall how the spin 3 charge can be determined, using the Drinfeld-Sokolov approach.

The coset representations are labelled by pairs of $\mathfrak { s u } ( N )$ representations $( \Lambda _ { + } ; \Lambda _ { - } )$ For each such $\Lambda$ ， we denote by $r _ { i }$ the number of boxes in the $i$ ’th row of the corresponding Young diagram. Then, in the orthonormal basis,the weight $\Lambda$ has components (see e.g. appendix A of [41])

$$
\Lambda _ { i } = r _ { i } - \frac { B } { N } ~ , \qquad i = 1 , \dots , N ~ ,
$$

where $B$ is the total number of boxes $\textstyle \sum _ { i } r _ { i }$ and ( $r _ { N } \equiv 0$ ). The Weyl vector $\rho$ has the components

$$
\rho _ { i } = \frac { N + 1 } { 2 } - i \ , \qquad i = 1 , \dots , N \ .
$$

Note that, by construction， we have $\textstyle \sum _ { i } \Lambda _ { i } = 0$ and $\textstyle \sum _ { i } \rho _ { i } = 0$ .Following [42],we also define the vector $\theta$ as

$$
\theta = \alpha _ { + } ( \Lambda ^ { + } + \rho ) + \alpha _ { - } ( \Lambda ^ { - } + \rho ) ~ , \quad \mathrm { w h e r e } \quad \alpha _ { + } = \sqrt { \frac { N + k + 1 } { N + k } } , \quad \alpha _ { - } = - \frac { 1 } { \alpha _ { + } } ~ ,
$$

and introduce the power sums $C _ { s } ( \theta )$ [42-44]

$$
C _ { s } ( \theta ) = \frac { 1 } { s } \sum _ { i } ( \theta _ { i } ) ^ { s } ~ = \frac { ( - 1 ) ^ { s - 1 } } { s } \sum _ { i _ { 1 } < i _ { 2 } < \cdots < i _ { s } } \theta _ { i _ { 1 } } \theta _ { i _ { 2 } } \cdot \cdot \cdot \theta _ { i _ { s } } ~ .
$$

In terms of these quantities, the conformal dimension and spin 3 charge of $( \Lambda _ { + } ; \Lambda _ { - } )$ in the‘primary basis’ is then [42, 44]

$$
\begin{array} { l } { { \displaystyle h \big ( ( \Lambda _ { + } ; \Lambda _ { - } ) \big ) = C _ { 2 } ( \theta ) + \frac { c - N + 1 } { 2 4 } } } \\ { { \displaystyle w ^ { ( 3 ) } \big ( ( \Lambda _ { + } ; \Lambda _ { - } ) \big ) = C _ { 3 } ( \theta ) ~ . } } \end{array}
$$

As a consistency check we note that, for the minimal representation $\Lambda _ { + } = \sqcup$ ,we find

$$
\begin{array} { l } { { \displaystyle h ( \Omega ; 0 ) = \frac { N - 1 } { 2 N } \frac { 1 + k + 2 N } { N + k } } } \\ { { \displaystyle w ^ { ( 3 ) } ( \Omega ; 0 ) = \frac { ( N - 1 ) ( N - 2 ) } { 6 N ^ { 2 } } \frac { ( 1 + k + 2 N ) ( 2 + 2 k + 3 N ) } { ( N + k ) ^ { 3 / 2 } ( N + k + 1 ) ^ { 1 / 2 } } . } } \end{array}
$$

Similarly, we find for example for the representation $( [ 0 ^ { b - 1 } , 1 , 0 , \dots , 0 ] ; 0 )$

$$
\begin{array} { l } { { \displaystyle h ( [ 0 ^ { b - 1 } , 1 , 0 , \dots , 0 ] ; 0 ) = \frac { b ( N - b ) } { 2 N } \frac { 1 + k + 2 N } { N + k } } } \\ { { \displaystyle w ^ { ( 3 ) } ( [ 0 ^ { b - 1 } , 1 , 0 , \dots , 0 ] ; 0 ) = \frac { b ( N - b ) ( N - 2 b ) } { 6 N ^ { 2 } } \frac { ( 1 + k + 2 N ) ( 2 + 2 k + 3 N ) } { ( N + k ) ^ { 3 / 2 } ( N + k + 1 ) ^ { 1 / 2 } } , } } \end{array}
$$

so that in the ’t Hooft limit (for finite $b \ll N , k$ ））

$$
\begin{array} { l } { { \displaystyle h ( [ 0 ^ { b - 1 } , 1 , 0 , \dots , 0 ] ; 0 ) = b h ( \bigtriangledown ; 0 ) \cong \frac { b } { 2 } ( 1 + \lambda ) } } \\ { { \displaystyle w ^ { ( 3 ) } ( [ 0 ^ { b - 1 } , 1 , 0 , \dots , 0 ] ; 0 ) = b w ^ { ( 3 ) } ( \bigtriangledown ; 0 ) \cong \frac { b } { 6 } ( 1 + \lambda ) ( 2 + \lambda ) ~ . } } \end{array}
$$

This approach also allows us to calculate the charges of representations for which both $\Lambda _ { + }$ and $\Lambda _ { - }$ are non-trivial. For example, for the representation $( \boldsymbol { \mathbf { \rho } } _ { \Xi } ; \boldsymbol { \mathbf { \rho } } _ { \Xi } )$ we find

$$
\begin{array} { c } { { \displaystyle h ( \bigtriangledown ; \bigtriangledown ) = \frac { \big ( N - 1 \big ) ( N + 1 ) } { 2 N ( N + k ) ( N + k + 1 ) } } } \\ { { \displaystyle w ^ { ( 3 ) } ( \bigtriangledown ; \bigtriangledown ) = \frac { ( N - 2 ) ( N - 1 ) ( N + 1 ) ( N + 2 ) } { 6 N ^ { 2 } ( k + N ) ^ { 3 / 2 } ( k + N + 1 ) ^ { 3 / 2 } } } } \\ { { \displaystyle \alpha ( \bigtriangledown ; \bigtriangledown ) = \frac { 3 w ^ { ( 3 ) } } { 2 h } = \frac { \left( N - 2 \right) ( N + 2 ) } { 2 N \sqrt { k + N } \sqrt { k + N + 1 } } \stackrel { \ast \mathrm { ~ H o o f t ~ } } { \approx } \frac { 1 } { 2 } \frac { N } { N + k } = \frac { \lambda } { 2 } , } } \end{array}
$$

where we have taken the 't Hooft limit in the last step. Note that the correct value of $\alpha$ in the 't Hooft limit can only be determined from the exact expression of $h$ and $w ^ { ( 3 ) }$ at finite $( N , k )$ since the 't Hooft limit of both $h$ and $w ^ { ( 3 ) }$ separately vanishes.

For the representations that describe the ground states of a single twisted boson, i.e. the representations with Dynkin labels $( [ 0 ^ { b - 1 } , 1 , 0 , \ldots , 0 ] ; [ 0 ^ { b - 1 } , 1 , 0 , \ldots , 0 ] )$ ，we then find

$$
\begin{array} { l } { { h = { \displaystyle \frac { b ( N + 1 ) ( N - b ) } { 2 N ( k + N ) ( k + N + 1 ) } } } } \\ { { \alpha = { \displaystyle \frac { ( N - 2 b ) ( N + 2 ) } { 2 N \sqrt { k + N } \sqrt { k + N + 1 } } } . } } \end{array}
$$

As explained in eq. (2.33), in the 't Hooft limit this solves the root of eq. (A.18) that appears first at level 4.

For the representations that describe the ground states of a single twisted fermion, i.e. the representations with Dynkin labels $( [ b , 0 , \dots , 0 ] ; [ b , 0 , \dots , 0 ] )$ ，we find instead

$$
\begin{array} { l } { { h = { \displaystyle \frac { b ( N - 1 ) ( N + b ) } { 2 N ( k + N ) ( k + N + 1 ) } } } } \\ { { \alpha = { \displaystyle \frac { ( N + 2 b ) ( N - 2 ) } { 2 N \sqrt { k + N } \sqrt { k + N + 1 } } } . } } \end{array}
$$

Upon setting $b = \nu k$ ，we have (in the‘t Hooft limit)

$$
\begin{array} { l } { { \displaystyle h ( b = \nu k ) \cong \frac { \nu } { 2 } ( 1 - \lambda ) ( \lambda ( 1 - \nu ) + \nu ) } } \\ { { \displaystyle \alpha ( b = \nu k ) \cong \frac { 1 } { 2 } ( \lambda ( 1 - 2 \nu ) + 2 \nu ) = \frac { 1 } { 2 } \sqrt { \lambda ^ { 2 } + 8 h ( b = \nu k ) } \ , } } \end{array}
$$

which is a root that first appears at level 2, see eq. (A.3)

# C Combinatorial description of wedge characters

In this appendix we outline a proof for the combinatorial identity between $p _ { 2 } ( n , \ell )$ and $p _ { 2 } ( n )$ of eq. (2.15). The identity for $\ell = 0$ is given and proven in [35]； in the following we will generalize it to generic $\ell$ . Let us first consider the case of $\ell \geq 0$

Recall that $p _ { 2 } ( n , \ell )$ counts the configurations that can be obtained from a pair of Young diagrams $\langle \Gamma ^ { + } ; \Gamma ^ { - } \rangle _ { n , \ell }$ with first columns of height $c _ { 1 } ^ { + } = c _ { 1 } ^ { - } + \ell$ by gluing them along their common first column,and removing the $\ell$ superfluous boxes of $\Gamma ^ { + }$ from the bottom, see Figure 1. Here $n$ is the number of‘visible’ boxes after the gluing.

On the other hand, $p _ { 2 } ( n )$ counts (ordered) pairs of Young diagrams $( \Gamma ^ { ( 1 ) } , \Gamma ^ { ( 2 ) } ) _ { n }$ whose total number of boxes is $n$ . To each such pair we can associate an element $\langle \Gamma ^ { + } ; \Gamma ^ { - } \rangle _ { n , \ell }$ , by shifting $\Gamma ^ { ( 2 ) }$ （ $\ell$ steps upwards and then placing it to the right of $\Gamma ^ { ( 1 ) }$ ， without leting anycolumns overlap.Aslongasc≤c2+l, wechoosethefirst column of $\Gamma ^ { ( 2 ) }$ as the ‘shared’ column of $\langle \Gamma ^ { + } ; \Gamma ^ { - } \rangle _ { n , \ell }$ ; otherwise we move $\ell$ boxes from the bottom of the first column of $\Gamma ^ { ( 1 ) }$ to the top so that this column becomes the 'shared' column.

This map is wel-defined and surjective, but it is not injective. In particular, if $c _ { 1 } ^ { - } > c _ { 2 } ^ { - } + \ell$ there are precisely two pairs of Young diagrams $( \Gamma ^ { ( 1 ) } , \Gamma ^ { ( 2 ) } ) _ { n }$ that give rise to the same configuration $\langle \Gamma ^ { + } ; \Gamma ^ { - } \rangle _ { n , \ell }$ - we can move $\ell$ boxes from the top of the first column of $\Gamma ^ { ( 2 ) }$ to the bottom, and then adjoin the corresponding column to $\Gamma ^ { ( 1 ) }$ . Therefore, if we start with $p _ { 2 } ( n )$ ， we now have to subtract $p _ { 2 } ( n - \ell - 1 )$ from it，since the diagrams that are overcounted in this manner can all be constructed from configurations $( \Gamma ^ { ( 1 ) } , \Gamma ^ { ( 2 ) } ) _ { n - \ell - 1 }$ : we simply add $\ell + 1$ boxes to the frst column of $\Gamma ^ { ( 2 ) }$ , and thus guarantee that after joining we have $c _ { 1 } ^ { - } > c _ { 2 } ^ { - } + \ell$ in the resulting （204号 $\langle \Gamma ^ { + } ; \Gamma ^ { - } \rangle _ { n , \ell }$ configuration. But subtracting $p _ { 2 } ( n - \ell - 1 )$ is an overkill - we now have to add back those configurations for which $c _ { 1 } ^ { - } > c _ { 2 } ^ { - } + \ell > c _ { 3 } ^ { - } + \ell$ ， and these cases are captured by $( \Gamma ^ { ( 1 ) } , \Gamma ^ { ( 2 ) } ) _ { n - ( \ell + 1 ) - ( \ell + 2 ) }$ since now we have to put $\ell + 1$ boxes on the second column of $\Gamma ^ { ( 2 ) }$ ，and $\ell + 2$ boxes on the first so as to guarantee that we end up with a configuration with $c _ { 1 } > c _ { 2 } ^ { - } + \ell > c _ { 3 } ^ { - } + \ell$ . Recursively proceeding in this manner we then arrive at the formula

$$
p _ { 2 } ( n , \ell ) = \sum _ { m = 0 } ( - 1 ) ^ { m } p _ { 2 } \Big ( n - \sum _ { k = \ell + 1 } ^ { \ell + m } k \Big ) \qquad \quad \ell \geq 0 ~ .
$$

This proves eq. (2.15) for $\ell \geq 0$ ; the argument for $\ell < 0$ is identical upon interchanging the roles of $\Gamma ^ { + }  \Gamma ^ { - }$ and $\Gamma ^ { ( 1 ) }  \Gamma ^ { ( 2 ) }$

# References

[1] M.A. Vasiliev,“Nonlinear equations for symmetric massless higher spin fields in (A)dS(d),” Phys. Lett.B 567 (2003)139 [arXiv:hep-th/0304049].   
[2] B. Sundborg,“Stringy gravity, interacting tensionless strings and massess higher spins,” Nucl.Phys.Proc. Suppl. 102(2001) 113 [arXiv:hep-th/0103247].   
[3] E. Witten, talk at the John Schwarz 6O-th birthday symposium (Nov. 2001), http://theory.caltech.edu/jhs6o/witten/1.html.   
[4] A. Mikhailov,“Notes on higher spin symmetries,” arXiv:hep-th/0201019.   
[5] I.R. Klebanov and A.M. Polyakov, “AdS dual of the critical O(N) vector model," Phys.Lett.B 550 (2002) 213 [arXiv:hep-th/0210114].   
[6] E. Sezgin and P. Sundell, “Holography in 4D (super) higher spin theories and a test via cubic scalar couplings,” JHEP 0507 (2005) 044 [arXiv:hep-th/0305040].   
[7] M.R. Gaberdiel and R. Gopakumar,“An AdS3 dual for minimal model CFTs," Phys.Rev.D 83(2011) 066007 [arXiv:1011.2986 [hep-th]]. fields to strings,” J. Phys. A: Math. Theor.46 (2013) 214009 [arXiv:1207.4485 [hep-th]]. [9] M.R. Gaberdiel and R. Gopakumar,“Higher Spins & Strings,” JHEP 1411 (2014) 044 [arXiv:1406.6103 [hep-th]].   
[10] M.R.Gaberdiel and R. Gopakumar,“Large ${ \mathcal N } = 4$ holography,” JHEP 1309 (2013) 036[arXiv:1305.4181 [hep-th]].   
[11] M.R. Gaberdiel and R. Gopakumar, “Stringy Symmetries and the Higher Spin Square,”J. Phys. A 48(2015) 185402 [arXiv:1501.07236 [hep-th]].   
[12] M.R. Gaberdiel and R. Gopakumar,“String Theory as a Higher Spin Theory,” arXiv:1512.07237 [hep-th].   
[13] M. Baggio, M.R. Gaberdiel and C. Peng,“Higher spins in the symmetric orbifold of K3,”Phys.Rev.D 92 (2015) 026007 [arXiv:1504.00926 [hep-th]].   
[14] M.R. Gaberdiel, C. Peng and I.G. Zadeh,“Higgsing the stringy higher spin symmetry,” JHEP 1510 （2015） 101 [arXiv:1506.02045 [hep-th]].   
[15] M.R. Gaberdiel and M. Kelm,“The symmetric orbifold of N=2 minimal models,” arXiv:1604.03964 [hep-th].   
[16] A. Jevicki and J. Yoon,“ $S _ { N }$ Orbifolds and String Interactions,” J. Phys. A 49 (2016) 205401 [arXiv:1511.07878 [hep-th]].   
[17] M.R.Gaberdiel and M. Kelm,“The continuous orbifold of ${ \mathcal N } = 2$ minimal model holography,” JHEP 1408（2014) 084 [arXiv:1406.2345 [hep-th]].   
[18] B.Feigin,E.Feigin,M. Jimbo,T.Miwa and E. Mukhin,“Quantum Continuous （20 ${ \mathfrak { g l } } _ { \infty }$ : Semi-infinite construction of representations,” Kyoto J. Math. 51, no. 2 (2011) 337 [arXiv:1002.3100 [math.QA]].   
[19] B.Feigin,E. Feigin,M. Jimbo,T.Miwa and E. Mukhin,“Quantum Continuous glo: Tensor Products of Fock Modules and ${ \mathcal { W } } _ { n }$ Characters,” Kyoto J. Math. 51, no. 2（2011)365 [arXiv:1002.3113 [math.QA]].   
[20] B.Feigin, M. Jimbo, T. Miwa and E. Mukhin,“Quantum toroidal ${ \mathfrak { g l } } _ { 1 }$ algebra: plane partitions,” Kyoto J. Math. 52,no.3(2012) 621 [arXiv:1110.5310 [math.QA]]   
[21] T. Procházka,“W-symmetry, topological vertex and afine Yangian,"” arXiv:1512.07178 [hep-th].   
[22] M.R.Gaberdiel and R. Gopakumar,“Triality in Minimal Model Holography,” JHEP 1207(2012) 127 [arXiv:1205.2472 [hep-th]].   
[23] S. Gautam and V. Toledano-Laredo,“Yangians and quantum loop algebras,” Selecta Mathematica 19 (2013) 271 [arXiv:1012.3687 [math.QA]].   
[24] A. Tsymbaliuk, “The affine Yangian of ${ \mathfrak { g l } } _ { 1 }$ revisited,” arXiv:1404.5240 [math.RT].   
[25] O. Ohlsson Sax and B. Stefanski, “Integrability, spin-chains and the AdS3/CFT2 correspondence,” JHEP 1108 (2011) 029 [arXiv:1106.2558 [hep-th]].   
[26] O. Ohlsson Sax, B. Stefanski, and A. Torrielli,“On the massless modes of the AdS3/CFT2 integrable systems,” JHEP 1303 (2013) 109 [arXiv:1211.1952 [hep-th]].   
[27] R.Borsato, O. Ohlsson Sax,A. Sfondrini and B. Stefaski, “The $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ worldsheet S matrix,” J. Phys. A 48 (2015) no.41, 415401 [arXiv:1506.00218 [hep-th]].   
[28] A. Sfondrini, “Towards integrability for AdS3/CFT2,” arXiv:1406.2971 [hep-th:   
[29] E. Bergshoeff, M.P. Blencowe and K.S. Stelle, “Area Preserving Diffeomorphisms and Higher Spin Algebra,” Commun. Math. Phys.128(1990) 213.   
[30] E. Bergshoeff, C.N. Pope, L.J. Romans, E. Sezgin and X. Shen,“The Super W(infinity） Algebra,” Phys. Lett. B 245(1990) 447.   
[31] D.A. Depireux, “Fermionic realization of W(1+infinity),” Phys. Lett. B 252 (1990) 586.   
[32] I. Bakas and E. Kiritsis,“Bosonic realisation of a universal W algebra and $\mathbb { Z } _ { \infty }$ parafermions,” Nucl. Phys. B 343 (1990) 185 [Erratum ibid. B 350, 512 (1991)].   
[33] M.R. Gaberdiel, K. Jin, and W. Li, “Perturbations of $\mathcal { W } _ { \infty }$ CFTs,” JHEP 1310 (2013) 162 [arXiv:1307.4087 [hep-th]].   
[34] M.R. Gaberdiel and P. Suchanek, “Limits of Minimal Models and Continuous Orbifolds,” JHEP 1203 (2012)104 [arXiv:1112.1708 [hep-th]].   
[35] R.P. Stanley,“Enumerative combinatorics,” vol 1. 2nd ed., Cambridge University Press (2012).   
[36] J. Keane, posted on the ‘On-line encyclopedia of integer sequences', https://oeis.0rg/A000712 (2002).   
[37] G.H. Hardy and S. Ramanujan, “Asymptotic Formulae in Combinatory Analysis,” Proc. London Math. Soc.17(1918） 75.   
[38] E. Wright,“Asymptotic partition formulae I. Plane partitions,” The Quarterly Journal of Mathematics,1 (1931) 177.   
[39] M. Bershtein, B. Feigin and G. Merzon,“Plane partitions with a ‘pit': generating functions and representation theory,” [arXiv:1512.08779 [math-C0]].   
[40] M.R. Gaberdiel and T. Hartman,“Symmetries of Holographic Minimal Models," JHEP 1105（2011) 031 [arXiv:1101.2910 [hep-th]].   
[41] M.R. Gaberdiel, R. Gopakumar, T. Hartman, and S. Raju, “Partition functions of holographic minimal models,” JHEP 1108 (2011) 077 [arXiv:1106.1897 [hep-th]].   
[42] E. Perlmutter, T. Prochazka, and J. Raeymaekers,“The semiclassical limit of W $N$ （204号 CFTs and Vasiliev theory,” JHEP 1305 (2013) 007 [arXiv:1210.8452 [hep-th]]   
[43] A. Castro, R. Gopakumar, M. Gutperle, and J. Raeymaekers,“Conical defects in higher spin theories,” JHEP 1202 (2012) 096 [arXiv:1111.3381 [hep-th]].   
[44] P. Bouwknegt and K. Schoutens,“W symmetry in conformal field theory,” Phys. Rept. 223 (1993)183 [arXiv:hep-th/9210010].   
[45] A.N. Sergeev,“Representations of the Lie superalgebras gl(n,m) and Q(n) on the space of tensors,” Funct. Anal. Appl. 18(1984） 70.   
[46] A. Berele and A. Regev,“Hook Young diagrams with applications to combinatorics and to representations of Lie superalgebras,” Adv. Math. 64(1987)118.   
[47] C. Candu and M.R.Gaberdiel, “Supersymmetric holography on $A d S _ { 3 }$ ,” JHEP 1309 (2013)071 [arXiv:1203.1939 [hep-th]].