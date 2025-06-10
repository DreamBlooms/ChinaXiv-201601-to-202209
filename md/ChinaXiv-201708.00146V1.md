# Perturbations of W CFTs

Matthias R. Gaberdiel $a$ , Kewang Jin $a$ ， and Wei Li $b$ （20

$\boldsymbol { a }$ Institut fir Theoretische Physik, ETH Zurich, CH-8093 Zirich, Switzerland gaberdiel@itp.phys.ethz.ch， jinke@itp.phys.ethz.ch

$\boldsymbol { b }$ Max-Planck-Institut fir Gravitationsphysik, Albert-Einstein-Institut, Am Mühlenberg 1, 14476 Golm, Germany wei.li@aei.mpg.de

# Abstract

The holographic duals of higher spin theories on AdS $^ 3$ are described by the large $N$ limit of a family of minimal model CFTs, whose symmetry algebra is equivalent to ${ \mathcal W } _ { \infty } [ \lambda ]$ . We study perturbations of these limit theories,and show that they possess a marginal symmetry-preserving perturbation that describes switching on the $\textstyle { \frac { 1 } { N } }$ corrections. We also test our general results for the specific cases of $\lambda = 0 , 1$ ,where free field realisations are available.

# Contents

1 Introduction

# 2The theory at $\lambda = 0$ （20 3

2.1 The free fermion description 4   
2.2 OPEs and commutation relations 5   
2.3 The U(1) coset 5   
2.4 The continuous orbifold viewpoint 8

# 3 The theory at $\lambda = 1$ （204号 9

3.1The higher spin currents 10   
3.2The primary basis. 11

# Deforming the theory 11

4.1 The perturbation in the 't Hooft limit 12   
4.2 The analysis for the non-linear ${ \mathcal W } _ { \infty } [ \lambda ]$ case 15   
4.3 The perturbing field at $\lambda = 0$ 16   
4.4 The perturbing field at $\lambda = 1$ 18

# 5The effect of the perturbation 19

5.1 The structure of the perturbation theory 20   
5.2 The mixing matrix 24   
5.3 The eigenvalue problem . 25   
5.4 The CFT interpretation 27

# ）Conclusions 30

A The free fermion theory at $\lambda = 0$ 31   
B The free boson theory at $\lambda = 1$ 33   
C Explicit mixing matrices 33   
D The eigenproblem of a scalar Jacobi matrix 34

# 1 Introduction

