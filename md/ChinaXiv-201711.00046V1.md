# Conjugate Heat Transfer Investigation on the Cooling Performance of Air Cooled Turbine Blade with Thermal Barrier Coating

JI Yongbin, MA Chao, GE Bing, ZANG Shusheng

School of Mechanical and Power Engineering,Shanghai Jiaotong University, Shanghai 2O0240, China

A hot wind tunnel of annular cascade test rig is established for measuring temperature distribution on a real gas turbine blade surface with infrared camera.Besides,conjugate heat transfer numerical simulation is performed to obtain cooling eficiency distribution on both blade substrate surface and coating surface for comparison.The effect of thermal barrier coating on the overallcooling performance for blades is compared under varied mas flow rate of coolant,and spatial difference is also discussed. Results indicate that the cooling eficiencyin the leading edge and trailing edge areas ofthe blade is the lowest.The cooling performance is not onlyinfluenced by the internal cooling structures layout inside the blade but also by the flowcondition of the mainstream in the external cascade path.Thermal barrier effects of the coating vary at different regions of the blade surface,where higher internal cooling performance exists,more effective the thermal barier willbe,which means the thermal protectioneffect of coatings is remarkablein these regions.At the designed massflow ratio condition,the cooling efficiency on the pressure side varies by O.13 for the coating surface and substrate surface,while this value is 0.09 on the suction side.

# Keywords: gas turbine blade, thermal barrier coating, cooling efficiency, conjugate heat transfei

# Introduction

Specific power and thermal efficiency of gas turbines improve with the increase of turbine inlet temperature. However, current inlet temperature of turbine blades has exceeded the limit of heat-resistant alloy. At present, many methods have been adopted to guarantee the reliable and stable operation of gas turbine in high temperature environment.The most effective solution is to employ advanced blade materials as well as molding technology with better thermal performance，which is restricted by the development of the material science and manufacturing process.In this case,advanced cooling techniques become necessary and nice options to control the temperature.Besides,thermal barrier coating(TBC)

is generally applied to insulate super alloy-based blade surface from hot gas mainstream [1-5]. There have been many studies concerning the cooling performance of turbine blades of different cooling structures with or without TBC so far.

Boyle et al. [6] built up a three-blade cascade test bench and meausred the temperature distribution on the blades surface by infrared thermography at low temperature $( 8 0 ^ { \circ } \mathrm { C } )$ to reveal the influences of surface roughness onthe cooling performance. Zhang et al.[7] measured the cooling efficiency distribution on the turbine blade pressure surface with single row of film holes for different blowing ratios ranging from 1.61 to 3.02 using pressure sensitive paint (PSP) technology. Their results indicated that cooling efficiency slightly increases with the increase of blowing ratio but enhacement is not obvious. Shi et al.[8] conducted heat transfer experiments on specially designed binary cooling vanes in a threeblade hot wind tunnel test rig to study the influences of different relative parameters of coolant on mainstream (temperature ratio,pressure ratio and mass flow ratio) on the temperature as well as cooling efficiency distribution on the vane surface.Work mentioned above doesn't take the effect of solid part on heat transfer into consideration while it is proved to be significant. Dees et al. [9-12] investigated both the adiabatic and overall cooling efficiency for gas turbine vanes experimentally and numerically under various flow and geometircal parameters, from whose results the difference between adiabatic and conjugate cases can be shown. Movever, Kuo-San Ho et al.[13] simulated and predicted the substrate surface temprature of cooling blades with conjugate heat transfer (CHT） model. Results showed that numerical CHT outcome is well consistent with the experimental data, which was obtained from a full engine test with Silicon Carbide (SiC） chip measurements.Thus the previous studies on cooling performance of air-cooled blades are in premise of assuming Biot number (Bi) of experimental blade and realistic blade to be equal meaning similar heat transfer condition of the solid parts.However, There are few discussion on the coating thermal conduction and its thermal protection effects on the cooling performance. Coating is an important thermal barrier technology in cooling blades and has been widely applied currently. Therefore,clarifying the influences of thermal barrier coating on the cooling performance for blades is of great importance to more accurate prediciton of blades thermal behavior for designers.

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>C</td><td>specific heat capacity, J/ (kg:K)</td><td>T</td><td>inlet temperature of internal cooling channel, K</td></tr><tr><td>Cp</td><td>Jpecific heat capacty at constat presure,</td><td>Tn</td><td>inlet temperature of cascade, K</td></tr><tr><td></td><td>the absolute arc length from one point to leading edge on the middle section of pressure surface of</td><td>Tw</td><td>surface temperature of the blade, K</td></tr></table></body></html>

