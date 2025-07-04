# Numerical Study of Hydrogen Peroxide Thermal Decomposition in a Shock Tube

Muhammad Rizwan Bhati1,Nadeem Ahmed Sheikh1\*,Shehryar Manzoor²,Muhammad Mahabat Khan1, Muzaffar Ali²

1 Departmentof Mechanical Engineering，Capital University of Science and Technology，Islamabad,Pakistan   
2 Mechanical Engineering Department, University of Engineering and Technology, Taxila, Pakistan

$\copyright$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

Hydrogen peroxide $\mathrm { ( H } _ { 2 } \mathrm { O } _ { 2 } )$ has its significance during the combustion of heavy hydrocarbons in the internal combustion (IC) engines.Owing to its importance the measurements of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ dissociation rate have been reported mostly using the shock tube apparatus.These types of experimental measurements are although quite reliable but require high cost.On the other hand, numerical simulations provide low cost and reliable solutions especially using computation fluid dynamics (CFD)software.In the current study an experimental shock tube flow is modeled using open access platform OpenFOAM to investigate the thermal decomposition of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ .Using two different convective schemes,limitedLinear and upwind,the propagation of shock wave and resultant disociation reaction are simulated.The results of the simulations are compared with the experimental data.Itis observed that the rate constant measured using the simulation data deviates from the experimental results in the low temperature range and approaches the experimental values as the temperature is raised.

# Keywords:Reactionkinetics,Rate constant,Numerical simulation,Shock wave,Reflected shock wave,Contact discontinuity,Expansion fan, Internal flow, Compressible flow, Gas dynamics

# Introduction

During the combustion of fossil fuels in the internal combustion engines,numerous intermediate reactions occur before the production of final products (Bhaskaran et al.20o2). Hydrogen peroxide is one of the most important intermediate compounds formed which guides and controls the downstream chain of reactions in the temperature range of $8 5 0 \mathrm { K }$ to $1 2 0 0 \mathrm { K }$ (Hong et al. 2011). Hydrogen peroxide is also used as monopropellant using the catalytic decomposition technique in some types of rocket engines.It has its future as a green monopropellant (Westbrook 2Ooo). For the delivery of micro satellites in the orbits,it is an established monopropellant fuel (Davenas et al. 2oo4). It is also being utilized as an oxidizer in some rocket engines. It has also found its utility for the alignment of satellites and attitude control pur poses.Besides hydrogen peroxide has numerous industrial applications; for instance treatment of waste water, industrial waste treatment, bleaching of textile products and bleaching of paper etc.

Due to its versatile applications, $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ dissociate reaction is extensively used experimentally. Most experimental setups used shock tube.In the shock tube environment, the propagating shock wave upon reflection from end wall provides appropriate environment (in terms of temperature and pressure） where the thermal decomposition can occur(Anderson 2oo3). This process has been studied using various diagnostic techniques. Bilwakesh et al.(1968) performed the thermal decompo

# Nomenclature

<html><body><table><tr><td>A</td><td>speed of sound (m/s)</td><td>R</td><td>gas constant (joules/kg:K)</td></tr><tr><td>Cp</td><td>sp.heat at const. pressure (joules/kg·K)</td><td>R</td><td>rate of production of lth species</td></tr><tr><td>D</td><td>diffusion coefficient of lth species</td><td>S</td><td>seconds</td></tr><tr><td>e</td><td>specific internal energy (joules/kg)</td><td>U</td><td>velocity vector (m/s)</td></tr><tr><td>h</td><td>specific enthalpy (joules/kg)</td><td>V</td><td>velocity of contact discontinuity (m/s)</td></tr><tr><td>I</td><td>Identity Matrix</td><td>W</td><td>specific volume (m³/kg)</td></tr><tr><td>J</td><td>diffusion flux of lth species</td><td>W</td><td>velocity of normal shock wave (m/s)</td></tr><tr><td>k</td><td>rate constant(cmmol-1s-1)</td><td>W</td><td>velocity of reflected shock wave (m/s)</td></tr><tr><td>K</td><td>Kelvin (temperature)</td><td>Y</td><td>mass fraction of lth species</td></tr><tr><td>K</td><td>Kinetic Energy (joules)</td><td>2</td><td>specific heat ratio</td></tr><tr><td>L</td><td>length (m)</td><td>V</td><td>del operator</td></tr><tr><td>m</td><td>meter</td><td>p</td><td>density (kg/m³)</td></tr><tr><td>p</td><td>Pressure in Pascal</td><td>T</td><td>viscous tensor</td></tr><tr><td>Pa</td><td>Pascal (pressure)</td><td>从</td><td>micro</td></tr><tr><td>q</td><td>heat flux (Watt/m²)</td><td>0</td><td>dynamic viscosity (N·s/m²)</td></tr></table></body></html>

sition analysis with the help of experimental shock tube facility. In order to monitor the thermal decomposition they utilized the absorption methods. The driver section consisted of air and helium mixture whereas the driven section consisted of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ and nitrogen mixture. The nitrogen served as the bath gas.Meyer et al.(1969) analyzed the decomposition of $\mathrm { N } _ { 2 } \mathrm { H } _ { 4 }$ and $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ . Theymeas ured the decomposition rate of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ between temperatures $9 5 0 \mathrm { K }$ to $1 4 5 0 \mathrm { K }$ and the pressure was kept up to 20 bar.UV absorption was used to monitor the decomposition rates.

Few other studies such as Trainor et al.(1974) conducted the study of reunification of OH ion using the photolysis technique at low pressure and temperature and utilized the absorption spectroscopy. Using flash photo lysis Zellner et al.（1988) conducted experiments at low temperature and pressure range.Forster et al.(1995) with the help of laser induced fluorescence monitored the ions at room temperature and pressure up to 15O bar.Fulle et al.(1996) also used the laser induced fluorescence for the reunification of OH radicals.The maximum pressure and temperature were 150 bar and 70o K respectively. Sangwan et al. (2012) performed the experimental study of hydroxyl to hydroxyl reaction with the help of UV absorption monitoring technique at temperatures ranging from $2 9 6 \mathrm { K }$ to $8 3 4 ~ \mathrm { K }$ and pressures ranging from 1 bar to 100 bar.Bahrini et al. (2012) performed the quantitative analysis of hydrogen peroxide.Brouwer et al.(1987) performed the theoretical calculations of reaction rates by using statistical adiabatic models.The temperature was in the range $2 0 0 ~ \mathrm { K }$ to $1 5 0 0 ~ \mathrm { K }$ 、Troe et al.(2008) used the ab-initio technique for the calculation of decomposition/ recombination of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ up to maximum temperature of $5 0 0 0 ~ \mathrm { K }$ . This ab-initio technique is a quantum chemistry method and is a subject of computational chemistry (Levine 1991). Sellevag et al. (2009) used two transition state model for the calculation of rate constants with temperature ranging between $2 0 0 \mathrm { K }$ and $3 0 0 0 \mathrm { K }$ ：

