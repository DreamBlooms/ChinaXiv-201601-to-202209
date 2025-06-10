# SIMULATIONS OF A GRADUAL SOLAR ENERGETIC PARTICLE EVENT OBSERVED BY HELIOS1, HELIOS 2, AND IMP 8

Gang Qin1 and Yang Wangl

gqin@spaceweather.ac.cn; ywang@spaceweather.ac.cn

Received accepted

# ABSTRACT

In this work,a gradual solar energetic particle (SEP) event observed by multispacecraft has been simulated. The time profiles of SEP fluxes accelerated by an interplanetary shock in the three-dimensional interplanetary space are obtained by solving numerically the Fokker-Planck focused transport equation. The interplanetary shock is modeled as a moving source of energetic particles. By fitting the 1979/03/01 SEP fluxes observed by Helios 1, Helios 2,and IMP 8 with our simulations,we obtain the best parameters for the shock acceleration efficiency model. And we also find that the particle perpendicular diffusion coefficient with the level of $\sim 1 \% - 3 \%$ of parallel diffusion coefficient at 1 AU should be included. The reservoir phenomenon is reproduced in the simulations, and the longitudinal gradient of SEP fluxes in the decay phase, which is observed by three spacecraft at different locations,is more sensitive to the shock acceleration efficiency parameters than that is to the perpendicular diffusion coefficient.

Subject headings: Sun: activity - Sun: coronal mass ejections (CMEs) - Sun: particle emission

# 1.INTRODUCTION

There are two categories of solar energetic particle (SEP) events: impulsive events and gradual events. The impulsive events are small,last for hours,are rich in electrons, $^ 3 \mathrm { H e }$ and heavy ions,have relatively high charge states,and are produced by solar flares. In contrast, gradual events are large,last for days,are electron poor, have relatively low charge states,and are related to the shocks driven by interplanetary coronal mass ejections (ICMEs). Some large ICME driven shocks can cover a large range of solar longitudes and latitudes in the interplanetary space, and the observers located at different locations can be connected to different parts of the shocks by interplanetary magnetic field (IMF). Therefore, multi-spacecraft observations by, e.g., Helios 1 and 2, usually show a large difference of SEP time profiles at different longitudes (Reames et al. 1996,1997). In addition,in some SEP events,both of solar flare and shock can exist in the same event. Therefore, there are also shock-fare-mixed SEP events which can be identified by abundance ratio and charge state of heavier ions.

Multi-spacecraft observation data provide essential information to understand the processes of particle acceleration and transport in the heliosphere. Multi-spacecraft observations in the ecliptic plane, e.g., by Helios 1 and 2, or at diferent latitudes and radial distances, e.g., by $A C E$ and Ulysses, usually show two interesting phenomena in some gradual events. For the first one, SEP events could be observed by multi-spacecraft with a very wide spatial distribution that could be wider than the size of the source (e.g., Wiedenbeck et al. 2O13). This phenomenon can be explained in part as a result of the effect of particle perpendicular diffusion,and has been investigated in detail with simulations (Zhang et al. 20O9; He et al. 2011; Dresing et al. 2012; Wang et al. 2012; Qin et al. 2013; Droge et al. 2014; G6mez-Herrero et al. 2015; Wang & Qin 2015).For the second one, the SEP fluxes observed by widely separated multi-spacecraft usually show similar intensities within a small $\sim 2 - 3$ factor in different positions (Reames et al. 1997; McKibben et al. 2001; Lario et al. 2003; Tan et al. 2009; Zhang et al. 2009; Qin et al.

2013;Wang & Qin 2015). McKibben (1972) discovered this phenomenon, and Roelof et al. (1992) named it as “reservoir". Recently, Wang et al. (2Ol2) use a numerical code (denoted as Shock Particle Transport Code, SPTC) considering shock as a moving SEP source by adopting the model of Kallenrode (1997). Qin et al.(2013) reproduced the reservoir phenomenon with different shock acceleration efficiency and perpendicular diffusion. In addition,Wang & Qin (2015) investigated the spatial and temporal invariance in the spectra of gradual SEP events. In their simulations,SPTC is used with the IMF set as Parker field model,and the disturbance of the IMF caused by ICME is ignored. They found that shock acceleration efficiency, parallel diffusion,adiabatic cooling,and perpendicular diffusion are four important factors in forming the reservoir phenomenon,and the first three factors are the main factors with the last factor being a secondary one. The peaks of SEP fluxes are mainly controlled by shock acceleration efficiency and parallel diffusion. And the fluxes decay in the similar ratio due to the effect of adiabatic cooling. Furthermore, because of the efect of perpendicular diffusion,the longitudinal gradient in the SEP fluxes,which is observed by spacecraft located at different locations, is further reduced. Observationally,the four factors change significantly in different SEP events (Kallenrode 1996, 1997), so that only in the gradual SEP events when the values of the controlling effect parameters are appropriate can the reservoir phenomenon be formed.

Generally, SEP acceleration by shocks are calculated in two major approaches: in the first approach, SEPs are injected at the shock with an assumed injection strength (Heras et al.1992, 1995; Kallenrode & Wibberenz 1997; Lario et al. 1998; Kallenrode 2001; Wang et al. 2012; Qin et al. 2O13), while in the second approach the acceleration of SEPs by shocks are included (Lee 1983; Gordon et al. 1999; Zuo et al. 2011; Zuo et al. 2013). Each approach has its own advantages, the first one can provide a reasonable description of the SEP fluxes in gradual events by focusing on the transport of energetic particles without the thorough knowledge of the details of shock acceleration, while the second one can help us to better understand diffusive shock acceleration by including more physics details. There are also some studies attempting to combine the advantages of the two approaches. The SEPs acceleration and transport processes are included in these studies ( $\mathbf { N g }$ et al. 1999; Zank et al. 2000; Li et al. 2003; Rice et al. 2003).

