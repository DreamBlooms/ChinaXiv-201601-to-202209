# Investigation of the Compressible Flow through the Tip-Section Turbine Blade Cascade with Supersonic Inlet

Martin Luxa1, Jaromir Prihoda1, David Simurdal,Petr Straka², Jaroslav Synac3

1. Institute of Thermomechanics AS CR, v.v.i.,Dolejskova,1402/5,18200, Prague, Czech Republic   
2.Aerospace Research and Test Establishment,Plc,Beranovych,130,19905,Prague, Czech Republic,   
3. Doosan Skoda Power Co., Ltd., Tylova, 1/57, 30128, Pilsen, Czech Republic

$\copyright$ Science Press and Institute of Engineering Thermophysics, CASand Springer-Verlag Berlin Heidelberg 2016

The contribution deals with the experimental and numerical investigation of compresible flow through the tip-section turbine blade cascade with the blade $5 4 ^ { \prime \prime }$ long. Experimental investigations by means of optical (interferometry and schlieren method)and pneumatic measurements provide more information about the behaviour and nature of basic phenomena occurring in the profile cascade flow field.

The numerical simulation was carried out by means of the EARSM turbulence model according to Helsten [5] completed by the bypass transition model with the algebraic equation for the intermittency coeffcient proposed by Strakaand Prihoda [6]and implemented into the in-house numericalcode.The investigation was focused particularlyon the efectof shock waveson the shear layer development including the laminar/turbulent transition. Interactions ofshock waves with shear layers on both sides ofthe blade result usually in the transition in attached and/ or separated flow and so to the considerable impact to the flow structure and energy losses in the blade cascade.

# Keywords: long turbine rotor blade,supersonic tip section, optical methods, transition modelling, CFD

# Introduction

Recent advances in steam turbine efficiency have lead to steam turbines with relatively long rotor blades of the last stages in low pressure cylinder. Considerable length of these blades results from pursuit of larger exit annulus area since larger exit annulus area leads to lower exit losses due to decreased exit velocity.Also, increasing the exit area leads to lower number of turbine rows and thus to lower production costs.However,aerodynamic design of efficient long blades is a challenging task since there is not much space for the design which often results in blades with tips operating under supersonic regimes [1], [2],[3],[4].Therefore,both experimental and numerical investigations of flow past blade cascades representing such supersonic tip sections are essential for successful design.

Recent investigations showed that among other phenomena attention has to be paid to the interaction of shock waves with either suction or pressure side boundarylayer.Namely interaction of front shock wave inner branch with either pressure side boundary layer or near wake structure significantly contributes to energy losses [1].In order to understand and predict behaviour of these phenomena,detailed experiments and advanced numerical simulations has to be performed. Such numerical simulations have to take into account many factors, especially the effect of the pressure gradient, free stream turbulence,and possibly wall roughness.The mathematical model should not be based on the turbulence model only, but should be completed by adequate models of the laminar/turbulent transition and turbulent heat transfer. Moreover in transonic and supersonic flows, the interaction of shock waves with shear layers on blade surface may cause the transition to turbulence and possibly the flow separation.

The contribution deals with the numerical simulation of 2D compressible flow through supersonic turbine blade cascade with profiles corresponding to the tipsection of the low-pressure part of the steam turbine. Simulations carried out by the in-house numerical code based on the finite-volume solver for the RANS equations closed by the explicit algebraic model Reynolds stresses completed by the modified algebraic transition model. Simulations for the supersonic inlet conditions were focused especially on the effect of shock waves on the development of shear layers on blades including the laminar/turbulent transition in attached and/or separated flows.Behaviour of the investigated phenomena is also studied and documented by classical optical methods such as interferometry and schlieren technique.

# InvestigatedBlade Cascade

The tip section of the last rotor wheel, comprising of titanium rotor blades $5 4 "$ long,is characterized by very large stagger angle of the tip section profiles. The convergent - divergent tip profile cascade is designed for a very small flow turning angle. The fan of these long blade airfoils is highly spaced on the tip diameter (the tip section will rotate on a diameter of $4 7 0 0 \ \mathrm { m m }$ ，sothe overlapping of the adjacent profiles is very small (Fig.1).

The profile applied to the tip section (Fig.1) is relatively very thin,and its central line is unusually cambered,so that shapes of the suction and pressure sides have converse curvatures: the nature of the shape of the suction side is therefore concave and,conversely,the shape of the pressure side is convex. Characteristic dimensions of the blade cascade are shown in Table 1.

