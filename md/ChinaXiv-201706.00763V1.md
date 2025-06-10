# Numerical Investigation of the Effects of ITD Length on Low Pressure Nozzle

LIU Guang12, LIU $\mathbf { J u n ^ { 1 * } }$ ,Liu Hongrui', Wang Pei',DU Qiangl

1. Institute of Engineering Thermophysics, Chinese Academy of Sciences,Beijing 100190, China   
2.University of Chinese Academy of Sciences,Beijing,10o049, China

$\copyright$ Science Press and Institute of Engineering Thermophysics,CASand Springer-Verlag Berlin Heidelberg 2017

The advantage of high eficiency,low SFC(Specific Fuel Consumption),ultra-high bypassratio turbofan engine attracts more and more atention in modern commercial engine.The intermediate turbine duct (ITD), which connects high pressure turbine (HPT) with low pressure turbine (LPT),has a critical impact on the overall performance of turbine by guiding flow coming from HPT to LPT without too much loss.Therefore,it becomes more and more urgent to master the technique of designing aggressive, even super-aggressive ITD.

Much more concerns have been concentrated on the duct.However,in order to further improve turbine,LPT nozle is arranged into ITD to shorten low pressure axle.With such design concept, it is obvious that LPT nozzle flow field is easily influenced by upstream duct structure,but receives much lessinterests on the contrary. In this paper, numerical method is used to investigate the efects of length ofITD with upstream swirl blades on LPT nozle.Nine models with the same swirl and nozzle blades,while the length of ITD is the only parameter to be changed, will be discussed.Finally,several conclusions and advices for designers are summarized.

After changing axial length of ducts,inlet and outlet flow field of nozle difers,correspondingly.On the other hand,the shearing stresson nozzle blade (suction and pressure)surface presents individual feature under various inletflow.In addition to that,“Clocking-like effect”is described inthis paper,which willcontribute much to the pressure loss and should be paid enough attention.

# Keywords: Intermediate Turbine Duct,Length, Nozzle,Pressure Loss

# Introduction

It is pursued all the time to design an engine with higher thrust-weight ratio and lower cost, which requires ultra-high bypass ratio to lead larger diameter fan.However, the tip speed of fan is limited to subsonic,so as to keep acceptable loss and be sure security. As the result, the rotation speed has to be decreased, so does the LPT rotors.With unchanged mass flow, the medium diameter ofLPT will increase.So it becomes more and more important, but more and more difficult to guide flow leaving HPT to LPT without severe pressure loss.The question will be how to achieve it? ITD is believed to be investigated essentially in more details,so as it could be designed more aggressively. More and more attention has been paid to this area in recent years.

Before designing aggressive, even super- aggressive ITD, the primary work is to understand flow mechanism ofITD.Many researchers made hard efforts to investigate this duct, from the original simple annular diffuser to S-shaped duct, and modern aggressive duct finally.

The investigation about flow in ITD began from simple annular diffuser, which was done by Stevens et al.[1] at the University of Durham,and then simple S-shaped duct was measured and discussed by many other researchers[2]-[4]. But subject to the limitation of measurement technology, the flow field gotten was crude and inaccurate.

<html><body><table><tr><td colspan="4">Nomenclature and Abbreviation</td></tr><tr><td>HPT</td><td>High Pressure Turbine</td><td>SP</td><td>Static Pressure</td></tr><tr><td>ITD</td><td>Intermediate Turbine Duct</td><td>Cpt</td><td>Total Pressure Loss Coefficient</td></tr><tr><td>LPT</td><td>Low Pressure Turbine</td><td>Pt</td><td>Local Total Pressure</td></tr><tr><td>Ma</td><td>Mach Number</td><td>Pti</td><td>Inlet Total Pressure</td></tr><tr><td>SFC</td><td>Specific Fuel Consumption</td><td></td><td></td></tr></table></body></html>

Miller et al.[5] described both the migration and dissipation of flow in the ITD with upstream high-pressure turbine stage ina transonic facility.The author found that the inlet flow to a downstream vane was dominated by two co-rotating vortices,the first caused by the rotor tip-leakage flow and the second by the rotor hub secondary flow,which was the first to describe the detailed vortices development within ITD as the author knew. And then downstream nozzle vanes were presented in the duct to get a more realistic flow field. In a large-scale, low-speed, experimental turbine facility，Axelsson et al6]-7linvestigatedtheflowdevelopmentfordifferent turbine conditions.

In addition, CFD simulation,as an effective means, was adopted to investigate the ducts. Walin et al.[8] and Osso et al.9] studied the flow field in an aggressive ITD under design inlet condition and off-design inlet condition.They found that the total pressure loss increased under off-design condition,especially in the ducts with separation. Peter et al.10] made experimental and numerical investigations of an aggressive intermediate duct configuration.With upstream HPT and downstream LPT nozzle, the author found that the hub and shroud pressure profiles were well predicted while the total pressure loss was over predicted in the numerical simulations.

