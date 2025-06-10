# Numerical Investigation of Effect of Inlet Swirl and Total-pressure Distortion on Performance and Stability of an Axial Transonic Compressor

A.Naseri, M.Boroomand, S. Sammak

Aerospace Engineering Department, Amirkabir University of Technology, Tehran, Iran

This paper represents numerical simulation offlow inside an axial transonic compressor subject to inlet flow distortion,to evaluate its effecton compressor performanceand stability.Two types of inlet distortion,namelyinlet swirl and total pressure distortion are investigated.To study the effect of combined distortion pattrns,dierent combinationsofinlet swirland total pressure distortion are also studied.Results for cases with total pressure distortion indicate that hub radial distortion improves stabilityrange of the compresor while tipradial distortion deteriorate it.An explanation for this observation is presented based onredistribution of flow parameters caused by distortion and the wayit interacts with stallinception mechanisms in a transonic axial compressor. Results also show that while co-swirl paterns slightly improve stability range of the compressor,counter-swirl patterns diminish it.Studyof combined distortion cases reveals that superimposition ofefects ofeach individual pattern could predict the effect of a combined pattrn on compressor's performance within an accuracy of $1 \%$ However, it is unable to predict the associated effect on compressor's stability.

# Keywords:AxialCompressors,Total-PressureDistortion,InletSwirl,CombinedDistortion,Performance,tability

# Introduction

Clean flow at the inlet is one of the most convenient assumptions in normal approach to compressor and fan design.It is the nominal inlet flow condition at which flow properties are assumed to be uniform and flow direction to be axial at the Aerodynamic Interface Plane (AIP).However in normal practice, the compressor is quite often faced with distorted flow at the inlet.

Inlet distortion can be divided into three main categories: total pressure, total temperature and swirl distortion. They affect compressor's performance in terms of its pressure ratio and efficiency, however, their effect on the compressor stability is normally more critical.Inlet distortion patterns redistribute flow parameters over the compressor blades which could in turn alter the stability condition of the compressor and trigger rotating stall or surge.

Total pressure distortion is defined as non-uniform distribution of total pressure at the inlet. The incoming flowmay have a radial or circumferential distribution of total pressure at the AIP. Similar definition is made for total temperature distortion [1]. Swirl distortion or flow angularity refers to non-axial flow at the inlet. Incoming flow may have both radial and circumferential compo nent of velocity at AIP, of which the latter is more important -and is considered in this study- because it directly affects the incidence angle of the rotor blade [,3]. Circumferential inlet swirl might further be categorized into two main types:1- Bulk swirl and 2- Paired swirl. Bulk swirl consists of a single vortex at the inlet, rotating either in the direction of compressor rotation (co-swirl)

or in the opposite direction (counter-swirl).Paired swirl consists of two vortices rotating in opposite directions (a co-swirl and a counter-swirl vortex). A detailed description of inlet swirl characterization may be found in Sheoran et al.[2]. This study considers radial total pressure and circumferential bulk swirl distortion patterns because of their practical prevalence.

Total pressure and swirl distortion are more common types of inlet distortion and have received more attention from researchers.Several workshave been carried out to provide better understanding of the characteristics and effects of these distortion patterns,using numerical [2-9] or experimental methods [10-14].

Sheoran et al. [2] studied performance and operability of an axial compressor under swirl distortion using 3-D flow simulations and a designed distortion generator geometry. Different types of inlet swirl including bulk-swirl, paired-swirl and offset-swirl cases are studied and shifts in compressor characteristics are reported.Results indicated that depending on type of the swirl distortion,performance and stability of the compressor might be improved or deteriorated.In particular it showed that corotating bulk swirl improves stability of the compressor while counter-rotating swirl deteriorates it. Similar results for effect of inlet swirl are reported by Fredrick et al [3] and Davis et al.[5] using 1-D parallel compressor model and by Castaneda et al.[15] using 3-D simulations.

Cameron et al. [16] conducted a numerical and experimental study of stall inception in transonic axial compressors with uniform inlet as well as with radial total-pressure distortion. Experimental measurements indicated a different spanwise distribution of axial velocity and pressure ratio caused by radial distortion pattern. The proposed tip momentum balance model has taken the redistribution of flow parameters into account to assess the effect of distortion on the stability of the compressor. Both experiments and the proposed model have shown that tip-weak radial distortion deteriorates compressor stability while hub-weak distortion improves it. Similar findings are also reported by Du et al [9].

