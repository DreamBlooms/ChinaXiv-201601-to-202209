# Investigation on Cooling Effectiveness and Aerodynamic Loss of a Turbine Cascade with Film Cooling

LIU Jianjun1, LIN Xiaochun1,², ZHANG Xiaodong1 and AN Baitao1

1.InstituteofEngineringThermophysics,ChineseAcademyofSciences11Beisihuan WestRoad,Beijing100190,China   
2. School of Physics, University of Chinese Academy of Sciences 19A Yuquan Road, Beijing 10o049, China

$\copyright$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2016

This paper describes the numerical study on film cooling effectiveness and aerodynamic loss due to coolant and main stream mixing for a turbine guide vane.The effects of blowing ratio,mainstream Mach number,surface curvature on the cooling effectiveness and mixing loss were studied and discussed.The numerical results show thatthe distributions offilm cooling efectiveness on the suction surface and pressure surface at the same blowing ratio (BR)are diferent due to local surface curvature and pressure gradient.The aerodynamic loss features for film holes on the pressure surface are also different from film holes on the suction surface.

# Keywords: turbine guide vane,film cooling,cooling effectiveness,aerodynamic loss

# Introduction

Film cooling is one of the most effective technologies to protect turbine vanes and blades from the hot gas.Previous film cooling studies focused on the influences of geometric and flow parameters on the adiabatic cooling effectiveness [1,2].The effects of blowing ratio, density ratio,turbulence intensity,hole incline/compound angle, length-diameter ratio and hole shapes on the film cooling effectiveness were well documented [3,4]. Film cooling reduces the turbine metal temperature.Meanwhile,the mixing of coolant and hot gas leads to kinetic energy loss The additional aerodynamic loss (or gain） due to the coolant and main stream mixing has a strong impact on the turbine thermal efficiency, especially for modern gas turbines in which full coverage film cooling is commonly applied.In the study of film cooling characteristics,the effects of film coolant ejection on turbine aerodynamic loss should also be taken into account.

Haller et al.[5] studied the effects of coolant ejection on the loss of vane cascade.The experiments showed that the aerodynamic loss due to coolant and main stream mixing is related to the locations of film holes,blowing ratios and exit Mach number,and the mixing loss is increased with the increase of blowing ratio.Day et al. [6] performed experiments to study the effects of coolant ejection on the aerodynamic loss of a turbine guide vane. The experimental results showed that the cascade aerodynamic loss depends on the coolant ejection location, number of film hole rows and film hole shape. The mixingloss due to fan-shaped holes is generally higher than that of round holes. The mixing loss due to the coolant ejection from the film hole on the suction surface is higher than that on the pressure surface. Gomes et al. [7] studied the effects of coolant ejection on flow separation on suction surface of a high loading turbine vane.It is found that the flow separation appearing at low Reynolds number can be restrained by the coolant ejection and the total aerodynamic loss can be reduced.Friedrichs and Hodson [8] experimentally studied the effects of endwall film cooling on the main flow. They found that coolant ejection can change the secondary flow structure in the main flow passage and even reduce the loss of secondary flow.The aerodynamic loss is enlarged with the increase of blowing ratio for the endwall film cooling. Colban and Thole [9] studied the effects of endwall film hole shape on the aerodynamic loss. They found that film cooling with fan-shaped hole results in smaller loss than with round film hole.Rehder [1O] studied the effects of coolant trailing-edge ejection on aerodynamic loss. It was found that the aerodynamic loss is small while the coolant is ejected from the slot at trailing edge center,and it is large when the coolant is ejected from the slot at pressure surface.Schobeiri and Pappu [11] investigated the correlations between the type of trailing edge slot and coolant to main stream momentum ratio,velocity ratio and trailing edge thickness.There are optimal momentum ratio,velocity ratio and trailing edge that lead to minimum aerodynamic loss.

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>BR</td><td>Blowing ratio, -</td><td>α</td><td>Injection angle, °</td></tr><tr><td>D</td><td>Diameter of cooling hole, mm</td><td>naw</td><td>Adiabatic cooling effectiveness, -</td></tr><tr><td>H</td><td>Pitch of cooling holes, mm</td><td>p</td><td>Density, kg/m³</td></tr><tr><td>I</td><td>Momentum ratio, -</td><td>Sp</td><td>Total pressure loss coefficient, -</td></tr><tr><td>K</td><td>Kinetic energy ratio, -</td><td>SP.hole</td><td>Total pressure loss coeficient generated inside the cooling hole, -</td></tr><tr><td>Laxial</td><td>Axial chord length of the vane, mm</td><td>SP.mix</td><td>Total pressure loss coefficient generated by mixing and inside boundary layer, -</td></tr><tr><td>Lc</td><td>Chord length of the vane, mm</td><td>SPtotal</td><td>Total pressure loss coefficient for film cool- ing, -</td></tr><tr><td>m</td><td>Mass flow rate, kg/s</td><td>Subscripts</td><td></td></tr><tr><td>Mex</td><td>Mach number at cascade exit, -</td><td>C</td><td>Coolant</td></tr><tr><td>P</td><td>Static pressure, Pa</td><td>m</td><td>Mainstream</td></tr><tr><td>P</td><td>Total pressure, Pa</td><td>cin</td><td>Cooling hole inlet</td></tr><tr><td>S</td><td>Curve length to the cooling hole center, mm</td><td>cout</td><td>Cooling hole outlet</td></tr><tr><td>T</td><td>Total temperature, K</td><td>W</td><td>Wall</td></tr><tr><td>V</td><td>Velocity, m/s</td><td>f</td><td>Computational domain outlet</td></tr></table></body></html>

Most of previous studies focused on either film coolingeffectiveness or aerodynamic loss.In this paper, numerical simulations were carried out to study both the film cooling effectiveness and the aerodynamic loss due to coolant and main stream mixing for a turbine guide vane.The effects of blowing ratio,main stream Mach number, surface curvature on the cooling effectiveness and mixing loss are presented and discussed.After this introduction,numerical method used for the simulation, validation of the method and main results are presented.

# Numerical Method and Validation

Ansys CFX was employed to simulate the main-flow and coolant flow in a turbine guide vane with film cooling.The solver is based on finite volume method,and is second order accurate.Fully implicit method is used for the discretization of Reynolds averaged Navier-Stokes equations.

SST turbulence model with scaled wall function was employed for thepresent simulations, whichcan smoothly change from the solution of RANS equation to wall function near the wall. SST model provided highly accurate prediction of flow separation under adverse pressure gradients,which are common in the boundary layer on the suction surface near the trailing edge.As film cooling was introduced, several studies [12-14] showed that the SST turbulence model is suitable for the film cooling calculations.

Convergence to a steady state is reached when the overall residuals of the primary variables are less than $1 \times$ ${ { 1 0 } ^ { - 6 } }$ and the variables at monitored points are kept unchange for enough iteration steps.

A validation simulation was performed for the case reported in[15],and then compared with the experiment result of Ito et al.[16],as shown in Figure 1.For the pressure surface film cooling,calculated loss profiles agree well with the experiment results.For the suction surface film cooling,calculated loss profiles at $\mathrm { B R } { = } 1 . 0$ agree well with the experiments at $\mathrm { B R } { = } 0 . 9 2$ ，except small discrepancies at $\scriptstyle \mathbf { y } / { \mathsf { p } } = 0$ and $\scriptstyle \mathbf { y } / { \mathsf { p } } = \mathbf { 0 } . 2$ . While at $\mathrm { B R = }$ 2.0,the calculated loss profiles were slightly higher than the experiments in the middle of the trailing edge wake. Both calculated loss profiles show the same variation trends as the experimental ones.The comparisons of numerical results and experiment results show that the numerical method applied is feasible and reliable.

# Calculation Setup and Boundary Conditions Geometry and grid

The turbine guide vane with a row of film cooling holes on both suction and pressure surface is shown in Figure 2.The overall chord $( L _ { c } )$ of the vane is $1 8 0 ~ \mathrm { m m }$ and the axial chord $( L _ { a x i a l } )$ is $9 4 . 1 \ \mathrm { m m }$ . The cylindrical cooling hole is located at 56 percent (suction surface) and 22 percent (pressure surface) of the axial chord downstream of the airfoil leading edge, respectively. Diameter of the cooling holes is $D { = } 2 ~ \mathrm { m m }$ ，with an injection angle of $\scriptstyle { \mathfrak { a } } = 2 3 ^ { \circ }$ . The pitch of the cooling holes $( H )$ is $5 D$ and the vane-to-vane pitch of the cascade is $1 5 0 \mathrm { m m }$

The computational domain includes the cascade flow passage, the cooling hole and the coolant plenum. The height of one hole pitch $( H { = } 5 D )$ ）at middle span of the cascade was chosen to decrease the grid scale and avoid the influence of secondary flow at the endwall. Periodic conditions were applied between the hub and shroud surface to model an infinite long vane. Coolant plenum region was extend to $1 0 D$ in both direction to simulate the full size coolant plenum.

![](images/3a7f121a593d20514eef6b1c6bc035aad4664e90646c18c492832ac08d84fc2f.jpg)  
Fig.1 Comparisons of total pressure loss coefficient profiles between computed and measured results

![](images/0e1804800410e859f45f31bd1f172c03163000684240ab9a64e0e0d3b11f1f82.jpg)  
Fig.2Turbine cascade with film cooling holes and computational domain

![](images/2f1abc23c2b22981f20b819f4fc9f36ce3f7021f7e1fa33c1dbb60ddea14351e.jpg)  
Fig.3Details of the grid near film hole:(a) Symmetry plane of the cooling hole;(b) Surface mesh of plenum and vane

Three different structured grids were generated respectively for vane cascade without film holes (NO HOLE),vane cascade with cooling holes on the suction surface(SSH) and vane cascade with cooling holes on the pressure surface (PSH) by using ICEM CFD.Double O-block grid was implemented in cooling holes to improve the local grid quality,as shown in Figure 3.The first layer height near the wall was $0 . 0 1 \mathrm { \ m m }$ and the growth ratio was 1.2. Thus, ${ \mathrm { Y } } ^ { + }$ was less than 3 for all grids near solid walls.

As shown in Figure 4, the cascade flow domain was divided into 31 blocks so that the local grid quality can be controlled separately.Different scale of the grid can be generated by change node numbers in the blocks.The grids of leading edge block 114 and the trailing edge blocks 74 and 142 were refined to improve the prediction accuracy in these areas.The blocks downstream of the cooling hole was refined as well, to make sure that the mixing between coolant and main flow can be captured accurately.

Grids for both SSH and PSH contain approximately $5 . 7 \mathrm { ~ M ~ }$ nodes.A SSH grid of $6 . 3 \mathrm { M }$ nodes was generated byrefining the special blocks to check grid independence. No visible change was obtained for both cooling effectiveness and downstream profile loss,as shown in Figure 5.So it can be judged that the present simulation was grid independent.

![](images/83e48298788e289d05a18b5df68c3da1e37154d3c2a080d1f438113a7a6d0842.jpg)  
Fig.4Mesh block details for cascade flow domain

# Boundary Conditions

As mentioned above,periodic conditions were applied to the hub-shroud interfaces to model an infinite linear cascade,and the vane-to-vane interface was also set as periodic boundary. On the wall surfaces of plenum, cooling hole and vane,adiabatic no slip wall conditions were applied.At the outlet of the computational domain,static pressure was specified as $\mathrm { P _ { f } } { = } 1 . 0 1$ atm.Main stream and coolant were both assumed as perfect gas.The total temperature of main stream and coolant were 5ooK and $3 3 3 \mathrm { K }$ ，respectively.Various inlet velocity or total pressure was applied to different cases to obtain different BR and/or $\mathbf { M } _ { \mathrm { e x . } }$ The inlet turbulence intensity was $5 \%$ for both the main stream and the coolant.

# Test Cases

There were 15 test cases calculated in the present work with various inlet conditions and blowing ratios, as shown in Table 1.Case O was a vane cascade without cooling hole (NO HOLE),and was a reference case.The inlet velocity of Case O was $2 0 \mathrm { m / s }$ ， the corresponding cascade exit Mach number was O.17. This inlet velocity was also applied to cases 1 to 8.Cooling hole for cases 1 to 4 was on the suction surface(SSH) and was on the pressure surface for cases 5 to 8(PSH). Cases 9 to 14 maintained the blowing ratio as an invariant and various exit Mach number were obtained from O.3 to O.7 by setting different inlet total pressure at main stream inlet.

![](images/099e7755e3783a7d21f3e6b56966b00181812acb04735fa636b2cbd1c6130061.jpg)  
Fig.5Grid independence verification

Table1 Test Cases   

<html><body><table><tr><td></td><td>Hole Position</td><td>BR</td><td>Mex</td><td>Notation</td></tr><tr><td>Case 0</td><td></td><td></td><td>0.17</td><td>NO HOLE</td></tr><tr><td>Case 1</td><td>SS</td><td>0.5</td><td>0.17</td><td>SSH</td></tr><tr><td>Case 2</td><td>SS</td><td>1.0</td><td>0.17</td><td>SSH</td></tr><tr><td>Case 3</td><td>SS</td><td>1.5</td><td>0.17</td><td>SSH</td></tr><tr><td>Case 4</td><td>SS</td><td>2.0</td><td>0.17</td><td>SSH</td></tr><tr><td>Case 5</td><td>PS</td><td>0.5</td><td>0.17</td><td>PSH</td></tr><tr><td>Case 6</td><td>PS</td><td>1.0</td><td>0.17</td><td>PSH</td></tr><tr><td>Case 7</td><td>PS</td><td>1.5</td><td>0.17</td><td>PSH</td></tr><tr><td>Case 8</td><td>PS</td><td>2.0</td><td>0.17</td><td>PSH</td></tr><tr><td>Case 9</td><td>SS</td><td>1.0</td><td>0.3</td><td>SSH</td></tr><tr><td>Case 10</td><td>SS</td><td>1.0</td><td>0.5</td><td>SSH</td></tr><tr><td>Case 11</td><td>SS</td><td>1.0</td><td>0.7</td><td>SSH</td></tr><tr><td>Case 12</td><td>PS</td><td>1.0</td><td>0.3</td><td>PSH</td></tr><tr><td>Case 13</td><td>PS</td><td>1.0</td><td>0.5</td><td>PSH</td></tr><tr><td>Case 14</td><td>PS</td><td>1.0</td><td>0.7</td><td>PSH</td></tr></table></body></html>

# Parameter Definitions

Define blow ratio, momentum ratio and kinetic energy ratio of the coolant to the main stream as follows,

$$
\begin{array} { c } { { B R = \displaystyle \frac { \rho _ { c } V _ { c } } { \rho _ { m } V _ { m } } } } \\ { { { } } } \\ { { I = \displaystyle \frac { \rho _ { c } V _ { c } ^ { 2 } } { \rho _ { m } V _ { m } ^ { 2 } } } } \\ { { { } } } \\ { { K = \displaystyle \frac { \rho _ { c } V _ { c } ^ { 3 } } { \rho _ { m } V _ { m } ^ { 3 } } } } \end{array}
$$

Where, $\rho _ { c }$ and $V _ { c }$ were the coolant density and velocity, $\rho _ { m }$ and $V _ { m }$ were the main stream density and velocity.

Define the adiabatic film cooling effectiveness as,

$$
\eta _ { \mathrm { a w } } = { \frac { T _ { m } - T _ { w } } { T _ { m } - T _ { c } } }
$$

Where $T _ { m }$ and $T _ { c }$ were the inlet temperature of main stream and coolant. $T _ { w }$ was the adiabatic temperature on the vane surface.

For the vane without film cooling hole, the total pressure loss coefficient $\xi _ { P , \nu a n e }$ was defined as,

$$
\xi _ { P , \nu a n e } = \frac { P _ { t , m } - P _ { t , f } } { P _ { t , m } - P _ { f } }
$$

Where $P _ { t , m }$ was the main stream inlet total pressure, and $P _ { t , f }$ and $P _ { f }$ were the outlet total pressure and static pressure,respectively.

For the cooled vane, total pressure loss coefficient should be transformed as:

$$
\xi _ { P , t o t a l } = \frac { \displaystyle \frac { \dot { m } _ { c } } { { \dot { m } } _ { c } + { \dot { m } } _ { m } } P _ { t , c i n } + \frac { { \dot { m } } _ { m } } { { \dot { m } } _ { c } + { \dot { m } } _ { m } } P _ { t , m } - P _ { t , f } } { P _ { t , m } - P _ { f } }
$$

Where $P _ { t , c i n }$ was the total pressure at the inlet of the cooling hole. $\dot { m } _ { c }$ and $\dot { m } _ { m }$ were respectively the mass flow rates of the coolant and the main stream. The total losses include the loss in cooling hole,the loss due to mixing process and the loss in cascade boundary layer. If replacing $P _ { t , c i n }$ with the total pressure $P _ { t , c o u t } ,$ at the cooling hole outlet, we can obtain the total pressure loss coefficient $\xi _ { P , m i x i n g } $ that contained the latter two parts of $\xi _ { P , t o t a l } ,$ i.e.,

$$
\xi _ { P , m i x } = \frac { \displaystyle \frac { \dot { m } _ { c } } { \dot { m } _ { c } + \dot { m } _ { m } } P _ { t , c o u t } + \frac { \dot { m } _ { m } } { \dot { m } _ { c } + \dot { m } _ { m } } P _ { t , m } - P _ { t , f } } { P _ { t , m } - P _ { f } }
$$

Obviously, the loss inside the cooling hole can be obtained as follows,

$$
\xi _ { P , h o l e } = \xi _ { P , t o t a l } - \xi _ { \mathrm { P , m i x } } = \frac { \frac { \dot { m } _ { c } } { { \dot { m } _ { c } } + \dot { m } _ { m } } ( P _ { t , c i n } - P _ { t , c o u t } ) } { P _ { t , m } - P _ { f } }
$$

# Results and Discussions

# Cooling Effectiveness at Different BR

To reduce the vane adiabatic temperature was the important purpose of film cooling. Cooling Effectiveness Was an indicator of temperature reduction by using film cooling.Figure 6 showed the lateral averaged adiabatic film cooling effectiveness on the suction surface and the pressure surface at different BR(Cases 1 to 8). S/D is the ratio of curve length from the center of the cooling hole outlet to the hole diameter. For film cooling on suction surface (SSH),cooling effectiveness at $\mathrm { B R } { = } 0 . 5$ is the highest at almost all district downstream of the cooling hole.While for film cooling on pressure surface (PSH), the cooling effectiveness at $\mathrm { B R } { = } 0 . 5$ is the highest near the cooling hole outlet and then dropped faster than that of SSH.The different cooling features between SSH and PSH may be caused by the surface curvature,normal pressure gradient and also stream-wise pressure gradient.

For both SSH and PSH, the same dropping trend of cooling effectiveness was found when BR was increased. This can be explained as that the high normal momentum of the coolant raised the coolant stream apart from the vane surface further. With the increase of BR, the cooling effectiveness for SSH dropped much faster than for PSH. For cases 6 to 8,the cooling effectiveness decreased till $\mathrm { S } / \mathrm { D } { = } 3 5$ ，and then rose up downstream,as a result of the coolant reattachment due to the concave curvature of the pressure surface.

![](images/53be6959b04a2ddbb2c3b8cbc39fd6c1308aa7c60d5ccda0d627ea330263c80c.jpg)  
Fig.6Lateral averaged adiabatic cooling effectiveness for SSH and PSH at different BR $( \mathrm { M } _ { \mathrm { e x } } { = } 0 . 1 7 )$

# CoolingEffectivenessatDifferent $\mathbf { M } _ { \mathbf { e x } }$

The lateral averaged adiabatic cooling effectiveness profiles for SSH and PSH at $\mathrm { B R } { = } 1 . 0$ and different $\mathbf { M } _ { \mathrm { e x } }$ were shown in Figure 7.For SSH, the cooling effectiveness downstream of the cooling hole increased as the exit Mach number varied from O.17 to O.5.Compared with $\mathbf { M } _ { \mathrm { e x } } = 0 . 5$ ，the cooling effectiveness at $\mathbf { M } _ { \mathrm { e x } } = 0 . 7$ was higher at $\mathrm { S / D } { < } 2 0$ ，and then almost identical at $\mathrm { S / D } { > } 2 0$ The cooling effectiveness for SSH is increased from the cooling hole exit to the trailing edge. The coolant jet at $\mathrm { B R } { = } 1 . 0$ was slightly raised up from vane suction surface, but vane surface could still be cooled by the coolant stream.The same profile trend was found for SSH at $\mathrm { B R } { = } 1 . 0$ in Figure 6.

Reattachment of coolant stream to the pressure surface was found for PSH at different $\mathbf { M } _ { \mathrm { e x } }$ .The effectsof coolant reattachment on the film cooling effectiveness are obviouslyincreased as $\mathbf { M } _ { \mathrm { e x } }$ is increased.At $\mathbf { M } _ { \mathrm { e x } } = 0 . 5$ and $\mathbf { M } _ { \mathrm { e x } } = 0 . 7$ ，the cooling effectiveness rose sharply to 0.15 and O.23 near the trailing edge, because the high speed coolant stream struck onto the pressure surface near the vane trailing edge and then spread in the span-wise of the vane surface.To illuminate the reattachment of coolant, Figure 8 showed the total temperature contours plotted on five planes perpendicular to PS at different $\mathbf { x } / L _ { a x i a l }$ for the case of $\mathbf { M } _ { \mathrm { e x } } = 0 . 7$ . It can be seen that main stream pushed the coolant onto the pressure surface. The core of coolant was forced to spread in the span-wise direction.

# AerodynamicLossatDifferentBR

Total pressure loss coefficient for SSH at different BR was shown in Figure 9. All $\xi _ { P , h o l e } , \ \xi _ { P , m i x }$ and $\boldsymbol { \xi } _ { P , t o t a l }$ were increased while BR was changed from O.5 to 2.0.The increment of $\xi _ { P , h o l e }$ was approximately the same as the increment of $\xi _ { P , m i x }$ . As a result, the percentage of $\xi _ { P , h o l e }$ in $\xi _ { P , t o t a l s }$ was increased.At higher BR, the loss generated in the cooling hole became more important and was not negligible.

![](images/909ff2198fb3ba13b8ad9c85449dd3944117029934ddd7880a15ee5c540b6574.jpg)  
Fig.7Lateral averaged adiabatic cooling effectiveness for SSH and PSH at different $\mathbf { M } _ { \mathrm { e x } }$ 0 $\mathrm { B R } { = } 1 . 0$ ）

The flow distributions inside the cooling hole at $\mathrm { B R = }$ 0.5 and $\mathrm { B R } { = } 2 . 0$ were show in Figure 10. Separation region in the cooling hole located near the hole inlet. Another separation region out of the cooling hole was found near the hole outlet. The coolant stream in the cooling hole separated much more severely at the high BR than at the low BR.

The boundary layer downstream of the cooling hole was thinned in the middle plane between the two holes as BR increased,as shown in Figure 11 (a).In the meridional plane of the computational domain,different trend was found as shown in Figure 11 (b).At $\mathrm { B R } { = } 0 . 5$ and $\mathrm { B R } { = } 1 . 0$ ,the boundary layer was thickened by the coolant jets downstream the cooling hole.At $\mathrm { B R } { = } 1 . 5$ the coolant rose apart from the suction surface and the boundary layer was thinned. At $\mathrm { B R } { = } 2 . 0$ , theboundary layer thickness increased because of the severe separation near the cooling hole outlet.

Figure 12 showed the total pressure loss coefficient profiles at the domain exit at different BR. $\mathrm { { y / p { > } 0 } }$ was for the suction surface and $\scriptstyle \mathbf { y } / \mathbf { p } < 0$ was for the pressure surface.It was obvious that loss coefficient profile for SSH wasthe highest at $\mathrm { B R } { = } 2 . 0$ and was the lowest at $\mathrm { B R } { = } 0 . 5$ which was coincident with Figure 9.As BR was increased,the baseline of the loss rose up and the difference between the peak and the baseline was decreased. As a result, the loss profiles became flatter at high BR.

![](images/eeae2e99c790b6eeffa7657614bd9ab47b3f9bec91efd272e5ad8ed065a8285a.jpg)  
Fig.8Total temperature contours on five different planes perpendicular to pressure surface ( $\mathrm { B R } { = } 1 . 0$ $\mathrm { M } _ { \mathrm { e x } } { = } 0 . 7$ ）

![](images/41cc19f890eb338c6c584aa8766f8a78db699946a635d97cb3b2d85a1c3b94f4.jpg)  
Fig.9Total pressure loss coefficient for SSH at different BR （20 $( \mathrm { M } _ { \mathrm { e x } } { = } 0 . 1 7 )$

![](images/b886ae0527ec1c47381d9d3ccc75d68d5bc3dc43488deb31d270f7eb56941224.jpg)  
Fig.10Flow distribution inside the cooling hole for SSH （204号 $( \mathrm { M } _ { \mathrm { e x } } { = } 0 . 1 7 )$

The locations of loss peaks for the cooled vane deflected to the suction surface compared with the uncooled vane,because the SSH coolant stream contained a normal velocity component towards the mainstream, which gave the wake a slight offset to the normal direction of the vane surface.Then the offset expanded to the exit and a visual deflection was found on the loss profiles.

The same analysis was implemented for PSH.Table 2 showed the total pressure loss coefficient for PSH at different BR at $\mathrm { M } _ { \mathrm { e x } } { = } 0 . 1 7$ $\xi _ { P , h o l e }$ was increased two orders of magnitude, and was still negligible compared with $\xi _ { P , m i x } ,$ （20 which was the main portion in $\xi _ { P , t o t a l } .$ .The reason for the less difference between PSH loss and NO HOLE loss Was discovered by further investigation. Coolant stream ofPSH stuck in the boundary layer of pressure surface andless impact was caused on the mainstream.Asa result, $\boldsymbol { \xi } _ { P , t o t a l }$ increased slightly with the increase of BR, because $\xi _ { P , m i x }$ maintained almost unchanged. Separation in the cooling hole and thickness increment in the boundary layer were observed at the same location and the intensity of the separation had the same variation among different BR.

![](images/035aae8db37a9bdcfdba65af62c3de6653cc2970fb6fa8d78ac49edf1556b79d.jpg)

![](images/b7094fe1619c9f58e310e87876f2246fa256de276513af8d37845fcc514c832c.jpg)  
Fig.11Boundary layer flow for SSH $( \mathrm { M } _ { \mathrm { e x } } { = } 0 . 1 7$ ）  
Fig.12Total pressure loss coefficient profiles for SSH at different BR $( \mathrm { M } _ { \mathrm { e x } } { = } 0 . 1 7 )$ （20

Table 2Total pressure loss coefficient for PSH   

<html><body><table><tr><td></td><td>SP.hole</td><td>SP.mix</td><td>SPtotal</td></tr><tr><td>NO HOLE</td><td></td><td></td><td>4.57E-02</td></tr><tr><td>BR=0.5</td><td>5.00E-06</td><td>4.57E-02</td><td>4.57E-02</td></tr><tr><td>BR=1.0</td><td>3.08E-05</td><td>4.57E-02</td><td>4.57E-02</td></tr><tr><td>BR=1.5</td><td>9.13E-05</td><td>4.57E-02</td><td>4.58E-02</td></tr><tr><td>BR=2.0</td><td>2.00E-04</td><td>4.59E-02</td><td>4.60E-02</td></tr></table></body></html>

Figure 13 showed the relations between the loss coefficient and the momentum ratio I or the kinetic energy ratio K. For $\xi _ { P , h o l e } .$ $\xi _ { P , m i x } ,$ and $\xi _ { P , t o t a l }$ , the relation was nonlinear with the momentum ratioIand was linear with the kinetic energy ratio K. So the aerodynamic loss caused by film cooling was in proportion to the third power of the velocityratio of coolant to main stream. The same trend was found for PSH, as shown in Figure 13 (b) and (c).

![](images/15cea21a8d32770ef18ba470907f75938a19da5c6d98980de84aa10b3cf6b684.jpg)  
Fig.13Relations between the loss coefficient and momentum ratio or kinetic energy ratio $( \mathrm { M } _ { \mathrm { e x } } { = } 0 . 1 7 _ { \cdot }$ 门

An equation can be fitted as,

$$
\xi _ { p } = A \cdot K + B = A \frac { \rho _ { c } V _ { c } ^ { 3 } } { \rho _ { m } V _ { m } ^ { 3 } } + B
$$

InwhichAwas the curvaturefactorandB was the intercept at $\scriptstyle \mathrm { B R = 0 }$ .ThevaluesofAandB for SSHandPSH were listed in Table 3 and Table 4.This equation can be used to predict the total pressure loss coefficient when the densityratio and velocityratio were known.

# Aerodynamic Loss atDifferent $\mathbf { M } _ { \mathbf { e x } }$

Total pressure loss coefficients at different $\mathbf { M } _ { \mathrm { e x } }$ （ $\mathrm { B R } =$ 1.0) were shown in Figure 14. $\xi _ { P , m i x }$ and $\boldsymbol { \xi } _ { P , t o t a l }$ for both SSH and PSH shared the same trend, i.e.,it is slightly decreased with the increase of $\mathbf { M } _ { \mathrm { e x } }$ at $ { \mathbf { M } } _ { \mathrm { e x } } { < } 0 . 4$ ，and then increased at $ { \mathrm { M } _ { \mathrm { e x } } } { > } 0 . 4$ .There was a proper $\mathbf { M } _ { \mathrm { e x } }$ to gain the minimum aerodynamic loss.Inner hole loss coefficient $\xi _ { P , h o l e }$ for SSH dropped as $\mathbf { M } _ { \mathrm { e x } }$ increased.The values of $\xi _ { P , h o l e }$ for PSH and SSH shown in Figure 14 were listed in Table 5.

Total pressure loss coefficient profiles at different $\mathbf { M } _ { \mathrm { e x } }$ Was shown in Figure 15.Deflections of the loss peaks towards $\scriptstyle \mathbf { y } / \mathbf { p } < 0$ were found for both SSH and PSH at high $\mathbf { M } _ { \mathrm { e x } }$ .As $\mathbf { M } _ { \mathrm { e x } }$ increased,main stream speed dominated the deflection because of the vane curvature.Different from the changes caused by BR, the peak value in the profiles increased and the baseline value decreased as $\mathbf { M } _ { \mathrm { e x } }$ increased,which meant that the losses concentrated in the region influenced by trailing edge.The increment of main stream speed leads to the increase of friction loss along the vane surface and mixing loss between coolant stream and main stream.

Table 3Values of factorA in equation 9   

<html><body><table><tr><td></td><td>SPhole</td><td>SPmix</td><td>SPtotal</td></tr><tr><td>SSH</td><td>7.78E-03</td><td>8.61E-03</td><td>1.64E-02</td></tr><tr><td>PSH</td><td>3.44E-05</td><td>3.64E-05</td><td>6.65E-05</td></tr></table></body></html>

Table 4Values of factorB in equation 9   

<html><body><table><tr><td></td><td>SPhole</td><td>SPmix</td><td>SPtotal</td></tr><tr><td>SSH</td><td>4.01E-04</td><td>4.35E-02</td><td>4.39E-02</td></tr><tr><td>PSH</td><td>5.15E-06</td><td>4.56E-02</td><td>4.57E-02</td></tr></table></body></html>

![](images/21486806a33bb0dee121208b5e20a8847934ac5ba1073e26f845c725cf59e5db.jpg)  
Fig.14Total pressure loss coefficient for SSH and PSH at different $\mathrm { M } _ { \mathrm { e x } } \left( \mathrm { B R } { = } 1 . 0 \right)$ （20

Table 5Inner hole loss coefficient at different $\mathbf { M } _ { \mathrm { e x } }$   

<html><body><table><tr><td></td><td>Mex=0.17</td><td>Mex=0.30</td><td>Mex=0.50</td><td>Mex=0.70</td></tr><tr><td>SSH</td><td>6.14E-03</td><td>5.13E-03</td><td>4.51E-03</td><td>3.98E-03</td></tr><tr><td>PSH</td><td>3.08E-05</td><td>2.44E-05</td><td>2.10E-05</td><td>1.77E-05</td></tr></table></body></html>

![](images/d05416a0ade1f7d473125a247302868b141bc8fd8bd46c8725bfa93a04b76dec.jpg)  
Fig.15Total pressure loss coefficient profiles at different $\mathbf { M } _ { \mathrm { e x } }$ $\mathrm { ( B R = 1 } . 0 )$ 1

# Conclusions

A validated numerical method was used to study cylindrical hole film cooling effectiveness and aerodynamic loss features of a turbine guide vane at different BR and different $\mathbf { M } _ { \mathrm { e x } }$ . The trends of cooling effectiveness variation were explained and the loss variation mechanisms were elucidated.Specific conclusions are drawn as follows:

(1)For both SSH and PSH, the highest cooling effectiveness is gained when cooling holes are located at suction surface at $\mathrm { B R } { = } 0 . 5$ 1 $( \mathrm { M } _ { \mathrm { e x } } { = } 0 . 1 7 )$ .Mach number of main stream has an impact on the film cooling effective ness.In general,averaged cooling effectiveness is increased with the increase of $\mathbf { M } _ { \mathrm { e x } }$ . Rapid increase of cooling effectiveness for PSH at high $\mathbf { M } _ { \mathrm { e x } }$ was noticed.

(2） Total pressure loss coefficients $\xi _ { P , h o l e } , \ \xi _ { P , m i x } ,$ and $\boldsymbol { \xi } _ { P , t o t a l }$ were in linear relation with the kinetic energy ratio. A linear equation was fitted for both SSH and PSH.Total pressure loss coefficients are also slightly impacted by $\mathbf { M } _ { \mathrm { e x } } .$ ，as well as BR(I or K).Loss coefficient profile at domain outlet became flatteras BR is increased.

# Acknowledgements

The authors wish to acknowledge the financial support fromthe NationalNatural Science Foundation of China through Grant No.51336007.

# References

[1]Goldstein,R.J.,Eckert,E.R. G.,and Burggraf,F.,(1974), Effects of Hole Geometry and Density on Three-Dimensional Film Cooling,International Journal of Heat and Mass Transfer,Vol.17,pp.595-607.   
[2]Bunker,R.S.,(20o5),AReview of Shaped Hole Turbine Film-Cooling Technology,ASME Journal ofHeat Transfer, Vol.127, No.2, pp.441-457.   
[3]Kusterer,K., Tekin,N.,Kasiri,A.,Bohn, D., Sugimoto, T.,Tanaka,R.,andKazari,M.,(2013),Highest Efficient Film Cooling by Improved Nekomimi Film Cooling - Part2:Hot Gas Flow Conditions,ASME paper GT2013- 95042,Proceedings of ASME Turbo Expo 2013,June $3 -$ 7, San Antonio,Texas,USA.   
[4]Bunker, R.S.,(2010),Film Cooling: Breaking the Limits of the Diffusion Shaped Hole,Heat Transfer Research, Vol.41,No.6, pp.627-650.   
[5]Haller, B.R. and Camus, J.J.,(1984) Aerodynamic Loss Penalty Produced by Film Cooling Transonic Turbine Vanes,ASME Journal of Engineering for Gas Turbines and Power, Vol.106,No.1,pp.198-205.   
[6]Day, C.R.B., Oldfield,M.L.G.,and Lock,G.D., (2000) Aerodynamic Performance of an Annular Cascade of Film Cooled Nozzle Guide Vanes under Engine Representative Conditions,Experiments in Fluids,Vol.29,No. 2,pp.117-129.   
[7] Gomes,R.A., (2012)，Aerothermodynamics of a HighPressure Turbine Vane with Very High Loading and Vortex Generators,ASME Journal of Turbomachinery, Vol.134,011020.   
[8] Friedrichs,S.,and Hodson,H.P.,(1997),Aerodynamic Aspects of Endwall Film-Cooling，ASME Journal of Turbomachinery,Vol.119,No.4,pp.786-793.   
[9]Colban，W.,and Thole,K.,(20o7),Influence of Hole Shape on the Performance of a Turbine Vane Endwall Film-cooling Scheme,International Journal of Heat and Fluid Flow, Vol.28,No.3,pp.41-356.   
[10] Rehder,H.J.，(2012)，Investigation of Trailing Edge Cooling Concepts in a High Pressure Turbine CascadeAerodynamic Experiments and Loss Analysis,ASME Journal of Turbomachinery,Vol.134,No.5,051029.   
[11] Schobeiri,M.T.,and Pappu,K.,(1999),Optimization of Trailing Edge Ejection Mixing Losses: A Theoretical and Experimental Study,ASME Journal of Fluid Engineering, Vol.121, No.1, pp.118-125.   
[12]Rezasoltani, M.,Lu,K., Schobeiri,M. T.,and Han,J.C. (2015),A Combined Experimental and Numerical Study of the Turbine Blade Tip Film Cooling Effectiveness Under Rotation Condition,ASME Journal of Turbomachinery,Vol.137,No.5,051009.   
[13]Abdelfattah,S.A.,and Schobeiri,M.T.(2010),Experimental and Numerical Investigations of Aerodynamic Behavior of a Three-Stage HP-Turbine at Different Operating Conditions,ASME paper GT2010-23564,Proceedings of ASME Turbo Expo 2010，June 14-18,2010, Glasgow, Scotland.   
[14]Liao,G.,Wang,X.,Li,J.,and Zhang,F.(2014),Effects of Curvature on the Film Cooling Effectiveness of Double-Jet Film Cooling,ASME paper GT2014-26263, ProceedingsofASME Turbo Expo 2014,June16-20,Du sseldorf, Germany.   
[15] Walters,D.K.,and Leylek,J.H.(2000),Impact of filmcooling jets on turbine aerodynamic losses,ASME Journal of Turbomachinery, 122(3), 537-545.   
[16]Ito,S.，Eckert,E.R.G.，and Goldstein，R.J.(1980), Aerodynamic Loss in a Gas Turbine Stage with Film Cooling,ASME Journal of Engineering for Gas Turbines and Power, vol.102,No.4, pp.964-970.