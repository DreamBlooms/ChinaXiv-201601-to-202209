# Modular Properties of 3D Higher Spin Theory

Wei Li, $a$ Feng-Li Lin, $b$ and Chih-Wei Wang $b$

$a$ Max-Planck-Institut fir Gravitationsphysik, Albert-Einstein-Institut, Am Muhlenberg 1， 14476 Golm, Germany wei.li@aei.mpg.de

（204号 $\boldsymbol { b }$ Department of Physics, National Taiwan Normal University, Taipei, 116, Taiwan linfengli@phy.ntnu.edu.tw，freeform1111@gmail.com

# Abstract

In the three-dimensional ${ \mathfrak { s l } } ( N )$ Chern-Simons higher-spin theory, we prove that the conical surplus and the black hole solution are related by the S-transformation of the modulus of the boundary torus. Then applying the modular group on a given conical surplus solution, we generate a‘ $\operatorname { S L } ( 2 , \mathbb { Z } )$ family of smooth constant solutions. We then show how these solutions are mapped into one another by coordinate transformations that act non-trivially on the homology of the boundary torus.

After deriving a thermodynamics that applies to all the solutions in the ‘SL $( 2 , \mathbb { Z } )$ 1 family, we compute their entropies and free energies,and determine how the latter transform under the modular transformations. Summing over all the modular images of the conical surplus, we write down a (tree-level) modular invariant partition function.

# Contents

1 Introduction and Summary 1

# Basics of 3D higher-spin theory 3

2.1 Action 4   
2.2 Asymptotic symmetries . 5   
2.3 Smooth solutions 6

# 3Thermodynamics 11

3.1Variational principle 13   
3.2 On-shell action, free energy,and entropy 17

# 4 Conical surplus and black hole are S-dual 21

4.1 S-transformation of holonomy condition and on-shell charges 22   
4.2 Coordinate transformation between conical surplus and black hole 25   
4.3 S-transformation of free energies . 26   
4.4 Example-1: $N = 3$ case. 30

# 5 $\mathbf { S L } ( 2 , \mathbb { Z } )$ family of smooth solutions 32

5.1 Solution 32   
5.2 Reasoning from dual CFT 35   
5.3 Coordinate transformations between members of ‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family 36   
5.4 Mapping of the free energy 38   
5.5 Modular invariant full partition function 40

# 6 Discussion 40

6.1Modular invariance of integrability condition 41   
6.2Canonical vs.holomorphic 43   
A Solving $\sigma _ { s }$ in terms of $\mu _ { s }$ 44   
B SL $( 2 , \mathbb { Z } )$ family in spin-2 case 45   
C Example-2: $N = 4$ （204号 46

# 1 Introduction and Summary

