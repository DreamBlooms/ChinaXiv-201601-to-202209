# Numerical Analysis of Flow Instability in the Water Wall of a Supercritical CFB Boiler with Annular Furnace

XIE Beibei, YANG Dong",XIE Haiyan, NIE Xin,LIU Wanyu

State Key LaboratoryofMultiphase Flow in Power Engineering, Xi'an Jiaotong University, Xi'an710049, China

In order to expand the study on flow instability of supercritical circulating fluidized bed (CFB)boiler,a new numerical computational model considering the heat storage of the tube wall metal was presented in this paper.The lumped parameter method was proposed for walltemperature calculation and the single channel model was adopted for the analysis of flow instability.Based on the time-domain method,a new numerical computational program suitable for the analysis offlow instability in the water wallof supercritical CFB boiler with annular furnace was established.To verifythe code,calculation results were respectively compared with data of commercial software.According to the comparisons,the new code was proved to be reasonable and accurate for practical engineering application in analysis offlow instability.Based on the new program,the flow instability of supercritical CFB boiler with annular furnace was simulated by time-domain method.When 1.2 times heat load disturbance was applied on the loop,results showed that the inlet flow rate,outlet flow rate and wall temperature fluctuated with time eventually remained at constant values,suggesting that the hydrodynamic flow was stable. The results also showed that in the case of considering the heat storage,the flow in the water wallis easier to return to stable state than without considering heat storage.

# Keywords: supercritical CFB with annular furnace; heat storage; flow instability;walltemperature; numerical analysis

# Introduction

The combustion technology of circulating fluidized bed(CFB) has the advantages of low NOx emission, wide adaptability, high combustion efficiency and low cost of pollution control, which has been widely used in many fields,such as electric power,petroleum,chemical and waste disposal and so on.Compared with subcritical CFB boiler, the operating parameters and mode of supercritical CFB boiler are high,and the fluid in the tube is likely to operate at the supercritical state of high load, or it may work at the two phase state of lower load.In order to ensure the safe and reliable operation of the equipment, we must ensure that the film boiling(DNB)doesn't occur, and the temperature of tube is in the safe range after the drying up (DRYOUT).

Inrecent decades, the flow instabilityhas caused wide concern on the design and operation of various heat transfer equipments,such as nuclear reactors,refrigeration plants and boilers.It may result in oscillation of wall temperature,lead to fatigue damage of tube and heat transfer deterioration [1]. Thus making investigations on flow instability is very essential. Since 1938, the domestic and foreign scholars have carried out extensive and in-depth study on the two-phase flow instability [2-16]. However,there is few research on the problem of the flow instability considering the heat storage of the tube wall metal in a boiler. The heat flux density of the furnace is influenced by the heat storage of metal, then the dynamic characteristics of the furnace will also be influenced,so it isnecessaryto study thehydrodynamic flow instability of a boiler when the heat storage of the tube wall metal is considered.In this paper,the numerical computational model considering the heat storage of metal and suitable for the analysis of flow instability and the calculation of wall temperature is established by the lumped parameter method.Based on Fortran, the single channel model and the time-domain method are adopted. In order to provide guidance for the design and operation of boiler,we select the loop that is most likely to occur flow instability in the water wall as the research object.

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>A</td><td>inner cross section area, m²</td><td>Z</td><td>axial length, m</td></tr><tr><td>dn</td><td>inner diameter, m</td><td></td><td>space step,m</td></tr><tr><td>f</td><td>friction factor</td><td>Greek symbols</td><td></td></tr></table></body></html>

