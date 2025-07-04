# Mechanical design and error prediction of a manipulator system applied in nuclear fusion environment

Shanshuang Shi, Huapeng Wu   
Laboratory of Intelligent Machines, Lappeenranta University of Technology, Lappeenranta, Finland Yuntao Song Institute of Plasma Physics, Chinese Academy of Sciences,Hefei, China,and Heikki Handroos   
Laboratory of Intelligent Machines,Lappeenranta University of Technology, Lappeenranta,Finland

# Abstract:

Purpose - The purpose of this paper is to develop a serial redundant manipulator system applied in nuclear fusion environment. It willallow remote inspection and maintenance of plasma facing components in the vacuum vessel of fusion device without breaking down the ultra-high vacuum condition during physical experiments.

Design/methodology/approach -Firstly,considering the dynamic sealing of actuators to avoid polluting the vacuum condition inside fusion reactor,the mechanical design ofrobot system has been introduced.The redundant manipulator system has 11 degreeof freedoms in total with an identical modular design.Besides,to improve the position accuracy, an error prediction model has been built based on the experimental study and back-propagation neural network (BPNN) algorithm.

Findings-Currently,the implementation of the manipulatorsystem has been successfully finished in both atmosphere and vacuum condition. The validation of BPNN model shown an acceptable prediction accuracy $( 9 4 \% { \sim } 9 8 \% )$ compared with the real measurement.

Originality/value-This is aspecial robot system whichis practicallyused in anuclear fusion device in China.Its design, mechanism and eror prediction strategy have great reference values to the similar robots in vacuumand temperature applications.

Keywords: EAMA robot; experimental study; BP neural network; Error prediction;

# 1.Introduction

Experimental Advanced SuperconductingTokamak (EAST) is the world's first fully superconducting tokamak fusion device with non-circular cross-section which was built in China (Wan et al., 2OO6). In recent years, with the increasingdeviceperformanceandexperimental parameters,EAST tokamak has made a series of important research results and scientific discoveries (Li et al., 2013; Wang et al.,2O14).However, EAST inner components will also be facing increasinglytough operating environment with huge heat flux as the plasma current during discharges becoming higher and higher.It leads the plasma facing components (PFCs) easily to be damaged, in which case the effective running time cannot be guaranteed (Yang et al., 2016; Li et al., 2016). Therefore, it is essential for the timely maintenance based on the condition of damaged internal components in the experimental period.

