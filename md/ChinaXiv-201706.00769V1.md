# Effects of the Aspect Ratio on the Optimal Tilting Angle for Maximum Convection Heat Transfer across Air-filled Rectangular Enclosures Differentially Heated at Sides

C. Cianfrini, M. Corcione, E. Habib,A. Quintino

DIAEE- Sezione Fisica Tecnica,Sapienza Universita di Roma via Eudossana,18-O0184 Rome, Italy $\copyright$ Science Press and Institute of Engineering Thermophysics,CASand Springer-Verlag Berlin Heidelberg 2017

Naturalconvection inair-filled rectangular cavities inclined with respect to gravity,so thatthe heated wall is facing upwards,is studied numericallyunder the assumption of two-dimensional laminar flow.A computational code based on the SIMPLE-C algorithm is used for the solution of the system of the mass,momentum and energy transfer governing equations.Simulations are performed for height-to-width aspect ratios of the enclosure from 0.25 to 8,Rayleigh numbers based on the length of the heated and cooled walls from $1 0 ^ { 2 }$ to $1 0 ^ { 7 }$ ,and tilting angles of the enclosure from $0 ^ { \circ }$ to $7 5 ^ { \circ }$ . The existence of an optimal tilting angle is confirmed for any investigated configuration,atalocation that increasesas the Rayleigh number is decreased,and the height-to-widthaspectratioof thecavityare increased,unlessthe value of the Rayleigh number is that corresponding to the onset ofconvection or just higher. Dimensionless correlating equations are developed to predict the optimal tlting angle and the heat transfer performance of the enclosure.

# Keywords:Naturalconvectioninair,Tiltedcavity,Dierential heating,Numericalanalysis,Dimensionlesscorrelations

# Introduction

Natural convection inside differentially-heated rectangular enclosures filled with air has been widely studied in the past decades,due to its relevance to many engineering applications,such as heat transfer in buildings,solar energy collection，and heat removal in micro-electronics, to name a few.

The main body of the research conducted on this topic deals with situations wherein the enclosure is either vertical or horizontal, which means that buoyancy is induced by imposing a heating either from the side,in examining conventional convection,or from below, in studying thermal instabilities.However,a number of studies related to the effects of the cavity inclination with respect to gravity on the enhancement or deterioration of the heat transfer performance of the enclosure are also available in the literature,demonstrating the existence of an optimal tilting angle of the enclosure for maximum heat transfer [1-19].A summary of these publications,subdivided according to the research method, i.e.,experimental or numerical,is presented in Tables 1 and 2,respectively,in which indications on the investigated ranges of the tilting angle of the enclosure with respect to the gravity vector, $\boldsymbol { \Phi }$ (where $\varphi = 0 ^ { \circ }$ corresponds to the vertical configuration in which the cavity is differentially heated at sides,and positive tilting angles denote configurations with the heated wall facing upwards), the height-to-width aspect ratio of the enclosure,A,and the Rayleigh number based on the cavity height, $\mathrm { R a } _ { \mathrm { H } }$ ，areenumerated.Indications on the optimal tilting angle of the enclosure,which our interest is focused on,are also reported. Indeed,

# Nomenclature

<html><body><table><tr><td>A</td><td>height-to-width aspect ratio of the enclosure</td><td>X,Y</td><td>dimensionless Cartesian coordinates</td></tr><tr><td>g</td><td> gravity vector, m/s²</td><td>x,y</td><td>Cartesian coordinates,m</td></tr><tr><td>g</td><td>gravitational acceleration, m/s²</td><td colspan="2">Greek symbols</td></tr><tr><td>H</td><td>height of the enclosure, m</td><td>α</td><td>thermal diffusivity, m²/s</td></tr><tr><td>k</td><td>thermal conductivity, W/(m K)</td><td>β</td><td>coefficient of volumetric thermal expansion,1/K</td></tr><tr><td>Nu</td><td>Nusselt number</td><td>V</td><td>kinematic viscosity, m²/s</td></tr><tr><td>P</td><td>dimensionless pressure</td><td>p</td><td>mass density, kg/m</td></tr><tr><td>Pr</td><td>Prandtl number</td><td>T</td><td>dimensionless tme</td></tr><tr><td>Q</td><td>heat transfer rate, W</td><td>p</td><td>tilting angle of the enclosure with respect to gravity, deg</td></tr><tr><td>q</td><td>heat flux, W/m²</td><td>Y</td><td>dimensionless stream function</td></tr><tr><td>Ra</td><td>Rayleigh number based on the cavity height</td><td colspan="2">Subscripts</td></tr><tr><td>T</td><td>dimensionless temperature</td><td colspan="2">av average</td></tr><tr><td>t</td><td>temperature, K</td><td>C</td><td>cooled wall, at the temperature of the cooled wall</td></tr><tr><td>U,V</td><td>X,y-wise dimensionless velocity component</td><td>h</td><td>heated wall, at the temperature of the heated wall</td></tr><tr><td>V</td><td>dimensionless velocity vector</td><td>opt</td><td>optimal value</td></tr><tr><td>W</td><td>width of the enclosure, m</td><td></td><td></td></tr></table></body></html>

Table 1Summary of experimental studies performed on natural convection in air-filled inclined cavities   

<html><body><table><tr><td>Year</td><td>Author(s)</td><td>RaH</td><td>H/L</td><td></td><td>Popt</td></tr><tr><td>1975</td><td>Ozoe et al. [1]</td><td>6.6 × 10-2.2 × 107</td><td>8.4, 15.5</td><td>-90°-90°</td><td>~10°</td></tr><tr><td>1976</td><td>Hollands et al. [2]</td><td>2 × 10-1.1×1010</td><td>48</td><td>30°-75°</td><td></td></tr><tr><td>1982</td><td>Elshirbiny [3]</td><td>1.3 ×10-2.4×1010</td><td>5-110</td><td>0°-90°</td><td></td></tr><tr><td>1983</td><td>Elshirbiny [4]</td><td>1.0 ×10-1.5×1010</td><td>10,80</td><td>0°-30°</td><td></td></tr><tr><td>1985</td><td>Schinkel and Hoogendorn [5]</td><td>2 ×10-2.7 ×108</td><td>1-11</td><td>0°-70°</td><td>15°-30°</td></tr><tr><td>1988</td><td>Karayiannis and Tarasuk [6]</td><td>6.0 × 10 -1.8 ×108</td><td>6.7-16.7</td><td>30°-75°</td><td></td></tr><tr><td>1989</td><td>Hamady et al. [5]</td><td>1 ×104-1 ×106</td><td>1</td><td>0°-180°</td><td>10°-20°</td></tr><tr><td>2007</td><td>Bairi et al. [8]</td><td>4.2 ×10-4.2×107</td><td>0.75</td><td>0°-360°</td><td>60°-90°</td></tr><tr><td>2008</td><td>Bairi [9]</td><td>1 ×10'-1×1010</td><td>1</td><td>0°-360°</td><td>60°-90°</td></tr><tr><td>2012</td><td>Corvaro et al. [10]</td><td>1.2 × 10 -4.6 × 105</td><td>1</td><td>0°-90°</td><td>0°</td></tr></table></body></html>

