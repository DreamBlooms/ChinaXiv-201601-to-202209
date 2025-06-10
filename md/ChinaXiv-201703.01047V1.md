# Correlation Analysis of Transient Heat Transfer Characteristics for Air Precooling Aggregate

GUO Chaohong1, ZENG Miao1\*,LU Fei², TANG Dawei1, GUAN Wei², LI Li², FU Tingwu²

1. Institute of Engineering Thermophysics, Chinese Academy of Sciences, Beijing 1OO190, China   
2.Northwest Engineering Corporation Limited,Power Construction Corporation of China,71Oo65,China

$\circledcirc$ Science Press and Institute of Engineering Thermophysics,CASand Springer-Verlag Berlin Heidelberg 2017

In dam works,air precooling of aggregate is a common and effective method to avoid temperature cracks in concrete structure.In order to offer a reliable design theory for the air precooling process to avoid unreasonable energy consumption,the transient heat transfer characteristics of the aggregate are intensively analyzed.The combined structureof the aggregate and the interstitial space in the hopper is treatedas a porous structure,and the space-average method is used to simulate the transient heattransfer process.Simulation results show that size of the hopper and the average air velocity in the cross section have great influence on the transient heat transfer process of the aggregate,while the porosity in the range of $0 . 4 \substack { - 0 . 5 }$ has little influence. Nomograms are abstracted from simulation results,and then correlations of the compared excess temperature are precisely fited to predict the air precooling transient heat transfer process of the aggregate.

# Keywords: Air precooling,Aggregate, Transient heat transfer, Nomogram

# Introduction

The safety of the dam construction prominently depends on the temperature control of the concrete structure [1]；precooling of aggregate is an effective method to avoid temperature cracks,and iswidely used in actual concrete works.By now, the aggregate precooling process is very critical for safety and economic performance of the hydraulic and hydro-power engineering，and the research on it is extremely important.

During the air precooling process， the aggregate moves down from the feeding opening to the discharge opening in the aggregate hopper, while the cool air flows up from the air inlet to the air outlet.The whole counter flow process makes the aggregate and the air fully exchange heat in the aggregate hopper. In actual concrete engineering，analysis of the air-cooled transient heat transfer process is based on simplified equivalent conversion of the transient heat transfer characteristics for water-cooled concrete [2-4],and to avoid the engineering disqualification， excessivedesign margin isusually adopted and then makes high energy consumption.In order to offer a reliable design theory and then reasonably reduce energy consumption, it is urgent to make an intensive study of the air-cooled transient heat transfer characteristics of the aggregate.

In this paper, the aggregate and the interstitial space are combined as a porous medium,and the transient heat transfer process in the aggregate hopper is simulated by means of the porous medium model.The simulations almost cover all actual working conditions.According to the simulation data, the influences of many factors,such as the hopper construction,the porosity,the air velocity, the cooling time,etc.,are analyzed,and the transient cooling regularity of the aggregate in the hopper is deduced.

#

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>a</td><td>heat diffusivity, m²/s</td><td>T</td><td>aggregate temperature, K</td></tr><tr><td>A</td><td>fitting coefficients in Eq. (23)</td><td>Ta</td><td>air temperature, K</td></tr><tr><td>Ah</td><td>cross section area of the hopper, m²</td><td>T0</td><td>initial temperature of the aggregate, K</td></tr><tr><td>B</td><td>fitting coefficients in Eq. (23)</td><td>U</td><td>perimeter of the cross section, m average air flow velocity in cross section,</td></tr><tr><td>Bi</td><td>Biot number</td><td>u</td><td>m/s</td></tr><tr><td>C</td><td>specific heat, J/(kg·K)</td><td>ua</td><td>inlet flow velocity, m/s</td></tr><tr><td>C</td><td>fitting coefficients in Eq. (23)</td><td>Ukx</td><td>air flow velocity in interstitial space, m/s</td></tr><tr><td>d</td><td>stone diameter, m</td><td colspan="2">Greek symbols</td></tr><tr><td>D</td><td>diameter of the hopper, m</td><td>α</td><td>convectiveheattransfercoefficient, W/(m²-K)</td></tr><tr><td>Dd</td><td>effective diffusion tensor in Eq. (2)</td><td>8</td><td>Porosity</td></tr><tr><td>Fo</td><td>Fourier number</td><td></td><td>thermal conductivity, W/(m·K)</td></tr><tr><td>Fo*</td><td>fitting coefficients in Eq. (23)</td><td>μ</td><td>kinematic viscosity, kg/(m·s)</td></tr><tr><td>H</td><td>height of the arrangement unit, Fig.7</td><td>p</td><td>density (kg /m³)</td></tr><tr><td>keff</td><td>effective thermal conductivity in Eq. (2)</td><td>T Subscripts</td><td>time, s</td></tr><tr><td>L</td><td>height between two air flues,m</td><td colspan="2"></td></tr><tr><td>Pr</td><td>Prandtl number</td><td>a air</td><td></td></tr><tr><td>Q1</td><td>convection heat transfer in interstitial space,Fig.7</td><td>e</td><td>equivalent values</td></tr><tr><td>Q2</td><td>heat conduction between two adjacent stones, Fig. 7</td><td>kx</td><td> interstitial space</td></tr><tr><td>r</td><td>radius of the touch area, Fig.7</td><td>s</td><td>stone</td></tr><tr><td>R</td><td> stone radius, m</td><td>V</td><td>virtual values</td></tr><tr><td>Re</td><td>Reynolds number</td><td></td><td></td></tr></table></body></html>

