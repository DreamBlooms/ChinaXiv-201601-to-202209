# Numerical Study of Unsteady Flows with Cavitation in a High-Speed Micro Centrifugal Pump

LI Yeqiang1, YUAN Shiwei², LAI Huanxin1\*

1.School of Mechanicaland Power Enginering,East China Universityof Scienceand Technology,Shanghai 200237, China.   
2. Shanghai First Fluid Machinery Co. Ltd, Shanghai 201709, China.

$\copyright$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

The unsteady flows caused by the interaction between the impeller and the volute in a high-speed micro centrifugal pump are numerically studied. The internal flows of both with and without cavitations are analyzed using the CFX.The characteristics of unsteady pressure on the blade surfaces and the symmetric plane of the volute are presented and compared.The results show that the amplitudes of pressure fluctuations of critical cavitation on the blade pressure surface (PS)are bigger as compared with those at the non-cavitation condition,but on the suction surface (SS),the situation ison the contrary.When cavitation occurs,reduction ofload in the impeller is a result. In the present study,such reduction of load is observed mainly on the first halfof the blades.Pressure fluctuations at five monitoring points,denoted byWK1 to WK5 in the volute,are also analyzed.No matterat the critical cavitation or at the non-cavitation conditions,the monitored pressure fluctuations are at the same frequencies,which equal to the blade passing frequency (BPF)and its multiples.However,the amplitudes of the fluctuations at critical cavitation condition are considerably stronger, as compared with those for without cavitation.

# Keywords: Micro-centrifugal pump, Unsteady flow, Cavitation, Pressure fluctuation.

# Introduction

Cavitation is a complex phenomenon of liquid vaporizing and forms bubbles in local low pressure regions. It is a common occurrence in hydraulic fluid machinery [1]. When cavitation occurs, the overall performance such as the efficiency of the pump may decline. Cavitations may also lead to some disadvantages such as vibration,noises and failure of impeller. In order to solve the extremely difficult problem relevant to the cavitation, the cavitating flow characteristics in a pump should be carefully studied.

When a micro-centrifugal pump operates at high speed, cavitation is very easy to occur in the flow passages of impeller. However, this kind of the internal flows in high speed micro-centrifugal pumps,especially the unsteady cavitation phenomena,are still very insufficiently studied as compared with those of traditional large scale centrifugal pumps.

There are many studies in which the cavitating flow fields in large scale centrifugal pumps are investigated [3-5].For instances,Medvitz et al.[3] adopted a cavitation model that was proposed by Kunz et al.[2], to predict the internal cavitation flows in a centrifugal pump. The curve of head-drop was calculated at several flow rates.

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>b2</td><td>blade width at exit[mm]</td><td>T</td><td>period of the impeller rotation[s]</td></tr><tr><td>BPF</td><td>blade passing frequency[Hz]</td><td>u2</td><td>velocity at the impeller outlet[m/s]</td></tr><tr><td>Cp</td><td>static pressure coefficient</td><td>Z</td><td>number of blades</td></tr><tr><td>D2</td><td>diameter of the impeller outlet[mm]</td><td>Zs</td><td>dimensionless distance from the hub to the shroud</td></tr><tr><td>Fcond</td><td>cavitation condensation coefficient</td><td>Y</td><td>volume fraction of vapor</td></tr><tr><td>Fvap</td><td>cavitation vaporization coefficient</td><td>Y</td><td>volume fraction of liquid</td></tr><tr><td>H</td><td>head</td><td>Pv</td><td>density of vapor</td></tr><tr><td>n</td><td>impeller rotating speed[r/min]</td><td>P</td><td>density of liquid[kg/m³]</td></tr><tr><td>Pin</td><td>static pressure of impeller inlet[Pa]</td><td>n</td><td>efficiency[%]</td></tr><tr><td>Prms</td><td>the static pressure root-mean-square</td><td>9</td><td>cavitation number</td></tr><tr><td>Q</td><td>flow rate[m³/h]</td><td>4</td><td>head coefficient</td></tr><tr><td>Qd</td><td>design flow rate[m³/h]</td><td></td><td>surface tension coefficient[N/m]</td></tr><tr><td>S</td><td>non-dimensional arc length at the midspan of the blade, from the leading to the trailing edges</td><td>3%</td><td>cavitation number at which the pump head is degraded by 3% because of cavitation</td></tr></table></body></html>

