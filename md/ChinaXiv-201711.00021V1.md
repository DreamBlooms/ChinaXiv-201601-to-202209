# Annular Supersonic Swirling Flows with Heterogeneous Condensation

Yusuke FUKUSHIMA1, Shigeru MATSUO², Norimasa SHIOMI’ and Toshiaki SETOGUCHI4

1. Graduate School of Science & Enginering,Saga University,1,Honjo-machi,Saga-shi,Saga 840-8502,Japan   
2.Department ofAdvanced Technology Fusion,Saga University,1,Honjo-machi, Saga-shi,Saga 840-8502,Japan   
3.Department of Mechanical Engineering, Saga University,1,Honjo-machi,Saga-shi,Saga 840-8502,Japan   
4. Institute of Ocean Energy, Saga University,1, Honjo-machi, Saga-shi, Saga 840-8502, Japan

In recent years,separating and extracting technologies of condensate gas have been developed by combining a swirl flow with non-equilibrium condensation phenomena of condensate gas generated in a supersonic flow.The technology can reduce the size of the device and does notuse chemicals.However,there are many unresolved problems for performance of the separation,extraction and operating principle.Therefore it is necessry to research further in order to improve the performance of the equipment.In the present study,the numerical study was carried outto clarify the effect of the heterogeneous condensation on the characteristics of the swirling flow field in a supersonic anular nozzle,and the differences between homogeneous condensation and heterogeneous condensation in the flow field.As the results,it is found that the condensation flow with aswirl afects the position of sonic line, the generating position of condensate and the radial distribution ratio of liquid phase.

# Keywords:compressble flow,heterogeneous condensation,homogeneouscondensation,supersonic nozzle,annular swirling flow, simulation

# Introduction

Condensation phenomenon of moist air or steam in a high speed flow field is,in general,induced through the non-equilibrium condensation process [1]. In this process condensation nuclei are generated by collision and aggregation of vapour molecules. The condensation of the vapour, so called homogeneous condensation, takes place on the nuclei. On the other hand,in heterogeneous condensation [2], the condensation of the vapour takes place on foreign nuclei :smoke and vapor from fires and various industries,dust from land surfaces,salt from ocean and particulate products from chemical reaction.Further, effects of foreign nuclei on the high speed flow field have not been clarified significantly.

Recently,we are faced with solution of environmental problems and the sophistication of the energy structure on a global scale.Natural gas of lower $\mathrm { C O } _ { 2 }$ emissions is important as an alternative energy of petroleum and coal [3].The separation and extraction of condensable gas and impurities contained in the natural gas are important for natural gas processing. Separating and extracting technologies of condensable gas have been developed by using a swirling flow in a supersonic annular nozzle [1,4. 5].The technology can reduce the size of the device and it has an advantage that does not use chemicals.However. there are many unresolved problems for performance of the separation, extraction and operating principle. There.

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>Q</td><td>Conservation mass term</td><td colspan="2">Greek symbols</td></tr><tr><td>E,F,G</td><td>Numerical flux</td><td>a</td><td>Closure coefficients in the specific dissipation-rate equation</td></tr><tr><td>Ev,Fv, Gv</td><td>Source term of viscosity</td><td></td><td>Displacement thickness, (m)</td></tr><tr><td>I</td><td>Source term of turbulence</td><td></td><td>Relative humidity, (%)</td></tr><tr><td>S</td><td>Source term of condensation</td><td>p</td><td>Density, (kg/m³)</td></tr><tr><td>D</td><td>Diameter, (m)</td><td>V</td><td>Kinematic viscosity, (m²/s)</td></tr><tr><td>g</td><td>Condensate mass fraction</td><td>@</td><td>Specific dissipation rate,(1/s)</td></tr><tr><td>I</td><td>Nucleation rate per unit time and volume,(1/(s:m))</td><td colspan="2">Subscripts</td></tr><tr><td>k</td><td>Specific turbulence kinetic energy, (J/m³)</td><td>0</td><td>Stagnation point</td></tr><tr><td>L</td><td>Latent heat, (J/kg)</td><td>V</td><td>Vapor</td></tr><tr><td>n</td><td>Number density, (1/kg)</td><td>a</td><td>Dry air</td></tr><tr><td>nhet</td><td>Number of embryos per unit mass, (kg-1)</td><td>e</td><td>Experiment</td></tr><tr><td>p</td><td>Pressure, (Pa)</td><td>het</td><td>Heterogeneous</td></tr><tr><td>Re</td><td>Reynolds number</td><td>hom</td><td>Homogeneous</td></tr><tr><td>r</td><td>Radius, (m)</td><td>in</td><td>Inner</td></tr><tr><td>Rp</td><td>Radius of a solid particle, (m)</td><td></td><td>Liquid</td></tr><tr><td>Swin</td><td>Swirl number</td><td>out</td><td>Outer</td></tr><tr><td>T</td><td>Temperature, (K)</td><td>8</td><td>Infinite flat plane</td></tr><tr><td>u, v, W</td><td>Velocity components,(m/s)</td><td>*</td><td>Dimensionless variable</td></tr><tr><td>x,y, %</td><td>Cartesian coordinates, (m)</td><td></td><td></td></tr></table></body></html>

