# Two-Loop SL(2) Form Factors and Maximal Transcendentality

Florian Loebbert $\mathbf { a }$ ， Christoph Sieg $\mathbf { a } , \mathbf { b }$ Matthias Wilhelm $\mathbf { a } , \mathbf { b } , \mathbf { c }$ ， Gang Yang ${ \bf d , a }$

（204号 $a$ Institut fir Physik, Humboldt-Universitat zu Berlin, Zum Groβen Windkanal 6, 12489 Berlin, Germany （20 $b$ Institut fir Mathematik, Humboldt-Universitat zu Berlin, Zum Groβen Windkanal 6, 12489 Berlin, Germany （204号 $c$ Niels Bohr Institute, Copenhagen University, Blegdamsvej 17, 2100 Copenhagen O, Denmark （204号 $d$ CAS Key Laboratory of Theoretical Physics, Institute of Theoretical Physics, Chinese Academy of Sciences, Beijing 100190, China

loebbert@physik.hu-berlin.de，csieg@physik.hu-berlin.de, matthias.wilhelm@nbi.ku.dk，yangg@itp.ac.cn

# Abstract

Form factors of composite operators in the SL(2） sector of $\mathcal { N } = 4$ SYM theory are studied up to two loops via the on-shell unitarity method. The non-compactness of this subsector implies the novel feature and technical challenge of an unlimited number of loop momenta in the integrand's numerator. At one loop,we derive the full minimal form factor to all orders in the dimensional regularisation parameter. At two loops, we construct the complete integrand for composite operators with an arbitrary number of covariant derivatives,and we obtain the remainder functions as well as the dilatation operator for composite operators with up to three covariant derivatives.The remainder functions reveal curious patterns suggesting a hidden maximal uniform transcendentality for the full form factor. Finally,we speculate about an extension of these patterns to QCD.

Contents

1 Introduction and summary 2

2Tree level 5

3One loop 7

3.1 Unitarity construction 7   
3.2 Dilatation operator 10   
3.3 Finite terms 11

4 Two loops 12

4.1 Unitarity construction 12   
4.2 Dilatation operator 15   
4.3 Remainders 18

5 Conclusion and outlook 22

A Explicit one-loop integral 24   
B Remainder densities 27

# 1Introduction and summary

Recent years have seen increasing interest in the study of form factors. In particular, $\mathcal { N } = 4$ （204号 super Yang-Mils (SYM) theory in four spacetime dimensions furnishes a rich setting for studying their properties. Form factors in $\mathcal { N } = 4$ SYM theory were initially investigated in 1985 [1]. Only recently, this subject was reconsidered, first at strong coupling [2, 3] and then at weak coupling [4, 5],and has subsequently aroused a lot more attention [6-36]. For recent reviews, see also the theses [37, 38].

An $n$ -point form factor describes the interaction of $n$ on-shell particles with momenta $p _ { i }$ （20 （ $p _ { i } ^ { 2 } = 0$ ） and a gauge-invariant local composite operator ${ \mathcal { O } } ( x )$ . Translated into momentum space, it takes the form

$$
\mathcal { F } _ { \mathcal { O } } ( 1 , . . . , n ; q ) = \int \mathrm { d } ^ { D } x \mathrm { e } ^ { - i q \cdot x } \langle 1 \cdot \cdot \cdot n | \mathcal { O } ( x ) | 0 \rangle ,
$$

where in this paper all form factors are considered to be colour-ordered super form factors and $q$ is off-shell ( $q ^ { 2 } \neq 0$ ). The motivation for studying form factors is multifold. Firstly, given the tremendous progress on on-shell techniques for scattering amplitudes (see e.g. [39- 41l), it is desirable to transfer these powerful methods to the computation of more general quantities. Form factors combine external on-shelland of-shell objects and are thus ideally suited for this purpose. Showing a rich structure, they also provide new testing grounds for the further development of on-shell techniques. Secondly, forming a bridge between on-shell and of-shell observables, the study of form factors should yield novel insights into the hidden symmetries of the underlying theory. Moreover, we should emphasise that form factors are interesting in their own right. Sudakov form factors, for instance,have played a key role in the understanding of infrared singularities in gauge theories [42-45]. Furthermore, they are closely related to Higgs production via gluon fusion as well as to Drell-Yan production in the standard model [46, 47].

The study of form factors of non-protected operators, as well as their connection to the spectral problem of planar $\mathcal { N } = 4$ SYM theory, was recently pushed forward in [19- 21, 28,32, 36]. In particular, the form factor remainder was made a central concept and it was shown how to extract the dilatation operator from form factor data. While previous studies mostly focused on individual operators or compact sectors, in this paper we consider operators in the non-compact SL(2） sector. The crucial new feature of non-compactness brings technical challenges and reveals novel properties.

Operators in the $\mathrm { S L } ( 2 )$ sector of $\mathcal { N } = 4$ SYM theory involve a single type of complex scalar $X$ and an arbitrary number of insertions of covariant derivatives D $\mu$ projected onto a lightlike vector $\tau ^ { \mu }$ ：

$$
\mathcal { O } _ { \vec { n } } = \mathrm { t r } \left[ \prod _ { j = 1 } ^ { L } \frac { ( \mathrm { D } ^ { + } ) ^ { n _ { j } } } { n _ { j } ! } X \right] , \qquad \mathrm { D } ^ { + } = \mathrm { D } ^ { \mu } \tau _ { \mu } .
$$

The length of the operator,i.e. the number of scalars $X$ , is denoted by $L$ . The configuration of a certain state is thus completely specified by the vector

$$
\vec { n } = \left( n _ { 1 } , \ldots , n _ { L } \right) ,
$$

which is identified with its images under cyclic permutations. We refer to the total number of covariant derivatives, $\begin{array} { r } { M = \sum _ { j = 1 } ^ { L } n _ { j } } \end{array}$ ,asthetotalspiorthetotalmagonumber.1In what follows,we will also speak of form factors in the SL(2) sector, meaning form factors with a composite operator from the above $\mathrm { S L } ( 2 )$ sector. Throughout this paper,we will mostly focus on minimal form factors,i.e. on the case where we have as many external fields $n$ as fields in the operator $L$ .2Moreover, we will restrict ourselves to the planar limit; the employed methods are also applicable for finite $N$ though.

At the technical level, the unlimited number of covariant derivatives in the SL(2) sector implies that the form factor integrand at fixed loop order involves arbitrarily high powers of loop momenta in the numerator. This is a completely new feature as compared to amplitude computations or to the previous studies of form factors with operators in compact sectors. As demonstrated in this paper,on-shel methods can still be efficiently applied in this case.

At one-loop order, we derive the full integrated form factor for all composite operators in the SL(2) sector. At two loops,we obtain the full integrand for an arbitrary magnon number using the unitarity method [49-51]. Solving the resulting integrals via traditional methods becomes more and more challenging for increasing magnon number. In this paper, we present the complete integrated result up to total spin three. We leave the solution for an arbitrary magnon number for future work. Besides universal IR divergences, the form factors contain UV divergences which alow us to extract the dilatation operator of the theory; our results (up to three magnons) match perfectly with the previously obtained data for the dilatation operator given in [52-54]. Despite the relatively small magnon numbers,we find very interesting patterns for the two-loop remainder function as well as for the finite terms at one-loop order. These observations indicate that form factors in （204号 ${ \mathcal N } = 4$ SYM theory have ‘hidden’ uniform maximal transcendentality for any operator, as will now be explained.

The first pattern to be noted is that the remainder function contains a universal piece of maximal transcendentality four， which is identical to the BPS result [17]. This was first observed in the compact SU(2) sector and conjectured to be a generic feature of the theory in [21]. So far, further support for this conjecture was already found in the ${ \mathrm { S U } } ( 2 | 3 )$ sector studied in [28]. In the SL(2) sector,also lower transcendental functions occur for remainders of non-protected operators, i.e. combinations of polylogarithms and constants such as $\zeta _ { 3 }$ and $\pi ^ { 2 }$ , whose total degree does not add up to four. While this is expected from the SU(2) and ${ \mathrm { S U } } ( 2 | 3 )$ sectors [21, 28],a curious observation of the present paper is that the functions of lower transcendentality come with coefficients composed of (generalised) harmonic numbers or factors of mi-ni, where mi,ni are magnon numbers as in (1.3). In particular, if also the latter are assgned an appropriate degree, the two-loop remainder is of uniform transcendentality four; similar structures can be seen in the one-loop form factor results. We refer to this assignment as hidden transcendentality.3

In order to illustrate the above idea, let us give the following list of exemplary expressions with a (formal) degree of transcendentality $k$ ：

<html><body><table><tr><td>1</td><td></td><td>Sk</td><td>Lik (ui)</td><td>logk（ui)</td><td>S(k) Snj</td><td>(mjn)</td><td>M</td><td></td><td>mn</td></tr></table></body></html>

Here, $u _ { i }$ and $v _ { i }$ represent kinematical variables, $m _ { i } , n _ { i }$ are magnon numbers as in (1.3), and the dimensional regularisation parameter $\varepsilon$ is assigned a transcendentality degree $- 1$ ， as normally done in the literature. The property of hidden uniform transcendentality can already be observed for the explicit expression for the two-loop dilatation operator given in [53]. The main observation made here is that this property appears to hold for the full form factor including functions with kinematical dependence, such as the remainder function. Note that in the case of the latter, we allow for generalisations of harmonic numbers or inverse powers of magnon numbers by inclusion of kinematical variables, such s $\begin{array} { r } { \sum _ { j = 1 } ^ { k } \frac { 1 } { j } \frac { ( 1 - u _ { i } ) ^ { j } } { v _ { i } ^ { j } } } \end{array}$ in thelistaoeAortaidexplaatiswellxpli will be given in section 4.3.

The above leads us to the following conjecture: The full form factor for any given operator in ${ \mathcal { N } } = 4$ （20 $S Y M$ theory has hidden uniform transcendentality.

Note that, in sectors beyond SL(2), the notion of magnon number might need to be suitably generalised, e.g. to the total number of excitations in the spin-chain picture for composite operators. Further note that the property conjectured above is not visible from the study of operators in compact subsectors as performed in [20, 21, 28], unless they are embedded into a larger non-compact sector (i.e. through inclusion of an arbitrary number of covariant derivatives).

Further backing for the above conjecture comes from the relation between $\mathrm { S L } ( 2 )$ operators and lightlike Wilson loops. It is known that twist-two operators (i.e. length-two operators in the $\operatorname { S L } ( 2 )$ sector） in the large spin limit are related to lightlike cusped Wilson loops [59,60], which have uniform transcendentality [61]. This is related to the fact that harmonic numbers $S _ { m } ^ { ( l ) }$ become transcendentalnumbersofdegree $l$ for $m  \infty$ Similarly, $\begin{array} { r } { \sum _ { j = 1 } ^ { m } \frac { 1 } { j } \frac { ( 1 - u _ { i } ) ^ { j } } { v _ { i } ^ { j } } \to } \end{array}$ $\begin{array} { r } { - \log { \left( 1 - \frac { 1 - u _ { i } } { v _ { i } } \right) } } \end{array}$ for $m \to \infty$ . Generic $\operatorname { S L } ( 2 )$ operators are related to multi-edge lightlike Wilson loops. Since lightlike Wilson loops,which are dual to amplitudes, have uniform transcendentality in ${ \mathcal N } = 4$ SYM theory [62-65], this provides more support for our conjecture.

While the theory underlying the considerations of this paper is $\mathcal { N } = 4$ SYM theory, we expect that the above insights may also teach us interesting lessons about similar calculations in QCD.In particular, one may wonder whether the maximal transcendentality principle [55, 66] extends to the notion of hidden transcendentality indicated above, see also [1O]. We will further discuss this point in the outlook in section 5.

The paper is organised as follows. In section 2，we give the tree-level form factors needed for the unitarity computations. Then,the full one-loop minimal form factor is obtained in section 3 and the one-loop dilatation operator and finite terms are extracted. In section 4, we construct the complete two-loop integrand and obtain the two-loop dilatation operator and the remainder functions for operators up to total magnon number three. We moreover discuss the interesting pattern and transcendentality property for the remainder functions. A conclusion and outlook is given in section 5. In appendix A, we give technical details on evaluating the one-loop form factor integrals. The complete remainder functions up to total magnon number three are given in terms of their densities in appendix B.

# 2 Tree level

In this section,we provide the tree-level form factors in the SL(2) sector which occur in the unitarity cuts in the subsequent sections.

Minimal form factors. Within the SL(2) sector, a minimal form factor for a singletrace operator of length $L$ contains $L$ external on-shell scalar states. While the state can be conveniently expressed in terms of oscillators acting on a (spin chain） vacuum [67],the minimal form factor is simply obtained by replacing these oscillators by spinor helicity variables $( \lambda , \tilde { \lambda } )$ and the ${ \mathrm { S U } } ( 4 )$ GraBmann spinors $\eta ^ { A }$ [19],see also [68,69]. For the SL(2） sector,each scalar $X ~ = ~ \phi _ { 3 4 }$ at position $i$ contributes a factor $\eta _ { i } ^ { 3 } \eta _ { i } ^ { 4 }$ and each covariant derivative $\mathrm { D ^ { + } }$ contributes a factor $p _ { i } ^ { + } = p _ { i } ^ { \mu } \tau _ { \mu }$ 4 For explicitness,but without loss of generality， we choose $\tau _ { \mu } = ( \sigma _ { \mu } ) ^ { \mathrm { 1 i } }$ ， such that $\mathrm { D ^ { + } = D ^ { 1 1 } }$ and $p ^ { + } = p ^ { 1 \mathrm { i } } = \lambda ^ { 1 } \tilde { \lambda } ^ { \mathrm { i } }$ ，when required. The minimal form factor can thus be written as

$$
\mathcal { F } _ { \mathcal { O } _ { \vec { n } } } ^ { ( 0 ) } ( 1 , 2 , \dots , L ; q ) = \delta ^ { 4 } \left( \sum _ { i = 1 } ^ { L } p _ { i } - q \right) \sum _ { k = 1 } ^ { L } \left( \prod _ { j = 1 } ^ { L } \frac { ( p _ { k + j } ^ { + } ) ^ { n _ { j } } } { n _ { j } ! } \eta _ { k + j } ^ { 3 } \eta _ { k + j } ^ { 4 } \right) ,
$$

where the sum over $k$ is due to the cyclicity of the colour-ordered form factor,which in the minimal case is essentially given by the manifestly cyclically invariant vertex of the operator. Having fixed the type of scalar $X$ ，a given operator or minimal form factor, respectively, is hence characterised by the derivative configuration ${ \vec { n } } = ( n _ { 1 } , \ldots , n _ { L } )$

Next-to-minimal form factors. As important building blocks for the two-loop computation via unitarity, we will also need the next-to-minimal tree-level form factors, which have $L + 1$ external states. These can be easily computed via Feynman diagrams. The results coincide with the corresponding tree-level expressions for general operators obtained via the twistor action in [26].

At MHV level, there are two different configurations of external states to be considered for the next-to-minimal form factors. The first configuration consists of $L - 1$ scalar external s $X _ { i } = \phi _ { i } ^ { 3 4 } \to \psi _ { i } ^ { 3 } \psi _ { i + 1 } ^ { 4 } - \psi _ { i } ^ { 4 } \psi _ { i + 1 } ^ { 3 }$ in the external states of the minimal form factor (2.1) for each $i = 1 , \ldots , L$ according to

$$
\frac { ( p _ { i } ^ { + } ) ^ { n _ { j } } } { n _ { j } ! } \eta _ { i } ^ { 3 } \eta _ { i } ^ { 4 }  \frac { 1 } { \langle i i + 1 \rangle } \sum _ { m = 0 } ^ { n _ { j } } \frac { ( p _ { i } ^ { + } ) ^ { m } } { m ! } \frac { ( p _ { i + 1 } ^ { + } ) ^ { n _ { j } - m } } { ( n _ { j } - m ) ! } ( \eta _ { i } ^ { 3 } \eta _ { i + 1 } ^ { 4 } - \eta _ { i } ^ { 4 } \eta _ { i + 1 } ^ { 3 } ) \ ,
$$

where we also have to relabel $p _ { l } ^ { + } \to p _ { l + 1 } ^ { + }$ for $l = i + 1 , \dotsc , L$ and include the momentum （20 $p _ { L + 1 }$ in the momentum-conserving delta function.

The second configuration consists of $L$ scalar external states and one positive-helicity gluon external states. For this configuration, two qualitatively different cases occur, which are distinguished via the $\overline { { \mathrm { S U } ( 2 ) } }$ indices,i.e. the indices $\dot { \alpha }$ of $\tilde { \lambda }$ . In the first case, all $\overline { { \mathrm { S U } ( 2 ) } }$ indices remain on the scalars. This process can only be attributed to a pair of neighbouring scalars, not to a single scalar, as gauge invariance is achieved by summing two Feynman diagrams: one with the left scalar emitting the gluon to the right and the other with the right scalar emitting the gluon to the left such that the gluon appears between the two scalars in the colour-ordered expression. We can obtain the contribution of this case from the minimal form factors (2.1） by replacing $X _ { i } X _ { i + 1 }  X _ { i } g _ { i + 1 } ^ { + } X _ { i + 2 }$ in the external states for $i = 1 , \ldots , L$ according to

$$
\frac { ( p _ { i } ^ { + } ) ^ { n _ { j } } } { n _ { j } ! } \eta _ { i } ^ { 3 } \eta _ { i } ^ { 4 } \frac { ( p _ { i + 1 } ^ { + } ) ^ { n _ { j + 1 } } } { n _ { j + 1 } ! } \eta _ { i + 1 } ^ { 3 } \eta _ { i + 1 } ^ { 4 } \to \frac { \langle i i + 2 \rangle } { \langle i i + 1 \rangle \langle i + 1 i + 2 \rangle } \frac { ( p _ { i } ^ { + } ) ^ { n _ { j } } } { n _ { j } ! } \frac { ( p _ { i + 2 } ^ { + } ) ^ { n _ { j + 1 } } } { n _ { j + 1 } ! } \eta _ { i } ^ { 3 } \eta _ { i } ^ { 4 } \eta _ { i + 2 } ^ { 3 } \eta _ { i + 2 } ^ { 4 } ,
$$

where we also have to relabel $p _ { l } ^ { + } \to p _ { l + 1 } ^ { + }$ for $l = i + 2 , \ldots , L$ and include the momentum （20 $p _ { L + 1 }$ in the momentum-conserving delta function. In the second case,at least one $\overline { { \mathrm { S U } ( 2 ) } }$ index from scalar $i$ lands on the gluon. Two Feynman diagrams contribute to this case: the emission of a gluon by scalar $i$ , and the insertion of a polarisation vector into the gaugefield part of the covariant derivative acting on this scalar. Their sum is gauge invariant, and, as they are only involving the scalar $i$ ，we can write this contribution by replacing $X _ { i }  X _ { i } g _ { i + 1 } ^ { + } + g _ { i } ^ { + } X _ { i + 1 }$ in (2.1) for $i = 1 , \ldots , L$ according to

$$
\begin{array} { r l r } & { } & { \frac { ( p _ { i } ^ { + } ) ^ { n _ { j } } } { n _ { j } ! } \eta _ { i } ^ { 3 } \eta _ { i } ^ { 4 }  + \frac { \lambda _ { i } ^ { 1 } \tilde { \lambda } _ { i + 1 } ^ { 1 } } { \langle i i + 1 \rangle } \displaystyle \sum _ { m = 1 } ^ { n _ { j } } \frac { 1 } { m } \frac { ( p _ { i } ^ { + } ) ^ { n _ { j } - m } } { ( n _ { j } - m ) ! } \frac { ( p _ { i + 1 } ^ { + } ) ^ { m - 1 } } { ( m - 1 ) ! } \eta _ { i } ^ { 3 } \eta _ { i } ^ { 4 } } \\ & { } & { + \frac { \tilde { \lambda } _ { i } ^ { 1 } \lambda _ { i + 1 } ^ { 1 } } { \langle i i + 1 \rangle } \displaystyle \sum _ { m = 1 } ^ { n _ { j } } \frac { 1 } { m } \frac { ( p _ { i } ^ { + } ) ^ { m - 1 } } { ( m - 1 ) ! } \frac { ( p _ { i + 1 } ^ { + } ) ^ { n _ { j } - m } } { ( n _ { j } - m ) ! } \eta _ { i + 1 } ^ { 3 } \eta _ { i + 1 } ^ { 4 } , } \end{array}
$$

where we again relabel $p _ { l } ^ { + } \to p _ { l + 1 } ^ { + }$ for $l = i + 1 , \dotsc , L$ and include the momentum $p _ { L + 1 }$ in the momentum-conserving delta function.

We acquire the next-to-minimal MHV form factor by applying the replacements rules (2.2)-(2.4) to all fields in the operator and summing the resulting expressions. The nextto-minimal NMHV form factor can be obtained from its MHV counterpart via conjugation, as described in [2O] in our conventions.

# 3 One loop

In this section，we calculate the one-loop correction to the minimal form factors in the SL(2) sector and extract from them the one-loop dilatation operator and the finite part.

# 3.1 Unitarity construction

Let us write the loop expansion of the minimal form factor in the following form:

$$
\mathcal { F } _ { \mathcal { O } } = \biggl ( 1 + \sum _ { \ell = 1 } ^ { \infty } g ^ { 2 \ell } \mathcal { T } ^ { ( \ell ) } \biggr ) \mathcal { F } _ { \mathcal { O } } ^ { ( 0 ) } ,
$$

where

$$
g ^ { 2 } = \frac { g _ { \mathrm { { \scriptscriptstyle Y M } } } ^ { 2 } N _ { \mathrm { c } } } { ( 4 \pi ) ^ { 2 } } ( 4 \pi \mathrm { e } ^ { - \gamma _ { \mathrm { { E } } } } ) ^ { \varepsilon }
$$

is the effective planar coupling constant. For operators such as BPS operators or the Konishi primary, which are eigenstates under renormalisation, $\boldsymbol { \mathcal { T } ^ { ( \ell ) } }$ is simply the ratio of the $\ell$ -loop and tree-level form factor. However, this is not true in general due to operator mixing. In particular, the loop corrections to vanishing tree-level form factors can be non-vanishing. It is therefore important to promote $\boldsymbol { \mathcal { T } ^ { ( \ell ) } }$ to an operator that acts on the tre-level form factor $\mathcal { F } _ { \mathcal { O } } ^ { ( 0 ) }$ andcancreatediferenttreevelffactorfromit.Examples in the SU(2) sector and for general operators can be found in [21] and [19], respectively.

In the planar limit,connected $\ell$ -loop interactions can maximally involve $\ell + 1$ neighbouring fields in the colour-ordered form factor at a time. Hence, $\boldsymbol { \mathcal { T } ^ { ( \ell ) } }$ can be written as a sum over connected interaction densities each of which involves $\ell + 1$ adjacent external legs plus disconnected products of lower-loop interaction densities. At one-loop order, the maximal interaction range is two, and we can write5

![](images/bbe20a70f8ef7c2d2b492b7a7285acbfeed82a88af9426b767a32c209e489f19.jpg)  
Figure 1: The double cut of one-loop form factor in the $s _ { 1 2 }$ -channel.

$$
\mathcal { T } ^ { ( 1 ) } = \sum _ { i = 1 } ^ { L } { I _ { i i + 1 } ^ { ( 1 ) } } ,
$$

where 1(1) acts on the external fields $i$ and $i + 1$ and cyclic identification $i + L \sim i$ is understood. 1(1) can be given in an operatorial form as

$$
I _ { i , i + 1 } ^ { ( 1 ) } = \sum _ { n _ { i } , m _ { i } = 0 } ^ { \infty } ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } \frac { ( p _ { i } ^ { + } ) ^ { m _ { 1 } } } { m _ { 1 } ! } \frac { ( p _ { i + 1 } ^ { + } ) ^ { m _ { 2 } } } { m _ { 2 } ! } \biggl ( \frac { \partial } { \partial p _ { i } ^ { + } } \biggr ) _ { p _ { i } ^ { + } = 0 } ^ { n _ { 1 } } \biggl ( \frac { \partial } { \partial p _ { i + 1 } ^ { + } } \biggr ) _ { p _ { i + 1 } ^ { + } = 0 } ^ { n _ { 2 } } ,
$$

where $( I _ { i } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } }$ is the matrix element ofthe interactiondensity that corresponds to changing the derivative configuration at momenta $p _ { i }$ ， $p _ { i + 1 }$ in the tree-level form factor (2.1) from （204号 $n _ { 1 }$ ， $n _ { 2 }$ to $m _ { 1 }$ ， $m _ { 2 }$ , respectively.6 Here, $\begin{array} { r } { \big ( \frac { \partial } { \partial p } \big ) _ { p = 0 } ^ { n } } \end{array}$ should be understood as acting to the right such that

$$
\left( \frac { \partial } { \partial p } \right) _ { p = 0 } ^ { n } f ( p ) = \frac { \partial ^ { n } f ( p ) } { \partial p ^ { n } } \bigg | _ { p = 0 } ,
$$

where the action is understood to be on the polynomial in $p _ { i } ^ { + }$ ，not on the momentumconserving delta function.

One-loop interaction. The loop correction $( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } }$ can be computed using the unitarity method. We wil be comparatively brief here; see e.g.[19-21, 37] for details of similar calculations and [21] for details on our conventions. As only interactions between two adjacent fields occur at one-loop order in the planar theory, it is enough to consider the double cut shown in Fig.1. The cut integrand takes the form

$$
\begin{array} { r l } { { } } & { { \displaystyle \int \mathrm { d } \mathrm { L I P S } ( l _ { 1 } , l _ { 2 } ) \mathrm { d } ^ { 4 } \eta _ { 1 } \mathrm { d } ^ { 4 } \eta _ { 2 } { \mathcal F } _ { \mathcal O } ^ { ( 0 ) } ( l _ { 1 } ^ { X } , l _ { 2 } ^ { X } , p _ { 3 } , . . , p _ { L } ; q ) A _ { 4 } ^ { ( 0 ) } ( - l _ { 2 } ^ { \bar { X } } , - l _ { 1 } ^ { \bar { X } } , p _ { 1 } ^ { X } , p _ { 2 } ^ { X } ) \eqno { ( 3 . 6 ) } ( \mathrm { ~ a . c . ~ } ) } } \\ { { } } & { { \displaystyle = \sum _ { n _ { i } = 0 } ^ { \infty } \left[ \int \mathrm { d } \mathrm { L I P S } ( l _ { 1 } , l _ { 2 } ) { \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } } { \frac { ( l _ { 2 } ^ { + } ) ^ { n _ { 2 } } } { n _ { 2 } ! } } { \frac { \langle l _ { 1 } l _ { 2 } \rangle \langle 1 2 \rangle } { \langle l _ { 1 } 1 \rangle \langle l _ { 2 } 2 \rangle } } \right] \left( { \frac { \partial } { \partial p _ { 1 } ^ { + } } } \right) _ { p _ { 1 } = 0 } ^ { n _ { 1 } } \left( { \frac { \partial } { \partial p _ { 2 } ^ { + } } } \right) _ { p _ { 2 } = 0 } ^ { n _ { 2 } } { \mathcal F } _ { \mathcal O } ^ { ( 0 ) } ( p _ { 1 } , . . , p _ { L } ; q ) . } } \end{array}
$$

where the minimal tree-level form factor is given in (2.1) and the four-point amplitude is given by the standard MHV expression. The two-particle phase-space measure is denoted by dLIPS.

The full integrand can be obtained from the cut integrand by adding the cut propagators and taking the cut momenta $l _ { 1 , 2 }$ to be off-shell. Explicitly, the square bracket part on the right hand side of (3.6),now written for general $i$ ， lifts to the one-loop integral as

$$
\begin{array} { l } { { ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } = - s _ { i i + 1 } = { { \displaystyle { \sum _ { p _ { i + 1 } } ^ { l _ { 1 } } } } } _ { n _ { 1 } } \frac { \ l ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 2 } ^ { + } ) ^ { n _ { 2 } } } { n _ { 2 } ! } \ } } \\ { { \equiv - s _ { i i + 1 } ( \mathrm { e } ^ { \gamma _ { \mathrm { E } } } \mu ^ { 2 } ) ^ { 2 - \frac { D } { 2 } } \frac { 1 } { n _ { 1 } ! n _ { 2 } ! } \int \frac { \mathrm { d } ^ { D } l _ { 1 } } { i \pi ^ { \frac { D } { 2 } } } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } ( l _ { 2 } ^ { + } ) ^ { n _ { 2 } } } { l _ { 1 } ^ { 2 } l _ { 2 } ^ { 2 } ( l _ { 1 } - p _ { i } ) ^ { 2 } } \ , } } \end{array}
$$

