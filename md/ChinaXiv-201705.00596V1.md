# Modeling of Torque Output and Magnetic Force for Novel Spherical Actuator with Three-dimensional Pole Arrays

Liang Yan1,2, Fengqi Liang1, Zewu $\mathrm { \Delta W u ^ { 1 } }$ , Zongxia Jiao1, Chin-Yin Chen³,I-Ming Chen4 1 School of Automation Science and Electrical Engineering, Beihang University, Beijing,10o191 China. ² Shenzhen Institute of Beihang University, Shenzhen, 518000 China. Email: lyan1991@gmail.com 3 Institute of Advanced Manufacturing Technology,Ningbo Instituteof Material Technology and Enginering, Ningbo,China,315201.E-mail: chenchinyin@nimte.ac.cn 4 School of Mechanical and Aerospace Engineering, Nanyang Technological University, 50 Nanyang Avenue, 609798 Singapore. Email: MIChen@ntu.edu.sg

Abstract—A novel PM spherical actuator based on threedimensional pole array is proposed and developed in this paper. Conventionally,2D pole arraysare widely employed in the design of spherical actuators,which constraints the system torque output greatly. The concept of 3D pole array is aimed at improving the torque performance.The torque has been analyzed and the corresponding analytical model is established based on curve fitting method (CFM) due to the importantance to real-time control.Magnetic force has been studied in a similar way. The results shows that the modeling method has a relatively high precision and can be further used in the real-time control.

# I.INTRODUCTION

Devlopment of robotics,automated manufacturing processes and military and aeronautics has led to strong demand for the devices that can achieve multiple degrees of freedom motions in a single joint.These devices denote as spherical actuators,which have drawn plenty of researchers’attention for several decades due to the compact structure,high precision,fast response and no backlash and singularities compared with the devices with multiple single-axis motors [1],[2]. The first spherical actuator was invented by Williams and Laithwaite in 1955 [3].Lee et al.proposed the concept of spherical actuator based on the variable-reluctance principle and conducted researches on its magnetic field and torque[4], [5] in198Os.After that,more in-depth designs and analysis [6], [7] were conducted.Chirikjian et al.developed aPM spherical stepper actuator with 12-inch diameter [8]. The corresponding kinematic design and the commutation problem are analyzed. Wang et al.conducted researches on magnetic field analysis and torque calculation based on the prototype of the PM spherical stepper motor implemented by Chirikjian et al.[9], [10].Motion control algorithm and kinematic characteristics are analyzed furthered.Wang et al.developed permanent magnet (PM) spherical actuators which can achieve either 2- DOF motion or 3-DOF motion [11],[12]. Serious of systematic work has been down on the magnetic field, torque calculation and control schemes. Studies on spherical actuators can be also found in [13]-[21].

