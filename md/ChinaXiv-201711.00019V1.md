# Effects of Acoustic Barriers and Crosswind on the Operating Performance of Evaporative Cooling Tower Groups

DANG Chao1,2, JIA Li1,2\*, YANG Lixin1,2

1. InstituteofThermal Engineering,SchoolofMechanical,ElectronicandControlEngineering,Beijing JiaotongUniversity, Beijing100044, China   
2.Beijing Key Laboratory of Flowand Heat Transfer of Phase Changing in Micro and Small Scale,Beijing100044, China

Most evaporative cooling towers are aranged on building roof due to the limitation of space and noise,and acoustic barriers are always installed around cooling towers in practical applications.The existence of acoustic barriers and crosswind may affect the recirculation phenomenon which is directly related to the operating performance of cooling towers.In this study,a physical and mathematical computation model is proposed to research the crosswind and distance between acoustic barriers and inlet ofcooling towers.Both sensible and latent heat are considered inthis research.The reflux flow rate and performance ratio are obtained to evaluate the recirculation and operating performance,respectively.The results show that the higher the crosswind velocity,the larger the reflux flow rate,and the lower the performance ratio of cooling tower groups.For high crosswind velocity, the presence of acoustic barriers is useful to inhibit reflux and improve operating performance,especially for $I C E$ （20 cooling tower groups. In addition, the optimum values are recommended for $L i B r / I C E$ cooling tower groups in theresearch cases The variationof reflux flow rate and performance ratio with the acoustic barrers’distance presents a parabolic tendency.

# Keywords: evaporative cooling tower groups,acoustic bariers,crosswind,reflux flow,operating performance

# Introduction