Fu et al.[4-5] applied a cavitation model, which had been implemented in commercial software, to numerically study cavitation flow phenomena in a centrifugal pump under low flow rates.They observed that cavitation occurred over a wide range of low flow rates,which showed a typical head-drop curve.Axially asymmetric cavities distributed in the impeller passages were also observed.

It is known that the rotational speed and the size of micro-centrifugal pumps are much different from those of conventional pumps. So the cavitation curves calculated by the similarity law for ordinary large scale pumps are not suitable for a micro pump [1]. Compared with large scale low-speed pumps,a high speed micro-centrifugal pump has a higher specific speed,which affects the cavitation significantly.In the present study,the internal unsteady cavitating flow characteristics of a high speed micro centrifugal pump are numerically studied by using a commercial package, the CFX.For the closure of the governing equations, the RNG k-ε model for turbulence and the Rayleigh-Plesset model for cavitation are employed. This study aims to analyze the influence of cavitation on unsteady pressure fluctuations in the high speed micro centrifugal pump. The flow details on blade surfaces and in the symmetric plane of the volute will be paid attention.

# Model studied and numerical scheme

# Basic geometric parameters of the pump

The computational model of the pump includes a shrouded impeller which has three blades,a volute,and the inlet and outlet pipes.The main relevant geometric and design parameters of the high speed micro centrifugal pump are summarized in Table1.

# Mesh and check of grid-independency

Unstructured tetrahedral cells were used for modelling the twisted blades and the complex internal flow passages of the micro-centrifugal pump,because of their good extensive adaptability to complicated geometries and the easiness for grid generation.

Table1 Design parameters of the centrifugal pump   

<html><body><table><tr><td>Flow rate: Qd (m³/h)</td><td>13.2</td></tr><tr><td>Head: H (m)</td><td>30</td></tr><tr><td>Rotational speed:n(r/min）</td><td>10000</td></tr><tr><td>Specific speed: ns</td><td>169</td></tr><tr><td>Impeller diameter:D2(mm)</td><td>56</td></tr><tr><td>Blade outlet width: b2 (mm)</td><td>4</td></tr><tr><td>Blade outlet angle: β（deg)</td><td>39</td></tr><tr><td>Blade Number: Z</td><td>3</td></tr></table></body></html>

![](images/faec8c31963c36cf9e6abc744b170f4be2f73c34c3c56ce7ca20a9014a04e0cf.jpg)  
Fig.1Grids of the impeller and tongue

The grids near the blade surfaces and in nearby of the volute tongue are refined to improve the resolution of the results.Figurel shows the refined grids of the impeller and the tongue.

Fourmesheslisted in Table2havebeenusedtocheck the grid-independence of the calculation.The check is based on calculating the steady flow with the cavitation number equal to O.115.General performance such as the head and the efficiency of the pump calculated by the four meshes are included in Table 2,which shows very slight differences between the results of meshes II and IV. Figure 2 is the comparison of the vapour fraction calculated by the four meshes,where $S$ is the non-dimensional arc length of the midspan, from the leading to the trailing edges of the blade; $Z _ { s }$ is defined as the dimensionless distance from the hub to the shroud,and its value is in the range from O to 1.Moreover,as clearly seen in Figure 2,the calculated vapour volume fraction is remained constant when the grids are refined from mesh III to meshIV. Therefore, the mesh III which has 1682417 elements is employed for the present simulations.

Table 2Meshes for grid-independence check   

<html><body><table><tr><td rowspan="2">zones</td><td colspan="4">Meshes</td></tr><tr><td>I</td><td>ⅡI</td><td>III</td><td>VI</td></tr><tr><td>Inlet</td><td>196918</td><td>196918</td><td>196918</td><td>196918</td></tr><tr><td>Impeller</td><td>196400</td><td>369994</td><td>474467</td><td>603025</td></tr><tr><td>Volute</td><td>778216</td><td>778216</td><td>778216</td><td>778216</td></tr><tr><td>Outlet</td><td>232816</td><td>232816</td><td>232816</td><td>232816</td></tr><tr><td>Total</td><td>1404350</td><td>1577944</td><td>1682417</td><td>1810975</td></tr><tr><td>H/m</td><td>30.73</td><td>30.64</td><td>30.36</td><td>30.39</td></tr><tr><td>n/%</td><td>76.15</td><td>76.82</td><td>77.32</td><td>77.27</td></tr></table></body></html>

