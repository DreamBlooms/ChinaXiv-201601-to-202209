# Non-Supersymmetric Attractor Flow in Symmetric Spaces

Davide Gaiotto, Wei Li and Megha Padi

Jefferson Physical Laboratory， Harvard University， Cambridge MA O2138， USA

# Abstract

We derive extremal black hole solutions for a variety of four dimensional models which,after Kaluza-Klein reduction,admit a description in terms of 3D gravity coupled to a sigma model with symmetric target space. The solutions are in correspondence with certain nilpotent generators of the isometry group. In particular, we provide the exact solution for a non-BPS black hole with generic charges and asymptotic moduli in ${ \mathcal N } = 2$ supergravity coupled to one vector multiplet. Multi-centered solutions can also be generated with this technique. It is shown that the non-supersymmetric solutions lack the intricate moduli space of bound configurations that are typical of the supersymmetric case.

# Contents

# ．Introduction 3

# 2Framework 5

2.1 3D Moduli Space 5   
2.2 Attractor Flow Equation 6   
2.3 Models with Symmetric Moduli Space 6

# 3 Torus Reduction of $D$ -dimensional Pure Gravity 10

3.1 Kaluza-Klein Reduction 10   
3.2 Nilpotency 12   
3.3 A Toy Example: Hyperkahler Euclidean Metrics in Four Dimensions . 12   
3.4 Single-centered Black Holes in Pure Gravity 13   
3.4.1 Constructing the flow generator $k$ 13   
3.4.2 Full flow 15   
3.4.3 Example: 5D pure gravity compactified on a circle. 16

3.5Multi-centered Solutions in Pure Gravity 17

# 4 Attractor Flows in $G _ { 2 ( 2 ) } / ( S L ( 2 , \mathbb { R } ) \times S L ( 2 , \mathbb { R } ) )$ 18

4.1 The moduli space $\mathcal { M } _ { 3 D }$ ： 19  
4.2 Extracting the Coordinates from the Coset Elements 20  
4.3 Nilpotency of the Attractor Flow Generator $k$ ： 23  
4.4 Properties of Attractor Flow 24

# 5 Flow Generators in the $G _ { 2 ( 2 ) } / ( S L ( 2 , \mathbb { R } ) \times S L ( 2 , \mathbb { R } ) )$ Model

5.1 Construction of Flow Generators 26   
5.1.1 Constructing $k _ { B P S }$ using supersymmetry 26   
5.1.2 Constructing kNonBPs 28   
5.2 Properties of Flow Generators 29   
5.2.1 Properties of $k _ { B P S }$ （2 29   
5.2.2 Properties of $k _ { N o n B P S }$ （20 30

# 6Single-centered Attractor Flows in $G _ { 2 ( 2 ) } / ( S L ( 2 , \mathbb { R } ) \times S L ( 2 , \mathbb { R } ) )$ Model

6.1 BPS Attractor Flow 32   
6.1.1 Lifting a geodesic to $4 D$ （20 32   
6.1.2 $4 D$ solution for given set of charges 34   
6.2 non-BPS Attractor Flow 37   
6.2.1 Lifting a geodesic to $4 D$ （204号 37   
6.2.2 4 $4 D$ solution for given set of charges 39

# 7Multi-centered Attractor Flows in $G _ { 2 ( 2 ) } / ( S L ( 2 , \mathbb { R } ) \times S L ( 2 , \mathbb { R } ) )$ model

7.1 BPS Multi-centered Solutions 42   
7.2 non-BPS Multi-centered Solutions. 44

8 Conclusion and Discussion 46

、Derivation of the moduli space $\mathcal { M } _ { 3 D }$ 47

# Y Introduction

Soon after the attractor mechanism was first discovered in supersymmetric (BPS) black holes [1], it was reformulated in terms of motion on an effective potential for the moduli [2]. Ferrara et al demonstrated that the critical points of this potential correspond to the attractor values of the moduli. More recently, several groups used the effective potential to show that non-supersymmetric (non-BPS) extremal black holes can also exhibit the attractor mechanism, thereby creating a new and exciting field of research [3,4]. Many connections between non-BPS attractors and other active areas of string theory soon revealed themselves. Andrianopoli et al found that both BPS and non-BPS black holes embedded in a supergravity with a symmetric moduli space can be studied using the same formalism,and they uncovered many intricate relations between the two [5,6]. Dabholkar, Sen and Trivedi proposed a microstate counting for non-BPS black holes (albeit subject to certain constraints [7]). Saraikin and Vafa suggested that a new extension of topological string theory generalizes the Ooguri-Strominger-Vafa (OSV) formula such that it is also valid for non-supersymmetric black holes [8]. Studying non-BPS attractors could also give insight into non-supersymmetric fux vacua. Given all these possible applications, it is important to characterize non-BPS black holes as fully as possible.

There has been a great deal of progress in understanding the near-horizon region of these non-BPS attractors. The second derivative of the efective potential at the critical point determines whether the black hole is an attractor, and the location of the critical point yields the values of the moduli at the horizon; in this way, one can compute the stability and attractor moduli for al models with cubic prepotential [9,10]. However,the effective potential has only been formulated for the leading-order terms in the supergravity lagrangian. If one wants to include higher-derivative corrections, one can instead use Sen's entropy formalism, which incorporates Wald's formula, to characterize the near-horizon geometry in greater generality [11]. Sen's method has led to many new results [12,13, 14,15,16,17]. The tradeoffis that this method cannot be used to determine any properties of the solution away from the horizon.

The BPS attractor flow is constructed from the attractor value $z _ { B P S } ^ { * } = z _ { B P S } ^ { * } ( p ^ { I } , q _ { I } )$ by simply replacing the D-brane charges with the corresponding harmonic functions:

$$
z _ { B P S } ( \vec { x } ) = z _ { B P S } ^ { * } ( p ^ { I }  H ^ { I } ( \vec { x } ) , q _ { I }  H _ { I } ( \vec { x } ) )
$$

where the harmonic functions are

$$
\left( \begin{array} { c } { { H ^ { I } ( \vec { x } ) } } \\ { { H _ { I } ( \vec { x } ) } } \end{array} \right) = \left( \begin{array} { c } { { h ^ { I } } } \\ { { h _ { I } } } \end{array} \right) + \frac { 1 } { | \vec { x } | } \left( \begin{array} { c } { { p ^ { I } } } \\ { { q _ { I } } } \end{array} \right)
$$

Moreover, this procedure can be applied to construct the multi-centered BPS attractor flow that describes the supersymmetric black hole bound state [18], where the harmonic functions

are generalized to have multiple centers:

$$
\left( \begin{array} { l } { { H ^ { I } ( \vec { x } ) } } \\ { { H _ { I } ( \vec { x } ) } } \end{array} \right) = \left( \begin{array} { l } { { h ^ { I } } } \\ { { h _ { I } } } \end{array} \right) + \sum _ { i } { \frac { 1 } { | \vec { x } - \vec { x } _ { i } | } } \left( \begin{array} { l } { { ( p ^ { I } ) _ { i } } } \\ { { ( q _ { I } ) _ { i } } } \end{array} \right)
$$

It is conjectured in [19] that the non-BPS flow can be generated in the same fashion, namely, by replacing the charges in the attractor value with the corresponding harmonic functions. However，as will be proven in this paper，this procedure does not work for systems with generic charge and asymptotic moduli.1

In principle, one could construct the full non-BPS flow (the black hole metric, together with the attractor flow of the moduli) by solving the equation of motion derived from the lagrangian. However, this is a second-order differential equation and only reduces to a firstorder equation upon demanding the preservation of supersymmetry. Ceresole et al have written down an equivalent first-order equation in terms of a “fake superpotential",but so far, the fake superpotential can only be explicitly constructed for special charges and asymptotic moduli [21, 20]. The most generic non-BPS equation of motion is complicated enough that it has not yet been solved. Similarly, multi-centered non-BPS black holes have not been studied.

Our goal is to construct the full fow for non-BPS stationary black holes in four dimensions. Instead of directly solving the equation of motion,we reduce the action on the timelike isometry and dualize all4D vectors to scalars. The new moduli space $\mathcal { M } _ { 3 D }$ contains isometries corresponding to all the charges of the black hole,and the black hole solutions are simply geodesics on $\mathcal { M } _ { 3 D }$ . This method was introduced in [22] and has been used to construct static and rotating black holes in heterotic string theory [23, 24] and to study the classical BPS single-centered flow and its radial quantization [25, 26].

In this paper, we work in two specific theories of gravity, but we expect that this method can be used for any model whose $\displaystyle { \mathcal { M } } _ { 3 D }$ is symmetric. The basic technique is reviewed in more detail in Section 2. In Section 3, we show how this method works in a simple case: the toroidal compactification of $D$ -dimensional pure gravity. Section 4 serves as an introduction to single-centered attractor flow in ${ \mathcal N } = 2$ supergravity coupled to one vector multiplet, and Sections 5 and 6 are dedicated to constructing the full flows for both BPS and non-BPS single-centered black holes with generic charges. We find that they are generated by the action of different classes of nilpotent elements in the coset algebra. Both types of flows are shown to reach the correct attractor values at the horizon. In Section 7, the procedure is generalized straightforwardly to construct both BPS and non-BPS multi-centered solutions. We use a metric ansatz with a flat spatial slice and we are able to recover the BPS bound states described by Bates and Denef. Using the same ansatz, we are able to build non-BPS multi-centered solutions. Unfortunately, solutions generated this way turn out to always have charges at each center which are mutually local. The last section reviews our conclusions and suggests possibilities for future work.

# 2 Framework

Here we outline the method we will use to construct black hole solutions. This method was first described in [22]. We first reduce a general gravity action from four dimensions down to three,and derive the equation of motion. We then specialize to certain theories which have a 3d description in terms of a symmetric coset space. In such situations, we can easily find solutions to the equation of motion. The solutions are geodesics (or generalizations thereof) on the 3d moduli space and they are generated by elements of the coset algebra.

# 2.1 3D Moduli Space

We will study stationary solutions in a theory with gravity coupled to scalar and vector matter. Let the scalars be $z ^ { i }$ and the vectors be $A ^ { I }$ . Then the most general ansatz for a stationary solution in four dimensions is:

$$
\begin{array} { r c l } { { d s ^ { 2 } } } & { { = } } & { { - e ^ { 2 U } ( d t + \omega ) ^ { 2 } + e ^ { - 2 U } { \bf g } _ { a b } d x ^ { a } d x ^ { b } } } \\ { { F ^ { I } } } & { { = } } & { { d A ^ { I } = d \left( A _ { 0 } ^ { I } ( d t + \omega ) + { \bf A } ^ { I } \right) } } \end{array}
$$

where $a , b = 1 , 2 , 3$ label the spatial directions and bold font denotes three-dimensional fields and operators. Since none of the fields are time-dependent， we can compactify on the time isometry and reduce to three-dimensional space $\displaystyle { \mathcal { M } } _ { 3 D }$ . This procedure is called the $c ^ { * }$ -map. In three dimensions, a vector is Hodge-dual to a scalar. The equations of motion for $\omega$ and the gauge fields allow us to define the dual scalars $\phi _ { \omega }$ and $\phi _ { \mathbf { A } ^ { I } }$ ：

We then obtain the 3d lagrangian in terms of only scalars

$$
{ \mathcal { L } } = { \frac { 1 } { 2 } } { \sqrt { \mathbf { g } } } ( - { \frac { 1 } { \kappa } } \mathbf { R } + \partial _ { a } \phi ^ { m } \partial ^ { a } \phi ^ { n } g _ { m n } )
$$

where $\phi ^ { n }$ are the moduli fields

$$
{ \phi } ^ { n } = \{ U , z ^ { i } , { \bar { z } } ^ { \bar { i } } , \phi _ { \omega } , A _ { 0 } ^ { I } , \phi _ { { \bf A } ^ { I } } \}
$$

and $\mathbf { g } _ { a b }$ is the space time metric and $g _ { m n }$ is the metric of a manifold $\mathcal { M } _ { 3 D }$ . The system is （20 $3 D$ gravity minimally coupled to a nonlinear sigma model with moduli space $\mathcal { M } _ { 3 D }$ .Next, we will find the equation of motion in this theory.

# 2.2 Attractor Flow Equation

The equation of motion of $3 D$ gravity is Einstein's equation:

$$
\mathbf { R } _ { a b } - \frac { 1 } { 2 } \mathbf { g } _ { a b } \mathbf { R } = \kappa T _ { a b } = \kappa ( \partial _ { a } \phi ^ { m } \partial _ { b } \phi ^ { n } g _ { m n } - \frac { 1 } { 2 } \mathbf { g } _ { a b } \partial _ { c } \phi ^ { m } \partial ^ { c } \phi ^ { n } g _ { m n } )
$$

and the equation of motion of the moduli is:

$$
\nabla _ { a } \nabla ^ { a } \phi ^ { n } + \Gamma _ { m p } ^ { n } \partial _ { a } \phi ^ { m } \partial ^ { a } \phi ^ { p } = 0
$$

For simplicity, we consider only the case where the $3 D$ spatial slice is flat (it is guaranteed to be fat only for extremal single-centered black holes). Then the dynamics of the moduli are decoupled from that of the $3 D$ gravity:

$$
\mathbf { \lambda } _ { \mathbf { \lambda } \mathbf { \lambda } \mathbf { \lambda } \mathbf { \lambda } } = 0 \qquad \implies \qquad \partial _ { a } \phi ^ { m } \partial _ { b } \phi ^ { n } g _ { m n } = 0
$$

In the multi-centered case, we need to solve the ful equations for the moduli as functions of the 3d coordinates $\vec { x }$ . For single-centered solutions, the moduli only depend on $r$ ; to satisfy the above equations, the motion of the moduli must follow null geodesics inside $\mathcal { M } _ { 3 D }$

A generic null geodesic flows to the boundary of the moduli space $\mathcal { M } _ { 3 D }$ .A singlecentered attractor flow is defined as a null geodesic that terminates at a point on the $U $ （20 $- \infty$ boundary and in the interior region with respect to all other coordinates. This is guaranteed for the BPS attractor by the constraints imposed by the supersymmetry. To find the single-centered non-supersymmetric attractor flow, one needs to find a way to construct null geodesics and a constraint that pick out the ones that stop at this specific component of the boundary. In the next section, we willshow that we can do this for models with special properties,and the method can be easily generalized to find the multi-centered attractor solution.

# 2.3 Models with Symmetric Moduli Space

The problem of finding such a constraint in a generic model is not easy. To simplify, we study any model whose moduli space is a symmetric homogeneous space: $\mathcal { M } _ { 3 D } = \mathbf { G } / \mathbf { H }$ .When （204号 $\mathcal { M } _ { 3 D }$ is a homogeneous space, the isometry group $\mathbf { G }$ acts transitively on $\mathcal { M } _ { 3 D }$ ： $\mathbf { H }$ denotes the isotropy group，which is the maximal compact subgroup of $\mathbf { G }$ when one compactifies on a spatial isometry down to $( 1 , 2 )$ space，or the analytical continuation of the maximal compact subgroup of $\mathbf { G }$ when one compactifies on the time isometry down to $( 0 , 3 )$ space. The Lie algebra $\mathbf { g }$ has the Cartan decomposition: $\mathbf { g } = \mathbf { h } \oplus \mathbf { k }$ where

$$
[ \mathbf { h } , \mathbf { h } ] = \mathbf { h } \qquad [ \mathbf { h } , \mathbf { k } ] = \mathbf { k }
$$

When $\mathbf { G }$ is semi-simple, the homogeneous space is symmetric,and

$$
[ \mathbf { k } , \mathbf { k } ] = \mathbf { h }
$$

The models with symmetric moduli space includes: $\boldsymbol { D }$ -dimensional gravity toroidally compactified to four dimensions, certain models of 4D ${ \mathcal N } = 2$ supergravity coupled to vectormultiplet, and all 4D $\mathcal { N } > 2$ extended supergravity. The entropy of the last two classes is U-duality invariant. In the present paper, we will only consider the first two classes, namely, the $D$ -dimensional gravity toroidally compactified to four dimensions,and the 4D $\mathcal { N } = 2$ supergravity coupled to $n _ { V }$ vector-multiplet.

The left-invariant current is

$$
J = M ^ { - 1 } d M = J _ { \mathbf { k } } + J _ { \mathbf { h } }
$$

where $M$ is the coset representative, and $J _ { \mathbf { k } }$ is the projection of $J$ onto the coset algebra $\mathbf { k }$ 1 The lagrangian density of the sigma-model with target space $\mathbf { G } / \mathbf { H }$ is given by $J _ { \mathbf { k } }$ as:

$$
{ \cal L } = \mathrm { T r } ( J _ { \bf k } \wedge * _ { 3 } J _ { \bf k } )
$$

The geodesic of the homogeneous space written in terms of the coset representative is simply

$$
M = M _ { 0 } e ^ { k \tau / 2 } \qquad \mathrm { w i t h } \qquad k \in { \bf k }
$$

where $M _ { 0 }$ parameterizes the initial point,and the $\textstyle { \frac { 1 } { 2 } }$ is for later convenience. A null geodesic has zero length:

$$
| \boldsymbol k | ^ { 2 } = 0
$$

Therefore, in a homogeneous space, we can find the null geodesics that end at an attractor point by imposing the appropriate constraint on the null elements of the coset algebra.

Since $M$ is defined up to the action of the isotropy group $\mathbf { H }$ , in order to read off the moduli fields from $M$ in an $\mathbf { H }$ -independent way, we construct the symmetric matrix using the metric signature matrix $S _ { 0 }$ ：

$$
\boldsymbol { S } \equiv \boldsymbol { M } \boldsymbol { S } _ { 0 } \boldsymbol { M } ^ { T }
$$

In all systems considered in the present paper, $\mathbf { H }$ is the maximal orthogonal subgroup of $\mathbf { G }$ with the correct signature:

$$
H S _ { 0 } H ^ { T } = S _ { 0 } \qquad \mathrm { f o r ~ } \forall H \in { \bf H }
$$

That is, the isotropy group $\mathbf { H }$ preserves the symmetric metric matrix $S _ { 0 }$ . Therefore, $S$ is invariant under $M  M H$ with $H \in \mathbf { H }$ . Moreover, as the isotropy group $\mathbf { H }$ acts transitively on the space of of matrices with a given signature, the space of possible $S$ is the same as the

symmetric space $\mathbf { G } / \mathbf { H }$ . That is, the moduli of $\mathbf { G } / \mathbf { H }$ can be combined into the symmetric matrix $S$ . And the current of $S$ is

$$
J _ { S } = S ^ { - 1 } d S
$$

It is easy to perform the projection onto the coset algebra $\mathbf { k }$ . The（generalized） orthogonality condition of the isotropy group $\mathbf { H }$ can be expressed in terms of the subalgebra element （204号 $h$ which is in $H = e ^ { h }$ as

$$
h S _ { 0 } + S _ { 0 } h ^ { T } = 0 \qquad \forall h \in { \bf h }
$$

In other words, $( \mathbf { h } S _ { 0 } )$ is anti-symmetric: $( { \bf h } S _ { 0 } ) ^ { T } = - ( { \bf h } S _ { 0 } )$ . Thus the coset algebra, being the compliment of $\mathbf { h }$ , can be defined as the $\mathbf { k }$ with $( \mathbf { k } S _ { 0 } )$ being symmetric: $( { \bf k } S _ { 0 } ) ^ { T } = ( { \bf k } S _ { 0 } )$ ， i.e.

$$
k ^ { T } = S _ { 0 } ^ { - 1 } k S _ { 0 } \qquad \forall k \in { \bf k }
$$

Therefore, the projection of an element $g$ in $\mathbf { g }$ onto the coset algebra $\mathbf { k }$ is:

$$
g _ { \bf k } = \frac { g + S _ { 0 } g ^ { T } S _ { 0 } ^ { - 1 } } { 2 }
$$

For the left-invariant current $J = { M ^ { - 1 } d M }$ ， the projection onto $\mathbf { k }$ is:

$$
J _ { \mathbf { k } } = \frac { J + S _ { 0 } J ^ { T } S _ { 0 } ^ { - 1 } } { 2 }
$$

It is straightforward to show that the current constructed from $S$ is related to the projected left-invariant current $J _ { \mathbf { k } }$ by:

$$
J _ { S } = S ^ { - 1 } d S = 2 ( S _ { 0 } M ^ { T } ) ^ { - 1 } J _ { \bf k } ( S _ { 0 } M ^ { T } )
$$

The lagrangian in terms of $S$ is thus $\begin{array} { r } { L = \frac { 1 } { 4 } \mathrm { T r } \big ( J _ { S } \wedge * _ { 3 } J _ { S } \big ) } \end{array}$ . That is, the lagrangian density is

$$
\mathcal { L } = \frac { 1 } { 4 } \mathrm { { T r } } ( S ^ { - 1 } \nabla S \cdot S ^ { - 1 } \nabla S )
$$

which is invariant under the action of the isometry group $\mathbf { G }$

$$
S \to G ^ { - 1 } S G \qquad { \mathrm { w h e r e } } \qquad G \in \mathbf { G }
$$

and whose conserved current is:

$$
J = { S } ^ { - 1 } \nabla S
$$

where we have dropped the subscript $S$ in $J _ { S }$ ， since we will only be dealing with this current from now on. The equation of motion is the conservation of the current:

$$
\nabla \cdot J = \nabla \cdot ( S ^ { - 1 } \nabla S ) = 0
$$

We now specialize to the single-centered solutions: they correspond to geodesics in the coset manifold. The spherical symmetry allows the $3 d$ metric to be parameterized as

$$
d s _ { 3 } ^ { 2 } = C ( r ) ^ { 2 } d \vec { x } ^ { 2 }
$$

Then the equations of motion involve the operator $d _ { r } r ^ { 2 } C ( r ) d _ { r }$ ， and reduce to geodesic equations in terms of a parameter $\tau$ such that

$$
\frac { d r } { d \tau } = r ^ { 2 } C ( r ) .
$$

The function $C ( \boldsymbol r )$ is then determined from the equations of motion of $3 d$ gravity. The equations of motion can be written as

$$
\frac { d } { d \tau } ( S ^ { - 1 } \frac { d S } { d \tau } ) = 0
$$

In the extremal limit the geodesics become null, the $3 d$ metric is flat and

$$
\tau = - { \frac { 1 } { r } }
$$

In the search for multi-centered extremal solutions, where the spherical symmetry is absent,it is very convenient to restrict to solutions with a flat 3d metric.This is consistent with the equations of motion as long as the $3 d$ energy momentum tensor is zero everywhere:

$$
T _ { a b } = T r ( J _ { a } J _ { b } ) = 0
$$

The coupled problem with generic non-flat $3 d$ metric is much harder,and exact solutions are hard to find unless a second Killing vector is present.

Since different values of the scalars at infinity are easily obtained by a $\mathbf { G }$ transformation, to start with,we will consider the flow starting from $M _ { 0 } = 1$ ， and generalize to generic asymptotic moduli later. For a single-centered solution, the flow of $M$ is $M = M _ { 0 } e ^ { k \tau / 2 }$ Since all the coset representatives can be brought into the form $e ^ { g }$ with some $g \in \mathbf { k }$ by an $\mathbf { H }$ -action, we can write $M _ { 0 } = e ^ { g / 2 }$ ，s0 $M = e ^ { g / 2 } e ^ { k \tau / 2 }$ . And the flow of $S$ is

$$
S ( \tau ) = e ^ { g / 2 } e ^ { k \tau } e ^ { g / 2 } S _ { 0 }
$$

The charges of the solution are read from the conserved currents

