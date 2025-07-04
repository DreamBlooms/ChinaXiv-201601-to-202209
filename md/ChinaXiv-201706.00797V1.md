# Interaction of Two Cavitation Bubbles in a Tube and its Effects on Heat Transfer

LIU $\mathbf { B } \mathbf { i n } ^ { 1 }$ ,CAI $\mathbf { J u n } ^ { 1 , 2 }$ , TAO Yuequn1,², HUAI Xiulan 1

1. Institute of Engineering Thermophysics, Chinese Academy of Sciences, Beijing 100190, China 2. University of the Chinese Academy of Sciences, Beijing 10o080, China $\copyright$ Science Press and Institute of Engineering Thermophysics, CASand Springer-Verlag Berlin Heidelberg 2017

When two cavitation bubbles exist in aconfined space,the interaction between the bubbles significantly affects thecharacteristics of bubble dynamic behaviors.In this paper,a three-dimensional(3D)model is established to studythe growth and collapse oftwo cavitation bubbles in aheated tube and its effects on heat transfer.The liquid and gas phases throughout the calculation domain are solved by a set of Navier-Stokes equations.It is assumed that the gas inside the bubble is compressible vapor,and the surrounding liquid is incompressible water.The mass transfer between two phases is ignored.The calculated bubble profiles were compared to theavailable experimental data,and a good agreement has been achieved.Then,the relationship among the bubble motion,flow field and pressure distributions was analyzed.On this basis,the effects of bubble interaction on the heat transfer between the wall surfaceand sounding liquid were discused.Itis found that heat transfer in the centre wallregion is enhanced owing to the vortex flow and micro-jet induced by the bubble contractionand colapse.In contrast, the highest surface temperature appears in the surrounding region, which is mainly attributed to the thermal esistance induced by the bubble.The present study is helpful to understand the heat transfer phenomenon with cavitation in the liquid.

# Keywords: Cavitation,Interaction effects,Bubble dynamics,Heat transfer

# Introduction

