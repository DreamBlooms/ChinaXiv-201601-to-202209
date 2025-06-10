# BPS spectrum on $\mathbf { A d S _ { 3 } } { \times } \mathbf { S ^ { 3 } } { \times } \mathbf { S ^ { 3 } } { \times } \mathbf { S ^ { 1 } }$

Lorenz Eberhardtα，Matthias R. Gaberdielα，Rajesh Gopakumar,and Wei Li

a Institut fir Theoretische Physik, ETH Zurich, CH-8093 Zirich, Switzerland   
$b$ International Centre for Theoretical Sciences-TIFR, Survey No. 151，Shivakote,Hesaraghatta Hobli, Bengaluru North,India 560 089   
$c$ Institute of Theoretical Physics, Chinese Academy of Science 100190 Beijing, P.R. China   
E-mail: eberhardtl@itp.phys.ethz.ch,   
gaberdiel@itp.phys.ethz.ch,   
rajesh.gopakumar@icts.res.in， weili@itp.ac.cn

ABSTRACT: The BPS spectrum of string theory on $\mathrm { A d S _ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 1 } }$ is determined using a world-sheet description in terms of WZW models. It is found that the theory only has BPS states with $j ^ { + } = j ^ { - }$ where $j ^ { \pm }$ refer to the spins of the $\mathfrak { s u } ( 2 )$ algebras of the large $\mathcal { N } = 4$ superconformal algebra. We then re-examine the BPS spectrum of the corresponding supergravity and find that, in contradistinction to previous claims in the literature, also in supergravity only the states with $j ^ { + } = j ^ { - }$ are BPS. This resolves a number of long-standing puzzles regarding the BPS spectrum of string theory and supergravity in this background.

# Contents

1 Introduction 2

2The world-sheet analysis 4

2.1 The spacetime BPS spectrum 5   
2.2 Supergravity interpretation 8

3Supergravity approach 9

3.1 The 9d vacuum solution 9   
3.2 Equations of motion for quadratic perturbations 12   
3.3 Expanding the Fields 13   
3.4 The scalars from the decoupled subsystem 14   
3.5 The scalars from the remaining fields 16   
3.6 The full scalar spectrum 16

# 4Discussion and Outlook 18

# A BPS representations of $D ( 2 , 1 | \alpha )$ and the ${ \mathcal N } = 4$ algebra 19

A.1 The $D ( 2 , 1 | \alpha )$ algebra 19   
A.1.1 BPS representations 20   
A.2 The large ${ \mathcal { N } } = 4$ superconformal algebra 21   
A.2.1 The BPS Bound 21

B The supergravity analysis 22

B.1 Harmonic Expansion on $\mathrm { S _ { + } ^ { 3 } \times S _ { - } ^ { 3 } }$ 22   
B.2 Splitting the Equations of Motion 23   
B.3 Scalar Part of the Equations of Motion 25

Special cases at low $\ell ^ { \pm }$ （204号 29

C.1 Residual gauge transformations 29   
C.2Metric, Dilaton and Kalb-Ramond Field 30   
C.2.1 （20 $\ell ^ { + } > 1$ ， $\ell ^ { - } = 1$ （204号 30   
C.2.2 （20 $\ell ^ { + } = 1$ ， $\ell ^ { - } > 1$ （20 31   
C.2.3 （204号 $\ell ^ { + } = \ell ^ { - } = 1$ （20 31   
C.2.4 $\ell ^ { + } > 1$ ， $\ell ^ { - } = 0$ （20 31   
C.2.5 （20 $\ell ^ { + } = 0$ ， $\ell ^ { - } > 1$ （20 31   
C.2.6 （204号 $\ell ^ { + } = 0$ ， $\ell ^ { - } = 1$ （20 32   
C.2.7 （204号 $\ell ^ { + } = 1$ ， $\ell ^ { - } = 0$ （2 32   
C.2.8 （20 $\ell ^ { + } = \ell ^ { - } = 0$ （20 32

C.3 The scalars from the decoupled subsystem 33

# 1 Introduction

