# Numerical Investigation of the Bowed Stator Effects in a Transonic Fan at Low Reynolds Number

HUANG Enliang, ZHAO Shengfeng, GONG Jianbo, LU Xingen, ZHU Junqiang

KeyLaboratoryofLight-dutyGas-turbine,Institute of Enginering Thermophysics,Chinese Academy ofSciences,Beijing,100190, China

$\copyright$ Science Press and Institute of Engineering Thermophysics, CAS and Springer-Verlag Berlin Heidelberg 2017

The performance offan stage in a smallturbofan engines is significantly affected at high-altitude low Reynolds number.In order to examine the efect of low Reynolds number on the fan stage,3D numerical simulation method was employed to analyse the performance variations and the underlying flow structure in the fan stage. For the sake of decreasing the influence of low Reynolds number,the diferent bowed stator airfoils were redesigned and the effect of the modified design was evaluated.

# Keywords: Transonic Fan; Low Reynolds Number; Bowed Stator

# Introduction

High-altitude long-endurance UAV low cruising speed and air density, coupled with the small size of the engine, resulted in a low Reynolds number in fan stage.When the Reynolds number is less than $3 . 5 { \times } 1 0 ^ { 5 }$ ，the effects of low Reynolds number on the fan stage flow field and the corresponding aerodynamic performance including the stability must be taken into account during the design process.

Considerable researches were conducted on the aspects of Reynolds number effect on axial flow compressors.Significant progress has been made to understand the flow physics of low Reynolds number effect. The Wassell correct method[1] can be used to correct the low Reynolds number effects on the fan stage.Previous researchers obtained fan performance at high-altitude by the Wassell correct method[2]. However, the Wassell correct method was semi-empirical and it was obtained by statistics in the 196Os.This method could not provide the detailedfan flowfieldandrevealtheflowmechanism of fan instability at different Reynolds numbers.More recently,as a resultof the remarkable developmentof computer technology, aerodynamic optimization methods composed of both CFD and numerical optimization algo rithms have been applied to provide better performance and to find new design concepts in the low Reynolds number regime[3-7]. Despite that, there is few research concerning the effect of Reynolds number on threedimensional fan blades,especially for transonic fans in turbofan engines.Most of the investigated fan were pre dominantly used for medium or large sized turbofan engines,and no significant issues were occurred due to the relativelyhigh Reynolds number.However,when applied to the small turbofan engines,the fan performance appears to be affected by Reynolds number effects and therefore it is worth investigating the Reynolds number effects when looking for more compact and efficient transonic fan design solutions.

This paper presents the study of the Reynolds number effect on the transonic fan performance and the underlying flow mechanism within fan stage by full threedimensional numerical simulations. Furthermore, the bowed stator was used to eliminate the low Reynolds number effect in the transonic fan.

# Fan Configuration

The rotor and stator geometries for the transonic fan stage are shown in Figure 1.The fan stage key aerodynamic and geometry parameters are given in Table 1.As shown in the figure,the blade tip bents to the suction surface side and transits smoothly by using parabolic. Three bowed stators with different axial position from the original stacking line, namely Bow5,Bow10, Bow15, are examined. The stacking line tangential distributions of different bowed stators are shown in Figure 2.

![](images/30a308d114fe2c924c314655b193b136c86a7abc70262cccdaff98da9da63328.jpg)  
Fig.1The geometry of fan stage

Table1 The aerodynamic and geometry parameters of fan   

<html><body><table><tr><td>Number ofRotor Blades</td><td>15</td></tr><tr><td>Speed</td><td>18000 r/minn</td></tr><tr><td>Mass Flow</td><td>24.6 kg/s</td></tr><tr><td>Average Pressure Ratio</td><td>1.59</td></tr><tr><td>Tip Tangential Velocity</td><td>436.4 m/s</td></tr><tr><td>Rotor Blade Tip Clearance</td><td>0.3 mm</td></tr><tr><td>Inlet Diameter</td><td>463 mm</td></tr><tr><td>Inlet Hub-tip Ratio</td><td>0.3587</td></tr><tr><td>Number of Stator Blades</td><td>44</td></tr><tr><td>Relative Tip MachNumberofRotor Blade</td><td>1.4</td></tr><tr><td>The Middle Aspect Ratio ofRotor Blade</td><td>1.178</td></tr><tr><td>Solidity of Rotor Blade Tip</td><td>1.2</td></tr><tr><td>Solidity ofRotor Blade Hub</td><td>2.12</td></tr><tr><td>The Middle Aspect Ratio of Stator Blade</td><td>2.09</td></tr><tr><td>Solidity of Stator Blade Tip</td><td>1.96</td></tr><tr><td>Solidity of Stator Blade Hub</td><td>3.59</td></tr></table></body></html>