Table1 Characteristic dimensions of the blade cascade   

<html><body><table><tr><td>Pitch/Chord</td><td>s/b</td><td>0.951</td></tr><tr><td>Max.Thickness/Chord</td><td>T/b</td><td>0.025</td></tr><tr><td>Throat Opening/Chord</td><td>o/b</td><td>0.169</td></tr><tr><td>Stagger Angle</td><td>Y</td><td>78.37°</td></tr><tr><td>Trailing edge Thickness/chord</td><td>TTE/b</td><td>0.0033</td></tr><tr><td>Design Inlet Flow Angle</td><td>α1des</td><td>81.25°</td></tr></table></body></html>

The profile cascade consists of 8 prismatic blades only. The profile chord of the model was chosen $b = 0 . 1 5 \ \mathrm { m } ,$ i.e. the reduction scale is approximately 1:2, considering the real blade dimensions. The blade height is $l = 0 . 1 6 \mathrm { m }$ so the aspect ratio is $A R = 1 . 0 7$ only. The model dimensions result from many requirements and restrictions (e.g.: corresponding Reynolds number values,solidity of the blades, dimensions of the test section, etc.).

# Experiment

The experiments were carried out in the Aerodynamic laboratory at Novy Knin. The high-speed intermittent blow-down wind tunnel for 2D cascade testing was used, and the flow medium was dry air.A special test section was used for an investigation of the flow in a prismatic profile cascade with a small flow turning angle and su personic inlet velocity. This test section has been described in [5].

The high-speed wind tunnel for 2D cascade measurements (see Fig.2) is equipped with an adjustable super sonic inlet nozzle.The nozzle has parallel side walls and the shape of the upper and lower wall can be continuously changed,so that inlet Mach number up to $M _ { I } = 2 . 0$ can be reached.The air flows from the test section to the settling chamber. The backpressure is controlled by an adjustable control nozzle,which is situated downstream the settling chamber. The scheme of the test section is depicted in Fig.3.Both the upper wall and the lower wall of the inlet channel are equipped with perforated inserts. These inserts are connected to the low pressure parts of the wind tunnel,and the suction is controlled by slide valves. The suction mode of the lower perforated wall is used for inlet velocities around a value of $M _ { I } = 1 . 0$ ，to

![](images/a6180c920b2758bc4991887207128310a7952c0b0d22efcb45dce89dd60d3886.jpg)  
Fig.1The convergent-divergent tip profile cascade

![](images/796ad7de8eb2a4e213453f4d213d43d6f9f69b4571283794b107f43eca12609b.jpg)  
Fig.2Scheme of the suction type high-speed wind tunnel

1. silicagel dryer,2.filters,3.entrance nozzle,4.inlet nozzle, 5.transient insert,6.rotatable test section,7.settling chamber, 8.control nozzle,9.quick-acting valve,10.diffuser,11 main duct

![](images/506f4275c86b4e8deae9dee84d39de9533dc74aef36d76ede9e3f2879a170337.jpg)  
Fig.3Test section with profile cascade arrangement for optical measurements