# Similarity Experiment and Simulation

The rough spherical packed bed is usually treated as a porous medium composed by the rough spherical material and the interstitial space in industry [5,6].The structure composed of the aggregate and the interstitial space in the aggregate hopper is similar with that of the packed bed,and also can be treated as a porous structure.The whole transient heat transfer process of the porous medium can be simulated by CFD software,which is suitable for large stacks of particles,and the simulation results show good prediction [7, 8].

# Similarityexperiment

Owing to the testing restriction on the construction site,it is difficult to obtain comprehensive and precise testing data,so it is necessary to establish a small-scale similarity experimental system to availably analyze the transient heat transfer characteristics of the aggregate during the air cooling process.

According to the similarity criterion of the heat transfermodel,the Nusselt numberis the samewhen the heat transfer phenomenon is similar[9].The definition of the Nusselt number is: $\mathrm { \Delta N u { = } } a d / \lambda$ ，where $\scriptstyle a$ is the convective heat transfer coefficient imposed on the stone surface, and mainly depends on the Reynolds number, so with the same Re,as well as the same air flow velocity, the experimental heat transfer process can be treated similar to the actual heat transfer process in the aggregate hopper.

Figure la shows the sketch of the similarity experimental system.The cooled air is drawn into the air inlet flue of the experimental hopper by the fan，and exchanges heat energy with the stones stored in the hopper, finally flows out through the air outlet flue.The aggregate flow velocity is usually in the order of $0 . 0 0 1 \mathrm { m / s }$ in actual concrete works,and itis so small that its flow velocity can be ignored in experiments. So the stones are statically accumulated in the experimental hopper.

The experimental hopper is contracted in equal proportion according to the actual hopper, and size of it is 1 $\mathrm { m } { \times } 1 ~ \mathrm { m } { \times } 2 \mathrm { m }$ 1 $( \mathrm { X } \times \mathrm { Y } \times \mathrm { Z } )$ ,andsizeoftheairinletandoutlet holes is $0 . 1 6 ~ \mathrm { m } { \times } 0 . 1 6 ~ \mathrm { m }$ . The actual air average velocity in the hopper cross section is about $0 . 5 { - } 1 . 5 ~ \mathrm { m / s }$ ，so the convertedair volume flowrate isabout $3 0 0 0 \ \mathrm { m } ^ { 3 } / \mathrm { h }$ in the similarity experiment.As for the fan chosen in the similarity experimental system,the rated air flow is 2996 $\mathrm { m } ^ { 3 } / \mathrm { \bar { h } }$ , the maximum air pressure is $1 3 0 0 \mathrm { P a }$ , and the rated power is $2 . 2 \ \mathrm { k W } .$ The flow rate can be adjusted by the butterfly valve.Temperature of the cooled airis about $1 0 ^ { \circ } \mathrm { C }$ lower than that of the stones.The experimental subjects

![](images/f99551ed0c5f86153140a61e1d03f761440302425d351ad9c1cc4e44341a43a8.jpg)  
Fig.1Similarity experimental system

1.Buterfly valve;2.Fan;3.Speedometer;4.Airinletflue;5.Airoutlet flue;6.Experimentalaggregate hopper; 7.Thermocouples; 8.Data acquisition system; 9.Computer.

are marble stones in three sizes:G2 with diameter of 40 $\mathrm { m m } { - } 8 0 \ \mathrm { m m }$ ，G3 with diameter of $2 0 \ \mathrm { m m } ^ { - } 4 0 \ \mathrm { m m }$ ，G4 with diameter of $5 \ \mathrm { m m } ^ { - } 2 0 \ \mathrm { m m }$ . The porosity measured in experiments is $0 . 4 \substack { - 0 . 5 }$

