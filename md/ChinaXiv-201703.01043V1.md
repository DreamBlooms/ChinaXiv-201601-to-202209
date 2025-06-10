# Performance Enhancement of a Pump Impeller Using Optimal Design Method

Seok-Yun Jeon, Chul-Kyu Kim, Sang-Moon Lee, Joon-Yong Yoon and Choon-Man Jang

Korea Institute of Civil Engineering and Building Technology, Goyang-si, Gyeonggi-do,10223, Korea \*Dep. of Mechanical Engineering,Hanyang University, Ansan, Gyeonggi-do, 15588, Korea

$\mathfrak { C }$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

This paper presents the performance evaluation of a regenerative pump to increase its effciency using optimal design method.Two design parameters which define the shape of the pump impeler,are introduced and analyzed. Pump performance is evaluated by numerical simulation and design of experiments(DOE).To analyze three-dimensional flow field in the pump,general analysis code,CFX,is used in the present work. Shear stress turbulence model is employed to estimate the eddy viscosity.Experimental apparatus with an open-loop facility is set up for measuring the pump performance. Pump performance,effciency and pressure,obtained from numerical simulationare validated by comparison with the results of experiments.Throughout the shape optimization of the pump impeller at the operating flow condition,the pump eficiency is successfully increased by 3 percent compared to the reference pump.It is noted that the pressure increase of the optimum pump is mainly caused by higher momentum force generated inside blade passage due to the optimal blade shape.Comparisons of pump internal flow on the reference and optimum pump are also investigated and discussed in detail.

# Keywords: Regenerative Pump,Efficiency, Impeller,Optimal Design, Computational Fluid Dynamics

# Introduction

Regenerative pump is capable of generating a high pressure rise at relatively low flow rates with a single impeller.[1]Multi-blades of the pump impeller generate high pressure with the rotation of the blades.With the higher head at low flow rates,compact structure[2] and stable discharge flow are other advantages of the regenerative pump.The pump has been widely used in the industrial fields including chemistry,oil industry,auto motive and aerospace.However,relativelylow efficiency[3] is still a challenge to overcome and a key issue for theregenerative turbomachinery including regenerative pump and air blower.

One-dimensional analysis models were introduced to predict the performance of a regenerative pump，and were limited in expressing the complex flow-field and fluidic phenomenon.[4] Quail et al.[5] found a novel series of design process for regenerative pump using oneand three-dimensional analysis. Song et al.[6] suggested a theoretical model that capable of explaining the changes in spiral velocity caused by variation of the channel area of regenerative pump. Yoo et al.[1] developed a mathematical model on the basis of conventional momentum exchange theory to analyze a regenerative turbomachinery.

With analytical and theoretical achievements,experimental and numerical studies have been carried out to improve mechanical performance of a regenerative turbomachinery. Choi et al.[7] investigated the effect of blade angle on the head and the efficiency of a regenerative pump with an inclined blade angle and radial che

