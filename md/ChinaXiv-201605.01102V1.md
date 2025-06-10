# Casimir Energy, Holographic Dark Energy and Electromagnetic Metamaterial Mimicking de Sitter Space

Miao Li,\* Rong-Xin Miao,t and Yi Pangt Kavli Institute for Theoretical Physics, Key Laboratory of Frontiers in Theoretical Physics, Institute of Theoretical Physics， Chinese Academy of Sciences, Beijing 100190， People's Republic of China, Interdisciplinary Center for Theoretical Study, University of Science and Technology of China， Hefei， Anhui 230026, China

# Abstract

We compute the Casimir energy of the photon field in a static de Sitter space and find it to be proportional to the size of the horizon,the same form of the holographic dark energy. We suggest to make metamaterials to mimic static de Sitter space in laboratory and measure the predicted Casimir energy.

# I. INTRODUCTION

The dark energy problem is one of the central unsolved problems in fundamental physics and cosmology. Many phenomenological models have been proposed since the discovery of the accelerated expanding universe [1], including the so-called holographic dark energy model [2].

The value of the observed dark energy is comparable to the critical energy density which in the Planck unit is proportional to the Hubble constant squared. Motivated by this fact, the holographic dark energy model presumes that the energy density is inversely proportional to the square of the size of some cosmological horizon, and the choice of the horizon, for the model to work, is proposed in [2] to be the event horizon. In a pure de Sitter space in which dark energy is a constant, one can choose a static coordinate system, thus the total energy of dark energy can be defined. The total energy in the Planck unit is proportional to the size of the horizon,unlike the usual result for the Casimir energy in the finite cavity in a fat spacetime, the latter is inversely proportional to the size of the cavity. Nevertheless, there has been no attempt to computing the Casimir energy in a static de Sitter space seriously, to the best of our knowledge.

In this paper, we take the assumption that the UV divergent zero-point energy is somehow regularized to vanish due to some unknown mechanism, therefore the observed dark energy is solely due to the residual zero-point energy which is known to be the Casimir energy. However，we are faced with the challenge that why the Casimir energy is not inversely proportional to the size of the cavity.

Motivated by the recent development in electromagnetic metamaterials,we will first try to convert the de Sitter space to a cavity of optical metamaterial, this is doable at least for the photon field. We shall find that the cavity is drastically different from a usual one in that the permittivity and permeability parameters both have divergent components tangent to the boundary, indeed these components are divergent near the boundary which is derived from the horizon of the de Sitter space. This fact encourages us to guess that the Casimir energy as a function of the size of the cavity behaves differently from that in a normal cavity. We carry out the calculation for the photon field and find that indeed after regularization there is still a divergent piece proportional to the size of the cavity， with the divergence cut-off by a UV scale. This UV scale in the metamaterials can be some intrinsic microscopic scale,and becomes the Planck scale when transformed back to the de Sitter space. Thus, we find a piece of theoretical evidence for the holographic dark energy model. We propose to do some laboratory experiment to verify our result about the Casimir energy. This kind of experiment is interesting in two aspects. First,it will mimic cosmology, second, it will detect a unusual Casimir energy inversely proportional to some microscopic cut-off.

There are two different designs of metamaterials, the first is based on the static de Siter space with the usual coordinate system, the second is based on the static de Sitter where the radial coordinate is replaced by the proper distance. The Casimir energy in the second metamaterial assumes the precisely same form as in the de Sitter space, which is proportional to the size of the material thus is enhanced to be easily detectable.

In the next section, we present the Maxwel equations in a curved spacetime. We discuss how to transform the de Sitter space into a cavity of metamaterial in sect.3 and compute the Casimir energy in sect.4,and discuss its form in a metamaterial filled cavity in sect.5. We conclude in sect.6.

# II.MAXWELL EQUATION IN STATIC CURVED SPACE TIME

We start with Maxwell equations in a curved spacetime

$$
\partial _ { [ \mu } F _ { \nu \lambda ] } = 0 , \quad \partial _ { \mu } H ^ { \mu \nu } = 0 ,
$$

where the first equation is the Bianchi identity satisfied by field strength $F _ { \mu \nu }$ ，and $H ^ { u v }$ is defined by

$$
H ^ { \mu \nu } = \sqrt { - g } F ^ { \mu \nu } = \sqrt { - g } g ^ { \mu \alpha } g ^ { \nu \beta } F _ { \alpha \beta } .
$$

The electric field $E _ { i }$ and magnetic field $H _ { i }$ are related to $F _ { \mu \nu }$ as

$$
E _ { i } = F _ { 0 i } , H _ { i } = - \frac { \epsilon _ { i j k } } { 2 } H ^ { j k } ,
$$

