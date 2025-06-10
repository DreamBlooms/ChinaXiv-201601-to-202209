# Thermal Analysis of Void Cavity for Heat Pipe Receiver under Microgravity

GUI Xiaohong1\*, SONG Xiange², NIE Baisheng

1. China University of Mining and Technology,Beijing 1Ooo83, China   
2.Beijing International Studies University, Beijing 1OoO24, China

$\mathfrak { C }$ Science Press and Institute of Enginering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

Based on theoretical analysis of PCM(Phase Change Material) solidification process,the model of improved void cavity distribution tending to high temperature region is established.Numerical results are compared with NASA (National Aeronautics and Space Administration)results.Analysis results show that the outer wall temperature, the melting ratioof PCMand the temperature gradient of PCM canister,have great diference in different void cavity distribution.The form of void distribution has a great efect on the process of phase change.Based on simulation results under the model of improved void cavity distribution,phase change heat transfer process in thermal storage container is analyzed.The main goal of the improved designing for PCMcanister is to take measures in reducing the concentration distribution of void cavity by adding some foam metal into phase change material.

# Keywords:Heat Pipe Receiver,Phase Change, Void Cavity Distribution

# Introduction

A heat pipe receiver with high temperature phase change material is a very important component for advanced solar dynamic power generation system during traversal of low earth orbit spacecraft through the dark phase of their orbit cycles.The main functions of the receiver are the absorption of solar energy,thermal energy storage(TES) for the dark period,and the heating of working gas [1-3].

A heat pipe receiver contains an array of heat pipes with mounted cylindrically toroidal thermal energy storage modules.A PCM canister is a basic thermal storage unit of a heat pipe receiver. Void cavity appears in canister when PCM freezes and shrinks.High temperature phase change material is commonly used as $8 0 . 5 \%$ LiF$1 9 . 5 \% \mathrm { C a F } _ { 2 }$ .Its void ratio is $8 \% - 2 2 \%$ .Since the thermal resistance of void cavity is very high,void cavity prevents phase change. Thermal spot and thermal ratcheting appear near the concentrated void cavity easily. Stress and creep deformation will appear with the effect of the thermal-structural coupling of void cavity and high temperature heat load. Thus the usage life of high temperature phase change thermal storage canister will decrease and even destroy. The thermodynamic performance of high temperature phase change material canister and compound phase change material canister need to be deeply studied. The influence of void cavity on thermal performance of PCM canister for heat pipe receiver undermicrogravity needs to be analyzed in detail.

# Structural Design and Working Principle of a HeatPipeReceiver

The heat pipe receiver design is shown in Fig.1 [4]