$$
\boldsymbol { J } ( \boldsymbol { r } ) = S ^ { - 1 } \nabla S = \frac { S _ { 0 } e ^ { - g / 2 } k e ^ { g / 2 } S _ { 0 } } { r ^ { 2 } } \hat { \vec { r } }
$$

# 3Torus Reduction of $D$ -dimensional Pure Gravity

Now we use the method introduced in the previous section to analyze pure gravity toroidally compactified down to four dimensions. We explain why the attractor flow generator, $k$ ， needs to be nilpotent,and we find the Jordan forms of $k ^ { 2 }$ and $k$ . Using this information, we construct single-centered attractor flows. We then generalize to multicentered black holes in pure gravity and show that these solutions have mutually local charges and no intrinsic angular momentum.

# 3.1 Kaluza-Klein Reduction

The simplest example of a system that admits a $3 d$ description in terms of a sigma model on a symmetric space is pure gravity in $\boldsymbol { D }$ dimensions,compactified on a $D - 4$ torus. The KK reduction to $4 D$ parameterizes the metric as

$$
d s _ { D } ^ { 2 } = \rho _ { p q } ( d y ^ { p } + A _ { \mu } ^ { p } d x ^ { \mu } ) ( d y ^ { q } + A _ { \nu } ^ { q } d x ^ { \nu } ) + \frac { 1 } { \sqrt { \operatorname * { d e t } \rho } } d s _ { 4 } ^ { 2 } ~ 1 \leq p , q \leq D - 4
$$

Here $y ^ { p }$ are the torus coordinates, $x ^ { \mu }$ the coordinates on $R ^ { 3 , 1 }$ ,and $\rho _ { p q }$ the metric of the torus. A $4 D$ metric with one timelike Killing spinor is then parameterized as

$$
d s _ { 4 } ^ { 2 } = - u ( d t + \omega _ { i } d x ^ { i } ) ^ { 2 } + \frac { 1 } { u } d s _ { 3 } ^ { 2 }
$$

where $u \ : = \ : e ^ { 2 U }$ , to connect with the parametrization in the later part of the paper; and （204号 $i = 1 , 2 , 3$ denote the $3 d$ space coordinates.

The two expressions combine as

$$
d s _ { D } ^ { 2 } = G _ { a b } ( d y ^ { a } + \tilde { \omega } _ { i } ^ { a } d x ^ { i } ) ( d y ^ { b } + \tilde { \omega } _ { j } ^ { b } d x ^ { j } ) + \frac { 1 } { - \operatorname * { d e t } G } d s _ { 3 } ^ { 2 } ~ 0 \leq a , b \leq D - 4
$$

Here $y ^ { a }$ are the torus coordinates plus time, $x ^ { i }$ coordinates on $R ^ { 3 }$ and

$$
G = \left( \begin{array} { c c } { { \rho _ { p q } } } & { { \rho _ { p r } A _ { 0 } ^ { r } } } \\ { { A _ { 0 } ^ { r } \rho _ { r q } } } & { { A _ { 0 } ^ { r } \rho _ { r s } A _ { 0 } ^ { s } - \frac { u } { \sqrt { \operatorname* { d e t } \rho } } } } \end{array} \right)
$$

and $\tilde { \omega } ^ { a } = ( \tilde { \omega } ^ { p } , \tilde { \omega } ^ { 0 } )$ is:

$$
\tilde { \omega } ^ { p } = ( A _ { i } ^ { p } - A _ { 0 } ^ { p } \omega _ { i } ) d x ^ { i } \qquad \tilde { \omega } ^ { 0 } = \omega
$$

If the forms $\widetilde { \omega } ^ { a }$ are dualized to scalars $\alpha _ { a }$ as

$$
d \alpha _ { a } = - \operatorname * { d e t } G G _ { a b } * _ { 3 } d { \tilde { \omega } } ^ { b }
$$

:he various scalars can be combined into a symmetric unimodular $( D - 2 ) \times ( D - 2 )$ matrix

$$
S = \left( \begin{array} { c c } { { G _ { a b } + \frac { 1 } { \operatorname* { d e t } G } \alpha _ { a } \alpha _ { b } } } & { { \frac { 1 } { \operatorname* { d e t } G } \alpha _ { a } } } \\ { { \frac { 1 } { \operatorname* { d e t } G } \alpha _ { b } } } & { { \frac { 1 } { \operatorname* { d e t } G } } } \end{array} \right)
$$

In terms of the $4 D$ fields that is

$$
S = \left( \begin{array} { c c c } { { \rho _ { p q } - \frac { 1 } { u \sqrt { \operatorname* { d e t } \rho } } \alpha _ { p } \alpha _ { q } } } & { { \rho _ { p r } A _ { 0 } ^ { r } - \frac { 1 } { u \sqrt { \operatorname* { d e t } \rho } } \alpha _ { p } \alpha _ { 0 } } } & { { - \frac { 1 } { u \sqrt { \operatorname* { d e t } \rho } } \alpha _ { p } } } \\ { { A _ { 0 } ^ { r } \rho _ { r q } - \frac { 1 } { u \sqrt { \operatorname* { d e t } \rho } } \alpha _ { 0 } \alpha _ { q } } } & { { A _ { 0 } ^ { r } \rho _ { r s } A _ { 0 } ^ { s } - \frac { u } { \sqrt { \operatorname* { d e t } \rho } } - \frac { 1 } { u \sqrt { \operatorname* { d e t } \rho } } \alpha _ { 0 } \alpha _ { 0 } } } & { { - \frac { 1 } { u \sqrt { \operatorname* { d e t } \rho } } \alpha _ { 0 } } } \\ { { - \frac { 1 } { u \sqrt { \operatorname* { d e t } \rho } } \alpha _ { q } } } & { { - \frac { 1 } { u \sqrt { \operatorname* { d e t } \rho } } \alpha _ { 0 } } } & { { - \frac { 1 } { u \sqrt { \operatorname* { d e t } \rho } } } } \end{array} \right)
$$

The equations of motion derive from the lagrangian density $\begin{array} { r } { \pmb { \mathcal { L } } = T r \nabla S S ^ { - 1 } \nabla S S ^ { - 1 } } \end{array}$ ,invariant under $S  U ^ { T } S U$ for any $U$ in $S L ( D - 2 )$ . As this $S L ( D - 2 )$ action is transitive on the space of matrices with a given signature, the space of possible $S$ is the same as the symmetric space $S L ( D - 2 ) / S O ( D - 4 , 2 )$ . Notice that the signature of the stabilizer （204号 $S O ( D - 4 , 2 )$ is appropriate for the reduction from $( D - 1 , 1 )$ to $( 3 , 0 )$ signature. The usual reduction from $( D - 1 , 1 )$ to $( 2 , 1 )$ would give a $S L ( D - 2 ) / S O ( D - 2 )$ , while the Euclidean reduction from $( D , 0 )$ to $( 3 , 0 )$ gives $S L ( D - 2 ) / S O ( D - 3 , 1 )$ [27].

The coset representative under the left $S O ( D - 4 , 2 )$ action can be described in terms of a set of vielbeins

$$
e ^ { A } = E _ { a } ^ { A } ( d y ^ { a } + \omega _ { i } ^ { a } d x ^ { i } ) \qquad e ^ { I } = { \frac { 1 } { \operatorname* { d e t } M } } e _ { ( 3 ) } ^ { I }
$$

as

$$
M = \left( \begin{array} { c c } { { E _ { a } ^ { A } } } & { { 0 } } \\ { { \frac { 1 } { \operatorname* { d e t } E } \alpha _ { b } } } & { { \frac { 1 } { \operatorname* { d e t } E } } } \end{array} \right)
$$

Then the symmetric $S O ( D - 4 , 2 )$ invariant matrix

$$
\boldsymbol { S } = M \boldsymbol { S } _ { 0 } \boldsymbol { M } ^ { T }
$$

can be used to read off the solution more easily. Without loss of generality, we can take $S _ { 0 }$ to be the signature matrix:

$$
S _ { 0 } = D i a g ( \eta , - 1 ) = D i a g ( 1 , \cdot \cdot \cdot , 1 , - 1 , - 1 )
$$

The equations of motion are equivalent to the conservation of the $S L ( D - 2 )$ currents （204号 $J = { S } ^ { - 1 } d { S }$ . Some of those currents correspond to the usual gauge currents in 4D: the first （204号 $D - 4$ elements of the last column $J _ { i , D - 2 }$ are the KK monopole currents, the first $D - 4$ elements of the row before the last $J _ { D - 3 , i }$ are the KK momentum currents and the element （204号 $J _ { D - 3 , D - 4 }$ is the current for the $3 d$ gauge field $\omega$ . Regular $4 D$ solutions must have zero sources for this current, otherwise $\omega$ will not be single valued.

# 3.2 Nilpotency

We now show that all the attractor flows are generated by the nilpotent generators in the coset algebra. To get extremal black hole solutions with a near horizon $A d S _ { 2 } \times S ^ { 2 }$ ，the function $u$ must scale as $r ^ { 2 }$ as $r$ goes to zero while the scalars go to a constant. This makes $S$ （204号 diverge as $\textstyle { \frac { 1 } { r ^ { 2 } } }$ . The most natural way for $S$ to diverge as $\tau ^ { 2 }$ for large $\tau$ is that $k$ is nilpotent, with

$$
\begin{array} { r } { k ^ { 3 } = 0 . } \end{array}
$$

This will be the crucial condition through the whole paper.

# 3.3A Toy Example: Hyperkähler Euclidean Metrics in Four Dimensions

Not every null geodesic corresponds to extremal black hole solutions. Let's consider a simple example: hyperkähler euclidean metrics in $4 D$

Although this example is not about a black hole, it is still quite instructive. The $3 d$ sigma model is $S L ( 2 ) / S O ( 1 , 1 )$ ,i.e. $A d S _ { 2 }$ . The coset representative is written as

$$
M = \left( \begin{array} { c c } { { u ^ { 1 / 2 } } } & { { 0 } } \\ { { \frac { a } { u ^ { 1 / 2 } } } } & { { \frac { 1 } { u ^ { 1 / 2 } } } } \end{array} \right)
$$

and the symmetric invariant

$$
S = \left( \begin{array} { c c } { { u - \frac { a ^ { 2 } } { u } } } & { { - \frac { a } { u } } } \\ { { - \frac { a } { u } } } & { { - \frac { 1 } { u } } } \end{array} \right)
$$

A geodesic is the exponential of a Lie algebra element in the orthogonal to the stabilizer. The stabilizer $S O ( 1 , 1 )$ is generated by $\sigma ^ { 1 }$ . A null geodesic is hence the exponential of （204号 $k = \sigma ^ { 3 } \pm i \sigma ^ { 2 }$ . This is a nilpotent matrix, $k ^ { 2 } = 0$ , hence $M = 1 + \tau k / 2$ . Take:

$$
k = \sigma ^ { 3 } + i \sigma ^ { 2 } = \left( \begin{array} { c c } { { 1 } } & { { 1 } } \\ { { - 1 } } & { { - 1 } } \end{array} \right)
$$

then

$$
M = \left( \begin{array} { c c } { { 1 + \tau / 2 } } & { { \tau / 2 } } \\ { { - \tau / 2 } } & { { 1 - \tau / 2 } } \end{array} \right)
$$

and we can read off the geodesic solution from the invariant

$$
S = M ^ { T } \left( \begin{array} { c c } { { 1 } } & { { 0 } } \\ { { 0 } } & { { - 1 } } \end{array} \right) M = \left( \begin{array} { c c } { { 1 + \tau } } & { { \tau } } \\ { { \tau } } & { { - 1 + \tau } } \end{array} \right)
$$

Hence

$$
u = \frac { 1 } { 1 - \tau } , \qquad a = - \frac { \tau } { 1 - \tau } .
$$

Dualizing $a$ ， we get

$$
\ast d \omega = - \frac { d a } { u ^ { 2 } } = \frac { 1 } { r ^ { 2 } } d r \qquad u ^ { - 1 } = 1 + \frac { 1 } { r }
$$

The 4D Euclidean metric is just the Taub-NUT metric. Notice that the multi-centered Taub-NUT generalization of the metric is obtained by replacing $\tau$ above with some harmonic function $\textstyle \sum _ { i } { \frac { q ^ { i } } { | x - x _ { i } | } }$ Thesigmamodelquatiosofmotionareequivalenttothecoseation of the current $J = { S } ^ { - 1 } \nabla S$ ，and if $S$ is given as above with $\tau = \tau ( \vec { x } )$ then the equation of motion are

$$
\nabla ^ { 2 } \tau ( \vec { x } ) = 0
$$

# 3.4 Single-centered Black Holes in Pure Gravity

# 3.4.1 Constructing the flow generator $k$

Now we look in detail at the single-centered black holes in pure gravity. Notice that as $u$ （20 goes to zero $S$ tends asymptotically to a rank one matrix

$$
S = - { \frac { 1 } { u { \sqrt { \operatorname* { d e t } \rho } } } } \left( { \begin{array} { c c c } { \alpha _ { p } \alpha _ { q } } & { \alpha _ { p } \alpha _ { 0 } } & { \alpha _ { p } } \\ { \alpha _ { 0 } \alpha _ { q } } & { \alpha _ { 0 } \alpha _ { 0 } } & { \alpha _ { 0 } } \\ { \alpha _ { q } } & { \alpha _ { 0 } } & { 1 } \end{array} } \right)
$$

hence the matrix $k ^ { 2 }$ should also have rank 1. By inspection of $S$ it is clear that a $k ^ { 2 }$ of rank higher than one gives a geodesic for which the matrix elements of $\rho$ also diverge as $\tau ^ { 2 }$ so that the scalar fields do not converge to fixed attractor values.

Notice that if $k$ is nilpotent,then $S$ is a polynomial in $\textstyle { \frac { 1 } { r } }$ ， and the various scalars in the solution will all be simple functions of $r$ for such extremal solutions!

The explicit form for $k$ in terms of the charges is then straightforward to write. Consider the Jordan form of $k ^ { 2 }$ : as it is nilpotent, the eigenvalues are all zero. As it is rank one, it has one single indecomposable block of size two: $\left( \begin{array} { l l } { 0 } & { 1 } \\ { 0 } & { 0 } \end{array} \right)$ It is written as

$$
k ^ { 2 } = - \eta v v ^ { T } f ( P , Q )
$$

with $v$ null in the metric $\eta$ ，and $f ( P , Q )$ any degree-two homogeneous function of the charge $( P , Q )$ . This form is chosen so that $\boldsymbol { v }$ does not scale with the charge $( P , Q )$

Then $k$ must have a Jordan form with all eigenvalues zero, one block of size 3: $\left( \begin{array} { l l l } { 0 } & { 1 } & { 0 } \\ { 0 } & { 0 } & { 1 } \\ { 0 } & { 0 } & { 0 } \end{array} \right)$ and possibly some other extra blocks of size two. Alternatively, there is a subspace $V$ annihilated by $k$ ， a subspace $V ^ { \prime }$ whose image under $k$ sits in $V$ and has the same dimension as （204 $V ^ { \prime }$ , and a single vector $w$ such that $k w \in V ^ { \prime }$ and is non-zero.

$$
k w \subset V ^ { \prime } , \qquad k V ^ { \prime } \subset V , \qquad k V = 0 .
$$

From the symmetry of $\eta K$ ， it follows that the space $k V ^ { \prime }$ is made of null vectors only, and that $k w$ is orthogonal to it. Because $\eta k ^ { 2 } = - v v ^ { T }$ ， $( k w ) ^ { T } \eta k w$ is negative. Because of the signature of $\eta$ it is straightforward to see that $V ^ { \prime }$ can be of dimension at most one; hence there are no blocks of size 2 in the Jordan form of $k$ ：

Taking this into account, the final form of $k$ is simply

$$
{ k } = \eta w v ^ { T } + \eta v w ^ { T }
$$

where $v$ and $w$ are two orthogonal $( D - 2 )$ -dimensional vectors with $v$ being null and $w$ having norm $- f ( P , Q )$

$$
w \eta v = 0 , \qquad v \eta v = 0 , \qquad w \eta w = - f ( P , Q ) .
$$

Using the fact that in $k$ ,the first $D - 4$ elements of the last column $K _ { i , D - 2 }$ are the magnetic charges,and the first $D \mathrm { ~ - ~ } 4$ elements of the row before the last $K _ { D - 3 , i }$ are the electric charges,and the element $K _ { D - 3 , D - 4 }$ is the Taub-NUT charge,which has to vanish,we have （204号 $2 ( D - 4 ) + 1 = 2 D - 7$ conditions. Together with the three constraints coming from the norms and orthogonality condition (3.26), they can be used to solve for the $2 D - 4$ degrees of freedom in $( v , w )$ ：

The full solution of $( v , w )$ requires one to solve some degree-four equations,hence we'll leave it in a slightly implicit form. Let $( p , q )$ be two $( D - 4 )$ -dimensional vectors proportional to the magnetic and electric charges, so that the magnetic charge and the electric charge $( P , Q )$ of the $4 D$ gauge fields are

$$
P = \sqrt { p ^ { 2 } + p \cdot q } p \qquad Q = \sqrt { q ^ { 2 } + p \cdot q } q
$$

And we choose $f ( P , Q )$ to be

$$
f ( P , Q ) = p \cdot q
$$

The solution of $v$ and $w$ written in terms of $( p , q )$ is

$$
v = \frac { 1 } { \sqrt { p \cdot q } } \left( \begin{array} { c } { { q + p } } \\ { { - \sqrt { q ^ { 2 } + p \cdot q } } } \\ { { - \sqrt { p ^ { 2 } + p \cdot q } } } \end{array} \right) , w = \frac { \sqrt { p \cdot q } } { 2 } \left( \begin{array} { c } { { q - p } } \\ { { - \sqrt { q ^ { 2 } + p \cdot q } } } \\ { { \sqrt { p ^ { 2 } + p \cdot q } } } \end{array} \right) .
$$

and $k$ can be written as

$$
k = \left( \begin{array} { c c c } { { q q ^ { T } - p p ^ { T } } } & { { - \sqrt { q ^ { 2 } + p \cdot q } q } } & { { \sqrt { p ^ { 2 } + p \cdot q } p } } \\ { { \sqrt { q ^ { 2 } + p \cdot q } q ^ { T } } } & { { - ( q ^ { 2 } + p \cdot q ) } } & { { 0 } } \\ { { - \sqrt { p ^ { 2 } + p \cdot q } p ^ { T } } } & { { 0 } } & { { p ^ { 2 } + p \cdot q } } \end{array} \right)
$$

# 3.4.2 Full flow

First, for the full flow starting from $M _ { 0 } = 1$ , the scalars for the attractor solution generated by this $k$ can be read off from $S ( \tau ) = e ^ { k \tau }$ , by comparing with the form of $S$ in terms of the 4D fields:

$$
u ^ { - 2 } = [ 1 + ( p ^ { 2 } + p \cdot q ) ( \tau + \frac { p \cdot q } { 2 } \tau ^ { 2 } ) ] [ 1 + ( q ^ { 2 } + p \cdot q ) ( \tau + \frac { p \cdot q } { 2 } \tau ^ { 2 } ) ]
$$

and

$$
\rho = 1 + { \frac { ( q q ^ { T } - p p ^ { T } ) \tau + [ ( p ^ { 2 } + p \cdot q ) q q ^ { T } - { \frac { p \cdot q } { 2 } } ( p + q ) ( p + q ) ^ { T } ] \tau ^ { 2 } } { 1 + ( p ^ { 2 } + p \cdot q ) ( \tau + { \frac { p \cdot q } { 2 } } \tau ^ { 2 } ) } }
$$

Notice that as $\tau \longrightarrow \infty$ ， $\tau ^ { - 2 } e ^ { - 2 U }$ has the correct limit $\textstyle { \frac { P \cdot Q } { 2 } }$ , which is the entropy where $P$ and $Q$ are the physical electric and magnetic charges.

To generalize to arbitrary asymptotic moduli, $\begin{array} { r } { M ( \tau ) = e ^ { g / 2 } e ^ { k \tau / 2 } } \end{array}$ ， and the flow of $S$ is (2.31), which can be written as $S ( \tau ) = e ^ { K ( \tau ) } S _ { 0 }$ ，where $K ( \tau )$ is a matrix function. From now on，we use lower case $k$ to denote the coset algebra that generates the attractor flow, and capital $K$ to denote the function which we exponentiate directly to produce the solution.

We will choose $K ( \tau )$ to have the same properties as the generator $k$

$$
K ^ { 3 } ( \tau ) = 0 \qquad \mathrm { a n d } \qquad K ^ { 2 } ( \tau ) \ \mathrm { r a n k \ o n e }
$$

The equations of motion $\nabla \cdot ( S ^ { - 1 } \nabla S ) = 0$ then simplify considerably with this ansatz. If one further requires that the subspace image of $K ^ { 2 } ( \tau )$ remains constant everywhere, such that

$$
K ^ { 2 } ( \tau ) \nabla K ( \tau ) = \nabla K ( \tau ) K ^ { 2 } ( \tau ) = 0
$$

then the current reduces to

$$
J = { S } ^ { - 1 } \nabla { S } = { S } _ { 0 } \left( \nabla K ( \tau ) + \frac { 1 } { 2 } [ \nabla K ( \tau ) , K ( \tau ) ] \right) { S } _ { 0 }
$$

and the equations of motion are

$$
\nabla ^ { 2 } K ( \tau ) + \frac { 1 } { 2 } [ \nabla ^ { 2 } K ( \tau ) , K ( \tau ) ] = 0
$$

which is solved by a harmonic $K ( \tau )$

It might appear hard to find a $K ( \tau )$ that is harmonic and satisfies all the required constraints. However， by remembering that the constraints dictate $K ( \tau )$ to have the form:

$$
\boldsymbol { K } ( \tau ) = \eta \boldsymbol { V } \boldsymbol { W } ^ { T } + \eta \boldsymbol { W } \boldsymbol { V } ^ { T }
$$

with $V$ being null and doesn't scale with the charge $( P , Q )$ ，and $W$ orthogonal to $V$ everywhere, one can simply pick a constant null vector $V = v ^ { \prime }$ and a harmonic vector $W ( \tau )$ everywhere orthogonal to $v ^ { \prime }$ ：

$$
W ( \tau ) = w ^ { \prime } \tau + m \qquad \mathrm { w i t h } \qquad v ^ { \prime } \cdot W ( \tau ) = 0
$$

Here $m$ isa $( D - 2 )$ -vector and contains the information of asymptotic moduli. Thus an appropriate $K ( \tau )$ is built:

$$
K ( \tau ) = k ^ { \prime } \tau + g
$$

where

$$
k ^ { \prime } = \eta v ^ { \prime } w ^ { \prime T } + \eta w ^ { \prime } v ^ { \prime T } ~ g = \eta v ^ { \prime } m ^ { T } + \eta m v ^ { \prime T }
$$

Now we need to solve for $( \boldsymbol { v } ^ { \prime } , \boldsymbol { w } ^ { \prime } )$ for the same charge $( P , Q )$ but in the presence of $m$ The form of $g$ guaranteed that

$$
[ k ^ { \prime } , g ] = 0
$$

where we have used the fact that $v ^ { \prime }$ is null and $w ^ { \prime }$ is orthogonal to $v ^ { \prime }$ . Therefore,shifting the starting point of moduli does not change the current as a function of $( v , w )$ ：

$$
J ( v ^ { \prime } , w ^ { \prime } ) = S _ { 0 } \left( \frac { k ^ { \prime } } { r ^ { 2 } } \right) S _ { 0 } = S _ { 0 } \left( \frac { \eta v ^ { \prime } ( w ^ { \prime } ) ^ { T } + \eta w ^ { \prime } ( v ^ { \prime } ) ^ { T } } { r ^ { 2 } } \hat { \vec { r } } \right) S _ { 0 }
$$

