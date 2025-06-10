# Role ofa. Single .Shield in Thermocouple Measurements in Hot Air Flow

MA Hongwei, SHI Lei, TIAN Yangtao

National Key Laboratory of Science and Technology on Aero-Engines Collaborative Innovation Center of Advanced Aero-Engine School of Energy & Power Engineering,Beihang University,Beijing,1Oo191, China

To investigate the role ofa single shield on steady temperature measurementusing thermocouples in hot air flow, amethodology for solving convection,conduction,and radiation in one single model is provided.Inorder to compare with the experimental results,a cylindrical computational domain is established,which is the same size with the hotcalibration wind-tunnel.Inthe computational domain,two kinds of thermocouples,the bare-bead and the single-shielded thermocouples,are simulated respectively.Surface temperature distribution and the temperature measurement bias of the two typical thermocouples are compared.The simulation results indicate that: 1) The existence of the shield reduces bead surface heat flux and changes the direction of wires inner heat conduction ina colder surrounding; 2) The existence of the shield reduces the temperature measurement bias both by improving bead surface temperature and by reducing surface temperature gradient; 3)The shield efectively reduces the effct of the ambient temperature on the temperature measurement bias; 4) The shield effctively reduces the influence of airflow velocity on the temperature measurement bias.

# Keywords:single-shield,bare-bead thermocouples,temperaturemeasurement,fluid-solidconjugated heattranfer.

# Introduction

Thermocouples have been widely used to measure airflowtotal temperature in research and industry. Bare-bead thermocouples,with the advantages of convenience,low cost,robustness and fast response time,are probably the most common,and possibly the easiest to implement.However, the uncertainty associated with this measurement method may be enormous[1]. One main reason for the measurement uncertainty is radiative exchange between the bead junction and the surrounding environment[2-4]. This is the consequence of bare-bead thermocouples directly exposing to the measurement environment.

thermocouples due to radiative exchange,single-shielded thermocouples are increasingly used in many applications.A single-shielded thermocouple has a cylindrical tube enclosed in a bare-bead thermocouple.The gas to be measured enters shield from the shield entrance,exchanges heat with the thermocouple bead and then flows out along the shield exit.

In order to reduce the measurement error of bare-bead   

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>db</td><td>bead diameter(mm)</td><td>Dw</td><td>domain inlet diameter(mm)</td></tr><tr><td>dw</td><td>wire diameter(mm)</td><td>Ts</td><td>static temperature (K)</td></tr><tr><td>Lw</td><td>bare wire length(mm)</td><td>V</td><td>bead volume(m³)</td></tr></table></body></html>

In the past few decades,a significant amount ofworks has investigated the uncertainty of temperature measurement using bare-bead and single-shielded thermocouples.Blevins et al. developed a steady-state energy balance model to study the measurement error associated with bare-bead,single and double shielded aspirated thermocouple measurements[5,6]. The model provides a methodology to study the thermocouple measurement errortrend.Luo[7] compared the difference of the reading froma bare-bead thermocouple with that from a suctionpyrometer ina series of fire experiments.The results show that the reading from the bare-bead thermocouple could be more than $2 0 0 ^ { \circ } \mathrm { C }$ higher than that from the suction pyrometer. Brohez et al [8] performed the experiments using a two thermocouples probe for the radiation corrections of measured temperature. A two thermocouples probe of unequal diameters was proposed to correct the thermocouple readings.

<html><body><table><tr><td>ds1</td><td>shell outer diameter(mm)</td><td>Greek letters</td><td></td></tr><tr><td>ds2</td><td>shield outer diameter(mm)</td><td></td><td>Recovery factor</td></tr><tr><td>d</td><td>shield entrance diameter(mm)</td><td>0</td><td>Relative temperature deviation</td></tr><tr><td>dv</td><td>shield vent diameter(mm)</td><td>Subscripts</td><td></td></tr><tr><td>Tb</td><td>bead temperature(K)</td><td>cond</td><td>conduction</td></tr><tr><td>Tw</td><td>wall temperature(K)</td><td>conv</td><td>convection</td></tr><tr><td>Q</td><td>rate of heat transfer(W)</td><td>rad</td><td>radiation</td></tr></table></body></html>

