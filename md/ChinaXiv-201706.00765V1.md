# Liquid Phase Evaporation on the Normal Shock Wave in Moist Air Transonic Flows in Nozzles

Slawomir Dykas\*,Artur Szymahski and Miroslaw Majkut

Instituteof PowerEngineringand Turbomachinery,Silesian Universityof Technology,ul.Konarskiego18,44-100 Gliwice, Poland

$\copyright$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

This paper presents a numerical analysis of the atmospheric air transonic flow through de Laval nozzles.By nature,atmospheric air always contains acertain amount of water vapor.The calculations were made using a Laval nozzle with a high expansion rate and a convergent-divergent (CD)“half-nozzle",referred to as a transonic diffuser, with a much slower expansion rate.The calculations were performed using an in-house CFD code.The computational model made it possible to simulate the formationof the liquid phase due to spontaneous condensation of water vapor contained in moist air.The transonic flow calculations also take account of the presence of a normal shock wave in the nozzle supersonic part to analyze the efect of the liquid phase evaporation.

# Keywords: moist air, condensation,transonic flow,shock wave,CFD simulation,in-house code

# Introduction

Moist air is a solution (or mixture) of dry air and superheated water vapor or dry saturated vapor, or dry saturated water vapor and liquid or ice mist.Depending on the combination，three cases can be distinguished. The first one is moist non-saturated air, the second - moist saturated air and the third - moist oversaturated air. The amount of superheated and saturated water vapor in air is limited. The vapor contained in air starts to condense if the air temperature is lowered to the vapor saturation temperature for its component pressure in moist air, which is referred to as the dewpoint.When condensation occurs in the moist air transonic flow field, the flow is affected bylatent heat released in the process.Within this study,a condensing flow was produced by moist air expansion in nozzles.This was accompanied by formation of shock waves in the supersonic parts of the flow field due to an increase in outlet pressure.The presented numerical investigations were carried out to show the effect of on-shock wave evaporation of the liquid phase resulting from water vapor condensation.

The numerical analyses presented herein were conducted using convergent-divergent nozzles.ALaval “full nozzle” and a ‘half-nozzle” were used.In the Laval "half-nozzle” the upper wall is shaped like a typical convergent-divergent nozzle,whereas the bottom wall is flat along its entire length. The flow through a convergentdivergent nozzle is one of the fundamental and most common transonic flows.Laval nozzles are widely used in technology,e.g.in transport and power engineering, mainly to accelerate gas to supersonic speeds. Due to very good insulating properties of transonic flows,de Laval nozzles are also used in high-voltage circuit breakers.

Air moisture has an essential impact on many processes taking place in power engineering equipment and machinery.If air cannot be dried at thenozzle inlet in technological applications using convergent-divergent nozzles,it is absolutely necessary to take account of the liquid phase formation,which occurs due to condensation of water vapor contained in atmospheric air. During the flow through CD nozzles normal shock waves are generated due to frequent changes in parameters at the nozzle outlet.On these waves,which are mainly normal,the flow parameters change dramatically.

The problem of the moist air condensing flow modeling has been investigated by numerous researchers for many years.Both experimental and numerical studies have been made in this field. The most known of them are the works of Schnerr and his research team[12,13, 14].The works focus both on the analysis of moist air internal flows [1,2]as well as on aerodynamic applications such as the flow around an aircraft wing profile [3]. Recent works in this field concern external flows in the first place and are related to aerodynamic issues [9].

The calculations presented herein were made using an in-house CFD code,which has been developed and used in many engineering applications for over 15 years in the moist air and steam condensing flow calculations, to predict condensation on the flow fields with shock waves, where the Navier-Stokes equations are solved numericallyusinga3rd-orderMUSCLtype TVDfinite-difference scheme with the 2nd-order Runga-Kutta method for time integration. The two-equation k-o SST turbulence model was selected for the purpose of turbulence modeling.

# Moist Air

Gases,air included,hardly ever occur in nature in the dry state.What is referred to as moist air is a mixture of dry air with water vapour or condensed water. The mass of moist air is defined as the sum of dry air mass, $m _ { a }$ and the total mass of water vapour and water, $m _ { \nu , \theta }$ ：

$$
m = m _ { a } + m _ { \nu , 0 } = m _ { a } + m _ { \nu } + m _ { l }
$$

The state of moist air (moist gas) is defined by stating its moisture (relative or absolute).

Absolutemoisture is defined as the ratio of thewater vapour mass to the dry air mass:

$$
x = \frac { m _ { \nu } } { m _ { a } }
$$

