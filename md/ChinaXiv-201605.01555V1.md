# A NUMERICAL SIMULATION OF COSMIC-RAY MODULATION NEAR THE HELIOPAUSE

X1 LUO12, MING ZHANG³, MARIUS POTGIETER², XUESHANG FENG1, AND N. V. POGORELOV4 SIGMA Weather Group,State Key Laboratory of Space Weather,Center for Space Science and Applied Research, Chinese Academy of Sciences,Beijing 10019o,China 2CentreforSeestsocheso Departmentofceerdoeited Departmentof Physicsand Center for Space Plasmaand Aeronomic Research,Universityof Alabama in Huntsville, 301 Sparkman Drive,Huntsville,AL 35899,USA Received 2015February 24;accepted 2015 June9;published 2015 July 21

# ABSTRACT

Based on a hybrid galactic cosmic-ray transport model, which incorporated MHD global heliospheric data into Parker'scosmic-ray transport equation, we studied the behavior of the transport of galactic cosmic rays and the corresponding gradients in their flux near the heliopause (HP).We found that,(1) by increasing the ratio of the parallel difusioncoeficient to the perpendicular diffusion coeficient in the interstellar magnetic field of the outer heliosheath, the simulated radial flux near the HP increases as well As the ratio multiplying factor reached $1 0 ^ { 1 0 }$ the radial fux experienced a sudden jump near the HP,similar to what Voyager 1 observed in 2012.(2) The effect of changing the diffusion coefcients’ratioon the radial flux variation depends on the energyof the cosmic rays, the lower the energy,the more pronounced the effect is.（3)The magnitudeof the diffusion coefficients also affect theradial flux near the HP,the modulation beyond the HP varies by adjusting the magnitude multiplying factor.