As reviewed above,most scholars have made experimental studies or algebraic analysis on thermocouplesmeasurement，theglobal performance and total errors of thermocouples have been obtained. However, there are very fewstudiesavailableregardingthree dimensional modeling of a thermocouple. Compared with thesetwomethods，a three-dimensional numerical study is capable of accounting for the deviation and delivering the local air flow temperatures and velocities at any desired positions in the field.Kim and Hamins [9] developed a three-dimensional simplified model to evaluate the measurement bias focusingondoubleshieldedaspirated thermocouples.After compared with algebraic solutions,themeasurementuncertainty characterized with the indicated thermocouple temperature and surrounding temperature was given. Etemad[1O] performed a threedimensional numerical study on the bare-bead model without considering the conduction. The bare-bead thermocouple is simplified as a small solid spherical bead. The results show that radiation is responsible for the temperature difference which grows with both bead size and gastemperature but decreaseswith the Reynolds number.

In this paper, to study the role of shield in thermocouples high temperature measurements, a detailednumericalapproachwith consideration of realistic boundary condition is described. Unlike early 3-D thermocouple numerical models introduced many simplifications, themodelusedinthis investigation take all the main components of thermocouples into consideration.Therefore,a combined solution of the flow field， energy equations, conduction in the thermocouple and radiation between different surfaces is obtained in these simulations. The numerical method is confirmedbyexperimentalresults.The thermocouple temperature measurement bias is characterized with the surrounding temperature and airflow Mach number. The effect of shield on temperature distribution and temperature measurement bias are discussed.Hopefully the present study gives a better understanding about the difference of measurement bias caused by heattransferringbetweenthebare-bead thermocouples and the single-shielded thermocouples.

# Numerical Scheme

Athermocouplecalibration in ahot calibration wind tunnel has been done before this numerical study. The computational result is compared with the experimental data to validate the numerical method. The further investigations in the role of single shield in the hot airflow temperature measurement will be discussed then.

# The computational domain and grid description

The K-type bare-bead thermocouple model, illustrated in Fig.1,consists of a bare bead, dual-wire, and a probe shell whilethe single-shielded thermocouple is identical to the bare-bead thermocouple enclosed in a radiation shield as shown in Fig.2.

The bead $\left( \mathrm { d } _ { \mathrm { b } } \right)$ and wires $\mathrm { ( d _ { w } ) }$ have diameters of $1 . 5 \mathrm { m m }$ and $0 . 5 \mathrm { m m }$ respectively while the exposed wire length $( \mathrm { L } _ { \mathrm { w } } )$ is specified to $8 ~ \mathrm { m m }$ The shield has a $6 \mathrm { m m }$ outer diameter $\left( \mathbf { d } _ { \mathrm { s } 2 } \right)$ and 1mm wall thickness,which is the same as the shell $\left( \mathrm { d } _ { \mathrm { s } 1 } \right)$ . The shield entrance $( \mathrm { d _ { e } } )$ and vent $\mathrm { ( d _ { v } ) }$ diameter are $4 ~ \mathrm { m m }$ and $2 ~ \mathrm { m m }$ respectively and the shield entrance-to-vent area ratio is 4.

The computational domain is composed of a geometry same as the test section of the hot calibration wind-tunnel and ahybrid gridis used in the domain,which are shown in Fig.3.The domain inlet diameter is 20oO times of the bead diameter. The bead of thermocouple model is located in the axial line of the computational domain. The distance between thermocouple bead center and the inlet is one time the wind-tunnel diameter, while the distance between thermocouple bead center and the outlet is two times.

Unstructured grid is employed in the region surrounding the probe,and the O-type grid is used for the other regions. Meanwhile,the size function [11] is applied to ensure the well stitching between the structured grid and unstructured grid.The $\mathbf { y } +$ values remain about 1 which met the enhanced wall function. In all cases, the grid skewness and aspect ratios are kept within reasonable bounds.

![](images/a526b6f35adfae00bf801380df7827012313101696ed6e575b259292349753b9.jpg)  
Fig.1Schematicofthebaredual-wirethermocouple(not to scale). The arrows are drawn to indicate the flow direction.

