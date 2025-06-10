# Theoretical and Computational Analyses of LNG Evaporator

Palani Kumar Chidambaram, Yang Myung Jo\*, Heuy Dong Kim

FMTRC, Daejoo Machinery Co Ltd,149, Seongseodong-ro, Dalseo-Gu, Daegu 42721, Korea Department Mechanical Engineering, Andong National University，1375, Gyeongdong-ro,Andong-si, Gyeongsangbuk-do 760-749, Korea

$\circledcirc$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

Theoretical and numerical analysis on the fluid flow and heat transfer inside a LNG evaporator is conducted in this work.Methane is used instead of LNG as the operating fluid.This is because; methane constitutes over $80 \%$ of natural gas.The analytical calculations are performed using simple mass and energy balance equations.The analytical calculations are made to assess the pressure and temperature variations in the steam tube.Multiphase numerical simulations are performed by solving the governing equations (basic flow equations of continuity, momentum and energy equations) in a portion of the evaporator domain consisting of a single steam pipe.The flow equations are solved along with equations of species transport. Multiphase modeling is incorporated using VOF method. Liquid methane is the primary phase. It vaporizes into the secondary phase gaseous methane. Steam is another secondary phase which flows through the heating coils.Turbulence is modeled by atwo equation turbulence model. Both the theoretical and numerical predictions are seen to match well with each other. Further parametric studies are planned based on the current research.

# Keywords: LNG Evaporator,Analytical Calculation, Numerical Simulation

# Introduction

LiquefiedNatural Gas,abbreviated asLNG is natural gas that is liquefied by refrigeration at its source.It is then usually transported via road or sea inlarge containers.LNG vaporizers are typically used for re-gasification of this LNG before it is transferred to a natural gas transportation pipeline.The vaporizers are basically heat exchangers which transfer heat from a hot fluid to LNG. The hot fluid varies depending on the kind of vaporizers. Some of the major types of evaporators are Open Rack Vaporizers(ORV)，Submerged Combustion Vaporizers (SCV)and Intermediate Fluid Vaporizers (IFV)[1].Each kind of vaporizer has its own benefits and limitations. The plant-specific selection of a vaporizer is made based upon several factors which include site location,availa bility of reliable heat source,environmental permissions and restrictions,demand and cost. Recently,a large number of LNG import terminals are shifting towards warmer climate equatorial regions where the IFVs are gaining importance [1].Besides,IFVs are also superior over other vaporizers for transportable re-gasification units and waste heat recovery units [2]. Some recent investigations in the IFVs can be found in literature [2-5].

An IFV is a shell and tube type heat exchanger consisting of three prominent components: an evaporator, a condenser and a thermolator [2].The evaporator contains high pressure steam tubes that are used to heat LNG.A typical evaporator is as shown in Fig.1.LNG is fed into the evaporator through a porous media where it drips over the steam tubes.A part of heat from this super heated steam is transferred to LNG thereby vaporizing it into gaseous NG. This gasified natural gas is collected throughthe outlet tube.Usually severallayers of steam tubeslocated in the evaporator.

![](images/d2b221bdefc0c1137714007437f88adb7bb2d3fa981a749e47f7a59e2799cbb7.jpg)  
Fig.1Parts of an evaporator forLNG re-gasification

In the present work, for simplicity,only a portion of this evaporator is examined both theoretically and numerically. The analytical calculations are carried out to predict pressure and temperature variation in the steam tubes.Numerical simulations are also carried out to predict the flow field inside the evaporator.Various thermo dynamic parameters like,pressure,temperature and velocity of LNG, evaporation rate of LNG, pressure, temperature and velocity of steam in the heating tubes are monitored and studied.

Parametric studies are planned for various arrangements of the heating coils like zig-zag，spiral etc. The ongoing research work focus on optimal arrangement of coils for uniform and efficient vaporization.

In the following sections,the theoretical predictions are discussed first. This is followed by discussions on the numerical simulations.

# Theoreticalmethodofsolutionsandresults

# Pipe flow - Prediction of pressure loss

Theoretical calculations for pressure loss in the pipe can be calculated using the classical Darcy-Weisbach equation.In SI units,the pressure drop can be rewritten [6] as follows.

$$
\Delta P = \frac { f l \nu W ^ { 2 } } { D ^ { 5 } }
$$

where $f , \ l , \ \nu , \ W$ and $D$ are Darcy friction factor extracted from Moody diagram，pipe length，specific volume of steam,steam flow rate in $k g / h r$ and pipe diameter in mm.