The existing of caviation bubbles in a liquid can cause noise and erosion,which isveryharmful and should be avoided in the hydrodynamic system[1-5]. However, on the other hand, those bubbles can also be widely applied in many fields,such as ultrasonic cleaning，waste water degradation, shock wave lithotripsy,and enhancing heat transfer[6-11]. Therefore, extensive studies on the cavitation bubble dynamics have been conducted to reveal the mechanism of cavitation.The development of high speed photography technique makes it possible to capture the extremely complex dynamic processes of cavitation bubbles.Brujan et al.[12] investigated the behavior of the laser-induced cavitation bubbles near a boundary. They pointed out that the shape of the liquid jet formed after the bubble collapse is strongly dependent on the dimensionless distance between the bubble and boundary. Then, the penetrating jet and its impacts on the opposite wall of the non-spherically bubble collapse were further studied. The maximum jet velocity and shock pressure up to 280 $\mathrm { m / s }$ and 25 GPa during the collapse stage have been observed[13]. Yang et al.[4] employed the hydrophone system with a sample rate of1 billion samples per second to monitor the dynamic features of a cavitation bubble near the solid boundary. The energy loss of the bubble from the first maximum expansion to the second maximum expansion has been estimated.The cavitation bubble in a liquid gap and a confined space with more than one boundary has also been widely studied.It is found that boundary layers will hinder the bubble collapse as well as the formation of the micro-jet[15]. Due to the short duration of bubble evolution,most high speed cameras are not fast enough to capture the actual time of bubble dynamics.Numerical simulation provides a powerful tool that can more accurately reveal the mechanism of cavitation by setting the parameter ranges that are dificult to achieve in the experiment.The Rayleigh-Plesset equation was proposed to describe the shape evolution of the bubble and liquid jets[16]. Furthermore, the theory was modifiedby considering the contact angle,surface tension and kinematic viscosity, which makes the results agreeing better with the experimental observations[17]. With the development of numerical techniques,more methods have been widely applied on cavitation bubble dynamics, such as the level-set, BEM,Front tracking and VO8-21] Researches mentioned above lay a solid foundation for the application of cavitation. In recent years,it is found that the cavitating flow can significantly enhance heat transfer, which has drawn a wide attention from scholars[22].Liu et al.[23] investigated the behavior of a single bubble near a heated boundary. Results show that the micro-jet formed during the bubble collapse is mainly responsible for the reinforcement of heat transfer. On this basis,the single bubble in a narrow gap and a micro-tube with constant heat fluxes are continually investigated to reveal the mechanism of the heat transfer enhancement by cavitation[24].Due to the complexity of the bubble dynamic model,most studies are on the simplifying assumption that the bubble is in a relatively isolated space without considering the interaction effect. However, when the cavitation occurs in the liquid, the bubbles are interrelated. Thus，the interaction effects between the bubbles should be considered in the study of bubble dynamics.Still, rather few modeling efforts have been reported on the bubble-bubble interaction in cavitation,as well as its effects on heat transfer. The present work describes a numerical investigation on the dynamics of two cavitationbubblesinaheatedtube.Athree-dimensional (3D)model is established to study the interaction effects of these bubbles and heat transfer. The liquid and gas phases throughout the calculation domain are solved by a set of Navier-Stokes equations. The volume of fluid (VOF) method is employed to track the interfaces of the two bubbles.

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>E</td><td>total energy (J)</td><td>Z</td><td>z coordinate (m)</td></tr><tr><td>F</td><td>force (N)</td><td colspan="2">Greek letters</td></tr><tr><td>h</td><td>heat transfer coefficient (W/m²-K)</td><td>p</td><td>Density (kg/m³)</td></tr><tr><td>H</td><td>distance from the centre point to the bubble</td><td>α</td><td>volume fraction (-)</td></tr><tr><td>k</td><td>effective conductivity (W/ m·K)</td><td>μ</td><td>viscosity (kg/m·s)</td></tr><tr><td>L</td><td>length of the tube (mm)</td><td>k</td><td>curvature of the interface (1/m)</td></tr><tr><td>M</td><td>molecular weight (kg/mol)</td><td>S</td><td>surface tension (N/m)</td></tr><tr><td>p</td><td>static pressure (Pa)</td><td colspan="2">Subscripts</td></tr><tr><td>q</td><td>heat flux (W/cm²)</td><td>f</td><td>fluid</td></tr><tr><td>R</td><td>bubble radius (mm)</td><td>g</td><td> gas phase</td></tr><tr><td>Rg</td><td> gas constant (J/K·mol)</td><td>1</td><td>liquid phase</td></tr><tr><td>t</td><td>time (s)</td><td>W</td><td>wall surface</td></tr><tr><td>T</td><td>temperature (K)</td><td>max</td><td>maximum value</td></tr><tr><td>V</td><td>velocity (m/s)</td><td>t</td><td>total</td></tr><tr><td>X</td><td> x coordinate (m)</td><td>0</td><td>initial</td></tr><tr><td>y</td><td>y coordinate (m)</td><td>8</td><td>far field</td></tr></table></body></html>

# Numerical Method

In this calculation, the liquid phase is incompressible pure water. The bubble is considered to be filled with vaporbehavingasanideal gas.Theheattransferbetween the gas and liquid phase is ignored due to a very short duration of the bubble evolution.The flow pattern is assumed to be laminar in the whole domain,which is described by one set of Navier-Stokes equations.

# Governing equations

The mass conservation equation for the mixture is expressed as

$$
\frac { \partial \rho } { \partial t } + \boldsymbol { \nabla } \cdot \left( \rho \vec { \nu } \right) = 0
$$

where $\rho , ~ \vec { \nu }$ and $t$ are the fluid density, velocity and time,respectively.

The momentum equation is given by

$$
\frac { \partial } { \partial t } \big ( \rho \vec { \nu } \big ) + \boldsymbol { \nabla } \cdot \big ( \rho \vec { \nu } \vec { \nu } \big ) = - \boldsymbol { \nabla } p + \boldsymbol { \nabla } \cdot \bigg [ \mu \Big ( \boldsymbol { \nabla } \vec { \nu } + \boldsymbol { \nabla } \vec { \nu } ^ { T } \Big ) \bigg ] + \vec { F }
$$

