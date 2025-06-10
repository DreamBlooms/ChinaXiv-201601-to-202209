# Influence of Thermal and Solutal Marangoni Effects on Free Surface Deformation in an Open Rectangular Cavity

ZHOU Xiaoming, HUAI Xiulan

Institute of Engineering Thermophysics, Chinese Academy of Sciences,Beijing,100190, China $\copyright$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

Steady thermo-solutocapillary convection in a rectangular cavity with deformable free surface under microgravity condition is numerically studied,where level set method is employed to capture the free surface deformation. Both the temperature and solute concentration gradients are applied horizontaly.The computational results show that,as the thermal to solutal Marangoni number ratio varies between -1O and $^ { - 1 }$ (namely, $- 1 0 \leq \mathrm { R } _ { \sigma } < - 1 \$ ),the flow field exists one anti-clockwise rotating convective celldriven by thermocapilary convection,and the free surface bulges out near the left end wall and bulges in near the right end wall. As $- 1 < \operatorname { R } _ { \sigma } < 0$ ,the flow field exists one clockwise rotating convective celldriven by solutocapilary convection,and the free surface bulges out near the right end wall and bulges in near the left end wall.As $\operatorname { R } _ { \sigma } = - 1$ ,the flow field consists of one clockwise and one anti-clockwise rotating convective cels,and the free surfacebulges inat the central pointand bulges out near the left and right end walls.

# Keywords: thermo-solutocapillary convection; rectangular cavity; free surface; level set method

# Introduction

Thermo-solutocapillary convection is driven by sur face tension gradient due to the variation of temperature and solute concentration at free surface.This phenomenon widely exists in crystal growth process,welting process,and many other industrial processes.The most widely studied model associated with the thermo-solutocapillary convection is a rectangular cavity with temperature and solute concentration differences between two end walls.At 1986,Bergman [1] numerically simulated the double-diffusive Marangoni convection in a rectangular cavity with horizontal temperature and concentration gradients,and he found that even though the opposing thermal and solutal capillary forces are of equal magnitude, convection occurs when thermal Marangoni number exceeds a critical number.Chen etal[2] studied the onset of steady and oscillatory flow of double-diffusive Marangoni convection when the resultant thermal and solutal Marangoni effects are equal and opposing,and the effectsof theLewisnumber,thePrandtlnumberand the aspect ratio on stability were analyzed. Similarly, Li et al. [3] further investigated the transitions to chaos in doublediffusive Marangoni convection in a rectangular cavity with horizontal temperature and concentration gradients. Zhan et al. [4] numerically investigated three-dimensional double-diffusive Marangoni convection in a cubic cavity with both the temperature and solute concentration gradients were applied horizontally,and the effect of surface-tension Reynolds number,surface tension ratio and Lewis number on the flow regime was discussed. Chen and Chan [5] studied the stability of double-diffusive Marangoni convection in a horizontal fluid layer driven by the combined effects of buoyancy and surface tension.Recently, Li etal. [6] investigate the characteristics of the coupled thermal and solutal capillary convection with the radial temperature and solute concentration gradients in a shallow annular pool by asymptotical analysis.Furthermore,Li et al.[7] simulated the transition characteristics of the thermal-solutal capillary convection numerically in an annular pool.However,all these studies were dedicated to the situation of infinite small capillary number,and the deformation of free surface or interface was neglected in order to avoid the simulation complexity associated with the unknown free surface or interface shapes.

