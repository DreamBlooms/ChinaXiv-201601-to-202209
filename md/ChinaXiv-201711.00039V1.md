# Optimum Heating of Thick-Walled Pressure Components Assuming a Quasi-steady State of Temperature Distribution

Piotr Dzierwa1,Marcin Trojan1, Dawid Taler², Katarzyna Kaminska³,Jan Talerl

1. Institute of Thermal Power Engineering, Cracow University of Technology, Cracow, Poland,   
2.Institute ofThermal Engineering and Air Protection,Facultyof Environmental Engineering, Cracow,Poland   
3. Department of Hydraulic Engineering and Geotechnics,Agricultural University of Cracow

As aresult of the development of wind farms,the gas-steam blocks, which shall quickly ensure energy supply in case the wind velocity is too low,are introduced to the energy system.To shorten the start-up time of the gas - steam and conventional blocks,the structure of the basic components of the blocks are changed,e.g.by reducing the diameterof the boiler,the thickness ofits walis also reduced.The attempts were also made to revise the currently binding TRD 301 regulations,replacing themby the EN12952-3 European Standard,to reduce the allowable heating and cooling rates of thick walled boiler components.The basic assumption,on which the boiler regulations allowing to calculate the allwable temperature change rates of presure components were based,was the quasi-steady state of the temperature field in the simple shaped component,such as a slab,cylindrical or spherical wall.

# Keywords: pressure component, thermal stress, quasi-steady state, optimum heating

# Introduction

The quasi - steady state occurs in structural components of boilers and turbines during a long heating or cooling process running at a constant rate of change of temperature.In this paper,a more detailed analysis of the quasi - steady state was conducted for non - weakened walls and for walls weakened by openings. The use of formulas for circumferential stress at the edges of the openings to determine the allowable heating and cooling rates for the assumed pressure was also presented.Those formulas can be used in real life,as the analysis of the temperature and stress fields in the quasi - steady state can be quickly conducted with the use of the Finite Elements Method (FEM)，even for components ofa complex structure.

following factors:

·constant temperature difference between the selected points of the component (Fig. 1) ·constant,time independent, thermal stress (Fig.2).

The results presented in Figs.1 and 2 were obtained for the following data: $r _ { i n } = 0 . 8 5 ~ \mathrm { m }$ $r _ { o } = 0 . 9 4 ~ \mathrm { m }$ ， $c = 5 1 1$ $\mathbf { J } / ( \mathrm { k g } { \cdot } \mathrm { K } )$ ， $\rho = 7 7 7 5 \mathrm { k g } / \mathrm { m } ^ { 3 }$ ， $k = 4 7 . 3 \ \mathrm { W } / ( \mathrm { m } { \cdot } \mathrm { K } )$ $E = 2 0 1 1 0 5$ $\mathbf { M P a }$ $\beta = 1 . 2 1 \times 1 0 ^ { - 5 } ~ { 1 / K }$ $\nu = 0 . 2 8 8$

Let's consider the simplifying assumption that the thermo-physical properties of the wall material: $k , c , \rho , E$ and $\nu$ are constant and determined for the average temperature over time and the wall thickness.The transient heat transfer equation in the quasi - steady state can be then simplified to form [1,2]

The quasi - steady state can be characterized by the

$$
\nabla ^ { 2 } T = { \frac { \nu _ { T } } { \kappa } }
$$

<html><body><table><tr><td colspan="2">Nomenclature</td><td colspan="2"></td></tr><tr><td>C</td><td>specific heat of the metal, J/(kg·K)</td><td>t</td><td>time, s</td></tr><tr><td>din</td><td>inner diameter of the drum, m</td><td>T</td><td>temperature,CorK</td></tr></table></body></html>

