# Three-dimensional Numerical Study of Laminar Confined Slot Jet Impingement Cooling using Slurry of Nano-encapsulated Phase Change Material

M. Mohib Ur Rehman, Z.G. $\mathbf { Q } \mathbf { u } ^ { * }$ , R. P. Fu

KeyLaboratoryof Thermal Fluid Science and Engineering,MinistryofEduction,School of Energyand Power Engineering, Xi'an Jiaotong University, Xi'an, Shaanxi, 710049, China

This Article presents a three dimensional numerical model investigating thermal performance and hydrodynamics features of the confined slot jet impingement using slurry of Nano Encapsulated Phase Change Material (NEPCM) as acoolant.The slurry is composed of water as a base fluid and n-octadecane NEPCM particles with mean diameter of $1 0 0 \mathrm { n m }$ suspended in it.A single phase fluid approach is employed to model the NEPCM slurry.The thermo physical properties of the NEPCM slurry are computed using modern approaches being proposed recently and governing equations are solved with a commercial Finite Volume based code.The efects of jet Reynolds number varying from 10O to 60o and particle volume fraction ranging from $0 \%$ to $28 \%$ are considered. The computed results are validated by comparing Nusselt number values at stagnation point with the previously published results with water as working fluid.It was found that adding NEPCM to the base fluid results with considerable amount of heat transfer enhancement.The highest values of heat transfer coeficients are observed at $\mathrm { H } / \mathrm { W } { = } 4$ and $\mathrm { C } _ { \mathrm { m } } { = } 0 . 2 8$ .However,due to the higher viscosity of slurry compared with the base fluid,the slurry can produce drastic increase in pressure drop of the system that increases with NEPCM particle loading and jet Reynolds number.

# Keywords: Nano-encapsulated phase change material, heat transfer enhancement,confined slot jet impingement

# Introduction

Heat transfer enhancement in jet impingement process is one of the most reliable technique for high heat flux removal from heated surfaces in many engineering and industrial applications such as cooling of gas turbine blades and electronic chips, annealing of glass and drying of textiles.A jet of working fluid leaving a slot or a round nozzle is directed towards a targeted heated surface where it generates high heat transfer coefficients with relatively low pressure drop. The use of slot nozzle provides larger stagnation zone with uniform spreading of coolant after impingement [1]. In fact, the flow fields and heat transfer parameters in slot jets are different from circular jets [2].The flow regime can vary from laminar to completely turbulent one depending on the application, where laminar impinging jets have been used frequently forthe cooling of electronic chips [3].Moreover, several studies have been conducted on laminar [4] and turbulent [5] flow regimes of confined jet impingement.

Jet Impingement has two major design configurations i.e.confined and unconfined. The presence of a confining top produces significant effects on fluid flow dynamics as well as on heat transfer characteristics of the jet [6]. Limited space requirement for compact design makes the confined configuration more suitable,while unconfined impinging jets are simple in design [7]. The importance of confinement in jet impingement heat transfer has been investigated in [8]. Lin et al. [9] ex-perimentally observed that heat transfer coefficients increases with the jet Reynolds number. Park et al. [1O] numerically re ported that the nozzle to target height influence the local and average Nusselt numbers for both laminar and turbulent cases.

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>Dp</td><td>particle diameter (m)</td><td>u,v,w</td><td>velocity components</td></tr><tr><td>cp</td><td>specific heat capacity of fluid (J/kg K)</td><td>x,y,z</td><td>spatial coordinates</td></tr><tr><td>K</td><td>thermal conductivity (W/m K)</td><td colspan="2">Greek symbols</td></tr><tr><td>kb</td><td>static thermal conductivity (W/m K)</td><td>e</td><td>shear rate (1/s)</td></tr></table></body></html>

<html><body><table><tr><td>H</td><td>nozzle to plate distance (m)</td><td>Cm</td><td>mass concentration of NEPCM</td></tr><tr><td>W</td><td>jet width (m)</td><td>从</td><td>dynamic viscosity (mPa.s)</td></tr><tr><td>X</td><td>length of copper plate (m)</td><td>P</td><td>density (kg/m³)</td></tr><tr><td>p</td><td>pressure (Pa)</td><td></td><td>viscous dissipation</td></tr><tr><td>△p</td><td>pressure drop (pa)</td><td></td><td>volume concentration of NEPCM</td></tr><tr><td>q</td><td>heat flux of the hot wall (W/m²)</td><td>α</td><td>thermal diffusivity (m²/s)</td></tr><tr><td>Re</td><td>Reynolds number</td><td>Subscripts</td><td></td></tr><tr><td>Pe</td><td>Peclet number</td><td>0</td><td>stagnation point</td></tr><tr><td>Nu</td><td>Nusselt number</td><td>avg</td><td>average</td></tr><tr><td>h</td><td>heat transfer coefficient (W/m² K)</td><td>p</td><td>particle</td></tr><tr><td>T</td><td>temperature (K)</td><td>b</td><td>bulk</td></tr><tr><td>T</td><td>lower melting temperature (K)</td><td>W</td><td>impingement wall</td></tr><tr><td>T2</td><td>upper melting temperature (K)</td><td>pcm</td><td> phase change material</td></tr><tr><td>TMr</td><td>melting range (K)</td><td>f</td><td>fluid</td></tr><tr><td>Tm</td><td>melting point (K)</td><td>S</td><td>solid</td></tr><tr><td>h1s</td><td>latent heat of fusion of PCM (kJ/kg)</td><td>j</td><td>jet</td></tr><tr><td>V</td><td>velocity</td><td>eff</td><td>effective thermophysical properties of fluid</td></tr></table></body></html>

