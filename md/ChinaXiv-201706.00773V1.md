# A New Method of Thermal Protection by Opposing Jet for a Hypersonic Aeroheating Strut

QIN Jiang, NING Dongpo, FENG Yu, ZHANG Junlong, FENG Shuo, BAO Wen\*

Harbin Institute of Technology, Heilongjiang 150oo1, China $\copyright$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

This paper presents the numerical investigation of thermal protection of scramjet strut by opposing jet in supersonic stream of Mach number 6 with a hydrogen fueled scramjet strut model using CFD software.Simulation results indicate that whenasmallamount of fuel is injected from the noseof the strut,the bow shock is pushed away from the strut,and the heatflux is reduced inthe strut,especiallyat the leading edge.Opposing jet forms a recirculation region near the nozzle so that the strut is covered with low temperature fuel and separated from free stream. An appropriate total pressure ratio can be used to reduce not only aerodynamic heating but also the drag of strut.It is therefore concluded that thermal protection of scramjet strut by opposing jet is one of the promising ways to protect scramjet strut in high enthalpy stream.

# Keywords: thermal protection, scramjet strut, opposing jet

# Introduction

Aerodynamic heating of scramjet becomes more severe[1,2] with the increasing flight Mach number, and it has attracted much attention [3,4,5] from the research community.Much work has been done on this particular aspectinrecent years.

Combustor is one of the most important parts of scramjet [6].As a usual means for fuel injection, the strut is used not only to inject fuel, but also to make the combustion stable [7]. Due to aerodynamic heating and combustion, the surface heat flux of the strut is very high. It is common to use a small strut wedge angle to reduce the drag[8],however, it leads to a high heat flux at the leading edge of a strut. So, the thermal protection of the leading edge of a strut is a problem.

Passive cooling is a common way of strut thermal protection at low Mach number, Sunami, T.et al.[9] designed a strut which was made of ablation resistant material.However, the temperature of the strut leading edge reaches $3 0 0 0 ~ \mathrm { K }$ when flight Mach number is higher than 5.It is hard to find an ideal material to accommodate such a high temperature.Regenerative cooling[1O] is an active way of thermal protection [11], fuel flows in the channel as coolant to absorb heat.For example,Russian scientist Semonov[12] designed a strut with an active cooling system,lowtemperature fuel flowedinthe thin walled tubes of the strut [13]. The regenerative cooling is effective for the thermal protection of strut.But it is difficult to design tubes at the leading edge because of its small size,and so, the method could not be used for the leading edge.Brune.A[14] used transpiration cooling to protect the strut from high temperature,yet the structure was too complex.In conclusion, the thermal protection of the leading edge is the key and difficult point [15] of strut, and it is hard to protect the leading edge from aerodynamic heating. Both the drag of strut and the effect of thermal protection should be taken into consideration when a cooling system of strut is designed.

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>FS</td><td>arc surface of strut leading edge</td><td>Ma</td><td>Mach number of free stream</td></tr><tr><td>FP</td><td>windward bevel of strut</td><td>Pj</td><td>Total pressure of opposing jet</td></tr><tr><td>S</td><td>Stanton number</td><td>P</td><td>Total pressure of free stream.</td></tr><tr><td>qw</td><td>heat flux</td><td>C</td><td>Drag coefficient,</td></tr><tr><td>Taw</td><td>wall recovery temperature of an adiabatic wall</td><td>Cp</td><td>Pressure drag coefficient,</td></tr><tr><td>Tw</td><td>wall temperature</td><td>Cf</td><td>Friction drag coefficient,</td></tr><tr><td>p</td><td>density of free stream</td><td>Cd</td><td>Total drag coefficient,</td></tr><tr><td>Cp</td><td>Specific heat of free stream</td><td>F</td><td>Drag,</td></tr><tr><td>u</td><td>Velocity of free stream</td><td>pV²/2</td><td>Dynamic air pressure at entrance,</td></tr><tr><td>T Subscripts</td><td>Temperature of free stream</td><td>Astrut</td><td>Windward area.</td></tr><tr><td colspan="2"></td><td></td><td></td></tr><tr><td colspan="2">j Opposing jet</td><td>0</td><td>Free stream</td></tr></table></body></html>

