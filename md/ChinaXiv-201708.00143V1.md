# Some aspects of holographic W-gravity

Wei Li $a$ and Stefan Theisen $b$

$a$ Centre for Particle Theory & Department of Mathematical Sciences Durham University, South Road,DurhamDH1 3LE,UK wei.li2@durham.ac.uk

$b$ Max-Planck-Institut fuir Gravitationsphysik,Albert-Einstein-Institut Am Mühlenberg1,D-14476 Golm,GERMANY stefan.theisen@aei.mpg.de

# ABSTRACT

We use the Chern-Simons formulation of higher spin theories in three dimensions to study aspects of holographic $\mathcal { W }$ -gravity. Concepts which were useful in studies of pure bulk gravity theories, such as the Fefferman-Graham gauge and the residual gauge transformations,which induce Weyl transformations in the boundary theory and their higher spin generalizations, are reformulated in the Chern-Simons language. Flat connections that correspond to conformal and lightcone gauges in the boundary theory are considered.

# Contents

1 Introduction 2   
2 Spin two 5   
3 Spin three and higher 16   
4 Conclusions 34   
A Conventions 35   
B Some explicit results for $\mathbf { S L } ( N )$ （204号 38

# 1 Introduction

Holography is a well-established powerful tool for detailed studies of conformal field theories. In general dimension $d$ the CFT is dual to a gravity theory in the $( d + 1 )$ dimensional bulk, possibly coupled to other bulk fields, whose boundary values are sources of certain operators in the CFT. Local symmetries in the bulk are in one-to-one correspondence with global symmetries on the boundary, where they can be gauged by coupling the theory to sources of conserved currents.

The coupling of the CFT to an external metric leads to a diffeomorphism invariant theory, which, in addition, possesses classical Weyl symmetry, i.e. invariance under rescaling of the metric and possibly of the fields of the CFT. In two dimensions, to which we restrict the following discussion, the three local symmetry parameters are sufficient to gauge away the external metric. In the quantum theory, the symmetries of the classical theory cannot all be maintained simultaneously, leading to an anomaly. It manifests itself in anomalous Ward identities or in a non-invariance of the effective action, a functional of the external metic which is obtained by integrating out the quantum fields and generates correlation functions of the energy-momentum tensor.

