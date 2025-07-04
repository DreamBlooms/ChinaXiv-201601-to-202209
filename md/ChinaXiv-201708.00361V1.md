# On-Shell Methods for the Two-Loop Dilatation Operator and Finite Remainders

Florian Loebbert $\mathbf { a }$ , Dhritiman Nandan $^ { \mathbf { a } , \mathbf { b } } _ { . }$ ， Christoph Sieg $\mathbf { \alpha } _ { \cdot } \mathbf { a } , \mathbf { b }$ Matthias Wilhelm $\mathbf { a } , \mathbf { b }$ , Gang Yanga

$a$ Institut fir Physik （204号 $b$ Institut fir Mathematik Humboldt-Universitit zu Berlin IRIS Gebäude, Zum Groβen Windkanal 6, 12489 Berlin {loebbert，dhritiman，csieg，mwilhelm，gang.yang}@physik.hu-berlin.de

# Abstract

We compute the two-loop minimal form factors of all operators in the SU(2) sector of planar ${ \mathcal N } = 4$ SYM theory via on-shell unitarity methods. From the UV divergence of this result,we obtain the two-loop dilatation operator in this sector. Furthermore,we calculate the corresponding finite remainder functions. Since the operators break the supersymmetry, the remainder functions do not have the property of uniform transcendentality. However, the leading transcendentality part turns out to be universal and is identical to the corresponding BPS expression. The remainder functions are shown to satisfy linear relations which can be explained by Ward identities of form factors following from R-symmetry.

# Contents

1 Introduction 2

2Minimal form factors in the SU(2) sector 5

2.1 Tree-level form factors 5   
2.2 One-loop form factors 6   
2.3 Two-loop form factors 10

# Two-loop dilatation operator and remainder function 14

3.1Renormalisation constant and dilatation operator 15   
3.2Finite remainders 16

4Conclusion and outlook 18

A Six-point scalar amplitudes 20

# 1 Introduction

In the last years, form factors in $\mathcal { N } = 4$ super Yang-Mills (SYM) theory have received increasing attention, both at weak coupling [1-17] and at strong coupling [18-20]. Containing both on-shell states and local composite operators, form factors provide a useful bridge between the purely on-shell amplitudes and the of-shell world of correlation functions. In particular, powerful computational methods developed in the context of scattering amplitudes can be applied to form factors and to other important physical quantities via form factors, such as the spectrum of anomalous dimensions of composite operators and their correlation functions. The form factor $\hat { \mathcal { F } } _ { \mathcal { O } }$ is defined as the matrix element of a given local operator ${ \mathcal { O } } ( x )$ between the vacuum $| 0 \rangle$ and an on-shell $n$ -particle state $\langle 1 , \ldots , n |$ ,i.e.

$$
\hat { \mathcal { F } } _ { \mathcal { O } } ( 1 , \dots , n ; q ) = \int \mathrm { d } ^ { 4 } x \mathrm { e } ^ { - i q x } \langle 1 , \dots , n | { \mathcal { O } } ( x ) | 0 \rangle .
$$

A special class of form factors are the so-called minimal form factors, which contain as many external fields $n$ as there are fields in the operator,and which will be of particular interest for this paper.

