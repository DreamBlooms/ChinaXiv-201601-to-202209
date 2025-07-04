# Optimization Design for SRM based on the Regulation Model of Ampere Density and Coil Space Factor

Peng Sun, Chi Zhang\*, Senior Member, IEEE, Jinhua Chen, Zhe Jiang

Ningbo Institute of Materials Technology& Engineering. Chinese Academy of Sciences, CO 315201,China Zhejiang Key Laboratory ofRobotics and Intellgent Manufacturing Equipment Technology, CO 315201, China E-mail: zhangchi@nimte.ac.cn

Abstract-In the preliminary design process of switched reluctance machine (SRM),adjusting the number of wingding turns or cross-sectional area of conductor to optimize windings designhas dramatic effects on the performances like torque density,efficiency and thermal dissipation and so on.However, the difficulty exists on how to guarantee these performances while optimizing winding design. This paper proposesan analytical optimization design method based on an regulation model of ampere density and coil space factor,which can directly determine the optimal number of winding turns, the crosssectional area of conductor, the ampere densityand the coil space factor.And a MATLAB pre-design program hasbeen developed to provide two design schemes respectively with and without the optimization model.The comparison analysis has been further carried out with finite element analysis (FEA).The simulation results verify that the performances can be highly improved with the proposed optimization model.

# Keywords-Switched reluctance machine,optimization design, ampere density,coil space factorIntroduction

# I．INTRODUCTION

Switched reluctance machine(SRM) has the concentrated windings on the stator but no permanent magnets and windings on the rotor. It is an attractive alternative for electric vehicle(EV) and hybrid electric vehicle (HEV) applications owing to its simple and low cost construction,wide constant power range,low inertia and low inrush current et al[1].

In many applications,it demands for high torque density, high efficiency， high outputpower, excellent thermal dissipation and low cost,which can be improved through comprehensive optimization design of SRM and its optimal control. Because the excitation and unique inductance profile is closely determined by the rotor position, the mathematical model of SRMis highly nonlinear and the flux linkage is easy to saturated at the poles,which makes it harder to design and adjust the geometric dimensions to meet the design specifications.Some works focus on the comprehensive design procedure and program for common SRM design, which allows an efficient and fast design by understanding the influence of relevant design parameters.Berker Bilgin et al.

\*Corresponding author: Chi Zhang is with the Ningbo Institute of Materials Technology & Engineering,Chinese Academy of Sciences and Zhejiang Key Laboratory of Robotics and Intelligent Manufacturing Equipment Technology，Zhejiang 315201 China (Research Professor email: zhangchi@nimte.ac.cn).Chi Zhang and Peng Sun contributed equally.

have proposed a MATLAB based design tool to calculate the geometry with the conventional magnetic circuit method and automatically draws and simulates the SRM model in FEA software without considering the optimization design[2].And some works focus on the geometry and configuration optimization to improve the performances like efficiency, torque density and power output et al.Kazuhiro Ohyama et al. have studied the approach to improve the efficiency through designing the cross sections and axial shapes of rotor and stator cores using the magnetic field analysis with 2D and 3D finite element methods[3].J.Hur et al.have implemented the flux barriers to improve the torque density[4].Anas Labak et al.have proposed a design and analysis method of a novel axial-flux SRM, in which the detailed procedures of deriving the output power equation as a function of the motor dimensions and parameters and an exclusive pole-shape design are presented. It focuses on the structural design to improve the performance[5]. Dong-Hee Lee et al. have proposed the first and second optimization process to reduce the torque ripple and improve the output torque through optimizing the air gap which is considered to be a function of the rotor position[6].

However, the empirical values are generally needed to guide and amend the design process which always needs abundant design experiences. One of the crucial design procedure is to design and optimize the winding,i.e.,the number of winding turns, slot fill factor,ampere density and wire diameter. And winding design and optimization also has great effects on the SRM performances[7-9]. Therefore, this paper mainly focuses on the winding design and optimization issue,and proposes a optimization regulation model based on the ampere density and coil space factor optimization,which is actually a winding design and optimization approach, aiming at improving the torque density and the output power as well as the efficiency through choosing optimal number of winding turns,wire diameter,ampere density and coil space factor.An comparison study with magnetic circuit method and FEM simulation also has been carried out.It verifies that the proposed optimization model isnot only advantageous for improvement of torque density,but also for power output and efficiency.