Thus, the solution of $( \boldsymbol { v } ^ { \prime } , \boldsymbol { w } ^ { \prime } )$ in terms of charges solved from the current does not change as we vary the starting point of the flow, i.e. they do not depend on the asymptotic moduli:

$$
v ^ { \prime } ( Q ) = v ( Q ) \qquad w ^ { \prime } ( Q ) = w ( Q )
$$

In summary, the flow with arbitrary starting point is simply generated by

$$
K ( \tau ) = \eta v W ( \tau ) ^ { T } + \eta W ( \tau ) v ^ { T } \qquad \mathrm { w i t h } \qquad W = w \tau + m
$$

where $( v , w )$ only depend on the charges $( P , Q )$ and $m$ gives the asymptotic moduli.

# 3.4.3 Example: 5D pure gravity compactified on a circle.

Consider for example the case of extremal black holes in $D = 5$ pure gravity compactifed on a circle. The $3 d$ sigma model is $S L ( 3 ) / S O ( 1 , 2 )$ . The symmetric invariant is

$$
S _ { g r } = \left( \begin{array} { c c c } { \rho - \frac { 1 } { u \sqrt { \rho } } \alpha _ { 1 } \alpha _ { 1 } } & { \rho A _ { 0 } - \frac { 1 } { u \sqrt { \rho } } \alpha _ { 1 } \alpha _ { 0 } } & { - \frac { 1 } { u \sqrt { \rho } } \alpha _ { 1 } } \\ { \rho A _ { 0 } - \frac { 1 } { u \sqrt { \rho } } \alpha _ { 1 } \alpha _ { 0 } } & { \rho ( A _ { 0 } ) ^ { 2 } - \frac { u } { \sqrt { \rho } } - \frac { 1 } { u \sqrt { \rho } } \alpha _ { 0 } \alpha _ { 0 } } & { - \frac { 1 } { u \sqrt { \rho } } \alpha _ { 0 } } \\ { - \frac { 1 } { u \sqrt { \rho } } \alpha _ { 1 } } & { - \frac { 1 } { u \sqrt { \rho } } \alpha _ { 0 } } & { - \frac { 1 } { u \sqrt { \rho } } } \end{array} \right)
$$

Then we can calculate $S = S _ { 0 } e ^ { k \tau }$ using (3.30) and compare the result to $S _ { g r }$ above to solve for all the scalars. We find that

$$
\begin{array} { r c l } { { e ^ { - 2 U } } } & { { = } } & { { \displaystyle \sqrt { [ 1 + ( q ^ { 2 } + p q ) ( \tau + \frac { p q } { 2 } \tau ^ { 2 } ) ] [ 1 + ( p ^ { 2 } + p q ) ( \tau + \frac { p q } { 2 } \tau ^ { 2 } ) ] } } } \\ { { } } & { { } } & { { } } \\ { { \rho } } & { { = } } & { { \displaystyle \frac { 1 + ( q ^ { 2 } + p q ) ( \tau + \frac { p q } { 2 } \tau ^ { 2 } ) } { 1 + ( p ^ { 2 } + p q ) ( \tau + \frac { p q } { 2 } \tau ^ { 2 } ) } } } \end{array}
$$

when starting from the identity. If we allow arbitrary $g$ the flow is too complicated to write əxplicitly here, but the attractor value of $\rho$ is the same: $q / p$

# 3.5 Multi-centered Solutions in Pure Gravity

In the context of pure gravity compactified on a torus, we can also give some examples of multi-centered solutions in the same spirit as the ones for BPS solutions in $N = 2$ supergravity, though some important features of the latter are not present here.

We are interested in solutions given in terms of harmonic functions which can generalize the single-centered extremal solutions presented above. Similar to the single-centered case, we exponentiate a matrix function $K ( \vec { x } )$ ：

$$
S ( \vec { x } ) = e ^ { K ( \vec { x } ) } S _ { 0 }
$$

We will choose $K ( \vec { x } )$ to have the same properties of the generator $k$

$$
K ^ { 3 } ( \vec { x } ) = 0 \qquad \mathrm { a n d } \qquad K ^ { 2 } ( \vec { x } ) \mathrm { r a n k ~ o n e }
$$

Using a similar argument to the single-centered fow, we require that the subspace image of $K ^ { 2 } ( \vec { x } )$ remains constant everywhere, such that $K ^ { 2 } ( \vec { x } ) \nabla K ( \vec { x } ) = \nabla K ( \vec { x } ) K ^ { 2 } ( \vec { x } ) = 0$ ，then the equations of motion are

$$
\nabla ^ { 2 } K ( \vec { x } ) + \frac { 1 } { 2 } [ \nabla ^ { 2 } K ( \vec { x } ) , K ( \vec { x } ) ] = 0
$$

which is solved by a harmonic $K ( \vec { x } )$

A multi-centered $K ( \vec { x } )$ that is harmonic and satisfies all the required constraints can then be built in the same way as the single-centered one:

$$
K ( \vec { x } ) = \eta v W ( \vec { x } ) ^ { T } + \eta W ( \vec { x } ) v ^ { T }
$$

where $v$ is the same constant null vector as in $k$ ，and $W ( \vec { x } )$ is the multi-centered harmonic function:

$$
W ( \vec { x } ) = \sum _ { i } { \frac { w _ { i } } { | \vec { x } - \vec { x } _ { i } | } } + m
$$

where $\vec { x } _ { i }$ is the position of the $i$ th center,and $w _ { i }$ is determined by the charges at the $i$ th center,and $m$ is related to the moduli at infinity. Requiring $W ( \vec { x } )$ to be orthogonal to $v$ everywhere gives the following constraints on the $\{ w _ { i } , m \}$ : First, taking $\vec { x }$ to infinity,it gives

$$
v \cdot m = 0
$$

Second, $w _ { i }$ are orthogonal to $v$

$$
\boldsymbol { v } \cdot \boldsymbol { w } _ { i } = 0
$$

In addition to the constraint from the zero Taub-NUT charge condition $- b z - c y = 0$ ，this makes the space of each possible $w _ { i }$ only $( D - 4 )$ -dimensional. That is,though $W$ isa $( D - 2 )$ -vector, one has only $( D - 4 )$ independent harmonic functions to work with, because of the orthogonality to $v$ and the requirement of no timelike NUT charges. This makes the solution relatively boring.

The multi-centered solution in pure gravity does not have the characteristic features of the typical BPS multi-centered solution in $\mathcal { N } = 2$ supergravity, where many centers with relatively non-local charges form bound states which carry intrinsic angular momentum.

The basic reason is that when the ansatz $K ( \vec { x } ) = \eta v W ^ { T } ( \vec { x } ) + \eta W ( \vec { x } ) v ^ { T }$ is used，the second term of the conserved currents ${ \cal J } = S _ { 0 } ( \nabla K + { \textstyle { \frac { 1 } { 2 } } } [ \nabla K , K ] ) S _ { 0 }$ drops out. The first result is that the charges of the various centers in the solution can be read off directly from $( v , w _ { i } )$ ， and they do not depend on the positions, charges of the other centers. Thus, there is no constraint on the position of each center as in the ${ \mathcal N } = 2$ BPS multi-centered solution; centers can be moved around freely.

Moreover, the condition of no timelike Taub-NUT charge is a linear constraint on the charges at each center which results in a static $4 D$ solution,as $\ast d \omega = 0$ leads to $\omega = 0$ ： Therefore,no angular momentum is present.

# 4Attractor Flows in $G _ { 2 ( 2 ) } / ( S L ( 2 , \mathbb { R } ) \times S L ( 2 , \mathbb { R } ) )$

We now tackle a more complicated subject: $\mathcal { N } ~ = ~ 2$ supergravity coupled to one vector multiplet. First，we reduce the theory down to three dimensions and derive the metric for the resulting moduli space,which is the coset $G _ { 2 ( 2 ) } / ( S L ( 2 , \mathbb { R } ) \times S L ( 2 , \mathbb { R } ) )$ .2 We then discuss the Cartan and Iwasawa decompositions of the group $G _ { 2 ( 2 ) }$ , which we use to construct the coset algebra and translate the flow of coset representative into the flow of the moduli fields, respectively. We then specify the representation of $G _ { 2 ( 2 ) }$ we will be working with, and describe the form of attractor flow generators in this representation.

# 4.1 The moduli space $\mathcal { M } _ { 3 D }$

The $3 d$ moduli space for $\mathcal { N } = 2 , d = 4$ supergravity coupled to $n _ { V }$ vector multiplets is wellstudied, for example in [31, 32, 33]. Some of the main results are compiled in the Appendix. Here we briefly review the essential points.

The bosonic part of the action is:

$$
S = - \frac { 1 } { 1 6 \pi } \int d ^ { 4 } x \sqrt { g ^ { ( 4 ) } } \left[ R - 2 g _ { i \bar { \jmath } } d z ^ { i } \wedge * _ { 4 } d \bar { z } ^ { \bar { \jmath } } - F ^ { I } \wedge G _ { I } \right]
$$

where $I = 0 , 1 . . . n _ { V }$ ，and $G _ { I } = ( R e \mathcal { N } ) _ { I J } F ^ { J } + ( I m \mathcal { N } ) _ { I J } \ast F ^ { J }$ . For a model endowed with a prepotential $F ( X )$ ，

$$
\mathcal { N } _ { I J } = F _ { I J } + 2 i \frac { ( \mathrm { I m } F \cdot X ) _ { I } ( \mathrm { I m } F \cdot X ) _ { J } } { X \cdot \mathrm { I m } F \cdot X }
$$

where $F _ { I J } = \partial _ { I } \partial _ { J } F ( X )$ . We reduce to three dimensions, dualizing the vectors $( \omega , \mathbf { A } ^ { I } )$ to the scalars $( \sigma , B _ { I } )$ ,and renaming $A _ { 0 } ^ { I }$ as $A ^ { I }$ . The metric of $\mathcal { M } _ { 3 D } ^ { * }$ is then

$$
\begin{array} { r c l } { { } } & { { = } } & { { { \bf d } U \cdot { \bf d } U + \displaystyle \frac { 1 } { 4 } e ^ { - 4 U } ( { \bf d } \sigma + A ^ { I } { \bf d } B _ { I } - B _ { I } { \bf d } A ^ { I } ) \cdot ( { \bf d } \sigma + A ^ { I } { \bf d } B _ { I } - B _ { I } { \bf d } A ^ { I } ) + g _ { i \bar { \it { i } } } ( z , { \bf d } A ^ { I } ) } } \\ { { } } & { { } } & { { + \displaystyle \frac { 1 } { 2 } e ^ { - 2 U } [ ( I m \mathcal { N } ^ { - 1 } ) ^ { I J } ( { \bf d } B _ { I } + \mathcal { N } _ { I K } { \bf d } A ^ { K } ) \cdot ( { \bf d } B _ { J } + \overline { { { \mathcal { N } _ { J L } } } } { \bf d } A ^ { L } ) ] } } \end{array}
$$

It is a para-quaternionic-Kahler manifold. Since the holonomy is reduced from $S O ( 4 n _ { V } +$ 4)）to $S p ( 2 , \mathbb { R } ) \times S p ( 2 n _ { V } + 2 , \mathbb { R } )$ ，the vielbein has two indices $( \alpha , A )$ transforming under $S p ( 2 , \mathbb { R } )$ and $S p ( 2 n _ { V } + 2 , \mathbb { R } )$ ， respectively. The para-quaternionic vielbein is the analytical continuation of the quaternionic vielbein computed in [34]. The explicit form is given in the appendix.

For $n _ { V } = 1$ ， $X ^ { I } = ( X ^ { 0 } , X ^ { 1 } )$ . For our purpose, we choose the prepotential

$$
F ( X ) = - { \frac { ( X ^ { 1 } ) ^ { 3 } } { X ^ { 0 } } }
$$

The metric of $\mathcal { M } _ { 3 D } ^ { * }$ with one-modulus is (4.3) with $\begin{array} { r } { g _ { z \bar { z } } = \frac { 3 } { 4 y ^ { 2 } } } \end{array}$ and $\mathcal { N }$ and $( I m \mathcal { N } ) ^ { - 1 }$ being

$$
{ \cal N } = \left( \begin{array} { c c } { { - ( 2 x - i y ) ( x + i y ) ^ { 2 } } } & { { 3 x ( x + i y ) } } \\ { { 3 x ( x + i y ) } } & { { - 3 ( 2 x + i y ) } } \end{array} \right) \qquad I m { \cal N } ^ { - 1 } = - \frac { 1 } { y ^ { 3 } } \left( \begin{array} { c c } { { 1 } } & { { x } } \\ { { x } } & { { 3 x ^ { 2 } + y ^ { 2 } } } \end{array} \right)
$$

The isometries of the $\mathcal { M } _ { 3 D } ^ { * }$ descend from the symmetries of the 4D system. The gauge symmetries in 4D give shifting isometries of $\mathcal { M } _ { 3 D } ^ { * }$ ， whose associated conserved charges are:

$$
l \tau = J _ { A ^ { I } } = P _ { A ^ { I } } - B _ { I } P _ { \sigma } , \qquad p ^ { I } d \tau = J _ { B _ { I } } = P _ { B _ { I } } + A ^ { I } P _ { \sigma } , \qquad k d \tau = J _ { \sigma }
$$

where the momenta $\{ P _ { \sigma } , P _ { A ^ { I } } , P _ { B _ { I } } \}$ are

$$
\begin{array} { r c l } { { P _ { \sigma } } } & { { = } } & { { \displaystyle \frac { 1 } { 2 } e ^ { - 4 U } ( { \bf d } \sigma + A ^ { I } { \bf d } B _ { I } - B _ { I } { \bf d } A ^ { I } ) } } \\ { { P _ { A ^ { I } } } } & { { = } } & { { e ^ { - 2 U } [ ( I m \mathcal { N } ) _ { I J } { \bf d } A ^ { J } + ( R e \mathcal { N } ) _ { I J } ( I m \mathcal { N } ^ { - 1 } ) ^ { J K } ( { \bf d } B _ { K } + ( R e \mathcal { N } ) _ { K L } { \bf d } A ^ { L } ) ] - 2 ( R e \mathcal { N } ) _ { I J } ( { \bf d } B _ { I } + ( R e \mathcal { N } ) _ { I J } { \bf d } A ^ { I } ) ] ^ { 2 } , } } \\ { { P _ { B _ { I } } } } & { { = } } & { { e ^ { - 2 U } [ ( I m \mathcal { N } ^ { - 1 } ) ^ { I J } ( { \bf d } B _ { J } + ( R e \mathcal { N } ) _ { J K } { \bf d } A ^ { K } ) ] + A ^ { I } P _ { \sigma } } } \end{array}
$$

Here $\tau$ is the affine parameter defined as $d \tau \equiv - \ast _ { 3 } \sin \theta d \theta d \phi$ ： $( p ^ { 0 } , p ^ { 1 } , q _ { 1 } , q _ { 0 } )$ are the D6- D4-D2-D0 charges, and $k$ the Taub-NUT charge. A non-zero $k$ gives rise to closed time-like curves, so we will set $k = 0$ from now on.

Note that the time translational invariance in 4D gives rise to the conserved current

$$
J _ { U } = P _ { U } + 2 \sigma J _ { \sigma } + A ^ { I } J _ { A ^ { I } } + B ^ { I } J _ { B ^ { I } }
$$

where $P _ { U } = 2 d U$ . The corresponding conserved charge is the ADM mass: $2 M _ { A D M } d \tau = J _ { U }$

# 4.2 Extracting the Coordinates from the Coset Elements

The metric (4.3) for the case $n _ { V } = 1$ describes an eight-dimensional manifold with coordinates $\phi ^ { n } = \{ u , x , y , \sigma , A ^ { 0 } , A ^ { 1 } , B _ { 1 } , B _ { 0 } \}$ . This manifold is the coset space $G _ { 2 ( 2 ) } / ( S L ( 2 , \mathbb { R } ) \times$ $S L ( 2 , \mathbb { R } ) _ { . }$ ). The root diagram for the Cartan decomposition of $G _ { 2 ( 2 ) }$ is shown in Figure 1. The six roots that lie on the horizontal and vertical axes $\{ L _ { h } ^ { \pm } , L _ { h } ^ { 3 } , L _ { v } ^ { \pm } , L _ { v } ^ { 3 } \}$ are the six non-compact generators of the subgroup $\mathbf { H } = S L ( 2 , \mathbb { R } ) _ { h } \times S L ( 2 , \mathbb { R } ) _ { v }$ ：

$$
[ L _ { h / v } ^ { 3 } , L _ { h / v } ^ { \pm } ] = \mp L _ { h / v } ^ { \pm } , \qquad [ L _ { h / v } ^ { + } , L _ { h / v } ^ { - } ] = 2 L _ { h / v } ^ { 3 }
$$

and the two vertical columns of eight roots $\{ a _ { \alpha A } \}$ are the basis of the subspace $\mathbf { K }$ ： $\left\{ a _ { 1 A } , a _ { 2 A } \right\}$ for each $A$ is a spin- $1 / 2$ doublet under the horizontal $S L ( 2 , \mathbb { R } )$ ：

$$
\left( \begin{array} { c } { { a _ { 1 A } } } \\ { { a _ { 2 A } } } \end{array} \right) ] = \left( \begin{array} { c } { { - \frac 1 2 a _ { 1 A } } } \\ { { \frac 1 2 a _ { 2 A } } } \end{array} \right) \qquad \lbrack L _ { h } ^ { + } , \left( \begin{array} { c } { { a _ { 1 A } } } \\ { { a _ { 2 A } } } \end{array} \right) ] = \left( \begin{array} { c } { { 0 } } \\ { { a _ { 1 A } } } \end{array} \right) \qquad \lbrack L _ { h } ^ { - } , \left( \begin{array} { c } { { a _ { 1 A } } } \\ { { a _ { 2 A } } } \end{array} \right) ] = \left( \begin{array} { c } { { 0 } } \\ { { a _ { 1 A } } } \end{array} \right) \qquad \left[ L _ { h } ^ { - } , \left( \begin{array} { c } { { a _ { 1 A } } } \\ { { a _ { 2 A } } } \end{array} \right) \right] = \left( \begin{array} { c } { { 0 } } \\ { { a _ { 1 A } } } \end{array} \right) \qquad \left[ L _ { h } ^ { - } , \left( \begin{array} { c } { { a _ { 1 A } } } \\ { { a _ { 2 A } } } \end{array} \right) \right] = \left( \begin{array} { c } { { 0 } } \\ { { a _ { 1 A } } } \end{array} \right) \qquad \left[ L _ { h } ^ { - } , \left( \begin{array} { c } { { a _ { 1 A } } } \\ { { a _ { 2 A } } } \end{array} \right) \right] = 0
$$

And $\{ a _ { \alpha 1 } , a _ { \alpha 2 } , a _ { \alpha 3 } , a _ { \alpha 4 } \}$ for each $\alpha$ span a spin- $3 / 2$ representation of the vertical $S L ( 2 , \mathbb { R } )$

$$
\begin{array}{c} \begin{array} { r } { \iota _ { \alpha _ { 2 } } ^ { \iota _ { \alpha 1 } } } \\ { \iota _ { \alpha 3 } } \\ { \iota _ { \alpha 4 } ^ { \iota _ { \alpha 2 } } } \end{array} ) \boldsymbol { \mathrm { I } } = ( \begin{array} { c } { - \frac { 3 } { 2 } a _ { \alpha 1 } } \\ { - \frac { 1 } { 2 } a _ { \alpha 2 } } \\ { \frac { 1 } { 2 } a _ { \alpha 3 } } \\ { \frac { 3 } { 2 } a _ { \alpha 4 } } \end{array} ) \qquad [ L _ { v } ^ { + } , ( \begin{array} { c } { a _ { \alpha 1 } } \\ { a _ { \alpha 2 } } \\ { a _ { \alpha 3 } } \\ { a _ { \alpha 4 } } \end{array} ) ] = ( \begin{array} { c } { 0 } \\ { 3 a _ { \alpha 1 } } \\ { 2 a _ { \alpha 2 } } \\ { a _ { \alpha 3 } } \end{array} ) \qquad [ L _ { v } ^ { - } , ( \begin{array} { c } { a _ { \alpha 1 } } \\ { a _ { \alpha 2 } } \\ { a _ { \alpha 3 } } \\ { a _ { \alpha 4 } } \end{array} ) ] = ( \begin{array} { c } { a _ { \alpha 1 } } \\ { a _ { \alpha 3 } } \\ { a _ { \alpha 4 } } \end{array} ) \qquad ( \begin{array} { c } { a _ { \alpha 1 } } \\ { a _ { \alpha 2 } } \\ { a _ { \alpha 3 } } \\ { a _ { \alpha 4 } } \end{array} ) ( \begin{array} { c } { a _ { \alpha 1 } } \\ { a _ { \alpha 3 } } \\ { a _ { \alpha 4 } } \end{array} )  \end{array}
$$

All the commutators can be easily read off from the Root diagram (1)，we will only write down the following ones which will be useful later.

$$
[ a _ { 1 1 } , a _ { 1 4 } ] = - \frac { 1 } { 3 } [ a _ { 1 2 } , a _ { 1 3 } ] = - 4 L _ { h } ^ { + } \qquad [ a _ { 2 1 } , a _ { 2 4 } ] = - \frac { 1 } { 3 } [ a _ { 2 2 } , a _ { 2 3 } ] = - 4 L _ { h } ^ { - }
$$

![](images/23ee646f20b47d4f38f5544bdc03df1a709245b0eb7c0ea316653642227f2024.jpg)  
Figure 1: Root Diagram of Cartan Decomposition of $G _ { 2 ( 2 ) }$

Being semisimple, the algebra of $G _ { 2 ( 2 ) }$ has the Iwasawa decomposition $\mathbf { g } = \mathbf { h } \oplus \mathbf { a } \oplus \mathbf { n }$ , where a is the maximal abelian subspace of $\mathbf { k }$ ，and $\mathbf { n }$ is the nilpotent subspace of the positive root space $\Sigma ^ { + }$ of $\mathbf { a }$ . In Figure 2,we show the Iwasawa decomposition of $G _ { 2 ( 2 ) }$ . The two Cartan generators in $\mathbf { a }$ are $\{ \mathbf { u } , \mathbf { y } \}$ ，and $\{ { \bf x } , \pmb { \sigma } , { \bf A } ^ { 0 } , { \bf A } ^ { 1 } , { \bf B } _ { 1 } , { \bf B } _ { 0 } \}$ span a nilpotent subspace $\mathbf { n }$ ： $n ^ { 7 } = 0$ for $n \in { \mathbf { n } }$ . a and $\mathbf { n }$ together generate the solvable subgroup $S o l v$ of $\mathbf { G }$ ，which act transitively on ${ \mathcal { M } } _ { 3 D } = G _ { 2 ( 2 ) } / S L ( 2 , \mathbb { R } ) \times S L ( 2 , \mathbb { R } )$ . In particular, $\mathbf { y }$ generates the rescaling of $y$ ，and $\{ { \bf u } , { \bf x } , { \pmb \sigma } , { \bf A } ^ { 0 } , { \bf A } ^ { 1 } , { \bf B } _ { 1 } , { \bf B } _ { 0 } \}$ generates the translation of $\{ U , x , \sigma , A ^ { 0 } , A ^ { 1 } , B _ { 1 } , B _ { 0 } \}$ . The moduli space $\mathcal { M } _ { 3 D }$ can be parameterized by the solvable elements:

$$
\Sigma ( \phi ) = e ^ { U { \bf u } + ( \ln y ) { \bf y } } e ^ { x { \bf x } + A ^ { I } { \bf A } ^ { I } + B _ { I } { \bf B _ { I } } + \sigma \sigma }
$$

The origin of the moduli space

$$
a = A ^ { 0 } = A ^ { 1 } = B _ { 1 } = B _ { 0 } = 0 \qquad x = 0 \qquad y = u = 1
$$

correspond to $\Sigma ( \phi ) = 1$

In Fig 2, the isometries are plotted according to their eigenvalues under the two Cartan

![](images/3fd49051002ecf4244af1b6836f6354f7fe113a3e0a4ab7c6d511eeb55873d84.jpg)  
Figure 2:Root Diagram of Isometry of $\begin{array} { r l r } { M _ { 3 D } } & { { } = } & { G _ { 2 ( 2 ) } / ( S L ( 2 , \mathbb { R } ) \ \times \ S L ( 2 , \mathbb { R } ) ) . } \end{array}$ （ $\{ { \bf u } , { \bf y } , { \bf x } , \sigma , { \bf A } ^ { 0 } , { \bf A } ^ { 1 } , { \bf B } _ { 1 } , { \bf B } _ { 0 } \}$ generates the solvable subgroup.

generators $\mathbf { u }$ and $\mathbf { y }$ [31]. $\{ \mathbf { u } , \mathbf { y } \}$ are related to $a _ { \alpha A }$ by3:

$$
\mathbf { u } = - \frac { 1 } { 8 } [ ( a _ { 1 1 } + a _ { 2 4 } ) - ( a _ { 1 3 } + a _ { 2 2 } ) ] \qquad \mathbf { y } = \frac { 1 } { 8 } [ 3 ( a _ { 1 1 } + a _ { 2 4 } ) + ( a _ { 1 3 } + a _ { 2 2 } ) ]
$$

The three generators $\{ \pmb { \sigma } , \mathbf { u } , \hat { \pmb { \sigma } } \}$ on the horizontal axis and $\{ \mathbf { x } , \mathbf { y } , { \hat { \mathbf { x } } } \}$ on the vertical axis form the horizontal and vertical $S L ( 2 , \mathbb { R } )$ , respectively. The vertical $S L ( 2 , \mathbb { R } )$ generate the duality invariance. Denote the two vertical columns of eight isometries as

$$
\left( \begin{array} { c c } { { \pmb \xi } _ { 2 1 } } & { { \pmb \xi } _ { 1 1 } } \\ { { \pmb \xi } _ { 2 2 } } & { { \pmb \xi } _ { 1 2 } } \\ { { \pmb \xi } _ { 2 3 } } & { { \pmb \xi } _ { 1 3 } } \\ { { \pmb \xi } _ { 2 4 } } & { { \pmb \xi } _ { 1 4 } } \end{array} \right) \equiv \left( \begin{array} { c c } { { - \hat { \bf A } ^ { 0 } } } & { { { \bf B } _ { 0 } } } \\ { { - 3 \hat { \bf A } ^ { 1 } } } & { { 3 { \bf B } _ { 1 } } } \\ { { \hat { \bf B } _ { 1 } } } & { { - \bf A } ^ { 1 } } \\ { { - \hat { \bf B } _ { 0 } } } & { { { \bf A } ^ { 0 } } } \end{array} \right)
$$

$\big \{ \pmb { \xi } _ { 1 A } , \pmb { \xi } _ { 2 A } \big \}$ for each $A$ span a spin- $1 / 2$ representation of the horizontal $S L ( 2 , \mathbb { R } )$ ,and $\{ \pmb { \xi } _ { \alpha 1 } , \pmb { \xi } _ { \alpha 2 } , \pmb { \xi } _ { \alpha 3 } , \pmb { \xi } _ { \alpha 4 } \}$ for each $\alpha$ span a spin- $3 / 2$ representation of the vertical $S L ( 2 , \mathbb { R } )$

$$
{ \mathbf u } = D i a g [ 0 , \frac { 1 } { 2 } , - \frac { 1 } { 2 } , 0 , - \frac { 1 } { 2 } , \frac { 1 } { 2 } , 0 ] \qquad { \mathbf y } = D i a g [ 1 , - \frac { 1 } { 2 } , - \frac { 1 } { 2 } , - 1 , \frac { 1 } { 2 } , \frac { 1 } { 2 } , 0 ]
$$

Parameterizing the coset representative $M$ as the solvable elements, the symmetric matrix $S$ can be written in terms of the eight coordinates $\phi ^ { n }$ , from the solvable elements $\Sigma$ （204号

$$
S ( \phi ) = \Sigma ( \phi ) S _ { 0 } \Sigma ( \phi ) ^ { T }
$$

The coordinates are read off from the symmetric matrix $S$

# 4.3 Nilpotency of the Attractor Flow Generator $k$ ：

The near-horizon geometry of the $4 D$ attractor is $A d S _ { 2 } \times S ^ { 2 }$ ,i.e

$$
e ^ { - U } \to \sqrt { V _ { B H } } | _ { * } \tau \qquad \mathrm { a s } \qquad \tau \to \infty
$$

In terms of the variable $u \equiv e ^ { 2 U }$ （20

$$
u \to { \frac { 1 } { { \cal V } _ { B H } } } \tau ^ { - 2 } \qquad \mathrm { a s } \qquad \tau \to \infty
$$

The solvable element is

$$
M = e ^ { U \mathbf { u } + \ldots } \sim u ^ { \frac { 1 } { 2 } \mathbf { u } }
$$

As the flow goes to the near-horizon, $u \longrightarrow 0$

$$
M ( \tau ) \sim u ^ { - \ell / 2 } \sim \tau ^ { \ell }
$$

where $- \ell$ is the lowest eigenvalue of $\mathbf { u }$ . That is, $M ( \tau )$ is a polynomial function of $\tau$

On the other hand, since the geodesic flow is generated by $k$ via

$$
M ( \tau ) = M ( 0 ) e ^ { k \tau / 2 }
$$

i.e., $M ( \tau )$ is an exponential function of $\tau$ . To reconcile the two statements, $k$ must be nilpotent:

$$
\boldsymbol { k } ^ { \ell + 1 } = 0
$$

That is, the element in $\mathbf { k }$ that generates the attractor flow is nilpotent. Moreover, by looking at the weights of the fundamental representation of $G _ { 2 }$ ， we see that $\ell = 2$ （20

$$
k _ { * } ^ { 3 } = 0
$$

Moreover, the nilpotency of the attractor flow generators guarantees that it is null:

$$
k ^ { 3 } = 0 \qquad \Longrightarrow \qquad ( k ^ { 2 } ) ^ { 2 } = 0 \Longrightarrow T r ( k ^ { 2 } ) = 0
$$

which means that $k$ is null.

# 4.4Properties of Attractor Flow

The scalar moduli space is parameterized by a symmetric $7 \times 7$ matrix $S$ which sits in $G _ { 2 ( 2 ) }$ ， i.e. preserves a non-degenerate three form $w _ { i j k }$ such that $\eta _ { i s } = w _ { i j k } w _ { s t u } w _ { m n o } \epsilon ^ { j k t u m n o }$ ejktumno is a metric with signature $( 4 , 3 )$ normalized so that $\eta ^ { 2 } = 1$ . To facilitate the comparison with the pure $5 D$ gravity case we decompose 7 as $3 \oplus 3 + 1$ of $S L ( 3 )$ and pick as non-zero components of $w$ the $3 \wedge 3 \wedge 3$ ， $3 \wedge 3 \wedge 3$ and $3 \otimes 3 \otimes 1$ as

$$
w = d x _ { 1 } \wedge d x _ { 2 } \wedge d x _ { 3 } + d y ^ { 1 } \wedge d y ^ { 2 } \wedge d y ^ { 3 } - \frac { 1 } { \sqrt { 2 } } d x _ { a } \wedge d y ^ { a } \wedge d z
$$

The resulting expression for $\eta$ is

$$
\eta = d x _ { a } d y ^ { a } - d z ^ { 2 }
$$

We know that $k$ must be an element of $G _ { 2 ( 2 ) }$ ， hence also of $S O ( 4 , 3 )$ . As in the pure gravity case, we choose the representation such that

$$
S _ { 0 } k S _ { 0 } = k ^ { T } S _ { 0 } k ^ { 2 } S _ { 0 } = ( k ^ { 2 } ) ^ { T }
$$

In this base a $G _ { 2 ( 2 ) }$ Lie algebra element is given as

$$
k = \left( \begin{array} { c c c } { { A _ { i 1 } ^ { j 1 } } } & { { \epsilon _ { i 1 j 2 k } v ^ { k } } } & { { \sqrt { 2 } w _ { i 1 } } } \\ { { \epsilon ^ { i 2 j 1 k } w _ { k } } } & { { - A _ { j 2 } ^ { i 2 } } } & { { - \sqrt { 2 } v ^ { i 2 } } } \\ { { - \sqrt { 2 } v ^ { j 1 } } } & { { \sqrt { 2 } w _ { j 2 } } } & { { 0 } } \end{array} \right)
$$

Here $A$ is a traceless $3 \times 3$ matrix. $S$ is a symmetric element in $G _ { 2 ( 2 ) }$ with signature $\{ 1 , - 1 , - 1 , 1 , - 1 , - 1 , 1 \}$ ,i.e. $S = M S _ { 0 } M ^ { T }$ with

$$
S _ { 0 } = \left( \begin{array} { c c c } { { \eta _ { 1 } } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { \eta _ { 1 } } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { 1 } } \end{array} \right) = D i a g ( 1 , - 1 , - 1 , 1 , - 1 , - 1 , 1 )
$$

where $\eta _ { 1 }$ is the one for pure gravity

If the gauge field is turned off, then $S$ is block diagonal

$$
S | _ { F = 0 } = \left( \begin{array} { c c c } { { S _ { g r } } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { S _ { g r } ^ { - 1 } } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { 1 } } \end{array} \right)
$$

where $S _ { g r }$ is the same as the one for pure $5 D$ gravity. Turning on a non-zero $5 D$ vector field corresponds to a more general $S$ ：

$$
S = e ^ { k _ { 1 } ^ { T } } ( S | _ { F = 0 } ) e ^ { k _ { 1 } }
$$

with $k _ { 1 }$ a $G _ { 2 ( 2 ) }$ Lie algebra matrix with $w _ { 1 }$ equal to the fifth component of the gauge field, （204 $v ^ { 2 }$ equal to the time component of the gauge field and $w _ { 3 }$ equal to the scalar dual to the three-dimensional part of the gauge field.

In this representation, $( x , y )$ can be extracted from symmetric matrix $S$ via:

$$
x ( \tau ) = - \frac { S _ { 3 5 } ( \tau ) } { S _ { 3 3 } ( \tau ) } \qquad y ^ { 2 } = \frac { S _ { 3 3 } ( \tau ) S _ { 5 5 } ( \tau ) - S _ { 3 5 } ( \tau ) ^ { 2 } } { S _ { 3 3 } ( \tau ) ^ { 2 } }
$$

And $u$ via:

$$
u = \frac { 1 } { \sqrt { S _ { 3 3 } ( \tau ) S _ { 5 5 } ( \tau ) - S _ { 3 5 } ( \tau ) ^ { 2 } } }
$$

The $4 D$ gauge currents sit in $J = { { S } ^ { - 1 } } \nabla S$ ，where ${ \cal J } _ { 1 2 } ( J _ { 3 1 } )$ is again the electric(magnetic) current for the $K K$ photon, $J _ { 3 2 }$ the timelike NUT current, and ${ \cal J } _ { 7 2 } ( J _ { 5 1 } )$ the electric(magnetic) current for the reduction of the $5 D$ gauge field.

$$
J _ { 3 2 } = - 2 J _ { \sigma } \qquad J _ { 1 2 } = \sqrt { 2 } J _ { A ^ { 0 } } \qquad J _ { 7 2 } = \frac { 2 } { 3 } J _ { A ^ { 1 } } \qquad J _ { 5 1 } = - \sqrt { 2 } J _ { B _ { 1 } } \qquad J _ { 3 1 } = \sqrt { 2 } J _ { B _ { 2 } } \qquad 
$$

Moreover,

$$
J _ { 2 2 } - J _ { 3 3 } = 2 J _ { U }
$$

We use $\mathbf { Q }$ to denote the charge matrix, where it relates to the D-brane charge $\{ p ^ { 0 } , p ^ { 1 } , q _ { 1 } , q _ { 0 } \}$ and the vanishing NUT charge $k$ by

$$
( { \bf Q } _ { 3 1 } , { \bf Q } _ { 5 1 } , { \bf Q } _ { 7 2 } , { \bf Q } _ { 1 2 } ) = ( \sqrt { 2 } p ^ { 0 } , - \sqrt { 2 } p ^ { 1 } , \frac { 2 } { 3 } q _ { 1 } , \sqrt { 2 } q _ { 0 } ) \qquad { \bf Q } _ { 3 2 } = - 2 k = 0
$$

Since $k$ is nilpotent: $k ^ { 3 } = 0$ 2

$$
S = e ^ { k \tau } S _ { 0 } = ( 1 + k \tau + \frac { 1 } { 2 } k ^ { 2 } \tau ^ { 2 } ) S _ { 0 }
$$

The $A d S _ { 2 } \times S ^ { 2 }$ near-horizon geometry of the $4 D$ attractor dictates $\begin{array} { r } { u = \frac { 1 } { V _ { B H } | _ { * } } \tau ^ { - 2 } } \end{array}$ as $\tau \longrightarrow \infty$ Therefore, the flow generator $k$ can be obtained by

$$
k ^ { 2 } = 2 V _ { B H } | _ { * } ( u S | _ { u  0 } ) S _ { 0 }
$$

Computing $k ^ { 2 }$ using $S$ constructed from the solvable elements $\Sigma ( \phi )$ shows that $k ^ { 2 }$ is of rank two,its Jordan form has two blocks of size 3. It can be written as

$$
k ^ { 2 } = \sum _ { a , b = 1 , 2 } v _ { a } v _ { b } ^ { T } c _ { a b } S _ { 0 }
$$

with $v _ { a }$ null and orthogonal to each other: $v _ { a } \cdot v _ { b } \equiv v _ { a } ^ { T } S _ { 0 } v _ { b } = 0$ ，and $c _ { a b }$ depends on the particular choice of $k$ . Thus $k$ can be expressed as:

$$
k = \sum _ { a = 1 , 2 } ( v _ { a } w _ { a } ^ { T } + w _ { a } v _ { a } ^ { T } ) S _ { 0 }
$$

where each $w _ { a }$ is orthogonal to both $\boldsymbol { v } _ { a }$ ： $\boldsymbol { w } _ { a } \cdot \boldsymbol { v } _ { b } = 0$ ，and $w _ { a }$ satisfy

$$
\boldsymbol { w } _ { a } \cdot \boldsymbol { w } _ { b } = c _ { a b }
$$

Paralel to the pure gravity case, the single-centered attractor flow is constructed as $S ( \tau ) = e ^ { K ( \tau ) } S _ { 0 }$ ， where we choose $K ( \tau )$ to have the same properties as the generator $k$

$$
K ^ { 3 } ( \tau ) = 0 \qquad \mathrm { a n d } \qquad K ^ { 2 } ( \tau ) \ \mathrm { r a n k \ t w o }
$$

This determines $K ( \tau ) = k \tau + g$ where

$$
k = \sum _ { a = 1 , 2 } [ v _ { a } w _ { a } ^ { T } + w _ { a } v _ { a } ^ { T } ] S _ { 0 } \qquad \mathrm { a n d } \qquad g = \sum _ { a = 1 , 2 } [ v _ { a } m _ { a } ^ { T } + m _ { a } v _ { a } ^ { T } ] S _ { 0 }
$$

where the two 7-vectors $m _ { a }$ 's are orthogonal to $v _ { a }$ and contain the information of asymptotic moduli. Using $[ [ k , g ] , g ] = 0$ , the current is reduced to

$$
J = \frac { S _ { 0 } ( k + \frac { 1 } { 2 } [ k , g ] ) S _ { 0 } } { r ^ { 2 } } \hat { \vec { r } }
$$

from which we obtain $\boldsymbol { v } _ { a }$ and $w _ { a }$ in terms of the charges and the asymptotic moduli.

# 5 Flow Generators in the $G _ { 2 ( 2 ) } / ( S L ( 2 , \mathbb { R } ) { \times } S L ( 2 , \mathbb { R } ) )$ Model

We now explicitly construct the generators of single-centered attractor flows. We start with the BPS flow which is associated with a specific combination of the coset algebra generators $a _ { \alpha A }$ .It can be derived from the condition of preservation of supersymmetry. We then construct the non-BPS attractor flow generator in analogy with the BPS one. In Section 5.2, we write $k _ { B P S }$ and $k _ { n o n B P S }$ in terms of the $v _ { a }$ and $w _ { a }$ vectors. This form willbe especially helpful in generalizing to the multi-centered case.

# 5.1 Construction of Flow Generators

# 5.1.1 Constructing $k _ { B P S }$ using supersymmetry

To describe BPS trajectories it is useful to remember that the stabilizer of $S$ in $G _ { 2 ( 2 ) }$ is （204号 $S O ( 1 , 2 ) \times S O ( 1 , 2 )$ ， corresponding to the elements of $G _ { 2 ( 2 ) }$ which are antisymmetric after multiplication by $S _ { 0 }$ . Geodesics are exponentials of elements that are symmetric after multiplication by $S _ { 0 }$ . Such elements sit in a $( 2 , 4 )$ representation of $S O ( 1 , 2 ) \times S O ( 1 , 2 )$ . A BPS trajectory is highest weight for the first $S O ( 1 , 2 )$ . Labelling the symmetric generators as $a _ { \alpha A }$ under the two $S O ( 1 , 2 )$ groups, a BPS trajectory is generated by

$$
k _ { B P S } = a _ { \alpha A } C ^ { A } z ^ { \alpha } \ .
$$

The twistor $z$ and the coefficients $C ^ { A }$ are fixed in terms of the charges of the extremal BPS black hole and the condition of zero time-like NUT charge.

To see why this is true,expand the coset element $k _ { B P S }$ that generates the BPS attractor flow using $a _ { \alpha A }$ ：

$$
k _ { B P S } = a _ { \alpha A } C ^ { \alpha A }
$$

where $C ^ { \alpha A }$ are conserved along the flow. On the other hand, the conserved currents in the homogeneous space are constructed by projecting the one-form valued Lie algebra $g ^ { - 1 } \cdot d g$ （204号 onto $\mathbf { k }$ ，which gives the vielbein in the symmetric space:

$$
g ^ { - 1 } d g | _ { \bf k } = a _ { \alpha A } V ^ { \alpha A }
$$

where $V ^ { \alpha A }$ is conserved:

$$
\frac { d } { d \tau } \left( V _ { a } ^ { \alpha A } \dot { \phi } ^ { a } \right) = 0
$$

Therefore, the expansion coefficients of $k _ { B P S }$ are

$$
C ^ { \alpha A } = V _ { a } ^ { \alpha A } \dot { \phi } ^ { a }
$$

In terms of the vielbein，the supersymmetry condition that gives the BPS geodesics are written as [33]:

$$
V ^ { \alpha A } z _ { \alpha } = 0
$$

That is:

$$
V _ { a } ^ { \alpha A } \dot { \phi } ^ { a } z _ { \alpha } = 0 \qquad \Longrightarrow \qquad C ^ { \alpha A } z _ { \alpha } = 0
$$

Define $z ^ { \alpha } = \epsilon ^ { \alpha \beta } z _ { \beta }$

$$
C ^ { \alpha A } = C ^ { A } z ^ { \alpha }
$$

Therefore, the coset element $k _ { B P S }$ is expanded by the coset algebra basis $a _ { \alpha A }$ as $k _ { B P S } =$ aaACAza.

Note that $k _ { B P S }$ has five parameters $( C ^ { A } , z )$ where $A = 1 , \dotsc , 4$ . As will be shown later, （204号 $z$ can actually be determined by $( C ^ { A } )$ and moduli at infinity. So the geodesic generated by $k _ { B P S }$ is indeed a four-parameter family. It is easy to show that $k _ { B P S }$ is null, but more importantly, it is nilpotent:

$$
k _ { B P S } ^ { 3 } = 0
$$

As will be shown later, $k _ { B P S }$ indeed gives the correct BPS attractor flow.

# 5.1.2 Constructing $k _ { N o n B P S }$

To construct the non-BPS attractor flow,one needs to find an element in the coset algebra distinct from $k _ { B P S }$ that satisfies:

$$
k _ { N o n B P S } ^ { 3 } = 0
$$

The hint again comes from the BPS generator. Note that $k _ { B P S } = a _ { \alpha A } P ^ { A } z ^ { \alpha }$ can be written as:

$$
k _ { B P S } = e ^ { - z L _ { h } ^ { - } } k _ { B P S } ^ { 0 } e ^ { z L _ { h } ^ { - } }
$$

where $k _ { B P S } ^ { 0 }$ spans only the right four coset generators $a ^ { 1 A }$

$$
k _ { B P S } ^ { 0 } = a _ { 1 A } C ^ { A }
$$

That is, $k _ { B P S }$ is generated by starting with the element spanning the four generators annihilated by the horizontal $S L ( 2 )$ raising operator $L _ { h } ^ { + }$ ， then conjugating with the horizontal $S L ( 2 )$ lowering operator $L _ { h } ^ { - }$ .And it is very easy to show that $( k _ { B P S } ^ { 0 } ) ^ { 3 } = 0$ which proves （204号 $( k _ { B P S } ) ^ { 3 } = 0$ ：

In $G _ { 2 ( 2 ) } / S L ( 2 , \mathbb { R } ) ^ { 2 }$ , there are two third-degree nilpotent generators in total. And since there are only two $S L ( 2 , \mathbb { R } )$ 's inside $\mathbf { H }$ ,a natural guess for a non-BPS solution is to look at vectors with fixed properties under the second $S L ( 2 , \mathbb { R } )$ group. An interesting condition is to have positive charge under some rotation of $L _ { v } ^ { 3 }$ ,i.e. an $S L ( 2 , \mathbb { R } )$ rotation of $\textstyle \sum _ { A = 1 , 2 } a _ { \alpha A } C ^ { \alpha A }$ ： Therefore, this suggests to us to start with the element spanning the four generators annihilated by the square of the vertical $S L ( 2 , \mathbb { R } )$ raising operator $( L _ { v } ^ { + } ) ^ { 2 }$ and then conjugate with the vertical $S L ( 2 , \mathbb { R } )$ lowering operator $L _ { v } ^ { - }$ ：：

$$
k _ { N o n B P S } ( z ) = e ^ { - z L _ { v } ^ { - } } k _ { N o n B P S } ^ { 0 } e ^ { z L _ { v } ^ { - } }
$$

where

$$
k _ { N o n B P S } ^ { 0 } = a _ { \alpha a } C ^ { \alpha a } \qquad \mathrm { w h e r e } \qquad \alpha , a = 1 , 2 .
$$

And one can show that: $( k _ { N o n B P S } ^ { 0 } ) ^ { 3 } = 0$ which proves $( k _ { N o n B P S } ) ^ { 3 } = 0$ .Moreover, $( k _ { N o n B P S } ) ^ { 2 }$ is rank two.