For, pipes with bends,an equivalent length [6] can be added with the pipe length.In the present manuscript the design with zig-zag steam tube evaporator alone is discussed. The original length of the pipe is $1 0 . 6 \mathrm { ~ m ~ }$ and considering the pipe bends,the equivalent length of the pipe increases to $1 2 . 0 6 \mathrm { ~ m ~ }$ .For the steam flow rate of 6.1 $\mathrm { g / s }$ through a single pipe at $4 3 3 \mathrm { ~ K ~ }$ and 5 bar pressure through the pipe diameter of $1 2 ~ \mathrm { m m }$ ,the Reynolds number of the flow is about 48121.For this Re,the friction factor from the Moody's diagram is O.O2O2.Thus，the pressure drop calculated using the Eq.(1) is $1 1 6 5 6 . 4 \mathrm { P a }$

# Evaporator - Prediction of steam temperature drop

Then,analytical calculations in the evaporator is performed by writing a simple energy balance equation to calculate the temperature drop in the steam for a given flow rate and thermal conditions of liquid methane, steam and the gaseous methane at the outlet. The equation is as follows.

$$
Q _ { S } = Q _ { M }
$$

Here $Q _ { S }$ is the heat transferred from the steam and $Q _ { M }$ is the heat received by methane.The heat received by methane comprises of sensible heat rise of liquid methane up to its boiling point $( Q _ { L M } )$ ,latent heat of vaporization $( L _ { E V } )$ and sensible heat rise of gaseous methane $( Q _ { G M } )$ up to the required outlet temperature.

Thus,

$$
\begin{array} { c } { { Q _ { S } = Q _ { L M } + Q _ { E V } + Q _ { G M } } } \\ { { { \displaystyle T _ { o v }  } } } \\ { { \Longrightarrow \dot { m } _ { S T } \begin{array} { c } { { T _ { I N } } } \\ { { \displaystyle \int _ { T _ { o U T } } C _ { P _ { - } S T } = \dot { m } _ { L M } \displaystyle \prod _ { T _ { i N } } \left( C _ { P _ { - } L M } d T \right) } } \\ { { + \dot { m } _ { E V } L _ { E V } } } \\ { { - \dot { m } _ { G M } \displaystyle \prod _ { T _ { o u t } } \left( C _ { P _ { - } G M } d T \right) } } \end{array} } } \end{array}
$$

Here,the symbol $\dot { m }$ ， $C _ { P } , \ T$ ，and $L _ { E V }$ stand for mass flow rate,specific heat capacity, temperature and latent heat of evaporation respectively. The subscripts $S T , L M$ and $G M$ indicate the properties of steam,liquid phase methane and gas phase methane respectively. Here the properties of methane are taken from[7] and the properties of steam are taken from NIST database. The boiling point of liquid methane [8] and the latent heat of vaporization of methane at the boiling point are taken from [9].

In the above Eq.(4), the mass flow rate of steam and liquid methane are given conditions.And, the inlet temperatures of both steam $( 4 3 3 ~ \mathrm { K } )$ and liquid methane(111 K)are given.The outlet temperature of gaseous methane and the mass of evaporation of liquid methane are taken from the CFD results which will be explained in the next section on numerical methods.This is done so as to ensure that Eq.4 becomes a non-linear equation with a single unknown parameter - the outlet temperature of the steam.Fora methane flow rate of $7 2 9 \ \mathrm { g / s }$ and steam flow rate of $6 . 1 ~ \mathrm { g / s }$ and these conditions from CFD,the outlet temperature of steam is $2 8 9 ~ \mathrm { K }$ and thus the temperature drop of the steam is $1 4 4 \mathrm { K }$

# Evaporator-Predictionof heat transfer

To calculate heat transfer from the steam, the heat transfer coefficient on the inner walls of the tube is needed.This is calculated by the following Dittus-Boelter correlation for Nusselt number.

$$
N u = \frac { h _ { i n } d } { k } = 0 . 0 2 3 \mathrm { R e } ^ { 4 / 5 } \mathrm { P r } ^ { 0 . 3 }
$$

The Reynolds number (Re)inside the tube is 48300 for the given steam flow rate and pipe diameter. The Prandtl number $( \mathrm { P r } )$ is 1.03.Hence, the Nusselt number $( N u )$ for the steam flow is calculated to be 129.8.And, the steam pipe internal heat transfer coefficient $( h _ { i n } )$ that is calculated from Nusselt number is $2 8 2 . 2 9 \mathrm { W } / ( \mathrm { m } ^ { 2 } . \mathrm { K } )$

For external flow over the tube,the $N u$ is calculated by the following Churchill-Bernstein equation.

