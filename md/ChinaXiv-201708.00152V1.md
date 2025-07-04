# CHIRAL GRAVITY IN THREE DIMENSIONS

Wei Li, Wei Song1 and Andrew Strominger

Center for the Fundamental Laws of Nature Jefferson Physical Laboratory， Harvard University， Cambridge MA O2138， USA

# Abstract

Three dimensional Einstein gravity with negative cosmological constant $- 1 / \ell ^ { 2 }$ deformed by a gravitational Chern-Simons action with coefficient $1 / \mu$ is studied in an asymptotically $A d S _ { 3 }$ spacetime.It is argued to violate unitary or positivity for generic $\mu$ due to negativeenergy massive gravitons. However at the critical value $\mu \ell = 1$ ，the massive gravitons disappear and BTZ black holes all have mass and angular momentum related by $\ell M = J$ . The corresponding chiral quantum theory of gravity is conjectured to exist and be dual to a purely right-moving boundary CFT with central charges $\left( c _ { L } , c _ { R } \right) =$ $( 0 , 3 \ell / G )$

# Contents

1 Introduction 1

2Topologically Massive Gravity 4

2.1 Action 4   
2.2 $A d S _ { 3 }$ vacuum solution 5   
2.3 Chiral gravity 5

3Gravitons in $A d S _ { 3 }$ 6

4 Positivity of energy 11

4.1 BTZ black holes . 11   
4.2 Gravitons 12

5 Conclusion and Discussion 14

# 1 Introduction

In three dimensions, the Riemann and Ricci tensor both have the same number (six) of independent components. Hence Einstein's equation，with or without a cosmological constant $\Lambda$ ， completely constrains the geometry and there are no local propagating degrees of freedom. At first sight this makes the theory sound too trivial to be interesting. However in the case of a negative cosmological constant, there are asymptotically $A d S _ { 3 }$ black hole solutions [1] as well as massess gravitons which can be viewed as propagating on the boundary. These black holes obey the laws of black hole thermodynamics and have an entropy given by one-quarter the horizon area. This raises the interesting question: what is the microscopic origin of the black hole entropy in these “trivial” theories?

In order to address this question one must quantize the theory. One proposal [2] is to recast it as an $S L ( 2 , \mathbb { R } ) _ { L } \times S L ( 2 , \mathbb { R } ) _ { R }$ Chern-Simons gauge theory with $k _ { L } = k _ { R }$ .Despite some effort this approach has not given a clear accounting of the black hole entropy (see however [3] for an interesting attempt). So the situation remains unsatisfactory.