Torque and force characteristics are extremely important to the analysis of the whole actuator. Thus,the torque and force performances are focused in this paper.A lot of relative work has been conducted on the calculation of the torque of the spherical actuators based on the prototypes.The torque model in [22]and[1O] are formulated based on Maxwell Stress Tensor (MST) method.The disadvantage of MST is that the result is very sensitive to discretization density and integration contour position [15]. The coenergy method has been utilized by Lee et al.[7] to derive the torque model of variable-reluctance spherical motor (VRSM） successfully. However, this method becomes unsuitable for some cases with large air-gap or air-core coils.Alternatively,Wang [11] and Yan [23] calculated the torque using Lorentz force law,which is suitable for stators with air-core coils and rotors with PM poles and can be used for real-time control.However,the control accuracy may not be that high due to the approximation during the modeling process.

To improve the torque performance,a novel spherical actuator based on 3D pole arrays has been proposed in our previous work [24]，[25].Magnetic field has been analyzed in analytical,numerical and experimental ways.In this paper, a curve fitting method(CFM) will be adopted to build the torque and magnetic force model to improve the modeling accuracy and facilitate real-time control. This method becomes especially useful for the control of a special spherical actuator.And the research of magnetic force model in this paper will be of significance to the further design and improvement. The rest of this paper is organized as follows.In Section II,the concept and working principle of the novel spherical actuator are introduced briefly.In Section III, the torque model is established.And in section IV, the magnetic force model is discussed.

# II. CONCEPTDESIGN AND OPERATING PRINCIPLE

The concept of 3D pole array patterns can be illustrated in Fig.1.In traditional design of spherical actuators,the coils and PM poles are always mounted on 2D spherical surfaces.Those pole array patterns can be defined as 2D pole array patterns. While in the novel array patterns design,the poles of the rotor and stator are distributed in 3D spaces.In this case,the inside volume of the actuator can be utilized more effectively through reasonable poles arrangement. The coils with current passing through interact with the enhanced magnetic field produced by the 3D PM poles.As a result,higher force/torque can be produced than the the 2D pole array spherical actuator.Fig.1 shows one typical 3D pole pattern design.As the sketch map illustrates,two spherical-shelf-like rotors mounted with PM pole arrays are fixed together through the output shaft and two stators mounted with coils are connected through a shaft fixed on the base.The two stators and two rotors gear to each other alternatively.To facilitate the observation,the outer shelves of the spherical stator and rotor are removed from Fig.1(a) and (b).Two layers of poles in radial direction are employed in this design.

![](images/b9cc365e0942cd4ced60a1bfe7a3bc500a65014520aa56c17b08264820e11e2e.jpg)  
Fig.1．Concept of three-dimensional pole arrays:(a) Rotor poles distribution (b) Stator poles distribution

To facilitate prototype manufacturing and analysis,a 3D pole array spherical actuator with two layers of PM poles and one layer of coils in radial direction is developed in the following study. The working principle of this machine is illustrated in Fig.2.The rare-earth PM poles with alternate polarities are mounted along the rotor equator to produce high flux density around the stator. The air-core coils are assembled on the stator symmetric about the stator equatorial plane.By energizing pairs of coils in two longitudinal directions,the rotor can tilt in two orthogonal directions as shown in Fig. 2 (a)and (b).Energizing all circumferential coils,the rotor can spinaboutitsown axisFig.2(c).Thus,byregulating the value and direction of input currents of in the coils,desirable 3-DOF rotary motion can be achieved within the workspace. Fig.2 (d) is the assembled actuator CAD model.

# [II. FORMULATIONOFOUTPUT TORQUE

Torque model is extremely important for the real-time control of the spherical actuator.Byutilizing the torque model, the required currents can be calculated from the desired actuator torque.Analytical torque model based on Lorentz force law can reflect relationship the between the torque performance and the actuator parameters very well and be applied in optimization design.However, it is not that suitable for the control of the spherical actuator because that too many approximation of the complex boundary conditions will deteriorate the control accuracy. The finite-element simulation can make up for the deficiency and be more accurate to obtain the torque data although it can not reflect the function relation between the torque performance and the actuator parameters. Thus,to build a more accurate torque model, it can be analyzed using the FEM.The FEM model is established in Maxwell 3D. Herein the torque is modeled through curve fit of the data from FEM simulation [6],[26].

![](images/b6a0e5a6848b439d2bc311ea6c4227b4c4e2c214a7f29c5af1c536cc6cfb707a.jpg)  
Fig.2.3-DOF motion of the spherical actuator.(a) First tilting motion. (b) Second tilting motion.(c) Spinning motion.(d) Assembled actuator

# A.TorqueAnalysiswithFEM

As the coils of the spherical actuator are mounted on nonferromagnetic cores,the torque output is proportional to the current input. Therefore,the torque model can be derived from one coil pole model through linear superposition. The air gap between the inner rotor and the stator is $0 . 5 \mathrm { m m }$ .And the air gap between the outer rotor and the stator is $2 \mathrm { m m }$ Considering the need of fixing the coils,the latteris a little bigger than the former one.In the future research,more means of coil fix could be discussed to diminish the air-gap's influence on the torque performance.The key parameters of the rotor and stator are given in TableI.

TABLE I. PARAMETERS OF THE INNER ROTOR   

<html><body><table><tr><td>Inner Rotor</td><td>CylindricalPM</td><td>Value</td></tr><tr><td>OuterRadius of Outer Rotor</td><td>R00</td><td>96mm</td></tr><tr><td>Inner Radius of Outer Rotor</td><td>R01</td><td>80mm</td></tr><tr><td>Outer Radius of Stator</td><td>R10</td><td>79.5mm</td></tr><tr><td>Inner Radius of Stator</td><td>R11</td><td>42.5mm</td></tr><tr><td>Outer Radius of Inner Rotor</td><td>R20</td><td>20mm</td></tr></table></body></html>

The torque produced by the interaction between the $i ^ { t h }$ PM pole and $j ^ { t \hat { h } }$ coil can be written into the following expression:

$$
\mathbf { T } _ { i , j } = f ( \phi _ { i , j } ) \mathbf { d } _ { i , j } i _ { j }
$$

$$
\phi _ { i , j } = \cos ^ { - 1 } \mathbf { r } _ { i } \mathbf { s } _ { j } / \left\| \mathbf { r } _ { i } \right\| \left\| \mathbf { s } _ { j } \right\|
$$

$$
\mathbf { d } _ { i , j } = \mathbf { r } _ { i } \times \mathbf { s } _ { j } / \left\| \mathbf { r } _ { i } \times \mathbf { s } _ { j } \right\|
$$

Where $\phi _ { i , j }$ is defined as the included angle between the $i ^ { t h }$ PM pole and $j ^ { t h }$ coil, $f ( \phi _ { i , j } )$ is the torque constant function, $\mathbf { r } _ { i }$ is the position vector of the $i ^ { t h }$ PM pole,and ${ \bf s } _ { j }$ isthe position vector of the $j ^ { t h }$ coil. $\mathbf { T } _ { i , j }$ is the torque vector from the interaction of the $i ^ { t h }$ PM pole and $j ^ { t h }$ coil.

Herein, the curve fit torque constant function $\tilde { f } ( \phi _ { i , j } )$ has the following form:

$$
\tilde { f } ( \phi _ { i , j } ) = a _ { 0 } + \sum _ { i = 1 } ^ { 8 } \left( a _ { i } \cos ( \phi _ { i , j } * w ) + b _ { i } s i n ( \phi _ { i , j } * w ) \right)
$$

where $a _ { 0 } , a _ { i }$ ， $b _ { i }$ and $w$ are coefficients determined by the least square method $\left\| \tilde { f } \left( \phi _ { i , j } \right) - f \left( \phi _ { i , j } \right) \right\| ^ { 2 }$ .The source function $f ( \phi _ { i , j } )$ is obtained from the FE computed data as shown in Fig.3.Parameters of the curve fitting equation are list on Table. II. The FE data comes from a pair of PM poles and one coil.

![](images/8e1c7b65580a0f40bc32eeaa26b534df63ff3a36e5f81029074e5b44c0753fa7.jpg)  
Fig.3．Curve fit of the FE computed torque

TABLE II. PARAMETERS OF THECURVE FITTINGEQUATION   

<html><body><table><tr><td>a0</td><td>0.5605</td><td>w</td><td>0.04718</td></tr><tr><td>a1</td><td>0.6784</td><td>b1</td><td>-0.6785</td></tr><tr><td>a2</td><td>-0.0841</td><td>b2</td><td>-0.7752</td></tr><tr><td>a3</td><td>-0.4719</td><td>b3</td><td>-0.3074</td></tr><tr><td>α4</td><td>-0.3559</td><td>b4</td><td>0.1259</td></tr><tr><td>a5</td><td>-0.09836</td><td>b5</td><td>0.2108</td></tr><tr><td>a6</td><td>0.01665</td><td>b6</td><td>0.1033</td></tr><tr><td>a7</td><td>0.0133</td><td>b7</td><td>0.01937</td></tr></table></body></html>

According to the symmetrical characteristics,when the coil is in different positions symmetrical about the PM axis,the torque between the coil anda pair ofPM poles(from inner and outer rotors respectively) is of the same amplitude considering the situation of only one pair of PM poles and one coil. Spinning torque and tilting torque amplitudes are compared with the FE data. The spinning torque and tilting torque fits verywell at the same included angle.The error range is less than $2 \%$ . Thus,through coordinate transformation,the torque between one coil and a pair of PM poles in the 3D space can be obtained.

# B.Torque Model ofSingle Coil in Rotor Frames

Supposing $( r _ { x } , r _ { y } , r _ { z } )$ is the direction vector of any axis in 3D space.Then the rotation matrix $R$ can be expressed as the Eqn. 5 when rotating a $\phi$ degree about the axis.With CEM, the analytical torque model can be obtained when the coil rotates about $Z$ axis.FE results show that when the coil rotates in xy plane, the torque component in $Z$ direction is much larger than in $\mathrm { \Delta } X$ and Y direction.Thus the torque model can be obtained from $( 0 , 0 , T z )$ or $( 0 , T y , 0 )$ rotation.

![](images/69b609bd93b559bc3ce83e63bc46bad76dd0ad52797bcbdaf7b2dea4954579f0.jpg)  
Fig.4．Rotation of the Coil

As shown in Fig.4，spherical coordinate of the coil start point in $\mathbf { \Delta x } \mathbf { Z }$ planeis $( r , \theta , 0 )$ ．The end point is $( r , \theta , \phi )$ ．Then,the torque vector can be obtained from the $\tilde { f } \left( \theta _ { 1 } \right) i \left( \cos \theta _ { 1 } , 0 , \sin \theta _ { 1 } \right)$ by rotating $\theta _ { 2 }$ about $\mathbf { X }$ axis.From Fig. 4, $\theta _ { 1 } , \theta _ { 2 }$ are the functions of $\theta$ and $\phi$ ：

$$
\begin{array} { l } { \theta _ { 1 } = \operatorname { a r c c o s } ( \sin \theta \cos \varphi ) } \\ { \theta _ { 2 } = \operatorname { a r c c o s } ( \sin \theta \cos \varphi ) } \end{array}
$$

Herein,the form of torque rotation matrix is changed into :

$$
R _ { 0 } = \left[ \begin{array} { c c c } { { 1 } } & { { 0 } } & { { 0 } } \\ { { 0 } } & { { \cos \theta _ { 2 } } } & { { \sin \theta _ { 2 } } } \\ { { 0 } } & { { - \sin \theta _ { 2 } } } & { { \cos \theta _ { 2 } } } \end{array} \right]
$$

The torque vector in $( r , \theta , \phi )$ can be calculated through Eqn 9

$$
\mathbf { T } = [ T x , T y , T z ] = [ 0 , \tilde { f } ( \theta _ { 1 } ) , 0 ] \mathbf { R } _ { 0 }
$$

Asshown in Fig.5 and6,the maximum error between the modified analytical model and the FE data is less than $1 \%$

Thus,the torque model of single coil in the rotor frames can be calculated through rotation and superposition.Through rotating for $( i - 1 ) 4 5 ^ { \circ }$ ,the torque model between the $i ^ { t h }$ PM and coil can be obtained.It needs to be pointed out that the torque is opposite due to the alternate PM poles.The result shows that the torque produced by single coil has the mechanical circle of $9 0 ^ { \circ }$ .Fig.7 and Fig.8 show the results in the total rotating area.Where $\theta _ { 1 }$ represents the longitudinal angle,to illustrate the symmetry about the equatorial plane, $9 0 ^ { \bar { \circ } }$ has been deducted.Thus, $\theta$ is from $- 2 0 ^ { \circ }$ to $2 0 ^ { \circ }$ and $\phi 1$ is from $0 ^ { \circ }$ to $3 6 0 ^ { \circ }$ .It can be concluded that the analytical model fits the FE results very well.The rotating torque is symmetrical about the equatorial plane,and is cyclicalin the $\phi$ direction.A total of four cycles exist in this direction.Because of the influences of the alternate PM poles,two peaks and two troughs exist in a cycle.

$$
\begin{array} { r } { R = \left[ \begin{array} { c c c } { \cos \phi + ( 1 - \cos \phi ) r _ { x } ^ { 2 } } & { ( 1 - \cos \phi ) r _ { x } r _ { y } - r _ { z } \sin \phi } & { ( 1 - \cos \phi ) r _ { x } r _ { z } + r _ { y } \sin \phi } \\ { ( 1 - \cos \phi ) r _ { x } r _ { y } + r _ { z } \sin \phi } & { \cos \phi + ( 1 - \cos \phi ) r _ { y } ^ { 2 } } & { ( 1 - \cos \phi ) r _ { y } r _ { z } - r _ { x } \sin \phi } \\ { ( 1 - \cos \phi ) r _ { x } r _ { z } - r _ { y } \sin \phi } & { ( 1 - \cos \phi ) r _ { y } r _ { z } + r _ { x } \sin \phi } & { \cos \phi + ( 1 - \cos \phi ) r _ { z } ^ { 2 } } \end{array} \right] } \end{array}
$$

![](images/623330c14836f231de2c2a79e6d72e3f56ea08d0d0cb488fc6da1c238258ed9a.jpg)  
Fig.5．Comparison of Analytical and FE Torque Results in y Direction

![](images/3d5039f73d8ee319b81478ae230b7614be94952c315b4e6f5c70017430e050f8.jpg)  
Fig.6．Comparison of Analytical and FE Torque Results in $\mathbf { z }$ Direction

![](images/3adff5797dace3e315c229c3af5418892e341c68aa419717f76d5af4627cb2fe.jpg)  
Fig.7．Comparison of Analytical and FE Torque in $z$ Direction Results

![](images/66dca6f72ba2598560838418f930180268a30ed08cdcccd836ae7cbc5c3c7595.jpg)  
Fig.8．Comparison of Analytical and FE Torque in Tilting Direction

# IV.FORMULATION OF MAGNETIC FORCE

To benefit the improvement of the rotor support, magnetic levitation force produced by the interaction of PM poles and the coils can be utilized.Thus magnetic levitation force model isof obvious significance.In this section,itis discussed based on the FE simulation and CFM.The magnetic levitation force can be defined as the force exerted on the rotor in the radial direction by the coils.In other words,the levitation force produced by one coil is the radial projection of the counterforce from the energized coil. So our method is as following: first, the analytical force expression between one PM pole and one coil is obtained with FE data and CFM; second,according to the symmetrical characteristics,the modelis extended to the whole 3D space.

$$
\mathbf { F } _ { r i , j } = - g _ { 0 } \left( \psi _ { i , j } \right) i _ { j } \frac { \mathbf { d } _ { i , j } \bullet \mathbf { s } _ { j } } { \left| \mathbf { s } _ { j } \right| } \frac { \mathbf { s } _ { j } } { \left| \mathbf { s } _ { j } \right| }
$$

Eqn.10 can be departed into three parts: $g _ { 0 } \left( \psi _ { i , j } \right) i _ { j }$ is the amplitude of the force between the PM pole and the coil. $g _ { 0 } \left( \psi _ { i , j } \right) i _ { j }$ is projection of the direction vector of the force on the radial direction. $g _ { 0 }$ is determined by Eqn.11. The third part $- \frac { \mathbf { s } _ { j } } { \left. \mathbf { s } _ { j } \right. }$ is the direction vector of the magnetic levitation force.

$$
g _ { 0 } \left( \psi _ { i , j } \right) = \frac { i _ { j } } { \left| F _ { i , j } \right| }
$$

$$
{ \bf s } _ { j } = { \bf s } _ { j , 0 } R _ { 1 }
$$

$$
R _ { 1 } = { \left[ \begin{array} { l l l } { ~ \cos ( \varphi ) } & { \sin ( \varphi ) } & { 0 } \\ { - \sin ( \varphi ) } & { \cos ( \varphi ) } & { 0 } \\ { ~ 0 } & { ~ 0 } & { 1 } \end{array} \right] }
$$

$$
\mathbf { d } _ { i , j } = \frac { 1 } { \vert \mathbf { F } _ { i , j } \vert } ( F _ { x ( i , j ) } , F _ { y ( i , j ) } , F _ { z ( i , j ) } )
$$

![](images/e1244c06353418647d66eca0e4b137e068302fbeb2958c1c766de4c6b6a923a6.jpg)  
Fig.9.Curve Fit of the FE Computed Torque

![](images/4ca0184febad674b45d17e4669687f77e6ff42f74f0487955008a1067e9a55ec.jpg)  
Fig.10.Comparison of Analytical and FE Magnetic Leviation Force in $\mathbf { \boldsymbol { x } }$ Direction Results

Similar to the process of torque derivation,spherical coordinate of the coil start point in Xz plane is $( r , \bar { \theta } , 0 )$ . The end point is $( r , \theta , \phi )$ .Then,the force vector can be obtained from the $\tilde { g } \left( \theta _ { 1 } \right) i \left( c o s \theta _ { 1 } , 0 , s i n \theta _ { 1 } \right)$ by rotating $\theta _ { 2 }$ about $\mathbf { \boldsymbol { x } }$ axis. $\theta _ { 1 }$ and $\theta _ { 2 }$ are defined in Eqn. 6 and 7. The final form of $\mathbf { F } _ { r ( } i , j )$ can be written as:

$$
\begin{array} { r } { { \bf F } _ { r ( i , j ) } = i _ { j } ( \tilde { g } _ { x } s i n \theta \cos \varphi + ( \tilde { g } _ { y } c o s \theta _ { 2 } - \tilde { g } _ { z } \sin \theta _ { 2 } ) \sin \theta \sin \varphi  } \\ {  + ( \tilde { g } _ { y } \sin \theta _ { 2 } + \tilde { g } _ { z } \cos \theta _ { 2 } ) \cos \theta ) ( s i n \theta \cos \varphi \sin \theta \sin \varphi  \cos \theta ) } \end{array}
$$

The FE force data and the analytical curve of three components ofForce in xz plane are shown in Fig.9.The fit equation form is the same as Eqn.4.The fourier fit type can satisfy the fitting precision very well.Fig.1O,11 and 12 show the comparisons of analytical results with the FE results in 3Dview.It can be concluded that the model is fit with the FE result very well.

# V. CONCLUSION

A novel PM spherical actuator with three-dimensional pole array is proposed in this paper. The torque output and the magnetic leviation force of this spherical actuator are modeled based on the curve fit method with FE results.The analytical model mainly benefits the real-time control and improvement of the bearing of the spherical actuator. According to the geometric characteristics,the 2D fitted models of the torque and magnetic leviation force is successfully extended to the 3D space.Results show good consistence of the analytical model and the FE results.The modeling errors are within the acceptance.Through appropriate correction, the modeling errorshave been reduced toalowerlever. Thus,the analytical models can validate the FE results very well and can be used in the real-time control.

![](images/b77208a339cb66939231fa74dbc028091ea848e6df8a776bfb05a7cc0f43030b.jpg)  
Fig.11．Comparison of Analytical and FE Magnetic Leviation Force in y Direction Results

![](images/a197acd9deb2f70af3310677c06fb6c9726f6dafa6f81a5d45ea6cd9c2d7b22a.jpg)  
Fig.12.Comparison of Analytical and FE Magnetic Leviation Force in z Direction Results

# ACKNOWLEDGMENT

The authors acknowledge the financial support from the National Natural Science Foundation of China (NSFC) under grant 51175O12,the National Key Basic Research Program of China under grant 2014CB046406,NSFC 51235002，the Program for New Century Excellent Talents in University of China under grant NCET-12-OO32,the Fundamental Research Funds for the Central Universities,and the Technology on Aircraft Control Laboratory.

# REFERENCES

in Robotics and Automation,2005.ICRA 2005.Proceedings of the 2005 IEEE International Conference on．IEEE,2005,pp.3646-3651.   
[21]L.Yan,I.-M. Chen,C.K.Lim,G.Yang,and K.-M.Lee,“Modeling and iron-effect analysis on magnetic field and torque output of electromagnetic spherical actuators with iron stator,”Mechatronics,IEEE/ASME Transactions on,vol.17,no.6,pp.1080-1087,2012.   
[22] K.Davey,G.Vachtsevanos,and R.Powers,“The analysis of fields and torques in spherical induction motors,”Magnetics,IEEE Transactions on,vol.23,no.1,pp.273-282,1987.   
[23] L.Yan,I.-M.Chen,G. Yang,and K.-M.Lee,“Analytical and experimental investigation on the magnetic field and torque of a permanent magnet spherical actuator,”Mechatronics,IEEE/ASME Transactions on, vol.11,no.4,pp.409-419,2006.   
[24]L.Yan,H. Meng,N.Yao,and Z.Jiao,“Magnetic field analysis of electromagnetic spherical actuators with multiple radial poles,”in Industrial Informatics(INDIN),20l21OthIEEE International Conference on．IEEE,2012,pp.675-677.   
[25]L.Yan,F.Liang，M.Yuan,H.Hu,C.-Y.Chen,and I.-M.Chen, "Analysis of novel three-dimensional pole arrays for electromagnetic spherical actuators,in Advanced IntelligentMechatronics(AIM),2013 IEEE/ASME International Conference on,July 2013,pp.780-785.   
[26]L.Zhang,W.Chen,L.Yan,and J.Liu,“Trajectory planning and current control optimization of three degree-of-freedom spherical actuator,”in IntelligentRobotsandSystems(IROS)，2Ol1IEEE/RSJInternational Conference on,Sept 2011, pp.744-749.   
[1]L.Yan,L.Zhang，Z. Jiao,H. Hu,C.-Y.Chen,and I.-M.Chen, “Armature reaction field and inductance of coreless moving-coil tubular linear machine” Industrial Electronics,IEEE Transactions on,vol.61, no.12,pp. 6956-6965,2014.   
[2]L.Yan,J. Peng,Z. Jiao,C.-Y.Chen,and I. M. Chen,“Novel permanent magnet linear motor with isolated movers:Analytical, numerical and experimental study,”Review of Scientific Instruments,vol. 85,no.10, p. 105007, 2014.   
[3]F.Wiliams and E.Laithwaite,“A brushless variable-speed induction motor,”Proceedings of the IEE-Part A:Power Engineering,vol.102, no.2,pp.203-210,1955.   
[4]K.-M. Lee and C.-K. Kwan,“Design concept development of a spherical stepper for robotic applications,”Roboticsand Automation, IEEE Transactions on,vol.7,no.1,pp.175-181,1991.   
[5]K.-M.Lee,G. Vachtsevanos,and C.Kwan,“Development of a spherical stepper wrist motor,”Journal of Intelligent and Robotic Systems,vol.1, no. 3,pp. 225-242,1988.   
[6]K.-M. Lee,R.A. Sosseh,and Z.Wei,“Effects of the torque model onthecontrol ofa VRspherical motorControl engineering practice, vol.12,no.11,pp.1437-1449,2004.   
[7]K.-M. Lee,H. Son et al.,“Torque model for design and control of a spherical wheel motor”in Proceedingsof the 2005 IEEE/ASME International Conference on Advanced Intelligent Mechatronics,2005, pp.335-340.   
[8]G. S.Chirikjian and D. Stein,“Kinematic design and commutation of a spherical stepper motor,”Mechatronics, IEEE/ASME Transactions on, vol. 4, no. 4, pp.342-353,1999.   
[9]Q.-j.Wang,Z.Li,and L.Chen,“Kinematic analysis and simulation of permanent magnet spherical stepper actuators,” Journal of System Simulation,vol.17, no.9,pp.2260-2264,2005.   
[10]Z.Qian,Q.Wang,L. Ju,A.Wang,and J.Liu,“Torque modeling and control algorithm of a permanent magnetic_spherical motor,”in Electrical Machines and Systems，2009.ICEMs 2009.International Conference on．IEEE,2009,pp.1-6.   
[11]J.Wang，G.Jewell,and D.Howe,“Analysis,design and control of a novel spherical permanent-magnet actuator,”in Electric Power Applications,IEE Proceedings-,vol.145,no.1． IET,1998,pp.61-71.   
[12]W.Wang,J.Wang,G.Jewell,and D.Howe,“Design and control of a novel spherical permanent magnet actuator with three degrees of freedom,”Mechatronics,IEEE/ASME Transactions on,vol.8,no.4, pp.457-468,2003.   
[13]S.Foong and K.-M. Lee,“Magnetic field-based multi-DOF orientation sensor for PM-based spherical actuators,”in Advanced Intelligent Mechatronics,2009.AIM 2009.IEEE/ASME International Conference on． IEEE,2009,pp.481-486.   
[14]H. Garner, K.-M.Lee et al.,“Development of a vision based orientation sensor,”Proceedings of the Dynamic Systems and Control Division, IMECE,pp.173-180,2000.   
[15]L.Yan,I.-M.Chen,C.K.Lim,G.Yang,and K.-M.Lee,Design, Modeling and Experiments of 3-DOF Electromagnetic Spherical Actuators. Springer, 2011.   
[16]L.Yan,B. Zhu,Z. Jiao,C.-Y.Chen,and I.-M. Chen,“An orientation measurement method based on hall-effect sensors for permanent magnet spherical actuators with 3d magnet array,”Scientific reports,vol.4,no. 6756,2014.   
[17]L.Rossini,O.Chetelat，E.Onillon，and Y.Perriard,“Force and torque analytical models of a reaction sphere actuator based on spherical harmonic rotation and decomposition,’Mechatronics,IEEE/ASME Transactions on,vol.18,no.3,pp.1006-1018,2013.   
[18]H. Son and K.-M. Lee,“Distributed multipole models for_ design and control of PM actuators and sensors,Mechatronics, IEEE/ASME Transactions on,vol.13,no.2,pp.228-238,2008.   
[19]C. Xia,H. Li,and T. Shi,“3-D magnetic field and torque analysis of a novel halbach array permanent-magnet spherical motor” Magnetics, IEEE Transactions on,vol.44,no.8,pp.2016-2020,2008.   
[20]L.Yan,I.-M. Chen,C.K.Lim, G.Yang,W.Lin,and K.-M.Lee, “Torque modeling of a spherical actuator based on lorentz force law”