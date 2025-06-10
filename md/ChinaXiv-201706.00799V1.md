# An Analysis of the Numerical Model Influence on the Ground Temperature Profile Determination

Marek Jaszczur1\*, Inga Polepszyc1,Aneta Sapinska-Sliwa², Andrzej Gonet²

1. Faculty of Energy and Fuels, Department ofFundamental Research in Energy Engineering 2.Faculty of Drilling, Oil and Gas ale Department of Drilling and Geoengineering AGH University of Science and Technology,al. Mickiewicza 30,30-059 Krakow,Poland

$\copyright$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

The estimation of the ground temperature profile with respect to the depth and time is the key issue in many engineering applications which use the ground as a source of thermal energy.In the present work,the influence of the model components on the calculated ground temperature distribution has been analysed in order to develop an accurate and robust model forthe prediction of the ground temperature profile.The presented mathematical modeltakes into account allthe key phenomena occurring in the soil and on its top surface.The impact of individual model elements on the temperature of the soil has been analysed.It has been found that the simplest models and the most complex model result in a similar temperature variation over the simulation period,but onlyat a low depth.Adetailed analysis shows that a larger depth requires more complex models and the calculation with the use of simple models results in an incorrect temperature and a theoretical COP estimation.

# Keywords: heat transfer, ground heat transport, ground temperature profile, ground source heat pump

# Introduction

The recent rapid growth in many engineering and geothermal applications which use the ground as a source of thermal energy or as a lower heat source has been noticed.