![](images/080d4e99f90a3fba1c50b778c52a36a3ecac7f1ab256b7bdfe8c24c67d27b4eb.jpg)  
Fig.2Calculated vapor fraction along the line $Z _ { s } { = } 0 . 5$ in SS of the blade

# Cavitation model

The cavitation flows of the fluid are assumed to be a homogeneous two-phase mixture in the cavitation model. The liquid-vapor mass transfer due to cavitation is solved by the transport equation-based cavitation model.

$$
\frac { \partial ( \gamma _ { \nu } \rho _ { \nu } ) } { \partial t } + \nabla ( \gamma _ { \nu } \rho _ { \nu } { \bf u } ) = \dot { m } _ { \nu } - \dot { m } _ { l }
$$

Where $\gamma _ { \nu }$ is the volume fraction of vapour, $\rho _ { \nu }$ is the vapourdensity, $\dot { m } _ { \nu }$ and $\dot { m } _ { l }$ are the mass transfer rates per unit volume for vaporization and condensation,respectively. The values of the $\dot { m } _ { \nu }$ and $\dot { m } _ { \iota }$ are deduced from the Rayleigh-Plesset equation,

$$
R _ { B } { \frac { d ^ { 2 } R _ { B } } { { d t } ^ { 2 } } } + { \frac { 3 } { 2 } } ( { \frac { d R _ { B } } { d t } } ) ^ { 2 } + { \frac { 2 \Theta } { \rho _ { l } R _ { B } } } = { \frac { P _ { s a t } - P } { \rho _ { l } } }
$$

where $R _ { B }$ is the bubble radius, $P$ is pressure while $P _ { s a t }$ is the saturation pressure for the vapour, $\rho _ { l }$ is the liquid density and $\Theta$ is the surface tension coefficient. By ignoring the effect of the second order derivative and the surface tension, the Rayleigh equation is simplified as:

$$
\frac { d R _ { B } } { d t } = ( \frac { 2 } { 3 } \frac { P _ { s a t } - P } { \rho _ { l } } ) ^ { 1 / 2 }
$$

Denote the number of bubbles per unit volume by $N _ { B } .$ then the rate of bubble mass transfer per unit volume is:

$$
\frac { d m } { d t } = N _ { B } \rho _ { \nu } \frac { d V _ { B } } { d t } = N _ { B } \rho _ { \nu } 4 \pi R _ { B } ^ { 2 } ( \frac { 2 } { 3 } \frac { P _ { s a t } - P } { \rho _ { l } } ) ^ { 1 / 2 }
$$

The values of $N _ { B }$ for vaporization and condensation, respectively, are calculated as follows [6,7],

$$
N _ { B } = \frac { 3 \alpha _ { n u c } } { 4 \pi R _ { B } ^ { 2 } } ( 1 - \alpha _ { \nu } )
$$

$$
N _ { B } = \frac { 3 \alpha _ { \nu } } { 4 \pi R _ { B } ^ { 2 } }
$$

The mass transfer rates per unit volume for vaporization and condensation,respectively,are therefore calcu lated by

$$
\dot { m } _ { \nu } = F _ { \nu a p } \frac { 3 \gamma _ { n u c } ( 1 - \gamma _ { \nu } ) \rho _ { \nu } } { R _ { B } } ( \frac { 2 } { 3 } \frac { P _ { s a t } - P } { \rho _ { l } } ) ^ { 1 / 2 } \qquad P < P _ { s a t }
$$

$$
\dot { m } _ { l } = F _ { c o n d } \frac { 3 \gamma _ { \nu } \rho _ { \nu } } { R _ { B } } ( \frac { 2 } { 3 } \frac { P - P _ { s a t } } { \rho _ { l } } ) ^ { 1 / 2 } \qquad P > P _ { s a t }
$$

In the Rayleigh-Plesset cavitation model, $\gamma _ { n u c } = 5 ~ \times$ $1 0 ^ { - 4 }$ $F _ { \nu a p }$ and $F _ { c o n d }$ are empirical constants, $F _ { \nu a p } = 5 0$ ,and $F _ { c o n d } = 0 . 0 1$ ，as recommended by Zwart et al.[6] and Bakir et al. [7].

# Computational scheme