![](images/bcfc409dc7357e0ede296b9be9545606d678939e259018a0cef140db8e9549c7.jpg)  
Fig.2Schematic of the single-shielded thermocouple (not to scale).The arrows are drawn to indicate the flow direction.

![](images/9da143b3c0f843cb8b20a4f09f4c6d6006a058ee13e825d85a2ba487c1cd9d9e.jpg)

![](images/55072620adb6d60b619d31545034e12462f2da60f58d605337d0907aab3126d8.jpg)  
Fig.3Theilustrationofthecomputationaldomainandmesh.a)Thecomputationaldomain.b)Themeshoftheentiredomain outer surface.c)The mesh of the entire domain intersecting surface.d) The refined grid in the near bead region.

# The boundary condition and turbulence model

At the inlet of the computational domain,a total temperature of $1 0 7 3 \mathrm { K }$ and a total pressure are specified, which are acquired from the experiment.Theatmosphericpressureis applied to the outlet. No-slip temperature condition is applied as the boundary condition for the wind-tunnel wall. This temperature is obtainedatdifferentpositionsofthe wind-tunnel wall, and then is averaged due to the little temperature discrepancy. In all cases, an emissivity of O.3 is used for the solid wall except for O.8 for the dual-wire and bead surfaces,as described in reference[12].

The turbulence model used is realizable $\mathbf { k } { - } \mathbf { \mathcal { E } }$ with enhanced wall treatment in the near wall region, theDiscrete Ordinatemodelis employed to solve the radiative heat transfer equation. The SIMPLEC algorithm is used to generate solutions. All equations are integrated over each cell of the grid system. The fluxes at the cell faces are interpolated by using the second-order upwind scheme.

The fluid at the inlet is specified as ideal gas mixture which is assumed to be ideal fluid with adensityvariationdependentonthe temperature only. The composition of the fluid is also acquired from the experiment. All other physical properties of ideal gas mixture are modifiedandkept unchanged foreach temperature. The thermocouple model is K type and its physical properties are considered as constant for this work as well.

The convergence criterion is met when the residualsreach ${ { 1 0 } ^ { - 4 } }$ . All calculationsare performed by using FLUENT.

# Numericalmethodverification

The experiments are conducted in a hot calibration wind-tunnel. The total temperature isrecordedbyadouble-shieldsuction thermocouple which is mounted at the same transverse plane withthecalibrated thermocoupleto obtainamore actual temperature.And Mach number is confirmed by the pressure sensors.When the temperature and velocity of gas reached steady-state， the corresponding parameters are recorded.