# NumericalSimulationMethodandGrid

The flow fields of the fan stage for all cases were conducted by commercial CFD software NUMECA, where the Reynolds-averaged Navier-Stokes equations with the Spalart-Allmaras turbulence model and AGS transition model were employed[8]. The fan stage with no bowed stator was used as baseline to compare with other cases.The computation domain is shown in Figure 3.The extended inlet section axial length is greater than the bladeroot axialchord.The extendedoutlet sectionaxial length is greater than the 1.5 blade root axial chord.

The structured grids were generated by the commercial software IGG (Figure 4). O-grid was used around the blades.H-grid and I-grid were set around O-grid.Butterfly grids were set in the blade tip clearance.In order to catch the detailed flow field in the boundary layer and meet the turbulence model request, the first grid distance off the wall and scale factor were adjusted to make the $\mathrm { y + }$ smaller than 5.After a grid sensitive study,an effective grid independent solution is achieved by the grid of 0.7 million.

The boundary conditions were set as total pressure at inlet and static pressure at outlet. The specific values were specified as follows: ground condition（ $( 0 ~ \mathrm { k m } )$ ，the inlet total pressure and temperature were set as $1 0 1 3 2 5 \mathrm { P a }$ and 288K,respectively；high altitude $( 2 0 ~ \mathrm { k m } )$ ，Mach number was set as O.6,the inlet total pressure and temperature were set as $7 0 5 2 . 6 6 \mathrm { P a }$ and 232.25K,respectively The outlet average static pressure and no-slip adiabatic wall was applied.

![](images/70dcde61ca32ff4ccfc1b53a14d645ea584f1a5a06e9ce45eaa3a47215b0b2db.jpg)  
Fig.2The stacking line tangential distributions

![](images/126eb6027a2c3d4859e03f6216bb40157cd17c953f8f64d8f4506ee9a84e40e7.jpg)  
Fig.3Distribution of Computation Domain

K

# Results and Discussion

Toaddress the effectof bowed stator on the fanat low Reynolds number, the present paper examines the effects of the bowed stator on aerodynamic performance and the underlying flow physics,in terms of the total pressure ratio,stage effciency, the stator suction surface limiting streamlines and Mach number distributions of S1 and S3.

# Effect on the fan performance

Fan aerodynamic performances at ground condition (O 1 $\mathrm { { c m } \colon \mathrm { { R e } } = 1 . 1 \times 1 0 ^ { 6 } ) }$ and high-altitude ( $2 0 \mathrm { k m } \mathrm { : } \mathrm { R e } = 1 . 8 \times$ $1 0 ^ { 5 } )$ are given in Table 2.As can be seen from the table, the choke mass flow ofBow5,Bow1O is increased while the choke mass flow of Bowl5 is slightly decreased as compared with the non-bow stator case.However, the choke mass flow of Bow5，Bowl0，Bowl5 at highaltitude is reduced by $0 . 9 1 \%$ ， $1 . 1 \%$ ， $1 . 3 3 \%$ respectively than those of the ground case. The near peak efficiency of Bow5,Bowl5 is decreased by $0 . 0 3 \%$ ， $0 . 4 \%$ respectively compared to that of non-bow at ground. The near peak efficiency of Bow 1O is increased by $0 . 0 2 \%$ At high-altitude, the near peak efficiency of Bow5,Bow10, Bow15 is increased by $0 . 0 2 \%$ $0 . 3 7 \%$ $0 . 2 6 \%$ respectively At ground, the near stall pressure ratio is reduced with the increased bow.At high-altitude, the near stall pressure ratio is reduced compared to the ground case.The near stall pressure ratio at high-altitude is no longer showing a monotonically decreasing trend.The near stall pressure ratio of Bowl5 at high-altitude is the highest. Both the mass flow at ground and high-altitude near stall conditions are reduced withthe increased bow.

