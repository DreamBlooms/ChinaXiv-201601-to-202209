# ANALYSIS OFMESHINGCHARACTERISTICSOFPINSANDPINHOUSINGINTEGRALSTRUCTUREINCYCLOIDALPLANETARYDRIVE

Yukun Wang,Guanyi Liu, Hao Yu, He Mao, \*Kai He Shenzhen Institutes of Advanced Technology, Chinese Academy of Sciences Shenzhen Key Laboratory of Precision Engineering Shenzhen,Guangdong,China yk.wang2@siat.ac.cn, gy.liu@siat.ac.cn, hao.yu@siat.ac.cn, he.mao@siat.ac.cn, kai.he@siat.ac.cn

Ruxu Du   
Institute of Precision Engineering   
Chinese University Of Hong Kong Hong Kong SAR, China rdu@mae.cuhk.edu.hk

# ABSTRACT

Precision reducer is one of the key parts of an industrial robot, whichgenerallyincorporatescycloidalplanetarydrive. Engagement of the cycloidal wheel and the pins causes rolling friction between the wheel and the pins as well as sliding friction between the pins and the pin housing in the traditional cycloidal transmission of the reducer.In this paper, we present a new kind of design to make the pins and the pin housing a whole structure, thereby the cost of manufacturing and assembly can be significantly reduced. And in this new structure,we only need to consider sliding friction between the cycloidal wheel and the unibody of the pins and pin housing. The difference between the new structure and the conventional structure in the meshing properties was given. In addition, we used finite element method to analyze the friction and contact stress between the cycloidal wheel and the pins in the actual working condition， and compared it with the traditional structure.The simulation results proved the feasibility of the new structure and provided a theoretical basis for further design and manufacturing of this new kind of cycloidal planetary drive structure.

# 1INTRODUCTION

Cycloidal planetary drive generally uses cycloidal wheel and pins to achieve the transmission and is widely used in robots, aerospace, CNC machines and other fields.RV (Rotate Vector) reducer is a typical type of cycloidal drive which is composed of the former planetary gear reducer and the rear cycloid reducer. It has a lot of advantages,such as small size,light weight,large reduction ratio,long life,stable stability，high efficiency and smooth transmission.

In the cycloidal planetary drive, meshing transmission is achieved by the rolling friction between the cycloidal wheel and pins as well as sliding friction between pins and pin housing.Because manufacturing and assembly precision are hard to satisfy, there is usually a gap between the pin housing and the pins.The gap causes vibration and noise.

Chui-Fan Hsieh [1] proposed a nonpin cycloidal gear housing design for the structural improvement of the cycloidal planetary drive.Caichao ZHU et al. [2] proposed a new type of fixed shaft cycloidal drive，because of the shortcomings of the cycloid wheel drive.A prototype is manufactured and the efficiency experiment is carried out on the test bed. Jingya LIU et al.[3] proposed a novel cycloidal actuator,and its meshing characteristicswereanalyzed. Thisnewcycloid-driven conjugate gear pair consists of an external cycloidal gear and an internal ring gear. The new cycloid driver of this arc gear is also a cycloidal planetary drive without a pin. Xin Li et al.[4] proposed a new cycloid reducer that uses a double crank-ring cycloidal drive to deliver greater torque than a typical existing planetary cycloid driver. Mirko Blagojevic et al.[5] made a new design for the traditional cycloid reducer,and proposed a new two-stage cycloid reducer,in each level there is a cycloid, which means the structure is more compact. Hidetsugu Terada [6] proposed a new type of cycloidal ball reducer, which can achieve no gap transmission,and gives a new type of reducer movement principle and contour calculation method. In the effort to improve the design， the researchers have also discussed other aspects，including the force distribution calculation on the cycloidal components, the power loss and the theoretical mechanical efficiency [7-9]. There are some studies focused on the dynamic behavior of cycloid reducers in Kahraman's research [10].

In this paper,we propose a new type of cycloidal planetary reducer whose structure holds the pins on the pin housing Using digital virtual prototyping technology and multi-rigid body dynamics technology we give 3D modeling and dynamic simulation analysis of the new structure.The simulation results show the new structure has almost same transmission performance and small contact force compared with the traditional cycloidal planetary reducer.

# 2CYCLOIDALPLANETARYDRIVETHEORIES 2.1Cycloidal ToothProfile GenerationPrinciple