<html><body><table><tr><td>NOI C solute concentration, wt%</td><td></td><td>U</td><td>characteristic velocity, U = Max(γτ△T|,γc△Cl)/ μ (m:s*1)</td></tr><tr><td>CaT</td><td>thermal Capilary number,，CaT</td><td>x,y</td><td>coordinate system (m)</td></tr><tr><td>Cac</td><td>00</td><td>Greek symbols</td><td></td></tr><tr><td></td><td>00 solute CapillayumberCc=YC</td><td></td><td></td></tr><tr><td>D</td><td> solute diffusivity (m²·s-1)</td><td>a</td><td>thermal diffusivity(m².s-1)</td></tr><tr><td>k</td><td>curvature</td><td></td><td>level set function</td></tr><tr><td>L</td><td>characteristic length (m)</td><td></td><td>surfacetensiontemperaturecoefficient (N·mT-1)</td></tr><tr><td>Le</td><td>D Lewis number, Le=</td><td></td><td>surface tension solute concentration coefi- cient (N·m-1·wt%-1)</td></tr><tr><td>Mac</td><td>Solutal Marangoninumber,MacYCL</td><td></td><td>thermal conductivity (W·m-1· K-1)</td></tr><tr><td>Mat</td><td>μa</td><td></td><td>dynamic viscosity (kg·s-1·m-1)</td></tr><tr><td></td><td>μa thermal Marangoninumber,Mar=Y</td><td>从</td><td></td></tr><tr><td>n</td><td>unit vector normal to the interface</td><td>V</td><td>kinematic viscosity (m²·s-1)</td></tr><tr><td>p</td><td>Pressure (Pa)</td><td>p</td><td>density (kg:m3)</td></tr><tr><td>Pr</td><td>Prandtl number， Pr = α1</td><td>9</td><td>surface tension,</td></tr><tr><td></td><td>V</td><td></td><td>σ=σ0+γt(T-T0)+γc(C-Co) (N·m*1)</td></tr><tr><td>Re</td><td>PUL Reynolds number, Re = 5</td><td>0</td><td> initial surface tension at T= To and C = Co</td></tr><tr><td>Rg</td><td>μ ratio of thermal to solutal Maragoni number,</td><td>Subscripts</td><td></td></tr><tr><td></td><td>R=YT·△T Yc·△C</td><td></td><td></td></tr><tr><td>t</td><td>time (s)</td><td>g</td><td>gas</td></tr><tr><td>T</td><td>temperature (K)</td><td></td><td></td></tr><tr><td></td><td></td><td></td><td>liquid</td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td></tr><tr><td>u</td><td>velocity vector (m.s-1)</td><td></td><td></td></tr></table></body></html>

It iswellknown that the deformationof free surface or interface has an important influence on the pure thermocapillary convection,in particular for the onset of the oscillatory flow [8]. Microgravity experiment by Koster [9]indicated that,a detailed investigation of thermocapillary convection in multilayered fluid systems needed to take account for finite interface deformations in conjunction with a suitable dynamic contact line condition. Moreover,thedeformation effectsoffree surface orinterface in the numerical simulation of pure thermocapil lary convection was considered by many investigators [10-14].

The authors first considered the dynamic deformation of free surface in the numerical simulation of thermo solutocapillary convection in our previous paper [15], and in the present work we further investigate the influence of thermal and solutal Marangoni effects on free surface deformation in an open rectangular cavity.

# PhysicalandMathematical Models

The two-dimensional model is an opened liquid-filled rectangular cavity,as shown in Figure 1,and the length and height are $\mathrm { ~ L ~ }$ andH, respectively. The cavity is filled with a binary fluid,and the gas-liquid interface on the top is a deformable free surface.Different temperatures and concentrations are applied at the left $( \mathrm { T } _ { 1 } , \mathrm { C } _ { 1 } )$ and right $( \mathrm { T } _ { 2 } , \mathrm { C } _ { 2 } )$ end walls,where $\mathrm { T } _ { 1 } < \mathrm { T } _ { 2 }$ and $\mathrm { C } _ { 1 } < \mathrm { C } _ { 2 }$ . The nonslip boundary condition is adopted for the end and bottom walls,and the surface tension force is applied on the free surface.All the thermal properties are assumed to be constant except for the surface tension,which is allowed to vary linearly with the liquid temperature and solute concentration. Thus the surface tension can be formulated as,

$$
\sigma = \sigma _ { 0 } + \gamma _ { \mathrm { T } } \big ( T - T _ { 0 } \big ) + \gamma _ { C } \big ( C - C _ { 0 } \big )
$$

Where $\begin{array} { r l r } { \sigma _ { 0 } } & { = } & { \sigma \mathrm { ( T _ { 0 } , } \quad C _ { 0 } ) , \quad \gamma _ { \mathrm { T } } = - \big ( \hat { \sigma } \sigma / \hat { \sigma } T \big ) _ { C } \vphantom { \frac { 1 } { 1 } } \mathrm { , } } \end{array}$ （2号 （204号 $\gamma _ { C } = - { \left( \hat { o } \sigma / \hat { \sigma } C \right) } _ { T }$ ．Thermophysical properties of the fluid are estimated at the reference temperature $\mathrm { T } _ { 0 }$ and concentration $\mathrm { C } _ { 0 }$ ，which are set to be equal to $\mathrm { T } _ { 1 }$ and $\mathrm { C } _ { 1 }$ respectively. Moreover,only the liquid surface tension increases with concentration and decreases with temper ature are considered.The fluid flow is assumed to be laminar,and buoyancy effects are neglected in the present study.