Thegrid independenceisverifiedby computingthe thermocouple in thehot calibration wind tunnel on four grids. The numbers of grid points are ${ 4 \times 1 0 } ^ { 6 }$ cells, ${ 6 } { \times 1 0 } ^ { 6 }$ cells, ${ 7 . 5 \times 1 0 } ^ { 6 }$ and $9 \times { 1 0 } ^ { 6 }$ cells. All the grids are refined near the wall. Fig.4 shows the variation of relative temperature deviation, ( $\partial \left( ( { { { T } _ { \mathrm { { t } } } } \mathrm { { - { T } _ { \mathrm { { b } } } } } } ) / { { { T } _ { \mathrm { { t } } } } } \right)$ withthegridnumbers. Basedonthe verification,all the data presented later were obtained with the grid $( 7 . 5 { \times } 1 0 ^ { 6 } )$ ： $\mathrm { { T _ { b } } }$ is thermocouple indicative temperature and $\mathrm { T _ { t } }$ is the gas total temperature. The first grid point away from the refined region has a $\mathrm { y + }$ value less than 1 and the first five grid points have $\mathrm { y + }$ less than 5.

Temperature measurements are undertaken at different Mach numbers.Fig.5 illustrates that thenumericalresultsofthebare-bead thermocouple shows the same trend with the experimentalresultsandthecalculated temperature ratio have a good agreement with the experimental values at different Mach numbers. ${ \mathrm { T } } _ { \mathrm { b } }$ represents the volume average temperature of the bead while $\mathrm { T _ { t } }$ indicates the totaltemperature.Thus,thisnumerical simulation is a feasible approach to study the temperature measurements using the thermocouples.

![](images/b96f46712381c96c60a77d9e73fac3fc02883b810f9e80a67391dabd128598b5.jpg)  
Fig.4Relative temperature deviation (0) versus grid numbers

![](images/770f440c4c78f6c3c81dfad973f3ebcbd1894edb0cfdc860fd221b9e84c55060.jpg)  
Fig.5Temperatureratio $( T _ { b } / T _ { t } )$ ofbarethermocoupleversus Ma

The fluid is set to air after the model was validated for simplifying the question. The simulated casesarelisted as Table1.

Table1 List of simulated cases   

<html><body><table><tr><td>Variables</td></tr></table></body></html>

<html><body><table><tr><td>Tw (K)</td><td>293,1000</td></tr><tr><td>Tt (K)</td><td>1073</td></tr><tr><td>Ma</td><td>0.1, 0.3, 0.5</td></tr></table></body></html>

# Results

Schematic diagram of different slices used for auxiliary explanation is shown in Fig.6.

![](images/818bc03e2edf7d779d3a2510d6d5ad9e2f99837d5ffc326bde6340e9eeece126.jpg)  
Fig.6Schematic diagram ofdifferent stices.

# Effectof shield on heatflux on the wires and bead surfaces

Heat is transferred to or from the bead via convection and radiation on surface and via conduction along the wires. Surface heat transfer rate was calculated by using an area integral as follows:

$$
\mathrm  { Q = } \mathrm  { J } \mathrm { { q } } \mathrm   \qquad ~ \ d A = \qquad \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \ S \Sigma \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S \ S
$$

To calculate heat conduction of bead along the wire, the formula of the energy balance on the bead is established as follows:

$$
Q _ { c o n \nu e c t i o n } = Q _ { r a d i a t i o n } + Q _ { c o n d u c t i o n }
$$

Therefore，heat conduction flux could be calculated as:

$$
Q _ { c o n d u c t i o n } { = } Q _ { c o n \nu e c t i o n } { - } Q _ { r a d i a t i o n }
$$

The shield significantly reduces surface heat exchangeandchangestheinfluenceof conduction on the measurement when radiant heat transfer is relatively intense.

FromFig.7.a), theshield reducesthe radiative exchange between the thermocouple and the surrounding,especially in a colder surrounding. When the computational domain wall temperature is 293K, the net radiative heat exchangebetween thesingle-shielded thermocouple and the surrounding is nearly

$1 5 \%$ ofthat between thebare-bead thermocoupleandthesurrounding. The existence of shield makes the bead surface radiative exchange heat flux with the shield inner wall mainly, whose temperature is higher than that of the computational domain wall. This leads to a reduction in the radiative exchange in steady state.

FromFig.7.b), theshield reduces the convectiveheatexchangebetween the thermocouple and the flow especially when the computational domain wall temperature is low. Fig.9 shows the flow field of two types of thermocouples near in the bead region when airflowtotal temperature is1073K， the computational domain wall temperatureis 293K and the Mach number is O.3.It shows that shield transformed the flow direction near the bead. Compared to airflow directly impacts the bare-bead thermocouple surface, the shield reduces the airflow velocity and reduces the difference of airflow velocity along the wire axial direction as well. This leads to a reduction in convective heat transfer coefficient in steady state.

![](images/e58a2f911dc6a1385d4c13fabb4c03f3c0a3d7f89ef8506b00edf5db3eec6432.jpg)

![](images/e9f7e4c1e1c1334ada4d6d9dd052e6eaaf212d1b2daac659f8642f910ec9ed7f.jpg)  
Fig.7 Heat transfer ratio of the single-shielded thermocouples to the bare-bead thermocouples: a) radiative heat transfer;b) convective heat transfer;c) conductive heat transfer.

From Fig.7.c)， the shield changesthe direction of heat conduction along wire when the wall temperature is 293K as the conductive heat transfer ratio of the single-shielded thermocouples to the bare-bead thermocouples is negative.