fore it is necessary to research further in order to improve the performance of the equipment In the previous research，by using a homogeneous condensation pheno menon of moist air occurred in the supersonic flow in the annular nozzle with a swirl, the effect of the nozzle inlet shape on spatial distribution of condensate was investigated numerically, and the possibilities of the condensable gas separation and reduction of device size was shown qualitatively [6]. However, the effect of heterogeneous condensation on the supersonic annular flow with a swirl has not been taken into account in the study.

In the present study, the numerical investigation is carried out to clarify the effect of the heterogeneous condensation on the characteristics of the swirling flow field in a supersonic annular nozzle and the differences between homogeneous condensation and heterogeneous condensation in the flow field.As the results,it is found that the condensation flow with a swirl affects the position of sonic line, the generating position of condensate and the radial distribution ratio of liquid phase.

# Experimental Apparatus and Method

In order to validate the present computation, an experimental work was conducted for homogeneous condensation phenomenon.Figure 1 shows a schematic diagram of experimental apparatus. A supersonic indraft wind tunnel where the moist air at atmospheric pressure is drawn into a vacuum tank, was used in the present experiment.

Figure 2 shows details of test section.An annular nozzle is composed of an inner body and an outer nozzle. The outer nozzle is coaxial with the inner body.Throat diameter of outer nozzle in case of no inner body is $D _ { \mathrm { e } } =$ $3 0 ~ \mathrm { m m }$ and design Mach number at exit in the annular nozzle is 3.0. The pressure measurements were conducted by a pressure transducer (Kulite XT-190) mounted on the pressure holes (diameter $: 1 . 0 \mathrm { m m } \rangle$ along the outer wall.The supersonic steady flow lasting about 30 se conds was obtained in the test section.The stagnation pressure $p _ { 0 }$ and the stagnation temperature $T _ { 0 }$ of moist air in the reservoir were set at $1 0 1 . 2 \mathrm { k P a }$ and $2 9 3 \mathrm { ~ K ~ }$ ,respectively. The values of relative humidity $\phi _ { 0 }$ are $2 5 \%$ and $70 \%$ =

![](images/fcd86e74600e58cd82b6a7906483d4f1336ecc2e38c89c4645013e9b4e1a0225.jpg)  
Fig.1Experimental apparatus

![](images/7008bae9dfc5f0866c4be9235e2e54a20bb398f2d89000484b32d3acc27bcc20.jpg)  
Fig.2Supersonic nozzle with inner body $( D _ { \mathrm { e } } = 3 0 \mathrm { m m } )$

Assumptions in the present calculation are as follows ; both velocity slip and temperature difference do not exist among condensate droplets,solid particles and inert gas mixture,and the effect of the condensate droplets and solid particles on pressure is neglected.All particles are assumed to have a smooth and spherical shape,and all condensation nuclei are assumed to be chemically inert and insoluble in water vapor.

The governing equations used in the present study are three dimensional compressible Navier-Stokes equations combined with equations of continuity, energy, turbulent kinetic energy, specific dissipation rate,conservation of mass of the liquid phase and conservation of the number density of droplets with homogeneous and heterogeneous nucleations.To estimate the eddy viscosity, $k { - } \omega$ model was employed in computations [7]. Non-dimensional governing equations are written in the three-dimensional Cartesian coordinate system $( x , y , z )$ as follows :

$$
\frac { \partial \pmb { Q } } { \partial t } + \frac { \partial E } { \partial x } + \frac { \partial F } { \partial y } + \frac { \partial \mathbf { G } } { \partial z }
$$

$$
= \frac { 1 } { R e } \left( \frac { \hat { \sigma } E _ { \pmb { \nu } } } { \hat { \sigma } x } + \frac { \hat { \sigma } F _ { \pmb { \nu } } } { \hat { \sigma } y } + \frac { \hat { \sigma } { \bf G } _ { \pmb { \nu } } } { \hat { \sigma } z } \right) + I + S
$$

In Eq.(1), $\varrho$ is conservative vector, $E$ and $F , G$ are inviscid flux vector and $\scriptstyle { E _ { \nu } }$ and $F _ { \nu } , G _ { \nu }$ are viscous flux vectors. $\boldsymbol { { \cal I } }$ and $s$ are the source terms corresponding to turbulence and condensation, respectively [8].

Total flow rate of liquid phase $g$ [8] is written as

$$
g = g _ { \mathrm { h o m } } + g _ { \mathrm { h e t } }
$$

where $g _ { \mathrm { h o m } }$ and $g _ { \mathrm { h e t } }$ are condensate mass fractions generated by homogeneous and heterogeneous condensations,respectively.Both of the condensate mass fractions $g$ are expressed as a rate equation, based on the following equation [9].

$$
\begin{array} { l } { \displaystyle \frac { d g } { d t } = \frac { 4 \pi } { 3 } \cdot \rho _ { l } \cdot r _ { c } ( t ) ^ { 3 } \cdot \frac { I ( t ) } { \rho _ { m } ( t ) } } \\ { \displaystyle + \int _ { - \infty } ^ { t } 4 \pi \cdot \rho _ { l } \cdot \frac { I ( \tau ) } { \rho _ { m } ( \tau ) } \cdot \frac { \hat { o } r ( t , \tau ) } { \hat { o } t } \cdot r ( t , \tau ) ^ { 2 } \cdot d \tau } \end{array}
$$

The density of liquid phase $\rho _ { l } ( T )$ is also a function of temperature [1O] and the density of gas mixture $\rho _ { m }$ is calculated by the sum of density of vapor $\rho _ { \nu }$ and dry air $\rho _ { a }$ ： $r$ and $r _ { \mathrm { c } }$ are averaged and critical droplet radius, respectively. $I$ is nucleation rate per unit time and volume.

Heterogeneous nucleation process consists of four nucleation stages [8];I. Generation of embryo，II. Growth of embryo, III. Formation of liquid film and IV. Growth of liquid film. In the first stage,embryos are generated on the surface of a solid particle.In the second stage,embryos on the surface of a solid particle grow up and new embryos are generated on the particle.In the third stage,a liquid film is formed on the whole surface of a solid particle and the solid particle covered by the liquid film can be assumed a nucleus. In the fourth stage, the liquid film grows up.

There are two models for heterogeneous nucleation process [8].For model1, four nucleation stages fromI to IV are considered for nucleation process.For model 2, only the fourth stage (IV) of nucleation process is used. This model is assumed that nucleation stages from I to III proceed in an infinitesimal time. In the present study, model 2 is used as a heterogeneous condensation model because the difference between results obtained by both models is very small. Equations for heterogeneous condensation in the present simulation were given based on Refs.[8,11,12].

Equations were discretized in space using a cellcentered finite volume formulation with a quadrilateral structured cell system and in time using the Euler implicit method [13]. Furthermore,a third-order accurate MUSCL TVD schemes based on Roe's approximate Riemann solver [14] were applied to the inviscid fluxes and the viscous fluxes were evaluated by second-order accurate central differences method.Generation terms associated with turbulence and condensation were evaluated by first-order accurate central differences method. Unfactored implicit equations derived with no approximate factorization were solved by a point Gauss-Seidel relaxation method [15].

# Computational Conditions

Figure 3 shows nozzle geometry used in the present study.An annular nozzle used in this calculation is composed of an inner body and an outer nozzle.The outer nozzle is coaxial with the inner body.Throat diameter of the outer nozzle in case without the inner body is $D = 1 0$ mm which is the same as one at the nozzle exit. The nozzle opening angle $a$ is $4 ^ { \circ }$ .Design Mach number for the nozzle is 2.24.

Figures 4 (a), (b) and (c) show a computational domain of the supersonic annular flow field, boundary condition and measuring line for physical properties,respectively. The number of cells is $2 1 1 \times 8 1 \times 3 1$ .Theadiabatic no-slip wall was used as boundary condition.Inflow condition was fixed at initial condition.Outflow condition is a zero-order extrapolation.Periodic boundary conditions were imposed for conservative variables. Condensate mass fraction $g$ was set at $g = 0$ on the wall.

Table 1 shows calculation conditions used in the present calculation. Stagnation pressure $p _ { 0 }$ and temperature $T _ { 0 }$ at stagnation point are $1 0 2 ~ \mathrm { k P a }$ and $2 9 3 \mathrm { ~ K ~ }$ respectively. The initial degree of relative humidity $\phi _ { 0 }$ of moist air is $80 \%$ . The concentration of the solid particles per unit volume $n _ { \mathrm { h e t } }$ was changed in the range from $1 . 0 \times$

![](images/0887b74b026eaf3b69d71857c02f69349372708174541d02e428107088994eff.jpg)  
Fig.3Nozzle geometry $( D = 1 0 ~ \mathrm { m m } )$

![](images/f82260bbd4932af1d9ab9ebd5ba1d46b0110f0199d2e4265008d7feda991da52.jpg)  
Inlet:Fixedat initial condition

![](images/5b58ec4119b5b870a39b11ade74bd87d0af375b7215437ca000f4547c8a97e0d.jpg)  
Fig.4Computational domain and boundary conditions

Table1 Calculation conditions   

<html><body><table><tr><td>po[kPa]</td><td>To[K]</td><td>[%]</td><td>nhet,0[m3]</td><td>Rp[m]</td><td>Sw.in[-]</td></tr><tr><td></td><td></td><td>0</td><td></td><td></td><td>0.0</td></tr><tr><td></td><td></td><td></td><td>Homogeneous</td><td></td><td>2.0</td></tr><tr><td></td><td></td><td></td><td>condensation</td><td></td><td>0.0</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>2.0</td></tr><tr><td></td><td></td><td></td><td>1.0×10²</td><td>1.0×10-8</td><td>0.0 2.0</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>1.0×10-5</td><td>0.0</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>2.0</td></tr><tr><td></td><td></td><td></td><td></td><td>1.0×10-8</td><td>0.0</td></tr><tr><td></td><td></td><td></td><td>1.0×104</td><td></td><td>2.0</td></tr><tr><td>102</td><td></td><td></td><td></td><td>1.0×10-5</td><td>0.0</td></tr><tr><td></td><td>293</td><td>80</td><td></td><td></td><td>2.0</td></tr><tr><td></td><td></td><td></td><td>1.0×108</td><td>1.0×10-8</td><td>0.0</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>2.0</td></tr><tr><td></td><td></td><td></td><td></td><td>1.0×10-5</td><td>0.0</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>2.0</td></tr><tr><td></td><td></td><td></td><td></td><td>1.0×10-8</td><td>0.0</td></tr><tr><td></td><td></td><td></td><td>1.0×1010</td><td></td><td>2.0</td></tr><tr><td></td><td></td><td></td><td></td><td>1.0×10-5</td><td>0.0</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td>2.0</td></tr></table></body></html>

$1 0 ^ { 2 }$ to $1 . 0 \times 1 0 ^ { 1 0 } ~ 1 / \mathrm { m } ^ { 3 }$ . The radius of the solid particle $R _ { \mathrm { p } }$ was set to $1 . 0 \times 1 0 ^ { - 8 }$ or $1 . 0 \times 1 0 ^ { - 5 } \mathrm { ~ m ~ }$ and swirl number $S _ { \mathrm { w , i n } }$ at the inlet was set to O or 2.0.

# Results and Discussions

Figure 5 shows static pressure distributions,which are obtained on the basis of the nozzle geometry in Fig.2,on the outer wall for dry air ( $\phi _ { 0 } = 2 5 ~ \% )$ and moist air $( \phi _ { 0 } =$ $70 \%$ ） in case of no swirl. In this figure,comparison between the experimental and simulated static pressure distributions is shown and it is found that simulated results agree well with experimental results qualitatively.

Figure 6 shows contour maps of condensate mass fraction $g$ and sonic lines for homogeneous.As seen from this figure, positions of sonic line and onset of condensa tion move upstream in case of swirling flow $( S _ { \mathrm { w , i n } } { = } 2 . 0 )$ and this tendency appears particularly in the range close to the inner side.

Contour maps of condensate mass fraction $g$ and sonic lines for heterogeneous condensation are shown in Figs. 7(a) $( n _ { \mathrm { h e t , 0 } } { = } 1 . 0 { \stackrel { - } { \times } } 1 0 ^ { 1 0 } \mathrm { m } ^ { - 3 }$ $R _ { \mathfrak { p } } = 1 . 0 { \times } 1 0 ^ { - 8 } \mathrm { m } )$ and 7(b) $( n _ { \mathrm { h e t , 0 } }$ $= 1 . 0 { \times } 1 0 ^ { 1 0 } ~ \mathrm { m } ^ { - 3 }$ ， $R _ { \mathrm { p } } = 1 . 0 { \times } 1 0 ^ { - 5 } \ \mathrm { m } )$ . In each figure, simulated results for $S _ { \mathrm { w , i n } } { = } 0$ and 2.0 are shown including the position of $g = 1 . 0 \times 1 0 ^ { - 1 3 }$ . It is found from these figures that positions of sonic line move upstream in case of swirling flow $( S _ { \mathrm { w , i n } } { = } 2 . 0 )$ and this tendency is similar to that in case of homogeneous condensation in Fig.6.Fur thermore,positions of the occurrence of heterogeneous condensation move upstream largely compared to those for homogeneous condensation. Flow characteristics in other combination of $n _ { \mathrm { h e t , 0 } }$ and $R _ { \mathfrak { p } }$ showed a similar tendency to that of Fig.7.

![](images/888dcf278c3a074a74a435fe4f2929affc1436e49e97bd440fb1fc3094cbdbd0.jpg)  
Fig.5Distributions of static pressure on the outer wall

![](images/4dd277af9117978d7643d4e664fcc03fb0c8b86cd65bda2b9affa4330fdc9369.jpg)  
Fig.6Contour maps of $g$ and sonic lines (Homogeneous condensation)

![](images/57a17ded5859424407b568a5322e474e3484a8ae13a60e236202f6ea7d8ed098.jpg)  
Fig.7Contour maps of $g$ and sonic lines $( n _ { \mathrm { h e t , 0 } } { = } 1 . 0 { \times } 1 0 ^ { 1 0 } \mathrm { m } ^ { - 3 } )$ （20

Figure 8 shows distributions of static pressure $p / p _ { 0 }$ and nucleation rate $I _ { \mathrm { h o m } }$ along line A-A' in Fig.4(c) for $R _ { \mathfrak { p } }$ $= 1 . 0 { \times } 1 0 ^ { - 8 } \mathrm { m }$ and $1 . 0 { \times } 1 0 ^ { - 5 } \mathrm { ~ m } ( n _ { \mathrm { h e t , 0 } } { = } 1 . 0 { \times } 1 0 ^ { 1 0 } \mathrm { m } ^ { - 3 }$ 1 $S _ { \mathrm { w , i n } } { = } 0$ and 2.O). In this figure,results for dry air and homoge neous condensation are also shown forreference.As seen from this figure,static pressures for swirling flow become small compared with those of no swirl and the position of the maximum of $I _ { \mathrm { h o m } }$ in case of $S _ { \mathrm { w , i n } } { = } 2 . 0$ islocated upstream of that for $S _ { \mathrm { w , i n } } { = } 0$ . Further, the positions that pressure begins to deviate from an isentrope (dry air) for heterogeneous condensation are almost the same as one of homogeneous condensation.These distributions in other combination of $n _ { \mathrm { h e t , 0 } }$ and $R _ { \mathfrak { p } }$ showed a similar tendency to that of Fig.8.

Effect of the radius of the solid particle $R _ { \mathfrak { p } }$ on distributions of condensate mass fraction $g _ { \mathrm { h o m } } , \ g _ { \mathrm { h e t } }$ and $g \ ( =$ $g _ { \mathrm { h o m } } \mathrm { + } g _ { \mathrm { h e t } } )$ along line A-A' in Fig.4(c) is shown in Fig.9 for cases of $S _ { \mathrm { w , i n } } { = } 0$ and 2.0 $( n _ { \mathrm { h e t , 0 } } = 1 . 0 { \times } 1 0 ^ { 1 0 } \ \mathrm { m } ^ { - 3 } )$ . It is found from this figure that the occurrence position of heterogeneous condensation is located upstream compared with that of homogeneous condensation and $g$ for $S _ { \mathrm { w , i n } } { = } 0$ or 2.0 is almost the same as one of homogeneous condensation regardless of $R _ { \mathfrak { p } }$ at nozzle exit $( x / D = 3 . 0 )$ ： Distributions of $g$ in other combination of $n _ { \mathrm { h e t , 0 } }$ and $R _ { \mathfrak { p } }$ showed a similar tendency to that ofFig.9.

![](images/564c41087cd15e3c2ea87af2800ed5183c0b71d35a207c0da9e55560cdc6f0f0.jpg)  
Fig.8Distributions of static pressure and nucleation rate （ $( n _ { \mathrm { h e t , 0 } } { = } 1 . 0 { \times } 1 0 ^ { 1 0 } \mathrm { m } ^ { - 3 } )$ （20

$$
{ \begin{array} { r l } { { - \ -- } } & { : S _ { \mathrm { w , i n } } = 0 , R _ { \mathrm { p } } = 1 . 0 { \times } 1 0 ^ { - 8 } \mathrm { m } } \\ { \quad \mathrm { -- } } & { : S _ { \mathrm { w , i n } } = 0 , R _ { \mathrm { p } } = 1 . 0 { \times } 1 0 ^ { - 5 } \mathrm { m } } \end{array} }
$$

![](images/e0fa59559adb0ffacb0fb6a6b7c7157e96201fbcaa1c8d656cf7a7537d8e8210.jpg)  
Fig.9Distributions of condensate mass fraction $( n _ { \mathrm { h e t , 0 } } = 1 . 0 \times$ $1 0 ^ { 1 0 } \mathrm { m } ^ { - 3 } )$ （20

In order to investigate the amount of condensate in the range of the outer wall side in the annular nozzle,a new function defined by the following equation was introduced.

$$
G = \int _ { y = r _ { \mathrm { i } } } ^ { y _ { \mathrm { o u t e r } } } 2 \pi g \rho u r \mathrm { d } r \bigg / \int _ { y _ { \mathrm { i n n e r } } } ^ { y _ { \mathrm { o u t e r } } } 2 \pi g \rho u r \mathrm { d } r
$$

where $G$ (radial distribution ratio of liquid phase) shows ratio of integrated value of mass flow rate of the liquid phase from $y { = } r _ { \mathrm { i } }$ (position of the radius corresponding to half of annular area) to outer wall to integrated value of mass flow rate of the liquid phase from inner wall to outer wall in the cross section in the annular nozzle channel perpendicular to the $x$ -axis.

Distributions of $G$ along $x$ -axisfor heterogeneous condensation are shown in Figs. 10(a) $( n _ { \mathrm { h e t } , 0 } ~ \mathrm { = } \mathrm { \bar { 1 } } . 0 { \times } 1 0 ^ { 2 }$ $\mathbf { m } ^ { - 3 } )$ and 10(b) $( n _ { \mathrm { h e t , 0 } } = 1 . 0 { \times } 1 0 ^ { 1 0 } \ \mathrm { m } ^ { - 3 } )$ . Results for homogeneous condensation are also illustrated for reference.In both figures,simulated results for $S _ { \mathrm { w , i n } } { = } 0$ and 2.0 are shown in cases of $R _ { \mathrm { p } } = 1 . 0 { \times } 1 0 ^ { - 8 } \ \mathrm { m }$ and $1 . 0 { \times } 1 0 ^ { - 5 } \mathrm { ~ m }$ .In downstream of the annular nozzle, $G$ in case with swirl for each figure becomes large in comparison with cases of no swirling flows. This means that the condensate gathers toward the outer wall side compared to cases of no swirling flows.Further, $G$ for $S _ { \mathrm { w , i n } } { = } 0$ or 2.0 is almost the same as one of homogeneous condensation at nozzle exit $( x / D = 3 . 0 )$ regardlessof value of $R _ { \mathfrak { p } }$ .Distributions of $G$ in other combination of $n _ { \mathrm { h e t , 0 } }$ and $R _ { \mathrm { p } }$ showed a similar

tendencyto thatof Fig.10.

Figure 11 shows distributions of displacement thickness of boundary layer $\delta ^ { * }$ on the inner and outer walls $( n _ { \mathrm { h e t , 0 } } { = } 1 . 0 { \times } 1 0 ^ { 1 0 } \mathrm { \overline { { m } } } ^ { - 3 } )$ .From this figure, it is found that the displacement thickness in the case with swirl becomes thick in the inner wall side and thin in the outer wall side in comparison with the case of no swirl.Further, $\delta ^ { * }$ for $S _ { \mathrm { w , i n } } { = } 0$ or 2.0 is almost the same as one of homogeneous condensation at nozzle exit $( x / D = 3 . 0 )$ regardlessof value of $R _ { \mathrm { p } }$ .Distributions of $\delta ^ { * }$ in other combination of $n _ { \mathrm { h e t , 0 } }$ and $R _ { \mathfrak { p } }$ showed a similar tendency to that of Fig.11.

Figure 12 shows distributions of kinematic viscosity $\nu$ in cross-section at $x / D = 3$ $( n _ { \mathrm { h e t , 0 } } { = } 1 . 0 { \times } 1 0 ^ { 1 0 } ~ \mathrm { m } ^ { - 3 } )$ . As seen from this figure, $\nu$ for $S _ { \mathrm { w , i n } } { = } 0$ or 2.0 is almost the same as one of homogeneous condensation regardless of $R _ { \mathfrak { p } }$ at nozzle exit and the kinematic viscosity becomes large on the inner wall side in case with swirl compared with that of no swirl. As a result, it is considered that displacement thickness becomes thin at the outer wall side and thick at the inner wall side as shown in Fig.11.Distributions of $\nu$ in other combination of $n _ { \mathrm { h e t , 0 } }$ and $R _ { \mathfrak { p } }$ showed a similar tendency to that ofFig.12.

![](images/c8a1649437b2ca131487ee2fa014e7b8f25cdbbe57940fe4244c0dcd421fe1fb.jpg)  
Fig.10Distributions of $G$

![](images/4ac53f196e1d131cdc0a31a02c00a49950240d7c6721d8623d2c824001aa7be9.jpg)  
Fig.11Distributions of displacement thickness $( n _ { \mathrm { h e t } , 0 } = 1 . 0 \times$ $1 0 ^ { 1 0 } \mathrm { m } ^ { - 3 } )$ （20

![](images/4905bde86b007619b5e78503dd8bcde4df18669e330f03ce465b96f41e11e6ff.jpg)  
Fig.12Distributions of kinematic viscosity $( x / D { = } 3$ ， $n _ { \mathrm { h e t , 0 } } =$ （204 $1 . 0 \times 1 0 ^ { 1 0 } \mathrm { m } ^ { - 3 } ,$

As is evident from Figs.8 to 12,the change in the physical properties due to heterogeneous condensation is similar to that due to homogeneous condensation.As a result,it was found in the present calculation condition that homogeneous condensation can predict flow properties by heterogeneous condensation to some extent.

# Conclusions

A computational study has been made to investigate the effect of the heterogeneous condensation on the characteristics of the swirling flow field in a supersonic annular nozzle and the differences between homogeneous condensation and heterogeneous condensation in the flow field. The results obtained are as follows:

(1) The generating position of condensate in the annular nozzle in case of heterogeneous condensation moved upstream compared with the case of homogeneous condensation.

(2) The position that pressure begins to deviate from anisentrope (dry air） for heterogeneous condensation was almost the same as one of homogeneous condensation.

(3) Condensate mass fraction and radial distribution ratio of liquid phase for $S _ { \mathrm { w , i n } } = 0$ or 2.0 is almost the same as one of homogeneous condensation regardless of the radius of the solid particle downstream of the nozzle.

(4) The displacement thickness in the case with swirl became thick in the inner wall side and thin in the outer wall side in comparison with the case of no swirl and $\delta ^ { * }$ for $S _ { \mathrm { w , i n } } = 0$ or 2.0 is almost the same as one of homogeneous condensation regardless of the radius of the solid particle downstream of the nozzle.

(5) The kinematic viscosity became large on the inner wall side in case with swirl compared with that of no swirl and kinematic viscosity for $S _ { \mathrm { w , i n } } = 0$ or 2.0 was almost the same as one of homogeneous condensation regardless of the radius of the solid particle downstream of the nozzle.

(6) In the present calculation condition,homogeneous condensation could predict flow properties by heterogeneous condensation to some extent.

# Acknowledgement

This work was supported by JSPS KAKENHI Grant number 26420116.

# References

[1]Wegener, P.P.,Mach,L.M.:Condensation in supersonic and hypersonic wind tunnels,Advances in applied mechanics,Vol.5,pp.307-447,(1958).   
[2]Kotake, S., Glass,I. I.: Condensation of Water Vapour on Heterogeneous Nucleation in a Shock Tube,UTIAS Report, No.207,(1976).   
[3]Kaneko,H.:Liquefied petroleum gas supply and demand perspective and LP gas synthesis technology development,Journal of Japan Institute of Energy,Vol.86,No.4, pp.232-237,(2007).   
[4]Prast,B.,Lammers,B.,Betting,M.:CFD for supersonic gas processing,The 5th international conference on CFD in the process industries,Melbourne,Australia,pp.1-6, (2006).   
[5]Wen, C., Cao, X., Yang, Y., Zhang, J.: Evaluation of natural gas dehydration in supersonic swirling separators applying the discrete particle method,Advanced powder technology, Vol.23 No.2,pp.228-233,(2012).   
[6]Fukushima,Y.,Matsuo,S.,Setoguchi，T.，Shiomi,N., Hashimoto,T.,Kim,H.D.and Yu,S.:Effect of Nozzle Inlet Shape on Annular Swirling Flow with Non-Equilibrium Condensation, Journal of Thermal Science,Vol.24, No.4,pp.344-349,(2015).   
[7]Wilcox, D.C.: Formulation of the $k$ -@ turbulence model revisited,AIAA Journal,Vol.46,No.11，pp.2823-2838, (2008).   
[8]Heiler, M.:, Instationäre Phänomene in homogen/heterogen kondensierenden Diüsen- und Turbinenstromungen,Dissertation,FakultätfirMaschinenbau,Universität Karlsruhe (TH), Germany, (1999).   
[9]Sislian, J.P.: Condensation of Water Vapor with or without a Carrier Gas ina Shock Tube,UTIAS Report,No. 201, (1975).   
[10]Adam, S.: Numerische und Experimentelle Untersuchung Instationärer Duisenstromungen mit Energiezufuhr durch Homogene Kondensation,Dissertation,Fakultät fur Maschinenbau,UniversitatKarlsruhe(TH)，Germany, (1999).   
[11] Tanaka,M.，Matsuo,S.， Setoguchi,T.and Kim,H.D.: Effect of Heterogeneous Condensation on the Transonic Flow Fields on a Bump,Journal of Thermal Science, Vol.14,No.1, pp.34-40,(2005).   
[12]Tanaka, M.,Matsuo,S., Setoguchi, T.and Kim, H.D., Yu, S.:Effect of Heterogeneous Condensation on the Flow Fields ina Ludwieg Tube,Procs.of the 7th Int. Symposium on Experimental and Computational Aerothermodynamics of Internal Flows,Tokyo，Vol.2，pp.395-400, (2005).   
[13]Furukawa,M.,Nakano,T.，Inoue,M.:Unsteady Navier-Stokes simulation of transonic cascade flow using an unfactored implicit upwind relaxation scheme with inner iterations,Transactions of the ASME,Journal of Turbomachinery,Vol.114,No.3,pp.599-606,(1992).   
[14]Roe,P.L.: Approximate Riemann solvers, parameter vectors,and difference schemes,Journal of Computational Physics,Vol.43,pp.357-372,(1981).   
[15]Chakravarthy,S.P.:Relaxation methods for unfactored implicit upwind schemes，AIAA paper 84-0165,Reno Nevada,USA(1984).