In summary, the fan mass flow, efficiency and pressure ratio at high-altitude are lower than the ground for all the stators because of the low Reynolds number.Different bowed designs have different effects on the fan stability margin and isentropic efficiency. The main pur pose of this section is to control the separation at the tip of stator. Therefore, the analysis below will focus on the comparison of separation flow at different bowed stator tips.

Table 2The fan aerodynamic parameters for different Re   

<html><body><table><tr><td rowspan="2"></td><td colspan="2">Block mass flow</td><td colspan="2">Near peak efficiency</td></tr><tr><td>0km</td><td>20km</td><td>0km</td><td>20km</td></tr><tr><td>Nobow</td><td>26.42</td><td>26.12</td><td>0.8975</td><td>0.8206</td></tr><tr><td>Bow5</td><td>26.44</td><td>26.20</td><td>0.8972</td><td>0.8208</td></tr><tr><td>Bow10</td><td>26.43</td><td>26.14</td><td>0.8977</td><td>0.8243</td></tr><tr><td>Bow15</td><td>26.35</td><td>26.00</td><td>0.8935</td><td>0.8232</td></tr><tr><td rowspan="3"></td><td colspan="2">Near stall</td><td colspan="2">Near stall</td></tr><tr><td colspan="2">pressure ratio 20km</td><td colspan="2">mass flow 20km</td></tr><tr><td colspan="2">0km</td><td colspan="2">0km</td></tr><tr><td>Nobow</td><td colspan="2">1.745 1.624</td><td colspan="2">22.94 23.15</td></tr><tr><td>Bow5</td><td colspan="2">1.743 1.621</td><td colspan="2">23.56 23.24</td></tr><tr><td>Bow10</td><td colspan="2">1.741 1.618</td><td colspan="2">23.46 23.08</td></tr><tr><td>Bow15</td><td colspan="2">1.735 1.647</td><td colspan="2">22.94 22.93</td></tr></table></body></html>

# Effect on the fan stator suction surface limiting streamlines

The suction surface limiting streamlines for different bowed stators are shown in Figure 5.As shown in the figure，the bowed design has greater effect on the tip streamlines at ground than at the other height.The bowed design at the stator tip results in the blade loading moves toward the leading edge and yields radial pressure gradient.This radial pressure gradient increases with the increased bow.As a result, the low momentum fluid at the top corner of stator moves to the midspan of stator blade and thus the location of separation moves to the trailing edge(as shown in Figure 5). The ability to control stator blade top separation in Bow5 is the weakest.The separations at top of stator blades at Bow10,Bowl5 disappear, but the separations appear at the $6 0 \% - 8 0 \%$ height of blade.Under the condition of high-altitude,the bowed design at the tip of stator blade also yields the radial pressure gradient. The radial pressure gradient increases with the increased bow. Separation exists along the entire blade height. The low energy fluid at the top corner of stator blade driven by the pressure gradient moves to the middle of stator blade and the location of separation moves to the trailing edge.The separation at top of stator blade reduces with the increased bow and the turning point of limit streamline along the height of stator blade disappears(as shown the green circle in Figure 5).

All of the three bowed stator blades in the paper can improve the separation flow at top of the stator blade. The ability to control stator blade top separation increases with the increased bow. The bowed design only has effect on the top flow at ground. The bowed design has effect on the top and middle flow at high-altitude.

![](images/34a94b9daa3cca02abb81d928fd9771c9d78caf429a3cc3a6c7ec5dc5faacba8.jpg)  
Fig.5Distribution of suction surface limit streamlines   
Fig.6Absolute Mach number contours at stator blade outlet S3

S/1 Nobow_0km Nobow_20km W 0 Bow5_20km 0 0.5 0.5 KST Bow15_0km 0 Bow10_20km 0 MM Bow15_0km Bow15_20km

# EffectontheMadistributionofS3