Because the calculation of SEP flux needs a precise mechanism for particle's injection into the diffusive shock acceleration, which is currently not available, we adopt the first approach to inject SEPs at the shock with an assumed injection strength, so that we could focus on interplanetary shock accelerated particles’ transport (Wang et al. 2O12; Qin et al. 2013; Wang & Qin 2015). In this paper, as a continuation of our previous research, we further study the the shock acceleration effciency and SEPs transport in a gradual SEP event by comparing our simulations with multi-spacecraft observations. We describe the SEP transport model and the shock model in section 2. We show the observation results in section 3. We show the shock geometry and the effect of perpendicular diffusion in Section 4. We show the simulation results and their comparison with multi-spacecraft observations in Section 5. We summary our results in Section 6.

# 2. MODEL

In this work we follow previous research (e.g., Qin et al. 2006,2011; Qin et al. 2013; Zhang et al. 2009; Droge et al. 2010; Zuo et al. 2011; Zuo et al. 2013; Wang et al. 2012; Wang et al. 2O14), to model the transport of SEPs. One can write a three-dimensional focused transport equation as (Skilling 1971; Schlickeiser 2002; Qin et al. 2006; Zhang et al. 2009)

$$
\begin{array} { r } { \displaystyle \frac { \partial f } { \partial t } = \nabla \cdot ( \kappa _ { \perp } \cdot \nabla f ) - \left( \nu \mu \hat { \boldsymbol b } + V ^ { s w } \right) \cdot \nabla f + \frac { \partial } { \partial \mu } \left( D _ { \mu \mu } \frac { \partial f } { \partial \mu } \right) } \\ { + p \left[ \frac { 1 - \mu ^ { 2 } } { 2 } \left( \nabla \cdot V ^ { s w } - \hat { \boldsymbol b } \hat { \boldsymbol b } : \nabla V ^ { s w } \right) + \mu ^ { 2 } \hat { \boldsymbol b } \hat { \boldsymbol b } : \nabla V ^ { s w } \right] \frac { \partial f } { \partial p } } \\ { - \frac { 1 - \mu ^ { 2 } } { 2 } \left[ - \frac { \nu } { L } + \mu \left( \nabla \cdot V ^ { s w } - 3 \hat { \boldsymbol b } \hat { \boldsymbol b } : \nabla V ^ { s w } \right) \right] \frac { \partial f } { \partial \mu } , } \end{array}
$$

where $f ( \boldsymbol { x } , \mu , p , t )$ is the distribution function averaged over gyrophase, $t$ is the time, $\boldsymbol { x }$ is the position in a non-rotating heliographic coordinate system, $p , \nu _ { : }$ and $\mu$ are the particle momentum, speed, and pitch-angle cosine, respectively, in the solar wind frame, $\hat { \pmb { b } }$ is a unit vector along the local magnetic feld, $V ^ { s w } = V ^ { s w } \hat { \pmb { r } }$ is the solar wind velocity,andthe magnetic focusing length $L$ （204 is obtained from the divergence of the IMF background strength $B _ { 0 }$ ,i.e., $L = \left( \stackrel { \wedge } { \pmb { b } } \cdot \nabla l n B _ { 0 } \right) ^ { - 1 }$ . Here, we use the Parker field model for the IMF. The equation (1) includes almost allimportant particle transport effects, such as particle streaming along the field line, adiabatic cooling in the expanding solar wind, magnetic focusing in the diverging IMF, and the parallel and perpendicular diffusion coefficients.

We define a pitch angle diffusion coefficient following (Beeck & Wibberenz 1986; Qin et al. 2005; Qin et al. 2006)

$$
D _ { \mu \mu } ( \mu ) = D _ { 0 } \nu ( R _ { L } k _ { m i n } ) ^ { s - 2 } \left( \mu ^ { s - 1 } + h \right) \left( 1 - \mu ^ { 2 } \right) ,
$$

where the constant $D _ { 0 }$ is adopted from Teufel & Schlickeiser (2003)

$$
D _ { 0 } = \bigg ( \frac { \delta B _ { s l a b } } { B _ { 0 } } \bigg ) ^ { 2 } \frac { \pi ( s - 1 ) } { 4 s } k _ { \mathrm { m i n } } ,
$$

here $\delta B _ { s l a b } / B _ { 0 }$ is the magnetic turbulence level of slab component, $R _ { L } = p c / \left( \left| q \right| B _ { 0 } \right)$ is the maximum particle Larmor radius, $q$ is the particle charge, $l _ { s l a b }$ is the slab turbulence correlation length, $k _ { \mathrm { m i n } } = 1 / l _ { s l a b }$ is the lower limit of wave number of the inertial range in the slab turbulence power spectrum, and $s = 5 / 3$ is the Kolmogorov spectral index of the magnetic field turbulence in the inertial range. The constant $h$ arises from the non-linear effect of magnetic turbulence on the pitch angle diffusion at $\mu = 0$ (Qin & Shalchi 2009,2014). In the following simulations,we set （204号 $h = 0 . 0 1$ ,and $k _ { \mathrm { m i n } } = 3 2 \mathrm { \ A U ^ { - 1 } }$