Table 2Summary of numerical studies performed on natural convection in air-filled inclined cavities   

<html><body><table><tr><td>Year</td><td>Author(s)</td><td>RaH</td><td>H/L</td><td></td><td>Popt</td></tr><tr><td>1983</td><td>Elshirbiny [4]</td><td>1.0 × 10-1.5 × 10'0</td><td>10,80</td><td>0°-30°</td><td></td></tr><tr><td>1993</td><td>Kuyper et al. [11]</td><td>1 ×104-1×10l2</td><td>1</td><td>0°-180°</td><td></td></tr><tr><td>1996</td><td>Soong et al. [12]</td><td>5.4 ×104-1.3 ×106</td><td>1,3,4</td><td>0°-90°</td><td>0°-30°</td></tr><tr><td>2001</td><td>Delgado-Buscalioni et al.[13]</td><td>1×10²-8×105</td><td>0.01-0.25</td><td>0°-90°</td><td>0°-20°</td></tr><tr><td>2006</td><td>Baez and Nicolas[14]</td><td>1 ×10²-5.12 ×108</td><td>1,8</td><td>0°-330°</td><td></td></tr><tr><td>2010</td><td>Nor Azwadi et al. [15]</td><td>1 ×105</td><td>1</td><td>20°-90°</td><td>10°-30°</td></tr><tr><td>2011</td><td>Munir et al. [16]</td><td>5×105</td><td>1</td><td>0°-180°</td><td>~10°</td></tr><tr><td>2012</td><td>Vivek et al. [17]</td><td>1 ×104-1× 106</td><td>0.2-1</td><td>0°-180°</td><td>~15°</td></tr><tr><td>2014</td><td>Chang [18]</td><td>1 ×10²-5.12 ×108</td><td>1-8</td><td>0°-180°</td><td>0°-20°</td></tr><tr><td>2016</td><td>Williamson et al. [19]</td><td>1 ×104-1×108</td><td>1</td><td>0°-80°</td><td>15°-25°</td></tr></table></body></html>

although some results obtained by the cited authors are contradictory, in line of principle the optimal tilting angle was found to increase as both the Rayleigh number and the aspect ratio of the enclosure were decreased. However, none of the cited authors developed a correlation for the prediction of the optimal tilting angle and the corresponding heat transfer rate across the cavity. Moreover, the physics behind the existence of the optimal tilting angle and its location in relation with the value of the independent variables used as controlling parameters was generally left out of the discussion of the results.

Framed in this general background,a comprehensive study of natural convection in air-filled,differentiallyheated rectangular cavities inclined with respect to gravity,so that the heated wall is facing upwards,is performed numerically under the assumption of two-dimen sional laminar flow, for ranges of the height-to-width aspect ratio of the enclosure from O.25 to 8,the Rayleigh number based on the length of the heated and cooled walls from $1 0 ^ { 2 }$ to $1 0 ^ { 7 }$ ，and the tilting angle of the enclosure with respect to gravity from $0 ^ { \circ }$ to $7 5 ^ { \circ }$ ,with the main scope to investigate the basic heat and momentum transfer features and develop accurate correlations for predicting the optimal tilting angle and the heat transfer performance of the enclosure,which seems useful for thermal engineering design purposes.

# Mathematical formulation

An air-filled rectangular enclosure of height $\mathrm { ~ H ~ }$ and width W is considered. The enclosure is differentially heated at two opposite walls,which are kept at uniform temperatures $\mathbf { t } _ { \mathrm { c } }$ and $\mathfrak { t } _ { \mathrm { h } } ,$ while the other pair of walls are assumed to be perfectly insulated. The enclosure is inclined at an angle $\boldsymbol { \Phi }$ with respect to the gravity vector, where $\Phi = 0 ^ { \circ }$ denotes the vertical configuration in which the cavity is differentially heated at sides.A sketch of the enclosure is displayed in Fig.1,where the reference Cartesian coordinate system $( \mathbf { x } , \mathbf { y } )$ ,and the thermal states of the boundary walls,are also represented. The resulting buoyancy-induced fluid flow is considered tobe two-dimensional, laminar and incompressible,with constant fluid properties and negligible viscous dissipation and pressure work.The buoyancy effects on momentum transfer are taken into account through the customary Boussinesq approximation.

![](images/4de59e8f3862202f7c2fbf4d6f7d8ca0fdb9b8588ebea541f6a53809f323770c.jpg)  
Fig.1Sketch of the geometry and coordinate system

Once these assumptions are employed in the conservation equations of mass,momentum and energy, the following set of governing dimensionless equations is ob

tained:

$$
\nabla \cdot \mathbf { V } = 0
$$

$$
{ \frac { \partial \mathbf { V } } { \partial \tau } } + ( \mathbf { V } \cdot \nabla ) \mathbf { V } = - \nabla P + \nabla ^ { 2 } \mathbf { V } - { \frac { R a } { \mathrm { P r } } } T { \frac { \mathbf { g } } { g } }
$$

$$
{ \frac { \partial T } { \partial \tau } } + ( \mathbf { V } \cdot \nabla ) T = { \frac { 1 } { \mathrm { P r } } } \nabla ^ { 2 } T
$$