In the theory of the three-dimensional pure Einstein gravity with a negative cosmological constant, as there is no propagating degree of freedom in the bulk, all asymptotically AdS solutions are locally diffeomorphic and differ only in their global structures [1-4]. In Euclidean signature, starting with a thermal AdS $_ 3$ ，whose conformal boundary is a torus with modulus $\tau$ ， we can obtain an ${ \mathrm { \cdot S L } } ( 2 , \mathbb { Z } ) \qquad $ family of solutions via modular transformations ( $\textstyle \tau \mapsto { \frac { a \tau + b } { c \tau + d } }$ ） on the modulus of the boundary torus [5]. In particular, the S-transformation $\tau \mapsto - { \frac { 1 } { \tau } }$ maps the AdS $_ 3$ into a BTZ black hole. The full modular invariant partition function consists of a sum of all the modular images of the AdS $_ 3$ partition function: $\begin{array} { r } { Z [ \tau ] = \sum Z _ { \mathrm { A d S } _ { 3 } } [ \frac { a \tau + b } { c \tau + d } ] } \end{array}$ [6]. One can then study the phase structure using $Z [ \tau ]$ ， and for example show how HawkingPage transition [7] occurs when $\tau$ moves across the boundary between different fundamental domains [5,6,8].

Vasiliev's higher-spin theory is a generalization of the gravity theory; besides the graviton,it contains massless spin- $s$ fields with $s \geq 3$ ; and it lives in spaces with non-zero constant curvatures,i.e. AdS or dS spaces [9-12]. In three dimensions, it can be consistently truncated to a Chern-Simons subsector after the scalar in the theory is decoupled [13,14].1 We only consider AdS space in this paper. In AdS $_ 3$ ， the gauge algebra of this Chern-Simons theory is an infinite-dimensional Lie algebra $\mathrm { { h s } } [ \lambda ]$ [15,16],which at $\lambda = N$ reduces to the finite-dimensional ${ \mathfrak { s l } } ( N )$ [9,17]. The 3D Chern-Simons high-spin theory is a straightforward generalization of the ${ \mathfrak { s l } } ( 2 )$ Chern-Simons theory (the alternative formulation of the 3D pure gravity with a negative cosmological constant [18,19]) and share its essential features: in particular, it does not have any propagating degree of freedom in the bulk of the three-manifold （20 $\mathcal { M }$ ; the topology of $\mathcal { M }$ and the boundary data on $\partial M$ determine the dynamics.

In the Chern-Simons higher-spin theory, two types of smooth solutions have been found and studied: the conical surplus constructed by [20] and the black hole by [21]. They can be viewed as the higher-spin-charge-carrying generalizations of the AdS $_ 3$ and BTZ black hole, respectively. Since the notion of the boundary torus stil exists in the higher-spin version of the Chern-Simons theory, we can ask whether these two solutions,the conical surplus and the black hole,are related via an S-transformation of the modulus of the boundary torus.

In some sense, this has to happen since these two solutions reduce to AdS $_ 3$ and BTZ when all the higher-spin charges are set to zero. The non-trivial part of the story is this: the boundary modulus $\tau$ can be considered as the thermodynamical conjugate of the spin-2 charge,and in the higher-spin theory, the spin-2 field is coupled with all the higher-spin fields, therefore a transformation of $\tau$ inevitably induces the corresponding transformations on the chemical potentials of all the higher-spin charges. The crux in generalizing the modular properties of the spin-2 theory to a higher-spin theory is in determining this induced transformations on the higher-spin chemical potentials.

For this purpose,one first needs a consistent description of the thermodynamics of the given solution. Up till now this is absent for the conical surplus; however for the black hole an extensive literature on its thermodynamics has already emerged: e.g. a ‘holomorphic' approach represented by [21-26] and a ‘canonical’ one represented by [27-29].

In this paper we choose the ‘canonical’ formalism because,as we will show later, in this formalism important quantities and equations are manifestly modular invariant or covariant.

In the‘canonical' formalism we generalize the thermodynamics of the black hole to include all smooth stationary solutions.

Once the thermodynamics of the conical surplus is established, we determine the required transformation on the higher-spin chemical potential accompanying the S-transformation on the boundary modulus $\tau \mapsto - { \frac { 1 } { \tau } }$ ，and prove that the conical surplus and the black hole are S-dual. We then show that the black hole and the conical surplus are related by a coordinate transformation (that changes the modular parameter of the boundary torus from $\tau$ to $- { \frac { 1 } { \tau } }$ ）

Then we generalize from the S-transformation to the full modular group: starting with a higher-spin-charge-carrying conical surplus solution and applying on it the full modular group, we can generate an ‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family of smooth stationary solutions. They are all connected by coordinate transformations that act non-trivially on the homology of the boundary torus. Their free energies hence their on-shell partition functions are related via modular transformations. The full modular invariant partition function then involves summing over all the modular images of the conical surplus.

The paper is organized as follows. In Section 2 we briefly review some basics of 3D ${ \mathfrak { s l } } ( N )$ higher-spin theory, summarize known stationary smooth solutions, and define new smooth stationary solutions in the‘SL $( 2 , \mathbb { Z } )$ family. In Section 3 we formulate a thermodynamics that is universal to all members of the‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family (including conical surplus and black hole). Then in Section 4 we prove that a conical surplus can be mapped into a black hole via an S-transformation of the modulus of the boundary torus. In section 5 we show how to generate an‘SL $( 2 , \mathbb { Z } )$ ’ family of smooth solutions. We summarize and discuss open problems in section 6. In Appendix A we present a detailed proof for a statement that is central to our paper; in Appendix B we review the spin-2 story; finally in Appendix C we discuss ${ \mathfrak { s l } } ( 4 )$ theory as a concrete example.

# 2 Basics of 3D higher-spin theory

In this section we first review some basics of the three-dimensional ${ \mathfrak { s l } } ( N )$ higher-spin theory (for more details see the earlier works [20,21,30] and the reviews [31,32]). Then we summarize known smooth solutions in this theory,i.e. the conical surplus and the black hole,and meanwhile prepare the readers for our later discussion on general smooth solutions. In this paper we focus on stationary, axially symmetric, solutions.

# 2.1 Action

In three dimensions,the Einstein-Hilbert action with a negative cosmological constant $\Lambda$ can be rewritten in terms of an ${ \mathfrak { s l } } ( 2 , \mathbb { R } ) \oplus { \mathfrak { s l } } ( 2 , \mathbb { R } )$ Chern-Simons theory (up to a boundary term) [18,19]:

$$
S = S _ { \mathrm { C S } } [ A ] - S _ { \mathrm { C S } } [ \bar { A } ] \qquad \mathrm { w i t h } \quad S _ { \mathrm { C S } } [ A ] = \frac { k } { 4 \pi } \int _ { \mathcal { M } } \mathrm { T r } [ A \wedge d A + \frac { 2 } { 3 } A \wedge A \wedge A ]
$$

where $\mathcal { M }$ is a locally AdS manifold; $A$ and $A$ are ${ \mathfrak { s l } } ( 2 , \mathbb { R } )$ gauge fields; the trace $\mathrm { T r } ^ { \mathbf { \Omega } }$ is on $^ 3$ the2-dimensionalrepresentationof ${ \mathfrak { s l } } ( 2 )$ and the level $\begin{array} { r } { k = \frac { l _ { \mathrm { A d S _ { 3 } } } } { 4 G _ { N } } } \end{array}$ This trick (of rewriting Einstein-Hilbert action with a negative $\Lambda$ into a gauge theory) only works in three dimensions.

On the other hand, the three-dimensional Vasiliev higher-spin theory is also much more   
tractable than its higher-dimensional siblings. Besides the gauge fields, the theory has only   
one additional scalar field,which can be consistently decoupled since it is not part of the   
higher-spin multiplet in 3D.The gauge field subsector can then be written as a Chern-Simons   
theory (2.1) with $A$ and $A \in \mathrm { { h s } } [ \lambda ]$ ,which is an infinite-dimensional Lie algebra and at $\lambda = N$   
reduces to ${ \mathfrak { s l } } ( N )$ (after quotiented by an infinite ideal). In this paper we will focus on the   
3D ${ \mathfrak { s l } } ( N )$ Chern-Simons theory. The trace‘ $\mathrm { \Delta } ^ { \prime } \mathrm { \Delta } \mathrm { I \dot { r } }$ ’in the Chern-Simons action (2.1） is now on   
the $N$ -dimensional representation of ${ \mathfrak { s l } } ( N )$ and the level becomes $\begin{array} { r } { k = \frac { \ell _ { \mathrm { A d S } } } { 4 G _ { N } } \frac { 1 } { 2 \mathrm { T r } [ ( L _ { 0 } ) ^ { 2 } ] } } \end{array}$ 2 ：

Now let us parametrize the base manifold $\mathcal { M }$ . Since the theory has a negative cosmological constant, we choose the boundary condition to be asymptotically AdS $_ 3$ . A constant-time slice of an asymptotically AdS $_ 3$ space $\mathcal { M }$ is topologically a disc. Specify a radial coordinate $\rho$ and an angular coordinate $\phi$ ， the coordinate is then $\{ \rho , t , \phi \}$ . The asymptotic boundary （20 $\partial \mathcal { M }$ isat $\rho \to \infty$ and the boundary coordinates are $\{ t , \phi \}$

In this paper, we focus on Euclidean signature. The Wick rotation into Euclidean signature is via $t \mapsto i t _ { E }$ and the coordinate becomes $\{ \rho , z , \bar { z } \}$ with

$$
z \equiv \phi + i t _ { E } \ .
$$

Accordingly, the gauge symmetry becomes ${ \mathfrak { s l } } ( N , \mathbb { C } )$ . The connection $A \in { \mathfrak { s l } } ( N , \mathbb { C } )$ ; and in the representation we will choose, $A$ is $A$ 's anti-hermitean conjugate:3

$$
\bar { A } = - A ^ { \dagger } .
$$

for $A$ can then be inferred using (2.3).

The Chern-Simons action (2.1) has gauge degrees of freedom $A \sim A + d \Lambda$ ，which allows us to fix the gauge as:

$$
A ( \rho , z , \bar { z } ) = b ^ { - 1 } ~ a ( z , \bar { z } ) ~ b + b ^ { - 1 } ~ d b
$$

where $b = e ^ { \rho L _ { 0 } }$ is an $\operatorname { S L } ( N )$ -valued O-form, and $a$ is an ${ \mathfrak { s l } } ( N )$ -valued 1-form on the boundary $\partial \mathcal { M }$

$$
a = a _ { z } d z + a _ { \bar { z } } d \bar { z } .
$$

# 2.2 Asymptotic symmetries

The ${ \mathfrak { s l } } ( 2 )$ subalgebra corresponds to the spin-2 (i.e. gravity） sector, with generators $\{ L _ { 0 , \pm 1 } \}$ whose commutators are:

$$
\left[ L _ { m } , L _ { n } \right] = ( m - n ) L _ { m + n } , \qquad m , n = - 1 , 0 , 1 .
$$

(We will also sometimes write $L _ { n } = W _ { n } ^ { ( 2 ) }$ .）From the ${ \mathfrak { s l } } ( N )$ gauge symmetry, we first need to make a choice as to which ${ \mathfrak { s l } } ( 2 )$ subalgebra corresponds to the gravity sector, namely we need to choose how the gravity ${ \mathfrak { s l } } ( 2 )$ embeds in the full gauge algebra ${ \mathfrak { s l } } ( N )$ .The choice of this embedding then determines the spectrum of the theory. The principal embedding is particularly simple because the field of each spin appears once and only once. In this paper we only discuss the principal embedding and a generalization to other embeddings is straightforward.

Next, one can choose the boundary condition for $A$ and determine the asymptotic sym metry group. This was done in [30,34-36]. In the absence of sources, the asymptotic AdS condition implies

$$
A _ { \bar { z } } = 0 .
$$

However this boundary condition (2.7) is too weak and gives rise to a phase space that is too large (with an affine ${ \mathfrak { s l } } ( N )$ algebra as its asymptotic symmetry). An additional boundary condition was proposed by [30] to supplement (2.7) (see also [37] for the spin-2 case):

$$
( A - A _ { A d S } ) | _ { \rho \to \infty } = { \mathcal O } ( 1 ) ,
$$

which reduces the phase space by imposing a first-class constraint on the ${ \mathfrak { s l } } ( N )$ affine algebra and results in a $\mathcal { W } _ { N }$ algebra as the asymptotic symmetry. This is the bulk realization of the Drinfeld-Sokolov reduction (the reduction of an affine algebra to a $\mathcal { W }$ -algebra) [38].

In the process of the Drinfeld-Sokolov reduction， different gauge choices give diferent bases for the $\mathcal { W } .$ -algebra. A particular convenient choice is the highest-weight gauge,which gives rise to a $\mathcal { W }$ -algebra in which all $W ^ { ( s ) }$ are primaries with respect to the lowest spins [30,36]. Since there is no spin-1 feld in the ${ \mathfrak { s l } } ( N )$ Chern-Simons theory, all $W ^ { ( s \ge 3 ) }$ fields are Virasoro primaries:

$$
[ L _ { m } , W _ { n } ^ { ( s ) } ] = [ ( s - 1 ) m - n ] W _ { m + n } ^ { ( s ) } , \qquad s = 3 , \ldots , N , \quad m , n \in \mathbb { Z } .
$$

This is the gauge we will use throughout this paper.4

Recall that in the spin-2 case the bulk isometry ${ \mathfrak { s l } } ( 2 )$ is given by the‘wedge’ subalgebra (generated by $L _ { - 1 , 0 , 1 }$ ）of Virasoro algebra. Here the $( N ^ { 2 } - 1 )$ -dimensional bulk isometry ${ \mathfrak { s l } } ( N )$ is generated by $W _ { m } ^ { ( s ) }$ with $s = 2 , \ldots , N$ and $m = - s + 1 , \ldots , s - 1$ .An explicit representation of (2.9) for $m \leq | N |$ is [39]:

$$
W _ { n } ^ { ( s ) } = ( - 1 ) ^ { s - n - 1 } { \frac { ( s + n - 1 ) ! } { ( 2 s - 2 ) ! } } ( \mathrm { A d j } _ { L _ { - 1 } } ) ^ { s - n - 1 } ( L _ { 1 } ) ^ { s - 1 }
$$

where the adjoint action $\mathrm { A d j } _ { A } B = \lfloor A , B \rfloor$ . Lastly, we will choose a convention in which

$$
\left( L _ { m } \right) ^ { \dagger } = ( - 1 ) ^ { m } L _ { - m }
$$

which together with (2.10) implies $( W _ { m } ^ { ( s ) } ) ^ { \dagger } = ( - 1 ) ^ { m } W _ { - m } ^ { ( s ) }$ for $s = 2 , \ldots , N$ . In this convention we have (2.3).

# 2.3 Smooth solutions

# 2.3.1 Equations of motion

The equation of motion of the Chern-Simons action is the flatness condition for $A$ ： $F \equiv$ （204号 $d A + A \land A = 0$ . In the gauge (2.4), this translates into the flatness of $a$ ：

$$
f \equiv d a + a \wedge a = 0 \ .
$$

In this paper we will only consider axially-symmetric, stationary， solutions. For these solutions, $A$ has only $\rho$ -dependence. In the gauge (2.4） ,this means that $a$ is constant, hence throughout this paper we will refer to them as constant solutions (although they can rotate).

Their equations of motion (2.12) reduce to

$$
\left[ a _ { z } , a _ { \bar { z } } \right] = 0 .
$$

Once $a _ { z }$ is fixed, $a _ { \bar { z } }$ can be determined via the equation of motion (2.13)，whose solution is simply $a _ { \bar { z } }$ being an arbitrary traceless function of $a _ { z }$ . By Cayley-Hamilton theorem，an arbitrary function of a $N \times N$ matrix $a _ { z }$ (that is generic enough) truncates to a polynomial of $a _ { z }$ of degree $( N - 1 )$ ; therefore $a _ { \bar { z } }$ has the expansion [51]:

$$
a _ { \bar { z } } = \sum _ { s = 2 } ^ { N } \sigma _ { s } \left[ ( a _ { z } ) ^ { s - 1 } - \frac { \mathrm { T r } ( a _ { z } ) ^ { s - 1 } } { N } { \bf 1 } \right] .
$$

Up to now, $\left\{ \sigma _ { s } \right\}$ are $( N - 1 )$ arbitrary complex parameters. Later we will show how they are fixed in terms of the chemical potentials of the higher-spin charge.

# 2.3.2 Holonomy condition

In this subsection， we define the condition that characterizes a generic smooth constant solution. The known solutions,i.e. the conical surplus and the black hole,are the two special cases.

Any given $a _ { z }$ together with the $a _ { \bar { z } }$ related by it via (2.14) would solve the equation of motion (2.13). However,requiring the solution be smooth imposes a much more stringent constraint. Since in the higher-spin theory,the spin-2 field is coupled with all higher-spin fields hence the Ricci scalar is no longer a gauge invariant entity, the smoothness condition need to be prescribed in terms of other，gauge-invariant， observables. In the 3D ChernSimons theory, the natural candidate is the holonomy around a one-cycle $\zeta$ in $\mathcal { M }$ ：

$$
\operatorname { H o l } _ { \mathcal { C } } ( A ) \equiv \mathcal { P } e ^ { \oint _ { \mathcal { C } } A } .
$$

The smoothness condition is then simply that the holonomy around any contractible cycle (A-cycle) must be trivial, i.e. ${ \mathrm { H o l } } _ { \mathrm { A } } ( A ) \in$ center of the gauge group [20,21].

First let us describe the cycles in this 3D Euclidean spacetime. The asymptotic boundary of the Euclidean AdS $_ 3$ is a torus. First we fix its homology basis $( \alpha , \beta )$ with $\alpha \cap \beta = 1$ . Then we give this torus a complex structure. This allows us to define a holomorphic 1-form $\omega$ ; we can choose its basis such that $\begin{array} { r } { \oint _ { \alpha } \omega = 1 } \end{array}$ ,then $\tau \equiv \oint _ { \beta } \omega$ defines the modulus of the torus. Once the modulus of the boundary torus is fixed, different bulk geometries correspond to different ways of flling the solid torus. We first fix the primitive contractible cycle (A-cycle), then the primitive non-contractible cycle (B-cycle) that satisfies AnB $= 1$ is uniquely determined up to shifts in the A-cycle. The (A,B) homology basis is related to the original $( \alpha , \beta )$ basis

viaamodular transformation:

$$
{ \binom { \mathrm { B } } { \mathrm { A } } } = { \binom { a } { c } } \ { \binom { b } { \alpha } } \qquad { \mathrm { w i t h } } \quad { \binom { a } { c } } \ b \in \mathrm { P S L } ( 2 , \mathbb { Z } )
$$

with

$$
\mathrm { L } ( 2 , \mathbb { Z } ) \equiv \mathrm { S L } ( 2 , \mathbb { Z } ) / Z _ { 2 } \ , \qquad \mathrm { S L } ( 2 , \mathbb { Z } ) \equiv \{ \ \left. { \left( \begin{array} { l l } { a } & { b } \\ { c } & { d } \end{array} \right) } \ \right| \ a , b , c , d \in \mathbb { Z } , a d - b c = 1 \} \ .
$$

Then the torus with (A,B) as the homology basis but with the same holomorphic 1-form $\omega$ has a modular parameter

$$
\mathrm { m o d u l a r ~ p a r a m e t e r } \equiv \frac { \int _ { \mathrm { B } } \omega } { \int _ { \mathrm { A } } \omega } = \frac { a \tau + b } { c \tau + d } ,
$$

which is a modular transformation of the original modulus $\tau$ . Throughout this paper， we use $\gamma$ to denote an element of the modular group PSL $( 2 , \mathbb { Z } )$ and define $\hat { \gamma } \tau$ to be its action on T:5

$$
\gamma \equiv \left( { a \atop c } \ { \begin{array} { l } { { b } } \\ { { d } } \end{array} } \right) \in \mathrm { P S L } ( 2 , \mathbb { Z } ) : \qquad \tau \longmapsto { \hat { \gamma } } \tau \equiv { \frac { a \tau + b } { c \tau + d } } .
$$

Also note that throughout this paper， by modular parameter we mean the ratio of the (complex) length of the non-contractible(B) cycle and that of the contractible(A) cycle, as defined in (2.18);and we reserve the term modulus for $\tau$ ：

The conical surplus solutions that carry higher-spin charges has a contractible cycle （204号 $\phi \sim \phi + 2 \pi$ , just like the AdS $_ 3$ [20].

$$
\mathrm { C S } \colon \qquad \gamma = \left( \begin{array} { l l } { { 1 } } & { { 0 } } \\ { { 0 } } & { { 1 } } \end{array} \right) \quad \Longrightarrow \qquad \mathrm { A - c y c l e } : \quad z \sim z + 2 \pi \ : ,
$$

Accordingly, the holonomy around this $\phi$ -cycle needs to lie in the center of the gauge group:

$$
\operatorname { H o l } _ { \phi } ( A ) = b ^ { - 1 } e ^ { 2 \pi \omega _ { \phi } } b \ \in \ { \mathrm { c e n t e r ~ o f ~ } } G
$$

where $\omega _ { \phi }$ is defined as6

$$
\omega _ { \phi } \equiv a _ { z } + a _ { \bar { z } } .
$$

Let's denote by ‘ $\Lambda \left( \omega \right) ^ { \prime }$ the vector of eigenvalues of a matrix $\omega$

$$
U \omega U ^ { - 1 } = \mathrm { D i a g o n a l M a t r i x } [ \lambda _ { 1 } , \dots , \lambda _ { N } ] \quad \Longrightarrow \quad \Lambda \left( \omega \right) \equiv \vec { \lambda } = \left( \lambda _ { 1 } , \dots , \lambda _ { N } \right) .
$$

The center of $\mathrm { S L } ( N , \mathbb { C } )$ is $e ^ { - 2 \pi i { \frac { \pi } { N } } } \mathbf { 1 }$ with $m \in \mathbb { Z } _ { N }$ , which implies that the eigenvalues of $\omega _ { \phi }$ （20 satisfies [20]:

$$
\Lambda \left( \omega _ { \phi } \right) = i \vec { n } ,
$$

where the vector ${ \vec { n } } = ( n _ { 1 } , \ldots , n _ { N } )$ with $\begin{array} { r } { n _ { i } \in \mathbb { Z } - \frac { m } { N } } \end{array}$ ， $n _ { i } \neq n _ { j }$ for $i \neq j$ ，and $\begin{array} { r } { \sum _ { i } ^ { N } n _ { i } = 0 } \end{array}$ ，and most importantly $n _ { i }$ must come in pairs for the solution to be a conical surplus,i.e. if we order $\{ n _ { i } \}$ into a monotone sequence then

$$
n _ { i } + n _ { N + 1 - i } = 0 \ .
$$

This imposes a very strong constraint on $m$ $m = 0$ for $N$ odd,and $m = 0$ or $\begin{array} { l } { { \frac { N } { 2 } } } \end{array}$ for $N$ even. But recall that the center of SL $( N , \mathbb { R } )$ is precisely $\mathbf { 1 }$ for $N$ odd and $\pm 1$ for $N$ even; $^ 7$ therefore the constraint (2.25) forces the holonomy to lie in the center of the Lorentzian gauge group SL ${ \mathbf \xi } _ { \iota } ( N , \mathbb { R } )$ rather than that of the Euclidean one SL $( N , \mathbb { C } )$ . In summary the vector $\vec { n }$ obeys

$$
\begin{array} { r } { \mathrm { \Lambda } ^ { \prime } = ( n _ { 1 } , \dots , n _ { N } ) , \quad n _ { i } \in \left\{ \begin{array} { l l } { \mathbb { Z } } & { N \mathrm { \ o d d } } \\ { \mathbb { Z } \mathrm { \ o r \ } \mathbb { Z } + \frac { 1 } { 2 } } & { N \mathrm { \ e v e n } } \end{array} \right. , \quad n _ { i } \neq n _ { j } \mathrm { \ f o r \ } i \neq j , \quad n _ { i } + n _ { N } } \end{array}
$$

and can be considered as a ‘topological charge' of the solution; and we will term it holonomy vector’. The global AdS $_ 3$ space corresponds to $\vec { n } = \bar { \rho }$ (the Weyl vector of ${ \mathfrak { s l } } ( N )$ ，with $\begin{array} { r } { \rho _ { i } = \frac { N + 1 } { 2 } - i \ ' , } \end{array}$ , and generic $\vec { n }$ 's satisfying (2.26) give conical surpluses [20]. For discussions on the conical surplus in $\mathrm { { h s } } [ \lambda ]$ Chern-Simons theory see e.g. [40-45]

On the other hand, the (Euclidean) black hole has a contractible cycle $z \sim z + 2 \pi \tau$

$$
\mathrm { B H z } \qquad \gamma = \left( \begin{array} { l l } { { 0 } } & { { - 1 } } \\ { { 1 } } & { { 0 } } \end{array} \right) \quad \Longrightarrow \qquad \mathrm { A - c y c l e : } \quad z \sim z + 2 \pi \tau \ ,
$$

Accordingly, the trivial holonomy condition is [21]:

$$
\mathrm { H o l } _ { t } ( A ) = b ^ { - 1 } e ^ { 2 \pi \omega _ { t } } b \in \mathrm { c e n t e r ~ o f ~ } \mathrm { S L } ( N , \mathbb { R } ) ,
$$

with $\omega _ { t }$ defined as

$$
\omega _ { t } \equiv \tau a _ { z } + \bar { \tau } a _ { \bar { z } } .
$$

Namely

$$
\Lambda \left( \omega _ { t } \right) = i \stackrel { \triangledown } { \vec { n } } ,
$$

with $\vec { n }$ satisfying the same set of conditions as the conical surplus (2.26). $\vec { n } = \bar { \rho }$ corresponds to the higher-spin-charge-carrying BTZ black hole first constructed in [21]； and other $\vec { n }$ 's give more generic higher-spin black holes.

This definition of smooth solution by the holonomy around the contractible cycle can be easily generalized to include solutions whose modular parameter is a generic $\hat { \gamma } \tau$ (other than $\tau$ or $- { \frac { 1 } { \tau } }$ ). For a generic $\gamma = { \binom { a } { c } } \ k \in \operatorname { P S L } ( 2 , \mathbb { Z } )$ , the A/B cycles are

$$
\begin{array} { r l } { \mathrm { C o n t r a c t i b l e ( A ) \mathrm { - } c y c l e : } \qquad } & { { } z \sim z + 2 \pi ( c \tau + d ) , } \\ { \mathrm { N o n \mathrm { - } c o n t r a c t i b l e ( B ) \mathrm { - } c y c l e : } \qquad } & { { } z \sim z + 2 \pi ( a \tau + b ) . } \end{array}
$$

Accordingly, for a smooth solution, the holonomy around the A-cycle should be trivial

$$
\operatorname { H o l } _ { \mathrm { A } } ( A ) = b ^ { - 1 } e ^ { 2 \pi \omega _ { \mathrm { A } } } b \in { \mathrm { ~ c e n t e r ~ o f ~ } } \mathrm { S L } ( N , \mathbb { R } ) ,
$$

with the holonomy matrix around the A-cycle given by

$$
\omega _ { \mathrm { A } } \equiv \frac { 1 } { 2 \pi } \oint _ { \mathrm { A } } a = ( c \tau + d ) a _ { z } + ( c \bar { \tau } + d ) a _ { \bar { z } } ,
$$

namely

$$
\Lambda \left( \omega _ { A } \right) = i \vec { n }
$$

again with $\vec { n }$ given by (2.26). Here we also write down the holonomy matrix around the B-cycle for comparison and for later use:

$$
\omega _ { \mathrm { { B } } } \equiv { \frac { 1 } { 2 \pi } } \oint _ { \mathrm { { B } } } a = ( a \tau + b ) a _ { z } + ( a \bar { \tau } + b ) a _ { \bar { z } } .
$$

For given $\vec { n }$ and $\tau$ , varying $\gamma \in \mathrm { { P S L } } ( 2 , \mathbb { Z } )$ then generates a ‘ $\operatorname { S L } ( 2 , \mathbb { Z } )$ family of solutions (a term coined in [5]). Since the T-transformation $\tau \mapsto \tau + 1$ does not change the A/B cycle (2.31), we should consider the subgroup of $\Gamma \equiv \mathrm { P S L } ( 2 , \mathbb { Z } )$ （20

$$
\Gamma _ { \infty } \equiv \{ \ \left( \begin{array} { c c } { { 1 } } & { { m } } \\ { { 0 } } & { { 1 } } \end{array} \right) \ | \ m \in \mathbb { Z } \} / Z _ { 2 } \ \subset \ \Gamma \equiv \mathrm { P S L } ( 2 , \mathbb { Z } ) .
$$

to be the stabilizer； hence the ${ \mathrm { S L } } ( 2 , \mathbb { Z } ) ^ { \prime }$ family is actually the quotient $\Gamma _ { \infty } \backslash \Gamma$ .Since a $\gamma$ （20 in $\Gamma _ { \infty } \backslash \Gamma$ is uniquely given by the lower row $( c , d )$ (which always satisfies $\operatorname* { g c d } ( c , d ) = 1$ )，an

enumeration of all the members in this family is thus [46]:

$$
\forall ( c , d ) \qquad \mathrm { w i t h } \quad c , d \in \mathbb { Z } , \quad c \geq 0 , \quad \operatorname* { g c d } ( c , d ) = 1 .
$$

Lastly, the holonomy vector for $A$ is always related to that of $A$ via

$$
\vec { \bar { n } } = \vec { n }
$$

in the anti-hermitean basis we choose. We summarize the discusson of this subsection in the following table:

<html><body><table><tr><td></td><td>EAdS: and CS</td><td>black hole</td><td>Smooth solution y</td></tr><tr><td>A-cycle</td><td>χ~z+2π</td><td>z~z+2πT</td><td>z ~ z+2π(cT+d)</td></tr><tr><td>B-cycle</td><td>z~z+2πT</td><td>z~z-2π</td><td>z ~ z +2π(aτ+b)</td></tr><tr><td>modular parameter</td><td>T</td><td>-1</td><td>a+d</td></tr><tr><td>A-cycle holonomy</td><td>W=a+az</td><td>Wt=Taz+Taz</td><td>WA= (cT+d)az+(cT+d)az</td></tr></table></body></html>

# 3 Thermodynamics

The conical surplus solution constructed in [20] has higher-spin charges but with no chemical potential turned on,and hence there is no study on its thermodynamics yet. Meanwhile, the thermodynamics of the black hole in the ${ \mathfrak { s l } } ( N )$ Chern-Simons theory has been extensively studied,and depending on the choice of the spin-2 conserved charge (the zero-mode of the energy-momentum tensor） there are two main approaches. In the‘holomorphic' formalism (initiated in [21] and used in [22-26]),the spin-2 conserved charge (for the left-mover $A$ （20 $T$ is holomorphic. In the ‘canonical’ formalism,the spin-2 conserved charge $T$ is obtained either via a canonical approach [28,29] a la Regge-Teitelboim [50],or via a direct derivation from the variational principle [27] (for a precursor see [51]) which gives the same result; in this formalism $T$ is not holomorphic and receives contribution from the right-mover $A$ . The different definitions of $( T , T )$ in turn leads to different results for the integrability condition, the entropy，and finally the free energy. For more details see the discussion in [27]. (For other discussions on the black hole thermodynamics see [52,53].)

Now we would like to generalize the result of the thermodynamics of the black hole to the conical surplus and to all smooth constant solutions in the‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family. Which of the two formalism is better suited for this purpose? Usually the modularity (w.r.t. $\mathrm { { P S L } } ( 2 , \mathbb { Z } ) )$ （20 requires the holomorphicity of the theory. Therefore naively one would expect that the ‘holomorphic' formalism be the choice whereas the modular property be absent or at least obscured in the ‘canonical’ formalism.

However, the fact that in the‘canonical’ formalism $T$ lacks holomorphicity therefore modularity does not pose any problem in a discussion of the modular properties in this formalism. First of all， although the spin-2 conserved charge $T$ ， and hence the entropy, is not modular covariant, this is to be expected since they are not holomorphic to start with.Moreover they are only intermediate quantities. As we will show presently, all the other final quantities — the connection, the holonomy condition,and the free energy — are modular invariant or covariant. We will derive manifestly modular covariant expressions for them. We will also show later in Section 6 that the crucial consistency condition — the integrability condition (relating conserved charges of different spins)- is modular invariant in the‘canonical’ formalism.

On the other hand,as we will discuss in Section 6,in the ‘holomorphic’ formalism, it is not clear to us how to write down a simple modular transformation such that the various important relations — the holonomy condition,the integrability condition,etc - are modular invariant or covariant.

This leads us to choose the ‘canonical’ formalism developed in [27] for our generalization of thermodynamics of the black hole to all members of the‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family. In this section, we generalize the procedure in [27,51]

1. Vary the bulk action and identify the source and charge terms in the connection. 2. Write down the suitable boundary action to ensure the variational principle. 3. Identify the conjugate pair of energy and temperature, compute the free energy and entropy, and check the first law of thermodynamics.

to generic smooth constant solutions (including the conical surplus). In particular, we compute the on-shell action for generic solutions and write down the modular covariant expressions for the entropy and free energy.

One clarification: the construction of these general smooth constant solutions will only be shown later,in Section 5. However, since we frst need to know the thermodynamics of the conical surplus solution (in order to consistently turn on its chemical potentials） before we can discuss its relation with the black hole solution,and since the thermodynamics of all these smooth solutions can be discussed in an unified way (and with no need to know the full details of the solutions), we will study all of them at once now,and postpone the explicit construction of these solutions to Section 5.

# 3.1 Variational principle

In the presence of higher-spin conserved charges $Q _ { s }$ with $s = 3 , \ldots , N$ , the partition function (evaluated as an Euclidean path-integral) is a function of the boundary modulus $\tau$ and the chemical potential $\mu _ { s }$ conjugate to the higher-spin charge $Q _ { s }$ ：

$$
Z \left[ \tau ; \ \mu _ { s } \right] \equiv \int { \cal D } A { \cal D } \bar { A } e ^ { - I ^ { ( \mathrm { E } ) } }
$$

The free energy of the system is

$$
- \beta F \left[ \tau ; \ \mu _ { s } \right] = \ln Z \left[ \tau ; \ \mu _ { s } \right] .
$$

In this paper, we take the saddle point approximation (i.e. only include the clasical result): each classcal solution contributes $e ^ { - I ^ { ( \mathrm { E } ) } | _ { \mathrm { o n - s h e l l } } }$ .For each clascal solutionitsfreeergy $F ^ { \prime }$ (in the saddle point approximation) is given by

$$
- \beta { \cal F } = - { \cal I } ^ { ( \mathrm { E } ) } | _ { \mathrm { o n - s h e l l } } .
$$

In this section， we study the on-shell action of individual solutions; we will discuss the contributions from all saddle points to the partition function later in Section 5.

# 3.1.1 Variation of bulk action

For the discussion in this section, it is enough to know that a smooth constant solution can be defined by the condition that its holonomy around the A-cycle is trivial, i.e. equation (2.31), (2.32),and (2.34); and it is determined by the PSL $( 2 , \mathbb { Z } )$ element $\gamma$ ：

The thermodynamics for the case of $\begin{array} { r } { \gamma = \binom { 0 } { 1 } \quad \mathbf { \Sigma } _ { 0 } ^ { - 1 } \biggr ) } \end{array}$ (the higher-spin black hole with modular parameter $- \frac { 1 } { \tau }$ ） was already given in [27]. We now generalize its derivation to the generic smooth solution with modular parameter $\gamma = { \binom { a } { c } } \quad b \quad$ . The thermodynamical relation comes out of a direct variational calculation of the Chern-Simons action, which tells us how to add the boundary term once the choice of source/field is made. In this variational calculation, the modulus of the boundary torus should actively vary since it carries the physical information of the inverse temperature (and the twist along the angular direction） [27,56]. However, in the coordinate system $( z , { \bar { z } } )$ which we have been using,the modular parameter $\hat { \gamma } \tau$ is hidden in the identification of the A/B cycle; to make it appear explicitly we need to first switch to a coordinate system $( w , \bar { w } )$ that lives on a rigid torus with fixed modulus $\tau = i$ .The coordinate transformation from $( z , { \bar { z } } )$ to $( w , \bar { w } )$ is

$$
z = ( c \tau + d ) ( \frac { 1 - i \hat { \gamma } \tau } { 2 } w + \frac { 1 + i \hat { \gamma } \tau } { 2 } \bar { w } )
$$

and similarly for $z$ . The A/B cycle is mapped to

$$
\begin{array} { r l r l r l } { \mathrm { A - c y c l e } ; } & { } & { z \sim z + 2 \pi ( c \tau + d ) } & { } & { \longmapsto } & { } & { w \sim w + 2 \pi } \\ { \mathrm { B - c y c l e } ; } & { } & { z \sim z + 2 \pi ( a \tau + b ) } & { } & { \longmapsto } & { } & { w \sim w + 2 \pi i } \end{array}
$$

Since in the $( w , \bar { w } )$ coordinate the torus is rigid, the on-shell variation of the Euclidean Chern-Simons action

$$
I _ { \mathrm { b u l k } } ^ { \mathrm { ( E ) } } [ A ] = \frac { i k } { 4 \pi } \int \mathrm { T r } [ A \wedge d A + \frac { 2 } { 3 } A \wedge A \wedge A ]
$$

in this coordinates is simply

$$
\delta I _ { \mathrm { b u l k } } ^ { ( \mathrm { E } ) } [ A ] | _ { \mathrm { o n * s h e l l } } = - { \frac { i k } { 4 \pi } } \int _ { \partial M } \mathrm { T r } [ a \wedge \delta a ] = - { \frac { i k } { 4 \pi } } \int _ { \partial M } d w \wedge d \bar { w } \mathrm { T r } [ a _ { w } \delta a _ { \bar { w } } - a _ { \bar { w } } \delta a _ { w } ]
$$

and similarly for the $A$ term. From now on we will omit the superscript ( $\mathrm { E }$ ） since we will only discuss the Euclidean signature. Now we translate this back to the $( z , { \bar { z } } )$ coordinate. First,the volume element is

$$
i d w \wedge d \bar { w } = \frac { i } { \tau _ { 2 } } d z \wedge d \bar { z }
$$

which is invariant under the modular transformation $\tau \mapsto { \hat { \gamma } } \tau$ ．Second， the 1-form $a$ is invariant under the coordinate transformation (3.4),hence

$$
a _ { w } = ( c \tau + d ) ( \frac { 1 - i \hat { \gamma } \tau } { 2 } a _ { z } ) + ( c \bar { \tau } + d ) ( \frac { 1 - i \overline { { { \hat { \gamma } \tau } } } } { 2 } a _ { \bar { z } } )
$$

whose variation contains explicitly the $\delta \tau$ and $\delta \bar { \tau }$ term:

$$
\delta a _ { w } = ( c \tau + d ) ( \frac { 1 - i \hat { \gamma } \tau } { 2 } \delta a _ { z } ) + ( c \bar { \tau } + d ) ( \frac { 1 - i \overline { { { \hat { \gamma } \tau } } } } { 2 } \delta a _ { \bar { z } } ) + \frac { c - i a } { 2 } ( a _ { z } \delta \tau + a _ { \bar { z } } \delta \bar { \tau } )
$$

and similarly for $a _ { \bar { w } }$ . The integrand in(3.7) is thus

$$
\mathrm { T r } [ a _ { w } \delta a _ { \bar { w } } - a _ { \bar { w } } \delta a _ { w } ] \Big | _ { \hat { \gamma } \tau } = \tau _ { 2 } \mathrm { T r } [ a _ { z } \delta a _ { \bar { z } } - a _ { \bar { z } } \delta a _ { z } ] + \frac { i } { 2 } \mathrm { T r } [ ( a _ { z } + a _ { \bar { z } } ) ( a _ { z } \delta \tau + a _ { \bar { z } } \delta \bar { \tau } ) ]
$$

with

$$
\tau _ { 2 } \equiv \operatorname { I m } \tau
$$

However this is identical to the corresponding expression for the special case of the modular parameter being $- { \frac { 1 } { \tau } }$ ,i.e. the black hole (see Eq. (4.16) in [27]). Namely, the variation of the bulk action only depends on the modulus $\tau$ of the boundary torus but not on $\gamma$ , i.e. not on the identification of the A/B cycles. This is to be expected: for the theory with boundary torus of the modular parameter $\hat { \gamma } \tau$ ， the inverse temperature $\beta$ and the angular velocity $\theta$ is still given by the modular $\tau$ ：

$$
{ \frac { \theta + i \beta } { 2 \pi } } = \tau
$$

instead of $\hat { \gamma } \tau$ . Accordingly, the zero modes of the stress tensor $( T , T )$ should still be read off from the coefficients of $( \delta \tau , \delta \bar { \tau } )$ , instead of $( \delta ( \hat { \gamma } \tau ) , \delta ( \hat { \gamma } \bar { \tau } ) )$ . The above computation confrms this.

# 3.1.2 Charges and chemical potentials

The fact that the variation of the bulk action (3.11) actually does not explicitly depend on $\gamma$ means that all the solutions in this ‘ ${ \mathrm { S L } } ( 2 , \mathbb { Z } ) ^ { \prime }$ family should have the same identification of source/charge term inside the connection $( a , { \bar { a } } )$ . Since for later proofs we will be using some of the details on how $( a , { \bar { a } } )$ depends on the charge and the chemical potential, we will explain them again in detail here, instead of merely referring to the earlier paper [27].

The symmetry algebra ${ \mathfrak { s l } } ( N )$ is $( N ^ { 2 } - 1 )$ -dimensional, and can be spanned by the generators $W _ { m } ^ { ( s ) }$ with $s = 2 , \ldots , N$ and $m = - s + 1 , \ldots , s - 1$ . The construction (2.10） produces an orthogonal basis

$$
\mathrm { T r } [ W _ { m } ^ { ( s ) } W _ { n } ^ { ( t ) } ] = t _ { m } ^ { ( s ) } \delta ^ { s , t } \ \delta _ { m + n , 0 }
$$

where $t _ { m } ^ { ( s ) } \equiv \mathrm { T r } [ W _ { m } ^ { ( s ) } W _ { - m } ^ { ( s ) } ]$ is the normalization factor of $W _ { m } ^ { ( s ) }$

The additional boundary conditions (2.8) are first-class constraints, using which we can bring $a _ { z }$ intoaform wherethecharge matrix $\mathbf { Q }$ sitsinthehighest-weightdirection $W _ { - s + 1 } ^ { ( s ) }$ [54]:

$$
a _ { z } = L _ { 1 } + { \bf Q } \qquad { \bf Q } = \sum _ { s = 2 } ^ { N } \frac { Q _ { s } } { t ^ { ( s ) } } W _ { - s + 1 } ^ { ( s ) }
$$

where $Q _ { s }$ is the zero mode of the spin-s field $W ^ { s }$ and $t ^ { ( s ) } \equiv t _ { - s + 1 } ^ { s }$ . Note that in this basis

$$
Q _ { 2 } = \frac { 1 } { 2 } \operatorname { T r } \left[ ( a _ { z } ) ^ { 2 } \right] \qquad Q _ { 3 } = \frac { 1 } { 3 } \operatorname { T r } \left[ ( a _ { z } ) ^ { 3 } \right]
$$

but for spins $s \geq 4$ ， $\textstyle { \frac { 1 } { s } } \operatorname { T r } \left[ ( a _ { z } ) ^ { s } \right]$ is no longer simply $Q _ { s }$ ，e.g.

$$
{ \frac { 1 } { 4 } } \operatorname { T r } \left[ ( a _ { z } ) ^ { 4 } \right] = Q _ { 4 } + r _ { 1 } Q _ { 2 } ^ { 2 } \qquad { \frac { 1 } { 5 } } \operatorname { T r } \left[ ( a _ { z } ) ^ { 5 } \right] = Q _ { 5 } + r _ { 2 } Q _ { 2 } Q _ { 3 } \qquad \ldots
$$

where $r _ { i }$ 's are some $N$ -dependent rational numbers that can be computed using (2.10), e.g. for $N = 5$ ， $\textstyle r _ { 1 } = { \frac { 1 7 } { 5 0 } }$ and $\textstyle r _ { 2 } = { \frac { 3 1 } { 3 5 } }$ , etc. Nevertheless we choose this basis because the modular transformation of the connection $( a , { \bar { a } } )$ takes very simple form in this basis,as we will show presently.

（204号 $a _ { \bar { z } }$ should contain the information of the chemical potentials $\mu _ { s }$ 's.Following [27],we demand that the lowest weight terms (i.e. $W _ { s - 1 } ^ { ( s ) }$ terms) of $a _ { \bar { z } }$ are linear in $\mu$ , in analogue to the construction of $a _ { z }$ in (3.15):

$$
a _ { \bar { z } } = { \bf M } + ( \mathrm { t e r m s } \sim W _ { m \leq s - 2 } ^ { ( s ) } ) \qquad { \bf M } = { \frac { i } { 2 \tau _ { 2 } } } \sum _ { s = 3 } ^ { N } \mu _ { s } W _ { s - 1 } ^ { ( s ) }
$$

First note the absence of $\mu _ { 2 }$ in the definition of M: since we are now in Euclidean signature, theroleofμshouldbereplacedbythe modulusTof theboundarytorus.Theprefactor is chosen to normalize the $\mu _ { s } Q _ { s }$ term in the on-shell action (see (3.26))；and it is common to all solutions in the‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family,as explained in the previous subsection. And the presence of $\because$ is from the Wick rotation to the Euclidean signature.

From the definition (3.18) and the orthogonality of the $\{ W _ { m } ^ { ( s ) } \}$ basis, we have the following （20 $N - 1$ equations:

$$
\frac { 1 } { t ^ { ( s ) } } \operatorname { T r } [ W _ { - s + 1 } ^ { ( s ) } a _ { \bar { z } } ] = \left\{ \begin{array} { l l } { 0 } & { s = 2 } \\ { \frac { i } { 2 \tau _ { 2 } } \mu _ { s } } & { s = 3 , . . . , N } \end{array} \right.
$$

which can uniquely determine the $N \mathrm { ~ - ~ } 1 \ \{ \sigma _ { s } \}$ in(2.14) in terms of $\{ \mu _ { s } \}$ for given $\{ Q _ { s } \}$ Once $a _ { \bar { z } }$ is written in terms of $\mu _ { s }$ and $Q _ { s }$ we can use the holonomy condition to select the smooth solutions: e.g. (2.24) for conical surpluses, (2.30) for black holes,and (2.32) for more generic solutions labeled by $\gamma$ . In the canonical ensemble,the higher-spin charges are given and their conjugate chemical potentials are solved in terms of them,the boundary modulus （204号 $\tau$ ，and the holonomy vector $\vec { n }$ （20

$$
\mu _ { t } = \mu _ { t } ( \vec { n } ; \tau ; Q _ { s \geq 2 } ) t = 3 , \ldots , N
$$

In the grand canonical ensemble, the chemical potential $\mu _ { s \ge 3 }$ are given and the charges of the solution are solved in terms of $\mu _ { s }$ , the boundary modulus $\tau$ ， and the holonomy vector $\vec { n }$ （20

$$
Q _ { t } = Q _ { t } ( \vec { n } ; \tau ; \mu _ { s \geq 3 } ) \qquad t = 2 , \ldots , N
$$

# 3.1.3 Boundary action

Now that we have made a choice of charge/source terms in $( a _ { z } , a _ { \bar { z } } )$ ， we can solve for the boundary action which, when added to bulk action, makes sure that the variation of the full action has the correct form of [charge · $\delta$ source].

In this derivation,a useful identity is

$$
\mathrm { T r } \left[ L _ { 1 } a _ { \bar { z } } \right] = \mathrm { T r } \left[ [ L _ { 0 } , \mathbf { Q } ] a _ { \bar { z } } \right] = \frac { i } { 2 \tau _ { 2 } } \sum _ { s = 3 } ^ { N } ( s - 1 ) \mu _ { s } Q _ { s }
$$

where the first $\mathit { \Psi } ^ { \bullet } = \mathit { \Psi } ^ { \eta }$ can be proven using the definition (3.15), $[ a _ { z } , a _ { \bar { z } } ] = 0$ ， $[ L _ { 0 } , L _ { 1 } ] = - L _ { 1 }$ ， and the cyclic nature of the trace; and the second one is proven by expanding the right hand side of (3.22) in terms of (3.15) and using $[ L _ { 0 } , W _ { - s + 1 } ^ { ( s ) } ] = ( s - 1 ) W _ { - s + 1 } ^ { ( s ) }$ +1: And (3.22) is also equivalent to

$$
\mathrm { T r } [ a _ { z } a _ { \bar { z } } ] = \frac { i } { 2 \tau _ { 2 } } \sum _ { s = 3 } ^ { N } s \mu _ { s } Q _ { s }
$$

The appropriate boundary term is

$$
I _ { \mathrm { b n d y } } = - \frac { k } { 2 \pi } \int _ { \partial \cal M } d ^ { 2 } z \mathrm { T r } [ ( a _ { z } - 2 L _ { 1 } ) a _ { \bar { z } } ]
$$

Combining the variation of this boundary term with that of the bulk one (eq. (3.7) with (3.11)), one can first read off the spin-2 conserved charges $T$ conjugate to $\tau$

$$
T = \frac { 1 } { 2 } \operatorname { T r } \left[ ( a _ { z } ) ^ { 2 } \right] + \operatorname { T r } \left[ a _ { z } a _ { \bar { z } } \right] - \frac { 1 } { 2 } \operatorname { T r } \left[ ( \bar { a } _ { z } ) ^ { 2 } \right]
$$

and then write down the variation of the full action (bulk plus boundary):

$$
\begin{array} { l } { { { \displaystyle { \bf { \bar { E } } } ) } _ { | \mathrm { o n - s h e l l } } = \delta I _ { \mathrm { b u l k } } ^ { ( \mathrm { E } ) } | _ { \mathrm { o n - s h e l l } } + \delta I _ { \mathrm { b n d y } } ^ { ( \mathrm { E } ) } | _ { \mathrm { o n - s h e l l } } } } \\ { { { \displaystyle ( 2 \pi i k ) \int \frac { d ^ { 2 } z } { 4 \pi ^ { 2 } \tau _ { 2 } } \left( T \delta \tau - \bar { T } \delta \tau + \mathrm { T r } \left[ ( a _ { z } - L _ { 1 } ) \delta ( - 2 i \tau _ { 2 } a _ { \bar { z } } ) \right] - \mathrm { T r } \left[ ( - \bar { a } _ { \bar { z } } + L _ { - 1 } ) \delta ( - 2 i \tau _ { 2 } a _ { \bar { z } } ) \right] \right) } } } \\ { { { \displaystyle ( 2 \pi i k ) \left( T \delta \tau - \bar { T } \delta \bar { \tau } + \sum _ { s = 3 } ^ { N } ( Q _ { s } \delta \mu _ { s } - \bar { Q } _ { s } \delta \bar { \mu } _ { s } ) \right) } } } \end{array}
$$

where we have restored the $A$ terms. We emphasize that equations (3.22) to (3.26) have already been given in [27] for the black hole case; here we have proved that they are valid for all solutions in the‘S $\operatorname { L } ( 2 , \mathbb { Z } ) ^ { \prime }$ family:

# 3.2 On-shell action, free energy, and entropy

For the black hole solution, the free energy and entropy were computed in [27,51]. In this subsection we follow their derivation and determine the entropy and free energy for all the solutions in the‘SL $( 2 , \mathbb { Z } ) ^ { \mathrm { : } }$ family, and more importantly, write them into modular covariant expressions.

As explained earlier, the variation of the action (bulk plus boundary) should take the same form for all solutions in the‘SL $( 2 , \mathbb { Z } )$ family, given by (3.26). However the on-shell value of the action depends on how we fill the solid torus therefore is different for different solutions in the ‘ ${ \mathrm { S L } } ( 2 , \mathbb { Z } ) ^ { \prime }$ family. [51] computed the on-shell action of a non-rotating black hole in this ${ \mathfrak { s l } } ( N )$ higher-spin theory. Now we generalize to a generic smooth constant solution labeled by （204号 $\gamma$ . The key point is to choose an appropriate foliation of the three-manifold $\mathcal { M }$ that is regular all the way to the center of $\mathcal { M }$ (i.e. the horizon),thereby avoiding a boundary term at the horizon. In the non-rotating black hole case, the contractible cycle is $t _ { E } \sim t _ { E } + 2 \pi$ , therefore [51] chose a slicing of the three-manifold $\mathcal { M }$ by disks with constant angular parameter $\phi$ ， andbtainedaosheui $\begin{array} { r } { I _ { \mathrm { b u l k } } ^ { \mathrm { ( E ) } } | _ { \mathrm { o n - s h e l l } } = - \frac { i k } { 4 \pi } \int _ { \partial \mathcal { M } } d t d \phi \mathrm { T r } \left[ a _ { t } a _ { \phi } \right] } \end{array}$ .

Now for the smooth constant solution labeled by $\gamma$ ， the contractible cycle is $z \sim z +$ （20 $2 \pi ( c \tau + d )$ . Go to the coordinate $( u ^ { \mathrm { A } } , u ^ { \mathrm { B } } )$ defined as

$$
u ^ { \mathrm { A } } \equiv \frac { i } { 2 \tau _ { 2 } } \left[ ( a \bar { \tau } + b ) z - ( a \tau + b ) \bar { z } \right] , \qquad u ^ { \mathrm { B } } \equiv \frac { i } { 2 \tau _ { 2 } } \left[ - ( c \bar { \tau } + d ) z + ( c \tau + d ) \bar { z } \right]
$$

We see as $z \mapsto z + 2 \pi ( c \tau + d )$

$$
u ^ { A } \longmapsto u ^ { A } + 2 \pi \qquad { \mathrm { a n d } } \qquad u ^ { B } \longmapsto u ^ { B } ~ ;
$$

i.e. $u ^ { \mathrm { B } }$ comes back to itself around the contractible cycle $z \sim z + 2 \pi ( c \tau + d )$ . Therefore we should foliate $\mathcal { M }$ with disks of constant $u ^ { \mathrm { B } }$ and such a foliation remains regular inside the bulk; thus we only need to compute the boundary term at the $\rho \to \infty$ ：

Expand the connection $( a , \bar { a } )$ in the coordinate $( u ^ { \mathrm { A } } , u ^ { \mathrm { B } } )$

$$
a = a _ { z } d z + a _ { \bar { z } } d \bar { z } = \omega _ { \mathrm { { A } } } d u ^ { \mathrm { { A } } } + \omega _ { \mathrm { { B } } } d u ^ { \mathrm { { B } } }
$$

where $\omega _ { \mathrm { A } } / \omega _ { \mathrm { B } }$ is precisely the holonomy matrix around the A/B cycle:

$$
\omega _ { \mathrm { A } } = ( c \tau + d ) a _ { z } + ( c \bar { \tau } + d ) a _ { \bar { z } } \ , \qquad \omega _ { \mathrm { B } } = ( a \tau + b ) a _ { z } + ( a \bar { \tau } + b ) a _ { \bar { z } } \ .
$$

Written in term of the coordinate $( u ^ { \mathrm { A } } , u ^ { \mathrm { B } } )$ ， the connection $A$ is then

$$
A = A _ { \rho } d \rho + [ b ^ { - 1 } \omega _ { \mathrm { A } } b ] d u ^ { \mathrm { A } } + [ b ^ { - 1 } \omega _ { \mathrm { B } } b ] d u ^ { \mathrm { B } } = A _ { \alpha } d x ^ { \alpha } + A _ { \mathrm { B } } d u ^ { \mathrm { B } } ,
$$

where $A _ { \alpha } d x ^ { \alpha } = A _ { \rho } d \rho + A _ { \mathrm { A } } d u ^ { \mathrm { A } }$ is the projection of $A$ onto the disk(with coordinate $x ^ { \alpha } =$ $\rho , u ^ { A } )$ ; and $b = b ( \rho )$ as defined earlier in (2.4) - not to be confused with the entry $b$ in the

matrix $\gamma$ . The bulk action is thus sliced into

$$
\stackrel { \mathrm { ( E ) } } { \mathrm { b u l k } } = \frac { i k } { 4 \pi } \int d u ^ { \mathrm { B } } \int d \rho d u ^ { \mathrm { A } } \mathrm { T r } \epsilon ^ { \alpha \beta } \left[ A _ { \mathrm { B } } F _ { \alpha \beta } - A _ { \alpha } \partial _ { \mathrm { B } } A _ { \beta } \right] - \frac { i k } { 4 \pi } \int _ { \rho \to \infty } d u ^ { \mathrm { A } } d u ^ { \mathrm { B } } \mathrm { T r } \left[ \omega _ { \mathrm { A } } \omega _ { \mathrm { B } } - \frac { \omega _ { \mathrm { B } } } { 2 } \right]
$$

with a bulk integral plus a boundary one.

Now let's compute the on-shell value of (3.32) for a smooth constant solution labeled by $\gamma$ . First,the bulk integral vanishes when taken on-shell, following from the bulk equation of motion $F = 0$ and the fact that the solution is constant (i.e. has no $( z , { \bar { z } } )$ -dependence). Second， in the boundary integral， since the integrand has no dependence on $( z , { \bar { z } } )$ ，the integration merely produces an overall volume of the boundary torus $\mathrm { v o l } ( \partial \mathcal { M } ) = 4 \pi ^ { 2 }$ 9. Therefore restoring the right-movers we conclude that the on-shell(Euclidean) bulk action for the solution $\gamma$ is

$$
I _ { \mathrm { b u l k } } ^ { \mathrm { ( E ) } } | _ { \mathrm { o n - s h e l l } } = - ( 2 \pi i k ) \frac { 1 } { 2 } \mathrm { T r } \left[ \omega _ { \mathrm { A } } \omega _ { \mathrm { B } } - \bar { \omega } _ { \mathrm { A } } \bar { \omega } _ { \mathrm { B } } \right] .
$$

Then as explained earlier, different solutions in the‘ $\operatorname { S L } ( 2 , \mathbb { Z } ) ^ { \prime }$ family share the same boundary term (3.24). The on-shell value of this boundary action is

$$
I _ { \mathrm { b n d y } } ^ { ( \mathrm { E } ) } | _ { \mathrm { o n - s h e l l } } = ( 2 \pi i k ) \frac { 1 } { 2 } \sum _ { s = 3 } ^ { N } ( s - 2 ) ( \mu _ { s } Q _ { s } - \bar { \mu } _ { s } \bar { Q } _ { s } ) .
$$

Combining (3.33) and (3.34) gives the total on-shel action and hence the free energy:

$$
\begin{array} { l } { { \displaystyle - \beta F = - ( I _ { \mathrm { b u l k } } ^ { \mathrm { ( E ) } } | _ { \mathrm { o n - s h e l l } } + I _ { \mathrm { b n d y } } ^ { \mathrm { ( E ) } } | _ { \mathrm { o n - s h e l l } } ) } } \\ { { \displaystyle ~ = ( 2 \pi i k ) \left( \frac { 1 } { 2 } \mathrm { T r } \left[ \omega _ { \mathrm { A } } \omega _ { \mathrm { B } } - { \bar { \omega } } _ { \mathrm { A } } { \bar { \omega } } _ { \mathrm { B } } \right] - \frac { 1 } { 2 } \sum _ { s = 3 } ^ { N } ( s - 2 ) ( \mu _ { s } Q _ { s } - { \bar { \mu } } _ { s } { \bar { Q } } _ { s } ) \right) . } } \end{array}
$$

Now let’s derive the entropy for generic members of the ‘SL $( 2 , \mathbb { Z } )$ family. The free-energy should take the form

$$
- \beta { \cal F } = { \cal S } + 2 \pi i k \left( T \tau - { \bar { T } } { \bar { \tau } } + \sum _ { s = 3 } ^ { N } ( \mu _ { s } Q _ { s } - { \bar { \mu } } _ { s } { \bar { Q } } _ { s } ) \right) .
$$

We first write down a useful identity

$$
\frac { 1 } { 2 } \operatorname { T r } \left[ \omega _ { \phi } \omega _ { t } - \bar { \omega } _ { \phi } \bar { \omega } _ { t } \right] = T \tau - \bar { T } \bar { \tau } + \frac { 1 } { 2 } \sum _ { s = 3 } ^ { N } s ( \mu _ { s } Q _ { s } - \bar { \mu } _ { s } \bar { Q } ) ,
$$

with $\omega _ { \phi }$ and $\omega _ { t }$ defined earlier in (2.22) and (2.29), respectively. (3.37) can be proven using $( T , T )$ 's definition (3.25) and the identity (3.23). Using (3.37) we obtain the entropy of a smooth constant solution labeled by $\gamma$

$$
S = ( 2 \pi i k ) \frac { 1 } { 2 } \left( \mathrm { T r } \left[ \omega _ { \mathrm { A } } \omega _ { \mathrm { B } } - { \bar { \omega } } _ { \mathrm { A } } { \bar { \omega } } _ { \mathrm { B } } \right] - \mathrm { T r } \left[ \omega _ { \phi } \omega _ { t } - { \bar { \omega } } _ { \phi } { \bar { \omega } } _ { t } \right] \right) \ .
$$

First,let us prove that the entropy defined by (3.38) is indeed a Legendre transform of the free energy (3.35). The method is the same as used in [27] to prove the corresponding statement for the black hole case. Since the holonomy around the contractible cycle is trivial, the eigenvalue of the holonomy matrix is given by integers hence is rigid, which means

$$
\delta \omega _ { \mathrm { A } } = [ \omega _ { \mathrm { A } } , \epsilon ] ,
$$

where $\epsilon$ is an infinitesimal matrix. This implies $\mathrm { T r } \left[ a _ { z } \ \delta \omega _ { \mathrm { A } } \right] = \mathrm { T r } \left[ a _ { \bar { z } } \ \delta \omega _ { \mathrm { A } } \right] = 0$ , following from （20 $[ a _ { z } , a _ { \bar { z } } ] = 0$ for constant solutions. Then using the above together with $\begin{array} { r } { \delta \omega _ { \mathrm { B } } = \frac { a } { c } \delta \omega _ { \mathrm { A } } - \frac { 1 } { c } \delta \omega _ { \phi } } \end{array}$ （20 we get the variation of the entropy (3.38) as:

$$
\delta S = - ( 2 \pi i k ) \operatorname { T r } \left[ \omega _ { t } \delta \omega _ { \phi } - \bar { \omega } _ { t } \delta \bar { \omega } _ { \phi } \right] .
$$

Translated back to the thermodynamical variables $\{ T , Q _ { s } ; \tau , \mu _ { s } \}$ ,it is

$$
\delta S = - ( 2 \pi i k ) \left( \tau ~ \delta T - \bar { \tau } ~ \delta \bar { T } + \sum _ { s = 3 } ^ { N } ( \mu _ { s } ~ \delta Q _ { s } - \bar { \mu } _ { s } ~ \delta \bar { Q } _ { s } ) \right) ~ ,
$$

which confirms that the entropy defined by (3.38) is indeed a Legendre transform of the free energy (3.35).

Finally let's check the modular covariant expression for the entropy in the two special cases,the conical surplus and the black hole. In these two cases, the holonomy matrices around A/B cycle (3.30) are

$$
\begin{array} { r l } { \mathrm { C S : } \quad } & { { } { \omega _ { \mathrm { A } } } = a _ { z } + a _ { \bar { z } } , } \\ { \mathrm { B H : } \quad } & { { } { \omega _ { \mathrm { A } } } = \tau a _ { z } + { \bar { \tau } } a _ { \bar { z } } , } \end{array} \qquad \begin{array} { r l } { \omega _ { \mathrm { B } } = \tau a _ { z } + { \bar { \tau } } a _ { \bar { z } } ; } \\ { \omega _ { \mathrm { B } } = - a _ { z } - a _ { \bar { z } } . } \end{array}
$$

Since

$$
\omega _ { \mathrm { A } } \omega _ { \mathrm { B } } = \left\{ { \omega _ { \phi } \omega _ { t } } \atop { - \omega _ { \phi } \omega _ { t } } \right.
$$

and similarly for $\omega _ { \mathrm { A } } \omega _ { \mathrm { B } }$ ，

$$
{ \cal S } = \left\{ \begin{array} { l } { { 0 } } \\ { { - ( 2 \pi i k ) \mathrm { T r } \left[ \omega _ { \phi } \omega _ { t } - { \bar { \omega } } _ { \phi } { \bar { \omega } } _ { t } \right] = - ( 2 \pi i k ) \left[ 2 ( T \tau - { \bar { T } } { \bar { \tau } } ) + \sum _ { s = 3 } ^ { N } s ( \mu _ { s } Q _ { s } - { \bar { \mu } } _ { s } { \bar { Q } } _ { s } ) + { \bar { \mu } } _ { s } { \bar { Q } } _ { s } { \bar { Q } } _ { s } \right] } } \end{array} \right.
$$

Therefore (3.38) indeed reproduces the known result for black hole in [27] and gives a reasonable answer for the conical surplus. The free energies for these two special cases are thus

$$
- \beta F = ( 2 \pi i k ) \cdot \left\{ \begin{array} { l } { { ( T \tau - \bar { T } \bar { \tau } ) + \sum _ { s = 3 } ^ { N } \left( \mu _ { s } Q _ { s } - \bar { \mu } _ { s } \bar { Q } _ { s } \right) } } \\ { { - ( T \tau - \bar { T } \bar { \tau } ) - \sum _ { s = 3 } ^ { N } \left( s - 1 \right) ( \mu _ { s } Q _ { s } - \bar { \mu } _ { s } \bar { Q } _ { s } ) } } \end{array} \right.
$$

# 4 Conical surplus and black hole are S-dual

In this section, we prove that any given conical surplus solution can be mapped into a black hole under an S-transformation of the modulus $\tau$ of the boundary torus. First, let's state precisely the full action of this S-transformation. The S-transformation is the special case of the modular transformation on the boundary torus $\tau \mapsto { \hat { \gamma } } \tau$ defined in (2.19):

$$
\mathrm { S } \colon \qquad \gamma = \binom { 0 } { 1 } \ - 1 ) : \qquad \tau \longmapsto \hat { \gamma } \tau = - \frac { 1 } { \tau } .
$$

Under this S-transformation, the A/B cycles of the conical surplus solution map to those of the black hole:

$$
{ \begin{array} { r l r l r l } { { \mathrm { A - c y c l e } } \colon } & { } & { z \sim z + 2 \pi } & & { \ \longmapsto \ } & { \ z \sim z + 2 \pi \tau } \\ { { \mathrm { B - c y c l e } } \colon } & { } & { z \sim z + 2 \pi \tau } & & { \ \longmapsto \ } & { \ z \sim z - 2 \pi } \end{array} }
$$

This would induce the corresponding transformations on the higher-spin charges $Q _ { s }$ and/or their chemical potentials $\mu _ { s }$ ：

Recall that in the grand canonical ensemble, once the chemical potentials $\{ \mu _ { s \geq 3 } \}$ of a conical surplus are given, the on-shell values of the charges $\{ Q _ { s \geq 2 } \}$ are solved in terms of $\mu _ { s }$ ， the boundary modulus $\tau$ ， and the holonomy vector $\vec { n }$ around its A-cycle (i.e. the $\phi$ -cycle):

$$
Q _ { t } ^ { \mathrm { C S } } = q _ { t } \left[ \vec { n } ; \ \tau ; \ \mu _ { s } \right] \qquad t = 2 , \ldots , N
$$

via the trivial holonomy condition around its A-cycle. In this section，we will first show that the S-transformation on the boundary modular parameter (4.1) maps the above conical surplus to a black hole with the same chemical potential $\mu _ { s }$ ，the same holonomy vector $\vec { n }$ （204号 but along the new A-cycle (i.e. the $z \sim z + 2 \pi \tau$ cycle),and with modular parameter $- { \frac { 1 } { \tau } }$ ： The on-shell values of the charges of this black hole are given by

$$
{ \cal Q } _ { t } ^ { \mathrm { B H } } = \frac { 1 } { \tau ^ { t } } q _ { t } \left[ \vec { n } ; { \bf \sigma } - \frac { 1 } { \tau } ; { \bf \sigma } \frac { \mu _ { s } } { \tau ^ { s } } \right] \qquad t = 2 , \ldots , N
$$

We emphasize that the function $q _ { t }$ in(4.3) and(4.4) is the same one.

Once (4.4) is proven,we will then show how the black hole and the conical surplus are related by a coordinate transformation (that changes the modular parameter of the boundary torus from $\tau$ to $- { \frac { 1 } { \tau } }$ ). We then prove that the free energy of the conical surplus and that of the black hole are mapped to each other via the S-transformation (4.1). Finally we illustrate with the example of the ${ \mathfrak { s l } } ( 3 )$ theory.

# 1.1 S-transformation of holonomy condition and on-shell charges

Since the defining difference between a conical surplus and a black hole is in the holonomy conditions around their respective A-cycles, we will derive the map from (4.3) to (4.4) using a map from the holonomy condition of the conical surplus (2.24) to that of the black hole (2.30).

First let us compare the two holonomy conditions in more details. First, from the equation of motion for constant solutions (2.13), $a _ { z }$ and $a _ { \bar { z } }$ of a constant on-shell configuration can be simultaneously diagonalized. Therefore, the vector of eigenvalues of the holonomy matrix （ $\omega _ { \phi }$ for the conical surplus and $\omega _ { t }$ for the black hole) has a decomposition in terms of vectors of eigenvalues of $a _ { z }$ and $a _ { \bar { z } }$ ：

$$
\begin{array} { r l } & { \mathrm { C S : } \qquad \Lambda \left( \omega _ { \phi } \right) = \Lambda \left( a _ { z } + a _ { \bar { z } } \right) = \Lambda \left( a _ { z } \right) + \Lambda \left( a _ { \bar { z } } \right) , } \\ & { \mathrm { B H : } \qquad \Lambda \left( \omega _ { t } \right) = \Lambda \left( \tau a _ { z } + \bar { \tau } a _ { \bar { z } } \right) = \tau \Lambda \left( a _ { z } \right) + \bar { \tau } \Lambda \left( a _ { \bar { z } } \right) ; } \end{array}
$$

since in computing e.g. $\Lambda \left( a _ { z } + a _ { \bar { z } } \right)$ by（2.23） we can choose $U$ to be a unitary matrix that diagonalizes both $a _ { z }$ and $a _ { \bar { z } }$ . Recall that $a _ { z }$ is the function of charges $\{ Q _ { s } \}$ only, as defined in (3.15); and $a _ { \bar { z } }$ is a function of $\{ \mu _ { s } , Q _ { s } \}$ and the modulus $\tau$ as defined via (2.14) and (3.19):10

$$
a _ { z } = a _ { z } [ Q _ { s } ] \ , \qquad a _ { \bar { z } } = a _ { \bar { z } } [ \tau ; \ \mu _ { s } ; \ Q _ { s } ] \ ,
$$

using which we can write the two holonomy conditions as

$$
\begin{array} { r l } & { \mathrm { C S : } \quad i \vec { n } = \Lambda \left( \omega _ { \phi } \left[ \tau ; \mu _ { s } ; Q _ { s } \right] \right) = \Lambda \left( a _ { z } \left[ Q _ { s } \right] \right) + \Lambda \left( a _ { \bar { z } } \left[ \tau ; \mu _ { s } ; Q _ { s } \right] \right) ; } \\ & { \mathrm { B H : } \quad i \vec { n } = \Lambda \left( \omega _ { t } \left[ \tau ; \mu _ { s } ; Q _ { s } \right] \right) = \tau \Lambda \left( a _ { z } \left[ Q _ { s } \right] \right) + \bar { \tau } \Lambda \left( a _ { \bar { z } } \left[ \tau ; \mu _ { s } ; Q _ { s } \right] \right) . } \end{array}
$$

To further compare the two, we now rewrite (4.8) into the form of (4.7). First,let's look at the $a _ { z }$ part. A crucial observation is that, in the highest-weight gauge, for any $\kappa \in \mathbb { C }$ ：

$$
\kappa \cdot \kappa ^ { L _ { 0 } } a _ { z } \left[ Q _ { s } \right] \kappa ^ { - L _ { 0 } } = a _ { z } \left[ \kappa ^ { s } Q _ { s } \right] .
$$

which follows from $a _ { z }$ 's definition in the highest-weight gauge (3.15) and the commutating relation $[ L _ { 0 } , W _ { - s + 1 } ^ { ( s ) } ] = ( s - 1 ) W _ { - s + 1 } ^ { ( s ) }$ .Relevnttotseee $\kappa = \tau$ in (4.9) and obtain

$$
\tau \cdot \tau ^ { L _ { 0 } } a _ { z } \left[ Q _ { s } \right] \tau ^ { - L _ { 0 } } = a _ { z } \left[ \tau ^ { s } Q _ { s } \right] .
$$

Taking the vectors of eigenvalues of both sides then immediately gives

$$
\tau \ \Lambda \left( a _ { z } \left[ Q _ { s } \right] \right) = \Lambda \left( a _ { z } \left[ \tau ^ { s } Q _ { s } \right] \right) .
$$

Then we look at the $a _ { \bar { z } }$ part. The identity (4.9) does not have an analogue for $a _ { \bar { z } }$ ，but the special case (4.10) with $\kappa = \tau$ does:

$$
\bar { \tau } \cdot \tau ^ { L _ { 0 } } a _ { \bar { z } } [ \tau ; \mu _ { s } ; Q _ { s } ] \tau ^ { - L _ { 0 } } = a _ { \bar { z } } \left[ - \frac { 1 } { \tau } ; \frac { \mu _ { s } } { \tau ^ { s } } ; \tau ^ { s } Q _ { s } \right] .
$$

Note that from l.h.s. to r.h.s. the variables of $a _ { \bar { z } }$ transform as:

$$
\tau \longmapsto - { \frac { 1 } { \tau } } , \qquad \mu _ { s } \longmapsto { \frac { \mu _ { s } } { \tau ^ { s } } } , \qquad Q _ { s } \longmapsto \tau ^ { s } Q _ { s } .
$$

The proof of (4.12) takes two steps.

1. Going back to (2.14) to rewrite $a _ { \bar { z } }$ in terms of only $\sigma _ { s }$ and $Q _ { s }$ (i.e. without the modulus), and then using (4.1O),we have

$$
\bar { \tau } \cdot \tau ^ { L _ { 0 } } a _ { \bar { z } } \left[ \sigma _ { s } ; Q _ { s } \right] \tau ^ { - L _ { 0 } } = \sum _ { s = 2 } ^ { N } \frac { | \tau | ^ { 2 } \sigma _ { s } } { \tau ^ { s } } \left[ ( a _ { z } \left[ \tau ^ { s } Q _ { s } \right] ) ^ { s - 1 } - \frac { \mathrm { T r } ( a _ { z } \left[ \tau ^ { s } Q _ { s } \right] ) ^ { s - 1 } } { N } \right] .
$$

2. Recall that the relations between $\{ \sigma _ { s \geq 2 } \}$ and $\{ \tau ; \mu _ { s \geq 3 } \}$ are given by the $( N - 1 )$ equa

tions in (3.19). This implies the following identity, which we will prove in Appendix A:

$$
\sigma _ { s } = \frac { i } { 2 \tau _ { 2 } } \sum _ { s ^ { \prime } = s } ^ { N } \mu _ { s ^ { \prime } } \ H _ { s ^ { \prime } - s } ( Q _ { t } ) ,
$$

where $H _ { s ^ { \prime } - s } ( Q _ { t } )$ is a homogenous polynomial (with rational coefficients） of degree$( s ^ { \prime } - s )$ ， with variables $Q _ { t }$ having degree- $t$ .Using that $\begin{array} { r } { \tau _ { 2 } \mapsto \frac { \tau _ { 2 } } { | \tau | ^ { 2 } } } \end{array}$ under $\tau \mapsto - { \frac { 1 } { \tau } }$ ，we see to get the transformation (4.13) of the variables in (4.12)，we need the following transformation of $( \sigma _ { s } , Q _ { s } )$

$$
\sigma _ { s } \longmapsto | \tau | ^ { 2 } { \frac { \sigma _ { s } } { \tau ^ { s } } } , \qquad Q _ { s } \longmapsto \tau ^ { s } Q _ { s } .
$$

Namely, the r.h.s. of (4.14) is preciely $a _ { \bar { z } } \ \lfloor - { \frac { 1 } { \tau } } ; \ { \frac { \mu _ { s } } { \tau ^ { s } } } ; \ \tau ^ { s } Q _ { s } \rfloor$ , which proves (4.12).

Computing the vectors of eigenvalues of both sides then gives the analogue of (4.11):

$$
\bar { \tau } \ \Lambda \left( a _ { \bar { z } } \left[ \tau ; \ \mu _ { s } ; \ Q _ { s } \right] \right) = \Lambda \left( a _ { \bar { z } } \left[ - \frac { 1 } { \tau } ; \ \frac { \mu _ { s } } { \tau ^ { s } } ; \ \tau ^ { s } Q _ { s } \right] \right) .
$$

Having proved (4.11) and (4.17), we can now plug them into the holonomy condition for the black hole (4.8) and recast it into the form of conical surplus’ holonomy condition (4.7） but with transformed variables:

$$
i \vec { n } = \Lambda \left( \omega _ { t } \left[ \tau ; \mu _ { s } ; Q _ { s } \right] \right) = \Lambda \left( \omega _ { \phi } \left[ - \frac { 1 } { \tau } ; \frac { \mu _ { s } } { \tau ^ { s } } ; \tau ^ { s } Q _ { s } \right] \right) .
$$

Equivalently, if we take the holonomy condition of the conical surplus (4.7) and apply on it a change of variables defined in (4.13),we arrive at the holonomy condition of the black hole (4.8).

In the proof above, we have adopted the passive viewpoint of transformation and shown that the conical surplus and black hole are mapped to each other via a passve change of variables (4.13). Now we need to translate this into the active viewpoint. To compare the two solutions, we place them into a common grand canonical ensemble: with common temperature and chemical potentials, and ask how their conserved charges are mapped into each other.

In the grand canonical ensemble,once the chemical potentials $\{ \mu _ { s \geq 3 } \}$ are given， the charges $\{ Q _ { s } \}$ are fixed by the holonomy condition around the A-cycle to be a function of $\{ \vec { n } ; \ \tau ; \ \mu _ { s } \}$ . The relation (4.18） between the holonomy condition of the conical surplus and the black hope then implies the following relation between their charge functions:11

$$
\partial _ { t } ^ { \mathrm { C S } } = q _ { t } \left[ \vec { n } ; \tau ; \mu _ { s } \right] \qquad \Longleftrightarrow \qquad Q _ { t } ^ { \mathrm { B H } } = \frac { 1 } { \tau ^ { t } } q _ { t } \left[ \vec { n } ; - \frac { 1 } { \tau } ; \frac { \mu _ { s } } { \tau ^ { s } } \right] \qquad t = 2 , \dots , N .
$$

The function $q [ \vec { n } ; \tau ; \mu _ { s } ]$ should be considered as defined using the charge function of the conical surplus solution.

# 4.2 Coordinate transformation between conical surplus and black hole

From the mapping (4.18) (or equivalently (4.19)） together with (4.10) and (4.12)，we see that the gauge field components $( a _ { z } , a _ { \bar { z } } )$ of a conical surplus and those of its S-dual black hole are related via:

$$
\begin{array} { l } { { a _ { z } ^ { \mathrm { C S } } \left[ \vec { n } ; - \displaystyle \frac { 1 } { \tau } ; \frac { \mu _ { s } } { \tau ^ { s } } \right] = \tau \cdot \tau ^ { L _ { 0 } } a _ { z } ^ { \mathrm { B H } } \left[ \vec { n } ; \tau ; \mu _ { s } \right] \tau ^ { - L _ { 0 } } , } } \\ { { a _ { \bar { z } } ^ { \mathrm { C S } } \left[ \vec { n } ; - \displaystyle \frac { 1 } { \tau } ; \frac { \mu _ { s } } { \tau ^ { s } } \right] = \bar { \tau } \cdot \tau ^ { L _ { 0 } } a _ { \bar { z } } ^ { \mathrm { B H } } \left[ \vec { n } ; \tau ; \mu _ { s } \right] \tau ^ { - L _ { 0 } } . } } \end{array}
$$

To further compare the two,let us rescale the coordinate of the conical surplus. Changing the coordinate while fixing the gauge components $( a _ { z } , a _ { \bar { z } } )$ gives a different gauge one-form. Under the rescaling of the coordinate $( z , { \bar { z } } )$

$$
z \longmapsto z ^ { \prime } = { \frac { z } { \tau } } \qquad { \bar { z } } \longmapsto { \bar { z } } ^ { \prime } = { \frac { \bar { z } } { \bar { \tau } } } ,
$$

the gauge one-form $a$ transforms as

$$
a ^ { ( z , \bar { z } ) } \equiv a _ { z } d z + a _ { \bar { z } } d \bar { z } \qquad \longmapsto \qquad a ^ { ( z ^ { \prime } , \bar { z } ^ { \prime } ) } \equiv a _ { z } d z ^ { \prime } + a _ { \bar { z } } d \bar { z } ^ { \prime } .
$$

The one-form $a$ of the conical surplus in the new coordinate $( z ^ { \prime } , \bar { z } ^ { \prime } )$ is then related to that of the black hole in the original coordinate $( z , { \bar { z } } )$ only by a similarity transformation:

$$
a ^ { \mathrm { { C S } } } \left[ \vec { n } ; - \frac { 1 } { \tau } ; \ \frac { \mu _ { s } } { \tau ^ { s } } \right] ^ { ( z ^ { \prime } , \bar { z } ^ { \prime } ) } = \tau ^ { L _ { 0 } } a ^ { \mathrm { { B H } } } \left[ \vec { n } ; \ \tau ; \ \mu _ { s } \right] ^ { ( z , \bar { z } ) } \tau ^ { - L _ { 0 } } .
$$

Similarly for the right mover:

$$
\bar { a } ^ { \mathrm { C S } } \left[ \vec { n } ; - { \frac { 1 } { \tau } } ; { \frac { \mu _ { s } } { \tau ^ { s } } } \right] ^ { ( z ^ { \prime } , \bar { z } ^ { \prime } ) } = \bar { \tau } ^ { - L _ { 0 } } a ^ { \mathrm { B H } } \left[ \vec { n } ; \tau ; \mu _ { s } \right] ^ { ( z , \bar { z } ) } \bar { \tau } ^ { L _ { 0 } } .
$$

Going back to the gauge connection $( A , A )$ ，related to $( a , \bar { a } )$ via (2.4)，we see that the similarity transformation in (4.23) and (4.24) can be reabsorbed by a simultaneous shifting of the radial coordinate $\rho$ accompanying the rescaling of $( z , { \bar { z } } )$ ：

$$
\rho \longmapsto \rho ^ { \prime } = \rho + \ln | \tau | , \qquad z \longmapsto z ^ { \prime } = { \frac { z } { \tau } } , \qquad { \bar { z } } \longmapsto { \bar { z } } ^ { \prime } = { \frac { \bar { z } } { \bar { \tau } } } .
$$

Namely, in terms of

$$
{ \bf \Pi } _ { \rho , z , \bar { z } } ^ { \prime } \equiv e ^ { - \rho L _ { 0 } } a ^ { ( z , \bar { z } ) } e ^ { \rho L _ { 0 } } + L _ { 0 } d \rho \qquad \mathrm { a n d } \qquad A ^ { ( \rho ^ { \prime } , z ^ { \prime } , \bar { z } ^ { \prime } ) } \equiv e ^ { - \rho ^ { \prime } L _ { 0 } } a ^ { ( z ^ { \prime } , \bar { z } ^ { \prime } ) } e ^ { \rho ^ { \prime } L _ { 0 } } + L _ { 0 } d \rho ^ { \prime }
$$

(and similarly for $A$ ） the full gauge one-form $( A , A )$ of the black hole with parameter $\{ \vec { n } ; ~ \tau ; ~ \mu _ { s } \}$ in the original coordinate $( \rho , z , \bar { z } )$ is identical to that of the conical surplus with parameter $\{ \vec { n } ; - \textstyle { \frac { 1 } { \tau } } ; \frac { \mu _ { s } } { \tau ^ { s } } \}$ in the new coordinate $( \rho ^ { \prime } , z ^ { \prime } , \bar { z } ^ { \prime } )$ up to an overall constant gauge transformation:

$$
\begin{array} { l } { { \hat { h } ^ { - 1 } \cdot A ^ { \mathrm { C S } } \left[ \vec { n } ; - \displaystyle \frac { 1 } { \tau } ; \displaystyle \frac { \mu _ { s } } { \tau ^ { s } } \right] ^ { ( \rho ^ { \prime } , z ^ { \prime } , \bar { z } ^ { \prime } ) } \cdot \hat { h } = A ^ { \mathrm { B H } } \left[ \vec { n } ; \tau ; \mu _ { s } \right] ^ { ( \rho , z , \bar { z } ) } \ , } } \\ { { \hat { h } ^ { - 1 } \cdot \bar { A } ^ { \mathrm { C S } } \left[ \vec { n } ; - \displaystyle \frac { 1 } { \tau } ; \displaystyle \frac { \mu _ { s } } { \tau ^ { s } } \right] ^ { ( \rho ^ { \prime } , z ^ { \prime } , \bar { z } ^ { \prime } ) } \cdot \hat { h } = \bar { A } ^ { \mathrm { B H } } \left[ \vec { n } ; \tau ; \mu _ { s } \right] ^ { ( \rho , z , \bar { z } ) } \ , } } \end{array}
$$

with $\begin{array} { r } { \hat { h } = \left( \frac { \bar { \tau } } { \tau } \right) ^ { \frac { L _ { 0 } } { 2 } } = e ^ { - i \arg ( \tau ) L _ { 0 } } } \end{array}$ . This means that the conical surplus and the black hole difer only in the global structure.This is the analogue of the spin-2 story: in the spin-2 case, the BTZ black hole can be mapped by a coordinate transformation into a thermal $\mathrm { A d S _ { 3 } }$ with modular parameter $- { \frac { 1 } { \tau } }$ (instead of $\tau$ ). They are both discrete quotients of the AdS $_ 3$ ; thermal AdS $_ 3$ with parameter $\tau$ whereas BTZ with parameter $- { \frac { 1 } { \tau } }$ [5,6].

# 4.3 S-transformation of free energies

We have just proved that the S-transformation $\tau \mapsto - { \frac { 1 } { \tau } }$ maps a conical surplus with parameter $\{ \vec { n } ; \tau ; \mu _ { s } \}$ (holonomy vector around A-cycle, boundary modulus, chemical potentials) into a black hole with the same set of parameters $\{ \vec { n } ; \tau ; \mu _ { s } \}$ , and that the on-shell value of charges $Q _ { s }$ is mapped via (4.19).

Now, between this S-dual pair of a conical surplus and a black hole, if we know the free energy of the conical surplus,as a function of parameters $\{ \vec { n } ; \tau ; \mu _ { s } \}$

$$
\boldsymbol { F } ^ { \mathrm { C S } } = \mathcal { F } \left[ \vec { n } ; ~ \tau ; ~ \mu _ { s } \right] ,
$$

what can we say about the free energy of the black hole? In other words,how does the free energy of the conical surplus change under the S-transformation?

To answer this question, we first need to compare the free energies of the two solutions. We have written down a few expressions of the free energy in Section 3.2. For instance the free energies in (3.45) were written in terms of thermodynamics variables $\{ T , Q _ { s } ; \tau , \mu _ { s } \}$ However, the most important condition in defining an S-dual pair is that the two share the same holonomy vector $\vec { n }$ , around their respective A-cycles. Therefore we should instead start with the general expression (3.35),and then use (3.43) to restrict to the conical surplus or the black hole, then finally rewrite the expression in terms of $\{ \vec { n } ; \ \tau ; \ \mu _ { s } ; \ Q _ { s } \}$ . We now do this separately for the conical surplus and the black hole.

# 4.3.1 Conical surplus

Now let us first rewrite the free energy of the conical surplus in terms of $\{ \vec { n } ; \tau ; \mu _ { s } ; Q _ { s } \}$ .The general expresson for the free energy (3.35） plus (3.43) give the free energy of the conical surplus to be:

$$
- \beta F ^ { \mathrm { C S } } = ( 2 \pi i k ) \left( \frac 1 2 \mathrm { T r } \left[ \omega _ { \phi } \omega _ { t } - { \bar { \omega } } _ { \phi } { \bar { \omega } } _ { t } \right] - \frac 1 2 \sum _ { s = 3 } ^ { N } ( s - 2 ) ( \mu _ { s } Q _ { s } - { \bar { \mu } } _ { s } { \bar { Q } } _ { s } ) \right) ,
$$

with $\omega _ { \phi }$ and $\omega _ { t }$ defined in (2.22) and (2.29),respectively

First,using

$$
Q _ { 2 } = { \frac { 1 } { 2 } } \mathrm { T r } \left[ ( a _ { z } ) ^ { 2 } \right] \qquad \mathrm { a n d } \qquad \mathrm { T r } \left[ a _ { z } a _ { \bar { z } } \right] = { \frac { i } { 2 \tau _ { 2 } } } \sum _ { s = 3 } ^ { N } s \mu _ { s } Q _ { s } ,
$$

we have

$$
\frac { 1 } { 2 } \operatorname { T r } \left[ \omega _ { \phi } \omega _ { t } \right] = \tau Q _ { 2 } + \tau _ { 1 } \frac { i } { 2 \tau _ { 2 } } \sum _ { s = 3 } ^ { N } s \mu _ { s } Q _ { s } + \bar { \tau } \frac { \operatorname { T r } \left[ ( a _ { \bar { z } } ) ^ { 2 } \right] } { 2 } ,
$$

where $\tau _ { 1 } \equiv \mathrm { R e } \tau$ . The last term in (4.31) is not immediately defined in terms of the parameters $\{ \vec { n } ; \tau ; \mu _ { s } ; Q _ { s } \}$ . However，recall that for the conical surplus,the holonomy matrix $\omega _ { \phi }$ ，with （204号 $\Lambda \left( \omega _ { \phi } \right) = i \vec { n }$ labeling different solutions, contains a $\operatorname { T r } { [ ( a _ { \bar { z } } ) ^ { 2 } ] }$ term:

$$
- \frac { 1 } { 2 } \vec { n } ^ { 2 } = \frac { 1 } { 2 } \mathrm { T r } \left[ ( \omega _ { \phi } ) ^ { 2 } \right] = ~ Q _ { 2 } + \frac { i } { 2 \tau _ { 2 } } \sum _ { s = 3 } ^ { N } s \mu _ { s } Q _ { s } + \frac { \mathrm { T r } \left[ ( a _ { \bar { z } } ) ^ { 2 } \right] } { 2 } .
$$

Therefore(4.31) and (4.32） together give an identity

$$
\frac { 1 } { 2 } \operatorname { T r } \left[ \omega _ { \phi } \omega _ { t } \right] ^ { \mathrm { C S } } = - \frac { \vec { n } ^ { 2 } } { 2 } \bar { \tau } + 2 i \tau _ { 2 } Q _ { 2 } - \frac { 1 } { 2 } \sum _ { s = 3 } ^ { N } s \mu _ { s } Q _ { s } ,
$$

using which (and its right mover counterpart） we can rewrite the free energy (4.29) of the CS solution in terms of $\{ \vec { n } ; \ \tau ; \ \mu _ { s } ; \ Q _ { s } \}$

$$
- \beta F ^ { \mathrm { C S } } = 2 \pi i k \left[ 2 i \tau _ { 2 } ( \frac { \vec { n } ^ { 2 } } { 2 } + Q _ { 2 } + \bar { Q } _ { 2 } ) - \sum _ { s = 3 } ^ { N } ( s - 1 ) ( \mu _ { s } Q _ { s } - \bar { \mu } _ { s } \bar { Q } _ { s } ) \right] .
$$

The set of parameters $\{ \vec { n } ; \ \tau ; \ \mu _ { s } ; \ Q _ { s } \}$ transform covariantly under modular transformation. However, this is not yet the last step. Since the free energy is in the grand canonical ensemble, we should consider its variables to be $\{ \vec { n } ; \ \tau ; \ \mu _ { s } \}$ ， and replace $Q _ { s }$ by its function of them. Plugging the charge function for the conical surplus (4.3) into (4.34), we get the final answer for its free energy

$$
\begin{array} { l } { { \displaystyle - \beta F ^ { \mathrm { C S } } = 2 \pi i k \Big [ ~ 2 i \tau _ { 2 } \left( \frac { \vec { n } ^ { 2 } } { 2 } + q _ { 2 } [ \vec { n } ; ~ \tau ; ~ \mu _ { s } ] + \bar { q } _ { 2 } [ \vec { n } ; ~ \tau ; ~ \mu _ { s } ] \right) } } \\ { { { } } } \\ { { \displaystyle ~ - \sum _ { s = 3 } ^ { N } ( s - 1 ) \left( \mu _ { s } q _ { s } [ \vec { n } ; ~ \tau ; ~ \mu _ { s } ] - \bar { \mu } _ { s } \bar { q } _ { s } [ \vec { n } ; ~ \tau ; ~ \mu _ { s } ] \right) \Big ] \equiv - \beta \mathcal { F } [ \vec { n } ; ~ \tau ; ~ \mu _ { s } ] . } } \end{array}
$$

In the last line we have used this result of the free energy of the conical surplus to define a‘free energy function’ $\mathcal { F } [ \vec { n } ; ~ \tau ; ~ \mu _ { s } ]$ ， which will be used later to relate to the free energy of other solutions in the‘ ${ \mathrm { S L } } ( 2 , \mathbb { Z } ) ^ { \prime }$ family.

# 4.3.2 Black hole

The black hole case is completely parallel. Applying (3.43) to the general expresson (3.35) gives the free energy of the black hole:

$$
- \beta F ^ { \mathrm { B H } } = ( 2 \pi i k ) \left( - \frac 1 2 \mathrm { T r } \left[ \omega _ { \phi } \omega _ { t } - { \bar { \omega } } _ { \phi } { \bar { \omega } } _ { t } \right] - \frac 1 2 \sum _ { s = 3 } ^ { N } ( s - 2 ) ( \mu _ { s } Q _ { s } - { \bar { \mu } } _ { s } { \bar { Q } } _ { s } ) \right) .
$$

The first term involving $\begin{array} { r } { \frac { 1 } { 2 } \operatorname { T r } \left[ \omega _ { \phi } \omega _ { t } - \bar { \omega } _ { \phi } \bar { \omega } _ { t } \right] } \end{array}$ can still be rewritten using (4.31). But since the topological charge $\vec { n }$ is given by the holonomy along the $t$ -cycle instead of the $\phi$ -cycle, (4.32) should now be replaced by

$$
- { \frac { 1 } { 2 } } \vec { n } ^ { 2 } = { \frac { 1 } { 2 } } \mathrm { T r } \left[ ( \omega _ { t } ) ^ { 2 } \right] = \tau ^ { 2 } Q _ { 2 } + { \frac { i | \tau | ^ { 2 } } { 2 \tau _ { 2 } } } \sum _ { s = 3 } ^ { N } s \mu _ { s } Q _ { s } + \bar { \tau } ^ { 2 } { \frac { \mathrm { T r } \left[ ( a _ { \bar { z } } ) ^ { 2 } \right] } { 2 } } ,
$$

which gives rise to the identity (the counterpart of (4.33))

$$
\frac { 1 } { 2 } \mathrm { T r } \left[ \omega _ { \phi } \omega _ { t } \right] ^ { \mathrm { B H } } = - \left( \frac { \vec { n } ^ { 2 } } { 2 } \frac { 1 } { \bar { \tau } } + \frac { 2 i \tau _ { 2 } } { | \tau | ^ { 2 } } \tau ^ { 2 } Q _ { 2 } - \frac { 1 } { 2 } \sum _ { s = 3 } ^ { N } s \mu _ { s } Q _ { s } \right) .
$$

Using this the free energy of the black hole can be written in terms of modular covariant quantities $\{ \vec { n } ; \ \tau ; \ \mu _ { s } ; \ Q _ { s } \}$ as

$$
- \beta { \cal F } ^ { \mathrm { B H } } = 2 \pi i k \left[ \frac { 2 i \tau _ { 2 } } { | \tau | ^ { 2 } } ( \frac { { \vec { n } } ^ { 2 } } { 2 } + \tau ^ { 2 } Q _ { 2 } + { \bar { \tau } } ^ { 2 } { \bar { Q } } _ { 2 } ) - \sum _ { s = 3 } ^ { N } ( s - 1 ) ( \mu _ { s } Q _ { s } - { \bar { \mu } } _ { s } { \bar { Q } } _ { s } ) \right] .
$$

Similar to the conical surplus, we should now replace $Q _ { s }$ by the charge functions of the black hole, given in (4.4),and thereby obtain the free energy of the black hole as a function of （204号 $\{ \vec { n } ; \ \tau ; \ \mu _ { s } \}$

$$
\begin{array} { l } { { \displaystyle - \beta F ^ { \mathrm { B H } } = 2 \pi i k \Big [ \frac { 2 i \tau _ { 2 } } { | \tau | ^ { 2 } } \left( \frac { { \vec { n } } ^ { 2 } } { 2 } + q _ { 2 } \left[ { \vec { n } } ; ~ - \frac { 1 } { \tau } ; ~ \frac { \mu _ { s } } { \tau ^ { s } } \right] + { \bar { q } } _ { 2 } \left[ { \vec { n } } ; ~ - \frac { 1 } { \bar { \tau } } ; ~ \frac { { \bar { \mu } } _ { s } } { { \bar { \tau } } ^ { s } } \right] \right) } } \\ { { \displaystyle ~ - \sum _ { s = 3 } ^ { N } ( s - 1 ) \left( \frac { \mu _ { s } } { \tau ^ { s } } q _ { s } \left[ { \vec { n } } ; ~ - \frac { 1 } { \tau } ; ~ \frac { \mu _ { s } } { \tau ^ { s } } \right] - \frac { { \bar { \mu } } _ { s } } { \bar { \tau } ^ { s } } { \bar { q } } _ { s } \left[ { \vec { n } } ; ~ - \frac { 1 } { \bar { \tau } } ; ~ \frac { { \bar { \mu } } _ { s } } { \bar { \tau } ^ { s } } \right] \right) \Big ] . } } \end{array}
$$

# 4.3.3 S-transformation of free energies

Now we have the free energy of the conical surplus (4.35) and that of the black hole (4.40), each written explicitly in terms of $\{ \vec { n } ; \ \tau ; \ \mu _ { s } \}$ . Comparing (4.35） with (4.40)，we conclude that the S-transformation between the free energy of the conical surplus and that of the black hole is the following

$$
{ \cal F } ^ { \mathrm { C S } } = { \mathcal F } \left[ \vec { n } ; \tau ; \mu _ { s } \right] \qquad \Longleftrightarrow \qquad { \cal F } ^ { \mathrm { B H } } = { \mathcal F } \left[ \vec { n } ; - \frac { 1 } { \tau } ; \frac { \mu _ { s } } { \tau ^ { s } } \right] .
$$

Similar to the charge function (4.19),we can consider the function $\mathcal { F } \left[ \vec { n } ; ~ \tau ; ~ \mu _ { s } \right]$ to be defined by the free energy of the conical surplus. The relations (4.19) and (4.41) show that the full S-transformation in the grand canonical ensemble (GCE) is:

$$
\mathrm { S - m a p ~ i n ~ G C E : } \qquad \tau \longmapsto - \frac { 1 } { \tau } , \qquad \mu _ { s } \longmapsto \frac { \mu _ { s } } { \tau ^ { s } } .
$$

# 4.4 Example-1: $N = 3$ case

Now let us illustrate what we have proven so far with the simplest example: ${ \mathfrak { s l } } ( 3 )$ higher-spin theory.

First, to write down $a _ { z }$ from (3.15) we need to specify a specific representation of $\boldsymbol { L } _ { 0 , \pm 1 }$ We wil adopt the one used in [20], namely

$$
\begin{array} { l } { { ( L _ { 0 } ) _ { m n } = \displaystyle \frac { N + 1 - 2 m } { 2 } \delta _ { m , n } \ : , } } \\ { { ( L _ { 1 } ) _ { m n } = \displaystyle - \sqrt { | ( m - 1 ) ( N + 1 - m ) | } \delta _ { m , n + 1 } \ : , } } \\ { { ( L _ { - 1 } ) _ { m n } = \displaystyle + \sqrt { | ( n - 1 ) ( N + 1 - n ) | } \delta _ { m + 1 , n } \ : . } } \end{array}
$$

Once $\boldsymbol { L } _ { 0 , \pm 1 }$ arechosen,wecan use (2.10)to write down althe $W _ { m } ^ { ( s \geq 3 ) }$ . In this representation, （20 $a _ { z }$ is

$$
a _ { z } = L _ { 1 } - \frac { Q _ { 2 } } { 4 } L _ { - 1 } + \frac { Q _ { 3 } } { 4 } W _ { - 2 } ^ { ( 3 ) } .
$$

Then take (2.14) and solve $\left\{ \sigma _ { 2 } , \sigma _ { 3 } \right\}$ using (3.19) we get

$$
\sigma _ { 2 } = 0 , \sigma _ { 3 } = \frac { i } { 2 \tau _ { 2 } } \mu _ { 3 } .
$$

So $a _ { \bar { z } }$ is simply

$$
a _ { \bar { z } } = \frac { i } { 2 \tau _ { 2 } } \mu _ { 3 } \left( ( a _ { z } ) ^ { 2 } - \frac { \mathrm { T r } \left[ ( a _ { z } ) ^ { 2 } \right] } { 3 } { \bf 1 } \right) .
$$

Note that for $N \geq 4$ ， $\sigma _ { s }$ is no longer simply $\begin{array} { r } { \frac { i } { 2 \tau _ { 2 } } \mu _ { s } } \end{array}$ but in general involves a non-trivial (i.e. $\neq 1$ ）homogenous polynomial of $Q _ { s }$ as given by (4.15). We remind that the expressions of $a _ { z }$ and $a _ { \bar { z } }$ as given in (4.44) and (4.46) are valid for all members of the ‘ ${ \mathrm { S L } } ( 2 , \mathbb { Z } ) ^ { \prime }$ family. However the charges $Q _ { s }$ are determined in terms of the chemical potentials via the holonomy condition (2.34),which is different for different solutions (labeled by $\gamma$ ）

First let's look at the conical surplus. The holonomy condition along the $\phi$ -cycle ((2.24) and (2.22)） is equivalent to the following two equations

$$
\operatorname { T r } \left[ ( a _ { z } + a _ { \bar { z } } ) ^ { 2 } \right] = - 2 n ^ { 2 } , \qquad \operatorname { T r } \left[ ( a _ { z } + a _ { \bar { z } } ) ^ { 3 } \right] = 0 , \qquad \mathrm { w i t h } \ n \in \mathbb { Z }
$$

where we have used $\vec { n } = ( n , 0 , - n )$ .12 Now let us use (4.47) to solve $\{ Q _ { 2 } , Q _ { 3 } \}$ in terms of $\tau$ and $\mu _ { 3 }$ . (4.47) is a pair of coupled algebraic equations, one quadratic and one cubic; therefore $\{ Q _ { 2 } , Q _ { 3 } \}$ has an algebraic expression in terms of $\{ \tau , \mu _ { 3 } \}$ . However they are rather long and not very illuminating so we instead provide (the first few terms of) their power expansion in terms of $\mu _ { 3 }$ ， which is enough to show the S-map between this conical surplus solution and

the black hole:

$$
\begin{array} { l } { { Q _ { 2 } ^ { \mathrm { C S } } = - n ^ { 2 } \left[ 1 - \displaystyle \frac { 5 } { 3 } \alpha ^ { 2 } + \displaystyle \frac { 1 0 } { 3 } \alpha ^ { 4 } - \displaystyle \frac { 2 2 1 } { 2 7 } \alpha ^ { 6 } + \displaystyle \frac { 1 8 0 2 } { 8 1 } \alpha ^ { 8 } + \cdot \cdot \cdot \right] \equiv q _ { 2 } [ { \vec { n } } ; \tau ; \mu _ { s } ] , } } \\ { { Q _ { 3 } ^ { \mathrm { C S } } = - n ^ { 3 } \left[ \displaystyle \frac { 2 } { 3 } \alpha - \displaystyle \frac { 4 0 } { 2 7 } \alpha ^ { 3 } + \displaystyle \frac { 3 4 } { 9 } \alpha ^ { 5 } - \displaystyle \frac { 8 4 8 } { 8 1 } \alpha ^ { 7 } + \cdot \cdot \cdot \right] \equiv q _ { 3 } [ { \vec { n } } ; \tau ; \mu _ { s } ] . } } \end{array}
$$

with

$$
\alpha \equiv n \frac { i } { 2 \tau _ { 2 } } \mu _ { 3 }
$$

In the last step we defined the function $q _ { s }$ using the charge function of the conical surplus. We could then plug the exact solution into (4.34) to write down the exact free energy. However, since the expression is too long and not very illuminating,we again content ourselves with an expansion:

$$
^ { \mathrm { c S } } = 4 \pi k \cdot n ^ { 2 } \tau _ { 2 } \cdot \bigg [ 1 - \frac { 1 } { 3 } ( \alpha ^ { 2 } + \bar { \alpha } ^ { 2 } ) + \frac { 1 0 } { 2 7 } ( \alpha ^ { 4 } + \bar { \alpha } ^ { 4 } ) - \frac { 1 7 } { 2 7 } ( \alpha ^ { 6 } + \bar { \alpha } ^ { 6 } ) + \frac { 1 0 6 } { 8 1 } ( \alpha ^ { 8 } + \bar { \alpha } ^ { 8 } ) + \frac { 1 1 } { 1 6 } \alpha ^ { 4 } \alpha ^ { 5 } \bigg ]
$$

Now we turn to the black hole. The condition that solves $\{ Q _ { 2 } , Q _ { 3 } \}$ is now the holonomy condition around the cycle $z \sim z + 2 \pi \tau$ ：

$$
\mathrm { T r } \left[ ( \tau a _ { z } + \bar { \tau } a _ { \bar { z } } ) ^ { 2 } \right] = - 2 n ^ { 2 } , \qquad \mathrm { T r } \left[ ( \tau a _ { z } + \bar { \tau } a _ { \bar { z } } ) ^ { 3 } \right] = 0 , \qquad \mathrm { w i t h } \qquad n \in \mathbb { Z } .
$$

The case with $n = 1$ gives the higher-spin black hole first constructed in [21]. Now we write down the solution $\{ Q _ { 2 } , Q _ { 3 } \}$ for generic $n$ , in a power expansion of $\mu _ { 3 }$

$$
\begin{array} { l } { { \displaystyle Q _ { 2 } ^ { \mathrm { B H } } = - \frac { n ^ { 2 } } { \tau ^ { 2 } } \left[ 1 - \frac { 5 } { 3 } \beta ^ { 2 } + \frac { 1 0 } { 3 } \beta ^ { 4 } - \frac { 2 2 1 } { 2 7 } \beta ^ { 6 } + \frac { 1 8 0 2 } { 8 1 } \beta ^ { 8 } + \cdot \cdot \cdot \right] \ : , } } \\ { { \displaystyle Q _ { 3 } ^ { \mathrm { B H } } = - \frac { n ^ { 3 } } { \tau ^ { 3 } } \left[ \frac { 2 } { 3 } \beta - \frac { 4 0 } { 2 7 } \beta ^ { 3 } + \frac { 3 4 } { 9 } \beta ^ { 5 } - \frac { 8 4 8 } { 8 1 } \beta ^ { 7 } + \cdot \cdot \cdot \right] \ : . } } \end{array}
$$

with

$$
\beta \equiv n \frac { i | \tau | ^ { 2 } } { 2 \tau _ { 2 } } \frac { \mu _ { 3 } } { \tau ^ { 3 } } .
$$

Comparing (4.48) and (4.52) together with (4.49) and (4.53) thus immediately shows $Q _ { s } ^ { \mathrm { B H } } =$ （20 ${ \begin{array} { l } { { \frac { 1 } { \tau ^ { s } } } q _ { s } \left[ { \vec { n } } ; \ - { \frac { 1 } { \tau } } ; \ { \frac { \mu _ { s } } { \tau ^ { s } } } \right] } \end{array} }$ hence confirms the relation (4.19) that we have proven earlier.Finally we compute the free energy of the black hole and write down its power expansion here

$$
^ { \mathrm { \tiny ~ B H } } = 4 \pi k \cdot n ^ { 2 } \frac { \tau _ { 2 } } { | \tau | ^ { 2 } } \cdot \left[ 1 - \frac { 1 } { 3 } ( \beta ^ { 2 } + \bar { \beta } ^ { 2 } ) + \frac { 1 0 } { 2 7 } ( \beta ^ { 4 } + \bar { \beta } ^ { 4 } ) - \frac { 1 7 } { 2 7 } ( \beta ^ { 6 } + \bar { \beta } ^ { 6 } ) + \frac { 1 0 6 } { 8 1 } ( \beta ^ { 8 } + \bar { \beta } ^ { 4 } ) \right] ,
$$

This is exactly the S-transformation (4.42) of (4.50).

# 5 SL $( 2 , \mathbb { Z } )$ family of smooth solutions

In this section we will show how to generate an “ $\operatorname { S L } ( 2 , \mathbb { Z } )$ family” of smooth solutions with higher-spin charges. The construction is a generalization of the spin-2 case,which we briefly review in Appendix B.

# 5.1 Solution

In the spin-2 case (i.e. pure Einstein gravity with a negative cosmological constant)，all BTZ black holes can be obtained from the AdS $_ 3$ space via modular transformations of the modulus of the boundary torus (which induces a large coordinate transformation） plus a local coordinate transformation. In the ${ \mathfrak { s l } } ( N )$ higher-spin gravity, let us start with a conical surplus solution and apply the full modular group $\mathrm { { P S L } } ( 2 , \mathbb { Z } )$ ：

Under a modular transformation on the boundary torus

$$
\gamma = \left( \begin{array} { c c } { { a } } & { { b } } \\ { { c } } & { { d } } \end{array} \right) \in \mathrm { P S L } ( 2 , \mathbb { Z } ) : \qquad \tau \longmapsto \hat { \gamma } \tau = \frac { a \tau + b } { c \tau + d }
$$

the A/B cycles of the conical surplus solution map to:

$$
{ \begin{array} { r l r l r l } { { \mathrm { A - c y c l e : } } \quad } & { } & { z \sim z + 2 \pi } & { } & { \longmapsto } & { } & { z \sim z + 2 \pi ( c \tau + d ) } \\ { { \mathrm { B - c y c l e : } } \quad } & { } & { z \sim z + 2 \pi \tau } & { } & { \longmapsto } & { } & { z \sim z + 2 \pi ( a \tau + b ) } \end{array} }
$$

The holonomy matrix around the contractible cycle should now be

$$
\omega _ { \mathrm { A } } = ( c \tau + d ) \ a _ { z } + ( c \bar { \tau } + b ) \ a _ { \bar { z } }
$$

which for a smooth solution should be:

$$
\Lambda \left( \omega _ { \mathrm { A } } \right) = i \vec { n }
$$

with $\vec { n }$ satisfying (2.26). Let us label this new solution by $\gamma$

Now, if we start with a given conical surplus with parameter $\{ \vec { n } ; \tau ; \mu _ { s } \}$ (holonomy vector around $\phi$ -cycle,boundary modulus, chemical potentials),and whose charge function is known to be given by (4.3)，what can we say about this new smooth solution labeled by $\gamma$ ? Again, since in this theory a solution is defined by the trivial holonomy condition around its A-cycle, the answer must lie in a comparison between the holonomy condition of the conical surplus and that of the solution $\gamma$ . Therefore we follow the strategy used earlier (in Section 4.1) in proving the S-duality between the conical surplus and the black hole: we first recast the holonomy condition of the solution $\gamma$ into the form of that of the conical surplus to facilitate the comparison, then we infer the transformation rules from this comparison.

The conical surplus with parameter $\{ \vec { n } ; \tau ; \mu _ { s } \}$ is defined by the equation (4.7),but we now write it again for the ease of comparison:

$$
\mathrm { C S : } \qquad i \vec { n } = \Lambda \left( \omega _ { \phi } \left[ \tau ; \mu _ { s } ; Q _ { s } \right] \right) = \Lambda \left( a _ { z } \left[ Q _ { s } \right] \right) + \Lambda \left( a _ { \bar { z } } \left[ \tau ; \mu _ { s } ; Q _ { s } \right] \right) ,
$$

whereas the new smooth constant solution with the same set of parameters $\{ \vec { n } ; \tau ; \mu _ { s } \}$ and labeled by $\gamma$ is defined by

$$
i \stackrel { . } { n } = \Lambda \left( \omega _ { \mathrm { A } } \left[ \tau ; \mu _ { s } ; Q _ { s } \right] \right) = \left( c \tau + d \right) \Lambda \left( a _ { z } \left[ Q _ { s } \right] \right) + \left( c \bar { \tau } + d \right) \Lambda \left( a _ { \bar { z } } \left[ \tau ; \mu _ { s } ; Q _ { s } \right] \right) .
$$

(We remind that in both cases, $Q _ { s }$ can be solved in terms of $\{ \vec { n } ; \tau ; \mu _ { s } \}$ , using (5.5) and (5.6), respectively.） To cast (5.6) into the form of (5.5),let us rerun the argument in Section 4.1. First, the pair (4.1O) and(4.12) now generalize to

$$
\begin{array} { c } { { ( c \tau + d ) \cdot ( c \tau + d ) ^ { L _ { 0 } } a _ { z } [ Q _ { s } ] ( c \tau + d ) ^ { - L _ { 0 } } = a _ { z } [ ( c \tau + d ) ^ { s } Q _ { s } ] , } } \\ { { { } } } \\ { { { } ^ { \circ } + d ) \cdot ( c \tau + d ) ^ { L _ { 0 } } a _ { \bar { z } } [ \tau ; \ \mu _ { s } ; \ Q _ { s } ] ( c \tau + d ) ^ { - L _ { 0 } } = a _ { \bar { z } } [ \hat { \gamma } \tau ; \ \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } ; \ ( c \tau + d ) ^ { s } Q _ { s } ] } } \end{array}
$$

The first identity in (5.7) comes from setting $\kappa = c \tau + d$ in (4.10). To prove the second identity, we again repeat the argument of the S-transformation. First, (4.14) should now be generalized into

$$
\begin{array} { l } { { \displaystyle \left( c \bar { \tau } + d \right) \cdot ( c \tau + d ) ^ { L _ { 0 } } a _ { \bar { z } } \left[ \sigma _ { s } ; Q _ { s } \right] ( c \tau + d ) ^ { - L _ { 0 } } } } \\ { { \displaystyle = \sum _ { s = 2 } ^ { N } \frac { | ( c \tau + d ) | ^ { 2 } \sigma _ { s } } { ( c \tau + d ) ^ { s } } \left[ ( a _ { z } \left[ ( c \tau + d ) ^ { s } Q _ { s } \right] ) ^ { s - 1 } - \frac { \mathrm { T r } ( a _ { z } \left[ ( c \tau + d ) ^ { s } Q _ { s } \right] ) ^ { s - 1 } } { N } \right] . } } \end{array}
$$

Second,(4.15） still applies (note the presence of $\tau _ { 2 }$ instead of the imaginary part of the modular parameter $\textstyle { \frac { a \tau + b } { c \tau + d } }$ ).The only difference is that,now from l.h.s. to ther.h.s.the variables undergo the following transformation:

$$
\begin{array} { r } { \tau \longmapsto \hat { \gamma } \tau = \displaystyle \frac { a \tau + b } { c \tau + d } , \qquad \mu _ { s } \longmapsto \displaystyle \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } , \qquad Q _ { s } \longmapsto ( c \tau + d ) ^ { s } Q _ { s } , } \end{array}
$$

of which (4.13) is merely a special case with $\begin{array} { r } { \gamma = \binom { 0 } { 1 } \quad \mathbf { 0 } } \end{array}$ . Accordingly, the transformation in terms of $( \sigma _ { s } , Q _ { s } )$ analogous to (4.16) should be

$$
\sigma _ { s } \longmapsto | c \tau + d | ^ { 2 } { \frac { \sigma _ { s } } { ( c \tau + d ) ^ { s } } } , \qquad Q _ { s } \longmapsto ( c \tau + d ) ^ { s } Q _ { s } .
$$

(We have used $\begin{array} { r } { \tau _ { 2 } \mapsto \frac { \tau _ { 2 } } { | c \tau + d | ^ { 2 } } } \end{array}$ under $\textstyle \tau \mapsto { \frac { a \tau + b } { c \tau + d } }$ .）Namely,ther.h.s.of (5.8)ispreciely $\begin{array} { r } { a _ { \bar { z } } \left[ \hat { \gamma } \tau ; \ \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } ; \ ( c \tau + d ) ^ { s } Q _ { s } \right] . } \end{array}$ which provestecodidetityf(5.).

With (5.7) proven, evaluating the vectors of eigenvalues of both sides of (5.7) then gives the generalization to the pair (4.11) and (4.17):

$$
\begin{array} { c } { { \displaystyle ( c \tau + d ) \ \Lambda \left( a _ { z } \left[ Q _ { s } \right] \right) = \Lambda \left( a _ { z } \left[ ( c \tau + d ) ^ { s } Q _ { s } \right] \right) , } } \\ { { \displaystyle ( c \bar { \tau } + d ) \ \Lambda \left( a _ { \bar { z } } \left[ \tau ; \mu _ { s } ; \ Q _ { s } \right] \right) = \Lambda \left( a _ { \bar { z } } \left[ \hat { \gamma } \tau ; \ \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } ; \ ( c \tau + d ) ^ { s } Q _ { s } \right] \right) . } } \end{array}
$$

Having proved the pair (5.11),we can now use them to rewrite the holonomy condition of the solution $\gamma$ into the form of the conical surplus:

$$
i \ { \vec { n } } = \Lambda \left( \omega _ { \mathrm { A } } \left[ \tau ; \mu _ { s } ; \ Q _ { s } \right] \right) = \Lambda \left( \omega _ { \phi } \left[ { \hat { \gamma } } \tau ; \ { \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } } ; \ ( c \tau + d ) ^ { s } Q _ { s } \right] \right) .
$$

Namely, the solution $\gamma$ can be generated by a passive change of variables (5.9) on the conical surplus.

In order to sum over the contributions from all members of the ‘SL $( 2 , \mathbb { Z } ) ^ { \dag }$ family to the full partition function, we need to place all the solutions in a common grand canonical ensemble, with common temperature and chemical potentials. This requires us to switch to the active viewpoint of the transformation, i.e. we hold $\{ \vec { n } ; \tau ; \mu _ { s } \}$ fixed and ask how the conserved charges $Q _ { s }$ transform. Comparing (5.12） with the holonomy condition (5.5） of the conical surplus we conclude that for given $\{ \vec { n } ; \tau ; \mu _ { s } \}$ the on-shell value of the charges $Q _ { s }$ of this new solution $\gamma$ is related to that of the conical surplus via:

$$
{ \mathrm {  ~ s ~ } } = q _ { t } \left[ { \vec { n } } ; \ { \tau } ; \ \mu _ { s } \right] \Longleftrightarrow \qquad Q _ { t } ^ { \gamma } = { \frac { 1 } { ( c \tau + d ) ^ { t } } } q _ { t } \left[ { \vec { n } } ; \ { \hat { \gamma } } \tau ; \ { \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } } \right] \qquad t = 2 , .
$$

To summarize, we have proved that starting with a conical surplus with parameters $\{ \vec { n } ; \tau ; \mu _ { s } \}$ (holonomy vector around $\phi$ -cycle,boundary modulus, chemical potentials)，the transformation (5.1) maps it into another smooth constant solution with the same chemical potentials $\{ \mu _ { s } \}$ ， whose holonomy around the new A-cycle $z \sim z + 2 \pi ( c \tau + d )$ is trivial and is given by the same vector $\vec { n }$ , and whose on-shell values of charges are given by

$$
\mathrm { s o l u t i o n } \ \gamma : \qquad Q _ { t } ^ { \gamma } = { \frac { 1 } { ( c \tau + d ) ^ { t } } } q _ { t } \left[ \vec { n } ; \ \hat { \gamma } T ; \ { \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } } \right] \qquad t = 2 , \ldots , N .
$$

where $q _ { t }$ is the function defined by the charge function of the conical surplus as in (4.3).

Then as $\gamma$ runs through $\Gamma _ { \infty } \backslash \Gamma$ , we obtain a ‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family of smooth constant solutions with a common set of $\{ \vec { n } ; \ \tau ; \ \mu _ { s } \}$ ; their only difference is in the choices of their A/B cycles which in turn give different on-shell values for the charges as given by (5.14). Within each such $\operatorname { S L } ( 2 , \mathbb { Z } )$ family (labeled by $\{ \vec { n } ; \tau ; \mu _ { s } \} )$ ，all except for the one with $\gamma = { \binom { 1 } { 0 } } 1$ (i.e. the conical surplus) are higher-spin black holes (since their A-cycles all have $t$ -direction),in complete parallel to the spin-2 case.

# 5.2 Reasoning from dual CFT

Let us see this from the dual CFT side,borrowing the argument from [55]. In the CFT side,switching on the chemical potentials $\mu _ { s }$ of the higher-spin charges can be accounted for perturbatively by adding an irrelevant perturbation to the action

$$
S _ { C F T } \to S _ { C F T } + \sum _ { s \geq 3 } ^ { N } \int \frac { d ^ { 2 } z } { 4 \pi \tau _ { 2 } } \left( \mu _ { s } W ^ { ( s ) } ( z ) - c . c . \right) .
$$

Correspondingly, the partition function (3.1) is equal to the torus amplitude in the CFT side:

$$
\begin{array} { r } { Z ^ { \mathrm { C F T } } [ \tau ; \mu _ { s } ] \equiv \langle e ^ { 2 \pi i \left( \sum _ { s = 3 } ^ { N } { \mu _ { s } \int \frac { { { d ^ { 2 } } z } } { 2 \pi { \tau _ { 2 } } } { W ^ { ( s ) } } ( z ) - c . c . } \right) } \rangle } \end{array}
$$

The volume element $\frac { d ^ { 2 } z } { 2 \pi \tau _ { 2 } }$ should be invariant under a modular transformation; therefore the modular transformation (2.19) induces a transformation of the coordinates:

$$
\tau \longmapsto { \hat { \gamma } } \tau = { \frac { a \tau + b } { c \tau + d } } \quad \quad \implies \quad z \longmapsto z ^ { \prime } = { \frac { z } { c \tau + d } } .
$$

In the highest-weight gauge we are using, the spin- $s$ field $W ^ { ( s ) } ( z )$ is a Virasoro primary of weight- $s$ , therefore under (5.17)

$$
W ^ { ( s ) } ( z ) \longmapsto W ^ { ( s ) \prime } ( z ^ { \prime } ) = ( c \tau + d ) ^ { s } W ^ { ( s ) } ( z ) .
$$

Namely $W ^ { ( s ) } ( z )$ has weight- $s$ under both conformal and modular transformations [55]. First this means that $\begin{array} { r } { Q _ { s } = \int \frac { d ^ { 2 } z } { 2 \pi \tau _ { 2 } } W ^ { ( s ) } ( z ) } \end{array}$ also transforms as

$$
Q _ { s } \longmapsto Q _ { s } ^ { \prime } = ( c \tau + d ) ^ { s } Q _ { s } .
$$

Second the invariance of the integrand implies that the chemical potential $\mu _ { s }$ transforms as

$$
\mu _ { s } \longmapsto \mu _ { s } ^ { \prime } = { \frac { 1 } { ( c \tau + d ) ^ { s } } } \mu _ { s } .
$$

The maps (5.17)，(5.19)，and (5.20) together are precisely what we have shown earlier in (5.9) to be the required change of variables (in the passive viewpoint of the transformation)

to map the conical surplus to the solution $\gamma$

Finally we make a comparison between the transformations in the passive viewpoint and the active one. In the passive viewpoint, one applies the following change of variables:

$$
\vec { n } \mathrm { ~ f i x e d , } \quad \tau \longmapsto \hat { \gamma } \tau = \frac { a \tau + b } { c \tau + d } , \quad \mu _ { s } \longmapsto \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } , \quad Q _ { s } \longmapsto ( c \tau + d ) ^ { s } Q _ { s } .
$$

We have adopted the passive viewpoint in the proof of the mapping between different members of solutions under the modular transformation. Once the mapping is established, we switch to the active viewpoint in order to place all solutions in the ‘ ${ \mathrm { S L } } ( 2 , \mathbb { Z } ) ^ { \prime }$ family in one grand canonical ensemble:

$$
\begin{array} { r l } { \mathrm { a c t i v e : } \quad } & { \{ \vec { n } ; \tau ; \mu _ { s } \} \quad \mathrm { f i x e d } , } \\ & { Q _ { s } = q _ { s } [ \vec { n } ; \tau ; \mu _ { r } ] \longmapsto Q _ { s } ^ { \gamma } = \displaystyle \frac { 1 } { ( c \tau + d ) ^ { s } } q _ { s } \left[ \vec { n } ; \hat { \gamma } \tau ; \displaystyle \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } \right] . } \end{array}
$$

# 5.3 Coordinate transformations between members of ‘\$ $\mathbf { S L } ( 2 , \mathbb { Z } ) ^ { \dag }$ family

In Section 4.2 we proved that a black hole with parameter $\{ \vec { n } ; \ \tau ; \ \mu _ { s } \}$ can be mapped to a conical surplus with parameter $\{ \vec { n } ; - \textstyle { \frac { 1 } { \tau } } ; \frac { \mu _ { s } } { \tau ^ { s } } \}$ via a coordinate transformation (see (4.27)). The generalization to the full ‘ $\operatorname { S L } ( 2 , \mathbb { Z } ) ^ { \prime }$ family is immediate.

First, the gauge field components $( a _ { z } , a _ { \bar { z } } )$ of a conical surplus and those of solutin $\gamma$ are related via:

$$
\begin{array} { l } { { a _ { z } ^ { \mathrm { C S } } \left[ \vec { n } ; \hat { \gamma } \tau ; \displaystyle \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } \right] = ( c \tau + d ) \cdot ( c \tau + d ) ^ { L _ { 0 } } a _ { z } ^ { \gamma } [ \vec { n } ; \tau ; \mu _ { s } ] ( c \tau + d ) ^ { - L _ { 0 } } , } } \\ { { a _ { z } ^ { \mathrm { C S } } \left[ \vec { n } ; \hat { \gamma } \tau ; \displaystyle \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } \right] = ( c \bar { \tau } + d ) \cdot ( c \tau + d ) ^ { L _ { 0 } } a _ { z } ^ { \gamma } [ \vec { n } ; \tau ; \mu _ { s } ] ( c \tau + d ) ^ { - L _ { 0 } } . } } \end{array}
$$

Similar to the S-dual case, we apply a coordinate transformation to the conical surplus:

$$
\longrightarrow \rho ^ { \gamma } = \rho + \ln | c \tau + d | , { \qquad z \longmapsto z ^ { \gamma } = { \frac { z } { c \tau + d } } } , { \qquad \bar { z } \longmapsto \bar { z } ^ { \gamma } = { \frac { \bar { z } } { c \bar { \tau } + d } } . }
$$

With the gauge component $( a _ { z } , a _ { \bar { z } } )$ kept fixed, the one-form $a$ and $A$ in this new coordinate are

$$
a ^ { ( z , \bar { z } ) ^ { \gamma } } \equiv a _ { z } d z ^ { \gamma } + a _ { \bar { z } } d \bar { z } ^ { \gamma } , \qquad A ^ { ( \rho , z , \bar { z } ) ^ { \gamma } } \equiv e ^ { - \rho ^ { \gamma } L _ { 0 } } a ^ { ( z , \bar { z } ) ^ { \gamma } } e ^ { \rho ^ { \gamma } L _ { 0 } } + L _ { 0 } d \rho ^ { \gamma } ;
$$

and similarly for $a$ and $A$ . The gauge one-form $\{ a , \bar { a } \}$ of the solution $\gamma$ with parameter $\{ \vec { n } ; \ \tau ; \ \mu _ { s } \}$ in the original coordinate $( \rho , z , \bar { z } )$ is related to that of the conical surplus with

parameter $\{ \vec { n } ; \hat { \gamma } \tau ; \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } \}$ but in the new coordinate $( \rho , z , \bar { z } ) ^ { \gamma }$ via:

$$
\begin{array} { l } { { a ^ { \mathrm { C S } } \left[ \vec { n } ; \hat { \gamma } \tau ; \displaystyle \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } \right] ^ { ( z , \bar { z } ) \gamma } = ( c \tau + d ) ^ { L _ { 0 } } a ^ { \gamma } \left[ \vec { n } ; \tau ; \mu _ { s } \right] ^ { ( z , \bar { z } ) } ( c \tau + d ) ^ { - L _ { 0 } } , } } \\ { { \bar { a } ^ { \mathrm { C S } } \left[ \vec { n } ; \hat { \gamma } \tau ; \displaystyle \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } \right] ^ { ( z , \bar { z } ) \gamma } = ( c \bar { \tau } + d ) ^ { - L _ { 0 } } \bar { a } ^ { \gamma } \left[ \vec { n } ; \tau ; \mu _ { s } \right] ^ { ( z , \bar { z } ) } ( c \bar { \tau } + d ) ^ { L _ { 0 } } . } } \end{array}
$$

The full gauge one-forms $( A , A )$ of the solution $\gamma$ with parameter $\{ \vec { n } ; \ \tau ; \ \mu _ { s } \}$ in the original coordinate $( \rho , z , \bar { z } )$ is then identical to that of the conical surplus with parameter $\textstyle \left\{ { \vec { n } } ; { \hat { \gamma } } \tau ; \ { \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } } \right\}$ but in the new coordinate $( \rho , z , \bar { z } ) ^ { \gamma }$ upto an overallostant gauge transformation:

$$
\begin{array} { r l } & { \hat { h } _ { \gamma } ^ { - 1 } \cdot A ^ { \mathrm { C S } } \left[ \vec { n } ; \hat { \gamma } \tau ; \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } \right] ^ { ( \rho , z , \bar { z } ) ^ { \gamma } } \cdot \hat { h } _ { \gamma } = A ^ { \gamma } \left[ \vec { n } ; \tau ; \mu _ { s } \right] ^ { ( \rho , z , \bar { z } ) } , } \\ & { \hat { h } _ { \gamma } ^ { - 1 } \cdot \bar { A } ^ { \mathrm { C S } } \left[ \vec { n } ; \hat { \gamma } \tau ; \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } \right] ^ { ( \rho , z , \bar { z } ) ^ { \gamma } } \cdot \hat { h } _ { \gamma } = \bar { A } ^ { \gamma } \left[ \vec { n } ; \tau ; \mu _ { s } \right] ^ { ( \rho , z , \bar { z } ) } , } \end{array}
$$

with

$$
\hat { h } _ { \gamma } = \left( \frac { c \bar { \tau } + d } { c \tau + d } \right) ^ { \frac { L _ { 0 } } { 2 } } .
$$

This means that all constant solutions in the $\operatorname { S L } ( 2 , \mathbb { Z } )$ family are locally identical: they are all discrete quotients of the $\mathrm { S L } ( N , \mathbb { R } ) \otimes \mathrm { S L } ( N , \mathbb { R } )$ .Explicitly, for constant solutions, the connection $A$ in the gauge (2.4) can be written as $A = g ^ { - 1 } d g$ with $g \equiv e ^ { z a _ { z } + z a _ { \bar { z } } } b \in \mathrm { S L } ( N , \mathbb { R } )$ （20 and $b = e ^ { \rho L _ { 0 } }$ [59]. Since for the solution $\gamma$ , the space has a B-cycle $( z , \bar { z } ) \sim ( z + 2 \pi ( a \tau +$ （204号 $b ) , \bar { z } + 2 \pi ( a \bar { \tau } + b ) )$ ， $g ^ { \gamma }$ satisfies

$$
g ^ { \gamma } \sim \left( b \mathrm { H o l _ { B } } ( A ^ { \gamma } ) b ^ { - 1 } \right) \cdot g ^ { \gamma } ,
$$

where $\operatorname { H o l } _ { \mathrm { B } } ( A ^ { \gamma } )$ is the holonomy of $A ^ { \gamma }$ around the B-cycle:

$$
\mathrm { H o l } _ { \mathrm { B } } ( A ^ { \gamma } ) = b ^ { - 1 } e ^ { 2 \pi \omega _ { \mathrm { B } } ^ { \gamma } } b
$$

with

$$
= ( c \tau + d ) ^ { - L _ { 0 } } \cdot \left( \hat { \gamma } \tau a _ { z } ^ { \mathrm { C S } } \left[ \vec { n } ; \hat { \gamma } \tau ; \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } \right] + \hat { \gamma } \bar { \tau } a _ { \bar { z } } ^ { \mathrm { C S } } \left[ \vec { n } ; \hat { \gamma } \tau ; \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } \right] \right) \cdot ( c \tau + d ) ^ { - L _ { 0 } }
$$

using the definition (2.35) and the relation (5.23),and similarly for the $A$ sector. Namely, the solution $\gamma$ is the quotient of SL $( N , \mathbb { R } )$ by a matrix that is given by the holonomy of $A ^ { \gamma }$ around the B-cycle conjugated by $b$ .13For fixed $\{ \tau , \mu _ { s } \}$ ，the matrix ( $\left( b \operatorname { H o l } _ { \mathrm { B } } ( A ^ { \gamma } ) b ^ { - 1 } \right)$ isa

representation of a point in $\Gamma _ { \infty } \backslash \Gamma$

This is the analogue of the spin-2 story: in the spin-2 case, a solution $\gamma$ in the ‘SL $( 2 , \mathbb { Z } )$ family can be mapped by a coordinate transformation into an AdS $_ 3$ with modular parameter （20 $\textstyle { \frac { a \tau + b } { c \tau + d } }$ (instead of $\tau$ ). All these solutions are discrete quotients of the AdS $^ 3$ space by elements of ${ \mathrm { S L } } ( 2 , \mathbb { Z } )$ [5,6].

# 5.4 Mapping of the free energy

Recall that the free energy of a conical surplus and that of its S-dual black hole are related by (4.41). Now we generalize this mapping to the entire‘SL $( 2 , \mathbb { Z } )$ family. Different members of the ‘ $\operatorname { S L } ( 2 , \mathbb { Z } ) ^ { \prime }$ family share the same holonomy vector $\vec { n }$ ,around their respective A-cycles. Therefore although we have a number of different expressions for the free energy, the one we should use to study the mapping under a modular transformation is the one written explicitly in terms of the holonomy matrices,and in a form universal across the ‘ $\operatorname { S L } ( 2 , \mathbb { Z } )$ （204号 family — the expression (3.35) is ideal for this purpose.

Within a‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family,all members share the same $\{ \vec { n } ; \ \tau ; \ \mu _ { s } \}$ but differ in their modular parameters $\gamma$ and hence their charges $Q _ { s } ^ { \gamma }$ , as given in (5.14). To obtain the mapping between the free energies of different members,we first need to rewrite (3.35) in terms of only $\{ \vec { n } ; \tau ; \mu _ { s } \}$ and $\gamma$ . Since we already know that the charges $Q _ { s } ^ { \gamma }$ for different $\gamma$ are related via (5.14),we will first rewrite (3.35) in terms of $\{ \vec { n } ; \ \tau ; \ \mu _ { s } ; \ Q _ { s } ^ { \gamma } \}$ and $\gamma$ ：

Using

$$
\begin{array} { c } { { { \frac { 1 } { 2 } } \mathrm { T r } \left[ \omega _ { \mathrm { A } } \omega _ { \mathrm { B } } \right] = \displaystyle ( a \tau + b ) ( c \tau + d ) Q _ { 2 } ^ { \gamma } + { \frac { i \mathrm { R e } [ ( a \tau + b ) ( c \bar { \tau } + d ) ] } { 2 \tau _ { 2 } } } \sum _ { s = 3 } ^ { N } s \mu _ { s } Q _ { s } ^ { \gamma } } } \\ { { + ~ ( a \bar { \tau } + b ) ( c \bar { \tau } + d ) { \frac { \mathrm { T r } [ ( a _ { \bar { z } } ) ^ { 2 } ] } { 2 } } , } } \end{array}
$$

and

$$
\ddot { n } ^ { 2 } = \frac { 1 } { 2 } \mathrm { T r } \left[ ( \omega _ { \mathrm { A } } ) ^ { 2 } \right] = ( c \tau + d ) ^ { 2 } Q _ { 2 } ^ { \gamma } + \frac { i | c \tau + d | ^ { 2 } } { 2 \tau _ { 2 } } \sum _ { s = 3 } ^ { N } s \mu _ { s } Q _ { s } ^ { \gamma } + \frac { ( c \bar { \tau } + d ) ^ { 2 } } { 2 } \mathrm { T r } \left[ ( a _ { \bar { z } } ) ^ { 2 } \right]
$$

we arrive at an identity

$$
\frac { 1 } { 2 } \operatorname { T r } \left[ \omega _ { \mathrm { A } } \omega _ { \mathrm { B } } \right] = - \frac { \vec { n } ^ { 2 } } { 2 } \hat { \gamma } \bar { \tau } + \frac { 2 i \tau _ { 2 } } { | c \tau + d | ^ { 2 } } ( c \tau + d ) ^ { 2 } Q _ { 2 } ^ { \gamma } - \sum _ { s = 3 } ^ { N } \frac { s } { 2 } \mu _ { s } Q _ { s } ^ { \gamma } ,
$$

which immediately allows us to rewrite the free energy (3.35) in terms of $\{ \vec { n } ; \ \tau ; \ \mu _ { s } ; \ Q _ { s } ^ { \gamma } \}$ and $\gamma$

$$
= 2 \pi i k \Big ( \frac { 2 i \tau _ { 2 } } { \vert c \tau + d \vert ^ { 2 } } \Big [ \frac { \vec { n } ^ { 2 } } { 2 } + ( c \tau + d ) ^ { 2 } Q _ { 2 } ^ { \gamma } + ( c \bar { \tau } + d ) ^ { 2 } \bar { Q } _ { 2 } ^ { \gamma } \Big ] - \sum _ { s = 3 } ^ { N } ( s - 1 ) ( \mu _ { s } Q _ { s } ^ { \gamma } - \bar { \mu } _ { s } \bar { Q } _ { \gamma } ^ { \gamma } )
$$

Then recall that $Q _ { s } ^ { \gamma }$ depends on $\{ \vec { n } ; \tau ; \mu _ { s } \}$ and $\gamma$ via (5.14), we obtain the expression of the free energy in terms of $\{ \vec { n } ; \ \tau ; \ \mu _ { s } \}$ only:

$$
\begin{array} { c } { { \displaystyle { \beta F ^ { \gamma } = 2 \pi i k [ \frac { 2 i \tau _ { 2 } } { | c \tau + d | ^ { 2 } } ( \frac { { \vec { n } } ^ { 2 } } { 2 } + q _ { 2 } [ { \vec { n } } ; \hat { \gamma } \tau ; \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } ] + { \bar { q } } _ { 2 } [ { \vec { n } } ; \hat { \gamma } \tau ; \frac { \bar { \mu } _ { s } } { ( c \bar { \tau } + d ) ^ { s } } ] ) } } } \\ { { \displaystyle { - \sum _ { s = 3 } ^ { N } ( s - 1 ) ( \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } q _ { s } [ \vec { n } ; \hat { \gamma } \tau ; \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } ] - \frac { \bar { \mu } _ { s } } { ( c \bar { \tau } + d ) ^ { s } } \bar { q } _ { s } [ \vec { n } ; \hat { \gamma } \bar { \tau } ; \frac { \bar { \mu } _ { s } } { ( c \bar { \tau } + d ) ^ { s } } ] ) } } } \end{array} .
$$

Comparing this with (4.35), we obtain the map between the free energy of the conical surplus and that of the solution $\gamma$ ·，

$$
\left[ { \vec { n } } ; ~ { \tau } ; ~ { \mu } _ { s } \right] = { \mathcal { F } } [ { \vec { n } } ; ~ { \tau } ; ~ { \mu } _ { s } ] \qquad \Longleftrightarrow \qquad F ^ { \gamma } \left[ { \vec { n } } ; ~ { \tau } ; ~ { \mu } _ { s } \right] = { \mathcal { F } } \left[ { \vec { n } } ; ~ { \hat { \gamma } } { \tau } ; ~ { \frac { \mu _ { s } } { \left( c { \tau } + d \right) ^ { s } } } \right]
$$

This proves that different solutions $\gamma$ in the ${ \mathrm { \hat { S L } } } ( 2 , \mathbb { Z } ) $ family share the same form for their free energies, and they can all be obtained by applying the following transformation

$$
\mathrm { d u l a r \ t r a n s f o r m a t i o n \ i n \ G C E : } \qquad \tau \longmapsto \hat { \gamma } \tau = \frac { a \tau + b } { c \tau + d } \qquad \mu _ { s } \longmapsto \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } ,
$$

on the free energy of the conical surplus.

Recall that in the spin-2 case, the metric of the solution labeled by $\gamma$ in the $\operatorname { S L } ( 2 , \mathbb { Z } ) ^ { \prime }$ family can be brought into the metric of the $\mathrm { A d S _ { 3 } }$ with modular parameter $\begin{array} { r } { \hat { \gamma } \tau ~ = ~ \frac { a \tau + b } { c \tau + d } } \end{array}$ (instead of $\tau$ ) via a coordinate transformation. Since the on-shell action should be invariant under the coordinate transformation, the free energies of the solution $\gamma$ and the ${ \mathrm { A d S } } _ { 3 }$ is necessrily related bythe modular transformation: $\begin{array} { r } { F ^ { \gamma } [ \tau ] = F ^ { \mathrm { A d S } _ { 3 } } [ \frac { a \tau + b } { c \tau + d } ] } \end{array}$ , and in particular $F ^ { \mathrm { B ^ { \prime } I ^ { \prime } Z } } [ \tau ] = F ^ { \mathrm { A d S } _ { 3 } } [ - { \frac { 1 } { \tau } } ]$ ，

The non-trivial part of the story is in the construction of the full action (including boundary terms) whose Euclidean on-shell action (hence the free energy) is invariant under coordinate transformations. Now we have seen a complete parallel in the ${ \mathfrak { s l } } ( N )$ ChernSimons theory. As shown in Section 5.3，different members of the ‘ ${ \mathrm { S L } } ( 2 , \mathbb { Z } ) ^ { \prime }$ family are related by the coordinate transformation (5.27), therefore the mapping between their free energies (5.37) not only confirms the mapping between diferent solutions via (5.22） and (5.27)，more importantly， it provides strong evidence that the thermodynamics that we derived in Section 3 is consistent and applies to all members in the‘SL $( 2 , \mathbb { Z } )$ family. We regard this as a much more non-trivial result than the mapping of different members at the level of solution.

# 5.5 Modular invariant full partition function

The full partition function should include contributions from all saddle points. Let us first classify all classical solutions known to us. First, for each holonomy vector $\vec { n }$ satisfying (2.26) there is a‘ $\operatorname { S L } ( 2 , \mathbb { Z } ) ^ { \prime }$ family of solutions constructed earlier in this section. Using $Z = e ^ { - \beta \boldsymbol { F } }$ （20 and (5.37)，we see that the contribution from each member $\gamma$ is an image of the modular transformation (5.38) of the contribution from the conical surplus:

$$
Z _ { \vec { n } } ^ { \gamma } \left[ \tau ; \mu _ { s } \right] = Z _ { \vec { n } } ^ { \mathrm { C S } } \left[ \hat { \gamma } \tau ; \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } \right] .
$$

For given $\vec { n }$ , we should first sum over all members within this ‘SL $( 2 , \mathbb { Z } ) ^ { \dag }$ family, which consists of all the modular images of the conical surplus:

$$
Z _ { \vec { n } } \left[ \tau ; \mu _ { s } \right] = \sum _ { \gamma \in \Gamma _ { \infty } \backslash \Gamma } Z _ { \vec { n } } ^ { \gamma } \left[ \tau ; \mu _ { s } \right] = \sum _ { \gamma \in \Gamma _ { \infty } \backslash \Gamma } Z _ { \vec { n } } ^ { \mathrm { C S } } \left[ \hat { \gamma } \tau ; \frac { \mu _ { s } } { ( c \tau + d ) ^ { s } } \right] .
$$

So far this is in complete parallel to the spin-2 case studied in [8,57]. Now comes the major difference: we should also sum over all distinct $\vec { n }$ satisfying (2.26):

$$
Z \left[ \tau ; \mu _ { s } \right] = \sum _ { \vec { n } } Z _ { \vec { n } } \left[ \tau ; \mu _ { s } \right] .
$$

This expression is manifestly modular invariant. After the appropriate regularization, one can then use it to extract the phase structure of the full theory. For instance, the (infinite) sum over $\vec { n }$ might smear out the Hawking-Page transition, as argued in [58]. We leave this to future work.

# 6 Discussion

The goal of this paper is simple: in the three-dimensional asymptotically AdS $^ 3$ space，we want to generalize the construction of the ‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family of solutions from the spin-2 gravity to the higher-spin gravity. We achieved this in the ${ \mathfrak { s l } } ( N )$ Chern-Simons theory. The main results have already been summarized in Section 1, now we end with a discussion on the main difference of the higher-spin theory from the spin-2 one.

In the spin-2 theory one usually works with the metric,and under a modular transformation of the boundary torus the mapping between different solutions can be written in terms of the coordinate transformations of the bulk metric. In the higher-spin theory, the metric (more precisely the line element $d s ^ { 2 }$ ） is no longer a gauge invariant concept therefore would not be suitable for a discussion on the modular property. However, as we have seen, the gauge connection in the Chern-Simon higher-spin theory is actually more convenient for the study of the modular properties than the metric in the spin-2 gravity.

First of all, the defining equation of a smooth solution (the trivial holonomy condition around its A-cycle) is manifestly modular covariant,i.e. a passive change of variables (5.9) directly maps it into the defining equation of another smooth solution, as shown in (5.12). Moreover, the free energy also has an expresson (3.35) that is universal for all solutions and using which one can arrive at a modular-covariant expression (5.36). For the entropy, we have also derived an expression (3.38) that applies to all members of ‘ ${ \mathrm { S L } } ( 2 , \mathbb { Z } ) ^ { \prime }$ family.

Finally，, we finish with a proof of the modular invariance of the integrability condition of the theory, and with it a discussion on an important difference between the‘canonical' formalism and the‘holomorphic’ one.

# 6.1 Modular invariance of integrability condition

The existence of the free energy formula (3.36) guarantees the following integrability condition

$$
\frac { \partial Q _ { s } } { \partial \mu _ { t } } = \frac { \partial Q _ { t } } { \partial \mu _ { s } } , \qquad \frac { \partial T } { \partial \mu _ { s } } = \frac { \partial Q _ { s } } { \partial \tau } , \qquad s , t = 3 , \ldots , N ,
$$

for all members of the ‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family, i.e. the relations (6.1) should be modular invariant. However, it is instructive to see how it works in detail. This not only serves as a non-trivial consistency check for our construction of the ‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family of solutions； it will also be used later when we compare with other discussions of the thermodynamics in this theory.

To show that (6.1) is modular invariant, we compare the relation (6.1) for a conical surplus with that of a generic solution labeled by $\gamma$ ，and show that the latter can be obtained by a modular transformation (5.38) of the former. First,let’s start with the first condition of (6.1). When the solution is a conical surplus,we plug (4.3) into (6.1) and obtain

$$
\frac { \partial q _ { s } } { \partial \mu _ { t } } [ \tau , \mu _ { r } ] = \frac { \partial q _ { t } } { \partial \mu _ { s } } [ \tau , \mu _ { r } ] .
$$

(In this proof we omit $\vec { n }$ since it stays invariant under modular transformations.） Then for

a generic solution labeled by $\gamma$ ， plugging in (5.14) and using14

$$
\frac { \partial Q _ { s } ^ { \gamma } } { \partial \mu _ { t } } = \frac { 1 } { ( c \tau + d ) ^ { s + t } } \frac { \partial q _ { s } } { \partial \mu _ { t } } [ \hat { \gamma } \tau ; \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } ] ,
$$

we get the integrability condition to be

$$
\frac { \partial q _ { s } } { \partial \mu _ { t } } [ \widehat { \gamma } \tau ; \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } ] = \frac { \partial q _ { t } } { \partial \mu _ { s } } [ \widehat { \gamma } \tau ; \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } ] ,
$$

which is precisely the modular transformation (5.38) of the integrability condition of the conical surplus (6.2).

The second condition of (6.1) is slightly harder since it involves $T$ ,which is not modular covariant in itself: for a generic solution labeled by $\gamma$ ， $' \boldsymbol { I } ^ { \prime }$ is

$$
T = \frac { 1 } { ( c \tau + d ) ^ { 2 } } \left[ \frac { \vec { n } ^ { 2 } } { 2 } + q _ { 2 } + \bar { q } _ { 2 } \right] + \frac { i } { 2 \tau _ { 2 } } \sum _ { s = 3 } ^ { N } s \left[ \frac { \mu _ { s } q _ { s } } { ( c \tau + d ) ^ { s } } - \frac { c \bar { \tau } + d } { c \tau + d } \frac { \bar { \mu } _ { s } \bar { q } _ { s } } { ( c \bar { \tau } + d ) ^ { s } } \right] ,
$$

where the variables inside the function $q _ { t }$ .is $\textstyle \left( { \widehat { \gamma } } \tau ; { \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } } \right)$ . However as we will now show, the integrability condition involving $'  { I } ^ { \prime }$ is nevertheless modular invariant.First, for the conical surplus

$$
\frac { \partial T } { \partial \mu _ { s } } = \frac { \partial q _ { 2 } } { \partial \mu _ { s } } [ \tau , \mu _ { r } ] + \frac { i } { 2 \tau _ { 2 } } \mathcal { G } _ { s } [ \tau , \mu _ { r } ] ,
$$

with $\mathcal { G } _ { s }$ defined as

$$
\mathcal { G } _ { s } [ \tau , \mu _ { r } ] \equiv s q _ { s } [ \tau , \mu _ { r } ] + \sum _ { t = 3 } ^ { N } t \mu _ { t } \frac { \partial q _ { t } } { \partial \mu _ { s } } [ \tau , \mu _ { r } ] ,
$$

and the integrability condition is

$$
\left( \frac { \partial q _ { 2 } } { \partial \mu _ { s } } [ \tau , \mu _ { r } ] + \frac { i } { 2 \tau _ { 2 } } \mathcal { G } _ { s } [ \tau , \mu _ { r } ] \right) - \frac { \partial q _ { s } } { \partial \tau } [ \tau , \mu _ { r } ] = 0 .
$$

Now for a generic solution, s Tbecomes

$$
\frac { \partial T } { \partial \mu _ { s } } = \frac { 1 } { ( c \tau + d ) ^ { 2 + s } } \left( \frac { \partial q _ { 2 } } { \partial \mu _ { s } } [ \hat { \gamma } \tau ; \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } ] + \frac { i ( c \tau + d ) ^ { 2 } } { 2 \tau _ { 2 } } \mathcal { G } _ { s } [ \hat { \gamma } \tau ; \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } ] \right) .
$$

Comparing (6.9) with (6.6) shows that $\frac { \partial T } { \partial \mu _ { s } }$ is almost covariant,but not quite: the factor in

front of gs is i(ct+d)² instead of iler+dl² . On the other hand, $\frac { \partial Q _ { s } ^ { \gamma } } { \partial \tau }$ becomes

$$
\frac { \partial Q _ { s } ^ { \gamma } } { \partial \tau } = \frac { 1 } { ( c \tau + d ) ^ { 2 + s } } \left( \frac { \partial q _ { s } } { \partial \tau } [ \hat { \gamma } \tau ; \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } ] - c ( c \tau + d ) \mathcal { G } _ { s } [ \hat { \gamma } \tau ; \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } ] \right) .
$$

In general the derivative (w.r.t. $\tau$ )of a modular form is not a modular form. We see something similar happens here as well: although $Q _ { s }$ transforms covariantly under the modular transformation,the last terms of the above equation (6.10) says that $\frac { \partial Q _ { s } ^ { \gamma } } { \partial \tau }$ does not. These two oddities cancel each other out when we subtract (6.10) from (6.9) to write down the integrability condition for the solution $\gamma$

$$
0 = \frac { \partial q _ { 2 } } { \partial \mu _ { s } } [ \hat { \gamma } \tau ; \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } ] + \frac { i | c \tau + d | ^ { 2 } } { 2 \tau _ { 2 } } \mathcal { G } _ { s } [ \hat { \gamma } \tau ; \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } ] - \frac { \partial q _ { s } } { \partial \tau } [ \hat { \gamma } \tau ; \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } ] ,
$$