The unsteady cavitation flow simulations are performed by using the commercial software CFX.The RNG k-ε model for turbulence and the Rayleigh-Plesset model for cavitation are selected for calculation. The RNG k-ε turbulence model is widely used to account for turbulence in cavitating flows [8-11]. The vapour and liquid volume fractions are zero and one,respectively,at the inflow boundary the total pressure is also specified. Target mass flow is applied at the outlet of the computational domain.In addition,no-slip and adiabatic conditions have been imposed on the solid walls.The transient rotor/ stator mode is applied at the interfaces between the impeller and volute.18O time steps are set in the period of a rotation T; this results in a time step for unsteady calculation, $\mathrm { t s } { = } \mathrm { T } / 1 8 0 { = } 3 . 3 3 3 { \times } 1 0 ^ { - 5 }$ (s),which is equivalent to the time interval for the impeller to rotates $2 ^ { \circ }$ . In order to ensure the convergence of calculation, the temporal history at a monitoring point which locates in the intersection between the midspan rotary surface $( Z _ { \mathrm { s } } { = } 0 . 5 )$ and the impeller/ volute interface is recorded and shown in Figure 3.The static pressure coefficient fluctuation at the monitored point has shown periodical unsteady changes after ten cycles(18oO iteration steps)，which indicates that the flow is fully developed and the calculation is converged.The static pressure coefficient is defined as:

$$
C _ { P } = \frac { P - P _ { i n } } { \rho _ { l } { u _ { 2 } } ^ { 2 } / 2 }
$$

![](images/1f75ebfb62a7a37897f5425d5e11d32ab622e66292d937232be52688963cbc9d.jpg)  
Fig.3Unsteady pressure signal at monitoring point

# Results and Discussion

# Cavitation performance

The cavitation performance of the micro-centrifugal pump is experimentally tested according to the Chinese GB3216-82 Standard. The test rig is a closed circuit with a container in the suction side of the pump,while a vacuum pump is installed on the container so as to adjust the suction pressure of the tested pump.The flow-rate is measured by an electromagnetic flow meter (BFGSDN50 type, range from 0 to $\mathrm { \bar { 2 0 } m ^ { 3 } h ^ { - 1 } }$ , an accuracy over the calibration range of $0 . 1 8 \%$ of reading). The pressure head is measured using a high resolution Bourdon tube. Inputshaft-work ismeasuredbycalculatingthe work-output of the driving motor, whose rotation speed is monitored and controlled at about $1 0 0 0 0 \mathrm { r / m i n }$ ·

Characteristics of cavitation in the high-speed micro centrifugal pump are simulated at several flow-rates. Figure 4(a) shows coefficient degradation characteristics of the head when cavitations occur, at $80 \%$ ， $100 \%$ and $120 \%$ of the design flow rate and under different cavitationnumbers.The cavitationnumber and head coefficient are defined as:

$$
\sigma = \frac { 2 ( P _ { t i n } - P _ { \nu } ) } { \rho _ { l } { u _ { 2 } } ^ { 2 } }
$$

$$
\scriptstyle \psi = \frac { 2 g H } { u _ { 2 } ^ { 2 } }
$$

Itcanbeobservedthatthe headcoefficienthasa sudden decrease when the cavitationnumberis decreased to the critical value,as expected under cavitating conditions. The critical cavitation number $\sigma _ { 3 \% }$ ，which denotes the cavitation number at which the pump head is degraded by $3 \%$ because of cavitation,is obtained by simulation and experiment, and are shown in Figure 4(b). The numerical values of $\sigma _ { 3 \% }$ are generally in good agreements with the experimental data.The results demonstrated that the numerical model and method can predict the cavitation flows precisely.

# Analysisofunsteadycavitatingflow

Figure 5 shows the distribution of volume fraction of vapour at the midspan of the impeller passage, for design flow-rate but with different cavitationnumbervalues.

![](images/66cd611d17175670b7af56d8daf94774896126d03e561fa3183689516ee9a123.jpg)  
Fig.4Performances of the micro centrifugal pump

![](images/d9b30205c63dc7541d982eb230bc33d53407be6d0fd5ddceab1a13951feb9e24.jpg)  
Fig.5Vapour fraction in the $Z _ { s } { = } 0 . 5$ of the impeller

Asmall and thin vapor bubble is initially observed to form near the leading edge of the suction side of the blades,as can be seen in Figure 5(a).As the cavitation number drops to O.054,the vapor bubbles grow in size along the suction side of the blades,and stretch to the middle of the blades in the flow passages.When the cavitationnumberis further decreased to O.O45,whichis called critical cavitation condition under design flow rate, the vapor bubbles almost occupy a half of the flow passages between blades,while the flow in the impeller is seriously affected.As a result, the head of the pump is degraded.