In practice, total pressure and swirl distortion patterns usually exist simultaneously at AIP [2,3,15],although most of previous numerical works have studied their effects separately. Investigating effect of separate patterns is more convenient since it is a relatively simpler input for a compressor analysis code.On the other hand, understanding the behavior of the compressor -as a highly nonlinear system - under combined distortion patterns, seems to be of great importance.The main question is whether the flow field and the compressor's response would change significantly when distortion patterns are combined or these patterns could be studied separately and their effects could be superimposed.

This paper represents a numerical study conducted to investigate the effect of total-pressure,swirl and combined distortion patterns on the performance and stability of a transonic axial compressor. Three dimensional numerical simulations are carried out for this purpose.Bulk swirl and radial total pressure distortion patterns with different intensities are examined.Different combined distortion patterns are also studied and their effects on the compressor performance and stability are compared with those of each individual pattern.

# Geometry

This numerical study is carried out on an isolated axial-flow compressor rotor, the NASA Rotor 67.Rotor 67 isa transonic low aspect ratio design rotor,originally tested at NASA Lewis research center and reported by Strazisar[17].The main specification of NASA Rotor 67 is represented in Table 1.Fig.1 shows the geometry of the blade and the aerodynamic survey locations.

Table1 NASA Rotor 67 specification [17]   

<html><body><table><tr><td>Characteristics</td><td>Value</td></tr><tr><td>No. of blades</td><td>22</td></tr><tr><td>Design rotational speed (r/min)</td><td>16043</td></tr><tr><td>Tip speed (m/s)</td><td>429</td></tr><tr><td>Inlet tip relative Mach number</td><td>1.38</td></tr><tr><td>Design mass flow rate (kg/s)</td><td>33.25</td></tr><tr><td>Design pressure ratio</td><td>1.63</td></tr><tr><td>Design tip clearance (mm)</td><td>1.01</td></tr><tr><td>Average aspect ratio</td><td>1.56</td></tr><tr><td>Tip solidity</td><td>1.29</td></tr><tr><td>Hub solidity</td><td>3.11</td></tr><tr><td>Inlet hub/tip ratio</td><td>0.375</td></tr><tr><td>Exit hub/tip ratio</td><td>0.478</td></tr></table></body></html>

![](images/0f9ced37b73933c0f4e0746b975f56ceb0386035c6b9c0df14f2969b1b34b368.jpg)  
Fig.1blade geometry and aerodynamic survey locations [17]

# Numerical Method

Simulations are conducted by solving three dimensional steady-state compressible Navier-Stokes equations Commercially available CFD solver code,ANSYS CFX, is used to solve the governing equations. Two equation $\mathbf { k } { - } \mathbf { \mathcal { E } }$ turbulence model which is tested and verified in previous studies on the same compressor[18,19] is used also in this work.A detailed description of governing equations and the turbulence model could be found in Sammak et al. [20].

ANSYS Turbogrid software is employed for mesh generation. H-type grid topology is applied to entire domain except for a relatively thin region around the blade where O-type grid is used. The grid is sufficiently refined to meet the $\mathrm { y ^ { + } }$ requirement of the turbulence model.

Fig.2 shows the study domain of the compressor and the computational grid in blade-to-blade plane.To ensure the grid independency of the results,amesh studyis carried out using four meshes with 200K,300K,400K and 500K nodes respectively. Current mesh consists of ap proximately 3ooK nodes and is found to be a good compromise between accuracy and computational cost.

![](images/febf98a1c250f41b4fbf13bfbe2fb101da985cd1f72a71755ad6335d2ca19fe6.jpg)  
Fig.2Upper:Domain of study of the test case compressor rotor,Lower: Computational grid used for simulations.

The flow inside the compressor is assumed axisymmetric so simulations are carried out only in a single passage.Periodic boundary condition is used at domain sides to account for axisymmetry of the flow. Solid boundaries are considered non-slip,adiabatic and smooth Average static pressure is specified at the outlet boundary Inlet boundary condition is defined according to the desired inlet distortion pattern and is discussed in the following section.

Unsteady events like shock motion and vortex shedding are not modeled in this steady-state simulation and will naturally cause inaccuracy especially in the near-stall condition, where unsteady phenomena play a critical role. However, a number of previous studies involving steady state simulation of the same compressor have shown that a satisfactory accuracy is achievable even at the near-stall condition [15,18,19].

