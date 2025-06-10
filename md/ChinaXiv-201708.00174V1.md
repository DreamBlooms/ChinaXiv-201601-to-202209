# Analytical solutions to single scattering of SH waves by a cylindrical fiber with radially gradient interphases

Jun Zhanga,b,\*, Lian Liua, Longhai Zenga, Jiading Baoc

$\boldsymbol { a }$ College of Aerospace Engineering, Chongqing University, Chongqing, 400044, PR. China bChongqing Key Laboratory of Heterogeneous Material Mechanics, Chongqing University, Chongqing, 400044,P.R. China eSchool ofMechanical and Electrical Engineering, Guilin University of Electronic Technology, Guilin,541004, P.R. China

Abstract: In this work, analytical solutions to the single scattering of SH waves by a cylindrical fiber with two specific radially gradient interphase layers are supported based on the method proposed by P.A.Martin (Martin 2002, JASA). In the first case,1) shear modulus $\mu ( \mathrm { r } ) = e ^ { 2 \beta r }$ and the square of wave number, $k ^ { 2 }$ , is a linear function of $1 / r$ and 2) $\mu ( \mathrm { r } ) = e ^ { - \beta r ^ { 2 } }$ and $k ^ { 2 }$ is a linear function of $r ^ { 2 }$ . For example, analytical solutions to single scattering of SH waves by a Sic fiber with the above two interphase layers embedded in aluminum are presented. The calculated scattering cross sections are compared with values obtained from an approximate method (dividing the continuous varying layer into multiple homogeneous sub-layers). The two methods yield similar results. The contribution of this work benefits the validation of various numerical methods used in the inhomogeneous media.

Key words: Single scattering; SH wave; Radially gradient interphase

# 1. Introduction

The multiple scattering of waves occurs throughout our daily lives - the scattering of sound by water drops in fog, for example, and the scattering of light by fine particles in the air. Research on the multiple scattering of waves has a lengthy history by virtue of its ubiquityl. The multiple scattering of elastic waves in composites is still an active research topic, as these materials are relatively new. Due to multiple scattering effect, even if the composite's matrix and inclusions are both elastic, the elastic waves propagating in the material remain attenuated; this is called attenuation caused by scattering. To date, there have been many theoretical models proposed to evaluate this attenuation, as accurately evaluating it facilitates the dynamic characterization and nondestructive assessment ² of composite materials.

The extant research can be roughly split into two groups. The first group consists of methods based on the wave function expansion and configurational averaging technique，which was pioneered by Foldy 3-7. In these methods, the exciting and scattered waves of each inclusion in a composite material are expressed as series of wave functions. The expansion coefficients of the scattered waves for each inclusion are related to the corresponding values of the exciting wave through a matrix $T .$ ，the components of which are determined by the boundary conditions of the corresponding single scattering problem 8. For SH waves, $T$ becomes a scalar since there is no mode conversion. After a sequence of mathematical operations, a homogeneous system for the ensemble averaged expansion coefficients of the exciting waves or scattered waves can be obtained. Solving this homogeneous system yields the attenuation coefficient. The second group consists of studies on the self-consistent method 9-12, where it is assumed that each inclusion behaves as an isolated one in a medium with the effective properties of the composite. The exciting wave acts on each inclusion is the coherent wave.The attenuation coefficient is then obtained through various consistency conditions; for example, the mean wave field equals the coherent wave field 1² or the total scattering by the inclusions embedded in the effective medium effectually vanishes 11

It is clear that, both the above introduced two groups of theoretical models necessitate solving a corresponding single scattering problem 8, that is, the scattering of a plane incident wave by a single inclusion embedded in an infinite matrix. The single scattering problem is solved to obtain the far-field scattering amplitude, $f ( \Theta )$ ，in models proposed by Waterman and Truell 3,13 for example, and is solved to obtain the scattering cross section. In most of the existing theoretical models， the fibers/ particulates are usually assumed to be perfectly bonded to the matrix while the interphase layer between the fibers and matrix is neglected. The interphase layer should be accounted for, however, as it features gradient changed properties that are generated via chemical reaction and atom diffusion during the manufacturing process (or created artificially to improve compatibility between the fibers and the matrix).

Up to date, the effect of the functional gradient interphase layer on the attenuation of elastic waves in composite materials has been sparsely considered in several works 14-18. In these previous studies, in order to solve the corresponding single scatering problem, the inhomogeneous interphase layer is usually divided into multi-layers with homogeneous properties to approximate a continuous varying one. The wave fields in the fiber, intermediate sub-layers, and matrix are then expressed as series of wave functions. The continuity conditions of displacements and stresses at all interfaces are listed and the resulting coupled linear equations for the expansion coefficients are solved. When the intermediate sub-layers are sufficiently thin, this yields accurate solutions 15. This treatment of the gradient interphase layer is straightforward and can be used to deal with any type of radially gradient profile, but the coefficient matrix of the resulting linear system is sometimes il-conditioned. Additionally, for composites with a high contrast of properties between fibers and the matrix, the interphase layer must be divided into a large number of sub-layers in order to obtain convergent results. This increases the computational cost as well as the condition number of the coefficient matrix 19.

