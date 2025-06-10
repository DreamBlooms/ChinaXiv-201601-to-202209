# A holographic dual for string theory on $\mathbf { A d S _ { 3 } } \times \mathbf { S ^ { 3 } } \times \mathbf { S ^ { 3 } } \times \mathbf { S ^ { 1 } }$

Lorenz Eberhardta，Matthias R.Gaberdielα and Wei Lib

a Institut fir Theoretische Physik, ETH Zurich, CH-8093 Zirich, Switzerland   
$b$ Institute of Theoretical Physics， Chinese Academy of Science 100190 Beijing,P.R. China

E-mail:eberhardtl@itp.phys.ethz.ch， gaberdiel@itp.phys.ethz.ch， weili@itp.ac.cn

ABSTRACT: The CFT dual of string theory on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ is conjectured to be the symmetric orbifold of the $S _ { \kappa }$ theory， provided that one of the two $Q _ { 5 } ^ { \pm }$ quantum numbers is a multiple of the other. We determine the BPS spectrum of the symmetric orbifold in detail， and show that it reproduces precisely the BPS spectrum that was recently calculated in supergravity. We also determine the BPS spectrum of the world-sheet theory that is formulated in terms of WZW models, and show that,apart from some gaps (which are reminiscent of those that appear in the corresponding $\mathbb { T } ^ { 4 }$ calculation)，it also reproduces this BPS spectrum. In fact，the matching seems to work as well as for the familiar $\mathbb { T } ^ { 4 }$ case,and thus our results give strong support for this proposal.

# Contents

1Introduction 1

2Strings on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ 4

2.1 （20 ${ \mathrm { D } } 5 ^ { + }$ brane with $\mathrm { D 5 ^ { - } }$ flux 4   
2.2 The instanton moduli space 5   
2.3 The case $Q _ { 5 } ^ { + } = 1$ （20 7   
2.4 The case $Q _ { 5 } ^ { + } > 1$ （204号 8

# 3BPS spectrum of symmetric orbifold of $S _ { \kappa }$ 9

3.1 BPS spectrum of $S _ { \kappa }$ 10   
3.2 Untwisted sector 11   
3.3 Twisted sectors 11   
3.3.1Odd twist 11   
3.3.2Even twist 14   
3.4 Recasting and summary of the spectrum 15

# 4BPS spectrum in string theory and supergravity 16