<html><body><table><tr><td>dwo</td><td>inner diameter of the downcomer, m</td><td colspan="2">Greek Symbols</td></tr><tr><td>E</td><td>modulus of elasticity, MPa</td><td>am</td><td>stress concentration factor for circumferential stress caused by pressure</td></tr><tr><td>h</td><td>heat transfer coefficient, W/(m²-·K)</td><td>aT</td><td>stresocetrtrferel</td></tr><tr><td>k</td><td>thermal conductivity, W/(m·K)</td><td>B</td><td>linear thermal expansion coefficient, 1/K</td></tr><tr><td>p</td><td>absolute pressure in the drum, MPa</td><td>K</td><td>thermal diffusivity, m²/s</td></tr><tr><td>Po</td><td>atmospheric pressure, MPa</td><td>V</td><td>Poisson's ratio</td></tr><tr><td>Pn</td><td>Mpae presure in the drumpn=P-Po</td><td>p</td><td>density, kg/m³</td></tr><tr><td>Pnd</td><td>design gauge pressure in the drum, MPa</td><td></td><td>normal stress, MPa</td></tr><tr><td>Yin</td><td>inner radius of the drum, m</td><td>?</td><td>shape factor</td></tr><tr><td>r</td><td>outer radius of the drum, m</td><td>@</td><td>ratio of outer to inner diameter</td></tr><tr><td>r</td><td>position vector</td><td>Subscripts</td><td></td></tr><tr><td>S</td><td>drum wall thickness, m</td><td>a</td><td>allowable</td></tr><tr><td>S</td><td>downcomer wall thickness,m</td><td>f</td><td>fluid</td></tr><tr><td>S</td><td>circumferential thermal stress at the downcomer edge, MPa</td><td>0</td><td>initial</td></tr></table></body></html>

![](images/6ef61227ed0259e40f7974f4e1d9cec92541197be7e4a602939fd7e5e2e3d66f.jpg)  
Fig.1The temperature difference between the internal and the external surface of the cylinder during heating at a constant rate $\nu _ { T } = 3 ~ \mathrm { K / m i n }$

![](images/26ad9723c5fa0a24cf950b23a9ce839a5d8c098d36d1eea449616914c41688b8.jpg)  
Fig.2Circumferential stress on the inner and outer surface of the boiler drum during heating at a constant rate: $\nu _ { T } =$ $3 \mathrm { { K / m i n } }$ ：

where $\nu _ { T } = \frac { \hat { o } T } { \hat { o } t } = c o n s t$ is the rate of wall temperature change. The symbol $\nabla ^ { 2 }$ denotes the Laplace operator. The thickness of the wall is constant, and the external surface $\boldsymbol { r } = \boldsymbol { r } _ { o }$ of the pressure component is thermally insulated

$$
\left. \frac { d T } { d r } \right| _ { r = r _ { o } } = 0
$$

The temperature on the internal surface $r = r _ { i n }$ rises linearly in time at a rate of $\nu _ { T }$

$$
T \big | _ { r = r _ { i n } } = T _ { i n } = \nu _ { T } t
$$

Expressing the Laplace operator in a cylindrical or

spherical coordinate system leads to the specific form of the Eq. (1)

$$
\frac { 1 } { r ^ { m } } \frac { d } { d r } \bigg ( r ^ { m } \frac { d T } { d r } \bigg ) = \frac { \nu _ { T } } { \kappa }
$$

where $m = 1$ for the cylindrical component and $m = 2$ for the spherical component. After double integration of the above equation and after determining the constants from the boundary conditions(2)-(3) for the cylindrical wall, the following expression is obtained

$$
T = T _ { i n } + \frac { \nu _ { T } } { 4 \kappa } \Bigg ( r ^ { 2 } - r _ { i n } ^ { 2 } - 2 r _ { o } ^ { 2 } \ln \frac { r } { r _ { i n } } \Bigg )
$$

The average temperature over the wall thickness is

calculatedfromtheformula

$$
T _ { m } = \frac { m + 1 } { { r _ { o } ^ { m + 1 } - r _ { i n } ^ { m + 1 } } } \int _ { r _ { i n } } ^ { r _ { o } } { r ^ { m } T d r }
$$

Substituting Eq. (5) into Eq.(6) with $m = 1$ and integrating gives the average temperature $T _ { m }$ on the thickness of the cylindrical wall

$$
T _ { m } = \nu _ { T } t + \frac { \nu _ { T } s ^ { 2 } } { \kappa } \frac { \left( u ^ { 2 } - 1 \right) \left( 3 u ^ { 2 } - 1 \right) - 4 u ^ { 4 } \ln u } { 8 \left( u ^ { 2 } - 1 \right) \left( u - 1 \right) ^ { 2 } }
$$

where: $u = r _ { o } / r _ { i n }$ - the ratio of the outer radius to the inner radius, $s = r _ { o } - r _ { i n } -$ wall thickness.