<html><body><table><tr><td></td><td>blade, mm the absolute arc length from one point to leading</td><td>Greek symbols</td></tr><tr><td>ls L</td><td>edge on the middle section of suction surface of blade, mm the relative arc length</td><td>p density, kg/m³</td></tr><tr><td>Lp</td><td>the absolute arc length from trailing edge to leading edge on the middle section of pressure</td><td>从 cooling efficiency</td></tr><tr><td>Ls</td><td>surface of blade,mm the absolute arc length from trailing edge to</td><td></td></tr><tr><td>mc</td><td>leading edge on the middle section of suction surface of blade, mm</td><td>μA area-averaged cooling efficiency</td></tr><tr><td>mh</td><td>mass flow rate of air, kg/s mass flow rate of main stream, kg/s</td><td>@ mass flow ratio v dynamic viscosity, kg/(m·s)</td></tr><tr><td>M</td><td>molar mass,kg/kmol</td><td>temperature ratio</td></tr><tr><td>P</td><td>static pressure,MPa</td><td>k heat conductivity coefficient, W/(m·K)</td></tr><tr><td>T</td><td>temperature, K</td><td>8 coating thickness</td></tr></table></body></html>

Davidson et al.[14] carried out experiments to evaluate the cooling performance of turbine blades with thermal barrier coating and different film cooling structures.They pointed out that thermal barrier coating can improve the cooling efficiency by $2 5 \%$ downstream film holes.Heat transfer characteristics of turbine blades with ceramic thermal barrier coating were computationally assessed by Kumar et al.[15] and compared with those without coating under high temperature condition. Results pointed out that ceramic thermal barrier coating can well hinder the radiation heat flux to blades made of alloy material, and which is more obvious when the mainstream temperature becomes higher. Tsipas[16] reported the thermophysical properties of plasma spraying thermal barrier coating and found that after thermal barrier coating spraying,the allowed temperature of the main flow can be significantly higher than the heat-resistant limit of blade material.Padture et al.[17] presented their work to conclude that the surface temperature of the blades with TBC experienced no significant change after the mianstream temperature was increased by $7 0 { - } 1 5 0 ^ { \circ } \mathrm { C }$

Rossette et al.[18] numerically investigated aerothermal performance of a first stage gas turbine blade with TBC as well as internal cooling configuration and summarized that a $1 0 0 { \ - } 4 0 0 \ \mu \mathrm { m }$ thick coating can reduce the blade substrate surface temperature by up to $2 0 0 ^ { \circ } \mathrm { C }$ namely TBC can be used to reduce the $36 \%$ coolant need for blade cooling with maintaining creep life of the substrate.Similarwork of Altun[19] also concluded a temperature decrease of $3 0 0 ^ { \circ } \mathrm { C }$ due to the TBC heat insulation. Antoher CFD work was performed by Sadowski et al.[20] to estimate the influence of the coating on the thermal response of a nozzle guide vane with $0 . 1 \mathrm { m m }$ thickness layer of TBC and several cylindircal cooling channels.Result shows that a $10 \%$ growth of cooling efficiency was achieved with the application of TBC.

From the literature reviewed above,it is found that few investigaions are done to evaluate cooling performance of realistic air cooled blades with complex internal cooling channels and TBC on the surface at hot gas environment. This paper used a hot wind tunnel with annular cascade test rig to measure the temperature distribution on the object blade surface with infrared camera. Besides,conjugate heat transfer CFD calculation was also conducted to obtain cooling efficiency distribution on both blade substrate surface and coating surface for comparison after the simulation was verified by the experimental resutls. The objective of the current work is to investigare the effect of thermal barrier coating on the overall cooling performance of blades by changing the amount of coolant,and spatial difference is also discussed.

![](images/a94bcb7e1911612e03b071421c44e0870b7cf2fde76bbd8a12c92d21477273ed.jpg)  
Fig.1Schematic view of the experimental system

1.The control room; 2.Centrifugal blower; 3,16.Air flow meter; 4.Combustor; 5,14.Plenum; 6,9.Thermocouples; 7. Inlet of the cascade；8.Cooled blade;10.Inlet of the internal cooling channel; 11.Electric heater；12.Voltage regulator;13.Regulating valve;15.Ball valve;17.Decompressing valve;18.Air compressor;19.Computer;20.Infrared camera;21.Outlet of the cascade.

# Experimental setup

The experimental system consists of gas supply system, cooling air system，test section and data acquisition system,shown in Fig.1.In the experiment,air supplied by $4 0 0 \mathrm { k W }$ blower and diesel as fuel are delivered into the combustor to burn sufficiently and generate high temperature gas.And then the high temperature combust gas enters into the plenum before flowing through the test section. Compressed air as coolant in the cooling system is provided by a piston air compressor, pressure reducing valve and plenum are equiped to keep steady pressure of the coolant.The regulating valve is manually adjusted to obtain the required amount of cooling air for different operation conditions.Before distributed into the blade cooling channel,cooling air is heated by an electric heater to simulate the similar temperature ratio in the real gas turbine applications.