# II.OPTIMIZATIONREGULATIONMODEL

Ampere density and coil space factor are two crucial factors that must be comprehensively investigatedand designed in certain appropriate intervals.It means that ,on the other hand, the ampere density and coil space factor are nonunique.There are various combinations of these two factors to meet the same design specifications and requirements. Therefore, guessing that it exists an optimal point, the problem is simply how to determine it.However,actually,whether there is an optimal point or not, it depends on the optimizable range，which is further determined by the preliminary structural design of SRM. The ampere density and coil space factor can be expressed as

$$
\begin{array} { c } { { J = \displaystyle \frac { I } { S _ { a } } = \frac { \pi D _ { a } A } { q } \frac { 1 } { N _ { p h } S _ { a } } } } \\ { { k _ { s } = \displaystyle \frac { S _ { c u } } { S _ { W } } = \frac { 1 } { 2 S _ { W } } N _ { p h } S _ { a } } } \end{array}
$$

where $J$ is the ampere density, $k _ { s }$ is the coil space factor, $N _ { p h }$ is the windings turns in series of each phase, $D _ { a }$ is the rotor outside diameter, $A$ is the current per unit length, $q$ is the number of phase, $I$ is the effective winding current, $S _ { w }$ is the stator yoke window area, $S _ { c u }$ is the net conductor crosssectional area of eachslotand $S _ { a }$ is the cross area of conductor. Corresponding definitions are illustrated in Figure 1.And the relationship between the ampere density and coil space factor is shown as Figure 2.

![](images/70c9c7b5923606cd7948542f58f1c4d93f2ce5f729d4218dcc9f9c8c4bdde781.jpg)  
Figure1Definitions of ampere density and coil space factor

![](images/8c23dd5ba9ddc770d71c8d16581a8ddf90f499687054a0e20b6ca3aa85bdabce.jpg)  
Figure 2 Relationship between ampere density and coil space factor

From(1) and (2),it is obvious that the ampere density and coil space factor can be regulated by changing the number of winding turns and cross-sectional area of conductor assuming that $D _ { a } , A ,$ $q$ and $S _ { w }$ change little and can approximately be considered to be constant.It hence yields that

$$
J \cdot k _ { s } = \frac { \pi D _ { a } A } { 2 q S _ { W } } = \mathrm { C o n s t }
$$

Only when the intervals of $J$ and $k _ { s }$ having overlapping section on the curve，there is an optimal point. And the overlapping intervals is the so called optimizable range.More detail discussion of the optimizable range can be found in reference[10]. Once the optimization possibility has been discussed,another problem is how to find the optimal point. So,an optimized regulation model has been proposed,which adapts the electromagnetic torque $T _ { e m }$ as the optimization objective function.According to the co-energy theory[11], the electromagnetic torque can be calculated with co-energy $W ^ { \prime }$ ：

