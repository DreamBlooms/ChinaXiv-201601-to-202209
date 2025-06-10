# Effects of Rising Angle on Upstream Blades and Intermediate Turbine Duct

LIU Jun, WANG Pei\*, DU Qiang, LIU Guang, ZHU Junqiang

Institute of Engineering Thermophysics, Chinese Academy of Sciences,Beijing 10o190, China

With the improvement of requirement,design and manufacture technology,aero-engines for the future are characterizedby furtherreduction in fuelconsumption,cost,but increment inpropulsion efciency,which leads to ultra-high bypass ratio.The intermediate turbine duct (ITD),which connects the high pressure turbine (HPT) with the low pressure turbine (LPT),has a critical impact on the overallperformances of such future engines.Therefore,it becomes more and more urgent to master the design technique of aggressive, even super-aggressive ITDs. Over the last years,a lot ofresearch works about the flow mechanism inthe difuser ducts were carried out. Many achievements were reported,but further investigation should be performed.With the aid of numerical method, this paper focuses on the change of performance and flow field of ITD,as wellas nearby turbines,brought by rising angle (RA).Eight ITDs with the same area ratio and length,but different RAs ranges from 8 degrees to 45 degrees,are compared.

According to the investigation,flow field,especially outlet Ma of swirl blade is influenced by RA under potential effect, which is advisable for designers to modify HPTrotor bladesafter changing ITD.In addition to that, low velocity area moves towards upstream until the first bend as RA increases,while pressure loss distributionat S2 stream surface shows that hub boundary layer is more sensitive to RA,and casing layer keeps almost constant. On the other hand,the overall total pressure loss could keep nearly equivalent among different RA cases,which implies the importance of optimization.

# Keywords: Intermediate Turbine Duct, Swirl Blades,Rising Angle, Pressure Loss

# Introduction

Efficiency and SFC(Specific Fuel Consumption） are two important indicators of engine.In order to raise the performance,and to decrease the cost,higher efficiency and lower SFC are goals which have been pursued unremittingly. To fulfill such requirement, larger bypass ratio engine received more attention for its advantage and potential.However,when bypass ratio increased and hence the power needed by the fan remains,itis logical that the radius ofLPT blades is tend to be larger. So the radius difference between HPT and LPT increased on certain extent.However, such radius difference might introduce some worry from the designer's point of view. ITD,so, not only plays the role of connecting the HPT and the LPT,but also with the function of diffusing air to decrease Ma with lower pressure loss,is believed to be investigated essentially in more detail.

The performance of ITD can be influenced by many factors,for example,area ratio(AR),non-dimensional length(ratio of ITD length to inlet height),and so on. Among them，upstream flow condition is an apparent factor. Dominy et al.[1] investigated the influence of swirl upon the flow through a diffusing duct. On the same experimental facility, Dominy et al.[2] investigated the influence of the upstream blade wakes on the performance of the duct. To the experience of the author, their work is the first experiment dealing with the pseudo-steady influence of two-dimensional wakes extending from hub to the casing on ITDs. More recently, Hu et al.3] and Zhang et al.4] researched the influence of casing swirl and hub swirl distributions separately on the flow field within ITDs with experimental and numerical methods systematically.Miller et al.[5] published their work of researching the migration and dissipation of flow phenomena in a swan-necked diffuser downstream of a transonic high-pressure turbine stage.And in the next year, Miller et al.6] extended the knowledge of this area, that they investigated the interaction mechanisms between a high-pressure rotor and a downstream vane located in a diffuser. The influence of upstream HPT rotor gap size variation on the ITD's flow field is discussed by Marn et al.[7,10],Gottlich et al.8].and Sanz et al.9]. In addition to that, Axelsson et al.[11] revealed the complex flow structure development within ITD.

<html><body><table><tr><td colspan="4">Nomenclature</td></tr><tr><td>AR</td><td>Area Ratio</td><td>Abbreviation</td><td></td></tr><tr><td>HPT</td><td>High Pressure Turbine</td><td>Cps</td><td>Static Pressure Coefficient</td></tr><tr><td>ITD</td><td>Intermediate Turbine Duct</td><td>Cpt</td><td>Total Pressure Coefficient</td></tr><tr><td>LPT</td><td>Low Pressure Turbine</td><td>Pso</td><td>Inlet Static Pressure</td></tr></table></body></html>