For the case of AdS $^ 3$ ， the AdS/CFT correspondence has been understood in quite some detail. In particular, there is very convincing evidence that the CFT dual of string theory on A $\mathrm { \Delta \Omega \backslash d S _ { 3 } \times S ^ { 3 } \times \mathcal { M } _ { 4 } }$ is (on the moduli space of） the symmetric orbifold of $\mathcal { M } _ { 4 }$ ，where $\mathcal { M } _ { 4 } = \mathbb { T } ^ { 4 }$ or $\mathcal { M } _ { 4 } = \mathrm { K 3 }$ , see e.g. [1] for a review. For example, the BPS spectrum of the two descriptions matches perfectly, and their correlation functions agree [2-4]. More recently, it was also found that the symmetric orbifold is a natural extension of the CFT dual of a supersymmetric higher spin theory on AdS $^ 3$ [5].For either choice of $\mathcal { M } _ { 4 }$ , the dual CFT has the (small) $\mathcal { N } = 4$ superconformal symmetry [6-8].

On the other hand, the situation is much less clear [9] for the other maximally supersymmetric AdS $^ 3$ background $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ , and no convincing proposal for what precisely the dual CFT should be exists to date, see however [1O] for a recent attempt. This is a bit surprising since the corresponding dual CFT has an even larger symmetry algebra, the so-called large ${ \mathcal N } = 4$ superconformal algebra $A _ { \gamma }$ [11], see also [12-15]. One of the reasons why the case with large ${ \mathcal N } = 4$ superconformal symmetry is more diffcult is related to the fact that the BPS bound for $A _ { \gamma }$ is in general stronger than the corresponding BPS bound [16-18] of the supergravity symmetry algebra $D ( 2 , 1 | \alpha )$ [19].Both algebras contain an ${ \mathfrak { s u } } ( 2 ) \oplus { \mathfrak { s u } } ( 2 )$ subalgebra,and the BPS bounds for the two algebras only agree if the spins with respect to these two algebras $( j ^ { + } , j ^ { - } )$ coincide, $j ^ { + } = j ^ { - }$ .In particular, this leads to the somewhat mysterious phenomenon that any supergravity BPS state with $j ^ { + } \neq j ^ { - }$ has to acquire nontrivial quantum corrections upon quantisation in order to satisfy (let alone saturate) the BPS bound of $A _ { \gamma }$ [9,19]. This is not just a theoretical possibility since, according to the analysis of [19], such BPS states exist in supergravity.

In this paper we revisit this somewhat unsatisfactory situation. We begin by studying string theory on $\mathrm { A d S _ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 1 } }$ from a world-sheet prespective, following the analysis of [20]. The relevant background has pure NS-NS flux, and the AdS $^ 3$ （204号 factor is described by a WZW model associated to ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ as in [21],while for the $\mathrm { S ^ { 3 } }$ factors we have the familiar $\mathfrak { s u } ( 2 )$ WZW models. It was shown in [20] that the spacetime CFT (i.e.， the dual CFT） has large $\mathcal { N } = 4$ superconformal symmetry $A _ { \gamma }$ . Thus we can analyse which states of the spacetime spectrum saturate the $A _ { \gamma }$ BPS bound, and we find that the only states with this property have $j ^ { + } = j ^ { - }$ ： Furthermore, since string theory reduces to supergravity in the limit of vanishing string size, our analysis also leads to a prediction for what the supergravity BPS spectrum should be. This suggests that all the BPS states of supergravity also have $j ^ { + } = j ^ { - }$ ：

Given that this conclusion is in contradiction to the claim of [19],we perform then a first principle supergravity analysis, following the strategy of [22] suitably adjusted to the current setting. We should stress that this somewhat tedious analysis was not done in [19] where it was simply assumed that for each harmonic there would be a BPS state - as was indeed the case for $\mathrm { A d S _ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathcal { M } _ { 4 }$ with $\mathcal { M } _ { 4 } = \mathbb { T } ^ { 4 }$ or K3. Using this assumption the BPS states were then organised into supermultiplets, using group theoretic methods [19].

In our analysis, we start with 9-dimensional supergravity (with a pure NS-NS background) and compactify it on $\mathrm { S ^ { 3 } \times S ^ { 3 } }$ , making an expansion in terms of spherical harmonics on the two spheres. We will concentrate on the scalar fields coming from the NS-NS fields in 9 dimensions; this is sufficient for the analysis of the BPS spectrum since every BPS multiplet in the list of [19] contains at least one such field. The resulting field equations are then Klein-Gordon equations from the viewpoint of $\mathrm { A d S _ { 3 } }$ , and hence we can easily read offtheir masses as a function of the spins along the two $\mathrm { S ^ { 3 } }$ 's. The analysis is however quite tedious, but with the help of Mathematica,1 we have managed to find all eigenfunctions and identify their corresponding masses. The result turns out to be exactly as predicted from the world-sheet analysis: the only BPS states of supergravity appear for $j ^ { + } = j ^ { - }$ ：

This is the main result of this paper. As was alluded to before, it resolves the puzzle about the mysterious quantum corrections of supergravity BPS states: the only BPS states that would have to behave in this manner arise for $j ^ { + } \neq j ^ { - }$ -and the resolution is simply that no such supergravity BPS states exist! In fact,our analysis also shows that the actual masses of the supergravity states with $j ^ { + } \neq j ^ { - }$ do not just obey the supergravity BPS bound, but in fact also the stronger $A _ { \gamma }$ BPS bound (and saturate neither).

As a consequence of our analysis, also the question about the CFT dual to string theory on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ needs to be re-examined. In particular, the most natural candidate theory at least for the case when the two $\mathrm { S ^ { 3 } }$ 's have the same size, the symmetric orbifold of the so-called $S _ { 0 }$ theory [9, 20],was largely discarded in [9] because of its failure to reproduce the BPS spectrum of supergravity - but since the latter was wrongly identified, this conclusion does not hold any more. In fact, it now seems that this symmetric orbifold is a viable candidate, and we are in the process of exploring this possibility further [23].

The paper is organised as follows. In Section 2 we review the world-sheet description of this background and then analyse its spacetime BPS spectrum. The main result of this section is eq. (2.9) which gives a lower bound on the conformal dimension of any spacetime state as a function of its spins. It follows from this bound that the only BPS states arise for $j ^ { + } = j ^ { - }$ .We furthermore speculate in

Section 2.2 what the supergravity incarnation of this result should be. In Section 3 we then perform the supergravity analysis from first principles: we first determine the 9-dimensional vacuum solution (Section 3.1)，and deduce the equations of motion for the fluctuations around this vacuum solution (Section 3.2). The various components are then expanded in terms of spherical harmonics (Section 3.3)，and the different modes are diagonalised into eigenfunctions of the Laplace operator on AdS $^ 3$ ; for three of the scalar fields this is done explicitly in Section 3.4, while the analysis of the remaining seven scalars is quite complicated and has been relegated to an appendix (Appendix B), with only the results being given in Section 3.5. The full scalar spectrum is then analysed in Section 3.6,and the above statements about the supergravity BPS bound are derived. Our analysis culminates in the description of the full supergravity spectrum in eq. (3.80). Finally, Section 4 contains our conclusions and outlines future directions of research. There are three appendices: in Appendix A we review the $D ( 2 , 1 | \alpha )$ and the large $\mathcal { N } = 4$ superconformal algebra $A _ { \gamma }$ and describe their BPS bounds. Appendix B contains part of the general supergravity analysis, while Appendix C deals with the special features that arise for the harmonics with small spin.

# 2 The world-sheet analysis

In this section we analyse the string spectrum on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ for the case of pure NS-NS flux. This background may be described by a WZW model as in [20]. More specifically, the AdS $^ 3$ factor is captured by an $\mathcal { N } = 1$ superconformal ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ WZW model at level $k$ ， while for the two $\mathrm { S ^ { 3 } }$ factors we have $\mathcal { N } = 1$ superconformal WZW models based on $\mathfrak { s u } ( 2 )$ at levels $k ^ { \pm }$ .Finally, the $\mathrm { S ^ { 1 } }$ factor is just described by a free boson and a free fermion. After decoupling the respective fermions,the bosonic currents (that commute with the fermions) then have levels $k + 2$ ,and $k ^ { \pm } - 2$ ， respectively. The requirement that the string theory is critical, i.e., has total central charge $c = 1 5$ , implies a relation between the levels, see e.g., [20]

$$
\frac { 1 } { k } = \frac { 1 } { k ^ { + } } + \frac { 1 } { k ^ { - } } \ , \mathrm { i . e . } \qquad k = \frac { k ^ { + } k ^ { - } } { k ^ { + } + k ^ { - } } \ .
$$

Geometrically, $k ^ { \pm }$ describe the sizes of the two ${ \mathrm { S } } ^ { 3 }$ 's,and (2.1) implies that the size of the AdS $_ 3$ space (that is described by $k$ ） is fixed in terms of these two.

To be more specific, we denote the bosonic modes of ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ at level $k + 2$ by $J _ { n } ^ { a }$ ，while $K _ { n } ^ { \pm , a }$ are the modes for $\mathfrak { s u } ( 2 )$ at level $k ^ { \pm } - 2$ . (In either case $a = 3 , \pm$ ） The corresponding fermions will be denoted by $\psi _ { r } ^ { a }$ and $\chi _ { r } ^ { \pm , a }$ , respectively, while for the $\mathrm { S ^ { 1 } }$ factor we have the bosonic and fermionic modes $\alpha _ { n }$ and $b _ { r }$ ， respectively. We also denote the corresponding supersymmetric currents by $\mathcal { J } _ { n } ^ { a }$ and $\kappa _ { n } ^ { \pm , a }$ ； their levels are then $k$ ，and $k ^ { \pm }$ ，respectively. The $\mathcal { N } = 1$ superconformal generators can be constructed in the usual manner [24].

In the following we shall mainly concentrate on the NS sector of the theory; we shall come back to the R sector at the end of this section. There the physical states $\Phi$ are characterised by the condition

$$
L _ { n } \Phi = 0 \ , \ n > 0 \ , \qquad G _ { r } \Phi = 0 \ , \ r > 0 \ , \qquad \left( L _ { 0 } - \frac { 1 } { 2 } \right) \Phi = 0 \ ,
$$

with a similar relation for the right-movers. We shall furthermore mainly consider the unflowed sector of the ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ WZW model [21]; we will later comment on the situation in the flowed sectors.

The affine representations that appear in the spectrum are (in the unflowed sector） conventional highest weight representations, and can be characterised by $( j _ { 0 } ; j _ { 0 } ^ { + } , j _ { 0 } ^ { - } )$ ，where $j _ { 0 }$ is the spin of the ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ highest weight representation,while $j _ { 0 } ^ { \pm }$ are the spins of the two $\mathfrak { s u } ( 2 )$ highest weight representations. In our conventions, $j _ { 0 } \geq 0$ labels the ‘highest weight state' that is characterised by

$$
J _ { 0 } ^ { - } \left| j _ { 0 } \right. = J _ { n } ^ { a } \left| j _ { 0 } \right. = 0 , n > 0 , \mathrm { a n d } J _ { 0 } ^ { 3 } \left| j _ { 0 } \right. = j _ { 0 } \left| j _ { 0 } \right. ,
$$

and the Casimirs of the ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ and $\mathfrak { s u } ( 2 )$ representations are

$$
C ^ { \mathrm { S L } ( 2 ) } = - j _ { 0 } \big ( j _ { 0 } - 1 \big ) , \qquad C ^ { \mathrm { S U } ( 2 ) } = j _ { 0 } ^ { \pm } \big ( j _ { 0 } ^ { \pm } + 1 \big ) .
$$

Let us denote by $N$ the excitation number of the physical state; then the mass-shell condition - the last equation in (2.2）— implies that

$$
N = \frac { 1 } { 2 } + \frac { j _ { 0 } ( j _ { 0 } - 1 ) } { k } - \frac { j _ { 0 } ^ { + } ( j _ { 0 } ^ { + } + 1 ) } { k ^ { + } } - \frac { j _ { 0 } ^ { - } ( j _ { 0 } ^ { - } + 1 ) } { k ^ { - } } .
$$

We have analysed the other two constraints of (2.2) on the low-lying ( $N \leq \frac { 3 } { 2 }$ ） physical states following the analysis of [25]. Modulo spurious null-states, we have found that the resulting spectrum has the standard form one expects from a light-cone gauge approach, where the two light-cone directions (whose oscillators do not create physical states) are the Cartan direction of ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ ，as well as the circle direction associated to the $\mathrm { S ^ { 1 } }$ ：

# 2.1 The spacetime BPS spectrum

It was shown in [2O], building on [26], that the spacetime theory has a large ${ \mathcal N } = 4$ （204号 superconformal symmetry. The large $\mathcal { N } = 4$ superconformal algebra is generated by the Virasoro algebra - the asymptotic symmetry algebra arising from AdS $^ 3$ 一 as well as two afffine $\mathfrak { s u } ( 2 )$ Kac-Moody algebras that arise from the two $\mathrm { S ^ { 3 } }$ factors. Furthermore there is a $\mathfrak { u } ( 1 )$ algebra corresponding to the S1.2 In the unflowed sector, the levels of the two $\mathfrak { s u } ( 2 )$ algebras of the spactime $\mathcal { N } = 4$ superconformal algebra can be identified with the levels of the two $\mathfrak { s u } ( 2 )$ algebras on the world-sheet,while the central charge is equal to $c = 6 k$ ，with $k$ the level of the ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ WZW model [20, 26]. The BPS bound of the large $\mathcal { N } = 4$ superconformal algebra has the form [16–18], see also [19]

$$
h \geq \frac { 1 } { k ^ { + } + k ^ { - } } \left[ k ^ { + } j ^ { - } + k ^ { - } j ^ { + } + u ^ { 2 } + ( j ^ { + } - j ^ { - } ) ^ { 2 } \right] ,
$$

where $h$ is the conformal dimension, while $j ^ { \pm }$ are the spins with respect to the two $\mathfrak { s u } ( 2 )$ algebras. Furthermore, $u$ is the $\mathfrak { u } ( 1 )$ charge. In the following we shall only consider the neutral sector $u = 0$ - we have checked that there are no BPS states for $u \neq 0$ ：

In terms of world-sheet parameters, we can identify $h$ with the eigenvalue $j$ of $\mathcal { I } _ { 0 } ^ { 3 }$ ，while $j ^ { \pm }$ are the spins of $\mathcal { K } _ { 0 } ^ { \pm , a }$ . We want to ask which physical states of the world-sheet theory saturate the BPS bound (2.6). In order to identify the potential BPS states we will fix $j ^ { \pm }$ , and look for the physical state with the lowest value of $j$ The eigenvalues $j ^ { \pm }$ differ from those of the ground states $j _ { 0 } ^ { \pm }$ by the charges that are carried by the oscillators,and we define

$$
j ^ { \pm } = j _ { 0 } ^ { \pm } - \Delta ^ { \pm } .
$$

If $\Delta ^ { \pm } = 0$ , then we can use all the oscillators to lower $j$ , leading to

$$
j = j _ { 0 } - N - \frac { 1 } { 2 } ~ .
$$

[Note that $N$ has to be half-integer (because of the GSO projection)； furthermore, for $N > \frac { 1 } { 2 }$ we can use the fermionic mode $\psi _ { - 1 / 2 } ^ { - }$ once, but then it becomes more efficient to use the bosonic $J _ { - 1 } ^ { - }$ modes.] On the other hand,if $\Delta ^ { + } \neq 0$ ，we need $\left| \Delta ^ { + } \right| - \mathrm { \Delta \frac { 1 } { 2 } }$ oscillators to obtain the correct $j ^ { + }$ spin and similarly for $j ^ { - }$ ，and then only the remaining oscillators can be used to reduce the eigenvalue of $j$ .Thus it seems plausible — and it is not hard to show rigorously, although the argument is a bit tedious — that the BPS states can only occur for $\Delta ^ { + } = \Delta ^ { - } = 0$ and $\begin{array} { r } { N = \frac { 1 } { 2 } } \end{array}$ (Note that this is also what one would have guessed on general grounds since $\begin{array} { r } { N = \frac { 1 } { 2 } } \end{array}$ （20 characterises the ‘supergravity’ states.） Then $j ^ { \pm } = j _ { 0 } ^ { \pm }$ , and determining $j _ { 0 }$ from the mass-shell condition and plugging it into (2.8) leads to

$$
\begin{array} { l } { { j = - \displaystyle \frac { 1 } { 2 } + \sqrt { \frac { 1 } { 4 } + \frac { k j ^ { + } ( j ^ { + } + 1 ) } { k ^ { + } } + \frac { k j ^ { - } ( j ^ { - } + 1 ) } { k ^ { - } } } } } \\ { { = - \displaystyle \frac { 1 } { 2 } + \sqrt { \frac { 1 } { 4 } + \frac { k ^ { - } j ^ { + } ( j ^ { + } + 1 ) } { k ^ { + } + k ^ { - } } + \frac { k ^ { + } j ^ { - } ( j ^ { - } + 1 ) } { k ^ { + } + k ^ { - } } } , } } \end{array}
$$

where we have used that $k$ is given by, see eq. (2.1)

$$
k = \frac { k ^ { + } k ^ { - } } { k ^ { + } + k ^ { - } } .
$$

One can convince oneself that (2.9) satisfies the BPS bound (A.5)

$$
j \geq \frac { 1 } { k ^ { + } + k ^ { - } } \left[ k ^ { - } j ^ { + } + k ^ { + } j ^ { - } + ( j ^ { + } - j ^ { - } ) ^ { 2 } \right]
$$

provided that $\begin{array} { r } { j _ { 0 } \le \frac { k + 1 } { 2 } } \end{array}$ ; this latter condition is a consequence of the no-ghost theorem [21, 25] and guarantees unitarity. More specifically, after squaring $( j + \frac { 1 } { 2 } )$ from (2.9) and comparing to (2.11), the BPS bound becomes

$$
( j ^ { + } - j ^ { - } ) ^ { 2 } \left[ k ^ { + } k ^ { - } - k ^ { + } - k ^ { - } - ( j ^ { + } - j ^ { - } ) ^ { 2 } - 2 ( k ^ { - } j ^ { + } + k ^ { + } j ^ { - } ) \right] \ge 0 ~ .
$$

The first factor is clearly non-negative, while the square bracket defines an ellipse in the $( j ^ { + } , j ^ { - } )$ -plane. One can see that this lies outside the variety - this is just the mass-shell condition for the maximal choice of $\begin{array} { r } { j _ { 0 } = \frac { k + 1 } { 2 } } \end{array}$ （204号

$$
- \frac { k ^ { 2 } - 1 } { 4 k } + \frac { j ^ { + } ( j ^ { + } + 1 ) } { k ^ { + } } + \frac { j ^ { - } ( j ^ { - } + 1 ) } { k ^ { - } } = 0 \ ,
$$

but they touch at the point

$$
j ^ { + } = j ^ { - } = \frac { k - 1 } { 2 } .
$$

Thus the BPS bound is always satisfied, but it can (and is) only saturated for the case

$$
j ^ { + } = j ^ { - } \ .
$$

This is the main result of our world-sheet analysis

We have also performed a similar analysis for the spectrally flowed sectors in the NS sector. They give rise to further BPS states, as explained in detail in [33]. However, since supergravity corresponds to the regime $k ^ { \pm } \to \infty$ ， these additional states are not important for the present analysis. Thus from now on we will only talk about the unflowed sector of string theory.

As regards the situation in the R sector, the analysis is similar to the above, and the only BPS states exist for $j ^ { + } = j ^ { - }$ . The corresponding values of $j ^ { + } = j ^ { - }$ are shifted by $\textstyle { \frac { 1 } { 2 } }$ relative to the NS analysis. These BPS states are therefore the states associated to the $j + \textstyle { \frac { 1 } { 2 } }$ term in (A.26)，and they are required in order to get the complete multiplet of the large $\mathcal { N } = 4$ superconformal algebra. Thus our analysis predicts that the entire BPS spectrum of string theory on $\mathrm { A d S _ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 1 } }$ consists of the representations

$$
\mathrm { B P S ~ s p e c t r u m ~ o f ~ s t r i n g ~ t h e o r y : } \quad \bigoplus _ { j = 0 } ^ { k - 1 } [ j , j , u = 0 ] _ { S } \otimes \overline { { [ j , j , u = 0 ] } } _ { S } ~ .
$$

# 2.2 Supergravity interpretation

Given the general relation between string theory and supergravity, one should expect that (2.9) also has a direct supergravity interpretation. Let us consider a scalar field on ${ \mathrm { A d S } } _ { 3 }$ that arises from a massless scalar field in 1O dimensions upon KK reduction on $\mathrm { S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ . If we take the KK momentum along the $\mathrm { S ^ { 1 } }$ to be trivial, then its mass (in AdS $^ 3$ units, i.e,relative to the size $k$ )，is

$$
\frac { m ^ { 2 } } { k } = \frac { j ^ { + } ( j ^ { + } + 1 ) } { k ^ { + } } + \frac { j ^ { - } ( j ^ { - } + 1 ) } { k ^ { - } } ~ ,
$$

where the two terms on the right-hand-side are the eigenvalues of the Laplacian on the sphere for the spherical harmonic labelled by $( j ^ { + } , j ^ { - } )$ . Again these eigenvalues are evaluated in appropriate units, i.e., relative to the sizes $k ^ { \pm }$ of the corresponding （204号 $\mathrm { S ^ { 3 } }$ 's. We can convert this expression into the conformal dimension of the dual CFT, using the general relation between the mass of a scalar field and the left-moving conformal dimension $\Delta = h + h$ (with $h = h$ )

$$
m ^ { 2 } = h ( h - 1 ) \ ,
$$

leading to

$$
h = { \frac { 1 } { 2 } } + \sqrt { { \frac { 1 } { 4 } } + m ^ { 2 } } = { \frac { 1 } { 2 } } + \sqrt { { \frac { 1 } { 4 } } + { \frac { k j ^ { + } ( j ^ { + } + 1 ) } { k ^ { + } } } + { \frac { k j ^ { - } ( j ^ { - } + 1 ) } { k ^ { - } } } } \ .
$$

This differs by a shift of 1 from (2.9) - as we shall see in the next section， the analysis is a bit more subtle,and there is in fact one scalar component for which (2.9) is precisely reproduced - but the dependence on the spins is exactly as in (2.9). For the supergravity analysis the relevant symmetry algebra is $D ( 2 , 1 | \alpha )$ ,whose BPS bound takes the form (A.12) (see Appendix A.1)

$$
h \geq \frac { 1 } { k ^ { + } + k ^ { - } } \left[ k ^ { - } j ^ { + } + k ^ { + } j ^ { - } \right] .
$$

Provided that the actual supergravity analysis leads to (2.19) (or rather to $h - 1$ )，it follows by similar arguments as above that it can only be saturated if $j ^ { + } = j ^ { - }$ . Indeed the supergravity bound (2.2O) is weaker than the stringy bound (2.11)，and hence at most those states that saturate the stringy bound can saturate the supergravity bound. Happily, the only states that saturate the stringy bound occur for $j ^ { + } = j ^ { - }$ where the two bounds coincide.

If this somewhat sketchy line of reasoning is correct it would suggests that the BPS spectrum of supergravity on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ consists only of representations of $D ( 2 , 1 | \alpha )$ with $j ^ { + } = j ^ { - }$ . This is contrary to what was claimed or assumed in the literature before, see in particular [19]. We shall therefore,in the next section, perform a careful and detailed supergravity computation to confirm this claim explicitly.

# 3 Supergravity approach

Let us start with 10-dimensional IIB supergravity. The bosonic part of the action is, in the string frame, given by

$$
\begin{array} { l } { { S _ { \mathrm { I I B } } = S _ { \mathrm { N S } } + S _ { \mathrm { R } } + S _ { \mathrm { C S } } } } \\ { { S _ { \mathrm { N S } } = \displaystyle \frac { 1 } { 2 \kappa ^ { 2 } } \int \mathrm { d } ^ { 1 0 } x \sqrt { - g } e ^ { - 2 \Phi } \left( R + 4 \partial _ { M } \Phi \partial ^ { M } \Phi - \displaystyle \frac { 1 } { 2 } \vert H \vert ^ { 2 } \right) ~ , } } \\ { { S _ { \mathrm { R } } = - \displaystyle \frac { 1 } { 4 \kappa ^ { 2 } } \int \mathrm { d } ^ { 1 0 } x \sqrt { - g } \left( \vert F _ { 1 } \vert ^ { 2 } + \vert \tilde { F } _ { 3 } \vert ^ { 2 } + \displaystyle \frac { 1 } { 2 } \vert \tilde { F } _ { 5 } \vert ^ { 2 } \right) ~ , } } \\ { { S _ { \mathrm { C S } } = - \displaystyle \frac { 1 } { 4 \kappa ^ { 2 } } \int C _ { 4 } \wedge H \wedge F _ { 3 } ~ , } } \end{array}
$$

where

$$
\begin{array} { l } { { \displaystyle \tilde { F } _ { 3 } = F _ { 3 } - C _ { 0 } \wedge H ~ , } } \\ { { \displaystyle \tilde { F } _ { 5 } = F _ { 5 } - \frac { 1 } { 2 } C _ { 2 } \wedge H + \frac { 1 } { 2 } B _ { 2 } \wedge F _ { 3 } ~ . } } \end{array}
$$

Here, $\Phi$ is the 1Od dilaton field, $g$ is the 10d metric with $R$ its associated curvature scalar, and $B$ is the Kalb-Ramond field. $C _ { 0 }$ ， $C _ { 2 }$ and $C _ { 4 }$ are the R-R-fields, whose fields strengths are defined as

$$
F _ { 1 } = \mathrm { d } C _ { 0 } \ , \quad H = \mathrm { d } B \ , \quad F _ { 3 } = \mathrm { d } C _ { 2 } \ , \quad F _ { 5 } = \mathrm { d } C _ { 4 } \ .
$$

Finally, we have to impose self-duality on $\tilde { F } _ { 5 }$ （204号

$$
\star { \tilde { F } } _ { 5 } = { \tilde { F } } _ { 5 } \ .
$$

We will look at solutions on $\mathrm { A d S _ { 3 } \times S _ { + } ^ { 3 } \times S _ { - } ^ { 3 } \times S ^ { 1 } }$ where we have pure NS-fux on the $\mathrm { A d S _ { 3 } }$ factor and through the two $\mathrm { S _ { \pm } ^ { 3 } }$ ：

It is consistent to set all R-R felds (as well as all the fermions) to zero. Then we are only left with the NS-NS fields,i.e., the metric, the dilaton and $H$ ， whose action is

$$
\tilde { S } _ { \mathrm { I I B } } = { \frac { 1 } { 4 \kappa ^ { 2 } } } \int \mathrm { d } ^ { 1 0 } x \sqrt { - g } e ^ { - 2 \Phi } \left( R + 4 \partial _ { M } \Phi \partial ^ { M } \Phi - { \frac { 1 } { 2 } } \vert H \vert ^ { 2 } \right) ~ .
$$

# 3.1 The 9d vacuum solution

We now compactify the theory on a circle to get an effective 9d theory. In the process, we have to dimensionally reduce the fields, see, e.g., [27]. The 1Od metric $g$ gives rise to a 9d-metric, which we again call $g$ ，a vector $A _ { \mu } = g _ { \mu , 1 0 }$ and a scalar $k = g _ { 1 0 , 1 0 }$ The Kalb-Ramond field $B$ leads to a vector $\hat { A } _ { \mu } = B _ { \mu , 1 0 }$ and a 9d two-form $B$ We call the field strengths associated to $A$ and $\hat { A }$ ， $F$ and $\hat { F }$ , respectively. The resulting action is then — this is eq. (21.25) of [27], after changing the signature, rescaling the fields and setting $\Psi = \log k$

$$
\begin{array} { c } { { S _ { 9 \mathrm { d } } = \displaystyle \frac { 1 } { 4 \kappa ^ { 2 } } \int \mathrm { d } ^ { 9 } x \sqrt { - g } e ^ { - 2 \Phi } \left[ R + 4 \partial _ { M } \Phi \partial ^ { M } \Phi - \displaystyle \frac { 1 } { 2 } \left| H \right| ^ { 2 } - \partial _ { M } \Psi \partial ^ { M } \Psi \right. } } \\ { { \displaystyle \left. - \frac { 1 } { 2 } \left| F \right| ^ { 2 } - \displaystyle \frac { 1 } { 2 } | \hat { F } | ^ { 2 } \right] . } } \end{array}
$$

The result is invariant under T-duality, which interchanges $A$ and $\hat { A }$ .The field equations for $\Psi$ and the one-forms read

$$
\Delta A = \Delta \hat { A } = 0 \ , \quad \Delta \Psi = 0 \ .
$$

It is hence consistent to set them all to zero. The $\Phi$ -equation of motion is

$$
R - \frac { 1 } { 2 } | H | ^ { 2 } = 4 \partial _ { M } \Phi \partial ^ { M } \Phi + 4 \Delta \Phi \ .
$$

We set $\Phi = 0$ (or $\Phi$ at least constant)，which imposes the condition

$$
R = { \frac { 1 } { 2 } } \left| H \right| ^ { 2 } .
$$

The $g$ -equation of motion is the usual Einstein equation,

$$
R _ { M N } - { \frac { 1 } { 4 } } H _ { M P R } H _ { N } { } ^ { P R } = 0 \ .
$$

where we have used (3.1O). Taking the trace gives

$$
R = \frac { 1 } { 4 } \left| H \right| ^ { 2 } ,
$$

and hence from (3.10) and (3.12) we must have $R = \left| H \right| ^ { 2 } = 0$ . The $H$ equation of motion finally reads

$$
\begin{array} { r } { \mathrm { d } \star H = 0 \ , } \end{array}
$$

i.e. $H$ is closed and coclosed and hence harmonic.

In order to find the vacuum solution corresponding to $\mathrm { A d S _ { 3 } \times S _ { + } ^ { 3 } \times S _ { - } ^ { 3 } }$ ，let us denote their radii by $r$ (for $\mathrm { A d S _ { 3 } }$ )，and $r _ { \pm }$ (for $\mathrm { S _ { \pm } ^ { 3 } }$ ). All factors are maximally symmetric,and thus the Riemann tensor takes the form

$$
R _ { M N P R } \propto \left( g _ { M P } g _ { N R } - g _ { M R } g _ { N P } \right) \ ,
$$

if all indices are in one factor. We thus have

$$
\begin{array} { r } { R _ { M N P R } = - r ^ { - 2 } \left( g _ { M P } ^ { \mathrm { A d S _ { 3 } } } g _ { N R } ^ { \mathrm { A d S _ { 3 } } } - g _ { M R } ^ { \mathrm { A d S _ { 3 } } } g _ { N P } ^ { \mathrm { A d S _ { 3 } } } \right) + r _ { + } ^ { - 2 } \left( g _ { M P } ^ { \mathrm { S _ { + } ^ { 3 } } } g _ { N R } ^ { \mathrm { S _ { + } ^ { 3 } } } - g _ { M R } ^ { \mathrm { S _ { + } ^ { 3 } } } g _ { N P } ^ { \mathrm { S _ { + } ^ { 3 } } } \right) } \\ { + r _ { - } ^ { - 2 } \left( g _ { M P } ^ { \mathrm { S _ { - } ^ { 3 } } } g _ { N R } ^ { \mathrm { S _ { - } ^ { 3 } } } - g _ { M R } ^ { \mathrm { S _ { - } ^ { 3 } } } g _ { N P } ^ { \mathrm { S _ { - } ^ { 3 } } } \right) \ , \ } \end{array}
$$

where we view $g ^ { \mathrm { A d S _ { 3 } } }$ etc.as 10d fields, ie., $g _ { M N } ^ { \mathrm { A d S _ { 3 } } } = 0$ except when $0 \le M , N \le 2$ etc. Contracting indices gives

$$
\begin{array} { r l } & { R _ { M N } = - 2 r ^ { - 2 } g _ { M N } ^ { \mathrm { A d S } _ { 3 } } + 2 r _ { + } ^ { - 2 } g _ { M N } ^ { \mathrm { S } _ { + } ^ { 3 } } + 2 r _ { - } ^ { - 2 } g _ { M N } ^ { \mathrm { S } _ { - } ^ { 3 } } \ , } \\ & { \qquad R = - 6 r ^ { - 2 } + 6 r _ { + } ^ { - 2 } + 6 r _ { - } ^ { - 2 } \ . } \end{array}
$$

Following [9], we now make the ansatz for $H$

$$
H = \lambda _ { 0 } \omega ^ { \mathrm { A d S _ { 3 } } } + \lambda _ { + } \omega ^ { \mathrm { S _ { + } ^ { 3 } } } + \lambda _ { - } \omega ^ { \mathrm { S _ { - } ^ { 3 } } } \ ,
$$

where $\omega ^ { \mathrm { A d S _ { 3 } } }$ are the volume forms on AdS $_ 3$ , etc. This form is trivially closed. The volume forms are harmonic and hence also coclosed， so $H$ obeys the equation of motion. The normalisations are chosen as

$$
\int _ { \mathrm { S } _ { \pm } ^ { 3 } } \omega _ { \pm } = 2 \pi ^ { 2 } r _ { \pm } ^ { 3 } \ ,
$$

and similarly for ${ \mathrm { A d S } } _ { 3 }$ ，which can be obtained by analytic continuation. We have $| \omega ^ { \mathrm { A d S _ { 3 } } } | ^ { 2 } = - 1$ and $| \omega ^ { \mathrm { S } _ { \pm } ^ { 3 } } | ^ { 2 } = 1$ , i.e. in total:

$$
\vert { \cal H } \vert ^ { 2 } = - \lambda _ { 0 } ^ { 2 } + \lambda _ { + } ^ { 2 } + \lambda _ { - } ^ { 2 } \ .
$$

The Einstein equations exhibit a connection between the $\lambda$ 's and the radii, namely

$$
r ^ { - 2 } = \frac { 1 } { 4 } \lambda _ { 0 } ^ { 2 } \ , r _ { \pm } ^ { - 2 } = \frac { 1 } { 4 } \lambda _ { \pm } ^ { 2 } \ ,
$$

and furthermore the vanishing of $R$ implies

$$
- \lambda _ { 0 } ^ { 2 } + \lambda _ { + } ^ { 2 } + \lambda _ { - } ^ { 2 } = 4 ( - r ^ { - 2 } + r _ { + } ^ { - 2 } + r _ { - } ^ { - 2 } ) = 0 \ .
$$

The fluxes through $\mathrm { S _ { \pm } ^ { 3 } }$ are given by

$$
\int _ { \mathrm { S _ { \pm } ^ { 3 } } } H = Q _ { 5 } ^ { \pm } = k ^ { \pm } = 4 \pi ^ { 2 } r _ { \pm } ^ { 2 } \ ,
$$

and are always integers. As a consequence, (3.22) coincides with the string theory criticality condition on the levels, see eq. (2.1)

$$
\frac { 1 } { k } = \frac { 1 } { k ^ { + } } + \frac { 1 } { k ^ { - } } \ ,
$$

where we defined in analogy $k$ as $k = 4 \pi ^ { 2 } r ^ { 2 }$

# 3.2 Equations of motion for quadratic perturbations

We now consider the fluctuations around this background geometry. To second order in the variations the above action becomes

$$
\delta ^ { 2 } \tilde { S } _ { \mathrm { I I B } } = \frac { 1 } { 4 \kappa ^ { 2 } } \int \mathrm { d } ^ { 9 } x ~ \sqrt { - g } \mathcal { L } ~ ,
$$

where $\mathcal { L }$ is explicitly given as

$$
\begin{array} { l } { { \displaystyle { \mathcal { L } } = \frac { 1 } { 2 } \nabla _ { P } h ^ { R } { } _ { R } \nabla ^ { P } h ^ { M } { } _ { M } - \frac { 1 } { 2 } \nabla _ { R } h _ { M P } \nabla ^ { R } h ^ { M P } + \nabla _ { P } h _ { M R } \nabla ^ { R } h ^ { M P } - \nabla _ { P } h ^ { R } { } _ { R } \nabla ^ { R } h ^ { P } { } _ { R } } } \\ { ~ - ~ 8 \nabla _ { P } \phi \nabla ^ { [ P } h ^ { M ] } { } _ { M } - 2 \nabla _ { M } \psi \nabla ^ { M } \psi + 8 \nabla _ { M } \phi \nabla ^ { M } \phi + \frac { 1 } { 6 } H _ { M P R } \Xi ^ { M P R } ( 4 \phi - h ^ { Q } \phi ) } \\ { ~ + H _ { M } ^ { R Q } h ^ { M P } \Xi _ { P R Q } - \frac { 1 } { 6 } \Xi _ { M P R } \Xi ^ { M P R } - \frac { 1 } { 2 } Z _ { M P } Z ^ { M P } - \frac { 1 } { 2 } \hat { Z } _ { M P } \hat { Z } ^ { M P } } \\ { ~ - \frac { 1 } { 2 } H _ { M R } { } ^ { N } H _ { P Q N } h ^ { M P } h ^ { R Q } ~ . } \end{array}
$$

Here we wrote $\delta g _ { M N } = h _ { M N }$ ， and we treat $h _ { M N }$ as a tensor, i.e., $\delta g ^ { M N } = - h ^ { M N }$ ： We similarly defned $\delta H _ { M N P } = \Xi _ { M N P }$ ， $\delta \Phi = \phi$ ， $\delta \Psi = \psi$ ， $\delta F _ { M N } = Z _ { M N }$ ， as well as （20 $\delta \hat { F } _ { M N } = \hat { Z } _ { M N }$ . The first terms are kinetic terms, but there are also mass terms. The connection is still the Levi-Civita connection of the background metric, and we raise and lower indices with the background metric. We used that $\mathrm { A d S _ { 3 } \times S _ { + } ^ { 3 } \times S _ { - } ^ { 3 } }$ has vanishing Ricci scalar and vanishing $| H | ^ { 2 }$ ; we have also already inserted the other background values of the fields and used the Einstein equation of the background solution. Note that there are no interference terms between $Z , { \hat { Z } }$ ， $\psi$ ,and the other fields,and hence we can treat the fluctuations of $F ^ { \prime }$ ， $\hat { F }$ and $\Psi$ separately from the rest. The resulting equations of motion for the remaining quadratic fluctuations are

$$
\begin{array} { r l r } { 0 - \Delta \phi - \frac { 1 } { 4 } \nabla _ { H } \nabla _ { P } h ^ { \lambda P } + \frac { 1 } { 4 } \Delta h ^ { \lambda P } _ { M } + \frac { 1 } { 2 4 } H ^ { \lambda P P Q } \Xi _ { \lambda P P Q } , } & { ( 3 , } \\ { 0 - \Delta h _ { M P } - 4 g _ { M P } \Delta \phi - g _ { M P } \nabla _ { R } \nabla _ { Q } h ^ { Q R } + g _ { M P } \Delta h ^ { Q } _ { Q } - \nabla _ { M } \nabla _ { P } h ^ { Q } } & \\ { + 2 \nabla _ { Q } \nabla _ { ( M } h _ { P ) } ^ { Q } + 4 \nabla _ { M } \nabla _ { P } \phi + \frac { 1 } { 6 } g _ { M P } H ^ { Q M } \Xi _ { Q R N } - H _ { M } ^ { Q R } \Xi _ { P Q R } } & \\ { + H _ { M Q } ^ { N } H _ { P R N } h ^ { Q R } , } & { ( 3 , } \\ { 0 - \Delta X _ { M P } + 2 \nabla _ { Q } \nabla _ { [ P ] } X _ { M } ) ^ { Q } + 2 \phi \nabla _ { Q } H _ { M P } \Theta ^ { Q } + 2 H _ { M P Q } \nabla ^ { Q } \phi + h ^ { Q R } \nabla _ { H } H _ { M P Q } } & \\ { - \frac { 1 } { 2 } h ^ { Q } _ { Q } \nabla _ { R } H _ { M P } - h ^ { Q } _ { M } \nabla _ { R } H _ { P Q } R + H _ { M P Q } \nabla _ { R } h ^ { Q R } - H _ { P Q R } \nabla ^ { n } h ^ { Q } _ { M } } & \\ { + \ H _ { M Q R } \nabla ^ { n } h ^ { Q } _ { P } - \frac { 1 } { 2 } \nabla ^ { R } h ^ { Q } _ { Q } . } & { ( 3 . } \end{array}
$$

where $\delta B _ { M N } = X _ { M N }$

# 3.3 Expanding the Fields

Following [22], we parametrise the metric fluctuations as

$$
\begin{array} { l } { { \delta g _ { \mu \nu } = H _ { \mu \nu } + g _ { \mu \nu } M ~ , \quad g ^ { \mu \nu } H _ { \mu \nu } = 0 ~ , } } \\ { { \delta g _ { \mu a } = R _ { \mu a } ~ , } } \\ { { \delta g _ { \mu i } = S _ { \mu i } ~ , } } \\ { { \delta g _ { a i } = T _ { a i } ~ , } } \\ { { \delta g _ { a b } = K _ { a b } + g _ { a b } N ~ , \quad g ^ { a b } L _ { a b } = 0 ~ , } } \\ { { \delta g _ { i j } = L _ { i j } + g _ { i j } P ~ , \quad g ^ { i j } T _ { i j } = 0 ~ . } } \end{array}
$$

Here and from now on, greek indices refer to $\mathrm { A d S _ { 3 } }$ , latin indices from the beginning of the alphabet $a , b , \ldots$ to $\mathrm { S _ { + } ^ { 3 } }$ , while the latin indices from the middle of the alphabet （20 $i , j , \dots$ refer to $\mathrm { S _ { - } ^ { 3 } }$ . We will use capital latin letters to indicate 9d-indices. For the antisymmetric tensor field, we have $H _ { M N P } = 3 \partial _ { [ M } B _ { N P ] }$ ， and we parametrise the fluctuations as

$$
\begin{array} { l } { { { \cal X } _ { \mu \nu } = \epsilon _ { \mu \nu \rho } U ^ { \rho } ~ , } } \\ { { { \cal X } _ { a b } = \epsilon _ { a b c } V ^ { c } ~ , } } \\ { { { \cal X } _ { i j } = \epsilon _ { i j k } W ^ { k } ~ , } } \\ { { { \cal X } _ { \mu a } = { \cal C } _ { \mu a } ~ , } } \\ { { { \cal X } _ { \mu i } = { \cal D } _ { \mu i } ~ , } } \\ { { { \cal X } _ { a i } = { \cal E } _ { a i } ~ . } } \end{array}
$$

We expand the fluctuations in harmonic functions on the two $\mathrm { S ^ { 3 } }$ 's as

$$
\begin{array} { l } { { \phi = \displaystyle \sum _ { \ell ^ { + } , \ell ^ { - } } \phi ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } Y _ { + } ^ { ( \ell ^ { + } 0 ) } Y _ { - } ^ { ( \ell ^ { - } 0 ) } ~ , } } \\ { { { } ~ { } ~ } } \\  { { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ } \\ { { { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ \bar { { } } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } { } _ { a } { } Y _ { + } ^ { ( \ell ^ { + } 0 ) } Y _ { - } ^ { ( \ell ^ { - } 0 ) } ~ , } } \\   { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~ { } ~  \end{array}
$$

where we have chosen，as representative examples, felds of spin $0$ ， $1$ and 2 on $\mathrm { S _ { + } ^ { 3 } }$ respectively； the complete list for all the felds is given in Appendix B.1. Here, $\{ a b \}$ resp. $\{ i j \}$ denotes the traceless symmetric part,and $Y _ { \pm , ( s ) } ^ { ( \ell _ { 1 } \ell _ { 2 } ) }$ is the eigenfunction of the Laplacian on $\mathrm { S _ { \pm } ^ { 3 } }$ ， which transforms under $\mathrm { S O ( 4 ) } \cong \mathrm { S U ( 2 ) } \times \mathrm { S U ( 2 ) }$ in the representation

$$
{ \frac { 1 } { 2 } } ( \ell _ { 1 } + \ell _ { 2 } ) \ , \quad { \frac { 1 } { 2 } } ( \ell _ { 1 } - \ell _ { 2 } ) \ .
$$

Here $\ell _ { i } \in  { \mathbb { N } } _ { 0 }$ , and the relation to the previously used $j$ variables is

$$
j = \frac { 1 } { 2 } ( \ell _ { 1 } + \ell _ { 2 } ) \ , \quad \bar { j } = \frac { 1 } { 2 } ( \ell _ { 1 } - \ell _ { 2 } ) \ .
$$

The space of 1-forms on $\mathrm { S _ { + } ^ { 3 } }$ is spanned by

$$
Y _ { + , a } ^ { ( \ell \pm 1 ) } \ , \partial _ { a } Y _ { + } ^ { ( \ell 0 ) }
$$

and the space of traceless symmetric 2-tensors is spanned by

$$
Y _ { + , a b } ^ { ( \ell \pm 2 ) } \ , \quad \nabla _ { \{ a } Y _ { + , b \} } { } ^ { ( \ell \pm 1 ) } \ , \quad \nabla _ { \{ a } \nabla _ { b \} } Y _ { + } ^ { ( \ell 0 ) } \ .
$$

As in [22], we choose the ‘Lorentz gauge'

$$
\nabla ^ { a } h _ { a \mu } = 0 \ , \quad \nabla ^ { a } h _ { \{ a b \} } = 0 \ , \quad \nabla ^ { a } h _ { a i } = 0 \ , \quad \nabla ^ { a } X _ { a M } = 0 \ .
$$

This gauge removes 9 degrees of freedom of the metric and 8 degrees of freedom of $X$ ，which are the right numbers. Hence locally, this gauge is admissible,and one can also confirm this more carefully. We should note that this gauge choice breaks the manifest symmetry between the two spheres (since we impose the divergence condition only with respect to the $a$ -coordinates on $\mathrm { S _ { + } ^ { 3 } }$ ). However,as we shall see later, the resulting spectrum will be symmetrical with respect to exchanging the two spheres. We should note that eq.(3.49) implies in particular that

$$
\begin{array} { c c c } { { \nabla ^ { a } R _ { \mu a } = 0 ~ , } } & { { \nabla ^ { a } K _ { a b } = 0 ~ , } } & { { \nabla ^ { a } T _ { a i } = 0 ~ , } } \\ { { \nabla ^ { a } C _ { \mu a } = 0 ~ , } } & { { \nabla _ { [ a } V _ { b ] } = 0 ~ , } } & { { \nabla ^ { a } E _ { a i } = 0 ~ . } } \end{array}
$$

Additionally, there is a gauge freedom in the decoupled subsystem which will be fixed in the next section.

# 3.4 The scalars from the decoupled subsystem

As was mentioned before, we can analyse the fluctuations of $\Psi$ ， $F ^ { \prime }$ and $\hat { F }$ separately from the rest; since this part of the analysis is simpler,let us frst explain that. The equation of motion of $\Psi$ is simply

$$
( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } ) \Psi = 0 \ .
$$

Expanding $\Psi$ in terms of harmonics,

$$
\Psi = \sum _ { \ell ^ { + } , \ell ^ { - } } \Psi ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } Y _ { + } ^ { ( \ell ^ { + } 0 ) } Y _ { - } ^ { ( \ell ^ { - } 0 ) } ,
$$

and using (B.1), we get

$$
\left( \Delta _ { 0 } - m _ { \ell ^ { + } , \ell ^ { - } } ^ { 2 } \right) \Psi ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } = 0 \ ,
$$

where

$$
m _ { \ell ^ { + } , \ell ^ { - } } ^ { 2 } \equiv r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) + r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \ ,
$$

is the AdS $_ 3$ mass squared. The treatment of $Z _ { M N } = 2 \dot { o } _ { [ M } \Upsilon _ { N ] }$ is a bit more complicated. Let us denote the perturbation of $A _ { M }$ as $\Upsilon _ { M }$ , and split $\Upsilon _ { M }$ as

$$
\Upsilon _ { \mu } = \Pi _ { \mu } \ , ~ \Upsilon _ { a } = \Sigma _ { a } \ , ~ \Upsilon _ { i } = \Omega _ { i } \ .
$$

To fix the gauge, we require the equivalent of the last equation of eq. (3.49)

$$
\nabla ^ { a } \Sigma _ { a } = 0 \ .
$$

The equations of motion, split into the different components, read

$$
\begin{array} { r l } & { 0 = ( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } + 2 \ell ^ { - 2 } ) \Pi _ { \mu } - \nabla _ { \mu } \nabla ^ { \nu } \Pi _ { \nu } - \nabla _ { \mu } \nabla ^ { i } \Omega _ { i } \ , } \\ & { 0 = ( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } - 2 r _ { + } ^ { - 2 } ) \Sigma _ { a } - \nabla _ { a } \nabla ^ { \nu } \Pi _ { \nu } - \nabla _ { a } \nabla ^ { i } \Omega _ { i } \ , } \\ & { 0 = ( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } - 2 r _ { - } ^ { - 2 } ) \Omega _ { i } - \nabla _ { i } \nabla ^ { \nu } \Pi _ { \nu } - \nabla _ { i } \nabla ^ { j } \Omega _ { j } \ . } \end{array}
$$

We shall in the following always focus on scalar quantities, i.e., on modes that are scalar with respect to $\mathrm { A d S _ { 3 } }$ as well as the two $\mathrm { S _ { \pm } ^ { 3 } }$ . In the present context, there are two of those, namely $\nabla ^ { \mu } \Pi _ { \mu }$ and $\nabla ^ { i } \Omega _ { i }$ . Thus, we have an overconstrained system, since the scalar parts of (3.58)-(3.60) constitute three equations for these two fields. Let us extract the scalar parts of these three equations by applying $\nabla ^ { \mu }$ to the first equation, $\nabla ^ { a }$ to the second one and $\nabla ^ { i }$ to the third one; the result is

$$
\begin{array} { l } { { 0 = ( \Delta _ { + } + \Delta _ { - } ) \nabla ^ { \mu } \Pi _ { \mu } - \Delta _ { 0 } \nabla ^ { i } \Omega _ { i } \ , } } \\ { { 0 = \Delta _ { + } ( \nabla ^ { \nu } \Pi _ { \nu } + \nabla ^ { i } \Omega _ { i } ) \ , } } \\ { { 0 = ( \Delta _ { 0 } + \Delta _ { + } ) \nabla ^ { \mu } \Omega _ { i } - \Delta _ { - } \nabla ^ { \mu } \Pi _ { \mu } \ . } } \end{array}
$$

For $\ell ^ { + } > 0$ , the second equation implies that there is actually only one scalar field, which we may take to be $\nabla ^ { \mu } \Pi _ { \mu }$ ； for $\ell ^ { + } = 0$ ， the situation is more complicated and requires fixing the residual gauge, as explained in Appendix C. Assuming $\ell ^ { + } > 0$ ， the first and third equation are equivalent to

$$
0 = ( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } ) \nabla ^ { \mu } \Pi _ { \mu } \ .
$$

(Later, we will also have a similar situation for the dilaton, the metric and the KalbRamond field, i.e.， the overconstrained system of scalar equations will imply some algebraic relationships among the fields,and once we have found these, there are some linear dependencies among the remaining equations.） We hence get again one set of scalar fields with mass

$$
m ^ { 2 } = m _ { \ell ^ { + } , \ell ^ { - } } ^ { 2 } \equiv r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) + r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \ .
$$

Thus in total we find three sets of scalar fields, one from $\Psi$ ， one from $A _ { M }$ and one from ${ \hat { A } } _ { M }$ , all having equal mass.

# 3.5 The scalars from the remaining fields

The analysis of the remaining fluctuations is more complicated， and the details are spelled out in Appendix B (and have been largely performed with the help of Mathematica, see also the ancillary workbook of the arXiv submission). It follows from eqs. (B.7O) - (B.76) that all the remaining fields mix, but one can diagonalize the corresponding matrix. The eigenvectors are complicated, but the eigenvalues - they correspond to the masses of the particles, since the above system of equation is simply the Klein-Gordon equation of seven coupled scalar particles on AdS $^ 3$ —are quite simple. Five of the eigenvalues of the matrix are directly of the above form

$$
\begin{array} { l } { { \lambda _ { 1 } = m _ { \ell ^ { + } , \ell ^ { - } - 2 } ^ { 2 } ~ , } } \\ { { \lambda _ { 2 } = m _ { \ell ^ { + } - 2 , \ell ^ { - } } ^ { 2 } ~ , } } \\ { { \lambda _ { 3 } = m _ { \ell ^ { + } , \ell ^ { - } } ^ { 2 } ~ , } } \\ { { \lambda _ { 4 } = m _ { \ell ^ { + } , \ell ^ { - } + 2 } ^ { 2 } ~ , } } \\ { { \lambda _ { 5 } = m _ { \ell ^ { + } + 2 , \ell ^ { - } } ^ { 2 } ~ , } } \end{array}
$$

where $m _ { \ell ^ { + } , \ell ^ { - } } ^ { 2 }$ is defined in (3.55),seealso (3.65).Theremaining two eigenvaluesare more complicated and take the form

$$
\lambda _ { 6 / 7 } = \left( 2 r ^ { - 1 } \pm \sqrt { r ^ { - 2 } + m _ { \ell ^ { + } , \ell ^ { - } } ^ { 2 } } \right) ^ { 2 } - r ^ { - 2 } ~ .
$$

Hence their associated conformal dimensions, which are obtained via $r ^ { 2 } \lambda ^ { 2 } = h ( h - 1 )$ ， are

$$
h _ { 6 / 7 } = { \frac { 1 } { 2 } } \left( 1 + \sqrt { 1 + r ^ { 2 } \lambda _ { 6 / 7 } } \right) = h _ { \ell ^ { + } , \ell ^ { - } } \pm 1 ~ ,
$$

where $h _ { \ell ^ { + } , \ell ^ { - } }$ is thecoforaldiesiooatedt $m _ { \ell ^ { + } , \ell ^ { - } } ^ { 2 }$

$$
\begin{array} { l } { { \displaystyle h _ { \ell ^ { + } , \ell ^ { - } } = \frac { 1 } { 2 } + \frac { 1 } { 2 } \sqrt { 1 + { r ^ { 2 } } \left( \frac { \ell ^ { + } ( \ell ^ { + } + 2 ) } { r _ { + } ^ { 2 } } + \frac { \ell ^ { - } ( \ell ^ { - } + 2 ) } { r _ { - } ^ { 2 } } \right) } } } \\ { { \displaystyle = \frac { 1 } { 2 } + \sqrt { \frac { 1 } { 4 } + k \left( \frac { j ^ { + } ( j ^ { + } + 1 ) } { k ^ { + } } + \frac { j ^ { - } ( j ^ { - } + 1 ) } { k ^ { - } } \right) } \equiv h _ { j ^ { + } , j ^ { - } } ~ . } } \end{array}
$$

In the final step we have used eq. (3.46) to convert the integer valued labels $\ell ^ { \pm }$ into the spin labels $j ^ { \pm }$ ，and eq. (3.23) to change from the radii to the levels we used earlier.

# 3.6 The full scalar spectrum

Taking these results together, we thus conclude that the supergravity spectrum contains the ten scalar fields

$$
( h _ { j ^ { + } \pm 1 , j ^ { - } } ; j ^ { + } , j ^ { - } ) ~ , ~ ( h _ { j ^ { + } , j ^ { - } \pm 1 } ; j ^ { + } , j ^ { - } ) ~ , ~ 4 \times ( h _ { j ^ { + } , j ^ { - } } ; j ^ { + } , j ^ { - } ) ~ , ~ ( h _ { j ^ { + } , j ^ { - } } \pm 1 ; j ^ { + } , j ^ { - } ) ~ .
$$

Note that we have suppressed $h$ and ${ \bar { j } } ^ { \pm }$ , since they agree with $h$ and $j ^ { \pm }$ , respectively, as we are only considering scalars, see the comment after eq. (3.6O). We have furthermore assumed that $j ^ { \pm } \geq 1$ ; for small values of $j ^ { \pm }$ (or rather $\ell ^ { \pm }$ ） the above analysis has to be adjusted, and this is explained in detail in Appendix C. (In particular, it follows that if $j ^ { \pm } = \textstyle { \frac { 1 } { 2 } }$ , the fields with spin $j ^ { \pm } - 1$ are absent; in addition, there are further restrictions if either (or both） spins vanish, $j ^ { \pm } = 0$ .） The above spectrum accounts correctly for the scalar modes of the NS-NS fields; there are also scalar fields arising from the R-R fields.

We note that $h _ { j ^ { + } , j ^ { - } }$ agrees precisely with our naive prediction from above, see eq. (2.19). As was explained there, this differs by 1 from (2.9); thus the only state that can directly satisfy the BPS bound is the one corresponding to the eigenvalue （204号 $h _ { j ^ { + } , j ^ { - } } - 1$ , and it actually only saturates the bound if $j ^ { + } = j ^ { - }$ ：

We can now compare this to the supergravity spectrum spelled out in [19], where it was claimed that it takes the form

Bosonic:

$$
\bigoplus _ { j ^ { + } \geq 0 , ~ j ^ { - } \geq 0 } \left( [ j ^ { + } , j ^ { - } ; j ^ { + } , j ^ { - } ] _ { s } ~ \oplus ~ [ j ^ { + } + \textstyle { \frac { 1 } { 2 } } , j ^ { - } + \textstyle { \frac { 1 } { 2 } } ; j ^ { + } + \textstyle { \frac { 1 } { 2 } } , j ^ { - } + \textstyle { \frac { 1 } { 2 } } ] _ { s } \right) ,
$$

except that the multiplet $[ 0 , 0 ; 0 , 0 ] _ { s }$ does not appear in the sum.

Fermionic:

$$
\bigoplus _ { j ^ { + } \geq 0 , ~ j ^ { - } \geq 0 } \left( [ j ^ { + } , j ^ { - } ; j ^ { + } + \frac { 1 } { 2 } , j ^ { - } + \frac { 1 } { 2 } ] _ { s } \oplus [ j ^ { + } + \frac { 1 } { 2 } , j ^ { - } + \frac { 1 } { 2 } ; j ^ { + } , j ^ { - } ] _ { s } \right) .
$$

In either case $[ j _ { 1 } ^ { + } , j _ { 1 } ^ { - } ; j _ { 2 } ^ { + } , j _ { 2 } ^ { - } ] _ { s } \equiv [ j _ { 1 } ^ { + } , j _ { 1 } ^ { - } ] _ { s } \otimes [ j _ { 2 } ^ { + } , j _ { 2 } ^ { - } ] _ { s }$ ，where the first and second factor corresponds to the left- and right-movers, respectively (and our conventions for the $D ( 2 , 1 | \alpha )$ representations are described in Appendix A.1.1). Since we have only analysed the scalar fields from the NS-NS sector, we cannot see all states from our above analysis; however, each multiplet (with the exception of the supergravity multiplet $[ \textstyle { \frac { 1 } { 2 } } , \textstyle { \frac { 1 } { 2 } } ; 0 , 0 ] _ { s }$ and $[ 0 , 0 ; { \textstyle \frac { 1 } { 2 } } , { \textstyle \frac { 1 } { 2 } } ] _ { s } )$ contains at least one NS-NS scalar field, and thus we can deduce the conformal dimensions of the relevant multiplets. In particular, in the first sum in (3.75) the ground states are NS-NS scalars, and they contain the four modes

$$
\begin{array} { r l } { [ j ^ { + } , j ^ { - } ; j ^ { + } , j ^ { - } ] _ { s } : \quad ( h _ { j ^ { + } , j ^ { - } } - 1 ; j ^ { + } , j ^ { - } ) \quad ( h _ { j ^ { + } , j ^ { - } } ; j ^ { + } , j ^ { - } ) } & { } \\ { \quad ( h _ { j ^ { + } , j ^ { - } } ; j ^ { + } - 1 , j ^ { - } ) \quad ( h _ { j ^ { + } , j ^ { - } } ; j ^ { + } , j ^ { - } - 1 ) ~ . } \end{array}
$$

On the other hand, the ground states of the second sum in (3.75) are R-R states, and their NS-NS contributions are then

$$
\begin{array} { r l } { [ j ^ { + } + \frac { 1 } { 2 } , j ^ { - } + \frac { 1 } { 2 } ; j ^ { + } + \frac { 1 } { 2 } , j ^ { - } + \frac { 1 } { 2 } ] _ { s } : \quad ( h _ { j ^ { + } , j ^ { - } } ; j ^ { + } + 1 , j ^ { - } ) } & { ( h _ { j ^ { + } , j ^ { - } } ; j ^ { + } , j ^ { - } + 1 ) } \\ & { ( h _ { j ^ { + } , j ^ { - } } ; j ^ { + } , j ^ { - } ) \qquad ( h _ { j ^ { + } , j ^ { - } } + 1 ; j ^ { + } , j ^ { - } ) ~ . } \end{array}
$$

Similarly, the two fermionic multiplets contain one NS-NS scalar each

$$
\begin{array} { l l } { { [ j ^ { + } , j ^ { - } ; j ^ { + } + { \frac { 1 } { 2 } } , j ^ { - } + { \frac { 1 } { 2 } } ] _ { s } : \quad ( h _ { j ^ { + } , j ^ { - } } ; j ^ { + } , j ^ { - } ) } } & { { } } \\ { { [ j ^ { + } + { \frac { 1 } { 2 } } , j ^ { - } + { \frac { 1 } { 2 } } ; j ^ { + } , j ^ { - } ] _ { s } : \quad ( h _ { j ^ { + } , j ^ { - } } ; j ^ { + } , j ^ { - } ) ~ . } } \end{array}
$$

In particular, it therefore follows that the first multiplet (3.77) is only BPS if $j ^ { + } = j ^ { - }$ ， since only in this case does $h _ { j + , j ^ { - } } - 1$ saturate the BPS bound; if $j ^ { + } \neq j ^ { - }$ , it is actually not BPS and combines with the second term in (3.75) to form a long multiplet, see eq. (A.14). The analysis in the other sectors works similarly (as does the various shortenings for small spin),and we therefore conclude that the correct supergravity spectrum takes the form

$$
\begin{array} { l } { { \displaystyle \bigoplus _ { j ^ { + } = j ^ { - } } \left( [ j ^ { + } , j ^ { - } ] _ { s } \oplus [ j ^ { + } + \frac { 1 } { 2 } , j ^ { - } + \frac { 1 } { 2 } ] _ { s } \right) \otimes \left( [ j ^ { + } , j ^ { - } ] _ { s } \oplus [ j ^ { + } + \frac { 1 } { 2 } , j ^ { - } + \frac { 1 } { 2 } ] _ { s } \right) } } \\ { { \displaystyle \oplus \bigoplus _ { j ^ { + } \neq j ^ { - } } [ j ^ { + } , j ^ { - } ] \otimes [ j ^ { + } , j ^ { - } ] ~ , } } \end{array}
$$

except that, as before, see eq. (3.75), the vacuum term $[ 0 , 0 ] _ { s } \otimes [ 0 , 0 ] _ { s }$ does not appear.

# 4Discussion and Outlook

In this paper we have analysed the BPS spectrum of supergravity and string theory on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ (with pure NS-NS flux). We have found that both spectra only contain BPS states in representations for which $j ^ { + } = j ^ { - }$ .Furthermore,the BPS spectra of both descriptions agree since the BPS part of supergravity - the first sum in (3.80) - agrees exactly with (2.16). Here we have used (A.26), namely that each BPS representation of the large $\mathcal { N } = 4$ superconformal algebra contains two BPS representations of the supergravity symmetry algebra $D ( 2 , 1 | \alpha )$

Our finding resolves a number of long-standing puzzles. In particular, the mysterious fact that the BPS bound for $D ( 2 , 1 | \alpha )$ is strictly weaker than that of the large （204号 $\mathcal { N } = 4$ superconformal algebra — compare （A.12） and （A.25） - seemed to imply that the supergravity BPS states have to acquire miraculous quantum corrections [9,19] in order to even satisfy the stringy BPS bound. This problem has now disappeared since the bounds only differ for $j ^ { + } \neq j ^ { - }$ -but for that case,there simply aren't any supergravity BPS states (and the supergravity states that do exist already satisfy the stringy BPS bound without any correction).

The other important consequence is that our result changes significantly the expectations for what the CFT dual of string theory on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ should be. In particular, the symmetric orbifold of the $S _ { 0 }$ theory that was first proposed for the case of $k ^ { + } = k ^ { - }$ in [20] and essentially ruled out because of its failure to reproduce the alleged BPS spectrum of supergravity [9] now appears to be a viable candidate after all; we will come back to analysing this possibility in more detail elsewhere [23]. We should also mention that, using integrability techniques, the BPS spectrum of string theory was analysed in [28],and that also from that perspective only BPS states with $j ^ { + } = j ^ { - }$ were found. This suggests that the BPS spectrum agrees for all (generic) points in moduli space (as is also the case for $\mathrm { A d S _ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { { \mathcal { M } } _ { 4 } }$ with $\mathcal { M } _ { 4 } = \mathbb { T } ^ { 4 }$ or $\mathcal { M } = \mathrm { K 3 }$ ); thus one should be able to identify the dual CFT directly based on the BPS spectrum, without any need to resort to the index techniques of [29].

# Acknowledgements

This paper is largely based on the Master thesis of one of us (LE). We thank Alessandro Sfondrini for comments on the draft and for sharing with us [28] prior to publication. We also thank Jan de Boer and Greg Moore for email correspondences, and Kevin Ferreira and Juan Jottar for discussions. The work of MRG is partly supported by the NCCR SwissMAP, funded by the Swiss National Science Foundation. He also thanks ITP of the Chinese Academy of Science for hospitality during the final stages of this work.

# A BPS representations of $D ( 2 , 1 | \alpha )$ and the $\mathcal { N } = 4$ algebra

# A.1 The $D ( 2 , 1 | \alpha )$ algebra

The superalgebra $D ( 2 , 1 | \alpha )$ is generated by

$$
{ \cal L } _ { 0 } ~ , { \cal L } _ { \pm 1 } ~ , ~ { \cal G } _ { \pm \frac { 1 } { 2 } } ^ { a } ~ , ~ { \cal A } _ { 0 } ^ { \pm , i } ~ .
$$

Here $a \in \{ 0 , 1 , 2 , 3 \}$ and $i \in \{ 1 , 2 , 3 \}$ , and the commutation relations are

$$
\begin{array} { l } { { \left[ L _ { m } , L _ { n } \right] = \left( m - n \right) L _ { m + n } } } \\ { { \left[ L _ { m } , G _ { r } ^ { a } \right] = \left( \frac { m } { 2 } - r \right) G _ { m + r } ^ { a } } } \\ { { \left[ A _ { 0 } ^ { \pm , i } , G _ { r } ^ { a } \right] = \mathrm { i } \alpha _ { a b } ^ { \pm i } G _ { r } ^ { b } } } \\ { { \left[ A _ { 0 } ^ { \pm , i } , A _ { 0 } ^ { \pm , j } \right] = \mathrm { i } \epsilon ^ { i j l } A _ { 0 } ^ { \pm , l } } } \\ { { \left\{ G _ { r } ^ { a } , G _ { s } ^ { b } \right\} = 2 \delta ^ { a b } L _ { r + s } + 4 \left( r - s \right) \left( \gamma \mathrm { i } \alpha _ { a b } ^ { + i } A _ { r + s } ^ { + , i } + \left( 1 - \gamma \right) \mathrm { i } \alpha _ { a b } ^ { - i } A _ { r + s } ^ { - , i } \right) \ , } } \end{array}
$$

while $[ L _ { m } , A _ { 0 } ^ { \pm , i } ] = 0$ .Furthermore, the expressions $\alpha _ { a b } ^ { \pm i }$ are the $4 \times 4$ matrices

$$
\alpha _ { a b } ^ { \pm i } = \frac { 1 } { 2 } \Big ( \pm \delta _ { i a } \delta _ { b 0 } \mp \delta _ { i b } \delta _ { a 0 } + \epsilon _ { i a b } \Big ) \ ,
$$

that satisfy the relations

$$
[ \alpha ^ { \pm i } , \alpha ^ { \pm j } ] = - \epsilon ^ { i j l } \alpha ^ { \pm l } ~ , \qquad [ \alpha ^ { + i } , \alpha ^ { - j } ] = 0 ~ , \qquad \{ \alpha ^ { \pm i } , \alpha ^ { \pm j } \} = - { \textstyle \frac 1 2 } \delta ^ { i j } ~ .
$$

The parameter $\gamma$ that appears in these commutation relations is expressed in terms of $\alpha$ as

$$
\gamma = \frac { \alpha } { 1 + \alpha } \ ,
$$

or equivalently

$$
\alpha = \frac { \gamma } { 1 - \gamma } \ .
$$

Note that the algebra is isomorphic under $\gamma  ( 1 - \gamma )$ ； in terms of $\alpha$ this is the transformation $\alpha  \alpha ^ { - 1 }$

# A.1.1 BPS representations

The highest weight representations of $D ( 2 , 1 | \alpha )$ are labelled by $j ^ { + } , j ^ { - } , h$ ，where $j ^ { \pm }$ are the spins of the two $\mathfrak { s u } ( 2 )$ algebras generated by $A _ { 0 } ^ { \pm i }$ ，while $h$ is the eigenvalue of $L _ { 0 }$ . (The highest weight states are annihilated by the positive modes, $G _ { 1 / 2 } ^ { a }$ and $L _ { 1 }$ .）A generic (long) representation has the form

$$
\begin{array} { c } { { ( j ^ { + } , j ^ { - } ) } } \\ { { ( j ^ { + } + \frac { 1 } { 2 } , j ^ { - } + \frac { 1 } { 2 } ) \left( j ^ { + } + \frac { 1 } { 2 } , j ^ { - } - \frac { 1 } { 2 } \right) \left( j ^ { + } - \frac { 1 } { 2 } , j ^ { - } + \frac { 1 } { 2 } \right) \left( j ^ { + } - \frac { 1 } { 2 } , j ^ { - } - \frac { 1 } { 2 } \right) } } \\ { { ( j ^ { + } + 1 , j ^ { - } ) \qquad ( j ^ { + } , j ^ { - } + 1 ) \qquad 2 \cdot ( j ^ { + } , j ^ { - } ) \qquad ( j ^ { + } - 1 , j ^ { - } ) \qquad ( j ^ { + } , j ^ { - } - 1 ) } } \\ { { ( j ^ { + } + \frac { 1 } { 2 } , j ^ { - } + \frac { 1 } { 2 } ) \left( j ^ { + } + \frac { 1 } { 2 } , j ^ { - } - \frac { 1 } { 2 } \right) \left( j ^ { + } - \frac { 1 } { 2 } , j ^ { - } + \frac { 1 } { 2 } \right) \left( j ^ { + } - \frac { 1 } { 2 } , j ^ { - } - \frac { 1 } { 2 } \right) } } \\ { { ( j ^ { + } , j ^ { - } ) \ , } } \end{array}
$$

where the different lines correspond to states with conformal dimension $h \ = \ h _ { 0 }$ ， （204号 $\begin{array} { r } { h = h _ { 0 } + \frac { 1 } { 2 } } \end{array}$ ， $h = h _ { 0 } + 1$ ， $\begin{array} { r } { h = h _ { 0 } + \frac { 3 } { 2 } } \end{array}$ and $h = h _ { 0 } + 2$ , respectively, whose $\mathfrak { s u } ( 2 ) \oplus \mathfrak { s u } ( 2 )$ representation is given. The BPS bound takes the form, see e.g., [9, 19]

$$
h \geq \left[ \frac { 1 } { 1 + \alpha } j ^ { - } + \frac { \alpha } { 1 + \alpha } j ^ { + } \right] .
$$

The corresponding BPS representation then consists of the subset of states, see [19] eq. (4.2)

$$
\begin{array} { c c c c } { { h = h _ { 0 } } } & { { } } & { { ( j ^ { + } , j ^ { - } ) } } & { { } } \\ { { h = h _ { 0 } + \frac { 1 } { 2 } } } & { { \ ( j ^ { + } + \frac { 1 } { 2 } , j ^ { - } - \frac { 1 } { 2 } ) \left( j ^ { + } - \frac { 1 } { 2 } , j ^ { - } + \frac { 1 } { 2 } \right) \left( j ^ { + } - \frac { 1 } { 2 } , j ^ { - } - \frac { 1 } { 2 } \right) } } & { { } } \\ { { h = h _ { 0 } + 1 } } & { { \ ( j ^ { + } , j ^ { - } - 1 ) } } & { { \ ( j ^ { + } - 1 , j ^ { - } ) } } & { { \ ( j ^ { + } , j ^ { - } ) } } \\ { { h = h _ { 0 } + \frac { 3 } { 2 } } } & { { \ } } & { { ( j ^ { + } - \frac { 1 } { 2 } , j ^ { - } - \frac { 1 } { 2 } ) } } \end{array}
$$

Here $\begin{array} { r } { h _ { 0 } = ( \frac { 1 } { 1 + \alpha } j ^ { - } + \frac { \alpha } { 1 + \alpha } j ^ { + } ) } \end{array}$ saturates the BPS bound. We shall denote the long representation (A.11） as $[ j ^ { + } , j ^ { - } ]$ ， and the short representation (A.13） as $[ j ^ { + } , j ^ { - } ] _ { s }$ Note that each long representation contains the set of states corresponding to two short representations

$$
[ j ^ { + } , j ^ { - } ] \cong [ j ^ { + } , j ^ { - } ] _ { s } \oplus [ j ^ { + } + { \textstyle { \frac { 1 } { 2 } } } , j ^ { - } + { \textstyle { \frac { 1 } { 2 } } } ] _ { s } ~ .
$$

The above description is only correct if $j ^ { \pm } \geq 1$ ; for small values of $j ^ { \pm }$ the representations are further shortened; explicit formulae for these representations are given in [19, eq. (4.3)].

# A.2 The large $\pmb { \mathcal { N } } = 4$ superconformal algebra

The large $\mathcal { N } = 4$ superconformal algebra $A _ { \gamma }$ whose wedge algebra is $D ( 2 , 1 | \alpha )$ is defined by (we follow the conventions of [30]),

$$
\begin{array} { r l } & { \quad [ U _ { m } , U _ { n } ] = \frac { k ^ { + + } } { 2 } m \delta _ { m , - n } } \\ & { \quad [ A _ { m } ^ { + , i } , Q _ { v } ^ { i } ] = \mathrm { i } \alpha _ { c \delta } ^ { + , i } Q _ { m + \gamma } ^ { \delta } } \\ & { \quad \{ Q _ { m } ^ { * } , Q _ { s } ^ { i } \} = \frac { k ^ { + } } { 2 } \frac { 1 } { \delta ^ { i } } \delta ^ { i k } \delta _ { n - s } } \\ & { \quad [ A _ { m } ^ { - i } , A _ { v } ^ { \pm , j } ] = \frac { k ^ { + } } { 2 } m \delta ^ { i j } \delta _ { m , \ \textrm { n } } + \mathrm { i } \mathrm { e } ^ { i j } A _ { m + \gamma } ^ { \pm , i } } \\ & { \quad [ U _ { m } , G _ { v } ^ { i } ] = m Q _ { m + \gamma } ^ { i j } } \\ & { \quad [ A _ { m } ^ { i , i } , G _ { m } ^ { i } ] = \mathrm { i } \alpha _ { c \delta } ^ { - 1 } \delta _ { m + \gamma } ^ { i j } = \frac { 2 k ^ { \pm } } { k ^ { + + } \mathcal { N } ^ { i j } } m \alpha _ { a b } ^ { \pm , i } Q _ { m + \gamma } ^ { \delta } } \\ & { \quad \{ Q _ { v } ^ { i } , G _ { s } ^ { i } \} = 2 \alpha _ { c \delta } ^ { i j } A _ { r + s } ^ { \pm , i } - 2 \alpha _ { c \delta } ^ { i j } A _ { r + s } ^ { - j } + \delta ^ { i \delta } U _ { r + s } } \\ & { \quad \{ G _ { r } ^ { - } , G _ { s } ^ { i } \} = \frac { 3 } { \delta } \delta ^ { i k } ( r ^ { 2 } - \mathrm { i } ) \delta _ { r , \alpha } + 2 \delta ^ { i \delta } L _ { r + s } } \\ & { \quad \quad \quad + 4 ( r - s ) \left( \gamma \mathrm { i } \alpha _ { d } ^ { \pm , i } A _ { r + s } ^ { \pm , i } + ( 1 - \gamma ) \mathrm { i } \alpha _ { c \delta } ^ { - , i } A _ { r + s } ^ { - , i } \right) . } \end{array}
$$

In terms of the levels of the two $\mathfrak { s u } ( 2 )$ algebras, we have

$$
\gamma = \frac { k ^ { - } } { k ^ { + } + k ^ { - } } ~ , \qquad c = \frac { 6 k ^ { + } k ^ { - } } { k ^ { + } + k ^ { - } } ~ .
$$

# A.2.1 The BPS Bound

The highest weight representations of the large superconformal $\mathcal { N } = 4$ algebra $A _ { \gamma }$ are characterised by $( h , j ^ { \pm } , u )$ ，where $h$ is the conformal dimension of the highest weight states,while $j ^ { \pm }$ are the spins of the two affine $\mathfrak { s u } ( 2 )$ algebras,and $u$ denotes the $\mathfrak { u } ( 1 )$ -charge, i.e. the eigenvalue under $U _ { 0 }$ . If we require unitarity, we need that $j ^ { \pm } \le k ^ { \pm } / 2$ . However, as explained in [16], unitarity actually requires that

$$
j ^ { \pm } \leq \frac { ( k ^ { \pm } - 1 ) } { 2 } .
$$

The BPS bound takes the form [16-18]

$$
h \geq \frac { 1 } { k ^ { + } + k ^ { - } } \left[ k ^ { + } j ^ { - } + k ^ { - } j ^ { + } + u ^ { 2 } + ( j ^ { + } - j ^ { - } ) ^ { 2 } \right] .
$$

Note that this bound differs from the the corresponding BPS bound of the wedge algebra $D ( 2 , 1 | \alpha )$ , see (A.12); apart from the additional $u ^ { 2 }$ term there is in particular also the $( j ^ { + } - j ^ { - } ) ^ { 2 }$ term. If we denote the corresponding representation by $[ j ^ { + } , j ^ { - } , u ]$ （20 then it only satisfies the BPS bound of $D ( 2 , 1 | \alpha )$ if $u = 0$ and $j ^ { + } = j ^ { - }$ . On the other hand,if this is the case, the BPS representation $[ j ^ { + } , j ^ { - } , u ]$ of the linear $A _ { \gamma }$ algebra contains actually two BPS representations of $D ( 2 , 1 | \alpha )$ （204号

$$
\begin{array} { r } { [ j , j , u = 0 ] _ { S } = [ j , j ] _ { s } \oplus [ j + \frac 1 2 , j \oplus \frac 1 2 ] _ { s } \oplus \mathrm { ~ n o n } { \bf - B P S } \mathrm { ~ r e p s ~ o f ~ } D ( 2 , 1 | \alpha ) ~ . } \end{array}
$$

This is basically a consequence of the fact that in addition to the four supercharges (that also appear in $D ( 2 , 1 | \alpha ) )$ ， $A _ { \gamma }$ also contains four free fermions.

# B The supergravity analysis

In this section we give some more details of the supergravity analysis of section 3. To start with,let us collect various identities that describe the action of differential operators on the spherical harmonics:

$$
\begin{array} { r l } & { \quad \Delta _ { + } Y _ { + } ^ { ( \ell 0 ) } = ( 1 - ( \ell + 1 ) ^ { 2 } ) Y _ { + } ^ { ( \ell 0 ) } ~ , } \\ & { \quad \Delta _ { + } Y _ { + , a } ^ { ( \ell + 1 ) } = ( 2 - ( \ell + 1 ) ^ { 2 } ) Y _ { + , a } ^ { ( \ell + 1 ) } ~ , } \\ & { \quad \nabla ^ { a } Y _ { + , a } ^ { ( \ell + 1 ) } = 0 ~ , } \\ & { \quad \Delta _ { 1 } Y _ { + , a b } ^ { ( \ell + 2 ) } = ( 3 - ( \ell + 1 ) ^ { 2 } ) Y _ { + , a b } ^ { ( \ell + 2 ) } ~ , } \\ & { \quad \nabla ^ { a } Y _ { + , a b } ^ { ( \ell + 2 ) } = 0 ~ , } \\ & { \quad \quad g ^ { a b } Y _ { + , a } ^ { ( \ell + 2 ) } = 0 ~ , } \\ & { \quad \quad \epsilon _ { a } ^ { b c } \partial _ { b } Y _ { + , c } ^ { ( \ell + 1 ) } = \pm ( \ell + 1 ) Y _ { - , a } ^ { ( \ell + 1 ) } ~ . } \end{array}
$$

Here, $\Delta _ { + }$ is the Laplace operator on $\mathrm { S _ { + } ^ { 3 } }$ . Similar formulae hold of course for $\mathrm { S _ { - } ^ { 3 } }$

# B.1Harmonic Expansion on $\mathbf { S _ { + } ^ { 3 } } \times \mathbf { S _ { - } ^ { 3 } }$

We expand the fields into harmonics as follows:

$$
\begin{array} { r l } & { \mathcal { A } _ { 4 , - } = \sum _ { \ell = 1 } ^ { n } \mathcal { L } _ { \ell } ^ { \mathrm { o r f } } \left( \mathcal { L } _ { \ell } ^ { \mathrm { o r f } } - \mathcal { L } _ { \ell } ^ { \mathrm { o r f } } \right) ^ { - 1 } \mathcal { L } _ { \ell } ^ { \mathrm { o r f } } = \mathcal { N } , } \\ & { \quad \bullet = \sum _ { \ell = 1 } ^ { n } e ^ { - \alpha _ { 1 } ( \ell - 1 ) \ell } \mathrm { e } ^ { \alpha _ { 2 } \Psi } \mathrm { e } ^ { \alpha _ { 2 } \Psi } + \mathcal { L } _ { \ell } ^ { \mathrm { o r f } } = \mathcal { L } _ { \ell } ^ { \mathrm { o r f } } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad }  \\ & & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad }  \\ & & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ &  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad  \end{array}
$$

$$
\begin{array} { l } { { E _ { a i } = \sum _ { \ell ^ { + } , \ell ^ { - } } E ^ { ( \ell ^ { + } \pm 1 ) ( \ell ^ { - } \pm 1 ) } Y _ { \downarrow , a } ^ { ( \ell ^ { + } \pm 1 ) } Y _ { - , \ell } ^ { ( \ell ^ { - } \pm 1 ) } + E ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } \pm 1 ) } \partial _ { a } Y _ { \downarrow } ^ { ( \ell ^ { + } 0 ) } Y _ { - , \ell } ^ { ( \ell ^ { - } \pm 1 ) } } } \\ { { \ \ \qquad + \ { \cal E } ^ { ( \ell ^ { + } \pm 1 ) ( \ell ^ { - } 0 ) } Y _ { \uparrow , a } ^ { ( \ell ^ { + } \pm 1 ) } \partial _ { i } Y _ { - } ^ { ( \ell ^ { - } 0 ) } + { \cal E } ^ { ( \ell ^ { - } 0 ) ( \ell ^ { - } 0 ) } \partial _ { a } Y _ { \uparrow } ^ { ( \ell ^ { + } 0 ) } \partial _ { i } Y _ { - } ^ { ( \ell ^ { - } 0 ) } ~ , } } \\  { { \cal K } _ { a b } = \sum _ { \ell ^ { + } , \ell ^ { - } } K ^ { ( \ell ^ { + } \pm 2 ) ( \ell ^ { - } 0 ) } Y _ { \uparrow , a b } ^ { ( \ell ^ { + } \pm 2 ) } Y _ { - } ^ { ( \ell ^ { - } 0 ) } + K ^ { ( \ell ^ { + } \pm 1 ) ( \ell ^ { - } 0 ) } \nabla _ { \left\{ a \right\} } Y _ { + , b \} ^ { ( \ell ^ { + } \pm 1 ) } Y _ { - } ^ { ( \ell ^ { - } 0 ) } } } \\ { { \ \qquad + \ { \cal K } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } \nabla _ { \left\{ a \right\} } \nabla _ { b } Y _ { + } ^ { ( \ell ^ { + } 0 ) } Y _ { - } ^ { ( \ell ^ { - } 0 ) } ~ , } } \\  { { \cal L } _ { i j } = \sum _ { \ell ^ { + } , \ell ^ { - } } L ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } \pm 2 ) } Y _ { \uparrow } ^ { ( \ell ^ { + } 0 ) } Y _ { - , j j } ^ { ( \ell ^ { - } \pm 2 ) } + { \cal K } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } \pm 1 ) } Y _ { \uparrow } ^ { ( \ell ^ { + } 0 ) } \nabla _ { \{ i } } Y _ { - , j \} ^ { ( \ell ^ { - } \pm 1 ) } } \\   \qquad + \ { \cal L } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } Y _ { \uparrow } ^ { ( \ell ^ { + } 0 ) } \nabla _ { \left\{ i \right\} ^ { \prime } } Y _ { - } ^ \end{array}
$$