A new thermal protection method by opposing jet for a scramjet strut was presented in this paper. The mechanism of aerodynamic heating reduction by opposing jet Was introduced.A scramjet strut with opposing jet model Was constructed.Numerical simulation was run to verify the effectiveness of the proposed method in protecting the strut. The heat flux distribution and characteristics of the strut flow field were analyzed in this study.

# Method of opposing jet

When aircraft flies in supersonic free stream,aerodynamic heating results in an ultra-high surface temperature and its thermal environment is similar to that of a strut. Passive, semi-passive cooling or active cooling is usually used for thermal protection of strut [16-18].In 1960s Japanese scientists began their study on the reduction of aerodynamic heating of aircraft nose by opposing jet. Finley.P.J[19] studied Mach disk recirculation region and shock wave in opposing jet flow field in 1966.Aso.S [20] studied the reduction of aerodynamic heating by opposing jet in supersonic stream.

As shown in Fig.1,a spindly nozzle is added to the leading edge of the strut. So that low temperature fuel flows through the cooling tubes to absorb heat. An opposing jet covers the whole surface of the strut, then, heat is transferred from the free stream to the strut.

![](images/9a929d16ebe903acbbec46c4e62fc823f3bfc974a044f061d492fc228a31eb88.jpg)  
Fig.1Thermal protection by opposing jet

# Calculation methodology

In the scramjet under study hydrogen fuel is injected from the nose of the strut to cool the strut,and then burned in the back of the combustor.

# Combustor and strut configuration

As the initial work on the use of opposing jet for thermal protection of scramjet strut, only a strut without sweepback is studied through calculation. The nozzle at the leading edge is a spindly seam,and so,a 2-D simulationis used to show the characteristics of its flow field. The grid and physical model are the same as those used in Zong's study [8].

# Physical model

All the meshes are generated by ICEM. The calculation is done by using Fluent (version 14.5). A density-based solver with implicit time-marching algorithm is used for simulation.A SST K-@ model with default values is used for modelling turbulence.Specific heat ratio is calculated using the simulated expressions of temperature with default value. Thermal conductivity is calculated using perturbation methods,and coefficient of viscosity is calculated using Sutherland law.

![](images/78a410d70111337aa9b704305f31ca77e33fce178927aa2e748ea6e01dbb82f4.jpg)  
Fig.2Schematic diagram of analysis model and strut installation

# Physical model boundary conditions

The surface temperature of the strut is a constant value for this study. The temperature is 10ooK,which is near the highest temperature for metal. Adiabatic and no-slip boundary conditions are for all the wall surfaces.

The entrance condition of flight Mach number 6 is used as the combustor entrance parameters. The entrance of opposing jet is pressure-inlet.

Table1 Initial boundary conditions   

<html><body><table><tr><td></td><td>Entrance of combustor</td><td>Entrance of opposing jet</td></tr><tr><td>Mach number</td><td>3.2</td><td>1.1</td></tr><tr><td>Total pressure (MPa)</td><td>2.7</td><td>By calculation</td></tr><tr><td>Static pressure (kPa)</td><td>52.7</td><td>By calculation</td></tr><tr><td>Total temperature(K)</td><td>1505</td><td>300</td></tr></table></body></html>

# Results and Analysis

# Effect of opposing jet on heat flux distribution

For this study, Stanton number [21] is used to compare eachheatfluxdistribution.Andit canbedefined as:

$$
\begin{array} { c } { { S t = \displaystyle \frac { q _ { w } } { ( T _ { a w } - T _ { w } ) \rho _ { \infty } C _ { p \infty } u _ { \infty } } } } \\ { { T _ { a w } = T _ { \infty } \left\{ 1 + \sqrt [ 3 ] { \mathrm { P r } } \big [ \big ( \gamma - 1 \big ) / 2 \big ] M a _ { \infty } ^ { 2 } \right\} } } \end{array}
$$

where $S _ { t }$ is the Stanton number, $q _ { w }$ is the heat flux, $T _ { a w }$ is wall recovery temperature of an adiabatic wall, $T _ { w }$ is the wall temperature, $\rho _ { \infty }$ is the density of free stream, $C _ { p \infty }$ is the specific heat of free stream, $u _ { \infty }$ is the velocity of free stream, $T _ { \infty }$ is the temperature of free stream, $M \boldsymbol { a } _ { \infty }$ is the Mach number of free stream.

Angle is used to show the heat flux distribution in Fig.3a. X-coordinate was adequate to show the heat flux distribution on FP in Fig.3b. $P _ { j }$ is the total pressure of opposing jet,and $P _ { 0 }$ is the total pressure of free stream.