The circumferential thermal stress $\sigma _ { w w }$ on the inner surfaceiscalculatedasfollows

$$
\sigma _ { w w } = \frac { E \beta } { 1 - \nu } \frac { \nu _ { T } s ^ { 2 } } { \kappa } \phi _ { w w }
$$

The circumferential thermal stress on the outer surface iscalculated fromthe similarformula

$$
\sigma _ { w z } = \frac { E \beta } { 1 - \nu } \frac { \nu _ { T } s ^ { 2 } } { \kappa } \phi _ { w z }
$$

where the so-called shape factors for the internal sur face $\phi _ { w w }$ and the external surface $\phi _ { w z }$ are given by the formulas

$$
\phi _ { w w } = { \frac { 1 } { 8 } } { \frac { \big ( u ^ { 2 } - 1 \big ) \big ( 3 u ^ { 2 } - 1 \big ) - 4 u ^ { 4 } \ln u } { \big ( u ^ { 2 } - 1 \big ) \big ( u - 1 \big ) ^ { 2 } } }
$$

$$
\phi _ { w z } = \frac { 1 } { 8 } \frac { \left( u ^ { 4 } - 1 \right) - 4 u ^ { 2 } \ln u } { \left( u ^ { 2 } - 1 \right) \left( u - 1 \right) ^ { 2 } }
$$

Similarly, the average temperature over the thickness of the sphere can be derived from Eq. (6). The shape factors for a sphere: $\phi _ { k w }$ for the inner surface and $\phi _ { k z }$ for the external surface,are given by

$$
\begin{array} { l } { { \phi _ { k w } = \displaystyle \frac { 1 } { 1 5 } \frac { 9 u ^ { 5 } - 5 u ^ { 6 } - 5 u ^ { 3 } + 1 } { \left( u ^ { 3 } - 1 \right) \left( u - 1 \right) ^ { 2 } } \ ~ } } \\ { { \phi _ { k z } = \displaystyle \frac { 1 } { 1 0 } \frac { \left( u ^ { 5 } - 1 \right) - 5 u ^ { 2 } \left( u - 1 \right) } { \left( u ^ { 3 } - 1 \right) \left( u - 1 \right) ^ { 2 } } \ ~ } } \end{array}
$$

The shape factors at the inner and outer surface of cylindrical and spherical walls are presented in Fig. 3.

The absolute values of the shape factors for the spherical wall $\phi _ { k w }$ and $\phi _ { k z }$ are smaller than the appropriate values of the shape factors for the cylindrical wall $\phi _ { w w }$ or $\phi _ { w z }$ (Fig. 3).

![](images/d8cd523ca40a9d025da24f07879fe2bfe16e87b7658abb8deccc6bdccbbb2a2e.jpg)  
Fig.3Shape factors for the inner and outer surface of cylindrical and spherical walls.

For the same rate of temperature changes, the thermal stresses in the spherical walls will be greater than the thermal stresses in the cylindrical walls.

# Optimum Heating of Components Without Openings

Heating or cooling of the components is conducted in away,whichwillassure thatthecircumferentialthermal stress on the inner surface equals the allowable stress.

$$
\sigma _ { w w } = \sigma _ { a }
$$

Substituting Eq.(8) into Eq. (14) gives

$$
\frac { E \beta } { 1 - \nu } \frac { \nu _ { T } s ^ { 2 } } { \kappa } \phi _ { w w } = \sigma _ { a }
$$

After transformation of Eq.(15), the expressions for the heating or cooling rate of the thick walled, cylindrical or spherical boiler components are obtained

cylindrical wall

$$
\nu _ { T } = \frac { \sigma _ { a } \kappa } { s ^ { 2 } \phi _ { w w } \displaystyle \frac { E \beta } { 1 - \nu } }
$$

spherical wall

$$
\nu _ { T } = \frac { \sigma _ { a } \kappa } { s ^ { 2 } \phi _ { k w } \displaystyle \frac { E \beta } { 1 - \nu } }
$$

The temperature change rate is positive during the heating process and negative during the cooling process. The wall temperature depends on the fluid temperature, but the temperature difference between the selected points in the components is constant and independent of time and the value of the fluid temperature.

# Quasi- Steady Distributions of the Temperature and Stresses in Pressure Components with Openings

