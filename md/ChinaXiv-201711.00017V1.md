# Mathematical Modelling of the Transient Response of Pipeline

DawidTaler,KarolKaczmarski

Cracow UniversityofTechnology,FacultyofEnvironmentalEngineering,ul.Warszawska24,31-155Cracow,Poland, Cracow UniversityofTechnology,FacultyofMechanical Engineering,Al.Jana Pawla I37,31-864 Cracow,Poland,

Steam pipelines applied in power units operate at high pressures and temperatures. In addition,to stress from the pipeline pressure also arise high thermal stresses in transient states such as start-up,shutdown ora load change of the power unit.Time-varying stresses are often the cause of the occurrence offatigue cracks since the plastic deformations appear at the stressconcentration regions.To determine the transient temperature of the steam along the steam flow path and axisymmetric temperature distribution in the pipeline wall,anumerical model of pipeline heating was proposed.To determine the transient temperature of the steam and pipeline wallthe finite volume method (FVM) was used Writing the energy conservation equations for control areas around al the nodes gives a system of ordinary differential equations with respect to time.The system of ordinary diferential equations of the first order was solved bythe Runge-Kutta method of the fourth order to givethe time-temperature changes at the nodes lying in the area of the walland steam.The steam pressre distribution along pipeline was determined from the solution of the momentum conservation equation.Based on the calculated temperature distribution,thermal stresses were determined.The friction factor was calculated using the correlations of Churchill and Haaland, which were proposed for pipes with a rough inner surface.To assess the accuracyof the proposed model, numerical calculations were also performed for the thin-walled pipe,and the results were compared to the exact analytical solution. Comparison of the results shows that the accuracy of the proposed model of pipeline heating is very satisfactory. The paper presents examples of the determination of the transient temperature of the steam and the wall.

# Keywords: steam pipeline,heating,mathematical model, thermal stresses

# Introduction

The high-temperature steam pipes applied in steam boilers are used to transport superheated live steam from the boiler to the turbine.

During startups and shutdowns of the power units as well as during load changes high thermal stresses can occur in the pipeline wall and pipeline fittings.Particularly high stresses occur in T-pipes and Y-pipes. Also, thick-walled parts with complex shapes such as gate

# Nomenclature

valves and valve housings are exposed to large thermal loads.High and time variable thermal stresses maylead to premature damage to the pipeline in the form of cracks. Knowledge of the range of the stresses in critical components allows conducting a startup of the boiler in a way thatprovidesa safe and long life of the boiler and turbine. Issues relating to the direct and inverse calculation and monitoring of thermal stresses in cylindrical components are the subjects of current research [1-2]. In this paper, transient temperature and thermal stress distributions in a pipeline connecting the boiler and turbine will be analyzed.At first, the temperature of the fluid and pipeline wall temperature will be determined analytically using the superposition method. In the analytical solution, the physical properties of the fluid and metal are assumed to be independent of temperature. Also,a temperature difference across the thickness of the pipeline wall is neglected,i.e. the wall is modeled as an element with lumped heat capacity. Next, the finite volume method (FVM) will be used to calculate the transient temperature of the steam and pipeline wall. Thermal stresses will also be determined. Time and space temperature changes of the fluid and metal calculated using analytical and numerical methods will be compared. The pipeline heating with superheated steam will also be presented.

<html><body><table><tr><td>a</td><td>thermal diffusivity a=λ/(c p), m²/s</td><td>Tn</td><td>nominal (design) temperature,C or K</td></tr><tr><td>A</td><td>cross-section area, m²</td><td>t</td><td>time, s</td></tr><tr><td>cp</td><td>specific heat capacity at constant presure, J/(kg·K)</td><td>tcn</td><td>time after which the steam tempe reaches the nominal temperature, s</td></tr><tr><td>Cw</td><td>specific heat capacity of the heat tube material, J/(kg:K)</td><td>tpr</td><td>transit time of the fluid particle, s</td></tr><tr><td>din</td><td>inner diameter, m</td><td>x,y,z</td><td>Cartesian coordinates, m</td></tr><tr><td>In(x)</td><td>modified Bessel functions of order n,</td><td>W</td><td>fluid velocity, m/s</td></tr><tr><td>L</td><td>length of the pipeline, m</td><td>Greek symbols</td><td></td></tr><tr><td>m</td><td>mass, kg</td><td>α</td><td>heat transfer coefficient, W/(m²·K)</td></tr><tr><td>m</td><td>fluid mass flow rate, kg/s</td><td>Ar</td><td>radial step ,m</td></tr><tr><td>(n+1)</td><td>number of nodes in the radial direction,</td><td>At</td><td>time step size, s</td></tr><tr><td>n</td><td>number of nodes in finite difference grid,</td><td></td><td>thermal conductivity, W/(m·K)</td></tr><tr><td>NTU</td><td>number of transfer units,</td><td>8</td><td>relative roughness, m</td></tr><tr><td>Nu</td><td>Nusselt number,</td><td>从</td><td>dynamic viscosity, kg/(m:s)</td></tr><tr><td>p</td><td>absolute pressure, Pa</td><td>V</td><td>kinematic viscosity, m²/s</td></tr><tr><td>Pr</td><td>Prandtl number,</td><td>VT</td><td>rate of change of temperature, K/s</td></tr><tr><td>r</td><td>radius,m</td><td>p</td><td>density, kg/m³</td></tr><tr><td>Yin</td><td> inner radius,m</td><td>T</td><td>time constant, s</td></tr><tr><td>Yout</td><td>outer radius,m</td><td>Tw</td><td>time constant for wall, s</td></tr><tr><td>Re</td><td>Reynolds number,</td><td>Tc</td><td>time constant for steam, s</td></tr><tr><td>S</td><td>wall thickness, m</td><td>Subscripts</td><td></td></tr><tr><td>T</td><td>temperature,C or K fluid and tube wall temperature for linear</td><td>C</td><td>steam</td></tr><tr><td>T,Tw1</td><td>increase of the fluid temperature at the pipeline inlet,C or K</td><td>in</td><td>inner surface</td></tr><tr><td>T1,Twl</td><td>fluid and tube wall temperature for linear de- crease of the fluid temperature at the pipeline</td><td>out</td><td>outer surface</td></tr><tr><td></td><td>inlet,°C or K fluid and tube wall temperature for a step</td><td></td><td></td></tr><tr><td>T/,Tw</td><td>change in fluid temperature at the pipeline inlet,C or K</td><td>m</td><td>mean</td></tr><tr><td>Tm(t)</td><td>mean temperature of the wall, °C or K</td><td>W</td><td>wall surface</td></tr></table></body></html>