where $l _ { 2 } = p _ { i } + p _ { i + 1 } - l _ { 1 }$ . The 't Hooft mass is denoted by $\mu$ , the spacetime dimension is $D = 4 - 2 \varepsilon$ and $\gamma _ { \mathrm { E } }$ is the Euler-Mascheroni constant. This expression agrees with the one already found in [19].

For given small magnon numbers $n _ { 1 }$ and $n _ { 2 }$ , it is straightforward to perform standard Passarino-Veltmann (PV) reduction [70] and integration-by-parts (IBP) reduction [71, 72], which reduces the integral to the scalar bubble integral (A.1O). The integral (3.7) evaluates to a polynomial in terms of the lightcone components of the two external momenta as

$$
( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } = \sum _ { \substack { m _ { 1 } , m _ { 2 } = 0 } } ^ { n _ { 1 } + n _ { 2 } } ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } \frac { ( p _ { i } ^ { + } ) ^ { m _ { 1 } } } { m _ { 1 } ! } \frac { ( p _ { i + 1 } ^ { + } ) ^ { m _ { 2 } } } { m _ { 2 } ! } .
$$

As shown in appendix A, the coefficients in the above expression can even be evaluated to a closed form in the generic case:

$$
\begin{array} { l } { \frac { n _ { 1 } , m _ { 2 } } { n _ { 1 } , m _ { 2 } } = \displaystyle \frac { m _ { 1 } ! m _ { 2 } ! } { \Gamma ( \frac { D } { 2 } + m _ { 1 } - 1 ) \Gamma ( \frac { D } { 2 } + m _ { 2 } - 1 ) } \displaystyle \frac { \Gamma ( D - 2 ) } { \Gamma ( \frac { D } { 2 } - 1 ) } = \longleftrightarrow \sum _ { \nu _ { i + 1 } } ^ { \infty } } \\ { \displaystyle \operatorname* { m i n } ( \displaystyle \sum _ { j = 0 } ^ { \infty } m _ { 2 } , m _ { 3 } , m _ { 2 } ) \underbrace { ( - 1 ) ^ { j } \Gamma ( \frac { D } { 2 } + n _ { 1 } + n _ { 2 } - j - 1 ) } _ { j ! ( m _ { 1 } - j ) ! ( m _ { 2 } - j ) ! } } \\ { \displaystyle \operatorname* { m i n } ( \displaystyle \sum _ { j = 0 } ^ { \infty } \frac { m _ { 1 } ! m _ { 2 } ! n _ { 1 } ! \cdots n _ { j } } { \Gamma ( \frac { D } { 2 } - m _ { 2 } - n _ { 2 } ) ! } \left( \displaystyle \frac { m _ { 1 } - j } { n _ { 1 } - j - r } \right) \left( \displaystyle \sum _ { r } ^ { m _ { 2 } - j } \right) } \\ { \displaystyle \quad \operatorname* { m a x } ( 0 , m _ { 2 } - n _ { 2 } ) \left( n _ { 1 } - j - 2 \right) \Gamma ( \frac { D } { 2 } + n _ { 1 } + m _ { 2 } - 2 j - 2 r - 1 ) \ : , } \end{array}
$$

where the diagram denotes the standard scalar bubble integral given in (A.1O). We have checked in numerous special cases that the general result agrees with the one obtained using PV and IBP reduction.

The result (3.9) contains the full $\boldsymbol { \varepsilon }$ -expansion,which, for example, also includes the rational contribution.7 This will be important for computing the two-loop dilatation operator and remainder function.

# 3.2 Dilatation operator

The anomalous dilatation operator is defined via the renormalisation factor $\mathcal { Z }$ according to

$$
\delta \mathfrak { D } = - \mu \frac { \mathrm { d } } { \mathrm { d } \mu } \log \mathcal { Z } = 2 \varepsilon g ^ { 2 } \frac { \partial } { \partial g ^ { 2 } } \log \mathcal { Z } .
$$

Expanding in powers of the coupling constant,we have

$$
\delta \mathfrak { D } = \sum _ { \ell = 1 } ^ { \infty } g ^ { 2 \ell } \mathfrak { D } ^ { ( \ell ) } , \qquad \quad \quad \quad \quad \quad \mathcal { Z } = \sum _ { \ell = 0 } ^ { \infty } g ^ { 2 \ell } \mathcal { Z } ^ { ( \ell ) } , \qquad \quad \quad \mathcal { Z } ^ { ( 0 ) } = \mathbb { 1 } .
$$

At one-loop order, the renormalised interaction (indicated by the underscore),

$$
\underline { { \tau } } ^ { ( 1 ) } = \mathcal { T } ^ { ( 1 ) } + \mathcal { Z } ^ { ( 1 ) } ,
$$

is UV finite by definition of the renormalisation matrix $\mathcal { Z } ^ { ( 1 ) }$ .As $\mathcal { T } ^ { ( 1 ) }$ , we can expand $\mathcal { Z } ^ { ( 1 ) }$ （20 in terms of densities as

$$
\mathcal { Z } ^ { ( 1 ) } = \sum _ { i = 1 } ^ { L } \mathcal { Z } _ { i i + 1 } ^ { ( 1 ) } ,
$$

where we expand $\mathcal { Z } _ { i i + 1 } ^ { ( 1 ) }$ interofitsatrietspetea.)

$$
\mathcal { Z } _ { i i + 1 } ^ { ( 1 ) } = \sum _ { n _ { i } , m _ { i } = 0 } ^ { \infty } ( \mathcal { Z } _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } \frac { ( p _ { i } ^ { + } ) ^ { m _ { 1 } } } { m _ { 1 } ! } \frac { ( p _ { i + 1 } ^ { + } ) ^ { m _ { 2 } } } { m _ { 2 } ! } \left( \frac { \partial } { \partial p _ { i } ^ { + } } \right) _ { p _ { i } ^ { + } = 0 } ^ { n _ { 1 } } \left( \frac { \partial } { \partial p _ { i + 1 } ^ { + } } \right) _ { p _ { i + 1 } ^ { + } = 0 } ^ { n _ { 2 } } .
$$

By definition, $\mathcal { Z } _ { i i + 1 } ^ { ( 1 ) }$ has tocancel theUVdivergence of $I _ { i i + 1 }$ . In terms fmatrix ements, this reads

$$
( \mathcal { Z } _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } = - ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } \Big | _ { \mathrm { U V } } = - \Big [ ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } - ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } \Big | _ { \mathrm { I R } } \Big ] \Big | _ { \frac { 1 } { \varepsilon } \mathrm { p o l e } } ,
$$

where we have written the UV divergence as the total divergence minus the IR divergence. The former is then given as the remaining $\frac { 1 } { \varepsilon }$ -pole,which we extract as indicated by the vertical bar. The IR divergent part is universal and given by (see e.g. [19])

$$
( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } \Big | _ { \mathrm { I R } } = - s _ { i i + 1 } \delta _ { n _ { 1 } } ^ { m _ { 1 } } \delta _ { n _ { 2 } } ^ { m _ { 2 } } \lesssim - \mathscr { C } _ { \quad \begin{array} { l } { p _ { i } } \\ { \frac { \textstyle } { 2 } } \end{array} } ^ { p _ { i } } = - \frac { 1 } { \varepsilon ^ { 2 } } \left( - \frac { s _ { i i + 1 } } { \mu ^ { 2 } } \right) ^ { - \varepsilon } \delta _ { n _ { 1 } } ^ { m _ { 1 } } \delta _ { n _ { 2 } } ^ { m _ { 2 } } + O ( \varepsilon ^ { 0 } ) ,
$$

where the scalar triangle integral is given in (A.12).

From equation (3.1O),we can read off the one-loop dilatation operator as

$$
\mathfrak { D } ^ { ( 1 ) } = 2 \varepsilon \mathcal { Z } ^ { ( 1 ) } , \quad \mathfrak { D } _ { i i + 1 } ^ { ( 1 ) } = 2 \varepsilon \mathcal { Z } _ { i i + 1 } ^ { ( 1 ) } , \quad ( \mathfrak { D } _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } = 2 \varepsilon ( \mathcal { Z } _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } ,
$$

where we have expanded the one-loop dilatation operator in terms of densities and matrix elements in complete analogy to (3.13) and (3.14), respectively. We have checked in explicit cases that the result from the above expression agrees with the well-known expression for the one-loop dilatation operator [67]:

$$
( \mathfrak { D } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } = 2 ( S _ { n _ { 1 } } ^ { ( 1 ) } \delta _ { n _ { 1 } } ^ { m _ { 1 } } \delta _ { n _ { 2 } } ^ { m _ { 2 } } - \frac { \theta _ { n _ { 2 } m _ { 2 } } } { n _ { 2 } - m _ { 2 } } \delta _ { n _ { 1 } + n _ { 2 } } ^ { m _ { 1 } + m _ { 2 } } + \{ \mathbf { \Gamma } _ { m _ { 1 }  m _ { 2 } } ^ { n _ { 1 }  n _ { 2 } } \} ) \ .
$$

Here,we employ the harmonic numbers defined by

$$
S _ { n } ^ { ( \ell ) } = \sum _ { k = 1 } ^ { n } { \frac { 1 } { k ^ { \ell } } }
$$

as well as the Heaviside function

$$
\theta _ { n m } = { \left\{ \begin{array} { l l } { 1 { \mathrm { ~ f o r ~ } } n > m , } \\ { 0 { \mathrm { ~ f o r ~ } } n \leq m ; } \end{array} \right. }
$$

see also [53l for the notation used here.

# 3.3 Finite terms

We would like to better understand the structure of the complete one-loop form factor obtained above.After extracting the dilatation operator as the $1 / \varepsilon$ -pole of the interaction symbol $\mathcal { T }$ ,let us now study the finite part of the form factor in the $\xi$ -expansion.We define the non-trivial finite part as the $\mathcal { O } ( \varepsilon ^ { 0 } )$ contributions in the $\varepsilon$ -expansion of (3.9) after the UV and IR divergences are subtracted using (3.15) and (3.16):

$$
\mathrm { F i n } \left( ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } \right) = ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } - ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } \Big | _ { \mathrm { I R } } + ( \mathcal { Z } _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } .
$$

This yields in the special case $n _ { 2 } = 0 ^ { 8 }$

$$
\begin{array} { c } { { \displaystyle \mathrm { F i n } \left( ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , 0 } ^ { m _ { 1 } , m _ { 2 } } \right) = \delta _ { n _ { 1 } } ^ { m _ { 1 } } \delta _ { 0 } ^ { m _ { 2 } } \left[ - \frac 1 2 \left( S _ { n _ { 1 } } ^ { ( 1 ) } \right) ^ { 2 } - \frac 3 2 S _ { n _ { 1 } } ^ { ( 2 ) } \right] + \theta _ { m _ { 2 } 0 } \delta _ { n _ { 1 } + 0 } ^ { m _ { 1 } + m _ { 2 } } \frac 1 { m _ { 2 } } \left[ \frac 1 { m _ { 2 } } + S _ { n _ { 1 } } ^ { ( 1 ) } \right] } } \\ { { + \displaystyle \frac 1 2 ( \mathfrak { D } _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , 0 } ^ { m _ { 1 } , m _ { 2 } } \log \big ( - \frac { s _ { i i + 1 } } { \mu ^ { 2 } } \big ) ~ . } } \end{array}
$$

The general case can be obtained from this special case via the following symmetry relation for 1(1)

$$
\begin{array} { r } { m _ { 1 } ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } - 1 , m _ { 2 } } + m _ { 2 } ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } - 1 } = ( n _ { 1 } + 1 ) ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } + 1 , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } + ( n _ { 2 } + 1 ) ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } + 1 } ^ { m _ { 1 } , m _ { 2 } } , } \end{array}
$$

which is a direct consequence of momentum conservation and leads to an identical equation for the finite part.As a result,we find

$$
\begin{array} { l l } { { } } & { { \mathrm { F i n } \left( ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } \right) = } } & { { ( 3 . 2 ) ( i , 1 ) ( i , 1 ) ( i , 1 ) ( i , 2 ) } } \\ { { } } & { { \displaystyle \frac { m _ { 1 } ! m _ { 2 } ! } { n _ { 1 } ! n _ { 2 } ! } \sum _ { j = 0 } ^ { n _ { 2 } } \sum _ { k = 0 } ^ { n _ { 2 } - j } \frac { ( - 1 ) ^ { j } n _ { 2 } ! } { j ! k ! ( n _ { 2 } - j - k ) ! } \frac { ( n _ { 1 } + j ) ! } { ( m _ { 1 } - k ) ! ( m _ { 2 } - n _ { 2 } + l ) ! } { \mathrm { F i n } \left( ( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } + j , 0 } ^ { m _ { 1 } - k , m _ { 2 } - n _ { 2 } + l } \right) } \ , } } \end{array}
$$

where $l = j + k$

We can see that the finite terms in (3.22) and (3.24) have a simple structure similar to the one of the dilatation operator in (3.18). In particular, they have uniform maximal transcendentality two if the harmonic numbers and inverse powers of differences of magnon numbers are attributed a degree of transcendentality according to the rules $\begin{array} { r } { S ^ { ( l ) } \to l , \frac { 1 } { m _ { j } - n _ { j } } \to 1 } \end{array}$ . As we willsee in the next section, the two-loop results show a similar pattern.