The quasi - steady state temperature distribution in components of complex shape can be determined using Eq.（1）with the appropriate boundary conditions.Equation(l） describes a steady state temperature distribution in the body $T ( r , t )$ with uniformly distributed heat sinks with the specific power equal to: $\dot { q } _ { \nu } = \nu _ { \scriptscriptstyle T } / \kappa$ ：

In the following,an application of the quasi - steady state approach for determining allowable heating rates in components with complex shape will be discussed. Since stresses at points ${ \bf P } _ { 1 }$ and ${ \bf P } _ { 2 }$ (Fig. 4) limit the heating rate ofthe boilerdrum orother thick-walled vessels weakened by nozzles [3-6], thermal and pressure stresses are calculated for these points.

![](images/5a67d47e31ba02afff1eb31402d823810c1de5afa69595d66bf922ca4853c27a.jpg)  
Fig.4 Section of the boiler drum- downcomer junction and mesh of finite elements used for thermo-mechanical analysis of the drum-downcomer junction

The following geometrical dimensions of the boiler drum: inner diameter of the drum $D = 1 . 7 \mathrm { m }$ ，inner diameter of the downcomer $d = 0 . 0 9 \mathrm { m }$ ，thickness of the drum wall $H = 0 . 0 9 ~ \mathrm { m }$ ，thickness of the downcomer wall $h = 0 . 0 0 6 \mathrm { m }$ and physical properties of the boiler material $k = 4 2 \ \mathrm { W / ( m { \cdot } K ) }$ ， $c = 5 3 8 . 5 \mathrm { J } / ( \mathrm { k g } { \cdot } \mathrm { K } )$ $\rho = 7 8 0 0 ~ \mathrm { k g / m } ^ { 3 }$ $E =$ $1 . 9 6 { \times } 1 0 ^ { 1 1 } \mathrm { N } / \mathrm { m } ^ { 2 }$ $\beta = 1 . 3 2 { \times } 1 0 ^ { - 5 } ~ 1 / \mathrm { K }$ and $\nu = 0 . 3$ were assumed for the calculations.At first, time changes of the circumferential stress in time at point ${ \bf P } _ { 1 }$ for different heat transfer coeffcients were computed (Fig. 5).An analysis of the results shows that the quasi- steady state at low values of the heat transfer coefficient $h = 5 0 0 \mathrm { W } / ( \mathrm { m } ^ { 2 } { \cdot } \mathrm { K } )$ is set only after a long heating time at a constant rate.After 4000 seconds of heating the stresses did not reach the constant values,characteristic for the quasi- steady state Equivalent stress distributions in the boiler drum - downcomer junction determined using ANSYS for different pressures and heating rates are depicted in Figures 6,7,and 8.The largest stress due to the pressure is at the point ${ \bf P } _ { 1 }$ which is located at the hole edge (Fig. 6).

The equivalent stress at the point ${ \bf P } _ { 1 }$ is about five times larger than the stress at the point ${ \bf P } _ { 2 }$ when the drum is loaded only by the inner pressure.If the pressure inside the drum is equal to zero,then the equivalent thermal stress at the point ${ \bf P } _ { 2 }$ is higher in comparison with the stress at the point $\mathrm { P _ { 1 } ( F i g s \ 7 a }$ and 7b).When pressure is increased to design pressure $p \ = \ 1 0 . 8 7$ MPa then the stresses due to pressure for $\nu _ { T } = 1 ~ \mathrm { K / m i n }$ at the point ${ \bf P } _ { 1 }$ exceed thermal stresses and the largest equivalent stress occurs at the point ${ \bf P } _ { 1 }$ (Fig.8a). After increasing the heating rate to $\nu _ { T } = 1 2 ~ \mathrm { K / m i n }$ negative thermal stresses exceed positive stresses due to pressure and the largest equivalent stress is at point ${ \bf P } _ { 2 }$ (Fig. 8b).

![](images/f13c85f37223c22f986b82270756bc0a2f015dfa204f858a7f0fb345e4e5d57a.jpg)  
Fig.5Time variations of the circumferential stress $\sigma _ { \varphi }$ in time at point ${ \bf P } _ { 1 }$ fordifferent heat transfer coefficients $h$

![](images/79c80e2328950586d3a708b20f41b3984dcfd322ef4470cf442e7dc50b7af06d.jpg)  
Fig.6Equivalent stress distribution caused by inner pressure

The stress concentration coefficients $\alpha _ { T }$ at the point ${ \bf P } _ { 1 }$ and ${ \bf P } _ { 2 }$ (Fig.4), for the quasi- steady state as a function of the heat transfer coefficient $h$ arepresented in Fig.9. Thermal stresses determined from Eqs (8) and (9) refer to simple shapes,such as hollow cylinders and spheres. In real life,components used in power units often have openings,which can be viewed as material discontinuity causing stress concentration,what shall be taken into consideration when determining the allowable heating or cooling rate.Most often the assumed value of the thermal stress concentration coefficient at the edge of the opening is: $\alpha _ { T } = 2$ . Then, the influence of the heat transfer coefficient $h$ on the thermal stress concentration coeficient $\alpha _ { T }$ at the edge of the opening is not considered.

![](images/a6e267a4b7f8265ac61c20c6055c84f89be0165188108828449e8aa80ee566c2.jpg)  
Fig.7Equivalent stress distributions at the drum - downcomer junction without pressure load (gauge pressure $p = 0 \mathrm { M P a } )$ for different heating rates; a) $\nu _ { T } = 1 ~ \mathrm { K / m i n }$ b) $\nu _ { T } = 1 2 \mathrm { K } / \mathrm { m i n }$ （204号