Three-dimensional temperature field in the experimental hopper is measured by K-thermocouples;all data are recorded by the data acquisition system and then are transferred to a computer. As shown in Figure 1b,thermocouples are placed on the four cross sections in the experimental hopper. Each thermocouple adheres to surface of one stone by metal foil.There are 12 measure points regularly arranged in each cross section. Agilent 34970A Data Acquisition is used to measure and record all temperature data. All the data are simultaneously measured and recorded every 1O seconds until the experiment ends.All thermocouples have been calibrated and the absolute error is not more than $\pm 1 ^ { \circ } \mathrm { C }$ . The pitot tube is used to measure the air flow velocity,and its measure precision is $0 . 5 \%$ ：

# Simulation of the similarity experiment

The transient heat transfer process in the experiment is simulated by means of the porous medium model.There are some important assumptions that should be indicated:

1） Thermal equilibrium between the solid and the gas phases is employed in the simulations; 2) The porous domain is assumed a homogeneous region with space-averaged properties; 3） The gas phase is considered as an incompressible ideal gas; 4) The radiation between particles is ignored.

The first assumption is suitable for small particles and fluids with high heat diffusion [7,8]. In the aggregate hopper, the average air flow velocity in the interstitial space is about $1 \ \mathrm { m / s }$ and the convective heat transfer coefficient is about $1 0 \ \mathrm { w / m } ^ { 2 } \mathrm { K }$ [3],the heat diffusion is much faster than that of the natural convection or heat conduction.In addition,the influence of the stone diameter can be ignored because the interior heat resistance is smaller than the exterior convective heat resistance. TheBiot number shows the ratio of the interior conductive heat resistance and the exterior heat resistance,the influence of the diameter can be ignored if Equation(1) is valid [9]:

$$
B i = \frac { \alpha \cdot R / 3 } { \lambda } < \frac { R } { 3 }
$$

Even for one stone with bigger diameter of $8 0 \mathrm { m m }$ Equation(1) is still valid,so the influence of the diameter of the experimental stones can be ignored.

So,the assumption of the thermal equilibrium adopted in the paper is reasonable.A single space-averaged temperature is then used which can be predicted by a convection-diffusion equation (2).

$$
\frac { \partial } { \partial t } \big ( \varepsilon \rho _ { f } C _ { f } + \big ( 1 - \varepsilon \big ) \rho _ { s } C _ { s } \big ) + \vec { \nabla } \big ( \rho _ { f } \vec { u } C _ { f } \big )
$$

$$
= \vec { \nabla } \Big ( k _ { e f f } \vec { \nabla } T \Big ) + ( \rho _ { f } C _ { f } ) \ \vec { \nabla } \cdot ( \varepsilon D ^ { d } \cdot \vec { \nabla } T )
$$

where $D ^ { d }$ is an effective diffusion tensor depending on fluid velocity and taking into account the axial and radial fluid dispersion due to the solid obstacles [10].

The transient flow and cooling process in the experimental hopper is simulated by CFD method, the combined structure of the stones and the interstitial spaces is set as porous domains.About two million tetrahedral grids are meshed in the model. The boundary condition on the air inlet hole is the flow velocity measured in experiments;the boundary condition on the air outlet hole is outflow. Other input parameters like initial temperature of the cooled air,initial temperature of the stones,the porosity, are determined according to the experimental data.

Some typical experimental result and simulation result are selected to make the comparison,as Figure 2 shows.

![](images/c5bc301929809774012fde5a156d527f62f975b619c96efa53d44ebdbd6a95c6.jpg)  
Fig.2Comparison of the temperature field between the experiment and the simulation (After 2100S（G3, ${ \cal T } _ { 0 } { = } 2 3 . 4 ^ { \circ } \mathrm { C }$ ， $T _ { a } { = } 1 2 . 8 ^ { \circ } \mathrm { C }$ $u _ { a } { = } 1 3 . 8 \ \mathrm { m / s } )$ ）

The area between two dashed lines in the simulation picture corresponds to the measured area. The prediction is in good agreement with the experiment. Because of the lower air flow resistance in the inlet flue,the cooled air easily rushes to the end of the flue and then changes its flow direction to disperse into interstitial spaces,so the region near the end of the inlet flue are cooler than others.

Figure 3 compares the measured and predicted transient average temperature in two cross sections.Overall, the simulations give good results. So,all hypotheses introduced in CFD simulations are reasonable.The simulation method can be reliably used in actual air pre-cooling works.

# Influence sensitivities of working conditions