$$
{ \begin{array} { r l } & { N u _ { D } = { \frac { h _ { o u t } d } { k } } } \\ & { \qquad = 0 . 3 + { \frac { 0 . 6 2 \mathrm { R e } _ { D } ^ { 1 / 2 } \mathrm { P r } ^ { 1 / 3 } } { \left[ 1 + \left( 0 . 4 / \mathrm { P r } \right) ^ { 2 / 3 } \right] ^ { 1 / 4 } } } { \Biggl [ 1 + \left( { \frac { \mathrm { R e } _ { D } } { 2 8 2 0 0 0 } } \right) ^ { 5 / 8 } \Biggr ] } ^ { 4 / 5 } } \end{array} }
$$

In this relation, the pipe external Reynolds number $( \mathrm { R e } _ { D } )$ is calculated based upon liquid methane flow rate and pipe diameter as 82.47.The Prandtl number $( \mathrm { P r } )$ is 8.2,calculated based on liquid methane properties. Thus the Nusselt number $( N u _ { D } )$ for the liquid methane flow is calculated to be 11.35.And the external heat transfer coefficient $( h _ { o u t } )$ is $3 1 . 4 2 ~ \mathrm { W / ( m } ^ { 2 } . \mathrm { K ) }$ . With inputs given for steam average temperature and liquid methane averagetemperature,the heattransfer on both sidesof the steam tube walls can be compared to calculate average wall temperature and the heat transfer rate.

$$
Q = h _ { i n } A \left( T _ { S T } - T _ { W } \right) = h _ { o u t } A \left( T _ { W } - T _ { L M } \right)
$$

The average values of steam temperature $( T _ { S T } )$ and liquid methane temperature $( T _ { L M } )$ are used in the above equation to find the only unknown wall temperature $( T _ { W } )$ which is calculated to be $3 3 9 \mathrm { K }$ for evaporator.

# Numerical methodof solutionsandresults

# Computational domain and mesh

For simplicity in the present numerical work,as explained earlier,only one row of the coils is chosen to be studied instead of choosing the whole evaporator. The computational domain is of $1 0 5 0 ~ \mathrm { { m m } }$ in diameter,which is the model evaporator shell diameter. A heating coil of $1 2 ~ \mathrm { m m }$ in diameter and $1 0 6 0 0 \ \mathrm { m m }$ in length is located inside the evaporator. The coil is arranged in zig-zag fashion.The height of the evaporator section considered is $7 2 ~ \mathrm { m m }$ and the coil is located at 1/3rd height from the bottom.This location is selected to avoid occurrence of reverse flow in the numerical simulations.

Fig.2 present the computational domain and the mesh used in the simulations.High quality structured prismatic mesh was created inside the steam tube.An oval shaped tubular region around the coil is also created with structured mesh.The mesh was clustered towards the wall to resolve the momentum and thermal boundary layers.The smallest cell size in the wall normal direction was 0.025 mm.Unstructured tetrahedral mesh was created to cover the remaining domain.A few layers of prismatic were alsoprovided near the inletand outletboundaries ofLNG The total mesh count in the domain was approximately 1 million cells.

![](images/3461fb60d03c886ba4a3729a095d6ce8ed730e5624b5927db5cab415b76414ef.jpg)  
Fig.2Computational domain and mesh details

# Cell zone and boundary conditions

The steam pipe is modeled as the fluid zone high pressure and temperature steam.The region around this pipe is the modeled as the fluid zone for methane flow. The bottom circular face of the evaporator tank is the inlet boundary for LNG with velocity inlet boundary condition. The top circular face is the outlet boundary for LNG with pressure outlet boundary condition.For the steam pipe,mass flow inlet and pressure outlet boundary conditions are provided.LNG is assumed to comprise of liquid methane,as methane isa predominant component, over $80 \%$ in the natural gas.The boundary condition of liquid methane at the inlet are 111K $( - 1 6 2 ^ { \circ } \mathrm { C } )$ and 5.5bar gauge pressure. The boundary condition for super- heated steam at the coil inlet are $4 3 3 \mathrm { ~ K ~ }$ 0 $\mathrm { 1 6 0 ^ { \circ } C ) }$ and 5 bar gauge pressure.

# Multiphasemodel

The complex flow occurring inside the evaporator is explained as follows.Hot steam flows through the pipe while liquid methane flows over the pipe. There is no mass transfer,but thereisheattransferfromhot steam to cold liquid methane.Liquid methane absorbs this heat and then evaporates into gaseous methane.In the present numerical model this physical system is represented by a multiphase model containing three phases；steam, liquid phase methane and gas phase methane.In reality when the liquid methane vaporizes,bubbles will be formed at the steam pipe surface and get collected through the outlet pipe. The bubbles may vary on a wide range of diameters depending upon several physical parameters like surface roughness of the pipe,heat transfer rate,flow rate of steam and LNG etc.Accurate modeling of such bubbly flow requires very refined mesh throughout computational domain making it prohibitive in terms of the computational cost.