![](images/d294db5d539df97f05e8fbd4331cb7b3940f6aa2e393a921df8cabf824f93a56.jpg)  
Fig.8 Equivalent stress distributions at the drum - downcomer junction without pressure load $( p = 1 0 . 8 7 \mathrm { M P a } )$ for different heating rates;a) $\nu _ { T } = 1 ~ \mathrm { K / m i n }$ b) $\nu _ { T } = 1 2$ $\mathrm { { K } / \mathrm { { m i n } } }$

![](images/3ba1ff9f4d82e44c87fc45d561fe74e686777e6c3817830168476387baa1f43f.jpg)  
Fig.9Thermal stress concentration coefficient $\alpha _ { T }$ asa functionof the heat transfer coefficient $h$

However, the thermal stress concentration coefficient at the opening edge in the complex shaped components depends on the heat transfer coefficient $h$ . Since the boiler drum has openings for downcomers,an intense concentration of stress is present at the edge of the opening.It can also be noted that the stress concentration coefficient at the edge of the opening strongly influences theheat transfer coefficient on the inner surface of the boiler drum and the downcomer. The value of the stress concentration coefficient $\mathbf { \alpha } _ { \mathrm { { { d r } } } }$ is lower at point ${ \bf P } _ { 1 }$ -as compared to its value at point ${ \bf P } _ { 2 }$ - regardless of the value of the heat transfer coefficient (Fig. 9).

When the heat transfer coefficient is equal to: $h =$ $1 0 0 0 0 ~ \mathrm { \ W / m ^ { 2 } K }$ ，the stress concentration coeficient at point ${ \bf P } _ { 1 }$ is: $\alpha _ { T } = 1 . 5 3$ ，and at point ${ \bf P } _ { 2 }$ ：： $\alpha _ { T } = 1 . 8 6$ . The thermal stress concentration coefficient was calculated using the formula

$$
\alpha _ { T } = \frac { \sigma _ { \varphi , P _ { 1 } } } { \sigma _ { \varphi , w } }
$$

where $\sigma _ { \varphi , P _ { 1 } }$ denotes circumferential stress at the edge of the opening at point ${ \bf P } _ { 1 }$ and $\sigma _ { \varphi , w } = \sigma _ { \varphi } \left( r _ { w } \right)$ stands for circumferential stress on the inner surface of the boiler drum or pressure vessel without openings.

The total circumferential and equivalent stress at the edge of the opening at points ${ \bf P } _ { 1 }$ and ${ \bf P } _ { 2 }$ can be approximated linearly as a function of the heating rate.At the beginning of the boiler start - up, the gauge pressure in the drum is equal to zero thus the absolute values of circumferential and equivalent stresses at the points ${ \bf P } _ { 1 }$ and ${ \bf P } _ { 2 }$ are equal (Fig. 1O). The total circumferential and equivalent stresses presented in Fig.11 were computed considering pressure and thermal loads.

The circumferential stress at points ${ \bf P } _ { 1 }$ and ${ \bf P } _ { 2 }$ for pressure $p = 1 0 . 8 7$ MPa can be approximated by a linear function with respect to $\nu _ { T }$