The experimental blade is a real air-cooled gas turbine blade with two primary cooling passage chambers inside of it. The blade adopted latticework cooling mode with different convective heat transfer enhancement structures, depicted as Fig.2,among which the front cooling chamber occupying $28 \%$ internal cooling region is a normal U-shape convenctive cooling channel and the rear cooling chamber taking up $2 8 \% - 8 0 \%$ region of the internal cooling camber is a latticework cooling channel with various dimple vortex generators. Specific to these two major cooling structures in this blade,Rao et al.[21] carried out mechanism adiabatic heat transfer experimental study and detailed structure configuration can be referred to no film cooling is designed for this blade,so the cooling air flows into the cooling chamber from the root and finally ejects from trailing edge slots.Besides,thewhole blade is covered with the thermal barrier coating.

From the view of the mid-span plane, flow inlet and outlet of this turbine blade are $4 9 . 5 ^ { \circ }$ and $2 0 . 1 ^ { \circ }$ ，respectively,and the blade spacing is $4 1 \mathrm { m m }$ .A 7-blades annular cascade test section is built up in the experiment, shown as Fig.3.The direction of tunnel axis is consistent with the direction of inflow in the cascade to guarantee the air

![](images/bf9bc89f735fe8676cea438596b2fdfc610b909f862e0fde7489b0b77c81b44b.jpg)  
Fig.2Schematic view of the cooling configuration

![](images/d9fb29a00e8f24103a98cae90f937db87e8d4d5f112b8e568a51ba5d5ac78c6c.jpg)  
Fig.3Schematic drawing of the test section flow attack angle of blade is $0 ^ { \circ }$ . The cooling air system onlyassembled for the middle blade of7bladeswhile the others are not cooled.

The temperature distribution on the external surface of blade is measured bya VarioTHERM I infrared (IR) camera,which is operated at wavelength from 1.8 to 5.0 micrometer. The camera has a focal plane detector array of $2 5 6 \times 2 5 6$ platinum silicide detectors,with the measuring range of $2 6 8 - 1 4 7 3 \mathrm { K }$ and the measuring accuracy of $12 \%$ . The view angle is $1 4 ^ { \circ } \times 1 4 ^ { \circ }$ ，and the spatial resolution is 1.0 mrad.Besides, two thermocouples are installed at the inlets of cascade and internal cooling channel to measure the inlet temperature of the hot gas and cooling air. Temperature uncertainties obtained by IR camera and thermocouples are $\pm 0 . 1 \mathrm { K }$ and $\pm 0 . 5 \mathrm { K }$ ，respectively.

Due to the optical view restriction, not the whole blade suction surface can be pictured by the IR camera.To detect region on the suction surface as large as possible, two optical windows are laid out in the front and back location of the test section cascade (See in Fig.3). In this way infrared camera can measure the temperature distribution in the region of O-O.26 and 0.42-O.95 arc length of blade suction surface.Auxiliary experiments for calibration of infrared camera are conducted respectively to obtain the calibration curves of the two view spots. Aftercalibartion,infrared temperature field can be translated into the real temperature field.

The experimental working conditions are determined referring to the actual operation conditions of the turbine in terms of mass flow ratio $\omega$ and temperature ratio $\lambda$ In the experiment,the mass flow rates of air and fuel for combustion， inflow temperature of gas (733K） and temperature ratio（ $\lambda = 0 . 5 3 )$ all remain settled.The effect of mass flow ratio ( $\mathit { \Omega } ^ { \prime } \omega = 0 . 0 1 6 - 0 . 0 3 6 )$ on the cooling effciency $\mu$ is investigated by changing cooling air mass flow rate.

# Data reduction and uncertainty analysis

# Datareduction

The local and averaged cooling efficiency are defined as following:

$$
\mu = \frac { T _ { h } - T _ { w } } { T _ { h } - T _ { c } }
$$

$$
\mu _ { A } = \int _ { A } \mu
$$

The mass flow ratio and temperature ratio are calculated based on the equations below:

$$
\begin{array} { c } { \omega { = } \displaystyle \frac { m _ { c } } { m _ { h } } } \\ { \lambda { = } \displaystyle \frac { T _ { c } } { T _ { h } } } \end{array}
$$

And the relative arc length is described as:

$$
L = \frac { l _ { p } } { L _ { p } } \operatorname { o r } \frac { l _ { s } } { L _ { s } }
$$

# Uncertaintyanalysis

The experimental uncertainties are determined by a standard error analysis.In this experiment, the maximum measurement error of the flow rate is $\pm 2 . 0 \%$ for air,and that for temperature of the coolant and the main stream are both $\pm 0 . 5 \mathrm { K }$ . According to the standard error analysis method suggested by Kline and McClintock [22],the errors of mass flow ratio $( \omega )$ and cooling efficiency $( \mu )$ in the experimental results are,respectively, $\pm 4 . 0 \%$ and $\pm 2 . 3 \%$ ：

