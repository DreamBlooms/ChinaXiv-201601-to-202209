# Numerical Visualization of Air Intake Induced by Free Surface Vortex

Young Kyu Park1, Mohan Kumar Dey², Yoon Hwan Choi1 and Yeon Won Lee³

1.Research Institute of Industrial Science & Technology,Pukyong National University, Busan, Korea 2.InterdisciplinaryProgramofBiomedical,Mechanical,andElectrical Enginering,Pukyong National UniversityBusan, Korea 3. Department of Mechanical Design Engineering, Pukyong National University, Busan, Korea

Free surface vortex control is vital in a pump sump system because the air absorbed by free surface vortex induces noise,vibration,and cavitation corrosion on the pumping system.Inthis study,the change offree surface vortex and air absorption in a pump intake has been investigated by the Volume ofFraction (VOF） method with steady multiphase flow model in order to represent the behavior of the free surface vortex exactly.The homogeneous free surface model is used to apply interactions of air and water.The results show that air intake by the free surface Vortex motion can be visualized using the iso-surface of air volume fraction.The vortices make an air column from the fre surface to the pump intake.Also,it was found thatthe free surface vortex canbe controlled by installing curtain walls.

Keywords: free surface vortex, numerical visualization, curtain wall, air intake

# Introduction

Pumps are extensively used in cooling water system for electrical power plants. Good design of a pump sump is needed for pumping efficiency. However, sump design has been influenced by field conditions and economic costs.Poor sump structures lead to serious problems causing vortex. There are two types of vortex,free surface vortex in the approaching flow and submerged vortex induced on the walls.Free surface vortex is generated on the free surface and then absorbs air into the suction pipe of the pump.Such vortices induced by fluid flow on the free surface and walls can reduce pump efficiency or damage the impeller.

Computational Fluid Dynamics (CFD） using numerical approach is widely used to solve fluid flow and heat transfer. The results are worth and reliable,both in fluid flow and heat transfer analysis. Therefore many researchers have analyzed fluid flow near the pump intake. Nagahara et al. compared the PIV experiment of velocity near the submerged vortex and CFD results [1]. Rajendran et al.simulated three-dimensional turbulent flow including a vertical tailpipe inside a square channel and compared it with experimental results [2].Padmanabhan and Hecker defined the shape of vortex which occurred near the tailpipe and classified it according to Froude number [3]. Okamura et al. used many CFD programs to solve the problem and analyzed the differences of the results [4,5]. Chuang et al. calculated swirl angle from Vorticities of cross section at the height of swirl meter [6]. Verhaart et al. constructed Anti Vortex Device (AVD) models and compared the velocity of inlet at suction pipe with respect to AVD dimensions [7]. Park et al. studied the change of free surface vortex according to various intake conditions [8].

In this study, the behavior of air intake caused by free surface vortex in the pump sump has been mainly investigated using CFD.Numerical visualization technique with the aid of VOF method was adopted to express clearly the air absorption process induced by surface vortex.Also, the function of a curtain wall to control the free surface vortex is studied.

# Numerical analysis

# Governing equation

The governing equations used to analyze the flow field

of pump sump are the continuity equation and the Navier-Stokes equation with standard $k { - } \varepsilon$ turbulence model. The equations are as follows:

Continuity equation:

$$
\frac { \partial \rho } { \partial t } + \frac { \partial \rho u _ { i } } { \partial x _ { i } } = 0
$$

Momentum equation:

$$
\begin{array} { r l } & { \frac { \displaystyle \partial \big ( \rho u _ { i } \big ) } { \displaystyle \partial t } { + \frac { \partial \big ( \rho u _ { i } u _ { j } \big ) } { \partial x _ { j } } } } \\ & { = \rho f _ { i } - \frac { \displaystyle \partial p } { \displaystyle \partial x _ { i } } { + \frac { \partial } { \partial x _ { j } } \Bigg [ \big ( \mu + \mu _ { t } \big ) \Bigg ( \frac { \displaystyle \hat { \alpha } u _ { i } } { \displaystyle \hat { \alpha } x _ { j } } { + \frac { \partial u _ { j } } { \partial x _ { i } } } \Bigg ) \Bigg ] } } \end{array}
$$

$k$ equation:

$$
\frac { \hat { \sigma } \big ( \rho k \big ) } { \hat { \sigma } t } + \frac { \hat { \sigma } \big ( \rho u _ { j } k \big ) } { \hat { \sigma } x _ { j } } - \frac { \hat { \sigma } } { \hat { \sigma } x _ { j } } \Bigg [ \Bigg ( \mu + \frac { \mu _ { t } } { \sigma _ { k } } \Bigg ) \frac { \hat { \sigma } k } { \hat { \sigma } x _ { j } } \Bigg ] = G _ { k } - \rho \varepsilon
$$

$\varepsilon$ equation:

$$
\frac { \partial \left( \rho \varepsilon \right) } { \partial t } + \frac { \partial \left( \rho u _ { j } \varepsilon \right) } { \partial x _ { j } } - \frac { \partial } { \partial x _ { j } } \Bigg [ \Bigg ( \mu + \frac { \mu _ { t } } { \sigma _ { \varepsilon } } \Bigg ) \frac { \partial \varepsilon } { \partial x _ { j } } \Bigg ]
$$

$$
= \frac { \varepsilon } { k } \big ( C _ { \varepsilon 1 } G _ { k } - \rho C _ { \varepsilon 2 } \varepsilon \big )
$$

where $u _ { i } ( i { = } 1 , 2 , 3 )$ is the velocity component in the $i$ direction; $f _ { i }$ is the quality forces in the $i$ direction; $p$ is pressure, $\rho$ is fluid density, $\mu$ is fluid viscosity; $G _ { k }$ ，the production of $k$ ,is given by

$$
G _ { k } = u _ { t } \left( \frac { \hat { \alpha } u _ { i } } { \hat { \alpha } x _ { j } } + \frac { \hat { \sigma } \rho u _ { i } } { \hat { \alpha } x _ { j } } \right) \frac { \hat { \alpha } u _ { i } } { \hat { \alpha } x _ { j } } \nonumber
$$

Where, $\mu _ { t }$ is the eddy viscosity:

$$
\mu _ { t } = \rho C _ { \mu } \frac { k ^ { 2 } } { \varepsilon }
$$

The $k { - } \varepsilon$ model coefficients are adopted as following

$C _ { \mu } { = } 0 . 0 9$ $\sigma _ { k } { = } 1 . 0$ $\sigma _ { \varepsilon } { = } 1 . 3$ ， $C _ { \varepsilon 1 } { = } 1 . 4 4$ ， $C _ { \varepsilon 2 } { = } 1 . 9 2$

In this study, the homogeneous model for multiphase flow analysis is applied. The density and physical quantity are represented by the volumetric ratio of multiphase flow on each of the working fluids.

$\rho , U ,$ ，┌are definedasfollows

$$
\rho = \sum _ { \alpha = 1 } ^ { N _ { P } } \gamma _ { \alpha } \rho _ { \alpha }
$$

$$
U = \frac { 1 } { \rho } \sum _ { \alpha = 1 } ^ { N _ { P } } \gamma _ { \alpha } \rho _ { \alpha } U _ { \alpha }
$$

$$
\Gamma = \sum _ { \alpha = 1 } ^ { N _ { P } } \gamma _ { \alpha } \Gamma _ { \alpha }
$$

Each fluid $\gamma _ { 1 } , \gamma _ { 2 } , . . . , N _ { p }$ is the total number of phases. Volume fraction, density, velocity, diffusion coefficient of each fluid are $\gamma _ { a } , \rho _ { \alpha } , U _ { a } , \Gamma _ { a } ,$ respectively. $ { \boldsymbol { a } }$ represents the total phase.

# Computational domain and boundary conditions

Fig.1 shows the computational domain of pump sump model used in the numerical analysis.This study is referenced by the model proposed by Okamura et al.[5]. Three-dimensional modeling,grid generation and computational model calculations were performed on this model.All dimensions were based on the outside diameter (D) at inlet of suction pipe.

Analysis software used for this purpose is ANSYS CFX-16.2,the number of grids used are $0 . 8 { \sim } 1 . 1$ million nodes,after checking the grid independency, steady calculations were performed. Homogeneous multiphase flow model is applied in order to implement the multi-phase flow of air and water, expressed as the volumetric ratio of the volume of fluid.On the inlet boundary condition, the pressure condition $\scriptstyle \mathtt { p } = \rho g \mathrm { h }$ was applied - using CFX user function(expression）- to express the pressure gradient according to water level.Outlet boundary is applied for the flow rate condition.

Flowrateandwaterlevel arecloselyrelatedto the vortex creation.If the flow rate is too high, then the wa ter level should be increased in order to prevent vortex occurrence.Therelationship between flowrate andwater levelisexpressedas

$$
\mathrm { S } { = } \mathrm { D } ( 1 . 0 { + } 2 . 3 F _ { D } )
$$

where S is the minimum water level, $F _ { D }$ is Froude number.Minimum water level S is the standard height to prevent the free surface vortex without any additional constructions [9].

The parameters for the water levels and flow rates are given in Table 1. For case 1, free surface vortices occur usually[5].Hence,case 1 was adopted to describe the numerical visualization of air intake induced by free surface vortex.In case 2,curtain wall is used to control the free surface vortex. The dimensions and location of the curtain wall are based on the HI Standard recommendations. Case 2 is used to check the effects of the curtain wall.

Table 1 Operating conditions of numerical model   

<html><body><table><tr><td></td><td>Flow rate (m³/h)</td><td>Water level (mm)</td><td>Curtain wall</td></tr><tr><td>Case 1</td><td>135</td><td>3.75D</td><td>No</td></tr><tr><td>Case 2</td><td>135</td><td>3.75D</td><td>Yes</td></tr></table></body></html>

# Results and discussion

# Free surface vortex visualization by the Volume Fraction method

For case 1 and 2, the real fluid flow is $1 3 5 ~ \mathrm { m ^ { 3 } / h }$ but $F _ { D }$ is based on $6 0 ~ \mathrm { m } ^ { 3 } / \mathrm { h }$ .Therefore,cases1 and2 are both severe water level conditions and hence it is easy to create free-surface vortices.

![](images/11e7efceeca2edc9b9203a9cde9b67737ea61b9ab17bb1511b1f671a8f31e2d6.jpg)  
Fig.1 Computational domain of pump sump model for numerical analysis

Fig.2 shows the streamline near suction pipe for case 1.The Free-surface vortex is identified at both sides of the suction pipe (Fig 2(a)) and it can be seen that the flow near the suction pipe inlet and free surface are connected to each other (Fig 2(b)). This flow is called free-surface vortex and it consists of mostly water and small parts of air bubble.For visualization of air intake induced by free-surfacevortex, airvolumefraction hasbeen checked.

Fig.3 indicates the vorticities and iso-surface of air volume fraction from $5 \%$ to $0 . 1 \%$ .When the volume fraction ratio of air is more than $5 \%$ ,vortex is not visualized;when the volume fraction is at $1 \%$ ，thefree surface vortex is observed and if less than $1 \%$ ，itcan be clearlyobserved from the free surface towards the inlet pipe of the pump making the air-water column as shown in Fig 3 (c) and (d).

In other words,when using the homogeneous model, the free surface vortices are expressed at the region of specific volume fraction by changing the air volume fraction factor.Free surface vorticities are observed for the case when air or water volumetric ratio is $5- 0 . 1 \%$ air and $9 5 . 9 9 . 9 \%$ water.

Fig.4(b) shows the side view streamline around the suction pipe with curtain wall for case 2.Flow near the free surface is blocked by the curtain wall and it is separated into upstream and downstream unlike Fig.4(a).The downstream flow flows to inlet of the suction pipe directly and rapidly. Due to the curtain wall, upstream flow makes recirculation zones under the free surface.These two flows are independent and the direction of movement isopposite to each other. Therefore，the vertical flow creating column from free surface to the inlet of suction pipe does not exist. The result can be shown through vortex visualization byair volume fraction.

![](images/823d0a392f5af63e9e10adfbd88ed2c3b237e543dff6fd3667b17796f1602f49.jpg)  
Fig.2Streamline near suction pipe for case

# Effectofcurtainwallforairintake

Curtain wall is a kind of AVD that is installed to control free-surface vortices in severe cases.Curtain walls are of various shapes,but the vertical type is widely used. The curtain wall used in case 2 is also of the vertical type and its dimension specifications are determined from the HI standard [9].However, the dimension of 1.OD is used as the depth of the curtain wall,instead of O.5 of the recommended dimension from HI standard,as Pyo Y.S. proposed that 1.OD is a more reasonable depth in order to control the free surface vortex [10].

Fig. 4(b) shows the side view streamline around the suction pipe with curtain wall for case 2.Flow near the free surface is blocked by the curtain wall and it is sepa rated into up and downstream unlike Fig. 4(a).The downstream flows to inlet of the suction pipe directly and rapidly. Due to the curtain wall, upstream flow makes recirculation zones under the free surface.These two flows are independent and the movement of direction is opposite to each other. Therefore,the vertical flow creating column from free surface to the inlet of suction pipe does not exist. The result can be shown through vortex visualization by air volume fraction in Fig.5(a).

Fig.5 shows the effect of the presence of the curtain wall for air intake with $0 . 1 \%$ air volume fraction comparing vorticities and iso-surfaces.For the case of no curtain wall as shown in Fig.5 (a), it can be seen that, the vortex flow move towards the inlet pipe of the pump from the free surface, thus creating air water column.In the case of Fig.5 (b),there is no strong vertical flow creating air-water column from free surface to the inlet of the suction pipe due to the presence of a curtain wall.

![](images/c0fa5181e3acc11307f832a06b6dfe501ef72476995861536dc8e2cee4007dab.jpg)  
Fig.3Air intake induced by free surface vortex

![](images/3beae09de067400fd08cc60cfd616883060282024f109e2ca28e51ad292e3bdc.jpg)  
Fig.4Comparison of streamline between no curtain wall and with curtain wall

3)Inorder to remove free surface vortex,the vertical flow created from free surface to the inlet of suction pipe has to be controlled. Curtain wall installation is a good choice for removing this vertical flow.

# Acknowledgement

This is the modified version of the paper presented in the $6 ^ { \mathrm { t h } }$ Asian Joint Workshop on Thermophysics and Fluid science.

This research was supported by “BK21 Plus project" and “Human Resources Program in Energy Technology" of the Korea Institute of Energy Technology Evaluation and Planning (KETEP),granted financial resource from the Ministry of Trade,Industry & Energy,Republic of Korea.(No.20164010200940)

# References

![](images/32dffe8ec6319a7460180220f664d56a16b6971a74b6f9795117206d9d5abe48.jpg)  
Fig.5Effect of curtain wall forair intake

A numerical visualization technique using iso-surface of air volume fraction has been applied for a better understanding of the air intake mechanism. The numerical results show that using the iso-surface of air volume fraction, the air intake by the free surface vortex motion can be visualized. The vortices make an air column from the free surface to the pump intake.Also, it was found that the free surface vortex can be controlled by installing curtain walls.

# Conclusions

The locations and behavior of free surface vortices have been studied in a pump sump using multi-phase flow simulation with steady condition. Numerical visualization technique with the aid of VOF method was adopted to express clearly the air absorption process induced by surface vortex.The conclusions are as follows:

1）Air intake induced by free surface vortex can be clearly visualized by expressing the streamlines and the iso- surface of constant air volume fraction.

2) It reveals that free surface vortex can be controlled by installing the curtain wall.

[1]Nagahara, T.， Sato,T.,Okamura, T.,and Iwano,R.: Measurement of the Flow around the Submerged Vortex Cavitation in a Pump Intake by Means of PIV, In Fifth International Symposium on Cavitation, Osaka, Japan, pp.1-7,(2003).   
[2]Rajendran, V.P., Constantinescu, G. S.,and Patel, V. C.: Experiments on flow in a model water-pump intake sump to validate a numerical model,In ASME Fluids Engineering Division Summer Meeting,Vol.6, USA:Washington DC, (1998).   
[3]Padmanabhan, M.，and Hecker, G. E.: Scale effects in pump sump models, Journal of Hydraulic Engineering, Vol.110, No.11, pp.1540-1556, (1984).   
[4]Okamura, T.,and Kanemoto,K.: CFD simulation of flow in model pump sumps for detection of vortices, ${ 8 } ^ { \mathrm { t h } }$ Asian International Fluid Machinery Conference， Yichang, China, (2005).   
[5]Okamura, T., Kanemoto, K.,and Matsui, J.: CFD prediction and model experiment on suction vortices in pump sump,9th Asian International Fluid Machinery Conference, Jeju,Korea, (2007).   
[6]Chuang, W.L., Hsiao, S. C., and Hwang, K. S.: Numerical and experimental study of pump sump flows,Mathematical Problems in Engineering,Article ID 735416,(2014).   
[7]Verhaart, F.I. H., Zwanenburg, S. A. A.,and de Fockert, A.: The results of a detailed measurement campaign on the effect of modifications to the pump compartment on spatial velocity profiles in vertically submersible pumps, Earth and Environmental Science,Vol.22,No.3,(2014).   
[8]Park, Y.K., Li,K.M., Choi, Y.H., and Lee,Y.W.: A Study on the Change of Free Surface Vortex according to Intake Conditions in the Pump Sump,Journal of the Korean Society of Visualization，Vol.9，No.4，pp.74-79, (2011). (in Korean)   
[9]Hydraulics Institute Standards,Centrifugal,Rotary and Reciprocating Pumps,HIS,Cleveland, Ohio,USA,15th edition,(2012).   
10]Pyo,Y.S.: Free Surface Vortex Flow Control around Pump Intake with Curtain Wall Installation,M.S. thesis, Pukyong National University, Busan,Korea, (2014).