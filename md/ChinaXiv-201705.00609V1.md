# Decoupled Powered Caster Wheel for Omnidirectional Mobile Platforms

Guilin Yang Ningbo Institute of Material Technology and Engineering China Academy of Sciences,Ningbo, China glyang@nimte.ac.cn

Yuanping Li, Tao Ming Lim, Chee Wang Lim Singapore Institute of Manufacturing Technology Singapore 638075 {ypli, tmlim, cwlim} $@$ SIMTech.a-star.edu.sg

Abstract—this paper presents a novel design of a Powered Caster Wheel (PCW) that decouples the steering and rolling motions.The working principles and mechanical design of the PCW are introduced in details.Kinematic modeling,trajectory planning and control algorithms are derived for PCW-based omnidirectional mobile platforms.To demonstrate the new PCW design， a PCWprototype hasbeen developed andan omnidirectional mobile platform based on the decoupled PCW has also been constructed and tested.

Keywords-powered caster wheel, decoupleddesign, omnidirectional mobile platform.

# I. INTRODUCTION

Omnidirectional wheeled mobile platforms have the ability to move in any direction regardless of the current pose so that they are widely employed to perform tasks in narrow and congested environment. To construct an omni-directional wheeled mobile platform, three types of driving wheels can be employed[1], i.e., the Mecanum wheel, the ball wheel,and the powered casterwheel (PCW).The Mecanum wheel (Fig.1(a)) consists of a drum with a plurality of idle rollers located on its periphery,as disclosedbyFuchs[2].Since all axes of the idle roller are skewed with respect to the axis of the drum,the Mecanum wheel can allow any directional motions when the wheel drum is actively rotating.The ball wheel (Fig.1(b)) has a spherical geometry that can actively move in any direction,as proposed by West [3], Pin [4],and Wada [5]. The PCW (Fig. 1(c))is basically a motorized caster wheel that can create both steering and rolling motions,as proposed by Holmberg and Khatib [6].

![](images/bf85f6cb8dcb9236a1f2c6477640e835f1469a93fa9c3f413bd98dd202c203c4.jpg)  
Figure 1:Three types of driving wheels for omnidirectional mobileplatform

The Mecanum wheel has the drawback of discontinuous wheel contact points,which is also a great source of vibration [6,7].It also has low driving efficiency due to the significant passive rotations of the idle rollers,which is unavoidable for a mobile platform with Mecanum wheels during its steering and side-way motions.

The ball wheel is difficult to implement, as it is not possible to place an axel through the ball without sacrificing its omnidirectional motion capability. Instead, the driving mechanisms are directly placed on the ball wheel.However,as there is no effective way to prevent the wheel from collecting dust and dirt from the floor, the driving mechanisms always have poor working conditions.Furthermore,it is also difficult to uniformly drive the ball wheel to move in an arbitrary direction.

Among the three types of wheels, the PCW is the simplest and most efficient wheel design for a mobile platform to achieve omnidirectional motions [8].Holmberg and Slater disclosed a PCW design (as shown in Fig.2)[9],which has been widely accepted for various omni-directional mobile platforms to provide full mobility and agility.However,there is a major problem in this PCW design,i.e., the coupling effect between the steering and rolling motions of the wheel such that the steering motion will always generate a parasitic rolling motion.Although a control technique can be employed to overcome this coupling effect, the control errors always exist. Asa result, the slip and slid phenomenon is significant in both longitudinal and lateral directions.

![](images/3f7da3856d0b7ffa2954eb621400efdcbd9d78c5ffc3804aaa4c5818865c25de.jpg)  
Figure 2:A patented PCW module formnidirectional mobile platforms [9]

To overcome the drawback of the existing PCW,a novel decoupled PCW design is proposed in this paper. By introducing a 2-DOF planetary gear set between the driving and steering motors,the steering motor provides an additional motion to the power transmission chain of rolling motion, which eventually removes the parasitic motion induced by the steering motion of wheel.