The cooling system of power plant has a great impact on the capacity and operational efficiency of the power plant.Numerous works related to the cooling system of power plant have been reported in a wide variety of scientific literatures,particularly with regard to the indirect air-cooling (IDAC) system [1]. L.J. Yang et al. [2] carefully discussed the wind effect on the performance and characteristics of air-cooled condensers (ACCs） by experimental and numerical methods. G. Barigozzi et al. [3] optimized the waste-to-energy cogeneration plant to

# Nomenclature

reach the maximum net power output, considering the combined wet and dry units of the cooling system. Hongfang Gu [4] investigated the mechanism and optimization of wind-break structures for IDAC towers.

However, the high operating costs and the corresponding hit on plant efficiency associated with IDAC systems make it an unsatisfactory option [5]. The mechanical draft evaporative cooling towers become increasingly popular for power plant cooling systems owing to the higher heat exchange efficiency as well as the lower water consumption [6]. However,most cooling towers have to be arranged on building roofs where have

# Acronyms

<html><body><table><tr><td>A</td><td>Area (m²)</td><td>IDAC</td><td>Indirect air-cooling</td></tr><tr><td>Cp</td><td>specific heat at constant pressure (J/kg K)</td><td>LiBr</td><td>Lithium bromide</td></tr><tr><td>D</td><td>Kinematic diffusivity (m²/s)</td><td>ICE</td><td>Internal combustion engine</td></tr><tr><td>d</td><td>Moisture content (kg(vapor)/kg(dry air))</td><td>AB</td><td>Acoustic barriers</td></tr><tr><td>d'</td><td>Moisture content of saturated air (kg(vapor)/ kg(dry air))</td><td>RH</td><td>Relative humidity</td></tr><tr><td>h</td><td>Enthalpy (J/kg)</td><td>Greek symbols</td><td></td></tr><tr><td>h’</td><td>Enthalpy of saturated air (J/kg)</td><td></td><td>Turbulence dissipation rate (m²/s)</td></tr><tr><td>ht</td><td>The total enthalpy (J/kg)</td><td></td><td>Evaporation loss rate (-)</td></tr><tr><td>k</td><td>turbulent kinetic energy (m²/s²)</td><td>2</td><td>Volumetric porosity (-)</td></tr><tr><td>Ka</td><td>Mass transfer coefficient (kg/m³ s)</td><td>n</td><td>Performance ratio (%)</td></tr><tr><td>K,K2</td><td>Slpead inteetofeiatshi</td><td>μ</td><td>Dynamic viscosity (Pa s)</td></tr><tr><td>L</td><td>Theditoleetwenacousticbarsand</td><td>p</td><td>Density (kg/m³)</td></tr><tr><td>M</td><td>Molecular weight (kg/mol)</td><td>Subscripts</td><td></td></tr><tr><td>p</td><td>Pressure (Pa)</td><td>a</td><td>Air</td></tr><tr><td>q</td><td>Mass flow rate (kg/s)</td><td>atm</td><td>Atmosphere</td></tr><tr><td>q.</td><td>Volume flow rate of air (m³/s)</td><td>b1,b2</td><td>Reflux flow for the group of cooling tower itself and the other surrounding one</td></tr><tr><td>R</td><td>Universal gas constant (J/mol K)</td><td>C</td><td>Cooling tower</td></tr><tr><td>r</td><td>Latent heat of vaporization (J/kg)</td><td>f</td><td>Process fluid</td></tr><tr><td>Ss</td><td>Source term of sensible heat (J/m s)</td><td>fr</td><td>Fan region</td></tr><tr><td>SM</td><td>Source term of latent heat (kg/s²)</td><td>fl</td><td>Filing layer</td></tr><tr><td>t</td><td>Temperature（℃)</td><td>in</td><td>Inlet</td></tr><tr><td>tw</td><td>Temperature of spray water (℃)</td><td>m</td><td>Moist air</td></tr><tr><td></td><td>Dry-bulb temperature(℃)</td><td>out</td><td>Outlet</td></tr><tr><td>U</td><td>Velocity vectors (m/s)</td><td>W</td><td>Spray water</td></tr><tr><td>VTB</td><td>Volume of tower body (m³)</td><td>wv</td><td>Water vapor</td></tr><tr><td>V</td><td>Velocity (m/s)</td><td></td><td></td></tr></table></body></html>

limitedlandresourcesand somenoisereduction facilities like acoustic barriers are needed [7]. The operating performance of mechanical draft evaporative cooling towers might be affected by these facilities,which have direct impact on the expected benefits of projects because of investment quota. It is important to study the layout plan of noise reduction facilities as well as the operating performance of cooling towers whether technical or economic reasons [8,9].

There are kinds of theoretical models of evaporative cooling process for both design and system simulation. Wojciech Zalewski and Piotr Antoni Gryglaszewski[10] developed a mathematical model of heat and mass transfer process in evaporative condensers which consists of four ordinary differential equations with their boundary conditions and some associated algebraic equations.A general non-dimensional mathematical model for description of all types of evaporative cooling deviceswas presented by Boris Halasz [11].He made the differential equations transformed to a pure non-dimensional form by the introduction of dimensionless coordinates and parameters.The description of the entire process becomes very simple. Sergey Anisimov and Pascal Stabat [12,13] adopted the e-NTU method to the indirect-contact evaporative cooling tower behavior and introduced only two parameters including air-side and water-side heat-transfer coefficients that allow one to estimate energy and water consumptionsunderdifferentoperatingconditions. Based on theoretical research,numerous studies about nature or mechanical draft cooling tower were reported in scientific literatures [14-16].

Recently, some researchers studied about multiple cooling towers or cooling tower groups with the crosswind and wind break wall. A. Chahine et al. [17] and Yuanshen Lu et al.[18] investigated the effect of crosswind on the operating performance and plume dispersal of cooling towers by the experiments and numerical simulation. They found that the crosswind sometimes may cause recirculation phenomenon and decrease operating performance at the same time.Z. Zhai et al.[19] and Y. Lu et al. [2O] used wind break wall within the cooling towers which reverse the negative effect of crosswind.

But rare works in related to the impact on cooling tower groups with external walls or obstacles were reported which often occur in real cases. The phenomenon, such as low pressure,recirculation which means that the exit flow re-enters the inlet of cooling tower, and vortex flow generated around the cooling towers are always related with the cooling tower shape and the external walls or obstacles around towers as well as ambient conditions like crosswind. J.H.Lee et al.[21] considered the recirculation phenomenon and plume generation of a row of cross-flow type forced draft cooling towers surroundedbyobstacles,and mostof the results focused on the moisture fraction.

The present paper numerically studied the operating performance and recirculation phenomenon as well as the internal and external flow of two cooling tower groups surrounded by acoustic barriers with ventilating shutters in the lower position. Two main source terms representing the latent and sensible heat of each cooling tower were investigated, which are great meaningful for the discussion of operating parameters of cooling towers.The evaporation of spray water and sensible heat were obtained from the simulation results as well as the enthalpy and moisture content at the inlet of cooling towers.The effects of the distance between the acoustic barriers and cooling towers and the crosswind velocity were studied.

# Theoretical model

Two groups of cross-flow cooling towers were studied in this research. The water vertically fell from the upper part of the tower and the air horizontally flowed through the filler layers.The air and water flow were orthogonal in the cooling tower. Cross-flow cooling towers are widely used in the field of generation and air conditioning with many advantages,such as energy-saving,lower pressure and wind resistance, etc..Besides,multiple tower can be placed on constructing basis freely built according to building shape and started with single or multiple tower according to the desired temperature [22].

# Heatand mass transfer process [1o,13,23]

The heat and mass transfer process of cooling tower can be divided into two stages: heat transfer from the cooled process fluid (herein refers to water） inside the tube to the water film outside the tube,and mass diffusion process to promote heat transfer by the latent heat of vaporization from the water film to the forced convection air outside the tube.It is a complex coupling of heat and mass transfer process [24,25].The specific implementation process is that the heat transfer through the tube wall from the fluid inside the tube to the water film formed by the spray water outside of the tube.After that, heat and mass transfer between the humid air in the boundary layer near the water film and the main air flow of the cooling tower should be considered.Finally, the hot and humid air is driven into the atmosphere by the fan [26].

# Assumptions

In order to simplify the theoretical model, the following assumptions are assumed:

1.The main air of the cooling towers have the same state with the inlet air; 2.The temperature of the saturated humid air in the boundary layer near the water film is the same as the water film; 3.The inlet air has the same state with the ambient air when the cooling tower is in an ideal operating state at rated conditions (no crosswind,no acoustic barriers and no recirculation).

# Modelofheatandmasstransfer

Heat and mass transfer process for each cooling tower occurs between the main air and spray water outside the tubes. The total heat exchange of cooling towers including sensible heat and latent heat is simplified to act on the tower body portion shown in Fig. 2.

$$
{ \cal Q } = { \cal Q } _ { S } + { \cal Q } _ { L }
$$

Where, $\boldsymbol { \mathcal { Q } }$ can be expressed as the heat loss of process fluid inside the tubes of cooling towers,because it is equal to the total heat exchange occurred between the main air and spray water outside the tubes.

$$
Q = q _ { f } \cdot c _ { P _ { f } } \cdot ( t _ { f , o u t } - t _ { f , i n } )
$$

Where, $q _ { _ { f } }$ is the mass flow rate of the process fluid, and $t _ { f , }$ out, $t _ { f , i n }$ represent the outlet and inlet temperature of the process fluid, respectively.

The heat obtained by the air outside the tube, i.e, the sensible heat between the main air and the saturated air in the boundaryis defined as:

$$
\mathcal { Q } _ { S } = K a \cdot ( h ^ { \prime } - h ) \cdot V _ { \mathrm { T B } }
$$

Where, $K a$ is the mass transfer coefficient between the water film and air,and $h _ { \mathrm { ~ , ~ } h } ^ { \prime }$ represent the enthalpy of saturated air in the boundary and main air, respectively. $V _ { T B }$ is the volume of tower body in the simplified model of cooling towerwhere heat and mass transfer occurs.

The heat loss of water film outside the tube which denotes the latent heat between the main air and the saturated air in the boundaryreads as:

$$
\begin{array} { r l } & { \boldsymbol { Q } _ { L } = \boldsymbol { q } _ { f } \cdot \boldsymbol { c } _ { P _ { f } } \cdot ( \boldsymbol { t } _ { f , o u t } - \boldsymbol { t } _ { f , i n } ) - K \boldsymbol { a } \cdot ( \boldsymbol { h } ^ { \prime } - \boldsymbol { h } ) \cdot \boldsymbol { V } _ { \mathrm { T B } } } \\ & { \quad = \boldsymbol { q } _ { f } \cdot \boldsymbol { \varphi } \cdot \boldsymbol { r } } \end{array}
$$

Where, $\varphi$ and $r$ represent the evaporation loss rate of cooling tower and latent heat, respectively.

According to the above assumptions and heat and mass transfer model,the mass transfer coefficient between the water film and air using the parameters of cooling tower under the rated conditions can be obtained, as shown in Table 1.

Table1Rated conditions of each cooling tower   

<html><body><table><tr><td>Parameter</td><td>LiBr cooling tower</td><td>ICEcoolingtower</td></tr><tr><td>tdb</td><td>31</td><td>31</td></tr><tr><td>RH</td><td>56</td><td>56</td></tr><tr><td>t.in</td><td>38</td><td>95</td></tr><tr><td>t.out</td><td>32</td><td>74</td></tr><tr><td>9</td><td>755</td><td>184</td></tr><tr><td>Pr</td><td>162.64</td><td>207</td></tr><tr><td></td><td>0.988</td><td>3.44</td></tr><tr><td>tw</td><td>33</td><td>35</td></tr></table></body></html>

# Numerical simulation

Two cooling tower groups surrounded by acoustic barriers with ventilating shutters in the lower position were numerically simulated and the standard $k { - } \varepsilon$ model was selected. Constants of the turbulence model were given in Table 2.The distance between the acoustic barriers and cooling towers as well as the crosswind are taken into consideration.

Table 2 Constants of standard $k { - } \varepsilon$ turbulence model   

<html><body><table><tr><td>k</td><td>E</td><td>Cμ</td><td>Ce1</td><td>Ce2</td><td></td><td></td></tr><tr><td>0.41</td><td>9.793</td><td>0.09</td><td>1.44</td><td>1.92</td><td>1.0</td><td>1.3</td></tr></table></body></html>

# Geometric model

Fig.1 illustrates the geometry and mesh configuration of 3D computational domain with acoustic barriers. The layout of cooling tower groups and acoustic barriers with ventilating shutters were given in Fig.1. The main geometric dimensions and crosswind direction also could be obtained.Seven different distances between the inlet of cooling tower and acoustic barriers from $1 \mathrm { ~ m ~ }$ to $1 7 \mathrm { ~ m ~ }$ were simulated and analyzed in this study.The crosswind velocities were of $0 ~ \mathrm { m / s }$ ， $2 . 6 \ \mathrm { m / s }$ ， $6 . 6 ~ \mathrm { m / s }$ and $1 0 . 6 ~ \mathrm { m / s }$ with the wind direction at NE and the atmosphere temperature of $3 1 ^ { \circ } \mathrm { C }$ . Those cases with no acoustic barriers were also simulated for comparison.

# Governing equations

The continuity equation can be expressed as:

$$
\nabla \cdot ( \rho _ { m } \pmb { U } ) = 0
$$

Where, $\rho _ { m }$ and $U$ represent the density and velocity vectors ofhumid air,respectively.

![](images/d90c3e745f02e8b2056fe67f25e62bfbc9b410ec498811a052d43955303d4af4.jpg)  
1.Ventilating shutter; 2.LiBr cooling tower group;3.ICE cooling tower group; 4.Computational domain; 5.Acoustic barrier

![](images/c1646f65bcd47f6d6cabf5fd1f86c8385a155c8b8d4bc086541fc60110e1c4af.jpg)  
Fig.1 Geometry and mesh configuration of computational domain with acoustic barriers   
1. Fan region $( S _ { f r } )$ ; 2.Filling layer $( S _ { f l } )$ ; 3.Tower body $( S _ { S } \& S _ { M } )$   
Fig.2Simplified model of cooling tower

The momentum equation is written as:

$$
\nabla \cdot ( \rho _ { m } \pmb { U } \times \pmb { U } ) = - \nabla p ^ { \prime } + \nabla \cdot \pmb { \tau } + S _ { M }
$$

Where, $p ^ { \prime }$ is the modified pressure and $\tau$ is the stress tensor, which is related to the strain rate by:

$$
\boldsymbol { \tau } = \mu _ { \mathrm { e f f } } ( \nabla U + ( \nabla U ) ^ { T } )
$$

The term $S _ { M }$ represents the external forces; $\mu _ { e f f }$ is the effective viscosity accounting for turbulence and $\mu _ { t }$ is turbulent viscosity. Their relationship is as follows:

$$
\mu _ { \mathrm { e f f } } = \mu + \mu _ { \mathrm { t } }
$$

$$
\mu _ { \mathrm { t } } = C _ { \mu } \rho \frac { k ^ { 2 } } { \varepsilon }
$$

Where, $k$ and $\varepsilon$ represent the turbulent kinetic energy per unit mass and turbulence dissipation rate,respectively. And $C _ { \mu }$ is the turbulence constant of standard $k$ -εmodel shown in Table 2.

The energy equation is:

$$
\nabla \cdot ( \rho \boldsymbol { U } h _ { \mathrm { t } } ) = \nabla \cdot ( \lambda \nabla T ) + \nabla \cdot ( \boldsymbol { U } \cdot \boldsymbol { \tau } ) + \boldsymbol { U } \cdot \boldsymbol { S } _ { \boldsymbol { M } } + \boldsymbol { S } _ { E }
$$

$S _ { E }$ is the source term of energy and $h _ { \mathrm { t } }$ is the total enthalpy which is in related to the static enthalpy $h ( T , p )$ by:

$$
h _ { \mathrm { t } } = h + { \frac { 1 } { 2 } } { \boldsymbol { U } } ^ { 2 }
$$

# Simplified model of cooling tower

Each cooling tower of two groups studied in this paper wasoperating at rated conditions,but the presence of obstaclesandcrosswindaffectedtheairflowrateand air state at the inlet/outlet of cooling towers [20,27-29]. Simplified model of cooling tower consisted of three parts including fan region, filling layer and tower body, as shown in Fig.2.It also described the acting positions of source terms and the dimensions of $L i B r / I C E$ cooling tower. Several source terms effected on every part of the cooling tower model were defined.Heat and mass transferprocess for each cooling tower occurred in the tower body portion.

# The source term of sensible heat

The sensible heat exchange of cooling tower can be defined as a source term of energy equation acting on the tower body:

$$
S _ { S } = K a \cdot ( h ^ { \prime } - h _ { c , i n } )
$$

Where, $h _ { c , i n }$ is the enthalpy at the inlet of cooling tower in related to the dry bulb temperature and moisture content of the inlet air, i.e., $h _ { c , i n } { = } \mathrm { f } ( t _ { c , i n } , d _ { c , i n } )$ ,which can be obtained by the following empirical formula [30]:

$$
h _ { c , i n } { = } 1 0 0 5 t _ { c , i n } + d _ { c , i n } \cdot ( 2 5 0 1 0 0 0 + 1 8 6 0 t _ { c , i n } )
$$

# The source term of latent heat

The latent heat exchange of cooling tower is equal to the spray water evaporation heat.An additional variable ${ { q } _ { _ { w v } } }$ (scalar) acting on the transport equation is defined to express the evaporation rate of spray water which is solved on the basis of each unit cell.The scalar transport equation is as follows:

$$
\nabla \cdot ( \rho _ { m } U q _ { w \nu } ) = \nabla \cdot ( \rho _ { m } D _ { q _ { w \nu } } \nabla q _ { w \nu } ) + S _ { q _ { w \nu } }
$$

Where, $D _ { q _ { w \nu } }$ denotes the kinematic diffusivity of water vapor and $\rho _ { m }$ is the density of humid air described by the following expression [21]:

$$
\rho _ { m } = \frac { p \cdot ( \frac { 1 } { 1 + d _ { c , i n } } M _ { a } + \frac { d _ { c , i n } } { 1 + d _ { c , i n } } M _ { w } ) } { R \cdot ( t _ { c , i n } + 2 7 3 . 1 5 ) }
$$

Where, $R$ is the universal gas constant; $\boldsymbol { M _ { a } } , \ M _ { \boldsymbol { w } }$ represent the molecular weight of dry air and water, respectively.

The evaporation capacity of spray water is defined as a source term of scalar transport equation effect on the tower body:

$$
S _ { M } = \frac { q _ { a } \cdot [ d ^ { ' } - d _ { c , i n } ] } { V _ { \mathrm { T B } } } \cdot A _ { o u t } \cdot \nu _ { o u t }
$$

Where, $\boldsymbol { q } _ { a _ { } }$ is the mass flow rate of dry air; $d ^ { \prime }$ denotes the moisture content of saturated air near the water film; $A _ { o u t } , \nu _ { o u t }$ represent the area and mean velocity at the outlet

of cooling tower, respectively; $d _ { c , i n }$ is the moisture content at the inlet of cooling tower obtained by the following expression:

$$
d _ { c , i n } = d _ { a t m , i n } + \frac { q _ { w \nu , b 1 } + q _ { w \nu , b 2 } } { q _ { a } }
$$

Where, ${ q } _ { { _ { w \nu , b I } } } , { q } _ { { _ { w \nu , b 2 } } }$ represent the reflux flow of water vaporby the group of cooling tower itself and other surrounding groups, respectively. $d _ { a t m , i n }$ is the moisture content at the inlet of cooling tower having the same relative humidity with atmosphere,and it is a function of dryair temperature at the inlet of cooling tower and relative ambient humidity, i.e., $d _ { a t m , i n } { = } \mathrm { f } ( t _ { c , i n } , R H _ { a t m } )$ ：

0.034 0.032 RH=86% Regression line 0.028 RH=76% 0.026 0.024 RH=66% 0.022 0.020 RH=56% 0.018 0.014 RH=46% 0.012 0.010 上 上 上 ⊥ 1 上 30 31 32 33 34 35 36 37 tcin(℃)

The relationship of $d _ { a t m , i n } { = } \mathrm { f } ( t _ { c , i n } , \ R H _ { a t m } )$ can be obtained using the database of Digital psychrometric Chart through which the moisture content data corresponding to the dry air temperature at different relative humidity is extracted andthe data is fitted as shown in Fig.3.The fitting relationship is defined as follows:

$$
d _ { a t m , i n } { = } K _ { 1 } t _ { c , i n } + K _ { 2 }
$$

Where, $K _ { I } , K _ { 2 }$ is the slope and intercept of the fitting relationship.

# The source term of filling layer

Considering the presence of fillers in a real cooling tower which will enhance the flow resistance and result in pressure loss and flow loss,the simplified model pre sented in this paper contains filling layer portions placed on both sides of the inlet of cooling tower. Filling layers can be regarded as porous medium using the square resistance coefficient of directional loss model to express:

$$
\displaystyle S _ { f l } = K _ { \mathrm { l o s s } } \frac { \rho _ { m } } { 2 \gamma ^ { 2 } }
$$

$$
K _ { \mathrm { l o s s } } = \frac { \xi } { D _ { \mathrm { e } } } + \frac { \zeta } { L _ { \mathrm { e } } }
$$

Where, $\gamma$ denotes the volumetric porosity of the filling

layer; $\xi$ and $\zeta$ represent the friction coefficient and the local resistance coefficient, respectively. $D _ { e }$ is equivalent diameter and $L _ { e }$ is the flow length.

# The source term of fan region [31]

Because the groups of mechanical draft cross-flow cooling tower studied were all driven by the fan at the top of tower body, fan model which could be set as a general momentum source term was introduced in the present paper:

$$
S _ { f r } = \frac { P _ { f r } } { L _ { f r } }
$$

$$
S _ { f r , c o e f } = { \frac { q _ { \mathrm { v } , a } \cdot \rho _ { m } } { 3 6 0 0 \cdot V _ { f r } } }
$$

Where, $P _ { f r }$ denotes the total pressure of fan and $\boldsymbol { q } _ { \nu , a }$ is the volume flow rate of air through cooling tower; $L _ { f r }$ and $V _ { f r }$ are the height and volume of fan region, respectively.

# Boundary conditions

A cylindrical region was selected as a whole computational domain to represent the atmospheric condition. The height and diameter of the region were $1 8 ~ \mathrm { m }$ and 80 m,respectively. The crosswind velocity and temperature were used as the inlet boundary conditions defined on the side of the cylinder in the inflow direction.Opening boundary conditions acting on the other side and top of the cylinder as the outlet flow boundary were defined using the static pressure and temperature to describe the atmospheric conditions.Besides,solid lines in the following figures indicated these cases with acoustic barriers,and dash lines denoted the comparing cases without acoustic barriers.

# Results and analysis

In the present paper, seven different distances between the inlet of cooling tower and acoustic barriers of $1 \mathrm { m } , 3 \mathrm { m }$ $5 \ \mathrm { m } , 7 \ \mathrm { m } , 9 \ \mathrm { m } , 1 3 \ \mathrm { m }$ and $1 7 \mathrm { m }$ were investigated as well as the crosswind wind velocity of $0 ~ \mathrm { m / s }$ 5 $2 . 6 ~ \mathrm { m / s }$ ， $6 . 6 ~ \mathrm { m / s }$ and $1 0 . 6 \ \mathrm { m / s }$ . Furthermore, the cases without acoustic barriers at different crosswind velocities were also simulated as a comparison with the above.Total of 32 cases were studied and discussed in this paper. The mean parameters of two groups cooling tower and streamlines on a representative cross section were analyzed as follows.

# Effect on the reflux flow rate

The scalar values at the inlet of cooling tower group could be obtained to represent the reflux flow rate of water vapor,and the evaporation rate of spray water have been defined as a scalar acting on transport equations for both $L i B r$ and $I C E$ cooling tower. The reflux flow consists of two parts,namely, their own reflux and the other group's reflux.It can directly reflect the strength of re circulation phenomenon.

Fig.4 shows the reflux flow rate in different cases for $L i B r$ cooling tower group. Overall, the reflux flow rate increased with crosswind velocity whether or not there were acoustic barriers.Nevertheless,the increasing rate of reflux flow with $_ { A B }$ decreased along with the rising of crosswind velocity in contrast with the cases without $_ { A B }$ (Table 3). The reason is that the augmentation of crosswind velocity leads to the deterioration of flow conditions at the inlet and outlet of cooling towers and the existence of acoustic barriers sometimes may play a blocking role for the crosswind. For $v _ { f } { = } 0 ~ \mathrm { m / s }$ and $\nu _ { f } { = } 2 . 6 ~ \mathrm { m / s }$ the reflux flow rate decreased with the augmentation of distance $L$ and then remained nearly constant after $\scriptstyle { L = 9 \mathrm { ~ m ~ } }$ However, for $\nu _ { f } = 6 . 6 \ \mathrm { \ m / s }$ and $\nu _ { f } = 1 0 . 6 \ \mathrm { m / s }$ ，the reflux flow rate increased with the distance after $L { = } 9 \mathrm { ~ m ~ }$ . A parabolic tendency with a minimum point was shown. This means that the reflux flow rate is larger than the cases without acoustic barriers under the same circumstances when acoustic barriers are close to the inlet of $L i B r$ cooling tower. The limited surrounding space near the inlet of cooling towers will result in the reduction of air flow rate as well as the generation and change of vortex. Comparing to the case of $\nu _ { f } = 1 0 . 6 ~ \mathrm { m / s }$ without $\boldsymbol { \mathcal { A } } \boldsymbol { B }$ ，the corresponding circumstance exhibited good phenomenon that acoustic barriers play a positive role in suppressing reflux.

The influence of the crosswind velocity on reflux flow rate for $I C E$ cooling tower group(Fig. 5） was roughly consistent with the above-mentioned one.But the reflux flowrate seemed to be more sensitive to acoustic barriers In other words, the reflux flow rate significantly reduced for $\nu _ { f }$ varying from $2 . 6 ~ \mathrm { m / s }$ to $1 0 . 6 ~ \mathrm { m / s }$ when the distance of acoustic barriers is more than $1 \mathrm { ~ m ~ }$ .The acoustic barriersplayed a positive role in these cases.In addition, the reflux flow rate decreased with the distance before $L { \le } 7 { \mathrm { m } }$ and then increased with $L$ .The minimum reflux flow rate occurred at $L { = } 7 ~ \mathrm { m }$

![](images/a95c1e002bb137f86fc002e2fc9a9ffaa65c311de9e405e49f90a67c98fe7b30.jpg)  
Fig.4Reflux flow rate versus the distance and crosswind velocity for $L i B r$ cooling tower group with $_ { A B }$

Table 3 Reflux flow rate for $L i B r / I C E$ cooling tower group without $_ { A B }$   

<html><body><table><tr><td rowspan="2"></td><td colspan="4">Reflux flow rate (kg/s)</td></tr><tr><td>0 m/s</td><td>2.6 m/s</td><td>6.6 m/s</td><td>10.6 m/s</td></tr><tr><td>LiBr cooling tower group</td><td>0.01023</td><td>0.08299</td><td>0.20599</td><td>0.46553</td></tr><tr><td>ICE cooling tower group</td><td>6.3356e-4</td><td>0.05885</td><td>0.09828</td><td>0.14524</td></tr></table></body></html>

![](images/391d2059fbfa31e70e03a6d0a217a48845847da00806157d83f335f26dcc8d41.jpg)  
Fig.5Reflux flow rate versus the distance and crosswind velocity for $I C E$ cooling tower group with $_ { A B }$ （204号

The operating performance of cooling towers would be directly affected by recirculation phenomenon caused by the suction at the inlet and the position of vortex and low pressure.On the one hand, the moisture content of theinletair increased with the reflux flow rate when the air flow was constant.This means the rise of actual relative humidity at the inlet,which would deteriorate the evaporation rate of spray water andled to a sharp decline of sensible heat of cooling towers (Eq.(l6),(17） and (18)).On the other hand, the reflux flow also resulted in the rising temperature of the inlet air. The decrease of sensible heat would be caused by the augmentation of enthalpy of main air due to the rising temperature and moisture content (Eq.(12),(13)),though the sensible heat accounted for only a small proportion of the total heat.In short,refluxflowisanunfavorable factor for the operating performance of cooling tower groups.

# Effect on the performance ratio

It is not accurate and adequate to evaluate the operating performance of cooling tower groups simply by reflux flow rate.Some other impact factors,such as the air flow rate determined by acoustic barriers and crosswind, can also affect the evaporation of spray water (Eq.(17)). Hence,the parameter of performance ratio to represent the operating performance of cooling tower groups was suggested in this paper.Itis defined as follows:

$$
\eta { = } \frac { \mathcal { Q } _ { \mathrm { r e a l } } } { \mathcal { Q } _ { \mathrm { r a t e d } } }
$$

Where, $Q _ { \mathrm { r a t e d } }$ is the rated total heat exchange of cooling tower groups under the rated conditions shown in Table 1; $\scriptstyle Q _ { \mathrm { r e a l } }$ denotes the actual total heat exchange of those numerical cases,which can be obtained through the post processing.

Fig.6 and Fig.7 show the performance ratio of $L i B r$ and $I C E$ cooling tower groups,respectively. There are some similarities between the two figures.With the augmentation of the distance $L$ ,the performance ratios both increased at first and then decreased when the crosswind velocities varied from $2 . 6 ~ \mathrm { m / s }$ to $1 0 . 6 ~ \mathrm { m / s }$ .The transition points of the two cooling tower groups were occurred when the distances were $9 \mathrm { ~ m ~ }$ and $7 ~ \mathrm { m }$ ,respectively.As for $\nu _ { f } { = } 0 ~ \mathrm { m / s }$ ,the performance ratios both increased with the distance $L$ and then remained a constant after their transition point.The changes in acoustic barriers’distance obviously alter the flow field around cooling tower groups,due to the generation and changing position of vortex as well as the low pressure region caused by crosswind.When the crosswind did not exist, the suction of the cooling towers held a dominant position,and the performance ratios approximately remained a constant after transition point.In addition, the performance ratios both decreased with the rise of crosswind velocity no matter whether there were acoustic barriers or not.The decrease rates of the two groups both increased with the increase of crosswind velocity when the acoustic barriers did not exist.

![](images/7d293eba293db970dc4ae9a7207ca2f7fe664198dfc6c9eb9b3243cf38fb2508.jpg)  
Fig.6Performance ratio versus the distance and crosswind velocity for $L i B r$ cooling tower group with $_ { A B }$ （204

![](images/3164e42c635d54169343ced7f8007ab01c4bd8c3339291f83aa64e3c027e03ab.jpg)  
Fig.7Performance ratio versus the distance and crosswind velocity for $I C E$ cooling tower group with $_ { A B }$

But there are also some differences between the two figures.For example, the performance ratio of $L i B r$ cooling tower group in most cases with $_ { A B }$ was lower than the corresponding cases without $_ { A B }$ for $\nu _ { f } { = } 0 ~ \mathrm { m / s }$ ， $\nu _ { f } { = } 2 . 6$ $\mathrm { m / s }$ and $\nu _ { f } = 6 . 6 ~ \mathrm { m } / \mathrm { s }$ . The existence of acoustic barriers hinders the operating performance of cooling towers. However, contrary to the previous situation,acoustic barriers played a positive role in improving the operating performance of ICE cooling tower group compared to the corresponding cases without $_ { A B }$ (Table 4).This indicates that it is easier for the $I C E$ cooling tower group to be affected by crosswind.Moreover, the performance ratio was not completely in accordance with the reflux flow rate such as the comparison of cases for $\nu _ { f } = 1 0 . 6 \ \mathrm { m / s }$

Fig.8 displays the streamlines of different cases on a representative cross section shown in Fig.1.It is visualized to describe the fluid flow situation around cooling towers through the streamlines.It is useful to explain the variant of operating performance qualitatively. Vortexes were generated in the low pressure region between the two cooling tower groups due to the high-speed flow at the outlet shown in the red ellipse of Fig. 8 (al). Comparing (b1), (b2) and (b3) of Fig.8,it is obvious that the relatively superior flow field occurred when the distance $L$ was $9 \mathrm { ~ m ~ }$ For $L = 1 \mathrm { ~ m ~ }$ ，there was not enough space around the inlet of cooling towers leading to the limita tion of air flow rate.The space was enough for $L = 1 7 ~ \mathrm { m }$ and low pressure region was formed when the crosswind blown over acoustic barriers. The vortex generated around cooling towers resulted in the rise of reflux flow and decrease of operating performance.In addition,it is easy to find that the existence of crosswind deteriorated the flow field for both the two cooling tower groups comparing the left and right sides of Fig. 8.ICE cooling tower group is more sensitive with crosswind due to the relatively small size.Even some tiny change can have a greater impact on it than the other one.

Table 4 Performance ratio for $L i B r / I C E$ cooling tower group without AB   

<html><body><table><tr><td rowspan="2"></td><td colspan="4">Performance ratio</td></tr><tr><td>0 m/s</td><td>2.6 m/s</td><td>6.6 m/s</td><td>10.6 m/s</td></tr><tr><td>LiBr cooling</td><td>0.9839</td><td>0.9505</td><td>0.8834</td><td>0.7701</td></tr><tr><td>tower group ICE cooling tower group</td><td>0.9775</td><td>0.8480</td><td>0.6787</td><td>0.4450</td></tr></table></body></html>

![](images/3a3e9e2dc6af2c9d402e92f5d390e9acf5d702ad7ba91f93a4bfff8a07fd87c0.jpg)  
Fig.8Streamlines on certain cross section at different crosswind velocity

# Conclusions

The recirculation phenomenon and operating performance of two groups cooling tower were investigated in the present study.The effects of crosswind velocities and distances between acoustic barriers and inlet of cooling towers were considered. The reflux flow rate and performance ratio were chosen as the evaluation criterion for recirculation and operating performance, respectively. Some results were obtained.

The recirculation and operating performance are strongly affected by crosswind velocity. The higher the crosswind velocity, the larger the reflux flow rate,and the lower the performance ratio of cooling tower groups, especially when there are no acoustic barriers.

The variation of reflux flow rate and performance ratio with the distance of acoustic barriers presents a parabolic trend. There are optimum values of the distance in this study for $L i B r / I C E$ cooling tower groups appeared when $L = 9 ~ \mathrm { m }$ and $L = 7 ~ \mathrm { m }$ ,respectively.

The presence of acoustic barriers plays a positive role for inhibiting reflux and improving operating performance when the crosswind velocity is high,especially for ICE cooling tower groups.

The operating performance cannot reach the sitation under the rated conditions even without crosswind and acoustic barriers. The vortexes have been already generated between the two groups cooling tower.

# References

[1]G.F. Hundy,A.R. Trott,T.C.Welch.: Chapter 6 - Condensers and Cooling Towers.Refrigeration and AirConditioning (Fourth Edition), pp.74-90,(2008).   
[2]L.J. Yang, X.Z. Du, Y.P. Yang.: Wind effect on the thermo-flow performances and its decay characteristics for air-cooled condensers in a power plant,International Journal of Thermal Sciences,vol.53,pp.175-187,(2012).   
[3]G. Barigozzi,A.Perdichizzi,S.Ravelli.: Performance prediction and optimization of a waste-to-energy cogeneration plant with combined wet and dry cooling system. Applied Energy,vol.115,pp.65-74,(2014).   
[4]Hongfang Gu,Haijun Wang,Yuqian Gu, Jianan Yao.:A numerical study on the mechanism and optimization of wind-break structures for indirect air-cooling towers, Energy Conversion and Management, vol.108, pp.43-49, (2016).   
[5]Lihua Liu, Xiaoze Du, Xinming Xi, Lijun Yang, Yongping Yang.: Experimental analysis of parameter influences on the performances of direct air cooled power generating unit, Energy, vol.56,pp.117-123,(2013). [6]Lei Chen, Lijun Yang,Xiaoze Du, Yongping Yang.: A novel layout of air-cooled condensers to improve thermoflow performances, Applied Energy, vol.165, pp.244-259. (2016).   
[7]Marshall Long.: 13-Noise in Mechanical Systems,Architectural Acoustics (Second Edition)， pp.495 - 528, (2014).   
[8]R.M. Elis.: Cooling tower noise generation and radiation, Journal of Sound and Vibration, vol.14,pp.171-182, (1971). [9]L. Schaudinischky,A. Schwartz.: Noise control of air conditioning cooling towers,Heat Transfer, pp.509-514, (1971).   
[10]Wojciech Zalewski, Piotr Antoni Gryglaszewski.: Mathematical model of heat and mass transfer processes in evaporative fluid coolers, Chemical Engineering and Processing, vol.36, pp.271-280,(1997).   
[11]Boris Halasz.: A general mathematical model of evaporative cooling devices,Revue Générale De Thermique, vol.37, pp.245-255,(1998).   
[12] Sergey Anisimov, Demis Pandelidis, Jan Danielewicz.: Numerical study and optimization of the combined indirect evaporative air cooler for air-conditioning systems, Energy, vol.80, pp.452-464, (2015).   
[13]Pascal Stabat, Dominique Marchio.: Simplified model for indirect-contact evaporative cooling-tower behavior, Applied Energy, vol.78,pp.433-451,(2004).   
[14]S.V. Bedekar, P. Nithiarasu, K.N. Seetharamu.: Experimental investigation of the performance of a counter-flow, packed-bed mechanical cooling tower, Energy， vol.23, pp.943-947,(1998).   
[15] M. Lemouari, M. Boumaza, A. Kaabi.: Experimental investigation of the hydraulic characteristics of a counter flow wet cooling tower, Energy, vol.36, pp.5815-5823, (2011).   
[16]D. Kang, R.K. Strand.: Modeling of simultaneous heat and mass transfer within passive down-draft evaporative cooling (PDEC) towers with spray in FLUENT, Energy and Buildings,vol.62, pp.196-209, (2013).   
[17]A.Chahine,P.Matharan,D.Wendum,L.Musson-Genon, R.Bresson, B.Carissimo.: Modeling atmospheric effects on performance and plume dispersal from natural draft wet cooling towers, Journal of Wind Engineering & Industrial Aerodynamics, vol.136,pp.151-164,(2015).   
[18] Yuanshen Lu, Zhiqiang Guan,Hal Gurgenci,Kamel Hooman, Suoying He,Desikan Bharathan.: Experimental study of crosswind effects on the performance of small cylindrical natural draft dry cooling towers, Energy Conversion and Management， vol.91， pp.238 - 248, (2015).   
[19] Z. Zhai, S. Fu.: Improving cooling efficiency of drycooling towers under cross-wind conditions by using windbreak methods，Applied Thermal Engineering,vol.26, pp.1008-1017,(2006).   
[20]Y. Lu, Z. Guan, H. Gurgenci, Z. Zou.: Windbreak walls reverse the negative effect of crosswind in short natural draft dry cooling towers into a performance enhancement, International Journal of Heat and Mass Transfer, vol.63, pp.162-170,(2013).   
[21]J.H. Lee, M. Moshfeghi, Y.K. Choi.: A numerical simulation on recirculation phenomena of the plume generated by obstacles around a row of cooling towers， Applied Thermal Engineering,vol.72,pp.10-19, (2014).   
[22] N.W. Kelly.: Kelly's Handbook of Crossflow Cooling Tower Performance, Neil.W. Kelly and Associates, Kansas City, Mo,(1976).   
[23]JM. Wu, X. Huang, H. Zhang.: Theoretical analysis on heat and mass transfer in a direct evaporative cooler, Applied Thermal Engineering,vol.29, pp.980-984,(2009).   
[24]Bourhan Tashtousha,Mahmood Tahat, Ahmed AlHayajneh, Victor A.Mazur，Doug Probert.: Thermodynamic behaviour of an air-conditioning system employing combined evaporative-water and air coolers,Applied Energy, vol.70,pp.305-319, (2001).   
[25]Nicholas P. Cheremisinoff, Nicholas P. Cheremisinoff.: Evaporative Cooling Equipment, Handbook of Chemical Processing Equipment, pp.65-93,(2000).   
[26]Stephen Hall.Cooling Towers.: Branan's Rules of Thumb for Chemical Engineers (Fifth Edition)，pp.182-189, (2012).   
[27]B.R. Becker, J.W.E. Stewart, T.M. Walter.: A numerical model of cooling tower plume recirculation,Mathematical and Computer Modelling, vol.12,pp.799-819,(1989).   
[28]L.J. Yang, M.H. Wang, X.Z. Du.: Trapezoidal array of air-cooled condensers to restrain the adverse impacts of ambient winds in a power plant，Applied Energy, pp.vol.99: 402-413,(2012).   
[29]A.F. Du Preez, D.G. Kroger.: Effect of wind on performance of a dry-cooling tower, Heat Recovery Systems & Chp, vol.13, pp.139-146,(1993).   
[30]J.A. Curry.: THERMODYNAMICS|Moist (Unsaturated) Air, Encyclopedia of Atmospheric Sciences,pp.2274-2278, (2003).   
[31] Zhihang Song.: Numerical cooling performance evaluation of fan-assisted perforations in a raised-floor data center, International Journal of Heat and Mass Transfr, vol.95, pp.833-842, (2016).