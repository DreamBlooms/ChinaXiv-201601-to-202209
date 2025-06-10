# Simulation of Unsteady State Performance of a Secondary Air System by the 1D-3D-Structure Coupled Method

WU Hong, LI Peng and LI Yulong \*

National Key Laboratory of Science and Technology on Aero-Engine Aero-Thermodynamics,Beihang University Xueyuan Road, 37,100191,Beijing, China

$\copyright$ Science Press and Institute of Enginering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2016

This paper describes the calculation method for unsteady state conditions in the secondary air systems in gas turbines.The 1D-3D-Structure coupled method was applied.A1D code was used to model the standard components that have typical geometric characteristics.Their flow and heat transfer were described by empiricalcorrelations based on experimental data or CFD calculations.A 3D code was used to model the non-standard components that cannot be described by typical geometric languages,while a finite element analysis was carried out to compute the structural deformation and heat conduction atcertain important positions.These codes were coupled through their interfaces.Thus,the changes in heat transfer and structure and their interactions caused by exterior disturbances can be reflected.The results of the coupling method in an unsteady state showed an apparent deviation fromthe existing data,while the results in the steady state were highlyconsistent with the existing data.The difference inthe results in the unsteady state was caused primarily by structural deformation that cannot be predicted by the 1D method.Thus,in order to obtain the unsteady state performance of a secondary air system more accurately and efficiently, the 1D-3D-Structure coupled method should be used.

# Keywords: Secondary air system, Unsteady,1D-3D-structure, Coupling, Gas turbine

# Introduction

The earliest exploration of one-dimensional (1D) fluid network calculations dates to 1936,when Cross[1] proposed the application of network iterations for the calculation of steady flow.In later decades，the theory and methods pertaining to this subject were integrated with experiments and improved gradually.A number of institutes and companies attempted to associate the theory of a flow network with engineering and developed a useful tool for complicated fluid networks.Yet it was not until the 199Os that the method of the flow network was truly adopted in the secondary air system of gas turbines.Kutz and Speer [2] reviewed a computer program for the simulation of a secondary air system.An algorithm for the solutions to the resulting nonlinear governing equations was introduced,and the loss correlations of the typical flow elements were also discussed.The results of the program were verified against test data with strong agreement.Muller [3] used the Newton-Raphson method to calculate the nonlinear equations for the set of unknown parameters, including total pressure, total temperature,mass flow rate,and others.Furthermore,the network was coupled within a thermo-mechanical finite element model of an engine's secondary air system structure with the free finite element software CalculiX. The results of the coupled investigation showed good agreement with test data, but heat transfer data were still derived on the basis of empirical correlations.Past research on secondary air systems focused mainly on steady state conditions [4]. However, the gas turbines in airplanes always work in unsteady state conditions that are caused primarily by the following:

1. Starting and stopping of the engines. 2. Change in rotational speed and power output. 3. Change in the altitude of the engine. 4.Fluctuations in the pressure and temperature at the outlet of the compressor. 5.Storage or dissipation of mass and energy in the system.

Moreover, the deformation of hot components may occur in concert with these factors and influence the flow and heat transfer inside the system.These phenomena can result in the ingress of gas into the cavities,which can destroy the pressure balance in the system.Hot parts may become overheated,and the efficiency of sealing can decrease as a result. Thus,whether or not the sec ondary air system can supply sufficient air cooling with proper pressure to prevent the system from failing becomes extremely important.In other industrial fields, such as petroleum,natural gas,internal-combustion engines,and pulse detonation engines,among others,research on unsteady state performance,such as water hammer, gas hammer, fuel injection, dynamic drainage, and pulse explosion,was carried out extensively by introducing the concept of“pressure wave and disturbance" into the calculations.Furthermore,methods pertaining to characteristics,finite difference,finite volume,and finite element were developed.

Since the 196Os,Benson andhis teamhave conducted research on unsteady state conditions in internal combustion engines and the calculation of characteristic sets of equations.In the 1970s,his team finished the UMIST program and published a monograph[7] that summarized the research on the method of characteristics.For a long period, the method of characteristics was the mainstream technique in 1D research of unsteady state conditions in internal combustion engines and in other industrial fields. With the development of computational techniques,the methods of finite difference,finite volume,and finite element have been applied more often,but the develop ment of boundary equations is still based primarily on the theory of characteristics [8]. The traditional 1D unsteady state methods can predict the unsteady effectiveness of the accumulation or dissipation of mass and heat inside the system, but for the structural deformation and resulting changes in flow, the 1D-Structure coupled method must be applied. For certain special and complicated structuresthat are difficult to describewith 1D correla tion, the 3D tool is used and finally coupled together with 1D and finite element analytical tools.

# Coupling Mechanism of Multi-physical Fields