![](images/41dc6028a9fe8d7513b84a08cf12300501e82970402642d868f23101ef50eeeb.jpg)  
Fig.8The ratio of conduction heat transfer to radiation heat transfer: a) $T w 2 9 3 K$ ;b) $T w I 0 0 0 K .$ （204

From Fig.8.b), the absolute value of the ratio of conduction heat transfer to radiation heat transferisbiggerinsingle-shielded thermocouple when the wall temperature is $1 0 0 0 ~ \mathrm { K }$ .A conclusion can be obtained that the shield increases the influence of conduction on the measurement when the wall temperature is high.

From Fig.8， the ratio of conduction heat transfer to radiation heat transfer of two types in all simulated cases is nearly O.1.Therefore, the influence of conduction on the measurement is relatively small.

# Effect of shield on temperature distribution on the wire and bead surface

Since this study mostly focused on the difference of surface temperature distribution between the bare-bead and the single-shielded thermocouples in the near-bead region, it is chosen to show sample results in the near bead region, detailed results for the entire domain are not presented.Fig.10,12,13 show the results for the cases with a Mach number of 0.3,an airflow total temperature of $1 0 7 3 \mathrm { K }$ and a wall temperature of $2 9 3 \mathrm { ~ K ~ }$ ：

![](images/73d42b69df174556dda7e1a79bb5d3ebc1c49b0d2f4d0a070daa8695416aba30.jpg)  
Fig.9The flow field of two typesof thermocouplesnear the bead region:a) slice2 ofthe bare-bead thermocouple; b) slice 3 of the bare-bead thermocouple; c) slice 2 of thesingle-shieldedthermocouple

The shield dramatically improved the bead surface temperature as compared to a bare-bead thermocouple for an airflow total temperature of 1073 K. From Fig.10, a nearly $2 5 \mathrm { K }$ closer to the airflow total temperature is found when comparing the single-shielded thermocouple bead surface average temperature with the bare-bead one.

What's more, the bead surface temperature gradientissmaller asthe existenceof single-shield. Fig.11showsthemaximum surface temperature deviation of two typical thermocouples changed with different Mach numbers.It can be seen from Fig.11 that as the Mach number increases, the bead surface temperaturedifferencesofthebare-bead thermocouple increase.The difference could be around $1 0 \mathrm { ~ K ~ }$ at high Mach number. However, the maximum surface temperature differences ofthe single-shielded thermocouple, maintained at about $0 . 3 \mathrm { ~ K ~ }$ ， do not substantially change with increasing Mach number.

In summary, the use of single-shield can be expected toreducethetemperature measurement bias both by improving the bead surface temperature and by reducing surface temperature gradient.

Fig.12.b) and Fig.13.b） show the inner temperature distribution of two types of thermocouples bead. The inner temperature distribution has the same trend of surface temperature distribution.Fig.15 shows the wire surface average temperature along wire axial direction. It could be seen that the single-shielded thermocouple wire surface average temperature decreases from bead to thermocouple wire roots.However， for the bare-bead thermocouple, there is a high temperature core area in the wire central surface.The surface temperature increases firstly and then decreases.Therefore，the existence of shield changes the direction of wire inner heat conduction when the wall temperature is low.

![](images/616d8bdc9ba219ea623b6ef3a0f2ba0f21e9260dfe8f8e2c51e4017ea6a37d5d.jpg)  
Fig.lOTemperaturedistributiononthe wireandbead surface: (a)thebare-bead thermocouples，(b)thesingle-shielded thermocouples(ThepositivedirectionofZ-axisistheinflowdirection.).

![](images/1a900400e9f958e07da6239799609f39ea73e73e274bd101ac3d8370f3f7352b.jpg)

![](images/1ee5aadf3c0c0df5dc63946d500c707a9456469bfe9dc674930b4afac7fc6933.jpg)  
Fig.llThe maximumsurface temperaturedeviationoftwo types ofthermocouples versus diferentMach numbers.The airflow total temperatureis $1 0 7 3 \ K . 4 )$ thecomputational domain wall temperature is $2 9 3 \ K ,$ b) the computational domain wall temperature is $\textbf { \textit { 1 0 7 3 K } }$ （20