In above equations, the Levi-Civita symbol $\epsilon ^ { i j k }$ is $+ 1$ for all even permutations of $\epsilon ^ { 1 2 3 }$ It should be noted that $E _ { i }$ and $H _ { i }$ are spatial vectors.

Especially, when the space time is static, we can express Eq. (1) in a spatial covariant form with respect to optical metric $\gamma ^ { i j }$ defined by

$$
\gamma ^ { i j } = - g _ { 0 0 } g ^ { i j } ,
$$

where $\gamma ^ { i j }$ is the usually called optic metric.

At this stage, Maxwell equations Eq.(1) can be rewritten as

$$
\nabla _ { i } E ^ { i } = 0 , \quad \nabla _ { i } H ^ { i } = 0 ,
$$

$$
\partial _ { t } E ^ { i } - \frac { \epsilon ^ { i j k } } { \sqrt { \gamma } } \partial _ { j } H _ { k } = 0 , \partial _ { t } H ^ { i } + \frac { \epsilon ^ { i j k } } { \sqrt { \gamma } } \partial _ { j } E _ { k } = 0 ,
$$

where $\nabla _ { i }$ denotes the covariant derivative with respect to $\gamma ^ { i j }$ , and all the indices are raised and lowered by $\gamma ^ { i j }$ ：

Eq.(6) can be rewritten in the following compact form

$$
i \partial _ { t } \left( \begin{array} { c } { E } \\ { H } \end{array} \right) = L \left( \begin{array} { c } { E } \\ { H } \end{array} \right) ,
$$

where the operator $L$ is given by

$$
L = i \left( \begin{array} { c c } { { 0 } } & { { \gamma _ { i j } \frac { \epsilon ^ { j k l } } { \sqrt { \gamma } } \partial _ { k } } } \\ { { - \gamma _ { i j } \frac { \epsilon ^ { j k l } } { \sqrt { \gamma } } \partial _ { k } } } & { { 0 } } \end{array} \right) .
$$

If we define

$$
\phi = \left( { E \atop H } \right) ,
$$

the operator $L$ is Hermitian in terms of the following inner product

$$
< \phi _ { 1 } , \phi _ { 2 } > = \int d ^ { 3 } x \sqrt { \gamma } \phi _ { 1 } ^ { + } \phi _ { 2 } = \int d ^ { 3 } x ( E _ { 1 i } \varepsilon ^ { i j } E _ { 2 j } + H _ { 1 i } \mu ^ { i j } H _ { 2 j } ) ,
$$

where

$$
\varepsilon ^ { i j } = \mu ^ { i j } = \sqrt { \gamma } \gamma ^ { i j } , \qquad \gamma = \operatorname * { d e t } ( \gamma _ { i j } ) .
$$

We will see that $\epsilon$ and $\mu$ have a physical interpretation in terms of metamaterials in the next section.

To make $L$ Hermitian under the inner product (1O) (which is the energy functional as it should be for $\phi _ { 1 } = \phi _ { 2 }$ )，we need to specify boundary conditions if there is a boundary. We find the following boundary conditions

$$
\sqrt { \gamma } ( E _ { 1 } \times H _ { 2 } - H _ { 1 } \times E _ { 2 } ) ^ { i } n _ { i } | _ { \partial { \cal M } } = 0
$$

where $n _ { i }$ is the normal vector of boundary and $\begin{array} { r } { ( E \times H ) ^ { i } = \frac { 1 } { \sqrt { \gamma } } \epsilon ^ { i j k } E _ { j } H _ { k } } \end{array}$ . Then the hermiticity of $L$ is guaranteed

$$
< \phi _ { 1 } , L \phi _ { 2 } > = < L \phi _ { 1 } , \phi _ { 2 } > .
$$

By acting $\partial _ { t }$ and $L$ again on the two sides of Eq.(7) respectively, we obtain the equations of electric and magnetic field

$$
\begin{array} { r } { - \partial _ { t } ^ { 2 } E _ { i } = ( \nabla ^ { j } \nabla _ { i } - \nabla ^ { 2 } \delta _ { i } ^ { j } ) E _ { j } , } \\ { - \partial _ { t } ^ { 2 } H _ { i } = ( \nabla ^ { j } \nabla _ { i } - \nabla ^ { 2 } \delta _ { i } ^ { j } ) H _ { j } , } \end{array}
$$

we read off the operator corresponding to $L ^ { 2 }$ from the above equations