$$
\sigma _ { \varphi } = a + b \nu _ { T }
$$

![](images/b28fb4147a113659815f455893a146a1ea9e7cf499379ff8f8d52abe52aaac1e.jpg)  
Fig.10 Circumferential stress and equivalent stress at the edge of the downcomer opening at points ${ \bf P } _ { 1 }$ and ${ \bf P } _ { 2 }$ for the gauge pressure $\mathrm { \Delta p = 0 \ M P a }$ ；1- circumferential stress at point ${ \bf P } _ { 1 }$ ,2- equivalent stress at point ${ \bf P } _ { 1 }$ ,3-circumferential stress at point ${ \bf P } _ { 2 }$ ,4-equivalent stress at point ${ \bf P } _ { 2 }$ ,5-allowable circumferential stress, $6 -$ allowable equivalent stress

![](images/202cec47b4b41113067af534e0a295ba2a7e98aa86d57e770a6fdf780ad8d584.jpg)  
Fig.11Circumferential stress and equivalent stress at the edge of the downcomer opening at points ${ \bf P } _ { 1 }$ and ${ \bf P } _ { 2 }$ for the pressure $\mathsf { p } = 1 0 . 8 7 \ \mathrm { M P a }$ ；1-circumferential stress at point $\mathbf { P } _ { 1 : }$ ，2-equivalent stress at point ${ \bf P } _ { 1 }$ 3 circumferential stress at point ${ \bf P } _ { 2 }$ ，4-equivalent stress at point ${ \bf P } _ { 2 }$ ,5-allowable circumferential stress, 6 -allowable equivalent stress

The allowable $\nu _ { T I }$ and $\nu _ { T 2 }$ boiler drum heating rates can be determined from the condition $\sigma _ { \varphi } = \sigma _ { a }$ ，where the circumferential stress $\sigma _ { \varphi }$ is given by Eq.(19). The same method can be applied to other components of complex shapes.The issue of optimization of heating and cooling of thick walled boiler components was presented in [5] without the assumption of the quasi-steady state.

However, the developed method for determining the allowable rate of cooling or heating pressure components is simple and can be easily used in the practice.

# Components with Non - uniform Circumferential Temperature Distribution

There is an uneven temperature distribution on the drum circumference due to the presence of the water and steam zone.During start-up of the boiler, steam condenses on the inner surface of the drum in the steam zone During the steam condensation, the upper part of the drum is heated very quickly because the heat transfer coefficient at the time of condensation is very high. The bottom of the drum, occupied by the water, the coeficient of heat transfer from the water to the inner surface of the drum is low,and the heating of the lower part of the drum occurs much more slowly. Heating at different rates of the upper and lower portions of the drum results in a temperature difference between the top and bottom of the drum. It should be pointed out that the temperature of the upper part of the drum is higher than the temperature of the lower part. A similar phenomenon can be observed in the horizontal sections of the pipeline and superheater headers.At the beginning of the start-up of the boiler, pipes are cold and water vapor condenses on the walls of the pipes.At the bottom of the horizontal piping and other pressure components of the boiler water accumulates at the bottom, especially when the drainages of the elements are not functioning properly. Such a case occurs when the horizontal pipelines and superheater headers are plastically deformed.In a later stage of the boiler start-up superheated steam flows through the upper part of the pipeline while at the bottom of the pipeline is saturated water. This is the reason for the occurrence of very large temperature differences on the circumference of the pipe,which reach up to about 20oK.For this reason,permanent deformation of pipes and headers often occur,which in turn makes that the draining horizontal elements are not working properly. The stresses caused by temperature non-uniformity on the circumference of the pipe may be higher than the stress caused by temperature difference across the thickness of the pipeline. In the current European Standard EN 12952-3， thermal stresses caused by the temperature difference on the circumference of the cylindrical element are not at all taken into account. In this paper,an analysis of the heating of horizontal thick walled components will be carried out taking into account the different values of heat transfer coefficients in the water and steam zone (Fig.12). Calculations are performed assuming that the temperature of the fluid increases linearly with time so that after some time forms a quasi-steady state temperature field. This paper examines thermal and strength loads of the drum of the steam boiler OP-210M during startup.Figure 13 illustrates the time changes of the water level. The water level in the drum situated $H _ { w } = 1 0$ cm below the horizontal plane passing through the axis of the drum is taken as the zero level. The water temperature in the evaporator increases resulting in an increase in the specific volume of the water and rising water level in the drum. After about 12ooo seconds, the excess water is discharged from the drum and the waterlevelisloweredto alevel close to zero.The time variations of the saturation pressure in the drumis depicted in Fig.14.Measured time variations of the drum temperature at seven points shown in Fig. 14 indicate that temperature differences on the drum circumference,especially at the initial period of the drum heating are significant.