This paper is organized as follows: the working principle and design of the decoupled PCW is introduced in Section II; the kinematic modeling， trajectory planning and motion control methods of a PCW based omnidirectional mobile platform are presented in Section II; the paper is summarized in Section IV.

# II. DECOUPLED POWERED CASTER WHEEL DESIGN

# A．WorkingPrinciple

As shown in Fig.3,a decoupled PCW design is proposed so that the rolling and steering motions of the wheel can be independently and precisely controlled by the driving motor and steering motor, respectively [10]. Its working principle is described as follows.

![](images/b3557ec34878a9abc0a4f28c5a7dbb883316c22f14d93ceaf8d4ed0a486a4491.jpg)  
Figure 3: Schematic drawing of the decoupled powered caster wheel design [10]

The steering motion of the wheel is independently driven by the steering motor with the following transmission sequence Steering Motor (Pulley 5) $\Rightarrow$ Pulley 6 (Wheel Frame) $\Rightarrow$ Steering motion. However,if Bevel Gear 1 does not rotate at the same speed of the Wheel Frame,the Bevel Gear 2 will rotate as its axle is fixed on the Wheel Frame.For the conventional PCW design，Bevel Gear 1 is independently controlled by the Driving Motor such that when the driving motor is locked,Bevel Gear 1 will not move.Hence，an additional rolling motion of the wheel will be created when the Wheel Frame rotates during the steering motion of the wheel.

In this design, the steering motor is also connected to the Bevel Gear 1 through a 2-DOF planetary gear set with the following transmission sequence: Steering Motor $( { \mathrm { P u l l e y ~ } } 3 ) \Rightarrow$ Pulley4 (Ring Gear) $\Rightarrow$ Carrier (Bevel Gear1).By choosing a proper gear ratio for this power transmission chain, the additional motion input to Bevel Gear1 by the steering motor can fully remove the parasitic rolling motion induced by the steering motion of the wheel.

The rolling motion the wheel is driven by the Driving Motor with the following transmission sequence:Driving Motor (Pulley 1) $\Rightarrow$ Pulley 2 (Sun Gear) $\Rightarrow$ Carrier (Bevel Gear 1) $\Rightarrow$ Bevel Gear 2 (Pulley 7) $\Rightarrow$ Pulley8 (Wheel) $\Rightarrow$ Rolling motion. Although the steering motor provides an additional motion input to Bevel Gear 1,it is only utilized to remove the parasitic rolling motion. Through such a novel PCW design， the rolling and steering motions can be independently and precisely controlled by the driving motor and steering motor,respectively.

# B. Design Analysis

The major purpose of the decoupled PCW design analysis is to determine the require gear ratios for its rolling and steering transmission chains.To facilitate the description of the design analysis,the following nomenclatures are adopted:

（204号 ${ \mathfrak { o } } _ { d }$ - the input angular velocity of the driving motor （204号 ${ \mathfrak { o } } _ { s }$ - the input angular velocity of the steering motor ${ { \bf { \omega } } _ { \omega _ { r } } }$ - the output angular velocity of the rolling motion of the wheel   
（20 ${ \mathfrak { o } } _ { w s }$ - the output angular velocity of the steering motion of the wheel   
（20 ${ \mathfrak { o } } _ { r s }$ - the angular velocity of the rolling motion of the wheel induced by the steering motion   
（204号 ${ \mathfrak { \omega } } _ { s u n }$ - the angular velocity of the sun gear   
（204号 ${ { \bf { \omega } } _ { { \omega } _ { r i n g } } }$ - the angular velocity of the ring gear   
（ ${ \mathfrak { o } } _ { c a r r i e r } .$ - the angular velocity of the carrier   
$i _ { p 1 } = \frac { z _ { p 2 } } { z _ { p 1 } } -$ ²-the gearratio of the puley-belt set1 where （204 $z _ { p 1 }$ and $z _ { p 2 }$ represent the teeth numbers of pulleys 1 and 2, respectively.   
4-the gear ratioof the pully-belt set 2 where $z _ { p 3 }$ and $z _ { p 4 }$ represent the teeth numbers of pulleys 3 and 4, respectively.   
$\begin{array} { r } { i _ { p 3 } = \frac { z _ { p 6 } } { z _ { p 5 } } - } \end{array}$ -the gear ratio of the pulley-belt set 3 where （20 $z _ { p 5 }$ and $z _ { p 6 }$ represent the teeth numbers of pulleys 5 and 6,respectively.   
$\begin{array} { r } { i _ { p 4 } = \frac { z _ { p 8 } } { z _ { p 7 } } - } \end{array}$ p- the gear ratio of the pulley-belt set 4 where $z _ { p 7 }$ and $z _ { p 8 }$ represent the teeth numbers of pulleys 7 and 8,respectively.

