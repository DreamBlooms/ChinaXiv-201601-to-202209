# Analysis of the Hydroelastic Performance of Very Large Floating Structures Based on Multi-Modules Beam Theory

Jin $X u ^ { a , b }$ ,Yonggang Sunʰ , Zhifu $L i ^ { c }$ ,Xiantao Zhangd, Da Lue\*

aPLAUniversity of Science and Technology,Nanjing,PR China; b Wuxi First Scientific Research Institute,Wuxi,PR China; cCollegeofShipbuilding Engineering,Harbin Engineering University,HeilongjiangPRChina d Center for Ofshore Foundation Systems,School of Civil,Environmental and Mining Engineering inthe University ofWestern Australia,Australia; eState Key Laboratory of Ocean Engineering,Shanghai Jiao Tong University, Shanghai,PR China;

# ABSTRACT

The hydroelastic behavior of very large floating structures (VLFSs） is investigated based on the proposed multi-modules beam theory (MBT).To carry out the analysis,the VLFS is first divided into multiple sub-modules that are connected through their gravity center by a spatial beam with specific stiffness.The external force exerted on the sub-modules includes the wave hydrodynamic force as well as the beam bending force due to the relative displacements of different sub-modules. The wave hydrodynamic force is computed based on three-dimensional incompressible velocity potential theory,and the boundary element method with the free surface Green function as the integral kernel is adopted to numerically find the solution. The beam bending force is expressed in the form of a stiffness matrix. The coupled motion equation is established according to the continuous conditions of the displacement and force. The motion response defined at the gravity center of the sub-modules is solved by the multi-body hydrodynamic control equations,then both the displacement and the structure bending moment of the VLFS are determined from the stiffness matrix equations.To account for the moving point mass effects,the proposed method is extended to the time domain based on impulse response function (IRF) theory. The accuracy of the proposed method is verified by comparison with existing results.Detailed results through the displacement and bending moment of the VLFS are provided to show the influence of the number of the sub-modules,and the influence of the moving point mass.

Keywords: VLFS, time domain, multi-body, hydroelasticity, moving point mass.

# 1. Introduction

A very large floating structure (VFLS) is a unique type of oceanic structure that embraces a range of unprecedented parameters. VLFSs are designed primarily for floating airports and as a dock for calm waters on open seas.

Because it is larger than existing floating structures,A VLFS's flexibility must be taken into account. Also,for a VLFS to be used as an airport or bridge, time-varying moving loads must be considered, e.g., the analysis of the displacement and bending moment of a very large floating bridge in calm water with some moving point masses (Wu et al.，1998；Fu, 2005),or the displacement response of a VLFS in waves with a moving load point (Endo, 2Ooo; Shin et al., 2001).

Simulations of the displacement and bending moment of a VLFS are mostly based on hydroelastic theory to date.In the frequency domain,hydroelastic theory was initially developed in two dimensions (Bets et al.,1977; Bishop and Price,1977). Wu (1984) extended the work of Bishop and Price to three dimensions，and Chen et al.(2Oo3a) developed three-dimensional nonlinear hydroelastic theory. Hydroelastic theory can be also extended to the time domain (Wang Dayun, 1996; Liu and Sakai,2002).

To account for the effects of moving point masses, simulations must be carried out in the time domain. Chakrabarti (2O01） and Jacobsen (2OO6） analyzed the hydrodynamic interactions of a multi-body system based on the impulse response function method (IRF),but the bodies are not connected to each other. Shen et al. (2OO2) presented procedures for numerical solutions of system motion responses of a multi-rigid-body in the time domain. A moving load on a rigid body has also been studied (Wu and Sheu,1996; Shen et al., 2003).

An approximation theory for the analysis of the displacement and bending moment of a VLFS, based on multi-modules beam theory (MBT),was recently developed by Lu et al.(2015, 2016).In this method,the VLFS is divided into sub-modules that are connected by a beam with specific stiffness through the gravity center of the sub-modules. The external force exerted on the sub-modules includes the wave hydrodynamic force as well as the beam bending force due to the relative displacements of different sub-modules. Then, the final hydroelastic response equations can be established based on multi-body hydrodynamic theory and beam theory. The displacement along the VLFS can be obtained by solving these equations,and then the structural deformation as

well as the section loads can be computed.

In this paper, Lu's methodology for the computation of the displacement along the VLFS has been improved,and some new methods have been developed for the computation of the section loads.We discard the beam bending method of Lu et al.(2O15，2O16) and calculate the displacement response of the structure by the method of matrix transformation. To obtain the complete bending moment distribution,the high-order difference is obtained for a few accurate moment values. This method is more rigorous,and the displacement and bending moment along the whole VLFS can be obtained. This paper avoids the resonance problem caused by small gap reasonably when calculating the hydrodynamic coefficient (Miao et al., 2000).

The methodology has been extended to time domain analysis based on IRF theory,and this paper attempts to simulate the hydroelastic response of the VLFS in waves with some moving point mass. Study on the moving load of an elastic floating body under wave action is the foundation of research on landing pontoons,but there is litle literature. This paper combines MBT (Lu, 2015), IRF theory (Cummins,1962; Ogilvie,1964),and the analysis method of moving load on rigid floating body. MBT and IRF are used in the time domain analysis of a VLFS; the floating body in the moving load is treated as a rigid body,and the inertia force introduced by the moving load is added to the wave force of this floating body. Although the method is very approximate, the results can reflect the response characteristics of the structure.

# 2.Mathematical formulation

Lu's method is based on potential theory and multi-body theory. For the hydrodynamic aspect, the ideal fluid assumption is adopted,i.e.,the fluid is inviscid, irrotational,and incompressible. The incident wave amplitude is assumed to be small relative to a characteristic wavelength and body dimension. For the structural aspect, a stiffness matrix is introduced between two adjacent modules to consider the flexible structure.

![](images/d7225cc1b8e6a997888ece6f83b1c204979119cf9acc0c80fca3c0c60fa139d1.jpg)  
Fig.1Definition of the fluid and structure boundaries

Based on the assumptions of an ideal fluid and linearity,the velocity potential can be decomposed into three parts as follows:

$$
\scriptstyle \phi = \phi _ { I } + \phi _ { D } + \phi _ { R }
$$

Where $\phi _ { I } , \ \phi _ { D }$ and $\phi _ { R }$ denote，respectively,the incident wave potential, diraction wave potential,and radiation wave potential.The incident, diffraction potential and radiation potential satisfy the following boundary conditions:

$$
o n \sum _ { q = 1 } ^ { n } S _ { q }
$$

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \mathrm { i v } _ { \phi } ^ { \mathrm { S } } = 0 , } \\ { \mathrm { i v } _ { \phi } ^ { \mathrm { S } } = 0 , } \\ { - \phi ^ { \mathrm { a } } \phi ^ { \mathrm { a } } \phi ^ { \mathrm { a } } \frac { \partial \phi } { \partial z } = \Omega , } \\ { \frac { \partial \phi } { \partial z } = 0 , } \\ { \mathrm { i v } _ { \phi } ^ { \mathrm { S } } + \phi _ { \phi } ^ { \mathrm { a } } \frac { \partial \phi } { \partial z } = \Omega , } \\ { \frac { \partial \phi } { \partial z } \frac { \partial \phi } { \partial z } = \Omega , } \\ { \frac { \partial \phi } { \partial z } \frac { \partial \phi } { \partial z } = \frac { \partial \phi } { \partial z } , } \\ { \frac { \partial \phi } { \partial z } = 0 , } \end{array} \right. } \end{array}
$$

$$
\begin{array} { r l } & { \displaystyle { | \frac { \hat { \sigma } \phi _ { _ { R k } } } { \hat { \sigma } n _ { j } } = 0  \qquad } \quad \quad \quad \quad \quad o n \sum _ { j = 1 , j \neq k } ^ { n } S _ { j } } \\ & { \displaystyle { | \operatorname* { l i m } _ { r \to \infty } \sqrt { r } ( \frac { \hat { \sigma } \phi _ { _ { R k } } } { \hat { \sigma } r } - \frac { i \omega ^ { 2 } } { g } \phi _ { _ { R k } } ) = 0 \qquad } \quad \quad \quad o n S _ { \infty } } \end{array}
$$

As shown in Fig. 1, $\Omega$ is the fluid domain,and $S _ { F } , S _ { B } , S _ { k } .$ and $S _ { \infty }$ are the free surface,bottom surface,wetted body surface of the $\boldsymbol { k } ^ { \mathrm { { t h } } }$ module,and boundary surface at infinity of the fluid, respectively. nk represents the outward-directed unit vector normal to the wetted surface of the kth module. $\vec { V } _ { s _ { k } }$ is the speed on the wetted surface of the ${ \boldsymbol { k } } ^ { t h }$ module. $\phi$ is the velocity potential. After the velocity potential $\phi$ is obtained, the added mass and the radiation damping of the bodies,as well as the wave excitation force, can be calculated.

In the frequency domain,the excitation forces are related to the incident and diffracted potential as follows,

$$
\vec { F } _ { e x k } = \rho i \omega \int \limits _ { S _ { 0 k } } [ ( \phi _ { \mathrm { I } } + \phi _ { \mathrm { D } } ) \cdot \vec { n } _ { k } d S
$$

where $I$ $I , \vec { F } _ { e x k } , \rho , \omega$ and $S _ { O k }$ are the imaginary unit ,wave excitation forces,fluid density, wave frequency and average wetted surfaces, respectively.

The added mass and damping coefficient is given by:

$$
[ a ] + \frac { i } { \omega } [ b ] = \rho \underset { S _ { 0 k } } { \iint } \phi _ { R } \cdot \vec { n } _ { k } d S
$$

# 2.2Motion equation

According to Lu's method,a VLFS is divided into many modules,and the equation of six degree-of-freedom (DOF) motion in the frequency domain for a given wave amplitude and wave frequency $\omega$ can be written as follows:

$$
\begin{array} { c } { { \displaystyle \left( { - \omega ^ { 2 } \left( \left[ { \bf { M } } _ { \mathrm { { k } } } \right] + \left[ { a } _ { \scriptscriptstyle { k k } } \right] \right) - i \omega \left[ { b } _ { \scriptscriptstyle { k k } } \right] + \left[ { C } _ { k } \right] } \right) \left\{ { u } _ { k } \right\} + \sum _ { j = 1 , j \ne k } ^ { m } \left( { - \omega ^ { 2 } \left[ { a } _ { \scriptscriptstyle { k j } } \right] - i \omega \left[ { b } _ { \scriptscriptstyle { k j } } \right] } \right) \left\{ { u } _ { j } \right\} } } \\ { { + \left[ { \bf { K } } \right] _ { \scriptscriptstyle { 6 \times 6 m } } \left[ { U } \right] _ { \scriptscriptstyle { 6 m \times 1 } } = \left\{ { f } _ { \mathrm { e x k } } \right\} _ { \scriptscriptstyle { 6 \times 1 } } } } \end{array}
$$

where $m$ is the number of floating bodies, $[ M _ { k } ]$ is the mass (or inertia moment) matrix of body $k _ { \cdot }$ $[ a _ { k k } ]$ is the added mass (or added mass moment) matrix of body $k$ caused by the motion of the body itself, $[ b _ { k k } ]$ is the radiation damping matrix of body $k$ caused by the motion of the body itself, $\left[ C _ { k } \right]$ is the hydrostatic stiffness matrix of body $k _ { \mathrm { - } }$ $[ a _ { k j } ]$ is the added mass matrix of body $k$ induced by the motion of body $j , [ b _ { k j } ]$ is the radiation damping matrix of body $k$ caused by the motion of body j, $\{ f _ { e x k } \}$ is the wave excitation force (or moment) of body $k , [ U ]$ is the displacement matrix of $m$ bodies, $[ K ]$ is the stiffness matrix that shows the relationship between displacement and force, and $\left\{ u _ { k } \right\}$ is the six degree-of-freedom (DOF) displacement of body $k$ expressed as $( x _ { k } , y _ { k } , z _ { k } , \alpha _ { k } , \beta _ { k } ,$ /k). The number of equations is the same as the number of floating bodies.

Further, considering all modules,Eq.5 is extended to the form of an equation set,

$$
\begin{array} { r l } & { - \omega ^ { * } [ \begin{array} { c c c c c c } { [ M _ { 1 } ] - [ \alpha _ { 1 1 } ] } & { \cdots } & { [ \alpha _ { 1 k } ] } & { \cdots } & { [ \alpha _ { k , 1 } ] } & \\ { \vdots } & { \ddots } & { \vdots } & { \ddots } & { \vdots } \\ { [ \alpha _ { 1 } ] } & { \cdots } & { [ M _ { 1 } ] - [ \alpha _ { k } ] } & { \cdots } & { [ \alpha _ { k , 1 } ] } & \\ { \vdots } & { \ddots } & { \vdots } & { \ddots } & { \vdots } \\ { [ \alpha _ { n } ] } & { \cdots } & { [ \alpha _ { n } ] } & { \cdots } & { [ M _ { n } ] + [ \alpha _ { n d } ] } \end{array} ] [ U ] _ { \mathrm { s o n d } } } \\ &  \{ \begin{array} { c c c c c } { [ \begin{array} { c c c c c } { [ b _ { 1 } ] } & { \cdots } & { [ b _ { 3 } ] } & { \cdots } & { [ b _ { k } ] } \\ { \vdots } & { \ddots } & { \vdots } & { \ddots } & { \vdots } \\ { - i \alpha [ \beta _ { k } ] } & { \cdots } & { [ b _ { k } ] } & { \cdots } & { [ b _ { k } ] } \\ { \vdots } & { \ddots } & { \vdots } & { \ddots } & { \vdots } \\ { [ b _ { k } ] } & { \cdots } & { [ b _ { k } ] } & { \cdots } & { [ b _ { k } ] } \end{array} ] [ \begin{array} { c } { [ C _ { 1 } ] } \\ { C _ { 1 } } \\ { \vdots } \\ { \ddots } & { \vdots } \\ { [ C _ { k } ] } \end{array} ] \} + [ \begin{array} { c } { [ C _ { 1 } ] } \\ { \vdots } \\ { \vdots } \\ { \Gamma _ { k , n } } \end{array} ] } \\ &  = \{ \begin{array} { c } { [ \begin{array} { c c c c c } { [ b _ { 1 } ] } & { \cdots } & { [ b _ { k } ] } & { \cdots } & { [ b _ { k } ] } \\ { \Gamma _ { k , n } } & { \cdots } & { \Gamma _ { k , n } } \end{array} ] [ \begin{array} { c } { [ C _ { 1 } ] } \\ { \Gamma _ { k , n } } \\ { \Gamma _ { k , n } } \end{array} ] + [ \begin{array} { c } { \Gamma _ { k , n } } \\ { \Gamma _ { k , n + 1 } } \\ { \Gamma _ { k , n + 1 } } \\ { \Gamma _ { k , n } } \end{array} ] + [ \begin{array} { c } { \Gamma _ { k , n + 1 } } \\ { \Gamma _ { k , n + 1 } } \\ { \Gamma _ { k , n + 1 } } \\ { \Gamma _ { k , n + 1 } } \end{array} ] } \end{array} \end{array} \end{array}
$$

As a linear system, the coefficient matrix of unknowns $[ U ] _ { 6 m \times 1 }$ can be replaced by $[ K ]$ ,and Eq. 6 can be rewritten as

$$
\begin{array} { r } { \left[ \mathbf { K } ^ { \prime } \right] _ { 6 \mathrm { m } \times 6 m } \left[ U \right] _ { 6 m \times 1 } = \left\{ f _ { e x } \right\} _ { 6 \mathrm { m } \times 1 } } \end{array}
$$

where $[ K ]$ is the total stiffness matrix.The expressions for the stiffness matrix $[ K ]$ will be discussed in the following section.

# 2.3 Analysis of spatial beam

The six DOF motion of a module's center is restricted by the deformation condition of the equivalent beam between two modules.

As Lu (2O16) has written，each side of the beam element $i \mathrm { - } j$ has six components of displacements and forces:

$$
\begin{array} { r l } & { \left[ \mathbf { U } \right] _ { i - j } = \left( x _ { i } , y _ { i } , z _ { i } , \alpha _ { i } , \beta _ { i } , \gamma _ { i } , x _ { j } , y _ { j } , z _ { j } , \alpha _ { j } , \beta _ { j } , \gamma _ { j } \right) ^ { T } } \\ & { \left[ \mathrm { F } \right] _ { i - j } = \left( F x _ { i } , F y _ { i } , F z _ { i } , M x _ { i } , M y _ { i } , M z _ { i } , F x _ { j } , F y _ { j } , F z _ { j } , M x _ { j } , M y _ { j } , M z _ { j } \right) ^ { T } } \end{array}
$$

where $( F x _ { i } , F y _ { i } , F z _ { i } )$ are forces in the $i ^ { t h }$ cross section, and $( M x _ { i } , M y _ { i } , M z _ { i } )$ are the corresponding bending moments. Similar expressions can be obtained for the $j ^ { t h }$ cross section. Generally, the forces and moments are assumed to be imposed on the center of the cross-section of the beam element.

The relationship between $[ U ]$ and $[ F ]$ is:

$$
\big [ F \big ] _ { i - j } = \operatorname { \textbf { \textup { K } } } \big ] _ { i - j } \big [ U \big ] _ { i - j }
$$

where $[ K ] _ { i - j }$ is the stiffness matrix that is used in Eq. 5,which is shown in the appendix.The specific instructions for the matrix are described by McGuire et al. (2Ooo).The size of the matrix

is $1 2 \times 1 2$ . The matrix is affected by the size of each body, Young's modulus,and the Poisson ratio. When there are $m$ floating bodies,the size of the total matrix [K'] in Eq.7 will be $6 m \times 6 m$

# 3.Hydroelastic response of the VLFS

# 3.1Numerical model

To illustrate this methodology,we use the model mentioned by Yokosuka (Yago and Endo, 1996). This VLFS is a scaled model of the Mega-Float, constructed and developed for use in sheltered waters. The wave amplitude is $1 \mathrm { ~ m ~ }$ ,and the main parameters are listed in Table 1. The grid in the hydrodynamic calculation of the VLFS is $1 6 0 { \times } 1 0 { \times } 1 0$

Table1.Details of the VLFS model   

<html><body><table><tr><td>Parameters</td><td>Units</td><td>Value</td></tr><tr><td>Length</td><td>L/m</td><td>300</td></tr><tr><td>Width</td><td>B/m</td><td>60</td></tr><tr><td>Depth</td><td>D/m</td><td>2</td></tr><tr><td>Draft</td><td>d/m</td><td>0.5</td></tr><tr><td>Young's modulus</td><td>E/N/m²</td><td>1.19e10</td></tr><tr><td>Poisson ratio</td><td>V</td><td>0.13</td></tr><tr><td>Density</td><td>p/kg/m³</td><td>256.25</td></tr><tr><td>Water depth</td><td>H/m</td><td>58.5</td></tr></table></body></html>

3.2Displacement along the VLFS

Lu (2015, 2016) proposed a method for the computation of the displacement along the VLFS based on spatial beam theory. In this paper, a more generalized method will be developed.

It can be seen from Eq.9 that once the displacement $[ U ]$ has been solved, the section load $[ F ]$ can be computed. The displacement along a given spatial beam can be calculated based on the end interfaces' displacements and section loads.

Eq. 9 can be rewritten as

$$
{ \begin{array} { r l } { { \mathord { \left[ { \begin{array} { l } { F _ { \mathrm { i } } } \\ { F _ { j } } \end{array} } \right] } } = { \left[ \begin{array} { l l } { K _ { i i } } & { K _ { i j } } \\ { K _ { j i } } & { K _ { j j } } \end{array} \right] } { \mathord { \left[ { \begin{array} { l } { U _ { i } } \\ { U _ { j } } \end{array} } \right] } } } \end{array} }
$$

The end interface loads $F _ { i }$ and $F _ { j }$ can be obtained once the displacement $U _ { i }$ and $U _ { j }$ have been solved.

To get the displacement $U _ { l }$ and section load $F _ { l }$ defined at any position between the two end interfaces,Eq.1O is modified as follows:

$$
\begin{array} { r } { \bigg [ \begin{array} { l } { F _ { i } } \\ { F _ { l } } \end{array} \bigg ] = \bigg [ \begin{array} { l l } { K _ { i i } } & { K _ { i l } } \\ { K _ { l i } } & { K _ { l l } } \end{array} \bigg ] \bigg [ \boldsymbol { U } _ { i } \bigg ] } \end{array}
$$

Then the displacement $U _ { l }$ and section load $F _ { l }$ defined at section $l$ can be computed by

$$
\begin{array} { r l } & { \Big \{ \big [ \boldsymbol { U } _ { \iota } \big ] = \big [ \boldsymbol { K } _ { i l } \big ] ^ { - 1 } \left( \big [ \boldsymbol { F } _ { i } \big ] - \big [ \boldsymbol { K } _ { i i } \big ] \big [ \boldsymbol { U } _ { i } \big ] \right) } \\ & { \Big \{ \big [ \boldsymbol { F } _ { \iota } \big ] = \big [ \boldsymbol { K } _ { l i } \big ] \big [ \boldsymbol { U } _ { i } \big ] + \big [ \boldsymbol { K } _ { l l } \big ] \Big \{ \big [ \boldsymbol { K } _ { i l } \big ] ^ { - 1 } \left( \big [ \boldsymbol { F } _ { i } \big ] - \big [ \boldsymbol { K } _ { i i } \big ] \big [ \boldsymbol { U } _ { i } \big ] \right) \Big \} } \end{array}
$$

Lu's method (Lu, 2O15） can only calculate the vertical displacement response.Eq.12 can provide the six-degree-of-freedom displacement along the VLFS,which is a big improvement over the original method proposed by Lu (2015, 2016).

The present results are compared with experimental results (Yago and Endo,1996） and numerically calculated data from three-dimensional hydroelastic theory (Fu et al., 2O07),which are shown in Fig.2.In this part, the continuous VLFS is divided into five modules with O-degree wave direction. Values calculated in this paper are denoted by “Present.” Experimental values (Yago and Endo 1996) are denoted by“Experiment,” and numerically calculated data from three-dimensional hydroelasticity theory (Fu et al.,2O07） are denoted by“Fu et al 2O07.”These results are in good agreement. The hydrodynamic responses of the model in 30-and 6O-degree wave directions are calculated. The vertical displacement response of the model is compared with the results of three-dimensional hydroelasticity theory (Fu, 2OO5). The results are listed in the appendix(Fig.15).

![](images/9c2df1609847ba30290f0b9353f934eb83feaaf2957b2156a5d12cedad625a46.jpg)

![](images/8b70116fa689344f0c5430807856e7416117678abdaaa2ffda6141ac58d35d0b.jpg)  
Fig.2 Vertical response contrast of VLFS

# 3.3 Bending moment distribution along the VLFS

To obtain the moment of the VLFS,Lu (2Ol6) proposed an equal force method based on the Darren Bell principle. It is equivalent to $m$ sets of forces being exerted on the center of each module for the VLFS.The whole problem can be described as follows: a free beam is subjected to a number of concentrated forces to reach static equilibrium, and to obtain the moment distribution of the beam section. This is shown in Fig.3.The forces conform to the following formulae:

$$
\big [ F \big ] _ { 6 m \times 1 } = \big [ \mathrm { K } \big ] _ { 6 \times 6 m } \big [ U \big ] _ { 6 m \times 1 }
$$

$$
{ \biggl [ } { \vec { F } } _ { 1 } { \biggr ] } _ { 6 \times 1 } + { \biggl [ } { \vec { F } } _ { 2 } { \biggr ] } _ { 6 \times 1 } + \dots + { \biggl [ } { \vec { F } } _ { m } { \biggr ] } _ { 6 \times 1 } = \sum _ { i = 1 } ^ { m } { \Bigl [ } { \vec { F } } _ { i } { \Bigr ] } _ { 6 \times 1 } = 0
$$

![](images/3a3fa6776245e43c9742df945bdfc3bca0488388a549254359b01c970ebc5e52.jpg)  
Fig.3 Schematic diagram of the equilibrium forces exerted on a free beam

Lu adopted this method and computed the bending moment along the VLFS,where eight sub-modules were used,and the numerical results were compared to the values calculated by the hydroelastic theory (Fu et al., 2OO7). It can be seen from Fig. 4 that the results based on beam theory are in good agreement with the results calculated by Fu et al. Since the continuous distribution forces are simplified to be the concentrated force on the gravity center of the sub-module,only the connection interfaces of the sub-modules are exactly right，which is explained in the next section,i.e.，eight sub-modules can obtain nine exact points,then the bending moment distribution along the VLFS can be computed by B-spline interpolation.

![](images/b88430a678aafa122d58c7697ff5f17687771a32251117bdec56e99d18ea1295.jpg)  
Fig.4 Moment distribution of the model

To demonstrate the influence of the number of sub-modules, Fig.5 shows the comparison of bending moment distributions of five and eight sub-modules,respectively, in which the frequency is chosen as $0 . 6 ~ \mathrm { r a d / s }$ . Here,FBP denotes the six exact values computed by the five sub-modules; FPS represents the bending moment distribution along the VLFS via B-spline interpolation; EBP means the nine exact values of the bending moment; and EPS represents the bending moment distribution along the VLFS via B-spline interpolation.

![](images/5bb0dc35f1b68ff57d06780e1d8ce5257a628dc6aed4e7c71a31327c685fddd1.jpg)  
Fig.5 Moment distributions with different numbers of sub-modules

It can be seen that there is a big difference between the bending moment distributions for five sub-modules and eight sub-modules.To overcome this problem, some improvements have been proposed in the following section,specifically to use fewer sub-modules to obtain high accuracy of the bending moment distribution.

# 3.3High order interpolationmethod

In the multi-sub-module beam theory of Lu (2O15,2O16)，the continuous distribution pressure is treated as the concentrated force exerting on the gravity centers of the sub-modules. Therefore,the displacement as well as the bending moment distributions can be determined by four parameters,as seen in the following equations:

$$
V { \left( { \bf { x } } \right) } = z _ { i } + \beta _ { i } x + { \frac { M _ { i } ^ { \prime } \mathrm { { x } } ^ { 2 } } { 2 E I } } + { \frac { \mathrm { N _ { i } ^ { \prime } } { \mathrm { x } } ^ { 3 } } { 6 E I } }
$$

$$
\mathbf { M } ( x ) = E I V ^ { \prime \prime } = M _ { i } ^ { \prime } + \mathbf { N } _ { i } ^ { \prime } x
$$

However, the continuous distribution pressure has to be taken into account when solving for the displacement and the bending moment, as seen in the following equations:

$$
V { \left( { \bf { x } } \right) } = z _ { i } + \beta _ { i } x + { \frac { { M _ { i } } { { \bf { x } } ^ { 2 } } } { 2 E I } } + { \frac { { { \bf { N } } _ { i } } { { \bf { x } } ^ { 3 } } } { 6 E I } } + \int _ { 0 } ^ { x } { \frac { q ( \xi ) } { 6 E I } } { ( x - \xi ) ^ { 3 } } d \xi
$$

$$
\mathbf { M } ( x ) = M _ { i } + \mathbf { N } _ { i } \mathbf { x } + \int _ { 0 } ^ { \mathbf { x } } q ( \xi ) ( x - \xi ) d \xi
$$

where $V { \big ( } \mathbf { x } { \big ) }$ is the vertical displacement at $x$ ： $z _ { i }$ ， $\beta _ { i }$ ， $M _ { i } ^ { \prime }$ ， $\mathbf { N } _ { i } ^ { \prime }$ ， $M _ { i }$ ，and $\mathbf { N } _ { i }$ are the displacement, rotation, equivalent bending moment and shear force,exact bending moment, and shear force,respectively， for the center of gravity of the $i \cdot$ -th cross section; $q ( x )$ isthe continuous distribution pressure;and $x$ is the distance of the target point from the center of the $i$ -th cross section. Eqs.15 through 18 explain why Lu's method can only obtain several exact values.

In Lu’s original work,only the exact bending moment is used to perform the spline interpolation. However, it can be seen from eq.16 that on the exact point, both the bending moment value and its partial derivative with respect to the variable $x$ are known. Therefore,the higher-order interpolation scheme can be applied.Li (1986) showed that the interpolation curves can be cubic order if both the point value and its partial derivative at the two ending points are known， i.e.， $\left\{ x _ { 0 } , y _ { 0 } , y _ { 0 } ^ { \prime } \right\}$ and $\left\{ x _ { 1 } , y _ { 1 } , y _ { 1 } ^ { \prime } \right\}$ are known.Then，the interpolation curve can be expressed as

$$
p ( x ) = a + b x + c x ^ { 2 } + d x ^ { 3 }
$$

where

$$
{ \left[ \begin{array} { l } { a } \\ { b } \\ { c } \\ { d } \end{array} \right] } = { \left[ \begin{array} { l l l l } { 1 } & { x _ { 0 } } & { x _ { 0 } ^ { 2 } } & { x _ { 0 } ^ { 3 } } \\ { 1 } & { x _ { 1 } } & { x _ { 1 } ^ { 2 } } & { x _ { 1 } ^ { 3 } } \\ { 0 } & { 1 } & { 2 x _ { 0 } } & { 3 x _ { 0 } ^ { 2 } } \\ { 0 } & { 1 } & { 2 x _ { 1 } } & { 3 x _ { 1 } ^ { 2 } } \end{array} \right] } ^ { \prime } { \left[ \begin{array} { l } { y _ { 0 } } \\ { y _ { 1 } } \\ { y _ { 0 } ^ { \prime } } \\ { y _ { 1 } ^ { \prime } } \end{array} \right] }
$$

Since the current method takes into account both the bending moment and the shear force when solving the bending moment distribution along the VLFS,the interpolation accuracy must be greater than that of the original method of Lu. Fig. 6 gives the values of the bending moment computed by five sub-modules and eight sub-modules,respectively. Here,FBHOI means the values are computed by the five sub-modules through the high-order interpolation method,and EBHOI means the values are computed by the eight sub-modules through the high-order interpolation method. It can be seen that the trend of the values computed by FBHOI is the same as that computed by EBHOI, which demonstrates that the HOI method is more accurate than the spline interpolation scheme.Besides,the comparison of EBS and EBHOI shows that if the number of sub-modules is enough, both the HOI method and the spline interpolation scheme can give reasonable results for the bending moment distribution along the VLFS.

![](images/5976fdacf512656747f9f37c73db4f7ebe5bb8e235aca24b503980d1f09892f8.jpg)  
Fig.6 Moment distributions computed by the high order interpolation method

Though the trend of the values computed by the HOI method is the same as for the spline interpolation scheme,there is still some difference in the absolute values of the bending moment distribution. Therefore the displacement-to-displacement to moment method (DDM) is developed to improve the accuracy of the absolute values. Fig.7 gives the displacement distributions along the VLFS computed by five sub-modules and eight sub-modules,respectively; here,the wave frequencies are chosen as $0 . 3 ~ \mathrm { r a d / s }$ and $0 . 6 ~ \mathrm { r a d / s }$ . It can be seen that the displacement distributions along the VLFS computed by five sub-modules are nearly the same as those computed by eight sub-modules. The core idea of DDM is that the displacement distributions calculated by five sub-modules and eight sub-modules are considered the same,so the six DOF of eight modules can be converted by the six DOF of five modules,and then the bending moment can be calculated by eight sub-modules.In the HOI scheme,the bending moment and the shear force are taken into account, but the DDM scheme also considers the displacement information,which means this method is more accurate than the HOI scheme in application.

![](images/92fda1ed1ee9f2025e298fd554d0750f4ccc024dfcc051d3588d9463aa0b94bf.jpg)  
Fig.7Displacement distributions with different sub-modules

![](images/40310b60a686573d7b1434d6cf6a5d46ace2f2e3799c9e4bae3eba20117d52d7.jpg)  
Fig.8Bending moment distribution with different interpolation schemes

Fig. 8 gives the bending moment distributions along the VLFS computed by the different interpolation schemes; the frequencies are chosen as O.3 rad/s,O.4 rad/s, O.6 rad/s,and $0 . 7 ~ \mathrm { r a d / s }$ Here,FTEP means the eight bending moment points computed by the DDM scheme using five sub-modules，and FTEHOI represents the bending moment distributions along the VLFS computed by the DDM scheme using five sub-modules. It can be seen that the DDM scheme is beter than the HOI method,and in realistic computations,the combination of five sub-modules and the DDM scheme can produce a reasonable result.

In the actual situation, considering the computational efficiency, fewer modules are used. The DDM method is useful to obtain high-precision calculation results.

# 4. Hydroelastic response with moving mass points

# 4.1 Time domain hydroelastic theory

To take into account the effects of moving mass points, the simulation must be carried out in the time domain. In terms of the convolution of body motions according to the Cummins equations (Cummins,1962) and Ogilive relations (Ogilvie,1964),for a multi-body system (with N bodies), the equations of motion can be rewritten in the following form:

$$
\begin{array} { c } { { { \displaystyle { [ \begin{array} { l l l } { M _ { 1 1 } + A _ { 1 1 } ( \alpha ) } & { { \cdots } } & { A _ { \mathrm { i n } } ( \alpha ) } \\ { { \vdots } } & { { \ddots } } & { { \vdots } } \\ { A _ { \mathrm { s h } } ( \alpha ) } & { { \cdots } } & { M _ { \mathrm { s n } } + A _ { m p } ( \alpha ) } \end{array} ] } \Bigg \{ \begin{array} { l } { { \ddot { u } _ { 1 } ( t ) } } \\ { { \vdots } } \\ { { \ddot { u } _ { \nu } ( t ) } \Bigg \} } \end{array} } } \\ { { { \downarrow } { [ \begin{array} { l l l l } { B _ { 1 1 } ( t - \tau ) } & { { \cdots } } & { B _ { \mathrm { i n } } ( t - \tau ) } \\ { { \vdots } } & { { \ddots } } & { { \vdots } } \\ { { \overline { { { \vartheta } } } _ { m } ( t - \tau ) } } & { { \cdots } } & { B _ { \mathrm { s n } } ( t - \tau ) } \end{array} ] } \Bigg \{ \begin{array} { l } { { \dot { u } _ { 1 } ( t ) } } \\ { { \dot { \vdots } } } \\ { { \dot { u } _ { \nu } ( t ) } \Bigg \} } \end{array} } - d \tau } } \\ { { { \downarrow } { [ \begin{array} { l } { { C _ { 1 } } } \\ { { \dot { \ddots } } } \\ { { \dot { C } _ { 1 } } } \end{array} ] } \Bigg \{ \begin{array} { l } { { [ \begin{array} { l } { { u _ { 1 } ( t ) } } \\ { { \dot { \ddots } } } \\ { { \dot { u } _ { \nu } ( t ) } } \end{array} ] } } \\ { { \dot { [ u _ { m } ( t ) ] } } } \end{array} ] } } \end{array}
$$

where $M$ and $A$ are the mass and the added mass with infinite coefficient, respectively; $B$ is the delay function matrix; $C$ is the hydrostatic resilience matrix; $u$ and the over dot means the displacement and the partial derivative with respect to time; and $F$ is the wave exciting force.

The delay function and the added mass with infinite coefficient can be computed via the following equations:

$$
B _ { i j } \left( t \right) = \frac { 2 } { \pi } \int _ { 0 } ^ { \infty } b _ { i j } \left( \omega \right) \cos ( \omega t ) d \omega
$$

$$
{ \cal M } = a ( \omega _ { _ { a c } } ) + \frac { 1 } { \omega _ { _ { a c } } } { \int } _ { 0 } ^ { \infty } B ( t ) \sin ( \omega _ { _ { a c } } t ) d t
$$

where $a$ and $b$ are the frequency domain added mass and damping coefficient, and $\omega _ { a c }$ is an arbitrarily chosen frequency.

Based on Lu's theory, for the time domain hydroelastic simulations,Eq. 21 should include the stiffness matrix as follows:

$$
\begin{array} { r l } &  [ \begin{array} { c c c c } { M _ { 1 1 } + A _ { 1 1 } ( \infty ) } & { \cdots } & { A _ { \ln } ( x ) } \\ { \vdots } & { \ddots } & { \vdots } \\ { A _ { \ln } ( \infty ) } & { \cdots } & { M _ { m } + A _ { \ln \pi } ( \infty ) \displaystyle \int \Biggl | \Biggl | \begin{array} { c } { \{ \ddot { u } _ { 1 } ( t ) \} } \\ { \vdots } \\ { \vdots } \\ { \Biggl \langle \vec { u } _ { \kappa } ( t ) \Biggr \rangle } \end{array} ] } \\ &  ~ + [ \begin{array} { c c c c } { B _ { 1 1 } ( t - \tau ) } & { \cdots } & { B _ { \ln } ( t - \tau ) } \\ { \vdots } & { \ddots } & { \vdots } \\ { \bigg \{ \begin{array} { c c c c } { [ \begin{array} { c } { B _ { 1 1 } ( t - \tau ) } & { \cdots } & { B _ { \ln } ( t - \tau ) } \\ { \vdots } & { \ddots } & { \vdots } \end{array} ] } & { \cdots } & { \vdots } \\ { \bigg \{ \begin{array} { c } { \dot { u } _ { \kappa } ( t - \tau ) } & { \cdots } & { B _ { \ln } ( t - \tau ) } \end{array} \} } & { [ \begin{array} { c } { \dot { u } _ { 1 } ( t ) } \\ { \vdots } \\ { \dot { u } _ { \nu } ( t ) } \end{array} ] \cdot d \tau } \\ { \vdots } \end{array} ] } \\ &  ~ + [ \begin{array} { c c c c } { C _ { 1 } + K _ { 1 } } & { \cdots } & { \gamma } \\ { \vdots } & { \ddots } & { \vdots } \\ { \qquad \begin{array} { c } { C _ { s 1 } + K _ { \kappa } } & { \cdots } & { \gamma } \\ { \vdots } & { \ddots } & { \vdots } \end{array} ] [ \begin{array} { c } { u _ { 1 } ( t ) } \\ { \vdots } \\ { u _ { s } ( t ) } \end{array} ] = [ \begin{array} { c } { F _ { 1 } ( t ) } \\ { \vdots } \\ { F _ { s } ( t ) } \end{array} ] } \end{array} \end{array} \end{array} \end{array}
$$

where $K$ isthe stiffness matrix coefficient.

If there exists some other force,e.g., moving point mass, then the above equations should be modified as follows:

$$
\begin{array} { r l } & { \left[ \begin{array} { c c c c } { M _ { 1 1 } + A _ { 1 1 } ( \infty ) } & { \cdots } & { A _ { \mathrm { N } } ( \infty ) } \\ { \vdots } & { \ddots } & { \vdots } \\ { A _ { \mathrm { s n } } ( \infty ) } & { \cdots } & { M _ { \mathrm { s n } } + A _ { \mathrm { w n } } ( \infty ) } \end{array} \right] \left[ \begin{array} { c } { \dot { u } _ { 1 } ( t ) } \\ { \vdots } \\ { \dot { u } _ { r } ( t ) } \end{array} \right] } \\ & { \quad + \left[ \begin{array} { c c c c } { B _ { 1 1 } ( t - \tau ) } & { \cdots } & { B _ { \mathrm { N } } ( t - \tau ) } \\ { \vdots } & { \ddots } & { \vdots } \\ { \Theta _ { \mathrm { L } } ( t - \tau ) } & { \cdots } & { B _ { \mathrm { w n } } ( t - \tau ) } \end{array} \right] \cdot \left[ \begin{array} { c } { \dot { u } _ { 1 } ( t ) } \\ { \vdots } \\ { \dot { u } _ { r } ( t ) } \end{array} \right] \cdot d \tau } \\ & { \quad + \left[ \begin{array} { c c c c } { C _ { 1 1 } + K _ { 1 1 } ( - \tau ) } & { \cdots } & { B _ { \mathrm { s n } } ( t - \tau ) } \\ { \vdots } & { \ddots } & { \vdots } \\ { C _ { \mathrm { r } } + K _ { \mathrm { x } } } \end{array} \right] \cdot \left[ \begin{array} { c } { \dot { u } _ { 1 } ( t ) } \\ { \vdots } \\ { \dot { u } _ { r } ( t ) } \end{array} \right] } \end{array}
$$

where $f$ is the additional external force.

Section 3 has shown that the combination of five sub-modules and the DDM scheme can provide reasonable results for both the displacement and bending moment distributions along the VLFS.Here, indirect time domain simulations are carried out,and the time domain results are transformed into the frequency domain. The comparisons of time domain (TD） values with the frequency domain (FD) results are shown in Fig. 9. The results are in good agreement,but there are some numerical errors.This paper uses the Runge-Kutta method in time-domain iteration. Normally, numerical methods have computational errors. In the process of using the IRF method, we need to truncate the delay function. This is another numerical error. For a number of floating bodies,the truncation term will increase,so the error will increase. The vertical response along the VLFS is calculated by Eq. 12, and the $[ U ] _ { 6 m \times 1 }$ term exists calculation error. When multiplied by a coefficient matrix, the whole displacement response exists calculation error.

![](images/c4077d98341d1afa63dba815b4712a6b6874aaa3fec82d915c9c28aba9a949f8.jpg)  
Fig.9 Comparisons of the time domain values with frequency domain results

# 4.2 Consideration of the moving point mass

![](images/73d71c5a39fbee168d0670e298b31b4eac7565d6c63398df1011c75256850cb8.jpg)  
Fig.10 Demonstration of the absolute acceleration of the moving point mass

To describe the position of the moving point mass, two coordinate systems are introduced in Fig.10. These are the space fixed coordinate system OXYZ and the body fixed coordinate system oxyz. With the origin o located at $\vec { \rho } _ { e } = \left( x _ { o } , y _ { o } , z _ { o } \right)$ in coordinate system OXYZ, the position of the moving point mass is $\vec { \rho } _ { r } = \left( x , y , z \right)$ in the body fixed coordinate system. Therefore，the position of the moving point mass in the space fixed coordinate system can be written as

$$
\vec { \rho } _ { a } = \vec { \rho } _ { e } + \vec { \rho } _ { r }
$$

If the relative velocity of the moving point mass with respect to the VLFS is taken as $\vec { \nu } _ { r }$ ,and keeping connected with the VLFS,then the acceleration of the moving point mass in the inertial coordinate system can be computed by the following equation (Shen, 2OO3; Shi min, 2001):

$$
\vec { a } _ { a } = \vec { a } _ { e } + \vec { a } _ { r } + 2 \big ( \vec { \omega } \times \vec { \nu } _ { r } \big )
$$

where $\vec { \omega }$ is the rotational velocity of oxyz, $\vec { a } _ { a }$ is the absolute acceleration, $\vec { a } _ { e }$ is the transport acceleration, $\vec { a } _ { r }$ is the relative acceleration, and $2 \big ( \vec { \omega } \times \vec { \nu } _ { r } \big )$ is the Coriolis acceleration.

For the linear case,Eq. 27 can be simplified as follows (Guo-ping,1989):

$$
\vec { a } _ { a } = \vec { a } _ { e } + \left[ \mathrm { T } _ { a } \right] \vec { \rho } _ { r } + 2 \left( \vec { \omega } \times \vec { \nu } _ { r } \right)
$$

where

$$
\left[ T _ { a } \right] = \left[ \begin{array} { c c c } { { 0 } } & { { - \ddot { \gamma } } } & { { \ddot { \beta } } } \\ { { \ddot { \gamma } } } & { { 0 } } & { { - \ddot { \alpha } } } \\ { { - \ddot { \beta } } } & { { \ddot { \alpha } } } & { { 0 } } \end{array} \right] , \vec { \omega } = \left( \dot { \alpha } , \dot { \beta } , \dot { \gamma } \right)
$$

Therefore, the external force exerting on the VLFS coming from the moving point mass can be computed by

$$
\vec { f } = - M \left[ \mathrm { T } _ { 1 } \right] ^ { T } \left[ \mathrm { T } _ { 1 } \right] \vec { \mathbf { a } } _ { o } - 2 M \left[ \mathrm { T } _ { 1 } \right] ^ { T } \left( \vec { \omega } \times \vec { \nu } _ { r } \right) + \left[ \mathrm { T } _ { 1 } \right] ^ { T } \vec { \mathrm { F } } _ { g }
$$

where

$$
\left[ T _ { 1 } \right] = \left[ \begin{array} { c c c c c c } { 1 } & { 0 } & { 0 } & { 0 } & { z } & { - y } \\ { 0 } & { 1 } & { 0 } & { - z } & { 0 } & { x } \\ { 0 } & { 0 } & { 1 } & { y } & { - x } & { 0 } \end{array} \right]
$$

$$
\vec { \mathbf { a } } _ { o } = \left( \ddot { x } _ { o } , \ddot { y } _ { o } , \ddot { z } _ { o } , \ddot { \alpha } _ { o } , \ddot { \beta } _ { o } , \ddot { \gamma } _ { o } \right) ^ { T }
$$

4.3 Hydroelastic response of the VLFS with a moving point mass

Here,we use a non- rigorous method to study the hydroelastic response of the VLFS with a moving mass point.

Through the combination of time domain hydroelastic theory (Eq.25) and the external force computation equation of the moving point mass (Eq. 33), the hydroelastic response of the VLFS with a moving mass point is investigated. If the moving point mass is located at the $i$ -th

sub-module, then the motion equation of the VLFS can be computed by as follows:

$$
\begin{array} { r l } &  [ \begin{array} { c c c c } { M _ { 1 1 } + A _ { 1 } ( \infty ) } & { \cdots } & { A _ { N } ( \infty ) } \\ { \vdots } & { \ddots } & { \vdots } \\ { A _ { N } ( \infty ) } & { \cdots } & { M _ { s n } + A _ { \mathrm { N s } } ( \infty ) \biggr ] \{ \begin{array} { l } { \bar { u } _ { 1 } ( t ) } \\ { \vdots } \\ { \bar { u } _ { s } ( t ) } \end{array} \} } \\ { \mathrm { ~ } } \\ { + [ \begin{array} { c c c c } { B _ { 1 1 } ( t - \tau ) } & { \cdots } & { B _ { \mathrm { N s } } ( t - \tau ) } \\ { \vdots } & { \ddots } & { \vdots } \\ { B _ { \mathrm { N s } } ( t - \tau ) } & { \cdots } & { B _ { \mathrm { N s } } ( t - \tau ) } \end{array} ] \ldots \{ \begin{array} { l } { \bar { u } _ { 1 } ( t ) } \\ { \vdots } \\ { \bar { u } _ { 1 } ( t ) } \end{array} \} \ldots d \tau } \\ { \mathrm { ~ } } \\ { + [ \begin{array} { c c c c } { C _ { 1 } + K _ { 1 } } & & \\ & { \ddots } & \\ & & { C _ { \scriptscriptstyle { N } } + K _ { \scriptscriptstyle { N } } } \end{array} ] [ \begin{array} { l } { u _ { 1 } ( t ) } \\ { \vdots } \\ { u _ { \nu } ( t ) } \end{array} ] = [ \begin{array} { l } { F _ { 1 } ( t ) } \\ { \vdots } \\ { F _ { n } ( t ) } \end{array} ] + \{ \begin{array} { l } { 0 } \\ { \bar { \xi } _ { 1 } ( t ) } \end{array} \} } \\ { 0 } \end{array} \end{array}
$$

where $f _ { i } ( t )$ is computed by Eq. (30).

![](images/302e29e392b1946637fcd9dde0fcbd6bea3fa5dd0454ab3c85e05aafe3da2779.jpg)  
Fig.11 Division of the total VLFS

The main purpose of this paper is to discuss the applications of the proposed method for the computation of the hydroelastic response of the VLFS,with or without the moving point mass. Therefore,only one wave condition (wave length $\lambda = 4 2 0 \mathrm { ~ m ~ }$ ）is taken as an example.In the numerical simulations,the total VLFS is divided into five sub-modules,as shown in Fig.11; the moving point mass is taken as $1 0 ^ { 6 } \mathrm { k g }$ ；the velocity of the moving point mass is $5 ~ \mathrm { m / s }$ ； and the moving point mass begins to go on the VLFS at time $6 0 ~ \mathrm { s }$

Fig.12 gives the time history of the displacement and bending moment of the VLFS, while Figs.13 and 14 give the contour of the displacement and bending moment of the VLFS with a moving point mass,respectively. It can be seen that before the moving point mass moves on the VLFS,the time variation of the VLFS is stable,and then the figure shows the influence of the moving point mass on the bending moment and the displacement.

![](images/78c01c9b5b7d8a08fbcda56bd6f16cc848289ef608a2c7c55d693342a3e28756.jpg)  
Fig.12 Bending moment and vertical response amplitude in midpoint

![](images/8a9e9324494c9b1a93eced351c504dfd802b9d3cf8de203b9d90a5195da6c083.jpg)  
Fig.13 Contour of the displacement of the VLFS

Time variation of the bending moment

![](images/d3b3e762656d00f9273bc4e5ffafe9a4280a5a459eb4b8e4c49b3ddb1bf5190d.jpg)  
Fig.14 Contour of the bending moment of the VLFS

# Conclusion

This paper first describes a new method, based on both multi-body hydrodynamics and the Euler-Bernoulli assumption, to calculate the response of the VLFS. Then two methods,the HOI method and DDM method,are proposed to improve the accuracy of the computation of the bending moment distributions along the VLFS.Via Fourier transformations,the method has been extended to time domain analysis, and then used to investigate the hydroelastic response of the VLFS with a moving point mass on it.

Some test cases have been carried out. All the results are compared with the values obtained by three-dimensional hydroelastic theory and the model experiment (Yago and Endo,1996). The results show that the new method is accurate enough to deal with the hydroelastic response of the VLFS. Some initial attempts have been made to study the hydroelastic response of the VLFS with a moving load. Further investigation will be conducted to study the influence of the moving point mass on the displacement, as well as the bending moment distributions of the VLFS.

# Reference

Betts C V, Bishop R E D,Price W G. The symmetric generalized fluid forces applied to a ship in a seaway [J]. RINA Supplementary Papers,1977,119.   
Bishop R.E.D.and Price W.G, 1977. The generalized anti-symmetry fluid forces applied to a ship in a seaway, International Shipbuilding Progress,V01.24:3-14.   
Cummins, W.E.“The Impulse Response Function and Ship Motions, Schifstechnik, pp.101-109,1962.   
Chakrabarti, S..“Time domain simulation of multiple-floating structures with nonlinear constraints”.In Proc, Offshore Mechanics and Arctic Engineering (OMAE), ASME. 2001.   
Endo H.The behavior of a VLFS and an airplane during takeoff/landing run in wave condition [J]. Marine structures,2000,13(4): 477-491.   
Fu S.,Moan T, Chen X,et al.Hydroelastic analysis of flexible floating interconnected structures [J].Ocean engineering,2007,34(11): 1516-1531.   
Fu S. The nonlinear hydroelastic analysis of flexible floating body and mooring carying bridge [D]. Doctoral dissertation (in Chinese).Shanghai: Shanghai Jiaotong Univercity,2005.   
Miao G,ISHIDA H, SAITOH T. Influence of gaps between multiple floating bodies on wave forces [J]. China Ocean Engineering,2000,14(4): 407-422.   
Miao G.,Liu Y.,The motion theory of the ship on the wave [M].1989.In Chinese.   
Goo JS, Yoshida K. A numerical method for huge semisubmersible responses in waves [J]. Transactions-Society of Naval Architects and Marine Engineers,1990,98: 365-387.   
Jacobsen K, Clauss GF. Time-domain simulations of multi-body systems in deterministic wave trains[Cl/25th International Conference on Offshore Mechanics and Arctic Engineering.American Society of Mechanical Engineers,2006: 375-384.   
Liu X,Sakai S.Time domain analysis on the dynamic response of a flexible floating structure to waves[J]. Journal of engineering mechanics,2002,128(1): 48-56.   
Lu D.,Fu S., Zhang X., Guo F., Gao Y..A method to estimate the hydroelastic behavior of VLFS based on the multi rigid body dynamics and beam bending[J].Journal of ship mechanics(in Chinese).2015.   
Lu D..Hydrodynamic performance study of floating multi-body with connector[D]. Shanghai: Shanghai Jiao Tong University.2016   
Lu D.,Fu S., Zhang X., Guo F.，Gao Y. A method to estimate the hydroelastic behavior of VLFS based on the multi rigid body dynamics and beam bending [J].Ships and Offshore Structures.2016.   
Ogilvie,T..“Recent Progress towards the Understanding and Prediction of Ship Motions”, In: Sixth Symposium on Naval Hydrodynamics,1964.   
QingY. Numerical analysis [M]. Hua zhong university of science press,1986. In Chinese.   
Shen Q,Chen X,Li Y,etal. An analysis method of the self-oscilltion in time domain of a multi-body system with a floating base [J]. Ocean Engineering/Haiyang Gongcheng, 2002,20(2): 7-13.   
Shen Q,Li Y,Chen X.Dynamic analysis of multibodies system with a floating base forroling of ro-ro shipcaused by wave and slip of heavy load [J]. Journal of Marine Science and Application,2O03,2(2): 17-24.   
Shen Q,Li Y, Wu G. Dynamic Analysis of Multi-body System with Floating Base in Heavy Equipment Urgent Unload Process [J]. Journal of PLA University of Science and Technology (Natural Science),20o3,1: 009.   
Shin H,Lee H Y, Lim C G, et al. Hydroelastic response simulation of a VLFS in irregular waves considering taking-off and landing impact[C]/2Oth International Conference on Offshore Mechanics and Arctic Engineering. 2001: 1-5.   
Wu, Y.S.. Hydroelasticity of floating bodies,Ph.D. Thesis, Brunel University, UK.1984.   
Wang D.. The analysis method of 3-D ship hydroelastic in time domain [J]. Doctoral dissertation (in Chinese).

Wuxi: China Ship Scientific Research Center,1996:35-37.

Wu J S,Sheu JJ.Anexact solution for a simplified model of the heave and pitch motions of aship hull due toa moving load and a comparison with some experimental results [J].Journal of Sound and Vibration,1996,   
192(2): 495-520. WuJS,Shih PY.Moving-load-induced vibrations of a moored floating bridge [J]. Computers & structures,1998,   
66(4): 435-461. Yago,K.,Endo,H.,Model experiment and numerical calculation of the hydroelastic behavior of matlike VLFS,   
1996,VLFS'96,pp.209-216.

# Appendix

![](images/0ae4934e5dc386792cee5d006099b4ec7dab6d590b3a25b6288471b66408e5c4.jpg)

![](images/95a811782c434fa9ad241bce231986428a27e808ae64b422d2d0e029c3baa73c.jpg)  
Fig.15.The hydrodynamic response of VLFS in differentwave direction