For example,consider a two-fold physical phenomenon.When two different systems have their own governing equations, coupling is realized by the interaction of c and d.

![](images/b80d0a1650ba7e8dcaefb64b2d0bc3bfa9b8f90ee4a587e51a55b0e85e9828b2.jpg)  
Fig.1 Coupling of two different codes

The coupling zone indicates different physical boundaries for different codes.For the 1D and 3D flow fields, the zone indicates the interface between them; for the flow field and solid body, the zone denotes a real wall surface.Coupling methods include direct, sequential, and synchronous coupling[9]. The method of direct coupling contains only one analysis and uses a coupling unit with multi-field free degrees. Coupling is carried out by calculating the cell matrix or load vector that contains the relative parameters.The method of sequential coupling contains more than two sequential analyses,and each pertains to one type of physical field; coupling is carried out by interacting the results of one analysis with another. The method of synchronous coupling indicates that differentfieldsarecalculatedincoincidencewith eachother thus satisfying the boundary equations of each. This is strong coupling in the physical sense.

# 1D-3D Coupling

For the secondary air system in an aero-engine,an absolute 1D analysis has the following difficulties in predicting the performance of the system:

1.Some non-standard flow structures cannot be described with existing mathematical models,or the error is extremely large. 2.Performance data of different components are uncertain.Although they can be derived from experiments or CFD simulations, the real-time effect over a transient course cannot be reflected.

The joint simulation of 1D and 3D fluid dynamics shows the data transfer and iteration at the interface between the 1D and 3D flow networks.In a secondary air system, the accuracy of cavity modeling is rather important,while the structure of the cavity is always compli cated and variable,and thus 1D empirical correlations cannot describe the flow and course of heat transfer pre cisely or are limited to certain confined working conditions.Therefore,1D-3D coupling should be carried out to obtain more reliable results.A3D flow dynamics tool is used to model complicated cavities or other components, while normal parts or discrete losses are modeled with the 1D tool. Heat and flow boundary conditions are transferred between these two types of tools for flow dynamics.In this way, the unsteady state performance of asecondary air system can be derived.Figure 2 shows the scheme of the data transfer between Flowmaster,a commercial 1D flow dynamics code,and CFD code in which the interface is specified artificially. Mass flow rate, total pressure, total temperature,etc., are transferred through the two sides of the interface,and the results of the last iteration are transferred to the next iteration as boundary conditions [10].

Themethodsofdata transferat the interfaceare listed in Table 1.

>Flowdirection .--→Data from Flowmaster to CFD -→Data from CFD to Flowmaster 00000 00000 Three-dimensional P F CFD Model →   
Flowmaster bc: CFD bc: CFD bc: Flowmaster bc:   
Pressure source Mass flow inlet Pressure outlet Flow source   
Mass Flux Rate-- Mass Flow Rate.--> ↑.. Total Pressure ↑- Total Pressure

Table1 1D-3D data transfer on the interface   

<html><body><table><tr><td></td><td>1D to 3D</td><td>3D to 1D</td></tr><tr><td>Extensive Quantities (flowrate,velocity, etc.)</td><td>A Vi=p- A</td><td></td></tr><tr><td>Intensive Quantities</td><td></td><td></td></tr><tr><td>(pressure,temperature, etc.)</td><td>Vi=p</td><td>i=0 A</td></tr></table></body></html>

In Table1,A represents the boundary surface area of the 3D model,and $A _ { i }$ represents the unit area of each cell mesh on the boundary of the 3D model.Also in the table, $p$ represents the boundary value of the 1D model, and $\mathbf { V _ { i } }$ represents the unit value of each cell mesh on the boundary surface of the 3D model.For data transfers from the 1D to the 3D model, the mass flow rate is divided according to the percentage area of each cell face,while the pressure and temperature remain the same on each cell node.

# Fluid Solid Coupling

In essence,all of the unknown variables in the fluid field and solid field should be calculated at the same time within one timestep for fluid solid coupling,or so-called strong coupling,although weak coupling is another method of fluid solid coupling. Zhang and Hisada of Tokyo University [11] distinguished strong coupling and weak coupling theoretically,compared their calculating efficiency,and then,on this basis,used the single physical equation as a starting point and clarified the essence of strong coupling, weak coupling, and one-way coupling.

# Establishment and Condensation of Coupling Equations

When solving the problems of fluid solid coupling by the finite element method (i.e.,dispersing the fluid and solid fields by the finite element method),the boundary conditions are realized during the combination of elements. If $\Delta X$ is the variable increment in the coupling system,according to the difference in the physical field where the nodes lie,then the simplified coupling equa tions can be obtained, as shown below.