# 4Two loops

In this section， we continue the study of SL(2) form factors at two loops. We will see that the unitarity method allows us to obtain the fullintegrand. We solve for the explicit dilatation operator and the remainder functions up to spin three. The two-loop dilatation operator and remainders show interesting patterns and suggest a hidden uniform maximal transcendentality property.

# 4.1 Unitarity construction

We first compute the two-loop integrand via the unitarity method. At two-loop order, connected interactions involve at most three fields of the composite operator, which are adjacent at the planar level. The two-loop corrections can be expressed as

$$
\mathcal { T } ^ { ( 2 ) } = \sum _ { i = 1 } ^ { L } \left( I _ { i i + 1 i + 2 } ^ { ( 2 ) } + I _ { i i + 1 } ^ { ( 2 ) } + \frac { 1 } { 2 } \sum _ { j = i + 2 } ^ { L + i - 2 } I _ { i i + 1 } ^ { ( 1 ) } I _ { j j + 1 } ^ { ( 1 ) } \right) ,
$$

where I(2) ii+1 and 1(2) $I _ { i i + 1 i + 2 } ^ { ( 2 ) }$ denote connected interactions of range two and three, respectively. We expand the interaction densities in terms of matrix elements as

$$
\begin{array} { r } { I _ { i i + 1 } ^ { ( 2 ) } = \displaystyle \sum _ { n _ { j } , m _ { j } = 0 } ^ { \infty } \big ( I _ { i } ^ { ( 2 ) } \big ) _ { n _ { 1 } , m _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } \frac { \big ( p _ { i } ^ { + } \big ) ^ { m _ { 1 } } } { m _ { 1 } ! } \frac { ( p _ { i + 1 } ^ { + } ) ^ { m _ { 2 } } } { m _ { 2 } ! } \Big ( \frac { \partial } { \partial p _ { i } ^ { + } } \Big ) _ { p _ { i } ^ { + } = 0 } ^ { n _ { 1 } } \Big ( \frac { \partial } { \partial p _ { i + 1 } ^ { + } } \Big ) _ { p _ { i + 1 } ^ { + } = 0 } ^ { n _ { 2 } } , \qquad } \\ { I _ { i i + 1 , i + 2 } ^ { ( 2 ) } = \displaystyle \sum _ { n _ { j } , m _ { j } = 0 } ^ { \infty } ( I _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , m _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } \frac { ( p _ { i } ^ { + } ) ^ { m _ { 1 } } } { m _ { 1 } ! } \frac { ( p _ { i + 1 } ^ { + } ) ^ { m _ { 2 } } } { m _ { 2 } ! } \frac { ( p _ { i + 2 } ^ { + } ) ^ { m _ { 3 } } } { m _ { 3 } ! } \qquad } \\ { \Big ( \frac { \partial } { \partial p _ { i } ^ { + } } \Big ) _ { p _ { i } ^ { + } = 0 } ^ { n _ { 1 } } \Big ( \frac { \partial } { \partial p _ { i + 1 } ^ { + } } \Big ) _ { p _ { i + 1 } ^ { + } = 0 } ^ { n _ { 2 } } \Big ( \frac { \partial } { \partial p _ { i + 2 } ^ { + } } \Big ) _ { p _ { i + 2 } ^ { + } = 0 } ^ { n _ { 3 } } \Big ( \frac { \partial } { \partial p _ { i + 2 } ^ { + } } \Big ) _ { p _ { i + 2 } ^ { + } = 0 } ^ { n _ { 3 } } . } \end{array}
$$

The $( I _ { i } ^ { ( 1 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } }$ le 1 tntior $( I _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } } ^ { m _ { 1 } , m _ { 2 } }$ $( I _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } }$ non-trivial double and triple cuts are shown in Fig.2. In the following,we briefly outline the major steps and present the full integrand. More technical details on this kind of calculation may be found in [21].

Double cuts. The simplest cuts are the two-particle cuts in the two-particle channels, with the one-loop amplitude or form factor on one side of the cut. They are shown in Fig. 2a and 2b, respectively. From them, we can fix the integrand contributions from the following topologies as

$$
( I _ { i , A } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } } = = \sum ^ { l _ { 1 } } \prod _ { \substack { i + 1 } } ^ { i } s _ { i i + 1 } ^ { 2 } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 2 } ^ { + } ) ^ { n _ { 2 } } } { n _ { 2 } ! } ,
$$

$$
( I _ { i , B } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } = = \sum _ { \bar { l } _ { 3 } \atop { l _ { 3 } } \ldots \ldots } ^ { l _ { 1 } } \sum _ { i + 2 } ^ { i } s _ { l _ { 1 } l _ { 2 } } s _ { i + 1 i + 2 } { \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } } { \frac { ( l _ { 2 } ^ { + } ) ^ { n _ { 2 } } } { n _ { 2 } ! } } { \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 3 } } } { n _ { 3 } ! } } ,
$$

![](images/bcc0ebf45d56ea164dff8e4d48c4168794883f32519e0339ecfc89d64cd6b1da.jpg)  
Figure2:Uitatfe $\mathcal { F } _ { \mathcal { O } , L } ^ { ( 2 ) }$

$$
( I _ { i , C } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } = = = \sum _ { l _ { 3 } \atop l _ { 3 } } ^ { l _ { 1 } } \prod _ { i + 1 } ^ { i } s _ { i i + 1 } s _ { l _ { 2 } l _ { 3 } } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 2 } ^ { + } ) ^ { n _ { 2 } } } { n _ { 2 } ! } \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 3 } } } { n _ { 3 } ! } ,
$$

where $n _ { 1 } , n _ { 2 } , n _ { 3 }$ are the numbers of derivatives occurring in the corresponding minimal treelevel form factor and thus in the integrand. Moreover, we have abbreviated $l _ { 2 } = p _ { i } + p _ { i + 1 } - l _ { 1 }$ （204号 in $I _ { i , A } ^ { ( 2 ) }$ and $l _ { 2 } = p _ { i } + p _ { i + 1 } + p _ { i + 2 } - l _ { 1 } - l _ { 3 }$ m $I _ { i , B } ^ { ( 2 ) }$ as well as $I _ { i , C } ^ { ( 2 ) }$ .Note that these contributions can be equally obtained via consecutive double cuts.

Triple cut in the three-particle channel. Next,we perform the triple cut in the three-particle channel as shown in Fig.2c. Both (4.5) and (4.6) contribute to this cut. The new contribution determined by this cut is

$$
( I _ { i , D } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } = - \sum _ { l _ { 3 } \atop l _ { 3 } } ^ { l _ { 1 } } \int _ { i + 2 } ^ { i } s _ { i + 1 } { } _ { i + 1 } { } _ { i + 2 } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 2 } ^ { + } ) ^ { n _ { 2 } } } { n _ { 2 } ! } \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 3 } } } { n _ { 3 } ! } \ .
$$

Triple cut in the two-particle channel. The most complicated cut is the triple cut in the two-particle channel as shown in Fig. 2d. All previous integrands contribute to this

cut.The new integrand contributions are

$$
( I _ { i , E } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } = \left( \left. = < \sum _ { l _ { 3 } } ^ { l _ { 1 } } \right| ^ { - i + 1 } ( p _ { i + 1 } ^ { + } + p _ { i + 2 } ^ { + } ) - \left. = < \sum _ { l _ { 3 } } ^ { l _ { 1 } } \right| ^ { - i + 1 } p _ { i + 1 } ^ { + } s _ { l _ { 2 } l _ { 3 } } \right.
$$

$$
-  \stackrel { l _ { 1 } } { \underbrace { \sum _ { i = 1 } ^ { n } \sum _ { i = 1 } ^ { n - 1 } ( l _ { 1 } ^ { + } + 1 _ { i + 2 } ( l _ { 1 } ^ { + } + l _ { 2 } ^ { + } ) ) } } [ \sum _ { m = 1 } ^ { n _ { 1 } } \frac { 1 } { m } \frac { ( p _ { i } ^ { + } ) ^ { n _ { 1 } - m } } { ( n _ { 1 } - m ) ! } \frac { ( l _ { 1 } ^ { + } ) ^ { m - 1 } } { ( m - 1 ) ! } \frac { ( l _ { 2 } ^ { + } ) ^ { n _ { 2 } } } { n _ { 2 } ! } \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 3 } } } { n _ { 3 } ! } 
$$

$$
\begin{array} { l } { { \displaystyle - \sum _ { m = 1 } ^ { n _ { 2 } } \frac { 1 } { m } \frac { ( p _ { i } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 1 } ^ { + } ) ^ { m - 1 } } { ( m - 1 ) ! } \frac { ( l _ { 2 } ^ { + } ) ^ { n _ { 2 } - m } } { ( n _ { 2 } - m ) ! } \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 3 } } } { n _ { 3 } ! } - \sum _ { m = 1 } ^ { n _ { 2 } } \frac { 1 } { m } \frac { ( p _ { i } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 2 } - m } } { ( n _ { 2 } - m ) ! } \frac { ( l _ { 2 } ^ { + } ) ^ { m - 1 } } { ( m - 1 ) ! } \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 3 } } } { n _ { 3 } ! } } } \\ { { \displaystyle + \sum _ { m = 1 } ^ { n _ { 3 } } \frac { 1 } { m } \frac { ( p _ { i } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 2 } } } { n _ { 2 } ! } \frac { ( l _ { 2 } ^ { + } ) ^ { m - 1 } } { ( m - 1 ) ! } \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 3 } - m } } { ( n _ { 3 } - m ) ! } \biggr ] , } } \end{array}
$$

and

$$
\begin{array} { l } { { \displaystyle { \cal I } _ { i , F } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } = (  { - \sum _ { i = 1 } ^ { n } \sum _ { i = 3 } ^ { i } \sum _ { i = 1 } ^ { n } ( p _ { i } ^ { + } + p _ { i + 1 } ^ { + } ) -  { \operatorname { s u p } \sum _ { l _ { 3 } } ^ { n } \sum _ { i = 1 } ^ { i + 3 } p _ { i + 1 } ^ { + } }  }  } } \\ { { \displaystyle \quad -  { \operatorname { \operatorname { \operatorname { \operatorname { \operatorname { \operatorname { \operatorname { \operatorname { \operatorname { \operatorname { \operatorname { \alpha } } } } } } } } } } } \sum _ { i = 1 } ^ { i } \sum _ { i + 1 } ^ { i } ( l _ { 2 } ^ { + } + l _ { 3 } ^ { + } ) } ) [ \sum _ { m = 1 } ^ { n _ { 1 } } \frac { 1 } { m } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } - m } } { ( n _ { 1 } - m ) ! } \frac { ( l _ { 2 } ^ { + } ) ^ { m - 1 } } { ( m - 1 ) ! } \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 2 } } } { n _ { 2 } ! } \frac { ( p _ { i + 2 } ^ { + } ) ^ { n _ { 3 } } } { n _ { 3 } ! }  } } \\  { \displaystyle  - \sum _ { m = 1 } ^ { n _ { 2 } } \frac { 1 } { m } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 2 } ^ { + } ) ^ { n _ { 2 } - m } } { ( n _ { 2 } - m ) ! } \frac { ( l _ { 3 } ^ { - } ) ^ { m - 1 } } { ( m - 1 ) ! } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 3 } } } { n _ { 3 } ! } - \sum _ { m = 1 } ^ { n _ { 2 } } \frac { 1 } { m } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 2 } ^ { + } ) ^ { m - 1 } } { ( m - 1 ) ! } \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 2 } - m } } { ( n _ { 2 } - m ) ! } \frac { ( p _ { i } ^ { + } ) ^ { m - 1 } } { n _ { 3 } ! }  } \\   \displaystyle  + \sum _ { m = 1 } ^ { n _ { 3 } } \frac { 1 } { m } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 2 } ^ { + } ) ^ { m - 1 } }  \end{array}
$$

as well as

$$
\begin{array} { r l } & { ( I _ { i , G } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } } =  \longrightarrow \bigoplus _ { l _ { 3 } } ^ { l _ { 1 } } \bigoplus _ { n _ { 1 } \uparrow } ^ { n } s _ { i + 1 } [ ( p _ { i + 1 } ^ { + } - l _ { 3 } ^ { + } ) \underset { m = 1 } { \sum _ { m } ^ { n _ { 1 } } } \frac { 1 } { m } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } - m } } { ( n _ { 1 } - m ) ! } \frac { ( l _ { 2 } ^ { + } ) ^ { m - 1 } } { ( m - 1 ) ! } \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 2 } } } { n _ { 2 } ! }  } \\ & {  + ( p _ { i } ^ { + } - l _ { 1 } ^ { + } ) \underset { m = 1 } { \sum _ { m } ^ { n _ { 2 } } } \frac { 1 } { m } \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 2 } ^ { + } ) ^ { m - 1 } } { ( m - 1 ) ! } \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 2 } - m } } { ( n _ { 2 } - m ) ! } + \frac { ( l _ { 1 } ^ { + } ) ^ { n _ { 1 } } } { n _ { 1 } ! } \frac { ( l _ { 3 } ^ { + } ) ^ { n _ { 2 } } } { n _ { 2 } ! } ] . } \end{array}
$$

Here, we have $l _ { 2 } = p _ { i + 1 } + p _ { i + 2 } - l _ { 1 } - l _ { 3 }$ i $I _ { i , E } ^ { ( 2 ) }$ and $l _ { 2 } = p _ { i } + p _ { i + 1 } - l _ { 1 } - l _ { 3 }$ i $I _ { i , F } ^ { ( 2 ) }$ as well as $I _ { i , G } ^ { ( 2 ) }$ =

We see that the structures of the loop momenta in the integrand are directly inherited from the corresponding structures in the tree-level form factors (2.1)-(2.3).

Result. Given the above building blocks, the interaction densities can be defined as

$$
\begin{array} { r l } & { I _ { i i + 1 } ^ { ( 2 ) } = I _ { i , A } ^ { ( 2 ) } + I _ { i , G } ^ { ( 2 ) } , } \\ & { I _ { i i + 1 i + 2 } ^ { ( 2 ) } = I _ { i , B } ^ { ( 2 ) } + I _ { i , C } ^ { ( 2 ) } + I _ { i , D } ^ { ( 2 ) } + I _ { i , E } ^ { ( 2 ) } + I _ { i , F } ^ { ( 2 ) } . } \end{array}
$$

They can be expanded in terms of matrix elements as

$$
\begin{array} { l } { { ( I _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } } = \displaystyle \sum _ { m _ { 1 } , m _ { 2 } } ( I _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , m _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } \frac { ( p _ { i } ^ { + } ) ^ { m _ { 1 } } } { m _ { 1 } ! } \frac { ( p _ { i + 1 } ^ { + } ) ^ { m _ { 2 } } } { m _ { 2 } ! } , \ } } \\ { { ( I _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } = \displaystyle \sum _ { m _ { 1 } , m _ { 2 } , m _ { 3 } } ( I _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } \frac { ( p _ { i } ^ { + } ) ^ { m _ { 1 } } } { m _ { 1 } ! } \frac { ( p _ { i + 1 } ^ { + } ) ^ { m _ { 2 } } } { m _ { 2 } ! } \frac { ( p _ { i + 2 } ^ { + } ) ^ { m _ { 3 } } } { m _ { 3 } ! } , \ } } \end{array}
$$

where $m _ { 1 } + m _ { 2 } = n _ { 1 } + n _ { 2 }$ and $m _ { 1 } + m _ { 2 } + m _ { 3 } = n _ { 1 } + n _ { 2 } + n _ { 3 }$ , respectively.

Let us explain the special combination of building blocks in (4.11). We should first note that there is an ambiguity in grouping and distributing the terms with integrals involving only two external momenta. In (4.11), a choice is made such that the terms in $I _ { i , A } ^ { ( 2 ) }$ and $I _ { i , G } ^ { ( 2 ) }$ are interpreted as contributions to the interaction density of range two acting on the sites $i$ and $i + 1$ , while the remaining terms are understood as interactions of range three acting on the sites $i$ ， $i + 1$ and $i + 2$ . While this assignment is irrelevant when summing over all densities to obtain $\mathcal { T } ^ { ( 2 ) }$ , it ensures the finiteness of the remainder density obtained from the corresponding interaction densities. We will come back to this point in subsection 4.3, see the discussion after (4.25).

As in the one-loop case, the integrands (4.4)-(4.10) contain uncontracted loop momenta. Using PV reduction, they can be expressed in terms of Lorentz scalar integrands, which contain loop momenta in the numerator only in the form of irreducible scalar products. The resulting integrals can be reduced to master integrals via IBP identities, using e.g. LiteRed [73]. The required master integrals are all known analytically and can be found in [74]. This procedure can be effciently applied for small numbers of magnons; we have computed explicit results for all cases up to a total magnon number three,i.e. $\textstyle \sum _ { i } n _ { i } \leq 3$ . While in principle applicable to higher numbers of magnons, the computation time for the employed method significantly increases from four magnons on.

# 4.2 Dilatation operator

The two-loop renormalised form factor is given by

$$
\underline { { \tau } } ^ { ( 2 ) } = \mathcal { I } ^ { ( 2 ) } + \mathcal { I } ^ { ( 1 ) } \mathcal { Z } ^ { ( 1 ) } + \mathcal { Z } ^ { ( 2 ) } ,
$$

where the two-loop renormalisation constant has to cancel the UV divergence and is given as

$$
\mathcal { Z } ^ { ( 2 ) } = \sum _ { i = 1 } ^ { L } \left( \mathcal { Z } _ { i i + 1 i + 2 } ^ { ( 2 ) } + \frac { 1 } { 2 } \sum _ { j = i + 2 } ^ { L + i - 2 } \mathcal { Z } _ { i i + 1 } ^ { ( 1 ) } \mathcal { Z } _ { j j + 1 } ^ { ( 1 ) } \right) .
$$

The first term inside the summation above is due to the connected interactions, while the last term accounts for all disconnected products of one-loop interactions in (4.1). Unlike in the one-loop case where the IR and UV divergences can be easily separated, at two-loop order the IR and UV divergences are entangled with each other. We can subtract the (universal) IR divergences via the BDS ansatz [75,76],as explained in detail in the next sbo $\mathcal { Z } _ { i i + 1 i + 2 } ^ { ( 2 ) }$ can be obtaine by imposing teBDSremaindersity $R _ { i i + 1 i + 2 } ^ { ( 2 ) }$ defned in (.25)to be fint

In terms of the renormalisation matrix $\mathcal { Z }$ , the form of the two-loop dilatation operator follows from the definition (3.10):

$$
{ \mathfrak { D } } ^ { ( 2 ) } = 4 \varepsilon { \Big ( } { \mathcal { Z } } ^ { ( 2 ) } - { \frac { 1 } { 2 } } ( { \mathcal { Z } } ^ { ( 1 ) } ) ^ { 2 } { \Big ) } ~ .
$$

It can be expanded in terms of densities as

$$
{ \mathfrak { D } } ^ { ( 2 ) } = \sum _ { i = 1 } ^ { L } { \mathfrak { D } } _ { i i + 1 i + 2 } ^ { ( 2 ) } .
$$

As usual, the densities are expressed via matrix elements in complete analogy to (4.3). Via the above relations, we may extract the matrix elements of the two-loop dilatation operator in analogy to the one-loop case. Note that the square in (4.15) has to be evaluated as a square of matrices. As an example, consider the following matrix element of the dilatation operator density, which is given in terms of the (non-vanishing) matrix elements of $\mathcal { Z } ^ { ( 1 ) }$ （204号 and $\mathcal { Z } ^ { ( 2 ) }$ as:

$$
\begin{array} { r l r } {  { ( \mathfrak { D } _ { i } ^ { ( 2 ) } ) _ { 0 , 1 , 2 } ^ { 2 , 1 , 0 } = 4 \varepsilon [ ( \mathcal { Z } _ { i } ^ { ( 2 ) } ) _ { 0 , 1 , 2 } ^ { 2 , 1 , 0 } - \frac { 1 } { 2 } ( \mathcal { Z } _ { i } ^ { ( 1 ) } ) _ { 0 , 3 } ^ { 2 , 1 } ( \mathcal { Z } _ { i + 1 } ^ { ( 1 ) } ) _ { 1 , 2 } ^ { 3 , 0 } ] } } \\ & { } & { = 4 \varepsilon [ ( \frac { 1 } { 8 \varepsilon ^ { 2 } } - \frac { 1 } { 1 6 \varepsilon } ) - \frac { 1 } { 2 } \Big ( - \frac { 1 } { 2 \varepsilon } \Big ) ^ { 2 } ] = - \frac { 1 } { 4 } , } \end{array}
$$

where the boldface number indicates the magnon number at the single internal leg. The matrix product willalso be used later in the definition of the remainder function, see (4.25) for a pictorial representation. Instead of giving explicit results for all matrix elements up to three magnons, we may compare the obtained expressons to the previous literature, where the two-loop dilatation operator in the SL(2) sector can be found in closed form.

