# The Study on the Heat Transfer Characteristics of Oxygen Fuel Combustion Boiler

WU Haibo1,\*,LIU Zhaohui²,LIAO Haiyan

1. Shenhua Guohua Electric Power Research Institute(Bering)Co.Ltd., Beijing 10o025, China   
2.Huazhong University of Science and Technology, Wuhan 43oo74, China

According to 350MW and 600MW boilers,under oxygen fuel condition,through the reasonable control of the primary and secondary flow and the corrct option and revision of mathematical model,the temperature distribution,heat flux distribution and absorption heat distribution,etc.was obtained which compared with those under air condition.Through calculation,it is obtained that the primary and secondary flow mixed well,good tangentially fired combustion in furnace was formed,the temperature under air condition obviously higher than the temperature under O26 condition.The adiabatic flame temperature of wet cycle was slightly higher than that of dry cycle.The maximum heat load appeared on the waterwallaround the burner area.The heat load gradually decreased along the furnace height up and down in burner area.The heat absorption capacity of the furnace under O26 was lower than that under the air condition.The heat absorption capacity of the platen heating surface under O26 was equal to that under air condition. And the heat absorbing capacity of waterwall under O26 was about $7 \% { \sim } 1 2 \%$ less than that under air condition.

# Keywords:Large-scale boiler,Oxygen fuel combustion,Heattransfer characteristics,Numericalcalculation

# Introduction

China is one of the high emissions countries, it was reported that the amount of global $\mathrm { C O } _ { 2 }$ emission was up to 32.3 billion tons[1]. The amount of $\mathrm { C O } _ { 2 }$ emission of china accounts for about 1/3 of global emissions.Coal combustion is an important source of emissions.At the Durban climate conference in 2011,The Chinese government promised to accept the $\mathrm { C O } _ { 2 }$ quantitative reduction agreement after 202Os.According to IEA's report, in 2020，CCS (Carbon Capture and Storage） technology will play an important role in China's carbon emission reduction technology.Under such conditions of climate, oxygen fuel combustion technology is bounded to be the focus of future development of our country[2]. Oxygen fuel combustion is on the basis of existing power plant boiler system,with high purity oxygen instead of air for combustion,and using the flue gas recirculation control, which can get up to $9 0 \% - 9 5 \%$ volume concentration (dry basis) of $\mathrm { C O } _ { 2 }$ enrichment flue gas [3]. The technology is not only easy to recover $\mathrm { C O } _ { 2 }$ ,but also can greatly reduce $\mathrm { S O } _ { 2 }$ and $\mathrm { N O } _ { \mathrm { x } }$ emission,which is a kind ofclean and efficient coal-fired power generation technology[4,5].

The heat transfer research of large capacity oxygen fuel boiler has important significance for understanding the process of oxygen fuel and the enlargement of oxygen fuel combustion boiler. Under the condition of oxygen fuel, the gas share of the three atoms is changed greatly,and the heat capacity of the flue gas increased, and the total flue gas quantity is lower than that of the air, which may affect the process of coal combustion[6-8], Such as adiabatic flame temperature,heat transfer coefficient,furnace outlet temperature,etc.And the different $\mathrm { O } _ { 2 } / \mathrm { C O } _ { 2 }$ ratio leads to the difference of combustion characteristics.It is not accurate that we just simply copy the air heat experience to evaluate the heat transfer of oxygen fuel combustion boiler. Oxygen fuel combustion numerical simulation was conducted on the practical operation of 350MW and 6ooMWboiler in the article,through the reasonable distribution of the flow medium, the temperature distribution in the furnace,the distribution of heat load,and the distribution of energy absorption was calculated and analyzed,which has certain guiding significance on the design of oxygen fuel combustion boiler.

# General situation

# Researchobject

The 350MW boiler is the sub-critical control loop coal-fired drum boiler,with once intermediate reheat. Boiler steel frame is full suspension structure,semi-open layout,solid state slag-tap.The boiler set 16 low $\mathsf { N O } _ { \mathrm { X } }$ burners,and four corners arrangement, staged-air., tangential firing.6 pieces of front platen heating surface arranged in the upper part of furnace which belongs to radiation superheater,behind front platen superheater,it is arranged 16 pieces of rear platen superheater.

The primary flow and secondary flow almost opposed jet flow, overfire flow reverse certain angle to reduce the top of furnace flue gas residual rotation. The schematic diagram of the furnace and burner layout is shown in Fig.1.