To solve this problem,an assumption is made to simplify the model that both the liquid and gas phase methane co-exist as interpenetrating media and both are continuous phases.Hence,the multiphase model needs to solve only one additional transport equation - volume fraction of the phases in addition to the original governing equations.This is achieved by the volume of fluid model (VOF model).The phase transfer between liquid and gaseous methane is achieved by the evaporationcondensation model which predicts the rate of evapora tion based on the saturation temperature of the methane.

In the following sections in this manuscript, numerical results of flow through steam pipe alone is discussed first. This result is compared with the theoretical pressure drop calculations discussed earlier. This is then followed by multiphase simulations in the evaporator.

# Numerical simulations in the steam pipe

Single phase numerical simulation was carried out initially in the pipe section alone with steam as the working fluid.The inlet flow rate of the steam was $6 . 1 ~ \mathrm { g / s }$ at 5bar and at $4 3 3 \mathrm { ~ K ~ }$ .The pressure drop contour inside the pipe for the simulationis shown below.

It is noticed that the simulated pressure drop is $1 1 4 9 0 . 5 \mathrm { P a }$ ，whereas the one predicted by the Darcy equation is $1 1 6 5 6 . 4 \mathrm { P a }$ .This iswithin $2 \%$ of the theoretical equation.Next multiphase simulations were performed in the full computational domain with heat and mass transfer between thephases.

Pressure drop (P - P_out) 1.14905e+004 1.07723e+004 1.00542e+004 9.33602e+003 8.61786e+003 7.89971e+003 7.18155e+003 6.46340e+003 5.74524e+003 5.02709e+003 4.30893e+003 3.59078e+003 2.87262e+003 2.15447e+003 1.43631e+003 7.18155e+002 0.00000e+000   
[Pa] 。

# Numerical simulationsin the evaporator

Liquid methane is supplied at a velocity of $2 \mathrm { m m / s }$ in the LNG inlet boundary that corresponds to a mass flow rate of about $7 2 9 ~ \mathrm { g / s }$ .Corresponding to the mass flow rate of $6 . 1 ~ \mathrm { g / s }$ , the inlet velocity of steam is $2 2 ~ \mathrm { m / s }$ .Inan actual evaporator, multiple layers of steam pipes are used typically to ensure large flow rate of steam through the evaporator.Whereas,in the present simulations,only one layerof pipe is used to understand the flow and thermal pattern caused by the steam pipe.

The gaseous methane volume fraction and the temperature in the evaporator at various planes are presented in Fig.4.One can note that the temperature of methane gas is higher near the periphery of the evaporator where the steam pipes bend and lower in the centre of the evaporator where the steam pipes run parallel to each other.

Fig. 5 shows the mass transfer rate contour indicating the phase transfer from liquid methane to gaseous methane.It is noticed that the phase transfer is restricted to a very small region around the steam tube.A volumetric integral of this mass transfer rate over the domain quantifies the total mass of liquid methane evaporated.For the given conditions, the simulations predicted $1 . 3 9 ~ \mathrm { g / s }$ of liquid methane evaporation and the mass averaged temperature at the exit of the evaporator was $1 1 1 . 7 \mathrm { ~ K ~ }$ Using these values in Eqs. (4) -(7),the steam temperature at the exit, the steam tube average wall temperature and the total heat transferred are calculated.As shown in Table1, the theoretical and the numerical predictions match well.

Also,gaseous methane seems to be present only along the steam pipe length. The liquid methane escaping in between the steam pipes without coming in proximity seems to be leaving the domain unaffected.This is caused by the use of only one steam pipe and the shortage of steam flow rate to heat and convert the liquid methane into gas.

The pressure and temperature of the steam in the evaporator are presented in Fig.6.It is interesting to note thatthe pressure drop hasreduced from $1 1 4 9 0 . 5 \mathrm { P a }$ in the first simulation with steam pipe alone to $1 0 3 5 6 . 3 \mathrm { P a }$ here. This is caused by the heat loss to the liquid methane.A decrease in steam temperature causes a corresponding decrease in its velocity and an increase in its density.Basic fluid mechanics states that the pressure drop varies as density and as square of velocity.Hence,the reduction in velocityisdominant than the increase in density. Therefore, the pressure drop in the steam pipe has reduced.

![](images/e13a0e924284de1abd7ba43b55ca211745f019d3bb0e87e32eeda752cc5e81f9.jpg)  
Fig.4Results of evaporator simulation