$$
D \equiv L ^ { 2 } = \left( \begin{array} { c c } { { \nabla ^ { j } \nabla _ { i } - \nabla ^ { 2 } \delta _ { i } ^ { j } } } & { { 0 } } \\ { { 0 } } & { { \nabla ^ { j } \nabla _ { i } - \nabla ^ { 2 } \delta _ { i } ^ { j } } } \end{array} \right) .
$$

An eigenvalue of $D$ is a nonnegative real number due to the Hermiticity of $L$ 业

With Gauss law, we get two sets of equations taking the same form

$$
- \partial _ { t } ^ { 2 } V _ { i } = D _ { i } ^ { j } V _ { j } = ( \nabla ^ { j } \nabla _ { i } - \nabla ^ { 2 } \delta _ { i } ^ { j } ) V _ { j } , \qquad \nabla ^ { i } V _ { i } = 0 ,
$$

where $V _ { i }$ can be $E _ { i }$ or $H _ { i }$

# III.MIMICKING DE SITTER WITH METAMATERIALS

Recently, the analogy between static curved space and inhomogeneous medium has been studied in [3-6]. It is proved in [7] that in geometric optic limit, light propagates along the same path in electromagnetic material and in static curved spacetime as long as the optic metric $\gamma _ { i j }$ is related to permittivity and permeability by Eq. (11).

One can see the analogy more clearly as follows. To solve Maxwell equation in inhomogeneous medium conveniently, the often used quantities are electric displacement field $D ^ { i }$ and magnetic induction field $B ^ { i }$ defined as

$$
D ^ { i } = \varepsilon ^ { i j } E _ { j } , B ^ { i } = \mu ^ { i j } H _ { j } ,
$$

where $\varepsilon ^ { i j }$ and $\mu ^ { i j }$ are permittivity and permeability specifying the electromagnetic properties of the medium. In terms of the newly defined quantities $D ^ { i }$ and $H ^ { \ i }$ ， Maxwell equations in inhomogeneous medium and Cartesian coordinate system are

$$
\partial _ { i } D ^ { i } = 0 , \quad \partial _ { i } B ^ { i } = 0 ,
$$

$$
\partial _ { t } D ^ { i } - \epsilon ^ { i j k } \partial _ { j } H _ { k } = 0 , \partial _ { t } B ^ { i } + \epsilon ^ { i j k } \partial _ { j } E _ { k } = 0 .
$$

Since under spatial coordinate transformation $\varepsilon ^ { i j }$ and $\mu ^ { i j }$ are tensor density with weight -1, we can define two tensors using $\varepsilon ^ { i j }$ and $\mu ^ { i j }$ by

$$
\tilde { \gamma } ^ { i j } = { \frac { \varepsilon ^ { i j } } { \operatorname* { d e t } ( \varepsilon ^ { i j } ) } } , \qquad \tilde { \tilde { \gamma } } ^ { i j } = { \frac { \mu ^ { i j } } { \operatorname* { d e t } ( \mu ^ { i j } ) } } .
$$

For electromaganetic material with equal $\varepsilon ^ { i j }$ and $\mu ^ { i j }$ ， $\tilde { \gamma } ^ { i j } = \tilde { \tilde { \gamma } } ^ { i j }$ .In this case, rewriting Eqs.(18) and (19) in terms of $\tilde { \gamma } ^ { i j }$ ， $E _ { i }$ and $H _ { i }$ , we find that Maxwell equations in the metameterial takes the same form as Eq.(5) and Eq.(6) if $\tilde { \gamma } ^ { i j }$ is identified with the optic metric $\gamma ^ { i j }$

By this analogy, one can design electromagnetic metamaterial corresponding a given metric. Along this line, theoretically, a new material called electromagnetic cloak was conceived [3-6]. All parallel bundles of incident rays are bent around some region covered by electromagnetic cloak and recombined in precisely the same direction as they entered the medium; Experimentally, a new class of electromagnetic materials are invented [8] which can be designed to have properties mimicking novel gravitational efects in Nature. Thus it is now conceivable that a material can be constructed whose permittivity and permeability values may be designed to vary arbitrarily.

With the static de Sitter space

$$
d s ^ { 2 } = - ( 1 - \frac { r ^ { 2 } } { L ^ { 2 } } ) d ^ { 2 } t + ( 1 - \frac { r ^ { 2 } } { L ^ { 2 } } ) ^ { - 1 } d ^ { 2 } r + r ^ { 2 } d ^ { 2 } \Omega
$$

The permittivity and permeability are