clockwise direction,which results tangential combustion, this part of secondary flow is known as the deflection secondary flow.In contrast, the nozzle of overfire flow deflect in counterclockwise deflection,which makes the rotation strength of the flow in the upper part of the furnace reduced or even eliminated. The schematic diagram of the furnace and burner layout is shown in Fig.2.

![](images/d3b44aa3e13163cb5346b9b23ef53fc35c1516390423f66d27cfc21bcd3f3921.jpg)  
Fig.1The schematic diagram of the furnace and burners layout

600MW boiler is also sub-critical pressure once intermediate reheat, controlled circulation steam drumboiler,single furnace,II type,steel suspension structure, solid state slag-tap.The burner adopts the four corners to arrange tangential firing mode. Boiler equipped with 6 sets of medium speed mill, each mill exports through four pulverized coal pipes connected to the four corners of the furnace with a layer of pulverized coal nozzle, five sets of coal mill machine are put into use under the boiler load of MCR(Maximum Continuous Rating),the other one reserve.The burner nozzle of primary flow and secondary flow are arranged at intervals,the over-fire flow isarranged on the top of burner.

![](images/eeacac01702c669b68ba1c9dd1976b19ffa9f1cfc3094deafff80142a642872a.jpg)  
Fig.2The schematic diagram of the furnace and burners layout

6 pieces of front platen heating surface arranged in the upper part of furnace which belongs to radiation superheater,behind front platen superheater, it is arranged 25 pieces of rear platen superheater.In the layout, the primary flow almost opposed jet flow, Namely, the design of imaginary circle diameter is close to zero.Because most of the secondary flow nozzle deflect in clockwise direction, which drives the furnace gas flow to rotate in a

# Coal quality characteristics

This is coal quality characteristics, Jinjie coal washing was used.

Table1 Coal quality characteristics   

<html><body><table><tr><td colspan="2">Item</td><td>Symbol</td><td>Unit</td><td>The design coal</td></tr><tr><td rowspan="7">Industrial analysis</td><td>Total moisture</td><td>Mt</td><td>%</td><td>10.5</td></tr><tr><td>Air dry basis moisture</td><td>Mad</td><td>%</td><td>7.19</td></tr><tr><td>Received base ash</td><td>Aar</td><td>%</td><td>16.97</td></tr><tr><td>Dry and ash free radical</td><td>Vdaf</td><td>%</td><td>38.51</td></tr><tr><td>Received base high calorific value</td><td>Qgrv.ar</td><td>MJ/kg</td><td>23.19</td></tr><tr><td>Received base low heat</td><td>Qnet.yar</td><td>MJ/kg</td><td>22.21</td></tr><tr><td>Received base carbon</td><td>Car</td><td>%</td><td>58.99</td></tr><tr><td rowspan="4">Element analysis</td><td>Received base hydrogen</td><td>Har</td><td>%</td><td>3.57</td></tr><tr><td>Received base nitrogen</td><td>Nar</td><td>%</td><td>0.80</td></tr><tr><td>Received oxygen</td><td>Oar</td><td>%</td><td>8.64</td></tr><tr><td>Total sulfur</td><td>SLar</td><td>%</td><td>0.53</td></tr></table></body></html>

# Calculation method

Simulation calculation process is divided into cold state simulation and hot state simulation.Firstly,cold state simulation was conducted, through cold simulation, we not only can understand the characteristics of the flow dynamic field, providing reliable theoretical basis for the design of the burner,but also can prepare for the thermal simulation,so as to achieve the convergence of the hot state.When the cold state simulation was carried out, the influence of the combustion and the radiation and the chemical reaction was not considered, and the gas phase turbulence model and the energy model was only enabled. Hot simulation is based on the cold state simulation results.By using the model of component transport model, evaporation model, volatile and coke combustion model, and the radiation model, the distribution of temperature and heat load and the distribution of the main components in the furnace were simulated.

SIMPLE algorithm was used to solve the pressure and velocity coupling. The standard method was used to solve the pressure.The first order upwind scheme was adopted to solve the components,velocity and momentum,etc.in the first stage,then the two order upwind method was used when calculation stable.