These applications typically strongly depend on the temperature fluctuations in the near surface region. The ground temperature is crucial parameters describing the potential of the thermal energy in the soil and directly influences the ground base heat pump systems efficiency COP(Coefficient of Performance）and SPF(Seasonal Performance Factor).An accurate design of the ground source system,which uses the ground heat in the winter season isa relatively complex task.It requiresknowledge in the field of heat transport,engineering application, geology as well as environmental protection.

To provide a sufficient number of data for a proper system design, typically,numerical models or simplified analytical/empirical models are used [2]. Numerical models have the advantage of being able to include complex physical phenomena, a complicated soil structure or realistic boundary conditions. Simulations of this type allow a detailed system analysis and a precise selection of the system's element. The designing of a heat exchanger for the lower heat source,without unnecessary re-dimensioning,may lead to a significant reduction of the investment costs [7,8] however, underestimation, may lead to improper system operation,often deep freezing and in the worst case, damage the ground heat exchanger.

In order to estimate precisely the ground potential and to conduct a computer analysis,it is necessary to have information about the soil's geological structure and thermo physical properties as well as the accurate boundary conditions at all surfaces.Without the knowledge of those parameters,a computer simulation which includes complex models of heat transport in the ground [9] is not able to provide correct information for the selection of the ground heat exchanger. Also,attention to the initial ground temperature profile has to be paid. The analysis presented in the literature [1O,11] shows that the soil temperature in the near surface region is significantly, daily and seasonally, dependent on ambient temperature [12],but there are no studies about such models which are a combination of different weather elements e.g. solar radiation, wind speed or air temperature.

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>Pz, Pw</td><td> ground, water density, kg/m3</td><td></td><td>Stefan-Boltzmann constant, W/(m²·K4)</td></tr><tr><td>Cpz, Cw</td><td> ground, water specific heat, J/(kg:K)</td><td>f</td><td>fraction of evaporation rate</td></tr><tr><td>k</td><td> ground thermal conductivity, W/(m·K)</td><td>rh</td><td>air relative humidity</td></tr><tr><td>t</td><td>time, s</td><td>Tsky</td><td>reference (sky) temperature, K</td></tr><tr><td>Vi</td><td>the Darcy velocity, m/s</td><td>Tair</td><td>air temperature, K</td></tr><tr><td></td><td>emissivity,</td><td></td><td></td></tr></table></body></html>

In the present work, we develop a mathematical and numerical model of heat transport in the ground, taking into account all the important, or only selected, physical phenomena.The analysis of the selected phenomena has allowed to decide which heat transfer components are the most important for this type of modelling. The estimation of the temperature profile [3] and the mean seasonal temperature of the ground has allowed to estimate the ground thermal potential, which is often one of the most important criteria for an economic justification for the use of this kind of systems.

# MathematicalModel

In order to calculate the temperature in the ground,it is necessary to construct an accurate mathematical model of the occurring transport phenomena [13]. A graphical representation of energy balance including the important phenomena is given in Figure 1.

The symbols represent the heat flux exchange by: $q _ { c o n 1 }$ - the natural convection, $q _ { c o n 2 } -$ the forced convection, $q _ { s o l } -$ the solar direct and indirect radiation, $q _ { t e r } -$ the Earth solar radiation, $q _ { e \nu a } -$ the water evaporation from the top ground surface.Additionally, $q _ { f }$ represents the the heat flux related to the groundwater flow, $q _ { p h }$ -the heat flux related to the phase change and $q _ { \theta }$ - the Earth natural heat flux.

In the present study, the soil consists of several lithological layers with $L _ { i }$ thicknesses and different thermophysical properties (see Table 1). Assuming unsteady phenomena, ground waters flow and phase changes in the soil as well as the variations of the soil properties with the depth, the equation for the thermal energy transfer can be written as follows:

$$
\begin{array} { r l } & { \rho _ { z } c _ { p z } \displaystyle \frac { \partial T } { \partial t } + \rho _ { w } c _ { w } \Bigg ( \upsilon _ { x } \displaystyle \frac { \partial T } { \partial x } + \upsilon _ { y } \displaystyle \frac { \partial T } { \partial y } + \upsilon _ { z } \displaystyle \frac { \partial T } { \partial z } \Bigg ) = } \\ & { k _ { z } \displaystyle \frac { \partial ^ { 2 } T } { \partial x ^ { 2 } } + k _ { z } \displaystyle \frac { \partial ^ { 2 } T } { \partial y ^ { 2 } } + \frac { \partial } { \partial z ^ { 2 } } \Bigg ( k _ { z } \displaystyle \frac { \partial T } { \partial z } \Bigg ) + s } \end{array}
$$

where $\rho _ { z } , \rho _ { w }$ ，are the ground and water densities, $c _ { p z } ,$ $c _ { w }$ is the specific heat of the ground and water, $k _ { z }$ is the thermal conductivity of the ground, $t$ istime, $\upsilon _ { x }$ is the Darcy velocity of the groundwater flow in $x$ direction, $\upsilon _ { y }$ and $\upsilon _ { z }$ are respectively in $y , z$ direction, and $s$ means the source term resulting from the phase change.

![](images/6546972eb9b09aae1f73225e904fc5539c37ea08f02cc91359bec80c77e65027.jpg)  
Fig.1The main elements of the thermal energy balance

Table1 Lithological profile of the ground   

<html><body><table><tr><td>Ceiling [m]</td><td>Floor [m]</td><td>Thermal conductivity [W/mK]</td><td>Heat capacity [kJ/m³K]</td></tr><tr><td>0</td><td>2.3</td><td>1.60</td><td>2400</td></tr><tr><td>2.3</td><td>3.0</td><td>1.00</td><td>1600</td></tr><tr><td>3.5</td><td>4.5</td><td>1.20</td><td>1700</td></tr><tr><td>4.5</td><td>10</td><td>1.40</td><td>2300</td></tr><tr><td>10</td><td>15</td><td>0.50</td><td>2300</td></tr><tr><td>15</td><td>35</td><td>2.40</td><td>2300</td></tr><tr><td>30</td><td>100</td><td>2.30</td><td>2300</td></tr><tr><td>Mean values</td><td></td><td>1.485</td><td>2128.5</td></tr></table></body></html>

It is important to notice that the water content in the ground is going to freeze when the temperature is lower than $0 ^ { \circ } \mathrm { C }$ and, in this case, the water property will change according to the formula presented in [1]. In the case of water freezing the local underground flow velocity changes according to the mass conservation equation.

# Elements of the energy balance on the top surface of the ground:

The equation of the energy balance for the ground surface depends on the model being considered and it maybewritten, forModel1,asfollows:

$$
T \left( x , y , z , t \right) = f \left( t \right)
$$

and for other models (Model2-Model4) as follow:

$$
\frac { \partial } { \partial z } \Bigg ( k _ { z } \frac { \partial T \left( x , y , z , t \right) } { \partial z } \Bigg ) = f \left[ q \left( t \right) \right] = f \left[ q _ { _ { t o t } } \left( t \right) \right]
$$

The heat flux $q _ { t o t }$ variable in time,is the difference between the heat flux transfer $q _ { i n }$ into the ground surface and the heat flux transfer from the ground surface $q _ { o u t }$ ：

$$
q _ { t o t } = q _ { i n } \mathrm { ~ - ~ } q _ { o u t }
$$

This study takes into account up to all (in the most complex Model 4) the key atmospheric phenomena presented in Fig.1.In accordance with the heat exchange methods provided, the heat flux balance for the ground top surface can be written as:

$$
q _ { t o t } = \operatorname* { m a x } { \left( q _ { c o n 1 } , q _ { c o n 2 } \right) } + q _ { s o l } + q _ { t e r } + q _ { e v a }
$$

The first two balance components in eq.(5) represent free and forced convection. When the positive temperature gradient is detected above the ground surface,the conditions for free (natural) convection $q _ { c o n 1 }$ are met. When the wind speed is non-zero forced convection $q _ { c o n 2 }$ occurs.In the present paper, is was assumed that,at the local scale,the earth is a flat horizontal plate and the convective heat transport may be determined as:

$$
q _ { c o n } = \alpha _ { _ { c o n } } \cdot \left( T _ { _ { a i r } } - T \left( x , y , z , t \right) \right)
$$

where: $\alpha _ { c o n } \mathrm { - } \alpha _ { c o n 1 }$ or $\alpha _ { c o n 2 }$ are the heat transfer coefficients,in the case of free and forced convection,respectively and, $T _ { a i r } ,$ is the air temperature.Because of the complex model equations for the convective heat transfer analysis,usually semi-empirical solutions are used. For forcedconvection,thevalueof theNusselt numberwas determined based on the following formula for the laminar and turbulent flow regime over the flat plate [9]:

$$
\begin{array} { r } { N u = 0 . 6 6 4 \mathrm { { R e } } ^ { 1 / 2 } { \mathrm { P r } } ^ { 1 / 3 } \quad } \\ { N u = 0 . 0 3 7 \mathrm { { R e } } ^ { 4 / 5 } { \mathrm { P r } } ^ { 1 / 3 } \quad \mathrm { { f o r } \quad { R e } > 1 0 ^ { 5 } } } \end{array}
$$

In the case of natural convection,the following for mula were used [7]:

$$
\begin{array} { c } { { N u = 0 . 5 4 \mathrm { R a } ^ { 1 / 4 } \quad \mathrm { f o r } \quad 1 0 ^ { 4 } < \mathrm { R a } < 1 0 ^ { 7 } } } \\ { { N u = 0 . 1 5 R a ^ { 1 / 3 } \quad \mathrm { f o r } \quad 1 0 ^ { 7 } > \mathrm { R a } } } \end{array}
$$

Each time step only one type of convection, the one that had higher contributions to the balance (eq. 5） was taken into account.

The second element of the heat balance on the ground surface is solar radiation $q _ { s o l }$ calculated based on the measured data. It was assumed in this study that the earth's surface can be treated as the approximation of a perfect grey body with the emissivity of $\varepsilon = 0 . 9 7$ ：

Due to the differences between ambient temperature and ground temperature,the amount of thermal radiation heat source $q _ { t e r }$ can be determined from the following formula:

$$
q _ { t e r } = \varepsilon \cdot \sigma \cdot \big ( T \big ( x , y , z , t \big ) ^ { 4 } - T _ { s k y } ^ { 4 } \big )
$$

Where $T _ { s k y }$ is the reference temperature. The reference (or sky) temperature in the present mathematical model was calculated with the following formula [12-14]:

$$
T _ { s k y } = 0 . 0 5 5 2 \cdot T _ { a i r } ^ { 1 . 5 }
$$

The heat flux related to the evaporation $q _ { e \nu a }$ depends on several factors (soil moisture,air temperature,velocityand humidity) and can be calculated from the following formula [16,17]:

$$
q _ { e v a } \ = \ f \cdot \alpha _ { _ { c o n } } \cdot \left[ \left( a \cdot T \left( x , y , 0 , t \right) + b \right) - r _ { h } \left( a \cdot T _ { _ { a i r } } + b \right) \right]
$$

where $f$ is the fraction of evaporation rate depending on the ground moisture and cover, $r _ { h }$ is the air relative humidity, and $a , b$ are the eq. constants $( \mathrm { a } { = } 1 . 7 3 , \mathrm { b } { = } 1 0 . 2 3$ ） The actual value of air relative humidity was taken from a meteorological measurement. The fraction of evaporation rate $f$ was assumed to be O.6 which is typical for moist soil.

For the current research,all the models take into consideration the Earth's heat flux $\mathrm { q } _ { \mathrm { e } } { = } 7 0 \mathrm { m W } / \mathrm { m } ^ { 2 }$ ：

Based on the heat balance on the surface (eq. 5), four different modelsconcerning selected environmental phenomena were developed (see Table 2).

Table 2Mathematical models for the top surface.   

<html><body><table><tr><td colspan="2">Assumed conditions on the ground top surface (z=0)</td></tr><tr><td>Model 1</td><td>T(x,y,z,t) = f(t)</td></tr><tr><td>Model 2</td><td>dz dT(x，y，z)= f[con()</td></tr><tr><td>Model 3</td><td>dz dr(xy,2)=f[4o()+qs()+qr()</td></tr><tr><td>Model4</td><td>dz dr(xy,2)= f[()+()+qr(1)+a()</td></tr></table></body></html>

# NumericalModelandResults

In order to solve the presented mathematical model, a numerical algorithm was developed in Fortran 9O,based on the finite volume method.For the convective terms and diffusion terms,the second order accurate central difference scheme was used CDS).For the spatial derivative，three-level second order accuracy methods were implemented.The spatial and temporary discretization were determined on the basis of the testing calculations, which allowed to make the solution independent from numerical parameters.In order to speed-up computations the variable time step procedure was used. The geometry for analysis including the area with the dimensions of 30 $\times ~ 3 0 \times 1 0 0 ~ \mathrm { m }$ ,in the directions X,y and $z$ ，respectively. The applied mesh $( 5 0 \times 5 0 \times 1 5 0 )$ ）was irregular, fine close to the surface,where the temperature changes were significant and coarse for the depth larger than $3 0 \mathrm { m }$ The local mean annual temperature $T _ { i n i } = 9 . 6 ^ { \circ } \mathrm { C }$ was used as initial and boundary condition for the side geometry walls.

Temporary values of air temperature $T _ { a i r } ,$ wind speed magnitude $U$ and solar total radiation $l _ { T } ,$ were introduced into the model from the meteorological measurements for the location:Kraków Poland (performed in 2014).In order to obtaina statistically steady solution(for a period of 1 year),the same weather information was repeated for a 10 year calculation period.

![](images/75c22025493e0a6ae65a591e25f326d8c1fda83422fd494df5252b45ab6a15d1.jpg)  
Fig.2Calculated temperature vs. experimental measurement for region of Bialystok City [18] and depth $z = 1 \textrm { m }$ (top) and $z = 2 \mathrm { m }$ (bottom).

# Comparison with experimental measurement:

The numerical model was validated with theexperimental measurements of the ground temperature carried out in the region of Bialystok,Poland[18].For the local soil thermal properties and the measured air temperature the ground temperature at the two different depths $\mathit { \Pi } _ { \left[ { \overline { { z } } } \right. } = 1$ m and $z = 2 ~ \mathrm { m }$ )for the time of one year 2oo1 is presented in Figure 3 and compared with the experimental measurements.

Taking into account the fact that the exact environ mental conditions were not known, the air temperature was measured at $1 0 \ \mathrm { a . m }$ .only (approximately every two weeks)，while the ground structure except density and moisture content were not measured. The agreement between the experimental measurements and the numerical prediction at two different depths is relatively good.

![](images/74dbf85cefb1d588e9f86d598c06ddfc9cf7b895062df18a393f12a2bbacacab.jpg)  
Fig.3Comparison of models for a lO-year calculation at the depth $z = 1 \mathrm { m }$ (top) and $z = 5 \mathrm { m }$ (bottom).

The largest difference occurs at the end of the summer season,when very high temperatures occasionally occur on the day of the measurement (237th day of the year with the temperature of $3 0 . 6 ^ { \circ } \mathrm { C }$ ),and this value was used until the next measurement was performed. The second source of difference between the numerical and the experimental results is the initial temperature profile.

The unsteady solution depends not only on the boundary conditions but also on the initial conditions.In the case of numerical simulations uniform temperature of $8 . 5 ^ { \circ } \mathrm { C }$ was set-up,while in the real soil structure, the temperature profile is a result of the historical weather phenomena.

Models analysis:Figure 3 shows the temperature of the ground calculated for 1O years with the use of four different models (Model 1-Model 4) considered in this work.Figure 3 (top) presents the temperature at the depth $z = 1 \mathrm { ~ m ~ }$ .It can be seen that the most complex model (Model 4)which is considered here as the reference model, could be roughly approximated with all other models.Similar results for the depth $z = 5 \mathrm { ~ m ~ }$ ，are shown in Figure 3(bottom) where the temperature level as well as the amplitude of temperature oscillations are much lower.Again,also at this depth,all the models follow roughly the Model 4.The temperatureat this depth is going to be statistically steady (for the period of1 year) after approximately 5 years.

Figure 4 presents temperatures at the four different depths $z = 0$ ，1, 2 and $5 \mathrm { m }$ and for the last year of simulations.The calculated top surface temperature depends on the mathematical models used.As a consequence, the temperatures inside the ground are also slightly different. The largest difference at the ground surface $( z = 0 \ \mathrm { m } )$ （号 occurs for Model 1.This model is only air temperature dependent and “smoothes” the surface temperature.Neither the solar radiation nor the wind speed influence the surface temperature in this model.It is interesting to notice that the top surface temperature calculated with Model1 is always between the results predicted with the other models.Additionally, the amplitude of temperature fluctuations was always significantly smaller for this model. These phenomena are well seen at larger depths. The temperature fluctuations predicted with Model1 are smaller also at depths $z = 1$ ,2, $5 \mathrm { m }$ in reference to Model 4 as well in comparison to the other models.

Models 2 and 3 result in temperatures which are overestimated in the summer season and in temperatures which are very close to the reference models in the winter season (see Model 3).Finally, Model 3 results in the largest temperature fluctuations.

This model takes into account all the weather pheno mena except for evaporation which significantly stabilises the temperature fluctuation.All these behaviours are very clearly seen at the largest depth $z = 5 \mathrm { ~ m ~ }$ ，where Model 2 predicted a temperature difference mostly in reference to Model 4,and the temperature difference is almost constant over the whole period and equal to about $1 . 5 ^ { \circ } \mathrm { C }$ 、For this depth it can be also clearly seen that the amplitude of the temperature fluctuations is the largest for Model 3.

Figure 5 presents the temperature distribution with the depth at two different time periods of the year (at the end of the year and in the middle of the year). The scope of changes regards mainly the area up to ca. $2 0 \mathrm { m }$ of depth. In the case of different mathematical models used to calculate the temperature,the difference occurs also at larger depths.

The profiles of temperature for different time periods show where the largest temperature variations are observed.Up to about $1 { \cdot } 1 . 5 \mathrm { ~ m ~ }$ ，the freezing zone occurs and the ground temperature may drop below $0 ^ { \circ } \mathrm { C }$ Approximately at this depth area,the largest temperature variation is seen.Approximate at the depth $z = 1 . 5 \mathrm { m }$ the first temperature inflection point is seen (see Figure 5 bottom).The second inflection point is seen at the depth z $= 5 \mathrm { ~ m ~ }$ .Depending on the model used for the temperature calculation result temperature atdifferent depths and at various time period may differ significantly. The largest temperature difference between the models was observed around the first inflection point in the middle of the year. The temperatures predicted with the Model 4 and Model 2 differ as much as $4 ^ { \circ } \mathrm { C }$ which is one of the largest differences detected between the models over the whole year.

![](images/4465389ded8f35d64db10d0cea06096bf1c1d82d34df1e6362990064627d30dd.jpg)  
Fig.4 Comparisonof mathematical models for last year calculation at the depth $z = 0 , 1 , 2 , 5 \mathrm { m }$

![](images/72b7db09ebdfac757d8d25bc7e9feaa454bba2559e2282dede4272adfcf04e3c.jpg)  
Fig.5The profile of temperature at the end of the simulation (top) and in the middle of last year (bottom).

At the depth of about $z = 2 0 \mathrm { ~ m ~ }$ ，the temperature time variation is below $0 { , } 5 ^ { \circ } \mathrm { C }$ and this value is influenced only by significant weather phenomena variations over a long period.

The mean annual and mean seasonal temperature calculated for all the models are presented in Table 3 for the depth $z = 1 \mathrm { ~ m ~ }$ and $5 \mathrm { ~ m ~ }$ .The mean seasonal temperature for $z = 5 \mathrm { ~ m ~ }$ is in the range from 9.39 to $1 0 . 7 5 ^ { \circ } \mathrm { C }$ for all the models and only 9.5 to $9 . 3 9 ^ { \circ } \mathrm { C }$ for Model1 and Model 4.It is worth noticing that the mean values acquired by means of the said models overlap highly. The presented mean annual and mean seasonal temperature values should be treated as the theoretical upper limit value for the heat pump or they should be more precise for the ground heat exchanger. In the absence of a ground heat exchanger (heat pump component) there is no heat transfer from the ground into the heating system. Typically, the heat transfer will decrease the local temperature significantly and influence the overall system performance (COP/SPF).

# Conclusions

In this paper, different mathematical modelsfor ground temperature calculations have been studied.The influence of the environmental model on the calculated ground temperature distribution has been analysed in order to develop a fast,accurate and well convergent model for the modelling of the ground source heat pump system.The presented mathematical model takes into account all the key phenomena occurring in the ground and on its top surface. The impact of individual compo nents on the temperature of the soil has been analysed.

Table 3Mean annual and mean seasonal ground temperature.   

<html><body><table><tr><td colspan="2">mean annual vs</td><td>Model 1</td><td>Model 2</td><td>Model 3</td><td>Model 4</td></tr><tr><td colspan="2">mean seasonal (1 Sep.-31 Mar.)</td><td>conduction</td><td>conduction + convection</td><td>conduction + convection+ thermal radiation</td><td>conduction+ convection+ thermal radiation + evaporation</td></tr><tr><td rowspan="2">z=0m</td><td>T[C]</td><td>9.78</td><td>9.64</td><td>9.64</td><td>9,64</td></tr><tr><td>T [c]</td><td>16.34</td><td>16.23</td><td>16.23</td><td>16.23</td></tr><tr><td rowspan="2">z=1m</td><td>T[oC]</td><td>9.75</td><td>11.36</td><td>10,62</td><td>9.61</td></tr><tr><td>T[c]</td><td>14.30</td><td>15.98</td><td>16.85</td><td>15.11</td></tr><tr><td rowspan="2">z=2 m</td><td>T [C]</td><td>9.74</td><td>11.27</td><td>10,57</td><td>9.6</td></tr><tr><td>T [C]</td><td>12.56</td><td>14.13</td><td>14.48</td><td>13.03</td></tr><tr><td rowspan="2">z=5m</td><td>T[C]</td><td>9.71</td><td>10.98 10.75</td><td>10,39</td><td>9.59</td></tr><tr><td>T[C]</td><td>9.5</td><td></td><td>10.21</td><td>9.39</td></tr></table></body></html>

Model 4, the most advanced one,taking into account all the important phenomena (convection, solar radiation, evaporation),hasbeen considered asa referencemodel and in theory, it should match the real conditions in the best way. It has been found that none of the models was able to reproduce the temperature distribution or temperature variation with an accuracy similar to thereference model.A good approximation with a relatively small errorhas been achieved with the simplest, Model1.This model behaves surprisingly well in comparison to the more complex models - Model2 and Model3 - and it is computationally cheap and numerically stable.

It has been found that the simplest models and the most complex model result in different temperature fluctuations over the simulation period, but the mean value may not differ significantly. A detailed analysis shows that a larger depth typically required more complex models and a calculation with the use of simple models results in an incorrect maximum and minimum as well as mean temperature and in consequence theoretical COP, SPF estimation.

For Model 1,the mean seasonal temperature prediction at the surface $z = 0 \mathrm { ~ m ~ }$ differs only by $0 . 1 4 ^ { \circ } \mathrm { C }$ (see Table3)inreference to Model4.Thismeans that,under the conditions taken into account in this work,the air temperature and the wind speed are good representative factors for all the environmental phenomena,regardless of the type of ground (layer thickness, lithology or saturation).

In any case,the temperature for the depth $z { > } 3 0 \mathrm { m }$ is almost model independent and, with a good approximation,equalsmean annual air temperature.In order to obtain a statistically steady temperature at larger depths, a much longer computational time (about 5O years） is required.

# Acknowledgements

The paper was carried out under the Statutory Research at the Faculty of Drilling,Oil and Gas,AGH University of Science and Technology, financed from the funds of the Polish Ministry of Science and Higher Education, grant 11.11.190.555

# References

[1]Gonet,A, Sliwa,T, Stryczek,S,Sapihska-Sliwa,A, Jaszczur,M,Pajak,L,and Zlotkowski,A,2011,Methodology for the identification of potential heat of the rock mass along with technology implementation and operation of the borehole heat exchangers,ed.A.Gonet, Wydawnictwa AGH,Krakow.   
[2]O'Sullivan，M,J,Pruess,K,and Lippmann，M,2001, Stateof the art of geothermal reservoir simulation,Geothermics,30,pp.395-429.   
[3]M van Manen,S,Wallin,E,2012,Ground temperature profiles and thermal rock properties at Wairakei,New Zealand,Renewable Energy,43， pp.313-321.   
[4]Bandos,T.V, Montero A,Fernandez de Cordoba P,Urchueguia J.F,2011, Improving parameter estimates obtained from thermal response tests:effect of ambient air temperature variations,Geothermics,40,pp.136-143.   
[5]Jaszczur M, Sliwa, T, 2012 Numerical analysis of the underground water flow on the borehole heat exchangers performance,XX fluid mechanics conference,Gliwice, pp.17-20 September,   
[6]Chiasson A. D,Advances in modeling of ground-source heat pump systems, Oklahoma State University,.   
[7]Sliwa T,Rosen M.A, Jezuit Z.,2014 Use of oil boreholes in the Carpathian in geoenergetic systems:historical and conceptual review. Research Journal of Environmental Sciences, 8 (5), pp. 231-242.   
[8]Sliwa T, Gonet A.,2004, The closing wells as heat source. Acta Montanistica Slovaca,9 (3), pp.300-302. [9]Pajak L,2O01,The numerical model of freezing zone development in the ground during ground heat exchanger exploitation, PAN,Kraków,[In Polish]   
[10]Tsilingiridis G., Papakostas K.，2014, Investigating the relationship between air and ground temperature variations in shallow depths in northern Greece,Energy,73, pp.1007-1016.   
[11]Mihalakakou G, Santamouris M., O.Lewis Asimakopoulos J,D. N,1997 On the application of the energy balance equation to predict ground temperature profiles, Solar Energy, 60 Nos.3/4, pp.181-190.   
[12] Chow T.T, Long H, Mok H.Y,Li K.W,2011 Estimation of soil temperature profile in Hong Kong from climatic variables, Energy and Buildings,43,pp. 3568-3575.   
[13] Bergman T.L, Lavine A.S, Incropera F.P, Dewitt D. P, 2011,Fundamentals of Heat and Mass Transfer, John Wiley & Sons.   
[14]Swinbank W.C,1963,Long-wave radiation from clear skies,Quarterly Journal of the Royal Meteorological Society, 89, pp. 339-348.   
[15]Brodowicz,K. T. 1990, Dyakowski, Pompy ciepla,PWN, Warszawa.   
[16]Mihalakakou,G, 2005,On estimating soil surface temperature profiles,Energy Build,34, pp.251-259.   
[17]Krarti, M. Lopez-Alonzo, C. Claridge, D.E. Kreider, J.F, 1995,Analytical model to predict annual soil surface temperature variation, Journal of Solar Engeneering, 117, pp. 91-99.   
[18]Biernacka B,20o1, Semi-empirical formula for the natural ground temperature distribution in bialystok city region, Civil and Environmental Engineering,1, pp. 5-9.