$$
\left[ \begin{array} { c c c } { { A _ { I I } ^ { f } } } & { { A _ { I C } ^ { f } } } & { { 0 } } \\ { { A _ { C I } ^ { f } } } & { { A _ { C C } ^ { f } + A _ { C C } ^ { s } } } & { { A _ { C I } ^ { s } } } \\ { { 0 } } & { { A _ { I C } ^ { s } } } & { { A _ { I I } ^ { s } } } \end{array} \right] \left( \begin{array} { c } { { \Delta X _ { I } ^ { f } } } \\ { { \Delta X _ { C } ^ { f s } } } \\ { { \Delta X _ { I } ^ { s } } } \end{array} \right) = \left( \begin{array} { c } { { R _ { I } ^ { f } } } \\ { { R _ { C } ^ { f s } } } \\ { { R _ { I } ^ { s } } } \end{array} \right)
$$

Where the superscripts $f$ and $s$ represent the fluid field and solid field,respectively,and the subscripts $C$ and $I$ represent variables on the coupling interface and interior nodes，respectively. $\boldsymbol { A } ^ { s }$ and $A ^ { f }$ are the equivalent mass matrices of the coupling system. $\Delta X _ { I } ^ { f } ~ , ~ \Delta X _ { C } ^ { f s }$ ，and $\Delta X _ { I } ^ { s }$ are the unknown number vectors on the nodes in the fluid field,coupling interface,and solid field,respectively. $R ^ { f } , R ^ { f s }$ ，and $\boldsymbol { R } ^ { s }$ are the external force vectors in the fluid field,coupling the interface,and solid field. There are two ways to solve the static force condensation in Eq (1):first,eliminate the interior variables inside the fluid field and then calculate the solid field in combination with the interface,or revise the interior variable vectors inside the fluid field; second,eliminate the interior variables inside the solidfield,andthen calculate the fluid fieldin combination with the interface or revise the interior variable vectors inside the solid field.

# Solution of Coupling Equations

Based on the uniform coupling equations and the method of condensation, strong coupling equations,coupling variables in linear coupling equations,and the revision of the variable vectors can be solved. Strong coupl ing must deal with transferred information.According to the difference in boundary information between the fluid and solid fields,the interface can be classified as the essential boundary and natural boundary. The essential boundary defines the kinematic conditions,such as velocity，displacement and other boundary information, while the natural boundary defines the external force conditions,such as pressure,pressure force,and so on. Unlike strong coupling，structure and fluid solvers are carried out alternately in weak coupling.According to the condensation method of coupling equations, there are four types of weak coupling methods:

1.The common solution of structure and interface (WCS):Take the interface as the natural boundary for the solid field calculation and the essential boundary for the fluid field calculation.

2. The common solution of fluid and interface (WCF): Because the free degree of the fluid field is much larger thanthatof the solidfield,in orderto solve the weak boundary conditions by WCS and additional huge time consumption of the mass matrix $A _ { a d d } ^ { f }$ caluation， the methodofWCF isadopted.The interface is taken as the natural boundary for the fluid field calculation and as the essential boundary for the solid field calculation.

3.The common solution of fluid, solid, and interface   
(WCFS): The interface is taken as the natural boundary   
forboth fluid and solid fields. 4.One-directional coupling:In some cases,the de   
formation of the solid is rather slight,so the influence on   
the fluid can be ignored. This method can be taken as the   
simplified WCS method when the mass matrix $A _ { a d d } ^ { f } = 0$ ．

# 1D-3D-Structure Coupling through MpCCI

For secondary air systems in gas turbines, there are always complicated flow structures, such as cavities with multi-connections.Because the flowand heat transfer in the cavities influence the system to a great extent, the model of the cavities must be very accurate.A1D model can model the cavity efficiently and simply, but the accuracy is mostly due to the embedded empirical correlations; thus, there exists much more uncertainty when this is applied to even more complicated structures.In order to obtain more reliable results for secondary air systems, this paper introduces a new method of coupling that integrates Flowmaster, Fluent and Abaqus through MpCCI. Fluent is used to model such complicated components as cavities,Flowmasterisusedtomodel the standard structures and discrete losses in the system,while Abaqus is imported to realize the bidirectional coupling of the flow network and structural network.As a result, the influence on the flow of sealing clearance changes caused by structural deformation,together with the influence of flow and heat transfer on the structure,can be taken into account.Furthermore,the method of 1D-3D-Structure coupling can eliminate the influence on the results of human factors when defining the boundary conditions at the interface of the fluid and solid fields artificially.

# 1D-3D-Structure Coupling of a Secondary Air System