Comparison with Feynman calculation. Notably, the fulltwo-loop dilatation operator in the SL(2) sector of ${ \mathcal { N } } = 4$ SYM theory has been obtained by Belitsky, Korchemsky and Mueller in [53]. The named authors provide an explicit expression in closed and relatively compact form. Our computation of the two-loop dilatation operator for states of up to three magnons shows perfect agreement with that operator if we evaluate both expressions on composite operators. For convenience, we display the respective expression in the following.9

In contrast to our expansion (4.16), the authors of [53] write the two-loop dilatation operator in terms of a range-two density and a range-three density:10

$$
\mathfrak { D } ^ { ( 2 ) } = \sum _ { i = 1 } ^ { L } \left( \tilde { \mathfrak { D } } _ { i i + 1 } ^ { ( 2 ) } + \tilde { \mathfrak { D } } _ { i i + 1 i + 2 } ^ { ( 2 ) } \right) .
$$

The range-two density reads

$$
\begin{array} { r l r } & { } & { ( \tilde { \mathfrak { D } } _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , m _ { 2 } } ^ { m _ { 1 } , m _ { 2 } } = - 2 [ 2 S _ { n _ { 1 } } ^ { ( 1 ) } S _ { n _ { 1 } } ^ { ( 2 ) } + S _ { n _ { 1 } } ^ { ( 3 ) } ] \delta _ { n _ { 1 } } ^ { m _ { 1 } } \delta _ { n _ { 2 } } ^ { m _ { 2 } } + \frac { \theta _ { n _ { 2 } m _ { 2 } } } { n _ { 2 } - m _ { 2 } } \delta _ { n _ { 1 } + n _ { 2 } } ^ { m _ { 1 } + m _ { 2 } } [ S _ { n _ { 1 } } ^ { ( 2 ) } + 3 S _ { m _ { 1 } } ^ { ( 2 ) }  } \\ & { } & {  + ( S _ { m _ { 1 } } ^ { ( 1 ) } - S _ { n _ { 1 } } ^ { ( 1 ) } ) ( S _ { n _ { 1 } } ^ { ( 1 ) } + 3 S _ { m _ { 1 } } ^ { ( 1 ) } - 4 S _ { n _ { 2 } - m _ { 2 } - 1 } ^ { ( 1 ) } ) ] + \{ \begin{array} { l l } { n _ { 1 }  n _ { 2 } } \\ { m _ { 1 }  m _ { 2 } } \end{array} \} , } \end{array}
$$

and the range-three density reads (for $n _ { 2 } = 0$

$$
\begin{array} { r l r } {  { ( \tilde { \mathfrak { D } } _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , 0 , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } = - 2 \frac { \delta _ { n _ { 1 } + 0 + n _ { 3 } } ^ { m _ { 1 } + m _ { 2 } + m _ { 3 } } \theta _ { n _ { 3 } m _ { 3 } } } { ( n _ { 1 } - m _ { 1 } ) ( n _ { 3 } - m _ { 3 } ) } \bigg [ \theta _ { m _ { 1 } n _ { 1 } } ( \frac { 1 } { n _ { 1 } - m _ { 1 } } + S _ { m _ { 1 } } ^ { ( 1 ) } - S _ { n _ { 1 } } ^ { ( 1 ) } - S _ { m _ { 1 } - n _ { 1 } } ^ { ( 1 ) } ) } } \\ & { } & { + \theta _ { n _ { 1 } m _ { 1 } } ( S _ { n _ { 1 } - m _ { 1 } } ^ { ( 1 ) } + S _ { n _ { 3 } - m _ { 3 } } ^ { ( 1 ) } - S _ { m _ { 2 } } ^ { ( 1 ) } ) \bigg ] + \{ \begin{array} { c } { n _ { 1 }  n _ { 3 } } \\ { m _ { 1 }  m _ { 3 } } \end{array} \} , \quad \quad ( \mathrm { R e } ) , } \end{array}
$$

as well as (for $n _ { 2 } \neq 0$ ）

$$
\begin{array} { c } { { ( \tilde { \mathfrak { D } } _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } = \displaystyle \frac { m _ { 1 } ! m _ { 2 } ! m _ { 3 } ! } { n _ { 1 } ! n _ { 2 } ! n _ { 3 } ! } \sum _ { j _ { 1 } = 0 } ^ { n _ { 2 } } \sum _ { j _ { 3 } = 0 } ^ { n _ { 2 } - j _ { 1 } } \sum _ { k _ { 1 } = 0 } ^ { n _ { 2 } - j _ { 1 } } \sum _ { k _ { 3 } = 0 } ^ { - k _ { 1 } } \frac { ( - 1 ) ^ { j } n _ { 2 } ! } { j _ { 1 } ! j _ { 3 } ! k _ { 1 } ! k _ { 3 } ! ( n _ { 2 } - \ell ) ! } } } \\ { { \frac { \ l ( n _ { 1 } + j _ { 1 } ) ! ( n _ { 3 } + j _ { 3 } ) ! } { ( m _ { 1 } - k _ { 1 } ) ! ( m _ { 2 } - n _ { 2 } + \ell ) ! ( m _ { 3 } - k _ { 3 } ) ! } ( \tilde { \mathfrak { D } } _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } + j _ { 1 } , 0 , n _ { 3 } + j _ { 3 } } ^ { m _ { 1 } - k _ { 1 } , m _ { 2 } - n _ { 2 } + \ell , m _ { 3 } - k _ { 3 } } , } } \end{array}
$$

where $j = j _ { 1 } + j _ { 3 }$ and $\ell = j + k _ { 1 } + k _ { 3 }$ . Note that the match with the two-loop dilatation operator of [53] is only at the level of the composite operators, i.e. after we sum over all matrix elements of the dilatation operator density that occur for a given (cyclically symmetric) single-trace operator. The matrix elements of the dilatation operator density do not directly match with the expressions of [53], which is of course also not required. To make this clear, we have marked the matrix elements of [53] with tildes.

We notice that the matrix elements (4.19) and (4.20) of the two-loop dilatation operator are of uniform transcendentality three if we formally assign the transcendentality $k$ to the harmonic number S(）and the transcendentality oneto the fraction mj-n; for $j = 1 , 2 , 3$ ： With the same assignment, the matrix elements (3.18) of the one-loop dilatation operator are formally of uniform transcendentality one. Let us refer to this property as hidden uniform transcendentality. Note that the assignment of transcendentality to harmonic numbers is standard in the context of anomalous dimensions, see e.g. [55]. An assignment of transcendentality to similar fractions also occurred in other contexts in the literature [56–58].

Comparison with algebraic construction. In [54], Zwiebel introduced an algebraic construction that allows to recursively compute the two-loop dilatation operator within the SL(2) sector. We have implemented this loop-recursion and we compared the spectrum of the resulting operator to the above findings for the $M = 1 , 2 , 3$ excitation sectors. In all cases, we found perfect agreement. The operatorial form of the two-loop dilatation operator obtained by the above recursion is rather lengthy and we thus refrain from displaying it here. We note, however, that the recursion in [54] actually applies to the larger PSU $( 1 , 1 | 2 )$ sector of ${ \mathcal { N } } = 4$ SYM theory, which makes it interesting for future extensions of our work.

Another advantage of this algebraic method is that it allows to construct a dilatation operator that is manifestly hermitian.11

# 4.3 Remainders

The (two-loop) BDS remainder [75,76] in the refned case of renormalised form factors [21] takes the form

$$
R ^ { ( 2 ) } = \underline { { { \mathbb Z } } } ^ { ( 2 ) } ( \varepsilon ) - \frac 1 2 \left( \underline { { { \mathbb Z } } } ^ { ( 1 ) } ( \varepsilon ) \right) ^ { 2 } - f ^ { ( 2 ) } ( \varepsilon ) \underline { { { \mathbb Z } } } ^ { ( 1 ) } ( 2 \varepsilon ) + { \cal O } ( \varepsilon ) ,
$$

where

$$
f ^ { ( 2 ) } ( \varepsilon ) = - 2 \zeta _ { 2 } - 2 \zeta _ { 3 } \varepsilon - 2 \zeta _ { 4 } \varepsilon ^ { 2 } .
$$

Similar to the example discussed in (4.17), the product of the one-loop density with itself has to be understood as a matrix product. For the two-loop remainder

$$
R ^ { ( 2 ) } = \sum _ { i = 1 } ^ { L } R _ { i i + 1 i + 2 } ^ { ( 2 ) } ,
$$

this is captured by the following pictorial expression

$$
\begin{array} { r l r } & { } & { R _ { i + i + 1 + 2 } ^ { ( 2 ) } = } \\ & { } & { \frac { 1 } { 2 } \overbrace { ( \underbrace { I _ { \langle \imath \downarrow \rangle } ^ { ( 2 ) } } ) } ^ { ( \frac { \lambda } { 2 } ) } \biggm \lvert + \overbrace { \Biggl \langle \underbrace { I _ { \langle \imath \uparrow \rangle } ^ { ( 2 ) } } \atop \frac { \lambda } { \gamma } \cdots } ^ { ( \frac { \lambda } { 2 } ) } \biggm \rangle + \frac { 1 } { 2 }  \underbrace { ( \overbrace { I _ { \langle \imath \downarrow \rangle } ^ { ( 2 ) } } ^ { ( \frac { \lambda } { 2 } ) } ) } _ { ( \frac { \lambda + 1 } { \gamma } ) } + \overbrace { \Biggl \langle \underbrace { Z _ { \langle \imath \uparrow \rangle } ^ { ( 2 ) } } \atop \frac { \lambda } { \gamma } \cdots } ^ { ( \frac { \lambda + 1 } { 2 } ) }  + \frac { 1 } { 2 } \overbrace { ( \underbrace { Z _ { \langle \imath \uparrow \rangle } ^ { ( 1 ) } } ) } ^ { ( \frac { \lambda - 1 } { \gamma } ) } + \overbrace { ( \underbrace { Z _ { \langle \imath \downarrow \rangle } ^ { ( 1 ) } } ) } ^ { ( \frac { \lambda } { \gamma } ) } + \overbrace { ( \underbrace { Z _ { \langle \imath \downarrow \rangle } ^ { ( 1 ) } } ) } ^ { ( \frac { \lambda } { \gamma + 1 } ) } + \frac { 1 } { 2 }  \underbrace { ( \overbrace { I _ { \langle \imath \downarrow \rangle } ^ { ( 1 ) } } ^ { ( \frac { \lambda } { 2 } ) } ) } _ { ( \underbrace { Z _ { \langle \imath \downarrow \rangle } ^ { ( 1 ) } } ) } } \\ & { } &  - \frac { 1 } { 2 } ( \frac { 1 } { 2 } \overbrace { [ \underbrace { I _ { \langle \imath \downarrow \rangle } ^ { ( 1 ) } } ] } ^ { ( \frac { \lambda - 1 } { \gamma } ) } ) + \underbrace { ( \overbrace { ( \frac { I _ { \langle \imath \downarrow \rangle } ^ { ( 1 ) } } ) } ^ { ( \frac { \lambda } { \gamma } ) } ) } _ { ( \underbrace { I _ { \langle \imath \downarrow \rangle } ^ { ( 1 ) } } ) } + \overbrace { [ \underbrace { I _ { \langle \imath \downarrow \rangle } ^ { ( 1 ) } } _ { \gamma \cdots } ] } ^ { ( \frac { \lambda } { \gamma } ) } + \frac { 1 } { 2 }  \underbrace { ( \frac { I _ { \langle \imath \downarrow \rangle } ^ { ( 1 ) } } { \gamma \cdots } ) } _ { ( \underbrace { I _ { \langle \imath \downarrow \rangle } ^ { ( 1 ) } } ) } - f ^  ( 2 ) \end{array}
$$

The remainder density $R _ { i i + 1 i + 2 } ^ { ( 2 ) }$ is exprsessa $( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } n _ { 2 } n _ { 3 } } ^ { m _ { 1 } m _ { 2 } m _ { 3 } }$ in complete analogy to (4.3). We determine Z(2)1i i+1i+2 from the requirement that the remainder density $R _ { i i + 1 i + 2 } ^ { ( 2 ) }$ isiesst $\frac { 1 } { \varepsilon }$ poles are absent in R(2 （24号 before adding $\mathcal { Z } _ { i i + 1 i + 2 } ^ { ( 2 ) }$ forc (4.11) of range and to average the range-two densities as in (4.25).

We have obtained explicit expressions of the remainder function (4.25) for all configurations up tomagnonnumberthree,i.e. $( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } }$ with $n _ { 1 } + n _ { 2 } + n _ { 3 } = m _ { 1 } + m _ { 2 } + m _ { 3 } \leq 3$ ： The densities can be written as linear combinations of 14 functions,which are partially related by relabelling the kinematical variables.The latter also enter in the form of

$$
\begin{array} { r } { u _ { i } = \frac { s _ { i i + 1 } } { s _ { i i + 1 i + 2 } } , \quad v _ { i } = \frac { s _ { i + 1 i + 2 } } { s _ { i i + 1 i + 2 } } , \quad w _ { i } = \frac { s _ { i i + 2 } } { s _ { i i + 1 i + 2 } } , } \end{array}
$$

where

$$
s _ { i i + 1 i + 2 } = s _ { i i + 1 } + s _ { i + 1 i + 2 } + s _ { i i + 2 } .
$$

Concretely, we can write

$$
( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } = ( { \vec { c } } _ { i } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } \cdot \vec { V _ { i } } \equiv \sum _ { k = 1 } ^ { 1 4 } [ ( { \vec { c } } _ { i } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } ] _ { k } [ { \vec { V _ { i } } } ] _ { k } ,
$$

where $\big [ \big ( \vec { c } _ { i } \big ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } \big ] _ { k }$ are rational functions of $u _ { i } , v _ { i } , w _ { i }$ and

$$
\begin{array} { r l } & { \dot { \bar { \tau } } _ { i } = \Bigg ( ( R _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { x x } , ( R _ { i } ^ { ( 2 ) } ) _ { Y X X } ^ { x x } \Big | _ { \mathrm { d e g \mathcal { S } } ^ { 2 } } ( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { x x } \Big | _ { \mathrm { d e g \mathcal { S } } ^ { 3 } } , \frac { \pi ^ { 2 } } { 6 } \log \big ( - \frac { s _ { \mathrm { s } + 1 , i + 2 } } { \mu ^ { 2 } } \big ) , - \frac { \pi ^ { 2 } } { 6 } \log \big ( - \frac { s _ { \mathrm { s } , i + 1 } } { \mu ^ { 2 } } \big ) , } \\ & { \quad \quad \log \big ( \frac { u _ { \mathrm { s } } } { \nu _ { i } } \big ) \log \big ( - \frac { s _ { \mathrm { s } + 1 , i + 1 } } { \mu ^ { 2 } } \big ) + \frac { \pi ^ { 2 } } { 3 } , \log \big ( \frac { u _ { \mathrm { s } } } { u _ { i } } \big ) \log \big ( - \frac { s _ { \mathrm { s } + 1 , i + 2 } } { \mu ^ { 2 } } \big ) + \frac { \pi ^ { 2 } } { 3 } , } \\ & { \quad \quad \mathrm { L i } _ { 2 } \big ( 1 - v _ { i } \big ) - \frac { 1 } { 2 } \log ^ { 2 } \big ( u _ { i } \big ) + \log \big ( u _ { i } \big ) \log \big ( v _ { i } \big ) - \frac { \pi ^ { 2 } } { 6 } , } \\ & { \quad \quad \mathrm { L i } _ { 2 } \big ( 1 - u _ { i } \big ) - \frac { 1 } { 2 } \log ^ { 2 } ( v _ { i } ) + \log ( u _ { i } ) \log \big ( v _ { i } \big ) - \frac { \pi ^ { 2 } } { 6 } , } \\ & { \quad \quad - \frac { \pi ^ { 2 } } { 6 } , \log \big ( u _ { i } \big ) , \log \big ( v _ { i } \big ) , \log \big ( - \frac { s _ { \mathrm { s } + 1 , i + 2 } } { \mu ^ { 2 } } \big ) , 1 \Bigg ) . } \end{array}
$$

In the vector $\vec { V _ { i } }$ ， the components are ordered according to their (decreasing） degree of transcendentality. The first component of $\vec { V _ { i } }$ has transcendentality four and is given by12

$$
\begin{array} { r l } { ( R _ { i } ^ { ( 2 ) } ) _ { x x x } ^ { x x } = - \mathrm { L i } _ { 4 } ( 1 - u _ { s } ) - \mathrm { L i } _ { 4 } ( u _ { s } ) + \mathrm { L i } _ { 4 } ( \frac { u _ { s } } { u _ { s } } ) - \log ( \frac { 1 - u _ { s } } { \omega _ { s } } ) [ \mathrm { L i } _ { 4 } ( \frac { u _ { s } } { u _ { s } } ) - \mathrm { L i } _ { 3 } ( 1 - u _ { s } ) ] } \\ & { - \log ( u _ { s } ) [ \mathrm { L i } _ { 4 } ( \frac { 1 - u _ { s } } { 1 - u _ { s } } ) + \mathrm { L i } _ { 3 } ( - \frac { w _ { s } } { u _ { s } } ) + \mathrm { L i } _ { 3 } ( \frac { 2 w _ { s } } { u _ { s } } ) - \frac { 1 } { 3 } \log ^ { 3 } { ( u _ { s } ) } - \frac { 1 } { 3 } \log ^ { 3 } { ( 1 - u _ { s } ) }  } \\ & {  - \mathrm { L i } _ { 2 } ( \frac { u _ { s } } { u _ { s } } ) \mathrm { L i } _ { 2 } ( \frac { 1 - u _ { s } } { 1 - u _ { s } } ) + \mathrm { L i } _ { 2 } ( u _ { s } ) [ \log ( \frac { 1 - u _ { s } } { 1 - u _ { s } } ) \log ( u _ { s } ) + \frac { 1 } { 2 } \log ^ { 2 } ( \frac { 1 - u _ { s } } { u _ { s } } ) ] } \\ & { + \frac { 1 } { 2 4 } \log ^ { 4 } { ( x _ { s } ) } - \frac { 1 } { 8 } \log ^ { 2 } { ( u _ { s } ) } \log ^ { 2 } { ( x _ { s } ) } - \frac { 1 } { 2 } \log ^ { 2 } { ( 1 - u _ { s } ) } \log { ( u _ { s } ) } \log ( \frac { u _ { s } } { u _ { s } } ) } \\ & { - \frac { 1 } { 2 } \log ( 1 - u _ { s } ) \log ^ { 2 } { ( u _ { s } ) } - \frac { 1 } { 6 } \log ^ { 3 } { ( u _ { s } ) } } \\ & { - \zeta _ { 2 } \log ( u _ { s } ) \log ( \frac { 1 - u _ { s } } { u _ { s } } ) + \frac { 1 } { 2 } \log ^ { 2 } { ( 1 - u _ { s } ) } - \frac { 1 } { 2 } \log ^ { 3 } { ( u _ { s } ) } } \\ &  + \zeta _ { 3 } \log ( u _ { s } ) + \frac { \zeta _ { 4 } } { 2 } \log ( \frac { 1 - u _ { s } } { u _ { s } } ) - \log ^  2  \end{array}
$$

It is the density of the BPS remainder first obtained in [17]. Moreover,

$$
\begin{array} { r l } & { R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y } \Big | _ { \mathrm { d e g : 3 } } = \bigg [ \mathrm { L i } _ { 3 } ( - \frac { u _ { i } } { w _ { i } } ) - \log ( u _ { i } ) \mathrm { L i } _ { 2 } ( \frac { v _ { i } } { 1 - u _ { i } } ) + \displaystyle \frac { 1 } { 2 } \log ( 1 - u _ { i } ) \log ( u _ { i } ) \log ( \frac { w _ { i } ^ { 2 } } { 1 - u _ { i } } ) } \\ & { \phantom { \frac { 1 } { 2 } } \quad \quad \quad \quad \quad - \displaystyle \frac { 1 } { 2 } \mathrm { L i } _ { 3 } ( - \frac { u _ { i } v _ { i } } { w _ { i } } ) - \frac { 1 } { 2 } \log ( u _ { i } ) \log ( v _ { i } ) \log ( w _ { i } ) - \frac { 1 } { 1 2 } \log ^ { 3 } ( w _ { i } ) + ( u _ { i }  v _ { i } ) \bigg ] } \\ & { \phantom { \frac { 1 } { 2 } } \quad \quad \quad \quad - \mathrm { L i } _ { 3 } ( 1 - v _ { i } ) + \mathrm { L i } _ { 3 } ( u _ { i } ) - \displaystyle \frac { 1 } { 2 } \log ^ { 2 } ( v _ { i } ) \log ( \frac { 1 - v _ { i } } { u _ { i } } ) + \displaystyle \frac { 1 } { 6 } \pi ^ { 2 } \log ( \frac { v _ { i } } { w _ { i } } ) } \\ & { \phantom { \frac { 1 } { 2 } } \quad \quad \quad \quad - \displaystyle \frac { 1 } { 6 } \pi ^ { 2 } \log \big ( - \frac { s _ { i } + 1 + 4 2 } { \mu ^ { 2 } } \big ) } \end{array}
$$

is the (up to relabelling) unique transcendentality-three contribution that occurs for remainders in the SU(2） sector built from the complex scalars $X$ and $Y$ [21]. Here and below, $\big | \mathrm { d e g } { - } k$ denotes the projection to the part of transcendentality degree $k$ . Note that at transcendentality two,besides the (up to relabelling) two functions encountered in the SU(2) sector

$$
\begin{array} { r l } & { ( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y X } \Big | _ { \mathrm { d e g - 2 } } = \frac { 1 } { 2 } [ \vec { V _ { i } } ] _ { 6 } + [ \vec { V _ { i } } ] _ { 7 } + [ \vec { V _ { i } } ] _ { 8 } + [ \vec { V _ { i } } ] _ { 9 } - [ \vec { V _ { i } } ] _ { 1 0 } , } \\ & { ( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y X } \Big | _ { \mathrm { d e g - 2 } } = - \frac { 1 } { 2 } [ \vec { V _ { i } } ] _ { 7 } - [ \vec { V _ { i } } ] _ { 9 } , } \end{array}
$$

only (up to relabelling) one further transcendentality-two function is required to express the transcendentality-two part of the remainder in the SL(2) sector. A similar relation holds for the functions at transcendentality one. Hence, compared to the SU(2) sector, an extended basis of functions with coefficients that contain ratios of Mandelstam variables is required. This goes also beyond the ${ \mathrm { S U } } ( 2 | 3 )$ case,where in addition to the remainder densities in the SU(2） sector with rational coeffcients only the constants $\pi ^ { 2 }$ and $\zeta _ { 3 }$ were encountered in [28]. The additional functions are still rather simple though.

One trivial symmetry of the remainder density is what is commonly called parity:

$$
( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } = ( R _ { i } ^ { ( 2 ) } ) _ { n _ { 3 } , n _ { 2 } , n _ { 1 } } ^ { m _ { 3 } , m _ { 2 } , m _ { 1 } } \Big | _ { s _ { i i + 1 }  s _ { i + 1 i + 2 } , u _ { i }  v _ { i } } ,
$$

which is a simple relabelling.13 This symmetry is already visible at the level of the integrand of the two-loop interaction density. Moreover, as a consequence of momentum conservation, the two-loop remainder obeys a relation analogous to (3.23) at one loop. It reads

$$
\begin{array} { r l } & { m _ { 1 } ( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } - 1 , m _ { 2 } , m _ { 3 } } + m _ { 2 } ( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } - 1 , m _ { 3 } } + m _ { 3 } ( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } - 1 } } \\ & { \ = ( n _ { 1 } + 1 ) ( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } + 1 , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } + ( n _ { 2 } + 1 ) ( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } + 1 , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } + ( n _ { 3 } + 1 ) ( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } + 1 } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } . } \end{array}
$$