where $p$ is the static pressure, $\mu$ is the viscosity, $\vec { F }$ is the sum of external body forces and is expressed as

$$
\vec { F } = \sigma \frac { \rho \kappa \nabla \alpha _ { \mathrm { g } } } { 0 . 5 \big ( \rho _ { \mathrm { g } } + \rho _ { \mathrm { l } } \big ) }
$$

where $\sigma$ is the surface tension coefficient, $\kappa$ is the curvature of the interface.

The energy equation is given by the following form

$$
\frac { \partial } { \partial t } \big ( \rho E \big ) + \boldsymbol { \nabla } \cdot \big ( \vec { \nu } \big ( \rho E + p \big ) \big ) = \boldsymbol { \nabla } \cdot \big ( k \boldsymbol { \nabla } T _ { \mathrm { f } } \big )
$$

where $k$ is the effective conductivity, $T _ { \mathrm { f } }$ is the fluid temperature, $E$ is the total energy.

The liquid-gas interface is calculated by the volume fraction equation

$$
\frac { \partial \alpha _ { 1 } } { \partial t } + \vec { \nu } \cdot \nabla \alpha _ { 1 } = 0
$$

The volume fraction of the gas phase is given by

$$
\alpha _ { \mathrm { l } } + \alpha _ { \mathrm { g } } = 1
$$

where $ { \boldsymbol { a } }$ is the volume fraction,and the subscripts“l and “g” represent the liquid phase and gas phase, respectively

The average fluid density and viscosity in each cell are calculated according to the volume fraction values of gas and liquid, which are expressed as

$$
\begin{array} { r } { \rho = \rho _ { \mathrm { l } } \alpha _ { \mathrm { l } } + \rho _ { \mathrm { g } } \alpha _ { \mathrm { g } } } \\ { \mu = \mu _ { \mathrm { l } } \alpha _ { \mathrm { l } } + \mu _ { \mathrm { g } } \alpha _ { \mathrm { g } } } \end{array}
$$

The density of the gas phase is given as

$$
\rho _ { \mathrm { g } } = { \frac { p M } { R _ { \mathrm { g } } T _ { \mathrm { f } } } }
$$

where $R _ { \mathrm { g } }$ is the gas constant, $M$ is the molecular weight of the vapor.

The two interacted bubbles are initially patched in a heatedtubewiththeradiusof $8 ~ \mathrm { m m }$ ,andthecalculation domain is shown in Fig.1.The distances from the left and right bubble to the centre point of the tube are the same $\left( H _ { \mathrm { l e f t } } = H _ { \mathrm { r i g h t } } \right)$ .Therefore，behavioursof the two bubbles are symmetrical in the calculation. In order to eliminate boundary effects, the total length of the tube is set to be $1 6 0 ~ \mathrm { m m }$ . The grids in the region of $- 4 R _ { \mathrm { m a x } } { < } x <$ $4 R _ { \mathrm { m a x } }$ is refined so as to precisely capture the motion of the bubbles.It is found that the results are independent when the number of grid cells is more than $3 . 6 \bar { \times } 1 0 ^ { 5 }$ A constant heat flux of $\mathsf { \bar { q } } = 2 0 \mathrm { \ W / c m } ^ { 2 }$ is imposed on the tube surface.For the pressure outlet boundary, the value of $p _ { \mathrm { o u t } } { = } 0 . 1$ MPais employed.The volume of fluid(VOF) method is employed to track the interfaces of two bubbles.The pressure-implicit with splittng of operators (PISO) algorithm is adopted to solve the flow field. The pressure staggering option (PRESTO) scheme is used for the pressure interpolation at the cell faces.The VOF equation is explicitly solved with the geometric reconstruction scheme.The second order upwind scheme is selected for computing the mass, momentum and energy conservation equations. The mathematical model is solved with the time step of $1 \times 1 0 ^ { - 5 }$ s. The convergence criterion is $1 0 ^ { - 5 }$ for the continuity and momentum equations, and ${ { 1 0 } ^ { - 6 } }$ for the energy equation.