Figure 6 shows the instantaneous pressure distribution in the critical cavitation condition,in both the PS and SS sides of the blade and at three spanwise locations. Seeing from Figure 6, local minima appear on pressure surface of the blade near the leading edge. The pressure increases along the blade firstly，than start to decrease around $S { = } 0 . 8$ . Meanwhile,with the time changing,the pressure on blade surface will increase gradually; this is due to the blade moves close to the volute tongue.The pressure on blade suction surface at different $Z _ { s }$ locations is remained low values of almost 0.

![](images/8bc18126eac3fb8be3e89c8d222f3d6f6b9afe68edc2dfaeaf1f198d26aad104.jpg)  
Fig.6Instantaneous pressure profiles along blade surface

In order to analyse the effects of critical cavitation on the load of blade,Figure 7 shows the distribution of the blade surface loads at the midspan,at both non-cavitation and critical cavitation conditions.The blade surface load is defined as the pressure difference between the pressure and the suction sides at the same radius.Figure 7 clearly shows that,at both of the two conditions,the blade loads display a trend of increasing firstly and then decreasing, from the blade leading edge to the trailing edge. However,in the first half of the blade,the blade load $C _ { \mathfrak { p } }$ at the critical cavitation condition is considerably lower than that of the non-cavitation case.So when the cavitation occurs and develops， the work-doing capacity of the blades in the first half of their length is cut down.

Figure 8 shows the distribution of the root-meansquare of the unsteady pressure,the $P _ { r m s }$ on the blade surface. $P _ { r m s }$ is defined as follows:

$$
P _ { r m s } = \frac { \sqrt { \displaystyle \sum _ { i = 1 } ^ { N } ( P _ { i } - \overline { { P } } ) ^ { 2 } \left/ N \right. } } { \rho u _ { 2 } ^ { 2 } / 2 }
$$

where $N$ is the number of time steps in a rotation of the impeller, $N { = } 1 8 0$ in the current calculation as mentioned above.

It can be seen in Figures 8 (a) and 8(c) that $P _ { r m s }$ graduallydecreases from the trailing edge to the leading edge on blade surfaces,while along the blade height direction

![](images/f50817997c7a4a86fa45e00bb6d61007358f8ece66502c9c96958d8bbfeb9187.jpg)  
Fig.7Blade load along midspan arc-length

$P _ { r m s }$ changes very slightly. The $P _ { r m s }$ denotes the circumferential non-uniform pressure fluctuations,caused by the interaction between the impeller and the volute.The $P _ { r m s }$ value of critical cavitation is larger than that at the non-cavitation condition,as shown in Figures 8(a) and 8(b).However,on the suction surface,the situation is on the contrary. As shown in Figure 8(d), the $P _ { r m s }$ is almost zero,except at the trailing edge of the blade for the critical cavitation case.In such situation, due to the generation and development of vapour on the suction surface of blade, the pressure fluctuations become weak within the vapourregion, thevalueof $P _ { r m s }$ is therefore small.

![](images/9aa571565ca59741f30d85a8760ca235ec78b00461ac674b19457382eb046336.jpg)  
Fig.8 $P _ { r m s }$ on PS and SS of the blade

In order to analyse the non-uniform circumferential fluctuations,5 monitoring points are set up in the symmetric plane of the volute;positions of the monitoring points are shown in Figure 9.The fast Fourier transform (FFT) results for the frequency characteristics of pressure fluctuations at design flow rate for both the non-cavitation and critical cavitation flows are given in Figure 10. The dominant frequency of the pressure fluctuation is the blade passing frequency (BPF) at all monitored points for both the non-cavitation and the critical cavitation flows. The fluctuation amplitudes at the critical cavitation condition are considerably stronger than those of without cavitation case. Comparing the pressure modes in the frequency domain, a peak value is firstly found at BPF at monitoring point WK1 which is near the tongue of the volute. The maximum amplitude of the pressure pulsation is found at monitoring point WK2,which is about 50 degree in downstream of the tongue.

In order to find the reason why pressure fluctuation at WK2 is stronger than that at WK1，secondary flow streamlines distribution at WK1 and WK2 sections in the critical cavitation case are compared in Figure 11. The results show that the secondaryflowsatWK1 areweaker than those at WK2,where large-scale vortices are observed all the time.Reasonably, the stronger instantaneous secondary motions in cross-section WK2 contribute to the intense pressure fluctuations.