![](images/23ac8a79f4b6d9fd937dd3a0fa6db530f9c6ce410604d8fe44f8bee1f6d542f0.jpg)  
Fig.5Mass transfer rate contour around the steam tube

Table1 Comparison of theoretical and numerical predictions   

<html><body><table><tr><td></td><td>Theoretical</td><td>CFD</td></tr><tr><td>Pressure drop (Pa)</td><td>11656.4</td><td>11490</td></tr><tr><td>Exit steam temperature (K)</td><td>289</td><td>287.3</td></tr><tr><td>Total heat transferred rate (W)</td><td>1778.2</td><td>1788.9</td></tr><tr><td>Steam tube average wall tmperature (K)</td><td>339.1</td><td>339</td></tr><tr><td>Mass of methane evaporated (g/s)</td><td>1.39</td><td></td></tr><tr><td>Mass-averaged LNG outlet temperature (K)</td><td>111.7</td><td></td></tr></table></body></html>

Temperar000 428.05 9709.05 423.11 9061.78 418.16 8414.51 413.21 7767.24 408.27 7119.97 403.32 6472.70 398.37 5825.43 393.43 5178.16 388.48 4530.89 383.53 3883.62 378.59 3236.35 373.64 2589.08 368.69 1941.81 363.75 1294.54 358.80 647.27 。 353.85 0.00   
[K] 0.100 0.200 0.300 0.400 (m) [Pa] 0.100 300 0.400 (0m)

# Conclusionsandfuturedirectionsoftheresearch work

In this manuscript, the physical processes in a typical LNG evaporator are analyzed by using both analytical equations and numerical simulations.The analytical calculations made use of theoretical equations based on simplified heat and mass balance equations to predict steam pressure and temperature drop.The numerical simulations were performed on a segment of the evaporator. Based on the study the following conclusions can be made.

A multiphase numerical model can be successfully applied for the prediction of physical processes inside a LNG evaporator. Comparisons of pressure drop and temperature drop in the steam were made between both predictions and they were found to match reasonably well.

Numerical simulation with the zig-zag arrangement of steam pipe shows non-uniform vaporization occurring in the evaporator.The vaporization rate and the temperature are higher around the periphery of the evaporator due to the presence of steam pipe bends and lower in the centre where they run parallel to each other.

Ongoing research focuses on modification of steam pipe design into a spiral pattern and further parametric studies on multiple steam pipes.It will be interesting to simulate and analyze the flow pattern in the evaporator with steam tubes of various patterns.

# References

[1]Patel,D.，Mak,J.,Rivera,D.and Angtuaco,J.,2013. LNG vaporizer selection based on site ambient conditions. Proceedings of the LNG,17, pp.16-19.   
[2] Xu,S., Chen,X.and Fan,Z.,2016.Thermal design of intermediate fluid vaporizer for subcritical liquefied natural gas. Journal of Natural Gas Science and Engineering,32, pp.10-19.   
[3]Fengxia, L., Yuqiang, D.,Wei, W., Jiupeng, Z., Che, Z., Chao,D.and Dapeng,H.,2013.Feasibility of intermediate fluid vaporizer with spiral wound tubes.China Petroleum Processing & Petrochemical Technology,15(1), pp.73-77.   
[4]Pu,L., Qu, Z., Bai, Y., Qi,D., Song,K. and Yi,P., 2014. Thermal performance analysis of intermediate fluid vaporizer for liquefied natural gas.Applied thermal engineering,65(1), pp.564-574.   
[5] Xu,S.,Cheng,Q., Zhuang,L.， Tang,B., Ren,Q.and Zhang,X.,2O15.LNG vaporizers using various refrigerants as intermediate fluid: Comparison of the required heat transfer area. Journal of Natural Gas Science and Engineering,25,pp.1-9.   
[6]Menon,S.,2004.Piping calculations manual. McGraw Hill Professional.   
[7]Younglove,B.A.and Ely,J.F.，1987. Thermophysical properties of fluids. II. Methane,ethane, propane,isobutane,and normal butane.Journal ofPhysical and Chemical Reference Data,16(4),pp.577-798.   
[8]Speight, J.G.,2005.Lange's handbook of chemistry. New York:McGraw-Hill.   
[9]Hestermans,P. and White,D.,1961. The vapor pressure, heat of vaporization and heat capacity of methane from the boiling point to the critical temperature. The Journal of Physical Chemistry, 65(2), pp.362-365.

# Acknowledgement

This work was supported by a grant from $2 0 1 6 ~ \mathrm { R e } -$ search Funds of Andong National University.