Key words: cosmic rays - magnetohydrodynamics (MHD）- Sun: heliosphere

# 1.INTRODUCTION

After nearly four decades since it was lunched,Voyager $\jmath$ is now more than 13O AU from the Earth.Recent observations indicate that Voyager1 may have already entered into the local interstellar medium (ISM).It was found that the above $7 0 \mathrm { M e V }$ galactic cosmic-ray intensity increased about $30 \%$ on 2012 August 25 as the spacecraft was at $1 2 1 . 7 \mathrm { A U }$ ，and at the same time,the anomalous cosmic-ray intensity detected by the Low Energy Charged Particle instrument decreased by an order of magnitude(Krimigis et al. 2013; Stone et al.2013;Webber & McDonald 2O13).In addition to the cosmic-ray intensity change,Decker et al.(2O12） found that the plasma speed at Voyager $\boldsymbol { { \mathit { 1 } } }$ is nearly zero after 2O1O April. Since it is widely accepted that the galactic cosmic-ray intensity should increase while anomalous cosmic-ray intensity should decrease when crossing the heliopause(HP)，these signatures are consistent with the HP crossing by Voyager 1.

Burlaga et al. (2O13),however, found that the magnetic feld direction did not change significantly during these cosmic-ray intensity changing events,and that the magnetic field lines still coincided more or less with the overall structure of the heliospheric spiral line.This is far different from the direction of the expected ISM magnetic field even after a draping of field lines by the center heliosheath has been taken into account.At first, this caused some uncertainty; thus,it was suggested that Voyager 1 had crossed a well-defined boundary for energetic particles that was possibly related to the HP (Webber & McDonald 2O13)，and that Voyager 1 was in a“heliosheath depletion region” (Burlaga et al. 2013;Krimigis et al. 2013; Stone et al. 2O13).More recently, the plasma wave instrument on Voyager1（Gurnett et al.2O13） detected locally generated plasma oscillations with a frequency consistent with the plasma density of the local ISM. Thus,it has become more certain that Voyager1 is in the local ISM,or at least in the very local ISM. Despite the latter observation, some debate still continues,e.g., Fisk & Gloeckler（2O14） proposed a model that is consistent with all of the Voyager 1 observations,but assuming that Voyager $\boldsymbol { { \mathit { 1 } } }$ isstill in the inner heliosheath.Later,Gloeckler & Fisk（2O14） even provided a test for this model. Meanwhile, Borovikov & Pogorelov（2014）argued that Voyager 1 might have been inside eddies formed by plasma instabilities at the HP.Alternative arguments were presented by e.g., Grygorczuk et al.(2014)and Strumik et al.(2014).Future data from Voyager $\boldsymbol { l }$ and the expected crossing of the HP by Voyager 2, perhaps sooner than expected,will surely enlighten us.Burlaga & Ness(2O14）showed that the sector boundary predicted byFisk & Gloeckler（2O14）had not been observed through 2014/151 and that the field direction, but not the magnitude, has been quite constant for this period.In addition,both the larger than 7O and $0 . 5 \mathrm { M e V }$ cosmic-ray counting rates detected by Voyager1 have been essentially constant for nearly three years (http://voyager.gsfc.nasa.gov/heliopause/data.html).

The observational data from Voyager 1 have stimulated also several theoretical investigations of galactic cosmic-ray transport near the HP. Scherer et al. (2O11) and Strauss et al. (2013) argued that the HP is not the modulation boundary for galactic cosmic rays so that there should be some level of modulation thathappened beyond the HP (in the outer heliosheath (OHS)). On the other hand,Kota & Jokipii (2O14) arrived at the opinion that galactic cosmic ray modulation is very small beyond the HP if the diffusion coefficients in this region are set to be large enough.Later，Guo & Florinski （2O14） shared the same opinion that galactic cosmic-ray modulation beyond the HP is negligible.

In such an atmosphere where different opinions exist, we are motivated to perform an independent study on this issue and strive to contribute some understanding for the community. Specifically，we will use a stochastic differential equation (SDE） numerical approach to investigate the galactic cosmicraytransport in a global heliosphere from an MHD-neutral kinetic simulation，which is thought to be as realistic as possible.A brief description of our numerical model, the hybrid transport model, will be presented in the subsequent section.In the third section,we will discuss our simulation results: the galactic cosmic-ray spectra, the simulated radial flux variations by modifying the diffusion coefficients differently,and some possible mechanism for the simulation results.We will conclude in the last section.

![](images/39de6fe47885335e3d28801e8070a576f5f69d9812f9310863ac1d5b67768bdd.jpg)  
Figure 1.MHD simulated profile of the magnetic field magnitude along the meridional plane (X-Z plane).Trajectories of the two spacecraft Voyager $I$ and Voyager2 are projected onto the same plane as shown by the white lines.The black curves outline the profiles of the termination shock and HP,respectively.

# 2.NUMERICALMETHOD

We performed this investigation by using a hybrid galactic cosmic-ray transport model, incorporating the output from a global heliospheric MHD model into the galactic cosmic-ray transport SDE-type code.SeeLuo et al.(2013）for details of this approach.

# 2.1.Realistic MHD Global Heliosphere Model

The numerical MHD global heliospheric data,which supply the plasma and magnetic field background to the galactic cosmic-ray transport model,is obtained by solving a set of MHD equations which describe the interaction between the ISM and the solar wind plasma flow. The ISM is partially ionized. Neutral ISM atoms interact with plasma through charge exchange and photoionization provide an extra source of particle momentum and energy.A multi-component model of neutral atoms is used where the latter are subdivided into populations depending on the place of their origin and further treated gasdynamically as separate fluids (Zank 1996; Pogorelov et al. 2OO6). For details,see Pogorelov et al.(2009a, 2009b，2012，2013).MHD simulations are performed on a grid,while their results may be required at arbitrary points inside the computational regions.These are obtained by interpolation.

Figure 1 shows a snapshot distribution of the magnetic field in the meridional plane formed by the Sun's rotation axis (the $Z$ -axis）and the unperturbed LISM velocity vector.As a result, the $X$ -axis belongs to the meridional plane and is directed upwind from the LISM. Similarly,Figure 2 shows the snapshot distribution of the plasma speed's radial component in the meridional plane. The trajectories of the two Voyager spacecraft,the profiles of the termination shock and HP are also shown in Figure 1.Based on these two figures,we note that there is a strong $\scriptstyle { V I - V 2 }$ asymmetry of the heliopause,which is created by the interstellar magnetic field (Pogorelov et al. 2008).It should be stated that within the confines of our MHDneutral model, the position of the heliopause in the $V I$ trajectory direction is overestimated(146AU instead of the observed 122 AU). However， this does not cause many qualitative differences.

![](images/3ace572de062180477211a756235b96dfcd8daca3ce4435f11cbcde61b71e552.jpg)  
Figure 2.MHD simulated solar wind radial component along the $X { - } Z$ plane.

# 2.2.Hybrid Galactic Cosmic-Ray Transport Model

Our investigation is based on the Parker's transport equation (Parker 1965)，which contains the solar wind velocity $V$ ，the averaged drift velocity $\left. V _ { D } \right.$ ，a diffusion term $\nabla \cdot \left( K ^ { ( s ) } \cdot \nabla f \right)$ and adiabatic energy changes $\begin{array} { r } { \frac { 1 } { 3 } ( \nabla \cdot \mathbf { V } ) { \partial f } / { \partial \ln p } } \end{array}$ ,with $p$ as the momentum and $f$ as the cosmic-ray distribution function.

$$
\begin{array} { r l r } {  { \frac { \partial f } { \partial t } = - \big ( { \boldsymbol { V } } + \langle { \boldsymbol { V } } _ { D } \rangle \big ) \cdot \nabla f } } \\ & { } & { + \nabla \cdot \Big ( { \boldsymbol { K } } ^ { ( s ) } \cdot \nabla f \Big ) + \frac { 1 } { 3 } ( \nabla \cdot { \boldsymbol { V } } ) \frac { \partial f } { \partial \ln p } . } \end{array}
$$

In the magnetic field coordinate system,the diffusion tensor $K ^ { ( s ) }$ can be written as

$$
K ^ { ( s ) } = \left( \begin{array} { c c c } { { \kappa _ { \parallel } } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { \kappa _ { \perp } } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { \kappa _ { \perp } } } \end{array} \right) .
$$

Following previous work (Luo et al. 2011, 2013),we adopt the following“traditional” forms for these diffusion coefficients:

$$
\begin{array} { r } { \kappa _ { \parallel } = \kappa _ { \parallel 0 } \beta \left( \frac { p } { p _ { 0 } } \right) ^ { 0 . 5 } \frac { B _ { \mathrm { e q } } } { B } , } \\ { \kappa _ { \perp } = \kappa _ { \perp 0 } \beta \left( \frac { p } { p _ { 0 } } \right) ^ { 0 . 5 } \frac { B _ { \mathrm { e q } } } { B } , } \end{array}
$$

where, $\kappa _ { \perp 0 }$ and $\kappa _ { \parallel 0 }$ are both constants, $B$ is the magnetic field magnitude,and $\beta$ is the ratio of particle speed to the speed of light. The $p _ { 0 }$ parameter is a reference momentum (in our case $1 \mathrm { G e V } / c )$ and $B _ { \mathrm { e q } }$ is the magnitude of the heliospheric magnetic field at the Earth (in the heliospheric equator at 1 AU). Using the MHD plasma data,we can calculate the diffusion tensor at any point $X$ for particle with a momentum of $p$ .As for the average drift velocity，we use the classical form (Jokipii & Thomas 1981; Potgieter & Moraal 1985)

$$
\left. V _ { d } \right. = \frac { p \nu } { 3 q } \nabla \times \frac { B } { B ^ { 2 } } .
$$

As for the diffusion coefficients,it depends on the spatial dependence of the magnitude of the heliospheric magnetic field，but also on the direction of this field.To obtain the convection and adiabatic energy change terms is straightforward,since they are related to the plasma speed profile,the latter on the divergence of this profile.

Following Markov's stochastic method (Zhang 1999),the transport equation can be changed to the following time backwardSDEs.

$$
\begin{array} { c } { d X = \Big ( \nabla \cdot K ^ { ( s ) } - V - \big \langle V _ { D } \big \rangle \Big ) d s + \displaystyle \sum _ { \sigma } \alpha _ { \sigma } d W _ { \sigma } ( s ) , } \\ { d p = \displaystyle \frac { 1 } { 3 } p ( \nabla \cdot V ) d s . } \end{array}
$$

In this equation, $d W _ { \sigma } ( s )$ is the Wiener process,and it can be generated in each step using a Gaussian distribution random number. Based on this method, $( \boldsymbol { \cal X } , p )$ constitutes the phase space for the distribution function $f .$ We set $\vert X \vert \leqslant 3 0 0$ AU, the polar angle $\theta \in [ 0 , \pi )$ ，the azimuthal angle $\varphi \in [ 0 , 2 \pi )$ ，and momentum $p \in ( 0 , 1 0 0 0 p _ { 0 } ) ; _ { l }$ $p _ { 0 }$ is the initial momentum for tracing. In order to get the value of $f ( X _ { 0 } , p _ { 0 } )$ at the point $( X _ { 0 } , p _ { 0 } )$ in phase space,we ran a large number of stochastic trajectories from $( X _ { 0 } , p _ { 0 } )$ backward in time until they hit the modulation boundary for the first time.A similar approach was followed by Kopp et al. (2012).

The solution for the modulated cosmic-ray distribution function is

$$
f ( X , p ) = { \Big \langle } f _ { \mathrm { b } } { \big ( } X _ { e } , p _ { e } { \big ) } { \Big \rangle } ,
$$

where $f _ { \mathrm { b } }$ is the boundary condition where the stochastic trajectories hit the boundary for the first time; $\langle \rangle$ denotes the ensemble average.Each stochastic trajectory represents a number of pseudo-particles proportional to the boundary value.

# 3.RESULTS AND DISCUSSION

In the following,we present our simulation results using this hybrid model. Specifically，we first simulate the galactic cosmic-ray spectrum at different radial locations to test and validate our code,then we modify the diffusion coefficients beyond the HP to explore how changing their ratio and their absolute values could affect the cosmic-ray transport ahead and beyond the HP.

# 3.1.Cosmic-Ray Spectra

We first run a series of test simulations for cosmic-ray spectra along the Voyager1directionat differentlocations.The interstellar spectrum is specified at 3OO AU，which isour simulation boundary.We take note that,recently, the very local interstellar spectrum(LIS） forprotonshas been newly determined (Webber et al.2013；Potgieter 2014)，but since the radial gradient of the flux is not affected by the exact LIS spectral shape (Luo et al. 2O13),we still adopt the previously used form in this study:

![](images/1fc6d7440d0a7b8219a207c4a7f776936ddd164fda1b59ab51807b3bdca99420.jpg)  
Figure3.Simulated galactic cosmic-ray spectraalong Voyager $I ^ { ' }$ strajectoryat different radial locations.The unit for flux is arbitrary for Figures 4,6,and 7.

$$
f _ { \mathrm { i s m } } ( p ) \propto \Big ( m _ { 0 } ^ { 2 } c ^ { 2 } + p ^ { 2 } \Big ) ^ { - 1 . 8 } / p ,
$$

where $m _ { 0 }$ is the mass of the proton.

Since our study is mainly about the galactic cosmic-ray radial gradient,its absolute levelis not crucially important. The simulationresultsshown beloware therefore inrelative intensity with arbitrary units of the flux $j$

Figure 3 illustrates these simulation results,which clearly demonstrate galactic cosmic-ray modulation and its basic features from the modulation boundary to the inner helio sphere.Thesimulationswerecomputedbysetting $\dot { \kappa _ { \| 0 } } = 5 0 \times 1 0 ^ { 2 0 } \mathrm { c m } ^ { 2 } \mathrm { s } ^ { - 1 }$ and $\kappa _ { \perp _ { 0 } } = 5 \times \mathsf { i } \mathsf { \bar { 0 } } ^ { 2 0 } \mathrm { c m } ^ { 2 } \mathrm { s } ^ { - 1 }$ in Equation (3)，so that the ratio of the diffusion coefficients is $\kappa _ { \| } / \kappa _ { \perp } = 1 0$ in the whole simulation domain.It should be noted that the spectrum at 155 AU is lower than the interstellar spectrum， becausethisparticular choice of modulation parameters causes modulation in this region,which is beyond the HP.This issue is further addressed below since it is presently debated as mentioned above.Based on current understanding of the ISM（Armstrong et al.1995;Büsching & Potgieter 2OO8; Shalchi etal. 2O1O), the diffusion there is quite different from the situation inside the heliosphere.In the following，we will investigate how the variation of the diffusion beyond the HP affects the cosmic-ray transport there by using our numerical approach.

# 3.2.TheRadial Intensity Variations

Assuggested by Busching & Potgieter(2OO8）and Shalchi et al.(2O1O)，cosmic-ray propagation in the ISM is quite different because of the properties of magnetic turbulence inside the ISM. The perpendicular diffusion coefficient is assumed to be much smaller than the parallel diffusion coefficient in the ISM.Calculations based on interstellar diffusion models by, e.g., Strong et al. (20O7) indicate that the scale of the diffusion coefficient is on the order of $1 0 ^ { 2 8 } \mathrm { c m } ^ { 2 } \mathrm { s } ^ { - 1 }$ This level of diffusion is mostly from particle diffusion along the local magnetic field direction, or $\kappa _ { \parallel }$ 、As for the OHS, the situation is still unclear,but we anticipate that parallel diffusion is also very effective in the OHS.The magnetic field turbulence in the OHS should be quite small as measured by Voyager 1 (Burlaga et al. 2O14）and inferred from the IBEX ribbon (Gamayunov etal.2O1O).A quiet magnetic field warrants large parallel diffusion and small perpendicular diffusion，so we expect $\kappa _ { \| } / \kappa _ { \perp }$ to be significantly large in the OHS.

![](images/b20426ca0530087161e87bbfb6ba379751c1c5bc6d833cdebe70fc42981d384a.jpg)  
Figure 4.Simulated radial flux for $1 0 0 \mathrm { M e V }$ protons.The threecurves ilustrate three differentcases bychangingtheratioofthe paralel diffusion coefcient to the perpendicular diffusion coeficient in the OHS:(A) blue solid curve with $\kappa _ { \| } / \kappa _ { \perp } = 1 0 ^ { 1 0 }$ ，(B） dashed brown curve with $\kappa _ { \| } / \kappa _ { \perp } = 1 0 ^ { \bar { 4 } }$ ,and (C) dotted purple curve with $\kappa _ { \| } / \kappa _ { \perp } = 1 0$ . In the rest of the heliosphere, $\kappa _ { \| } / \kappa _ { \perp } = 1 0$ for all cases,which means that for the“no change”scenario,this ratio remains the same.

We investigate the diffusion coefficients in the OHS by adjusting the ratio of the parallel diffusion coefficient to the perpendicular diffusion,as was done by Strauss et al.(2013), as well as their absolute values. In this numerical approach, we also want to illustrate and understand how cosmic-ray modulation behaves inside of the HP (upstream),closer and across the HP when these type of changes are made.

Figure 4 shows the simulated radial flux for $1 0 0 \mathrm { M e V }$ protons along Voyager $\jmath$ sdirection (polar angle $\theta = 5 6 ^ { \circ }$ azimuthal angle $\phi = 4 ^ { \circ }$ ).The three curves represent three different cases: (A） for the blue solid curve the ratio of $\kappa _ { \| } / \kappa _ { \perp }$ was increased by ${ \mathrm { i } 0 } ^ { 1 0 }$ in the OHS.(B) For the brown dashed curve, the ratio of $\kappa _ { \| } / \kappa _ { \perp }$ was magnified by a factor of $1 0 ^ { 4 }$ in the OHS.(C) For the purple dotted curve,we keep the ratio as a constant in the simulation domain. For these scenarios, excluding the OHS,we set the ratio of $\kappa _ { \| } / \kappa _ { \perp } = 1 0$ everywhere inside the heliosphere,that is,in all upstream regions from the HP.The details of the value of the diffusion coefficients and magnetic field magnitude variations along the Voyager 1 direction in the simulation domain are shown in Figure 5.In the outer heliosphere, $\kappa _ { r r }$ is very close to $\kappa _ { \perp }$ . It increases beyond the HP as we set the $\kappa _ { \| } / \kappa _ { \perp }$ ratio to ${ 1 0 } ^ { 1 0 }$ and it reaches the value of $\kappa _ { \parallel }$ after crossing the HP.The magnetic field magnitude decreases inside the supersonic solar wind region,such as in

Parker's interplanetary magnetic field model.It increases after crossing the termination shock,probably due to the shock compression.Around 13O AU,because of the current sheet crossing，it decreases again，and a“magnetic wall" with magnitude increase can be seen around 15O-18O AU.

From Figure 4, it follows that the corresponding radial flux gradient becomes significantly different after adjusting the ratio of the parallel diffusion coefficient to the perpendicular diffusion coefficient. The higher the ratio,the larger the radial gradient near the HP. As the ratio approaches $1 0 ^ { 1 \widetilde { 0 } }$ like the $\kappa _ { r r }$ curve trend, the radial gradient reaches very large values as the flux jumps to the interstellar value in a very short distance; which is quiet similar to what Voyager $\boldsymbol { { \mathit { 1 } } }$ observed in 2012 August(Webber & McDonald 2O13).In addition,beyond the HP,the simulations demonstrate that the flux and corresponding gradient differ significantly depending on the assumed ratios.If the ratio is unchanged, the modulation simply continues in the OHS as if itis part of the global heliospheric medium.

We also expanded our simulation for protons with different energy.Figure 6 shows the simulated radial flux for 2Oo,100, 80,and ${ 5 0 } \mathrm { M e V }$ ，which is above the anomalous proton energies. We set $\kappa _ { \| } / \kappa _ { \perp } = 1 0 ^ { 1 0 }$ in the OHS for all of these simulations.Similar to case(C）of Figure 4,the radial flux jumps upward near the $\mathrm { H P }$ for all of these energies.For $5 0 \mathrm { M e V }$ , this jump near the HP contributes about $2 5 \%$ of total modulation; for $8 0 \mathrm { M e V }$ ，the jump contributes $17 \%$ of the total modulation; for $1 0 0 \mathrm { M e V }$ ,it contributes $1 5 \%$ and for $2 0 0 \mathrm { M e V }$ protons,only $12 \%$ . Evidently，as the energy increases，the radial flux jump level near the HP became less.As a result, the effect of the ratio variation becomes less and the increasing factor becomes less important near the HP for higher energy protons,but clearly quite significant at lower energies.

We also perform simulations by increasing the value of each individual diffusion coefficient inside the OHS while keeping the ratio the same as used inside of the HP (upstream).In Figure 7，the results are shown together with two scenarios from Figure 4，repeated as references (the black dotted and dashed curves).We multiply both parallel and perpendicular diffusion coefficients bya factor of five in the OHS.The flux (solid blue curve） increases correspondingly，but the value around the HP is still lower than the interstellar value,with some modulation still occurring beyond the HP for this case. As we set the multiplying factor for both diffusion coefficients to 10O,the flux (dash-dotted curve）value around the HP reaches the interstellar value very quickly,with the jump in the flux at the HP not as obvious as before.This simulation shows that either changing the ratio or the value of the individual diffusion coefficients affects galactic cosmic-ray transport near the HP.It appears that the observed jump in the flux at the HP and a case of no modulation beyond the HP,requires a large $\kappa _ { \parallel }$ and $\kappa _ { \| } / \kappa _ { \perp }$ ratio.

![](images/63cd4383a80f28a5fcec276a2b0e642b39788c4db8d59a03a5022229dcbb133f.jpg)  
Fige distance in the simulation domain for cases (A） and (C).

![](images/162eb3a57c3157343c5a1af42f9902efc2a101631d42cd8e7dcc933b9cffebd3.jpg)  
grelooo ecreasing energy across the HP.

It is worth mentioning here that, based on the stochastic method as utilized here,we are able to trace individual pseudoparticle trajectories in the simulation domain.Because the pseudo-particles have the same distribution as real particles entering at the modulation boundary，for a case of little modulation near the HP region,we can approximately consider these pseudo-particles as real particles.Since this requires a lengthy description,we refrain from showing such trajectories in this manuscript but as a next step,we plan to investigate the exiting characteristics of these pseudo-particles,which is where real particles are entering the heliosphere in order to reach the Voyager1 position.Hopefully，this will yield some understanding of the possible physical processes throughout the heliosphere,also beyond the HP,and from where cosmic-ray particles can actually be transported before reaching Voyager 1 and Voyager 2.

![](images/793abbff433e562c61c06d02336da90f4475cf3e68532612019fdaaaec4951e3.jpg)  
Figure 7.Simulated radial flux for $1 0 0 \mathrm { M e V }$ protonsacross the HP.Insteadofchangingtheratioof the difusioncoeficients,the individualdifusioncoeficientsare now changed as indicated in the legend while keeping the ratio the same asused inside (upstream)of the HP.

# 4.SUMMARY

In this paper,by incorporating the output of a global MHD heliospheric model into the galactic cosmic-ray transport model,we constructed a hybrid cosmic-ray transport model. Based on this model,we investigated the behavior and features for cosmic-ray transport near the HP.We presented proton fluxes showing that the radial flux near the HP can already be modulated by the OHS if the diffusion coefficient ratio $\kappa _ { \| } / \kappa _ { \perp }$ is set to a small value.By adjusting this ratio to a very large value inthe OHS,itwas foundthat radial flux exhibitsa sudden upward jump near the HP,which is similar to what Voyager 1 observed in 2O12.Similar features have also been shown by Strauss et al.(2013)，Guo & Florinski (2014)，and Kota & Jokipii (2014)．Modulation beyond the HP seems indeed possible,but since we do not know the exact values for the relevant diffusion coefficients itis difficult to predict how large this modulation may be.We found that the effect of changing the ratio on the jump in flux is closely related to the energy of the protons,the lower the energy,the larger the effect.After adjusting the magnitude of the individual diffusion coefficients, the radial flux also differs significantly.However, this does not give a significant jump of flux at the HP.

We also showed that there is little modulation occurring beyond the HP after multiplying the values of the individual diffusion coefficients by a small factor,while $\kappa _ { \| } / \kappa _ { \perp }$ remains the same as it is inside of the HP,upstream toward the Sun.

However, at thisstage， without published observational cosmic-ray data,it is difficult to figure out if this scenario is plausible.For future work,we plan to investigate this further and to link the Voyager $\boldsymbol { { \mathit { 1 } } }$ observations with a realistic physical environment near the HP,thus constraining the range of relevant parameters. This should contribute to a further understanding of the recent observations by Voyager 1 and what it may imply for Voyager 2.In this study,we used the analytic forms asdone before(Zhang1999） for the perpendicular and parallel diffusion coefficients,in particular, using a simple rigidity dependence,which,if changed, could affect the results in terms of energy dependence shown here.In a next paper,changing this to more complex forms will be investigated.

The work is jointly supported by the National Basic Research Program （973 program） under grant 2012CB825601，the Knowledge Innovation Program of the Chinese Academy of Sciences(KZZD-EW-O1-4)， the National Natural Science Foundation of China(41231068， 41031066， 41074121, 41274192，41074122,and 41304137)，and the Specialized Research Fund for State Key Laboratories. Xi Luo acknowledges the support of the post-doctoral programme of the NorthWest University in South Africa and Scientific Research Foundation forthe Returned Overseas Chinese Scholars,State Education Ministry.M.P.acknowledges the financial support of the South African NRF under the Incentive and Competitive Funding for Rated Researchers, grants 8782O and 68198.M.Z. and N.P. weresupported， inpart, byNASA grants NNX12AB30G，NNX14AJ53G，and NNX14AF41G.MHD simulations were supported through NSF PRAC award OCI114412O and related computer resources from the Blue Waters sustained petascale computing project. N.P.also acknowledges supercomputer time allocations provided on SGI Pleiades by NASA High-end Computing Program award SMD-11-2195 and Cray XT5 Kraken by NSF XSEDE project MCA07S033.M.Z.,

M.P.,and N.P.highly appreciate discussions at the team meeting Heliosheath Processes and Structure of the Heliopause: modeling of Energetic Particles,Cosmic Rays,and Magnetic Fields supported by the International Space Science Institute in Bern, Switzerland. This material is based upon work supported by the National Science Foundation under grant No. CNS O9-23050.

# REFERENCES

Armstrong,J.W.,Rickett,B.J.,& Spangler,S.R.1995,ApJ,443,209   
Borovikov,S.N.,&Pogorelov,N.V.2014,ApJL,783,L16   
Burlaga,L. F.,& Ness,N.F.2014,ApJL, 795,L19   
Burlaga,L.F.,Ness,N.F.,Florinski,V.,& Heerikhuisen,J.2O14,ApJ,   
792, 134   
Burlaga,L.F.,Ness,N.F.,& Stone,E.C.2013,Sci,341,6142   
Bisching,I.,&Potgieter,M.S.2008,AdSpR,42,504   
Decker,R.B.,Krimigis,M. S.,Roelof,E.C.,et al.2012,Natur,489,124   
Fisk,L.A.,& Gloeckler,G.2014,ApJ,789,1   
Gamayunov,K., Zhang,M.,& Rassoul,H.2010,ApJ,725,2251   
Gloeckler,G.,&Fisk,L.A.2014,GeoRL,41,15   
Grygorczuk,J.,Czechowski,A.,& Grzedzielski, S.2014,ApJL,789,L43   
Guo,X.,& Florinski,V.2014,ApJ,793,18   
Gurnett,D.A.,Kurth,W. S.,Burlaga,L.F., et al.2013, Sci,341,6153   
Jokipii,J.R.,& Thomas,B.1981,ApJ,243,1115   
Kopp，A.，Büsching,I.,Strauss,R.D.，& Potgieter,M.S.2012,CoPhC,   
183, 530   
Kota,J.,& Jokipii, J.R.2014,ApJ,782,24

Krimigis,S.M.,Decker,R.B.,Roelof,E.C.,et al.2013,Sci,341,6142   
Luo,X.,Zhang,M.,Rassoul,K.H.,& Pogorelov,N.V.2011,ApJ,730,13   
Luo,X.,Zhang,M.,Rassoul,K.H.,Pogorelov,N.V.,& Heerikhuisen,J. 2013,ApJ, 764, 85   
Parker,E.N.1965,P&SS,13,9   
Pogorelov,N.V.,Borovikov,S.N., Zank,G.P.,et al.2012,ApJL,750,L4   
Pogorelov,N.V.,Borovikov,S.N.,Zank,G.P.,& Ogino,T.2Oo9a,ApJ, 696,1478   
Pogorelov,N.V.,Heerikhuisen,J.,& Zank,G.P.2008,ApJL,675,L41   
Pogorelov,N.V.,Heerikhuisen,J.,Zank,G.P.,& Borovikov,S.N.2009b, SSRv, 143, 31   
Pogorelov,N.V.,Suess,S.T.,Borovikov,S.N.,et al.2013,ApJ,772,2   
Pogorelov,N.V.,Zank,G.P.,& Ogino,T.2006,ApJ,644,1299   
Potgieter,M. S.2014,BrJPh,44,581   
Potgieter,M. S.,& Moraal,H.1985,ApJ,294,425   
Scherer,K.,Fichtner,H.,Strauss,R.D.,et al.2011,ApJ,735,128   
Shalchi,A.，Büsching，I.，Lazarian，A.，& Schlickeiser，R．2O1O，ApJ, 725,2117   
Stone,E.C.,Cummings,A.C.,McDonald,F.B.,et al.2013,Sci,341,6142   
Strauss,R.D.,Potgieter,M.S.,Ferreira,S.E.S.,Fichtner,H.,& Scherer,K. 2013,ApJL, 765,L18   
Strong,A.W.,Moskalenko,I.V.,&Ptuskin,V.S.20O7,ARNPS,57,285   
Strumik，M.，Grzedzielskil，S.，Czechowskil，A.，Macek，W.M.，& Ratkiewicz,R.2014, ApJL, 782,L7   
Webber,W.R.,Higbie,P.R.,&McDonald,F.B.2013,arXiv:1308.1895   
Webber,W.R.,&McDonald,F.B.2013,GeoRL,40,1665   
Zank,G.P.,& Pauls,H.L 1996, SSRv, 78,95   
Zhang,M.1999,ApJ, 513,409