Understanding the connection between form factors and the spectral problem of ${ \mathcal { N } } = 4$ SYM theory was recently pushed forward in [16,17]. In [16], form factors for generic operators were investigated. In particular, it was shown that the complete one-loop dilatation operator [21] can be derived using one-loop minimal form factors,which explains the relation between the one-loop dilatation operator and the four-point scattering amplitude derived from symmetry in [22].1 In [17], it was demonstrated that form factors can also be used to calculate anomalous dimensions at two-loop order by investigating the Konishi primary operator. In these studies,on-shell amplitude techniques have played a major role,in particular the (generalised） unitarity method [23-25]. In order to treat general operators, however,an extension of this method is required [17].

Interesting on-shell approaches towards the computation of correlation functions and the dilatation operator were also applied in the following works: see [10, 26] for the application of generalised unitarity, [27] for a spacetime version thereof, [28, 29] for twistor techniques and [3O] for the application of MHV diagrams.

Computing form factors and correlators of non-protected local gauge-invariant operators requires renormalisation，which in general implies the mixing of these operators. This procedure singles out certain subsectors, which are closed under renormalisation and which transform under subalgebras of the full PSU $( 2 , 2 | 4 )$ symmetry [21]. The simplest testing ground for studying the full renormalisation problem of $\mathcal { N } = 4$ SYM theory is given by the so-called ${ \mathrm { S U } } ( 2 )$ sector. The operators in this sector are built out of two complex scalar fields $X$ and $Y$ transforming in the fundamental representation of ${ \mathrm { S U } } ( 2 )$ e.g. $X ~ = ~ \phi _ { 1 4 }$ and $Y ~ = ~ \phi _ { 2 4 }$ . In particular, the single-trace operators are of the form （20 $\mathcal { O } _ { \mathrm { b a r e } } = \mathrm { t r } ( X ^ { k _ { 1 } } Y ^ { k _ { 2 } } X ^ { k _ { 3 } } Y ^ { k _ { 4 } } \cdot \cdot \cdot )$ ，where $k _ { j } \in \{ 0 , 1 , 2 , \ldots \}$ . The renormalised operators of the interacting theory are obtained from these bare operators via the mixing matrix $\mathcal { Z }$ as

$$
\mathcal { O } _ { \mathrm { r e n } } = \mathcal { Z O } _ { \mathrm { b a r e } } , \qquad \mathcal { Z } = \Im + g ^ { 2 } \mathcal { Z } ^ { ( 1 ) } + g ^ { 4 } \mathcal { Z } ^ { ( 2 ) } + \mathcal { O } \bigl ( g ^ { 6 } \bigr ) .
$$

The study of this mixing problem has been of great importance for capturing the novel integrable structures appearing in planar $\mathcal { N } = 4$ SYM theory at higher loop orders [31]. At one-loop order, the crucial observation introducing integrability to planar $\mathcal { N } = 4$ SYM theory was that the anomalous dilatation operator defined as

$$
\delta \mathfrak { D } = - \mu \frac { \mathrm { d } } { \mathrm { d } \mu } \log \mathcal { Z } = 2 \varepsilon g ^ { 2 } \frac { \partial } { \partial g ^ { 2 } } \log \mathcal { Z } = \sum _ { \ell = 1 } ^ { \infty } g ^ { 2 \ell } \mathfrak { D } ^ { ( \ell ) }
$$

takes the form of the integrable Heisenberg spin-chain Hamiltonian within the SU(2) sector [32].2 The central role of the dilatation operator and its interpretation as an (asymptotic) spin-chain Hamiltonian was further emphasized in [33], where the two-loop dilatation operator with ${ \mathrm { S U } } ( 2 )$ symmetry was computed from Feynman diagrams and its three-loop correction was derived under the assumption of integrability. A field-theoretic computation of the latter was later performed in [34]. Making use of integrability, a recursive construction for the asymptotic dilatation operator in the SU(2) sector is available by now, which allows to compute its operatorial form to high orders in the 't Hooft coupling constant [35, 36].

In this paper, we continue the program of [16, 17] and study form factors and the dilatation operator at two-loop order in the full SU(2) sector. We employ the unitarity method to obtain the complete two-loop form factors in this sector of planar ${ \mathcal N } = 4$ SYM theory. Interestingly, the form factor results satisfy linear relations. It turns out that they can be explained by Ward identities of form factors following from R-symmetry.

Form factors of non-protected operators contain both infrared (IR) divergences, due to soft and collinear virtual momenta, and ultraviolet (UV) divergences. The information of the latter allowsus to determine the renormalisation matrix $\mathcal { Z }$ ,andtherefore,thedilatation operator.' In dimensional regularisation,where the four-dimensional theory is continued to $D = 4 - 2 \varepsilon$ dimensions,4 all divergences are given by $1 / \varepsilon ^ { k }$ terms.In order to obtain the dilatation operator, we need to disentangle the IR and UV divergences,which is possible since the IR divergences have a well-understood universal structure [37-40]. Concretely, we will subtract the IR divergences via the BDS ansatz [41, 42];5 a similar procedure has already been used in [16,17].

For amplitudes,it is well-known that the BDS ansatz does in general not give the full result but allows for a finite remainder function [18],which was first studied for the six-gluon case in [45-47]. For form factors of BPS operators, remainder functions have also been studied in [8,14]. In particular, interesting properties associated to the so-called transcendentality were observed, such as the maximal transcendentality principle,which we will review below. In this paper, we will study the remainder functions of form factors of non-protected operators,where new features appear.

Quantities in $\mathcal { N } ~ = ~ 4$ SYM theory have shown interesting properties with respect to their transcendentality. Scattering amplitudes and form factors of BPS operators as well as their remainders have uniform transcendentality:6at $\ell$ -loop order，they can be expressed as linear combinations of functions and numbers with transcendentality degree 2l. Furthermore, remarkable relations have been found between the results of ${ \mathcal N } = 4$ SYM theory and QCD.It was first argued in [51] that, for anomalous dimensions of twist-two operators, the $\mathcal { N } = 4$ SYM theory result is given by the leading transcendental part of the QCD result. This is usually referred to as the maximal transcendentality principle; see also [7, 52-54] for further discussions. While this heuristic relation was observed only for anomalous dimensions,in [8] it was found that the remainder function of certain BPS two-loop form factors matches exactly the leading transcendental part of related two-loop Higgs-to-gluons amplitudes in QCD [55]. This provides a frst example where the maximal transcendentality principle is extended from pure numbers to functions which may have non-trivial kinematic dependence.7

In this paper, we demonstrate that form factors of non-protected operators show new universality properties regarding their transcendentality. Since the considered operators break supersymmetry, the remainder functions are expected not to have the property of uniform transcendentality. However， we find that all contributions of maximal transcendentality are identical to the corresponding results of BPS form factors. This provides further evidence for the universality of the leading transcendental part,which furthermore has a non-trivial kinematic dependence.

This paper is organised as follows. In section 2, we present results for tree-level and one-loop form factors in the SU(2) sector. This also serves to introduce our conventions and notation. Moreover, we calculate the minimal two-loop form factors of such operators. In section 3, we extract the two-loop dilatation operator and two-loop remainder function from these results. Section 4 contains our conclusions and outlook. We provide simplified expressions for six-point amplitudes appearing in the unitarity calculation in appendix A.

# 2 Minimal form factors in the SU(2) sector

# 2.1 Tree-level form factors

In this subsection, we summarise some general facts about form factors and give explicit tree-level expressions that are required in the unitarity calculations of the subsequent subsections.

In analogy to amplitudes， we can strip off the gauge-group dependence of the form factors by introducing colour-ordered form factors $\mathcal { F } _ { \mathcal { O } }$

$$
\hat { \mathcal { F } } _ { \mathcal { O } } ( 1 , \dots , n ; q ) = \sum _ { \sigma \in \mathbb { S } _ { n } / \mathbb { Z } _ { n } } \mathrm { t r } [ \Gamma ^ { a _ { \sigma ( 1 ) } } \cdot \cdot \cdot \cdot \Upsilon ^ { a _ { \sigma ( n ) } } ] \mathcal { F } _ { \mathcal { O } } ( \sigma ( 1 ) , \dots , \sigma ( n ) ; q ) + \mathrm { m u l t i - t r a c e ~ t e r m s } ,
$$

where $\mathrm { T } ^ { a }$ with $a = 1 , \dots , N _ { c } ^ { 2 } - 1$ are the generators of the gauge group $\mathrm { S U } ( N _ { c } )$ and the sum is over all non-cyclic permutations. The multi-trace terms in (2.1) can start to appear at one-loop order but are suppressed in the planar limit,and will not be considered in this paper.

We describe the external on-shell states using Nair's ${ \mathcal { N } } = 4$ on-shell superfield [57]:

$\Phi ( p , \eta ) = g _ { + } ( p ) + \eta ^ { A } \bar { \psi } _ { A } ( p ) + \frac { \eta ^ { A } \eta ^ { B } } { 2 ! } \phi _ { A B } ( p ) + \frac { \epsilon _ { A B C D } \eta ^ { A } \eta ^ { B } \eta ^ { C } } { 3 ! } \psi ^ { D } ( p ) + \eta ^ { 1 } \eta ^ { 2 } \eta ^ { 3 } \eta ^ { 4 } g _ { - } ( p ) ,$ (2.2) where $\eta _ { A }$ are GraBmann variables that encode the flavour and helicity of the component particles,and $A = 1 , \dotsc , 4$ is the ${ \mathrm { S U } } ( 4 )$ R-symmetry index. In this formalism,we can combine form factors with different external fields into one super form factor. As we wil see later， this also makes it easier to study the supersymmetry properties of the form factors.

In this paper, we focus on form factors in the SU(2) sector. The corresponding singletrace operators involve two complex scalar fields with a common SU(4) index, which are chosen explicitly as $X = \phi _ { 1 4 }$ and $Y = \phi _ { 2 4 }$ . The tree-level minimal super form factor for the operator $\mathcal { O } = \mathrm { t r } ( X X Y X \cdot \cdot \cdot )$ with $L = n$ fields, for instance,is simply given by

$$
\mathcal { F } _ { \mathcal { O } } ^ { ( 0 ) } ( 1 , \dots , L ; q ) = \delta ^ { 4 } ( q - \sum _ { i = 1 } ^ { L } \lambda _ { i } \tilde { \lambda } _ { i } ) \left( \eta _ { 1 } ^ { 1 } \eta _ { 1 } ^ { 4 } \eta _ { 2 } ^ { 1 } \eta _ { 2 } ^ { 4 } \eta _ { 3 } ^ { 2 } \eta _ { 3 } ^ { 4 } \eta _ { 4 } ^ { 1 } \eta _ { 4 } ^ { 4 } \cdot \cdot \cdot + \mathrm { c y c l i c ~ p e r m u t a t i o n s } \right) .
$$

In general, the colour-ordered minimal tree-level super form factors of any operator can be obtained from the operator's oscillator representation by replacing the oscillators by spinor helicity variables and multiplying the result by the momentum-conserving delta function [16].

We also need the next-to-minimal tree-level form factors in the two-loop unitarity computation below,which contain one more external field than the minimal ones. They may be computed easily by Feynman diagrams, or obtained from the BPS form factor component expressions, see e.g. [13]. For convenience, we provide some explicit rules that are useful in practice. There are four different cases that can occur. In the first case, a $g _ { + }$ （20 can be inserted between two neighbouring positions $i$ and $i + 1$ . This leads to the following replacement in the colour-ordered minimal tree-level form factor:

$$
\cdots \cdot \cdot \eta _ { i } ^ { A } \eta _ { i } ^ { B } \eta _ { i + 1 } ^ { C } \eta _ { i + 1 } ^ { D } \cdots \longrightarrow \cdots \cdot \cdot \eta _ { i } ^ { A } \eta _ { i } ^ { B } \frac { \langle i i + 2 \rangle } { \langle i i + 1 \rangle \langle i + 1 i + 2 \rangle } \eta _ { i + 2 } ^ { C } \eta _ { i + 2 } ^ { D } \cdots .
$$

In the second case,a $g _ { - }$ can be inserted at the same position, leading to

$$
\cdots \cdot \eta _ { i } ^ { A } \eta _ { i } ^ { B } \eta _ { i + 1 } ^ { C } \eta _ { i + 1 } ^ { D } \cdots \longrightarrow \cdots \cdot \eta _ { i } ^ { A } \eta _ { i } ^ { B } \frac { [ i i + 2 ] } { [ i i + 1 ] [ i + 1 i + 2 ] } \eta _ { i + 1 } ^ { 1 } \eta _ { i + 1 } ^ { 2 } \eta _ { i + 1 } ^ { 3 } \eta _ { i + 1 } ^ { 4 } \eta _ { i + 2 } ^ { C } \eta _ { i + 2 } ^ { D } \cdots .
$$

In the third case, a $\phi _ { C D }$ at position $i$ is split into two anti-fermions $\psi _ { C }$ and $\psi _ { D }$ . This leads to

$$
\cdots \eta _ { i - 1 } ^ { A } \eta _ { i - 1 } ^ { B } \eta _ { i } ^ { C } \eta _ { i } ^ { D } \eta _ { i + 1 } ^ { E } \eta _ { i + 1 } ^ { F } \cdots \longrightarrow \cdots \eta _ { i - 1 } ^ { A } \eta _ { i - 1 } ^ { B } \frac { 1 } { \langle i \dot { i } + 1 \rangle } ( \eta _ { i } ^ { C } \eta _ { i + 1 } ^ { D } - \eta _ { i } ^ { D } \eta _ { i + 1 } ^ { C } ) \eta _ { i + 2 } ^ { E } \eta _ { i + 2 } ^ { F } \cdots \ .
$$

In the fourth case, the $\phi _ { C D }$ is split into two fermions $\psi ^ { C ^ { \prime } }$ and $\psi ^ { D ^ { \prime } }$ with $\epsilon _ { C D C ^ { \prime } D ^ { \prime } } = 1$ ， leading to

$$
\cdot \cdot \eta _ { i - 1 } ^ { A } \eta _ { i - 1 } ^ { B } \eta _ { i } ^ { C } \eta _ { i } ^ { D } \eta _ { i + 1 } ^ { E } \eta _ { i + 1 } ^ { F } \cdots \longrightarrow \cdots \eta _ { i - 1 } ^ { A } \eta _ { i - 1 } ^ { B } \frac { - 1 } { [ i \ - i + 1 ] } ( \bar { \eta } _ { i , C ^ { \prime } } \bar { \eta } _ { i + 1 , D ^ { \prime } } - \bar { \eta } _ { i , D ^ { \prime } } \bar { \eta } _ { i + 1 , C ^ { \prime } } ) \eta _ { i + 2 } ^ { E } \eta _ { i + 2 } ^ { F } \cdots \ ,
$$

where $\begin{array} { r } { \bar { \eta } _ { i , A } = \frac { 1 } { 3 ! } \epsilon _ { A B C D } \eta _ { i } ^ { B } \eta _ { i } ^ { C } \eta _ { i } ^ { D } } \end{array}$ and the minus sign is related to the order of the $\eta$ 's. The complete next-to-minimal form factor is obtained by summing over all four replacements and all insertion points.

# 2.2 One-loop form factors

In this subsection,we consider the one-loop minimal form factors in the SU(2) sector and show how to obtain the one-loop dilatation operator from them. This also allows us to introduce our notation and some important concepts that are required for the two-loop case. The results for the one-loop form factors, as well as the recipe to obtain the one-loop dilatation operator, were already given in [16]. Here,a useful new formulation, given in (2.11),is developed, which will be convenient to study the symmetry properties of form factors.

Form factors in the loop expansion can be written in the following form:

$$
\mathcal { F } _ { \mathcal { O } } = \big ( 1 + g ^ { 2 } \mathcal { Z } ^ { ( 1 ) } + g ^ { 4 } \mathcal { Z } ^ { ( 2 ) } + \dots \big ) \mathcal { F } _ { \mathcal { O } } ^ { ( 0 ) } .
$$

![](images/0d15698a78fcfe1e600572e2cf83e7bb31918579dcdc20ba62e07236c0d203f5.jpg)  
Figure 1: The one-loop $( p _ { 1 } + p _ { 2 } ) ^ { 2 }$ double cut.

For operators that are eigenstates under renormalisation， such as BPS operators or the Konishi primary, $\boldsymbol { \mathcal { T } ^ { ( \ell ) } }$ is simply the ratio of the $\ell$ -loop and tree-level form factor. However, for form factors of operators that renormalise non-diagonally, this is no longer the case, because the loop corrections to vanishing tree-level form factors can be non-vanishing. To overcome this problem, it is necessary to promote $\boldsymbol { \mathcal { T } ^ { ( \ell ) } }$ to an operator that acts on the tree-levl form factor $\mathcal { F } _ { \mathcal { O } } ^ { ( 0 ) }$ andcreatett

In the planar limit, connected $\ell$ -loop interactions can maximally involve $\ell + 1$ neighbouring fields in the colour-ordered form factor at a time. Hence, $\boldsymbol { \mathcal { T } ^ { ( \ell ) } }$ can be written as an interaction density that is summed over all insertion points. At one-loop order, the maximal interaction range is two,and we can write

$$
\mathcal { T } ^ { ( 1 ) } = \sum _ { i = 1 } ^ { L } { I _ { i i + 1 } ^ { ( 1 ) } } .
$$

Here,L denotes the length of the operator O, I(𝑖)1 (i+1 acts on the external felds i and i +1 and cyclic identification $i + L \sim i$ is understood. We depict $I _ { i i + 1 } ^ { ( 1 ) }$ ii+1as

$$
I _ { i i + 1 } ^ { ( 1 ) } = \binom { - 1 } { i - 1 } ,
$$

where we in general specify only the first field $i$ that is acted on when the range is explicitly specified by the number of occurring legs.

In the ${ \mathrm { S U } } ( 2 )$ sector, the following six range-two interactions are allowed by R-charge conservation: $X X  X X$ ， $X Y  X Y$ ， $X Y  Y X$ ， $Y Y  Y Y$ ， $Y X  Y X$ and $Y X  X Y$ . It is sufficient to consider the first three,as the last three can be obtained from them by replacing $X  Y$ ，which is a symmetry of the theory. We denote the contribution toagivencombinatioofetealfiels $Z _ { A } Z _ { B }  Z _ { C } Z _ { D }$ by $( I _ { i } ^ { ( 1 ) } ) _ { Z _ { A } Z _ { B } } ^ { Z _ { C } Z _ { D } }$ ，where $Z _ { 1 } = X$ ， $Z _ { 2 } = Y$ and $A , B , C , D = 1 , 2$ Intet $I _ { i i + 1 } ^ { ( 1 ) }$ 3 explicitly given by

$$
I _ { i i + 1 } ^ { ( 1 ) } = \sum _ { A , B , C , D = 1 } ^ { 2 } ( I _ { i } ^ { ( 1 ) } ) _ { Z _ { A } Z _ { B } } ^ { Z _ { C } Z _ { D } } \eta _ { i } ^ { C } \frac { \partial } { \partial \eta _ { i } ^ { A } } \eta _ { i + 1 } ^ { D } \frac { \partial } { \partial \eta _ { i + 1 } ^ { B } } .
$$

![](images/86ee1e532a7f5df34a2baf881db2b4c5c0e9f9a907d9fcbed1c3a91c7a16bd86.jpg)  
Table 1: Linear combinations of diagrams contributing to the minimal one-loop form factors in the ${ \mathrm { S U } } ( 2 )$ sector.

The matrix elements $( I _ { i } ^ { ( 1 ) } ) _ { z _ { A } z _ { B } } ^ { z _ { C } z _ { D } }$ can be computed via unitarity. In the one-loop case, we only need to consider the double cut shown in figure 1. Let us briefly consider the （204号 $( I _ { 1 } ^ { ( 1 ) } ) _ { X Y } ^ { Y X }$ Case. Thecut integrandgivenby

$$
\int \mathrm { d } \mathrm { L I P S } ( l _ { 1 } , l _ { 2 } ) \mathrm { d } ^ { 4 } \eta _ { l _ { 1 } } \mathrm { d } ^ { 4 } \eta _ { l _ { 2 } } \mathcal { F } _ { \mathcal { O } } ^ { ( 0 ) } ( l _ { 1 } ^ { X } , l _ { 2 } ^ { Y } , p _ { 3 } , \ldots , p _ { L } ; q ) \mathcal { A } _ { 4 } ^ { ( 0 ) } ( - l _ { 2 } , - l _ { 1 } , p _ { 1 } ^ { Y } , p _ { 2 } ^ { X } ) ,
$$

where the tree-level form factor is given in (2.3) and the four-point amplitude is given by the standard MHV expression. The labelling of the external legs with $X , Y$ in the tree-level amplitude and form factor means to take the corresponding $\eta$ components； for example, $\mathcal { A } _ { 4 } ( - l _ { 2 } , - l _ { 1 } , p _ { 1 } ^ { Y } , p _ { 2 } ^ { X } )$ means to take the component of $\mathcal { A } _ { 4 } ( - l _ { 2 } , - l _ { 1 } , p _ { 1 } , p _ { 2 } )$ containing the $( \eta _ { 1 } ^ { 2 } \eta _ { 1 } ^ { 4 } ) ( \eta _ { 2 } ^ { 1 } \eta _ { 2 } ^ { 4 } )$ factor. Integrating out the ${ \boldsymbol { \eta } } _ { l _ { i } }$ variables, the cut integrand is given by8

$$
( \eta _ { 1 } ^ { 2 } \eta _ { 1 } ^ { 4 } ) ( \eta _ { 2 } ^ { 1 } \eta _ { 2 } ^ { 4 } ) \mathcal { F } _ { \mathcal { O } } ^ { ( 0 ) } ( p _ { 1 } ^ { X } , p _ { 2 } ^ { Y } , p _ { 3 } , \ldots , p _ { L } ; q ) \big | _ { \eta _ { 1 } ^ { A } = \eta _ { 2 } ^ { A } = 1 } \int \mathrm { d } \mathrm { L I P S } ( l _ { 1 } , l _ { 2 } ) .
$$

The variables $\eta _ { 1 }$ and $\eta _ { 2 }$ indicate that the result is not necessarily proportional to the tree-level form factor of the original operator but to the one of the operator in which the corresponding $X$ and $Y$ fields are permuted. The occurring phase space integral is simply the cut of a scalar bubble integral:

![](images/0e3a2d7d0b348a23149c32fdbc597e394a24bc87449dec40c4b6e30e0dfdbda6.jpg)

Atone-loop level, thiscutissuffcienttodeterminethe matrix element $( I _ { 1 } ^ { ( 1 ) } ) _ { X Y } ^ { Y X }$ as the bubble integral. The other matrix elements can be obtained in a similar way. More details of such computations can be found e.g. in [16,17].

The one-loop results are summarised in table 1. It is interesting to note that

$$
( I _ { i } ^ { ( 1 ) } ) _ { X Y } ^ { X Y } + ( I _ { i } ^ { ( 1 ) } ) _ { X Y } ^ { Y X } = ( I _ { i } ^ { ( 1 ) } ) _ { X X } ^ { X X } .
$$

$$
\mathcal { F } _ { \mathcal { O } } ^ { ( 0 ) } ( p _ { 1 } ^ { X } , p _ { 2 } ^ { Y } , p _ { 3 } , \ldots , p _ { L } ; q ) \bigr | _ { \eta _ { 1 } ^ { A } = \eta _ { 2 } ^ { A } = 1 } = \frac { \partial ^ { 2 } } { \partial \eta _ { 1 } ^ { 1 } \partial \eta _ { 1 } ^ { 4 } } \frac { \partial ^ { 2 } } { \partial \eta _ { 2 } ^ { 2 } \partial \eta _ { 2 } ^ { 4 } } \mathcal { F } _ { \mathcal { O } } ^ { ( 0 ) } ( p _ { 1 } , \ldots , p _ { L } ; q ) \Bigr | _ { \eta _ { 1 } ^ { A } = \eta _ { 2 } ^ { A } = 0 } .
$$

This relation is a consequence of the SU(2) symmetry of the theory. Let us establish a formalism to deal with these symmetries in more detail since it demonstrates the general principle of how symmetries can be used to study form factors.

The PSU $( 2 , 2 | 4 )$ symmetry of $\mathcal { N } = 4$ SYM theory leads to the following Ward identity of form factors:

$$
\sum _ { i = 1 } ^ { n } \Im _ { i } ^ { A } \mathcal { F } _ { \mathcal { O } } ( 1 , \dots , n ; q ) = \mathcal { F } _ { \mathfrak { I } ^ { A } \mathcal { O } } ( 1 , \dots , n ; q ) ,
$$

which holds for any generator $\Im _ { i } ^ { A }$ of PSU $( 2 , 2 | 4 )$ ; see e.g. [4] for a detailed derivation. Let us consider explicitly the generators9

$$
\mathfrak { I } _ { i } ^ { 1 } = \eta _ { i } ^ { 1 } \frac { \partial } { \partial \eta _ { i } ^ { 2 } } + \eta _ { i } ^ { 2 } \frac { \partial } { \partial \eta _ { i } ^ { 1 } } , \quad \mathfrak { I } _ { i } ^ { 2 } = - i \eta _ { i } ^ { 1 } \frac { \partial } { \partial \eta _ { i } ^ { 2 } } + i \eta _ { i } ^ { 2 } \frac { \partial } { \partial \eta _ { i } ^ { 1 } } , \quad \mathfrak { I } _ { i } ^ { 3 } = \eta _ { i } ^ { 1 } \frac { \partial } { \partial \eta _ { i } ^ { 1 } } - \eta _ { i } ^ { 2 } \frac { \partial } { \partial \eta _ { i } ^ { 2 } }
$$

of SU(2). Applying (2.17) to (2.8) for the minimal tree-level and one-loop form factor, we find

$$
[ \mathfrak { I } ^ { A } , \mathcal { T } ^ { ( 1 ) } ] = 0 ,
$$

where $\begin{array} { r } { \Im ^ { A } = \sum _ { i = 1 } ^ { L } \Im _ { i } ^ { A } } \end{array}$ . Inserting (2.11) into (2.19) yields (2.16) as well as similar identities.

The results of table $^ 1$ contain the one-mass triangle and bubble integral, for which explicit expressions can be found e.g. in [59]. The one-mass triangle integral is IR divergent and UV finite. The bubble integral,on the other hand,is IR finite but UV divergent. Hence, the IR and UV divergences can be separated immediately.

The IR divergences of the above results match the universal form of one-loop IR divergences [1]:

$$
\begin{array} { l } { \left. I _ { i i + 1 } ^ { ( 1 ) } \right| _ { \mathrm { I R } } = - \displaystyle \frac { 1 } { \varepsilon ^ { 2 } } ( - s _ { i i + 1 } ) ^ { - \varepsilon } \mathbb { 1 } _ { i i + 1 } + { \mathcal O } ( \varepsilon ^ { 0 } ) } \\ { = \left[ - \frac { \gamma _ { \mathrm { c u s p } } ^ { ( 1 ) } } { 8 \varepsilon ^ { 2 } } - \frac { { \mathcal G } _ { 0 } ^ { ( 1 ) } } { 4 \varepsilon } \right] ( - s _ { i i + 1 } ) ^ { - \varepsilon } \mathbb { 1 } _ { i i + 1 } + { \mathcal O } ( \varepsilon ^ { 0 } ) , } \end{array}
$$

where $\gamma _ { \mathrm { c u s p } } ^ { ( 1 ) } = 8$ is the one-loop cusp anomalous dimension and $\mathcal { G } _ { 0 } ^ { ( 1 ) } = 0$ is the one-loop collinear anomalous dimension. We have also introduced the identity operator

$$
\mathbb { 1 } _ { i i + 1 } = \sum _ { A , B = 1 } ^ { 2 } \eta _ { i } ^ { A } \frac { \partial } { \partial \eta _ { i } ^ { A } } \eta _ { i + 1 } ^ { B } \frac { \partial } { \partial \eta _ { i + 1 } ^ { B } } .
$$

The UV divergences require the renormalisation of the operators. The renormalised operators are defined in terms of the bare operators and the renormalisation constant $\mathcal { Z }$ （20 as shown in (1.2). The renormalised form factor is nothing but the form factor of the renormalised operator.l0 Since the form factor is linear in the operator,we can write in the case of the minimal form factor:

$$
\mathcal { F } _ { \mathcal { Z O } } ^ { ( 0 ) } ( 1 , \dots , L ; q ) = \mathcal { Z F } _ { \mathcal { O } } ^ { ( 0 ) } ( 1 , \dots , L ; q ) ,
$$

where,on the right hand side, $\mathcal { Z }$ acts as an operator on the tree-level form factor,similar to $\boldsymbol { \mathcal { T } ^ { ( \ell ) } }$ discussed before, cf. (2.8).

At one-loop level, $\mathcal { Z } ^ { ( 1 ) }$ has to render the renormalised one-loop interaction

$$
\underline { { \underline { { \tau } } } } ^ { ( 1 ) } = \underline { { \underline { { \tau } } } } ^ { ( 1 ) } + \mathcal { Z } ^ { ( 1 ) }
$$

UV finite. This means that $\mathcal { Z } _ { i i + 1 } ^ { ( 1 ) }$ hastocaeltUVdvegeeftebe occurring in I1)1: . The UV divergence of the bubble integral is given by $\frac { 1 } { \varepsilon }$ .11 Accordingly, using the results in table $^ 1$ , the one-loop renormalisation constant density is given by the matrix elements

$$
( \mathcal { Z } _ { i } ^ { ( 1 ) } ) _ { x x } ^ { x x } = 0 , \qquad ( \mathcal { Z } _ { i } ^ { ( 1 ) } ) _ { x Y } ^ { x Y } = \frac { 1 } { \varepsilon } , \qquad ( \mathcal { Z } _ { i } ^ { ( 1 ) } ) _ { x Y } ^ { Y X } = - \frac { 1 } { \varepsilon } .
$$

It can be written in the compact operatorial form

$$
\mathcal { Z } _ { i i + 1 } = \binom { \longmapsto } { \underbrace { \mathcal { Z } _ { i } ^ { ( 1 ) } } } = \frac { 1 } { \varepsilon } ( \mathbb { 1 } - \mathbb { P } ) _ { i i + 1 } ,
$$

where $^ { 1 }$ is the identity operator (2.21） and

$$
\mathbb { P } _ { i i + 1 } = \sum _ { A , B = 1 } ^ { 2 } \eta _ { i } ^ { B } \frac { \partial } { \partial \eta _ { i } ^ { A } } \eta _ { i + 1 } ^ { A } \frac { \partial } { \partial \eta _ { i + 1 } ^ { B } }
$$

denotes the permutation operator.

In analogy to the renormalisation constant,we can also write the dilatation operator as an operator acting on the minimal tree-level form factor. Applying (1.3) to (2.24),we find the one-loop dilatation operator density

$$
( \mathfrak { D } _ { i } ^ { ( 1 ) } ) _ { x x } ^ { x x } = 0 , \qquad ( \mathfrak { D } _ { i } ^ { ( 1 ) } ) _ { x Y } ^ { x Y } = 2 , \qquad ( \mathfrak { D } _ { i } ^ { ( 1 ) } ) _ { x Y } ^ { Y X } = - 2 .
$$

These expressions can be combined into the well-known form [32]

$$
\mathfrak { D } _ { i i + 1 } ^ { ( 1 ) } = 2 ( \mathbb { 1 } - \mathbb { P } ) _ { i i + 1 } .
$$

Let us now proceed to two-loop order.

# 2.3 Two-loop form factors

In the two-loop case, the range of connected interactions can be either two or three. Furthermore, two disconnected one-loop interactions can occur at two-loop level. In total, we can introduce the two-loop operator $\mathcal { T } ^ { ( 2 ) }$ similar to the one-loop case as

$$
\mathcal { T } ^ { ( 2 ) } = \sum _ { i = 1 } ^ { L } \left( I _ { i i + 1 i + 2 } ^ { ( 2 ) } + I _ { i i + 1 } ^ { ( 2 ) } + \frac { 1 } { 2 } \sum _ { j = i + 2 } ^ { L + i - 2 } I _ { i i + 1 } ^ { ( 1 ) } I _ { j j + 1 } ^ { ( 1 ) } \right) ,
$$

![](images/cb8f5d10788e258384822f295d91e639253f2da69fe9d4c6eb6a75321d3c09ad.jpg)  
Table 2: Linear combinations of diagrams of range two contributing to the minimal twoloop form factors in the SU(2) sector. Terms between horizontal lines always occur in fixed combinations.

where the last term accounts for the insertion of two one-loop interactions i+1 at nonoverlapping positions.The two-loopinteractions (2)1 ii+1 and 1(2) ii+1i+2 are given by

$$
\begin{array} { r l } { I _ { i i + 1 } ^ { ( 2 ) } = } & { \overbrace { \binom { I _ { i } ^ { ( 2 ) } } { \omega _ { \downarrow } - I } } ^ { \left( \digamma \right) } = \underset { A , B , C , D = 1 } { \sum } ( I _ { i } ^ { ( 2 ) } ) _ { z _ { A } z _ { B } } ^ { z _ { C } z _ { D } } \eta _ { i } ^ { C } \frac { \partial } { \partial \eta _ { i } ^ { A } } \eta _ { i + 1 } ^ { D } \frac { \partial } { \partial \eta _ { i + 1 } ^ { B } } , } \\ { I _ { i i + 1 i + 2 } ^ { ( 2 ) } = \sqrt { \underset { i , B , C , D , E , F = 1 } { \sum } } ( I _ { i } ^ { ( 2 ) } ) _ { z _ { A } z _ { B } z _ { C } } ^ { z _ { D } z _ { E } z _ { F } } \frac { \partial } { \partial \eta _ { i } ^ { A } } \frac { \partial } { \partial \eta _ { i + 1 } ^ { A } } \frac { \partial } { \partial \eta _ { i + 1 } ^ { B } } \eta _ { i + 2 } ^ { F } \frac { \partial } { \partial \eta _ { i + 2 } ^ { C } } . } \end{array}
$$

For interaction range two,three distinct cases occur: $X X  X X$ ， $X Y  X Y$ and $X Y  Y X$ .For interaction range three, six distinct cases occur: $X X X  X X X$ ， $X X Y  X X Y$ ， $X Y X  X Y X$ ， $X X Y  X Y X$ ， $X Y X  X X Y$ and $X X Y  Y X X$ ： The remaining combinations can be obtained from these cases by exchanging $X ~  ~ Y$ （204号 and by using parity, i.e. reverting the order of the fields. We collect our results for the corresponding matrix elements in table 2 and table 3. The matrix elements $( I _ { i } ^ { ( 2 ) } ) _ { X X } ^ { X X }$ and （204号 $( I _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { X X X }$ occurintheBPScaseand werecomputedin[14]usingtheunitaritymethod. The other matrix elements can be calculated in a similar but slightly more involved computation. Let us give a brief account of this computation.

The cuts that have to be considered are depicted in figures 2a, 2b, 2c and 2d. The treelevel next-to-minimal and one-loop minimal form factors,which occur as building blocks, are given in subsections 2.1 and 2.2， respectively. The required tree-level and one-loop amplitudes are standard. A particularly interesting cut is the triple cut shown in figure 2d, which involves the tree-level next-to-MHV six-point scalar amplitudes. As given explicitly in appendix A, these scalar amplitudes take a simple form in terms of Mandelstam variables. Let us consider for example the $( I _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { Y X X }$ case.Thecutintegrand is givenbytheproduct of the minimal tree-level form factor and the six-point tree-level amplitude:

<html><body><table><tr><td></td><td>RAAARAAAAAA Si+2</td><td>Si+1i+2</td><td></td><td>Sil</td><td>i+2 Sii+1</td><td>Sii+li i+2</td><td>i+2 Sii+1Si+2l</td><td>2 SilSi+li+2</td></tr><tr><td>0</td><td>0 0</td><td>0</td><td>0</td><td>0 0</td><td>0</td><td>-1</td><td>+ +1</td><td>xxx</td></tr><tr><td>0</td><td>0</td><td>0</td><td>0</td><td>-1 +</td><td>+1</td><td>-1</td><td>±±</td><td>xxY</td></tr><tr><td>+1</td><td>+</td><td></td><td>+1</td><td>-1 +</td><td>士</td><td>-1</td><td>±±</td><td></td></tr><tr><td>0</td><td>0 0</td><td>0</td><td></td><td>+1 -1</td><td>1</td><td>0</td><td>0 0</td><td>xxx</td></tr><tr><td>-1</td><td>0 0</td><td>0</td><td>0</td><td>土 1</td><td></td><td>0</td><td>0 0</td><td></td></tr><tr><td>0</td><td>0</td><td>0 0</td><td></td><td>0 0</td><td>0</td><td>0</td><td>0 0</td><td></td></tr></table></body></html>

![](images/c953300a8c99adcb2d9e21a99ad9e62a02d991dccbfc71bd4e954375445f8f49.jpg)  
Figure 2: Unitary cuts of the minimal two-loop form factor

$$
\int \mathrm { d } \mathrm { L I P S } ( l _ { 1 } , l _ { 2 } , l _ { 3 } ) \prod _ { i = 1 } ^ { 3 } \mathrm { d } ^ { 4 } \eta _ { l _ { i } } \mathcal { F } _ { \mathcal { O } } ^ { ( 0 ) } ( l _ { 1 } ^ { X } , l _ { 2 } ^ { X } , l _ { 3 } ^ { Y } , p _ { 4 } , \ldots , p _ { L } ; q ) \mathcal { A } _ { 6 } ( - l _ { 3 } , - l _ { 2 } , - l _ { 1 } , p _ { 1 } ^ { Y } , p _ { 2 } ^ { X } , p _ { 3 } ^ { X } ) .
$$

After integrating out the ${ \boldsymbol { \eta } } _ { l _ { i } }$ variables, we obtain

$$
\begin{array} { r l r } & { } & { \mathcal { F } _ { \mathcal { O } } ^ { ( 0 ) } ( p _ { 1 } ^ { X } , p _ { 2 } ^ { X } , p _ { 3 } ^ { Y } , \dots , p _ { L } ; q ) \big | _ { \eta _ { 1 } ^ { A } = \eta _ { 2 } ^ { A } = \eta _ { 3 } ^ { A } = 1 } ( \eta _ { 1 } ^ { 2 } \eta _ { 1 } ^ { 4 } ) ( \eta _ { 2 } ^ { 1 } \eta _ { 2 } ^ { 4 } ) ( \eta _ { 3 } ^ { 1 } \eta _ { 3 } ^ { 4 } ) } \\ & { } & { \qquad \times \displaystyle \int \mathrm { d } \mathrm { L I P S } ( l _ { 1 } , l _ { 2 } , l _ { 3 } ) \frac { 1 } { ( - l _ { 1 } + p _ { 1 } + p _ { 2 } ) ^ { 2 } } , } \end{array}
$$

where we have used (A.2) for $( A ^ { ( 0 ) } ) _ { X X Y } ^ { Y X X }$ 12The phase spacintegralcorrspondstthe triple-cut loop integral

$$
\begin{array}{c} \frac  \underset { \overset { . } { 1 } ^ { \prime } } { \underset { . } { \overset { . } { 1 } } } \underset { . } { \overset { . } { \underset { . } { \overset { . } { 1 } } } } \underset { . } { \overset { . } { \underset { . } { \overset { . } { 1 } } } } \underset { . } { \overset { . } { \underset { . } { \overset { . } { 1 } } } } \underset { . } { \overset { . } { \underset { . } { \overset { . } { 1 } } } } \underset { . } { \overset { . } { \underset { . } { \overset { . } { 1 } } } } \end{array}
$$

Similarly, each term in the other amplitudes in (A.2) is mapped to one graph in table 3 via the triple cut.

Looking at table 2 and table 3 and using the parity transformation, we observe some linear identities, e.g.

$$
( I _ { i } ^ { ( 2 ) } ) _ { X Y } ^ { X Y } + ( I _ { i } ^ { ( 2 ) } ) _ { X Y } ^ { Y X } = ( I _ { i } ^ { ( 2 ) } ) _ { X X } ^ { X X } ,
$$

and

$$
\begin{array} { r } { ( I _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { Y X X } + ( I _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y X } + ( I _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X X Y } = ( I _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { X X } , } \\ { ( I _ { i } ^ { ( 2 ) } ) _ { X Y X } ^ { X Y X } + ( I _ { i } ^ { ( 2 ) } ) _ { X Y X } ^ { Y X X } + ( I _ { i } ^ { ( 2 ) } ) _ { X Y X } ^ { X X Y } = ( I _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { X X } , } \\ { ( I _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y X } + ( I _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { Y X X } = ( I _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { X Y } + ( I _ { i } ^ { ( 2 ) } ) _ { Y X X } ^ { X X Y } . } \end{array}
$$

Similar to the one-loop case, all these identities are a consequence of SU(2) invariance and follow from the Ward identity (2.17),which at two-loop order yields

$$
[ \mathfrak { I } ^ { A } , \mathcal { T } ^ { ( 2 ) } ] = 0 .
$$

Given the full integrand of the two-loop form factor, we can perform a similar analysis as in the one-loop case. However,we will see that this requires a more involved subtraction of the IR divergences. This will be the topic of the next section.

# 3Two-loop dilatation operator and remainder function

In the one-loop case,the UV divergences stem from the bubble integrals alone. Therefore, the one-loop renormalisation constant can be read off directly from the coefficient of these integrals. This is no longer true for two-loop form factors, since the two-loop integrals in general contain a mixing of IR and UV divergences. However, IR divergences have a well-understood universal structure [37-40]. This allows us to subtract the IR divergences systematically using the BDS ansatz [41, 42].

Similar to the one-loop case (2.23), the two-loop renormalised form factor is given by

$$
\underline { { \tau } } ^ { ( 2 ) } = \mathcal { T } ^ { ( 2 ) } + \mathcal { T } ^ { ( 1 ) } \mathcal { Z } ^ { ( 1 ) } + \mathcal { Z } ^ { ( 2 ) } ,
$$

where

$$
\mathcal { Z } ^ { ( 2 ) } = \sum _ { i = 1 } ^ { L } \left( \mathcal { Z } _ { i i + 1 i + 2 } ^ { ( 2 ) } + \frac { 1 } { 2 } \sum _ { j = i + 2 } ^ { L + i - 2 } \mathcal { Z } _ { i i + 1 } ^ { ( 1 ) } \mathcal { Z } _ { j j + 1 } ^ { ( 1 ) } \right) .
$$

Applying the BDS ansatz [41, 42] to the renormalised form factors, we obtain a finite two-loop remainder function:

$$
\mathcal { R } ^ { ( 2 ) } = \underline { { \mathbb { Z } } } ^ { ( 2 ) } ( \varepsilon ) - \frac { 1 } { 2 } \left( \underline { { \mathbb { Z } } } ^ { ( 1 ) } ( \varepsilon ) \right) ^ { 2 } - f ^ { ( 2 ) } ( \varepsilon ) \underline { { \mathbb { Z } } } ^ { ( 1 ) } ( 2 \varepsilon ) + \mathcal { O } ( \varepsilon ) ,
$$

where

$$
f ^ { ( 2 ) } ( \varepsilon ) = - 2 \zeta _ { 2 } - 2 \zeta _ { 3 } \varepsilon - 2 \zeta _ { 4 } \varepsilon ^ { 2 } .
$$

At two-loop order, connected interactions involve at most three fields of the composite operator, which have to be adjacent at the planar level. Hence, both the remainder function and the dilatation operator can be written in terms of densities that act only on triples of neighbouring sites at a time and are summed over all $L$ insertion points. For each triple of neighbouring points,we define the variables

$$
\begin{array} { r } { u _ { i } = \frac { s _ { i i + 1 } } { s _ { i i + 1 i + 2 } } , \quad v _ { i } = \frac { s _ { i + 1 i + 2 } } { s _ { i i + 1 i + 2 } } , \quad w _ { i } = \frac { s _ { i + 2 i } } { s _ { i i + 1 i + 2 } } , } \end{array}
$$

where

$$
s _ { i i + 1 i + 2 } = s _ { i i + 1 } + s _ { i + 1 i + 2 } + s _ { i + 2 i }
$$

and cyclic identification $i \sim i + L$ is understood. These variables satisfy $u _ { i } + v _ { i } + w _ { i } = 1$ ： The remainder $\mathcal { R } ^ { ( 2 ) }$ can be written in terms of its density as

$$
\mathcal { R } ^ { ( 2 ) } = \sum _ { i = 1 } ^ { L } R _ { i i + 1 i + 2 } ^ { ( 2 ) } .
$$

An important subtlety arises due to the fact that the composite operators are not necessarily eigenstates under renormalisation. This requires a careful treatment of the product of one-loop form factors in (3.3). As already mentioned, the renormalisation constant is a matrix (i.e.an operator) and so are the interactions. Hence,the one-loop product in (3.3) should be understood as a product of operators. This can be explicitly depicted by the following equation in terms of graphs:

$$
\Big ( \underline { { Z } } ^ { ( 1 ) } ( \varepsilon ) \Big ) ^ { 2 } = \sum _ { i = 1 } ^ { L } \left( \frac { \binom { i - 1 } { 2 } } { \underset { i = 1 } { \overset { . } { \sum } } } \right) + \frac { \Big | \binom { i - 1 } { 2 } } { \underset { i = 1 } { \overset { . } { \sum } } } + \frac { \binom { i - 1 } { 2 } } { \underset { i = 1 } { \overset { . } { \prod } } } + \frac { 1 } { 2 } \left| \binom { i - 1 } { \underset { i = 1 } { \overset { . } { \sum } } } + \sum _ { j = i + 2 } ^ { L + i - 2 } \underset { i = j } { \overset { . } { \sum } } \binom { i - 1 } { \underset { i = 1 } { \overset { . } { \sum } } } \binom { i - 1 } { \underset { i = 1 } { \overset { . } { \sum } } } \right| .
$$

Note that the states corresponding to the internal lines are summed over as required for a product of operators. The prefactors of $\textstyle { \frac { 1 } { 2 } }$ stem from distributing products of densities with effective range two equally between the first two and the last two sites.

The remainder density, which itself is an operator, can be similarly expressed by the following graph equation:

$$
\begin{array} { r l } & { R _ { i \dot { i } + 1 \dot { i } + 2 } ^ { ( 2 ) } = } \\ &  \qquad \frac { 1 } { 2 } \underset  \underset { \left( \underset { \left( \underset { \sum _ { i } ^ { ( i ) } } { 1 + 1 } \right) } { \binom { k - \frac { i } { i } } { i - 1 } } \right) } { \binom { k - \frac { i } { i - 1 } } { i - 1 } } + \frac { 1 } { 2 } \left| \underset  \left( \underset { \underset { \sum _ { i + 1 } ^ { ( i ) } } { 1 + 1 } \right) } { \binom { k - \frac { i } { i + 1 } } { i - 1 } } + \left. \underset { \underset { \sum _ { i - 1 } ^ { ( i ) } } { \overset { k - \frac { i } { i + 1 } } { \underset { \sum _ { i } ^ { ( i ) } } { \sum _ { i } ^ { ( i ) } } } + 1 } + \frac { 1 } { 2 } \underset { \left( \underset { \sum _ { i - 1 } ^ { ( i ) } } { 1 + 1 } \right) } { \binom { k - \frac { i } { i + 1 } } { i - 1 } } \right| + \underset { \left( \underset { \sum _ { i - 1 } ^ { ( i ) } } { 1 + 1 } \right) } { \binom { k - \frac { i } { i + 1 } } { i - 1 } } + \frac { 1 } { 2 } \left| \underset { \left( \underset { \sum _ { i + 1 } ^ { ( i ) } } { 1 + 1 } \right) } { \binom { k - \frac { i } { i + 1 } } { i + 1 } } + \right. } \\ &  \qquad - \frac { 1 } { 2 } \left( \underset { \left( \underset { \sum _ { i } ^ { ( i ) } } { 1 + 1 } \right) } { \binom { k - \frac { i } { i } } { i - 1 } } \right| + \underset { \left( \underset { \sum _ { i - 1 } ^ { ( i ) } } { 1 + 1 } \right) } { \binom { k - \frac { i } { i - 1 } } { i } } + \frac { \binom { k - \frac { i } { i } } { i } } { \binom { k - \frac { i + 1 } { i } } { i - 1 } } \right) + \frac { 1 } { 2 } \left| \underset { \left( \underset { \sum _ { i - 1 } ^ { ( i ) } } { 1 + 1 } \right) } { \binom { k - \frac { i } { i + 1 } } { i - 1 } } \right| - f ^ { ( 2 ) } \left( \frac { 1 } { 2 } \underset { \left( \underset { \sum _ { i - 1 } ^ { ( i ) } } { \binom { k - 1 } { i } } \right) } { \binom { k - \frac { i } { i + 1 } } { i - 1 } } \right| + \frac { 1 } { 2 } \binom { k - \frac { i } { i + 1 } } { i - 1 } \underset { \left( \underset { \sum _ { i - 1 } ^ { ( i ) } } { 1 + 1 } \right) }  \binom  k - \frac { i }  i \end{array}
$$

where we have depicted thetwo-loop renormalisation constant density Z(2) ii+li+2 analogously to 1(2) $I _ { i i + 1 i + 2 } ^ { ( 2 ) }$ . Requiring that this remainder density is finite allows us to fix the two-loop renormalisation constant density.

The integrals occurring in the two-loop result can be reduced to master integrals via IBP reduction,e.g. as implemented in the Mathematica package LiteRed [60]. The resulting master integrals can be found in [61].

# 3.1 Renormalisation constant and dilatation operator

From the requirement that the two-loop renormalisation constant densities have to cancel all divergences in (3.9), we find

$$
\begin{array} { r l r l r l } & { ( \mathcal { Z } _ { i } ^ { ( 2 ) } ) _ { x x x } ^ { x x } = 0 , \quad } & & { ( \mathcal { Z } _ { i } ^ { ( 2 ) } ) _ { x y x } ^ { x Y x } = + \displaystyle \frac { 2 } { \mathcal { E } ^ { 2 } } - \frac { 2 } { \mathcal { E } } , \quad } & & { ( \mathcal { Z } _ { i } ^ { ( 2 ) } ) _ { x x Y } ^ { x X } = + \displaystyle \frac { 1 } { 2 \varepsilon ^ { 2 } } - \frac { 1 } { 2 \varepsilon } , } & \\ & { ( \mathcal { Z } _ { i } ^ { ( 2 ) } ) _ { x Y X } ^ { x x Y } = - \displaystyle \frac { 1 } { \varepsilon ^ { 2 } } + \frac { 1 } { \varepsilon } , \quad } & & { ( \mathcal { Z } _ { i } ^ { ( 2 ) } ) _ { x X Y } ^ { x Y x } = - \displaystyle \frac { 1 } { \varepsilon ^ { 2 } } + \frac { 1 } { \varepsilon } , \quad } & & { ( \mathcal { Z } _ { i } ^ { ( 2 ) } ) _ { x X Y } ^ { Y x x } = + \displaystyle \frac { 1 } { 2 \varepsilon ^ { 2 } } - \frac { 1 } { 2 \varepsilon } . } & \end{array}
$$

Alternatively, this can be written in the operatorial forml3

$$
\mathcal { Z } _ { i i + 1 } ^ { ( 2 ) } { } _ { i + 1 } { } _ { i + 2 } = \frac { 1 } { 2 } \left( \frac { 1 } { \varepsilon ^ { 2 } } - \frac { 1 } { \varepsilon } \right) \left( \mathbb { P } _ { i i + 1 } \mathbb { P } _ { i + 1 } { } _ { i + 2 } + \mathbb { P } _ { i + 1 } { } _ { i + 2 } \mathbb { P } _ { i + 1 } - 3 \mathbb { P } _ { i + 1 } - 3 \mathbb { P } _ { i + 1 } { } _ { i + 2 } + 4 \right) .
$$

Using (1.3)，we have for the two-loop dilatation operator

$$
{ \mathfrak { D } } ^ { ( 2 ) } = 4 \varepsilon { \Big ( } { \mathcal { Z } } ^ { ( 2 ) } - { \frac { 1 } { 2 } } ( { \mathcal { Z } } ^ { ( 1 ) } ) ^ { 2 } { \Big ) } ,
$$

where $( \mathcal { Z } ^ { ( 1 ) } ) ^ { 2 }$ should be understood as a product of operators.For example

$$
\begin{array} { r l r } & { } & { ( \mathfrak { D } _ { i } ^ { ( 2 ) } ) _ { x x Y } ^ { x Y x } = 4 \varepsilon \left( ( \mathcal { Z } _ { i } ^ { ( 2 ) } ) _ { x x Y } ^ { x Y x } - \frac { 1 } { 2 } ( \mathcal { Z } _ { i + 1 } ^ { ( 1 ) } ) _ { x Y } ^ { Y X } ( \mathcal { Z } _ { i } ^ { ( 1 ) } ) _ { x x } ^ { x x } - \frac { 1 } { 2 } ( \mathcal { Z } _ { i } ^ { ( 1 ) } ) _ { x Y } ^ { x Y } ( \mathcal { Z } _ { i + 1 } ^ { ( 1 ) } ) _ { x Y } ^ { Y X } \right. } \\ & { } & { \left. \qquad - \frac { 1 } { 4 } ( \mathcal { Z } _ { i + 1 } ^ { ( 1 ) } ) _ { x Y } ^ { Y X } ( \mathcal { Z } _ { i + 1 } ^ { ( 1 ) } ) _ { X Y } ^ { X Y } - \frac { 1 } { 4 } ( \mathcal { Z } _ { i + 1 } ^ { ( 1 ) } ) _ { Y X } ^ { Y X } ( \mathcal { Z } _ { i + 1 } ^ { ( 1 ) } ) _ { x Y } ^ { Y X } \right) = 4 . } \end{array}
$$

In total, we have

$$
\begin{array} { r l r l r l r } & { ( \mathfrak { D } _ { i } ^ { ( 2 ) } ) _ { x x x } ^ { x x } = 0 , \quad } & & { ( \mathfrak { D } _ { i } ^ { ( 2 ) } ) _ { x Y X } ^ { x Y X } = - 8 , \quad } & & { ( \mathfrak { D } _ { i } ^ { ( 2 ) } ) _ { x X Y } ^ { x X Y } = - 2 , } \\ & { ( \mathfrak { D } _ { i } ^ { ( 2 ) } ) _ { x Y X } ^ { x x Y } = 4 , \quad } & & { ( \mathfrak { D } _ { i } ^ { ( 2 ) } ) _ { x X Y } ^ { x Y X } = 4 , \quad } & & { ( \mathfrak { D } _ { i } ^ { ( 2 ) } ) _ { x X Y } ^ { Y X X } = - 2 , } \end{array}
$$

which agrees exactly with the known result [33]

$$
\mathfrak { D } _ { i i + 1 i + 2 } ^ { ( 2 ) } = - 2 \bigl ( \mathbb { P } _ { i i + 1 } \mathbb { P } _ { i + 1 i + 2 } + \mathbb { P } _ { i + 1 i + 2 } \mathbb { P } _ { i i + 1 } - 3 \mathbb { P } _ { i i + 1 } - 3 \mathbb { P } _ { i + 1 i + 2 } + 4 \bigr ) .
$$

# 3.2 Finite remainders

Next,we calculate the finite remainder densities. The remainder densities fulfil analogous relations to (2.35):

$$
\begin{array} { r } { ( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { Y X X } + ( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y X } + ( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X X Y } = ( R _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { X X } \mathrm { , } } \\ { ( R _ { i } ^ { ( 2 ) } ) _ { X Y X } ^ { X Y X } + ( R _ { i } ^ { ( 2 ) } ) _ { X Y X } ^ { Y X X } + ( R _ { i } ^ { ( 2 ) } ) _ { X Y X } ^ { X X Y } = ( R _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { X X X } \mathrm { , } } \\ { ( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y X } + ( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { Y X X } = ( R _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { X Y } + ( R _ { i } ^ { ( 2 ) } ) _ { Y X X } ^ { X X Y } \mathrm { . } } \end{array}
$$

These are equally a consequence of SU(2) symmetry and can be derived from

$$
[ \mathfrak { I } ^ { A } , \mathcal { R } ^ { ( 2 ) } ] = 0 ,
$$

which is a consequence of (2.19) and (2.36). Combining (3.16) with the symmetry under te eska gest $X  Y$ mst m， derd s Hec, iea $( R _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { X X X }$ $( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y X }$ $( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { Y X X }$ to consider these three cases.

Thereainderdesity)xasleadsiedindisof transcendentality four:

$$
( R _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { X X X } = ( R _ { i } ^ { ( 2 ) } ) _ { X X X } ^ { X X X } \Big \vert _ { 4 } ,
$$

which is given explicitly as

$$
\begin{array} { r l } & { | ( \overline { { g } } _ { i } ^ { ( j ) } ) _ { \mathcal { N } , \overline { { x } } } | _ { 0 } } \\ & { = - \operatorname { I m } _ { i } ( 1 - s _ { i } ) - \operatorname { I m } _ { i } ( u _ { i } ) - \operatorname { I m } _ { i } ( \frac { u _ { i } } { \operatorname { I m } _ { i } } - 1 ) - \operatorname { I m } _ { i } ( \frac { 1 - u _ { i } } { \operatorname { I m } _ { i } } ) [ \operatorname { I m } _ { i } ( \frac { s _ { i } } { \operatorname { I m } _ { j } } - 1 ) - \operatorname { I m } _ { i } ( 1 - u _ { i } ) ] } \\ & { \quad - \operatorname { I m } _ { i } ( \operatorname { I m } _ { i } [ \operatorname { I m } _ { i } ( \frac { s _ { i } } { \operatorname { I m } _ { i } } ) + \operatorname { I m } _ { i } ( - \frac { u _ { i } } { \operatorname { I m } _ { j } } ) - \operatorname { I m } _ { i } ( \frac { s _ { i } - 1 } { \operatorname { I m } _ { j } } ) - \frac { 1 } { 3 } ] \operatorname { I m } _ { i } \operatorname { S p } ^ { ( 2 ) } ( \frac { 1 - u _ { i } } { \operatorname { I m } _ { i } } ) - \frac { 1 } { 3 } \operatorname { I m } _ { i } \operatorname { S p } ^ { ( 4 ) } ( 1 - u _ { i } ) ) } \\ & { \quad - \operatorname { I m } _ { i } ( \frac { 1 } { \operatorname { I m } _ { i } } - 1 ) \operatorname { I m } _ { j } ( \frac { 1 } { \operatorname { I m } _ { i } } ) + \operatorname { I m } _ { i } ( \frac { 1 - u _ { i } } { \operatorname { I m } _ { j } } ) [ \operatorname { I m } _ { i } ( \frac { 1 - u _ { i } } { \operatorname { I m } _ { j } } ) \operatorname { I m } _ { i } ( \frac { 1 } { \operatorname { I m } _ { i } } ) - \frac { 1 } { 3 } \operatorname { I m } _ { i } \operatorname { S p } ^ { ( 2 ) } ( \frac { 1 - u _ { i } } { \operatorname { I m } _ { i } } ) ] } \\ &  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \frac { 1 } { 2 } \operatorname { I m } _ { i } ^ { ( j ) } ( 1 - u _ { i } ) - \operatorname { I m } _ { i } \operatorname { I m } _ { j } ^ { ( j ) } ( 1 - u _ { i } ) \operatorname { I m } _ { i } ( \frac { 1 } { \operatorname { I m } _ { i } } ) \operatorname { I m } _ { i } ( u _ { i } ^ { ( j ) } ) \operatorname { I m } _ { j } ( u _ { i } ^ { ( j ) } ) \operatorname  I m \end{array}
$$

Here, the Goncharov polylogarithm in the last line is the only piece that cannot be written in terms of classical polylogarithms. This relatively compact expression was obtained using the symbol techniques [62, 63]. The corresponding symbol is given by [14]14

$$
\begin{array} { r } { 5 ( ( R _ { i } ^ { ( 2 ) } ) _ { x x x } ^ { x x } \Big | _ { 4 } ) = - u _ { i } \otimes ( 1 - u _ { i } ) \otimes [ \frac { u _ { i } - 1 } { u _ { i } } \otimes \frac { v _ { i } } { w _ { i } } + \frac { v _ { i } } { w _ { i } } \otimes \frac { w _ { i } ^ { 2 } } { u _ { i } v _ { i } } ] - u _ { i } \otimes u _ { i } \otimes \frac { 1 - u _ { i } } { v _ { i } } \otimes \frac { w _ { i } } { v _ { i } } } \\ { - u _ { i } \otimes v _ { i } \otimes \frac { v _ { i } } { w _ { i } } \otimes \frac { u _ { i } } { w _ { i } } - u _ { i } \otimes v _ { i } \otimes \frac { u _ { i } } { w _ { i } } \otimes \frac { v _ { i } } { w _ { i } } + ( u _ { i }  v _ { i } ) . \qquad ( 3 . 2 0 ) } \end{array}
$$

The remainder density $( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y X }$ is of mixed transcendentality with degreeranging from three to zero. Its contribution of degree three has the symbol

$$
\mathcal { S } \left( ( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y X } \Big | _ { 3 } \right) = v _ { i } \otimes \frac { v _ { i } } { 1 - v _ { i } } \otimes \frac { u _ { i } } { 1 - v _ { i } } - v _ { i } \otimes \frac { 1 - v _ { i } } { u _ { i } } \otimes \frac { v _ { i } } { w _ { i } } - u _ { i } \otimes \frac { 1 - u _ { i } } { v _ { i } } \otimes \frac { v _ { i } } { w _ { i } } .
$$

The full transcendentality-three part can be given as

$$
\begin{array} { r l r } & { \left. { R _ { i } ^ { ( 2 ) } } \right) _ { X X Y } ^ { X Y } \right. _ { 3 } = \left[ \mathrm { L i } _ { 3 } \left( - \frac { u _ { i } } { w _ { i } } \right) - \log \left( u _ { i } \right) \mathrm { L i } _ { 2 } \left( \frac { v _ { i } } { 1 - u _ { i } } \right) + \displaystyle { \frac { 1 } { 2 } } \log \left( 1 - u _ { i } \right) \log \left( u _ { i } \right) \log \left( \frac { w _ { i } ^ { 2 } } { 1 - u _ { i } } \right) \right. } \\ & { \left. \phantom { \left( \frac { 1 } { 2 } \right) } - \displaystyle { \frac { 1 } { 2 } } \mathrm { L i } _ { 3 } \left( - \frac { u _ { i } v _ { i } } { w _ { i } } \right) - \frac { 1 } { 2 } \log \left( u _ { i } \right) \log \left( v _ { i } \right) \log \left( w _ { i } \right) - \displaystyle { \frac { 1 } { 1 2 } } \log ^ { 3 } \left( w _ { i } \right) + \left( u _ { i } \left. v _ { i } \right) \right] } \\ & { - \mathrm { L i } _ { 3 } \left( 1 - v _ { i } \right) + \mathrm { L i } _ { 3 } \left( u _ { i } \right) - \displaystyle { \frac { 1 } { 2 } } \log ^ { 2 } \left( v _ { i } \right) \log \left( \displaystyle { \frac { 1 - v _ { i } } { u _ { i } } } \right) + \displaystyle { \frac { 1 } { 6 } } \pi ^ { 2 } \log \left( \frac { v _ { i } } { w _ { i } } \right) } & \\ & { - \displaystyle { \frac { 1 } { 6 } } \pi ^ { 2 } \log \left( - s _ { i i + 1 i + 2 } \right) . } & { \left( 3 . 2 2 \right) } \end{array}
$$

Together with the terms of lower transcendentality,we have

$$
\begin{array} { l } { { ( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y } = ( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y X } \displaystyle \Big \vert _ { 3 } + \mathrm { L i } _ { 2 } \left( 1 - u _ { i } \right) + \mathrm { L i } _ { 2 } \left( 1 - v _ { i } \right) ~ } } \\ { { \displaystyle ~ + \log \left( u _ { i } \right) \log \left( v _ { i } \right) - \frac { 1 } { 2 } \log \left( - s _ { i + 1 i + 2 } \right) \log \left( \displaystyle \frac { u _ { i } } { v _ { i } } \right) + 2 \log \left( - s _ { i i + 1 } \right) + \displaystyle \frac { \pi ^ { 2 } } { 3 } - 7 . } } \end{array}
$$

Thefinalmaeresity)ofdsetiti ing from two to zero. It reads

$$
\begin{array} { c } { { ( R _ { i } ^ { ( 2 ) } ) _ { x x x } ^ { x x } = \displaystyle \frac { 1 } { 2 } \log \left( - s _ { i + 1 i + 2 } \right) \log \left( \displaystyle \frac { u _ { i } } { v _ { i } } \right) - \mathrm { L i } _ { 2 } \left( 1 - u _ { i } \right) - \log \left( u _ { i } \right) \log \left( v _ { i } \right) + \displaystyle \frac { 1 } { 2 } \log ^ { 2 } \left( v _ { i } \right) } } \\ { { + \log \left( - s _ { i + 1 i + 2 } \right) - 2 \log \left( - s _ { i i + 1 } \right) + \displaystyle \frac { 7 } { 2 } . } } \end{array}
$$

Let us emphasise that, if non-vanishing, the transcendentality-four contribution is the same for al remainder function densities. Furthermore, there is only one transcendentalitythree function and two functions of transcendentality smaller or equal to two that contribute to the results in the SU(2) sector. Notably, the highest degree of transcendentality $t = 4 - s$ （204号 is directly related to the shuffling number $s$ of the respective remainder density, i.e. to the number indicating by how many legs the field favours are shuffed. For instance, $( R _ { i } ^ { ( 2 ) } ) _ { X X Y } ^ { X Y X }$ （2 has shuffling number $s = 1$ and maximal transcendentality degree $t = 3$ ：

Interestingly, the rational pieces of the remainder function are connected to the dilatation operator as

$$
{ \mathfrak { D } } _ { i i + 1 i + 2 } ^ { ( 2 ) } = - { \frac { 4 } { 7 } } R _ { i i + 1 i + 2 } ^ { ( 2 ) } \Big | _ { 0 } .
$$

# 4 Conclusion and outlook

In this paper, we have calculated the two-loop minimal form factor for all operators in the SU(2） sector of planar $\mathcal { N } = 4$ SYM theory via the on-shell method of unitarity. Moreover, we have extracted the corresponding two-loop remainder function and the two-loop dilatation operator from it. The results of this paper provide a solid stepping stone towards calculating the complete two-loop dilatation operator of ${ \mathcal N } = 4$ SYM theory. The employed method, however, is independent of the high symmetry of planar $\mathcal { N } = 4$ SYM theory, in particular of its integrability, and it is thus also applicable to less symmetric theories.

The SU(2) sector is the simplest closed sector of the theory whose operators do not renormalise diagonally. It is hence well suited to study the occurrence of operator mixing and the dilatation operator. Due to the on-shell nature of the external fields, the divergences of the form factors are a combination of UV and IR divergences. We have disentangled the UV divergences from the IR divergences using the BDS ansatz and the universality of the latter. Because of the operator mixing, we needed to promote the interactions to operators and the iterative structure of the BDS ansatz to an operatorial form as well. From the UV divergences, we have determined the renormalisation constants and the dilatation operator.

In contrast to the BPS case, the two-loop remainders of non-protected operators in the SU(2) sector do not exhibit maximal uniform transcendentality. However, their maximally transcendental part coincides with the remainder of the BPS vacuum computed in [14]. These results and further evidence in other sectors lead us to conjecture that the twoloop remainder of every minimal form factor has the same degree-four part as the BPS one. Moreover, the two-loop remainder of the three-point form factor of every length-two operator should agree with the corresponding BPS remainder found in [8]. It would be interesting to check our conjecture about this universality for a wider class of operators, or even to prove it.15

Another observation is that the maximal transcendentality of the various remainders is related to their shuffling number,i.e. to the number indicating by how many places the field flavours are shufled. It would be interesting to explore this pattern in larger sectors and at higher loops,where more complicated interactions contribute.

Soft or collinear limits of scattering amplitudes or form factors are typically given by lower-point amplitudes or form factors multiplied by a universal function. Thus, they provide important constraints and sometimes even allow to bootstrap the full function under consideration. As already observed in [14] for the BPS case, soft and colinear limits of minimal form factors also do not vanish for the cases considered here. This may be surprising since a priori there is no physical interpretation for this limit because these form factors correspond to the minimal physical configuration. Actually, similar questions also appear at the amplitude level. For example,taking certain soft or colinear limits of the sixscalar amplitudes given in appendix A does not generate any physical amplitude, though the limit is non-zero. Via unitarity cuts, this consideration on the level of amplitudes affects the limits of minimal form factors. It would be interesting to understand this point better,and to see if one can obtain the soft or collinear limit without computing the full quantity.

We have seen that the two-loop form factors, as well as the remainder functions and dilatation operator derived from them, obey Ward identities induced by the underlying R-symmetry. Going beyond the SU(2) sector, the realisation of similar Ward identities following from other symmetries should be more involved due to corrections to the generators which are absent for SU(2), cf. examples of such corrections in the case of spin chains [66] or scattering amplitudes [58, 67]. Capturing these extensions in the case of form factors is currently under investigation.

# Acknowledgements

It is a pleasure to thank Andreas Brandhuber, Burkhard Eden, Jan Fokken, Gregory Korchemsky, Brenda Penante, Gabriele Travaglini and Christian Vergu for useful discussions.

FL would like to thank Simon Caron-Huot for initial collaboration on a related project and for useful discussions. We thank the Marie Curie network GATIS (gatis.desy.eu) of the European Union's Seventh Framework Programme FP7/2007-2013/ under REA Grant Agreement No 317089 for support. MW dankt der Studienstiftung des deutschen Volkes fir ein Promotionsforderstipendium. DN and GY are supported by a DFG grant in the framework of the SFB 647 “Raum-Zeit-Materie. Analytische und Geometrische Strukturen".

# A Six-point scalar amplitudes

In this appendix,we provide all six-point amplitudes that are required in the unitarity computation of the two-loop form factors in the SU(2) sector. We use the short notation

$$
( A ^ { ( 0 ) } ) _ { z _ { 6 } z _ { 5 } z _ { 4 } } ^ { z _ { 1 } z _ { 2 } z _ { 3 } } = A ^ { ( 0 ) } ( 1 ^ { z _ { 1 } } , 2 ^ { z _ { 2 } } , 3 ^ { z _ { 3 } } , 4 ^ { \bar { z } _ { 4 } } , 5 ^ { \bar { z } _ { 5 } } , 6 ^ { \bar { z } _ { 6 } } ) \big | _ { \eta _ { i } ^ { A } = 1 } ,
$$

where,on the right-hand side, all momenta are taken to be outgoing and we have set all Ni variables to 1.

The required amplitudes can be explicitly given in terms of Mandelstam variables as

$$
\begin{array} { r l } { \| A ^ { \mu } \| _ { \infty } ^ { 2 } \mathrm { S e c } } & { = } & { \frac { 1 } { \mu _ { 0 } } , } \\ { \| A ^ { \mu } \| _ { \infty } ^ { 3 } \| _ { \infty } ^ { 2 } = } & { \frac { 1 } { \mu _ { 0 } } , } \\ { \| A ^ { \mu } \| _ { \infty } ^ { 3 } \| _ { \infty } ^ { 2 } = } & { \frac { 1 } { \mu _ { 0 } } , } \\ { \| A ^ { \mu } \| _ { \infty } ^ { 3 } \| _ { \infty } ^ { 2 } = } & { \frac { 1 } { \mu _ { 0 } } , } \\ { \| A ^ { \mu } \| _ { \infty } ^ { 3 } \| _ { \infty } ^ { 2 } = } & { \frac { \sqrt { 3 } \mu _ { 0 } ^ { 3 } } { \mu _ { 0 } } - \frac { 3 } { \mu _ { 0 } } \frac { \sqrt { 3 } \mu _ { 0 } ^ { 3 } } { \mu _ { 0 } } - \frac { 3 } { \mu _ { 0 } } \frac { \sqrt { 3 } \mu _ { 0 } ^ { 3 } } { \mu _ { 0 } } , } \\ { \| A ^ { \mu } \| _ { \infty } ^ { 3 } \| _ { \infty } ^ { 2 } = } & { \frac { 1 } { \sqrt { 3 } \mu _ { 0 } } , } \\ { \| A ^ { \mu } \| _ { \infty } ^ { 3 } \| _ { \infty } ^ { 4 } = } & { \frac { 1 } { \sqrt { 3 } \mu _ { 0 } } , } \\ { \| A ^ { \mu } \| _ { \infty } ^ { 3 } \| _ { \infty } ^ { 4 } = } & { \frac { 1 } { \sqrt { 3 } \mu _ { 0 } } - \frac { 3 } { \mu _ { 0 } } \frac { \sqrt { 3 } \mu _ { 0 } ^ { 3 } } { \mu _ { 0 } } - \frac { 3 } { \mu _ { 0 } } \frac { \sqrt { 3 } \mu _ { 0 } ^ { 3 } } { \mu _ { 0 } } , } \\ { \| A ^ { \mu } \| _ { \infty } ^ { 4 } \| _ { \infty } ^ { 2 } = } & { \frac { 1 } { \sqrt { 3 } \mu _ { 0 } } , } \\ { \| A ^ { \mu } \| _ { \infty } ^ { 3 } \| _ { \infty } ^ { 2 } = } &  \frac { 1 } { \sqrt { 3 } \mu _ { 0 } ^ { 3 } } \\ { \| A ^ { \mu } \| _ { \infty } ^ { 4 } = } &  \frac { 3 } { \sqrt { 3 } \mu _ { 0 } ^ { 3 } } \left( \frac { 1 } { \sqrt { 3 } \mu _ { 0 } ^ { 3 } } - \frac { 3 } { \sqrt { 3 } \mu _ { 0 } ^ { 3 } } + \frac { 1 } { \sqrt { 3 } \mu _ { 0 } ^ { 3 } } \right. \end{array}
$$

where all poles are physical.16 Through the triple cut shown in fgure 2d, each term in (A.2) is exactly mapped to one graph in table 3.

It is easy to find various relations among these amplitudes, such as

$$
\begin{array} { r l } & { ( A ^ { ( 0 ) } ) _ { X X Y } ^ { Y X X } + ( A ^ { ( 0 ) } ) _ { X X Y } ^ { X Y X } + ( A ^ { ( 0 ) } ) _ { X X Y } ^ { X X Y } = - ( A ^ { ( 0 ) } ) _ { X X X } ^ { X X X } , } \\ & { ( A ^ { ( 0 ) } ) _ { X Y X } ^ { X Y X } + ( A ^ { ( 0 ) } ) _ { X Y X } ^ { Y X X } + ( A ^ { ( 0 ) } ) _ { X Y X } ^ { X X Y } = - ( A ^ { ( 0 ) } ) _ { X X X } ^ { X X X } , } \\ & { ( A ^ { ( 0 ) } ) _ { X X Y } ^ { X Y X } + ( A ^ { ( 0 ) } ) _ { X X Y } ^ { Y X X } = ( A ^ { ( 0 ) } ) _ { X Y X } ^ { X X Y } + ( A ^ { ( 0 ) } ) _ { Y X X } ^ { X X Y } . } \end{array}
$$

These are the counterparts of (2.35） and nothing but supersymmetric Ward identities (SWI) for amplitudes [68].17

# References

[1] W.van Neerven,“Infrared Behavior of On-shell Form-factors in a ${ \mathcal N } = 4$ Supersymmetric Yang-Mills Field Theory,” Z.Phys. C30(1986) 595.   
[2] A.Brandhuber,B. Spence,G. Travaglini,and G. Yang,“Form Factors in ${ \mathcal N } = 4$ Super Yang-Mills and Periodic Wilson Loops,” JHEP 1101 (2011) 134, arXiv:1011.1899 [hep-th].   
[3] L.Bork,D.Kazakov,and G.Vartanov,“On form factors in ${ \mathcal N } = 4$ SYM," JHEP 1102 (2011) 063,arXiv:1011.2440 [hep-th].   
[4] A. Brandhuber, O. Gurdogan, R. Mooney, G. Travaglini,and G. Yang,“Harmony of Super Form Factors,” JHEP 1110 (2011) 046,arXiv:1107.5067 [hep-th].   
[5] L. Bork, D. Kazakov, and G. Vartanov,“On MHV Form Factors in Superspace for ${ \mathcal N } = 4$ （ SYM Theory,” JHEP1110 (2011) 133, arXiv:1107.5551 [hep-th].   
[6] J. M. Henn, S. Moch,and S.G. Naculich,“Form factors and scattering amplitudes in ${ \mathcal { N } } = 4$ SYM in dimensional and massive regularizations,” JHEP 1112 (2011) 024, arXiv:1109.5057 [hep-th].   
[7] T.Gehrmann,J.M.Henn,and T.Huber,“The three-loop form factor in ${ \mathcal N } = 4$ super Yang-Mills,” JHEP 1203 (2012) 101, arXiv:1112.4524 [hep-th].   
[8] A.Brandhuber,G. Travaglini,and G. Yang,“Analytic two-loop form factors in ${ \mathcal N } = 4$ （204号 SYM,” JHEP 1205 (2012) 082,arXiv:1201.4170 [hep-th].   
[9] L. Bork,“On NMHV form factors in ${ \mathcal N } = 4$ SYM theory from generalized unitarity," JHEP 1301 (2013) 049,arXiv:1203.2596 [hep-th].   
[10] O.T. Engelund and R. Roiban,“Correlation functions of local composite operators from generalized unitarity,” JHEP 1303 (2013) 172,arXiv:1209.0227 [hep-th].   
[11] H. Johansson, D. A. Kosower,and K. J. Larsen,“Two-Loop Maximal Unitarity with External Masses,” Phys.Rev. D87 (2013) 025030, arXiv:1208.1754 [hep-th].   
[12] R. H. Boels, B.A. Kniehl, O. V. Tarasov,and G. Yang,“Color-kinematic Duality for Form Factors,” JHEP 1302(2013) 063,arXiv:1211.7028 [hep-th].   
[13] B.Penante, B. Spence, G. Travaglini,and C.Wen,“On super form factors of half-BPS operators in ${ \mathcal N } = 4$ super Yang-Mills,” JHEP 1404 (2014) 083, arXiv:1402.1300 [hep-th].   
[14] A. Brandhuber,B.Penante, G. Travaglini, and C.Wen,“The last of the simple remainders,” JHEP 1408(2014) 100,arXiv:1406.1443 [hep-th].   
[15] L.Bork,“On form factors in ${ \mathcal N } = 4$ SYM theory and polytopes,” JHEP 1412 (2014) 111, arXiv:1407.5568 [hep-th].   
[16] M.Wilhelm,“Amplitudes,Form Factors and the Dilatation Operator in ${ \mathcal N } = 4$ SYM Theory,” JHEP1502 (2015) 149,arXiv:1410.6309 [hep-th].   
[17] D. Nandan, C. Sieg, M. Wilhelm,and G. Yang,“Cutting through form factors and cross sections of non-protected operators in ${ \mathcal { N } } = 4$ SYM,” JHEP 06 (2015) 156, arXiv:1410.8485 [hep-th].   
[18] L. F. Alday and J. Maldacena,“Comments on gluon scattering amplitudes via AdS/CFT,” JHEP0711 (2007) 068,arXiv:0710.1060 [hep-th].   
[19] J. Maldacena and A. Zhiboedov,“Form factors at strong coupling via a Y-system,” JHEP 1011 (2010) 104,arXiv:1009.1139 [hep-th].   
[20] Z.Gao and G. Yang,“Y-system for form factors at strong coupling in $A d S _ { 5 }$ and with multi-operator insertions in $A d S _ { 3 }$ ,” JHEP 1306 (2013) 105,arXiv:1303.2668 [hep-th].   
[21] N. Beisert,“The complete one-loop dilatation operator of ${ \mathcal N } = 4$ superYang-Mills theory,” Nucl.Phys. B676 (2004) 3-42, arXiv:hep-th/0307015 [hep-th].   
[22] B.I. Zwiebel,“From Scattering Amplitudes to the Dilatation Generator in ${ \mathcal N } = 4$ SYM," J.Phys. A45 (2012) 115401, arXiv:1111.0083 [hep-th].   
[23] Z. Bern, L. J. Dixon, D. C. Dunbar,and D. A. Kosower,“One-loop $n$ -point gauge theory amplitudes,unitarity and collinear limits,” Nucl.Phys. B425 (1994) 217-260, arXiv:hep-ph/9403226 [hep-ph].   
[24] Z. Bern, L. J. Dixon, D. C. Dunbar, and D. A. Kosower,“Fusing gauge theory tree amplitudes into loop amplitudes,” Nucl.Phys. B435 (1995) 59-101, arXiv:hep-ph/9409265 [hep-ph].   
[25] R.Britto,F. Cachazo,and B.Feng,“Generalized unitarity and one-loop amplitudes in ${ \mathcal N } = 4$ （204号 super-Yang-Mills,” Nucl.Phys. B725 (2005) 275-305, arXiv:hep-th/0412103 [hep-th].   
[26] A. Brandhuber, B. Penante, G. Travaglini,and D. Young,“Integrability and unitarity,” JHEP05 (2015) 005,arXiv:1502.06627 [hep-th].   
[27] O.T. Engelund, “Lagrangian Insertion in the Light-Like Limit and the Super-Correlators/Super-Amplitudes Duality,” arXiv: 1502.01934 [hep-th].   
[28] L. Koster, V. Mitev,and M. Staudacher,“A Twistorial Approach to Integrability in ${ \mathcal { N } } = 4$ SYM,” Fortsch.Phys. 63 no. 2, (2015) 142-147, arXiv:1410.6310 [hep-th]   
[29] D.Chicherin,R. Doobary, B. Eden,P. Heslop,G.P. Korchemsky, L. Mason,and E. Sokatchev,“Correlation functions of the chiral stress-tensor multiplet in ${ \mathcal N } = 4$ SYM," JHEP06 (2015) 198,arXiv:1412.8718 [hep-th].   
[30] A. Brandhuber,B. Penante, G. Travaglini, and D. Young,“Integrability and MHV diagrams in ${ \mathcal N } = 4$ supersymmetric Yang-Mills theory,” Phys.Rev.Lett. 114 (2015) 071602, arXiv:1412.1019 [hep-th].   
[31] N. Beisert et al., “Review of AdS/CFT Integrability: An Overview,” Lett.Math.Phys.99 (2012) 3-32, arXiv:1012.3982 [hep-th].   
[32] J. Minahan and K. Zarembo,“The Bethe ansatz for ${ \mathcal { N } } = 4$ superYang-Mills,” JHEP 0303 (2003)013, arXiv:hep-th/0212208 [hep-th].   
[33] N. Beisert, C. Kristjansen, and M. Staudacher,“The Dilatation operator of conformal ${ \mathcal N } = 4$ superYang-Mills theory,” Nucl.Phys. B664 (2003) 131-184, arXiv:hep-th/0303060 [hep-th].   
[34] C. Sieg,“Superspace computation of the three-loop dilatation operator of ${ \mathcal { N } } = 4$ SYM theory,” Phys.Rev. D84 (2011) 045014, arXiv:1008.3351 [hep-th].   
[35] T. Bargheer, N. Beisert, and F. Loebbert,“Boosting Nearest-Neighbour to Long-Range Integrable Spin Chains,” J.Stat.Mech. 0811 (2008) L11001, arXiv:0807.5081 [hep-th].   
[36] T.Bargheer, N. Beisert, and F.Loebbert,“Long-Range Deformations for Integrable Spin Chains,” J.Phys.A42 (2009) 285205,arXiv:0902.0956 [hep-th].   
[37] A.H. Mueller,“On the Asymptotic Behavior of the Sudakov Form-factor,” Phys.Rev. D20 (1979) 2037.   
[38] J.C.Collins,“Algorithm to Compute Corrections to the Sudakov Form-factor,” Phys.Rev. D22 (1980) 1478.   
[39] A. Sen,“Asymptotic Behavior of the Sudakov Form-Factor in QCD,” Phys.Rev. D24 (1981) 3281.   
[40] L.Magnea and G. F. Sterman,“Analytic continuation of the Sudakov form-factor in QCD,” Phys.Rev. D42 (1990) 4222-4227.   
[41] C. Anastasiou, Z. Bern, L. J. Dixon, and D. Kosower,“Planar amplitudes in maximally supersymmetric Yang-Mills theory,” Phys.Rev.Lett. 91 (2003) 251602, arXiv:hep-th/0309040 [hep-th].   
[42] Z. Bern,L.J. Dixon,and V. A. Smirnov,“Iteration of planar amplitudes in maximally supersymmetric Yang-Mills theory at three loops and beyond,” Phys.Rev. D72 (2005) 085001, arXiv:hep-th/0505205 [hep-th].   
[43] S.Catani,“The Singular behavior of QCD amplitudes at two loop order,” Phys.Lett. B427 (1998) 161-171, arXiv:hep-ph/9802439 [hep-ph].   
[44] G. F. Sterman and M. E. Tejeda-Yeomans,“Multiloop amplitudes and resummation," Phys.Lett. B552 (2003) 48-56, arXiv:hep-ph/0210130 [hep-ph].   
[45] J. Bartels,L. Lipatov,and A. Sabio Vera, “BFKL Pomeron, Reggeized gluons and Bern-Dixon-Smirnov amplitudes,” Phys.Reu. D80 (2009) 045002, arXiv:0802.2065 [hep-th].   
[46] Z. Bern, L. Dixon, D. Kosower, R. Roiban,M. Spradlin, C. Vergu, and A. Volovich,“The Two-Loop Six-Gluon MHV Amplitude in Maximally Supersymmetric Yang-Mills Theory," Phys.Rev. D78 (2008) 045007, arXiv:0803.1465 [hep-th].   
[47] J.Drummond, J. Henn, G. Korchemsky,and E. Sokatchev,“Hexagon Wilson loop = six-gluon MHV amplitude,” Nucl.Phys. B815 (2009) 142-173, arXiv:0803.1466 [hep-th].   
[48] S. Caron-Huot and K. J. Larsen，“Uniqueness of two-loop master contours,” JHEP 1210 (2012) 026,arXiv:1205.0801 [hep-ph].   
[49] N.Arkani-Hamed,J.L. Bourjaily, F. Cachazo,A. B.Goncharov,A. Postnikov,and J. Trnka, "Scattering Amplitudes and the Positive Grassmannian,” arXiv:1212.5605 [hep-th].   
[50] D. Nandan, M. F.Paulos, M. Spradlin, and A. Volovich,“Star Integrals, Convolutions and Simplices,” JHEP 1305 (2013) 105,arXiv:1301.2500 [hep-th].   
[51] A. Kotikov and L. Lipatov,“DGLAP and BFKL evolution equations in the ${ \mathcal N } = 4$ （204号 supersymmetric gauge theory,” arXiv:hep-ph/0112346 [hep-ph].   
[52] A. Kotikov,L. Lipatov,A. Onishchenko,and V. Velizhanin,“Three loop universal anomalous dimension of the Wilson operators in ${ \mathcal N } = 4$ SUSY Yang-Mills model," Phys.Lett. B595 (2004) 521-529, arXiv:hep-th/0404092 [hep-th].   
[53] A.Kotikov and L.Lipatov,“On the highest transcendentality in ${ \mathcal N } = 4$ SUSY," Nucl.Phys. B769 (2007) 217-255,arXiv:hep-th/0611204 [hep-th].   
[54] Y.Li, A. von Manteuffel, R. M. Schabinger,and H. X. Zhu,“Soft-virtual corrections to Higgs production at N $^ { \cdot 3 }$ LO,” Phys.Rev. D91 no.3, (2015) 036008, arXiv:1412.2771 [hep-ph].   
[55] T. Gehrmann, M. Jaquier, E. Glover,and A. Koukoutsakis,“Two-Loop QCD Corrections to the Helicity Amplitudes for $H  3$ partons,” JHEP 1202 (2012) 056, arXiv:1112.3554 [hep-ph].   
[56] A.Belitsky, S. Hohenegger,G. Korchemsky, E. Sokatchev,and A. Zhiboedov, “Energy-Energy Correlations in ${ \mathcal N } = 4$ Supersymmetric Yang-Mills Theory," Phys.Rev.Lett.112 no. 7, (2014) 071601, arXiv:1311.6800 [hep-th].   
[57] V. Nair,“A Current Algebra for Some Gauge Theory Amplitudes," Phys.Lett. B214 (1988) 215.   
[58] T.Bargheer,N. Beisert,W.Galeas,F.Loebbert,and T.McLoughlin,“Exacting ${ \mathcal N } = 4$ （204号 Superconformal Symmetry,” JHEP 0911 (2009) 056, arXiv:0905.3738 [hep-th].   
[59] V.A. Smirnov,“Evaluating Feynman integrals,” Springer Tracts Mod.Phys. 211 (2004) 1-244.   
[60] R. N.Lee,“LiteRed 1.4: a powerful tool for reduction of multiloop integrals,” J.Phys.Conf.Ser. 523 (2014) 012059, arXiv:1310.1145 [hep-ph].   
[61] T. Gehrmann and E.Remiddi,“Two loop master integrals for $\gamma ^ { * } \longrightarrow 3$ jets: The Planar topologies,” Nucl.Phys. B601 (2001) 248-286, arXiv:hep-ph/0008287 [hep-ph].   
[62] A. B. Goncharov,“A simple construction of Grassmannian polylogarithms,” arXiv:0908.2238 [math.AG].   
[63] A. B. Goncharov, M. Spradlin, C. Vergu, and A. Volovich,“Classical Polylogarithms for Amplitudes and Wilson Loops,” Phys.Rev.Lett. 105 (2010) 151605, arXiv:1006.5703 [hep-th].   
[64] C.Vergu,“Lecture Notes for the Mathematica Summer School on Theoretical Physics.” http://msstp.org/sites/default/files/Demo.nb, 2011.   
[65] Z. Bern and D.A. Kosower,“The Computation of loop amplitudes in gauge theories,” Nucl.Phys. B379 (1992) 451-561.   
[66] N. Beisert,“The su(2|3) dynamic spin chain,” Nucl.Phys.B682 (2004) 487-520, arXiv:hep-th/0310252 [hep-th].   
[67] N. Beisert,J. Henn, T. McLoughlin,and J. Plefka,“One-Loop Superconformal and Yangian Symmetries of Scattering Amplitudes in ${ \mathcal N } = 4$ Super Yang-Mills,” JHEP 1004 (2010) 085, arXiv:1002.1733 [hep-th].   
[68] M. T.Grisaru, H. Pendleton,and P.van Nieuwenhuizen,“Supergravity and the S Matrix,” Phys.Rev. D15 (1977) 996.