# Simplified Analytical Model

In a simplified mathematical model of heating or cooling of the pipeline, the following simplifying assump tions were made:

· the temperature of the fluid in the pipeline cross sections is constant and depends only on the time and axial coordinate,   
· the temperature drop across the wall thickness is negligible,   
·axial heat conduction in the pipeline wall has been omitted,   
· the outer surface of the pipeline is perfectly thermally insulated,

·physical properties of the fluid and the wall material do not depend on the temperature and location.

Equations for thesteam andthe pipeline wall are as follow:

$$
\tau _ { c } \frac { \partial T } { \partial t } + \frac { 1 } { N T U } \frac { \partial T } { \partial z } = - \left( T - T _ { w } \right)
$$

$$
\tau _ { w } \frac { \partial T _ { w } } { \partial t } = T - T _ { w }
$$

Boundary conditions:

$$
\begin{array} { c c } { { T \mid _ { _ { z = 0 } } = T _ { _ { 0 } } + \Delta T + \nu _ { _ { T } } t } } & { { 0 \leq t \leq t _ { _ { c n } } } } \\ { { T \mid _ { _ { z = 0 } } = T _ { _ { n } } } } & { { t \geq t _ { _ { c n } } } } \end{array}
$$

where:

$$
T _ { n } = T _ { 0 } + \Delta T + \nu _ { _ { T } } t _ { c n }
$$

Initial condition

$$
\begin{array} { c } { { T \mid _ { t = 0 } = T _ { 0 } } } \\ { { T _ { w } \mid _ { t = 0 } = T _ { 0 } } } \end{array}
$$

The superposition method was applied to solve Eqs. (1-4).Formulas for the transient temperature of the liquid and the wall for the abrupt and a linear increase in fluid temperature at the inlet of the pipeline are given in [3].

The solution of the boundary-initial value problem given by Eqs.(1-4) is:

The temperature of the steam

$$
T = T _ { _ { I } } ( t ) + T _ { _ { I I I } } ( t ) , \quad 0 \le t \le t _ { _ { c n } } , t _ { _ { c n } } \ge t _ { _ { p r } }
$$

$$
T = T _ { I } ( t ) + T _ { I I } ( t - t _ { c n } ) + T _ { I I I } ( t ) , t \leq t _ { c n }
$$

![](images/5dbe3dc70cd4aaa92ecca976618466d88eed2c62aac94677e8f48a053f4d6aff.jpg)  
Fig.1 Time changes of the fluid temperature at the pipeline inlet- boundary conditions for solution components I, II,and III in the superposition method where:

$$
T _ { I } = \nu _ { T } \tau _ { w } \{ e ^ { - ( \xi + \eta ) } \Big [ ( \eta - \xi ) U ( \xi , \eta ) + \xi I _ { 0 } ( 2 \sqrt { \xi \eta } )
$$

$$
\begin{array} { r l } &  \quad _ { I } - \nu _ { T } ^ { I } \nu _ { u \setminus v }  e ^ { -  \nu _ { T }  \nu _ { T }  - \xi ^ { \prime } \nu _ { T }  \xi ^ { \prime }  + \xi ^ { \prime } \nu _ { T }  - \xi ^ { \prime } \nu _ { T }  2  } \\ & { \qquad + \sqrt { \xi } \eta _ { T } I _ { 1 } ( 2 \sqrt { \xi } \eta ) )  \} , \quad t \geq t _ { p r } , \quad t _ { e n } \geq t _ { p r } } \\ & { \qquad I _ { u } ( t - t _ { e n } ) = - \nu _ { T } \tau _ { v }  e ^ { - ( \xi + \eta _ { 1 } ) } [ ( \eta _ { 1 } - \xi ) U ( \xi , \eta _ { 1 } )    } \\ & { \qquad   + \xi I _ { 0 } ( 2 \sqrt { \xi \eta _ { 1 } } ) + \sqrt { \xi \eta _ { 1 } } I _ { 1 } ( 2 \sqrt { \xi \eta _ { 1 } } ) ]  } \\ & { \qquad t \leq t _ { e n } , t _ { e n } \geq t _ { p r }  } \\ & { T _ { u \eta } = T _ { 0 } + \Delta T U ( \xi , \eta ) e ^ { - ( \xi + \eta _ { 0 } ) } } \\ & { \qquad \quad _ { t \leq t _ { p r } , t _ { e n } } 2 t _ { p r } , } \end{array}
$$

The temperature of the pipeline wall

$$
\begin{array} { r } { T _ { w } = T _ { w I } ( t ) + T _ { w I I I } ( t ) , 0 \leq t \leq t _ { c n } , t _ { c n } \geq t _ { p r } } \\ { T _ { w } = T _ { w I } ( t ) + T _ { w I I } ( t - t _ { c n } ) + T _ { w I I I } ( t ) , \phantom { 0 } } \end{array}
$$

where:

$$
\begin{array} { r l } & { T _ { w l } = T _ { i } - \nu _ { T } \tau _ { w } e ^ { - ( \xi + \eta ) } \Big [ U \left( \xi , \eta \right) + I _ { 0 } \left( 2 \sqrt { \xi \eta } \right) \Big ] , } \\ & { \qquad t \geq t _ { p r } , t _ { c n } \geq t _ { p r } } \\ & { T _ { w l f } \left( t - t _ { c n } \right) = T _ { i l } + \nu _ { T } \tau _ { w } e ^ { - ( \xi + \eta _ { l } ) } \left[ U \left( \xi , \eta _ { 1 } \right) \right. } \\ & { \qquad \left. + I _ { 0 } \left( 2 \sqrt { \xi \eta } \right) \right] \Big . } \\ & { \qquad t \geq t _ { p r } , t _ { c n } \geq t _ { p r } , } \\ & { T _ { w l f } = T _ { 0 } + \Delta T e ^ { - ( \xi + \eta ) } \Big [ U \left( \xi , \eta \right) + I _ { 0 } \left( 2 \sqrt { \xi \eta } \right) \Big ] \Big ] } \\ & { \qquad t \geq t _ { p r } , t _ { c n } = t _ { p r } , } \end{array}
$$

The following designations in formulas 1-14 were adopted [3]:

$$
\begin{array} { r l } & { v _ { T } = \frac { \left( T _ { n } - T _ { 0 } \right) } { t _ { \infty } } , \ U \left( \xi , \eta \right) = e ^ { i \xi + \eta } \rangle - \frac { \widetilde { \lambda } } { 2 \pi \vert \sqrt { 1 } } \left( \frac { \xi } { \eta } \right) ^ { 2 } I _ { n } \left( 2 \sqrt { \xi \eta } \right) } \\ & { \xi = \frac { z \sqrt { N T } } { L } , \ \eta = \frac { t - r _ { \eta \gamma } } { t _ { \infty } } , } \\ & { \eta _ { 1 } = \frac { t - t _ { \infty } - t _ { \infty } } { t _ { \eta } } , f _ { \eta \rho } = x N T \ U \tau _ { c } , } \\ & { N T U = \frac { \alpha A _ { n } } { \hat { m } _ { c \rho } } = \frac { \alpha A _ { n } } { \rho _ { c } w _ { c } d _ { c } c _ { \rho \sigma } } , } \\ & { \tau _ { c } = \frac { c _ { \rho } r _ { \tilde { m } } } { \alpha A _ { n } } = \frac { \rho _ { c } L _ { d } c _ { \rho \sigma } } { \alpha A _ { n } } } \end{array}
$$

The analytical solution given by Eqs. (5-14) will be used for comparison with the numerical solution proposed in this paper.

# NumericalModel

A scheme of the pipeline linking the boiler with a turbine in power unit with capacity of 12oMWis depicted in Fig. 2.

The governing equations for the steam are

mass conservation equations

$$
\frac { \partial \rho } { \partial t } = - \frac { 1 } { A } \frac { \partial \dot { m } } { \partial z }
$$

momentum conservation equations

$$
\begin{array} { c } { \displaystyle \frac { \partial \dot { m } } { \partial t } = - \frac { \partial } { \partial z } \Bigg ( \frac { \dot { m } ^ { 2 } } { \rho A } \Bigg ) - \mathbf { A } \Bigg ( \frac { \partial p } { \partial z } + \rho g \sin \varphi } \\ { \displaystyle - \frac { \xi } { d _ { i n } } \frac { \dot { m } \big | \dot { m } \big | } { 2 \rho A ^ { 2 } } \Bigg ) } \end{array}
$$

energy conservation equations

$$
\begin{array} { l } { \displaystyle \rho c _ { p } \Bigg ( \frac { \hat { \sigma } T } { \hat { \sigma } t } + \frac { \dot { m } } { \rho A } \frac { \hat { \sigma } T } { \hat { \sigma } z } \Bigg ) = \beta \Upsilon \Bigg ( \frac { \hat { \sigma } p } { \hat { \sigma } t } + \frac { \dot { m } } { \rho A } \frac { \hat { \sigma } p } { \hat { \sigma } z } \Bigg ) + } \\ { \displaystyle \frac { \xi } { d _ { i n } } \frac { \Big | \dot { m } ^ { 3 } \Big | } { 2 \rho ^ { 2 }  { \textbf { \ i } } ^ { 3 } } - \frac { \alpha \big ( T - T _ { w } \big ) \mathrm { U } _ { w } } { A } + \frac { 1 } { A } \frac { \hat { \sigma } } { \hat { \sigma } z } \Bigg ( \mathrm { A } \lambda \frac { \hat { \sigma } T } { \hat { \sigma } z } \Bigg ) } \end{array}
$$

![](images/56b1aad59adf10c6df2f891013a0468700d3fca19d9aa46a3e602e98621da705.jpg)  
Fig.2Pipeline connecting the boiler and turbine

Transient heat conduction equation for the pipeline wall is as follows

$$
\rho _ { w } c _ { p w } \frac { \partial T _ { w } } { \partial t } = \nabla \cdot \left[ \lambda _ { w } \left( T _ { w } \right) \nabla T _ { w } \right]
$$

