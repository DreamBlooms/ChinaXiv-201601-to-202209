# Dynamic Characteristics of Hydrocarbon Fuel within the Channel at Supercritical and Pyrolysis Condition

YU Bin, ZHOU Weixing, QIN Jiang, BAO Wen

Harbin Institute of Technology, 15o001 Heilongjiang, China

Regenerative cooling with fuel as the coolant is used in the scramjet engine.In order to grasp the dynamic characteristics of engine fuel supply processes,this article studies the dynamic characteristics of hydrocarbon fuel within the channel.Aone-dimensional dynamic model was proved,the thermal energy storage efect, fuel volume effect and chemical dynamic effect have been considered in the model,the ordinary diferential equations were solved using a 4th order Runge-Kuta method.The precision of the model was validated by three groups of experimental data.The effects of input signal, working condition,tube size on the dynamic characteristics ofpressure, flow rate,temperature have been simulated.It is found that cracking reaction increased the compresibility of the fuel pyrolysis mixture and lead to longer responding time of outlet flow.The responding time of outlet flow can reach 3s when tube is $5 \mathrm { m }$ long which will greatly influence the control performance of the engine thrust system. Meanwhile, when the inlet flow rate appears the step change,the inlet pressure leads to overshoot, the overshoot can reach as much as $100 \%$ , such highly transient impulse will result in detrimental effect on fuel pump.

# Keywords: dynamic characteristics, n-Decane, supercritical, pyrolysis

# Introduction

Hydrocarbon-fueled scramjet has broad application prospect in the field of space transportation and military in the foreseeable futureli,2]l. The hydrocarbon carried by scramjet not only works as fuel for combustion,but also works as coolant345].Ashydrocarbon fuel flows through cooling channels of regenerative cooling system for scramjet, there is a dramatic variation in properties of hydrocarbon fuel, since both fuel temperature and pressure would change substantially,especially under the operating conditions with endothermic chemical reaction of hydrocarbon fuel[6,7].

As computational fluid dynamics (CFD) is becoming a powerful simulation tool[8], there has been significant interest in developing mathematical models for cooling channel, in an order to analyze the complicated interactions between the various factors and to optimize the system performance.Most of them focused on the steady characteristics1].T.A.Wardstudied thepresureeffects on flowing mildly cracked n-Decane at steady condition[9]. Silong Zhang introduced 3-D model of cracking coolant in cooling channel,and studied the thermal behavior in the cracking reaction zone at different aspect ratios[10]. Ward et al. conducted studies about the pressure effects on flowing mildly-cracked n-Decane using two dimensional model[11].

Other researchers investigated the transient dynamic characteristics[12,13,14,15]. Nicolas Gascoin developeda one-dimensional transient numerical model using a complete validated pyrolysis mechanism for n-dodecane[13]. Dahm K.D et al uses a full n-dodecane pyrolysis mechanism(1185 reactions and 153 species,designed by the French laboratory DCPR)[14]. However, each calculation costs too much hours and computing resource.This highlights the fact that CFD cannot be suitable for complete transient simulation with chemistry effects,particularly as an engineering tool on a single computer. Wen Bao conducted a one-dimensional unsteady model of hightemperature fuel supply tube containing chemical reaction of hydrcarobon fuel, and the model can reflect not only the dramatic variation in properties of hydrocarbon fuel caused by the changes of temperature and pressure in wide ranges,but also the coupling among flow, heat transfer and chemical reaction of hydrocarbon fuel15].Its simplified chemical mechanism greatly save the time to run a calculation without losing the capacity of analyze the flow and thermal characteristics of the cooling channel.Although various kinds of model has been built, none of the researchers has analyzed the transient dynamic characteristics of hydrocarbon fuel within the channel,and their effects on the fuel supply system and thermal protection has not been talked about.

The purpose of this paper is to study the dynamic characteristics of cooling channel during the engine working process,the one-dimensional unsteady model of high temperature fuel supply tube containing chemical reaction of hydrcarobon fuel in the paper[15] is used. The effects of input signal,working condition, tube size on the dynamic characteristics of pressure,flow rate, temperature have been simulated.The influence of transient dynamic characteristics on the engine fuel supply system and thermal protection has been discussed.

# Model and solving method

The model of hydrocarbon fuel within channel under supercritical pressures consists of two parts: one is the fluid flow in cooling channel, and the other is the properties of hydrocarbon fuel.

# Geometry model of cooling channel

A kind of cooling channel with rectangular cross section is usually used for hypersonic application, and Figure 1 shows the corresponding schematic diagram of a cooling channel, into which the heat flux that comes from engine is injected.Assuming that it is a 1D flow for coolant in the cooling channel and all the variations in the radial fuel properties and in the radial flow velocities can beneglected,byusinga hydraulic diameter d to characterize the cooling channel, the model of cooling channel is presented in detail below.

![](images/0250c69ad06bd8e9b55efd19b04171af44cdad6860f2dd32870aadb5933ab302.jpg)  
Fig.1 Schematic diagram of cooling channels with heat flux injected into

# Modeling of fluid flow in cooling channel

The set of PDE (partial differential equations) used to describe the 1D flow dynamics in a cooling channel is established by applying the conservations of mass,moment, and energy to an infinitesimal control volume.The mass conservation equation can be expressed as equation (1)

$$
\frac { \partial \rho } { \partial t } + \frac { \hat { c } \rho { u } } { \hat { c } { x } } = 0
$$