Figure 5 shows the scheme of the flow network of the secondary air system in one type of gas turbine. Compressed air is imported into the conical stationary cavity through a circular array of foil nozzles and orifices.Next, the air flows into an annulus passage with an inner wall that rotates through two circular arrays of orifices. Following that, the air is divided into three branches.One branch discharges through a straight-through labyrinth seal at the left end of the passage.A second branch flows into the rotor-stator structure in front of the rotating disk through a straight-through labyrinth seal at the right end of the passage. Because of the centrifugal effect of rotation,this portion of the air is pumped out of the cavity through the rim seal and mixed with the mainstream gas. The third branch flows into the central rotating passage through a circular array of orifices,and then flows successively across round-sectional long orifices，discrete losses,and the rotor-stator structure at the back of the rotating disk,where it finally joins the mainstream gas through the rim seal structure.

The whole system contains standard structures,such as rotating orifices,straight-through labyrinth seals,and annulus passages,and non-standard components with volumes,such as rotor-stator structures.The former, together with non-standard discrete losses,are modeled by Flowmaster [12-16],while the latter are modeled by Fluent, so that the flow conditions can be reflected instantlyandmore reliably.Theinterface between them transfers relative boundary conditions.Furthermore,Abaqus is applied to conduct a structural analysis and is coupled with Fluent, thereby allowing the interaction of the fluid field and structure to be taken into account.For the system shown in Figure 5,the position of the fasten ing bolts influences the clearance gap of the labyrinth seals,as well as the flow and heat transfer performance. Therefore,the interaction of the structure and the flow system must be analyzed.

![](images/0bf9fb419039a6c04386bedc520d6fa869ef5e3005acb769823818ca186a8644.jpg)  
Fig.3Scheme of Fluid Solid Coupling

![](images/63c5c405b8cba7ec9f498edcbc56f94a15714cd22d4ccdece42054c2e34dc0c9.jpg)  
Fig.4Scheme of 1D-3D-Structure coupling through MpCCI

![](images/8b662d39f37a57560d30f01f4ce93944848b699a2107944bfcef98b37921c34c.jpg)  
Fig.5Scheme of the flow network of the secondary air system in one type of gas turbine

Figure 6 shows the structured grid of the flow field of the rotor-stator structures,and Figure 7 shows the finite element model of the rotating disk.

![](images/1f5b7214b6c7ced9914753ecca7f2efc00c98cc1e50709971ae9ee1d21e16d37.jpg)  
Fig.6Structured grid of the flow field of the rotor-stator structures

![](images/7f461c623f67fda439211e7a192b5e55a177a979b0226135554692ec5ce0c2b2.jpg)  
Fig.7Finite element model of the rotating disk

Figure 8 shows the modeling scheme of the flow paths of the secondary air system. The radial positions of each component are aligned with the nodes connected to the inlet and the outlet. This paper takes the starting process of the aero-engine as an example and analyzes the per formance in unsteady state conditions. The unsteady re sults are verified and compared with experimental data and simulation results in the steady state.

The standard structural components,including the foil nozzles,annulus passage,round orifices,labyrinth seals, and non-standard discrete losses were modeled in Flowmaster. Two structures of the rotor-stator were modeled in Fluent,and the structural rotating disk was modeled in Abaqus.MpCCI was used to build the topological relationship between different physical fields.Figure 9 shows the scheme of the 1D-3D-Structure coupling.

![](images/e2c8dcc6495a1f1d088f11b950152bc1ac03472cff2e5ff32f45995d23eaa34b.jpg)  
Fig.8Scheme of the flow paths of the secondary air system

![](images/45420bc81084d413fbd77ef6a973e5d41231678b05821551d41856e5b916a5d6.jpg)  
Fig.91D-3D-Structure coupling basing on MpCCI

# Simulation and Results

# Steady State

The boundary conditions in a steady state are shown in Table 2.Because the accumulation or dissipation of mass and heat need not be considered, the sealing clearance of the labyrinths can be taken as a constant.In this way, the influence of the structure can be neglected. The heat transfer takes place primarily on the wall of the cavities. The heat flow through the disk's outer boundary to the mainstream gas is given by existing data. Other walls can betakenasadiabatic.

Table 2Boundary conditions under steady state   

<html><body><table><tr><td>Ω (r/min)</td><td>Boundary</td><td>Press. (Pa)</td><td>Temp.(℃)</td></tr><tr><td rowspan="5">11440</td><td>Node 1</td><td>200114</td><td>374.20</td></tr><tr><td>Node 7</td><td>198113</td><td>374.20</td></tr><tr><td>Node 11</td><td>190751</td><td>376.67</td></tr><tr><td>Node 18</td><td>117017</td><td>377.25</td></tr><tr><td>Node 1</td><td>275048</td><td>414.90</td></tr><tr><td rowspan="4">15400</td><td>Node 7</td><td>272298</td><td>414.90</td></tr><tr><td>Node 11</td><td>258766</td><td>414.90</td></tr><tr><td>Node 18</td><td>130033</td><td>420.40</td></tr><tr><td>Node 1</td><td>432901</td><td>478.00</td></tr><tr><td rowspan="4">19800</td><td>Node 7</td><td>428572</td><td>478.00</td></tr><tr><td>Node 11</td><td>406025</td><td>485.31</td></tr><tr><td>Node 18</td><td>171318</td><td>487.01</td></tr><tr><td>Node 1</td><td>557501</td><td>517.40</td></tr><tr><td rowspan="4">22000</td><td>Node 7</td><td>551926</td><td>517.40</td></tr><tr><td>Node 1l</td><td></td><td></td></tr><tr><td></td><td>523774</td><td>526.36</td></tr><tr><td>Node 18</td><td>219152</td><td>528.44</td></tr></table></body></html>