![](images/c6d8f33ed83e1a9c61af9841f589643f586f992a86a55f9d62eda2a8f579adc2.jpg)  
Fig.1Physical model

The non-dimensional variables of velocity, tempera ture，concentration，coordinates,time and pressure are defined as $V = \frac { \pmb { u } } { U } , \Theta = \frac { T - T _ { 1 } } { T _ { 2 } - T _ { 1 } } , C ^ { * } = \frac { C - C _ { 1 } } { C _ { 2 } - C _ { 1 } }$ ， $( \mathrm { X } , \mathrm { Y } ) =$ ${ \frac { \big ( x , y \big ) } { L } } , \ \tau = { \frac { t U } { L } } , \ P = p / ( \rho _ { l } U ^ { 2 } ) ,$ respectively. Here, $U =$ $M a x \big ( \vert \gamma _ { T } \Delta T \vert , \vert \gamma _ { C } \Delta C \vert \big ) \big / \mu _ { l }$ is characteristic velocity. Then, the non-dimensional Navier-Stokes equations governing the thermo-solutocapillary convection are expressed as follows:

$$
\nabla \cdot \boldsymbol { V } = 0
$$

$$
\frac { \partial { \bf V } } { \partial \tau } + \boldsymbol { \nabla } \cdot \big ( { \bf V } { \bf V } \big ) = - \frac { 1 } { \tilde { \rho } } \boldsymbol { \nabla } P + \frac { 1 } { \tilde { \rho } \mathrm { R e } } \boldsymbol { \nabla } \cdot \big ( \tilde { \mu } \boldsymbol { \nabla } { \bf V } \big )
$$

$$
+ \frac { 1 } { \tilde { \rho } \operatorname { R e } } \boldsymbol { \nabla } \cdot ( \tilde { \mu } \boldsymbol { \nabla } \mathbf { V } ) ^ { T } + \frac { 1 } { \tilde { \rho } \operatorname { R e } } \ ( \boldsymbol { \nabla } _ { s } \Theta + \frac { \boldsymbol { \nabla } _ { s } \boldsymbol { C } ^ { * } } { R _ { \sigma } } ) \delta ( \phi )
$$

$$
+ \frac { 1 } { \tilde { \rho } \mathrm { R e } } \left( \frac { 1 } { C a } + \Theta + \frac { C ^ { * } } { R _ { \sigma } } \right) \frac { k \left( \phi \right) \delta \left( \phi \right) \nabla \phi } { \tilde { \rho } }
$$

$$
\frac { \partial \Theta } { \partial \tau } + \boldsymbol { V } \cdot \boldsymbol { \nabla } \Theta = \frac { 1 } { \tilde { \rho } \tilde { C } M a } \boldsymbol { \nabla } \cdot \left( \tilde { \lambda } \boldsymbol { \nabla } \Theta \right)
$$

$$
\frac { \partial \boldsymbol { C } ^ { * } } { \partial \tau } + \boldsymbol { \mathbf { V } } \cdot \boldsymbol { \nabla } \boldsymbol { C } ^ { * } = \frac { 1 } { P r L e \boldsymbol { \mathrm { R e } } } \boldsymbol { \nabla } \cdot \left( \tilde { \boldsymbol { \mathrm { D } } } \boldsymbol { \nabla } \boldsymbol { C } ^ { * } \right)
$$

where $\tilde { \mu } = \mu / \mu _ { l } , \tilde { \rho } = \rho / \rho _ { l } , \tilde { \lambda } = \lambda / \lambda _ { l } , \tilde { D } = D / D _ { l }$ and $\tilde { C } _ { p } = C _ { p } / C _ { p l }$ are the dimensionlessviscosity,density, thermal conductivity, solute diffusivity,and specific heat,respectively.δ is the smeared-out Dirac delta function, and $\nabla _ { s } = \left( \pmb { I } - \pmb { n } \pmb { n } \right) \cdot \nabla$ is free surface gradient operator. The dimensionless parameters are defined as follows: Thermal Marangoni numberMar=Y△TL Solutal Marangoni number Mac=Y△CL Marangoni number $\scriptstyle \mathrm { M a = M a x } ( \mid M a _ { T } \mid , \mid M a _ { C } \mid )$ ，Reynolds number $\mathrm { R e } = \frac { U L } { \nu _ { l } }$ ， Capillary number $\mathrm { C a } = \mathrm { M a x } ( | \mathrm { C } a _ { T } | , | C a _ { C } | ) .$ （2 the ratio of thermal Marangoni number to solutal Marangoni R=Yr:△T $R _ { \sigma } = { \frac { \gamma _ { T } \cdot \Delta T } { \gamma _ { C } \cdot \Delta C } }$ ，Prandtl number Pr =α and Lewis number $\mathrm { L e } = \frac { \alpha _ { l } } { D _ { l } }$ .The subscripts of g and l note the gas and liquid, respectively. The continuum surface force(CSF) model[16] is used to reformulate the surface tension as a volume force,and the fourth and fifth terms at the right hand of the momentum equation are the tangential and normal surface tension, respectively.