where $\mathbf { V }$ is the dimensionless velocity vector having Xwise and y-wise dimensionless velocity components $\mathrm { ~ U ~ }$ and $\mathrm { \Delta V }$ normalized by $\nu / \mathrm { H }$ ， $\tau$ is the dimensionless time normalized by ${ \mathrm { H } } ^ { 2 } / { \mathrm { v } } , \ { \mathrm { P } }$ is the dimensionless pressure normalized by $\rho \nu ^ { 2 } / \mathrm { H } ^ { 2 }$ $\mathrm { \Delta T }$ is the dimensionless temperature excess over the uniform temperature of the cooled wall normalized by the temperature difference between the heated and cooled walls $\left( \mathfrak { t } _ { \mathrm { h } } - \mathfrak { t } _ { \mathrm { c } } \right)$ ， g is the gravity vector, $\mathrm { P r } = \mathrm { v } / \alpha$ is the Prandtl number,and $\mathrm { R a }$ is the Rayleigh number defined as

$$
R a = \frac { g \beta ( t _ { h } - t _ { c } ) H ^ { 3 } } { \alpha \nu }
$$

where $\beta , \nu$ and $\alpha$ are the coefficient of volumetric thermal expansion, thekinematic viscosity and the thermal diffusivity of the fluid,respectively.

Another parameter which enters into this study is the height-to-width aspect ratio of the enclosure

$$
A = { \frac { H } { L } }
$$

The assigned boundary conditions are: (a) $\mathrm { T } = 1$ and $\mathbf { V }$ $= 0$ at the heated wall; (b) $\mathrm { { T } } = 0$ and $\mathbf { V } = 0$ at the cooled wall; and (c) $\hat { \sigma } \mathrm { T } / \hat { \sigma } \mathrm { n } = 0$ and $\mathbf { V } = 0$ at the adiabatic walls, where n denotes the normal to the wall.

The initial conditions assumed throughout the enclosure are fluid at rest, i. e., $\mathbf { V } = 0$ ，and uniform temperature $\mathrm { { T } } = 0$ ：

# Computational procedure

The system of the governing equations defined by Eqs. (1)-(3),combined with the boundary and initial conditions stated earlier,is solved through a control-volume formulation of the finite-difference method. The pressure-velocity coupling is handled using the SIMPLE-C algorithm introduced by Van Doormaal and Raithby [20], which is a more implicit variant of the SIMPLE algorithm developed by Patankar and Spalding [21]. Convective terms are approximated by the QUICK discretization scheme proposed by Leonard [22]. A second-order backward scheme is employed for time integration.Both space discretization and time stepping are chosen uniform.Starting from the assigned initial fields of the dependent variables across the cavity,at each time-step the system of discretized algebraic governing equations is solved iterativelyby way ofa line-by-line application of the Thomas algorithm.A standard under-relaxation technique is enforced in all steps of the computational pro cedure to ensure adequate convergence.Within each timestep, the spatial numerical solution of the velocity and tem perature fields is considered to be converged when the maximum absolute values of the mass source,as well as the relative changes of the dependent variables at any gridnode between two consecutive iterations,are smaller than the pre-specified values of $1 0 ^ { - 5 }$ and ${ { 1 0 } ^ { - 6 } }$ , respectively. As time passes,the dynamic behavior of the system analyzed is followed by plotting the phase trajectories of the dependent variables T,U,andV,ata number of assigned spatial locations,i.e.,the distributions of the local timederivatives of the dependent variables versus the variables themselves with time as a parameter,and continuously monitoring the time distributions of the heat transfer ratesattheheatedandcooledwalls,aswellastheirrelative difference,so as to visualize the path of the system toward the steady-state.Time-integration is stopped when the relative changes of the time-derivatives of the dependent variables at any grid node and the relative difference between the heat transfer rates added to the fluid by the heated wall andwithdrawn from the fluidbythe cooled wall between two consecutive time steps are smaller than the pre-set values of $1 0 ^ { - 7 }$ and $1 0 ^ { - 8 }$ ,respectively.

Once steady-state is reached, the local Nusselt numbers at the heated and cooled walls, $\mathrm { N u _ { h } }$ and $\mathrm { N u _ { c } }$ ，are calculated by the following expressions:

$$
\mathrm { N } \mathbf { u } _ { \mathrm { h } } = { \frac { \mathbf { q } _ { \mathrm { h } } \mathrm { H } } { \mathrm { k } ( \mathbf { t } _ { \mathrm { h } } - \mathbf { t } _ { \mathrm { c } } ) } } = - { \frac { \partial \mathrm { T } } { \partial \mathrm { X } } } \bigg | _ { \mathrm { X } = 0 }
$$

$$
N u _ { c } = \frac { q _ { c } H } { k ( t _ { c } - t _ { h } ) } = - \frac { \partial T } { \partial X } \bigg | _ { X = 1 / A }
$$

where $\mathbf { q } _ { \mathrm { h } }$ and ${ \sf q } _ { \mathrm { c } }$ are the heat fluxes at the heated and cooled walls, $\mathbf { k }$ is the thermal conductivity of the fluid, and $\mathrm { \Delta X }$ and $\mathrm { Y }$ are the dimensionless Cartesian coordinates normalized by $\mathrm { H }$ .Both temperature gradients in Eqs. (6) and (7) are evaluated by a second-order temperature profile embracing the wal-node and the two adjacent fluid-nodes.The corresponding average Nusselt numbers $( \mathrm { N u _ { h } } ) _ { \mathrm { a v } }$ and $( \mathrm { N u _ { c } ) _ { a v } }$ are then calculated as:

$$
\left( N u _ { h } \right) _ { a v } = \frac { Q _ { h } } { k ( t _ { h } - t _ { c } ) } = - \int _ { 0 } ^ { 1 } \frac { \partial T } { \partial X } \bigg | _ { X = 0 } d Y
$$

$$
\left( N u _ { c } \right) _ { a \nu } = \frac { Q _ { c } } { k ( t _ { c } - t _ { h } ) } = - \int _ { 0 } ^ { 1 } \frac { \partial T } { \partial X } \Bigg | _ { X = 1 / A } d Y
$$