Using this identity, we can reconstruct $( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } }$ from the knowledge of $( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , 0 , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } }$ （2 in complete analogy to (4.21):

$$
\begin{array} { c } { { ( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } = \displaystyle \frac { m _ { 1 } ! m _ { 2 } ! m _ { 3 } ! } { n _ { 1 } ! n _ { 2 } ! n _ { 3 } ! } \sum _ { j _ { 1 } = 0 } ^ { n _ { 2 } } \sum _ { j _ { 3 } = 0 } ^ { n _ { 2 } - j _ { 1 } } \sum _ { k _ { 1 } = 0 } ^ { n _ { 2 } - j _ { n 2 } - j _ { 1 } } \sum _ { k _ { 3 } = 0 } ^ { ( - 1 ) ^ { j } n _ { 2 } ! } \frac { ( - 1 ) ^ { j } n _ { 2 } ! } { j _ { 1 } ! j _ { 3 } ! k _ { 1 } ! k _ { 3 } ! ( n _ { 2 } - \ell ) ! } } } \\ { { \frac { ( n _ { 1 } + j _ { 1 } ) ! ( n _ { 3 } + j _ { 3 } ) ! } { ( m _ { 1 } - k _ { 1 } ) ! ( m _ { 2 } - n _ { 2 } + \ell ) ! ( m _ { 3 } - k _ { 3 } ) ! } ( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } + j _ { 1 } , 0 , n _ { 3 } + j _ { 3 } } ^ { m _ { 1 } - k _ { 1 } , m _ { 2 } - n _ { 2 } + \ell , m _ { 3 } - k _ { 3 } } , } } \end{array}
$$

where $j = j _ { 1 } + j _ { 3 }$ and $\ell = j + k _ { 1 } + k _ { 3 }$ .Thus,it isucenttolookat $( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , 0 , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } }$ with $n _ { 1 } \geq n _ { 3 }$ , and $m _ { 1 } > m _ { 3 }$ 证劵 $n _ { 1 } = n _ { 3 }$ . The correspondingcoeffcients )m1,m2,m3 are given in appendix B.

Inspecting the explicit expressions in the appendix, we observe several interesting patterns. Firstly, the highest transcendental part is universal:

$$
\lbrack ( \vec { c } _ { i } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } ] _ { 1 } = \delta _ { n _ { 1 } } ^ { m _ { 1 } } \delta _ { n _ { 2 } } ^ { m _ { 2 } } \delta _ { n _ { 3 } } ^ { m _ { 3 } } ,
$$

which is to say