The heat generated by the viscous effect of fluid,axial heat conduction of fluid,and kinetic energy of fluid are usually much smaller than the radial heat which is injected into the fluid. Then, by neglecting those relatively smaller terms,the energy conservation equation can be expressed as equation (2)

$$
\frac { \partial } { \partial t } { \left( \rho h \right) } + \frac { \partial } { \partial x } { \left( \rho u h \right) } = \frac { 4 } { d } \cdot q _ { f }
$$

where ${ \bf q } _ { \mathrm { f } }$ is the convective heat between the fluid and the inner wall surface of the cooling channel. It can be expressed as equation (3)

$$
q _ { f } = \alpha \cdot \left( T _ { w } - T _ { f } \right)
$$

where $\alpha$ is a heat transfer coeficient determined by equations(4) and(5).Here,only a qualitative expression is given,and the specific heat transfer correlation employed in this study will be discussed later on. $\mathrm { { T _ { w } } }$ is the wall temperature of the cooling channel,and it is calculated through equation (6) by neglecting its radial temperature difference.Although axial heat conduction for the wall of the cooling channel is neglected, the axial wall temperature is still varying; so,expression $\partial T _ { w } / \partial t ,$ （20 instead of $\mathrm { { d T _ { w } / d t } }$ is used in equation (6)

$$
\alpha = \frac { \lambda } { d } \cdot N u
$$