4.1 Supergravity 16   
4.2 World-sheet analysis 17   
4.3 Review: full perturbative BPS spectrum for $\mathrm { A d S _ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { T ^ { 4 } }$ 17   
4.4 The full perturbative BPS spectrum for $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ 19   
4.4.1 R-sector 19   
4.4.2NS sector 21   
4.4.3 Full perturbative BPS spectrum 22

# 5Comparison between symmetric orbifold and world-sheet 23

5.1 BPS spectrum 23   
5.2 The chiral ring 24   
5.3 An effective $\mathbb { T } ^ { 2 }$ description 25

6Discussion and outlook 26

A Thelarge ${ \mathcal N } = 4$ algebra and its BPS bound 27

A.1 The BPS Bound 28   
A.2 The ${ \mathcal N } = 2$ subalgebra 29

B Superconformal affine algebras 29

B.1 Spectral flow automorphism 29

C $S _ { \kappa }$ theory and its chiral algebra 30   
D Character derivation of the twisted sector spectrum 31   
D.1 Odd twist 32   
D.2 Even twist 32

E BPS states in the spectrally flowed NS sectors 33

F Non-renormalization of the chiral ring 35

# 1Introduction

The AdS $_ 3$ /CFT $^ 2$ duality provides some unique insights into the AdS/CFT correspondence, mainly because of the powerful CFT techniques that are available in two dimensions. Indeed, the CFT dual of string theory on A $\mathrm { 1 S _ { 3 } \times S ^ { 3 } \times \mathcal { M } _ { 4 } }$ ，where $\mathcal { M } _ { 4 }$ （204号 is a 4D hyper-Kähler manifold (i.e. $ { \mathbb { T } } ^ { 4 }$ or K3)， is one of the first explicitly known AdS/CFT dualities constructed from string theory. On the gravity side, the background arises from the near horizon limit of $Q _ { 1 }$ D1 branes smeared in $Q _ { 5 }$ coincident D5 branes that wrap $\mathcal { M }$ . The dual CFT is then realized as the decoupling limit of the world-volume theory of the D1-D5 system, i.e. as a sigma model on the moduli space of $Q _ { 1 }$ instanton in the $\mathrm { U } ( Q _ { 5 } )$ gauge theory living on $\mathcal { M } _ { 4 }$ ：

As a consequence, the dual CFT lies on the same moduli space as the $Q _ { 1 } Q _ { 5 }$ -fold symmetric orbifold of $\mathcal { M } _ { 4 }$ ，which is essentially a free theory (at least for the case of $\mathbb { T } ^ { 4 }$ ). Together with the large amount of supersymmetry (described by the small ${ \mathcal N } = 4$ superconformal algebra) this allows many aspects of the duality to be checked and matched explicitly, see e.g. [1] for a review. In particular, the BPS spectrum on both sides agrees, as do the three-point functions [2, 3]. Finally, for the case of K3, the matching of the elliptic genus provides further non-trivial evidence [4].

For both $\mathbb { T } ^ { 4 }$ and K3, the dual CFT has small $\mathcal { N } ~ = ~ 4$ superconformal symmetry. Replacing the hyperkähler manifold $\mathcal { M } _ { 4 }$ by $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ (which is the smallest “hyperkahler manifold with torsion"),one obtains a close cousin to the above setup, i.e. string theory on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ . The dual CFT dual is then expected to have large ${ \mathcal N } = 4$ superconformal symmetry [5-7].

Despite its apparent similarity to the familiar $ { \mathbb { T } } ^ { 4 }$ or K3 case, the CFT dual of string theory on AdS $_ 3 \times$ S $^ 3 \times$ S $^ 3 \times$ S $^ { 1 }$ has proven much more difficult to find. This might be surprising at first sight, given that this background has slightly larger symmetry than the small $\mathcal { N } = 4$ algebra supported by the $ { \mathbb { T } } ^ { 4 }$ or K3 case. For example, the CFT dual of the $\mathcal { N } = 4$ Vasiliev higher-spin theory was actually first identified for the $\mathrm { A d S _ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 1 } }$ background and shown to be a relatively simple (Wolf) coset

CFT [8], while the identification for the $ { \mathbb { T } } ^ { 4 }$ or K3 case was only subsequently found as a limiting case [9, 10].

One reason why finding the stringy CFT dual of $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ has turned out to be difficult, is that the corresponding brane constructions are rather nontrivial. A simple D1-D5 system suffces for the $ { \mathbb { T } } ^ { 4 }$ or K3 case, and the large U-duality symmetry of the system allows one to show that the CFT dual can only depend on the the product $N = Q _ { 1 } Q _ { 5 }$ [11]. For the $\mathrm { A d S _ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 1 } }$ case, on the other hand, there are,in addition to the $Q _ { 1 }$ quantum number, two different $Q _ { 5 } ^ { \pm }$ quantum numbers (corresponding to the sizes of the two $\mathrm { S ^ { 3 } }$ 's). We then either need two different kinds of D5 branes, or we must realize one set of charges in terms of some non-trivial flux. In either case,the description of the moduli space of instantons is much more complicated. Furthermore, the U-duality group is much smaller in this case, as was emphasized already in [7]; in particular, one should therefore not expect the answer to depend just on some simple combinations of the different brane charges.

The other main diffculty for finding the CFT dual had to do with the structure of the BPS bounds for the large $\mathcal { N } = 4$ superconformal algebra $A _ { \gamma }$ ， and its relation to the BPS bound of the corresponding supergravity algebra $D ( 2 , 1 | \alpha )$ . In particular, as was stressed in [6, 7], the BPS bound for $A _ { \gamma }$ is in general stronger than that for $D ( 2 , 1 | \alpha )$ ， with the bound only coinciding for those BPS states whose spins with respect to the two $\mathfrak { s u } ( 2 )$ algebras (corresponding to the two $\mathrm { S ^ { 3 } }$ 's)agree. Compounding the problem, it was long believed [6] that the supergravity theory had lots of BPS states, including many states whose spins with respect to the two $\mathfrak { s u } ( 2 )$ algebra do not agree - and that need to acquire a magical amount of quantum correction in order to just satisfy the $A _ { \gamma }$ BPS bound. Furthermore, none of proposed CFT duals had a corresponding BPS spectrum, even for some special choice of charges [7].

Recently, this problem was revisited in [12], where it was found that there are no troublesome BPS states (i.e. states whose $\mathfrak { s u } ( 2 )$ -spins do not agree) in supergravity. Indeed, motivated by the suggestive results of a world-sheet analysis, we performed a first principle supergravity calculation [12], and found that the only BPS states that appear in supergravity have the property that their $\mathfrak { s u } ( 2 )$ spins agree - in the old analysis of [6], the BPS spectrum of supergravity had only been guessed based on group theoretical methods. Furthermore, all the states of supergravity satisfy also the $A _ { \gamma }$ BPS bound — in fact, this is also true for the non-BPS states in supergravity whose spins difer - and hence there is no need for any miraculous quantum correction.

With this roadblock removed, we return in this paper to the search for the CFT dual of string theory on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ . The dual CFT will be motivated by largely the same methods as those used for the small $\mathcal { N } = 4$ case, i.e. we start with a D-brane construction and invoke open/closed duality. (Proposals of this form were already discussed before, in particular in [7], see also [5], but they were discarded because of their failure to reproduce the ‘old' BPS spectrum of supergravity as incorrectly predicted in [6].） The most promising brane construction appears to be the one where we consider $Q _ { 5 } ^ { + }$ D5 branes wrapping S $^ { 1 3 } \times \mathrm { S ^ { 1 } }$ ，where $\mathrm { S ^ { 3 } }$ is the special Lagrangian sub-manifold, supported by $Q _ { 5 } ^ { - }$ units of flux, that is wrapped by the $Q _ { 5 } ^ { + }$ D5-branes — this is the “third” construction proposed by [7]. In addition， we add an arbitrary number of $Q _ { 1 }$ branes smeared on the D5 brane. We argue that the dual CFT is then the symmetric orbifold of $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ , where the flux through the $\mathrm { S ^ { 3 } }$ turns out to be $( Q _ { 5 } ^ { - } / Q _ { 5 } ^ { + } ) - 1$ . This can be fairly directly understood for the case when $Q _ { 5 } ^ { + } = 1$ since we can then give a direct description of the instanton moduli space; the result for $Q _ { 5 } ^ { + } > 1$ is somewhat more conjectural. Since the flux has to be quantized, the proposal only makes sense if $Q _ { 5 } ^ { + }$ is a factor of $Q _ { 5 } ^ { - }$ .We also give a microscopic argument (based on anomaly considerations, following [13]） for where this condition may come from.

We then subject this proposal to some consistency checks. In particular， we show that the BPS spectra match from both sides. This requires us to determine the BPS spectrum of the symmetric orbifold of $S _ { \kappa }$ in detail, completing the analysis of [7]. We also compute the full perturbative BPS spectrum from the worldsheet perspective; in particular, we work out the contribution from the spectrally flowed sectors, extending the analysis of [12] where only the unflowed sector was analysed. As it turns out, this analysis is quite intricate and the resulting BPS spectrum has the same qualitative structure (including some gaps, see the discussion in [11]) as for the familiar case of $ { \mathbb { T } } ^ { 4 }$ and K3.

This paper is organized as follows. In Section 2 we discuss various brane scenarios and discuss their implications on the dual CFT. For the case where only one class of D5-branes is present，we can read off an explicit realization of the dual CFT from this picture as the symmetric orbifold of the $S _ { \kappa }$ [7,14] theory. This is only directly possible for $Q _ { 5 } ^ { + } = 1$ ， but we also speculate how the construction should be generalized to $Q _ { 5 } ^ { + } > 1$ in Section 2.4. Finally, Appendix C is then devoted to reviewing this theory.

Section 3 contains the calculation of the BPS spectrum of the proposed dual - the symmetric orbifold of $S _ { \kappa }$ . This is done carefully and in detail, since there are a number of subtleties (depending on whether the twist of the twisted sector is even or odd, see Sections 3.3.2 and 3.3.1, respectively) that have to be taken into account. Some of the more technical arguments are explained in Appendix D,but the main result is simple and spelled out in (3.2).

The next section is concerned with explaining the BPS spectrum of string theory and supergravity on the background $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ . Section 4.1 reviews the supergravity calculation of [12]， Section 4.2 the corresponding worldsheet calculation. Section 4.3 clarifies some issues relating to the missing chiral primaries in the case of $ { \mathbb { T } } ^ { 4 }$ ， while Section 4.4 finally discusses the full perturbative BPS spectrum of string theory, described by (4.31). (Some technical derivations are described in Appendix E.)

Section 5 makes some comparisons between the two sides of the duality. First and foremost， we concentrate on the BPS spectrum (Section 5.1), but we offer also some further tests by employing the chiral ring (Section 5.2) of an ${ \mathcal N } = 2$ subalgebra of the large ${ \mathcal N } = 4$ algebra. We also explain how our proposal leads to the symmetric orbifold of $ { \mathbb { T } } ^ { 4 }$ in the infinite radius limit of one of the two three-spheres. Finally, we conclude in Section 6. For the convenience of the reader we have also reviewed some of the algebras that appear in Appendices A and B. Furthermore,we have included the derivation of a non-renormalization theorem we have used in the main text in Appendix F.

# 2 Strings on $\mathbf { A d S _ { 3 } } \times \mathbf { S ^ { 3 } } \times \mathbf { S ^ { 3 } } \times \mathbf { S ^ { 1 } }$

In this section we discuss a brane configuration whose near horizon limit gives rise to $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ . Since it is engineered from string theory, we can read off from it various aspects of the holographic dual. It also guarantees that the duality is consistent non-perturbatively.

# 2.1 （20 ${ \bf D 5 ^ { + } }$ brane with $\mathbf { D 5 ^ { - } }$ flux

For generic values of the background charges, [7] proposed two brane configurations which reproduce different aspects of the geometry. In the following we shall concentrate on the one that is more similar to the cases involving $\mathbb { T } ^ { 4 }$ or K3, and that gives rise to a natural proposal for the dual CFT. To preserve the right amount of supersymmetry, we consider $Q _ { 5 } ^ { + }$ D5-branes wrapping $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ ，where the $\mathrm { S ^ { 3 } }$ is a special Lagrangian sub-manifold of the six-dimensional D5 world-volume, which is supported by the flux $Q _ { 5 } ^ { - }$ . This construction breaks explicitly the symmetry between $Q _ { 5 } ^ { + }$ and $Q _ { 5 } ^ { - }$ . We will adopt the convention that the $\mathrm { S ^ { 3 } }$ is located in the directions 678,the ${ \mathrm { S } } ^ { 1 }$ in the direction 9,i.e. that the brane configuration is

$$
\begin{array} { r l r l r l r l r l r l } & { \mathrm { ~  ~ { \mathcal ~ { ~ O ~ } } ~ } } & { 1 } & { 2 } & { 3 } & { 4 } & { 5 } & { 6 } & { 7 } & { 8 } & { 9 } \\ & { Q _ { 5 } ^ { + } \mathrm { ~ D 5 ~ b r a n e s } } & { \times } & { } & { } & { \times } & { \times } & { \times } & { \times } & { \times } \\ & { Q _ { 1 } \mathrm { ~ D 1 ~ b r a n e s } } & { \times } & { } & { } & { \times } & { \sim } & { \sim } & { \sim } \\ & { Q _ { 5 } ^ { - } \mathrm { ~ D 5 ~ f l u x e s } } & { } & { } & { } & { \mathrm { ~ o ~ } } & { \circ } & { \circ } \end{array}
$$

where $\times$ denotes the directions in which the brane extends, $\sim$ the directions along which the brane is smeared,and $\bigcirc$ denotes fluxes. The corresponding supergravity was analysed in [15-18]. In particular, the brane configuration gives the near-horizon geometry $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ .1

The resulting gauge theory on the D5 world-volume has ${ \mathcal N } = 2$ supersymmetry, and the three-dimensional low-energy limit is an ${ \mathcal N } = 2$ Chern-Simons theory with level $Q _ { 5 } ^ { - }$ living on the directions O59. The bosonic level is however shifted by integrating out the fermions; because of ${ \mathcal N } = 2$ SUSY, this shift is twice as large as the one given in [13], so we get a Chern-Simons theory with gauge group $\mathrm { U } ( Q _ { 5 } ^ { + } )$ and level $Q _ { 5 } ^ { - } - Q _ { 5 } ^ { + }$ , see also [7]. It was also argued in [13] that supersymmetry is broken for $Q _ { 5 } ^ { + } > Q _ { 5 } ^ { - }$ , thus we restrict in the following to the case $Q _ { 5 } ^ { + } \leq Q _ { 5 } ^ { - }$ ； the opposite case can be treated similarly by interchanging the roles of $Q _ { 5 } ^ { + }$ and $Q _ { 5 } ^ { - }$ 2．

Before we proceed further we should stress that there is one crucial difference of our setup relative to the case of $ { \mathbb { T } } ^ { 4 }$ .For $ { \mathbb { T } } ^ { 4 }$ we can use four T-dualities in the directions 6789 to arrive again at the same brane configuration, but with the D5- brane charge $Q _ { 5 }$ and the D1-brane charge $Q _ { 1 }$ interchanged. This implies that the dual CFT should be symmetric under interchange of $Q _ { 1 }$ and $Q _ { 5 }$ ，a constraint which is obviously satisfied by the $Q _ { 1 } Q _ { 5 }$ -fold symmetric product of $\mathbb { T } ^ { 4 }$ . Importantly, this Tduality is no longer available for $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ and so the dual CFT should not be expected to be symmetric in any permutation of $Q _ { 1 }$ ， $Q _ { 5 } ^ { + }$ and $Q _ { 5 } ^ { - }$ . In fact, the dual CFT is expected to have large ${ \mathcal N } = 4$ superconformal symmetry with levels $( Q _ { 1 } Q _ { 5 } ^ { + } , Q _ { 1 } Q _ { 5 } ^ { - } )$ （20 [5-7]— for a brief review of this superconformal algebra see Appendix A - and central charge

$$
c = 6 Q _ { 1 } \frac { Q _ { 5 } ^ { + } Q _ { 5 } ^ { - } } { Q _ { 5 } ^ { + } + Q _ { 5 } ^ { - } } .
$$

In particular, this formula does not exhibit any permutation symmetry (except for the obvious $Q _ { 5 } ^ { + }  Q _ { 5 } ^ { - }$ exchange symmetry).

# 2.2 The instanton moduli space

Given that the brane construction of the previous section gives rise to a gauge theory living on the D5 world-volume, we can now follow the usual logic of the AdS/CFT correspondence [22],and identify the dual CFT with the $1 + 1$ -dimensional lowenergy theory living on the intersection of the D1- and D5-brane. In particular, the D1-branes can be viewed as instantons in the D5-brane theory [23], living on the transverse direction of the D1-branes in the D5-branes, i.e. on $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ . Low energy fluctuations are described by fluctuations in this moduli space, and thus we can formally identify the dual CFT with the supersymmetric $\sigma$ -model on the moduli space $\mathcal { M } _ { Q _ { 1 } , Q _ { 5 } ^ { + } , Q _ { 5 } ^ { - } }$ d $Q _ { 1 }$ instantons of $\mathrm { S U } ( Q _ { 5 } ^ { + } )$ on S-Q+ X S1. Here, we have decoupled the overall $\mathrm { U } ( 1 )$ as usual. The dimension of this moduli space is

$$
\dim ( { \mathcal M } _ { Q _ { 1 } , Q _ { 5 } ^ { + } , Q _ { 5 } ^ { - } } ) = 4 Q _ { 1 } Q _ { 5 } ^ { + } \ ,
$$

as follows from essentially the same argument as for $ { \mathbb { T } } ^ { 4 }$ or K3.Indeed, the dimension can be written as twice the absolute value of the index of a Dirac fermion in the adjoint representation. We can then use the Atiyah-Singer Index theorem

$$
\dim ( { \mathcal { M } } _ { Q _ { 1 } , Q _ { 5 } ^ { + } , Q _ { 5 } ^ { - } } ) = 2 \left| { \mathrm { i n d } } ( \nabla _ { \mathbf { a d j } } ) \right| = 2 \left| \int _ { { \mathrm { S } } ^ { 3 } \times { \mathrm { S } } ^ { 1 } } { \mathrm { t r } } _ { \mathbf { a d j } } ( e ^ { i F } ) { \widehat { A } } ( R ) \right| ~ ,
$$

where $F$ is the feld strength and $R$ the Riemann curvature of an arbitrary metric on （20 $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ ，while $\widehat { A } ( R )$ is the corresponding Dirac genus. The main point now is that $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ is a Lie group: as a consequence, its tangent bundle is parallelizable, and all characteristic classes of the tangent bundle vanish, from which we deduce that （20 $\widehat { A } ( R ) = 1$ in cohomology. Thus the expression reduces to the usual one

$$
\begin{array} { l } { { \displaystyle \dim ( { \mathcal M } _ { Q _ { 1 } , Q _ { 5 } ^ { + } , Q _ { 5 } ^ { - } } ) = 2 \left| \int _ { { \mathbb S } ^ { 3 } \times { \mathbb S } ^ { 1 } } \mathrm { t r } _ { { \bf a d j } } ( e ^ { i F } ) \right| = 2 \left| p _ { 1 } ( F _ { { \bf a d j } } ) [ { \mathbb S } ^ { 3 } \times { \mathbb S } ^ { 1 } ] \right| } } \\ { { \displaystyle \qquad = 4 Q _ { 5 } ^ { + } \left| p _ { 1 } ( F _ { \bf f } ) [ { \mathbb S } ^ { 3 } \times { \mathbb S } ^ { 1 } ] \right| = 4 | Q _ { 1 } | Q _ { 5 } ^ { + } ~ } , } \end{array}
$$

where we have used the fact that the Dynkin index of the adjoint representation is $Q _ { 5 } ^ { + }$ , whereas in the fundamental representation it reads $\textstyle { \frac { 1 } { 2 } }$ . Moreover, we have inserted the definition of the instanton number as the first Pontyagin class in the fundamental representation. In the following we shall always assume $Q _ { 1 } \geq 0$ ,i.e. that there are no anti-instantons. We should also mention that since the first Pontryagin class of the tangent bundle of $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ vanishes, the D5-branes do not induce an effective D1-charge [24]. Thus the identifications of $Q _ { 1 }$ and $Q _ { 5 } ^ { + }$ made above do not receive corrections.

This moduli space was considered before in the special case $Q _ { 5 } ^ { + } = 2$ by mathematicians [25]. It inherits many nice geometric properties from the underlying manifold $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ . Indeed, the Hopf surface $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ is a hypercomplex manifold, with Hodge diamond

$$
\begin{array} { c c c c c c } { { } } & { { } } & { { } } & { { 1 } } & { { } } & { { } } \\ { { } } & { { 0 } } & { { } } & { { 1 } } & { { } } & { { } } \\ { { 0 } } & { { } } & { { 0 } } & { { } } & { { 0 } } & { { . } } \\ { { } } & { { 1 } } & { { } } & { { 0 } } & { { } } & { { } } \\ { { } } & { { } } & { { 1 } } & { { } } & { { } } & { { } } \end{array}
$$

It is moreover “hyperkahler with torsion” (HKT),and supports a $( 4 , 4 )$ -structure as described in [26]. As a consequence, the moduli space also supports a HKT and a $( 4 , 4 )$ -structure.’ According to [6], see also [27], this is the geometric requirement that the $\sigma$ -model admits classically a large $\mathcal { N } = 4$ superconformal symmetry. This gives a consistency check of the identification of the dual CFT with the supersymmetric $\sigma$ -model on $\mathcal { M } _ { Q _ { 1 } , Q _ { 5 } ^ { + } , Q _ { 5 } ^ { - } }$ .Furthermore, the Hopf surface $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ along with its secondary versions, which are discrete quotients of it,are the only four-dimensional HKT manifolds.

# 2.3 The case $Q _ { 5 } ^ { + } = \bf { 1 }$

Let us first focus on the case $Q _ { 5 } ^ { + } = 1$ , for which an explicit description of the moduli space is available. To start with we consider the special case where in addition $Q _ { 1 } = 1$ . Then the moduli space is four dimensional,and since every moduli space of instantons contains the base-manifold as a factor (describing the position of the instanton)， and since this has already the right dimension from (2.3)， we conclude that in this case

$$
\mathcal { M } _ { 1 , 1 , Q _ { 5 } ^ { - } } \cong \mathrm { S } _ { Q _ { 5 } ^ { - } - 1 } ^ { 3 } \times \mathrm { S } ^ { 1 } ~ .
$$

For general $Q _ { 1 }$ , the moduli space contains the position of all $Q _ { 1 }$ instantons and hence is naturally identified with the symmetric orbifold [28]

$$
\mathcal { M } _ { Q _ { 1 } , 1 , Q _ { 5 } ^ { - } } \cong \mathrm { S y m } ^ { Q _ { 1 } } ( \mathrm { S } _ { Q _ { 5 } ^ { - } - 1 } ^ { 3 } \times \mathrm { S } ^ { 1 } ) ~ ,
$$

where $\mathrm { S y m } ^ { N } ( \mathcal { M } ) \equiv \mathcal { M } ^ { \otimes N } / S _ { N }$ .Since both $\mathrm { S ^ { 3 } }$ and $\mathrm { S ^ { 1 } }$ are group manifolds, the relevant conformal field theory should simply be the WZW model associated to

$$
S _ { \kappa } \ : \qquad \mathfrak { s u ( 2 ) } _ { \kappa + 2 } ^ { ( 1 ) } \oplus \mathfrak { u ( 1 ) } ^ { ( 1 ) } \ ,
$$

where the superscripts ‘ $^ { \circ } ( 1 ) ^ { \prime \prime }$ indicate that these are the ${ \mathcal N } = 1$ superconformal affine algebras, and $\kappa$ is to be identified with $\kappa = Q _ { 5 } ^ { - } - 1$ . (As explained in Appendix B, the decoupled bosonic $\mathfrak { s u } ( 2 )$ algebra of $\mathfrak { s u } ( 2 ) _ { \kappa + 2 } ^ { ( 1 ) }$ has level $\kappa$ ,and thisshould be identified with the flux $Q _ { 5 } ^ { - } - 1$ .） This CFT，which was denoted by $S _ { \kappa }$ in [7],will play an important role for the rest of the paper,and we have therefore reviewed its salient features in Appendix C. In particular, the $S _ { \kappa }$ theory supports a large ${ \mathcal N } = 4$ algebra with levels $( Q _ { 5 } ^ { + } , Q _ { 5 } ^ { - } ) = ( 1 , Q _ { 5 } ^ { - } )$ [14, 29].

By the same arguments as for the familiar $ { \mathbb { T } } ^ { 4 }$ (or K3） case, these considerations then suggest that the CFT dual of string theory on . $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ with $Q _ { 5 } ^ { + } = 1$ （20 is on the moduli space of the symmetric orbifold

$$
\mathrm { S y m } ^ { Q _ { 1 } } ( S _ { \kappa } ) \ , \qquad \mathrm { w i t h } \ \kappa = Q _ { 5 } ^ { - } - 1 .
$$

This symmetric orbifold has a large $\mathcal { N } = 4$ superconformal symmetry with levels $( Q _ { 1 } , Q _ { 1 } Q _ { 5 } ^ { - } )$ , in agreement with the expectations from supergravity, see the discussion around eq. (2.2).

# 2.4 The case $Q _ { 5 } ^ { + } > 1$

For $Q _ { 5 } ^ { + } > 1$ the identification of the moduli space of instantons is more complicated, and thus the following is somewhat more speculative. In addition, there is a potential subtlety with the world-volume theory. Recall that the low energy effective action of the world-volume theory on the D5-branes includes a Chern-Simons theory with gauge group $\mathrm { U } ( Q _ { 5 } ^ { + } )$ and level $Q _ { 5 } ^ { - } - Q _ { 5 } ^ { + }$ . When going to the near-horizon limit of the geometry, the overall $\mathrm { U } ( 1 )$ is decoupled. There is then the very subtle issue of whether we end up with a $\mathrm { S U } ( Q _ { 5 } ^ { + } )$ or a $\mathrm { S U } ( Q _ { 5 } ^ { + } ) / \mathbb { Z } _ { Q _ { 5 } ^ { + } }$ gauge theory in the end. In the case of $\mathrm { A d S } _ { 5 } \times \mathrm { S } ^ { 5 }$ , it was shown that the center of the group can be spontaneously broken [30]. It thus seems natural that also S $\mathrm { U } ( Q _ { 5 } ^ { + } ) / \mathbb { Z } _ { Q _ { 5 } ^ { + } }$ Chern-Simons theory with level $Q _ { 5 } ^ { - } - Q _ { 5 } ^ { + }$ should be consistent.

On the other hand, it was argued in [13] that this theory is anomalous unless $Q _ { 5 } ^ { + }$ divides $Q _ { 5 } ^ { - }$ . (Again, one has to make a careful translation of conventions to this paper, since it is formulated in $\mathcal { N } = 1$ language.） We are thus led to conclude that the brane scenario we have engineered is only consistent if $Q _ { 5 } ^ { + }$ divides $Q _ { 5 } ^ { - }$ and thus yields also only a prediction on the dual CFT in this case.4 This requirement was of course trivially satisfied for $Q _ { 5 } ^ { + } = 1$ ：

Obviously, the moduli space of instantons becomes very complicated in the general case, but it still tells us that the dual CFT should be a supersymmetric $\sigma$ -model on a $4 Q _ { 1 } Q _ { 5 } ^ { + }$ -dimensional HKT space. There is one very natural candidate,which fulfills all the requirements, namely the symmetric orbifold

$$
\mathrm { S y m } ^ { Q _ { 1 } Q _ { 5 } ^ { + } } ( \mathrm { S } _ { Q _ { 5 } ^ { - } / Q _ { 5 } ^ { + } - 1 } ^ { 3 } \times \mathrm { S } ^ { 1 } ) = \mathrm { S y m } ^ { Q _ { 1 } Q _ { 5 } ^ { + } } ( { \cal S } _ { \kappa } ) \qquad \mathrm { w i t h } \quad \kappa = \frac { Q _ { 5 } ^ { - } } { Q _ { 5 } ^ { + } } - 1 \ .
$$

This CFT is only unitary if $Q _ { 5 } ^ { - }$ is divisible by $Q _ { 5 } ^ { + }$ ， since otherwise the WZW-level would not be an integer. This condition is in accordance with the above argument of the brane picture being anomalous.

We hence propose that (2.12) lies on the same moduli space as string theory on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ with $Q _ { 5 } ^ { - } / Q _ { 5 } ^ { + } \ \in \ \mathbb { Z }$ . This proposal generalizes (2.11)， to which it reduces for $Q _ { 5 } ^ { + } = 1$ . The opposite case $Q _ { 5 } ^ { + } / Q _ { 5 } ^ { - } \in \mathbb { Z }$ can again be treated by interchanging the roles of $Q _ { 5 } ^ { + }$ and $Q _ { 5 } ^ { - }$ .Since $S _ { \kappa }$ supports the large $\mathcal { N } ~ = ~ 4$ algebra with levels $( 1 , \kappa )$ ， see Appendix C, the symmetric orbifold (2.12） has levels $( Q _ { 1 } Q _ { 5 } ^ { + } , Q _ { 1 } Q _ { 5 } ^ { - } )$ , and central charge, see eq. (C.4),

$$
c = 6 Q _ { 1 } Q _ { 5 } ^ { + } \frac { Q _ { 5 } ^ { - } } { Q _ { 5 } ^ { + } } \frac { 1 } { \frac { Q _ { 5 } ^ { - } } { Q _ { 5 } ^ { + } } + 1 } = \frac { 6 Q _ { 1 } Q _ { 5 } ^ { + } Q _ { 5 } ^ { - } } { Q _ { 5 } ^ { + } + Q _ { 5 } ^ { - } } \ ,
$$

in agreement with the supergravity expectation [7], see eq. (2.2)

We should also mention that this proposal generalizes the one given in [5, 31] for the case of $Q _ { 5 } ^ { + } ~ = ~ Q _ { 5 } ^ { - }$ ，where it was argued that the dual CFT lies on the same moduli space as the symmetric orbifold of $S _ { 0 }$ . Note that in this case the condition $Q _ { 5 } ^ { + } / Q _ { 5 } ^ { - } \ \in \ \mathbb { Z }$ is automatic. We should also mention that the proposal only depends on the products $Q _ { 1 } Q _ { 5 } ^ { + }$ and $Q _ { 1 } Q _ { 5 } ^ { - }$ .This is not directly in conflict with the missing T-duality of the theory， since the theory is not symmetric in any permutation of the three D-brane charges. However， it implies that there should be some not yet uncovered duality of the bulk theory which acts by rescaling $( Q _ { 1 } , Q _ { 5 } ^ { + } , Q _ { 5 } ^ { - } )  ( m Q _ { 1 } , Q _ { 5 } ^ { + } / m , Q _ { 5 } ^ { - } / m )$ . It would be very interesting to see this directly.

Finally, there is yet another consistency condition: for $Q _ { 5 } ^ { - } \to \infty$ , the size of the ${ \mathrm { S } } ^ { 3 }$ in $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ tends to infinity, and as in [9], one should expect to make contact with the CFT dual of string theory on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times \mathbb { T } ^ { 4 } }$ .(Strictly speaking, this should only hold for the zero-momentum sector,but this includes in particular the chiral algebra.） Since $S _ { \kappa }$ becomes $ { \mathbb { T } } ^ { 4 }$ ， i.e. the theory of 4 free bosons and fermions, for $\kappa  \infty$ , it follows that

$$
\mathrm { S y m } ^ { Q _ { 1 } Q _ { 5 } ^ { + } } ( \mathrm { S } _ { Q _ { 5 } ^ { - } / Q _ { 5 } ^ { + } - 1 } ^ { 3 } \times \mathrm { S } ^ { 1 } ) \stackrel { Q _ { 5 } ^ { - } \to \infty } { \longrightarrow } \mathrm { S y m } ^ { Q _ { 1 } Q _ { 5 } ^ { + } } ( \mathbb { T } ^ { 4 } ) ~ .
$$

This provides a very non-trivial test of the proposal; in fact, this requirement seems hard to satisfy with any other candidate.

Since the brane scenario only works for $Q _ { 5 } ^ { - }$ a multiple of $Q _ { 5 } ^ { + }$ , this indicates that the dual CFT will be much more complicated in the other cases and not simply given by a symmetric product orbifold. It remains open whether anything more concrete can be said about the dual theories in this case.

# 3 BPS spectrum of symmetric orbifold of $\scriptstyle { S _ { \kappa } }$

As a first check of our proposal we should compare the BPS spectrum of the two theories. In this section, we compute the BPS spectrum of the CFT dual, the $N$ -fold symmetric orbifold of $S _ { \kappa }$ ，where

$$
N = Q _ { 1 } Q _ { 5 } ^ { + } \qquad \mathrm { a n d } \qquad \kappa = { \frac { Q _ { 5 } ^ { - } } { Q _ { 5 } ^ { + } } } - 1 \ .
$$

This was already partially done in [7], but we shall be more explicit below, and, as will become apparent, the situation is somewhat more complicated than outlined there. We shall only concentrate on the BPS spectrum from the single-cycle twist sectors of the symmetric orbifold — these correspond to the single-particle states in AdS.

This spectrum is to be compared with the predictions coming from the worldsheet theory in string theory (with pure NS-NS flux), as well as supergravity, using the results of [12]. For this comparison only the low-lying BPS states (whose conformal dimension does not scale with $N = Q _ { 1 } Q _ { 5 } ^ { + }$ ） play a role,and we shall therefore also concentrate on these BPS states in our analysis of the symmetric orbifold.

While the detailed analysis is quite complicated - it will be described in the rest of this section - the result is simple: the low-lying single-cycle BPS states of the symmetric orbifold are given by

$$
\bigoplus _ { j = 0 } ^ { \frac { c } { 1 2 } } \left[ j , j , u = 0 \right] _ { S } \otimes \overline { { { \left[ j , j , u = 0 \right] } } } _ { S } \ ,
$$

where $c$ is the total central charge of the symmetric orbifold. Here and in the following $[ j ^ { + } , j ^ { - } , u ] _ { S }$ denotes a BPS representation of the large ${ \mathcal N } = 4$ algebra with $\mathfrak { s u } ( 2 )$ -spins （20 $j ^ { + }$ and $j ^ { - }$ and $\mathfrak { u } ( 1 )$ -charge $u$ , see [12] and Appendix A.1 for our conventions.

# 3.1 BPS spectrum of $\scriptstyle { \mathcal { S } } _ { \kappa }$

First, we summarize the BPS spectrum of a single $S _ { \kappa }$ theory. Representations of the （204号 ${ \mathcal N } = 4$ algebra are labelled by $( h , j ^ { + } , j ^ { - } , u )$ ， see e.g. [8, 29]. The BPS bound for the large $\mathcal { N } = 4$ algebra of such a representation is given by, see eq. (A.13)

$$
h _ { \mathrm { B P S } } ( j ^ { + } , j ^ { - } , u ) = \frac { k ^ { + } j ^ { - } + k ^ { - } j ^ { + } + ( j ^ { + } - j ^ { - } ) ^ { 2 } + u ^ { 2 } } { k ^ { + } + k ^ { - } } ,
$$

where $k ^ { + }$ and $k ^ { - }$ are the levels of the algebra. Importantly, the last two terms in the numerator are suppressed for $k ^ { \pm }$ large,so they are invisible in the limit in which both levels become large — recal that for the symmetric orbifold, the relevant levels are $k ^ { \pm } = Q _ { 1 } Q _ { 5 } ^ { \pm }$ ， and hence this will be the case for large $Q _ { 1 }$ ：

In the case of $S _ { \kappa }$ ， the representations are labelled by $j ^ { - } ~ = ~ 0 , \frac { 1 } { 2 } , \ldots , \frac { 1 } { 2 } \kappa$ and $j ^ { + } = 0$ , and hence satisfy the unitarity bound for representations of the large $\mathcal { N } = 4$ algebra [29]. Furthermore, $u$ can take any value, and the conformal weight of the corresponding representation is

$$
h = \frac { j ^ { - } ( j ^ { - } + 1 ) } { \kappa + 2 } + \frac { u ^ { 2 } } { \kappa + 2 } = h _ { \mathrm { B P S } } ( 0 , j ^ { - } , u ) \ .
$$

Here we have normalized the $\mathfrak { u } ( 1 )$ -current in the canonical manner of the large $\mathcal { N } = 4$ algebra, see (A.1)； depending on the radius of the free boson, the values for $u$ are then quantized in suitable units. Since (3.4) saturates the BPS bound, all representations of $S _ { \kappa }$ are in fact BPS. We should note that the conformal weight of BPS representations with $u \neq 0$ is not protected under deformations of the theory, since we can continuously change the compactification radius of the boson and hence the conformal dimension.

# 3.2 Untwisted sector

BPS states from the untwisted sector are simple to determine (even if we drop the constraint that they should be ‘low-lying'). Since $j ^ { + } = 0$ for all representations of $S _ { \kappa }$ ， clearly also any symmetric combination will have $j ^ { + } = 0$ ．To pick out the representations which result in BPS states, we note that the BPS bound is convex in the sense that

$$
h _ { \mathrm { B P S } } ( 0 , j _ { 1 } ^ { - } , u _ { 1 } ) + ( 1 - \lambda ) h _ { \mathrm { B P S } } ( 0 , j _ { 2 } ^ { - } , u _ { 2 } ) \ge h _ { \mathrm { B P S } } ( 0 , \lambda j _ { 1 } ^ { - } + ( 1 - \lambda ) j _ { 2 } ^ { - } , \lambda u _ { 1 } + ( 1 - \lambda ) u _ { 2 } ) ,
$$

where $\lambda \in ( 0 , 1 )$ , and we have equality only if $j _ { 1 } ^ { - } = j _ { 2 } ^ { - }$ and $u _ { 1 } = u _ { 2 }$ . Thus only states that arise upon choosing the same representation in all factors can be BPS. Thus, the untwisted BPS spectrum consists simply of the BPS states of $S _ { \kappa }$ ， except that all quantum numbers have been multiplied by $N$ . Since the conformal weight of these states scales with $N$ , they are not low-lying' states — they have the interpretation of different vacua in the bulk,e.g. black hole geometries.

There are further BPS states which are constructed by the action of the fermions $\psi _ { - 1 / 2 } ^ { + + }$ onthegroudstatesoftrepresentasTyfillitesbeteethe above BPS states, since there are $N$ such fermions, one for each copy. Symmetrization introduces however multiple traces (except for the excitation involving a single fermion，which is part of the $\mathcal { N } = 4$ multiplet, see the comment after eq.(A.15)), and thus these states should not be interpreted as being single-particle states in the bulk. We should mention that this spectrum is precisely the BPS spectrum which was inferred from the index in [7, 48]. This suggests that the index is not very powerful in our context since it can be accounted for purely in terms of untwisted sector states (as well as states from the maximally twisted sector) that are not relevant for the comparison with supergravity. This is somewhat similar to the situation encountered in [32],where for the case of $\mathbb { T } ^ { 4 }$ ， the index could be obtained just from the groundstate.

# 3.3 Twisted sectors

Next we consider the BPS states from the single-cycle twisted sectors; in order to simplify the analysis, we shall concentrate from now on the low-lying BPS states. They have necessarily the property that $j ^ { + } = j ^ { - }$ and $u = 0$ . For, if this is not the case, then replacing $N$ by $M N$ the last two terms in the BPS bound (3.3) decrease by a factor $M$ , and hence the given state does not saturate the BPS bound any longer. Because of this fact, we will restrict from now on to the zero-charge sector ( $u = 0$ ）） of the $S _ { \kappa }$ -theory.

# 3.3.1 Odd twist

The detailed analysis of the twisted sectors depends on whether the twist is odd or even; in this subsection we first deal with the case that the twist $n = 2 m + 1$ is odd

![](images/4e51a0cbd4adab5c65f004438e41a1a2d598d2b985ef8ff669da33f00a39bac7.jpg)  
Figure 1. Minimal conformal weight for a given spin

- the even twist case will be discussed in the following subsection. Let us recall that a state of weight $h _ { 0 }$ and charge $R$ (here we collect all possible charges into one index) gives rise to a state in the $n$ -twisted sector with charge $R$ and weight

$$
h _ { n } = \frac { h _ { 0 } } { n } + \frac { c ( n ^ { 2 } - 1 ) } { 2 4 n } \ .
$$

For a derivation of this fact from the character point of view,see Appendix D. To obtain minimal conformal weight for a given set of charges, we first need to know the minimal conformal weight at which a given spin of the decoupled ${ \mathfrak { s u } } ( 2 ) _ { \kappa }$ algebra appears. This is quite intricate and interesting in its own right due to the appearance of null-vectors in the Verma module. The situation is depicted in Figure $1$ for $\kappa = 3$ ， which we have extracted directly from the affine $\mathfrak { s u } ( 2 )$ -character. Clearly, the minimal conformal weight can come potentially from all representations. One convenient way to parametrize the minimal conformal weight is as in [7]: we introduce a spectral flow of ${ \mathfrak { s u } } ( 2 ) _ { \kappa }$ ， which reshuffes states. Then the conformal weight and $\mathfrak { s u } ( 2 )$ -spin is given by

$$
h _ { 0 } ( j _ { \mathrm { b } } ) = \frac { j ( j + 1 ) } { \kappa + 2 } + j w + \frac { w ^ { 2 } \kappa } { 4 } , \qquad j _ { \mathrm { b } } ^ { - } = j + \frac 1 2 w \kappa .
$$

This state exists for $j = 0 , \frac { 1 } { 2 } , \dots , \frac { \kappa - 1 } { 2 }$ and $w \in \mathbb { Z } _ { \geq 0 }$ .Here, we excluded $j = \frac { \kappa } { 2 }$ to avoid overcounting, since, e.g. $\begin{array} { r } { j = \frac { \kappa } { 2 } } \end{array}$ ， $w = 0$ and $j = 0$ ， $w = 1$ are the same state.

On top of this state we can apply fractionally moded fermion modes in order to bring the state closer to the BPS bound. In terms of the original untwisted state with conformal weight $h _ { 0 }$ we should apply the lowest $\textstyle m = { \frac { n - 1 } { 2 } } \psi ^ { + + }$ modes since all of them have conformal weight smaller than $\begin{array} { l } { { \frac { \mathit { \Pi } _ { \pi } } { 2 } } } \end{array}$ ; thus upon dividing by $n$ as in (3.6), the spin increases more than the conformal weight. (Applying $m + 1$ of these fermions is also possible - this just reflects the fact that each BPS multiplet of the large ${ \mathcal N } = 4$ superconformal algebra contains two BPS states that are obtained from one another by the action of the free fermions of the algebra, see the comment after eq. (A.15).) The $m \ \psi ^ { + + }$ fermions contribute to the conformal weight ${ \scriptstyle { \frac { 1 } { 2 } } } m ^ { 2 }$ . We can furthermore also use $p$ fermions of the type $\psi ^ { + - }$ - here we adopt the notation that a negative $p$ means $- p$ fermions of the type $\psi ^ { - + }$ — but it is easy to see that no other modes can bring one closer to the BPS bound. Again, the contribution of these $p \psi ^ { + - }$ (or $\psi ^ { - + } )$ fermions to the conformal weight is ${ \textstyle \frac { 1 } { 2 } } p ^ { 2 }$ . We then have

$$
j ^ { + } = \frac 1 2 p + \frac 1 2 m ~ , ~ j ^ { - } = j _ { \mathrm { b } } ^ { - } - \frac 1 2 p + \frac 1 2 m ~ .
$$

Using (3.6) with (C.4), the difference to the BPS bound (3.3) is then

$$
\begin{array} { l } { \Delta h = \displaystyle \frac { \kappa + 1 } { \kappa + 2 } \displaystyle \frac { m ( m + 1 ) } { 2 m + 1 } + \displaystyle \frac { m ^ { 2 } + p ^ { 2 } + 2 h _ { 0 } ( j _ { \mathrm { b } } ^ { - } ) } { 2 ( 2 m + 1 ) } } \\ { - \displaystyle \frac { ( \kappa + 1 ) N ( p + m ) + N ( 2 j _ { \mathrm { b } } ^ { - } - p + m ) + 2 ( j _ { \mathrm { b } } ^ { - } - p ) ^ { 2 } } { 2 N ( \kappa + 2 ) } ~ . } \end{array}
$$

We have searched systematically for states saturating this bound, and we have found that for all such states $p = j _ { \mathrm { b } } ^ { - }$ and thus $j ^ { + } = j ^ { - }$ ， as expected, see the discussion at the beginning of this subsection. Then for each $w$ and $j$ ， there are two solutions of the quadratic equation $\Delta h = 0$ in $m$ ， which are given by

$$
m = j + \frac { w ( \kappa + 2 ) } { 2 } , \quad m = j + \frac { w ( \kappa + 2 ) } { 2 } + \frac { 4 j } { \kappa } .
$$

Clearly, the second solution is almost always not an integer. There is one exception, however，where we need both solutions, namely for $\begin{array} { r } { j = \frac { \kappa } { 2 } } \end{array}$ (which can be identified with a state with $j = 0$ and different $w$ ). A convenient way to get both solutions is to relax the above conditionthat $\begin{array} { r } { j \le \frac { \kappa - 1 } { 2 } } \end{array}$ to $j \le \frac { \kappa } { 2 }$ ,and nly keepthefirst solution.

We should note that the result has a slightly irregular structure. The associated spin quantum numbers are

$$
j ^ { + } = j ^ { - } = j + \frac { 1 } { 2 } ( \kappa + 1 ) w ~ .
$$

Thus,if $0 ~ < ~ j ~ < ~ \frac { \kappa - 1 } { 2 }$ ， the solutions are always integer-spaced. However， when changing the spectral flow index $w$ ， there is one solution which is only half-integer

spaced or three-half-integer spaced, depending on whether $\kappa$ is even or odd. As an example,we explicitly list the BPS spectrum for the example $\kappa = 5$ ：

$$
[ 0 , 0 ] _ { S } \ , \quad [ 1 , 1 ] _ { S } \ , \quad [ 2 , 2 ] _ { S } \ , \quad [ \textstyle \frac { 7 } { 2 } , \textstyle \frac { 7 } { 2 } ] _ { S } \ , \quad [ \textstyle \frac { 9 } { 2 } , \textstyle \frac { 9 } { 2 } ] _ { S } \ , \quad [ \textstyle \frac { 1 1 } { 2 } , \textstyle \frac { 1 1 } { 2 } ] _ { S } \ , \quad [ 6 , 6 ] \ , \quad \ldots .
$$

This irregularity does not occur for $\kappa = 0$ ， since then all representations are half integer spaced. In fact, the second solution of (3.1O) is absent in this case.

# 3.3.2 Even twist

Let us now analyse the BPS states that appear in the even twisted sectors, i.e. for $n = 2 m$ . As explained in Appendix D, (3.6) is modified in this case to

$$
h _ { n } = { \frac { h _ { 0 } } { n } } + { \frac { c n } { 2 4 } } + { \frac { 1 } { 4 n ( \kappa + 2 ) } } = { \frac { h _ { 0 } } { n } } + { \frac { c } { 2 4 } } { \frac { n ^ { 2 } - 1 } { n } } + { \frac { 1 } { 4 n } } ~ .
$$

In addition, there are fermionic zero modes which generate the representation $( { \bf 2 } , { \bf 1 } ) \oplus$ （204号 $( \mathbf { 1 } , \mathbf { 2 } )$ , see Appendix D. (The aditional term $\textstyle { \frac { 1 } { 4 n } }$ can be interpreted as coming from the ground state energy of the Ramond fermions [33].） Obviously to achieve a BPS state, $j ^ { + }$ will be shifted by $+ \textstyle { \frac { 1 } { 2 } }$ . Furthermore, we can continue to use the parametrization (3.7)，and it is now advantageous to use $m - 1$ fermions of the type $\psi ^ { + + }$ ， and $p$ fermions of type $\psi ^ { + - }$ . Because of the different moding,they now contribute $\textstyle { \frac { 1 } { 2 } } m ( m - 1 )$ and ${ \scriptstyle { \frac { 1 } { 2 } } p ( p - 1 ) }$ to the conformal weight, respectively. Then (3.9） becomes in this case

$$
\begin{array} { l } { \Delta h = \displaystyle \frac { \kappa + 1 } { \kappa + 2 } \displaystyle \frac { m } { 2 } + \displaystyle \frac { 1 } { 8 m ( \kappa + 2 ) } + \displaystyle \frac { m ( m - 1 ) + p ( p - 1 ) + 2 h ( j _ { \mathrm { b } } ^ { - } ) } { 4 m } } \\ { \displaystyle \qquad - \displaystyle \frac { ( \kappa + 1 ) N ( p + m ) + N ( 2 j _ { \mathrm { b } } ^ { - } - p + m - 1 ) + 2 ( j _ { \mathrm { b } } ^ { - } - p - \frac { 1 } { 2 } ) ^ { 2 } } { 2 N ( \kappa + 2 ) } ~ . } \end{array}
$$

Again, an extensive search shows that only states with $\begin{array} { r } { p = j _ { \mathrm { b } } ^ { - } - \frac { 1 } { 2 } } \end{array}$ and hence $j ^ { + } = j ^ { - }$ （204号 can satisfy the bound. There is one exception to this rule, however, namely when $N$ is even: then there are also BPS states in the $N$ -twisted sector which do not satisfy $j ^ { + } = j ^ { - }$ . But these are high-lying BPS states - they have to be,given our general argument from the beginning of Section 3.3.1 — and thus we will not consider them any further for the moment; we wil come back to them briefly in Section 5. Similarly, for each given $j$ and $w$ , there are two solutions to this equation

$$
m = j + \frac { w ( \kappa + 2 ) } { 2 } + \frac { 1 } { 2 } , \quad m = j + \frac { w ( \kappa + 2 ) } { 2 } + \frac { 4 j } { \kappa } - \frac { 1 } { 2 } .
$$

We again relax the restriction $\begin{array} { r } { j \le \frac { \kappa - 1 } { 2 } } \end{array}$ to $j \le \frac { \kappa } { 2 }$ in order to accommodate the cases where the second solution is integer. Luckily, because the terms $\pm \frac { 1 } { 2 }$ are now present, these conspire in such a way that here the half-integer steps occur where previously for odd twists we had three-half-integer steps and vice versa.

Thus, taking together the contributions from the even- and odd-twisted sectors, we obtain a regular BPS spectrum. We illustrate this again for the case $\kappa = 5$ ：

<html><body><table><tr><td>twist odd</td><td>1 [0,0]s</td><td>2</td><td>3 [1,1]s</td><td>4</td><td>5 6 [2,2]s</td><td>8</td><td>[，]s</td><td>9</td></tr><tr><td>even</td><td></td><td>[，]s</td><td></td><td>[,2]s</td><td></td><td>[，]s</td><td>[3,3]s</td><td></td></tr><tr><td>twist</td><td>10</td><td>11</td><td>12</td><td>13</td><td>15 16</td><td>17</td><td>18</td><td></td></tr><tr><td>odd</td><td></td><td>[s</td><td></td><td>[，]s</td><td>[6,6]s</td><td>[7,7]s</td><td></td><td></td></tr><tr><td>even</td><td>[4,4]s</td><td></td><td>[5,5]s</td><td></td><td></td><td>[，1]s</td><td></td><td>[，]s</td></tr></table></body></html>

This pattern continues in a similar fashion for generic twists. One can see from this numerical example that there are no BPS states in the twisted sectors of twist （204号 $n = q ( \kappa + 2 )$ ，where $q \in \mathbb { Z } _ { > 0 }$ ; we will argue below, see comment (i) in the following subsection, that this holds in general.

# 3.4 Recasting and summary of the spectrum

The above method to obtain the BPS spectrum looks quite complicated, and one may be tempted to suspect that there is a simpler description of the resulting BPS states. Such a formulation can indeed be given by looking at the supersymmetric ${ \mathfrak { s u } } ( 2 ) _ { 1 } \oplus { \mathfrak { s u } } ( 2 ) _ { \kappa + 1 }$ -current algebra of $S _ { \kappa }$ .From this perspective, the twisted BPS states arise from the $S _ { \kappa }$ states corresponding to $( 0 , j )$ upon applying the spectral flow by $( 2 j + w ( \kappa + 1 ) , w )$ with respect to ${ \mathfrak { s u } } ( 2 ) _ { 1 } \oplus { \mathfrak { s u } } ( 2 ) _ { \kappa + 1 }$ . Several comments are in order.

(i) From (3.10) and (3.15), the corresponding twist is given by $n = 2 j + 1 + w ( \kappa { + } 2 )$ As promised, we see that $n$ does not attain multiples of $\kappa + 2$ and thus these twisted sectors do not contribute BPS states.   
(ii) We see that $j$ and $w$ can be reinterpreted as spins and spectral flow numbers of the $\mathfrak { s u } ( 2 ) _ { \kappa + 1 }$ -algebra, instead of the bosonic algebra ${ \mathfrak { s u } } ( 2 ) _ { \kappa }$ . This explains why including the case $\begin{array} { r } { j = \frac { \kappa } { 2 } } \end{array}$ in the above parametrization accounted precisely for all states. Here, this property is natural and manifest.   
(iii） Spectral flow by one unit in one of the $\mathfrak { s u } ( 2 )$ 's changes the moding of the fermions from NS-moding to R-moding and vice versa. Thus the above construction leads to NS-fermions precisely when the sum of both spectral flow parameters is even. But from (i) we see that the sum equals precisely the cycle length minus one. Thus for odd cycle length NS-fermions occur, while for even cycle length R-fermions occur.   
(iv） The formula for the spectral flow already incorporates the ground state energy of the Ramond fermions as in (3.13). Thus, we should continue to use (3.6) as the ground state energy of the twisted sector.

(v) Given (i), (ii) and (iv) above, it is now easy to calculate the conformal weights and spins of the given state to confirm that they are indeed the BPS states we found above. However, it is not very transparent from this perspective why these are the only BPS states — this is why we presented the more pedestrian argument first.

The BPS spectrum reproduces the one of [7]. However, at least on the face of it, the details are a bit different, e.g. in [7] the first formulation was used but even and odd twists were treated uniformly. We have also shown that all low-lying BPS states have （204号 $j ^ { + } = j ^ { - }$ and $u = 0$ ， whereas [7] only analysed such BPS states (without showing that these are the only ones).

Let us finally comment on the cutoff of the spectrum. It is given by

$$
j _ { \mathrm { m a x } } ^ { + } = j _ { \mathrm { m a x } } ^ { - } = \frac { N ( \kappa + 1 ) } { 2 ( \kappa + 2 ) } = \frac { c } { 1 2 } ,
$$

where $c$ is the central charge of the complete theory. In order to see this we note that there are no gaps in the spin spectrum,and that each twisted sector contributes one BPS state, except that there are none for twist $n = q ( \kappa + 2 )$ . Thus the total numberofsinglecycletwistedso $( N )$ needs to muliplied by $\textstyle { \frac { \kappa + 1 } { \kappa + 2 } }$ , leading to (3.17). The cutoff is of course understood to be the half-integer part of $\textstyle { \frac { c } { 1 2 } }$ ,i.e. ${ \frac { 1 } { 2 } } \left\lfloor { \frac { c } { 6 } } \right\rfloor$ ： In the extreme cases of $\kappa = 0$ or $\kappa  \infty$ ， we get $\textstyle { \frac { 1 } { 4 } } N$ and ${ \scriptstyle { \frac { 1 } { 2 } } } N$ , respectively. The cutoff $\textstyle { \frac { 1 } { 2 } } N$ is indeed familiar from the torus $ { \mathbb { T } } ^ { 4 }$ [34], which on the level of the vacuum sector can be viewed as the limit of $\mathrm { S ^ { 3 } \times S ^ { 1 } }$ with infinite radius, see [9]. This completes our derivation of eq. (3.2).

# 4 BPS spectrum in string theory and supergravity

In this section we derive the corresponding BPS spectrum in supergravity and in the explicit WZW world-sheet description of the background.

# 4.1 Supergravity

The BPS spectrum of supergravity on $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ was analysed from first principles in [12], correcting the old analysis of [6]. It was found there that only states with equal spins with respect to the two $\mathfrak { s u } ( 2 )$ 's are BPS, and that the whole BPS spectrum organizes itself into representations of the large $\mathcal { N } = 4$ superconformal algebra as

$$
\bigoplus _ { j \in \frac { 1 } { 2 } \mathbb { Z } _ { \geq 0 } } ^ { \infty } [ j , j , u = 0 ] _ { S } \otimes \overline { { [ j , j , u = 0 ] } } _ { S } \ .
$$

As before,here $[ j , j , u = 0 ] _ { S }$ labels the BPS representation of the $A _ { \gamma }$ algebra，see Appendix A.1 for our conventions. In supergravity, only the wedge-modes of the $A _ { \gamma }$ algebra are visible, and thus (4.1) should be read in the sense of (A.15).

# 4.2 World-sheet analysis

In the same paper, the BPS spectrum was also determined using the explicit worldsheet description of the background with pure NS-NS flux in terms of WZW models [35-37], see also [38] and references therein for a description of the supersymmetric setting. Since we were only interested in the supergravity limit there, it was sufficient to study only the unflowed representations, for which the spectrum turned out to be the same as (4.1),but with an upper bound for the spin $j$ — this is a consequence of the unitarity bound of [39], see also [40],

$$
j \leq { \frac { 1 } { 2 } } \left\lfloor { \frac { Q _ { 5 } ^ { + } Q _ { 5 } ^ { - } } { Q _ { 5 } ^ { + } + Q _ { 5 } ^ { - } } } - 1 \right\rfloor \ .
$$

Since $Q _ { 1 }$ is to be identified with an upper bound on the spectrally flowed sectors $( w \leq Q _ { 1 } - 1 )$ ，we need to include in general also the spectrally flowed sectors (whose relevance for $\mathrm { A d S _ { 3 } }$ was first recognised in [41]). The analysis of the BPS spectrum for the spectrally flowed sectors is surprisingly complicated, and since there are misleading statements in the literature about it,we shall be fairly explicit in the following. The reader who is not interested in these details,may jump directly to Section 5 where the comparison to the $S _ { \kappa }$ theories is discussed.

In order to explain the spectrally flowed representations in detail, we need to introduce a bit of notation beyond that introduced already in [12]. The worldsheet theory is described in terms of supersymmetric affne theories associated to ${ \mathfrak { s l } } ( 2 , \mathbb { R } ) _ { k }$ （204号 and $\mathfrak { s u } ( 2 ) _ { k ^ { \pm } }$ . For the spectrally flowed representations, we consider the vector space of the unflowed ${ \mathfrak { s l } } ( 2 , \mathbb { R } ) _ { k }$ representations,but define on it the action of ${ \mathfrak { s l } } ( 2 , \mathbb { R } ) _ { k }$ (and the Virasoro algebra) by the hatted modes that are related by the spectral flow automorphism to the original modes, see eq. (B.3) in Appendix B. With respect to the hatted modes the representation is then not a conventional (Virasoro） highest weight representation. However， provided that $w > 0$ ，the representation (with respect to the hatted modes) consists of lowest weight representations of the global （204号 ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ algebra — this is the case one is interested in, since then the spectrum of the dual CFT will be bounded from below. In order to describe the resulting spectrum, it is convenient to spectrally flow also in the $\mathfrak { s u } ( 2 ) _ { k ^ { \pm } }$ algebra, although this does not lead to new representations; the relevant spectral flow is also described in eq. (B.3).

# 4.3 Review: full perturbative BPS spectrum for $\mathbf { A d S _ { 3 } } \times \mathbf { S ^ { 3 } } \times \mathbb { T } ^ { 4 }$

Let us begin by reviewing the more familiar case of 1 $\mathrm { 4 d S _ { 3 } \times S ^ { 3 } \times T ^ { 4 } }$ . In this case the worldsheet theory consists of an ${ \mathfrak { s l } } ( 2 , \mathbb { R } ) _ { k }$ WZW model together with a single $\mathfrak { s u } ( 2 ) _ { k ^ { \prime } }$ WZW model as well as 4 free bosons and fermions. The requirement that the string theory is critical leads to the condition that $k ^ { \prime } = k$ ，where $k = k ^ { \prime } = Q _ { 5 }$ in the brane description.

Let us first review the BPS states that come from the unflowed sector. In the NS-sector (the analysis for the R-sector is similar) the BPS states arise from the representation with $j _ { 0 } = j _ { 0 } ^ { \prime } - 1$ where $j _ { 0 }$ and $j _ { 0 } ^ { \prime }$ are the spins of the ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ and $\mathfrak { s u } ( 2 )$ ground state representation, respecitvely. In each such sector, there are two types of BPS states, $\mathcal { W }$ corresponding to $j = j _ { 0 } - 1$ and $y$ corresponding to $j = j _ { 0 }$ ， see e.g. [31]. The ground state spins in the unflowed sector are constrained by the Maldacena-Ooguri bound, which requires that the ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ -spin of the ground state has to satisfy

$$
\frac { 1 } { 2 } < j _ { 0 } < \frac { k + 1 } { 2 } ~ .
$$

(Incorporating the continuous representations of ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ amounts to taking the upper bound to be less or equal, so in the following,continuous representations are automatically taken care of.） In addition to (4.3), there is also the familiar unitarity bound associated to the bosonic $\mathfrak { s u } ( 2 )$ algebra at level $k - 2$ ，which requires that

$$
0 \leq j _ { 0 } ^ { \prime } \leq \frac { k - 2 } { 2 } ~ .
$$

Thus from the unflowed sector we get $\mathcal { W }$ and $y$ -type BPS states for

$$
\begin{array} { c } { { \mathcal { W } : ~ j = 0 , \ldots , { \frac { k - 2 } { 2 } } } } \\ { { \mathcal { Y } : ~ j = 1 , \ldots , { \frac { k } { 2 } } ~ . } } \end{array}
$$

In order to describe the BPS states in the spectrally flowed sector, we now consider a BPS state in the unflowed sector,and let it flow simultaneously by the same $w$ in both the ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ and $\mathfrak { s u } ( 2 )$ algebra.

$$
\begin{array} { r l } { L _ { 0 } ^ { \mathfrak { s l } ( 2 , \mathbb { R } ) } \ \mapsto \ } & { \widehat { L } _ { 0 } ^ { \mathfrak { s l } ( 2 , \mathbb { R } ) } = L _ { 0 } ^ { \mathfrak { s l } ( 2 , \mathbb { R } ) } - w \mathcal { I } _ { 0 } ^ { 3 } - \frac { k } { 4 } w ^ { 2 } } \\ { L _ { 0 } ^ { \mathfrak { s u } ( 2 ) } \ \mapsto \ } & { \widehat { L } _ { 0 } ^ { \mathfrak { s u } ( 2 ) } \ = L _ { 0 } ^ { \mathfrak { s u } ( 2 ) } \ + w K _ { 0 } ^ { 3 } + \frac { k } { 4 } w ^ { 2 } \ . } \end{array}
$$

Evaluated on the original BPS state for which the eigenvalues of $\mathcal { I } _ { 0 } ^ { 3 }$ and $\mathcal { K } _ { 0 } ^ { 3 }$ agree, the total $L _ { 0 }$ then remains unchanged,

$$
L _ { 0 } = L _ { 0 } ^ { \mathfrak { s l } ( 2 , \mathbb { R } ) } + L _ { 0 } ^ { \mathfrak { s u } ( 2 ) } \ \mapsto { \widehat L } _ { 0 } = L _ { 0 } \ .
$$

Thus the flowed state is again on-shell and passes also all the other requirements for being physical. Furthermore, since the $\mathcal { I } _ { 0 } ^ { 3 }$ and $\mathcal { K } _ { 0 } ^ { 3 }$ eigenvalues are shifted by the same amount (namely ${ \scriptstyle { \frac { k } { 2 } } } w$ ), the new state is again BPS, but with a spin that is now

$$
j \mapsto j + \frac { k } { 2 } w ~ .
$$

Spectrally flowing thus allows us to obtain BPS states whose spins go beyond the finite range described by (4.5). However, the resulting spectrum still has gaps [31, 42]. In particular, the $\mathcal { W }$ -type BPS states with $j = - { \textstyle \frac { 1 } { 2 } } + { \textstyle \frac { k } { 2 } } \mathbb { Z } _ { > 0 }$ do not arise, and for the $\mathcal { V }$ -type those with $j =  { { \frac { 1 } { 2 } } } +  { { \frac { k } { 2 } } }  { \mathbb { Z } } _ { > 0 }$ are missing. Combining this with the analysis in the R-sector and putting left- and right-movers together then leads to the BPS spectrum of the worldsheet theory for $ { \mathbb { T } } ^ { 4 }$ ， given by

$$
\bigoplus _ { \substack { j \in \frac { 1 } { 2 } \mathbb { Z } _ { \geq 0 } \setminus \frac { k } { 2 } \mathbb { Z } _ { > 0 } } } \left( [ j - \frac { 1 } { 2 } ] s \oplus 2 [ j ] s \oplus [ j + \frac { 1 } { 2 } ] s \right) \otimes ( \overline { { [ j - \frac { 1 } { 2 } ] } } _ { S } \oplus 2 \overline { { [ j ] } } _ { S } \oplus \overline { { [ j + \frac { 1 } { 2 } ] } } _ { S } ) \ .
$$

Here $[ j ] _ { S }$ denotes the short representation of the small ${ \mathcal N } = 4$ algebra, see, e.g. [43].

The missing chiral primaries,i.e. the missing terms $j \in { \frac { k } { 2 } } \mathbb { Z }$ break explicitly the Tduality the theory is supposed to have, since the expression is no longer symmetric in $Q _ { 1 }$ and $Q _ { 5 } = k$ ，see the discussion at the end of Section 2.1. However， this is believed to be a special feature of the pure NS-NS background, and these missing chiral primaries are expected to be hidden at the instanton singularity [11]. The corrected BPS spectrum thus reads

$$
\bigoplus _ { j \in \frac 1 2 \mathbb { Z } _ { \geq 0 } } ^ { \frac { c } { 1 2 } } ( [ j - \frac 1 2 ] _ { S } \oplus 2 [ j ] _ { S } \oplus [ j + \frac 1 2 ] _ { S } ) \otimes ( \overline { { [ j - \frac 1 2 ] } } _ { S } \oplus 2 \overline { { [ j ] } } _ { S } \oplus \overline { { [ j + \frac 1 2 ] } } _ { S } ) \ .
$$

Finally, in order to understand the upper bound of (4.1O), we note that $Q _ { 1 }$ should be identified with the maximal winding number as

$$
Q _ { 1 } = \left| w \right| + 1
$$

since $w + 1$ corresponds to the number of fundamental string (one short, and a long one, winding $w$ times around AdS ). Thus the upper bound for $j$ is $_ 3$

$$
j \leq { \frac { 1 } { 2 } } k Q _ { 1 } = { \frac { 1 } { 2 } } Q _ { 1 } Q _ { 5 } = { \frac { c } { 1 2 } } \ .
$$

# 4.4The full perturbative BPS spectrum for $\mathbf { A d S _ { 3 } } \times \mathbf { S ^ { 3 } } \times \mathbf { S ^ { 3 } } \times \mathbf { S ^ { 1 } }$ （204号

For the case of AdS $\phantom { + } 3 \times \mathrm { S } ^ { 3 } \times \mathrm { S } ^ { 3 } \times \mathsf { S } ^ { \leq }$ , the situation is much more complicated because the BPS states in the spectrally flowed sectors do not directly originate from BPS states in the unflowed sector. We begin with the technically easier case of the R-sector on the worldsheet.

# 4.4.1 R-sector

In the R-sector, the BPS states in the spectrally flowed sectors always originate from ground states before spectral flow. Recall from [12] that the $L _ { 0 }$ eigenvalues of the ground states in the unflowed sector are

$$
L _ { 0 } ^ { \mathfrak { s l } ( 2 , \mathbb { R } ) } = - \frac { j _ { 0 } ( j _ { 0 } - 1 ) } { k } \qquad \mathrm { a n d } \qquad L _ { 0 } ^ { \mathfrak { s u } ( 2 ) ^ { \pm } } = \frac { j _ { 0 } ^ { \pm } ( j _ { 0 } ^ { \pm } + 1 ) } { k } ,
$$

where $j _ { 0 }$ and $j _ { 0 } ^ { \pm }$ denote the ${ \mathfrak { s l } } ( 2 , \mathbb { R } ) _ { k + 2 }$ ， $\mathfrak { s u } ( 2 ) _ { k ^ { \pm } - 2 }$ decoupled bosonic spins of the ground state. Flowing by $w$ ， $w ^ { + }$ and $w ^ { - }$ in ${ \mathfrak { s l } } ( 2 , \mathbb { R } ) _ { k }$ ， ${ \mathfrak { s u } } ( 2 ) _ { k ^ { + } }$ and ${ \mathfrak { s u } } ( 2 ) _ { k ^ { - } }$ ， respectively, the $L _ { 0 }$ eigenvalues are shifted by

$$
\begin{array} { r l } { L _ { 0 } ^ { \mathfrak { s l } ( 2 , \mathbb { R } ) } \mapsto } & { \widehat { L } _ { 0 } ^ { \mathfrak { s l } ( 2 , \mathbb { R } ) } = L _ { 0 } ^ { \mathfrak { s l } ( 2 , \mathbb { R } ) } - w \left( j _ { 0 } - \frac 1 2 \right) - \frac { k } { 4 } w ^ { 2 } } \\ { L _ { 0 } ^ { \mathfrak { s u } ( 2 ) ^ { \pm } } \mapsto } & { \widehat { L } _ { 0 } ^ { \mathfrak { s u } ( 2 ) ^ { \pm } } = L _ { 0 } ^ { \mathfrak { s u } ( 2 ) ^ { \pm } } + w ^ { \pm } \left( j _ { 0 } ^ { \pm } + \frac 1 2 \right) + \frac { k } { 4 } ( w ^ { \pm } ) ^ { 2 } . } \end{array}
$$

Note that shift by $\pm \frac { 1 } { 2 }$ in the terms proportional to $w$ and $w ^ { \pm }$ ， respectively， comes from the fact that the spectral flow is performed with respect to the full (coupled) algebra,and the spin with respect to the coupled algebra is shifted by $\pm \frac { 1 } { 2 }$ , see e.g. [38] for a detailed discussion. (In order to move closer to the BPS bound, we choose the shift so as to lower the ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ -spin,but to increase the $\mathfrak { s u } ( 2 )$ -spins.） After spectral flow, the resulting spins are then equal to

$$
j = j _ { 0 } + \frac { k w } { 2 } - \frac { 1 } { 2 } \quad \mathrm { a n d } \quad j ^ { \pm } = j _ { 0 } ^ { \pm } + \frac { k ^ { \pm } w ^ { \pm } } { 2 } + \frac { 1 } { 2 } ~ .
$$

The mass shell condition in the spectrally flowed sector is thus

$$
\begin{array} { r l r } {  { - \frac { j _ { 0 } ( j _ { 0 } - 1 ) } { k } - w ( j _ { 0 } - \frac { 1 } { 2 } ) - \frac { k } { 4 } w ^ { 2 } + \frac { j _ { 0 } ^ { + } ( j _ { 0 } ^ { + } + 1 ) } { k ^ { + } } + w ^ { + } ( j _ { 0 } ^ { + } + \frac { 1 } { 2 } ) + \frac { k ^ { + } } { 4 } ( w ^ { + } ) ^ { 2 } } } \\ & { } & { \qquad + \frac { j _ { 0 } ^ { - } ( j _ { 0 } ^ { - } + 1 ) } { k ^ { - } } + w ^ { - } ( j _ { 0 } ^ { - } + \frac { 1 } { 2 } ) + \frac { k ^ { - } } { 4 } ( w ^ { - } ) ^ { 2 } = 0 \ . \ ~ ( 4 . } \end{array}
$$

The crucial observation is now that (4.16) can be rewritten in terms of $j$ and $j ^ { \pm }$ as

$$
- { \frac { j ^ { 2 } - { \frac { 1 } { 4 } } } { k } } + { \frac { ( j ^ { + } ) ^ { 2 } - { \frac { 1 } { 4 } } } { k ^ { + } } } + { \frac { ( j ^ { - } ) ^ { 2 } - { \frac { 1 } { 4 } } } { k ^ { - } } } = - { \frac { j ^ { 2 } } { k } } + { \frac { ( j ^ { + } ) ^ { 2 } } { k ^ { + } } } + { \frac { ( j ^ { - } ) ^ { 2 } } { k ^ { - } } } = 0 \ .
$$

This gives a relation for $j$ in terms of $j ^ { + }$ and $j ^ { - }$ . Combining with the $A _ { \gamma }$ BPS bound, one can easily see that there are no BPS states with $j ^ { + } \neq j ^ { - }$ whose unflowed spin （20 $j _ { 0 }$ satisfies the Maldacena-Ooguri bound - this follows by a similar argument as for the unflowed NS sector in [12]. On the other hand, setting

$$
j = j ^ { + } = j ^ { - }
$$

clearly solves equation (4.17) since the levels of the coupled algebras must satisfy

$$
\frac { 1 } { k } = \frac { 1 } { k ^ { + } } + \frac { 1 } { k ^ { - } } \ ,
$$

as follows from criticality, see e.g. [12] for more details. In addition, the corresponding state is BPS. Furthermore, by choosing $w$ suitably, any half-integer $j$ can be written in the form (4.15） where $j _ { 0 }$ satisfies the Maldacena-Ooguri bound (4.3). Thus, we conclude that there is a BPS state for each half-integer value of $j = j ^ { + } = j ^ { - }$ ：

There is however one subtlety. Since the spin $j _ { 0 } ^ { \pm }$ of the ground state of the bosonic $\mathfrak { s u } ( 2 ) _ { k ^ { \pm } - 2 }$ algebra must be of the form $j _ { 0 } ^ { \pm } = 0 , { \textstyle \frac { 1 } { 2 } } , . . . , { \textstyle \frac { k ^ { \pm } - 2 } { 2 } }$ （204号 we can never obtain

$$
j ^ { + } \notin { \frac { k ^ { + } } { 2 } } \mathbb { Z } _ { > 0 } \qquad \mathrm { a n d } \qquad j ^ { - } \notin { \frac { k ^ { - } } { 2 } } \mathbb { Z } _ { > 0 } \ .
$$

Thus it follows from (4.18) that

$$
\begin{array} { r } { j \not \in \frac { k ^ { + } } { 2 } \mathbb { Z } _ { > 0 } \cup \frac { k ^ { - } } { 2 } \mathbb { Z } _ { > 0 } \ . } \end{array}
$$

We therefore conclude that BPS states that arise from the R-sector are of the form

$$
\bigoplus _ { j \in \frac 1 2 \mathbb { Z } _ { > 0 } \backslash \left( \frac { k ^ { + } } { 2 } \mathbb { Z } _ { > 0 } \cup \frac { k ^ { - } } { 2 } \mathbb { Z } _ { > 0 } \right) } ( j , j , u = 0 ) _ { S } \ .
$$

Here,round brackets refer to BPS states, not to complete BPS multiplet.

Recall from the representation theory of the large ${ \mathcal N } = 4$ superconformal algebra that a BPS multiplet always contains two BPS states, the latter being obtained by acting with the fermion $Q _ { - 1 / 2 } ^ { + + }$ on the highest weight state.From the space-time viewpoint,the action of $Q _ { - 1 / 2 } ^ { + + }$ mapsanNSsewodsestatetaRs state and vice versa. Thus the above states will need to combined with suitable NS-sector states to form full large ${ \mathcal N } = 4$ multiplets.

# 4.4.2 NS sector

The analysis for the spectrally flowed NS sector is similar, except that in the NSsector the states before spectral flow are not ground states， but involve also $- \textstyle { \frac { 1 } { 2 } }$ （20 fermion modes. As it turns out, we only need at most one fermionic mode in each of the three algebras, and we can hence parametrize the unflowed state in terms of $\delta , \delta ^ { \pm } \in \{ 0 , 1 \}$ ，where $\delta = 0 , 1$ means that a ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ mode has or has not been applied, and similarly for the two $\mathfrak { s u } ( 2 ) _ { k ^ { \pm } }$ algebras.(The relevant mode must again decrease the ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ spin,and increase the $\mathfrak { s u } ( 2 )$ spins in order to bring the state closer to the BPS bound.） After spectral flow, the massshell condition then reads

$$
\begin{array} { l } { { \displaystyle - \frac { j _ { 0 } ( j _ { 0 } - 1 ) } { k } - w ( j _ { 0 } - \delta ) - \frac { k } { 4 } w ^ { 2 } + \frac { j _ { 0 } ^ { + } ( j _ { 0 } ^ { + } + 1 ) } { k ^ { + } } + w ^ { + } ( j _ { 0 } ^ { + } + \delta ^ { + } ) + \frac { k ^ { + } } { 4 } ( w ^ { + } ) ^ { 2 } } } \\ { { \displaystyle \qquad + \frac { j _ { 0 } ^ { - } ( j _ { 0 } ^ { - } + 1 ) } { k ^ { - } } + w ^ { - } ( j _ { 0 } ^ { - } + \delta ^ { - } ) + \frac { k ^ { - } } { 4 } ( w ^ { - } ) ^ { 2 } + \frac { 1 } { 2 } \delta + \frac { 1 } { 2 } \delta ^ { + } + \frac { 1 } { 2 } \delta ^ { - } = \frac { 1 } { 2 } ~ . } } \end{array}
$$

The true spins $j$ ， $j ^ { + }$ and $j ^ { - }$ are given by

$$
j = j _ { 0 } + \frac { k w } { 2 } - \delta ~ , ~ j ^ { \pm } = j _ { 0 } ^ { \pm } + \frac { k ^ { \pm } w ^ { \pm } } { 2 } + \delta ^ { \pm } ~ .
$$

It is not entirely trivial to find the solutions that saturate the BPS bound, and the detailed construction is described in Appendix $\mathrm { E }$ . It follows from the analysis there

that the NS-sector BPS spectrum equals5

$$
\begin{array} { r l } & { \quad \quad \displaystyle \bigoplus _ { j \in \frac 1 2 \mathbb { Z } _ { \geq 0 } \setminus \left( \frac 1 2 \lfloor k \mathbb { Z } _ { \geq 0 } \rfloor \setminus \frac 1 2 \operatorname { l c m } ( k ^ { + } , k ^ { - } ) \mathbb { Z } _ { \geq 0 } \cup \left( \frac 1 2 \lfloor k \mathbb { Z } _ { \geq 0 } \rfloor + \frac 1 2 \right) \setminus \left( \frac 1 2 \lfloor \operatorname { c m } ( k ^ { + } , k ^ { - } ) \mathbb { Z } _ { \geq 0 } + \frac 1 2 \right) \right) } } \left( j , j , u = 0 \right) _ { S }  \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad j \in \frac { k ^ { + } } 2 \mathbb { Z } _ { > 0 } \cup \frac { k ^ { - } } 2 \mathbb { Z } _ { > 0 } } \end{array}
$$

where as in R sector the round brackets refer to BPS states rather than to complete BPS multiplets. Here $k$ is the level of the supersymmetric ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ WZW model, defined via (4.19). $\lfloor k \mathbb { Z } _ { > 0 } \rfloor$ denotes the elementwise floor of this set - this is necessary since $k$ is not an integer in the generic case,which complicates the analysis significantly. The Maldacena-Ooguri bound (4.3) still applies, and it implies that the states $\frac { 1 } { 2 } \lfloor k \mathbb { Z } _ { > 0 } \rfloor$ are located at the boundary between two successive spectrally flowed sectors, exactly as in the case of $ { \mathbb { T } } ^ { 4 }$ ， see (4.9).

# 4.4.3 Full perturbative BPS spectrum

Combining the BPS states in the R-sector (4.22) with those in the NS-sector (4.25), we obtain

$$
\begin{array} { r } { \bigoplus _ { \substack { j \in \frac { 1 } { 2 } \mathbb { Z } _ { \geq 0 } \setminus \left( \frac { 1 } { 2 } \lfloor k \mathbb { Z } _ { \geq 0 } \rfloor \setminus \frac { 1 } { 2 } \operatorname { l c m } ( k ^ { + } , k ^ { - } ) \mathbb { Z } _ { \geq 0 } \right) } } \left( j , j , u = 0 \right) _ { S } \oplus ( j + \frac { 1 } { 2 } , j + \frac { 1 } { 2 } , u = 0 ) _ { S } \ . } \end{array}
$$

Again, the round brackets refer to BPS states instead of the complete BPS multiplets. It is very reassuring that (4.26) fits into BPS multiplets (as it has to), i.e. that the terms in the sum are just the BPS states of the multiplet

$$
[ j , j , u = 0 ] _ { S } = ( j , j , u = 0 ) _ { S } \oplus ( j + \textstyle { \frac { 1 } { 2 } } , j + \textstyle { \frac { 1 } { 2 } } , u = 0 ) _ { S }
$$

(that contains two BPS states). The above discussion explains also when the Rsector state is the highest weight state of the BPS multiplet and when the NS-sector state is. The full spectrum (including right-movers） is then obtained by tensoring the BPS representations $[ j , j , u = 0 ] _ { S }$ (for a given $j$ ） for left- and right-movers; this then leads to

$$
\bigoplus _ { \substack { j \in \frac { 1 } { 2 } \mathbb { Z } _ { \geq 0 } \setminus \left( \frac { 1 } { 2 } \left\lfloor k \mathbb { Z } _ { \geq 0 } \right\rfloor \setminus \frac { 1 } { 2 } \operatorname { l c m } ( k ^ { + } , k ^ { - } ) \mathbb { Z } _ { \geq 0 } \right) } } ^ { \frac { c } { 1 2 } } [ j , j , u = 0 ] _ { S } \otimes \overline { { \left[ j , j , u = 0 \right] } } _ { S } \ .
$$

A few comments are in order. First of all, we note that

$$
{ \textstyle \frac { 1 } { 2 } } \mathbb { Z } _ { \ge 0 } \cap { \textstyle \frac { 1 } { 2 } } k \mathbb { Z } _ { \ge 0 } = { \textstyle \frac { 1 } { 2 } } \operatorname { l c m } ( k ^ { + } , k ^ { - } ) \mathbb { Z } _ { \ge 0 } ~ ,
$$

so the states $j$ ，with $j$ divisible by $\frac { k ^ { + } } { 2 }$ and $\frac { k ^ { - } } { 2 }$ appear in the sum. Secondly, taking the limit of $k ^ { - } \to \infty$ in (4.28) indeed gives back (4.9). Finally, the cutoff $\textstyle { \frac { c } { 1 2 } }$ arises in exactly same manner as it did for $ { \mathbb { T } } ^ { 4 }$ , i.e. imposing a maximum spectral flow $w$ for （204号 ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ by(4.11） imposes an upper limit on $j$

Some of the BPS states can be obtained by spectrally flowing the BPS states of the unflowed sector, as was possible for the case of $ { \mathbb { T } } ^ { 4 }$ above. However,in order for this procedure to map BPS states to BPS states, we must now choose the spectral flow parameters of the two $\mathfrak { s u } ( 2 )$ 's as a function of the spectral flow parameter $w$ of （20 ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ as

$$
w ^ { + } = \frac { k ^ { - } w } { k ^ { + } + k ^ { - } } , \quad w ^ { - } = \frac { k ^ { + } w } { k ^ { + } + k ^ { - } } .
$$

On the other hand, $w ^ { \pm } \in \mathbb { Z }$ must be integers, and hence this is not always possible, but only when $w$ is a multiple of $( k ^ { + } + k ^ { - } ) / \mathrm { g c d } ( k ^ { + } , k ^ { - } )$ . Hence this accounts only for a fraction of the BPS states. These special states were already identified in [31] in the particular case of $k ^ { + } = k ^ { - }$ ， but the other BPS states were overlooked.

Now again by the general logic of [11]，we expect this BPS spectrum to be corrected to

$$
\bigoplus _ { j \in \frac 1 2 \mathbb { Z } _ { \geq 0 } } ^ { \frac { c } { 1 2 } } [ j , j , u = 0 ] _ { S } \otimes \overline { { [ j , j , u = 0 ] } } _ { S } \ .
$$

This spectrum then agrees with the supergravity spectrum (4.1) in the limit $c  \infty$ ， and this is the spectrum with which we should compare the BPS spectrum of the dual CFT.

# 5 Comparison between symmetric orbifold and world-sheet

After these preparations, it is now straightforward to compare the BPS spectra of the different descriptions. We shall also make a few additional comments in support of our proposal.

# 5.1 BPS spectrum

The low-lying single-particle BPS spectrum of the symmetric orbifold of $S _ { \kappa }$ was calculated in eq. (3.2)，and this agrees exactly with the BPS of string theory as determined in eq. (4.31). Apart from the fact that there is a single BPS multiplet for each half-integer spin, also the upper cutoff matches exactly. This is quite nontrivial, since this upper bound arises in quit different ways in the two descriptions.

The CFT has three types of additional BPS states, which we now discuss in turn.

1. Multi-particle states: Since the single-particle BPS spectrum agrees on the two sides,and since the states are constructed in exactly the same manner in the

CFT and in supergravity or the world-sheet theory, the multi-particle states must also agree.

2. There are further BPS states arising from the untwisted sector,as discussed in subsection 3.2.6 At conformal weight

$$
h = \frac { c } { 2 4 } < \frac { c } { 1 2 }
$$

the Ramond ground state appears, which corresponds to a black hole in supergravity, so we expect， a priori， only agreement of the BPS spectrum up to $\textstyle { \frac { c } { 2 4 } }$ . However, as for $ { \mathbb { T } } ^ { 4 }$ and K3, the agreement continues actually up to $\textstyle { \frac { c } { 1 2 } }$ The additional BPS states from the untwisted sector should correspond to BPS states in the geometry $\mathrm { B T Z \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ . The cutoff $\textstyle { \frac { c } { 1 2 } }$ seems to be a generic feature of string holography on AdS $_ 3$ -backgrounds.

3.Finally, the symmetric orbifold of $S _ { \kappa }$ possesses additional BPS states in the maximally twisted sector, provided that the number of copies is even. This corresponds to a deeply stringy effect and hence cannot be seen in supergravity, nor in the worldsheet description，where the emergence of $Q _ { 1 }$ is somewhat hidden. The relevant states all have spins $j ^ { + } \neq j ^ { - }$ ， and therefore do not give rise to ${ \mathcal N } = 2$ chiral primaries, as will be discussed in the following subsection.

# 5.2 The chiral ring

The large ${ \mathcal N } = 4$ superconformal algebra contains an ${ \mathcal N } = 2$ superconformal algebra as a subalgebra [7, 29], see Appendix A.2 for a short review. It is not difficult to see that the only BPS states of the large $\mathcal { N } = 4$ superconformal algebra that are also BPS with respect to this ${ \mathcal N } = 2$ subalgebra are those with $j ^ { + } = j ^ { - }$ and $u = 0$ ： Indeed, the BPS bound of the ${ \mathcal { N } } = 2$ algebra agrees with the one of $\mathrm { D } ( 2 , 1 | \alpha )$ (A.14), as one can see from (A.16). This implies that the only ${ \mathcal N } = 2$ chiral primaries have （20 $j ^ { + } = j ^ { - }$ and $u = 0$ ， since otherwise the state would violate the ${ \mathcal N } = 4$ BPS bound. The highest weight state with respect to the two $\mathfrak { s u } ( 2 )$ -algebras is a chiral primary state,while the lowest weight state describes an anti-chiral primary. This explains also why the BPS bound (3.3) has such a simple form in this case.

It is very intriguing that the only BPS multiplets of supergravity are of this form, i.e. contain $\mathcal { N } = 2$ chiral (or anti-chiral) primary states. In particular, it is known that the spectrum of ${ \mathcal N } = 2$ chiral primaries is invariant under deformations,7 and thus we should find the same chiral primary spectrum at all points in moduli space. This is nicely borne out by our analysis: the only additional BPS states of the symmetric orbifold of $S _ { \kappa }$ (that appear in the maximally twisted sector provided that the number of copies is even) always have different spins $j ^ { + } \neq j ^ { - }$ ，and hence do not give rise to (stable) ${ \mathcal N } = 2$ chiral primary states. It also ties in nicely with the conclusions reached in [47] where using integrability arguments it was argued that the BPS spectrum is the same everwhere in moduli space (and that it only consists of BPS states with $j ^ { + } = j ^ { - }$ ）

We should also stress that the moduli correspond to special BPS states of this kind: they are described by the states with $\begin{array} { r } { j ^ { + } = j ^ { - } = \frac { 1 } { 2 } } \end{array}$ . In particular,our dual CFT has therefore the same number of moduli (namely one complex modulus） as supergravity or the world-sheet description.

Finally, one might wonder whether one can compare the elliptic genus for this （20 $\mathcal { N } = 2$ subalgebra as this would also explore the $1 / 4$ BPS spectrum.However,as remarked in [48], the elliptic genus for this subalgebra always vanishes, as it did in the case of $\mathbb { T } ^ { 4 }$ .8 It is possible to modify the index so that it does not vanish [48]. (This is the natural analogue of the construction of [32] for the case of $\mathbb { T } ^ { 4 }$ .）However,in either case, the resulting index does not give rise to interesting constraints. For example, in our context only the untwisted sector contributes to the low-lying spectrum, while the contributions from the twisted sectors cancel out.

# 5.3 An effective $\mathbb { T } ^ { 2 }$ description

The form of the chiral primary spectrum is formally the same as that of the symmetric orbifold of $ { \mathbb { T } } ^ { 2 }$ . In order to see this, recall that a large ${ \mathcal N } = 4$ BPS multiplet always contains two $\mathcal { N } = 2$ chiral primaries: in addition to the highest weight, the state that is obtained by the action of the free fermion $Q _ { - 1 / 2 } ^ { + + }$ is also chiral primary. Thus the chiral primary spectrum is given by $\textstyle { \frac { c } { 6 } }$ overlapping diamonds of the form

$$
\begin{array} { c c c } { { } } & { { } } & { { 1 } } \\ { { 1 } } & { { } } & { { 1 } } \\ { { } } & { { } } & { { 1 } } \end{array}
$$

Since (5.2) is the Hodge diamond of $ { \mathbb { T } } ^ { 2 }$ ， the BPS spectrum has the same form as the symmetric orbifold of $\mathbb { T } ^ { 2 }$ . This also has a neat microscopic interpretation，at least for $\kappa = 0$ : the algebra $S _ { 0 }$ consists of 4 free fermions and one boson - the （204号 ${ \mathfrak { s u } } ( 2 ) _ { \kappa }$ theory disappears at $\kappa = 0$ . Two fermions of the four are uncharged w.r.t. the $\mathfrak { u } ( 1 )$ -current ( $\psi ^ { + - }$ and $\psi ^ { - + }$ ). These two fermions only appear together as a bilinear combination in the generators of the ${ \mathcal N } = 2$ subalgebra，as one can see from (C.2) and (A.16). We can thus bosonize the two uncharged fermions and write down the （204号 ${ \mathcal N } = 2$ algebra without the use of vertex operators. We thus obtain a torus theory, where the ${ \mathcal N } = 2$ algebra agrees with the canonical ${ \mathcal N } = 2$ structure on $ { \mathbb { T } } ^ { 2 }$ . Among other things, this allows us to copy well-known results for the chiral ring of the $\sigma$ model on $ { \mathbb { T } } ^ { 2 }$ for $S _ { 0 }$ . In particular the chiral ring of the $Q _ { 1 }$ -fold symmetric orbifold of $S _ { 0 }$ can be identified with the Dolbeault cohomology ring of $( \mathbb { T } ^ { 2 } ) ^ { Q _ { 1 } } / S _ { Q _ { 1 } }$ . It is wellknown that this cohomology ring has the structure of a Fock space of free particles [28, 45, 49, 50], one particle for every cohomology element of $\mathbb { T } ^ { 2 }$ . Furthermore, the cohomology of the $Q _ { 1 }$ -fold symmetric product corresponds to the subset in this Fock space with conformal weight $Q _ { 1 }$ ：

In particular, it is easy to write down a generating function for the Poincaré polynomial of the symmetric product [43, eq. (5.4)], see also [51] for a mathematical treatment for the case of K3

$$
\sum _ { Q _ { 1 } = 0 } ^ { \infty } p ^ { Q _ { 1 } } P _ { t , \bar { t } } ( \mathrm { S y m } ^ { Q _ { 1 } } ( S _ { 0 } ) ) = \prod _ { m = 1 } ^ { \infty } \frac { ( 1 + p ^ { m } t ^ { \frac { 1 } { 2 } ( m + 1 ) } \bar { t } ^ { \frac { 1 } { 2 } ( m - 1 ) } ) ( 1 + p ^ { m } t ^ { \frac { 1 } { 2 } ( m - 1 ) } \bar { t } ^ { \frac { 1 } { 2 } ( m + 1 ) } ) } { ( 1 - p ^ { m } t ^ { \frac { 1 } { 2 } ( m - 1 ) } \bar { t } ^ { \frac { 1 } { 2 } ( m - 1 ) } ) ( 1 - p ^ { m } t ^ { \frac { 1 } { 2 } ( m + 1 ) } \bar { t } ^ { \frac { 1 } { 2 } ( m + 1 ) } ) } \ .
$$

Here, the variable $m$ parametrizes the length of the cycle,and to extract the contribution from a single-twist cycle of length $n$ ， we take one term coming from $m = n$ ， with all the other terms coming from the vacuum contribution $m = 1$ and the term $( 1 - p ) ^ { - 1 }$ . More specifically, the single-twist contribution from the $n$ -twisted sector turns out to be

$$
\sum _ { Q _ { 1 } = n } ^ { \infty } p ^ { Q _ { 1 } } P _ { t , \bar { t } } ^ { n - \mathrm { t w i s t } } ( \mathrm { S y m } ^ { Q _ { 1 } } ( S _ { 0 } ) ) = \frac { p ^ { n } t ^ { \frac { 1 } { 2 } n } \bar { t } ^ { \frac { - 1 } { 2 } n } } { 1 - p } ( t ^ { \frac { 1 } { 2 } } \bar { t } ^ { \frac { 1 } { 2 } } + t ^ { \frac { 1 } { 2 } } \bar { t } ^ { - \frac { 1 } { 2 } } + t ^ { - \frac { 1 } { 2 } } \bar { t } ^ { \frac { - 1 } { 2 } } + t ^ { - \frac { 1 } { 2 } } \bar { t } ^ { - \frac { 1 } { 2 } } )
$$

and in particular does not change when increasing $Q _ { 1 }$ beyond $n$ . We see that the exponents of $t$ and $t$ are only integers when $n$ is odd. Hence only those states can lift to BPS representations $[ j , j , u = 0 ] _ { S }$ of the large $\mathcal { N } = 4$ algebra, since these states always have half-integer charges, i.e. integer exponents of $t$ and $t$ . The contribution is then simply given by a diamond at height $\scriptstyle { \frac { 1 } { 2 } } ( n - 1 )$ ， and since $n \leq Q _ { 1 }$ , the maximal achievable exponent of $t$ (or $t$ ）is ${ \scriptstyle { \frac { 1 } { 2 } } } Q _ { 1 }$ .This then reproduces precisely the chiral primary spectrum of eq. (3.2) with the correct cutoff.

# 6 Discussion and outlook

In this paper we have identified the CFT dual of string theory on $\mathrm { A d S _ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 3 } } \times \mathrm { S ^ { 1 } }$ for the case that the larger of the two $Q _ { 5 } ^ { \pm }$ quantum numbers is a multiple of the smaller one: for the case that $Q _ { 5 } ^ { - } \geq Q _ { 5 } ^ { + }$ , the relevant CFT is the symmetric orbifold

$$
\mathrm { S y m } ^ { Q _ { 1 } Q _ { 5 } ^ { + } } ( S _ { \kappa } ) \qquad \mathrm { w i t h } \quad \kappa = { \frac { Q _ { 5 } ^ { - } } { Q _ { 5 } ^ { + } } } - 1 \ .
$$

This proposal was motived by considering a brane construction, from which the CFT dual could be read off; this argument is fairly clean provided that $Q _ { 5 } ^ { + } = 1$ ,while for

$Q _ { 5 } ^ { + } > 1$ our proposal is more of an educated guess. In either case, however, we have managed to give convincing evidence for this proposal. In particular, we have shown that the BPS spectra of the dual CFT reproduces exactly that of supergravity or the world-sheet description. In fact， the agreement is as good as for the familiar case of $ { \mathbb { T } } ^ { 4 }$ . As a consequence the moduli also match. Finally, our proposal also has the right behaviour in the limit in which the radius of the ${ \mathrm { S } } ^ { 3 }$ goes to infinity: the chiral algebra of the dual CFT then becomes that of the symmetric orbifold of $ { \mathbb { T } } ^ { 4 }$ ， as expected, see also [9].

It would be very interesting to perform further tests on the proposal; for example, it would be very interesting to compare 3-point functions as in [2, 3]. It would also be very interesting to understand to which extent our proposal fits together with the UV description suggested in [52], and how it relates to the large ${ \mathcal N } = 4$ superconformal higher spin - CFT duality of [8]. We hope to come back to some of these questions in the near future.

# Acknowledgements

We are grateful to Rajesh Gopakumar for many useful discussons as well as for initial collaboration. We also thank Ofer Aharony， Costas Bachas, Kevin Ferreira, Sergei Gukov, Juan Maldacena, Emil Martinec, Greg Moore, Alessandro Sfondrini, Andy Strominger, David Tong, Edward Witten and Zhixian Zhu for useful conversations. MRG thanks the ITP at the Chinese Academy of Sciences for hospitality at various stages of this work. The research of LE and MRG is (partly) supported by the NCCR SwissMAP, funded by the Swiss National Science Foundation. All of three of us gratefully acknowledge the hospitality of the Galileo Galilei Institute for Theoretical Physics (GGI) for hospitality, and INFN for partial financial support during the program “New Developments in AdS3/CFT2 Holography".

# A The large $\pmb { \mathcal { N } } = 4$ algebra and its BPS bound

In bi-spinor notation, the large ${ \mathcal N } = 4$ superconformal algebra $A _ { \gamma }$ is generated by

$$
\begin{array} { c } { { \left[ U _ { m } , U _ { n } \right] = \frac { k ^ { + } + k ^ { - } } { 2 } m \delta _ { m , - n } } } \\ { { \left[ A _ { m } ^ { + } , Q _ { r } ^ { w } \right] = \frac { 1 } { 2 } ( \sigma ^ { i } ) ^ { \mu } \ Q _ { m + r } ^ { m } } } \\ { { \left[ A _ { m } ^ { - i } , Q _ { r } ^ { w } \right] = \frac { 1 } { 2 } ( \sigma ^ { i } ) ^ { \nu } \ Q _ { m + r } ^ { i \mu } } } \\ { { \left\{ Q _ { m } ^ { w } , Q _ { o } ^ { w } \right\} = \left( k ^ { + } + k ^ { - } \right) \epsilon ^ { \mu \nu } \epsilon ^ { \nu \sigma } \delta _ { r - s } } } \\ { { \left[ A _ { m } ^ { \pm i } , A _ { n } ^ { \pm j } \right] = \frac { k ^ { \pm } } { 2 } m \delta ^ { i j } \delta _ { m , - n } + \mathrm { i } \epsilon ^ { i j i } A _ { m + n } ^ { \pm { \frac { i } { 2 } } i } } } \\ { { \left[ U _ { m } , G _ { r } ^ { w } \right] = \mathrm { i } m Q _ { m + r } ^ { m \neq { \nu } } } } \\ { { \left[ A _ { m } ^ { + } , G _ { r } ^ { w \mu } \right] = \frac { 1 } { 2 } ( \sigma ^ { i } ) ^ { \mu } G _ { m + r } ^ { \mu \nu } + ( 1 - \gamma ) m \left( \sigma ^ { i } \right) _ { p } ^ { \mu } Q _ { m + r } ^ { \mu \nu } } } \\ { { \left[ A _ { m } ^ { - i } , G _ { r } ^ { w \mu } \right] = \frac { 1 } { 2 } ( \sigma ^ { i } ) ^ { \nu } G _ { m + r } ^ { m \neq { - } } - \gamma m \left( \sigma ^ { i } \right) _ { p } ^ { \nu } Q _ { m + r } ^ { \mu \nu } . } } \end{array}
$$

$$
\begin{array} { r l } & { \{ Q _ { r } ^ { \mu \nu } , G _ { s } ^ { \rho \tau } \} = 2 \epsilon ^ { \mu \pi } ( \sigma _ { i } ) _ { \pi } ^ { \rho } \epsilon ^ { \nu \tau } A _ { r + s } ^ { + , i } - 2 \epsilon ^ { \nu \pi } ( \sigma _ { i } ) _ { \pi } ^ { \tau } \epsilon ^ { \mu \rho } A _ { r + s } ^ { - , i } + 2 \mathrm { i } \epsilon ^ { \mu \rho } \epsilon ^ { \nu \tau } U _ { r + s } } \\ & { \{ G _ { r } ^ { \mu \nu } , G _ { s } ^ { \rho \tau } \} = - \frac { 2 c } { 3 } \epsilon ^ { \mu \rho } \epsilon ^ { \nu \tau } ( r ^ { 2 } - \frac { 1 } { 4 } ) \delta _ { r , - s } - 4 \epsilon ^ { \mu \rho } \epsilon ^ { \nu \tau } L _ { r + s }  } \\ & { \qquad + 4 ( r - s ) ( \gamma \epsilon ^ { \mu \pi } ( \sigma ^ { i } ) _ { \pi } ^ { \rho } \epsilon ^ { \nu \tau } A _ { r + s } ^ { + , i } + ( 1 - \gamma ) \epsilon ^ { \nu \pi } ( \sigma ^ { i } ) _ { \pi } ^ { \tau } \epsilon ^ { \mu \rho } A _ { r + s } ^ { - , i } ) . } \end{array}
$$

In terms of the levels of the two $\mathfrak { s u } ( 2 )$ algebras, we have

$$
\gamma = \frac { k ^ { - } } { k ^ { + } + k ^ { - } } , \qquad c = \frac { 6 k ^ { + } k ^ { - } } { k ^ { + } + k ^ { - } } .
$$

Here，greek indices $\mu , \nu , \ldots$ indices are spinor indices and get as usual raised and lowered by the epsilon symbol $\epsilon _ { \mu \nu }$ , which we have indicated explicitly. Indices $i , j , \dots$ are adjoint indices of $\mathfrak { s u } ( 2 )$ .Finally, $\boldsymbol { \sigma ^ { i } }$ denotes the Pauli matrices, i.e. the twodimensional spinor representation of $\mathfrak { s u } ( 2 )$

# A.1 The BPS Bound

The highest weight representations of the large superconformal ${ \mathcal N } = 4$ algebra $A _ { \gamma }$ are characterized by $( h , j ^ { \pm } , u )$ ，where $h$ is the conformal dimension of the highest weight states，while $j ^ { \pm }$ are the spins of the two affine $\mathfrak { s u } ( 2 )$ algebras,and $u$ denotes the （20 $\mathfrak { u } ( 1 )$ charge, i.e. the eigenvalue under $U _ { 0 }$ . Unitarity implies that $\begin{array} { r } { j ^ { \pm } \le \frac { k ^ { \pm } } { 2 } } \end{array}$ .However, as explained in [29], unitarity actually requires that

$$
j ^ { \pm } \le { \frac { k ^ { \pm } - 1 } { 2 } } .
$$

The BPS bound takes the form [29, 53, 54]

$$
h \geq \frac { 1 } { k ^ { + } + k ^ { - } } \left[ k ^ { + } j ^ { - } + k ^ { - } j ^ { + } + u ^ { 2 } + ( j ^ { + } - j ^ { - } ) ^ { 2 } \right] .
$$

Note that this bound differs from the the corresponding BPS bound of the wedge algebra $D ( 2 , 1 | \alpha )$ , whose BPS bound is [6,7]

$$
h \geq \left[ \frac { 1 } { 1 + \alpha } j ^ { - } + \frac { \alpha } { 1 + \alpha } j ^ { + } \right] .
$$

Indeed,apart from the additional $u ^ { 2 }$ term there is in particular also the $( j ^ { + } - j ^ { - } ) ^ { 2 }$ term. If we denote the corresponding representation by $[ j ^ { + } , j ^ { - } , u ]$ then it only satisfies the BPS bound of $D ( 2 , 1 | \alpha )$ if $u = 0$ and $j ^ { + } = j ^ { - }$ . On the other hand,if this is the case, the BPS representation $[ j ^ { + } , j ^ { - } , u ]$ of the linear $A _ { \gamma }$ algebra contains actually two BPS representations of $D ( 2 , 1 | \alpha )$ （20

$$
\begin{array} { r } { [ j , j , u = 0 ] _ { S } = [ j , j ] _ { s } \oplus [ j + \frac { 1 } { 2 } , j \oplus \frac { 1 } { 2 } ] _ { s } \oplus \mathrm { ~ n o n } { \mathrm { - B P S ~ r e p s ~ o f ~ } } D ( 2 , 1 | \alpha ) ~ . } \end{array}
$$

This is basically a consequence of the fact that in addition to the four supercharges (that also appear in $D ( 2 , 1 | \alpha ) )$ ， $A _ { \gamma }$ also contains four free fermions. In particular, every BPS representation of $A _ { \gamma }$ contains always two BPS states whose spins differ by $\begin{array} { r } { j ^ { \pm \prime } = j ^ { \pm } + \frac { 1 } { 2 } } \end{array}$

# A.2 The $\mathbf { \mathcal { N } } = \mathbf { 2 } \mathbf { \Psi }$ subalgebra

The large superconformal ${ \mathcal N } = 4$ algebra contains a superconformal ${ \mathcal N } = 2$ algebra [7]. Set

$$
J = 2 i ( \gamma A ^ { + , 3 } + ( 1 - \gamma ) A ^ { - , 3 } ) ,
$$

this constitutes together with $G ^ { + + }$ ， $G ^ { -- }$ and the energy-momentum tensor an ${ \mathcal { N } } = 2$ （20 algebra. Chiral primaries of this $\mathcal { N } = 2$ algebra correspond to BPS states of the large $\mathcal { N } = 4$ algebra of the form $( j , j , u = 0 ) _ { S }$ . Moreover, by (A.15)，every short representation of the form $[ j , j , u = 0 ] _ { S }$ of the large $\mathcal { N } = 4$ algebra contains two chiral primaries of the ${ \mathcal N } = 2$ subalgebra.

# B Superconformal affine algebras

In this appendix we review briefly the structure of superconformal affine algebras. We will only be interested in two examples,the algebra ${ \mathfrak { s l } } ( 2 , \mathbb { R } ) _ { k } ^ { ( 1 ) }$ and the algebra （204号 ${ \mathfrak { s u } } ( 2 ) _ { k ^ { \prime } } ^ { ( 1 ) }$ .For the former we choose a basis as

$$
\begin{array} { l l } { { \mathcal { I } _ { m } ^ { + } , \mathcal { I } _ { n } ^ { - } \Big ] = - 2 \mathcal { I } _ { m + n } ^ { 3 } + k m \delta _ { m , - n } } } & { { \Big [ \mathcal { I } _ { m } ^ { 3 } , \mathcal { I } _ { n } ^ { \pm } \Big ] = \pm \mathcal { I } _ { m + n } ^ { \pm } \qquad \Big [ \mathcal { I } _ { m } ^ { 3 } , \mathcal { I } _ { n } ^ { 3 } \Big ] = - \displaystyle \frac { k } { 2 } m \delta _ { m , - n } } } \\ { { \big [ \mathcal { I } _ { m } ^ { \pm } , \psi _ { r } ^ { 3 } \big ] = \mp \psi _ { m + r } ^ { \pm } } } & { { \big [ \mathcal { I } _ { m } ^ { 3 } , \psi _ { r } ^ { \pm } \big ] = \pm \psi _ { m + r } ^ { \pm } \qquad \big [ \mathcal { I } _ { m } ^ { \pm } , \psi _ { r } ^ { \mp } \big ] = \mp 2 \psi _ { m + r } ^ { 3 } } } \\ { { \psi _ { r } ^ { + } , \psi _ { s } ^ { - } \big \} = k \delta _ { r , - s } } } & { { \big \{ \psi _ { r } ^ { 3 } , \psi _ { s } ^ { 3 } \big \} = - \displaystyle \frac { k } { 2 } \delta _ { r , - s } . } } \end{array}
$$

On the other hand, the affine ${ \mathfrak { s u } } ( 2 ) _ { k ^ { \prime } } ^ { ( 1 ) }$ generators satisfy

$$
\begin{array} { l r c l } { { \displaystyle \left[ K _ { m } ^ { + } , K _ { n } ^ { - } \right] = 2 K _ { m + n } ^ { 3 } + k ^ { \prime } m \delta _ { m , - n } } } & { { \displaystyle \left[ K _ { m } ^ { 3 } , K _ { n } ^ { \pm } \right] = \pm K _ { m + n } ^ { \pm } } } & { { \displaystyle \left[ K _ { m } ^ { 3 } , K _ { n } ^ { 3 } \right] = \frac { k ^ { \prime } } { 2 } m \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m } } } \\ { { \displaystyle \left[ K _ { m } ^ { \pm } , \chi _ { r } ^ { 3 } \right] = \mp \chi _ { m + r } ^ { \pm } } } & { { \displaystyle \left[ K _ { m } ^ { 3 } , \chi _ { r } ^ { 3 } \right] = \pm \chi _ { m + r } ^ { \pm } } } & { { \displaystyle \left[ K _ { m } ^ { \pm } , \chi _ { r } ^ { \mp } \right] = \pm 2 \chi _ { m + r } ^ { 3 } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { m , - n } \delta _ { - m } \delta _ { - m , - n } \delta _ { - m } \delta _ { - m , - n } \delta _ { - m } \delta _ { - m , - n } \delta _ { - m } \delta _ { - m , - n } \delta _ { - m } \delta _ { - m , - n } \delta _ { - m } \delta _ { - m } \delta _ { - m } \delta _ { - m } . } } \\ { { \displaystyle \left\{ \chi _ { r } ^ { + } , \chi _ { s } ^ { - } \right\} = k ^ { \prime } \delta _ { r , - s } } } &   \displaystyle \left\{ \chi _ { r } ^ { 3 } , \chi _ { s } ^ { 3 } \right\} = \frac { k ^ { \prime } } { 2 } \delta _ { r , - s } \delta _ { m , - n } \delta _ { - m } \delta _ { - m } \delta _ { - m } \delta _ { - m } \delta _ { - m } \delta _ { - m } \delta _ { - m } \delta _ { - m } \delta _ { - m } \delta _ { - m } \delta _ { - m } \delta _ { - m } \end{array}
$$

In each case it is possible to decouple the fermions from the bosons,i.e. to redefine the bosonic generators by bilinears in the fermions so that they commute with the fermions. For ${ \mathfrak { s l } } ( 2 , \mathbb { R } ) _ { k } ^ { ( 1 ) }$ , the resulting decoupled bosonic algebra then has level $k + 2$ ， while for ${ \mathfrak { s u } } ( 2 ) _ { k ^ { \prime } } ^ { ( 1 ) }$ the level of the decoupled bosonic algebra is $k ^ { \prime } - 2$ ：

# B.1 Spectral flow automorphism

For the description of the spectrally flowed representations the existence of a family of automorphisms is important. For any $w \in \mathbb { Z }$ ， we define new generators as

$$
\begin{array} { r l r l } & { \hat { \mathcal { T } } _ { n } ^ { \pm } = \mathcal { I } _ { n \mp w } ^ { \pm } } & & { \hat { K } _ { n } ^ { \pm } = K _ { n \pm w } ^ { \pm } } \\ & { \hat { \mathcal { T } } _ { n } ^ { 3 } = \mathcal { I } _ { n } ^ { 3 } + \frac { k } { 2 } w \delta _ { n , 0 } } & & { \hat { K } _ { n } ^ { 3 } = K _ { n } ^ { 3 } + \frac { k ^ { \prime } } { 2 } w \delta _ { n , 0 } } \\ & { \hat { L } _ { n } ^ { \mathrm { g t } } = L _ { n } ^ { \mathrm { g t } } - w \mathcal { I } _ { n } ^ { 3 } - \frac { k } { 4 } w ^ { 2 } \delta _ { n , 0 } } & & { \hat { L } _ { n } ^ { \mathrm { g t } } = L _ { n } ^ { \mathrm { g t } } + w K _ { n } ^ { 3 } + \frac { k ^ { \prime } } { 4 } w ^ { 2 } \delta _ { n , 0 } } \\ & { \hat { \psi } _ { r } ^ { 3 } = \psi _ { r } ^ { 3 } } & & { \hat { \chi } _ { r } ^ { 3 } = \chi _ { r } ^ { 3 } } \\ & { \hat { \psi } _ { r } ^ { \pm } = \psi _ { r \mp w } ^ { \pm } } & & { \hat { \chi } _ { r } ^ { \pm } = \chi _ { r \pm w } ^ { \pm } \ . } \end{array}
$$

One verifies easily that these new generators also satisfy the commutation relations of the superconformal affine algebra, i.e. eqs.(B.1) and (B.2) above. In addition, they satisfy the relations

$$
[ L _ { m } ^ { \mathfrak { s l } } , \mathcal { T } _ { n } ^ { a } ] = - n \mathcal { T } _ { m + n } ^ { a } \ , \qquad [ L _ { m } ^ { \mathfrak { s u } } , K _ { n } ^ { a } ] = - n K _ { m + n } ^ { a } \ ,
$$

and similarly for the fermions,

$$
\begin{array} { r l r } { \left[ L _ { m } ^ { \mathfrak { s l } } , \psi _ { n } ^ { a } \right] = \left( - \frac { m } { 2 } - n \right) \psi _ { m + n } ^ { a } , } & { { } } & { \left[ L _ { m } ^ { \mathfrak { s l } } , \chi _ { n } ^ { a } \right] = \left( - \frac { m } { 2 } - n \right) \chi _ { m + n } ^ { a } . } \end{array}
$$

# C $\scriptstyle { S _ { \kappa } }$ theory and its chiral algebra

Since the $S _ { \kappa }$ algebra,i.e. the chiral algebra of the $S _ { \kappa }$ theory, will play a central role for the remainder of the paper, we shall briefly review its structure here. The superconformal affne algebra $\mathfrak { s u } ( 2 ) _ { \kappa + 2 } ^ { ( 1 ) }$ is generated bybosonic generators (that defie an affine $\mathfrak { s u } ( 2 )$ algebra at level $\kappa + 2$ ),as well as free fermions in the adjoint representation of $\mathfrak { s u } ( 2 )$ , see Appendix B for an explicit description. As is also mentioned there, it is possible to decouple the fermions from the bosons, and the resulting (decoupled) generators (that we shall denote by $J ^ { i }$ with $i = 1 , 2 , 3$ ） then have level $\kappa$ . The $\mathfrak { u } ( 1 ) ^ { ( 1 ) }$ （20 algebra, on the other hand, consists of a single free boson that we shall denote by $\partial \phi$ ， as well as a single free fermion. (For $\mathfrak { u } ( 1 )$ ， there is no need to decouple the fermion since the commutators in the adjoint representation vanish anyway.） Together with the three fermions from $\mathfrak { s u } ( 2 ) ^ { ( 1 ) }$ we therefore have altogether four decoupled free fermions that we denote by $\psi ^ { \mu \nu }$ with $\mu , \nu = 1 , 2$ being bispinor indices as explained in Appendix A. The commutation relations of the associated modes are then

$$
\begin{array} { c } { { \left[ J _ { n } ^ { i } , J _ { m } ^ { j } \right] = \epsilon _ { i j l } J _ { m + n } ^ { l } + \kappa m \delta ^ { i j } \delta _ { m , - n } } } \\ { { \left[ \alpha _ { m } , \alpha _ { n } \right] = m \delta _ { m , - n } } } \\ { { \{ \psi _ { r } ^ { \mu \nu } , \psi _ { s } ^ { \rho \tau } \} = \epsilon ^ { \mu \rho } \epsilon ^ { \nu \tau } \delta _ { r , - s } ~ , } } \end{array}
$$

where we have denoted the modes of the free boson $\partial \phi$ by $\alpha _ { m }$ . The bilinears in the fermions generate the current algebra ${ \mathfrak { s o } } ( 4 ) _ { 1 } \cong { \mathfrak { s u } } ( 2 ) _ { 1 } \oplus { \mathfrak { s u } } ( 2 ) _ { 1 }$ , with respect to which they transform in the representation ${ \bf 4 } = ( { \bf 2 } , { \bf 2 } )$ . The $S _ { \kappa }$ algebra contains the large （20 ${ \mathcal N } = 4$ superconformal algebra (whose definition we spell out, for the convenience of the reader, in Appendix A),where the associated fields are defined as [14]

$$
\begin{array} { r l } & { L _ { m } = \frac { 1 } { 2 } ( \alpha \alpha ) _ { m } + \frac { ( \beta ^ { \prime } , \beta ^ { \prime } ) _ { \sigma } } { 8 + 2 } - \frac { 1 } { 4 } c _ { \mu } \epsilon _ { \sigma } ( \psi ^ { \mu } \psi ^ { \alpha } ) _ { \psi } ( \psi ^ { \alpha } ) _ { m } } \\ & { A _ { m } ^ { + , i } = \frac { 1 } { 8 } \epsilon _ { \mu } \epsilon ( \psi ^ { i } ) _ { \mu } ^ { \dagger } \epsilon _ { \sigma } ( \psi ^ { \alpha \mu } ) _ { \psi } ( \psi ^ { \alpha } ) _ { m } } \\ & { A _ { m } ^ { - i } = \frac { 1 } { 8 } \epsilon _ { \mu } \epsilon ( \psi ^ { i } ) _ { \mu } ^ { \dagger } \epsilon _ { \sigma } ( \psi ^ { \alpha \mu } ) _ { m } + J _ { m } ^ { + } } \\ & { G _ { \nu } ^ { \mu , \alpha } = \mathrm { i } ( \alpha \omega ^ { \alpha } ) _ { \nu } - \frac { 1 } { 8 } \sqrt { \frac { \gamma ^ { 2 } } { \kappa ^ { 2 } + 2 } } ( \alpha _ { \nu } ) _ { \rho } ^ { \mu } \epsilon ( A ^ { \nu } \psi ^ { \alpha } ) _ { \nu } + \frac { 2 } { 3 } \sqrt { \frac { \gamma ^ { 2 } } { \kappa ^ { 2 } + 2 } } ( \sigma _ { \nu , \mu } ^ { \gamma \mu } ( J ^ { \alpha \mu } ) _ { m } ) } \\ & { \quad \quad - \frac { 1 } { 8 } \sqrt { \frac { \gamma ^ { 2 } } { \kappa ^ { 2 } + 2 } } ( \alpha _ { \nu } ) _ { \rho } ^ { \mu } \epsilon ( A ^ { - \alpha } \psi ^ { \alpha \mu } ) _ { \gamma } } \\ & { U _ { m } = \sqrt { \frac { \gamma ^ { 4 } - 2 } { 2 } } \alpha _ { \alpha \alpha } } \\ & { Q _ { \nu } ^ { \mu , \alpha } = \sqrt { \frac { \gamma ^ { 6 } + 2 } { 2 } } \gamma _ { \mu } ^ { \mu } . } \end{array}
$$

In this realization, the two affine $\mathfrak { s u } ( 2 )$ algebras appear at level

$$
Q _ { 5 } ^ { + } = k ^ { + } = 1 \qquad \mathrm { a n d } \qquad Q _ { 5 } ^ { - } = k ^ { - } = \kappa + 1 \ .
$$

The central charge of the $S _ { \kappa }$ theory is then

$$
c ( S _ { \kappa } ) = \frac { 3 \kappa } { \kappa + 2 } + 3 = 6 \frac { \kappa + 1 } { \kappa + 2 } \ .
$$

It is obvious that the symmetric orbifold (2.12) inherits the large ${ \mathcal N } = 4$ superconformal symmetry from its seed theory, and that its levels are $( Q _ { 1 } Q _ { 5 } ^ { + } , Q _ { 1 } Q _ { 5 } ^ { - } )$ .It therefore has the correct charges to match the expectations from [5, 7].

# D Character derivation of the twisted sector spectrum

In this appendix, we derive the claims made about twist sectors of the symmetric product orbifold of $S _ { \kappa }$ in the main text. The partition function of a single $S _ { \kappa }$ -theory reads

$$
\begin{array} { r l r } {  { Z ( q , y , z ) = Z _ { \mathrm { b o s } } ( q ) Z _ { \mathrm { s u } ( 2 ) _ { \kappa } } ( q , z ) \Big | q ^ { - \frac { 1 } { 1 2 } } \prod _ { m = 1 } ^ { \infty } ( 1 + y ^ { \frac { 1 } { 2 } } z ^ { \frac { 1 } { 2 } } q ^ { m - \frac { 1 } { 2 } } ) ( 1 + y ^ { - \frac { 1 } { 2 } } z ^ { \frac { 1 } { 2 } } q ^ { m - \frac { 1 } { 2 } } ) } } \\ & { } & { \times ( 1 + y ^ { \frac { 1 } { 2 } } z ^ { - \frac { 1 } { 2 } } q ^ { m - \frac { 1 } { 2 } } ) ( 1 + y ^ { - \frac { 1 } { 2 } } z ^ { - \frac { 1 } { 2 } } q ^ { m - \frac { 1 } { 2 } } ) | ^ { 2 } } \\ & { } & { = Z _ { \mathrm { b o s } } ( q ) Z _ { \mathrm { s u } ( 2 ) _ { \kappa } } ( q , z ) | \frac { \vartheta _ { 3 } ( \frac { 1 } { 2 } ( \xi + \zeta ) ; \tau ) \vartheta _ { 3 } ( \frac { 1 } { 2 } ( \xi - \zeta ) ; \tau ) } { \eta ( \tau ) ^ { 2 } } | ^ { 2 } . } \end{array}
$$

Here, $Z _ { \mathrm { b o s } } ( q )$ and $\boldsymbol { Z } _ { \mathfrak { s u ( 2 ) _ { K } } }$ are the partition functions of the free boson and of ${ \mathfrak { s u } } ( 2 ) _ { \kappa }$ ， respectively. We shall not need their precise forms，only the fact that they are modular invariant. Finally, $y = e ^ { 2 \pi i \xi }$ and $z = e ^ { 2 \pi i \zeta }$ are the chemical potentials for the two $\mathfrak { s u } ( 2 )$ 's.

# D.1 Odd twist

Consider an odd cyclic twist of length $n$ . Then

$$
\operatorname * { 1 } _ { ( 1 \cdots n ) } = Z ( q ^ { n } , y ^ { n } , z ^ { n } ) \left( Z ( q , y , z ) \right) ^ { N - n } .
$$

We now perform an S-modular transformation to relate this to the sector where the boundary conditions along the two cycles of the torus are interchanged. Omitting phase factors obtained from the Jacobi form transformations, this leads to

$$
( 1 \cdot \cdot \cdot n ) \Bigl [ \prod _ { 1 } = Z \bigl ( q ^ { \frac { 1 } { n } } , y , z \bigr ) \bigl ( Z ( q , y , z ) \bigr ) ^ { N - n } \ ,
$$

where we have used the modular properties of the theta functions. Thus, we can interpret the states as generated by the usual operators, but fractionally moded. Furthermore, in order to determine the ground state energy we note that the leading term is $q ^ { - { \frac { c } { 2 4 n } } - { \frac { c } { 2 4 } } \left( N - n \right) }$ ，where $c$ is the central charge of $S _ { \kappa }$ . Since the total central charge of the symmetric orbifold is $c N$ ， the ground state energy relative to the vacuum is

$$
h = \frac { c } { 2 4 n } ( n ^ { 2 } - 1 ) \ .
$$

Furthermore, since in (D.4), $q ^ { \frac { 1 } { n } }$ instead of $q$ appears, the conformal weights are divided by a factor $n$ . This then yields eq. (3.6).

# D.2 Even twist

For even twist the story is more subtle. Combining an even number of fermions changes the statistics [33], so the character has an additional $( - 1 ) ^ { F }$ inserted. Thus, in this case

$$
\begin{array} { l } { { \displaystyle \prod _ { ( 1 \cdots n ) } = Z _ { \mathrm { b o s } } ( q ^ { n } ) Z _ { \mathrm { s u } ( 2 ) _ { \kappa } } ( q ^ { n } , z ^ { n } ) \left| \frac { \vartheta _ { 4 } ( \frac { n } { 2 } ( \xi + \zeta ) ; n \tau ) \vartheta _ { 4 } ( \frac { n } { 2 } ( \xi - \zeta ) ; n \tau ) } { \eta ( n \tau ) ^ { 2 } } \right| ^ { 2 } \left( Z ( q , y , z ) \right) ^ { N - n } , } } \end{array}
$$

where now different theta functions appear. Under a modular $S$ -transformation, $\vartheta _ { 4 }$ （20 transforms into $\vartheta _ { 2 }$ ，and we obtain

$$
{ \begin{array} { r l r } {  { ( 1 \cdots n ) \bigg [ \prod _ { 1 } } = Z _ { \mathrm { b o s } } ( q ^ { \frac { 1 } { n } } ) Z _ { \mathrm { s u ( 2 ) } _ { \kappa } } ( q ^ { \frac { 1 } { n } } , z ) | y ^ { \frac { 1 } { 2 } } + y ^ { - \frac { 1 } { 2 } } + z ^ { \frac { 1 } { 2 } } + z ^ { - \frac { 1 } { 2 } } | ^ { 2 } ( q \bar { q } ) ^ { \frac { 1 } { 6 n } } } } \\ & { } & { \times | \prod _ { m = 1 } ^ { \infty } ( 1 + y ^ { \frac { 1 } { 2 } } z ^ { \frac { 1 } { 2 } } q ^ { \frac { m } { n } } ) ( 1 + y ^ { \frac { 1 } { 2 } } z ^ { - \frac { 1 } { 2 } } q ^ { \frac { m } { n } } ) ( 1 + y ^ { - \frac { 1 } { 2 } } z ^ { \frac { 1 } { 2 } } q ^ { \frac { m } { n } } ) ( 1 + y ^ { - \frac { 1 } { 2 } } z ^ { - \frac { 1 } { 2 } } q ^ { \frac { m } { n } } ) | ^ { 2 } } \\ & { } & { \times ( Z ( q , y , z ) ) ^ { N - n } . } \end{array} 
$$

Thus,again the operators are fractionally moded. For the bosons, the analysis is unchanged relative to odd twist， whereas for the fermions, instead of the $q ^ { - \frac { 1 } { 1 2 n } }$ we now have $q ^ { \frac { 1 } { 6 n } }$ . Thus the ground state energy is in this case

$$
c = { \frac { c n } { 2 4 } } + { \frac { 1 } { 2 4 n } } \Big [ 4 - 1 - { \frac { 3 \kappa } { \kappa + 2 } } \Big ] = { \frac { c n } { 2 4 } } + { \frac { 1 } { 4 n ( \kappa + 2 ) } } ~ .
$$

Note that the last term is positive and goes away in the limit $\kappa  \infty$ , as is well-known for the case of $ { \mathbb { T } } ^ { 4 }$ . Since $\vartheta _ { 2 }$ appears in the twisted sector, the relevant representation has fermionic zero modes, and the ground states transform as $( \mathbf { 2 } , \mathbf { 1 } ) \oplus ( \mathbf { 1 } , \mathbf { 2 } )$ ,i.e. as the spinor representation of ${ \mathfrak { s o } } ( 4 )$ . The orbifold projection eliminates some of the ground states since the fermionic zero-modes are odd under the orbifold action. Combining left- and right-movers, the surviving states are then $\left[ ( { \bf 1 } , { \bf 2 } ) \otimes ( { \bf 1 } , { \bf 2 } ) \right] \oplus \left[ ( { \bf 2 } , { \bf 1 } ) \otimes ( { \bf 2 } , { \bf 1 } ) \right]$ (Since the orbifold acts symmetrically on left- and right-movers,the same should be the case for the orbifold projection in the twisted sectors.)

# E BPS states in the spectrally flowed NS sectors

In this appendix we will construct the BPS states, solving (4.23). As we explained above, the BPS states must come in pairs, i.e. to each BPS state in the R-sector, there must be a corresponding BPS state in the NS sector with spins shifted by $\pm \frac { 1 } { 2 }$ Starting from aR-sector BPS stateof subsection 4.4.1 characterized by $j ^ { \mathrm { R } }$ ， $j ^ { \mathrm { R } ^ { \pm } }$ 1， $j _ { 0 }$ ， （20 $j _ { 0 } ^ { \pm }$ ， $w$ and $w ^ { \pm }$ ， we can write down two canonical candidates for BPS states in the NS-sector, one with the spins shifted up by $\textstyle { \frac { 1 } { 2 } }$ , the other with the spins shifted down by $\textstyle { \frac { 1 } { 2 } }$ ：

(i) The following state has the spins shifted down by $\textstyle { \frac { 1 } { 2 } }$

$$
j ^ { \mathrm { N S } } = j ^ { \mathrm { R } } - \frac { 1 } { 2 } , \quad j ^ { \mathrm { N S } \pm } = j ^ { \mathrm { R } ^ { \pm } } - \frac { 1 } { 2 } .
$$

We can achieve this by setting $j _ { 0 }$ ， $j _ { 0 } ^ { \pm }$ ， $w$ and $w ^ { \pm }$ to the same values as in the R-sector. Furthermore,we set $\delta = 1$ ， $\delta ^ { + } = \delta ^ { - } = 0$ . The state has then the required quantum numbers. The mass shell condition (4.23) is satisfied, provided that

$$
w = w ^ { + } + w ^ { - } .
$$

Since we (implicitly） apply $w + w ^ { + } + w ^ { - } = 2 w$ fermions due to spectral flow and since $\delta = 1$ ， $\delta ^ { \pm } = 0$ ， we have an odd number of fermions altogether (as required by the GSO projection).

(ii) Similarly, we construct a state with spins shifted up by $\textstyle { \frac { 1 } { 2 } }$

$$
j ^ { \mathrm { N S } } = j ^ { \mathrm { R } } + \frac { 1 } { 2 } \ , \quad j ^ { \mathrm { N S ^ { \pm } } } = j ^ { \mathrm { R ^ { \pm } } } + \frac { 1 } { 2 } \ .
$$

Again, $j _ { 0 } , j _ { 0 } ^ { \pm }$ ， $w$ and $w ^ { \pm }$ take the same values as in the R-sector, but in this case we set $\delta = 0$ ， $\delta ^ { + } = \delta ^ { - } = 1$ . Then the mass shell condition is satisfied provided that

$$
w = w ^ { + } + w ^ { - } + 1 ~ .
$$

Again, the total number of fermions is odd (as must be the case in order to satisfy the GSO projection): there is an odd number of fermions because of the spectral flow ( $w + w ^ { + } + w ^ { - }$ is odd)，whereas now $\delta + \delta ^ { + } + \delta ^ { - } = 2$ ：

![](images/aaf059bdd585c1748dcf7d9a5bd330fdef4cb8e560a1823b4d449d47fa14b066.jpg)  
Figure 2. Distribution of states in the intervals (E.5) for the case of $k ^ { + } = 5$ ， $k ^ { - } = 3$ Solid markers indicate the boundary of an interval, dotted markers are multiples of ${ \scriptstyle { \frac { 1 } { 2 } } } k ^ { + }$ ， dashed markers are multiples of $\bar { \frac { 1 } { 2 } } k ^ { - }$ . One can clearly see that there is precisely one point where all markers meet and the following solid interval does not contain any other marker. Apart from this exception, every two solid markers enclose exactly one dotted or dashed marker. Hence either no marker meets or all three markers meet at one point.

We will explain below that for each R-sector BPS state either $w = w ^ { + } + w ^ { - }$ or $w = w ^ { + } + w ^ { - } + 1$ holds. As a consequence there is precisely one corresponding BPS state in the NS-sector to each BPS state in the R-sector. Depending on the arithmetic properties of the BPS state in the R-sector, (E.2) or (E.4) applies, which determines whether the R-sector BPS state is the highest weight state in the multiplet or the descendant.

We have performed an extensive search on the computer to confirm that there are no other BPS states in the NS-sector than those we have constructed in this manner. (This is,of course， required by supersymmetry.） However，in doing this analysis one has to be very careful since our description above is redundant. While the spectral flow in the ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ algebra leads to genuinely new representations, spectral flow in the two $\mathfrak { s u } ( 2 )$ algebras is just a convenient method to describe descendant states，and there are identifications. For example, the state $\begin{array} { r l r } {  { ( j _ { 0 } ^ { + } = \ \frac { k ^ { + } } { 2 } - 1 , \delta ^ { + } = } } \end{array}$ （204号 $1 , w ^ { + } = 0$ ） is equivalent to $( j _ { 0 } ^ { + } = 0 , \delta ^ { + } = 0 , w ^ { + } = 1 )$ ，and similarly for $j _ { 0 } ^ { - }$ . We can fix this ambiguity by choosing the $\delta$ variables to be either $( \delta , \delta ^ { + } , \delta ^ { - } ) = ( 1 , 0 , 0 )$ or $( \delta , \delta ^ { + } , \delta ^ { - } ) = ( 0 , 1 , 1 )$ ：

To determine whether the corresponding NS-sector state has the spin shifted up or down by $\textstyle { \frac { 1 } { 2 } }$ ， we make the following observation for the R-sector BPS states. Consider the following intervals for $j$

$$
( { \textstyle \frac { 1 } { 2 } } k , k ] ~ , ~ ( k , { \textstyle \frac { 3 } { 2 } } k ] ~ , ~ ( { \textstyle \frac { 3 } { 2 } } k , 2 k ] ~ , ~ . ~ . ~ .
$$

corresponding to $w = 1$ , 2, 3,.... Then each interval contains precisely one element of the set $\frac { k ^ { + } } { 2 } \mathbb { Z } _ { > 0 } \bigcup \frac { k ^ { - } } { 2 } \mathbb { Z } _ { > 0 }$ with oneexception.Ifthecorresponding state inthe set lies on the right edge of the interval, then the successive interval contains no state of the set. The exceptional case occurs if the spin is a multiple of $\scriptstyle { \frac { 1 } { 2 } } \ln ( k ^ { + } , k ^ { - } )$ ,i.e. if it is a multiple of both $\textstyle { \frac { k ^ { + } } { 2 } }$ and $\frac { k ^ { - } } { 2 }$ . This is illustrated in figure 2 for the case of $k ^ { + } = 5$ ， （20 $k ^ { - } = 3$ ：

In each fixed interval (E.5),to the left of the dotted or dashed marker we have （204号 $w = w ^ { + } + w ^ { - } + 1$ , while to the right of it we have $w = w ^ { + } + w ^ { - }$ — this just follows from the fact that the markers indicate exactly where $w ^ { + }$ (dotted), $w ^ { - }$ (dashed） or $w$ (solid) changes. So in between two solid markers, the spins in the NS-sector are shifted up by $\textstyle { \frac { 1 } { 2 } }$ below the point where the dotted or dashed marker occurs, while above that point they are shifted down. Furthermore, at the position of the dotted or dashed marker itself, both solutions exist, so the states whose $j$ is a multiple of $\textstyle { \frac { k ^ { + } } { 2 } }$ （20 or $\frac { k ^ { - } } { 2 }$ occur twice in the NS-sector. The only exception occurs if a dotted or dasher marker coincides with a solid one — then the two solutions have different values for （ $j$ ：

Similarly, below a solid marker, the spins are shifted down, above they are shifted up. So when a solid marker occurs, there are two BPS states missing in the NS-sector. Finally consider the case when all three markers coincide. Below this triple point, spins are shifted up, above they are shifted down, since all of $w$ ， $w ^ { + }$ and $w ^ { - }$ change by one unit. Hence in this case there are two NS-sector BPS states sitting at this triple point, and there is no gap occurring as at the other solid markers. In summary, the NS-sector BPS spectrum therefore reads

$$
\begin{array} { r l } & { \quad \quad \displaystyle \bigoplus _ { j \in \frac 1 2 \mathbb { Z } _ { \geq 0 } \setminus \left( \frac 1 2 \lfloor k \mathbb { Z } _ { \geq 0 } \rfloor \setminus \frac 1 2 \lfloor \cos ( k ^ { + } , k ^ { - } ) \mathbb { Z } _ { \geq 0 } \cup \left( \frac 1 2 \lfloor k \mathbb { Z } _ { \geq 0 } \rfloor + \frac 1 2 \right) \setminus \left( \frac 1 2 \lfloor \cos ( k ^ { + } , k ^ { - } ) \mathbb { Z } _ { \geq 0 } + \frac 1 2 \right) \right) } } \left( j , j , u = 0 \right) _ { S }  \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad j \in \frac { k ^ { + } } 2 \mathbb { Z } _ { > 0 } \cup \frac { k ^ { - } } 2 \mathbb { Z } _ { > 0 } } \end{array}
$$

Strictly speaking, this formula is only true for $k \geq 2$ ; for small values of $k ^ { \pm }$ there are some subtleties in the notation since then the intersection

$$
\frac { 1 } { 2 } \lfloor k \mathbb { Z } _ { \ge 0 } \rfloor \setminus \frac { 1 } { 2 } \mathrm { l c m } ( k ^ { + } , k ^ { - } ) \mathbb { Z } _ { \ge 0 } \cap \left( \frac { 1 } { 2 } \lfloor k \mathbb { Z } _ { \ge 0 } \rfloor + \frac { 1 } { 2 } \right) \setminus \left( \frac { 1 } { 2 } \mathrm { l c m } ( k ^ { + } , k ^ { - } ) \mathbb { Z } _ { \ge 0 } + \frac { 1 } { 2 } \right)
$$

may be non-empty and we have to remove these states. Morally speaking, they are then removed twice from the set of the first direct sum in (E.6).

# FNon-renormalization of the chiral ring

In this appendix, we show that the conformal weights of $\mathcal { N } = 2$ chiral primaries is stable under deformations of the theory. This is probably well-known， but we could not find a good reference in the literature and therefore include a short proof (in the spirit of [44-46l) for the convenience of the reader. In order to determine the change of conformal dimension, we need to calculate the two-point function of a chiral primary $\Phi _ { i } ^ { + }$ and an anti-chiral primary $\Phi _ { j } ^ { - }$

$$
\langle \Phi _ { i } ^ { + } ( z _ { 1 } ) \Phi _ { j } ^ { - } ( z _ { 2 } ) \rangle
$$

in conformal perturbation theory.9 These are the only relevant two-point functions, since the two-point function of two chiral primaries vanishes by conservation of the

$\mathfrak { u } ( 1 )$ -charge. By the (anti-)chirality condition, $\Phi _ { i } ^ { + }$ and $\Phi _ { j } ^ { - }$ must have equal conformal weights. First order conformal perturbation theory involves the correlation functions

$$
\langle ( G _ { - 1 / 2 } ^ { + } \cdot \Phi _ { 1 / 2 } ^ { - } ) ( z ) \Phi _ { i } ^ { + } ( z _ { 1 } ) \Phi _ { j } ^ { - } ( z _ { 2 } ) \rangle \ ,
$$

where $\Phi _ { 1 / 2 } ^ { - }$ is chiral primary with conformal weight $\textstyle { \frac { 1 } { 2 } }$ (the index $\textstyle { \frac { 1 } { 2 } }$ is not a mode number). Similarly, also terms with $^ +$ and $-$ interchanged are involved. However symmetry in chiral and anti-chiral components lets us restrict to this case. We now show that (F.2) vanishes. Writing

$$
( G _ { - 1 / 2 } ^ { + } \cdot \Phi _ { 1 / 2 } ^ { - } ) ( z ) = \oint _ { w = z } \frac { \mathrm { d } w } { 2 \pi i } \frac { w - z _ { 2 } } { z - z _ { 2 } } G ^ { + } ( w ) \Phi ^ { - } ( z )
$$

and inserting this into the correlator (F.2)，we can deform the contour such that it encircles $z _ { 1 }$ ， $z _ { 2 }$ and potentially infinity (with the opposite orientation). Since $G ^ { + } ( w ) \Phi _ { i } ^ { + } ( z _ { 1 } )$ is regular, the contour integral around $z _ { 1 }$ vanishes. Furthermore, we chose the factor in the integrand of (F.3) in such a way that the single pole at $z _ { 2 }$ （20 exactly cancels. Finally, there is no contribution from infinity since

$$
\begin{array} { r } { \oint _ { w = z } \frac { d w } { 2 \pi i } \frac { w - z _ { 2 } } { z - z _ { 2 } } G ^ { + } ( w ) = \oint _ { w = z } \frac { d w } { 2 \pi i } \frac { w - z _ { 2 } } { z - z _ { 2 } } \sum _ { r } G _ { r } ^ { + } w ^ { - r - 3 / 2 } } \\ { = \frac { 1 } { z - z _ { 2 } } G _ { 1 / 2 } ^ { + } - \frac { z _ { 2 } } { z - z _ { 2 } } G _ { - 1 / 2 } ^ { + } ~ , } \end{array}
$$

and hence,inside (F.2)，allthe modesof $G _ { - 1 / 2 } ^ { + }$ annihilate the in-vacuum $\langle 0 |$ at infinity. Thus, (F.2) vanishes.

This shows that the derivative of (F.1） vanishes at every smooth point in the moduli space and thus the conformal weights of the chiral primaries are protected throughout the moduli space.

# References

[1] J.R. David, G. Mandal, and S.R. Wadia,“Microscopic formulation of black holes in string theory,”Phys.Rept.369 (2002) 549 [arXiv:hep-th/0203048].   
[2] M.R.Gaberdiel and I. Kirsch,“Worldsheet correlators in AdS $^ 3$ /CFT $2$ ,” JHEP 0704 (2007) 050 [hep-th/0703001].   
[3] A. Dabholkar and A. Pakman, “Exact chiral ring of AdS $_ 3$ /CFT $2$ ,” Adv. Theor. Math.Phys.13(2009) no.2, 409 [hep-th/0703022].   
[4] J. de Boer,“Large N eliptic genus and AdS / CFT correspondence,” JHEP 9905 (1999)017 [hep-th/9812240].   
[5] S.Elitzur, O.Feinerman,A. Giveon and D.Tsabar,“String theory on （204号 $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ ,”Phys. Lett.B 449 (1999) 180 [hep-th/9811245].   
[6] J. de Boer,A. Pasquinucci and K. Skenderis,“AdS / CFT dualities involving large 2-D N=4 superconformal symmetry,” Adv. Theor. Math. Phys. 3 (1999） 577 [arXiv:hep-th/9904073].   
[7] S. Gukov, E. Martinec, G.W. Moore and A. Strominger,“The Search for a holographic dual to A $\mathrm { { 1 S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } } }$ ,” Adv. Theor. Math. Phys. 9 (2005) 435 [hep-th/0403090].   
[8] M.R. Gaberdiel and R. Gopakumar,“Large ${ \mathcal N } = 4$ holography,” arXiv:1305.4181 [hep-th].   
[9] M.R. Gaberdiel and R. Gopakumar,“Higher Spins & Strings,” JHEP 1411 (2014) 044 [arXiv:1406.6103 [hep-th]].   
[10] M. Baggio,M.R.Gaberdiel and C.Peng,“Higher spins in the symmetric orbifold of K3,”Phys.Rev. D 92 (2015) 026007 [arXiv:1504.00926 [hep-th]].   
[11] N. Seiberg and E. Witten, “The D1 / D5 system and singular CFT,” JHEP 9904 (1999)017 [hep-th/9903224].   
[12] L. Eberhardt, M.R. Gaberdiel, R. Gopakumar and W. Li,“BPS spectrum on AdS $_ 3 \times$ S $^ 3 \times$ S $^ 3 \times$ S1,” JHEP 1703 (2017) 124 [arXiv:1701.03552 [hep-th]].   
[13] E. Witten, “Supersymmetric index of three-dimensional gauge theory,” In $^ *$ Shifman, M.A.(ed.): The many faces of the superworld $*$ 156-184 hep-th/9903005.   
[14] A. Sevrin, W. Troost and A. Van Proeyen,“Superconformal Algebras in Two-Dimensions with N=4,” Phys. Lett.B 208(1988) 447.   
[15] B.S. Acharya, J.P. Gauntlett and N. Kim, “Five-branes wrapped on associative three cycles,” Phys.Rev.D 63 (2001） 106003 [hep-th/0011190].   
[16] M. Schvellinger and T.A. Tran,“Supergravity duals of gauge feld theories from （204号 $\mathrm { S U } ( 2 ) \times \mathrm { U } ( 1 )$ gauged supergravity in five dimensions,” JHEP O106 (2001） 025 [hep-th/0105019].   
[17] J.P. Gauntlett, N. Kim, D. Martell and D. Waldram,“Five-branes wrapped on SLAG three cycles and related geometry,” JHEP 0111 (2001) 018 [hep-th/0110034].   
[18] J.M. Maldacena and H.S. Nastase, “The Supergravity dual of a theory with dynamical supersymmetry breaking,” JHEP 0109 (2001) 024 [hep-th/0105049].   
[19] P.M. Cowdall and P.K. Townsend, “Gauged supergravity vacua from intersecting branes,” Phys. Lett.B 429(1998) 281; Erratum: Phys. Lett.B 434(1998） 458 [hep-th/9801165].   
[20] H.J. Boonstra, B. Peeters and K. Skenderis,“Brane intersections,anti-de Sitter space-times and dual superconformal theories,” Nucl. Phys. B 533 (1998) 127 [hep-th/9803231].   
[21] J.P. Gauntlett, R.C. Myers and P.K. Townsend, “Supersymmetry of rotating branes,”Phys.Rev.D 59(1998) 025001 [hep-th/9809065].   
[22] O.Aharony, S.S. Gubser, J.M. Maldacena, H. Ooguri and Y. Oz,“Large N field theories, string theory and gravity,” Phys. Rept. 323 (2000) 183 [hep-th/9905111].   
[23] M.R. Douglas,“Branes within branes,” hep-th/9512077.   
[24] M. Bershadsky, C. Vafa and V. Sadov,“D-branes and topological feld theories," Nucl. Phys.B 463 (1996) 420 [hep-th/9511222].   
[25] J. Braam and J. Hurtubise,“Instantons on Hopf surfaces and monopoles on solid tori,”J. reine angew.Math 400（1989) 146-172.   
[26] R. Moraru, M. Verbitsky, “Stable bundles on hypercomplex surfaces,” Cent. Eur. J. Math. 8（2010) 327-337.   
[27] J. Michelson and A. Strominger,“The Geometry of (super)conformal quantum mechanics,” Commun. Math.Phys.213(2000) 1 [hep-th/9907191].   
[28] C. Vafa and E. Witten,“A Strong coupling test of S duality,” Nucl. Phys. B 431 (1994)3 [hep-th/9408074].   
[29] M. Gunaydin, J.L. Petersen,A. Taormina and A. Van Proeyen, “On the Unitary Representations of a Class of $N = 4$ Superconformal Algebras,” Nucl. Phys.B 322 (1989）402.   
[30] O.Aharony and E. Witten,“Anti-de Sitter space and the center of the gauge group,” JHEP 9811 (1998) 018 [hep-th/9807205].   
[31] R. Argurio,A. Giveon and A. Shomer,“Superstrings on AdS(3) and symmetric products,” JHEP 0012 （2000) 003 [hep-th/0009242].   
[32] J.M. Maldacena, G.W. Moore and A. Strominger,“Counting BPS black holes in toroidal Type II string theory,” hep-th/9903163.   
[33] O. Lunin and S. D. Mathur,“Three point functions for M(N)/ S(N) orbifolds with （204号 ${ \mathcal N } = 4$ supersymmetry,” Commun. Math. Phys. 227 (2002) 385 [hep-th/0103169].   
[34] J.M. Maldacena and A. Strominger,“AdS(3) black holes and a stringy exclusion principle,” JHEP 9812 （1998) 005 [hep-th/9804085].   
[35] J.M. Maldacena and H. Ooguri, “Strings in AdS(3) and SL(2,R) WZW model 1.: The Spectrum,” J. Math. Phys. 42(2001) 2929 [hep-th/0001053].   
[36] J.M. Maldacena, H. Ooguri and J. Son,“Strings in AdS(3) and the SL(2,R) WZW model.Part 2. Euclidean black hole,” J.Math. Phys.42(2001） 2961 [hep-th/0005183].   
[37] J.M. Maldacena and H. Ooguri, “Strings in AdS(3) and the SL(2,R) WZW model. Part 3. Correlation functions,” Phys. Rev. D 65 (2002） 106006 [hep-th/0111180].   
[38] K. Ferreira, M.R. Gaberdiel and J. I. Jottar,“Higher spins on AdS $^ 3$ from the worldsheet,” arXiv:1704.08667 [hep-th].   
[39] J.M. Evans,M.R. Gaberdiel and M.J. Perry, “The no ghost theorem for AdS(3) and the stringy exclusion principle,” Nucl. Phys.B 535 (1998) 152 [hep-th/9806024].   
[40] S. Hwang,“No ghost theorem for SU(1,1) string theories,” Nucl. Phys. B 354 (1991 100.   
[41] M. Henningson, S. Hwang, P. Roberts and B. Sundborg,“Modular invariance of SU(1,1) strings,” Phys. Lett. B 267(1991) 350.   
[42] S. Raju, “Counting giant gravitons in AdS(3),” Phys. Rev. D 77 (2008) 046012 [arXiv:0709.1171 [hep-th]].   
[43] J. de Boer,“Six-dimensional supergravity on $\mathrm { S ^ { 3 } \times A d S _ { 3 } }$ and 2-D conformal field theory,” Nucl. Phys.B 548(1999) 139 [hep-th/9806104].   
[44] L.J. Dixon， “Some World Sheet Properties Of Superstring Compactifications, On Orbifolds And Otherwise,” PUPT-1074, C87-06-29.1.   
[45] J.de Boer, J. Manschot,K. Papadodimas and E. Verlinde,“The Chiral ring of AdS(3)/CFT(2） and the attractor mechanism,” JHEP 0903 (2009） 030 [arXiv:0809.0507 [hep-th]].   
[46] M. Baggio, J. de Boer and K. Papadodimas,“A non-renormalization theorem for chiral primary 3-point functions,” JHEP 1207 (2012) 137 [arXiv:1203.1036 [hep-th]].   
[47] M. Baggio, O. Ohlsson Sax,A. Sfondrini, B. Stefanski and A. Torrielli,“Protected string spectrum in AdS $^ 3$ /CFT $^ 2$ from worldsheet integrability,” JHEP 1704(2017) 091 [arXiv:1701.03501 [hep-th]].   
[48] S.Gukov, E. Martinec, G.W. Moore and A. Strominger, “An Index for 2-D field theories with large N = 4 superconformal symmetry,” hep-th/0404023.   
[49] R. Dijkgraaf, “Fields, strings, matrices and symmetric products,” hep-th/9912104.   
[50] R. Dijkgraaf, G.W. Moore, E.P. Verlinde and H.L. Verlinde,“Elliptic genera of symmetric products and second quantized strings,” Commun. Math. Phys.185 (1997）197 [hep-th/9608096].   
[51] W. Soergel and L. Gottsche,“Perverse sheaves and the cohomology of Hilbert schemes of smooth algebraic surfaces.",Math. Ann. 296 (1993) 235.   
[52] D. Tong,“The holographic dual of $\mathrm { A d S _ { 3 } \times S ^ { 3 } \times S ^ { 3 } \times S ^ { 1 } }$ ,” JHEP 1404 (2014） 193 [arXiv:1402.5135 [hep-th]].   
[53] J.L. Petersen and A. Taormina,“Characters of the $N = 4$ Superconformal Algebra With Two Central Extensions,” Nucl. Phys. B 331 (1990) 556.   
[54] J.L. Petersen and A. Taormina, “Characters of the $N = 4$ Superconformal Algebra With Two Central Extensions: 2. Massless Representations,” Nucl. Phys. B 333 (1990) 833.