where $\mathrm { Q } _ { \mathrm { h } }$ and $\mathrm { Q _ { c } }$ are the heat transfer rates added to the fluid by the heated sidewall and withdrawn from the fluid by the cooled sidewall. Both integrals in Eqs. (8) and (9) are computed numerically by means of the trapezoidal rule. Of course，since at steady-state the heat transfer rates at both the thermally active walls are the same, i.e., $\mathrm { Q _ { h } } = - \mathrm { Q _ { c } } = \mathrm { Q }$ ，the average Nusselt numbers coincide with what can be assumed to be the average

Nusselt number of the enclosure $\mathrm { N u _ { a v } = ( N u _ { h } ) _ { a v } = ( N u _ { c } ) _ { a v } }$ （20

Numerical tests related to the dependence of the re sults obtained on the mesh spacing and time stepping have been performed for several combinations of the three controlling parameters,namely A,Ra,and $\boldsymbol { \Phi }$ . The mesh-spacing and time-step used for computations are chosen in such a way that further refinements do not produce noticeable modifications either in the heat transfer rates or in the flow fields. In particular, the percentage change of Nu,as well as that of the maximum absolute value of the dimensionless stream function throughout the enclosure $| \Psi | _ { \mathrm { m a x } } ,$ ，where $\psi$ is defined as usual by $\mathrm { U } =$ ${ \hat { o } } \Psi / { \hat { o } } \mathrm { Y }$ and $\mathrm { V } = - { \hat { o } } \Psi / \operatorname { \hat { o } } \mathrm { X }$ ,must be smaller than the preestablished accuracyvalue of $1 \%$ .The typical number of nodal points and the time-step used for computations lie in the rangesbetween $6 0 \times 6 0$ and $1 2 0 \times 4 8 0$ ,and between $1 0 ^ { - 2 }$ and $1 0 ^ { - 4 }$ ，respectively. Selected results of the grid and time-step sensitivity analysis are listed in Tables 3-5.

Finally,with the scope to validate the numerical code used for the present study, three different tests have been executed.In the first test,the steady-state solutions obtained for an air-filled,vertical square cavity differentially heated at sides with adiabatic top and bottom walls have been compared with the benchmark solutions of de Vahl Davis [23],Mahdi and Kinney [24],Hortman et al. [25],and Wan et al. [26]. In the second test, the average Nusselt numbers computed numerically at steady-state for vertical rectangular cavities using a Prandtl number $\mathrm { P r } = 0 . 7$ and Rayleigh numbers $\mathrm { { R a } } = 1 0 ^ { 3 } { - 5 } { \times } 1 0 ^ { 7 }$ ，have been compared with the usually recommended Berkovsky-Polevikov correlation，see,e.g.,Bejan [27] and Incropera et al. [28]. In the third test, the average Nusselt numbers computed numerically for inclined rectangular cavities have been compared with the results of Bairi [9]. A good degree of agreement between our numerical solutions and the literature data was achieved in any valida tion test carried out, as e.g. shown for the third test in Fig 2.More details on the code validation can be found in a previous paper authored by Corcione and Habib [29].

![](images/cfa66a10c78d9584f6ee9d1ea32609515541a804c8f0087082f403d1709402b2.jpg)  
Fig.2Comparison between present numerical results and the results ofBairi[9] fora square enclosure

Table 3Time-step sensitivity analysis for square cavity   

<html><body><table><tr><td>Ra</td><td>A</td><td>p[deg]</td><td>Mesh size</td><td>△t[s]</td><td>Nuh</td><td>%</td><td>|P|max</td><td>%</td></tr><tr><td>106</td><td>1</td><td>0°</td><td>120 x 120</td><td>10²</td><td>9.47</td><td></td><td>25.53</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>10-</td><td>9.11</td><td>-3.85</td><td>24.56</td><td>-3.80</td></tr><tr><td></td><td></td><td></td><td></td><td>10-4</td><td>8.93</td><td>-1.96</td><td>24.09</td><td>-1.94</td></tr><tr><td></td><td></td><td></td><td></td><td>10-5</td><td>8.93</td><td>0.01</td><td>24.06</td><td>-0.11</td></tr></table></body></html>

Table 4 Grid sensitivity analysis for inclined square cavity   

<html><body><table><tr><td>△t (s)</td><td>Ra</td><td>A</td><td>p[deg]</td><td>Mesh size</td><td>Nuh</td><td>%</td><td>||max</td><td>%</td></tr><tr><td>10-3</td><td>105</td><td>1</td><td>0°</td><td>60 × 60</td><td>4.60</td><td></td><td>13.95</td><td>-</td></tr><tr><td></td><td></td><td></td><td></td><td>80×80</td><td>4.55</td><td>-1.22</td><td>13.76</td><td>-1.38</td></tr><tr><td></td><td></td><td></td><td></td><td>100 ×100</td><td>4.54</td><td>-0.12</td><td>13.71</td><td>-0.37</td></tr><tr><td></td><td></td><td></td><td>30°</td><td>60 × 60</td><td>4.72</td><td></td><td>21.97</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>80×80</td><td>4.64</td><td>-1.58</td><td>21.59</td><td>-1.75</td></tr><tr><td></td><td></td><td></td><td></td><td>100 ×100</td><td>4.64</td><td>-0.17</td><td>21.54</td><td>-0.22</td></tr><tr><td></td><td></td><td></td><td>60°</td><td>60 ×60</td><td>4.51</td><td></td><td>34.19</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>80×80</td><td>4.45</td><td>-1.49</td><td>33.65</td><td>-1.59</td></tr><tr><td></td><td></td><td></td><td></td><td>100 ×100</td><td>4.43</td><td>-0.30</td><td>33.49</td><td>-0.47</td></tr></table></body></html>

Table 5Grid sensitivity analysis for inclined rectangular cavity   

