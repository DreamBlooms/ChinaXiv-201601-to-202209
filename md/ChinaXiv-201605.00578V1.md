# One-Dimensional Steady Transport by Molecular Dynamics Simulation: Non-Boltzmann Position Distribution and Non-Arrhenius Dynamical Beh

SHI Rui(石锐）and WANG Yan-Ting(王延頲)+   
State Key Laboratory of Theoretical Physics,Institute of Theoretical Physics,Chinese Academy of Sciences,   
Beijing 100190,China   
(Received May 12, 2014; revised manuscript received June 3, 2014)

AbstractA non-equilibrium steady state can be characterized bya nonzero but stationary fux driven by a static externalforce.Underaweak external force,thedriftvelocityisdiffculttodetect becausethedrift motionis feeble and submerged intheintense thermal diffusion.In thisarticle,weemployanaccurate method inmoleculardynamics simulation todeterminethedrift velocityofaparticledrivenbya weak external force inaone-dimensional periodic potential.With thecalculated drift velocity,we foundthat the mobilityanddifusionoftheparticleobey the Einstein relation,whereas their temperature dependences deviate from the Arhenius law.A microscopic hopping mechanism wasproposedtoexplainthenon-Arrhenius behavior.Moreover,thepositiondistributionoftheparticleinthepotential well was found todeviate fromthe Boltzmann equation inanon-equilibrium steadystate.Thenon-Boltzmann behavior maybe attributed tothe thermostat which introducesan efective“viscous”drag oppositeto thedriftdirectionof the particle.

PACS numbers: 05.70.Ln, 82.20.Wt Key words: non-equilibrium steady state,mobility, self-diffusion, hopping mechanism

# 1 Introduction

Non-equilibrium phenomena are ubiquitous in the universe. In particular, many machines, including biomolecules in living cells,often function in a nonequilibrium steady state (NESS). $[ 1 - 4 ]$ When a system is driven by a static “force” (such as electric feld,shear, chemical-potential gradient,etc.） and dissipates at the same time to reach a stationary state,it works in an NESS,[2,4] which is quite common and pivotal in many applications,such as propellants,batteries,sensors,electrospray,and electrophoresis systems.Therefore,the properties and processes of systems working in an NESS are of significant fundamental and practical interests. One unique feature of an NESS is the nonzero but stationary flux driven by an external force,which characterizes the active transport process in the system. The response of a system to a strong external force is noticeable and the unidirectional drift velocity is easy to detect in both experiments $[ 5 - 8 ]$ and simulations. $[ 9 - 1 8 ]$ However, in most applications, the system usually works in a moderate condition，i.e.,driven by a weak force,in which the drift motion is submerged in the intense thermal diffusion and thus difficult to detect. $[ 1 1 , 1 9 - 2 1 ]$ This difficulty in determining the drift velocity severely retards further exploration of the transport properties of the system working in an NESS.Besides,compared with the well-established equilibrium statistical mechanics theory, our understanding of non-equilibrium states is still very primitive. Therefore,until now a better understanding on the properties of systems in an NESS is very challenging from both the oretical and practical points of view.

Transport process is essential in the study of an NESS Usually, particles in solids and liquids vibrate around their local equilibrium positions，and occasionally hop from one equilibrium position to another.[22] Therefore, transport properties such as mobility，conductivity,and selfdiffusion can be simplified as a sequence of particle hops between effective potential wells. $[ 2 3 - 2 6 ]$ The motion of a particle in a one-dimensional (1-D) periodic potential well is a simple but important model in studying various transport behaviors in an NESS.In particular,a large number of phenomena in physics and chemistry, such as surface diffusion，superionic conductors,rotation of molecules in solids,and charge carrier transport,can be understood based on this simple model.[27] Compared with the intensive studies on the transport under a strong external force, $\lfloor 2 8 - 3 5 \rfloor$ the properties and the underlying microscopic dynamics of the transport behavior in the weak force regime are still not fully understood,heavily attributed to the difficulty of determining the drift velocity in this regime.

In the present paper，we employ a numeric method to accurately calculate the drift velocity of a particle driven by a weak external force in a 1-D periodic potential by non-equilibrium molecular dynamics (MD) simulation. Mobility and self-diffusion coefficient of the system can thenbe determined according to the obtained drift velocity.We found that mobility is independent of external force but increases with temperature.Moreover,it deviates from the Arrhenius law and follows a modified Arrhenius equation with its activation energy much smaller than the real energy barrier. Similarly, self-diffusion coefficient also deviates from the Arrhenius behavior and along with mobility obeys the Einstein relation.A microscopic hopping mechanism was proposed to explain the non-Arrhenius behavior. Moreover,the position distribution of the particle in the potential well was found to deviate from the Boltzmann equation in an NESS.The non-Boltzmann behavior may be attributed to the thermostat introducing an effective “viscous” drag opposite to the drift direction of the particle,which also explains the fact that the activation energies for mobility and diffusion are much smaller than the real energy barrier of the potential well.

# 2Computational Procedures

# 2.1DriftVelocity，Mobility，andSelf-Diffusion

Drift velocity is an essential quantity for characterizing transport properties.However,since the weak drift motion is typically submerged in the intense thermal diffusion，drift velocity that driven by a weak external force can hardly be detected in both experiment[36l and simulation.[1120] For example, in a commonly used ionic liquid 1-ethyl-3-methylimidazolium tetrafluoroborate, the ion drift velocity is around $1 0 ^ { - 7 } ~ \mathrm { m / s }$ under a weak electric field of $1 0 0 ~ \mathrm { V / m }$ ，whereas the thermal velocity of ion can be as high as $1 9 0 \mathrm { m / s }$ at 298 K.[21] This is the reason why most non-equilibrium simulations were carried out at a strong external force. There are three major methods for calculating the drift velocity in an NESS: average velocity, mean-square displacement (MSD),and transient time-correlation function (TTCF).When the drift velocityis comparable to orlarger than thermal velocity under a strong force,it can be directly obtained from the average velocity of all particles.[11,37] Another way to calculate the drift velocity is comparing MSD with and without the external force.By using this approach,Murad $[ 1 2 ]$ calculated the drift velocity of an NaCl solution under a strong electric field.This approach is only valid when the MSD is independent of an external force,but in many systems the force-dependent MSDs have been observed.[2i,38-39] Delhommelle,et al.[19] employed the TTCF method to calculate the current density and conductivity of a molten salt under an external electric field. They found that the TTCF method can be used to analyze the response of a system to an arbitrary external force. However,in the TTCF approach an enormous number of non-equilibrium trajectories are required to perform data analysis,which limits the application of the TTCF method.

In our previous work,a method has been successfully applied to calculate the drift velocities of ionic liquids and aqueous solutions under external electric fields.[21,38] Compared with the above approaches, this method only needs several trajectories and is able to obtain the drift velocity accurately at a moderate external force.Here we briefly describe this method as follows. The displacement of a particle under an external driving force in a time interval $\Delta t$ at a time $t _ { i }$ can be decomposed into a unidirectional drift term and a random diffusive term:

$$
\Delta x ( t _ { i } ) = \Delta x _ { \mathrm { d r i f t } } ( t _ { i } ) + \Delta x _ { \mathrm { d i f f u s i o n } } ( t _ { i } ) ,
$$

where $\Delta x _ { \mathrm { d r i f t } } ( t _ { i } )$ and $\Delta x _ { \mathrm { d i f f u s i o n } } \left( t _ { i } \right)$ are the displacements caused by drift motion and thermal diffusion, respectively. The two types of motions have totally different behaviors: the drift motion shows a steady and unidirectional movement,whereas the thermal diffusion performs random walks and has a spectrum of white noise. For an infinite number of spontaneous displacements,we have

$$
\operatorname* { l i m } _ { N  \infty } \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \Delta x _ { \mathrm { d i f f u s i o n } } ( t _ { i } ) = 0 ,
$$

where $N$ is the number of time intervals.Therefore,the drift velocity can be approximately obtained from a finite length trajectory by the following expression

$$
v _ { \mathrm { t r a j } } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \frac { \Delta x _ { \mathrm { d r i f t } } ( t _ { i } ) } { \Delta t } = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } \frac { \Delta x ( t _ { i } ) } { \Delta t } .
$$

In an NESS the drift velocity remains constant, so we calculate a series of $\Delta x$ with respect to various time intervals $\Delta t$ and obtain $v _ { \mathrm { t r a j } }$ by linear fitting $\Delta x$ against $\Delta t$ . If we replace the long time average by the ensemble average over many independent short trajectories,we estimate the drift velocity by the equation,

$$
\begin{array} { r } { v _ { \mathrm { d r i f t } } \approx \left. v _ { \mathrm { t r a j } } \right. , } \end{array}
$$

where $\langle \cdots \rangle$ denotes the ensemble average over all trajec tories.

The mobility $u$ , characterizing the ability of ion movement in response to an external driving force $f$ ，can be calculated from the drift velocity by

$$
u = v _ { \mathrm { d r i f t } } / f .
$$

In equilibrium,the self-diffusion coefficient $D$ in one dimension can be determined by using the Einstein expression

$$
\langle \Delta x ^ { 2 } ( t ) \rangle = 2 D t ,
$$

where $\langle \Delta x ^ { 2 } ( t ) \rangle$ is the MSD. This Einstein expression suggests that the MSD increases linearly with time for a diffusive motion.However,in an NESS the drift motion deviates the MSD from a normal diffusive behavior.Therefore,the relative MSD that deducting the drift contribution from the overall MSD is defined to calculate the self-diffusion coefficient in an NESS as

$$
\begin{array} { r } { \Sigma ( t ) - \langle \Delta x ( t ) \rangle ) ^ { 2 } \rangle = \langle \Delta x ^ { 2 } ( t ) \rangle - \langle \Delta x ( t ) \rangle ^ { 2 } = 2 D t . } \end{array}
$$

According to this equation，we can determine the self diffusion coefficient in an NESS by linearly fitting the relative MSD against time.

# 2.2 Model

The method described above can be easily applied to determining the drift velocity for various systems in MD simulation.In this work,a 1-D particle moving in a periodic potential was simulated to understand the behavior of a system driven out of equilibrium by a weak external force.In our MD simulations, the particle moves in a bistable-potential model proposed by $\mathrm { S u n } ^ { [ 4 0 ] }$ as

$$
V ( x ) = x ^ { 4 } - 1 6 x ^ { 2 } ,
$$

where $x$ is the particle position and the periodicity is satisfied by applying the condition $V ( x + L ) ~ = ~ V ( x )$ with the periodic length $L$ set to be 14. This model was used to study the biased sampling of non-equilibrium trajectories.[41] In absence of the external force, the po tential well is bistable with its minima separated by a low energy barrier $V _ { 0 } ~ = ~ 6 4$ within the well and by a high energy barrier $V _ { 1 } = 1 6 8 1$ between neighboring wells. Focusing on the weak force regime,the driving force $f$ studied in this paper was chosen to be in the range from $0$ to 50 along the $^ { x + }$ direction and hence the potential well is effectively weakly tilted,as shown in Fig.1. The temperature-dependent behavior was investigated at different temperatures ( $T = 5 0 0$ ，750,1000,1250,and 1500), respectively,with the kinetic energy of the particle defined as

$$
E _ { k } = { \frac { 1 } { 2 } } k _ { B } T ,
$$

where the Boltzmann constant $k _ { B }$ is scaled to be 1.

![](images/0f5aa061d431e0ac09e61b849f816e47d0f9d640e5984714b6c527251bb0f329.jpg)  
Fig.1 Tilted bistable effective potentials with different external forces in one period.

# 2.3 Molecular Dynamics

In the present paper, the velocity Verlet algorithm.[42] with a time step $\Delta t = 0 . 0 0 1$ was employed to integrate the Newton equation:

$$
m { \frac { \mathrm { d } ^ { 2 } x } { \mathrm { d } t ^ { 2 } } } = - { \frac { \mathrm { d } V ( x ) } { \mathrm { d } x } } + f .
$$

In order to detect the weak drift motion submerged in the thermal diffusion,an ensemble of 2O trajectories was sampled from 2O independent constant $N V T$ MD simulations.Each simulation was carried out for $2 \times 1 0 ^ { 9 }$ MD steps with the particle position sampled every looO steps. The quantities studied in the present paper were averaged overall the 2O independent trajectories.The temperature was kept constant by using the Andersen thermostat.[43]

In the strong coupling limit,the particle frequently undergoes stochastic collisions and its new velocity is drawn from a Maxwell-Boltzmann distribution in every step.

# 3 Results and Discussions

# 3.1 Mobility

Drift velocity is an important quantity for character izing the transport process.However,as described above, it is very diffcult to obtain the drift velocity under a weak driving force because the particle motion is usually dominated by the intense thermal diffusion. On the microscopic scale,if one tracks the movement of a particle un der a weak external force in a short period of time,only isotropic random walks can be observed and the drift motion is not detectable.Only when the observation time is sufficiently long can the hidden drift motion accumulate to be macroscopically measurable.Some typical trajectories at $T = 1 0 0 0$ under different external driving forces are shown in the inset of Fig.2.It can be seen that the system exhibits a random motion caused by thermal diffusion and no noticeable unidirectional drift. However, no matter how weak the drift motion is,the microscopic structure and dynamics should have some signatures that are responsible to the macroscopic transport behavior.

![](images/f161b8c2bd0f676a4b23bee4e1836bc3566f92369db432dac5f15acedb71b9f2.jpg)  
Fig.2Average displacements as a function of time at （204号 $T = 1 0 0 0$ under different external forces.Inset:Typical trajectories at $T ^ { \prime } = 1 0 0 0$ under different external forces.

In order to reveal the drift behavior submerged in the intense thermal diffusion,we applied the method described in Subsec.2.1 to calculate the drift velocity in our simulations.Figure 2 shows the average displacements at different external forces.Compared with the real trajec tories that show random walks, the average displacements increase linearly with time,showing a typical drift behavior.

![](images/0d4925d19be4764646ce7c0707ada04797e09cf6def97fd2c462eaa195fc2910.jpg)  
Fig.3(a)Drift velocities and(b) mobilities at different temperatures and external forces.The solid lines in (a) depict the linear fits to the data.

Figure 3(a) shows the drift velocities versus the external force at different temperatures and the solid lines are the linear fits to the drift velocities.By using the method described above,we managed to calculate the drift velocities even at very small external forces ( $f L / V _ { 1 } = 0 . 0 1 7$ ). It can be seen that the drift velocity increases linearly with the external force,suggesting that the system remains in a linear-response regime.The drift velocity also increases with temperature at a given external force,but this trend becomes weaker as the temperature increases.The mobility was then calculated from the drift velocity according to Eq. (5). Figure $\mathrm { 3 ( b ) }$ shows the mobility against $1 / T$ inasemi-logarithmic plot.As expected,mobility is inde pendent of the external force in the linear-response regime and apparently increases with temperature.However, the mobility deviates from the Arrhenius law,

$$
u = u _ { 0 } ^ { \prime } \exp ( - E _ { u } ^ { \prime } / k _ { B } T ) ,
$$

where $u$ is the mobility， $u _ { 0 } ^ { \prime }$ is the prefactor, $E _ { u } ^ { \prime }$ is the activation energy for mobility, $k _ { B }$ is the Boltzmann constant,and $T$ is the temperature. The deviation from the Arrhenius law has been observed in many systems. The transport properties,such as mobility, conductivity,and diffusion coefficient，that deviate from the Arrhenius law can usually be described by the Vogel-Fulcher-Tamman （VFT） equation, $[ 4 4 - 4 6 ]$ （204号 $X ~ = ~ X _ { 0 } T ^ { \gamma } \exp ( - B / ( T - T _ { 0 } ) )$ or a modified Arrhenius equation, $\lfloor 4 7 - 5 0 \rfloor$ （2 $X = X _ { 0 } T ^ { \gamma } \exp ( - E / k _ { B } T )$ ，where $X$ represents transport properties.In our system,we found that the mobility can be best fitted by the following equation,

$$
u = u _ { 0 } T ^ { - 2 / 3 } \exp \Big ( - \frac { E _ { u } } { k _ { B } T } \Big ) .
$$

The fitting results are listed in Table $^ { 1 }$ .The mean activation energy for mobility is 1O52,much lower than the real energy barrier height of 1681.In the following sections,we will show that the low activation energy and the non-Arrhenius behavior of mobility can be understood by a microscopic hopping mechanism.

Table 1 The fitting parameters of mobility by Eq. (12).   

<html><body><table><tr><td>f</td><td>Eu</td><td>uo</td><td>R2a</td></tr><tr><td>0</td><td></td><td>1</td><td>-</td></tr><tr><td>10</td><td>1077</td><td>0.12</td><td>0.9995</td></tr><tr><td>20</td><td>1052</td><td>0.12</td><td>0.9996</td></tr><tr><td>30</td><td>1049</td><td>0.12</td><td>0.9998</td></tr><tr><td>40</td><td>1039</td><td>0.12</td><td>0.9990</td></tr><tr><td>50</td><td>1041</td><td>0.12</td><td>0.9990</td></tr></table></body></html>

a $R ^ { 2 }$ is the coefficient of determination of the fit.

# 3.2Self-Diffusion

In the linear-response regime,if the particles in a many-body systemareuncorrelated,the mobility and selfdiffusion coefficient satisfy the Einstein relation

$$
\begin{array} { r } { D = u k _ { B } T . } \end{array}
$$

The self-diffusion coefficient was calculated according to Eq.(7). Figure 4 shows the relation between mobility and self-diffusion coefficient at different temperatures and external forces.It can be seen that the mobilities and self-diffusion coefficients indeed obey the Einstein relation very well within the statistical errors.

According to Eqs.(12) and (13),the self-diffusion coefficient also deviates from the Arrhenius law and can be well fitted by a modified version of the Arrhenius equation,

$$
D = D _ { 0 } T ^ { 1 / 3 } \exp \Big ( - \frac { E _ { D } } { k _ { B } T } \Big ) ,
$$

where $D _ { 0 }$ is the prefactor and $E _ { D }$ is the activation energy for self-diffusion.Figure 5 shows the self-diffusion coefficients against $1 / T$ on a semi-logarithmic scale.It can be seen that the diffusion coefficient indeed can be described by Eq.(14) very well. The fitting parameters are given in Table 2. The mean activation energy was found to be 1048,very close to the activation energy for mobility and also much lower than the real energy barrier height of 1681.

Table 2Fitting parameters of self-diffusion coefficient by Eq. (14).   

<html><body><table><tr><td>F</td><td>ED</td><td>Do</td><td>R²</td></tr><tr><td>0</td><td>1021</td><td>0.12</td><td>0.9999</td></tr><tr><td>10</td><td>1064</td><td>0.13</td><td>0.9992</td></tr><tr><td>20</td><td>1068</td><td>0.13</td><td>0.9999</td></tr><tr><td>30</td><td>1036</td><td>0.12</td><td>0.9991</td></tr><tr><td>40</td><td>1013</td><td>0.12</td><td>0.9998</td></tr><tr><td>50</td><td>1036</td><td>0.12</td><td>0.9995</td></tr></table></body></html>

![](images/fae3b603daf7da23cc45f5e5247533c00478344a3610cdd10b4549c83170704f.jpg)  
Fig.4 Einstein relation connecting the mobility and self-diffusion coefficient.For each temperature,different data points represent the data at different external forces.

![](images/69e0e2678cf64c5af54c71cc2d30fb083fe4a954ce6c13e48fc36323c3012773.jpg)  
Fig.5Self-diffusion coefficients at different temperatures and external forces.

Up to now,we have successfully determined the mobility and self-diffusion coefficient of the system driven out of equilibrium by a weak external force.We found that both mobility and self-diffusion show non-Arrhenius behavior，but still obey the Einstein relation. To further understand the non-Arrhenius behavior,thedistribution of particle positions (DPP) and hopping process are studied in detail in the following sections.

# 3.3Distribution of Particle Positions in the Potential Well

In equilibrium states,at a given temperature the DPP in a potential well obeys the Boltzmann distribution

$$
P = { \frac { 1 } { Z } } \exp \left( - { \frac { E } { k _ { B } T } } \right) ,
$$

where $k _ { B }$ is the Boltzmann constant, $T$ is the temperature, $E$ is the potential energy,and $Z$ is the normalization constant.When an external force is applied, the particle moves along the force direction with a drift velocity and the system reaches an NESS.Unfortunately， no general theories for the DPP in an NESS are currently available. Inthe present model,we calculated the DPPs at different external forces and temperatures.Figures 6(a) and 6(b) show the equilibrium DPPs at different temperatures and the non-equilibrium DPPs under various external forces at $T = 5 0 0$ ，respectively. The DPPs at other temperatures and external forces are not shown since they have no qualitative differences from those plotted in Fig.6.

![](images/c06d6ff2747bfc8ab9735b36f51335fd0c6bc387ea104a124ea6498ac2909fa4.jpg)  
Fig.6 Distributions of particle positions in the potential well at (a) different temperatures at $f = 0$ and (b) different external forces at $T ' = 5 0 0$ ：

As shown in Fig.6(b)，the external force obviously tilts the distributions in an NESS.We fitted the DPPs phenomenologically and found that the DPPs can be well described by a Boltzmann-type distribution function,

$$
P ( x ) = \frac { 1 } { Z } \exp \bigg [ \frac { - ( V ( x ) - f ^ { * } x ) } { k _ { B } T ^ { * } } \bigg ] ,
$$

where $P ( x )$ is the DPP probability, $V ( x )$ is the potential energy, $Z$ is the normalization constant, $f ^ { * }$ and $T ^ { * }$ （204号 are phenomenological parameters. The fitting results at $T = 5 0 0$ are listed in Table 3.(The DPPs at other tem peratures and forces can also be well fitted by Eq. (16) and the fitting results are not shown.)

Table 3The ftting parameters of particle position distributions by Eq.(16) at $T = 5 0 0$   

<html><body><table><tr><td>f</td><td>f*</td><td>fT</td><td>T*</td><td>Z</td><td>R²</td></tr><tr><td>0</td><td>-0.48</td><td>0.48</td><td>501.6</td><td>11.34</td><td>0.9996</td></tr><tr><td>10</td><td>5.97</td><td>4.03</td><td>500.9</td><td>11.34</td><td>0.9996</td></tr><tr><td>20</td><td>12.02</td><td>7.98</td><td>502.9</td><td>11.37</td><td>0.9995</td></tr><tr><td>30</td><td>18.61</td><td>11.39</td><td>503.3</td><td>11.42</td><td>0.9995</td></tr><tr><td>40</td><td>24.50</td><td>15.50</td><td>504.9</td><td>11.49</td><td>0.9994</td></tr><tr><td>50</td><td>31.06</td><td>18.94</td><td>506.2</td><td>11.57</td><td>0.9992</td></tr></table></body></html>

It can be seen that the phenomenological temperature $T ^ { * }$ is approximately equal to the real temperature $T$ .However，the phenomenological driving force $f ^ { * }$ is much smaller than the applied external force,indicating a deviation from the equilibrium behavior.The difference $f _ { T } = f - f ^ { * }$ is also listed in Table 3. We found that $f _ { T }$ increases roughly linearly with the external force and surprisingly, strongly correlated with the drift velocity. Figure 7 shows the relation between $f _ { T }$ and drift velocity. It can be clearly seen that $f _ { T }$ also increases linearly with the drift velocity and the slope changes slightly with temperature.All these features suggest that $f _ { T }$ actually acts as an effective “viscous” force opposite to the drift direction.

![](images/0fc6735174f88be36e70a20f1227a6da2a30ffa3532a4484514f214a261e846d.jpg)  
Fig.7Relation between the effective “viscous” force and drift velocity. For each temperature,different data points represent the data at different external forces.

To quantify the “viscous”force,we introduced an effective“viscosity” $\xi$ and fitted $f _ { T }$ as a function of drift velocity by the following equation,

$$
f _ { T } = \xi v _ { \mathrm { d r i f t } } .
$$

The fitting results are given in Table 4.Clearly, the effective“viscosity”increases slightly with temperature,inferring that,in our model the Andersen thermostat exerts an effective “viscous” force on the system to balance the external driving force and thus stabilize the system. From a microscopic point of view,the Andersen thermostat dissipates the system energy through stochastic collisions of particles with the reservoir.In an equilibrium state,the collision is isotropic -the probability of a par ticle undergoing a collision from right and left sides are the same. However,when we apply the Andersen thermostat to an NESS, the isotropic collision tends to eliminate the anisotropic drift motion,since the symmetric Maxwell-Boltzmann distribution is assumed in the Andersen thermostat,which brings in an effective“viscous" drag opposite to the drift direction.Here we should distinguish the effective “viscous” force $f _ { T }$ from the physical viscous force. The former effectively responds to the drift velocity in an NESS,whereas the latter is in response to the spontaneous velocity in a real viscous system.

Table 4Fitting parameters of effective“viscous” force by Eq. (17).   

<html><body><table><tr><td>T</td><td>500</td><td>750</td><td>1000</td><td>1250</td><td>1500</td></tr><tr><td>m</td><td>1618.6</td><td>1708.6</td><td>1770.6</td><td>1817.4</td><td>1846.6</td></tr><tr><td>R²</td><td>0.9997</td><td>0.9999</td><td>0.9999</td><td>0.9999</td><td>0.9999</td></tr></table></body></html>

Based on the results above,we propose that the thermostat in an NESS seems to play an essential role in determining the non-equilibrium DPP.By introducing an effective“viscous” force in response to the unidirectional drift motion, the DPP in an NESS can be well described by the modified Boltzmann distribution function.

# 3.4 Hopping Dynamics

An NESS is always related to the transport process with a constant mass，charge,or energy flux. At the atomistic scale,the transport mechanism can be described bya sequence of incoherent hops of particles,which have been observed in many systems, such as liquid crystal,[51] ionic liquid,[52] glass forming liquid,[53] membrane,[54] and polymer.[55] Therefore,it is of great importance to understand the hopping mechanism behind the drift behavior.Here we analyze the hopping dynamics in our system by using the intermittent time correlation functions (TCFs):[56-57]

$$
C ( t ) = \frac { \langle p ( 0 ) p ( t ) \rangle } { \langle p \rangle } ,
$$

where the population variable $p ( t )$ is unity when the particle stays in a particular potential well at time $t$ and zero otherwise. The bracket $\langle \cdots \rangle$ indicates an average over all starting time. By definition, $C ( t )$ describes the structural relaxation of a particle stays in the same potential well at time $t$ as at time O after a sequence of hops.Because a particle moving away with a faster drift speed has a lower probability to travel back to its original position,the hopping dynamics $C ( t )$ can be used to study the mobility of the particle. Figure 8(a) shows $C ( t )$ in equilibrium at different temperatures.It can be seen that $C ( t )$ decays much faster at a higher temperature,but this trend becomes weaker as the temperature increases,consistent with the behavior of drift velocity (see Fig. 3(a)).

![](images/56782f63073e136c774d425fa2ebd2e37ae26d001250d5fc1462ebc94bc372b2.jpg)  
Fig.8 Intermittent time correlation function of hoppingdynamics $C ( t )$ at (a) $f = 0$ and (b) $T ' = 5 0 0$ ：

Figure 8(b) displays the non-equilibrium $C ( t )$ at $T =$ 500 under various external forces ( $C ( t )$ at other temperatures and external forces show no qualitative differences and are therefore not shown).Because a faster drift mo tion can effectively decrease the probability of the particle moving back to its original well, $C ( t )$ decays faster under a stronger external driving force. Moreover,comparing the equilibrium $C ( t )$ with non-equilibrium $C ( t )$ ，one can find that the temperature and external force influence the hopping dynamics at two different time scales.As shown in Figs. 8(a) and 8(b), $C ( t )$ begins to change with temperature at a very short time scale,whereas the external force manages to affect the hopping dynamics at a longer time scale.This can be understood by the fact that tem perature changes particle hopping rate immediately and hence influences $C ( t )$ at a short time scale.In contrast, since the external force is relatively weak, it can only break the symmetry of hops: the particle has a slightly higher probability to hop out of the well toward the force direction and a slightly lower probability to hop backward.At a short time scale,the asymmetry of hops is negligible and as a result,the particle exhibits a random diffusive behavior. At a long time scale,the asymmetric hops accumulate to be detectable,leading to the decrease of $C ( t )$ and resulting in a unidirectional drift motion.

# 3.5 Hopping Rate

In the previous section, the force and temperature dependences of hopping dynamics were discussed by using the intermittent TCF.However,the TCF is insensitive to the hopping direction which is essential to the unidirectional drift motion. Therefore,the directional hopping rate defined as the number of hops toward each direction per unit time was calculated to further investigate the microscopic dynamics of the system.In an equilibrium state, the particle performs random but symmetric hops in the potential well. When an external force is applied,the symmetry is broken and the hopping rates toward different directions become asymmetric,resulting in a net drift current.In our model,after being trapped for a period of time, the particle may escape from a potential well forward with a hopping rate $k _ { + }$ or backward with a rate $k _ { - }$ 5 and $k = k _ { + } + k _ { - }$ is the total hopping rate escaping out of the well. By definition, the drift velocity is connected with the hopping rate difference by the following equation,

$$
\begin{array} { r } { v _ { \mathrm { d r i f t } } = ( k _ { + } - k _ { - } ) L ^ { * } , } \end{array}
$$

where $L ^ { * }$ is the mean hopping length.

![](images/7e0130f5c94a0a09e08d900ffc131c1dd8ef05f80a0ed002879f8df490b4571c.jpg)  
Fig.9 Relation between the drift velocity and the hoppingrate difference.For each temperature,different data points represent the data at different external forces.

Figure 9 plots the relation between the drift velocity and the hopping rate difference.It can be seen that,at different forces and temperatures, the drift velocities and the hopping rate differences follow Eq.(19) very well. The mean hopping length $L ^ { * }$ was determined to be $1 4 . 1 \pm 0 . 8$ . which equals the well length within the statistical error. Therefore,according to Eq. (19),the transport property of the system can be further understood by the microscopic hopping process.

![](images/ee40e627904af8078bd845f6ccc7bc2a325db2881b139db3dace914bfd7c98fd.jpg)  
Fig.1O(a)Hopping rate without the external force and (b）reduced hopping rate differences at various external forces as a function of temperature.The solid lines in (a) and(b)depict the best fits to the data by Eqs.(2O)and (24),respectively.

The hopping rate without the external force is shown in Fig.1O(a).In equilibrium the hops are symmetric with $k _ { + 0 } ~ = ~ k _ { - 0 } ~ = ~ k _ { 0 }$ ，and the hopping rate increases significantly with temperature,consistent with the hopping dynamics discussed above. For a simple system, it is usually accepted that the hopping rate obeys the Arrhenius law,[2,25,58-59] whereas a number of systems, such as glass, $[ 4 8 , 6 0 - 6 1 ]$ ionic conductor, $[ 6 2 - 6 5 ]$ polymer electrolyte, $[ 4 4 - 4 5 , 4 9 ]$ ionic liquid,[46,66] and glass-forming liquid, $[ 6 7 - 6 8 ]$ were found to show non-Arrhenius behavior. In our model, we found that the equilibrium hopping rate also deviates from the Arrhenius law and can be well described (with $R ^ { 2 } = 0 . 9 9 9 9 9 9$ ）bya modified version of the Arrhenius equation similar to the one for self-diffusion,

$$
k _ { 0 } = A T ^ { 1 / 3 } \exp \bigg ( - \frac { E _ { k } } { k _ { B } T } \bigg ) ,
$$

where $A$ is the prefactor and $E _ { k }$ is the activation energy for hopping.The activation energy $E _ { k }$ was found to be 1528, very close to the real barrier $V _ { 1 } = 1 6 8 1$ .Here it is noteworthy that the real barrier $V _ { 1 }$ is the maximum height between the peak and valley of the potential well. However, since the particle has a probability to stay in any position of the well in a finite temperature (see Fig.6),the activa tion energy for a particle to hop out of the well should be somehow lower than the maximum barrier height $V _ { 1 }$ .Al though the equilibrium hopping rate deviates from the Arrhenius law,the activation energy obtained from Eq.(20) turns out to be a good estimation of the energy barrier.

Figure 1O(b） shows the reduced hopping rate differences against $1 / T$ on a semi-logarithmic scale. The reduced hopping rate difference is defined as the difference between the forward and backward hopping rates divided by its equilibrium value $k _ { 0 }$ . If we assume that the external force changes the hopping rate by modifying the activation energy, we can calculate the non-equilibrium hopping rate by modifying its equilibrium formula (Eq.(2O)） by,

$$
\begin{array} { l } { \displaystyle { k _ { \pm } = A T ^ { 1 / 3 } \exp \bigg ( - \frac { E _ { k } \mp \alpha f L / 2 } { k _ { B } T } \bigg ) } } \\ { \displaystyle { = k _ { 0 } \exp \bigg ( \pm \frac { \alpha f L } { 2 k _ { B } T } \bigg ) \approx k _ { 0 } \bigg ( 1 \pm \frac { \alpha f L } { 2 k _ { B } T } \bigg ) , } } \end{array}
$$

where $\alpha$ isaparameter that describes the effect of external force on the activation energy. Therefore,the reduced hopping rate difference can be expressed as

$$
\frac { k _ { + } - k _ { - } } { k _ { 0 } } = \frac { \alpha f L } { k _ { B } T } .
$$

By fitting the simulation data,we found that $\alpha$ exponentially depends on temperature,

$$
\alpha = \alpha _ { 0 } \exp \Big ( \frac { E _ { \alpha } } { k _ { B } T } \Big ) .
$$

According to Eqs. (22) and (23), the reduced hopping rate difference can be well fitted by the following equation

$$
\frac { k _ { + } - k _ { - } } { k _ { 0 } } = \frac { \alpha _ { 0 } f L } { k _ { B } T } \exp \Big ( \frac { E _ { \alpha } } { k _ { B } T } \Big ) .
$$

The fitting results are displayed in Fig.1O(b) and given in Table 5. Combining Eqs.(19),(20),and (24),we have

$$
\begin{array} { l } { { \displaystyle v _ { \mathrm { d r i f t } } = ( k _ { + } - k _ { - } ) L ^ { * } = k _ { 0 } \frac { k _ { + } - k _ { - } } { k _ { 0 } } L ^ { * } } } \\ { { \displaystyle \phantom { \frac { k _ { + } - k _ { - } } { k _ { B } } T ^ { * } = k _ { 0 } \frac { k _ { - } } { k _ { B } T } } = \frac { A \alpha _ { 0 } f L ^ { 2 } } { k _ { B } } T ^ { - 2 / 3 } \exp \left( - \frac { E _ { k } - E _ { \alpha } } { k _ { B } T } \right) . } } \end{array}
$$

Therefore, the mobility can be expressed as

$$
u = { \frac { v _ { \mathrm { d r i f t } } } { f } } = { \frac { A \alpha _ { 0 } L ^ { 2 } } { k _ { B } } } T ^ { - 2 / 3 } \exp \left( - { \frac { E _ { k } - E _ { \alpha } } { k _ { B } T } } \right) .
$$

This equation explains why the mobility is independent of the external force,and gives the exact (Non-Arrhenius) temperature dependence as we have already obtained from Eq.(12). Comparing Eq.(12) with Eq. (26),we found that the prefactor $\left( A \alpha _ { 0 } L ^ { 2 } / k _ { B } \right)$ equals $u _ { 0 }$ and the activation energy $\left( E _ { k } - E _ { \alpha } \right)$ is 1041，very close to $E _ { u }$ of 1052.This suggests that，by introducing a temperature dependent parameter $\alpha$ ，the dependence of mobility on temperature and force can be well described by a microscopic hopping mechanism.Moreover,the exponential dependence of $\alpha$ on temperature explains the fact that the activation energy $E _ { u }$ becomes much lower than the real energy barrier, considering that $E _ { k }$ is a good estimation of the real energy barrier.

Table 5The fitting parameters of reduced hopping rate differences by Eq. (24).   

<html><body><table><tr><td>F</td><td>αo</td><td>EQ</td><td>R²</td></tr><tr><td>0</td><td>-</td><td>-</td><td></td></tr><tr><td>10</td><td>0.15</td><td>468</td><td>0.9999</td></tr><tr><td>20</td><td>0.15</td><td>478</td><td>0.9999</td></tr><tr><td>30</td><td>0.15</td><td>493</td><td>0.9999</td></tr><tr><td>40</td><td>0.15</td><td>498</td><td>0.9999</td></tr><tr><td>50</td><td>0.15</td><td>499</td><td>0.9999</td></tr></table></body></html>

![](images/404a4b4ab3dc7713a2573bdd37ed5d162dc38bcfe4fe7eaf1fb9a308b77b45f6.jpg)  
Fig.11 Parameter $\alpha$ calculated by Eqs.(23) and (27) at different temperatures and external forces.

The parameter $\alpha$ was usually chosen to be 1 in theoretical calculations,[22,69] but in our model we found that it is actually smaller than 1 and becomes temperature dependent in an NESS.Figure 11 plots $\alpha$ calculated by Eq. (23) in red lines.It can be seen that $\alpha$ decreases with temperature and takes a value between O.4 and O.2. Moreover, $\alpha$ seems to be force independent.According to Eq.(21),αj can be considered as an effective force that drives the particle hopping.On the other hand,since we have described in Subsect 3.3 that the Andersen thermostat exerts an effective“viscous”force $f _ { T }$ on the particle,the net effective force experienced by the particle can also be expressed as

$$
\alpha f = f - f _ { \scriptscriptstyle T } .
$$

According to Eq. (27)，the parameter $\alpha$ was also calculated from the effective“viscous” force $f _ { T }$ and shown in black lines in Fig.11.It can be seen that the effective driving forces $\alpha f$ obtained from DPP and hopping rate display similar force and temperature dependences. The quantitative difference may be attributed to the assumption in dealing with the effect of force on the hopping rate.For example,in Eq.(21) the external force changes the hopping rate by simply modifying the activation energy with $\pm \alpha f L / 2$ ,but in fact the effect of the external force is expected to be more complex,since it depends on the DPP in the potential well. Moreover,the decrease of $\alpha$ with temperature can be naturally explained on the basis of the “viscous” force:the“viscosity” $\xi$ and drift velocity $v _ { \mathrm { d r i f t } }$ both increase with temperature,and as a result the effective driving force $\alpha f$ decreases with temperature due to the increasing“viscous” force $f _ { T } = \xi v _ { \mathrm { d r i f t } }$ (Eq. (17)). This again supports our previous conclusion that,in an NESS,the Andersen thermostat exerts an effective “viscous” force on the system. As a result，the transport properties of the system can be understood as a sequence of non-Arrhenius hops under an external driving force and an effective “viscous” drag.

# 4 Conclusion

In conclusion,by non-equilibrium MD simulation,the drift velocity of a 1-D particle moving in a periodic potential well under a weak external force has been successfully determined.The mobility and self-diffusion coefficient of the particle were also obtained by using the drift velocity. We found that the mobility is independent of the external force and increases with temperature,and the mobility deviates from the Arrhenius law and follows a modified Arrhenius equation with the activation energy much smaller than the real energy barrier.Similarly, the self-diffusion coefficient also deviates from the Arrhenius behavior.Nevertheless,the mobility and the self-diffusion coefficient still obey the Einsteinrelation.

To further understand the microscopic structure and dynamics in an NESS,the DPP and hopping dynamics in the potential well were calculated. We found that the non-equilibrium DPP can be well describedby a modified Boltzmann distribution function if we introduce an effective“viscous” force which probably originates from the energy dissipation by the Andersen thermostat. Moreover,the microscopic hopping dynamics was analyzed by the intermittent TCF.In contrast to the temperature that changes the hopping rate at a short time scale,a weak external force can only slightly break the symmetry of hop that accumulates to result in a unidirectional drift motion at along time scale.We also propose a microscopic explanation to the non-Arrhenius behavior of mobility by a hopping mechanism. By introducing a temperaturedependent effective driving force,we successfully explain the fact that the activation energy $E _ { u }$ for mobility becomes much lower than the real energy barrier.This again supports our result of the DPP,inferring that the Andersen thermostat exerts an effective “viscous”drag on the particle opposite to the drift direction.

This work advances our understanding of the transport properties and processes in an NESS.Even though all the results in this work are based on a 1-D abstract model, the method of determining the drift velocity from diffusiondominant trajectories and the microscopic hopping mechanism may be easily extended to investigate other abstract models and real materials in an NESS.Since our work only studied a 1-D abstract model coupled to the Andersen thermostat,whether or not these non-Boltzmann and non-Arrhenius behaviors are general in other models and thermostats is an interesting topic for future work.

# Acknowledgments

The authors thank the Supercomputing Center in the Computer Network Information Center at the CAS for allocations of computer time

# References

[1] H.Qian,J. Phys.Chem.B 110 (2006)15063. [2] H.Qian,Ann.Rev.Phys.Chem.58 (2007) 113. [3] H. Ge, M. Qian,and H. Qian, Phys. Rep. 510 (2012) 87.   
[4] Y. Demirel, Nonequilibrium Thermodynamics: Transport and Rate Processes in Physical, Chemical and Biological Systems, Elsevier, Amsterdam (2007). [5] M.Holz,Chem.Soc.Rev.23(1994) 165.   
[6] P.Kohn,K. Schroter,and T.Thurn-Albrecht,Phys. Rev. Lett.99 (2007) 086104.   
[7] H.W.Ellis,R.Y. Pai, E.W.McDaniel,E.A.Mason,and L.A.Viehland,Atom. Data Nucl. Data Tables17 (1976) 177.   
[8] J.P. England and M.T. Elford, Austr. J. Phys. 40 (1987) 355.   
[9] W. Zhao,F.Leroy, S.Balasubramanian,et al.,J.Phys. Chem.B 112(2008） 8129.   
[10] M.S. Kelkar and E.J. Maginn,J. Phys. Chem.B 111 (2007) 4867.   
[11] J.W. Daily and M.M. Micci, J. Chem.Phys.131 (2009) 094501.   
[12] S. Murad, J. Chem. Phys. 134 (2011) 114504.   
[13] J.Petravic and J. Delhommell,J. Chem. Phys.118 (2003) 7477.   
[14] A.D. Koutselos, J. Chem. Phys.134 (2011) 194301.   
[15] G.Balla and A.D.Koutselos,J. Chem.Phys.119 (2003) 11374.   
[16] A.D.Koutselos,J. Chem.Phys.106(1997) 7117.   
[17] A.D. Koutselos, J. Chem. Phys.104 (1996) 8442.   
[18] A.D. Koutselos, J. Chem. Phys. 102 (1995) 7216.   
[19] J.Delhommelle,P.T. Cummings，and J. Petravic，J. Chem.Phys.123(2005)114505..   
[20] N.J. English, D.A. Mooney, and S. O'Brien, Mol. Phys. 109 (2011） 625.   
[21] R. Shi and Y. Wang, J. Phys. Chem. B 117 (2013) 5102.   
[22] M.J.Polissar,J.Chem.Phys.6(1938) 833.   
[23] I. Bleyl, C. Erdelen, H.W. Schmidt,and D. Haarer, Philos.Mag.B 79（1999) 463.   
[24] Y.N. Gartstein and E.M. Conwell, Chem. Phys. Lett. 245 (1995) 351.   
[25] T. Ala-Nissila, R. Ferrando, and S.C. Ying, Adv. Phys. 51 (2002) 949.   
[26] A.M. Lacasta, J.M. Sancho,A.H. Romero, I.M. Sokolov, and K.Lindenberg,Phys.Rev.E 70 (2004) 051104.   
[27] H. Risken， The Fokker-Planck Equation: Methods of Solution and Application, Springer-Verlag,Berlin (1996).   
[28] K. Lindenberg,A.M. Lacasta,J.M. Sancho,and A.H. Romero,New J.Phys.7(2005) 29.   
[29] M. Khoury,A.M. Lacasta, J.M. Sancho,and K. Lindenberg,Phys.Rev.Lett.106(2011） 090602.   
[30] K. Lindenberg， J.M. Sancho，A.M. Lacasta, and I.M. Sokolov,Phys.Rev.Lett.98(2007) 020602.   
[31] P.Reimann and R.Eichhorn,Phys.Rev.Lett.101 (2008) 180601.   
[32] P. Reimann, C. Van den Broeck, H. Linke, P. Honggi, J. M.Rubi,and A.Pérz-Madrid,Phys.Rev.Lett.87 (2001) 010602.   
[33] P.Reimann,C.Van den Broeck,H. Linke,P. Honggi, J.M.Rubi,and A. Pérz-Madrid,Phys.Rev.E 65 (2002) 031104.   
[34] M. Khoury, J.P.Gleeson, J.M. Sancho, A.M. Lacasta, and K.Lindenberg,Phys.Rev.E 80 (2009) 021123.   
[35] K.Lindenberg, J.M. Sancho,M. Khoury, and A.M.Lacasta,Fluct.Noise Lett.11 (2012) 1240004.   
[36] K.Hayamizu and Y.Aihara,J. Phys.Chem.Lett.1 (2010) 2055.   
[37] S.H. Lee and J.C.Rasaiah,J. Chem. Phys.101 (1994) 6964.   
[38] G. Ren，R. Shi,and Y. Wang, J.Phys. Chem. B 118 (2014) 4404.   
[39] H.Zhao,R.Shi,and Y.Wang,Commun.Theor.Phys. 56 (2011) 499.   
[40] S.X. Sun, J. Chem. Phys.118 (2003) 5769.   
[41]H.Oberhofer，C.Dellago，and P.L.Geissler，J.Phys. Chem.B 109 (2005) 6902.   
[42] W.C. Swope, H.C. Andersen,P.H. Berens,and K.R.Wilson,J.Chem.Phys.76(1982)637.   
[43] H.C. Andersen, J. Chem. Phys. 72 (1980) 2384.   
[44] P. Jeevanandam and S.Vasudevan, J.Chem. Phys.109 (1998) 8109.   
[45] M. Nookala, B. Kumar，and S. Rodrigues， J. Power Sources 111 (2002） 165.   
[46] H. Tokuda,K.Hayamizu,K. Ishii,M.A.B.H. Susan,and M.Watanabe,J.Phys.Chem.B i08(2004) 16593.   
[47] S.Murugavel, Phys.Rev.B 72(2005) 134204.   
[48]S.Murugavel, C.Vaid,V.S.Bhadram,and C. Narayana, J.Phys.Chem.B 114(2010)13381.   
[49] S.J.Pas,R.D.Banhatti,and K. Funke,Solid State Ion. 177 (2006) 3135.   
[50] M. Schulz, Phys.Rev. B 57 (1998) 11319.   
[51] M.Goto,H. Takezoe,and K.Ishikawa, Phys.Rev.E 76 (2007)040701.   
[52] Z. Hu and C.J. Margulis,Proc.Natl. Acad. Sci.U.S.A. 103(2006） 831.   
[53] M.C.C. Ribeiro, Phys. Chem. Chem. Phys. 6 (2004) 771.   
[54] J.F. Nagle and H.J. Morowitz, Proc.Natl. Acad. Sci.75 (1978) 298.   
[55] D.H. Dunlap, P.E. Parris,and V.M. Kenkre, Phys. Rev. Lett. 77 (1996) 542.   
[56] E.Guardia, J. Marti,L.Garcia-Tarrés,and D.Laria, J. Mol. Liq.117 (2005) 63.   
[57] B.S.Mallik and A. Chandra,J. Chem. Phys.125 (2006) 234502.   
[58] L.Y. Chen and S.C. Ying,Phys. Rev. B 49 (1994) 13838.   
[59] P. Hanggi, P. Talkner,and M. Borkovec, Rev. Mod. Phys. 62 (1990) 251.   
[60] J. Kincs and S.W. Martin, Phys. Rev. Lett. 76 (1996) 70.   
[61] M.Malki,M. Micoulaut,F.Chaimbault,and Y.Vaills, Phys. Rev.Lett.96（2006) 145504.   
[62] C. Le6n, J. Santamaria,M.A. Paris, J. Sanz, J. Ibarra, and L.M. Torres,Phys.Rev.B 56(1997) 5302.   
[63] M. Ribes,G. Taillades,and A. Pradel, Solid State Ion. 105 (1998） 159.   
[64] P. Maass, M. Meyer,A. Bunde,and W. Dieterich, Phys. Rev.Lett.77(1996)1528.   
[65] R.Belin，A.Zerouale，A.Pradel,and M.Ribes,Solid State Ion.143(2001） 445.   
[66] K.Hayamizu,Y.Aihara,H. Nakagawa,T.Nukuda,and W.S. Price,J. Phys.Chem.B 108(2004) 19527.   
[67] M. Cutroni,A. Mandanici,A. Spanoudaki,and R.Pelster,J.Chem.Phys.114(2001) 7118.   
[68] F.Stickel,E.W.Fischer,and R.Richert,J.Chem.Phys. 104 (1996) 2043.   
[69] L.Dagdug and A.M. Berezhkovskii, J.Chem. Phys.131 （2009) 056101.