Relative moisture is referred to as the real-to-maximum moisture content ratio;it is defined as the ratio of the water vapour pressure to the water vapour saturation pressure.However, the relative moisture value is often given for integral parameters (in the computational practice - for stationary parameters at the inlet) and it is expressed inpercentages.The result is then as follows:

$$
\Phi _ { 0 } = \frac { p _ { \nu , 0 } } { p _ { \nu , s } ( T _ { 0 } ) } { \cdot 1 0 0 \% }
$$

Knowing the relative moisture value and the moist air pressure and total temperature,it is possible to find the absolute moisture value from the following equation:

$$
x = \frac { R _ { a } } { R _ { \nu } } \frac { 1 } { \Phi _ { 0 } \brace { \Phi _ { 0 } \int _ {  1 0 0  } ^ {  } \ d \mathbf { p } _ { \nu , s } ( T _ { 0 } ) } ^ {  \vphantom { \ d \ d } }  } - 1
$$

In addition to the moist air relative and absolute moisture values,the wetness mass fraction,i.e.the ratio of the water mass (condensate mass） to the moist air mass, is also defined:

$$
y = \frac { m _ { l } } { m }
$$

The wetnessmass fraction reaches itsmaximum value upon complete condensation of the entire water vapour contained in air.

$$
y _ { \mathrm { m a x } } = \frac { m _ { \nu , 0 } } { m }
$$

The relationship between absolute moisture and the maximum wetness mass fraction is expressed in the following way:

$$
x = \frac { m _ { \nu , 0 } } { m _ { a } } = \frac { m _ { \nu , 0 } } { m - m _ { \nu , 0 } } = \frac { m _ { \nu , 0 } } { 1 - \left. m _ { \nu , 0 } \right/ m } = \frac { y _ { \mathrm { m a x } } } { 1 - y _ { \mathrm { m a x } } }
$$

In aerodynamic issues air may with a good approximation be treated as a perfect gas because under relatively small pressures and in higher temperatures it behaves like perfect gases.

In the case of moist air, it may with a close approximation be assumed that the temperatures of the mixture, the air and the water vapour are equal:

$$
T = T _ { a } = T _ { \nu }
$$

whereas the pressure of the mixture,according to Dalton's law,is equal to the sum of the pressures of dry air and water vapour:

$$
p = p _ { a } + p _ { \nu }
$$

where,assuming that moist air is described by the perfect gas equation of state and the water vapour temperature is equal to the temperature of dry air, the water vapour pressure can be determined from the following equation:

$$
p _ { \nu } = p \frac { \left( y _ { \mathrm { m a x } } - y \right) } { \frac { R _ { a } } { R _ { \nu } } \cdot \left( 1 - y _ { \mathrm { m a x } } \right) + \left( y _ { \mathrm { m a x } } - y \right) }
$$

The water vapour and the dry air density may be found using the following relations:

$$
\begin{array} { r } { \rho _ { \nu } = \big ( y _ { \mathrm { m a x } } - 1 \big ) \cdot \rho } \\ { \rho _ { a } = \big ( 1 - y _ { \mathrm { m a x } } \big ) \cdot \rho } \end{array}
$$

whereas the air and water vapour mixture density $\rho$ ignoring the liquid phase volume,is calculated from the following equation:

$$
\rho = \frac { \rho _ { a } + \rho _ { \nu } } { ( 1 - y ) }
$$

The other thermodynamic quantities of moist air are found using the following relations:

$$
\begin{array} { l } { { h = \bigcup _ { a } \cdot \left( 1 - y _ { \operatorname* { m a x } } \right) + \nonumber h _ { \nu } \cdot \left( y _ { \operatorname* { m a x } } - y \right) + h _ { l } \cdot y } } \\ { { s = s _ { a } \cdot \left( 1 - y _ { \operatorname* { m a x } } \right) + s _ { \nu } \cdot \left( y _ { \operatorname* { m a x } } - y \right) + s _ { l } \cdot y } } \end{array}
$$

The surface tension for water enveloped in air is determined experimentally. One of the ways to do so is to apply the formula put forward by Pruppacher and Klett [10],which for a flat surface of the water-air phase separation may be written as:

$$
\sigma ( T ) = \{ \begin{array} { c } { { ( 7 6 . 1 + 0 . 1 5 5 \cdot ( 2 7 3 . 1 5 - T ) ) \cdot 1 0 ^ { - 3 } } } \\ { { \mathrm { f o r } T \geq 2 4 9 . 3 9 K } } \\ { { } } \\ { { ( ( 1 . 1 3 1 3 - 3 . 7 0 9 1 \cdot 1 0 ^ { - 3 } \cdot T ) \cdot T ^ { 4 } \cdot 1 0 ^ { - 4 } ) \cdot 1 0 ^ { - 6 } } } \\ { { - 5 . 6 4 6 4 ) \cdot 1 0 ^ { - 6 } } } \\ { { \mathrm { f o r } T < 2 4 9 . 3 9 K } } \end{array} 
$$

The moist air dynamic viscosity may be described using the Sutherland formula for the perfect gas:

$$
\mu \ = 1 . 7 1 \cdot 1 0 ^ { - 5 } \frac { 2 7 3 + 1 1 0 . 4 } { T + 1 1 0 . 4 } \Bigg ( \frac { T } { 2 7 3 } \Bigg ) ^ { 1 . 5 }
$$

In the case of moist air for the temperature range of $2 0 0 K$ to $3 0 0 K ,$ ，latent heat may be expressed as being linearly dependent on temperature [1]:

$$
L ( T ) = 3 1 0 5 9 1 3 . 9 9 - 2 2 1 2 . 9 7 \cdot T
$$

# Homogeneous Condensation Model

Upstream the condensation zone the mixture is in a non-equilibrium,metastable state.Departures from equilibrium are represented in terms of either subcooling $\varDelta T$ or supersaturation ratio $S$ Subcooling is defined as $\ A T =$ $T _ { s } ( p _ { \nu } ) \ : - \ : T ,$ where $T _ { s } ( p _ { \nu } )$ is the saturation temperature corresponding to the water vapour local partial pressure $p _ { \nu }$ and $T$ is the actual moist air temperature (for superheated states $A T < \theta$ and for subcooled states $A T > 0$ ） The supersaturation ratio is defined as $S = p _ { \nu } / p _ { s } ( T )$ (for superheated states $S < I$ and for subcooled states $S > I$ ） The methods of describing metastable states using either $\angles { T }$ or $S$ are equivalent and their choice depends on personal preferences.Downstream the condensation zone, where equilibriumis established, $\varDelta T = 0$ and $S = I$ ：

Due to expansion below the saturation line, the water vapour contained in moist air is strongly subcooled (4T), which leads to the formation of accidental clusters of Water molecules and, later on as subcooling proceeds, to a rise in the number and probability of formation of critical droplets. Critical droplets create condensation nuclei on which water vapour condenses rapidly. This phenomenon isreferred to as spontaneous (homogeneous)condensation,which results in primary droplets and then subcooled water vapour changes into mist. As the expansion rate gets higher, the number and average size of primary droplets decrease.The higher the expansion rate,the later spontaneous condensation takes place.Water molecules settle on the droplets being formed and the droplets get bigger. In the model of the condensation process applied in the calculations presented herein it is assumed that secondary effects of condensation,i.e.the settlement of droplets on solid surfaces limiting the flow, are omitted.

The liquid phase is represented by a countless number of droplets for which rotational motion and internal mass circulation are ignored; it is also assumed that there is no interaction between the droplets.The liquid phase is incompressible and it is made of spherical droplets.

Another assumption is that the two-phase flow de scribed herein is a non-slip one.Consequently,the flow conservation equations and the equation for the twoequationviscous turbulence model are written for a mixture [4,15]. Additional conservation equations describing the liquid phase formation and growth due to homogeneous condensation,assuming an averaged radius value, maybe reduced to a system of transport equations for two additional conservation variables: moisture $\rho \cdot y _ { h o m }$ and the number of droplets in a kilogram of moist air $\rho \cdot n _ { h o m }$ ：

Additional transport equations modelling the liquid phase formation and growth due to homogeneous condensation have the following form:

$$
\frac { \partial Q _ { \mathrm { h o m } } } { \partial t } + \frac { \partial E _ { \mathrm { h o m } } } { \partial x } + \frac { \partial F _ { \mathrm { h o m } } } { \partial y } + \frac { \partial G _ { \mathrm { h o m } } } { \partial z } + S _ { \mathrm { h o m } } = 0
$$

where $\boldsymbol { \mathcal { Q } }$ is the vector of conservation variables, $E , F$ and $G$ are flux vectors,and $S$ is the source term.For Car tesian coordinates the column vectors in the equation abovearedefinedasfollows:

$$
\begin{array} { r l } & { Q _ { \mathrm { h e m } } = \Bigg [ \int \boldsymbol { \phi } ^ { - 1 } \cdot \mathrm { B e m } } \\ & { \qquad \quad \times _ { \mathrm { B e m } } = [ \boldsymbol { \phi } ^ { - 1 } \cdot \mathrm { B e m } \cdot \boldsymbol { u } ] , } \\ & { E _ { \mathrm { h e m } } = [ \boldsymbol { \hat { \rho } } ^ { - 1 } \cdot \boldsymbol { \mathcal { P } } _ { \mathrm { b a m } } \cdot \boldsymbol { u } ] , \quad E _ { \mathrm { y , i m e } } = [ \boldsymbol { \Phi } ] , } \\ & { V _ { \mathrm { h e m } } = [ \boldsymbol { \hat { \rho } } ^ { - 1 } \cdot \mathrm { B i m } \cdot \boldsymbol { u } ^ { \prime } ] , \quad E _ { \mathrm { y , i m e } } = [ \boldsymbol { \Phi } ] , } \\ & { V _ { \mathrm { h e m } } = [ \boldsymbol { \hat { \rho } } ^ { - 1 } \cdot \boldsymbol { \mathcal { P } } _ { \mathrm { b a m } } \cdot \boldsymbol { v } ] , \quad E _ { \mathrm { t a n d } } = [ \boldsymbol { \Phi } ] , } \\ & { G _ { \mathrm { h e m } } = [ \boldsymbol { \hat { \rho } } ^ { - 1 } \cdot \boldsymbol { \mathcal { P } } _ { \mathrm { b a m } } \cdot \boldsymbol { v } ] , \quad G _ { \mathrm { v , i m e } } = [ \boldsymbol { \Phi } ] , } \\ & { V _ { \mathrm { s i m e } } = [ - \boldsymbol { \hat { \mathcal { Q } } } ^ { - 1 } \cdot \boldsymbol { \pi } \cdot \boldsymbol { \rho } ^ { - 1 } \boldsymbol { \rho } \boldsymbol { \hat { \rho } } ] , \quad \quad G _ { \mathrm { v , i m e } } = \boldsymbol { \hat { \mathcal { P } } } \cdot \boldsymbol { \mathcal { P } } _ { \mathrm { h a m } } \cdot \boldsymbol { \hat { \mathcal { P } } } _ { \mathrm { b a m } } ^ { 2 } , \quad \hat { \mathcal { P } } _ { \mathrm { a m } } ) \Bigg ] } \\ & { S _ { \mathrm { h e m } } = [ - \boldsymbol { \hat { \mathcal { Q } } } ^ { - 1 } \cdot \boldsymbol { \pi } \cdot \boldsymbol { \rho } \boldsymbol { \mathcal { P } } \cdot ( \boldsymbol { v } ^ { 2 } \cdot \boldsymbol { \mathcal { P } } _ { \mathrm { b a m } } + \boldsymbol { \hat { \mathcal { Q } } } \cdot \boldsymbol { \mathcal { P } } _ { \mathrm { v , i m e } } \cdot \boldsymbol { \hat { \mathcal { P } } } _ { \mathrm { b a m } } \cdot \boldsymbol { \hat { \mathcal { P } } } _ { \mathrm { b a m } } \cdot \boldsymbol { \hat { \mathcal { P } } } _ { \mathrm { b a m } } ) \Bigg ] . } \end{array}
$$

Wetness mass fraction $y _ { h o m }$ and the number of droplets per mixture mass unit $n _ { h o m }$ determined from the equations make it possible to find the averaged radius of the droplets:

$$
r _ { \mathrm { h o m } } = \left( \frac { 3 } { 4 \pi } \frac { y _ { \mathrm { h o m } } } { \rho _ { l } n _ { \mathrm { h o m } } } \right) ^ { 1 / 3 }
$$

The homogenous condensation model requires a description of two mechanisms: nucleation (formation of condensation nuclei with critical radius $r ^ { * }$ ）anddroplets growth.

# Nucleationrate

The fundamental condition that decides whether the condensation nuclei formed in water vapour will stand a chance to survive and not evaporate results from a comparison of specific free enthalpy of nuclei formation to the enthalpy maximum value. The maximum value of specific free enthalpy of nuclei formation is characterized by an unsteady condition of equilibrium between the liquid and the gaseous phase.The condition makes it possibleto determine thevalueof the critical radiusthat the arising nuclei should have to survive.

$$
r ^ { * }  d g ( p , T ) _ { \nu } \big | _ { T = c o n s t } = d g ( p , T ) _ { l } \big | _ { T = c o n s t }
$$

where $g ( p _ { \nu } , \nu _ { \nu } ) \big | _ { T } = \nu _ { \nu } d p$ ：

Knowing that the pressure on the liquid convex surface is bigger than on the flat one,according to the following relation:

$$
p _ { l } = p _ { \nu } + p _ { \sigma } = p _ { \nu } + \frac { 2 \cdot \sigma ( T _ { \nu } ) } { r }
$$

specific free enthalpy for the liquid may be written as:

$$
g ( p _ { l } , \nu _ { l } ) = \nu _ { l } d p _ { l } = \nu _ { l } d p _ { \nu } + \nu _ { l } d \Biggl ( \frac { 2 \cdot \sigma ( T _ { \nu } ) } { r } \Biggr )
$$

Comparing it to free enthalpy for water vapour, the following isobtained:

$$
\nu _ { \nu } d p _ { \nu } = \nu _ { l } d p _ { \nu } + \nu _ { l } d \Biggl ( \frac { 2 \cdot \sigma ( T _ { \nu } ) } { r } \Biggr )
$$

and finally,after transformations:

$$
\nu _ { \nu } d p _ { \nu } - \nu _ { l } d p _ { \nu } = \nu _ { l } d \Bigg ( \frac { 2 \cdot \sigma ( T _ { \nu } ) } { r } \Bigg ) .
$$

Substituting $\nu _ { \nu }$ determined from the gas equation of state and integrating both sides - the left one from $p _ { s }$ to $p _ { \nu }$ and the right one from $r \to \infty$ to $r ^ { * }$ ,the result is the Kelvin equation for the droplet critical radius,i.e. for a radius for which the droplet can grow further. Assuming the perfect gas model, the equation takes the form well-known from literature:

$$
\boldsymbol { r } ^ { * } = \frac { 2 \cdot { \sigma } } { \rho _ { l } \cdot R \cdot T _ { \nu } \cdot \mathrm { l n } \Bigg ( \frac { p _ { \nu } } { p _ { s } } \Bigg ) }
$$

Based on the assumed condition of equilibrium between the nuclei and the surrounding gaseous phase, the condensation nuclei formation rate,i.e.the nucleation rate,may be determined ina unit of time and ina unit of mass of the mixture $J _ { h o m }$ .Using the classic theory of nucleation [5,6,8], the nucleation rate may be calculated

from the following equation:

$$
\begin{array} { c } { { \displaystyle { J _ { \mathrm { h o m } } = C \cdot \sqrt { \frac { 2 \cdot \sigma } { \pi } } \cdot m _ { \nu } ^ { - 3 / 2 } } } } \\ { { \displaystyle { \cdot \frac { \rho _ { \nu } } { \rho _ { l } } \cdot \exp \left( - \beta \frac { 4 \cdot \pi \cdot r ^ { * 2 } \cdot \sigma } { 3 \cdot k \cdot T _ { \nu } } \right) } } } \end{array}
$$

The nucleation rate is very sensitive to changes in subcooling (4T) or supersaturation $( S )$ . As these quantities decide about the critical radius,which in Equation (19)is in the second power,even a slight change in subcooling involves great changes in the rate of critical dropletsformation.

In fact there is a difference between the temperature of the droplet being formed and the temperature of the gaseous phase surrounding it,which has a direct impact on the value of the nucleation rate.The effect may be taken into account using what is referred to as the nonisothermal coefficient put forward by Kantrowitz [7]:

$$
C = \left[ 1 + 2 \frac { \gamma - 1 } { \gamma + 1 } \frac { L } { R \cdot T _ { \nu } } \left( \frac { L } { R \cdot T _ { \nu } } - \frac { 1 } { 2 } \right) \right] ^ { - 1 } .
$$

It should be noted that due to difficulties that need to be faced in numerical research on condensing flows many correction factors modifying quantity $J$ can be found in literature.However, their physical justification is very poor. One such coefficient is coefficient $\beta$ ，which may limit the nucleation rate value.In practice，it is adopted based on experimental testing in convergentdivergent nozzles.The ranges of the selection of correction factors for flows through nozzles are defined relatively well. For other flows through more sophisticated channels the situation is more complex due to differences in the nature of the expansion processes and a more limited reference and experimental material. No correction coefficients are used in the numerical model applied herein,and coefficient $\beta$ in Equation (19) is equal to $\jmath$

# Droplet growth model

Describing the processes of exchange between the droplet and the gaseous phase surrounding it, the basic principles of the molecular-kinetic mechanism of the interaction of the gaseous medium with the phase separationsurfaceneedto be considered.The molecular-kinetic model is the case where the droplet free path length $1 _ { \mathrm { s } }$ is comparable to or bigger than the droplet diameter. Otherwise， the situation concerns a continuous medium model. The droplet free path-to-diameter ratio is called the Knudsen number expressed as follows:

$$
K n = { \frac { l _ { s } } { 2 \cdot r } } = { \frac { \mu _ { l } { \frac { \sqrt { \% } ^ { * } { \cdot } \pi \cdot R \cdot T _ { \nu } } { p } } } { 2 \cdot r } }
$$

In the case of water vapour condensation in moist air, the droplet free path value is much higher than the droplet diameter: $K n { > } { > } 1$ . The wetness mass fraction is here far smaller than in the case of pure water vapour. Therefore,the process of the heat and mass transfer between the gaseous and the liquid phase is based on the molecular-kinetic theory [6]. Thus, the droplet growth equation may be written as:

$$
\frac { d r } { d t } { = } \frac { \alpha } { \rho _ { l } } . \frac { p _ { \nu } - p _ { s } } { \sqrt { 2 \cdot \pi \cdot R \cdot T } }
$$

where $\boldsymbol { a } _ { c }$ is the condensation coefficient, here $= 1$ , and $p _ { s }$ is the water vapour saturation pressure.

# Numerical Results

# Validation calculations- Condensation model validationfor moist air expansion in theBarltmä nozzle

The experimental testing of the moist air transonic condensing flow carried out by Dohrmann [3] in the Barltmä hyperbolic nozzle is well known． The nozzle profile is described by the following equation:

$$
y = y ^ { * } \cdot { \sqrt { 1 + { \frac { y ^ { * } } { R ^ { * } } } { \left( { \frac { x } { y ^ { * } } } \right) } ^ { 2 } } }
$$

where the nozzle height in the critical cross-section and the nozzle radius are $y ^ { * } { = } 0 . 0 6 \mathrm { ~ m ~ }$ and $R ^ { * } { = } 0 . 2 ~ \mathrm { m }$ respectively.

For the purpose of the calculations presented herein, the flow with the inlet air relative moisture value $\varPhi _ { 0 } =$ $2 9 . 4 \%$ at the pressure of the surroundings of $1 0 9 \mathrm { k P a }$ and temperature of $3 0 0 . 6 \mathrm { K }$ ，was selected. The static pressure value at the level of $1 0 ~ \mathrm { { k P a } }$ is assumed at the outlet, which ensures a supersonic outflow. The numerical mesh adopted for the calculations is a structural, single-block mesh with the dimensions of $1 6 1 \times 1 0 1 \times 5$ Fig.1 presents the nozzle geometry and the distributions of the Mach number and the wetness mass fraction;Fig.2 shows the distributions of static pressure and the wetness mass frac tion along the nozzle central part.

As it can be seen in Fig.2, the comparison between computational and experimental results is satisfactory. Both the computational spontaneous condensation location and the condensation wave intensity are very close to experimental data.

The moist air flow validation calculations were also performed for many other cases,both in nozzles and around blade profiles.They proved the developed inhouse CFD code good capacity for modelling transonic condensing flows.

# Validation of the transonic flow with a normal shock wave

The next validation test presented herein was conducted using an experiment carried out by Sajben and Kroutil [11].The test is very common and concerns the transonic flow through a de Laval “half-nozzle".It was used to investigate the impact of back pressure in the nozzle on thenormal shockwave location. Correct modelling of the shock wave location depends largely on the correct discretization of the viscous terms in the RANS equations and on the applied turbulence model. The computations were performed ona structural numerical mesh (Fig.3).The boundary conditions adopted for the calculations correspond to the shock wave location in the divergent part close to the critical cross-section $y ^ { * }$ . The pressure and the total temperature at the nozzle inlet were 134470 Pa and $2 7 7 . 8 \mathrm { ~ K ~ }$ ，respectively，whereasstatic pressure at the outlet was $1 1 0 6 6 0 \mathrm { P a }$ ：

The Mach number distribution in the nozzle is shown in Fig.4,where the normal shock wave location,which for the adopted pressure ratio is close to the critical crosssection,canbe seenclearly.

![](images/8be619c780a23da9461281e50a7f7c020db5039212878d8abe764b9910ae2781.jpg)  
Wetness contour lines $\mathrm { ( y = 0 \div 7 ~ g l / k g }$ with $\Delta \mathbf { y } = 0 . 5 ~ \mathrm { g l / k g } )$

![](images/b346bca0c3effdf91017f7888f29b9d0d922528a6d82bedbda2bd79b39f95498.jpg)  
Fig.1 Isolines of the Mach number and the mass moisture degree in the Barltmä nozzle   
Fig.2Distributions of calculated and measured static pressure and of calculated wetness mass fraction along the nozzle central part

![](images/3d91dcbd93a673580833affa6ba4615f961044141458fa5fe5ac141d5c1db290.jpg)  
Fig.3Sajben's nozzle geometry and numerical mesh (3 blocks: $3 1 \times 1 5 1 \times 3$ $2 0 1 \times 1 5 1 \times 3$ and $3 1 \times 1 5 1 \times 3$ ）

![](images/75625fe6338f6d7201081f83ffd157b07ac0bd7b888d06af05e5352bc0e49908.jpg)  
Fig.4Mach number contour lines( $\mathrm { M a } { = } 0 { \div } 1 . 2$ with $\Delta \mathrm { M a } =$ 0.05) for Sajben's nozzle

The experiment provides a relatively large body of data that can be compared to the calculation results,such as the static pressure distribution along the nozzle upper and bottom walls, the velocity distribution for a few cross-sections of the nozzle,and the separation zone location on the upper wall. With so much experimental data. the numerical code and the selected turbulence model maybevalidated reliably.Further on,Fig.5 and Fig.6 show a comparison between the calculation results and the experimental data available from literature [11]. It can clearly be seen that the applied numerical code is able to model the transonic flow with a normal shock wave in Laval nozzles correctly.

![](images/42a81a93746e0a37f5aaee3725b07535a954df3a836d5e2d734960c9a52de28f.jpg)  
Fig.5Distribution of calculated and measured static pressure on the nozzle bottom and upper wall

# Calculations of the liquid phase evaporation on the normal shock wave at Barltmä convergent-divergent nozzle

For the Barltmä CD nozzle, the outlet static pressure was raised to $7 0 \mathrm { k P a }$ to generate a normal shock wave at the nozzle outlet. The generated shock wave was strong due to the fact that the expansion rate in the CD nozzle under consideration is high.There is an almost triple increase in pressure on the shock wave,which results in rapid and complete evaporation of the liquid phase created due to homogeneous condensation (Fig.7) even if the relative moisture values at the nozzle inlet are high.

![](images/278a87a829b7b1faafaa2005c9e129c33dfdc296a065fb36128cf56f390b4345.jpg)  
Fig.6Calculated and measured velocity profiles in the nozzle two cross-sections

It is known that on the normal shock wave there is a change in all parameters except total temperature (and for a perfect gas - also total enthalpy). In the case of moist air expansion， total temperature on the condensation wave increases initially, ${ \varDelta { T _ { 0 , c o n } } } ,$ due to the process of nucleation and droplets growth,whereas on the shock wave - there is a drop in total temperature, $\varDelta T _ { 0 , e \nu a } ,$ due to evaporation,and the total temperature value returns to the value at the nozzle inlet (Fig. 8).

Fig.9 and Fig. 1O present distributions of the Mach number andof thewetness mass fraction in a deLaval nozzle with a normal shock wave at the outlet for two values of relative moisture at the inlet.A clear impact can be seen of the relative moisture value at the inlet on the shock wave location - as the relative moisture value at the inlet rises,at other parameters at the nozzle inlet and outlet maintained at the same level, the shock wave is shifted downstream.Also the shock wave intensity decreases as the relative moisture value gets higher.

![](images/3b348673e8c7932afa4b934e64f42ae13fb60e301599125a25d22d35a164c32d.jpg)  
Fig.7Distributions of static pressure, Mach number and wetness mass fraction along the nozzle central part

![](images/02ae079464c468d972392788ba2f339c9df0f2a3a3f7555aad57eef1a54048b9.jpg)  
Fig.8Distributions of static and total temperature along the nozzle central part

![](images/46a31b934604034508ab03580a4aabdb5598bd9867565587d76e316a59696ad8.jpg)  
Fig.9Mach number contour lines $\mathrm { M a } = 0 \div 1 . 5$ with△ma $= 0 . 1$ ）

![](images/585a9c82f9312e5c7ddc6c1660c0ebe675a2bf222e5639308cc662c3badc1c28.jpg)  
Fig.10Moisture contour lines $\mathrm { ( y = 0 \div 1 0 g / k g }$ with $\Delta \mathbf { y } = 1 \ \mathbf { g } _ { \mathrm { l } } / \mathbf { k g } )$

# Sajben's transonic diffuser

Similar analyses were conducted for the flow through Sajben's nozzle,for two values of relative moisture at the inlet and for the same as before values of total parameters at the inlet and of static pressure at the outlet. In this case. because the nozzle opening degree is smaller, the expansion rate is much slower and,consequently, the shock wave is much weaker (Fig.11). Therefore，complete evaporation of the liquid phase occurs if the relative moisture value at the inletis small,whereas forthe relative moisture value of $70 \%$ onlya small part of the liquid phase evaporates on the shock wave.This is also the effect of the shock wave weakening due to a rise in the moist air relative moisture.

Fig.12 and Fig.13,respectively, show distributions of the Mach number and the mass moisture degree for the analysed cases of the moist air flow in Sajben's nozzle.

![](images/4d2721755cf96e1c9f770d493a96b03d260305d8341939594008047a2198fba6.jpg)  
Fig.11 Distributions of static pressure,the Mach number and the wetness mass fraction along Sajben's nozzle central part

![](images/c354a6d414203fe8540b9f3d65385bcc7c482ec594809c847ad8030e6db269a7.jpg)  
Fig.13Moisture contour lines $( \mathrm { y } = 0 \div 2 2 \mathrm { g } _ { \mathrm { l } } / \mathrm { k g }$ with $\Delta \mathbf { y } = 1$ （204号 $\mathbf { g } _ { \mathrm { l } } / \mathbf { k g } )$ for Sajben's nozzle

![](images/0a4a426f241f8f8e3d0031f475b177856338f2502a1ba90473a337c9ce71a7da.jpg)  
Fig.12Mach number contour lines( $\mathrm { { M a } } = 0 \div 1 . 1 5$ with △ma $= 0 . 0 5$ forSajben'snozzle

# Conclusion

This work considers the problem of the liquid phase evaporation due to condensation of water vapour contained in atmospheric air. The condensation process occurs as a result of moist air expansion in convergent-divergent nozzles.The capacity of the developed in-house CFD code for modelling this type of physical phenomena was tested. The following conclusions can be drawn based on the calculations:

· The applied in-house CFD code models the water vapour condensing flow in convergent-divergent nozzles with a normal shock wave correctly.   
· In a Laval nozzle,complete evaporation of the liquid phase created due to homogeneous condensation occurs on the shock wave almost in every case. Another water vapour condensation process may take place for example as a result of further expansion of moist air.   
· Gentle and gradual evaporation of the liquid phase is possible in the case of weak shock waves.   
·A rise in the air relative humidity has an impact on the normal shock wave location and intensity - the wave is weakened and shifted downstream.   
·A rise in total temperature occurs on the condensation wave,whereas on the shock wave, due to the liquid phase evaporation, the total temperature returns to the value that was initially at the nozzle inlet.

Further workswill focus on the developed methodology application for more complex geometries,as well as for flows with oblique shock waves.

# Acknowledgements

The presented work was supported by the Polish National Science Centre funds within the project with nr. UMO-2014/15/B/ST8/00203.

# References

[1]Adam S.，1996,Numerische und experimentelle Untersuchung instationaerer Duesenstroemungen mit Energiezufuhr durch homogene Kondensation,Dissertation, Fakultaet fuer Maschinenbau,Universitaet Karlsruhe   
[2]Doerffer P., Dykas S., 2005,Numerical analysis of shock induced separation delay by air humidity,Journal of Thermal Science 14 (2),120-125   
[3]Dohrmann U.，1989,Ein numerisches Verfahren zur Berechnung stationärer transsonischer Stromungen mit Energiezufuhr durch homogene Kondensation,Dissertation,Universitaet Karlsruhe,1989   
[4]Dykas S.，Wróblewski W.,2013,Two-fluid model for prediction of wet steam transonic flow,International Journal ofHeat and Mass Transfer,60,pp.88-94   
[5] FrenkelJ.,1955,Kinetic TheoryofLiquids,Dover,New York.   
[6] Gyarmathy G.，1969,Grundlagen einer Theorie der Nassdampfturbine,Juris Verlag,Zirich   
[7] Kantrowitz A.,1951,Nucleation in Very Rapid Vapour Expansions,Journal Chem.Phys.,19,1097-1100   
[8]Knudsen M.,1915,Annalen der Physik, Vol. 47, pp. 697- 708   
[9]Matsuo S., Yokoo K., Nagao J., Nishiyama Y., Setoguchi T.,Kim H.D.,Yu S.,2013,Numerical Study on Transonic Flow with Local Occurrence of Non-Equilibrium Condensation, Open Journal of Fluid Dynamics, 3,pp. 42-47,http://dx.doi.org/10.4236/ojfd.2013.32A007   
[10]Pruppacher H.R.，Klett J.D.，1980，Microphysics of Clouds and Precipitation, D.Reidel Publishing Company, Dordrecht, Boston,London.   
[11]Sajben,M.,Kroutil, J.C.,1981,Effect of Initial Boundary-Layer Thickness on Transonic Diffuser Flow,AIAA Journal, Vol.19,pp.1386-1393   
[12] Schnerr,G.H.,and Dohrmann,U.,199o,Transonic flow around airfoils with relaxation and energy supply by ho mogeneous condensation.AIAA Journal,28,pp.1187-1193   
[13] Schnerr G.H.,Mundinger G.,1993,Similarity,drag,and lift in transonic flow with given internal heat addition, Euro.J.Mech.，B/Fluids,Vol.12,No.5,pp.597-611, 1993597-611   
[14] Schnerr,G.H.,and Dohrmann,U.，1994，Drag and lift in non-adiabatic transonic flow. AIAA Journal, 32, pp. 101-107   
[15] Wroblewski W.,Dykas S.,Gepert A.,2009,Steam condensing flow modelling in turbine channels,International Journal of Multiphase Flow,35(6),pp.498-506