improve the periodicityof the cascade inlet flow field. The upper perforated wall (with suction or with ventilation only） effectively prevents reflection of the outer branch of the inlet shock waves back into the studied flow field in the whole range of supersonic inlet Mach numbers,i.e.for $1 < M _ { I } < 2$ .The adjustable perforated tailboard is usually placed next to the trailing edge of the lateral profile in order to improve the periodicity of the exit flow field.In this specific configuration, the perforated tailboard is situated downstream the blade next to the lateral blade.The optimal value for the angle between the tailboard and the plane of the trailing edges of the cascade was found experimentally. The tailboard not only prevents exit shock waves from reflecting back to the exit flow field, it also prevents expansion taking place at the lower wall block edge from influencing the exit flow field [5].

The inlet flow field parameters are measured by a number of static pressure taps on the sidewalls and by a Prandtl probe,which was placed upstream the cascade inlet. The relatively remote position of the probe is aimed at reducing the probe disturbances in the proximity of the leading edges of the cascade. The representative value of the inlet Mach number is evaluated from the average value of the static pressures,which is obtained from six pressure taps before the cascade (see Fig.3) and the total pressure at the inlet (measured by the Prandtl probe), respectively. The isentropic exit Mach number was determined according to the static pressure,which was measured in the settling chamber downstream the cascade.

Optical measurements were carried out (interferometry-infinite fringe method, schlieren method in the Toepler configuration). The field of vision for the optical measurements covered an important part of the cascade middle channel only (see Fig.3). The dimension of this optical field is limited by the diameter of the glass windows for interferometry ( $\mathrm { 1 8 0 ~ m m } )$ ：

Experimental investigations were made at regime $M _ { I } = 1 . 4 5$ and $M _ { 2 i s } = 2 . 0$ .Corresponding Reynolds number related to the profile chord $b$ and to the isentropic exit Mach number $M _ { 2 i s }$ in the wind tunnel (dry air) was during the experiment $R e _ { e x p } = 1 . 9 2 \times 1 0 ^ { 6 }$ .This value is of the same order as that of real operating turbine where the value is $R e = 1 . 1 \times 1 0 ^ { 6 }$ . The Axial Velocity Density Ratio $( A V D R )$ ,which to some extent characterises the extent of 3D phenomena,was monitored during the pneumatic measurements; the $A V D R$ value for nominal condition was 1.059.

Level of free stream turbulence is estimated from earlier measurements with transonic cascade to $1 { \div } 2 \%$

# Mathematical model

The mathematical model of compressible flow is based on the conditionally-averaged Navier-Stokes equations closed by the EARSM turbulence model by Hellsten [6] with the algebraic bypass transition model by Straka and Prihoda [7]. The EARSM model is modified into the form corresponding to models with the turbulent viscosity and so the turbulent stress is given by the relation

$$
\begin{array} { l } { { \displaystyle \tau _ { i j } = \mu _ { t } \left( \frac { { \partial \widehat { U } _ { i } } } { { \partial { x _ { j } } } } { + \frac { { \partial \widehat { U } _ { j } } } { { \partial { x _ { i } } } } } { - \frac { 2 } { 3 } { \delta _ { i j } } \frac { { \partial \widehat { U } _ { k } } } { { \partial { x _ { k } } } } } \right) } } \\ { { \displaystyle \quad - \frac { 2 } { 3 } { \delta _ { i j } } \overline { { \rho } } k - a _ { i j } ^ { ( e x ) } \overline { { \rho } } k } } \end{array}
$$

where the extra-anisotropy tensor $a _ { i j } ^ { ( e x ) }$ is given by relation

$$
\begin{array} { r l } & { a _ { i j } ^ { ( e x ) } = \beta _ { 3 } \left( \mathcal { Q } _ { l k } ^ { * } \mathcal { Q } _ { k j } ^ { * } - \frac { 1 } { 3 } \delta _ { i j } I I _ { \boldsymbol { \mathcal { Q } } } \right) + \beta _ { 4 } \left( S _ { i k } ^ { * } \mathcal { Q } _ { k j } ^ { * } - \mathcal { Q } _ { l k } ^ { * } S _ { k j } ^ { * } \right) } \\ & { \quad \quad \quad \quad + \beta _ { 6 } \left( S _ { i k } ^ { * } \mathcal { Q } _ { k l } ^ { * } \mathcal { Q } _ { l j } ^ { * } + \mathcal { Q } _ { l k } ^ { * } \mathcal { Q } _ { k l } ^ { * } S _ { l j } ^ { * } - I I _ { \boldsymbol { \mathcal { Q } } } S _ { i j } ^ { * } - \frac { 2 } { 3 } \delta _ { i j } I V \right) } \\ & { \quad \quad \quad \quad \quad + \beta _ { 9 } \left( \mathcal { Q } _ { l k } ^ { * } S _ { k l } ^ { * } \mathcal { Q } _ { l m } ^ { * } \mathcal { Q } _ { m j } ^ { * } - \mathcal { Q } _ { l k } ^ { * } \mathcal { Q } _ { k l } ^ { * } S _ { l m } ^ { * } \mathcal { Q } _ { m j } ^ { * } \right) } \end{array}
$$

The coefficients $\beta _ { i }$ depend on invariants of strain-rate and vorticity tensors in the non-dimensional form. Transport equations for the turbulent energy $k$ and the specific dissipation rate $\omega$ are given by the SST model according to Menter[8] in the form

$$
\begin{array} { l } { { \displaystyle \frac { \hat { c } \big ( \overline { { \rho } } k \big ) } { \hat { c } t } + \frac { \hat { c } \big ( \overline { { \rho } } \overline { { U } } _ { j } k \big ) } { \hat { c } x _ { j } } = P _ { k } + \frac { \hat { c } } { \hat { \alpha } x _ { j } } \bigg [ \big ( \mu + \sigma _ { k } \mu _ { t } \big ) \frac { \hat { c } k } { \hat { \alpha } x _ { j } } \bigg ] } } \\ { ~ - \beta ^ { * } \overline { { \rho } } \omega k }  \\ { { \displaystyle \frac { \hat { c } \big ( \overline { { \rho } } \omega \big ) } { \hat { c } t } + \frac { \hat { c } \big ( \overline { { \rho } } \overline { { U } } _ { j } \omega \big ) } { \hat { \alpha } x _ { j } } = \frac { \gamma \omega } { k } P _ { k } - \beta \overline { { \rho } } \omega ^ { 2 } + } } \\ { { \displaystyle \frac { \hat { c } } { \hat { \alpha } x _ { j } } \bigg [ \big ( \mu + \sigma _ { \omega } \mu _ { t } \big ) \frac { \hat { \alpha } \omega } { \hat { \alpha } x _ { j } } \bigg ] + C _ { D } } } \end{array}
$$

Turbulent viscosity is given by the relation

$$
\mu _ { t } = C _ { \mu } \overline { { \rho } } k \tau _ { t }
$$

withtheturbulenttimescale

$$
\tau _ { t } = \operatorname* { m a x } \left( \frac { 1 } { \beta ^ { * } \omega } ; C _ { \tau } \sqrt { \frac { \nu } { \beta ^ { * } \omega k } } \right)
$$

where the Kolmogorov viscous time scale is used near the wall. The variable coefficient $C _ { \mu }$ is obtained from the equation

$$
C _ { \mu } = - \big ( \beta _ { 1 } + I I _ { \varOmega } \beta _ { 6 } \big ) / 2
$$

For the reduction of the undesirable over-production of the turbulent energy in the stagnation region, the pro duction term in the turbulent energy equation was modified into form

$$
P _ { k } = \psi \left( \tau _ { i j } \frac { \partial \bar { U _ { i } } } { \partial x _ { j } } \right) + \left( 1 - \psi \right) \mu _ { t } \varOmega ^ { 2 }
$$

where $\tau _ { i j }$ is the Reynolds stress tensor and $\varOmega$ is the absolute value of the vorticity tensor.The parameter $\psi$ is given by the relation

$$
\psi = 1 - \operatorname * { m a x } \biggl [ \operatorname * { m i n } \Bigl ( C _ { \psi } \tau _ { t } \Bigl | S ^ { 2 } - \varOmega ^ { 2 } \Bigr | ; 1 \Bigr ) ; 0 \biggr ]
$$

$$
C _ { \psi } = 0 . 0 5 \div 0 . 2
$$

The parameter $\psi$ is equal to 1 nearly in all the computational domain except the vicinity of the stagnation point where it decreases to zero.The EARSM model is described in detail by Hellsten [6].

For the prediction of the transitional flows, the production and destruction terms in the $k$ -equation are multiplied by the intermittency coefficient $\gamma .$ Similarly, the effective viscosity is given by $\mu _ { e f } = \mu + \gamma \mu _ { t }$ in the transition region. The transition model is based on the concept of different values of the intermittency coefficient in the boundary layer $\gamma _ { i }$ and in the free stream $\gamma _ { e }$ . The intermittencycoefficient in the boundary layer $\gamma _ { i }$ is expressed by the relation

$$
\gamma _ { i } = 1 - \exp \Bigl [ - \hat { n } \sigma \bigl ( \mathrm { R e } _ { x } - R e _ { x t } \bigr ) ^ { 2 } \Bigr ]
$$

The transition onset is given according to Straka and Prihoda [7] by the empirical correlation for the momentum Reynolds number $R e _ { \theta t } = \textrm { f } ( T u , \ \lambda _ { t } )$ where $T u \ ( \% )$ is the free-stream turbulence level and $\lambda _ { t }$ is the pressure-gradient parameter. The length of the transition region is expressed using the parameter $N = \hat { n } \sigma { \ R e _ { \theta t } } ^ { 3 }$ where $\hat { n }$ is the spot generation rate and $\sigma$ is the spot propagation rate introduced by Narasimha [9]. The effect of the free-stream turbulence and the pressure gradient on the parameter $N$ is correlated by an empirical relation proposed for the attached flow by Solomon et al. [10]. The onset of transition in separated flow is given by the correlation proposed by Mayle[11] in the form $R e _ { x t } = \mathrm { f } \left( R e _ { \theta s } , R e _ { x s } \right)$ where $R e _ { \theta s }$ is the momentum Reynolds number at the separation and $R e _ { x s }$ is the Reynolds number related to the distance of the separation from the leading edge. The length of the transition region is expressed according to Mayle[7]by the relation

$$
\hat { n } \sigma = \frac { 2 . 2 8 \times 1 0 ^ { - 5 } } { R e _ { \theta s } ^ { 1 . 4 } }
$$

To avoid the application of local variables, the maximum of the vorticity Reynolds number $R e _ { \nu m a x }$ is used instead of the momentum Reynolds number $R e _ { \theta } .$ This link is expressed by the relation $R e _ { \theta } { = } R e _ { { \nu } m a x } / C$ where the parameter $C$ depends on the pressure gradient. The used version of the algebraic transition model is described in detail by Fürst et al. [12].

The algebraic model was implemented into the inhouse numerical code.The code is based on the finitevolume method of the cell-centered type with the Osher'sSolomon's approximation of the Riemann solver and a two-dimensional linear reconstruction with the Van Albada's limiter. The governing equations are discretized using a multi-block quadrilateral structured grid with a block overlapping implementation.

# Calculation setup

Due to supersonic inlet conditions,the flow through the blade cascade is influenced by parasitic shock waves arising by the reflection from the computational domain boundaries.The application of the quadrilateral blockstructured computational grids with their overlapping leads moreover to the reflection of shock waves on the block boundaries.Therefore the computational domain was adequately prolonged before and behind the blade cascade to weaken these reflections.The detail of the computational grid of the "chimera" type near the leading and trailing edges is given in Fig. 4.

![](images/6d31b053b22c23c2b07989b2f26d11530ca29fec931156b2338fbfaf980b748f.jpg)  
Fig.4Detail of the computational domain "chimera"

The constant values of the total pressure $p _ { { \boldsymbol { \theta } } { \boldsymbol { I } } }$ ，total temperature $T _ { 0 I }$ and incidence angle $\alpha _ { I }$ were prescribed as inlet conditions.The static pressure was extrapolated from the computational domain. The static pressure given by the outlet isentropic Mach number was prescribed as the outlet condition.Inlet free-stream turbulence was chosen $T u = 5 \%$ .The ratio of viscosities $\mu _ { t } / \mu$ was chosen according to the length of inlet part.The free-stream turbulence in the distance of one spacing before the cascade was $T u = 1 . 2 \%$

# Results

The flow field in the interblade channel is supersonic, with a small subsonic region around the leading edge. The sonic throat is missing. In the relatively small area of the interblade channel,very intense supersonic simple expansion takes place on the suction surface near the leading edge (Fig. 5).

Figure 6 compares the distributions of the isentropic Mach number along the suction side and the pressure sideof theprofile.Thefirst distributionisobtainedfrom experiment, while the second distribution is obtained from CFD simulation (commercial code) described in [1] The calculated flow field in this case is completely turbulent (Fig.7). This results ina less complicated interaction of the boundary layer with the internal branch of the inlet shock wave on the pressure side of the profile.By contrast, the test result(Fig.5) shows that the interaction is more complex and local separation takes place. This is because the boundary layer on the pressure side is probably laminar up to the interaction area.The impact of this complex interaction is that it suppresses the expansion area on the suction side of the neighbouring profile.The expected additional supersonic expansion upstream the point where internal branch of exit shock wave interacts with suction side boundary layer is completely cancelled (in the range $0 . 4 < x / b x < 0 . 6$ for CFD and $0 . 2 < x / b x <$

![](images/976d2c24d3b72c41e51de9c5b3ac6f42fb26380b142be60ce9d5fe1c2174cb19.jpg)  
Fig.5Interferogram showing subsonic region and expansion on the suction surface behind the leading edge   
Fig.6Distribution of isentropic Mach number along profile obtained by commercial code and experiment

![](images/d7ad00634ac6e6a65f969a232605be7c26921514ac85a8e102347074785e02a1.jpg)  
Fig.7Distribution of Mach number - fully turbulent CFD

0.4 for experiment as can be seen from Fig.6).Therefore,downstream this interaction,the values ofMach number up to the trailing edge are lower than in the case of turbulent interaction on the pressure side.This is also the reason why the interaction of exit shock with the suction sideboundarylayerislocated further downstreamincase of CFD (Fig. 6). This fact has an essential negative influence on the aerodynamic loading of the studied profile.

# Current numerical results

The distribution of the pressure coefficient along the blade obtained by the EARSM model with the algebraic transition model is shown in Fig.8.The coordinate s is measured along the blade surface from the leading edge. Theeffect of the interaction of shock waveswithboundary layer on the suction side is well visible at $\mathbf { S } / \mathbf { S } _ { \mathrm { m a x } } \approx 0 . 2$ 0.35 and O.5 approximately. This distribution does not fit that obtained from experiment perfectly,but it is clear that location of the exit shock/suction side boundary layer interaction is at $\mathrm { \ s / s } _ { \mathrm { m a x } } \approx 0 . 5$ unlike in case of fully turbulent calculation (Fig. 6,[1]).

The field of Mach number isolines in the blade cascade is shown in Fig.9.Because of the staggerangle and inlet flow conditions, the concave side of the blade is the suction type while the convex side is the pressure type.It can be seen in Figures 9,1O and 11,that the reflected oblique shock wave impinges on the suction side where the interaction with the boundary layer causes the bypass transition in attached flow in the distance $s / s _ { \mathrm { m a x } } \approx 0 . 1 5$ from the leading edge. On the contrary, the impact of the front shock wave from the adjacent blade leads on the pressure side to the transition in the distance $s / s _ { \mathrm { m a x } } \approx 0 . 8 8$ from the leading edge.

The distribution of the Reynolds number $R e _ { \theta }$ related to the momentum thickness of the boundary layer and of the skin friction coefficient $C _ { f }$ related to inlet flow parameters is shown in Fig.10.

![](images/b078e58b86421455134c3dac7bd09f7dda2ba5effe49306d14f14eed21e5c1c8.jpg)  
Fig.8Distribution of the pressure coefficient along the blade surface obtained by inhouse code and experiment

![](images/cffcbb6b120d042fc7317a9ed9dd6afe26171730a7a50c127a7c29da4b94b9c7.jpg)  
Fig.9Mach number isolines in the detail of the computational domain

The bypass transition on the suction side is evident from the distribution of $C _ { f }$ The interaction of the boundarylayer with inner branch of the exit shock wave can be shown on the distribution of $R e _ { \theta }$ and especially $C _ { f }$ in the distance $s / s _ { \mathrm { m a x } } \approx 0 . 5$ from the leading edge.Following the smooth development of the laminar boundary layer, the separated-flow transition with a short separation region and following reattachment occurs on the pressure side before the trailing edge due to the interaction with the front shock wave from the adjacent blade.

Comparison of the flow field by CFD and schlieren technique in the interaction region is shown in Fig. 11. Both CFD and experiment show structure typical for shock/boundary layer interaction with local separation region. Impinging front shock causes boundary layer to separate with separation point upstream of the interaction. Effective change of the flown surface at the separation point and reattachment point results in origin of two left running shockwaves.In case of experiment, the separation region is noticeably longer and the point of front shock impingement is closer to the trailing edge.

The field of turbulent energy in the prolonged compu tational domain is shown in Fig.12. The flow along the whole blade is attached with the exception of the short separated bubble before the trailing edge of the pressure side.This is in accordance with the turbulent energy field. where the growth of turbulent energy is more apparent on the suction side with the earlier transition.The substan tially higher increase of turbulent energy occurs only in thewake behindblades.

![](images/17cd15a32718d8cdaa26e47bec84d1c26882ba33fd9f0e0d1cfb470a0a3abbfd.jpg)  
Fig.10Distribution of boundary layer parameters along the blade surface

![](images/6ca771176ca413be080915849ce02c53629a42b595573e9cb393c560da783cfc.jpg)  
Fig.11 Comparison of flow in the region of interaction of the front shock and pressure side boundary layer - schlieren pictures

![](images/7576a194ee623537768b5090eff0a1034ff00277e5f850cbd239b538cbec62d9.jpg)  
Fig.12 Field of turbulent energy in the detail of prolonged computational domain

The distribution of the relative total pressure $p _ { 2 0 } / p _ { I 0 }$ in the wake in the distance of $2 5 ~ \mathrm { m m }$ behind the cascade exit plane is shown in Fig.13.Besides the prediction by means of the EARSM model with algebraic transition model, the $\gamma { - } R e$ transition model of Langtry and Menter [13] implemented in the commercial code ANSYSFluent was used for the comparison. The distribution of total pressure corresponds to the mean velocity profiles in the wake behind blades and is a measure of energy losses in theblade cascade.Besides the actual wake, theeffectof the outer branch of the exit shock wave is shown on the distribution of the total pressure.

![](images/a1753d82891e55157fd4ffc5fa5377db4227bfe39bfc38c9587b75cedfa3c0d4.jpg)  
Fig.13Distribution of the relative total pressure behind the blade cascade

# Conclusions

The paper shows that problem of shock wave boundarylayer interactionplays important role in case of recent designs of supersonic tip sections for long last stage rotor blades.It has been shown that in case of tip section blade cascades,very short region before trailing edge has great influence on the flow within the interblade channel.Moreover,in case of supersonic tip sections,the flow in this region is influenced by front shock wave.From this point of view it is crucial whether the boundary layer on the pressure side can withstand interaction with this front shockwave.Therefore,to predict flow through such blade cascades correctly, it is necessary to employ transitional turbulence model when RANS is to be used.Results published in the paper show that the EARSM model performs reasonably well.

# Acknowledgements

The work was supported by the Technology Agency of the Czech Republic under the grant TA03020277 and by the Czech Science Foundation under grant P101/12/ 1271.Institutional support RVO 61388998 is also gratefully acknowledged. The authors also thank DOOSAN SKODA POWER Co., Ltd., who made this research possible.

# References

[1]Luxa,M., Simurda, D., Fort, J., Fuürst, J., Safarik, P., Synac,J.,Rudas,B.,(2015),Aerodynamic Investigation of Tip Section for Titanium Blade 54",Proceedings of the 11th European Conference on Turbomachinery Fluid Dynamics and Thermodynamics (ETC11),March 23-27, 2015, Madrid, Spain.   
[2]Parvizinia,M.,Berlich, C.,Truckenmüller, F., Stuier, H., (2004), Numerical and Experimental Investigations into the Aerodynamic Perfor-mance of a Supersonic Turbine Blade Profile,ASME Paper GT2004-53823,Atlanta, USA.   
[3]Shibata, T.,Nakano, S., Ono,H.,Morishita,K., Tani, Y., (2013), Linear Cascade Wind Tunnel Testing of Supersonic Inflow and Outflow Turbine Blades, Transactions of JSME,Series B,Vol.79,No.806,pp.2120-2133   
[4]Senoo, S.,Asai, K., Kurosawa,A.,Lee, G., (2013), Titanium 50-inch and 60-inch Last-stage Blades for Steam Turbines,Hitachi Review, vol. 62,No.1   
[5]Simurda, D., Luxa, M.,Safarik,P., Synac, J. and Rudas, B.,(2014),Measurements on Supersonic Turbine Cascades - Methodical Approach, Proceedings of the XXII Symposium on Measuring Techniques in Turbomachinery, Lyon, France.   
[6]Hellsten,A.,(2005),A new advanced $\mathbf { k }$ -omega turbulence model for high-lift aerodynamics,AIAA Jour., 43,1857- 1869   
[7]Straka,P.,Prihoda,J.(2010),Application of the algebraic bypass-transition model for internal and external flows, Proc.Conf. Experimental Fluid Mechanics 2010,636- 641,Liberec, Czech Republic.   
[8]Menter, F.R. (1994), Two-equation eddy-viscosity turbulence models for engineering applications,AIAA Jour., 32,1598-1605   
[9]Narasimha,R.(1985),The laminar-turbulent transition Zone in the boundary layer, Progress in Aerospace Science,22,29-80   
10]Solomon,W.J.,Walker, G.J., Gostelow, J.P. (1996), Transition Length Prediction for Flows with Rapidly Changing Pressure Gradients,Jour. Turbomachinery, 118,744-751   
11]Mayle,R.E.(1991), The role of laminar-turbulent transition in gas turbine engines,Jour. Turbomachinery,113, 509-537   
12]Furst,J.,Prihoda,J., Straka,P. (2013),Numerical simulation of transitional flows, Computing, 95, S163-S182   
13]Langtry, R.B., Menter, F.R. (20o9), Correlation-based Transition Modeling for Unstructured Parallelized Computational Fluid Dynamics Codes,AIAA Jour., 47,2894-2906