i.e. for each $\ell ^ { \pm } \in \mathbb { N } _ { 0 }$ we have one set of harmonics.

# B.2 Splitting the Equations of Motion

In this section we study the equations of motion for the fluctuations $\left( \mathrm { B } . 8 \right) - \left( \mathrm { B } . 2 3 \right)$ 号 Inserting them into the quadratic action (3.26) we find the following equations of motion:

Dilaton:

$$
\begin{array} { l } { { 0 = \displaystyle - ( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } ) \phi + \frac 1 4 \Delta _ { 0 } ( 2 M + 3 N + 3 P ) + \frac 1 4 \Delta _ { + } ( 3 M + 2 N + 3 P ) } } \\ { { \displaystyle ~ + \frac 1 4 \Delta _ { - } ( 3 M + 3 N + 2 P ) - \frac 1 2 r ^ { - 1 } \nabla _ { \lambda } U ^ { \lambda } + \frac 1 2 r _ { + } ^ { - 1 } \nabla _ { a } V ^ { a } + \frac 1 2 r _ { - } ^ { - 1 } \nabla _ { i } W ^ { i } } } \\ { { \displaystyle ~ - \frac 1 4 \nabla _ { \mu } \nabla _ { \nu } H ^ { \mu \nu } - \frac 1 4 \nabla _ { i } \nabla _ { j } L ^ { i j } - \frac 1 2 \nabla _ { \mu } \nabla _ { i } S ^ { \mu i } ~ . } } \end{array}
$$