Taking into account small changes in pressure along the length of the pipeline,a small steam density change can be assumed that the derivative $\partial \rho / \partial t$ is equals to zero.The assumption $\partial \rho / \partial t = 0$ in Eq.(15）implies that mass flow rate $\dot { m }$ is constant over the tube length, i.e.

$$
\dot { m } = c o n s t
$$

The velocity of the steam in each cross section of the pipeline can be calculated from the formula

$$
w = \frac { 4 \dot { m } } { \pi \rho d _ { i n } ^ { 2 } }
$$

Considering that $\partial \dot { m } / \partial t = 0$ ，the momentum conservation equation(17) reduces to

$$
\frac { d p } { d z } = - \rho w \frac { d w } { d z } - \rho g \sin \varphi - \frac { \xi } { d _ { i n } } \frac { \rho w \vert w \vert } { 2 }
$$

Using Eq.(21) the steam pressure can be determined

along the flow path.

Neglecting the thermal expansion of the steam $( \beta = 0 )$ L the heat generation due to friction and the axial thermal conduction in the steam, the energy conservation equation (17) for the steam is simplified to form

$$
\rho c _ { p } \Bigg ( \frac { \partial T } { \partial t } { + } \frac { \dot { m } } { \rho A } \frac { \partial T } { \partial z } \Bigg ) = { - } \frac { \alpha \big ( T - T _ { w } \big ) \mathrm { U } _ { i n } } { A }
$$

The heat conduction equation(18) in cylindrical coordinate system is

$$
\begin{array} { c } { { \displaystyle { \rho _ { w } c _ { p w } \frac { \partial T _ { w } } { \partial t } = \frac { 1 } { r } \frac { \partial \rho } { \partial r } \bigg [ r \lambda _ { w } \left( T _ { w } \right) \frac { \partial T _ { w } } { \partial r } \bigg ] } } } \\ { { + \frac { \partial } { \partial z } \bigg ( \lambda _ { w } \left( T _ { w } \right) \frac { \partial T _ { w } } { \partial z } \bigg ) } } \end{array}
$$

System of partial differential equations (22）-(23） is subject to the following initial and boundary conditions

$$
\left. T \right| _ { t = 0 } = T _ { o }
$$

$$
T _ { w } \mid _ { t = 0 } = T _ { w , o }
$$

$$
{ \cal T } | _ { z = 0 } = f ( t )
$$

$$
\lambda _ { w } \frac { \partial T } { \partial r } | _ { r = r _ { i n } } = \alpha \left( T - T _ { w } \right)
$$

$$
\lambda _ { w } \frac { \partial T } { \partial r } | _ { r = r _ { o u t } } = 0
$$

$$
\lambda _ { w } \frac { \partial T _ { w } } { \partial z } | _ { z = 0 } = 0
$$

$$
\lambda _ { w } \frac { \partial T _ { w } } { \partial z } \vert _ { z = 0 } = L
$$

In addition to the conditions (24)- (3O), the pressure and mass flow rate of the steam are known at the inlet of the pipeline.

The initial -boundary value problem (24)-(30) was solved using the finite volume method (FVM)[4-6].

First computational domain,i.e. the wall and the area occupied by the steam was divided into finite volumes. (Fig.3.)

![](images/96453c52c102882b92528f414a492dea304e843d74ca0f094fbcc9b87a3dc24f.jpg)  
Fig.3Division of the computational domain into finite volumes.

For each control volume lying both in the wall and the steam,energy balance equations were formed.For example,the energy balance equation for node i is set for

control volume located in the computational area of the wall (Fig.4.)

![](images/136fc0875d9024ba4ec08216ad374ba323c7442e901e454954822cb3f90444d3.jpg)  
Fig.4Wall temperature at the node i and adjacent nodesi-1, $\mathbf { i } { + } \mathbf { 1 }$ ,i-n-1, $\mathbf { i } { + } \mathbf { n } { + } \mathbf { 1 }$

The energy balance equation for the node i is

$$
\begin{array} { r l } & { \rho _ { w _ { i } } \left( T _ { w _ { i } } \right) c _ { p w _ { i } } \left( T _ { w _ { i } } \right) \pi \left( r _ { j + 1 } ^ { 2 } - r _ { j } ^ { 2 } \right) \Delta \tau \frac { d T _ { w _ { i } } } { d t } } \\ & { = 2 \pi r _ { j } \Delta z \frac { \lambda _ { w _ { i } } \left( T _ { w _ { i } } \right) + \lambda _ { w _ { i } } \left( T _ { w _ { i - 1 } } \right) } { 2 } \frac { T _ { w _ { i - 1 } } } { \Delta r } - T _ { w _ { i } } } \\ & { + 2 \pi r _ { j + 1 } \lambda \tau \frac { \lambda _ { w } \left( T _ { w _ { i } } \right) + \lambda _ { w _ { i } } \left( T _ { w _ { i - 1 } } \right) } { 2 } \frac { T _ { w _ { i + 1 } } - T _ { w _ { i } } } { \Delta r } } \\ & { + \pi \left( r _ { j - 1 } ^ { 2 } - r _ { j } ^ { 2 } \right) \frac { \lambda _ { w } \left( T _ { w _ { i } } \right) + \lambda _ { w _ { i } } \left( T _ { w _ { i + 1 } } \right) } { 2 } \frac { T _ { w _ { i + 1 } } } { \Delta z } - T _ { w _ { i } } } \\ & { + \pi \left( r _ { j - 1 } ^ { 2 } - r _ { j } ^ { 2 } \right) \frac { \lambda _ { w } \left( T _ { w _ { i } } \right) + \lambda _ { w _ { i } } \left( T _ { w _ { i - 1 } } \right) } { 2 } \frac { T _ { w _ { i + 1 } - 1 } - T _ { w _ { i } } } { \Delta z } } \end{array}
$$

Transformation of Eq.(31) gives

$$
\begin{array} { r l } &  \frac { d T _ { v _ { \mathrm { e f f } } } } { d t } = \frac { a \left( T _ { v _ { \mathrm { e f f } } } \right) } { \lambda _ { \mathrm { v } } \left( T _ { v _ { \mathrm { e f f } } } \right) \left[ \frac { r _ { v _ { \mathrm { e f f } } } } { \Delta r } \frac { \lambda _ { \mathrm { e f f } } \left( T _ { v _ { \mathrm { e f f } } } \right) + \lambda _ { \mathrm { v } } \left( T _ { v _ { \mathrm { e f f } } } \right) } { r _ { v _ { \mathrm { e f f } } ^ { 2 } - 1 } ^ { 2 } } \left( T _ { v _ { \mathrm { e f f } } } - T _ { v _ { \mathrm { e f f } } } \right) \right. } \\ & { \phantom { \frac { d T _ { v _ { \mathrm { e f f } } } } { d t } } + \frac { r _ { v _ { \mathrm { f f } } + 1 } } { \Delta r } \frac { \lambda _ { \mathrm { v } } \left( T _ { v _ { \mathrm { e f f } } } \right) + \lambda _ { \mathrm { v } } \left( T _ { v _ { \mathrm { e f f } } } \right) } { r _ { v _ { \mathrm { e f f } } ^ { 2 } - 1 } ^ { 2 } - r _ { v _ { \mathrm { e f f } } ^ { 2 } } ^ { 2 } } \left( T _ { v _ { \mathrm { e f f } } } - T _ { v _ { \mathrm { e f f } } } \right) } \\ & { \phantom { \frac { d T _ { v _ { \mathrm { e f f } } } } { d t } } + \frac { \lambda _ { \mathrm { v } } \left( T _ { v _ { \mathrm { e f f } } } \right) + \lambda _ { v } \left( T _ { v _ { \mathrm { e f f } } + 1 } \right) } { 2 \left( \Delta r \right) ^ { 2 } } \left( T _ { v _ { \mathrm { e f f } } - 1 } - T _ { v _ { \mathrm { e f f } } } \right) } \\ & { \phantom { \frac { d T _ { v _ { \mathrm { e f f } } } } { d t } } + \frac { \lambda _ { v } \left( T _ { v _ { \mathrm { e f f } } } \right) + \lambda _ { v } \left( T _ { v _ { \mathrm { e f f } } - 1 } \right) } { 2 \left( \Delta r \right) ^ { 2 } } \left( T _ { v _ { \mathrm { e f f } } - 1 } - T _ { v _ { \mathrm { e f f } } } \right) } \end{array}
$$

In a similar manner, the heat balance equation for the $i \cdot$ -th control volume located in the region occupied by steam can be set

$$
\begin{array} { l } { \displaystyle \frac { d T _ { w _ { i + 1 } } } { d t } = \frac { \dot { m } } { \rho \left( T _ { i } \right) \mathrm { A } } \frac { T _ { i + 1 } - T _ { i } } { \Delta z } - \frac { \alpha \left( T _ { i } \right) \mathrm { U } _ { w } } { A \rho \left( T _ { i } \right) c _ { p } \left( T _ { i } \right) } \Bigg [ \frac { T _ { i + 1 } - T _ { i } } { 2 } } \\ { \displaystyle - \frac { T _ { w _ { i ( n - 1 ) + 1 } } - T _ { w _ { ( i - 1 ) ( n + 1 ) + 1 } } } { 2 } \Bigg ] \qquad i = 1 , . . . , m } \end{array}
$$

Theheat transfer coefficient $\mathfrak { a }$ on inner surface of the pipeline was determined using Gnielinski's correlation [7]

$$
N u = { \frac { { \frac { \xi } { 8 } } { \big ( } \mathrm { R e } - 1 0 0 0 { \big ) } \mathrm { P r } } { 1 + 1 2 . 7 { \Bigg ( } { \frac { \xi } { 8 } } { \Bigg ) } ^ { 1 / 2 } { \Big ( } \mathrm { P r } ^ { 2 / 3 } - 1 { \Big ) } } } { \Bigg [ } 1 + { \Bigg ( } { \frac { d _ { i n } } { L } } { \Bigg ) } ^ { 2 / 3 } { \Bigg ] }
$$

where the friction factor $\xi$ is given by the Colebrook correlation

$$
\xi = \left[ 1 . 8 \log ( \mathrm { R e } ) - 1 . 1 5 \right] ^ { - 2 }
$$

The Reynolds number, Prandtl number,and Nusselt number are defined as follows

$$
\mathrm { R e } = { \frac { \rho w d _ { i n } } { \mu } } ; \quad \mathrm { P r } = { \frac { c _ { p } \mu } { \lambda } } ; \quad N u = { \frac { \alpha d _ { i n } } { \lambda } }
$$

After the formulation of all balance equations for the wall and steam,a system of ordinary differential equations for node temperatures is obtained. The number of equations for the nodes lying in the wall area is $( m { + } 1 ) ( n { + } 1 )$ while for the steam is $( m { + } 1 )$ ：

The system of ordinary differential equations was solved by the Runge-Kutta method of the fourth order.

To ensure the stability of determining the wall and steam temperature,the Fourier stability condition for the wall and Courant-Friedrichs-Levy condition for the steam should be satisfied. The smallest allowable time step $\Delta \mathrm { t } _ { \mathrm { m a x } }$ results from the Courant-Friedrichs-Levy condition

$$
\frac { w _ { i } \Delta t } { \Delta z } \le 1 , \qquad i = 1 , . . . , \mathrm { m } + 1
$$

Knowing the transient temperature distribution in the wall thermal stresses canbe determined.

Considering that the axial component of the temperature gradient ${ \partial T _ { w } } / { \partial z }$ is very little only radial temperature drop in the wall of the pipeline is taken into account.

Assuming that the ends of the pipeline are free to lengthen the thermal stress components are given by the following formulas [8]

$$
\sigma _ { r } = \frac { E \beta _ { T } } { 2 ( 1 - \nu ) } { \left( 1 \frac { r _ { i n } ^ { 2 } } { r ^ { 2 } } \right) } \left[ \overline { { \operatorname { T } } } ( t ) - \overline { { \operatorname { T } } } ( \mathbf { r } , t ) \right]
$$

$$
\sigma _ { \varphi } = \frac { E \beta _ { T } } { 2 ( 1 - \nu ) } \Bigg [ \Bigg ( 1 \frac { r _ { i n } ^ { 2 } } { r ^ { 2 } } \Bigg ) \overline { { { \Gamma } } } ( t ) + \Bigg ( 1 \frac { r _ { i n } ^ { 2 } } { r ^ { 2 } } \Bigg ) \overline { { { \Gamma } } } ( \mathrm { r } , t ) - 2 \ : \mathrm { T } ( \mathrm { r } , \mathrm { t } ) \Bigg ]
$$

$$
\sigma _ { z } = \frac { E \beta _ { T } } { 2 ( 1 - \nu ) } \big [ \overline { { \mathrm { T } } } ( t ) - 2 \mathrm { T } ( \mathbf { r } , \mathbf { t } ) \big ]
$$

where the mean wall temperature T(t)

$$
\begin{array} { c } { \overline { { \mathrm { T } } } ( t ) = \frac { 2 } { r _ { o u t } ^ { 2 } - r _ { i n } ^ { 2 } } { \displaystyle \int _ { r _ { i n } } ^ { r _ { o u t } } } { r T d r \approx \frac { 2 \Delta r } { r _ { o u t } ^ { 2 } - r _ { i n } ^ { 2 } } } } \\ { \cdot \Biggl [ r _ { 2 } \frac { T _ { 1 } + T _ { 2 } } { 2 } + r _ { n + 1 } \frac { T _ { n } + T _ { n + 1 } } { 2 } + \sum _ { i = 2 } ^ { n - 1 } \frac { r _ { i } + r _ { i + 1 } } { 2 } T _ { i } \Biggr ] } \end{array}
$$

$$
\begin{array} { c } { \overline { { \mathrm { T } } } \displaystyle ( \mathrm { r } , t ) = \overline { { \mathrm { T } } } \left( \mathrm { r } _ { i } , t \right) = \frac { 2 } { r ^ { 2 } - r _ { i n } ^ { 2 } } { \int _ { r _ { i n } } ^ { r _ { o u t } } { r T d r } } } \\ { \approx \displaystyle \frac { 2 \Delta r } { { r _ { i } ^ { 2 } - r _ { i n } ^ { 2 } } \left[ r _ { 2 } \frac { T _ { 1 } + T _ { 2 } } { 2 } + \sum _ { j = 2 } ^ { i } { \frac { r _ { j } + r _ { j + 1 } } { 2 } T _ { j } } \right] } } \end{array}
$$

where:

$$
\begin{array} { l } { r _ { 2 } = r _ { 1 } + \Delta r / 2 } \\ { r _ { i } = r _ { 2 } + ( i - 2 ) \Delta r ; \quad i = 3 , . . . , n + 1 } \\ { r _ { n + 2 } = r _ { n + 1 } + \Delta r / 2 } \end{array}
$$

Radial stresses $\sigma _ { \mathrm { r } }$ are equal to zero on the inner and outer pipeline surface. Circumferential ${ \sigma } _ { \phi }$ and axial stresses $\sigma _ { \mathrm { z } }$ are equal on those surfaces.

# Results

This paper presents the results of calculations of the pipeline connecting the boiler OP-38O with a steam turbine.

The steam pipeline is made of low alloy steel 13HMF （2号 $( C - 0 . 1 8 \%$ ， $M n \mathrm { - } 0 . 4 0 \%$ ， $S _ { 1 - 0 . 3 5 \% }$ ， $\mathrm { P _ { m a x } } { - } 0 . 0 4 0 \%$ ， $ { \mathrm { S } } _ { \mathrm { m a x } }$ $0 . 0 4 0 \%$ ， $\mathrm { C u } _ { \operatorname* { m a x } } { - 0 . 2 5 \% }$ ， $C r { - } 0 . 6 0 \%$ ， $\mathrm { N i } _ { \mathrm { m a x } } – 0 . 3 0 \%$ ，Mo$0 . 6 5 \%$ ， $\mathrm { A l } _ { \mathrm { m a x } } { - } 0 . 0 2 0 \% )$ . The main dimensions are outer diameter $d _ { o u t } = 0 . 3 2 4 \mathrm { ~ m ~ }$ ，the wall thickness $s = 0 . 0 4 \mathrm { ~ m ~ }$ and length $L = 4 5 ~ \mathrm { m }$ ：

First,the results obtained by the numerical method proposed in this paper will be compared with the analytical solution. The comparison will be carried out for constant physical properties of steam and steel because of constant physical properties assumed in analytical solution.The following constant physical properties have been used in calculations:

$\lambda _ { \mathrm { w } } = 4 4 . 6 8 ~ \mathrm { W / ( m { \cdot } K ) }$ ， $\rho _ { \mathrm { w } } = 7 7 6 6 ~ \mathrm { k g } / \mathrm { m } ^ { 3 }$ ， $\mathrm { c _ { w } } = 5 4 5 . 3$ $\mathbf { J } / ( \mathbf { k g } { \cdot } \mathbf { K } )$ ， $\mathrm { ~ a ~ } = \ : 0 . 0 1 3 3 \mathrm { ~ m } ^ { 2 } / \mathrm { s }$ ， $\mathrm { c _ { p c } = 2 6 7 2 . 3 ~ J / ( k g { \cdot } K ) }$ ， $\rho _ { \mathrm { c } } =$ $3 9 . 8 ~ \mathrm { k g / m } ^ { 3 }$ $\lambda _ { \mathrm { c } } = 0 . 0 8 3 7 \mathrm { W } / ( \mathrm { m \cdot K } )$ ， $\mathrm { v } = 0 . 7 7 5 5 { \cdot } 1 0 ^ { - 6 } \mathrm { m } ^ { 2 } / \mathrm { s } .$

The initial temperature of the fluid and the pipeline wall was equal to $\mathrm { T } _ { 0 } = 2 0 ^ { \circ } \mathrm { C }$ . Initial temperature jump was $\Delta T = 1 0 0 K$ 、The steam temperature increased at a constant rate $\mathrm { v _ { T } } = 1 0 ~ \mathrm { K / m i n } = 1 / 6 ~ \mathrm { K / s }$ in the range from 0 to $\mathrm { t _ { c n } } = 2 5 1 9 . 9 \ \mathrm { s }$ ，Steam velocity in the pipeline is constant: $\mathrm { w _ { c } } = 5 6 . 5 7 \mathrm { m / s }$ 1 $\mathrm { { R e } } = 1 . 7 7 9 8 9 4 \times 1 0 ^ { 7 } ,$ .Heattransfer coefficient was calculated from the Dittus-Boelter formula:

$$
N u = 0 . 0 2 3 \mathrm { R e } ^ { 0 . 8 } \mathrm { P r } ^ { 0 . 4 3 }
$$

Given that the Reynolds number is $\mathsf { R e } = 1 . 7 7 9 8 9 4 \times 1 0 ^ { 7 }$ and the Prandtl number $\mathrm { P r } = 0 . 9 8 5$ ，the heat transfer coefficient calculated using Eq.43 is:

$\alpha = 4 9 5 9 . 2 \ \mathrm { W / ( m ^ { 2 } { \cdot } K ) }$ .The number of transfer units is equal to $N T U = 0 . 6$ and the time constants for the fluid and pipeline wall are: $\tau _ { c } = 1 . 3 1 \mathrm { ~ s ~ }$ ， $\tau _ { w } = 3 9 . 7 6 \mathrm { ~ s ~ }$ ，respectively.

Comparing the temperature of the fluid and the pipeline wall calculated using the analytical formulas and the proposed numerical method is depicted in Fig.5.From the analysis of the results shown in Fig. 5 it can be seen that in the initial stage of pipeline heating,the mean wall temperatures calculated from the analytical formula and by using the finite volume method differ significantly. In a further heating phase the pipeline,average temperature of the pipeline wall calculated from the analytical formula is similar to the internal surface temperature calculated using the numerical method developed.

![](images/eb5f397931c1d6b1a0108f34a03b31a638d198a4bccf2939c45f606fe503a5d7.jpg)  
Fig.5Comparing the temperature of the fluid and the pipeline wall calculated using the analytical formulas and the proposed numerical method;a) the time interval from $\mathbf { t } = 0$ to $\mathrm { t } = 3 0 0 0 \mathrm { s }$ ,b) the time interval from $\mathbf { t } = 0$ to $\mathrm { { t } } = 5 0 0 \mathrm { { s } }$

Differences between the temperatures of fluid calcu lated using analytical and numerical methods are slightly different.

The numerical method must be used to calculate the thermal stresses in the wall of the pipeline.

Test calculations of the pipeline heating were performed taking into account the temperature-dependent physical properties of the fluid and the pipeline material.

Thermo-physical properties of steel are a function of temperature.

$$
\begin{array} { l } { \lambda = 4 8 . 4 9 5 + 0 . 0 0 1 2 T - 6 . 4 6 \times 1 0 ^ { - 5 } T ^ { 2 } } \\ { + 4 . 1 7 5 \times 1 0 ^ { - 8 } T ^ { 3 } } \end{array}
$$

$$
\begin{array} { c } { { a = 1 . 3 4 1 \times 1 0 ^ { - 5 } - 3 . 4 5 2 \times 1 0 ^ { - 9 } T } } \\ { { - 3 . 1 9 3 \times 1 0 ^ { - 1 1 } T ^ { 2 } + 2 . 8 5 3 \times 1 0 ^ { - 1 4 } T ^ { 3 } } } \end{array}
$$

where the thermal conductivity $\lambda$ isin $\mathrm { W / ( m \cdot K ) }$ ，the thermal diffusivity $a$ in $\mathrm { m } ^ { 2 } / \mathrm { s }$ ,and temperature $T$ in $^ { \circ } \mathrm { C }$

Calculating the transient temperature of the fluid and pipeline wall was carried out for a different number of finite volumes across the thickness of pipe wall.

Inspection of the results shown in Fig.6 illustrates that even at four finite volumes,i.e. for the five nodes evenly distributed over the wall thickness satisfactory accuracy of the calculations is obtained.

Almost identical results are obtained for the division of the pipe wall into nine（lO nodes） or nineteen finite volumes (2O nodes) as for the division into four finite volumes (5 nodes) Fig.6.

The temperature of the wall in the radial direction is computed in five nodes evenly spaced $( n { = } 4 )$ . The number of nodes in the axial direction is equal to $m + 1 = 2 1$

The pressure is $p = 1 3 . 9 \ \mathrm { M P a }$ . The mass flow rate of the steam is equal to $\dot { m } = 1 0 5 . 5 5 ~ \mathrm { { k g / s } }$ ，The initial temperature of the pipeline and steam is $T w _ { 0 } = 2 0 ^ { \circ } \mathrm { C }$ At time $\mathbf { t } > 0$ , the temperature of the steam pipeline inlet increases abruptly to a constant temperature at $\scriptstyle { T _ { 0 } = 5 4 0 ^ { \circ } C }$

Selected modelling results are shown in Figures 7-11 The steam temperature as a function of time at nodes No. 2 $( z = 2 . 2 5 \ \mathrm { m } )$ ，No.10 $( z = 2 0 . 2 5 ~ \mathrm { m } )$ ，and No. 20 $( z =$ $4 2 . 7 5 \mathrm { m } )$ are displayed in Fig.7.

![](images/48b555a0a89353b11f5f0393f1a8e136615138acce38b727c2a1c1f292cb5cfb.jpg)  
Fig.6The temperature of the inner and outer surface of the pipeline at its inlet $( \mathbf { z } = 0 ) ,$ asafunctionof time $t$ for various numbers of control volumes $n$ across the thickness of the pipeline wall.

The analysis of the results shown in Fig.7 shows that after about 6Oo s steam temperature reaches a steady state.

Fig.8 illustrates steam temperature changes over the length of the pipeline at time points 10 s,60 s,240 s,and $6 0 0 \mathrm { ~ s ~ }$ ：

The pipeline wall temperature in two different crosssections as a function of time depicts Fig.9. The wall temperature is shown in five uniformly spaced nodes. Thenodes11 and 1o1 are located on the inner surface while the nodes 15 and 105 lie of the outer pipeline surface.

![](images/d17282f46993a4c3c84877677e425922bf55d2943035919bcf4036e57467f9e9.jpg)  
Fig.7Steam temperature as a function of time at nodes No.2 $( z = 2 . 2 5 \ \mathrm { m } )$ ，No.10 $( z = 2 0 . 2 5 ~ \mathrm { m } )$ ，andNo.20（ $\ _ { Z } =$ $4 2 . 7 5 \mathrm { m } )$ （

![](images/5baca207861285aa4b4ec8f27d0d4275f2ea4c188c34c179e50d25e303e52dbb.jpg)  
Fig.8Steam temperature changes over the length of the pipeline at time points $1 0 \mathrm { ~ s ~ }$ ,60 s, $2 4 0 ~ \mathrm { s } .$ ,and 600s.

At the beginning of the heating process, the temperature differences over the thickness of the wall are large but rapidly decrease in time (Fig.9.).

Circumferential stresses on the inner and outer surface of the pipeline as a function of time presents in Fig.10.

The analysis of the results presented in Fig.1O shows that the inner surface is exposed to high compressive stresses while on the outer surface occur substantially lower tensile stresses.

High thermal stresses in the pipeline are caused by a high jump of $5 2 0 \mathrm { K }$ in steam temperature at time $\scriptstyle { t = 0 }$

The distribution of the circumferential thermal stress over the wall thickness is shown in Fig.11.

![](images/d9384e8fd938e31c4a2c2f6b02fe79277987cd6e376d092ec17a51e8103e4430.jpg)  
Fig.9Wall temperature in two cross-sections as a function of time a) $z = 2 . 2 5 \ \mathrm { m } , \mathrm { b }$ ） $z = 4 2 . 7 5 \mathrm { m }$

