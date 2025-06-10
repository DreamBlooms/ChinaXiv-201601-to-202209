# Computational Fluid Dynamics (CFD) Modeling of Heat Transfer in a Polymeric Membrane using Finite Volume Method

Muhammad Ahsan and Arshad Hussain

School of Chemicaland Materials Enginering (SCME),National Universityof Sciences and Technology (NUST),Islamabad,Pakistan

The efficiency,robustness and reliabilityofrecent numerical methods for finding solutions to flow problems have given rise to the implementation of computational fluid dynamics (CFD)as a broadly used analysis method for engineering problems like membrane separation system.The CFD modeling in this study observes steady and unsteady(transient) heat flux and temperature profiles in a polymeric (cellulose acetate) membrane.This study is novel due to the implementationofuser defined scalar (UDS)difusion equation by using user-defined functions (UDFs) infinite volume method (FVM).Some details of the FVMused by the solver are carefully discussed when implementing terms in the governing equation and boundary conditions (BC).The contours of temperature due to high-temperature gradient are reported for steady and unsteady problems.

# Keywords:Computational fluid dynamics,finite volume method,heat transfer,cellulose acetate based membrane

# Introduction

Computational methods have the ability for improving the understanding of flow problems in membrane separation systems.They have the proficiency of giving data on flow conditions at any point of the geometry without troubling the flow. Furthermore,the implementation of mathematical modeling expressively decreases the costs, risks,and time-related to performing repetitive experiments. One numerical method implemented for simulating fluid flow is known as computational fluid dynamics (CFD）[1-4].CFD has become a more commonly im plemented method in the research area of membrane science [5,6] Several researchers are using this tool in order to obtain understanding into the phenomena taking place inside membrane modules,to support the design process and increase the performance of modules.As an analysis method, CFD gives the permission to change fluid properties,operating conditions and geometric cha racteristicsof the flowchannelsinaflexible but defined way. The geometric parameters of the channels simulated can be changed deprived of the requirement to make and check new meshes. This signifies a major benefit of the CFD tool over traditional experimental methods.Also, flow data can be described at any point and time throughout the simulation,and the assessment of these flow variables is conceivable deprived of any trouble to the original flow [7,8]. Because of its easiness and minor computational requirements,many scholars have chosen CFD for modeling membrane in two and three dimensions,as is showed by the quantity of effort carried out in this area [9-13]. Consequently, CFD is currently recognized as a dependable technique,and progressively unsteady flow studies are developing,mostly finding decent similarity within calculated and experimental results [14].

Organic and inorganic materials are used to synthesize membranes for gas separation.In late 197Os commercial polymeric membranes i.e.polydimethylsiloxane，cellulose acetate,polyether sulphone etc. for gas applications became available [15].Membranes based on polymers establish extensive use in the separation of ${ \bf N } _ { 2 }$ ， $\mathrm { O } _ { 2 }$ and $\mathrm { C O } _ { 2 }$ at lower temperatures $( < 1 0 0 ^ { \circ } \mathrm { C } )$ . Though,several engineering methods include the production of gases at high temperatures.One case is the production of syngas (a mixture of carbon dioxide and hydrogen) through coal gasification or natural gas reforming [16]. Preliminary research directed to different ideas on the consequence of gas polarization which is linked with the reduction of the additional permeable gas species through the membrane. This consequence allows the increase of the less permeable gas on the feed side and have a tendency to increase in significance for membranes providing very high selectivities [17].But, it is reported that at high temperatures the gas-through-gas diffusivity in the feed stream is quite a few orders of higher magnitude than the diffusion of gases through the membrane, therefore decreasing concentration polarization [18].

Membrane gas system is an important separation process of chemical engineering. In this research，we focused on heat transfer through the domain of a 2D rectangular membrane using general scalar diffusion equation with mixed boundary conditions.This research covers the solution of steady and unsteady state problems with the formulation of boundary conditions for first order discretization technique.The UDF is integrated with FVM based CFD solver (ANSYS FLUENTTM) for the solution. The contours of rectangular membrane domain show the behavior of a temperature through a polymeric (cellulose acetate） membrane. The heat transfer problem of flow in a membrane is a less focused area, especially for high-temperature gradient due to its complexity This study is an effort to solve user defined scalar(UDS) diffusion equation to solve complex thermal diffusion phenomena in a membrane.

# CFD modeling

The heat transfer modeling and the phenomena of transport mechanisms are permanently linked with the fundamental properties of the material used to synthesize a membrane.A common principle of membrane operation is that there must be a driving force for a gas molecule to diffuse from the feed domain to the permeate domain. This driving force is generally expressed as a temperature gradient in the case of heat transfer in polymerbased membranes.The membraneis described asa zero-thickness wall. The first cell in the first row of a mesh on the feed side is considered as a source.Introducing the negative source and source term at two sides of the membrane permits the gas disappear from the feed domain via the membrane surface and emerge at the permeate domain. The mesh of membrane is developed by using GAMBIT TM. Grid size analysis is carried out using different mesh intervals.All the simulation results did not show any major difference.The selected membrane mesh is shown in Figure 1. The mesh consists of 8oO cells with the dimension of $0 . 0 5 \mathrm { m } \times 0 . 1 \mathrm { m }$

![](images/d98425649bc549b32cd89ecad0bddb55eefa684153686b7881eb78bd6d8c70f2.jpg)  
Fig.12D mesh of a membrane

FVM solver (ANSYS FLUENTTM) solves the transport equation for a user-defined scalar(UDS) in the same way as it solves the transport equation for a scalar in the core equations, such as a species mass fraction. The UDS capability can be used to implement a wide range of physical models.In this study,a model is developed to solve a general scalar diffusion equation （1）with the possible types of boundary condition (BC) at the boundary (or a part of the boundary) of the domain [19].

$$
c \frac { \hat { \mathcal { O } } \phi } { \hat { \mathcal { O } } t } - \nabla \big ( \Gamma \nabla \phi \big ) = S _ { \phi } , i n \Omega , t > 0
$$

The possible types of boundary conditions (BC) are as follows:

Dirichlet BC: $D _ { 0 } ,$ Neumann BC: $- \Gamma \left( \hat { \partial } \phi / \hat { c } n \right) = q _ { 0 }$ andmixed BC: $- \Gamma \big ( \hat { \sigma } \phi / \hat { \sigma } n \big ) = \ h _ { c } \left( \phi - \phi _ { \infty } \right)$ （204号

Here, $D _ { 0 } , \ q _ { 0 }$ and $\phi _ { \infty }$ are constant values. The boundary conditions for left-wall and top-wall are $q =$ $- \Gamma \left( \partial \phi / \partial n \right) = 0$ and $\phi = 3 0$ respectively. The following equation gives mixed boundary condition for right-wall and bottom-wall.

$$
- \Biggl ( \Gamma \frac { \partial \phi } { \partial n } \Biggr ) _ { w } = h _ { c } \left( \phi - \phi _ { \infty } \right)
$$

# Steady State modeling

Consider a steady-state scalar equation with constant $\Gamma$ and zero source term $( S _ { \phi } = 0 )$ )as follows:

$$
- \nabla \left( \Gamma \nabla \phi \right) = 0
$$

This is the Laplace's equation. Solving the Laplace's equation using the FVMUDS solver (ANSYS FLUENTTM) does not necessarily require user-defined functions (UDFs). We can activate the UDS from the graphical user interface.FVM solver UDS provides only Dirichlet and Neumann conditions for the boundaries.Hence,we need to use the UDF to apply the mixed boundary condition for the UDS equation.

# Formulation of mixed boundary conditions

For a generic cell $c 0$ adjacent to the boundary, the diffusive flux across the boundary face $f$ of the cell is expressed as follows:

$$
- \int _ { f } \Gamma \left( \frac { \partial \phi } { \partial n } \right) d S = \int _ { f } h _ { c } \left( \phi - \phi _ { \infty } \right) d S
$$

![](images/22a58e9a7b113c9c9b675f076b987833cb5a7e169f41fd6aff6500b2e54ecb68.jpg)  
Fig.2Schematic of a cell adjacent to a boundary

Using the mid-point rule of surface integral, the diffusive flux can be approximated as:

$$
- \Gamma _ { f } \left( \frac { \hat { \sigma } \phi } { \hat { \sigma } n } \right) _ { f } A _ { f } = h _ { c } \left( \phi _ { f } - \phi _ { \infty } \right) A _ { f }
$$

In FVM solver, the diffusive flux is approximated in two parts;in the first part primary gradient is evaluated implicitly along the line connecting the cell centroid $c 0$ to the centroid face $f .$ It is corrected by a secondary gradient (or cross diffusion) term evaluated explicitly by the gra dient obtained from the previous iteration $\overline { { \nabla \phi } }$ ：

$$
\begin{array} { l } { \displaystyle - \Gamma _ { f } \left( \frac { \partial \phi } { \partial n } \right) _ { f } A _ { f } \approx \Gamma _ { f } \underbrace { \left( \phi _ { f } - \phi _ { c o } \right) } _ { d r } \left( \frac { \vec { A } , \vec { A } } { \vec { A } , \overline { { e _ { s } } } } \right) } \\ { \displaystyle + \underbrace { \Gamma _ { f } \left( \overline { { \nabla \phi } } \cdot \vec { A } - \overline { { \nabla \phi } } \cdot \overline { { e _ { s } } } , \frac { \vec { A } , \vec { A } } { \vec { A } , \overline { { e _ { s } } } } \right) } _ { \mathrm { s e c o n a r y } } } \end{array}
$$

FVM solver provides specific macros for UDF which define the necessary geometrical variables of the cell and also calculate the secondary gradient term in equation (6). If we designate the secondary gradient term in equation (6) $\beta _ { 0 }$ and $\vec { A } , \vec { A } / \vec { A } , \overline { { e _ { s } } }$ as $\boldsymbol { A } _ { b e }$ ，equation (5） and (6) can be written as

$$
- h _ { c } \left( \phi _ { f } - \phi _ { \infty } \right) A _ { f } = \Gamma _ { f } \left( \frac { \phi _ { f } - \phi _ { c o } } { d r } \right) A _ { b e } + \beta _ { 0 }
$$

$\phi _ { f }$ can be expressed as follows:

$$
\phi _ { f } = \frac { \Gamma _ { f } \left( \frac { A _ { b e } } { d r } \right) - \beta _ { 0 } + h _ { c } A _ { f } \phi _ { \infty } } { h _ { c } A _ { f } + \Gamma _ { f } \left( \frac { A _ { b e } } { d r } \right) }
$$

The mixed boundary condition for the UDS is ready to be specified by boundary profile $\phi _ { f }$ in equation(8) through the UDF macro [20].

# Unsteady state modeling

The unsteady (transient) user-defined scalar equation is as follows:

$$
c \frac { \partial \phi } { \partial t } - \nabla \left( \Gamma \nabla \phi \right) = 0 , i n \Omega , t > 0
$$

It has to be solved with the same boundary conditions and given an initial condition. When the transient term is $\hat { \sigma } ( \rho \phi ) / \hat { \sigma } t$ ,FVM can readily handle this unsteady UDS term when you enable the unsteady solver (either first or second-order).But if the transient term of the user's equation is not the same as the given form,you must supply the unsteady term through the specific UDF macro.For example,in equation (9), $c$ is a variable.For an unsteady heat conduction problem in dimensional form it represents $\rho c _ { p }$ of the solid material.

In finite-volume methods,the transient term is first approximated by first or second order finite difference expression and then integrated with respect to the cell volume.The FVM solver expects this transient term to be moved to the right-hand side of the governing equation and included in the discretized equation as a source term.

# First-OrderUnsteady Formulation

The first-order finite-difference backwards differencing approximation gives:

$$
\frac { \partial \phi } { \partial t } \approx \frac { \phi ^ { n } - \phi ^ { n - 1 } } { \Delta t }
$$

Where, $\phi ^ { n }$ is the value of $\phi$ at the current time interval, $\phi _ { n - 1 }$ is the value at previous time level and $\Delta t$ is the time step size.Hence

$$
- \int c \frac { \hat { \sigma } \phi } { \hat { \sigma } t } d V \approx \underbrace { \left( - c \frac { \Delta V } { \Delta t } \right) } _ { A _ { p u } } \phi ^ { n } + \underbrace { c \frac { \Delta V } { \Delta t } } _ { S _ { u } } \phi ^ { n - 1 }
$$

where, $\Delta V$ is the volume of each individual cell, $A _ { p u }$ is the coefficient multiplying $\phi ^ { n }$ (the implicit part) and $S _ { u }$ the explicit part (because it is expressed by known values at the previous time-step). We can rewrite the volume integral of the unsteady term as:

$$
- \int _ { } ^ { } c \frac { \hat { \sigma } \phi } { \hat { \sigma } t } d V = A _ { p u } \phi ^ { n } + S _ { u }
$$

and it is ready to be coded in UDF as the unsteady macro.

In most existing types of CFD software based on FVM, this problem can be resolved by introducing source terms which are known as user-defined functions (UDF).The correctness of CFD model is very sensitive to the source term which can disturb the flow position of neighboring cells in both feed and permeate domains.

# Simulation setup and discretization

Table 1 shows values of different properties used in this research work. Figure 3 illustrate the solution procedure for steady and unsteady (transient) problems. A UDF written in C programming language is developed and compiled with FVM solver. The library functions based on UDF build and load during the execution of a CFD model.Heat transfer from a hot air to a cellulose acetate based membrane is a problem thatis aligned with the grid, the numerical diffusion will be certainly low, and so we can normally implement the first-order discretization scheme instead of the second-order scheme without any substantial loss of accuracy. The target of all discretization techniques like FVM is to develop a mathematical model to convert each term into an algebraic equation. Once implemented to complete control volumes in a particular mesh,we attain a full linear system of equations that requires being solved. There are no common criteria for examining convergence.Definitions of residual that are advantageous for one type of problem are occasionally deceptive for other types of problems. So it is a good idea to examine convergence by judging residual stages besides observingrelated integrated quantities such as heat transfer coeficient. Intel CoreTM i5 with 4GB RAM is used to solve the steady and unsteady problem.For steady state problem, the CFD model is run forl00 iterations.For unsteady problem,the step size is 0.1 seconds,a number of time steps are 2oo and maximum iterations per time step are 40.

# Results and discussion

The default convergence criterion for most problems in FVM solver (ANSYS FLUENTTM) is satisfactory. The scaled residuals should decrease up to ${ { 1 0 } ^ { - 3 } }$ for all equations except the heat equation for which the scaled residuals should decrease up to $1 0 ^ { - 6 }$ . Figure 4 shows that in this simulation the scaled residuals are decreased up to ${ { 1 0 } ^ { - 8 } }$ .Figure 5 illustrates the sum of facet values on a middle point. The middle point is created at the position (0.025，O.o5） in a rectangular grid of the membrane. ANSYS FLUENTTM is a cell centred solver, so it stores data based on the cell centered values.The only exception is boundary conditions which are stored in the facet centers.As the value of temperature remains constant after 40 iterations (Figure 5),we can consider the solution as converged.Figure 6 shows the contours of thermal diffusion from the feed side to a cellulose acetate based membrane due to a temperature gradient in a steady state problem.Figures 7-11 describe the contours of temperature diffusion in a membrane at various time steps for an unsteady state problem.The diffusion into the rectangular membrane from high to low temperature is clearly visible due to the use of mixed boundary condition.This has been observed that maximum thermal diffusion occurs in first five seconds and the maximum surfaced temperature of cellulose acetate based membrane reached up to $1 9 3 ^ { \circ } \mathrm { C }$ .The surface temperature increased up to $1 9 8 ~ ^ { \circ } \mathrm { C }$ in twenty seconds.The process of heat transfer from air to the membrane is also due to the motion of a fluid and diffusion of heat through the still boundary layer next to the membrane.

Table1Values of different properties used in CFD modeling   

<html><body><table><tr><td>Properties</td><td>Symbols</td><td>Values</td><td>Units</td><td>References</td></tr><tr><td>Thermal conductivity</td><td>Γ</td><td>0.167</td><td>W/(m. K)</td><td>[21]</td></tr><tr><td>Specific heatof thematerial</td><td>Cp</td><td>1451</td><td>J/(kg·K)</td><td>[21]</td></tr><tr><td>Heat transfer coefficient</td><td>hc</td><td>20</td><td>W/(m²·K)</td><td>[22]</td></tr><tr><td>Density (Air)</td><td>p</td><td>1.225</td><td>kg/m³</td><td>[23]</td></tr><tr><td>Viscosity</td><td>从</td><td>1.7894×10-5</td><td>kg/m-s</td><td>[23]</td></tr><tr><td>Material temperature</td><td>?</td><td>30</td><td>℃</td><td></td></tr><tr><td>Surrounding fluid (Air) tem-</td><td></td><td>303 200</td><td>K</td><td></td></tr><tr><td>perature at feed side</td><td></td><td>473</td><td>℃ K</td><td>[24]</td></tr></table></body></html>

# Conclusion

A CFD solution for heat transfer problem was formu lated to examine the performance of the thermal diffusion through the 2D rectangular cellulose acetate based membrane.The model was used to predict the steady and unsteady state problems in a membrane by solving the general scalar diffusion equation.In particular,we focused on high-temperature diffusion process in a membrane, which is industrially useful especially in chemical engineering. The FVM solver (ANSYS FLUENTTM） pro

(a) Start (b) Start ↓ ↓   
Create the geometry/ mesh Create the geometry/ mesh ↓ ↓ Read the mesh in a solver Read the mesh in a solver ↓ ↓ General solver settings Transient solver setings ↓ ↓ Set the UDS values Set the UDS values ↓ ↓ Compile the UDF Compile the UDF ↓ ↓   
Set the membrane properties Set the membrane properties ↓ ↓   
Set the boundary conditions Set the boundary conditions ↓ ↓ Iteration for steady state Iteration for unsteady state ↓ ↓ Post-processing Post-processing ↓ ↓ End End

![](images/9cef0d268ec7f7da497355c1994762627ab889f8c90195b3b8f78dc73eeafc45.jpg)  
Fig.4Residuals profile of UDS

![](images/4291ebdc9b63e69dbdd17fc9d031728d4c4bb0a8a391298839fb118432f8c4a7.jpg)

![](images/fd30f9d9d99407c8e770133c1b5159658c2ec41a3f259acfe62a1b89e541dbb6.jpg)  
Fig.3Solution procedure for(a) steady state (b） unsteady state problems

![](images/dc6b9cd9d67ab2105708b058da9df53a6c15751abc0533d37d138e1d91e0efb3.jpg)  
Fig.5Convergence history of sum of facet values on a middle point   
Fig.7Contours of temperature at time $\ O =$ 1 second

![](images/77630749593f945d21689b4f7436e82bb2116f48071d25e47a6abd60252c44e4.jpg)  
Fig.6 Contours of temperature for steady state problemin a membrane   
'ig.8Contours of temperature at time $: =$ 5 second

![](images/6b10fa8f413b0c94f84c9f8f9766e65031c3b838616cdf8cfa14756cfb84926d.jpg)  
Fig.9Contours of temperature at time $\ c =$ 10 seconds

![](images/5b2b46495631fcdb794a636f115faa5c70fcc17ece147eace0ae3d65151eb694.jpg)  
Fig.10 Contours of temperature at time= 15 seconds

![](images/135bb11ad40fce9142039cc5ca04d5d71324db8f7e184ed91c22cb9a2005a557.jpg)  
Fig.11 Contours of temperature at time= 20 seconds

vided the implementation of user-defined functions (UDFs) which have to be written in the C programming language. These UDFs were afterwards compiled for their use during solver execution for the solution of a problem. The residuals for the CFD model were decreased beyond the standard level in order to achieve more reliable results.The results for the steady and unsteady problems showed that the developed CFD modeling approach is capable of predicting heat transfer in the polymeric membrane.This model can be extended to use for the modeling of complex gas mixtures as well as mass transfer problems to narrow the gap between laboratoryand industrial scales.

# References

[1]Versteeg,H.K.，An introduction to computational fluid dynamics the finite volume method,2/E.1995:Pearson Education India.   
[2]Marriott,J.,E. Sorensen,and I.Bogle,Detailed mathematical modelling of membrane modules. Computers & Chemical Engineering,2001.25(4):p. 693-700.   
[3]Wiley,D.E.and D.F.Fletcher, Computational fluid dynamics modelling of flow and permeation for pressure-driven membrane processes. Desalination，2002. 145(1): p. 183-186.   
[4]Huang, L.and M.T. Morrissey, Finite element analysis as a tool for crossflow membrane filter simulation.Journal of membrane science,1999.155(1): p.19-30.   
[5] Ghidossi，R.,D.Veyret,and P.Moulin,Computational fluid dynamics applied to membranes: State of the art and opportunities. Chemical Engineering and Processing:

ΓIUUCss CISIvauUI, ∠Uvu.4J(U). ρ. 4)/ 4J4. [6]Bao,L.and G.G.Lipscomb,Well-developed mass transfer in axial flows through randomly packed fiber bundles with constant wall flux. Chemical Engineering Science, 2002.57(1): p. 125-132.   
[7]Lipscomb,G.G. and S.Sonalkar, Sources of Nonideal Flow Distribution and Their Effect on the Performance of Hollow Fiber Gas Separation Modules. Separation & Purification Reviews,2005.33(1): p.41-76. [8]Takaba, H. and S.-i. Nakao, Computational fluid dynamics study on concentration polarization in $\mathrm { H } <$ sub> $2 < \mathrm { / s u b > / C O }$ separation membranes. Journal of membrane science,2005.249(1): p.83-88. [9]Schwinge,J.,D.Wiley,and D.Fletcher,Simulation of the flow around spacer filaments between narrow channel walls.1.Hydrodynamics. Industrial & engineering chemistry research,2002.41(12): p.2977-2987.   
[10]Fletcher,D. and D. Wiley,A computational fluids dynamics study of buoyancy effects in reverse osmosis. Journal of membrane science,2004.245(1): p.175-181.   
[11]Cao,Z.,D.Wiley,and A. Fane,CFD simulations of net-type turbulence promoters in a narrow channel. Journal of membrane science,2001.185(2):p.157-176.   
[12]Geraldes,V.t., V. Semiao,and M.N. de Pinho,Flow and mass transfer modelling of nanofiltration．Journal of membrane science,2001.191(1):p.109-128.   
[13]Koutsou,C.,S.Yiantsios,and A.Karabelas,Numerical simulation of the flow in a plane channel containing a periodic array of cylindrical turbulence promoters. Journal of membrane science,2004.231(1): p.81-90.   
[14]Koutsou, C.,S.Yiantsios,and A. Karabelas,Direct numerical simulation of flow in spacer-filled channels:Effect of spacer geometrical characteristics. Journal of membrane science,2007.291(1):p.53-69.   
[15]Koros,W.and G.Fleming,Membrane-based gas separation. Journal of membrane science,1993.83(1):p.1-80.   
[16] McLellan,B.,et al.,Hydrogen production and utilisation opportunities for Australia. International journal of hydrogen energy,2005.30(6): p.669-679.   
[17]Zhang, J.,et al., Experimental and simulation studies on concentration polarization in $\mathrm { H } <$ sub> $2 { < } / { \mathrm { s u b } } >$ enrichment by highly permeable and selective Pd membranes. Journal of membrane science,2006.274(1):p.83-91.   
[18]Abdel-Jawad,M.,et al.,Flowfields on feed and permeate sides of tubular molecular sieving silica (MSS) membranes. Journal of membrane science,2007. 299(1): p. 229-235.   
[19] Fluent,A.,Fluent 6.3 User Guides:8.6 User-Defined Scalar(UDS) Diffusivity.Fluent Inc,2006:p.50-58.   
[20] Fluent,A.,Fluent 6.3 UDF Manual.Fluent Inc,2006.   
[21] Acetate,P.C. Properties: Cellulose Acetate. 2014 [cited Accessed June 2014]; Available from http://www. azom.com/properties.aspxArticleID $\scriptstyle 1 = 1 4 6 1$ ：   
[22] Ranges,H.t.Heat transfer coefficient 2O14 [cited Accessed June 2014; Available from http://www.engineeringtoolbox. com/convective-heat-transfer-d_ $_ { - } 4 3 0 . \mathrm { h t m l }$   
[23] Fluent,A.,Fluent 6.3 Tutorial Guides.Fluent Inc,2006.   
[24] Arthanareeswaran,G.,et al.,，Synthesis,characterization and thermal studies on cellulose acetate membranes with additive. European polymer journal,20o4. 40(9): p.2153- 2159.