· $\begin{array} { r } { i _ { b } = \frac { z _ { b 2 } } { z _ { b 1 } } - } \end{array}$ the gear ratio of the bevel-gear set where $\boldsymbol { z } _ { b 1 }$ （20 and $z _ { b 2 }$ represent the teeth numbers of bevel gears 1 and 2,respectively. $\scriptstyle \alpha = { \frac { z _ { r } } { z _ { s } } } \ -$ the characteristic parameter of the planetarygear set where $z _ { r }$ and $\boldsymbol { z _ { s } }$ represent the teeth numbers of ring gear and sun gear, respectively.

As shown in Fig.3,the output angular velocity of the steering motion $\omega _ { w s }$ is given by:

$$
\begin{array} { r } { \omega _ { w s } = \frac { \omega _ { s } } { i _ { p 3 } } } \end{array}
$$

Equation (1） indicates that the steering motion only depends on the motion of the steering motor. However,the steering motion will induce an additional rolling motion $\omega _ { r s }$ ， which is written as:

$$
\begin{array} { r } { \omega _ { r s } = - \frac { \omega _ { s } } { i _ { p 3 } i _ { b } i _ { p 4 } } } \end{array}
$$

For the planetary gear set, the angular velocity relationship among the sun gear $( \mathfrak { o } _ { s u n } )$ , the ring gear $( \mathfrak { \omega } _ { r i n g } )$ ,and the carrier $( \mathfrak { o } _ { c a r r i e r } )$ is as follows:

$$
\omega _ { s u n } + \alpha \omega _ { r i n g } - \left( 1 + \alpha \right) \omega _ { c a r r i e r } = 0
$$

$$
\begin{array} { r } { \omega _ { w r } = \frac { \omega _ { r } } { ( 1 + \alpha ) i _ { b } i _ { p 1 } i _ { p 4 } } } \end{array}
$$

$$
\begin{array} { r } { \omega _ { c a r i e r } = \frac { \frac { \omega _ { r } } { i _ { p 1 } } + \frac { \alpha \omega _ { s } } { i _ { p 2 } } } { ( 1 + \alpha ) } } \end{array}
$$

$$
\begin{array} { r c l } { \omega _ { w r } } & { = } & { \frac { \omega _ { c a r r i e r } } { i _ { b } i _ { p 4 } } + \omega _ { r s } } \\ & { = } & { \frac { \frac { \omega _ { r } } { i _ { p 1 } } + \frac { \omega _ { \omega _ { s } } } { i _ { p 2 } } } { ( 1 + \alpha ) i _ { b } i _ { p 4 } } - \frac { \omega _ { s } } { i _ { p 3 } i _ { b } i _ { p 4 } } } \\ & { = } & { \frac { \omega _ { r } } { ( 1 + \alpha ) i _ { b } i _ { p 1 } i _ { p 4 } } + \frac { [ \alpha i _ { p 3 } - ( 1 + \alpha ) i _ { p 2 } ] \omega _ { s } } { ( 1 + \alpha ) i _ { b } i _ { p 2 } i _ { p 3 } i _ { p 4 } } } \end{array}
$$

When Eq.(7) is satisfied, the output angular velocity of the rolling motion is given by:

# C.Mechanical Design

flexibility for performance optimization by adjusting the three independent parameters.

Therefore, the output angular velocity of the rolling motion of the wheel is given by:

Based on the kinematic diagram(as shown in Fig.3） as well as the kinematic formulations presented above,a typical mechanical design of the decoupled powered caster wheel has beencompleted.Figure 4 shows the front,left and back views of the powered caster wheel design,respectively.The selected design parameters are listed in Table 1.Based on Eqs.(1)and (8),the gear ratios for the steering and rolling transmission chains are 4 and 8, respectively.

Equation (5) indicates that the resultant rolling motion of the wheel depends on the motion inputs from both the driving motor and the steering motor.However, the rolling motion will be decoupled from the motion input of the steering motor when the following condition is satisfied:

$$
\alpha i _ { p 3 } - ( 1 + \alpha ) i _ { p 2 } = 0
$$

Rearranging Eq. (4), it yields:

$$
\begin{array} { r } { \alpha = \frac { i _ { p 2 } } { i _ { p 3 } - i _ { p 2 } } } \end{array}
$$

From Eq. (7), it can be depicted that if the values of $\alpha , i _ { p 2 }$ and $i _ { p 3 }$ are appropriately selected to make Eq.(5) valid, the rolling motion will be decoupled from the motion input of the steering motor.In other words,to achieve decoupled motion characteristics for the PCW,only one equation,i.e.,Eq.(7) needs to besatisfied, which involvesthreekinematic parameters. Therefore， the PCW design possesses high 电丰真

Table 1: Design parameters of the decoupled PCW   

<html><body><table><tr><td>Design Parameters</td><td>Values</td></tr><tr><td>i1</td><td>2</td></tr><tr><td>ip2</td><td>3</td></tr><tr><td>ip3</td><td>4</td></tr><tr><td>ip4</td><td>1</td></tr><tr><td>ib</td><td>1</td></tr><tr><td>α</td><td>3</td></tr></table></body></html>

To valid the design and performance of the proposed decoupled PCW,a research prototype has been developed as shown in Fig.5.To simplify the control scheme,smart motors from Animatics SmartMotorTM[12],which has integrated driver and controller, have been employed in the prototype development.

![](images/83ae9348fc66532449c01c0be10d58fb3f3e37e4e4c63903a6893a7d1213f0a1.jpg)  
Figure 4: Mechanical design of the decoupled PCW   
Figure 5:Prototype of the decoupled PCW module

The advantages of the novel decoupled PCW design are summarized as follows:

1 It is capable of performing decoupled rolling and steering motions with two independently controlled motors. It has the merits of simplified control scheme and reduced the slip and slid motions. It allows the two driving motors to be mounted onto the base so to simplify the wiring scheme. It has the flexibility to adjust the kinematic parameters so to achieve optimized performance. The mechanical design of the decoupled PCW employs a number of pulley-belt drives,which is able to reduce the vibration of system.It also offers the advantages for ease of assembly,adjustment, and maintenance.   
. The decoupled rolling and steering motion characteristic is independent with the offset between the rolling and steering axis.As a result,the offset is free for adjustment in the design stage.

# III. OMNIDIRECTIONAL MOBILEPLATFORMBASED ON DECOUPLED PCWMODULES

As each decoupled PCW module is able to produce two independent motions,i.e., steering and rolling motions,an omnidirectional mobile platform can be constructed with at least two PCW modules.Figure 7 shows an omni-directional mobile platform constructed with three identicalPCW modules.

# A.Kinematic Modeling of the decoupled PCW

In an omnidirectional mobile platform, a PCW module can be modeled as a 3-DOF serial kinematic chain (as shown in Fig 5), in which the rolling $( \rho )$ and steering $( \varphi )$ joints are active, while the twisting $( \sigma )$ joint is passive [6].The differential kinematics of one PCW module is given by

$$
\dot { x } = J _ { i } \dot { \bf q } _ { \mathrm { i } }
$$

where $\dot { \mathbf { x } } { = } [ \mathbf { v } \quad \mathbf { w } ] ^ { \mathrm { T } } { \in } \mathfrak { R } ^ { 3 \times 1 }$ represents the motion of the platform W.r.t.theplatformframe $X _ { B } B Y _ { B }$ ； $\dot { q } _ { i } = [ \dot { \sigma } _ { i } \quad \dot { \rho } _ { i } \quad \dot { \varphi } _ { i } ] ^ { T }$ represents the wheel's joint velocity vector，and $J _ { i }$ is the Jacobian of wheel $i$ 0 $( i ~ = ~ 1$ .…,，n; n - number of PCW modules）,which is given as:

$$
J _ { i } = \left[ { - h \cos ( \beta _ { i } ) - b \cos ( \beta _ { i } - \varphi _ { i } ) } \quad { - r \cos ( \beta _ { i } - \varphi _ { i } ) } \quad h \sin ( \beta _ { i } ) \right]
$$

where $r$ and $b$ are the radius and offset of the PCW; $h$ and $\beta _ { i }$ are location parameters for steering axis of wheel $i$ W.r.t. the platform frame $X _ { B } B Y _ { B }$ $\varphi _ { i }$ is the steering angle of wheel $i$

It is not difficult to verify that the determinant of matrix $J _ { i }$ is always a constant $- b r$ which implies that $J _ { i }$ is always full rank.The invertabilityof $J _ { i }$ also implies that the mobile platform is omnidirectional if at least two PCW modules are employed [11].

![](images/50da1d074fbfbc14320f97a0483cbe20a7746b31fb3e802e56a389fa2314477d.jpg)  
Figure 6:Kinematic diagramof a powered caster wheel

![](images/bbdc420629a2b133ea562d637f8e4d8d6f60a01d287366928cfbcb395a88119b.jpg)  
Figure 7:Kinematic diagram of an omnidirectional mobile platform based on decoupled PCW modules

As shown in Fig.7, the platform frame $X _ { B } B Y _ { B }$ is defined as the frame attached to the center of the mobile platform and moves with the platformbase.The location of the wheel with respect to the platform frame $X _ { B } B Y _ { B }$ is defined by vector $h _ { i }$ forming an angle $\beta _ { i }$ with the $X$ axis of the platform frame $X _ { B } B Y _ { B }$ .The contact point between the wheel $i$ and the ground is defined as point $C _ { i }$ and its position with respect to frame $X _ { B } B Y _ { B }$ is defined as $P _ { C _ { i } }$ . A wheel frame $X _ { C i } C _ { i } Y _ { C i }$ is defined with its origin at point $C _ { i }$ ，with axis $Y _ { C i }$ defined along the translational motion of the wheel and the axis $X _ { C i }$ perpendicular to $Y _ { C i }$ S0 that it results in axis $Z _ { C i }$ pointing vertically upwards. Each PCW module is capable of producing steering and rolling motions. The steer angle for wheel $i$ is defined as $\varphi _ { i }$ and the rolling angle as $\rho _ { i }$ . The wheel has an offset of length $b$ and radius $r$ ：

The kinematics of the mobile platform can be derived by equating the velocities of the wheel-floor contact points $C _ { i }$ as generated by the task space velocity at the center of the platform ( $\mathbf { \Psi } ( \dot { x } = [ v \mathbf { \Psi } \textbf { \textit { w } } ] ^ { T } )$ and those generated by the joint spacevelocities $\dot { \mathbf { \Omega } } \dot { q } = [ \dot { \varphi } _ { i } \dot { \quad } \dot { \rho } _ { i } \dot { \quad } \dots \dot { \quad } \dot { \varphi } _ { N } \dot { \quad } \dot { \rho } _ { N } ] ^ { T } \mathbf { \Omega } )$ .When expressed in the platform frame $X _ { B } B Y _ { B }$ ,it is described by the following equation:

$$
v + \omega \times p _ { C _ { i } } = b \dot { \varphi } _ { i } x _ { C _ { i } } + r \dot { \rho } _ { i } y _ { C _ { i } }
$$

where $x _ { C _ { i } }$ and $y _ { C _ { i } }$ are the axis vectors of the wheel frame expressed with respect to the platform frame $X _ { B } B Y _ { B }$ and are given as

$$
\begin{array} { r l } & { { x _ { C } } _ { i } = \left[ \begin{array} { l } { - \sin ( \beta _ { i } - \varphi _ { i } ) } \\ { \cos ( \beta _ { i } - \varphi _ { i } ) } \end{array} \right] } \\ & { { y _ { C } } _ { i } = \left[ \begin{array} { l } { - \cos ( \beta _ { i } - \varphi _ { i } ) } \\ { - \sin ( \beta _ { i } - \varphi _ { i } ) } \end{array} \right] } \end{array}
$$

Vector $t _ { C _ { i } }$ is obtained by rotating $P _ { C _ { i } }$ by $9 0 ^ { \circ }$ keeping the same magnitude. The result of the cross product $\omega \times p _ { C _ { i } }$ is simplified as $\omega t _ { C _ { i } }$ where $\omega$ is the scalar value of the rotation of the platform around the vertical $z$ axis.Therefore,Eq.(11) can be rearranged into

$$
\begin{array} { r l } { \big [ I _ { 2 \times 2 } } & { { } t _ { C _ { i } } \big ] \Big [ _ { \omega } ^ { v } \Big ] = \big [ b x _ { C _ { i } } \quad r y _ { C _ { i } } \big ] \Big [ \dot { \varphi } _ { i } \Big ] } \end{array}
$$

For convenience,Eq.(12) can be expressed with respect to wheel frame $X _ { C i } C _ { i } Y _ { C i }$ to reveal the individual contribution of the steering and rolling motions of wheel $i .$ This is done by pre-multiplying both sides of the equation with rotation matrix $\boldsymbol { R _ { B } } = [ \mathcal { X } _ { C _ { i } } \quad y _ { C _ { i } } ] ^ { \scriptscriptstyle T }$ . The resulting equation of motion for the mobile platform,taking into account all the available joints,is expressed as

$$
A { \dot { x } } = B { \dot { q } }
$$

where

$$
A = { \left[ \begin{array} { l } { x _ { C _ { i } } \quad x _ { C _ { i } } t _ { C _ { i } } } \\ { y _ { C _ { i } } \quad y _ { C _ { i } } t _ { C _ { i } } } \\ { \qquad \vdots \quad \vdots } \\ { x _ { C _ { n } } \quad x _ { C _ { n } } t _ { C _ { n } } } \\ { y _ { C _ { n } } \quad y _ { C _ { n } } t _ { C _ { n } } { \mathrm { ] } } } \end{array} \right] }
$$

$$
B = \left[ \begin{array} { c c c c c } { b _ { 1 } } & { 0 } & { \cdots } & { 0 } & { 0 } \\ { 0 } & { r _ { 1 } } & { \cdots } & { 0 } & { 0 } \\ { \vdots } & { 0 } & { \ddots } & { 0 } & { 0 } \\ { 0 } & { 0 } & { \cdots } & { b _ { n } } & { 0 } \\ { 0 } & { 0 } & { \cdots } & { 0 } & { r _ { n } } \end{array} \right]
$$

The odd and even rows in Eqs.(16) and(17) describe the relationship of the velocities at the center of the platform with the velocities generated by the steering joint $\varphi _ { i }$ and the rolling joint $\rho _ { i }$ of wheel $i ,$ respectively.

# B. Trajectory Planning

Trajectory planning is very critical to achieve smooth motion control for an omnidirectional mobile platform. There are various techniques to plan a smooth trajectory and the polynomial based method is the most popular one.

Due to the agile motion capability of omnidirectional mobile platforms,the dynamics effect is very significant for the motion control of omnidirectional mobile platforms with steerable wheels such as PCW modules Therefore,it is important to use high order polynomials for the trajectory planning such that the position,velocity and acceleration and even jerk set-points are all smooth.Moreover, the order of the polynomial should be high enough so that users can specify sufficient boundary conditions to improve the smoothness of the desired motion.However,too high order polynomial trajectorywill introduce multiple acceleration and deceleration phases between every two via-points which reduce the motion efficiency.

Based on the analysis,the quintic polynomial (polynomial of degree 5) based trajectory planning method has been adopt to generate smooth motion set-points.The benefits of quintic polynomial are as follows:the motion set-points for position, velocity,acceleration and jerk are all smooth;end users are free to specify boundary conditions for positions,velocities and accelerations; there is only one deceleration phase between every two via-points. As an example,the position, velocity and acceleration trajectories of a straight line motion in the XY plane based on quintic polynomial are shown in Fig. 8.

![](images/dd1313230d7acc6a0a82db7315da5de96cac9af8e7c70969f2aab6660c01eae4.jpg)  
Figure 8: Quintic polynomial based trajectory planning

# C.Dual Loop Velocity Control

Unlike fixed base robot manipulators where the position control is dominantly adopted for their motion control, velocity control is more suitable for mobile platform motion control because the absolute position of the platform is obtained through odometry,i.e.integration of the platform velocity. In order to implement velocity control,differential kinematic model is required. Based on Eq.(15),the inverse differential kinematics of the mobile platform is given as

$$
\dot { q } = B ^ { - 1 } A \dot { x }
$$

It is obvious that square matrix $B$ is always invertable and thus the inverse differential kinematics is always unique. Similarly,the forward differential kinematics is obtained by inverting the matrix $A$ in Eq.(15).However, matrix $A$ is nonsquare and thus its general inverse is often given as the left pseudo-inverse denoted $\mathbf { A _ { L P I . } }$ According to the definition, left pseudo-inverse of a non-square matrix is represented as

$$
\mathrm { A } _ { \mathrm { L P I } } = ( \mathrm { A } ^ { \mathrm { T } } \mathrm { A } ) ^ { - 1 } \mathrm { A } ^ { \mathrm { T } }
$$

Hence,the forwarddifferentialkinematicsis formulatedas

$$
\dot { \mathbf { x } } = \mathsf { A } _ { \mathrm { L P I } } \mathsf { B } \dot { \mathbf { q } }
$$

In order to improve the robustness of the motion control, it is proposed to adopt the dual loop velocity control structure for the mobile platform with the decoupled PCW.The proposed dual loop control structure will close the control loop in both the Cartesian space and joint space of the mobile platform as shown in Figure 9.It can be shown that the outer loop is the Cartesian space velocity control while the inner loop is the joint space velocity control. The forward differential kinematics is utilized in the outer Cartesian space velocity loop to obtain the actual Cartesian space velocity $\dot { x } _ { a c t }$ . The inverse differential kinematics is used in the inner joint space velocity control to compute the desired joint velocity set-points $\dot { q } _ { d e s }$

It is noticed that in both the outer and inner velocity control loops,PI control is employed instead of PID control which is standard in most controller design. The reason is that only encoders are used in most actuator servo control,joint velocities are obtained by computing the back-differences of the joint angles.Therefore,to implement differential control using velocity computed by back-difference is not effective.

![](images/1f37f111a7607b3cbe67fbdb7b582947af995312cd3dba383a7de2f2188222db.jpg)  
Figure 9:Dual loop velocity control block diagram

The PI control of both the inner and outer loops are given by

$$
\begin{array} { r } { \dot { x } _ { C } = K _ { I } ( x _ { d e s } - x _ { a c t } ) + K _ { P } ( \dot { x } _ { d e s } - \dot { x } _ { a c t } ) } \\ { \Gamma = K _ { I } ( q _ { d e s } - q _ { a c t } ) + K _ { P } ( \dot { q } _ { d e s } - \dot { q } _ { a c t } ) } \end{array}
$$

where the outputs of both control loops are the commanded Cartesian space velocity vector $\dot { x } _ { C }$ and the joint torque vector $\boldsymbol { \varGamma }$ ,respectively.

To demonstrate the effectiveness of the decoupled PCW design,an omnidirectional mobile platform has been developed, asshown in Fig.10.With three decoupled PCW modules, the mobile platform is able to achieve omnidirectional motions such as zero-radius steering，side-way motions,and spiral motions. The actual motion control performance of the prototype will be investigated in the future.

# IV. CONCLUSION ANDFUTUREWORK

The decoupled PCW module presents many merits for constructingomnidirectional mobileplatformssuchas simplified control scheme,reduced the slip and slid motions, high driving efficiency,and simple wiring scheme.It is expected that the proposed decoupled PCW will have a wide adoption by the industry to develop omnidirectional mobile platforms for various in-door applications.Future works will be focused on the implementation of the proposed trajectory planning and motion control algorithms.

![](images/893dcf24c9cf338ca653f787b42a4bb2eb4764113f477e19079eb375b1b3ecc9.jpg)  
Figure 10: An omnidirectional mobile platform prototype withthreedecoupledPCW

# REFERENCES

[1] P.Muir and C.P.Newman,“Kinematic modeling of wheeled mobile robots,”Journal of Robotic Systems,vol.4,no.2,pp.281-340,1987.   
[2] C.Fuchs,“Rad,das eine unmittelbare Fortbewegung in jeder Richtung gestattet," German Patent # 822660,Class 63d,Group 1,July8,1949.   
[3] A.M.T.West,“Omnidirectional vehicle,”U.S.Patent # 5,186,270, February16,1993.   
[4] F.G.Pin and S.M.Killough,“Omni-directional and holonomic rolling platform with decoupled rotational and translational degrees of freedom,”U.S.Patent#5374879,December20,1994.   
[5] M.Wada,“Omnidirectional vehicle and method of controlling the same,"U.S.Patent # 6408230,June 18,2002.   
[6] R.Holmberg and O.Khatib,“Development and Control of a Holonomic Mobile Robot for Mobile Manipulation Tasks,”The International JournalofRoboticsResearch,Vol.19,No.11,1066-1074,2000.   
[7] J.Alexander and J.Maddocks,“On the kinematics of wheeled mobile robots,”The International Journal of Robotics Research,vol.8,no.5, pp.15-27,1989.   
[8] A.Shenawy A.Wellenreuther,and E.Badreddi，Practical evaluation for two different holonomic wheeled mobile robots,20o8 IEEE International Conference on Systems,Man and Cybernetics,pp.3102- 3107,2008.   
[9] R.Holmberg and J.C. Slater P,“Powered caster wheel module for use on omni-directional drive systems",U.S.Patent # 6491127,Dec 10, 2002.   
[10]G.Yang,C.W.Lim,T.M.Lim,C.J.Kong,“Powered caster wheel Assembly",WO2010/039102A1,Sep 30,2008.   
[11]Campion G,Bastin G,Dandrea B(1996)Structural properties and classification of kinematic and dynamic models of wheeled mobile robots.IEEE Trans Robot Autom 12(1):47

[12] http://www.animatics.com