# Effect of Marangoni Number on Thermocapillary Convection and Free-Surface Deformation in Liquid Bridges

ZHANG $\mathbf { Y i n } ^ { 1 }$ , HUANG Hu-Lin1\*, ZHOU Xiao-Ming², ZHU Gui-Ping1, ZOU Yong

1. College of Energy and Power Engineering,Nanjing University of Aeronautics and Astronautics,Nanjing,210016, China 2. Institute of Engineering Thermophysics, Chinese Academy of Sciences,Beijing,100190, China

$\copyright$ Science Press and Institute of Engineering Thermophysics, CASand Springer-Verlag Berlin Heidelberg 2016

Floating zone technique is a crucible-free processfor growth of high quality single crystals. Unstable thermocapillary convection is a typical phenomenon during the process under microgravity.Therefore,it is very important to investigate the instabilityof thermocapillary convection in liquid bridges with deformable free-surface under microgravity. In this works,the Volume of Fluid (VOF) method is employed to track the free-surface movement. The results are presented as the behavior of flow structure and temperature distribution of the molten zone.The impact of Marangoni number $( M a )$ is also investigated on free-surface deformation as well as the instability of thermocapillary convection.The free-surface exhibits a noticeable axisymmetric (but it is non-centrosymmetric) and eliptical shape along the circumferential direction.This specific surface shape presents a typical narrow ‘neck-shaped'structure with convex at two ends of the zone and concave at the mid-plane along the axial direction. At both $\theta = 0 ^ { \circ }$ and $\theta = 9 0 ^ { \circ }$ ,the deformation ratio $\xi$ increases rapidly with Ma at first,and then increases slowly. Moreover, the hydrothermal wave number $m$ and the instability of thermocapillary convection increase with $M a$

# Keywords: thermocapillaryconvection,microgravity,Floating zone,deformable freesurface,VOF,liquidbridge

# Introduction

The Floating zone method,which avoids undesirable contact with the crucible walls,becomes a promising technique to produce oflarger and higher quality crystals of semiconductors[1,2].Under a microgravity condition. thermocapillary convection driven by an unbalanced surface tension plays a dominant role in the crystal growth process.The unstable thermocapillary flow may induce undesirable macroscopic and microscopic imperfections in the obtained final crystals[3,4].Therefore,the investigation of characteristics of the thermocapillary flow under microgravity isnecessary for crystals growth processing in the future.

For a better understanding and optimizing of the crystal growth process,extensive researches have been conducted on the thermocapillary convection in liquid bri dges.Numerical simulations were carried out to investigate the effects of aspect ratio $( A r )$ [5],shape factor [6] and high-frequency vibrations [7] on the instability of thermocapillary flow in liquid bridges.In recent years,a number of experimental [8,9] and numerical [10-12] investigations were also dedicated to analyze the impact of interfacial heat transfer on the stability of thermocapillary flow in liquid bridges.However, the above-mentioned researches were performed without considering the free- surface movement.

The free-surface deformation was a necessary condition for the onset of oscillatory thermocapillary convection[13]. It's of great importance to investigate the freesurface deformation behavior of the liquid bridge in fabricating single crystals with high purity. To date, only a few investigations concerned the effect of free-surface deformation.Kuhlmann and Nienhuiser[14] investigated the flow-induced dynamic free-surface deformations in liquid bridges. They found that the total dynamic deformation could be decomposed to elucidate the relative importance of the hydrodynamic pressure, viscous stress, change of volume,surface tension and hydrostatic pressure.Sim et al.[15] investigated the dynamic free-surface deformations in two-dimensional (2D) liquid bridges, and their numerical results indicated that the free-surfaces were convex at the cold wall and concave at the hot wall. Shevtsova et al.[16] investigated the dynamic freesurface in non-cylindrical liquid bridges of $5 \ : c S t$ silicone oil,and found the magnitude of deformation increased with the temperature difference of the cold and hot walls. Liang and Kawaji [17] developed a three-dimensional (3D) numerical simulation to investigate the vibration-induced oscillation of liquid bridge by level set method.The results showed that the external vibration in $x$ direction at resonance frequency controlled the surface oscillation in $x$ direction while the influence of external vibrations in $y$ and $z$ directions on the surface vibration was small.Ahmed et al.[18] found the flexible freesurface capable of influencing the thermocapillary convection of small scale liquid bridges. Zhou and Huang [19] numerically studied the steady thermocapillary convection in 3D rectangular cavities using level set method. The interface was discovered to bulge out near the hot wall and bulge in near the cold wall and the deformability increased with an increasing Ma. Zhou and Huai [20] investigated the thermo-solutocapillary convection in axisymmetric liquid bridge with a dynamic free surface. The free surface bulged out at the two ends of zone and bulged in at the central zone when the thermal Marango ni number was identical to the solutal Marangoni number.