Simulations in a steady state were carried out according to the working conditions listed in Table 2.The comparison of the pressure distribution between the results and experimental data is shown in Figure 1O. The comparison of the pressure change of some of the main components is shown in Table 3,while the comparison of the volumetric flow and temperature distribution is shown in Table 4.

These figures and tables show that the results of the simulations are highly consistent with the experimental data.The largest error in the pressure change,approximately $10 . 1 \%$ ,appears at the position of labyrinth seal 2 because its ratio in the whole system is very low and therefore this error is acceptable.The comparison shows that the calculation model can describe the flow characteristics of different components accurately. The temperature changes most significantly at the position of the rotor-stator structure,and the higher the engine's rotational speed,the greater the temperature increases through the rotor-stator. In the simulation in a steady state,the error is due primarily to the 1D calculation model and the codes themselves.Some simplifications mayalso contribute to the errors,such as the fact that the heattransferinsomediscretelossesandtheheattransfer between the rotor disk and the axis were not considered.

![](images/535c8edb84e75ba8d4f03e9bdf95d5385c2a31e76f46e5d8255f9cae91dae801.jpg)  
Fig.10Pressure distribution under steady state

Table 3Pressure change of some important components   

<html><body><table><tr><td>Ω (r/min)</td><td>Pressure change(Pa)</td><td>Laby seal 1</td><td>Rotor-stator 1</td><td>Rotor-stator 2</td><td>Discrete loss</td></tr><tr><td rowspan="3">11440</td><td>Test</td><td>10658</td><td>-1326</td><td>-915</td><td>41559</td></tr><tr><td>Calculation</td><td>10456</td><td>-1244</td><td>-1007</td><td>41785</td></tr><tr><td>Error (%)</td><td>1.89</td><td>6.18</td><td>9.14</td><td>0.54</td></tr><tr><td rowspan="3">15400</td><td>Test</td><td>19140</td><td>-2936</td><td>-1656</td><td>78039</td></tr><tr><td>Calculation</td><td>19234</td><td>-2814</td><td>-1701</td><td>78493</td></tr><tr><td>Error (%)</td><td>0.49</td><td>4.16</td><td>2.65</td><td>0.58</td></tr><tr><td rowspan="3">19800</td><td>Test</td><td>33342</td><td>-6598</td><td>-3120</td><td>146323</td></tr><tr><td>Calculation</td><td>33771</td><td>-7003</td><td>-3301</td><td>146133</td></tr><tr><td>Error (%)</td><td>1.27</td><td>5.78</td><td>2.45</td><td>0.13</td></tr><tr><td rowspan="3">22000</td><td>Test</td><td>43256</td><td>-9699</td><td>-4547</td><td>189856</td></tr><tr><td>Calculation</td><td>43315</td><td>-10137</td><td>-4671</td><td>189424</td></tr><tr><td>Error (%)</td><td>0.14</td><td>4.32</td><td>2.65</td><td>0.23</td></tr></table></body></html>

Table 4Volumetric flow rate and temperature distribution   