As shown in Fig.4,the heat transfer process is in the right tropism, and so the Stanton number could be either positive or negative.For this study, Stanton number is positive when heat is transferred from strut to gas,and negative when in the opposite direction. Stanton number is negative on FS and FP when there is no opposing jet, which means that heat is transferred from gas to strut. Besides,heat flux inFSishigher than thatin FP,which means that the aerodynamic heating is more serious at the stagnation point of the strut.It can be seen from Fig.4 that the strut is covered with cooling fuel,and is separated from the free stream,heat is transferred from strut to gas when the temperature of fuel is lower than that of thestrut.What is more,the heat flux transferred from strut to gas increases with the increasing total pressure of opposing jet in FS,and so is FP.The cooling of the strut is more effective with the increasing total pressure of opposing jet.Heat flux is directly linked to the temperature of gas around as the transfer between strut and gas around is heat convection as shown in Fig.5.

Free stream hits against the strut straightly when there is no opposing jet. The majority of kinetic energy of free stream is transferred into the internal energy on FS.The temperature around FS is more than $1 4 0 0 \mathrm { ~ K ~ }$ ，and the temperature around FP is about $1 0 0 0 ~ \mathrm { K }$ .Therefore,heat istransferred from free stream to the strut.The heat flux increases as the difference in temperature between FS

![](images/c7b07896b045c7c845e1bac3820649966af698e6695a232535967757d9fdffb5.jpg)  
Fig.3Coordinate in strut

![](images/8595fd551ea71b200fb10756512b5b4bea0c12a2e4977d9221152138c4aa97c9.jpg)  
Fig.4Stanton number distributions in FS and FP for different total pressure ratios

![](images/67d69ae0b52ddf6693960cc8cc8067b5b8e231119a435fc111f963395f5606f3.jpg)  
Fig.5Temperature contours on FS and FP at different total pressure ratios

and gas increases and so, the leading edge ablation can be easily caused.After the fuel with a total temperature of only 3ooK is injected from the nozzle of strut, the strut is covered with fuel because of the pressure and friction of free stream,and consequently, the heat cannot be transferred from free stream to the strut.

# Effect of opposing jet on shock wave

As shown in Fig.6,a bow shock wave appears when supersonic stream hits the wedge. The stream is compressed more severely,and the temperature increases with the increasing shock wave strength.And then, the heat fluxbetween strut and stream increases.

It can be seen from Fig.6 that the air temperature is the highest near the stagnation point when there is no opposing jet.However, the gas temperature goes down to 200 K when fuel is injected,and the peak point of temperature profiles moves away from the strut, which implies that the bow shock wave is pushed off the strut by opposing jet. The shock wave is pushed further away with the increasing total pressure ratio.

The temperature, pressure and density of gas increase suddenly after the gas passing the shock wave. The distances between the shock wave and the strut at different total pressure ratios are shown in Fig.7.The distance between the shock wave and the strut is only $0 . 3 \ \mathrm { m m }$ when there is no opposing jet as shown in Fig.7. The shock wave moves away from the strut after fuel is injected. The distance is $4 \mathrm { m m }$ when the total pressure is 0.8.

![](images/f1ec0960e36d658d898a35def4c8243f3c7fe607e31b1131674f778cab665edc.jpg)  
Fig.6Temperature profiles in front of the strut at different total pressure

![](images/cf9496dcc9c425c3f49aad69f066be45290126fdf4e4e0e26a82ab189eb37da0.jpg)  
Fig.7Distance between strut and shock waves for different total pressure ratios

As shown in Fig.8,there is a detached bow shock wave near the leading edge of the strut when there is no opposing jet. When there is an opposing jet, there is a Mach disk in front of the strut to balance the pressure of jet with the pressure behind the detached shock wave, which grows with increasing total pressure ratio.

# Effect of opposing jet on flow field

As shown in Fig.9, free stream hits the leading edge of the strut straightly and flows backward against 2 strut when there is no opposing jet.There is a recirculation region near the nozzle at the leading edge as fuel is injected from the nozzle. The recirculation region expands with the increasing total pressure ratio.The recirculation region is covered with cooling fuel,and then it reduces the aerodynamic heating on FS.The reflowing fuel flows along the strut to separate FP from free stream.