As long as one can pick the coefficients $C ^ { \alpha A }$ and the twistor $z$ that describes the $S O ( 1 , 2 )$ （20 direction to be such that the time NUT charge is zero, this generator will give nice non-BPS extremal black holes. All the known non-BPS solutions may be recovered this way, and more,as this construction gives absolute freedom to pick the charges and moduli at infinity for the black hole (clearly for certain values of charges and moduli the solution will crash into a naked singularity, but this is to be expected from comparison with the BPS case)

# 5.2 Properties of Flow Generators

# 5.2.1 Properties of $k _ { B P S }$

We now turn to solving for $v _ { a }$ and $w _ { a }$ in (4.40) in terms of $C ^ { A }$ and $z$ .First， from (4.39) we know that the null space of $k ^ { 2 }$ is five-dimensional and the $v _ { a }$ span the two-dimensional complement of this null space. For $k _ { B P S } = a _ { \alpha A } C ^ { A } z ^ { \alpha }$ the null space of $( k _ { B P S } ) ^ { 2 }$ does not depend on $C ^ { A }$ . Therefore, the $v _ { a }$ depend only on the twistor $z = z ^ { 2 } / z ^ { 1 }$ ：

Recallthat we are using theasis where $k$ has the form (4.28).Frominspectionof $k _ { B P S } ^ { 2 }$ we find that $( v _ { 1 } , v _ { 2 } )$ can always be chosen to have the form:4

$$
v _ { 1 } = \left( V _ { 1 } , - \eta _ { 1 } V _ { 1 } , 0 \right) \qquad v _ { 2 } = \left( - V _ { 2 } , \eta _ { 1 } V _ { 2 } , \sqrt { 2 } \right)
$$

where $\eta _ { 1 }$ is a 3d metric of signature $( 1 , - 1 , - 1 )$ ,and $V _ { 1 } , V _ { 2 }$ are two three-vectors with

$$
V _ { 1 } \cdot V _ { 1 } = 0 \qquad V _ { 1 } \cdot V _ { 2 } = 0 \qquad V _ { 2 } \cdot V _ { 2 } = - 1
$$

Since any linear combination of $( v _ { 1 } , v _ { 2 } )$ forms a new set of $( v _ { 1 } , v _ { 2 } )$ , this means in particular that any $\boldsymbol { v } _ { 2 } + c \boldsymbol { v } _ { 1 }$ gives a new $v _ { 2 }$ . Looking at the forms of $( v _ { 1 } , v _ { 2 } )$ ， we see that $V _ { 2 }$ is defined up to a shifting of $V _ { 1 }$ as $V _ { 2 } = V _ { 2 } ^ { 0 } - c V _ { 1 }$ ：

An explicit computation shows that $V _ { 1 }$ and $V _ { 2 }$ are given by the twistor $z$ and $u$ as

$$
V _ { 1 } = \left( \begin{array} { c } { { ( z ^ { 1 } ) ^ { 2 } + ( z ^ { 2 } ) ^ { 2 } } } \\ { { ( z ^ { 1 } ) ^ { 2 } - ( z ^ { 2 } ) ^ { 2 } } } \\ { { 2 z ^ { 1 } z ^ { 2 } } } \end{array} \right) \qquad V _ { 2 } = { \frac { 1 } { z ^ { 1 } u ^ { 2 } - z ^ { 2 } u ^ { 1 } } } \left( \begin{array} { c } { { z ^ { 1 } u ^ { 1 } + z ^ { 2 } u ^ { 2 } } } \\ { { z ^ { 1 } u ^ { 1 } - z ^ { 2 } u ^ { 2 } } } \\ { { z ^ { 1 } u ^ { 2 } + z ^ { 2 } u ^ { 1 } } } \end{array} \right) .
$$

where the twistor $\textstyle u = { \frac { u ^ { 2 } } { u ^ { 1 } } }$ is related to $c$ by

$$
u = - \frac { 1 + 2 c z } { 1 - 2 c z } z
$$

The twistor representation 5 of $V _ { 1 }$ and $V _ { 2 }$ are

$$
V _ { 1 } ^ { \alpha \beta } = 2 z ^ { \alpha } z ^ { \beta } \qquad V _ { 2 } ^ { \alpha \beta } = z ^ { \alpha } u ^ { \beta } + z ^ { \beta } u ^ { \alpha }
$$

$$
( v _ { 1 } , v _ { 2 } ) \to ( v _ { 1 } , v _ { 2 } ) \left( \begin{array} { c c } { { R _ { 1 1 } } } & { { R _ { 1 2 } } } \\ { { R _ { 2 1 } } } & { { R _ { 2 2 } } } \end{array} \right) \qquad \mathrm { a n d } \qquad ( w _ { 1 } , w _ { 2 } ) \to ( w _ { 1 } , w _ { 2 } ) \left( \begin{array} { c c } { { R _ { 1 1 } } } & { { R _ { 1 2 } } } \\ { { R _ { 2 1 } } } & { { R _ { 2 2 } } } \end{array} \right)
$$

where we have used the rescaling freedom to set $z ^ { 1 } u ^ { 2 } - z ^ { 2 } u ^ { 1 }$ to be 1. Note that for the BPS case, the twistor $u$ is totally arbitrary.

Now we solve for $w _ { a }$ . The condition that $w _ { a }$ are orthogonal to $v _ { a }$ dictates that they have the form:

$$
w _ { 1 } = ( W _ { 1 } , \eta _ { 1 } W _ { 1 } , 0 ) \qquad w _ { 2 } = ( W _ { 2 } , \eta _ { 1 } W _ { 2 } , 0 )
$$

where $W _ { 1 }$ and $W _ { 2 }$ are linearly independent, and are related to the charges by ${ w _ { a } } \cdot { w _ { b } } = { c _ { a b } }$

$$
W _ { 1 } \cdot W _ { 1 } = { \frac { 1 } { 2 } } c _ { 1 1 } \qquad W _ { 1 } \cdot W _ { 2 } = { \frac { 1 } { 2 } } c _ { 1 2 } \qquad W _ { 2 } \cdot W _ { 2 } = { \frac { 1 } { 2 } } c _ { 2 2 }
$$

Recall that $V _ { 2 }$ is defined up to a shift by $V _ { 1 }$ ： $V _ { 2 } = V _ { 2 } ^ { 0 } - c V _ { 1 }$ . The consequence is that $W _ { 1 }$ is defined up to a shift by $W _ { 2 }$ ： $W _ { 1 } = W _ { 1 } ^ { 0 } + c W _ { 2 }$ . Note that the numerical factors in front of $V _ { 1 }$ and $W _ { 2 }$ are opposite. Write down $( W _ { 1 } ^ { 0 } , W _ { 2 } )$ in terms of $( C ^ { A } , z )$

$$
{ \mathrm {  ~ \sigma _ { 1 } ^ { \circ } = } } \frac { 1 } { 4 z } \left( \begin{array} { c } { { ( C ^ { 2 } + C ^ { 4 } ) + ( C ^ { 1 } + C ^ { 3 } ) z } } \\ { { ( C ^ { 2 } - C ^ { 4 } ) + ( C ^ { 1 } - C ^ { 3 } ) z } } \\ { { 2 C ^ { 3 } + 2 C ^ { 2 } z } } \end{array} \right) \qquad W _ { 2 } = \frac { 1 } { 2 } \left( \begin{array} { c } { { - ( C ^ { 2 } + C ^ { 4 } ) + ( C ^ { 1 } + C ^ { 3 } ) z } } \\ { { - ( C ^ { 2 } - C ^ { 4 } ) + ( C ^ { 1 } - C ^ { 3 } ) z } } \\ { { - 2 C ^ { 3 } + 2 C ^ { 2 } z } } \end{array} \right)
$$

The twistor representations of $W _ { 1 }$ and $W _ { 2 }$ are

$$
{ \begin{array} { r l r } { } & { = { \left( \begin{array} { l l } { C ^ { 1 } u ^ { 2 } - C ^ { 2 } u ^ { 1 } } & { C ^ { 2 } u ^ { 2 } - C ^ { 3 } u ^ { 1 } } \\ { C ^ { 2 } u ^ { 2 } - C ^ { 3 } u ^ { 1 } } & { C ^ { 3 } u ^ { 2 } - C ^ { 4 } u ^ { 1 } } \end{array} \right) } } & { \quad W _ { 2 } = { \left( \begin{array} { l l } { C ^ { 1 } z ^ { 2 } - C ^ { 2 } z ^ { 1 } } & { C ^ { 2 } z ^ { 2 } - C ^ { 3 } z ^ { 1 } } \\ { C ^ { 2 } z ^ { 2 } - C ^ { 3 } z ^ { 1 } } & { C ^ { 3 } z ^ { 2 } - C ^ { 4 } z ^ { 1 } } \end{array} \right) } } \end{array} }
$$

Define the totally symmetric $P ^ { \alpha \beta \gamma }$

$$
P ^ { 1 1 1 } = C ^ { 1 } \qquad P ^ { 1 1 2 } = C ^ { 2 } \qquad P ^ { 1 2 2 } = C ^ { 3 } \qquad P ^ { 2 2 2 } = C ^ { 4 }
$$

Then the three-vectors $( W _ { 1 } , W _ { 2 } )$ span the four dimensional space

$$
( W _ { 1 } ^ { \alpha } , W _ { 2 } ^ { \alpha } ) _ { B P S } = ( P ^ { \alpha \beta \gamma } u _ { \gamma } , P ^ { \alpha \beta \gamma } z _ { \gamma } )
$$

# 5.2.2 Properties of $k _ { N o n B P S }$ （204

The form of $\boldsymbol { v } _ { a }$ for the non-BPS case is only slightly different from the BPS case: the two vectors $v _ { a }$ can be chosen to have the form:

$$
v _ { 1 } = ( V _ { 1 } , \eta _ { 1 } V _ { 1 } , 0 ) \qquad v _ { 2 } = ( V _ { 2 } , - \eta _ { 1 } V _ { 2 } , \sqrt { 2 } )
$$

The twistor representation of a three-vector $\boldsymbol { v } = ( x , y , z )$ is

$$
\sigma _ { v } = x \sigma _ { 0 } + y \sigma _ { 3 } + z \sigma _ { 1 } = \left( \begin{array} { c c } { { x + y } } & { { z } } \\ { { z } } & { { x - y } } \end{array} \right)
$$

It's length is

$$
v ^ { T } \eta _ { 1 } v = \operatorname* { d e t } ( \sigma _ { v } ) = x ^ { 2 } - y ^ { 2 } - z ^ { 2 }
$$

where $V _ { 1 } , V _ { 2 }$ are two three-vectors satisfying the same condition as the BPS ones (5.18). Again, the vectors $V _ { 1 }$ and $V _ { 2 }$ can be written as (5.19), and the twistor representations are given in (5.24) with one major difference: $u$ is no longer arbitrary, but is determined by $C ^ { \alpha A }$ as:

$$
u = \frac { u ^ { 2 } } { u ^ { 1 } } = \frac { C ^ { 2 2 } } { C ^ { 1 2 } }
$$

The form of $( w _ { 1 } , w _ { 2 } )$ are also slightly different from the BPS one (5.25)

$$
w _ { 1 } = \left( W _ { 1 } , - \eta _ { 1 } W _ { 1 } , 0 \right) \qquad w _ { 2 } = \left( W _ { 2 } , \eta _ { 1 } W _ { 2 } , 0 \right)
$$

The $( W _ { 1 } , W _ { 2 } )$ can be written in terms of $( C ^ { \alpha a } , z )$ thus:

$$
\frac { 1 } { ( C ^ { 2 2 } z ^ { 1 } - C ^ { 1 2 } z ^ { 2 } ) } \left( \begin{array} { c } { { [ ( C ^ { 1 1 } C ^ { 2 2 } - C ^ { 1 2 } C ^ { 2 1 } ) z ^ { 2 } + ( C ^ { 2 2 } ) ^ { 2 } ] + [ C ^ { 1 1 } C ^ { 2 2 } - C ^ { 1 2 } C ^ { 2 1 } + ( C ^ { 1 2 } C ^ { 2 2 } ) ^ { 2 } ] } } \\ { { - [ ( C ^ { 1 1 } C ^ { 2 2 } - C ^ { 1 2 } C ^ { 2 1 } ) z ^ { 2 } + ( C ^ { 2 2 } ) ^ { 2 } ] + [ C ^ { 1 1 } C ^ { 2 2 } - C ^ { 1 2 } C ^ { 2 1 } + ( C ^ { 1 2 } C ^ { 2 2 } ) ^ { 2 } ] } } \\ { { 2 [ ( C ^ { 1 1 } C ^ { 2 2 } - C ^ { 1 2 } C ^ { 2 1 } ) z + C ^ { 1 2 } C ^ { 2 2 } ] } } \end{array} \right) .
$$

$$
W _ { 2 } = - \frac { 1 } { 2 } \left( \begin{array} { c } { { z [ C ^ { 1 1 } z ^ { 2 } + ( 3 C ^ { 1 2 } - C ^ { 2 1 } ) z - 2 C ^ { 2 2 } ] + [ C ^ { 1 1 } z + C ^ { 1 2 } - C ^ { 2 1 } ] } } \\ { { - z [ C ^ { 1 1 } z ^ { 2 } + ( 3 C ^ { 1 2 } - C ^ { 2 1 } ) z - 2 C ^ { 2 2 } ] + [ C ^ { 1 1 } z + C ^ { 1 2 } - C ^ { 2 1 } ] } } \\ { { 2 [ C ^ { 1 1 } z ^ { 2 } + ( 2 C ^ { 1 2 } - C ^ { 2 1 } ) z - C ^ { 2 2 } ] } } \end{array} \right)
$$

In terms of u =² $\begin{array} { r } { u = \frac { u ^ { 2 } } { u ^ { 1 } } = \frac { C ^ { 2 : 2 } } { C ^ { 1 2 } } } \end{array}$ , the twistor representation of $W _ { 1 }$ and $W _ { 2 }$ are:

$$
W _ { 1 } ^ { \alpha \beta } = u ^ { \alpha } u ^ { \beta } + ( C ^ { 1 1 } u ^ { 2 } - C ^ { 1 2 } u ^ { 1 } ) z ^ { \alpha } z ^ { \beta }
$$

$$
\begin{array} { r } { W _ { 2 } ^ { \alpha \beta } = ( z ^ { \alpha } u ^ { \beta } + u ^ { \alpha } z ^ { \beta } ) + ( C ^ { 2 1 } - C ^ { 1 1 } z - 3 u ^ { 1 } ) z ^ { \alpha } z ^ { \beta } } \end{array}
$$

As a consequence, the precise value of $u$ is an extra constraint on the vectors $w _ { a }$ ,and there is only a three-dimensional space of them，with $( W _ { 1 } , W _ { 2 } )$ a linear combination of $( 0 , V _ { 1 } )$ 5 $( V _ { 1 } , 0 )$ and $( u ^ { \alpha } u ^ { \beta } , 2 V _ { 2 } )$ ：

$$
( W _ { 1 } , W _ { 2 } ) _ { N o n B P S } = m ( 0 , V _ { 1 } ) + n ( V _ { 1 } , 0 ) + \ell ( u ^ { \alpha } u ^ { \beta } , 2 V _ { 2 } )
$$

# 6 Single-centered Attractor Flows in $G _ { 2 ( 2 ) } / ( S L ( 2 , \mathbb { R } ) \times$ $S L ( 2 , \mathbb { R } ) )$ Model

Now that we have completely characterized the generators of single-centered attractor flow, we can lift the geodesics to four-dimensional black hole solutions. After some calculational effort, we find that the BPS solution is given in terms of harmonic functions. Next, we show that the non-BPS case is qualitatively diferent, and the final solutions cannot be formulated so simply.

# 6.1 BPS Attractor Flow

# 6.1.1 Lifting a geodesic to $4 D$

We have already noted that the flow starting from generic asymptotic moduli $( x _ { 0 } , y _ { 0 } )$ is generated by $\begin{array} { r } { M ( \tau ) = e ^ { ( k \tau + g ) / 2 } } \end{array}$ ，with $g$ defined before in (4.43). The matrix $g$ has the same form as $k$ . Therefore, in the BPS case, it has the expansion

$$
g _ { B P S } = a _ { \alpha A } z ^ { \alpha } G ^ { A }
$$

where the twistor $z$ is the same as the one in $k _ { B P S }$ . The flow of $( x , y )$ and $u$ can be extracted from the symmetric matrix $S ( \tau ) = M ( \tau ) S _ { 0 } M ( \tau ) ^ { T }$ via (4.32) and (4.33). Using $k _ { B P S } ^ { 3 } = 0$ and $g ^ { 3 } = 0$ ， $S ( \tau ) = S _ { 0 } e ^ { k \tau + g }$ is a quadratic function of $\tau$

$$
\begin{array} { r c l } { { S _ { 5 5 } ( \tau ) _ { B P S } } } & { { = } } & { { \alpha _ { B } ( \tau ) + \beta _ { B } ( \tau ) - 1 } } \\ { { S _ { 3 5 } ( \tau ) _ { B P S } } } & { { = } } & { { \gamma _ { B } ( \tau ) + \delta _ { B } ( \tau ) } } \\ { { S _ { 3 3 } ( \tau ) _ { B P S } } } & { { = } } & { { \epsilon _ { B } ( \tau ) + \zeta _ { B } ( \tau ) - 1 } } \end{array}
$$

where $\{ \alpha _ { B } ( \tau ) , \gamma _ { B } ( \tau ) , \epsilon _ { B } ( \tau ) \}$ are quadratic functions of $\tau$ ，and $\{ \beta _ { B } , \delta _ { B } , \zeta _ { B } \}$ are linear func tions of $\tau$ ：