<html><body><table><tr><td rowspan="2">Ω (r/min)</td><td rowspan="2">Position</td><td colspan="3">Vol. Flow (m/s)</td><td colspan="3">Temperature(℃)</td></tr><tr><td>Test</td><td>Cal</td><td>Error (%)</td><td>Test</td><td>Cal</td><td>Error (%)</td></tr><tr><td rowspan="4">11440</td><td>Outlet of cavity 1</td><td>0.0275</td><td>0.0293</td><td>6.55</td><td>376.6</td><td>378.3</td><td>0.42</td></tr><tr><td>Outlet of cavity 2</td><td>0.00885</td><td>0.00835</td><td>5.65</td><td>377.2</td><td>380.1</td><td>0.76</td></tr><tr><td>Outlet of laby seal 2</td><td>0.00536</td><td>0.00518</td><td>3.36</td><td>374.2</td><td>374.4</td><td>0.05</td></tr><tr><td>Inlet of nozzles</td><td>0.0417</td><td>0.0428</td><td>2.64</td><td>374.2</td><td>-</td><td>，</td></tr><tr><td rowspan="4">15400</td><td>Outlet of cavity 1</td><td>0.0408</td><td>0.0432</td><td>5.89</td><td>419.4</td><td>421.9</td><td>0.60</td></tr><tr><td>Outlet of cavity 2</td><td>0.0122</td><td>0.0117</td><td>4.10</td><td>420.4</td><td>424.3</td><td>0.93</td></tr><tr><td>Outlet of laby seal 2</td><td>0.007</td><td>0.00667</td><td>4.71</td><td>414.9</td><td>415.2</td><td>0.07</td></tr><tr><td>Inlet of nozzles</td><td>0.06</td><td>0.06157</td><td>2.62</td><td>414.9</td><td></td><td></td></tr><tr><td rowspan="4">19800</td><td>Outlet of cavity 1</td><td>0.0628</td><td>0.0655</td><td>4.30</td><td>485.3</td><td>489.4</td><td>0.84</td></tr><tr><td>Outlet of cavity 2</td><td>0.0184</td><td>0.0172</td><td>6.52</td><td>487.0</td><td>492.5</td><td>1.13</td></tr><tr><td>Outlet oflaby seal 2</td><td>0.0102</td><td>0.0094</td><td>7.84</td><td>478.0</td><td>479.2</td><td>0.25</td></tr><tr><td>Inlet of nozzles</td><td>0.0914</td><td>0.0921</td><td>0.77</td><td>478.0</td><td></td><td></td></tr><tr><td rowspan="4">22000</td><td>Outlet of cavity 1</td><td>0.078</td><td>0.0813</td><td>4.23</td><td>526.4</td><td>533.2</td><td>0.01</td></tr><tr><td>Outlet of cavity 2</td><td>0.0227</td><td>0.0212</td><td>6.61</td><td>528.4</td><td>535.7</td><td>0.01</td></tr><tr><td>Outlet of laby seal 2</td><td>0.0127</td><td>0.0119</td><td>6.30</td><td>517.4</td><td>519.0</td><td>0.003</td></tr><tr><td>Inlet of nozzles</td><td>0.1134</td><td>0.1144</td><td>0.88</td><td>517.4</td><td></td><td></td></tr></table></body></html>

# Unsteady State

Using the startup of an engine as an example, this paper also investigated the unsteady state performance of the secondary air system by the 1D-3D-Structure coupling method,allowing the characteristics of flow,heat transfer, structure,and their interactions during the unsteady process to be predicted more reliably and accurately. Because the convergence and the speed of convergence during unsteady calculation are influenced greatly by the initial field, especially for the CFD model, the interactive iteration of boundary parameters may make the convergence of the calculation much harder. Thus,before the unsteady calculation is carried out,it is necessary to have the initial field ina steady state.

# Working conditions

Theunsteady factors that must be considered include rotational speed change of the engine, total pressure and total temperature at the inlet of the whole system, total pressure or static pressure at the outlet of the whole system,and so on. Figure 11 shows the speed curve of the engine during a 6Os startup process.

Accordingly, the boundary conditions of the secondary air system are shown in Figures 12 and 13.

Heat transfer in the system occurs primarily at the wall surface of the rotating disk. The heat flow between the outer disk surface and the mainstream gas is set according to the existing data. Other surfaces are taken as adiabatic.For the calculation in an unsteady state, the phenomena of mass and heat accumulation or dissipation are the main causes of unsteadiness in large systems.Moreover,the influence of structure must be considered for secondary air systems. Because there are many sealing structures in the system (for example, the labyrinth seal), its sealing clearance isas low as a fraction of a millimeter Thus,the deformation of relative components may influence the sealing efficiency considerably.

![](images/28a05886d37b8e5fb7de3a58599913108284ab2a48103f463dd8cff739e7b356.jpg)  
Fig.11 Speed curve of the engine during starting process

![](images/212015413eafd48c2cad599370012c806117d61bbc328d83610abbcb6d095e24.jpg)  
Fig.12Total pressure curve of boundary nodes

![](images/1c12f5870faee4dd013b689634e32ce160d4e4292651718ad91d40a11d191c21.jpg)  
Fig.13Total temperature curve of boundary nodes

# Results

It can be seen from Figure 5 that the rotational parts of labyrinth seal1 and labyrinth seal 2 are fastened on the rotating disk with a group of screw bolts.Thus, the radial deformation of the disk will influence the sealing clearance directly,and then further influence the flow characteristics of the entire system. Figure 14 shows the variations in the clearance of labyrinth seal 1 and labyrinth seal 2 during the startup of the engine.The deformation of the disk is due to the change in its centrifugal force and the consequent increase of thermal stress caused by the radial temperature difference.During this 6Os process. the clearance decreased by $0 . 1 2 \mathrm { m m }$ ，which accounts for $20 \%$ of the initial sealing gap,and its influence on flow is obvious.