$$
\varepsilon ^ { r r } = \mu ^ { r r } = r ^ { 2 } \sin \theta , \varepsilon ^ { \theta \theta } = \mu ^ { \theta \theta } = { \frac { \sin \theta } { 1 - { \frac { r ^ { 2 } } { L ^ { 2 } } } } } , \varepsilon ^ { \varphi \varphi } = \mu ^ { \varphi \varphi } = { \frac { 1 } { \left( 1 - { \frac { r ^ { 2 } } { L ^ { 2 } } } \right) \sin \theta } } ,
$$

where $( r , \theta , \varphi )$ stands for spherical coordinate. In terms of Cartesian coordinate, the permittivity and permeability are

$$
\varepsilon ^ { i j } = \mu ^ { i j } = \frac { 1 } { 1 - r ^ { 2 } / L ^ { 2 } } ( \delta ^ { i j } - \frac { x ^ { i } x ^ { j } } { L ^ { 2 } } ) .
$$

The metamaterial can always be redesigned by making a coordinate mapping [3, 5]. By making the following mapping

$$
r  \tilde { r } = L \arcsin ( r / L ) .
$$

Then the permittivity and permeability becomes

$$
= \mu ^ { \tilde { r } \tilde { r } } = L ^ { 2 } \frac { \sin ^ { 2 } ( \tilde { r } / L ) } { \cos ( \tilde { r } / L ) } \sin \theta , \quad \varepsilon ^ { \theta \theta } = \mu ^ { \theta \theta } = \frac { \sin \theta } { \cos ( \tilde { r } / L ) } , \quad \varepsilon ^ { \varphi \varphi } = \mu ^ { \varphi \varphi } = \frac { 1 } { \cos ( \tilde { r } / L ) \sin \theta } ,
$$

where $( \tilde { r } , \theta , \varphi )$ denotes the spherical coordinate. In terms of the Cartesian coordinate

$$
\varepsilon ^ { i j } = \mu ^ { i j } = \frac { 1 } { \cos ( \tilde { r } / L ) } ( \delta ^ { i j } - ( \frac { L ^ { 2 } } { \tilde { r } ^ { 2 } } \sin ^ { 2 } ( \tilde { r } / L ) - 1 ) \ \frac { x ^ { i } x ^ { j } } { \tilde { r } ^ { 2 } } ) .
$$

These two kinds of metamaterial mimicking the same de Sitter space， since they are related by a spatial coordinate transformation. However, the different permittivity and permeability will lead to distinct physical phenomenon in laboratory due to their different physical composition.

The event horizon at $r \ = \ L$ or $\tilde { r } = \pi L / 2$ now becomes the boundary of a cavity of metamaterial. As we shal see shortly, to metamaterial with $\epsilon$ and $\mu$ as in Eq.(23), the leading term in the Casimir energy is a constant inversely proportional to certain microscopic length scale; while to metamaterial with $\epsilon$ and $\mu$ as in Eq.(26)， the leading term in the Casimir energy in this cavity is proportional to $L$ , we encourage experimenters to design such cavity to measure the Casimir energy, the result will have important implication for dark energy.

# IV. CASIMIR ENERGY OF ELECTROMAGNETIC FIELD IN STATIC DE SITTERSPACE

In Maxwell theory, the electric sector and magnetic sector contribute the same amount to the Casimir energy, as the equations governing them are identical. In the following, we will focus on the electric sector.

Consider the solution of electric field taking the form

$$
E _ { i } ( t , x ) = e ^ { i \omega t } E _ { i } ( x ) ,
$$

where the absolute value of $\omega$ should be interpretated as the energy with respect to time （204号 $t$ . Upon quantization, the eigenvalue $\omega$ contributes to the zero-point energy. The Casimir energy of electric field is the infinite sum

$$
E _ { \mathrm { C a s i m i r } } = { \frac { 1 } { 2 } } \sum _ { \omega } | \omega | .
$$

Substitutting Eq.(27) into Eq.(16) we obtain the eigen equation of operator $D$ with eigenvalue $\omega ^ { 2 }$ （204号

$$
D _ { i } ^ { j } E _ { j } = \omega ^ { 2 } E _ { i } .
$$

Then in the framework of zeta function regularization, the problem of computing the Casimir energy is converted into the problem of computing the heat kernel of $\boldsymbol { D }$ , the Casimir Energy can be extracted from the heat kernel as follows [9]:

$$
E _ { \mathrm { C a s i m i r } } \equiv \operatorname* { l i m } _ { \epsilon  0 } \frac { 1 } { 2 } \{ E _ { \mathrm { r e g } } ( + \epsilon ) + E _ { \mathrm { r e g } } ( - \epsilon ) \} ,
$$

where

$$
E _ { \mathrm { r e g } } ( \epsilon ) = \frac { \mu } { 2 } \zeta ( - \frac { 1 } { 2 } + \epsilon ) ,
$$