As shown in Fig.10,without opposing jet the pressure is the highest at stagnation point,and the detached shock wave from the stagnation point is the strongest. The pressure declines with increasing O and weakening shock wave. Compared with the case without opposing jet, the pressure on FS is $0 . 0 5 \mathrm { M P a }$ lower,and the pressure is far less than that in the case of without opposing jet,which implies the bow shock wave is weakened by opposing jet.

# Effect of opposing jet on drag of strut

Low drag can reduce the loss of specific impulse and

obtain a higher thrust. The drag coefficient of strut is used to study the effect of opposing jet on the drag of strut. The drag coefficient can be defined as:

$$
C = \frac { F } { \displaystyle { \frac { 1 } { 2 } \rho V ^ { 2 } A _ { s t r u t } } }
$$

where $C$ is the drag coefficient, $C _ { p }$ is the pressure drag coefficient, $C _ { f }$ is the friction drag coefficient, $C _ { d }$ is the total drag coefficient, $F$ is the drag, $\rho V ^ { 2 } / 2$ is the dynamic air pressure at entrance, $A _ { s t r u t }$ is the windward area.

As shown in Fig.11,the total drag coefficient at different total pressure ratios is smaller than that for the strut without opposing jet. The total drag coefficient is the smallest when the total pressure ratio is O.6,which is reduced by about $2 8 . 5 \%$ . The pressure drag coefficient gradually declines as the total pressure ratio increases. Friction drag coefficient changes slightly with the increasing total pressure,and it was higher than that in the case of no opposing jet when the total pressure ratio is 0.8.

Opposing jet can cause a recirculation region near the nozzle of strut. The pressure of gas in the recirculation region is lower than the pressure of free stream,and so, the pressure drag of strut declines.As the total pressure ratio increases, the recirculation region expands,and the pressure drag of strut declines further. A proper total pressure ratio can reduce not only the aerodynamic heating but also the drag of strut.

![](images/731271ad0e41fe42df4e97ea509483b2fcfab87e867eed781901376489be74c8.jpg)  
Fig.8Mach number contours of flow field at different total pressure ratios

![](images/decb238a0d8f07d6a5d4b1170e24f8ade6bd6d5418ef380c3a3697b1d1ae98b0.jpg)  
Fig.9Streamlines near leading edge of the strut at different total pressure ratios

![](images/2e467e4d8d70c865b433f8ddf222b50cac8e77c85e683d2544af63175796d78c.jpg)  
Fig.10Pressure distributions on FS and FPat different total pressure ratios

![](images/335b58892d99c4da96f7fd331c60c33dd958aad2029b4db61deb07db1c9460de.jpg)  
Fig.11Drag coefficient of the flow fields at different total pressure ratios

# Conclusions

It can be seen from the presentation above that when a small amount of fuel is injected from the nose of strut, the bow shock is pushed away from the strut,and the heat flux is reduced in the strut, especially in the leading edge.A recirculation region is formed near the nozzle so that the strut is covered with low temperature fuel and separated from free stream. The heat flux from strut to fuel increases with the increasing total pressure ratio,and an appropriate total pressure ratio can be used to reduce not onlyaerodynamic heating butalso the dragof strut.It is therefore concluded that thermal protection of scramjet strut by opposing jet is one of the promising ways to protect scramjet strut in high enthalpy stream.

# Acknowledgments