<html><body><table><tr><td>△t (s)</td><td>Ra</td><td>p[deg]</td><td>A</td><td>Mesh size</td><td>Nuh</td><td>%</td><td>|y|max</td><td>%</td></tr><tr><td>10-3</td><td>106</td><td>0°</td><td>1</td><td>60 ×60</td><td>9.33</td><td></td><td>25.28</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>80×80</td><td>9.16</td><td>-1.81</td><td>24.79</td><td>-1.93</td></tr><tr><td></td><td></td><td></td><td></td><td>100 ×100</td><td>9.13</td><td>-0.32</td><td>24.68</td><td>-0.43</td></tr><tr><td></td><td></td><td></td><td></td><td>120 × 120</td><td>9.11</td><td>-0.23</td><td>24.56</td><td>-0.49</td></tr><tr><td></td><td></td><td>0°</td><td>0.25</td><td>60×240</td><td>61.92</td><td></td><td>30.62</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>80×320</td><td>61.21</td><td>-1.15</td><td>30.02</td><td>-1.98</td></tr><tr><td></td><td></td><td></td><td></td><td>100 ×400</td><td>61.04</td><td>-0.27</td><td>29.87</td><td>-0.48</td></tr><tr><td></td><td></td><td></td><td></td><td>120 ×480</td><td>60.88</td><td>-0.26</td><td>29.72</td><td>-0.51</td></tr><tr><td></td><td></td><td>30°</td><td>0.25</td><td>80 ×320</td><td>304.12</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>100 ×400</td><td>298.22</td><td>-1.94</td><td>101.63</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td>120 ×480</td><td>296.80</td><td>-0.48</td><td>99.50</td><td>-2.10</td></tr><tr><td></td><td></td><td></td><td></td><td>140 × 560</td><td>296.12</td><td>-0.23</td><td>98.75 98.43</td><td>-0.75 -0.32</td></tr></table></body></html>

# Results and discussion

Numerical simulations are performed for different values of(a) the height-to-width aspect ratio of the cavity, A，in the range between O.25 and 8,(b) the Rayleigh number based on the length of the thermally active walls, Ra, in the range between $1 0 ^ { 2 }$ and $1 0 ^ { 7 }$ ，and (c) the tilting angle of the enclosure with respect to the gravity vector, $\boldsymbol { \Phi }$ ,in the range between $0 ^ { \circ }$ and $7 5 ^ { \circ }$ ：

Typical local results are reported in Fig.3,in which equispaced isotherm and streamline contour plots at different tilting angles are depicted for $\mathbf { A } { } = 1$ and $\mathrm { R a } = 1 0 ^ { 5 }$ In the streamline plots, the contours correspond to equispaced values of the normalized dimensionless stream function ${ \left| { \Psi } \right| } / { \left| { \Psi } \right| } _ { \mathrm { m a x } }$ in the range between Oand 1.In the isotherm plots,the contours correspond to equispaced values of the dimensionless temperature in the range between O and1.

It may be seen that at $\varphi = 0 ^ { \circ }$ the flow field,as expected, consists of a single-roll cell that derives from the rising of the hot fluid adjacent to the heated wall and its descent along the opposite cooled wall,which leads to the distinctive temperature distribution featured by a fluid stratification in the core of the cavity. As the tilting angle $\boldsymbol { \Phi }$ isincreased,the vertical path available for the accelerationof the heated fluid increases,which results in a growth of the motion intensity and a simultaneous promotion of the thermal stratification breakdown, with a consequent increase of the heat transfer rate.On the other hand, as $\boldsymbol { \Phi }$ is further increased, the jet of cold fluid that moves downwards along the adiabatic wall tends to separate from it, with the consequent formation of a stagnation region on the heated wall downstream the point of impingement of the descending fluid,and, therefore,a more or less significant decrease of the amount of heat transferred across the cavity. This is displayed in Fig. 4, where the distributions of the local Nusselt number along the heated wall, $\mathrm { N u _ { h } }$ ,are reported for three different tilting angles, demonstrating that the thermal performance at $\varphi = 1 5 ^ { \circ }$ is higher than at $\varphi = 0 ^ { \circ }$ and $6 0 ^ { \circ }$ . Equivalent but reversed distributions could be depicted for the opposite cooled wall. Notice that the single-roll flow structure is a common pattern for all the examined configurations. Flow pattern evolutions not too dissimilar from that de scribed above are encountered for other values of A and Ra,as e.g. shown in Figs.5 and 6 for $\mathrm { A } = 0 . 2 5$ and $\mathrm { { R a } = }$ ${ { 1 0 } ^ { 6 } }$ ,and for $\mathrm { A } { = } 4$ and $\mathrm { R a } = 1 0 ^ { 6 }$ ,respectively.

As far as the overall results are concerned, the distributions of the average Nusselt number $\mathrm { \Delta N u }$ plotted versus Ra at $\scriptstyle \Phi = 0 ^ { \circ }$ are displayed in Fig.7 using the aspect ratio of the cavity as a parameter. It is apparent that,as long as conduction is the dominant heat transfermode and then the Nusseltnumberisindependent of the Rayleigh number, the thermal performance of the cavity increases with increasing the aspect ratio,due to the increase of the uniform temperature gradient existing between the heated and cooled walls. On the other hand, once the onset of motion takes place,which occurs at a critical Rayleigh number whose value increases with increasing the aspect ratio,the Nusselt number increases with increasing the Rayleighnumber, tending to become almost independent of the aspect ratio when the buoyancy force is high enough to give rise to the formation of two boundary layers adjacent to the thermally active walls.Actually, owing to the smaller amount of heat transferred between the fluid streams moving along the adiabatic walls, the thermal performance is slightly higher for the tall cavities and lower for the shallow cavities.An alternative representation of the results reported in Fig.7 can be obtained by plotting the distributions of the average Nusselt number Nu versus Ausing the Rayleigh number as a parameter,as shown in Fig.8,in which the mentioned slight increase of the thermal performance occurring with the increase of the cavity aspect ratio is pointed out. Trends of this same type of those illustrated in both Figs.7 and 8 can be observed when the cavity is inclined with respect to the gravity vector.

![](images/58fa95b1b2de67c34d094dc49e6ceb0008be6ccd68d4c9a2c05f33b735069eca.jpg)  
Fig.3Isotherm and streamline contours plots for $\mathrm { R a } = 1 0 ^ { 5 }$ $\mathbf { A } = 1$ and $\varphi = 0 ^ { \circ } - 6 0 ^ { \circ }$

![](images/d716dab825e12267f5b3cdd934b35cc1caa0f8a26612c9d9877c7cf3111d8559.jpg)  
Fig.4Local Nusselt number for $\mathrm { R a } = 1 0 ^ { 5 }$ $\mathbf { A } = 1$ and $\Phi ^ { = 0 ^ { \circ } - }$ $6 0 ^ { \circ }$