# Numerical modeling

Because of the experimental view limitations,flow details as well as surface temperature data on the blade pressure side can not be acquired.Besides, surface where temperature imaged by IR camera is only for the coating not the blade alloy substrate，so it’s impossible for quantifying the influence of thermal performance of the coating.For this reason,numerical simulation is implemented. Simulation object is one actual turbine blade which is tested in the experiment and its surface is covered with a thin layer of coating.

To characterize the real cooling performance of the cooling blade,it is necessary to consider the solid heat conduction effect. Thus,conjugate heat transfer numerical method is adopted.At the same time,properties parameters of the main gas flow,air,blade and coating materials under experimental conditions are predefined, like Table 1-4 shows.Gas and air are both handled as ideal gas for the atmospheric environment.In additon, thegastemperaturereaches 733K,the influence of radiation must be considered [15,23] for accuracy.Rosseland radiation model is selected in the computation. Coating in the numerical model is viewed as one thin layer material of $0 . 3 \mathrm { m m }$ uniform thickness,which is consistent with the mean thickness of the actual coating on external blade surface,and this thin material are endowed with the similar physical property of the blade coating for calculation.

Table 1 Physical properties of gas   
Table 3Physical properties of blade material.   

<html><body><table><tr><td>Parameter</td><td>Unit</td><td>Value</td></tr><tr><td>P</td><td>MPa</td><td>0.1</td></tr><tr><td>T</td><td>K</td><td>733</td></tr><tr><td>M</td><td>kg/kmol</td><td>28.76</td></tr><tr><td>Cp</td><td> J/(kg·K)</td><td>1250</td></tr><tr><td>D</td><td>kg/(m·s)</td><td>17.2E-6</td></tr><tr><td>k</td><td>W/(m·K)</td><td>0.0454</td></tr><tr><td colspan="3">Table 2 Physical properties of air.</td></tr><tr><td>Parameter</td><td>Unit</td><td>Value</td></tr><tr><td>P</td><td>MPa</td><td>0.1</td></tr><tr><td>T</td><td>K</td><td>423</td></tr><tr><td>M</td><td>kg/kmol</td><td>29</td></tr><tr><td>Cp</td><td>J/(kg·K)</td><td>1026</td></tr><tr><td>D</td><td>kg/(m-s)</td><td>23.7E-6</td></tr><tr><td>k</td><td>W/(m·K)</td><td>0.0349</td></tr></table></body></html>

<html><body><table><tr><td>Parameter</td><td>Unit</td><td>Value</td></tr><tr><td>p</td><td>kg/m³</td><td>7820</td></tr><tr><td>C</td><td>J/(kg·K)</td><td>460</td></tr><tr><td>k</td><td>W/(m·K)</td><td>15</td></tr></table></body></html>

Table 4Physical properties of coating material   

<html><body><table><tr><td>Parameter</td><td>Unit</td><td>Value</td></tr><tr><td>P</td><td>kg/m³</td><td>5210</td></tr><tr><td>C</td><td>J/(kg·K)</td><td>502</td></tr><tr><td>k</td><td>W/(m·K)</td><td>1.02</td></tr></table></body></html>

ANSYS-CFX14.5 software based on finite volume method of finite element and fullyimplicit format isused to solve three-dimensional steady N-S equation and solid heat conduction equation. $k { - } \omega$ SST turbulence model is adopted for its strength in solving CHT issues,and the convergence criteria is that each item residual decreases until ${ { 1 0 } ^ { - 5 } }$ .Due to the of cascade, this study only simulated one blade and the computational domain as well as boundaries are shown in Fig.4.

Structure of the blade with latticework cooling channels is highly complex,so both fluid and solid zone are meshed with unstructured grids. Specially,5layer boundary layer grids are added in the fluid near wall region,with total number of 14 million after grid independence validation.The grid nodes on the fluid and solid interface is in one-to-one correspondence. Fig.5 shows the typical mesh in the mid-span section. The calculation working conditions are in agreement with the experiments,to wit, with mass flow ratio $\omega$ varing from 0.016 to O.036,the cooling performance on the blade substrate surface and coating surface are separately investigated.

# Result and discussion

# Validationof thenumerical model