Following Jokipii (1966), Hasselmann (1968),and Earl (1974),the relationship between $D _ { \mu \mu }$ and parallel mean free path (MFP) $\lambda _ { \parallel }$ is written as

$$
\lambda _ { \parallel } = \frac { 3 \upsilon } { 8 } \int _ { - 1 } ^ { + 1 } \frac { ( 1 - \mu ^ { 2 } ) ^ { 2 } } { D _ { \mu \mu } } d \mu .
$$

In addition, the parallel diffusion coefficient $\kappa _ { \parallel }$ is related to $\lambda _ { \parallel }$ by $\kappa _ { \parallel } = \nu \lambda _ { \parallel } / 3$

The perpendicular diffusion coefficient is set by using the nonlinear guiding center theory (Matthaeus et al. 2O03) with the following analytical approximation (Shalchi et al. 2004, 2010)

$$
\kappa _ { \perp } = \frac { 1 } { 3 } \nu \Bigg [ \left( \frac { \delta B _ { 2 D } } { B _ { 0 } } \right) ^ { 2 } \sqrt { 3 \pi } \frac { s - 1 } { 2 s } \frac { \Gamma \left( \frac { s } { 2 } + 1 \right) } { \Gamma \left( \frac { s } { 2 } + \frac { 1 } { 2 } \right) } l _ { 2 D } \Bigg ] ^ { 2 / 3 } \lambda _ { \parallel } ^ { 1 / 3 } \left( { \bf I } - \hat { \pmb { b } } \hat { \pmb { b } } \right)
$$

where $B _ { 2 D } / B _ { 0 }$ are the turbulence level of 2D component, and $l _ { 2 D }$ is the correlation length. I is the gamma function. I is a unit tensor. In our simulations, $l _ { 2 D }$ is set to $3 . 1 \times 1 0 ^ { - 3 }$ AU, $( \delta B _ { 2 D } ) ^ { 2 } / ( \delta B _ { s l a b } ) ^ { 2 } = 4$ ,and $s = 5 / 3$ . As a result, the values of parallel and perpendicular diffusion coefficients can be altered bychanging the magnetic turbulence level $\delta B / B _ { 0 } \equiv \sqrt { \delta B _ { s l a b } ^ { 2 } + \delta B _ { 2 D } ^ { 2 } } / B _ { 0 } .$ （204号

The particle injection into the shock at position $( r , \theta , \varphi )$ and time $t$ with momentum $p$ is specified by boundary values from Kallenrode & Wibberenz (1997); Kallenrode (2001); Wang et al. (2012), and Qin et al. (2013)