As shown in Figure 1,when a rolling circle with radius $r$ performs pure rolling on basic circle with radius $R$ ，the rotating angle of the rolling circle around the center of the basic circle $O _ { a }$ is represented by $\psi$ . The trace of a point $M$ on the rolling circle generates a curve.The cycloidal profile is the equidistant curve of the former curve with the distance $r _ { z }$ ,and the $r _ { z }$ is also the radius of the pin.All the pins evenly distributed around a circle with center $O _ { b }$ and radius $R _ { _ z }$ .The distance between $O _ { a }$ and $O _ { b }$ is $A$ . The number of pins $Z _ { b }$ is more than that of the cycloidal wheel teeth $Z _ { a }$ by 1.

Parametric equation of theoretical cycloidal tooth profile is derivedasfollows:

$$
\begin{array} { l } { \displaystyle x _ { 0 } = R _ { z } ( \sin \psi - \frac { K _ { 1 } } { Z _ { b } } \sin Z _ { b } \psi ) } \\ { \displaystyle y _ { 0 } = R _ { z } ( \cos \psi - \frac { K _ { 1 } } { Z _ { b } } \cos Z _ { b } \psi ) } \end{array}
$$

When one tooth profile formed, the rotating angle $\psi$ of the rolling circle is calculated below.

$$
\psi = 2 \pi / Z _ { a }
$$

Parametric equation of practical cycloidal tooth profile is derived as follows.

$$
\begin{array} { r } { x = x _ { 0 } + r _ { z } \cos \gamma } \\ { y = y _ { 0 } - r _ { z } \sin \gamma } \end{array}
$$

Where, $\gamma$ represents the angle between Line $A M$ and $\mathbf { \boldsymbol { x } }$ -axis, and Line $A M$ is the tangent of the circle with the center $O _ { a }$ and radius $R _ { a }$ ： Itssine function and cosine function are derived as follows.

$$
\begin{array} { r } { \cos \gamma = \frac { K _ { 1 } \sin Z _ { b } \psi - \sin \psi } { \sqrt { 1 + K _ { 1 } ^ { ' } - 2 K _ { 1 } \cos Z _ { b } \psi } } } \\ { \sin \gamma = \frac { - K _ { 1 } \cos Z _ { b } \psi + \cos \psi } { \sqrt { 1 + K _ { 1 } ^ { ' } - 2 K _ { 1 } \cos Z _ { b } \psi } } } \end{array}
$$

![](images/465fd62f40e502c6d16278160e9b236c67d887f4563d283827821d9ddbc3b5c5.jpg)  
Figure.1 The generation principle of cycloidal tooth profile TorqueofCycloidal Wheel Transmission

As shown in Figure 2,the output shaft torque of the RV reducer is represented by $M _ { \nu }$ ，because two cycloidal wheels work at the same time, so the torque on one piece of cycloidal wheel $\boldsymbol { { M } } _ { a }$ is:

$$
M _ { a } = M _ { \nu } / 2
$$

![](images/7ce8209d4c79823a8a92091cc9c44a0b311cb24ae43dc9bde8ac7bd89d35718a.jpg)  
Figure.2 Scheme of cycloidal planetary drive

$M _ { a }$ acts on the rotation center $O _ { a }$ of the cycloidal wheel. Taking into account the cycloidal wheel and pin manufacturing error and the installation error of the pins,unevenly load distribution happens on the two cycloidal wheels, so we generally increase $M _ { a }$ by $10 \%$ ,that is

$$
M _ { a } = 0 . 5 5 M _ { \nu }
$$

# 2.3Meshing Force between the Pins and Cycloidal Wheel

As shown in Figure 3,assuming that the pins are fixed, under the torque $M _ { a }$ ， due to elastic deformation,the cycloidal wheel turns a very smal angle $\beta$ clockwise. On the right side of Y-axis, the pins have a tendency to leave the cycloidal wheel, and there is no meshing force between each other. On the left side of Y-axis, the pins and cycloidal wheel mesh together to achieve transmission, force and reaction force exists between them.

![](images/7107d53f350a13c219be0c19f3d5b7a35f98bebaffcdc9680438acb34bbd7cc6.jpg)  
Figure.3 Schematic diagram of the force in the process of cycloidal wheel and pins meshing

The force that the pin with number $i$ acts on the cycloidal wheel is $P _ { i }$ , and the elastic deformation of the pin with number $i$ is defined as $\delta _ { i }$ (including the bending deformation of the pin and the contact deformation of the meshing point)