The level set method is employed to capture the free surface implicitly by introducing a smooth level set function,with the zero level set as the free surface,positive value underside the free surface, and negative value upside the free surface.Consider the following free surface evolution equation:

$$
\frac { \partial \phi } { \partial \tau } { + \boldsymbol { V } } \cdot \nabla \phi = 0
$$

which will evolve the zero level of $\phi = 0$ exactly as the actual free surface moves. The corresponding physical variantscanbeexpressedas

$$
\begin{array} { c } { { \tilde { \rho } = \eta _ { \rho } + \left( 1 - \eta _ { \rho } \right) H \left( \phi \right) } } \\ { { \tilde { \mu } = \eta _ { \mu } + \left( 1 - \eta _ { \mu } \right) H \left( \phi \right) } } \end{array}
$$

Where $\eta _ { \rho } = \rho _ { \mathrm { g } } / \rho _ { 1 } , ~ \eta _ { \mu } = \mu _ { \mathrm { g } } / \mu _ { l } , ~ H ( \phi )$ is the smeared-out Heaviside function defined by

$$
H { \left( \phi \right) } = \left\{ \begin{array} { l l } { 0 } & { \quad } \\ { \displaystyle \frac { 1 } { 2 } { + } \frac { \phi } { 2 \xi } { + } \frac { 1 } { 2 \pi } \mathrm { s i n } \Biggl ( \frac { \pi \phi } { \xi } \Biggr ) } & { \quad \phi < - \xi } \\ { 1 } & { \quad \phi > \xi } \end{array} \right. 
$$

where $\xi$ is a tunable parameter that determines the size of the bandwidth of numerical smearing.A typical good value is $\xi = 1 . 5 \varDelta Y$

To keep the level set function as a distance function from the front, an approach based on solving the hyper bolic partial differential equation has been presented in reference (Sussman et al. [17]).The reinitialization equation is

$$
\phi _ { Y } = s i g n \big ( \phi _ { 0 } \big ) \big ( 1 - \big | \nabla \phi \big | \big ) , \phi \big ( Y , 0 \big ) = \phi _ { 0 } \big ( Y \big )
$$

Where $\left| \nabla \phi \right| = \sqrt { \phi _ { X } ^ { 2 } + \phi _ { Y } ^ { 2 } }$ ，and the sign function $s i g n _ { \xi } \left( \phi _ { 0 } \right) = \frac { \phi } { \sqrt { \phi ^ { 2 } + \xi ^ { 2 } } } .$

Moreover, in order to make the total mass completely satisfy the mass conservation in time,the mass conserving procedure proposed by Liang et al. [18] is used.

Boundary and Initial Conditions

$$
\Theta { = } 0 , \mathrm { C = } 0 , \mathrm { V = } 0 , \frac { \partial \phi } { \partial X } { = } 0 \mathrm { a t } \mathrm { X = } 0
$$

$$
\Theta { = } 1 , \mathrm { C = } 1 , \mathrm { V = } 0 , \frac { \partial \phi } { \partial X } { = } 0 \mathrm { a t } \mathrm { X = } 1
$$

$$
\frac { \partial \Theta } { \partial Y } = 0 , \frac { \partial C } { \partial Y } = 0 , \mathrm { V } = 0 , \frac { \partial \phi } { \partial Y } = 0 \mathrm { a t } \mathrm { Y } = 0
$$

$$
\Theta \mathrm { = } 0 , \mathrm { C = } 0 , \mathrm { V = } 0 , \phi \left( X , \mathrm { A } \right) = 0 , \mathrm { P = } 0 \mathrm { ~ a t ~ } \tau \mathrm { = } 0
$$

In this paper, we consider the contact conditions of interface with the end walls is contact points fixed, and the gas-liquid interface is a thermally insulated interface.

# Computational method

In this article we use the RKCN projection method presented by Ni et al.[19] to solve the control equations. The Crank-Nicholson implicit technique is employed to update the diffusion term, and the low storage three-stage Runge-Kutta technique is employed to update the convective term. This method has second-order temporal accuracy for variable-density unsteady incompressible flows.The diffusion term in momentum equation is discretized using standard central difference schemes,while the convective term is discretized by high-order compact schemes. The convective term in the level set equation using the third-order ENO scheme.The time step for all the simulations is $1 \times 1 0 ^ { - 3 }$ . This detailed description of the computational method can refer to our previous paper [20].The numerical code is validated by comparing computed surface deformation of pure thermocapillary convection with those from Sim [8] in Figure 2. The parameters for the simulation are $\mathrm { P r } = 1$ ， $\mathbf { A } \mathbf { r } = 1$ ， $\mathrm { C a } = 0 . 0 5$ and $\mathrm { { R e } } = 1$ . The numerical results at $\mathbf { B } \mathbf { i } = 0$ are in good agreement with Sim's results.

The two-dimensional rectangular cavity is discretized with a uniform mesh,and this mesh is determined by refining the mesh size until convergence and constancy of flow velocity, temperature, concentration and free surface deformation is achieved. In this paper the grid $4 0 0 { \mathrm { ~ x ~ } }$ $\times 2 0 0 \ : \mathrm { y }$ is adopted, which meets the demands of convergence.

![](images/68c348e507c962ba4b6fa82e4fff8fa40cfac5cb7f56cd2a174601876a848d78.jpg)  
Fig.2Comparison of free surface deformation with Sim's results

# Results and Discussions

In the open double-diffusive fluid cavity, both the temperature and solute concentration differences between the left and right end walls producea surface tension gradient at free surface,so the thermocapillary and solutocapillary convection in the liquid layer can be induced. The relative importance of the thermocapillary and solu tocapillary convection for the flow depends on the ther mal to solutal Marangoni number ratio ${ \mathrm { \sf R } } _ { \sigma }$ therefore, different convective cell structures and free surface deformation modes under different thermal to solutal Marangoni number $\mathtt { R } _ { \sigma }$ can occur. The numerical simulations are carried out for Prandtl number $ { \mathrm { P r } } = 1$ ，Capillary number $\mathrm { C a } = 0 . 1$ ，Marangoni number $\mathrm { { M a } = 1 0 }$ ，Lewis number $\mathrm { L e } = 1 0$ ,and thermal to solutal Marangoni number ratio $- 0 . 1 \leq R _ { \sigma } \leq - 1 0$

At first, the case of thermal to solutal Marangoni number ratio $\mathtt { R } _ { \sigma } = - 1 0$ is considered,which means the thermocapillary convection dominates the fluid flow. Figure 3 shows the streamline, temperature and solute concentration field distribution.It can be seen that the flow structure has an anti-clockwise rotating convective cell and occupies the whole cavity. Under the action of dominant thermocapillary forces at free surface,the free surface bulges out near the left wall and bulges in near the right wall.At the same time, the temperature and solute concentration contours manifest as gradient distribution along the horizontal direction, this is due to the convective intensity is weaker at $\mathrm { { M a } = 1 0 }$ and the flow is a steady flow when the thermo-solutocapillary convection fully developed. Moreover, the distortion intensity of solute concentration contours is larger than that of the temperature contours, that is because the solute diffusivityis smaller than thermal diffusivity as $\mathrm { L e } = 1 0$

Due to the thermo-solutocapillary convection is driven by surface tension gradient, so the mechanism of flow structure and the free surface deformation mode can be interpreted by the surface tension distribution.Figure 4 gives the variation of non-dimensional surface tension along horizontal direction at ${ \sf R } _ { \sigma } = - 1 0$ .In the figure,the non-dimensional surface tension is monotone decreasing withthe increase of coordinate X.It is well known that the fluid flow driven by surface tension at free surface is from the smaller surface tension spot to the larger surface tension spot. Therefore,under the action of the monotone decreasing surface tension the flow at free surface is from the right end wall to the left wall, then leads to the fluid accumulates in the vicinity of the left end wall and the free surface bulges out.

![](images/29878d906b7fe0c566f9050ef5296b1dbd548c4f2005653bd3b1ce4ca0a02ca2.jpg)  
Fig.3Streamline, temperature,and solute concentration distribution at $R _ { \sigma } = - 1 0$ (a)streamlines,(b)temperature, and (c)solute concentration distribution)