Steady flow field is important to understanding the mechanism ofITD,but whether the unsteady flow field is similar to the steady condition? With numerical simulation,Davisetal.presented theunsteadyflowina transonic turbine stage,and compared their result with experiment, which showed overall good agreement between the simulation and experiment data.

Gotlich et al.[12] built a transonic test turbine facility to explore flow within aggressive ITDs in Graz University_of Technology.With this facility，Gottlich et al.[13] studied the steady and unsteady flow field in an aggressive ITD downstream of a single-stage turbine. On this basis,a much shorter so-called super-aggressive intermediate duct ( $20 \%$ shorter than_the aggressive duct) was designed by Gotlich et al.[14]. And Marn et al.[15] discussed the flow field in this super-aggressive ITD and compared it with aggressive ITD.With numerical simulation and experiment, the authors gained a more detailed insight into the flowbehavior of a fully separated duct.

Except for investigating the steady and unsteady flow field within different ITDs, the influence of nearby turbine stages on ITD was researched.

Dominy et al. discussed the influence of swirl[16] and upstream wake[17] on ducts. And then the effect of blade tipclearance8]etirgeistt upstream flow field[25] were reported by many researchers. On the other hand, the flow fields in ITDs with different geometries, such as various streamline curvatures262tie were described as well. Through different methods,investigators got many meaningful conclusions,and gave many valuable advices for designing ITDs.

According to the above introduction,muck work was finished. Steady,as well as unsteady flow field in annular diffuser, S-shaped ducts,and aggressive ITDs were described with experimental and numerical methods.The systematic knowledge about ITD flow field has been built.Besides flow field analysis in ITDs,the influences of blade tip clearing,upstream wake, geometry of area ratio,diffuser ratio,curvature,and so on,on the flow field of ITD were investigated.What's more, through comparison with experimental results,a common conclusion was drawn that numerical simulation could get a good enough flow field and ITD performance,which could be used to analyze and evaluate the flow in ITD.

Many excellent studies have been done about perfor mance of ITD under different conditions,which are important for designing aggressive diffuser duct.However, hownearbyturbinesare influencedbyduct remainsunknown, which is important for designing future turbine as well.This issue should be analyzed and discussed to draw clear conclusions and to give advisable guidance for designers essentially.

In this paper, ITDs with the same upstream swirl blades and downstream LPT nozzle are designed,as shown in Figure 1.Nine models with different duct length are simulated with numerical method to investigate the effect of ITD length on LPT nozzle.As shown in Figure 2,four typical models are presented. The author hopes this paper could give an insight into how to design an ITD,as well as nearby turbine stages with more prop er length while ITD is working under engine environments.Meanwhile, findings revealed by the current paper will provide meaningful insights for further optimization of the ITD through the engineering perspective.

![](images/a7919843cc1c34c90d9abf94d1f4ecb9f366369992a96b3a22073b4eb33f9de0.jpg)  
Fig.1Definition of ITD model

![](images/009c933626e12670f02f2a9024322784b57a6255bcaddf6feb4af4dfeb0658c7.jpg)  
Fig.2The sketch of different length ITDs

# Numerical Model and Boundary Conditions

The original aggressive ITD prototype in this paper comes from another investigation paper, which focused on the effect of rising angle on ITD performance.In that paper,eight ITD models with the same upstream swirl blades were simulated. Area ratio $_ { ( = 1 . 5 7 ) }$ and nondimensional length $\mathrm { ( L / H } = 3 . 4 )$ of ducts remained unchanged, while rising angle $( 8 ^ { \circ } { \sim } 4 5 ^ { \circ } )$ was the only parameter modified.On the basis of that paper, the ITD with $2 5 ^ { \circ }$ rising angle is chosen to be the target object further investigated.