To obtain the compressor characteristics,simulations started from the choking condition and moved toward near-stall point by gradually increasing the outlet pressure.The near-stall condition is decided to be the last stable operating point prior to onset of oscillation of flow parameters.All simulations are at design rotational speed of the compressor.

# Distortion Types and Inlet Boundary Condition

Presence of distortion patterns at incoming flow is introduced into the simulations by defining appropriate boundary conditions at the domain inlet. In this work, inlet flow with total pressure distortion,swirl distortion and a combination of the two types are studied.All investigated distortion patterns are axisymmetric and thus consistent with the single-passage simulations.

Total pressure,total temperature and flow direction are parameters that are specified as inlet boundary condition. For clean inlet flow, the flow properties are set to be uniform at the inlet and equal to the values in Table 2.For each distorted flow case,total pressure and flow direction are specified in a way that characterizes the presence of the specific distortion pattern. Total temperature at the inletis identical forall cleanand distorted cases.

Table 2Specified inlet boundary condition for clean inlet flow case.   

<html><body><table><tr><td>Total pressure</td><td>Total temperature</td><td>Flow direction</td></tr><tr><td>1 atm</td><td>288K</td><td>Axial</td></tr></table></body></html>

Two radial total-pressure distortion patterns,namely tip-radial and hub-radial patterns are studied in this work. In tip-radial distortion pattern, total pressure has a radial distribution ina way that its value in the blade hub area equals to the total pressure of clean inlet but linearly decreases to a lower value at the blade tip area. In hubradial pattern, total pressure in the blade tip area is equal to clean value and the low pressure side is in the hub area. The relative amount of pressure drop in the distorted (low-pressure) side determines the Distortion Intensity:

$$
D I = \frac { P _ { 0 c } - P _ { o d } } { P _ { 0 c } } \times 1 0 0 \%
$$

where $P _ { 0 c }$ and $P _ { o d }$ refer to total pressures of clean and distorted sides respectively.

Fig.3 shows a tip-radial and a hub-radial distortion pattern with an intensity of $D I = 1 0 \%$ .Flow direction in pressure distortion cases is axial,as for the clean inlet case.

![](images/3728a744488346452b988429978e5a1f26e633d11f2dd1527ce96eaf8bb0a719.jpg)  
Fig. 3Tip and hub radial distortion patterns with $\mathrm { D I } =$ （204号 $10 \%$ ：

Bulk swirl distortion with Co- and Counter-rotating swirl flow is also investigated in this work. Total pressure boundary condition for these cases is the same as clean inlet case but incoming flow is no longer axial and has a circumferential component at the inlet. An appropriate flow direction angle is imposed at the inlet to produce the desired circumferential velocity while avoiding a radial velocity component.

Positive and negative swirl angles corresponding to co- and counter-swirl patterns are imposed at the inlet with magnitudes of 5 and 10 degrees. Swirl angle is the angle between inlet flow direction and the axis of the compressor. Note that swirl angle is constant for all radii thus uniform in whole AIP.

# Results and Discussion

This section is dedicated to presentation of the simula tion results and a discussion on the phenomena. First results for the validation tests are presented and then simulations with different distortion types.

# Model Assessment and Validation

Numerical results for clean inlet flow are used for model assessment and validation of results.Results for compressor pressure ratio and efficiency are plotted in Fig. 4 and compared against experimental data from Strazisar [17]. Numerical and experimental mass flow rates are normalized against their respective choking mass flow. Numerical results agree fairly well with the experimental data in whole mass flow range.Accuracy is slightly deteriorated near the stall point,however,it is still in a good level. Maximum error for stall total pressure ratio and mass is $4 . 6 \%$ and $0 . 7 5 \%$ respectively.

Fig.5 and 6 show distribution of relative Mach number over the compressor blade.Fig.5 shows the contours at $70 \%$ blade span, at near-stall point while Fig.6 is taken at $30 \%$ blade span and near-peak-efficiency point. Experimental data for few other span-wise locations are also provided in Ref.[17] which agree with the simulation results in the same manner and accuracy and is not presented for the sake of conciseness.

![](images/fde7e874652a58979f5b0a38923262f4ceb28bf0e8cc9d975583abbdd1d91d14.jpg)  
Fig.4Comparison of numerical results for compressor's characteristic map against experimental data