$$
( R _ { i } ^ { ( 2 ) } ) _ { n _ { 1 } , n _ { 2 } , n _ { 3 } } ^ { m _ { 1 } , m _ { 2 } , m _ { 3 } } \Big | _ { \mathrm { d e g \ } 4 } = \delta _ { n _ { 1 } } ^ { m _ { 1 } } \delta _ { n _ { 2 } } ^ { m _ { 2 } } \delta _ { n _ { 3 } } ^ { m _ { 3 } } ( R _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { X X } .
$$

This property was already observed in [21] for the ${ \mathrm { S U } } ( 2 )$ sector and conjectured to extend to all operators. Secondly, also the coefficients of the transcendentality-three functions $[ \vec { V _ { i } } ] _ { 2 }$ （20 to $[ \vec { V _ { i } } ] _ { 5 }$ follow some interesting patterns. We analyse the following expressions as examples below

$$
\begin{array} { r l } & { \displaystyle \big ( \boldsymbol { R } _ { 2 } ^ { ( 2 ) } \big ) _ { m , \omega , \theta , \omega } ^ { - 3 , 0 } \Big | _ { \partial \varphi , \varphi } = - \sum _ { k = 1 } ^ { m } \frac { 1 } { k } \Big ( \frac { 1 - u _ { \omega } } { w _ { i } } \Big ) ^ { k } \underbrace { \big ( \boldsymbol { R } _ { i } ^ { ( 2 ) } \big ) _ { \le x \cdot \ x } } _ { | V _ { i } ^ { ( 2 ) } | _ { \le x } } - S _ { \omega } ^ { ( 1 ) } \underbrace { \big ( - 1 \big ) _ { \omega } ^ { \frac { \pi ^ { 2 } } { 2 } } \log \big ( - \frac { S _ { \omega + 1 , \omega - \varphi } } { R ^ { 2 } } \big ) } _ { | V _ { i } ^ { ( 2 ) } | _ { \le x } } , } \\ & { \displaystyle ( R _ { i } ^ { ( 2 ) } ) _ { m , \omega , \theta , \omega } ^ { - 3 , 0 } \Big | _ { \partial \varphi , \varphi } = \frac { 1 } { m } \underbrace { \big ( - 1 \big ) _ { \omega } ^ { \frac { \pi ^ { 2 } } { 2 } } \log \big ( - \frac { S _ { \omega + 1 , \omega + 2 } } { \theta ^ { 2 } } \big ) } _ { | V _ { i } ^ { ( 2 ) } | _ { \le x } } , } \\ & { \displaystyle ( R _ { i } ^ { ( 2 ) } ) _ { m , \omega , \theta , \omega } ^ { - 3 , 0 } \Big | _ { \partial \varphi , \varphi } = - \frac { \big ( - 1 \big ) _ { \omega } ^ { m } u _ { \omega } ^ { ( 2 ) } } { m } \underbrace { u _ { \omega } ^ { ( 2 ) } \big ( R _ { i } ^ { ( 2 ) } \big ) _ { \le x \cdot \ x } } _ { | V _ { i } ^ { ( 2 ) } | _ { \le x } \pi _ { i } ^ { ( 2 ) } } \Big | _ { \partial \varphi , \varphi } ( 4 , \varphi - \varphi ) , \qquad \mathrm { ( 4 . } } \\ & { \displaystyle ( R _ { i } ^ { ( 2 ) } ) _ { m , \omega , \theta , \omega } ^ { - 3 , 0 } \Big | _ { \partial \varphi , \varphi } , } \end{array}
$$

Similar patterns are encountered also in the coeffcients of the transcendentality-two functions; e.g.

$$
\displaystyle ( R _ { i } ^ { ( 2 ) } ) _ { m , 0 , 0 } ^ { 0 , m , 0 } \Big | _ { \mathrm { d e g - 2 } } = \frac { S _ { m } ^ { ( 1 ) } } { 2 m } \underbrace { \left( \log \left( \frac { u _ { i } } { v _ { i } } \right) \log \big ( - \frac { s _ { i i + 1 } } { \mu ^ { 2 } } \big ) + \frac { \pi ^ { 2 } } 3 \right) } _ { [ \widetilde V _ { i } ] _ { 6 } } + \left( - \frac { S _ { m } ^ { ( 1 ) } } { m } - \frac 1 { m ^ { 2 } } \right) \underbrace { ( - 1 ) \frac { \pi ^ { 2 } } 6 } _ { [ \widetilde V _ { i } ] _ { 1 0 } } .
$$

We see that the coeffcients of transcendental functions contain harmonic numbers and factors $\textstyle { \frac { 1 } { m } }$ ，where $\begin{array} { r } { \frac { 1 } { m } \equiv \frac { 1 } { m _ { j } - n _ { j } } } \end{array}$ for some $j$ . These are precisely the building blocks occurring in the one- and two-loop dilatation operator (3.18)，(4.19) and (4.20) and the one-loop finite terms (3.22). Moreover, we have generalisations of harmonic numbers which include $\scriptstyle \sum _ { k = 1 } ^ { m } { \frac { 1 } { k } } { \frac { ( 1 - u _ { i } ) ^ { k } } { w _ { i } ^ { k } } }$ $1 - u _ { i } = w _ { i }$ $S _ { m } ^ { ( 1 ) }$

The given matrix elements of the remainder function density have a formal transcendentality degree four if we attribute a degree to the above coefficients according to the following rules:

$$
S _ { m } ^ { ( l ) } \to l , \qquad \sum _ { k = 1 } ^ { m } { \frac { 1 } { k } } { \frac { ( 1 - u _ { i } ) ^ { k } } { w _ { i } ^ { k } } } \to 1 , \qquad { \frac { 1 } { m _ { i } - n _ { i } } } \to 1 , \qquad { \frac { 1 } { m _ { j } - n _ { j } } } { \frac { u _ { i } } { w _ { i } } } \to 1 .
$$

This generalises the property of hidden maximal transcendentality observed for the twoloop dilatation operator in the previous section to the case of functions of (ratios of) Mandelstam variables. In the limit of large spin,we have

$$
\operatorname* { l i m } _ { m \to \infty } S _ { m } ^ { ( l ) } = \zeta _ { l } , \qquad \operatorname* { l i m } _ { m \to \infty } \sum _ { k = 1 } ^ { m } \frac { 1 } { k } \left( \frac { 1 - u _ { i } } { w _ { i } } \right) ^ { k } = - \log \left( 1 - \frac { 1 - u _ { i } } { w _ { i } } \right) ,
$$

i.e. the result is of uniform maximal transcendentality in the usual sense.

It would be very interesting to understand the full pattern of the remainders, in particular to obtain a closed expression in analogy to (4.19)-(4.21) for the dilatation operator. In order to guess such an expresson，we would need more data for higher numbers of magnons. We leave this point for future work.

# 5 Conclusion and outlook

In this paper, we have computed the minimal form factors of composite operators in the （204号 $\operatorname { S L } ( 2 )$ sector of ${ \mathcal { N } } = 4$ SYM theory up to two-loop order. In particular, we have determined their finite remainders as well as the dilatation operator. The employed on-shell unitarity methods have once more proven to be an efficient tool in this context. Let us summarise the main results in some more detail:

· At one-loop order, we have calculated the full minimal form factor to all orders in the dimensional regularisation parameter. Extracting the one-loop dilatation operator from this data,we found perfect agreement with the existing literature. Moreover, we have extracted the previously unknown finite terms.   
· At two loops,we have determined the two-loop integrand for states with an arbitrary number of magnons and the complete form factor remainder and dilatation operator for states with up to three magnons,i.e. with up to three derivative insertions into the composite operator. Also here, the obtained dilatation operator matches with the closed expression that was determined previously.   
· While the remainders contain functions of lower transcendentality, we have observed that their coefficients follow some interesting patterns. These support the conjecture of a hidden uniform maximal transcendentality property, cf. section 1.

In order to confirm the above conjecture, the next logical step is to consider further examples of two-loop form factors. In particular, an important goal is to extend the above results to all composite operators in the SL(2） sector, i.e. to composite operators with more than three magnons. This requires a more efficient approach to the PV and IBP reduction of the general integrals (4.4)-(4.10). Although it would be desirable to solve the integrals for arbitrary magnon numbers,this is not strictly necessary. As the hidden uniform maximal transcendentality property conjectured above significantly constrains the dependence on the magnon numbers, we can fix the coefficients of an appropriate ansatz from explicit results with sufficiently high but finite magnon numbers. In order to better understand the transcendentality patterns, it may then be useful to consider the inverse Mellin transform of the remainder results.14

It would also be interesting to consider larger subsectors closed under renormalisation, such as the PSU(1,1|2） sector. The two-loop dilatation operator in this subsector can be computed via the iterative construction given in [54],which should provide a useful guideline. Finally, it would of course be very interesting to calculate the two-loop form factor remainder and the two-loop dilatation operator in the full theory, which is currently unknown. We believe that the study of $\mathrm { S L } ( 2 )$ form factors,with their new feature of non-compactness,provides an essential step in this direction.

While $\mathcal { N } = 4$ SYM theory is interesting in its own right, methods developed in the context of this model have often lead to broad applications, such as in QCD or pure YangMills theory. Apart from this,results from $\mathcal { N } = 4$ SYM theory are also useful building blocks in QCD. Notably, based on the so-called maximal transcendentality principle [55], the three-loop universal anomalous dimension was initially extracted [66] as the leading transcendentality contribution of the three-loop non-singlet splitting functions of QCD [79].15 Further evidence comes from the study of the three-point two-loop form factors of the stress-tensor supermultiplet in $\mathcal { N } = 4$ SYM theory [1O],where it was found that the two-loop remainder of ${ \mathcal N } = 4$ SYM theory matches exactly the leading transcendental part of the two-loop Higgs-to-three-gluon amplitude in QCD [82]. This generalises the maximal transcendentality principle from pure numbers to functions depending on the kinematics; see also [83].

Given these observations,it is plausible that the contribution to the QCD form factor remainder with the leading hidden transcendentality should coincide with the corresponding form factor remainder in ${ \mathcal N } = 4$ SYM theory. Again, the word ‘hidden' refers to the fact that besides harmonic numbers also factors such as mj=nj should formally be attributed a degree of transcendentality. A possible starting point to check this conjecture would be a comparison between the two-loop dilatation operator of $\mathcal { N } = 4$ SYM theory and QCD, see e.g. the recent work [84]. In [53], it was shown that the two-loop dilatation operator in the (scalar) $\mathrm { S L } ( 2 )$ sector of ${ \mathcal N } = 2$ SYM theory is indeed given by the expression in ${ \mathcal N } = 4$ （204号 SYM theory plus terms of lower transcendentality, which at least points into this direction. It would also be interesting to study the remainder functions of form factors in QCD with regard to this point.

# Acknowledgments

For helpful discussions and exchange, we would like to thank Lance Dixon, Burkhard Eden, Valentina Forini, Johannes Henn, Qing-Jun Jin, Thomas Klose, David Kosower,Anatoly Kotikov, Kasper Larsen, Dhritiman Nandan, Robert M. Schabinger, and in particular Grisha Korchemsky. M.W. would like to thank the KITPC/ITP-CAS for kind hospitality during the final phase of this project. The work of M.W. was supported by DFF-FNU through grant number DFF-4002-00037. G.Y. was supported in part by the Chinese Academy of Sciences (CAS) Hundred-Talent Program and by the Key Research Program of Frontier Sciences of CAS (Grant No. QYZDB-SSW-SYS014),and by a DFG grant in the framework of the SFB 647 “Raum-Zeit-Materie. Analytische und Geometrische Strukturen". We also thank the Marie Curie network GATIS (gatis.desy.eu) of the European Union's Seventh Framework Programme FP7/2007-2013/ under REA Grant Agreement No 317089 for support.

# A Explicit one-loop integral

In this appendix， we evaluate the one-loop integral (3.7） and show how to obtain the explicit result (3.9).

The integral (3.7)，shown here for $i = 1$ for simplicity, can be regarded as a certain component of the tensor integral

$$
\begin{array} { l } { { ( I _ { 1 } ^ { ( 1 ) } ) _ { m , n , \mu _ { 1 } \dots \mu _ { m + n } } = - s _ { 1 2 } ( \mathrm { e } ^ { \gamma _ { \mathrm { E } } } \mu ^ { 2 } ) ^ { 2 - \frac { D } { 2 } } \displaystyle \frac { 1 } { m ! n ! } \int \displaystyle \frac { \mathrm { d } ^ { D } l _ { 1 } } { i \pi ^ { \frac { D } { 2 } } } \displaystyle \frac { l _ { 1 } ( \mu _ { 1 } \dots l _ { 1 \mu _ { m } } l _ { 2 \mu _ { m + 1 } } \dots l _ { 2 \mu _ { m + n } } ) } { l _ { 1 } ^ { 2 } l _ { 2 } ^ { 2 } ( p _ { 1 } - l _ { 1 } ) ^ { 2 } } } } \\ { { = \displaystyle \sum _ { k = 0 } ^ { m + n } ( I _ { 1 } ^ { ( 1 ) } ) _ { m , n } ^ { k , l } \displaystyle \frac { p _ { 1 ( \mu _ { 1 } } \dots p _ { 1 \mu _ { k } } p _ { 2 \mu _ { k + 1 } } \dots p _ { 2 \mu _ { l + k } } ) } { k ! l ! } . } } \end{array}
$$

Here, $l _ { 2 } = p _ { 1 } + p _ { 2 } - l _ { 1 }$ ， $s _ { 1 2 } = ( p _ { 1 } + p _ { 2 } ) ^ { 2 } = 2 p _ { 1 } \cdot p _ { 2 }$ ， and the parentheses around the Lorentz indices indicate traceless symmetrisation w.r.t. the enclosed indices. The traceless symmetrised product built from a single momentum was given in [85] as

$$
( \mu _ { 1 } \dots l _ { \mu _ { n } } ) = \sum _ { \sigma \in \mathbb { S } _ { n } } \sum _ { j = 0 } ^ { [ \frac { n } { 2 } ] } \frac { ( - 1 ) ^ { j } \Gamma ( \frac { D } { 2 } + n - j - 1 ) } { 2 ^ { 2 j } j ! \left( n - 2 j \right) ! \Gamma ( \frac { D } { 2 } + n - 1 ) } l ^ { 2 j } \eta _ { \mu _ { \sigma _ { 1 } \mu _ { \sigma _ { 2 } } } } \dots \eta _ { \mu _ { \sigma _ { 2 j - 1 } } \mu _ { \sigma _ { 2 j } } } l _ { \mu _ { \sigma _ { 2 j + 1 } } } \dots l _ { \mu _ { \sigma _ { n } } } \ ,
$$

where $\mathbb { S } _ { n }$ denotes the group of permutations of $n$ elements and $\eta _ { \mu \nu }$ is the metric of $D$ 1 dimensional Minkowski space in the mostly-minus convention. The above expression is identical to the ordinary product if the momentum $l$ is on-shell. Using the above result, an expression for the numerator of the integral in (A.1) can be found:

$$
\begin{array} { l } { { l _ { 1 } { _ { ( \mu _ { 1 } \dots l _ { 1 \mu _ { m } } l _ { 2 \mu _ { m + 1 } } \dots l _ { 2 \mu _ { m + n } } ) } } } } \\ { { = { \displaystyle \frac { 1 } { ( m + n ) ! } \sum _ { \sigma \in \mathbb { S } _ { m + n } } \sum _ { j = 0 } ^ { \operatorname* { m i n } ( m , n ) } \frac { ( - 1 ) ^ { j } m ! n ! \Gamma ( \frac { D } { 2 } + m + n - j - 1 ) } { 2 ^ { j } j ! ( m - j ) ! ( n - j ) ! \Gamma ( \frac { D } { 2 } + m + n - 1 ) } } ( l _ { 1 } \cdot l _ { 2 } ) ^ { j } } } \\ { { \qquad \quad \eta _ { \mu _ { \sigma _ { 1 } } \mu _ { \sigma _ { m + 1 } } } \dots \eta _ { \mu _ { \sigma _ { j } } \mu _ { \sigma _ { m + j } } } l _ { 1 } ( \mu _ { \sigma _ { j + 1 } } \dots l _ { 1 \mu _ { \sigma _ { m } } } ) l _ { 2 ( \mu _ { \sigma _ { m + j + 1 } } \dots l _ { 2 \mu _ { \sigma _ { m + n } } } ) } . } } \end{array}
$$

If the momenta $l _ { 1 }$ and $l _ { 2 }$ are on-shell, the traceless symmetric products on the r.h.s. become ordinary products. It is easy to see that in this case the contraction of two of these tensor products with rank $m + n$ yields zero unless the two tensor products are related al exs str $m$ 1 $n$ tTisemilest o $( I _ { 1 } ^ { ( 1 ) } ) _ { m , n } ^ { k , l }$   
$p _ { 2 } ^ { ( \mu _ { 1 } } \cdot \cdot \cdot p _ { 2 } ^ { \mu _ { k } } p _ { 1 } ^ { \mu _ { k + 1 } } \cdot \cdot \cdot p _ { 1 } ^ { \mu _ { k + l } ) }$ ，where $k + l = m + n$ ：

$$
\begin{array} { l } { { ( I _ { 1 } ^ { ( 1 ) } ) _ { m , n } ^ { k , l } = - \displaystyle \frac { s _ { 1 2 } ^ { 1 - m - n } } { P _ { k l } } ( \mathrm { e } ^ { \gamma _ { \mathrm { E } } } \mu ^ { 2 } ) ^ { 2 - \frac { D } { 2 } } \displaystyle \frac { k ! l ! } { m ! n ! } } } \\  { { \phantom { ( } \int \displaystyle \frac { \mathrm { d } ^ { D } l _ { 1 } } { i \pi ^ { \frac { D } { 2 } } } \displaystyle \frac { l _ { 1 } ( \mu _ { 1 } \dots l _ { 1 \mu _ { m } } l _ { 2 \mu _ { m + 1 } } \dots l _ { 2 \mu _ { m + n } } ) ^ { p _ { 2 } ^ { \mu _ { 1 } } } \dots p _ { 2 } ^ { \mu _ { k } } p _ { 1 } ^ { \mu _ { k + 1 } } \dots p _ { 1 } ^ { \mu _ { k + l } } } { l _ { 1 } ^ { 2 } l _ { 2 } ^ { 2 } ( p _ { 1 } - l _ { 1 } ) ^ { 2 } } ~ , } } \end{array}
$$

where

$$
\begin{array} { l } { { P _ { m , n } = \displaystyle \frac { 1 } { s _ { 1 2 } ^ { m + n } } p _ { 1 } ( \mu _ { 1 } \cdot \cdot \cdot p _ { 1 \mu _ { m } } p _ { 2 \mu _ { m + 1 } } \cdot \cdot \cdot p _ { 2 \mu _ { m + n } } ) p _ { 2 } ^ { \mu _ { 1 } } \cdot \cdot \cdot p _ { 2 } ^ { \mu _ { m } } p _ { 1 } ^ { \mu _ { m + 1 } } \cdot \cdot \cdot p _ { 1 } ^ { \mu _ { m + n } } = \displaystyle \frac { m ! n ! } { ( m + n ) ! } Q _ { m , n } , } } \\ { { 2 _ { m , n } = \displaystyle \frac { 1 } { s _ { 1 2 } ^ { m + n } } q _ { ( \mu _ { 1 } } \cdot \cdot \cdot q _ { \mu _ { m + n } ) } p _ { 2 } ^ { \mu _ { 1 } } \cdot \cdot \cdot p _ { 2 } ^ { \mu _ { m } } p _ { 1 } ^ { \mu _ { m + 1 } } \cdot \cdot \cdot p _ { 1 } ^ { \mu _ { m + n } } } } \\ { { \displaystyle \quad \quad = - \frac { 1 } { 2 ^ { m + n } } \displaystyle \frac { \Gamma ( \frac { D } { 2 } + m - 1 ) \Gamma ( \frac { D } { 2 } + n - 1 ) } { \Gamma ( \frac { D } { 2 } + m + n - 1 ) } \Gamma ( 2 - \frac { D } { 2 } ) \frac { \sin { \frac { \pi D } { 2 } } } { \pi } . } } \end{array}
$$

Here, $q = p _ { 1 } + p _ { 2 } $ with $q ^ { 2 } = s _ { 1 2 } < 0$ denotes an off-shell momentum which should not be confused with the total momentum used in the main text. These latter expressions follow from contractions of (A.3) and (A.2) in which $l _ { 1 }$ ， $l _ { 2 }$ are replaced by $p _ { 1 }$ ， $p _ { 2 }$ and $l$ is replaced by $q$ ，respectively. The expression for $Q _ { m , n }$ ，which is manifestly symmetric in $m$ and $n$ （20 as expected, was obtained by also making use of the reflection formula for the Gamma functions:

$$
\Gamma ( z ) \Gamma ( 1 - z ) = \frac { \pi } { \sin \pi z } .
$$

The numerator in (A.4) is given bycontracting (A.3） with $p _ { 2 } ^ { ( \mu _ { 1 } } \ldots p _ { 2 } ^ { \mu _ { k } } p _ { 1 } ^ { \mu _ { k + 1 } } \ldots { p _ { 1 } ^ { \mu _ { k + l } ) } }$ where $k + l = m + n$ . This yields

$$
\begin{array} { l } { { l _ { 1 } { _ { ( \mu _ { 1 } \ddots l _ { 1 } \mu _ { m } l _ { 2 } \mu _ { m + 1 } \ldots l _ { 2 \mu _ { m + n } } ) } { p _ { 2 } ^ { \mu _ { 1 } } } \ldots p _ { 2 } ^ { \mu _ { k } } { p _ { 1 } ^ { \mu _ { k + 1 } } } \ldots p _ { 1 } ^ { \mu _ { k + i } } } } } \\  { \ = { \frac { m ! n ! } { ( m + n ) ! } } \displaystyle { \sum _ { j = 0 } ^ { \operatorname* { m i n } ( m , n , k , l ) } { { \frac { ( - 1 ) ^ { j } k ! l ! \Gamma ( { \frac { D } { 2 } } + m + n - j - 1 ) } { j ! ( k - j ) ! \Gamma ( { \frac { D } { 2 } } + m + n - n - 1 ) } } { ( l _ { 1 } \cdot l _ { 2 } ) ^ { j } } { ( p _ { 1 } \cdot p _ { 2 } ) ^ { j } } } } } \\ { { \displaystyle { \sum _ { r = \operatorname* { m a x } ( k - n , 0 ) } ^ { \operatorname* { m i n } ( m , k ) - j } { \binom { k - j } { r } } \binom { l - j } { m - j - r } { l _ { 1 } ( _ { \nu _ { 1 } } \ldots l _ { 1 \nu _ { m - j } } ) p _ { 2 } ^ { \nu _ { 1 } } } \ldots p _ { 2 } ^ { \nu _ { r } } p _ { 1 } ^ { \nu _ { r } + 1 } \ldots p _ { 1 } ^ { \nu _ { m - j } } } } } \\ { { \ } } \\ { { l _ { 2 ( \rho _ { 1 } \cdot \cdot \cdot \cdot l _ { 2 } \rho _ { n - j } ) } { p _ { 2 } ^ { \rho _ { 1 } } } \ldots p _ { 2 } ^ { \rho _ { k - j - r } } p _ { 1 } ^ { \rho _ { k - j - r + 1 } } \ldots p _ { 1 } ^ { \rho _ { n - j } } \ldots { p _ { 1 } ^ { \rho _ { n - j - r } } } . } } \end{array}
$$

In the integral (A.4),all numerator terms that contain $l _ { 1 } ^ { 2 }$ or $l _ { 2 } ^ { 2 }$ lead to (massless） bubble integrals with a single on-shell momentum,which vanish.Hence, the traceless symmetric products on the r.h.s. of the above expression can be regarded as ordinary products. Moreover, $l _ { 1 } \cdot l _ { 2 }$ can be replaced by $p _ { 1 } \cdot p _ { 2 }$ . These changes do not alter the result of the integral, which can thus be expressed as

$$
\begin{array} { c } { { - s _ { 1 2 } ( \mathrm { e } ^ { ; \pi } \mu ^ { 2 } ) ^ { 2 - \frac { p } { 2 } } \displaystyle \int \displaystyle \frac { \mathrm { d } D } { i \pi ^ { \frac { p } { 2 } } } \frac { \mathrm { d } ( \mu _ { 1 } \dots \dots \lfloor \mathrm { l } _ { \mu \mathrm { m } } l _ { 2 \mu _ { m - 1 } } \dots \lfloor \mathrm { ~ } \lambda _ { 2 \mu _ { m + n } } ) p _ { 2 } ^ { \mu _ { 2 } } \dots , p _ { 2 } ^ { \mu _ { k } } p _ { 1 } ^ { \mu _ { k + 1 } } \dots \dots \mu _ { 1 } ^ { \mu _ { k + i } } } } } \\ { { \displaystyle \sum _ { i = m + n } \operatorname* { m i n } \displaystyle \sum _ { j = 0 } ^ { m + n } \displaystyle \sum _ { j = 0 } ^ { k } \frac { ( - 1 ) ^ { j } k ! l ! \Gamma ( \frac { p } { 2 } + m + n - j - 1 ) } { j ! ( k - j ) ! ( l - j ) ! \Gamma ( \frac { p } { 2 } + m + n - 1 ) } } } \\ { { \displaystyle \operatorname* { m i n } ( \operatorname* { m a x } \mu ) ^ { - j } } } \\ { { \displaystyle \sum _ { r = 0 } ^ { \operatorname* { m a x } \binom { k - n } { ( k - n ) 0 } } ( \begin{array} { c } { { k - j } } \\ { { r } } \end{array} ) \binom { l - j } { m - j - r } ) \sum _ { s = 0 } ^ { k - j - r } \binom { k - j - r } { s } ( - 1 ) ^ { s } } } \\ { { \displaystyle \sum _ { i = 0 } ^ { n - k + r } \binom { n - k + r } { \ell } ( - 1 ) ^ { t } ( p _ { 1 } \dots p _ { 2 } ) ^ { n + j - s - t } I _ { r _ { 1 } , s , m - j - r ; \ell } , } } \end{array}
$$

where we also have inserted $l _ { 2 } = p _ { 1 } + p _ { 2 } - l _ { 1 }$ and then expanded the obtained binomial products.

The integral that occurs in the above expression is given by

$$
\begin{array} { l } { { { \cal I } _ { m , n } = - s _ { 1 2 } ( \mathrm { e } ^ { \gamma _ { \mathrm { E } } } \mu ^ { 2 } ) ^ { 2 - \frac { D } { 2 } } \displaystyle \int \displaystyle \frac { \mathrm { d } ^ { D } l _ { 1 } } { i \pi ^ { \frac { D } { 2 } } } \displaystyle \frac { ( l _ { 1 } \cdot p _ { 2 } ) ^ { m } ( l _ { 1 } \cdot p _ { 1 } ) ^ { n } } { l _ { 1 } ^ { 2 } l _ { 2 } ^ { 2 } ( p _ { 1 } - l _ { 1 } ) ^ { 2 } } } } \\ { { = - \left( \displaystyle \frac { s _ { 1 2 } } { 2 } \right) ^ { m + n } \displaystyle \frac { ( - 1 ) ^ { n } \Gamma ( 2 - \frac { D } { 2 } ) } { \Gamma ( 3 - n - \frac { D } { 2 } ) } \displaystyle \frac { \Gamma ( D - 2 ) \Gamma ( \frac { D } { 2 } + m - 1 ) } { \Gamma ( \frac { D } { 2 } - 1 ) \Gamma ( D + m + n - 3 ) } = { \cal C } \displaystyle \binom { \nu _ { 1 } } { \nu _ { 2 } } . } } \end{array}
$$

as explained below. The diagram denotes the standard scalar bubble integral, i.e.

$$
\begin{array} { r c l } { { } } & { { } } & { { = \displaystyle { \longrightarrow } \Bigg \langle } } \\ { { } } & { { } } & { { = \displaystyle { ( \mathrm { e } ^ { \gamma _ { \mathrm { E } } } \mu ^ { 2 } ) ^ { 2 - \frac { D } { 2 } } \int \frac { \mathrm { d } ^ { D } l } { i \pi ^ { \frac D 2 } } \overline { { { l ^ { 2 } ( p _ { 1 } + p _ { 2 } - l ) ^ { 2 } } } } } } } \\ { { } } & { { } } & { { = \displaystyle { \mathrm { e } ^ { ( 2 - \frac D 2 ) \gamma _ { \mathrm { E } } } \frac { \Gamma ( \frac D 2 - 1 ) ^ { 2 } \Gamma ( 2 - \frac D 2 ) } { \Gamma ( D - 2 ) } \Big ( \frac { \mu ^ { 2 } } { - s _ { 1 2 } } \Big ) ^ { 2 - \frac { D } { 2 } } . } } } \end{array}
$$

In the case $n \geq 1$ ， the result (A.9） can straightforwardly be obtained by using $l _ { 1 } \cdot p _ { 1 } =$ $\scriptstyle { \frac { 1 } { 2 } } ( l _ { 1 } ^ { 2 } - ( l _ { 1 } - p _ { 1 } ) ^ { 2 } )$ for one of the numerator factors and exploiting the fact that the cancellation of $l _ { 1 } ^ { 2 }$ in the denominator yields a (massless) bubble integral with a single external on-shell momentum, which hence vanishes. In the special case $n = 0$ but $m \geq 1$ , one shifts the loop momentum as $l _ { 1 } = \tilde { l } _ { 1 } + p _ { 1 }$ and expands the power of $( \tilde { l } _ { 1 } + p _ { 1 } ) \cdot p _ { 2 }$ in a binomial series, then using $\begin{array} { r } { \vec { l } _ { 1 } \cdot p _ { 2 } = \frac { 1 } { 2 } ( \vec { l } _ { 1 } ^ { 2 } - ( \vec { l } _ { 1 } - p _ { 2 } ) ^ { 2 } ) } \end{array}$ for one of the numerator factors of the resulting integrals. The resulting (massless） bubble integrals are either zero since they depend only on one external on-shell momentum or they can be evaluated using (see e.g. [86])

$$
( \mathrm { e } ^ { \mathrm { \gamma \kappa } } \mu ^ { 2 } ) ^ { 2 - \frac { D } { 2 } } \int \frac { \mathrm { d } ^ { D } l } { i \pi ^ { \frac { D } { 2 } } } \frac { l _ { ( \mu _ { 1 } } \ldots l _ { \mu _ { n } ) } } { l ^ { 2 } ( l - q ) ^ { 2 } } = q _ { ( \mu _ { 1 } } \ldots q _ { \mu _ { n } ) } \frac { \Gamma ( \frac { D } { 2 } + n - 1 ) } { \Gamma ( D + n - 2 ) } \frac { \Gamma ( D - 2 ) } { \Gamma ( \frac { D } { 2 } - 1 ) } = { \cal C } \bigcup _ { \ L _ { p , \ L } } \ .
$$

Finally, also the scalar triangle diagram occurs, in particular for $n = m = 0$ but also in the binomial expansions. It can be related to the bubble integral via

$$
\overline { { \frac { \ d S } { \ d t } } } = \frac { 1 } { s _ { 1 2 } } \frac { 2 ( D - 3 ) } { 4 - D } = \widetilde { \ d S } _ { \frac { \ d S } { \ d t } } ^ { \ d S _ { 1 } } .
$$

A resummation of the binomial series yields a result which is in accordance with (A.9) for $n = 0$ ：

After inserting (A.9) into (A.8), the sums over $s$ and $t$ can be performed,and after

also applying the reflection formula (A.6),the expression reads

$$
- s _ { 1 2 } ( \mathrm { e } ^ { \gamma \mathrm { E } } \mu ^ { 2 } ) ^ { 2 - \frac { D } { 2 } } \int \frac { \mathrm { d } ^ { D } l _ { 1 } } { i \pi ^ { \frac { D } { 2 } } } \frac { l _ { 1 ( \mu _ { 1 } } \ldots l _ { 1 \mu _ { m } } l _ { 2 \mu _ { m + 1 } } \ldots l _ { 2 \mu _ { m + n } } ) p _ { 2 } ^ { \mu _ { 1 } } \ldots p _ { 2 } ^ { \mu _ { k } } p _ { 1 } ^ { \mu _ { k } + 1 } \ldots p _ { 1 } ^ { \mu _ { k } + \mu _ { m + 1 } } \ldots l _ { k } } { l _ { 1 } ^ { 2 } l _ { 2 } ^ { 2 } ( p _ { 1 } - l _ { 1 } ) ^ { 2 } } \ ,
$$

$$
\begin{array} { l } { \displaystyle \sum _ { j = 0 } ^ { \operatorname* { m i n } ( m , n , k , l ) } \frac { ( - 1 ) ^ { j } k ! l ! \Gamma ( \frac { D } { 2 } + m + n - j - 1 ) } { j ! ( k - j ) ! ( l - j ) ! \Gamma ( \frac { D } { 2 } + m + n - 1 ) } \sum _ { r = \operatorname* { m a x } ( 0 , l - n ) } ^ { \operatorname* { m i n } ( l , m ) - j } { \binom { k - j } { m - j - r } } \binom { l - j } { r } } \\ { \displaystyle \qquad \frac { \Gamma ( \frac { D } { 2 } - m + k + 2 r - 2 ) \Gamma ( \frac { D } { 2 } + m + l - 2 j - 2 r - 1 ) } { \Gamma ( D + m + n - 2 j - 3 ) } . } \end{array}
$$

Inserting this result and (A.5) into (A.4), we finally obtain for the coeffcients in (A.1):

$$
\begin{array} { l } { \displaystyle \frac { k ! l ! } { \Gamma ( \frac { D } { 2 } + k - 1 ) \Gamma ( \frac { D } { 2 } + l - 1 ) } \frac { \Gamma ( D - 2 ) } { \Gamma ( \frac { D } { 2 } - 1 ) } = \bigcup _ { \substack { p _ { 2 } } } } \\ { \displaystyle \operatorname* { m i n } _ { j = 0 } ^ { ( m , n , k , l ) } \frac { ( - 1 ) ^ { j } \Gamma ( \frac { D } { 2 } + m + n - j - 1 ) } { j ! ( k - j ) ! ( l - j ) ! } \sum _ { \substack { r = \operatorname* { m a x } ( 0 , l - n ) } } ^ { \operatorname* { m i n } ( l , m ) - j } \binom { k - j } { m - j - r } \binom { l - j } { r } } \\ { \displaystyle \qquad \frac { \Gamma ( \frac { D } { 2 } - m + k + 2 r - 2 ) \Gamma ( \frac { D } { 2 } + m + l - 2 j - 2 r - 1 ) } { \Gamma ( D + m + n - 2 j - 3 ) } . } \end{array}
$$

# B Remainder densities

In this appendix, we give the remainder densities up to spin three in the notation introduced in (4.28).

$$
\begin{array} { r l } &  \begin{array} { r l } & { \langle \tilde { c } \rangle _ { 1 , 0 , 0 , 0 } ^ { 0 , 0 , 0 } - \langle 1 , 1 , 0 , 0 , 0 , 1 , 0 , 0 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 \rangle } \\ & { \langle \tilde { c } \rangle _ { 1 , 0 , 0 } ^ { 0 , 0 , 1 } = ( ( \begin{array} { l } { 0 , \frac { 1 } { w _ { 1 } } , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 \rangle } \\ { 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 \rangle } \end{array} ) } \\ &  \begin{array} { r l } { \langle \tilde { c } \rangle _ { 1 , 0 , 0 } ^ { 0 , 1 } = ( ( \begin{array} { l } { 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 \rangle ) } \\ { 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 \rangle } \end{array} } \\ & { \begin{array} { r l } { \langle \tilde { c } \rangle _ { 1 , 0 , 0 } ^ { 1 , 0 } = ( ( 1 , \frac { 1 } { w _ { 1 } } , - \frac { 1 } { w _ { 1 } } , 0 , 0 , - 1 , 0 , - \frac { \sqrt { 1 - w _ { 1 } } } { 2 w _ { 1 } } , - \frac { 1 } { 2 w _ { 1 } } , - \frac { 1 } { 2 w _ { 1 } } , - \frac { 1 } { w _ { 1 } } , \frac { 1 } { w _ { 1 } } , \frac { 1 } { w _ { 1 } } , - \frac { 1 } { w _ { 1 } } , \frac { 1 } { w _ { 1 } } , \frac { 1 } { w _ { 1 } } , \frac { 1 - w _ { 1 } } { w _ { 1 } } , - \frac { 1 } { w _ { 1 } } , \frac { 1 - w _ { 1 } } { w _ { 1 } } , - \frac { 1 } { w _ { 1 } } , \frac { 1 } { w _ { 1 } } ) } \\ & { - 1 , \frac { \sqrt { 1 - w _ { 1 } } } { 2 } } \end{array} } \end{array} \end{array} \end{array}
$$

$$
\begin{array} { r l } { \frac { \varepsilon _ { 1 } ^ { ( 1 ) } } { \varepsilon _ { 1 } ^ { ( 2 ) } } } & { = ( \begin{array} { l l l l l l l } { 1 } & { 1 } & { 1 } & { 1 } & { 0 } & { 1 } & { 0 } \\ { 0 } & { 1 } & { 0 } & { 0 } & { 1 } & { 0 } \\ { 0 } & { 0 } & { 1 } & { 0 } & { 0 } & { 1 } \end{array} ) ^ { 2 } ( \begin{array} { l l l l l } { 1 } & { - \varepsilon _ { 1 } } & { 1 } & { 0 } & { \varepsilon _ { 1 } ^ { ( 2 ) } } & { 0 } \\ { 0 } & { 1 } & { 0 } & { 2 } & { 1 } & { 0 } \\ { 0 } & { 0 } & { 1 } & { 0 } & { 2 } & { 0 } \\ { 0 } & { 0 } & { 1 } & { 0 } & { 0 } & { 2 } \end{array} ) ^ { 2 } } \\ &  = ( \begin{array} { l l l l l l } { \frac { 2 ( 1 - \nu ) \varepsilon _ { 1 } } { \nu _ { 1 } \nu _ { 1 } } } & { \frac { \varepsilon _ { 1 } ^ { ( 2 ) } } { \nu _ { 1 } \nu _ { 1 } } } & { \frac { \varepsilon _ { 1 } ^ { ( 3 ) } } { \nu _ { 2 } } } & { \frac { \varepsilon _ { 1 } ^ { ( 4 ) } } { \nu _ { 1 } } } & { \frac { \varepsilon _ { 1 } ^ { ( 4 ) } } { \nu _ { 1 } ^ { ( 2 ) } } } & { \frac { 2 \nu _ { 2 } \nu _ { 1 } } { \nu _ { 1 } } } & { \frac { 2 } { \nu _ { 1 } ^ { ( 2 ) } } } & { \frac { 2 \nu _ { 2 } } { \nu _ { 1 } } } & { \frac { 3 } { \nu _ { 1 } ^ { ( 2 ) } } } \\ { 0 } & { - \frac { \nu _ { 1 } ( 1 - \nu ) \varepsilon _ { 1 } } { \nu _ { 1 } \nu _ { 1 } } } & { \frac { \varepsilon _ { 1 } ^ { ( 4 ) } } { \nu _ { 1 } \nu _ { 1 } } } & { \frac { \varepsilon _ { 1 } ^ { ( 4 ) } } { \nu _ { 1 } \nu _ { 1 } } } &  \frac { \varepsilon _ { 1 } ^ { ( 2 ) } } { \nu _ { 1 } \nu _ { 1 } } & { \frac { 3 \varepsilon _ { 1 } ^ { ( 2 ) } } } & { \frac { 2 \nu _ { 1 } } { \nu _ { 1 } \nu _ { 1 } } } & { \frac { 2 ( 1 - \nu ) \varepsilon _ { 1 } } { \nu _ { 1 } \nu _ { 1 } } } & { 0 } \\ & { - \frac { \nu _ { 1 } ( 1 - \nu ) \varepsilon _ { 1 } } { \nu _ { 1 } \nu _ { 1 } } } &  \frac   \end{array} \end{array}
$$$$
\begin{array} { c } { { ( \vec { c } _ { i } ) _ { 2 , 0 , 0 } ^ { 0 , 0 , 2 } = \left( 0 , - \displaystyle { \frac { u _ { i } ^ { 2 } } { 2 w _ { i } ^ { 2 } } } , 0 , 0 , 0 , \displaystyle { \frac { v _ { i } u _ { i } ^ { 2 } } { 4 ( 1 - u _ { i } ) w _ { i } ^ { 2 } } } - \displaystyle { \frac { u _ { i } ^ { 2 } } { 8 w _ { i } ^ { 2 } } } - \displaystyle { \frac { 1 } { 8 } } , \displaystyle { \frac { u _ { i } ^ { 2 } v _ { i } } { 4 ( 1 - u _ { i } ) w _ { i } ^ { 2 } } } - \displaystyle { \frac { u _ { i } ^ { 2 } } { 8 w _ { i } ^ { 2 } } } , \displaystyle { \frac { u _ { i } ^ { 2 } } { 4 w _ { i } ^ { 2 } } } \right. } } \\ { { \displaystyle \left. - \displaystyle { \frac { 1 } { 4 } } , \displaystyle { \frac { u _ { i } ^ { 2 } v _ { i } } { 2 ( 1 - u _ { i } ) w _ { i } ^ { 2 } } } - \displaystyle { \frac { u _ { i } ^ { 2 } } { 4 w _ { i } ^ { 2 } } } , \displaystyle { \frac { u _ { i } ^ { 2 } v _ { i } } { 2 ( 1 - u _ { i } ) w _ { i } ^ { 2 } } } - \displaystyle { \frac { u _ { i } ^ { 2 } } { 4 w _ { i } ^ { 2 } } } , \displaystyle { \frac { 3 u _ { i } ^ { 2 } } { 4 ( 1 - u _ { i } ) w _ { i } } } + \displaystyle { \frac { 1 } { 4 } } , \displaystyle { \frac { 3 u _ { i } } { 4 w _ { i } } } - \displaystyle { \frac { 3 } { 8 } } , - \displaystyle { \frac { 1 } { 8 } } , \displaystyle { \frac { 1 5 } { 3 2 } } \right. } } \end{array}
$$

$$
\begin{array} { r l } & { v _ { 1 2 , 0 , 0 } ^ { ( - 1 ) , 1 } = \left( \int _ { 0 } ^ { 1 } \frac { \partial v _ { 1 } } { \partial x _ { 0 } ^ { 0 } } \left( v _ { 1 } \partial _ { x } \partial _ { x } \partial _ { y } - \frac { 1 } { \sqrt { 3 } \partial x _ { 0 } ^ { 0 } } \right) - \frac { 1 } { \sqrt { 3 } \omega _ { 0 } } v _ { 1 } - \frac { 1 } { \sqrt { 3 } \omega _ { 0 } } v _ { 2 } - \frac { \sin _ { x } } { 2 \omega _ { 0 } } - \frac { \sin _ { x } } { 2 \omega _ { 0 } } - \frac { 1 } { \sqrt { 3 } \omega _ { 0 } } \frac { \sin _ { y } } { \sqrt { 3 } } - \frac { \sin _ { y } } { 2 } \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } \right) } \\ & { - \frac { 1 } { \sqrt { 3 } \omega _ { 0 } } v _ { 1 } - \frac { 1 } { \sqrt { 3 } \omega _ { 0 } } v _ { 1 } \sin _ { x } - \frac { 1 } { \sqrt { 3 } \omega _ { 0 } } \frac { \sin _ { x } } { \sqrt { 3 } } - \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } } \\ &  \mathrm { ( E _ { x } ^ { - 1 , 0 } \partial _ { x } \partial _ { y } - \left( \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } \right) - \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } - \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } \omega _ { 0 } } - \frac { \sin _ { x } } { 2 \omega _ { 0 } } - \frac { \sin _ { y } } { 2 \omega _ { 0 } } - \frac { \sin _ { x } } { 2 \omega _ { 0 } } - \frac { \sin _ { y } } { 2 \omega _ { 0 } } , \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } \right. } \\ & { \left. \qquad - \frac { \sin _ { x } } { \sqrt { 3 } \omega _ { 0 } } \frac { \sin _ { x } } { \sqrt { 3 } \omega _ { 0 } } - \frac { 1 } { \sqrt { 3 } \omega _ { 0 } } \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } \frac { 1 } { \sqrt { 3 } } \right. } \\ &  \left. \qquad - \frac { 1 } { \sqrt { 3 } \omega _ { 0 } } \frac { \sin _ { x } }  \sqrt { 3 } \omega _  0  \end{array}
$$

$$
\begin{array} { r l r } { \zeta _ { 1 } ^ { 1 0 , 0 3 } = \binom { 0 } { 4 } - \frac { 3 w _ { 1 } ^ { 2 } } { 2 w _ { 2 } ^ { 2 } } , 0 , 0 , 0 , - \frac { w _ { 3 } ^ { 2 } } { 2 w _ { 1 } ^ { 3 } } + \frac { 3 w _ { 1 } ^ { 4 } w _ { 2 } ^ { 2 } } { 4 ( 1 - w _ { 2 } ) w _ { 1 } ^ { 2 } } - \frac { 9 w _ { 2 } ^ { 2 } } { 8 w _ { 3 } ^ { 2 } } - \frac { 1 } { 8 } , - \frac { 5 w _ { 1 } ^ { 4 } } { 8 ( 1 - w _ { 3 } ) w _ { 3 } ^ { 3 } } + \frac { 7 w _ { 3 } ^ { 3 } } { 4 ( 1 - w _ { 4 } ) w _ { 2 } ^ { 3 } } } & \\ { } & { } & { - \frac { 3 w _ { 1 } ^ { 2 } w _ { 2 } ^ { 2 } } { 4 ( 1 - w _ { 3 } ) w _ { 3 } ^ { 3 } } + \frac { 1 5 w _ { 2 } ^ { 2 } w _ { 1 } ^ { 2 } } { 8 8 w _ { 3 } ^ { 3 } } - \frac { 9 w _ { 1 } ^ { 3 } } { 8 ( 1 - w _ { 3 } ) w _ { 3 } ^ { 3 } } , - \frac { w _ { 3 } ^ { 3 } } { 4 w _ { 3 } ^ { 3 } } - \frac { 3 ( 1 - v _ { 3 } ) u _ { 1 } ^ { 4 } } { 4 w _ { 3 } ^ { 3 } } - \frac { 1 } { 4 } , - \frac { 5 w _ { 4 } ^ { 4 } } { 4 ( 1 - w _ { 2 } ) w _ { 3 } ^ { 2 } } } \\ { } & { } &  \frac { 7 w _ { 3 } ^ { 3 } } { 2 ( 1 - w _ { 2 } ) w _ { 3 } ^ { 3 } } - \frac { 9 w _ { 2 } ^ { 3 } u _ { 1 } ^ { 2 } } { 2 ( 1 - w _ { 2 } ) w _ { 2 } ^ { 3 } } + \frac { 1 5 w _ { 3 } ^ { 4 } } { 4 ( 1 - w _ { 3 } ) w _ { 3 } ^ { 2 } } - \frac { 9 w _ { 3 } ^ { 2 } } { 4 ( 1 - w _ { 1 } ) w _ { 3 } ^ { 3 } } , - \frac { 5 w _ { 4 } ^ { 4 } } { 3 ( 1 - w _ { 2 } ) w _ { 3 } ^ { 2 } } \\ { } & { } &  + \frac { 7 w _ { 3 } ^ { 3 } } { 2 ( 1 - w _ { 4 } ) w _ { 3 } ^ { 3 } } - \frac { 3 w _ { 3 } ^ { 2 } w _ { 4 } ^ { 2 } } { 2 ( 1 - w _ { 4 } ) w _ { 3 } ^ { 2 } } + \frac { 1 5 w _ { 3 } ^ { 3 } } { 4 ( 1 - w _ { 4 } ) w _ { 3 } ^ { 2 } } - \ \end{array}
$$

$$
\vec { \ z } _ { i } ^ { 0 , 1 , 2 } = \left( 0 , \frac { u _ { i } } { w _ { i } } , 0 , 0 , 0 , \frac { u _ { i } ^ { 2 } } { 4 w _ { i } ^ { 2 } } - \frac { 1 } { 4 } , \frac { u _ { i } ^ { 2 } } { 4 w _ { i } ^ { 2 } } , \frac { u _ { i } ^ { 2 } } { 2 w _ { i } ^ { 2 } } - \frac { 1 } { 2 } , \frac { u _ { i } ^ { 2 } } { 2 w _ { i } ^ { 2 } } , \frac { u _ { i } ^ { 2 } } { 2 w _ { i } ^ { 2 } } , \frac { u _ { i } ^ { 2 } } { 2 ( 1 - u _ { i } ) w _ { i } } + \frac { 5 } { 8 } , \frac { u _ { i } } { 2 w _ { i } } - \frac { 3 } { 2 } , \right. \nonumber
$$

$$
\begin{array} { r l } { \widehat { ( \ell ) } _ { 2 , 0 , 1 1 } ^ { 0 , 2 , 1 } = \left( 0 , 0 , 0 , \frac { 1 } { 2 } \frac { 1 } { 0 } , 0 , \frac { 3 } { 8 } , 0 , 0 , 0 , - \frac { 3 } { 2 } \frac { 1 } { 9 } , \frac { 1 } { 8 } , \frac { 3 } { 9 } , - \frac { 1 3 } { 2 4 } \right) } & { } \\ { \widehat { ( \ell ) } _ { 2 , 0 , 1 1 } ^ { 0 , 3 , 0 , 1 } = \left( 0 , 0 , 0 , 0 , 0 , 0 , \frac { 1 } { 2 } , - \frac { 3 } { 8 } , - \frac { 1 } { 4 } , - \frac { 5 } { 8 } , \frac { 1 5 7 } { 1 2 } \right) } & { } \\ { \widehat { ( \ell ) } _ { 2 , 0 , 1 1 } ^ { 1 , 0 , 2 } = \left( 0 , \frac { 2 \widehat { \ell } _ { 1 } ^ { 1 } - \ell _ { 1 } ^ { 3 } \ell _ { 1 } } { \omega _ { 1 } ^ { 2 } } - \frac { \mu \widehat { \nu } _ { 1 } ^ { 2 } \gamma _ { 2 } } { 8 \omega _ { 1 } ^ { 2 } } , 0 , 0 , 0 , \frac { \mu \widehat { \nu } _ { 1 } ^ { 2 } } { 2 \omega _ { 1 } ^ { 3 } } + \frac { 2 \widehat { \ell } _ { 1 } ^ { 1 } - \mu \widehat { \nu } _ { 1 } \mu _ { 1 } ^ { 3 } } { \omega _ { 1 } ^ { 4 } } - \frac { 3 \widehat { \ell } _ { 1 } ^ { 3 } \mu _ { 1 } } { \omega _ { 1 } ^ { 3 } } - \frac { 3 \widehat { \ell } _ { 1 } ^ { 3 } \mu _ { 2 } \omega _ { 1 } } { 2 \omega _ { 1 } ^ { 3 } } \right. } & { } \\  \widehat { ( \ell ) } _ { 2 , 0 , 1 1 } ^ { 1 , 0 , 2 } = \left( 0 , \frac { 2 \widehat { \ell } _ { 1 } ^ { 1 } - \nu _ { 1 } ^ { 3 } \mu _ { 1 } ^ { 3 } } { \omega _ { 1 } ^ { 2 } } , \frac { ( 1 - u ) \mu _ { 1 } ( 1 - u ) } { 2 \omega _ { 1 } ^ { 3 } } , \frac { ( 1 - u ) \widehat { \ell } _ { 1 } ^ { 3 } } { \omega _ { 1 } ^ { 2 } } - \frac { ( 1 - u ) \widehat { \ell } _ { 1 } ^ { 3 } } { \omega _ { 1 } ^ { 2 } } - \frac { 3 \widehat { \ell } _ { 1 } ^ { 3 } } { \omega _ { 1 } ^ { 2 } } \right) ^ { 3 } - \frac { 3 \widehat { \ell } _ { 1 } ^ { 3 } ( 1 - u ) } { 2 \omega _ { 1 } ^ { 2 } } + \frac  3 \widehat { \ell } _  1  \end{array}
$$

$$
( \vec { c } _ { i } ) _ { 2 , 0 , 1 } ^ { 1 , 2 , 0 } = \left( 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 1 , - \frac { 1 } { 2 } , - \frac { 1 } { 2 } , - 1 , \frac { 4 7 } { 1 2 } \right)
$$

$$
\begin{array} { r l r } & { } & { \Delta \xi \widetilde { \phi } _ { \mu \lambda } ^ { \lambda \lambda } - \frac { \lambda } { 4 } ( \lambda _ { \mu } ^ { \nu \lambda } - \gamma _ { \nu } ^ { \lambda } ) - \frac { \lambda } { 4 } \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \lambda } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \lambda } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \lambda } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \lambda } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \lambda } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \lambda } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } } \\ & { } & { - \frac { 2 \eta _ { \nu } ^ { \lambda } } { 3 } + \frac { \gamma _ { \nu } } { 2 } - \frac { \lambda } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } } \\ & { } &  - \frac { 2 \eta _ { \nu } ^ { \lambda } } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 3 } + \frac { \gamma _ { \nu } ^ { \lambda } } { 3 } + \frac { \gamma _ { \nu } ^ { \lambda } } { 3 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 2 } - \frac { \gamma _ { \nu } ^ { \lambda } } { 3 } - \frac  \gamma _  \ \end{array}
$$