Under the influence of the decrease of the clearance, the volumetric flowrate of the rotor-stator structures, labyrinthseal2,andthefoil nozzlesis shownovertime in Figures 15-18,respectively.In these figures,the results of 1D-3D-Structure coupling,1D-3D coupling that does not take into account the deformation of the structure, and the steady state are all included.

Ascan be seen from these results,if the structure is not coupled, then the clearance of the labyrinth seals remains constant.The scale of the system itself is too small to accumulate or dissipate much mass and heat, and so the results of 1D-3D coupling match those from the steady state well.In fact, the increase in engine speed and the radial temperature gradient decreases the sealing clearance of the labyrinths.As a result,the flow resistance increases,and the flowrate decreases.In this system, the flowrate of the branches that contain labyrinth seal 1 and labyrinth seal 2 decreases clearly by comparison to the flowrate in the steady state.Also, the decreasing amplitude increases gradually with the decrease in the sealing gap.At 6Os,the flowrate of these two branches decreases by $1 4 . 9 \%$ and $23 . 8 \%$ ，respectively，compared to the steady state,while the gross flow decreases by $1 5 . 3 \%$

![](images/515d49af7dff02281e16f1e93bba8d3ed28937d9290c02d8f654fda29ff75b32.jpg)  
Fig.14Sealing clearance of labyrinth seals

![](images/8548f9c85b7982b0ec1784bd20107906ecb6dd62bdeebfde6c2c58632b8c3f86.jpg)  
Fig.15Volumetric flowrate of rotor-stator 1

![](images/8851306e4f84d334501000db2b697ef8ea0cbccdf40a63d80b9152c45dbf8897.jpg)  
Fig.16Volumetric flowrate of rotor-stator 2

![](images/2f07f2cda94390ed9091a4cd1f9e4667963306841f65e348a81f477268c99430.jpg)  
Fig.17Volumetric flowrate of labyrinth seal 2

![](images/c5df6af8c3a107fe05fb2446b428a7eab0e9191feb8075f97647749298af15ce.jpg)  
Fig.18Volumetric flowrate of foil nozzles

![](images/37c6b92b1632f3bcdd6cbe3204a01a925777bfec38c7d1c1ed2ce698a9815559.jpg)  
Fig.19Temperature rise of rotor-stator 1

Under the same heat transfer conditions,the decrease in airflow is indicative of the decrease in dissipated heat. The radial temperature gradient inside the rotating disk mayincrease,as does the air temperature.As is shown in Figures 19 and 20,at the end of the 6Os process of engine startup,the temperature of the air from rotor-stator1 and rotor-stator 2 increases by $12 . 3 3 \%$ and $1 4 . 0 2 \%$ ，respectively,compared to that in the steady state.This indicates that the cooling efficiency of the secondary air is lower than predicted. Therefore,it is necessary to take into account the interaction of structure,heat,and flow.

![](images/b09c8776cee3dd022ce1451aa21821e2786b9843601a9df33639c40ab313b6da.jpg)  
Fig.20Temperature rise of rotor-stator 2

In addition to the axial sealing change caused by the change in radial force,if the system contains a radial sealing structure,the axial force must also be investigated.As shown in Figure 5,the sealing structure between nodes 15 and 16 adopts a radial sealing pattern, the flow capability of which may be influenced greatly by the axial force and clearance.However, because the sealing structure is assembled by the fixed constraint method,the total axial force caused by the pressure change in rotor-stator 2 is not sufficient to overcome the constraint.Thus,the influence of the axial force on the systemis verylimited.

In summary,in the traditional simulation method of a secondary air system in a steady state，flow and heat transfer are calculated successively and the influence of structure is separated as well. This is acceptable for predictions in the steady state.However, for the unsteady state,only the 1D-3D-Structure coupling method can integrate the flow,heat transfer,and structure calculations to provide the researchers with more reliable data with which to test this theory.

# Conclusion

This paper summarizes the basic theory and realization method of fluid solid coupling and 1D-3D coupling Based on the interface code MpCCI,Flowmaster,Fluent, and Abaqus were integrated.Thus, the flow, heat transfer, and solid network of a secondary air system may be integrated by the 1D-3D-Structure coupling method. First, 1D-3D coupling was applied to the simulation of the system in a steady state. The results of pressure were consistent with the test data.The greatest error in the pressure change $( 1 0 . 1 \% )$ appeared at labyrinth seal 2. Because this accounts for a very small percentage of the pressure change in the whole system, the error is acceptable.Furthermore,the largest errors in flowrate and tem perature between simulation and the test were $6 . 6 \%$ and $1 . 1 3 \%$ ,respectively.