![](images/d7644c7d022360c7887750d6def60c5591da5ce4898b56ac3444347992bb5ea0.jpg)  
Fig.5Contour plot of relative Mach number at $70 \%$ blade span,near stall point: (a) numerical,(b) experimental.

![](images/3fddb7922d856b7744bf5dbe3a90a6c423af48f0680a728dd25f4cc405e05f8a.jpg)  
Fig.6Contour plot of relative Mach number at $30 \%$ blade span,near peak efficiency point: (a) numerical,(b) experimental.

Asseen in the figures,numerical results for distribution of relative Mach number is in a close agreement with the experimental data and indicates that the simulations predicted the shock structure with a very good accuracy.

# TotalPressure Distortion

Two radial distortion patterns,described earlier,with two different intensities are imposed at rotor inlet boundary and their effect on compressor characteristics is illustrated in Fig.7(upper).As seen in the figures,both distortion patterns reduce choking mass flow of the compressor and shift the characteristic map toward left side of the diagram.Fig.7(upper) indicates that hub radial distortion improves operability range of the compressor. Stall mass flow is reduced and mass flow range between stall and choking condition is widened. Stall pressure ratio is also slightly reduced.In contrast, tip radial distortion reduces operability range of the compressor. Mass flow range between choking and stall conditions is considerably reduced by increasing intensity of tip radial distortion.

Stability Margin criterion could be defined considering change in mass flow function between working line (design point) and surge line of the compressor for the same corrected rotational speed [21]. Using corrected mass flow at inlet $F$ the criterion yields to:

$$
S M = \frac { F _ { w } - F _ { s } } { F _ { w } }
$$

in which $w$ and $s$ refer to conditions on working line and surge line respectively.

Because working line cannot be defined for an isolated rotor, choking mass flow is used to define Stability Range criterion:

$$
S R = \frac { F _ { c h } - F _ { s } } { F _ { c h } }
$$

in which $c h$ refers to choking condition.This criterion measures the stable mass flow range of the compressor from choke to stall conditions. Fig. 7(lower) shows the effect of radial distortion on the compressor stability range using criterion defined in Eq.3.It indicates that hub radial distortion improves stability range of the compressor while tip radial pattern deteriorates it. To explain the effect of inlet distortion on the stability,one should take a more detailed look at flow instability and stall inception in axial compressors.

There are two distinctive stall inception routes in axial compressors and their difference is the type of initial perturbation in pressure/velocity. Long length-scale or modal inception is characterized by gradual evolution of a small amplitude disturbance. Second stalling route which is called spike type stall inception,initiates with a short length-scale disturbance that can grow into a two dimensional stall cell more rapidly than in modal incep

tion [22].

Modal inception is considered a well-known pheno menon and is described in [23,24]. Spike type stall incep tion is,however, less understood. This stalling route and its characteristics are studied in [16,22,25-27].

![](images/573177a490e61df44efb8d186bcee6f728dae7dcc05a257f9d2544757647214c.jpg)  
Fig.7Upper: Characteristic map of the compressor under hub and tip radial pressure distortion,Lower:Effect of radial pressure distortion on the stability range of the compressor.

Previous studies on stall inception of NASA Rotor 67 have indicated spike type stall inception for this compressor[19,28,29].Effect of inlet distortion on the stability can be explained based on its interaction with the spike-type stall inception mechanism.

Spike-type stall inception is primarily influenced by the tip clearance flow. Vo et al. [22] conducted a computational study to explain this stall route and based on unsteady simulation results suggested that there are two conditions necessary for this stall type and both of them are linked with tip clearance flow. First condition is that the interface between tip clearance and main incoming flow become parallel to the blade leading edge plane. Second condition is initiation of reverse flow at rotor trailing edge, stemming from fluid in adjacent passage.

Cameron et al.[16] investigated tip-leakage flow and its relationship to stall in a transonic axial compressor using both numerical and experimental methods and provided support for Vo's hypothesize.Results indicate that a very distinctive interface exists in the blade tip region where the main incoming flow meets the reverse tip-leakage flow.Location of the interface is determined from momentum balance between main incoming flow at blade tip area and reverse tip-leakage flow.As flow coefficient reduces，momentum of the incoming flow decreases.Reduction in flow coefficient also increases blade incidence angle and therefore blade load which results in an increase in tip-leakage flow. So the resulting momentum balance causes the interface to move toward the blade leading edge as flow coefficient decreases. Compressor falls into stall condition when the interface reaches the blade leading edge plane.