![](images/a46876308a67ffa2d6db25fb4e055e2f302afba86a958750c2b474a24ebd808e.jpg)  
Fig.9Monitoring points

![](images/7ec46f1e05f6165eadb9b9503f41686c1137e00de733bd420645c8cadfb2eeff.jpg)  
Fig.10FFT results of static pressure at monitoring points

# Conclusions

In this paper, numerical study on the unsteady cavitation flow in a high speed micro centrifugal pump has been carried out. The main conclusions are summarized as follows:

The amplitudes of pressure fluctuation at critical cavitation condition on the blade pressure surface are stronger than that in the non-cavitation case; but on the suction surface of the blade, the situation is on the contrary.When the cavitation occurs,reduction of load is observed mainly on the first half of the blades in the flow passages.

![](images/fefa9b52ee058eaa3094e3bd65002506882d2c20ad76d440f401bac83875563b.jpg)  
Fig.11Secondary flow in WK1 and WK2 sections

The unsteady interaction between impeller and volute results in large scale pressure fluctuations.When cavitation occurs,such interactions become stronger in amplitudes.Peak pressure fluctuations due to unsteady interaction are firstly observed near the volute tongue,while the strongest fluctuations occur at about 5O degrees in downstream of the tongue where the secondary flow is also strong and unsteady.

# Acknowledgments

The study in this paper is funded by the National NaturalScience Foundation of China under Grants 51176048 and 51576067.

# References

[1] X. Guan. Modern Pumps Theory and Design. China Astronautic Publishing House,Beijing,2011: pp.74-80.   
[2]R.F. Kunz, D.A. Boger, D. R. Stinebring, et al. A preconditioned Navier-Stokes method for two-phase flows with application to cavitation prediction. Comput & fluids 2000; 29(8): 849-875.   
[3]R.B. Medvitz,R.F. Kunz, D.A. Boger,et al.Performance analysis of cavitating flow in centrifugal pumps using multiphase CFD. Journal of Fluids Engineering, 2002,124(2): 377-383.   
[4]Y.Fu, J. Yuan, S. Yuan, et al. Numerical and Experimental Analysis of Flow Phenomena in a Centrifugal Pump Operating Under Low Flow Rates. Journal of Fluids Engineering,2015,137(1): 011102.   
[5]J. Yuan, Y.Fu.,S. Yuan，A Study of Cavitation Flow in a Centrifugal Pump at Part Load Conditions Based on Numerical Analysis. ASME 2012 Fluids Engineering Division Summer Meeting collocated with the ASME 2012 Heat Transfer Summer Conference and the ASME 2012 10th International Conference on Nanochannels, Microchannels,and Minichannels.American Society of Mechanical Engineers，Rio Grande,Puerto Rico,2012: 193-202.   
[6] Zwart P. J.,Gerber A. G. Belami T.“2004 A two phase flow model for predicting cavitation dynamics,” In: Proceeding of the 5th International Conference on Mulitphase Flow (ICMF 2004).30 May\~ 3 June 2004,paper no.152. Yokohama, Japan: Japanese Society for Multiphase Flow.   
[7]F. Bakir,R. Rey,A. G.Gerber,et al. Numerical and experimental investigations of the cavitating behavior of an inducer. International Journal of Rotating Machinery, 2004,10(1): 15-25.   
[8] V. Yakhot, S. A .Orszag, S. Thangam, et al. Development of turbulence models for shear flows by a double expansion technique. Physics of Fluids A: Fluid Dynamics,1992,4(7): 1510-1520.   
[9]L. Zhou, Z. Wang. Numerical Simulation of Cavitation Around a Hydrofoil and Evaluation of a RNG k-ε Model. Journal of Fluids Engineering,2008,130(1): 011302.   
10] L. Tan, S. Cao, Y. Wang, et al. Direct and inverse iterative design method for centrifugal pump impellers. Proceedings of the Institution of Mechanical Engineers, Part A: Journal of Power and Energy,2012,226(6): 764-775.   
11]N. Dittakavi, A. Chunekar, S. Frankel. Large Eddy Simulation of Turbulent-Cavitation Interactions in a Venturi Nozzle. Journal of Fluids Engineering,2010,132(12): 121301