![](images/413ac64ee0387d39357ca595eeb7e51047ffae374f15e471319610cd40fca977.jpg)  
Fig.4Variation of non-dimensional surface tension along horizontal direction at $\mathtt { R } _ { \sigma } = - 1 0$

Figure 5 gives free surface deformation under different thermal to solutal Marangoni number ratios as $- 1 0 \leq$ ${ \sf R } _ { \sigma } < - 1$ . These free surfaces bulge out near the left end wall,and bulge in near the right end wall. The free surfaces is almost asymmetric about the point ( $\mathrm { T } = 0 . 5$ ， ${ \mathrm { Y } } =$ O).With the increase of the thermal to solutal Marangoni number ratio the deformation intensity of free surface is decreased. The surface deformation is $\mathrm { O } ( 1 0 ^ { - 3 } )$ ，and its maximum value is $5 . 4 \times 1 0 ^ { - 3 }$ with $\mathrm { C a } = 0 . 1 \ \mathrm { M a } = 1 0$ and $\mathrm { L e } = 1 0$ .Figure 6 shows horizontal velocity distribution atfree surfaceunderdifferentthermaltosolutalMarangoni number ratios as $- 1 0 \leq \mathbf { R } _ { \sigma } < - 1$ .In the figure,the horizontal velocity at the free surface is minus,and with the thermal to solutal Marangoni number ratio increasing the free surface velocity is decreased.Thatis because the fluid flow is driven by thermocapillary convection,and thermocapillary convection intensity is strengthened as ${ \mathrm R } _ { \sigma }$ decreases.