After optimizing LPT nozzle blades to improve flow field again, the prototype model (Aero ratio $= 1 . 5 7$ ， $\scriptstyle { \Theta = 2 }$ $5 ^ { \circ }$ $\mathrm { L } / \mathrm { H } = 3 . 4 \AA$ isdefined.In ordertounderstandhowITD length influences downstream LPT nozzle,nine models modified of $\mathrm { ~ L ~ } _ { - } 3 . 4$ 0 $\mathrm { L } / \mathrm { H } = 3 . 4 \$ ，L_3.2 $\mathrm { L } / \mathrm { H } = 3 . 2 \$ ）, $\mathrm { ~ L ~ } _ { - } 3 . 0$ $\mathrm { ( L / H } = 3 . 0 \$ ） $\mathrm { ~ L ~ } 2 . 8$ 1 $\mathrm { { L } / \mathrm { { H } } } = 2 . 8 \$ ）， $\mathrm { ~ L ~ } _ { - 2 . 6 }$ 0 $\mathrm { { L } / \mathrm { { H } } } = 2 . 6$ L_2.4 $\mathrm { ( L / H } = 2 . 4 )$ ，L_2.2 $\mathrm { L } / \mathrm { H } = 2 . 2 \$ L_2（ $\mathrm { L } / \mathrm { H } = 2 \$ ）， $\mathrm { ~ L ~ } _ { - } 1 . 8$ $\mathrm { { L } / \mathrm { { H } } = 1 . 8 \mathrm { { \Omega } } }$ ）are simulated in parallel.Swirl blades and nozzle blades remain unchanged,as Table 1 lists.Blade numbers of swirl and nozzle are set the same 44 to guarantee the results being credible, from which wake of swirl blade could be transported to LPT nozzle accurately without circumferential average.

Table 1 Blade Parameters   

<html><body><table><tr><td></td><td>Swirl</td><td>Nozzle</td></tr><tr><td>Blade Number</td><td>44</td><td>44</td></tr><tr><td>Axial Chord</td><td>21.64</td><td>28.88</td></tr><tr><td>Exit Angle</td><td>-20.80</td><td>61.74</td></tr><tr><td>Inlet Angle</td><td>0</td><td>-31.39</td></tr><tr><td>Stagger Angle</td><td>-12.79</td><td>34.23</td></tr><tr><td>Unguided Turning</td><td>0</td><td>15.46</td></tr><tr><td>Pitch/Chord</td><td>0.77</td><td>0.77</td></tr><tr><td>Tmax/Axial Chord</td><td>0.07</td><td>0.21</td></tr></table></body></html>

The boundary conditions for all models are the same, with a constant in-mass-flow of $8 . 5 2 ~ \mathrm { k g / s }$ at inlet, and back pressure of $2 4 0 \ \mathrm { k P a }$ . So the Reynolds number is kept $\bar { 3 \times 1 0 ^ { 5 } }$ to remove its influence on boundary layers.

The commercial CFD software of Numeca is used. The topology of building model mesh is O4H,and matching periodicity technology is used to escape numerical dissipation so as to get an accurate flow field in blade passages.Figure 3 is the numerical model and structured grids of $\mathrm { ~ L ~ } _ { - } 2 . 6$ as an example created with IGG The mesh at blade root and leading edge is magnified locally to show the mesh detail. The orthogonality of mesh is good enough to reflect the flow field.And ${ \mathrm { Y } } ^ { + }$ near wall is set below 1 to fulfill the requirement of the Shear Stress Transport(SST) turbulence model.With the same count of blades,full non-matching frozen rotor between swirl blades and LPT nozzle is chosen to provide steady upstream wake for ITD.

The quantity of model mesh is an important factor for numerical results.So a test of mesh independence to simulation result is necessary.Figure 4 is the relationship between total pressure ratio (of model inlet to model outlet) and mesh quantity ofL_3.4. This regularity applies to other models as well. From this chart, the total pressure ratio will not be influenced any more when the mesh is more than 3 million,which means that the flow field is independent of mesh count. So each model will be simulatedwithmore than3 millionmeshes.

![](images/88a2933e71203cfb32ac6081c73ccce51c7b2f9cfdfb35732debc5103807c4b5.jpg)  
Fig.3Numerical Model and Mesh of L_2.6

![](images/08941ee65ea059c93d5d6974c12378084b55228f31a4575eb7c4c412f0cf2f8a.jpg)  
Fig.4Test of Mesh Independence

# Results and Discussion

After simulating all the models, it is found that separation occurs in ITD models shorter than $\mathrm { ~ L ~ } _ { - 2 . 2 }$ ，especially $\mathrm { ~ L ~ } _ { - } 1 . 8$ ,in which separation is very severe at leading edge of LPT nozzle blade. Because all the nozzle blades remain the same with $\mathrm { ~ L ~ } _ { - } 3 . 4$ so as to investigate the influence of ITD length separately, blade profile is not optimizational except L_3.4.

In the following discussion, four typical models of L_3.4,L_3,L_2.6,L_2.2 are chosen to be analyzed to draw objective conclusions.As what has been stated above, this paper focuses on the effects ofITD length on LPT nozzle,so flow field and performance of nozzle bladeswillbe discussed in detail,while flow field within ITD is paid less attention. Inlet as well as outlet angle distribution will be discussed preferentially.

The radial yaw angle distribution at LPT nozzle inlet differs when the length of upstream ITD changes.As shown in Figure 5, the overall trends for all the ducts are very similar. The peak magnitude locates at about $9 5 \%$ passage height, and two relative local troughs appear at about $1 9 \%$ and $78 \%$ height,which mean that the ITD length will not change the radial angle distribution trend too much.

![](images/100ee3925327a27d166d3439aee9863e34a3315e65bf0434cd0431e120a26e41.jpg)  
Fig.5Radial yaw angle atLPT nozzle inlet

But local detail is various.An evident phenomenon is that the regions near walls are more easily influenced According to Figure 5, the deviation amplitude difference nearwallsis large.A circumferential flow about 42 degrees in model L-2.2 compared with 32 degrees in L-3.4 presents a severer deviation near outer wall. Tangential velocity is larger thanaxial velocity,which means thicker boundary layer on outer casing in shorter models.On the other hand, within the main flow near mid-height passage, the angle is more stable relativelywith a more axial flow in shorter ITDs.And this trend is severer nearhub.So the boundary layer on hub of shorter duct is thinner correspondingly. Obviously, the attack angle ofLP nozzle blade will be more negative in more aggressive ITD model, which may induce separation on the pressure surface to increase pressure loss.This phenomenon will be de scribed in following contents.Though the boundary layer distribution within ITD is not emphasized in this paper, such conclusion should be acknowledged that boundary layer on hub will be thinner,while it is thicker on casing when ITD length decreases.Without doubt,the blade profile of LPT nozzle near walls should receive more attention in order to control pressure loss.

After developing through the same nozzle passage, flow information at the outlet of LPT nozzle shows the effect of upstream ITD is opposite,as Figure 6 shows.

![](images/263ec4adf9008852c77853efd07230a6c7e54f932d1b90648d89189a7add99f4.jpg)  
Fig.6Radial yaw angle atLPT nozzle outlet

Near walls, the flow yaw angles among various ducts have similar trend relatively that the number and located height of local extremums are almost the same,which is identical with the distribution at inlet.The angles near walls are larger within boundary layers,while more axial in the main stream,especially at about $1 5 \%$ and $7 5 \%$ passage height where upper passage vortex and lower passagevortexlocate.

However, the radial angle details show individual features above $1 5 \%$ to $80 \%$ passage height. The regularity where yaw angle changes within different ducts shows that the peak magnitude migrates with a period radially in Figure 6.Actually,the angle distribution is influenced mainly by passage vortices and flow near blade corners. With the same blade profile and downstream passage, the pressure field near hub remains almost unchanged, given the thinner boundary layers at nozzle inlet. While near outer wall, the boundary layer thickens to accumulate more low energy fluid. So the angle differs more than that near hub.While in other main stream regions, pas sage vortices are influenced by upstream wake evidently, especially upper passage vortex,as the black dashed line region shows.

How the flow field in nozzle blade passage is affected is more interesting for designers.The detail analysis on shearing stress distribution on blade surfaces will be presented.

In Figure 7, the static pressure(SP) contour on LPT nozzle blade suction surface is presented with the limiting streamlines exhibited as well.Because the blade pro file of all the ducts remains unmodified, the inlet flow angle in main stream is affected little relatively. With decreasing of ITD length,the boundary layer on blade surface shows similar information according to limiting streamlines distribution: radial migration towards midheight passage near trailing edge remains existed. And SP contours almost keep unchanged: the low SP(blue) area locates near hub in the vicinity of throat and high SP (red) area sticks to leading edge.

![](images/f759e0ab007b5e3ece78e5e9e212a812340b66d3733870821fc16b5a51ff50f9.jpg)  
Fig.7SP on blade suction surface

Scrutinizing SP distribution, individual feature could be observed in different model to imply that the flow within LPT passage experiences individual accelerating-decelerating process.In shorter ITD models,the high pressure area near hub decreases while it is larger near casing. In addition to that,low pressure area near hub after throat enlarges.So the radial pressure gradient is larger from outer wall to inner wall. On the blade surfaces of ducts except L-2.2,two separation lines formed under the interaction between radial pressure gradient and passage pressure gradient could be observed. Such phenomenon means that the low speed fluid in boundary layer near walls will migrate towards mid-span height However, in the passage of L-2.2,given the extremely large yaw angle at LPT inlet near outer casing, the separation line on the upper blade surface disappears or becomes very weak. And the limiting streamlines are twisted at about $80 \%$ height,which means the upper passage vortex is disturbed severely by radial pressure gradient.

Comparing with the flow field near suction surface, SF distribution on blade pressure surface is influenced more severelyas shown in Figure 8,especially nearLPT inlet. In shorter ducts,on one hand, the peak SP is obviously lower,and the continuous local high SP area in duct L-3.4 is interrupted to form two isolated high SP regions in duct L-2.2.On the other hand,as what has been mentioned the inlet yaw angle below $80 \%$ passage height is more axial to lead larger negative attack angle. Conse quently in Figure 8,a little area of separation (red dashed line) can be seen near leading edge in duct L-2.2 according to the limi- ting streamlines.What's more,above $80 \%$ height, the trend of angle is different with more circumferential inlet flow in shorter ducts.As the result,the flow is more uneven radially to change local SP distribution on blade surface with the decrease of duct length, and then the boundary layer migrates more to form a clearer separation line at about $8 5 \%$ blade height except L_3.4.

“Clocking Effect” is an important factor for turbine performance,which indicates the difference of relative circumferential position between neighboring nozzle stages that could influence the flow field as well as per formance of downstream turbines. Much research [31-32] has been done to investigate this effect. Especially Schennach et al.[33] discussed the effect of upstream HPT nozzle wake on downstream LPT nozzle after an ITD. Ten models were compared to get the best relative circumferential position between HPT nozzle blade and LPT nozzle blade.In this paper, similar effect is found, which could influence the performance of turbine as well.

![](images/f5af2b3fee5c2f3075efc7d9bcbf3be2082daa732d60b5325b9c87c49c5a85ee.jpg)  
Fig.8SP on blade pressure surface

In Figure 9,Ma contours at mid-span are presented. The relative axial position between swirl blade and nozzle blade is different as the length of duct is shortened. Although the circumferential positions ofblades,aswell as inlet swirl angle remain unchanged, the virtual path for flow is different, including upstream wake. Under various local pressure gradients,dissipation rate differs to form individual strength and range wake (low energy) region in the diffuser duct.In addition to that, the relative circumferential position of wake in different models Would not be definitely the same.In Figure 9, the variations of wake circumferential position at nozzle leading edge caused by shortening of ITD follow evident periodic feature,as the blue dashed line shows: the wake in $\mathrm { ~ L ~ } _ { - } 3 . 4$ locates just in front of nozzle blade leading edge, and closer to suction side; in $\mathrm { ~ L ~ } _ { - } 3$ the wake appears in the blade passage and closer to blade pressure side; however, it remains in the blade passage while locates closer to neighboring blade's suction surface; finally, the wake migrates back near nozzle blade's leading edge again. Although this periodic change of wake position is described according to its distribution at $50 \%$ blade height, it actually applies to the whole passage all the same. Such phenomenon is similar to modifying the relative azimuthal positions between neighboring stator blades, which would be called “Clocking-like Effect” in this pa per. Such effect could change nozzle blade performance surely. In aero-engine,HPT rotor wake sweeps LPT nozzle periodically.However, the“Clocking effect” of HPT blade wake should not be ignored according to literature [34] even through the high speed rotor blades. So the conclusions reported in other papers about “the best relative position of nearby stator blades”should be in the same ITD length and inlet swirl angle,while that advice would be modified when ITD changes.

Under the influence of“Clocking-like Effect”, stagnation and low velocity areas near nozzle blade leading edges are different.FromFigure 9,low Ma areaofL-3 is the severest, with the largest area and lowest speed.

In addition to that, streamlines in the passage are presented as well.Although the “Clocking-like effect”is obvious within the models investigated in this study, flow field in nozzle blade passage is well,without separation or back flow existing.According to Figure 8, the separationarea locatesnearhub inL_2.2,while flowis smooth in other regions. However, Ma isolines in Figure 9 exhibit individual features,under the influence of “Clocking-like Effect”.

In order to estimate the influence of duct length on the loss, total pressure loss coefficient Cpt is defined:

$$
C _ { p t } = \frac { P _ { t } - P _ { t i } } { P _ { t i } }
$$

where $\mathrm { P t }$ is the mass averaged total pressure at different cut planes,Pti is the mass averaged total pressure at duct inlet of individual duct. The larger Cpt represents severer pressure loss.

Figure 1O compares Cpt at LPT nozzle outlet of dif ferent models. Apparently, pressure loss caused by upper passage vortex (region A in Figure 1O) is larger in shorter models.In addition to that,it breaks away from blade wake gradually under larger passage pressure gradient

Obviously,as what has been discussed, the boundary layer on outer casing in shorter ducts is thicker as seen in Figure 5.So the leading edge horse shoe vortex near outer wall would be larger. Finally, the up passage Vortex, which is formed by pressure side branch and adjacent blade's suction side branch of horse shoe vortex,would be larger to cause more pressure loss definitely. What should be analyzed againis the flow yaw angle distribution at nozzle outlet in Figure 6.Under the effect of individual up passage vortex, flow angle at $70 \% 8 0 \%$ passage height differs,as the black dashed line region shows.

![](images/fb98c972980292a11d7e266bd588b18167261aed7d69fdc92009be7c89663116.jpg)  
Fig.9Ma at $50 \%$ passage height

![](images/45b3e3e54560299d5e197bc9644e3553a6224ca1f5ee7bb78495185159d9feaf.jpg)  
Fig.10 Cpt at LPT nozzle outlet

Region C represents upstream wake,while being differentfrom each otherin various models.InL 3.4,itis skewed to across almost the passage from nozzle blade pressure side corner to suction side neighboring blade at mid-heightpassage;inL_3 andL_2.6,itis closerto hub radially,even forms induce vortex with the boundary layer near inner wall to produce more pressure loss, which means wake moves along anti-clockwise direction in shorter models; so in L_2.2，it comes again to mid-height passage.This trend verifies above“Clocking-like effect" again.

An interesting phenomenon appears for total pressure core region B,which is caused by lower passage vortex formed by leading edge horse shoe vortices near hub. Evidently this region presents individual feature as well. However,the transformation is different from that of region A,whichis largerin shortermodels.Actuallyit is the smallest in L_3,while largest in $\mathrm { ~ L ~ } _ { - 2 . 2 }$ with separation.The boundary layer on ITD hub is thinner according to Figure 5.Correspondingly the horse shoe vortices would be weaker in more aggressive ITD models. Such resultis led under the influenceof“Clocking-like Effect" Given upstream swirl wake at nozzle outlet, it is similar to each other between $\mathrm { ~ L ~ } _ { - } 3 . 4$ and $\mathrm { ~ L ~ } _ { - } 2 . 2$ ，while similar to eachother between $\mathrm { ~ L ~ } _ { - } 3$ andL_2.6.Especially inL_2.2, even a part of wake is entrained into the lower passage vortex to increase pressure loss evidently.

Based on Cpt, the pressure loss coefficient of LPT nozzlebladeisdefined:

$$
\Delta C _ { p t } \ = C _ { p t o } - \ C _ { p t i }
$$

where $C _ { p t o }$ is the $C _ { p t }$ at LPT nozzle outlet, and $C _ { p t i }$ is the $C _ { p t }$ at inlet.

In Figure 11, the total pressure loss coefficients of ITD passage (Blue-line-ITD), nozzle blade (Green line-Blade), as well as the total loss ofITD and nozzle blade (Red line-Total),are compared.

The trend of total loss of ITD passage is almost the same with nozzle blade's.And pressure loss within ITD duct is small. This is an interesting result that more aggressive duct would not produce more pressure loss definitelywhenITDshortens.

In addition to that,blade passage and total pressure loss in shorter (more aggressive ITD) model is not larger, for example L-3 VSL-2.8 or L-2.6 VS L-2.4,which is believed affected by Clocking-like Effect. So it is reasonable to design a more aggressive ITD with larger radial offset and shorter length without too much increase ofpressure loss in theLPT nozzle.The relative azimuthal position ofLPT nozzle blade should be modified correspondingly to improve turbine'sperformance further. However, when separation occurs (L-2.2, L-2 and L-1.8 in this paper) the pressure loss is larger definitely.

![](images/295fbbf0eed0829b07714da58d3bdd9871781c6616d3849ff4dee850c5308d9d.jpg)  
Fig.11 Total PressureLoss Coefficient

# Conclusion

Numerical method is applied to investigate the influence of ITDlength onLPT nozzle flow field and performance.Nine models are simulated.However, separation occurs in super-aggressive ITD models shorter than L_2.2,which warns the limitation of length for designers. Four typical models are chosen to be analyzed in detail. According to the discussion,several conclusions and advices are contributed in this paper.

The radial angle distributions at inlet and outlet of nozzle of different models present the same trend to indicate good news for designers.However, at inlet the flow field near walls is affected more severely. The boundary layerat hub is thinner,while it is thicker at casing in shorter models.While at outlet the angle of main flow changes more，which implies that passage vortices are influenced more evidently. The shearing stress development on nozzle suction surface verifies such conclusion.Finally, the pressure loss distribution at nozzle outlet is affected correspondingly.

An interesting phenomenon is “Clocking-like Effect" caused by the change of ITD length,which will influence the attack angle at leading edge of nozzle blade,even lead separation at pressure surface.As the result, pressure loss of blade passage fluctuates periodically according to such“Clocking-like Effect".So itis essential to eliminate this effect as improving ITD through shortening length.

In this paper, downstream nozzle flow field is found to be sensitive to ITD length.And separation is unavoidable as the ITD is too aggressive.More work about flow control to remove separation in such super-aggressive models is being done.

# Acknowledgements

The authors want to thank the National Natural Science Foundation of China for sponsoring the research

described in the current paper (approval serial number: 51406204).

# References

[1]Stevens S.J.,and Fry P.. (1973).Measurements of the Boundary-layer Growth in Annular Diffusers.J.Aircraft, Vol.10.   
[2]Britchford K.M., Manners A. P., McGuirk J. J.,and Stevens S.J..(1993). Measurement and Prediction of Flow in Annular S-Shaped Ducts[J]. Experimental Thermal & Fluid Science,1993,9(2): 197-205.   
[3]Bailey D.W., Britchford K.M., Carrotte J.F., Stevens S. J..(1997).Performance Assessment of an Annular SShaped Duct. Journal of Turbomachinery. Vol. 119, pp.149-156.   
[4]Dominy R. G., Kirkham D. A., and Smith A. D..(1998). Flow Development Through Inter-turbine Diffusers, ASME J. Turbomach. Vol.120,pp.298-304.   
[5]Miller R.J.,MossR.W.,Ainsworth R.W.,and Harvey N. W.. (2003).The Development of Turbine Exit Flow in a Swan-Necked Inter-Stage Diffuser.Proceedings of ASME Turbo Expo 2003，Atlanta,Georgia，USA.GT2003- 38174.   
[6]Axelsson L.U., Johansson T.G.. (2008). Evaluation of the Flow in an Intermediate Turbine Duct at Off-Design Conditions. $2 6 ^ { \mathrm { t h } }$ International Congress Of The Aeronautical Sciences, Anchorage, USA.   
[7]Axelsson L. U., George W. K.. (2008). Spectral Analysis of the Flow in an Intermediate Turbine Duct. Proceedings of ASME Turbo Expo 2008,Berlin, Germany. GT2008- 51340.   
[8]Walln F., Osso C. A., Johansson T. G. (2008). Experimental and Numerical Investigation of an Aggressive Intermediate Turbine Duct:Part 1-Flowfield at Design Inlet Conditions. $2 6 ^ { \mathrm { t h } }$ AIAA Applied Aerodynamics Conference，18-21 August 2008,Honolulu,Hawaii．AIAA 2008-7055.   
[9]Osso C.A.,Wallin F., Johansson T.G. (2008). Experimental and Numerical Investigation of an Aggressive Intermediate Turbine Duct: Part 2-Flow field under Off-Design Inlet Conditions. $2 6 ^ { \mathrm { t h } }$ AIAA Applied Aerodynamics Conference,18 - 21 August 20o8,Honolulu, Hawaii. AIAA 2008-7056.   
[10]Peter B.V., Johansson T.G.,Axelsson L.U.. (2009). Numerical and Experimental Analysis of the Flow in an Aggressive Intermediate Turbine Duct.20o9.Proceedings of ASMETurbo Expo 2009，Orlando，Florida，USA. GT2009-59299   
[11]Davis R.L., Yao J.X., Clark J.P., Stetson G.,Alonso J. J., and Jameson A.. (2002). Unsteady Interaction between a Transonic Turbine Stage and Downstream Components. Proceedings of ASME Turbo Expo 2002,Amsterdam, The Netherlands.GT-2002-30364   
[12]Gottlich E.，Malzacher F.J.,，Heitmeir F.J.，Marn A.. (2005).Adaptation of a Transonic Test Turbine Facility for Experimental Investigation of Aggressive Intermediate Turbine Duct Flows.AIAA Paper No.ISABE-2005- 1132, Munich, Germany.   
[13]Gottlich E.,Marn A.,and Malzacher F.J., Schennach O., and Heitmeir F..(2oo7).Experimental Investigation of the Flow Through an Aggressive Intermediate Turbine Duct Downstream of a Transonic Turbine Stage. Proceedings of the Seventh ETC, Athens, p. 383.   
[14]Gottlich E., Marn A., Malzacher F., Heitmeir,F.. (2009). On Flow Separation in a Super- Aggressive Intermediate Turbine Duct. Proceedings ${ 8 } ^ { \mathrm { t h } }$ European Conference on Turbomachinery Fluid Dynamics and Thermodynamics 2009, Graz, Austria.   
[15]Marn A., Gottlich E.,Malzacher F.,Heitmeir F., Santner C..(2009). Comparison between the Flow through an Aggressive and a Super-aggressive Intermediate Turbine Duct. ISABE-2009-1259,Montreal, Canada.   
[16]Dominy R.G.,Kirkham D.A.(1995). The Influence of Swirl on the Performance of Inter-Turbine Diffusers. VDI Berichte 1186, pp.107-122.   
[17]Dominy R. G.,and Kirkham D.A. (1996). The Influence of Blade Wakes on the Performance of Inter-Turbine Diffusers,ASME J. Turbomach, Vol.118, pp.347-352.   
[18]Marn A., Göttlich E.,Pecnik R., Malzacher F.J., Schennach O.,Pirker H.P..(2007). The Influence of Blade Tip Gap Variation on the Flow Through an Aggressive SShaped Intermediate Turbine Duct Downstream a Transonic Turbine Stage: Part I-Time-Averaged Results.Proceedings of ASME Turbo Expo 2007,Montreal, Canada. GT2007-27405.   
[19]Gottlich E.,Marn A., Pecnik R.,Malzacher F.J., Schennach O., Pirker H. P.. (2007). The Influence of Blade Tip Gap Variation on the Flow Through an Aggressive SShaped Intermediate Turbine Duct Downstream a Transonic Turbine Stage: Part II-Time- Resolved Results and Surface Flow, Proceedings of ASME Turbo Expo 2007, Montreal, Canada. GT2007-28069.   
[20]Sanz W.,Kelterer M., Pecnik R.,Marn A.,and Göttlich E.. (2009). Numerical Investigation of the Effect of Tip Leakage Flow on an Aggressive S-Shaped Intermediate Turbine Duct. Proceedings of ASME Turbo Expo 2009, Orlando,Florida, USA.GT2009-59535.   
[21]Marn A., Gottlich E.,MalzacherF.,Pirker H.P.. (2009). The Effect of Rotor Tip Clearance Size onto the Separation Flow Though a Super- Aggressive S-shaped Intermediate Turbine Duct Downstream of a Transonic Turbine Stage.Proceedings of ASME Turbo Expo 2009, Orlando, Florida, USA.GT2009-59934.   
[22] Lengani D.， Santner C.， Spataro R.， Paradiso B.,and Gottlich E..(2012). Experimental Investigation of the Unsteady Flow Field Downstream of a Counter-Rotating Two-Spool Turbine Rig.Proceedings of ASME Turbo Expo 2012, Copenhagen,Denmark.GT2012-68583.   
[23]Hu S. Z., Zhang Y.F., Zhang X.F.,Vlasic E.. (2011). Influences of Inlet Swirl Distributions on an Inter-Turbine Duct: Part I-Casing Swirl Variation. Proceedings of ASME Turbo Expo 2011,Vancouver,British Columbia, Canada. GT2011-45554.   
[24]Zhang Y.F.,Hu S.Z., Zhang X.F.,Vlasic E.. (2011). Influences of Inlet Swirl Distributions on an Inter-Turbine Duct:Part II-Hub Swirl Variation.Proceedings of ASME Turbo Expo 2011,Vancouver,British Columbia,Canada. GT2011- 45555.   
[25]Zhang X.F.,Hu S. Z.,Benner M., GostelowP.,Vlasic E.. (2010).Experimental and Numerical Study on an Inter-turbine Duct.Proceedings of the ASME 2010 International Mechanical Engineering Congress & Exposition, Vancouver,British Columbia，Canada.IMECE2010- 37322.   
[26] Patel V.C., Sotiropoulos F.. (1997).Longitudinal Curvature Effects in Turbulent Boundary Layers.Prog.Aerospace Sci., Vol.33,pp.1-70.   
[27] Gillis J.C.，Johnston J.P..(1983).Turbulent BoundaryLayer Flow and Structure on a Convex Wall and Its Redevelopment on a Flat Wall. J. Fluid Mech. Vol. 135, pp. 123-153.   
[28]Axelsson L.-U., Osso C.A., Cadrecha D., Johansson T.G.. (2007).Design,Performance Evaluation and Endwall Flow Structure Investigation of an S-Shaped Intermediate Turbine Duct.Proceedings of ASME Turbo Expo 2007, Montreal, Canada. GT2007-27650.   
[29]Axelsson L.-U.,Johansson T.G.(2008). Experimental Investigation of the Time-Averaged Flow in an Intermediate Turbine Duct.Proceedings of ASME Turbo Expo 2008,Berlin, Germany.GT2008-50829.   
[30]Norris G.,Dominy R.G.. (1997).Diffusion Rate Influences on Inter-Turbine Diffusers.ImechE Part A:J.of Power and Energy. Vol. 211, pp.235-242.   
[31]Arnone A.， Marconcini M.，Pacciani R.，Schipani C., Spano E.. (20o2). Numerical Investigation of Airfoil Clocking in a Three-Stage Low-Pressure Turbine.ASME J. Turbomach., Vol.124, pp.61-68.   
[32]Schennach O.，Woisetschläger J.,Fuchs A.,Gottlich E., Marn A.,Pecnik R..(2oo7).Experimental Investigation of Clocking in a One-and-a-Half Stage Transonic Turbine Using Laser Doppler Velocimetry and a Fast Response Aerodynamic Pressure Probe.ASME J.Turbomach., vol. 129,pp.373-381.   
[33]Schennach O.,Pecnik R.,Paradiso B.,Gottlich E.,Marn A.,Woisetschläger J..(2oo8).The Effect of Vane Clocking on the Unsteady Flow Field in a One-and-a-Half Stage Transonic Turbine.ASME J. Turbomach，Vol. 130(03), pp.10-22.