![](images/29a872bf3cce1f05f299113ef3d7ab7234765f34f80abf0bc711300810fa51ac.jpg)  
Fig.1 Calculation domain of the present model

# Results and discussion

The initial radii of the bubbles are $R _ { \mathrm { l e f t , 0 } } { = } R _ { \mathrm { r i g h t , 0 } } { = } 0 . 8$ mm,and values of initial pressure and temperature of the bubbles are $p _ { \mathrm { l e f t , 0 } } { = } p _ { \mathrm { r i g h t , 0 } } { = } 1 0 \ \mathrm { M }$ Pa and $T _ { \mathrm { l e f t , 0 } } { = } T _ { \mathrm { r i g h t , 0 } } { = } 1 2 0 0$ K,respectively. The initial centre distance between two bubbles is $H _ { 0 } { = } 3 . 6 ~ \mathrm { m m }$ ，and the initial temperate of the liquid in the domain is $T _ { \mathrm { w } } { = } 3 0 0 ~ \mathrm { K }$ .The numerical results are compared with the observation result from the experiment by Ji et al.[25],as shown in Fig.2. The evolution of two cavitation bubbles in a tube obtained by the present simulation agrees well with the experimental photography,which proves the accuracy and reliability of the model. Due to the interaction effects，dynamic behaviours of each individual bubble are significantly influenced,which is very different from the case of a single bubble near a solid boundary or between the two parallel walls.At the beginning, the initially both spherical bubbles grow to a roughly ellipsoidal shape,and the growth rate of the inner side of the bubble is lower than that of outer side.In the late stages of the growth phase, only a very thin liquid film is left between the two bubbles,as shown in Fig.2(a).With further expansion, the two bubbles merge into a bigger one (See Fig. 2(b)). After reaching the maximum volume,the bubble begins to collapse. Figure 2(c) shows that, during the collapse stage,it firstly shrinks from the left and right side to the bubble centre. Then, the bubble is penetrated by the liquid jets from the left and right sides and is separated into two small sub-bubbles at the final stage of the first collapse phase. As shown in Fig.2(d), the sub-bubbles are finally penetrated by the liquid jets towards the wall surface and turn into a ring shape,which is the second collapse being similar to that of a single bubble near a solid boundary or between two parallel walls.

8

Figure 3 shows the typical flow fields around the two interacted bubbles at different times.The reference velocity of the flow jet is represented by the arrow at the upper right corner of each drag.It can be seen that at $t =$ $0 . 4 \mathrm { ~ m s ~ }$ ，in the growth phase of the bubbles,the liquid between the bubbles is squeezed out leaving only a very thin film. Meanwhile, the outward flow jets with the maximum velocity of $4 . 5 ~ \mathrm { { m } / \mathrm { { s } } }$ can be observed around the bubbles,as shown in Fig.3(a).After the fusion of two bubbles， the merged bubble continually grows until reaching the maximum volume.Also,it is shown that the speed of the outflow jet gradually decreases during the late stage of the growth phase being about only $2 ~ \mathrm { m / s }$ at $t$ $= 1 . 4 ~ \mathrm { m s }$ ，which is attributed to the weakened effects of the bubble expansion (see Fig.3(b)). During the first collapse phase,as can be seen, the opposing inflow jets near the left and right sides of the bubble are formed due to the contraction of the bubble interface.Meanwhile, the liquid micro-jets develop on the upper and lower sides of the bubble,which flow outward along the tube after impinging on the rigid surface,as shown in Fig. 3(c). It is shown in Fig.3(d) that the micro-jets directing towards the rigid surface finally penetrate the sub-bubbles in the second collapse phase and the maximum velocity of the jets increases to about $1 2 ~ \mathrm { m / s }$ However, the velocity is still much lower than the case of a single bubble near a solid boundary or between two parallel walls. This is because of the hinder effect of the bubble. In addition, the flow fields around the bubbles show that, in the first and second collapse phases, stagnation points exist on the middle of the tube surface due to the impinging of the micro-jets (vortex flow).