More might be learned by deforming the theory with the addition of the gravitational Chern-Simons term with coefficient $\textstyle { \frac { 1 } { \mu } }$ [4][5]. The resulting theory is known as the topologically massive gravity (TMG） and contains a local， massive propagating degree of freedom，as well as black holes and massless boundary gravitons. The addition of the Chern-Simons term leads to more degrees of freedom because it contains three, rather than just two, derivatives of the metric. It is the purpose of this note to study this theory for negative $\Lambda = - 1 / \ell ^ { 2 }$ . We will argue that the theory is unstable/inconsistent for generic $\mu$ : either the massive gravitons or BTZ black holes have negative energy. The exception occurs when the parameters obey $\mu \ell = 1$ ，at which point several interesting phenomena simultaneously arise:

(i) The central charges of the dual boundary CFT become $c _ { L } = 0$ ， $c _ { R } = { }$ $3 \ell / G$ ： (ii) The conformal weights as well as the wave function of the massive graviton， generically ${ \textstyle \frac { 1 } { 2 } } ( 3 + \mu \ell , - 1 + \mu \ell )$ ，degenerate with those of the leftmoving weight $( 2 , 0 )$ massless boundary graviton. They are both pure gauge, but the gauge transformation parameter does not vanish at infinity. (iii) BTZ black holes and all gravitons have non-negative masses. Further the angular momentum is fixed in terms of the mass to be $J = M { \boldsymbol { \ell } }$ ：

This suggests the possibility of a stable, consistent theory at $\mu \ell = 1$ （204号 which is dual to a holomorphic boundary CFT (i.e. containing only rightmoving degrees of freedom） with $c _ { R } ~ = ~ 3 \ell / G$ . The hope - which remains to be investigated - is that for a suitable choice of boundary conditions the zero-energy left-moving excitations can be discarded as pure gauge. We will refer to this theory as 3D chiral gravity. As we will review herein, if such a dual CFT exists, and is unitary, an application of the Cardy formula gives a microscopic derivation of the black hole entropy [6][7][8].

Related recent work [9]-[16] has considered an alternative deformation of pure 3D gravity, locally described by the $S L ( 2 , \mathbb { R } ) _ { L } \times S L ( 2 , \mathbb { R } ) _ { R }$ ChernSimons gauge theory with $k _ { L } \neq k _ { R }$ . This is a purely topological theory with no local degrees of freedom and is not equivalent to TMG. It contains all the subset of solutions of TMG which are Einstien metrics but not the massive gravitons. It is nevertheless possible that the arguments given in [9] (adapted to the case $k _ { L } = 0$ as in [1O]） which are quite general apply to the chiral gravity discussed herein. Indeed discrepancies with the semiclassical analysis mentioned in [9]-[16] disappear for the special case $k _ { L } = 0$ .2 Moreover the main assumption of 9] - holomorphic factorization of the partition function - is simply a consistency requirement for chiral gravity because there are only right movers.

The paper is organized as follows. Section 2 gives a brief review of the cosmological TMG and its $A d S _ { 3 }$ vacuum solution, and shows that the theory is purely chiral at the special value of $\mu = 1 / \ell$ .Section 3 describes the linearized gravitational excitations around $A d S _ { 3 }$ ． Section 4 shows how the positivity of energy imposes a stringent constraint on the allowed value of $\mu$ We end with a short summary and discussion of future directions.

# 2 Topologically Massive Gravity

# 2.1 Action

The action for TMG (topologically massive gravity） with a negative cosmological constant is [17]

$$
I = \frac { 1 } { 1 6 \pi G } \int d ^ { 3 } x \sqrt { - g } ( R - 2 \Lambda ) + \frac { 1 } { 1 6 \pi G \mu } I _ { C S }
$$

where $I _ { c s }$ is the Chern-Simons term

$$
I _ { c s } = \frac { 1 } { 2 } \int d ^ { 3 } x \sqrt { - g } \epsilon ^ { \lambda \mu \nu } \Gamma _ { \lambda \sigma } ^ { \rho } [ \partial _ { \mu } \Gamma _ { \rho \nu } ^ { \sigma } + \frac { 2 } { 3 } \Gamma _ { \mu \tau } ^ { \sigma } \Gamma _ { \nu \rho } ^ { \tau } ]
$$

and we take $\Lambda$ negative. We have chosen the sign in front of the EinsteinHilbert action so that BTZ black holes have positive energy for large $\mu$ , while the massive gravitons will turn out to have negative energy for this choice.3 The equation of motion is

$$
\mathcal { G } _ { \mu \nu } + \frac { 1 } { \mu } C _ { \mu \nu } = 0 ~ ,
$$

where $\mathcal { G } _ { \mu \nu }$ is the cosmological-constant-modified Einstein tensor:

$$
\mathcal { G } _ { \mu \nu } \equiv R _ { \mu \nu } - \frac { 1 } { 2 } g _ { \mu \nu } R + \Lambda g _ { \mu \nu }
$$

and $C _ { \mu \nu }$ is the Cotton tensor

$$
C _ { \mu \nu } \equiv \epsilon _ { \mu } ^ { ~ \alpha \beta } \nabla _ { \alpha } ( R _ { \beta \nu } - \frac { 1 } { 4 } g _ { \beta \nu } R ) .
$$

Einstein metrics with $\mathcal { G } _ { \mu \nu } = ~ 0$ are a subset of the general solutions of (3)

# 2.2 （204号 $A d S _ { 3 }$ vacuum solution

TMG has an $A d S _ { 3 }$ solution:

$$
d s ^ { 2 } = \bar { g } _ { \mu \nu } d x ^ { \mu } d x ^ { \nu } = \ell ^ { 2 } ( - \cosh ^ { 2 } { \rho } d \tau ^ { 2 } + \sinh ^ { 2 } { \rho } d \phi ^ { 2 } + d \rho ^ { 2 } )
$$

where the radius is related to $\Lambda$ by

$$
\ell ^ { - 2 } = - \Lambda
$$

The Riemann tensor, Ricci tensor and Ricci scalar of the $A d S _ { 3 }$ are:

$$
\bar { R } _ { \mu \alpha \nu \beta } = \Lambda ( \bar { g } _ { \mu \nu } \bar { g } _ { \alpha \beta } - \bar { g } _ { \mu \beta } \bar { g } _ { \alpha \nu } ) , \quad \bar { R } _ { \mu \nu } = 2 \Lambda \bar { g } _ { \mu \nu } , \quad \bar { R } = 6 \Lambda ,
$$

The metric (6) has isometry group $S L ( 2 , \mathbb { R } ) _ { L } \times S L ( 2 , \mathbb { R } ) _ { R }$ . The $S L ( 2 , \mathbb { R } ) _ { L }$ generators are

$$
\begin{array} { r c l } { { { \cal L } _ { 0 } } } & { { = } } & { { i \partial _ { u } ~ , } } \\ { { { \cal L } _ { - 1 } } } & { { = } } & { { i e ^ { - i u } \displaystyle \left[ \displaystyle \frac { \cosh 2 \rho } { \sinh 2 \rho } \partial _ { u } - \displaystyle \frac { 1 } { \sinh 2 \rho } \partial _ { v } + \displaystyle \frac { i } { 2 } \partial _ { \rho } \right] ~ , } } \\ { { { \cal L } _ { 1 } } } & { { = } } & { { i e ^ { i u } \displaystyle \left[ \displaystyle \frac { \cosh 2 \rho } { \sinh 2 \rho } \partial _ { u } - \displaystyle \frac { 1 } { \sinh 2 \rho } \partial _ { v } - \displaystyle \frac { i } { 2 } \partial _ { \rho } \right] } } \end{array}
$$

where $\boldsymbol { u } \equiv \boldsymbol { \tau } + \boldsymbol { \phi } , \boldsymbol { v } \equiv \boldsymbol { \tau } - \boldsymbol { \phi }$ . The $S L ( 2 , \mathbb { R } ) _ { R }$ generators $\{ L _ { 0 } , L _ { \pm 1 } \}$ are given by the above expressions with $u  v$ . The normalization of the $S L ( 2 , \mathbb { R } )$ algebra is

$$
\left[ L _ { 0 } , L _ { \pm 1 } \right] = \mp L _ { \pm 1 } , \left[ L _ { 1 } , L _ { - 1 } \right] = 2 L _ { 0 } .
$$

The quadratic Casimir of $S L ( 2 , \mathbb { R } ) _ { L }$ is $\begin{array} { r } { L ^ { 2 } = \frac { 1 } { 2 } ( L _ { 1 } L _ { - 1 } + L _ { - 1 } L _ { 1 } ) - L _ { 0 } ^ { 2 } } \end{array}$ . When acting on scalars, $\begin{array} { r } { L ^ { 2 } + \bar { L } ^ { 2 } = - \frac { \ell ^ { 2 } } { 2 } \bar { \nabla } ^ { 2 } } \end{array}$ [18].

# 2.3 Chiral gravity

As shown by Brown and Henneaux [19], quantum gravity on asymptotically $A d S _ { 3 }$ spacetimes with appropriate boundary conditions is described by a 2D CFT which lives on the boundary. They computed the total central charge of the CFT and found $c _ { L } + c _ { R } = 3 \ell / G$ . Simplified calculations were given in [20][21][22]． The difference $c _ { L } - c _ { R }$ corresponds to the diffeomorphism anomaly. In reference [8][23] it is shown that $\begin{array} { r } { c _ { L } - c _ { R } = - \frac { 3 } { \mu G } } \end{array}$ .In summary, we have

$$
c _ { L } = \frac { 3 \ell } { 2 G } ( 1 - \frac { 1 } { \mu \ell } ) \qquad c _ { R } = \frac { 3 \ell } { 2 G } ( 1 + \frac { 1 } { \mu \ell } )
$$

In order that both central charges are non-negative,we must have,as was also noticed in [24],

$$
\mu \ell \geqslant 1
$$

We note that had we chosen the opposite sign in front of the Einstein-Hilbert action the central charge would be negative. An interesting special case is

$$
\mu \ell = 1
$$

which implies

$$
c _ { L } = 0 , \qquad c _ { R } = \frac { 3 \ell } { G } .
$$

We will refer to this theory as chiral gravity. If the chiral gravity is unitary it can have only right-moving excitations.

# 3 Gravitons in $A d S _ { 3 }$

In this section we describe the linearized excitations around background $A d S _ { 3 }$ metric $g _ { \mu \nu }$ . Expanding

$$
g _ { \mu \nu } = \bar { g } _ { \mu \nu } + h _ { \mu \nu }
$$

with $h _ { \mu \nu }$ small, the linearized Ricci tensor and Ricci scalar are [25] [26]

$$
\begin{array} { r c l } { { R _ { \mu \nu } ^ { ( 1 ) } } } & { { = } } & { { \displaystyle \frac { 1 } { 2 } ( - \bar { \nabla } ^ { 2 } h _ { \mu \nu } - \bar { \nabla } _ { \mu } \bar { \nabla } _ { \nu } h + \bar { \nabla } ^ { \sigma } \bar { \nabla } _ { \nu } h _ { \sigma \mu } + \bar { \nabla } ^ { \sigma } \bar { \nabla } _ { \mu } h _ { \sigma \nu } ) } } \\ { { R ^ { ( 1 ) } } } & { { \equiv } } & { { ( R _ { \mu \nu } g ^ { \mu \nu } ) ^ { ( 1 ) } = - \bar { \nabla } ^ { 2 } h + \bar { \nabla } _ { \mu } \bar { \nabla } _ { \nu } h ^ { \mu \nu } - 2 \Lambda h . } } \end{array}
$$

The leading terms in $\mathcal { G }$ and $C$ are

$$
\begin{array} { r c l } { { \displaystyle \mathcal { G } _ { \mu \nu } ^ { ( 1 ) } } } & { { = } } & { { R _ { \mu \nu } ^ { ( 1 ) } - \frac { 1 } { 2 } \bar { g } _ { \mu \nu } R ^ { ( 1 ) } - 2 \Lambda h _ { \mu \nu } , } } \\ { { \displaystyle C _ { \mu \nu } ^ { ( 1 ) } } } & { { = } } & { { \epsilon _ { \mu } ^ { \alpha \beta } \bar { \nabla } _ { \alpha } \left( R _ { \beta \nu } ^ { ( 1 ) } - \frac { 1 } { 4 } \bar { g } _ { \beta \nu } R ^ { ( 1 ) } - 2 \Lambda h _ { \beta \nu } \right) . } } \end{array}
$$

We note $\overline { { \mathrm { T r } } } C ^ { ( 1 ) } = 0$ and the Bianchi identity implies $\bar { \nabla } ^ { \mu } \mathcal { G } _ { \mu \nu } ^ { ( 1 ) } = \bar { \nabla } ^ { \mu } C _ { \mu \nu } ^ { ( 1 ) } = 0$ ： The linearized equations of motion are then

$$
{ \mathcal G } _ { \mu \nu } ^ { ( 1 ) } + \frac { 1 } { \mu } { C } _ { \mu \nu } ^ { ( 1 ) } = 0
$$

Tracing this equation yields ${ \overline { { \mathrm { T r } } } } { \mathcal { G } } ^ { ( 1 ) } = - { \textstyle \frac { 1 } { 2 } } R ^ { ( 1 ) } = 0$ . So the equation of motion becomes

$$
\mathcal { G } _ { \mu \nu } ^ { ( 1 ) } + \frac { 1 } { \mu } \epsilon _ { \mu } ^ { \phantom { \dagger } } { } ^ { \alpha \beta } \bar { \nabla } _ { \alpha } \mathcal { G } _ { \beta \nu } ^ { ( 1 ) } = 0
$$

where in terms of $h _ { \mu \nu }$

$$
{ \mathcal G } _ { \mu \nu } ^ { ( 1 ) } = \frac { 1 } { 2 } ( - \bar { \nabla } ^ { 2 } h _ { \mu \nu } - \bar { \nabla } _ { \mu } \bar { \nabla } _ { \nu } h + \bar { \nabla } ^ { \sigma } \bar { \nabla } _ { \nu } h _ { \sigma \mu } + \bar { \nabla } ^ { \sigma } \bar { \nabla } _ { \mu } h _ { \sigma \nu } ) - 2 \Lambda h _ { \mu \nu }
$$

Now we fix the gauge. We define $\bar { h } _ { \mu \nu } \equiv h _ { \mu \nu } - \bar { g } _ { \mu \nu } h$ ， which gives $\tilde { h } = - 2 h$ Plugging $h _ { \mu \nu } = \tilde { h } _ { \mu \nu } - { \textstyle \frac { 1 } { 2 } } \bar { g } _ { \mu \nu } \tilde { h }$ into (19) and setting it to zero gives

$$
\bar { \nabla } _ { \mu } \bar { \nabla } _ { \nu } \tilde { h } ^ { \mu \nu } = - \Lambda \tilde { h }
$$

Thus, the gauge

$$
\bar { \nabla } _ { \mu } \tilde { h } ^ { \mu \nu } = 0
$$

together with the linearized equation of motion implies tracelessness of $h _ { \mu \nu }$ ： （20 $\tilde { h } = - 2 h = 0$ . This gauge is equivalent to the harmonic plus traceless gauge $\bar { \nabla } _ { \mu } h ^ { \mu \nu } = h = 0$ . Noting that

$$
[ \bar { \nabla } _ { \sigma } , \bar { \nabla } _ { \mu } ] h _ { \nu } ^ { \sigma } = \bar { R } ^ { \sigma } { } _ { \lambda \sigma \mu } h _ { \nu } ^ { \lambda } - \bar { R } ^ { \lambda } { } _ { \nu \sigma \mu } h _ { \lambda } ^ { \sigma } = 3 \Lambda h _ { \mu \nu } - \Lambda h g _ { \mu \nu }
$$

and imposing the gauge condition, (24) is just

$$
{ \mathcal G } _ { \mu \nu } ^ { ( 1 ) } = \frac { 1 } { 2 } ( - \bar { \nabla } ^ { 2 } h _ { \mu \nu } + 2 \Lambda h _ { \mu \nu } \ ) \ .
$$

The equation of motion (23) thus becomes

$$
( \bar { \nabla } ^ { 2 } + { \frac { 2 } { \ell ^ { 2 } } } ) ( h _ { \mu \nu } + { \frac { 1 } { \mu } } \epsilon _ { \mu } { } ^ { \alpha \beta } \bar { \nabla } _ { \alpha } h _ { \beta \nu } ) = 0
$$

Define three mutually commuting operators $( \mathcal { D } ^ { L } , \mathcal { D } ^ { R } , \mathcal { D } ^ { M } )$

$$
( \mathcal { D } ^ { L / R } ) _ { \mu } { } ^ { \beta } \equiv \delta _ { \mu } { } ^ { \beta } \pm \ell \epsilon _ { \mu } { } ^ { \alpha \beta } \bar { \nabla } _ { \alpha } , \qquad \mathrm { a n d } \qquad ( \mathcal { D } ^ { M } ) _ { \mu } { } ^ { \beta } \equiv \delta _ { \mu } { } ^ { \beta } + \frac { 1 } { \mu } \epsilon _ { \mu } { } ^ { \alpha \beta } \bar { \nabla } _ { \alpha }
$$

where the meaning of superscripts will become clear presently. The equations of motion (23) can then be written as

$$
( { \mathcal { D } } ^ { L } { \mathcal { D } } ^ { R } { \mathcal { D } } ^ { M } h ) _ { \mu \nu } = 0
$$

where we have used the linearized Bianchi identity. Since the three operators commute equation (31） has three branches of solutions. First, the massive gravitons $h _ { \mu \nu } ^ { M }$ given by

$$
( { \cal D } ^ { M } h ^ { M } ) _ { \mu \nu } = h _ { \mu \nu } ^ { M } + { \frac { 1 } { \mu } } \epsilon _ { \mu } ^ { \ \alpha \beta } \bar { \nabla } _ { \alpha } h _ { \beta \nu } ^ { M } = 0
$$

are solutions special for TMG. The other two branches are massless gravitons which are also solutions of Einstein gravity: $\mathcal { G } _ { \mu \nu } ^ { ( 1 ) } = 0$ The left-mover $h _ { \mu \nu } ^ { L }$ （204号 and right-mover $h _ { \mu \nu } ^ { R }$ have different first order equations of motion:

$$
( { \cal D } ^ { L } h ^ { L } ) _ { \mu \nu } = h _ { \mu \nu } ^ { L } + \ell \epsilon _ { \mu } ^ { \alpha \beta } \bar { \nabla } _ { \alpha } h _ { \beta \nu } ^ { L } = 0 \qquad ( { \cal D } ^ { R } h ^ { R } ) _ { \mu \nu } = h _ { \mu \nu } ^ { R } - \ell \epsilon _ { \mu } ^ { \alpha \beta } \bar { \nabla } _ { \alpha } h _ { \beta \nu } ^ { R } = 0
$$

Note that the components of (32) and (33) tangent to the $A d S _ { 3 }$ boundary relate those components of $h _ { \mu \nu }$ to their falloff at infinity. This could be used to directly infer their conformal weights but we will instead just find the full solutions.

Next we solve for the three branches of solutions. Define linear operator $( \bar { D } ^ { M } ) _ { \mu } { } ^ { \beta } \equiv \delta _ { \mu } { } ^ { \beta } - { \textstyle \frac { 1 } { \mu } } \epsilon _ { \mu } { } ^ { \alpha \beta } \bar { \nabla } _ { \alpha }$ ， which commutes with $\mathcal { D } ^ { M }$ defined earlier. Applying $\tilde { \mathcal { D } } ^ { M }$ on (23), we get a second order equation,

$$
( \tilde { D } ^ { M } \mathcal D ^ { M } \mathcal G ^ { ( 1 ) } ) _ { \mu \nu } = ( \mathcal D ^ { M } \tilde { D } ^ { M } \mathcal G ^ { ( 1 ) } ) _ { \mu \nu } = - \frac { 1 } { \mu ^ { 2 } } [ \bar { \nabla } ^ { 2 } - ( \mu ^ { 2 } + 3 \Lambda ) ] \mathcal G _ { \mu \nu } ^ { ( 1 ) } = 0
$$

where we have used the linearized Bianchi identity. Note that $\tilde { \mathcal { D } } ^ { M } \mathcal { G } = 0$ is just the linearized gravitational wave equation if we exchange $\mu$ for $- \mu$ . So solutions of TMG with both signs of $\mu$ are solutions of (34). It can conversely be shown that all solutions of (34) are solutions of TMG for one sign of $\mu$ or the other.

Rewrite the Laplacian acting on rank two tensors in terms of the sum of two $S L ( 2 , \mathbb { R } )$ Casimirs:

$$
\bar { \nabla } ^ { 2 } h _ { \mu \nu } = - [ \frac { 2 } { \ell ^ { 2 } } ( L ^ { 2 } + \bar { L } ^ { 2 } ) + \frac { 6 } { \ell ^ { 2 } } ] h _ { \mu \nu }
$$

$\mathcal { G } _ { \mu \nu } ^ { ( 1 ) }$ can be written as

$$
{ \mathcal G } _ { \mu \nu } ^ { ( 1 ) } = [ \frac { 1 } { \ell ^ { 2 } } ( L ^ { 2 } + \bar { L } ^ { 2 } ) + \frac { 2 } { \ell ^ { 2 } } ] h _ { \mu \nu } ~ .
$$

Thus(34) becomes

$$
[ - \frac { 2 } { \ell ^ { 2 } } ( L ^ { 2 } + \bar { L } ^ { 2 } ) - \frac { 3 } { \ell ^ { 2 } } - \mu ^ { 2 } ] [ \frac { 1 } { \ell ^ { 2 } } ( L ^ { 2 } + \bar { L } ^ { 2 } ) + \frac { 2 } { \ell ^ { 2 } } ] h _ { \mu \nu } = 0 \ .
$$

This allows us to use the $S L ( 2 , \mathbb { R } ) _ { L } \times S L ( 2 , \mathbb { R } ) _ { R }$ algebra to classify the solutions of (34). Consider states with weight $( h , \bar { h } )$

$$
{ \cal L } _ { 0 } | \psi _ { \mu \nu } \rangle = h | \psi _ { \mu \nu } \rangle , \qquad \bar { \cal L } _ { 0 } | \psi _ { \mu \nu } \rangle = \bar { h } | \psi _ { \mu \nu } \rangle .
$$

From the explicit form of the generators, we see

$$
\psi _ { \mu \nu } = e ^ { - i h u - i \bar { h } v } F _ { \mu \nu } ( \rho )
$$

Now let's specialize to primary states $| \psi _ { \mu \nu } \rangle$ which obey $L _ { 1 } | \psi _ { \mu \nu } \rangle = L _ { 1 } | \psi _ { \mu \nu } \rangle =$ 0. These conditions plus the gauge conditions give $h - h = \pm 2$ and

$$
F _ { \mu \nu } ( \rho ) = f ( \rho ) \left( \begin{array} { c c c } { { 1 } } & { { \frac { h - \bar { h } } { 2 } } } & { { \frac { i } { \sinh ( \rho ) \cosh ( \rho ) } } } \\ { { \frac { h - \bar { h } } { 2 } } } & { { 1 } } & { { \frac { i ( h - \bar { h } ) } { 2 \sinh ( \rho ) \cosh ( \rho ) } } } \\ { { \frac { i } { \sinh ( \rho ) \cosh ( \rho ) } } } & { { \frac { i ( h - \bar { h } ) } { 2 \sinh ( \rho ) \cosh ( \rho ) } } } & { { - \frac { 1 } { \sinh ^ { 2 } ( \rho ) \cosh ^ { 2 } ( \rho ) } } } \end{array} \right)
$$

where

$$
\partial _ { \rho } f ( \rho ) + \frac { ( h + \bar { h } ) \sinh ^ { 2 } \rho - 2 \cosh ^ { 2 } \rho } { \sinh \rho \cosh \rho } f ( \rho ) = 0
$$

for the primary states. The solution is

$$
f ( \rho ) = ( \cosh \rho ) ^ { - ( h + \bar { h } ) } \sinh ^ { 2 } \rho
$$

We see that $\sqrt { - \bar { g } } \psi ^ { \mu \nu * } \psi _ { \mu \nu } = 4 \sinh \rho$ （2 $( \cosh \rho ) ^ { - 3 - 2 ( h + h ) }$ . Also using $L ^ { 2 } | \psi _ { \mu \nu } \rangle =$ $- h ( h - 1 ) | \psi _ { \mu \nu } \rangle$ for primaries,the primary weights $( h , h )$ obey:

$$
[ 2 h ( h - 1 ) + 2 \bar { h } ( \bar { h } - 1 ) - 3 - \mu ^ { 2 } \ell ^ { 2 } ] [ h ( h - 1 ) + \bar { h } ( \bar { h } - 1 ) - 2 ] = 0 , \quad h - \bar { h } = \pm 2
$$

There are two branches of solutions. The first branch has $h ( h - 1 ) + h ( h -$ $1 ) - 2 = 0$ ，which gives:

$$
h = \frac { 3 \pm 1 } { 2 } , \bar { h } = \frac { - 1 \pm 1 } { 2 } \quad \mathrm { o r } \quad h = \frac { - 1 \pm 1 } { 2 } , \bar { h } = \frac { 3 \pm 1 } { 2 }
$$

These are the solutions that already appear in Einstein gravity. The solutions with the lower sign will blow up at the infinity, so we will only keep the upper ones corresponding to weights $( 2 , 0 )$ and $( 0 , 2 )$ .Wewill referto these as left and right-moving massless gravitons.

The second branch has $2 h ( h - 1 ) + 2 h ( h - 1 ) - 3 - \mu ^ { 2 } \ell ^ { 2 } = 0$ , which gives:

$$
\begin{array} { r l } { { \displaystyle h = \frac { 3 } { 2 } \pm \frac { \mu \ell } { 2 } \qquad } } & { { \bar { h } = - \frac { 1 } { 2 } \pm \frac { \mu \ell } { 2 } } } \\ { { \mathrm { o r } \qquad h = - \displaystyle \frac { 1 } { 2 } \pm \frac { \mu \ell } { 2 } \qquad } } & { { \bar { h } = \displaystyle \frac { 3 } { 2 } \pm \frac { \mu \ell } { 2 } } } \end{array}
$$

where (45) are the solutions of (23),and (46) are the solutions of (23) with $\mu$ replaced by $- \mu$ . In the case of interest $\mu \geq 1 / \ell$ ， only the solutions with the plus signs in (45) will not blow up at the infinity. Hence the relevant solutions corresponding to massive gravitons are

$$
h = \frac { 3 } { 2 } + \frac { \mu \ell } { 2 } , \qquad \bar { h } = - \frac { 1 } { 2 } + \frac { \mu \ell } { 2 } .
$$

Descendants are obtained by simply applying $L _ { - 1 }$ and $L _ { - 1 }$ on the primary $| \psi _ { \mu \nu } \rangle$ ：

Note that for chiral gravity at $\mu \ell = 1$ ，with $\begin{array} { r } { c _ { L } = 0 , c _ { R } = \frac { 3 l } { G } } \end{array}$ ，（47) becomes $h \ = \ 2$ ， $\bar { h } \ = \ 0$ . Furthermore the wave function for the massive graviton becomes identical to that of the left-moving massless graviton. In fact， we can eliminate the $( 2 , 0 )$ modes with the residual gauge transformation

$$
\begin{array} { r c l } { { \epsilon _ { t } } } & { { = } } & { { e ^ { - 2 i u } { \displaystyle \frac { i \sinh ^ { 4 } ( \rho ) } { 6 \cosh ^ { 2 } ( \rho ) } } ~ , } } \\ { { } } & { { } } & { { } } \\ { { \epsilon _ { \phi } } } & { { = } } & { { e ^ { - 2 i u } { \displaystyle \frac { - i \sinh ^ { 2 } ( \rho ) \left( 2 + \cosh ^ { 2 } ( \rho ) \right) } { 6 \cosh ^ { 2 } ( \rho ) } } ~ , } } \\ { { } } & { { } } & { { } } \\ { { \epsilon _ { \rho } } } & { { = } } & { { e ^ { - 2 i u } { \displaystyle \frac { \sinh ( \rho ) \left( 1 + 2 \cosh ^ { 2 } ( \rho ) \right) } { 6 \cosh ^ { 3 } ( \rho ) } } ~ , } } \end{array}
$$

which satisfies

$$
\bar { \nabla } _ { \mu } \epsilon _ { \nu } + \bar { \nabla } _ { \nu } \epsilon _ { \mu } + \psi _ { \mu \nu } ^ { ( 2 , 0 ) } = 0 .
$$

Note that this gauge transformation does not vanish at the boundary， so whether or not the $( 2 , 0 )$ solution should be regarded as gauge equivalent to the vacuum depends on the so-far-unspecified boundary conditions.

# 4Positivity of energy

# 4.1 BTZblack holes

The addition of the Chern-Simons term to the bulk action requires additional surface terms which in turn modify the definition of energy [5]. These surface terms are non-vanishing in general even for those solutions which satisfy the Einstein equation - namely BTZ black holes and massless gravitons. For Einstein metrics, the mass $M ( \mu )$ and angular momentum $J ( \mu )$ at general coupling $\mu$ are related to their values at $\mu = \infty$ by [27] [8],

$$
\ell M ( \mu ) = \ell M ( \infty ) + { \frac { J ( \infty ) } { \mu \ell } }
$$

$$
J ( \mu ) = J ( \infty ) + \frac { M ( \infty ) } { \mu }
$$

The bound $\ell M ( \infty ) \geq | J ( \infty ) |$ then implies positivity of energy for Einstein metrics when $\mu \ell > 1$ . When $\mu \ell < 1$ ， the energy of the black holes can be negative (There is some discussion in this region in [29][30],where signs of instability also appear). Note that for chiral gravity at $\mu \ell = 1$ we have

$$
\ell M ( { \frac { 1 } { \ell } } ) = J ( { \frac { 1 } { \ell } } ) .
$$

This can be interpreted as the statement that all Einstein geometries are right-moving.

Now let's compute the entropy of the black hole, assuming the existence of a unitary dual CFT, following [7] [8]. The inner and outer horizons are at

$$
r _ { \pm } = \sqrt { 2 G \ell ( \ell M ( \infty ) + J ( \infty ) ) } \pm \sqrt { 2 G \ell ( \ell M ( \infty ) - J ( \infty ) ) }
$$

and do not depend on $\mu$ . In terms of these the macroscopic formula for the entropy, including a contribution from the Chern-Simons term，is [24] [28] [29] [31].

$$
S _ { B H } ( \mu ) = \frac { \pi } { 2 G } ( r _ { + } + \frac { 1 } { \mu \ell } r _ { - } )
$$

The left and right temperatures of the black hole are determined by periodicities and also do not depend on $\mu$ . They are

$$
T _ { L } = \frac { r _ { + } - r _ { - } } { 2 \pi \ell ^ { 2 } } , T _ { R } = \frac { r _ { + } + r _ { - } } { 2 \pi \ell ^ { 2 } }
$$

In terms of these quantities, the microscopic Cardy formula for the entropy is

$$
S _ { B H } ( \mu ) = \frac { \pi ^ { 2 } c _ { L } ( \mu ) T _ { L } \ell } { 3 } + \frac { \pi ^ { 2 } c _ { R } ( \mu ) T _ { R } \ell } { 3 }
$$

Using formula (13) for the central charges one readily finds that this agrees with the macroscopic result (56).

# 4.2 Gravitons

For $\mu \ell > 1$ the weights $( h , h )$ of the massive gravitons are positive. The energy of the massive gravitons is proportional to these weights but with a possible minus sign. In particular if the overall sign of the action is changed, so is the energy, but the equations of motion and hence the weights are unaffected. In [4] [5] [32],it was shown that with the sign taken herein but no cosmological constant massive gravitons have negative energy. In this section we redo this analysis for the case of negative cosmological constant, by constructing the Hamiltonian [33].

The fluctuation $h _ { \mu \nu }$ can be decomposed as

$$
h _ { \mu \nu } = h _ { \mu \nu } ^ { M } + h _ { \mu \nu } ^ { L } + h _ { \mu \nu } ^ { R }
$$

where we use the subscript $M$ to represent the $\textstyle \left( { \frac { 3 + \mu \ell } { 2 } } , { \frac { - 1 + \mu \ell } { 2 } } \right)$ primary and their descendants, $L$ to represent the $( 2 , 0 )$ primary and their descendants, and $R$ to represent the $( 0 , 2 )$ primary and their descendants. We will call them massive modes, left-moving modes and right-moving modes hereafter.

Up to total derivatives, the quadratic action of $h _ { \mu \nu }$ is

$$
\begin{array} { r c l } { { S _ { 2 } } } & { { = } } & { { \displaystyle - \frac { 1 } { 3 2 \pi G } \int d ^ { 3 } x \sqrt { - g } h ^ { \mu \nu } ( { \mathcal G } _ { \mu \nu } ^ { ( 1 ) } + \frac { 1 } { \mu } C _ { \mu \nu } ^ { ( 1 ) } ) } } \\ { { } } & { { = } } & { { \displaystyle \frac { 1 } { 6 4 \pi G } \int d ^ { 3 } x \sqrt { - g } \{ - \bar { \nabla } ^ { \lambda } h ^ { \mu \nu } \bar { \nabla } _ { \lambda } h _ { \mu \nu } + \frac { 2 } { \ell ^ { 2 } } h ^ { \mu \nu } h _ { \mu \nu } - \frac { 1 } { \mu } \bar { \nabla } _ { \alpha } h ^ { \mu \nu } { \epsilon } _ { \mu } { } ^ { \alpha \beta } ( \bar { \nabla } ^ { 2 } + \frac { 2 } { \ell ^ { 2 } } ) h _ { \mu \nu } ^ { \nu } \} , } } \end{array}
$$

The momentum conjugate to $h _ { \mu \nu }$ is

$$
\Pi ^ { ( 1 ) \mu \nu } = - \frac { \sqrt { - g } } { 6 4 \pi G } \left( \bar { \nabla } ^ { 0 } ( 2 h ^ { \mu \nu } + \frac 1 \mu \epsilon ^ { \mu \alpha } { } _ { \beta } \bar { \nabla } _ { \alpha } h ^ { \beta \nu } ) - \frac 1 \mu \epsilon _ { \beta } { } ^ { 0 \mu } ( \bar { \nabla } ^ { 2 } + \frac { 2 } { \ell ^ { 2 } } ) h ^ { \beta \nu } \right)
$$

Using the equations of motion we find,

$$
\begin{array} { l c l } { { \Pi _ { M } ^ { ( 1 ) \mu \nu } } } & { { = } } & { { \displaystyle { \frac { \sqrt { - g } } { 6 4 \pi G } } ( - \bar { \nabla } ^ { 0 } h ^ { \mu \nu } + \frac { 1 } { \mu } ( \mu ^ { 2 } - \frac { 1 } { \ell ^ { 2 } } ) \epsilon _ { \beta } { } ^ { 0 \mu } h _ { M } ^ { \beta \nu } ) } } \\ { { \Pi _ { L } ^ { ( 1 ) \mu \nu } } } & { { = } } & { { \displaystyle { - \frac { \sqrt { - g } } { 6 4 \pi G } } ( 2 - \frac { 1 } { \mu \ell } ) \bar { \nabla } ^ { 0 } h _ { L } ^ { \mu \nu } } } \\ { { \Pi _ { R } ^ { ( 1 ) \mu \nu } } } & { { = } } & { { \displaystyle { - \frac { \sqrt { - g } } { 6 4 \pi G } } ( 2 + \frac { 1 } { \mu \ell } ) \bar { \nabla } ^ { 0 } h _ { R } ^ { \mu \nu } } } \end{array}
$$

Because we have up to three time derivatives in the Lagrangian, using the Ostrogradsky method we should also introduce $K _ { \mu \nu } \equiv \bar { \nabla } _ { 0 } h _ { \mu \nu }$ as a canonical variable, whose conjugate momentum is

$$
\Pi ^ { ( 2 ) \mu \nu } = \frac { - \sqrt { - g } g ^ { 0 0 } } { 6 4 \pi G \mu } \epsilon _ { \beta } ^ { \ \lambda \mu } \bar { \nabla } _ { \lambda } h ^ { \beta \nu }
$$

again using equations of motion we have

$$
\begin{array} { l c l } { { \Pi _ { M } ^ { ( 2 ) \mu \nu } } } & { { = } } & { { \displaystyle \frac { - \sqrt { - g } g ^ { 0 0 } } { 6 4 \pi G } h _ { M } ^ { \mu \nu } } } \\ { { \displaystyle \Pi _ { R } ^ { ( 2 ) \mu \nu } } } & { { = } } & { { \displaystyle \frac { - \sqrt { - g } g ^ { 0 0 } } { 6 4 \pi G \mu \ell } h _ { L } ^ { \mu \nu } } } \\ { { \displaystyle \Pi _ { L } ^ { ( 2 ) \mu \nu } } } & { { = } } & { { \displaystyle \frac { \sqrt { - g } g ^ { 0 0 } } { 6 4 \pi G \mu \ell } h _ { R } ^ { \mu \nu } } } \end{array}
$$

The Hamiltonian is then

$$
H = \int d ^ { 3 } x \big ( \dot { h } _ { \mu \nu } \Pi ^ { ( 1 ) \mu \nu } + \dot { K } _ { i \mu } \Pi ^ { ( 2 ) i \mu } - S \big )
$$

Specializing to linearized gravitons,and using their equations of motion， we then have the energies

$$
\begin{array} { l l l } { { E _ { M } } } & { { = } } & { { \displaystyle { \frac { 1 } { \mu } ( \mu ^ { 2 } - \frac { 1 } { \ell ^ { 2 } } ) \int d ^ { 3 } x \frac { \sqrt { - g } } { 6 4 \pi G } \epsilon _ { \beta } ^ { ~ 0 \mu } h _ { M } ^ { \beta \nu } \dot { h } _ { M \mu \nu } } } } \\ { { \ } } & { { } } & { { } } \\ { { E _ { L } } } & { { = } } & { { \displaystyle { ( - 1 + \frac { 1 } { \mu \ell } ) \int d ^ { 3 } x \frac { \sqrt { - g } } { 3 2 \pi G } \bar { \nabla } ^ { 0 } h _ { L } ^ { \mu \nu } \dot { h } _ { L \mu \nu } } } } \\ { { \ } } & { { } } & { { } } \\ { { E _ { R } } } & { { = } } & { { \displaystyle { ( - 1 - \frac { 1 } { \mu \ell } ) \int d ^ { 3 } x \frac { \sqrt { - g } } { 3 2 \pi G } \bar { \nabla } ^ { 0 } h _ { R } ^ { \mu \nu } \dot { h } _ { R \mu \nu } } } } \end{array}
$$

All the integrals above are negative, as can be shown by plugging in the solutions (39), (40) and (42) for primaries and by using the $S L ( 2 , \mathbb { R } )$ algebra for descendants. For the massive mode, the energy is negative when $\mu \ell > 1$ （204号 (it becomes infinitely negative at $\mu = \infty$ ）and positive when $\mu \ell < 1$ .The energy of left-moving modes is positive when $\mu \ell > 1$ ，and negative when $\mu \ell < 1$ . The energy of right-moving modes is always positive. $\mu \ell = 1$ isa critical point, where the energy of both massive modes and the left-moving modes becomes zero. Note $E _ { L }$ and $E _ { R }$ are consistent with (52).

Recall that positivity of central charges requires that $\mu \ell \geq 1$ ， so the only possibility for avoiding negative energy is to take the chiral gravity theory with $\mu \ell = 1$ . In that case, we see that massive and left-moving gravitons carry no energy, and might perhaps be regarded as pure gauge.

# 5 Conclusion and Discussion

In this note，we investigated the cosmological TMG，and found that the theory can be at most sensible at $\mu \ell = 1$ . At this special point, the theory is completely chiral. In order to show that the chiral theory is classically sensible asymptotic boundary conditions which consistently eliminate the infinite degeneracy of zero-energy excitations must be specified. One must also prove a non-linear positive energy theorem. Renormalizability must be addressed to define the quantum theory.

At the classical level the chiral structure might enable an exact solution of the theory. Some exact non-Einstein solutions of TMG with arbitrary $\mu$ have been found in [34]-[40]. Should there turn out to also be a consistent quantum theory it would be interesting to find the chiral CFT dual. Towards this end the approach of [9] may prove useful.

# Acknowledgements

We thank E. Witten and X. Yin for helpful discussions. The work is supported by DOE grant DE-FG02-91ER40654. WS is also supported by CSC. WS would like to thank the hospitality of the physics department of Harvard University.

# APPENDIX:Energy-momentum pseudotensor

In this appendix we show that the energy defined from the energy momentum pseudotensor for massive gravitons can be negative. For simplicity we specialize to $\Lambda = 0$ : for $\mu \ell \gg 1$ the Compton wavelength of the gravitons is much shorter than the $A d S _ { 3 }$ radius so the latter can be locally ignored.

Let us first review how the energy-momentum pseudo tensor at quadratic order is defined without the Chern-Simons term or cosmological constant term. The full Einstein equation in the presence of matter is

$$
G _ { \mu \nu } = 1 6 \pi G T _ { \mu \nu } ^ { M }
$$

Expanding the metric $g _ { \mu \nu } = \eta _ { \mu \nu } + h _ { \mu \nu }$ , we have through quadratic order

$$
G _ { \mu \nu } ^ { ( 1 ) } = - G _ { \mu \nu } ^ { ( 2 ) } + 1 6 \pi G T _ { \mu \nu } ^ { M }
$$

where $G _ { \mu \nu } ^ { ( 1 ) }$ and $G _ { \mu \nu } ^ { ( 2 ) }$ are terms linear and quadratic in $h _ { \mu \nu }$ .The energy momentum pseudo tensor defined as

$$
t _ { \mu \nu } = - \frac { 1 } { 1 6 \pi G } G _ { \mu \nu } ^ { ( 2 ) } , \quad \mathrm { w i t h } \quad \partial ^ { \mu } t _ { \mu \nu } = 0 ,
$$

sources the Newtonian part of the gravitational potential in the same way that the matter stress tensor does. When adding the Chern-Simons term, the energy momentum pseudo tensor is similarly defined as

$$
t _ { \mu \nu } = - \frac { 1 } { 1 6 \pi G } ( G _ { \mu \nu } ^ { ( 2 ) } + \frac { 1 } { \mu } C _ { \mu \nu } ^ { ( 2 ) } ) .
$$

In flat background, the linearized equation of motion (23) becomes

$$
\partial ^ { 2 } h _ { \mu \nu } + \frac { 1 } { \mu } \epsilon _ { \mu } ^ { ~ \alpha \beta } \partial _ { \alpha } \partial ^ { 2 } h _ { \beta \nu } = 0
$$

under the harmonic plus traceless gauge. For a plane wave solution in the form of hμv(k) = 5 $\begin{array} { r } { h _ { \mu \nu } ( k ) = \frac { 1 } { \sqrt { 2 k _ { 0 } } } e ^ { - i k \cdot x } e _ { \mu \nu } ( k ) } \end{array}$ , the gauge conditions and the equations of motion are

$$
\begin{array} { l } { { k ^ { \mu } e _ { \mu \nu } ( k ) } } \\ { { { } } } \end{array} = 0 , e ^ { \mu } { } _ { \mu } ( k ) = 0
$$

The $k ^ { 2 } = 0$ solution is pure gauge. So $\begin{array} { r } { e _ { \mu \nu } ( k ) - \frac { i k _ { \alpha } } { \mu } \epsilon _ { \mu } ^ { \alpha \beta } e _ { \beta \nu } ( k ) = 0 } \end{array}$ ，which implies $( k ^ { 2 } + \mu ^ { 2 } ) e _ { \mu \nu } ( k ) = 0$ . When $k _ { \mu } = ( \mu , 0 , 0 )$ , the positive energy solution is

$$
h _ { \mu \nu } = \frac { e ^ { - i \mu \tau } } { \sqrt { 2 \mu } } \left( \begin{array} { c c c } { { 0 } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { 1 } } & { { i } } \\ { { 0 } } & { { i } } & { { - 1 } } \end{array} \right)
$$

It is convenient to define $e _ { \mu } ( \vec { 0 } ) = ( 0 , 1 , i )$ ，such that

$$
\begin{array} { r c l } { { } } & { { e _ { \mu \nu } ( \vec { 0 } ) } } & { { = } } & { { e _ { \mu } ( \vec { 0 } ) e _ { \nu } ( \vec { 0 } ) , } } \\ { { \mathrm { a n d } } } & { { e _ { \mu \nu } ( \vec { k } ) } } & { { = } } & { { e _ { \mu } ( \vec { k } ) e _ { \nu } ( \vec { k } ) , } } \end{array}
$$

where $e _ { \mu } ( \vec { k } )$ is obtained from $e _ { \mu } ( \vec { 0 } )$ by a boost. The metric fluctuation can be expanded in Fourier modes,

$$
h _ { \mu \nu } = \int d \vec { k } ^ { 2 } \frac { 1 } { \sqrt { 2 k _ { 0 } } } \{ \alpha ( \vec { k } ) e _ { \mu \nu } ( \vec { k } ) e ^ { - i k \cdot x } + \alpha ^ { \dagger } ( \vec { k } ) e _ { \mu \nu } ^ { * } ( \vec { k } ) e ^ { i k \cdot x } \}
$$

To calculate the energy momentum pseudo tensor, we will need the following,

$$
\begin{array} { r c l } { { t _ { \mu \nu } } } & { { = } } & { { - \displaystyle \frac { 1 } { 1 6 \pi G ^ { ( 2 ) } } ( E _ { \mu \nu } ^ { ( 2 ) } + \frac { 1 } { p } C _ { \nu \alpha } ^ { ( 2 ) } ) } } \\ { { \displaystyle \mathcal { G } _ { \mu \nu } ^ { ( 2 ) } } } & { { = } } & { { R _ { \mu \nu } ^ { ( 2 ) } - \frac { 1 } { 2 } \eta _ { \mu \nu } R ^ { ( 2 ) } } } \\ { { \displaystyle \mathit { F } _ { \mu \nu } ^ { ( 2 ) } } } & { { = } } & { { \displaystyle \frac { 1 } { 2 } b ^ { \nu \nu } \partial _ { \nu } \partial _ { \nu } \partial _ { \nu } - b ^ { \nu \alpha } \partial _ { \nu } \partial _ { \nu } \partial _ { \nu } b _ { \nu \alpha } + \frac { 1 } { 4 } ( \partial _ { \nu } b _ { \nu \alpha } ) \partial _ { \nu } b ^ { \nu \alpha } } } \\ { { } } & { { } } & { { } } \\ { { } } & { { + } } & { { ( \partial ^ { \nu } b ^ { \nu } \partial _ { \nu } ) \partial _ { \nu } \partial _ { \nu } b _ { \nu \alpha } + \frac { 1 } { 2 } \partial _ { \nu } ( b ^ { \nu \alpha } \partial _ { \nu } b _ { \nu \alpha } ) } } \\ { { \displaystyle C _ { \mu \nu } ^ { ( 2 ) } } } & { { = } } & { { \epsilon _ { \mu } \epsilon ^ { \alpha } \partial _ { \alpha } ( R _ { \mu \nu } ^ { ( 2 ) } - \frac { 1 } { 4 } \eta _ { \beta \nu } R ^ { ( 2 ) } ) + \bar { h } _ { \mu \nu } k ^ { \alpha \lambda \delta } \partial _ { \nu } H _ { \beta \nu } ^ { ( 1 ) } - \epsilon _ { \alpha } \partial _ { \nu } ^ { \alpha } \hat { \hat { Z } } _ { \alpha \nu } ^ { ( 1 ) } \hat { \hat { Z } } _ { \alpha \nu } ^ { ( 1 ) } } } \\ { { \displaystyle \Gamma _ { \mu \nu } ^ { ( 3 ) } } } & { { = } } & { { \displaystyle \frac { 1 } { 2 } \gamma ^ { \lambda \nu } ( j _ { \lambda \nu } \partial _ { \nu } + \partial _ { \nu } h _ { \alpha \alpha } - \partial _ { \nu } h _ { \alpha \alpha } ) } } \\ { { } } & { { } } & { { } } \\ { { R _ { \mu \nu } ^ { ( 2 ) } } } & { { = } } & { { \displaystyle - \frac { 1 } { 2 } \hat { \rho } h _ { \mu \nu } } } \end{array}
$$

Using the equation of motion (32),it simplifies to

$$
\begin{array} { r c l } { { G _ { \mu \nu } ^ { ( 2 ) } } } & { { = } } & { { \displaystyle - \frac { 1 } { 4 } ( \partial _ { \mu } h _ { \rho \sigma } ) \partial _ { \nu } h ^ { \rho \sigma } - \frac { \mu ^ { 2 } } { 2 } h ^ { \rho } { } _ { \mu } h _ { \rho \nu } - \frac { \mu ^ { 2 } } { 8 } \eta _ { \mu \nu } h ^ { \rho \sigma } h _ { \rho \sigma } , } } \\ { { { \cal C } _ { \mu \nu } ^ { ( 2 ) } } } & { { = } } & { { \displaystyle \frac { \mu ^ { 2 } } { 4 } ( 3 \mu h _ { \rho \mu } h ^ { \rho } { } _ { \nu } + \epsilon _ { \mu } { } ^ { \alpha \beta } h ^ { \lambda } { } _ { \alpha , \nu } h _ { \beta \lambda } ) } } \end{array}
$$

up to total derivatives. So the energy is

$$
\begin{array} { r c l } { { E } } & { { = } } & { { \displaystyle \int d ^ { 2 } \vec { x } t _ { 0 0 } } } \\ { { } } & { { = } } & { { \displaystyle \int d ^ { 2 } \vec { k } \frac { n ( k ) } { 1 6 \pi G k _ { 0 } } \{ ( k _ { 0 } ^ { 2 } - \frac { \mu ^ { 2 } } { 2 } - k _ { 0 } \mu ) - \frac { 1 } { 2 } \mu ^ { 2 } e _ { 0 } ( \vec { k } ) ^ { * } e _ { 0 } ( \vec { k } ) \} . } } \end{array}
$$

For vanishing spatial momentum $n ( \vec { k } ) \propto \delta ^ { 2 } ( \vec { k } )$ , the energy is just $- \mu$ times a positive normalization factor.

# References

[1] M.Banados,C. Teitelboim and J. Zaneli,“The Black hole in threedimensional space-time,” Phys. Rev. Lett. 69,1849 (1992) [arXiv:hepth/9204099].   
[2] E. Witten, “(2+1)-Dimensional Gravity as an Exactly Soluble System," Nucl. Phys. B 311, 46 (1988).   
[3] J. Fjelstad and S. Hwang，“Sectors of solutions in three-dimensional gravity and black holes,” Nucl. Phys. B 628，331 (2002） [arXiv:hepth/0110235].   
[4] S.Deser，R. Jackiw and S. Templeton，Annals Phys. 140, 372 (1982) [Erratum-ibid. 185, 406.1988 APNYA,281,409 (1988 APNYA,281,409- 449.2000)]   
[5] S.Deser， R. Jackiw and S. Templeton，“Three-Dimensional Massive Gauge Theories,” Phys. Rev. Lett. 48, 975 (1982).   
[6] A. Strominger， “Black hole entropy from near-horizon microstates," JHEP 9802,009 (1998) [arXiv:hep-th/9712251].   
[7] P.Kraus and F.Larsen，“Microscopic black hole entropy in theories with higher derivatives,” JHEP 0509, 034(2005) [arXiv:hep-th/0506176].   
[8] P. Kraus and F. Larsen，“Holographic gravitational anomalies,” JHEP 0601,022 (2006)[arXiv:hep-th/0508218].   
[9] E.Witten， “Three-Dimensional Gravity Revisited,” arXiv:0706.3359 [hep-th].   
[10] J. Manschot，“ $A d S _ { 3 }$ Partition Functions Reconstructed,” JHEP 0710, 103（2007) [arXiv:0707.1159 [hep-th]].   
[11] D.Gaiotto and X. Yin，“Genus Two Partition Functions of Extremal Conformal Field Theories,” JHEP 0708， 029 （2007） [arXiv:0707.3437 [hep-th].   
[12] M. R. Gaberdiel, “Constraints on extremal self-dual CFTs,” JHEP 0711,087 (2007) [arXiv:0707.4073 [hep-th].   
[13] S. D.Avramis,A. Kehagias and C. Mattheopoulou, “Three-dimensional AdS gravity and extremal CFTs at c=8m,” JHEP 0711， 022 (2007) [arXiv:0708.3386 [hep-th].   
[14] X. Yin， “Partition Functions of Three-Dimensional Pure Gravity,” arXiv:0710.2129 [hep-th].   
[15] X. Yin，“OnNon-handlebodyInstantonsin3D Gravity,” arXiv:0711.2803 [hep-th].   
[16] A. Maloney and E. Witten,“Quantum Gravity Partition Functions in Three Dimensions,” arXiv:0712.0155 [hep-th].   
[17] S. Deser and B. Tekin，“Massive, topologically massive, models,” Class. Quant. Grav. 19,L97 (2002) [arXiv:hep-th/0203273].   
[18] J. Maldacena and A. Strominger “Ads3 Black Holes and a Stringy Exclusion Principle” JHEP 9812, 005 (1998) [arxiv:hep-th/9804085].   
[19] J.D. Brown and M. Henneaux, “Central charges in the canonical realization of asymptotic symmetries: an example from three-dimensional gravity,” Commun. Math. Phys.104, 207(1986).   
[20] M. Henningson and K. Skenderis, “The holographic Weyl anomaly," JHEP 9807, 023 (1998) [arXiv:hep-th/9806087].   
[21] S. de Haro, S. N. Solodukhin and K. Skenderis, “Holographic reconstruction of spacetime and renormalization in the AdS/CFT correspondence," Commun.Math. Phys. 217, 595 (2001) [arXiv:hep-th/0002230].   
[22] V. Balasubramanian and P. Kraus,“A stress tensor for anti-de Sitter gravity,” Commun. Math. Phys. 208, 413 (1999) [arXiv:hep-th/9902121].   
[23] P. Kraus,“Lectures on black holes and the AdS(3)/CFT(2) correspondence,” arXiv:hep-th/0609074.   
[24] S. N. Solodukhin, “Holography with gravitational Chern-Simons,” Phys. Rev. D 74, 024015 (2006) [arXiv:hep-th/0509148].   
[25] S. Deser and B. Tekin，“Energy in topologically massive gravity,” Class. Quant. Grav. 20 (2003) L259 [arXiv:gr-qc/0307073].   
[26] S. Olmez, O. Sarioglu and B. Tekin, “Mass and angular momentum of asymptotically AdS or flat solutions in the topologically massive gravity," Class. Quant. Grav. 22 (2005) 4355 [arXiv:gr-qc/0507003].   
[27] K. A. Moussa, G. Clement and C. Leygnac,“The black holes of topologically massive gravity,” Class. Quant. Grav. 20, L277 (2003) [arXiv:grqc/0303042].   
[28] B. Sahoo and A. Sen，“BTZ black hole with Chern-Simons and higher derivative terms,” JHEP 0607, 008 (2006) [arXiv:hep-th/0601228].   
[29] M. I. Park, “BTZ black hole with gravitational Chern-Simons: Thermodynamics and statistical entropy,” Phys. Rev. D 77, 026011 (2008) arXiv:hep-th/0608165.   
[30]_M.I. Park，Phys.Lett.B 647,472 (2007) [arXiv:hep-th/0602114]; [arXiv:hep-th/0610140]; [arXiv:hep-th/0609027]; [arXiv:hepth/0611048].   
[31] Y. Tachikawa,“Black hole entropy in the presence of Chern-Simons terms,” Class. Quant. Grav. 24, 737 (2007) [arXiv:hep-th/0611141].   
[32] S. Deser and J. H. Kay, “Topologically Massive Supergravity,” Phys. Lett. B 120,97 (1983).   
[33] I.L. Buchbinder, S.L. Lyahovich and V.A.Krychtin, “Canonical Quantization Of Topologically Massive Gravity,” Class. Quant. Grav. 10, 2083 (1993).   
[34] R. Percacci， P. Sodano and I. Vuorio, “Topologically massive planer universes with constant twist,” Annals Phys. 176, 344 (1987).   
[35] G. S. Hall, T. Morgan and Z. Perjes,“Three-dimensional space-times,"   
[36] Y. Nutku, “Exact solutions of topologically massive gravity with a cosmological constant,” Class. Quant. Grav. 10, 2657 (1993).   
[37] A. N. Aliev and Y. Nutku, “A theorem on topologically massive gravity," Class. Quant. Grav. 13, L29 (1996) [arXiv:gr-qc/9812089].   
[38] A. N. Aliev and Y. Nutku, “Spinor formulation of topologically massive gravity," arXiv:gr-qc/9812090.   
[39] T. Dereli and O. Sarioglu， “Topologically massive gravity and black holes in three dimensions,” arXiv:gr-qc/0o09082.   
[40] A. Bouchareb and G. Clement, “Black hole mass and angular momentum in topologically massive gravity,” Class. Quant. Grav. 24， 5581 (2007) [arXiv:0706.0263 [gr-qc]].