The proposed dualities relating a higher spin theory on AdS $d { + 1 }$ to vector-like nearly free conformal field theories in $d$ dimensions constitute simplified versions of the AdS/CFT correspondence that are under very good quantitative control. As such they may open the way towards understanding their inner workings. The prototype example was proposed some years ago by Klebanov $\&$ Polyakov [1],see also [2,3,4, 5] for earlier work and [6] for a subsequent generalisation. It relates a Vasiliev higher spin theory [7] on AdS $_ 4$ to the large （204号 $N$ limit of the O( $N$ ） vector model in 3 dimensions. Compelling evidence for this duality was recently found by comparing correlation functions in [8,9], as well as through the work [10,11] that determined interesting general constraints on the structure of the correlation functions based on symmetry considerations. More recently, these dualities were further generalised to a one-parameter family of (in general) parity-breaking theories in [12,13,14].

In a somewhat independent development, a lower dimension analogue of this duality was proposed in [15], relating a higher spin theory on AdS $_ 3$ [16,17] to the large $N$ limit of a family of minimal model 2d CFTs. One of the guiding principles in proposing this duality was the observation that the asymptotic algebra of the higher spin theory on AdS $^ 3$ is described by a （20 ${ \mathcal W } _ { \infty } [ \lambda ]$ algebra [18,19, 20, 21], which therefore largely controls the dual CFT. This proposal was subsequently checked in various ways [22, 23].

In the 3d/2d case, the underlying symmetry algebra ${ \mathcal W } _ { \infty } [ \lambda ]$ is characterised, in addition to the central charge (that corresponds geometrically to the size of the AdS space)，by a continuous parameter $\lambda$ that controls the higher spin interactions.1 From the dual minimal model perspective, $\lambda$ is identified with

$$
\lambda = { \frac { N } { N + k } } \ , \qquad \mathrm { w h i l e } \quad c = ( N - 1 ) \Bigl [ 1 - { \frac { N ( N + 1 ) } { ( N + k ) ( N + k + 1 ) } } \Bigr ] \ ,
$$

where $k$ is the level of the coset model. In particular, $\lambda$ therefore becomes a continuous parameter in the 't Hooft limit,in which $c \sim N ( 1 - \lambda ^ { 2 } )$ . However, from the viewpoint of the （204号 ${ \mathcal W } _ { \infty } [ \lambda ]$ symmetry algebra, $\lambda$ and $c$ are arbitrary (finite) parameters, and there is a priori no need to take $c \to \infty$ in order for $\lambda$ to become continuous.

It is then natural to ask whether theories corresponding to different values of $\lambda$ (and $c$ )are connected by continuous deformations. For example, one may wonder whether there exist exactly marginal operators that change $\lambda$ continuously (while preserving the $\mathcal { W } _ { \infty }$ symmetry) without affecting $c$ . Or there could be deformations that change both $\lambda$ and $c$ infinitesimally. Given that the $\mathcal { W } _ { N , k }$ minimal models do not possess any exactly marginal operators, one may suspect that the first option is not possible,and indeed there is a fairly general argument - due to Stefan Fredenhagen — that implies that such deformations cannot exist.(This will be briefly reviewed in section 5.1.） However, we find evidence that a marginal deformation exists,at least in the 't Hooft limit,that modifies both $\lambda$ and $c$ . In fact, it can be identified with a perturbation that introduces $\textstyle { \frac { 1 } { N } }$ and $\textstyle { \frac { 1 } { k } }$ corrections such that to first order $\lambda$ does not change.

More specifically, we characterise quite generally the perturbing operators that preserve the $\mathcal { W } _ { \infty }$ symmetry to first order,and find that there is a one-parameter family of operators with this property. They are uniquely characterised by their eigenvalues of the spin-3 generator. Quite remarkably, the $h = 1$ descendant of the light state corresponding to $( \boxed { } ; \boxed { } )$ has this property in the ’t Hooft limit and therefore defines (together with its conjugate operator) an interesting perturbing field. We analyse its properties, first for the special cases $\lambda = 0 , 1$ ， where free field realisations are available,² and then for general $\lambda$ ， using conformal perturbation theory. The conformal perturbation theory is quite intricate since, in the 't Hooft limit,there are infinitely many fields of the same conformal dimension,and hence we need to analyse an infinitely degenerate case. However, because of the structure of the fusion rules,the perturbation problem has a lot of structure,and we can identify at least certain qualitative features.

The paper is organised as follows. We begin with reviewing the free field realisations of the special ${ \mathcal W } _ { \infty } [ \lambda ]$ theories at $\lambda = 0$ (section 2) and $\lambda = 1$ (section 3). In particular, we show that the singlet sector of $N$ complex free fermions defines a $\mathcal { W } _ { \infty } [ 0 ]$ algebra at $c = N - 1$ ， while the singlet sector of $k$ complex free bosons lead to $\mathcal { W } _ { \infty } [ 1 ]$ at $c = 2 k$ .While both of these statements are certainly expected, they had not been established at finite $c$ before; in particular, we confirm that the structure constants of the ${ \mathcal W } _ { \infty } [ \lambda ]$ algebras agree precisely with the prediction of [23] for these values of $\lambda$ and $c$ .In section 4 we then study the conditions a perturbing operator must satisfy in order to preserve the $\mathcal { W } _ { \infty }$ algebra at first order. This is first done in the 't Hooft limit,and then for finite $c$ , using the full quantum version of the ${ \mathcal W } _ { \infty } [ \lambda ]$ algebra. We give strong evidence that the $h = 1$ descendant of the light state corresponding to $( \boxed { } ; \boxed { } )$ has this property in the 't Hooft limit,and confirm this statement explicitly for the special cases $\lambda = 0$ and $\lambda = 1$ (where the statement remains true even at finite $c$ ). In section 5 we then study the effect of the perturbation by this field (and its conjugate) in the 't Hooft limit,and identify the perturbed spectrum with what is obtainedfromthinialmodelperspectieuonswitchingonacrtaincombinatioof $\textstyle { \frac { 1 } { N } }$ and $\textstyle { \frac { 1 } { k } }$ corrections. Finally, we conclude in section 6. There are four appendices where some of the more technical material has been collected together.

# 2 The theory at $\lambda = 0$ （204号

The simplest explicit realisation of the ${ \mathcal W } _ { \infty } [ \lambda ]$ algebra exists at $\lambda = 0$ ， where we can describe the theory in terms of free fermions. We shallater also comment on how this description is related to the continuous orbifold point of view proposed in [24].

# 2.1 The free fermion description

Let us consider the theory of $N$ free complex fermions $\psi ^ { i }$ and $\psi ^ { * i }$ ， $i = 1 , \ldots , N$ with action

$$
S _ { 0 } = \int d ^ { 2 } z \left( \psi ^ { * i } \bar { \partial } \psi ^ { i } + \bar { \psi } ^ { i } \partial \bar { \psi } ^ { * i } \right) .
$$

The corresponding equations of motion are

$$
\bar { \partial } \psi ^ { i } = \bar { \partial } \psi ^ { * i } = 0 ~ ,
$$

and the OPEs take the form

$$
\psi ^ { i } ( z _ { 1 } ) \psi ^ { * j } ( z _ { 2 } ) \sim \frac { \delta ^ { i j } } { ( z _ { 1 } - z _ { 2 } ) } \ ,
$$

with similar expressions for the right movers $\psi ^ { i }$ and $\psi ^ { * j }$ .We shall always consider only states that are singlets with respect to the global $\mathrm { S U } ( N )$ action.

The free theory has the conserved spin- $s$ chiral currents [25, 26, 27] (the expressions for the anti-chiral currents are analogous)

$$
W ^ { s } = n ( s ) \sum _ { k = 0 } ^ { s - 1 } ( - 1 ) ^ { k } { \binom { s - 1 } { k } } ^ { 2 } \partial ^ { s - 1 - k } \psi ^ { * i } \partial ^ { k } \psi ^ { i } \ ,
$$

where the sum over $i$ is implicit,and we choose the normalisation convention

$$
n ( s ) = { \frac { [ ( s - 1 ) ! ] ^ { 2 } } { ( 2 s - 2 ) ! } } \ .
$$

Explicitly, for small values of $s$ , these current are then

$$
\begin{array} { r c l } { { J } } & { { \equiv } } & { { W ^ { 1 } = \psi ^ { * i } \psi ^ { i } } } \\ { { T } } & { { \equiv } } & { { W ^ { 2 } = \displaystyle \frac { 1 } { 2 } ( \partial \psi ^ { * i } \psi ^ { i } - \psi ^ { * i } \partial \psi ^ { i } ) } } \\ { { } } & { { } } & { { } } \\ { { W } } & { { \equiv } } & { { W ^ { 3 } = \displaystyle \frac { 1 } { 6 } \Big ( \partial ^ { 2 } \psi ^ { * i } \psi ^ { i } - 4 \partial \psi ^ { * i } \partial \psi ^ { i } + \psi ^ { * i } \partial ^ { 2 } \psi ^ { i } \Big ) } } \\ { { } } & { { } } & { { } } \\ { { U } } & { { \equiv } } & { { W ^ { 4 } = \displaystyle \frac { 1 } { 2 0 } \Big ( \partial ^ { 3 } \psi ^ { * i } \psi ^ { i } - 9 \partial ^ { 2 } \psi ^ { * i } \partial \psi ^ { i } + 9 \partial \psi ^ { * i } \partial ^ { 2 } \psi ^ { i } - \psi ^ { * i } \partial ^ { 3 } \psi ^ { i } \Big ) ~ . } } \end{array}
$$

# 2.2 OPEs and commutation relations

It follows from the OPEs given in Appendix A that the modes of the stress energy tensor $T$ satisfy a Virasoro algebra with central charge $c = N$ ，

$$
\left[ L _ { m } , L _ { n } \right] = ( m - n ) L _ { m + n } + \frac { N } { 1 2 } m \left( m ^ { 2 } - 1 \right) \delta _ { m , - n } \ ,
$$

while $J$ isa $\mathrm { U } ( 1 )$ -current whose modes satisfy

$$
[ J _ { m } , J _ { n } ] = N m \delta _ { m , - n } , \qquad [ L _ { m } , J _ { n } ] = - n J _ { m + n } .
$$

It also follows from (A.5) and (A.6) that $W$ is neither U(1)- nor Virasoro-primary. Indeed, converted into modes, these OPEs imply that the commutation relations take the form

$$
[ J _ { m } , W _ { n } ] = 2 m L _ { m + n } ~ , \qquad [ L _ { m } , W _ { n } ] = ( 2 m - n ) W _ { m + n } + { \textstyle { \frac { 1 } { 6 } } } m ( m ^ { 2 } - 1 ) J _ { m + n } ~ .
$$

The OPE of $W$ with itself (A.7) then leads to

$$
\begin{array} { r c l } { { W _ { m } , W _ { n } \Big ] } } & { { = } } & { { \frac { 2 N } { 3 6 0 } m ( m ^ { 2 } - 1 ) ( m ^ { 2 } - 4 ) \delta _ { m , - n } + \frac { 1 } { 1 5 } ( m - n ) ( 2 m ^ { 2 } + 2 n ^ { 2 } - m n - 8 ) { \cal L } } } \\ { { } } & { { } } & { { } } \\ { { } } & { { } } & { { + 2 ( m - n ) U _ { m + n } . } } \end{array}
$$

Note that this algebra is linear, i.e. the commutators (2.13) do not involve the normal ordered （20 $\Lambda ^ { ( 4 ) } = : L L$ : term that generically appears in this commutator.

# 2.3 The U(1） coset

The free fermion theory does not directly describe ${ \mathcal W } _ { \infty } [ \lambda ]$ for any value of $\lambda$ ， since it contains a spin 1 current $J$ ，and hence leads to $\mathcal { W } _ { 1 + \infty }$ . Furthermore,in the above basis (in which the generators are bilinears in the fermions,and hence the OPEs do not contain any non-linear term） the generators $W ^ { s }$ with $s \geq 2$ do not close among themselves,as follows for example from (A.6). There is, however,a different basis in which $\mathcal { W } _ { \infty } [ 0 ]$ appears as a subalgebra of the free fermion theory. In this basis, the generators are not just bilinears in the free fermions,and as a consequence the algebra will turn out to be non-linear.

The basic idea for finding this basis is inspired by the coset construction, and in effect, the resulting construction is what the coset by the U(1)-current $J$ would amount to. We can recursively construct currents $\tilde { W } ^ { s }$ of spin $s = 2 , 3 , \ldots$ that are primary with respect to $J$ . In terms of modes this then means that the modes $\tilde { W } _ { m } ^ { s }$ commute with $J _ { n }$ .Because of the Jacobi identity, the same is then also true for the commutators of $\tilde { W } ^ { s _ { 1 } }$ and $\tilde { W } ^ { s _ { 2 } }$ ,i.e. the $\tilde { W } ^ { s }$ generators form a closed algebra. In the following we shallconstruct the first few of these generators explicitly; we can then determine their commutation relations, and show that they generate indeed $\mathcal { W } _ { \infty } [ 0 ]$ at $c = N - 1$

# 2.3.1 The coset generators

Let us first define the generators $\tilde { W } _ { s }$ recursively. For $s = 2$ ， we get

$$
{ \tilde { T } } = T - { \frac { 1 } { 2 N } } : J J : \ ,
$$

or in terms of states

$$
\tilde { L } _ { - 2 } \Omega = L _ { - 2 } \Omega - { \frac { 1 } { 2 N } } J _ { - 1 } J _ { - 1 } \Omega \ .
$$

It is easy to see that (2.15) is U(1)-primary, i.e. $J _ { n } \tilde { L } _ { - 2 } \Omega = 0$ for $n \geq 0$ . The OPEs of $\tilde { T }$ with （204号 $J$ and itself are then

$$
\tilde { T } ( z _ { 1 } ) J ( z _ { 2 } ) \sim 0 \ , \qquad \tilde { T } ( z _ { 1 } ) \tilde { T } ( z _ { 2 } ) \sim \frac { ( N - 1 ) / 2 } { ( z _ { 1 } - z _ { 2 } ) ^ { 4 } } + \frac { 2 \tilde { T } ( z _ { 2 } ) } { ( z _ { 1 } - z _ { 2 } ) ^ { 2 } } + \frac { \tilde { T } ^ { \prime } ( z _ { 2 } ) } { ( z _ { 1 } - z _ { 2 } ) } \ ,
$$

i.e. the new modes ${ \tilde { L } } _ { n }$ define a Virasoro algebra (2.10) with central charge $N - 1$ (instead of （204号 $N$ ),and commute with the modes $J _ { n }$

For $s = 3$ ，the $\mathrm { U } ( 1 )$ -primary generator is

$$
{ \tilde { W } } = W - \frac { 2 } { N } : J T : + \frac { 2 } { 3 N ^ { 2 } } : J J J : { , }
$$

or in terms of states

$$
\tilde { W } _ { - 3 } \Omega = W _ { - 3 } \Omega - \frac { 2 } { N } J _ { - 1 } L _ { - 2 } \Omega + \frac { 2 } { 3 N ^ { 2 } } J _ { - 1 } J _ { - 1 } J _ { - 1 } \Omega \ .
$$

Moreover, $\tilde { W }$ is also primary with respect to $\tilde { T }$ ，i.e.

$$
\tilde { T } ( z _ { 1 } ) \tilde { W } ( z _ { 2 } ) \sim { \frac { 3 \tilde { W } ( z _ { 2 } ) } { ( z _ { 1 } - z _ { 2 } ) ^ { 2 } } } + { \frac { \tilde { W } ^ { \prime } ( z _ { 2 } ) } { ( z _ { 1 } - z _ { 2 } ) } } \ ,
$$

which in particular does not involve the current $J$ any longer,in contrast to the situation in (A.6),and in agreement with the above general argument. Incidentally, the simplest way to compute (2.19) is to use the general formula

$$
\tilde { T } ( z _ { 1 } ) \tilde { W } ( z _ { 2 } ) = \sum _ { n \in \mathbb { Z } } ( z _ { 1 } - z _ { 2 } ) ^ { - n - 2 } V \bigl ( \tilde { L } _ { n } \tilde { W } _ { - 3 } \Omega , z _ { 2 } \bigr ) \ ,
$$

where $V ( \psi , z )$ denotes the vertex operator associated to $\psi$ , together with the mode expansion

of $\tilde { T }$ ，

$$
\tilde { L } _ { n } = L _ { n } - \frac { 1 } { 2 N } \sum _ { l \in \mathbb { Z } } : J _ { n - l } J _ { l } : \ .
$$

We also need the explicit formula for the U(1)-primary state at $h = 4$ , which equals

$$
\begin{array} { r c l } { { \tilde { U } _ { - 4 } \Omega } } & { { = } } & { { U _ { - 4 } \Omega - \displaystyle \frac { 1 } { 5 N } J _ { - 1 } J _ { - 3 } \Omega - \displaystyle \frac { 3 } { 2 0 N } J _ { - 2 } J _ { - 2 } \Omega - \displaystyle \frac { 3 } { N } J _ { - 1 } W _ { - 3 } \Omega + \displaystyle \frac { 3 } { N ^ { 2 } } J _ { - 1 } J _ { - 1 } L _ { - 1 } } } \\ { { } } & { { } } & { { - \displaystyle \frac { 3 } { 4 N ^ { 3 } } J _ { - 1 } J _ { - 1 } J _ { - 1 } J _ { - 1 } \Omega - \displaystyle \frac { ( 2 1 - \frac { 1 5 } { N } ) } { ( 5 N + 1 7 ) } ( \tilde { L } _ { - 2 } \tilde { L } _ { - 2 } - { \scriptstyle \frac { 3 } { 5 } \tilde { L } _ { - 4 } } ) \Omega ~ , } } \end{array}
$$

where the last term is required in order to make it also Virasoro primary with respect to $\tilde { T }$

Continuing in this manner, we can recursively construct U(1)-primary felds $\tilde { W } ^ { s }$ that generate a closed algebra. We can furthermore recursively make them Virasoro primary (with respect to $\tilde { T }$ )，and thus the resulting ${ \cal W } _ { \infty }$ algebra has the spin content $2 , 3 , 4 , \ldots$ Following the general logic of [23], it must therefore be isomorphic to ${ \mathcal W } _ { \infty } [ \lambda ]$ for some value of $\lambda$ . In the following we shall show that the relevant value of $\lambda$ is $\lambda = 0$ . Note that the classical analysis of [2O] only tells us that this has to be true to leading order in $1 / c$ ; now we have shown that it is actually true even at fnite $c = N - 1$ ：

# 2.3.2 Determining $\lambda$

In order to determine the value of the parameter $\lambda$ , it is sufficient to calculate two commutators. Indeed, in the conventions of [23] and [28], we have³

$$
\begin{array} { r c l } { { \displaystyle \left[ \tilde { W } _ { m } , \tilde { W } _ { n } \right] ~ = } } & { { \displaystyle \frac { N _ { 3 } c } { 1 4 4 } m ( m ^ { 2 } - 1 ) ( m ^ { 2 } - 4 ) \delta _ { m , - n } + \displaystyle \frac { N _ { 3 } } { 1 2 } ( m - n ) ( 2 m ^ { 2 } + 2 n ^ { 2 } - m n - 1 ) } } \\ { { } } & { { } } & { { + 2 ( m - n ) \tilde { U } _ { m + n } + \displaystyle \frac { 4 0 N _ { 3 } } { ( 5 c + 2 2 ) } ( m - n ) \tilde { \Lambda } _ { m + n } , } } \\ { { } } & { { } } & { { } } \\ { { \displaystyle \left[ \tilde { U } _ { m } , \tilde { U } _ { n } \right] ~ = } } & { { \displaystyle \frac { N _ { 4 } c } { 4 3 2 0 } m ( m ^ { 2 } - 1 ) ( m ^ { 2 } - 4 ) ( m ^ { 2 } - 9 ) \delta _ { m , - n } + \cdots ~ , } } \end{array}
$$

and the parameter $\gamma ^ { 2 }$ ，which determines the coefficient of $U$ in the $W W$ OPE [23] and characterises the $\mathcal { W }$ algebra uniquely, is then given by

$$
\gamma ^ { 2 } = \frac { 8 9 6 } { 7 5 } \frac { N _ { 4 } } { N _ { 3 } ^ { 2 } } .
$$

Using the analogue of (2.2O), we have worked out the first few terms of the $\tilde { W } \tilde { W }$ OPE to be

$$
\begin{array} { r c l } { { \tilde { \cal V } ( z _ { 2 } ) } } & { { \sim } } & { { \displaystyle \frac { 2 ( N - 1 ) ( N - 2 ) } { 3 N } \frac { 1 } { ( z _ { 1 } - z _ { 2 } ) ^ { 6 } } + \frac { 4 ( N - 2 ) } { N } \frac { \tilde { \cal T } ( z _ { 2 } ) } { ( z _ { 1 } - z _ { 2 } ) ^ { 4 } } + \frac { 2 ( N - 2 ) } { N } \frac { \tilde { \cal T } ^ { \prime } ( z _ { 1 } ) } { ( z _ { 1 } - z _ { 2 } ) ^ { 6 } } } } \\ { { } } & { { } } & { { \displaystyle + \frac { 4 \tilde { \cal U } ( z _ { 2 } ) + \frac { 3 } { 5 } \tilde { \cal T } ^ { \prime \prime } ( z _ { 2 } ) } { ( z _ { 1 } - z _ { 2 } ) ^ { 2 } } + \frac { 6 4 ( N - 2 ) } { 5 N ( N - 1 ) } \frac { \tilde { \cal N } ^ { ( 4 ) } ( z _ { 2 } ) } { ( z _ { 1 } - z _ { 2 } ) ^ { 2 } } + { \mathcal O } \left( \frac { 1 } { z _ { 1 } - z _ { 2 } } \right) , \quad \quad ( 3 ) \equiv } } \end{array}
$$

where $\tilde { \Lambda } ^ { ( 4 ) }$ is the composite field $\begin{array} { r } { \tilde { \Lambda } ^ { ( 4 ) } = : \tilde { T } \tilde { T } : - \frac { 3 } { 1 0 } \partial ^ { 2 } \tilde { T } } \end{array}$ . Comparing with the central term in (2.23) and using that $c = N - 1$ ，we conclude that

$$
N _ { 3 } = \frac { 4 } { 5 } \frac { N - 2 } { N } ~ .
$$

In order to compute $N _ { 4 }$ , we have also determined the central term in the $\tilde { U } \tilde { U }$ OPE,i.e.

$$
\tilde { U } _ { 4 } \tilde { U } _ { - 4 } \Omega = \frac { 9 ( N - 1 ) ( N - 2 ) ( N - 3 ) ( N + 1 ) } { N ^ { 2 } ( 5 N + 1 7 ) } \Omega ,
$$

which gives

$$
N _ { 4 } = { \frac { 5 4 } { 7 } } { \frac { ( N - 2 ) ( N - 3 ) ( N + 1 ) } { N ^ { 2 } ( 5 N + 1 7 ) } } \ .
$$

Thus $\gamma ^ { 2 }$ becomes

$$
= { \frac { 1 4 4 ( N + 1 ) ( N - 3 ) } { ( 5 N + 1 7 ) ( N - 2 ) } } = \left. { \frac { 6 4 ( c + 2 ) ( \lambda - 3 ) \bigl ( c ( \lambda + 3 ) + 2 ( 4 \lambda + 3 ) ( \lambda - 1 ) \bigr ) } { ( 5 c + 2 2 ) ( \lambda - 2 ) \bigl ( c ( \lambda + 2 ) + ( 3 \lambda + 2 ) ( \lambda - 1 ) \bigr ) } } \right| _ { \lambda = 0 , c = \beta } .
$$

i.e. it agrees with the general formula of [23, eq. (2.15)] at $\lambda = 0$ and $c = N - 1$ . This proves that the free fermion construction indeed gives rise to $\mathcal { W } _ { \infty } [ \lambda = 0 ]$ at $c = N - 1$

We should mention that this argument relies on the assumption that the only consistent $\mathcal { W } _ { \infty }$ algebras that are generated by one field of each integer spin $s \geq 2$ are described by ${ \mathcal W } _ { \infty } [ \lambda ]$ . While this statement has not been established in complete generality, there is very convincing evidence,based on the analysis of [29], that this is indeed the case.4

# 2.4 The continuous orbifold viewpoint

It was argued in [24] that the theory at $\lambda = 0$ can be described in terms of a continuous orbifold. More specifically, one considers the affine $\mathfrak { s i } ( N ) _ { 1 }$ theory, and takes the orbifold by the action of the group SU $( N ) / \mathbb { Z } _ { N }$ . In the untwisted sector this amounts to restricting the

affine level 1 theory to those states that are SU $( N ) / \mathbb { Z } _ { N }$ singlets. From this point of view, the higher spin currents then arise from the Casimir operators; in particular,the stress energy tensor of the continuous orbifold theory equals

$$
T ^ { \mathrm { c o } } = \frac { 1 } { 2 ( N + 1 ) } \sum _ { a } : J ^ { a } J ^ { a } : ,
$$

where $J ^ { a }$ are the currents of the $\mathfrak { s i } ( N ) _ { 1 }$ theory, while the spin 3 generator is

$$
W ^ { \mathrm { c o } } = \frac { 1 } { 3 ( N + 1 ) ( N + 2 ) } \sum _ { a b c } d _ { a b c } : J ^ { a } J ^ { b } J ^ { c } : { , }
$$

where $d _ { a b c }$ is the totally symmetric invariant tensor. The higher spin generators are similarly associated to the higher order Casimir operators.

Actually, the relation between this continuous orbifold description and the free fermion construction from above is fairly immediate. The theory of $N$ complex fermions has a $\hat { \mathfrak { u } } ( N ) _ { 1 }$ algebra, whose generators are

$$
J ^ { i j } = \psi ^ { * i } \psi ^ { j } \ .
$$

This current algebra contains the $\hat { \mathfrak { u } } ( 1 )$ subalgebra generated by $\begin{array} { r } { J = \sum _ { i } \psi ^ { * i } \psi ^ { i } } \end{array}$ and the coset by this $\hat { \mathfrak { u } } ( 1 )$ algebra (see section 2.3) leads to an affine $\mathfrak { s i } ( N ) _ { 1 }$ theory at $c = N - 1$ . Indeed, the $\mathfrak { s i } ( N ) _ { 1 }$ currents are simply given by, see [30, chapter 15.5.6]

$$
J ^ { a } = \sum _ { i j } \psi ^ { * i } t _ { i j } ^ { a } \psi ^ { j } \ ,
$$

where $t _ { i j } ^ { a }$ are the generators of $\mathfrak { s u } ( N )$ in the fundamental representation. In both theories we are furthermore considering only singlets with respect to the global SU $( N )$ action,and thus the spectra agree precisely (in the untwisted sector). The twisted sectors are then completed by consistency, and thus should also match. (It might be interesting to understand the twisted sectors more directly from the free fermion point of view; this could be closely related to the discussion of [31] in one dimension higher.)

Using the translation between the free fermion and the $\mathfrak { s i } ( N ) _ { 1 }$ description, it was shown in [30,chapter 15.5.6] that the stress energy tensor of (2.31） agrees indeed with $\tilde { T }$ from (2.14). We have also checked that (2.32) and (2.17) similarly agree.

# 3 The theory at $\lambda = 1$

The other simple realisation of the ${ \mathcal W } _ { \infty } [ \lambda ]$ algebra arises for $\lambda = 1$ ， for which there is a description in terms of $k$ complex free bosons.

# 3.1 The higher spin currents

The theory of $k$ complex free bosons has spin- $s$ currents [32]

$$
W ^ { s } ( z ) = m ( s ) \sum _ { l = 1 } ^ { s - 1 } \frac { ( - 1 ) ^ { l } } { ( s - 1 ) } \binom { s - 1 } { l } \binom { s - 1 } { s - l } \partial ^ { l } \phi ^ { j } \partial ^ { s - l } \bar { \phi } ^ { j } ,
$$

where the sum over $j = 1 , \dots , k$ is implicit, and we choose the normalization factor

$$
m ( s ) = \frac { 2 ^ { s - 3 } s ! } { ( 2 s - 3 ) ! ! } \ .
$$

Explicitly, the first few currents are

$$
\begin{array} { r c l } { { { \cal T } ( z ) } } & { { \equiv } } & { { W ^ { 2 } ( z ) = - : \partial \phi ^ { j } \partial \bar { \phi } ^ { j } : } } \\ { { { \cal W } ( z ) } } & { { \equiv } } & { { W ^ { 3 } ( z ) = - 2 : ( \partial \phi ^ { j } \partial ^ { 2 } \bar { \phi } ^ { j } - \partial ^ { 2 } \phi ^ { j } \partial \bar { \phi } ^ { j } ) : } } \\ { { { \cal U } ( z ) } } & { { \equiv } } & { { W ^ { 4 } ( z ) = - \displaystyle \frac { 1 6 } { 5 } : ( \partial \phi ^ { j } \partial ^ { 3 } \bar { \phi } ^ { j } - 3 \partial ^ { 2 } \phi ^ { j } \partial ^ { 2 } \bar { \phi } ^ { j } + \partial ^ { 3 } \phi ^ { j } \partial \bar { \phi } ^ { j } ) : . } } \end{array}
$$

Using the OPEs of the currents

$$
\partial \phi ^ { i } ( z _ { 1 } ) \partial \bar { \phi } ^ { j } ( z _ { 2 } ) \sim - \frac { \delta ^ { i j } } { ( z _ { 1 } - z _ { 2 } ) ^ { 2 } }
$$

we can work out the OPEs of higher spin currents,and one finds for the stress energy tensor

$$
T ( z _ { 1 } ) T ( z _ { 2 } ) = { \frac { k } { ( z _ { 1 } - z _ { 2 } ) ^ { 4 } } } + { \frac { 2 T ( z _ { 2 } ) } { ( z _ { 1 } - z _ { 2 } ) ^ { 2 } } } + { \frac { \partial T ( z _ { 2 } ) } { ( z _ { 1 } - z _ { 2 } ) } } + \cdots ,
$$

thus showing that the central charge equals $c = 2 k$ ，as expected. Some of the other OPEs are worked out explicitly in Appendix B, see eqs. (B.1) - (B.5); converted into modes, they give rise to the commutation relations

$$
{ \begin{array} { r l } { [ L _ { m } , L _ { n } ] } & { = { \mathrm { \it ~ ( m - n ) } } L _ { m 1 n } + { \frac { k } { 6 } } m { \mathrm { \it ~ ( m ^ { 2 } - 1 ) } } \delta _ { m 1 n } } \\ { [ L _ { m } , W _ { n } ] } & { = { \mathrm { \it ~ ( 2 m - n ) } } W _ { m + n } } \\ { [ L _ { m } , U _ { n } ] } & { = { \mathrm { \it ~ ( 3 m - n ) } } U _ { m + n } + { \frac { 3 2 } { 5 } } m { \mathrm { \it ~ ( m ^ { 2 } - 1 ) } } L _ { m + n } } \\ { W _ { m } , W _ { n } ] } & { = { \mathrm { \it ~ 2 ( m - n ) } } U _ { m + n } + { \frac { 3 } { 5 } } { \mathrm { \it ~ ( m - n ) } } { \mathrm { \it ~ ( 2 m ^ { 2 } + 2 n ^ { 2 } - m n - 8 ) } } L _ { m + n } } \\ & { \quad + { \frac { 2 k } { 1 5 } } m { \mathrm { \it ~ ( m ^ { 2 } - 1 ) } } { \mathrm { \it ~ ( m ^ { 2 } - 4 ) } } \delta _ { m + n } } \\ { [ W _ { m } , U _ { n } ] } & { = { \mathrm { \it ~ ( 3 m - 2 n ) } } X _ { m + n } + { \frac { 6 4 } { 3 5 } } { \mathrm { \it ~ ( 5 m ^ { 3 } - 5 m ^ { 2 } n + 3 m n ^ { 2 } - 1 7 m - n ^ { 3 } + 9 n ) } } W _ { n } } \\ { [ U _ { m } , U _ { n } ] } & { = { \mathrm { \it ~ \frac { 6 4 } { 5 2 5 } } } k m { \mathrm { \it ~ ( m ^ { 2 } - 1 ) ( m ^ { 2 } - 4 ) } } ( m ^ { 2 } - 9 ) \delta _ { m + n } + \cdots \ , } \end{array} }
$$

where we have only worked out the leading term for the $[ U , U ]$ commutator.

# 3.2 The primary basis

The $W ^ { s }$ as defined in (3.1) are not primaries: while $W ^ { 3 }$ is still a primary (see (3.9))， the spin-4 field $U$ is already not primary (see eq. (3.1O)). In order to identify the $\lambda$ value of the resulting algebra, it is convenient to go to a primary basis. For instance, the spin-4 current in the primary basis is

$$
\tilde { U } = U - { \frac { 1 9 2 } { 1 0 k + 2 2 } } \Lambda ^ { ( 4 ) } \ ,
$$

where $\Lambda ^ { ( 4 ) } \left( = : T T : - \textstyle { \frac { 3 } { 1 0 } } \partial ^ { 2 } T \right)$ is the familiar composite field, see eq. (2.26). In terms of this field, the relevant OPEs then become

$$
\begin{array} { r c l } { { W ( z _ { 1 } ) W ( z _ { 2 } ) } } & { { = } } & { { \displaystyle { \frac { 1 6 k } { z _ { 1 2 } ^ { 6 } } } + 4 8 \left[ \frac { T } { z _ { 1 2 } ^ { 4 } } + \frac { 1 } { 2 } \frac { \partial T } { z _ { 1 2 } ^ { 3 } } + \frac { 3 } { 2 0 } \frac { \partial ^ { 2 } T } { z _ { 1 2 } ^ { 2 } } + \frac { 1 } { 3 0 } \frac { \partial ^ { 3 } T } { z _ { 1 2 } } \right] } } \\ { { } } & { { } } & { { \displaystyle { + \frac { 4 } { z _ { 1 2 } ^ { 2 } } \left[ \tilde { U } + \frac { 1 9 2 } { 1 0 k + 2 2 } \Lambda ^ { ( 4 ) } \right] + \frac { 2 } { z _ { 1 2 } } \left[ \partial \tilde { U } + \frac { 1 9 2 } { 1 0 k + 2 2 } \partial \Lambda ^ { ( 4 ) } \right] ~ , } } } \\ { { } } & { { } } & { { \displaystyle { \tilde { U } ( z _ { 1 } ) \tilde { U } ( z _ { 2 } ) ~ = } } } & { { \displaystyle { \frac { 3 0 7 2 ( 2 k + 2 ) k } { 1 0 k + 2 2 } \frac { 1 } { z _ { 1 2 } ^ { 8 } } + \cdots ~ . } } } \end{array}
$$

Comparing as before with eqs. (2.23) and (2.24) we thus conclude that

$$
N _ { 3 } = { \frac { 4 8 } { 5 } } \ , \qquad N _ { 4 } = { \frac { 9 2 1 6 } { 7 } } { \frac { c + 2 } { 5 c + 2 2 } } \ ,
$$

where we have used that $c = 2 k$ . Thus the $\gamma ^ { 2 }$ parameter from eq.(2.25） becomes

$$
\gamma ^ { 2 } = \frac { 5 1 2 ( c + 2 ) } { 3 ( 5 c + 2 2 ) } = \left. \frac { 6 4 ( c + 2 ) ( \lambda - 3 ) ( c ( \lambda + 3 ) + 2 ( 4 \lambda + 3 ) ( \lambda - 1 ) ) } { ( 5 c + 2 2 ) ( \lambda - 2 ) ( c ( \lambda + 2 ) + ( 3 \lambda + 2 ) ( \lambda - 1 ) ) } \right| _ { \lambda = 1 } ~ .
$$

Hence the free boson theory generates indeed $\mathcal { W } _ { \infty } [ \lambda = 1 ]$ at $c = 2 k$ . Moreover, the seemingly non-linear $\mathcal { W } _ { \infty } [ \lambda = 1 ]$ algebra of eq. (3.14) is in fact linear upon going to the original nonprimary basis (3.1), in agreement with the analysis of [20].

# 4Deforming the theory

We are interested in perturbing the ${ \mathcal W } _ { \infty } [ \lambda ]$ algebra by a marginal operator that preserves the current symmetry, i.e. by a perturbation that leaves all currents of ${ \mathcal W } _ { \infty } [ \lambda ]$ holomorphic. From the analysis of [33],see also [34],we know that to first order in perturbation theory

this will be the case provided that

$$
\operatorname * { l i m } _ { \epsilon  0 } \oint _ { | w - z | = \epsilon } d w \Phi ( w , \bar { w } ) W ^ { s } ( z ) = 0 .
$$

Since we know that the OPE of $W ^ { s }$ with $\Phi$ is of the form

$$
W ^ { s } ( z ) \Phi ( w , \bar { w } ) = \sum _ { l } ( W _ { l } ^ { s } \Phi ) ( w , \bar { w } ) ( z - w ) ^ { - l - s }
$$

the requirement that $W ^ { s }$ remains holomorphic means that

$$
\mathcal { N } _ { s } \equiv \sum _ { l = 0 } ^ { s - 1 } \frac { ( - 1 ) ^ { l } } { l ! } ( L _ { - 1 } ) ^ { l } W _ { - s + 1 + l } ^ { s } \Phi = 0 \qquad s \geq 2 ~ .
$$

(Here we have assumed that $\Phi$ is ${ \mathcal W } _ { \infty } [ \lambda ]$ primary.） Given that the $\mathcal { W } _ { N , k }$ minimal models are not expected to have any such perturbation — the integrable perturbation by the field $( 0 ; \mathrm { a d j } )$ is relevant and induces the RG flow from $k  k - 1$ — we can only hope to find a solution to this problem either at generic values of $( \lambda , c )$ of the ${ \mathcal W } _ { \infty } [ \lambda ]$ theory,or in the ’t Hooft limit of the $\mathcal { W } _ { N , k }$ models. Remarkably, there is a simple perturbing field $\Phi$ that seems to satisfy (4.3) in the 't Hooft limit, as we shall now explain.

# 4.1 The perturbation in the 't Hooft limit

We begin by analysing the condition (4.3) in the ’t Hooft limit,i.e.in the limit of the minimal models $\mathcal { W } _ { N , k }$ where we take $N , k \to \infty$ while keeping

$$
\lambda = { \frac { N } { N + k } }
$$

fixed. It was shown in [23] that with the central charge

$$
c _ { N , k } = ( N - 1 ) \bigg [ 1 - \frac { N ( N + 1 ) } { ( N + k ) ( N + k + 1 ) } \bigg ]
$$

the chiral algebra $\mathcal { W } _ { N , k } \cong \mathcal { W } _ { \infty } \lfloor \lambda \rfloor$ , even at finite $N$ and $k$ . In the 't Hooft limit $c _ { N , k } \to \infty$ ， and hence the non-linear terms in ${ \mathcal W } _ { \infty } [ \lambda ]$ drop out. Let us denote the eigenvalues of the （204号 ${ \mathcal W } _ { \infty } [ \lambda ]$ primary state $\Phi$ by

$$
W _ { 0 } ^ { t } \Phi = w ^ { t } \Phi \qquad t \geq 2 ~ .
$$

By construction $\mathcal { N } _ { 2 } = 0$ provided that $\Phi$ is marginal, i.e. $w ^ { 2 } \equiv h = 1$ . On the other hand, the $\mathcal { N } _ { s }$ with $s \geq 3$ are generically non-trivial null-vectors. In order to confirm that they are

indeed null we need to show that they are annihilated by all positive ${ \mathcal W } _ { \infty } [ \lambda ]$ modes. Using the commutation relations $\left[ L _ { m } , W _ { n } ^ { s } \right] = ( ( s - 1 ) m - n ) W _ { m + n } ^ { s }$ one can easily check that

$$
L _ { n } { \mathcal { N } } _ { s } = 0 \qquad n \geq 1 ~ , ~ s \geq 3 ~ .
$$

Thus it is sufficient to require

$$
W _ { n } ^ { s } \mathcal { N } _ { t } = 0 \ , \qquad s , t \geq 3 \ , \ n \geq 1 \ .
$$

We now consider the special case of (4.8) with $s = 3$ and $n = t - 1$ . Then using the structure of the commutation relations of ${ \mathcal W } _ { \infty } [ \lambda ]$ ，in particular the fact that the highest spin mode that appears in the commutator of $W ^ { 3 }$ with $\boldsymbol { W } ^ { t }$ is $W ^ { t + 1 }$ , (4.8) leads to an equation for the eigenvalue $w ^ { t + 1 }$ in terms of the eigenvalues $w ^ { s }$ with $s \leq t$ (as well as the structure constants of the algebra). For example, from (4.8) with $s = 3$ and $n = t - 1 = 2$ with $t = 3 , 4 , 5$ we obtain

$$
\begin{array} { r c l } { { w ^ { 4 } } } & { { = } } & { { \displaystyle \frac { 3 } { 4 } \biggl ( N _ { 3 } + ( w ^ { 3 } ) ^ { 2 } \biggr ) } } \\ { { w ^ { 5 } } } & { { = } } & { { \displaystyle \frac { 1 } { 1 5 } \biggl ( 1 0 w ^ { 4 } w ^ { 3 } + 8 \frac { N _ { 4 } } { N _ { 3 } } w ^ { 3 } \biggr ) } } \\ { { w ^ { 6 } } } & { { = } } & { { \displaystyle \frac { 1 } { 9 } \biggl ( 5 ( w ^ { 4 } ) ^ { 2 } + 3 0 n _ { 4 4 } w ^ { 4 } - 3 N _ { 4 } \biggr ) ~ , } } \end{array}
$$

where $N _ { 3 }$ ， $N _ { 4 }$ and $n _ { 4 4 }$ are the structure constants of the $\mathcal { W } _ { \infty } [ \lambda ]$ algebra,which equal, in our conventions,

$$
N _ { 3 } = \frac { 1 6 } { 5 } \sigma ^ { 2 } ( \lambda ^ { 2 } - 4 ) \ , \quad N _ { 4 } = \frac { 3 8 4 } { 3 5 } \sigma ^ { 4 } ( \lambda ^ { 2 } - 4 ) ( \lambda ^ { 2 } - 9 ) \ , \quad n _ { 4 4 } = \frac { 8 } { 1 5 } \sigma ^ { 2 } \left( \lambda ^ { 2 } - 1 9 \right)
$$

where $\sigma$ is a normalisation constant.

Thus this subset of conditions fixes the eigenvalues of $\Phi$ up to an arbitrary choice of $w ^ { 3 }$ One might wonder whether some of the other conditions in (4.8) would then fix $w ^ { 3 }$ ,but this does not seem to be the case.5 In fact there is an intuitive reason why this should be so: the set of conditions (4.8） with $s = 3$ and $n = t - 1$ is equivalent to the set of conditions with （20 $t = 3$ ， $n = 1 , 2$ and $s = 3 , 4 , \ldots$ . On the other hand, these latter conditions are equivalent to the statement that ${ \mathcal { N } } _ { 3 }$ is indeed a null-vector,i.e. to the statement that the $W ^ { 3 }$ -current remains holomorphic to first order in perturbation. But since the whole ${ \mathcal W } _ { \infty } [ \lambda ]$ algebra is generated by repeated OPEs from $W ^ { 3 }$ , this should then imply that the whole ${ \mathcal W } _ { \infty } [ \lambda ]$ algebra remains holomorphic to first order, i.e.(4.8) is satisfied for all $s , t \geq 3$ and $n \geq 1$ ：

This suggests that a one-parameter family of representations preserve the ${ \mathcal W } _ { \infty } [ \lambda ]$ algebra to first order in perturbation theory. One might then wonder whether one of the coset fields would satisfy these constraints in the 't Hooft limit. Quite remarkably, this does seem to be the case. To see how this goes, recall that the $( \boxed { } ; \boxed { } )$ representation becomes indecomposable in the 't Hooft limit,i.e. its structure is [22]

$$
\begin{array} { r l r } { L _ { 0 } = } & { { } } & { 0 } \end{array}
$$

![](images/1938e0572fb9ece372f23e1ba5935642dc961fa11565e74fff6063cf11298198.jpg)

Furthermore, in a suitable rescaling limit (see Section 5), the arrow between $\phi$ and $\omega$ disappears，and $\phi$ becomes a primary field of conformal dimension $h = 1$ . Its eigenvalues are simply

$$
w ^ { s } ( \phi ) = w ^ { s } ( ⨏ ; 0 ) + w ^ { s } ( 0 ; ⨏ ) ,
$$

where $w ^ { s } ( \Sigma ; 0 )$ and $w ^ { s } ( 0 ; \sqsupset )$ are the eigenvalues of $W _ { 0 } ^ { s }$ on the highest weight states of $( \boxed { \cdot } ; 0 )$ and $( 0 ; \boxed { \dag } )$ ， respectively. In the conventions of [28] the eigenvalues of these representations are

$$
{ \begin{array} { r l r l r l } { { \vec { \jmath } } ; 0 ) } & { = } & { { \frac { 1 } { 2 } } ( 1 + \lambda ) } & { \quad w ^ { 2 } ( 0 ; \bigtriangledown ) } & { = } & { { \frac { 1 } { 2 } } ( 1 - \lambda ) } \\ { { \vec { \jmath } } ; 0 ) } & { = } & { { \frac { 2 } { 3 } } i \sigma \left( 1 + \lambda \right) ( 2 + \lambda ) } & { \quad w ^ { 3 } ( 0 ; \bigtriangledown ) } & { = } & { - { \frac { 2 } { 3 } } i \sigma \left( 1 - \lambda \right) ( 2 - \lambda ) } \\ { { \vec { \jmath } } ; 0 ) } & { = } & { - { \frac { 4 } { 5 } } \sigma ^ { 2 } \left( 1 + \lambda \right) ( 2 + \lambda ) ( 3 + \lambda ) } & { \quad w ^ { 4 } ( 0 ; \bigtriangledown ) } & { = } & { - { \frac { 4 } { 5 } } \sigma ^ { 2 } \left( 1 - \lambda \right) ( 2 - \lambda ) ( 3 + \lambda ) } \end{array} }
$$

and

$$
\begin{array} { r c l } { { w ^ { 5 } ( \boxdot { \Sigma } ; 0 ) } } & { { = } } & { { - \frac { 3 2 } { 3 5 } i \sigma ^ { 3 } ( 1 + \lambda ) ( 2 + \lambda ) ( 3 + \lambda ) ( 4 + \lambda ) ~ , } } \\ { { w ^ { 5 } ( 0 ; \boxdot { \Sigma } ) } } & { { = } } & { { \frac { 3 2 } { 3 5 } i \sigma ^ { 3 } ( 1 - \lambda ) ( 2 - \lambda ) ( 3 - \lambda ) ( 4 - \lambda ) ~ , } } \\ { { w ^ { 6 } ( \boxdot { \Sigma } ; 0 ) } } & { { = } } & { { \frac { 6 4 } { 6 3 } \sigma ^ { 4 } ( 1 + \lambda ) ( 2 + \lambda ) ( 3 + \lambda ) ( 4 + \lambda ) ( 5 + \lambda ) ~ , } } \\ { { w ^ { 6 } ( 0 ; \boxdot { \Sigma } ) } } & { { = } } & { { \frac { 6 4 } { 6 3 } \sigma ^ { 4 } ( 1 - \lambda ) ( 2 - \lambda ) ( 3 - \lambda ) ( 4 - \lambda ) ( 5 - \lambda ) ~ , } } \end{array}
$$

from which we deduce

$$
w ^ { 2 } ( \phi ) = 1 \ , \qquad w ^ { 3 } ( \phi ) = 4 i \sigma \lambda \ , \qquad w ^ { 4 } ( \phi ) = - { \frac { 4 8 } { 5 } } \sigma ^ { 2 } ( 1 + \lambda ^ { 2 } ) \ ,
$$

and

$$
w ^ { 5 } ( \phi ) = - \frac { 1 2 8 } { 7 } i \sigma ^ { 3 } \lambda ( 5 + \lambda ^ { 2 } ) , \quad w ^ { 6 } ( \phi ) = \frac { 6 4 0 } { 2 1 } \sigma ^ { 4 } ( 8 + 1 5 \lambda ^ { 2 } + \lambda ^ { 4 } ) .
$$

Together with the values for the structure constants (4.12)， it is then straightforward to check that eqs. (4.9) -(4.11) are indeed satisfied. This gives strong support to the assertion that $\phi$ indeed satisfies all the requirements in (4.8). We shall also be able to confirm this using different methods for the special cases of $\lambda = 0$ and $\lambda = 1$ ， see sections 4.3 and 4.4 below.

# 4.2 The analysis for the non-linear ${ \mathcal W } _ { \infty } [ \lambda ]$ case

The above analysis was done in the 't Hooft limit,but we may ask whether the situation for the ${ \mathcal W } _ { \infty } [ \lambda ]$ algebra at finite $c$ would be different. We have repeated the analysis of (4.8) for this case,using the explicit form of the quantum algebra ${ \mathcal W } _ { \infty } [ \lambda ]$ as given in [23, Appendix A] (see also [29]). While there are $\textstyle { \frac { 1 } { c } }$ corrections, e.g. (4.9) and (4.10) become

$$
\begin{array} { r c l } { { w ^ { 4 } } } & { { = } } & { { \displaystyle \frac { 3 } { 4 } \Big ( \frac { 5 ( c - 2 ) } { 5 c + 2 2 } N _ { 3 } + ( w ^ { 3 } ) ^ { 2 } \Big ) } } \\ { { w ^ { 5 } } } & { { = } } & { { \displaystyle \frac { 1 } { 1 5 } \Big ( 1 0 w ^ { 4 } w ^ { 3 } + \frac { 5 6 ( c - 6 ) } { ( 7 c + 1 1 4 ) } \frac { N _ { 4 } } { N _ { 3 } } w ^ { 3 } \Big ) ~ , } } \end{array}
$$

we have found that the general structure is largely unmodified, i.e. there continues to be a one-parameter family of such perturbing fields (that are characterised by the $W _ { 0 } ^ { 3 }$ eigenvalue $w ^ { 3 }$ ). In order to find the analogue of $\phi$ in this context we have demanded in addition that the representation generated from $\Phi$ has the same character as that of $\phi$ ，i.e.

$$
\chi _ { \phi } = { \frac { q } { ( 1 - q ) ^ { 2 } } } \prod _ { s = 2 } ^ { \infty } \prod _ { n = s } ^ { \infty } { \frac { 1 } { ( 1 - q ^ { n } ) } } = q ^ { 1 } \Big ( 1 + 2 q + 4 q ^ { 2 } + 7 q ^ { 3 } + \cdots \Big ) \ .
$$

In particular, this means that there are only two linearly independent states at the first descendant level, i.e. the representation possesses many null states,e.g. a null state of the form $( W _ { - 1 } ^ { 4 } + \alpha W _ { - 1 } ^ { 3 } + \beta L _ { - 1 } ) \Phi = 0$ , etc. Then there are only six solutions for $w ^ { 3 }$ , namely the roots of the sextic equation

$$
\begin{array} { r l } & { 2 1 0 0 0 ( 5 c + 2 2 ) ^ { 2 } ( c - 1 ) N _ { 3 } ^ { 3 } N _ { 4 } - 2 5 3 1 2 5 ( 5 c + 2 2 ) ( c ^ { 2 } - 4 ) N _ { 3 } ^ { 5 } } \\ & { - 5 6 2 5 ( 2 5 9 c ^ { 3 } + 2 1 7 0 c ^ { 2 } + 8 1 8 0 c + 9 7 5 2 ) N _ { 3 } ^ { 4 } ( w ^ { 3 } ) ^ { 2 } - 1 2 5 4 4 ( c + 2 ) ( 5 c + 2 2 ) ^ { 2 } N _ { 4 } ^ { 2 } \left( w ^ { 3 } \right) ^ { 2 } } \\ & { \phantom { = } + 8 4 0 0 ( 5 c + 2 2 ) ( 3 1 c ^ { 2 } + 1 4 1 c + 2 6 6 ) N _ { 3 } ^ { 2 } N _ { 4 } \left( w ^ { 3 } \right) ^ { 2 } } \\ & { - 1 1 2 5 ( 5 c + 2 2 ) ( 3 5 c ^ { 2 } - 1 9 2 c - 5 2 4 ) N _ { 3 } ^ { 3 } \left( w ^ { 3 } \right) ^ { 4 } + 8 4 0 ( 5 c - 1 7 ) ( 5 c + 2 2 ) ^ { 2 } N _ { 3 } N _ { 4 } \left( w ^ { 3 } \right) ^ { 5 } } \\ & { - 2 2 5 ( 5 c + 2 2 ) ( 5 c ^ { 2 } + 3 2 c + 4 4 ) N _ { 3 } ^ { 2 } \left( w ^ { 3 } \right) ^ { 6 } = 0 \ . } \end{array}
$$

In the large $c$ limit,plugging in the values for $N _ { 3 }$ and $N _ { 4 }$ from (4.12)，we obtain the solutions

$$
w ^ { 3 } = \pm 4 i \sigma \lambda \quad \mathrm { o r } \quad w ^ { 3 } = \pm 4 i \sigma ( \lambda + 2 ) \quad \mathrm { o r } \quad w ^ { 3 } = \pm 4 i \sigma ( \lambda - 2 ) \ .
$$

Note that the first two solutions correspond precisely to $\phi$ and its conjugate $\phi ^ { * }$ (i.e. the corresponding state in $( \overline { { \Pi } } ; \overline { { \Pi } } )$ ). We don't know the interpretation for the other four solutions.

It is instructive to compare these general results to what happens at the special points （204号 $\lambda = 0$ and $\lambda = 1$ where we have free field realisations of the algebra, see Section 2 and 3, respectively. In particular, for these cases we can construct the analogue of $\phi$ explicitly, and show that it preserves indeed the full ${ \mathcal W } _ { \infty } [ \lambda ]$ algebra to first order. Let us first consider the case of $\lambda = 0$ ·

# 4.3 The perturbing field at $\lambda = 0$ （20

In the free fermion theory there is only one U(1)-primary field of conformal dimension $( 1 , 1 )$ in the untwisted sector, namely

$$
\Phi = \left( \bar { \psi } ^ { * i } \psi ^ { i } \right) \left( \bar { \psi } ^ { j } \psi ^ { * j } \right) - \frac { 1 } { N } J \bar { J } = \left( \bar { \psi } ^ { * i } \psi ^ { i } \right) \left( \bar { \psi } ^ { j } \psi ^ { * j } \right) - \frac { 1 } { N } \left( \psi ^ { * i } \psi ^ { i } \right) \left( \bar { \psi } ^ { * j } \bar { \psi } ^ { j } \right) ,
$$

where $J$ and $J$ are the holomorphic and anti-holomorphic U(1)-currents, respectively. In terms of the continuous orbifold description it corresponds to the field

$$
\Phi = \sum _ { a } J ^ { a } { \bar { J } } ^ { a } \ ,
$$

as one confirms using the identity of the representation matrices in the fundamental representation

$$
\sum _ { a } t _ { i j } ^ { a } t _ { k l } ^ { a } = \delta _ { i l } \delta _ { j k } - \frac { 1 } { N } \delta _ { i j } \delta _ { k l } .
$$

The perturbation by this field leaves the ${ \mathcal { W } } _ { \infty } [ \lambda = 0 ]$ currents holomorphic to first order. One way to see this is to consider the perturbed action

$$
S = S _ { 0 } + g \int d ^ { 2 } z \Phi ( z , \bar { z } ) \ ,
$$

where $S _ { 0 }$ was defined in (2.1). This perturbation modifies the equations of motion of the free theory (2.2) to

$$
\bar { \partial } \psi ^ { i } = g ( \bar { \psi } ^ { i } { \cal K } + { \frac { 1 } { \cal N } } \psi ^ { i } \bar { \cal J } ) \qquad \bar { \partial } \psi ^ { * i } = - g ( \bar { \psi } ^ { * i } \bar { \cal K } + { \frac { 1 } { \cal N } } \psi ^ { * i } \bar { \cal J } ) \ ,
$$

where $K$ and $K$ are defined as

$$
K \equiv \bar { \psi } ^ { * j } \psi ^ { j } \ , \qquad \bar { K } \equiv \psi ^ { * j } \bar { \psi } ^ { j } \ .
$$

It is easy to check that the $\mathrm { U } ( 1 )$ current remains conserved, $\partial J = 0$ ， and the same is true for the stress energy tensor $T$ (and hence for $\tilde { T }$ ）since

$$
\begin{array} { l l l } { { \bar { \partial } T } } & { { = } } & { { 2 g \left[ - ( \bar { \psi } ^ { * } \cdot \partial \psi ) \bar { K } - ( \partial \psi ^ { * } \cdot \bar { \psi } ) K + \partial ( K \bar { K } ) \right] } } \\ { { } } & { { = } } & { { 2 g \left[ - g ( \psi ^ { * } \cdot \psi ) K \bar { K } + g ( \psi ^ { * } \cdot \psi ) \bar { K } K \right] = 0 , } } \end{array}
$$

where the dot‘.’is a shorthand for the sum over $i$ . On the other hand, one shows that the higher spin currents $W ^ { s }$ (and hence $\tilde { W } ^ { s }$ ） are only preserved to first order in $g$ ，

$$
\begin{array} { r c l } { { \bar { \partial } W ^ { s } } } & { { = } } & { { \displaystyle - g \sum _ { k = 0 } ^ { s - 1 } \sum _ { p = 1 } ^ { s - 1 - k } \sum _ { q = 0 } ^ { p } ( - 1 ) ^ { k } \binom { s - 1 } { k , p - q , q } [ \binom { s - 1 } { k } - ( - 1 ) ^ { p } \binom { s - 1 } { k + p } ] } } \\ { { } } & { { } } & { { \times ( \partial ^ { s - 1 - k - p } \psi ^ { * } \cdot \partial ^ { p - q } \bar { \psi } ) ( \partial ^ { q } \bar { \psi } ^ { * } \cdot \partial ^ { k } \psi ) , } } \end{array}
$$

where

$$
{ \binom { s - 1 } { k , p - q , q } } = \frac { ( s - 1 ) ! } { k ! ( p - q ) ! q ! ( s - 1 - k - p ) ! } .
$$

Since the sum over $p$ starts with $p = 1$ ， we can apply the equations of motion at least once more, and find that $\bar { \partial } W ^ { s } = \mathcal { O } ( g ^ { 2 } )$

Thus our perturbation by $\Phi$ should satisfy the conditions (4.8) from above. In fact, using Wick's theorem repeatedly, one finds that

$$
\tilde { W } _ { 0 } \Phi = 0 ~ .
$$

This solves indeed (4.25) since,at $\lambda = 0$ ， we have the relation

$$
\frac { N _ { 4 } } { N _ { 3 } ^ { 2 } } = \frac { 2 5 3 1 2 5 ( c ^ { 2 } - 4 ) } { 2 1 0 0 0 ( 5 c + 2 2 ) ( c - 1 ) } = \frac { 6 7 5 } { 5 6 } \frac { c ^ { 2 } - 4 } { ( 5 c + 2 2 ) ( c - 1 ) } = \frac { 7 5 } { 8 9 6 } \left. \gamma ^ { 2 } \right| _ { \lambda = 0 } \ ,
$$

where $\gamma ^ { 2 }$ was defined in (2.25) and (2.30). Furthermore, $\Phi$ corresponds to the solution with $w ^ { 3 } = \pm 4 i \sigma \lambda | _ { \lambda = 0 } = 0$ , i.e. it describes in the 't Hooft limit precisely the left-right symmetric combination of the feld $\phi$

While the perturbation by $\Phi$ in (4.27） preserves the ${ \mathcal { W } } _ { \infty } [ \lambda = 0 ]$ currents to frst order in perturbation theory, it does not do so to higher orders. One explicit way to see this is to use (4.34) to determine

$$
\bar { \partial } \tilde { W } ^ { 3 } = 6 g ^ { 2 } \big [ J \partial ( \bar { K } K ) - ( \partial J ) \bar { K } K \big ] \ ,
$$

which does not vanish. We have also confirmed this conclusion by a direct perturbative analysis.

Another way to arrive at the same conclusion is to observe that it follows from the analysis of [35] that $\Phi$ ， given by (4.28)， is not exactly marginal. Indeed, a current-current deformation is only exactly marginal if all chiral currents that appear in the sum lie in an abelian subalgebra,and similarly for the anti-chiral currents. However,this is clearly not the case for (4.28). Thus, in particular, the $T$ component of the stress energy tensor does not remain holomorphic to higher order in perturbation theory. The same conclusion can also be reached by observing that in the free fermion description we have the identification

$$
\left( \sqcup ; \sqcup \right) \cong \left( 0 ; 0 \right) \oplus \left( \mathrm { a d j } ; 0 \right) ,
$$

as follows from [24, eq. (2.10)]. The perturbing field corresponds to the second representation, （204号 $( \mathrm { a d j } ; 0 )$ ，which is not exactly marginal.

# 4.4 The perturbing field at $\lambda = 1$ （20

For the free boson theory at $\lambda = 1$ , the only real singlet field (in the untwisted sector) that has conformal dimension $( 1 , 1 )$ is

$$
\Phi _ { 1 } = \partial \phi ^ { j } \bar { \partial } \bar { \phi } ^ { j } + \bar { \partial } \phi ^ { j } \partial \bar { \phi } ^ { j } \ .
$$

It is proportional to the Lagrangian itself, and thus switching on this feld only changes the ‘radius’ of the bosons; in particular it therefore does not break the ${ \mathcal { W } } _ { \infty } [ \lambda = 1 ]$ symmetry. (It also cannot deform $\lambda$ since otherwise ${ \mathcal W } _ { \infty } [ \lambda ]$ algebras with $\lambda \neq 1$ would also have a free boson realisation and hence must be linear, in contradiction with the results of [20].6)

Thus we should expect that $\Phi _ { 1 }$ is again a solution of (4.25). Using Wick's theorem， we have determined the $W _ { 0 } ^ { 3 }$ eigenvalue of $\Phi _ { 1 }$ ; in fact, the two terms in $\Phi _ { 1 }$ (that are complex conjugates of one another） have opposite $W _ { 0 } ^ { 3 }$ eigenvalue, and thus $\Phi _ { 1 }$ is only an eigenvector of $( W _ { 0 } ^ { 3 } ) ^ { 2 }$ with eigenvalue

$$
( w ^ { 3 } ) ^ { 2 } = 1 6 \ .
$$

Together with (3.16) one can easily check that (4.25) is indeed satisfied for all values of （204号 $c$ ， i.e. all values of $k$ . We should also mention that comparing (3.16) to (4.12） it follows that $\sigma ^ { 2 } = - 1$ in the conventions of Section 3. Thus (4.41） corresponds again to the first eigenvalue in (4.26） at $\lambda = 1$ ,i.e. $\Phi _ { 1 }$ can be identified with the left-right symmetric version of $\phi + \phi ^ { * }$ in the 't Hooft limit.

The fact that the perturbing field is trivial can also be understood from the point of view of the minimal models. At $\lambda = 1$ , all eigenvalues of the fields of the form $( 0 ; \Lambda _ { - } )$ vanish,and hence the analogue of [24, eq. (2.10)] is

$$
( \Lambda _ { 1 } ; \Lambda _ { 2 } ) \cong ( \Lambda _ { 1 } ; 0 ) ~ .
$$

The analogue of (4.39) is therefore

$$
\left( \left[ \bigcirc ; \bigsqcup \right) \cong \left( \bigsqcup ; 0 \right) , \right.
$$

i.e. the perturbing field agrees indeed with the ‘scalar’ field $\partial \phi ^ { j } \partial \phi ^ { j }$ 业

# 5 The effect of the perturbation

As we have seen in Section 4.1, in the 't Hooft limit the $\phi$ ‘descendant’of the $( \boxed { } ; \boxed { } )$ representation (which decouples from the ground state in the 't Hooft limit） defines a perturbation that leaves the full set of ${ \mathcal W } _ { \infty } [ \lambda ]$ currents holomorphic at first order in perturbation theory. Thus we can ask how the perturbation by the corresponding left-right symmetric field $\Phi$ (i.e. the combination of $\phi$ with its right-moving analogue) changes the underlying ${ \mathcal W } _ { \infty } [ \lambda ]$ theory.

Since the perturbation only has the desired properties in the 't Hooft limit, we need to be careful about how precisely the limit is defined. Let us denote by $\omega$ the ground state of the $( \boxed { } ; \boxed { } )$ representation in the $\mathcal { W } _ { N , k }$ minimal model, and by $\omega ^ { * }$ its conjugate, i.e. the ground state of the $( \overline { { \square } } ; \overline { { \sqcup } } )$ representation. At finite $( N , k )$ we define, following [36]

$$
\Phi = \frac { 1 } { 2 h _ { \omega } } \bar { L } _ { - 1 } L _ { - 1 } \omega \ , \qquad \omega = \frac { 1 } { 2 h _ { \omega } } \bar { L } _ { 1 } L _ { 1 } \Phi \ ,
$$

and then take the $N  \infty$ limit, keping as before $\begin{array} { r } { \lambda = \frac { N } { N + k } } \end{array}$ fixed,seq.(.4).7 （20 $\omega$ and $\Phi$ have unit norm in the limit, but become disconnected in the sense that

$$
\bar { L } _ { - 1 } L _ { - 1 } \omega = 0 \ , \qquad \bar { L } _ { 1 } L _ { 1 } \Phi = 0 \ .
$$

In particular, $\Phi$ is therefore a primary non-descendant feld,and it makes sense to perturb with it. Actually, since we should perturb with a real field we shal consider the perturbation by $P = \Phi + \Phi ^ { * }$ ，where

$$
\Phi = \operatorname * { l i m } _ { \stackrel { N  \infty } { \lambda \mathrm { ~ f i x e d ~ } } } \frac { 1 } { 2 h _ { \omega } } \bar { L } _ { - 1 } L _ { - 1 } \omega , \qquad \Phi ^ { * } = \operatorname * { l i m } _ { \stackrel { N  \infty } { \lambda \mathrm { ~ f i x e d ~ } } } \frac { 1 } { 2 h _ { \omega } } \bar { L } _ { - 1 } L _ { - 1 } \omega ^ { * } .
$$

Since the four-point function of $P$ with itself does not factorise over the identity channel, the perturbation by $P$ will not be exactly marginal [37]. However, as in [36] there are suitable holomorphic descendants of $\omega$ (and its higher powers) that begin to mix with the stress energy tensor in perturbation theory,and it is plausible that a suitable linear combination of them will remain holomorphic.In any case,we shallonly work to first order in perturbation theory, where the theory remains conformal.

# 5.1 The structure of the perturbation theory

In order to study the effect of the perturbation by $P$ , one could try to study the behaviour of the structure constants of the ${ \mathcal W } _ { \infty } \vert \lambda \vert$ algebra (i.e. the correlators of the holomorpic currents) under the perturbation by $P$ . However, this is quite delicate since the perturbation directly affects the holomorphic correlators only at second order in perturbation theory: since $P$ has conformal dimension $( 1 , 1 )$ , the ‘right-moving' conformal dimension must be soaked up by at least one other field with non-zero right-moving conformal dimension. In fact, there is a quite generic argument that shows that $\lambda$ can never be changed by an exactly marginal operator （20 $P$ .8 In order to see this, suppose that we have a family of $\mathcal { W }$ -algebras (parametrised by $\lambda$ ） and suppose that we could change $\lambda$ by switching on a perturbation by an exactly marginal field $P$ with coupling constant $g$ . As we have just explained, the first order perturbation must always vanish, thus the derivative of all $\mathcal { W }$ -algebra correlators with respect to $g$ vanishes when evaluated at $g = 0$ — and this holds for all values of $\lambda$ . But if the perturbation by $g P$ （204号 just changes $\lambda$ , then the fact that this holds for all values of $\lambda$ implies that it also holds for all values of $g$ , i.e. that the derivative of the $\mathcal { W }$ -algebra correlators with respect to $g$ vanishes for all values of $g$ . But then this means that these correlators are actually independent of $g$ ， i.e. that the $\mathcal { W }$ -algebra does not change under the perturbation.

In our case the situation is different since $P$ is not exactly marginal, and hence the previous argument does not apply. However, it highlights the diffculty in trying to determine the change of $\lambda$ directly from the correlators of the holomorphic currents. We shall therefore follow a different route: we will compute the conformal dimension of the simplest representation $\mathcal { O } \equiv ( \ v { \mathrm { { \boxed { \Gamma } } 0 } } )$ (which has conformal dimension $h = { \textstyle \frac { 1 } { 2 } } ( 1 + \lambda )$ at $\mathcal { O } ( g ^ { 0 } )$ ） in the perturbed theory, and read off the effect of the perturbation from the change of $h$ . The computation is an analysis of operator-mixing following [38] (see also [39]) which we shall now outline.

Let us consider all the fields $\{ \mathcal { O } _ { i } , \mathcal { O } _ { i } ^ { * } \}$ with conformal dimension $\textstyle h = { \frac { 1 + \lambda } { 2 } }$ in the unperturbed theory， where $\mathcal { O } _ { i }$ and ${ \mathcal { O } } _ { i } ^ { * }$ are a conjugate pair. Define $\mathcal { M }$ as the matrix of their two-point functions. Because these two-point functions always couple conjugate pairs to

gether, the structure of $\mathcal { M }$ is of the form

$$
\mathcal { M } = { \bf M } \otimes \left( \begin{array} { l l } { { 0 } } & { { 1 } } \\ { { 1 } } & { { 0 } } \end{array} \right) \ .
$$

As we shall see， we only need to know the eigenvalues of $\mathcal { M }$ ； therefore it is enough to concentrate on the matrix $\mathbf { M }$ , i.e. we shall simply write $\mathcal { O } _ { i }$ for the pair $\{ \mathcal { O } _ { i } , \mathcal { O } _ { i } ^ { * } \}$ ，

$$
{ \bf M } _ { i j } = \langle { \mathcal O } _ { i } ( z _ { 1 } , \bar { z } _ { 1 } ) { \mathcal O } _ { j } ( z _ { 2 } , \bar { z } _ { 2 } ) \rangle \ .
$$

At $\mathcal { O } ( g ^ { 0 } )$ , the matrix $\mathbf { M }$ is diagonal

$$
{ \bf \Phi } ^ { " } ) = \langle \mathcal { O } _ { i } ( z _ { 1 } , \bar { z } _ { 1 } ) \mathcal { O } _ { j } ( z _ { 2 } , \bar { z } _ { 2 } ) \rangle ^ { ( 0 ) } = \frac { 1 } { | z _ { 1 } - z _ { 2 } | ^ { 4 h } } \delta _ { i j } \quad \mathrm { a n d } \ \ln \mathbf { M } ^ { ( 0 ) } = ( - 4 h ) \ln | z _ { 1 } - z _ { 2 } | \mathbf { 1 } | \mathcal { O } ( [ \mathbf { x } _ { 1 } , \mathbf { x } _ { 2 } ] ) ,
$$

At order $g$ ，two representations（ $\mathcal { O } _ { i }$ and $O _ { j }$ ） that are related to each other by adding or subtracting a box can start to have a non-zero two-point function

$$
\begin{array} { l l l } { { \langle { \mathcal O } _ { i } ( z _ { 1 } , \bar { z } _ { 1 } ) { \mathcal O } _ { j } ( z _ { 2 } , \bar { z } _ { 2 } ) \rangle ^ { ( 1 ) } } } & { { = } } & { { g \displaystyle \int d ^ { 2 } w \langle { \mathcal O } _ { i } ( z _ { 1 } , \bar { z } _ { 1 } ) { \mathcal O } _ { j } ( z _ { 2 } , \bar { z } _ { 2 } ) P ( w , \bar { w } ) \rangle } } \\ { { } } & { { = } } & { { g \displaystyle \frac { 1 } { | z _ { 1 } - z _ { 2 } | ^ { 4 h } } \ln | z _ { 1 } - z _ { 2 } | { \bf P } _ { i j } ~ . } } \end{array}
$$

Thus, to $\mathcal O ( g )$ , the mixing matrix $\mathbf { M }$ is

$$
\mathbf { M } = \mathbf { M } ^ { ( 0 ) } + g \mathbf { P } + \mathcal { O } ( g ^ { 2 } ) = \frac { 1 } { | z _ { 1 } - z _ { 2 } | ^ { 4 h } } \Big ( 1 + g \mathbf { P } \ln | z _ { 1 } - z _ { 2 } | + \mathcal { O } ( g ^ { 2 } ) \Big )
$$

with $\ln \mathbf { M } = [ ( - 4 h ) \mathbf { 1 } + g \mathbf { P } ] \ln | z _ { 1 } - z _ { 2 } | + \mathcal { O } ( g ^ { 2 } )$ . In particular, after the perturbation is turned on,the two-point function matrix is no longer diagonal, i.e. the fields $\{ \mathcal { O } _ { i } , \mathcal { O } _ { i } ^ { * } \}$ we started with are no longer conformal eigenstates. The new conformal eigenstates in the perturbed theory at $\mathcal O ( g )$ are the eigenvectors of the mixing matrix defined as

$$
M = \left( - 4 h \right) \mathbf { 1 } + g \mathbf { P } \ ,
$$

and their conformal dimensions are the corresponding eigenvalues divided by $( - 4 )$

Now in order to study the effect of the perturbing field $P$ on $( \boxed { \cdot } ; 0 )$ ，we first need to identify all states that are ‘mixed' together at order $g$ ; a necessary condition for this is that they have conformal dimension $h = { \textstyle \frac { 1 } { 2 } } ( 1 + \lambda )$ in the 't Hooft limit.To enumerate these fields, first recall that the conformal dimension of $( \Lambda _ { + } ; \Lambda _ { - } )$ at finite $( N , k )$ can be written in terms

of the quadratic Casimir $C _ { 2 }$ of $\mathfrak { s u } ( N )$ as

$$
h ( \Lambda _ { + } ; \Lambda _ { - } ) = { \frac { C _ { 2 } ( \Lambda _ { + } ) } { N + k } } + { \frac { C _ { 2 } ( \Lambda _ { 0 } ) } { N + 1 } } - { \frac { C _ { 2 } ( \Lambda _ { - } ) } { N + k + 1 } } + n \ ,
$$

where $\{ \Lambda _ { + } , \Lambda _ { 0 } , \Lambda _ { - } \}$ are highest weight representations of $\{ \mathfrak { s u } ( N ) _ { k } , \mathfrak { s u } ( N ) _ { 1 } , \mathfrak { s u } ( N ) _ { k + 1 } \}$ ，respectively. They satisfy the constraint that, as a weight of $\mathfrak { s u } ( N )$ ， $\Lambda _ { + } + \Lambda _ { 0 } - \Lambda _ { - }$ lies in the root lattice of $\mathfrak { s u } ( N )$ . Furthermore, $n$ is the‘height’ at which $\Lambda _ { - }$ appears in $\Lambda _ { + } \otimes \Lambda _ { 0 }$ . The quadratic Casimir has the large $N$ expansion (that is exact even at finite $N$ ）

$$
C _ { 2 } ( \Lambda ) = N \frac { B ( \Lambda ) } { 2 } + \frac { D ( \Lambda ) } { 2 } - \frac { B ( \Lambda ) ^ { 2 } } { 2 N } ,
$$

where $B ( \Lambda )$ is the number of boxes of $\Lambda$ ， $\begin{array} { r } { B ( \Lambda ) = \sum _ { i } r _ { i } = \sum _ { j } c _ { j } } \end{array}$ ，and $D ( \Lambda )$ is defined as （204号 $\begin{array} { r } { D ( \boldsymbol { \Lambda } ) = \sum _ { i } r _ { i } ^ { 2 } - \sum _ { j } c _ { j } ^ { 2 } } \end{array}$ ，with $r _ { i }$ and $c _ { j }$ being the number of boxes in the $i$ 'th row and $j$ 'th column,respectively. Expressed in terms of $B$ and $\boldsymbol { D }$ , the large $N$ expansion of the conformal dimension (5.10) is then

$$
_ - ) = { \frac { B _ { 0 } + ( B _ { + } - B _ { - } ) \lambda } { 2 } } + n + { \frac { 1 } { 2 N } } \Big [ ( D _ { 0 } - B _ { 0 } ) + ( D _ { + } - D _ { - } ) \lambda + B _ { - } \lambda ^ { 2 } \Big ] + { \mathcal O } \left( { \frac { 1 } { N } } \right)
$$

where $B _ { + }$ is a shorthand for $B ( \Lambda _ { + } )$ ， and similarly for the others.9 Therefore for the state （204号 $( \Lambda _ { + } ; \Lambda _ { - } )$ to have conformal dimension $\textstyle { \frac { 1 + \lambda } { 2 } }$ in the 't Hooft limit we need

$$
B _ { 0 } = 1 , \qquad B _ { + } - B _ { - } = 1 , \qquad \mathrm { a n d } \quad n = 0 \ ,
$$

which means that $\Lambda _ { + } \subset \Lambda _ { - } \otimes \square$ .For these representations - in the following we shall refer to them sometimes as the ‘scalar-like’ representations — the conformal dimension then equals

$$
h ( \Lambda _ { + } ; \Lambda _ { - } ) = { \frac { 1 } { 2 } } ( 1 + \lambda ) + { \frac { \lambda ^ { 2 } B _ { - } - 1 } { 2 N } } + { \frac { D _ { + } - D _ { - } } { 2 N } } \lambda + { \mathcal O } \Bigl ( { \frac { 1 } { N ^ { 2 } } } \Bigr ) \ .
$$

Note that this formula is only correct for $\lambda < 1$ ; for $\lambda = 1$ ， we need to take $N  \infty$ at finite $k$ ，and then an expansion in inverse powers of $N$ does not make sense. Instead, we should then consider an expansion in inverse powers of $k$ , i.e. we should replace

$$
\frac { 1 } { N } \mapsto \frac { ( 1 - \lambda ) } { \lambda } \frac { 1 } { k } .
$$

The property that $\Lambda _ { + } \subset \Lambda _ { - } \otimes \sqcup$ implies that the fields of interest are in one-to-one correspondence with the edges of the Young lattice (see e.g. [40] for an introduction to some of its basic properties —the different colours of the arrows in Fig. 1 willbe explained below).

![](images/4814d0b7105e10658d44af1a10c717747d26369a7a502193e0c9047c7069e65e.jpg)  
Figure 1: Young lattice.

Recall that the number of Young tableaux at level $n$ (i.e. with $n$ boxes） equals $P ( n )$ (the partition number of $n$ ),while the number of edges at level $n$ (i.e. edges from level $n$ to level （20 $n + 1 )$ is $S ( n )$ defined by

$$
S ( n ) = \sum _ { k = 0 } ^ { n } P ( k ) \ .
$$

Their generating functions are

$$
\sum _ { n = 0 } ^ { \infty } P ( n ) x ^ { n } = \prod _ { m = 1 } ^ { \infty } { \frac { 1 } { 1 - x ^ { m } } } \qquad \sum _ { n = 0 } ^ { \infty } S ( n ) x ^ { n } = { \frac { 1 } { 1 - x } } \prod _ { m = 1 } ^ { \infty } { \frac { 1 } { 1 - x ^ { m } } } ~ .
$$

$S ( n )$ counts the number of scalar-like fields for which $\Lambda _ { - }$ has $n$ boxes, and it grows exponentially with $n$ .10 Therefore there are infinitely many such fields in the 't Hooft limit,and we need to deal with an infinitely-degenerate operator mixing problem. However,as we shall see below in Section 5.3,the perturbation analysis has a lot of structure,and we can therefore understand at least its qualitative features in some detail.

# 5.2 The mixing matrix

Next we want to determine the mixing matrix $M$ explicitly. Its off-diagonal entries can be computed from the integral

$$
\int d ^ { 2 } w \langle { \mathcal O } _ { i } ( z _ { 1 } , \bar { z } _ { 1 } ) { \mathcal O } _ { j } ( z _ { 2 } , \bar { z } _ { 2 } ) P ( w , \bar { w } ) \rangle = { \bf P } _ { i j } \frac { 1 } { | z _ { 1 } - z _ { 2 } | ^ { 4 h } } \ln | z _ { 1 } - z _ { 2 } | ~ ,
$$

where $h = { \textstyle \frac { 1 } { 2 } } ( 1 + \lambda )$ is the conformal dimension at $\mathcal { O } ( g ^ { 0 } )$ . As explained above, the correlators in the integrand are first to be evaluated at finite $N$ and $k$ ，with $P = \Phi + \Phi ^ { * }$ as given in (5.3); the large $N$ ， $k$ limit is then only taken at the end.At finite $N$ and $k$ and up to $\textstyle { \mathcal { O } } ( { \frac { 1 } { N } } )$ ， the three-point function of $\mathcal { O } _ { 1 }$ and $\mathcal { O } _ { 2 }$ with $\omega$ equals

$$
z _ { 1 } , \bar { z } _ { 1 } ) \mathcal { O } _ { 2 } ( z _ { 2 } , \bar { z } _ { 2 } ) \omega ( w , \bar { w } ) \rangle = C _ { \mathcal { O } _ { 1 } \mathcal { O } _ { 2 } \omega } \left| \frac { 1 } { ( z _ { 1 } - z _ { 2 } ) ^ { 2 h + \frac { 1 } { N } \Delta _ { 1 } } ( z _ { 2 } - w ) ^ { \frac { 1 } { N } \Delta _ { 2 } } ( z _ { 1 } - w ) ^ { \frac { 1 } { N } \Delta _ { 3 } } } \right| ^ { 2 }
$$

where $\Delta _ { i } = \delta _ { i } + \delta _ { i + 1 } - \delta _ { i + 2 }$ ,and $\delta _ { i }$ (with $i \equiv i + 3$ )are the $\textstyle { \mathcal { O } } ( { \frac { 1 } { N } } )$ corrections to the conformal dimensions

$$
\mathcal O _ { 1 } : ~ h _ { 1 } = h + \frac { \delta _ { 1 } } { N } ~ \omega _ { 2 } : ~ h _ { 2 } = h + \frac { \delta _ { 2 } } { N } ~ \omega : ~ h _ { 3 } = \frac { \delta _ { 3 } } { N } = \frac { \lambda ^ { 2 } } { 2 N } .
$$

In ordertodduefrotis tecoreaorcorrsding to $\Phi$ , we then apply $\begin{array} { r } { \frac { 1 } { 2 h _ { \omega } } L _ { - 1 } L _ { - 1 } } \end{array}$ t0 (5.19) and obtain

$$
\therefore \bar { z } _ { 1 } , \bar { z } _ { 1 } ) \mathcal { O } _ { 2 } ( z _ { 2 } , \bar { z } _ { 2 } ) \Phi ( w , \bar { w } ) \rangle = \frac { 4 } { N \lambda ^ { 2 } } C _ { { \mathcal { O } } _ { 1 } { \mathcal { O } } _ { 2 } \omega } \left| \frac { \frac { \Delta _ { 2 } } { z _ { 2 } - w } + \frac { \Delta _ { 3 } } { z _ { 1 } - w } } { ( z _ { 1 } - z _ { 2 } ) ^ { 2 h + \frac { 1 } { N } \Delta _ { 1 } } ( z _ { 2 } - w ) ^ { \frac { 1 } { N } \Delta _ { 2 } } ( z _ { 1 } - w ) ^ { \frac { 1 } { N } \Delta _ { 3 } } } \right| 0 \rangle
$$

Finally, we take the large $N$ limit and evaluate the $w$ -integral to obtain

$$
\int d ^ { 2 } w \langle { \mathcal O } _ { 1 } ( z _ { 1 } , \bar { z } _ { 1 } ) { \mathcal O } _ { 2 } ( z _ { 2 } , \bar { z } _ { 2 } ) \Phi ( w , \bar { w } ) \rangle = \Bigl ( - \frac { 1 6 \pi } { N } \cdot \frac { \Delta _ { 2 } \Delta _ { 3 } } { \lambda ^ { 2 } } \cdot C _ { { \mathcal O } _ { 1 } { \mathcal O } _ { 2 } \omega } \Bigr ) \frac { 1 } { | z _ { 1 } - z _ { 2 } | ^ { 4 h } } \ln | .
$$

where $\begin{array} { r } { \Delta _ { 2 } \Delta _ { 3 } = ( \frac { \lambda ^ { 2 } } { 2 } ) ^ { 2 } - ( \delta _ { 1 } - \delta _ { 2 } ) ^ { 2 } } \end{array}$ ; here we have used the identity

$$
\int d ^ { 2 } w \frac { 1 } { ( w - z _ { 1 } ) ( \bar { w } - \bar { z } _ { 2 } ) } = 2 \pi \ln r \Big | _ { | z _ { 1 } - z _ { 2 } | } ^ { \infty } .
$$

and dropped the $\ln \infty$ term.11

Thus the $\mathbf { P } _ { i j }$ entry in the mixing matrix between ${ \mathcal { O } } _ { i }$ and $O _ { j }$ is

$$
{ \bf P } _ { i j } = \frac { 1 6 \pi } { N } \cdot C _ { \mathcal { O } _ { i } \mathcal { O } _ { j } \omega } \cdot \Big ( \frac { ( \delta _ { i } - \delta _ { j } ) ^ { 2 } } { \lambda ^ { 2 } } - \frac { \lambda ^ { 2 } } { 4 } \Big ) \ .
$$

The coefficients $\delta _ { i }$ and $\delta _ { j }$ are read off from (5.14),and for the calculation of the structure constants $C _ { O _ { i } O _ { j } \omega }$ we can use the results of [41, 42], see also [43] for earlier work. In particular, some of them were calculated explicitly in [41] using the Coulomb gas approach. Based on the large $N$ factorisation properties of these structure constants, [42] wrote down an effective Hamiltonian that captures the exact spectrum and cubic interactions in the 't Hooft limit. Since we only need the large $N$ result,we can therefore directly use this effective Hamiltonian point of view.

We have worked out the explicit coefficients for the low-lying representations up to level 4; some of the details are spelled out in Appendix C.

# 5.3 The eigenvalue problem

As we have reviewed above, the eigenvalues of the mixing matrix $M$ (5.9） give the perturbed conformal dimensions of the states under consideration. Thus we need to study the eigenproblem

$$
M \cdot { \vec { F } } = \rho { \vec { F } } \ .
$$

In the strict $N  \infty$ limit $\vec { F }$ is an infinite-dimensional vector,and hence we expect $\rho$ to take a continuum of eigenvalues. Nevertheless, as we shall now explain, the structure of the eigenvalues can be identified naturally with that of the conformal dimensions of the scalar-like states in the 't Hooft limit.

To start with we observe that the matrix $M$ has the form of a block Jacobi matrix

$$
M ( \{ A _ { n } \} , \{ B _ { n } \} ) = \left( \begin{array} { c c c c c c } { { A _ { 1 } } } & { { B _ { 1 } } } & { { 0 } } & { { 0 } } & { { 0 } } & { { . . . } } \\ { { B _ { 1 } ^ { T } } } & { { A _ { 2 } } } & { { B _ { 2 } } } & { { 0 } } & { { 0 } } & { { . . . } } \\ { { 0 } } & { { B _ { 2 } ^ { T } } } & { { A _ { 3 } } } & { { B _ { 3 } } } & { { 0 } } & { { . . . } } \\ { { 0 } } & { { 0 } } & { { \ddots } } & { { \ddots } } & { { \ddots } } & { { 0 } } \end{array} \right)
$$

with

$$
\begin{array} { r } { n = - 4 h { \bf 1 } _ { S ( n - 1 ) \times S ( n - 1 ) } \ , \qquad B _ { n } = S ( n - 1 ) \times S ( n ) \mathrm { m a t r i x ~ o f ~ r a n k } \ S ( n - 1 ) \ . } \end{array}
$$

The first few explicit expressions for $B _ { n }$ are given in Appendix C. At low levels (for which we have worked them out, i.e. up to level 4), the matrix $B _ { n }$ has rank $S ( n - 1 )$ provided that （204号 $\lambda \neq 0$ . This is also what one should expect generically, and we therefore conjecture that this

will continue to be true for all $n$

Under this assumption the eigenvector problem (5.25) can be solved recursively, generalising the method of finding the eigenvalues of a scalar Jacobi matrix (which we review in Appendix D). We first decompose the eigenvector $\vec { F }$ into $\Vec { F } = \{ \Vec { f } _ { 1 } , \Vec { f } _ { 2 } , . . . \}$ ，with ${ \vec { f _ { n } } }$ being a vector of dimension $S ( n - 1 )$ . Then for any given eigenvalue $\rho$ , we have to solve the recursive relations

$$
B _ { n } \cdot \vec { f } _ { n + 1 } = ( \rho + 4 h ) \vec { f } _ { n } - B _ { n - 1 } ^ { T } \cdot \vec { f } _ { n - 1 } \ , \qquad n \in \mathbb { N } _ { \geq 1 } \ ,
$$

where we have set $\vec { f } _ { 0 } \equiv 0$ . Unlike the scalar Jacobi case for which the equation, at each level, is a scalar equation,now the equation at level $n$ is a matrix equation with $S ( n - 1 )$ components for the $S ( n )$ unknowns in ${ \vec { f } } _ { n + 1 }$ . However， since $B _ { n }$ has rank $S ( n - 1 )$ ， we can always find $a$ solution for ${ \vec { f } } _ { n + 1 }$ , and hence an eigenvector with eigenvalue $\rho$ . This solution is, however, not unique — in fact the kernel of $B _ { n }$ has dimension $S ( n ) - S ( n - 1 ) = P ( n )$ ，and thus, at every level $n$ ,we obtain $P ( n )$ new families of solutions with $\vec { f } _ { n + 1 } \neq 0$ but ${ \vec { f } } _ { i } = 0$ for $i \leq n$ ：

In order to illustrate the structure of these various solutions let us describe some simple examples. Consider first the eigenvector that involves the original scalar representation $( \boxed { \cdot } ; 0 )$ , i.e. the eigenvector with $f _ { 1 } = 1$ . In this case,(5.28) is to be solved with the initial condition

$$
f _ { 1 } = 1 ~ .
$$

We may choose to supplement the recursion relation (5.28) with the requirement that $\vec { f } _ { n + 1 }$ is orthogonal to the kernel of $B _ { n }$ ，

$$
\vec { f } _ { n + 1 } ^ { T } \cdot g _ { n } = 0 \qquad \forall g _ { n } \in \ker ( B _ { n } )
$$

in order to guarantee that at level $n$ the corresponding eigenvector is orthogonal to the new families of eigenvectors that will appear at that level. These $P ( n )$ equations, together with the $S ( n - 1 )$ equations from (5.28), then uniquely determine the $S ( n )$ components of ${ \vec { f } } _ { n + 1 }$ for all $n \geq 1$ . This construction works for arbitrary $\rho$ , and thus we conclude that the eigenvalue spectrum is continuous. This is consistent with the fact that, in the strict $N  \infty$ limit, there are infinitely many states that are‘mixed' with $( \boxed { \cdot } ; 0 )$ via $P$ ：

In constructing the solution with $f _ { 1 } = 1$ we have in effect identified from the infinite mixing matrix $M$ (5.9)a sub-matrix (which is also infinite) that describes the mixing of （204号 $( \boxed { \cdot } ; 0 )$ with all states that couple to it at $\mathcal O ( g )$ . For example, the condition(5.30) with $n = 1$ identifes a specific linear combination $\vec { f _ { 2 } } ^ { ( 1 ) }$ of the two states $( \boxed { \begin{array} { r l } \end{array} } ; \boxed { \begin{array} { r l } \end{array} } )$ and $( \boxed { \dag } ; \boxed { \dag } )$ at level 2, namely the linear combination that mixes with $( \boxed { \cdot } ; 0 )$ at order $g$ , and similarly at the higher levels.However, since there are two scalar-like states at level 2, we may construct a second state $\vec { f _ { 2 } } ^ { ( 2 ) }$ from $( \boxed { \begin{array} { r l } \end{array} } ; \boxed { \begin{array} { r l } \end{array} } )$ and $( \boxed { \dag } ; \boxed { \dag } )$ that is orthogonal to $\vec { f _ { 2 } } ^ { ( 1 ) }$ and hencelies in the kernel of $B _ { 1 }$ . It will generate a new family of solutions; this is to say, we can repeat the above procedure replacing $( \boxed { \cdot } ; 0 )$ by $\vec { f _ { 2 } } ^ { ( 2 ) }$ , i.e.by imposing the initial conditions

$$
f _ { 1 } = 0 \ , \qquad \vec { f } _ { 2 } = \vec { f } _ { 2 } ^ { ( 2 ) } \ .
$$

The eigenvectors of this second sub-matrix then involve the states that mix with the linear combination of $( \boxed { \begin{array} { r l } \end{array} } ; \boxed { \begin{array} { r l } \end{array} } )$ and $( \boxed { \dag } ; \boxed { \dag } )$ given by $\vec { f _ { 2 } } ^ { ( 2 ) }$ at order $g$ . Again, we can find the solution for the $\vec { f _ { n } }$ recursively, requiring as before (5.30） for $n \geq 2$ ， and since this can be done for any choice of $\rho$ , it will also lead to a continuum of eigenvalues.

It should now be clear how to proceed in general: at level $n$ , we find $P ( n ) = S ( n ) – S ( n - 1 )$ new families of solutions for which $\vec { f } _ { n + 1 } \neq 0$ lies in the kernel of $B _ { n }$ and $\vec { f } _ { j } = 0$ for $j \le n$ ： For each choice of ${ \vec { f } } _ { n + 1 }$ we can then construct an eigenvector recursively for any value of $\rho$ Thus each of these families will also give rise to a continuum of eigenvalues in the 't Hooft limit. Altogether we therefore get at each level $n$ ， $P ( n )$ families of eigenvectors,where each family has in turn a continuum of eigenvalues.

So far we have studied the eigenvalue problem in the strict $N  \infty$ limit.It is natural to ask whether it is possble to formulate (and hopefully answer） the same question at large but finite $N$ . At finite $( N , k )$ , the number of scalar-like states is finite ( $\sim \operatorname* { m i n } ( N , k ) )$ （20 and correspondingly the spectrum is no longer a continuum. In fact，as is explained in Appendix D,it is straightforward to determine the eigenvalues of the finite problem by similar techniques. The resulting eigenvalues are then distributed symmetrically with respect toh=1+.

# 5.4The CFT interpretation

As we have explained above, see eq. (5.9), each eigenstate with eigenvalue $\rho$ corresponds to a state in the spectrum with conformal dimension

$$
h _ { \rho } = - \frac { \rho } { 4 } = h - \frac { 1 } { 4 } ( \rho + 4 h ) \ , \qquad \mathrm { i . e . } \quad \delta h = - \frac { 1 } { 4 } ( \rho + 4 h ) \ .
$$

We now want to match $\delta h$ as computed from the perturbative analysis, to the change in conformal dimension of the primary operators of the $\mathcal { W } _ { N , k }$ models in the 't Hooft limit as we vary $( N , k )$ . Recall that the 't Hooft parameter and the central charge of the $\mathcal { W } _ { N , k }$ models are given by $\lambda$ and $c _ { N , k }$ in (4.4) and (4.5), respectively. As we modify $N \mapsto N + \delta N$ and $k \mapsto k + \delta k$ , they change to first order(in the 't Hooft limit）as

$$
\delta \lambda = - \frac { 1 } { N } \lambda ( \lambda - 1 ) \delta N - \frac { 1 } { N } \lambda ^ { 2 } \delta k
$$

and

$$
\delta c = ( 2 \lambda + 1 ) ( \lambda - 1 ) ^ { 2 } \delta N + 2 \lambda ^ { 3 } \delta k \ .
$$

Furthermore, the $\gamma ^ { 2 }$ parameter, defined in (2.30),can be expressed in terms of $N$ and $k$ as

$$
\gamma ^ { 2 } = \frac { 6 4 ( k + 1 ) ( N - 3 ) ( N + 1 ) ( k + 2 N ) ( 3 k + 2 N ) ( 3 k + 4 N + 3 ) } { ( N - 2 ) ( 2 k + N ) ( 2 k + 3 N + 2 ) \big ( k ( 5 N + 1 7 ) ( k + 2 N + 1 ) + 2 2 N ( N + 1 ) \big ) }
$$

and thus it changes as

$$
\delta \gamma ^ { 2 } = - { \frac { 1 2 8 \lambda ^ { 2 } ( \lambda - 1 ) } { N ( \lambda - 2 ) ^ { 2 } ( \lambda + 2 ) ^ { 2 } } } \delta N - { \frac { 1 2 8 \lambda ^ { 3 } } { N ( \lambda - 2 ) ^ { 2 } ( \lambda + 2 ) ^ { 2 } } } \delta k \ .
$$

Given our general argument above (see the beginning of Section 5.1) we should expect that to first order $\delta \gamma ^ { 2 } = 0$ . Thus we conclude that $\delta k$ and $\delta N$ should be related as

$$
\delta k = - { \frac { ( \lambda - 1 ) } { \lambda } } \delta N .
$$

Note that then we also have $\delta \lambda = 0$ ,and

$$
\delta c = \left( 1 - \lambda ^ { 2 } \right) \delta N \ .
$$

Under this deformation the conformal dimensions of the scalar-like representations in eq. (5.14) change as

$$
\delta h ( \Lambda _ { + } ; \Lambda _ { - } ) = - { \frac { 1 } { 2 } } { \frac { \delta N } { N } } \Bigl [ { \frac { \lambda ^ { 2 } B _ { - } - 1 } { N } } + { \frac { ( D _ { + } - D _ { - } ) } { N } } \lambda \Bigr ] \ .
$$

This should now be compared to (5.32) above.

In order to do so,let us frst explain how the structure of the answer is the same on both sides. As we have seen above, the eigenstates of the mixing matrix $M$ organise themselves into families,where at each level $n$ ， $P ( n )$ new families of eigenvectors of $M$ emerge.Each such family gives rise to a continuum of eigenvalues $\rho$

From the viewpoint of the minimal model representations on the other hand, let us consider the ‘branches’ of the Young lattice.Recall that the edges of the Young lattice are in one-to-one corresponding to the scalar-like states $( \Lambda _ { + } ; \Lambda _ { - } )$ ．A branch is a collection of edges,starting from a given level and including one edge at each subsequent level. Given the structure of the Young lattice,see in particular eq. (5.16), it is clear that at each level （204号 $n$ ， there are $P ( n )$ edges that are not on any branch that emerges before level $n$ and are the roots of $P ( n )$ new branches. Thus the branches of the Young lattice are in natural one-to-one correspondence to the families of eigenstates of $M$ ：

One definite (and natural) way to construct these branches is as follows. Let us begin with the original scalar representation $( \boxed { \cdot } ; 0 )$ ，and define its branch by picking one representation at each level (i.e. for each value of $B _ { - }$ ),namely the one for which $\Delta D \equiv D _ { + } - D _ { - }$ is maximal. (This is the branch described by the black edges in Fig. 1.） Then we consider the corresponding transposed branch,where we replace each representation $( \Lambda _ { + } ; \Lambda _ { - } )$ by its transpose $( \Lambda _ { + } ^ { t } ; \Lambda _ { - } ^ { t } )$ .12 Obviously the transposed branch shares the representation $( \boxed { \cdot } ; 0 )$ with the original branch; thus we should take it to start from $( \boxplus ; 0 )$ instead - this then leads to the branch corresponding to the red edges in Fig. 1. Note that taking the transpose does not modify $B _ { - }$ — so the transposed branch also has one representation at each level ——but it changes the sign of both $D _ { + }$ and $D _ { - }$ , and hence the sign of $\Delta D$ . Thus the change in conformal dimensions of the transposed representations are, apart from the ‘drift term' （204号 $( \lambda ^ { 2 } B _ { - } - 1 ) / N$ , opposite to those of the original representations, see eq. (5.39).

We now propose that these two branches together are to be mapped to the first two families that come out of the perturbative analysis,i.e. the family (5.29) that mixes with $( \boxed { \cdot } ; 0 )$ ,and the family (5.31)that mixes with the level 2 state given by $\vec { f _ { 2 } } ^ { ( 2 ) }$ . In particular, in the 't Hooft limit the ratio $\Delta D / N$ (as well as the drift term $( \lambda ^ { 2 } B _ { - } - 1 ) / N )$ become continuous variables,and hence the branches of minimal model representations lead to a continuum of perturbed conformal dimensions; this matches the continuum for $\rho$ we found above. At finite $N$ and $k$ ， the two branches contain the same number of states as the two families,and their eigenvalues are, except for the‘drift term' $( \lambda ^ { 2 } B _ { - } - 1 ) / N$ ， symmetrically distributed around $h$ ， thereby matching the structure found in the perturbative analysis. (We shallcomment below on the origin of the‘drift term’ in the perturbative analysis.)

It should now be clear how to continue. While the above two branches account for all representations up to level 2, there are two more branches starting with edges linking level 2 to level 3. Again, they can be completed into branches by picking at each level a representation with the second biggest (or smallest） value for $\Delta D$ —— these two branches can be chosen to be transposes of one another, and they correspond to the solutions of the perturbative analysis with $f _ { 1 } = \vec { f } _ { 2 } = 0$ and $\vec { f } _ { 3 } \neq 0$ . (They are described by the blue and green edges in Fig. 1.） Furthermore, their eigenvalues will,again apart from the drift term, be symmetrically distributed around $h$ ：

Continuing in this manner, there will be $P ( n )$ branches emerging at level $n$ ，and their   
conformal weights will,apart from the drift term,be symmetrically distributed around $h$   
This matches nicely the structure of the eigenvalues as computed in the perturbative analysis. It remains to comment on the reason that the ‘drift term’ $( \lambda ^ { 2 } B _ { - } - 1 ) / N$ in (5.39) is

invisible to the perturbation analysis of the previous subsection. Recall that in the formula of the quadratic Casimir (5.11), the term proportional to $B$ is the leading term in the $\textstyle { \frac { 1 } { N } }$ （20 expansion. It should therefore be considered as the‘classical’ contribution, while the term proportional to $D$ corresponds to the first $\textstyle { \frac { 1 } { N } }$ correction. Correspondingly, in the expansion ofthcofolisio(.)o $\frac { \lambda ^ { 2 } B _ { -- } - 1 } { 2 N }$ and $\frac { D _ { + } - D _ { - } } { 2 N } \lambda$ are of $\textstyle { \mathcal { O } } ( { \frac { 1 } { N } } )$ , in some sense only the first one is ‘classical'.13 Therefore in the large but finite $N$ case, we shouldn't merely truncate the infinite mixing matrix to a finite one; we should also shift the diagonal entries of the mixing matrix by the‘clasical' picce $( - 4 ) \frac { \lambda ^ { 2 } B _ { -- } - 1 } { 2 N }$ .Once this is done, the new eigenvalues are distributed symmetrically with respect to the shifted $\mathcal { O } ( g ^ { 0 } )$ conformal dimension,tusexplaiingthedriftt $\frac { \lambda ^ { 2 } B _ { -- } - 1 } { N }$ in (5.39).

We therefore regard this as good evidence for the assertion that the perturbation by $P$ （204号 corresponds to switching on the above $\textstyle { \frac { 1 } { N } }$ corrections of the $\mathcal { W } _ { N , k }$ minimal models in the 't Hooft limit.We should also mention that this identification fits with what we have seen explicitly for the special cases $\lambda = 0$ and $\lambda = 1$ above. Indeed,for $\lambda = 1$ ， it follows from (5.36) that in order for $\delta \gamma ^ { 2 } = 0$ ， we need to take $\delta k = 0$ , see also (5.37). But then, it follows from (5.33) and (5.34) that both $\delta \lambda = \delta c = 0$ , i.e. that the perturbation does not change anything, in nice agreement with what we saw in Section 4.4. From the point of view of the perturbative analysis, at $\lambda = 1$ where $N  \infty$ at finite $k$ , it is no longer appropriate to make a $\textstyle { \frac { 1 } { N } }$ expansion, but we should rather perform a $\frac { 1 } { k }$ expansion, replacing $\textstyle { \frac { 1 } { N } }$ by $\frac { 1 } { k }$ as in (5.15). But then (5.24) vanishes at $\lambda = 1$ , i.e. the spectrum is not perturbed at all.

On the other hand, for $\lambda = 0$ ， $\delta \lambda = 0$ automatically from (5.33） and $\delta c = \delta N$ from (5.34). In this case the condition $\delta \gamma ^ { 2 } = 0$ from(5.36) does not impose any restriction on $\delta k$ and $\delta N$ ， and thus $\delta c = \delta N$ will be non-zero. Note,however, that the coefficient of the $\Delta D$ -term in (5.39) vanishes for $\lambda = 0$ . This is reflected, in the context of the perturbation computation, by the fact that the analysis breaks down for $\lambda = 0$ as the $B _ { n }$ do not have maximal rank any longer. (For instance, the rank of $B _ { 3 }$ is $\operatorname { r k } ( B _ { 3 } ) = 3 < 4$ ，at $\lambda = 0$ .）This reduction in the rank of $B _ { n }$ at $\lambda = 0$ is a sign that the scalar-like states do not ‘mix’ strongly enough to break the degeneracy of their conformal dimensions.

# 6 Conclusions

In this paper we have studied the behaviour of the ${ \mathcal W } _ { \infty } [ \lambda ]$ theories under perturbations that preserve the symmetry algebra to frst order. In particular, we have found that the minimal models possess such a perturbing field in the 't Hooft limit,and we have shown that it corresponds to switching on the $\textstyle { \frac { 1 } { N } }$ corrections, while keeping $\lambda$ fixed at first order. Since the theory at finite $N$ involves necessarily the light states (that may be taken to decouple in the 't Hooft limit [22]), it is not surprising that these states, as well as their descendants, play an important part in the analysis. The perturbative analysis is technically rather demanding since the strict ’t Hooft limit is a degenerate point where infinitely many states - the analogues of the light states at $h = { \textstyle \frac { 1 } { 2 } } ( 1 + \lambda )$ - have the same conformal dimension and hence can mix in perturbation theory. However, as we have seen, the structure of the theory is sufficiently rigid so as to allow one to understand at least some of the qualitative features.

We should mention that the 2d case we have considered here difers qualitatively from what happens in higher dimensions. In particular, it was shown in [10,11] that for $d \geq 3$ ， the $\textstyle { \frac { 1 } { N } }$ corrections necessarily break the higher spin symmetry to frst order. This is to be contrasted with what we have found here, namely that there are perturbing fields that preserve the symmetry at least to first order.

Perturbations of these ${ \mathcal W } _ { \infty } [ \lambda ]$ algebras, not necessarily preserving the higher spin symmetry, will also be important in order to connect suitable generalisations of these theories to string theory. In particular,it would be interesting to understand what the effect of the exactly marginal perturbing field of the large $\mathcal { N } = 4$ higher spin theory of [44] is. It should be possible to study this question with similar techniques as those used in the present paper.

# Acknowledgements

We thank Stefan Fredenhagen, Rajesh Gopakumar and Igor Klebanov for useful discussions, Maximilian Kelm and Carl Vollenweider for providing us access to their unpublished results [29],and Maximilian Kelm for explanations and discussons. The work of MRG and KJ is supported in parts by the Swiss National Science Foundation. Part of this work was done while we were visiting the GGI during the programme on Higher Spins, Strings and Duality'. We thank the Galileo Galilei Institute for Theoretical Physics for the hospitality and the INFN for partial support. MRG and WL thank IPMU,and WL thanks KEK and the Benasque string workshop for their hospitality during various stages of this work.

# A The free fermion theory at $\lambda = 0$

In this appendix we collect some of the OPEs we have calculated for the free fermion theory. Using Wick's theorem it is not difficult to work out the singular part of the OPEs of these

currents. In particular, we find that

$$
\begin{array} { r l } &  \begin{array} { r l } & { \bar { X } _ { 5 3 } ^ { \prime } ( 1 \bar { x } ) \approx ~ \frac { \bar { X } _ { 5 3 } ^ { \prime } } { ( 1 0 \bar { x } ) ^ { 2 } } } \\ & { \bar { Y } _ { 5 3 } ^ { \prime } ( 1 \bar { x } ) \approx ~ \frac { \bar { Y } _ { 7 3 } ^ { \prime } ( 1 \bar { x } ) } { ( 1 0 \bar { x } ) ^ { 2 } } ~ - \frac { 2 ( \bar { x } - \bar { x } ) ^ { 2 } } { ( 1 0 \bar { x } ) ^ { 2 } } ~ + \frac { \bar { Y } _ { 1 2 } ^ { \prime } ( 1 \bar { x } ) } { ( 1 0 \bar { x } - \bar { x } ) ^ { 2 } } ~ + } \\ & { \bar { Y } _ { 5 3 } ^ { \prime } ( 1 \bar { x } ) \approx ~ \frac { \bar { X } _ { 9 3 } ^ { \prime } } { ( 1 0 \bar { x } ) ^ { 2 } } ~ - \frac { 2 ( \bar { x } - \bar { x } ) ^ { 2 } } { ( 1 0 \bar { x } ) ^ { 2 } } ~ - \frac { \bar { Y } _ { 1 2 } ^ { \prime } ( 1 \bar { x } ) } { ( 1 0 \bar { x } - \bar { x } ) ^ { 2 } } ~ } \\ & { \bar { Y } _ { 1 3 } ^ { \prime } ( 1 \bar { x } ) \approx ~ \frac { \bar { X } _ { 9 3 } ^ { \prime } } { ( 1 0 \bar { x } ) ^ { 2 } } ~ - \frac { 2 ( \bar { x } - \bar { x } ) ^ { 2 } } { ( 1 0 \bar { x } ) ^ { 2 } } ~ - \frac { \bar { Y } _ { 1 2 } ^ { \prime } ( 1 \bar { x } ) } { ( 1 0 \bar { x } ) ^ { 2 } } } \\ & { \bar { Y } _ { 5 3 } ^ { \prime } ( 1 \bar { x } ) \approx ~ \frac { \bar { Y } _ { 1 2 } ^ { \prime } ( 1 \bar { x } ) } { ( 1 0 \bar { x } ) ^ { 2 } } ~ - \frac { 2 ( \bar { x } - \bar { x } ) ^ { 2 } } { ( 1 0 \bar { x } ) ^ { 2 } } ~ } \\ & { \bar { Y } _ { 1 4 } ^ { \prime } ( 1 \bar { x } ) \equiv \frac { \bar { Y } _ { 2 3 } ^ { \prime } ( 1 \bar { x } ) } { ( 1 0 \bar { x } ) ^ { 2 } } ~ \bar { Y } _ { 1 5 } ^ { \prime } ( 1 \bar { x } ) ~ } \\ &  \bar { Y } _ { 1 5 } ^ { \prime } ( 1 \bar { x } ) \equiv \frac { \bar { Y } _ { 1 2 } ^ { \prime } ( 1 \bar { x } ) } { ( 1 0 \bar { x } ) ^ { 2 } } ~ \bar { Y } _ { 1 6 } ^ { \prime } ( 1 \bar { x } ) ~ \bar  \end{array} \end{array}
$$

where $\sim$ always denotes the singular part of the operator product expansion.

# B The free boson theory at $\lambda = 1$

The first few OPEs of the free boson higher spin fields defined in eq. (3.1) are explicitly given by $z _ { 1 2 } \equiv z _ { 1 } - z _ { 2 }$ ）

$$
\begin{array} { r l } { \sum _ { i = 1 } ^ { 3 } | \theta ^ { \mathrm { P } } _ { i , j } | _ { \infty } \sum _ { s = 0 } ^ { 1 } \left( \frac { \kappa _ { i } ^ { 2 } } { s } \right) ^ { 2 } \frac { \kappa _ { i } ^ { 2 } } { s } + \frac { \kappa _ { i } ^ { 2 } } { 2 s } \left( \kappa _ { i } ^ { 2 } \varepsilon _ { i } ^ { 2 } - \frac { 1 } { 3 } \frac { \kappa _ { i } ^ { 2 } } { s } \right) ^ { 2 } \frac { \kappa _ { i } ^ { 3 } } { 2 s } } & { = } \\ { \sum _ { i = 1 } ^ { 3 } | \theta ^ { \mathrm { P } } _ { i , j } | _ { \infty } \left( \kappa _ { i } ^ { 2 } \right) } & { = } & { \kappa _ { i } ^ { 3 } \left[ \frac { \kappa _ { i } ^ { 2 } } { s } \right] _ { \infty } \left( \kappa _ { i } ^ { 2 } \right) ^ { 2 } \frac { \kappa _ { i } ^ { 3 } } { 2 s } + \frac { \kappa _ { i } ^ { 2 } } { 2 s } \left( \kappa _ { i } ^ { 2 } \varepsilon _ { i } ^ { 2 } - \frac { 1 } { 3 } \right) \frac { \kappa _ { i } ^ { 3 } } { 2 s } } \\ & { = } & { \kappa _ { i } ^ { 4 } \frac { \kappa _ { i } ^ { 2 } } { s } + \frac { \kappa _ { i } ^ { 2 } } { 2 s } \left( \kappa _ { i } ^ { 2 } \varepsilon _ { i } ^ { 2 } + \frac { 1 } { 3 } \varepsilon _ { i } ^ { 2 } \right) \frac { \kappa _ { i } ^ { 3 } } { 2 s } + \frac { \kappa _ { i } ^ { 2 } } { 2 s } } \\ & { \quad + \frac { \kappa _ { i } ^ { 2 } } { s } \mu ^ { 4 } \kappa _ { i } ^ { 4 } \left( \kappa _ { i } ^ { 2 } + \kappa _ { i } ^ { 2 } \varepsilon _ { i } ^ { 2 } + \frac { 1 } { 3 } \varepsilon _ { i } ^ { 4 } \right) \kappa _ { i } \varepsilon _ { i } + \frac { \kappa _ { i } ^ { 2 } } { s } } \\ { \sum _ { i = 1 } ^ { 3 } \left( \kappa _ { i } ^ { 2 } \right) _ { \infty } \sum _ { s = 0 } ^ { 3 } \left[ \frac { \kappa _ { i } ^ { 2 } } { s } - \frac { 1 } { 3 } \frac { \kappa _ { i } ^ { 2 } } { s } + \frac { \kappa _ { i } ^ { 2 } } { s } + \frac { 1 } { 2 s } \frac { \kappa _ { i } ^ { 2 } } { s } \right] _ { \infty } \frac { \kappa _ { i } ^ { 2 } } { s } \left( \kappa _ { i } ^ { 2 } \right) } \\ &  \quad + \frac { \kappa _ { i } ^ { 2 } }  s \end{array}
$$

# C Explicit mixing matrices

Using the notation of (5.26), the first few explicit expressions for the $B _ { n }$ are as follows

$\textstyle { \frac { N } { 1 6 \pi g } } B _ { 1 }$

<html><body><table><tr><td></td><td>（；□) (;□）</td></tr><tr><td>(；0)</td><td></td></tr></table></body></html>

$\textstyle { \frac { N } { 1 6 \pi g } } B _ { 2 }$

<html><body><table><tr><td></td><td>（日) (中) （HH日)</td></tr><tr><td>(日；□) (;□）</td><td>0 2+入 0 √3 √(1+入） √2(1-1)</td></tr></table></body></html>

$\begin{array} { r } { { \frac { N } { 1 6 \pi g } } B _ { 3 } } \end{array}$

<html><body><table><tr><td rowspan="2" colspan="2">(田甲)</td><td rowspan="2">（；中)</td><td></td><td>日日</td><td></td><td rowspan="2">;)</td><td rowspan="2">（HHH；)</td></tr><tr><td></td><td></td></tr><tr><td></td><td>0</td><td>0</td><td>0</td><td>√3(-1+>)</td><td>-3</td><td>0</td><td>0</td></tr><tr><td>中)</td><td>V3（1-</td><td>3-</td><td>3（1+x)</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td></td><td>√3(1+入)</td><td>3(-1+λ)</td><td>_3+></td><td></td><td></td><td>0</td><td>0</td></tr><tr><td></td><td>2√2</td><td>4</td><td>4</td><td>0</td><td>0</td><td></td><td></td></tr><tr><td>日）</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>3</td><td>3（1+2）</td></tr></table></body></html>

# D The eigenproblem of a scalar Jacobi matrix

Let us consider the perturbative solution corresponding to $f _ { 1 } = 1$ ，i.e. the solution that involves the original scalar field ${ \mathcal { O } } \equiv ( \sqcup , 0 )$ itself. As was argued in section 5.3, the perturbative analysis will mix to this state one specific linear combination of scalar-like states at each level; thus we can consider the truncated problem,where instead of the ful matrix $M$ （20 we just consider the eigenvalue problem

$$
J \cdot \vec { F } = \rho \vec { F } \qquad \mathrm { w i t h } \quad \vec { F } = ( f _ { 1 } , f _ { 2 } , \ldots )
$$

for the‘scalar Jacobi matrix

$$
J ( \{ a _ { n } \} , \{ b _ { n } \} ) = \left[ { \begin{array} { c c c c c c } { a _ { 1 } } & { b _ { 1 } } & { 0 } & { 0 } & { 0 } & { . . . } \\ { b _ { 1 } } & { a _ { 2 } } & { b _ { 2 } } & { 0 } & { 0 } & { . . . } \\ { 0 } & { b _ { 2 } } & { a _ { 3 } } & { b _ { 3 } } & { 0 } & { . . . } \\ { 0 } & { 0 } & { \ddots } & { \ddots } & { \ddots } & { } \end{array} } \right] ~ ,
$$

where now all $a _ { n }$ and $b _ { n }$ are numbers. This can be solved recursively; since the value of $f _ { 1 }$ only affects the overall normalisation, we can start by setting $f _ { 1 } = 1$ . Then given any $\rho \in \mathbb { C }$ ， we solve for $f _ { n } ( \rho )$ as

$$
\begin{array} { r } { \begin{array} { c c } { f _ { 1 } = 1 } \\ { a _ { 1 } f _ { 1 } + b _ { 1 } f _ { 2 } = \rho f _ { 1 } } \\ { \ldots } \\ { b _ { n - 1 } f _ { n - 1 } + a _ { n } f _ { n } + b _ { n } f _ { n + 1 } = \rho f _ { n } } \\ { \ldots } \end{array} \begin{array} { l } { f _ { 1 } = 1 } \\ { f _ { 2 } = \displaystyle \frac { 1 } { b _ { 1 } } ( \rho - a _ { 1 } ) f _ { 1 } } \\ { \ldots } \\ { f _ { n - 1 } = \displaystyle \frac { 1 } { b _ { n } } \bigl [ ( \rho - a _ { n } ) f _ { n } - b _ { n - 1 } f _ { n - 1 } \bigr ] } \\ { \ldots } \end{array} } \end{array}
$$

Note that, by construction, $f _ { n } ( \rho )$ is a polynomial of degree $n - 1$ in $\rho$ . If the Jacobi matrix is strictly infinite, this is the most general solution.

If the Jacobi matrix truncates to some finite matrix, say to a matrix of size $K \times K -$ this will be the case for finite $N$ and $k$ — then the analysis can be performed similarly. We simply extend the Jacobi matrix to an infinite matrix by choosing the $a _ { n }$ and $b _ { n }$ for $n > K$ arbitrarily. Then we can construct recursive eigenvalues as above. Up to level $K$ the solution agrees with the solution to the actual eigenvalue problem we are interested in, so all we have to require is that the analysis terminates at level $K$ ,i.e. that $f _ { K + 1 } ( \rho ) = 0$ . Since $f _ { n } ( \rho )$ isa polynomial of degree $n - 1$ in $\rho$ ， this gives rise to $K$ different solutions,as expected. Note that if all $a _ { i }$ ， $i = 1 , \ldots , K$ agree, $a _ { i } \equiv a$ ，then $f _ { n } ( \rho )$ is an even (odd) polynomial of $\rho - a$ if （204号 $n$ is odd (even); in this case the eigenvalues will be symmetrically distributed around $\rho = a$ If the diagonal entries exhibit some ‘drift',we expect that also the eigenvalues will become symmetrically distributed w.r.t. some shifted mean.

# References

[1] I.R. Klebanov and A.M. Polyakov,“AdS dual of the critical O(N) vector model,” Phys. Lett. B 550,213 (2002) [arXiv:hep-th/0210114].   
[2] B. Sundborg,‘Stringy gravity, interacting tensionless strings and massess higher spins,” Nucl. Phys. Proc. Suppl. 102, 113(2001) [arXiv:hep-th/0103247].   
[3] E.Witten, talk at the John Schwarz 60-th birthday symposium (Nov. 2001), http://theory.caltech.edu/jhs6o/witten/1.html.   
[4] A. Mikhailov, “Notes on higher spin symmetries,” arXiv:hep-th/0201019.   
[5] E. Sezgin and P. Sundell, “Massless higher spins and holography,” Nucl. Phys.B 644, 303(2002) [Erratum-ibid.B 660, 403 (2003)] [arXiv:hep-th/0205131].   
[6] E. Sezgin and P. Sundell, “Holography in 4D (super) higher spin theories and a test via cubic scalar couplings,” JHEP 0507, 044 （2005) [arXiv:hep-th/0305040].   
[7] M.A. Vasiliev, “Consistent equation for interacting gauge fields of all spins in (3+1)- dimensions,” Phys. Lett. B 243, 378 (1990).   
[8] S.Giombi and X. Yin，“Higher spin gauge theory and holography: the three-point functions,” JHEP 1009,115（2010) [arXiv:0912.3462 [hep-th]].   
[9] S. Giombi and X. Yin,“Higher spins in AdS and twistorial holography,” JHEP 1104, 086（2011） [arXiv:1004.3736 [hep-th]].   
10] J.Maldacena and A. Zhiboedov,“Constraining conformal feld theories with a higher spin symmetry,” J. Phys. A 46, 214011 (2013) [arXiv:1112.1016 [hep-th]].   
[11] J. Maldacena and A. Zhiboedov, “Constraining conformal field theories with a slightly broken higher spin symmetry,” Class. Quant. Grav. 30， 104003 (2013) [arXiv:1204.3882 [hep-th]].   
[12] O. Aharony, G. Gur-Ari and R. Yacoby, “d=3 bosonic vector models coupled to ChernSimons gauge theories,” JHEP 1203,037 (2012) [arXiv:1110.4382 [hep-th]].   
[13] S. Giombi, S.Minwall, S.Prakash, S.P. Trivedi, S.R. Wadia and X. Yin,“Chern-Simons theory with vector fermion matter,” Eur. Phys. J. C 72, 21l2 (2012) [arXiv:1110.4386 [hep-th]].   
[14] C.-M. Chang, S. Minwalla, T. Sharma and X. Yin,“ABJ triality: from higher spin fields to strings,” J. Phys. A 46, 214009 (2013) [arXiv:1207.4485 [hep-th]].   
[15] M.R. Gaberdiel and R. Gopakumar,“An AdS $^ 3$ dual for minimal model CFTs,” Phys. Rev.D 83,066007 (2011） [arXiv:1011.2986 [hep-th]].   
[16] S.F. Prokushkin and M.A. Vasiliev,“Higher spin gauge interactions for massive matter fields in 3d AdS space-time,” Nucl. Phys.B 545, 385 (1999) [arXiv:hep-th/9806236 [hep-th]].   
[17] S.F Prokushkin and M.A. Vasiliev,“3-d higher spin gauge theories with matter,” arXiv:hep-th/9812242 [hep-th].   
[18] M. Henneaux and S.J. Rey， “Nonlinear W(infinity) algebra as asymptotic symmetry of three-dimensional higher spin Anti-de Sitter gravity,” JHEP 1012, O07 (2010) [arXiv:1008.4579 [hep-th]].   
[19] A. Campoleoni, S. Fredenhagen, S. Pfenninger and S. Theisen,“Asymptotic symmetries of three-dimensional gravity coupled to higher-spin fields,” JHEP 1011， O07 (2010) [arXiv:1008.4744 [hep-th]].   
[20] M.R. Gaberdiel and T. Hartman,“Symmetries of holographic minimal models,” JHEP 1105,031(2011） [arXiv:1101.2910 [hep-th]].   
[21] A. Campoleoni, S.Fredenhagen and S. Pfenninger,“Asymptotic W-symmetries in threedimensional higher-spin gauge theories,” JHEP 1109,113 (2011） [arXiv:1107.0290 [hep-th]].   
[22] M.R. Gaberdiel, R. Gopakumar, T. Hartman， and S. Raju,“Partition functions of holographic minimal models,” JHEP 1108, 077 (2011) [arXiv:1106.1897 [hep-th]].   
[23] M.R. Gaberdiel and R. Gopakumar，“Triality in minimal model holography,” JHEP 1207,127(2012)[arXiv:1205.2472 [hep-th]].   
[24] M.R. Gaberdiel and P. Suchanek, “Limits of minimal models and continuous orbifolds," JHEP 1203,014 (2012) [arXiv:1112.1708 [hep-th]].   
[25] E. Bergshoeff, M.P. Blencowe and K.S. Stelle, “Area preserving diffeomorphisms and higher spin algebra,” Commun.Math. Phys. 128, 213 (1990).   
[26] E. Bergshoef, C.N. Pope, L.J. Romans, E. Sezgin and X. Shen,“The super W(infinity) algebra,” Phys. Lett. B 245, 447 (1990).   
[27] D.A. Depireux,“Fermionic realization of W(1+infinity),” Phys. Lett.B 252, 586 (1990).   
[28] M.R. Gaberdiel, T. Hartman and K. Jin，“Higher spin black holes from CFT,” JHEP 1204,103（2012)[arXiv:1203.0015 [hep-th]].   
[29] M. Kelm and C. Vollenweider, private communication.   
[30] P. Di Francesco, P. Mathieu and D. Sénéchal, “Conformal Field Theory,” Springer (1997).   
[31] S.Banerjee, S. Hellrman, J. Maltz and S.H. Shenker，“Light states in Chern-Simons theory coupled to fundamental matter,” JHEP 1303, 097 (2013) [arXiv:1207.4195 [hep-th]].   
[32] I. Bakas and E. Kiritsis, “Bosonic realisation of a universal W algebra and Z $\infty$ parafermions,” Nucl. Phys. B 343,185 (1990) [Erratum ibid. B 350, 512 (1991)].   
[33] S. Fredenhagen, M.R. Gaberdiel and C.A. Keller, “Symmetries of perturbed conformal field theories,” J. Phys. A 40,13685 (2007) [arXiv:0707.2511 [hep-th]].   
[34] J.L. Cardy, “Conformal invariance and statistical mechanics,” in: Les Houches XLIX (1988)， Fields， Strings and Critical Phenomena, eds. E. Brezin and J. Zinn-Justin, North-Holland (1990).   
[35] S. Chaudhuri and J.A. Schwartz,“A criterion for integrably marginal operators,” Phys. Lett. B 219,291 (1989).   
[36] C.-M. Chang and X. Yin,“A semi-local holographic minimal model,” arXiv: 1302.4420 [hep-th].   
[37] J.L. Cardy,“Continuously varying exponents and the value of the central charge,” J. Phys. A 20, L891 (1987).   
[38] A.B. Zamolodchikov,“Integrals of motion in scaling three state Potts model field theory,” Int. J. Mod. Phys. A 3, 743 (1988).   
[39] A.B. Zamolodchikov,“Integrable feld theory from conformal field theory,” in: Integrable Systems in Quantum Field Theory and Statistical Mechanics, Adv. Studies in Pure Mathematics 19, 641 (1989).   
[40] R.P. Stanley， “Enumerative combinatorics,” 2nd ed.， Cambridge University Press (2012).   
[41] C.-M. Chang and X. Yin, “Correlators in $W _ { N }$ minimal model revisited,” JHEP 1210, 050（2012)[arXiv:1112.5459 [hep-th]].   
[42] A. Jevicki and J. Yoon, “Field theory of primaries in $\mathrm { W } _ { N }$ minimal models," arXiv:1302.3851 [hep-th].   
[43] K. Papadodimas and S. Raju, “Correlation functions in holographic minimal models,” Nucl. Phys. B 856,607(2012) [arXiv:1108.3077 [hep-th]].   
[44] M.R. Gaberdiel and R. Gopakumar， “Large $\mathcal { N } = 4$ holography,” arXiv:1305.4181 [hep-th].