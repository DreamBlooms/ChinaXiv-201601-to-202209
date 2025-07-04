# Computational Study of Performance Characteristics for Truncated Conical Aerospike Nozzles

Prasanth P Nair1,Abhilash Suryan1 and Heuy Dong Kim²

1.Department of Mechanical Engineering, College of Engineering Trivandrum,Trivandrum,695016,India   
2. Department of Mechanical Engineering,Andong National University,Andong,760749, Korea

Aerospike nozles are advanced rocket nozzles that can maintain its aerodynamic eficiency over a wide range of altitudes.It belongs to class ofaltitude compensating nozzes.Avehicle with anaerospike nozzle uses less fuel at lowaltitudes due to its altitude adaptabilitywhere most missons have the greatest need for thrust.Aerospike nozles are beter suited to Single Stage to Orbit (SSTO) missions compared to conventional nozzles.In the current study, the flow through $20 \%$ and $40 \%$ aerospike nozzle is analyzed in detail using computational fluid dynamics technique.Steady state analysis with implicit formulation is carredout.Reynolds averaged Navier-Stokes equations are solved with the Spalart-Allmaras turbulence model.The resultsare compared with experimental results from previous work. The transition from open wake to closed wake happens in lower Nozzle Pressure Ratio for $20 \%$ as compared to $40 \%$ aerospike nozzle.

# Keywords: aerospike nozzle,plug nozzle,advanced rocket nozzes, thrust coefficient,base pressure.

# Introduction

dual-expander nozzle.All these nozzle concepts have altitude compensating capabilities.

Conventional bell nozzles are not suited for Single Stage To Orbit (SSTO) missions on account of the fixed geometry which cannot compensate performance at varying altitudes.The performance is reduced at low altitudes due to overexpansion and at high altitudes due to under expansion.At low altitude where the atmospheric pressure is high,the flow gets compressed radially inWards towards the nozzle exit.This can cause formation ofMach disc and flow separates from the boundary wall within the nozzle and hence,decreasing the efficiency as shown in Fig.1(a).At higher altitudes,the atmospheric pressure decreases,causing the exhaust gases to continue to expand beyond the nozzle exit. This external expansion does not exert force on the nozzle wall, resulting in reduced thrust and hence,again decreasing the engine efficiency as shown in Fig. 1(b). There are studies on different types of advanced unconventional rocket nozzles which can be used efficiently in the future to replace conventional bell nozzles. The different types of rocket nozzles discussed by Hagemann [1] are plug nozzle,expansion-deflectionnozzle， dual-bellnozzle，and

Plug (spike) nozzle can be described as bell nozzle inside out.Unlike in bell nozzle,the exiting gases in plug nozzles are not contained by the outer boundary. The spike prevents turbulent mixing in the exhaust flow that would occur in its absence,while maintaining isentropic expansion.For aerospike nozzles, the spike is truncated which keeps the flowin closed wake rather than in open wake athigh altitudes.

At low altitudes,when the atmospheric pressure is high,the exhaust remains close to the nozzle contour, and at higher altitudes,recompression shock waves occur inside the plume,forcing the plume to remain column-shaped in a closed-wake state,irrespective of expanding exhaust plume shape.This maintains efficiency because the exhaust gases are not expanding past the physical nozzle,but still exerting force on the nozzle as shown in Fig.2.The performance loss due to truncation at high altitudes is countered by providing secondary flow into the base region,hence the name aerospike as given by Rocketdyne.Aerospike or trun cated plug nozzle was first proposed by Griffith[2] in 1954 and then upheld by Rocketdyne from the beginning of 1960s [3].Different methods for contouring of nozzle surface were proposed by Rao [4] and Angelino [5] to optimize the thrust.

![](images/1416144cd3b759c5e7f17952718a1a4fc09378734ddc98fa61e358a89cf4c8c2.jpg)  
Fig.1Flow phenomena for a conventional rocket nozzle: (a) Overexpansion; (b) Under expansion [1]