which is precisely the modular transformation (5.38) of the integrability condition of the conical surplus (6.8).

# 6.2 Canonical vs.holomorphic

Now we would like to compare the ‘holomorphic' formalism with the ‘canonical’ one (which we used throughout this paper). The main difference between these two approaches is in the identification of the spin-2 conserved charges: $Q _ { 2 }$ in the‘holomorphic’ approach and $'  { I } ^ { \prime }$ (as defined in (3.25)) in the‘canonical’ one. This difference in turn leads to different results for the entropy and the free energy. Now relevant to this paper we will focus on the difference in the modular properties of these two formalisms.

The first tell-tale sign that the modular transformation (5.38) would not be applicable in the‘holomorphic' formalism is from the integrability condition. It suffices to look at the ${ \mathfrak { s l } } ( 3 )$ theory considered in [21]. For the black hole in this theory, the spin-2 conserved charge is the holomorphic $Q _ { 2 }$ ，which satisfies the integrality condition [21]

$$
\frac { \partial Q _ { 2 } } { \partial \mu _ { 3 } } = \frac { \partial Q _ { 3 } } { \partial \tau } .
$$

However, if $Q _ { s }$ was to transform under the modular transformation (5.38) in the same way as what we proposed:

$$
Q _ { s } = q _ { s } [ \tau ; \mu _ { r } ] \longmapsto Q _ { s } ^ { \gamma } = \frac { 1 } { ( c \tau + d ) ^ { s } } q _ { s } [ \widehat { \gamma } \tau ; \frac { \mu _ { r } } { ( c \tau + d ) ^ { r } } ]
$$