<html><body><table><tr><td>Ma</td><td>Mach Number</td><td>Ps</td><td>Local Static Pressure</td></tr><tr><td>RA</td><td>Rising Angle</td><td>Pto</td><td>Inlet Total Pressure</td></tr><tr><td>SP</td><td>Static Pressure</td><td>Pt</td><td>Local Total Pressure</td></tr><tr><td>TP</td><td>Total Pressure</td><td></td><td></td></tr></table></body></html>

Gottlich et al.[12] and Pullan et al.[13]have studied the flow field within ITD.Johansson et al.[14] finished a work that focused on a joint experimental and numerical investigation of an intermediate duct configuration.Marn et al[15]compared the flow through two different s-shaped intermediate turbine duct configurations with different diffusion ratio.Hu et al.16]optimized a baseline ITD geometry by the software of Numeca to get a second ITD with $2 5 \%$ larger mean RA and a third ITD with $20 \%$ largerarea ratio.

Gottlich[17] summarized the previous work about ITD. The author reviewed the flow evolution through intermediate turbine diffusers and discussed the influence of different effects in a systematic way. This was a meaningful work for all the following investigations to have a good start and get a correct direction when they try to develop ITD.In addition to that, other useful investigations[18]-[26] about the ITD were finished by researchers.

Upstream flow condition is one important and apparent factor for ITD performance,which could also be realized by means of experimental facility and receives much study as above introductions.Another one,which is vital as well and attracts much attention but less investigation to be done,is the duct geometry itself.

Norris and Dominy[27] used both experimental and numerical results to show the differences between two Sshaped ducts with the same area ratio and radial offset but with different axial length.

Couey et al.[28] developed the original annular-diffuserperformance chart for ITDs This original chart has been widely used for diffuse-type duct design after Sovran and Klomp[29] reported it. With numerical method, Couey et al.assessed the interaction of duct slope and pitch-wise turning with area ratio and length using approximately sixty different duct configurations. After investigation, they got the conclusion that the influence of slope and exit pitch angle can be as significant as the area ratio and length parameters traditionally used to correlate duct performance.And a combination of new area ratio-length and slope-length parameters was found to segregate ducts between separated and non-separated cases. At last， they modified the Sovran and Klomp Chart.

A more detailed investigation of the effects of mean RA and area ratio on the aerodynamics of ITDs was done by Zhang[30] et al. in the large scale,low-speed, annular wind-tunnel facility at the National Research Council of Canada.After study, they found that the duct mean rise angle determined the severity of adverse pressure gradient in the casing's first bend whereas the duct area ratio mainly governed the second bend's static pressure rise.

In above contents,Norris and Dominy did the work to research the flow field of two ducts with the same area ratio and radial offset,but these ducts had different axial lengths.A more detailed work was done by Couey et al.. Almost sixty models were simulated to find the influence of duct slope parameter and pitch-wise turning parameter onITD, they focused on the relationship between overall performance and these key design parameters of ITD, but without further investigation of the flow field detail correspondingly. In addition to that,as author pointed out, without upstream blades, the real coupled influence was not captured.Because upstream wake is the main source of pressure loss,that should be paid more attention to if one wants to evaluate the ITD performance more accurately. Another question confused the writer is that whether the throat area of LPT vane keeps unchanged, which should be a more important parameter for vanes.

What's more,almost all the attentions were focused on the performance of ITD,while how the nearby turbines，especially upstream blades，were influenced re ceived muchlessfocus.

In this paper, ITD model is designed with upstream swirl vanes (which can supply wake and inlet swirl angle),and downstream LP nozzle vanes (which can supply real downstream flow field with effect of potential and blockage),as Figure 1 shown. Eight configurations are chosen with the aid of numerical method.All of these model configurations have the same AR and axial length, but different radial offsets.Performance comparison and flow field analysis for these models will be presented in the current paper with the purpose of identifying the influence of the radial offset of ITD on turbine performance and flow field.It is hopeful that the result would give some sensible thoughts when more aggressive ITD design is ready to be used in the future advance engine.

![](images/217c8bcc3a1c4a49f048749f1c1c2b16b558a14f2a5915ae9a063120b41348a4.jpg)  
Fig.1Defination of ITD model

# Numerical Model and Boundary Conditions