The transfer matrix method is another candidate for the above interphase problem 18.Inthismethod,thedisplacementsandstressesattheinnersurfaceofeach intermediate sub-layer are related to the corresponding values on the outer interface through a transfer matrix $M _ { ; }$ ， the components of which are functions of the material properties and geometry uniquely defined by the sub-layer. Using the transfer matrix for each intermediate sub-layer, the displacements and stresses on the outer surface of the whole interphase layer are related to the inner surface. Assuming the fiber, interphase layer, and matrix are perfectly bonded, a linear system for the expansion coefficients of waves in the fiber and matrix is established and solved. For SH waves, the transfer matrix $M$ is a matrix of size $2 \times 2$ . Therefore, the final resulting linear system to be solved is of size 2, which is much smaller than that in the method described above. Similarly, the final coefficient matrix of the resulting linear system can be illconditioned if the sub-layers are thin.

Though several approximate methods to solve the single scattering problem with a radially gradient interphase layer have been proposed, to date, analytical solutions are still elusive. In this work,analytical solutions to single scattering with a radially gradient interphase layer of two specific profiles are reported for SH waves. The derivation process follows the work of P.A. Marin 20, in which general solutions to the single scattering of acoustic waves by an inhomogeneous sphere with spherically symmetrical properties was investigated. The two transformations used in the current derivation process differ from Martin's due to the different governing equations for distinct waves. We also demonstrated how to extend the proposed transformations to other waves.

The remainder of this paper is organized as follows: Section 2 derives the governing equations for SH waves in a radially gradient medium. General solutions for two specific radially gradient materials are then derived in Section 3. Section 4 presents analytical solutions for the single scattering problem of SH waves by a cylindrical fiber with the two specific interphase layers and a detailed example. Section 5 provides a brief summary and conclusion.

# 2. Governing Equations

For SH waves, only the displacement in the out-of-plane has value and can be expressed as $w = w ( \mathbf { x } , \mathfrak { t } )$ ，where $\mathbf { x } = ( x , y )$ is the position vector and $t$ represents time variable. The corresponding stress components can be expressed as follows:

$$
\sigma _ { _ { 1 1 } } = \sigma _ { _ { 2 2 } } = \sigma _ { _ { 3 3 } } = \sigma _ { _ { 1 2 } } = 0 , \sigma _ { _ { 1 3 } } = \mu \left( \mathbf { x } \right) \frac { \hat { \sigma } w } { \hat { \sigma } x } , \sigma _ { _ { 2 3 } } = \mu \left( \mathbf { x } \right) \frac { \hat { \sigma } w } { \hat { \sigma } y }
$$

where $\mu ( \mathbf { x } )$ is the shear modulus,which is a function of position. Substitution of the stress components to the governing equations of elastodynamics yields the following equation:

$$
\frac { \partial } { \partial x } \Bigg ( \mu ( { \bf x } ) \frac { \partial w } { \partial x } \Bigg ) + \frac { \partial } { \partial y } \Bigg ( \mu ( { \bf x } ) \frac { \partial w } { \partial y } \Bigg ) = \rho \big ( { \bf x } \big ) \frac { \partial ^ { 2 } w } { \partial t ^ { 2 } }
$$

where $\rho ( \mathbf { x } )$ is the mass density. After a simple mathematical operation, Eq. (2) can be re-written as follows:

$$
{ \frac { 1 } { \mu \left( \mathbf { x } \right) } } \nabla \mu { \left( \mathbf { x } \right) } \cdot \nabla w + \nabla ^ { 2 } w = { \frac { 1 } { c ^ { 2 } \left( \mathbf { x } \right) } } { \frac { { \hat { \sigma } } ^ { 2 } w } { { \hat { \sigma } } t ^ { 2 } } }
$$

where $\nabla$ and $\nabla ^ { 2 }$ are the 2D gradient and Laplace operator, respectively. $c ( \mathbf { x } ) =$   
$\sqrt { { \mu ( { \bf x } ) } / { \rho ( { \bf x } ) } }$ is the wave speed, which is also a function of position.

Define $w ( { \bf x } , { \bf t } ) = \mu ^ { \lambda } ( { \bf x } ) u ( { \bf x } , { \bf t } ) ^ { 2 0 }$ ，where $\lambda$ is a constant which is determined to force $u ( \mathbf { x } , \mathrm { t } )$ into the following form:

$$
\nabla ^ { 2 } \boldsymbol { u } + K \boldsymbol { u } = \frac { 1 } { c ^ { 2 } } \frac { \partial ^ { 2 } \boldsymbol { u } } { \partial t ^ { 2 } }
$$