then (6.12) would not be modular invariant — the l.h.s. of (6.12) is modular covariant as shown in (6.3) whereas the r.h.s. is not,as explained in (6.10) and the lines below. This suggests that if we are to extend the result of [21] into a full ‘SL $( 2 , \mathbb { Z } ) ^ { \prime }$ family, the modular transformation would not be the same as given in the present paper. It would be interesting to work out the appropriate modular transformation in the‘holomorphic’ formalism， for which the translation between the two formalisms discussed in [27] would be helpful.15

# Acknowledgements

We take great pleasure in thanking Matthias Gaberdiel and Stefan Theisen for very helpful discussions. WL also thanks Galileo Galilei Institute for Theoretical Physics and the Benasque string workshop for their hospitality during various stages of this work. FLL is supported by Taiwan's NSC grants (grant NO. 100-2811-M-003-011).

# A Solving $\sigma _ { s }$ in terms of $\mu _ { s }$ （204号

An identity that is central to the proof of this paper is eq. (4.15). To prove it, we can equivalently prove its inverse:

$$
\frac { i } { 2 \tau _ { 2 } } \mu _ { s } = \sum _ { s ^ { \prime } = s } ^ { N } \sigma _ { s ^ { \prime } } \ \tilde { H } _ { s ^ { \prime } - s } ( Q _ { t } )
$$