Yin ZHANG etal.EectofMarangoni NumberonThermocapillryConvectionandFree-SurfaceDeformation inLiquidBridges179   

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>A</td><td>monitoring point</td><td colspan="2">Greek symbols</td></tr><tr><td>Ar</td><td>aspect ratio (=L/r1)</td><td>p</td><td>density, [kg·m-1]</td></tr><tr><td>Ca</td><td>Capillary number(=(△T|σrl)/σ0)</td><td></td><td>thermal conductivity,[W·m-1·K-1]</td></tr><tr><td>g</td><td>gravitational acceleration,[m²·s-1]</td><td>Cp</td><td>specific heat,[J·kg-1 ·K1]</td></tr><tr><td>k</td><td>unit tangential vector</td><td>从</td><td>dynamic viscosity,[kg:s-·m-1]</td></tr><tr><td>L</td><td>length of the molten zone,[cm]</td><td>v</td><td>kinematic viscosity,[m²·s-1]</td></tr><tr><td>m</td><td>hydrothermal wave number</td><td>X</td><td>thermal diffusivity, [K-1]</td></tr><tr><td>Ma</td><td> Marangoni number (=(△TL|σrI)/μx )</td><td>8</td><td>thickness of the air layer, [cm]</td></tr><tr><td>n</td><td>unit normal vector</td><td></td><td>surface tension (= O0- Or(T-To)),[N·m-1]</td></tr><tr><td>P</td><td>pressure of the inner fluid, [Pa]</td><td>OT</td><td> interfacial tension temperature coefficient,[N·m-1·K-1]</td></tr><tr><td>P</td><td>pressure of the outer fluid, [Pa]</td><td></td><td>deformation ratio (= (rmax - rmin)/r1)</td></tr><tr><td>Pr</td><td>Prandtl number (= Cpμ/𝜆 )</td><td>u, v, w</td><td>teveyotsid</td></tr><tr><td>Re</td><td>Reynolds number (=pVL/μ1)</td><td>r,0,z</td><td>radial, azimuthal and axial coordinates</td></tr><tr><td>Q</td><td>convergence criteria</td><td>x,y</td><td>coordinates directions (x =rcos0,y =rsinθ),[cm]</td></tr><tr><td>r</td><td>radius of the molten zone,[cm]</td><td colspan="2">Subscripts</td></tr><tr><td>Ri</td><td>normal radii of curvature</td><td colspan="2">av average</td></tr><tr><td>Sik</td><td>tensor of viscous stress</td><td>C</td><td>cold wall</td></tr><tr><td>t</td><td>time,[s]</td><td>h</td><td>hot wall</td></tr><tr><td>T</td><td>temperature, [K]</td><td>max</td><td>maximum</td></tr><tr><td>△T</td><td>temperature difference (=Th-Tc),[K]</td><td>min</td><td>minimum</td></tr><tr><td></td><td></td><td>1</td><td> inner melt layer</td></tr><tr><td></td><td></td><td>2</td><td></td></tr><tr><td></td><td></td><td></td><td>outer air layer</td></tr></table></body></html>

A few numerical studies have been performed for 2D liquid bridges,axisymmertic liquid bridges and 3D rectangular cavities with deformable free-surfaces.However, there is no work available for 3Dlarge scale cylindrical liquid bridges and no report on the effect of Ma on the instability of thermocapillary convection with considering free-surface deformation. Consequently this paper aims to numerically investigate the thermocapillary convection in a 3D liquid bridge with considering the free-surface deformation.With a fixed aspect ratio,the effect of Ma on deformable free-surface shape is explored as well as the instability of thermocapillary convection. The characteristics of melt flow and heat transfer are also investigated and analyzed in a liquid bridge with deformable free-surface.

# Physical and mathematical models

In the present study,the main features of thermocapillary flow in floating zone can be captured in half-zone model which can simplify the numerical calculations [1]. The geometry and coordinate system of this model is shown in Fig.1 with a height $( H )$ at $3 \mathrm { c m }$ and radius $( r _ { 2 } )$ at $2 \mathrm { c m }$ ,respectively.The silicon-melt inner fluid is suspended between two co-axial disks,has a length of $L$ 0 $L =$ $1 . 5 ~ \mathrm { c m } )$ andradiusof $r _ { 1 }$ $( r _ { 1 } = 1 ~ \mathrm { c m } )$ which makes the aspect ratio at $A r = L / r _ { 1 } = 1 . 5$ .The temperatures $T _ { h } , \ T _ { c }$ $( T _ { h } { > } T _ { c } )$ are prescribed at the lower and upper disks respectively,which keeps a constant temperature difference of $\Delta T$ $\left( \Delta T = T _ { h } – T _ { c } \right)$ between the two disks.The outer fluid ofliquid bridge isair with a height $( H )$ at $3 \mathrm { c m }$ and thickness $\begin{array} { r } { ( \delta = r _ { 2 } – r _ { 1 } ) } \end{array}$ at $1 ~ \mathrm { c m }$ ，respectively. The detailed properties of silicon-melt in the inner layer and air in the outer layer are available in Table 1 [21].A cylindrical coordinate system $( r , \theta , z )$ is applied with $z$ -axis corresponding to the centerline of the liquid bridge and origin from the centerof thelower disk.