Theresultsshowed that the 1D and CFD models describe the flow and heat transfer of the corresponding components accurately， while the 1D-3D-Structure coupling method is applied to the simulation of the system in the unsteady state.The results showed that the centrifugal force of the rotating disk increased with the engine speed,as did the radial temperature gradient inside the disk and the successive thermal stress.Thus, the disk deformed in the radial direction.The clearance of the labyrinth seals decreased,the flow resistance increased,and the flowrate decreased.At 6Os,the flowrates of the two branches that are connected with the labyrinth seals decreased by $14 . 9 \%$ and $23 . 8 \%$ ，respectively， by comparison to the data in the steady state.The gross flowrate of the whole system decreased by $1 5 . 3 \%$ ,as did the cooling effect.

During the unsteady state process, the temperatures of rotor-stator 1 and rotor-stator 2 increased by $12 . 3 3 \%$ and $1 4 . 0 2 \%$ ,respectively,compared to the data in the steady state.Thus,it is clear that it is necessary to introduce the 1D-3D-Structure coupling method into the unsteady state simulation of a secondary air system. Especially for small-scale aero-engines, the phenomena of mass and heat accumulation or dissipation are very weak.The unsteady state characteristics are reflected mainly in the interaction of flow,heat transfer,and structure.The 1D3D-Structure coupling method can predict the unsteady state process more reliably and accurately.

# Acknowledgements

This study was supported by funds from National natural science foundation of China (Grant No.51176004). The support is gratefully acknowledged.

# References

[1]Cross H.,(1936),Analysis of flow in networks of conduits or conductors,URBANA,University of Illinois Bulletin, Illinois.   
[2]Kutz K.J., Speer T.M.,(1994), Simulation of the secondaryair system of aero engines,ASME Journal of Turbomachinery, vol.116,pp.306-315.   
[3]Yannick Muller, (2oo9),Integrated fluid network-thermomechanical approach for the coupled analysis of a jet engine,In ASME Turbo Expo 2009:Power forLand, Sea and Air, Orlando,USA,ASME GT2009-59104.   
[4]Schallhorn P.A.，Hass N.E.,(2004),Forward looking pressure regulator algorithm for improved modeling performance within the generalized fluid system simulation program, In AIAA/ASME/SAE/ASEE Joint Propulsion Conference and Exhibit,Fort Lauderdale,USA,AIAA 2004-3667.   
[5]Salvo R.D.,Deaconu S.,Majumdar A.K., (2006),Development and implementation of non-Newtonian Rheology into the Generalized Fluid System Simulation Program (GFSSP),In AIAA/ASME/SAE/ASEE Joint Propulsion Conference and Exhibit， Sacramento，USA，AIAA 2006-4869.   
[6]McAmis R.W., Miller J.T., Burdette R.R., (1996),Modeling fluid flow networks,In AIAA/ASME/SAE/ASEE Joint Propulsion Conference and Exhibit,Lake Buena Vista,USA,AIAA 1996-3120.   
[7] Benson R S.,(1982), The thermodynamics and gas dynamics of internal combustion engines[M]. Oxford: Clarendon Press.   
[8]Morel T, Flemming MF, (1990), Characterization of manifold dynamics in the Chrysler 2.2 S.I. engine by measurements and simulation, In SAE,Detroit, USA, SAE Paper 900679.   
[9]Kolke A，Walhorn E,Hubner B,，Dinkler D,(2004), Strongly coupled analysis of fluid-structure interaction with free surface flow, Proceedings in applied mathematics and mechanics.4(1), pp. 338-339.   
[10]D.S.MILLER,(1996), Internal flow systems-2nd ed[M]. Cranfield, BHR Group Limited.   
[11]Qun Zhang,Toshiaki Hisada, (20o1),Analysis of fluid-structure interaction problems with structural buckling and large domain changes by ALE finite element method, Computer Methods in Applied Mechanics and Engieering. 1(1): 231-236.   
[12]W.F.McGreehan, M.J.Schotsch,(1988), Flow characteristics of long orifices with rotation and corner radiusing, Journal of Turbomachinery,110(4),pp.213-217.   
[13]G.J.Yoo,R.M.C.So,B.C.Hwang, (1991), Calculation of developing turbulent flows in a rotating pipe,Journal of Turbomachinery, vol.113, pp.34-41.   
[14]Riccardo Da Soghe, Bruno Facchini, (2011), Analysis of gas turbine rotating cavities by a one-dimensional model: definition of new disk friction coefficient correlations set, Journal of Turbomachinery, vol.133,pp. 021020-1-8.   
[15]Qinxue Tan, Jing Ren, Hongde Jiang,(2009)， Prediction of flow features in rotating cavities with axial throughflow by rans and les,In ASME Turbo Expo 2009: Power for Land, Sea and Air, Orlando, USA, ASME pp. GT2009-59428.   
[16]Hay N.,and Spencer A.,(1992),Discharge coefficients of cooling holes with radiused and chamfered inlets. Journal of Turbomachinery, vol.114, pp. 701-706.