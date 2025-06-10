# Some No-go Theorems for String Duals of Non-relativistic Lifshitz-like Theories

Wei Li $a 1$ , Tatsuma Nishioka $\boldsymbol { b } , \boldsymbol { a }$ ² and Tadashi Takayanagi $^ { a 3 }$

（204号 $a$ Institute for the Physics and Mathematics of the Universe (IPMU), University of Tokyo， Kashiwa, Chiba 277-8582， Japan （20 $b$ Department of Physics, Kyoto University, Kyoto 606-8502, Japan

# Abstract

We study possibilities of string theory embeddings of the gravity duals for non-relativistic Lifshitz-like theories with anisotropic scale invariance. We search classical solutions in type IIA and eleven-dimensional supergravities which are expected to be dual to (2+1)- dimensional Lifshitz-like theories. Under reasonable ansätze,we prove that such gravity duals in the supergravities are not possible. We also discuss a possible physical reason behind this.

# 1Introduction

Recently, two interesting extensions of the AdS/CFT correspondence [1] to non-relativistic systems were proposed in the papers [2] and [3]. The former has the non-relativistic conformal symmetry including the special conformal transformation， while the latter, calld quantum Lifshitz-like points, only has the non-relativistic scale invariance.4

To understand their microscopic holographic dual theories,we need to find their concrete string theory realizations. Another reason for this is that string embeddings are expected to give a consistency condition for solutions of an effective gravity theory which lives in the lower dimensions via compactifications [24]. The original gravity duals for the non-relativistic systems have been proposed in effective gravity-matter theories living in $d < 1 0$ (or $d < 1 1$ ) dimension [2, 3], which are not a priori guaranteed to be derived from ten (or eleven) dimensional supergravity. The effective $d$ -dimensional spacetime dual to a $( d - 1 )$ -dimensional Lifshitz-like theory will be called $L i _ { d }$ in this paper. Later,it has been found that the gravity duals of the former (i.e. non-relativistic conformal） theories can be realized as solutions in ten or eleven dimensional supergravities as was first done in [25]. However,the presence of a null circle in the gravity dual [2] of non-relativistic conformal systems makes the connection to interesting condensed matter systems (such as cold atoms) ambiguous.

The main purpose of this paper is to point out that it is surprisingly diffcult to embed the gravity duals of quantum Lifshitz-like points [3] into ten or eleven dimensional supergravities as opposed to our naive expectation. Actually, the only known supergravity solution with the Lifshitz-like property is the one in the paper [14]. It is based on the D3-D7 system frst introduced in [26] and can be embedded into type IIB string theory. However, in this solution we can introduce the anisotropy of the scale transformation only through one of the three spatial directions therefore it corresponds not to a non-relativistic quantum Lifshitz point but to a classcal Lifshitz point.5 Also since it has a non-constant dilaton,the anisotropic scale invariance only holds at the leading order of interactions, though thermodynamical quantities such as the entropy still respect the scale invariance.

In this paper, we will present no-go arguments under certain ansätze of fluxes,which we expect will not cause the loss of generality significantly. Such ansatze are necessary to determine clearly if physical solutions are possible or not in our analysis. It may be possible that we can extend our no-go arguments if we develop excellent technical devises in near future. Under the ansätze we will prove that no solutions of the form $L i _ { 4 } \times M _ { 7 }$ ,where $M _ { 7 }$ is an arbitrary compact manifold,are allowed in the eleven-dimensional supergravity even if we take the possbility of warp factor into account. We will also present a similar no-go argument in the massive type IIA supergravity. Interestingly enough, we often encounter unphysical supergravity solutions, whose fuxes become imaginary-valued. We will also ofer a heuristic physical reason why quantum Lifshitz-like theories are difficult to realize in string theory via a holography argument in the final section,which relates the dual theory to certain non-commutative theories.

Though in this paper we always consider the $( 2 + 1 )$ -dimensional Lifshitz-like fixed points to perform concrete calculations,we believe that the main conclusions can be applied to other dimensions. As opposed to the proofs of no-go theorems for de-Sitter spaces [28] and fux backgrounds [29] in supergravity, we need more detailed arguments due to the lack of the Lorentz symmetry.

This paper is organized as follows: In section 2, we will review the gravity dual of quantum Lifshitz-like points following the paper [3]. In section 3,we will prove a no-go theorem for the spacetime $L i _ { 4 } \times M _ { 7 }$ in M-theory assuming a certain ansatz of fluxes. In section 4,we will present a no-go argument for the spacetime $L i _ { 4 } \times M _ { 6 }$ in massive IIA supergravity under an even form ansatz of fuxes. We will also show the no-go theorem for deformations of standard flux compactifications when $M _ { 6 }$ is an arbitrary nearly Kähler manifold. Moreover，we also consider the possibility of adding an orientifold 6-plane (O6-plane) and show that the result will not be changed. In section 5, we will summarize our conclusion and discuss our results.

# 2 Review of Gravity Duals of Lifshitz-like Fixed Points

Let us first review the gravity dual $L i _ { 4 }$ of Lifshitz-like fixed points in $2 + 1$ dimension, which was first presented in [3]. We start with the four-dimensional gravity coupled to a one-form gauge field $A _ { 1 }$ and a two-form field $B _ { 2 }$ . The action is

$$
S = \int d ^ { 4 } x \sqrt { - g } ( R - 2 \Lambda ) - \frac { 1 } { 2 } \int \left( F _ { 2 } \wedge { * } F _ { 2 } + H _ { 3 } \wedge { * } H _ { 3 } \right) - c \int B _ { 2 } \wedge F _ { 2 } .
$$

The gravity dual $L i _ { 4 }$ of a Lifshitz-like point is defined by the following metric

$$
\begin{array} { r c l } { { d s ^ { 2 } } } & { { = } } & { { L ^ { 2 } \left( - r ^ { 2 z } d t ^ { 2 } + r ^ { 2 } ( d x ^ { 2 } + d y ^ { 2 } ) + \frac { d r ^ { 2 } } { r ^ { 2 } } \right) } } \\ { { } } & { { \equiv } } & { { - ( \theta ^ { t } ) ^ { 2 } + ( \theta ^ { x } ) ^ { 2 } + ( \theta ^ { y } ) ^ { 2 } + ( \theta ^ { r } ) ^ { 2 } , } } \end{array}
$$

where we defined the orthonormal basis of one-forms

$$
\theta ^ { t } = L r ^ { z } d t , \theta ^ { x } = L r d x , \theta ^ { y } = L r d y , \theta ^ { r } = L \frac { d r } { r } .
$$

The Ricci tensor $R _ { \mu \nu }$ and the Ricci scalar $R _ { 4 }$ is given by

$$
\begin{array} { l } { { R _ { t t } = z ( z + 2 ) r ^ { 2 z } , \quad R _ { x x } = R _ { y y } = - ( 2 + z ) r ^ { 2 } , \quad R _ { r r } = - \displaystyle \frac { 2 + z ^ { 2 } } { r ^ { 2 } } . } } \\ { { R _ { 4 } = - \displaystyle \frac { 2 } { L ^ { 2 } } ( 3 + 2 z + z ^ { 2 } ) . } } \end{array}
$$

In order to break the $( 2 + 1 )$ -dimensional Lorentz symmetry, we introduce the background fluxes

$$
F _ { 2 } = \alpha \theta ^ { t } \wedge \theta ^ { r } , \quad H _ { 3 } = \beta \theta ^ { x } \wedge \theta ^ { y } \wedge \theta ^ { r } .
$$

Here the fact that the fluxes are written by the orthonormal one-forms (2.4) guarantees the non-relativistic scale invariance and is consistent with the Einstein equations discussed below. In this system the equations of motion for fluxes are given by

$$
d * F _ { 2 } = - c H _ { 3 } , \quad d * H _ { 3 } = c F _ { 2 } .
$$

This leads to the constraints

$$
{ \frac { \alpha } { \beta } } = { \sqrt { \frac { z } { 2 } } } , \qquad c ^ { 2 } = { \frac { 2 z } { L ^ { 2 } } } .
$$

The Einstein equation becomes

$$
R _ { \mu \nu } + g _ { \mu \nu } \left( - \frac { R } { 2 } + \frac { 1 } { 2 4 } H _ { \rho \sigma \lambda } H ^ { \rho \sigma \lambda } + \frac { 1 } { 8 } F _ { \rho \sigma } F ^ { \rho \sigma } + \Lambda \right) = \frac { 1 } { 2 } F _ { \mu \alpha } F _ { \nu } ^ { \ \alpha } + \frac { 1 } { 4 } H _ { \mu \alpha \beta } H _ { \nu } ^ { \ \alpha \beta } .
$$

By substituting the Ricci tensor (2.5) and the flux ansatz (2.7) into (2.10), we obtain in the end

$$
\alpha = \frac { \sqrt { 2 z ( z - 1 ) } } { L } , \beta = \frac { 2 } { L } \sqrt { z - 1 } , \Lambda = - \frac { z ^ { 2 } + z + 4 } { 2 L ^ { 2 } } .
$$

Notice that in this solution the coefficient $c$ of Chern-Simons term is uniquely determined by the cosmological constant $\Lambda$ . In the later arguments of its string theory embedding,what turns out to be crucial is whether this constraint is consistent with string theory compactifcations or not.

It is also useful to take a duality transformation. We add a term $\int d \phi \wedge H _ { 3 }$ assuming that $H _ { 3 }$ is now a general three-form. The equation of motion for $\phi$ leads to the Bianchi identity $d H _ { 3 } = 0$ . If we integrate out $H _ { 3 }$ ,we find the action looks like

$$
S = \int d ^ { 4 } x \sqrt { - g } ( R - 2 \Lambda ) - \frac { 1 } { 2 } \int \left( F _ { 2 } \wedge * F _ { 2 } + ( d \phi - c A _ { 1 } ) \wedge * ( d \phi - c A _ { 1 } ) \right) .
$$

By absorbing $\phi$ via the gauge transformation, this theory is equivalent to a massive vector field theory coupled to gravity, as already noted in [5].

# 3 No-Go Theorem for $L i _ { 4 } \times M _ { 7 }$ in M-theory

# 3.1 Direct Product Metric $L i _ { 4 } \times M _ { 7 }$

The action of the eleven-dimensional supergravity is given by6

$$
S = \frac { 1 } { 2 \kappa _ { 1 1 } ^ { 2 } } \left[ \int d ^ { 1 1 } x \sqrt { - g } \left( R - \frac { 1 } { 2 \cdot 4 ! } F _ { \mu \nu \rho \sigma } F ^ { \mu \nu \rho \sigma } \right) - \frac { 1 } { 6 } \int C _ { 3 } \wedge F _ { 4 } \wedge F _ { 4 } \right] .
$$

The Bianchi identity and equations of motion of the four-form flux read

$$
d F _ { 4 } = 0 , d * F _ { 4 } + \frac { 1 } { 2 } F _ { 4 } \wedge F _ { 4 } = 0 ,
$$

where $F _ { 4 } = d C _ { 3 }$

We assume that the spacetime metric takes the form of the direct product $L i _ { 4 } \times M _ { 7 }$ without any warp factor，where $M _ { 7 }$ is taken to be an arbitrary seven-dimensional compact manifold. The coordinates of $M _ { 7 }$ are denoted by $\boldsymbol { x } ^ { i } = ( x ^ { 1 } , x ^ { 2 } , \cdot \cdot \cdot , x ^ { 7 } )$ . We denote the volume-form of $M _ { 7 }$ （204号 by $V _ { 7 }$ . Now we take the the four-form flux with the symmetry of $L i _ { 4 }$ to be in the following form

$$
F _ { 4 } = f \ \theta ^ { t } \theta ^ { x } \theta ^ { y } \theta ^ { r } + \theta ^ { x } \theta ^ { y } \theta ^ { r } \wedge \alpha + \theta ^ { t } \theta ^ { r } \wedge \beta + \theta ^ { r } \wedge \Omega + \eta .
$$

This form of flux is the most general form in which we can tell precisely if the corresponding supergravity solution exists or not，using the arguments presented below. Its Hodge dual is given by7

$$
* F _ { 4 } = - f V _ { 7 } + \theta ^ { t } \wedge * \alpha - \theta ^ { x } \theta ^ { y } \wedge * \beta + \theta ^ { t } \theta ^ { x } \theta ^ { y } \wedge * \Omega + \theta ^ { t } \theta ^ { x } \theta ^ { y } \theta ^ { r } \wedge * \eta .
$$

The Einstein equation requires that the $r$ -dependence in $F _ { 4 }$ only appears through $\theta ^ { \mu }$ as in the previous section. Thus, $f$ ， $\alpha$ ， $\beta$ ， $\Omega$ and $\eta$ are 0,1,2,3 and 4-form in $M _ { 7 }$ and they do not depend on $r$ ：

The Bianchi identity requires

$$
d \alpha = d \beta = d \Omega = d f = d \eta = 0 .
$$

The flux equations of motion lead to

$$
\begin{array} { l } { \displaystyle d \ast \alpha = d \ast \beta = d \ast \Omega = 0 , } \\ { \displaystyle \beta \wedge \eta = \frac { z } { L } \ast \alpha , } \\ { \alpha \wedge \eta = \frac { 2 } { L } \ast \beta , } \\ { \displaystyle d \ast \eta - \frac { z + 2 } { L } \ast \Omega + \eta f = 0 , } \\ { \Omega \wedge \eta = 0 . } \end{array}
$$

In particular, from(3.19)and(3.2O),we find

$$
z \alpha ^ { 2 } = { \beta } ^ { 2 } ,
$$

where we have defined $\alpha ^ { 2 } = \alpha _ { i } \alpha ^ { i }$ and $\beta ^ { 2 } = \beta _ { i j k } \beta ^ { i j k }$ with $i = 1 , 2 , \cdots , 7$ ：

The Einstein equation can be rewritten into the following form

$$
R _ { \mu \nu } = - \frac { 1 } { 6 \cdot 4 ! } F ^ { 2 } g _ { \mu \nu } + \frac { 1 } { 1 2 } F _ { \mu \rho \sigma \tau } F _ { \nu } ^ { ~ \rho \sigma \tau } .
$$

Therefore,the Einstein equation (3.24) for the $\mathbf { \Psi } ( t t )$ ， $( x x )$ and $( r r )$ components reads

$$
\begin{array} { l } { \displaystyle - \frac { z ( z + 2 ) } { L ^ { 2 } } = - \frac { 1 } { 6 } ( - f ^ { 2 } + \alpha ^ { 2 } - \frac { 1 } { 2 } \beta ^ { 2 } + \frac { 1 } { 3 ! } \Omega ^ { 2 } + \frac { 1 } { 4 ! } \eta ^ { 2 } ) + \frac { 1 } { 2 } ( - f ^ { 2 } - \frac { 1 } { 2 } \beta ^ { 2 } ) , } \\ { \displaystyle - \frac { 2 + z } { L ^ { 2 } } = - \frac { 1 } { 6 } ( - f ^ { 2 } + \alpha ^ { 2 } - \frac { 1 } { 2 } \beta ^ { 2 } + \frac { 1 } { 3 ! } \Omega ^ { 2 } + \frac { 1 } { 4 ! } \eta ^ { 2 } ) + \frac { 1 } { 2 } ( - f ^ { 2 } + \alpha ^ { 2 } ) , } \\ { \displaystyle - \frac { 2 + z ^ { 2 } } { L ^ { 2 } } = - \frac { 1 } { 6 } ( - f ^ { 2 } + \alpha ^ { 2 } - \frac { 1 } { 2 } \beta ^ { 2 } + \frac { 1 } { 3 ! } \Omega ^ { 2 } + \frac { 1 } { 4 ! } \eta ^ { 2 } ) + \frac { 1 } { 2 } ( - f ^ { 2 } + \alpha ^ { 2 } - \frac { 1 } { 2 } \beta ^ { 2 } + \frac { 1 } { 6 } \Omega ^ { 2 } ) . } \end{array}
$$

By taking differences among them，we can easily find

$$
{ \frac { 2 ( z - 1 ) } { L ^ { 2 } } } = { \frac { 1 } { 2 } } \alpha ^ { 2 } + { \frac { 1 } { 1 2 } } \Omega ^ { 2 } , \quad { \frac { z ( z - 1 ) } { L ^ { 2 } } } = { \frac { \beta ^ { 2 } } { 4 } } - { \frac { 1 } { 1 2 } } \Omega ^ { 2 } .
$$

By combining these two equations with the relation (3.23)，we find if $\Omega ^ { 2 } \neq 0$ ， then $z = - 2$ In this case, we only have unphysical solutions that has $\textstyle { \frac { \beta ^ { 2 } } { \alpha ^ { 2 } } } = - 2 < 0$ .Therefore, we need to require $\Omega ^ { 2 } = 0$ (or equivalently $\Omega _ { i j k } = 0$ ）below.

Now let us look at the off-diagonal components of the Einstein equation. In particular, if we consider $( t i )$ component it behaves like $R _ { t i } \propto f \alpha _ { i }$ and this contradicts our metric ansatz unless it is vanishing. If we assume $f \neq 0$ , then we need to set $\alpha _ { i } = 0$ and $z = 1$ . Thus we recover the full Lorentz symmetry, which we do not want.

Thus, we need to set $f = 0$ . In this case, all equations of motion can be reduced to

$$
\begin{array} { l } { \displaystyle \frac { 2 z ^ { 2 } + 1 2 z + 4 } { L ^ { 2 } } = \frac { \eta ^ { 2 } } { 4 ! } , } \\ { R _ { i j } = - \frac { 3 z } { L ^ { 2 } } g _ { i j } + \frac { 1 } { 2 } \big ( \alpha _ { i } \alpha _ { j } - \beta _ { i k } \beta _ { j } ^ { k } + \frac { 1 } { 6 } \eta _ { k k l m } \eta _ { j } ^ { k l m } \big ) , } \\ { \displaystyle d \alpha = d \beta = d \eta = 0 , \quad \quad f = \Omega = 0 , \quad d \ast \alpha = d \ast \beta = d \ast \eta = 0 , } \\ { \beta \wedge \eta = \frac { z } { L } \ast \alpha , \quad \alpha \wedge \eta = \frac { 2 } { L } \ast \beta , } \\ { \displaystyle \alpha ^ { 2 } = \frac { \beta ^ { 2 } } { z } = \frac { 4 \big ( z - 1 \big ) } { L ^ { 2 } } . } \end{array}
$$

We can also find that the value of the Ricci scalar of M7 as Rm = (2z+3)(z+2)

By using(3.29) we can find the relation

$$
\alpha \wedge * \alpha = \frac { L ^ { 2 } } { 2 z } \ * ( \alpha \wedge \eta ) \wedge ( \alpha \wedge \eta ) .
$$

This equation (3.31） can be rewritten in the component expression as

$$
\begin{array} { r c l } { { \alpha ^ { 2 } } } & { { = } } & { { \displaystyle \frac { 2 5 L ^ { 2 } } { 2 z \cdot 5 ! } \alpha _ { [ \mu _ { 1 } } \eta _ { \mu _ { 2 } \mu _ { 3 } \mu _ { 4 } \mu _ { 5 } ] } \alpha ^ { [ \mu _ { 1 } } \eta ^ { \mu _ { 2 } \mu _ { 3 } \mu _ { 4 } \mu _ { 5 } ] } } } \\ { { } } & { { = } } & { { \displaystyle \frac { L ^ { 2 } } { 2 z \cdot 4 ! } \left( \alpha ^ { 2 } \eta ^ { 2 } - 4 \alpha ^ { i } \alpha _ { j } \eta _ { i k l m } \eta ^ { j k l m } \right) . } } \end{array}
$$

By plugging into (3.30) we obtain

$$
\frac { 1 } { 4 ! } { \alpha } ^ { i } \alpha _ { j } \eta _ { i k l m } \eta ^ { j k l m } = \frac { 2 ( z - 1 ) ( z ^ { 2 } + 5 z + 2 ) } { L ^ { 4 } } > 0 .
$$

On the other hand, we can show $\alpha ^ { i } \beta _ { i j } = 0$ as we can easily see $\alpha \wedge * \beta = 0$ from (3.29). By combining these results,we can finally evaluate

$$
R _ { i j } \alpha ^ { i } \alpha ^ { j } = \frac { 4 z ( z - 1 ) ( z + 4 ) } { L ^ { 4 } } > 0 ,
$$

which actually proves that there is no such harmonic one-form on $M _ { 7 }$ .This statement follows from the Weitzenbock formula (see e.g. [31])

$$
\alpha ^ { i } \Delta \alpha _ { i } = - \alpha ^ { i } \nabla _ { j } \nabla ^ { j } \alpha _ { i } + R _ { i j } \alpha ^ { i } \alpha ^ { j } ,
$$

where the Laplacian is defined by $\Delta = d \delta + \delta d$ as usual in the harmonic analysis; $\delta$ is the codifferential and $\nabla$ is the covariant derivative. Since a harmonic one-form $\alpha$ satisfies $d \alpha =$ （204 $\delta \alpha = 0$ , the left-hand side of (3.36) vanishes. On the other hand,if we integrate the right-hand side on $M _ { 7 }$ , it should be positive by the partial integration and the formula (3.35). Therefore, such a harmonic one-form $\alpha$ cannot exist and this completes our no-go argument for $L i _ { 4 } \times M _ { 7 }$

# 3.2 Warp Factor in $L i _ { 4 } \times M _ { 7 }$

Actually, we can still have the freedom of taking the warp factor of the metric into account as follows

$$
d s ^ { 2 } = e ^ { 2 A ( \xi ) } d s _ { L i _ { 4 } } ^ { 2 } + e ^ { \frac { 4 } { 5 } A ( \xi ) } d s _ { M _ { 7 } } ^ { 2 } ,
$$

where $\xi$ denotes the seven coordinates of $M _ { 7 }$ . We fixed the power of the warp factor by the reparameterizations such that the one-form $\alpha$ in $M _ { 7 }$ again becomes harmonic $d \alpha = d * \alpha = 0$ （20 due to the fux equation of motion. The equations of motion for fluxes are only modified by powers of $e ^ { A }$ . For example, we can show

$$
\alpha ^ { 2 } = \frac { \beta ^ { 2 } } { z } e ^ { \frac { 6 } { 5 } A } = 4 ( z - 1 ) e ^ { \frac { 2 4 } { 5 } A } .
$$

We also have to require $f = \Omega _ { i j k } = 0$ again. Moreover， by using these relations， we can eventually evaluate the right-hand side of (3.36) as follows:

$$
\begin{array} { r l } & { R _ { i j } \alpha ^ { i } \alpha ^ { j } - \alpha ^ { i } \nabla _ { j } \nabla ^ { j } \alpha _ { i } } \\ { = } & { 4 z ( z - 1 ) ( z + 4 ) e ^ { \frac { 1 8 } { 5 } A } + \frac { 4 8 ( z - 1 ) } { 5 } \left( \nabla _ { i } \nabla ^ { i } A + 6 ( \nabla _ { i } A ) ( \nabla ^ { i } A ) \right) e ^ { \frac { 2 4 } { 5 } A } + 6 \alpha ^ { i } \alpha ^ { j } \nabla _ { i } \nabla _ { j } A } \\ & { + ( \nabla _ { i } \alpha ^ { j } ) ( \nabla ^ { i } \alpha _ { j } ) - \nabla _ { j } ( \alpha ^ { i } \nabla ^ { j } \alpha _ { i } ) } \\ { = } & { 4 z ( z - 1 ) ( z + 4 ) e ^ { \frac { 1 8 } { 5 } A } - \frac { 1 1 5 2 } { 2 5 } ( z - 1 ) ( \nabla _ { i } A ) ( \nabla ^ { i } A ) e ^ { \frac { 2 4 } { 5 } A } + 6 \nabla ^ { i } ( \alpha _ { i } \alpha _ { j } \nabla ^ { j } A ) + ( \nabla _ { i } \alpha ^ { j } ) ( \nabla ^ { i } A ) ( \nabla ^ { j } \alpha ^ { j } ) } \end{array}
$$

Now let us recall that $M _ { 7 }$ is a compact manifold. Therefore, the function $A ( \xi )$ on $M _ { 7 }$ should take its maximum and minimum value somewhere. Suppose it takes the minimum value at （204号 $\xi = \xi _ { m i n }$ . It is obvious that

$$
\partial _ { i } A ( \xi _ { m i n } ) = 0 , \qquad \alpha ^ { i } \alpha ^ { j } \partial _ { i } \partial _ { j } A ( \xi _ { m i n } ) \geq 0 .
$$

On the other hand, since $\alpha$ is a harmonic one-form, the left-hand side of (3.39) is vanishing as explained before. By evaluating this at $\xi = \xi _ { m i n }$ ， we obtain

$$
0 = 4 z ( z - 1 ) ( z + 4 ) e ^ { \frac { 1 8 } { 5 } A } + 6 \alpha ^ { i } \alpha ^ { j } \partial _ { i } \partial _ { j } A + ( \nabla _ { i } \alpha ^ { j } ) ( \nabla ^ { i } \alpha _ { j } ) .
$$

This is clearly inconsistent as its right-hand side is positive. Thus, there are no such harmonic one-form $\alpha$ and this finishes the no-go theorem for the warped case.

# 4Massive IIA Supergravity on $L i _ { 4 } \times M _ { 6 }$

# 4.1 Massive IIA theory

The massive IIA supergravity [32] is obtained by adding a new auxiliary scalar feld $M$ and ten-form RR-flux $F _ { 1 0 } = d C _ { 9 } ^ { \prime }$ and by shifting the flux $F _ { 2 }$ and $F _ { 4 }$ such that

$$
\begin{array} { l } { { \displaystyle \tilde { F } _ { 2 } = d C _ { 1 } - M B _ { 2 } , } } \\ { { \displaystyle \tilde { F } _ { 4 } = d C _ { 3 } - A _ { 1 } \wedge H _ { 3 } + \frac { 1 } { 2 } M B _ { 2 } \wedge B _ { 2 } . } } \end{array}
$$

The action is defined by

$$
S _ { m a s s i v e \ I I A } = \frac { 1 } { 2 \kappa ^ { 2 } } \int \mathcal { L } ,
$$

where

$$
\begin{array} { c } { { { \mathcal { L } = \sqrt { - g } e ^ { - 2 \phi } ( R + 4 \partial _ { \mu } \phi \partial ^ { \mu } \phi ) - { \displaystyle \frac { e ^ { - 2 \phi } } { 2 } } H _ { 3 } \wedge * H _ { 3 } - \frac { 1 } { 2 } \tilde { F } _ { 2 } \wedge * \tilde { F } _ { 2 } - \frac { 1 } { 2 } \tilde { F } _ { 4 } \wedge * \tilde { F } _ { 4 } - \frac { 1 } { 2 } M \wedge * h _ { 2 } } } } \\ { { { { } } } } \\ { { + M \wedge F _ { 1 0 } - \frac { 1 } { 2 } B _ { 2 } \wedge d C _ { 3 } \wedge d C _ { 3 } - \frac { M } { 6 } d C _ { 3 } \wedge B _ { 2 } \wedge B _ { 2 } \wedge B _ { 2 } - \frac { M ^ { 2 } } { 4 0 } B _ { 2 } \wedge B _ { 2 } \wedge B _ { 2 } \wedge B _ { 2 } \wedge * \partial _ { \mu } } } \\ { { { } } } \end{array}
$$

The Bianchi identities and equations of motion of the fluxes are summarized as follows:

$$
\begin{array} { r c l } { { } } & { { } } & { { d M _ { 3 } = 0 , \quad d M = 0 , } } \\ { { } } & { { } } & { { d \tilde { F } _ { 2 } = - M H _ { 3 } , \quad d \tilde { F } _ { 4 } = - \tilde { F } _ { 2 } \wedge H _ { 3 } , } } \\ { { } } & { { } } & { { d \ast \tilde { F } _ { 2 } = H _ { 3 } \wedge \ast \tilde { F } _ { 4 } , } } \\ { { } } & { { } } & { { d \ast \tilde { F } _ { 4 } = - \tilde { F } _ { 4 } \wedge H _ { 3 } , } } \\ { { } } & { { } } & { { d \big ( e ^ { - 2 \phi } \ast H _ { 3 } \big ) = - M \wedge \ast \tilde { F } _ { 2 } + \displaystyle \frac { 1 } { 2 } \tilde { F } _ { 4 } \wedge \tilde { F } _ { 4 } - \tilde { F } _ { 2 } \wedge \ast \tilde { F } _ { 4 } . } } \end{array}
$$

The equation of motion for $C _ { 9 }$ requires that $M$ is a constant: $M = m$ . On the other hand, the equation of motion of $M$ just determines $F _ { 1 0 }$ in terms of other fields.

The dilaton equation of motion is

$$
R + 4 \nabla _ { \mu } \nabla ^ { \mu } \phi - \frac { 1 } { 1 2 } H _ { \mu \nu \rho } H ^ { \mu \nu \rho } - 4 \nabla _ { \mu } \phi \nabla ^ { \mu } \phi = 0 .
$$

The Einstein equation becomes

$$
R _ { \mu \nu } + \frac { 1 } { 4 } g _ { \mu \nu } A = - 2 \nabla _ { \mu } \nabla _ { \nu } \phi + \frac { 1 } { 4 } H _ { \mu \alpha \beta } H _ { \nu } ^ { \ \alpha \beta } + \frac { 1 } { 2 } e ^ { 2 \phi } \tilde { F } _ { \mu \alpha } \tilde { F } _ { \nu } ^ { \ \alpha } + \frac { 1 } { 1 2 } e ^ { 2 \phi } \tilde { F } _ { \mu \alpha \beta \gamma } \tilde { F } _ { \nu } ^ { \ \alpha \beta \gamma } ,
$$

where

$$
A \equiv { \frac { e ^ { 2 \phi } } { 4 ! } } \tilde { F } _ { \mu \nu \rho \sigma } \tilde { F } ^ { \mu \nu \rho \sigma } + { \frac { e ^ { 2 \phi } } { 2 ! } } \tilde { F } _ { \mu \nu } \tilde { F } ^ { \mu \nu } + e ^ { 2 \phi } M ^ { 2 } .
$$

# 4.2 No-go Argument in Massive IIA on $L i _ { 4 } \times M _ { 6 }$

Now we would like to see if the spacetime $L i _ { 4 } \times M _ { 6 }$ can be a classical solution of the tendimensional massive IIA supergravity. The form of Ricci tensor and the scale invariance require that the dependence of fluxes on $r$ all comes from the normalized one-forms $\theta ^ { t , x , y , z }$ again.

In this subsection,we take into account only even forms in $M _ { 6 }$ in the fux ansatz to make the problem easier. In this case, the general flux ansatz with the required Lorentz symmetry breaking for the Lifshitz spacetime can be written as follows8

$$
\begin{array} { l } { M = m , } \\ { \displaystyle { \tilde { F } _ { 2 } = \alpha \theta ^ { t } \theta ^ { r } + \eta \theta ^ { x } \theta ^ { y } + J _ { 1 } , } } \\ { \displaystyle { H _ { 3 } = \beta \theta ^ { x } \theta ^ { y } \theta ^ { r } , } } \\ { \displaystyle { \tilde { F } _ { 4 } = f \theta ^ { t } \theta ^ { x } \theta ^ { y } \theta ^ { r } + \theta ^ { x } \theta ^ { y } J _ { 2 } + \theta ^ { t } \theta ^ { r } J _ { 3 } + V _ { 4 } , } } \end{array}
$$

where $\alpha , \beta$ and $\eta$ are constants. $J _ { 1 } , J _ { 2 }$ and $J _ { 3 }$ are some two-forms on $M _ { 6 }$ ，and $V _ { 4 }$ is a certain four-form on $M _ { 6 }$

Bianchi identities lead to

$$
d J _ { 1 } = d J _ { 2 } = d J _ { 3 } = 0 , J _ { 2 } = - \frac { \beta L } { 2 } J _ { 1 } , m = - \frac { 2 \eta } { \beta L } , d V _ { 4 } = 0 .
$$

The flux equations of motion for $\tilde { F } _ { 2 }$ and ${ \tilde { F } } _ { 4 }$ lead to

$$
d * J _ { 1 } = d * J _ { 3 } = 0 , d * V _ { 4 } = 0 , f \beta L = 2 \alpha , \beta L V _ { 4 } = 2 * J _ { 3 } .
$$

Below we write $J _ { 1 } \equiv J$ and $J _ { 3 } \equiv K$ . Notice that $\begin{array} { r } { J _ { 2 } = - \frac { \beta L } { 2 } J } \end{array}$ and $\begin{array} { r } { V _ { 4 } = \frac { 2 } { \beta L } * K } \end{array}$

Notice that the presence of a non-trivial warp factor $\Omega ( \xi )$ (which depends on the coordinates $\xi$ of $M _ { 6 }$ ） in the metric $d s ^ { 2 } = \Omega ^ { 2 } ( d s _ { L i _ { 4 } } ^ { 2 } + d s _ { M _ { 6 } } ^ { 2 } )$ contradicts with one of the fux equations of motion that reads $f \beta L = 2 \alpha \Omega ^ { 4 } ( \xi )$ . Therefore, in this setup we can set $\Omega = 1$ , namely the metric is in the form of the direct product.

If we plug in the explicit values of the fluxes, the $( t t )$ ， $( x x )$ and $( r r )$ components of Einstein equation are expressed as follows:

$$
\begin{array} { r l } & { - \displaystyle \frac { z ( z + 2 ) } { L ^ { 2 } } = - \frac { A } { 4 } - \frac { g _ { s } ^ { 2 } } { 2 } \alpha ^ { 2 } - \frac { 2 g _ { s } ^ { 2 } \alpha ^ { 2 } } { \beta ^ { 2 } L ^ { 2 } } - \frac { g _ { s } ^ { 2 } K ^ { 2 } } { 4 } , } \\ & { - \displaystyle \frac { z + 2 } { L ^ { 2 } } = - \frac { A } { 4 } - \frac { 2 g _ { s } ^ { 2 } \alpha ^ { 2 } } { \beta ^ { 2 } L ^ { 2 } } + \frac { g _ { s } ^ { 2 } \beta ^ { 2 } L ^ { 2 } J ^ { 2 } } { 1 6 } + \frac { g _ { s } ^ { 2 } m ^ { 2 } L ^ { 2 } \beta ^ { 2 } } { 8 } + \frac { \beta ^ { 2 } } { 2 } , } \\ & { - \displaystyle \frac { z ^ { 2 } + 2 } { L ^ { 2 } } = - \frac { A } { 4 } - \frac { g _ { s } ^ { 2 } } { 2 } \alpha ^ { 2 } - \frac { 2 g _ { s } ^ { 2 } \alpha ^ { 2 } } { \beta ^ { 2 } L ^ { 2 } } - \frac { g _ { s } ^ { 2 } K ^ { 2 } } { 4 } + \frac { \beta ^ { 2 } } { 2 } , } \end{array}
$$

with

$$
A = g _ { s } ^ { 2 } \left[ - \frac { 4 \alpha ^ { 2 } } { \beta ^ { 2 } L ^ { 2 } } + \frac { J ^ { 2 } \beta ^ { 2 } L ^ { 2 } } { 8 } - \frac { K ^ { 2 } } { 2 } + \frac { 2 K ^ { 2 } } { \beta ^ { 2 } L ^ { 2 } } - \alpha ^ { 2 } + \frac { m ^ { 2 } L ^ { 2 } \beta ^ { 2 } } { 4 } + \frac { J ^ { 2 } } { 2 } + m ^ { 2 } \right] .
$$

Bytaking the differences,we immediately obtain

$$
\begin{array} { l } { \displaystyle { \beta ^ { 2 } = \frac { 4 ( z - 1 ) } { L ^ { 2 } } , } } \\ { \displaystyle { \frac { z ( z - 1 ) } { L ^ { 2 } } = \frac { g _ { s } ^ { 2 } m ^ { 2 } L ^ { 2 } \beta ^ { 2 } } { 8 } + \frac { g _ { s } ^ { 2 } \alpha ^ { 2 } } { 2 } + \frac { g _ { s } ^ { 2 } \beta ^ { 2 } L ^ { 2 } J ^ { 2 } } { 1 6 } + \frac { g _ { s } ^ { 2 } K ^ { 2 } } { 4 } . } } \end{array}
$$

On the other hand,after combined with (4.55) and (4.56), the equation (4.51) actually leads to $z ~ = ~ - 4$ . This shows that we can only have unphysical solutions as the equation (4.55) implies that the $H$ -fux becomes imaginary. In this way, we have found that under this ansatz, there is no physical solution corresponding to the Lifshitz-like fixed point in the IIA massive supergravity.

Moreover, we can find explicit unphysical solutions. Suppose that $M _ { 6 }$ is Kahler-Einstein and that the fluxes are given by the parameters

$$
m = \eta = 0 , \quad J _ { 1 } = - \frac { 2 k } { R ^ { 2 } } \omega , \quad J _ { 2 } = \frac { k L \beta } { R ^ { 2 } } \omega , \quad J _ { 3 } = V _ { 4 } = 0 ,
$$

where $R$ is the radius of $M _ { 6 }$ such that $\begin{array} { r } { R _ { i j } = \frac { 8 } { R ^ { 2 } } g _ { i j } } \end{array}$ . The Kahler form $\omega$ is a harmonic two-form, which satisfies $g ^ { k l } { \omega } _ { i k } { \omega } _ { j l } = g _ { i j }$ . Then we can show that al equations of motion are satisfied if we set

$$
\alpha ^ { 2 } = \frac { 3 5 } { 2 g _ { s } ^ { 2 } L ^ { 2 } } , \quad \beta ^ { 2 } = - \frac { 2 0 } { L ^ { 2 } } , \quad k ^ { 2 } = - \frac { 6 L ^ { 2 } } { g _ { s } ^ { 2 } } , \quad R ^ { 2 } = 4 L ^ { 2 } , \quad z = - 4 .
$$

This requires that $\beta$ and $k$ to be imaginary. This argument includes Lorentz symmetry breaking deformations of the $A d S _ { 4 } \times C P ^ { 3 }$ solution dual to the $\mathcal { N } = 6$ Chern-Simons gauge theory [33]. Notice that this is a rather basic setup as in this model all moduli are stabilized.

Finally, it is also possible to check that the situation will not be improved even if we insert spacetime flling D-branes i.e. non-BPS D9-branes $^ { 9 }$ whose action is proportional to $\int d ^ { 9 } x e ^ { - \phi } \sqrt { g }$ setting the tachyon feld vanishing.

# 4.3No-go Argument for Nearly Kähler Compactifications

To generalize our previous no-go argument of Lifshitz-like solutions, we need to take into account odd forms in the compact six-dimensional manifold $M _ { 6 }$ . Since a general argument in this case turns out to be quite complicated,we would like to assume the case where $M _ { 6 }$ is a nearly Kahler manifold, including Calabi-Yau manifolds. This is motivated by the expectation that the Lifshitz-like solutions will appear by deforming the $A d S _ { 4 } \times M _ { 6 }$ solution to the massive IIA supergravity. The backgrounds $A d S _ { 4 } \times M _ { 6 }$ have been intensively studied in the context of flux compactifications (see e.g. [35-39]). One major way to maintain the $N = 1$ supersymmetry after the compactification is to assume that $M _ { 6 }$ is a nearly Kähler manifold [35,38,39],which is known to be Einstein.Thus,we believe that this restriction to nearly Kähler manifolds will not lose the generality seriously.

When $M _ { 6 }$ is nearly Kähler, the two-form $J$ that defines the almost complex structure and the holomorphic three-form $\Omega$ satisfies

$$
\begin{array} { l } { \Omega \wedge J = 0 , } \\ { V _ { 6 } = \mathrm { R e } \Omega \wedge \mathrm { I m } \Omega = \displaystyle \frac { 1 } { 3 ! } J \wedge J \wedge J , } \\ { d \mathrm { R e } \Omega = 0 , } \\ { d J = b \mathrm { R e } \Omega , } \\ { d \mathrm { I m } \Omega = - \displaystyle \frac { b } { 6 } J \wedge J . } \end{array}
$$

The constant $b$ measures the extent to which the metric deviates from the Calabi-Yau condition and is relate to the Ricci curvature via

$$
R _ { i j } = \frac { 5 } { 3 6 } b ^ { 2 } g _ { i j } .
$$

Since it is straightforward to show that there is no physical solution when $b = 0$ (i.e.when $M _ { 6 }$ is Calabi-Yau),we will restrict to the values $b \neq 0$ below.

By employing $J$ and $\Omega$ ， we can write down the flux ansatz $^ { 1 0 }$ with the expected Lorentz symmetry breaking as follows:11

$$
\begin{array} { l } { M = m , } \\ { \displaystyle \tilde { F } _ { 2 } = a J + \alpha \theta ^ { t } \theta ^ { r } + \eta \theta ^ { x } \theta ^ { y } , } \\ { \displaystyle H _ { 3 } = \beta \theta ^ { x } \theta ^ { y } \theta ^ { r } + k \mathrm { R e } \Omega , } \\ { \displaystyle \tilde { F } _ { 4 } = f \theta ^ { t } \theta ^ { x } \theta ^ { y } \theta ^ { r } + g \theta ^ { x } \theta ^ { y } \wedge J + h \theta ^ { t } \theta ^ { r } \wedge J + q \theta ^ { t } \wedge \mathrm { R e } \Omega + \frac { s } { 2 } J ^ { 2 } . } \end{array}
$$

The Bianchi identities lead to

$$
\begin{array} { l } { \displaystyle { \eta = - \frac { m \beta L } { 2 } , \quad a b + k m = 0 , } } \\ { \displaystyle { g = - \frac { \beta a L } { 2 } , \quad g b + \eta k = 0 , \quad h b - \frac { z q } { L } + \alpha k = 0 . } } \end{array}
$$

The equations of motion lead to

$$
\begin{array} { l } { \displaystyle \frac { 2 \alpha } { L } = f \beta + k q , } \\ { \displaystyle k f - \beta q + s b = 0 , \quad - \frac { h } { L } + \frac { b q } { 6 } + \frac { s \beta } { 2 } = 0 , } \\ { \displaystyle \frac { z \beta } { L g _ { s } ^ { 2 } } + m \eta - 3 h s + 3 g a - \alpha f = 0 , } \\ { \displaystyle \frac { m a } { 2 } - \frac { f s } { 2 } - g h + s a - \frac { \alpha h } { 2 } + \frac { g \eta } { 2 } - \frac { b k } { 6 g _ { s } ^ { 2 } } = 0 , } \\ { \displaystyle m \alpha + 3 g s + 3 h a + f \eta = 0 . } \end{array}
$$

Next we would like to write down the Einstein equationsl2. The useful identities are

$$
J _ { i k } J _ { j l } g ^ { k l } = g _ { i j } , ~ \mathrm { R e } \Omega _ { i k l } \mathrm { R e } \Omega _ { j } { } ^ { k l } = g _ { i j } .
$$

The Einstein equation can be eventually expressed as follows after taking suitable linear combinations

$$
\begin{array} { r l } & { - \frac { z \left( z + 2 \right) } { L ^ { 2 } } = - \frac { g _ { s } ^ { 2 } } { 4 } ( \alpha ^ { 2 } + f ^ { 2 } + 3 g ^ { 2 } + 3 h ^ { 2 } + q ^ { 2 } + 3 s ^ { 2 } + 3 a ^ { 2 } ) - \frac { g _ { s } ^ { 2 } \eta ^ { 2 } } { 4 } - \frac { g _ { s } ^ { 2 } m ^ { 2 } } { 4 } , } \\ & { \frac { z \left( z - 1 \right) } { L ^ { 2 } } = \frac { g _ { s } ^ { 2 } } { 2 } ( \alpha ^ { 2 } + 3 h ^ { 2 } + 3 g ^ { 2 } ) + \frac { g _ { s } ^ { 2 } \eta ^ { 2 } } { 2 } , } \\ & { \frac { 2 \left( z - 1 \right) } { L ^ { 2 } } = \frac { g _ { s } ^ { 2 } } { 2 } q ^ { 2 } + \frac { \beta ^ { 2 } } { 2 } . } \end{array}
$$

If $q = 0$ , then the situation becomes simpler and become the same as the previous subsection and we immediately find $z = - 4$ . In this case, there are no physical solutions. Thus,we need to set $q \neq 0$ below.

Now the remaining equations of motion which we have to impose are the dilaton equation and the Einstein equation in $M _ { 6 }$ direction. They are equivalent to

$$
\begin{array} { l l l } { { } } & { { \displaystyle - \frac { 2 ( z ^ { 2 } + 2 z + 3 ) } { L ^ { 2 } } + R _ { 6 } = \frac { \beta ^ { 2 } + k ^ { 2 } } { 2 } , } } \\ { { 0 } } & { { = } } & { { \displaystyle \frac { 1 } { 6 } H _ { \mu \nu \rho } H ^ { \mu \nu \rho } - \frac { 3 g _ { s } ^ { 2 } } { 4 } \tilde { F } _ { \mu \nu } \tilde { F } ^ { \mu \nu } - \frac { g _ { s } ^ { 2 } } { 4 8 } \tilde { F } _ { \mu \nu \rho \lambda } \tilde { F } ^ { \mu \nu \rho \lambda } - \frac { 5 } { 2 } g _ { s } ^ { 2 } m ^ { 2 } } } \\ { { } } & { { = } } & { { \displaystyle \beta ^ { 2 } + k ^ { 2 } - \frac { 3 g _ { s } ^ { 2 } } { 2 } ( 3 a ^ { 2 } - \alpha ^ { 2 } + \eta ^ { 2 } ) - \frac { g _ { s } ^ { 2 } } { 2 } ( - f ^ { 2 } + 3 g ^ { 2 } - 3 h ^ { 2 } - q ^ { 2 } + 3 s ^ { 2 } ) - \frac { 5 } { 2 } g _ { s } ^ { 2 } m ^ { 2 } . } } \end{array}
$$

By combining these with previous equations we can actually show

$$
3 L ^ { 2 } k ^ { 2 } + 3 L ^ { 2 } \beta ^ { 2 } = - 6 + z - 2 z ^ { 2 } .
$$

Since the right-hand side is clearly negative when $z \ > \ 1$ ，we cannot construct any physical solutions.

# 4.4 Adding Orientifold Plane

Adding orientifold planes in general enlarges the set of possible solutions in the flux compactification. For example, adding an O6 plane to the IIA string flux compactification allows supersymmetric $A d S _ { 4 } \times M _ { 6 }$ solutions with all moduli stablized and with $M _ { 6 }$ being half-flat [35-39]. Supersymmetry requires an O6 to wrap the entire $A d S _ { 4 }$ and a supersymmetric three-cycle inside （204号 $M _ { 6 }$ . Moreover, smearing an O6 inside $M _ { 6 }$ allows solutions with $M _ { 6 }$ being Calabi-Yau three-fold. For our present purpose, since we do not require Lorentz symmetry, more generic O6 configurations should in principle be allowed (for example, with an O6 wrapping only $( t x y )$ -direction and a four-cycle inside $M _ { 6 }$ ). However, for simplicity and for parallel comparison with the $A d S _ { 4 }$ case,we will only consider the configuration of an O6 wrapping the entire $\mathit { L i } _ { 4 }$ and a three-cycle inside $M _ { 6 }$ ：

In this subsection，we will show that adding an O6 plane wrapping the entire $L i _ { 4 }$ and a three-cycle inside $M _ { 6 }$ will not help evade the no-go theorem in the case of $L i _ { 4 } \times M _ { 6 }$ with $M _ { 6 }$ being nearly Kahler. To warm up,we first show that even in the presence of a smeared O6 plane,there exist no Lifshitz-like solutions when $M _ { 6 }$ is a Calabi-Yau three-fold with only one two-form (the Kähler form). Then, we wil generalize the result to the case where $M _ { 6 }$ is a nearly Kahler manifold.

The O6 plane couples to the $C _ { 7 }$ fux and sources $F _ { 2 }$ magnetically. Therefore,in the presence of O6 plane, the Bianchi identity of $F _ { 2 }$ flux becomes

$$
d \tilde { F } _ { 2 } = - M H _ { 3 } - \mu _ { 6 } \delta _ { 3 }
$$

where ${ \delta } _ { 3 }$ is three-form localized on the supersymmetric three-cycle. The smearing of the O6 plane is simply done by replacing $\mu _ { 6 } \delta _ { 3 }$ with $\mu _ { 6 } ^ { \prime } \mathrm { R e } \Omega$ [36].

For $M _ { 6 }$ being $C Y _ { 3 }$ with only one two-form,we can first start with the most generic flux ansatz,then use the Bianchi identities and equations of motions of the fluxes to eliminate most of the terms. In the end, there are only two possibilities:

$$
\begin{array} { r l r } { H _ { 3 } = \beta \theta ^ { x y r } , } & { \quad } & { \tilde { F } _ { 2 } = \alpha \theta ^ { t r } + \eta \theta ^ { x y } + a J , \quad } & { \tilde { F } _ { 4 } = f \theta ^ { t x y r } + \frac { s } { 2 } J ^ { 2 } + h \theta ^ { t r } \wedge J + g \theta ^ { x y } \wedge J } \\ { H _ { 3 } = k \mathrm { R e } \Omega , } & { \quad } & { \tilde { F } _ { 2 } = a J , \quad } & { \tilde { F } _ { 4 } = \frac { s } { 2 } J ^ { 2 } } & { ( 4 . 8 \ell ^ { - 1 } ) ^ { \ell } , } \end{array}
$$

The first one reduces to the situation without the O6 plane. Only the second one takes advantage of the presence of the O6 plane, however, it does not break Lorentz symmetry. Therefore,adding an O6 plane in this case does not help finding solution with the anisotropic scale invariance. This is also clear from (4.76) as it leads to $z = 1$ by setting $q = \beta = 0$ . Notice that though the presence of O6 plane changes Einstein equations, it does not change the differences of them such as (4.76).

For $M _ { 6 }$ being nearly Kahler, the ineffectiveness of adding an O6 also arises from the fluxes. The flux ansatz remains the same as the one without the O6; the only change is that the second equation coming from the $F _ { 2 }$ 's Bianchi identity now becomes

$$
a b + k m = n _ { 6 } ,
$$

where $n _ { \mathrm { 6 } }$ counts the smeared O6 charge after a proper normalization. In the process of solving flux Bianchi identities and equations of motion, the first equation from $F _ { 4 }$ 's Bianchi identity and the third equation from $H _ { 3 }$ 's equations of motion become

$$
\beta n _ { 6 } = 0 , \qquad \mathrm { a n d } \qquad q n _ { 6 } = 0 ,
$$

respectively. Namely， for a nonzero smeared O6 charge，we have $q \ = \ \beta \ = \ 0$ .Again (4.76) requires the relativistic dynamical exponent $z = 1$ . This means that adding an O6 does not help evade the no-go theorem in the present setup.

# 5 Conclusion and Discussion

# 5.1 Conclusions:No-go Theorems for Lifshitz-like Spacetime in Supergravities

In this paper, we examined possibilities of string theory embeddings of the gravity duals (denoted by $L i _ { d }$ ）for $( d - 1 )$ -dimensional quantum Lifshitz-like fixed points,which are invariant under anisotropic scale transformations. We considered the ten- or eleven-dimensional supergravity description of string theory by taking the ordinary low energy limit. A no-go argument in supergravities as general and simple as the one for de-Sitter spaces [28] or the one for fux compactifications [29] does not seem to be available in our case because we consider less symmetric spacetimes with a negative curvature. Therefore, we had to examine each possibilities of compactifications of supergravities.

In all of our supergravity setups (we will summarize them in the next subsection) we examined,we found that it is impossible to construct $L i _ { 4 }$ solutions. Notice that in all such setups, there exist $A d S _ { 4 }$ solutions. Even though our analysis has been done only for the $L i _ { 4 }$ spacetime defined by (2.3),we believe that our result wil not significantly lose generality as many aspects of $A d S _ { 4 }$ solutions are similar to $A d S _ { 3 }$ and $A d S _ { 5 }$ . Motivated by these results,we are tempted to conjecture that the gravity duals $L i _ { d }$ of Lifshitz-like theories cannot be embedded into any supergravity description of string theory or M-theory. The rigorous proof of this no-go theorem will certainly be an important future problem.

Under certain flux ansatze, we proved that no solutions of the form $L i _ { 4 } \times M _ { 7 }$ ，where $M _ { 7 }$ is an arbitrary compact manifold,are alowed in the eleven-dimensional supergravity, even if we take the possibility of warp factor into account. We also presented a similar no-go theorem in the massive type IA supergravity for the spacetime $L i _ { 4 } \times M _ { 6 }$ . Finally we examined massive IIA compactifications on nearly Kahler manifolds and showed that solutions of the form $L i _ { 4 } \times M _ { 6 }$ are impossible.

Since the Einstein gravity coupled to a massive vector field can have a Lifshitz-like solution as we noticed in the end of section 2, one may expect that holographic superconductor systems [40,41] which can be embedded into string theory may have $L i _ { d }$ solutions.13 However， we can check after some analysis that $L i _ { d }$ solutions are impossible as least in the recently found string theory embeddings [42,43] via ten or eleven dimensional supergravity, as consistent with our claim. In the Chern-Simons-Maxwell type description (2.1) of the gravity dual, our no-go theorem comes from the fact that in the string compactification, the cosmological constant $\Lambda$ （20 and the Chern-Simons coefficient $c$ cannot be chosen independently.

As in the case of de-Sitter spaces [44] or flux compactifications [29],one might expect that the addition of orientifolds or non-supersymmetric D-branes may evade our no-go arguments in supergravities. We performed preliminary analysis in tractable examples and observed that such effects do not help us to construct $L i _ { d }$ spacetimes. Therefore,we do not know at all whether a gravity dual of non-relativistic Lifshitz-like theories exists in string theory or not.We might also improve this situation by considering non-critical string setups such as in [45]. These issues should certainly deserve future studies.

# 5.2 Summary of the No-go Setups

Since it might be helpful for future studies of possible Lifshitz-like solutions in supergravities, we would like to summarize our setups where we could manage to prove the no-go theorems for a four dimensional Lifshitz spacetime $L i _ { 4 }$ as follows:

· The eleven-dimensional supergravity with the four form flux ansatz given by (3.15) compactified on an arbitrary manifold $M _ { 7 }$ . (Section 3)   
· The ten-dimensional massive IIA supergravity with the flux ansatz (4.48) compactified on an arbitrary manifold $M _ { 6 }$ . (Section 4.2)   
· The ten-dimensional massive IIA supergravity with the flux ansatz (4.65) compactified on an nearly Kahler manifold $M _ { 6 }$ . (Section 4.3)   
· The previous massve IIA nearly Kahler compactifications with orientfold 6-plane. (Section 4.4)

# 5.3 Why String Duals ofLifshitz-like Points are Hard

Before we end this paper, we would like to suggest an intuitive physical reason for our no-go theorems. Consider type IIA or IIB string theory. Let us remember that to realize a $L i _ { 4 }$ solution we need to turn on several RR and $H$ fluxes to break the Lorentz symmetry. The presence of the Chern-Simons coupling, which is important in the argument of [3] as reviewed in section 2, requires turning on an $H$ flux.Then the requirement $d H = 0$ argues that $H \propto \theta ^ { x } \theta ^ { y } \theta ^ { r }$ asis indeed so in our setups.14 We can easily imagine that such a gravity solution should be dual to a non-commutative gauge theory as the NS $B$ field will be induced in the boundary [46]. The effect of non-commutativity is interpreted as the the UV cutoff of the gauge theory. Therefore, the AdS/CFT argues that the IR region is described by $A d S$ , while in the UV region, the spatial directions shrink to zero size. The latter fact requires $z < 0$ as in the solutions [47] and we will not have a nice scaling limit which extracts the UV part because it contradicts with the relation like (3.30)，which requires $z > 1$ . Note that a simple analysis shows that this condition $z > 1$ （20 should always be correct even in the presence of the warp factor in the metric $L i _ { 4 } \times M _ { 6 }$ ：

# Acknowledgments

We are very grateful to T. Azeyanagi， T. Banks, G. Giribet， J. Gomis, A. Maloney, J. Mcgreevy, M. Mulligan， N. Ohta, M. Schulz, D. T. Son，A. Strominger and K. Yoshida for useful discussions, and especially to G. Horowitz, S. Kachru and Y. Nakayama for very important comments. We are supported by World Premier International Research Center Initiative (WPI Initiative)， MEXT,Japan. The work of TN is supported by JSPS Grant-in-Aid for Scientific Research No.19.3589. The work of TT is supported in part by JSPS Grant-in-Aid for Scientific Research No.20740132 and by JSPS Grant-in-Aid for Creative Scientific Research No. 19GS0219. TT would like to thank very much the organizers and participants in the workshop “Quantum Criticality and the AdS/CFT Correspondence",at KITP in UCSB and those in the conference “Quantum Theory and Symmetries $6 ^ { \circ }$ at University of Kentucky, where some parts of our work have been done.

# References

[1] J.M. Maldacena,“The large N limit of superconformal feld theories and supergravity,” Adv. Theor. Math.Phys.2,231 (1998)[Int. J. Theor. Phys.38,1113 (1999)] [arXiv:hep-th/9711200]; O. Aharony, S. S. Gubser, J. M. Maldacena, H. Ooguri and Y. Oz,“Large N feld theories, string theory and gravity,” Phys. Rept. 323,183 (2000) [arXiv:hep-th/9905111].   
[2] D.T.Son,“Toward an AdS/cold atoms correspondence: a geometric realization of the Schroedinger symmetry,” Phys. Rev. D 78, 046003 (2008) [arXiv:0804.3972 [hep-th]; K. Balasubramanian and J. McGreevy,“Gravity duals for non-relativistic CFTs,” Phys. Rev. Lett. 101,061601 (2008) [arXiv:0804.4053 [hep-th]].   
[3] S. Kachru, X.Liu and M. Muligan,“Gravity Duals of Lifshitz-like Fixed Points,” Phys. Rev. D 78 (2008）106005 [arXiv:0808.1725 [hep-th]]. [4] S. Sekhar Pal,“Towards Gravity solutions of AdS/CMT,” arXiv:0808.3232 [hep-th];“More gravity solutions of AdS/CMT,” arXiv:0809.1756 [hep-th].   
[5]M. Taylor,“Non-relativistic holography,” arXiv:0812.0530[hep-th]. [6] A. Adams, A. Maloney, A. Sinha and S. E. Vazquez,“1/N Effects in Non-Relativistic Gauge-Gravity Duality,” JHEP 0903 (2009) 097 [arXiv:0812.0166 [hep-th]. [7] U. H.Danielsson and L. Thorlacius,“Black holes in asymptotically Lifshitz spacetime,” JHEP 0903 (2009) 070 [arXiv:0812.5088 [hep-th]]. [8] S. S.Pal,“Anisotropic gravity solutions in AdS/CMT,” arXiv:0901.0599 [hep-th]. [9] S.A. Hartnoll，“Lectures on holographic methods for condensed matter physics,” arXiv:0903.3246 [hep-th].   
[10] S.Schafer-Nameki, M. Yamazaki and K. Yoshida,“Coset Construction for Duals of Non-relativistic CFTs,” arXiv:0903.4245 [hep-th].   
[11] I. Gordeli and P. Koroteev，“Comments on Holography with Broken Lorentz Invariance,” arXiv:0904.0509 [hep-th].   
[12] C.P. Herzog,“Lectures on Holographic Superfuidity and Superconductivity,” arXiv:0904.1975 [hepth].   
[13] B.Chen and Q. G. Huang,“Field Theory at a Lifshitz Point,” arXiv:0904.4565 [hep-th].   
[14] T.Azeyanagi, W. Li and T. Takayanagi,“On String Theory Duals of Lifshitz-like Fixed Points,” arXiv:0905.0688 [hep-th].   
[15]R.B. Mann,“Lifshitz Topological Black Holes,” JHEP 0906 (2009) 075 [arXiv:0905.1136 [hep-th].   
[16] D. W. Pang,“A Note on Black Holes in Asymptotically Lifshitz Spacetime,” arXiv:0905.2678 [hepth].   
[17] A.Dhar,G. Mandal and S. R. Wadia,“Asymptotically free four-fermi theory in 4 dimensions at the z=3 Lifshitz-like fixed point,” arXiv:0905.2928 [hep-th].   
[18] G. Bertoldi, B.A. Burrington and A. Peet,“Black Holes in asymptotically Lifshitz spacetimes with arbitrary critical exponent,” arXiv:0905.3183 [hep-th].   
[19] S. R. Das and G. Murthy,‘ $C P ^ { N - 1 }$ Models at a Lifshitz Point,”arXiv:0906.3261 [hep-th].   
[20] Y.Nakayama,“Gravity Dual for Reggeon Field Theory and Non-linear Quantum Finance,” arXiv:0906.4112 [hep-th].   
[21] S.F.Ross and O. Saremi,“Holographic stress tensor for non-relativistic theories,” arXiv:0907.1846 [hep-th].   
[22] G. Bertoldi, B. A. Burrington and A. W. Peet,“Thermodynamics of black branes in asymptotically Lifshitz spacetimes,” arXiv:0907.4755 [hep-th].   
[23] E.Ardonne,P. Fendley,E.Fradkin,“ Topological Order and Conformal Quantum Critical Points,” Annals Phys. 310 (2004) 493 [arXiv:cond-mat/0311466].   
[24] C. Vafa,“The string landscape and the swampland,” arXiv:hep-th/0509212; H. Ooguri and C.Vafa, "On the geometry of the string landscape and the swampland,” Nucl. Phys. B 766, 21 (2007) [arXiv:hep-th/0605264].   
[25] C.P. Herzog, M. Rangamani and S.F. Ross,“Heating up Galilean holography,” JHEP 0811,080 (2008）[arXiv:0807.1099 [hep-th]; J. Maldacena, D. Marteli and Y. Tachikawa,“Comments on string theory backgrounds with nonrelativistic conformal symmetry,” JHEP 0810,072 (2008) [arXiv:0807.1100 [hep-th]; A. Adams, K. Balasubramanian and J. McGreevy,“Hot Spacetimes for Cold Atoms,” JHEP 0811, 059 （2008）[arXiv:0807.1111[hep-th]].   
[26] M. Fujita, W. Li, S. Ryu and T. Takayanagi, “Fractional Quantum Hall Efect via Holography: Chern-Simons, Edge States,and Hierarchy,” arXiv:0901.0924 [hep-th].   
[27] T. Azeyanagi, T .Nishioka and T. Takayanagi, unpublished note, 2007. A summary of this result can be found in the appendix C of [14].   
[28] J. M. Maldacena and C. Nunez,“Supergravity description of field theories on curved manifolds and a no go theorem,” Int. J. Mod. Phys. A 16 (2001) 822 [arXiv:hep-th/0007018].   
[29] S.B. Giddings, S. Kachru and J.Polchinski,“Hierarchies from fluxes in string compactifications," Phys. Rev. D 66,106006 (2002)[arXiv:hep-th/0105097].   
[30] J. Polchinski,“String theory. Vol. 1 and Vol. 2,” Cambridge, UK: Univ. Pr. (1998） 402 $p$   
[31] A. L. Besse,“Einstein Manifolds,” Classics in Mathematics, Springer, 1986.   
[32] L.J. Romans,“Massive N=2a Supergravity In Ten-Dimensions,” Phys.Lett.B 169 (1986) 374.   
[33] O.Aharony, O. Bergman, D.L. Jafferis and J. Maldacena,“N=6 superconformal Chern-Simonsmatter theories, M2-branes and their gravity duals,” JHEP 0810 (2008) 091 [arXiv:0806.1218 [hepth]].   
[34] A.Sen，“Tachyon dynamics in open string theory,” Int.J. Mod. Phys. A 20 (2005） 5513 [arXiv:hep-th/0410103].   
[35] D. Lust and D. Tsimpis，“Supersymmetric AdS(4) compactifications of IIA supergravity,” JHEP 0502 (2005) 027 [arXiv:hep-th/0412250].   
[36] O.DeWolfe, A. Giryavets,S. Kachru and W. Taylor,“Type IIA moduli stabilization,” JHEP 0507 (2005）066 [arXiv:hep-th/0505160].   
[37] B. S. Acharya, F. Benini and R. Valandro,“Fixing moduli in exact type IIA flux vacua,” JHEP 0702,018 (2007) [arXiv:hep-th/0607223].   
[38] G.Aldazabal and A. Font,“A second look at N=1 supersymmetric $A d S _ { 4 }$ vacua of type IIA supergravity,” JHEP 0802,086 (2008） [arXiv:0712.1021 [hep-th]].   
[39] A. K. Kashani-Poor,“Nearly Kaehler Reduction,” JHEP 0711,026 (2007) [arXiv:0709.4482 [hepth]].   
[40] S. S. Gubser,“Breaking an Abelian gauge symmetry near a black hole horizon,” Phys. Rev. D 78 (2008) 065034 [arXiv:0801.2977 [hep-th].   
[41] S.A. Hartnol, C.P. Herzog and G. T. Horowitz,“Building a Holographic Superconductor,” Phys. Rev.Lett.101 (2008) 031601 [arXiv:0803.3295 [hep-th].   
[42] S.S.Gubser, C.P. Herzog，S.S. Pufu and T. Tesileanu,“Superconductors from Superstrings,” arXiv:0907.3510 [hep-th].   
[43] J.P. Gauntlett， J. Sonner and T. Wiseman， “Holographic superconductivity in M-Theory,” arXiv:0907.3796 [hep-th]; J. P. Gauntlett, S. Kim, O. Varela and D. Waldram,“Consistent supersymmetric Kaluza-Klein truncations with massive modes,” JHEP 0904(2009)102 [arXiv:0901.0676 [hep-th]].   
[44] S. Kachru,R. Kallosh,A. Linde and S.P. Trivedi,“De Sitter vacua in string theory,” Phys. Rev. D 68（2003） 046005 [arXiv:hep-th/0301240].   
[45] A.Maloney, E. Silverstein and A. Strominger，“De Sitter space in noncritical string theory,” arXiv:hep-th/0205316.   
[46] N.Seiberg and E.Witten,“String theory and noncommutative geometry,” JHEP 9909,032(1999) [arXiv:hep-th/9908142].   
[47] A.Hashimoto and N. Itzhaki,“Non-commutative Yang-Mills and the AdS/CFT correspondence," Phys.Lett.B 465 (1999)142 [arXiv:hep-th/9907166]; J. M. Maldacena and J. G. Russo,“Large N limit of non-commutative gauge theories,” JHEP 9909 (1999) 025 [arXiv:hep-th/9908134].