![](images/4e90f45783e9abc46896575196c524633fcf79edda53435ce4dd4a637540582b.jpg)  
Fig.12The cross-section of the boiler drum with locations of thermocouples used for temperature measurement

![](images/345af4164eecee49a309f028003ef2ac54143e4e7e75cb9e22485efa147c0ca7.jpg)  
Fig.13Time variations of the level of water in the drum of OP-210Mboiler during the start-up

Asalready explained earlier, the faster heating of the upper part of the drum is due to vapor condensation on the inner surface of the drum,during which the heat transfer coefficient is very high. After about 15000 seconds the temperature difference between the top and the bottom of the drum is reduced considerably (Fig.14). The maximum temperature difference between the top and bottom of the drum does not exceed $5 0 \mathrm { K }$ . It must be emphasized that such a large temperature difference at the circumference of the drum is the cause of high thermal stresses.The analysis of the experimental results shows that in the initial stage of drum heating there are large temperature differences on the perimeter, which are the cause of additional thermal stresses.The current boiler standards do not take into account the boiler stresses due to temperature difference on the perimeter of the horizontal elements. Onlyquasi-stationarythermal stresses caused by the temperature difference across the wall thickness are considered.

Assuming the existence of quasi-stationary temperature field in the pressure element, the temperature difference on the component circumference caused by different heat transfer coefficients on the inner surface will be taken into account. The time variations of the circumferential stress at the edge of the drum- downcomer junc tion at the points ${ \bf P } _ { 1 }$ and ${ \bf P } _ { 2 }$ are shown in Figs.15 and 16.

![](images/c879fe09add4e1a21840816154a8facf3ffb690bc8da71ff1382fc99425560a6.jpg)  
Fig.14Temperature and pressure variations on the drum circumference during the boiler start -up

The analysis of the results depicted in Figs.15 and 16 shows that the absolute value of thermal stresses at the point ${ \bf P } _ { 2 }$ is much greater than those at the point ${ \bf P } _ { 1 }$ .It should be noted that the heat transfer coefficient in the water area is greater than $1 0 0 0 \ \mathrm { \ W / ( m ^ { 2 } { \cdot } K ) }$ .Due to the higher value of compressive thermal stress and a lower value of the tensile stress due to pressure occurring at point ${ \bf P } _ { 2 }$ , the permissible rate of the drum heating should be determined due to the stress at the point ${ \bf P } _ { 2 }$ . Changes in the circumferential stress and equivalent at points ${ \bf P } _ { 1 }$ and ${ \bf P } _ { 2 }$ as a function of heating rate are shown in Figure 17.In Figure 17a, the gauge pressure in the drum is $\boldsymbol { \mathrm { p } } = \boldsymbol { 0 }$ while in Figure 17b the pressure is equal to the design value of $1 0 . 8 7 \mathrm { M P a }$ ：

It should be emphasized that during the start-up of the boiler heat transfer coefficient in the water zone is less than in the steam zone.In such cases,a maximum allowable heating rate is determined by the stresses at the point ${ \bf P } _ { 1 }$ ：

![](images/354d544580479aa0345482fa8e0525c0fc53f26e2bf6ef42a87a319ff23bf197.jpg)  
Fig.15Circumferential stresses on the hole edge at the point ${ \bf P } _ { 1 }$

![](images/b6b03a8faf57002cfca5cc84fbc6a76682abf18f867afdc12fa785d0652378ed.jpg)  
Fig.16 Circumferential stresses on the hole edge at the point ${ \bf P } _ { 2 }$