![](images/c694bac1842e01dd42b6946e97349eee2ec45b04acc9a79e2bf5488cc0bdde64.jpg)  
Fig.l2Temperature contours of the bare-bead thermocouple case:(a) slicel.(b) slice2.

![](images/a364603ef1146c3df1e1c9bc3bd18a85034914a78dd18907211d44b332138af5.jpg)  
Fig. 13Temperature contours of the single-shielded thermocouple case: (a) slicel. (b) slice2.   
Fig.14shows the surface circumferential temperature distribution of thermocouple wires

central section.It could be seen from Fig.14 that the shield makes surface temperature distribution at wire circumferential direction more even. The shield decreases the difference of circumferential convective heat transfer, though it does not significantly changed measurement bias.

![](images/9a935281b937194e712db1c61ca7f40c290a7a63359e56e81f1832620a13de4d.jpg)  
Fig. 14The surface average temperature versus circumferential angle.

![](images/4a281e866eb6832e5d5308401a06d702a947f9a7549760612ed29d0b29266b30.jpg)  
Fig. 15The surface average temperature versus distance fromthebead

# Effectofshield on thermocoupletemperature measurement bias

As for the measurement bias,it can be characterized using the difference between the incoming airflow total temperature $\left( \mathrm { T _ { t } } \right)$ and the representative thermocouple

![](images/0f2e4159723cef4df158491e1ba45c09ec0ea414c03f75407c89bed58b215444.jpg)  
Fig.16 Temperature measurement bias of two type thermocouple versus Ma:a) Tw 293 K;b) Tw 1000 K.

![](images/9059fcf89607a58e69c99f8749494a49f77b091885bd8e00db429efc52348480.jpg)  
Fig. 17Variation of temperature measurement bias caused bytwo different wall temperature (293K,1000K) versus Ma

temperature $\left( \mathrm { T _ { b } } \right)$ inthispaper. The representative thermocouple temperature here

$\mathrm { ( T _ { b } ) }$ （ wascalculated byusing a bead volume-weighted average temperature as follows:

$$
T _ { b } = \frac { 1 } { V _ { b } } \Big \{ { T \cdot d V } = \frac { 1 } { V _ { b } } \sum _ { i = 1 } ^ { N } T _ { b , i } \cdot d V _ { i }
$$

It is worthwhile reminding that the main objective of this study is to illustrate the differenceofthebare-beadand the single-shielded thermocouples in temperature measurement and to attempt to estimate the relativemagnitudeofthetemperature measurement bias in steady state rather than delivering an exactly absolute value of the thermocouple temperature measurement bias.

From Fig.l6 the shield does not change the variation trend of temperature biaswith increasing Mach numbers in the subsonic region.

From Fig.16.a), the temperature measurement biasoftwo typesof thermocouples increases with increasing Mach numbers when the wall temperature $( \mathrm { T _ { w } } )$ is close to the airflow total temperature $\left( \mathrm { T _ { t } } \right)$ . It is mainly due to the velocity error is proportional to airflow velocity.

However, it can be seen from Fig.16.b) that the relationship of temperature measurement bias and Mach number is not monotonous when the wall temperature is farless than the airflow total temperature.There is an optimum Mach number at which point the temperature measurement bias is the minimum. It is mainly due to the radiation loss cannot be neglected when the wall temperature is low, and the radiation effect decreases with increasing Mach number.

Theshield effectivelyreduces the temperature measurement bias and reduces the effect of wall temperature on the temperature measurement bias as compared to the bare-bead thermocouple.Fig.17 shows the deviation of the temperature measurement bias when the wall temperature changes from $2 9 3 \mathrm { ~ K ~ }$ to 1000 K at different Mach number. The maximum deviation caused by varied wall temperature, appears when Ma is O.1,decreases from 55 K to $2 0 \mathrm { K }$ as the existence of the shield.

The shield effectively reduces the influence offlowvelocityonthetemperature measurement bias as compared to the bare-bead thermocouple as well. It can be seen from Fig.16 that when the wall temperature is $1 0 0 0 \mathrm { ~ K ~ }$ the deviation of the single-shielded thermocouple temperature measurement bias is $5 \mathrm { ~ K ~ }$ with the Mach number changes,which is 15K less than that of the bare-bead thermocouple.