![](images/4c1fd7f3c3c8f7839c8e775c45e8e810d0dd40b8b5130293192d646794f7b9f8.jpg)  
Fig.5Isotherm and streamline contours plots for $\mathrm { R a } = 1 0 ^ { 6 }$ A $= 0 . 2 5$ and $\wp = 0 ^ { \circ } - 4 5 ^ { \circ }$ （204

Thus,in order to clearly highlight in what measure the inclination with respect to gravity affects the thermal performance of the cavity, the distributions of the ratio $\left( { \mathrm { N u } } / { \mathrm { N u } } _ { 0 } \right)$ between the average Nusselt numbers for the tilting angle $\boldsymbol { \Phi }$ and for the vertical position at same Rayleighnumber and aspect ratio,plotted versus $\boldsymbol { \Phi }$ using Ra as a parameter,are depicted in Figs.9-11 for $\mathrm { A } = 0 . 2 5 , 1$ ， and 4,respectively. It is apparent that, owing to the progressively larger inclination of the cavity,and the mentioned increase of the motion intensity, the ratio $\left( { \mathrm { N u } } / { \mathrm { N u } } _ { \mathrm { 0 } } \right)$ increases up to reaching a peak.As a rule, the impact of the increased motion cavity aspect ratio are smaller, but some exceptions occur. In fact, at any given aspect ratio larger than unity,should the Rayleigh number be such that heat transfer occurs by pure conduction, then speaking of motion intensity has no meaning and, obviously, the inclination of the cavity cannot have any effect on the heat transfer performance,which is for example what happens for $\mathrm { A } = 4$ at $\mathrm { { R a } } = 1 0 ^ { 4 }$ .On the other hand, should the Rayleigh number be of the order of that corresponding to the onset of convection, then the inclination of the cavity mayresult in a degradation of the heat transfer perfor mance, due to the fact that at large tilting angles conduction tends to become the dominant heat transfer mode which is for example what happens for $\mathrm { A } { = } 4$ at $\mathrm { R a } = 1 0 ^ { 5 }$ ：

![](images/645389a71a191c0583024f626121723dcee41a6bd7731e8b707491246ef74786.jpg)  
Fig.6Isotherm and streamline contours plots for $\mathrm { R a } = { 1 0 } ^ { 6 }$ $\mathbf { A } = 4$ and $\varphi = 0 ^ { \circ } - 6 0 ^ { \circ }$

![](images/ae88dd1caf08290040b7063a31c35d40fd0594d7a96caf84e1566d0882febc41.jpg)  
Fig.7Distributions of $\mathrm { { N u } }$ vs. Ra for $\Phi ^ { = } 0 ^ { \circ }$ and $\mathbf { A } = 0 . 2 5 - 4$ （204号

![](images/92bd059e40ea8f7e7558d540991aecd6387000751b3fc56b310bdbd489dfe2e8.jpg)  
Fig.8Distribution of $\mathrm { { N u } }$ vs.Afor $\Phi = 0 ^ { \circ }$ and $\mathrm { { R a } } = 1 0 ^ { 3 } - 1 0 ^ { 7 }$

![](images/4ffbc4922334738382ce3d4bd2621f2deaf09997d3c4823c20ac608bd5c76497.jpg)  
Fig.9Distributions of $\mathrm { N u } / \mathrm { N u } _ { 0 }$ vs. $\boldsymbol { \Phi }$ for $\mathrm { A } = 0 . 2 5$ and $\mathrm { { R a } = }$ ${ { 1 0 } ^ { 4 } } - { { 1 0 } ^ { 7 } }$

![](images/fe425fade365e9fca411499262b822b9fcf4ba37ac66d1c4d863649b9683ee10.jpg)  
Fig.10 Distributions of $\mathrm { N u } / \mathrm { N u } _ { 0 }$ vs. $\boldsymbol { \Phi }$ for $\mathbf { A } = 1$ and $\mathrm { R a } = 1 0 ^ { 4 }$ （204号 $- 1 0 ^ { 7 }$ （204号

![](images/28a311a98332a05f0b0a174bbb37dbae31409dee4be001d40d71f66fc40370b4.jpg)  
Fig.11 Distributions of $\mathrm { N u } / \mathrm { N u } _ { \mathrm { 0 } }$ vs. $\boldsymbol { \Phi }$ for $\mathrm { A } = 4$ and $\mathrm { R a } = 1 0 ^ { 4 }$ （204号 $- 1 0 ^ { 7 }$

The value of $\boldsymbol { \Phi }$ corresponding to the peak of $\left( { \mathrm { N u } } / { \mathrm { N u } } _ { 0 } \right)$ is defined as the optimal tilting angle for maximum heat transfer and denoted as $\boldsymbol { \Phi } _ { \mathrm { o p t } }$ . The value of the maximum average Nusselt number occurring at such optimal inclination is denoted as $\mathrm { N u _ { o p t } }$ . As the tilting angle of the enclosure is further increased above $\Phi _ { \mathrm { o p t } } ,$ the ratio $\left( { \mathrm { N u } } / { \mathrm { N u } } _ { 0 } \right)$ decreases,which is due to the excessive growth of the mentioned stagnation regions that form on both the heated and cooled walls. Obviously,when the increased stagnation effect outweighs the increased velocity effect, the ratio $\left( { \mathrm { N u } } / { \mathrm { N u } } _ { 0 } \right)$ becomeslower than unity,which means that the inclination with respect to gravity leads to a degradation of the heat transfer performance of the cavity.

As far as the dependence of the optimal tilting angle on the Rayleigh number and the aspect ratio of the cavity, a set of distributions of $\boldsymbol { \Phi } _ { \mathrm { o p t } }$ versus Ra are depicted in Fig. 12 for different values of A,showing that,as long as convection is the dominant heat transfer mode, $\boldsymbol { \Phi } _ { \mathrm { o p t } }$ increasesasRa is decreased,and Ais increased.The corresponding distributions of $\mathrm { \Delta N u _ { \mathrm { o p t } } }$ versus Ra are plotted in Fig. 13.