$$
N u = f ^ { ' } \big ( R e , P r , \mu _ { f } , \mu _ { w } \big )
$$

$$
\boldsymbol { C } \cdot \boldsymbol { M } \cdot \frac { \partial T _ { w } } { \partial t } = \boldsymbol { Q _ { w } } - \boldsymbol { q _ { f } } \cdot \boldsymbol { A _ { i n n e r } } + \lambda _ { w } \cdot \boldsymbol { A _ { c s } } \cdot \frac { \partial ^ { 2 } T _ { w } } { \partial x ^ { 2 } }
$$

Re and $\mathrm { P r }$ used in equation(5) are expressed as equations(7） and(8),where vector $\mathrm { ~  ~ u ~ }$ has become a scalar through the absolute value transformation

$$
R e = \frac { \left| \rho \boldsymbol { u } \right| \cdot d } { \mu _ { f } }
$$

$$
P r = \frac { C _ { p } \mu _ { f } } { \lambda }
$$

Considering that cooling channel is horizontal, the momentum conservation equation can be expressed as equation (9),which contains expression $\lvert \mathrm { u } \rvert \mathrm { u }$ instead of ${ \mathrm {  ~ u } } ^ { 2 }$ to reflect the direction of fluid flow

$$
\frac { \hat { \sigma } } { \hat { \sigma } t } \big ( \rho \boldsymbol { u } \big ) + \frac { \hat { \sigma } } { \hat { \sigma } x } \big ( \big | \rho \boldsymbol { u } \big | \cdot \boldsymbol { u } \big ) = - \frac { \hat { \sigma } p } { \hat { \sigma } x } - \frac { 1 } { 2 } \cdot \frac { f } { d } \cdot \big ( \big | \rho \boldsymbol { u } \big | \cdot \boldsymbol { u } \big )
$$

where f is the friction coefficient and can be expressed as equation (10)

$$
f = \left\{ \begin{array} { c c } { { 6 4 / R e } } & { { R e \leq 2 3 2 0 } } \\ { { 0 . 1 1 \cdot ( { \displaystyle \frac { \delta } { d } } + { \displaystyle \frac { 6 8 } { R e } } ) ^ { 0 . 2 5 } } } & { { R e > 2 3 2 0 } } \end{array} \right.
$$

# ModelingofChemicalReaction

In this paper,n-Decane is chosen as a fuel compound for the present study because it is a typical pure liquid hydrocarbon fuel with1O carbon atoms in its molecule.It is the main component of hydrocarbon fuel and has carbon number and properties similar to those of liquid hydrocarbon material commonly used in aerospace applications.

The chemical formula of n-Decane is $\mathrm { C } _ { 1 0 } \mathrm { H } _ { 2 2 }$ and the criticaltemperatureandcritical pressureofn-Decaneare $6 1 7 . 7 \mathrm { ~ K ~ }$ and $2 . 1 1 ~ \mathrm { M P a }$ respectively. PPD model, which was firstly brought out by Ward et al. in Ref.[16],is adopted for the thermal cracking reaction in this paper. The details of product distribution got from the experimental table in Ref.[16] are shown in Table 1 and the values in the table are average results over many experiments. The products and their distribution in a general PPD model are kept unchanged while the pressure and the temperature change at a certain pressure range.

Table1Distribution of pyrolysis products of n-Decane [16]   

<html><body><table><tr><td>No.</td><td>Name</td><td>Formula</td><td>Mass fraction</td></tr><tr><td>1</td><td>Hydrogen</td><td>H2</td><td>0.0021</td></tr><tr><td>2</td><td>Methane</td><td>CH4</td><td>0.0162</td></tr><tr><td>3</td><td>Ethane</td><td>C2H6</td><td>0.0267</td></tr><tr><td>4</td><td>Ethylene</td><td>C2H4</td><td>0.0506</td></tr><tr><td>5</td><td>Propane</td><td>C3H8</td><td>0.0559</td></tr><tr><td>6</td><td>Propylene</td><td>C3H6</td><td>0.0682</td></tr><tr><td>7</td><td>n-butane</td><td>C4H10</td><td>0.0419</td></tr><tr><td>8</td><td>Butane</td><td>C4H8</td><td>0.0777</td></tr><tr><td>9</td><td>1-pentene</td><td>C5H10</td><td>0.0848</td></tr><tr><td>10</td><td>n-pentane</td><td>C5H12</td><td>0.0630</td></tr><tr><td>11</td><td>1-hexene</td><td>C6H12</td><td>0.1160</td></tr><tr><td>12</td><td>n-hexane</td><td>C6H14</td><td>0.0538</td></tr><tr><td>13</td><td>1-heptene</td><td>C7H14</td><td>0.1171</td></tr><tr><td>14</td><td>n-heptane</td><td>C7H16</td><td>0.0506</td></tr><tr><td>15</td><td>1-octene</td><td>C8H16</td><td>0.1199</td></tr><tr><td>16</td><td>n-octane</td><td>C8H18</td><td>0.0099</td></tr><tr><td>17</td><td>1-nonene</td><td>C9H18</td><td>0.0468</td></tr><tr><td>18</td><td>n-nonene</td><td>C9H20</td><td>0.0025</td></tr></table></body></html>

According to the general PPD model based on experimental data used in this paper, the cracking process can be approximated as an overall reaction which can be expressed as

$$
\begin{array} { r l } { C _ { 1 0 } H _ { 2 2 } } & {  0 . 1 5 1 H _ { 2 } + 0 . 1 4 3 C H _ { 4 } + 0 . 2 5 6 C _ { 2 } H _ { 4 } } \\ & { + 0 . 1 2 6 C _ { 2 } H _ { 6 } + 0 . 2 3 0 C _ { 3 } H _ { 6 } + 0 . 1 8 0 C _ { 3 } H _ { 8 } } \\ & { + 0 . 1 9 6 C _ { 4 } H _ { 8 } + 0 . 1 0 2 C _ { 4 } H _ { 1 0 } + 0 . 1 7 1 C _ { 5 } H _ { 1 0 } } \\ & { + 0 . 1 2 4 C _ { 5 } H _ { 1 2 } + 0 . 1 9 5 C _ { 6 } H _ { 1 2 } + 0 . 0 8 9 C _ { 6 } H _ { 1 4 } } \\ & { + 0 . 1 6 9 C _ { 7 } H _ { 1 4 } + 0 . 0 7 2 C _ { 7 } H _ { 1 6 } + 0 . 1 5 2 C _ { 8 } H _ { 1 6 } } \\ & { + 0 . 0 1 2 C _ { 8 } H _ { 1 8 } + 0 . 0 5 3 C _ { 9 } H _ { 1 8 } + 0 . 0 0 3 C _ { 9 } H _ { 2 0 } } \end{array}
$$

The cracking rate constant is generally a function of fuel temperature.In addition,according to Arrhenius expression, reaction rate $\mathbf { k }$ can be expressed as

$$
k = A \cdot e ^ { - { \frac { E _ { a } } { R T _ { f } } } }
$$

where $A$ and $E a$ are given in Table 2

Table 2 Reaction rate constants   

<html><body><table><tr><td colspan="2">Parent fuel</td><td>n-Decane</td></tr><tr><td rowspan="4">Ward et al.[16] P=3.45MPa and T=773-873K.</td><td>Activation energy</td><td>63</td></tr><tr><td>Ea, kcal/mol</td><td></td></tr><tr><td>A factor A,s-1</td><td>2.1×1015</td></tr><tr><td>Activation energy</td><td>63</td></tr><tr><td rowspan="3">Ward et al. [9] P=3.45-11.38MPa and T=823-873K.</td><td>Ea, kcal/mol</td><td></td></tr><tr><td>A factor</td><td>1.6×1015</td></tr><tr><td>A,s-1</td><td></td></tr><tr><td rowspan="3">Stewart et al. [17] P=2.96MPa and T=713-808K. A,s-1</td><td>Activation energy</td><td>64±2.4</td></tr><tr><td>Ea,kcal/mol</td><td></td></tr><tr><td>A factor</td><td>1.0×1015.9±1.5</td></tr></table></body></html>

The fuel in the cooling channel of a scramjet engine works under supercritical pressure with a wide temperature variation range,and the chemical reaction happens when the fuel flow through the cooling channel, increasing the complexity of fuel thermophysical properties prediction.

# Calculating method of mixture property

Peng-Robinson equation of state (Peng & Robinson, 1976),a Cubic Equation of State(CEOS),is used in this paper to predict the density of fluid in a wide range with a good prediction of the fuel properties near the critical points[18].

$$
P = \frac { R T } { V - b } - \frac { a } { V + 2 b V - b ^ { 2 } }
$$

where $P , T , V$ are the pressure, the temperature and the specific volume.Coefficients $a$ and $b$ can be calculated using the following equations.

$$
a = a _ { 0 } [ 1 + n ( 1 - ( T / T _ { c } ) ^ { 0 . 5 } ) ] ^ { 2 }
$$

$$
a _ { 0 } = \frac { 0 . 4 5 7 2 4 7 R ^ { 2 } T _ { c } ^ { 2 } } { P _ { c } }
$$

$$
n = 0 . 3 7 4 6 4 + 1 . 5 4 2 2 6 \omega - 0 . 2 6 9 9 2 \omega ^ { 2 }
$$

$$
b = { \frac { 0 . 0 7 7 8 0 R T _ { c } } { P _ { c } } }
$$

where $\mathrm { T _ { c } }$ and $\mathrm { \Delta P _ { c } }$ are the critical temperature and critical pressure, $\mathtt { R }$ is the universal gas constant and $\boldsymbol { \omega }$ is the acentric factor. The density is calculated by solving Eq.13，which can be regarded as a cubic equation with specific volume $\mathrm { v }$ as a variable.

For the thermal properties of fuel, for instance, specific heat $\mathrm { C p }$ ， they are calculated using relevant ideal gas properties and the departure functions. The departure function of any conceptual property F is defined as

$$
F _ { d e p } = F _ { i d e a l } - F
$$

where $\mathrm { F _ { i d e a l } }$ is the value of the property as computed from the ideal gas relations. The departure function can be derived from the basic thermodynamic relations and the equation of state.Ideal specific heatis needed for the calculation of specific heat $\mathrm { C p }$ .An ideal specific heat $\mathrm { C _ { p i d e a l } }$ is generally regarded as the function of temperature,which can be expressed as

$$
C _ { p i d e a l } / R = a _ { 0 } T ^ { 0 } + a _ { 1 } T + a _ { 2 } T ^ { 2 } + a _ { 3 } T ^ { 3 } + a _ { 4 } T ^ { 4 }
$$

As for the viscosity and thermal conductivity of the fluid, the method proposed by Chung et al. is adopted[19]. And compared with the conventional method, Chung's method takes the high pressure and high density of the fluid into consideration to avoid a large relative error.

Parameters such as $M , V c , T c , P c , \omega$ are the molecular weight, critical specific volume,critical temperature, critical pressure and the acentric factor used for the calculation of fuel properties respectively and the parameters for the species in Eq.11 can be found in open litera ture.

The property-evaluation methods briefly described in this section have been used to calculate the thermodynamic and transport properties of n-Decane, including its density, specific heat, viscosity, and thermal conductivity. The methods have been validated using the NIST da$\tan ^ { [ 2 0 ] }$ in Ref. [21].

As shown above, the ways to calculate the real properties of n-Decane and its crack products have been calculated and verified.However, the fuel will become a mixture of itself and its crack products when the crack reaction happens. So,it is very important to calculate the real properties of the mixture.

A pseudo critical method is used in this paper for the computation of properties in a real-gas mixture and it can be found in Ref.[22]. According to this method, the behavior and properties of a real gas mixture will be the same as that of a pure component, to which appropriate critical constants are assigned. These mixture critical constants are the functions of the mixture composition and pure component critical properties,and are sometimes called pseudo critical constants,because their values are generally expected to be different from the true mixture critical constants that may be determined experimentally. However, for computational purposes, they are the appropriate critical constant values for the mixture.

According to the pseudo critical method,Eq.13 is also applied for mixtures,where the critical temperature,critical pressure,critical specific volume,and acentric factor, are replaced by the corresponding mixture critical constants,critical temperature,critical pressure,critical spe cific volume,and acentric factor of the mixture.

One-fluid van der Waals mixing rules[23] are used for the mixture.According to this approach,in order to apply the equation of state models to the mixtures, coefficients a and b in Eq.13 are replaced by the following composition-dependent expressions:

$$
\begin{array} { c } { { a _ { m } ^ { 0 . 5 } = \sum _ { i } x _ { i } { ( a _ { i } ) } ^ { 0 . 5 } } } \\ { { b _ { m } = \sum _ { i } x _ { i } b _ { i } } } \end{array}
$$

the critical parameters of mixture can be expressed as

$$
T _ { c m } = \frac { \left[ \sum _ { i } \left( x _ { i } \frac { T _ { c i } } { P _ { c i } ^ { 0 . 5 } } \right) \right] ^ { 2 } } { \sum _ { i } \left( \frac { x _ { i } T _ { c i } } { P _ { c i } } \right) }
$$

$$
P _ { c m } = { \frac { T _ { c m } } { \displaystyle \sum _ { i } \Biggl ( { \frac { x _ { i } T _ { c i } } { P _ { c i } } } \Biggr ) } }
$$

$$
V _ { c m } = \sum \frac { x _ { i } P _ { c i } V _ { c i } } { T _ { c i } } ( \frac { T _ { c m } } { P _ { c m } } )
$$

The following are the notation for Eqs.

$T _ { c m } { = }$ mixture pseudo critical temperature. $P _ { c m } { = }$ mixture pseudo critical pressure. $V _ { c m } { = }$ mixture pseudo critical molar volume. $T _ { c i } { = }$ critical temperature for component $i$ $P _ { c i } { = }$ critical pressure for component $i$ $V _ { c i } { = }$ critical molar volume for component $i$ $x _ { i } =$ mole fraction for component $i$

The numerical model and property-evaluation methods have been implemented into a commercial CFD package,Fluent, through its user coding capability.

# Numerical calculation method of equations

All the above PDEs are solved by finite difference method. Firstly turned to ODEs by discretizing space with forward difference format, then the set of ODEs can bedirectly solved based on Simulink with suitable boundary conditions,and initial conditions.The details for solving the cooling channel model are shown below.

![](images/ae0b22ab5c5a7ff6bc0f9888820068a626e638dac8c200412484542aefead60f.jpg)  
Fig.2Schematic diagram of space dimension discretization with boundaryconditions

Take mass conservation equation for example,the space dimension is divided into n equipartitions,and generates $\mathtt { n } { + } 1$ nodes.Point O is considered as a boundary point,and point i represents one of the middle mesh points. By applying a first-order difference scheme (backward difference scheme) into spatial derivative only, equation（1) can be converted to equation(13) which is a set of ODEs belonging to a series of mesh points

$$
\frac { d } { d t } \left( \left[ \begin{array} { c } { \rho _ { 1 } } \\ { \rho _ { 2 } } \\ { \vdots } \\ { \rho _ { n } } \end{array} \right] \right) + \frac { 1 } { \Delta x } \cdot \left( \left[ \begin{array} { c } { \left( \rho u \right) _ { 1 } } \\ { \left( \rho u \right) _ { 2 } } \\ { \vdots } \\ { \left( \rho u \right) _ { n } } \end{array} \right] - \left[ \begin{array} { c } { \left( \rho u \right) _ { 0 } } \\ { \left( \rho u \right) _ { 1 } } \\ { \vdots } \\ { \left( \rho u \right) _ { n - 1 } } \end{array} \right] \right) = 0
$$

Similarly, by applying backward difference scheme into the spatial derivative of the energy conservation equation,equation(2） can also be converted into a set of ODEs as equation (14)

$$
\begin{array}{c} \begin{array} { l } { \displaystyle \frac { d } { d t } \left( \left[ \left( \rho h \right) _ { 1 } \right] \right) + \frac { 1 } { \Delta x } \left( \left[ \left( \rho u h \right) _ { 1 } \right] \right) = \left( \begin{array} { c } { \left( \rho u h \right) _ { 0 } } \\ { \left( \rho u h \right) _ { 0 } } \\ { \vdots } \\ { \left( \rho h \right) _ { n } } \end{array} \right) } \\ { \displaystyle = \frac { 4 } { d } \left[ \begin{array} { c } { q _ { f 1 } } \\ { q _ { f 2 } } \\ { \vdots } \\ { q _ { f n } } \end{array} \right] } \end{array} + \frac { 1 } { \Delta x } \left( \left[ \begin{array} { c } { \left( \rho u h \right) _ { 1 } } \\ { \left( \rho u h \right) _ { 2 } } \\ { \vdots } \\ { \left( \rho u h \right) _ { n } } \\ { \left( \rho u h \right) _ { n } } \end{array} \right] - \left( \begin{array} { c } { \left( \rho u h \right) _ { 0 } } \\ { \left( \rho u h \right) _ { 1 } } \\ { \vdots } \\ { \left( \rho u h \right) _ { n - 1 } } \end{array} \right) \right)  \\ { \displaystyle } \\ { \displaystyle = \frac { 4 } { d } \left[ \begin{array} { c } { q _ { f 1 } } \\ { q _ { f 2 } } \\ { \vdots } \\ { q _ { f n } } \end{array} \right] } \end{array}
$$

Finally,applying backward difference scheme and forward difference scheme into term $\partial ( \int \rho u \vert u ) / \partial x$ and term $\hat { c } p / \hat { c } x$ of the momentum conservation equation, respectively, equation (9) can be converted into a set of ODEs as equation (15)

$$
\begin{array}{c} \begin{array} { c } { { \displaystyle \frac { d } { d t } \left( \left[ \left( \rho { \boldsymbol { u } } \right) _ { 1 } \right] \right) + \frac { 1 } { \Delta x } \left( \left[ \left( \rho { \boldsymbol { u } } \boldsymbol { u } \boldsymbol { \cdot } \boldsymbol { u } \right) _ { 1 } \right] - \left( \left( \left| \rho { \boldsymbol { u } } \right| \boldsymbol { \cdot } \boldsymbol { u } \right) _ { 0 } \right) \right) } } \\ { { \displaystyle \frac { d } { d t } \left[ \left( \rho { \boldsymbol { u } } \right) _ { 2 } \right] + \frac { 1 } { \Delta x } \left( \left[ \left( \rho { \boldsymbol { u } } \boldsymbol { u } \boldsymbol { \cdot } \boldsymbol { u } \right) _ { 2 } \right] - \left( \left( \left| \rho { \boldsymbol { u } } \boldsymbol { u } \boldsymbol { \cdot } \boldsymbol { u } \right) _ { 1 } \right) \right) \right)} } \\ { { \displaystyle \qquad \vdots } } \\ { { \displaystyle = - \frac { 1 } { \Delta x } \left( \left[ \begin{array} { c } { { \displaystyle p _ { 2 } } } \\ { { \displaystyle p _ { 3 } } } \\ { { \displaystyle \vdots } } \\ { { \displaystyle p _ { n + 1 } } } \end{array} \right] - \left[ \begin{array} { c } { { \displaystyle p _ { 1 } } } \\ { { \displaystyle p _ { 2 } } } \\ { { \displaystyle \vdots } } \\ { { \displaystyle p _ { n } } } \end{array} \right] \right) - \frac { 1 } { 2 } \cdot d \cdot \left[ \left( \left| \rho { \boldsymbol { u } } \right| \boldsymbol { \cdot } \boldsymbol { u } \right) _ { 1 } \right] } } \\ { { \displaystyle f _ { n } \cdot \left( \left| \rho { \boldsymbol { u } } \right| \boldsymbol { \cdot } \boldsymbol { u } \right) _ { n } } } \end{array}    \end{array}
$$

# Validation of the model

As shown in Fig. 3,an experimental set-up is built to investigate the flow characteristic,heat transfer and cracking characteristics of hydrocarbon fuel under supercritical conditions.

![](images/fbbc517d035fdaec16107776e2cb732aebca686d1018bffc8e3302cd12279cb5.jpg)  
Fig.3Single tube test apparatus schematic with preheater he facilities consist primarily of a fuel reservoir,a fuel pump,a fuel reactor (tube),an electric heating power

anda fuel cooler. The tube section can easily heat fuel to $1 0 0 0 \mathrm { K }$ .The test section is a GH3128 superalloy pipe.

The pump is a constant-flux pump which can provide constant and continuous flow flux.The flow rate is not affected by the load pressure with a safety pressure as high as $4 0 \mathrm { M P a }$ .The range of the flow is $0 { - } 8 0 ~ \mathrm { m l / m i n }$

The test section is placing at the experimental table horizontally. The two ends of the pipe are wrapped with two copper electrodes.The pipe is heated by a direct current supply the power of which can be $3 ~ \mathrm { k W } .$ The power used to heat the pipe can be adjusted by changing the voltage and electric current.

The pipe wall temperature distribution is measured using K-type thermocouples spot-welded to the outside of the pipes.In order to increase the accuracy of the welded thermocouple,each thermocouple was checked by heating the test section. The temperatures along with the tube are equal theoretically when the tube firstly heated withoutfuel to obtain the heatloss.The fuel temperatures at the center point of the pipe inlet and outlet are measured using a thermocouple inserted into the flow of fuel. Fuel pressure is measured with pressure gauges installed at the outlet of the pump and upstream back pressure valve,and the pressure drop is measured with Rosemount 3051 transducer produced by Emerson Company.Fuel mass flow rate is measured byMicroMotion $\mathrm { C M F ~ } 0 1 0$ mass flow meter produced by Emerson Company with uncertainty less than $\pm 0 . 1 \%$ . The uncertainty associated with the measurement of wall temperature and the temperature offuel is estimated to be less than $\pm 3 \mathrm { ~ K ~ }$ ，whereas that of pressure measurement is less than $1 \%$ and that of the pressure drop measurement is less than $10 . 0 7 5 \%$ [24,25]. The error of the pressure dropis much lower than that of pressure measurement it is because that the sensor used to measure the pressure drop has a better accuracy than that used for pressure measurement (Pressure sensor produced by Micro Sensor Co.,Ltd.）All the experimental data are recorded via a data acquisition system for analysis.

The liquid and gaseous components of the fuel are separatelymetered and analyzed.The gas products are analyz ed using a gas chromatograph/mass spectrometry (GC7900/ MS),which consists of flame ionization and thermal conductivity detectors,and the liquid portion of the stressed fuel is analyzed by liquid chromatography (LC).

Two groups of experiments were conducted. The operating condition of the experiments used to validate the model is as follows: The back pressure is $3 \mathrm { M P a }$ ，the mass flow rate of n-Decane is $0 . 7 ~ \mathrm { g / s }$ ，the inlet fuel temperature is $2 9 3 \mathrm { K }$ and outlet fuel temperature is 773K. The length of the pipe is $1 \mathrm { m }$ with inner diameter being $1 \mathrm { m m }$ and outer diameter being $3 \mathrm { m m }$ =

The first group of experiment is under the condition of inlet flow rate step change,it change from $0 . 4 \mathrm { g / s }$ to $1 \mathrm { g / s }$ (Figure 4).The second group of experiment is under the condition of outlet throttle valve opening step change, it change from $50 \%$ to $5 5 \%$ (Figure 5). Comparison resultsshowthe calculateddatais similarto themeasured data,the reason of dynamic characteristics will be explained below.

# Results and discussion

To study the effect of transient dynamic characteristics of cooling channel on rapidity and safety of the engine, two kinds of perturbation are used in the simulation. The input signal of mass flow rate is used to simulate the engine fuel supply process,and the change of outlet tube throttle coefficient is used to simulate the switching of flow rate valve at the outlet of the cooling channel.During the calculation,the structure parameters and initial stable conditionsare listed in Table3.

![](images/8bdace384a75a281a84f52376a2b0207a83afdf681f6c6bff38d522790353b1c.jpg)  
Fig.4Comparison of calculated and measured data when inlet flow step change

![](images/4ec30709731e7409be4e5c634c0c83796c1b0320045b65c0bdd71ad05bba269a.jpg)  
Fig.5Comparison of calculated and measured data when outlet throttle valve opening step change

Table 3The structure parameters and initial stable conditions of calculations   

<html><body><table><tr><td colspan="2">Structure parameters</td></tr><tr><td>Tube length</td><td>1m</td></tr><tr><td>tube wall outer diameter</td><td>4 mm</td></tr><tr><td>inner diameter</td><td>2 mm</td></tr><tr><td>metal density</td><td>8000 kg/m³</td></tr><tr><td>metal specific heat capacity</td><td>400 J/(kg·K)</td></tr><tr><td colspan="2">Initial stable conditions</td></tr><tr><td>outlet pressure</td><td>0.1 MPa</td></tr><tr><td>heat flux</td><td>1.1 MW/m²</td></tr><tr><td>Inlet mass flow rate</td><td>3g/s</td></tr><tr><td>outlet fuel temperature</td><td>750℃</td></tr></table></body></html>

# Inlet flow rate perturbation

The inlet flow rate perturbation is from $3 \mathrm { g / s }$ to $3 . 3 \mathrm { g / s }$ and the outlet flow rate and inlet pressure responses of various tube lengths, fuel temperatures and pressures are shown in Figure 6 to Fig..It can be seen from that the longer the tube is, the slower the outlet flow rate reaches equilibrium state.The outlet flow rate takes almost 4 second to reach equilibrium state in 5 meters long tube, compared to the $1 0 ^ { - 3 } \mathrm { s }$ of combustion, it can be concluded that the dynamic characteristics of engine trust control primarily depends on the fuel supply system. The inlet pressures response is shown in Figure 6 (b),inlet pressure time response curve can be divided into two parts,it firstly rush to a high point then slowly reduce to a lower stable state. it can be explained by Eq.9 that inlet pressure increases as mass flow rate increases and inlet pressure drops as fuel velocity drops.When inlet mass flow rate step increases, the fuel temperature decreases slowly, and the fuel density drops slowly at the same time.Thus, the fuel velocity drops and leads to inlet pressure drops.

It can be seen from Figure 6 (b),as the tube length increase,the inlet pressure increases more,and the overshot of inlet pressure is more severe.

As shown in Figure 7 (a),it takes the outlet flow rate longer time to reach equilibrium state as the outlet fuel temperature rises.When the outlet fuel temperature is $3 0 0 ^ { \circ } \mathrm { C }$ , the tube is full of the low compressibility liquid. When the fuel heated to $5 0 0 ^ { \circ } \mathrm { C }$ ，part of the fuel in the tube turns to higher compressibility super critical fluid. As fuel reaches $7 0 0 ^ { \circ } \mathrm { C }$ ， thermal cracking produces high compressibility pyrolysis products,thus the outlet flow costs 2s to rebalance.It can be seen from Figure 7(b), with the same amplitude of mass flow rate step changes, the higher the fuel temperature is,the slower the fuel temperature rebalances and thus the larger the inlet pressure increases.

![](images/c1c76a0f0da06643a08d45e7632ac624bfe43fe0bbd8d415de44d9103471e5ee.jpg)  
Fig.6The outlet flow and inlet pressure response at different tube length when inlet flow step change

It can be seen from Figure 8(a) that the increasing of fuel pressure can increase the outlet flow response rate feebly， because the fuel compressibility is smaller at higher pressure.Figure 8 (b) also shows that the overshot of inlet pressure is more sever at lower pressure.

# Outlet throttle valve opening perturbation

As the outlet throttle valve opening decreases by step, the fuel in the tube rush out of outlet then the flow rate recovers to the initial state because the inlet flow rate keeps unchanged. In section 4.1,it is known that when inlet flow changed, the outlet flow response time is very long.It can be seen from Figure 9(a) that controlling the outlet valve opening can be a method to increase the response speed of the engine fuel supply system. Figure 9 (c) and Figure 9(d) shows the change of the outlet throttle valve opening has a few effects on the wall temperature and fuel temperature.

![](images/69a82d916bf92f63abe1d57ea9bb187e78b333a14c285069d87436019db7c06e.jpg)  
Fig.8The outlet flow and inlet pressure response at different pressure when inlet flow step change

![](images/61527e4372a9c4aa93e89cb2530264c088fab5fe355b9e77341506f3188ee89d.jpg)  
Fig.7The outlet flow and inlet pressure response at different outlet fuel temperature when inlet flow step change

# Conclusion

To investigate the transient dynamic characteristics of cooling channel during the process of fuel flow supply and the change of cooling channel outlet valve opening, this article focuses on the simulation of a one-dimensional model with high temperature hydrocarbon fuel at pyrolysis condition. Tube length，working pressure and heat load are chosen to investigate the effect on channel parameters dynamic characteristics.

An important result was that the time constant of outlet flow is 2 to 5 seconds,and time constant increased with increasing tube length and heat load, working pressure has few effects on it.As inlet fuel step changed, the inlet pressure appeared overshoot, thus caused transient impulse on pumping power. Increasing the tube length, heat load and decreasing the working pressure all lead to higher transient impulse.To increase the response speed of the engine fuel supply system, the step decrease of outlet throttle valve opening was a good way without large fluctuation of fuel and channel wall temperature.

![](images/3917d52d9d4dcbbff5b07ec06c65e99e1d119c79a764115ac69d21273d075b34.jpg)  
Fig.9Theoutletflow,temperaturesand inlet pressureresponseat diferent valvechange amplitudewhenoutletthrotte valve opening change by step.

# References

[1]E.T.Curran,“Scramjet engines: the first forty years", J Propulsion Power,17 (6)(2001),pp.1138-1148.   
[2]Hopkins R.P.,Raymond N.E.，White S.T.,DeLong S., “The Analysis of Conventional Prompt Global Strike Alternatives",2010 IEEE Systems and Information Engineering Design Symposium, Charlottesville,Virginia, USA,2010:135-140.   
[3]Richman M.S.,Kenyon J.A.， “High Speed and Hypersonic Science and Technology”, $4 1 ^ { \mathrm { s t } }$ AIAA/ASME/ ASEE Joint Propulsion Conference and Exhibit, Tucson, Arizona,AIAA 2005-4099,2005.   
[4] Smart M.K.,Hass N.E.,and Paull A.,“FlightData Analysis of the HyShot2 Scramjet Flight Experiment",AIAA Journal, Vol. 44,No.10,2006,pp.2366-2375.   
[5]J.T. Chang,W.Bao,D.R.Yu.,“Hypersonic inlet control with pulse periodic energy addition",Proc IMechE Part G JAerospace Eng,223 (2009), pp.85-94.   
[6]Jiang Qin,Wen Bao,Silong Zhang,and Weixing Zhou., "Comparison During a Scramjet Regenerative Cooling and Recooling Cycle"，Journal of Thermophysics and Heat Transfer,Vol.26,No.4(2012),pp.612-618.   
[7]Silong Zhang,Yu Feng,Yuguang Jiang,“Thermal behavior in the cracking reaction zone of scramjet cooling channelsat different channel aspect ratios",Acta Astronautica,Volume 127,October-November 2016,Pages   
41-56. [8] Oberkampf W.L., Trucano T.G.,“Verification and Validation in Computational Fluid Dynamics”,Progress in Aerospace Sciences,Vol.38,No.3,April 2002,pp.209-   
272. [9]T.A. Ward, J.S. Ervin, S. Zabarnick, L. Shafer,“Pressure effects on flowing mildly-cracked n-Decane",J.Propuls. Power,21 (2) (2005),pp.344-355 [10]Silong Zhang,Yu Feng,Yuguang Jiang,“Thermal behavior in the cracking reaction zone of scramjet cooling channels at different channel aspect ratios",Acta Astronautica,Volume 127,October-November 2016,Pages   
41-56. [11]T.A.Ward, J.S.Ervin,R.C. Striebich, S. Zabarnick,“Simulations of flowing mildly-cracked normal alkanes incorporating proportional product distributions",J. Propuls. Power,20 (3) (2004), pp.394-402 [12]Linne D.L.,Meyer M.L.,Braun D.C.,et al,“InvestigationofInstabilities andHeat TransferPhenomena in Supercritical Fuels at High Heat Flux and Temperatures",   
36th AIAA/ASME/SAE/ASEE Joint Propulsion Conference and Exhibit Las Vegas,Nevada,U.S.A.AIAA 2000-3128,2000.   
[13]Nicolas Gascoin,Philippe Gillard,Emmanuel Dufour, and Youssoufi Toureé."Validation of Transient Cooling Modeling for Hypersonic Application", Journal of Thermophysics and Heat Transfer, Vol. 21,No.1 (2007), pp. 86-94.   
[14]Dahm K.D.,Virk P.S.,Bounaceur R.,Battin-Leclerc F., Marquaire P.M.,FournetR.,Daniau E.,and Bouchez M., “Experimental and Modeling Investigation of the ThermalDecomposition of n-Dodecane",Journal of Analytical and Applied Pyrolysis,Vol.71, No.2, June 2004, pp. 865-881.   
[15] W Bao, X-L Li, J Qin,and W-X Zhou, “Modeling and simulation methodology of channel cooling using hydrocarbon fuel as coolant under supercritical pressures", Proceedings of the Institution of Mechanical Engineers, Part G: Journal of Aerospace Engineering.Vol 225,Issue 9,pp.969-984.   
[16]T.A. Ward, J.S. Ervin,R.C. Striebich, S. Zabarnick,“Simulations of flowing mildly-cracked normal alkanes incorporating proportional product distributions”,J. Propuls.Power,20 (3)(2004),pp.394-402.   
[17]J. Stewart, K. Brezinsky, I. Glassman,“Supercritical pyrolysis ofDecalin, Tetralin,and n-Decane at $7 0 0 { - } 8 0 0 ~ \mathrm { K }$ Product distribution and reaction mechanism",Combust. Sci. Technol., 136 (1998), pp.373-390.   
[18] D.Y. Peng, D.B. Robinsion,“A new two-constant equation of state Ind. Eng. Chem. Fundam",51 (1) (1976), pp. 59-64.   
[19] E.Bruce Poling,J.M.Prausnitz,O.J.Paul, “The Properties of Gases and Liquids",5,McGraw-Hill,New York (2001).   
[20] E.W.Lemmon,L.H.Marcia,M.O.Mclinden,“NIST 23: Reference Fluid Thermodynamic and Transport Properties",NIST Standard Reference Database Number 23, Version 9.1.NIST,2013.   
[21] W.Bao, S. Zhang,J.Qin,W. Zhou,K.Xie.“Numerical analysis of flowing cracked hydrocarbon fuel inside cooling channels in view of thermal management", Energy,67 (2014), pp.149-161   
[22] ANSYSFLUENTUser'sGuide,Release13.0,November 2010.   
[23] O.Redlich, J.N.S.Kwong On the thermodynamics of solutions.V.“An equation of state",Fugacities of gaseous solutions Chem. Rev.,44 (1) (1949), pp.233-244.   
[24] Z.Jia, H.Huang,W. Zhou, et al. Experimental and modeling investigation of n-Decane pyrolysis at supercritical pressures,Energy Fuels,28(9) (2014),pp.6019-6028.   
[25] W. Zhou, Z. Jia, J.Qin,et al. Experimental study on effect of pressure on heat sink of n-Decane, Chem.Eng. J., 243 (2014), pp. 127-136