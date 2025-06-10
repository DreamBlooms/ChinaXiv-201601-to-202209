# Fuzzy sliding mode controller with integral sliding surface for permanent magnet synchronous motor

Jing Wang2heng-eZang2bY $^ { I }$ Key Laboratory of Microwave Remote Sensing, CAS Beijing100190,China ²National Space Science Center, CAS Beijing100190,China $^ 3$ University of Chinese Academy of Sciences Beijing,100190,China igjingcoral@126.com,bzhangshengwei@mirslab.cn,zhangyu@mirslab.cn

In this paper,sliding mode controller with integral sliding surface is proposed to reject the system disturbances for permanent magnet synchronous motor (PMSM） speed regulation system.To reduce the chattering phenomenon,the signum function is replaced by the saturation function and fuzzy module is introduced in sliding mode controller. Simulation results show that the proposed control method can obtain satisfactory tracking performance and dynamic performance with smaller chattering.

Keywords:Permanent Magnet Synchronous Motor (PMSM);Speed Regulation System;   
Fuzzy Sliding Mode Controller (FSMC); Integral Sliding Surface.

# 1．Introduction

Permanent magnet synchronous motor (PMSM) has been widely used in many fields due to its high power density,high efficiency,low inertia and reliable operation. The method of speed regulation system is important to improve the dynamic performance.The Field Orientation Control (FOC） strategy is used in speed system regulation, and there are many different forms for FOC strategy [1,2]. The FOC strategy always includes speed loop and current loop.In this paper，Current Hysteresis Band Pulse Width Modulation (CHBPWM）is introduced to control the three-phase stator current and its structure is shown in Figure 1. CHBPWM is the fastest strategy in current closed-loop controlling.

In PMSM system, there are many disturbances and uncertainties such as load disturbances, friction force and parameter uncertainties. Therefore, many intelligent algorithms and nonlinear control strategies are introduced to improve the system performances, e.g.,artificial neural network (ANN) [3], fuzzy control [4], active disturbance rejection control (ADRC)[5], sliding mode control (SMC) [6],and so on. The SMC is widely used for its invariant property to uncertain internal parameter variations and external disturbances.However,the SMC has a chattering phenomenon which can excite high frequency dynamic performance. In [7],a new exponential reaching law of sliding mode control is proposed to reduce the chattering.In [8],sliding mode based model predictive controller is proposed to track the desired currents in finite time.

In this paper, fuzzy sliding mode controller with integral sliding surface is proposed to suppress chattering and improve the reaching speed. Simulation results show that the proposed method is able to improve the dynamic performance and robustness characteristics of speed servo system compared with the PI controller.

![](images/4bbd94c917b721238759a02e843b27bbf2a2216c580e770ab5755febfbd71435.jpg)  
Fig.1.The structure of PMSM speed regulation system.

# 2. Model of PMSM System

Assume that magnetic circuit is unsaturated, hysteresis and eddy current lose are ignored, the distribution of the magnetic field is sine space and the variations of the motor parameters are ignored.In the $\mathtt { d - q }$ rotor reference frame,a surfacemounted PMSM can be expressed as the following dynamic equations.

(i) Voltage dynamic equations:

$$
\begin{array} { c } { { u _ { d } = R _ { s } i _ { d } + \displaystyle \frac { d \psi _ { d } } { d t } - \omega _ { e } L _ { q } i _ { q } } } \\ { { u _ { q } = R _ { s } i _ { q } + \displaystyle \frac { d \psi _ { q } } { d t } + \omega _ { e } L _ { d } i _ { d } + \omega _ { e } \psi _ { f } } } \end{array}
$$

where $u _ { d } , u _ { q }$ are the $\mathrm { ~ d ~ }$ -axis and $\mathsf { q }$ -axis stator voltages; $i _ { d } , i _ { q }$ are the ${ \mathrm { d } } { \mathrm { } }$ -axis and $\mathfrak { q }$ -axis stator currents; $\psi _ { d } , \psi _ { q }$ are the d-axis and $\mathsf { q }$ -axis stator flux linkage; $L _ { d } , L _ { q }$ are the $\mathrm { ~ d ~ }$ -axis and $\mathsf { q }$ -axis stator inductances and $L _ { d } = L _ { q } = L ; R _ { s }$ is the stator resistance; $\psi _ { f }$ is the rotor flux linkage; $\omega _ { e }$ is the electrical angular velocity.

(ii) Flux linkage dynamic equations:

$$
\begin{array} { c } { { \psi _ { d } = L _ { d } i _ { d } + \psi _ { f } } } \\ { { \psi _ { q } = L _ { q } i _ { q } . } } \end{array}
$$

(iii) Electromagnetic torque dynamic equation:

$$
T _ { e } = 1 . 5 n _ { p } [ \psi _ { f } i _ { q } + ( L _ { d } - L _ { q } ) i _ { d } i _ { q } ] = 1 . 5 n _ { p } \psi _ { f } i _ { q }
$$

where $n _ { p }$ is the number of pole-pairs, $T _ { e }$ is the electromagnetic torque. (iv) Mechanical dynamic equation:

$$
T _ { e } = J \frac { d \omega _ { r } } { d t } + T _ { L } + B \omega _ { r }
$$

where $\omega _ { r }$ is the mechanical angular velocity and $\omega _ { r } = \omega _ { e } / n _ { p } ; J$ is the system moment of inertia; $B$ is the viscous friction coefficient; $T _ { L }$ is the load torque.

According to Eq. (1) to Eq. (4), the $\mathrm { ~ d ~ }$ -axis reference current $\mathrm { i _ { d } ^ { * } }$ is set to zero, and we can get the following relationship between $\dot { \omega _ { \mathrm { r } } }$ and $\mathrm { i } _ { \mathrm { q } }$

$$
\dot { \omega _ { r } } = \frac { 1 . 5 n _ { p } \psi _ { f } } { J } i _ { q } - \frac { B } { J } \omega _ { r } - \frac { T _ { L } } { J } .
$$

To obtain the relationship between $\dot { \omega _ { r } }$ and $i _ { q } ^ { * }$ ,Eq. (5) is rewritten as:

$$
\overset { \cdot } { \omega _ { r } } = \frac { 1 . 5 n _ { p } \psi _ { f } } { J } i _ { q } ^ { \ast } + d ( t )
$$

where $i _ { q } ^ { * }$ is the $\mathsf { q }$ -axis reference current; $d ( t )$ is the disturbance of the system and it is defined as:

$$
d ( t ) = - \frac { 1 . 5 n _ { p } \psi _ { f } } { J } ( i _ { q } ^ { * } - i _ { q } ) - \frac { B } { J } \omega _ { r } - \frac { T _ { L } } { J } .
$$

# 3.Design of Fuzzy Sliding Mode Speed Controller

# 3.1. Design of sliding surface

In [6]-[8],the sliding surface contains the differential of speed error.In some low speed servo systems,the differential operation will introduce high frequency noise.This may cover the real speed error and the whole system will be unstable. In this paper, the integral of speed error is added to the sliding surface as shown in Eq. (8). Torque is more smooth and steady state error is reduced by adopting integral sliding surface [9].

$$
s = e + c \int _ { 0 } ^ { t } e ( \tau ) d \tau
$$

where $s \in R$ is the sliding surface, $e$ is the speed error which is defined as $e = \omega _ { r } ^ { * } - \omega _ { r } ,$ $\omega _ { r } ^ { * }$ is the reference mechanical angular velocity, $c$ is a design positive value which is met the Hurwitz condition.

# 3.2. Design of sliding mode control law

The control law $u ( u = i _ { q } ^ { * } )$ contains equivalent control law $u _ { e q }$ and switching control law $u _ { s w }$ ，and $u = u _ { e q } + u _ { s w }$ ．Equivalent control law controls the certainty of system and maintains the system states on the sliding surface. Switching control law forces the system states to approach the stable point by high-frequency switching. By setting $\dot { s } = 0$ and $d ( t ) = 0$ , we can get $u _ { e q }$ just as shown in the following equation:

$$
\begin{array} { l } { { \displaystyle { \dot { s } } = { \dot { \mathrm { e } } } + c e } } \\ { ~ = { \dot { \omega _ { r } ^ { * } } } - { \dot { \omega _ { r } } } + c e } \\ { ~ = { \dot { \omega _ { r } ^ { * } } } - \frac { 1 . 5 n _ { p } \psi _ { f } } { J } { \dot { u _ { q } } } - d ( t ) + c e = 0 } \end{array}
$$

hence

$$
u _ { e q } = \frac { c J } { 1 . 5 n _ { p } \psi _ { f } } e + \frac { J } { 1 . 5 n _ { p } \psi _ { f } } \dot { \omega _ { r } ^ { * } } .
$$

Switching control law $\mathtt { u } _ { s _ { \mathsf { W } } }$ is selected as:

$$
u _ { s w } = \frac { J } { 1 . 5 n _ { p } \psi _ { f } } \eta \cdot s i g n ( s )
$$

where $\eta > | d ( t ) | , s i g n ( \cdot )$ is a signum function. To reduce the chattering,the signum function is replaced by the saturation function $s a t ( \cdot )$ ,shown as:

$$
s a t ( \mathrm { s } ) = { \left\{ \begin{array} { l l } { s / \Delta } & { ( | \mathrm { s } | \leq \Delta ) } \\ { s i g n ( s ) } & { ( | \mathrm { s } | > \Delta ) } \end{array} \right. }
$$

where $\varDelta$ is the thickness of the boundary layer neighboring the sliding surface, and this is a design parameter. Therefore,the control law is written as:

$$
i _ { q } ^ { * } = u = u _ { e q } + u _ { s w } = \frac { c J } { 1 . 5 n _ { p } \psi _ { f } } e + \frac { J } { 1 . 5 n _ { p } \psi _ { f } } \dot { \omega _ { r } ^ { * } } + \frac { J } { 1 . 5 n _ { p } \psi _ { f } } \eta \cdot s a t ( s ) .
$$

# 3.3.Stability analysis

To set up the existence condition of the sliding mode,the Lyapunov function candidate is defined as:

$$
V = { \frac { 1 } { 2 } } s ^ { 2 } .
$$

Taking the derivation of $\mathtt { V }$ with respect to time domain:

$$
\begin{array} { l } { \dot { V } = s \dot { s } } \\ { = s ( \dot { \mathrm { e } } + \mathrm { c e } ) } \\ { = s ( \dot { \omega _ { r } } ^ { * } - \frac { 1 . 5 n _ { p } \psi _ { f } } { J } i _ { q } ^ { * } - d ( t ) + c e ) } \\ { = s \{ \dot { \omega _ { r } } ^ { * } - \frac { 1 . 5 n _ { p } \psi _ { f } } { J } [ \frac { c J } { 1 . 5 n _ { p } \psi _ { f } } e + \frac { J } { 1 . 5 n _ { p } \psi _ { f } } \dot { \omega _ { r } } ^ { * } + \frac { J } { 1 . 5 n _ { p } \psi _ { f } } \eta \cdot s a t ( s ) ] - d ( t ) + c e \} } \\ { = s [ - \eta \cdot s a t ( s ) - d ( t ) ] } \\ { = - \eta \cdot s \ a t ( s ) - s d ( t ) } \\ { \quad \le - \eta \mid s \mid + \mid d ( t ) \mid s \mid \le 0 . } \end{array}
$$

Lyapunov function is less than or equal to O and when $\dot { V } \equiv 0 , s \equiv 0$ Therefore,the control system is stable and the system states will converge towards the sliding mode surface in the limited time.

# 3.4. Design of fuzzy sliding mode controller

Sliding mode control causes chattering phenomenon in the switching control law, and the chattering phenomenon can excite high frequency dynamics.In order to reduce the chattering and improve the control performance,the fuzzy module is introduced in switching control law.That is to say，when the disturbance is larger the switching control law is larger；when the disturbance is smaller the switching control law is smaller. The control law is designed as:

$$
\boldsymbol { u } = \boldsymbol { u } _ { e q } + \boldsymbol { a } \cdot \boldsymbol { u } _ { s w }
$$

where $a$ is the output of fuzzy module. The input of fuzzy module is sliding surface function s.The membership functions of $s$ and $a$ are shown in Figure 2.

![](images/50e50aeb4c76196e395fd7df0dd6272e33b4b6bcc13e886e800979ab8ca1747b.jpg)  
Fig.2.Membership functions of $s$ and $a$ #

If the system states are near the sliding surface,a will become smaller. If the system states are far away from the sliding surface,a will become larger. This strategy will reduce chattering and ensure that the system states will reach the sliding surface.The fuzzyrules are described as:

If $s$ is $\mathbf { N }$ then $a$ is $\mathrm { \bf P }$ If $s$ is $Z$ then $a$ is $Z$ If $s$ is $\mathrm { \bf P }$ then $a$ is $\mathrm { \bf P }$

# 4.Simulation Results

In this section,the simulation is implemented in MATLAB/Simulink to validate the feasibility and effectiveness of the proposed method. The parameters of the PSMS system are as follows:the stator resistance $R _ { s } = 2 . 8 7 5 \Omega$ ；the rotor flux linkage $\psi _ { f } = 0 . 1 7 5 W b$ ；the $\mathrm { ~ d ~ }$ -axisand $\mathsf { q }$ -axis stator inductances $L _ { d } = L _ { q } =$ $8 . 5 m H$ ； the number of pole-pairs $n _ { p } = 4$ ；the system moment of inertia $J = 7 . 7 \times 1 0 ^ { - 3 } k g \cdot m ^ { 2 }$ ； the viscous friction coeficient $B = 0 N \cdot m \cdot s$ ；the load torque $T _ { L } = 0 . 3 N \cdot m$ ；the rated DC voltage $U _ { d } = 2 7 V$ ; the saturation limit of $i _ { q } ^ { * }$ is $\pm 1 . 5 A$ .With these parameters,the disturbance of system $d ( t )$ is estimated as $3 0 s i n ( t )$ . The reference mechanical angular velocity $\omega _ { r } ^ { * }$ is set to $s i n ( 2 \pi t )$ . In CHBPWM, the time constant of current filter $t _ { o i }$ is $5 \times 1 0 ^ { - 5 }$ and the width of current hysteresis band $\beta$ is 0.05.

The comparative simulation results of the PI speed controller and fuzzy sliding mode speed controller are shown in Figure 3.For PI speed controller, the proportional gain $\mathrm { K } _ { \mathrm { p } } = 0 . 5$ and the integral gain $\mathrm { K } _ { \mathrm { i } } = 2 . 0$ . For fuzzy sliding mode speed controller, ${ \mathrm { c } } = 3 0$ ， $\mathfrak { n } = 3 0 . 2$ and the thickness of the boundary layer $\Delta = 0 . 0 0 6$ . It indicates that the dynamic performance is improved based on the fuzzy sliding mode speed controller.

![](images/386e2cc82d2cb7a90290cbaa39dbe9a299ac4cd6e28530c6083111129eadd4ab.jpg)  
Fig.3. Speed tracking curves with PIcontroller and FSMC.

In order to reduce the chattering,the signum function is replaced by the saturation function and fuzzy module is introduced in sliding mode controller. The control outputs of SMC, SMC with saturation function and FSMC with saturation function are shown in Figure 4.It shows that the control output has the smallest chattering with the proposed method.

![](images/fad3fe6d30d0f3ee291de50588b04e935aae2835843e0412802a685a571410f6.jpg)  
Fig.4.The control output with different methods.(a) SMC.(b) SMC with saturation function.(c) FSMCwith saturation function.

# 5．Conclusion

This paper has proposed a SMC with integral sliding surface to enhance the robustness of the PMSM speed regulation system. In order to suppress the chattering,the signum function is replaced by the saturation function and fuzzy module is introduced in sliding mode controller. Comparative simulation results have validated the proposed method.

# References

1．Li L B,Sun L L, Zhang S Z, et al. Speed tracking and synchronization of multiple motors using ring coupling control and adaptive sliding mode control[J]. ISA transactions, 2015,58: 635-649.   
2.Saghafinia A,Ping H W,Uddin M N,et al. Adaptive fuzzy sliding-mode control into chattering-free IM drive[J]. Industry Applications,IEEE Transactions on, 2015,51(1): 692-701.   
3．Pajchrowski T,Zawirski K.Application of artificial neural network for adaptive speed control of PMSM drive with variable parameters[J]. COMPEL-The international journal for computation and mathematics in electrical and electronic engineering,2013,32(4):1287-1299.   
4. Wang L,Tian M, Gao Y.Fuzzy self-adapting PID control of PMSM servo system[C]//Electric Machines & Drives Conference，2OO7.IEMDC'07. IEEE International.IEEE,20O7,1:860-863.   
5.Zhang J,Kang L.A sensorless vector control system of permanent magnet synchronousmotorbasedonlineactivedisturbancerejection controller[C]//Electrical Machines and Systems (ICEMS)，2014 17th International Conference on.IEEE,2014:1140-1144.   
6.Yang J,Li S,Su J,et al. Continuous nonsingular terminal sliding mode control for systems with mismatched disturbances[J]. Automatica,2013, 49(7): 2287-2291.   
7．Wang A, Jia X,Dong S.A new exponential reaching law of sliding mode control to improve performance of permanent magnet synchronous motor[J]. Magnetics,IEEE Transactions on,2013,49(5):2409-2412.   
8．Lee I, Lee Y, Shin D,et al. A sliding mode based model predictive control structureforpermanentmagnetsynchronousmotor[C]//Control, Automation and Systems (ICCAS),2O15 15th International Conference on. IEEE,2015: 550-555.   
9.Du Z, Chen Z,Liu X,et al. Adaptive switch gain time-varying sliding mode controller design for the low speed servo system in a control moment gyroscope[C]//Mechatronicsand Automation(ICMA)， 2015IEEE International Conference on.IEEE,2015:935-940.