After having outlined the basic heat and fluid flow features,and discussed the effects of A,Ra,and $\boldsymbol { \Phi }$ ,on the overall thermal performance of the enclosure,a number of dimensionless correlations are now proposed for predicting the optimal tilting angle $\boldsymbol { \Phi } _ { \mathrm { o p t } }$ and the corresponding average Nusselt number $\mathrm { { N u } _ { \mathrm { { m a x } } } }$ ，aswell as the ratio $\left( { \mathrm { N u } } / { \mathrm { N u } } _ { 0 } \right)$ in the investigated range of tilting angles.

The numerical results obtained for the Nusselt Number for vertical cavities,i.e. $\varphi = 0 ^ { \circ }$ ，for the whole set of Rayleigh number, with $1 0 ^ { 4 } \le \mathrm { R a } \le 1 0 ^ { 7 }$ , and aspect ratios, with $0 . 2 5 \leq \mathrm { A } \leq 4$ ,asfar as convection heat transfer is prevalent, i.e. $\mathrm { N u } \geq 2 \mathrm { \times A }$ ,maybe correlated through the following algebraic equation, derived by a multiple regression procedure:

![](images/d87284c6ec5ef35d73c3c8e8ce766a9edea24a883401fe08564742070a26f312.jpg)  
Fig.12 Distribution of $\boldsymbol { \Phi } _ { \mathrm { o p t } }$ vs. Ra

![](images/481c364096fdf60a7c4efb42ddff6554fe7a6ecb6c82e2136e018e3a1120b117.jpg)  
Fig.13Distribution of $\mathrm { N u _ { o p t } }$ vs. Ra

$$
\mathbf { N } \mathbf { u } _ { 0 } = \left( 0 . 1 4 2 + 0 . 0 6 8 \cdot \ln ( \mathbf { A } ) \right) \cdot \mathbf { R } \mathbf { a } ^ { 0 . 2 + 0 . 1 \cdot \mathbf { A } ^ { - 0 . 3 } }
$$

with a $5 . 3 \%$ standard deviation of error and $92 \%$ of data within a $\pm 5 . 3 \%$ range of error. The numerical results obtained for other tilting angles,with $0 ^ { \circ } \leq \varphi \leq 4 5 ^ { \circ }$ ,in the same ranges ofRa and $\mathrm { { N u } }$ ，maybe correlated through the following algebraic equation, derived by a multiple regressionprocedure:

$$
\frac { \mathrm { N u } } { \mathrm { N u } _ { \mathrm { 0 } } } { = } 1 - 0 . 0 6 \cdot \mathrm { R a } ^ { a _ { \mathrm { A } } } \cdot \mathrm { A } ^ { - b _ { \mathrm { R a } } } \cdot \frac { \varphi - 5 . 5 \cdot \mathrm { R a } ^ { - 0 . 1 5 6 } \cdot \mathrm { A } ^ { c _ { \mathrm { R a } } } } { 1 + \mathrm { R a } ^ { 0 . 1 5 } \cdot \mathrm { A } ^ { 0 . 4 4 } }
$$

where

$$
a _ { \mathrm { { A } } } = - 0 . 0 4 + 0 . 3 1 \cdot \mathrm { { A } } ^ { - 0 . 0 4 5 }
$$

$$
{ \sf b } _ { \mathrm { R a } } = \frac { 1 0 ^ { 4 } } { \mathrm { R a } }
$$

$$
{ \mathbf { c } _ { \mathrm { { R a } } } } = 0 . 0 0 5 { \cdot } { \mathrm { R a } } ^ { 0 . 2 6 }
$$

with a $2 . 4 \%$ standard deviation of error and $9 5 \%$ of data within a $\pm 4 . 3 \%$ range of error.

The numerical results obtained for the optimum position tilting angle for the whole set of Rayleigh number, with $1 0 ^ { 4 } \le \mathrm { R a } \le 1 0 ^ { 7 }$ , as far as convection heat transfer is prevalent, i.e. $\mathrm { N u } \geq 2 \mathrm { \times A }$ ，may be correlated through the following algebraic equations,derived by a multiple re gression procedure:

for low aspect ratio cavities,i.e. $0 . 2 5 \leq \mathbf { A } \leq 2$

$$
\Phi _ { \mathrm { o p t } } = 0 . 1 5 5 { \cdot } \mathrm { A } + 3 0 { \cdot } \mathrm { R a } ^ { - 0 . 4 9 } + \frac { 5 { \cdot } \mathrm { A } ^ { 0 . 5 } { \cdot } \mathrm { R a } ^ { - 0 . 2 2 } } { \ln ( \mathrm { R a } { \cdot } \mathrm { A } ^ { - 5 } ) }
$$

with a 0.026 rad $( 1 . 5 ^ { \circ } )$ standard deviation and range of error from $- 0 . 0 5 5$ rad $( - 3 . 1 ^ { \circ } )$ to $+ 0 . 0 4 0$ rad $( + 2 . 3 ^ { \circ } )$

for high aspect ratio cavities, i.e. $3 \leq \mathrm { A } \leq 8$ （204号

$$
\Phi _ { \mathrm { o p t } } = 0 . 2 8 + { \frac { \left( 4 . 2 - 0 . 3 \cdot \mathrm { A } \right) \cdot \ln ( \mathrm { R a } ) - 0 . 4 5 } { \mathrm { A } ^ { 5 } } }
$$

with a 0.029 rad $( 1 . 7 ^ { \circ } )$ standard deviation and range of error from $- 0 . 0 6$ rad $( - 3 . 5 ^ { \circ } )$ to $+ 0 . 0 2$ rad $( + 1 . 3 ^ { \circ } )$ =

Absolute errors has been considered as the angle valuesmay be ina range between $0 ^ { \circ }$ to $4 5 ^ { \circ }$ that means that relative error of the correlation would be very dependent on the actual value, thus being less meaningful.

# Conclusions

Natural convection in air-filled rectangular cavities inclined with respect to gravity, so that the heated wall is facing upwards,has been studied numerically under the assumption of two-dimensional laminar flow,for heightto-width aspect ratios of the enclosure from O.25 to 8, Rayleigh numbers based on the length of the heated and cooled walls from $1 0 ^ { 2 }$ to $1 0 ^ { 7 }$ ，and tilting angles of the enclosure from $0 ^ { \circ }$ to $7 5 ^ { \circ }$ .A computational code based on the SIMPLE-C algorithm has been used for the solution of the system of the mass,momentum and energy transfer governing equations, assuming the initial condition of motionless fluid at the uniform temperature of the cooled wall up to the achievement of a steady-state solution.