$$
\begin{array} { l c l } { { \alpha _ { B } ( \tau ) } } & { { = } } & { { z ^ { 2 } ( H ^ { 2 } H ^ { 4 } - ( H ^ { 3 } ) ^ { 2 } ) + z ( H ^ { 2 } H ^ { 3 } - H ^ { 1 } H ^ { 4 } ) + ( H ^ { 1 } H ^ { 3 } - ( H ^ { 2 } ) ^ { 2 } ) } } \\ { { \beta _ { B } ( \tau ) } } & { { = } } & { { ( H ^ { 2 } - H ^ { 4 } ) z + ( H ^ { 3 } - H ^ { 1 } ) } } \\ { { } } & { { } } & { { } } \\ { { \gamma _ { B } ( \tau ) } } & { { = } } & { { - \displaystyle \frac { 1 } { 2 } \left( ( H ^ { 1 } H ^ { 4 } - H ^ { 2 } H ^ { 3 } ) ( z ^ { 2 } - 1 ) + 2 ( H ^ { 2 } ( H ^ { 2 } + H ^ { 4 } ) - H ^ { 3 } ( H ^ { 1 } + H ^ { 3 } ) ) z \right. } } \\ { { } } & { { } } & { { } } \\ { { \delta _ { B } ( \tau ) } } & { { = } } & { { - \displaystyle \frac { 1 } { 2 } ( ( H ^ { 1 } + H ^ { 3 } ) z - ( H ^ { 2 } + H ^ { 4 } ) ) } } \\ { { } } & { { } } & { { \epsilon _ { B } ( \tau ) } } & { { = } } & { { ( H ^ { 1 } H ^ { 3 } - ( H ^ { 2 } ) ^ { 2 } ) z ^ { 2 } + ( H ^ { 1 } H ^ { 4 } - H ^ { 2 } H ^ { 3 } ) z + ( H ^ { 2 } H ^ { 4 } - ( H ^ { 3 } ) ^ { 2 } ) } } \\ { { } } & { { } } & { { \zeta _ { B } ( \tau ) } } & { { = } } \end{array}
$$

where $H ^ { A }$ is a linear function of $\tau$ defined as $H ^ { A } ( \tau ) \equiv C ^ { A } \tau + G ^ { A }$

The attractor values are reached when $\tau \longrightarrow \infty$ along the geodesic:

and

$$
x _ { B P S } ^ { * } = - \frac { ( k ^ { 2 } S _ { 0 } ) _ { 3 5 } } { ( k ^ { 2 } S _ { 0 } ) _ { 3 3 } } \qquad y _ { B P S } ^ { * } = \frac { \sqrt { ( k ^ { 2 } S _ { 0 } ) _ { 3 3 } ( k ^ { 2 } S _ { 0 } ) _ { 5 5 } - ( k ^ { 2 } S _ { 0 } ) _ { 3 5 } ^ { 2 } } } { ( k ^ { 2 } S _ { 0 } ) _ { 3 3 } }
$$

$$
u _ { B P S } ^ { \ast } = \frac { 1 } { \sqrt { ( k ^ { 2 } S _ { 0 } ) _ { 3 3 } ( k ^ { 2 } S _ { 0 } ) _ { 5 5 } - ( k ^ { 2 } S _ { 0 } ) _ { 3 5 } ^ { 2 } } }
$$

The asymptotic moduli $( x _ { 0 } , y _ { 0 } )$ can be expressed in terms of $( G ^ { A } , z )$ by extraction from （20 $S = e ^ { g } S _ { 0 }$ ：

![](images/c3bd1e8f39f0040f8c2cc860ad04df4398907c493aae28b52494d347b8bdd1df.jpg)  
Figure 3: Sample BPS fow. The attractor point is labeled $( x ^ { * } , y ^ { * } )$ . The initial points of each flow are given by $( x _ { 1 } = 1 . 5 , y _ { 1 } = 0 . 5 )$ ， $( x _ { 2 } = 2 , y _ { 2 } = 4 )$ ， $x _ { 3 } = - 0 . 2 , y _ { 3 } = 0 . 1 \mathrm { , }$ ， $x _ { 4 } =$ $- 1 , y _ { 4 } = 3$ ）

Using this technique, one can construct all BPS single-centered black holes. The charges of each black hole can be read off from the current $J$ using (4.34). One example is given in Figure 3,where we parametrically plot $x ( \tau )$ and $y ( \tau )$ for a BPS black hole with charges $( p ^ { 0 } , p ^ { 1 } , q _ { 1 } , q _ { 0 } ) = ( 5 , 2 , 7 , - 3 )$ and attractor point $( x ^ { * } , y ^ { * } ) = ( 0 . 3 2 9 7 8 7 , 0 . 7 8 8 5 0 3 )$ .6

# 6.1.2 $4 D$ solution for given set of charges

To get the solution for a specific set of charges requires more effort. In this section， we present the analytical result for any set of charges $( p ^ { I } , q _ { I } )$

The ten parameters in $k _ { B P S }$ and $g$ are $\{ z , u , C ^ { A } , G ^ { A } \}$ ，among which the twistor $u$ is arbitrary, corresponding to the freedom of the shift by $( v _ { 1 } , w _ { 2 } )$ in the definition of $( v _ { 2 } , w _ { 1 } )$ ： $( v _ { 2 } , w _ { 1 } ) \to ( v _ { 2 } + c v _ { 1 } , w _ { 1 } - c w _ { 2 } )$ . The remaining true parameters are enough to parameterize the four D-brane charges $( p ^ { I } , q _ { I } )$ and the arbitrary asymptotic moduli $( x _ { 0 } , y _ { 0 } )$ under the condition of vanishing Taub-NUT charge and fixing $u _ { 0 } = 1$ .We now solve for $k _ { B P S }$ and $g$ for the given D-brane charges and $( x _ { 0 } , y _ { 0 } )$ , using the eight constraints, namely, 4 charges and zero Taub-NUT charge plus 3 asymptotic moduli, to fix $C ^ { A }$ and $G ^ { A }$ , leaving the other twistor $z$ unfixed.7

For the sake of simplicity, we will denote $k _ { B P S }$ by $k$ for the rest of this section. Then the current $\begin{array} { r } { J ( Q ) = { \frac { k ^ { T } } { r ^ { 2 } } } } \end{array}$ gives the five coupled equations:

$$
\mathbf { Q } = S _ { 0 } ( k + \frac { 1 } { 2 } [ k , g ] ) S _ { 0 }
$$

In order to show that the BPS flow can be expressed in terms of harmonic functions:

$$
H ( \tau ) = Q \tau + h \qquad \mathrm { w i t h } \qquad Q = ( p ^ { I } , q _ { I } ) \qquad \mathrm { a n d } \qquad h = ( h ^ { I } , h _ { I } )
$$

we will solve $g$ in terms of $h$ instead of $( x _ { 0 } , y _ { 0 } )$ . The four $h$ 's relate to the asymptotic moduli by

$$
x _ { 0 } = x ^ { * } ( Q \to h ) \qquad y _ { 0 } = y ^ { * } ( Q \to h ) \qquad u _ { 0 } = u ^ { * } ( Q \to h )
$$

and there is one extra degree of freedom to be fixed later.

To evaluate $[ k , g ]$ ， we first use the commutation relation (4.11) to obtain

$$
\left[ a _ { 1 A } C ^ { A } , a _ { 1 B } G ^ { B } \right] = \langle C , G \rangle ( - 4 L _ { h } ^ { + } )
$$

where the product between $C ^ { A }$ and $G ^ { A }$ is defined as $' C , G \rangle \equiv C ^ { 1 } G ^ { 4 } - 3 C ^ { 2 } G ^ { 3 } + 3 C ^ { 3 } G ^ { 2 } - C ^ { 4 } G ^ { 1 }$ Then twisting Eq (6.9) with the twistor $z$ as in (5.11） gives the commutator of $k$ and $g$ with the same twistor $z$ ：

$$
[ k , g ] = [ a _ { \alpha A } z ^ { \alpha } C ^ { A } , a _ { \beta B } z ^ { \beta } G ^ { B } ] = \langle C , G \rangle \Theta
$$

where $\Theta$ is defined as $\Theta \equiv - \textstyle { \frac { 4 } { 1 + z ^ { 2 } } } e ^ { - z L _ { h } ^ { - } } L _ { h } ^ { + } e ^ { z L _ { h } ^ { - } }$ . On the other hand,using (4.43),

$$
[ k , g ] = \big ( \boldsymbol { v _ { 2 } } \boldsymbol { v } _ { 1 } ^ { T } - \boldsymbol { v } _ { 1 } \boldsymbol { v } _ { 2 } ^ { T } \big ) S _ { 0 } \big ( \boldsymbol { w _ { 2 } } \cdot \boldsymbol { m } _ { 1 } - \boldsymbol { w } _ { 1 } \cdot \boldsymbol { m } _ { 2 } \big )
$$

（20 $\Theta$ can also be written as $\Theta = ( v _ { 2 } v _ { 1 } ^ { T } - v _ { 1 } v _ { 2 } ^ { T } ) S _ { 0 }$ , and we can check that $\left( w _ { 2 } \cdot m _ { 1 } - w _ { 1 } \cdot m _ { 2 } \right) =$ （204号 $\langle C , G \rangle$

First, separate from $G ^ { A }$ the piece which has the same dependence on $( h , z )$ as $C ^ { A }$ on $( Q , z )$

$$
G ^ { A } = G _ { h } ^ { A } + E ^ { A } \qquad \mathrm { w i t h } \qquad G _ { h } ^ { A } \equiv C ^ { A } ( Q \to h , z )
$$

That is, $g$ contains two pieces:

$$
g = g _ { h } + \Lambda \qquad \mathrm { w i t h } \qquad g _ { h } = a _ { \alpha A } z ^ { \alpha } G _ { h } ^ { A } \qquad \mathrm { a n d } \qquad \Lambda = a _ { \alpha A } z ^ { \alpha } E ^ { A }
$$

We need to solve for $E ^ { A }$

There are three constraints from (6.8). The $( x _ { 0 } , y _ { 0 } )$ and $u _ { 0 }$ are extracted from the symmetric matrix $S \ = \ e ^ { g } S _ { 0 }$ via (4.32） and (4.33). On the other hand, requiring (6.8） gives $( x _ { 0 } , y _ { 0 } , u _ { 0 } )$ in terms of $h$ ：

$$
\begin{array} { r } { \underbrace { \phantom { i } g _ { h } ^ { 2 } S _ { 0 } ) _ { 3 5 } } _ { \langle g _ { h } ^ { 2 } S _ { 0 } \rangle _ { 3 3 } } \qquad y _ { 0 } = \frac { \sqrt { ( g _ { h } ^ { 2 } S _ { 0 } ) _ { 3 3 } ( g _ { h } ^ { 2 } S _ { 0 } ) _ { 5 5 } - ( g _ { h } ^ { 2 } S _ { 0 } ) _ { 3 5 } ^ { 2 } } } { ( g _ { h } ^ { 2 } S _ { 0 } ) _ { 3 3 } } \qquad u _ { 0 } = \frac { 1 } { \sqrt { ( g _ { h } ^ { 2 } S _ { 0 } ) _ { 3 3 } ( g _ { h } ^ { 2 } S _ { 0 } ) _ { 5 5 } - ( g _ { h } ^ { 2 } S _ { 0 } ) _ { 3 5 } ^ { 2 } } } } \end{array}
$$

Therefore, defining $\begin{array} { r } { \Pi \equiv ( e ^ { g } - \frac { g _ { h } ^ { 2 } } { 2 } ) S _ { 0 } } \end{array}$ ， $\Pi$ has to satisfy three constaints:

$$
\Pi _ { 3 3 } = \Pi _ { 3 5 } = \Pi _ { 5 5 } = 0
$$

in order for(6.14) to hold for arbitrary $h$ . Using the unfixed degree of freedom in $h$ 's to set $\langle C , G _ { h } \rangle = 0$ ，(6.6）becomes

$$
\mathbf { Q } = S _ { 0 } ( k + \frac { 1 } { 2 } [ k , \Lambda ] ) S _ { 0 }
$$

The zero Taub-NUT charge condition in (6.16) imposes the fourth constraint on $\Lambda$ ：the (3,2)-element of $S _ { 0 } ( k + { \textstyle \frac { 1 } { 2 } } [ k , \Lambda ] ) S _ { 0 }$ for arbitrary $k$ has to vanish. Combining with (6.15),we have 4 constraints to fix $E ^ { A }$ to be:

$$
E ^ { 1 } = - E ^ { 3 } = - { \frac { 1 } { 1 + z ^ { 2 } } } \qquad E ^ { 2 } = - E ^ { 4 } = { \frac { z } { 1 + z ^ { 2 } } }
$$

The remaining 4 conditions in the coupled equations (6.16) determine $C ^ { A }$ in the BPS generator $k _ { B P S } = a _ { \alpha A } z ^ { \alpha } C ^ { A }$ to be

$$
\begin{array} { l l l } { { C ^ { 1 } } } & { { = } } & { { \sqrt { 2 } { \frac { - q _ { 0 } - q _ { 1 } z - 3 p ^ { 1 } z ^ { 2 } + p ^ { 0 } z ^ { 3 } } { ( 1 + z ^ { 2 } ) ^ { 2 } } } } } \\ { { } } & { { } } & { { } } \\ { { C ^ { 2 } } } & { { = } } & { { \sqrt { 2 } { \frac { - { \frac { q _ { 1 } } { 3 } } - { \bigl ( 2 p ^ { 1 } - v _ { 0 } \bigr ) } z + { \bigl ( p ^ { 0 } + 2 { \frac { q _ { 1 } } { 3 } } \bigr ) } z ^ { 2 } + p ^ { 1 } z ^ { 3 } } } } } \\ { { } } & { { } } & { { } } \\ { { C ^ { 3 } } } & { { = } } & { { \sqrt { 2 } { \frac { - p ^ { 1 } + { \bigl ( p ^ { 0 } + 2 { \frac { q _ { 1 } } { 3 } } \bigr ) z + \bigl ( 2 p ^ { 1 } - v _ { 0 } \bigr ) z ^ { 2 } - { \frac { q _ { 1 } } { 3 } } z ^ { 3 } } } { \bigl ( 1 + z ^ { 2 } \bigr ) } } } } \\ { { } } & { { } } & { { } } \\ { { C ^ { 4 } } } & { { = } } & { { \sqrt { 2 } { \frac { p ^ { 0 } + 3 p ^ { 1 } z - q _ { 1 } z ^ { 2 } + q _ { 0 } z ^ { 3 } } { \bigl ( 1 + z ^ { 2 } \bigr ) ^ { 2 } } } } } \end{array}
$$

The $G _ { h } ^ { A }$ are then determined by $G _ { h } ^ { A } = a _ { \alpha A } z ^ { A } C ^ { A } ( Q  h , z )$ . Using the solution of $C ^ { A }$ and $G _ { h } ^ { A }$ ， we see the product $\langle C ^ { A } , G _ { h } ^ { A } \rangle$ is proportionaltothesmplectic productof $( p ^ { I } , q _ { I } )$ and （20 $( h ^ { I } , h _ { I } )$ ：

$$
\langle C ^ { A } , G _ { h } ^ { A } \rangle = \frac { 2 } { 1 + z ^ { 2 } } < Q , h > \qquad \mathrm { w h e r e } \qquad < Q , h > \equiv p ^ { 0 } h _ { 0 } + p ^ { 1 } h _ { 1 } - q _ { 1 } h ^ { 1 } - q _ { 0 } \mathrm { } \mathrm { } \omega _ { 0 } .
$$

The condition $\langle C ^ { A } , G _ { h } ^ { A } \rangle = 0$ is then the integrability condition on $h$

$$
< Q , h > = p ^ { 0 } h _ { 0 } + p ^ { 1 } h _ { 1 } - q _ { 1 } h ^ { 1 } - q _ { 0 } h ^ { 0 } = 0
$$

Substituting the expressions of $C ^ { A }$ and $G ^ { A }$ in terms of $( p ^ { I } , q _ { I } )$ into (6.2),we obtain the BPS attractor flow in terms of the charges $( p ^ { I } , q _ { I } )$ . In particular, the attractor values are

$$
x _ { B P S } ^ { * } = - \frac { p ^ { 0 } q _ { 0 } + p ^ { 1 } \frac { q _ { 1 } } { 3 } } { 2 [ ( p ^ { 1 } ) ^ { 2 } + p ^ { 0 } \frac { q _ { 1 } } { 3 } ] } \qquad y _ { B P S } ^ { * } = \frac { \sqrt { J _ { 4 } ( p ^ { 0 } , p ^ { 1 } , \frac { q _ { 1 } } { 3 } , q _ { 0 } ) } } { 2 [ ( p ^ { 1 } ) ^ { 2 } + p ^ { 0 } \frac { q _ { 1 } } { 3 } ] }
$$

where $J _ { 4 } ( p ^ { 0 } , p ^ { 1 } , q _ { 1 } , q _ { 0 } )$ is the quartic $E _ { 7 ( 7 ) }$ invariant:

$$
J _ { 4 } ( p ^ { 0 } , p ^ { 1 } , q _ { 1 } , q _ { 0 } ) = 3 ( p ^ { 1 } q _ { 1 } ) ^ { 2 } - 6 ( p ^ { 0 } q _ { 0 } ) ( p ^ { 1 } q _ { 1 } ) - ( p ^ { 0 } q _ { 0 } ) ^ { 2 } - 4 ( p ^ { 1 } ) ^ { 3 } q _ { 0 } + 4 p ^ { 0 } ( q _ { 1 } ) ^ { 3 }
$$

thus $J _ { 4 } ( p ^ { 0 } , p ^ { 1 } , \frac { q _ { 1 } } { 3 } , q _ { 0 } )$ is the discriminant of charge. The attractor values match those from the compactification of Type I string theory on diagonal $T ^ { 6 }$ ，with $q _ { 1 } \to { \frac { q _ { 1 } } { 3 } }$ . The attractor value of $u$ is

$$
u _ { B P S } ^ { * } = \frac { 1 } { \sqrt { J _ { 4 } ( p ^ { 0 } , p ^ { 1 } , \frac { q _ { 1 } } { 3 } , q _ { 0 } ) } }
$$

The constraint on $h$ from $u _ { 0 } = 1$ is then $J _ { 4 } ( h ^ { 0 } , h ^ { 1 } , \frac { h _ { 1 } } { 3 } , h _ { 0 } ) = 1$

Now we will show that the geodesic we constructed above indeed reproduces the attractor fow given by replacing charges by the corresponding harmonic functions in the attractor

moduli. Using the properties of $\Lambda$ ，we have proved that, in terms of $k$ and $g$ , the flow of $( x , y )$ can be generated from the attractor value by replacing $k$ with the harmonic function （20 $k \tau + g _ { h }$ ：

$$
x ( \tau ) = x ^ { * } ( k \to k \tau + g _ { h } ) y ( \tau ) = y ^ { * } ( k \to k \tau + g _ { h } ) 
$$

Since $k$ and $g _ { h }$ have the same twistor $z$ ， this is equivalent to replacing the $C ^ { A }$ with the harmonic function $C ^ { A } \tau + G _ { h } ^ { A }$ while leaving the twistor $z$ fixed:

$$
x ( \tau ) = x ^ { * } ( C ^ { A }  C ^ { A } \tau + G _ { h } ^ { A } , z ) y ( \tau ) = y ^ { * } ( C ^ { A }  C ^ { A } \tau + G _ { h } ^ { A } , z )
$$

Since $C ^ { A }$ is linear in $Q$ and $G _ { h } ^ { A }$ linear in $h$ , and since $z$ drops out after plugging in the solution of $C ^ { A }$ in terms of $( Q , z )$ and $G _ { h } ^ { A }$ in terms of $( h , z )$ , this proves that the flow of $( x _ { 0 } , y _ { 0 } )$ is given by replacing the charges in the attractor moduli by the corresponding harmonic functions:

$$
x _ { B P S } ( \tau ) = x _ { B P S } ^ { * } ( Q  Q \tau + h ) \qquad y _ { B P S } ( \tau ) = y _ { B P S } ^ { * } ( Q  Q \tau + h )
$$

The integrability condition $< Q , h > = 0$ , in terms of $H = Q \tau + h$ ，is

$$
< H , d H > = 0
$$

# 6.2 non-BPS Attractor Flow

# 6.2.1 Lifting a geodesic to $4 D$

Similar to the BPS attractor flow， the non-BPS flow is generated by $\begin{array} { r } { M ( \tau ) ~ = ~ e ^ { ( k \tau + g ) / 2 } } \end{array}$ ， and $( x , y )$ can be extracted from the symmetric matrix $S ( \tau )$ by（4.32） and the relevant elements of $S ( \tau )$ are given by (6.2). The only difference is that now $\left\{ \alpha _ { B } , \beta _ { B } , \gamma _ { B } , \delta _ { B } , \epsilon _ { B } , \zeta _ { B } \right\}$ （204号 are changed into the non-BPS counterparts $\left\{ \alpha _ { N B } , \beta _ { N B } , \gamma _ { N B } , \delta _ { N B } , \epsilon _ { N B } , \zeta _ { N B } \right\}$ ，which can be written in terms of ${ \cal H } ^ { \alpha a } \equiv C ^ { \alpha a } \tau + G ^ { \alpha a }$ and $z$ ：

$$
\begin{array} { l c l } { { \alpha _ { N B } ( \tau ) } } & { { = } } & { { - ( ( H ^ { 2 1 } H ^ { 1 2 } - H ^ { 2 2 } H ^ { 1 1 } ) ( z ^ { 2 } - 1 ) ^ { 2 } + ( H ^ { 2 2 } ) ^ { 2 } z ^ { 2 } - 2 z H ^ { 1 2 } H ^ { 2 2 } + ( H ^ { 1 2 } ) ^ { 2 } ) ^ { 2 } } } \\ { { \beta _ { N B } ( \tau ) } } & { { = } } & { { ( z ^ { 2 } - 1 ) ( H ^ { 1 1 } - H ^ { 2 1 } z ) - 3 z ^ { 2 } H ^ { 2 2 } + 2 z H ^ { 1 2 } + H ^ { 2 2 } } } \\ { { \gamma _ { N B } ( \tau ) } } & { { = } } & { { ( z ^ { 2 } - 1 ) ( 2 z ( H ^ { 1 1 } H ^ { 2 2 } - H ^ { 1 2 } H ^ { 2 1 } ) + H ^ { 2 2 } H ^ { 1 2 } ) + z ( ( H ^ { 2 2 } ) ^ { 2 } - ( H ^ { 1 2 } ) ^ { 2 } ) } } \\ { { \delta _ { N B } ( \tau ) } } & { { = } } & { { \displaystyle \frac { 1 } { 2 } ( z ( 1 + z ^ { 2 } ) H ^ { 1 1 } + z ^ { 2 } ( 3 H ^ { 1 2 } - H ^ { 2 1 } ) - 2 H ^ { 2 2 } z + ( H ^ { 1 2 } - H ^ { 2 1 } ) ) } } \\ { { \epsilon _ { N B } ( \tau ) } } & { { = } } & { { ( 4 H ^ { 1 1 } H ^ { 2 2 } - H ^ { 1 2 } ( H ^ { 1 2 } + 4 H ^ { 2 1 } ) ) z ^ { 2 } - 2 H ^ { 1 2 } H ^ { 2 2 } z - ( H ^ { 2 2 } ) ^ { 2 } } } \\ { { \zeta _ { N B } ( \tau ) } } & { { = } } & { { 2 ( H ^ { 1 1 } z ^ { 2 } + ( 2 H ^ { 1 2 } + H ^ { 2 1 } ) z + H ^ { 2 2 } ) } } \end{array}
$$

Note that H2 $\textstyle { \frac { H ^ { 2 2 } } { H ^ { 1 2 } } } = u$ is fixed, independent of $\tau$ . The non-BPS flow written in terms of $( H ^ { \alpha a } , z )$ has the same simple form as the BPS flow, i.e. the scalars are rational functions with both the numerator and denominator being only quadratic. This is due to the nilpotency of the

generator: $k ^ { 3 } = 0$ . Again, the attractor values are reached when $\tau \longrightarrow \infty$ , and the asymptotic moduli can be expressed in terms of $( G ^ { \alpha a } , z )$ by extraction from $S = e ^ { g } S _ { 0 }$

Unlike the BPS case, there are only eight parameters in $k _ { N o n B P S }$ and $g _ { N o n B P S }$ : the two twistors $( z , u )$ and $( C ^ { \alpha a } , G ^ { \alpha a } )$ under the constraints that

$$
u = \frac { C ^ { 2 2 } } { C ^ { 1 2 } } = \frac { G ^ { 2 2 } } { G ^ { 1 2 } }
$$

Therefore, while $k _ { B P S }$ and $g _ { B P S }$ can parameterize arbitrary $( p ^ { I } , q _ { I } )$ and $( x _ { 0 } , y _ { 0 } )$ while leaving $( z , u )$ free,all the parameters in $k _ { N o n B P S }$ and $g _ { N o n B P S }$ , including $( z , u )$ , will be fixed.

![](images/8809161ae5973f938eb8cce83ebe7ea56d016f2f6db901a83cf4a7e6e0e4b594.jpg)  
Figure 4: Sample non-BPS flow. The attractor point is labeled $( x ^ { * } , y ^ { * } )$ . The initial points ofeach flow are given by: ( $x _ { 1 } = 0 . 5 3 9 6 2 4$ $y _ { 1 } = 5 . 4 6 1 1 3 5$ ，( $x _ { 2 } = 1 . 6 7 9 8 4 ,$ （204号 $y _ { 2 } = 0 . 5 1 8 7 2 5$ ），( $x _ { 3 } =$ −0.432811, $y _ { 3 } = 0 . 2 8 9 4 9 3$ ），( $x _ { 4 } = 1 . 2 8 4 4 7$ ， $y _ { 4 } = 1 . 4 9 8 1 5$ ），( $x _ { 5 } = - 0 . 4 9 9 4 9 1$ ， $y _ { 5 } = 0 . 1 8 1 7 4 4 _ { , }$ ）

The attractor point in terms of $C ^ { \alpha a }$ is

$$
{ _ { 3 P S } } = { \frac { \gamma _ { N B } ( H ^ { \alpha a }  C ^ { \alpha a } ) } { \epsilon _ { N B } ( H ^ { \alpha a }  C ^ { \alpha a } ) } } \qquad y _ { N o n B P S } ^ { * } = { \frac { \sqrt { \alpha _ { N B } ( H ^ { \alpha a }  C ^ { \alpha a } ) } \epsilon _ { N B } ( H ^ { \alpha a }  C ^ { \alpha a } ) } { \epsilon _ { N B } ( H ^ { \alpha a }  C ^ { \alpha a } ) } } \quad \qquad 
$$

with $z$ given by

$$
\frac { 1 } { 2 } \left( - 3 C ^ { 1 2 } - C ^ { 2 1 } + z \left( ( z ^ { 2 } - 3 ) C ^ { 1 1 } + 3 z ( C ^ { 1 2 } + C ^ { 2 1 } ) + 6 C ^ { 2 2 } \right) \right) = 0
$$

As in the BPS case, the charges of the black hole are read off from the current $J$ using (4.34). We have checked that the attractor point is a non-supersymmetric critical point of the black hole potential $V _ { B H } = | Z | ^ { 2 } + | D Z | ^ { 2 }$ ：

$$
\partial V _ { B H } = 0 \qquad \mathrm { a n d } \qquad D Z \neq 0
$$

It reproduces the results reported in the literature [9]. An example of the non-BPS attractor flow is shown in Figure 4,with $( p ^ { 0 } , p ^ { 1 } , q _ { 1 } , q _ { 0 } ) = ( 5 , 2 , 7 , 3 )$ and attractor point $( x ^ { * } , y ^ { * } ) =$ $( - 0 . 3 2 3 3 8 5 , 0 . 5 8 0 3 7 5 )$ .Note that $J _ { 4 } ( 5 , 2 , 7 / 3 , 3 ) < 0$ , so this is indeed a non-BPS black hole. Unlike the BPS attractor flow,all the non-BPS flows starting from different asymptotic moduli have the same tangent direction at the attractor point. The mass matrix of the blackhole potential at a BPS critical point has two identical eigenvalues, whereas the eigenvalues at a non-BPS critical point are different. The common tangent direction for the non-BPS flows corresponds to the eigenvector associated with the smaller mass.

# 6.2.2 4 $. D$ solution for given set of charges

We now discuss how to construct the non-BPS black hole solution for a specific set of charges $( p ^ { I } , q _ { I } )$ ：

One major difference between the non-BPS case and the BPS case is that

$$
\left[ k _ { N o n B P S } , g _ { N o n B P S } \right] = 0
$$

automatically, since the forms of $( w _ { 1 } , w _ { 2 } )$ and $( m _ { 1 } , m _ { 2 } )$ guarantee that $w _ { 1 } \cdot m _ { 2 } = w _ { 2 } \cdot m _ { 1 } = 0$ ： Thus the charge equation (6.6) becomes simply

$$
\mathbf { Q } _ { N o n B P S } = S _ { 0 } ( k _ { N o n B P S } ) S _ { 0 }
$$

These five coupled equations determine the two twistors $( z , u )$ and $C ^ { \alpha a }$ in terms of $( p ^ { I } , q _ { I } )$ Similar to the BPS case, the four equations which determine the D-brane charge allow us to write $C ^ { \alpha a }$ in terms of the charges $( p ^ { 0 } , p ^ { 1 } , q _ { 1 } , q _ { 0 } )$ and the twistor $z$ via

$$
\begin{array} { r c l } { { C ^ { 1 1 } } } & { { = } } & { { \displaystyle \frac { ( - 2 q _ { 0 } + 6 ( p ^ { 1 } - q _ { 0 } ) z ^ { 2 } + 4 ( p ^ { 0 } + q _ { 1 } ) z ^ { 3 } - 6 p ^ { 1 } z ^ { 4 } ) } { \sqrt { 2 } \left( 1 + z ^ { 2 } \right) ^ { 3 } } } } \\ { { } } & { { } } & { { } } \\ { { C ^ { 1 2 } } } & { { = } } & { { \displaystyle \frac { ( p ^ { 0 } + \frac { q _ { 1 } } { 3 } ) - 2 ( 2 p ^ { 1 } - q _ { 0 } ) z - ( p ^ { 0 } + 5 \frac { q _ { 1 } } { 3 } ) z ^ { 2 } + 2 p ^ { 1 } z ^ { 3 } } { \sqrt { 2 } \left( 1 + z ^ { 2 } \right) ^ { 2 } } } } \\ { { } } & { { } } & { { } } \\ { { C ^ { 2 1 } } } & { { = } } & { { \displaystyle \frac { ( p ^ { 0 } - q _ { 1 } ) - 4 q _ { 1 } z ^ { 2 } + 4 ( 3 p ^ { 1 } - q _ { 0 } ) z ^ { 3 } + ( 3 p ^ { 0 } + q _ { 1 } ) z ^ { 4 } } { \sqrt { 2 } \left( 1 + z ^ { 2 } \right) ^ { 3 } } } } \\ { { } } & { { } } & { { } } \\ { { C ^ { 2 2 } } } & { { = } } & { { \displaystyle \frac { 2 p ^ { 1 } + ( p ^ { 0 } + 5 \frac { q _ { 1 } } { 3 } ) z - 2 ( 2 p ^ { 1 } - q _ { 0 } ) z ^ { 2 } - ( p ^ { 0 } + \frac { q _ { 1 } } { 3 } ) z ^ { 3 } } { \sqrt { 2 } \left( 1 + z ^ { 2 } \right) ^ { 2 } } } } \end{array}
$$

and $\begin{array} { r } { u = \frac { C ^ { 2 2 } } { C ^ { 1 2 } } } \end{array}$ . In contrast tothe BPS case,the $G ^ { \alpha a }$ do not enter the equations and therefore cannot be used to eliminate the twistor $z$ . Requiring the Taub-NUT charge to vanish gives the following degree-six equation for the $z$ ：

$$
^ { 0 } z ^ { 6 } + 6 p ^ { 1 } z ^ { 5 } - ( 3 p ^ { 0 } + 4 q _ { 1 } ) z ^ { 4 } - 4 ( 3 p ^ { 1 } - 2 q _ { 0 } ) z ^ { 3 } + ( 3 p ^ { 0 } + 4 q _ { 1 } ) z ^ { 2 } + 6 p ^ { 1 } z - p ^ { 0 } = 0
$$

The three parameters in $g _ { N o n B P S }$ ， namely, $G ^ { \alpha a }$ with the constraint $\textstyle { \frac { G ^ { 2 2 } } { G ^ { 1 2 } } } = u$ are then fixedby the given asymptotic moduli $( x _ { 0 } , y _ { 0 } )$ and $u _ { 0 } = 1$ ：

Similar to the BPS flow, the full non-BPS flow can be generated from the attractor value by replacing $C ^ { \alpha a }$ with the harmonic function $H ^ { \alpha a } ( \tau ) = C ^ { \alpha a } \tau + G ^ { \alpha a }$ ， while leaving （204号 $z$ unchanged as in (6.25). However, there are two major differences. First, the harmonic functions $H ^ { \alpha a }$ have to satisfy the constraint

$$
\frac { H ^ { 2 2 } ( \tau ) } { H ^ { 1 2 } ( \tau ) } = u = \frac { C ^ { 2 2 } } { C ^ { 1 2 } } = \frac { G ^ { 2 2 } } { G ^ { 1 2 } }
$$

Note that this does not impose any constraint on the alowed asymptotic moduli since there are still three degrees of freedom in $G ^ { \alpha a }$ to account for $( x _ { 0 } , y _ { 0 } , u _ { 0 } )$ . We will see later that it instead imposes a stringent constraint on the allowed D-brane charges in the multi-centered non-BPS solution.

Secondly, unlike the BPS flow, replacing $C ^ { \alpha a }$ in the attractor moduli by the harmonic function $H ^ { \alpha a } ( \tau )$ is not equivalent to replacing the charges $Q$ with $H = Q \tau + h$ as in (6.26). The twistor $z$ here is no longer free,but is determined in terms of the charges as a root of the degree-six equation (6.36)， so replacing $Q$ by $Q \tau + h$ ， for generic $Q$ and $h$ ， would not leave （204号 $z$ invariant. Therefore, the generic non-BPS flow cannot be given by the naive harmonic function procedure, as proposed by Kallosh et al [19]. Next, we will define the subset of the NonBPS single-centered flow that can be constructed by the harmonic function procedure.

When the attractor has only $D 4 - D 0$ charges, namely, $Q _ { 4 0 } = ( 0 , p ^ { 1 } , 0 , q _ { 0 } )$ ， (6.36) has a root $z = 0$ ，which is independent of the value of charges. If the asymptotic moduli $h$ is also of the form of $h _ { 4 0 } = ( 0 , h ^ { 1 } , 0 , h _ { 0 } )$ , replacing $Q _ { 4 0 }$ by $Q _ { 4 0 } \tau + h _ { 4 0 }$ would leave the solution $z = 0$ invariant. Now we will use the duality symmetry to extend the subset to a generic charge system with restricted asymptotic moduli.

The one-modulus system can be considered as the STU attractor with the three moduli $( S , T , U )$ identified. Since the STU model has $S L ( 2 , \mathbb { Z } ) ^ { 3 }$ duality symmetry at the level of the equations of motion, the one-modulus system has an $S L ( 2 , \mathbb { Z } )$ duality symmetry coming from identifying the three $S L ( 2 , \mathbb { Z } )$ symmetries of the STU model. That is, the one-modulus system is invariant under the following element of $S L ( 2 , \mathbb { Z } ) ^ { 3 }$ （20

$$
{ \hat { \Gamma } } = \left( { \begin{array} { c c } { a } & { b } \\ { c } & { d } \end{array} } \right) \otimes \left( { \begin{array} { c c } { a } & { b } \\ { c } & { d } \end{array} } \right) \otimes \left( { \begin{array} { c c } { a } & { b } \\ { c } & { d } \end{array} } \right) \qquad { \mathrm { w i t h } } \qquad a d - b c = 1
$$

The modulus $z = x + i y$ transforms as

$$
z  { \hat { \Gamma } } z = { \frac { a z + b } { c z + d } }
$$

and the transformation on the charges is given by [35]. A generic charge $( p ^ { 0 } , p ^ { 1 } , q _ { 1 } , q _ { 0 } )$ can be reached by applying the transformation $\hat { \Gamma }$ on a $D 4 - D 0$ system.

Under the aforementioned transformation, a $D 4 - D 0$ system transforms into $\hat { \Gamma } Q _ { 4 0 }$

$$
Q _ { 4 0 } = ( \begin{array} { c } { { 0 } } \\ { { p ^ { 1 } } } \\ { { 0 } } \\ { { q _ { 1 } } } \end{array} )  \hat { \Gamma } Q _ { 4 0 } = ( \begin{array} { c } { { - c ( 3 d ^ { 2 } p ^ { 1 } + c ^ { 2 } q _ { 0 } ) } } \\ { { d ( 2 b c + a d ) p ^ { 1 } + a c ^ { 2 } q _ { 0 } } } \\ { { 3 ( b ( b c + 2 a d ) p ^ { 1 } + a ^ { 2 } c q _ { 0 } ) } } \\ { { a ( 3 b ^ { 2 } p ^ { 1 } + a ^ { 2 } q _ { 0 } ) } } \end{array} )
$$

The solution of the twistor $z$ with the new charges $\hat { \Gamma } Q _ { 4 0 }$ is

$$
z = { \frac { a \pm { \sqrt { a ^ { 2 } + c ^ { 2 } } } } { c } }
$$

independent of the $D 4 - D 0$ charges we started with. Now given an arbitrary charge $Q$ there exists a transformation $\hat { \Gamma } _ { Q }$ such that $Q = { \hat { \Gamma } } _ { Q } Q _ { 4 0 }$ for some $Q _ { 4 0 }$ . The twistor $z$ remains invariant under $Q  Q \tau + \hat { \Gamma } _ { Q } h _ { 4 0 }$ for arbitrary $h _ { 4 0 }$ . We conclude that the non-BPS singlecentered black holes that can be constructed via the naive harmonic function procedure are only those with $( Q , h )$ being the image of a single transformation $\hat { \Gamma }$ on the $\left( Q _ { 4 0 } , h _ { 4 0 } \right)$ from a （204号 $D 4 - D 0$ system:

$$
{ \bf \Gamma } _ { B } ( \tau ) = x _ { N B } ^ { * } ( \hat { \Gamma } Q _ { 4 0 }  \hat { \Gamma } Q _ { 4 0 } \tau + \hat { \Gamma } h _ { 4 0 } ) \qquad y _ { N B } ( \tau ) = y _ { N B } ^ { * } ( \hat { \Gamma } Q _ { 4 0 }  \hat { \Gamma } Q _ { 4 0 } \tau + \hat { \Gamma } h _ { 4 0 } )
$$

Since we are considering arbitrary charge system, the constraint is on the allowed values of （204号 $h$ ：

# 7 Multi-centered Attractor Flows in $G _ { 2 ( 2 ) } / ( S L ( 2 , \mathbb { R } ) \times$ $S L ( 2 , \mathbb { R } ) )$ model

As proven in the pure gravity system, the multi-centered attractor solutions are given by exponentiating the matrix harmonic function $K ( \vec { x } )$ ：

$$
S ( \vec { x } ) = e ^ { K ( \vec { x } ) } S _ { 0 }
$$

with $K ( \vec { x } )$ having the same properties as the generator $k$

$$
K ^ { 3 } ( \vec { x } ) = 0 \qquad \mathrm { a n d } \qquad K ^ { 2 } ( \vec { x } ) \mathrm { r a n k \ t w o }
$$

We now describe how to formulate $K ( \vec { x } )$ for multi-centered solutions in $G _ { 2 ( 2 ) }$

The $K ( \vec { x } )$ satisfying all the above constraints is constructed as

$$
K ( \vec { x } ) = \sum _ { a = 1 , 2 } [ v _ { a } W _ { a } ( \vec { x } ) ^ { T } + W _ { a } ( \vec { x } ) v _ { a } ^ { T } ] S _ { 0 }
$$

with $v _ { a }$ being the same two constant null vectors in $k$ ，and the multi-centered harmonic function

$$
W _ { a } ( \vec { x } ) = \sum _ { i } { \frac { ( w _ { a } ) _ { i } } { | \vec { x } - \vec { x } _ { i } | } } + m _ { a }
$$

is everywhere orthogonal to $\boldsymbol { v } _ { a }$ . The two 7-vectors $( m _ { 1 } , m _ { 2 } )$ contain the information of asymptotic moduli andhasthe sameformas $( w _ { 1 } , w _ { 2 } )$ Write $K ( \vec { x } )$ $\begin{array} { r } { K ( \vec { x } ) = \sum _ { i } \frac { k _ { i } } { | \vec { x } - \vec { x } _ { i } | } + g } \end{array}$ where

$$
k _ { i } = \sum _ { a = 1 , 2 } [ v _ { a } ( w _ { a } ) _ { i } ^ { T } + ( w _ { a } ) _ { i } v _ { a } ^ { T } ] S _ { 0 } \qquad \mathrm { a n d } \qquad g = \sum _ { a = 1 , 2 } [ v _ { a } m _ { a } ^ { T } + m _ { a } v _ { a } ^ { T } ] S _ { 0 }
$$

Since $\boldsymbol { v }$ only depends on the twistor $( z , u )$ ，and $( w _ { 1 } , w _ { 2 } )$ are linear in $C ^ { A }$ or $C ^ { \alpha a }$ ， the above generating procedure is equivalent to replace $C ^ { A }$ or $C ^ { \alpha a }$ by the multi-centered harmonic functions while keeping the twistor $( z , u )$ fixed.

Next we discuss the properties of the BPS multi-centered attractor solution and non-BPS ones separately, since they are very different in character.

# 7.1 BPS Multi-centered Solutions

In constrast with the multi-centered solutions in pure gravity, now the second term of the current $\begin{array} { r } { J = \nabla K + \frac { 1 } { 2 } [ \nabla K , K ] } \end{array}$ does not vanish automatically since

$$
[ k _ { i } ^ { B P S } , k _ { j } ^ { B P S } ] \neq 0 \qquad \mathrm { a n d } \qquad [ k _ { i } ^ { B P S } , g ^ { B P S } ] \neq 0
$$

Therefore, the centers are no longer free,and we cannot simply read off the charges from $J$ Instead, we need to solve for $C _ { i } ^ { A }$ and $G ^ { A }$ in a set of $5 N$ coupled equations. The divergence of the current is

$$
\nabla \cdot J = 4 \pi \sum _ { i } \delta ( \vec { x } - \vec { x } _ { i } ) S _ { 0 } ( k _ { i } + \frac { 1 } { 2 } [ k _ { i } , g ] + \frac { 1 } { 2 } \sum _ { j } \frac { [ k _ { i } , k _ { j } ] } { | \vec { x } _ { i } - \vec { x } _ { j } | } ) S _ { 0 }
$$

Using $\mathbf { Q } _ { i }$ to denote the charge matrix which relates to the D-brane charge $\{ p ^ { 0 } , p ^ { 1 } , q _ { 1 } , q _ { 0 } \} _ { i }$ as in (4.36),and with $Q _ { 3 2 }$ as the vanishing NUT charge,we have $5 N$ coupled equations from （20 $\begin{array} { r } { \mathbf Q _ { i } = \frac { 1 } { 4 \pi } \int _ { i } \nabla \cdot \boldsymbol J } \end{array}$ ：

$$
\mathbf { Q } _ { i } = S _ { 0 } \big ( k _ { i } + \frac { 1 } { 2 } [ k _ { i } , g ] + \frac { 1 } { 2 } \sum _ { j } \frac { [ k _ { i } , k _ { j } ] } { | \vec { x } _ { i } - \vec { x } _ { j } | } \big ) S _ { 0 }
$$

The generators of the multi-centered BPS attractor solution $\{ k _ { i } \}$ and $g$ have $4 ( N + 1 ) + 2$ （20 parameters in total: the two twistors $( z , u )$ and $\{ C _ { i } ^ { A } , G ^ { A } \}$ . On the left hand side of (7.8), there are also $3 N - 3$ degrees of freedom from the position of the centers $\vec { x } _ { i }$ .On the other hand, a generic $N$ -centered attractor solution has $4 N$ D-brane charges $( p ^ { I } , q _ { I } )$ ，and three additional constraints from the asymptotic moduli $( x _ { 0 } , y _ { 0 } )$ and $u _ { 0 } = 1$ . As we will show, like the single-centered BPS solution, the three asymptotic moduli, together with the vanishing of the total Taub-NUT charge, determine the 4 $G ^ { A }$ inside $g$ .Moreover，as in the singlecentered case, we can solve $C _ { i } ^ { A }$ in terms of the $4 D$ D-brane charges $Q _ { i }$ while leaving $( z , u )$ unfixed. The remaining $N - 1$ zero Taub-NUT charge conditions at each center will impose （204号 $N - 1$ constraints on the distances between the $N$ -centers $\vec { x } _ { i }$

First, integrating over the circle at the infinity, $\begin{array} { r } { \sum _ { i } \mathbf { Q } _ { i } = \frac { 1 } { 4 \pi } \int \nabla \cdot \boldsymbol { J } } \end{array}$ gives the sum of the above $N$ matrix equations:

$$
\mathbf { Q } _ { t o t } = \sum _ { i } \mathbf { Q } _ { i } = S _ { 0 } ( \sum _ { i } k _ { i } + \frac { 1 } { 2 } [ \sum _ { i } k _ { i } , g ] ) S _ { 0 }
$$

which is the same as the one for the single-center attractor with charge $\mathrm { \Delta } Q _ { t o t }$ . This determines $g$ to be $g = g _ { h } + \Lambda$ , same as the one for single-centered attractor in (6.13). As in the single centered case, $h$ is fixed by the asymptotic moduli $( x _ { 0 } , y _ { 0 } )$ by

$$
x _ { 0 } = x _ { B P S } ^ { * } ( Q \to h ) \qquad y _ { 0 } = y _ { B P S } ^ { * } ( Q \to h )
$$

and the two constraints:

$$
< Q _ { t o t } , h > = 0 \qquad J _ { 4 } ( h ^ { 0 } , h ^ { 1 } , { \frac { h _ { 1 } } { 3 } } , h _ { 0 } ) = 1
$$

We have used the vanishing of the total Taub-NUT charge to determine $\Lambda$ . Next, we will use the remaining coupled $5 N - 1$ equations to solve for the $4 N \ \{ C _ { i } ^ { A } \}$ and impose $N - 1$ constraints on the relative positions between the $N$ centers $\{ \vec { x } _ { i } \}$ where $i = 1 , \cdots , N$ ：

The tentative solutions of $C _ { i } ^ { A }$ are given by (6.18) with $( p ^ { I } , q _ { I } )$ replaced by $( p _ { i } ^ { I } , q _ { I , i } )$ . The fow generator of each center $k _ { i }$ is then $k _ { i } = a _ { \alpha A } z ^ { \alpha } C _ { i } ^ { A }$ . Substituting the solution of $k _ { i }$ and $g = g _ { h } + \Lambda$ into (7.8), and using

$$
[ k _ { i } , g _ { h } ] = 2 < Q _ { i } , h > \Theta \qquad [ k _ { i } , k _ { j } ] = 2 < Q _ { i } , Q _ { j } > \Theta
$$

where all the $k _ { i }$ 's and $g _ { h }$ have the same value for the twistor $z$ ，we get

$$
\mathbf { Q } _ { i } = S _ { 0 } ( k _ { i } + < Q _ { i } , h > \Theta + \frac { 1 } { 2 } [ k _ { i } , \Lambda ] + \sum _ { j } \frac { < Q _ { i } , Q _ { j } > } { | \vec { x } _ { i } - \vec { x } _ { j } | } \Theta ) S _ { 0 }
$$

Just as in the single-centered case, the solution of $k _ { i }$ and the form of $\Lambda$ guarantee that

$$
\mathbf { Q } _ { i } = S _ { 0 } \bigl ( k _ { i } + \frac { 1 } { 2 } [ k _ { i } , \Lambda ] \bigr ) S _ { 0 }
$$

We see that as long as the following integrability condition is satisfied:

$$
< Q _ { i } , h > + \sum _ { j } { \frac { < Q _ { i } , Q _ { j } > } { | \vec { x } _ { i } - \vec { x } _ { j } | } } = 0
$$

the $k _ { i }$ and $g$ given above indeed produce the correct multi-centered attractor solution. Just like in the single-centered case, the multi-centered solution flows to the correct attractor moduli $( x _ { i } ^ { * } , y _ { i } ^ { * } )$ near each center，independent of the value of $z$ .It also follows that the multi-centered solution can be generated by replacing the charges inside the attractor value by the multi-centered harmonic function:

$$
\cdot _ { B P S } ( \vec { x } ) = x _ { B P S } ^ { * } ( Q \to \sum _ { i } \frac { Q _ { i } } { | \vec { x } - \vec { x } _ { i } | } + h ) y _ { B P S } ( \vec { x } ) = y _ { B P S } ^ { * } ( Q \to \sum _ { i } \frac { Q _ { i } } { | \vec { x } - \vec { x } _ { i } | } + h ) ,
$$

The sum of the $N$ equations in the integrability condition (7.15) reproduces the constraint on $h$ $: < Q _ { t o t } , h > = 0$ . Thus the remaining $N - 1$ equations impose $N - 1$ constraints on the relative positions between the $N$ centers $\{ \vec { x } _ { i } \}$ with $i = 1 , \cdots , N$ . From (A.5) and (4.6), we see that $\ast \mathrm { d } \omega$ is given by $J _ { 2 3 }$ . Defining the angular momentum $\bar { J }$ by

$$
\omega _ { i } = 2 \epsilon _ { i j k } J ^ { j } \frac { x ^ { k } } { r ^ { 3 } } \qquad \mathrm { a s } \ r \to \infty
$$

we see that there exists a nonzero angular momentum given by

$$
\vec { J } = \frac { 1 } { 2 } \sum _ { i < j } \frac { \vec { x } _ { i } - \vec { x } _ { j } } { | \vec { x } _ { i } - \vec { x } _ { j } | } \langle Q _ { i } , Q _ { j } \rangle
$$

Thus we have shown that our multi-centered BPS attractor solution reproduces the one found in [18].

# 7.2 non-BPS Multi-centered Solutions.

For given $( z , u )$ and $\{ C _ { i } ^ { \alpha a } , G ^ { \alpha a } \}$ , the non-BPS multi-centered solution is the same as the single-centered one as in (6.28) with $H ^ { \alpha a } ( \tau )$ replaced by the multi-centered harmonic function $\begin{array} { r } { H ^ { \alpha a } ( \vec { x } ) = \sum _ { i } \frac { C _ { i } ^ { \alpha a } } { | \vec { x } - \vec { x } _ { i } | } + G ^ { \alpha a } } \end{array}$ satisfying the constraint

$$
u = \frac { H _ { i } ^ { 2 2 } ( \vec { x } ) } { H _ { i } ^ { 1 2 } ( \vec { x } ) } = \frac { C _ { i } ^ { 2 2 } } { C _ { i } ^ { 1 2 } } = \frac { G ^ { 2 2 } } { G ^ { 1 2 } }
$$

Accordingly, the attractor values at each center is the same as (6.30) with the corresponding （204号 $C _ { s } ^ { \alpha a }$ . The asymptotic moduli are obtained by extraction from $S = e ^ { g } S _ { 0 }$ ：

The equation of motion for the non-BPS multi-centered solution simplifies a great deal since

$$
[ \nabla K ( \vec { x } ) , K ( \vec { x } ) ] = 0
$$

automatically, following from the fact that for the non-BPS system:

$$
( w _ { 1 } ) _ { i } \cdot m _ { 2 } = ( w _ { 2 } ) _ { i } \cdot m _ { 1 } = 0
$$

which are guaranteed by the forms of NonBPS $( w _ { 1 } , w _ { 2 } ) _ { i }$ and $( m _ { 1 } , m _ { 2 } )$ . Therefore,the $5 N$ equations（7.8) decouple into $N$ sets of 5 coupled equations:

$$
\mathbf { Q } _ { i } = S _ { 0 } ( k _ { i } ) S _ { 0 }
$$

Equation (7.22) difers greatly from the BPS counterpart (7.8). Firstly, the generators of the multi-centered non-BPS attractor solution $\{ k _ { i } \}$ and $g$ have $3 ( N + 1 ) + 2$ parameters: the two twistors $( z , u )$ and $\{ C _ { i } ^ { \alpha a } , G ^ { \alpha a } \}$ with the constraint (7.19). In constrast to the BPS case, $g$ does not enter the equation. Thus we can simply use the three asymptotic moduli, without invoking the zero Taub-NUT condition, to determine the 3 $G ^ { \alpha a }$ inside $g$ . Secondly, unlike the BPS multi-centered solution, the position of the centers $\vec { x } _ { i }$ do not appear in the equation, therefore there willbe no constraint imposed on them: the centers are free.Last but not least, the remaining $3 N + 2$ parameters in $( z , u )$ and $C ^ { \alpha a }$ are not enough to parameterize a generic （20 $N$ -centered attractor solution， which has $4 N$ D-brane charges $( p _ { i } ^ { I } , q _ { I , i } )$ .Accordingly, the multi-centered non-BPS attractor generated by this ansatz will not have arbitrary charges. Combining with the fact that $\vec { x } _ { i }$ do not appear in the R.H.S of the equation, we find that all the $N$ vanishing Taub-NUT charge conditions can only act on the charges on the L.H.S. We conclude that, in total, there will be $2 N - 2$ constraints on the allowed charges.

Now we will show in detail the derivation of the constraints. First， like in the singlecentered NonBPS solution, the absence of the Taub-NUT charge at infinity fixes $z$ via

$$
\sum _ { i } { \bf Q } _ { i } = S _ { 0 } ( \sum _ { i } k _ { i } ) S _ { 0 }
$$

The solution is the same as the solution to (6.36) with the charges replaced by the total charges of $N$ centers: $z = z ( Q  \textstyle \sum _ { i } Q _ { i } )$ . Since all the $N$ centers share the same twistor （204号 $z$ , the absence of the NUT charge at each center imposes $N - 1$ constraints on the allowed charges $Q _ { i }$ : all $z ( Q _ { i } )$ have to be equal.

The remaining $4 N$ equations in （7.22） determine $C ^ { \alpha a }$ in terms of $z$ and $Q _ { i }$ . Since the N-centers decouple, (7.22) for each center is the same as the single-center one (6.34). Thus the solution of $C _ { i } ^ { \alpha a }$ is given by (6.35) with $( p ^ { I } , q _ { I } )$ replaced by $( p _ { i } ^ { I } , q _ { I , i } )$ . Again, since all the centers share the same twistor $u$ , the condition（7.19） imposes another $N - 1$ constraints on the allowed charges. Solving these $2 N - 2$ constraints,we see all the charges $\{ Q _ { i } \}$ are the image of a single transformation $\hat { \Gamma }$ on a multi-centered $D 4 - D 0$ system $Q _ { 4 0 , i }$ ：

$$
Q _ { i } = \hat { \Gamma } Q _ { 4 0 , i }
$$

The charges at different centers are all mutually local

$$
\langle Q _ { i } , Q _ { j } \rangle = 0
$$

Except for the constraint on the charges, the $N$ centers are independent,and there is no constraint on the position of the centers.A related fact is that the the angular momentum is zero.

Like the non-BPS single-centered case, though the multi-centered solution can be generated from the attractor value by replacing $C ^ { \alpha a }$ with the multi-centered harmonic function $\begin{array} { r } { H ^ { \alpha a } ( \vec { x } ) = \sum _ { i } \frac { C _ { i } ^ { \alpha a } } { | \vec { x } - \vec { x } _ { i } | } + G ^ { \alpha a } } \end{array}$ $z$ upcddasm :s BPS case, namely, by replacing the charges inside the attractor value by the corresponding multi-centered harmonic functions. The reason is again due to the fact that the twistor $z$ ， being a function of charges, does not remain invariant under this substitution of charges by harmonic functions. The multi-centered non-BPS solutions that can be generated by the harmonic function procedure are those with $\{ Q _ { i } , h \}$ being the image of a single $\hat { \Gamma }$ on the $\{ Q _ { 4 0 , i } , h _ { 4 0 } \}$ of a pure $D 4 - D 0$ system:

$$
= x _ { N B } ^ { * } ( \hat { \Gamma } Q _ { 4 0 } \to \sum _ { i } \frac { \hat { \Gamma } Q _ { 4 0 , i } } { | \vec { x } - \vec { x } _ { i } | } + \hat { \Gamma } h _ { 4 0 } ) y _ { N B } ( \vec { x } ) = y _ { N B } ^ { * } ( \hat { \Gamma } Q _ { 4 0 } \to \sum _ { i } \frac { \hat { \Gamma } Q _ { 4 0 , i } } { | \vec { x } - \vec { x } _ { i } | } + \hat { \Gamma } h _ { 4 0 } ) \qquad \quad
$$

It appears that the existence of a simple linear ansatz for “superimposing” single center solutions exists in general only for mutually local extremal black holes，and only in the supersymmetric case does it extend to mutually non-local centers.

To summarize, the non-BPS multi-centered solution is different from the BPS case because it imposes no constraints on the position of the centers,but instead on the allowed charges $Q _ { i }$ : the choice of charges at each center are restricted to a three-dimensional subspace,and they are mutually local. The result is that the centers can move freely,and there is no angular momentum in the system. It does not have interesting moduli spaces of centers with mutually non-local charges, so it is as “boring” as the pure gravity case.

# 8 Conclusion and Discussion

In this paper, we find exact single-centered and multi-centered black hole solutions in theories of gravity which have a symmetric 3D moduli space. The BPS and extremal non-BPS singlecentered solutions correspond to certain geodesics in the moduli space. We construct these geodesics by exponentiating diferent types of nilpotent elements in the coset algebra. Using the Jordan form of these nilpotent elements, we are able to write them down in closed explicit form. Furthermore, we can use a symmetric matrix parametrization to recover the metric and full fow of the scalars in four dimensions.

We have also generalized the geodesics to find solutions for non-BPS and BPS multicentered black holes. The BPS multi-centered solution reproduces the known solution of Bates and Denef. Given our assumption that the 3D spatial slice is flat, we find that a nonBPS multi-centered black hole is very diferent from its BPS counterpart. It is constrained to have mutually local charges at all of its centers and therefore carries no intrinsic angular momentum. It is possible that if we dropped this assumption，we could find more general non-BPS multi-centered solutions. Such configurations would probably be amenable to exact analysis only in the axially symmetric case,using inverse scattering methods.

There are many other avenues for future work. One could explore nilpotent elements in other symmetric spaces,and see whether non-BPS bound states with nonlocal charges exist. In particular, it would be interesting to study $E _ { 8 ( 8 ) } / S O ^ { * } ( 1 6 )$ , which is the 3d moduli space for $d = 4 , \mathcal { N } = 8$ supergravity. We would also like to find a way to modify our method so that we can apply it to non-symmetric homogeneous spaces, and eventually to generic moduli spaces. We could then study the much larger class of non-BPS extremal black holes in generic ${ \mathcal N } = 2$ supergravities.

# Acknowledgements

We thank A. Neitzke, J. Lapan and A. Strominger for helpful discussions. The work is supported by DOE grant DE-FG02-91ER40654. M.P. is also supported by an NSF Graduate Fellowship.

# A Derivation of the moduli space $\mathcal { M } _ { 3 D }$

Here we briefly review the derivation of the $3 d$ moduli space $\mathcal { M } _ { 3 D }$ from the $c ^ { * }$ -map of the （204号 $4 D$ supergravity coupled to $n _ { V }$ vector multiplets [31] [32] [33].

The bosonic part of the action for the ${ \mathcal N } = 2$ supergravity coupled to $n _ { V }$ vector-multiplets is:

$$
S = - \frac { 1 } { 1 6 \pi } \int d ^ { 4 } x \sqrt { g ^ { ( 4 ) } } \left[ R - 2 g _ { i \bar { j } } d z ^ { i } \wedge * _ { 4 } d \bar { z } ^ { \bar { j } } - F ^ { I } \wedge G _ { I } \right]
$$

where the ranges of the indices are $i , j ~ = ~ 1 , \ldots , n _ { V }$ and $I ~ = ~ 0 , 1 , . . . , n _ { V }$ ，and $G _ { I } \ =$

$( R e \mathcal { N } ) _ { I J } F ^ { J } + ( I m \mathcal { N } ) _ { I J } \ast F ^ { J }$ . The complex symmetric matrix $\mathcal { N } _ { I J }$ is defined by

$$
F _ { I } = \mathcal { N } _ { I J } X ^ { J } \qquad D _ { i } F _ { I } = \overline { { \mathcal { N } } } _ { I J } D _ { i } X ^ { J }
$$

For model endowed with a prepotential $F ( X )$

$$
\mathcal { N } _ { I J } = F _ { I J } + 2 i \frac { ( \mathrm { I m } F \cdot X ) _ { I } ( \mathrm { I m } F \cdot X ) _ { J } } { X \cdot \mathrm { I m } F \cdot X }
$$

where $F _ { I J } = \partial _ { I } \partial _ { J } F ( X )$

After reduction on the time-like isometry,the action is $\begin{array} { r } { S = - \frac { 1 } { 8 \pi } \int d t \int d ^ { 3 } { \bf x } \mathcal { L } } \end{array}$ .The 3D lagrangian $\mathcal { L }$ has three parts: $\pmb { \mathcal { L } } = \pmb { \mathcal { L } } _ { g r a v i t y } + \pmb { \mathcal { L } } _ { m o d u l i } + \pmb { \mathcal { L } } _ { e . m }$ where

$$
\begin{array} { r c l } { r a v i t y } & { = } & { \displaystyle - \frac { 1 } { 2 } \sqrt { \mathbf { g } } \ \mathbf { R } + \mathbf { d } U \wedge \ast \mathbf { d } U - \frac { 1 } { 4 } e ^ { 4 U } \mathbf { d } \omega \wedge \ast \mathbf { d } \omega } \\ { m o d u l } & { = } & { g _ { i \bar { j } } \mathbf { d } z ^ { i } \wedge \ast \mathbf { d } \bar { z } ^ { \bar { j } } } \\ { \mathcal { L } _ { e . m . } } & { = } & { \displaystyle \frac { 1 } { 2 } e ^ { - 2 U } ( I m \mathcal { N } ) _ { I J } \mathbf { d } A _ { 0 } ^ { I } \wedge \ast \mathbf { d } A _ { 0 } ^ { J } + \frac { 1 } { 2 } e ^ { 2 U } ( I m \mathcal { N } ) _ { I J } ( \mathbf { d } \mathbf { A } ^ { I } + A _ { 0 } ^ { I } \mathbf { d } \omega ) \wedge \ast ( \mathbf { d } \mathbf { A } ^ { J } \mathbf { d } \omega ) } \\ & { } & { \displaystyle + ( R e \mathcal { N } ) _ { I J } \mathbf { d } A _ { 0 } ^ { I } \wedge ( \mathbf { d } \mathbf { A } ^ { J } + A _ { 0 } ^ { J } \mathbf { d } \omega ) } \end{array}
$$

The dual scalars for $\omega$ and $\mathbf { A } ^ { I }$ are defined by:

$$
\begin{array} { r l r } { e ^ { 2 U } ( I m \mathcal { N } ) _ { I J } * ( \mathbf { d A } ^ { J } + A _ { 0 } ^ { J } \mathbf { d } \omega ) + ( R e \mathcal { N } ) _ { I J } \mathbf { d } A _ { 0 } ^ { J } } & { = } & { - \mathbf { d } \phi _ { \mathbf { A } ^ { I } } } \\ { e ^ { 4 U } * \mathbf { d } \omega + ( A _ { 0 } ^ { I } \mathbf { d } \phi _ { \mathbf { A } ^ { I } } - \phi _ { \mathbf { A } ^ { I } } \mathbf { d } A _ { 0 } ^ { I } ) } & { = } & { - \mathbf { d } \phi _ { \omega } } \end{array}
$$

After renaming the variables $\phi _ { \omega }  \sigma , A _ { 0 } ^ { I }  A ^ { I } , \phi _ { \bf A ^ { I } }  B _ { I }$ ，we obtain the 3d lagrangian in terms of scalars only:

$$
\begin{array} { r l } { { } } & { { = } } & { { \displaystyle - \frac { 1 } { 2 } \sqrt { \bf g \Lambda } { \bf R } + { \bf d } U \wedge { \bf * } { \bf d } U + \frac { 1 } { 4 } e ^ { - 4 U } ( { \bf d } \sigma + A ^ { I } { \bf d } B _ { I } - B _ { I } { \bf d } A ^ { I } ) \wedge { \bf * } ( { \bf d } \sigma + A ^ { I } { \bf d } B _ { I } - { \bf d } A ^ { I } { \bf d } { \bf d } { \bf d } { \bf d } { \bf d } { \bf d } { \bf d } { \bf d } - { \bf d } { \bf d } { \bf d } { \bf d } { \bf d } { \bf d } { \bf d } ^ { I } { \bf d } { \bf d } { \bf d } { \bf d } { \bf d } } } \\ { { } } &  { \displaystyle + g _ { i \bar { j } } ( z , \bar { z } ) { \bf d } z ^ { i } \wedge { \bf * { d } } \bar { z } ^ { \bar { j } } + \frac { 1 } { 2 } e ^ { - 2 U } ( I m \mathcal { N } ) _ { I J } { \bf d } A ^ { I } \wedge { \bf * } { \bf d } A ^ { J } } \\ { { } } & { { \displaystyle + \frac { 1 } { 2 } e ^ { - 2 U } ( I m \mathcal { N } ^ { - 1 } ) ^ { I J } ( { \bf d } B _ { I } + ( R e \mathcal { N } ) _ { I K } { \bf d } A ^ { K } ) \wedge { \bf * } ( { \bf d } B _ { J } + ( R e \mathcal { N } ) _ { J L } { \bf d } A ^ { L } ) } } \\ { { } } & { { = } } & { { \displaystyle - \frac { 1 } { 2 } \sqrt { \bf g \Lambda } { \bf R } + g _ { m n } \partial _ { a } \phi ^ { m } \partial ^ { a } \phi ^ { n } } } \end{array}
$$

where, as before, $\phi ^ { n }$ are the $4 ( n _ { V } + 1 )$ moduli fields: $\phi ^ { n } = \{ U , z ^ { i } , \bar { z } ^ { \bar { i } } , \sigma , A ^ { I } , B _ { I } \}$ ，and $\mathbf { g } _ { a b }$ is the space time metric, $g _ { m n }$ is the moduli space metric. Therefore, the moduli space $\mathcal { M } _ { 3 D }$ （20 has metric:

$$
\begin{array} { l l l } { { \displaystyle \mathrm {  ~ \Omega ~ } ^ { 2 } ~ } = } & { { \displaystyle { \bf d } U \cdot { \bf d } U + \frac { 1 } { 4 } e ^ { - 4 U } ( { \bf d } \sigma + A ^ { I } { \bf d } B _ { I } - B _ { I } { \bf d } A ^ { I } ) \cdot ( { \bf d } \sigma + A ^ { I } { \bf d } B _ { I } - B _ { I } { \bf d } A ^ { I } ) + g _ { i \overline { { { j } } } } } } \\ { { } } & { { } } & { { \displaystyle + \frac { 1 } { 2 } e ^ { - 2 U } [ ( I m \mathcal { N } ^ { - 1 } ) ^ { I J } ( { \bf d } B _ { I } + \mathcal { N } _ { I K } { \bf d } A ^ { K } ) \cdot ( { \bf d } B _ { J } + \overline { { { \mathcal { N } } } } _ { J L } { \bf d } A ^ { L } ) ] } } \end{array}
$$

It is a para-quaternionic-Kähler manifold. Since the holonomy is reduced from $S O ( 4 n _ { V } +$ 4)）to $S p ( 2 , \mathbb { R } ) \times S p ( 2 n _ { V } + 2 , \mathbb { R } )$ ，the vielbein has two indices $( \alpha , A )$ transforming under $S p ( 2 , \mathbb { R } )$ and $S p ( 2 n _ { V } + 2 , \mathbb { R } )$ ， respectively. The para-quaternionic vielbein is the analytical continuation of the quaternionic vielbein computed in [34]:

$$
V ^ { \alpha A } = \left( \begin{array} { c c } { { i u } } & { { v } } \\ { { e ^ { a } } } & { { i E ^ { a } } } \\ { { - i \bar { E } ^ { \bar { a } } } } & { { \bar { e } ^ { \bar { a } } } } \\ { { - \bar { v } } } & { { i \bar { u } } } \end{array} \right)
$$

The 1-forms are defined as

$$
\begin{array} { r c l } { { u } } & { { \equiv } } & { { e ^ { K / 2 - U } X ^ { I } ( { \bf d } B _ { I } + \mathcal { N } _ { I J } d A ^ { J } ) } } \\ { { e ^ { a } } } & { { \equiv } } & { { e _ { i } ^ { a } { \bf d } z ^ { i } } } \\ { { E ^ { a } } } & { { \equiv } } & { { e ^ { - U } e _ { i } ^ { a } g ^ { i \bar { j } } e ^ { K / 2 } \bar { D } _ { \bar { j } } X ^ { I } ( { \bf d } B _ { I } + \mathcal { N } _ { I J } { \bf d } A ^ { J } ) } } \\ { { v } } & { { \equiv } } & { { - { \bf d } U + \displaystyle \frac { i } { 2 } e ^ { - 2 U } ( { \bf d } a + A ^ { I } { \bf d } B _ { I } - B _ { I } { \bf d } A ^ { I } ) } } \end{array}
$$

where $e _ { i } ^ { u }$ is the veilbein of the 4D moduli space, and the bar denotes complex conjugate. The line element is related to the vielbein by

$$
d s ^ { 2 } = - u \cdot \bar { u } + g _ { a \bar { b } } e ^ { a } \cdot \bar { e } ^ { \bar { b } } - g _ { a \bar { b } } E ^ { a } \cdot \bar { E } ^ { \bar { b } } + v \cdot \bar { v } = \epsilon _ { \alpha \beta } \epsilon _ { A B } V ^ { \alpha A } \otimes V ^ { \beta B }
$$

where $\epsilon _ { \alpha \beta }$ and $\epsilon _ { A B }$ are the anti-symmetric tensors invariant under $S p ( 2 , \mathbb { R } ) \cong S L ( 2 , \mathbb { R } )$ and $S p ( 2 n _ { v } + 2 , \mathbb { R } )$

The isometries of the $\mathcal { M } _ { 3 D } ^ { * }$ descends from the symmetry of the 4D system. The gauge symmetries in 4D gives the shifting isometries of $\mathcal { M } _ { 3 D } ^ { * }$

$$
\begin{array} { r c l } { { } } & { { } } & { { A ^ { I } \begin{array} { c } { { } } \end{array} \longrightarrow \begin{array} { c } { { A ^ { I } + \Delta A ^ { I } } } \end{array} } } \\ { { } } & { { } } & { { B _ { I } \begin{array} { c } { { } } \end{array} \longrightarrow \begin{array} { c } { { B _ { I } + \Delta B _ { I } } } \end{array} } } \\ { { \sigma } } & { { \longrightarrow \begin{array} { c } { { \sigma + \Delta \sigma + \Delta B _ { I } A ^ { I } - \Delta A ^ { I } B _ { I } } } \end{array} } } \end{array}
$$

The conserved currents and charges are given by (4.5) and the discussion thereafter.

# References

[1] S. Ferrara， R. Kallosh and A. Strominger， Phys. Rev. D 52， 5412 (1995) [arXiv:hep-th/9508072].   
[2] S.Ferrara，G. W. Gibbons and R. Kallosh， Nucl. Phys. B 500，75 (1997) [arXiv:hep-th/9702103]. [3] R.Kallosh， N. Sivanandam and M. Soroush， JHEP O603， O60(2006) [arXiv:hep-th/0602005].   
[4] K.Goldstein, N. Iizuka,R. P. Jena and S. P. Trivedi, Phys. Rev.D 72,124021 (2005) [arXiv:hep-th/0507096].   
[5] L. Andrianopoli, R. D'Auria, S. Ferrara and M. Trigiante, arXiv:hep-th/O611345.   
[6]R.D'Auria,_S.FerraraandM.Trigiante,JHEP0703，097(2007) [arXiv:hep-th/0701090].   
[7] A.Dabholkar, A. Sen and S. P. Trivedi, JHEP 0701, 096 (2007) [arXiv:hep-th/0611143].   
[8] K. Saraikin and C. Vafa, arXiv:hep-th/0703214.   
[9] P.K. Tripathy and S. P. Trivedi, JHEP 0603,022 (2006) [arXiv:hep-th/0511117].   
[10] S. Nampuri, P. K. Tripathy and S. P. Trivedi, arXiv:0705.4554 [hep-th].   
[11] A. Sen, JHEP 0509,038 (2005)[arXiv:hep-th/0506177].   
[12] B. Sahoo and A. Sen, JHEP 0701, 010 (2007) [arXiv:hep-th/0608182].   
[13] D. Astefanesei, K. Goldstein, R. P. Jena, A. Sen and S. P. Trivedi, JHEP O610,058 (2006）[arXiv:hep-th/0606244].   
[14] B. Sahoo and A. Sen, JHEP 0609, 029 (2006) [arXiv:hep-th/0603149].   
[15] B. Chandrasekhar, S. Parvizi, A. Tavanfar and H. Yavartanoo, JHEP O608, O04 (2006) [arXiv:hep-th/0602022].   
[16] M.Alishahiha and H. Ebrahim, JHEP 0603, 003 (2006) [arXiv:hep-th/0601016].   
[17] A. Sen, JHEP 0603,008 (2006)[arXiv:hep-th/0508042].   
[18] B. Bates and F. Denef, arXiv:hep-th/0304094.   
[19] R.Kallosh，N. Sivanandam and M. Soroush，Phys. Rev. D 74，065008 (2006) [arXiv:hep-th/0606263].   
[20] G. Lopes Cardoso,A. Ceresole, G. Dall'Agata, J. M. Oberreuter and J. Perz, JHEP 0710,063 (2007)[arXiv:0706.3373 [hep-th].   
[21] A. Ceresole and G. DallAgata, JHEP 0703,110 (2007) [arXiv:hep-th/0702088].   
[22] P.Breitenlohner，D. Maison and G.W.Gibbons,Commun. Math. Phys.120， 295 (1988).   
[23] M. Cvetic and D. Youm, Nucl. Phys. B 472, 249 (1996) [arXiv:hep-th/9512127].   
[24] M. Cvetic and D. Youm, Nucl. Phys. B 476,118 (1996) [arXiv:hep-th/9603100].   
[25] M. Gunaydin,A. Neitzke, B. Pioline and A. Waldron, Phys. Rev. D 73, 084019 (2006) [arXiv:hep-th/0512296].   
[26] A. Neitzke, B. Pioline and S. Vandoren, JHEP 0704, 038 (2007) [arXiv:hep-th/0701214].   
[27] C. M. Hull and B. Julia, Nucl. Phys. B 534, 250 (1998) [arXiv:hep-th/9803239].   
[28] A. Bouchareb, G. Clement, C. M. Chen, D. V. Gal'tsov, N. G. Scherbluk and T. Wolf, Phys. Rev. D 76,104032 (2007) [arXiv:0708.2361 [hep-th]].   
[29] G. Clement,arXiv:0710.1192 [gr-qc].   
[30] M. Gunaydin,A. Neitzke, O. Pavlyk and B. Pioline,arXiv:0707.1669 [hep-th].   
[31] B. de Wit，F. Vanderseypen and A. Van Proeyen， Nucl. Phys.B 400,463(1993) [arXiv:hep-th/9210068].   
[32] A. Ceresole, R. D'Auria and S. Ferrara, Nucl. Phys. Proc. Suppl. 46, 67 (1996) [arXiv:hep-th/9509160].   
[33] B. Pioline, Class. Quant. Grav. 23, S981 (2006) [arXiv:hep-th/0607227].   
[34] S. Ferrara and S. Sabharwal, Nucl. Phys. B 332, 317 (1990).   
[35] K.Behrndt,R. Kallosh, J. Rahmfeld, M. Shmakova and W. K. Wong, Phys.Rev. D 54,6293 (1996) [arXiv:hep-th/9608059].