Before analysis and discussion, the simulation results need verified.At the designed working condition (mass flow ratio $\scriptstyle { \omega = 0 . 0 2 6 }$ ，temperature ratio $\lambda { = } 0 . 5 3$ ）inthis experiment, infrared camera successfully capature the infrared temperature fields of the front and rear regions on suction surface,which can be seen in Fig.6.Fig.7a presents cooling efficiency distribution on the suction side surface,which is analyzed after the real surface temperaure was translated by IR temperature with calibration correlation. And what Fig.7b shows is the numerical simulation results at the same working condition.

![](images/baf9b16842e12490f81a7411218e01e2ba66d73240ca317eb7c1db5381d653fd.jpg)  
Fig.4Mesh topology and boundary conditions

![](images/e428afdb25f933b3a2bc84b511b564631dfbda7c8a8751191e56087c7656a9f4.jpg)  
Fig.5Cross sectional view of the mesh

It can be seen from the figures (Fig.7a and Fig.7b) that the numerical results of cooling effciency distribution characteristics on the suction surface is similar to the experimental results.Besides,inflow stagnation occurs at the leading edge region of the blade and the corresponding cooling efficiency here is the lowest.The cooling air enters into the blade internal channel from the bladeroot with the lowest temperature,and in the start process of passing through the channel, heat begins to be transferred frominternal blade wall to the coolant.So the maximum cooling efficiency in the front area of the suction surface occurs at this region.With the further heat transfer of cooling air with the blade,the coolant temperature increases continuously,resulting in the air cooling performance decreases rapidly. Therefore, the cooling efficiency in the suction surface front region shows an obvious decreasing trend along the spanwise direction.

The cooling efficiency in the overall rear region of the blade suction surface is promoted compared with that in the front area. This is because that the gas mainstream expands in the cascade flow path leading to temperature decrease,which in the end reduces the heat flux from the hot gas into the coating external surface.The optimum cooling efficiency on the suction rear surface occurs in the mid-chord region close to the root. However, the location of best cooling protection differs between the numerical and experimental results. The prediction of numerical calculations shows that the highest cooling efficiency area is closer to the root than that of the experiment.

![](images/22de19d94ab385d9c31400beeb7fb32ace8263c49721e58a7c7b679ab726c041.jpg)

The area-averaged cooling efficiency in the front and rear regions on the suction surface obtained from the experiment and numerical calculation is shown in Fig.8. It can be seen that for the rear part of the blade suction surface,numerical simulation shows a good agreement with the experimental results,only with a little bias for larger mass flow ratio.For the front part, the simualtion seems to overestimate the cooling efficiency but keeping the same trend as the experiment. The major reason for the numerical prediction error lies in the complex geometry of the model structure and flow structure which are difficult to accurately simulate as well as some hypothesis in the numerical simulation.For example, the numerical simulation hypothesis that the thickness and

![](images/0a01e64041719d6bebc18c5900e77817d82339a219caf4121b6cc3eef2431758.jpg)  
Fig.6IR Photos of temperature field   
Fig.7Cooling efficiency distribution on the suction surface   
Fig.8Area-averaged cooling efficiency on the suction surface

d rrelgeelre 403 。 。   
0.30   
0.25   
0.20   
Aaeeeeeeeeaa □ □   
0.15 □ □ □ 一Front area on suction surface (CFD)   
0.10 □ Front area on suction surface (Exp)   
0.05 Reararea on sunction surface (CFD) 。 Reararea on sunction surface (Exp)   
0.00   
0.0140.017 0.0200.0230.0260.0290.032 0.0350.038 Mass flow ratio w

roughness of the blade coating is uniform,while for the realistic case, the roughness of the coating is not uniform due to deposition,erosion and spallation.The fact is that trends of mass flow ratio influence on the area-averaged cooling efficiency are consistent for both simuation and experiment. Combined with the comparison of cooling efficiency distributions in Fig.7,it can be shown that this numerical model can predict the cooling efficiency characteristics of the blade and the effect of the mass flow ratio on cooling efficiency can also be accurately estimated.Thus,the numerical results are credible to some extent.

# Analysis of the cooling performance

Fig.9a and 9b respectively present the cooling efficiency distribution on the coating surface and substrate surface for both pressure side and suction side.It shows that the thermal barrier effect of the coating is very apparent,for that the cooling performance of the substrate surface is significantly better than that of the coating surface.There is a high cooling efficiency region on the coating pressure surface which is close to the blade root and cooling efficiency distribution characteristicsis similar to that on the corresponding substrate pressure surface,which means the internal heat conduction through coating wouldn't change general cooling efficiency distribution feature on the pressure side.Nevertheless, for the suction side,there is a little bit difference.Overall, two high cooling efficiency areas are identifiable on the coating surface and substrate surface,one is close to the leading eage and the other is located at the mid-chord zone. The area close to the mid-chord of the suction surface is obviously larger, while the maximum cooling efficiency is lower.Furthermore,the high cooling efficiency area on the substrate surface closing to leading edge is larger than that on the coating surface.Above comparison reveals that thermal barrier coating has significant influence on the cooling efficiency distribution characteristics on the blade suction surface.

Fig.lO depicts the cooling efficiency distribution at mid-span section of the solid domain,where the normal direction of the cooling efficiency isoline represents heat transfer direction.The denser the isolines are, the quicker heat transfer generates.It is concluded that the cooling efficiency isolines in the leading edge area is almost parallel to the blade contour and they are relatively denser，which indicates a great amount of heat flux occuring here due to the big temperature difference between the inside and outside of blade wall in this region. The heat conduction of the blade solid wall is mainly in a way of one-dimensional heat transfer within the solid blade alloy part. The cooling efficiency isolines close to the trailing edge area of the blade tends to be perpendicular to the blade contour. This may be caused by the lack of effective cooling structure near the tailing edge, leading to poor cooling performance. Heat transfer between the inner and outer surface of the blade is weak in this region and at the same time heat flux is flowing in the direction towards the blade trailing edge tip.

![](images/d9a7c7aff68f3d716781bc26106cd5c898385f9a8547b3c896b766daf621027e.jpg)  
Fig.9Cooling efficiency distribution on both pressure and suction sides

Movever, It can be clearly observed from Fig.1O that on the blade suction surface and pressure surface，the locations of the cooling efficiency peak both correspond to the front cooling chamber which is close to the leading edge area. The cooling air enters into the blade from the front cooling chamber with relatively low temperature, leading to the relatively better cooling potential. While facing the incoming stagnation flow with extremly high total temperature,it is impossible to achieve high cooling efficiency at the leading edge region. Thus,high cooling efficiency zones locate just downstream the leading edge area on both suction and pressure surfaces. At the location of cooling chamber far downstream the blade suction surface, there is another high cooling efficiency region,whose formation mechanism will be analyzed by combining the flow field in the following.

Fig.11 demonstrates the streamline and velocity magnitude distribution at mid-span section of the blade.It clearly shows that main flow attaches the blade surface contour well,no flow separation appears on both sides. The mainstream undergoes an accelerating expansion process when passing along the cascade path and its velocity reaches the maximum at the throat location. Later within a short process of diffusion, the flow speed decreases.Also the temperature countour map is presented in Fig.l2 as a correspondence with the areodynamic characteristics.As mentioned above, the mainstream flows into the passage of cascade experiencing an accelerating expansion,resulting in gradual decrease of fluid temperature.Accordingly, the main stream temperature achieves the minimum value at the throat region of the cascade. This region is exactly where high cooling efficiency happens at the rear part of the suction surface. Although after heat exchanging between the cooling air and the inner surface of hot blade metal,air owns reduced cooling capacity, the temperature of the main stream in this region decreases a lot.Therefore,another high cooling efficiency area shows up in the throat location on suction side ofblade.

![](images/33a098ecaaec2b265aab54b131ecd418a9903cab9a2819d7c430aa66c5be5bc3.jpg)  
Fig.10Cooling efficiency distribution at the mid-span section

![](images/f5d7cc737c4254e4d758d7f23f0a8b322850bb49e3c5ea6177c3af7963395094.jpg)  
Fig.11Velocity distribution and streamline at the mid-span section

![](images/c12efdf7e20a668b68791009034841c95700ec727a8fcaf4c6dd94954ec5de78.jpg)  
Fig.12Temperature distribution at the mid-span section

Fig.13 and Fig.14 show the cooling efficiency on coating and substrate(alloy) surface at mid-span section along with the normalized arc length separately. It points out that the variation of cooling air amount does not change cooling efficiency distribution characteristics on the coating and substrate surface.As cooling air amount increase, the cooling efficiency obviously enhances.

It is the truth that three-dimensional heat conduction effect in the coatinglayer makesa little difference of the cooling efficiency distribution on the substrate surface from that on the coating surface.For substrate surface, under the working condition of mass flow ratio $\scriptstyle \omega = 0 . 0 2 6$ the maximum cooling efficiency on the suction side and pressure side at mid-span section are $60 . 7 \%$ and $3 7 . 9 \%$ respectively,which are higher than those for coating surface.The enhancement of cooling efficiency for coating is the poorest at the trailing edge with only $1 . 8 \%$ improvement. The reason may be that the formation of the maximum cooling efficiency area on the pressure surface is caused by the strongest cooling effect inside the blade in this region and the heat load on the blade can be efficiently taken away by the internally flowing cooling air.In this way, the thermal barrier effect of the low heat conductivity coefficient of coating material is very significant. On the other hand, the maximum cooling efficiency on the suction surface is generated due to the decreasing temperature of the externally flowing gas in this region and its inside convective cooling performance is poorer than that at the maximum cooling efficiencylocations on the pressure surface.Thus,the thermal barrier effect of the coating at this position weakens. The trailing edge of the blade lacks effective cooling protection,so its cooling efficiency is the poorest and heat loaded on the blade alloy is difficult to be taken away by cooling air.Superalloyblade constructs heat balance with the coating layer,so the thermal barrier effect of the coating is seriously weakened.

![](images/2d4203e9a151dedcaf89ae25f8882650a378a870e109afdf3c3820b90b79c1c3.jpg)  
Fig.13Cooling efficiency distribution on the coating surface at mid-span section: $\omega$ effect

![](images/fd1fca6546a0e0cbcdd448916220448bc189c3690142e3aab230fbceae5d1d0b.jpg)  
Fig.14 Cooling efficiency distribution on the substrate surface at mid-span section: $\omega$ effect

The variations of area-averaged cooling effciency with the mass flow ratio on the pressure and suction side of both substrate and coating surfaces are shown in Fig.15.When the mass flowratio increases from O.016 to 0.036，the area-averaged cooling efficiencies of the substrate pressure surface， substrate suction surface, coating pressure surface,and coating suction surface respectivley increase by $5 2 . 3 \%$ ， $4 3 . 4 \%$ ， $4 8 . 7 \%$ and $3 2 . 9 \%$ .Due to the complex internal cooling and external fluid flow combination effect, the thermal barrier impact of the coating on the pressure surface and suction surface varies.Under the condition of the designed mass flow ratio,the cooling efficiency on the pressure side varies by 0.13 for the coating surface and metal surface,while this value is O.o9 on the suction side.

Fig.16 and Fig.17 sketch the cooling efficiency on the coating surface and substrate surface at the mid-span section at varied coating thickness $( \delta )$ in the range of $0 { - } 0 . 4 5 ~ \mathrm { m m }$ .Results indicate that with the increase of the coating thickness,cooling efficiency on the coating surface decreases while corresponding cooling efficiency on the substrate surface increase gradually. However, for different locations at mid-span section on the substrate and coating surfaces,enhancement or reduction of the cooling efficiency varies. On the coating surface,0.010 and O.oo1 cooling efficiency reduction happen at the leading edge and trailing edge respectively. In addition, the maximum cooling efficiency on the suction side reaches O.0o6 decrease,accordingly,it's 0.025 for the pressure side. On the substrate surface,cooling eficiency at these four locations get 0.052,0.007,0.038 and 0.047 enhancement.So,it can be concludedthat,thermal barrier coating performs best thermal protection at the leading edge area,while worst at the trailing edge area.

![](images/adf3a394b28144586df39159a7dabfb3da2bc52d2e3131690554ceb2e834c805.jpg)  
Fig.15Comparison of area-averaged cooling efficiency for substrate and coating surfaces

![](images/07cce2068fc1c5761ec557d7a6d11ceb7dd5b1430f4d20e6360fc73a538d3bb3.jpg)  
Fig.16Cooling efficiency distribution on the coating surface at mid-span section: $\delta$ effect

![](images/854281843a367a8eaa7e9372a5668c6c5e5e0f0035df799c4fb62ddc2987363e.jpg)  
Fig.17Cooling efficiency distribution on the substrate surface at mid-span section: $\delta$ effect

# Conclusions

The leading edge and trailing edge are the two main regions where the poorest cooling performance happens.

For the leading edge area, the cooling efficiency is mainly influenced by total temperature of the mainstream. which makes the blade temperature a little higher. Even if the internal convective cooling is intense, the cooling performance on outer surface in the leading edge region is not ideal. The cooling efficiency in the trailing edge region is low for lack of highly cooling performance structures.

Due to the accelerating expansion of main flow in the path of cascade, there is a low temperature zone near the cascade throat location. Also in the corresponding location on the suction side,there is a high cooling efficiency region.

The thermal barrier effect of the coating layer with the same thickness varies a lot at different loactions.In the area with good internal cooling effectiveness inside the blade,the thermal barrier effect of the coating is obvious while in the area lacking effective cooling structures, for example blade tailing edge area, the thermal barrier effect isweakened.

Coating can significantly improve the area-averaged cooling efficiency on the blade substrate surface compared with that on coating surface.However, its effect differs much on the suction and pressure surface.Under the designed mass flow ratio condition， the cooling efficiency on the pressure surface varies by O.13 for the coating surface and metal surface,while this value is 0.09 on the suction side.

# Acknowledgement

The research was funded by the National Natural Science Foundation of China (Funding No.51206109).

# References

[1]D. Stover,G. Pracht,H. Lehmann,et al. New Material Concepts for the Next Generation of Plasma-sprayed Thermal Barrier Coating[J]. Journal of Thermal Spray Technol0gy.2004,13(1): 76-83.   
[2]M.J.Kelly, D.E.Wolfe,J. Singh,et al.Thermal Barrier Coating Design with Increased Reflectivity and Lower Thermal Conductivity for High-Temperature Turbine Applications[J]. International Journal of Applied Ceramic Technology. 2006,3(2): 81-93.   
[3]M.Bialas.Finite Element Analysis of Stress Distribution in Thermal Barrier Coatings[J]. Surface & Coating Technolg0y.2008,202:6002-6010.   
[4]M.Seraffon,N.J.Simms,J.Sumner,et al.The Development of New Bond Coat Compositions for Thermal Barrier Coating Systems Operating under Industrial Gas Turbine Conditions[J]. Surface & Coating Technolgoy. 2011,206:1529-1537.   
[5]T. Sodowski, P. Golewski. Multidisciplinary Analysis of the Operational Temperature Increase of Turbine Blades in Combustion Engines by Application of the Ceramic ThermalBarrierCoatings(TBC)[J].Computational Materials Science. 2011,50: 1326-1335.   
[6]R.J.Boyle, C.M. Spuckler,B.L.Lucci, et al. Infrared Low-Temperature Turbine Vane Rough Surface Heat Transfer Measurements. Journal of Turbomachinery. 2001,123: 168-177.   
[7]L. Z. Zhang, J. Yin and H. K. Moon. The Effect of Compound Angle on Nozzle Pressure Side Film Cooling[C]. Proceedings of ASME Turbo Expo 2009,June 8-12, 2009, Orlando,Florida, USA, GT2009-59141.   
[8]X. J. Shi, W. Wang,J. M. Gao,et al. Experimental Investigation on Cooling Performance of Binary Cooling Gas Turbine Vane. Journal of Xi'an Jiaotong University, 2013, 47(10): 81-86.   
[9]J.E. Dees,D.G. Bogard, G. A. Ledezma, et al. Overall and Adiabatic Effectiveness Values on a Scaled Up, Simulated Gas Turbine Vane[J]. ASME Journal of Turbomachinery,2013,135(5): 051017-051017-10.   
[10]J. E.Dees,D. G. Bogard,G. A. Ledezma,et al. Experimental Measurements and Computational Predictions for an Internally Cooled Simulated Turbine Vane[J].ASME Journal of Turbomachinery，2012，134(6): 061005- 061005-9.   
[11]J.E.Dees,D.G Bogard,G. A. Ledezma, et al.Momentum and Thermal Boundary Layer Development on an Internally Cooled Turbine Vane[J]. ASME Journal of Turbomachinery, 2012,134(6): 061004-061004-11.   
[12]J.E. Dees,D.G. Bogard and R. S.Bunker. Heat Transfer Augmentation Downstream of Rows of Various Dimple Geometries on the Suction Side of a Gas Turbine Airfoil [J].ASME Journal of Turbomachinery, 2010,132(3): 031010-031010-7.   
[13]K. S.Ho,C. Urwiller, S.M. Konan, et al. Conjugate Heat Transfer Analysis for Gas Turbine Cooled Blade[C]. Proceedings of ASME Turbo Expo 2014: Turbine Technical Conference and Exposition. June 16-20,2014, Dusseldorf, Germany. GT2014-25952.   
[14]F. T. Davidson,J.E.Dees and D.G. Bogard.An Experimental Study of Thermal Barrier Coatings and Film Cooling on an Internally Cooled Simulated Turbine Vane[C]. Proceedings of ASME Turbo Expo 2011. June 6-10, 2011, Vancouver, British Columbia, Canada. GT2011-46604.   
[15]N.A. Kumar and S.R. Kale. Numerical simulation of steady state heat transfer in a ceramic-coated gas turbine blade[J].International Journal of Heat and Mass Transfer 2002,45: 4831-4845.   
[16] S. A. Tsipas. Thermophysical properties of plasma sprayed thermal barrier coatings[D]. PhD thesis. UK: Cambridge University; 2005.   
[17]N.Padture,M. Gell and Jordan EH. Thermal barrier coatings for gas turbine engine applications[J]. Science.2002, 296:280-284.   
[18] A.H. Rossette，Z.M.C,A. Demeulenaere,et al. The Effect of Start-up Cycle in Ceramic Coating used as Thermal Barrier for a Gas Turbine Bucket[J].Applied Thermal Engineering.2009,29:3056-3065.   
[19]T. Sadowski, P.Golewski. The Influence of Quantity and Distribution of Cooling Channels of Turbine Elements on Level of Stresses in the Protective Layer TBC and the Efficiency of Cooling[J]. Computational Materials Science.2012,52:293-297.   
[20]ö．Altun.Heat Transfer Analysis in the TBC Coated Exhaust Nozzle of Gas Turbines[J].Heat Transfer Research.2015,46(1):13-29.   
[21]Y. Rao and S. S. Zang.Flow and Heat Transfer Characteristics inLatticework Cooling ChannelsWithDimple Vortex Generators [J].ASME Journal of Turbomachinery, 2014,136(2):021017-021017-10.   
[22] S.J.Kline and F.A.McClintock.Describing uncertainties insingle-sample experiments,Mechanical Engineering[J], 1953,75:3-8.   
[23]L. F. Zhang, Z. X. Liu, X. C. Lian. Numerical study of 3D heat transfer for turbine blade with air cooling[J]. Journalof Aerospace Power.2007,22(8):1268-1272.