Some assumptions are made in this numerical model as follows:(1) the two kinds of fluids are incompressible Newtonian fluid;(2) the flow is laminar;(3) the thermocapillary force is taken into account at the interface of the melt and air,and the no-slip condition is applied at the upper and lower disks;(4) the liquid bridge is under microgravity (set $0 g$ in present investigation);(5) the interfaceof the melt-airisdeformable.The surface tension at the interface is assumed to be a linear function of temperature:

$$
\sigma = \sigma _ { 0 } - \sigma _ { T } ( T - T _ { 0 } )
$$

where $\sigma _ { 0 }$ is the surface tension at $T = T _ { 0 }$ ， $\sigma _ { T }$ is the negative surface tension change rate of with temperature （20 $( \sigma _ { T } = - ( \hat { c } \sigma / \hat { c } T ) > 0 )$ 1

# Governing Equations

With the above assumptions, the non-dimensional governing equations for thermocapillary flow with deformable free-surface in 3D model can be written as ( $( i = 1 , 2$ and 1 denotes the inner fluid,2 denotes the outer fluid),

$$
\nabla \cdot \boldsymbol { V } _ { i } = 0
$$

$$
\frac { \partial V _ { i } } { \partial t ^ { * } } + V _ { i } \cdot \nabla V _ { i } = - \nabla p _ { i } ^ { * } + \frac { 1 } { R e } \nabla ^ { 2 } V _ { i }
$$

$$
\frac { \partial \theta _ { i } } { { \partial t } ^ { * } } + V _ { i } \cdot \nabla \theta _ { i } = \frac { 1 } { M a } \nabla ^ { 2 } \theta _ { i }
$$

$$
\mathrm { a s } \left( r ^ { * } , z ^ { * } \right) = \frac { \left( r , z \right) } { L } , V = \left( u ^ { * } , \nu ^ { * } , w ^ { * } \right) = \frac { \left( u , \nu , w \right) } { U ^ { * } } , t ^ { * } = \frac { t U ^ { * } } { L } ,
$$

$$
\boldsymbol { U } ^ { * } = \frac { \Delta T \left| \sigma _ { T } \right| } { \mu _ { 1 } } , \boldsymbol { \Theta } = \frac { T - T _ { a \nu } } { T _ { h } - T _ { c } } ( T _ { a \nu } = \frac { T _ { h } + T _ { c } } { 2 } ) , \boldsymbol { p } ^ { * } = \frac { \boldsymbol { p } } { \rho _ { 1 } \boldsymbol { U } ^ { * 2 } } ;
$$

# Free-surface deformation

The position of the melt-air interface is described by a function $F ( z )$ ，with $F ( 0 ) = r _ { 1 } = F ( L ) = R _ { 0 } ,$ and the initial shape of interface is assumed to be a cylindrical surface. The stress balance between the viscous fluid and idealgas on the interface, $R { = } F ( z )$ ,is controlled by,

![](images/fa5b4aaf9385152e5a52d5ba97f84e48b75fd4f64d484bf99a168f4f50eabbc4.jpg)  
Fig.1 Geometry and coordinate system

$$
\bigg [ P - P _ { 0 } + \sigma ( \frac { 1 } { R _ { 1 } } + \frac { 1 } { R _ { 2 } } ) \bigg ] \pmb { n _ { i } } = \pmb { S } _ { i k } \pmb { n _ { k } } + \frac { \hat { \sigma } \sigma } { \hat { \sigma } \kappa _ { i } }
$$

where $S _ { i k } , R _ { i }$ are the tensor of viscous stress and the normal radii of curvature, $P$ and $P _ { 0 }$ are the pressure of the inner and outer fluid, $k$ and $\pmb { n }$ are the unit tangential vector and the outward unit normal vector, respectively. The mean curvature is defined as,

Table 1Thermophysical properties of Silicon-melt and Air   

<html><body><table><tr><td>Fluids</td><td>μ(Pa·s)</td><td>p(kg:m3)</td><td>Cp(J·kg1·K−1)</td><td>𝜆(W·m1·K1)</td><td>0 (N·m)</td><td>Or(N·m1·K-1)</td></tr><tr><td> Silicon-melt</td><td>8.89×10-4</td><td>2530</td><td>1000</td><td>67</td><td rowspan="2">0.4868</td><td rowspan="2">2.8×104</td></tr><tr><td>Air</td><td>1.78×10-5</td><td>1.225</td><td>1006.43</td><td>0.0242</td></tr></table></body></html>

$$
\frac { 1 } { R _ { 1 } + R _ { 2 } } { = } \sqrt { 1 + { F _ { z } } ^ { 2 } } ( \frac { F _ { z z } } { 1 { + } { F _ { z } } ^ { 2 } } { - } \frac { 1 } { F } )
$$

where the subscript $z$ denotes the derivative, $F _ { z } { \mathrm { = d } F / \mathrm { d } z }$ The normal and tangential projections of Eq. (6） are given by,

$$
P - P _ { 0 } = \pmb { n } \cdot \pmb { S } \cdot \pmb { n } - \frac { \sigma } { R _ { 1 } + R _ { 2 } }
$$

$$
\pmb { k } \cdot \pmb { S } \cdot \pmb { n } = \frac { \hat { \sigma } \sigma } { \hat { \sigma } \pmb { k } }
$$

The location of the interface is determined by the normal projection of Eq.(7). The tangential projection of Eq.(8) defines the driving thermocapillary force. Since the liquid is assumed to be incompressible, its total volume must remain constant,

$$
\int _ { 0 } ^ { L } F ^ { 2 } \mathrm { d } z = \mathrm { c o n s t }
$$

# Boundary and Initial Conditions

The boundary conditions are written as follows:

At the interface $( r ^ { * } = F ( z ^ { * } ) , 0 { \le } z ^ { * } { \le } 1 , 0 { \le } \theta { < } 2 \pi ) , \theta _ { 1 } = \theta _ { 2 } ,$

$$
\frac { \mu _ { 1 } } { \mu _ { 2 } } \frac { \hat { { \sigma } } u _ { 1 } ^ { * } } { \hat { { \sigma } } z ^ { * } } - \frac { \hat { { \sigma } } u _ { 2 } ^ { * } } { \hat { { \sigma } } z ^ { * } } = M a \frac { \hat { { \sigma } } \theta } { \hat { { \sigma } } r ^ { * } } , \frac { \mu _ { 1 } } { \mu _ { 2 } } \frac { \hat { { \sigma } } \nu _ { 1 } ^ { * } } { \hat { { \sigma } } r ^ { * } } - \frac { \hat { { \sigma } } \nu _ { 2 } ^ { * } } { \hat { { \sigma } } r ^ { * } } = M a \frac { \hat { { \sigma } } \theta } { \hat { { \sigma } } z ^ { * } } , \frac { \mu _ { 1 } } { \mu _ { 2 } } \frac { \hat { { \sigma } } w _ { 1 } ^ { * } } { \hat { { \sigma } } \theta } - \frac { \hat { { \sigma } } w _ { 2 } ^ { * } } { \hat { { \sigma } } \theta } = M a \frac { \hat { { \sigma } } \theta } { r \hat { { \sigma } } \theta } .
$$

At the outer wall $( r ^ { * } = r _ { 2 } / L , - 0 . 7 5 / L \le z ^ { * } \le 2 . 2 5 / L , 0 \le \theta < 2 \pi ) , \frac { \partial \theta } { \partial r } = 0 .$

The initial condition is expressed as follows $( t = 0$ ）， $u ^ { * } = \nu ^ { * } = w ^ { * } = 0 ,$ （2号 $\scriptstyle { \Theta = 0 }$

# Validation of the numerical system

# Results and discussion

The fundamental equations are discretized by the finite volume method on a non-uniform staggered grid system which can prevent unphysical oscillations of the computed pressure.A finer mesh gradation is utilized in the regions near the upper and lower disks,as well as the interface.The central difference approximation is applied to the diffusion terms while the second order upwind scheme is used for the convective terms.The pressureimplicit with splitting of operators (SIMPLE) algorithm is used to handle the pressure-velocity coupling. The present numerical code is validated by comparing the dimensionless temperature distributions on free-surface with the result of Zeng et al.[3],as shown in Fig.2. Our numerical result is in a good agreement with Zeng's.

In order to check the grid independence,simulations with four sets of different meshes are performed at $M a =$ $1 . 1 \times 1 0 ^ { 4 }$ ，as shown in Table 2.As it can be seen, these four sets of grids show almost same maximum axial velocity and average temperature at the monitoring point $A ( r / r _ { 1 } = 0 . 5$ ， $\theta = 0 ^ { \circ }$ ， $z / L = 0 . 5$ ).Thechoice of grid $8 0 ^ { r } \times$ $1 2 0 ^ { \theta } \times 8 0 ^ { z }$ (M3） is made corresponding to a reasonable compromise between the minimum dependence of the threshold of the instability upon the mesh size and the computational time.For each time step (using the adapted calculation time step),thequotient Q=|+|/max is calculated for all dependent variables at all grid points. If $Q { \le } 1 0 ^ { - 6 }$ is valid for all variables at all grid points, the solution is interpreted as converged.

The thermocapillary convection appears as a steady flow when $M a$ is small, which is called the‘stable flow'. When Ma exceeds a certain threshold value, this stable flow will however change to oscillatory convection. In this investigation, the Ma varies from $1 . { \dot { 1 } } \times 1 0 ^ { 4 }$ to $1 . 8 2 \times$ ${ 1 0 } ^ { 4 }$ and other parameters of the liquid bridge are kept constant.

![](images/011a3d1a6a559734d4c1ddc9e9edc9274669419dd16ae39b5fb858bedf1e735c.jpg)  
Fig.2Dimensionless temperature distributions on free-surface with $A r { = } 1$ $P r { = } 1$ ， $\scriptstyle { M a = 1 0 0 0 }$

# Free-surface Deformation

The deformation of an interface in microgravity may result from two different contributions [14],fluid dynamic pressure induced by fluid motion and the capillary pressure due to the change of interfacial tension as shown in Eq. (5). The normal viscous stress now promotes a bulging near both the hot and the cold corners.And this bulge is accelerated by the positive radial flow near the hot corner and suppressed by the negative radial flow near the cold corner (see Fig.5(a)). Thus,the extent of bulging out near the hot wall is much larger than near the cold wall.At the same time, due to the constant volume of the liquid bridge,the interface is constricted at the mid-plane of the liquid bridge.As a result, the free-surface presents a typical narrow‘neck-shaped’ structure with convex near the cold and hot walls and concave at the middle section of the liquid bridge,as shown in Fig. 3(a).For a better understanding of the characteristics, the free-surface deformation at different circumferential positions is also conducted,as shown in Fig.3(b).It is evident that the free-surfaces show a noticeable oscillation and axisymmetric,but non-centrosymmetry distribution. The bulge point has axial positions at $z = 0 . 2 2 5 \ \mathrm { c m }$ and $1 . 4 4 3 ~ \mathrm { c m }$ ，and the biggest contraction point has axial position at $z = 0 . 9 1 1 \ \mathrm { c m }$ .The free-surfaces are almost coincide at $\theta = 0 ^ { \circ }$ and $\theta = 1 8 0 ^ { \circ }$ ，and they are also the same at $\theta = 9 0 ^ { \circ }$ as that $\theta = 2 7 0 ^ { \circ }$ .Moreover, the outward bulgingis larger than inward shrinking at $\theta = 9 0 ^ { \circ }$ and $\theta =$ $2 7 0 ^ { \circ }$ ，while the outward bulging is smaller than inward shrinking at $\theta = 0 ^ { \circ }$ and $\theta = 1 8 0 ^ { \circ }$ . This specific bulging mode makes the total volume of deformed liquid bridge equal to that of the initial cylindrical one.

Figure 4 illustrates the free-surface deformation at $M a$ $= 1 . 1 { \overset { - } { \times } } 1 0 ^ { 4 }$ on different horizontal planes, where $x$ and $y$ are defined as $r \mathrm { c o s } \theta$ and $r s i n \theta .$ ，respectively. The freesurfaces exhibit an elliptical-shape distribution with long axis at $y$ direction and short axis along $x$ direction.Moreover,the free-surfaces bulge outward on $z = 0 . 2 2 5$ cm and $z = 1 . 4 4 3 \ \mathrm { c m }$ planes while shrinking inward on $z =$ 0.911 cm plane,which is consistent with the free-surface deformation shown in Fig.3(b).

# BasicFlowandHeatTransferCharacteristics

As the temperature difference happens between the two co-axial circular disks,surface tension gradient (called thermocapillary force) generates on the interface between the melt and air. Thus, flow occurs in the liquid bridge from hot disk to cold disk along the interface,and then returns to the hot disk in the center. This is known as the thermocapillary convection. The flow along the freesurface towards the cold diskiscalled a surface flow,and theinteriorflowtowardsthehotdiskiscalledaback-flow herein.

The thermocapillary convection is also found in the liquid bridge with deformable free-surface.However, the flow structure is significantly different from that with a fixed surface.The streamlines present a narrow‘neckshaped’structure,which presents the similar behavior as the free-surface shape shown in Fig.3.The streamlines bulge outward at two ends of zone and shrink inward at the mid-plane in deformable free-surface case (Fig.5(a)), which is not found in fixed surface case (Fig. 5(b)). It is also noticed that,both in deformable free-surface and fixed surface cases, two larger and axisymmetric convectioneddies(A andB）are formedin thewholemolten zone.The vortexes A and B are closely located at the lower region of the molten zone in deformable free-surface case,while they are closely located at the midline of EF in the fixed free-surface case.This is caused by the free-surface shrinking inward at $z = 0 . 9 1 1 \ \mathrm { c m }$ in the deformable free-surface case which pushes the vortex downward. Owing to thermocapillary convection in liquid bridge,convective heat transfer plays a crucial role here.The surface flow near the interface is strong as well as the back-flow in the center. Thus,an obvious distortion is found nearby the free-surface and the center of the molten zone.However,it should be noted that the temperature distributions are different between the deformable free-surface and fixed surface cases,as shown in Fig. 5(c,d).The distortion of isotherms in deformable freesurface case is larger than that in the fixed surface case. And the area of narrow and sharp low temperature area in deformable free-surface case is also bigger than that in the fixed surface case.In conclusion,the free-surface deformation has a significant effect on the flow structure and temperature distribution of the liquid bridge.It is necessary to consider the effect of free-surface deformation when investigating the thermocapillary convection in the floating-zone crystal growth.

Table 2Mesh dependence   

<html><body><table><tr><td>Meshes</td><td>M1</td><td>M2</td><td>M3</td><td>M4</td></tr><tr><td>Number of nodes</td><td>70'×100×70²</td><td>75'×110×75²</td><td>80"×120×80²</td><td>85'×130×85²</td></tr><tr><td>Vmax (cm·s−1)</td><td>8.598</td><td>8.542</td><td>8.531</td><td>8.528</td></tr><tr><td>TA (K)</td><td>1685.019</td><td>1685.031</td><td>1685.037</td><td>1685.04</td></tr></table></body></html>

![](images/19bbd2d83e366a8d51e71a351129443e806b10b5ee45768aadcc865e6056ea5e.jpg)  
Fig.3Free-surface deformation at $M a = 1 . 1 \times 1 0 ^ { 4 }$ ：(a) Free-surface deformation at ${ \boldsymbol { t } } { - } { \boldsymbol { t } } _ { 0 }$ ；(b)Free-surface deformation at different circumferential positions.

![](images/4bddb01271e93120771e9c4d5dc2775b845406e051cdea07d678b84febc87acd.jpg)  
Fig.4Free-surface deformation at $M a { = } 1 . 1 { \times } 1 0 ^ { 4 }$ on different horizontal planes

Figure 6 illustrates the temperature and azimuthal velocity distributions along circumferential direction at different radii on the $z / L = 0 . 5$ plane at $M a = 1 . 1 \times 1 0 ^ { 4 }$ The temperature distributions show a sinusoidal fluctuation shapes and all the three lines are symmetric on $\scriptstyle \theta = 1 8 0 ^ { \circ }$ (Fig. 6(a)). The amplitude of the three curves is almost consistent and the temperature fluctuations keep the same pace at different radii. So we can suspect a strong oscillation in the whole molten region.At $r / r _ { 1 } =$ 0.5 (near the center of liquid bridge), the average temperature is lower as the fluid is cooled down by the lowtemperature fluid from the cold wall. At $r / r _ { 1 } = 0 . 8$ with weak back-flow and surface flow relatively strong, the average temperature is significantly higherthan that at $r / r _ { 1 } = 0 . 5$ ,butlowerthan that at $r / r _ { 1 } = 1$ . At $r / r _ { 1 } = 1$ (near the interface)，the surface flow becomes stronger and makes a strong heat transfer. Together with the heating up of the melt by the high-temperature fluid from the hot wall, the average temperature is the highest. As shown in Fig. 6(b), the azimuthal velocity keeps the same trend at $r / r _ { 1 } = 0 . 5$ and $r / r _ { 1 } = 1$ ,while the azimuthal velocity at $r / r _ { 1 }$ $= 0 . 8$ exhibits the opposite trend. Moreover, the azimuthal velocity presents a strong fluctuation and keeps the approximate identical amplitude at different radii on the $z / L = 0 . 5$ plane.

![](images/473348a32943fb71fab459c391265220338eae237cac42bd89788bfb4fdbdb3c.jpg)  
Fig.5Streamlines (a,b) and isotherms (c,d) on $\theta = 9 0 ^ { \circ }$ plane at $M a = 1 . 1 \times 1 0 ^ { 4 }$

# Marangoni Number Dependence

Figure 7 presents the isotherms and radial velocity at different $M a$ on the $z / L = 0 . 5$ plane. At $M a = 1 . 1 \times 1 0 ^ { 4 }$ (Fig. 7(a)), two large high-temperature areas appear near the free-surface. The low temperature area presents an elliptical-shape in the center.When the $M a$ is $1 . 4 6 \times 1 0 ^ { 4 }$ (Fig.7(b)), the isotherms exhibit a hexagonal distribution and the wave number $m$ is 6.It implies an increase of the instability of thermocapillary convection.When the $M a$ further increases to $1 . 6 4 \times 1 0 ^ { 4 }$ (Fig. 7(c)), the wave number m increases to 7,which also demonstrates an enhancement of the instability of thermocapillary convection. The radial velocity distribution at different $M a$ on $z / L =$ 0.5 plane all exhibits a‘petal' shape,as shown in Fig.7(d e, f). At $M a = 1 . 1 \times 1 0 ^ { 4 }$ (Fig. 7(d)), two pairs of vortexes occur at the center on the $z / L = 0 . 5$ plane.When $M a =$ $1 . 4 6 \times 1 0 ^ { 4 }$ (Fig. 7(e), the petal number $m$ is 6. When the Ma further increases to $1 . 6 4 \times 1 0 ^ { 4 }$ (see Fig. 7(f)), the petal number $m$ increases to 7 with a small petal not easy spotted at the right side.Moreover, the number and the outline of the‘petal’ increase with $M a$ ，which indicates that the hydrothermal wave number $m$ and the strength of the thermocapillary convection increase withMa.With a careful comparison of Fig.7(a, b,c) and Fig. $7 ( \mathrm { d } , \mathrm { e } , \mathrm { f } )$ it is found that the petal number of the radial velocity is equal to the hydrothermal wave number at different $M a$ This feature indicates a strong coupling between temperature field and flow field in the whole molten zone.In other words,thedistribution offlowfield inducesa similar temperature field.

![](images/12e2f73b5f14ba6a29e8fd558493117dbebaf2df36b4b66cfcb03f96e8321aeb.jpg)  
Fig.6Temperature and velocity distributions along circumference of different radii on the $z / L = 0 . 5$ plane at $M a = 1 . 1 \times 1 0 ^ { 4 }$

![](images/2740406348337698116eec6fe8d0f6c500ffba1f87a5bac87ee4595ce3e2d563.jpg)  
Fig.7Isotherms and radial velocity distributions of different Ma on the $z / L { = } 0 . 5$ plane

For the effect of $M a$ number,the free-surface deformation $F ( z )$ at different circumferential positionsis shown in Fig.8.Both at $\theta = 0 ^ { \circ }$ and $\theta = 9 0 ^ { \circ }$ ,itis found that the axial position of bulge and contraction points, do not change with Ma.However, due to non-centrosymmetry, the free-surface shape is different at circumferential positions. At $\theta = 0 ^ { \circ }$ ，the magnitude of contraction remains constant at $z = 0 . 9 1 1$ cm and the extent of outward bulging increases with $M a$ at $z = 0 . 2 2 5 \ \mathrm { c m }$ and $z = 0 . 1 4 4 3$ cm (Fig. 8(a)).Conversely,at $\theta = 9 0 ^ { \circ }$ ，theextent of outward bulging remains constant at $z = 0 . 2 2 5 \ \mathrm { c m }$ and $z =$ $0 . 1 4 4 3 ~ \mathrm { c m }$ and the magnitude of contraction increases with the increment of $M a$ at $z = 0 . 9 1 1 \ \mathrm { c m }$ (Fig. 8(b)). Both the extent of bulge at $\theta = 0 ^ { \circ }$ and the contraction at $\theta$ $= 9 0 ^ { \circ }$ increases with increasing $M a$ .The volume of convex at two ends of the zone is equal to that of concave in the central regionat different Ma. Consequently, the total volume of deformed liquid bridge conforms to the initial cylindrical one.

$M a$ at different circumferential positions.The deformation ratio $\xi$ is defined as $\xi = ( r _ { \mathrm { m a x } } - r _ { \mathrm { m i n } } ) / r _ { 1 }$ with $r _ { \mathrm { m a x } }$ and $r _ { \mathrm { m i n } }$ denoting the maximum and minimum radius of the freesurface,respectively.The solid and dottedlines stand for the nonlinear fitting curve of the deformation ratio at $\theta =$ $0 ^ { \circ }$ and $\theta = 9 0 ^ { \circ }$ ,respectively. The deformation ratio $\xi$ increaseswith Maat first,and then increases slowlyboth at $\theta = 0 ^ { \circ }$ and $\theta = 9 0 ^ { \circ }$ .For instance,at $\theta = 0 ^ { \circ }$ , the increment $\Delta \xi$ is 0.05012 when $M a$ increases from $1 . 1 \times 1 0 ^ { 4 }$ to 1.46 $\times 1 0 ^ { 4 }$ ，while the increment $\Delta \xi$ is only 0.02208 as $M a$ increasing from $1 . 4 6 \times 1 0 ^ { 4 }$ to $1 . 8 2 \times 1 0 ^ { 4 }$ . Likewise, the deformation ratio $\xi$ at $\theta = 9 0 ^ { \circ }$ shows the similar behavior with that at $\theta = 0 ^ { \circ }$ . In addition,at the same $M a$ ，thedeformation ratio $\xi$ at $\theta = 0 ^ { \circ }$ is larger than that at $\theta = 9 0 ^ { \circ }$ ：

# Conclusions

In this paper, the characteristics of flow and heat transfer in the Floating zone crystal growth process under microgravity are investigated using the VOF tracking method.Theeffectof $M a$ on free-surface deformation as well as the instability of thermocapillary convection is also calculated and analyzed. The following conclusions are drawn,

Under microgravity environment, the free-surface is convex near the cold and hot walls,while concave at the mid-plane of the liquid bridge.The free-surface shows a noticeable axisymmetric and elliptical-shape distribution along circumferential direction. And its presents a typical narrow ‘neck-shaped' structure along axial direction.Moreover,both at $\theta$ $= 0 ^ { \circ }$ and $\theta = 9 0 ^ { \circ }$ ， the deformation ratio $\xi$ increases rapidly with $M a$ at first,and then increases slowly. The free-surface deformation makes a significant effect on the flow structure and temperature distribution of the liquid bridge.The vortexes are closely located at the lower region of the molten zone in the deformable free-surface case while they are closely locate at the midline of EF in the fixed free-surface case.

![](images/34159517249dad54668752535584c109d9fc67d0f7bfac346e52c3292318ede1.jpg)  
Figure 9 exhibits the deformation ratio $\xi$ varies with   
Fig.8Free-surface deformation $F ( z )$ at different circumferential positions

![](images/a9f02709767b192ad7448e92e7978790c4165f36b5726ea7eb9666fc5eba1578.jpg)  
Fig.9Deformation ratio $\xi$ varies with $M a$ at different circumferential positions

：The instability of the thermocapillary convection is enhanced with $M a$ . The hydrothermal wave number $m$ increases from 2 to 7 with the $M a$ increasing from $1 . 1 \times 1 0 ^ { 4 }$ to $1 . 6 4 \times 1 0 ^ { 4 }$ ：

# Acknowledgements

This work is supported by National Natural Science Foundation of China(Grant No.51276089)and the Sixtalents Peaks project of Jiangsu Province (2015-XNY003).

# References

[1]Zeng,Z.,Mizuseki,H.,Shimamura,K.,Higashino,K., Fukuda, T.,and Kawazoe,Y.,(2oo1),Marangoni convection in model of floating zone under microgravity, Journal of crystal growth, Vol. 229,No.1, pp. 601-604.   
[2]Melnikov,D.E.,Shevtsova,V. M.,and Legros,J.C., (2005),Route to aperiodicity followed by high Prandtlnumber liquid bridge.1-g case, Acta astronautica, Vol. 56, No. 6,pp.601-611.   
[3]Zeng,Z.,Mizuseki,H., Shimamura,K., Fukuda, T., Kawazoe,Y.,and Higashino,K.,(2oo2),Usefulness of experiments with model fluid for thermocapillary convection—effect of Prandtl number on two-dimensional thermocapillary convection,Journal of crystal growth,Vol. 234,No. 1, pp.272-278.   
[4]Minakuchi,H., Takagi, Y., Okano,Y.,Gima, S.,and Dost, S.,(2014),The relative contributions of thermo-solutal Marangoni convections on flow patterns in a liquid bridge, Journal of Crystal Growth,Vol.385,pp. 61-65.   
[5]Lappa,M.，Savino,R.,and Monti，R., (2001)，Threedimensional numerical simulation ofMarangoni instabilities in liquid bridges: influence of geometrical aspect ratio,International journal for numerical methods in fluids, Vol. 36,No.1, pp.53-90.   
[6]Lappa,M.,(20o5),Analysis of flow instabilities in convex and concave floating zones heated by an equatorial ring under microgravity conditions, Computers & fluids, Vol. 34, No. 6, pp. 743-770.   
[7]Lyubimova,T.P.,and Skuridyn,R.V., (2014),The influence of vibrations on the stability of thermocapillary flow in liquid zone, International Journal of Heat and Mass Transfer, Vol. 69, pp.191-202.   
[8]Gaponenko, Y., Glockner, S., Mialdun, A.,and Shevtsova, V., (2011), Study of a liquid bridge subjected to interface shear stresses,Acta astronautica, Vol. 69, No.3, pp.119- 126.   
[9]Gaponenko,Y.，Mialdun，A.，and Shevtsova, V.,2012, Shear driven two-phase flows in vertical cylindrical duct, International journal of multiphase flow,Vol. 39,pp. 205-215.   
[10]Tiwari, S.,and Nishino,K.,(2007),Numerical study to investigate the effect of partition block and ambient air temperature on interfacial heat transfer in liquid bridges of high Prandtl number fluid, Journal of crystal growth, Vol. 300, No.2, pp.486-496.   
[11]Xun,B.,Li,K.,Hu,W.R.,and Imaishi,N.,(2011),Effect of interfacial heat exchange on thermocapillary flow in a cylindrical liquid bridge in microgravity， International Journal of Heat and Mass Transfer,Vol. 54,No.9, pp. 1698-1705.   
[12]Melnikov,D.E.,and Shevtsova, V.M.,(2014), The effect of ambient temperature on the stability of thermocapillary flow in liquid column, International Journal of Heat and Mass Transfer, Vol. 74, pp.185-195.   
[13]Kamotani, Y., Ostrach, S.,and Vargas,M., (1984),Oscillatory thermocapillary convection in a simulated floating-zone configuration, Journal of Crystal Growth, Vol. 66, No. 1, pp. 83-90.   
[14]Kuhlmann,H.C.,& Nienhuser, C.(2002).Dynamic freesurface deformations in thermocapillry liquid bridges. Fluid dynamics research, 31(2),103-127.   
[15]Sim, B. C., Kim, W. S.,and Zebib,A., (2004), Dynamic free-surface deformations in axisymmetric liquid bridges, Advances in Space Research,Vol.34, No.7, pp.1627- 1634.   
[16]Shevtsova,V.，Mialdun,A.， Ferrera, C.，Ermakov，M., Cabezas,M. G.,and Montanero,J. M., (2008), Subcritical and oscillatory dynamic surface deformations in noncylindrical liquid bridges, FDMP:Fluid Dynamics & Materials Processing, Vol. 4, No.1, pp.43-54.   
[17]Liang, R.,and Kawaji, M., (2009), Surface oscillation of a liquid bridge induced by single and multiple vibrations, MicrogravityScience andTechnology, Vol.21,.1,pp. 31-37.   
[18]Ahmed,I., Masud,J., Nigar, M.,and Khan, A. M., (2010), Effect of First Vibration Mode on Sub-Critical Thermocapillary Convection in Floating Zone Liquid Bridge,

AIAA-2010-637, 48th AIAA Aerospace Sciences Meet- formation of Thermo-Solutocapillary Convection in Axiing,Anaheim, USA, pp.4-7. symmetric Liquid Bridge,Microgravity Science and [19] Zhou, X. M.,and Huang, H. L., (2010), Numerical simu- Technology,Vol. 27,No.1,pp.39-47. lation of steady thermocapillary convection in a two-layer [21]Dold, P.， Croll,A.,Lichtensteiger, M., Kaiser, T.,and system using level set method, Microgravity Science and Benz,K.W.,(2oo1),Floating zone growth of silicon in Technology, Vol.22, No.2, pp.223-232. magnetic fields: IV. Rotating magnetic fields, Journal of [20] Zhou, X. M.,and Huai, X.L.,(2015), Free Surface De- crystal growth, Vol.231, No.1, pp.95-106.