An analytical method was presented by Migdal [6] for the design of axisymmetric annular nozzles to yield uniform and axial flow. Sule et al.[7] studied base pressure characteristics of annular truncated plug nozzle.

In 1997, Rocketdyne,conducted the Linear Aerospike SR-71 Experiment (LASRE) program to demonstrate the performance of the linear aerospike on a lifting body to simulate the X-33. This was accomplished by mounting a $20 \%$ scale, X-33 fore body onto an SR-71 [8]. Tomita et al.[9-11] performed experimental studies on linear and clustered plug nozzles.Research was also conducted in Europe on clustered plug nozzles [12]. Bui et al.[13] conducted flight research on aerospike nozzle using solid motor rocket.

In the current study, computational fluid dynamics (CFD) simulation is performed on a $1 5 ^ { \mathrm { { \circ } } }$ annular conical aerospike nozzle (design Mach number 2.O) without free stream flow[14].The simulation is conducted on $40 \%$ of the spike length and $40 \%$ of the spike length with different Nozzle Pressure Ratios (NPR). NPR is the ratio of jet stagnation pressure $( \mathrm { P _ { o j } } )$ and ambient pressure $\left( \mathrm { { P _ { a } } } \right)$ . The numerical simulation results and experimental results are compared.

![](images/ddbfb353bd8306bafe2f9755ef02d0d180c15901432c63e338f9dffcef0318d7.jpg)  
Fig.2Flow phenomena of an aerospike nozzle(a) Overexpansion (b) Under expansion

# Experimental details and modeling

Experimental study of Verma [14] is considered for validating the numerical results.Experiments were conducted in a $0 . 5 \mathrm { m }$ base flow facility, in a special purpose blow down-type tunnel. The results in the experiment indicated good mean flow uniformity and axisymmetry of the jet flow in the tunnel.

Design Mach number 2.0 conical ( $1 5 ^ { \mathrm { { \circ } } }$ half-angle) annular aerospike model was mounted on the central cylin drical inner body. The truncated nozzle had two static pressure ports in the base to acquire base pressure.Exit nozzle radius $\mathrm { ( r _ { e } ) }$ was fixed as $2 5 ~ \mathrm { m m }$ . The annular gap at throat $\mathrm { ( h _ { t } ) }$ is $9 \ \mathrm { m m }$ ，as shown in Fig.3.Jet stagnation pressure $\mathrm { { \cal P } _ { \mathrm { o j } } }$ was changed to vary NPR[14].

![](images/5eba450d232e70d1162ef3c5d3986383d9773d02be91ce3756cd9a038308cc31.jpg)  
Fig.3Schematic of the experimental annular conical aerospike nozzle model

# Numerical method

Numerical modeling and analysis of flow for aerospike nozzle with different plug shapes was done using ANSYS Fluent. Reynolds averaged NavierStokes (RANS) solver was used along with one equation Spalart-Allmaras turbulence model.

In this study,2-D computation is done assuming axisymmetric flow.The domain varies from 6OD(where D is exit nozzle diameter) horizontally to 1oD vertically and 5D in the upstream of the throat as shown in Fig.4 (a).Inlet is at 2.5D from the upstream of throat. The mesh is generated in ICEM CFD,with the first grid point from either the spike or the cowl wall giving a $\mathrm { y + }$ .The mesh is finer at the throat region as shown in Fig. 4 (b).

The grid independence study was conducted on the $40 \%$ aerospike nozzle to reduce influence of grid on the computational result.The coefficient of thrust,mass flow rate,velocity and pressure at the exit were compared to select the computational grid as shown in Table 1.On comparison, the values are almost constant for coarse and fine mesh.Hence coarse mesh was selected for the computational study to reduce the computational time. The computational grid selected was O.156893 million for $40 \%$ aerospike nozzle and 0.155133 million for $20 \%$ aerospike nozzle. The governing equations used are as follows:

Table 1 Grid independence study for nozzle with $40 \%$ spike   

<html><body><table><tr><td>S1. No.</td><td>Cells</td><td>Mass flow rate at nozzle exit (kg/s)</td><td>Velocity at nozzle exit (m/s)</td><td>Pressure at nozzle exit (Pa)</td><td>Coefficient of Thrust</td></tr><tr><td>1.</td><td>156893</td><td>0.682836</td><td>433.3473</td><td>67553.96</td><td>0.810273</td></tr><tr><td>2.</td><td>310613</td><td>0.682829</td><td>433.3339</td><td>67558.63</td><td>0.810349</td></tr><tr><td>3.</td><td>614188</td><td>0.682773</td><td>433.3197</td><td>67559.49</td><td>0.810236</td></tr></table></body></html>

![](images/c28f23e330e14a32cd5695ad5140dccde122e58a6a7013897b3c399fc67ec65f.jpg)  
Fig.4Domain of nozzle numerical model: (a) overall computational domain (b） closer view of computational 3rid in the area of the nozzle region

Mass Conservation Equation:

For 2D axisymmetric geometries, the continuity equation is given by:

$$
\frac { { \partial \rho } } { { \partial t } } + \frac { { \partial } } { { \partial x } } { \left( { \rho v _ { x } } \right) } + \frac { { \partial } } { { \partial r } } { \left( { \rho v _ { r } } \right) } + \frac { { \rho v _ { r } } } { r } = 0
$$

where $\mathbf { \boldsymbol { x } }$ is the axial coordinate,ris the radial coordinate, $\mathbf { V } _ { \mathbf { X } }$ is the axial velocity, and $\mathbf { V } _ { \mathrm { r } }$ is the radial velocity.

Momentum Conservation Equation:

For 2D axisymmetric geometries,the axial and radial

momentum conservation equations are given by:

$$
\begin{array} { l } { \displaystyle \frac { \hat { \partial } } { \partial t } ( \rho \upsilon _ { x } ) + \frac { 1 } { r } \frac { \hat { \partial } } { \hat { \partial } x } ( r \rho \upsilon _ { x } \upsilon _ { x } ) + \frac { 1 } { r } \frac { \hat { \partial } } { \partial x } ( r \rho \upsilon _ { r } \upsilon _ { r } ) } \\ { \displaystyle = - \frac { \hat { \partial } p } { \hat { \partial } x } + \frac { 1 } { r } \frac { \hat { \partial } } { \hat { \partial } x } \Bigg [ r \mu \Bigg ( 2 \frac { \hat { \partial } \upsilon _ { x } } { \hat { \partial } x } - \frac { 2 } { 3 } \big ( \nabla \bar { \upsilon } \big ) \Bigg ) \Bigg ] } \\ { \displaystyle + \frac { 1 } { r } \frac { \hat { \partial } } { \hat { \partial } x } \Bigg [ r \mu \Bigg ( \frac { \hat { \partial } \upsilon _ { x } } { \hat { \partial } r } + \frac { \hat { \partial } \upsilon _ { r } } { \hat { \partial } x } \Bigg ) \Bigg ] } \end{array}
$$

and

$$
\begin{array} { l } { \displaystyle \frac { \hat { \mathcal { O } } } { \hat { \mathcal { O } } t } ( \rho v _ { r } ) + \frac { 1 } { r } \frac { \hat { \mathcal { O } } } { \hat { \mathcal { D } } x } ( r \rho v _ { x } v _ { r } ) + \frac { 1 } { r } \frac { \hat { \mathcal { O } } } { \hat { \mathcal { D } } r } ( r \rho v _ { r } v _ { r } ) } \\ { \displaystyle = - \frac { \hat { \mathcal { O } } p } { \hat { \mathcal { D } } r } + \frac { 1 } { r } \frac { \hat { \mathcal { O } } } { \hat { \mathcal { D } } r } \bigg [ r \mu \bigg ( \frac { \hat { \mathcal { O } } v _ { r } } { \hat { \mathcal { O } } x } + \frac { \hat { \mathcal { O } } v _ { x } } { \hat { \mathcal { O } } r } \bigg ) \bigg ] } \\ { \displaystyle + \frac { 1 } { r } \frac { \hat { \mathcal { O } } } { \hat { \mathcal { D } } r } \bigg [ r \mu \bigg ( 2 \frac { \hat { \mathcal { O } } v _ { r } } { \hat { \mathcal { O } } r } - \frac { 2 } { 3 } \big ( \nabla \bar { x } \big ) \bigg ) \bigg ] } \\ { \displaystyle - 2 \mu \frac { v _ { r } } { r ^ { 2 } } + \frac { 2 } { 3 } \frac { \mu } { r } ( \nabla \bar { x } ) } \end{array}
$$

Energy Equation:

Turbulent heat transport is modeled using the concept of Reynolds' analogy to turbulent momentum transfer. The energy equation is thus given by the following:

$$
\begin{array} { l } { \displaystyle \frac { \hat { \sigma } } { \hat { \sigma } t } \big ( \rho E \big ) + \frac { \hat { \sigma } } { \hat { \sigma } x _ { i } } \Big [ u _ { i } \big ( \rho E + p \big ) \Big ] } \\ { \displaystyle = \frac { \hat { \sigma } } { \hat { \sigma } x _ { j } } \Bigg [ \Bigg ( k _ { T } + \frac { c _ { p } \mu _ { t } } { \mathrm { P r } _ { t } } \Bigg ) \frac { \hat { \sigma } T } { \hat { \sigma } x _ { j } } + u _ { i } \left( \tau _ { i j } \right) _ { e f f } \Bigg ] } \end{array}
$$

Where $\mathbf { k } _ { \mathrm { T } }$ ，is the thermal conductivity, $\mathrm { ~ E ~ }$ is the total energy, and $\left( \tau _ { i j } \right) _ { e f f }$ is the deviatoric stress tensor.

Spalart-Allmaras TurbulenceModel:

Thetransported variable in the Spalart-Allmaras turbulence model [15], $\tilde { v }$ is identical to the turbulent kinematic viscosity. Transport Equations for $\tilde { v }$ is given by:

$$
\begin{array} { l } { \displaystyle \frac { \hat { \mathcal { O } } } { \hat { \omega } t } \big ( \rho \tilde { \upsilon } \big ) + \frac { \hat { \mathcal { O } } } { \hat { \omega } x _ { i } } \big ( \rho \tilde { \upsilon } u _ { i } \big ) } \\ { \displaystyle = G _ { \upsilon } + \frac { 1 } { \sigma _ { \tilde { \upsilon } } } \Bigg [ \frac { \hat { \mathcal { O } } } { \hat { \alpha } x _ { j } } \Bigg \{ \big ( \mu + \rho \tilde { \upsilon } \big ) \frac { \hat { \alpha } \tilde { \upsilon } } { \hat { \alpha } x _ { j } } \Bigg \} + C _ { b 2 } \rho \Bigg ( \frac { \hat { \alpha } \tilde { \upsilon } } { \hat { \alpha } x _ { j } } \Bigg ) ^ { 2 } \Bigg ] } \end{array}
$$

In these equations, $G _ { \upsilon }$ is the production of turbulent viscosity and $Y _ { \upsilon }$ is the destruction of turbulent viscosity. $\sigma _ { \tilde { v } }$ and $\mathrm { C } _ { \mathrm { b } 2 }$ are constants and $\upsilon$ is the molecular kinematic viscosity.

# Comparison of flow structure with experimental result

For $40 \%$ truncated spike, the Schlieren images of experimental results of NPR 2.57,4.15 and 7.0 are compared with shadowgraph obtained from numerical results. Due to truncation, trailing shock and recirculation occurs at the base region of nozzle.Flow features that can be observed from these results are compression shocks,external jet boundary which developed from the cowl exit, the internal nozzle overexpansion shock originating from cowl lip,and the overexpansion shock formed on the nozzle surface.At low NPR,interaction between overexpansion shocks on nozzle surface results in flow separation.While increasing the NPR,the angle of these shocks is changed as the internal nozzle operates from over expansion condition to under expansion condition. The flow conditions on the nozzle can be classified into three types as‘A’，‘B’ and‘C’. In type‘A’ flow, the change of angle for the overexpansion shocks from the internal nozzle alters the interaction between overexpansion shocks at the cowl lip and nozzle surface in a way that the reflected shock causes flow to reattach on the plug surface causing a separation bubble as shown in Fig.5,which increases the pressure at the base.The reattachment of flow can cause undesirable side force.The flow on the plug further expands around the corner, which further decreases the base pressure.In type‘B" flow, the overexpansion shock stays exactly at the corner of the truncation as shown in Fig. 6.

When internal nozzle begins to operate in the underexpanded condition, the expansion fan from the cowl lip inflicts the inner shear layer, this leads to the generation of a strong trailing shock that is visible in Fig.7 for NPR 7.0, this flow is type‘C', the nozzle operates in closed wake condition [14].

![](images/62e6dcdec9daa6eff73e4651aa2d5f38080276a55c86e0e3b07692ddd2516a79.jpg)  
Fig.5Flow structure for $40 \%$ spike at NPR 2.57: (a) Experimental Schlieren image [14];(b) Numerical shadow

![](images/d8c24a672b7586cb19a14a33b29f16e29056f2d296adede350495b861eb1c6f3.jpg)  
Fig. 6Flow structure for $40 \%$ spike at NPR 4.15: (a) Experimental Schlieren image [14], (b) Numerical shadowgraph

![](images/7d671817e03cd7a21ac524ecb6446f51b12f6e4b0dbdca7c3383aafc6212c83a.jpg)  
Fig.7Flow structure for $40 \%$ spike at NPRe 7.O: (a) Experimental Schlieren image [14],(b) Numerical shadowgraph

# Pressure ratio along the base for $4 0 \%$ spike

The base pressure comparison of experimental and numerical results in $40 \%$ spike nozzle is plotted for varying NPR.The ratio of pressure at base $( \mathrm { P _ { b } } )$ and jet stagnation pressure $( \mathrm { P _ { o j } } )$ is plotted against NPR in Fig. 8. Two major flow regimes,open wake and closed wake can be identified [10,16-18] from Fig.8.The one in which base pressure ratio $( \mathrm { P _ { b } } / \mathrm { P _ { o j } } )$ continues to decrease sharply and later, in which the base pressure ratio is constant.The open wake is based on the influence of ambient pressure on base pressure. While analyzing Fig. 8, there is a decrease in base pressure ratio $\mathrm { P _ { b } / P _ { o j } }$ ，tillNPR 5.6 for experimental result and NPR 6 for numerical result,which corresponds to open wake regime,after the transition from open wake to closed wake the base pressure remains constant since base pressure is not affected by ambient pressure [16].

# Performance characteristics: $4 0 \%$ spike

Coefficient of thrust obtained in experimental study is compared with current numerical results with respect to varying NPR.The comparison for the nozzle with $40 \%$ spike is shown in Fig. 9.

![](images/da8bf7681fad2a18a0a80235a97a60bd515d57eba5887bcb5105da5e0682fa59.jpg)

![](images/7c9a0a5d154364995457cc7ac5a449ee4cfc14bbd0dc9156b5ca115cf88255f8.jpg)  
Fig.8Comparison of experimental and numerical base pressure measurements for $40 \%$ spike; $\mathrm { P _ { b } / P _ { o j } }$ vs NPR

The thrust of the nozzles were found out using thefollowing formula [14,19]:

$$
\begin{array} { l } { F = \left[ m V _ { e x i t } + \left( P _ { e x i t } - P _ { a } \right) A _ { e x i t } \right] } \\ { + \displaystyle \int \left( P _ { w } - P _ { a } \right) \cos { 7 } 5 d A + \left( P _ { b } - P _ { a } \right) A _ { b } } \end{array}
$$

Where dA, is the elemental area on the spike surface, $\mathrm { P _ { w } }$ is the wall pressure and $\mathrm { { \Delta P _ { a } } }$ ，the ambient pressure. The coefficient of thrust of a nozzle is given by [19]:

$$
C _ { f } \left( \boldsymbol { x } \right) = { F } \mathord { \left/ { \vphantom { F } } \right. \kern - delimiterspace } \left( A _ { t } P _ { o j } \right) 
$$

The numerical $\mathrm { C _ { f } }$ is in match with the experimental result for $40 \%$ spike. Numerical results of $40 \%$ spike nozzle are used to compare the base pressure and $\mathrm { C _ { f } }$ of $20 \%$ spike nozzle.For $20 \%$ spike nozzle, the base pressure decreases and becomes constant at NPR 5.7 as shown in Fig.10. On comparing $20 \%$ spike nozzle with $40 \%$ spike nozzle it is seen that transition from open wake to close wake regime happens at lower NPR.

![](images/303cea4969e6a156e03c27718cc966952bec4a12a866c64bf4dafc82e5ff1be7.jpg)  
Fig.10Comparison of base pressure measurement between $20 \%$ aerospike nozzle and $40 \%$ aerospike nozzle, $\mathrm { P _ { b } / P _ { o j } }$ Vs NPR

Although truncation of nozzle leads to reduction in thrust as shown in Fig. 11,but for practical purpose transition at low NPR is preferable and at higher NPR larger base area is advantageous as it contributes in increased thrust [2O].The thrust loss can be compensated by providing a secondary flow through the base.

![](images/091ba7db31f76a4b059c8491466900dca1ea0198551cc37af7fc6d817127bd20.jpg)  
Fig.9Comparison of experimental and numerical coefficient of thrust for $40 \%$ spike, $\mathbf { C } _ { \mathrm { f } } ( \mathbf { x } )$ Vs NPR   
Fig.11 Coefficient of thrust; comparison between $20 \%$ spike and $40 \%$ spike; $\mathbf { C } _ { \mathrm { f } } ( \mathbf { x } )$ Vs NPR

# Conclusion

The base pressure, shock pattern, flow structure and performance characteristics of numerical result agrees with the experimental data. The flow separation due to restricted shock separation at low NPR can result in undesirable side or lateral forces.In order to reduce this effect, truncated plug nozzles are suggested in which there is no reattachment of flow due to shorter length Due to truncation there is the reduction in thrust but transition from open wake to closed wake occurs in lower NPR.

# Acknowledgement

This work was supported by Advanced Research Center Program (NRF-2013R1A5A1073861) through the National Research Foundation of Korea (NRF) grant funded by the Korea government (MSIP） contracted through Advanced Space Propulsion Research Center at Seoul National University. (Project Number: 0659-20160012).

# References

[1]Hagemann, G., Immich,H., Nguyen,T.V.and Dumnov, G.E.,(1998),“Advanced Rocket Nozzles", Journal of Propulsion and Power, vol. 14, no.5,pp. 620-634.   
[2]Griffith,A.A.,(1954),“Jet Propulsion Nozzle for Use at Supersonic Jet Velocities”,Patent No.2,683,962,RollsRoyce.   
[3]Sutton, G.P.,(20o6),“History of Liquid Propellant Rocket Engines", AIAA, Reston, VA, Chap.7, pp.339-340.   
[4]Rao，G.V.R.，(1961)，“Spike Nozzle Contours for Optimum Thrust”, Planetary and Space Science 4,pp. 92-101.   
[5]Angelino,G.,(1964)，“Approximate Method for Plug Nozzle Design", AIAA Journal, vol. 2, no.10, pp. 1834- 1835.   
[6]Migdal，D.，(1972)，“Supersonic AnnularNozzles", Journal of Spacecraft and Rockets,vol.9,no.1,pp.3-6.   
[7]Sule，W.P.and Mueller，T.J.，(1973)，“Annular Truncated Plug Nozzle Flowfield and Base Pressure Characteristics”,Journal of Spacecraft and Rockets,vol. 10, No. 11, pp. 689-695.   
[8]Kutin， M. S.， (1997)，“LinearAerospike SR-71 Experiment (LASRE) Rocket Engine",AIAA 97-3319, 33rd Joint Propulsion Conference and Exhibit, Seattle, WA,USA.   
[9]Tomita, T.,Tamura,H.and Takahashi,M.,(1996),“An Experimental Evaluation of Plug Nozzle Flowfields”, AIAA 96-2632,32nd Joint Propulsion Conference and Exhibit,Lake Buena Vista,FL,USA.   
[10]Tomita,T.，Tamura,H.and Takahashi,M.,(1997), “Flowfield of Clustered Plug Nozzles",AIAA 97-3219, 33rd Joint Propulsion Conference and Exhibit,Seattle, WA, USA.   
[11]Tomita,T.,Takahashi,M., Onodera, T.and Tamura,H., (1998),“Visualization of Shock Wave Interaction on the Surface of Aerospike Nozzles"，AIAA 98-3523，34th AIAA/ASME/ SAE/ASEE Joint Propulsion Conference and Exhibit, Cleveland, OH, USA.   
[12]Vuillamy,D.,Duthoit,V.and Berry，W.，(1999), “European Investigation of Clustered Plug Nozzles”, A I A A 99-2350, $3 5 ^ { \mathrm { t h } }$ Joint Propulsion Conference and Exhibit, Los Angeles, CA, USA.   
[13]Bui，T.T.，Rogers,C.E.，Murray，J.E.，Bartel，S., Cesaroni,A.and Dennett,M.,(20o5),“Flight Research of an Aerospike Nozzle Using High Power Solid Rockets”, AIAA 2005-3797, 41st AIAA/ASME/SAE/ASEE Joint Propulsion Conference and Exhibit, Tucson, Arizona, USA.   
[14]Verma, S.B.,(2o09),“Performance Characteristics of an Annular Conical Aerospike Nozzle with Freestream Effect”, Journal of Propulsion and Power,vol. 25, no. 3, pp.783-791.   
[15]Spalart, P.and Allmaras S., (1992),“A One-Equation TurbulenceModel forAerodynamic Flows”，30th Aerospace Sciences Meeting and Exhibit，Reno，NV, USA, pp. 1-22.   
[16]Ruf, J.H.and McConnaughey,P.K.,(1997),“The Plume Physics Behind Aerospike Nozzle Altitude Compensation and Slipstream Effect"，AIAA 97-3217,33rd Joint Propulsion Conference and Exhibit, Seattle,WA,USA.   
[17]Fick, M. and Schmucker,R.H.,(1996),“Performance Aspects of Plug Cluster Nozzles", Journal of Spacecraft and Rockets,vol.33,no.4,pp. 507-512.   
[18] Rommel, T., Hagemann, G., Schley, C. A., Kruelle,G. and Manski，D.，(1997)，“PlugNozzleFlowfield Analysis”, Journal of Propulsion and Power,vol.13, no. 5,pp. 629-634.   
[19]Sutton,G.P.,and Biblarz,O.,Rocket Propulsion Elements,7th ed.,Wiley Interscience,New York,2000.   
[20]Rajesh,G.,Kumar, G.,Kim,H. D., George, M.,(2012), “Computational and Experimental Simulations of the Flow Characteristics of an Aerospike Nozzle", Jourmal of the Korean Society of Visualization, vol. 10,no.1, pp. 47-54.