For SH waves, $\lambda$ can be set to be $- 1 / 2$ and then $K = { \frac { 1 } { 4 } } \mu ^ { - 2 } \left| \nabla \mu \right| ^ { 2 } - { \frac { 1 } { 2 } } \mu ^ { - 1 } \nabla ^ { 2 } \mu$ . The values of $\lambda$ should be changed for other scalar waves. In this work, only the radial inhomogeneity has been considered; that is, $\mu ( \mathbf { x } ) \mathrm { a n d } \ \rho ( \mathbf { x } )$ are functions of only the radial coordinate $r$ ，SO $K$ can be simplified as follows:

$$
K = - \frac { 1 } { 2 } \frac { \mu ^ { \prime \prime } } { \mu } - \frac { 1 } { 2 r } \frac { \mu ^ { \prime } } { \mu } + \frac { 1 } { 4 } \Biggl ( \frac { \mu ^ { \prime } } { \mu } \Biggr ) ^ { 2 }
$$

For time-harmonic problems, $u ( \mathbf { x } , t ) = \overline { { u } } ( \mathbf { x } ) e ^ { - \mathbf { i } \omega t }$ , hence $\overline { { u } } ( \mathbf { x } )$ satisfies the following equation:

$$
\nabla ^ { 2 } \overline { { u } } + \Big [ k ^ { 2 } ( r ) + K \Big ] \overline { { u } } = 0
$$

where $k ( r ) = \omega / c ( r )$ . Next, we seek the solution to Eq. (6) in the following form:

$$
\overline { { u } } ( \mathbf { x } ) = u _ { n } ( r ) Y _ { n } ( \theta )
$$

where $n$ is an integer and $Y _ { n } ( \theta )$ is a cylindrical harmonic function, such as the Legendre function $P _ { n } ( \cos \theta )$

We have the following relation:

$$
{ \nabla ^ { 2 } } \left( { { u _ { n } } { Y _ { n } } } \right) = { { u _ { n } } } { \nabla ^ { 2 } } \left( { { Y _ { n } } } \right) + 2 { \left( { \nabla { u _ { n } } } \right) \cdot \left( { \nabla { Y _ { n } } } \right) } + { { Y _ { n } } } { \nabla ^ { 2 } } \left( { { u _ { n } } } \right)
$$

because $u _ { n }$ is a function of $r$ and $Y _ { n }$ is a function of variable $\theta$ ,S0 $\left( \nabla u _ { n } \right) \cdot \left( \nabla Y _ { n } \right) = 0$ We also know that $r ^ { n } Y _ { n } ( \theta )$ is a separated solution to the Laplace equation in the polar coordinate system. To this effect:

$$
\nabla ^ { 2 } Y _ { n } = - \frac { n ^ { 2 } } { r ^ { 2 } } Y _ { n } , n = \left( - \infty , + \infty \right)
$$

By substituting Eqs.(7) and (9) into Eq. (6), it is clear that $u _ { n } ( r )$ should satisfy the following equation:

$$
\frac { d ^ { 2 } u _ { n } } { d r ^ { 2 } } + \frac { 1 } { r } \frac { d u _ { n } } { d r } + \Biggl [ k ^ { 2 } ( r ) + K ( r ) - \frac { n ^ { 2 } } { r ^ { 2 } } \Biggr ] u _ { n } = 0
$$

which is a second-order differential equation for $u _ { n } ( r )$

# 3. Two Cases of Radially Gradient Interphase Layers

Two kinds of radially gradient interphase layers are considered here.

Case $\boldsymbol { { \mathit { 1 } } : }$ In this case, the shear modulus is an exponential function of $r$ and $k ^ { 2 } ( r )$ is a linear function of $r ^ { - 1 }$ as follows:

$$
\mu ( r ) = \mu _ { 1 } e ^ { 2 \beta r } , \left[ k ( r ) \right] ^ { 2 } = k _ { 1 } ^ { 2 } + \frac { 2 \alpha } { r }
$$

where $\mu _ { 1 } , \ \mathsf { \beta } , \ k _ { 1 } ^ { 2 }$ ， and $\alpha$ are constants that are specified according to the following relation:

$$
\left\{ \begin{array} { l l } { \mu \bigr | _ { r = a } = \mu _ { f } ; \ \mu \bigr | _ { r = b } = \mu _ { m } } \\ { \left. k ^ { 2 } \right| _ { r = a } = k _ { f } ^ { 2 } ; \ \boldsymbol { k } ^ { 2 } \bigr | _ { r = b } = k _ { m } ^ { 2 } } \end{array} \right.
$$

where $ { \mu } _ { f } ,  { \mu } _ { m }$ and $k _ { f } , \ k _ { m }$ are the shear modulus and wavenumber of the fibers and matrix, respectively; $a$ and $b$ are the inner and outer radius of the interphase layer. After a mathematical operation, the expression for $K ( r )$ in this case can be expressed as follo ws:

$$
K ( r ) = - \beta ^ { 2 } - \frac { \beta } { r }
$$

Then the corresponding Eq.(10) becomes:

$$
\frac { d ^ { 2 } u _ { n } } { d r ^ { 2 } } + \frac { 1 } { r } \frac { d u _ { n } } { d r } + \biggl [ k _ { 1 } ^ { 2 } - \beta ^ { 2 } + \frac { 2 \alpha - \beta } { r } - \frac { n ^ { 2 } } { r ^ { 2 } } \biggr ] u _ { n } = 0
$$

In order to solve this equation, we make the substitution:

$$
u _ { n } ( r ) = r ^ { c } w _ { n } ( x ) \mathrm { w i t h } x = \delta r ^ { d }
$$

where $c$ and $d$ are constants. Here, $c$ is set to be $- { \frac { 1 } { 2 } }$ and $d { = } 1$ . The general process to specify these two constants is provided in the appendix. S is a parameter can be selected at the operator's disposal. Eq.(14) can be transformed as follows:

$$
w _ { n } ^ { \prime \prime } ( x ) + \left[ \frac { k _ { 1 } ^ { 2 } - \beta ^ { 2 } } { \delta ^ { 2 } } + \frac { 1 } { \delta } \frac { 2 \alpha - \beta } { x } - \frac { n ^ { 2 } - 1 / 4 } { x ^ { 2 } } \right] w _ { n } ( x ) = 0
$$

According to the relative values of $( k _ { 1 } ^ { 2 } - \beta ^ { 2 } )$ ，solutions to Eq.(16) can be classified into three types.

Case 1(a) $( k _ { 1 } ^ { 2 } - \beta ^ { 2 } < 0 )$

Here, we choose $\begin{array} { r } { ( k _ { 1 } ^ { 2 } - \beta ^ { 2 } ) / \delta ^ { 2 } = - \frac { 1 } { 4 } } \end{array}$ and set $\kappa = ( 2 \alpha - \beta ) / \delta$ so that Eq.(16) becomes:

$$
w _ { n } ^ { \prime \prime } ( x ) + \left[ - { \frac { 1 } { 4 } } + \kappa x ^ { - 1 } + ( { \frac { 1 } { 4 } } - n ^ { 2 } ) x ^ { - 2 } \right] w _ { n } ( x ) = 0
$$

which is known as Whittaker's Equation 20. The general solution is:

$$
w _ { n } ( x ) = A _ { n } M _ { \kappa , n } ( x ) + B _ { n } W _ { \kappa , n } ( x )
$$

where $M _ { \kappa , n } ( \boldsymbol { x } )$ and $W _ { \kappa , n } ( x )$ are Whittaker functions.

Case $I ( b ) ( k _ { 1 } ^ { 2 } - \beta ^ { 2 } = 0 )$

We chose $\left( 2 \alpha - \beta \right) = 4 \delta$ and set $\textstyle \upsilon = n - { \frac { 1 } { 2 } }$ so that Eq.(16) becomes:

$$
w _ { n } ^ { \prime \prime } ( x ) + \left[ \frac { 1 } { 4 } x ^ { - 1 } - \upsilon ( \upsilon + 1 ) x ^ { - 2 } \right] w _ { n } ( x ) = 0
$$

which is related to the Bessel's equation. The general solution of Eq.(19) is:

$$
w _ { n } ( x ) = \sqrt { x } \left\{ A _ { n } J _ { 2 n } ( \sqrt { x } ) + B _ { n } Y _ { 2 n } ( \sqrt { x } ) \right\}
$$

where $J _ { n } ( )$ and $Y _ { n } ( )$ are the Bessel function of the first and second type, respectively.

Case $I ( c ) ( k _ { 1 } ^ { 2 } - \beta ^ { 2 } > 0 )$

We chose $( k _ { 1 } ^ { 2 } - \beta ^ { 2 } ) / \delta ^ { 2 } = 1$ and set $\eta = - ( 2 \alpha - \beta ) / 2 \delta$ and $\textstyle \upsilon = n - { \frac { 1 } { 2 } }$ SO that Eq.(16) becomes:

$$
w _ { n } ^ { \prime \prime } ( x ) + \left[ 1 - 2 \eta x ^ { - 1 } - \upsilon ( \upsilon + 1 ) x ^ { - 2 } \right] w _ { n } ( x ) = 0
$$

which is the Coulomb wave equation. Its general solution is:

$$
w _ { n } ( x ) = A _ { n } F _ { { n - 1 } / 2 } ( \eta , x ) + B _ { n } G _ { { n - 1 } / 2 } ( \eta , x )
$$

where $F _ { \upsilon } ( \eta , x )$ is the regular Coulomb wave function and $G _ { \upsilon } ( \eta , x )$ is the irregular Coulomb wave function.

Case 2: In this case, the shear modulus is a Gaussian function of $r$ and $k ^ { 2 } ( r )$ is a linear function of $r ^ { 2 }$ as follows:

$$
\mu ( r ) = \mu _ { 1 } e ^ { - \beta r ^ { 2 } } , \left[ k ( r ) \right] ^ { 2 } = k _ { 1 } ^ { 2 } + \gamma r ^ { 2 }
$$

where $\mu _ { 1 } , \ \mathsf { \beta } , \ k _ { 1 } ^ { 2 }$ ， and $\gamma$ are constants that are determined in the same manner as in Case 1. The expression for $K ( r )$ is:

$$
K ( r ) = 2 \beta - \beta ^ { 2 } r ^ { 2 }
$$

So the corresponding Eq.(1O) becomes:

$$
{ \frac { d ^ { 2 } u _ { n } } { d r ^ { 2 } } } + { \frac { 1 } { r } } { \frac { d u _ { n } } { d r } } + \Biggl [ k _ { 1 } ^ { 2 } + 2 \beta + ( \gamma - \beta ^ { 2 } ) r ^ { 2 } - { \frac { n ^ { 2 } } { r ^ { 2 } } } \Biggr ] u _ { n } ( r ) = 0
$$

We make the similar substitution as Case 1 to solve this problem:

$$
u _ { n } ( r ) = r ^ { - 1 } w _ { n } ( x ) \ { \mathrm { ~ w i t h ~ } } x = \delta r ^ { 2 }
$$

Similarly, $\delta$ is a parameter that can be selected at our disposal. Eq. (25) is transformed to:

$$
w _ { n } ^ { \prime \prime } ( x ) + \left[ \frac { \gamma - \beta ^ { 2 } } { 4 \delta ^ { 2 } } + \frac { 1 } { 4 \delta } \frac { k _ { 1 } ^ { 2 } + 2 \beta } { x } - \frac { n ^ { 2 } - 1 } { 4 x ^ { 2 } } \right] w _ { n } ( x ) = 0
$$

As before, according to the relative values of $( \gamma - \beta ^ { 2 } )$ , solutions to Eq.(27） can be also classified into three types.

Case 2(a) $( \gamma - \beta ^ { 2 } < 0 )$ （20 We chose $( \gamma - \beta ^ { 2 } ) / \delta ^ { 2 } = - 1$ and set $\kappa = ( k _ { 1 } ^ { 2 } + 2 \beta ) / 4 \delta$ so that Eq. (27) becomes:

$$
w _ { n } ^ { \prime \prime } ( x ) + \left[ - \frac { 1 } { 4 } + \kappa x ^ { - 1 } + ( \frac { 1 } { 4 } - \frac { n ^ { 2 } } { 4 } ) x ^ { - 2 } \right] w _ { n } ( x ) = 0
$$

the general solution to which is:

$$
w _ { n } ( x ) = A _ { n } M _ { \kappa , n / 2 } ( x ) + B _ { n } W _ { \kappa , n / 2 } ( x )
$$

Case $2 ( b ) ( \gamma - \beta ^ { 2 } = 0 )$

We choose $k _ { 1 } ^ { 2 } + 2 \beta = \delta$ and set $\textstyle \upsilon = { \frac { n - 1 } { 2 } }$ so that Eq. (27) becomes Eq. (19), the general solution to which is:

$$
w _ { n } ( x ) = \sqrt { x } \left\{ A _ { n } J _ { n } ( \sqrt { x } ) + B _ { n } Y _ { n } ( \sqrt { x } ) \right\}
$$

Case $2 ( c ) \left( \gamma - \beta ^ { 2 } > 0 \right)$

We chose $\gamma - \beta ^ { 2 } = 4 \delta ^ { 2 }$ and set $\begin{array} { r } { \eta = - \frac { k _ { 1 } ^ { 2 } + 2 \beta } { 8 \delta } } \end{array}$ and $\textstyle \upsilon = { \frac { n - 1 } { 2 } }$ so that Eq. becomes Eq. (21). The general solution of Eq. (27) is thus:

$$
w _ { n } ( x ) = A _ { n } F _ { _ { ( n - 1 ) / 2 } } ( \eta , x ) + B _ { n } G _ { _ { ( n - 1 ) / 2 } } ( \eta , x )
$$

# 4.Analytical Solutions of Single Scattering Problems

![](images/f6f5e1ac7a726dc82526c69aa03475aa9a15419a607a2d82b6e8f83fc133f298.jpg)  
Fig.1 Schematic of single scattering problem with a radially gradient interphase layer

In this work, the single scattering of SH waves by a cylindrical fiber with the two interphase layers discussed above was investigated. Figure 1 shows a schematic diagram ofthe single scattering by a cylindrical fiber with a radially gradient interphase layer. The inner radius of the interphase layer is $a$ and the outer radius is $b$ . The incident wave is a plane SH wave propagating in the positive $x$ direction with a unit magnitude. Under the exciting of this incident wave, the total wave in the matrix, interphase layer, and the fibers can be expressed as follows:

$$
w ( r , \theta ) = \left\{ \begin{array} { l l } { \displaystyle \sum _ { n = 0 } ^ { \infty } \left[ \varepsilon _ { n } \mathbf { i } ^ { n } J _ { n } \left( k _ { m } r \right) + A _ { n } H _ { n } ^ { ( 1 ) } \left( k _ { m } r \right) \right] \cos \left( n \theta \right) , } & { \quad r > b } \\ { \displaystyle \sum _ { n = 0 } ^ { \infty } \left[ C _ { n } \varphi _ { 1 } \left( r \right) + D _ { n } \varphi _ { 2 } \left( r \right) \right] \cos \left( n \theta \right) , } & { \quad a < r < b } \\ { \displaystyle \sum _ { n = 0 } ^ { \infty } B _ { n } J _ { n } \left( k _ { f } r \right) \cos \left( n \theta \right) , } & { \quad r < a } \end{array} \right.
$$

where $ { \varepsilon } _ { 0 } = 1$ and $\varepsilon _ { n } = 2 \ ( n \neq 0 ) , \ H _ { n } ^ { ( 1 ) } ( )$ is the nth order Hankel function of the first type; $\varphi _ { 1 } \left( r \right)$ and $\varphi _ { 2 } \left( r \right)$ are two functions with detailed expressions dependent on the type and material properties of the interphase layer. In Case 1, $\varphi _ { 1 } \left( r \right)$ and $\varphi _ { 2 } \left( r \right)$ can be expressed as follows

$$
\begin{array} { r l r }   { [ \varphi _ { 1 , 2 } ( r ) = \frac { 1 } { \sqrt { r \mu ( r ) } } \Big [ M _ { \kappa , n } ( \delta r ) \pm \mathbf { i } W _ { \kappa , n } ( \delta r ) \Big ] , } & { k _ { 1 } ^ { 2 } - \beta ^ { 2 } < 0 } \\ & { } \\ { \displaystyle \mathcal { G } _ { 1 , 2 } ( r ) = \frac { 1 } { \sqrt { r \mu ( r ) } } \sqrt { \delta r } H _ { 2 n } ^ { ( 1 ) , ( 2 ) } ( \sqrt { \delta r } ) , } & { k _ { 1 } ^ { 2 } - \beta ^ { 2 } = 0 } \\ & { } \\ { \displaystyle \varphi _ { 1 , 2 } ( r ) = \frac { 1 } { \sqrt { r \mu ( r ) } } \Bigg [ F _ { n - \frac { 1 } { 2 } } ( \eta , \delta r ) \pm \mathbf { i } G _ { n - \frac { 1 } { 2 } } ( \eta , \delta r ) \Bigg ] , } & { k _ { 1 } ^ { 2 } - \beta ^ { 2 } > 0 } \end{array}
$$

In Case 2, $\varphi _ { 1 } \left( r \right)$ and $\varphi _ { 2 } \left( r \right)$ are:

$$
\left\{ \begin{array} { l l } { \displaystyle \varphi _ { 1 , 2 } ( \boldsymbol { r } ) = \frac { 1 } { r \sqrt { \mu ( \boldsymbol { r } ) } } \Big [ M _ { \kappa , n / 2 } ( \delta \boldsymbol { r } ^ { 2 } ) \pm \mathbf { i } W _ { \kappa , n / 2 } ( \delta \boldsymbol { r } ^ { 2 } ) \Big ] , } & { \gamma - \beta ^ { 2 } < 0 } \\ { \displaystyle \varphi _ { 1 , 2 } ( \boldsymbol { r } ) = \frac { 1 } { r \sqrt { \mu ( \boldsymbol { r } ) } } \sqrt { \delta } r H _ { n } ^ { ( 1 ) , ( 2 ) } ( \sqrt { \delta } r ) , } & { \gamma - \beta ^ { 2 } = 0 } \\ { \displaystyle \varphi _ { 1 , 2 } ( \boldsymbol { r } ) = \frac { 1 } { r \sqrt { \mu ( \boldsymbol { r } ) } } \Bigg [ F _ { \frac { n - 1 } { 2 } } ( \eta , \delta \boldsymbol { r } ^ { 2 } ) \pm \mathbf { i } G _ { \frac { n - 1 } { 2 } } ( \eta , \delta \boldsymbol { r } ^ { 2 } ) \Bigg ] , } & { \gamma - \beta ^ { 2 } > 0 } \end{array} \right.
$$

$A _ { n } , \ B _ { n } , \ C _ { n } ,$ and $D _ { n }$ are the expansion coefficients to be determined by the continuity conditions of displacements and stresses across the interfaces at $r = a$ and $b$ ：

$$
\left\{ \begin{array} { c } { \displaystyle w \Big | _ { r = a ^ { + } } = w \Big | _ { r = a ^ { - } } } \\ { \displaystyle \mu \frac { \hat { \sigma } w } { \hat { \sigma } r } \Big | _ { r = a ^ { + } } = \mu \frac { \hat { \sigma } w } { \hat { \sigma } r } \Big | _ { r = a ^ { - } } } \end{array} \right.
$$

As the expansion coefficients $A _ { n } , \ B _ { n } , \ C _ { n }$ ,and $D _ { n }$ （ $( n = 1 , 2 , \cdots , n _ { \operatorname* { m a x } } )$ are obtained, the far-field scattering magnitude l3 and the scattering cross section 8 can be calculated as fo llo ws:

$$
\left\{ \begin{array} { l l } { \displaystyle f ( \theta ) = \sum _ { n = 0 } ^ { \infty } \varepsilon _ { n } \frac { A _ { n } } { \mathbf { i } ^ { n } } \cos \left( n \theta \right) } \\ { \displaystyle \sigma _ { s } = \frac { 2 } { k _ { m } } \sum _ { n = 0 } ^ { \infty } \varepsilon _ { n } \left| A _ { n } \right| ^ { 2 } } \end{array} \right.
$$

For the sake of illustration, the single scattering of SH waves by a Sic fiber embedded in an aluminum matrix with a radially gradient interphase layer was solved in this work.The material properties are listed in Table 1. Figure 2 plots the calculated $\sigma _ { s }$ changes with $k _ { m } a$ for the interphase types (Case 1 and Case 2). The results of the approximate approach (i.e., dividing the interphase layer into multiple homogeneous sub-layers) are also plotted for comparison. Both approaches yield similar results.

Table 1: Material properties of Sic and Al   

<html><body><table><tr><td>Sic</td><td>Pf (kg/m^3)</td><td>μf(GPa)</td></tr><tr><td rowspan="2">Al</td><td>3181</td><td>188.1</td></tr><tr><td>Pm (kg/m^3)</td><td>μm(GPa)</td></tr><tr><td></td><td>2706</td><td>26.7</td></tr></table></body></html>

![](images/36b3540fedeb4668012908420871a17679fedc7820281ce5d8a72fbc2eb5d1fc.jpg)  
Fig. 2 Comparison of $\sigma _ { s }$ between current theoretical solutions and approximate method for interphase layer types (Case 1, Case 2) at several frequencies. Note: $a { = } 7 1 \mathrm { u m }$ and interphase layer thickness is $h = 0 . 1 ~ a$ （204号

# 5. Conclusions

This paper reported the analytic solutions to the single scattering of SH waves by a cylindrical fiber with two specific radially gradient interphase layers, using the method proposed by P.A. Martin. In the first case, the shear modulus is an exponential function of $r$ and $k ^ { 2 }$ is a linear function of $1 / r ;$ ：in the second case, the shear modulus is a Gaussian function of $r$ and $k ^ { 2 }$ is a linear function of $r ^ { 2 }$ . Besides SH waves, the extension of the current method to other waves has also been mentioned.

An example of the single scattering of SH waves by a Sic fiber in an aluminum matrix was calculated and the scattering cross sections were compared against the values obtained by dividing the continuous varying interphase layer into multiple homogeneous sub-layers. The two approaches yielded similar results. The main contribution of this work is that it provides several benchmark solutions for inhomogeneous problems.

# Acknowledgements

This work was supported by the Chinese National Natural Science Fund (Grant 11502036） and the Natural Science Fund of the city of Chongqing (Grant cstc2015jcyjA0577). The Guangxi Key Laboratory of Manufacturing Systems and Advanced Manufacturing Technology (No:16-380-12-014k) also provided financial support.

# References:

1Lord.Rayleigh， Philosophical magazine 41 (1871).   
2S. I. Rokhlin, W. Huang, and Y. C. Chu,Ultrasonics 33 (5), 351 (1995).   
3P.C Waterman and Rohn Truell, JMath Phys 2 (4), 512 (1960).   
4Vijay K. Varadan, Vasundara V. Varadan, and Yih-Hsing Pao,JAcoust Soc Am 63 (5),1310 (1978).   
5V. K.Varadan, Y. Ma,and V. V. Varadan,JAcoust Soc Am 77 (2), 375 (1985).   
6S. K. Bose and A. K. Mal, Journal of the Acoustical Society of America 55 (3), 519 (1974).   
7Leslie L.Foldy， Physical Review 67(Copyright (C) 2009 The American Physical Society),107 (1945).   
8C.C.Mow and Y.H.Pao, The diffaction of elastic waves and dynamic stress concentrations. (1971).   
9S. K. Kanaun and V. M. Levin, Archive of Applied Mechanics 73 (1-2), 105 (2003).   
10J. Y. Kim, J. G. Ih,and B. H. Lee,Journal of the Acoustical Society of America 97(3),1380 (1995).   
11P. G. J. Bussink, P.L. Iske,J. Oortwijn,andG.L. M. M. Verbist，Journal of the Mechanics and Physics of Solids 43 (10), 1673 (1995).   
（204号 $^ { 1 2 } \mathrm { S }$ K. Kanaun and V. M. Levin,International Journal of Solids and Structures 40 (18), 4859 (2003).   
13A. N. Norris and J. M. Conoir,JAcoust Soc Am 129 (1),104 (2011).   
14Y. Shindo, H. Nozaki, and S. K. Datta，Journal of Applied Mechanics, Transactions ASME 62 (1), 178 (1995).   
（204号 ${ } ^ { 1 5 } \mathrm { Y } .$ Shindo and N. Niwa, Acta Mech 117 (1-4),181 (1996).   
16Y. Shindo, N. Niwa,and R. Togawa, International Journal of Solids and Structures 35 (7-8),733 (1998).   
$^ { 1 7 } \mathrm { R } .$ B. Yang and A. K. Mal, Intermational Journal of Engineering Science 34 (1), 67 (1996).   
（204号 $^ { 1 8 } \mathrm { W }$ Huang, S. I. Rokhlin,and Y. J. Wang,Ultrasonics 33 (5),365 (1995).   
（2 $^ { 1 9 } \mathrm { L }$ . W. Cai and J. Sanchez-Dehesa, JAcoust Soc Am 124 (5),2715 (2008).   
（20 $^ { 2 0 } \mathrm { P } .$ A. Martin, JAcoust Soc Am 111 (5), 2013 (2002).

# Appendix: General approach to make the second transformation

Define $u _ { n } ( r ) = r ^ { c } w _ { n } ( x )$ with $x = \delta r ^ { d }$ ， $c$ and $d$ are two constants to be determined. The first and second derivatives of $u _ { n } ( r )$ with regard to $r$ can then be expressed as

$$
\begin{array} { r l } & { \left\{ u _ { n } ^ { \prime } ( r ) = c r ^ { c - 1 } w _ { _ n } ( x ) + r ^ { c + d - 1 } w _ { n } ^ { \prime } ( x ) \delta d \right. } \\ & { \left. \vphantom { \int } u _ { n } ^ { \prime } ( r ) = c ( c - 1 ) r ^ { c - 2 } w _ { _ n } ( x ) + \delta d ( 2 c + d - 1 ) r ^ { c + d - 2 } w _ { _ n } ^ { \prime } ( x ) + \delta ^ { 2 } d ^ { 2 } r ^ { c + 2 d - 2 } w _ { n } ^ { \prime \prime } ( x ) \right. } \end{array}
$$

Substitution of the expressions of $u _ { n } ^ { \prime } ( r )$ and $u _ { n } ^ { \prime \prime } ( r )$ into Eq.(14), we can obtain

$$
\begin{array} { l } { { { c ^ { 2 } r ^ { c - 2 } w _ { n } ( x ) + \delta d ( 2 c + d ) r ^ { c + d - 2 } w _ { n } ^ { \prime } ( x ) + \delta ^ { 2 } d ^ { 2 } r ^ { c + 2 d - 2 } w _ { n } ^ { \prime \prime } ( x ) + . . . } } } \\ { { { \displaystyle { \left( k _ { 1 } ^ { 2 } - \beta ^ { 2 } + \frac { 2 \alpha - \beta } { r } - \frac { n ^ { 2 } } { r ^ { 2 } } \right) r ^ { c } w _ { n } ( x ) = 0 } } } } \end{array}
$$

Therefore, if Eq.(A.2) is required to have the form of the confluent hypergeometric equation, the coefficients $c$ and $d$ should satisfy

$$
2 c + d = 0
$$

The term of the first derivative of $w _ { n } ^ { \prime } ( x )$ disappears. Then Eq.(A.2) becomes

$$
\delta ^ { 2 } d ^ { 2 } r ^ { 2 d - 2 } w _ { n } ^ { \prime } ( x ) + \left( k _ { 1 } ^ { 2 } - \beta ^ { 2 } + \frac { 2 \alpha - \beta } { r } - \frac { n ^ { 2 } - c ^ { 2 } } { r ^ { 2 } } \right) w _ { n } ( x ) = 0
$$

Then $d$ can be set to be 1 and $c = - { \frac { 1 } { 2 } }$ Then Eq.(A.4) is simplified as

$$
w _ { n } ^ { \prime \prime } ( x ) + \left( \frac { k _ { 1 } ^ { 2 } - \beta ^ { 2 } } { \delta ^ { 2 } } + \frac { 1 } { \delta } \frac { 2 \alpha - \beta } { x } - \frac { n ^ { 2 } - 1 / 4 } { x ^ { 2 } } \right) w _ { n } ( x ) = 0
$$