Which of the symmetries one wants to maintain dictates the choice of the counterterms. Opting for diffeomorphism invariance (or equivalently conservation of the energymomentum tensor） leads to the non-local Polyakov action [1],whose only dependence on the specific CFT is through an overall factor proportional to the central charge,which parametrizes the anomaly. In this context, the anomaly manifests itself in the noninvariance of the Polyakov action under Weyl rescaling of the metric，causing a nonvanishing vacuum expectation value of the trace of the energy-momentum tensor in an external metric background, or a non-vanishing trace of the two-point function of the energy-momentum tensor in flat space. The anomaly is also well known as the quantummechanically induced central extension of the infinite-dimensional conformal algebra (the symmetry algebra of classical CFT's) to the Virasoro algebra.

Besides conformal symmetry, two-dimensional CFT's can also have enhanced symmetries, the most prominent ones being Kac-Moody symmetries with spin-one currents and supersymmetries with fermionic symmetry currents with spin $3 / 2$ . In this paper we are interested in CFT's with conserved higher-spin currents whose symmetry algebras are known as $\mathcal { W }$ -symmetries,which have the Virasoro algebra as a sub-algebra. The simplest and earliest example is Zamolodchikov's $\mathcal { W } _ { 3 }$ algebra [2]. In the same way as a CFT can be coupled to an external metric, which sources the energy-momentum tensor of the CFT, a CFT with higher-spin $\mathcal { W }$ -symmetries can be coupled to higher-spin gauge fields,which source conserved higher-spin currents. This leads to the notion of $\mathcal { W }$ gravity. At the classical level, the symmetries are higher-spin generalizations of diffeomorphism, parametrized by a traceless symmetric rank $s - 1$ tensor with two components,and generalized Weyl transformations, parametrized by a symmetric rank $s - 2$ tensor with $s - 1$ components.

In the classical theory, these symmetries are sufficient to gauge away the $s + 1$ components of the spin- $s$ sources; but after quantization this is no longer possible. Choosing to preserve difeomorphism invariance and higher-spin gauge symmetries results in anomalies in generalized Weyl symmetries. The anomalous symmetry transformations, called ${ \mathcal W } _ { s }$ -Weyl transformations, are parametrized by one scalar field for each spin $s$ . The corresponding anomalies, which we call ${ \mathcal W } _ { s }$ -anomalies, manifest themselves as trace anomalies in the two-point functions of higher-spin currents or as the non-invariance of the effective action under the (anomalous) ${ \mathcal W } _ { s }$ -Weyl transformations. Two-dimensional theories with $\mathcal { W }$ -algebras as symmetry algebra were intensively studied about 25 years ago, also in the context of string theory, but it is fair to say that the implications of the higher-spin symmetries are much less understood than those of the conformal symmetry. A good review of the early literature is [3].

Since then the AdS/CFT correspondence has equipped us with a new tool to study conformal field theories. To study two-dimensional conformal field theories with higher-spin $\mathcal { W }$ -symmetries and their couplings to higher-spin sources,we need a three-dimensional bulk theory which has, in addition to diffeomorphism, higher-spin gauge symmetries. The Source for the boundary spin- $s$ conserved current is the boundary value of the bulk gauge field of the same spin.

The AdS/CFT correspondence with higher-spin symmetry has recently been studied, in particular for the boundary dimensions $d = 2 , 3$ .For $d = 2$ ,which is the dimension we are interested in this paper, the bulk gravity theory has an alternative description as ChernSimons theory. For 3D pure gravity, whose boundary metric sources components of the CFT energy-momentum tensor, its alternative description as $\mathrm { S L } ( 2 , \mathbb { R } ) \times \mathrm { S L } ( 2 , \mathbb { R } )$ ChernSimons theory has been known for a long time [4, 5]. More recently this was extended to include higher-spin bulk fields [6,7],where a formulation as $\mathrm { S L } ( N , \mathbb { R } ) \times \mathrm { S L } ( N , \mathbb { R } )$ ChernSimons theory was proposed. Corresponding to the presence of the higher-spin bulk fields the boundary theory is a CFT with higher-spin $\mathcal { W } _ { N }$ -symmetry.

A bulk spin- $s$ gauge field is realized by a symmetric space-time tensor of rank $s$ ，which we will refer to as a metric-like field. An action principle for the interacting higher-spin theory in terms of metric-like fields is not known in general. In three dimensions, since we have an alternative description in terms of Chern-Simons theory, we have,in principle, all the information at our disposal. Given a pair of fat connections,i.e. a solution of the equations of motion of the CS theory, we can construct the metric-like fields. Likewise, the higher-spin symmetries are encoded in the ${ \mathfrak { s l } } ( N )$ gauge symmetries, i.e. given a gauge symmetry we can construct the parameters of the higher-spin symmetries,which we refer to as generalized diffeomorphisms.

However, for $N \geq 3$ , it is unclear how to translate from connections to metric-like fields at the level of the action and the equations of motion. Attempts to construct them order by order in the higher-spin fields were made e.g. in [8,9,10]. One difficulty lies in determining the transformations of the metric-like fields under the generalized diffeomorphism,which at present can only be done order by order in the higher-spin fields. What is missing is an understanding of a generalization of Riemannian geometry which would allow us to write down expressions which are covariant w.r.t. to all generalized higher-spin diffeomorphism, e.g. generalized curvatures.

Even though the Chern-Simons formulation provides a complete description of the system, there are situations where a reformulation in terms of metric-like fields seems desirable. For instance, in the context of holography, the boundary conformal field theory is coupled to the boundary values of the metric-like felds in the bulk. The way we bypass this difficulty in this paper is to use pure gravity as a guiding principle, in the following sense. For pure gravity, both the metric and Chern-Simons formulations are well understood, therefore we can translate all wel-known features, in particular those which are relevant in the context of holography, from the metric formulation to the connection one and then look for a natural generalization to higher-rank gauge groups, as appropriate for the description of higher-spin fields.

One of the earliest results in the AdS/CFT correspondence is the holographic description (in any even dimension) of the Weyl anomaly in terms of the dual bulk gravity theory, which plays the role of the non-local effective action [11]. For a three-dimensional bulk,one can translate the analysis into the equivalent Chern-Simons formulation and interpret the bulk diffeomorphism,which induces a Weyl rescaling of the boundary metric, as a particular gauge transformation. In the same way as the Weyl anomaly can be interpreted as the non-invariance of the bulk action under bulk diffeomorphism due to the presence of a boundary, it can be alternatively interpreted as the non-invariance of the Chern-Simons action under gauge transformations, again due to the appearance of a boundary term. Once this is realized, a generalization to higher-rank gauge groups, i.e. to higher-spin theories, is possible, in the sense that W-Weyl symmetries can be interpreted as particular gauge transformations and the non-invariance of the Chern-Simons action can be interpreted as the non-invariance of the non-local effective action of the boundary theory, thus representing the anomalies. The relevant gauge transformations turn out to be those generated by the diagonal Cartan subalgebra of the two ${ \mathfrak { s l } } ( N )$ factors.

The outline of the paper is as follows. In the second chapter we reformulate many features of pure three-dimensional AdS-gravity in the language of $\mathrm { S L } ( 2 , \mathbb { R } ) \times$ SL $( 2 , \mathbb { R } )$ ChernSimons theory. This is mostly a review of well-known facts and follows to a large extent [12], in particular in translating the Fefferman-Graham gauge for the metric to the connection formulation of the theory. We then consider different gauge choices for the connection which correspond to different boundary metrics for the dual CFT. In the third chapter we extend the analysis to higher-rank Chern-Simons theories. We make an attempt to reinterpret the gauge theory results in terms of the higher-spin metric-like fields. As the main new features (and diffculties) arise already for SL(3),we will restrict mostly to this case,i.e. to spin three. We define the Fefferman-Graham gauge and among the residual gauge transformations those which induce W-Weyl rescaling of the boundary fields. We use them to compute the variation of the Chern-Simons action，which is interpreted as the effective action of the boundary theory. We do this in the same gauges which we studied in the Chapter 2. They were also studied recently， however with different emphasis,in [13] and [14], respectively. The interpretation of our result, which also touches upon the interpretation of the relation between bulk and boundary fields, does not seem to be straightforward, though. In Appendix A we establish our conventions for the ${ \mathfrak { s l } } ( N )$ algebras and their representations. In Appendix B we collect some results for general ${ \mathfrak { s l } } ( N )$ ：

# 2 Spin two

# 2.1 Generalities

Our objectives are higher spin theories. As a preparation we review the CS-formulation of pure three-dimensional gravity and state some of the relevant features in a way that suggests a natural generalization to the higher-spin case.

The action of three-dimensional gravity with a cosmological constant in the secondorder formulation is

$$
S = \frac { 1 } { 1 6 \pi G _ { N } } \int _ { \mathcal { M } } d ^ { 3 } x \sqrt { G } \Big ( \mathcal { R } + \frac { 2 } { \ell ^ { 2 } } \Big )
$$

where $G$ is the metric and $\mathcal { R }$ the Ricci scalar. $\ell$ is a length scale, which we will often set to one and $G _ { N }$ is Newton's constant in three dimensions. The action in the first-order formulation is

$$
S = { \frac { 1 } { 4 \pi G _ { N } } } \int _ { \mathcal { M } } \mathrm { t r } \left( e \wedge R + { \frac { 1 } { 3 \ell ^ { 2 } } } e \wedge e \wedge e \right)
$$

where $e = e _ { \mu } ^ { a } J _ { a } d x ^ { \mu }$ is the ${ \mathrm { s o } } ( 2 , 1 )$ -valued dreibein, $R = d \omega + \omega \wedge \omega$ the curvature 2-form, and $\omega = \omega _ { \mu } ^ { a } J _ { a } d x ^ { \mu }$ with $\begin{array} { r } { \omega ^ { a } = \frac { 1 } { 2 } \epsilon ^ { a } \ d _ { b c } \omega ^ { b c } } \end{array}$ the spin connection. For further details on the notation we refer to Appendix A. The equations of motion for $\omega$ are the vanishing of the torsion， which allows to solve algebraically $\omega = \omega ( e )$ . The equations of motion for $e$ are then the Einstein equations for the metric.

These formulations of three-dimensional gravity can be trivially generalized to arbitrary dimensions. There is, however,an alternative formulation which does not generalize to higher dimensions,1 namely in terms of an $\mathrm { S L } ( 2 , \mathbb { R } ) \times \mathrm { S L } ( 2 , \mathbb { R } )$ Chern-Simons theory [4, 5]. If we denote the gauge fields of the two SL(2) factors by $A$ and $\tilde { A }$ , respectively, the action (2.2) can be written as

$$
S = S _ { \mathrm { C S } } [ A ] - S _ { \mathrm { C S } } [ \tilde { A } ] + S _ { \mathrm { b n d y } }
$$

where the Chern-Simons actions are²

$$
S _ { \mathrm { C S } } [ A ] = { \frac { k } { 4 \pi } } \int _ { \mathcal { M } } \mathrm { t r } ( A \wedge d A + { \frac { 2 } { 3 } } A \wedge A \wedge A )
$$

and we need to identify $\begin{array} { r } { k = \frac { \ell } { 4 G _ { N } } } \end{array}$ and

$$
e = { \frac { \ell } { 2 } } { \big ( } A - { \tilde { A } } { \big ) } \qquad { \mathrm { a n d } } \qquad \omega = { \frac { 1 } { 2 } } { \big ( } A + { \tilde { A } } { \big ) }
$$

The difference between the Chern-Simons action and the Einstein-Hilbert action is a boundary term

$$
S _ { \mathrm { b n d y } } = - \frac { k } { 4 \pi } \int _ { \mathcal { M } } \mathrm { t r } \left[ d \left( A \wedge \tilde { A } \right) \right] = - \frac { k } { 4 \pi } \int _ { \partial \mathcal { M } } \mathrm { t r } ( A \wedge \tilde { A } )
$$

The metric can be recovered from the connection via

$$
d s ^ { 2 } = G _ { \mu \nu } d x ^ { \mu } d x ^ { \nu } = 2 \operatorname { t r } ( e \otimes e )
$$

The equations of motion are the flatness conditions for $A$ and $\tilde { A }$

$$
F = d A + A \wedge A = 0
$$

They are invariant $^ 3$ under $\operatorname { S L } ( 2 , \mathbb { R } )$ gauge transformations

$$
A \to U ^ { - 1 } A U + U ^ { - 1 } d U
$$

whose infinitesimal version is $\delta A = d \lambda + [ A , \lambda ]$ .Here $U = \exp ( \lambda ) \in \mathrm { S L } ( 2 , \mathbb { R } )$ and $\lambda \in$ （204号 ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ ：

If we define

$$
\zeta \equiv { \frac { 1 } { 2 } } ( \lambda - \tilde { \lambda } ) \qquad \mathrm { ~ a n d ~ } \qquad \Lambda \equiv { \frac { 1 } { 2 } } ( \lambda + \tilde { \lambda } )
$$

then the infinitesimal version of (2.9) gives

$$
\delta _ { \zeta } e = d \zeta + [ \omega , \zeta ] \qquad \mathrm { a n d } \qquad \delta _ { \Lambda } e = [ e , \Lambda ]
$$

Comparing this with pure gravity [5] identifies $\zeta$ as the parameters of diffeomorphisms and $\Lambda$ as those of Lorentz transformations. In these expressions $\zeta$ is Lie algebra valued. The corresponding space-time vector $\xi$ is

$$
\xi _ { \mu } d x ^ { \mu } = \mathrm { t r } ( e \otimes \zeta )
$$

Holographic considerations usually use the metric formulation based on the EinsteinHilbert action. To this end， the Fefferman-Graham (FG） gauge for the metric, its Fefferman-Graham expansion, and the Penrose-Brown-Henneaux (PBH) transformations have proven very useful. One uses diffeomorphisms to bring the metric to the FG form [15]

$$
d s ^ { 2 } = G _ { \mu \nu } d x ^ { \mu } d x ^ { \nu } = \ell ^ { 2 } \left( { \frac { d \rho ^ { 2 } } { \rho ^ { 2 } } } + { \frac { 1 } { \rho ^ { 2 } } } g _ { i j } ( \rho , x ^ { i } ) d x ^ { i } d x ^ { j } \right) \quad \quad i , j = 1 , \dots , d
$$

where $\rho$ is the radial coordinate and $\rho = 0$ is the boundary with coordinates $x ^ { i }$ .This gauge is particularly convenient in writing the bulk/boundary dictionary as there are no cross-terms $G _ { \rho i }$ . As shown in [15], $g _ { i j } ( \rho , x )$ has an expansion in the vicinity of the boundary (FG expansion)4

$$
g _ { i j } ( \rho , x ) = \sum _ { n \geq 0 } \rho ^ { 2 n } \stackrel { \scriptscriptstyle ( 2 n ) } { \mathcal { I } } _ { i j } ( x )
$$

where $\stackrel { ( 0 ) } { g }$ is the boundary metric. For even boundary dimension $d$ there are additional terms containing logarithms of the radial coordinate. In $d = 2$ ，which is the case we are interested in, they are however absent. Furthermore, in $d = 2$ , in contrast to higher dimensions, the FG expansion is finite [16,17].5 It terminates after the third term $\rho ^ { 2 } { \overset { \underset { \mathrm { ( 4 ) } } { } } { g } } ( x )$ ， which is completely fixed in terms of the lower terms as

$$
\begin{array} { r } { \stackrel { ( 4 ) } { g } = \frac { 1 } { 4 } \stackrel { ( 2 ) } { g } \stackrel { ( 0 ) } { g } ^ { - 1 } \stackrel { ( 2 ) } { g } } \end{array}
$$

The vacuum expectation value of the conserved stress-energy tensor $\mathbfcal { T }$ of the boundary CFT coupled to an external metric $\stackrel { \left( 0 \right) } { g }$ is [19]

$$
\langle \pmb { T } _ { i j } \rangle = k \left( \det ^ { ( 2 ) } _ { \pmb { j } _ { i j } } - \det ^ { ( 0 ) } _ { \pmb { j } _ { i j } } \mathrm { t r } \binom { \binom { 2 } { 2 } } { \pmb { j } } \right) \equiv k T _ { i j } = k \left( t _ { i j } + q _ { i j } \right)
$$

where $t _ { i j }$ is a (non-local) functional of $\stackrel { ( 0 ) } { g }$ and $q _ { i j }$ is traceless and conserved w.r.t. $\mathbf { \dot { \boldsymbol { g } } }$ ． $g$ and $q$ are the boundary data which specify a bulk solution.

The FG gauge is not a complete gauge fixing. The residual diffeomorphism， called PBH transformations, are generated by those $\xi ^ { \mu }$ which satisfy $\mathcal { L } _ { \xi } G _ { \rho \rho } = \mathcal { L } _ { \xi } G _ { \rho i } = 0$ ,whose solution is [20]

$$
\xi ^ { \rho } ( \rho , x ) = - \rho \sigma ( x ) , \qquad \xi ^ { i } ( \rho , x ) = \partial _ { j } \sigma ( x ) \int _ { 0 } ^ { \rho } d \rho ^ { \prime } \rho ^ { \prime } g ^ { i j } ( \rho ^ { \prime } , x ) + \xi ^ { i } ( 0 , x )
$$

Except for the boundary term $\xi ^ { i } ( 0 , x )$ ，which generates an uninteresting boundary diffeomorphism and which will be set to zero from here on, the PBH transformation is parametrized by a single function $\sigma ( x )$ on the boundary. A PBH transformation acts on $g _ { i j } ( \rho , x )$ as

$$
\delta _ { \xi } g _ { i j } = \sigma ( 2 - \rho \partial _ { \rho } ) g _ { i j } + \nabla _ { i } \xi _ { j } + \nabla _ { j } \xi _ { i }
$$

where $\nabla$ is w.r.t. $g _ { i j }$ and $\xi _ { i } \equiv g _ { i j } \xi ^ { j }$ . This implies

$$
\delta _ { \xi } ^ { ( 0 ) } g _ { i j } = 2 \sigma _ { g _ { i j } } ^ { ( 0 ) }
$$

i.e. the bulk PBH transformation induces a Weyl rescaling of the boundary metric which integrates to $\stackrel { ( 0 ) } { g } _ { i j } \mapsto e ^ { 2 \sigma } \stackrel { ( 0 ) } { g } _ { i j }$ for finite transformations.It is easy to work out the PBH transformations of the higher $\stackrel { ( n ) } { g }$ ; for instance, $\delta _ { \xi } \stackrel { ( 2 ) } { g } _ { i j } = \stackrel { ( 0 ) } { \nabla } _ { i } \stackrel { ( 0 ) } { \nabla } _ { j } \sigma$ , which is solved by

$$
{ \bf \Delta } _ { g } ^ { ( 2 ) } = - \frac { 1 } { ( d - 2 ) } \left( \sp { ( 0 ) } R _ { i j } - \frac { 1 } { 2 ( d - 1 ) } R \sp { ( 0 ) } { \bf \Delta } _ { g } ^ { ( 0 ) } { } _ { i j } \right)
$$

The pole at $d = 2$ reflects the non-locality of $\langle \pmb { T } _ { i j } \rangle$ and the fact that

$$
\mathrm { t r } \stackrel { ( 2 ) } { g } = - \frac { 1 } { 2 ( d - 1 ) } \stackrel { ( 0 ) } { R }
$$

is finite reflects the locality of the Weyl anomaly $\left. \pmb { T } ^ { i } { } _ { i } \right.$ .We remark that (2.20) is the part of $\stackrel { ( 2 ) } { g }$ which can be expressed completely in terms of $\stackrel { ( 0 ) } { g }$ . It does not yet contain the second set of boundary data, $q$ . In addition, if other fields are present which allow for the Construction of Weyl-invariant symmetric tensors, they can also contribute to $\stackrel { ( 2 ) } { g } _ { i j }$ and to fix them we need to go on-shell.

Using holography there is an easy way to compute the Weyl anomaly of the boundary CFT，i.e. the non-invariance of the effective action $W [ g ]$ under Weyl rescaling of $g$ （204号 $W [ g ]$ , the generating function for correlation functions of the energy-momentum tensor, is obtained by coupling the CFT to an external metric $g = \stackrel { ( 0 ) } { g }$ and integrating out the CFT.A bulk diffeomorphism leaves the dual gravity action with Lagrangian $\mathcal { L }$ invariant, up to a boundary term

$$
\delta _ { \xi } S = \int _ { \mathcal { M } } \partial _ { \mu } ( \xi ^ { \mu } \mathcal { L } ) = \int _ { \partial \mathcal { M } } \xi ^ { \rho } \mathcal { L }
$$

If we go to FG gauge, perform a FG expansion of the integrand, and use a PBH diffeomorphism,i.e. $\xi ^ { \rho } = - \rho \sigma$ , the on-shell $\mathcal { O } ( \rho ^ { 0 } )$ term is the anomaly [21]6

$$
\delta _ { \sigma } W [ g ] = \delta _ { \xi } S { \big \vert } _ { \rho ^ { 0 } } = { \frac { 1 } { 2 \pi } } \int _ { \partial { \mathcal { M } } } \sqrt { g } \sigma { \mathcal { A } }
$$

Possible divergencies at $\rho = 0$ are cancelled by adding local boundary terms to the bulk action. Applied to (2.1） this gives $\begin{array} { r } { \mathcal { A } = \frac { \ell } { 4 G _ { N } } \mathrm { t r } _ { \mathscr { G } } ^ { ( 2 ) } } \end{array}$

$$
\mathcal { A } = - \frac { c } { 1 2 } R \qquad \mathrm { w i t h } \qquad c = \frac { 3 \ell } { 2 G _ { N } }
$$

where $R$ is the Ricci scalar of the boundary metric

We will now translate these results to the CS formulation (2.3). Here, of course, we will have to set $d = 2$

In the coordinates $x ^ { \mu } = \left( \rho , x ^ { 1 } , x ^ { 2 } \right)$ the connection decomposes as

$$
A = A _ { \mu } d x ^ { \mu } = A _ { \rho } d \rho + A _ { i } d x ^ { i } \ \in \ \mathfrak { s l } ( 2 , \mathbb { R } )
$$

Using the invariance of the action under (2.9) we can choose a gauge for $( A , { \tilde { A } } )$ that best suits the holographic description: the analogue of the Fefferman-Graham gauge with （20 $G _ { \rho \rho } = 1 / \rho ^ { 2 }$ and $G _ { i \rho } = 0$ . It is easy to see that with

$$
A _ { \rho } = - { \frac { 1 } { \rho } } L _ { 0 } \qquad \mathrm { a n d } \qquad \tilde { A } _ { \rho } = { \frac { 1 } { \rho } } L _ { 0 }
$$

(2.7) leads to

$$
G _ { \rho \rho } = \frac { 1 } { \mathrm { t r } [ ( L _ { 0 } ) ^ { 2 } ] } \mathrm { t r } \Big ( \frac { A _ { \rho } - \tilde { A } _ { \rho } } { 2 } \Big ) ^ { 2 } = \frac { 1 } { \rho ^ { 2 } } .
$$

In [7] it was shown that this gauge choice can always be achieved with a group element （204号 $U$ that goes to the identity at the boundary. This condition is necessary if we want that any Dirichlet boundary condition (in [7] it was $A _ { - } = 0$ at $\rho = 0$ ）is preserved.

Our gauge choice for $( A , { \tilde { A } } )$ is therefore

$$
\begin{array} { r l } { \boldsymbol { A } = b ^ { - 1 } \boldsymbol { a } \boldsymbol { b } + b ^ { - 1 } d \boldsymbol { b } \quad } & { { } \mathrm { w i t h } \quad } & { \boldsymbol { b } \equiv e ^ { - ( \log \rho ) L _ { 0 } } } \\ { \boldsymbol { \tilde { A } } = \boldsymbol { \tilde { b } } ^ { - 1 } \boldsymbol { \tilde { a } } \boldsymbol { \tilde { b } } + \boldsymbol { \tilde { b } } ^ { - 1 } d \boldsymbol { \tilde { b } } \quad } & { { } \mathrm { w i t h } \quad } & { \boldsymbol { \tilde { b } } \equiv b ^ { - 1 } } \end{array}
$$

where $( a , \tilde { a } )$ are ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ -valued one-forms along the boundary directions: $a = a _ { i } d x ^ { i }$ and $\tilde { a } = \tilde { a } _ { i } d x ^ { i }$ . With this choice $F _ { \rho i } = 0$ leads to

$$
a = a ( \boldsymbol { x } )
$$

i.e. $a$ depends only on the boundary coordinates $x ^ { i }$ . The remaining flatness conditions $F _ { i j } = 0$ are simply flatness of $a$ and $\tilde { a }$ ：

$$
d a + a \wedge a = 0
$$

All information is now encoded in the connections $( a , \tilde { a } )$ ，which only depends on the boundary coordinates $x ^ { i }$ . A generic $a \in { \mathfrak { s l } } ( 2 )$ can be expanded as

$$
a ( x ) = a _ { i } ( x ) d x ^ { i } \qquad \mathrm { w i t h } \qquad a _ { i } = a _ { i } ^ { + } L _ { 1 } + a _ { i } ^ { 0 } L _ { 0 } + a _ { i } ^ { - } L _ { - 1 }
$$

and,using (2.28)

$$
\begin{array} { l l l } { { A _ { \rho } = - \displaystyle \frac { L _ { 0 } } { \rho } \ : , \ : } } & { { \ : } } & { { A _ { i } = \displaystyle \frac { 1 } { \rho } a _ { i } ^ { + } L _ { 1 } + a _ { i } ^ { 0 } L _ { 0 } + \rho a _ { i } ^ { - } L _ { - 1 } } } \\ { { \tilde { A } _ { \rho } = \ : \ : \frac { L _ { 0 } } { \rho } \ : , \ : } } & { { \ : } } & { { \tilde { A } _ { i } = \rho \tilde { a } _ { i } ^ { + } L _ { 1 } + \tilde { a } _ { i } ^ { 0 } L _ { 0 } + \displaystyle \frac { 1 } { \rho } \tilde { a } _ { i } ^ { - } L _ { - 1 } } } \end{array}
$$

For the dreibein $e = e _ { \rho } d \rho + e _ { i } d x ^ { \imath }$ defined in (2.5) we obtain

$$
e _ { \rho } = - \frac { 1 } { \rho } { \cal L } _ { 0 } , \quad e _ { i } = \frac { 1 } { 2 } ( a _ { i } ^ { 0 } - \tilde { a } _ { i } ^ { 0 } ) { \cal L } _ { 0 } + \frac { 1 } { 2 } \left( \frac { 1 } { \rho } a _ { i } ^ { + } - \rho \tilde { a } _ { i } ^ { + } \right) { \cal L } _ { 1 } + \frac { 1 } { 2 } \left( \rho a _ { i } ^ { - } - \frac { 1 } { \rho } \tilde { a } _ { i } ^ { - } \right) { \cal L } _ { - } .
$$

With (2.7) it is clear that the metric will not be in FG gauge, the culprit being the zero mode component in $e _ { i }$ ，which leads to $G _ { i \rho } \neq 0$ . To remove it we use the residual gauge freedom which preserves the gauge choice (2.26). Making a Gauss decomposition of $U ( \rho , x )$ and $\tilde { U } ( \rho , x )$ (with $\alpha ^ { \pm } = \alpha ^ { \pm } ( x )$ ，etc.)

$$
U = e ^ { \frac { 1 } { \rho } \alpha ^ { + } L _ { 1 } } e ^ { \alpha L _ { 0 } } e ^ { \rho \alpha ^ { - } L _ { - 1 } } , \qquad { \tilde { U } } = e ^ { \frac { 1 } { \rho } { \tilde { \alpha } } ^ { - } L _ { - 1 } } e ^ { { \tilde { \alpha } } L _ { 0 } } e ^ { \rho { \tilde { \alpha } } ^ { + } L _ { 1 } }
$$

with the choice7

$$
\alpha ^ { + } = \tilde { \alpha } ^ { - } = \alpha = \tilde { \alpha } = 0 , \qquad \left( { \frac { \alpha ^ { - } } { \tilde { \alpha } ^ { + } } } \right) = - { \frac { 1 } { 2 } } M ^ { - 1 } \left( { a _ { 1 } ^ { 0 } - \tilde { a } _ { 1 } ^ { 0 } } \right) \qquad M = \left( { a _ { 1 } ^ { + } \atop { \tilde { a } _ { 1 } ^ { - } \tilde { a } _ { 2 } ^ { - } } } \right)
$$

leads to [12]

$$
\tilde { a } _ { i } ^ { 0 } = a _ { i } ^ { 0 }
$$

and therefore removes the zero modes of the dreibein, giving $G _ { i \rho } = 0$ . The gauge choices (2.28) and (2.36) are the FG gauge condition in the CS formulation of three-dimensional gravity. We note that the finiteness of the FG expansion of the dreibein and the metric is manifest. One can show that the FG expansions of $\xi _ { i }$ and $\sqrt { G }$ (but not of $\xi ^ { i }$ ）are finite as well.

With the above gauge choice, the bulk metric (2.7) becomes

$$
G _ { \rho \rho } = \frac { 1 } { \rho ^ { 2 } } , \qquad G _ { i \rho } = 0 , \qquad G _ { i j } = \frac { 1 } { \rho ^ { 2 } } { } ^ { ( 0 ) } { } ^ { ( 2 ) } { } ^ { ( 2 ) } { } _ { i j } + { } ^ { ( 2 ) } { } _ { i j } + \rho ^ { 2 } { } ^ { ( 4 ) } { } _ { i j }
$$

with

$$
\stackrel { \scriptscriptstyle ( 0 ) } { \ = g } = \frac 1 2 a _ { i } ^ { + } \tilde { a } _ { j } ^ { - } d x ^ { i } d x ^ { j } , \quad \stackrel { \scriptscriptstyle ( 2 ) } { \ = g } = - \frac 1 2 \left( a _ { i } ^ { + } a _ { j } ^ { - } + \tilde { a } _ { i } ^ { - } \tilde { a } _ { j } ^ { + } \right) d x ^ { i } d x ^ { j } , \quad \stackrel { \scriptscriptstyle ( 4 ) } { \ = g } = \frac 1 2 a _ { i } ^ { - } \tilde { a } _ { j } ^ { + } d x ^ { i } d x ^ { j }
$$

where the coefficients satisfy the flatness condition (2.30). Using those and the FG gauge condition (2.36),one verifies (2.15) and (2.21).

We know from the metric formulation that the gauge fixing is not yet complete. Indeed, transformations parametrized by $\alpha$ and $\tilde { \alpha }$ have a simple effect on $a _ { i } ^ { \pm }$ and $\tilde { a } _ { i } ^ { \pm }$

$$
a _ { i } ^ { \pm } \to e ^ { \pm \alpha } a _ { i } ^ { \pm } , \qquad \tilde { a } _ { i } ^ { \pm } \to e ^ { \pm \tilde { \alpha } } \tilde { a } _ { i } ^ { \pm }
$$

If we define

$$
\sigma = { \textstyle \frac { 1 } { 2 } } ( \alpha - \tilde { \alpha } ) \qquad \mathrm { a n d } \qquad \tau = { \textstyle \frac { 1 } { 2 } } ( \alpha + \tilde { \alpha } )
$$

then $\sigma$ acts as a Weyl rescaling and $\tau$ as a Lorentz transformation of the boundary zweibein.In particular

$$
\stackrel { ( 0 ) } { g } _ { i j }  e ^ { 2 \sigma } \stackrel { ( 0 ) } { g } _ { i j }
$$

Of course, the transformation (2.39) reintroduces $G _ { i \rho }$ components,but from the previous discussion we know that we can transform them away without afecting the boundary zweibein. In the metric formulation these are the transformations generated by the $\xi ^ { i }$ ： We therefore conclude that the transformations parametrized by $\sigma$ are the PBH transformations of the metric formulation. The remaining two parameters $\alpha ^ { - }$ and $\tilde { \alpha } { } ^ { - }$ parametrize boundary diffeomorphisms.

We now discuss the holographic computation of the Weyl anomaly in the CS formulation.For this we apply the procedure outlined above to the action (2.3). On-shell a diffeomorphism of $A$ can be written as a gauge transformation,

$$
\delta _ { \xi } A = \mathcal { L } _ { \xi } A = d \lambda + [ A , \lambda ] = \delta _ { \lambda } A \qquad \mathrm { w i t h } \qquad \lambda = \iota _ { \xi } A
$$

and likewise $\delta _ { \xi } { \tilde { A } } = \delta _ { \tilde { \lambda } } { \tilde { A } }$ with $\tilde { \lambda } = \iota _ { \xi } \tilde { A }$ . Under such a transformation with $\xi ^ { \mu }$ being the PBH diffeomorphism, the action changes as8

$$
\begin{array} { r l } { { \delta _ { \sigma } W = } } & { { { \displaystyle \frac { k } { 2 \pi } \int _ { \partial { \cal M } } \mathrm { t r } \big [ \sigma L _ { 0 } ( d A + d \tilde { A } ) \big ] } } } \\ { { = } } & { { { \displaystyle \frac { k } { 4 \pi } \int _ { \partial { \cal M } } \sigma \left( \partial _ { i } a _ { j } ^ { 0 } - \partial _ { j } a _ { i } ^ { 0 } \right) d x ^ { i } \wedge d x ^ { j } } } } \end{array}
$$

Bulk and boundary term in (2.3) give equal contributions. This was also observed in [22].9 Using(2.38) and the on-shell and FG gauge conditions, one finds

$$
\delta _ { \sigma } W [ g ] = - \frac { k } { 4 \pi } \int _ { \partial \mathcal { M } } d ^ { 2 } x \sqrt { g } \sigma R
$$

Comparing(2.44) with (2.23) and (2.24) we verify the known relation $c = 6 k$ 号

We note that (2.43) is nothing but (the $\mathcal { O } ( \rho ^ { 0 } )$ term of) the change of the action under a gauge transformation with parameter $\lambda = \sigma L _ { 0 } = - \tilde { \lambda }$ . This was expected from the discussion above,where we found the relation between PBH transformations and ${ \mathfrak { s l } } ( 2 )$ gauge transformations.

So far the discussion has been completely general. We will now consider special choices of the boundary metric and translate them into the CS formulation. This discussion follows largely [12].

# 2.2 Conformal gauge

The first case is ${ \bf \Phi } _ { { \bf \Phi } ^ { ( 0 ) } } ^ { ( 0 ) } = e ^ { \Phi } \delta _ { i j }$ , i.e.the boundary metric is in conformal gauge. In this case, the non-local Polyakov action $W [ g ]$ , which is completely fixed up to a multiplicative

constant $c$ (the central charge of the CFT)，becomes the (local) Liouville action for $\Phi$ （204号 and correlation functions of the energy-momentum tensor are expressed in terms of the Liouville field $\Phi$ . In this gauge $\stackrel { ( 2 ) } { g }$ in (2.20) has a well-defined limit in $d = 2$

$$
\begin{array} { r } { \mathbf { \Phi } _ { } ^ { ( 2 ) } { } _ { i j } = \frac { 1 } { 2 } \partial _ { i } \partial _ { j } \Phi - \frac { 1 } { 4 } \partial _ { i } \Phi \partial _ { j } \Phi + \frac { 1 } { 8 } \delta _ { i j } ( \partial \Phi ) ^ { 2 } + q _ { i j } } \end{array}
$$

where we have added a conserved and traceless $q _ { i j }$ . Via (2.15) the bulk metric is now completely fixed in terms of $\Phi$ and $q$ . Choosing a complex structure on the boundary10 s.t. $d s ^ { 2 } = e ^ { \Phi } d z d \bar { z }$ , one finds for $T$ of (2.16)

$$
t _ { z z } = - { \textstyle \frac 1 4 } ( \partial \Phi ) ^ { 2 } + { \textstyle \frac 1 2 } \partial ^ { 2 } \Phi \qquad t _ { \bar { z } \bar { z } } = - { \textstyle \frac 1 4 } ( \bar { \partial } \Phi ) ^ { 2 } + { \textstyle \frac 1 2 } \bar { \partial } ^ { 2 } \Phi \qquad t _ { z \bar { z } } = { \textstyle \frac 1 2 } \partial \bar { \partial } \Phi
$$

and

$$
q _ { z z } = q ( z ) q _ { \bar { z } \bar { z } } = \bar { q } ( \bar { z } ) , q _ { z \bar { z } } = 0
$$

We recognize $t _ { z z }$ and $t _ { \bar { z } \bar { z } }$ as the (traceless) energy-momentum tensor of Liouville theory.11

The bulk metric with $\Phi \neq 0$ can be obtained from the one with $\Phi = 0$ by a finite PBH transformation. As we will now show,this can be easily translated to the CS-formulation of pure gravity (and generalized to the higher-spin case, cf. Section 3). In FG gauge, the flat connections $( a , \tilde { a } )$ that correspond to the on-shell bulk metric in conformal gauge are [12]

$$
\begin{array} { r l r } & { } & { a _ { z } = e ^ { \phi } L _ { 1 } - \partial \tilde { \phi } L _ { 0 } - e ^ { - \phi } T L _ { - 1 } , \qquad a _ { \bar { z } } = \bar { \partial } \phi L _ { 0 } + { \frac { 1 } { 2 } } e ^ { - \phi } R L _ { - 1 } } \\ & { } & { \tilde { a } _ { z } = - \partial \tilde { \phi } L _ { 0 } + { \frac { 1 } { 2 } } e ^ { - \tilde { \phi } } R L _ { 1 } , \qquad \tilde { a } _ { \bar { z } } = e ^ { \tilde { \phi } } L _ { - 1 } + \bar { \partial } \phi L _ { 0 } - e ^ { - \tilde { \phi } } \bar { T } L _ { 1 } } \end{array}
$$

where $( T , \bar { T } ) \equiv ( T _ { z z } , T _ { \bar { z } \bar { z } } )$ ，and $R \equiv R _ { z \bar { z } } = - \partial \bar { \partial } \Phi$ is the boundary Ricci tensor. The two fields $\phi$ and $\tilde { \phi }$ satisfy

$$
\phi + { \tilde { \phi } } = \Phi
$$

Consider the pair of connections

$$
a _ { 0 } = [ L _ { 1 } - q ( z ) L _ { - 1 } ] d z \qquad \mathrm { a n d } \qquad \tilde { a } _ { 0 } = [ L _ { - 1 } - \tilde { q } ( \bar { z } ) L _ { 1 } ] d \bar { z }
$$

It is obviously flat and in FG gauge. It corresponds to a flat boundary metric and vev's $( q ( z ) , \bar { q } ( \bar { z } ) )$ in the absence of the source. The flat connection (2.48) is related to (2.50) via a gauge transformations with

$$
g = e ^ { - \frac { 1 } { 2 } \partial \Phi L _ { - 1 } } e ^ { \phi L _ { 0 } } \qquad \mathrm { a n d } \qquad \tilde { g } = e ^ { - \frac { 1 } { 2 } \bar { \partial } \Phi L _ { 1 } } e ^ { - \bar { \phi } L _ { 0 } } = ( g ^ { - 1 } ) ^ { \dagger }
$$

Note that this gauge transformation does not depend on $( q ( z ) , \bar { q } ( \bar { z } ) )$ . The bulk metrics derived from (2.48) and (2.5O) are related by a finite PBH transformation generated by (2.51). The zero mode parts in $( g , \tilde { g } )$ introduce the conformal mode,while the other factors in $( g , \tilde { g } )$ restore the FG gauge. As we have already remarked before, this does not modify the leading terms in the FG expansion.

Finally, applying (2.43) to the connections (2.48) we obtain the conformal anomaly

$$
\delta _ { \sigma } W = \frac { k } { 2 \pi } \int _ { \partial \mathcal { M } } \sigma \partial \bar { \partial } \Phi d z \wedge d \bar { z }
$$

Using that the Ricci scalar for the conformal metric is $R = - 4 e ^ { - \Phi } \partial \partial \Phi$ ，we confirm that thisagreeswith (2.4).Tiscanbeintegatedto $\begin{array} { r } { W = { \frac { k } { 8 \pi } } \int _ { \partial M } \Phi \partial { \bar { \partial } } \Phi } \end{array}$ 迁 $\delta _ { \sigma } \Phi = 2 \sigma$ ，which is the Weyl rescaling of the boundary metric in conformal gauge.

# 2.3 （204号 $\mu$ - gauge

The second gauge choice which we will discuss is constructed such that the boundary metric is

$$
d s ^ { 2 } = | d z + \mu d \bar { z } | ^ { 2 }
$$

where the Beltrami differential $\mu \equiv \mu _ { \bar { z } } ^ { z } ( z , \bar { z } )$ defines the complex structure.12 $( \mu , \bar { \mu } )$ source the $( T _ { z z } , T _ { \bar { z } \bar { z } } )$ components of the CFT energy-momentum tensor. The most general metric can be written as $e ^ { \Phi } | d z + \mu d { \bar { z } } | ^ { 2 }$ and our gauge fixing amounts to setting the conformal factor to one. We can restore it via a PBH transformation.

We wil now construct the ${ \mathfrak { s l } } ( 2 ) \oplus { \mathfrak { s l } } ( 2 )$ connection $( a , \tilde { a } )$ from which we can construct the bulk metric in FG gauge with (2.53) as boundary metric. Recall that the Beltrami differential $\mu$ parametrizes the complex structure $u$ on the boundary. Demanding $d u =$ $\lambda ( d z + \mu d \bar { z } )$ requires $u$ to satisfy the Beltrami equation

$$
( { \bar { \partial } } - \mu \partial ) u = 0
$$

The pair $( \mu , T )$ with

$$
T = - { \frac { 1 } { 2 } } \{ u , z \} \qquad { \mathrm { w h e r e } } \qquad \{ u , z \} = \partial \left( { \frac { \partial ^ { 2 } u } { \partial u } } \right) - { \frac { 1 } { 2 } } \left( { \frac { \partial ^ { 2 } u } { \partial u } } \right) ^ { 2 }
$$

defines a projective structure. Given $T$ and $\mu$ , the consistency between (2.54) and (2.55) requires them to satisfy the anomalous Virasoro Ward identityl3

$$
( \bar { \partial } - \mu \partial - 2 \partial \mu ) T = - \frac { 1 } { 2 } \partial ^ { 3 } \mu
$$

whose l.h.s. is proportional to $\partial _ { \bar { u } } T _ { u u }$ and the general solution to the non-anomalous Ward identity is therefore $( \partial u ) ^ { 2 } q ( u )$

The following observation connects this to the ${ \mathfrak { s l } } ( 2 )$ CS theory [23]. Consider the linear system

$$
\Psi = 0 \qquad \mathrm { w i t h } \qquad \nabla = d z \otimes ( \partial + a _ { z } ) + d \bar { z } \otimes ( \bar { \partial } + a _ { \bar { z } } ) \qquad \mathrm { a n d } \quad \Psi = \left( \frac { \tilde { \psi } } { \psi } \right)
$$

where $a$ is an ${ \mathfrak { s l } } ( 2 , \mathbb { C } )$ connection with

$$
a _ { z } \equiv L _ { 1 } - T L _ { - 1 } = \left( \begin{array} { c c } { { 0 } } & { { - T } } \\ { { - 1 } } & { { 0 } } \end{array} \right) , \qquad a _ { \bar { z } } \equiv \mu L _ { 1 } + \bar { \omega } L _ { 0 } + \beta L _ { - 1 } = \left( \begin{array} { c c } { { \frac { \bar { \omega } } 2 } } & { { \beta } } \\ { { - \mu } } & { { - \frac { \bar { \omega } } 2 } } \end{array} \right)
$$

The holomorphic and anti-holomorphic parts of $\nabla \Psi = 0$ imply a second-order holomorphic equation and a first-order mixed one for $\psi$ ， respectively:

$$
\left( \partial ^ { 2 } - T \right) \psi = 0 \qquad \mathrm { a n d } \qquad \left( \bar { \partial } - \mu \partial - \frac { 1 } { 2 } \bar { \omega } \right) \psi = 0
$$

Compatibility between the holomorphic and the anti-holomorphic parts requires $a$ to be flat. This in turn implies two algebraic equations

$$
\bar { \omega } = - \partial \mu \qquad \mathrm { a n d } \qquad \beta = - \frac 1 2 \partial \bar { \omega } - \mu T
$$

and one first-order ODE, which is precisely the Virasoro Ward identity (2.56). It is then straightforward to show that the ratio of two linearly independent solutions of (2.59), i.e.

$$
u = \frac { \psi _ { 1 } } { \psi _ { 2 } }
$$

is a solution of (2.54) and (2.55). The linear system (2.57) is therefore equivalent to (2.54) and (2.55) [24].

To derive (2.54) and (2.55) from the flat connection $a$ (2.58） we rewrite $a$ as a pure gauge $a = g ^ { - 1 } d g$ and make a Gauss decomposition of $g$ ：

$$
g = e ^ { f _ { + } L _ { 1 } } e ^ { - f _ { 0 } L _ { 0 } } e ^ { f _ { - } L _ { - 1 } }
$$

The minus sign in front of $f _ { 0 }$ is for later convenience. The condition for $a _ { z } = g ^ { - 1 } \partial g$ to be in the highest weight gauge (2.58) gives

$$
f _ { - } = \frac { 1 } { 2 } \partial f _ { 0 } \qquad \mathrm { a n d } \qquad e ^ { f _ { 0 } } = \partial f _ { + }
$$

Then $T$ can be read off from the $L _ { - 1 }$ direction of $a _ { z }$

$$
T = \frac { 1 } { 4 } ( \partial f _ { 0 } ) ^ { 2 } - \frac { 1 } { 2 } \partial ^ { 2 } f _ { 0 } = - \frac { 1 } { 2 } \{ f _ { + } , z \}
$$

and μcanberead ofromtheL directionof az: μ=ft Of+.Tis the Schwarzian derivative of $f _ { + }$ , which satisfies the Beltrami equation (2.54). ( $T$ is also the negative of the energy of Liouville theory with $\Phi = f _ { 0 }$ ）

One is now tempted to use the connection (2.58) and its anti-holomorphic counterpart （204号 $\tilde { a } = - a ^ { \dagger }$ to construct the bulk metric with boundary metric (2.53). However, this fails because the metric would not be in FG gauge. The latter is obvious as the zero modes of （204号 $a$ and $\tilde { a }$ are not coupled. This can be cured with a gauge transformation generated by

$$
g = e ^ { - \frac { 1 } { 2 } \omega _ { \mathrm { { F G } } } L _ { - 1 } } \qquad \mathrm { ~ a n d ~ } \qquad \tilde { g } = \left( g ^ { - 1 } \right) ^ { \dagger } = e ^ { - \frac { 1 } { 2 } \bar { \omega } _ { \mathrm { { F G } } } L _ { 1 } }
$$

This leads to

$$
\begin{array} { l l } { { a _ { z } = L _ { 1 } - \omega L _ { 0 } - T L _ { - 1 } , } } & { { \qquad a _ { \bar { z } } = \mu L _ { 1 } + \bar { \omega } L _ { 0 } + \beta L _ { - 1 } } } \\ { { { \tilde { a } } _ { z } = \bar { \mu } L _ { - 1 } - \omega L _ { 0 } + \bar { \beta } L _ { 1 } , } } & { { \qquad { \tilde { a } } _ { \bar { z } } = L _ { - 1 } + \bar { \omega } L _ { 0 } - { \bar { T } } L _ { 1 } } } \end{array}
$$

where we have chosen $\omega = \omega _ { \mathrm { F G } } + \bar { \mu } \bar { \omega } _ { \mathrm { F G } }$ .We have also redefined $\beta$ and dropped the subscript on $\omega _ { \mathrm { { F G } } }$ . We will call the gauge (2.66) the $\mu$ -gauge.

The flatness condition leads to two algebraic equations for $\omega$ and $\beta$

$$
\mu \omega + \bar { \omega } = - \partial \mu \qquad \mathrm { a n d } \qquad \beta = - \frac 1 2 \bigl ( \bar { \partial } \omega + \partial \bar { \omega } \bigr ) - \mu T
$$

The first, combined with its anti-holomorphic counterpart, gives

$$
\omega = \frac { \bar { \mu } \partial \mu - \bar { \partial } \bar { \mu } } { 1 - | \mu | ^ { 2 } }
$$

The last relation following from fatness is the anomalous Virasoro Ward identity (2.56)

$$
( \bar { \partial } - \mu \partial - 2 \partial \mu ) ( T - Q _ { 2 } ) = - \frac { 1 } { 2 } \partial ^ { 3 } \mu \qquad \mathrm { w i t h } \qquad Q _ { 2 } = - \frac { 1 } { 4 } \omega ^ { 2 } + \frac { 1 } { 2 } \partial \omega
$$

The shift of $T$ by $- \mathcal { Q } _ { 2 }$ simply undoes the shift of $T$ when going from (2.58) to (2.66). The ambiguity in $T$ ， previously denoted by $q$ , is a solution of the non-anomalous Ward identity. The Ward identity obeyed by $T$ is the complex conjugate of (2.69).

From (2.66) we can compute the dreibein and the bulk metric, for which we find

$$
{ \stackrel { \scriptscriptstyle ( 0 ) } { g } } = | d z + \mu d \bar { z } | ^ { 2 } , \qquad { \stackrel { \scriptscriptstyle ( 2 ) } { g } } = \frac { 1 } { 2 } [ ( T d z - \beta d \bar { z } ) ( d z + \mu d \bar { z } ) + \mathrm { c . c . } ] , \qquad { \stackrel { \scriptscriptstyle ( 4 ) } { g } } = | T d z - \beta d \bar { z } | ^ { 2 } ,
$$

with $\beta$ as in (2.67).

As a check we compute, using (2.43)

$$
\delta _ { \sigma } W [ g ] = \frac { k } { 2 \pi } \int _ { \partial \mathcal { M } } \sigma \left( \partial \bar { \omega } + \bar { \partial } \omega \right) d ^ { 2 } z
$$

Using (2.68) one finds $\begin{array} { r } { \partial \omega + \partial \bar { \omega } = - \frac 1 2 \sqrt { g } R [ g ] } \end{array}$ ， which shows that the Weyl anomaly is correctly reproduced.

We can also write down the bulk metric with the boundary metric in lightcone gauge

$$
d s ^ { 2 } = ( d z + \mu d { \bar { z } } ) d { \bar { z } }
$$

by setting $\bar { \mu } = 0$ . This results in the connections

$$
\begin{array} { l l } { { a _ { z } = L _ { 1 } - T L _ { - 1 } , \qquad } } & { { a _ { \bar { z } } = \mu L _ { 1 } + \bar { \omega } L _ { 0 } + \beta L _ { - 1 } } } \\ { { { \nonumber } } } & { { { \nonumber } } } \\ { { { \tilde { a } } _ { z } = - \frac { 1 } { 2 } \partial \bar { \omega } L _ { 1 } , \qquad } } & { { { \nonumber } } } \\ { { { \qquad } } } & { { { \qquad } { \tilde { a } } _ { \bar { z } } = L _ { - 1 } + \bar { \omega } L _ { 0 } - { \bar { T } } L _ { 1 } } } \end{array}
$$

The equation of motion obeyed by $( \bar { \omega } , \beta )$ reduces from (2.67) back to (2.60). Note however that the holomorphic $a$ and anti-holomorphic $\tilde { a }$ are still coupled, so as to ensure FG gauge.

The Ward identity satisfied by $T$ reduces to the chiral one (2.56)，whereas the one satisfied by $T$ is

$$
\partial \left( { \bar { T } } - { \bar { \mathcal { Q } } } _ { 2 } ( \bar { \omega } ) \right) = 0
$$

with $\bar { \omega } = - \partial \mu$ . The Weyl anomaly is simply

$$
A _ { 2 } = \frac { c } { 3 } \partial ^ { 2 } \mu = - \frac { c } { 1 2 } R [ g ]
$$

# 3 Spin three and higher

# 3.1 Generalities

The goal of the previous chapter was to establish relations between the metric formulation of three-dimensional gravity and its connection formulation as a Chern-Simons theory. In this chapter we will turn our attention to higher-spin theories in three dimensions. Here we have only limited knowledge of its formulation in terms of the metric and higher-spin fields and we thus have to resort to its CS formulation. Much of the discussion of Chapter 2, which was largely review and reformulation of wel-known results, was presented in such a way that it can be straightforwardly generalized from ${ \mathfrak { s l } } ( 2 )$ to ${ \mathfrak { s l } } ( N )$ . However, since explicit expression become rather cumbersome, we will often restrict to ${ \mathfrak { s l } } ( 3 )$

The relation between the CS formulation and the formulation in terms of metric-like fields was studied recently, see for instance [8,9,1O],but here the emphasis is on different aspects than in those references.

The description of higher-spin theories in three dimensions as higher-rank ChernSimons theories was established in [6,7, 25]. The spectrum of spins depends on the embedding of the gravitational ${ \mathrm { S L } } ( 2 , \mathbb { R } ) \times { \mathrm { S L } } ( 2 , \mathbb { R } ) \hookrightarrow G \times G$ . Here we will only consider （20 $G = \mathrm { S L } ( N , \mathbb { R } )$ and the principal embedding ${ \mathrm { S L } } ( 2 , \mathbb { R } ) \hookrightarrow { \mathrm { S L } } ( N , \mathbb { R } )$ ：

The staring point for our discussion is the action (2.3) with $A \in { \mathfrak { s l } } ( N , \mathbb { R } )$ . In order for the gravity subsector to match the Einstein-Hilbert action, we need

$$
k = { \frac { \ell } { 4 G _ { N } } } { \frac { 1 } { 2 \operatorname { t r } [ ( L _ { 0 } ) ^ { 2 } ] } } = { \frac { c } { 1 2 \operatorname { t r } [ ( L _ { 0 } ) ^ { 2 } ] } }
$$

where $\ell$ is the AdS radius,which we will often set to one, and $c$ is the central charge of the boundary CFT. The group theory notation is explained in Appendix A.

The generalized dreibein and spin-connection are again given by (2.5), but now they are elements of ${ \mathfrak { s l } } ( N , \mathbb { R } )$ . We could also rewrite the action in terms of those fields (see e.g. [7]),but we willinstead use (2.3), which is more systematic and elegant. The equations of motion are again the flatness conditions for $A$ and $\tilde { A }$ ，i.e. $F ( A ) = 0$ and $F ( { \tilde { A } } ) = 0$ ， and they are invariant under $\operatorname { S L } ( N )$ gauge transformations.

The parameters $\zeta$ and $\Lambda$ ， defined as in (2.1O)，now parametrize generalized diffeomorphisms and Lorentz transformations. Given $\zeta$ ，the generators of diffeomorphism and spin-3 transformation are (cf. (2.12))

$$
\xi _ { \mu } = \mathrm { t r } { \left( e _ { \mu } \zeta \right) } \qquad \mathrm { a n d } \qquad \xi _ { \mu \nu } = \mathrm { t r } { \left( e _ { ( \mu } e _ { \nu ) } \zeta \right) }
$$

and similarly for $s \geq 4$ gauge transformations.

For principal embedding, which is essentially unique, there is one spin- $s$ fields $\Psi ^ { ( s ) }$ for （204号 $s = 2 , \ldots , N$ , one for each Casimir invariant; they are totally symmetric rank- $s$ space-time tensors with additional constraints, e.g. double tracelessness in the free theory. They can all be constructed from $e$ . The metric ( $s = 2$ ）is

$$
d s ^ { 2 } = G _ { \mu \nu } d x ^ { \mu } d x ^ { \nu } = \frac { 1 } { \mathrm { t r } \big [ ( L _ { 0 } ) ^ { 2 } \big ] } \mathrm { t r } \big ( e \otimes e \big )
$$

where the normalization has been chosen to make it independent of the normalization of the generators of ${ \mathfrak { s l } } ( N )$ . Similarly, the spin-3 field is the unique (up to a normalization) totally symmetric rank-3 tensor which can be constructed from $e$ ：

$$
\Psi = \Psi _ { \mu \nu \lambda } d x ^ { \mu } d x ^ { \nu } d x ^ { \lambda } = { \frac { 2 } { 3 } } \operatorname { t r } { \big ( } e \otimes e \otimes e { \big ) }
$$

By construction the higher-spin fields are invariant under generalized Lorentz transformations. For $s > 3$ this criterion leaves some ambiguities; e.g. for $s = 4$ field,any linear combination

$$
\operatorname { t r } ( e \otimes e \otimes e \otimes e ) + c \left( \operatorname { t r } ( e \otimes e ) \right) ^ { 2 }
$$

is a Lorentz invariant symmetric rank-4 space-time tensor.

The invariance of the action under (2.9) can again be used to choose the gauge (2.26) which, in addition to (2.27) also implies $\Psi _ { \rho \rho \rho } ^ { ( 3 ) } = 0$ . This is necessary if we want to have a pure gravity limit. In fact, if we require $A _ { \rho } = - \tilde { A } _ { \rho }$ (i.e. symmetry between the two connections) and that in the pure gravity case (i.e. when we switch off all higher-spin fields) $A _ { \rho }$ and $\tilde { A } _ { \rho }$ reduce to (2.26), this is the only choice. For $s = 4$ this requirement e.g. fixes the coefficient $c$ in (3.5). We can therefore impose

$$
\Psi _ { \rho . . . \rho } ^ { ( s ) } = 0
$$

as part of our FG gauge condition. As shown in [7] this gauge choice is alway possible and can be achieved by a group element that goes to the identity at the boundary $\rho = 0$ ：

Our gauge choice for $( A , { \tilde { A } } )$ is therefore again (2.28) where $( a , \tilde { a } )$ are now ${ \mathfrak { s l } } ( N , \mathbb { R } )$ -valued and $F _ { \rho i } = 0$ lead again to (2.29) and (2.30). The mode expansions (2.31) are generalized to

$$
a = \sum _ { s = 2 } ^ { N } \sum _ { m = - s + 1 } ^ { s - 1 } a _ { ( s ) } ^ { m } W _ { m } ^ { ( s ) } { } ~ \tilde { a } = \sum _ { s = 2 } ^ { N } \sum _ { m = - s + 1 } ^ { s - 1 } \tilde { a } _ { ( s ) } ^ { m } W _ { m } ^ { ( s ) }
$$

with $a _ { ( s ) } ^ { m }$ being one-forms on the boundary. Note that the $\rho$ -dependence is completely fixed and the residual gauge transformations, to be discussed next, are parametrized by functions on the boundary.

The choice (2.28) has a residual gauge freedom with

$$
U ( \rho , x ) = b ^ { - 1 } u ( x ) b \qquad \mathrm { a n d } \qquad \tilde { U } ( \rho , x ) = \tilde { b } ^ { - 1 } \tilde { u } ( x ) \tilde { b }
$$

which acts as

$$
a  u ^ { - 1 } a u + u ^ { - 1 } d u
$$

Make Gauss decompositions

$$
u = u _ { + } u _ { 0 } u _ { - } \mathrm { a n d } \tilde { u } = \tilde { u } _ { - } \tilde { u } _ { 0 } \tilde { u } _ { + }
$$

where $u _ { + }$ is generated by all the positive modes $W _ { m } ^ { ( s ) }$ with $m > 0$ , etc. The conditions for （204号 $U$ and $\tilde { U }$ to go to the identity at the boundary are

$$
u _ { + } = u _ { 0 } = 1 \qquad \mathrm { a n d } \qquad \tilde { u } _ { - } = \tilde { u } _ { 0 } = 1
$$

For ${ \mathfrak { s l } } ( 2 )$ ， $G _ { \rho i } = 0$ is equivalent to the condition that $e _ { i }$ has no $L _ { 0 }$ component. The generalization to ${ \mathfrak { s l } } ( N )$ is that $e _ { i }$ has no $W _ { 0 } ^ { ( s ) }$ components, i.e.

$$
\mathrm { t r } \big [ W _ { 0 } ^ { ( s ) } ( a _ { i } - \tilde { a } _ { i } ) \big ] = 0 \qquad \mathrm { w i t h } \quad s = 2 , \dots , N
$$

This can be achieved with $u = u _ { - }$ and $\tilde { u } = \tilde { u } _ { + }$ and leads to

$$
\Psi _ { \rho \dots \rho i } ^ { ( s ) } = 0
$$

In pure gravity we could gauge away all mixed components. This is not possible for the higher-spin fields.

Before we continue to compute the FG expansion of the bulk spin-s field, we briefly discuss what we should expect from the boundary point of view. A field $\Phi ( x )$ with scaling dimension $\Delta$ ， when coupled to gravity, has Weyl weight $\Delta$ ：

$$
g _ { i j }  e ^ { 2 \sigma ( x ) } g _ { i j } \qquad \Longrightarrow \qquad \Phi _ { \Delta } ( x )  e ^ { \Delta \sigma ( x ) } \Phi _ { \Delta } ( x )
$$

where $\sigma ( x )$ is the Weyl factor. In flat space a conserved spin- $s$ current $W _ { a _ { 1 } . . . a _ { s } }$ has scaling dimension, hence Weyl weight, $\Delta = 2 - d - s$ ；therefore $W _ { i _ { 1 } \ldots i _ { s } } = e _ { i _ { 1 } } ^ { a _ { 1 } } \cdot \cdot \cdot e _ { i _ { s } } ^ { a _ { s } } W _ { a _ { 1 } \ldots a _ { s } }$ has Weyl weight $( 2 - d )$ . Coupling $W _ { i _ { 1 } \dots i _ { s } }$ to the background spin- $s$ field $\varphi ^ { ( s ) }$ via

$$
\Delta S = \int d ^ { d } x \sqrt g W _ { i _ { 1 } . . . i _ { s } } \varphi ^ { i _ { 1 } . . . i _ { s } }
$$

and requiring Weyl invariance of (3.15) fixes the Weyl weight of the source

$$
\varphi ^ { i _ { 1 } \ldots i _ { s } }  e ^ { - 2 \sigma } \varphi ^ { i _ { 1 } \ldots i _ { s } } \qquad \Longleftrightarrow \qquad \varphi _ { i _ { 1 } \ldots i _ { s } }  e ^ { 2 ( s - 1 ) \sigma } \varphi _ { i _ { 1 } \ldots i _ { s } }
$$

For the metric ( $s = 2$ ),which is the source for the energy-momentum tensor with $\Delta = d$ ， this is the usual Weyl rescaling.

In the holographic description, the sources are boundary values of bulk felds. Since the Weyl rescaling of the boundary metric is induced by a bulk diffeomorphism with （20 $\xi ^ { \rho } = - \rho \sigma ( x )$ , this diffeomorphism must also lead to a rescaling of the boundary value of the spin- $s$ fields. Given their transformation under Weyl rescalings this means that

$$
\Psi _ { i _ { 1 } \ldots i _ { s } } ^ { ( s ) } ( \rho , x ) = \frac { \varphi _ { i _ { 1 } \ldots i _ { s } } ( x ) } { \rho ^ { 2 ( s - 1 ) } } + \ldots .
$$

when all components are along the boundary. For bulk fields with mixed components

$$
\Psi _ { \rho . . . \rho i _ { 1 } . . . i _ { k } } ^ { ( s ) } ( \rho , x ) = \frac { \varphi _ { \rho . . . \rho i _ { 1 } . . . i _ { k } } ( x ) } { \rho ^ { s + k - 2 } } + . . .
$$

For pure gravity the FG expansion of the metric can be translated to a FG expansion of the dreibein (or vielbein,in general). In the CS formulation it translates into a $\rho$ ， expansion of the connections. In FG-gauge

$$
e _ { \rho } = - \frac { 1 } { \rho } L _ { 0 }
$$

The remaining two components have the $\rho$ -expansion

$$
e _ { i } = \frac { 1 } { \rho } \sum _ { n = - N + 2 } ^ { N } \rho ^ { n } \stackrel { ( n ) } { e } _ { i }
$$

with

$$
{ \bf \Pi } _ { e } ^ { ( n ) } d x ^ { i } = \frac 1 2 \sum _ { s = \left| n - 1 \right| + 1 } ^ { N } \left[ a _ { ( s ) } ^ { - n + 1 } W _ { - n + 1 } ^ { ( s ) } - \tilde { a } _ { ( s ) } ^ { n - 1 } W _ { n - 1 } ^ { ( s ) } \right]
$$

for a generic $( a , \tilde { a } )$ with mode-expansion (3.7). In terms of the $\rho$ -expansion of $e$ ，the Fefferman-Graham gauge (3.12) is that $e _ { i }$ has no $\mathcal { O } ( \rho ^ { 0 } )$ term.

The $\rho$ -expansion of the metric-like fields can then simply be computed from their definitions in terms of the dreibein $e$ . The finiteness of the FG expansion is an immediate consequence of the construction,e.g. for the metric

$$
G _ { i j } ( x , \rho ) = \frac { 1 } { \rho ^ { 2 } } \sum _ { n = - N + 2 } ^ { N } \rho ^ { 2 n } { } ^ { ( 2 n ) } g _ { i j } ( x )
$$

If $^ { ( n ) } _ { g } \neq 0$ for $n < 0$ ,the back-reaction due to the higher-spin felds changes the leading behavior of the metric. This is to be expected, since the higher-spin fields at the boundary are irrelevant perturbations of the boundary CFT.14 We will later discuss special cases where the strong back-reaction is absent. The $\rho$ -expansion of the bulk spin- $s$ field can also be easily worked out using (3.21).

We now discuss residual gauge transformations which preserve FG gauge. As in the pure gravity case,we call them PBH transformations. In pure gravity we saw that they induce Weyl transformations of the boundary metric, which, in the CS formulation,are generated by gauge transformations along the Cartan direction $L _ { 0 }$ ， accompanied by compensating gauge transformations which vanish at the boundary and restore FG gauge. The generalization to ${ \mathfrak { s l } } ( N )$ are the gauge transformations along the Cartan directions W accompanied by gauge transformations which vanish at the boundary and restore FG gauge.

Infinitesimal gauge transformations which preserve (2.26) are of the form

$$
\delta A = d \lambda + [ A , \lambda ] \qquad \mathrm { w i t h } \qquad \lambda = b ^ { - 1 } \alpha ( x ) b
$$

together with the $\tilde { A }$ part; $\alpha$ has the mode expansion $\begin{array} { r } { \alpha = \sum _ { s , m } \alpha _ { m } ^ { s } W _ { m } ^ { ( s ) } } \end{array}$ . Demanding this to preserve (3.12） imposes the following constraints on the parameters in $( \alpha , \tilde { \alpha } )$ ：

$$
\mathrm { t r } [ W _ { 0 } ^ { ( s ) } ( \delta a _ { i } - \delta \tilde { a } _ { i } ) ] = 0 \qquad \mathrm { w i t h } \quad s = 2 , \dots , N
$$

The gauge transformation (3.23) contains the (generalized) diffeomorphism $\delta _ { \zeta }$ and the (generalized) Lorentz transformation $\delta _ { \Lambda }$ (2.11). By construction,the Lorentz transformation has no effect on the metric-like fields because all $\mathrm { t r } \big [ [ e , \Lambda ] \otimes e \cdot \cdot \cdot \otimes e \big ] = 0$ . The effect of $\delta _ { \zeta }$ on the metric-like fields can be computed straightforwardly

$$
\delta _ { \zeta } G _ { \mu \nu } d x ^ { \mu } d x ^ { \nu } = { \frac { 2 } { \mathrm { t r } [ ( L _ { 0 } ) ^ { 2 } ] } } \left( \mathrm { t r } [ d \zeta \otimes e ] + \mathrm { t r } [ [ \omega , \zeta ] \otimes e ] \right)
$$

$$
\delta _ { \zeta } \Psi _ { \mu \nu \sigma } d x ^ { \mu } d x ^ { \nu } d x ^ { \sigma } = 2 \left( \mathrm { t r } \left[ d \zeta \otimes e \otimes e \right] + \mathrm { t r } \left[ \left[ \omega , \zeta \right] \otimes e \otimes e \right] \right)
$$

We emphasize that restricting the gauge transformations to lie in the gravitational ${ \mathfrak { s l } } ( 2 ) \oplus$ ${ \mathfrak { s l } } ( 2 )$ subalgebra does not imply that the corresponding transformation on the metric-like fields is an ordinary diffeomorphism: in (3.2) the spin-3 transformation $\xi _ { \mu \nu }$ can be nonvanishing even when $\zeta$ lies only in the ${ \mathfrak { s l } } ( 2 )$ spanned by $\boldsymbol { L } _ { 0 , \pm 1 }$ (unless we also restrict the dreibein $e$ to the same ${ \mathfrak { s l } } ( 2 )$ ). The gauge transformation that corresponds to pure diffeomorphism is simply given by $g ^ { \mu \nu } e _ { \mu } \mathrm { t r } [ e _ { \nu } \zeta ]$ (cf. the first equation in (3.2) and eq. (3.18) of [8]).

We now separate $\zeta$ into positive, zero and negative powers of $\rho$ as

$$
\zeta = \zeta _ { + } + \zeta _ { 0 } + \zeta _ { - }
$$

where

$$
\zeta _ { 0 } = \frac { 1 } { 2 } \sum _ { s = 2 } ^ { N } ( \alpha _ { 0 } ^ { s } - \tilde { \alpha } _ { 0 } ^ { s } ) W _ { 0 } ^ { ( s ) }
$$

Generalizing the discussion of the previous chapter we expect that $\zeta _ { 0 }$ parametrizes Weyl and $\mathcal { W }$ -Weyl transformations of the boundary fields and that $\zeta _ { + }$ can be used to transform the connections back to FG gauge.15 We therefore define

$$
\sigma _ { s } \equiv \frac { 1 } { 2 } \big ( \alpha _ { 0 } ^ { s } - \tilde { \alpha } _ { 0 } ^ { s } \big )
$$

as the parameters of $\mathcal { W }$ -Weyl transformations.

To make the discussion more concrete, we discuss in detail the case of ${ \mathfrak { s l } } ( 3 )$ .With principal embedding, there are two metric-like fields: one spin-2 and one spin-3. For the following discusion it isconvenient touse the generators W±2,E±=E)，F=E), and $L _ { 0 } , W _ { 0 }$ defined in Appendix A.

We expand $a _ { i }$ in this basis with coefficients $\scriptstyle { \frac { 1 } { 2 } } w _ { i } ^ { ( \pm 2 ) }$ ， $e _ { i } ^ { ( \pm ) }$ ， $f _ { i } ^ { ( \pm ) }$ ， $a _ { i }$ and $b _ { i }$ , all functions of the boundary coordinates. Conjugation by $b$ gives $A _ { i }$ by simply replacing $W _ { m } \to \rho ^ { - m } W _ { m }$ ， and conjugation by $\tilde { b }$ gives ${ \tilde { A } } _ { i }$ by replacing $W _ { m } \to \rho ^ { m } W _ { m }$

The components of the metric and the spin-3 field are (cf. (3.3, 3.4))

$$
G _ { \mu \nu } = \frac { 1 } { \mathrm { t r } \left[ ( L _ { 0 } ) ^ { 2 } \right] } \mathrm { t r } \left( e _ { \mu } e _ { \nu } \right) \qquad \mathrm { a n d } \qquad \Psi _ { \mu \nu \lambda } = \frac { 2 } { 3 } \mathrm { t r } \left( e _ { ( \mu } e _ { \nu } e _ { \lambda ) } \right)
$$

where the parenthesis in $\Psi$ denotes symmetrization,and the normalization factor $\frac { 2 } { 3 }$ for $\Psi$ is chosen for later convenience. As

$$
G _ { \rho i } = { \frac { 1 } { 2 \rho } } \left( a _ { i } - \tilde { a } _ { i } \right) \qquad \mathrm { a n d } \qquad \Psi _ { \rho \rho i } = { \frac { 1 } { 2 \rho ^ { 2 } } } \left( b _ { i } - \tilde { b } _ { i } \right)
$$

they are not yet in FG gauge. This can be fixed via a residual gauge transformation (3.8). For this it suffices to use $u = u _ { + }$ and $\tilde { u } = \tilde { u } _ { - }$ (which have no effect on the boundary zweibein).

This being done we can easily work out the components of $G$ and $\Psi$ . As we have already remarked, from the CS construction it is a priori obvious that their FG expansions are finite. We will only give the leading components though:

$$
G _ { \rho \rho } = \frac { 1 } { \rho ^ { 2 } } , \qquad G _ { \rho i } = 0 , \qquad \mathrm { a n d } \qquad G _ { i j } = \frac { 1 } { \rho ^ { 2 } } \sum _ { n = - 1 } ^ { 3 } \rho ^ { 2 n } \overset { ( 2 n ) } { g _ { i j } }
$$

with

$$
\begin{array} { c } { { \displaystyle { \stackrel { ( - 2 ) } { g } = - \frac { 1 } { 4 } \left[ w _ { i } ^ { ( + 2 ) } \tilde { w } _ { j } ^ { ( - 2 ) } \right] d x ^ { i } d x ^ { j } } } } \\ { { \displaystyle { \stackrel { ( 0 ) } { g } = - \frac { 1 } { 4 } \left[ e _ { i } ^ { ( + ) } \tilde { e } _ { j } ^ { ( - ) } + f _ { i } ^ { ( + ) } \tilde { f } _ { j } ^ { ( - ) } \right] d x ^ { i } d x ^ { j } } } } \end{array}
$$

Here and for the spin-3 field below, the coeffcients are assumed to satisfy the flatness condition (2.30).16 The spin-3 field with

$$
\Psi _ { \rho \rho \rho } = 0 , \qquad \Psi _ { \rho \rho i } = 0 ,
$$

and

$$
\Psi _ { i j k } = \frac { 1 } { \rho ^ { 4 } } \sum _ { n = 0 } ^ { 4 } \rho ^ { 2 n } \stackrel { ( 2 n ) } { \psi } _ { i j k } \qquad \mathrm { a n d } \qquad \Psi _ { \rho i j } = \frac { 1 } { \rho ^ { 3 } } \sum _ { n = 0 } ^ { 2 } \rho ^ { 2 n } \stackrel { ( 2 n ) } { \psi } _ { \rho i j }
$$

has the leading components

$$
\begin{array} { r l } { { \stackrel { \scriptscriptstyle ( 0 ) } { \psi } = } } & { { \frac { 1 } { 4 } \left[ w _ { i } ^ { ( + 2 ) } \tilde { e } _ { j } ^ { ( - ) } \tilde { f } _ { k } ^ { ( - ) } - \tilde { w } _ { i } ^ { ( - 2 ) } e _ { j } ^ { ( + ) } f _ { k } ^ { ( + ) } \right] d x ^ { i } d x ^ { j } d x ^ { k } } } \\ { { \stackrel { \scriptscriptstyle ( 0 ) } { \psi } _ { \rho } = } } & { { \frac { 1 } { 2 } \left[ e _ { i } ^ { ( + ) } \tilde { e } _ { j } ^ { ( - ) } - f _ { i } ^ { ( + ) } \tilde { f } _ { j } ^ { ( - ) } \right] d x ^ { i } d x ^ { j } } } \end{array}
$$

We see that generically $^ { ( - 2 ) } _ { g } \ \ne \ 0$ ,i.e. the asymptotic behavior of the bulk metric is changed due to the strong back-reaction of the spin-3 field on the metric. The residual gauge transformations parametrized by $\sigma _ { 2 }$ and $\sigma _ { 3 }$ act in a simple way on the leading terms of the FG expansion of the metric-like fields:17

$$
{ \stackrel { ( - 2 ) } { g _ { i j } } } \to e ^ { 4 { \sigma } _ { 2 } { \bf \sigma } _ { g _ { i j } } ^ { ( - 2 ) } } \qquad \mathrm { a n d } \qquad { \stackrel { ( 0 ) } { \psi } } _ { i j k } \to e ^ { 4 { \sigma } _ { 2 } } \left( { \stackrel { ( 0 ) } { \psi } } _ { i j k } + { \textstyle \frac { 4 } { 3 } } { \stackrel { ( - 2 ) } { g } } _ { ( i j } \partial _ { k ) } \sigma _ { 3 } \right)
$$

The boundary spin-3 field has the same Weyl weight as the metric, which contradicts the expectation from the boundary analysis.18

There are two ways to proceed. One is to redefine the radial coordinate $\rho \to \rho ^ { 2 }$ . The metric (3.31) is still asymptotically AdS,but with half the original radius. The leading term $g ^ { ( - 2 ) }$ now plays the role of the boundary metric. Comparing this to the boundary metric $g ^ { ( 0 ) }$ in (2.38) for pure gravity, we see that here $W _ { \pm 2 }$ serve the role of $L _ { \pm 1 }$ there. With $[ W _ { 2 } , W _ { - 2 } ] = 4 L _ { 0 }$ ， we conclude that instead of $\{ L _ { 0 , \pm 1 } \}$ ， the gravitational ${ \mathfrak { s l } } ( 2 )$ is now $\{ \textstyle { \frac { 1 } { 2 } } W _ { 2 } , { \frac { 1 } { 2 } } L _ { 0 } , - { \frac { 1 } { 2 } } W _ { - 2 } \}$ . This was interpreted in [26, 27] as a flow from a CFT with （20 $\mathcal { W } _ { 3 }$ symmetry, triggered by an irrelevant operator (i.e. the spin-3 current coupled to the boundaryspi-3feld)，toCith $\mathcal { W } _ { 3 } ^ { ( 2 ) }$ syetryoeoa by choosing a diagonal embedding $\mathrm { S L } ( 2 ) \hookrightarrow \mathrm { S L } ( 3 )$ , rather than the principal embedding. The different embedding entails a different spectrum in the boundary CFT: The spin-2 field (i.e. the metric) still exists and is defined via (3.3), but now with the dreibein $e$ only spanning the new gravitational ${ \mathfrak { s l } } ( 2 )$ [29]. In addition,there is one spin-1 and two spin- $\frac { 3 } { 2 }$ fields. One can compute the FG expansion of these fields as in (3.31) and (3.34). We will not pursue this line further in this paper.

Instead, we will proceed by observing (see the explicit expression (3.31） for $g ^ { ( - 2 ) }$ ）that for well-chosen connections $( a , \tilde { a } )$ , i.e. when either or both of $w _ { i } ^ { ( + 2 ) }$ and $\tilde { w } _ { i } ^ { ( - 2 ) }$ vanish, the $g ^ { ( - 2 ) }$ term in the FG expansion of the metric is absent and the asymptotic behavior of the bulk metric is preserved. We will consider both options later.19

We will now discuss generalized Weyl anomalies. Here we do not have the option to discuss them in terms of the metric-like fields since their bulk action is not known. We therefore have to resort to the Chern-Simons formulation. We recall the discussion in Chapter 2 and note that (2.43) is nothing but the $\mathcal { O } ( \rho ^ { 0 } )$ term of the change of the action under a gauge transformation with parameter $\lambda = \sigma L _ { 0 } = - \tilde { \lambda }$ . This was expected from our discussion of PBH transformations as specific gauge transformations. In this chapter we identified the $\mathcal { W }$ -Weyl transformations as the diagonal gauge transformations generated by the Cartan directions in ${ \mathfrak { s l } } ( N )$ . This therefore leads us to conjecture the change of the effective action, which is now a non-local functional of the metric and the higher-spin boundary fields

$$
\delta _ { \sigma _ { s } } W = \frac { k } { 2 \pi } \int _ { \partial \mathcal { M } } \sigma _ { s } \mathrm { t r } \left[ W _ { 0 } ^ { ( s ) } ( d A + d \tilde { A } ) \right]
$$

as the direct generalization of (2.43). This should be expressible in terms of ‘generalized curvatures', which respect the covariance of $W$ under generalized diffeomorphisms. In the spin-two case this is what we did in (2.44)，but the higher-spin geometry, which would allow us to rewrite the r.h.s. of (3.37), is not known. Even for $s = 2$ , if there is a nontrivial higher-spin background $\psi$ to which the two-dimensional field theory with $\mathcal { W }$ -symmetry is coupled, the anomaly is not proportional to the Ricci scalar, because of the presence of higher-spin sources and because they transform as well under $\sigma _ { 2 }$ . Since we only have control over the Weyl variations but not over the variations of the metric and the higherspin fields separately, we cannot, in general, compute the trace of the energy-momentum tensor and the conserved higher-spin currents. We will come back to this when we discuss specific gauges, which is what we will do next.

# 3.2 Conformal gauge

We start with the conformal gauge where we turn on only those sources (metric and higher-spin backgrounds) that couple to the trace of the energy-momentum tensor and the spin- $s$ currents. They receive a vev only through the need to regularize, which introduces counter-terms that break Weyl and $\mathcal { W }$ -Weyl symmetries. Since the operators to which the sources couple vanish, the boundary CFT is not perturbed by any irrelevant operator and we do not encounter the strong back-reaction that changes the asymptotics.

The starting point is the generalization of (2.50)

$$
a _ { 0 } = \left( L _ { 1 } + \pmb { q } ( z ) \right) d z \qquad \mathrm { w i t h } \qquad \pmb { q } ( z ) = \sum _ { s = 2 } ^ { N } \frac { q _ { s } ( z ) } { t _ { s - 1 } ^ { ( s ) } } W _ { - s + 1 } ^ { ( s ) }
$$

and similarly for $\tilde { a } _ { 0 }$ ： $\textbf { \em q } = \textbf { \em 0 }$ gives the AdS $_ 3$ vacuum and $q _ { s }$ is the vev of the $( d z ) ^ { s }$ component of the spin- $s$ current of the boundary field theory in a trivial background. The normalization of the $q _ { s }$ is for later convenience. The connections $( a _ { 0 } , \tilde { a } _ { 0 } )$ are obviously in FG gauge.

The flat connection (3.38) can be related to an asymptotic AdS solution via gauge transformations $( g , \tilde { g } )$ that are finite on the boundary. The gauge transformations $g \left( \tilde { g } \right)$ that transform (3.38) to the conformal gauge include negative (positive) modes and zero modes. We write the group element in factorized form as

$$
g = M ^ { - 1 } e ^ { \phi }
$$

where the first (second) factor is the negative (zero) mode part. The notation will be explained momentarily.

To find $M$ ，we use the fact that two-dimensional $\mathcal { W }$ -gravity in conformal gauge is related to Toda theory and recall the following construction, well-known from the theory of integrable hierarchies and from $\mathcal { W }$ -algebras [31]: given a generic element $\omega \in { \mathfrak { s l } } ( N )$ （204号 along the Cartan subalgebra (spanned by the zero modes) there exists a unique group element $M$ which is generated by negative modes only and which transforms $L _ { 1 } - \omega$ into $L _ { 1 } - \mathcal { \Omega }$ where $\begin{array} { r } { \pmb { \mathcal { Q } } = \sum _ { s = 2 } ^ { N } \frac { Q _ { s } } { t ^ { ( s ) } } W _ { - s + 1 } ^ { ( s ) } } \end{array}$ $^ { 2 0 }$ d ${ \mathfrak { s l } } ( N )$

$$
M ^ { - 1 } ( L _ { 1 } - \omega ) M + M ^ { - 1 } \partial M = L _ { 1 } - \pmb { \mathscr { Q } }
$$

The transformation (3.4O) is known as Miura transformation. If we take $\omega$ to be $\partial \Phi$ where $\Phi$ is a vector of $( N - 1 )$ scalar fields which we refer to as Toda fields,then the Miura matrix and the $\mathcal { Q } _ { s }$ are functions of $\partial \Phi$ （204号

$$
M = M ( \partial \Phi ) \qquad { \mathrm { a n d } } \qquad Q _ { s } = \mathcal { Q } _ { s } ( \partial \Phi )
$$

and $\mathcal { Q } _ { s }$ are the conserved charges of Toda theory.21 It is known that they generate a classical $\mathcal { W } _ { N }$ algebra (in the same way as $\mathcal { Q } _ { 2 }$ generates the Virasoro algebra). Applying the inverse Miura transformation to $a _ { 0 }$ and using (3.40) gives

$$
\begin{array} { l } { { a _ { z }  M \big ( L _ { 1 } + \pmb q \big ) M ^ { - 1 } - \partial M M ^ { - 1 } = L _ { 1 } - \partial \pmb \Phi + M \big ( \pmb q + \pmb \mathcal { Q } ( \pmb \Phi ) \big ) M ^ { - 1 } } } \\ { { \qquad } } \\ { { a _ { \bar { z } }  - \bar { \partial } M M ^ { - 1 } } } \end{array}
$$

For the zero-mode part we split (non-uniquely, cf. (2.49))

$$
\Phi = \phi + { \bar { \phi } }
$$

This second gauge transformation generates ${ \mathcal W } _ { s }$ -Weyl transformations and, at the same time,brings the connection into FG gauge (3.13). The combined gauge transformation generated by (3.39) generates a finite PBH transformation of (3.38).

We now specify to $N = 3$ and refer to Appendix B for general $N$ . Using the shorthand $W _ { m } \equiv W _ { m } ^ { ( 3 ) }$ ,we expand

$$
{ \pmb \Phi } \equiv \Phi _ { 1 } { \cal H } ^ { ( 1 ) } + \Phi _ { 2 } { \cal H } ^ { ( 2 ) } = \Phi _ { L } L _ { 0 } + \Phi _ { W } { \cal W } _ { 0 }
$$

which implies

$$
\begin{array} { r } { \Phi _ { L } = \frac { 1 } { 2 } \bigl ( \Phi _ { 1 } + \Phi _ { 2 } \bigr ) \qquad \mathrm { a n d } \qquad \Phi _ { W } = \frac { 3 } { 2 } \bigl ( \Phi _ { 1 } - \Phi _ { 2 } \bigr ) } \end{array}
$$

The Miura matrix $M ( \partial \Phi ) = \exp ( h _ { - } )$ is

$$
\begin{array} { r } { h _ { - } = \frac { 1 } { 2 } \partial \Phi _ { L } L _ { - 1 } + \frac { 1 } { 3 } \partial \Phi _ { W } W _ { - 1 } + \left( \frac { 1 } { 6 } \partial \Phi _ { L } \partial \Phi _ { W } - \frac { 1 } { 1 2 } \partial ^ { 2 } \Phi _ { W } \right) W _ { - 2 } } \end{array}
$$

It generates the two Toda charges

$$
\begin{array} { l } { { { \mathcal Q } _ { 2 } ( \partial \Phi ) = - ( \partial \Phi _ { 1 } ) ^ { 2 } - ( \partial \Phi _ { 2 } ) ^ { 2 } + \partial \Phi _ { 1 } \partial \Phi _ { 2 } + \partial ^ { 2 } \Phi _ { 1 } + \partial ^ { 2 } \Phi _ { 2 } } } \\ { { \ \qquad = - ( \partial \Phi _ { L } ) ^ { 2 } + 2 \partial ^ { 2 } \Phi _ { L } - \frac 1 3 ( \partial \Phi _ { W } ) ^ { 2 } } } \\ { { \ } } \\ { { \mathcal Q } _ { 3 } ( \partial \Phi ) = \frac 1 2 \partial ^ { 3 } \Phi _ { 1 } - \frac 1 2 \partial ^ { 2 } \Phi _ { 1 } \partial \Phi _ { 2 } + ( \partial \Phi _ { 1 } ) ^ { 2 } \partial \Phi _ { 2 } - \partial \Phi _ { 1 } \partial ^ { 2 } \Phi _ { 1 } - ( \Phi _ { 1 }  \Phi _ { 2 } ) }  \\ { { \ \qquad = \frac 2 3 ( \partial \Phi _ { L } ) ^ { 2 } \partial \Phi _ { W } - \frac 2 { 2 7 } ( \partial \Phi _ { W } ) ^ { 3 } - \frac 1 3 \partial ^ { 2 } \Phi _ { L } \partial \Phi _ { W } - \partial \Phi _ { L } \partial ^ { 2 } \Phi _ { W } + \frac 1 3 \partial ^ { 3 } \Phi _ { W } } } \end{array}
$$

and,combined with $e ^ { \phi }$ the ${ \mathfrak { s l } } ( 3 )$ connection in FG gauge from which we compute the dreibein and from there the metric-like fields.

Since in conformal gauge there is no strong back-reaction from the spin-three field, the FG expansion of the dreibein (3.20) starts with $\stackrel { ( 0 ) } { \boldsymbol { \mathcal { e } } }$ as in the ${ \mathfrak { s l } } ( 2 )$ case:

$$
\begin{array} { l } { { \stackrel { \scriptscriptstyle ( 0 ) } { e } = - { \cal L } _ { 0 } d \rho - { \frac { 1 } { \sqrt 2 } } \displaystyle \sum _ { i = 1 } ^ { 2 } \left[ e ^ { \alpha _ { i } } E _ { - } ^ { ( i ) } d z + h . c . \right] ~ , ~ \stackrel { \scriptscriptstyle ( 1 ) } { e } = 0 } } \\ { { \stackrel { \scriptscriptstyle ( 2 ) } { e } = { \frac { 1 } { \sqrt 2 } } \displaystyle \sum _ { i = 1 } ^ { 2 } \left[ e ^ { - \alpha _ { i } } E _ { + } ^ { ( i ) } d t _ { i } + h . c . \right] ~ , ~ \stackrel { \scriptscriptstyle ( 3 ) } { e } = { \frac { 1 } { 2 } } \left[ e ^ { - \phi _ { 1 } - \phi _ { 2 } } W _ { - 2 } d w + \mathrm { h . c . } \right] } } \end{array}
$$

with $\left( \alpha _ { 1 } , \alpha _ { 2 } \right) = \left( 2 \phi _ { 1 } - \phi _ { 2 } , 2 \phi _ { 2 } - \phi _ { 1 } \right)$ . We then find for the FG expansion (3.22) of the metric

$$
\begin{array} { l } { { \stackrel { \scriptscriptstyle ( 0 ) } { g } = \frac { 1 } { 2 } \big ( e ^ { 2 \Phi _ { 1 } - \Phi _ { 2 } } + e ^ { 2 \Phi _ { 2 } - \Phi _ { 1 } } \big ) d z d \bar { z } = e ^ { \Phi _ { L } } \cosh ( \Phi _ { W } ) d z d \bar { z } } } \\ { { \stackrel { \scriptscriptstyle ( 2 ) } { g } = - \frac { 1 } { 2 } \big ( d t _ { 1 } + d t _ { 2 } \big ) d z + \mathrm { c . c . } = ( \partial \bar { \partial } \Phi _ { L } \big ) d z d \bar { z } + \frac { 1 } { 4 } T d z ^ { 2 } + \frac { 1 } { 4 } \bar { T } d \bar { z } ^ { 2 } } } \\ { { \stackrel { \scriptscriptstyle ( 4 ) } { g } = \frac { 1 } { 2 } e ^ { \Phi _ { 2 } - 2 \Phi _ { 1 } } | d t _ { 1 } | ^ { 2 } + \frac { 1 } { 2 } e ^ { \Phi _ { 1 } - 2 \Phi _ { 2 } } | d t _ { 2 } | ^ { 2 } \ ~ \stackrel { \scriptscriptstyle ( 6 ) } { g } = e ^ { - \Phi _ { 1 } - \Phi _ { 2 } } | d w | ^ { 2 } } } \end{array}
$$

Here we have defined

$$
\begin{array} { l l l } { { d t _ { i } \equiv - { \frac { 1 } { 4 } } T d z - { \frac { 1 } { 2 } } \partial { \bar { \partial } } \Phi _ { i } d { \bar { z } } \quad } } & { { \mathrm { a n d } } } & { { \quad d w \equiv { \frac { 1 } { 4 } } { \tilde { W } } d z - { \frac { 1 } { 4 } } K d { \bar { z } } } } \end{array}
$$

and

$$
T \equiv q _ { 2 } + Q _ { 2 } \qquad W \equiv q _ { 3 } + Q _ { 3 }
$$

and finally $^ { \cdot 2 2 }$

$$
\begin{array} { l } { { \tilde { W } \equiv W - \frac { 1 } { 3 } \partial \Phi _ { W } T } } \\ { { \nonumber } } \\ { { K \equiv ( \partial \bar { \partial } \Phi _ { L } ) ( \partial \Phi _ { W } ) + \frac { 1 } { 3 } ( \partial \Phi _ { L } ) ( \partial \bar { \partial } \Phi _ { W } ) - \frac { 1 } { 3 } \partial ^ { 2 } \bar { \partial } \Phi _ { W } } } \end{array}
$$

As in the ${ \mathfrak { s l } } ( 2 )$ case, $( T , W )$ are related to the vev of the stress energy $\mathbfcal { T }$ and spin-3 current $W$ by a rescaling: $\begin{array} { r } { ( T , W ) = \frac { 1 } { k } ( \pmb { T } , \pmb { W } ) } \end{array}$ with $k = \textstyle { \frac { c } { 2 4 } }$

In the ${ \mathfrak { s l } } ( 2 )$ limit $\Phi _ { W } \to 0$ , the boundary metric reduces to $e ^ { \Phi _ { L } } d z d \bar { z }$ . By construction, the spin-3 field $\Psi$ is in FG gauge, with $\Psi _ { \rho \rho \rho } = \Psi _ { \rho \rho i } = 0$ .The $\rho$ -expansion (3.34) of $\Psi _ { i j k }$ （204号 starts only at $\mathcal { O } ( \rho ^ { 0 } )$ with

$$
\begin{array} { l } { { \stackrel { \scriptscriptstyle ( 4 ) } { \psi } = 2 d w d z ^ { 2 } + \mathrm { c . c . } \qquad \stackrel { \scriptscriptstyle ( 6 ) } { \psi } = - d w d z \bigl ( e ^ { - 2 \Phi _ { 1 } + \Phi _ { 2 } } d \bar { t } _ { 1 } + e ^ { - 2 \Phi _ { 2 } + \Phi _ { 1 } } d \bar { t } _ { 2 } \bigr ) + \mathrm { c . c . } } } \\ { { \stackrel { \scriptscriptstyle ( 8 ) } { \psi } = e ^ { - \Phi _ { 1 } - \Phi _ { 2 } } d w d \bar { t } _ { 1 } d \bar { t } _ { 2 } + \mathrm { c . c . } } } \end{array}
$$

For the expansion of $\Psi _ { \rho i j }$ we find

$$
\begin{array} { l c r } { { \stackrel { \scriptscriptstyle ( 0 ) } { \psi } _ { \rho } = - 2 e ^ { \Phi _ { L } } \sinh ( \Phi _ { W } ) d z d \bar { z } } } & { { \stackrel { \scriptscriptstyle ( 2 ) } { \psi } _ { \rho } = - \frac 2 3 \partial \bar { \partial } \Phi _ { W } d z d \bar { z } } } \\ { { \stackrel { \scriptscriptstyle ( 4 ) } { \psi } _ { \rho } = - e ^ { \Phi _ { 2 } - 2 \Phi _ { 1 } } | d t _ { 1 } | ^ { 2 } + e ^ { \Phi _ { 1 } - 2 \Phi _ { 2 } } | d t _ { 2 } | ^ { 2 } } } \end{array}
$$

0 We observe that there is no boundary spin-three field $\psi _ { i j k }$ in conformal gauge. Instead $\psi _ { \rho } ^ { ( 0 ) }$ is non-zero and depends on the two Toda fields. Note also that the vev of the spin-3 current appears at $\mathcal { O } ( \rho ^ { 0 } )$ , which is a generic feature, valid for all spins and in all gauges.

Since the Toda fields are introduced via a finite PBH transformation on the connection (3.38), further PBH transformations are very transparent. The PBH transformation between two solutions labeled by $\left\{ \Phi _ { 1 } \right\}$ and $\left\{ \Phi _ { 2 } \right\}$ is simply

$$
g = ( g _ { 1 } ) ^ { - 1 } g _ { 2 }
$$

The effect on a solution in conformal gauge is the shift of the conformal modes ( $\mathbf { \Phi } _ { s } ^ { \prime } = L , W$ （号

$$
\Phi _ { s }  \Phi _ { s } + 2 \sigma _ { s }
$$

With $\left( \sigma _ { L } , \sigma _ { W } \right) \equiv \left( \sigma _ { 2 } , \sigma _ { 3 } \right)$ the boundary metric $\stackrel { ( 0 ) } { g }$ transforms as

$$
{ \delta } _ { \sigma _ { 2 } } \stackrel { ( 0 ) } { g } = 2 { \sigma } _ { 2 } \stackrel { ( 0 ) } { g } \qquad \mathrm { a n d } \qquad { \delta } _ { \sigma _ { 3 } } \stackrel { ( 0 ) } { g } = - { \sigma } _ { 3 } \stackrel { ( 0 ) } { \psi } _ { \rho }
$$

22 $K$ vanishes upon using Toda equation $\partial \partial \Phi _ { 1 } = c e ^ { 2 \Phi _ { 1 } - \Phi _ { 2 } }$ and $\partial \partial \Phi _ { 2 } = c e ^ { 2 \Phi _ { 2 } - \Phi _ { 1 } }$

There is no boundary spin-3 field and the leading term of $\Psi _ { \rho i j }$ transforms as

$$
\begin{array} { r } { \delta _ { \sigma _ { 2 } } \stackrel { ( 0 ) } { \psi } _ { \rho } = 2 \sigma _ { 2 } \stackrel { ( 0 ) } { \psi } _ { \rho } \qquad \mathrm { a n d } \qquad \delta _ { \sigma _ { 3 } } \stackrel { ( 0 ) } { \psi } _ { \rho } = - 4 \sigma _ { 3 } \stackrel { ( 0 ) } { g } } \end{array}
$$

Using (3.37) and (B.4) one finds that the effective action transforms as

$$
\delta _ { \sigma _ { s } } W = \frac { t _ { 0 } ^ { ( s ) } k } { \pi } \int _ { \partial \mathcal { M } } \sigma _ { s } \partial { \bar { \partial } } \Phi _ { s } d z \wedge d { \bar { z } }
$$

from which one reads off the ${ \mathcal W } _ { s }$ anomaly:

$$
\sqrt { g } \mathcal { A } _ { s } = ( 2 t _ { 0 } ^ { ( s ) } k ) \partial \bar { \partial } \Phi _ { s }
$$

This can be integrated to

$$
W = \sum _ { s } \frac { t _ { 0 } ^ { ( s ) } k } { 4 \pi } \int _ { \partial \mathcal { M } } \Phi _ { s } \partial \bar { \partial } \Phi _ { s } d z \wedge d \bar { z }
$$

This generalizes,in a natural way， eq.(2.52) to the case where several Toda felds are present and we can view $W$ as the generalization of the non-local Polyakov action which has become local in conformal gauge. This agrees with [32]; but what is puzzling is that here we do not have a boundary spin-3 feld - $\psi _ { i j k } ^ { ( 0 ) } = 0$ -but instead $\psi _ { \rho i j } ^ { ( 0 ) } \neq 0$ ：

We note that for $s = 2$ ，using (3.1) and (3.49) we find from (3.60)

$$
\mathcal { A } _ { 2 } = \frac { c } { 6 } \mathrm { t r } \big ( \overset { ( 2 ) } { \boldsymbol { g } } \big )
$$

as for pure gravity. However, except for $N = 2$ this is not proportional to the Ricci scalar of the boundary metric. For $N > 2$ ，since higher-spin fields also transform under the Weyl transformation, $\mathcal { A } _ { 2 }$ contains contributions from the trace anomaly of the energymomentum tensor and from higher-spin background fields,and it reduces to $T _ { \ i } ^ { i }$ only if all scalars except $\Phi _ { 2 }$ are switched off (the ${ \mathfrak { s l } } ( 2 )$ limit).

# 3.3 （204号 $\mu$ - gauge

The second gauge choice is what we called the $\mu$ -gauge in Chapter 2. In this gauge higherspin sources $\{ \mu _ { s } \}$ are turned on while the conformal modes are set to zero. We explain （204号 ${ \mathfrak { s l } } ( 3 )$ in detail, where in addition to $( \mu _ { 2 } , \bar { \mu } _ { 2 } )$ ， the sources for $( T , T )$ ，we can also turn on （204 $\left( \mu _ { 3 } , \bar { \mu } _ { 3 } \right)$ ， the sources for $( W , { \bar { W } } )$ .23 We will refer to the pair $( \mu _ { 2 } , \mu _ { 3 } )$ as the generalized complex structure and to $( T , W )$ as the generalized projective structure.

Just as the Virasoro Ward identity (2.56) can be obtained as the compatibility condition of the complex structure $\mu$ and the projective structure $T$ ,the $\mathcal { W } _ { 3 }$ Ward identities can be derived from the compatibility condition between the generalized structures [33].

In analogy to (2.57) and (2.58) for ${ \mathfrak { s l } } ( 2 )$ ，the linear system for ${ \mathfrak { s l } } ( 3 )$ acts on a 3-vector $\Psi$ whose last component we denote by $\psi$ . The flat ${ \mathfrak { s l } } ( 3 )$ connection that encodes the $\mathcal { W } _ { 3 }$ （204号 Ward identity is

$$
a _ { z } = L _ { 1 } + q \qquad \mathrm { a n d } \qquad a _ { \bar { z } } = \mu + \bar { \omega } + \gamma + \beta
$$

The connection $a$ is in highest weight gauge: in the charge vector

$$
\begin{array} { r } { \pmb q = - \frac { 1 } { 4 } T L _ { - 1 } + \frac { 1 } { 4 } W W _ { - 2 } } \end{array}
$$

$( T , W )$ ，the rescaled （by $1 / k$ ） stress energy and spin-3 current，are along the highest weight directions (L-1,W-2)inaz (the prefactorsaredue tothenormalizationt24 and $t _ { 2 } ^ { ( 3 ) } = 4$ ); in the source vector

$$
\pmb { \mu } = \mu _ { 2 } L _ { 1 } + \mu _ { 3 } W _ { 2 }
$$

$\left( \mu _ { 2 } , \mu _ { 3 } \right)$ are along the lowest weight directions $( L _ { 1 } , W _ { 2 } )$

$$
\bar { \omega } = \bar { \omega } _ { 2 } L _ { 0 } + \bar { \omega } _ { 3 } W _ { 0 }
$$

is along the zero modes and, finally,

$$
\begin{array} { r } { \gamma = \gamma W _ { 1 } \qquad \mathrm { a n d } \qquad \beta = \beta _ { 1 } L _ { - 1 } + \beta _ { 2 } W _ { - 1 } + \beta _ { 3 } W _ { - 2 } } \end{array}
$$

Requiring flatness of $a$ gives eight equations, six of which can be solved algebraically for $\bar { \omega } , \gamma$ ，and $\beta$ ：：

$$
\begin{array} { c c } { { \gamma = - \partial \mu _ { 3 } } } & { { \bar { \omega } _ { 2 } = - \partial \mu _ { 2 } } } & { { \bar { \omega } _ { 3 } = \frac { 1 } { 2 } ( \partial ^ { 2 } - T ) \mu _ { 3 } } } \\ { { } } & { { } } \\ { { \beta _ { 1 } = - \frac { 1 } { 2 } \partial \bar { \omega } _ { 2 } - \frac { 1 } { 4 } \mu _ { 2 } T - \frac { 1 } { 2 } \mu _ { 3 } W , } } & { { \beta _ { 2 } = - \frac { 1 } { 3 } \partial \bar { \omega } _ { 3 } - \frac { 1 } { 4 } \gamma T , } } & { { \beta _ { 3 } = \frac { 1 } { 4 } \mu _ { 2 } W - \frac { 1 } { 8 } \bar { \omega } _ { 3 } T - \frac { 1 } { 4 } \mu _ { 3 } T . } } \end{array}
$$

The remaining two equations are the two $\mathcal { W } _ { 3 }$ Ward identities:24

$$
\big ( \bar { \partial } - \mu _ { 2 } \partial - 2 \partial \mu _ { 2 } \big ) T = - 2 \partial ^ { 3 } \mu _ { 2 } + \big ( 2 \mu _ { 3 } \partial + 3 \partial \mu _ { 3 } \big ) W
$$

for $T$ and

$$
{ \begin{array} { r l } & { \left( { \bar { \partial } } - \mu _ { 2 } \partial - 3 \partial \mu _ { 2 } \right) W } \\ & { \qquad = { \frac { 1 } { 6 } } \partial ^ { 5 } \mu _ { 3 } - \left( { \frac { 1 } { 6 } } \mu _ { 3 } \partial ^ { 3 } + { \frac { 3 } { 4 } } \partial \mu _ { 3 } \partial ^ { 2 } + { \frac { 5 } { 4 } } \partial ^ { 2 } \mu _ { 3 } \partial + { \frac { 5 } { 6 } } \partial ^ { 3 } \mu _ { 3 } \right) T + { \frac { 1 } { 3 } } ( \mu _ { 3 } \partial + 2 \partial \mu _ { 3 } ) T } \end{array} }
$$

for $W$ . Together they encode the $\mathcal { W } _ { 3 }$ -algebra. The first term on the r.h.s. of each identity is the anomaly. The ${ \mathfrak { s l } } ( 3 )$ analogues of the pair of equations (2.59) on $\psi$ are a third-order holomorphic equation

$$
\left( \partial ^ { 3 } - T \partial - { \textstyle \frac { 1 } { 2 } } \partial T + W \right) \psi = 0
$$

and

$$
{ \Big [ } { \bar { \partial } } + \mu _ { 3 } \partial ^ { 2 } - ( \mu _ { 2 } + { \frac { 1 } { 2 } } \partial \mu _ { 3 } ) \partial + \partial \mu _ { 2 } + { \frac { 1 } { 6 } } \partial ^ { 2 } \mu _ { 3 } - { \frac { 2 } { 3 } } \mu _ { 3 } T { \Big ] } \psi = 0
$$

The Ward identities (3.69) and (3.70) can be obtained as compatibility conditions between (3.71) and (3.72).

As in the case of ${ \mathfrak { s l } } ( 2 )$ ， these Ward identities can also be understood directly as compatibility conditions of the generalized projective and complex structures. To explain this, we write the connection, which is pure gauge, in the form

$$
a = g ^ { - 1 } d g
$$

We make a Gauss decomposition Ansatz for $g$ where, for convenience we use the Chevalley basis

$$
g = e ^ { w _ { 2 } W _ { 2 } + e _ { + } E _ { + } + f _ { + } F _ { + } } e ^ { - \phi _ { 1 } H ^ { ( 1 ) } - \phi _ { 2 } H ^ { ( 2 ) } } e ^ { w _ { - 2 } W _ { - 2 } + e _ { - } E _ { - } + f _ { - } F _ { - } }
$$

Requiring $a$ to be in highest weight gauge gives

$$
\begin{array} { r } { \partial w _ { 2 } = \frac { 1 } { 4 } \big ( f _ { + } \partial e _ { + } - e _ { + } \partial f _ { + } \big ) , } \end{array}
$$

relates the $+ 1$ modes to the zero mode:

$$
\partial e _ { + } = - \sqrt { 2 } e ^ { 2 \phi _ { 1 } - \phi _ { 2 } } \qquad \mathrm { a n d } \qquad \partial f _ { + } = - \sqrt { 2 } e ^ { 2 \phi _ { 2 } - \phi _ { 1 } }
$$

and solves all negatives modes in terms of the zero modes

$$
e _ { - } = \frac { 1 } { \sqrt { 2 } } \partial \phi _ { 1 } , \qquad f _ { - } = \frac { 1 } { \sqrt { 2 } } \partial \phi _ { 2 } , \qquad w _ { - 2 } = \frac { 1 } { 8 } \bigl [ ( \partial \phi _ { 1 } ) ^ { 2 } - \partial ^ { 2 } \phi _ { 1 } \bigr ] - \frac { 1 } { 8 } \bigl [ ( \partial \phi _ { 2 } ) ^ { 2 } - \partial ^ { 2 } \phi _ { 2 } \bigr ] ,
$$

$( T , W )$ can be read off from the $( L _ { - 1 } , W _ { - 2 } )$ direction of $a _ { z }$ ; they are the negative of the two conserved charges (3.47) of the Toda theory with Toda fields $( \phi _ { 1 } , \phi _ { 2 } )$ .Using (3.76) we can rewrite $( T , W )$ in terms of the (holomorphic derivatives of the) two positive modes in the simple root directions, $( e _ { + } , f _ { + } )$ . These are the generalizations of the Schwarzian derivative (2.55） to ${ \mathfrak { s l } } ( 3 )$ .25

$$
\begin{array} { r c l } { { T } } & { { = } } & { { \displaystyle - \{ \frac { \partial ^ { 3 } e } { \partial e } - \frac { 4 } { 3 } ( \frac { \partial ^ { 2 } e } { \partial e } ) ^ { 2 } \} + \frac { 1 } { 6 } \frac { \partial ^ { 2 } e } { \partial e } \frac { \partial ^ { 2 } f } { \partial f } + ( e  f ) } } \\ { { } } & { { } } & { { } } \\ { { W } } & { { = } } & { { \displaystyle - \frac { 1 } { 6 } \{ \frac { \partial ^ { 4 } e } { \partial e } - 5 \frac { \partial ^ { 3 } e } { \partial e } \frac { \partial ^ { 2 } e } { \partial e } + \frac { 4 0 } { 9 } ( \frac { \partial ^ { 2 } e } { \partial e } ) ^ { 3 } \} + \frac { 1 } { 6 } \frac { \partial ^ { 3 } e } { \partial e } \frac { \partial ^ { 2 } f } { \partial f } + \frac { 5 } { 1 8 } \frac { \partial ^ { 2 } e } { \partial e } ( \frac { \partial ^ { 2 } f } { \partial f } ) ^ { 2 } - } }  \end{array}
$$

Here and later we drop the subscripts in $( e _ { + } , f _ { + } )$ for better readability. When expressed in terms of the zero modes $\phi _ { i }$ , these are simply the Toda charges. For $\boldsymbol { f } = \boldsymbol { e } = \boldsymbol { u }$ ， $W = 0$ and $T$ reduces to $T = - 2 \{ u , z \}$ ，i.e. the stress energy $\mathbfcal { T }$ reduces to the ${ \mathfrak { s l } } ( 2 )$ result

（204号 $\textstyle \pmb { T } = - \frac { c } { 1 2 } \{ u , z \}$ , cf. (2.55). For infinitesimal transformations parametrized by $\epsilon ( z )$ and （204号 $\partial \eta ( z )$ ，

$$
e = z + \epsilon ( z ) - { \textstyle \frac { 1 } { 2 } } \partial \eta ( z ) , \qquad f = z + \epsilon ( z ) + { \textstyle \frac { 1 } { 2 } } \partial \eta ( z )
$$

one finds

$$
T = - 2 \partial ^ { 3 } \epsilon , \qquad W = \frac 1 6 \partial ^ { 5 } \eta
$$

Note that $\partial \eta$ rather than $\eta$ appears in (3.79) so that for infinitesimal transformations all functions in (3.74) can be expressed in terns of $\xi$ ， $\eta$ and their (holomorphic） derivatives.

The generalization of the Beltrami equation (2.54) is obtained by solving $\left( \mu _ { 2 } , \mu _ { 3 } \right)$ from （204号 $a$ ： $\mu _ { 2 }$ and $\mu _ { 3 }$ are algebraic functions of the positive modes $( w _ { 2 } , e _ { + } , f _ { + } )$ and their derivatives (both holomorphic and anti-holomorphic). In these functions $w _ { 2 }$ only appears in the form of $\partial w _ { 2 }$ , then applying $\dot { O }$ on it and using (3.75) we can replace it in favor of $( e _ { + } , f _ { + } )$ ，and obtain two equations on $( e _ { + } , f _ { + } )$ ：

$$
\begin{array} { c } { { \displaystyle \left[ \bar { \partial } - \left( \mu _ { 2 } - \frac 1 2 \partial \mu _ { 3 } - \frac 2 3 \mu _ { 3 } \frac { \partial ^ { 2 } f } { \partial f } \right) \partial + \frac 1 3 \mu _ { 3 } \partial ^ { 2 } \right] e = 0 } } \\ { { \displaystyle \left[ \bar { \partial } - \left( \mu _ { 2 } + \frac 1 2 \partial \mu _ { 3 } + \frac 2 3 \mu _ { 3 } \frac { \partial ^ { 2 } e } { \partial e } \right) \partial - \frac 1 3 \mu _ { 3 } \partial ^ { 2 } \right] f = 0 } } \end{array}
$$

These are the ${ \mathfrak { s l } } ( 3 )$ analogues of the Beltrami equation (2.54). They agree with eqs. (4.10) in [33] after the redefinition $\begin{array} { r l } { \mu _ { 2 } \to \mu _ { 2 } - \frac { 1 } { 2 } \partial \mu _ { 3 } } \end{array}$ . The Ward identities (3.69) and (3.70) can be obtained as the compatibility conditions between them and the generalized Schwarzian derivatives (3.78). As a consistency check one can verify (3.81) by using (3.84) below, (3.71) and (3.72).

Eqs.(3.81) can be simplified to yield one algebraic equation relating $\mu _ { 2 }$ and $\mu _ { 3 }$ and one first-order differential equation for $\mu _ { 3 }$

$$
\begin{array} { c } { { \displaystyle \mu _ { 2 } = - \displaystyle \frac 1 6 \mu _ { 3 } \left( \frac { \partial ^ { 2 } e } { \partial e } - \frac { \partial ^ { 2 } f } { \partial f } \right) + \displaystyle \frac 1 2 \left( \frac { \bar { \partial } e } { \partial e } + \frac { \bar { \partial } f } { \partial f } \right) } } \\ { { \displaystyle \partial \mu _ { 3 } = - \mu _ { 3 } \left( \frac { \partial ^ { 2 } e } { \partial e } + \frac { \partial ^ { 2 } f } { \partial f } \right) - \left( \frac { \bar { \partial } e } { \partial e } - \frac { \bar { \partial } f } { \partial f } \right) } } \end{array}
$$

The Schwarzian derivative (2.55) is invariant under Mobius transformation $\textstyle u \to { \frac { a u + b } { c u + d } }$ which is a non-linear realization of SL(2). To obtain the non-linear realization of SL(3) action on $( e _ { + } , f _ { + } )$ which leaves (3.78) invariant,we use the fact that $e _ { + }$ and $f _ { + }$ can be related to the two ratios

$$
u _ { 1 } \equiv \frac { \psi _ { 1 } } { \psi _ { 3 } } \qquad \mathrm { a n d } \qquad u _ { 2 } \equiv \frac { \psi _ { 2 } } { \psi _ { 3 } }
$$

of any three independent solutions $\psi _ { i }$ of (3.71) and (3.72) as [33]

$$
f = u _ { 2 } \qquad \mathrm { a n d } \qquad e = { \frac { \partial u _ { 1 } } { \partial u _ { 2 } } }
$$

Since any linear combination of the three solution vectors $\Psi _ { i }$ of the linear system (2.57) with $a$ given in (3.63) is still a solution, the generalized Schwarzian derivatives (3.78) are invariant under the following GL(3) action

$$
u _ { 1 } \to { \frac { c _ { 1 1 } u _ { 1 } + c _ { 1 2 } u _ { 2 } + c _ { 1 3 } } { c _ { 3 1 } u _ { 1 } + c _ { 3 2 } u _ { 2 } + c _ { 3 3 } } } \qquad { \mathrm { a n d } } \qquad u _ { 2 } \to { \frac { c _ { 2 1 } u _ { 1 } + c _ { 2 2 } u _ { 2 } + c _ { 2 3 } } { c _ { 3 1 } u _ { 1 } + c _ { 3 2 } u _ { 2 } + c _ { 3 3 } } }
$$

One also checks that the r.h.s.'s of (3.78) vanish for

$$
u _ { 1 } = \frac { c _ { 1 1 } \frac { z ^ { 2 } } { 2 } + c _ { 1 2 } z + c _ { 1 3 } } { c _ { 3 1 } \frac { z ^ { 2 } } { 2 } + c _ { 3 2 } z + c _ { 3 3 } } , \qquad u _ { 2 } = \frac { c _ { 2 1 } \frac { z ^ { 2 } } { 2 } + c _ { 2 2 } z + c _ { 2 3 } } { c _ { 3 1 } \frac { z ^ { 2 } } { 2 } + c _ { 3 2 } z + c _ { 3 3 } }
$$

where $\{ c _ { i j } \} \in \mathrm { G L } ( 3 )$ . For infinitesimal transformations with $c _ { i j } = \delta _ { i j } + \gamma _ { i j }$ ， $u _ { 1 }$ and $u _ { 2 }$ lead to quadratic and quartic polynomials (in $z$ ）for $\epsilon$ and $\eta$ (cf.(3.79)); for this the factors （204号 $\textstyle { \frac { 1 } { 2 } }$ in (3.86) are needed. Recall that infinitesimal Mobius transformations are quadratic polynomials, which reflects the fact that normalizable holomorphic vector fields $\xi ^ { i }$ which generate infinitesimal diffeomorphisms on the Poincaré sphere grow at most as $z ^ { 2 }$ for large $z$ .‘Generalized diffeomorphisms’ are generated by symmetric tensors $\xi ^ { i j }$ which are normalizable as long as they do not grow faster than $z ^ { 4 }$ . Put differently, there are three (five) $c$ -ghost zero modes on the sphere for a $\lambda = 2$ ( $\lambda = 3$ ） $( b , c )$ ghost system (and none for the $b$ -ghost).

The generalizations of the construction that gives (3.78） and (3.81） to $S L ( N )$ with $N > 3$ ， and presumably also to other other classical groups, are straightforward. Some results for $S L ( N )$ are presented in Appendix B.

After this excursion to generalized complex and projective structures, we now combine the flat connection (3.63) with $\tilde { a } = - a ^ { \dagger }$ . Clearly $( a , \tilde { a } )$ is not in FG gauge: their zero-mode parts do not match. The task is to modify them in such a way that they are in FG gauge while still encoding, via the flatness conditions,the Ward identities. In doing so we want to preserve the following properties: the only positive mode in $a _ { z }$ is along $L _ { + 1 }$ as this captures the AdS $^ 3$ vacuum and the charges are along the highest weight directions. This can be accomplished by a gauge transformation of (3.63) such that

$$
L _ { 1 }  L _ { 1 } - \omega + \mathrm { n e g a t i v e ~ m o d e s }
$$

with

$$
\omega = \bar { \omega } ^ { \dagger } = \omega _ { 2 } L _ { 0 } + \omega _ { 3 } W _ { 0 }
$$

A moment's thought reveals that this is solved by

$$
g = M ^ { - 1 }
$$

where $M = M ( \omega )$ in the Miura transformation given explicitly in (3.46),which satisfies (cf. (3.40))

$$
M ( L _ { 1 } - \mathcal { Q } ( \omega ) ) M ^ { - 1 } - \partial M M ^ { - 1 } = L _ { 1 } - \omega
$$

with $\mathcal { Q }$ as in (3.47). The gauge transformed connection has the structure

$$
\begin{array} { l l } { { a _ { z } = L _ { 1 } - \omega + q ~ } } & { { ~ a _ { \bar { z } } = \mu + \bar { \omega } + \beta + \gamma } } \\ { { { \tilde { a } } _ { z } = \bar { \mu } + \omega + \bar { \beta } + \bar { \gamma } ~ } } & { { ~ { \tilde { a } } _ { \bar { z } } = L _ { - 1 } + \bar { \omega } + \bar { q } } } \end{array}
$$

where

$$
\bar { q } = - q ^ { \dagger } , \qquad \bar { \mu } = - \mu ^ { \dagger } , \qquad \bar { \gamma } = - \gamma ^ { \dagger } , \qquad \bar { \beta } = - \beta ^ { \dagger }
$$

We emphasize that given the same $( \mu _ { 2 } , \mu _ { 3 } )$ ， the remaining variables in (3.63) and (3.91) take different values.

The effect of the gauge transformation (3.89) on the charge vector is

$$
\bullet  M ( \bullet + \mathcal { Q } ( \omega ) ) M ^ { - 1 }
$$

This gives

$$
T \to T + Q _ { 2 } ( \omega ) \qquad \mathrm { a n d } \qquad W \to [ W + Q _ { 3 } ( \omega ) ] - { \textstyle { \frac { 1 } { 3 } } } \omega _ { 3 } [ T + Q _ { 2 } ( \omega ) ]
$$

Similarly, the sources are shifted

$$
\mu _ { 2 } \to \mu _ { 2 } + \frac { \omega _ { 3 } } { 3 } \mu _ { 3 } \qquad \mathrm { a n d } \qquad \mu _ { 3 } \to \mu _ { 3 }
$$

The charge vector therefore transforms as

$$
\mu _ { 2 } T + \mu _ { 3 } W  \mu _ { 2 } ( T + \mathcal { Q } _ { 2 } ) + \mu _ { 3 } ( W + \mathcal { Q } _ { 3 } )
$$

Applying the gauge transformation (3.89) we see that the six algebraic equations (3.68) in the flatness condition of $a$ change to

$$
\begin{array} { r l } & { \gamma = - ( \partial + 2 \omega _ { 2 } ) \mu _ { 3 } , } \\ & { \mu _ { 2 } \omega _ { 2 } + \bar { \omega } _ { 2 } = - \partial \mu _ { 2 } - \frac { 1 } { 2 } \gamma \omega _ { 3 } , \qquad \mu _ { 2 } \omega _ { 3 } + \bar { \omega } _ { 3 } = - \frac { 1 } { 2 } \big ( \mu _ { 3 } T + ( \partial + \omega _ { 2 } ) \gamma \big ) } \\ & { \beta _ { 1 } = - \frac { 1 } { 2 } \big ( \partial \bar { \omega } _ { 2 } + \bar { \partial } \omega _ { 2 } \big ) - \frac { 1 } { 4 } \mu _ { 2 } T - \frac { 1 } { 2 } \mu _ { 3 } W , \qquad \beta _ { 2 } = - \frac { 1 } { 3 } \big ( \partial \bar { \omega } _ { 3 } + \bar { \partial } \omega _ { 3 } \big ) - \frac { 1 } { 4 } \gamma T , } \\ & { \beta _ { 3 } = \frac { 1 } { 4 } \mu _ { 2 } W - \frac { 1 } { 8 } \bar { \omega } _ { 3 } T - \frac { 1 } { 4 } \partial \beta _ { 2 } + \left( \frac { 1 } { 4 } \omega _ { 2 } \beta _ { 2 } + \frac { 1 } { 2 } \omega _ { 3 } \beta _ { 1 } \right) } \end{array}
$$

and the complex conjugate set of conditions from flatness of $\tilde { a }$ . Note that we can no longer express the zero modes algebraically in terms of the sources and their derivatives. This is in contrast to the situation for ${ \mathfrak { s l } } ( 2 )$ ，which we discussed in Section 2.3.

The Ward identities take the same form as the chiral Ward identities (3.69) and (3.70 with the replacements

$$
\begin{array} { r l } { \mu _ { 2 } \to \mu _ { 2 } - \frac { 1 } { 3 } \omega _ { 3 } \mu _ { 3 } \ } & { { } } \\ { T \to T - \mathcal { Q } _ { 2 } ( \omega ) } & { { } \ \mathrm { a n d } \qquad W \to W - \mathcal { Q } _ { 3 } ( \omega ) + \frac { 1 } { 3 } \omega _ { 3 } T } \end{array}
$$

which are the inverse transformation of (3.94) and (3.95); $T$ and $W$ satisfy the same identities with $\mu \to \mu$ ，etc.

The dreibein, the metric, and the spin-three field and their FG expansions are now easily computed and they follow the general pattern outlined before. In particular, the metric is strongly backreacted as long as $\mu _ { 3 } \bar { \mu } _ { 3 } \neq 0$ . To avoid this we can set $\bar { \mu } _ { 3 } = 0$ ，and obtain a configuration with boundary metric at $\mathcal { O } ( \rho ^ { - 2 } )$ and spin-3 field at $\mathcal { O } ( \rho ^ { - 4 } )$

$$
{ \stackrel { \scriptscriptstyle ( 0 ) } { g } } = | d z + \mu _ { 2 } d \bar { z } | ^ { 2 } \qquad \mathrm { a n d } \qquad { \stackrel { \scriptscriptstyle ( 0 ) } { \psi } } = \mu _ { 3 } d \bar { z } ( d \bar { z } + \bar { \mu } _ { 2 } d z ) ^ { 2 }
$$

The flatness condition of this configuration follows by setting $\bar { \mu } _ { 3 } = 0$ in (3.97) and its complex conjugate. We can see that even with $\bar { \mu } _ { 3 } = 0$ the zero modes still cannot be solved algebraically in terms of the sources and their derivatives.

This is not a problem in itself. However, to simplify the computation (without losing real content） we consider

$$
\bar { \mu } _ { 2 } = \bar { \mu } _ { 3 } = 0
$$

which generalizes the lightcone gauge for ${ \mathfrak { s l } } ( 2 )$ (2.73） to ${ \mathfrak { s l } } ( 3 )$ . The connections (3.91 simplify to

$$
\begin{array} { l l } { { a _ { z } = L _ { 1 } + q \qquad } } & { { \qquad a _ { \bar { z } } = \pmb { \mu } + \bar { \omega } + \beta + \gamma } } \\ { { \tilde { a } _ { z } = \bar { \beta } \qquad } } & { { \qquad \tilde { a } _ { \bar { z } } = L _ { - 1 } + \bar { \omega } + \bar { q } } } \end{array}
$$

In particular $a$ has reduced to (3.63)， from which we derived the $\mathcal { W } _ { 3 }$ Ward identities. Therefore the parameters in $( \bar { \omega } , \beta , \gamma )$ are as in (3.68). However $\tilde { a }$ is no longer $- a ^ { \dagger }$ In particular $\bar { \beta } = \bar { \beta } _ { 1 } L _ { 1 } + \bar { \beta } _ { 2 } W _ { 1 } - \bar { \beta } _ { 3 } W _ { 2 } \neq \beta ^ { \dagger }$ , but instead

$$
\begin{array} { r } { \bar { \beta } _ { 1 } = - \frac 1 2 \partial \bar { \omega } _ { 2 } \qquad \bar { \beta } _ { 2 } = - \frac 1 3 \partial \bar { \omega } _ { 3 } \qquad \bar { \beta } _ { 3 } = \frac 1 { 1 2 } \partial \bar { \partial } \bar { \omega } _ { 3 } - \frac 1 { 1 2 } \bar { \omega } _ { 2 } \partial \bar { \omega } _ { 3 } - \frac 1 4 \bar { \omega } _ { 3 } \partial \bar { \omega } _ { 2 } } \end{array}
$$

With(3.101） we can compute the $\rho$ -expansion of the dreibein，which starts with $^ { ( - 1 ) } _ { e }$ at $\mathcal { O } ( \rho ^ { - 2 } )$ due to the presence of the spin-3 source. We give the leading terms:

$$
\begin{array} { r } { \stackrel { ( - 1 ) } { e } = \frac { 1 } { 2 } \mu _ { 3 } W _ { 2 } d \bar { z } , \qquad \stackrel { ( 0 ) } { e } = - L _ { 0 } d \rho + \frac { 1 } { 2 } \left[ L _ { 1 } \left( d z + \mu _ { 2 } d \bar { z } \right) - \partial \mu _ { 3 } W _ { 1 } d \bar { z } - L _ { - 1 } d \bar { z } \right] . } \end{array}
$$

The $\mathcal { O } ( \rho ^ { - 4 } )$ term of the bulk metric is now absent but the leading term of the bulk spin-3 field remains. The boundary metric and spin-3 field are

$$
{ \bf \Pi } _ { g } ^ { ( 0 ) } = ( d z + \mu _ { 2 } d \bar { z } ) d \bar { z } \qquad \mathrm { a n d } \qquad { \bf \Pi } _ { \psi } ^ { ( 0 ) } = \mu _ { 3 } d \bar { z } ^ { 3 }
$$

With only a chiral spin-3 source, the bulk energy-momentum tensor is such that it does not modify the asymptotic behavior of the bulk metric. The boundary value of $\Psi _ { \rho i j }$ is also present (as in the conformal gauge):

$$
\stackrel { ( 0 ) } { \psi } _ { \rho } = ( \partial \mu _ { 3 } ) d \bar { z } ^ { 2 }
$$

and vanishes only when $\partial \mu _ { 3 } = 0$ =

Under PBH transformations the boundary metric $\stackrel { ( 0 ) } { g }$ transforms as26

$$
\delta _ { \sigma _ { 2 } } \stackrel { ( 0 ) } { g } = 2 \sigma _ { 2 } \stackrel { ( 0 ) } { g } \qquad \mathrm { a n d } \qquad \delta _ { \sigma _ { 3 } } \stackrel { ( 0 ) } { g } = - \sigma _ { 3 } \stackrel { ( 0 ) } { \psi } _ { \rho } + \frac { 2 } { 3 } \partial \sigma _ { 3 } \mu _ { 3 } d \bar { z } ^ { 2 }
$$

0 while for the boundary spin-3 field $\psi$ one finds

$$
\delta _ { \sigma _ { 2 } } \stackrel { ( 0 ) } { \psi } = 4 \sigma _ { 2 } \stackrel { ( 0 ) } { \psi } \qquad \mathrm { a n d } \qquad \delta _ { \sigma _ { 3 } } \stackrel { ( 0 ) } { \psi } = 0
$$

In contrast to (3.36)，where the spin-3 source has a strong back-reaction, the boundary spin-3 field now is invariant under the spin-3 Weyl transformation, whereas the boundary metric transforms. Finally, the $\psi _ { \rho i j } ^ { ( 0 ) }$ component transforms as

$$
{ \delta } _ { \sigma _ { 2 } } \stackrel { ( 0 ) } { \psi } _ { \rho } = 2 \sigma _ { 2 } \stackrel { ( 0 ) } { \psi } _ { \rho } + 4 \partial ( \sigma _ { 2 } \mu _ { 3 } d \bar { z } ^ { 2 } \qquad \mathrm { a n d } \qquad { \delta } _ { \sigma _ { 3 } } \stackrel { ( 0 ) } { \psi } _ { \rho } = - 4 { \sigma } _ { 3 } \stackrel { ( 0 ) } { g }
$$

From (3.37) we find for the $\mathcal { W }$ -Weyl variations of the effective action

$$
\delta _ { \sigma _ { s } } W = \frac { t _ { 0 } ^ { ( s ) } k } { \pi } \int _ { \partial \mathcal { M } } \sigma _ { s } \left( \partial \bar { \omega } _ { s } \right) d z \wedge d \bar { z }
$$

The interpretation of this is not obvious. For $s = 2$ ， using (3.68)，we see that this agrees with (2.75) and there is no contribution from the spin-3 field. For $s = 3$ , using once again (3.68) we find

$$
\delta _ { \sigma _ { 3 } } W = { \frac { k } { 3 \pi } } \int _ { \partial { \mathcal { M } } } d ^ { 2 } z \sigma _ { 3 } \partial \big [ ( \partial ^ { 2 } - T ) \mu _ { 3 } \big ]
$$

The appearance of $T$ is at first surprising. On second thought it might be expected because the boundary metric, the source for $T$ , transforms under $\sigma _ { 3 }$ . The details of how (3.110) results are, however, not clear to us.

# 4 Conclusions

Higher-spin theories in three dimensions coupled to gravity with a negative cosmological constant are most easily described in terms of Chern-Simons theories. They are dual to conformal field theories with $\mathcal { W }$ -symmetry. These two-dimensional field theories can be coupled to external sources; the source for the conserved spin- $s$ current is a spin- $s$ gauge field. The usual way to describe them holographically is in terms of metric-like bulk fields whose boundary configurations can be identified as the sources. This is well known and understood for pure gravity, where a Chern-Simons description as well as a metric one are known. For the higher-spin generalizations the situation is considerably more difficult, as their formulation in the bulk is not known in terms of the metric-like fields. They are derived from the connections and consequently also the boundary data, i.e. the sources and vev's of the dual field theory on the boundary, have to be encoded in the connection.

We have addressed these issues by frst translating results known for the case of pure gravity into the Chern-Simons language in such a way that a generalization to the higherrank,i.e. higher-spin case, is immediate. This concerns the Fefferman-Graham gauge, the action of the residual PBH transformations, and different gauge choices for the boundary theory， such as conformal gauge and light-cone gauge. While the generalizations are straightforward, the interpretation of the results they lead to are not. One problem is to find configurations that, on the one hand, have no strong back-reaction on the metric (i.e. the radius of the asymptotic AdS does not change) and on the other, incorporate sources for the metric and the higher-spin fields. For instance, in conformal gauge, which is parametrized by ${ \mathfrak { s l } } ( N )$ Toda fields, the spin $s$ source for $s > 2$ does not appear in the expected way. Another problem which we encountered was the interpretation of the variation of the effective action， which can be computed using holography. Only in the conformal gauge did we succeed to connect to results which were previously derived in the （204号 $\mathcal { W }$ -gravity literature. The situation in the light-cone gauge was much less clear. However, the analysis of this gauge leads us to a natural generalization of the Schwarzian derivative from ${ \mathfrak { s l } } ( 2 )$ to ${ \mathfrak { s l } } ( 3 )$ and beyond.

It would be interesting to explore the open issues discussed here further. The FeffermanGraham gauge we have used throughout the paper relies on a particular choice of the radial component of the connections (2.26) and the matching of the zero-modes between the two connections (3.12). Although these choices are natural — one reason being that they have a straightforward ${ \mathfrak { s l } } ( 2 )$ (i.e.pure gravity) limit - their appropriateness in the higher-spin theory might be questioned. We hope to address some of the open problems in the near future.

# Acknowledgments

We thank M. Banados, J. de Boer, S. Campoleoni, S. Fredenhagen,M. Gaberdiel, J. Jottar,Y. Korovin, R. Manvelyan, A. Perez,and Z. Skvortsov for helpful discussions. WL is supported by the European Research Council under the European Union's Seventh Framework Programme (FP7/2007-2013), ERC Consolidator Grant Agreement ERC-2013-CoG615443: SPiN (Symmetry Principles in Nature).

# A Conventions

# A.1 （204号 ${ \mathfrak { s l } } ( N )$

In this appendix we give details of the two bases for ${ \mathfrak { s l } } ( N )$ which we use and also fix some notation.

In the Chevalley basis there is a triplet of generators $\{ H ^ { ( i ) } , E _ { + } ^ { ( i ) } , E _ { - } ^ { ( i ) } \}$ ( $E _ { - } ^ { ( i ) } = ( E _ { + } ^ { ( i ) } ) ^ { \dagger } )$ （204号 for each simple root $\alpha _ { i }$ ， $i = 1 , \ldots , N - 1$ . The commutation relations are

$$
[ H ^ { ( i ) } , E _ { \pm } ^ { ( j ) } ] = \pm K _ { j i } E _ { \pm } ^ { ( j ) } \qquad [ E _ { + } ^ { ( i ) } , E _ { - } ^ { ( j ) } ] = \delta ^ { i j } H ^ { ( i ) }
$$

$K _ { i j }$ is the Cartan matrix of ${ \mathfrak { s l } } ( N )$

$$
K _ { i j } = 2 \delta _ { i j } - \delta _ { i , j + 1 } - \delta _ { i + 1 , j } = \mathrm { t r } [ H ^ { ( i ) } H ^ { ( j ) } ] = 2 { \frac { \langle \alpha _ { i } , \alpha _ { j } \rangle } { \langle \alpha _ { j } , \alpha _ { j } \rangle } }
$$

H(i) are the Cartan generators

$$
H ^ { ( i ) } = \mathcal { E } _ { i i } - \mathcal { E } _ { i + 1 , i + 1 } \qquad i = 1 , \dots , N - 1
$$

and E(i) are raising and lowering operators

$$
E _ { + } ^ { ( i ) } = \mathcal { E } _ { i , i + 1 } \qquad E _ { - } ^ { ( i ) } = \mathcal { E } _ { i + 1 , i }
$$

$\mathcal { E } _ { i j }$ is the matrix unit with matrix elements $( \mathcal { E } _ { i j } ) _ { k l } = \delta _ { i k } \delta _ { j l }$ , i.e. the only non-zero matrix element is a one in the $( i j )$ position. The remaining generators are obtained by the commutators $[ E _ { \pm } ^ { ( i ) } , E _ { \pm } ^ { ( j ) } ]$ . Altogether they are $\mathcal { E } _ { i j } , i \neq j$ and the $H ^ { ( i ) }$ ：

The Chevalley basis is often used when discussing Toda systems. There is a second basis which is adapted to the study of ${ \mathfrak { s l } } ( N )$ Chern-Simons theory as a gravitational theory. Since the gravity sector corresponds an ${ \mathfrak { s l } } ( 2 )$ algebra，we first need to choose a subalgebra embedding ${ \mathfrak { s l } } ( 2 ) \hookrightarrow { \mathfrak { s l } } ( N )$ （20

$$
\left[ L _ { m } , L _ { n } \right] = ( m - n ) L _ { m + n } \qquad \quad m , n = - 1 , 0 , 1
$$

as the gravitational subsector. We then decompose the adjoint representation of ${ \mathfrak { s l } } ( N )$ in irreducible representations $\{ W _ { m } ^ { ( s ) } \}$ of this gravity ${ \mathfrak { s l } } ( 2 )$ , where the spin $s$ is integer or half-integer and $m \in \{ - s + 1 , \ldots , s - 1 \}$ is the magnetic quantum number:

$$
\left[ L _ { m } , W _ { n } ^ { ( s ) } \right] ~ = ~ \left[ ( s - 1 ) m - n \right] W _ { m + n } ^ { ( s ) }
$$

(We sometimes write $W _ { m } ^ { ( 2 ) } = L _ { m }$ ）.

There are inequivalent embeddings ${ \mathfrak { s l } } ( 2 ) \hookrightarrow { \mathfrak { s l } } ( N )$ and they differ by the spectrum of spins.There is always one,the principal embedding,with the property that there is one spin- $s$ field for each $s = 2 , \ldots , N$ . In this paper we focus on the principal embedding.

In terms of the Chevalley basis, the ${ \mathfrak { s l } } ( 2 )$ for the principal embedding is

$$
L _ { 0 } \equiv \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N - 1 } k _ { i } H ^ { ( i ) } \qquad L _ { \pm 1 } \equiv \mp \sum _ { i = 1 } ^ { N - 1 } \sqrt { k _ { i } } E _ { \mp } ^ { ( i ) }
$$

where $\begin{array} { r } { k _ { i } = 2 \sum _ { j } ( K ^ { - 1 } ) _ { i j } } \end{array}$ are the heights of the fundamental weights. Note the switch of the $\pm$ in passing from $E _ { \mp }$ to $L _ { \pm 1 }$ . Then starting from the ${ \mathfrak { s l } } ( 2 )$ generators $\{ L _ { 0 } , L _ { \pm } \}$ ，the higher-spin generators $W _ { m } ^ { ( s ) }$ are

$$
W _ { m } ^ { ( s ) } = ( - 1 ) ^ { s - m - 1 } { \frac { ( s + m - 1 ) ! } { ( 2 s - 2 ) ! } } ( \mathrm { a d j } _ { L _ { - 1 } } ) ^ { s - m - 1 } ( L _ { 1 } ) ^ { s - 1 }
$$

with the adjoint action defined as $\operatorname { a d j } _ { A } B \ = \ [ A , B ]$ .(A.8)， together with $\left( L _ { m } \right) ^ { \dagger } =$ $( - 1 ) ^ { m } L _ { - m }$ , implies

$$
( W _ { m } ^ { ( s ) } ) ^ { \dagger } = ( - 1 ) ^ { m } W _ { - m } ^ { ( s ) } \qquad s = 2 , \dots , N
$$

The thus constructed basis is orthogonal but not normalized:

$$
\mathrm { t r } [ W _ { m } ^ { ( s ) } W _ { n } ^ { ( t ) } ] = \delta ^ { s t } \delta _ { m , - n } t _ { m } ^ { ( s ) } \qquad \mathrm { w i t h } \qquad t _ { m } ^ { ( s ) } \equiv \mathrm { t r } [ W _ { m } ^ { ( s ) } W _ { - m } ^ { ( s ) } ]
$$

# A.2s(2)

The height is $k _ { 1 } = 2$ , from which we get the ${ \mathfrak { s l } } ( 2 )$ algebra (A.7)

$$
L _ { 0 } = { \binom { \frac { 1 } { 2 } } { 0 } } \qquad L _ { 1 } = { \binom { 0 } { - 1 } } \qquad L _ { - 1 } = { \binom { 0 } { 0 } } \qquad L _ { - 1 } = { \binom { 0 } { 0 } } \qquad 
$$

The normalization factors (A.1O) are

$$
t _ { 0 } ^ { ( 2 ) } = \mathrm { t r } [ ( L _ { 0 } ) ^ { 2 } ] = \frac { 1 } { 2 } \qquad t _ { 1 } ^ { ( 2 ) } = \mathrm { t r } [ L _ { 1 } L _ { - 1 } ] = - 1
$$

Define the combinations

$$
J _ { 0 } = \frac { 1 } { 2 } \big ( L _ { 1 } + L _ { - 1 } \big ) , \qquad J _ { 1 } = \frac { 1 } { 2 } \big ( L _ { 1 } - L _ { - 1 } \big ) , \qquad J _ { 2 } = L _ { 0 }
$$

They satisfy

$$
[ J _ { a } , J _ { b } ] = \epsilon _ { a b } ^ { \phantom { a b } c } J _ { c } , \qquad \mathrm { T r } ( J _ { a } J _ { b } ) = \frac 1 2 \eta _ { a b }
$$

where $\eta _ { a b } = \mathrm { d i a g } ( - 1 , + 1 , + 1 )$ is used to raise and lower indices.

# A.3s(3)

The height vector is $\vec { k } = ( 2 , 2 )$ , from which we get via (A.7)

$$
L _ { 0 } = { \left( \begin{array} { l l l } { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { - 1 } \end{array} \right) } L _ { 1 } = \left( { \begin{array} { l l l } { 0 } & { 0 } & { 0 } \\ { - { \sqrt { 2 } } } & { 0 } & { 0 } \\ { 0 } & { - { \sqrt { 2 } } } & { 0 } \end{array} } \right) L _ { - 1 } = \left( { \begin{array} { l l l } { 0 } & { { \sqrt { 2 } } } & { 0 } \\ { 0 } & { 0 } & { { \sqrt { 2 } } } \\ { 0 } & { 0 } & { 0 } \end{array} } \right)
$$

and from (A.8)

$$
W _ { 0 } = { \left( \begin{array} { l l l } { { \frac { 1 } { 3 } } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { - \frac { 2 } { 3 } } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { \frac { 1 } { 3 } } } \end{array} \right) } \qquad W _ { 1 } = \left( { \begin{array} { r r r } { { 0 } } & { { 0 } } & { { 0 } } \\ { { - { \frac { 1 } { \sqrt { 2 } } } } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { { \frac { 1 } { \sqrt { 2 } } } } } & { { 0 } } \end{array} } \right) \qquad W _ { - 1 } = \left( { \begin{array} { r r r } { { 0 } } & { { { \frac { 1 } { \sqrt { 2 } } } } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { - { \frac { 1 } { \sqrt { 2 } } } } } \\ { { 0 } } & { { 0 } } & { { 0 } } \end{array} } \right)
$$

$$
\begin{array}{c} W _ { 2 } = { \binom { 0 } { 0 } } \ 0 0  \\ { 2 { } } \end{array} \qquad W _ { - 2 } = { \left( \begin{array} { l l l } { 0 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } \end{array} \right) } \qquad W _ { - 2 } = { \left( \begin{array} { l l l } { 0 } & { 0 } & { 2 } \\ { 0 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } \end{array} \right) }
$$

The normalization factors (A.10) are

$$
t _ { 0 } ^ { ( 2 ) } = 2 \qquad t _ { 0 } ^ { ( 3 ) } = { \frac { 2 } { 3 } } \qquad t _ { 1 } ^ { ( 2 ) } = - 4 \qquad t _ { 1 } ^ { ( 3 ) } = - 1 \qquad t _ { 2 } ^ { ( 3 ) } = 4
$$

# B Some explicit results for SL $( N )$

In this appendix we collect some explicit results of the constructions presented in Chapter 3 which are valid for all $N$ ：

We decompose elements of the Cartan subalgebra of ${ \mathfrak { s l } } ( N )$ ， such as $\Phi$ into the two bases specified in Appendix A:

$$
\Phi \equiv \sum _ { i = 1 } ^ { N - 1 } \Phi _ { i } H ^ { ( i ) } = \sum _ { s = 2 } ^ { N } \Psi _ { s } W _ { 0 } ^ { ( s ) }
$$

While the closed form expression for the $\operatorname { S L } ( N )$ group element $M$ ， which implements the Miura transformation, is not available, we can write down the part along the simple root directions $M = \exp [ h _ { - } ] = \mathbb { 1 } + h _ { - 1 } + . ~ . ~ .$ where

$$
h _ { - 1 } = \sum _ { i = 1 } ^ { N - 1 } \frac { 1 } { \sqrt { k _ { i } } } \partial \Phi _ { i } E _ { + } ^ { ( i ) } = \sum _ { s = 2 } ^ { N } \frac { 1 } { s } \partial \Psi _ { s } W _ { - 1 } ^ { ( s ) }
$$

Using

$$
e ^ { - \phi } E _ { \pm } ^ { ( i ) } e ^ { \phi } = e ^ { \mp \alpha _ { i } } E _ { \pm } ^ { ( i ) } \qquad \mathrm { w i t h } \qquad \alpha _ { i } \equiv K _ { i j } \phi _ { j }
$$

the leading terms in the gauge transformed connection become

$$
\begin{array} { l } { { \displaystyle a _ { z } = - \sum _ { i } \sqrt { k _ { i } } e ^ { \alpha _ { i } } E _ { - } ^ { ( i ) } - \partial \bar { \phi } + \frac { T } { t _ { 1 } ^ { ( 2 ) } } \sum _ { i } \sqrt { k _ { i } } e ^ { - \alpha _ { i } } E _ { + } ^ { ( i ) } + \ldots } } \\ { { \displaystyle a _ { \bar { z } } = \bar { \partial } \phi - \sum _ { i } \frac { 1 } { \sqrt { k _ { i } } } \partial \bar { \partial } \Phi _ { i } e ^ { - \alpha _ { i } } E _ { + } ^ { ( i ) } + \ldots } } \end{array}
$$

and $\tilde { a } = - a ^ { \dagger }$ .Here $T \equiv q _ { 2 } ( z ) + { \mathcal Q } _ { 2 } ( \Phi )$ ，where $\mathcal { Q } _ { 2 }$ is the $( z z )$ -component of the energymomentum tensor of Toda theory:

$$
{ \mathcal { Q } } _ { 2 } = - { \frac { 1 } { 2 } } \sum _ { i , j } K _ { i j } \partial \Phi _ { i } \partial \Phi _ { j } + \sum _ { i } \partial ^ { 2 } \Phi _ { i }
$$

The terms displayed suffice to compute the leading and subleading terms in the $\rho$ expansions of $A$ and $\tilde { A }$ and the metric-like fields. The terms which we have not shown are rather long and we do not have closed expressions for all $N$ . But for any $N$ they can be worked out straightforwardly, following the procedure outlined before.

Using (B.4) we can give the leading terms of the $\rho$ -expansion of the bulk dreibein (cf. (3.20))

$$
\begin{array} { l } { { \displaystyle { \stackrel { \scriptscriptstyle ( 0 ) } { e } } = - L _ { 0 } d \rho - \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N - 1 } \sqrt { k } _ { i } [ e ^ { \alpha _ { i } } E _ { - } ^ { ( i ) } d z + h . c . ] ~ } } & { { ~ \stackrel { \scriptscriptstyle ( 1 ) } { e } = 0 } } \\ { { \displaystyle { \stackrel { \scriptscriptstyle ( 2 ) } { e } } = \frac { 1 } { 2 } \sum _ { i = 1 } ^ { N - 1 } \sqrt { k } _ { i } [ e ^ { - \alpha _ { i } } E _ { + } ^ { ( i ) } d t _ { i } + h . c . ] } } \end{array}
$$

where we have defined $d t _ { i }$

$$
d t _ { i } \equiv \frac { 1 } { t _ { 1 } ^ { ( 2 ) } } T d z - \frac { 1 } { k _ { i } } \partial \bar { \partial } \Phi _ { i } d \bar { z }
$$

It is now straightforward to compute the bulk metric. The first few terms in its FG expansion (2.14） are

$$
\begin{array} { l } { { \displaystyle { \begin{array} { l } { { \stackrel { \scriptscriptstyle ( 0 ) } { g } = \frac { 1 } { \displaystyle 2 t _ { 0 } ^ { ( 2 ) } } ( \sum _ { i } k _ { i } e ^ { A _ { i } } ) d z d \bar { z } } \qquad \mathrm { w i t h } \qquad A _ { i } \equiv \alpha _ { i } + \bar { \alpha } _ { i } } } } \\ { { \displaystyle { \begin{array} { l } { { \scriptstyle ( \frac { \scriptscriptstyle ( 2 ) } { \displaystyle 2 } ) = - \frac { 1 } { \displaystyle 2 t _ { 0 } ^ { ( 2 ) } } ( \sum _ { i } k _ { i } d t _ { i } ) d z + c . c . = ( \partial \bar { \partial } \Phi _ { L } ) d z d \bar { z } + \frac { T } { \displaystyle 2 t _ { 0 } ^ { ( 2 ) } } d z ^ { 2 } + \frac { \bar { T } } { \displaystyle 2 t _ { 0 } ^ { ( 2 ) } } d \bar { z } ^ { 2 } } } } \\ { { \displaystyle { \vphantom { \Biggl ( } \frac { \scriptscriptstyle { ( 4 ) } } { \displaystyle 2 } = \frac { 1 } { \displaystyle 2 t _ { 0 } ^ { ( 2 ) } } \sum _ { i } k _ { i } e ^ { - A _ { i } } d t _ { i } d \bar { t } _ { i } } } } \end{array} } } } \end{array} \end{array}
$$

where, using $t _ { 1 } ^ { ( 2 ) } = - \textstyle \sum _ { i } k _ { i }$ ，

$$
\Phi _ { L } = { \frac { 1 } { t _ { 0 } ^ { ( 2 ) } } } \mathrm { t r } \bigl ( L _ { 0 } \Phi \bigr ) = { \frac { 1 } { t _ { 0 } ^ { ( 2 ) } } } \sum _ { i } \Phi _ { i }
$$

The $i _ { 1 } i _ { 2 } \dots i _ { s }$ components of the bulk spin- $s$ field has a $\rho$ -expansion that starts at $\mathcal { O } ( \rho ^ { - s } ) / \mathcal { O } ( \rho ^ { 0 } )$ for even/odd spin. The component Φ(s.p p.pij component has an p-expansion

$$
\Psi _ { \rho \ldots \rho i j } ^ { ( s ) } = \frac { 1 } { \rho ^ { s } } \sum _ { n = 0 } ^ { s - 1 } \rho ^ { 2 n } \stackrel { { \scriptscriptstyle ( 2 n ) } } { \psi } _ { \rho \ldots \rho i j }
$$

Finally we mention that, in analogy to the fact that $g _ { z \bar { z } } ^ { ( 2 ) } = \partial \bar { \partial } \Phi _ { L }$ is proportional to the Weyl anomaly in conformal gauge(cf.(B.8)), $\psi _ { \rho . . . \rho z \bar { z } } ^ { ( 2 ) } \sim \partial \bar { \partial } \Phi _ { s }$ is proportional to the spin $s$ $\mathcal { W }$ -Weyl anomaly in the same gauge.

The construction of the Schwarzian derivatives for ${ \mathfrak { s l } } ( N )$ can be easily described. One uses the Miura transformation to find the higher-spin charges $Q _ { s }$ in terms of the zero modes $\partial \Phi _ { i }$ ， $i = 1 , \ldots , N - 1$ along the Cartan directions, cf. (B.1). One then replaces

$$
\partial \Phi _ { i } = \sum _ { j } ( K ^ { - 1 } ) _ { i j } \frac { \partial ^ { 2 } e _ { j } } { \partial e _ { j } }
$$

where $K ^ { - 1 }$ is the inverse Cartan-Matrix of ${ \mathfrak { s l } } ( N )$ and $e _ { i }$ are the functions along the simple root directions which appear in the Gauss decomposition of the general group element. They were called $e _ { + }$ and $f _ { + }$ in (3.74). From the $\psi _ { i }$ ， which are a basis of solutions of the $N$ -th order holomorphic differential equation which generalizes (3.71), one forms the （204号 $N - 1$ ratios $u _ { i } = \psi _ { i } / \psi _ { N }$ . The relation between these ratios and the $e _ { i }$ is [33]

$$
\mathrm {  ~ \xi ~ } = u _ { N - 1 } , \quad e _ { N - 2 } = \frac { 1 } { \partial e _ { N - 1 } } \partial u _ { N - 2 } , \quad \mathrm {  ~ \cdot ~ } \cdot \mathrm {  ~ \cdot ~ } \quad e _ { N - i } = \frac { 1 } { \partial e _ { N - i + 1 } } \partial \frac { 1 } { \partial e _ { N - i + 2 } } \partial \cdot \cdot \cdot \partial \frac { 1 } { \partial e _ { N - 1 } } e _ { N } ,
$$

Equations (3.85) and (3.86) generalize to

$$
u _ { i } \to { \frac { \sum _ { j = 1 } ^ { N } c _ { i j } u _ { j } } { \sum _ { j = 1 } ^ { N } c _ { N j } u _ { j } } } , \qquad i = 1 , \dots , N - 1 , \qquad \{ c _ { i j } \} \in G L ( N )
$$

and

$$
u _ { i } = \frac { \sum _ { j = 1 } ^ { N } c _ { i j } \frac { z ^ { N - j } } { ( N - j ) ! } } { \sum _ { j = 1 } ^ { N } c _ { N j } \frac { z ^ { N - j } } { ( N - j ) ! } }
$$

respectively. We have checked these statements explicitly for $S L ( 4 )$ .For this case we have also found the Beltrami equations,but they are too long to present here,as are the explicit expressions for the charges.

# References

[1] A.M. Polyakov, “Quantum Gravity in Two-Dimensions,” Mod. Phys. Lett. A 2 (1987) 893.   
[2] A. B. Zamolodchikov,“Infinite Additional Symmetries in Two-Dimensional Conformal Quantum Field Theory,” Theor. Math.Phys.65（1985） 1205[Teor. Mat. Fiz. 65 (1985) 347].   
[3] C. M. Hull, “Lectures on W Gravity, W Geometry and W Strings,” In \*Trieste 1992, Proceedings, High energy physics and cosmology\* 76-142 and London Queen Mary and Westfield Coll. - QMW-93-02 (93/02) 54 p. (305933) [hep-th/9302110].   
[4] A.Achucarro and P. K. Townsend, “A Chern-Simons Action for Three-Dimensional Anti-de Sitter Supergravity Theories,” Phys. Lett. B 180 (1986) 89.   
[5] E. Witten,“(2+1)-Dimensional Gravity as an Exactly Soluble System,” Nucl. Phys. B 311(1988) 46.   
[6] M. Henneaux and S. -J. Rey, “Nonlinear $W _ { \infty }$ as Asymptotic Symmetry of Three-Dimensional Higher Spin Anti-de Sitter Gravity,” JHEP 1012 (2010) 007 [arXiv:1008.4579 [hep-th]].   
[7] A.Campoleoni， S. Fredenhagen, S. Pfenninger and S. Theisen， “Asymptotic Symmetries of Three-Dimensional Gravity Coupled to Higher-Spin Fields,” JHEP 1011 (2010) 007 [arXiv:1008.4744 [hep-th]].   
[8] A. Campoleoni, S. Fredenhagen, S. Pfenninger and S. Theisen,“Towards Metric-Like Higher-Spin Gauge Theories in Three Dimensions,” J. Phys. A 46 (2013) 214017 [arXiv:1208.1851 [hep-th].   
[9] S. Fredenhagen and P. Kessel,“Metric- and Frame-Like Higher-Spin Gauge Theories in Three Dimensions,” arXiv:1408.2712 [hep-th].   
[10] A. Campoleoni and M. Henneaux,“Asymptotic symmetries of three-dimensional higher-spin gravity: the metric approach,” arXiv:1412.6774 [hep-th].   
[11] M. Henningson and K. Skenderis,“The Holographic Weyl Anomaly,” JHEP 9807 (1998)023 [hep-th/9806087].   
[12] M. Banados, O. Chandia and A. Ritz， “Holography and the Polyakov Action,” Phys. Rev. D 65 (2002) 126008 [hep-th/0203021]; M. Banados and R. Caro,“Holographic Ward Identities: Examples from 2+1 Gravity,” JHEP O412 (2004) 036 [hep-th/0411060].   
[13] J. de Boer,A. Castro, E. Hijano, J. I. Jottar and P. Kraus,“Higher Spin Entanglement and $W _ { N }$ Conformal Blocks,” arXiv:1412.7520 [hep-th].   
[14] R. R. Poojary and N. V. Suryanarayana, “Holographic chiral induced W-gravities,” arXiv:1412.2510 [hep-th].   
[15] C. Fefferman and R. Graham， “Conformal invariants,” Elie Cartan et les Mathématiques d'Aujourdui, Asterisque (1985), p. 95.   
[16] M. Banados,“Three-Dimensional Quantum Geometry and Black Holes,” AIP Conf. Proc. 484 (1999) 147 [hep-th/9901148].   
[17] K. Skenderis and S.N. Solodukhin,“Quantum Effective Action from the AdS / CFT Correspondence,” Phys. Lett. B 472 (2000) 316 [hep-th/9910023].   
[18] M. Banados, O. Miskovic and S. Theisen,“Holographic currents in first order gravity and finite Fefferman-Graham expansions,” JHEP 0606 (2006) 025 [hep-th/0604148].   
[19] S. de Haro， S. N. Solodukhin and K. Skenderis，“Holographic Reconstruction of Space-Time and Renormalization in the AdS/CFT Correspondence,” Commun. Math. Phys.217 (2001） 595 [hep-th/0002230].   
[20] C. Imbimbo,A. Schwimmer, S. Theisen and S. Yankielowicz,“Diffeomorphisms and Holographic Anomalies,” Class. Quant. Grav. 17 (2000) 1129 [hep-th/9910267].   
[21] A. Schwimmer and S. Theisen,“Entanglement Entropy, Trace Anomalies and Holography,” Nucl. Phys.B 801 (2008)1 [arXiv:0802.1017 [hep-th]].   
[22] M.Rooman and P. Spindel，“Holonomies, anomalies and the Fefferman-Graham ambiguity in AdS(3) gravity,” Nucl. Phys. B 594 (2001) 329 [hep-th/0008147].   
[23] H. L. Verlinde,“Conformal Field Theory, 2-D Quantum Gravity and Quantization of Teichmuller Space,” Nucl. Phys. B 337 (1990) 652.   
[24] R.C. Gunning，“Lectures on Riemann surfaces,” Princeton University Press (1966).   
[25] A. Campoleoni， S. Fredenhagen and S. Pfenninger，“Asymptotic W-symmetries in three-dimensional higher-spin gauge theories,” JHEP 1109 (2011） 113 [arXiv:1107.0290 [hep-th].   
[26] M.Gutperle and P. Kraus，“Higher Spin Black Holes,” JHEP 1105 (2011） 022 [arXiv:1103.4304 [hep-th].   
[27] M. Ammon，M. Gutperle,P. Kraus and E. Perlmutter，“Spacetime Geometry in Higher Spin Gravity,” JHEP 1110 (2011) 053 [arXiv:1106.4788 [hep-th]].   
[28] M. Banados,R. Canto and S. Theisen，“The Action for higher spin black holes in three dimensions,” JHEP 1207,147 (2012) [arXiv:1204.5105 [hep-th]].   
[29] A. Castro, E. Hijano,A. Lepage-Jutier and A. Maloney, “Black Holes and Singularity Resolution in Higher Spin Gravity,” JHEP 1201 (2012) 031 [arXiv:1110.4117 [hepth]].   
[30] C. Bunster, M. Henneaux, A. Perez, D. Tempo and R. Troncoso,“Generalized Black Holes in Three-Dimensional Spacetime,” JHEP 1405 (2014) 031 [arXiv:1404.3305 [hep-th].   
[31] V. A. Fateev and S. L. Lukyanov,“The Models of Two-Dimensional Conformal Quantum Field Theory with Z(N) Symmetry,” Int. J. Mod. Phys. A 3 (1988) 507.   
[32] C. M. Hull, “W Gravity Anomalies 1: Induced Quantum W Gravity,” Nucl. Phys. B 367 (1991) 731.   
[33] A. Bilal, V. V. Fock and I. I. Kogan,“On the Origin of W Algebras,” Nucl. Phys. B 359 (1991) 635.   
[34] J.de Boer and J. I. Jottar,“Boundary Conditions and Partition Functions in Higher Spin AdS $_ 3$ /CFT $2$ ,” arXiv:1407.3844 [hep-th].   
[35] A. Marshakov and A. Morozov,“A Note on W(3) Algebra,” Nucl. Phys. B 339 (1990) 79 [Sov. Phys. JETP 70(1990) 403].   
[36] J.Gomis, J. Herrero, K. Kamimura and J. Roca, “Finite W(3) Transformations in a Multitime Approach,” Phys. Lett.B 339(1994) 59 [hep-th/9409024].