Figure 4 shows the pressure contours around the bubbles with various times. The initial pressure inside the bubble is up to $1 0 ~ \mathrm { M P a }$ ，which releases extremely high energy at the very beginning of the growth and leading to the bubble expansion.However, the motion of bubble interface lags behind the transmission of pressure in liquid.Thus,it can be observed that pressure in the bubble is even lower than it in the surrounding liquid, in spite of the bubble growth (see Fig. 4(a)\~(b)). As time goes on, the bubble begins to collapse after growing to the maximumvolume.When $t = 2 . 8 ~ \mathrm { m s }$ ，it can be seen that the higher pressure around the bubble lead to the bubble contraction,as shown in Fig.4(c). Thus,inflow jets towards the tube centre are developed which causes the shrinking and splitting of the bubble in the first collapse phase.In contrast,the pressure field in the tube centre region between two sub-bubbles shows a significant increase in the second collapse,as shown in Fig. 4(d). When $t = 4$ ms,a maximum value of $1 . 3 2 ~ \mathrm { M P a }$ is observed in the high pressure region,which is the main reason for a higher velocity of the impinging jets observed in Fig.3(d).

![](images/4f2a3593eac19576cc0459a5313de570358404ed854b75a894b32175ba3b565c.jpg)  
Fig.2 Comparison between the numerical and experimental results   
Fig.3Flow fieldsaround the bubbles

The deformation of the bubbles and the resulting liquid flow would affect heat transfer between the liquid and the wall. Figure 5 shows the temperature distributions of the wall surface along the $x$ direction.On the whole,temperature of the wall surface gradually increases as the heating time.During the growth phase of the bubbles, temperature along the tube surface is almost unaffected due to the limited effects of the liquid flow.In contrast, the bubble interface gets closer to the wall surface as well as the resulting liquid flow in the first collapse phase.Thus,heat transfer in the centre region of the wall is enhanced owing to the impinging effects of the vortexflow inducedbythebubblemotion.