where $\tilde { H } _ { s ^ { \prime } - s } ( Q _ { t } )$ is another homogenous polynomial of degree- $( s ^ { \prime } - s )$ with variables $Q _ { t }$ having degree- $t$ ：

First recall that the $N - 1$ equations (3.19) with $a _ { \bar { z } }$ given in (2.14) determine $\sigma _ { s }$ in terms of $\mu _ { s }$ . Plugging (2.14) into (3.19), and using $\mathrm { T r } [ W _ { m } ^ { ( s ) } ] = 0$ and $a _ { z } = L _ { 1 } + \mathbf { Q }$ , we have

$$
\frac { 1 } { t ^ { ( s ) } } \sum _ { s ^ { \prime } = 2 } ^ { N } \sigma _ { s ^ { \prime } } \operatorname { T r } \left[ W _ { - s + 1 } ^ { \left( s \right) } \left( L _ { 1 } + \mathbf { Q } \right) ^ { s ^ { \prime } - 1 } \right] = \frac { i } { 2 \tau _ { 2 } } \mu _ { s } \qquad s = 2 , \dots , N
$$

where $\mu _ { 2 } \equiv 0$ . Then plugging in $\begin{array} { r } { \mathbf { Q } = \sum _ { s = 2 } ^ { N } \frac { Q _ { s } } { t ^ { ( s ) } } W _ { - s + 1 } ^ { ( s ) } } \end{array}$ into above andusing thefactthe trace only picks up the zero modes, namely