# Metric:

$\mu \nu \mathrm { \cdot }$ -trace component:

$$
\begin{array} { l }   0 = \displaystyle - ( \Delta _ { 0 } + 3 \Delta _ { + } + 3 \Delta _ { - } - 1 2 r ^ { - 2 } ) M - \Delta _ { 0 } ( 3 N + 3 P - 4 \phi ) - \Delta _ { + } ( 3 N + \frac { 9 } { 2 } P - 6 \phi ) M - \Delta _ { - } ( \frac { \Delta _ { + } } { 2 } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial \theta } \frac { \partial } { \partial r } \frac { \partial } { \partial r } \frac { \partial } { \partial \theta } \frac { \partial } { \partial r } \frac { \partial } { \partial \theta } \frac { \partial } { \partial r } \frac { \partial } { \partial \theta } \frac { \partial } { \partial r } \frac { \partial } { \partial \theta } \frac { \partial }  \partial \theta  \end{array}
$$

$\mu \nu$ -traceless component:

$$
\begin{array} { c } { { 0 = - ( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } - 4 r ^ { - 2 } ) H _ { \mu \nu } + 2 \nabla _ { \rho } \nabla _ { \{ \mu } } H _ { \nu \} ^ { \rho } + 2 \nabla _ { i } \nabla _ { \{ \mu } } S _ { \nu \} ^ { \quad i } } } \\ { { - \nabla _ { \{ \mu } } \nabla _ { \nu \} ( M + 3 N + 3 P - 4 \phi ) ~ . } } \end{array}
$$