In recent years,researchers mainly focus on different types of working fluids used for impinging jet heat transfer.Numerous studies has been conducted on air as a working fluid for jet impingement [11]. However, impinging jets with liquid have attracted much more attention recently due to its better heat transfer performance [12].Literature suggested that thermophysical properties of the working fluid will greatly influence the cooling capability of jet impingement. Moreover, the specific heat capacity of the traditional fluids like water is not sufficient enough to meet the requirements of high heat flux removal [13].To address this issue,an innovative technique has been suggested recently to add nano-encapsulated phase change material (NEPCM) particles in the base fluid to form a two phase suspension [14].The particle size vary from micro to nano depending on the application [15].

The PCM has the capability to absorb and release heat during melting and solidification simultaneously, while encapsulation prevent PCM from leakage [16]. In general NEPCM particles are made up of organic paraffin cores with surrounding shells of cross linked polymer [17]. The latent heat of NEPCM capsule suspended in the base fluid drastically increase the thermal storage capacity of the slurry when particles undergoes phase change process [18]. Therefore,using these types of advanced fluids are beneficial for applications such as compact heat exchanger and heat sinks if the cooling system parameters are well designed to take maximum advantage of the NEPCM latent heat [19].

Numerous studies reported the heat transfer enhancement in forced convection by adding NEPCM particles to the coolant. Wu [2O] conducted experimental study to investigate the effect of NEPCM slurry on heat transfer enhancement of jet impingement cooling. The results suggested that the volume fraction of the NEPCMin base fluid greatly influence the thermal performance.Slurry with $28 \%$ volume fraction of NEPCM enhance the heat transfer coefficient by $50 \%$ for jet impingement as compare to base fluid.

In the present article,a three dimensional conjugate heat transfer model is used to study the cooling and hydrodynamic performance of a confined slot jet impinge ment in laminar regime with NEPCM slurry as a coolant. To the best of authors’knowledge,no published data exist in literature on experimental and numerical study of confined slot jet impingement using NEPCM slurry. Therefore,this attempt is expected to provide a breakthrough in engineering applications such as electronic cooling and material processing.

# Geometrical configuration and Model description

The schematic diagram of the physical domain is presented in Figure 1,which illustrates geometrical configurations of confined slot jet impingement cooling system. The three-dimensional model has nozzle width(W) equal to $6 . 2 \mathrm { m m }$ and plate's length to width ratio (L/W) equal to 60 while the nozzle to plate distance (H/W) ranging from 4 to 6.The Cartesian coordinate system is employed in the present study,which origin is located at the center of impingement surface.A constant heat flux value of $1 0 , \bar { 0 0 0 } \ \mathrm { W / m } ^ { 2 }$ is applied on the bottom surface of copper plate.The confinement top is made up of aluminum, which is insulated completely so that no heat transfer takeplaceacrossit.Furthermore,uniforminletvelocities are considered with laminar and incompressible flow regime. Radiation and natural convection effects are small enough to be neglected in the model design.

![](images/2ed8280741197e985e47aab0aa267605c8836194a418244c4138848aa4c55107.jpg)  
Fig.1Schematic diagram of confined slot jet impingement cooling system

As present simulation is conducted at low Reynolds number, effects caused by viscous dissipation are neglected [16].The working fluid is either water or slurry with different mass concentrations of NEPCM particles in water.Fluid jet temperature is set at 298K for all studied configurations to ensure that NEPCM particles experience phase change process as soon as slurry reaches the impingement surface.The particles mass concentrationintheslurryisbelow O.3;therefore,thefluidisassumed to be Newtonian [21].Furthermore,it is assumed that the base fluid and NEPCM particles flow at the same velocity without having any lag between the phases [22]. And also,no mass transfer take place between the base fluid and NEPCM capsule in order to make it ensure that melted PCM inside the capsule will not disperse in the base fluid.NEPCM particles are considered to be spherical in shape with mean diameter of $1 0 0 \mathrm { n m }$ [18]. Further, there is no temperature gradient present inside the particle and its melting range is between 293.15K to 303.15K.The effect of shell material on heat transfer is neglected as it is very thin relatively to the core[19].It is also important to mention that, due to homogenous distribution of particles across the base fluid, the bulk prop erties of slurry are expected to be constant apart from thermal conductivity and specific heat capacity that depends on micro-convection and slurry operating temperature respectively [17].