# Conclusion

Two kinds of thermocouple temperature measurements in hot, flowing air are simulated respectively by means of CFD.In order to compare with the experimental results,a cylindrical computational domain is established which is the same size with the hot calibration wind-tunnel. The computational domain wall representtingthesurroundinginthereal thermocouple measurement exchanges radiative heat with the thermocouples. Allthe simulations are performed using a commercial flow solver (Fluent)，using a hybrid mesh, Reynolds- averaged transport equations, Realizable k-ε turbulence model and radiation model (DO).A combined solution of the flow field, energy equations， conduction in the thermocouple and radiation between different surfaces is obtained in these simulations.

The parameters varied in two kinds of thermocouplethermalsimulationsarethe airflow Mach number(from O.1 to O.5) and the computational domain wall temperature (from $2 9 3 \mathrm { ~ K ~ }$ to $1 0 0 0 ~ \mathrm { ~ K ~ } )$ when the airflow total temperature is fixed to $1 0 7 3 \mathrm { ~ K ~ }$ .The effect of shield ontemperaturedistribution and temperature measurement bias are discussed, and the results show that:

(1) The numerical method of fluid-solid conjugated heat transfer is a feasible approach for studying the temperature measurement using a thermocouple.

(2) The existence of the shield can be expected toreducethetemperature measurement bias both by improving bead surface temperature and by reducing bead surface temperature gradient. (3) The existence of the shield reduces surface heat flux and changes the direction of wires inner heat conduction when the wall temperature is low. (4) The shield effectively reduces the effect ofwall temperatureon thetemperature measurement bias. (5) The shield effectively reduces the influence of airflow velocity on the temperature measurement bias.

# Acknowledgement

This study was supported by the National Natural Science Foundation of China (Grant No.51776011).

# References

[1]Park R M.: Manual on the use of thermocouples in temperature measurement.American Society for Testing &

Materials,Philadelphia,(1993).   
[2]Rizika, J. W.,and Rohsenow,W. M.: Thermocouple thermal error, Industrial & Engineering Chemistry, 44(5), pp.1168-1171,(1952).   
[3]Bontrager, P.J.: Development of thermocouple-type total temperature probes in the hypersonic flow regime,Arnold Engineering Development Center, Tennessee, pp.20-23,(1969).   
[4]Bradley, D.,and Mathews,K.: Measurement of high gas temperatures with fine wire thermocouples,Journal of Mechanical Engineering Science，10(4)，pp.299-305, (1968).   
[5]Blevins,L. G,and Pitts,W. M.: Modeling of bare and aspirated thermocouples in compartment fires,Fire safety journal,33(4),pp.239-259,(1999).   
[6]Pitts,W.M.,Braun,E.,Peacock,R.D.,Mitler,H.E., Johnsson,E.L.,Reneke,P.A.,and Blevins,L.G.: Temperature uncertainties for bare-bead and aspirated thermocouple measurements in fire environments, Thermal Measurements: The Foundation of Fire Standards, Tsukuba, (2003).   
[7]Luo,M.: Effects of radiation on temperature measurement in a fire environment, Journal of Fire Sciences, 15(6), pp. 443-461,(1997).   
[8]Brohez,S.,Delvosalle,C.,and Marlair,G.: A two-thermocouples probe for radiation corrections of measured temperatures in compartment fires," Fire Safety Journal, 39(5), pp.399-411, (2004).   
[9]Kim, S. C.,and Hamins,A.: On the Temperature Measurement Bias and Time Response of an Aspirated Thermocouple in Fire Environment,"Journal ofFire Sciences, 26(6), pp.509-529,(2008).   
10]Etemad, S.: Thermal Simulations of Thermocouple Tips in Hot Jets," Journal of Thermal Science and Engineering Applications, 6(4),p. 041008,(2014).   
11]Inc,F.: GAMBIT Modeling Guide Fluent Inc,(2003).   
[12]Rohsenow, W. M., Hartnett, J. P.,and Cho, Y. I.: Handbook of heat transfer, McGraw-Hill New York,(1998).