Vron impellers experimentally. On the other hand,design optimization coupled with computational fluid dynamics (CFD）is one of the method that effectively provides various practical information of turbomachinery.Lee and Kim[8] carried out the shape optimization of a stator blade in an axial compressor. Wang and Choi[9] studied parametric effects on the impeller blades and hub of a regenerative blower and optimized their blade shape to enhance the pump efficiency using two design variables.

In the present study,design of experiments combined with three-dimensional Navier-Stokes solver is introduced to determine optimal blade shape in the regenerative pump.Two design variables,upper blade height and hub height,are selected to enhance the pump performance and analyze by response surface method(RSM). Pump efficiency is selected as an objective function. Comparison of pump internal flow on the reference and optimal pump is also investigated and discussed in detail.

# Regenerative Pump and Experimental Set-up

Fig.1 shows the schematic view of the experimental set-up for measuring the pump performance.The test rig is designed by an open-loop facility having two reservoirs.

![](images/94fa08d9bd3cdf26d2bf54d3320f05e2265dc1d40bd83e2a73dd4c6be1d8851d.jpg)  
Fig.1Schematic view of an experimental apparatus

The facility mainly consists of an electronic flowmeter, a regenerative pump,an electronic pressure gauge,a flow control valve, a pump driving motor, a torque meter and a reservior.

The detailed specifications of the pump are summarized in Table 1.Pump performance obtained by experimental measurement is shown in Fig.2.The flow coefficient $( \Phi )$ and pressure rise coefficient $( \Psi )$ are defined as

$$
\Phi = { \frac { Q } { A U _ { t } } }
$$

$$
\Psi = \frac { 2 \Delta P } { \rho { U _ { t } ^ { 2 } } }
$$

where $\boldsymbol { \mathcal { Q } }$ is the volume flow rate, $\Delta P$ is the pressure rise, $U _ { t }$ is the rotor tip speed, $\rho$ is density, and $A$ is the outlet area of the pump.

Table1Specifications of a test regenerative pump   

<html><body><table><tr><td colspan="2">At operating condition</td></tr><tr><td>Flow coefficient</td><td>0.06</td></tr><tr><td>Pressure coefficient</td><td>2.32</td></tr><tr><td>Rotational speed [r/min]</td><td>3,590</td></tr><tr><td>Diameter of impeller [mm]</td><td>72.6</td></tr><tr><td>Number of impeller blades</td><td>48</td></tr></table></body></html>

![](images/7bdcfe46412c37343a6645970369e6945dc1fa096ec801c6a130ecfed5eeef5e.jpg)  
Fig.2Performance curve of the test pump

The flow and pressure coefficient of the pump at the operating condition are O.O6 and 2.32 while the rotational frequency of the impeller is $3 { , } 5 9 0 ~ \mathrm { r / m i n }$ . The outer diameter of the impeller is $7 2 . 6 ~ \mathrm { m m }$ and the number of impeller blades is48.

# Numerical Model of a Regenerative Pump

To analyze the pump performance, flow analysis code, ANSYS CFX, is employed in the present study. It solves incompressible Reynolds averaged Navier-Stokes equations(RANS) and continuity equation.

Fig.3 shows the computational domain of the regenerative pump,which consists of a pump impeller,a casing and ducts.The length of inlet and outlet ducts corresponds to 5 and 1O times their inner duct diameters, respectively. The upstream duct length of the pump is determined by consideration of fully developed flow while the duct length from the downstream of the pump is determined by considering vortical flow generated from the pump impeller. Computational domain is modeled into two parts: stationary and rotating domain of the pump.

![](images/673f6ae8b7d5ca7616a2e70fb03c58772aa0855504aec8e9d478f6a7355ff3c5.jpg)  
Fig.3Computational domain

Fig.4 shows the computational grid system. Tetrahedral elements are mainly imposed on casing.Wedge and hexahedral elements are used near the wall of the impeller and duct,respectively. The whole grid for the pump analysis consists of over 6,7Oo,OOO elements，which is determined through the grid dependency test as shown in Fig. 5.

![](images/a5a9585b6c928d15ed067650feeb056fbd83c9490ff25ce886e9f7cd4f8fcc7f.jpg)  
Fig.4Computational grid

![](images/954bc2bbc329270c12089988772e248c955eb90d43e34fc91ba0fab40725cd8d.jpg)  
Fig.5Grid dependency test

Shear stress transport(SST)model is employed as a turbulence model.For boundary conditions,atmospheric pressure is specified at the inlet and mass flow rate at the outlet.No-slip and adiabatic wall conditions are used on impeller blade and casing surfaces.Boundary plane between the impeller and casing regions is imposed frozen rotor interference.

# ShapeOptimizationofan ImpellerBlade

# Method for Shape Optimization

In the present paper, a response surface method combined with three-dimensional numerical simulation is introduced to study the performance of the regenerative pump.The objective function is defined as a primary parameter for the shape optimization at the first stage of design process.The design variables are selected for generating the shapes of pump impeller, and then experimental points are determined with the help of design of experiments.The value of the objective function at each experimental point is obtained by numerical analysis.

Finally,a response surface is determined to obtain an optimal point. The polynomial-based response surfaces are commonly employed in RSM.A response model $f$ .is assumed as a second-order polynomial,which can be written asEq. (3).

$$
f = \beta _ { 0 } + \sum _ { j = 1 } ^ { n } \beta _ { j } x _ { j } + \sum _ { j = 1 } ^ { n } \beta _ { j j } x _ { j } ^ { 2 } + \sum _ { i \neq j } \sum _ { \beta _ { i j } } \beta _ { i j } x _ { i } x _ { j }
$$

where $n$ is the number of design variables, $x$ and $\beta$ indicate the design variables and coefficients,respectively. The number of coefficients $( \beta _ { o } , \beta _ { I }$ ,etc.）is $( n { + } 1 ) { \cdot } ( n { + } 2 ) / 2$ Unknown coefficients of polynomial are obtained from a standard least-squares regression.

# Objective Function and Design Variables

To investigate the pump performance,pump efficiency is selected as objective function.Pump efficiency $( \eta )$ is defined as

$$
\eta = \frac { Q \Delta P } { T \Omega }
$$

where $T$ and $\varOmega$ are the torque and rotational speed of impeller, respectively.

To enhance the pump efficiency,the impeller blade is optimized by introducing two design variables: upper blade height $\left( \mathrm { H } _ { \mathrm { b } } \right)$ and hub height $\left( \mathrm { H } _ { \mathrm { h } } \right)$ are defined as shown in Fig.6.The hub height determines the hub shape,which guides the radial flow due to the rotation of impeller. The angle between upper blade and radial direction of blade impeller is constant angle of 6 degrees. The range of each variable is determined through the preliminary evaluation of a pump performance,and is summarized in Table 2.In the design space,the middle design values of each design variable are those of the reference pump.Even interval is taken for analyzing the effect of design variables on the objective function.

![](images/02701b651ec52e101bcf58bbe2ffecf9062ce7eb465a61934bddf8a7d33d8c9a.jpg)  
Fig.6Definition of design variables

Table 2Design space of variables   

<html><body><table><tr><td>Variables</td><td>Lower Bound</td><td>Middle</td><td>Upper Bound</td></tr><tr><td>Hb [mm]</td><td>1.2</td><td>3.0</td><td>4.8</td></tr><tr><td>Hh [mm]</td><td>1.4</td><td>3.8</td><td>6.2</td></tr></table></body></html>

# Results and Discussion

# ValidationofNumericalSimulation

For the validation of numerical simulation, pump efficiency is compared with the experimental result respect to flow rates in Fig.7.The figure shows that the efficiencies obtained by numerical simulation relatively match well with the experiments.The computed efficiency has a maximum of 5 percent error with the experimental data at the pump operating condition. The comparison between the numerical and experimental results shows that the efficiency of the pump is simulated correctly by the present calculation. It is noted that present optimal design is performed at the pump operating condition.

![](images/c0f3bff9a6a0bd39713e9f45cf4b87e5699b4df300527bc83dde49b8c703dda6.jpg)  
Fig.7Validation of numerical model

# Shape optimization of the pump impeller

Fig.8 shows the contour plot of the predicted response surfaces for the object function of efficiency.From the response surfaces for the pump efficiency,optimal positions for each design variable can be found easily. Results of the shape optimization of the regenerative pump for the two design variables at the operating flow condition are summarized in Tables 3 and 4.

![](images/1c76ebfd7d112465a18fb3bbecaec5a2e057d6279abbf83eab497648af43ffea.jpg)  
Fig.8Response surface for pump eficiency

Table 3Predicted optimum values   

<html><body><table><tr><td>Variables</td><td>Hb</td><td>Hh</td></tr><tr><td>Optimum values [mm]</td><td>3.0</td><td>0.4</td></tr></table></body></html>

Table 4Results of optimization   

<html><body><table><tr><td>Object Function</td><td>Reference</td><td>Optimum</td><td>Increment [%]</td></tr><tr><td>Efficiency [%]</td><td>32.3</td><td>35.3</td><td>3.0</td></tr></table></body></html>

Fig.9 shows measuring planes for reference model and optimum pumps.In the figure,Plane 1 is the start position of the outlet duct while Plane 3 is a divergence throat connected to flow channel.

![](images/cab5fdef0aec02d515377c16efeb973f10003207f0981a5c29ce9cb012fa83f3.jpg)  
Fig.9Measuring planes

![](images/8037eb1b82d42774bb2e0c630b8003bc641fcb168a034b2240ec4f66e79e8a2c.jpg)  
Fig.10Velocity distributions at measuring planes (left: reference,right:optimum)

# Comparison of Internal Flow for Reference and Op timum Pumps

Fig.1O shows the velocity distribution at three measuring positions as shown in Fig. 9. The optimum pump shows relatively uniform velocity compared to the reference pump for three planes.Especially,larger velocity difference is observed at plane 3 where outlet flow from the impeller starts.It is noted that non-uniform flow at the outlet region of the pump impeller makes circulation flow,which results in low velocity region.

Fig.11 shows pressure distributions at the three measuring positions as shown in Fig.9.

As shown in the figure,relatively higher pressure is observed at the optimum pump for three planes compared to the reference ones.It is no use to say that the pressure increase for the optimum pump comes from the reduction of pressure loss.Averaged pressures on each plane of the pump are shown in Table 5.Relatively high pressure increase for the optimum pump is also obtained compared to the reference pump.

To observe the pressure rise of the optimum pump in detail, the pressure distributions along the casing wall for two pumps are compared.

Table 5Averaged pressure coefficient at three measuring planesinFig.11   

<html><body><table><tr><td>Plane No.</td><td>Reference</td><td>Optimum</td></tr><tr><td>Plane 1</td><td>2.26</td><td>2.29</td></tr><tr><td>Plane 2</td><td>2.23</td><td>2.30</td></tr><tr><td>Plane 3</td><td>2.22</td><td>2.29</td></tr></table></body></html>

亚 2.15 2.36 0O (a)plane 1 2.15 亚 2.36 180 (b) plane 2 2.15 亚 2.79 8 (c) plane 3

![](images/7b9acb28bbb3150d99b0fe6c15d4781dc5d8d6f565dc74a279fd3d5ea431081c.jpg)  
Fig.12Pressure distributions along the casing wall   
Fig.11Pressure distributions at measuring planes (left: reference,right: optimum)

The measuring positions along the casing wall from inlet to outlet are shown in Fig.12(a).Linear increase in pressure is observed for both cases along the measuring positions while the pressure of the optimum pump has a higher value after passing drainage valve compared to the reference pump.It is noted that the optimum pump has rapid recovery characteristic of pressure compared to reference one.Higher pressure increase of the optimum pump is mainly caused by higher momentum force generated inside the blade passage due to the optimal blade shape.

# Conclusions

The optimum design of the impeller blade of a regenerative pump has been performed by the response surface method and the three-dimensional Navier-Stokes analysis. Two design variables,impeller upper blade height and hub height,are introduced to investigate the pressure and efficiency at the operating flow condition.

Throughout the shape optimization process of the impeller blade,the efficiency for the optimal pump is suc cessfully increased up to 3.O percent compared to that of the reference pump at the same operating flow condition.

From the response surface plot, it is clear that hub height is more effective than upper blade height to increase pump efficiency.

Relatively uniform outlet flow from the pump impeller is observed in the optimum pump,which reduces circulation flow inside receiving chamber. Relatively higher pressure is also observed for the optimum pump at the pump outlet.It is noted that the pressure increase of the optimum pump is mainly caused by higher momentum force generated inside blade passage due to the optimal blade shape.

# Acknowledgement

This study was supported by a grant (16AUDPB0837O4-O3） from Architecture & Urban Development Research Program funded by Ministry of Land,Infrastructure and Transport of Korean government.

# References

[1]I. S. Yoo,M. R. Park,M.K. Chung: Improved momentum exchange theory for incompressible regenerative turbomachines,Proc.Inst.Mech.Eng.Part AJ.Power Energy,vol.219,pp.567-581,(2005).   
[2]M.Raheel,A.Engeda:Systematic design approach for radial blade regenerative turbomachines,J.Propul.Power, vol.21,(2005).   
[3]T.Meakhail, S.O.Park:An improved theory for regenerative pump performance,Proc.Inst. Mech.Eng.Part A J.Power Energy, vol.219,pp.213-222,(2005).   
[4]A. Engeda: Flow analysis and design suggestions for regenerative flow pumps，ASME FEDSM2003-45681, Honolulu, USA(2003).   
[5]F.J. Quail, T. Scanlon and A.Baumgartner: Design study of a regenerative pump using one-dimensional and three dimensional numerical techniques,European Journal of Mechanics B/Fluids,vo.31,pp.181-187,(2012).   
[6]J.W. Song，A.Engeda and M.K.Chung:A modified theory for the flow mechanism in a regenerative flow pump,Journal of Power and Energy, vol.217,pp.311-321, (2003).   
[7]W. C. Choi,I. S. Yoo,M.R. Park and MK. Chung: Experimental study on the effect of blade angle on regenerative pump performance,Journal of Power and Energy, vol.227, pp.585-592,(2013).   
[8]S.Y.Lee and K.Y. Kim:Design optimization of axial flow compressor blades with three-dimensional NavierStokes solver,KSME International Journal, vol.14, pp.1005-1012,(2000).   
[9]C.H. Wang and C.H. Choi: Optimized design of regenerative blowers for enhanced efficiency，ASME 2010 International Mechanical Engineering Congress and Exposition,Vancouver, Canada,IMECE2O10-40600,(2010).