Heat transfer deterioration is found around the centre region of the wall,which is mainly attributed to the thermal resistance induced by the bubble.During the late stages of the second collapse phase, the heat transfer enhanced region is narrowed (in the range of $- 0 . 0 0 2 < x <$ 0.002,when $\scriptstyle t = 4 { \mathrm { ~ m s } }$ ） due to the limited width of the impinging jet.

p (Pa)58000640007000076000820008800094000 1000000.004  
宣 0 OO  
y-0.004 -0.01 -0.005 0 0.005 0.01x (m)(a) $t = 0 . 4 ~ \mathrm { m s }$ （204号P (Pa)20000 25000 30000 35000 40000 45000 50000  
直 0.004 0 8  
y-0.004-0.01 -0.005 0 0.005 0.01x (m)(b) $t = 1 . 4 ~ \mathrm { m s }$ p (Pa)20000 25000 30000 35000 40000 45000 50000 550000.004  
(u) 0-0.004-0.01 -0.005 0 0.005 0.01x (m)(c) $t = 2 . 8 ~ \mathrm { m s }$ （204p (Pa)100000 104000 108000 112000 116000 120000 124000 128000 1320000.00400  
目 0  
y-0.004-0.01 -0.005 0 0.005 0.01x (m)(d) $t = 4$ ms

![](images/92224f32a001f70b8a391e90629bb7629d0b0215ac5224ac222012e2ef33a0bc.jpg)  
Fig.5Distributions of the wall temperature

Figure 6 displays the changes of the wall temperatures with time. The $T _ { \mathrm { w } , \infty }$ ， $T _ { \mathrm { w , c } }$ and $T _ { \mathrm { w , m a x } }$ are the wall temperature at the far field, the wall temperature at the centre point (stagnation point) and the maximum wall temperature,respectively.It can be seen that the $T _ { \mathrm { w , \infty } }$ increases lineallyunder the constant heat fluxwithout anydisturbance. The increasing rate of $T _ { \mathrm { w , c } }$ is much lower than $T _ { \mathrm { w } , \infty }$ especially during the late stages of the second collapse phase.It is believed that the impinging micro-jet formed during the second bubble collapse plays a major role for the better effects of heat transfer enhancement. The $T _ { \mathrm { w } , }$ $\operatorname* { m a x }$ is almost the same as $T _ { \mathrm { w } , \infty }$ before $2 ~ \mathrm { m s }$ .Since then, it rises dramatically because the bubble are getting closer to thewall surface and therefore induce extraheat transfer resistance.For the application of cavitating flow in heat transfer, the micro-jet should be strengthened and the bubble interface should keep away from the heating surface by the control of the bubble dynamic behaviours.

![](images/57c82d0f1c14bb0c67052f5cd3182a30247f2f80102d6a94c900252a364e0e09.jpg)  
Fig.4Pressure distributions around the bubbles   
Fig.6Variations of the wall temperatures with time

# Conclusions

On the basis of the VOF method,the interaction of two cavitation bubbles in a tube is numerically investigated together with its effect on heat transfer by using a three-dimensional model. The evolution of bubble profile results show that the bubble mainly grows along the length ( $x$ direction） of the tube because of the wall restriction. The bubble changes to a roughly ellipsoidal and onlya very thin liquid film is retained between the bubbles.With further expansion, the bubbles finally merged intoa single one.The outward flowhas beenobserved in thebubble growth process.After reaching the maximum volume,the single bubble begins to collapse.It firstly shrinks from the left and right side to the centre. Then, the liquid jets from the left and right sides will penetrate the bubble and separate it into two sub-bubbles. The sub-bubbles continually shrink and are penetrated by liquid jets and turn into a ring shape,which is the second collapse being similar with the case of a single bubble neara solid boundary or between two parallel walls.Heat transfer at the centre region of the wall surface is enhanced owing to the vortex flow and the micro-jet induced by the bubble contraction and collapse.In contrast, the highest surface temperature appears in the surrounding region,which is mainly attributed to the thermal resistance induced by the bubble.During the late stages of the second collapse phase,the heat transfer enhancement effect is better due to the impinging of the micro-jet. Meanwhile, the value of $T _ { \mathrm { w , \infty } }$ has a significant increase after $2 ~ \mathrm { m s }$ because of the heat transfer resistance induced by the bubble interface.Thus,the bubble interface should keep away from the heating surface to avoid the heat transfer deterioration.In the future work,the effects of such parameters as the initial bubble radius, pressure and position on bubble dynamics and heat transfer will be discussed in details.

# Acknowledgement

This work is financially supported by the National Natural Science Foundation of China (Grant No. 51606190, Grant No. 51376181).

# References

[1]EscalerX.,EgusquizaE.,FarhatM.,AvellanF.,Coussirat M.:Detection of cavitation in hydraulic turbines,Mechanical Systems and Signal Processing,vol.20,pp.983 -1007,(2006).   
[2]Dorji U.,Ghomashchi R.: Hydro turbine failure mechanisms:An overview, Engineering Failure Analysis,vol. 44, pp. 136-147,(2014).   
[3]Ryl J.,Wysocka J., Slepski P.,Darowicki K.: Instantaneous impedance monitoring of synergistic effect between cavitation erosion and corrosion processes, Electrochimica Acta, vol.203,pp.388-395,(2016).   
[4]KimK.H., Chahine G.,Franc J.P.,Karimi A.: Advanced experimental and numerical techniques for cavitation erosion prediction,Springer Netherlands,Dordrecht, (2014). [5]Singh R., Tiwari S.K., Mishra S. K.: Cavitation erosion in hydraulic turbine components and mitigation by coatings: current status and future needs, Journal of Materials Engineering and Performance,vol.21,pp. 1539-1551, (2012).   
[6] Niemczewski B.: Cavitation intensity of water under practical ultrasonic cleaning conditions,Ultrasonics Sonochemistry,vol.21, pp.354-359,(2014). [7]Verhaagen B., Fernández R. D.: Measuring cavitation and its cleaning effect, Ultrasonics Sonochemistry,vol.29,pp. 619-628,(2016). [8]Angaji M. T., Ghiaee R.: Decontamination of unsymmetrical dimethylhydrazine waste water by hydrodynamic cavitation-induced advanced Fenton process, Ultrasonics Sonochemistry, vol. 23, pp.257-265,(2015). [9]Dular M.，Griesslerbulc T.,Griesslerbulc I.，Heath E., Kosjek T.,Klemencic A. K.， Oder M., Petkovsek M., Racki N., Ravnikar,M. Sarc A., Sirok B., Zupanc M., Zitnik M.,Kompare B., Use of hydrodynamic cavitation in (waste） water treatment, Ultrasonics Sonochemistry, vol. 29, pp. 577-588 (2016).   
[10]Frank S., Lautz J.， Sankin G. N., Szeri A.J., Zhong P.: Bubble proliferation or dissolution of cavitation nuclei in the beam path of a shock-wave lithotripter, Physical Review Applied, vol. 3, pp.034002,(2015).   
[11]Schneider B., Kosar A.,Kuo C.J.,Mishra C., Cole G. S., Scaringe R.P., Peles Y.: Cavitation enhanced heat transfer in microchannels, Journal of Heat Transfer, vol.128, pp. 1293-1301,(2006).   
[12]Brujan E. A., Nahen K., Schmidt P., Vogel A.: Dynamics of laser-induced cavitation bubbles near an elastic boundary, Journal of Fluid Mechanics,vol. 433, pp.251-281, (2001).   
[13] Brujan E.A., Ikeda T. Matsumoto Y.: On the pressure of cavitation bubbles,Experimental Thermal and Fluid Science, vol.32, pp.1188-1191,(2008).   
[14]Yang Y. X., Wang Q. X., Keat T. S.: Dynamic features of a laser-induced cavitation bubble near a solid boundary, Ultrasonics Sonochemistry，vol. 20，pp.1098-1103, (2013).   
[15]Ohl C.,Avila S.R., Klaseboer E.Liu A. Q., Tandiono T., Ando K.: Cavitation in confined spaces,The Journal of the Acoustical Society of America,vol.131,pp. 3338- 3338, (2012).   
[16]Hilgenfeldt S., Brenner M. P., Grossmann S., Lohse D.: Analysis of Rayleigh-Plesset dynamics for sonoluminescing bubbles,Journal ofFluid Mechanics, vol.365,pp. 171-204,(1998).   
[17]Wafaa S., Tetsutaro N.,Noriharu T., Koichi S.: Modification of Rayleigh-Plesset Theory for Reproducing Dynamics of Cavitation Bubbles in Liquid-Phase Laser Ablation, Japanese Journal of Applied Physics,vol. 49, pp. 116202,(2010).   
[18] Huang J., Zhang H.: Level set method for numerical simulation of a cavitation bubble,its growth,collapse and rebound neara rigid wall,Acta Mechanica Sinica,vol.23, pp.645-653,(2007).   
[19] BalS.,Kinnas A.S.,ABEM for the prediction of free surface effects on cavitating hydrofoils, Computational Mechanics,vol.28,pp.260-274,(2002).   
[20] Tryggvason G.,Bunner B., Juric D.,Rawahi N.,Han J., NasS., Jan Y.J.:AFront-Tracking Method for the Computations of Multiphase Flow, Journal of Computational Physics,vol.169,pp.708-759,(2001).   
[21] Sussman M.,A second order coupled level set and volume-of-fluid method for computing growth and collapse of vapor bubbles, Journal of Computational Physics,vol. 187,pp.110-136,(2003).   
[22] Cai J.,Huai X.L., Yan R., Cheng Y., Numerical simulation on enhancement of natural convection heat transfer by acoustic cavitation in a square enclosure,Applied Thermal Engineering,vol.29 pp.1973-1982,(2009).   
[23] LiuB.,Cai J.,Huai X.L.,LiX.F.:Cavitation bubble collapse near a heated wall and its effect on the heat transfer,Journal of Heat Transfer,vol.136,pp.022901- 022901,(2013).   
[24] Liu B., Cai J., Huai X.L.: Heat transfer with the growth and collapse of cavitation bubble between two parallel heated walls,International Journal of Heat and Mass Transfer, vol. 78,pp. 830-838,(2014).   
[25]Ji C.:Numerical and experimental research of bubble behavior in restricted space,Doctoral dissertation, Zhejiang University,Hangzhou, China,(2013).