Table 1 lists change ranges of working conditions according to actual air precooling works.All 256 permutations are simulated by the CFD method mentioned above in order to analyze influences of these conditions on transient heat transfer characteristics of the aggregate. The initial temperature of the aggregate is $2 9 3 \mathrm { ~ K ~ }$ ,and the air inlet temperature is $2 7 0 \mathrm { K }$

Fig.4 shows influence of the cross section area of the hopper on transient cooling process of the aggregate. The larger the cross section area is,the higher the aggregate average temperature is.The reason is that the temperature field is more nonuniform and the stones far away from the air inlet flue are more difficult to be cooled when the cross section area becomes larger.

Fig.5 shows influence of the porosity on transient cooling process of the aggregate. When the porosity is larger,the stones can more fully touch the cooled air flowing in interstitial spaces,so the cooling rate is faster. The porosity in the range of $0 . 4 \substack { - 0 . 5 }$ has negligible influence on the aggregate transient cooling process.

Fig.6 shows influence of the air flow velocity on transient cooling process of the aggregate. The cooling rate obviously becomes faster and the average temperature of the aggregate significantly decreases when the air flow velocity increases.So the air flow velocity has great influence on the cooling process.

![](images/c1e361d44da9891df2216f7fd2338540f6cae226c6e0a2f0faba35f8fdd81271.jpg)  
Fig.3Transient average temperature in cross sections (G3)   
Fig.4Aggregate transient temperature with different crosssection area of the hopper ( $\scriptstyle { L = 5 \mathrm { ~ m ~ } }$ $u { = } 1 \ \mathrm { m / s }$ $\scriptstyle \varepsilon = 0 . 4$ ）

Table 1Actual working conditions   

<html><body><table><tr><td>Cross section area of the hopper A (m²)</td><td>10 (2.5x4)</td><td>18 (3.6x5)</td><td>24 (4x6)</td><td>30 (5x6)</td></tr><tr><td>Height between two air flues L (m)</td><td>3</td><td>3.5</td><td>4.5</td><td>5</td></tr><tr><td>Average air flow velocity in cross section u (m/s)</td><td>0.2</td><td>0.6</td><td>1</td><td>1.5</td></tr><tr><td>Porosity ε</td><td>0.4</td><td>0.43</td><td>0.46</td><td>0.5</td></tr></table></body></html>

I1 $\scriptstyle A _ { h } = 1 0 { \mathrm { ~ m } } ^ { 2 }$ ,cross section A 294 Ib1 $A _ { h } { = } 1 8 ~ \mathrm { m } ^ { 2 }$ ,cross section A CHOOOR 292 —A=24 m²,cross section A 290 — A=30 m²,cross section A 288 O— A=10 m²,cross section C [r garrrsets 286 —A=18 m²,cross section C 282 A=24 m²,cross section C 280 — A=30 m²,cross section C 278 276 274 女 Ylolabo 272 □ 270 1 0 2000 4000 6000 8000 10000 Time (s)

![](images/9447556afd2f803754443366f907b98d187153c72ebbf7aca795861f7215090e.jpg)  
Fig.5Aggregate transient temperature with different porosity 0 $\scriptstyle { L = 5 \mathrm { ~ m ~ } }$ $\scriptstyle { u = 0 . 6 \ \mathrm { m / s } }$ $\scriptstyle A _ { h } = \bar { 2 } 4 \ m ^ { 2 }$ ）

![](images/5d1d427e58771bb7e126cdb61c7256e7b4a009c2b162c035801ecd7e8d460035.jpg)  
Fig.6Aggregate transient temperature with different air flow velocity $\scriptstyle ( L = 3 . 5 { \mathrm { ~ m ~ } }$ $\scriptstyle A _ { h } = 1 8 \mathrm { ~ m } ^ { 2 }$ ， $\scriptstyle \varepsilon = 0 . 4$ $z / \delta = 0$ ,cross section A)

# Correlation Analysis of the Transient Heat Transfer Characteristics

The transient heat transfer regularity of the aggregate can be deduced according to the enormous simulation results under different working conditions.Nomogram is anavailable and convenient method to analyze the transient heat transfer process and is commonly used in engineering. Nomogram of the air precooling process of the aggregate is drawn in the paper,and the fitting correlations are suggested.

# Equivalent thermophysical properties ofthe porous structure

The structure composed by the stones and the interstitial spaces in the aggregate hopper is treated as a porous structure. The equivalent thermal conductivity $\lambda _ { e }$ is commonly determined by fluid and solid conductivity,porosity and solid structure,while the fluid convection in interstitial spaces is usually ignored [5,11,12].However, the air convection between stones is so critical in the air precooling process that it couldn't be ignored.

Fig.7 shows assumed regular arrangement of two adjacent stones. It is assumed that the heat energy transfers from the lower surface to the upper surface of the unit. The heat transfer capacity in the unit includes two parts: one is the convection heat transfer in the interstitial space; the other is the heat conduction between two adjacent stones.

![](images/e1c2d4c97de7af13024c97bb4474c724c9211328e78312f607b874572dc24cc0.jpg)  
Fig.7Arrangement unit

The convection heat transfer in the interstitial space can be calculated by Eq. (3):

$$
\begin{array} { l } { \displaystyle { { \mathcal { Q } } _ { 1 } = \int _ { r } ^ { d / 2 } \frac { \Delta T \cdot 2 \pi x d x } { \displaystyle { \frac { 2 \sqrt { \left( d / 2 \right) ^ { 2 } - x ^ { 2 } } } { \lambda _ { s } } + \frac { 2 } { \alpha _ { k x } } } } = \frac { \pi d \lambda _ { s } \cdot \Delta T } { 2 } \sqrt { 1 - \left( 2 \mathrm { r } / d \right) ^ { 2 } } } } \\ { \displaystyle { + \frac { \pi \lambda _ { s } ^ { 2 } \cdot \Delta T } { \alpha _ { k x } } \Bigg [ \mathrm { l n } \Bigg ( \frac { d } { 2 } \sqrt { 1 - \left( \frac { 2 r } { d } \right) ^ { 2 } } + \frac { \lambda _ { s } } { \alpha _ { k x } } \Bigg ) - \mathrm { l n } \Bigg ( \frac { \lambda _ { s } } { \alpha _ { k x } } \Bigg ) \Bigg ] } } \end{array}
$$

Where $\varDelta T$ is temperature difference between the lower and upper surfaces of the unit.

The heat conduction between two adjacent stones can be calculated by Eq.(4):

$$
Q _ { 2 } { = } \frac { { \pi } { r } ^ { 2 } { \cdot } { \Delta T } } { H { / } { \lambda _ { S } } } { = } \frac { { \pi } { r } ^ { 2 } { \lambda _ { S } } { \cdot } { \Delta T } } { H }
$$

So the equivalent thermal conductivity of $\lambda _ { e }$ can be deduced from Eq.(3) and Eq.(4):

$$
\begin{array} { r l } & { \lambda _ { e } = \cfrac { Q _ { 1 } + Q _ { 2 } } { d ^ { 2 } \Delta T / H } = \cfrac { \pi H \lambda _ { s } } { 2 d } \sqrt { 1 - \left( 2 r / d \right) ^ { 2 } } + \cfrac { \pi H \lambda _ { s } ^ { 2 } } { \alpha _ { k x } d ^ { 2 } } } \\ & { \quad \quad \left[ \ln \left( \cfrac { d } { 2 } \sqrt { 1 - \left( \cfrac { 2 r } { d } \right) ^ { 2 } } + \cfrac { \lambda _ { s } } { \alpha _ { k x } } \right) - \ln \left( \cfrac { \lambda _ { s } } { \alpha _ { k x } } \right) \right] + \cfrac { \pi r ^ { 2 } \lambda _ { s } } { d ^ { 2 } } } \end{array}
$$

The diameter of the touch area has little change and always closes to zero in the porosity range of $0 . 4 \substack { - 0 . 5 }$ . So Eq.(5) can be simplified as follows:

$$
\lambda _ { e } = \frac { \pi \lambda _ { s } } { 2 } + \frac { \pi \lambda _ { s } ^ { 2 } } { \alpha _ { k x } d } \Bigg [ \ln \left( \frac { d } { 2 } + \frac { \lambda _ { s } } { \alpha _ { k x } } \right) - \ln \left( \frac { \lambda _ { s } } { \alpha _ { k x } } \right) \Bigg ]
$$

It is assumed that the air flow in each interstitial space is one-way from lower cross section to upper cross section in the hopper, so the equivalent diameter of the assumed flow pipe can be calculated by Eq. (7):

$$
d _ { k x } = { \frac { 4 { \Bigl ( } d ^ { 2 } - \pi d ^ { 2 } / 4 { \Bigr ) } } { \pi d } } = \left( { \frac { 4 } { \pi } } - 1 \right) \cdot d
$$

The convective heat transfer coefficient in the as sumed flow pipe is given by:

$$
\alpha _ { k x } = 0 . 0 2 3 \cdot \frac { \lambda _ { a } } { d _ { k x } } \cdot \mathbf { R e } _ { k x } ^ { 0 . 8 } \mathbf { P r } _ { a } ^ { 0 . 4 }
$$

$$
\mathrm { R e } _ { k x } = \frac { \rho _ { a } u _ { k x } d _ { k x } } { \mu _ { a } }
$$

$$
u _ { k x } = \frac { u } { \varepsilon }
$$

The equivalent thermal conductivity of $\lambda _ { e }$ can be calculated by Eq. (6) - Eq. (10).

The equivalent density and specific heat of the combined structure are determined by Eqs.(11）- (12):

$$
{ \rho } _ { e } \mathrm { = } \varepsilon \cdot { \rho } _ { a } + ( 1 \mathrm { - } \varepsilon ) \cdot { \rho } _ { s }
$$

$$
c _ { e } = \frac { \varepsilon \rho _ { a } } { \rho _ { e } } \cdot c _ { a } + \frac { ( 1 - \varepsilon ) \rho _ { s } } { \rho _ { e } } \cdot c _ { s }
$$

# Nomograms abstracted from simulation results

In air precooling aggregate works, four side walls of the aggregate hopper are adiabatic and heat can only be transferred from lower surface to upper surface in $\textbf { \em z }$ direction. So the transient heat transfer process of the aggregate can be approximately described by Eq. (13) [9]:

$$
\cfrac { \theta \left( z , \tau \right) } { \theta _ { 0 } } = \frac { T \left( z , \tau \right) - T _ { a } } { T _ { 0 } - T _ { a } } = f \left( F o , B i , \frac { z } { \delta } \right)
$$

$$
F o { = } \frac { a \tau } { \delta ^ { 2 } }
$$

$$
B i { = } \frac { \alpha \delta } { \lambda }
$$

$$
a { = } \frac { \lambda } { \rho c }
$$

The cooled air flows in the inlet flue and then dis perses into interstitial spaces in the hopper,which is different from the ideal convective condition on the upper surface and the lower surface of the hopper. So it is necessary to redefine the Biot number and the Fourier number. The effective Biot number is redefined according to the converted convective condition in the whole cross section (see Eq.(17)); the effective Fourier number is redefined according to the hopper size and thermal properties of the combined structure (see Eq.(18)):

$$
B i = \frac { \alpha _ { \nu } L } { \lambda _ { e } }
$$

$$
F o { = } \frac { a _ { e } \tau } { L ^ { 2 } }
$$

Otherparameters are defined as follows: The effective heat diffusivity:

$$
a _ { e } = \frac { \lambda _ { e } } { \rho _ { e } c _ { e } }
$$

The virtual convective coefficient:

$$
\alpha _ { \nu } { = } 0 . 0 2 3 \cdot \frac { \lambda _ { a } } { D _ { e } } \cdot \mathrm { R e } _ { \nu } ^ { 0 . 8 } \mathrm { P r } _ { a } ^ { 0 . 4 }
$$

Equivalent diameter of the hopper:

$$
D _ { e } { = } \frac { 4 A } { U }
$$

Virtual Reynolds number:

$$
\mathbf { R e } _ { \nu } = \frac { \rho _ { a } u ~ D _ { e } } { \mu _ { a } }
$$

So the transient heat transfer process in the aggregate hopper can be described by Eq.(13),Eq.(17)- Eq. (22).

Calculation of Eq.(13) is so difficult that nomogram is usually introduced to describe and predict the transient heat transfer process,and it has been widely used in engineering. $\mathrm { \Delta } X$ -coordinate of the nomogram is $F o$ ; Y-coordinate is T-T Inthpaperhetasienthattrasfer characteristics of the aggregate are analyzed according to the enormous simulation results, $B i$ and $F o$ arecalculated by Eqs.(17）- Eq.(22)，and then nomograms under different work conditions are drawn.

Simulation results show that the transient heat transfer ruleis similar when $L / D _ { e }$ changes little.So the simulations are ranked according to $L / D _ { e }$ (see Table 2).

Nomograms are selectively shown in the paper. Fig. 8 show nomograms in cross section D $\scriptstyle ( z / L = 1 )$ ！

Table 2Ranked simulations according to $L / D _ { e }$   

<html><body><table><tr><td rowspan="2">No.</td><td rowspan="2">L/D</td><td rowspan="2">LIDe</td><td rowspan="2">Cross section area of the hopper Ah (m²)</td><td rowspan="2">Height between two air flues L (m)</td></tr><tr><td></td></tr><tr><td rowspan="2">1</td><td rowspan="2">0.634</td><td>0.625</td><td>24</td><td>3</td></tr><tr><td>0.642</td><td>30</td><td>3.5</td></tr><tr><td rowspan="2">2</td><td rowspan="2">0.724</td><td>0.717</td><td>18</td><td>3</td></tr><tr><td>0.73</td><td>24</td><td>3.5</td></tr><tr><td rowspan="2">3</td><td rowspan="2">0.831</td><td>0.826</td><td>30</td><td>4.5</td></tr><tr><td>0.836</td><td>18</td><td>3.5</td></tr><tr><td rowspan="2">4</td><td rowspan="2">0.943</td><td>0.917</td><td>30</td><td>5</td></tr><tr><td>0.938</td><td>24</td><td>4.5</td></tr><tr><td rowspan="2">5</td><td rowspan="2">1.058</td><td>0.975</td><td>10</td><td>3</td></tr><tr><td>1.04</td><td>24</td><td>5</td></tr><tr><td rowspan="2">6</td><td rowspan="2">1.166</td><td>1.075</td><td>18</td><td>4.5</td></tr><tr><td>1.137</td><td>10</td><td>3.5</td></tr><tr><td rowspan="2">7</td><td rowspan="2"></td><td>1.194</td><td>18</td><td>5</td></tr><tr><td>1.46</td><td>10</td><td>4.5</td></tr><tr><td></td><td>1.543</td><td>1.625</td><td>10</td><td>5</td></tr></table></body></html>

![](images/1b81fb824468c72ab5ca7db2b8611ddbdf837064b7c1083d2cddd314804c7acc.jpg)  
Fig.8Nomograms when $\overline { { L / D _ { e } } } = 1 . 5 4 3$ (cross section D)

Nomograms show that the compared excess temperature T-Toincreases whenBincreases,whichmeans that temperature of the aggregate more obviously deviates from the initial value and approaches air temperature when the air convection becomes intensive.

# Fitting equations for transient heat transfer processes

Change regularity of $\frac { T - T _ { 0 } } { T _ { a } - T _ { 0 } }$ seriously depends on $F o$ and $B i$ ，as shown in nomograms.The exponential function of $F o$ can be used to predict the compared excess temperature according to the obtained nomograms:

$$
{ \frac { T - T _ { 0 } } { T _ { a } - T _ { 0 } } } = A - B \cdot \exp \Bigl [ - 1 \cdot C \cdot \bigl ( F o - F o ^ { \ast } \bigr ) \Bigr ]
$$

Where $A , B , C , F o ^ { * }$ are fitting coefficients and seriously depends on $B i . F o ^ { * }$ explains temperature delay of the aggregate in the cross section.In the cross section A $\scriptstyle ( z / L = 0 )$ , the aggregate temperature immediately changes when the air flows into the inlet flue,so $F o ^ { * } { = } 0$ ：

Correlations of the fitting coefficients can be deduced from simulation results,as shown in Eq.(24) and Table 3.

$$
\begin{array} { r l } & { A { = } A ^ { \prime } { \cdot } B i { + } A ^ { \prime \prime } { = } f ( L / D _ { e } , B i ) } \\ & { B { = } B ^ { \prime } \cdot B i { + } B ^ { \prime \prime } { = } f ( L / D _ { e } , B i ) } \\ & { C { = } C ^ { \prime } \cdot B i { + } C ^ { \prime \prime } { = } f ( L / D _ { e } , B i ) } \\ & { F o ^ { * } { = } f ( B i ) } \end{array}
$$

Fig.9 presents relative error of the fitting equations for the compared excess temperature in four cross sections.The relative error is about less than $\pm 1 0 \%$ ，so the fitting equations are precise enough to predict the transient heat transfer process of the aggregate in the air pre cooling hopper.

# Conclusions

The transient heat transfer characteristics of the aggregate in the air precooling hopper are analyzed by CFD method, nomograms of the transient heat transfer processes are sorted out and fitting equations are deduced to precisely predict the transient heat transfer process. Some important conclusions can be obtained from the analyses:

Table 3Correlations of the fitting coefficients   

<html><body><table><tr><td>Cross section</td><td>Fitting coefficients</td></tr><tr><td rowspan="3">A (z/L=0)</td><td>A'=-0.0225·L/De + 0.0453; A" =0.0451·L/D +0.8156;</td></tr><tr><td>B'=-0.0254·L/De +0.0192; B"=0.0919·L/De +0.5492 ;</td></tr><tr><td>C' =1332.8·L/De +154.81; C"= -275.36·L/De +114.87 ; Fo*=0</td></tr><tr><td rowspan="3">B (z/L=1/3)</td><td>A'=-0.0123·L/De +0.0219 ;A"=0.0535·L/De +0.807 ;</td></tr><tr><td>B'=0.0037·L/De-0.0351; B"=0.5833·L/De +0.4248;</td></tr><tr><td>C'=1366.4·L/De +554.02;C"=-530.2·L/De +215.72; Fo*=0.0005·Bi-1.166</td></tr><tr><td rowspan="3">C (z/L=2/3)</td><td>A' =-0.0838·L/De +0.0246 ; A" =0.2522·L/De +0.7434 ;</td></tr><tr><td>B'=0.0374·L/De-0.1893;B"=1.0151·L/De +0.2248;</td></tr><tr><td>C'=1126.9·L/De +489.25 ; C"=-621.13·L/De + 253.8; F0*=0.001·Bi-1.146</td></tr><tr><td rowspan="3">D (z/L=1)</td><td>A' =-0.0838·L/De +0.0246； A"=0.2522·L/De +0.7434 ;</td></tr><tr><td>B'=0.0374·L/De-0.1893；B"=1.0151·L/De+0.2248</td></tr><tr><td>C'=1126.9·L/De +489.25；C"=-621.13·L/De+253.8; Fo*=0.0016·Bi-1.14</td></tr></table></body></html>

![](images/46ed2298b1e6b9a07a905d3f60d82829c267392cebf49450be2d5fab6f0a7b96.jpg)  
Fig.9Relative error of the fitting equations

1.The structure composed by the aggregate and the interstitial space in the hopper can be treated as a porous structure,and the similarity experiment results verify that the space-average method is suitable for the stones with diameter not more than $8 0 \mathrm { m m }$

2. Size of the hopper and the average air velocity in the cross section have obvious influence on the transient heat transfer process of the aggregate,while the porosity in the range of $0 . 4 \substack { - 0 . 5 }$ has little influence,according to enormous simulations of actual air precooling works.

3.Correlations of the compared excess temperature $\frac { T - T _ { 0 } } { T _ { a } - T _ { 0 } }$ fitted from nomograms can precisely predict the air precooling transient heat transfer process of the aggregate.The calculation offers a reliable method for design of the air precooling process to avoid temperature cracks and unreasonable energy consumption.

# Acknowledgements

The authors acknowledge the financial supports provided by the Power Construction Corporation of China (GW-KJ-2011-14) .

# References

[1]Chunxiang Qian,Guibo Gao.Reduction of Interior Tem

perature of Mass Concrete Using Suspension of Phase Change Materials as Cooling Fluid,Construction and Building Materials,2012(26):527-531   
[2] Bofang Zhu.Thermal Stress and Temperature Control of Mass Concrete.Tsinghua University Press,Beijing,2014   
[3] Dingbo Weng.Precooling Technology ofMass Concrete. China Electric Power Press,Beijing,2012   
[4]E Casanova.Concrete Cooling on Dam Construction for World's Largest Hydroelectric Power Station,International Journal ofRefrigeration,1980,3(1):25-36   
[5]W. van Antwerpen,P.G. Rousseau,C.G.du Toit. Multisphere Unit Cell Model to Calculate the Effective Thermal Conductivity in Packed Pebble Beds of Mono-sized Spheres,Nuclear Engineering and Design，2O12,247: 183-201   
[6]Bahrami,M.,Yovanovich,M.M.,Culham,J.R.Effective Thermal Conductivity of Rough Spherical Packed Beds, International Journal ofHeat and Mass Transfer,2OO6,49: 3691-3701   
[7]O.Laguerre,S.Ben Amar,G.Alvarez,D.Flic,Transient heat transfer by free convection in a packed bed of spheres:comparison between two modelling approaches and experimental results,Appl. Therm.Eng.2Oo8,28(1): 14-24.   
[8]M.A.Gomez,D.PatinomR.Comesana，J.Porteiro, M.A.Alvarez Feijoo,J.L.Miguez. CFD Simulation of a solar radiation absorber,International Journal of Heat and Mass Transfer,2013,57:231-240   
[9]John H. Lienhard IV,John H. Lienhard V.A Heat Transfer Textbook,Phlogiston Press,Cambridge,Massachusetts,2003   
[10]M.Kaviany.Principles of Heat Transfer in Porous Media, Mechanical Engineering Series，Springer-Verlag，New York,1991   
[11]Zeng S.Q.,Hunt A.,Greif R.Geometric Structure and Thermal Conductivity of Porous Medium Silica Aerogel, ASME Journal ofHeat Transfer,1995,117(4):1055-1058   
[12]Wei G. S.,Liu Y. S., Zhang X.X., et al. Thermal Conductivities Study on Silica Aerogel and its Composite Insulation Materials.International Journal of Heat and Mass Transfer,2011,54:2355-2365