# Note on asymptotic symmetries and soft gluon theorems

Pujian Mao\* $\mathrm { a }$ and Jun-Bao Wut b,c,d

（204号 $\mathbf { a }$ Institute of High Energy Physics and Theoretical Physics Center for Science Facilities, Chinese Academy of Sciences, 19B Yuquan Road, Beijing 100049, P. R. China bSchool of Science, Tianjin University, 92 Weijin Road, Tianjin 30oo72, P. R. China cSchool of Physics and Nuclear Energy Engineering, Beihang University, 37 Xueyuan Road, Beijing 100191, P.R. China （20 $\mathrm { d }$ Center for High Energy Physics, Peking University, 5 Yiheyuan Road, Beijing 100871, P. R. China

# Abstract

Recently, the leading soft gluon theorem with single soft emission was shown to be the Ward identity of a two dimensional $\mathcal { G }$ -Kac-Moody symmetry. In this note,we show that the leading soft gluon theorem can be interpreted as the Ward identity for the asymptotic symmetries of non-Abelian gauge theory. We further argue that the sub-leading soft gluon theorem can follow from the same symmetry.

# 1 Introduction

As the most perfect microscopic structures in the universe, scattering amplitudes have been undergoing a revolution in our understanding recently [1]. One of the most remarkable discoveries is the on-shell recursion relation for tree amplitudes [2,3] (also [4] from a different set-up). The perturbative S-matrix of massless excitations of the theory turns out to be much simpler than expected. The S-matrix is an object living at the boundary of space-time, so it is fair to ask whether this simplicity might be somehow connected to the structure of nullinfinity which is accessible to the massless excitations.

Meanwhile, there has been renewed interest in asymptotic symmetries at null infinity. The novel advance is the promotion of the asymptotic symmetries to nontrivial symmetries of the quantum S-matrix [5,6]. The novel symmetries and the on-shell recursion relations converge at the understanding of the scattering of very low-energy massless quanta i.e. soft theorems. On the one hand, the on-shell recursion relations provide a systematical way to derive soft factors at tree level [7-11]. On the other hand, the soft theorems can be interpreted as Ward identities of asymptotic symmetries [12,13] (see also [14-22] for further development).

With such connection in mind, one would expect that the emergence of one side would indicate the other. However, this is not always obvious. In practice, one can first associate certain soft theorem to the Ward identity of some unknown symmetries and then try to understand the nature of the unknown symmetries [23-34]. In YangMills theory, the soft gluon theorem [35] has been connected to the Ward identity of a holomorphic two dimensional $\mathcal { G }$ -Kac-Moody symmetry [27]. This new Kac-Moody symmetry is argued to be related to the asymptotic symmetries derived in [5]. It would be definitely illuminating to show directly that the soft gluon theorem is just the Ward identity for the asymptotic symmetries of non-Abelian gauge theory following closely the line of [12,13]. This is precisely what we will demonstrate in the following pages.

In this note, we study a matter coupled non-Abelian gauge theory. The reason for coupling matter is to have a consistent investigation into both the leading and subleading soft gluon theorem, while the tree-level sub-leading soft factor vanishes in pure Yang-Mills theory [36] under a certain prescription in which one solves the momentum conservation of the hard gluons according to the cyclic order in partial amplitudes (see also a supersymmetric extension [37]). Our results show that the leading soft gluon theorem is nothing but the Ward identity for asymptotic symmetries of the matter coupled non-Abelian gauge theory. We also find that the sub-leading soft gluon theorem can follow from the same asymptotic symmetry responsible for the leading soft gluon theorem in a particular case where we consider only three-point vertices with one gluon coupling to two scalars.

This note is organized as follows. In the next section, we derive the general solutions of non-Abelian gauge theory and define the associated charges. Section 3 is devoted to the connection of the leading soft gluon theorem and asymptotic symmetries. In section 4, we argue that the sub-leading soft gluon theorem can follow the same symmetry in the scattering of $n$ scalars and one single soft gluon. We end this note with some discussions on future directions. There are also two appendixes in which we review the surface charge in non-Abelian gauge theories and the soft gluon theorems.

# 2 4D non-Abelian gauge theory

In this note, we will deal with theory living on the flat Minkowski spacetime in the retarded coordinates

$$
d s ^ { 2 } = \eta _ { \mu \nu } \mathrm { d } x ^ { \mu } \mathrm { d } x ^ { \nu } = - \mathrm { d } u ^ { 2 } - 2 \mathrm { d } u \mathrm { d } r + 2 r ^ { 2 } \gamma _ { z \bar { z } } \mathrm { d } z \mathrm { d } \bar { z } ,
$$

where γzz = $\begin{array} { r } { \gamma _ { z \bar { z } } = \frac { 2 } { ( 1 + z \bar { z } ) ^ { 2 } } } \end{array}$ . This coordinate system will cover only future null infinity ${ \mathcal { T } } ^ { + }$ at （204号 $r  \infty$ . The non-zero components of the Levi-Civita connection are

$$
\Gamma _ { z \bar { z } } ^ { u } = r \gamma _ { z \bar { z } } , ~ \Gamma _ { z \bar { z } } ^ { r } = - r \gamma _ { z \bar { z } } , ~ \Gamma _ { r z } ^ { z } = { \frac { 1 } { r } } , ~ \Gamma _ { z z } ^ { z } = \partial _ { z } \ln \gamma _ { z \bar { z } } .
$$

For simplicity, we consider a non-Abelian gauge theory with only scalar matter. The scalar fields are in the adjoint representation of the gauge group. The Lagrangian of the theory is

$$
\mathcal { L } = \frac { 1 } { 4 } F _ { \mu \nu } ^ { a } F ^ { a \mu \nu } + D _ { \mu } \phi ^ { a } ( D ^ { \mu } \phi ^ { a } ) ^ { \dagger } ,
$$

where the field-strength is defined by

$$
F _ { \mu \nu } ^ { a } = \partial _ { \mu } A _ { \nu } ^ { a } - \partial _ { \nu } A _ { \mu } ^ { a } + i g _ { _ { Y M } } C ^ { a b c } A _ { \mu } ^ { b } A _ { \nu } ^ { c } ,
$$

and $D _ { \mu }$ is the covariant derivative associated to the local group $G$

$$
D _ { \mu } X ^ { a } = \nabla _ { \mu } X ^ { a } + i g _ { { \scriptscriptstyle Y M } } C ^ { a b c } A _ { \mu } ^ { b } X ^ { c } .
$$

The group structure constant $C _ { a b c }$ is totally antisymmetric and satisfies the Jacobi identity:

$$
C ^ { a b c } C ^ { b d e } + C ^ { a b d } C ^ { b e c } + C ^ { a b e } C ^ { b c d } = 0 .
$$

The equations of motion derived from the Lagrangian (3) are

$$
D _ { \mu } F ^ { c \mu \nu } = g _ { _ { Y M } } J ^ { c \nu } , \quad D _ { \mu } D ^ { \mu } \phi ^ { a } = 0 , \quad D _ { \mu } D ^ { \mu } \bar { \phi } ^ { a } = 0 ,
$$

where

$$
J ^ { c \nu } = i C ^ { a b c } ( \phi ^ { a } D ^ { \nu } \bar { \phi } ^ { b } - \bar { \phi } ^ { b } D ^ { \nu } \phi ^ { a } ) .
$$

The Lagrangian of the theory is invariant up to the total derivative under the gauge transformation

$$
\delta _ { \varepsilon } A _ { \mu } ^ { a } = D _ { \mu } \varepsilon ^ { a } , \quad \delta _ { \varepsilon } \phi ^ { a } = i g _ { _ { Y M } } C ^ { a b c } \phi ^ { b } \varepsilon ^ { c } .
$$

# Asymptotic symmetries

The asymptotic symmetry of 4 dimensional Yang-Mills theory was discovered recently in [5] (see also [27,38]). We will derive the asymptotic symmetries of non-Abelian gauge theory with adaption to our conventions. The radial gauge

$$
A _ { r } ^ { a } = 0 ,
$$

will be applied. The boundary condition of the rest components of the gauge fields is set to ensure the radiation flux is finite asymptotically:

$$
A _ { u } ^ { a } = { \cal O } ( r ^ { - 1 } ) , \quad A _ { z ( \bar { z } ) } ^ { a } = { \cal O } ( 1 ) , \quad \phi ^ { a } = { \cal O } ( r ^ { - 1 } ) , \quad \bar { \phi } ^ { a } = { \cal O } ( r ^ { - 1 } ) .
$$

The conditions (1O) and (11) yield the residual gauge transformation parameter $\varepsilon ^ { a } ( z , { \bar { z } } )$ One can further check the symmetry algebra

$$
[ \delta _ { \varepsilon _ { 1 } } , \delta _ { \varepsilon _ { 2 } } ] A _ { \mu } ^ { a } = \delta _ { [ \varepsilon _ { 1 } , \varepsilon _ { 2 } ] } A _ { \mu } ^ { a } , \quad [ \delta _ { \varepsilon _ { 1 } } , \delta _ { \varepsilon _ { 2 } } ] \phi ^ { a } = \delta _ { [ \varepsilon _ { 1 } , \varepsilon _ { 2 } ] } \phi ^ { a } .
$$

# Asymptotic conserved charges

The definition of charge in Yang-Mills theory is quite subtle in contrast with the Abelian case i.e. Maxwell theory. The reason is that the field-strength is covariant under gauge transformation in a non-Abelian theory. However this issue was fixed in Yang-Mills theory asymptotically by Abbott and Deser [39] (see also [40] for a comprehensive analysis). We compute the asymptotic conserved charge for scalar matter coupled theory (3) in Appendix A using the cohomological techniques 40,41]. The charge is given by

$$
{ \mathcal { Q } } _ { \varepsilon } = - \int \mathrm { d } z \mathrm { d } \bar { z } r ^ { 2 } \gamma _ { z \bar { z } } \varepsilon ^ { a } F ^ { a u r } .
$$

# Solution space

In analogy with the charge associated to global symmetry, the charge (13) is conserved on-shell asymptotically. Thus solving the equations of motion (7) in series expansion around ${ \mathcal { T } } ^ { + }$ is necessary for further investigation. As a gauge theory, not all the equations of motion are independent. They are connected off-shell by the Noether identityl

$$
D _ { \nu } \left[ D _ { \mu } F ^ { c \mu \nu } - g _ { _ { Y M } } J ^ { c \nu } \right] = i g _ { _ { Y M } } C ^ { a b c } \left[ \bar { \phi } ^ { b } D _ { \mu } D ^ { \mu } \phi ^ { a } - \phi ^ { a } D _ { \mu } D ^ { \mu } \bar { \phi } ^ { b } \right] .
$$

It will be very helpful to arrange (7) into

hypersurface equations:

$$
D _ { \mu } F ^ { a \mu u } = g _ { { } _ { Y M } } J ^ { a u } ,
$$

standard equations:

$$
D _ { \mu } F ^ { a \mu z } = g _ { _ { Y M } } J ^ { a z } , \quad D _ { \mu } F ^ { a \mu \bar { z } } = g _ { _ { Y M } } J ^ { a \bar { z } } , \quad D _ { \mu } D ^ { \mu } \phi ^ { a } = 0 , \quad D _ { \mu } D ^ { \mu } \bar { \phi } ^ { a } = 0 ,
$$

supplementary equations:

$$
D _ { \mu } F ^ { a \mu r } = g _ { { } _ { Y M } } J ^ { a r } .
$$

The advantage of such an arrangement is that (14) will be reduced to

$$
\partial _ { r } \left[ \sqrt { - g } \Big ( D _ { \mu } F ^ { a \mu r } - g _ { { } _ { Y M } } J ^ { a r } \Big ) \right] = 0 ,
$$

when the hypersurface equations and the standard equations are satisfied. Hence, one just needs to solve

$$
\sqrt { - g } ( D _ { \mu } F ^ { a \mu r } - g _ { { } _ { Y M } } J ^ { a r } ) = 0
$$

at order $\mathcal { O } ( r ^ { 0 } )$ and all the other orders (in $\textstyle { \frac { 1 } { r } }$ ） will be zero automatically. That is the reason why they are called supplementary equations.

We start to solve the equations of motion (7) with the hypersurface equations （204 $D _ { \mu } F ^ { a \mu u } = g _ { { \scriptscriptstyle Y M } } J ^ { a u }$ , from which one can solve out

$$
\begin{array} { l } { { \displaystyle { 4 _ { u } ^ { a } = \frac { A _ { u } ^ { a ( 0 ) } ( u , z , \bar { z } ) } { r } + \gamma _ { z \bar { z } } ^ { - 1 } \int _ { r } ^ { \infty } \frac { \mathrm { d } r ^ { \prime } } { r ^ { \prime 2 } } \int _ { r ^ { \prime } } ^ { \infty } \mathrm { d } r ^ { \prime \prime } \Bigl [ \partial _ { z } \partial _ { r ^ { \prime \prime } } A _ { \bar { z } } ^ { a } + \partial _ { \bar { z } } \partial _ { r ^ { \prime \prime } } A _ { z } ^ { a } } } } \\  { \displaystyle { \phantom { \frac { } { } } + i g _ { _ { Y M } } C ^ { a b c } \Bigl ( A _ { z } ^ { b } \partial _ { r ^ { \prime \prime } } A _ { \bar { z } } ^ { c } + A _ { \bar { z } } ^ { b } \partial _ { r ^ { \prime \prime } } A _ { z } ^ { c } + r ^ { \prime \prime 2 } \gamma _ { z \bar { z } } \phi ^ { b } \partial _ { r ^ { \prime \prime } } \bar { \phi } ^ { c } - r ^ { \prime \prime 2 } \gamma _ { z \bar { z } } \bar { \phi } ^ { c } \partial _ { r ^ { \prime \prime } } \phi ^ { b } \Bigr ) \Bigr ] , } } \end{array}
$$

where $A _ { u } ^ { a ( 0 ) } ( u , z , \bar { z } )$ are integration constants. Suppose that $A _ { z } ^ { a }$ ， $A _ { \bar { z } } ^ { a }$ ， $\phi ^ { a }$ ，and $\phi ^ { a }$ are given as initial data:

$$
\begin{array} { c c } { { \displaystyle { A _ { z } ^ { a } = \sum _ { m = 0 } ^ { \infty } \frac { A _ { z } ^ { a ( m ) } ( u _ { 0 } , z , \bar { z } ) } { r ^ { m } } } , } } & { { \displaystyle { A _ { \bar { z } } ^ { a } = \sum _ { m = 0 } ^ { \infty } \frac { A _ { \bar { z } } ^ { a ( m ) } ( u _ { 0 } , z , \bar { z } ) } { r ^ { m } } } , } } \\ { { \displaystyle { \phi ^ { a } = \sum _ { m = 0 } ^ { \infty } \frac { \phi ^ { a ( m ) } ( u _ { 0 } , z , \bar { z } ) } { r ^ { m + 1 } } } , } } & { { \displaystyle { \bar { \phi } ^ { a } = \sum _ { m = 0 } ^ { \infty } \frac { \bar { \phi } ^ { a ( m ) } ( u _ { 0 } , z , \bar { z } ) } { r ^ { m + 1 } } } . } } \end{array}
$$

$A _ { u } ^ { a }$ are completely fixed up to the integration constants $A _ { u } ^ { a ( 0 ) } ( u , z , \bar { z } )$ . More precisely,

$$
A _ { u } ^ { a } = \frac { A _ { u } ^ { a ( 0 ) } } { r } - \frac { \gamma _ { z \bar { z } } ^ { - 1 } A _ { u } ^ { a ( 1 ) } } { 2 r ^ { 2 } } + \mathcal { O } ( r ^ { - 3 } ) ,
$$

$$
A _ { u } ^ { a ( 1 ) } = \partial _ { z } A _ { \bar { z } } ^ { a ( 1 ) } + \partial _ { \bar { z } } A _ { z } ^ { a ( 1 ) } + i g _ { \gamma _ { M } } C ^ { a b c } \Big ( A _ { z } ^ { b ( 0 ) } A _ { \bar { z } } ^ { c ( 1 ) } - A _ { z } ^ { b ( 1 ) } A _ { \bar { z } } ^ { c ( 0 ) } + \gamma _ { z \bar { z } } \phi ^ { b ( 0 ) } \bar { \phi } ^ { c ( 1 ) } - \gamma _ { z \bar { z } } \phi ^ { b ( 0 ) } \bar { \phi } ^ { c ( 1 ) } \Big ) .
$$

The standard equations will determine the time dependence of $A _ { z } ^ { a ( m ) }$ ， $A _ { \bar { z } } ^ { a ( m ) }$ ， $\phi ^ { a ( m ) }$ ， and $\bar { \phi } ^ { a ( m ) }$ recursively. In particular,

$$
\begin{array} { r l } & { 2 \partial _ { u } { \cal A } _ { z } ^ { a ( 1 ) } = \partial _ { z } { \cal A } _ { u } ^ { a ( 0 ) } + \gamma _ { z \overline { { z } } } ^ { - 1 } \partial _ { z } \Big ( \partial _ { z } { \cal A } _ { \overline { { z } } } ^ { a ( 0 ) } - \partial _ { \overline { { z } } } { \cal A } _ { z } ^ { a ( 0 ) } \Big ) + i g _ { _ { Y M } } C ^ { a b c } \Big ( \phi ^ { b ( 0 ) } \partial _ { \overline { { z } } } \overline { { \phi } } ^ { c ( 0 ) } - \overline { { \phi } } ^ { c ( 0 ) } \partial _ { z } \langle \phi ^ { b ( 0 ) } \partial _ { \overline { { z } } } \phi ^ { c ( 0 ) } \partial _ { \overline { { z } } } \phi ^ { c ( 0 ) } } \\ & { \qquad + i g _ { _ { Y M } } \gamma _ { z \overline { { z } } } ^ { - 1 } C ^ { a b c } \partial _ { z } \Big ( { \cal A } _ { z } ^ { b ( 0 ) } { \cal A } _ { \overline { { z } } } ^ { c ( 0 ) } \Big ) + i g _ { _ { Y M } } \gamma _ { z \overline { { z } } } ^ { - 1 } C ^ { a b c } { \cal A } _ { z } ^ { b ( 0 ) } \Big ( \partial _ { z } { \cal A } _ { \overline { { z } } } ^ { c ( 0 ) } - \partial _ { z } { \cal A } _ { z } ^ { c ( 0 ) } \Big ) } \\ & { \qquad - i g _ { _ { Y M } } C ^ { a b c } { \cal A } _ { u } ^ { b ( 0 ) } { \cal A } _ { z } ^ { c ( 0 ) } + \gamma _ { z \overline { { z } } } ^ { - 1 } g _ { _ { Y M } } ^ { 2 } C ^ { a b c } C ^ { d c e } { \cal A } _ { z } ^ { b ( 0 ) } { \cal A } _ { z } ^ { d ( 0 ) } { \cal A } _ { \overline { { z } } } ^ { e ( 0 ) } } \\ & { \qquad + g _ { _ { Y M } } ^ { 2 } C ^ { a b c } C ^ { d e c } { \cal A } _ { z } ^ { d ( 0 ) } \Big ( \phi ^ { b ( 0 ) } \overline { { \phi } } ^ { e ( 0 ) } + \phi ^ { e ( 0 ) } \overline { { \phi } } ^ { b ( 0 ) } \Big ) , } \end{array}
$$

$$
\begin{array} { r l } & { 2 \partial _ { u } A _ { \bar { z } } ^ { a ( 1 ) } = \partial _ { \bar { z } } A _ { u } ^ { a ( 0 ) } - \gamma _ { z \bar { z } } ^ { - 1 } \partial _ { \bar { z } } \Big ( \partial _ { z } A _ { \bar { z } } ^ { a ( 0 ) } - \partial _ { \bar { z } } A _ { z } ^ { a ( 0 ) } \Big ) + i g _ { _ { Y M } } C ^ { a b c } \Big ( \phi ^ { b ( 0 ) } \partial _ { \bar { z } } \bar { \phi } ^ { c ( 0 ) } - \bar { \phi } ^ { c ( 0 ) } \partial _ { \bar { z } } \bar { \phi } ^ { c ( 0 ) } } \\ & { \qquad - i g _ { _ { Y M } } \gamma _ { z \bar { z } } ^ { - 1 } C ^ { a b c } \partial _ { \bar { z } } \Big ( A _ { \bar { z } } ^ { b ( 0 ) } A _ { \bar { z } } ^ { c ( 0 ) } \Big ) - i g _ { _ { Y M } } \gamma _ { z \bar { z } } ^ { - 1 } C ^ { a b c } A _ { \bar { z } } ^ { b ( 0 ) } \Big ( \partial _ { z } A _ { \bar { z } } ^ { c ( 0 ) } - \partial _ { \bar { z } } A _ { z } ^ { c ( 0 ) } \Big ) } \\ & { \qquad - i g _ { _ { Y M } } C ^ { a b c } A _ { u } ^ { b ( 0 ) } A _ { \bar { z } } ^ { c ( 0 ) } + \gamma _ { z \bar { z } } ^ { - 1 } g _ { _ { Y M } } ^ { 2 } C ^ { a b c } C ^ { d c e } A _ { \bar { z } } ^ { b ( 0 ) } A _ { \bar { z } } ^ { d ( 0 ) } A _ { z } ^ { e ( 0 ) } } \\ & { \qquad + g _ { _ { Y M } } ^ { 2 } C ^ { a b c } C ^ { d a e } A _ { \bar { z } } ^ { d ( 0 ) } \Big ( \phi ^ { b ( 0 ) } \bar { \phi } ^ { e ( 0 ) } + \phi ^ { e ( 0 ) } \bar { \phi } ^ { b ( 0 ) } \Big ) , } \end{array}
$$

$$
\begin{array} { r l } & { 2 \partial _ { u } \phi ^ { a ( 1 ) } = - 2 \gamma _ { z \bar { z } } ^ { - 1 } \partial _ { z } \partial _ { \bar { z } } \phi ^ { a ( 0 ) } - i \gamma _ { z \bar { z } } ^ { - 1 } g _ { _ { Y M } } C ^ { a b c } \Bigl ( \partial _ { z } A _ { \bar { z } } ^ { b ( 0 ) } \phi ^ { c ( 0 ) } + \partial _ { \bar { z } } A _ { z } ^ { b ( 0 ) } \phi ^ { c ( 0 ) } \Bigr ) } \\ & { \phantom { 2 p c } - i g _ { _ { Y M } } C ^ { a b c } A _ { u } ^ { b ( 0 ) } \phi ^ { c ( 0 ) } - 2 i \gamma _ { z \bar { z } } ^ { - 1 } g _ { _ { Y M } } C ^ { a b c } \Bigl ( A _ { \bar { z } } ^ { b ( 0 ) } \partial _ { z } \phi ^ { c ( 0 ) } + A _ { z } ^ { b ( 0 ) } \partial _ { \bar { z } } \phi ^ { c ( 0 ) } \Bigr ) } \\ & { \phantom { 2 p c } + \gamma _ { z \bar { z } } ^ { - 1 } g _ { _ { Y M } } ^ { 2 } C ^ { b e c } C ^ { d c a } \Bigl ( A _ { z } ^ { b ( 0 ) } A _ { \bar { z } } ^ { d ( 0 ) } + A _ { z } ^ { d ( 0 ) } A _ { \bar { z } } ^ { b ( 0 ) } \Bigr ) \phi ^ { e ( 0 ) } , } \end{array}
$$

$$
\begin{array} { r l } & { 2 \partial _ { u } \bar { \phi } ^ { a ( 1 ) } = - 2 \gamma _ { z \bar { z } } ^ { - 1 } \partial _ { z } \partial _ { \bar { z } } \bar { \phi } ^ { a ( 0 ) } - i \gamma _ { z \bar { z } } ^ { - 1 } g _ { _ { Y M } } C ^ { a b c } \Big ( \partial _ { z } A _ { \bar { z } } ^ { b ( 0 ) } \bar { \phi } ^ { c ( 0 ) } + \partial _ { \bar { z } } A _ { z } ^ { b ( 0 ) } \bar { \phi } ^ { c ( 0 ) } \Big ) } \\ & { \phantom { 2 p c } - i g _ { _ { Y M } } C ^ { a b c } A _ { u } ^ { b ( 0 ) } \bar { \phi } ^ { c ( 0 ) } - 2 i \gamma _ { z \bar { z } } ^ { - 1 } g _ { _ { Y M } } C ^ { a b c } \Big ( A _ { \bar { z } } ^ { b ( 0 ) } \partial _ { \bar { z } } \bar { \phi } ^ { c ( 0 ) } + A _ { z } ^ { b ( 0 ) } \partial _ { \bar { z } } \bar { \phi } ^ { c ( 0 ) } \Big ) } \\ & { \phantom { 2 p c } + \gamma _ { z \bar { z } } ^ { - 1 } g _ { _ { Y M } } ^ { 2 } C ^ { b e c } C ^ { d c a } \Big ( A _ { z } ^ { b ( 0 ) } A _ { \bar { z } } ^ { d ( 0 ) } + A _ { z } ^ { d ( 0 ) } A _ { \bar { z } } ^ { b ( 0 ) } \Big ) \bar { \phi } ^ { e ( 0 ) } . } \end{array}
$$

However there is no constraint on the leading terms $A _ { z } ^ { a ( 0 ) }$ ， $A _ { \bar { z } } ^ { a ( 0 ) }$ ， $\phi ^ { a ( 0 ) }$ ，and $\bar { \phi } ^ { a ( 0 ) }$ We would refer to $\partial _ { u } A _ { z } ^ { a ( 0 ) }$ ， $\partial _ { u } A _ { \bar { z } } ^ { a ( 0 ) }$ ， $\partial _ { u } \phi ^ { a ( 0 ) }$ ，and $\partial _ { u } \bar { \phi } ^ { a ( 0 ) }$ as news functions following the terminology of [42-44]. The appearance of news functions reflects the local propagating degree of freedom.

In the end, the supplementary equations $D _ { \mu } F ^ { a \mu r } = g _ { { } _ { Y M } } J ^ { a r }$ control the time evolution of the integration constants as

$$
\begin{array} { r l r } & { } & { ) _ { u } A _ { u } ^ { a ( 0 ) } = \gamma _ { z \bar { z } } ^ { - 1 } \partial _ { u } \Big ( \partial _ { z } A _ { \bar { z } } ^ { a ( 0 ) } + \partial _ { \bar { z } } A _ { z } ^ { a ( 0 ) } \Big ) + i \gamma _ { z \bar { z } } ^ { - 1 } g _ { _ { Y M } } C ^ { a b c } \Big ( A _ { z } ^ { b ( 0 ) } \partial _ { u } A _ { \bar { z } } ^ { c ( 0 ) } - A _ { \bar { z } } ^ { c ( 0 ) } \partial _ { u } A _ { z } ^ { b ( 0 ) } \Big ) } \\ & { } & { + i g _ { _ { Y M } } C ^ { a b c } \Big ( \phi ^ { b ( 0 ) } \partial _ { u } \bar { \phi } ^ { c ( 0 ) } - \bar { \phi } ^ { c ( 0 ) } \partial _ { u } \phi ^ { b ( 0 ) } \Big ) . } \end{array}
$$

We summarize as follows: to specify one solution to the non-Abelian gauge system (3) with the conditions (10) and (11)，one must specify the data $A _ { z } ^ { a ( m ) } ( u _ { 0 } , z , \bar { z } )$ ， $A _ { \bar { z } } ^ { a ( m ) } ( u _ { 0 } , z , \bar { z } )$ $\phi ^ { a ( m ) } ( u _ { 0 } , z , \bar { z } )$ ， $\bar { \phi } ^ { a ( m ) } ( u _ { 0 } , z , \bar { z } )$ 9 $( m ~ \geq ~ 1 )$ and $A _ { u } ^ { a ( 0 ) } ( u _ { 0 } , z , \bar { z } )$ at the initial time $u _ { 0 }$ ， and specify the functions $A _ { z } ^ { a ( 0 ) } ( u , z , \bar { z } )$ ， $A _ { \bar { z } } ^ { a ( 0 ) } ( u , z , \bar { z } )$ ， $\phi ^ { a ( 0 ) } ( u , z , \bar { z } )$ and （20 $\bar { \phi } ^ { a ( 0 ) } ( u , z , \bar { z } )$ at any time on ${ \mathcal { T } } ^ { + }$ ：

# 3 Leading soft gluon theorem

The soft gluon theorem [8,35] is a relation connecting an $n + 1$ particle scattering where the extra particle is a soft gluon (with very low energy） to an $n$ particle scattering. In color-ordered amplitude form,it can be put in the following way:

$$
M _ { n + 1 } ^ { \pm } = ( S _ { \pm } ^ { ( 0 ) } + S _ { \pm } ^ { ( 1 ) } ) M _ { n } + { \mathcal O } ( \omega ) , \quad \omega  0 ,
$$

where $\pm$ and $\omega$ denote the helicity and the energy of the extra soft gluon, respectively. On the right-hand side, $S _ { \pm } ^ { ( 0 ) }$ and $S _ { \pm } ^ { ( 1 ) }$ are the so-called leading and sub-leading (in $\omega$ ·） soft factors. We revisit the soft gluon theorem in Appendix B. The soft factors are given explicitly by equations (87) and (88). The relation (29) is universal in the sense that it is valid for any type of matter minimally coupled at tree level2.

To connect soft theorems with asymptotic symmetries, one needs to recal the Ward identity of a spontaneously broken symmetry. In S-matrix language, a symmetry is just a relation between matrix elements $\langle \mathrm { o u t } ^ { \prime } | \mathrm { i n } ^ { \prime } \rangle = \langle \mathrm { o u t } | \mathrm { i n } \rangle$ ，where the in and out states are transformed as $| \mathrm { i n ^ { \prime } } \rangle = \mathrm { U } ^ { \mathrm { i n } } | \mathrm { i n } \rangle$ and $\lvert \mathrm { o u t } ^ { \prime } \rangle = \mathrm { U } ^ { \mathrm { o u t } } \lvert \mathrm { o u t } \rangle$ . If a conserved charge $Q$ can be associated to the symmetry, the Ward identity becomes

$$
\mathrm { \langle o u t | Q ^ { o u t } - Q ^ { i n } | i n \rangle = 0 . }
$$

The charge for a spontaneously broken symmetry must act non-linearly on the states, otherwise it will annihilate the vacuum. In principle, it can be split into a linear piece that annihilates the vacuum and a non-linear piece that does not annihilate the vacuum

$$
Q = Q _ { \mathrm { L } } + Q _ { \mathrm { N L } } .
$$

The Ward identity for a broken charge is

$$
\langle \mathrm { o u t } | \mathrm { Q } _ { \mathrm { N L } } ^ { \mathrm { o u t } } - \mathrm { Q } _ { \mathrm { N L } } ^ { \mathrm { i n } } | \mathrm { i n } \rangle = - \langle \mathrm { o u t } | \mathrm { Q } _ { \mathrm { L } } ^ { \mathrm { o u t } } - \mathrm { Q } _ { \mathrm { L } } ^ { \mathrm { i n } } | \mathrm { i n } \rangle .
$$

If $Q _ { \mathrm { N L } }$ creates zero-momentum Goldstone bosons,equation (32) looks very much like the soft theorem (29). We willshow precisely that the broken symmetry responsible for the soft gluon theorem is the asymptotic symmetry preserving the prescribed conditions (10)and(11） with the associated charge(13) in this section.

It is important to point out that we will only deal with the out part of the states in this note. The analysis of the in part can be performed analogously, up to an anti-podal identification. These details have been laid out for other theories in [12,13] (see also [27] for the Yang-Mills case), which can be easily extended to the non-Abelian gauge theory that we are exploring.

Following [12,13], we evaluate the charge (13) at the far past of the future null infinity ${ \mathcal { I } } _ { - } ^ { + }$ . The leading piece of the charge is

$$
\begin{array} { l } { { \displaystyle \mathrm { \Lambda } _ { \mathcal { T } _ { - } ^ { ( 0 ) } } ^ { ( 0 ) } = \int _ { \mathcal { T } _ { - } ^ { + } } \mathrm { d } z \mathrm { d } \bar { z } \gamma _ { z \bar { z } } \varepsilon ^ { a } A _ { u } ^ { a ( 0 ) } = \int _ { \mathcal { T } ^ { + } } \mathrm { d } u \mathrm { d } z \mathrm { d } \bar { z } \gamma _ { z \bar { z } } \varepsilon ^ { a } \partial _ { u } A _ { u } ^ { a ( 0 ) } } } \\ { { \displaystyle \quad = \int _ { \mathcal { T } ^ { + } } \mathrm { d } u \mathrm { d } z \mathrm { d } \bar { z } \varepsilon ^ { a } \partial _ { u } \Big ( \partial _ { z } A _ { \bar { z } } ^ { a ( 0 ) } + \partial _ { \bar { z } } A _ { z } ^ { a ( 0 ) } \Big ) + i \varepsilon ^ { a } g _ { _ { Y M } } C ^ { a b c } \Big ( A _ { z } ^ { b ( 0 ) } \partial _ { u } A _ { \bar { z } } ^ { c ( 0 ) } - A _ { \bar { z } } ^ { c ( 0 ) } \partial _ { u } A _ { u } ^ { c ( 0 ) } \Big ) } } \\ { { \displaystyle \quad \quad + \gamma _ { z \bar { z } } i g _ { _ { Y M } } \varepsilon ^ { a } C ^ { a b c } \Big ( \phi ^ { b ( 0 ) } \partial _ { u } \bar { \phi } ^ { c ( 0 ) } - \bar { \phi } ^ { c ( 0 ) } \partial _ { u } \phi ^ { b ( 0 ) } \Big ) . } } \end{array}
$$

The charge splits into linear and non-linear pieces?

$$
\begin{array} { r l } & { \mathcal { Z } _ { \mathrm { L } } ^ { ( 0 ) } = \displaystyle \int _ { \mathcal { T } ^ { + } } \mathrm { d } u \mathrm { d } z \mathrm { d } \bar { z } g _ { _ { Y M } } i \varepsilon ^ { a } g _ { _ { Y M } } C ^ { a b c } \Big ( A _ { z } ^ { b ( 0 ) } \partial _ { u } A _ { \bar { z } } ^ { c ( 0 ) } - A _ { \bar { z } } ^ { c ( 0 ) } \partial _ { u } A _ { z } ^ { b ( 0 ) } \Big ) } \\ & { \qquad + \gamma _ { z \bar { z } } i g _ { _ { Y M } } \varepsilon ^ { a } C ^ { a b c } \Big ( \phi ^ { b ( 0 ) } \partial _ { u } \bar { \phi } ^ { c ( 0 ) } - \bar { \phi } ^ { c ( 0 ) } \partial _ { u } \phi ^ { b ( 0 ) } \Big ) , } \\ & { \mathcal { Q } _ { \mathrm { N L } } ^ { ( 0 ) } = \displaystyle \int _ { \mathcal { T } ^ { + } } \mathrm { d } u \mathrm { d } z \mathrm { d } \bar { z } \varepsilon ^ { a } \partial _ { u } \Big ( \partial _ { z } A _ { \bar { z } } ^ { a ( 0 ) } + \partial _ { \bar { z } } A _ { z } ^ { a ( 0 ) } \Big ) . } \end{array}
$$

For the news fields, one needs to perform a stationary-phase approximation of the gauge field mode expansion:

$$
A _ { z ( \bar { z } ) } ^ { a ( 0 ) } ( x ) = - \frac { i g _ { _ { Y M } } } { 8 \pi ^ { 2 } } \frac { \sqrt { 2 } } { 1 + z \bar { z } } \int _ { 0 } ^ { \infty } \mathrm { d } \omega _ { q } \left[ \mathfrak { a } _ { + ( - ) } ^ { a } ( \omega _ { q } \hat { x } ) e ^ { - i \omega _ { q } u } - \mathfrak { a } _ { - ( + ) } ^ { a \dagger } ( \omega _ { q } \hat { x } ) e ^ { i \omega _ { q } u } \right] ,
$$

where the creation and annihilation operators satisfy the standard commutation relations.Then,using the Fourier relation,

$$
F ( u ) = \int _ { - \infty } ^ { \infty } \mathrm { d } \omega e ^ { i \omega u } \tilde { F } ( \omega ) , \quad \int _ { - \infty } ^ { \infty } \mathrm { d } u \partial _ { u } F ( u ) = 2 \pi i \operatorname * { l i m } _ { \omega  0 } [ \omega \tilde { F } ( \omega ) ] ,
$$

and a special choice of the gauge parameter

$$
\varepsilon ^ { a } ( z , \bar { z } ) = \frac { 1 } { w - z } ,
$$

which leads to $\partial _ { \bar { z } } \varepsilon ^ { a } = - 2 \pi \delta ^ { 2 } ( z - w )$ , we obtain for the non-linear pieces of the charge $^ 4$

$$
\langle \mathrm { o u t } | { \mathcal Q } _ { \mathrm { N L } } ^ { ( 0 ) } | \mathrm { i n } \rangle = \frac { 1 } { 4 } \frac { \sqrt { 2 } g _ { _ { Y M } } } { 1 + | w | ^ { 2 } } \operatorname* { l i m } _ { \omega _ { q } \to 0 } \langle \mathrm { o u t } | \omega _ { q } \mathfrak { a } _ { + } ^ { a } ( q ) | \mathrm { i n } \rangle _ { i _ { 1 } \cdots i _ { n } } ,
$$

where $a$ and $i _ { k } \left( k = 1 , 2 , \cdots n \right)$ are color indices.

In order to obtain the proper action of the linear pieces of the charge on the out states, one has to define canonical commutation relations at infinity. The non-vanishing ones are

$$
\begin{array} { l } { { \displaystyle { [ A _ { \bar { z } } ^ { a ( 0 ) } ( u , z , \bar { z } ) , A _ { z } ^ { b ( 0 ) } ( u ^ { \prime } , w _ { k } , \bar { w } _ { k } ) ] = \frac { 1 } { 4 } \delta ^ { a b } \Theta ( u ^ { \prime } - u ) \delta ^ { 2 } ( z - w _ { k } ) , } } } \\ { { \displaystyle { [ \overline { { { \phi } } } ^ { a ( 0 ) } ( u , z , \bar { z } ) , \phi ^ { b ( 0 ) } ( u ^ { \prime } , w _ { k } , \bar { w } _ { k } ) ] = \frac { 1 } { 4 } \delta _ { a b } \gamma _ { z \bar { z } } ^ { - 1 } \Theta ( u ^ { \prime } - u ) \delta ^ { 2 } ( z - w _ { k } ) . } } } \end{array}
$$

We define the Fourier modes as

$$
\begin{array} { l } { { \displaystyle { \cal A } _ { E _ { k } } ^ { d } ( w _ { k } , \bar { w } _ { k } ) = \int \mathrm { d } u ^ { \prime } e ^ { i E _ { k } u ^ { \prime } } { \cal A } _ { z } ^ { d ( 0 ) } ( u ^ { \prime } , w _ { k } , \bar { w } _ { k } ) , } } \\ { { \displaystyle \phi _ { E _ { k } } ^ { d } ( w _ { k } , \bar { w } _ { k } ) = \int \mathrm { d } u ^ { \prime } e ^ { i E _ { k } u ^ { \prime } } \phi ^ { d ( 0 ) } ( u ^ { \prime } , w _ { k } , \bar { w } _ { k } ) . } } \end{array}
$$

Theactions of the fields on the Fourier modes are

$$
\begin{array} { c } { { \displaystyle { \big [ } A _ { \bar { z } } ^ { a ( 0 ) } , A _ { E _ { k } } ^ { d } ( w _ { k } , \bar { w } _ { k } ) { \big ] } = i \frac { 1 } { 4 } \delta ^ { a d } \delta ^ { 2 } ( z - w _ { k } ) \frac { e ^ { i E _ { k } u } } { E _ { k } } , } } \\ { { \displaystyle { \big [ } \bar { \phi } ^ { a ( 0 ) } , \phi _ { E _ { k } } ^ { d } ( w _ { k } , \bar { w } _ { k } ) { \big ) } { \big ] } = i \frac { 1 } { 4 } \delta ^ { a d } \delta ^ { 2 } ( z - w _ { k } ) \frac { e ^ { i E _ { k } u } } { E _ { k } } , } } \end{array}
$$

which yield

$$
\begin{array} { l } { { \displaystyle \big [ \mathcal { Q } _ { \mathrm { L } } ^ { ( 0 ) } , \mathcal { A } _ { E _ { k } } ^ { d } \big ( w _ { k } , \bar { w } _ { k } \big ) \big ] = - \frac { i g _ { _ { Y M } } C _ { k } ^ { a b d } } { 4 \big ( w - w _ { k } \big ) } A _ { E _ { k } } ^ { b } \big ( w _ { k } , \bar { w } _ { k } \big ) , } }  \\ { { \displaystyle \big [ \mathcal { Q } _ { \mathrm { L } } ^ { ( 0 ) } , \phi _ { E _ { k } } ^ { d } \big ( w _ { k } , \bar { w } _ { k } \big ) \big ] = - \frac { i g _ { _ { Y M } } C _ { k } ^ { a b d } } { 4 \big ( w - w _ { k } \big ) } \phi _ { E _ { k } } ^ { b } \big ( w _ { k } , \bar { w } _ { k } \big ) , } }  \end{array}
$$

where the special choice of $\varepsilon ^ { a }$ in(38) has been used.Hence

$$
\langle \mathrm { o u t } | Q _ { \mathrm { L } } ^ { ( 0 ) } | { \mathrm { i n } } \rangle = - \sum _ { k = 1 } ^ { n } { \frac { g _ { Y M } ( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } } { 4 ( w - w _ { k } ) } } \langle \mathrm { o u t } | { \mathrm { i n } } \rangle _ { i _ { 1 } \cdots j _ { k } \cdots i _ { n } } ,
$$

where $( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } = - i C _ { k } ^ { a i _ { k } j _ { k } }$ in adjoint representation.Inserting (47)and (39) into the Ward identity (32)，one should be able to reproduce the leading soft gluon theorem (92）in asymptotic position space.

# 4 Sub-leading soft gluon theorem

After the realization that the leading soft gluon theorem follows from the asymptotic symmetry of the non-Abelian gauge theory, whether or not the sub-leading soft gluon theorem follows from new asymptotic symmetries becomes a very important question. In Abelian gauge theory and linearized gravity theory, the sub-leading soft theorems were shown [20,21] to be equivalent to the Ward identities for the sub-leading pieces (in $\textstyle { \frac { 1 } { r } }$ ) of the charge associated to the same asymptotic symmetry responsible for the leading soft theorem. It is very interesting to check whether this prescription can recover the sub-leading soft gluon theorem in our case.

The sub-leading piece of the charge (13) is

$$
\begin{array} { l } { { \displaystyle Q ^ { ( 1 ) } = - \frac { 1 } { r } \int _ { \mathbb { Z } _ { - } ^ { + } } \mathrm { d } z \mathrm { d } \bar { z } \varepsilon ^ { a } A _ { u } ^ { a ( 1 ) } } } \\ { { \displaystyle \ } = - \frac { 1 } { r } \int _ { \mathbb { Z } _ { - } ^ { + } } \mathrm { d } z \mathrm { d } \bar { z } \varepsilon ^ { a } \biggl [ \partial _ { z } A _ { \bar { z } } ^ { a ( 1 ) } + \partial _ { \bar { z } } A _ { z } ^ { a ( 1 ) } } \\ { { \displaystyle \ + i g _ { \scriptscriptstyle Y M } C ^ { a b c } \biggl ( A _ { z } ^ { b ( 0 ) } A _ { \bar { z } } ^ { c ( 1 ) } - A _ { z } ^ { b ( 1 ) } A _ { \bar { z } } ^ { c ( 0 ) } + \gamma _ { z \bar { z } } \phi ^ { b ( 0 ) } \bar { \phi } ^ { c ( 1 ) } - \gamma _ { z \bar { z } } \phi ^ { b ( 1 ) } \bar { \phi } ^ { c ( 0 ) } \biggr ) \biggr ] . } } \end{array}
$$

The next step should be checking the action of the charge on the states using the stationary-phase approximation (36) and the commutation relations (40)-(41). However, we find that this is very hard, if not impossible,to achieve due to the complicated expressions in (24)-(27). Another difficulty is from the translation of the sub-leading soft factor (88) to asymptotic position space. It is not yet clear how to translate the helicity terms in the angular momentum operator in the sub-leading soft factor to asymptotic position space. As a first step to check the proposal of [20,21] in the non-Abelian case, we focus on a particular case for the linearized part of the theory. We make the change of variables

$$
A _ { \mu } ^ { a }  A _ { \mu } ^ { a } + g _ { _ { Y M } } a _ { \mu } ^ { a } , \quad \phi ^ { a }  \Phi ^ { a } + g _ { _ { Y M } } \varphi ^ { a } ,
$$

where $( \mathcal { A } _ { \mu } ^ { a } , \Phi ^ { a } )$ is a background solution of the equations of motion (7), and we consider the lowest non-trivial order of the theory i.e. the quadratic order (in $g _ { _ { Y M } }$ ）in the Lagrangian. In terms of Feynman diagrams, we will only deal with three-point vertices in which one gluon couples to two scalars in this note. The gluon three-point vertices and more point vertex are left for future investigation. For simplicity, we choose the background solution of the gauge field $A _ { \mu } ^ { a } = 0$ . With such simplification,the effective currents $J ^ { c \mu }$ defined in (8） become globally conserved currents while equations (24), (25),and (28) reduce to

$$
\begin{array} { r l } & { 2 \partial _ { u } a _ { z } ^ { a ( 1 ) } = \partial _ { z } a _ { u } ^ { a ( 0 ) } + \gamma _ { z \bar { z } } ^ { - 1 } \partial _ { z } \bigl ( \partial _ { z } a _ { \bar { z } } ^ { a ( 0 ) } - \partial _ { \bar { z } } a _ { z } ^ { a ( 0 ) } \bigr ) + j _ { z } ^ { a } , } \\ & { 2 \partial _ { u } a _ { \bar { z } } ^ { a ( 1 ) } = \partial _ { \bar { z } } a _ { u } ^ { a ( 0 ) } - \gamma _ { z \bar { z } } ^ { - 1 } \partial _ { \bar { z } } \bigl ( \partial _ { z } a _ { \bar { z } } ^ { a ( 0 ) } - \partial _ { \bar { z } } a _ { z } ^ { a ( 0 ) } \bigr ) + j _ { \bar { z } } ^ { a } , } \\ & { \partial _ { u } a _ { u } ^ { a ( 0 ) } = \gamma _ { z \bar { z } } ^ { - 1 } \partial _ { u } \bigl ( \partial _ { z } a _ { \bar { z } } ^ { a ( 0 ) } + \partial _ { \bar { z } } a _ { z } ^ { a ( 0 ) } \bigr ) + j _ { u } ^ { a } , } \end{array}
$$

where

$$
\begin{array} { l } { { j _ { z } ^ { a } = i C ^ { a b c } ( \Phi ^ { b ( 0 ) } \partial _ { z } \bar { \Phi } ^ { c ( 0 ) } - \bar { \Phi } ^ { c ( 0 ) } \partial _ { z } \Phi ^ { b ( 0 ) } ) , } } \\ { { j _ { \bar { z } } ^ { a } = i C ^ { a b c } ( \Phi ^ { b ( 0 ) } \partial _ { \bar { z } } \bar { \Phi } ^ { c ( 0 ) } - \bar { \Phi } ^ { c ( 0 ) } \partial _ { \bar { z } } \Phi ^ { b ( 0 ) } ) , } } \\ { { j _ { u } ^ { a } = i C ^ { a b c } ( \Phi ^ { b ( 0 ) } \partial _ { u } \bar { \Phi } ^ { c ( 0 ) } - \bar { \Phi } ^ { c ( 0 ) } \partial _ { u } \Phi ^ { b ( 0 ) } ) . } } \end{array}
$$

The sub-leading charge becomes

$$
Q ^ { ( 1 ) } = - \frac { g _ { { \scriptscriptstyle Y M } } } { r } \int _ { \bar { \cal Z } _ { - } ^ { + } } \mathrm { d } z \mathrm { d } \bar { z } \varepsilon ^ { a } ( \partial _ { z } a _ { \bar { z } } ^ { a ( 1 ) } + \partial _ { \bar { z } } a _ { z } ^ { a ( 1 ) } + \gamma _ { z \bar { z } } j _ { r } ^ { a } ) ,
$$

where

$$
j _ { r } ^ { a } = i C ^ { a b c } ( \Phi ^ { b ( 0 ) } \bar { \Phi } ^ { c ( 1 ) } - \Phi ^ { b ( 1 ) } \bar { \Phi } ^ { c ( 0 ) } ) .
$$

One can recognize that $j _ { \mu } ^ { a }$ are just the leading terms of the conserved current $J _ { \mu } ^ { a }$ . In [20], it is very crucial to set the radial component of the current to zero by the ambiguities of a conserved current to adapt to the radial gauge condition5. Applying the same reasoning, we will drop the ${ j } _ { r } ^ { a }$ term from the sub-leading charge (54).

Now the sub-leading charge can be arranged into

$$
\begin{array} { r l } & { \mathcal { Q } ^ { ( 1 ) } = - \frac { g _ { _ { Y M } } } { r } \displaystyle \int _ { \mathcal T _ { - } ^ { + } } \mathrm { d } z \mathrm { d } \bar { z } \varepsilon ^ { a } \big ( \partial _ { z } a _ { \bar { z } } ^ { a ( 1 ) } + \partial _ { \bar { z } } a _ { z } ^ { a ( 1 ) } \big ) = - \frac { g _ { _ { Y M } } } { r } \displaystyle \int _ { \mathcal T ^ { + } } \mathrm { d } u \mathrm { d } z \mathrm { d } \bar { z } \varepsilon ^ { a } \partial _ { u } \big ( \partial _ { z } a _ { \bar { z } } ^ { a ( 1 ) } + } \\ & { \quad \quad = - \frac { g _ { _ { Y M } } } { r } \displaystyle \int _ { \mathcal T ^ { + } } \mathrm { d } u \mathrm { d } z \mathrm { d } \bar { z } \varepsilon ^ { a } \bigg [ \partial _ { u } \big ( u \partial _ { z } \partial _ { \bar { z } } a _ { u } ^ { a ( 0 ) } \big ) - u \partial _ { z } \partial _ { \bar { z } } \partial _ { u } a _ { u } ^ { a ( 0 ) } + \frac { 1 } { 2 } \big ( \partial _ { z } j _ { \bar { z } } ^ { a } + \partial _ { \bar { z } } j _ { z } ^ { a } \big ) \bigg ] } \\ & { \quad \quad = \frac { g _ { _ { Y M } } } { r } \displaystyle \int _ { \mathcal T ^ { + } } \mathrm { d } u \mathrm { d } z \mathrm { d } \bar { z } \varepsilon ^ { a } \bigg [ u \partial _ { z } \partial _ { \bar { z } } \big ( \gamma _ { z \bar { z } } ^ { - 1 } \partial _ { u } \big ( \partial _ { \xi } a _ { \bar { z } } ^ { a ( 0 ) } + \partial _ { \bar { z } } a _ { z } ^ { a ( 0 ) } \big ) \big ) } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad + u \partial _ { z } \partial _ { \bar { z } } j _ { u } ^ { a } - \frac { 1 } { 2 } \big ( \partial _ { z } j _ { \bar { z } } ^ { a } + \partial _ { \bar { z } } j _ { z } ^ { a } \big ) \bigg ] , } \end{array}
$$

where we have used integration by parts several times and one can drop the boundary term

$$
\int _ { \mathbb { Z } ^ { + } } \mathrm { d } z \mathrm { d } \bar { z } \mathrm { d } u \partial _ { u } \left( u \varepsilon ^ { a } \partial _ { z } \partial _ { \bar { z } } a _ { u } ^ { a ( 0 ) } \right) = - \operatorname* { l i m } _ { u \to \infty } u \int _ { \mathbb { Z } _ { - } ^ { + } } \mathrm { d } z \mathrm { d } \bar { z } \partial _ { \bar { z } } \partial _ { \bar { z } } \varepsilon ^ { a } a _ { u } ^ { a ( 0 ) } ,
$$

which is simply a consequence of6

$$
\langle \mathrm { o u t } | Q _ { \varepsilon _ { \mathrm { o u t } } ^ { a } = \partial _ { z } \partial _ { \bar { z } } \varepsilon ^ { a } } ^ { ( 0 ) } | \mathrm { i n } \rangle = 0 .
$$

The charge also splits into linear and non-linear pieces

$$
\begin{array} { r l } & { \mathcal { Z } _ { \mathrm { L } } ^ { ( 1 ) } = \frac { g _ { \gamma _ { M } } } { 2 r } \int _ { \mathbb { Z } ^ { + } } \mathrm { d } u \mathrm { d } z \mathrm { d } \bar { z } \left[ u ( \partial _ { z } \partial _ { \bar { z } } \varepsilon ^ { a } + \partial _ { \bar { z } } \partial _ { z } \varepsilon ^ { a } ) j _ { u } ^ { a } + \partial _ { z } \varepsilon ^ { a } j _ { \bar { z } } ^ { a } + \partial _ { \bar { z } } \varepsilon ^ { a } j _ { \overline { { z } } } ^ { a } \right] , } \\ & { \mathcal { Z } _ { \mathrm { N L } } ^ { ( 1 ) } = \frac { g _ { \gamma _ { M } } } { r } \int _ { \mathbb { Z } ^ { + } } \mathrm { d } u \mathrm { d } z \mathrm { d } \bar { z } \left( - \partial _ { z } \big ( \gamma _ { \overline { { z \bar { z } } } } ^ { - 1 } \partial _ { \bar { z } } \big ( u \partial _ { u } a _ { \overline { { z } } } ^ { a ( 0 ) } \big ) \big ) \partial _ { \bar { z } } \varepsilon ^ { a } - \partial _ { \bar { z } } \big ( \gamma _ { \overline { { z \bar { z } } } } ^ { - 1 } \partial _ { \bar { z } } \big ( u \partial _ { u } a _ { z } ^ { a ( 0 ) } \big ) \big ) \partial _ { z } \varepsilon ^ { a } \right) . } \end{array}
$$

By exploiting the stationary-phase approximation

$$
a _ { z ( \bar { z } ) } ^ { a ( 0 ) } ( x ) = - \frac { i } { 8 \pi ^ { 2 } } \frac { \sqrt { 2 } } { 1 + z \bar { z } } \int _ { 0 } ^ { \infty } \mathrm { d } \omega _ { q } \left[ \mathfrak { a } _ { + ( - ) } ^ { a } ( \omega _ { q } \hat { x } ) e ^ { - i \omega _ { q } u } - \mathfrak { a } _ { - ( + ) } ^ { a \dagger } ( \omega _ { q } \hat { x } ) e ^ { i \omega _ { q } u } \right] ,
$$

and the Fourier relation

$$
\int _ { - \infty } ^ { \infty } \mathrm { d } u u \partial _ { u } F ( u ) = - 2 \pi \operatorname* { l i m } _ { \omega  0 } [ \partial _ { \omega } ( \omega \tilde { F } ( \omega ) ) ] ,
$$

one gets the action of the non-linear piece of the charge7

$$
\langle \mathrm { o u t } | Q _ { \mathrm { N L } } ^ { ( 1 ) } | \mathrm { i n } \rangle = - \frac { \sqrt { 2 } i } { 4 } \partial _ { w } \left[ \gamma _ { w \overline { { { w } } } } ^ { - 1 } \partial _ { w } \left( \frac { 1 } { 1 + | w | ^ { 2 } } \operatorname * { l i m } _ { \omega _ { q } \to 0 } \partial _ { \omega _ { q } } \langle \mathrm { o u t } | \omega _ { q } \mathfrak { a } _ { - } ^ { a } ( q ) | \mathrm { i n } \rangle _ { i _ { 1 } \cdots i _ { n } } \right) \right] ,
$$

where the special choice of $\varepsilon ^ { u }$ in(38) has been inserted.

From the commutation relations

$$
| \overline { { \Phi } } ^ { a ( 0 ) } ( u , z , \bar { z } ) , \Phi ^ { b ( 0 ) } ( u ^ { \prime } , w _ { k } , \bar { w } _ { k } ) ] = \frac { 1 } { 4 } \delta _ { a b } \gamma _ { z \bar { z } } ^ { - 1 } \Theta ( u ^ { \prime } - u ) \delta ^ { 2 } ( z - w _ { k } ) ,
$$

the action of the linear piece of the charge is

$$
\begin{array} { c } { { \displaystyle Q _ { \mathrm { L } } ^ { ( 1 ) } , \Phi _ { E _ { k } } ^ { d } ( w _ { k } , \bar { w } _ { k } ) ] = - \frac { i \pi C _ { k } ^ { a b d } } { 2 } } } \\ { { \left( \partial _ { w } ( \gamma _ { w \bar { w } } ^ { - 1 } \delta ( w - w _ { k } ) ) \partial _ { \omega _ { k } } + \gamma _ { w \bar { w } } ^ { - 1 } \omega _ { k } ^ { - 1 } \delta ( w - w _ { k } ) \partial _ { w _ { k } } \right) \phi _ { E _ { k } } ^ { b } ( w _ { k } , \bar { w } _ { k } ) , } } \end{array}
$$

where $\begin{array} { r } { \Phi _ { E _ { k } } ^ { d } ( w _ { k } , \bar { w } _ { k } ) = \int \mathrm { d } u ^ { \prime } e ^ { i E _ { k } u ^ { \prime } } \Phi ^ { d ( 0 ) } ( u ^ { \prime } , w _ { k } , \bar { w } _ { k } ) } \end{array}$ is the Fourier mode of the scalar field. Hence

$$
\begin{array} { l }  \displaystyle { { \mathrm { ' } \mathrm { o u t } | Q _ { \mathrm { L } } ^ { ( 1 ) } | \mathrm { i n } \rangle } = - \sum _ { k = 1 } ^ { n } \frac { \pi ( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } } { 2 } } \end{array}
$$

To recover the sub-leading soft gluon theorem (93), one just needs to insert (63) and (66) into the Ward identity (32),and the relation

$$
\begin{array} { r l } & { \displaystyle \partial _ { w } \left\{ \gamma _ { w \overline { { w } } } ^ { - 1 } \partial _ { w } \left[ \frac { 1 } { 1 + | w | ^ { 2 } } \left( \frac { 1 + w \overline { { w } } _ { k } } { \bar { w } - \bar { w } _ { k } } \partial _ { \omega _ { k } } + \frac { \left( 1 + | w _ { k } | ^ { 2 } \right) \left( w - w _ { k } \right) } { \omega _ { k } \left( \bar { w } - \bar { w } _ { k } \right) } \partial _ { w _ { k } } \right) \right] \right\} } \\ & { \quad \quad \quad \quad = - 2 \pi \gamma _ { w \overline { { w } } } \left( \partial _ { w } \left( \gamma _ { w \overline { { w } } } ^ { - 1 } \delta ( w - w _ { k } ) \right) \partial _ { \omega _ { k } } + \gamma _ { w \overline { { w } } } ^ { - 1 } \omega _ { k } ^ { - 1 } \delta ( w - w _ { k } ) \partial _ { w _ { k } } \right) } \end{array}
$$

needs to be utilized.

# 5 Discussions

Based on recent proposals in QED and gravitational theory that soft theorems can be interpreted as Ward identities of certain asymptotic symmetries [12,13], we have shown precisely the equivalence of the leading soft gluon theorem and the Ward identity for the asymptotic symmetry of non-Abelian gauge theory. Following the prescription in [20,21]， we also show that the sub-leading soft gluon theorem can actually follow from the same symmetry in a simpler set-up for which we consider only vertices where a gluon couples to two scalars.

There are several open questions which need detailed investigation in the future. An immediate one is whether we can recover the sub-leading soft gluon theorem from the Ward identity of the sub-leading charge, including all vertices of the non-Abelian gauge theory. There are technical difficulties from the sub-leading charge and the subleading soft factor with helicity terms. Nevertheless,we believe that this problem can be fixed with very careful analysis since the prescription in [20,21] presents a remarkably consistent matching of two expansions and it also partially succeeds in deriving the sub-leading gluon theorem.

Another interesting question comes from the multiple soft emissions [35] (see also [52] for recent development). In such a case, the soft factor does not have a simple factorization even at the leading order; namely, the soft factor is related to the order of the gluons taken to be soft. Such a phenomenon is related to the structure of the symmetry group controlling the soft theorem [53]. It would be a very enlightening investigation to check the possible connection of the soft theorems with multiple soft emissions and asymptotic symmetries.

# Acknowledgments

The authors thank Glenn Barnich and Eduardo Conde for useful discussions. This work is supported in part by the National Natural Science Foundation of China Grant No. 11575202.

# A Surface charge in non-Abelian gauge theory

We will derive the surface charge for non-Abelian gauge theory (3) using the cohomological technique [40,41]. Such an approach is based on the equivalence classes of the Lagrangian up to total divergences.

We use $\phi ^ { i }$ to denote the fields in general in the variational principle. In an $n$ （20 dimensional spacetime, the theory is defined by the Lagrangian $L = \mathcal { L } \mathrm { d } ^ { n } x$ ，where $\mathrm { d } ^ { n } x$ （20 is the spacetime volume form. The notation

$$
( d ^ { n - p } x ) _ { \mu _ { 1 } . . . \mu _ { p } } = \frac { 1 } { p ! ( n - p ) ! } \epsilon _ { \mu _ { 1 } . . . \mu _ { p } \mu _ { p + 1 } . . . \mu _ { n } } \mathrm { d } x ^ { \mu _ { p + 1 } } . . . \mathrm { d } x ^ { \mu _ { n } }
$$

will be used in this appendix where $\epsilon _ { \mu _ { 1 } \dots \mu _ { n } }$ is completely antisymmetric. The Lagrangian is invariant up to total divergences under the non trivial gauge transformations

$$
\delta _ { f } \phi ^ { i } = R _ { \alpha } ^ { i } ( f ^ { \alpha } ) .
$$

The construction of the $n - 2$ forms can be summarized as follows: for any $f ^ { \alpha }$ standard integrations by parts lead to

$$
R _ { \alpha } ^ { i } ( f ^ { \alpha } ) { \frac { \delta L } { \delta \phi ^ { i } } } = f ^ { \alpha } R _ { \alpha } ^ { + i } ( { \frac { \delta L } { \delta \phi ^ { i } } } ) + \mathrm { d } _ { H } S _ { f } ,
$$

for some $n - 1$ form

$$
S _ { f } = S _ { \alpha } ^ { i \mu } ( \frac \partial { \partial \mathrm { d } x ^ { \mu } } \frac { \delta { \cal L } } { \delta \phi ^ { i } } , f ^ { \alpha } )
$$

vanishing on-shell. The $n - 2$ form will be obtained by acting the contracting homotopy operator $\rho _ { H }$ for the horizontal differential of the variational bi-complex [54]

$$
\{ \mathrm { d } _ { H } , \rho _ { H } \} \omega ^ { p } = \omega ^ { p } \mathrm { f o r } p < n
$$

on $S _ { f }$

$$
k _ { f } = \rho _ { H } S _ { f } .
$$

For particular gauge transformations that satisfy $R _ { \alpha } ^ { i } ( f ^ { \alpha } ) = 0$ (we refer to them as reducibility parameters)，(70) leads to $\mathrm { d } _ { H } S _ { f } = 0$ . Hence （72） reduces to

$$
\mathrm { d } _ { H } k _ { f } = S _ { f } \approx 0 .
$$

However, the reducibility parameter does not exist in general in many theories (e.g. Yang-Mills theory and Einstein gravity). Normally, one would linearize such theories around a background solution $\bar { \phi } ^ { i }$ for deriving the surface charges. For instance, using the linearized theory at infinity with prescribed asymptotics to define conservation laws in general relativity is well explained in [55]. In the linearized theory, the gauge transformations are denoted by $\delta _ { \epsilon } \varphi ^ { i } = R _ { \alpha } ^ { i } [ \varphi ^ { i } , \phi ] ( \epsilon ^ { \alpha } )$ . It has been shown [56] that one can obtain the $n - 2$ forms for the linearized theory from the full theory through

$$
k _ { f } [ \delta \phi , \phi ] = k _ { f } ^ { \mu \nu } ( \mathrm { d } ^ { n - 2 } x ) _ { \mu \nu } = \frac { \lvert \lambda \rvert + 1 } { \lvert \lambda \rvert + 2 } \partial _ { ( \lambda ) } [ \delta \phi ^ { i } \frac { \delta } { \delta \phi _ { ( ( \lambda ) \nu ) } ^ { i } } \frac { \partial } { \partial \mathrm { d } x ^ { \nu } } S _ { f } ] ,
$$

by the following arrangements: $f$ replaced by the reducibility parameters of the linearized theory, $\phi ^ { i }$ replaced by the background solution ${ \bar { \phi } } ^ { i }$ and $\delta \phi ^ { i }$ replaced by any solution $\bar { \varphi } ^ { i }$ of the linearized theory. In particular, for $S _ { f }$ up to second order derivatives, one can reduce（75） to

$$
k _ { f } [ \delta \phi , \phi ] = \frac { 1 } { 2 } \delta \phi ^ { i } \frac { \delta } { \delta \phi _ { \nu } ^ { i } } \frac { \partial } { \partial \mathrm { d } x ^ { \nu } } S _ { f } + \frac { 2 } { 3 } \partial _ { \sigma } [ \delta \phi ^ { i } \frac { \delta } { \delta \phi _ { \nu \sigma } ^ { i } } \frac { \partial } { \partial \mathrm { d } x ^ { \nu } } S _ { f } ] .
$$

Associating conserved charges to asymptotic symmetries is a somewhat tricky question [57]. In practice, one can take a more pragmatic step [40] that lies in using the formula for the $n - 2$ forms above,but substituting asymptotic reducibility parameters and asymptotic solutions determined by the fal-off conditions instead of the exact ones from linearized theory. Consequently, the $n - 2$ forms are in general non-integrable. This is precisely what happens in [58-62]. We will follow the same strategy for getting the surface charges associated to asymptotic symmetries in non-Abelian gauge theory.

Applying (7O) to the Lagrangian (3) with the precise gauge transformations (9), the $n - 1$ form is obtained as

$$
S _ { f } [ \delta \phi , \phi ] = - \nabla _ { \nu } \left( f ^ { a } F ^ { a \mu \nu } \right) ( \mathrm { d } ^ { n - 1 } x ) _ { \mu } .
$$

Using (76), one finds the $n - 2$ form is actually integrable and given by

$$
k _ { f } [ \delta \phi , \phi ] = - \delta \left( f ^ { a } F ^ { a \mu \nu } \right) ( \mathrm { d } ^ { n - 2 } x ) _ { \mu \nu } .
$$

# BLeading and sub-leading soft gluon theorems

For completeness， we review the leading and sub-leading soft gluon theorems. We have set all of the momenta outgoing by using crossing symmetry. The discussion of the sub-leading soft limit follows closely the one in [51]. We denote the amplitude with $n$ particles as $A ( p _ { 1 } , \cdots , p _ { n } ) _ { i _ { 1 } \cdots i _ { n } }$ and the amplitude with the extra one gluon as （204号 $\epsilon _ { q \mu } A ^ { \mu } ( p _ { 1 } , \cdot \cdot \cdot , p _ { n } , q ) _ { i _ { 1 } \cdot \cdot \cdot i _ { n } a }$ where $i _ { k }$ and $a$ are color indices. We have

$$
\begin{array} { c } { { ( p _ { 1 } , \cdots , p _ { n } , q ) _ { i _ { 1 } \cdots i _ { n } a } = \displaystyle \sum _ { k = 1 } ^ { n } \displaystyle \frac { - i } { ( q + p _ { k } ) ^ { 2 } } i ( q + 2 p _ { k } ) ^ { \mu } ( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } A ( p _ { 1 } , \cdots , p _ { k } + q , \cdots , p _ { n } ) _ { i _ { 1 } \cdots i _ { n } } } } \\ { { + N ^ { \mu } ( p _ { 1 } , \cdots , p _ { n } , q ) _ { i _ { 1 } \cdots i _ { n } a } , ~ ( \tilde { \eta } _ { \mu \nu \mu } , \tilde { \eta } _ { \nu \mu } ) _ { i _ { 1 } \cdots i _ { n } } , } } \end{array}
$$

where $( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } \equiv ( T _ { R _ { k } } ^ { a } ) _ { i _ { k } j _ { k } }$ . Gauge invariance yields

$$
\begin{array} { r c l } { { 0 } } & { { = } } & { { q _ { \mu } A ^ { \mu } ( p _ { 1 } , \cdots , p _ { n } , q ) _ { i _ { 1 } \cdots i _ { n } a } } } \\ { { } } & { { = } } & { { \displaystyle \sum _ { k = 1 } ^ { n } ( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } ( 1 + q _ { \mu } \frac \partial { \partial p _ { k \mu } } ) A ( p _ { 1 } , \cdots , p _ { k } , \cdots , p _ { n } ) _ { i _ { 1 } \cdots j _ { k } \cdots i _ { n } } } } \\ { { } } & { { } } & { { + q _ { \mu } N ^ { \mu } ( p _ { 1 } , \cdots , p _ { n } , q = 0 ) _ { i _ { 1 } \cdots i _ { n } a } + { \mathcal O } ( q ^ { 2 } ) . } } \end{array}
$$

At leading order this leads to

$$
\sum _ { k = 1 } ^ { n } ( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } A ( p _ { 1 } \cdot \cdot \cdot p _ { k } \cdot \cdot \cdot p _ { n } ) _ { i _ { 1 } \cdot \cdot \cdot j _ { k } \cdot \cdot \cdot i _ { n } } = 0 .
$$

Such a relation can be understood as the Ward identity for a global symmetry which is induced from the gauge symmetry by just choosing constant gauge transformation parameter. One can also consider (81) as the non-Abelian generalization of charge conservation.

At sub-leading order this gives

$$
q _ { \mu } N ^ { \mu } ( p _ { 1 } , \cdots , p _ { n } , q = 0 ) _ { i _ { 1 } \cdots i _ { n } a } = - \sum _ { k = 1 } ^ { n } ( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } q _ { \mu } { \frac { \partial } { \partial p _ { k \mu } } } A ( p _ { 1 } , \cdots , p _ { k } , \cdots , p _ { n } ) _ { i _ { 1 } \cdots j _ { k } \cdots i _ { n } } .
$$

As noticed in [51], the solution of $q ^ { \mu } E _ { \mu } = 0$ which is local in $q ^ { \mu }$ can only be

$$
E ^ { \mu } = ( B _ { 1 } ( p _ { k } , q ) \cdot q ) B _ { 2 } ^ { \mu } ( p _ { k } , q ) - ( B _ { 2 } ( p _ { k } , q ) \cdot q ) B _ { 1 } ^ { \mu } ( p _ { k } , q ) .
$$

Hence it will not contribute to $N ^ { \mu } ( p _ { 1 } , \cdot \cdot \cdot , p _ { n } , q = 0 ) _ { i _ { 1 } \cdot \cdot \cdot i _ { n } a }$ . So we have

$$
N ^ { \mu } ( p _ { 1 } , \cdots , p _ { n } , q = 0 ) _ { i _ { 1 } \cdots i _ { n } a } = - \sum _ { k = 1 } ^ { n } ( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } \frac { \partial } { \partial p _ { k \mu } } A ( p _ { 1 } , \cdots , p _ { k } , \cdots , p _ { n } ) _ { i _ { 1 } \cdots j _ { k } \cdots i _ { n } } ,
$$

whichleadsto

$$
A ^ { \mu } ( p _ { 1 } , \cdots , p _ { n } , q ) _ { i _ { 1 } \cdots i _ { n } a } = \sum _ { k = 1 } ^ { n } \frac { ( T _ { k } ^ { a } ) _ { i _ { k } , j _ { k } } } { p _ { k } \cdot q } ( p _ { k } ^ { \mu } - i q _ { \nu } J _ { k } ^ { \mu \nu } ) A ( p _ { 1 } , \cdots , p _ { n } ) _ { i _ { 1 } \cdots i _ { n } } + { \mathcal O } ( q ) ,
$$

where $J _ { k } ^ { \mu \nu }$ is the total angular momentum operator. Finally the leading and sub-leading limit of the amplitude are

$$
\begin{array} { l } { { A ( p _ { 1 } , \cdots , p _ { n } , q ) _ { i _ { 1 } \cdots i _ { n } a } \equiv \epsilon _ { q \mu } A ^ { \mu } ( p _ { 1 } , \cdots , p _ { n } , q ) _ { i _ { 1 } \cdots i _ { n } a } } } \\ { {  \displaystyle \sum _ { k = 1 } ^ { n } ( S _ { k } ^ { ( 0 ) } + S _ { k } ^ { ( 1 ) } ) ( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } A ( p _ { 1 } , \cdots , p _ { n } ) _ { i _ { 1 } \cdots j _ { k } \cdots i _ { n } } , } } \end{array}
$$

where

$$
\begin{array} { r c l } { { S _ { k } ^ { ( 0 ) } } } & { { = } } & { { \displaystyle \frac { p _ { k } \cdot \epsilon _ { q } } { p _ { k } \cdot q } , } } \\ { { } } & { { } } & { { } } \\ { { S _ { k } ^ { ( 1 ) } } } & { { = } } & { { \displaystyle - i \frac { \epsilon _ { q \mu } q _ { \nu } J _ { k } ^ { \mu \nu } } { p _ { k } \cdot q } . } } \end{array}
$$

Let us now put the soft factors to asymptotic position space to compare with the result of the Ward identity for asymptotic symmetries. The null momenta need to be parametrized as

$$
\begin{array} { c } { { p _ { k \mu } = \displaystyle \frac { \omega _ { k } } { 1 + w _ { k } \bar { w } _ { k } } \left( 1 + w _ { k } \bar { w } _ { k } , w _ { k } + \bar { w } _ { k } , i ( \bar { w } _ { k } - w _ { k } ) , 1 - w _ { k } \bar { w } _ { k } \right) , } } \\ { { q _ { \mu } = \displaystyle \frac { \omega _ { q } } { 1 + w \bar { w } } \left( 1 + w \bar { w } , w + \bar { w } , i ( \bar { w } - w ) , 1 - w \bar { w } \right) , } } \end{array}
$$

and similarly the polarization tensors as

$$
\epsilon _ { \mu } ^ { - } ( q ) = { \frac { 1 } { \sqrt { 2 } } } \left( \bar { w } , 1 , - i , - \bar { w } \right) , \qquad \epsilon _ { \mu } ^ { + } ( q ) = { \frac { 1 } { \sqrt { 2 } } } \left( w , 1 , i , - w \right) .
$$

Now we particularize to an outgoing negative (positive)-helicity soft gluon for the leading (sub-leading) soft theorem. The corresponding leading and sub-leading pieces of the soft gluon theorems can be rewritten as

$$
\operatorname * { l i m } _ { \omega _ { q } \to 0 } \langle \mathrm { o u t } | \omega _ { q } \mathfrak { a } _ { + } ^ { a } ( q ) | \mathrm { i n } \rangle _ { i _ { 1 } \cdots i _ { n } } = \frac { 1 + | w | ^ { 2 } } { \sqrt { 2 } } \sum _ { k = 1 } ^ { n } \frac { ( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } } { w - w _ { k } } \langle \mathrm { o u t } | \mathrm { i n } \rangle _ { i _ { 1 } \cdots j _ { k } \cdots i _ { n } } ,
$$

$$
\begin{array} { l } { \displaystyle \operatorname* { l i m } _ { \varkappa _ { q } \to 0 } \partial _ { \omega _ { q } } \langle \mathrm { o u t } | \omega _ { q } \mathfrak { a } _ { - } ^ { a } ( q ) | \mathrm { i n } \rangle _ { i _ { 1 } \cdots i _ { n } } = } \\ { \displaystyle \qquad \sum _ { k = 1 } ^ { n } \frac { ( T _ { k } ^ { a } ) _ { i _ { k } j _ { k } } } { \sqrt { 2 } } \bigg ( \frac { 1 + w \bar { w } _ { k } } { \bar { w } - \bar { w } _ { k } } \partial _ { \omega _ { k } } + \frac { ( 1 + | w _ { k } | ^ { 2 } ) ( w - w _ { k } ) } { \omega _ { k } ( \bar { w } - \bar { w } _ { k } ) } \partial _ { w _ { k } } \bigg ) \langle \mathrm { o u t } | \mathrm { i n } \rangle _ { i _ { 1 } \cdots j _ { k } \cdots i _ { n } } . } \end{array}
$$

We have only paid attention to vertices where a gluon couples to two scalars for the sub-leading soft theorem when deriving (93), so that the angular momentum operator is just

$$
J _ { k } ^ { \mu \nu } = i \left( { p _ { k } } ^ { \mu } { \frac \partial { \partial p _ { k \nu } } } - { p _ { k } } ^ { \nu } { \frac \partial { \partial p _ { k \mu } } } \right) ,
$$

without extra helicity terms.

# References

[1] L. J. Dixon, “Scattering amplitudes: the most perfect microscopic structures in the universe,” J. Phys. A44 (2011) 454001, arXiv:1105.0771 [hep-th].   
[2] R. Britto, F. Cachazo,and B. Feng,“New recursion relations for tree amplitudes of gluons,” Nucl. Phys. B715 (2005) 499-522, arXiv:hep-th/0412308 [hep-th].   
[3] R. Britto, F. Cachazo, B. Feng,and E. Witten,“Direct proof of tree-level recursion relation in Yang-Mills theory,” Phys. Rev. Lett. 94 (2005) 181602, arXiv:hep-th/0501052 [hep-th].   
[4] F. Cachazo, S. He, and E. Y. Yuan,“Scattering of Massless Particles in Arbitrary Dimensions,” Phys. Rev. Lett.113 no.17, (2014) 171601, arXiv:1307.2199 [hep-th].   
[5] A. Strominger， “Asymptotic Symmetries of Yang-Mills Theory," JHEP07 (2014) 151,arXiv:1308.0589 [hep-th].   
[6] A. Strominger, “On BMS Invariance of Gravitational Scattering," JHEP07(2014) 152,arXiv:1312.2229 [hep-th].   
[7] F. Cachazo and A. Strominger,“Evidence for a New Soft Graviton Theorem,” arXiv:1404.4091 [hep-th].   
[8] E. Casali, “Soft sub-leading divergences in Yang-Mills amplitudes," JHEP08 (2014) 077,arXiv:1404.5551 [hep-th].   
[9] B. U. W. Schwab and A. Volovich,“Subleading Soft Theorem in Arbitrary Dimensions from Scattering Equations," Phys. Rev. Lett.113 no.10, (2014) 101601,arXiv:1404.7749 [hep-th].   
[10] C. Kalousios and F. Rojas,“Next to subleading soft-graviton theorem in arbitrary dimensions,” JHEP01 (2015)107,arXiv:1407.5982 [hep-th].   
[11] M. Zlotnikov,“Sub-sub-leading soft-graviton theorem in arbitrary dimension," JHEP10 (2014) 148,arXiv:1407.5936 [hep-th].   
[12] T. He, V. Lysov,P. Mitra, and A. Strominger,“BMS supertranslations and Weinberg's soft graviton theorem,” JHEP 05 (2015） 151, arXiv:1401.7026 [hep-th].   
[13] T. He, P. Mitra,A. P. Porfyriadis,and A. Strominger,“New Symmetries of Massless QED,” JHEP 10 (2014) 112,arXiv:1407.3789 [hep-th].   
[14] D. Kapec,V. Lysov, and A. Strominger,“Asymptotic Symmetries of Massless QED in Even Dimensions,” arXiv:1412.2763 [hep-th].   
[15] A. Mohd,“A note on asymptotic symmetries and soft-photon theorem," JHEP 02 (2015) 060,arXiv:1412.5365 [hep-th].   
[16] D.Kapec, V. Lysov, S. Pasterski, and A. Strominger,“Higher-Dimensional Supertranslations and Weinberg's Soft Graviton Theorem," arXiv:1502.07644 [gr-qc].   
[17] M. Campiglia and A. Laddha,“Asymptotic symmetries of QED and Weinber's soft photon theorem,” JHEP 07 (2015) 115,arXiv:1505.05346 [hep-th].   
[18] D. Kapec, M. Pate, and A. Strominger,“New Symmetries of QED," arXiv:1506.02906 [hep-th].   
[19] M. Campiglia and A. Laddha,“Asymptotic symmetries of gravity and soft theorems for massive particles,” JHEP 12 (2015) 094, arXiv:1509.01406 [hep-th].   
[20] E. Conde and P. Mao,“Remarks on Asymptotic Symmetries and the Sub-leading Soft Photon Theorem,” Phys. Rev. D95 no. 2,(2017) 021701, arXiv:1605.09731 [hep-th].   
[21] E. Conde and P. Mao,“BMS Supertranslations and Not So Soft Gravitons,” JHEP 05 (2017) 060,arXiv:1612.08294 [hep-th].   
[22] A. Campoleoni, D. Francia, and C. Heissenberg,“On higher-spin supertranslations and superrotations,” JHEP 05 (2017） 120, arXiv:1703.01351 [hep-th].   
[23] D. Kapec, V. Lysov, S. Pasterski, and A. Strominger,“Semiclassical Virasoro symmetry of the quantum gravity $\boldsymbol { S }$ -matrix,” JHEP 08 (2014) 058, arXiv:1406.3312 [hep-th].   
[24] V. Lysov, S. Pasterski, and A. Strominger,“Low's Subleading Soft Theorem as a Symmetry of QED,” Phys. Rev. Lett.113 no. 11, (2014) 111601, arXiv:1407.3814 [hep-th].   
[25] M. Campiglia and A. Laddha,“Asymptotic symmetries and subleading soft graviton theorem,” Phys.Rev.D90 no.12,(2014) 124028, arXiv:1408.2228 [hep-th].   
[26] M. Campiglia and A. Laddha,“New symmetries for the Gravitational S-matrix," JHEP04 (2015) 076,arXiv:1502.02318 [hep-th].   
[27] T.He, P. Mitra, and A. Strominger,“2D Kac-Moody Symmetry of 4D Yang-Mills Theory,” JHEP10 (2016) 137,arXiv:1503.02663 [hep-th].   
[28] T.T. Dumitrescu, T. He, P. Mitra,and A. Strominger,“Infinite-Dimensional Fermionic Symmetry in Supersymmetric Gauge Theories," arXiv:1511.07429 [hep-th].   
[29] V. Lysov,“Asymptotic Fermionic Symmetry From Soft Gravitino Theorem,” arXiv:1512.03015 [hep-th].   
[30] M. Campiglia and A. Laddha,“Sub-subleading soft gravitons: New symmetries of quantum gravity?,” Phys. Lett. B764 (2017) 218-221, arXiv:1605.09094 [gr-qc].   
[31] M. Campiglia and A. Laddha,“Subleading soft photons and large gauge transformations,” JHEP11 (2016) 012,arXiv:1605.09677 [hep-th].   
[32] M. Campiglia and A. Laddha,“Sub-subleading soft gravitons and large diffeomorphisms,” JHEP01 (2017) 036,arXiv:1608.00685 [gr-qc].   
[33] D. Kapec, P. Mitra, A.-M. Raclariu, and A. Strominger,“A 2D Stress Tensor for 4D Gravity,” arXiv:1609.00282 [hep-th].   
[34] M. Campiglia, L. Coito, and S. Mizera,“Can scalars have asymptotic symmetries?,” arXiv:1703.07885 [hep-th].   
[35] F. A. Berends and W. T. Giele,“Multiple Soft Gluon Radiation in Parton Processes,” Nucl. Phys. B313(1989) 595-633.   
[36] M. Bianchi, S. He, Y.-t. Huang,and C. Wen,“More on Soft Theorems: Trees, Loops and Strings,” Phys. Rev. D92 no. 6, (2015) 065022, arXiv:1406.5155 [hep-th].   
[37] Z.-W. Liu,“Soft theorems in maximally supersymmetric theories," Eur. Phys. J. C75 no.3, (2015) 105,arXiv:1410.1616 [hep-th].   
[38]G. Barnich and P.-H. Lambert,“Einstein-Yang-Mills theory: Asymptotic symmetries,” Phys. Rev. D88 (2013) 103006,arXiv:1310.2698 [hep-th].   
[39] L. F. Abbott and S. Deser,“Charge Definition in Nonabelian Gauge Theories,” Phys. Lett.B116 (1982) 259-263.   
[40] G. Barnich and F. Brandt,“Covariant theory of asymptotic symmetries, conservation laws and central charges,” Nucl. Phys. B633(2002) 3-82, arXiv:hep-th/0111246 [hep-th].   
[41] I. M. Anderson and C. G. Torre,“Asymptotic conservation laws in field theory," Phys. Rev. Lett. 77 (1996) 4109-4113, arXiv:hep-th/9608008 [hep-th].   
[42] H. Bondi, M. G. J. van der Burg, and A. W. K. Metzner,“Gravitational waves in general relativity. 7. Waves from axisymmetric isolated systems,” Proc. Roy. Soc. Lond. A269 (1962) 21-52.   
[43] R. K. Sachs,“Gravitational waves in general relativity. 8. Waves in asymptotically fat space-times,” Proc. Roy. Soc. Lond. A270 (1962) 103-126.   
[44] G. Barnich and C. Troessaert,“Aspects of the BMS/CFT correspondence," JHEP05 (2010) 062,arXiv:1001.1541 [hep-th].   
[45] Z. Bern, V. Del Duca,and C. R. Schmidt,“The Infrared behavior of one loop gluon amplitudes at next-to-next-to-leading order," Phys. Lett. B445 (1998) 168-177,arXiv:hep-ph/9810409 [hep-ph].   
[46] Z. Bern, V. Del Duca,W.B. Kilgore,and C. R. Schmidt,“The infrared behavior of one loop QCD amplitudes at next-to-next-to leading order," Phys. Rev. D60 (1999) 116001,arXiv:hep-ph/9903516 [hep-ph].   
[47] D. A. Kosower and P. Uwer,“One loop splitting amplitudes in gauge theory,” Nucl. Phys. B563 (1999) 477-505, arXiv:hep-ph/9903515 [hep-ph].   
[48] D. A. Kosower,“All orders singular emission in gauge theories,” Phys. Rev. Lett. 91 (2003) 061602,arXiv:hep-ph/0301069 [hep-ph].   
[49] Z. Bern, S. Davies,and J. Nohle,“On Loop Corrections to Subleading Soft Behavior of Gluons and Gravitons,” Phys. Rev. D90 no. 8, (2014) 085015, arXiv:1405.1015 [hep-th].   
[50] S. He, Y.-t. Huang, and C. Wen,“Loop Corrections to Soft Theorems in Gauge Theories and Gravity,” JHEP 12 (2014) 115,arXiv:1405.1410 [hep-th].   
[51] Z. Bern, S. Davies, P. Di Vecchia,and J. Nohle,“Low-Energy Behavior of Gluons and Gravitons from Gauge Invariance,” Phys. Rev. D90 no. 8, (2014) 084035, arXiv:1406.6987 [hep-th].   
[52] F. Cachazo, S. He, and E. Y. Yuan,“New Double Soft Emission Theorems,” Phys. Rev.D92 no.6,(2015) 065030,arXiv:1503.04816 [hep-th].   
[53] N. Arkani-Hamed, F. Cachazo, and J. Kaplan,“What is the Simplest Quantum Field Theory?,” JHEP 09 (2010) 016, arXiv:0808.1446 [hep-th].   
[54] I. Anderson， The variational bicomplex. Formal Geometry and Mathematical Physics, Department of Mathematics, Utah State University technical report, unpublished,1989.   
[55] C. W. Misner, K. S. Thorne, and J. A. Wheeler, Gravitation. W. H. Freeman, San Francisco, 1973.   
[56] G. Barnich,“Boundary charges in gauge theories: Using Stokes theorem in the bulk,” Class. Quant. Grav. 20 (2003) 3685-3698, arXiv:hep-th/0301039 [hep-th].   
[57] G. Barnich,“Private communication, 2015,".   
[58] R.M. Wald and A. Zoupas,“A General definition of ‘conserved quantities’ in general relativity and other theories of gravity,” Phys. Rev. D61 (2000) 084027, arXiv:gr-qc/9911095 [gr-qc].   
[59] G. Barnich and C. Troessaert,“BMS charge algebra,” JHEP 12 (2011) 105, arXiv:1106.0213 [hep-th].   
[60] G. Barnich and C. Troessaert,“Comments on holographic current algebras and asymptotically flat four dimensional spacetimes at null infinity," JHEP11 (2013) 003,arXiv:1309.0794 [hep-th].   
[61] G. Barnich, P.-H. Lambert, and P. Mao,“Three-dimensional asymptotically flat Einstein-Maxwell theory,” Class. Quant. Grav. 32 no. 24, (2015) 245001, arXiv:1503.00856 [gr-qc].   
[62] G. Barnich, P. Mao,and R. Ruzziconi, “Conserved currents in the Cartan formulation of general relativity,” 2016. arXiv:1611.01777 [gr-qc]. https://inspirehep.net/record/1495975/files/arXiv:1611.01777.pdf.