![](images/4f9338a82daac9d369e3db96781585d60c466564e68af40182b49133dd188e8c.jpg)  
Fig.5Free surface deformation as $- 1 0 \leq \mathbf { R } _ { \sigma } < - 1$

![](images/9313106fccc155ccbb9b11efe8f5da9b515eb879a545905afe4b30434940d5ef.jpg)  
Fig.6Horizontal velocity distribution at free surface as $- 1 0 \leq$ $\scriptstyle \mathrm { \mathsf { R } } _ { \sigma } < - 1$

Next, the case of thermal to solutal Marangoni number ratio $\operatorname { R } _ { \sigma } = - 0 . 1$ is considered,which means the solutocapillary convection dominates the flow in the cavity. The streamlines,temperature and solute concentration contours distribution is shown in Figure 7. It can be seen that, the flow field has a clockwise rotating convective cell, thisis reverse to that of the case $\mathtt { R } _ { \sigma } = - 1 0$ ，thisis due to the driving direction of solutocapillary forces opposite to that of thermocapillary forces.Moreover, the free surface bulges out near the right end wall and bulges in near the left wall. The temperature and solute concentration contours are gradient distribution along the horizontal direction,and the distortion intensity of solute concentration contours is larger than that of the temperature contours.

Figure 8 gives the variation of non-dimensional surface tension along horizontal direction as $\mathrm { R } _ { \sigma } \mathrm { = } - 0 . 1$ . In the figure, the non-dimensional surface tension is monotone increasing with coordinate X.Therefore,under the action of the monotone increasing surface tension the flow at free surface is from the left end wall to the right end wall,so leads to the fluid accumulates near the right end wall and the free surface bulges out.

Figure 9 gives free surface deformation under different thermal to solutal Marangoni number ratios as $- 1 <$ $\mathrm { R } _ { \sigma } { \leq } - 0 . 1$ . These free surfaces bulge out near the right end wall,and bulge in near the left wall.The free surfaces is almost asymmetric about the point $\mathrm { T } = 0 . 5$ ， $\mathrm { Y } = 0 \mathrm { \ : \ : }$ ).The surface deformation is $\mathrm { O } ( 1 0 ^ { - 3 } )$ ,and its maximum value is $5 . 0 \times 1 0 ^ { - 3 }$ with $\mathrm { C a } = 0 . 1 \ \mathrm { M a } = 1 0$ and $\mathrm { L e } = 1 0$ . Moreover, with the increase of the thermal to solutal Marangoni number ratio the deformation intensity of free surface is increased.

![](images/29831aa51b50748db076f9afc351f3ab2430cb734cf0ae1d67bd4318e5fd418a.jpg)  
Fig.7Streamline,temperature and solute concentration distribution as $\operatorname { R } _ { \sigma } = - 0 . 1$ ((a) streamlines,(b) temperature, and (c) solute concentration distribution)