$$
\mathrm { T r } [ W _ { - s + 1 } ^ { ( s ) } ( L _ { 1 } + { \bf Q ) } ^ { s ^ { \prime } - 1 } ] = \sum _ { m = 0 } ^ { s ^ { \prime } - 1 } c _ { s ^ { \prime } , s } \cdot ( \prod _ { j = 1 } ^ { m } Q _ { s _ { j } } ) \cdot \delta _ { - s + 1 + ( s ^ { \prime } - 1 - m ) + \sum _ { j = 1 } ^ { m } ( - s _ { j } + 1 ) , 0 }
$$

where ${ { \mathcal { C } } _ { \boldsymbol { s } , \boldsymbol { s } ^ { \prime } } }$ are some rational numbers which can be computed from (2.1O) but whose explicit values do not concern us here. Therefore the trace in (A.2） contains only terms $\prod _ { m = 1 } ^ { r } Q _ { s _ { j } }$ with $\begin{array} { r } { \sum _ { j = 1 } ^ { m } s _ { j } = s ^ { \prime } - s } \end{array}$ ,i.e. it is ahomogenous polynomialof degree $( s ^ { \prime } - s )$ with variables $Q _ { t }$ having degree $t$ . Thus we have proved (A.1),which in turns gives (4.15).

# B SL $( 2 , \mathbb { Z } )$ family in spin-2 case

Now we review how all BTZ black holes in spin-2 gravity can be obtained from modular transformations of the AdS $_ 3$ space.Below mostly follows the exposition of [6].

The thermal AdS $_ 3$ is a solid torus,with metric

$$
d s ^ { 2 } = d \rho ^ { 2 } + d u ^ { 2 } + d \bar { u } ^ { 2 } + 2 d u d \bar { u } \cosh \rho
$$

where $\begin{array} { r } { u = \frac { i } { 2 } ( \phi + i t _ { E } ) } \end{array}$ with $\phi$ the angular coordinate and $t _ { E }$ the Euclidean time. In terms of （204号 $u$ the contractible and non-contractible cycles are

$$
\begin{array} { c c } { { \mathrm { C o n t r a c t i b l e ( A ) - c y c l e : } \qquad } } & { { 2 u \sim 2 u + 2 \pi i } } \\ { { \mathrm { N o n - c o n t r a c t i b l e ( B ) - c y c l e : } \qquad } } & { { 2 u \sim 2 u + 2 \pi i s } } \end{array}
$$

where $s = s _ { 1 } + i s _ { 2 }$ (with $s _ { 2 } = 2 \pi \beta \ge 0$ ）is the modulus of the boundary torus in this homology basis (contractible cycle,non-contractible cycle).

Starting with the thermal $\mathrm { A d S _ { 3 } }$ solution， all asymptotically $\mathrm { A d S } _ { s }$ solutions (including AdS $_ 3$ and all BTZ black holes) can be obtained via modular transformations. The easiest way to see this is the following. Since all asymptotically AdS $s$ solutions are locally diffeomorphic, they share the same metric (B.1) but with different maps of $u$ to $z \equiv \phi + i t _ { E }$ . Since $s$ can be mapped to a unique point $\tau$ in the fundamental domain via

$$
s = { \frac { a \tau + b } { c \tau + d } } \qquad { \binom { a } { c } } \in \mathrm { P S L } ( 2 , \mathbb { Z } )
$$

we can uniquely define

$$
2 u = \frac { i } { c \tau + d } z \qquad z = \phi + i t _ { E }
$$

First,the A/B cycle in terms of $u$ translate into the A/B cycle in terms of $z$ ：

$$
\begin{array} { r l } { \mathrm { C o n t r a c t i b l e ( A )  – c y c l e : } \qquad } & { { } z \sim z + 2 \pi ( c \tau + d ) } \\ { \mathrm { N o n \mathrm { - } c o n t r a c t i b l e ( B ) \mathrm { - } c y c l e : } \qquad } & { { } z \sim z + 2 \pi ( a \tau + b ) } \end{array}
$$

Namely， the map plus the designation of A/B-cycles (2.31) determines which space-time cycle is non-contractible ( $\phi$ ，or $t$ ，or a combination of the two)，thus tell us whether the geometry is a thermal AdS $_ 3$ or a BTZ black hole.

This can be confrmed by directly computing the metric. The metric in terms of $( \rho , t _ { E } , \phi )$ obtained by plugging (B.5) into (B.1),can be brought into the BTZ form via another local coordinate transformation (see [6] for details):

$$
\begin{array} { l } { { d s ^ { 2 } = N ^ { 2 } ( r ) d t _ { E } ^ { 2 } + { \displaystyle \frac { d r ^ { 2 } } { N ^ { 2 } ( r ) } } + r ^ { 2 } ( d \phi + N ^ { \phi } ( r ) d t _ { E } ) ^ { 2 } } } \\ { { \displaystyle N ^ { 2 } ( r ) = { \displaystyle \frac { ( r ^ { 2 } - r _ { 2 } ^ { 2 } ) ( r ^ { 2 } + r _ { 1 } ^ { 2 } ) } { r ^ { 2 } } } , \qquad N ^ { \phi } ( r ) = { \displaystyle \frac { r _ { 1 } r _ { 2 } } { r ^ { 2 } } } , \qquad \mathrm { w i t h } r _ { 1 } + i r _ { 2 } = \pm { \displaystyle \frac { 1 } { c \tau + d } } } } \end{array}
$$

where $( c , d ) = ( 0 , 1 )$ corresponds to the thermal $\mathrm { A d S _ { 3 } }$ and $( c , d ) = ( 1 , 0 )$ to the BTZ black hole with $z \sim z + 2 \pi \bigl ( - \frac { 1 } { \tau } \bigr )$ ; and other $( c , d )$ with $\operatorname* { g c d } ( c , d ) = 1$ gives the whole “SL $( 2 , \mathbb { Z } )$ ” family of ${ \mathrm { A d S } } _ { 3 }$ and BTZ black holes.

Once we write down the AdS $_ 3$ solution, we can generate the entire family via modular transformation. The full partition function is the sum over all modular images:

$$
Z = \sum _ { \Gamma _ { \infty } \backslash \Gamma } Z _ { \mathrm { A d S } _ { 3 } } ( \frac { a \tau + b } { c \tau + d } )
$$

The resulting partition function is divergent and need to be regularized. We refer this issue to [6,61].

# C Example-2: $N = 4$ （20

Now let's check the next simplest example: the $N = 4$ case. The computation is essentially the same as the previous $N = 3$ case,only with longer expressions. First, $a _ { z }$ is

$$
a _ { z } = L _ { 1 } - \frac { Q _ { 2 } } { 1 0 } L _ { - 1 } + \frac { Q _ { 3 } } { 2 4 } W _ { - 2 } ^ { ( 3 ) } - \frac { Q _ { 4 } } { 3 6 } W _ { - 3 } ^ { ( 4 ) } ,
$$

And $a _ { \bar { z } }$ is solved via (3.19):

$$
a _ { \bar { z } } = \frac { i } { 2 \tau _ { 2 } } \Big [ - \frac { 4 1 } { 5 0 } \mu _ { 4 } Q _ { 2 } ~ a _ { z } + \mu _ { 3 } ( a _ { z } ^ { 2 } - \frac { \mathrm { T r } [ ( a _ { z } ) ^ { 2 } ] } { 4 } { \bf 1 } ) + \mu _ { 4 } ( a _ { z } ^ { 3 } - \frac { \mathrm { T r } [ ( a _ { z } ) ^ { 3 } ] } { 4 } { \bf 1 } ) \Big ] ,
$$

Note the appearance of linear term of $a _ { z }$ ，which is absent in the $a _ { \bar { z } }$ for $N = 3$ case (4.46). Now let's repeat the procedure for $N = 3$ case. First the holonomy vector is now

$$
\vec { n } = ( n _ { 2 } , n _ { 1 } , - n _ { 1 } , - n _ { 2 } ) \qquad \mathrm { w i t h } \qquad n _ { i } \in \mathbb { N } , \quad n _ { 2 } > n _ { 1 } .
$$

For the conical surplus, the holonomy condition along the $\phi$ -cycle((2.24) and (2.22)）is equivalent to the following three equations

$$
\Upsilon \left[ ( a _ { z } + a _ { \bar { z } } ) ^ { 2 } \right] = - 2 \sum _ { i = 1 } ^ { 2 } n _ { i } ^ { 2 } , \quad \Upsilon \left[ ( a _ { z } + a _ { \bar { z } } ) ^ { 3 } \right] = 0 , \quad \Upsilon \left[ ( a _ { z } + a _ { \bar { z } } ) ^ { 4 } \right] = 2 \sum _ { i = 1 } ^ { 2 } n _ { i } ^ { 4 }
$$

which determines the charges $\{ Q _ { 2 } , Q _ { 3 } , Q _ { 4 } \}$ in terms of $\{ \mu _ { 3 } , \mu _ { 4 } \}$ and $\tau$ .We will omit the rather long expressons for this result but simply plug them into the free energy (4.34) to get the final answer for the free energy (in terms of a power expansion of $\{ \mu _ { 3 } , \mu _ { 4 } \} _ { \mathrm { ~ , ~ } }$ ）

$$
\begin{array} { l } { { \beta F ^ { \mathrm { C S } } = 4 \pi k \cdot \tau _ { 2 } \cdot \left[ ( n _ { 1 } ^ { 2 } + n _ { 2 } ^ { 2 } ) - \displaystyle \frac { ( n _ { 1 } ^ { 2 } - n _ { 2 } ^ { 2 } ) ^ { 2 } } { 2 } ( \alpha _ { 3 } ^ { 2 } + \bar { \alpha } _ { 3 } ^ { 2 } ) + ( n _ { 1 } ^ { 2 } - n _ { 2 } ^ { 2 } ) ^ { 2 } ( n _ { 1 } ^ { 2 } + n _ { 2 } ^ { 2 } ) \left( \alpha _ { 3 } ^ { 4 } + \bar { \alpha } _ { 3 } ^ { 2 } \right) \right. } } \\ { { \phantom { \beta } } } \\ { { \phantom { \beta } + \left. \displaystyle \frac { \left( 9 n _ { 1 } ^ { 4 } - 8 2 n _ { 1 } ^ { 2 } n _ { 2 } ^ { 2 } + 9 n _ { 2 } ^ { 4 } \right) } { 1 0 0 } ( \alpha _ { 4 } - \bar { \alpha } _ { 4 } ) - \displaystyle \frac { 7 \left( n _ { 1 } ^ { 2 } - n _ { 2 } ^ { 2 } \right) ^ { 2 } \left( n _ { 1 } ^ { 2 } + n _ { 2 } ^ { 2 } \right) } { 1 0 } ( \alpha _ { 3 } ^ { 2 } \alpha _ { 4 } - \bar { \alpha } _ { 3 } ^ { 2 } ) \right. } } \\ { { \phantom { \beta } + \left. \displaystyle \frac { \left( n _ { 1 } ^ { 2 } + n _ { 2 } ^ { 2 } \right) \left( 8 1 n _ { 1 } ^ { 4 } + 8 6 2 n _ { 1 } ^ { 2 } n _ { 2 } ^ { 2 } + 8 1 n _ { 2 } ^ { 4 } \right) } { 2 5 0 0 } ( \alpha _ { 4 } ^ { 2 } + \bar { \alpha } _ { 4 } ^ { 2 } ) \right. } } \\ { { \phantom { \beta } - \left. \displaystyle \frac { \left( n _ { 1 } ^ { 2 } - n _ { 2 } ^ { 2 } \right) ^ { 2 } \left( 8 9 n _ { 1 } ^ { 4 } - 2 n _ { 1 } ^ { 2 } n _ { 2 } ^ { 2 } + 8 9 n _ { 2 } ^ { 4 } \right) } { 1 0 0 } ( \alpha _ { 3 } ^ { 2 } \alpha _ { 4 } ^ { 2 } + \bar { \alpha } _ { 3 } ^ { 2 } \bar { \alpha } _ { 4 } ^ { 2 } ) + \cdots \right] . } } \end{array}
$$

with

$$
\alpha _ { 3 } \equiv { \frac { i } { 2 \tau _ { 2 } } } \mu _ { 3 } \qquad \quad \alpha _ { 4 } \equiv { \frac { i } { 2 \tau _ { 2 } } } \mu _ { 4 }
$$

Now we turn to the black hole. The conditions that solves $\{ Q _ { 2 } , Q _ { 3 } \}$ is now the holonomy condition around the cycle $z \sim z + 2 \pi \tau$ ：：

$$
z + \bar { \tau } a _ { \bar { z } } ) ^ { 2 } \big ] = - 2 \sum _ { i = 1 } ^ { 2 } n _ { i } ^ { 2 } , \quad \mathrm { T r } \left[ ( \tau a _ { z } + \bar { \tau } a _ { \bar { z } } ) ^ { 3 } \right] = 0 , \quad \mathrm { T r } \left[ ( \tau a _ { z } + \bar { \tau } a _ { \bar { z } } ) ^ { 4 } \right] = 2 \sum _ { i = 1 } ^ { 2 } n _ { i } ^ { 4 }
$$

Again we will only write the final answer of the free energy:

$$
\begin{array} { l } { { \displaystyle \beta F ^ { \mathrm { B H } } = 4 \pi k \cdot \frac { \tau _ { 2 } } { | \tau | ^ { 2 } } \cdot \left[ ( n _ { 1 } ^ { 2 } + n _ { 2 } ^ { 2 } ) - \frac { ( n _ { 1 } ^ { 2 } - n _ { 2 } ^ { 2 } ) ^ { 2 } } { 2 } ( \beta _ { 3 } ^ { 2 } + \bar { \beta } _ { 3 } ^ { 2 } ) + ( n _ { 1 } ^ { 2 } - n _ { 2 } ^ { 2 } ) ^ { 2 } ( n _ { 1 } ^ { 2 } + n _ { 2 } ^ { 2 } ) \left( \beta _ { 3 } ^ { 4 } \right. \right. } } \\ { { \displaystyle \phantom { \frac { \beta _ { 1 } } { 1 } } } + \left. \frac { ( 9 n _ { 1 } ^ { 4 } - 8 2 n _ { 1 } ^ { 2 } n _ { 2 } ^ { 2 } + 9 n _ { 2 } ^ { 4 } ) } { 1 0 0 } ( \beta _ { 4 } - \bar { \beta } _ { 4 } ) - \frac { 7 \left( n _ { 1 } ^ { 2 } - n _ { 2 } ^ { 2 } \right) ^ { 2 } ( n _ { 1 } ^ { 2 } + n _ { 2 } ^ { 2 } ) } { 1 0 } ( \beta _ { 3 } ^ { 2 } \beta _ { 4 } - \bar { \beta } _ { 3 } ^ { 2 } \bar { \beta } _ { 4 } ) \right. }  \\  { \displaystyle \phantom { \frac { \beta _ { 1 } } { 1 } } + \left. \frac { ( n _ { 1 } ^ { 2 } + n _ { 2 } ^ { 2 } ) \left( 8 1 n _ { 1 } ^ { 4 } + 8 6 2 n _ { 1 } ^ { 2 } n _ { 2 } ^ { 2 } + 8 1 n _ { 2 } ^ { 4 } \right) } { 2 5 0 0 } ( \beta _ { 4 } ^ { 2 } + \bar { \beta } _ { 4 } ^ { 2 } ) \phantom { \frac { \beta _ { 2 } } { 1 } } } \\  { \displaystyle \phantom { \frac { \beta _ { 1 } } { 1 } } - \frac { ( n _ { 1 } ^ { 2 } - n _ { 2 } ^ { 2 } ) ^ { 2 } \left( 8 9 n _ { 1 } ^ { 4 } - 2 n _ { 1 } ^ { 2 } n _ { 2 } ^ { 2 } + 8 9 n _ { 2 } ^ { 4 } \right) } { 1 0 0 } ( \beta _ { 3 } ^ { 2 } \beta _ { 4 } ^ { 2 } + \bar { \beta } _ { 3 } ^ { 2 } \bar { \beta } _ { 4 } ^ { 2 } ) + \cdots \right] . } \end{array}
$$

with

$$
\beta _ { 3 } \equiv \frac { i | \tau | ^ { 2 } } { 2 \tau _ { 2 } } \frac { \mu _ { 3 } } { \tau ^ { 3 } } \qquad \quad \beta _ { 4 } \equiv \frac { i | \tau | ^ { 2 } } { 2 \tau _ { 2 } } \frac { \mu _ { 4 } } { \tau ^ { 4 } }
$$

We see the free energy of the black hole is exactly the S-transformation

$$
\tau \longmapsto - \frac { 1 } { \tau } , \qquad \mu _ { 3 } \longmapsto \frac { \mu _ { 3 } } { \tau ^ { 3 } } , \qquad \mu _ { 4 } \longmapsto \frac { \mu _ { 4 } } { \tau ^ { 4 } } .
$$

of the conical surplus answer (C.10).

# References

[1] D. Cangemi, M. Leblanc and R. B. Mann， “Gauge Formulation of the Spinning Black Hole in (2+1)-Dimensional Anti-de Sitter Space,” Phys. Rev. D 48 (1993) 3606 [gr-qc/9211013].   
[2] M.Banados, M. Henneaux, C. Teitelboim and J. Zanelli,“Geometry of the (2+1) Black Hole,”Phys.Rev. D 48 (1993) 1506 [gr-qc/9302012].   
[3] S. Carlip and C. Teitelboim，“Aspects of Black Hole Quantum Mechanics and Thermodynamics in (2+1)-Dimensions,” Phys. Rev. D 51 (1995) 622 [gr-qc/9405070].   
[4] A.R. Steif,“Supergeometry of Three-Dimensional Black Holes,” Phys. Rev. D 53 (1996) 5521 [hep-th/9504012].   
[5] J. M. Maldacena and A. Strominger,“AdS(3) black holes and a stringy exclusion principle,” JHEP 9812, 005 (1998) [hep-th/9804085].   
[6] R. Dijkgraaf, J. M. Maldacena, G. W. Moore and E. P. Verlinde,“A Black Hole Farey Tail,” hep-th/0005003.   
[7] S. W. Hawking and D.N. Page,“Thermodynamics of Black Holes in anti-De Sitter Space,” Commun. Math. Phys.87, 577 (1983).   
[8] A.Maloney and E. Witten，“Quantum Gravity Partition Functions in Three Dimensions,” JHEP 1002, 029 (2010) [arXiv:0712.0155 [hep-th].   
[9] M. A. Vasiliev,“Higher Spin Algebras And Quantization On The Sphere And Hyperboloid,” Int. J. Mod.Phys.A 6,1115 (1991).   
10] M.A. Vasiliev,“Higher Spin Gauge Theories in Four-Dimensions, Three-Dimensions, and Two-Dimensions,” Int. J. Mod. Phys. D 5 (1996) 763 [hep-th/9611024].   
11] M. A. Vasiliev,“Higher spin gauge theories: Star product and AdS space,” In \*Shifman, M.A. (ed.): The many faces of the superworld\* 533-610 [hep-th/9910096].   
12] M. A. Vasiliev,“Higher spin symmetries, star product and relativistic equations in AdS space,” hep-th/0002183.   
13] M. P. Blencowe, “A Consistent Interacting Massess Higher Spin Field Theory In D = (2+1)," Class. Quant. Grav. 6, 443 (1989).   
[14] E.Bergshoeff, M. P. Blencowe and K. S. Stelle,“Area Preserving Diffeomorphisms And Higher Spin Algebra,” Commun. Math. Phys.128, 213 (1990).   
[15] S. F. Prokushkin and M. A. Vasiliev,“Higher Spin Gauge Interactions for Massive Matter Fields in 3-D AdS Space-Time,” Nucl. Phys.B 545 (1999) 385 [hep-th/9806236].   
[16] S.Prokushkin and M. A. Vasiliev, “3-D Higher Spin Gauge Theories with Matter,” hep-th/9812242.   
[17] E. S. Fradkin and V. Y. .Linetsky, “Supersymmetric Racah Basis, Family of Infinite Dimensional Superalgebras, SU(infinity+1—Infinity) and Related 2-D Models,” Mod. Phys. Lett. A6(1991) 617.   
[18] A.Achucarro and P.K. Townsend，“A Chern-Simons Action for Three-Dimensional Anti-de Sitter Supergravity Theories,” Phys. Lett. B 180 (1986) 89.   
[19] E. Witten, “(2+1)-Dimensional Gravity as an Exactly Soluble System,” Nucl. Phys. B 311 (1988) 46.   
[20] A. Castro, R. Gopakumar, M. Gutperle and J. Raeymaekers, “Conical Defects in Higher Spin Theories,” JHEP 1202,096 (2012) [arXiv:1111.3381 [hep-th].   
[21] M.Gutperle and P. Kraus，“Higher Spin Black Holes,” JHEP 1105 (2011） 022 [arXiv:1103.4304 [hep-th].   
[22] M. Ammon, M. Gutperle, P. Kraus and E. Perlmutter,“Spacetime Geometry in Higher Spin Gravity,” JHEP 1110 (2011) 053 [arXiv:1106.4788 [hep-th].   
[23] A. Castro,E. Hijano, A. Lepage-Jutier and A. Maloney,“Black Holes and Singularity Resolution in Higher Spin Gravity,” JHEP 1201 (2012) 031 [arXiv:1110.4117 [hep-th]].   
[24] J. R. David, M. Ferlaino and S. P. Kumar,“Thermodynamics of higher spin black holes in 3D,” JHEP 1211,135 (2012)[arXiv:1210.0284 [hep-th]].   
[25] B. Chen, J.Long and Y.-N. Wang,“Phase Structure of Higher Spin Black Hole,” JHEP 1303(2013) 017 [arXiv:1212.6593 [hep-th]].   
[26] M. Ferlaino, T. Hollowood and S. P. Kumar,“Asymptotic symmetries and thermodynamics of higher spin black holes in AdS3,” arXiv:1305.2011 [hep-th].   
[27] J. de Boer and J. I. Jottar，“Thermodynamics of Higher Spin Black Holes in AdS $_ 3$ ”， arXiv:1302.0816 [hep-th].   
[28] A.Perez, D. Tempo and R. Troncoso,“Higher spin black hole entropy in three dimensions,” arXiv:1301.0847 [hep-th].   
[29] A. Perez, D. Tempo and R. Troncoso,“Higher spin gravity in 3D: black holes,global charges and thermodynamics,” arXiv:1207.2844 [hep-th].   
[30] A. Campoleoni, S.Fredenhagen, S.Pfenninger and S. Theisen，“Asymptotic Symmetries of Three-Dimensional Gravity Coupled to Higher-Spin Fields,” JHEP 1011 (2010) 007 [arXiv:1008.4744 [hep-th].   
[31] M. R. Gaberdiel and R. Gopakumar，“Minimal Model Holography,” J. Phys. A 46 (2013）214002 [arXiv:1207.6697 [hep-th].   
[32] M. Ammon,M. Gutperle,P. Kraus and E. Perlmutter,“Black Holes in Three Dimensional Higher Spin Gravity: a Review,” arXiv:1208.5182 [hep-th].   
[33] M.Banados，“Three-DimensionalQuantumGeometryandBlackHoles,” hep-th/9901148.   
[34] M. Henneaux and S. -J. Rey，“Nonlinear $W _ { \infty }$ as Asymptotic Symmetry of Three-Dimensional Higher Spin Anti-de Sitter Gravity,” JHEP 1012 (2010） 007 [arXiv:1008.4579 [hep-th].   
[35] M. R. Gaberdiel and T. Hartman,“Symmetries of Holographic Minimal Models,” JHEP 1105 （2011) 031 [arXiv:1101.2910 [hep-th].   
[36] A. Campoleoni， S. Fredenhagen and S. Pfenninger， “Asymptotic W-Symmetries in Three-Dimensional Higher-Spin Gauge Theories,”JHEP 1109 (2011） 113 [arXiv:1107.0290 [hep-th].   
[37] O. Coussaert, M. Henneaux and P. van Driel,“The Asymptotic Dynamics of ThreeDimensional Einstein Gravity with a Negative Cosmological Constant,” Class. Quant. Grav.12 (1995) 2961 [gr-qc/9506019].   
[38] V. G. Drinfeld and V. V. Sokolov,“Lie Algebras and Equations of Korteweg-De Vries Type,” J. Sov.Math.30 (1984) 1975.   
[39] C. N. Pope,L. J. Romans and X. Shen,“W(infinity) And The Racah-wigner Algebra,” Nucl. Phys.B 339,191 (1990).   
[40] H. S. Tan,“Exploring Three-Dimensional Higher-Spin Supergravity Based on $S l ( N | N -$ 1) Chern-Simons Theories,” JHEP 1211 (2012) 063 [arXiv:1208.2277 [hep-th].   
[41] S. Datta and J. R. David, “Supersymmetry of Classical Solutions in Chern-Simons Higher Spin Supergravity,” JHEP 1301 (2013) 146 [arXiv:1208.3921 [hep-th].   
[42] Y. Hikida,“Conical Defects and $\mathcal { N } = ~ 2$ Higher Spin Holography,” arXiv:1212.4124 [hep-th].   
[43] B. Chen, J. Long and Y. -N. Wang,“Conical Defects, Black Holes and Higher Spin (Super-)Symmetry,” JHEP 1306 (2013) 025 [arXiv:1303.0109 [hep-th].   
[44] A. Campoleoni and S. Fredenhagen,“On the Higher-Spin Charges of Conical Defects,” arXiv:1307.3745 [hep-th].   
[45] A. Campoleoni, T. Prochazka and J. Raeymaekers,“A Note on Conical Solutions in 3D Vasiliev Theory,” JHEP 1305 (2013) 052 [arXiv:1303.0880 [hep-th]].   
[46] J.P. Serre, Chapter VII, “A Course in Arithmetic,” Springer (1973).   
[47] P.Kraus and E. Perlmutter,“Partition Functions of Higher Spin Black Holes and Their CFT Duals,” JHEP 1111 (2011) 061 [arXiv:1108.2567 [hep-th].   
[48] M. R. Gaberdiel, T. Hartman and K. Jin,“Higher Spin Black Holes from CFT,” JHEP 1204 (2012) 103 [arXiv:1203.0015 [hep-th]].   
[49] M. R. Gaberdiel,K. Jin and E. Perlmutter，“Probing Higher Spin Black Holes from CFT,” arXiv:1307.2221 [hep-th].   
[50] T.Regge and C. Teitelboim,“Role of Surface Integrals in the Hamiltonian Formulation of General Relativity,” Annals Phys. 88 (1974) 286.   
[51] M. Banados,R. Canto and S. Theisen,“The Action for higher spin black holes in three dimensions,” JHEP 1207, 147 (2012) [arXiv:1204.5105 [hep-th]].   
[52] A. Campoleoni, S.Fredenhagen, S. Pfenninger and S. Theisen，“Towards Metric-Like Higher-Spin Gauge Theories in Three Dimensions,” J. Phys. A 46 (2013） 214017 [arXiv:1208.1851 [hep-th].   
[53] G. Compre and W. Song,“W Symmetry and Integrability of Higher Spin Black Holes,” arXiv:1306.0014 [hep-th].   
[54] J.Balog, L. Feher, L. O'Raifeartaigh, P. Forgacs and A. Wipf,“Toda Theory and W Algebra from a Gauged Wznw Point of View,” Annals Phys. 203 (1990) 76.   
[55] R.Dijkgraaf,“Chiral Deformations of Conformal Field Theories,” Nucl. Phys.B 493 (1997) 588 [hep-th/9609022].   
[56] P. Kraus,“Lectures on black holes and the AdS $_ 3$ /CFT $^ 2$ correspondence,” Lect. Notes Phys. 755,193(2008) [arXiv:hep-th/0609074].   
[57] E.Witten,“Three-Dimensional Gravity Revisited,” arXiv:0706.3359 [hep-th].   
[58] S.Banerjee,A. Castro, S. Hellerman， E. Hijano,A. Lepage-Jutier，A. Maloney and S. Shenker,“Smoothed Transitions in Higher Spin AdS Gravity,” Class. Quant.Grav. 30（2013）104001 [arXiv:1209.5396 [hep-th].   
[59] J. Mei, R-x. Miao, and E.D. Skvotsov, private communication.   
[60] G. Compere, J. I. Jottar and W. Song,“Observables and Microscopic Entropy of Higher Spin Black Holes,” arXiv:1308.2175 [hep-th].   
[61] J. Manschot and G. W. Moore,“A Modern Farey Tail,” Commun. Num. Theor. Phys. 4 （2010) 103 [arXiv:0712.0573 [hep-th]].