$a b$ -trace component:

$$
\begin{array} { l } { { \displaystyle 0 = - \left( \Delta _ { 0 } + \frac 1 3 \Delta _ { + } + \Delta _ { - } + 4 r _ { + } ^ { - 2 } \right) N - \Delta _ { 0 } \left( M + \frac 3 2 P - 2 \phi \right) - \Delta _ { + } \left( M + P - \frac 4 3 \phi \right) ^ { 2 } } } \\ { { \displaystyle ~ - \Delta _ { - } \left( \frac 3 2 M + P - 2 \phi \right) + r ^ { - 1 } \nabla _ { \lambda } U ^ { \lambda } + r _ { + } ^ { - 1 } \nabla _ { a } V ^ { a } - r _ { - } ^ { - 1 } \nabla _ { i } W ^ { i } } } \\ { { \displaystyle ~ + \frac 1 2 \nabla _ { \mu } \nabla _ { \nu } H ^ { \mu \nu } + \frac 1 2 \nabla _ { i } \nabla _ { j } L ^ { i j } + \nabla _ { \mu } \nabla _ { i } S ^ { \mu i } ~ . } } \end{array}
$$

$a b$ -traceless component:

$$
\begin{array} { l } { { 0 = - ( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } - 2 r _ { + } ^ { - 2 } ) K _ { a b } - \nabla _ { \{ a } } \nabla _ { b \} ( 3 M + N + 3 P - 4 \phi ) } } \\ { { \qquad + \ 2 \nabla _ { \mu } \nabla _ { \{ a } } { R ^ { \mu } } _ { \ b { b } \} + 2 \nabla _ { i } \nabla _ { \{ a } } T _ { b \} \ d ^ { i } \ . } } \end{array}
$$