# Governing equations

The continuity,momentum and energy equations are considered to be the governing equations of flow and heat transfer in our analysis. They are specified by the following expressions:

Continuity equation:

$$
\frac { \partial u } { \partial x } + \frac { \partial \nu } { \partial y } + \frac { \partial w } { \partial z } = 0
$$

Momentum equations:

$$
\begin{array} { r l } & { \rho _ { e f f } ( u \stackrel { \widehat { \sigma \boldsymbol { u } } } { = } + \frac { \widehat { \sigma \boldsymbol { u } } _ { e } } { \widehat { \sigma \boldsymbol { u } } _ { e } } + \frac { \widehat { \sigma \boldsymbol { u } } _ { e } } { \widehat { \sigma \boldsymbol { u } } _ { e } } + \frac { \widehat { \sigma \boldsymbol { u } } _ { e } } { \widehat { \sigma \boldsymbol { u } } _ { e } } ) = } \\ & { - \frac { \widehat { \sigma \boldsymbol { u } } _ { e } } { { \widehat { \sigma \boldsymbol { u } } _ { e } } } + \frac { \widehat { \sigma } } { { \widehat { \sigma \boldsymbol { u } } _ { e } } } ( \mu _ { e g } \frac { \widehat { \sigma \boldsymbol { u } } _ { e } } { \widehat { \sigma \boldsymbol { u } } _ { x } } ) + \frac { \widehat { \sigma } } { { \widehat { \sigma } _ { e } } } ( \mu _ { e g } \frac { \widehat { \sigma \boldsymbol { u } } _ { e } } { \widehat { \sigma \boldsymbol { y } } _ { e } } ) + \frac { \widehat { \sigma } } { { \widehat { \sigma } _ { e } } } ( \mu _ { e g } \frac { \widehat { \sigma \boldsymbol { u } } _ { e } } { \widehat { \sigma \boldsymbol { u } } _ { e } } ) } \\ & { \rho _ { e g } ( u \frac { \widehat { \sigma \boldsymbol { v } } } { \widehat { \sigma } _ { e } } + \frac { \widehat { \sigma \boldsymbol { v } } _ { e } } { \widehat { \sigma \boldsymbol { v } } _ { e } } + \nu \frac { \widehat { \sigma \boldsymbol { v } } _ { e } } { \widehat { \sigma \boldsymbol { v } } _ { e } } ) - \frac { \widehat { \sigma } } { { \widehat { \sigma } _ { e } } } } \\ & { - \frac { \widehat { \sigma \boldsymbol { p } } _ { e } } { \widehat { \sigma } _ { e } } + \frac { \widehat { \sigma } } { { \widehat { \sigma } _ { e } } } ( \mu _ { e g } \frac { \widehat { \sigma \boldsymbol { v } } _ { e } } { \widehat { \sigma } _ { e } } ) + \frac { \widehat { \sigma } } { { \widehat { \sigma } _ { e } } } ( \mu _ { e g } \frac { \widehat { \sigma \boldsymbol { v } } _ { e } } { \widehat { \sigma } _ { e } } ) + \frac { \widehat { \sigma } } { { \widehat { \sigma } _ { e } } } ( \mu _ { e g } \frac { \widehat { \sigma \boldsymbol { v } } _ { e } } { \widehat { \sigma } _ { e } } ) } \\ &  \rho _ { e g } ( u \stackrel { \widehat { \sigma \boldsymbol { v } } \boldsymbol { v } } { = } + \frac { \widehat { \sigma } } { { \widehat { \sigma } _ { e } } } ) + \frac { \widehat { \sigma } } { { \widehat { \sigma } _ { e } } } ( \mu  \end{array}
$$

Energy equation for the fluid domain:

$$
\begin{array} { r l } & { \rho _ { e f f } C _ { p , e f f } \left( u \frac { \partial T _ { f } } { \partial x } + \nu \frac { \partial T _ { f } } { \partial y } + w \frac { \partial T _ { f } } { \partial z } \right) } \\ & { = \cfrac { \partial } { \partial x } \left( k _ { e f f } \frac { \partial T _ { f } } { \partial x } \right) + \cfrac { \partial } { \partial y } \left( k _ { e f f } \frac { \partial T _ { f } } { \partial y } \right) + \cfrac { \partial } { \partial z } \left( k _ { e f f } \frac { \partial T _ { f } } { \partial z } \right) + \dot { \varphi } ^ { 2 } } \end{array}
$$

Energy equation for the solid domain:

$$
\frac { \hat { \sigma } } { \hat { \sigma } x } \bigg ( k _ { s } \frac { \hat { \sigma } T _ { s } } { \hat { \sigma } x } \bigg ) + \frac { \hat { \sigma } } { \hat { \sigma } y } \bigg ( k _ { s } \frac { \hat { \sigma } T _ { s } } { \hat { \sigma } y } \bigg ) + \frac { \hat { \sigma } } { \hat { \sigma } z } \bigg ( k _ { s } \frac { \hat { \sigma } T _ { s } } { \hat { \sigma } z } \bigg ) = 0
$$

The term $\dot { \varphi }$ in energy equation predict the rate at which viscous energy is dissipated per unit volume by virtue of fluid viscosity.

# Thermophysical properties of NEPCM slurry

The bulk properties of slurry are function of NEPCM concentration and operating temperature. The slurry considered in the present analysis is composed of water as a base fluid and NEPCM capsules suspended in it.Whereas, NEPCM capsules are made up of n-octadecane core as a phase change material with melting point $\left( \mathrm { T } _ { \mathrm { m } } \right)$ of 298.15 K and a surrounding cross linked polymer shell. Table 1 illustrate thermophysical properties of slurry components. The effective properties of slurry are predicted by the following co-relations derived in literature:

Density:

$$
\rho _ { e f f } = ( 1 - c _ { m } ) \rho _ { w a t e r } + c _ { m } \rho _ { p }
$$

Where $c _ { m }$ and $\rho _ { p }$ are mass concentration of slurry and density ofNEPCM particle.

Table 1Thermophysical properties of NEPCM slurry components [12,20]   

<html><body><table><tr><td></td><td>p</td><td>C</td><td>k</td><td>hs</td><td>μ</td></tr><tr><td>Octadecane</td><td>850</td><td>1800</td><td>0.34</td><td>220.3</td><td>-</td></tr><tr><td>Nano Particles</td><td>1055</td><td>1965</td><td>0.22</td><td>107.1</td><td>-</td></tr><tr><td>Water (292K)</td><td>999</td><td>4182</td><td>0.60</td><td>-</td><td>0.993</td></tr><tr><td>Water (298K)</td><td>996</td><td>4143</td><td>0.61</td><td>二</td><td>0.9</td></tr></table></body></html>

Viscosity [23]:

$$
\mu _ { e f f } = \mu _ { w a t e r } \left( 1 - \xi - 1 . 1 6 \xi ^ { 2 } \right) ^ { - 2 . 5 }
$$

Where $\xi$ is the volume fraction or particle loading fraction of slurry and $\mu _ { w a t e r }$ is function of temperature.

Thermal conductivity:

Maxwell's co-relation is used to predict static thermal conductivity of NEPCM slurry at rest. It is expressed as follows:

$$
k _ { b } = k _ { w a t e r } . \frac { 2 + \displaystyle \frac { k _ { p } } { k _ { w a t e r } } + 2 \xi \left( \displaystyle \frac { k _ { p } } { k _ { w a t e r } } - 1 \right) } { 2 + \displaystyle \frac { k _ { p } } { k _ { w a t e r } } - \xi \left( \displaystyle \frac { k _ { p } } { k _ { w a t e r } } - 1 \right) }
$$

The effects caused due to particle-particle,particlefluid and particle-wall interactions are lumped together to compute the effective thermal conductivity of slurry, specified by the following co-relation [24]:

$$
\begin{array} { l } { { { k _ { e f f } } = k _ { b } \left( 1 + B \xi P e _ { p } ^ { m } \right) } } \\ { { B = 3 , m = 1 . 5 , P e _ { p } < 0 . 6 7 } } \\ { { B = 1 . 8 , m = 0 . 1 8 , 0 . 6 7 < P e _ { p } < 2 5 0 } } \\ { { B = 3 , m = \displaystyle \frac { 1 } { 1 1 } , P e _ { p } > 2 5 0 } } \end{array}
$$

where $P { e _ { p } }$ is particle Peclet number which is defined as;

$$
P e _ { p } = \frac { e D _ { p } ^ { 2 } } { \alpha _ { w a t e r } }
$$

where $\alpha _ { w a t e r }$ is thermal diffusivity of water and $e$ is shearrate,whichisa functionof spatial coordinatesand corresponding velocities.Shear rate can be expressed as follows:

$$
e = \left( { \frac { 1 } { 2 } } \sum _ { i } \sum _ { j } \gamma _ { i j } \gamma _ { j i } \right)
$$

Heat Capacity:

$$
C _ { p , e f f } = ( 1 - c _ { m } ) C _ { p , w a t e r } + c _ { m } C _ { p , p }
$$

Where $C _ { p , \ w a t e r }$ and $C _ { p , p }$ are specific heat capacity of water and NEPCM particle. Alisetti and Roy [25] suggested that the difference between various profiles for calculating the specific heat capacity of NEPCM particle is less than $4 \%$

![](images/1051a51b2460e08631139df2439807fc6277e5a6e75573d8ea617a879b0fd656.jpg)  
Fig.2Sine profile of specific heat capacity model

Therefore,sine profile is used in the present study to predict the specific heat capacity of NEPCM particle as illustrated in Figure 2.The melting process starts when the temperature ofNEPCM particle reaches $\mathrm { T } _ { 1 }$ (solidus temperature） and terminates at $\mathrm { T } _ { 2 }$ (liquidus temperature). Furthermore, $\mathrm { T _ { M r } }$ and $\mathrm { { T } _ { m } }$ are the melting range and meltingpoint of NEPCM particle.When the temperature is below and above the melting range, specific heat capacity of particle is given by $C _ { p , p c m }$ . While, for the temperature in the melting range; the specific heat capacity is given by:

$$
C _ { p , p } = C _ { p , p c m } + \left\{ \frac { \pi } { 2 } . \left( \frac { h _ { l s } } { T _ { M r } } - C _ { p , p c m } \right) . \sin { \pi \left[ \frac { \left( T - T _ { 1 } \right) } { T _ { M r } } \right] } \right\}
$$

More details about co-relation utilization in the present study are given in the specified references.

# Numerical procedure and boundary conditions

A commercial computational fluid dynamics (CFD) code FLUENT [26] has been employed in the present study as numerical solver. The three-dimensional governing equations of continuity, momentum and energy are discretized by the finite volumemethod.The convection/diffusion terms present in momentum and energy equations are discretized with QUICK scheme.Further, SIMPLE algorithm is employed in the numerical solver to provide a coupling between velocity and pressure.

The three-dimensional computational grid is displayed in Figure 3.A commercial grid generating software Gambit is used to divide the computational domain into small hexahedral elements in both fluid and solid domains.A relatively fine grid is adopted in the local domain near the impingement surface,where the solid liquid interface occurs for conjugate heat transfer boundary condition. Coarse grid is used in the rest of domain.

![](images/c47041b165ad77aa0f7eeffeba8bf025cf6ac41c5f2acd1ef7a490fda614af80.jpg)  
Fig.3Three-dimensional computational grid design

Numerical solution is terminated when convergence has been ensured at a particular iteration.To check if the convergence is achieved the summation of absolute valuesof relative errors(i.e.Residuals) of pressure,velocity components and temperature falls below $1 0 ^ { - 5 }$ ， $1 0 ^ { - 6 }$ and $1 0 ^ { - 8 }$ ，respectively. Furthermore, the Nusselt number and temperature values at stagnation point are also checked as a second criteria of convergence.

The assigned boundary conditions are as following: Inlet boundary condition:

$$
w = - V _ { j } , \ : \ : \ : u = \nu = 0 , \ : \ : \ : T _ { f } = T _ { j }
$$

Outlet boundary condition:

$$
\frac { \partial u } { \partial x } = \frac { \partial \nu } { \partial x } = \frac { \partial w } { \partial x } = \frac { \partial T _ { f } } { \partial x } = 0
$$

Bottom wall heat flux boundary condition:

$$
{ \dot { q } } = { k _ { s } } \frac { { \partial { T _ { s } } } } { { \partial z } }
$$

Solid-Liquid interface boundary condition:

$$
k _ { s } \frac { \partial T _ { s } } { \partial n } = k _ { f } \frac { \partial T _ { f } } { \partial n }
$$

Confinement top and other walls:

$$
k _ { s } \frac { \partial T _ { s } } { \partial n } = k _ { f } \frac { \partial T _ { f } } { \partial n } = 0
$$

# Grid independency and model verification

The grid sensitivity of numerical model was examined by considering four grid sizes of 134,872 (coarse), 369,700 (medium),876,732 (fine) and 1,798,236 (very fine).Grid independency test was conducted for worst Reynolds number and water is used as a working fluid. The test results predicted that numerical solution become grid independed at fine grid and maximum deviation of stagnation Nusselt numbers and pressure drops among fine and very fine grids is below $3 \%$ .Therefor,fine grid with 876,732 elements is appropriate enough to capture heat and flow characteristics precisely.

To the best knowledge of the author,no published experimental data is present in the literature related to confined slot jet impingement cooling systems working in laminar regime.Therefore,in order to ensure the code validity and solution reliability, the numerical simulation is conducted with the same geometrical and operating parameters as presented in Di Lorenzo [12]. In this validation test,water will be taken under consideration as a coolant. Furthermore,a constant temperature of 313K is maintained at the impingement surface,while all other surfaces are insulated in solid domain.The fluid jet tem perature was kept at 292K.Further details regarding the numerical models and procedures can be found in the original articles [9] and [12].

The validation of the present model is illustrated in Figure 4 which predicts the Nusselt numbers at stagnation point. The maximum deviation found is below $20 \%$ which show good agreement as Nusselt number calculations are extremely sensitive regarding grid size and design.

![](images/a9ab250c48434a48945a3a424e7b8f99a636082730341ec0e3a6b8bda7e128b4.jpg)  
Fig.4Verification of present study with past numerical models

# Results and discussion

Numerical simulation is carried out to evaluate thermal and hydrodynamic characteristics of confined slot jet impingement in laminar regime by using NEPCM slurry as coolant. The effects of Reynolds numbers varying from 1Oo to 6Oo are taken under consideration.The ranges of NEPCM particles mass concentration $\left( \mathrm { C } _ { \mathrm { m } } \right)$ and nozzle to plate distance (H/W） are $C _ { \mathrm { m } } { = } 0 \mathrm { ~ - ~ } 0 . 2 8$ and $\mathrm { H } / \mathrm { W } { = } 4 \ - \ 6$ ，respectively.The results are analyzed and reported in terms of Nusselt number, heat transfer coefficient, pressure drop,and bulk fluid temperature.

Figure 5 illustrates the effects of mass con-centrations of NEPCM particles in slurry on bulk fluid temperature at different Reynolds number and constant nozzle to plate distance.As seen,using NEPCM slurry as a coolant reduces the bulk temperature of the fluid in comparison with water. In addition, increasing the mass concentration of NEPCM in slurry reduces the bulk fluid temperature considerably.Thisis due to the fact thataddingNEPCM capsules to the base fluid increase the effective heat capacity of the coolant,which further enhance thermal energy storage capabilitywithlittle rise ofbulk fluid temperature.An additional observation is that,with increasing Reynolds number, the fluid bulk temperature de creases and heat transfer enhancement takes place.This can be explained with the basic theory that at low Reynolds number, fluid flows slowly over the impingement surface, thus having much more time to absorb heat. Therefore,diffusion is the only source for heat transfer resulting in higher bulk fluid temperature.Apart from this,at higher Reynolds number,associated velocities increasedandforcedconvectionbecomedominant factor for heat transfer. Hence, in this case more heat will be transferred with little rise in the bulk temperature of fluid.

![](images/0812c3506840618e2f402d7f54c66e5382ac65267d6e1f2381c642c385533df0.jpg)  
Fig.5Effect of NEPCM particle concentration on bulk fluid temperature

Figure 6 shows velocity stream lines of impinging coolant in three-dimensional domain.The fluid jet shows a sudden suppression in velocity just before hitting the heated surface.This velocity reduction tends to increase the static pressure by converting kinetic energy of partially stagnated coolant to potential energy. Therefore, stagnation zone corresponds to high static pressure.

The temperature distributions in fluid domain are shown in Figure 7 for water and NEPCM slurry with different mass concentrations.As expected,for all the cases，thermal boundary layer is relatively thinner at stagnation zone as compared to the area near the outlet. This is primarily due to the fact that, strong temperature gradients exists at stagnation zone as indicated by denselypacked isotherms.Temperature gradients decreases away from the stagnation zone,where thick boundary layer is present.

This means that, higher heat transfer rates will be found at stagnation zone.It is also evident from Figure 7 that the thermal boundary layer grows slowly across the copper plate for NEPCM slurry as compared to water as coolant. This is mainly because oflatentheat storage ofNEPCM capsules suspended in water. Another important result shown in Figure 7 is that the thermal boundary layer thickness reduces as the mass concentration of NEPCM increases in base fluid at a fixed Reynolds number and nozzle to plate distance.It can be observed that thermal layerof water is more thick than the slurry with $\mathrm { C } _ { \mathrm { m } } { = } 0 . 2 8$ Therefore, this reduction in boundary layer thickness will enhance heat transfer due to establishment of strong temperature gradients across the copper plate in thermal boundary layer region.

Figure 8 depicts the effects of nozzle to plate distance (H/W) on stagnation point Nusselt number with jet speed variation at a constant NEPCM concentration.This also holds true for other mass concentrations of NEPCM particles in slurry.It is observed that the Nusselt number at stagnation point increases with jet speed at a particular nozzle to plate distance.In addition,as H/W increases slightly for a fixed jet speed,the stagnation Nusselt number decreases considerably. This effect is more prominent at high jet speeds,for example at $0 . 1 \mathrm { { \ m / s } }$ .The common conclusion is that the confined jet impingement cooling systems working at low nozzle to plate distance is more beneficial for heat transfer enhancement.

![](images/8472a9ad620c5da5047642e7ebbcc0a183e24ea39f9317cd133a1d3172fadc60.jpg)  
Fig.6Slot jet impingement 3D velocity streamlines

![](images/9868cf0a2d9cb95a1c1a872aba9e05370217874769a94359b4c297e421ba6aa3.jpg)  
Fig.7Effect ofNEPCM mass concentration on thermal boundary layer

![](images/6346ed6124b6148c972a2cc67e3b3ac80f0289fefafe7ddd6b31324d992bcd25.jpg)  
Fig.8Effect of Nozzle to plate distance on Nusselt number at stagnation point

![](images/78ea694c8df611e7c6d82eb7bae2cff73c2f7bbf03dfc52abe01f56a1a33ab63.jpg)  
Fig.9Average heat transfer coefficient as a function of NEPCM concentration

In Figure 9, the average heat transfer is plotted against the Reynolds number for various slurry concentrations at $\mathrm { H } / \mathrm { W } { = } 4$ 、It shows that heat transfer from the impingement surface is highly affected byusing NEPCM slurry instead of water as coolant.Predicted trend shows an enhancement of heat transfer coefficient with increase of jet Reynolds number and NEPCM mass concentration.This enhancement is basically a result of high thermal heat capacity of the slurry.A significant heat transfer improvement is found at NEPCM $C _ { \mathrm { m } } { = } 0 . 2 8$ as compared with water. Another important point to be discussed is that the average heat transfer co-eficient increases as Reynolds number increases for all considered cases.

The pressure drop between the nozzle exit and outlet of confined slot jet impingement systems for varying Reynolds numbers is illustrated in Figure 10 at $\mathrm { H } / \mathrm { W } { = } 4$ It is obvious that at higher Reynolds number, system exhibits a significantly higher pressure drops. Moreover, pressure drop in system is extremely sensitive with NEPCM concentration. This is due to the fact that higher NEPCM concentrations in the base fluid results in higher effective viscosity of coolant which,in consequence increase pressure drops and pumping power of the system. The pressure drop recorded for NEPCM $C _ { \mathrm { m } } { = } 0 . 2 8$ at $\scriptstyle \mathrm { R e = } 6 0 0$ is the worst scenario in the present model. Therefore, it is highly recommended that the higher pressure drops associated with high concentration of NEPCM particles at higher Reynolds number should be considered carefully for designing a confined slot jet impingement system with NEPCM slurry as coolant.

![](images/66643073743cf7feff580c1798c640a7e731625811971c3c7b874ee290aa4ca4.jpg)  
Fig. 10 Effects ofReynold numbers and NEPCMconcentration on pressure drop

# Conclusion

The cooling performance and hydrodynamic features of NEPCM slurry were compared with that of water, used inside the confined slot jet impingement system as coolants.The effects of jet Reynolds number, jet to plate spacing and mass concentration of NEPCM particles on heat transfer coefficient,pressure drop and fluid bulk temperature were discussed. A good agreement was found between the present results and previous numerical works.Analysis predicted that adding NEPCM particles in the base fluid helps in improving the Nusselt number and decrease the bulk temperature of fluid.It was also found that the thermal performance of the system highly depends on the jet to target spacing.For the Reynolds number considered,an increase in mass concentration above O.2 results in very little heat transfer enhancement. However, the associated pressure drop will increase drastically which,in consequence,will reduce the total efficiency of the system.Therefore,the present findings are expected to provide guidelines in designing and optimizing the confined slot jet impingement cooling systems using NEPCM slurry as a working fluid in the near future.

# Acknowledgments

This study was supported by the National Natural Science Foundation of China (No.51322604).

# References

[1]Di Lorenzo, G.,Manca, O., Nardini, S.,and Ricci, D., "Laminar confined impinging slot jets with nanofluids on heated surfaces," Proc. Thermal Investigations of ICs and Systems (THERMINIC),2011 17th International Workshop,Paris,France,pp.1-6.   
[2]Basaran，A.，and Selimefendigil,F.，2013,"Numerical study of heat transfer due to twinjets impingement onto an isothermal moving plate," Mathematical and Computational Applications,18(3), pp. 340-350.   
[3]Manca, O., Mesolella,P., Nardini, S.,and Ricci, D.,2011, "Numerical study of a confined slot impinging jet with nanofluids," Nanoscale Research Letters, 6.   
[4]Lee, H. G, Yoon, H. S.,and Ha, M.Y.,2008, "A numerical investigation on the fluid flow and heat transfer in the confined impinging slot jet in the low Reynolds number region for diferent channel heights," International Journal of Heat and Mass Transfer, 51(15-16),pp.4055- 4068.   
[5]Behnia, M., Parmeix, S., Shabany, Y.,and Durbin, P. A., 1999,"Numerical study of turbulent heat transfer in confined and unconfined impinging jets," International Journal of Heat and Fluid Flow, 20(1), pp.1-9.   
[6]Huang,J.-B.，2013,，"Numerical Study of a Confined Axisymmetric Jet Impingement Heat Transfer with Nanofluids," Engineering, O5(01), pp. 69-74.   
[7]Gao,N.,and Ewing,D.,2006,"Investigation of the ffect of confinement on the heat transfer to round impinging jets exiting a long pipe," International Journal of Heat and Fluid Flow, 27(1), pp. 33-41.   
[8]Choo,K. S.,and Kim, S.J., 2010,"Comparison of thermal characteristics of confined and unconfined impinging jets,"International Journal of Heat and Mass Transfer, 53(15-16), pp. 3366-3371.   
[9]Lin,Z.H., Chou,Y.J.,and Hung,Y.H., 1997, "Heat transfer behaviors of a confined slot jet impingement," International Journal of Heat and Mass Transfer, 40(5), pp. 1095-1107.   
10]Park,T.H., Choi, H. G, Yoo,J.Y.,and Kim, S.J.,2003, "Streamline upwind numerical simulation of two-dimensional confined impinging slot jets," International Journal of Heat and Mass Transfer, 46(2), pp.251-262.   
11] Baydar,E.，1999, "Confined impinging air jet at low Reynolds numbers," Experimental Thermal and Fluid Science,19(1), pp.27-33.   
12]Di Lorenzo,G.,Manca,O.,Nardini, S.,and Ricci,D., 2012,"Numerical Study of Laminar Confined Impinging Slot Jets with Nanofluids," Advances in Mechanical En gineering.   
[13]Wu,W., Chow,L. C., Wang, C.M., Su, M.,and Kizito,J. P.,2014, "Jet impingement heat transfer using a Field's alloy nanoparticle - HFE71oo slurry," International Journal ofHeat and Mass Transfer, 68,pp.357-365.   
[14]Wang,S.,and Zhang,Y.,20o8,"Forced-Convection Heat Transfer of Microencapsulated Phase-Change Material Suspensions Flow in a Circular Tube Subject to External Convective Heating," Journal of Enhanced Heat Transfer, 15(2),pp. 171-181   
[15]Liu, C., Rao,Z., Zhao,J.,Huo, Y., and Li, Y., 2015, "Review on nanoencapsulated phase change materials: Preparation,characterization and heat transfer enhancement," Nano Energy,13,pp.814-826.   
[16]Sabbah,R., Seyed-Yagoobi,J.,and Al-Hallaj, S.,2011, "Heat Transfer Characteristics of Liquid Flow With Micro-Encapsulated Phase Change Material: Numerical Study," Journal of heat transfer,133(12),pp.121702- 121702.   
[17]Lu,H.,Seyf,H.R.,Zhang,Y.,and Ma,H.B.,2015, "Heat Transfer Enhancement of Backward-Facing Step Flow by Using Nano-Encapsulated Phase Change Material Slurry,"Numerical Heat Transfer,Part A:Applications,67(4), pp.381-400.   
[18]Rajabifar,B.,2O15,"Enhancement of the performance of a double layered microchannel heatsink using PCM slurry and nanofluid coolants," International Journal of Heat and Mass Transfer, 88,pp. 627-635.   
[19]Seyf, H. R., Zhou, Z., Ma, H. B.,and Zhang, Y., 2013, "Three-dimensional numerical study of heat-transfer en