The original conservative ITD prototype is a welldesigned duct which is positioned between HPT and LPT with RA of 8 degrees from an aero-engine.With the purpose of further improving power output of LPT, it is prepared to study the ultimate potential of such ITD in this paper.

In order to investigate the influence of RA on ITD flow field separately,apart from the RA,other parameters are kept unchanged in these models.Inlet conditions and swirl blades are kept the same,as well as the axial outlet position (inlet of LPT nozzle).The parameters of ITD and LP nozzle are listed in Table 1.The numerical models with RA of 8(A8),15(A15), 20(A20), 25(A25), 30(A30)，35(A35)，40(A40) and 45(A45) degrees are investigated in parallel. However, the inner and outer walls of ITD's outlet section are modified to make sure that the ARof ITDis equivalent.Meanwhile, the hub and casing curvature of LPT nozzle are adapted to the modified duct.AsFigure 2 shown,A8,A20,A30 and A40 are presented.

Table1Parameters of ITD   

<html><body><table><tr><td>AR</td><td>L/H</td><td>Inlet Swirl Angle(°)</td><td>Throat Area of LPT(m²)</td></tr><tr><td>1.57</td><td>3.38</td><td>20</td><td>0.0198</td></tr></table></body></html>

![](images/8b79683f8ff40fc742dffd9875ff1c91fed004ab67b3367fd6520b6431ea010b.jpg)  
Fig.2The sketch of different RA ITDs

What should be paid more attention is that the LPT nozzle blade numbersofall the models are kept the same (44for swirlbladesandLPT nozzle).As whathas been mentioned above,in the current paper, authors would like to distinguish the RA's influence on the ITD.To fulfill such goal,it is believed by the authors that the same throat area of the LPT nozzles must be realized to guarantee the equivalent mass flow rates.Usually there are two ways to realize such requirement. One way is increasing the blade number of nozzle with all the blades profile kept unchanged; another way is altering the blade profile on certain extent, on one section or multi sections, while the blade number keeps unchanged.Although it is easier to finish the model modification with the first method, the unexpected relative larger weight of LPT nozzle accompanied with the increase of profile loss may eliminate our maneuver for further improving the turbine performance.So the second strategy is adopted. The throat area remains constant of $0 . 0 1 9 8 ( \mathrm { m } ^ { 2 } )$ in all the studied cases.And this is achieved by altering the nozzle's outlet mental angle, stagger angle and ratio of outlet passage width to the thickness of blade. Unguided turning angle is amended to smooth the blade surface. The boundary conditions for all models are the same,with a constant in-mass-flow of $8 . 5 2 ~ \mathrm { k g / s }$ at inlet,and back pressure of $2 4 0 \mathrm { k P a }$ . So the Reynolds number is kept $3 \times 1 0 ^ { 5 }$ to avoid its influence on boundary layers.

Commercial CFD software of Numeca is used.The topology of building model mesh is O4H,and matching periodicity technology is used to get an accurate flow field in blade passages.Figure 3 is the numerical model and structured grids of A4O as an example created by IGG. The mesh at blade root and leading edge is magnified locally to show the detail mesh. The orthogonality of mesh is good enough to reflect the flow field.And $\mathrm { Y + }$ near wall is set below 1 to fulfill the requirement of the Shear Stress Transport(SST) turbulence model. With the same count of blades,full non matching frozen rotor between swirl vanes and LPT nozzle is chosen to provide steadyupstream wake for ITD.

The quantity of model mesh is an important factor for numerical results.So a test of mesh independence to simulation result is necessary. Figure 4 is the relationship between total pressure ratio and mesh quantity of A8. This regularity applies to other models as well.From this chart, the mesh count will not influence the pressure ratio when it is more than3 million,which means that the flow field is independent of mesh count. So each model will be simulated with more than3 million meshes and their computation results are ready to be compared in the current paper.

![](images/38e8c9d334a67ae9c6c8d405dddd8050e26b679e690cf6fd7b9d9245f2dc5fc9.jpg)  
Fig.3Numerical Model and Mesh ofA40

![](images/7279b01a36165aa4d5759437e8e89fb0f166921d46f231f4fff9dd8f0c681cb6.jpg)  
Fig.4TestofMeshIndependence

