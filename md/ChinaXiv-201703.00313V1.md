# Linear interpolation of shape operators for umbilical points via local parameterization

WuJun Che\* InstituteofAutomation,CAS,Beijingl0o19o,P.R.China

# Abstract

Principalcurvaturesand principaldirectionsareexploitedubiquitouslyinshapeanalysis.Onone hand,umbilicalpointsseverely hindertheanalysisasthesingularitiesinthevectorfeldof principaldirections;ontheotherhand,providingshape-intrinsic qualitativeinformationabout asurface,theyaredesirablequantities insomeapplications.Umbilical points are fundamental for geometricanalysis,buttheiraccratecomputationonadscretesurfaceisstllchallenging.Intispaper,wedevelopasmplend ffective method todetectumbilicalpointsonatrangle mesh,inwhichanyparametrization works.Inparticular,we propose two practical processes forlocalparametrizationbyorthogonall projectingorconforally transformingthe matrix ontoaspecified parametric plane.Furthermore,we make a systematic analysis on our method and demonstrate its convergence behavior.The algorithm of our approach is flexible and easy to implement for a triangular mesh of arbitrary topology.

Keywords:Lieariterpolation,Localparametezation,Principalurature,Principaldirection,apeoperatorUbialpi

# 1.Introduction

Principal curvatures and their corresponding directions are basic entities for shape analysis because they entirely exhibit the variation of curvature across a smooth two-manifold surface in a three-dimensional Euclidean space.Their calculation is a fundamental issue for enormous geometric applications in many aspects such as shape retrieval, shape registration, surface remeshing,surface segmentation, and shape design.

Anumbilical pointis a singularity with anomalous behavior in the vector field of principal directions.It is of theoretical interest because lines of curvature,which integrate the field,become complicated near it. In applications favoring the orthogo nality of the field,such as feature-aligned remeshing[1,9], umbilical points make waves;we have to isolate them by design so as to deal with them separately.Umbilical points are invariant features of the surface's differential structure,acting like fingerprints across the surface [1O];hence,their reliable determination is also significant for quantitative analysis in other settings, such as for describing or identifying objects [16],shape interrogation[13], ship-hull design and progressive additional lens design [17].Although a wealth of estimators for differential quantities have been proposed in the vast literature of discrete geometry,the literature lacks a critical examination regarding how to detect umbilical points over a mesh as opposed to a smooth surface.

The purpose of this work is to investigate a mathematically sound and computationally efficient approach to umbilical point detection over a mesh model of arbitrary topology. The remainder of this paper is organized as follows.In the next section,a summary of related work and their mathematical background are provided on the numerical computation of umbilical points over a mesh.In Section 3 mathematical preliminaries in classical differential geometry are described concerning the characteristics of umbilical points and shape operators；and then the theoretical foundation of our method is developed to linearly interpolate the shape operators for umbilical points.We propose our algorithms to re-formulate shape operators by a local transformation onto a parameter plane to facilitate the linear interpolation of shape operators in Section 4. Section 5 presents a unified error analysis on our method. The last two sectionS present some experimental results with discussion and then conclude the paper, respectively.

# 2.Previous work

Umbilical points have been studied intensively.We shall restate those work from the view point of numerical computation. Interested readers can refer to [5,12,13,16] and references therein formore details.

In the following text,a bold uppercase letter represents a matrix and a bold lowercase letter represents a column vector.

# 2.1．An umbilical point

Given a unit normal vector at a point $\mathbf { p }$ on a smooth surface,a normal plane at $\mathbf { p }$ is one that contains the normal and therefore also contains a unique direction tangent to the surface,cuting the surface in a plane curve. This curve usually has different curvature for different normal planes at p. The two principal curvatures at $\mathbf { p }$ ,denoted as $\kappa _ { 1 }$ and $\kappa _ { 2 }$ ,are the maximal and minimal values,respectively. The pioneering Swiss mathematician,LeonhardEuler,first discovered that thetwo principal directions of $\alpha _ { 1 }$ and $\alpha _ { 2 }$ at $\mathbf { p }$ ,corresponding to the tan gent directions realizing $\kappa _ { 1 }$ and $\kappa _ { 2 }$ ，respectively,are mutually perpendicular. The normal curvature $\kappa _ { n }$ in the tangent direction making an angle $\theta$ with $\alpha _ { 1 }$ is characterized by the well-known Euler's formula:

$$
\kappa _ { n } ( \theta ) = \kappa _ { 1 } \cos ^ { 2 } \theta + \kappa _ { 2 } \sin ^ { 2 } \theta
$$

If $\boldsymbol { \kappa } _ { 1 } = \boldsymbol { \kappa } _ { 2 }$ , however, $\kappa _ { n }$ in all directions is the same; this point is called an umbilical point and each direction is principal. Umbilical points exhibit special properties and their computation is an important topic in shape analysis.Two commonly used approaches are related to two properties of umbilical points, respectively:

1.In classical differential geometry, an umbilical point is defined as a point where $\kappa _ { 1 }$ and $\kappa _ { 2 }$ are equal. A trivial algorithm to locate an umbilical point is to locally minimize $f = | { \boldsymbol { \kappa } } _ { 1 } - { \boldsymbol { \kappa } } _ { 2 } |$ ata vertex against other vertices adjacent to it,or,to have the ratio of $\kappa _ { 1 }$ and $\kappa _ { 2 }$ larger than a threshold [9]. Its equivalent form of $g = \kappa _ { M } ^ { 2 } - \kappa _ { G }$ is more frequently exploited in practice,where $\kappa _ { M } = ( \kappa _ { 1 } + \kappa _ { 2 } ) / 2$ is the mean curvature and $\begin{array} { r } { \kappa _ { G } = \kappa _ { 1 } \kappa _ { 2 } } \end{array}$ the Gaussian curvature. Because the notion of continuous geometric attributes on a smooth surface do not match those on its piecewise linear counterpart (more or less),it is uncommon to determine an umbilical point by $f$ or $g$ alone on a sampled surface.This method is more widelyutilized for an analytical surface on which numerical optimization can be performed to situate an umbilical point accurately.For instance,a method was proposed in[12,13] for a free-form surface by solving a system of polynomial equations.For an implicit surface, novel evaluationfunctions and numerical algorithms have been developed to extract umbilical points in [20].

2．Another common method is based on the index of principal direction field at a specified point $\mathbf { p }$ The index of an umbilical point describes the way the lines of curvature turn around the umbilical point and can be computed by:

$$
{ \frac { 1 } { 2 \pi } } \oint \nabla \theta ( \mathbf { c } ) \cdot d \mathbf { c }
$$

where $\theta$ is the angle through which the coordinate axes wouldhave to berotated to align them with the local principal axes at $\mathbf { p }$ [2]. The integral is taken over a small counterclockwise circuit c around $\mathbf { p }$ .In implementation,the computation is simplified by pulling the field back onto the tangent plane at $\mathbf { p }$ and computing the circuit there [13,16]:

$$
\frac { 1 } { 2 \pi } \oint _ { \mathbf { c } } d \theta
$$

where $\theta$ is the angle between a direction of the field and some fixed direction in the parametric plane.The integral is now taken going around the circuit c around $\mathbf { p }$ but in the plane.

The index of a generic umbilical point is either of index $- { \frac { 1 } { 2 } }$ or of index $+ { \frac { 1 } { 2 } }$ . Thus this method provides a conclusive test for an umbilical point. If the index is zero no umbilical point is present.

# 2.2.Linear interpolation for an umbilical point