The receiver is constructed in three axial sections,a receiver portion,a TSD(Thermal Storage Device） portion,and a HSHX (Heat Source Heat Exchanger) por

# Nomenclature

<html><body><table><tr><td colspan="4">Nomenciature</td></tr><tr><td>A</td><td>area (m²)</td><td>S</td><td>source term</td></tr><tr><td>Amush</td><td>the mushy zone constant</td><td>T</td><td>temperature (K)</td></tr><tr><td>Cp</td><td>specific heat capacity at constant pressure (J/ (kg ·K))</td><td>t</td><td>time(s)</td></tr><tr><td>H</td><td>enthalpy (J/kg)</td><td>7 axial direction Greek letters</td><td></td></tr><tr><td>△H</td><td>latent heat of phase change (J/kg)</td><td colspan="2">volume expansion coefficient of liquid</td></tr><tr><td>h</td><td>sensible enthalpy (J/kg)</td><td></td><td>(1/K)</td></tr><tr><td>k</td><td>thermal conductivity (W/(m· K))</td><td></td><td>a small number(O.0o1） to prevent division by zero</td></tr><tr><td>L</td><td>the axial length (m)</td><td></td><td>turbulence quantity</td></tr><tr><td>Q</td><td>heat flux (W)</td><td>p Subscripts</td><td>density (kg/m³)</td></tr><tr><td>R</td><td>radial length (m)</td><td colspan="2"></td></tr><tr><td>Rco</td><td>radial length of canister outer wall (m)</td><td>hw</td><td>heat-pipe wall</td></tr><tr><td>Rthick</td><td>radial thickness of PCM (m)</td><td>Ref</td><td>reference</td></tr><tr><td>r</td><td colspan="3"></td></tr></table></body></html>

![](images/443cd877b4c2773cee9152354e7bdc29c2ca686a8d583ca5e99e6fe268032f57.jpg)  
Fig.1The configuration of the heat pipe receiver

tion.The first of these sections is located nearest the receiver aperture and includes no PCM canisters.Solar energy entering through the aperture strikes the central tubes directly. Inside the tube is a heat pipe working fluid The evaporated fluid then transports the energy into the remaining two sections.In the central section the tube is surrounded by PCM canisters,with a configuration much like those in the base case design.The central section contains $9 1 . 6 ~ \mathrm { k g }$ of $\mathrm { L i F } _ { 2 2 } \mathrm { C a F }$ divided into full length canisters (4.8-cm ID，8.2-cm OD， $^ { 7 1 - \mathrm { m } }$ length） surrounding each of the 2O tubes.

# Numerical Simulation of PCM Canister for Heat Pipe Receiver under Microgravity

# PhysicalModel

The heat transfer of PCM canister of thermal storage unit of the heat pipe receiver [5] includes

(1) Heat conduction among solid, liquid in PCM zone and saturated vapor in void cavity，heat conduction among PCM canister wall, fin and other enhanced heat additions,

(2)Radiation among the interfaces of void cavity with   
different temperature,radiation among different PCM   
crystals,and (3）Evaporation and condensation heat transfer be  
tween high- and low- temperature interface in void cavity.

The above process of heat transfer is transient. If all the above are considered,it is very difficult to solve the problem.To find easy solutions and simplify the calculations,some assumptions are made as follows when the heattransfer model of the PCMcanisteris built.

(1)The temperature along heat pipe wall is uniform.

(2)The initial void volume of thermal storage unit is fixed,and void cavity distributes in the region tending to high temperature during the process of solidification. Prior to the domestic and foreign simulation of the phase change process in PCM canister, the existence of void cavity is usually ignored,or void cavity is simply assumed to distribute in annual region near the outer wall of PCM canister (hereinafter referred as the model of simple void cavity distribution).In this paper, the distribution model of void cavity tending to high temperature region during the process of solidification is established by assuming that the volume of void cavity occupies $10 \%$ of the volume ofPCMcanister.The detailed method is as follows.The solidification process of liquid phase PCM in thermal storage container is firstly simulated in the condition of ignoring void cavity,and then，simulation results of temperature field and PCM solidification can be obtained.In the end, the model of void cavity distribution is established by selecting $10 \%$ of the volume of final solidification region as void cavity (hereinafter referred as the model of improved void cavity distribution). The model for improved void cavity distribution is more reasonable than that of the previously neglecting void cavity or simple void cavity distribution,and the calculation process is relatively simpler.

(3)Heat convection of liquid PCM is ignored.Natural convection disappears under microgravity.

(4)The contact resistance between the PCM canister and heat pipe wall is ignored.

(5)The surfaces of all void cavities are the ones of gray bodies with diffusion reflection.

# MathematicalModel

# Mathematical Model of PCM Zone [6] Energy Equation

For solidification-melting problems,the energy equation is written as

$$
\frac { \partial ( \rho H ) } { \partial t } + \nabla \cdot ( \rho \stackrel {  } { \nu } H ) = \nabla \cdot ( k \nabla T ) + S
$$

The enthalpy of the PCMis defined as

$$
H = h + \Delta H
$$

The sensible enthalpy of the PCMis defined as

$$
h = h _ { r e f } + \intop _ { T _ { r e f } } ^ { T } C _ { P } d T
$$

The liquid fraction of the PCMis defined as

$$
\left\{ \begin{array} { l l } { \displaystyle { \beta = 0 \qquad } } & { \mathrm { i f } \quad T < T _ { s d s } } \\ { \displaystyle { \beta = \frac { T - T _ { s d s } } { T _ { l q s } - T _ { s d s } } \qquad } } & { \mathrm { i f } \quad T _ { s d s } < T < T _ { l q s } } \\ { \displaystyle { \beta = 1 \qquad } } & { \mathrm { i f } \quad T > T _ { l q s } } \end{array} \right.
$$

The solution for temperature is essentially an iteration between the energy equation (Equation 1） and the liquid fraction equation (Equation 4). Directly using Equation(4） to update the liquid fraction usually results in poor convergence of the energy equation.In FLUENT 6.2,the method suggested by Voller and Swaminathan [7] is used to update the liquid fraction.

# Momentum Equation

The enthalpy-porosity technique treats the mushy region (partially solidified region） as a porous medium. The porosity in each cell is set equal to the liquid fraction in that cell.In fully solidified regions,the porosity is equal to zero,which extinguishes the velocities in these regions.The momentum sink due to the reduced porosity in the mushy zone takes the following form

$$
S = \frac { ( 1 - \beta ) ^ { 2 } } { ( \beta ^ { 3 } + \varepsilon ) } A _ { m u s h } { \stackrel {  } { ( } \nu - \nu _ { p u l l } ^ {  } ) }
$$

The mushy zone constant measures the amplitude of the damping. The higher this value, the steeper the transition of the velocity of the material to zero as it solidifies. Very large values may cause the solution to oscillate.

# Turbulence Equation

Sinks are added to all of the turbulence equations in the mushy and solidified zones to account for the pres ence of solid matter. The sink term is very similar to the momentum sink term (Equation 5).

$$
S = \frac { \left( 1 - \beta \right) ^ { 2 } } { \left( \beta ^ { 3 } + \varepsilon \right) } A _ { m u s h } \phi
$$

# Mathematical model for zone of void cavity [8]

Since the axial temperature gradient is very small, the temperature of void cavity is defined by radial steady heat transfer equation,

$$
\frac { 1 } { r } \frac { \partial } { \partial r } \bigg ( r \frac { \partial T } { \partial r } \bigg ) = 0
$$

The thermal conductivity of vapor in void cavity can be calculated according to the kinetic theory of gas.

$$
k _ { \nu } = 1 . 4 5 7 \times { 1 0 } ^ { - 3 } { \sqrt { T _ { \nu } } }
$$

# AnApproach to Solution [9]

Computationalfluiddynamics(CFD）software (FLUENT6.2)isused to simulatethe heat transfer of PCM canister of the heat pipe receiver. Software (GAMBIT 2.1) is used as a pre-processor. In FLUENT 6.2,the separate solver is used to solve the equations. Finite control volume(FCV) method is used to solve the above equations.Thus,non-linear differential equations arelinearized.Alternate direction iteration(ADI) method isused asamethod of solution.In FLUENT 6.2,a solidification-melting model upon the enthalpy-porosity method is specially provided to deal with phase changes.

# MeshGeneration

Fig.2 shows the geometric model and mesh divisions of thermal storage unit for heat pipe receiver with three kinds of void cavity distribution relevantly. The regions of PCM zone,void cavity and canister wall are plotted with the triangle meshes.The spacing of mesh is $0 . 5 \mathrm { m m }$

# Boundary andInitial Conditions

# Boundary Conditions

$$
z = 0 , \Delta H = 0
$$

$$
z = L , \Delta H = 0
$$

$$
r = R _ { C O } , \Delta H = 0
$$

$$
r = R _ { h w } , - k _ { h w } \frac { \hat { \sigma } T _ { h w } } { \hat { \sigma } z } = \pm Q ( T _ { h w } ) / A
$$

The boundary condition of heat pipe wall (canister inner wall) is taken as periodic various heat flux. The canister outer wall and sidewall areadiabatic with outside. In the void cavity, thermal radiation is considered.

![](images/dee53b2d73caf43795affbcee8db31f815abdb45ab743ad6595afb562b783434.jpg)  
Fig.2Geometric model and mesh divisions of thermal storage unit for heat pipe receiver with three kinds of void cavity distribution

The driving heat flux from the heat pipe wall to PCM canister is kept constant when the PCM thickness of the canister varies. The value of heat flux is positive during sunlight period,and it is negative during eclipse period. The heat flux is the function of heat pipe wall temperature during both sunlight and eclipse period.

# Initial Conditions

The initial temperature is set to 95O K.PCM is solid. Each orbit cycle consists of 94.61 minutes.The physical properties of the canister wall and phase change material are constant. The eutectic salt $8 0 . 5 \%$ LiF- $1 9 . 5 \% \mathrm { C a F } _ { 2 }$ selected as the PCM in our simulation,with a melting point of $1 0 4 0 \mathrm { K }$ ,and the cobalt-base super alloy Haynes 188 as the canister material.

The temperature of the heat sink is $2 0 0 ~ \mathrm { K }$ .The height of orbit is $5 0 0 \mathrm { k m }$ .The pressure of low earth orbit is $\bar { 1 0 ^ { - 8 } }$ $- 1 0 ^ { - 7 }$ Torr.

![](images/0cd16f9e41b94bcc0cae6ff1dcbd979ad7f86295420c0121116881322bb18a50.jpg)  
Fig.3Temperature fluctuations on heat-pipe wall and PCMcanister outer wall during orbital periods with three kinds of void cavity distribution

# Results and Discussion

# Comparative Analysis on Calculation Results under the ModelsofDifferentVoid CavityDistribution

Fig.3a,Fig.3b and Fig.3c show the temperature fluctuations on heat-pipe wall and PCM-canister outer wall during orbital periods by our simulation corresponding to the models of neglecting void cavity,simple void cavity distribution and improved void cavity distribution respectively. Fig.4 and Fig.5 show the fluctuations of temperature and liquid fraction in one steady period respectively.It can be seen that with the periodic variation of incident solar heat flux,heat pipe wall temperature attains the maximum at the end of sunlight,and attains the minimum at the end of eclipse.

heat pipe wall temperature for the model of simple void cavity distribution PCM canister outer wall temperature for the model of simple void cavity distribution heat pipe wall temperature for the model of improved void cavity distribution PCM canister outer wall temperature for the model of improved void cavity distribution 1080 - heat pipe walltemperature for the model of ignoring void cavity PCM canister outer wall temperature for the model of ignoring void cavity 1070 1060 K 1040 1030 1020 1010 1000 1 1 厂 0 10 20 30 40 50 60 70 80 90 Time/min

![](images/a50b69a12cfec4aeaae01a9874417e1118e10771e17608e1eb2888391717c585.jpg)  
Fig.4Temperature fluctuations of heat pipe wall and PCM canister outer wall in one steady period with three kinds of void cavity distribution   
Fig.5Liquid fraction in one steady period with three kinds of void cavity distribution

By comparison of the temperature change curve and liquid phase fraction distribution of PCM canister corresponding to three kinds of void cavity distribution,it can be seen that the outer wall temperature and the melting ratio of PCM have great difference under the models of neglecting void cavity， simple void cavity distribution and improved void cavity distribution.The form of void cavity distribution has a great influence on the process of phase change and thermal storage. The melting rate and effective utilization of PCM for three void cavity distributionmodels are shown in Table 1.

Table 1The melting ratio and effective utilization ratio of PCMfor three kinds of void cavity models   

<html><body><table><tr><td>Model of void cavity</td><td>Melting ratio of PCM</td><td>Effective utilization ratio of PCM</td></tr><tr><td>Ignoring void cavity</td><td>0.0612-0.97393</td><td>0.9127</td></tr><tr><td>Simple void cavity distribution</td><td>0.03405-0.8015</td><td>0.76745</td></tr><tr><td>Improved void cavity distribution</td><td>0.15998-0.9609</td><td>0.80092</td></tr></table></body></html>

It can be seen that the effective utilization ratio of PCM is the minimum,the middle,and the maximum respectively with the model of neglecting void cavity, simple void cavity distribution and improved void cavity distribution.

By the above comparative analysis,it can be found that different void cavity distribution model has a great influence on simulation results for the process of phase change thermal storage.Therefore,the establishment of a reasonable void cavity model is a precondition to improve the accuracy of simulation results.In the process of simulation,a simple void cavity model is used to assume that void cavity distributes in a uniform annular region close to the outer wall of thermal storage container, which simplifies the determination of void cavity region and mesh generation of geometric model, but this kind of void cavity distribution model is too simple,and will affect the accuracy of simulation results.The assumption of ignoring void cavity simplifies the calculation process greatly,but which is obviously inconsistent with the actual situation and makes the simulation results have great difference with the actual process of phase change thermal storage. The improved void cavity model is established on the basis of the theoretical analysis.The improved model tending to high temperature region is based on the actual solidification process.The model of improved void cavity distribution is more reasonable and reliable than that of ignoring void cavity and simple void cavity distribution. According to the main characteristics of phase change thermal storage during the above process. the improvement for the designing of PCM canister is necessary. The concentrated distribution of void cavity not only reduces thermal performance of PCM canister due to local heat resistance,but also generates thermal stress and influences structural reliability of thermal storage container due to large temperature gradient. Therefore, the main goal of the improved designing for thermal storage container is to take measures in reducing the concentration distribution of void cavity by adding some foam metal into phase change material. In addition, heat transfer in the container can be effectively enhanced by side wall,which needs to be fully considered in the structural designing of thermal storage container.

# Comparative analysis on our numerical results and NASA numerical ones

In NASA project [1O],the model of void cavity distribution is built by the assumption as follows.Void cavity distributes along the outer wall of thermal storage canister.During eclipse periods,PCM in the TSD region freezes.PCM releases latent heat to heat pipe.At the same time, PCM shrinks and void cavity appears. Since the temperature of PCM close to canister inner wall decreases more quicklythan that ofPCM closeto canister outer wall,PCM close to canister inner wall freezes earlier.PCM in canister freezes gradually along the radial from inner wall to outer wall. Most of void cavities appearnear the outer wall in canister.

In order to make a better comparison,the model of void cavity distribution for our simulation is the same with that for NASA project. Fig.6 shows a comparison between ournumerical results andNASAnumerical ones [10].In the comparison,it can be seen that the corresponding temperature differences between our simulation and NASA simulation on both heat-pipe wall and PCMcanister outer wall are small. The temperature-change trend of our numerical results agrees with that of NASA numerical ones.The difference is that phase change temperature of PCM(LiF) for our simulation is set to 1117- $1 1 2 5 \mathrm { ~ K ~ }$ ，which is more in line with the actual melting process of LiF. In NASA model, the phase transition temperature of $1 1 2 1 \mathrm { ~ K ~ }$ is adopted.The temperature fluctuation both on heat-pipe wall and in PCM canister remains less than $1 6 \mathrm { K }$ throughout a sunlight and dark cycle.

![](images/b97e5d684252c1af6fb62a9decaac62bc3df2e9f1e0e4a56139728cf5ab8588e.jpg)  
Fig. 6 Liquid fraction in one steady period with three kinds of void cavity distribution

# Conclusions

With both void cavity and phase change considered, PCM canister of heat pipe receiver is numerically simulated under microgravity. Some conclusions are as follows.

(1）The physical model and mathematical model of phase change during the process of heat transfer in thermal storage container are established.Based on theoretical analysis and calculation results of PCM canister during the process of solidification, the model of improved void distributionis established.

(2) The phase change thermal storage process is numerically simulated under the model of ignoring void cavity distribution，simple void cavity distribution and improved void cavity distribution. The calculation results for three kinds of void distribution are compared and analyzed.The results show that the form of void cavity distribution has a great effect on calculation results.

(3)Our simulation results are compared with NASA ones under the model of simple void cavity distribution. Theaccuracy of calculation model and method is verified. (4)Based on simulation results under the model of improved void cavity distribution，phase change heat transfer process in thermal storage container is analyzed. The main goal of the improved designing for PCM canister is to take measures in reducing the concentration distribution of void cavity by adding some foam metal into phase change material.

# Acknowledgement

The authors acknowledge the financial support providedbyNationalNatural Science FoundationofChina (Grant No.51476172).

# References

[1]Zhang L., Yu Z.T.,Fan L.W.,Wang W.J. (2013). An Experimental Investigation of the Heat Losses of a U-Type SolarHeatPipe Receiver of a Parabolic Trough Collector-Based Natural Circulation Steam Generation System. Renewable Energy,57(3),262-268   
[2]Thayer J.,Rosenfeld J.，Galbraith R.(2O13).Thermal Energy Storage for a Dish Stirling Concentrated Solar Power System.11th International Energy Conversion Engineering Conference,San Jose,California   
[3]Xiao L.(2O12).Convection Heat Loss Characteristics of the Heat Pipe Receiver in Solar Dish/AMTEC Thermal Power System,Ph.D. thesis, Chongqing University, China   
[4]Roger A.(1991).Evaluation of Thermal Energy Storage Devices for Advanced Solar Dynamic Systems.Journal of Solar Energy Engineering,113(4),138-145   
[5]Dong K.Y., Yuan X.G. (1998). Two-Dimensional TransientHeat Transfer AnalysisofaPhase Change Material Container. Taiyangneng Xuebao,19(1), 41-47   
[6]FLUENT Inc (2003).FLUENT 6.2 Users Guide Manual. Lebanon New Hampshire   
[7]Voller V.R.，Swaminathan C.R.(1991).Generalized Source-Based Method for Solidification Phase Change. Numerical Heat Transfer Fundamentals,19(2),175-189   
[8]Dong K.Y.(1998). Thermal Analysis of High Temperature Solid-Liquid Phase Change Thermal Energy Storage Container.Ph.D. thesis,Beijing University of Aviation and Aerospace,Beijing, China   
[9]Zhao Y.X. (2003). Tutorial of FLUENT. The Press for National Defense University of Science and Technology, Changsha, China   
10]Strumpf H.J., Coombs M.G. (1988).Advanced Heat Receiver Conceptual Design Study.NASA-88-25977,Lewis Research Center, Ohio,USA.