hancement by nano-encapsulated phase change material slurry in microtube heat sinks with tangential impingement,"International Journal of Heat and Mass Transfer, 56(1-2), pp.561-573. [20]Wu,W.,Bostanci,H.,Chow,L.C.,Ding, S.J.,Hong,Y., Su,M.,Kizito,J.P., Gschwender,L.,and Snyder, C.E., 2011,"Jet impingement and spray cooling using slurry of nanoencapsulated phase change materials," International Journal of Heat and Mass Transfer,54(13-14), pp.2715- 2723. [21]Zhang，Y.,and Faghri，A.，1995,"Analysis of forced convection heat transfer in microencapsulated phase change material suspensions,"Journal of Thermophysics and Heat Transfer, 9(4),pp. 727-732. [22]Kuravi, S.,Kota,K.M.,Du, J.,and Chow,L. C., 2009, "Numerical Investigation of Flow and Heat Transfer Performance of Nano-Encapsulated Phase Change Material Slurry in Microchannels," Journal of heat transfer, 131(6), p. 062901. [23]Vand,V.,1948,"Viscosity of Solutions and Suspensions. I. Theory,"The Journal ofPhysical and Colloid Chemistry, 52(2),pp.277-299. [24]Sabbah,R., Seyed-Yagoobi, J.,and Al-Hallaj,S.,2012, "Natural Convection With Micro-Encapsulated Phase Change Material," Journal of heat transfer, 134(8)，pp. 082503-082503. [25]Alisetti,E.L.,and Roy, S.K.,20oo,"Forced Convection Heat Transfer to Phase Change Material Slurries in Circular Ducts," Journal of Thermophysics and Heat Transfer, 14(1),pp. 115-118. [26]Fluent 14.5:User's Guide,Fluent Inc.,2012.