Localizing an umbilical point is more than just a matter of evaluating $\left| \kappa _ { 1 } - \kappa _ { 2 } \right|$ or calculating the index.Because it is likely that the actual umbilical point will fall between the sampling points,the structure of the principal direction field should be taken into account [16]. A method by linearly interpolating some quantities at vertices of a geometric primitive — for example,a triangle overa mesh — is being sought to yield an umbilical point.

In a 2D symmetric tensor field $\mathbf { T }$ of type $2 { \times } 2$ ,the location of a singular point on a discrete grid is reduced to an interpolating point of zero using bilinear interpolation of the tensor-matrix components between the grid vertices [6]; later generalized to linear interpolation within each triangle △abc by solving a linear system of $\mathbf { T }$ [18]:

$$
x \mathbf { D _ { a } } + y \mathbf { D _ { b } } + ( 1 - x - y ) \mathbf { D _ { c } } = \mathbf { 0 }
$$

where the deviator part $\mathbf { D }$ of $\mathbf { T }$ is defined as $\mathbf { D } = \mathbf { T } - { \textstyle { \frac { 1 } { 2 } } } t r ( \mathbf { T } ) \mathbf { E }$ here $\mathbf { E }$ is an identity matrix of $2 \times 2$

This method is then employed in remeshing for an umbilical point over a triangular mesh by flattening it to a 2D parametric plane and by interpolating the curvature tensor[1].Fora parametric surface,linear interpolation of curvature tensors in the parametric domain is advantageous to fixing an umbilical point insidea primitive cell rather than only ona vertexas the former two do. Their practice,however, has to rely ona globally conformal parameterization of the mesh in order for symmetrical curvature tensors in the parametric domain.Parameterization is a central issue in computer graphics and it is a nontrivial task to obtain a conformal one.Furthermore,a parametrization is not indispensable in most applications.Needless to say, the global parametrization requires the mesh surface to be equal to a planar disk or a planar square in topology;additional errors will be produced in the parametrization, too.

How to estimate an umbilical point with a local parameterization is the key to popularizing the method through linearly interpolating certain quantities at vertices ofa geometric primitive. The contributions in this work is such a novel method of local computation for umbilical points on a triangular mesh. It significantly frees the interpolation from both symmetrical tensors and conformal parameterization so that the underlying surface is of arbitrary topology. We also carry out a mathematical analysis on it by examining its numerical and convergence behaviors of estimating an umbilical point on a discrete mesh surface — a method that has not yet appeared in the extant literature.

# 3.Mathematical preliminaries

Although our method can be portrayed compactly, its mathematics does not described explicitly in the literature.To provide a practical foundation,a brief review of some important mathematical preliminaries related to the algorithmis in order.

# 3.1.Background of differential geometry

We summarize the relevant definitions and results about lines of curvature on a parametric surface to depict our method. Differential geometry in parametric representation has been developed richly,and most facts can be found ina standard textbook on classical differential geometry when proofs are not given explicitly.

Given a variable vector $\mathbf { u } = [ u , \nu ] ^ { T }$ , in which $u$ and $\nu$ are local curvilinear coordinates,a vector-valued parameterized surface in terms of $\mathbf { u }$ is represented as

$$
\mathbf { r } ( \mathbf { u } ) = \left[ x ( u , \nu ) , y ( u , \nu ) , z ( u , \nu ) \right] ^ { T }
$$

If $\mathbf { r }$ is regular, $\mathbf { r } _ { u }$ and ${ \bf r } _ { \nu }$ are linearly independent and form a basis of the tangent plane at $\mathbf { r } ( \mathbf { u } )$ . The shape operator S for $\mathbf { r } ( \mathbf { u } )$ is:

$$
\begin{array} { r c l } { \mathbf { S } = \mathbf { I } ^ { - 1 } \mathbf { I I } } & { = } & { \left[ \begin{array} { l l } { S _ { 1 1 } } & { S _ { 1 2 } } \\ { S _ { 2 1 } } & { S _ { 2 2 } } \end{array} \right] } \\ & { = } & { \displaystyle \frac { 1 } { d e t ( \mathbf { I } ) } \left[ \begin{array} { l l } { G L - F M } & { G M - F N } \\ { E M - F L } & { E N - F M } \end{array} \right] } \end{array}
$$

$$
{ \begin{array} { r l } & { { \mathrm { ~ w h e r e ~ } } \mathbf { I } = { \left[ \begin{array} { l l } { E } & { F } \\ { F } & { G } \end{array} \right] } = { \left[ \begin{array} { l l } { \mathbf { r } _ { u } \cdot \mathbf { r } _ { u } \quad \mathbf { r } _ { u } \cdot \mathbf { r } _ { \nu } } \\ { \mathbf { r } _ { u } \cdot \mathbf { r } _ { \nu } \quad \mathbf { r } _ { \nu } \cdot \mathbf { r } _ { \nu } } \end{array} \right] } { \mathrm { ~ a n d ~ } } \mathbf { I I } = { \left[ \begin{array} { l l } { L } & { M } \\ { M } & { N } \end{array} \right] } } \\ & { { \left[ \begin{array} { l l } { \mathbf { n } \cdot \mathbf { r } _ { u u } \quad \mathbf { n } \cdot \mathbf { r } _ { u \nu } } \\ { \mathbf { n } \cdot \mathbf { r } _ { u \nu } \quad \mathbf { n } \cdot \mathbf { r } _ { \nu \nu } } \end{array} \right] } { \mathrm { ~ a r e ~ t h e ~ m a t r i c e s ~ o f ~ t h e ~ f i r s t ~ a n d ~ s e c o n d ~ f u n - } } } \\ & { { \mathrm { ~ d o . } } \mathbf { r } _ { \nu \times \nu \times 2 } { \mathrm { ~ i s ~ } } _ { \nu \times \nu } { \mathrm { ~ a . ~ k . . . ~ k . . ~ } } { \mathrm { ~ a s . ~ r . . ~ } } \quad \mathbf { r . } _ { \nu \times \nu \times 2 } { \mathrm { ~ a . ~ r . . . ~ r . . ~ } } \quad \mathbf { r . } \quad } \end{array} }
$$

damental forms in the basis $\mathbf { r } _ { u }$ and $\mathbf { r } _ { \nu }$ ,respectively; $\mathbf { n }$ is the unit normal vector.

A basic property of the shape operator is $\mathbf { S } \alpha _ { i } = \kappa _ { i } \alpha _ { i } , i =$ $^ { 1 , 2 }$ ,where $\kappa _ { i }$ and $\alpha _ { i }$ are the principal curvatures and the corresponding principal directions.

The differential equation of lines of curvature in coordinates is given by

$$
U d u ^ { 2 } + V d u d \nu + W d \nu ^ { 2 } = 0
$$

where $U = E M - F L$ ， $V = E N - G L$ ,and $W = F N - G M$

Therefore,we havea well-known result of an umbilical point in classical differential geometry:

Lemma 3.1. $\mathbf { r } ( \mathbf { u } )$ is an umbilical point if andonlyif $U = V =$ $W = 0$ at u.

It seems that $U = V = W = 0$ are over-determined to situate an umbilical point;nevertheless,they are not independent,as shown by the following corollary:

Corollary 3.2. $\mathbf { r } ( \mathbf { u } )$ is an umbilical point if and only ij $\boldsymbol { c } \left\{ \begin{array} { l l } { V = 0 } \\ { U - W = 0 _ { 3 } } \end{array} \right.$ at u.

$$
\begin{array} { r } { \left\{ \begin{array} { l } { V = 0 } \\ { U - W = 0 } \end{array} \right. \Leftrightarrow \left\{ \begin{array} { l } { \frac { L } { E } = \frac { N } { G } } \\ { \frac { M } { F } = \frac { L + N } { E + G } } \end{array} \right. \Leftrightarrow \frac { L } { E } = \frac { M } { F } = \frac { N } { G } \Leftrightarrow } \\ { = W = 0 } \end{array}
$$

Remark 3.3. In the sketch proof of Corollary 3.2，we use a concentrated notion of $\begin{array} { r } { \frac { L } { E } = \frac { M } { F } = \frac { N } { G } } \end{array}$ for the sake of a compact proof.It infersa presupposition that Mmust be zero ifFis zero forthisequationto hold.Areadercanexamine thatitdoes not affect the whole validity of the proof.We should also note that both $E$ and $G$ are always positive numbers for a regular r.

Corollary 3.2 is inconvenient to characterize an umbilical point in numerical computation for a discrete mesh model. Instead, defining $\mathbf { t } = [ S _ { 1 1 } - S _ { 2 2 } , S _ { 1 2 } + S _ { 2 1 } ] ^ { T }$ ,a more intuitive and practical condition can be derived for this purpose, say:

Lemma 3.4. $\mathbf { p }$ is an umbilical point if and only $i f \mathbf { t } = \mathbf { 0 }$

PROOF. $\textbf { t } = \textbf { 0 } \Leftrightarrow \left\{ \begin{array} { l l } { S _ { 1 1 } - S _ { 2 2 } = 0 } \\ { S _ { 1 2 } + S _ { 2 1 } = 0 } \end{array} \right. \Leftrightarrow \left\{ \begin{array} { l l } { V = 0 } \\ { U - W = 0 } \end{array} \right.$ U-W=0· We verify this lemma immediately following from Corollary 3.2.

To the best of our knowledge,Lemma 3.4 is not described explicitly in the literature.Its power will be reflected by our new algorithm to compute umbilical points over a two-manifold mesh model with arbitrary topology.

# 3.2.Linear interpolation of shape operators for umbilical points

In this subsection,we further give an essential link that exists between a shape operator and a curvature tensor under a conformal parameterization. We then develop a novel approach to linear interpolation based on shape operators for umbilical points rather than curvature tensors,which can relax the restriction of the symmetry of shape operators as opposed to curvature tensors.

# 3.2.1.A shape operator and a curvature tensor

In contrast to a shape operator, $\boldsymbol { \kappa } _ { i }$ and $\alpha _ { i }$ $( i = 1 , 2 )$ together are also thought of as the curvature tensor $\begin{array} { r } { \mathbf { C } = \kappa _ { 1 } \alpha _ { 1 } \boldsymbol { \alpha } _ { 1 } ^ { T } + \kappa _ { 2 } \alpha _ { 2 } \boldsymbol { \alpha } _ { 2 } ^ { T } } \end{array}$ in the computer graphics community. The tensor field $\mathbf { T }$ in Eq.(3) is set as C for umbilical points,but C must be symmetrical,which is too strict to exploit in applications.Because both S and C are closely related to $\boldsymbol { \kappa } _ { i }$ and $\alpha _ { i }$ ， $i = 1 , 2$ ，there must be a connection between them and a well-founded thought is to replace $\mathbf { C }$ with S so as to take full advantage of shape operators, which have been well studied in differential geometry.

The following proposition reveals the relationship between S and C:

Proposition 3.5. $\mathbf { C } = \mathbf { S }$ if both are represented in conformal curvilinearcoordinates.

PROOF. Let $( u , \nu )$ be conformal coordinates. $\alpha _ { 1 }$ and $\alpha _ { 2 }$ are unit vectors of principal directions in coordinates.Because $\alpha _ { 1 } \cdot \alpha _ { 2 } =$ 0, $\alpha _ { 1 } \alpha _ { 1 } ^ { T } + \alpha _ { 2 } \alpha _ { 2 } ^ { T } = { \bf E }$ holds.Thus ${ \bf C } = \kappa _ { 1 } \alpha _ { 1 } \alpha _ { 1 } ^ { T } + \kappa _ { 2 } \alpha _ { 2 } \alpha _ { 2 } ^ { T } =$ $\mathbf { S } \left( \alpha _ { 1 } \alpha _ { 1 } ^ { T } + \alpha _ { 2 } \alpha _ { 2 } ^ { T } \right) = \mathbf { S } .$

# 03.2.2. A new method for umbilical points

Lemma 3.4 and Proposition 3.5 imply not only that Eq.(3) can be simplified by t, but that it can also be applied to any parameterization so as to free S from symmetry, namely there being $( x , y ) \in [ 0 , 1 ] \times [ 0 , 1 ]$ and $x + y \leqslant 1$ fora triangle of△abc such that

$$
x \mathbf { t _ { a } } + y \mathbf { t _ { b } } + ( 1 - x - y ) \mathbf { t _ { c } } = \mathbf { 0 }
$$

We call $\triangle$ abc meeting Eq.(5) as a zero-crossing triangle. A triangle containing an umbilical point is called an umbilical

triangle.A zero-crossing triangle is unnecessarily an umbilical triangle in practical compuation.

We shall continue the numerical analysis on Eq.(5) and illustrate more of its behaviors by experiments later — in Sections 5 and7, respectively.

# 4.Finding a zero-crossing triangle

Given a mesh model,a great many methods have been developed to derive the principal curvatures and directions at each vertex[7,19]. In this section,we develop a local parameterization of high efficiency to synthesize the estimated principal curvatures and principal directions to be shape operators consistently ina coordinate system.

# 4.1.Overview of the method

Suppose principal curvatures and principal directions, i.e. shape operators at their respective frames,at vertices have been acquired by some means,either analytically or numerically. To depict our method,it suffices to carry out Eq.(5) on one triangle △abc of the mesh model. Now imagine a right-handed uvw coordinate system at a point $\mathbf { p } _ { 0 }$ inside △abcwith $w$ -axisparallel to the normal to △abc. We have a demand to project shape operators of a, $\mathbf { b }$ and c onto the $u \nu$ plane,respectively. Once theyare determined, interpolationis performed via Eq.(5). The resultant interpolating umbilical point is calculated as $x { \mathbf { a } } + y { \mathbf { b } } +$ $( 1 - x - y ) \mathbf { c }$

The rest of the issues involves projecting relevant shape operators to the parametric domain on △abc.We shall portray our method to parameterize a shape operator locally for this purpose in the next subsection.

# 4.2. Local parameterization of S

We here illustrate the concrete implementations of our method with two local parameterizations.

# 4.2.1. Local orthogonal projection

We choose uvw-coordinates so that a point on the surface is at the origin and so that the three axes are the principal directions and normal, respectively. The surface is then expressible in Monge form as

$$
w = \frac { 1 } { 2 } ( { \kappa _ { 1 } } u ^ { 2 } + { \kappa _ { 2 } } { \nu ^ { 2 } } ) + \frac { 1 } { 6 } ( { b _ { 0 } } { u ^ { 3 } } + 3 { b _ { 1 } } u ^ { 2 } \nu + 3 { b _ { 2 } } u { \nu ^ { 2 } } + { b _ { 3 } } { \nu ^ { 3 } } ) + O ( { \bf { u } } ) ^ { 4 } ( 6 )
$$

in which $O ( { \bf u } ) ^ { 4 }$ is aPeano remainder.

For each vertex of the mesh,the Monge form in its neighborhood can be established numerically and uniquely to degree 2 by estimating its normal, principal directions and principal curvatures from a set of near-neighbor vertices.However, the shape operators of two distinct vertices cannot be put into arithmetical operation directly because they are obtained separately and measured in their respective frames.To reconcile them to a consistent frame, the Monge forms need to be reshaped in a common parametric domain. Given a local xyz coordinate system at $\mathbf { p } _ { 0 }$ and a Monge form in the local uvw coordinate system at $\mathbf { p } _ { k }$ as shown in Fig.1,we intend to re-parameterize $\mathbf { S } \vert _ { \mathbf { p } _ { k } }$ from in the frame $\mathbf { p } _ { k } – u \nu \boldsymbol { w }$ to in the frame $\mathbf { p } _ { 0 }$ -xyz. As described in Section 3.1, S is computable by setting $\mathbf { r } ( \mathbf { x } ) = [ x , y , z ] ^ { T }$ if $J _ { \mathbf { x } } ( z )$ and $H _ { \mathbf { x } } ( z )$ are computable,where $J _ { \mathbf { x } } ( z )$ and $H _ { \mathbf { x } } ( z )$ are the Jacobian and the Hessian matrices of $z$ in terms of $\mathbf { x }$ ,respectively.

![](images/1cf30e6787c05a6f3cff3efdcaec55152a4c580c15b576174b1c6f0b286a502f.jpg)  
Figure 1: Coordinate transformation for local parameterization of S.Frame $\mathbf { p } _ { k }$ uvw is a Monge frame at $\mathbf { p } _ { k }$ to be re-parameterized. $\overline { { \mathbf { p } } } _ { k }$ is the projection of $\mathbf { p } _ { k }$ on the xy plane.

Let $\mathbf { e } _ { 1 } , \mathbf { e } _ { 2 }$ ，and $\mathbf { e } _ { 3 }$ be the unit vectors in the frame $ { \mathbf { p } } _ { 0 } \not { p } \scriptscriptstyle { - } x \ y z$ along the positive directions of the $x , y$ ,and $z$ axes,respectively; $\bar { \mathbf { e } } _ { 1 } , \bar { \mathbf { e } } _ { 2 }$ ，and $\bar { \bf e } _ { 3 }$ are those of the $u , \nu$ ，and $w$ axes,respectively,as displayed in Fig. 1. Let $a _ { i j } = { \bf e } _ { i } { \cdot } \bar { \bf e } _ { j } , b _ { i } = ( { \bf p } _ { k } { - } { \bf p } _ { 0 } ) { \cdot } { \bf e } _ { i } , i , j = 1 , 2 , 3 .$ and $\mathbf { U } = [ u , \nu , w ] ^ { T }$ ， $\mathbf { X } = [ x , y , z ] ^ { T }$ . We have

$$
\mathbf { X } = \left[ a _ { i j } \right] _ { 3 \times 3 } \mathbf { U } + [ b _ { i } ] _ { 3 \times 1 }
$$

Let $\mathbf { a } = [ a _ { 1 2 } , a _ { 1 1 } ] ^ { T }$ ， $\mathbf { b } = [ a _ { 2 2 } , a _ { 2 1 } ] ^ { T }$ ， $\mathbf { c } = [ a _ { 2 3 } , a _ { 1 3 } ] ^ { T }$ ， $\mathbf { A } =$ $[ \mathbf { b } , - \mathbf { a } ] , \mathbf { B } = \left[ \begin{array} { l l } { a _ { 1 1 } } & { a _ { 1 2 } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } \end{array} \right] ^ { - 1 }$ and $\begin{array} { r } { \mathbf { K } = \left[ \begin{array} { c c } { \kappa _ { 1 } } & { 0 } \\ { 0 } & { \kappa _ { 2 } } \end{array} \right] . } \end{array}$ By elementary computation,we have

$$
{ \begin{array} { r l r l } { J _ { \mathbf { x } } ( \mathbf { u } ) } & { \cong } & { \mathbf { B } } \\ { H _ { \mathbf { x } } ( u ) } & { \cong } & { \operatorname* { d e t } ( [ \mathbf { c } , \mathbf { b } ] ) \operatorname* { d e t } ( \mathbf { B } ) ^ { 3 } \mathbf { A } ^ { T } \mathbf { K A } } \\ { H _ { \mathbf { x } } ( \nu ) } & { \cong } & { \operatorname* { d e t } ( [ \mathbf { a } , \mathbf { c } ] ) \operatorname* { d e t } ( \mathbf { B } ) ^ { 3 } \mathbf { A } ^ { T } \mathbf { K A } } \\ { J _ { \mathbf { x } } ( w ) } & { \cong } & { \mathbf { 0 } } \\ { H _ { \mathbf { x } } ( w ) } & { \cong } & { \mathbf { B } ^ { T } \mathbf { K B } } \end{array} }
$$

where $\cong$ means the evaluation is taken at $\mathbf { p } _ { k }$ (or $\overline { { \mathbf { p } } } _ { k }$ ，e.g $J _ { \mathbf { x } } ( w ) \vert _ { \mathbf { p } _ { k } } = \mathbf { 0 }$

According to $z = a _ { 3 1 } u + a _ { 3 2 } \nu + a _ { 3 3 } w$ in Eq.(7) and the resultant Eqs.(8)-(12),we eventually achieve $J _ { \mathbf { x } } ( z )$ and $H _ { \mathbf { x } } ( z )$ at $\bar { \mathbf { p } } _ { k }$ and thus Slpk ·

# 4.2.2. Local conformal transformation

Instead of orthogonally projecting them onto a parametric plane,we can flatten the matrices of shape operators onto the triangle plane by transforming the vertex frames to the face frame rotating around cross product of their respective normals with the plane normal, $\mathbf { e . g \ e } _ { 3 }$ and $\overline { { \mathbf { e } } } _ { 3 }$ in Fig.1,while keeping the angles of the principal directions [15]. Only three triangle vertices account for the interpolation and this local conformal transformation can regarded as a local structure of a certain global conformal mapping. Our experiments show that it works almost as good as the local orthogonal projection.

# 5.Error Analysis

We now set out to address the fundamental question of its convergence rate as the mesh resolution is increasing.

# 5.1. Invariant in linear interpolation

We shall examine the quantitative behavior of our linear interpolation method on a surface locally represented in the Monge form. Before proceeding,we give a lemma to this end:

Lemma 5.1. The interpolating point of a zero-crossing triangleis invariant in any curvilinear coordinate arising out of $a$ rigid transformation.

PROOF.S is expressed in terms of $\mathbf { u }$ . Given a rigid transformation between u and $\hat { \mathbf { u } }$ ,i.e. $\mathbf { u } = \mathbf { R } \hat { \mathbf { u } } + \mathbf { u } _ { 0 }$ ,where $\mathbf { R } = { \left[ \begin{array} { l l } { \cos \theta } & { - \sin \theta } \\ { \sin \theta } & { \cos \theta } \end{array} \right] } $ and ${ \bf u } _ { 0 }$ is a constant translation, then S in terms of ü can be represented by $\mathbf { R } ^ { T } \mathbf { S } \mathbf { R }$ . The elementary computation shows that

$$
\mathbf { t } ( \hat { \mathbf { u } } ) = \mathbf { M } \mathbf { t } ( \mathbf { u } )
$$

Suppose the three vertices of a zero-crossing triangle are represented as $( \mathbf { a } , \mathbf { b } , \mathbf { c } )$ in terms of $\mathbf { u }$ and $( \hat { \mathbf { a } } , \hat { \mathbf { b } } , \hat { \mathbf { c } } )$ in terms of $\hat { \mathbf { u } }$ respectively.We have

$$
x \mathbf { t } ( \hat { \mathbf { a } } ) + y \mathbf { t } ( \hat { \mathbf { b } } ) + ( 1 - x - y ) \mathbf { t } ( \hat { \mathbf { c } } ) = \mathbf { M } \left( x \mathbf { t } ( \mathbf { a } ) + y \mathbf { t } ( \mathbf { b } ) + ( 1 - x - y ) \mathbf { t } ( \mathbf { c } ) \right)
$$

Because det $( \mathbf { M } ) = 1$ , it holds that $x \mathbf { t } ( \hat { \mathbf { a } } ) + y \mathbf { t } ( \hat { \mathbf { b } } ) + ( 1 - x -$ $y ) \mathbf { t } ( \hat { \mathbf { c } } ) = \mathbf { 0 } \Leftrightarrow x \mathbf { t } ( \mathbf { a } ) + y \mathbf { t } ( \mathbf { b } ) + ( 1 - x - y ) \mathbf { t } ( \mathbf { c } ) = \mathbf { 0 }$ We verify this lemma immediately.

# 5.2.Error Analysis

Bysubstituting the Monge form ofEq.(6),elementary computation works out as follows:

$$
\begin{array} { r c l } { { { \bf { S } } } } & { { = } } & { { \left[ \begin{array} { c c } { { S _ { 1 1 } } } & { { S _ { 1 2 } } } \\ { { S _ { 2 1 } } } & { { S _ { 2 2 } } } \end{array} \right] } } \\ { { } } & { { = } } & { { \left[ \begin{array} { c c } { { \kappa _ { 1 } + b _ { 0 } u + b _ { 1 } \nu } } & { { b _ { 1 } u + b _ { 2 } \nu } } \\ { { b _ { 1 } u + b _ { 2 } \nu } } & { { \kappa _ { 2 } + b _ { 2 } u + b _ { 3 } \nu } } \end{array} \right] + O ( { \bf { u } } ) ^ { 2 } } } \end{array}
$$

Hence

$$
\begin{array} { r l r } { \mathbf { t } ( \mathbf { u } ) } & { = } & { \left[ \begin{array} { c } { \kappa _ { 1 } - \kappa _ { 2 } + ( b _ { 0 } - b _ { 2 } ) u + ( b _ { 1 } - b _ { 3 } ) \nu } \\ { 2 ( b _ { 1 } u + b _ { 2 } \nu ) } \end{array} \right] } \\ & { = } & { \mathbf { t } _ { 0 } + u \mathbf { t } _ { 1 } + \nu \mathbf { t } _ { 2 } + O ( \mathbf { u } ) ^ { 2 } } \end{array}
$$

where $\mathbf { t } _ { 0 } = \left[ \begin{array} { c } { \kappa _ { 1 } - \kappa _ { 2 } } \\ { 0 } \end{array} \right] , \mathbf { t } _ { 1 } = \left[ \begin{array} { c } { b _ { 0 } - b _ { 2 } } \\ { 2 b _ { 1 } } \end{array} \right] \mathrm { a n d } \mathbf { t } _ { 2 } = \left[ \begin{array} { c } { b _ { 1 } - b _ { 3 } } \\ { 2 b _ { 2 } } \end{array} \right] .$ $\mathbf { t } _ { 1 }$ and $\mathbf { t } _ { 2 }$ are the principal linear parts.

Given a △abc in the $\boldsymbol { u } \nu$ domain with origin $\mathbf { p }$ ，it covers a point of $\bar { \mathbf { d } } \ = \ [ \bar { u } , \bar { \nu } ] ^ { T }$ under consideration．Without loss of generality, we can imagine that $\mathbf { p }$ is inside △abc,for example,

the centroid, according to Lemma 5.1. Suppose the barycentric coordinates of $\bar { \mathbf { d } }$ in terms of △abc were $( x , y )$ .Denote $h = m a x ( | \mathbf { a } - \mathbf { p } | , | \mathbf { b } - \mathbf { p } | , | \mathbf { c } - \mathbf { p } | )$ ,then

$$
x \mathbf { t } ( \mathbf { a } ) + y \mathbf { t } ( \mathbf { b } ) + ( 1 - x - y ) \mathbf { t } ( \mathbf { c } ) = \mathbf { t } _ { 0 } + { \bar { u } } \mathbf { t } _ { 1 } + { \bar { \nu } } \mathbf { t } _ { 2 } + O ( h ^ { 2 } ) (
$$

According to Eqs.(15) and (16),we have

$$
\mathbf { t } ( \bar { \mathbf { d } } ) = x \mathbf { t } ( \mathbf { a } ) + y \mathbf { t } ( \mathbf { b } ) + ( 1 - x - y ) \mathbf { t } ( \mathbf { c } ) + O ( h ^ { 2 } )
$$

Eq.(17) reveals the operational principle of our method. It means that t is approximated by linear interpolation to accuracy of $O ( h ^ { 2 } )$ . Here $h$ can be relaxed to be the resolution size of the mesh — the maximal length of all edges.It also reflects that the key to linear interpolation is that t can be linearized locally such that tis dominated by its linear terms.Either $\mathbf { t } _ { 1 } \neq \mathbf { 0 }$ or $\mathbf { t } _ { 2 } \neq \mathbf { 0 }$ is required to make Eq.(17) in proper operation, namely

$$
b _ { 1 } b _ { 2 } \neq 0 \quad { \mathrm { o r } } \quad ( b _ { 0 } - b _ { 2 } ) ( b _ { 1 } - b _ { 3 } ) \neq 0
$$

Eq.(18) is satisfied with a generic umbilical point. If the mesh is fine enough,a zero-crossing triangle of △abc implies that △abc is also umbilical by both Eqs.(17) and(18).

Because an interpolating point can approximate a zero point of t — that is,an umbilical point — we need to address the further issue of what the accuracy is between an umbilical point and an interpolating point to complete our discussion.

Assume $\bar { \mathbf { d } }$ be an interpolating point, we have by Eq.(16):

$$
\mathbf { t } _ { 0 } + \bar { u } \mathbf { t } _ { 1 } + \bar { \nu } \mathbf { t } _ { 2 } = O ( h ^ { 2 } )
$$

Suppose $\mathbf { t } ( \mathbf { d } ) = \mathbf { 0 }$ inside △abc — that is, $\mathbf { d } = [ u , \nu ] ^ { T }$ is an umbilical point — then

$$
\mathbf { t } _ { 0 } + u \mathbf { t } _ { 1 } + \nu \mathbf { t } _ { 2 } = O ( h ^ { 2 } )
$$

Eq.(20) subtracted from Eq.(19) gives

$$
( \bar { u } - u ) \mathbf { t } _ { 1 } + ( \bar { \nu } - \nu ) \mathbf { t } _ { 2 } = O ( h ^ { 2 } )
$$

According to the Cauchy-Schwarz inequality,we have

$$
\left| \mathbf { d } - { \bar { \mathbf { d } } } \right| = { \sqrt { ( { \bar { u } } - u ) ^ { 2 } + ( { \bar { \nu } } - \nu ) ^ { 2 } } } \geqslant O ( h ^ { 2 } )
$$

On the other hand,if the umbilical point is generic and the mesh resolution is high enough, $\mathbf { t }$ is approximated to sufficient accuracy by its principal linear components and thus a zerocrossing triangle coincides with an umbilical triangle. In this case we obviously have $\left| \mathbf { d } - \bar { \mathbf { d } } \right| \leqslant O ( h )$ . Therefore,we have the following proposition.

Proposition5.2.If themesh resolutionis sufficiently high,the interpolatingpoint ofa zero-crossing triangle approximates an umbilical point to accuracy between $O ( h )$ and $O ( h ^ { 2 } )$

# 5.3.Error propagation

The above analysis is based on the exact S. However, principal curvatures and principal directions are estimated on accuracy in practice up to some extent. Thus,their errors have to be considered in estimation of umbilical points by linearly interpolating S,i.e.error propagation from shape operators to an interpolating point. According to the discussion in Section 5.2, it entirely relies on the accuracy of the estimated S.

We think of it under the conditions presented by [8]:

Proposition 5.3.Given the position, gradient, and Hessian of coordinate functions that approximated to $O ( h ^ { d + 1 } ) , O ( h ^ { d } )$ and $O ( h ^ { d - 1 } )$ , respectively, and assuming the condition number of the Jacobian matrix is bounded,we have:(a) The angle between the computed and exact normals is $O ( h ^ { d } )$ ； (b)the components of the shape operator and curvature tensor are approximated to $O ( h ^ { d - 1 } )$ ：

For a mesh model, $d$ is typically 2 such that S is approximated to accuracy $O ( h )$ ,which gives us the following corollary:

Corollary 5.4.A resultant umbilical pointby linear interpolationis typically approximated to accuracy $O ( h )$

# 6.Recondition umbilical points

Umbilical points are difficult to be reconditioned with complete fidelity although they are inherent in a surface. There are two factors of S tensor distribution as well as geometry detail across the strongly affecting their computational quality. In practical usage,two crucial issues are to be addressed:One is howto judge an umbilical point to be mistakable and the other is how to compute operable umbilical point set.

Judging mistakable umbilical points.To the best of our knowledge,no work has been done for this purpose in the literature yet.We propose a method to determine if an umbilical point is mistakable by a necessary condition: An umbilical point is either spherical or planar and thus distributes over an elliptic $\left( \kappa _ { G } > 0 \right)$ oraplanar $\overset { \vartriangle } { \boldsymbol { K } } \boldsymbol { G } = 0$ and $\begin{array} { r } { \kappa _ { H } = 0 . } \end{array}$ )regions of the surface [5]. It generally occur as an isolated point in the elliptical region and,furthermore,a flat region is left out of account since itis unusually of interest in actual applications.Another obvious observation indicates that a significant umbilical point should be supported over a sufficiently large elliptic region; in contrast, the local shape variation only yields a small region of same type. Based on those two considerations,our first strategy is devised as follows:

1.First, the surface is partitioned into parts with surface type labels based on $\kappa _ { G }$ and $\kappa _ { H }$ . Only elliptic surface types are remained,i.e.Peak and Pit typesl [4],for further treatment.   
2.Then, two fundamental operations in mathematical morphology- dilation operator $D$ and erosion operator $E$ ，are used in turn. They compose an opening operator $D ^ { n } \circ E ^ { n }$ with $n$ erosions followed by $n$ dilations and applied to the elliptic parts to erase narrow connectors and open up large holes or caves. $n$ is determined by the the sizes of narrow connectors to be erased.Umbilical points are eroded away near the boundaries of elliptic parts.   
3.Finally, the remaining umbilical points are kept over the elliptic parts.

Inconsequential umbilical points can be clean out significantly in this way. We will demonstrate this effect in our experiments.

Computing operable umbilical points.A real-world mesh model usually contains a plenty of curvature variation across its surface arising from various desired or undesired factors,such as detail enhancement and sampling noise. The sensitivity of umbilical points to those variation reflects their characteristic response to the shape undulation,leading to a massive amount of umbilical points.But too many umbilical points might affect their application. To make them operable in practice,their number should be drastically reduced.For example,it is reduced to simplify the topology of the extracted field so as to cut a surface for quadrangulation [3]. In this scenario,an approach to smoothing or denoising shape operators will be beneficial to minimizing the number to meet different requirements— such asremoving superfluous points by C smoothing[1] or by refinement of principal frame fields [16]. In contrast to those methods by denoising 2-order differential quantities,we smooth normals by a linear filter and shape operators are then estimated based the resultant normals. Our experimental results will show that our method can decimate undesire umbilical points effectively.

# 7．Experimental results and discussion

In this section, we shall demonstrate our method by experiments and comparisons with other methods based on a surface of analytical representation and some real-world mesh models.

# 7.1.Method validation

We confirm our proposed techniques by using a practical example with known umbilical points on a given Monge patch:

$$
z = 0 . 5 ( x ^ { 2 } + y ^ { 2 } ) + 1 . 2 x ^ { 3 } - 0 . 5 x ^ { 2 } y + 0 . 2 x y ^ { 2 } + 1 . 6 y ^ { 3 }
$$

Since Eq.(21) is a polynomial expression,all its umbilical points can be found by a solver of polynomial system,as done in [20]. As a matter of fact, there are exactly three umbilical points on the patch:

$$
\begin{array} { r c l } { \mathbf { p } _ { 1 } } & { = } & { [ 0 , 0 , 0 ] ^ { T } } \\ { \mathbf { p } _ { 2 } } & { = } & { [ - 0 . 9 5 6 9 5 0 8 8 , - 0 . 1 8 5 7 1 1 7 5 , - 0 . 5 0 8 2 9 2 6 9 ] ^ { T } } \\ { \mathbf { p } _ { 3 } } & { = } & { [ - 0 . 3 9 1 6 5 2 7 4 , - 0 . 8 1 9 2 2 0 2 3 , - 0 . 5 2 9 2 4 7 7 3 ] ^ { T } } \end{array}
$$

Given a set of 5.4K points by a random sampling inside the region $[ - 1 . 2 , 1 . 2 ] \times [ - 1 . 2 , 1 . 2 ]$ on the parametric plane,a Delaunay triangulation is constructed. We polygonize such a patch to be a triangular mesh using the Delaunay triangulation. For the sake of clarity, $\mathbf { p } _ { 1 } , \mathbf { p } _ { 2 }$ and ${ \bf p } _ { 3 }$ are marked noticeably by their respective bounding boxes as in Fig. 2.

We devise the experiments following the line from fine shape operatorsto coarse ones.

# 7.1.1.Numerical behavior

We first consider an instance excluding the influence of noise The exact principal curvatures and principal directions are both computed analytically at each vertex according to Eq.(21） so that shape operators are ready to be applied to our approach regardless of numerical errors in discrete estimation.The linearly interpolating points are displayed in Fig.4. Not unexpectedly, it exhibits favorable interpolation despite the irregular mesh: three umbilical triangles are figured out correctly and the interpolating points are close to the ground truth umbilical points for sufficient accuracy.

![](images/b525df6fe4f87ec65517174faea92b8fcf9b5758b91de046459a31d71641c66b.jpg)  
Figure 2:A designed irregular mesh of a surface patch on the parametric domain with ground-truth umbilical points of p1，P2 and p3,marked inside their respective boxes with same indexes.The zoom-in views are exhibited in Fig.4(a)-4(c) of umbilical points resulting form index of vector field,curvaturetensor interpolation and shape-operator interpolation,where shape operators are computed analytically. Those with shape operators estimated in discrete fashion are exhibited in Fig.5(a)-5(d),respectively; umbilical points inside Box 4 are suspicious.

![](images/27680ab07c1c14b69d95d0108a76a1806fa41ddbadbfd4948076c233330490c3.jpg)  
Figure 3: Sharply changing principal directions near erroneous umbilical points in the parameter plane by local orthogonal projection.

an opening operator.

Table 1:Linear interpolation with ground truth shape operators based local orthogonal projection(O) and local conformal transformation(C).   

<html><body><table><tr><td></td><td>Estimated</td><td>Projection</td></tr><tr><td rowspan="2">p1</td><td>1.10570e-3,7.25923e-4,8.05220e-4</td><td>0</td></tr><tr><td>1.10569e-3,7.25909e-4,8.05220e-4</td><td>C</td></tr><tr><td rowspan="2">P2</td><td>-0.959762,-0.184829,-0.515272</td><td>0</td></tr><tr><td>-0.959762,-0.184829,-0.515272</td><td>C</td></tr><tr><td rowspan="2">P3</td><td>-0.388567,-0.827572,-0.551645</td><td>0</td></tr><tr><td>-0.388567，-0.827572,-0.551644</td><td>C</td></tr></table></body></html>

We then compute the shape operators by a discrete estimator: We approximate the rough normal at a vertex using the method of[14] and choose it as the $\textbf { \em z }$ axis to fit a polynomial surface in its two-ring neighbors to estimate the applied normal; based on these resultant normals,the shape operators are finally computed using normal-fitting method.Fig.5 exhibits the results using the discrete estimator of shape operator. In contrast to exact $s$ , the resultant $\mathbf { p } _ { 1 }$ lies slightly outside the relevant umbilical triangle and thus the zero-crossing triangle of $\mathbf { p } _ { 1 }$ fails to coincide with its umbilical triangle (See Fig.5(a) for zoom-in views).But it is acceptable since the ground truth $\mathbf { p } _ { 1 }$ isnear a triangle edge.Moreover, there are some exceptions for interpolation of discretely estimated shape operators: Two additional umbilical points are produced in error,as shown in Fig. 5(d). They obviously come into conflict with the ground truth. We elucidate the reason for these wrong points. We project the principal directions onto the parametric plane,as illustrated with Fig.3,and we can see that principal directions change very sharply near them.Itis really an ambiguous case due to the sudden change of the principal directions. The elementary calculation shows that the angle between the nearby principal directions near it is right-angled as $9 2 ^ { \circ }$ . They lie at the transition region of different surface types and can be filtered by

Table 2:Linear interpolation with estimated shape operators based local orthogonal projection(O) and local conformal transformation(C).   

<html><body><table><tr><td></td><td>Estimated</td><td>Projection</td></tr><tr><td rowspan="2">p1</td><td>2.90345e-3,2.18191e-3,8.30664e-4</td><td>0</td></tr><tr><td>2.90349e-3,2.18194e-3,8.30665e-4</td><td>C</td></tr><tr><td rowspan="2">p2</td><td>-0.962192,-0.185054,-0.520515</td><td>0</td></tr><tr><td>-0.962192,-0.185054,-0.520515</td><td>C</td></tr><tr><td rowspan="2">P3</td><td>-0.388707，-0.827926,-0.552492</td><td>0</td></tr><tr><td>-0.388707，-0.827926，-0.552492</td><td>C</td></tr></table></body></html>

We have shown that any valid parametrization can apply to the shape-operator-based interpolation. Besides local orthogonal projection,we also give a local conformal transformation asa means of implementing the method in Section 4.2.2.Table 1 and 2 list the experimental data of the two implementations. There is no appreciable difference between them, also as expected in our more experiments. Therefore,shape-operatorbased interpolation via orthogonal projection is only taken in following comparison experiments.

# 7.1.2. Comparisons

Can other comparable methods do better than our proposed method since ours might fail to respect the true umbilical points as shown in Fig.5(d)? In this subsection,we compare our shape-operator-based interpolationmethodto the index-based method grounding onEq.(2) and the curvature-tensor-based interpolation method via global conformal parameterization, denoted with S, I and $\mathbb { C }$ methods for short,respectively.For curvature-tensor interpolation,we apply LSCM parameterization in [11] to performing the global parameterization; because it requires the mesh to be homeomorphic to a planar disk or a planar square in the parametric domain, the Monge patch of Eq.(21) happens to meet. In this scenario,we can re-flatten it to the planar domain of conformal parameterization.

Reusing the shape operators in Section 7.1.1, both analytical and discrete,we compute the umbilical points with the three methods,respectively.Figs.2 and 4illustrate the resultant interpolating points in analytical case.So do Figs.2 and 5 in discrete case.It is obvious that the interpolation behavior of $\mathbb { C }$ and $\mathbb { S }$ methods are quite similar — something that is expected.Without regard to the error effects of global discrete parameterization, their resultant umbilical points can be thought of comparable; unfortunately, the error of approximately global parametrization can make the interpolation less reliable,which will be shown by experiments in the following text. In vivid contrast against both $\mathbb { C }$ and $\mathbb { S }$ ,I method can yields a cluster of points near an umbilical points rather than one.

![](images/3db685e0d6996b04916d1d778793ca916525f7c8c330ec9c080aab428ce2fd66.jpg)  
Figure 4: Resultant umbilical points based on exact shape operators near ${ \bf p } _ { 1 }$ ${ \bf p } _ { 2 }$ and ${ \bf p } _ { 3 }$ . A green $\because \sqsupset \$ represents an exact umbilical point, a magenta $\mathbf { \bar { \rho } } _ { \times } ,$ results from linearly interpolating curvature tensor,and a blue $\ ' _ { + } \ '$ is from linearly interpolating shape operators; a red'o' is determined by index-based method.

![](images/30a7905c761d758970b2700009991c9cb62972633f34f2b05c3e1aaa6b8478e5.jpg)  
igureo withlocal parameterization,based on discrete estimate.

Fig.5 makes a response to the inquiry at the beginning of this subsection:both I and $\mathbb { C }$ methods cannot do better than $\mathbb { S }$ These facts will be more evident in the following experiments.

# 7.2. Linear interpolation over mesh models

We shall demonstrate our method with real-world mesh mod els.

Fig.6 shows the resultant umbilical points on a hand model by the three methods,respectively. To help understanding their distribution over the mesh,one branch of estimated principal directions are also displayed.In the I method,a cluster of vertices can be detected arising out of an umbilical point, typically either1,or2,or3(See Fig.6(a)); the $\mathbb { C }$ method fails to work near the tips of the fingers except for the thumb because the parameter gradients of the underlying global conformal parameterization are too large (See Fig. 6(b)); the $\mathbb { S }$ behaves the best(See Fig.6(c)).And, of course, $\mathbb { S }$ method will work better if the model is decomposed into more smaller charts and then flatten to reduce the distortion.

The second example is of a rocker-arm model.It is close and thus the global parameterization is not performed. Fig.7illustrates the difference between the $\mathbb { S }$ method and the I method. The former usually determines only one umbilical point near a singular point in the principal direction field,but the I does not.Because sufficient points per boundary curve are required to estimate the index,the index-based is more sensitive to the irregularity of the mesh.

![](images/2a05a11802b3071404a91608af86884d58ec9f2a0d54614c0c5f37f2be636149.jpg)  
(a)Umbilical points over the rocker-arm model

![](images/24362be4481c6390597aa2b5f340994adc326b8a60eb84d556dbb86336cf5196.jpg)  
Figure 7: The rocker-arm model. The detected umbilical points by the I method are drawnas a smaller red ballwhile those by the $\mathbb { S }$ are larger black balls.

![](images/92dd6d9dbfe5d9e27aaf0007642380842720a3c7d018456a268ccd43a679b809.jpg)  
Figure 6:The hand model.Local methods,i.e.I and S,behave themselves,but the global $\mathbb { C }$ results in some fallacious umbilical points near the tips of the four fingers other than the thumb.(d) shows the resultant points processed by ellptic regions based on $\mathbb { S }$

# 7.3.Filtering umbilical points

Given trivially-estimated shape operators,the previous example with ground-truth umbilical points exhibit some mistakable ones even if the mesh is noise-free(See Figs.2 and 5(d)). As pointed out in Section 6,two strategies can be exploited to recondition the resultant umbilical points and thus to increase the practical utility of those resultant points.

The first one is applying the opening operator to an elliptical region over the surface so as to erase narrow regions usually related to geometry details or transition regions of different surface types. The bigger $n$ is,the more umbilical points are removed.To balance the fidelityand practicability of resultant umbilical points, $n = 2$ is chosen in our experiments.Furthermore,a flat region is left out of account since it is unusually of interest in practical applications.We apply this strategy to Fig.5(d),and the result is shown in Fig.8.We can see that the mistakable points outside elliptical regions are eliminated. Fig. 6(d) shows the reconditioned umbilical points for the hand model.

However, the first strategy is not capable of handling complex geometry, for instance,the Standford Bunny with plenty of curvature variation. Fig.9 shows the interpolating umbilical points handled without and with opening operator,respectively.Because the 'low’mesh resolution of the Bunny cannot accommodate its surface roughness, too many umbilical points still remain even after opening operation,which will affect their practical utility. In this setting,an approach to smoothing or denoising shape operators will be beneficial to make further improvement on the filtering quality.As an alternative,we apply linear fiting to the normals before shape operators are estimated.The experimental results are shown in Fig.1O.This strategyworks very well for the rocker-arm model; as illustrated with Fig.11, it makes a significant improvement in contrast to Fig.7. Fig.12 results from the combination of the two strategies. It shows that the resultant points reflect symmetry for a symmetrical shape.They can be used as anchor points to extract the symmetrical plane of the Torso.

![](images/2a4ccaa8c5a3d2cc60a4d022a6591cfbdcd921db5708d1405af7125aa5cf3f6e.jpg)  
Figure 8:Recondition the umbilical points on the surface patch by surface type. (Refer to Figs.2 and 5).Colorful regions are elliptical regions where umbilical points should locate.Mistakable umbilical points in Box 4 are excluded successfully.

# 7.4. Computational cost

Given principal curvatures and principal directions of ver tices over a mesh,linear interpolation of shape operators for umbilical points is performed by going over all triangles. For an interpolation of each triangle,no optimization computation is required. Instead,only some necessary floating point arithmetic for local reparameterization of shape operators onto each triangle plane (as described in Section 4.2) is needed. Therefore,the computational cost of our algorithm increases linearly with the number of triangles and runs on-the-fly as opposed to the cost for estimating shape operators.

![](images/58ee39809596f577b2aa898b1e116915b819f6566daf78a87f600db451a9dc6c.jpg)

![](images/b8f240c1f003b1a2fedf1dbe5c4c667e38bd7586940f3f5c81f0eb76d68bb2e2.jpg)  
Figure 1O:Umbilical points over the Bunny by smoothing shape operators with normal fitting.

![](images/8cdd3302b8984efe6c78da5f377069cd2b58c4662773a7e0aeeee6182f13a619.jpg)  
Figure 9:Umbilical points over the Bunny. The top calculates umbilical points straightforwardly;the bottom filters the points by elliptic regions.   
Figure 11:Umbilical points over the rocker-arm.Umbilical points over the flat regions are discarded.

![](images/a514db5423b4b5d109ae9b5b7b3b4c4994ef4390036b3dc3aa5ebb974cc47673.jpg)  
Figure 12:Umbilical points over the symmetrical Human-Torso model.The resultant points reflect the symmetry of the model.

# 8.Conclusion

In this paper,we described a novel approach developed for umbilical-point detection over a mesh by interpolating shape operators via a local parameterization. The shape operators do not need to be symmetrical any more and we propose using a local parameterization by orthogonal projection or local conformal transformation to cooperate with the interpolation of shape operators.Furthermore,we conducted a systematic error analysis on the interpolation to demonstrate its efficiency.

Linear interpolation is superior to the index-based method because the latter should collect sufficient neighboring points for index computation and,accordingly, the former is less sensitive to the regularity of the underlying mesh. In contrast to curvature-tensor based on global conformal parametrization, the proposed method in this work is significantly advanced because its local parametrization is done more robustly and no additional errors are introduced in parameterization;furthermore, it does not suffer from the topological requirements of the mesh surface for global parametrization; and thus significant computational burden and implementation complexity are removed without the construction of a global parametrization or the segmentation of a complex model. As a result, our method saves considerable time,and is more flexible and easy to implement.

# Acknowledgments

The author thanks AimShape, Standford,and others for providing 3D surface models.

# References

[1]P.Alliez，D.Cohen-Steiner,O.Devillers，B．Lévy，M.Desbrun. Anisotropic polygonal pemeshing.In: Proceedings of ACM SIGGRAPH, 485-493,2003. [2] M.V.Berry,J.H. Hannay. Umbilic points on Gaussian random surfaces. Journal of Physics A:Mathematical and General,10(11),1809-1821, 1977.   
[3]D.Bommes,H. Zimmer,L.,Kobbelt.Mixed-Integer Quadrangulation. ACM Transactions on Graphics,28(3),2009. [4] P.J.Besl,R.C.Jain. Segmentation Through Variable-Order Surface Fitting.IEEE Trans.on Pattrn Analysis and Machine Intelligence,10(2), 167-192,1988.   
[5]W.J. Che,J.-C.Paul, X.P. Zhang.Lines of curvature and umbilical points for implicit surfaces. Computer Aided Geometric Design,24(7),395-409, 2007.   
[6] T.Delmarcelle,L.Hesselink.The topology of symmetric,second-order tensor fields.In:Proceedings of IEEE Visualization,14O-145,1994. [7]T.Gatzke,C.Grimm.Estimating curvature on triangular meshes.International Journal of Shape Modeling,12(1),1-28,2006. [8] X.M. Jiao,H. Y. Zha. Consistent computation of first- and second-order differential quantities for surface meshes.In: Proceedings of the 2008 ACM symposium on Solid and physical modeling. [9] E. Kalogerakis,D.Nowrouzezahrai,P.Simari, K. Singh. Extracting lines of curvature from noisy point clouds. Computer Aided Design,41(4), 282-292,2009.   
[10]K.H.Ko,T.Maekawa,N.M.Patrikalakis,H.Masuda,F.Wolter. Shape intrinsic fingerprints for free-form object matching.In:Proceedings of the 8th ACM symposium on Solid modeling and applications,196-207, 2003.   
[11]B.Lévy,S.Petitjean,N.Ray,J. Maillot.Least squares conformal maps for automatic texture atlas generation. In: Proceedings of ACM SIGGRAPH, 362-371,2002.   
[12] T.Maekawa,N. M.Patrikalakis. Interrogation of differential geometry properties for design and manufacture.The Visual Computer,1O(4),216- 237,1994.   
[13]T.Maekawa,F.E.Wolter,N.M.Patrikalakis.Umbilics and lines of curvature for shape interrogation. Computer Aided Geometric Design,13(2), 133-161, 1996.   
[14]N.Max.Weights for Computing Vertex Normals from Facet Normals. Journal of Graphics Tools,4(2),1-6,1999.   
[15]Rusinkiewicz,S.,2OO4.Estimating curvatures and their derivatives on triangle meshes.In Proceedings of 2nd International Symposium on 3D Data Processing,Visualization and Transmission,486-493.   
[16] P.T. Sander, S.W. Zucker. Singularities of principal direction fields from 3-D images.IEEE Trans.on Patern Analysis and Machine Intelligence, 14(3),309-317,1992.   
[17]G. Savio,G.Concheri,R.Meneghello.Lines of curvature and umbilical points: computation method and applications.Applied Mechanics and Materials,Vol.421,489-495,2013.   
[18] X. Tricoche. Vector and Tensor Field Topology Simplification, Tracking, and Visualization.PhD thesis, Universitat Kaiserslautern,2002.   
[19]X.N. Yang,J.M. Zheng.Curvature Tensor Computation By Piecewise Surface Interpolation. Computer-Aided Design, 45(12),1639-1650, 2013.   
[20]X.P. Zhang,W.J.Che,J.-C.Paul. Computing lines of curvature for implicit surfaces.Computer Aided Geometric Design,26(9),923-940,2009.