$$
\begin{array} { r c l } { f _ { b } ( r , \theta , \varphi , p , t ) } & { = } & { a \cdot \delta ( r - \upsilon _ { s } t ) \cdot S ( r , \theta , \varphi ) \cdot p ^ { \gamma } \cdot \xi ( \theta , \varphi ) } \\ { S ( r , \theta , \varphi ) } & { = } & { \displaystyle \left( \frac { r } { r _ { c } } \right) ^ { - \alpha } \exp \left[ - \frac { | \phi ( \theta , \varphi ) | } { \phi _ { c } } \right] } \\ & & { \displaystyle \xi ( \theta , \varphi ) } & { = } & { \left\{ \begin{array} { l l } { 1 } & { \mathrm { ~ i f ~ } | \phi ( \theta , \varphi ) | \le \phi _ { s } } \\ { 0 } & { \mathrm { ~ o t h e r w i s e } , } \end{array} \right. } \end{array}
$$

where $r$ is the solar radial distance, $\upsilon _ { s }$ is the shock speed, $\begin{array} { r } { \psi _ { s } t = r _ { b 0 } + n \cdot \Delta r } \end{array}$ with $n = 0 , 1 , 2 , \cdots , n _ { 0 }$ （204号 and $\Delta r$ being space interval between two ‘fresh’ injections, $r _ { b 0 }$ is the inner boundary, $S$ is the shock acceleration efficiency which specifies the particles ejection and changes with a power law in radial distance and is exponential towards the flank of shock, $r _ { c }$ is the radial normalization parameter, $\alpha$ and $\phi _ { c }$ are the shock acceleration efficiency parameters, $\xi$ determines the spatial scale of shock front, $\phi$ is the angle between the center of shock and the point at the shock front where the particles injected, and $\phi _ { s }$ is the half width of the shock. $\gamma$ is the energy spectral index of SEP source.

In order to numerically solve the transport equation (1),a time-backward Markov stochastic process method is used by following Zhang (1999), see also Qin et al. (2006) for details of the application of the methods to study SEPs.Here,we denote the numerical code to calculate the propagation of energetic particles, which treats the CME driven shock as a moving particle source, as Shock Particle Transport Code, i.e., SPTC.

# 3. OBSERVATIONS

The SEP data from the Helios University of Kiel particle instrument provides proton and heavier nuclei with energy range between 1.3 and several hundred MeV/nuc, and electrons of $0 . 3 - 0 . 8 { \bf M e V } .$ The SEP data from the IMP 8 Goddard Medium Energy (GME) Experiment provides an energy range of $0 . 5 - 4 5 0 \mathbf { M e V }$ proton and 2 - 45O MeV/nuc heavier nuclei, and relativistic electrons. During the time period March 1-11,1979,a gradual SEP event was observed by Helios 1 and 2,and IMP 8,which were located near 1 AU ecliptic, but at different longitudes. On March 1,1979, the radial distances of Helios 1, Helios 2,and IMP 8 on March 1,1979 are 0.95 AU, 0.93 AU,and 0.99 AU, respectively. And the Helios 1, Helios 2, and IMP 8 were located at $1 7 ^ { \circ } , 5 7 ^ { \circ }$ ,and $8 4 ^ { \circ }$ in the heliographic inertial coordinate, respectively. Figures 1,2,and 3 show the time series of SEP fluxes, interplanetary magnetic field, and solar wind measurements from the Helios 1, Helios 2,and IMP 8,respectively. In each of the three figures, from top to bottom, the observation data are for SEP fluxes, magnetic field strength $| \mathbf { B } |$ ，polar and azimuthal field angles $\theta$ and $\phi$ in the Selenocentric Solar Ecliptic (SSE) coordinate for Helios 1 and 2 but in the Geocentric Solar Ecliptic (GSE) coordinate for IMP 8, plasma density $N$ ，plasma temperature $T$ , and bulk solar wind speed $V$ . The vertical line indicates a interplanetary shock passage. From Figure 1 we find that during the period March 3-5 Helios 1 observed both a shock and an ICME event characterized by increases in the solar wind speed, density, temperature,and the rotation of the azimuthal field angle $\phi$ . From Figure 2 we find that

Helios 2 only observed a shock without ICME. The ICME driven shock was detected by the Helios 1 and Helios 2 during March 3. If the same shock was detected by IMP 8,it should be detected nearly in the same time interval. However, during March 3, we find that IMP 8 observed neither a shock nor an ICME in Figure 3. This SEP event is also investigated by Lario et al. (2006) and Reames (2010). In these two studies, they also found that IMP 8 did not observe a shock.

Just before the onset of the March 1-11, 1979 gradual SEP event at 1 AU,a solar fare is observed (Kallenrode et al.1992). The flare is located at S23E58,and the time of the maximum of soft X-ray is at 10:19 on March 1. If we assume the time of the maximum of soft X-ray to be the moment of formation of the CME driven shock, the average speed of the shock can be obtained, i.e., 0.57 AU/day and O.47 AU/day for the average speed of shocks detected by Helios 1 and 2, respectively. In this work, we further take an average of O.57 AU/day and O.47 AU/day, and set the shock speed to be a constant 0.52 AU/day.

# 4.SHOCK'S GEOMETRY AND PERPENDICULARDIFFUSION

In fact, the geometry of an interplanetary shock would be very complicate. For simplicity, we do not include shock angle (obliquity) in our model, but only use a cone to model the shock's geometry in our simulations.The shock nose (the center of the cone) is located in ecliptic,and the longitude of the shock nose is set as the same as that of solar flare. In this event, the shock nose points to E58. Since the locations of spacecraft are known, then we can determine the relative positions between the shock nose and the spacecraft. In this case, the Helios1, Helios 2, and IMP 8 are $9 ^ { \circ }$ east, $3 1 ^ { \circ }$ west, and $5 8 ^ { \circ }$ west of the shock nose,respectively. Although the direction of the shock nose is a hypothesis, we can use the spacecraft's in-situ observation to identify if the hypothesis is reasonable. In this SEP event, Helios 1 detected the shock and ICME, but IMP 8 didn't. These observations implied that the Helios 1 is located the nearest to the shock nose,and IMP 8 is the farthest. Therefore, the locations of spacecraft in our model are consistent with the in-situ observations of spacecraft. Furthermore, the solid angle of shock front is set as $3 5 ^ { \circ }$ ，which agrees with the fact that both Helios 1 and Helios 2 detected shock,but IMP 8 did not. According to the observations of Helios 1, there is no significant difference in the SEP fluxes when the spacecraft is inside and outside the ICME.As a result, the disturbances of IMF caused by ICME could be ignored, and the IMF is set as Parker spiral in our simulations.

Based on our shock model and the observations of Helios 1, Helios 2,and IMP 8,we plot a cartoon for illustrating the cross-section of the shock and the locations of three spacecraft in Figure 4.In this figure,the shock front is indicated by the dashed arc line,and the shock nose is indicated by the dashed-arrow radial line passing through the center of the shock. The big solid circles indicate the locations of the three observers, Helios 1 and 2,and IMP 8,and the small ones indicate the protons of SEPs. As the shock propagates outward, the shock front is connected with the Helios 1 by the IMF first, then with the Helios 2,at last with the IMP 8.Note that the spacecraft's field line is not connected to the shock front all the time. For example,the field line of the IMP 8 is not connected to the shock at the beginning, then as the shock front moves to a larger radial distance than that of the IMP 8, the field line becomes connected to the shock. Eventually, the observer will be disconnected from the shock as the shock continues to propagate outward.

In Figure 4 (a),we assume that SEPs propagate in the interplanetary space without perpendicular diffusion. In this case, the SEPs can only propagate along the IMF. The particles can be detected at the onset time when the spacecraft's IMF is connected to the shock front. In Figure 4 (b), however, we assume that SEPs propagate in the interplanetary space with perpendicular diffusion. In this case, SEPs can cross magnetic field lines. The particles can be detected before the spacecraft is connected to the shock by field lines,and they can more easily spread in the interplanetary space. In March 1,1979 SEP event,the onset time of SEP fluxes observed by three spacecraft was very close. Therefore, in order to reproduce the observations with our model, perpendicular diffusion must be included in the following simulations.

# 5. THE RESULTS OF SEP SIMULATIONS AND THEIR COMPARISONS WITH OBSERVATIONS

The parameters used in the simulations are listed in tables 1 and 2. The parameters in table 1 are the same in all of following simulations, but the ones in table 2 are different in individual simulations.In the observations, the speed of solar wind is always changing with time, but the variance in the speed would not change our main conclusions significantly. As result, we used a constant speed of $4 0 0 \mathrm { k m / s }$ in our simulations.

# 5.1. Effect of Perpendicular Diffusion on SEP Flux

Figure 5 shows the simulation and observation results of the time profiles of SEP fluxes. The black and red lines indicate the observations of $3 - 6 \mathrm { M e V }$ protons and the simulations of $5 \mathrm { M e V }$ protons, respectively. And the solid, dotted,and dashed lines are corresponding to the observations of Helios 1, Helios 2,and IMP 8, respectively. The vertical lines indicate the moment when the spacecraft's field lines are connected to the shock. Due to the different locations of the three spacecraft and the width of the shock, the spacecraft's field lines are connected to the shock front at different time.The Helios 1 is connected to the shock by IMF first, then is the Helios 2,at last is the IMP 8. The simulations in Figure 5 (a) are noted as Case 1. Note that the parameters for different cases are shown in Table 2. The onset time when the shock is connected to IMP 8 by IMF is nearly two days later than that to Helios 1. With perpendicular diffusion, particles can cross magnetic field lines in the interplanetary space,so they can be detected before the spacecraft's magnetic field line is connected to the shock. As a result, the onset time of SEP fluxes in the simulations is very close because of the effect of perpendicular diffusion. As we can see,the simulations roughly agree with the observations in Figure 5 (a). The simulations in Figure 5 (b) are noted as Case 2. Figure 5 (b) is the same as Figure 5 (a) except that the ratio of perpendicular diffusion coefficient to parallel one is larger. In Figure 5 (b), SEP flux observed by Helios 1 is very close to that in Figures 5 (a). However, during the early stage of flux rising phase, SEP fluxes observed by Helios 2 and IMP 8 in Figure 5 (b) are slightly larger than that in Figure 5 (a). This is because all particles arrive at Helios 2 and IMP 8 by crossing field lines before the observers field lines are connected to the shock front. Due to the effect of stronger perpendicular diffusion in Figure 5 (b) than that in Figure 5 (a), during the decay phases,the spatial gradients of SEP fluxes in Figure 5 (b) are slightly smaller than that in Figure 5 (a). In this SEP event, the effect of perpendicular diffusion is very important when the spacecraft's feld line is disconnected from the shock front,and it also helps to reduce the spatial gradient in the decay phase of SEP fluxes.

# 5.2. Effect of Source Injection Profile on SEP Flux

Figures 6 (a) and (b) are the same as Figure 5 (a) but with different shock acceleration efficiency parameters,and the simulations in Figures 6 (a) and (b) are noted as Case 3 and Case 4, respectively. In simulations of Figure 6 (a), the shock acceleration parameter $\alpha$ is set to 2.5. Comparing with the simulations in Figure 5 (a),the shock acceleration efficiency decreases more slowly with radial distance,and the longitudinal gradient in the simulation fluxes is larger. In the simulations of Figure 6 (b), the shock acceleration parameter $\phi _ { c }$ is set to $5 ^ { \circ }$ . Comparing with the simulations in Figure 5 (a), the shock acceleration efficiency decreases more quickly toward the shock flank,and the simulation fluxes increase more quickly during the rising phase.The peak intensity of SEP fluxes are mainly determined by shock acceleration efficiency,and the gradient of SEP fluxes in the decay phase is more sensitive to the shock acceleration efficiency parameters than the perpendicular diffusion coefficient. In this SEP event, at the peak time of flux for Helios 2 (IMP 8),the flux for Helios 2 (IMP 8) was similar to that for Helios 1 which had been in decay phase. The reservoir phenomenon is formed in the decay phase in the SEP fluxes.

# 5.3. Effect of Adiabatic Cooling on SEP Flux

Figures 7 is the same as Figure 5 (a) but with different injection spectrum. The simulations in Figure 7 is noted as Case 5. When propagating in the heliosphere, SEPs would lose energy because of the effect of adiabatic cooling,so that the SEPs with the same energy observed by spacecraft later generally originate with higher energies at the source. Because the source has a negative energy spectral index $\gamma$ ,the flux decreases more quickly with a smaller $\gamma$ The fluxes observed by Helios 1,Helios 2,and IMP 8 decay as a similar ratio due to the effect of adiabatic cooling. In the simulations of Figure 7, the injection spectral index $\gamma$ is set to $- 8 . 5$ . Comparing with the simulations in Figure 5 (a), the simulation fluxes decrease more quickly,and the decay ratios of SEP fluxes are mainly determined by the efect of adiabatic cooling and the energy spectral index $\gamma$ .

# 5.4. Higher Energetic Particles

In Figures 8, the black and red lines indicate the observations of $3 2  { - } 4 5  { \mathbf { M e V } }$ protons and the simulations of $3 5 \mathbf { M e V }$ protons, respectively. The simulations in Figure 8 is noted as Case 6. In simulations of Figure 8, the shock acceleration parameter $\alpha$ is set to 4. Comparing with the simulations in Figure 5 (a), the peak time of simulation fluxes in Figures 8 comes earlier. This means that source acceleration eficiency decreases with radial distance faster at higher energy channel.

# 6.DISCUSSION AND CONCLUSIONS

In this work, we study a gradual SEP event which was observed by Helios 1 and 2,and IMP 8. The event studied in this paper began on March 1, 1979,and lasted nearly eight days. By solving a three-dimensional focused transport equation, the fluxes observed by the three spacecraft are calculated. The transport equation we use in this work includes many important particle transport effects,such as particle streaming along the field line, solar wind convection,adiabatic cooling, magnetic focusing,and the diffusion coefficients parallel and perpendicular to the IMF. By comparing the simulations and the observations, we get the shock efficient parameters and diffusion coefficients to get the best fitting. The following are our major findings.

The effect of perpendicular diffusion is very important when the spacecraft's field line is disconnected with the shock front. In 1979/O3/01 SEP event, the in-situ observation shows that an ICME is detected by Helios 1, but not by Helios 2 or IMP 8 which are in the west of Helios 1. Therefore, Helios 1 is located near the center of shock front but Helios 2 and IMP 8 are located in the west flank of the shock,if it is assumed that the ICME is located behind the center of the shock. Furthermore,the interplanetary shock is only observed by Helios 1 and 2, but not by IMP 8. In the case without perpendicular diffusion, the IMP 8 can not detect any SEP when the radial distance of the shock is smaler than 1 AU.However,according to the observations of IMP 8, the particles can be detected by IMP 8 before IMP 8's field line is connected to the shock front. In order to reproduce the observations of $3 - 6 \mathrm { M e V }$ and $3 2 - 4 5 \mathrm { \ : M e V }$ protons in the simulations, the perpendicular diffusion coefficient with the level of about $1 \% - 3 \%$ of parallel one at 1 AU should be included,

The peaks of fluxes are mainly determined by the shock acceleration effciency, and the decay ratios of SEP fluxes are mainly due to the effect of adiabatic cooling and the energy spectral index.Due to the effect of adiabatic cooling,the fluxes observed by Helios 1,Helios 2,and IMP 8 decay as a similar ratio. The shock acceleration efficiency $S$ is assumed as $r ^ { - \alpha } \exp \left( - \left| \phi \right| / \phi _ { c } \right)$ in the simulations.The shock acceleration efficiency is weaker in the flank of the shock front than that in the center, and decreases as the solar radial distance $r$ increases.For 3 -6 MeV protons, by comparing the simulations and the 1979/03/01 SEP event observed by Helios 1, Helios 2, and IMP 8, we find that $\alpha$ is set to 3, $\phi _ { c }$ is set to $1 0 ^ { \circ }$ , and the energy spectral index y is set to -6.5.We also calculated the SEP fluxes in the cases of different model parameters which are listed in the Table 2. For $3 2  { - } 4 5  { \mathbf { M e V } }$ protons, we find that $\alpha$ is set to about 4 in the Case 6 of Table 2. Comparing with the simulations in the Case 1 of $3 - 6 \mathbf { M e V }$ protons, the $\alpha$ is larger in the case of $3 2  { - } 4 5  { \mathbf { M e V } }$ protons, which means the source acceleration efficiency decreases with radial distance faster at higher energy channel.

The longitudinal gradient of SEP fluxes in the decay phase observed by different spacecraft is more sensitive to the shock acceleration efficiency parameters than the perpendicular diffusion coefficient. In 1979/03/O1 event, at the peak time of flux for Helios 2 (IMP 8),the flux for Helios 2 (IMP 8) was similar to that for Helios 1 which was in decay phase,and the reservoir phenomenon was formed in the decay phase of SEP fluxes. In this event, the reservoir phenomenon is also reproduced in the simulations.However, in some other SEP events,at the peak time of flux for Helios 2 (IMP 8),the flux for Helios 2 (IMP 8) was significantly different than that for Helios 1 which was in decay phase. The reservoir phenomenon can not be formed in the decay phase of SEP fluxes with normal diffusion coefficients ( $\kappa _ { \perp } / \kappa _ { \parallel }$ is a few percent).

The IMF is set to the Parker field model in our simulations,and the disturbance of the IMF caused by ICME is ignored. However, according to the observations of Helios 1 in this event, there is no obvious difference in the SEP fluxes after the spacecraft enter the ICME comparing to the fluxes detected by Helios 1 when it is out of ICME. As a result, we assume that the disturbance of the IMF would not change the main results of our simulations. Furthermore, our model can not be used to study the shock-flare-mixing SEP events. In the future work, we plan to include the particle source combined with shock and flare to model the shock-fare-mixed

SEP events. And we also intend to include a realistic three-dimensional ICME shock with the disturbance of IMF caused by ICME,so that the SEP acceleration and transport in the heliosphere can be investigated more precisely.

The authors thank the anonymous referee for valuable comments. We are partly supported by grants NNSFC 41374177, NNSFC 41125016, and NNSFC 41304135, the CMA grant GYHY2011O6011,and the Specialized Research Fund for State Key Laboratories of China. The computations were performed by Numerical Forecast Modeling R&D and VR System of State Key Laboratory of Space Weather and Special HPC work stand of Chinese Meridian Project. We are grateful to the plasma and SEP data provided by the Helios and IMP 8 teams.

#

REFERENCES   
Beeck,J.,&Wibberenz,G.1986,ApJ,311,437   
Dresing,N., Gómez-Herrero,R., Klassen, A., Heber, B., Kartavykh, Y.,& Droge,W. 2012,   
Sol. Phys., 281, 281   
Droge,W., Kartavykh, Y. Y., Dresing,N., Heber, B.,& Klassen, A. 2O14, Journal of Geophysical   
Research (Space Physics), 119, 6074   
Drge, W., Kartavykh, Y. Y., Klecker, B., & Kovaltsov, G. A. 201O, ApJ, 709, 912   
Earl, J. 1974, The Astrophysical Journal, 193, 231   
G6mez-Herrero,R., et al. 2015,ApJ, 799, 55   
Gordon,B.E.,Lee,M. A., Mobius,E.,& Trattner, K.J.1999,J. Geophys. Res.,104,28263   
Hasselmann, K. 1968, Z. Geophys., 34, 353   
He, H.-Q., Qin, G., & Zhang, M. 2011, The Astrophysical Journal, 734, 74   
Heras,A. M., Sanahuja,B., Lario, D., Smith,Z. K., Detman, T.,& Dryer, M.1995, ApJ, 445, 497   
Heras, A. M., Sanahuja, B., Smith, Z. K., Detman, T.,& Dryer, M.1992, ApJ, 391, 359   
Jokipii, J. R. 1966, ApJ, 146, 480   
Kallenrode, M. 1996,J. Geophys. Res., 101, 24393   
-.1997,J.Geophys.Res.,102,22347   
-. 2001,J. Geophys.Res.,106,24989   
Kallenrode,M.,& Wibberenz, G.1997, J. Geophys. Res., 102,22311

Kallenrode,M.-B., Cliver, E.W.,& Wibberenz, G.1992,ApJ,391, 370   
Lario,D., Kallenrode,M.-B., Decker, R.B., Roelof, E. C., Krimigis, S.M., Aran, A.,& Sanahuja, B. 2006, ApJ, 653, 1531   
Lario,D., Roelof, E. C., Decker, R.B.,& Reisenfeld,D.B. 2O03, Advances in Space Research, 32, 579   
Lario, D., Sanahuja, B.,& Heras, A. M.1998,ApJ, 509, 415   
Lee,M. A. 1983, J. Geophys. Res., 88, 6109   
Li, G., Zank, G. P.,& Rice, W. K.M. 2O03, Journal of Geophysical Research (Space Physics), 108,1082   
Matthaeus, W. H., Qin, G., Bieber, J. W., & Zank, G. P. 2003, ApJ, 590, L53   
McKibben,R. B. 1972, J. Geophys. Res., 77, 3957   
McKibben,R. B., et al. 20O1, in International Cosmic Ray Conference, Vol. 8, International Cosmic Ray Conference, $^ { 3 2 8 1 - + }$   
Ng, C. K., Reames, D. V., & Tylka, A. J. 1999, Geophys. Res. Lett, 26, 2145   
Qin, G., He, H.-Q.,& Zhang, M. 2011, ApJ, 738, 28   
Qin, G.,& Shalchi, A. 2009, The Astrophysical Journal, 707, 61   
-. 2014, Physics of Plasmas (1994-present), 21, 042906   
Qin, G., Wang, Y., Zhang, M., & Dalla, S. 2O13, The Astrophysical Journal, 766, 74   
Qin, G., Zhang, M., Dwyer, J., Rassoul, H., & Mason, G. 2Oo5, The Astrophysical Journal, 627,

Qin, G., Zhang,M.,& Dwyer, J. R. 2O06, Journal of Geophysical Research (Space Physics),111, 8101   
Reames,D. V. 2010, Sol. Phys., 265,187   
Reames, D. V., Barbier, L. M., & Ng, C. K. 1996, ApJ, 466, 473   
Reames, D. V., Kahler, S. W.,& Ng, C. K. 1997, ApJ, 491, 414   
Rice,W. K. M., Zank, G. P.,& Li, G. 2OO3, Journal of Geophysical Research (Space Physics), 108, 1369   
Roelof, E. C., Gold, R. E., Simnet, G. M., Tappin, S. J., Armstrong, T. P., & Lanzerotti, L. J. 1992, Geophys. Res. Lett., 19, 1243   
Schlickeiser,R. 2002, Cosmic Ray Astrophysics (Berlin: Springer)   
Shalchi, A., Bieber, J. W., Matthaeus, W. H., & Qin, G. 2004, ApJ, 616, 617   
Shalchi, A.,Li, G.,& Zank, G.P. 2010,Ap&SS,325,99   
Skilling, J. 1971, ApJ, 170, 265   
Tan,L. C., Reames, D. V., Ng, C. K., Saloniemi, O., & Wang, L. 2009, ApJ, 701, 1753   
Teufel,A.,& Schlickeiser, R. 2003,A&A,397,15   
Wang, Y., & Qin, G. 2015, ApJ, 806, 252   
Wang, Y., Qin, G., & Zhang, M. 2012, The Astrophysical Journal, 752, 37   
Wang, Y., Qin, G., Zhang, M., & Dalla, S. 2014, ApJ, 789,157   
Wiedenbeck, M. E., Mason, G. M., Cohen, C. M. S., Nitta,N. V., Gómez-Herrero,R., & Haggerty, D. K. 2013, ApJ, 762, 54

Zank, G. P., Rice, W. K. M., & Wu, C. C.2000, J. Geophys.Res., 105,25079   
Zhang, M. 1999, ApJ, 513, 409   
Zhang, M., Qin, G., & Rassoul, H. 2009, ApJ, 692,109   
Zuo, P., Zhang, M., Gamayunov, K., Rassoul, H., & Luo, X. 2011, ApJ, 738, 168   
Zuo,P., Zhang,M.,& Rassoul,H. K. 2O13, The Astrophysical Journal, 767, 6

![](images/862fe7657b7e1eb61efbb415eff0ae34f27750a9a1447b0c841af5c30acab6c1.jpg)  
Helios 1   
Fig.1.— Solar wind plasma and magnetic field parameters observed at the Helios 1 spacecraft. From top to bottom, magnetic field strength $\mathbf { \left| B \right| }$ ，polar and azimuthal field angles $\theta$ and $\phi$ (in SSE coordinate),plasma density $N$ ，plasma temperature $T$ ,and bulk solar wind speed $V$ . The vertical line indicates a interplanetary shock passage.

![](images/6b5d4ff9b2bd51ecf0dd297ceb2d08bbd48d13e5a8ab557ac556554cd99c4328.jpg)  
Helios 2   
Fig. 2.— Same as Figure 1 except that the parameters are observed at the Helios 2 spacecraft.

![](images/e2ad3888ec0751a255d4218f9974bd8ad58b6d7307700ecfaf9665edf3e31ce8.jpg)  
Fig. 3.— Same as Figure 1 except that the parameters are observed at the IMP 8 spacecraft and olar and azimuthal field angles are in GSE coordinate.

Without perpendicular diffusion

With perpendicular diffusion

![](images/0ac7709f85f5a676aa35d214cb4b340179846497f627ab499b5e968249b5cc5d.jpg)  
Helios 1 Helios 2 IMP 8

![](images/8333dd8f9502afca356eca0d7bc0a55d1b1c01d6304409fc6b8f612372aaeb67.jpg)  
Helios 1 Helios 2 IMP 8

Fig. 4.— Geometry of a shock cross-section with three spacecraft at different locations. The dashed-arrow radial line indicates the center of the shock. The big solid circles represent the three spacecraft, and the small ones represent protons of SEPs.

![](images/6c6fc29d93975007735bb55dbdaa41e3a908450f505fa47459fb5b87cd8e297d.jpg)

Fig. 5.— Comparison of the observations of $3 - 6 \mathrm { M e V }$ proton fluxes with black lines and the simulation results of $5 \ \mathrm { { M e V } }$ protons with red lines. The observers are located at 1 AU in the ecliptic,but at different longitudes. The black lines show the time profiles of the observation fluxes,and the red lines indicate the simulation fluxes.The vertical lines indicate the moment of the spacecraft's field line is connected to the shock.

![](images/372b3c5227841cf2a513be27f1a91b0b2c384e0bbe30727bb2b12d3491193f78.jpg)  
Fig. 6.- Same as Figure 5 (a) but with different shock acceleration effciency parameters $\alpha$ and （204号 $\phi _ { c }$ ：

![](images/5f62220618edb61b41351480eef7f0a739df742f50d6f8bb6fb5d52039930f71.jpg)  
Fig. 7.— Same as Figure 5 (a) but with different injection spectrum $\gamma$

![](images/22642ab76896d3d32e3e32a2c9e12d16a124289dfee55cc6d9ad5abd1fe38948.jpg)  
Fig.8.— Comparison of the observations of $3 2 \mathrm { ~ - ~ } 4 5 ~ \mathrm { M e V }$ proton fluxes with black lines and the simulation results of $3 5 \ \mathrm { M e V }$ protons with red lines.The observers are located at 1 AU in the ecliptic,but at diferent longitudes. The black lines show the time profiles of the observation fluxes,and the red lines indicate the simulation fluxes.

Table 1: Model Parameters Used in the Calculations.   

<html><body><table><tr><td>Parameter</td><td>Physical meaning</td><td>Value</td></tr><tr><td>Vsw</td><td>solar wind speed</td><td>400 km/s</td></tr><tr><td>rc</td><td>radial normalization parameter</td><td>0.05 AU</td></tr><tr><td>△r</td><td>shock space interval between two fresh injections</td><td>0.001 AU</td></tr><tr><td>Vs</td><td>shock speed</td><td>0.52 AU/day</td></tr><tr><td>中s</td><td>shock width</td><td>35°</td></tr><tr><td>rb0</td><td>inner boundary</td><td>0.05 AU</td></tr><tr><td>rb1</td><td>outer boundary</td><td>50 AU</td></tr></table></body></html>

Table 2: Model Parameters Used in the Calculations.   

<html><body><table><tr><td>Case</td><td>a</td><td>c</td><td></td><td></td><td>2</td><td>(δB/B0)²</td></tr><tr><td>1</td><td>3.0</td><td>10°</td><td>0.48 AU</td><td>1.2% X K|l</td><td>-6.5</td><td>0.4</td></tr><tr><td>2</td><td>3.0</td><td>10°</td><td>0.24 AU</td><td>3.1% X Kll</td><td>-6.5</td><td>0.8</td></tr><tr><td>3</td><td>2.5</td><td>10°</td><td>0.48 AU</td><td>1.2% X Kll</td><td>-6.5</td><td>0.4</td></tr><tr><td>4</td><td>3.0</td><td>5°</td><td>0.48 AU</td><td>1.2% X KIl</td><td>-6.5</td><td>0.4</td></tr><tr><td>5</td><td>3.0</td><td>10°</td><td>0.48 AU</td><td>1.2% X Kll</td><td>-8.5</td><td>0.4</td></tr><tr><td>6</td><td>4.0</td><td>10°</td><td>0.66 AU</td><td>0.97% X Kll</td><td>-6.5</td><td>0.4</td></tr></table></body></html>