The inlets of primary flow, secondary flow and over fire flow(OFA） used quality inlet boundary conditions, which is to ensure the quality of flow into furnace.Mass flow rate, temperature was given out according to the operating parameters.Uniform outlet boundary conditions were used. The no-slip temperature boundary condition of the furnace wall was used, the temperature was 623K, the emission rate was 0.45.

The particle diameter of pulverized coal was distributed according to Rosin-Rammler method, the minimum particle diameter was $0 . 0 0 5 \mathrm { m m }$ ,the maximum particle diameter was $0 . 2 5 \mathrm { m m }$ , the average particle diameter was $0 . 0 6 5 \mathrm { m m }$ ,and the distribution index was 1.5.

# Results and discussion

# The temperature distribution of furnace

Fig.3 and Fig.4 are section temperature distribution of second layers primary flow of furnace of 35oMW and 600MW boilers,respectively. The figures indicate that primary flow and secondary flow mixed well, the furnace can form good tangential circle combustion. we can see that after entering the furnace, the coal can stably com bust and form a stable temperature field, the high temperature area of the flame is concentrated in the central part of the furnace,and the flame has perfect performances.The shape of the flame under O26 condition (Oxygen volume concentration is about $2 6 \%$ ）isroughly consistent with that under air condition,but the peak temperature and the overall level of flue gas temperature under O26 conditionislower.

The combustion temperature under the air condition is obviously higher than that under O26.The adiabatic flame temperature under the wet condition is slightly higher than that under the dry condition.For 350MW boiler, the adiabatic flame temperature under air condition is about 1883K, the adiabatic flame temperature under O26 dry condition is about 1750K，the adiabatic flame temperature under O26 wet condition is $1 7 5 8 \mathrm { ~ K ~ }$

The adiabatic flame temperature difference is about 130K between air and oxygen fuel combustion condition.

Fig.5 and Fig. 6 are the temperature distribution of vertical section of the furnace of 350MW and 60oMWboilers,respectively.From the figures,it is obtained that the pulverized coal with the flow into the furnace can combust smoothly, the flue gas temperature rapidly increased.

In the burner region, with the increase of the height of the furnace, the high temperature region of the furnace enlarged, and the temperature distribution was more uni

1.900e+003 gna   
1.764e+003   
1.629e+003   
1.493e+003   
1.357e+003   
1.221e+003   
1.086e+003   
9.500e+002   
8.143e+002   
6.786e+002   
5.429e+002   
4.071e+002   
2.714e+002   
1.357e+002   
0.000e+000   
Air O26 dry 026 wet   
1.830e+003   
1.699e+003 ·   
1.569e+003   
1.438e+003   
1.307e+003   
1.176e+003   
1.046e+003   
9.150e+002   
7.843e+002   
6.536e+002   
5.229e+002   
3.921e+002   
2.614e+002   
1.307e+002   
0.000e+000   
Air O26 dry 026wet   
1.900e+003   
1.764e+003   
1.629e+003   
1.493e+003   
1.357e+003   
1.221e+003   
1.086e+003   
9.500e+002   
8.143e+002   
6.786e+002   
5.429e+002   
4.071e+002   
2.714e+002   
1.357e+002   
0.000e+000   
Air O26 dry O26wet

![](images/b4066d014148d2a19b0dda125fbe3a4eeca26144c0ef70a59913d5173a87edf8.jpg)  
Fig.6The temperature distribution diagram of the horizontal section of the 60oMW boiler

form.The combustion situation of the exit of burner was the most intense.We can see the combustion temperature under air condition is obviously higher than that of the oxygen fuel combustion temperature,which is consistent with the previous conclusion.

The flowing figures (Fig. 7, Fig. 8) are the temperature distribution of flue gas along the furnace height of 350MW and 60oMW boiler respectively.

![](images/cf6db36919f5c4ccfe8691a0057402cc8151ac2095d940786e04c24910ad15d5.jpg)  
Fig.7The temperature distribution of flue gas along the furnace heightof 350MW boiler

![](images/a7b642084b12765b84af35b324ca506818c7bd5f75b574b77ac40e531cb5144e.jpg)  
Fig.8The temperature distribution of flue gas along the furnace heightof 60oMWboiler

The calculation results obtained are based on mass weighted method.Under the conditions of air and oxygen fuel combustion, the height of the flame center has little change,and the maximum temperature of each working condition appears at 2O to 25 meters high. The overall combustion temperature of oxygen fuel is relatively lower than that of the air condition.The simulation results coincide with the experimental results of the 3MW test platform of Huazhong University of Science and Technology[9].

The flue gas temperature along the height of the furnace under air condition is more fiercely,and the temperature under oxygen combustion is more gently.

Under different working conditions, from Table 2 we can see the maximum temperature of combustion flame, the temperature of the bottom of the front heating platen surface and the outlet temperature of the furnace,and the temperature of the bottom of the front heating platen surface under the air condition is slightly higher than that under the oxygen fuel combustion condition,and their outlet temperature of the furnace have little difference.

Table 2The temperature contrast of different operating conditions in350MWboiler Unit:K   

<html><body><table><tr><td></td><td>Air</td><td>O26 Dry</td><td>O29 Wet</td></tr><tr><td>Flame maximum temperature</td><td>1897</td><td>1785</td><td>1801</td></tr><tr><td>the temperature under the front heating platen surface</td><td>1675</td><td>1620</td><td>1623</td></tr><tr><td>Furnace outlet temperature</td><td>1544</td><td>1425</td><td>1437</td></tr></table></body></html>

# Thedistribution of heat load

Most of the heat transfer in the furnace is radiation heat transfer, the heat load distribution of the wall of 350MW boiler was given in Fig. 9 and Fig.10.Fig.9 was the heat load distribution of back wall and right wall of the furnace.Fig.1O was the heat load distribution of front wall and left wall of the furnace.

Here simple analyze 35oMWboiler，from the figures we can see that the heat load near the burner region is higher, the heatload at the bottom and top of the furnace is the lowest. This is mainly due to the waterwall of burner region near the center of the flame which suffering from the strong radiation and the radiation effect of the bottom furnace and the top of the four corner areas was weak, this is mainly because they were away from the centre of the flame and flow turbulent intensity became lower,and ultimately it is formed that the heat load distribution of waterwall surface of burner region is much higher than other region,which causes local high load region.

The maximum heat load appears on the waterwall near the burner. Along the furnace height up and down the value gradually reduced to zero,and even the heat load of the four corners of the furnace appears positive value, the reason is analyzed,on the one hand, it reflects the heat load difference and inhomogeneity between the central of the furnace and the four corner region, on the other hand, it shows that the boundary conditions selection of wall temperature of the four corner regions is higher, and it should be cut down.

In addition, it can be seen from Fig.9 that the heat load peak value appeared on the front wall and back wall in the burner region,which is related to the flow dynamics, this may cause the slagging of the wall. From Figure 9 andFigure 1O,it can also be seen that the heat load under air condition is significantly higher than that under O26.

Fig.11 and Fig.12 are the heat load distribution of 600MWboiler wall, respectively,which is similar to the heatloaddistributionof35oMWboiler.

# The heat absorption distribution

Table 3 is the heat absorption of different heating sur facein350MWboiler.From Tab.3 it indicatesthatthe amount of heat absorption of the furnace under air condition is greater than that under oxygen condition.Because of the high share of three atomic gas,the heat absorption ability become larger，but the amount of flue gas under O26 is less than that under air condition,which may lead to weak disturbance ability of flue gas.Two factors mentioned above make the heat absorption capacity of the furnace under air condition is greater than that under oxygen fuel combustion.But for the rear platen superheater, it belongs to semi radiation and semi convection heating surface, the heat absorption of rear platen super heater under air condition and O26 is basically the same, for the front platen superheater, it belongs to the radiation heating surface,the heat absorption under O26 condition slightly larger than that under air condition.

![](images/79aabeb3e15815b4048ea3f636164671318d2b2f32667cc3d305accc3ecdc910.jpg)  
Fig.9The heat load distribution of back wall and right wall of the furnace of 35oMWboiler

![](images/322060da046bdc1ca0f04d7896fa4e96bcd567b0910dd6f4b4bb1f7b216d546e.jpg)  
Fig.10The heat load distribution of front wall and left wall

![](images/29c3ac0bd78f483e0853a0ff541fca963d2d407b793d152aaa1928fc32523599.jpg)  
Fig.11The heat load distribution of back wall and right wall of the furnace of 6ooMWboiler

![](images/c31483eabc639d091844b55377b36913957981e2f018cb8a01d063e1ea0d28c4.jpg)  
Fig.12The heat load distribution of front wall and left wall of the furnace of 6ooMWboiler

The calculation shows that the heat absorption capaci ty of the waterwall under O26 is about $7 \% - 1 2 \%$ lower than that under air condition. Therefore, to ensure the same heat power under oxygen fuel combustion as under air condition, the heating surface of furnace should appro

priately increase when conduct oxygen fuel combustion. Table 3The heat absorption of different heating surface in 350MWboilerunitMW   

<html><body><table><tr><td></td><td>Air</td><td>DRY</td><td>WET</td></tr><tr><td>Furnace total heat absorption</td><td>417</td><td>355</td><td>364</td></tr><tr><td>Furnace radiant heat</td><td>379</td><td>316</td><td>324</td></tr><tr><td>Front heat platen total heat absorption</td><td>110.5</td><td>114</td><td>115</td></tr><tr><td>Front heating platen surface radiant heat</td><td>99</td><td>102</td><td>104</td></tr><tr><td>Radiation ratio</td><td>89.5%</td><td>89.5%</td><td>90.5%</td></tr><tr><td>rear heating platen surface total heat absorption</td><td>90</td><td>90</td><td>91</td></tr><tr><td>rear heating platen surface radiation heat absorption</td><td>75</td><td>76</td><td>77</td></tr><tr><td>Radiation ratio</td><td>83.3%</td><td>84.4%</td><td>84.6%</td></tr><tr><td>Total energy absorption</td><td>617.5</td><td>559</td><td>570</td></tr></table></body></html>

# Conclusion

(1）Based on the numerical simulation model, determining the parameters of the flow distribution by calculation of flow distribution characteristics of oxygen fuel combustion boiler,according to different capacity of boiler, the combustion characteristics of the pulverized coal was studied.The result shows that the flow distribution of the primary and the secondary flow was reasonable, the coal can stably combust and form a stable temperature field, the high temperature area of the flame is concentrated in the central part of the furnace,and the flame have perfect performances.

(2) The combustion temperature under the air conditon is obviously higher than that under O26.The adiabatic flame temperature under wet conditon is slightly higher than that under dry condition.

(3) The amount of heat absorption in the furnace under air condition is greater than that under Oxygen fuel combustion.For rear platen superheater, the amount of heat absorption between air condition and O26 is basicallyequivalent.For front platen superheater, the amount ofheat absorption of O26 is slightly higher than that of air condition. The heat absorbing capacity of waterwall under O26 was about $7 \% - 1 2 \%$ less than that under air condition.

# References

[1]http://www.chinairn.com/news/20150316/150415113.sht ml.   
[2]Zheng Chuguang,Zhao Yongchun,Guo Xin. Research and Development of Oxy-fuel Combustion in China[J]. Proceedings of the CSEE,2014, 23(34): 3856-3864.   
[3] Zheng Ligang. Oxy-fuel combustion for power generation and carbon dioxide $\left( \mathrm { C O } _ { 2 } \right)$ capture[M]. Sawston,UK: Woodhead Publishing Limited, 2011.   
[4]T. Wall, Y. Liu, C. Spero., et al. An Overview on Oxy Fuel Coal Combustion-state of the Art Research and Technology Development[J]. Chemical Engineering Research and Design,2009,87(8):1003-1016.   
[5]B. J. P. Buhre,L.K. Elliott C.D. Sheng,R.P. Gupta, T. F.Wall, Oxy-fuel Combustion Technology for Coal Fired Power Generation[J]. Progress in Energy and Combustion Science,2005,31(4): 283-307.   
[6]Liu Jingzhang. Numerical optimization design and experimental study of oxygen fuel pulverized coal burner[D]. Wuhan, Huazhong University of Science and Technology, 2012.   
[7]K.Andersson,F.Johnsson.Flame and Radiation Characteristics of Gas-fired $\mathrm { O } _ { 2 } / \mathrm { C O } _ { 2 }$ Combustion[J].Fuel,2007, 86(5-6):656-668.   
[8]R.Johansson,K.Andersson,B.Leckner,H. Thunman. Models for Gaseous Radioactive Heat Transfer Applied to Oxy-fuel Conditions in Boilers[J]. International Journal ofHeat and Mass Transfer,2010,53(1-3):220-230.   
[9] Guo Junjun,Huang Xiaohong,Liu Zhaohui,et al. Numerical Simulation of Oxy-Fuel Combustion on 3 MW Coal-Fired Boiler[J].JOURNAL OF ENGINEERING THERMOPHYSICS,2014,35(5):1007-1110.