![](images/319cc8edad18afd9acbe17861bfb7fe0468a07da158631fc7746835e6aec7197.jpg)  
Fig.8Variation of non-dimensional surface tension along horizontal direction as ${ \mathrm { R } } _ { \sigma } = - 0 . 1$

![](images/8f912e43eb125d53e5816ad1574d6e05b24605ecf7c35e8343c88c111152a49b.jpg)  
Fig.9Free surface deformation as $- 1 < \mathrm { R } _ { \sigma } \underline { { < } } - 0 . 1$

Figure 1O shows horizontal velocity distribution at free surface under different thermal to solutal Marangoni number ratios as $- 1 < \mathsf { R } _ { \sigma } \underline { { < } } - 0 . 1$ . The horizontal velocity at the free surface is positive,and with the thermal to solutal Marangoni number ratio increasing the free surface velocity is increased.That is because the fluid flow is driven by solutocapillary convection,and its convective intensity is strengthened as $\mathtt { R } _ { \sigma }$ increases.

Finally, the case of thermal to solutal Marangoni numberratio ${ \sf R } _ { \sigma } = - 1$ is considered,this means that the opposing thermocapillary and solutocapillary forces are of equal magnitude at free surface as the flow fully developed, then the whole fluid system manifests as a balance system.Figure 11 gives the flow, temperature,and solute concentration fields distributions as $\boldsymbol { \mathrm { R } } _ { \sigma } = - 1$ . It can be seen that the flow field consists of two convective cells,where the left cell is anti-clockwise rotating and the right cell is clockwise rotating.That is because both convective cells are driven by thermocapillary forces and solutocapillary forces,respectively. Both the temperature and solute concentration contours are strictly gradient distribution along the horizontal direction due to the weaker convective intensity.

![](images/07ac0e05d8a5ed764143d2f3ef5eb4a3d08cd9b05fb3e6220cc8581393b2738e.jpg)  
Fig.10 Horizontal velocity distribution at free surface as $- 1 <$ $\mathrm { R } _ { \sigma } \underline { { < } } - 0 . 1$

![](images/df694f127111c7d30d32dbad675938b88dc3dc14aec08f53da910b8596f09f29.jpg)  
Fig.13Free surface deformation as $\boldsymbol { \mathrm { R } } _ { \sigma } = - 1$

![](images/f46d053ffbb8a87f2d15de79ffda1fc87159f57f38c71dae8141d64043ae6b4a.jpg)  
Fig.11 Streamline,temperature and solute concentration distribution at ${ \sf R } _ { \sigma } = - 1$ ((a)streamlines,(b)temperature, and (c)solute concentration distribution)

![](images/9d8a415328159ac9845db8445a9b76ef043d15710b3677ca671796997cc3f44c.jpg)  
Fig.14Horizontal velocity distribution at free surface as ${ \sf R } _ { \sigma } = - 1$

![](images/263a68d43695cbfbd90f7ef20993ead34e4a86392266b76be788643751882366.jpg)  
Fig.12Variation of surface tension along horizontal direction as ${ \sf R } _ { \sigma } = - 1$

# Conclusions

In this paper, thermo-solutocapillary convection in a rectangular cavitywithdynamic deformable free surface under microgravity condition is numerically simulated, and the effect of thermal to solutal Marangoni number ratio on the flow and free surface deformation is discussed.The following conclusions were drawn:

1）As the thermal to solutal Marangoni number ratio varies between-1O and -1, namely $- 1 0 \leq \mathbf { R } _ { \sigma } < - 1$ , the flow field exists one anti-clockwise rotating convective cell, which is driven by thermocapillary convection,and the free surface bulges out near the left end wall and bulges in near the right end wall.

2)As the thermal to solutal Marangoni number ratio variesbetween $^ { - 1 }$ and O,namely $- 1 < \mathbf { R } _ { \sigma } < 0$ ，theflow field exists one clockwise rotating convective cell, which is driven by solutocapillary convection, and the free surface bulges out near the right end wall and bulges in near the left end wall.

3）As the thermal to solutal Marangoni number ratio equals to $^ { - 1 }$ ，namely ${ \sf R } _ { \sigma } = - 1$ ，the flow field consists of one clockwise and one anti-clockwise rotating convective cells, they are driven by solutocapillary and thermocapillary convection,respectively. The free surface bulges in at the central point and bulges out near the left and right end walls.