The above analysis reveal the mechanism of the separation mitigating at top corner of stator blade by bowed design. The flow improvement in the boundary layer will have direct effect on the flow in the blade passage.Absolute Mach number contours near peak efficiency at stator blade outlet are shown in Figure 6.The bowed design eliminates the separation flow above $80 \%$ stator blade height. All of the three bowed designs make the separation zone disappear at ground. The larger separation zone exists at top of non-bow blade at high-altitude. The stators of Bow5,Bowl0 designs caused the separation zone significantly reduced, whilst the Bowl5 design removed the separation zone.

# Effect on the Mach number distribution of S1

The blade to blade absolute Mach number contours at $9 5 \%$ span near peak efficiency are shown in Figure 7. As shown in the figure,the bowed design reduces the separation at stator suction surface. The separation zone reduces as the bow increases. The ability to control separation of Bow5,Bow10,Bowl5 hasa slight difference at ground. The ability to control separation increases as the bow increasesathigh-altitude.

Insummary, the bowed design at the tip of stator blade changes the distribution of the stator blade load and yields radial pressure gradient. The low energy fluid at the top corner of stator blade driven by the pressure gradient moves to the middle of stator blade to provide improvement of the separation flow. The designers need to select reasonable bow in accordance with actual situation The effects on fan performance and flow field ofBow5, Bow10,Bow15 have a tiny difference at ground. However,Bowl5shows superior performance at highaltitude.

![](images/f6bb0896d614897232ce85a230af2b2762f219ae26cc3c60203472109e01f5cd.jpg)  
Fig.7Distribution of Ma of S1

# Conclusions

This paper presented a computational investigation of the flow fields in a transonic fan stage with different bowed stators,aiming at understanding of the underlying flow physics at low Reynolds number. Particular emphasis Was placed on the influence of different bowed stators on the overall aerodynamic performance and flow field of the transonic fan stage.The following conclusions are drawn.

(1) The aerodynamic performance of the fan stage,in cluding the efficiency and stability margin,were significantly reduced as the Reynolds number decreasing.

(2)The bowed stator improved the fan performance compared to the baseline stator, especially at highaltitude low Reynolds number. This was because the bowed stator could eliminate the separation at top corner of the stator.

(3) At the stator tip region, the bowed design changed the distribution of the stator loading，yielded the radial pressure gradient. The low momentum fluid at the top corner of stator mitigated toward the middle of stator driven by the radial pressure gradient, resulted in reduction of the separation flow.

# References

[1]Wassell A B.Reynolds Number Effects in Axial Compressors[J].ASME Journal of Engineering for Power, 1968,pp.149-156.   
[2] Wang Jin, Luo Guangqi, Tao Zengyuan. Effects of Reynolds Number on Compressor Performance and Engine Stability. Journal of Aerospace Power, 2003,18(1): 20-23.   
[3] Sonoda T,Yamaguti Y,Arima T,etal.Advanced High Turning Compressor Airfoils forLow Reynolds Number Condition，Part 1:Design and Optimization，ASME Journal of Turbomachinery,2004,126(3):350-359.   
[4] Schreiber H A,Steinert W,Sonoda T,et al.Advanced High Turning Compressor Airfoils for Low Reynolds Number Condition,Part 2:Experimental and Numerical Analysis,ASME Journal of Turbomachinery，2004, 126(4): 482-492.   
[5] Sonoda T,Schreiber HA.Aerodynamic Characteristics of Supercritical Outlet Guide Vanes atLow Reynolds Number Conditions,ASME Journal of Turbomachinery, 2007, 129(4): 694-704.   
[6]Endicott G, Sonoda T,Olhofer M,et al. Aerodynamic Improvement of A Transonic Fan Outlet Guide Vane Using3D Design Optimization， 2011，ASME Paper GT2011-46363.   
[7]Sonoda T,Arima T,Endicot $\mathbf { G }$ et al.A New Aerodynamic Design Concept for Transonic Swept Fan Outlet Guide Vanes,2011,ISABE-2011-1224.   
[8] Zeng Lingjun,Ma Qianli. The Simulation of the Reynolds Number Effects On the Characteristic of the Compressor, 2008,50(5): 325-327.