$$
\delta _ { _ i } = l _ { i } \beta
$$

Where $l _ { i }$ is the vertical distance from $O _ { a }$ to $P _ { i }$

Consideringtheengagingforcecharacteristics, （204号 $P _ { i }$ is proportional to $\delta _ { i }$

$$
P _ { i } = K \delta _ { i } = K l _ { i } \beta
$$

Where $K$ is a constant.

When $l _ { i } = r _ { a }$ ， $l _ { i }$ reaches the maximum value, at the same time $l _ { i }$ also reaches the maximum value $P _ { \mathrm { m a x } }$

$$
P _ { \operatorname* { m a x } } = K r _ { a } \beta
$$

So, we can derive $P _ { i }$ as follows.

$$
P _ { i } = P _ { \operatorname* { m a x } } \cdot l _ { i } ~ r _ { a }
$$

Considering the moment balance, we can see that the torque transmitted by the cycloidal wheel is equal to the torque of the pins acting on the cycloidal wheel.

$$
M _ { a } = \sum _ { i = 1 } ^ { Z _ { b a s } } \underbrace { P _ { i } } _ { i } l _ { i } = \frac { P _ { \operatorname* { m a x } } } { r _ { a } } \sum _ { i = 1 } ^ { Z _ { b } } l _ { i } ^ { 2 }
$$

$Z _ { b }$ （204号Solve ²,we obtain

i=1

$$
\stackrel { Z _ { b } } { l _ { i } } = { \frac { 1 } { 4 } } Z _ { b } { r _ { a } ^ { 2 } } ^ { 2 } \nonumber
$$

So,

$$
P _ { \mathrm { m a x } } { = } 4 M _ { a } / r _ { a } Z _ { b } .
$$

By solving the $\triangle M _ { i } O _ { b } P$ , we obtain

$$
l _ { i } = \frac { r _ { a } \sin \theta _ { b i } R _ { z } } { \sqrt { { R _ { z } } ^ { 2 } + { r _ { b } } ^ { 2 } - 2 { R _ { z } } r _ { b } \cos \theta _ { b i } } \ . }
$$

Where $\theta _ { b i }$ is the angle between $M _ { i } O _ { b }$ and $\mathrm { Y }$ axis.

Substitute equation(14) to equation(1O),we obtain,

$$
P _ { i } = \frac { P _ { \mathrm { m a x } } \sin \theta _ { b i } R _ { z } } { \sqrt { { R _ { z } } ^ { 2 } + { r _ { b } } ^ { 2 } - 2 { R _ { z } } r _ { b } \cos \theta _ { b i } } \ . }
$$

When the reducer outputs assumed torque, the pin force situation is shown in Figure 4.

![](images/c41344eb9c9df1d09245cc514b444b1c420341b421057e0d8861eed54d7afbe1.jpg)  
Figure.4Force of pins and cycloidal wheel engagement

# 3 DYNAMIC SIMULATION OF CYCLOIDAL PLANETARYDRIVEMODEL 3.1Prototype Design of the Cycloid Planetary Reducer

We designed the gear ratio of the reducer of 121,assuming the input speed of $1 8 1 5 \mathrm { r / m i n }$ , the output load of $1 6 7 \mathrm { N . m }$

For the cycloidal wheel and pin housing, $R _ { _ z }$ is $1 0 0 \mathrm { m m }$ ， $A$ is $1 \mathrm { m m }$ ,and $r _ { z }$ is $2 ~ \mathrm { m m }$ . For the sun gear and planetary gear, the gear modulus is $1 . 5 \mathrm { m m }$ , and gear pressure angle is $2 0 ^ { \circ }$ ： The new cycloidal planetary reducer with nonpin structure is constructed in 3D software,and reducer with pin structure is also modeled for comparison purpose. The models of the two types of reducer are shown in Figure 5-8.

Table 1 Design of the gears   

<html><body><table><tr><td>Type of gear</td><td>Cycloidal wheel</td><td>Pin housing</td><td>Sun gear</td><td>Planetar ygear</td></tr><tr><td>Number of tooth</td><td>39</td><td>40</td><td>9</td><td>27</td></tr></table></body></html>

After the model is established, it is necessary to carry out part interference check, including static interference detection and dynamic interference detection.If there is interference,then adjust the parts until there is no part interference.