$$
\begin{array} { r l } { \sum _ { k = 1 } ^ { \infty } } & { \Bigg ( \sum _ { k = 1 } ^ { \infty } \Bigg ( \frac { 1 } { N } - \frac { 1 } { N } \Bigg ( \sum _ { k = 1 } ^ { \infty } - \frac { 1 } { N } \Bigg ) ^ { k } + \frac { 1 } { N } \Bigg ( \sum _ { k = 1 } ^ { \infty } - \frac { 1 } { N } \Bigg ) ^ { k } \Bigg ) ^ { k } } \\ { < \frac { 1 } { N } - \frac { 1 } { N } \Bigg ( \sum _ { k = 1 } ^ { \infty } \frac { 1 } { N } - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ) ^ { k } } \\ { < \frac { 1 } { N } - \frac { 1 } { N } \Bigg ( \sum _ { k = 1 } ^ { \infty } \frac { 1 } { N } - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } } \\ { \qquad - \frac { 1 } { N } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } } \\  - \frac { 1 } { N } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg ( - \frac { 1 } { N } \Bigg ) ^ { k } - \frac { 1 } { N } \Bigg  \end{array}
$$

$$
\begin{array} { r l } { \mathrm { E q } ^ { \mathrm { i } \mathrm { i } \mathrm { i } \mathrm { i } } } & { = \left\{ \begin{array} { l l l } { \mathrm { E q } _ { \mathrm { i } } ^ { \mathrm { i } \mathrm { i } \mathrm { i } } } & { \mathrm { E \cdot } \mathrm { e } ^ { - \mathrm { i } \mathrm { i } \mathrm { \ ' { s } } } } \\ { - \mathrm { i } } & { \mathrm { E q } _ { \mathrm { i } } ^ { \mathrm { i } \mathrm { i } \mathrm { i } } } \end{array} \right. \mathrm { t r u n } \mathrm { ~ } _ { \mathrm { F } } ^ { \mathrm { i } \mathrm { i } } \cdot \mathrm { e } ^ { - \mathrm { i } \mathrm { \ ' { s } } } , \quad \mathrm { t r } _ { \mathrm { i } } ^ { \mathrm { i } \mathrm { i } \mathrm { i } } } \\ & { \quad + \left( \begin{array} { l l l } { \mathrm { E q } _ { \mathrm { i } } ^ { \mathrm { i } \mathrm { i } \mathrm { i } } } & { \mathrm { E q } _ { \mathrm { i } } ^ { \mathrm { i } \mathrm { i } } } & { \mathrm { E q } _ { \mathrm { i } } ^ { \mathrm { i } \mathrm { i } } } \\ { - \mathrm { i } } & { \mathrm { E q } _ { \mathrm { i } } ^ { \mathrm { i } \mathrm { i } } } & { \mathrm { E q } _ { \mathrm { i } } ^ { \mathrm { i } \mathrm { i } } } \end{array} \right) \cdot \mathrm { t r u n } \left( \mathrm { E q } _ { \mathrm { i } } ^ { \mathrm { i } \mathrm { i } } \cdot \mathrm { e } ^ { - \mathrm { i } \mathrm { \ ' { s } } } \right) , } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad }  \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ &  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \ \end{array}
$$

$$
\begin{array} { r l } { ( \mathbf x ) ^ { \mu _ { 3 } } = } & { \frac { 1 } { \mu _ { 3 } \mu _ { 4 } } \sum _ { i = 1 } ^ { \infty } - \frac { 1 } { \mu _ { 3 } \mu _ { 4 } } \sum _ { j = 1 } ^ { \infty } \mu _ { 5 } ( \mathbf x - \mathbf x ) \sum _ { k = 1 } ^ { \infty } ( \mathbf x - \mathbf x ) \sum _ { k = 1 } ^ { \infty } \mu _ { 4 } \sum _ { \mathbf x = 1 } ^ { \infty } \mu _ { 5 } } \\ & { - \frac { 1 } { \mu _ { 3 } \mu _ { 2 } } \sum _ { i = 1 } ^ { \infty } \mu _ { 4 } \sum _ { \mathbf x = 1 } ^ { \infty } - \frac { 1 } { \mu _ { 3 } \mu _ { 4 } } - \frac { 1 } { \mu _ { 4 } \mu _ { 4 } } - \frac { 1 } { \mu _ { 5 } \mu _ { 4 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 6 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 6 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } } \\ & { - \frac { 1 } { \mu _ { 3 } \mu _ { 2 } } \sum _ { i = 1 } ^ { \infty } - \frac { 1 } { \mu _ { 2 } \mu _ { 3 } } - \frac { 1 } { \mu _ { 4 } \mu _ { 4 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } \sum _ { k = 1 } ^ { \infty } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } } \\ &  - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } \\ &  - \frac { 1 } { \mu _ { 6 } \mu _ { 7 } } \\ &  \frac { 1 } { \mu _ { 7 } } \sum _ { k = 1 } ^ { \infty } \mu _ { k } \frac { 1 } { \mu _ { 6 } } \sum _ { l = 1 } ^ { \infty } \mu _ { l } \frac { 1 } { \mu _ { 7 } } \sum _ { l = 1 } ^ { \infty } \mu _ { l } \frac { 1 } { \mu _ { 7 } } - \frac { 1 }  \end{array}
$$

# References

[1] W.van Neerven,“Infrared Behavior of On-shel Form-factors in a ${ \mathcal N } = 4$ Supersymmetric Yang-Mills Field Theory,” Z.Phys. C30 (1986) 595.   
[2] L. F. Alday and J. Maldacena,“Comments on gluon scattering amplitudes via AdS/CFT,” JHEP 0711 (2007) 068,arXiv:0710.1060 [hep-th].   
[3] J. Maldacena and A. Zhiboedov,“Form factors at strong coupling via a Y-system,” JHEP 1011 (2010) 104, arXiv:1009.1139 [hep-th].   
[4] A.Brandhuber,B. Spence,G. Travaglini,and G. Yang,“Form Factors in ${ \mathcal { N } } = 4$ Super Yang-Mills and Periodic Wilson Loops,” JHEP 1101 (2011) 134, arXiv:1011.1899 [hep-th].   
[5] L. Bork,D. Kazakov, and G. Vartanov, “On form factors in ${ \mathcal N } = 4$ SYM," JHEP1102 (2011) 063,arXiv:1011.2440 [hep-th].   
[6] A. Brandhuber,O. Gurdogan, R. Mooney, G. Travaglini,and G. Yang,“Harmony of Super Form Factors,” JHEP 1110 (2011) 046,arXiv:1107.5067 [hep-th].   
[7] L. Bork, D. Kazakov, and G. Vartanov,“On MHV Form Factors in Superspace for ${ \mathcal N } = 4$ （20 SYM Theory,” JHEP1110 (2011) 133,arXiv:1107.5551 [hep-th].   
[8] J. M. Henn, S. Moch, and S.G. Naculich,“Form factors and scattering amplitudes in ${ \mathcal N } = 4$ SYM in dimensional and massive regularizations,” JHEP 12 (2011) 024, arXiv:1109.5057 [hep-th].   
[9] T.Gehrmann, J.M. Henn,and T. Huber,“The three-loop form factor in ${ \mathcal N } = 4$ super Yang-Mills,” JHEP 1203 (2012) 101, arXiv:1112.4524 [hep-th].   
[10] A.Brandhuber,G. Travaglini, and G. Yang,“Analytic two-loop form factors in ${ \mathcal N } = 4$ SYM,” JHEP 1205 (2012) 082, arXiv:1201.4170 [hep-th].   
[11] L.Bork,“On NMHV form factors in ${ \mathcal N } = 4$ SYM theory from generalized unitarity,” JHEP 1301 (2013) 049,arXiv:1203.2596 [hep-th].   
[12] O. T. Engelund and R. Roiban,“Correlation functions of local composite operators from generalized unitarity,” JHEP 1303 (2013) 172, arXiv:1209.0227 [hep-th].   
[13] H. Johansson, D. A. Kosower,and K. J. Larsen,“Two-Loop Maximal Unitarity with External Masses,” Phys.Rev. D87 (2013) 025030, arXiv:1208.1754 [hep-th].   
[14] R. H. Boels, B.A. Kniehl, O. V. Tarasov,and G. Yang,“Color-kinematic Duality for Form Factors,” JHEP 1302 (2013) 063,arXiv:1211.7028 [hep-th].   
[15] Z. Gao and G. Yang,“Y-system for form factors at strong coupling in $A d S _ { 5 }$ and with multi-operator insertions in $A d S _ { 3 }$ ,” JHEP1306 (2013)105,arXiv:1303.2668 [hep-th].   
[16] B. Penante, B. Spence, G. Travaglini, and C. Wen,“On super form factors of half-BPS operators in ${ \mathcal N } = 4$ super Yang-Mills,” JHEP 1404 (2014) 083, arXiv:1402.1300 [hep-th].   
[17] A. Brandhuber,B.Penante, G. Travaglini,and C. Wen,“The last of the simple remainders," JHEP 1408 (2014) 100, arXiv:1406.1443 [hep-th].   
[18] L.Bork,“On form factors in ${ \mathcal N } = 4$ SYM theory and polytopes,” JHEP 1412 (2014) 111, arXiv:1407.5568 [hep-th].   
[19] M. Wilhelm,“Amplitudes,Form Factors and the Dilatation Operator in ${ \mathcal N } = 4$ SYM Theory,” JHEP 1502 (2015) 149,arXiv:1410.6309 [hep-th].   
[20] D.Nandan, C. Sieg, M. Wilhelm,and G. Yang,“Cutting through form factors and cross sections of non-protected operators in ${ \mathcal N } = 4$ SYM,” JHEP 06 (2015) 156, arXiv:1410.8485 [hep-th].   
[21] F.Loebbert, D. Nandan, C. Sieg,M. Wilhelm,and G. Yang,“On-Shell Methods for the Two-Loop Dilatation Operator and Finite Remainders,” JHEP 10 (2015) 012, arXiv:1504.06323 [hep-th].   
[22] R. Frassek, D. Meidinger, D. Nandan, and M. Wilhelm,“On-shell diagrams, GraBmannians and integrability for form factors,” JHEP01 (2016) 182, arXiv:1506.08192 [hep-th].   
[23] R. Boels, B.A. Kniehl,and G. Yang,“Master integrals for the four-loop Sudakov form factor,” Nucl. Phys. B902 (2016) 387-414, arXiv:1508.03717 [hep-th].   
[24] R. Huang, Q. Jin, and B.Feng,“Form Factor and Boundary Contribution of Amplitude,” JHEP06 (2016) 072,arXiv:1601.06612 [hep-th].   
[25] L. Koster,V. Mitev,M. Staudacher,and M. Wilhelm,“Composite Operators in the Twistor Formulation of ${ \mathcal N } = 4$ Supersymmetric Yang-Mills Theory,"” Phys. Rev. Lett. 117 no. 1, (2016) 011601, arXiv:1603.04471 [hep-th].   
[26] L.Koster, V.Mitev, M. Staudacher,and M. Wilhelm,“All Tree-Level MHV Form Factors i1 （204号 $\mathcal { N } = 4$ SYM from Twistor Space,” JHEP06 (2016) 162, arXiv:1604.00012 [hep-th].   
[27] D. Chicherin and E. Sokatchev,“Composite operators and form factors in ${ \mathcal N } = 4$ SYM," arXiv:1605.01386 [hep-th].   
[28] A. Brandhuber, M. Kostacinska, B. Penante,G. Travaglini, and D. Young,“The SU(2|3) dynamic two-loop form factors,” JHEP 08 (2016) 134, arXiv:1606.08682 [hep-th].   
[29] L.V. Bork and A.I. Onishchenko,“Grassmannians and form factors with $q ^ { 2 } = 0$ in ${ \mathcal N } = 4$ （204号 sym theory,” arXiv:1607.00503 [hep-th].   
[30] L. V. Bork and A. I. Onishchenko,“Wilson lines, Grassmannians and Gauge Invariant Off-shell Amplitudes in ${ \mathcal N } = 4$ SYM,” arXiv:1607.02320 [hep-th].   
[31] S. He and Y. Zhang,“Connected formulas for amplitudes in standard model," arXiv:1607.02843 [hep-th].   
[32] S. Caron-Huot and M. Wilhelm,“Renormalization group coefficients and the S-matrix.” arXiv:1607.06448 [hep-th].   
[33] A.Brandhuber,E. Hughes,R.Panerai, B. Spence,and G.Travaglini,“The connected prescription for form factors in twistor space,” arXiv:1608.03277 [hep-th].   
[34] S.He and Z. Liu,“A note on connected formula for form factors,” arXiv:1608.04306 [hep-th].   
[35] G. Yang,“Color-Kinematics Duality and Sudakov Form Factor at Five Loops,” arXiv:1610.02394 [hep-th].   
[36] T.Ahmed, P. Banerjee,P.K. Dhani, N. Rana, V. Ravindran, and S. Seth,“Konishi Form Factor at Three Loop in ${ \mathcal N } = 4$ SYM," arXiv:1610.05317 [hep-th].   
[37] M. Wilhelm, Form factors and the dilatation operator in ${ \mathcal { N } } = 4$ super Yang-Mills theory anc its deformations. PhD thesis, Humboldt U., Berlin, 2016. arXiv:1603.01145 [hep-th].   
[38] B.Penante, On-shell methods for off-shell quantities in ${ \mathcal N } = 4$ Super Yang-Mills: from scattering amplitudes to form factors and the dilatation operator. PhD thesis, Queen Mary, U. of London, 2016. arXiv:1608.01634 [hep-th].   
[39] H. Elvang and Y.-t. Huang,“Scattering Amplitudes,” arXiv:1308.1697 [hep-th].   
[40] L. J. Dixon，“A brief introduction to modern amplitude methods,” in Proceedings, 2012 European School of High-Energy Physics (ESHEP 2012): La Pommeraye, Anjou, France, June 06-19, 2012, pp.31-67. 2014. arXiv:1310.5353 [hep-ph].   
[41] J.M. Henn and J. C. Plefka,“Scattering Amplitudes in Gauge Theories,” Lect.Notes Phys. 883 (2014) 1-195.   
[42] A.H. Mueller,“On the Asymptotic Behavior of the Sudakov Form-factor," Phys.Rev. D20 (1979) 2037.   
[43] J. C. Collins,“Algorithm to Compute Corrections to the Sudakov Form-factor,” Phys.Rev. D22 (1980) 1478.   
[44] A. Sen,“Asymptotic Behavior of the Sudakov Form-Factor in QCD,” Phys.Rev. D24 (1981) 3281.   
[45] L. Magnea and G. F. Sterman,“Analytic continuation of the Sudakov form-factor in QCD,” Phys.Rev. D42 (1990) 4222-4227.   
[46] H. M. Georgi, S.L. Glashow, M. E. Machacek,and D. V. Nanopoulos,“Higgs Bosons from Two Gluon Annihilation in Proton Proton Collisions,” Phys. Rev. Lett. 40 (1978) 692.   
[47] S.D. Drel and T.-M. Yan,“Massive Lepton Pair Production in Hadron-Hadron Colisions at High-Energies,” Phys. Rev. Lett. 25 (1970) 316-320. [Erratum: Phys. Rev. Lett.25,902(1970)].   
[48] N. Beisert et al., “Review of AdS/CFT Integrability: An Overview,” Lett.Math.Phys.99 (2012) 3-32, arXiv:1012.3982 [hep-th].   
[49] Z. Bern, L. J. Dixon, D. C. Dunbar,and D.A. Kosower,“One-loop $n$ -point gauge theory amplitudes,unitarity and colinear limits,” Nucl.Phys. B425 (1994) 217-260, arXiv:hep-ph/9403226 [hep-ph].   
[50] Z. Bern, L. J. Dixon, D.C. Dunbar, and D. A. Kosower,“Fusing gauge theory tree amplitudes into loop amplitudes,” Nucl.Phys. B435 (1995) 59-101, arXiv:hep-ph/9409265 [hep-ph].   
[51] R.Britto,F.Cachazo,and B. Feng,“Generalized unitarity and one-loop amplitudes in ${ \mathcal N } = 4$ （20 super-Yang-Mills,” Nucl.Phys. B725 (2005) 275-305, arXiv:hep-th/0412103 [hep-th].   
[52] B.Eden and M. Staudacher，“Integrability and transcendentality,” J. Stat. Mech. 0611 (2006) P11014, arXiv:hep-th/0603157 [hep-th].   
[53] A. V. Belitsky, G.P. Korchemsky, and D. Mueller,“Towards Baxter equation in supersymmetric Yang-Mills theories,” Nucl. Phys. B768 (2007) 116-134, arXiv:hep-th/0605291 [hep-th].   
[54] B.I. Zwiebel,“Iterative Structure of the ${ \mathcal N } = 4$ SYM Spin Chain,” JHEP 07 (2008) 114, arXiv:0806.1786 [hep-th].   
[55] A. V. Kotikov and L. N. Lipatov,“DGLAP and BFKL equations in the ${ \mathcal N } = 4$ （204号 supersymmetric gauge theory,” Nucl. Phys. B661 (2003) 19-61, arXiv:hep-ph/0208220 [hep-ph]. [Erratum: Nucl. Phys.B685,405(2004)].   
[56] J. Fleischer,A. V. Kotikov,and O.L. Veretin,“The Differential equation method: Calculation of vertex type diagrams with one nonzero mass,” Phys. Lett. B417 (1998) 163-172, arXiv:hep-ph/9707492 [hep-ph].   
[57] J. Fleischer, A. V. Kotikov,and O.L. Veretin,“Analytic two loop results for selfenergy type and vertex type diagrams with one nonzero mass,” Nucl. Phys. B547 (1999) 343-374, arXiv:hep-ph/9808242 [hep-ph].   
[58] L. Bianchi, V. Forini, and A.V. Kotikov,“On DIS Wilson coefficients in ${ \mathcal N } = 4$ super Yang-Mills theory,” Phys. Lett.B725 (2013) 394-401, arXiv:1304.7252 [hep-th].   
[59] G. P. Korchemsky,“Asymptotics of the Altarell-Parisi-Lipatov Evolution Kernels of Parton Distributions,” Mod. Phys. Lett. A4 (1989) 1257-1276.   
[60] G.P.Korchemsky and G. Marchesini,“Structure function for large x and renormalization of Wilson loop,” Nucl. Phys. B406 (1993) 225-258, arXiv:hep-ph/9210281 [hep-ph].   
[61] N. Beisert, B. Eden,and M. Staudacher,“Transcendentality and Crossing,” J.Stat.Mech. 0701 (2007) P01021, arXiv:hep-th/0610251 [hep-th].   
[62] J. Drummond,J. Henn, G. Korchemsky,and E. Sokatchev,“Hexagon Wilson loop $\ c =$ six-gluon MHV amplitude,” Nucl.Phys. B815 (2009) 142-173, arXiv:0803.1466 [hep-th].   
[63] Z. Bern, L. J. Dixon, D. A. Kosower,R. Roiban, M. Spradlin, C. Vergu,and A. Volovich, “The Two-Loop Six-Gluon MHV Amplitude in Maximally Supersymmetric Yang-Mills Theory,” Phys. Rev. D78 (2008) 045007, arXiv:0803.1465 [hep-th].   
[64] V. Del Duca, C. Duhr,and V. A. Smirnov,“The Two-Loop Hexagon Wilson Loop in ${ \mathcal { N } } = 4$ （204号 SYM,” JHEP 05 (2010) 084, arXiv:1003.1702 [hep-th].   
[65] N. Arkani-Hamed, J. L. Bourjaily, F. Cachazo,A. B. Goncharov, A. Postnikov, and J. Trnka, Scattering Amplitudes and the Positive Grassmannian. Cambridge University Press, 2012. arXiv:1212.5605 [hep-th].   
[66] A. Kotikov,L. Lipatov,A. Onishchenko,and V. Velizhanin,“Three loop universal anomalous dimension of the Wilson operators in ${ \mathcal N } = 4$ SUSY Yang-Mills model," Phys.Lett B595 (2004) 521-529, arXiv:hep-th/0404092 [hep-th].   
[67] N. Beisert,“The complete one-loop dilatation operator of ${ \mathcal N } = 4$ superYang-Mills theory,"” Nucl.Phys. B676 (2004) 3-42, arXiv:hep-th/0307015 [hep-th].   
[68] N. Beisert,“On Yangian Symmetry in Planar ${ \mathcal N } = 4$ SYM,” arXiv:1004.5423 [hep-th].   
[69] B.I. Zwiebel,“From Scattering Amplitudes to the Dilatation Generator in $\mathcal { N } = 4$ SYM," J.Phys. A45 (2012) 115401, arXiv:1111.0083 [hep-th].   
[70] G. Passarino and M. Veltman,“One-Loop Corrections for $e ^ { + } e ^ { - }$ Annihilation Into $\mu ^ { + } \mu ^ { - }$ in the Weinberg Model,” Nucl.Phys. B160 (1979) 151.   
[71] K. Chetyrkin and F. Tkachov,“Integration by Parts: The Algorithm to Calculate beta Functions in 4 Loops,” Nucl.Phys. B192 (1981) 159-204.   
[72] F. Tkachov,“A Theorem on Analytical Calculability of Four Loop Renormalization Group Functions,” Phys.Lett. B100 (1981) 65-68.   
[73] R. N. Lee,“LiteRed 1.4: a powerful tool for reduction of multiloop integrals,” J.Phys.Conf.Ser. 523 (2014) 012059, arXiv:1310.1145 [hep-ph].   
[74] T. Gehrmann and E. Remiddi,“Two loop master integrals for $\gamma ^ { * } \longrightarrow 3$ jets: The Planar topologies,” Nucl.Phys. B601 (2001) 248-286, arXiv:hep-ph/0008287 [hep-ph].   
[75] C. Anastasiou, Z. Bern, L. J. Dixon, and D. Kosower,“Planar amplitudes in maximally supersymmetric Yang-Mills theory,” Phys.Reu.Lett. 91 (2003) 251602, arXiv:hep-th/0309040 [hep-th].   
[76] Z.Bern,L. J. Dixon,and V.A. Smirnov,“Iteration of planar amplitudes in maximally supersymmetric Yang-Mills theory at three loops and beyond," Phys.Rev.D72 (2005) 085001, arXiv:hep-th/0505205 [hep-th].   
[77] V. M. Braun, G. P. Korchemsky, and A.N. Manashov,“Evolution equation for the structure function $g _ { 2 } ( x , Q ^ { 2 } )$ ," Nucl. Phys. B603 (2001) 69-124, arXiv:hep-ph/0102313 [hep-ph].   
[78] E. Pomoni and C. Sieg,“From ${ \mathcal N } = 4$ gauge theory to ${ \mathcal N } = 2$ conformal QCD: three-loop mixing of scalar composite operators,” arXiv:1105.3487 [hep-th].   
[79] S.Moch, J.A. M. Vermaseren,and A. Vogt,“The Three loop spliting functions in QCD: The Nonsinglet case,” Nucl. Phys. B688 (2004) 101-134, arXiv:hep-ph/0403192 [hep-ph].   
[80] B.Eden, C. Jarczak,and E. Sokatchev,“A Three-loop test of the dilatation operator in （ ${ \mathcal N } = 4$ SYM,” Nucl. Phys.B712 (2005) 157-195, arXiv:hep-th/0409009 [hep-th].   
[81] C. Sieg,“Superspace computation of the three-loop dilatation operator of ${ \mathcal { N } } = 4$ SYM theory,” Phys.Rev. D84 (2011) 045014, arXiv:1008.3351 [hep-th].   
[82] T. Gehrmann, M. Jaquier,E. Glover,and A. Koukoutsakis,“Two-Loop QCD Corrections to the Helicity Amplitudes for $H  3$ partons,” JHEP 1202 (2012) 056, arXiv:1112.3554 [hep-ph].   
[83] Y.Li and H. X. Zhu,“Bootstrapping Rapidity Anomalous Dimension for Transverse-Momentum Resummation,” arXiv:1604.01404 [hep-ph].   
[84] V.M. Braun, A. N. Manashov, S. Moch,and M. Strohmaier,“Two-loop conformal generators for leading-twist operators in QCD,” JHEP 03 (2016) 142, arXiv:1601.05937 [hep-ph].   
[85] A. V. Kotikov,“The Gegenbauer polynomial technique: The Evaluation of a class of Feynman diagrams,” Phys. Lett B375 (1996) 240-248, arXiv:hep-ph/9512270 [hep-ph].   
[86] K. Chetyrkin,A. Kataev,and F. Tkachov,“New Approach to Evaluation of Multiloop Feynman Integrals: The Gegenbauer Polynomial x Space Technique," Nucl.Phys. B174 (1980) 345-377.