![](images/cb29aeb852fd205bfa066cd6028c20e96a6652c3f7e27fbea6c4c779808e7cb1.jpg)  
Fig. 5

# Results and Discussion

All the models are simulated while RA is changed. In the following contents, the numerical results will be exhibited systematically.According to the simulation result, RA is an important factor which can change the performance ofITD and nearbyturbineblades.

After simulation, separation occurs in A45,and could not be diminished by modifying LPT nozzle blade profile So it is advised in this paper that RA should be set smaller than 45 to prevent separation. A45 will not be discussed to avoid severe numerical error.

Figure 5(a) and Figure 5(b) are yaw angle and Ma at ITD's inlet section,Plane C1.

From Figure 5(a) and Figure 5(b),compared with Ma, yaw angle is less influenced accompanied with the variation of RA,which means that angle is more stable under the influence of potential field. Except near hub region, the initial A8 case has a larger yaw angle in the main flow region than other cases. This can be deduced by the fact that the relatively smaller concave curvature along inner wall of A8 brings such phenomenon. In A8,more specifically, the tangential velocity is smaller near hub region,which reduces the yaw angle slightly.As the same reason，yaw angle above $50 \%$ passage height of A40 model is the smallest, especially at $9 5 \%$ passage height.

At theITD inlet section itcan be evidentlyfound that largerRA accompanied with smaller Ma.While A40 case has evident Ma unevenness, its counterpart A8 case owned more even Ma model. So it is important to focus on this characteristic to get a more even flow field.