Using shock tubes,Hong et al.(2oo9) conducted experiments regarding the $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ thermal decomposition. They used tunable laser absorption near $2 . 5 \times 1 0 ^ { - 6 } \mathrm { ~ m ~ }$ to detect the $\mathrm { H } _ { 2 } \mathrm { O }$ in the products.Hong et al. (2010) used IR absorption for the detection of $_ \mathrm { H } _ { 2 } \mathrm { O }$ at $2 . 5 5 \times 1 0 ^ { - 6 } \mathrm { m }$ in the temperature between $1 0 0 0 ~ \mathrm { K }$ to $1 2 0 0 \mathrm { K }$ and pressure between O.9 atm. to 3.2 atm. In another study, Hong et al. (2011) used UV absorption to monitor OH near $3 0 6 . 7 \times$ $1 0 ^ { - 9 } \mathrm { m }$ and used infrared absorption to monitor water near $2 . 5 5 \times 1 0 ^ { - 6 } \mathrm { m }$ .They measured the rate constant for hydrogen peroxide thermal decomposition at temperatures between 1020 to $1 4 6 0 ~ \mathrm { K }$ and pressure at 1.8 atm. More recently, Sajid et al. (2013） performed the experiments for the analysis of thermal decomposition of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ ina shock tube and used quantum cascade laser absorption near $7 . 7 \times 1 0 ^ { - 6 } \mathrm { ~ m ~ }$ . They performed the experiments in temperature range $9 3 0 - 1 2 3 5 \mathrm { ~ K ~ }$ and for pressures at 1,2 and $1 0 \mathrm { a t m }$

As briefed above,most of the work in this area is experimental. On the other hand, Computational Fluid Dynamics(CFD) is a fast growing area to simulate the expensive physical experiments.Due to cheap availability of computers and state of the art softwares/tools which are both open source and freelyavailable,it has become feasible to perform simulations in a rapid and cost effective manner. To harness the potential of CFD, the expe rimental setup described by Sajid et al.(2O13) has been simulated in an open source OpenFOAM software. One of its solvers,reactingFoam has been used to perform the simulations using the limitedLinear and upwind convective schemes.The reactingFoam solver supports the reac tion kinetics. The thermal decomposition analysis of hydrogen peroxide has been conducted by modeling the experimental shock tube and the results have been compared with the experimental results.

# Shock Tubeanalytical model

# Theory

The shock tube is a circular or rectangular pipe with both ends closed.The shock tube for the current study has circular cross-section.A thin membrane called diaphragm divides the shock tube into two compartments. InFig.1 the left compartment is called the driver section and is denoted by $\cdot _ { 4 } \cdot$ . The right compartment is called the driven section and is denoted by‘1'.Both compartments are filled with gas whereas the pressure of driver section is greater than the driven section.Both the sections can have the same gas or different gases.Similarly both compartments may have the same temperature or different temperature.

The velocities in both compartments are initially zero. Suppose that ${ \bf P } _ { 1 }$ ， $\mathrm { T } _ { 1 }$ are pressure and temperature in compartment 1 and ${ \bf P } _ { 4 }$ $\mathrm { T } _ { 4 }$ are pressure and temperature in compartment 4. Then the pressure ratio $\mathrm { P } _ { 4 } / \mathrm { P } _ { 1 }$ is said to be the diaphragm pressure ratio.

![](images/d01f50470cd2095eb706ccefb5d499dad804afb80114b7907de80fa5914d3a14.jpg)  
Fig.1Initial Profile of Shock Tube   
Fig.2Pre Shock Reflection Scenario   
Fig.3 Post Shock Reflection Scenario

Figure 2 shows different regions formed due to sudden removal of diaphragm by some mechanism.The region 1 and 2 is separated by normal shock wave which is heading towards right. The region 2 and 3 are separated by contact discontinuity. There is an expansion fan in between the regions3 and 4.The regions2 and3 have same velocity and pressure but different temperature and density.

4↑ Expanion 3 TComae Dleomii P4 P P P. 13

Figure 3 is depicting the post shock reflection scene. When the shock is reflected back after striking the end wall of driven compartment, the region 5 appears. It has comparatively high pressure and temperature and zero velocity.

4 Expasion 3 (Reflected) Normal Shock Wave 5 P4 P P P

# Governing Equations

The movement of shock wave in the shock tube can be modeled analytically using continuity,momentum and energy balance across the normal shock wave.

$$
\begin{array} { c } { \rho _ { 1 } W = \rho _ { 2 } \left( W - \nu \right) } \\ { p _ { 1 } + \rho _ { 1 } W ^ { 2 } = p _ { 2 } + \rho _ { 2 } \left( W - \nu \right) ^ { 2 } } \\ { e _ { 1 } + \displaystyle \frac { p _ { 1 } } { \rho _ { 1 } } + \frac { W ^ { 2 } } { 2 } = e _ { 2 } + \displaystyle \frac { p _ { 2 } } { \rho _ { 2 } } + \frac { \left( W - \nu \right) ^ { 2 } } { 2 } } \end{array}
$$

Here $\rho$ denotes density, $W$ represents shock velocity, $\nu$ is the velocity of contact discontinuity, $p$ represents pressure and $e$ Here $\rho$ denotes density, $W$ represents shock velocity, $\nu$ is the velocity of contact discontinuity, $p$ represents pressure and $e$ is the internal energy.The Eq.(4) is the Hugoniot equation,whereas $w$ represents the specific volume.

$$
e _ { 2 } - e _ { 1 } = \left( \frac { p _ { 2 } + p _ { 1 } } { 2 } \right) \left( w _ { 1 } - w _ { 2 } \right)
$$

The Eq. (5） provides the shock strength P2 from $p _ { 1 }$ which the unknown value of $p _ { 2 }$ is obtained.

$$
\frac { p _ { 2 } } { p _ { 1 } } \Bigg [ 1 - \frac { \big ( \gamma _ { 4 } - 1 \big ) \big ( a _ { 1 } / a _ { 4 } \big ) \big ( p _ { 2 } / p _ { 1 } - 1 \big ) } { \sqrt { 2 \gamma _ { 1 } \big ( 2 \gamma _ { 1 } + \big ( \gamma _ { 1 } + 1 \big ) \big ) \big ( p _ { 2 } / p _ { 1 } - 1 \big ) } } \Bigg ] ^ { - 2 \gamma _ { 4 } / \big ( \gamma _ { 4 } - 1 \big ) } = \frac { p _ { 4 } } { p _ { 1 } }
$$

Where $\gamma$ is the specific heat ratio and $a$ represents the speed of sound.

The Eqs. (6)-(8) represent the mass,momentum and energy equationsrespectivelyforthereflected shock.

$$
\begin{array} { c } { \rho _ { 2 } \left( W _ { r } + \nu \right) = \rho _ { 5 } W _ { r } } \\ { p _ { 2 } + \rho _ { 2 } \left( W _ { r } + \nu \right) ^ { 2 } = p _ { 5 } + \rho _ { 5 } W _ { r } ^ { 2 } } \\ { h _ { 2 } + \displaystyle \frac { \left( W _ { r } + \nu \right) ^ { 2 } } { 2 } = h _ { 5 } + \displaystyle \frac { W _ { r } ^ { 2 } } { 2 } } \end{array}
$$

Where $W _ { r }$ is the velocity of the reflected shock and $h$ is the enthalpy.

# Numerical modeling

The Navier Stokes equations along with the species transport equation are given by

$$
\begin{array} { c } { \displaystyle \frac { \partial \rho } { \partial t } + \nabla \cdot ( \rho \boldsymbol { U } ) = 0 } \\ { \displaystyle \frac { \partial \left( \rho \boldsymbol { U } \right) } { \partial t } + \nabla \cdot ( \rho \boldsymbol { U } ) = \nabla \cdot \boldsymbol { \mathrm { p } } + \nabla \cdot \boldsymbol { \tau } } \\ { \displaystyle \frac { \partial \left( \rho h \right) } { \partial t } + \nabla \cdot ( \rho h \boldsymbol { U } ) + \frac { \hat { c } \left( p \boldsymbol { K } \right) } { \hat { \sigma } t } + \nabla \cdot ( \rho \boldsymbol { K } \boldsymbol { U } ) - \frac { d p } { d t } } \\ { = - \nabla \cdot \boldsymbol { \mathrm { q } } + \nabla \cdot ( \boldsymbol { \tau } \cdot \boldsymbol { \mathrm { U } } ) } \end{array}
$$

$$
\frac { \partial \left( \rho Y _ { l } \right) } { \partial t } + \nabla \cdot \left( \rho Y _ { l } \pmb { U } \right) + \nabla \cdot \pmb { J } _ { l } = R _ { l }
$$

$$
J _ { l } = - \rho D _ { l } \nabla Y _ { l }
$$

$$
\boldsymbol { \tau } = \mathcal { S } \biggl [ \boldsymbol { \nabla } \pmb { U } + \left( \boldsymbol { \nabla } \pmb { U } \right) ^ { T } \biggr ] + \frac { 2 } { 3 } \mathcal { S } \bigl ( \boldsymbol { \nabla } \cdot \pmb { U } \bigr ) \pmb { I }
$$

Where $\mathbf { U }$ is velocity vector, $\tau$ represents viscous tensor, $\boldsymbol { { \cal I } }$ is the identity matrix, $\theta$ isdynamic viscosity, $K$ represents kinetic energy, $Y _ { l }$ is mass fraction of $l ^ { \mathrm { { t h } } }$ species, $J _ { l }$ is the diffusion flux of ${ \bf \ddot { \boldsymbol { l } } ^ { \mathrm { t h } } }$ species, $R _ { l }$ represents production rate of the $l ^ { \mathrm { { t h } } }$ species, $D _ { l }$ is diffusion coefficient, $R$ is the gas constant, $\mathbf { q }$ is heat flux, $\rho$ is density, $p$ is the pressure, and $h$ is the enthalpy. The chemical reaction and the rate constant for the reaction are given by Eq.(19) and Eq. (20) respectively.

# Solver

The OpenFOAM supports a diverse range of solvers including the pressure based and density based solvers. The shock tube phenomena can be modeled by sonicFoam pressure based solver and rhoCentralFoam density based solver.But these solvers work in inert scenario only.As has been previously mentioned that reacting Foam solver in OpenFOAM supports reaction kinetics. However it is a pressure based generic solver in which intermediate or global reactions can be modeled. Therefore,it has been chosen as a suitable candidate to simulate the thermal decomposition of hydrogen peroxide by modeling the shock tube apparatus.

The reactingFoam solver consists of PIMPLE algorithm.It is a combination of SIMPLE and PISO algorithms.The $\mathbf { k }$ -epsilon turbulence model has beenused for the current study due to its robustness and accuracy.It is also suitable for confined flows(Versteeg 2oo7).In order to compute the dynamic viscosity, the Sutherland transport model has been used. $\mathrm { C } _ { \mathrm { p } }$ is calculated using the JANAF tables for the species (McBride 1993). The Par tially Stirred Reactor(PaSR) combustion model has been used to model the combustion phenomena (Correa 1993). It is a modification of Eddy Dissipation Concept (EDC). The species considered in the simulations are $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ $\mathrm { H } _ { 2 } \mathrm { O }$ OH, Ar and He.

For the time discretization, the Euler implicit scheme has been utilized which is first order and bounded.In order to interpolate the diffusion coefficient, the linear interpolation scheme has been utilized.To discretize the surface normal gradient the uncorrected scheme has been implemented which is first order and bounded.

# Convective Schemes

For the aforementioned case two different convective schemes,LimitedLinear and upwind,are used.LimitedLinear falls into the helm of Total Variation Diminishing

(TVD)schemes (Direct 2015).It is bounded and is of second order.

Figure 4 represents the control volume around P.E andWare eastandwest nodes.eis thecell interface.The fluxes are calculated at cell interfaces.

![](images/5fd4259d182bde5469ac647175f2dfde91e43591402511fe2f38526f849cf866.jpg)  
Fig.4Control Volume around P

Using Fig. 4, the central difference scheme is given by

$$
\phi _ { e } = \phi _ { P } + \frac { 1 } { 2 } \varphi \big ( r \big ) \big ( \phi _ { E } - \phi _ { P } \big )
$$

Where $\phi _ { e }$ is flux at the cell interface e, $\varphi ( \boldsymbol { r } )$ is flux limiter and for the case of central difference $\varphi ( r ) = 1$ The limitedLinear scheme is obtained by replacing the flux limiter of central difference scheme with the Sweby flux limiter. The Sweby limiter is given byEq.(17) (Versteeg 2007)

$$
\varphi \left( r \right) = \operatorname* { m a x } \left[ 0 , \operatorname* { m i n } \left( 1 . 5 r , 1 \right) , \operatorname* { m i n } \left( r , 1 . 5 \right) \right]
$$

The upwind scheme is first order bounded.It is given by Eq. (18)

$$
\phi _ { e } = \phi _ { P }
$$

# Behavior of Convective Schemes

In order to compare the results of convective schemes with the analytical results,each simulation for limitedLinear and upwind schemes has been run by using the reactingFoam solver. Initially laminar and inert settings havebeen taken for the simulations.Air has been taken as the working inert gas.The simulation is 1-D and the mesh resolution is 2oo computational cells.

Table 1 Shock Tube Specs   

<html><body><table><tr><td>Quantity</td><td>Symbol</td><td>Value</td></tr><tr><td>Driver Length</td><td>L</td><td>0.1 m</td></tr><tr><td>Driven Length</td><td>L2</td><td>0.1 m</td></tr><tr><td>Total Length</td><td>L+L2</td><td>0.2 m</td></tr><tr><td>Driver Pressure</td><td>P4</td><td>1000,000 pa.</td></tr><tr><td>DriverTemperature</td><td>T4</td><td>800 K</td></tr><tr><td>Driven Pressure</td><td>P1</td><td>100,000 pa.</td></tr><tr><td>Driven Temperature</td><td>T</td><td>300K</td></tr></table></body></html>

Figures 5 and 6 show almost the same results in both cases of limitedLinear and upwind schemes.There is only slight difference in the overshoot at the normal shock. The overshoot is more prominent in case of limitedLinear. The normal shock wave in analytical case is lagging behind the numerical shock predictions.

Both schemes have shown that the pressure and velocity are the same in regions 2 and 3 which conform to the physics of the problem. There is an over prediction in pressure and an under prediction in velocity in both cases. The contact discontinuity has been captured in both cases, which has been shown in the temperature and density plots.The temperature is over predicted in both regions but the difference is less in region 3 as compared to region 2. The results are very good in case of density in region 3 and there is under prediction in the case of region 2.

![](images/121b45b3cbcd417e04d132fecff455fc0cd5f61317e701745f43528b66795e04.jpg)  
Fig.5limitedLinearand analytical results

![](images/b3289bbc1eeb596d2413df42fd64f531808e450af9da3721372d538fec445306.jpg)  
Fig.6Upwind and analytical results

# Comparison of reactingfoam results with experimental data

This section provides the details of the results of reactingFoam simulations regarding the thermal decomposition of hydrogen peroxide in the shock tube model. The reactingFoam solver has been run for both limitedLinear and upwind convective schemes.

# SummaryofExperimental Data

Sajid Es-Sebbar et al. (2O13） experimental data has been taken to run the reactingFoam simulations.Sajid used analytical model to calculate temperature and pressure in region 5.Equation(19) represents the hydrogen peroxide decomposition reaction while Eq. (2O) is its rate constant measured from the experiment.It has been entered as an input to the reactingFoam solver.

$$
\begin{array} { c } { { \mathrm { H } _ { 2 } \mathrm { O } _ { 2 } + \mathrm { A r } {  } 2 \mathrm { O H } { + } \mathrm { A r } } } \\ { { k ( T ) _ { a t 1 , 2 a t m s } } } \\ { { = 1 0 ^ { ( 1 6 . 2 9 \pm 0 . 1 2 ) } \times \exp ( - 2 1 9 9 3 \pm 3 0 1 / T ) \quad ( \mathrm { c m } ^ { 3 } \mathrm { m o l } ^ { - 1 } \mathrm { s } ^ { - 1 } ) } } \end{array}
$$

# Simulation Results (limitedLinear)

1-D shock tube simulations have been run using 4000, 6000 and 8ooo spatial resolutions using limitedLinear as the convective scheme.The purpose to use different mesh resolutions is to ensure the mesh resolution independence for thermal decom-position of hydrogen peroxide. Each simulation has been run for time duration of16 milliseconds with the initial time step of $5 \times { 1 0 } ^ { - 7 }$ seconds. The shock tube specifications used are detailed in Table 2. The driver section comprised of helium gas.The driven section consists of gas mixture as mentioned in Table 3.

Table 2Shock Tube Specs   
Table 3Mole Fraction of Gases(Driven Section)   

<html><body><table><tr><td>Gas</td><td>Mole Fractions</td></tr><tr><td>Argon</td><td>0.991</td></tr><tr><td>HO2</td><td>0.005</td></tr><tr><td>HO</td><td>0.004</td></tr></table></body></html>

$\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ Decomposition Simulation in OpenFOAM   

<html><body><table><tr><td>Quantity</td><td>Symbol</td><td>Value</td></tr><tr><td>Driver Length</td><td>L</td><td>4.5 m</td></tr><tr><td>Driven Length</td><td>L2</td><td>9m</td></tr><tr><td>Total Length</td><td>L +L2</td><td>13.5 m</td></tr><tr><td>Driver Pressure</td><td>P4</td><td>107998 Pa</td></tr><tr><td>Driver Temperature</td><td>T4</td><td>800K</td></tr><tr><td>Driven Pressure</td><td>P1</td><td>12000 Pa</td></tr><tr><td>Driven Temperature</td><td>T</td><td>296K</td></tr></table></body></html>

A probe has been placed at $1 3 . 4 9 5 \mathrm { ~ m ~ }$ from the origin, so that the thermal decomposition data, temperature, pressure and velocity could be recorded. The probe location has been finalized to ensure the maximum temperature of post reflection region, since the temperature falls drastically as the reflected normal shock gets away from the driven section end wall. This phenomenon of reflected shock wave can be viewed in Fig.7.

110U Driver Section Driven Section   
800   
700   
600   
500   
400 Time = 13.60 msec.   
300 mesh = 6000   
200 150 01 2345678910111213 Shock Tube Length x (m) (a) Temperature profile $( \mathrm { t } = 0 . 0 1 3 6 0 \mathrm { s } )$ $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ Decomposition Simulation in OpenFOAM   
1300   
1200 reactingFoam   
1100 Driver Section Driven Section   
800   
700   
600 500 400 Time =13.75 msec.   
300 mesh $= 6 0 0 0$ （20 200 150 0 1 2 345678910111213 Shock Tube Length x (m) (b) Temperature profile $\mathrm { ( t = 0 . 0 1 3 7 5 ~ s ) }$ ） $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ Decomposition Simulation in OpenFOAM   
1300   
1200 reactingFoam   
1100 Driver Section Driven Section   
800   
700   
600   
500   
400 Time = 14.00 msec. 300 mesh $= 6 0 0 0$ （204号 200 150 0 1 2345678910111213 Shock Tube Length $\mathbf { x }$ (m) (c) Temperature profile $( \mathrm { t } = 0 . 0 1 4 0 \mathrm { s } )$

Fig. 7

The thermal decomposition profile for $2 5 0 ~ \mu \mathrm { s }$ from the beginning of decomposition in the post reflection region 5 at the specified probe for the mesh resolution 6000 is shown in Fig. 8.

The velocity, temperature and pressure scenarios for the $2 5 0 ~ \mu \mathrm { s }$ thermal decomposition duration have been shown by Figs. 9,10 and 11 respectively.

It has been observed that the temperature plot could not capture the contact discontinuity. The region 2 temperature is nearly $6 9 0 \mathrm { ~ K ~ }$ ，which agrees well with the temperature $6 9 6 . 9 4 \mathrm { ~ K ~ }$ predicted by WGD calculator for this region. The pressure for the region 2is $5 8 0 0 0 \ \mathrm { P a }$ which is comparable to 69643 Pa predicted by WGD calculator for this region. The pressure and temperature valuespredicted bythe reactingFoam solver,with limitedLinear convective scheme,in region 5 were lower as compared to WGD calculator values and the experimental values (see Table 4). The pressure and temperature values in region 5 as reported by Sajid et al. are also based on the analytical equations. The comparison of hydrogen peroxide mole fraction profile with the experimental data has been analyzed in section 4.4.Italso has been observed that the thermal decomposition profiles are not changing significantly by changing mesh resolution from 400O to 800o.So it is safe to consider the mesh independence of hydrogen peroxide decomposition profile at 6ooO mesh resolution.

![](images/ebbddbe5dcf5731b8fd39323853e8d8ed558524bf69b3278e39d2cb2cf4c0f05.jpg)  
Fig.8 $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ mole fraction time history

![](images/225b6f9666ed29798044134e8e88411c1dd6398256ceab21f21e3741e75bbbe7.jpg)  
Fig.9Velocity profile during thermal decomposition of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$

![](images/494b79ba41a60a94e3eab7721cfda6195f5a619f3c89e46adbc7707269c0f151.jpg)  
Fig.10 Temperature profile during thermal decomposition of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ （204

![](images/45399370a7ce2da8fb2e033412dde0e1f81c5fc0a3c6e41ff1e7587cbcc297a0.jpg)  
Fig.11 Pressure profile during thermal decomposition of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$

Table 4Temperatures and Pressures (Region 5)   

<html><body><table><tr><td>Source</td><td>Temperature T5 (K)</td><td>(atmosphe Ps)</td></tr><tr><td>(Sajid et al. 2013)</td><td>1167</td><td>2.35</td></tr><tr><td>(WGD 2008)</td><td>1211.45</td><td>2.3687</td></tr><tr><td>limitedLinear 4000 mesh</td><td>875.4</td><td>1.45</td></tr><tr><td>limitedLinear 6000 mesh</td><td>878.59</td><td>1.42</td></tr><tr><td>limitedLinear 8000 mesh</td><td>874.62</td><td>1.415</td></tr></table></body></html>

# Simulation Results (upwind)

Table 5 shows the temperature and pressure values in region 5 produced by reactingFoam upwind case at mesh resolution 6000.

It is observed that the velocity remains the same in region 2 as has been predicted by limitedLinear based simulation.Ithasbeenobservedthatlike thelimitedLinear scheme, the upwind scheme also could not capture the contact discontinuity. The temperature in region 2 is almost $7 0 0 ~ \mathrm { K }$ . The pressure in region 2 is $6 0 0 0 0 \mathrm { P a }$ .Figure 14 shows that the temperature for upwind case has increased as compared to limitedLinear. It has resulted in more dropping of the mole fractions of hydrogen peroxide in case of upwind as shown in Fig.12.

Table 5Temperatures and Pressures (Region 5)   

<html><body><table><tr><td>Source</td><td>Temperature T5 (K)</td><td>Pressure P5 (atmospheres)</td></tr><tr><td>(Sajid et al. 2013)</td><td>1167</td><td>2.35</td></tr><tr><td>(WGD 2008)</td><td>1211.45</td><td>2.3687</td></tr><tr><td>60windesh</td><td>911.61</td><td>1.496</td></tr></table></body></html>

![](images/572f4c14478d19b6005e4efb35e7aff3da19a1272982b906f4ab95cd8a8ea7ed.jpg)  
Fig.12 $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ mole fraction time history (at probe location)

![](images/e3d1fe10889581c57f3000da494d88ca86a077bc46b4569579f6c46050586060.jpg)  
Fig.13Velocity profile during thermal decomposition of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$

![](images/185a3b24488886a3c1df40ab7ba2d835864c8bc3d51267b874a551efedbb2f47.jpg)  
Fig.14 Temperature profile during thermal decomposition of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ （204

![](images/a34fe699458e81e1bb154cd2170064fc5f5126b28011e9eb4032a36409ba3754.jpg)  
Fig.15Pressure profile during thermal decomposition of $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$

# Comparison of Results

Figure 16 is the comparison of the hydrogen peroxide thermal decomposition profiles of the limitedLinear and upwind schemes with the Sajid et al. experimental results.

![](images/906076e5ff35d5645c9508aaae1a72492865468dbccdf8fa5e1173935fa6c2c1.jpg)  
Fig.16 $\mathrm { H } _ { 2 } \mathrm { O } _ { 2 }$ Decomposition Profile (at probe location)

The Sajid et al. data is shown by $\cdot _ { + } ,$ sign，which serves as the reference.The results shown by limitedLinearand upwind schemes are for the 6ooO grid resolution The plots for limitedLinear and upwind cases are for average temperatures $8 7 8 . 5 9 \mathrm { ~ K ~ }$ and $9 1 1 . 6 1 \mathrm { ~ K ~ }$ respectively. The average pressure values in region 5 for these two schemes are 1.42 atm.and 1.469 atm. respectively. Sajid et al.reported the temperature $1 1 6 7 \mathrm { ~ K ~ }$ and pressure 2.35 atm.for this region,which are based on analytical computations.

Sajid et al. plot represents the exponential decay in the mole fraction of hydrogen peroxide， whichisa non-linear phenomenon.Figure 16 shows that the limitedLinear and upwind cases also follow the same type of non-linear behavior. The limitedLinear curve overlaps the Sajid et al. curve from the start of decomposition point up to $1 0 0 \ \mathrm { s } .$ 、Afterwards it deviates due to reduction in decay rate and finally it terminates the graph at

$2 5 0 \mathrm { ~ s ~ }$ to the value of O.00168,which is higher than the experimental mole fraction value O.0oo78 at this point.

The upwind curve shows fast exponential decay in the mole fraction as compared to experimental data during the first half section.The second half portion of the curve shows the comparatively low decomposition rate.The curve finally ends the graph with slightly lower value than the experimental value of mole fraction.The fast exponential decay of mole fraction is attributed to the high temperature obtained in the upwind scheme as compared to the limitedLinear scheme.The latter parts of the curves in both cases show decrease in the decomposition rates,which is due to sharp decrease in temperature. It is again mentioned here that Sajid et al. used the values of temperature and pressure on the basis of analytical equations.

Table 6 shows the relation between rate constant k and $1 0 0 0 / \mathrm { T } ,$ ，where T represents temperature.The results of Sajid et al. and Hong et al.are for pressure 2 atmospheres and 1.7 atmospheres respectively，which have been shown for comparison.The limitedLinear results have also been shown.The limitedLinear results deviate from the Sajid et al.and Hong et al. results at lower temperatures and approach the experimental values as the temperature is increased.

Table 6Rate constant vs Temperature   

<html><body><table><tr><td>Source</td><td>1000/T (1/K)</td><td>k (cm³mol−1s-1)</td></tr><tr><td rowspan="5">limitedLinear</td><td>1.1382</td><td>1.44 ×108</td></tr><tr><td>1.0763</td><td>1.95 ×108</td></tr><tr><td>0.9730</td><td>4.42 ×10</td></tr><tr><td>0.8857</td><td>2.95 ×108</td></tr><tr><td>1.0639</td><td>1.44 × 106</td></tr><tr><td rowspan="6">Sajid et al. (2013)</td><td>1.0029</td><td>5.16 ×106</td></tr><tr><td>0.9475</td><td>1.61 ×10</td></tr><tr><td>0.9057</td><td>4.54 × 107</td></tr><tr><td>0.8568</td><td>1.44 × 108</td></tr><tr><td>0.8319</td><td>2.47 ×108</td></tr><tr><td>0.9924</td><td>8.50 ×106</td></tr><tr><td rowspan="9">Hong et al. (2011)</td><td>0.9812</td><td>9.77 × 106</td></tr><tr><td>0.9724</td><td></td></tr><tr><td></td><td>1.15 × 107</td></tr><tr><td>0.9563 0.9378</td><td>1.61 ×10 2.40 ×107</td></tr><tr><td>0.8953</td><td>5.65×10</td></tr><tr><td>0.8913</td><td>6.77 ×10</td></tr><tr><td>0.8648</td><td>1.01 ×108</td></tr><tr><td></td><td></td></tr><tr><td>0.8552</td><td>1.28×108 1.95 ×10</td></tr><tr><td></td><td>0.8407 0.8319</td><td>2.11 ×108</td></tr></table></body></html>

# Conclusion

The importance of hydrogen peroxide can be gauged from the fact that it is produced in the bulk quantities as an intermediate compound during the combustion of fossil fuels in various types of engines. It controls the chain of intermediate reactions leading to the final formation of products.It is used as fuel in some kinds of rockets, whereas it is also used as oxidizer in some other types of rocket systems.It is also used in industry.

In the present study, the shock tube model of an experimental setup has been simulated using the reactingFoam solver in the OpenFOAM.The results of limitedLinear and upwind convective schemes have been discussed and compared with the experimental results. The thermal decomposition curves produced by the limitedLinear and upwind convective schemes agree well with the experimental curve as shown in Fig. 16.The rate constantk in case oflimitedLinear has been computed at different temperatures.Table 6 shows that it deviates from the experimental results at low temperatures and agrees well to the experimental values as the temperature is raised.

# References

[1] “WiSTL Wisconsin Shock Tube Laboratory，Gas Dynamics Calculator.”Retrieved 14th June 2015,2015,from http://silver.neep.wisc.edu/\~shock/tools/gdcalc.html.   
[2] Anderson,J.D.(2003).Modern Compressible Flowwith Historical Perspective.New York,Mc GrawHill.   
[3] Bahrini, C., O.Herbinet, P.-A.Glaude, C.Schoemaecker, C.Fittschen and F.Battin-Leclerc (2012).“Quantification of Hydrogen Peroxide during the Low-Temperature Oxidation of Alkanes.”J.Am.Chem．Soc.134:11944- 11947.   
[4] Bhaskaran,K.A.andP.Roth (2002).“The shock tube as wave reactor for kinetic studies and material systems." (28):151-192.   
[5] Bilwakesh,K.R.,W.A.Strauss,R.Edse and E. S.Fishburne (1968). The Thermal Decomposition of Hydrogen Peroxide Vapor. Columbus, Ohio: 28.   
[6] Bonnie J.McBride, S.G.,Martin A.Reno.(1993). “Coefficients for Calculating Thermodynamic and Trasport Properties of Individual Species.”Retrieved 16th August,2o15,from http://ntrs.nasa.gov/archive/nasa/casi.ntrs.nasa.gov/19940013151.pdf.   
[7] Brouwer,L.,C.J.Cobos,J. Troe,H.R.Dubal and F.F. Crim(1987).“Specific rate constants k(E,J) and product state distributions in simple bond fission reactions.I. Application to HOOH - $\mathrm { \Gamma _ { O H + O H } }$ .”J.Chem. Phys.86: 6171.   
[8] Correa, S.M.(1993).“Turbulence-chemistry interactions in the intermediate regime of premixed combustion.” Combustion and Flame 93(1-2): 41-60.   
[9]Davenas,A., G. Jacob, Y. Longevialle and C. Perut （7-8 June 2004). Energetic Compounds for Future Space Applications.proc.'2nd Int.Conference on Green Propellants for Space Propulsion', Cagliari, Sardinia, Italy.   
[10] Direct, C. (2015).“OpenFOAM User Guide: 4.4 Numericalschemes.”Retrieved 14th June, 2015， from http://cfd.direct/openfoam/user-guide/fvSchemes/.   
[11]Forster,R.,M.Frost,D.Fulle,H.Hamann,H.Hippler,A. Schlepegrell and J. Troe (1995).“High pressure range of the addition of HO to HO, NO, NO2,and CO.I. Saturated laser induced fluorescence measurements at 298 K.”JChem.Phys.103.   
[12]Fulle,D.,H. F. Hamann, H. Hippler and J. Troe (1996). “High - pressure range of the addition of HO to HO. III. Saturated laser - induced fluorescence measurements between 200 and $7 0 0 \mathrm { K }$ ”J.Chem.Phys.105   
[13]Hong,Z.,R.D. Cook,D.F.Davidson and R.K.Hanson (2010).“A Shock Tube Study of $\mathrm { O H } \ + \ \mathrm { H } 2 \mathrm { O } 2 \ \cdot >$ $_ { \mathrm { H } 2 \mathrm { O } + \mathrm { H O } 2 }$ and $\mathrm { H } 2 \mathrm { O } 2 + \mathrm { M } \cdot > 2 \mathrm { O H } + \mathrm { M }$ using Laser Absorption of H2O and OH.”J. Phys. Chem.A 114: 5718- 5727.   
[14]Hong, Z., D. F. Davidson and R. K. Hanson (2011). “An improved H2/O2 mechanism based on recent shock tube/laser absorption measurements.’Combustion and Flame 158:633-644.   
[15]Hong,Z.,A. Farooq,E.A.Barbour,D.F.Davidson and R.K.Hanson (20o9).“Hydrogen Peroxide DecompositionRate:A Shock Tube StudyUsing Tunable Laser Absorption of H2O near 2.5 micro meter.”J.Phys.Chem.A 113:12919-12925.   
[16] Levine,I. N. (1991). Quantum Chemistry. Englew0od Cliffs,New jersey,Prentice Hall.   
[17]Meyer,E.,H.A. Olschewski, J. Troe and H.G.Wagner (1969).“Investigation of N2H4 and H2O2 decomposition in low and high pressure shock waves.” Symposium (International) on Combustion 12(1): 345-355.   
[18]Sajid, M.B.,E. Es-Sebbar, T. Javed,C.Fittschen and A. Farooq (2013).“Measurement of the Rate of Hydrogen Peroxide Thermal Decomposition in a Shock Tube Using Quantum Cascade Laser Absorption Near 7.7 micro meter.”International Journal of Chemical Kinetics 46(5): 275-284.   
[19]Sangwan,M.,E.N. Chesnokov and L.N. Krasnoperov (2012)."Reaction $\mathrm { O H + O H }$ Studied over the 298-834 K Temperature and $\mathrm { ~ 1 ~ - ~ } 1 0 0$ bar Pressure Ranges.” J. Phys. Chem.A116: 6282-6294.   
[20]Sellevag, S.R., Y. Georgievskii and J.A. Milller (2009). “Kinetics of the Gas-Phase Recombination Reaction of Hydroxyl Radicals to Form Hydrogen Peroxide.”J. Phys. Chem. A 113: 4457-4467.   
[21]Trainor, D.W. and C.W. J. v. Rosenberg (1974).“Flash photolysis study of the gas phase recombination of hydroxyl radicals.”J. Chem. Phys. 61.   
[22]Troe, J. and V.G. Ushakov (2008).“SACM/CT Study of the dissociation/recombination dynamics of hydrogen peroxide on an ab initio potential energy surface Part II. Specific rate constants $\mathbf { k } ( \mathrm { E , J } )$ ,thermal rate constants $\mathbf { k } \ : \mathbf { N }$ (T),and lifetime distributions.”Phys. Chem Chem Phys. 10: 3915-3924.   
[23]Versteeg,H.K.and W. Malalasekera (2007).An Introduction to Computational Fluid Dynamics,The Finite Volume Method.Harlow，England，Pearson，Prentice Hall.   
[24]Westbrook, C. K. (2000).“Chemical Kinetics of Hydrocarbon Ignition in Practical Combustion Systems.”Proceedings of the Combustion Institute 28:1563-1577.   
[25] Zellner,R.,F.Ewig,R. Paschke and G.Wagner (1988). “Pressure and Temperature Dependence of the Gas-Phase Recombination of Hydroxyl Radicals.”J.Phys. Chem. 92: 4184-4190.