![](images/2fb9e4a3d467fa9cce689e5167684c6e75cef31cc51736d6aae6dd6e3ebf11b8.jpg)  
Fig.10Circumferential thermal stress at the inner (nodes 11 and 96) and outer (nodes 15 and 1oo) surface of the pipeline as a function of time; (a) $z = 2 . 2 5 \ : \mathrm { m } .$ (b) $z = 4 2 . 7 5 \mathrm { m }$

![](images/f8041ca0faf18f0d70361e678ee2acd1f1680937ea7e683fb88cfec4417aeaa6.jpg)  
Fig.11 Circumferential thermal stress as a function of radial coordinate and time (a) $z = 2 . 2 5 \ : \mathrm { m }$ (b) $z = 4 2 . 7 5 \mathrm { m }$

The stresses are compressive near the inner surface. In the vicinity of the outer surface,the stresses are tensile.

The largest absolute value of stress occurs at the beginning of heating and tend to zero over time.

# Summary

The mathematical model of the steam pipeline heating developed in the paper allows determining the temperature of the steam and the pipeline wall as a function of position and time.A comparison of the transient steam and pipeline wall temperature obtained from the analytical formulas with the results obtained using the proposed numerical model was conducted. This comparison indicates that the analytical formulascan onlybe used to calculate the temperature of the steam. It is possible to determine transient thermal stresses caused by the temperature difference across the wall thickness,using the model developed in the paper.Examples of calculations of the steam temperature,wall temperature and circumferential thermal stresses on the innerand outersurface of the pipeline have been presented.The calculation tests performed in the paper shows that the developed mathematical model can be used to simulate the actual pipeline heating or cooling in a power plant.