<html><body><table><tr><td>g</td><td> gravity, m/s²</td><td>p</td><td>density, kg/m³</td></tr><tr><td>h</td><td>specific enthalpy, J/kg</td><td>0</td><td>angle of flow direction with respect to horizontal plane, radian</td></tr><tr><td>i</td><td>space index</td><td>8d</td><td>dimensional Dirac delta function, m-1</td></tr><tr><td>j</td><td>time index</td><td>α</td><td>convective heat transfer coefficient (W/m²·K)</td></tr><tr><td>k</td><td>pressure drop coefficient</td><td>Subscripts</td><td></td></tr><tr><td>L</td><td>total length of channel, m</td><td>in</td><td>inlet</td></tr><tr><td>M</td><td>mass flow rate, kg/s</td><td>out</td><td>outlet</td></tr><tr><td>n</td><td>total number of control volume</td><td>jb</td><td>local</td></tr><tr><td>P</td><td>pressure, Pa</td><td>n</td><td>inner</td></tr><tr><td>AP</td><td>pressure drop from inlet to outlet, Pa</td><td>f</td><td>fluid</td></tr><tr><td>qi</td><td>linear power density, W/m</td><td>W</td><td>wall</td></tr><tr><td>F2</td><td>internal surface area per unit length</td><td>Superscripts</td><td></td></tr><tr><td>Cw</td><td>specific heat(W/m² K)</td><td>0</td><td>the initial steady value</td></tr><tr><td>mw</td><td> mass per unit length(kg/m)</td><td>j</td><td>the old time value</td></tr><tr><td>t</td><td>temperature(℃)</td><td>j+1</td><td>the new time value</td></tr><tr><td>△t</td><td>time step, s</td><td></td><td></td></tr></table></body></html>

# Mathematic model

Generally, there are mainly two kinds of approaches for solving the governing equations of mass,momentum and energy. The first one is frequency-domain method, which converts the linearized equations to transfer functions by Laplace transform [17-23].However,the frequency domain method can't solve nonlinear problems very well. The second one is time-domain method, based on numerical discretization and integration,which conserves the nonlinear information of the original equations [24-28]. The time domain method is employed in the present code.The temperature of the tube wall can be calculated by using lumped parameter method or distributed parameter method.In this paper,the lumped parameter method is used to analyze and calculate the wall temperature.

# Basic assumptions

For the purpose of analyzing the flow instability of boiler, the following assumptions are proposed:

(1）One-dimensional model is employed with considering compressibility and thermal expansion. (2) The temperature and velocity of water are uniformly distributed in cross section,and water flows only along the axial direction. (3) Only heat transfer in the radial direction is considered. (4） Effects of kinetic，potential energy and viscous dissipation on energy equation are ignored.

# Transient equations for supercritical fluid

Supercritical water has no phase change which can be regarded as single phase. The basic governing equations of supercritical water are the same as the equations of homogeneous flow model.

The mass equation is:

$$
\frac { \hat { \sigma } M } { \hat { \sigma } z } + A \frac { \hat { \sigma } \rho } { \hat { \sigma } t } = 0
$$

The momentum equation is:

$$
\begin{array} { l } { { \displaystyle { \frac { \partial { \cal M } } { \partial t } } + \frac { \hat { \mathcal { O } } } { \hat { \mathcal { O } } z } ( \frac { { \cal M } ^ { 2 } } { \rho A } ) + { \cal A } \frac { \hat { \mathcal { O } } P } { \hat { \mathcal { O } } z } = - \rho g { \cal A } \sin \theta } } \\ { ~ } \\ { { \displaystyle ~ - \bigg [ \frac { f } { d } + K _ { i n } \delta _ { d } ( z ) + K _ { o u t } \delta _ { d } ( z - L ) } } \\ { { \displaystyle ~ + K _ { j b } \delta _ { d } ( z - z _ { j b } ) \bigg ] \frac { { \cal M } ^ { 2 } } { 2 \rho A } } } \end{array}
$$

The energy equation is:

$$
\frac { \hat { \sigma } ( M h ) } { \hat { \sigma } z } + A \frac { \hat { \sigma } ( \rho h ) } { \hat { \sigma } t } = q _ { l }
$$

The state equation is:

$$
\rho = f ( h , P )
$$

The metal heat storage equation is:

$$
q _ { 1 } - q _ { 2 } = c _ { w } m _ { w } \frac { \partial t _ { w } } { \partial t }
$$

The heat transfer equation of working fluid side:

$$
q _ { 2 } = \alpha F _ { 2 } ( t _ { w } - t _ { f } )
$$

# Numerical calculation method

# Discretization

Asshown in Figl,the channel is divided into several control volumes from the inlet to the outlet with equal length of $\Delta z$ . The non-staggered grid method is used for dividing the control volume of flow channel.The fluid physical state parameters,such as mass flow rate,pressure,density, temperature and enthalpy are located in the center of the control volume.Discretization of the governing equations employs first-order upwind scheme in space phase and implicit scheme in time phase.According to the first-order upwind scheme,physical state parameters on the junction are equal to that of the adjacent upstream control volume.Integration of the governing equations on every control volume yields the following equations:

·1 123 i-1i+1 p,h,M,p n n+1

Mass equation:

$$
A \frac { \rho _ { i + 1 } ^ { j + 1 } - \rho _ { i + 1 } ^ { j } } { \Delta t } + \frac { M _ { i + 1 } ^ { j + 1 } - M _ { i } ^ { j + 1 } } { \Delta z } = 0
$$

Momentum equation:

$$
\begin{array} { l } { \displaystyle \frac { M _ { j } ^ { j + 1 } - M _ { i } ^ { j } } { \Lambda } + \frac { 1 } { 4 \Lambda  { \mathrm { K } } } \Biggl [ \Biggl ( \frac { M ^ { 2 } } { \rho } \Biggr ) _ { i \mathrm { t } 1 } ^ { j + 1 } - \Biggl ( \frac { M ^ { 2 } } { \rho } \Biggr ) _ { i } ^ { j - 1 } \Biggr ] } \\ { + \frac { \lambda } { \Delta z } \Bigl ( P _ { i - 1 } ^ { j + 1 } - P _ { i } ^ { j + 1 } \Bigr ) } \\ { = - \rho _ { i } ^ { j + 1 } g \ s i \ s i \theta \theta - \frac { 1 } { 2 ^ { \ell } } \Biggl ( \frac { M ^ { 2 } } { \rho } \Biggr ) _ { i } ^ { j - 1 } } \\ { \displaystyle \left[ \frac { f _ { i } ^ { j + 1 } } { d _ { s } } + K _ { i i } \delta _ { d } ( z ) + K _ { o u } \delta _ { d } ( z - L ) \right] } \\ { + K _ { i j } \delta _ { d } ( z - z _ { j } ) } \end{array}
$$

Energy equation:

$$
\underset { \Delta t } { \underbrace { ( \rho h ) _ { i + 1 } ^ { j + 1 } - ( \rho h ) _ { i + 1 } ^ { j } } } + \frac { ( M h ) _ { i + 1 } ^ { j + 1 } - ( M h ) _ { i } ^ { j + 1 } } { \Delta z } = q _ { l i } ^ { j + 1 }
$$

State equation is:

$$
\rho _ { i } ^ { j + 1 } = f ( h _ { i } ^ { j + 1 } , P _ { i } ^ { j + 1 } )
$$

The metal heat storage equation is:

$$
q _ { 1 i } ^ { j + 1 } - q _ { 2 i } ^ { j + 1 } = c _ { w i } m _ { w i } \frac { t _ { w i } ^ { j + 1 } - t _ { w i } ^ { j } } { \Delta t }
$$

The heat transfer equation of working fluid side:

$$
q _ { 2 i } ^ { j + 1 } = \alpha _ { i } ^ { j + 1 } F _ { 2 i } ( t _ { w i } ^ { j + 1 } - t _ { f i } ^ { j + 1 } )
$$

Facilitate the heat transfer equation:

$$
q _ { 2 i } ^ { j + 1 } \approx \alpha _ { i } ^ { j } F _ { 2 i } ( t _ { w i } ^ { j + 1 } - t _ { f i } ^ { j } )
$$

# Boundaryconditions

For the single channel model, the boundary conditions are as follows:

(1)inlet enthalpy $ { \mathrm { h } } _ { \mathrm { i n } }$ is given and be constant;   
(2)inlet pressure $\mathrm { \bf P _ { \mathrm { i n } } }$ is given and be constant;   
(3)pressure drop from inlet to outlet $\Delta P$ is constant.

# Solution method

A summary of the solution method is shown in Fig 2:

(1) The initial values of P, M, h, $\rho , t _ { w } ,$ tf are firstly computed.After that, a small perturbation of heat flux is imposed on the steady state and steps (2)-(5)are repeated to calculate the transient values of the next time step level.

(2) Combine the equation of metal heat storage (11) and heat transfer (13), $t _ { w i } ^ { j + 1 }$ of the control volume and （20 $q _ { 2 i } ^ { j + 1 }$ are solved.

(3)Assume the inlet mass flow rate $M _ { 1 } ^ { j + 1 }$ （204号 (4) Repeated steps (a) $\sim ( \mathrm { e ) }$ from inlet to outlet,which means i is from 1 to n. (a) Assume the value of $\rho _ { i + 1 } ^ { j + 1 }$ ：

(b)According tothe massquation(7）， $M _ { i + 1 } ^ { j + 1 }$ i solved.   
(c) Acording to the momentum equation(8）， $P _ { i + 1 } ^ { j + 1 }$ （ is solved.   
(d) According to theenergy equation(9）， $h _ { i + 1 } ^ { j + 1 }$ s solved.   
(e) According to the state equation(1O)，an improved value of $\rho _ { i + 1 } ^ { \prime J + 1 }$ is obtained by using $P _ { i + 1 } ^ { j + 1 } , h _ { i + 1 } ^ { j + 1 }$ . Compare the density of the former and latter.Repeat steps (b)-(e) until the absolute error of density reaches a desired convergence. $\rho _ { i + 1 } ^ { \prime J + 1 }$ can be treated as an updated guess.

(5）After Step (4),the outlet pressure $P _ { n + 1 } ^ { j + 1 }$ is obtained.

If the relative difference $| ( P _ { i n } - P _ { n + 1 } ^ { j + 1 } ) - \Delta P | / \Delta P$ meets the requirement of precision, then the assumption of （204号 $M _ { 1 } ^ { j + 1 }$ is correct. Solution turns to next time step level. If not, a chord secant method is used to iterate on $M _ { 1 } ^ { j + 1 }$ （204号 untiltherelativedifference is satisfied.

The solution method for steady-state equations is similar to the transient equations which are not mentioned here.

# Validation

To validate the present code, calculation results obtained by the present numerical code are compared with the simulation results of Dynastab software.Dynastab software isakindofcommercial software developed by Siemens Ltd for simulating the hydrodynamic flow, aiming at providing guidance for the design and operation of boiler. In this paper, the geometric structure and thermal parameters are the same with those of Dynastab software in practical engineering application of a $6 0 0 \mathrm { M W }$ supercritical W-shaped boiler Initial calculating parameters are shown in Table.1. In order to simulate the flow instability precisely and calculate the wall temperature within a smaller error range,the factors of inclined angle,heat distribution and type of tube are considered, comparison results are shown in Fig.3, Fig.4, Fig.5.

Fig.3 shows that the wave curve of the inlet flow versus time derived from the present program is consistent with the curve derived from Dynastab,it indicates that the method of this paper has certain reliability for simulating the flow instability of the supercritical water.

According to the Fig.4,we can calculate the relative error of the fluid temperature and the wall temperature between program and Dynastab is $0 . 0 4 \%$ and $0 . 2 \%$ .It proves that the present program is reasonable to simulate the fluid temperature and wall temperature within error limits.

![](images/045b6dd9f9d197b4bb607c98fbf2a0fedc11155ec7cc631b9d873b3418e6395e.jpg)  
Fig.2Program calculation process

Table1Initial calculating parameters   

<html><body><table><tr><td>Parameter</td><td>Value</td></tr><tr><td>Inlet pressure</td><td>12.566MPa</td></tr><tr><td>Inlet enthalpy</td><td>1256.6 kJ/kg</td></tr><tr><td>Inlet mass flow rate</td><td>0.1367 kg/s</td></tr><tr><td>Inlet pressure drop coeficient</td><td>0.5</td></tr><tr><td>Outlet pressure drop coefficient</td><td>1</td></tr></table></body></html>

![](images/4c2366e925226e233a80cc4dff44f32225e526394c24f5539341650038477060.jpg)  
Fig.3The inlet flow versus time

Fig.5 shows that the wave curve of the inlet flow versus time in the case of considering heat storage of the tube wall metal is quicker to restore to the initial state than the flow fluctuation without considering heat storage.It means that the flow in the water wall is more stable with heat storage.This phenomenon indicates that the heat storage of metal is an influence on the dynamic characteristics of the furnace,so it's necessary to consider the heat storage of metal when analyze the flow instability of aboiler.

![](images/5e644dc9b7cc61ea1c364f925e755d704f041a428a85b50bfb54e377687bbde3.jpg)  
Fig.4The outlet temperature distribution of section

![](images/b177f2d04da585481b2173cfdb75871f6b0eb2d2de1b66fdae79f71b8c39fa99.jpg)  
Fig.5Effect of heat storage on the inlet flow

# Analysis of flow instability in supercritical CFB boiler with annular furnace

# Annularfurnace

Fig.6 shows the simple structure of the annular furnace.The furnace ofboiler is divided into inner and out ring,the outer and inner ring are arranged in parallel. In front wall of the outer ring of furnace, three groups of cyclone separator are set, the same arrangement in back wall. Not only more water cooling walls can be arranged in this structure to obtain enough heat exchange areas, but also this structure reduces the height of furnace and reduces the power consumption of the circulating pump.

In this paper,we selected the sixth loop of the front wall as object of study, the initial calculating parameters are expressed in Table.2.The tube in the loop is vertical smooth tubes withlow mass flow,of which the inner and outer diameters are $1 9 \mathrm { m m }$ and $3 2 \mathrm { m m }$ ，while the length is $5 5 . 6 0 2 6 \mathrm { m }$

![](images/f45e8dbc0459f6b7cb3e54eb04f10794609c9e74451dc22153e7c489a99d09b4.jpg)  
Fig.6Structure of annular furnace

Fig.7 and Fig.8 show the pipeline structure and heat load distribution, the distribution of heat load along the height ofthe furnace is not uniform.According to the characteristics of heat flux distribution along the furnace height, the water wall is divided into more sections where the heat flux experiences a sharp heat flux change and is divided into fewer sections where the heat flux expe riences a gentle heat flux change [29].By doing this, the characteristic ofnon-uniform distribution ofheat flux can be fully considered in calculations.In this paper, the water wall is firstly divided into 33 sections and each section is further divided into equal length which is equivalent to the space step size $\Delta z$ .Fig.7 shows the length of each section in which the heat flux is uniformly distributed. Take the space grid length about $0 . 1 \mathrm { m }$ ，the loop can be divided into 560 segments,take two constants as the time step $\Delta t$ to ensure the independence between time and space step.From O to $\mathrm { ~ 1 ~ s ~ }$ ,the time step is O.1s.From 1 to $5 0 0 \mathrm { ~ s ~ }$ ,the time step takes $1 . 0 \mathrm { ~ s ~ }$

Table 2 Initial calculating parameters   

<html><body><table><tr><td>Parameter</td><td>Value</td></tr><tr><td>Inlet pressure</td><td>10.16 MPa</td></tr><tr><td>Inlet enthalpy</td><td>1343.1 kJ/kg</td></tr><tr><td>Inlet mass flow rate</td><td>0.0653 kg/s</td></tr><tr><td>Inlet pressure drop coefficient</td><td>0</td></tr><tr><td>Outlet pressure drop coeficient</td><td>0</td></tr></table></body></html>

![](images/200fae08091f269f5a2ffbb6e29a5e54a4c631d31a4e7c58f6c9bdb6c00c6568.jpg)  
Fig.7Geometry of water wall

![](images/80e69e98ae702c8ffc9cc76bea0ccd35b0efe1a93814e6c7b7bdb8602ecc37ec.jpg)  
Fig.8Heat load distribution versus time

# The dynamic characteristics of furnace

The dynamic instability of the furnace occurs when the heat flux density is changed for some reasons. The inlet and outlet of the loop will form a reciprocating cycle mode in which the flow rate increase or decrease when the dynamic instability occurs.If the resistance characteristics of the furnace and the fluctuation of the flow reach a certain resonance, then the flow fluctuations will always be in a stable state of fluctuation and will not decay. In some cases, the temperature of the tube is changed frequently, which leads to fatigue failure of pipe and is not conducive to the safe operation ofthe boiler,so it should be avoided.In the case of considering heat storage of the tube metal, applying 1.2 times heat load disturbance on the sixth loop, the fluctuation of the inlet flow rate and outlet flow rate versus time is shown in Fig.9.

It can be seen from Fig.9, the inlet flow rate and outlet flow rate versus time were reversed phase fluctuation,when the inlet flow rate increases,the outlet flow rate decreases, when the inlet flow rate decreases, the outlet flow increases,the amplitude of the inlet flow rate and outlet flow rate decreases gradually with time,eventually the outlet flow rate equaled to the inlet flow rate and restore to a steady state, suggesting thatthe flow conditionis stable.

# Analysisofthetemperature

Without the heat load disturbance, the inlet pressure of the sixth loop at steady state is $1 0 . 1 6 ~ \mathrm { M P a }$ ,the inlet enthalpy is $1 3 4 3 . 0 9 7 ~ \mathrm { k J / k g }$ and the inlet flow rate is 0.065 $\mathrm { k g / s }$ .On the basis of steady state,1.2 times heat load disturbance is applied on the sixth loop.The simulation results are shown as follows:

Fig.l0 shows the average temperature of fluid at steady state and the wall temperature in three cases.At $4 . 1 \mathrm { ~ s ~ }$ ，the heat load reaches the maximum value and the inlet flow rate drops to the minimum value; but at $\begin{array} { r } { 1 3 . 1 \ \mathrm { s } , } \end{array}$ the inlet flow rate reaches the maximum value and the heat load recoveries to the initial value. In Fig.lO,the inflection point of each curve is the phase transition point. Take the steady state as an example, there are two inflection points in the curve of average temperature distribution,one is in the 8th section and the other one is in the 26th section,which means the fluid in the first seven sections is in the single phase liquid state, the fluid which is in the section of 8\~26th is in the two-phase region, the fluid in the remaining sections is superheated steam. From 1 to $5 0 0 ~ \mathrm { s } .$ ，the maximum temperature of the tube wall is $4 3 5 \mathrm { ^ \circ C }$ ，which is in the allowable range,so the operation of boileris safe and reliable.

![](images/6b035bee7d2dad38f589bbb29195f10149626f2b5875771fd2c2ac18449d6b02.jpg)  
Fig.9The flow versus time

![](images/4667d9e44deff5e521acf33ffa012e34ce2645a4e00dc86c13f2f07b328225f8.jpg)  
Fig.10The average temperature of section

Fig.11 and Fig.12 exhibit the temperature fluctuation of the 55th control volume (single phase region) and the 275th control volume (two-phase region). From Fig.11 and Fig.l2,the fluid temperature and wall temperature fluctuated with time finally remained at constant values. The wall temperature in the single phase liquid zone is only $1 . 5 \mathrm { ^ \circ C }$ higher than the fluid temperature,but the valueof temperature difference between the wall temperature and the fluid in the two-phase region is $2 . 8 \mathrm { { ^ \circ C } }$

![](images/bcc6831c244ee7c3d517df0ced7c8775134ec9cb29ed373db5d3007645ef13e9.jpg)  
Fig.11The temperature of 55th segment versus time

![](images/73a8df4900e4b91bbb0f82a0e90dc7342a408ce35052c95b62b5497cfc1821ee.jpg)  
Fig.12The temperature of 275th segment versus time

# Conclusion

In this study,a general model considering the heat storage of the tube wall metal is proposed. In order to further expand the study of supercritical flow instability of boiler,a numerical program applying time-domain method is developed. The program is capable to simulate the flow instability of boiler with various geometric structures and thermal parameters and calculate the temperature of tube wall. Comparisons with the data of Dynastab numerical calculation show that the present model is suitable and adequate for the analysis of flow instability in water wall and the temperature calculation of the tube wall, so it can be used for practical engineering application.

Thenumerical analysis of the flow instability in water wall of a supercritical CFB boiler with annular furnace show that applying 1.2 times heat load disturbance on the loop,the inlet flow rate and outlet flow rate versus time werereversed phase fluctuation and eventually the outlet flow rate equaled to the inlet flow rate, the wall temperature fluctuated with time also remained at constant values. suggesting that the flow condition was stable.In addition, the results also showed that in the case of considering the heat storage, the flow in the water wall is easier to return to stable state than without considering heat storage.

# Acknowledgments

This work was supported by the “Strategic Priority Research Program” of the Chinese Academy of Sciences, Grant No. XDA07030100 and the National Key Technology R&D Program of China during the 12th Five-YearPlanPeriodNo.2015BAA03B01-01.

# References

[1]T.J. Zhang,J. T. Wen, Y. PELES,et al., Two-phase refrigerant flow instability analysis and active control in transient electronics cooling systems, International Journal of Multiphase Flow. 37(2011) 84-97.   
[2] T.Xiong,X.Yan,Z.J.Xiao,et al.,Experimental study on flow instability in parallel channels with supercritical water,Annals of Nuclear Energy. 48 (2012) 60-67.   
[3] T.Xiong,X.Yan,S.F.Huang,etal.,Modeling and analysis of supercritical flow instability in parallel channels, International Journal of Heat and Mass Transfer .57(2) (2013) 549-557.   
[4]L. C. Ruspini, C.P. Marcel,A. Clausse, Two-phase flow instabilities:A review, International Journal ofHeat and Mass Transfer 71 (4). (2014) 521-548.   
[5]Z. W. Li, X. B. Sun, Z. H. Shi, Hydrodynamic calculation of a $6 0 0 ~ \mathrm { M W }$ supercritical CFB boiler, Thermal Power Generation.12(2006)7-9(in Chinese).   
[6] W.X.Tian,X.Y.Tian,F.Jian,etal.,Flow instability analysis of supercritical water-cooled reactor CSR1000 based on frequency domain, Nuclear Power Engineering. 34 (1) (2013) 45-51(in Chinese).   
[7]D. Yang,J.Pan, Chenn Q. Zhou, et al., Experimental investigation on heat transfer and frictional characteristics ofvertical upward rifled tube in supercritical CFBboiler, Experimental Thermal and Fluid Science.35 (2011) 291-   
[8]J. Pan,D. Yang, G. M. Chen,X. Zhou, Q. C. Bi, Thermal-hydraulic analysis of a $6 0 0 ~ \mathrm { M W }$ supercritical CFB boiler with low mass flux, Applied Thermal Engineering. 32(2012)41-48.   
[9]J.Pan,G. Wu,D. Yang,Thermal-hydraulic calculation and analysis on water wall system of 60oMW supercritical CFB boiler, Applied Thermal Engineering.82 (2015) 225-236.   
[10]Y. R. Shen, D. Yang,L. Wang,B.B.Xie, Numerical Analysis of Flow Instability in 6Oo MW Supercritical W Flame Boiler, Journal of Xi'an Jiaotong University. 49 (5) (2015)68-72.   
[11]T. T. Yi, S. Koshizuka, Y. Oka,A linear stability analysis of supercritical water reactors,(I) thermal-hydraulic stability, Journal of Nuclear Science and Technology. 41 (12) (2004) 1166-1175.   
[12]P. F. Liu, D. Hou, M. Lin, et al., Stability analysis of parallel-channel systems under supercritical pressure with heat exchanging, Annals of Nuclear Energy. 69 (2014) 267-277.   
[13]S. Zheng, Z. X. Luo, Y. X. Deng, et al., Development of a distributed-parameter model for the evaporation system in a supercritical W-shaped boiler, Applied Thermal Engineering. 62 (2014) 123-132.   
[14]W. S. Wang, X. J. Zhu, Q. C. Bi, et al., Heat sensitivity of vertical water wall at low mass velocity in supercritical pressure W-shaped flame boiler, International Journal of Thermal Sciences.53 (2012) 202-208.   
[15]J. Pan, D. Yang, R.G Xiao, Experimental investigation on frictional resistance characteristics of optimized rifled tube at low mass flux, Chinese High Technology Letters. 24 (4) (2014) 429-423(in Chinese).   
[16]The National Standard of the Boiler Hydrodynamics Calculation (JB/Z201-83)， Shanghai Power Equipment Packaged Design Research Institute, Shanghai, 1983 (in Chinese).   
[17]T. T. Yi, J. Liu, S.Koshizuka, Y. Oka, Thermal and stability considerations of super LWR during sliding pressure startup,Journal of Nuclear Science and Technology. 42 (2005) 537-548.   
[18]Y. F. Zhang, H. X. Li,L. X. Li, et al.,A new model for studying the density wave instabilities of supercritical water flows in tubes,Applied Thermal Engineering.75 (2015)397-409.   
[19]Y. F. Zhang, H. X. Li,L. X.Li, et al., Study on two-phase flow instabilities in internally-ribbed tubes by using frequency domain method, Applied Thermal Engineering. 65 (1-2) (2014) 1-13.   
[20]G. T. Ortega,A. Class,R. T. Lahey, et al., Stability analysis of a uniformly heated channel with supercritical water, Nuclear Engineering and Design. 238(8)(2008) 1930- 1939.   
[21]M. Sharma, D. Pilkhwal, P. Vijayan, et al., Steady state and linear stability analysis of a supercritical water natural circulation loop, Nuclear Engineering and Design. 240 (2010) 588-597.   
[22]T.T.Yi, S.Koshizuka,Y. Oka,A linear stability analysis of supercritical water reactors,(II) coupled neutronic thermal-hydraulic stability, Journal of Nuclear Science and Technology.41 (12) (2004) 1176-11860   
[23]J.L. Munoz-Cobo,M. Z. Podowski, S.Chiva,Parallel channel instabilities in boiling water reactor systems: boundary conditions for out of phase oscillations,Annals of Nuclear Energy. 29 (16) (2002) 1891-1917.   
[24]W. Ambrosini,M. Sharabi, Dimensionless parameters in stability analysis of heated channels with fluids at supercritical pressures,Nuclear Engineering and Design. 238 (2008) 1917-1929.   
[25]Y. Guo, S. Z. Qiu, G H. Su, et al., Theoretical investigations on two-phase flow instability in parallel multichannel system,Annals of Nuclear Energy.35(4) (2008) 665-676.   
[26]V. Chatoorgoon, Stability of supercritical fluid flow in a single-channel natural-convection loop, International Journal of Heat and Mass Transfer .44 (2001) 1963-1972.   
[27]Y.L. Su, J. Feng,H. Zhao, et al., Theoretical study on the flow instability of supercritical water in the parallel channels,Progress in Nuclear Energy. 68 (2013) 169-176.   
[28]V. Chatoorgoon,A. Voodi, D. Fraser, The stability boundary for supercritical flow in natural convection loops: part I: $\mathrm { H } _ { 2 } \mathrm { O }$ studies,Nuclear Engineering and Design. 235 (2005) 2570-2580.   
[29]J.Pan,D. Yang,H. Yu, et al., Mathematical modeling and thermal-hydraulic analysis of vertical water wall in an ultra supercritical boiler,Applied Thermal Engineering. 29 (2009) 2500-2507.