$$
T _ { e m } = \frac { q N _ { r } } { 2 \pi } { W } ^ { ' }
$$

where $N _ { r }$ is the number of rotor poles.Figures 3 shows the magnetization curves at aligned position $\theta _ { a }$ and unaligned position $\theta _ { u }$ , in which the shaded area represents the co-energy, where $\boldsymbol { I } _ { m _ { m _ { } } } ^ { * }$ is the ideal square wave peak current, $i _ { s }$ is the critical saturation current for $\psi _ { a } \left( \theta _ { a } , i \right)$ ， $L _ { \phantom { } _ { u } }$ is the inductance at $\theta _ { u }$ position, $\boldsymbol { L } _ { \boldsymbol { a o } }$ is the inductance at $\theta _ { a }$ position when $i < i _ { s }$ ·

![](images/218ce83157aa0c24b9ba74ba72d4b5d402884909709a33942ef76dcf35d685e1.jpg)  
Figure3Magnetization curves at aligned ( $\theta _ { a } \ )$ and unaligned ( $\left( \theta _ { u } \right)$ positions. Shown as Figure 3,the co-energy can be expressed as

$$
\begin{array} { c l c r } { { W ^ { ' } = \displaystyle { \int _ { 0 } ^ { I _ { m } ^ { * } } } \Bigl [ \psi _ { a } \left( \theta _ { a } , i \right) - \psi _ { u } \left( \theta _ { u } , i \right) \Bigr ] \mathrm { d } i } } \\ { { } } & { { } } \\ { { } } & { { } } \\ { { } } & { { } } & { { \approx S _ { O P M N } - S _ { O P Q S } - S _ { S Q M } } } \\ { { } } & { { } } & { { } } \\ { { } } & { { } } & { { = { \displaystyle { \frac { 1 } { 2 } } } \psi _ { m } ^ { * } \left( I _ { m } ^ { * } - i _ { s } \right) - { \displaystyle { \frac { 1 } { 2 } } } \psi _ { u m } ^ { * } I _ { m } ^ { * } + { \displaystyle { \frac { 1 } { 2 } } } \psi _ { s } I _ { m } ^ { * } } } \end{array}
$$

On the other hand, the co-energy can also be expressed as a function of the number of winding turns in series of each phase [10, 12],

$$
\begin{array} { r } { W ^ { ' } = \left\{ \begin{array} { l l } { P _ { 1 } \displaystyle \frac { 1 } { N _ { p h } } + P _ { 2 } \displaystyle \frac { 1 } { N _ { p h } ^ { ~ 3 } } + P _ { 3 } \quad \mathrm { ~ w h e n ~ } ~ \theta _ { o n } \in \left[ \theta _ { 0 } , \theta _ { u } \right] } \\ { P _ { 4 } \displaystyle \frac { 1 } { N _ { p h } } + P _ { 5 } \quad } & { \mathrm { ~ w h e n ~ } ~ \theta _ { o n } \in \left[ \theta _ { u } , \theta _ { 1 } \right] } \end{array} \right. } \end{array}
$$

where $P _ { I } { \sim } P _ { 5 }$ are constants which are related to the flux and inductance at special rotor positions[1O]. Thus,ultimately, the electromagnetic torque $T _ { e m }$ can be expressed in the form of $N _ { p h }$ as follows,

$$
T _ { \mathrm { e m } } = \left\{ \begin{array} { l l } { \displaystyle \frac { q N _ { r } } { 2 \pi } \Biggl ( P _ { 1 } \frac { 1 } { N _ { p h } } + P _ { 2 } \frac { 1 } { N _ { p h } ^ { \quad 3 } } + P _ { 3 } \Biggr ) } & { \mathrm { w h e n ~ } \theta _ { o n } \in \left[ \theta _ { 0 } , \theta _ { u } \right] } \\ { \displaystyle \frac { q N _ { r } } { 2 \pi } \Biggl ( P _ { 4 } \frac { 1 } { N _ { p h } } + P _ { 5 } } & { \Biggl ) } & { \mathrm { w h e n ~ } \theta _ { o n } \in \left[ \theta _ { u } , \theta _ { 1 } \right] } \end{array} \right.
$$

The practical task of the model is to determine the optimal ampere density $J$ and coil space factor $k _ { s }$ by simply regulating $S _ { a }$ and $N _ { p h }$ in the optimization range,meanwhile guaranteeing providing optimal electromagnetic torque.Therefore， the optimized regulation model canbe described as

$$
\left\{ \begin{array} { l l } { f i n d \left( N _ { p h } , S _ { a } \right) } \\ { \left( T _ { \mathrm { e m } } \right) _ { \mathrm { m a x } } = \operatorname* { m a x } \left[ T _ { e m } \left( N _ { p h } , S _ { a } \right) \right] } \\ { J _ { \operatorname* { m i n } } \leq J \left( N _ { p h } , S _ { a } \right) \leq J _ { \operatorname* { m a x } } } \\ { k _ { s \operatorname* { m i n } } \leq k _ { s } \left( N _ { p h } , S _ { a } \right) \leq k _ { s \operatorname* { m a x } } } \end{array} \right.
$$

There are also some constraint conditions as follows,

$$
\begin{array} { c } { { \displaystyle \left( T _ { \mathrm { e m } } \right) _ { \mathrm { m a x } } > T _ { \mathrm { e m N } } } } \\ { { \displaystyle \left( S _ { a } N _ { p h } \right) _ { \mathrm { m i n } } \le S _ { a } N _ { p h } \le \left( S _ { a } N _ { p h } \right) _ { \mathrm { m a x } } } } \\ { { \displaystyle J = \frac { I } { S _ { a } } = \frac { I _ { m } ^ { * } / \sqrt { 2 } } { S _ { a } } } } \end{array}
$$

Thus,the optimization regulation model can ultimately be expressed as a standard nonlinear optimization model shown as

$$
\begin{array} { r l } & { [ ( T _ { \mathrm { e n } } ) _ { \mathrm { m a x } } = \mathrm { m a x } [ T _ { \mathrm { e n } } ( N _ { p h } ) ]  } \\ & {  J \cdot k _ { s } = \pi D _ { a } A / 2 q S _ { w }  } \\ & {  J = I _ { n } ^ { * } \sqrt { \sqrt { 2 } } { S } _ { a }  } \\ & {  \{ ( T _ { \mathrm { e n } } ) _ { \mathrm { m a x } } > T _ { \mathrm { e n x } }   } \\ & {  ( S _ { a } { N _ { p h } } ) _ { \mathrm { m i n } } \leq { S } _ { a } { N _ { p h } } \leq ( S _ { a } { N _ { p h } } ) _ { \mathrm { m a x } }  } \\ & {  [ J _ { \mathrm { m i n } } \leq J \leq J _ { \mathrm { m a x } }   } \\ & {   { k _ { \mathrm { s m i n } } } \leq k _ { s } \leq k _ { \mathrm { m a x } }  } \end{array}
$$

This is a standard nonlinear optimization model,which can be solved with various numerical computing methods like the Kuhn-Tucker (K-T) equation method and the Sequential Quadratic Programming (SQP） methods. There are also corresponding commands in MATLAB.

# III.OPTIMIZATION DESIGN PROGRAM WITHMATLAB

In order to verify the feasibility of the optimization regulation model,a pre-design program has been completed with MATLAB， which utilizes the conventional design approach and procedure to determine the initial geometric dimensions[13,14]. It provides two preliminary designs,one of which is with the optimization regulation model,and the other is without the model. Figure 4 shows the program flow chart with the optimization regulation model. And the one with no optimization is the same with the procedure shown as in the dashed box.

Correspondingpreliminary designspecificationsand parameters without the optimization regulation model are listed in TABLE I. Compared with the design without the optimizationregulation model, thedesignedstructural parameters with the model are the same excepting the winding and electromagnetic parameters as shown in TABLE II.

![](images/fbc89698270a3af60000b20ecf39d08953a41804d908c87b22c406c48840be33.jpg)  
Figure 4MATLAB programflowchart

TABLE IDesign specifications and parameters   

<html><body><table><tr><td colspan="4">Design Specifications</td></tr><tr><td>Number of phases</td><td>4</td><td> Nnumberof stator</td><td>8/6</td></tr><tr><td>Rated voltage</td><td>380VAC</td><td>Rated speed</td><td>1500rpm</td></tr><tr><td>Rated output power</td><td>11KW</td><td>Rated efficiency</td><td>88%</td></tr><tr><td colspan="4">Design Parameters</td></tr><tr><td>Turn-on angle</td><td>-2.35deg</td><td>Turn-off angle</td><td>18.5deg</td></tr><tr><td>Rotor inner diameter</td><td>59.5mm</td><td>Statorouter</td><td>210mm</td></tr><tr><td>Rotor yoke height</td><td>16.60mm</td><td>Core lamination length</td><td>178.5mm</td></tr><tr><td>Stator pole width</td><td>21.83mm</td><td>Stator pole arc</td><td>21deg</td></tr><tr><td>Rotor pole width</td><td>23.72mm</td><td>Rotor pole arc</td><td>23deg</td></tr><tr><td>Air gap length</td><td>0.4mm</td><td>Rotor outer diameter</td><td>119mm</td></tr><tr><td>Stator slot depth</td><td>30.19mm</td><td>Stator yoke height</td><td>14.19mm</td></tr><tr><td>Stator pole pitch</td><td>62.31mm</td><td></td><td></td></tr></table></body></html>

TABLE II Theoretical performances comparison   

<html><body><table><tr><td colspan="3">Effects of the optimization regulation model</td></tr><tr><td>Nominal</td><td>Before Optimized</td><td>After Optimized</td></tr><tr><td>Winding turns in series of each phase</td><td>124</td><td>116</td></tr><tr><td>Crnsuctor( of m2)</td><td>3.9408</td><td>4.9087</td></tr><tr><td>Wire diameter(mm)</td><td>2.24</td><td>2.5</td></tr><tr><td>Ampere density(A/mm2)</td><td>5.53</td><td>4.79</td></tr><tr><td>Coil space factor</td><td>0.5277</td><td>0.6051</td></tr><tr><td>Rated electromagnetic torque(N.m)</td><td>75.02</td><td>99.19</td></tr></table></body></html>

The optimizable range is shown in Figure 5. The coil space factor $k _ { s }$ and the ampere density $J$ are expected to be designed in an certain appropriate interval, whichis $k _ { s } \in [ 0 . 5 , 0 . 7 ]$ and $J \in [ 3 . 5 , 5 . 5 ]$ ．After optimized, the coil space factoris $k _ { s } { = } 0 . 6 0 5 1$ ，and the ampere densityis $J { = } 4 . 7 9 \mathrm { A } / \mathrm { m m } ^ { 2 }$ It means that both $k _ { s }$ and $J$ are in the optimizable range. And Figure 6 shows the theoretical relationship between the electromagnetic torque and the number of winding turns.It states that the number of winding turns in series of each phase $N _ { p h }$ should be in the interval of $N _ { p h } \in [ 1 1 6 , 1 5 6 ]$ when the cross-sectional area of conductor is $S _ { a } { = } 4 . 9 0 8 7 \mathrm { m m } ^ { 2 }$ ，and the corresponding electromagnetic torque theoretically varies from $7 5 . 0 2 \mathrm { N } . \mathrm { m }$ to $1 0 0 . 5 \mathrm { N . m }$ as shown in Figure 6. It means that the theoretical value of optimal electromagnetic torqueshould between $7 5 . 0 2 \mathrm { N } . \mathrm { m }$ and $1 0 0 . 5 \mathrm { N . m }$ ，and TABLE I shows that the theoretical optimal electromagnetictorqueis $9 9 . 1 9 \mathrm { N . m }$ ，whichisinthe optimizable range.

![](images/37bb9bc2efc3007f80672ba33e62f9b021133e07f935b90cd84710da0d4e4d94.jpg)  
Figure 5 Ampere density vs.coil space factor (Optimizable range)

![](images/37756649fd662f75fa10ea91876ed86fb8cd86d0384390fb3b84266fac8e7437.jpg)  
Figure 6 Electromagnetic torque vs.the number of winding turns

It states that the optimization regulation model functions well.It can effectively search an theoretical optimal point in the optimizable range.Before optimized, the designed rated electromagnetic torque is theoretically about $7 5 . 0 2 \mathrm { N } . \mathrm { m }$ ，while after optimized, it increasesto 99.19N.m, which can theoretically improved by $3 2 . 2 2 \%$ ：

# IV．COMPARISON ANALYSIS

And a performances comparison analysis has been carried out with ANSYS Maxwell. The purpose is merely comparatively study the effects of the optimization regulation model on theperformancesof SRM. Thewinding configuration here is the conventional type of long magnetic circuit loop shown as Figure 7， of which the corresponding excitationsequenceA-A&B-B-B&C-C-C&D-D-D&A.

Figure 8 shows the finite element mesh result, in which the maximum elements length of the coils is $9 . 0 2 \mathrm { m m }$ and $9 . 1 \mathrm { m m }$ of stator and rotor. The maximum surface deviation is $0 . 1 0 5 \mathrm { m m }$ ,and the deviation angle is 15deg.

![](images/a39d0f71b7086c6038fdd96c60d42f57468705e02e0d4fca96be64577f61daa9.jpg)  
Figure 7Winding configuration and excitation phase sequence

![](images/74ff4d63cf57fd9d2f2d21dfbf7553fb1f3e320f1f258d91f16232461170d108.jpg)  
Figure 8Finite element mesh

Figure $9 ( \mathrm { a } ) \mathrm { \sim } ( \mathrm { c } )$ and Figure $1 0 ( \mathrm { a } ) \mathrm { \sim } ( \mathrm { c } )$ respectively show the flux linkage and density distribution at certain special rotor positions including the partial overlapped, aligned and unaligned positions with respect to the pole of phase-A. Specifically,when the stator pole and the rotor overlapping, the flux density at corresponding overlapped part is relatively larger than thatataligned or unaligned positions.And TABLE III lists the average flux linkage and flux density comparison.

TABLE II Flux linkage and flux density comparison   

<html><body><table><tr><td>Nominal</td><td>Before Optimized</td><td>After Optimized</td></tr><tr><td>Flux linkage(Wb)</td><td>0.682204</td><td>0.640847</td></tr><tr><td>Stator-pole flux density(T)</td><td>1.64944</td><td>1.65630</td></tr><tr><td>Stator-yoke flux density(T)</td><td>1.14319</td><td>1.14795</td></tr><tr><td>Rotor-pole flux density(T)</td><td>1.63482</td><td>1.64162</td></tr><tr><td>Rotor-yoke flux density(T)</td><td>0.977221</td><td>0.981288</td></tr></table></body></html>

![](images/eaee74bcffb2dc72905579234800e93b02d7079172dd16c1a8c572d417d282a3.jpg)  
Figure1O Flux density distribution( $1 5 0 0 \mathrm { r p m } )$

TABLE IV lists the theoretical performances comparison. It shows that the performances has indeed improved after optimized.

TABLE IV Simulation performances comparison   

<html><body><table><tr><td colspan="3">Performances comparison</td></tr><tr><td>Nominal</td><td>Before optimized</td><td>After optimized</td></tr><tr><td>Rated speed(rpm)</td><td>1761</td><td>1884</td></tr><tr><td>Rated output torque(N.m)</td><td>69.35</td><td>69.97</td></tr><tr><td>500rt m(N.m )t</td><td>91.87</td><td>103.06</td></tr><tr><td>Estimated start torque(N.m)</td><td>540.85</td><td>669.45</td></tr><tr><td>Rated electromagnetic power(KW)</td><td>13.86</td><td>14.84</td></tr><tr><td>Rated output power(KW)</td><td>12.79</td><td>13.81</td></tr><tr><td> Maximuw output</td><td>16.91</td><td>18.41</td></tr><tr><td>Winding copper loss(W)</td><td>688.10</td><td>597.01</td></tr><tr><td>Total loss(W)</td><td>1074.55</td><td>1026.65</td></tr><tr><td>Efficiency(%)</td><td>92.25</td><td>93.08</td></tr></table></body></html>

Figure 11 shows the simulation output torque curve at different speed,which states that the output torque has been highly improved. When applied the same rated load toque of 70N.m,it is obvious that after optimized, the steady speed increases from 176lrpm to $1 8 8 4 \mathrm { r p m }$ ，which means that the operation range has been improved with the optimization regulationmodel. Correspondingly， theratedoutput mechanical torque increased from $6 9 . 3 5 \mathrm { N . m }$ to $6 9 . 9 7 \mathrm { N . m }$ Besides,before optimized, the output torque is 91.87N.m at

$1 5 0 0 \mathrm { r p m }$ ，while after optimized,it increases to 103.06N.m, which is improved by $12 . 1 8 \%$

The simulation output power also has been improved shown as Figure 12. The output power at $1 5 0 0 \mathrm { r p m }$ is about 14.34KW before optimized and 16.09KW after optimized, which has been increased by $12 . 2 \%$

Shown as Figure 13,it states that under the speed of $1 5 0 0 \mathrm { r p m }$ ，the efficiency is not significantly improved,while above the rated speed it obviously increases compared with the circumstance before optimized.

![](images/e105426fa28923eef19b6f36cf14727aa3e9dda29f9f72248ecb28b150e94f34.jpg)  
Figure 11 Output torque comparison with various speed

![](images/67ff99a53fc8c21020c584587decfb25e47abeb758a962cab09ddee8bd5c9784.jpg)  
Figure l2 Output power comparison with various speed

![](images/ac493d8b3cfd11a82d68ba8417d1f698e8bfa987b7d1fec28e3b6505a243e01c.jpg)  
Figure 13Efficiency comparisonwith various speed

# V．CONCLUSION

This paper proposes a regulation model of ampere density and coil space factor to optimize the winding design of SRM. The purpose is to improve the performances through choosing the optimal number of winding turns, the cross-sectional area of conductor,which in turn leads to the optimal ampere density and coil space factor.It ultimately verifies that,after optimized, the ampere density is effectively decreased,which is beneficial for reducing the windings loss and increasing the efficiency. And the coil space factor is appropriately increased. which leads to the improvement of thermal performance of SRM on the other hand.Besides, not only the torque density, but also the power density and efficiency performances can be further improved. The simulation indicates that the average output power can be improved by $12 . 2 \%$ with the proposed optimization model and the rated efficiency increases from $9 2 . 2 5 \%$ to $9 3 . 0 8 \%$ ·

The future work is torque ripple optimization and noise suppression through optimal design of SRM,and thermal performance is still remaining to be analyzed.

# ACKNOWLEDGEMENT

This research is supported by the Science and Technology Innovation Group of Ningbo(Grant No.2012B82005) and One

Hundred Talents Program of the Chinese Academy of Sciences, NaturalScienceFoundationof Ningbo(No. 2015A610146 & No.2015A610154)，Major Scientific and Technological Projects of Ningbo(No. 2013B10042& No.2013B10043).

# REFERENCES

[1]K.M.Rahman,B.Fahimi,G.Suresh,A.V.Rajarathnam,and M. Ehsani,"Advantages of switched reluctance motor applications to EV and HEV:design and control issues," Industry Applications,IEEE Transactions on,vol.36,pp.111-121,2000.   
[2] B.Bilgin and M. Krishnamurthy,"An FEA/MATLAB based machine design tool for switched reluctance motors," in Vehicle Power and Propulsion Conference (VPPC),2011 IEEE,2011, pp.1-6.   
[3]K.Ohyama,Y.Nakazawa,K.Nozuka,H.Fujii,H. Uehara,and Y. Hyakutate,"Design of high efficient switched reluctance motor for electric vehicle,"in Industrial Electronics Society,IECON2013-39th Annual Conference of the IEEE,2013,pp.7325-7330.   
[4]J. Hur, G.H. Kang, J. Y.Lee,J.P. Hong,and B. K. Lee, "Design and optimization of high torque,low ripple switched reluctance motor with flux barrier for direct drive,"in Industry Applications Conference,2004. 39thIAS Annual Meeting. Conference Record of the 2004 IEEE,2004, p. 407 Vol.1.   
[5] A.Labak and N.C.Kar,"Designing and Prototyping a Novel FivePhase Pancake-Shaped Axial-Flux SRM for Electric Vehicle ApplicationThrough DynamicFEA Incorporating Flux-Tube Modeling," Industry Applications,IEEE Transactions on,vol.49,pp. 1276-1288,2013.   
[6] L.Dong-Hee,P.Trung Hieu,and A. Jin-Woo,"Design and Operation Characteristics of Four-Two Pole High-Speed SRM for Torque Ripple Reduction," Industrial Electronics,IEEE Transactionson,vol.60,pp. 3637-3643,2013.   
[7] C.Laudensack and D.Gerling,"Vibration and noise analyses of canned switched reluctance machines with different winding topologies," in AFRICON,2013,2013,pp.1-5.   
[8] C.Laudensack,Q.Yu,and D.Gerling,"Analysis of different winding topologies for canned switched reluctance machines,"in Electrical Machines (ICEM),2012 XXth International Conference on,2012,pp. 66-72.   
[9]H.J. Brauer,B.Burkhart,and R.W.De Doncker,"Comprehensive electromagnetic design procedure for switched reluctance machines," in Power Electronics,Machines and Drives (PEMD 2012)，6th IET International Conference on,2012, pp. 1-6.   
[10] P.Sun, C.Zhang,J.Chen,and F.Z.Ningbo,"Research on optimization regulation method of ampere density and coil space factor for switched reluctance machine,"in Electrical Machines and Systems (ICEMS), 2014 17th International Conference on,2014,pp.2637-2641.   
[11] T.Miller,"Optimal design of switched reluctance motors," Industrial Electronics,IEEE Transactions on,vol.49,pp.15-27,2002.   
[12]T.J.E.Miller and M.McGilp,"Nonlinear theory of the switched reluctance motor for rapid computer-aided design,"Electric Power Applications,IEE Proceedings B,vol.137,pp.337-347,1990.   
[13] P.Rafajdus,P.Dubravka,A.Peniak,J. Saitz,and L. Szabo,"Design procedure of switched reluctance motor used for electric car drive," in Power Electronics，Electrical Drives，Automation and Motion (SPEEDAM),2014 International Symposium on,2014,pp.112-117.   
[14] M.N.Anwar, I. Hussain,and A.V.Radun,"A comprehensive design methodology forswitched reluctancemachines,"inIndustry Applications Conference,20oo.Conference Record of the 20oo IEEE, 2000,pp.63-70 vol.1.