# References

[1]Taler J.,Zima W, Jaremkiewicz M.: Simple method for monitoring transient thermal stresses in pipelines,Journal of Thermal Stresses,39 (2016) no.4,pp.386-397   
[2]Dzierwa P., Taler D., Taler J.: Optimum heating of cylin drical pressure vessels,Forsch Ingenieurwes,80 (2016) DOI10.1007/s10010-016-0196-7   
[3] Serov E.P, Korolkov B.P.Dynamics of steam generators, Energoizdat,Moscow 1981   
[4] Taler J.,Duda P.: Solving Direct and Inverse Heat Conduction Problems,Springer,Berlin-Heidelberg 2006 [5]Taler D.: Dynamics of tube heat exchengers, Dissertation and monographs193,Publishing House of AGH, Cracow   
2009 [6] Taler D., Cisek P.,Modeling of cooling of ceramic heat accumulator. Archives of Thermodynamics,34(2013) no.   
4, pp.161-173 [7] GnielinskiV.:NewEquation forHeat andMass Transfer in Turbulent Pipe and Channel Flow. Int. Chem. Engng.   
16 (1976),359-368 [8] Hetnarski R.B.,Noda N., Tanigawa Y.: Thermal Stresses, Second edition Solution Manual, Taylor & Francis Inc. London,2002