This research work is supported by Program (Nos. 51476044 and 51606051） and Innovative Research Groups (No.51421063） of National Natural Science Foundation of China,and Shenzhen Technology Projects (No. JCYJ20160427184254731).

# References

[1]Prisell. E,“The Scramjet: A Solution for Hypersonic AerodynamicPropulsion,”AIAA/ASME/SAE/ASEE Joint Propulsion Conference & Exhibit, 2013.   
[2]Tetlow. M.R,Doolan.C.J,“Comparison of Hydrogen and Hydrocarbon-Fueled Scramjet Engines for Orbital Insertion,”Journal of Spacecraft and Rockets,Vol. 44, No.2,2007,pp. 365-373.   
[3]Voland.R.T,Auslender.A.H, Smart.M.K,Roudakov.A, Semenov. V, and Kopchenov. V,“CIAM/NASA Mach 6.5 Scramjet Flight and Ground Test Program,”AIAA Journal, 1999.   
[4]Kanda.T, Sunami. T, and Tomioka. S,"Mach 8 Testing of a Scramjet Engine Model,” Journal of Propulsion and Power, Vol.17,No.1,2001, pp.132-138.   
[5]Fletcher. E.A,“Scramjets and surfboards: Some forgotten history,”Journal of Propulsion and Power,Vol.23, No.1,2007,pp. 15-20.   
[6]Song. J, Wang. L. Q, Qin. J. N, Weijie. L, Zhang. D, and Hou.H.L“Effect of Thermo Hydrogen Treatment on Microstructure and Mechanical Propertiesof(TiB, TiC)/Ti-6Al-4V Composite,”Materials for Mechanical Engineering, 2012.   
[7]Mai. T, Sakimitsu. Y, Nakamura. H, Ogami. Y, Kudo. T, and Kobayashi.H,“Effect of incident shock wave interacting with transversal jet flow on the mixing and combustion,”Proceedings of the Combustion Institute, Vol. 33,No.2,2011,pp.2336-2342.   
[8] Bao. W, Zong. Y,“Effects of Strut Swept Angle on the Drag of Scramjet,”Proceedings of the Institution of Mechanical Engineers Part G Journal of Aerospace Engineering,Vol.226,No.4,2013,pp.455-466.   
[9]Sunami. T, Scheel. F,“Analysis of Mixing Enhancement Using Streamwise Vortices in a Supersonic Combustor by Application of Laser Diagnostics,”AIAA/AAAF International Conference Space Planes and Hypersonic Systems and Technologies, Orleans,France,2002.   
[10]Feng. Y, Qin. J, Zhang. S, Bao. W, Cao. Y,and Huang. H, “Modeling and analysis of heat and mass transfers of supercritical hydrocarbon fuel with cracking in mini-channel,”International Journal of Heat and Mass Transfer, Vol. 91,No.5,2015, pp.520-531.   
[11]Zhang. S,Jiang.Q.Wen.B,Yu.F,and Xie.K,“Thermal management of fuel in advanced aeroengine in view of chemical recuperation,”Energy, Vol. 77,2014, pp.201- 221.   
[12]Semenov. V.L,“The Possibility Investigation of Strut Fuel Feed System Use in Scramjet Combustors on Results of Tests with Hydrocarbon fuel,”CENTRAL INST OF AVIATION MOTORS Moscow, Russia, 1997.   
[13]Zhou. W, Wang. D, Bao. W, Qin J,“Experimental method study on heat flux measurement on sharp leading edge," Proceedings of the Institution of Mechanical Engineers Part G Journal of Aerospace Engineering, Vol. 228, No. 11,2013, pp. 2055-2065.   
[14]Brune.A, Hosder. S, Maddalena.L,and Gulli. S,“Numerical Investigation of Variable Transpiration Cooling Effectiveness in Laminar and Turbulent Flowsfor Hypersonic Cruise Vehicles,”AIAA Aerospace Sciences Meeting Including the New Horizons Forum and Aerospace Exposition, 2013.   
[15]Lehnen. M. V, Lee. C,“Nu Correlation for Impingement Wall Cooling by Synthetic Jet,”AIAA Journal, 2006.   
[16]Dorsey. J. T, Chen. R.R,Wurster. K.E,and Poteet. C.C, “Metallic Thermal Protection System Requirements,Environments,and Integrated Concepts,” Journal of Spacecraft and Rockets, Vol. 41, No.2,2004,pp.162-172.   
[17]Rakow. J. F, Waas. A. M,“Response of Actively Cooled Metal Foam Sandwich Panels Exposed to Thermal Loading,"AIAA Journal, Vol.45,No.2,2007,pp.329-336.   
[18]Bouchez. M, Cahuzac.G, and Beyer. S,“PTAH-SOCAR Fuel-Cooled Composite Materials Structure”AIAA, 2003.   
[19] Finley. P. J,“The flow of a jet from a body opposing a supersonic free stream,” Journal of Fluid Mechanics, Vol. 26, No. 2,1966, pp.337-368.   
[20]Aso.S,Hayashi. K,and Mizoguchi.M,“A study on aerodynamic heating reduction due to opposing jet in hypersonic flow,”AIAA Aerospace Sciences Meeting & Exhibit, 2002.   
[21]Baumeister.K. J，Hamill. T. D,“Hyperbolic HeatConduction Equation—A Solution for the Semi-Infinite BodyProblem,”Journal of Heat Transfer,Vol.91,No.1, 1969, pp. 543-548.