# Acknowledgements

This work was supported by National Natural Science Foundation of China (Grant No.51206165) and National KeyR & D Program of China (Grant Number 2016YFB0601100).

# References

[1]T.L.Bergman,Numerical simulation of double-diffusive Marangoni convection,Phys.Fluids 29(1986） 2103- 2108.   
[2]Z.W. Chen,Y.S.Li, J.M. Zhan,Double-diffusive Marangoni convection in a rectangular cavity:onset of convection,Phys.Fluids 22 (2010) 034106.   
[3]Y.S.Li, Z.W. Chen, J.M. Zhan, Double-diffusive Marangoni convection in a rectangular cavity: transition to chaos,Int.J.HeatMass Transfer 53 (2010) 5223-5231.   
[4]J.M. Zhan, Z.W. Chen, Y.S.Li,Y.H.Nie,Three-dimensional double-diffusive Marangoni convection in a cubic cavity with horizontal temperature and concentration gradients,Physical Review E 82 (2010) 066305.   
[5]C.F. Chen, C.L. Chan, Stability of buoyancy and surface tension driven convection ina horizontal double-diffusive fluid layer,Int.J.Heat Mass Transfer 53(2010) 1563- 1569.   
[6]Y.R.Li, Z.X. Gong,C.M.Wu,S.Y. Wu, Steady thermal-solutal capillary convection in a shallow annular pool with the radial temperature and concentration gradients, Sci. China Tech. Sci.55 (2012) 2176-2183.   
[7]Y.R. Li, Y.L. Zhou, J.W. Tang, Z.X. Gong,Two-Dimensional Numerical Simulation for Flow Pattern Transition of Thermal-Solutal Capillary Convection in an Annular Pool,Microgravity Sci. Technol.(2013) 25:225-230. [8]B.C. Sim,W.S.Kim,A. Zebib,Dynamic free-surface deformations in axisymmetric liquid bridges,Advances in Space Research 34 (2004) 1627-1634.   
[9]J.N.Koster,Early Mission Report on the four ESA facilities:Biorack;Bubble,Drop and Particle Unit; Critical Point Facility and Advanced Protein Crystallization Facility flown on the IML-2 spacelab mission. Microgr. News from ESA7 (1994) 2-7.   
[10]M. Mundrane,J. Xu,A. Zebib, Thermocapillary convection in a rectangular cavity with a deformable interface, Adv. Space Res.16 (1995)41-53.   
[11]M.Z. Saghir, R.Abbaschian, R. Raman, Numerical analysis of thermocapillary convection in axisymmetric liquid encapsulated In Bi, J. Crys. Grow.169 (1996) 110-117.   
[12]M. Hamed, J.M. Floryan, Marangoni convection. Part 1. A cavity with differentially heated sidewalls,J. Fluid Mech.405 (2000) 79-110.   
[13]N.R.Gupta, H.H. Hossein,A. Borhan, Thermocapillary flow in double-layer fluid structures:An effective singlelayer model, J. Colloid Interface Sci. 293(2006) 158- 171.   
[14]R.Q.Liang, S.Y. Ji, Z.Li, Thermocapillary Convection in Floating Zone with Axial Magnetic Fields, Microgravity Sci. Technol. 25 (2014) 285-293.   
[15]X.M. Zhou, X.L.Huai, Thermo-solutocapillary convection in open rectangular cavity with dynamic free surface, ASME Journal of Heat Transfer,2015,137(8)   
[16]J.U.Brackbill,D.B.Kothe,C.Zemach,A continuum method for modeling surface tension. J. Comput. Phys. 100(2) (1992) 335-354.   
[17]M. Sussman,P. Smereka, S. Osher, A level set approach for computing solutions to incompressible two-phase flow, J. Comput.Phys.114 (1994) 146-159.   
[18]R.Q. Liang, Z.Q. Liao, W. Jiang, G.D. Duan, J.Y. Shi, P. Liu, Numerical simulation of water droplets falling near a wall: existence of wall repulsion，Microgravity Sci. Technol.23 (2011) 59-65.   
[19]M.J. Ni, S. Komori, M. Abdou, A variable-density projection method for interfacial flows,Numerical Heat Tran. B.44 (2003) 553-574.   
[20] X.M. Zhou, H.L. Huang, Numerical simulation of steady thermocapillary convection in a two-layer system using level set method,Microgravity Sci. Technol. 22 (2010) 223-232.