Radial total pressure distortion alters velocity distribu tion at the compressor inlet.Fig. 8 shows the span-wise distribution of axial velocity just upstream of the blade leading edge for clean and hub-radial distortion cases studied in this work. Axial velocities are normalized against their average value.Mass flow rate and thus average axial velocity is identical for all three cases and corresponds to the near-stall point on compressor map with cleaninlet.

As seen in Fig. 8,pressure distortion at the inlet caused a different distribution of axial velocity upstream of blade leading edge. Area with lower total pressure corresponds to area with lower axial velocity，i.el hub-radial distortion pattern results in a velocity distribution with higher values at blade tip area. Increasing the distortion intensity causes the axial velocity at blade tip to increase more.

Change in axial velocity at blade tip area modifies the momentum balance between the main incoming and secondary tip-leakage flows.Higher velocity at tip helps to push back the tip-leakage flow and move the interface toward the flow passage,i. e.away from the blade leadingedge.Thisdisplacementof the interface betweentwo flows improves the stability of the compressor. On the contrary, tip-radial distortion pattern reduces the axial velocity (thus the flow momentum） at blade tip area. Reduction in the momentum of the incoming flow causes the interface to move toward the blade leading edge which in turn deteriorates the stability of the compressor. These results are in line with the findings in [9,16].

![](images/3cb09e0990533dc6aa7cee361f7568191bf69fa39a91046c5dcd70b1548cd610.jpg)  
Fig.8Spanwise distribution of axial velocity in blade leading edgeplane for clean and distorted inlet flow

# Inlet Swirl

Four cases with bulk swirl pattern at the inlet are simulated and their effects on compressor characteristics map are discussed.Fig.9 (upper) shows the calculated characteristics of the compressor when subject to co- and counter-rotating bulk swirl with magnitudes of 5 and 10 degrees.Results show that for a constant mass flow rate, co-rotating inlet swirl decreases compressor total pressure ratio.Furthermore the stall point is moved to a lower mass flow. Although both choking and stall mass flow rates are decreased but the stable operational range of the compressor is widened.This fact is also seen in Fig.9 (lower) which shows an increase in stability range of the compressor due to co-swirl distortion.

![](images/ca97a267df501428033ac6cc9796a88690229d060e06560fb9ece168782b942f.jpg)  
Fig.9 Upper: Characteristic map of the compressor under bulk swirl,Lower:Effect of swirl distortion on the stability range of the compressor.

Counter-rotating swirl affects compressor characteristics oppositely. As illustrated in Fig.9(upper),pressure ratio is increased for a constant mass flow rate.Both choking and stall conditions are moved to a point with higher mass flow rate but stable operational range of the compressor is shrunk which means a reduction in stability range,as shown in Fig. 9(lower).

Co-swirl flow reduces the relative flow angle at the blade leading edge which in turn reduces blade load and thus pressure ratio at a constant mass flow. Moreover, decrease in relative flow angle reduces blade incidence angle which makes flow over the blade less likely to separate and thus improves the stability margin of the rotor. On the contrary, counter-swirl flow increases the relative flow angle at rotor leading edge,which results in an increase in blade load that raises the pressure ratio of the compressor. It also increases the blade incidence angle and makes the flow more likely to separate from the blade which results in loss in stability range.

Findings on effect of inlet swirl are in line with previous findings [2,3,5,15].

# Combined Distortion Patterns

Six cases with combined swirl and total-pressure distortion patterns are examined to study the effect of combined patterns on compressor performance and stability. Table 3 shows the combined cases that are investigated in this study.

Table 3Combined swirl and total pressure distortion patterns studied in thiswork   

<html><body><table><tr><td>Distortion patterns</td></tr><tr><td>5°co-swirl + 10% tip-radial</td></tr><tr><td>10° co-swirl + 10% tip-radial</td></tr><tr><td>10° counter-swirl + 10% tip-radial</td></tr><tr><td>10° co-swirl + 5% tip-radial</td></tr><tr><td>10°co-swirl + 10% hub-radial</td></tr><tr><td>10° counter-swirl + 10% hub-radial</td></tr></table></body></html>

Fig.10 shows the compressor characteristics map under combined distortion patterns.Results for cases with only one of each distortion pattern are also plotted for comparison.

A qualitative examination of results in Fig. 10 suggests that combining distortion patterns does not change the way they affect the compressor characteristics map. For instance,adding a 1O degree co- or counter-swirl flow to the inlet of a compressor which is already subject to a tip-radial distortion pattern,has a same qualitative effect as adding it to a compressor with a clean inlet, i.e. counter-swirl flow shifts the compressor map to right and upwards while co-swirl shifts it to left and downwards (Fig.10a). Same trend is seen in Fig. 1Ob for adding swirling flow to a hub-radial pressure distortion pattern at the inlet.

Fig.10c compares effect of adding tip-radial pressure distortion to a compressor with a clean inlet and another one with a 1O degree of co-swirl. Again one can see that tip radial distortion changes the two characteristics maps in a similar way,i.e.it reduces compressor choking mass flow and shrinks the operability range. Same inference can be drawn by assessing Fig.10d.

A quantitative investigation of the results,however, reveals that effects of isolated distortion patterns cannot always be simply added up to determine the effect of a combined pattern. To indicate this point three aspects of change in compressor map due to distortion are analyzed. These three criteria are change in the compressor stability range, choking mass flow and stall pressure ratio.

A criterion is defined for each aspectof change.△ SR is defined as the amount of deviation in Stability Range criterion of each case with respect to the clean inlet case (Eq. 4), $\Delta F _ { c h }$ is the normalized change of choking mass flow with respect to the clean inlet case (Eq. 5) and $\Delta \mathrm { P r } _ { s }$ is normalized change in compressor stall pressure ratio with respect to the clean inlet case (Eq. 6). Knowing these three criteria, one can relocate the compressor map for clean inlet and estimate the new map for distorted inlet cases.

$$
\Delta S R = S R - S R _ { c l e a n }
$$

$$
\Delta F _ { c h } = \frac { F _ { c h } - F _ { c h , c l e a n } } { F _ { c h , c l e a n } }
$$

$$
\Delta \mathrm { P r } _ { s } = \frac { \mathrm { P r } _ { s } - \mathrm { P r } _ { s , c l e a n } } { \mathrm { P r } _ { s , c l e a n } }
$$

Fig.11 illustrates the values of the so mentioned three criteria that are obtained by superimposition of the effects of each individual pattern. The error bars indicates the amount of error in reference to the values obtained by direct simulation of combined patterns.

Evaluation of the results in Fig.1lb and 1lc shows that values for $\Delta F _ { c h }$ and $\Delta \mathrm { P r } _ { s }$ obtained by superimposition are in a close agreement with those obtained by simulation of the associated combined patterns. The amount of error is in a very acceptable range (less than $1 \%$ for all cases.It is also interesting to note that in most of the cases, superimposition of the results slightly overestimated the effect of a combined pattern.Fig.1la on the other hand shows that values obtained by superimposition for $\Delta S R$ are significantly different than those obtained by simulation of combined patterns. The magnitude of the error is far beyond the acceptable range. It is worth to mention that superimposition again has overestimated the effect of the combined pattern. Moreover, values for $\Delta S R$ of combined patterns are somehow close to the average of the values of each individual pattern.

![](images/6d0b585fcefb53100861a04300235af87bf5fc462990537688ae86c651cf3ab0.jpg)  
Fig.10Characteristic map of the compressor under combined distortion patterns.

![](images/3493979a481bc88bd73d92f9b6ad20c5ccc62ffff0302cf0a81e2858e6cbdba3.jpg)  
Fig.IlResults foreffectofacombined distortionpattemobtainedbysuperimpositionanditsassciated error inreference tore sults obtained by simulation.

These indications suggest that although superimposition of effects of each individual pattern could predict some aspects of a combined pattern's effect on compressor performance,it cannot be used to assess the compressor stability condition.For a reliable analysis of compressor stability under a combined inlet distortion pattern,a simulation with the real, combined pattern is necessary.

# Conclusions

This study is concerned with the effect of inlet flow distortion on the performance and stability of an axial transonic compressor. Numerical simulations with radial total-pressure and circumferential swirl distortion patterns are carried out and following conclusions are drawn:

1-Co-swirl distortion shifts compressor map to the left and downward and increases stability range of the compressor.For a constant mass flow rate, it reduces pressure ratio of the compressor. On the contrary, counter-swirl distortion shifts the compressor map to the right and upward and decreases stability range of the compressor. It increases pressure ratio of the compressor for a constant mass flow rate. Change in relative flow angle (and thus the blade incidence angle) due to swirl distortion explains its effect on the compressor performance and stability.

2-Hub radial distortion improves stability range of the compressor. Both choking and stall mass flow rates are reduced and operational mass flow range of the compressor is widened.In contrast, Tip radial distortion deteriorates stability range of the compressor.

3-Radial total-pressure distortion alters span-wise distribution of axial velocity at the inlet to the rotor.Effect of this distortion pattern on stability is explained based on how this redistribution of parameters interacts with spike-type stall inception mechanism.Hub-radial distortion results in a velocity distribution with higher values at blade tip area.Higher velocity helps the incoming flow to push back the tip-leakage flow and move their interface toward the flow passage.This displacement of interface then improves stability of the compressor. On the contrary,tip-radial distortion alters the axial velocity distribution in a way that lowers the axial velocity in the blade tip area.Lower axial velocity (thus lower flow momentum) at tip area causes the interface to move toward the leading edge and thus deteriorates stability of the compressor.

4-A qualitative analysis of results for combined dis tortion patterns suggests that adding a new distorton pattern to an already existing one at the inlet,has the same qualitative effect on the compressor map shift.A quantitative analysis,however, indicates that although superimposition of effects of each individual pattern provided acceptable prediction for a combined pattern's effect on compressor performance,it is unable to predict its effect on the compressor stability.Results obtained for stability range by simulation of combined patterns are significantly different than those obtained by the superimposition.

# References

[1]SAE S-16 Committee. "ARP 1420." Revision B,”Gas Turbine Inlet Flow Distortion Guidelines,” Society of Automotive Engineers (2002).   
[2]Sheoran,Y.,B. Bouldin, and P. M. Krishnan. "Compressor Performance and Operability in Swirl Distortion." Journal of Turbomachinery 134，no.4 (2012): 041008.   
[3]Fredrick,N.,and M. Davis."Investigation of the Effects of Inlet Swirl on Compressor Performance and Operability Using a Modified Parallel Compressor Model." In ASME 2011 Turbo Expo: Turbine Technical Conference and Exposition,Vancouver, Canada, (2011).   
[4] Nie,Chaoqun，Jingxuan Zhang， Zhiting Tong，and Hongwu Zhang. "The response of a low speed compressor on rotating inlet distortion." Journal of Thermal Science 15,no.4 (2006): 314-318.   
[5]Davis,M.,and A.Hale."A parametric study on the effects of inlet swirl on compression system performance and operability using numerical simulations." In ASME Turbo Expo 2oo7: Power for Land, Sea,and Air, pp.1-10. Montreal, Canada,2007.   
[6]Khaleghi,H.，G. Doulgeris,M.Boroomand,P. Pilidis, and A.M. Tousi."A method for calculating inlet distortion effects on stability of split-flow fans."Aeronautical Journal 113,no.1147 (2009): 591-598.   
[7]Iseler, Jens,A.Lesser,and R.Niehuis."Numerical Investigation of a Transonic Axial Compressor Stage with Inlet Distortions." In High Performance Computing in Science and Engineering, Garching/Munich 2009,pp.185-195. 2010.   
[8]V. J.Fidalgo,C. Hall and Y. Colin,"A Study of FanDistortion Interaction Within the NASA Rotor 67 Transonic Stage," J Turbomach,vol. 134,no.5,p. 051011, 2012.   
[9]Du, J.,Lin,F.,Chen, J., Morris, S.C., and Nie,C., "Numerical study on the influence mechanism of inlet distortion on the stall margin in a transonic axial rotor." Journal of Thermal Science 21, no.3 (2012): 209-214.   
[10]Leinhos,D.C.,Norbert R. Schmid,and Leonhard Fottner. "The influence of transient inlet distortions on the instability inception of a low-pressure compressor in a turbofan engine."Journal of turbomachinery 123,no.1(2001): $_ { 1 - 8 }$ ：   
[11]Lin,F.,M.Li and J. Chen,"Long-to-short length-scale transition: a stall inception phenomenon in an axial compressor with inlet distortion,"J Turbomach,vol.128, no. 1,pp.130-140,2006.   
[12]Naseri, A.,M. Boroomand,and A.M. Tousi. "The Effect of Inlet Flow Distortion on Performance of a Micro-Jet Engine:Part 1—Development of an Inlet Simulator." In ASME 2012 Intermational Mechanical Engineering Congress and Exposition,pp. 317-324. Houston,USA, 2012.   
[13]Naseri,A.,M. Boroomand,A. M. Tousi,and A.R. Alihosseini. "The Effect of Inlet Flow Distortion on Performance of a Micro-Jet Engine:Part 2—Engine Tests." In ASME 2012 International Mechanical Engineering Congress and Exposition,pp.311-316. Houston,USA, 2012.   
[14]Gunn,E. J.,S.E. Tooze, C.A. Hall and Y. Colin, "An experimental study of loss sources in a fan operating with continuous inlet stagnation pressure distortion,"J Turbomach,vol.135,no.5,p.051002,2013.   
[15]Castaneda,J.,A. Mehdi, D. di Cugno,and V. Pachidis. "A preliminary numerical CFD analysis of transonic compressor rotors when subjected to inlet swirl distortion." In ASME 2011 Turbo Expo:Turbine Technical Conference and Exposition, pp.417-429. Vancouver, Canada, 2011.   
[16] Cameron, J. D.,M. A. Bennington, M. H. Ross,S. C. Morris,J. Du,F.Lin,and J. Chen."The Influence of Tip Clearance Momentum Flux on Stall Inception in a High-Speed Axial Compressor." Journal of Turbomachinery 135,no.5 (2013): 051005.   
[17]Strazisar, A. J., J. R. Wood, M. D. Hathaway, and K. L. Suder."Laser anemometer measurements in a transonic axial-flow fan rotor." NASA TP-2879,(1989).   
[18]Khaleghi,H.,A.M. Tousi,M.Boroomand,and J.A. Teixeira. "Recirculation casing treatment by using a vaned passage for a transonic axial-flow compressor." Proc IMechE,Part A: Journal of Power and Energy 221,no.8 (2007): 1153-1162.   
[19]Khaleghi, H.,M. Boroomand,J.A. Teixeira,and A.M. Tousi."A numerical study of the effects of injection velocity on stability improvement in high-speed compressors."Proc IMechE,Part A: Journal of Power and Energy 222,no.2 (2008): 189-198.   
[20] Sammak，S.and M. Boroomand,"Three dimensional numerical analysis of flow within an isolated rotor with stepped blades," Journal of Thermal Science 21, no.5, pp. 420-427,2012.   
[21] Cumpsty，N. A.Compressor aerodynamics. Longman Scientific & Technical,London,1989.   
[22]Vo,Huu Duc,Choon S.Tan,and Edward M.Greitzer. "Criteria for spike initiated rotating stall." Journal of turbomachinery 130,no.1 (2008): 011023.   
[23]Moore,F. K.,and E. M. Greitzer. "A theory of post-stall transients in axial compression systems: Part I—Development of equations." Journal of engineering for gas turbines and power 108,no.1(1986): 68-76.   
[24] Longley, J. P. "A review of nonsteady flow models for compressor stability."Journal of turbomachinery 116,no. 2 (1994): 202-215.   
[25]Wu, Y., Q. Li, W. Chu, H. Zhang and Z. Su, "Numerical investigation of the unsteady behaviour of tip clearance flow and its possible link to stall inception,"Proc IMechE, Part A: J Power and Energy, vol. 224, no. 1, pp.85-96, 2010.   
[26]Tan, C. S., I. Day, S. Morris,and A. Wadia. "Spike-type compressor stall inception,detection,and control." Annual review of fluid mechanics 42 (2010): 275- 300.   
[27]Wu, Y., Q. Li, H. Zhang and W. Chu, "Numerical investigation into the mechanism of spike-type stall inception in an axial compressor rotor," Proc IMechE,Part A: Journal of Power and Energy 226,no.2,pp.192-207,2012.   
[28]Khaleghi,H.,M. Boroomand,A.M.Tousi,and J.A. Teixeira."Stall inception in a transonic axial fan." Proc IMechE,Part A: Journal of Power and Energy 222, no. 2 (2008):199-208.   
[29]Khaleghi, H., "Stall inception and control in a transonic fan, part A: Rotating stall inception," Aerospace Science and Technology 41, pp.250-258, 2015.