$i j$ -trace component:

$$
\begin{array} { r } { 0 = - \displaystyle \left( \Delta _ { 0 } + \Delta _ { + } + \frac { 1 } { 3 } \Delta _ { - } + 4 r _ { - } ^ { - 2 } \right) P - \Delta _ { 0 } \left( M + \frac { 3 } { 2 } N - 2 \phi \right) } \\ { - \Delta _ { + } \left( \frac { 3 } { 2 } M + N - 2 \phi \right) - \Delta _ { - } \left( M + N - \frac { 4 } { 3 } \phi \right) + r ^ { - 1 } \nabla _ { \lambda } U ^ { \lambda } - r _ { + } ^ { - 1 } \nabla _ { a } V ^ { a } } \\ { + r _ { - } ^ { - 1 } \nabla _ { i } W ^ { i } + \frac { 1 } { 2 } \nabla _ { \mu } \nabla _ { \nu } H ^ { \mu \nu } + \frac { 1 } { 6 } \nabla _ { i } \nabla _ { j } L ^ { i j } + \frac { 2 } { 3 } \nabla _ { \mu } \nabla _ { i } S ^ { \mu i } . \eqno { ( \mathrm { B } . } } \end{array}
$$

$i j$ -traceless component:

$$
\begin{array} { l } { { 0 = - ( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } + 4 r _ { - } ^ { - 2 } ) L _ { i j } - \nabla _ { \{ i } } \nabla _ { j \} ( 3 M + 3 N + P - 4 \phi ) } } \\ { { \qquad + \ 2 \nabla _ { k } \nabla _ { \{ i } } L _ { j \} ^ { k } + 2 \nabla _ { \mu } \nabla _ { \{ i } } S _ { ~ j \} ^ { \mu } \ . } } \end{array}
$$

μa-component:

$$
\begin{array} { r l r } { 0 = - \left( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } - 2 r _ { + } ^ { - 2 } \right) R _ { \mu a } + \nabla _ { \lambda } \nabla _ { \mu } R _ { ~ a } ^ { \lambda } + \nabla _ { \lambda } \nabla _ { a } H _ { \mu } { } ^ { \lambda } + \nabla _ { i } \nabla _ { \mu } T _ { a } { } ^ { i } + \nabla _ { i } \nabla _ { \alpha } S _ { \mu } } & { { } = 0 , } & { } \\ { + \nabla _ { b } \nabla _ { \mu } K _ { a } ^ { b } - \nabla _ { \mu } \nabla _ { a } \left( 2 M + 2 N + 3 P - 4 \phi \right) + 2 r ^ { - 1 } \nabla _ { a } U _ { \mu } - 2 r _ { + } ^ { - 1 } \nabla _ { \mu } V _ { a } } & { { } = 0 , } & { } \\ { - 2 r _ { + } ^ { - 1 } \epsilon _ { a b c } \nabla ^ { c } C _ { \mu } ^ { b } + 2 r ^ { - 1 } \epsilon _ { \mu \lambda \nu } \nabla ^ { \nu } C _ { ~ a } ^ { \lambda } \ . } & { { } } & { { \mathrm { ( B . 3 1 5 ~ \ ' ~ } } } \end{array}
$$

$\mu i$ -component:

$$
\begin{array} { r l r } { 0 = - \left( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } \right) S _ { \mu i } + \nabla _ { \lambda } \nabla _ { \mu } S _ { ~ i } ^ { \lambda } + \nabla _ { j } \nabla _ { \mu } L _ { i } ^ { ~ j } + \nabla _ { \lambda } \nabla _ { i } H _ { \mu } ^ { ~ \lambda } + \nabla _ { j } \nabla _ { i } S _ { \mu } ^ { ~ j } } & { } & \\ { - \nabla _ { \mu } \nabla _ { i } \left( 2 M + 3 N + 2 P - 4 \phi \right) + 2 r ^ { - 1 } \nabla _ { i } U _ { \mu } - 2 r _ { - } ^ { - 1 } \nabla _ { \mu } W _ { i } } & { } & \\ { - 2 r _ { - } ^ { - 1 } \epsilon _ { i j k } \nabla ^ { k } D _ { \mu } ^ { ~ j } + 2 r ^ { - 1 } \epsilon _ { \mu \lambda \nu } \nabla ^ { \nu } D _ { ~ i } ^ { \lambda } . } & { } & { { \mathrm { ( f } } } \end{array}
$$

$a i$ -component:

$$
\begin{array} { r l r } { \mathrm {  ~ \lambda ~ } } & { \mathrm {  ~ \lambda ~ } } & { \mathrm {  ~ \lambda ~ } ) = - \left( { \Delta } _ { 0 } + { \Delta } _ { + } + { \Delta } _ { - } - 2 r _ { + } ^ { - 2 } \right) T _ { a i } + \nabla _ { j } \nabla _ { a } L _ { i } ^ { ~ j } + \nabla _ { \mu } \nabla _ { i } R _ { ~ a } ^ { \mu } + \nabla _ { \mu } \nabla _ { a } S _ { ~ i } ^ { \mu } + \nabla _ { j } \nabla _ { i } T _ { a } ^ { ~ j } } \\ & { } & { \mathrm {  ~ \lambda ~ } - \nabla _ { i } \nabla _ { a } \left( 3 M + 2 N + 2 P - 4 \phi \right) - 2 r _ { - } ^ { - 1 } \nabla _ { a } W _ { i } - 2 r _ { + } ^ { - 1 } \nabla _ { i } V _ { a } \qquad } \\ & { } & { \mathrm {  ~ \lambda ~ } + 2 r _ { + } ^ { - 1 } \epsilon _ { a b c } \nabla ^ { c } L _ { ~ i } ^ { b } - 2 r _ { - } ^ { - 1 } \epsilon _ { i j k } \nabla ^ { k } L _ { a } ^ { ~ j } ~ . } \end{array}
$$

# Kalb-Ramondfield:

$\mu \nu$ -component (contracted with $\epsilon ^ { \mu \nu \lambda }$ ）

$$
\begin{array} { r c l } { { } } & { { } } & { { 0 = - \nabla ^ { \lambda } \nabla _ { \mu } U ^ { \mu } - ( \Delta _ { + } + \Delta _ { - } ) U ^ { \lambda } + r ^ { - 1 } \nabla ^ { \lambda } ( 3 M - 3 N - 3 P + 4 \phi ) } } \\ { { } } & { { } } & { { + 2 r ^ { - 1 } \nabla _ { i } S ^ { \lambda i } - \epsilon _ { \mu \nu } ^ { \lambda } \nabla _ { i } \nabla ^ { \nu } D ^ { \mu i } - \epsilon _ { \mu \nu } ^ { \lambda } \nabla _ { a } \nabla ^ { \nu } C ^ { \mu a } . } } \end{array}
$$

$a b$ -component (contracted with $\epsilon ^ { a b c }$ ）

$$
\begin{array} { r } { 0 = - \nabla ^ { c } \nabla _ { a } V ^ { a } - ( \Delta _ { 0 } + \Delta _ { - } ) V ^ { c } + r _ { + } ^ { - 1 } \nabla ^ { c } ( - 3 M + 3 N - 3 P + 4 \phi ) + 2 r _ { + } ^ { - 1 } \nabla _ { i } T ^ { c i } } \\ { + 2 r _ { + } ^ { - 1 } \nabla _ { \mu } R ^ { \mu c } + \epsilon ^ { c } { } _ { a b } \nabla _ { i } \nabla ^ { b } E ^ { a i } - \epsilon ^ { c } { } _ { a b } \nabla _ { \lambda } \nabla ^ { b } C ^ { \lambda a } \ . \eqno { ( \mathrm { B } . } } \end{array}
$$

$i j$ -component (contracted with $\epsilon ^ { i j k }$ ):

$$
\begin{array} { r l r } { \mathrm { } } & { 0 = - \nabla ^ { k } \nabla _ { i } W ^ { i } - ( \Delta _ { 0 } + \Delta _ { + } ) W ^ { k } + r _ { - } ^ { - 1 } \nabla ^ { k } ( - 3 M - 3 N + 3 P + 4 \phi ) + 2 r _ { - } ^ { - 1 } \nabla _ { \mu } S ^ { \mu k } } & { } \\ { - \epsilon _ { \ i j } ^ { k } \nabla _ { a } \nabla ^ { j } E ^ { a i } - \epsilon _ { \ i j } ^ { k } \nabla _ { \mu } \nabla ^ { j } D ^ { \mu i } . } & { } &  \mathrm  ( B . 3 M - 3 H \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H } \mathrm  H \mathrm { H } \mathrm { H } \mathrm { H } \mathrm { H ~ H } \mathrm { H ~ H } \mathrm  H \mathrm { H } \mathrm { H } \mathrm { H } \mathrm  \end{array}
$$

μa-component:

$$
\begin{array} { r } { 0 = - \left( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } - 2 r _ { + } ^ { - 2 } \right) C _ { \mu a } + \nabla _ { \lambda } \nabla _ { \mu } C ^ { \lambda } _ { a } + \nabla _ { i } \nabla _ { a } D _ { \mu } { } ^ { i } - \nabla _ { \mu } \nabla _ { i } E _ { a } ^ { \lambda } } \\ { + 2 r ^ { - 1 } \epsilon _ { \mu \lambda \nu } \nabla ^ { \nu } R ^ { \lambda } _ { a } - 2 r _ { + } ^ { - 1 } \epsilon _ { a b c } \nabla ^ { c } R ^ { \frac { b } { \mu } } + \epsilon _ { a b c } \nabla ^ { c } \nabla _ { \mu } V ^ { b } - \epsilon _ { \mu \lambda \nu } \nabla ^ { \nu } \nabla _ { a } U ^ { \lambda } . } \end{array}
$$

$\mu i$ -component:

$$
\begin{array} { r l } & { 0 = - \left( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } \right) D _ { \mu i } + \nabla _ { \lambda } \nabla _ { \mu } D _ { i } ^ { \lambda } _ { i } + \nabla _ { j } \nabla _ { i } D _ { \mu } ^ { \phantom { \mu } j } } \\ & { \phantom { = } + 2 r ^ { - 1 } \epsilon _ { \mu \lambda \nu } \nabla ^ { \nu } S _ { i } ^ { \lambda } - 2 r _ { - } ^ { - 1 } \epsilon _ { i j k } \nabla ^ { k } S _ { \mu } ^ { \phantom { \mu } j } + \epsilon _ { i j k } \nabla ^ { k } \nabla _ { \mu } W ^ { j } - \epsilon _ { \mu \lambda \nu } \nabla ^ { \nu } \nabla _ { i } U ^ { \lambda } . } \end{array}
$$

$a i$ -component:

$$
\begin{array} { r l } & { 0 = - \left( \Delta _ { 0 } + \Delta _ { + } + \Delta _ { - } - 2 r _ { + } ^ { - 2 } \right) E _ { a i } + \nabla _ { j } \nabla _ { i } E _ { a } ^ { \ j } - \nabla _ { \lambda } \nabla _ { i } C _ { \phantom { \lambda } a } ^ { \lambda } + \nabla _ { \lambda } \nabla _ { a } D _ { \phantom { \lambda } i } ^ { \lambda } } \\ & { \phantom { = } + 2 r _ { + } ^ { - 1 } \epsilon _ { a b c } \nabla ^ { c } T _ { \phantom { \frac { b } { ~ } } i } ^ { b } - 2 r _ { - } ^ { - 1 } \epsilon _ { i j k } \nabla ^ { k } T _ { \phantom { \mu } a } ^ { \ j } + \epsilon _ { i j k } \nabla ^ { k } \nabla _ { a } W ^ { j } \ . } \end{array}
$$

Note that we have broken the symmetry $\mathrm { S _ { + } ^ { 3 } }  \mathrm { S _ { - } ^ { 3 } }$ by our gauge choice, see eq. (3.49).

# B.3 Scalar Part of the Equations of Motion

From now on, we discuss the generic case where $\ell ^ { + } \geq 2$ and $\ell ^ { - } \geq 2$ . For low $\ell ^ { \pm }$ , there are additional issues to be taken care of; these cases are discussed in Appendix C. We now extract the scalar part of these equations. We have the following scalars:

$$
M , \ { \cal N } , \ { \cal P } , \ \phi , \ \nabla ^ { \mu } U _ { \mu } , \ \nabla ^ { a } V _ { a } , \ \nabla ^ { i } W _ { i } , \ \nabla _ { \mu } \nabla _ { \nu } H ^ { \mu \nu } , \ \nabla _ { i } \nabla _ { j } L ^ { i j } , \ \nabla _ { \mu } \nabla _ { i } S ^ { \mu i } , \ \nabla _ { \mu } \nabla _ { i } D ^ { \mu i } ~ .
$$

Note that we have

$$
\begin{array} { l } { { \nabla ^ { a } V _ { a } = - r _ { + } ^ { - 2 } \sum _ { \ell ^ { + } , \ell ^ { - } } \ell ^ { + } ( \ell ^ { + } + 2 ) V ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } Y _ { + } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } Y _ { - } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } ~ , ~ } } \\ { { \nabla ^ { i } W _ { i } = - r _ { - } ^ { - 2 } \sum _ { \ell ^ { + } , \ell ^ { - } } \ell ^ { - } ( \ell ^ { - } + 2 ) W ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } Y _ { + } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } Y _ { - } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } ~ , ~ } } \\ { { \nabla ^ { i } \nabla ^ { j } L _ { i j } = \frac { 2 } { 3 } r _ { - } ^ { - 4 } \sum _ { \ell ^ { + } , \ell ^ { - } } ( \ell ^ { - } - 1 ) \ell ^ { - } ( \ell ^ { - } + 2 ) ( \ell ^ { - } + 3 ) L ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } Y _ { + } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } Y _ { - } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } Y _ { - } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } ~ . } } \end{array}
$$

Since in the following， only $\Omega ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) }$ for some quantity $\Omega$ appears and we will consider fixed $\ell ^ { + }$ and $\ell ^ { - }$ ， we will use the shorthand notation

$$
\begin{array} { r l } & { \tilde { \phi } = \phi ^ { - \alpha \beta - \theta \beta - \theta \beta } , } \\ & { \mathcal { M } = M _ { \alpha } ^ { \dagger } ( \theta ) \otimes \theta , } \\ & { \mathcal { M } - N ^ { \prime } ^ { ( \epsilon ) } \otimes \theta ^ { ( \epsilon ) \alpha } , } \\ & { \mathcal { P } - r ^ { \alpha \beta - \theta \beta - \theta } , } \\ & { \mathcal { M } = r ^ { - \alpha \beta } \nabla r _ { \alpha } ^ { \beta + \gamma \theta } + \theta ^ { \epsilon } , } \\ & { \mathcal { M } = \nabla \theta ^ { \epsilon } \nabla r _ { \alpha } ^ { \beta + \gamma \theta } \Theta ^ { \epsilon } , } \\ & { \mathcal { P } - r ^ { \alpha \beta } \langle \tilde { \xi } ^ { \ast } | \tilde { \xi } ^ { \ast } | \ 2 \rangle \theta ^ { \epsilon + \gamma \theta } \Theta \ , } \\ & { \mathcal { N } - r ^ { \alpha \beta - \theta } \langle \tilde { \xi } ^ { \ast } | \ 2 \rangle \theta ^ { \epsilon + \alpha \beta - \theta \beta } , } \\ & { \mathcal { S } = - r ^ { \alpha \beta - \theta } \langle \tilde { \xi } ^ { \ast } + 2 \rangle \nabla r ^ { \alpha \beta - \theta \beta - \theta \beta } , } \\ & { \mathcal { D } = - r ^ { \alpha \beta - \theta } \langle \tilde { \xi } ^ { \ast } | \tilde { \xi } ^ { \ast } | \ 2 \rangle \theta ^ { \epsilon } \nabla \theta ^ { \epsilon } \Theta ^ { \epsilon } , } \\ & { \mathcal { D } = - r ^ { \alpha \beta - \theta } \langle \tilde { \xi } ^ { \ast } | \mathcal { E } ^ { \ast } - 2 \rangle \theta ^ { \epsilon + \gamma \theta } \langle \tilde { \xi } ^ { \ast } | \ 2 \rangle \theta ^ { \epsilon + \alpha \beta - \theta } , } \\ & { \mathcal { E } = \frac { 2 } { 2 } \xi ^ { - \alpha } \langle \tilde { \xi } ^ { \ast } - 1 \rangle \xi ^ { \alpha } \langle \tilde { \xi } ^ { \ast } + 2 | \tilde { \xi } ^ { \ast } - \mathrm { R i } \rangle \theta ^ { \epsilon + \gamma \theta } \Theta ^ { \epsilon } . } \end{array}
$$

Let us first discuss the equations. (B.37) gives immediately $\mathcal { D } = 0$ ,and this then also implies immediately the scalar parts of (B.38) and (B.39). On (B.28), we will apply $\nabla ^ { a } \nabla ^ { b }$ , then we will get an algebraic equation relating $\Phi$ ， $\mathcal { M }$ ， $\mathcal { N }$ and $\mathcal { P }$ . Extracting the scalar part of (B.33) by applying $\nabla ^ { a } \nabla ^ { i }$ will yield a further algebraic equation. A last algebraic equation will come from a combination of (B.25) and (B.27). We then have four algebraic equations, cutting down the number of scalar fields to seven. These seven fields combine with the three scalar fields we found earlier to yield a total of ten scalar fields in the compactification.

Let us begin with this outlined program. From (B.28)，we can upon application of $\nabla ^ { a } \nabla ^ { b }$ directly deduce that

$$
3 { \mathcal M } + { \mathcal N } + 3 { \mathcal P } - 4 \Phi = 0 \ .
$$

So we will eliminate the field $\Phi$ , furthermore $\mathcal { D } = 0$ holds as already mentioned. The remaining equations written with these replacements are:

# Dilaton:

$$
\begin{array} { l } { { 0 = \Delta _ { 0 } \left( - \displaystyle \frac 1 4 { \cal M } + \displaystyle \frac 1 2 { \cal N } \right) - \displaystyle \frac 1 4 \left( r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) + r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \right) { \cal N } + \displaystyle \frac 1 4 r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) { \cal N } , } } \\ { { { \mathrm { ~ ~ } } } } \\  { { \mathrm { ~ } - \displaystyle \frac 1 2 { \cal U } + \displaystyle \frac 1 2 { \cal V } + \displaystyle \frac 1 2 { \cal W } - \displaystyle \frac 1 4 { \cal H } - \displaystyle \frac 1 2 { \cal S } - \displaystyle \frac 1 4 { \cal L } . } } \\ { { { \mathrm { ~ ~ } } } } \end{array}
$$

Metric:

$\mu \nu$ -trace component:

$$
\begin{array} { r l } & { 0 = \Delta _ { 0 } ( 2 { \mathcal { M } } - 2 { \mathcal { N } } ) + r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \left( - \displaystyle \frac { 3 } { 2 } { \mathcal { M } } + 3 { \mathcal { N } } - \displaystyle \frac { 3 } { 2 } { \mathcal { P } } \right) + 1 2 r ^ { - 2 } { \mathcal { M } } } \\ & { \qquad + r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) \left( - \displaystyle \frac { 3 } { 2 } { \mathcal { M } } + \displaystyle \frac { 3 } { 2 } { \mathcal { N } } \right) - 3 { \mathcal { U } } - 3 { \mathcal { V } } - 3 { \mathcal { W } } + \displaystyle \frac { 1 } { 2 } { \mathcal { H } } + 3 { \mathcal { S } } - \displaystyle \frac { 3 } { 2 } { \mathcal { L } } ~ . } \end{array}
$$

$\mu \nu$ -traceless component:

$$
\begin{array} { l } { { 0 = \displaystyle \frac { 4 } { 3 } \Delta _ { 0 } ^ { 2 } ( { \mathcal M } - { \mathcal N } ) + \Delta _ { 0 } \left( - 4 r ^ { - 2 } { \mathcal M } + 4 r ^ { - 2 } { \mathcal N } + \displaystyle \frac { 1 } { 3 } { \mathcal H } + \displaystyle \frac { 4 } { 3 } { \mathcal S } \right) } } \\ { { + \left( r _ { + } ^ { - 2 } { \ell } ^ { + } ( { \ell } ^ { + } + 2 ) + r _ { - } ^ { - 2 } { \ell } ^ { - } ( { \ell } ^ { - } + 2 ) \right) { \mathcal H } - 4 r ^ { - 2 } { \mathcal S } \ . } } \end{array}
$$

$a b$ -trace component:

$$
\begin{array} { l } { { 0 = { \displaystyle \frac { 1 } { 2 } } \Delta _ { 0 } \left( { \cal M } - { \mathcal N } \right) + { \displaystyle \frac { 1 } { 2 } } r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \left( { \mathcal N } - { \mathcal P } \right) - 4 r _ { + } ^ { - 2 } { \mathcal N } + { \mathcal U } + { \mathcal V } - { \mathcal W } } } \\ { { \displaystyle \quad \quad + { \displaystyle \frac { 1 } { 2 } } { \mathcal H } + { \mathcal S } + { \displaystyle \frac { 1 } { 2 } } { \mathcal L } } . } \end{array}
$$

$i j$ -trace component:

$$
\begin{array} { r } { 0 = \Delta _ { 0 } \left( \displaystyle \frac 1 2 \mathcal { M } - \mathcal { N } + \displaystyle \frac 1 2 \mathcal { P } \right) + \left( \displaystyle \frac 1 2 r _ { + } ^ { - 2 } \mathcal { \ell } ^ { + } ( \ell ^ { + } + 2 ) + \displaystyle \frac 2 3 r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \right) ( \mathcal { N } - \mathcal { P } ) } \\ { - \displaystyle 4 r _ { - } ^ { - 2 } \mathcal { P } + \mathcal { U } - \mathcal { V } + \mathcal { W } + \displaystyle \frac 1 2 \mathcal { H } + \displaystyle \frac 2 3 \mathcal { S } + \displaystyle \frac 1 6 \mathcal { L } ~ . } \end{array}
$$

$i j$ -traceless component:

$$
\begin{array} { r l } {  { 0 = - \Delta _ { 0 } \mathcal { L } - 4 r _ { - } ^ { - 2 } \mathcal { L } + \frac { 4 } { 3 } r _ { - } ^ { - 4 } ( \ell ^ { - } - 1 ) \ell ^ { - } ( \ell ^ { - } + 2 ) ( \ell ^ { - } + 3 ) ( - \mathcal { N } + \mathcal { P } ) } } \\ & { + ( r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) - \frac { 1 } { 3 } r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) ) \mathcal { L } - \frac { 4 } { 3 } r _ { - } ^ { - 2 } ( \ell ^ { - } ( \ell ^ { - } + 2 ) - 3 ) \mathcal { S } \ . } \end{array}
$$

μa-component:

$$
0 = \Delta _ { 0 } \left( r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) ( { \cal M } + { \cal N } ) - 2 { \mathcal { V } } \right) + r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) ( - 2 { \mathcal { U } } - { \mathcal { H } } - { \mathcal { S } } ) \ .
$$

$\mu i$ -component:

$$
\begin{array} { r l r } { 0 } & { = \Delta _ { 0 } \left( r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) ( - \mathcal { M } + 2 \mathcal { N } - \mathcal { P } ) - 2 \mathcal { W } + \mathcal { L } \right) - r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) ( \mathcal { H } + 2 \mathcal { U } ) } & \\ & { \quad \quad \quad \quad + r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) \mathcal { S } . } & { \quad \quad \quad \quad ( \mathrm { B } . } \end{array}
$$

$a i$ -component:

$$
\begin{array} { r l } & { 0 = r _ { - } ^ { - 2 } r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) \ell ^ { - } ( \ell ^ { - } + 2 ) ( - \mathcal { N } + \mathcal { P } ) + 2 r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \mathcal { V } } \\ & { \qquad + r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) ( 2 \mathcal { W } - \mathcal { S } - \mathcal { L } ) ~ . } \end{array}
$$

Kalb-Ramondfield: $\mu \nu$ -component:

$$
0 = \Delta _ { 0 } \left( 6 \ell ^ { - 1 } \mathcal { M } - 2 \ell ^ { - 1 } \mathcal { N } - \mathcal { U } \right) + \left( r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) + r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \right) \mathcal { U } + 2 r ^ { - 1 } \mathcal { S } \ .
$$

$a b$ -component:

$$
0 = - \Delta _ { 0 } \mathcal { V } - 4 r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) \mathcal { N } + \left( r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) + r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \right) \mathcal { V } .
$$

$i j$ -component:

$$
\begin{array} { r l } & { 0 = - \Delta _ { 0 } \mathcal { W } + r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \left( 2 \mathcal { N } - 6 \mathcal { P } \right) } \\ & { \qquad + \left( r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) + r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \right) \mathcal { W } + 2 \mathcal { S } \ . } \end{array}
$$

From these equations, (B.57) $-$ $\cdot 4 \times ( 1$ 3.59) and (B.64) are algebraic and hence impose algebraic relationships among the fields. We use these relations to eliminate the fields （204号 $\boldsymbol { S }$ and $\mathcal { L }$ from the equations. Once these relations are imposed, we have

$$
\begin{array} { l } { { 0 = \displaystyle \frac { 1 } { 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) \times \left( \mathrm { B . 5 7 } \right) - 2 \times \left( \mathrm { B . 6 6 } \right) + r _ { + } ^ { 2 } \times \left( \mathrm { B . 6 2 } \right) , \hfill } } \\ { { 0 = 2 r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \times \left( \mathrm { B . 6 0 } \right) + \left( \mathrm { B . 6 1 } \right) + \left( \mathrm { B . 6 3 } \right) - 2 r _ { - } ^ { - 2 } \times \left( \mathrm { B . 6 7 } \right) . \hfill } } \end{array}
$$

Thus, we do not have to consider the equations (B.62) and (B.67) any longer.

We will not use the equation (B.58), since it contains squares of Laplacians. We will however check that the solution we obtain fulfills also this equation. Omitting for the moment this equation, we are left with seven equations for the seven unknowns $\mathcal { M } , \mathcal { N } , \mathcal { P } , \mathcal { U } , \mathcal { V } , \mathcal { W } , \mathcal { H }$ , namely (B.56)， (B.57)， (B.60), (B.63), (B.65), (B.66) and (B.67). For the sake of completeness, we reproduce here the solution, when solving these equations for the Laplacians:

$$
\begin{array} { r l r } {  { \Delta _ { 0 } \mathcal { M } = \big ( r _ { + } ^ { - 2 \ell ^ { 1 } } ( \ell ^ { 1 } + 2 ) + r _ { - } ^ { - 2 \ell ^ { - } } ( \ell ^ { - } + 2 ) - 8 r ^ { - 2 } \big ) } } \\ & { } & { \times ( \mathcal { M } + 4 r ^ { - 2 } \mathcal { U } + 2 r _ { - } ^ { - 2 } \mathcal { W } - \frac { 3 2 } { 3 } r ^ { - 2 } \mathcal { H } ) , } & { \mathrm { ( B . 7 . ~ } } \\ { \bigtriangleup _ { 0 } \mathcal { N } = \frac { 1 6 } { 3 } r _ { + } ^ { - 2 } \mathcal { M } + \big ( r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) + r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \big ) \mathcal { N } + \frac { 1 1 2 } { 3 } r ^ { - 2 } r _ { + } ^ { - 2 } \mathcal { U } \ ~ } \\ & { } & { + 4 r _ { + } ^ { - 4 } \ell ^ { 1 } ( \ell ^ { 1 } + 2 ) \mathcal { V } + 2 r _ { - } ^ { - 2 } ( r _ { + } ^ { - 2 } \ell ^ { 1 } ( \ell ^ { 1 } + 2 ) + 2 \ell ^ { - } ( \ell ^ { - } + 2 ) + \frac { 3 2 } { 3 } r _ { + } ^ { - 2 } ) \mathcal { W } } \\ & { } & { + \frac { 3 2 } { 3 } r _ { - } ^ { - 2 } ( 2 r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) + 2 r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) - \frac { 1 3 } { 3 } r _ { + } ^ { - 2 } - \frac { 3 7 } { 3 } r _ { - } ^ { - 2 } ) \mathcal { H } ~ , } \end{array}
$$

$$
\begin{array} { l } { { \Delta _ { 0 } \mathcal { P } = \left( r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) + r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) + 8 r _ { - } ^ { - 2 } \right) \mathcal { P } - 6 r _ { - } ^ { - 4 } \ell ^ { - } ( \ell ^ { - } + 2 ) \mathcal { W } \ , } } \\ { { \Delta _ { 0 } \mathcal { U } = \displaystyle \frac { 8 } { 3 } \mathcal { M } + \left( r _ { + } ^ { - 2 } \ell ^ { + } ( \ell ^ { + } + 2 ) + r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) + \displaystyle \frac { 2 0 } { 3 } r ^ { - 2 } \right) \mathcal { U } - \displaystyle \frac { 2 8 } { 3 } r _ { - } ^ { - 2 } \mathcal { W } } } \end{array}
$$

$$
\begin{array} { r l } { - \frac { \Delta } { \Delta x } \left( \frac { \partial } { \partial x } \rho ^ { - \alpha } + \gamma _ { + } + \alpha ^ { - \beta } + \gamma _ { - } ^ { \alpha } + \gamma _ { - } ^ { \beta } + \alpha ^ { - \beta } + 1 \right) + \frac { 1 } { \Delta x } - \frac { \partial } { \partial x } \mathbb { R } _ { - 1 } } & { \qquad \mathbb { E } \rho \geq \frac { \partial } { \partial x } } \\ { \Delta \rho ^ { \beta } - ( \gamma ^ { + } + \gamma _ { - } ^ { \beta } + \gamma _ { - } ^ { \beta } + \gamma _ { - } ^ { \beta } + \gamma _ { - } ^ { \beta } ) } & { \qquad \mathrm { i f ~ } \rho > \frac { \partial } { \partial x } < \rho ^ { \beta } < \gamma _ { - } ^ { \beta } < \gamma _ { - } ^ { \beta } < \gamma _ { - } ^ { \beta } < \gamma _ { 0 } \medskip \medskip } \\ { - \frac { \Delta ^ { \beta } ( \gamma ^ { + } \gamma _ { + } ^ { \beta } - \gamma _ { - } ^ { \beta } - \gamma _ { - } ^ { \beta } + \gamma _ { - } ^ { \beta } + \gamma _ { - } ^ { \beta } - \gamma _ { 0 } ^ { \beta } - \alpha ^ { - \beta } + \gamma _ { - } ^ { \beta } ; \gamma _ { - } ^ { \beta } + \gamma _ { \gamma } ^ { \beta } ) } { \mathrm { i f ~ } \rho > \alpha ^ { \beta } } } & { } \\ { - \frac { \Delta ^ { \beta } ( \gamma ^ { + } \gamma _ { + } ^ { \beta } + \gamma _ { - } ^ { \beta } - \gamma _ { 0 } ^ { \beta } - \gamma _ { - } ^ { \beta } - \gamma _ { 0 } ^ { \beta } - \gamma _ { 0 } ^ { \beta } - \gamma _ { 0 } ^ { \beta } - \gamma _ { - } ^ { \beta } + \gamma _ { - } ^ { \beta } ; \gamma _ { \pm } ^ { \beta } + \gamma _ { 0 } ^ { \beta } ) } { \mathrm { i f ~ } \rho > \alpha ^ { \beta } } } \\  - \frac { \Delta ^ { \beta } ( \gamma ^ { + } \gamma _ { + } ^ { \beta } - \gamma _ { 0 } ^ { \beta } - \gamma _ { 0 } ^ { \beta } - \gamma _ { 0 } ^ { \beta } - \gamma _ { 0 } ^ { \beta } ) } { \mathrm { i f ~ } \rho > \alpha ^ { \beta } + \gamma _ { - } ^ { \beta } } & { \qquad \mathrm { i f ~ } \rho > \alpha ^ { \beta } + \gamma _ { 0 } ^ { \beta } } \\  - \frac { \partial } { \partial x } \rho ^ { - \alpha } \mathrm { f o r ~ } \rho ^ { \beta } < \gamma _ { - } ^ { \beta } \mathrm { f o r ~ } \rho ^ { \beta } - \mathrm { i d . } \rho ^  \beta  \end{array}
$$

As promised, also (B.58) is satisfied by this solution.

# CSpecial cases at low $\ell ^ { \pm }$

# C.1 Residual gauge transformations

Before discussing the various special cases, we have to find all residual gauge transformations, since those gauge away modes with low $\ell ^ { + }$ . There are two of those, modifying scalar fields.

$\mathbf { A d S _ { 3 } } \times \mathbf { S ^ { 3 } }$ -reparametrisations:

$$
\begin{array} { l } { { \displaystyle \xi _ { \mu } = \sum _ { \ell ^ { - } } \xi _ { \mu } ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } Y _ { - } ^ { ( \ell ^ { - } 0 ) } ~ , } } \\ { { \displaystyle \xi _ { a } = 0 ~ , } } \\ { { \displaystyle \xi _ { i } = \sum _ { \ell ^ { - } } \xi ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } \nabla _ { i } Y _ { - } ^ { ( \ell ^ { - } 0 ) } ~ . } } \end{array}
$$

They induce the following transformations on the fields (only the non-trivial transformations are displayed):

$$
\begin{array} { c } { { \delta H _ { \mu \nu } ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } = 2 \nabla _ { \{ \mu } { \xi } _ { \nu \} } \qquad } } \\ { { \delta M ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } = \displaystyle \frac { 2 } { 3 } \nabla ^ { \mu } { \xi } _ { \mu } ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } \ , } } \\ { { \delta L _ { i j } ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } = 2 \xi ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } \ , } } \end{array}
$$

$$
\begin{array} { l } { { \delta P ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } = - \displaystyle \frac { 2 } { 3 } r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \xi ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } ~ , } } \\ { { \delta S _ { \mu } ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } = \xi _ { \mu } ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } + \nabla _ { \mu } \xi ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } ~ . } } \end{array}
$$

Stückelberg shift symmetries:

$$
\begin{array} { l } { { \xi _ { \mu } = - \sum _ { \ell ^ { - } } \nabla _ { \mu } \lambda ^ { \left( 1 0 \right) ( \ell ^ { - } 0 ) } Y _ { + } ^ { \left( 1 0 \right) } Y _ { - } ^ { \left( \ell ^ { - } 0 \right) } \ , } } \\ { { \xi _ { a } = \sum _ { \ell ^ { - } } \lambda ^ { \left( 1 0 \right) ( \ell ^ { - } 0 ) } \nabla _ { a } Y _ { + } ^ { \left( 1 0 \right) } Y _ { - } ^ { \left( \ell ^ { - } 0 \right) } \ , } } \\ { { \xi _ { i } = - \sum _ { \ell ^ { - } } \lambda ^ { \left( 1 0 \right) ( \ell ^ { - } 0 ) } Y _ { + } ^ { \left( 1 0 \right) } \nabla _ { i } Y _ { - } ^ { \left( \ell ^ { - } 0 \right) } \ . } } \end{array}
$$

Transforming the coordinate system with this vector field preserves the gauge (3.49) and we find for the metric

$$
\begin{array} { l }  { \displaystyle \delta H _ { \mu \nu } ^ { ( 1 0 ) ( \ell ^ { - 0 } ) } = - 2 \nabla _ { \{ \mu } \} \nabla _ { \nu \} \lambda ^ { ( 1 0 ) ( \ell ^ { - 0 } ) } ~ , } } \\ { { \displaystyle \delta H ^ { ( 1 0 ) ( \ell ^ { - 0 } ) } = - \frac { 2 } { 3 } \Delta _ { 0 } \lambda ^ { ( 1 0 ) ( \ell ^ { + 0 } ) } ~ , } } \\ { { \displaystyle \delta N ^ { ( 1 0 ) ( \ell ^ { - 0 } ) } = - 2 r _ { + } ^ { - 2 } \lambda ^ { ( 1 0 ) ( \ell ^ { + 0 } ) } ~ , } } \\ { { \displaystyle \delta P ^ { ( 1 0 ) ( \ell ^ { - 0 } ) } = \frac { 2 } { 3 } \ell ^ { - } ( \ell ^ { - } + 2 ) r _ { - } ^ { - 2 } \lambda ^ { ( 1 0 ) ( \ell ^ { - 0 } ) } ~ , } } \\ { { \displaystyle \delta L ^ { ( 1 0 ) ( \ell ^ { - 0 } ) } = - 2 \lambda ^ { ( 1 0 ) ( \ell ^ { - 0 } ) } ~ , } } \\ { { \displaystyle \delta S _ { \mu } ^ { ( 1 0 ) ( \ell ^ { - 0 } ) } = - 2 \nabla _ { \mu } \lambda ^ { ( 1 0 ) ( \ell ^ { - 0 } ) } ~ . } } \end{array}
$$

We will not need the transformation properties of the antisymmetric tensor field.

# C.2 Metric，Dilaton andKalb-RamondField

Let us first describe how the analysis of Appendix B gets modified for small $\ell ^ { \pm }$ ; the corresponding analysis for the decoupled subsystem of Section 3.4 will be described below in Section C.3.

# C.2.1 $\ell ^ { + } > 1$ ， $\ell ^ { - } = 1$ （20