For a typical case that occurs in practice [7], when $h _ { w }$ $= 1 0 0 0 \ \mathrm { W / ( m } ^ { 2 } \mathrm { \cdot K ) }$ and $h _ { s } = 1 0 0 0 0 \mathrm { W } / ( \mathrm { m } ^ { 2 } \mathrm { K } )$ , the permissible heating rate at the beginning of the boiler start-up when $\mathbf { p } = 0$ is approximately $3 \mathrm { ~ K ~ } / \mathrm { \ m i n }$ Currently, the permissible rate of the drum heating recommended by boiler manufacturers is about $1 \mathrm { K / m i n }$ .Allowable heating rate equal $3 \mathrm { K / m i n }$ (Figure 17a) resulting from the FEM analysis is significantly higher than the value prescribed by the boiler manufacturers.The start-up of the boiler can thus be shortened three times.

# Conclusions

Summarizing the obtained results,it should be noted that the assumption of quasi - steady temperature field significantly simplifies the determination of the allowable rates of fluid temperature changes during the heating and cooling of boiler thick walled components.The thermal stress concentration coefficients can be quickly determined with the use of the Finite Element Method (FEM),also for components of very complex shapes.For flat,cylindrical and spherical walls,in which the temperature distribution is one-dimensional, the thermal stress concentration coefficient does not depend on the value of the heat transfer coefficient.It was also shown that the heat stress concentration coefficient for the structural components of complex shapes depends on the value of the heat transfer coefficient on their inner surface.

![](images/6d50b234fa4105799e3d993a604a7396a6ccf51afe252e90d6333c4328fc4203.jpg)  
Fig.17Circumferential stress and equivalent stress at the edge of the downcomer opening at points ${ \bf P } _ { 1 }$ and ${ \bf P } _ { 2 }$ for $h _ { \scriptscriptstyle { w } } = 1 0 0 0 \mathrm { W } / ( \mathrm { m } ^ { 2 } \mathrm { K } )$ and $h _ { s } = 1 0 0 0 0 \mathrm { W } / ( \mathrm { m } ^ { 2 } \mathrm { K } )$ ;a) drum gauge pressure $\mathrm { ~ \tt ~ p ~ } = \mathrm { ~ 0 ~ }$ MPa,b） drum gauge pressure $\mathsf { p } = 1 0 . 8 7 \mathrm { M P a }$ ; 1-circumferential stress at point ${ \bf P } _ { 1 }$ ，2- equivalent stress at point $\mathrm { ~ P ~ } _ { 1 } , \ 3 \ \mathrm { ~ - ~ }$ circumferential stress at point ${ \bf P } _ { 2 }$ ，4-equivalent stress at point ${ \bf P } _ { 2 }$ ，5- allowable circumferential stress, $6 -$ allowable equivalent stress

It has also analyzed quasi-steady state temperature field and stress in thedrum - downcomer junction considering the different heat transfer coefficients in the water and steam space.Graphs presented in the chapter allow to determine heating rate limits at the beginning of the boiler start-up when the pressure is equal to O and at the end of starting when the pressure is equal to the nominal pressure.Permissible drum heating rates,assuming both circularly symmetric and asymmetric circular cross-section temperature field in the due drum obtained by the proposed method are several times higher than the limit values recommended by the manufacturers ofboilers.

# References

[1]Dzierwa,P.,2O12,Determining of allowable heating and cooling rates of boiler pressure components using the quasi steady-state theory,Energetyka 65,pp.32-37.   
[2]Dzierwa,P.，2013,Quasi-Steady-State Approach for Solving Transient Heat Conduction Problems, Chapter in: Encyclopedia ofThermal Stresses,Vol.VI,ed.Hetnarski R., Springer, pp.4083-4092,Dordrecht-Heidelberg.   
[3]European Standard EN 12952-3 (2012）Water-tube boilers and auxiliary installations-Part 3:Design and calculation for pressure parts, European Committee for Standardization,Brussels.   
[4] Taler,J.,1995,Theory and practice of identification of heat flux processes, Ossolineum,Wroclaw (in Polish).   
[5] Taler,J.,Dzierwa,P.,2011,A new method for optimum heating of steam boiler pressure components.International Journal ofEnergy Research,35,pp.897-908.   
[6]TRD 301,2001,Zylinderschalen unter innerem Uberdruck. Technische Regeln fir Dampfkessel (TRD), Heymanns Beuth Koln-Berlin, pp.143-185.   
[7]P.Dzierwa,2015,Increasing flexibility of steam boilers with natural circulation,Monograph No.515,Publishing House of Cracow University of Technology, Cracow.