![](images/cce951878bdf5cde1793543084f1e5c56e03b6c4351b784a08ebfb880c498e89.jpg)  
Figure.5 Reducer with nonpin structure design (front view)

![](images/fd8697246635ebdb800614d26641470121662614babce61575b1a528b2d463d3.jpg)  
Figure.6 Reducer with nonpin structure design (exploded view)

![](images/cfdf00ec5e40fa96ef755a4be27726ceb2b92aa212fbdc3b5d01b7d0e8c4c815.jpg)  
Figure.7 Reducer with pin structure design (front view)

![](images/9970a590dce68e5fb489ffc0dce067557cad1a4e49750bce9f0b0d651e687ab4.jpg)

Figure.8 Reducer with pin structure design (exploded view) The new designed cycloidal planetary reducer is shown in Figure 5 (front view） and Figure 6 (exploded view).The cycloid planetaryreducer with pins isused as a reference model and shown in Figure 7(front view） and Figure 8(exploded view). The two type of reducer has the same parameters.

# 3.2Dynamic Simulation of Virtual Prototype of Cycloidal Planetary Reducer

In order to improve the simulation speed of the model, the RV reducer model is simplified without affecting the system analysis results.We remove the bearings,bearing frames and all tiny features such as chamfering，fillet,etc.The gears are replacedby cylinders.

In 3D model, we set the material properties of steel, the friction coefficient of O.05. Set the input speed to $1 8 1 5 ~ \mathrm { r / m i n }$ and apply a load torque of $1 6 7 \mathrm { N . m }$

For the nonpin structure, the import entity contains 1O rigid body parts.4 Fixed Joints are added to the model. The pin housing is fixed to the ground to simulate the installation of the reducer. The planet carrier is fixed to the output plate to simulate the bolt connection and cone positioningpin connection. The planet gear is fixed to the eccentric shaft to simulate the spline connection.8 Rotation Joints are also added to the model to simulate the rotation relationship between sun gear and planet carrier,planet gear and planet carrier,planet carrier and pin housing,as well as eccentric shaft and cycloidal wheel. 2 Gear Joints are added to the sun gear and planet gear. 2 Contact Forces are added to the two cycloidal wheels and pin housing. Finally angular velocity is input to drive the sun gear, and load is added to the output plate in the form of torque. The input speed and load are used to simulate the actual working condition of the designed reducer.

For the pin structure system. The import entity is represented by 50 rigid body parts.4 Fixed Joints,48 Rotation Joints，2 GearJoints,80 Contacts are added to the model.The difference between the pin structure model and the nonpin structure lies in that there are 4O pins which contact with the pin housing and rotate in the groove of the cycloidal wheel and the pin housing.

According to the above constraints,force,drive and load as well as the degree of freedomof the reducer model, the analysis type is automatically selected.The end time is set as 5 s,steps is set as 500.

# 4RESULTSANDDISCUSSION

The dynamic simulation results of the key components such as sun gear, planet gear, cycloidal wheel and output plate of the nonpin and pin structure are shown in Figure 9-12.

From Figure 9-12,we can see that the nonpin structure has a slight velocity fluctuation, butis basically the same with the pin structure.Reduction ratio is calculated by the angular velocity of the sun gear and the output plate and both the reduction ratio of the two types of structure is 121.

![](images/38a8a8a34b61ca3beaabd955d5e26e867c9c0155c1ea19b7fb2c20177f8ce238.jpg)  
Figure.9 Angular velocity of the sun gear with nonpin $\&$ pin design

![](images/1907fe8682a2a4489947a0f23c6ea09b478e1392d917554b7dd4fd9134729195.jpg)  
Figure.1O Angular velocity of the planet gear with nonpin $\&$ pin design

The designed reducer has two pieces of cycloidal wheels, the onenear the output plate is numbered as the $1 ^ { \mathrm { s t } }$ ，and the otheris numbered as the $2 ^ { \mathrm { n d } }$ ，in order to describe the simulation results. And for the nonpin structure the pin number means the corresponding position of the same pin number in the pin structure.

![](images/510194880074d92ff609063a0f67deea4237b485a4e2e68ddbb7679629f4dc82.jpg)  
Figure.11 Angular velocity of the cycloidal wheel with nonpin $\&$ pin design

![](images/abea0d60aca2771fdaf65c356561834350c68739e945d3092c2f9b47fc2367a1.jpg)  
Figure.12 Angular velocity of the output plate with nonpin $\&$ pin design

Figure 13 shows the curve of contact force change between pin 1 and the two cycloidal wheels of the designed nonpin structure.Figure 14 shows the curve of contact force change between pin 1 and the two cycloidal wheels of the traditional pin structure.From the two figures,we can see that the force magnitude of the nonpin structure is a little smaller than the pin structure.Figure 15 and Figure 16 show the curves of the force change of pin 1,pin 2 and pin 3 between the $1 ^ { \mathrm { s t } }$ cycloidal wheel. Contact force of every pin in the nonpin structure is smaller than the pin structure.

Because there is a gap between the pins and the pin housing in the pin structure,when the cycloidal gears rotate at high speed, the pins swing slightly due to the continuous engagement and collision. Therefore, the pin structure has a higher contact force, which reduces transmission performance.

![](images/01fd02e531ac89ad3994bb47e2bbc8541457cca1b692f35ff9ad753ff022b2af.jpg)  
Figure.13 Contact force between the pin1 and the lst cycloidal wheel and the 2nd cycloidal wheel of the nonpin structure

![](images/e6914776512b500d58555fbff8a282fe5d6cc58329d88ecf1017563cd4138619.jpg)  
Figure.14 Contact force between the pin1and the lst cycloidal wheel and the 2nd cycloidal wheel of the pin structure

![](images/ef477520b79dfc6c544c46254b85d08ee646ad6de1f48936f7f2dfe36c5114b4.jpg)  
Figure.15 Contact force between the cycloidal wheel and pin1to 3 of the nonpin structure

![](images/56d17fa3bb03bd41cc6f3c318e26cac5f467f99227af5de5b91a5f51516e76aa.jpg)  
Figure.16 Contact force between the cycloidal wheel and pin 1 to 3 of the pin structure

Finite element analysis is used here to give a stress simulation of the second stage of this nonpin structure drive. The mechanical properties of the materials are listed in Table 2. Cycloidal wheel tooth profile is a special curve with high precision, so a small grid of $0 . 8 ~ \mathrm { m m }$ was used in the meshing of cycloidal wheel and pin,and the mesh type is mixed with tetrahedron and hexahedron. The finite element model is discretized into 451956 nodes and 57800 elements as shown in Figure 17.

Table 2 Mechanical properties   

<html><body><table><tr><td>Part name</td><td>Elastic modulus(GPa)</td><td>Poisson's ratio</td><td>Density(kg/m³)</td></tr><tr><td>Pin housing</td><td>208</td><td>0.295</td><td>7870</td></tr><tr><td>Cycloidal wheel</td><td>208</td><td>0.295</td><td>7870</td></tr></table></body></html>

The material of cycloidal wheel is the same as pin housing,and the contact type is the surface contact of soft body to soft body. When creating a contact pair, the convex surface should be selected as the contact surface and the concave surface should be the target surface. So pin surface was selected for as the contact surface,while cycloidal wheel surface was defined as the target surface. The contact pair setting is show in Table 3. The partial magnification of contact pair is shown in Figure 18. Constraint boundary conditions for cycloidal drive are shown in Figure 19.   
The calculated contact stress distribution of the pin housing and cycloidal wheel is shown in Figure 2O.It can be seen from the stress distribution cloud diagram that the stress concentration occurred at the eccentric shaft installation holes on the cycloidal wheel, and the contact point on pin housing is also the dangerous part.

Table 3 Contact pair settings   

<html><body><table><tr><td>Type</td><td>Behavior</td><td>Formulation</td><td>Interface treatment</td></tr><tr><td>Frictionless</td><td>Auto Asymmetric</td><td>Augmented Lagrange</td><td>Adjust to touch</td></tr></table></body></html>

![](images/0e5e123e1a8177c7ec559e2d448f74c4f7d9202220724053a7739067f98a7956.jpg)  
Figure.17 FEM mesh of the nonpin structure

![](images/e6d7286ebdec31f46093fedbe311253a91a1ca4c74cbafe149938a968ab9a814.jpg)  
Figure.18 The partial magnification of contact pair

The pin contact stress distribution is shown in Figure 21.A total of 20 pins are in contact with the cycloidal wheel,which is the same as the theoretical engagement. The maximum contact stress appears in the fourth pin. Its value is $4 5 . 9 6 \mathrm { M P a }$ ,which is much smaller than the allowable contact stress of the material $6 5 0 \ \mathrm { M P a }$ ，so it meets the contact strength requirement. The difference between the finite element calculation and the theory is because nonlinear factors caused by bearing holes and center holes on cycloidal wheel. But the stress distribution trend is substantially consistent with the ideal elastic linear contact theory.

![](images/21a123b30280129b0182def2414c3c2eb11dbad63aa0b7e92c136208f57b7db0.jpg)  
Figure.19 Constraint boundary conditions

![](images/283b9e73f914dc8c2d967b77a195846d4267fbd557f970d60a9c903c1a2a3182.jpg)  
Figure.2O Contact stress distribution of the pin housing and cycloidal wheel

![](images/bc32bbefb2cabd284c048748cb034bc580e72ab28f5a4e18c7d190893a03038a.jpg)  
Figure.21 Pin contact stress distribution 5 CONCLUSIONS

In this study, we proposed a new type of cycloidal planetary reducer with a pins and pin housing integral structure.

A systematic dynamics analysis model of this new type of cycloidal speed reducer was developed and then the effects of the pin and nonpin designs on the speed reducer's dynamics performance were compared. The new nonpin structure has almost the same speed and transmission ratio to meet the transmission requirements.The peak value of the contact force in the nonpin structure is smaller than that of the pin structure due to the continuous engagement of the collision between the pins and pin housing.On the other hand, through the stress analysis,it is concluded that the peak value of the contact stress of the nonpin structure is much smaller than the allowable contact stress of the material,which satisfies the strength requirement.

In general, the nonpin structure has some advantages, such as pin housing and cycloidal wheel in good contact state, symmetrical contact stress distribution， no tooth profile eccentricity. The feasibility of this type of nonpin structure is proved by simulation study.

# ACKNOWLEDGMENTS

The presented research work was supported by ShenzhenBasic Research Project (JCYJ20150925163026555).

# REFERENCES

[1] Chui-Fan Hsieh,2014, "Dynamics Analysis of Cycloidal Speed Reducers with Pinwheel and Nonpinwheel Designs", ASME J. Mech.Des,136(9), pp. 091008-1-11   
[2] Caichao ZHU, Mingyong LIU ,Xuesong DU, Ning XIAO, BinZHANG，2010，"AnalysisonTransmission CharacteristicsofNewAxis-fixed Cycloid Gear", Advanced Materials Research, Vol.97-101,pp. 60-63   
[3]Jingya LIU，Bingkui CHEN，Shigeki MATSUMURA, ChaoyangLI, 2012,"Design of a Novel Cycloid Drive with a Cycloid-arc Gear and Analysis of ItsMeshing Characteristic", Journal of Advanced Mechanical Design, Systems,and Manufacturing,Vol. 6,No.2,pp.310-322   
[4] XinLi,WeidongHe,LixingLi andLinda C. Schmidt,2004 "A New Cycloid Drive with High-Load Capacity and High Efficiency ",ASME J.Mech. Des 126(4), pp. 683-686   
[5]Mirko Blagojevic，Nenad Marjanovic,Zorica Djordjevic, Blaza Stojanovic and Aleksandar Disic,2011，"A New Design ofa Two-Stage Cycloidal Speed Reducer", J.Mech. Des 133(8), pp. 085001-1-7   
[6] Hidetsugu Terada,2Oo9，"The Development of gearless reducers with rolling balls", Journal of Mechanical Science and Technology, Vol.24, Issue 1,pp.189-195   
[7]S.K Malhotra,M.A Parameswaran,1983，"Analysis of a Cycloid Speed Reducer",Mechanism and Machine Theory, Vol. 18 Issue 6, pp.491-499   
[8] Yunhong Meng， Changlin Wu, Liping Ling， 2007, "Mathematical Modeling of the Transmission Performance of 2K-H Pin Cycloid Planetary Mechanism",Mechanism and Machine Theory, 42(7), pp. 776-790.   
[9]Carlo Gorla,Piermaria Davoli,Francesco Rosa,Claudio Longoni, Franco Chiozzi and Alessandro Samarani,2008, "Theoretical and Experimental Analysis of a Cycloidal Speed Reducer",ASME J.Mech.Des,130(11),pp.112604.   
[10]A.Kahraman,H.Ligata and A. Singh,2O1o, "Influence of Ring Gear Rim Thickness on Planetary Gear Set Behavior", ASME J.Mech.Des,132(2), pp.021002.