with the zeta function associated with $\boldsymbol { D }$ defined by

$$
\zeta ( s ) = \frac { \mu ^ { 2 s } } { \Gamma ( s ) } \int _ { 0 } ^ { \infty } d t ~ t ^ { s - 1 } \mathrm { t r } ^ { \prime } ( e ^ { - t D } ) .
$$

In above expressions, a scale $^ { \ast } \mu ^ { \prime \prime }$ is introduced to keep the zeta function dimensionless; while the prime in $\mathrm { t r } ^ { ' }$ indicates that zero eigenvalues are not included. In coordinate representation, $\langle x | e ^ { - t D } | x ^ { ' } \rangle$ is called the heat kernel denoted by $K ( t , x , x ^ { ' } )$ satisfying the heat equation related to $D$ as

$$
\partial _ { t } K ( t , x , x ^ { ' } ) + D K ( t , x , x ^ { ' } ) = 0 .
$$

To solve this equation, we need to specify appropriate boundary conditions.

At this moment, with above preparation, we can calculate the Casimir energy of electromagnetic field in static de Sitter space time. This space time is described by the following metric

$$
d s ^ { 2 } = - ( 1 - \frac { r ^ { 2 } } { L ^ { 2 } } ) d ^ { 2 } t + ( 1 - \frac { r ^ { 2 } } { L ^ { 2 } } ) ^ { - 1 } d ^ { 2 } r + r ^ { 2 } d ^ { 2 } \Omega
$$

where $L$ is the de Sitter radius. However, the effective metric relevant to our calculation is the optic metric $\gamma ^ { i j }$ appearing in the Maxwell equation with the following form

$$
d s _ { 3 } ^ { 2 } = \gamma _ { i j } d x ^ { i } d x ^ { j } = ( 1 - \frac { r ^ { 2 } } { L ^ { 2 } } ) ^ { - 1 } ( ( 1 - \frac { r ^ { 2 } } { L ^ { 2 } } ) ^ { - 1 } d ^ { 2 } r + r ^ { 2 } d ^ { 2 } \Omega ) ,
$$

where the lower index $^ { \circ \mathfrak { s } ^ { \mathfrak { s } } }$ is used to emphasize that this metric is three dimensional. An interesting observation is that $\gamma _ { i j }$ actually describes an anti de Sitter space. One can see this clearly by performing the following transformation on $r$ coordinates:

$$
r = \frac { \tilde { r } } { \sqrt { 1 + \tilde { r } ^ { 2 } / L ^ { 2 } } } .
$$

In terms of $\tilde { r }$ ，

$$
d s _ { 3 } ^ { 2 } = ( 1 + \frac { \tilde { r } ^ { 2 } } { L ^ { 2 } } ) ^ { - 1 } d ^ { 2 } \tilde { r } + \tilde { r } ^ { 2 } d ^ { 2 } \Omega .
$$

In the case of static de Sitter space time,the boundary condition Eq.(12) for retaining the Hermiticity of operator $L$ in Eq.(15) becomes

$$
( E _ { 1 \theta } H _ { 2 \phi } - H _ { 1 \theta } E _ { 2 \phi } ) | _ { r = L - \delta } = 0 ,
$$

where the boundary is chosen at $r = L - \delta$ and $\delta$ is a cut off to avoid the divergence of energy and its meaning will become clear later (see later for an explicit calculation of energy). Thus to keep Hermiticity, we choose

$$
E _ { \theta } | _ { r = L - \delta } = E _ { \varphi } | _ { r = L - \delta } = 0
$$

as the boundary condition. It is similar to the case of electromagnetic field in a spherical conductor shell. Therefore in the following,we will concentrate on the problem of finding the heat kernel corresponding to $D$ defined with respect to $\gamma _ { i j }$ in Eq.(35) and restricted to the space spanned by its eigenfunctions satisfying the Gauss law and boundary conditions.

$$
\nabla ^ { i } E _ { i } = 0 , \qquad E _ { \theta } | _ { r = L - \delta } = E _ { \varphi } | _ { r = L - \delta } = 0 .
$$

Usually, in a curved manifold the heat equation Eq.(33) is hard to solve completely. However, the trace of the heat kernel has the following asymptotic expansion for small $t$ ， especially in three dimensions as

$$
\mathrm { t r } ^ { \prime } ( e ^ { - t D } ) = ( { \frac { 1 } { 4 \pi t } } ) ^ { 3 / 2 } \{ \ \sum _ { 0 } ^ { N } ( \int _ { \cal M } a _ { n } t ^ { n } + \int _ { \partial { \cal M } } b _ { n } t ^ { n } ) + o ( t ^ { N } ) \ \} ,
$$

where $a _ { n }$ are bulk terms independent of boundary condition， composed by polynomial of Riemann tensor, Ricci tensor, Ricci scalar, and their covariant derivatives; $b _ { n }$ are boundary terms comprised of the curvature, second fundamental form and their derivatives on the boundary. The sum runs over half-integers, but $a _ { n }$ vanishes for half-odd-integers. Above asymptotic expansion implies that $\zeta ( s )$ has a pole structure [9]:

$$
\zeta ( s ) = { \frac { \mu ^ { 2 s } } { \Gamma ( s ) ( 4 \pi ) ^ { \frac { 3 } { 2 } } } } \bigl \{ \sum _ { n = 0 } ^ { \infty } { \frac { a _ { n } + b _ { n } } { s + n - { \frac { 3 } { 2 } } } } + f ( s ) \bigr \} ,
$$

where $f ( s )$ is an entire analytic function of $s$ , but in general, one has little information about it [9]. In the previous version of this work,we calculate the Casimir energy with above formulas. It is found that the leading term comes from a surface integral on the boundary horizon. Based on this expression, one may think that the Casimir energy is localized near the boundary horizon,but this may be a misunderstanding.For instance,in the frame work of heat kernel expansion, the Casimir energy between two infinite conductor plane in flat space will turn up as a boundary term depending on the permittivity and permeability of the conductor appearing to be localized on the boundary. However, L. Ford's result [10] shows that in this case the Casimir energy distributes homogeneously between the two conductor planes.

To avoid this misunderstanding, We willseak for a compact expression for the heat kernel. It is recalled that the optical metric describes an Euclidean AdS $^ 3$ space and the heat kernel defined with respect to it can be solved by utilizing Harmonic analysis [11]. To vector field the corresponding heat kernel satisfying the transverse condition and vanishing at the AdS $_ 3$ boundary was given by [12] (In our convention, the AdS boundary corresponds to $r = L$ （204号 $_ 3$ or $\tilde { r } ~ = ~ \infty$ ). From Eq. (40),it is obvious that the result of [12] amounts to the $\delta  0$ （20 limit of the heat kernel in our case. In other words, we can use the result of [12] as a good approximation to the heat kernel sought by us up to the order $\delta / L$ . Based on that result we write down the contracted coincident limit of the heat kernel as

$$
\gamma ^ { i j } K _ { i j } ( x , x , t ) = \frac { 2 } { ( 4 \pi t ) ^ { \frac { 3 } { 2 } } } ( 1 + 2 \frac { t } { L ^ { 2 } } ) e ^ { - t / L ^ { 2 } } + o ( \delta / L ) .
$$

With above result, $\mathrm { t r } ^ { \prime } ( \mathrm { e } ^ { - \mathrm { t D } } )$ can be evaluate by

$$
\begin{array} { l } { { \displaystyle { \mathrm { t r } } ^ { \prime } ( { \mathrm { e } } ^ { - { \mathrm { t D } } } ) ~ = ~ \int \sqrt { \gamma } \gamma ^ { i j } K _ { i j } ( x , x , t ) d ^ { 3 } x } } \\ { { ~ = ~ \pi L ^ { 3 } ( \displaystyle \frac { L } { \delta } - \ln ( \displaystyle \frac { 2 L } { \delta } ) ) \times \displaystyle \frac { 2 } { ( 4 \pi t ) ^ { \frac { 3 } { 2 } } } ( 1 + 2 \displaystyle \frac { t } { L ^ { 2 } } ) e ^ { - t / L ^ { 2 } } + o ( 1 ) , } } \end{array}
$$

where $o ( 1 )$ denotes terms $\ll \frac { L } { \delta }$ . Substituting this result into Eqs. (32) and (30),we obtain

$$
E _ { \mathrm { C a s i m i r } } = { \frac { 3 } { 1 6 \pi } } ( \ln \mu ^ { 2 } - \gamma - \psi ( - { \frac { 1 } { 2 } } ) ) ( { \frac { 1 } { \delta } } - { \frac { 1 } { L } } \ln ( { \frac { 2 L } { \delta } } ) ) + o ( 1 / L ) ,
$$

where $\gamma$ is Euler constant and $\psi ( - \textstyle { \frac { 1 } { 2 } } ) = \Gamma ^ { \prime } ( - \textstyle { \frac { 1 } { 2 } } ) / \Gamma ( - \textstyle { \frac { 1 } { 2 } } )$ . In above result, $\delta$ is a coordinate cut off so the physical meaning is not clear. To express it in terms of the physical cut off, we recall that in static de Sitter space the physical distance between $r = L - \delta$ and $r = L$ is given by

$$
\Delta l _ { \mathrm { p h y } } = L \arcsin ( r / L ) | _ { r = L - \delta } ^ { r = L } .
$$

By requiring $\Delta l _ { \mathrm { p h y } }$ to be the Planck length $l _ { \mathrm { p } }$ ， we derive

$$
\delta = L ( 1 - \cos ( \frac { l _ { \mathrm { p } } } { L } ) ) \approx \frac { l _ { \mathrm { p } } ^ { 2 } } { 2 L ^ { 2 } } .
$$

In terms of the physical cut off, the Casimir energy of electromagnetic field is

$$
E _ { \mathrm { C a s i m i r } } = { \frac { 3 } { 8 \pi } } ( \ln \mu ^ { 2 } - \gamma - \psi ( - { \frac { 1 } { 2 } } ) ) ( { \frac { L } { l _ { \mathrm { p } } ^ { 2 } } } - { \frac { 1 } { L } } \ln ( { \frac { 2 L } { l _ { \mathrm { p } } } } ) ) + o ( 1 / L ) ,
$$

where the dominant term proportional to $L / l _ { p } ^ { 2 }$ takes the same form as in the holographic dark energy model [2]. Compared with previous result given in [13,14], it is found that the leading term in the vacuum energy density of static de Sitter space is proportional to （20 $( L ^ { 2 } - r ^ { 2 } ) ^ { - 2 }$ which can also generate a leading term proportional to $L / l _ { \mathrm { p } } ^ { 2 }$ after integrated over the bulk of static de Sitter space. Finally we note that the running renormalization $\ln \mu ^ { 2 }$ can be absorbed into $l _ { \mathrm { p } } ^ { \mathrm { 2 } }$ or be determined experimentally [13].

# V. CASIMIR ENERGY OF ELECTROMAGNETIC FIELD IN ELECTROMAGNETIC METAMATERIAL MIMICKING DESITTER

We have designed two kinds of metamaterial mimicking de Sitter in sect.3. For an electromagnetic metamaterial with $\epsilon$ and $\mu$ taking the value of Eq.(23) in laboratory, coordinate （20 $r$ has been the physical distance between origin and $r$ , since metric measuring the physical distance is flat. In this case, the physical IR cut off is chosen to be $L - d$ , and the Casimir energy is given by

$$
E _ { \mathrm { C a s i m i r } } = { \frac { 3 } { 1 6 \pi } } ( \ln \mu ^ { 2 } - \gamma - \psi ( - { \frac { 1 } { 2 } } ) ) ( { \frac { 1 } { d } } - { \frac { 1 } { L } } \ln ( { \frac { 2 L } { d } } ) ) + o ( 1 / L ) ,
$$

where $d$ is the counterpart of the Planck length in metamaterial, its value depends on the detailed chemical components and structure of the material which should be determined by experiment. We note that when $L \gg d$ ，

$$
E _ { \mathrm { C a s i m i r } } \approx { \frac { 3 } { 1 6 \pi } } ( \ln \mu ^ { 2 } - \gamma - \psi ( - { \frac { 1 } { 2 } } ) ) { \frac { 1 } { d } } .
$$

（204号 $L$ is usuaully much larger than $d$ ， the leading term is much larger than the usual term proportional to $1 / L$ (for example, if $d$ is nanometer,and $L$ is lcm, then the leading term is about $1 0 ^ { 6 }$ times of the second term, the usual term which is almost undetectable).

Alternatively, to metamaterial with $\epsilon$ and $\mu$ taking the form as in Eq.(26), the Casimir energy is

$$
\mathrm { ~  ~ \pi ~ } _ { \mathrm { m i r } } = { \frac { 3 } { 8 \pi } } ( \ln \mu ^ { 2 } - \gamma - \psi ( - { \frac { 1 } { 2 } } ) ) L ^ { - 1 } ( { \frac { \sin ( \tilde { r } / L ) } { \cos ^ { 2 } ( \tilde { r } / L ) } } - { \frac { 1 } { 2 } } \ln ( { \frac { 1 + \sin ( \tilde { r } / L ) } { 1 - \sin ( \tilde { r } / L ) } } ) ) | _ { \tilde { r } = \pi L / 2 - d  \pi L / 2 } + { \frac { 1 } { 2 } } | _ { \mathrm { m i n } } | _ { \tilde { r } = \pi / 2 - d  \pi L / 2 } .
$$

where $\tilde { r }$ stands for physical distance between origin and $\tilde { r }$ in this coordinate system and the size of the cavity is $\pi L / 2$ . So distinguished from the first case, $\pi L / 2 - d$ is the physical IR cut off. $d$ has the same meaning as in previous case. Usually $L \gg d$ （204

$$
E _ { \mathrm { C a s i m i r } } \approx \frac { 3 } { 8 \pi } ( \ln \mu ^ { 2 } - \gamma - \psi ( - \frac { 1 } { 2 } ) ) \frac { L } { d ^ { 2 } } .
$$

It is remarkable that in this metamaterial, the Casimir energy has the same form as in its gravity analogy, except that some microscopic scale $d$ takes the place of Planck scale.

# VI. CONCLUSION

It is a surprising result that the Casimir energy in a de Sitter space is not inversely proportional to the size of the horizon as for a usual finite cavity, rather it is proportional to the size of the horizon. However, if one is to expect that the Casimir energy is dark energy or at least a part of dark energy, this is a desired result,the normal answer in a cavity is just too small to be relevant in cosmology.

Although we only computed the Casimir energy due to the photon field, it is expected that other fields will have the same form of Casimir energy. Since we suggest to construct a cavity of metamaterial to do experiment in laboratory, it is enough to know the form of the photon field Casimir energy, since this is what to be measured in laboratory. However, because the corresponding Casimir force is combined with the elastic force, it seems difficult to measure the predicted Casimir energy immediately.

Aside from the issue of dark energy, to use metamaterials to mimic cosmology by itself is an exciting future direction， we look forward to developments in the future.

# Acknowledgments

We would like to thank Prof. Mo Lin Ge for informing us of the exciting developments in the field of electromagnetic cloaking and metamaterials. This work is mostly motivated by looking for the possibility of studying cosmology in laboratory with metamaterials. This work was supported by the NSFC grant No.10535060/A050207, a NSFC group grant No.10821504 and Ministry of Science and Technology 973 program under grant No.2007CB815401.

[1] A.G. Riess et al., Astron. J.116 (1998) 1009; S. Perlmuttter et al.,APJ 517 (1999) 565.   
[2] Miao Li，“A Model of holographic dark energy ”， Phys.Lett.B 603，1 (2004) [arXiv:hep-th/0403127 ]; Qing-Guo Huang and Miao Li,“The Holographic Dark Energy in a Non-flat Universe”, JCAP 0408 (2004) 013, [arXiv:astro-ph/0404229v3].   
[3] J. B. Pendry, D. Schurig, D. R. Smith, Science 312,1780 (2006).   
[4] D. Schurig, J. J. Mock, B. J. Justice, S. A. Cummer, J.B. Pendry, A. F. Starr, D.R. Smith, Science 314, 977 (2006).   
[5] D. Schurig, J. B. Pendry, D. R. Smith, Opt. Express 14, 9794 (2006).   
[6] U.Leonhardt and T.Philbin,“General Relativity in Electrical Engineering”,New J. Phys.8 (2006) 247 [arXiv:cond-mat/0607418].   
[7] K.Niu, C. Song, M. L. Ge, Optics Express, Vol 17, No 14, 11753,[arXiv:0903.5401]physicsoptics].   
[8] R. A. Shelby, D.R. Smith, S. Shultz, Science 292,77 (2001); A. A. Houck, J. B. Brock, I. L. Chuang, Phys. Rev. Lett.90,137401 (2003); D.R. Smith, J.B. Pendry, M. C.K. Wiltshire, Science 305, 788 (2004); E. Cubukcu, K. Aydin, E. Ozbay, S. Foteinopoulou, C. M. Soukoulis, Nature 423,604 (2003); T. J. Yen et al., Science 303,1494 (2004); S. Linden et al. Science 306,1351 (2004)； X. Zhang et al., [arXiv:0904.3602][physics-optics].   
[9] S. Blau and M. Visser,A. Wipf,“ Zeta Functions and the Casimir Energy”,Nucl. Phys. B310 (1988)163 [arXiv:0906.2817]. D. V. Vassilevich，“ Heat kernel expansion: user's manual", Phys. Rept. 388 :279-360, 2003 [arXiv:hep-th/0306138].   
[10] L. Ford,“Ph.D thesis, Princeton University”,1974.   
[11] R. Camporesi， “Harmonic analysis and propagators on homogeneous spaces,” Phys. Rept. 196,1 (1990).   
[12] J.R. David,M. R. Gaberdiel and R. Gopakumar,“The Heat Kernel on AdS $_ 3$ and its Applications,” arXiv:0911.5085 [hep-th].   
[13] N. D. Birell and P.C.W. Davies,“ Quantum Fields In Curved Space” Cambridge University Press 1982.   
[14] P. Candelas and J. S. Dowker, Phys. Rev. D 19, 2902 (1979).