The AIA robot is a related application which was specially developed for ITER fusion reactor (Shimomura et al.，1999）and demonstrated in Tore-supra tokamak device (Gargiulo et al.,2Oo9).Itis able to inspect the invessel components under $1 2 0 ^ { \circ } \mathrm { C }$ and $1 0 ^ { - 6 }$ Pa condition with a $2 0 0 \ \mathrm { \ m m }$ maximum position error due to the flexibility of the 1O-meter cantilever structure (Perrot et al.，2012). The poor position accuracy means that the robot can only run in the middle of the vacuum vessel rather than close-range operate or even touch the tokamak wall from a security point of view.

For the purpose of real-time detection and rapid repairing of the damaged internal components during plasma discharges,EAST articulated maintenance arm (EAMA） system has been developed since 2O13.It will allow remote inspection and simple repair of plasma facing components (PFCs) in EAST vacuum vessel (VV) without breaking down the ultra-high vacuum condition $\mathrm { ( { \sim } 1 0 ^ { - 5 } P a ) }$ .Due to its long-reach mechanisms with a weightmore than $1 0 0 \mathrm { k g }$ ,similar with the AIA robot, the gravity effect will cause huge flexible deformation,which is unacceptable for running inside a narrow and complexshaped space asEASTVV.Figure1 shows the cantilever structure of fully assembled EAMA robot without endeffector and the finite element simulation results for the position errors.

![](images/591be695de2a4f7c0c83c6422aa51663dd754b86a043fa30f7df84e70aa4f659.jpg)  
Figure1CantileverstructureofEAMArobot   
Note:(a)ThefullyassembledEAMArobot wihoutend-effctor; (b)Thefiniteelementsimulatioresultsforthepositionrorsof different links.

Elastic deformations due to gravity will cause robot trajectory planning to be quite a complicated issue, especially for serial long-reach manipulators.Error prediction strategy should always be studied in advance if high accuracy was required. In fact, research on the robotic flexibility has become a matter of great concern in recent years because of the pursuit of high accuracy and reliability. Normally,two kinds of methods could be considered to build the flexible model for error predicting. On one hand, the mathematic model of flexible multibody dynamics can be derived from classical mechanics theories such as Newton-Euler formulation, Lagrange formulation,etc.Then either the finite element method (FEM) or assumed modes method (AMM) can be used to truncate the dynamic formulations for rapid solution with an appropriate accuracy (Dwivedy and Eberhard, 2006). On the other hand, for some complex systems with several uncertain coupling factors,the flexible model can be identified using some computing algorithm without considering the complicated mechanical model and highly nonlinear formulations, such as fuzzy algorithm (Schiavo and Luciano，2O01)，genetic algorithm (Chang，2007), artificial neural network approach (Liu, 2O12),etc.

For the case study of EAMA manipulator， the mathematicalmodellingusingclassical mechanics theories is difficult to obtain high accuracy and eficiency owing to two reasons.Firstly, the complicated mechanism, transmission chain and multi links make the accurately flexible modelling to be quite a difficult issue. Secondly, the dynamic formulations with high nonlinearity is not necessary as the manipulator speed is extremely low(less than O.5 degree per second)，which means that the dynamic behaviors are slight enough compared with the gravity effect.Therefore,static modelling can be a better choice for error predicting with a relatively high accuracy.

In this paper, the conceptual design of the manipulator system was firstly introduced. Then,an experimental study was deployed to measure the errors of EAMA prototype assembled with different loads through a loaddeflection platform.Based on the experimental data,a static error prediction model was built and trained by utilizingback-propagation neuralnetwork(BPNN) algorithm.The results show an acceptable prediction accuracy while around $5 \%$ predicting error compared with the real measurement. Furthermore, the mathematic formulation for static loads of robot joints in arbitrary position were derived. The calculated joint loads can be treated as the input of the trained BPNN model to predict the robot errors in arbitrary positions and postures without any experiments and measurements in future.

# 2. Manipulator system design

EAMA system consists of a highly redundant manipulator: one mobile base,5 serial arms and an end-effector(CCD cameras,gripper, etc.) for dedicated functional operations. Besides,a storage cask facility has been developed to maintain the equivalent vacuum environment for the manipulator before docking with EAST vacuum vessel. Figure 2 shows an overall schematic view of EAMA system and the robot specifications is given in Table 1(Shi et al., 2016).

Table1 Specifications ofEAMA manipulator   

<html><body><table><tr><td>Vacuum</td><td>10-5 Pa to 1 atm</td></tr><tr><td>Temperature</td><td>Running:80 oC; baking:120 C</td></tr><tr><td>Workspace</td><td>In-vessel: R=1920,a=550 mm</td></tr><tr><td>DOFs</td><td>1(base)+7(arm) +end-effector</td></tr><tr><td>Payload</td><td>25kg</td></tr><tr><td>Dimension</td><td>Radius:160mm,length: 8.8m</td></tr><tr><td>Weight</td><td><100 kg (arm)</td></tr><tr><td>Function</td><td>Inspection and simple repair</td></tr></table></body></html>

![](images/908d86593913b6867ba8ff4403928ec501dfa1391256a4e605a6ea7a734a05b1.jpg)  
Figure2LayoutofEAMAsystem

For the manipulator arms,an identical modular design with a parallelogram mechanism has been adopted for all of the 5 arm segments. Each segment can provide the motions of both rotation and elevation by integrating yaw and pitch joints inside one modular arm segment. As shown in Figure 3, the parallelogram structure is composed of two clevis (yaw joints),horizontal rods,arm tube and diagonal rod (pitch actuator).The five-bar mechanism can produce huge reduction ratio and withstand strong torques generated from the cantilever armsand the gravity effects.Besides,the axis of yaw joint will be always vertical owing to the motion characteristics of the parallelogram structure.

![](images/cd59aaddfcdb976c0d6f4bd651e8cc7342107d541f67b6ede94ddec8c0d4a32c.jpg)  
Figure 3Modular design of EAMA robotarms

Note: Five segments with identical principle design, the $1 ^ { \mathrm { s t } }$ to $3 ^ { \mathrm { r d } }$ segments have only rotation motions by using rigid rods instead of elevation actuators; the $4 ^ { \mathrm { t h } }$ and $5 ^ { \mathrm { t h } }$ segments have both rotation and elevation motions.

The motion actuators are placed inside robot tubes: rotation actuator connected to the tube while elevation actuator located in diagonal of the parallelogram. To avoid polluting the ultra-high vacuum condition inside EAST vacuumvessel, themotionactuatorswiththe consideration of dynamic sealing have been developed. All high-speed lubricated by high temperature grease are sealed by SS bellowswhile the All high-speed components(motors， gears， etc.） which should be lubricated very well,are sealed in boxes by welding bellows so that high temperature grease can be used. Meanwhile,some low-speed components (joint bearings and bushes） are considered to use $\mathbf { M o S } _ { 2 }$ -Ti-C coating films for solid lubricating.The detailed design of motion actuators can be summarized as follows:

(1）yaw actuator:

As shown in Figure 4, firstly two planetary roller screw divide the rotation motion produced by high-temperature motor and reducer into two parallel linear motions through a gear group.The two screws will move at a same speed but opposite directions due to the opposite threads of screw nut.Then, the screws are connected with two steel cables which can deliver the linear motions to yaw joint through bellows welded together with the seal box. The cables will be finally assembled with a pulley system attached to yaw joint to produce the rotation motion.The whole transmission process can be summarized to be a “rotation-linear-rotation” chain. Two benefits can be provide by this chain: dynamic sealing to protect the vacuum condition and huge reduction ratio to generate enough driving torque (1:3o82O from motor to yaw joint). (2）pitch actuator:

![](images/c350d40a6548f52d6d8518c79b1380bd6d1f5572c2a7b61f0c94701469687dcf.jpg)  
Figure4DetaileddesignofEAMAyawactuator

As shown in Figure 5,the pitch actuator has a similar “rotation-linear-rotation” chain with yaw actuator. The difference is only one roller screwisused here to transfer the rotation to linear motion.As the pitch actuator is located in the diagonal position, the changes in diagonal length will lead the whole parallelogram structure to do elevate while other links'length are fixed. The reduction ratio can reach up to 1:51660.

Currently,all of the manipulator components have been developed. The whole EAMA robot system was also successfully implemented in EAST vacuum vessel (Figure 6).

![](images/cf1375f5d44f0b03ad206f18277133d1a62f394d2c0916fd89112fbe7ff0031d.jpg)  
Figure5Detailed designofEAMA pitchactuator

![](images/86f51853e78c50ea24665a2e84f594f0b78dfd40b012b9c90660ecadc1c98341.jpg)  
Figure6 The implementationofEAMAmanipulator system

# 3. Experimental study

Compared with industry robot,EAMA system has more significant position errors,which are caused by the flexibilities of long-reach links as well as the complicated joints and transmission chains.Accurate theoretical model for errorprediction is difficult to build as the factors and their weights to affect the system stiffness are multiple and time-varying.Therefore,a load-deflection platform has been considered for the experimental study on the manipulator flexible properties. Figure 7 givesthe illustration of the platform design. Three types of external loads (mass in $y$ direction, torques along $x$ and $z$ axis)as system inputs were applied to the prototype of EAMA modular arm.Correspondingly， three items of position errors (deflections in $x$ and $y$ direction,angles along $z$ axis) were measured byLaser Tracker.Finally,272 sets of loaddeflection data under different loads have been recorded, which can be treated as the samples to train the BPNN prediction model.

![](images/9794912abeb28439aeae218752af2c8760c0b364f5f76ebef391568a86bda067.jpg)  
Figure 7 The illustration and implementation of load-deflection platform   
Note: different payloads were attached to two adjustable beams in $x$ and $z$ direction to generate different torques on robot joint

# 4. BPNN Prediction model

In a BPNN algorithm, several strongly coupled neurons are used to approximate the nonlinear functions. The learning process can be summarized as two steps (Negnevitsky, 2OO5). Firstly, a set of training data is input to the multi-layer network to obtain relevant output. Two kinds of functions willbe used:alinear transfer function with different weights and thresholds (Eq. 1）and a sigmoid activation function (Eq. 2). Secondly, an error is calculated by comparing the output with its expected value.Normally the expected values are obtained from experimental measurements.Then the error is propagated backwards through the network to modify the weights and thresholds of the coupled neurons. The rule for modifying weights and thresholds should always aimat reducing the error.

$$
X = \sum _ { i = 1 } ^ { n } x _ { i } w _ { i } - \theta
$$

$$
Y ^ { s i g m o i d } = \frac { 1 } { 1 + e ^ { - X } }
$$

For error prediction of EAMA manipulator,a final three-layer network has been built as the topological structure shown in Figure 8:

![](images/70a08b3354f89f26e761dc244ba314f974c6e7f8877e1367720bacda0b3ab201.jpg)  
Figure 8 The topological structure of BPNN model

(1）4 neurons in input layer: $\theta -$ the pitch angle of robot, $T _ { z }$ - the torque along z axis, $T _ { z } -$ the torque along $\mathbf { \boldsymbol { x } }$ axis, $F _ { y }$ - the equivalent gravity;   
(2） single hidden layer with 8 neurons;   
(3）3 neurons in output layer: the errors of end clevis in

different directions: $\Delta x , \Delta y$ and $\Delta \theta _ { z }$ · (4) $w _ { i j }$ and $\theta _ { j }$ denote the weights and thresholds between input and hidden layer; $w _ { i j }$ and $\theta _ { k }$ denote the weights and thresholds between hidden to output layer. The 272 sets of sample data were divided into two parts: 243 sets of data were utilized for network training, among which $70 \%$ for training, $1 5 \%$ for testing and $1 5 \%$ for validation; 29 extra measurement data were utilized to check the prediction accuracy of the BPNN model after training.

ThemathematicalmodelwasestablishedbytheNeural Network toolbox in Matlab environment. The network trainingfunction isTraingdx， which isableto automatically adjust learning rate based on the classical BP algorithm (Shi et al., 2OO9). The training was ended at epoch 6751 while the mean squared error was converged to 6.7717e-5 (Figure 9).

![](images/17aa402d3ff7c91702da9f11a3873fee7d98f7058020edf82512c0c82939123d.jpg)  
Figure9 The training process of BPNN model

To evaluate the prediction performance of the trained BPNN model,the extra 29 sets of load data were calculated by the offline BPNN model with the trained weights and thresholds listed in Table 2 and Table 3. Figure 1O gives the fitting situation between predicted and measured values which indicate a prediction error range from $2 \%$ to $6 \%$ (Figure 11). Considering the huge flexibilityandcomplicatedstructureofEAMA manipulator, the predicting accuracy is acceptable.The trained BPNN model can be integrated the control system to compensate the deflection error and improve the final position accuracy.

![](images/ad422b476f07d962735157a8d3ee58495d77a83bee3d69c571b787df0056be0a.jpg)  
Figure 10 The fitting situation between predicted and measured values

![](images/87a2e3b0feb8543b0f034cdcac5ea97097ff4eddf670401fee3cb86fa2fb62d3.jpg)  
Figure 11 The prediction error of the trained BPNN model

<html><body><table><tr><td rowspan="2">j</td><td colspan="4">Wij (i=4,j=8)</td><td rowspan="2">0j</td></tr><tr><td>-0.22532639</td><td>-0.021457862</td><td>0.000143862</td><td>0.021266973</td></tr><tr><td>1</td><td></td><td>0.002737846</td><td>0.000151412</td><td>0.061871295</td><td>1.168193494 0.506266839</td></tr><tr><td>2 3</td><td>-0.36576382 0.374547274</td><td>0.02131777</td><td>-0.000453784</td><td>0.022556882</td><td>0.265934803</td></tr><tr><td>4</td><td>-0.324228676</td><td>0.000747825</td><td>0.000236239</td><td>0.016785358</td><td>0.113202306</td></tr><tr><td>5</td><td>-0.313983181</td><td>-0.00378339</td><td>0.000254887</td><td>0.005711087</td><td>-0.02688637</td></tr><tr><td>6</td><td>-1.88891379</td><td>-0.004668008</td><td>-0.0000337</td><td>-4.908188396</td><td>-2.751156441</td></tr><tr><td>7</td><td>0.389308685</td><td>-0.011864381</td><td>-0.000147494</td><td>0.045723211</td><td>0.828719931</td></tr><tr><td>8</td><td>0.33108</td><td>-0.0137</td><td>-0.00012</td><td>0.036749</td><td>0.816560631</td></tr></table></body></html>

Table 3 The trained weights and thresholds between hidden and output layer   

<html><body><table><tr><td rowspan="2">k</td><td colspan="8">Vjk (j=8,k=3)</td><td rowspan="2">0k</td></tr><tr><td>46.3462</td><td>-19.279</td><td>-17.9038</td><td>54.933</td><td>-81.8616</td><td>-0.01364</td><td>89.21414</td><td>-121.38</td></tr><tr><td>1 2</td><td>7.83777</td><td>-30.161</td><td>-15.0365</td><td>181.49</td><td>-183.839</td><td>-0.05781</td><td>-73.7377</td><td>71.93208</td><td>-11.933 -12.3189</td></tr><tr><td></td><td></td><td></td><td>-19.0517</td><td>30.596</td><td>-69.5353</td><td>0.016233</td><td>106.448</td><td>-146.954</td><td>41.26604</td></tr><tr><td>3</td><td>-23.872</td><td>9.81833</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 5. Formulation of static loads

![](images/448819d775e2f01c7575f5be7c4544d92267859e573b4df27f12b91c62aaf23d.jpg)  
Table 2 The trained weights and thresholds between input and hidden layer

Since the motion speed ofEAMA manipulatoris quite slow (less than O.6 deg/second)， the dynamical characteristics are not significant when considering the payloads on each joint. To simplify the calculation，static loads due to gravity were derived using the model built in Figure 12.With the load results, the deflections of all segments can be predicted with the trained BPNN model in former section.

Figure12 Modelling of static loads

Considering the static loads on the end point $O _ { i }$ of Link $i$ ，firstly the gravity load can be easily written as Eq. 3:

$$
P _ { i } = \sum _ { j = i } ^ { n } m _ { j } g
$$

treated as the input of the trainedBPNN model for error evaluation without any experiments and measurements in future.

For the torques, the effect on Link $i$ caused by Link $j$ was firstly considered as Eq. 4, among which the torque was divided into two parts that respectively represent the torque along $\textbf { x } ( M _ { i j } ^ { x } )$ and y axis $( M _ { i j } ^ { y } )$ in the local coordinate system of Link $i$ -CS $( i )$ Besides, $\overrightarrow { O _ { i } P _ { j } } ^ { ( i ) }$ isthe position vector of point $P _ { j }$ (mass center of $\operatorname { L i n k } j )$ （2 with respect to point $O _ { i }$ in CS(i) while （2 $g _ { y } = \left[ 0 \textrm { \textit { g } } 0 \right]$ and $\scriptstyle { g _ { x } = { \left[ { g \begin{array} { l l l } { 0 } & { 0 } & { 0 } & { 0 } \end{array} } \right] } }$

$$
{ M } _ { i j } = \left[ \begin{array} { l } { { M _ { i j } ^ { x } } } \\ { { M _ { i j } ^ { y } } } \end{array} \right] = \left[ \begin{array} { l } { { m _ { j } g _ { y } \cdot \overrightarrow { O _ { i } P _ { j } } } } \\ { { m _ { j } g _ { x } \cdot \overrightarrow { O _ { i } P _ { j } } } } \end{array} \right]
$$

Furthermore, $\overrightarrow { O _ { i } P _ { j } } ^ { ( i ) }$ can be derived into Eq. 5. where $T _ { i } ^ { j }$ is the transfer matrix from CS $( i )$ to CS $( j )$ which can be obtained using D-H method (Denavit and Hartenberg， 1955). $\overline { r } _ { j } ^ { j }$ isthe position vector of mass center $P _ { j }$ in $\mathrm { C S } \left( j \right)$ ，which isdetermined by the geometryand mass properties of $\operatorname { L i n k } j .$ （204号

$$
\overrightarrow { O _ { i } P _ { j } } ^ { ( i ) } { = } T _ { i } ^ { j } { \stackrel { - j } { r _ { j } } }
$$

Combining Eq. 4 and Eq. 5，the total torque applied on the end point $O _ { i }$ of Link $i$ can be derived as:

$$
\begin{array}{c} { M _ { i } } = { \left[ \begin{array} { l } { { M _ { i } ^ { \mathrm { ~ x ~ } } } } \\ { { M _ { i } ^ { \mathrm { ~ y ~ } } } } \end{array} \right] } = \left[ \begin{array} { l } { { \displaystyle \sum _ { j = i } ^ { n } \biggl ( } { m _ { j } } { g _ { \mathrm { ~ x ~ } } } { { T _ { i } ^ { j } } ^ { - j } } { \displaystyle \sum _ { j } ^ { j } } } \\ { { \displaystyle \sum _ { j = i } ^ { n } \biggl ( } { m _ { j } } { g _ { \mathrm { ~ x ~ } } } { { T _ { i } ^ { j } } ^ { - j } } { \displaystyle \sum _ { j } ^ { j } } } \end{array} \biggr )  \end{array} \right]
$$

With the formulations above,the static loads oneach joint can be calculated when the manipulatorpositionis known.The loads can be

# 6.Conclusions

An articulated manipulator system applied in fusion environment has been developed in China for the purpose of real-time detection and rapid repairing of the damaged internal components in EAST tokamak device.The mechanical design of EAMA system was introduced firstly in this paper, including the modular parallelogram mechanism, the“rotation-linear-rotation’’ actuator design for dynamic sealing etc.Besides，to predict and compensate the flexible errors due to gravity effect，a load-deflection platform directed to EAMA prototype was built. Based on the 272 sets of deformation data, a BPNN model was established by the Neural Network toolbox in Matlab environment. After training,the fitting situationbetweenBPNNpredictedand experimentalmeasuredvaluesindicatea prediction error range from $2 \%$ to $6 \%$ .Finally, the static loads of each manipulator link was formulated,which can be integrated with the BPNN model for the error evaluation in control system. The conceptual design and error prediction strategy introduced in the paper can give beneficial reference to the similar robotic applicationsinvacuumandtemperature condition.

# Acknowledgements

Thiswork was supported by the National “973" Program of China(Chinese ITER Special Support Project,No.2014GB101000), funding of China Scholarship Council andacollaboration framework between ASIPP China and LUT Finland.

# Reference

Wan Y，Li J,and Weng P. (2006)，‘First engineering commissioning of EAST tokamak" Plasma Science and Technology,Vol.8 No.3. Li,J., Guo,H. Y., Wan, B. N., Gong, X. Z.,Liang, Y. F., Xu, G. S.,..& Zeng, L. (2013), "A long

pulse high-confinement plasma regime in the Experimental Advanced Superconducting Tokamak", Nature physics,Vol. 8 No.3, pp. 817- 821.   
Wang, H. Q., Xu, G. S., Wan, B. N., Ding, S. Y., Guo,H. Y., Shao,L. M.,..& Naulin,V. (2014), “New edge coherent mode providing continuous transportinlong-pulseh-modeplasmas”, Physical review letters, Vol. 112 No. 18, pp. 185004.   
Yang, Z., Fang, J., Gong, X., Gan, K., Luo, J., Zhao,H.,and Chen,M.(2016),“The study of heat flux for disruption on experimental advanced superconducting tokamak",Physics of Plasmas (1994-present), Vol.5 No.23, pp.052502.   
Li, W. X., Song, Y. T., Ye, M. Y., Peng, X. B., Wu, S. T., Qian, X. Y. and Zhu, C. C. (2016), “Thermo-mechanical and damage analyses of EAST carbon divertor under type-I ELMy Hmode operation”, Fusion Engineering and Design, Vol. 105, pp.15-21.   
Gargiulo,L.,Bayetti,P.,Bruno,V.,Hatchressian, J.C.,Hernandez，C.，Houry，M.，Keller，D., Martins， J.P.,Measson， Y.， Perrot， Y.and Samaille，F. (2009),"Operation of an ITER relevant inspection robot on ToreSupra tokamak", Fusion Engineering and Design, Vol.84 No. 2, pp. 220-223.   
Shimomura，Y.， Aymar， R.， Chuyanov,V., Huguet，M.，and Parker，R.(1999)，‘ITER overview”. Nuclear Fusion，Vol. 39 No.9Y, pp.1295.   
Perrot,Y., Gargiulo,L.,Houry,M., Kammerer, N.，Keller， D.， Measson，Y.， Piolain,G． and Verney， A.(2012)，‘Long-reach articulated robotsforinspectionandmini-invasive interventions in hazardous environments:Recent robotics research,qualification testing,and tool developments”,Journal ofField Robotics,Vol. 29 No.1, pp.175-185.   
Dwivedy，S.K. and Eberhard，P.(2006), “Dynamic analysis of flexible manipulators,a literature review”， Mechanism and Machine Theory, Vol. 41 No.7, pp.749-777.   
Schiavo，A.L.and Luciano，A.M. (2001), “Powerful and flexible fuzzy algorithm for nonlinear dynamic system identification”,IEEE Transactions on Fuzzy Systems, Vol. 9 No.6, pp.828-835.   
Chang，W.D.(2007)，“Nonlinearsystem identification and control using a real-coded geneticalgorithm”, AppliedMathematical Modelling,Vol. 31 No.3, pp.541-550.   
Liu,G.P.(2012),‘Nonlinear identification and control: a neural network approach", Springer Science&BusinessMedia.   
Shi, S., Song, Y., Cheng, Y., Villedieu,E., Bruno, V.,Feng,H... and Wang,K.(2016),"Conceptual design main progress of EAST Articulated Maintenance Arm (EAMA） system”,Fusion Engineering and Design,Vol.1O4, pp.40-45. Negnevitsky,M. (2005),“Artificial intelligence: aguidetointelligentsystems”， Pearson Education.   
Shi, Y., Zhao, X. T., Zhang,Y. M.,and Ren,N. Q.(2009)，“Back propagation neural network (BPNN） prediction model and control strategies of methanogen phase reactor treating traditional Chinesemedicinewastewater(TCMW）”, Journal of biotechnology, Vol. 144 No.1, pp.70- 74.   
Denavit，J.，& Hartenberg，R.S.(1955).“A kinematic notation for lower-pair mechanisms based on matrices”， Journalof Applied Mechanics, vol. 22, pp.215-221.