This is the first special case. Then we have from (B.54) that $\mathcal { L } = 0$ . We still have exactly the same algebraic relationships,i.e. $\mathcal { D } = 0$ , (B.55), (B.57) $-$ 4 $\times$ (B.59) and (B.64). We use them to eliminate also $\mathcal { W }$ in this case, so we remain only with six fields. We have the same linear relationships as (B.68) and (B.69). On top of this, (B.61) just vanishes trivially. Thus, in this case, we are left with six equations for the six unknowns. They can again be solved and (B.58) is automatically satisfied by the solution. The eigenvalues of the corresponding matrix are exactly the same as before, except that now $m _ { \ell ^ { + } , \ell ^ { - } - 2 } ^ { 2 }$ is missig.Tis wastoeexpected,icee cannot have negative $\ell ^ { - }$

# C.2.2 （204号 $\ell ^ { + } = 1$ ， $\ell ^ { - } > 1$ （204号

Now we cannot deduce any longer (B.55)， since the application of $\nabla ^ { a } \nabla ^ { b }$ on (B.28) just vanishes. However, we can use the Stickelberg shift symmetry (C.12) - (C.17) to gauge some fields away. Using $\lambda ^ { ( 1 0 ) ( \ell ^ { - } 0 ) }$ satisfying

$$
( \Delta _ { 0 } + r _ { + } ^ { - 2 } - r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) ) \lambda ^ { ( 1 0 ) ( \ell ^ { - } 0 ) } = { \frac { 1 } { 2 } } ( 3 { \mathcal { M } } + { \mathcal { N } } + 3 { \mathcal { P } } - 4 \Phi ) ~ ,
$$

we can impose (B.55） as a gauge condition. Afterwards the analysis goes through as in the general case,but we still have a residual gauge transformation, as we can perform the Stickelberg shift with $\lambda ^ { ( 1 0 ) ( \ell ^ { - } 0 ) }$ satisfying

$$
\begin{array} { r } { ( \Delta _ { 0 } + r _ { + } ^ { - 2 } - r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) ) \lambda ^ { ( 1 0 ) ( \ell ^ { - } 0 ) } = 0 \ . } \end{array}
$$

Thisquationofotioswithtgenvetoroingt $m _ { \ell ^ { + } - 2 , \ell ^ { - } } ^ { 2 }$ and hence we can use this remaining gauge freedom to gauge this eigenvector away. Thus, we conclude,asinthepreviouscase,that weobtaialfeds,but $m _ { \ell ^ { + } - 2 , \ell ^ { - } } ^ { 2 }$ is missing. This was to be expected, since the spectrum must be symmetric in $\ell ^ { + }$ and $\ell ^ { - }$ ：

# C.2.3 （204号

This is just the combination of the previous cases. After setting the gauge as in (C.18)，we perform the same analysis as for $\ell ^ { + } > 1$ and $\ell ^ { - } = 1$ . Thus again the eigenvalue $m _ { \ell ^ { + } , \ell ^ { - } - 2 } ^ { 2 }$ getsdt away $m _ { \ell ^ { + } - 2 , \ell ^ { - } } ^ { 2 }$ .Thus we are left with only five fields.

# C.2.4 $\ell ^ { + } > 1$ ， $\ell ^ { - } = 0$ （204号

In this case we have by definition $\mathcal { W } = \boldsymbol { S } = \mathcal { L } = \mathcal { D } = \boldsymbol { 0 }$ . (B.55） again holds since $\ell ^ { + } > 1$ . The equations (B.61),(B.63), (B.64) and (B.67) are trivially satisfied, since $\nabla ^ { i }$ now annihilates everything. We are left with the six unknowns $\mathcal { M } , \mathcal { N } , \mathcal { P } , \mathcal { U } , \mathcal { H }$ and $\nu$ . From (B.57) $-$ 4 $\times$ (B.59),we get again one further algebraic constraint with which we eliminate $\nu$ . (B.68) ist still true, the second linear dependency is trivial in this case. We are thus left with five equations (B.56)， (B.57)， (B.60)， (B.65) and (B.66) for the five unknowns. The solution again passes the check of satisfying (B.58).Theigevaeebortie $m _ { \ell ^ { + } , \ell ^ { - } } ^ { 2 }$ and $m _ { \ell ^ { + } , \ell ^ { - } - 2 } ^ { 2 }$ are missing.

# C.2.5 （204号 （204号

We now have by definition $\nu = 0$ .We choose $\xi _ { \mu } ^ { ( 0 0 ) ( \ell ^ { - } 0 ) }$ and $\xi ^ { ( 0 0 ) ( \ell ^ { - } 0 ) }$ such that

$$
\begin{array} { r c l } { { r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \xi ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } - \nabla ^ { \mu } \xi _ { \mu } ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } = \displaystyle \frac { 1 } { 2 } \left( 3 { \mathcal { M } } + { \mathcal { N } } + 3 { \mathcal { P } } - 4 \Phi \right) ~ , } } \\ { { \displaystyle ( \Delta _ { 0 } - 3 r ^ { - 2 } ) \nabla ^ { \mu } \xi _ { \mu } = - \frac { 3 } { 4 } { \mathcal { H } } ~ , } } \end{array}
$$

so (B.55） again holds and $\mathcal { H } = 0$ . Now the equations (B.62)， (B.64)， (B.66) are trivial， furthermore the constraint $\mathcal { D } = 0$ is no longer implied by (B.37)， (B.38) and (B.39),and their scalar part is now also trivial. However, $\mathcal { D }$ does not appear anywhere in the field equations and hence is not a dynamical field, so we will not consider it further. The residual gauge transformations now satisfy

$$
( \Delta _ { 0 } - 3 r ^ { - 2 } ) \nabla ^ { \mu } \xi _ { \mu } ^ { ( \ell ^ { + } 0 ) ( \ell ^ { - } 0 ) } = 0 \ , \quad r _ { - } ^ { - 2 } \ell ^ { - } ( \ell ^ { - } + 2 ) \xi ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } - \nabla ^ { \mu } \xi _ { \mu } ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } = 0 \ .
$$

Again (B.57) $-$ 4 $\times$ (B.59) is algebraic and we use it to eliminate $\boldsymbol { S }$ . Thus, we remain with the fields $\mathcal { M } , \mathcal { N } , \mathcal { P } , \mathcal { U } , \mathcal { W } , \mathcal { L }$ . Now (B.68) is trivial, but (B.69) eliminates the equation (B.61). We are left with six independent equations, namely (B.56), (B.57), (B.60), (B.63)， (B.65) and (B.67) for the six unknowns. The solution satisfies again (B.58), and the eigenvalues are

$$
m _ { \ell ^ { + } + 2 , \ell ^ { - } } ^ { 2 } ~ , ~ m _ { \ell ^ { + } , \ell ^ { - } \pm 2 } ^ { 2 } ~ , ~ \lambda _ { 6 / 7 } ~ , ~ 3 r ^ { - 2 } ~ ,
$$

where $\lambda _ { 6 / 7 }$ are as in (3.71). Since the equations of motion of the residual gauge transformation （C.22） and the eigenvector corresponding to $3 r ^ { - 2 }$ coincide,we can gauge that eigenvector away. Thus, we find again the same states as in the previous subsection, except that $\ell ^ { + }$ and $\ell ^ { - }$ are interchanged.

# C.2.6 （204 （20

Everything is as in the previous section, except that also $\mathcal { L } = 0$ by definition. (B.61) is now identically zero and hence we use (B.69) to eliminate (B.6O). The resulting system has five unknowns, the solution fulfills again (B.58) and the eigenvalues are

$$
m _ { \ell ^ { + } + 2 , \ell ^ { - } } ^ { 2 } \ , m _ { \ell ^ { + } , \ell ^ { - } + 2 } ^ { 2 } \ , \lambda _ { 6 / 7 } \ , 3 r ^ { - 2 } \ .
$$

Again, using a residual gauge transformation, we can gauge the eigenvector corresponding to $3 r ^ { - 2 }$ away.

# C.2.7 $\ell ^ { + } = 1$ ， $\ell ^ { - } = 0$ （20

We again use the Stückelberg transformation (C.18) to enforce (B.55). Afterwards, the analysis is the same as for $\ell ^ { - } = 0$ and $\ell ^ { + } > 1$ . As for general $\ell ^ { + } > 1$ ，we can gauge away the eigenvector corresponding to the eigenvalue $m _ { \ell ^ { + } - 2 , \ell ^ { - } } ^ { 2 }$ . Thus, the only remaining eigenvalues are

$$
m _ { \ell ^ { + } + 2 , \ell ^ { - } } ^ { 2 } \ , m _ { \ell ^ { + } , \ell ^ { - } + 2 } ^ { 2 } \ , \lambda _ { 6 / 7 } \ .
$$

# C.2.8 （20 $\ell ^ { + } = \ell ^ { - } = 0$ （20

We have by definition $\mathcal { V } = \mathcal { W } = \mathcal { S } = \mathcal { L } = 0$ ： $\mathcal { D }$ again never appears in any equation and is hence not physical. We again perform a reparametrisation of $\mathrm { A d S _ { 3 } \times S _ { - } ^ { 3 } }$ to enforce (B.55), but one easily sees that $\mathcal { H } = 0$ can no longer be achieved. In fact, $\xi ^ { ( 0 0 ) ( 0 0 ) }$ never enters in the transformation. Again the combination (B.57)-4 $\times$ (B.59) is algebraic and we eliminate also $\boldsymbol { \mathcal { U } }$ . Thus we are left with only $\mathcal { M }$ ， $\mathcal { N }$ ， $\mathcal { P }$ and $\mathcal { H }$ The solution again fulfills (B.58) and has eigenvalues

$$
m _ { \ell ^ { + } , \ell ^ { - } } ^ { 2 } \ , m _ { \ell ^ { + } + 2 , \ell ^ { - } } ^ { 2 } \ , m _ { \ell ^ { + } , \ell ^ { - } + 2 } ^ { 2 } \ , m _ { \ell ^ { + } + 2 , \ell ^ { - } + 2 } ^ { 2 } \ .
$$

[Note that for $\ell ^ { + } = \ell ^ { - } = 0$ ，（ $m _ { \ell ^ { + } + 2 , \ell ^ { - } + 2 } ^ { 2 } = m _ { 2 , 2 } ^ { 2 } = \lambda _ { 6 }$ ] Residual gauge transfomations are $\xi _ { \mu } ^ { ( 0 0 ) ( 0 0 ) }$ satisfying $\nabla ^ { \mu } \xi _ { \mu } ^ { ( 0 0 ) ( 0 0 ) } = 0$ ,i. stting

$$
\xi _ { \mu } ^ { ( 0 0 ) ( 0 0 ) } = \nabla _ { \mu } \zeta ^ { ( 0 0 ) ( 0 0 ) } \ ,
$$

$\zeta ^ { ( 0 0 ) ( 0 0 ) }$ satisfies $\Delta _ { 0 } \zeta ^ { ( 0 0 ) ( 0 0 ) } = 0$ . Hence we can use it to gauge away the zero eigenvector which corresponds to $m _ { \ell ^ { + } , \ell ^ { - } } ^ { 2 } = m _ { 0 , 0 } ^ { 2 } = 0$ （2

# C.3 The scalars from the decoupled subsystem

Finally, let us describe what happens to the scalar degrees of freedom from the decoupled subsystem， see Section 3.4. We have already used up al residual gauge transformations for the metric, dilaton and the Kalb-Ramond field. We easily see that $\Psi$ is always present, regardless of the value of $\ell ^ { + }$ and $\ell ^ { - }$ .For $\Upsilon _ { M }$ ，we note that there is a residual gauge symmetry for $\Upsilon _ { M }$ ， namely $\delta \Upsilon _ { M } = \nabla _ { M } \Lambda$ . Choosing

$$
\Lambda = \sum _ { \ell ^ { - } } \Lambda ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } Y _ { - } ^ { ( \ell ^ { - } 0 ) } \ ,
$$

the Lorentz gauge is preserved. If $\ell ^ { - } = 0$ ， $\nabla ^ { i } \Omega _ { i } = 0$ and hence no scalar component of $\Upsilon _ { M }$ survives. Similarly, if $\ell ^ { + } = 0$ ， we can use this remaining gauge symmetry to set $\nabla ^ { \mu } \Pi _ { \mu } = 0$ . But in this case, $\nabla ^ { i } \Omega _ { i }$ survives, since it must not be equal to $\nabla ^ { \mu } \Pi _ { \mu }$ . It is however annihilated by $\Delta _ { 0 }$ and hence can be gauged away, since we have a remaining gauge freedom of $\Lambda ^ { ( 0 0 ) ( \ell ^ { - } 0 ) }$ satisfying $\Delta _ { 0 } \Lambda ^ { ( 0 0 ) ( \ell ^ { - } 0 ) } = 0$ ：

# References

[1] J.R. David, G. Mandal and S.R. Wadia,“Microscopic formulation of black holes in string theory,”Phys.Rept.369 (2002) 549 [hep-th/0203048].   
[2] M.R. Gaberdiel and I. Kirsch，“Worldsheet correlators in AdS $^ 3$ /CFT $^ 2$ ,” JHEP 0704 (2007) 050 [hep-th/0703001].   
[3] A. Dabholkar and A. Pakman，“Exact chiral ring of AdS3 / CFT $_ 2$ ,” Adv. Theor. Math.Phys.13(2009）409 [hep-th/0703022].   
[4] J. de Boer, J. Manschot,K. Papadodimas and E. Verlinde,“The Chiral ring of AdS3/CFT $_ 2$ and the attractor mechanism,” JHEP 0903(2009）030 [arXiv:0809.0507 [hep-th]].   
[5] M.R.Gaberdiel and R.Gopakumar,“Higher Spins & Strings,” JHEP 1411 (2014) 044 [arXiv:1406.6103 [hep-th]].   
[6] M. Ademollo et al.， “Dual String Models with Nonabelian Color and Flavor Symmetries,” Nucl. Phys.B 114(1976) 297.   
[7] T. Eguchi and A. Taormina, “Unitary Representations of $N = 4$ Superconformal Algebra,” Phys. Lett. B 196 (1987） 75.   
[8] T. Eguchi and A. Taormina,“Character Formulas for the $N = 4$ Superconformal Algebra,”Phys. Lett. B 200（1988) 315.   
[9] S. Gukov, E. Martinec, G. W. Moore and A. Strominger，“The Search for a holographic dual to $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ ,” Adv. Theor. Math. Phys. 9 (2005） 435 [hep-th/0403090].   
[10] D. Tong,“The holographic dual of $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ ,” JHEP 1404 (2014） 193 [arXiv:1402.5135 [hep-th]].   
[11] A. Sevrin, W. Troost and A. Van Proeyen,“Superconformal algebras in two-dimensions with N=4,” Phys. Lett.B 208 (1988) 447.   
[12] K. Schoutens,“O(n) extended superconformal field theory in superspace,” Nucl. Phys.B 295 (1988) 634.   
[13] P. Spindel, A. Sevrin,W. Troost and A. Van Proeyen，“Extended supersymmetric sigma models on group manifolds. 1. The complex structures,” Nucl. Phys. B 308 (1988) 662.   
[14] A. Van Proeyen, “Realizations of N=4 superconformal algebras on Wolf spaces," Class.Quant.Grav.6(1989) 1501.   
[15] A. Sevrin and G. Theodoridis,“N=4 superconformal coset theories,” Nucl. Phys. B 332 (1990) 380.   
[16] M. Gunaydin, J.L. Petersen,A. Taormina and A. Van Proeyen, “On the Unitary Representations of a Class of $N = 4$ Superconformal Algebras,” Nucl. Phys. B 322 (1989) 402.   
[17] J.L. Petersen and A. Taormina, “Characters of the $N = 4$ Superconformal Algebra With Two Central Extensions,” Nucl. Phys. B 331 (1990) 556.   
[18] J.L. Petersen and A. Taormina,“Characters of the $N = 4$ Superconformal Algebra With Two Central Extensions: 2. Massless Representations,” Nucl. Phys. B 333 (1990) 833.   
[19] J. de Boer,A. Pasquinucci and K. Skenderis,“AdS / CFT dualities involving large 2-D N=4 superconformal symmetry,” Adv. Theor. Math. Phys.3(1999) 577 [arXiv:hep-th/9904073].   
[20] S. Elitzur, O. Feinerman, A. Giveon and D. Tsabar, “String theory on （204号 $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ ,” Phys. Lett.B 449 (1999) 180 [hep-th/9811245].   
[21] J.M. Maldacena and H. Ooguri, “Strings in AdS(3) and SL(2,R) WZW model 1.: The Spectrum,” J.Math. Phys. 42 (2001) 2929 [hep-th/0001053].   
[22] S. Deger,A. Kaya, E. Sezgin and P. Sundell, “Spectrum of D = 6, N=4b supergravity on AdS in three-dimensions $\times ~ \mathrm { S ^ { 3 } }$ ,” Nucl. Phys. B 536 (1998) 110 [hep-th/9804166].   
[23] L. Eberhardt, M.R. Gaberdiel, R. Gopakumar and W. Li, in progress.   
[24] P. Di Vecchia,V.G. Knizhnik, J.L.Petersen and P. Rossi, “A Supersymmetric Wess-Zumino Lagrangian in Two-Dimensions,” Nucl. Phys. B 253 (1985） 701.   
[25] J.M. Evans, M.R. Gaberdiel and M.J. Perry,“The no ghost theorem for AdS3 and the stringy exclusion principle,” Nucl. Phys. B 535 (1998) 152 [hep-th/9806024].   
[26] A.Giveon,D. Kutasov and N. Seiberg,“Comments on string theory on AdS $^ 3$ ,” Adv. Theor.Math. Phys.2（1998) 733 [hep-th/9806194].   
[27] T. Ortin, “Gravity and strings,” Cambridge University Press (2004).   
[28] M. Baggio, O. Ohlson Sax,A. Sfondrini, B. Stefanski and A. Torielli, “Protected string spectrum in AdS $^ 3$ /CFT $_ 2$ from worldsheet integrability,” to appear.   
[29] S. Gukov, E. Martinec, G.W. Moore and A. Strominger,“An Index for 2-D field theories with large N = 4 superconformal symmetry,” hep-th/0404023.   
[30] M.R. Gaberdiel and R. Gopakumar,“Large ${ \mathcal { N } } = 4$ holography,” arXiv:1305.4181 [hep-th].   
[31] R. Argurio,A. Giveon and A. Shomer,“Superstrings on AdS(3) and symmetric products,” JHEP 0012（2000) 003 [hep-th/0009242].   
[32] M. Gunaydin, G. Sierra and P.K. Townsend, “The Unitary Supermultiplets of $d = 3$ （204号 Anti-de Sitter and $d = 2$ Conformal Superalgebras,” Nucl. Phys. B 274 (1986) 429.   
[33] L. Eberhardt, M. R. Gaberdiel and W. Li,“A holographic dual for string theory on （20 $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ ,” arXiv:1707.02705 [hep-th].