The detailed flow field in S3 stream surface is useful to observe the local flow characteristic in totality.Figure 6presents the ITD inlet(Plane C1）Ma.Within the smaller RA case,high Ma region almost occupies all the passage height.However, the range oflow Ma increases gradually whenRA increased steadily.As RA reaches its peak in case A4O,Ma,higher than O.7,can be only seen above about $8 5 \%$ passage height. Stemming from swirl blade's pressure side,low velocity region developed and the core of low energy fluid remained closed to its pressure side.

According to Ma and yaw angle variations, ITD RA affects HPT rotor deviation angle.As the result,HPT performance is influenced,which should be forecasted during turbine design process.

The SP distributions on swirl blade surfaces are compared in Figure 7,and black dotted lines represent SP isolines.According to Figure 7(a), the blade surface SP increases when RA is larger.High pressure(larger than $2 9 2 \mathrm { { k P a } ) }$ regions extend from area near casing to entire blade surface. So the fluid decelerates near blade in larger RA model. Low pressure corner(less than $2 5 4 \mathrm { k P a } )$

![](images/8be48786def279149a53070e2829f71065963b094cc29009cfa107e71c21100f.jpg)  
Fig.6ITD Inlet Ma (From Downstream)

![](images/c76af4846629d4fcc78fa601da0eec64caa649d2327abf49ffa171b64ccda27d.jpg)  
Fig.7SP Distribution on Swirl Blade Surface

regions locate in blade trailing edge near root in A8. However, it moves near casing in A30 and A4O.As the swirl blade passage is horizontal,and blade profile was designed without twisting,the pressure distribution is influenced by stream-wise adverse pressure gradient. Low pressure corner area will change blade deviation angle.The feature of suction surface pressure is various Low pressure corner region is not observed instead of high pressure corner region developing from area near casing of A8 to area near root of A40.Low pressure regions narrow down from entire blade surface of A8 to trailing edge area of A4O (the blank area at trailing edge).

In subsonic turbine stage,on one hand, more attention should be received for downstream flow field;On the other hand, different RA can cause change to upstream flow field simultaneously. With larger ITD outlet radius of investigated models,the inlet flow for LPT nozzle differs. The yaw angle and velocity distribution would present various features to affect downstream turbine performance.

More specifically, flow field in S2 surface of duct will be discussed. If separation occurs within S2 stream surface,three-dimensional flow field must be abominable and design progress should be restart.Pressure loss distribution could present an objective orientation whether the duct wall's curvature design is acceptable or not.

Total pressure coefficient Cpt is defined here as:

In which Pt is local total pressure, $\mathrm { P t } _ { 0 }$ the mass averaged inlet total pressure of ITD respectively，Cpt represents total pressure loss.Larger value of Cpt denotes that higher total pressure loss will be occurred.

Figure 8 and Figure 9 are Cpt and Ma contours of different models,only A8 and A4O are presented.The dashed white lines imply the stream-wise planes, S3 surface,C1 to C5 correspondingly. C1 to C5 planes are approximately perpendicular to streamlines along ITD, which is intended for analyzing the detailed flow field correspondingly.

Within ITD, ultra high total pressure loss spots mainly concentrate on the hub wall while the RA of ITD decreases (red dashed line ellipse areas in Figure 8). This means a thicker hub boundary layer on inner wall of smaller radial offset ITD(Noting that no separation happened within all the models except A45). The inner wall curvature effects the low velocity region,which moves gradually towards the first bend of ITD in higher ITDs (dashed blue ellipses in Figure 9).As increase of ITD's mean radius,the curvature of ITD wall differs.This causes variable positions of the peak adverse pressure gradient along inner wall.As the result,the main low energy fluid congregated near the first bend ofITD.

The feature of pressure loss near casing is different from that near hub.The high total pressure loss area near casing keeps almost the same.It extends from swirl blade to LPT nozzle (Figure 8). However, more evident and lower velocity area within ITD appears (Figure 9),and locates near LPT nozzle for all models.As RA increases, the adverse pressure gradient increases along outer wall within ITD,and the peak magnitude region keeps nears LPT nozzle.

Boundary layers on duct walls are influenced by RA severely according to above discussion.In order to further find out how the shearing stress on walls is affected, streamlines and SP coefficient, Cps,are presented simultaneously.

SP coefficient, Cps,is defined as:

$$
\mathrm { C p s } = ( \mathrm { P s } { \mathrm { - } } \mathrm { P s o } ) / ( \mathrm { P t o } { \mathrm { - } } \mathrm { P s o } )
$$

where Ps is the local static pressure, $\mathrm { P _ { t 0 } }$ and $\mathbf { P _ { s 0 } }$ the mass averaged total and static pressure at inlet of ITD correspondingly. Cps could distinguish how the SP field is changed by various factors while ruling out velocity.

![](images/56fafe021c3dddb5b576f2319ba56b913fd36058307fb4851dd86db47e061747.jpg)  
Fig.8Cpt of S2 Stream Surface

In all the ITDs,LPT nozzle locates before the $2 ^ { \mathrm { n d } }$ bend of the ITD,while the $1 ^ { \mathrm { s t } }$ bend starts from right downstream the ITD inlet section (the starting position of the figures).From Figure 1O(a),it can be easily found that completely different limited streamlines appear on the hub wall. For A8,smooth surface limited streamlines near inlet concentrated near the hub wall,while streamlines before LPT nozzle are nearly perpendicular to the axial direction,which means an extremely large circumferential velocity compared with the axial velocity. Such phenomenon indicates that relatively extremely thick & low velocity boundary layer concentrated near the ITD's hub wall.

Variation of the saddle point location, with increasing of the RA,near the LPT nozzle's leading edge,implies different inlet angle performance. Comparatively, limited streamlines’skewness near ITD inlet is more overt when the RA increases.Span-wise pressure gradient which is changed by the $1 ^ { \mathrm { s t } }$ and $2 ^ { \mathrm { n d } }$ bend of the ITD induce such difference.With larger RA,higher span-wise pressure gradient can be found at both the $1 ^ { \mathrm { s t } }$ and $2 ^ { \mathrm { n d } }$ bend within the ITD,which causes the low momentum boundary layer flow that accumulated near the hub,at the $1 ^ { \mathrm { s t } }$ bend position,mixing with the main-stream flow. Such kind of flow movement may result in less low momentum flow accumulating near the hub wall, and hence reduces the streamlines’skewness.Cps contours reaffirm such variation again.

![](images/34dd881073dc1cbffb6a06d13f21562160933a990ddd52a476559463e3c13164.jpg)  
Fig.9Ma of S2 Stream Surface

![](images/b81c3130cb511a5681cfcf073b114f4e150251f5c3e17ce6b1577231fc96108d.jpg)  
Fig. 10

Similarly, the flow movement close to the outer wall differs from each other. The limited streamline on shroud of A8 is smoother comparing with its counterpart A40 case,which is formed by the smaller stream-wise pressure gradient near the first bend Comparing the limited streamlines on hub and shroud, it is influenced more easily near inner wall.

Figure 11 is Cpt of S2 stream surface at $50 \%$ span. The dissipation of trailing edge shed vortex generated by upstream swirl vanes can be observed clearly. However, since RA is various in different cases,which means that the actual length (not axial length) of the ITD is also modified. So even the swirl vane's design remains unchanged in all cases,different circumferential positions of upstream trailing edge induced wake can be scrutinized at the inlet of the LPT nozzle.Under its influence, incidence angle of LPT nozzle no doubt will change.As the result, LPT nozzle's performance will be definitely changed. So it is necessary for designers to optimize the blade profile as well as the wall curvature, especially the parts near the ITD's outlet section,to improve downstream turbine's performance.

Finally, total pressure losses of all the models (except A45)at different planes (Figure 8) are compared by Cpt in Figure 12. C1-C2 means pressure loss from Plane C1 to C2.Apparently, pressure loss is the severest between C1 to C2 for all models, near $1 ^ { \mathrm { s t } }$ bend of the ITD.At this region, upstream wake is strongly dissipated to increase pressure loss. After C2，pressure loss is generated by wake dissipation and boundary layer accumulation.

![](images/94b4c0b47c1f64b84977b3ceb39488bb14bbe49e64e9c4a462861ec99c449315.jpg)  
Fig.11Cpt at $50 \%$ Passage Height   
Fig.12Cpt of different models

1  
0.9  
0.8  
0.70.40.3 一0.20.1C1-C50 C1-C4A8 A15 A20 A25 CC1-C3A30 A35 A40

While it is evident that pressure loss exhibits weak relationship relatively between pressure loss and RA.Larger RA will not lead severer pressure loss consequently. For example, Cptof A2O is the least than all other models.So it seems like that RA is not the only decisive factor for pressure loss,while other reason should be considered. In this paper, wall curvatures are modified by RA，while length and area ratio are constant.As a result,in order to decrease loss,it is strongly advised that optimization of walls should be takenafterRAis decided.

# Conclusions

In this paper, authors investigate the influence of RA on upstream blade and ITD with numerical method.On the basis of the same original model coming from a real engine, seven ITDs are gotten to be simulated.However, separation is found in A45 because of too large RA.So it is advised that RA should be smaller than 45 to prevent separation.After analysis,several coclusions are drawn.

Larger RA will lead high loss area (also be the low Ma area) near hub to move towards ITD inlet and increase the risk of separation within ITD.

At the inlet section of ITD(outlet of swirl vanes), relatively lower Ma area distributes near inner wall region and lower yaw angle area seperates near outer casing when RA increases to infer a stronger potential effect of ITD.So it is issential for designers to modify or optimize HPT rotor blade profile while improving ITD. More specifically， the outlet angle,as well as stagger angle should be larger to keep a relatively constant angle, especiallynearshroud.

With various RA，the limited streamlines on walls present individual characteristics.More specifically, they are more twisted near the first bend to indicate the trend that the flow field near the first bend is effected most. However, the total pressure loss analysis shows that the loss is not necessarily larger in ITD with higher outlet radius.So an acceptable loss level with large RA is possible.Cpt is superiorly high when the ITD is too aggressive.

As a conclusion, the RA's selection plays a key role in making sure a well-designed ITD. Since the flow thread through the ITD will decide the downstream flow field's quality and hence the downstream part's aerodynamic characteristic, so the flow movement characteristic should be kept in mind when the ITD is studied and ready to be used in an engine.An important issue of this paper is the total pressure loss could be controlled in larger RA ITDs,while optimization is essential.

# Acknowledgements

Thanks for the support from the National Natural Science Foundation of China (No. 51406204).

# References

[1]Dominy,R.G.,Kirkham,D.A..1995.The Influence of Swirl on the Performance of Inter-Turbine Diffusers.VDI Berichte 1186,pp.107-122.   
[2]Dominy,R.G.,Kirkham,D.A..1996. The Influence of Blade Wakes on the Performance of Inter-Turbine Diffusers,ASME J. Turbomach.,118,pp.347-352.   
[3]Hu, S. Z., Zhang, Y.F., Zhang,X.F.,and Vlasic,E.. 2011. Influences of Inlet Swirl Distributions on an Inter-TurbineDuct,Part I:Casing Swirl Variation.Proceedings of ASME Turbo Expo 2011.Vancouver,British Columbia, Canada. GT2011-45554.   
[4]Zhang, Y.F.,Hu, S.Z., Zhang,X.F.,and Vlasic,E..2011. Influences of Inlet Swirl Distributions on an Inter-Turbine Duct,Part II:Hub Swirl Variation. Proceedings of ASME Turbo Expo 2011.Vancouver,British Columbia, Canada. GT2011-45555.   
[5]Miller,R.J., Moss,R.W., Ainsworth,R. W.,and Harvey, N.W..20o3.The Development of Turbine Exit Flow in a Swan-Necked Inter-Stage Diffuser.Proceedings of ASME Turbo Expo 2003．Atlanta，Georgia，USA.GT2003- 38174.   
[6]Miller,R.J.,Moss,R.W.,Ainsworth,R.W.,and Harvey, N.W..2004.The Effect of an Upstream Turbine on a Low-Aspect Ratio Vane.Proceedings of ASME Turbo Expo 2004. Vienna,Austria. GT2004-54017.   
[7]Marn，A.，Gottlich，E.，Pecnik，R.，Malzacher,F.J., Schennach,O.,and Pirker,H.P..2oo7.The Influence of Blade Tip Gap Variation on the Flow Through an Aggressive S-Shaped Intermediate Turbine Duct Downstream a Transonic Turbine Stage - Part I: Time-Averaged Results. Proceedings of ASME Turbo Expo 2007. Montreal, Canada. GT2007-27405.   
[8]Göttlich，E.，Marn，A.，Pecnik，R.，Malzacher,F.J., Schennach, O.,and Pirker, H. P..20o7.The Influence of Blade Tip Gap Variation on the Flow Through an Aggressive S-Shaped Intermediate Turbine Duct Downstream a Transonic Turbine Stage - Part I: Time- Resolved Results and Surface Flow, Proceedings of ASME Turbo Expo 2007. Montreal, Canada. GT2007-28069. [9]Sanz, W.,Kelterer,M.,Pecnik,R.,Marn,A.,and Gottlich, E.,2009.Numerical Investigation of the Effect of Tip Leakage Flow on an Aggressive S-Shaped Intermediate Turbine Duct. Proceedings of ASME Turbo Expo 2009. Orlando,Florida, USA. GT2009-59535.   
[10]Marn,A., Gottlich,E.,Malzacher,F.,and Pirker,H. P.. 2009.The Effect of Rotor Tip Clearance Size onto the Separation Flow Though a Super- Aggressive S-shaped Intermediate Turbine Duct Downstream of a Transonic Turbine Stage.Proceedings of ASME Turbo Expo 2009 Orlando,Florida, USA. GT2009-59934.   
[11]Axelsson,L.-U. Johansson, T.G.20o8.Experimental Investigation of the Time- Averaged Flow in an Intermediate Turbine Duct. Proceedings of ASME Turbo Expo 2008.Berlin, Germany. GT2008-50829   
[12]Gotlich,E., Marn,A., Malzacher,F.J., Schennach,O., and Heitmeir, F..2Oo7. Experimental Investigation of the Flow Through an Aggressive Intermediate Turbine Duct Downstream of a Transonic Turbine Stage.Proceedings of the Seventh ETC, Athens, p. 383.   
[13]Pullan,G., Denton, J.,and Dunkley, M..2003.An Experimental and Computational Study of the Formation of a Streamwise Shed Vortex in a Turbine Stage.ASME J. Turbomach.,125, pp.291-297.   
[14]Peter,B.V., Johansson, T.G.,and Axelsson,L.-U.. Numerical and Experimental Analysis of the Flow in an Aggressive Intermediate Turbine Duct. 2009.Proceedings of ASME Turbo Expo 2009.Orlando,Florida,USA.GT2009- 59299.   
[15]Marn,A., Gottlich,E.，Malzacher,F.,and Heitmeir, F. 2009.Comparison Between the Flow Through an Aggressive and a Super-Aggressive Intermediate Turbine Duct.Montreal, Canada. ISABE-2009-1259.   
[16]Hu, S. Z., Zhang,X. F., Benner, M., Gostelow,P.,and Vlasic,E..2010. Geometric Optimization of Aggressive Inter-turbine Duct. Proceedings of the 14th International Mechanical Enginering Congress & Exposition. Vancouver,British Columbia, Canada.IMECE 2010-37323.   
[17]Gotlich,E.. 2011. Research on the aerodynamics of intermediate turbine diffusers. Prog Aerospace Sci (2011), doi:10.1016/ j.paerosci. 2011.01.002   
[18]Satta F., Simoni D., Ubaldi M., Zunino P., Bertini F., and Spano E..20o7. Velocity And Turbulence Measurements ina Separating Boundary Layer with and without Passive Flow Control. Proceedings of the Institution of Mechanical Engineers,Part A: Journal of Power and Energy. 2007 221: 815, DOI: 10.1243/09576509JPE457.   
[19]Axelsson,L.-U.,Arroyo Osso, C., Cadrecha,D.,and Johansson,T.G.2oo7.Design,Performance Evaluation and Endwall Flow Structure Investigation of an S-Shaped Intermediate Turbine Duct.Proceedings of ASME Turbo Expo 2007.Montreal, Canada.GT2007-27650.   
[20]Wallin,F., Osso,C.A.,and Johansson,T.G..2008.Experimental and Numerical Investigation of an Aggressive Intermediate Turbine Duct: Part 1-Flow Field at Design Inlet Conditions.26th AIAA Applied Aerodynamics Conference,18-21 August 2008,Honolulu,Hawaii.AIAA 2008-7055.   
[21]Osso, C.A.,Wallin,F.,and Johansson,T.G.. 2008. Numerical Investigation of an Aggressive Intermediate Turbine Duct -Part 2:Flow field under Off-Design Inlet Conditions.26th AIAA Applied Aerodynamics Conference，18-21 August 2008,Honolulu,Hawaii.AIAA 2008-7056.   
[22]Wallin,F.,Eriksson,L.E..20o6.Response Surface-based Transition Duct Shape Optimization. Proceedingsof ASME Turbo Expo 2006.Barcelona，Spain.GT2006- 90978.   
[23]Lavagnoli, S., Yasa,T.,Paniagua, G.,and Duni, S.. 2010. Aerodynamic Analysis of an Innovative Low Pressure Vane Placed ina S-Shape Duct.In Proceedings of ASME Turbo Expo 2010.Glasgow,UK.GT2010-22546.   
[24]Karakasis,M.K.,Edward,M.J.N.,Miller,R.J.,and Hodson,H.P..2010.The Effect of an Upstream Compressor on a Non-Axisymmetric S-Duct. In Proceedings of ASME Turbo Expo 2010.Glasgow,UK.GT2010- 23404.   
[25]Spataro,R.,Gottlich,E.,Lengani,D.,Faustmann,C., Heitmeir, F..2013.Development of a Turning Mid Turbine Frame with Embedded Design - Part I:Design and Steady Measurements.Proceedings of ASME Turbo Expo 2013.San Antonio, Texas,USA.GT2013-95279.   
[26]Spataro,R.,Gottlich,E.， Lengani, D.,Faustmann,C., Heitmeir, F..2013.Development of a Turning Mid Turbine Frame with Embedded Design -Part II:Unsteady Measurements.Proceedings of ASME Turbo Expo 2013. San Antonio,Texas,USA.GT2013-95280.   
[27]Norris,G,Dominy,R.G.1997.Diffusion Rate Influences onInter-TurbineDiffusers,IMechEJ.ofPowerand Energy,211 Part A,pp.235-242.   
[28] Couey,P.T.,McKeever, C.W.,and Malak,M.F..2010. Computational Study of Geometric Parameter Influence on Aggressive Inter-Turbine Duct Performance.Proceedings of ASME Turbo Expo 2010.Glasgow, UK.GT2010- 3604.   
[29]Sovran G.,Klomp E.D..1967.Experimentally Determined Optimum Geometries for Rectilinear Diffusers with Rectangular,Conical or Annular Cross-Section. Fluid Mechanics of Internal Flow,Elsevier,Amsterdam, pp.270-319,1967.   
[30]Zhang,Y.F.,Hu,S.Z.,Mahallati,A.,Zhang,X.F.,and Vlasic,E..2014.Effects of Area Ratio and Mean Rise Angle on the Aerodynamics of Inter-Turbine Ducts.Proceedings of ASME Turbo Expo 2014.Diüsseldorf,Germany. GT2014-27207