It has been found that,as the inclination angle is increased starting from the vertical position,the heat transfer performance increases up to reaching a peak at an optimal tilting angle,that, in line of principle,unless the value of the Rayleigh number was that corresponding to the onset of convection or just higher, turned out to increase as the Rayleigh number was decreased,as well as the height-to-width aspect ratio of the cavity was in creased.

Dimensionless correlating equations have been pro posed to evaluate the optimal tilting angle and the heat transfer performance of the enclosure.

# References

[1]Ozoe,H.,et al.,Natural convection in an inclined rectangular channel at various aspect ratios and angles -experimental measurements,Int.J.Heat Mass Transfer,18 (1975), pp.1425-1431   
[2]Hollands,K.G. T.，et al., Free convection heat transfer acrossinclined air layers,J.Heat Transfer,98 (1976), pp. 189-193   
[3]Elshirbiny,S.M.,et al.,Heat transfer by natural convection across vertical and inclined air layers,J.Heat Transfer,104 (1982), pp. 96-102   
[4]Elshirbiny,S.M.,et al.,Nusselt number distribution in vertical and inclined air layers,J.Heat Transfer,105 (1983),pp.406-408   
[5]Schinkel, W.M.M., Hoogendoorn, C.J., Core stratification effects on natural convection in inclined cavities,Applied Scientific Research,42 (1985), pp.109-130   
[6]Karayiannis,T.G., Tarasuk,J.D., Natural convection in an inclined rectangular cavity with different thermal boundary conditions at the top plate,J.Heat Transfer, 110 (1988), pp. 350-357   
[7]Hamady,F.J.，Study of local natural convection heat transfer in an inclined enclosure,Int.J.Heat Mass Transfer,32 (1989), pp.1697-1708   
[8] Bairi,A., et al.,Numerical and experimental study of natural convection in tilted parellelepipedic cavities for large Rayleigh numbers,Exp.Therm. Fluid Sci.，31 (2007), pp.309-324   
[9]Bairi,A.,Nusselt-Rayleigh correlations for design of industrial elements:Experimental and numerical investigation of natural convection in tilted square air filled enclosures,Energy Conv. Manag.,49 (2008), pp.771-782.   
10]Corvaro,F.,et al.,PIV and numerical analysis of natural convection in tilted enclosures filled with air and with opposite active walls,Int.J.Heat Mass Transfer,55 (2012), pp.6349-6362   
11] Kuyper,R.A.,et al.,Numerical study of laminar and turbulent natural convection in an inclined square cavity, Int.J.Heat Mass Transfer,36 (1993),pp.2899-2911 [12]Soong,C.Y.,et al.,Numerical study on mode-transition of natural convection in differentially heated inclined enclosures，Int. J. Heat Mass Transfer,39 (1996)， pp.   
2869-2882 [13]Delgado-Buscaliani,R., Crespo del Arco,E.,Flow and heat transfer regimes in inclined differentially heated cavities,Int.J.Heat Mass Transfer,44 (2001),pp.1947-   
1962 [14]Baez,E.，Nicolas,A.，2D natural convection flows in tilted cavities: porous media and homogeneous fluids, Int. J. Heat Mass Transfer,49 (2006),pp.4773-4785 [15]Nor Azwadi, C. S.,et al., Virtual study of natural convection heat transfer in an inclined square cavity,J.Applied Sciences,10 (2010),pp.331-336 [16]Munir, F.A.,et al., Numerical simulation of natural convection in an inclined square cavity,J.Applied Sciences,   
11 (2011), pp.373-378 [17]Vivek,V.,et al.,Interaction effects between laminar natural convection and surface radiation in tilted square and shallow enclosures,Int.J.Thermal Sciences,60 (2012), pp. 70-84 [18] Chang,B.H.,Numerical study of flow and heat transfer in differentially heated enclosures,Thermal Science,18 (2014), pp. 451-463 [19] Williamson,N.,et al.,Stability and Nusselt number scaling for inclined differentially heated cavity flow,Int.J. Heat Mass Transfer,92 (2016),pp.787-793 [20]Van Doormaal, J.P.,Raithby, G.D.,Enhancements of the simple method for predicting incompressible fluid flows, Numer: Heat Transfer,11 (1984), pp.147-163   
[21]Patankar, S.V., Spalding,D.B.,A calculation procedure for heat,mass and momentum transfer in three-dimensional parabolic flows,Int.J.Heat Mass Transfer,15 (1972), pp.1787-1797   
[22]Leonard,B.P.,A stable and accurate convective modelling procedure based on quadratic upstream interpolation, Comp.Meth.in Appl.Mech.Engng.,19(1979),pp.59-78   
[23]de Vahl Davis,G.,Natural convection of air in a square cavity:a bench mark numerical solution, Int.J.Num. Meth.Fluids,3(1983),pp.249-264   
[24]Mahdi,H. S.，Kinney,R.B.，Time-dependent natural convection in a square cavity:application of a new finite volume method, Int. J. Num. Meth. Fluids,11 (1990), pp. 57-86   
[25]Hortmann,M.,et al.,Finite volume multigrid prediction of laminar natural convection: bench-mark solutions, Int. J. Num. Meth.Fluids,11 (1990),pp.189-207   
[26] Wan,D.C.,et al.,A new benchmark quality solution for the buoyancy-driven cavity by discrete singular convolution,Num.Heat Transfer,40 (2001),pp.199-228   
[27] Bejan,A.,Convection Heat Transfer,JohnWiley& Sons Inc.,Hoboken,New Jersey,2004   
[28] Incropera,F.P.,Dewitt,D.P.,Bergman,T.L.,Lavine,A.S., Fundamentalsof Heat and Mass Transfer,John Wiley& Sons Inc.,Hoboken,New Jersey,2007.   
[29] Corcione,M.,Habib,E.,Buoyant heat transport in fluids across tilted square cavities discretely heated at one side, Int.J. Therm. Sci.,49 (2010),pp.797-808