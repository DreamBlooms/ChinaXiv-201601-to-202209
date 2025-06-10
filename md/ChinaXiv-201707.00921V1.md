# Energy-Dependence of Nucleus-Nucleus Potential and Friction Parameter in Fusion Reactions

Kai Wen,1 Fumihiko Sakata, $^ { 2 , 1 }$ Zhu-Xia Li, $^ 3$ Xi-Zhen Wu,’ Ying-Xun Zhang,’ and Shan-Gui Zhou ${ } ^ { 1 , 4 , 5 , * }$

（20 $^ { 1 }$ State Key Laboratory of Theoretical Physics， Institute of Theoretical Physics, Chinese AcademyofSciences，Beijing 10019o,China $^ 2$ InstituteofApplied BeamScience,Gradate ShlofSiencendTehoogyaraki UnersityMito1851Jpan $^ 3$ China Institute of Atomic Energy， Beijing 102413， China （20 $^ 4$ Center of Theoretical Nuclear Physics,National Laboratory of Heavy Ion Accelerator,Lanzhou 73oo0, China （20 $^ { 5 }$ Center for Nuclear Matter Science, Central China Normal University， Wuhan 430079, China (Dated: July 30,2017)

Applying a macroscopic reduction procedure on the improved quantum molecular dynamics (ImQMD） model,the energy dependences of the nucleus-nucleus potential,the friction parameter, and the random force characterizing a one-dimensional Langevin-type description of the heavy-ion fusion process are investigated. Systematic calculations with the ImQMD model show that the fluctuation-disspation relation found in the symmetric head-on fusion reactions at energies just above the Coulomb barrier fades out when the incident energy increases. It turns out that this dynamical change with increasing incident energy is caused by a specific behavior of the friction parameter which directly depends on the microscopic dynamical process,i.e.,on how the collective energy of the relative motion is transferred into the intrinsic excitation energy.It is shown microscopically that the energy disspation in the fusion process is governed by two mechanisms: One is caused by the nucleon exchanges between two fusing nuclei,and the other is due to a rearrangement of nucleons in the intrinsic system.The former mechanism monotonically increases the dissipative energy and shows a weak dependence on the incident energy,while the latter depends on both the relative distance between two fusing nuclei and the incident energy.It is shown that the latter mechanism is responsible for the energy dependence of the fusion potential and explains the fading out of the fluctuation-dissipation relation.

PACS numbers:24.60.-k,24.10.Lx,25.60.Pj,25.70.Lm

# I. INTRODUCTION

Energy dissipation process observed in heavy-ion reactions ranging from deep-inelastic collisions to sub-barrier fusions has been described by various macroscopic transport models [1-14]. Although many of these macroscopic models are very successful in predicting the cross section of compound nucleus formation,their microscopic foundation,e.g.,how the colliding two nuclei fuse and how the relative kinetic energy dissipates into the intrinsic energy,still requires further research.

Besides these macroscopic transport models, many microscopic approaches like the time-dependent HartreeFock(TDHF) theory [15-28], the many-body correlation transport theory [29]，and the quantum molecular dynamics（QMD） [30,31],the antisymmetrized molecular dynamics [32,33]，and the fermion molecular dynamics [34] models have been developed.It is worthwhile mentioning that，among the TDHF approaches,there have been proposed new methods in recent years like the dissipative-dynamics（DD）TDHF [22,23] and the density-constrained(DC) TDHF [35,36] theories,which intend to explore how the macroscopic collective behavior of two colliding nuclei described by the Langevin-type equation appears as a result of huge dimensional microscopic dynamics.With the aid of these methods, the incident energy dependences of the macroscopic potential, the collective inertia parameter as well as the friction force have been derived from microscopic TDHF simula tions and the discussions of which are made in relation with the internal structure change of the colliding nuclei.

As is widely accepted, the above subject of heavy-ion fusion process is related to a more general problem, i.e., how to get a better understanding on various macroscopic collective behavior of non-equilibrium systems in a deeper level,which is currently studied in many fields of sciences,e.g., in physical and chemical as well as biological systems,by exploiting state-of-the-art $a b$ -initio numerical simulations of the molecular dynamics model [37, 38].

Recently,we have proposed a macroscopic reduction procedure based on the improved quantum molecular dynamics (ImQMD）model,aiming at exploring how the macroscopic Langevin-type equation emerges out of the microscopic dynamics in such a finite quantum manybody system as an atomic nucleus 39].We found that the dissipation dynamics of the relative motion between two fusing nuclei is caused by a non-Gaussian distribution of the random force.A clear non-Markovian effect was also observed in the time correlation function of the random force.Note that the non-Gaussian fluctuation isa general feature in non-equilibrium systems ranging from the cosmoscopic [40，41]，mesoscopic [42，43]，to microscopic systems [44]. Furthermore,as discussed in

Ref. [45], the non-Markovian dynamics were relevant in many fields and applications.

In this paper,we further develop our macroscopic reduction procedure applicable to the ImQMD model.An extension is based on a new method [46] which projects the effects of intrinsic degrees of freedom onto the collective subspace by transforming the time-scale into a macroscopic collective space-scale.With the aid of this macroscopic scale transformation，we explicitly extract the effects of intrinsic degrees of freedom in a convenient form that is appropriate for discussing the dynamical change of the fusion reaction from the adiabatic regime to the diabatic one. Exploiting the representation obtained after the transformation,one may clearly discuss how the dynamical role of the intrinsic system changes when the incident energy increases and how the energy transfer from collective motion to the intrinsic one,which is found to be carried out through both nucleon transfer between two fusing nuclei and the rearrangement effects in the intrinsic system.

The paper is organized as follows. In Sec.II,we briefly introduce the ImQMD model and recapitulate the macroscopic reduction procedure of the ImQMD model proposed in Ref. [39]. Applying the macroscopic reduction method of the ImQMD model to $^ { 9 0 } \mathrm { Z r + } ^ { 9 0 } \mathrm { Z r }$ head-on fusion reaction, in Sec.III,numerical results on the incident energy dependences of the random force, the fluctuationdissipation relation,and the fusion potential are discussed. In Sec.IV,we introduce various macroscopic quantities by further developing the macroscopic reduction procedure suitable for exploring the macroscopic dissipative motion. Applying these new quantities on the numerical simulations of the ImQMD model, it is clearly shown that the energy dissipation is characterized by two competitive microscopic processes. The energy dependence of the fluctuation-dissipation relation and that of the fusion potential are consistently explained as a result of these competitive factors. Concluding remarks are given in Sec.V.In the appendix,we give the derivation of the energy dissipation due to the nucleon exchange.

# II. IMQMDMODEL AND THEMACROSCOPIC REDUCTIONPROCEDURE

# A．ImQMD

Like in the original QMD model [30] and in various modern versions of QMD models [47-54]，a trial wave function for a nucleus in the ImQMD model [55-59] is restricted within a parameter space $\{ \mathbf { r } _ { j } , \mathbf { p } _ { j } \}$ ，where $\mathbf { r } _ { j }$ and $\mathbf { p } _ { j }$ are mean values of position and momentum operators of the $j$ th nucleon expressed by a Gaussian wave packet,and the total wave function is a direct product of these wave functions of Gaussian form.With the aid of a Wigner transformation,a nucleus composed of distinguishable $N$ nucleons is characterized by the following one-body phase space distribution function,

$$
f ( \mathbf { r } , \mathbf { p } ) = \sum _ { i } { \frac { 1 } { ( \pi \hbar ) ^ { 3 } } } \exp \left[ - { \frac { ( \mathbf { r } - \mathbf { r } _ { i } ) ^ { 2 } } { 2 \sigma _ { r } ^ { 2 } } } - { \frac { 2 \sigma _ { r } ^ { 2 } } { \hbar ^ { 2 } } } ( \mathbf { p } - \mathbf { p } _ { i } ) ^ { 2 } \right] ( 1 )
$$

and a density distribution function is expressed as

$$
\begin{array} { l } { \displaystyle \rho ( { \bf r } ) = \int f ( { \bf r } , { \bf p } ) d { \bf p } } \\ { \displaystyle = \sum _ { i } \frac { 1 } { ( 2 \pi \sigma _ { r } ^ { 2 } ) ^ { 3 / 2 } } \exp \left[ - \frac { ( { \bf r } - { \bf r } _ { i } ) ^ { 2 } } { 2 \sigma _ { r } ^ { 2 } } \right] , } \end{array}
$$

where $\sigma _ { r }$ represents the spatial width of the nucleon wave packet.

The time evolution of the system in question is governed by a set of canonical equations of motion

$$
{ \dot { \bf p } } _ { i } = - { \frac { \partial H } { \partial { \bf r } _ { i } } } , \quad { \dot { \bf r } } _ { i } = { \frac { \partial H } { \partial { \bf p } _ { i } } } ,
$$

which is derived from the time-dependent variational principle [30,32,34]. Upon that,collisions are included in the ImQMD simulations and the scattering angle of a single nucleon-nucleon collision is randomly chosen in such a way that the distribution of the scattering angles of all collisions agrees with the measured angular distribution for elastic and inelastic collisions [30]. The Hamiltonian $H$ consists of the kinetic energy and an effective interaction potential energy,

$$
H = T + U _ { \mathrm { l o c } } + U _ { \mathrm { C o u l } } .
$$

Here, $U _ { \mathrm { C o u l } }$ denotes the Coulomb energy and the nuclear potential energy $U _ { \mathrm { l o c } }$ is expressed as

$$
\begin{array} { c } { { \displaystyle U _ { \mathrm { l o c } } = \int V _ { \mathrm { l o c } } [ \rho ( { \bf r } ) ] d { \bf r } } , } \\ { { \displaystyle V _ { \mathrm { l o c } } [ \rho ] = \frac { \alpha } { 2 } \frac { \rho ^ { 2 } } { \rho _ { 0 } } + \frac { \beta } { \gamma + 1 } \frac { \rho ^ { \gamma + 1 } } { \rho _ { 0 } ^ { \gamma } } + \frac { g _ { \mathrm { s u r } } } { 2 \rho _ { 0 } } ( \nabla \rho ) ^ { 2 } } } \\ { { +  \frac { C _ { s } } { 2 \rho _ { 0 } } [ ( \rho ^ { 2 } - \kappa _ { s } ( \nabla \rho ) ^ { 2 } ] \delta ^ { 2 } + g _ { \tau } \frac { \rho ^ { \eta + 1 } } { \rho _ { 0 } ^ { \eta } } .  } } \end{array}
$$

In the present paper, $V _ { \mathrm { l o c } } [ \rho ]$ is defined by applying the effective Skyrme interaction energy density functional without the spin-orbit term. The isospin asymmetry $\delta = ( \rho _ { n } - \rho _ { p } ) / ( \rho _ { n } + \rho _ { p } )$ where $\rho , ~ \rho _ { n }$ ，and $\rho _ { p }$ are the nucleon,neutron,and proton densities,respectively. In the present work, the parameter set IQ2 is used [60].

After integration,one obtains the local interaction potential energy:

$$
\begin{array} { l } { { \displaystyle U _ { \mathrm { l o c } } = \frac { \alpha } { 2 } \sum _ { i } \sum _ { j \neq i } \frac { \rho _ { i j } } { \rho _ { 0 } } + \frac { \beta } { \gamma + 1 } \sum _ { i } \left( \sum _ { j \neq i } \frac { \rho _ { i j } } { \rho _ { 0 } } \right) ^ { \gamma } } } \\ { { \displaystyle \quad \quad + \frac { g _ { \mathrm { s u r } } } { 2 } \sum _ { i } \sum _ { j \neq i } f _ { s i j } \frac { \rho _ { i j } } { \rho _ { 0 } } + g _ { \tau } \sum _ { i } \left( \sum _ { j \neq i } \frac { \rho _ { i j } } { \rho _ { 0 } } \right) ^ { \eta } } } \\ { { \displaystyle \quad \quad + \frac { C _ { s } } { 2 } \sum _ { i } \sum _ { j \neq i } t _ { i } t _ { j } \frac { \rho _ { i j } } { \rho _ { 0 } } ( 1 - \kappa _ { s } f _ { s i j } ) } , } \end{array}
$$

where

$$
\begin{array} { l } { \displaystyle \rho _ { i j } = \frac { 1 } { ( 4 \pi \sigma _ { r } ^ { 2 } ) ^ { 3 / 2 } } \exp \left[ - \frac { ( \mathbf { r } _ { i } - \mathbf { r } _ { j } ) ^ { 2 } } { 4 \sigma _ { r } ^ { 2 } } \right] , } \\ { \displaystyle f _ { s i j } = \frac { 3 } { 2 \sigma _ { r } ^ { 2 } } \exp \left[ - \left( \frac { \mathbf { r } _ { i } - \mathbf { r } _ { j } } { 2 \sigma _ { r } ^ { 2 } } \right) ^ { 2 } \right] , } \end{array}
$$

and $t _ { i } ~ = ~ + 1$ for protons and $- 1$ for neutrons. The Coulomb energy is expressed as the sum of the direct and the exchange contribution

$$
\begin{array} { l } { { \displaystyle U _ { \mathrm { C o u l } } = \frac { 1 } { 2 } \int \int \rho _ { p } ( { \bf r } ) \frac { e ^ { 2 } } { | { \bf r } - { \bf r } ^ { \prime } | } \rho _ { p } ( { \bf r } ^ { \prime } ) d { \bf r } ^ { \prime } d { \bf r } } \ ~ } \\ { { \displaystyle ~ + e ^ { 2 } \frac { 3 } { 4 } \left( \frac { 3 } { \pi } \right) ^ { 1 / 3 } \int \rho _ { p } ^ { 4 / 3 } d { \bf r } } . } \end{array}
$$

For low energy nuclear reactions, the Pauli principle plays an important role [34,61]. In the ImQMD model,by using the phase space occupation constraint method [62], the fermionic properties of nucleons is approximately taken into account.

Many ImQMD simulations are made and each of them is called one event. We examine the average properties of these events and the deviation of each event from the average.For each event, to prepare the initial nuclei for the projectile and the target, the position and momentum of each nucleon are randomly given under certain macroscopic conditions,such as the binding energy and the radius. Numerical details can be found in Refs. [63,64].

# B.Macroscopic Reduction Procedure for ImQMD model

Since we focus on symmetric fusion reactions with the impact parameter equal to zero,we can introduce a separation plane at the center of mass (CoM) of the whole system,and divide the whole system into the left(projectile-like) and right- (target-like) half parts. The relative motion between two CoMs of the left and right parts is chosen to be the relevant degree of freedom to be described by the Langevin equation.

The one-dimensional generalized Langevin equation with memory effects is given as [2, 65-67]

$$
{ \frac { d P ( t ) } { d t } } = - \int _ { - \infty } ^ { t } \gamma ( t - t ^ { \prime } ) P ( t ^ { \prime } ) d t ^ { \prime } + \delta F ( t ) - { \frac { d U ( R ) } { d R } } ,
$$

where $P ( t )$ is the relative momentum between two parts, $\delta F ( t )$ is the random force felt by either part,and $U ( R )$ is the collective potential between two parts.The first term on the right hand side represents the retarded friction force.

Based on this stochastic equation,in the ImQMD simulations, the mean value of the relative momentum $\langle { P } \rangle _ { R }$ between two CoMs at a given $R$ is defined as

$$
\langle P \rangle _ { R } \equiv \frac { 1 } { n } \sum _ { i = 1 } ^ { n } P _ { i } ( t _ { i } ) | _ { \{ t _ { i } | R _ { i } ( t _ { i } ) = R \} } ,
$$

where $P _ { i } ( t )$ and $R _ { i } ( t )$ are the momentum and position of the $i$ -theventat time $t$ .The time $t _ { i }$ for the $i$ -thevent is chosen in such a way that the relative distance takes a given value $R$ ，i.e., $R _ { i } ( t _ { i } ) = R$ .In the present work, various microscopic variables are discussed as a function of relative distance $R$ instead of time $t$ ，because $R$ characterizes how near the two nuclei locate.In Eq.(1O) and hereafter, $\langle Q \rangle$ denotes an average of $Q$ over all events. When it does not cause any confusion,we hereafter use the same notation $Q ( R )$ for the single event $Q _ { i } ( R )$ as well as for the average $\textstyle \langle Q ( R ) \rangle = \sum _ { i = 1 } ^ { n } Q _ { i } ( R ) / n$ otherwise mentioned.

A collective potential for the relative motion is defined as,

$$
U ( R ) = E _ { \mathrm { t o t } } ( R ) - E _ { \mathrm { l e f t } } ( R ) - E _ { \mathrm { r i g h t } } ( R ) ,
$$

where $E _ { \mathrm { t o t } } ( R )$ ， $E _ { \mathrm { l e f t } } ( R )$ ，and $E _ { \mathrm { r i g h t } } ( R )$ represent the energy of the total system and those of the left and right parts,respectively. Each of them consists of the kinetic energy, the nuclear and the Coulomb potential energies, and numerical results of $U ( R )$ are shown in Figs.2 and 3(b). The DC- and DD-TDHF have been applied to extract the collective potentials between two nuclei [22,68] which gave similar features as those obtained in the present work and in other QMD simulations [69,70].

With the collective potential and the momentum，we define the collective energy as

$$
\begin{array} { l } { { E _ { \mathrm { c o l l } } ( R ) = T _ { \mathrm { c o l l } } ( R ) + U ( R ) , } } \\ { { T _ { \mathrm { c o l l } } ( R ) = \displaystyle \frac { \langle P \rangle _ { R } ^ { 2 } } { 2 \mu } , } } \end{array}
$$

where $\mu$ is the reduced mass of the system.After the two nuclei contact each other, $\mu$ becomes dependent on the relative distance $R$ and $E _ { \mathrm { c . m } }$ . [22,23, 64]. As our discussion is limited to regions of $R$ and $E _ { \mathrm { c . m } }$ .where $\mu$ does not change largely, in this work we take it to be a constant.

In the ImQMD simulations,the random force for the $i$ -th event is defined as

$$
\begin{array} { l } { { \displaystyle \delta F _ { i } ( R ) \equiv F ^ { i } ( R ) - \langle F ( R ) \rangle , } } \\ { { \displaystyle F ^ { i } ( R ) \equiv \sum _ { j = 1 } ^ { A } f _ { i } ^ { j } ( t ) \Big \vert _ { \{ t \mid R ( t ) = R \} } , } } \\ { { \displaystyle \langle F ( R ) \rangle \equiv \frac { 1 } { n } \sum _ { i = 1 } ^ { n } F ^ { i } ( R ) , } } \end{array}
$$

where $f _ { i } ^ { j } ( t )$ denotes,in the $i$ -th event, the force acting on the $j$ -th nucleon due to all other nucleons in the two fusing nuclei, $A$ is the number of nucleons contained in the left (right） part,and $n$ is the total number of events.

The fluctuation-dissipation relation links the energy dissipation of the collective energy $E _ { \mathrm { c o l l } } ( R )$ to the fuctuation force originated from the microscopic dynamics, both of which play decisive roles in the macroscopic description of dissipation phenomena.In the ImQMD simulations,the strength of the fluctuation is characterized

by

$$
\langle \delta F ( R ) \delta F ( R ) \rangle \equiv { \frac { 1 } { n } } \sum _ { i = 1 } ^ { n } \delta F _ { i } ( R ) \delta F _ { i } ( R ) .
$$

Assuming the work done by the collective motion against the friction force is completely converted into the intrinsic energy $E _ { \mathrm { i n t r } } ( R )$ ，we get a relation

$$
E _ { \mathrm { i n t r } } ( R ) \equiv E _ { \mathrm { c . m . } } - E _ { \mathrm { c o l l } } ( R ) ,
$$

where $E _ { \mathrm { c . m } }$ . means the initial bombarding energy. With the aid of the Rayleigh's dissipation function [71, 72] defined as

$$
\mathcal { F } \equiv \mu \gamma ( R ) ( d R / d t ) ^ { 2 } ,
$$

where $\gamma ( R )$ expresses the friction parameter without considering the non-Markovian effects,the rate of energy loss from the collective motion (which is equivalent to the energy gain of the intrinsic system under the above assumption） is expressed as $d E _ { \mathrm { i n t r } } = { \mathcal { F } } d t$ .From these relations, one gets

$$
\frac { d E _ { \mathrm { i n t r } } ( R ) } { d R } = \mu \gamma ( R ) \frac { d R } { d t } = \gamma ( R ) P .
$$

The friction parameter $\gamma _ { 0 }$ under the Markovian approximation is expressed as

$$
\gamma _ { 0 } ( R ) \equiv \frac { \langle F _ { \mathrm { f r i c } } ( R ) \rangle } { \langle P \rangle _ { R } } , \quad F _ { \mathrm { f r i c } } ( R ) \equiv \frac { d E _ { \mathrm { i n t r } } ( R ) } { d R } .
$$

It should be noticed that the $R$ -dependence of the friction parameter $\gamma ( R )$ contains a sensitive information on the dynamics of energy transfer from the collective motion to the intrinsic degrees of freedom，because it depends on the derivative of the collective potential $U ( R )$ with respect to $R$ ：

# III. INCIDENT ENERGYDEPENDENCEOF FLUCTUATION AND DISSIPATION

# A.Random force in the ImQMD simulations

Figure 1 shows the width of the random force,which is defined as the root mean square of $\delta F ( R )$ ，i.e.，the square root value of the strength of fluctuation defined in Eq. (16). In the case of $E _ { \mathrm { c . m . } } = 1 9 5$ MeV,the width of the random force turns out to be a smooth function of relative distance $R$ , reaching a peak at $R \cong 1 1$ fm which locates slightly inside of the Coulomb barrier and then levels out after a small down slope.At $R = 3 0$ fm where we start our numerical simulation,the fluctuation comes from the randomness of the position and momentum of each particle at the initial time when each event is initialized under the macroscopic conditions.This fluctuation propagates following the equation of motion (3). Since the scattering angles of the nucleon-nucleon collisions are randomly chosen in such a way that the distribution of the scattering angles of all collisions agree with the measured angular distribution for elastic and inelastic collisions in the QMD model [30], the randomness coming from the scattering may also contribute to the fluctuation.According to the shape of the distribution of the random force,we divide the whole process into three regions [39]. As is seen from Fig.1, the width is narrow and stays unchanged at $1 5 ~ \mathrm { f m } \lesssim R \lesssim 3 0$ fm (region I), indicating the stability of ImQMD simulations.

In region II (11 fm $\lesssim R \lesssim 1 5$ fm） where the two nuclei are going to merge into one nucleus,one may see that the width has a growing asymmetric component in addition to the symmetric Gaussian.It turns out [39] that the asymmetric distribution is caused by a small number of events where a few nucleons are exchanged between two nuclei; these nucleons play a role in opening a window. In the majority of events which contribute to the main part of the Gaussian distribution,all nucleons well split into two separated groups,expressing a projectile nucleus and a target nucleus and keeping their initial stable meanfields. As can be seen in Fig.1,after eliminating those events where a few nucleons are exchanged between two nuclei, one gets a Gaussian distribution for the random force (the dark blue part in the inset corresponding to $R = 1 3 . 5$ fm）and a smaller root mean square of the random force displayed by the pink diamond in region II.

After this merging stage,we may see that the width of the random force in region III has again a Gaussian shape which is,however,two order of magnitude wider than that in region I.The main origin of this enlargement is caused by the above discussed transferred nucleons that feel the nuclear force from the other nucleus.It is an open question whether this factor is related to the formation of a neck or not [4, 8, 9,12,73-79].

Figure 2 shows how the strength of random force and the friction parameter $\gamma _ { 0 } ( R )$ defined in Eq.(20) change depending on the initial bombarding energy $E _ { \mathrm { c . m . } }$ .One may see that the fluctuation $\langle \delta F ( R ) \delta F ( R ) \rangle$ and the fric tion coefficient $\gamma _ { 0 } ( R )$ at $E _ { \mathrm { c . m } }$ . = 195 MeV show similar shapes and their peaks locate at the same point. Such a bumped shape in the friction parameter near the Coulomb barrier energy is also observed in the DDTDHF calculations [23, 24].

When $E _ { \mathrm { c . m } }$ . increases, the friction parameter exhibits a sizable energy dependence. Comparing the case of （204号 $E _ { \mathrm { c . m . } } ~ = ~ 1 9 5$ MeV with that of $E _ { \mathrm { c . m . } } ~ = ~ 2 0 5$ MeV [Figs.2(a) and (b)]，one may recognize that the peak in the friction parameter disappears,while the strength of the random force keeps its shape almost unchanged. That is,a similarity between these two curves at energies just above the Coulomb barrier gradually disappears as $E _ { \mathrm { c . m } }$ .increases.When $E _ { \mathrm { c . m } }$ .increases more,the friction parameter shows a monotonically increasing behavior [Figs. 2(c) and (d)]. At the region near the barrier top 11 $\mathrm { f m } { \lesssim } R \lesssim 1 2$ fm,that is, the initial stage of fusion just after the capture,the higher the incident energy, the smaller the friction parameter,while the situation becomes reverse when the two colliding nuclei come closer with each other.

![](images/1b5a2185b324da06ffc61b61e51e2d2b6bb4432bd96763a18c529ad33878fde1.jpg)  
FIG.1.(Color online）Root mean square of the random force distribution as a function of relative distance $R$ ．Each inset showsatypicaldisibutioningionsI,IandIesectivelyInteisetcespondingtoatypicaldstributioingion I,the distribution is shifted so that the symmetric Gaussian distribution centers at $\delta F = 0$ ,but the mean value of the random force is stillzero.The pink diamondis theroot mean squareof therandom force after eliminating events in theasymmetric tail as shown by the inset in region II.

![](images/f43ed98bedad3a8f0d80e73da5e8b62e7079718b5754936720aefead890fc706.jpg)  
FIG.2.(Color online） The strength of random force $\langle \delta F ( R ) \delta F ( R ) \rangle ^ { \mathrm { t o t } }$ [red dots,in $\mathrm { ( M e V / f m ) ^ { 2 } ] }$ and the friction coefficient $\gamma _ { 0 } ( R )$ (blue squares, in $0 . 0 0 1 ~ c / \mathrm { f m }$ at $E _ { \mathrm { c . m . } } = 1 9 5$ MeV, 205 MeV, 215 MeV, and $2 3 5 ~ \mathrm { M e V }$ , respectively. The grey line shows the potential $U ( R )$ . Pink diamonds represent $\langle \delta F ( R ) \delta F ( R ) \rangle ^ { \mathrm { s y m } }$ which is obtained by eliminating events in the asymmetric tail.

Note that in the ImQMD simulations, the nucleon collision effects are included in addition to the one-body dissipation.From the above discussions,it is seen that the ImQMD model gives similar energy dependence and magnitude of the friction parameter as those of the TDHF calculations [23, 24, 80],indicating a dominance of onebody dissipation in the energy region under discussion.

# B．Incident Energy Dependences of Collective Kinetic,Potential,and Intrinsic Energies

Recently, it becomes clear that the collective potential $U ( R )$ exhibits rather sensitive energy dependence when $E _ { \mathrm { c . m } }$ . takes near the Coulomb barrier energy [22, 80, 81]. It has been discussed that this energy dependence might be related to the dynamical change from adiabatic to sudden fusion process: The two fusing nuclei have enough time to rearrange their intrinsic structure when $E _ { \mathrm { c . m } }$ ： is just above the Coulomb barrier energy,and the nonadiabatic effects gradually play a role as $E _ { \mathrm { c . m } }$ . increases. However, the above arguments are mainly based on the bulk information like the density distribution of many nucleons,without referring to any microscopic dynamics of individual nucleons.Next we investigate the incident energy dependences of the collective kinetic energy $T _ { \mathrm { c o l l } } ( R ) \equiv E _ { \mathrm { c o l l } } ( R ) - U ( R )$ ， the potential energy $U ( R )$ 5 and the intrinsic energy $E _ { \mathrm { i n t r } } ( R )$ with the microscopic ImQMD model.

Figure 3(a) shows the $R$ -dependence of collective kinetic energy $T _ { \mathrm { c o l l } } ( R )$ as a function of relative distance at $E _ { \mathrm { c . m . } } = 1 9 5$ MeV and $E _ { \mathrm { c . m . } } = 2 3 5$ MeV.In the case of $E _ { \mathrm { c . m . } } = 1 9 5$ MeV, the main part of the collective kinetic energy has already changed into a form of collective potential energy just after the collective motion overcomes the Coulomb barrier at $R \cong 1 2 . 5$ fm. Since there remains about 3MeVrather constant collective kinetic energyin 8 $3 ~ \mathrm { f m } \le \ R \lesssim 1 1 . 5$ fm as is shown in the inset of Fig. 3(a)，the fusing process takes place very slowly. In the case of $E _ { \mathrm { c . m . } } = 2 3 5$ MeV,after passing through the barrier,the collective kinetic energy takes almost ten times larger value than that in the case of $E _ { \mathrm { c . m . } } = 1 9 5$ MeV,and shows continuous down slope without reachinga constant value.Here,it should be mentioned that the dissipated energy (equivalent to $E _ { \mathrm { i n t r } }$ )at $E _ { \mathrm { c . m . } } = 2 3 5$ MeV is much smaller than that at $E _ { \mathrm { c . m . } } = 1 9 5$ MeVin the region $9 ~ \mathrm { f m } \lesssim R \lesssim 1 1 . 5$ fm as shown in Fig. 3(c), which is caused by the same reason why the friction parameter gets reduced as $E _ { \mathrm { c . m } }$ .increases.This point will be clarified in Sec. IV.

By comparing $E _ { \mathrm { i n t r } } ( R )$ in Fig.3(c)with $U ( R )$ and $T _ { \mathrm { c o l l } } ( R )$ in Figs.3(a) and 3(b),one finds that the dissipated energy at $E _ { \mathrm { c . m . } } = 2 3 5$ MeV is around 30 MeV smaller than that at 195 MeV,while $U ( R )$ is around 30 MeVlarger at $R \cong 1 0$ fm.This means that the friction force is not proportional but inversely proportional to the momentum of the collective motion at the initial stage of fusion process at $R \cong 1 0$ fm. In Fig. 3(b), the grey line shows the potential energy calculated under the frozen approximation,i.e., the potential calculated by fixing the density distribution of the projectile and target and making them overlapped at a given $R$ . The barrier height is about 182 MeV. The deviation of $U ( R )$ from this potential energy under the frozen approximation could be attributed to the rearrangement effect of all the intrinsic degrees of freedom,which will be discussed in the next section.

![](images/7c0b2f053fd56f5da59483b0898ede1d88412f260daf9be43a2e03f93e84235b.jpg)  
FIG.3.(Color online)(a) Collective kinetic energy $T _ { \mathrm { c o l l } } ( R ) =$ $E _ { \mathrm { c o l l } } ( R ) - U ( R )$ ，(b）potential energy $U ( R )$ ,and(c） intrinsic energy $E _ { \mathrm { i n t r } } ( R )$ as functions of relative distance $R$ . The red line represents results at $E _ { \mathrm { c . m . } } = 1 9 5$ MeV and the blue line shows results at $E _ { \mathrm { c . m . } } = 1 9 5$ MeV.In (a),the inset shows the kinetic energy from 8 fm to 10 fm at $E _ { \mathrm { c . m . } } ~ = 1 9 5$ MeV.In (b),the light grey line shows the potential energy calculated under the frozen approximation.

# IV. MICROSCOPICDYNAMICSOFENERGY DISSIPATION

In the previous Section， we have discussed $E _ { \mathrm { c . m } }$ -. dependence of the nucleus-nucleus potential $U ( R )$ as well as that of the friction parameter $\gamma _ { 0 } ( R )$ . Since the significant $E _ { \mathrm { c . m . } }$ -dependence occurs near the Coulomb barrier energy where the applicability of the adiabatic approximation is gradually replaced by that of the sudden approximation when $E _ { \mathrm { c . m } }$ .increases,let us introduce new macroscopic quantities and further develop the macroscopic reduction procedure.

# A.New Quantities Based on Macroscopic Reduction Procedure

In this Subsection,we discuss how the collective energy is transferred into the intrinsic one by dividing the dissipation into two processes.The first one is caused by the nucleon transfer which takes place frequently between the left and right parts of the whole system,and the amount of energy transferred from the relative kinetic energy to the intrinsic one up to a point $R$ is given by $T _ { \mathrm { d i s s } } ( R )$ in Eq. (A2) in Appendix A.

To discuss the second process of dissipation，we pay attention to $F _ { \mathrm { i n t r } } ^ { i } ( R )$ for the $i$ -th event which expresses thedifferencebetween the forceobtainedbydifferentiating the nucleus-nucleus potential $U ( R )$ in Eq.(11)and that obtained by summing all the nucleon-nucleon forces in Eq. (14). $F _ { \mathrm { i n t r } } ^ { \imath } ( R )$ is defined as,

$$
\begin{array} { r l r } & { } & { F _ { \mathrm { i n t r } } ^ { i } ( R ) \equiv F _ { \mathrm { t o t } } ^ { i } ( R ) - F _ { \mathrm { c o l l } } ^ { i } ( R ) , ~ } \\ & { } & { F _ { \mathrm { t o t } } ^ { i } ( R ) \equiv - \displaystyle \frac { \partial U ^ { i } ( R ) } { \partial R } , ~ F _ { \mathrm { c o l l } } ^ { i } ( R ) \equiv F ^ { i } ( R ) , } \end{array}
$$

where $U ^ { i } ( R )$ and $F ^ { i } ( R )$ for the $i$ -th event are given in Eqs.(11） and (14)，respectively. For the sake of convenience, $F _ { \mathrm { c o l l } } ^ { i } ( R )$ and $F _ { \mathrm { t o t } } ^ { \imath } ( R )$ will be_calledas the collective force and the total nucleus-nucleus force,respectively. Corresponding to the collective force $F _ { \mathrm { c o l l } } ^ { i } ( R )$ ,one may introduce another potential $U _ { \mathrm { c o l l } } ^ { i } ( R )$ defined by

$$
U _ { \mathrm { c o l l } } ^ { i } ( R ) \equiv - \int _ { \infty } ^ { R } F _ { \mathrm { c o l l } } ^ { i } ( R ^ { \prime } ) d R ^ { \prime } , \quad U _ { \mathrm { c o l l } } ^ { i } ( \infty ) = 0 ,
$$

which expresses the work done by the collective system against $F _ { \mathrm { c o l l } } ^ { \imath } ( R )$ up to the point $R$ Using $U _ { \mathrm { c o l l } } ( R )$ together with $U ( R )$ in Eq. (11),in addition to the difference in Eq. (21),one may further introduce a deference as

$$
\begin{array} { r l r } {  { W ( R ) = - \int _ { \infty } ^ { R } d R ^ { \prime } ( F _ { \mathrm { t o t } } ^ { i } - F _ { \mathrm { c o l l } } ^ { i } ) } } \\ & { } & { = - \int _ { \infty } ^ { R } d R ^ { \prime } F _ { \mathrm { i n t r } } ( R ^ { \prime } ) . \quad } \end{array}
$$

Asis well known, the reduction of many-body dynamics onto a one-dimensional collective space inevitably introduces additional effects coming from the intrinsic degrees of freedom,besides the genuine effect within the collective space. That is, $F _ { \mathrm { i n t r } } ^ { i } ( R )$ and $W ( R )$ originally acting in the intrinsic space are expressed as the additional force and additional potential in the collective space because of eliminating the intrinsic degrees of freedom,and of changing the time-scale into the collective space-scale introduced in Eq. (1O). More generally, it is shown analytically [46] that the dynamics in the collective system and that in the intrinsic system are distinguishable when one applies the macroscopic reduction procedure on the ImQMD simulations.

The additional potential $W ( R )$ is then regarded as the work done by the intrinsic system to rearrange its state which has been disturbed by the transferred nucleons. In other words, $- W ( R )$ represents the second process which changes the energy in the intrinsic system.With the aid of $W ( R )$ and $T _ { \mathrm { d i s s } } ( R )$ , the total amount of energy transferred from the relative motion to the intrinsic one is given by

$$
E _ { \mathrm { d i s s } } ( R ) = T _ { \mathrm { d i s s } } ( R ) - W ( R ) ,
$$

where the former is from the collective kinetic energy through the nucleon transfer,and the latter is due to the rearrangement of the intrinsic system.

To test our calculation,we may pay attention to a new quantity defined through

$$
K _ { \mathrm { d i s s } } ( R ) \equiv E _ { \mathrm { c . m . } } - \left\{ \frac { P ^ { 2 } } { 2 \mu } + U _ { \mathrm { c o l l } } ( R ) \right\} ,
$$

where $U _ { \mathrm { c o l l } } ( R )$ is defined in Eq. (22). It should be noticed that there holds an energy conservation law within the collective degree of freedom as

$$
E _ { \mathrm { c . m . } } \cong T _ { \mathrm { d i s s } } ( R ) + \left\{ \frac { P ^ { 2 } } { 2 \mu } + U _ { \mathrm { c o l l } } ( R ) \right\} ,
$$

where $T _ { \mathrm { d i s s } } ( R )$ means the dissipated energy due to nucleon exchange defined in Eq.(A2) as mentioned at the beginning of this Subsection，provided that there holds the relation

$$
T _ { \mathrm { d i s s } } ( R ) \cong K _ { \mathrm { d i s s } } ( R ) .
$$

In the following, the validity of Eq.(27) will be shown with numerical simulations. By using Eq. (24),the ap proximate energy conservation law in Eq.(26) is then expressed as

$$
E _ { \mathrm { c . m . } } \cong E _ { \mathrm { d i s s } } ( R ) + \frac { P ^ { 2 } } { 2 \mu } + U _ { \mathrm { c o l l } } ( R ) + W ( R ) .
$$

Since the relation

$$
E _ { \mathrm { i n t r } } ( R ) \approx E _ { \mathrm { d i s s } } ( R ) ,
$$

is satisfied [c.f. Fig. 5 and relevant discussions], Eq. (28) is reduced to Eq.(17) which expresses an energy conservation of the total system.

![](images/c272ccfbfa823864cdc8b96f8665d709177205d995bcd846b89a32297f584338.jpg)  
FIG.4.(Color online) $F _ { \mathrm { i n t r } } ( R )$ ，the difference between the total nucleus force $F _ { \mathrm { t o t } } = - \partial U ( R ) / \partial R$ and the collective force $F _ { \mathrm { c o l l } } ( R )$ for the case of (a) $E _ { \mathrm { c . m . } } = 1 9 5$ MeV and (b) $E _ { \mathrm { c . m . } } =$ 235 MeV.“I” and “II" in each subfigure correspond to regions I and I defined in Fig.1.   
FIG.5.(Color online) Two microscopic sources of dissipation and its comparison with an increase of intrinsic energy.(a) $T _ { \mathrm { d i s s } } ( R )$ is from nucleon exchange process. (b) $W ( R )$ is due to the rearrangement effects in the intrinsic system.(c) and (d) show the difference between two processes $E _ { \mathrm { d i s s } } = T _ { \mathrm { d i s s } } ( R ) -$ $W ( R )$ compared to the intrinsic energy $E _ { \mathrm { i n t r } } ( R )$ at $E _ { \mathrm { c . m . } } =$ 195 MeV and $E _ { \mathrm { c . m . } } = 2 3 5$ MeV respectively.

# B.Two Microscopic Processes of Energy Dissipation

Making clear what information we get from the energy dependence of the collective potential $U ( R )$ ,we first examine $F _ { \mathrm { i n t r } } ( R )$ .It expresses what happens in the intrinsic system when many nucleons are exchanged between two nuclei, and when two nuclei closely approach each other. It also tells us how these effects subsequently develop inside of the intrinsic system，which are usually considered as the rearrangement of the intrinsic system.

As is seen from Fig.4, our numerical simulation tells us that $F _ { \mathrm { i n t r } } ( R )$ takes positive value in the range of 10.5 fm $\lesssim$ $R \lesssim 1 2 . 5$ fm (10.0 fm $\lesssim R \lesssim 1 2 . 5$ fm) and negative value at $R \lesssim 1 0 . 5$ fm ( $R$ ≤10 fm) in the case of $E _ { \mathrm { c . m . } } = 1 9 5$ $\cdot E _ { \mathrm { c . m . } } = 2 3 5$ ）MeV.It is also recognized from this figure that $F _ { \mathrm { i n t r } } ( R )$ in the case of $E _ { \mathrm { c . m . } } = 1 9 5$ MeV shows much stronger $R$ -dependence than that of $E _ { \mathrm { c . m . } } = 2 3 5$ MeV.A steep slope of $F _ { \mathrm { i n t r } } ( R )$ in the region 9 fm $\lesssim R \lesssim 1 1$ fm at $E _ { \mathrm { c . m . } } = 1 9 5$ MeV indicates that the rearrangement of the intrinsic system takes place more strongly than that in the case of $E _ { \mathrm { c . m . } } = 2 3 5$ MeV.

Since the intrinsic system is kept unchanged in the region $R > 1 2 . 0$ fm irrespective of $E _ { \mathrm { c . m . } }$ ，which is expected from Fig.3(c)，it is reasonable that $F _ { \mathrm { i n t r } } ( R )$ does not take any appreciable value in this region. In the case of $E _ { \mathrm { c . m . } } = 1 9 5$ MeV, the adiabatic approximation is expected to be applicable because of a strong rearrangement of the intrinsic system.In the case of $E _ { \mathrm { c . m . } } = 2 3 5$ MeV，however,there appears more gentle slope which indicates rather weak rearrangement effect in the intrin

(a) = 195 MeV 1020 E = 235 MeV c.m. sSIPL 80 40 0 (AJ1) (Y) M - 80 (b) Ec. m.= 195 MeV 40 E = 235MeV c.m. 0 40 -80 8 10 12 14 16 R (fm) 200 (c) Ec. m.= 195 MeV 160 Tdiss(R) - W (R) 80 Eintr(R) 40 0 200 160 (d) Ec.m. =235MeV 120 (R) - W (R) 80 Eintr (R) 40 0E 8 10 12 14 16 18 R (fm)

sic system.In this case,the main parts of original nuclei invade into each other with much shorter distance $R$ so that the frozen density and/or sudden approximation may have more sense than the case with $E _ { \mathrm { c . m . } } ~ = ~ 1 9 5$ MeV.

Let us discuss $W ( R )$ which is the integrated value of the difference $F _ { \mathrm { i n t r } } ( R )$ .Equation (24) tells us that the increase of $E _ { \mathrm { d i s s } } ( R )$ comes from two sources,i.e., $T _ { \mathrm { d i s s } } ( R )$ and $W ( R )$ .As is discussed in Appendix A,the former comes from the nucleon transfer between two fusing nuclei,enhances the dissipation,and might be related to the window effect.On the other hand,the latter is caused by the rearrangement process of the intrinsic system. Namely, the disturbance due to the nucleon exchange, and the subsequent process of forming a new state like an excited mean-field in the intrinsic system play a role to first enhance the dissipation and subsequently to suppress it.

In Fig. 5， two microscopic sources of dissipation $T _ { \mathrm { d i s s } } ( R )$ and $W ( R )$ ，and their combined effects $E _ { \mathrm { d i s s } } ( R )$ in comparison with $E _ { \mathrm { i n t r } } ( R )$ defined in Eq.(17）are shown.Figures $5 ( \mathrm { c } )$ and 5(d) show that there well holds the relation given in Eq. (29） irrespective of the initial bombarding energy. From this figure,one may conclude that the energy transfer from the collective motion to the intrinsic one in the region $8 \mathrm { f m } \lesssim R \lesssim 1 1 . 5$ fm can be understood microscopically as follows.Firstly, the nucleon exchange process always contribute largely to the dissipation and the dissipated energy $T _ { \mathrm { d i s s } } ( R )$ can reach around 150 MeV. Secondly, the rearrangement effect of intrinsic system may either enhance or suppress the dissipation, depending on the relative distance $R$ . Thirdly, the rearrangement effect is very sensitive to the incident energy. For the case of $E _ { \mathrm { { c m } } } = 1 9 5$ MeV,the rearrangement effect is very pronounced and $- 6 0$ MeV $< W ( R ) < 4 0$ MeV.This is because that, the fusion takes place slowly and there is much time for the whole system to rearrange nucleons. In other words, the fusion process goes adiabatically. However, for the case of $E _ { \mathrm { { c m } } } = 2 3 5$ MeV,the rearrangement effect is less pronounced and $- 2 0$ MeV $< W ( R ) < 2 0$ MeV.In this case,the fusion is mainly diabatic.Theadiabatic ordiabaticcharacteristics in the fusion will be discussed in more detail in next Subsection.

From the above numerical results,one may see that the nucleus-nucleus interaction $F _ { \mathrm { t o t } } ( R )$ is reduced to the simple summation of constituent forces $F _ { \mathrm { c o l l } } ( R )$ ，provided there are no internal correlations in the intrinsic system. Namely $F _ { \mathrm { i n t r } } ( R )$ in Eq. (21) expresses the amount of correlations inside the intrinsic system.

At the end of this Subsection,we pay attention to another approximate way of calculating $T _ { \mathrm { d i s s } } ( R )$ given by Eq.(A2). In Fig. 6,we show the calculated $U _ { \mathrm { c o l l } } ( R )$ and $K _ { \mathrm { d i s s } } ( R )$ . Comparing Fig.6(b) with Fig.5(a)，one can draw a conclusion that there holds the relation in Eq.(27). That is, the dissipation energy due to the nucleon exchange $T _ { \mathrm { d i s s } } ( R )$ is well reproduced by $K _ { \mathrm { d i s s } } ( R )$ defined in Eq. (25) which only takes account of the potential $U _ { \mathrm { c o l l } } ( R )$ without considering the internal correlation $W ( R )$ of the intrinsic system.

# C. Adiabatic vs.Diabatic Processes

In the previous Subsection,it is clearly shown that the fusion potential $U ( R )$ observed in Fig.3(c) can be divided into two different components $U _ { \mathrm { c o l l } } ( R )$ and $W ( R )$ which are depicted in Figs.6(a) and 5(b)，respectively. Since

240 (a) 160 120 H = 195 MeV c.m. 80 E = 235 MeV c.m. （） (y) sspy N 240 200 (b) E =195MeV c.m. 160 E = 235MeV c. m. 120 80 40 0F 8 10 12 14 16 R (fm)

the energy dependence of $W ( R )$ is discussed in the previous Subsection,let us explore the energy dependence of $T _ { \mathrm { d i s s } } ( R )$ which gives information on the incident energy dependence of $U _ { \mathrm { c o l l } } ( R )$ . From Figs. 5(a) and 6(b), the most important point to be explored on the energy dependence of $T _ { \mathrm { d i s s } } ( R )$ and $K _ { \mathrm { d i s s } } ( R )$ is why the collective energy dissipation through the nucleon transfer occurs more frequently at remote distance in the case of $E _ { \mathrm { c . m . } } = 1 9 5$ MeV than the case of $E _ { \mathrm { c . m . } } = 2 3 5$ MeV.

In Fig.7(a), the nucleon exchange rate defined as the number of nucleons which go through the separation plane per unit time is shown as a function of $R$ .In the region 9.5 fm $\lesssim R \lesssim 1 3$ fm,there are almost no appreciable incident energy dependence in the nucleon exchange rate,though it becomes larger in the case of $E _ { \mathrm { c . m . } } = 2 3 5$ MeV than the case of $E _ { \mathrm { c . m . } } ~ = ~ 1 9 5$ MeV for $R \lesssim 9 . 5$ fm.In Fig.7(b),the total number of nucleons $N _ { \mathrm { e x } } ( R )$ which have ever transferred up to a distance $R$ is shown. From Fig.3(a),one may see that the kinetic energy of relative motion around $R \approx 1 3$ fm at $E _ { \mathrm { c . m . } } = 2 3 5$ MeV is more than 40 MeV larger than that at $E _ { \mathrm { c . m . } } ~ = ~ 1 9 5$ MeV.Namely, the velocity in the former case is a few times faster than that in the case at $E _ { \mathrm { c . m . } } = 1 9 5$ MeV. From Figs.3(a) and 7(b)，one may recognize that,at $E _ { \mathrm { c . m . } } ~ = ~ 2 3 5$ MeV,the nuclei approach each other too fast to exchange comparable amount of nucleons as in the case of $E _ { \mathrm { c . m . } } = 1 9 5$ MeV.In other words,the two nuclei at $E _ { \mathrm { c . m . } } ~ = ~ 2 3 5$ MeV keep much larger part of their original shapes into a small relative distance $R$ than that at $E _ { \mathrm { c . m . } } = 1 9 5$ MeV.This mechanism explains the rather slow startup of the $T _ { \mathrm { d i s s } } ( R )$ and $K _ { \mathrm { d i s s } } ( R )$ in the case of $E _ { \mathrm { c . m . } } ~ = ~ 2 3 5$ MeV observed in Figs. 5(a) and

![](images/c5eba8e007f2fe15755c649d624a3fd6917a6d0bc63319ccedb021156bc7f5a7.jpg)  
FIG.7.(Color online) (a) Nucleon exchanging rate as a function of relative distance,(b) Total number of nucleons which has ever transferred from left (or right) part to the right (or left).The red and blue lines represent two cases with $E _ { \mathrm { c . m . } } =$ 195 and 235 MeV,respectively.

6(b). Since there holds the relation given in Eq. (25), the above discussed diabatic aspect of nucleon transfer process and the large collective momentum in the region 8 fm $\lesssim R \lesssim 1 1$ fm for the case of $E _ { \mathrm { c . m . } } = 2 3 5$ MeVare two microscopic ingredients to determine the amount of work $U _ { \mathrm { c o l l } } ( R )$ done by the collective degrees of freedom.

In order to show whether or not our microscopic discussion based on the role of $F _ { \mathrm { i n t r } } ( R )$ [and $W ( R ) ]$ is consistent with the understanding obtained by the density profile, the density at $E _ { \mathrm { c . m . } } = 1 9 5$ MeV and $E _ { \mathrm { c . m . } } = 2 3 5$ MeV, as well as that corresponding to the frozen density at different $R$ are depicted in Fig.8(a). The density profile under the frozen density approximation is obtained by fixing the density distribution of the projectile and target and making them overlapped at a given $R$ by hands.An obvious difference in the density distribution among these three cases is observed at the central part or the “neck” region of the system.This situation is displayed more clearly by the densities along the reaction axis shown in Fig. 8(b), which shows the nucleon number densities along the reaction axis $Z$ with $X = Y = 0$ at $R = 1 0 . 5$ fm.From these figures,one may learn that the density at $E _ { \mathrm { c . m . } } = 1 9 5$ MeV in the neck region is obviously higher than the case at $E _ { \mathrm { c . m . } } = 2 3 5$ MeV,and the latter case gives a similar profile as that of the frozen density. This lower density at the neck region in the latter case just corresponds to the smaller number of transferred nucleons which explain the slower startup of the transfer process $T _ { \mathrm { d i s s } } ( R )$ in the case of $E _ { \mathrm { c . m . } } = 2 3 5$ MeV.

# D. Friction parameter

We are now in the position to discuss the energy dependence of the friction parameter $\gamma _ { 0 } ( R )$ shown in Fig. 2.According to the macroscopic reduction procedure, the friction parameter is derived in Eq. (2O)． Consequently, the energy dependence of the friction parameter is directly related to that of the nucleus-nucleus fusion potential which is shown in Fig. 3(b). From Figs.3(b) and (c),one may recognize that the $U ( R )$ and $E _ { \mathrm { i n t r } } ( R )$ at $E _ { \mathrm { c . m . } } ~ = ~ 1 9 5$ MeV show an inflection point at $R \approx$ 11.5 fm,while at $E _ { \mathrm { c . m . } } ~ = ~ 2 3 5$ MeV such an inflection point does not exist.This inflection point is responsible for the peak structure of the friction parameter shown in Fig. 2(a).

Using $E _ { \mathrm { i n t r } } ( R ) \simeq E _ { \mathrm { d i s s } } ( R )$ ，and from Eqs.(20）and (24),the friction parameter can also be expressed as

$$
\gamma _ { 0 } ( R ) = \frac { 1 } { \langle P \rangle _ { R } } \left. \left( \frac { d T _ { \mathrm { d i s s } } ( R ) } { d R } - \frac { \partial W ( R ) } { \partial R } \right) \right. .
$$

which tells us that the friction parameter is determined by two microscopic processes,i.e., the nucleon exchange and the rearrangement. Since the $R$ dependence of $T _ { \mathrm { d i s s } } ( R )$ does not have the inflection point irrespective of the incident energy in Fig. 5(a),one may see that the first derivative of $T _ { \mathrm { d i s s } } ( R )$ with respect to $R$ does not show a strong incident energy dependence.On the other hand, $- W ( R )$ shown in Fig. 5(b) has a strong incident energy dependence.

In Fig. 9, the $R$ -dependence of the friction parameter is shown together with the two components originating from two different microscopic processes. The bumped structure of the friction parameter in the case of $E _ { \mathrm { c . m . } } =$ 195 MeV can be understood to be a pronounced intrinsic effects at $R \simeq 1 1$ fm [c.f. $F _ { \mathrm { i n t r } } ( R )$ shown in Fig. 4]. This bumped structure disappears rather quickly as $E _ { \mathrm { c . m } }$ .increases,because the rearrangement effects of the intrinsic system around $R \cong 1 1 . 0$ fm become small,which is observed from Fig. 4.

At the end of this Subsection, some comments on the validity of the fluctuation-dissipation relation should be addressed.As is mentioned above,the $E _ { \mathrm { c . m } }$ . dependence of the friction parameter is directly related to the rearrangement effects in the intrinsic system expressed by $F _ { \mathrm { i n t r } } ( R )$ ．On the other hand,the fluctuation $\delta F ( R )$ is related to $F _ { \mathrm { c o l l } } ( R )$ which does not depends on the rearrangement taking place in the intrinsic system,and the shape change in the correlation function of the fluctuation does not show an energy dependence as is seen from Fig.2.According to these different microscopic effects on the friction parameter and on the fluctuation force, the fluctuation-dissipation relation realized at $E _ { \mathrm { c . m . } } ~ = ~ 1 9 5$ MeVbreaks down when the incident energy increases.

![](images/e080bcf7b72847850893c8059cc953871598946518537bf484b4b21609c9cbd3.jpg)  
FIG.8.(Color online)(a) Density profiles obtained in ImQMD for different relative distances $R$ at $E _ { \mathrm { c . m . } } { = } 1 9 5$ MeV and 235 MeV and those with the frozen density. The abscissa axis is the reaction axis $Z$ and the vertical axis is axis $Y$ .（b）Nucleon number density along the reaction axis $Z$ with $X = Y = 0$ at relative $R = 1 0 . 5$ fm obtained by the ImQMD model. The red line represents the density at $E _ { \mathrm { c . m . } } = 1 9 5$ MeV,the blue line at $E _ { \mathrm { c . m . } } = 2 3 5$ MeV. The dark grey dashed line is the density with frozen density,the light grey dashed-dotted lines are densities for projectile and target.

# V.CONCLUDINGREMARKS

In this paper,we have systematically studied the incident energy dependence of the nucleus-nucleus potential, that of the friction parameter,as well as that of the random force in heavy-ion fusion reactions,by applying the macroscopic reduction procedure based on the ImQMD numerical simulation. Making the discussion clear,we focus our attention on the head-on fusion reaction of symmetric $^ { \mathrm { y 0 } } \mathrm { Z r } + ^ { \mathrm { y 0 } } \mathrm { Z r }$ system at above the Coulomb barrier energies and pay special attention to the fluctuationdissipation relation.

It should be mentioned that our discussion is based on a separation of the total nucleus-nucleus force $F _ { \mathrm { t o t } } ( R )$ into the collective part $F _ { \mathrm { c o l l } } ( R )$ and the intrinsic part $F _ { \mathrm { i n t r } } ( R )$ .Although the latter also depends on the relative distance $R$ rather than the intrinsic coordinates,one may regard $W ( R )$ as the work performed by the intrinsic system against $F _ { \mathrm { i n t r } } ( R )$ ．A theoretical justification of this point will be given in Ref. [46],where a reduction of the many-body dynamics onto one-dimensional collective space is discussed.In the present paper,it is numerically shown that there holds the relation given in Eq. (27), i.e., $T _ { \mathrm { d i s s } } ( R ) \approx K _ { \mathrm { d i s s } } ( R )$ which gives another justification for the above separation. By exploiting the procedure appropriate for the ImQMD numerical simulations,the first step toward the dynamics of emergence about how the macroscopic fusion dynamics comes out as a result of the microscopic nucleonic motion is clarified.

FIG.9.(Color online) $R$ -dependence of friction parameter caused by two competitive microscopic processes at (a) $E _ { \mathrm { c . m . } } = 1 9 5$ MeV and (b) $E _ { \mathrm { c . m . } } = 2 3 5$ MeV.The blue dashed line shows effects of nucleon exchange. The red dashed line shows effects of rearrangement in intrinsic system.

We note that more study should be performed with non-zero impact parameters and for different reaction systems,particularly for asymmetric reactions. The spinorbit coupling has been shown to be very important in low-energy heavy-ion fusion reactions [19,27]. Furthermore,it was also found that the negative shell correction energies lower potential barriers [53]. Therefore，more dissipations are expected if these effects are included in the ImQMD simulations.Finally,detailed investigations should also be made about the influence of two-body collisions on the dissipation process in fusion reactions at energies around the Coulomb barrier.

![](images/bb13810eb12e8445d1e4de289f581db5b31ee8374153d7f3aa6dc2b8d5f83451.jpg)  
FIG.10.(Color online） The basic processes of nucleon exchange between two fusing nuclei.

# Appendix A:Derivation of $T _ { \mathrm { d i s s } } ( R )$

Let us discuss the nucleon exchange process between two nuclei with mass $M = A m$ where $m$ denotes the nucleon mass and $A$ the number of nucleons in the nucleus. Since we are interested in head-on symmetric heavy-ion collisions,we focus on the one-dimensional case depicted in Fig. 1O in which only the right part of the system is shown.

At certain time $t _ { 0 }$ ,the right part with mass $m A$ is as

$$
\cdot \stackrel { \mathrm { m a } } { \longrightarrow } \Bigg \{ \begin{array} { l l } { \underbrace { ^ { \mathrm { p _ { r o c e s s \ A } } } } _ { \mathrm { P _ { l } = \mathrm { e v _ { 0 } } } } ^ { \mathrm { m a x } } } & { \stackrel { \mathrm { \sharp } } { \longrightarrow } \Bigg ( \stackrel { \mathrm { f o r } } { \longrightarrow } \Bigg ) ^ { \mathrm { m ( A + 1 ) } } } \\ & { \qquad \quad \stackrel { \mathrm { p _ { l } = \mathrm { P _ { 0 } - \mathrm { p _ { l } } } } } { \longrightarrow } \Bigg \{ } _ { \mathrm { P _ { l } = \mathrm { e v _ { 0 } } } } ^ { \mathrm { P _ { l } = \mathrm { e v _ { 0 } } } }  \end{array}
$$

sumed to move toward the left part with the momentum Po,andtheieticeP/A Iio reaction, there occur many nucleon transfers between two nuclei which are characterized by two basic processes depicted in Fig. 10.The one denoted as Process A is to get an additional nucleon with a momentum $p _ { 1 }$ heading to the right,which is originally from the left part of the system. The other shown as Process B is to lose one nucleon with a momentum $p _ { 1 }$ heading to the left.After the $i$ -th nucleon transfer process,the kinetic energy of the right part denoted as $T _ { R } ^ { ( i ) }$ is expressed as

$$
\begin{array} { r l } & { T _ { R } ^ { ( i ) } = \cfrac { P _ { i } ^ { 2 } } { 2 m A _ { i } } , \quad P _ { i } = P _ { i - 1 } - p _ { i } , \quad A _ { i } = A _ { i - 1 } + \pi _ { i } , } \\ & { \pi _ { i } = \left\{ \begin{array} { l l } { + 1 ; \mathrm { n u c l e o n ~ f r o m ~ t h e ~ l e f t ~ i n v o l v e d } , } \\ { - 1 ; \mathrm { n u c l e o n ~ f r o m ~ t h e ~ r i g h t ~ i n v o l v e d } , } \end{array} \right. } \\ & { \quad i = 1 , 2 , \cdot \cdot \cdot , \quad A _ { 0 } = A , } \end{array} \quad ( .
$$

where $i$ counts the number of nucleon transfer processes after $t _ { 0 }$ . The difference between the kinetic energy at the initial time $t _ { 0 }$ and that after the $i$ -th nucleon transfer process is then expressed as $T _ { \mathrm { d i s s } } ( i ) = P _ { 0 } ^ { 2 } / 2 m A - P _ { i } ^ { 2 } / 2 m A _ { i }$ ： We denote the number of nucleons which have been exchanged up to a given relative distance $R$ as $N _ { \mathrm { e x } } ( R )$ Then one-half of the total dissipation energy of the collective motion at $R$ is expressed as

$$
\begin{array} { l } { \displaystyle T _ { \mathrm { d i s s } } ( R ) = \frac { P _ { 0 } ^ { 2 } } { 2 m A } - \frac { P _ { N _ { \mathrm { e x } } ( R ) } ^ { 2 } } { 2 m A _ { N _ { \mathrm { e x } } ( R ) } } \mathrm { , } } \\ { \displaystyle P _ { N _ { \mathrm { e x } } ( R ) } = P _ { 0 } - \sum _ { i = 1 } ^ { N _ { \mathrm { e x } } ( R ) } p _ { i } \mathrm { , } } \\ { \displaystyle A _ { N _ { \mathrm { e x } } ( R ) } = A _ { 0 } + \sum _ { i = 1 } ^ { N _ { \mathrm { e x } } ( R ) } \pi _ { i } \mathrm { . } } \end{array}
$$

Here,it should be mentioned that the sum of the dissipation energy in Eq. (A2)and the amount of increased energyin the intrinsic kinetic energy of the right (left) part is easily proven to be zero. Namely, the amount of energy lost from the collective motion through the nucleon exchange is just the same amount as that is increased in the intrinsic system.

# ACKNOWLEDGMENTS

We thank Lu Guo,K. Washiyama, En-Guang Zhao, and Yi-Zhong Zhuo for helpful discussions. This work has been supported by the National Key Basic Research Program of China (Grant No.2013CB834400)，the National Natural Science Foundation of China (Grants No.11075215，No．11121403，No.11120101005，No. 11275052，No.11275248，and No.11375062)，and the

Knowledge Innovation Project of the Chinese Academy of Sciences (Grant No. KJCX2-EW-N01). F. S. appreciates the support by the Chinese Academy of Sciences (CAS) Visiting Professorship for Senior International Scientists (Grant No. 2013T1J0046). The computational results presented in this work have been obtained on the High-performance Computing Cluster of SKLTP/ITP-CAS and the ScGrid of the Supercomputing Center, Computer Network Information Center of the Chinese Academy of Sciences.

[1] S. Bjornholm and W. J. Swiatecki, Nucl. Phys.A 391, 471 (1982). [2] P. Frobrich and I. Gontchar, Phys.Rep. 292,131 (1998).   
[3] G.G.Adamian, N.V.Antonenko,W. Scheid, and V.V. Volkov, Nucl. Phys. A 633, 409 (1998). [4] C.Shen,G. Kosenko， and Y. Abe, Phys. Rev.C 66, 061602(R) (2002).   
[5] V. Zagrebaev and W. Greiner, J. Phys. G: Nucl. Phys. 34, 2265 (2007).   
[6] A. Zubov, G. Adamian， and N. Antonenko, Phys.Part. Nucl. 40, 847 (2009).   
[7] J.-Q.Li, Z.-Q.Feng, Z.-G. Gan,X.-H. Zhou,H.-F. Zhang, and W. Scheid, Nucl. Phys. A 834, 353c (2010).   
[8] Y.Aritomo,K. Hagino,K. Nishio, and S. Chiba, Phys. Rev. C 85, 044614 (2012).   
[9] K.Siwek-Wilczynska, T. Cap,M. Kowal, A. Sobiczewski, and J. Wilczynski, Phys.Rev. C 86, 014611 (2012).   
[10] A.K. Nasirov,G. Mandaglio，G.Giardina，A.Sobiczewski，and A.I. Muminov,Phys.Rev.C 84,044612 (2011).   
[11] N. Wang, E.-G. Zhao, W. Scheid, and S.-G. Zhou, Phys. Rev.C 85, 041601(R) (2012).   
[12] Z.-H. Liu and J.-D. Bao, Phys. Rev. C 87, 034616 (2013).   
[13] A.Nasirov,K.Kim,G.Mandaglio,G.Giardina,A.Muminov，and Y.Kim, Euro.Phys. J.A 49,147 (2013).   
[14]I.I.Gontchar，R.Bhattacharya， and M.V.Chushnyakova, Phys.Rev. C 89, 034601 (2014).   
[15] P.Bonche, S.Koonin，and J.W.Negele, Phys.Rev.C 13, 1226 (1976).   
[16] S. E. Koonin, Prog. Part. Nucl. Phys. 4, 283 (1980).   
17D.Brink and F. Stancu, Phys.Rev.C 24,144 (1981).   
[18] J. W. Negele, Rev. Mod. Phys. 54, 913 (1982).   
[19] A. S. Umar, M. R. Strayer, and P.G. Reinhard, Phys. Rev. Lett. 56, 2793 (1986).   
[20] L. Guo, J. A. Maruhn, and P.-G. Reinhard, Phys. Rev. C 76,014601 (2007).   
[21] L.Guo,J. A.Maruhn，P.-G.Reinhard, and Y.Hashimoto, Phys. Rev. C 77, 041301(R) (2008).   
[22] K. Washiyama and D. Lacroix, Phys. Rev.C 78, 024610 (2008).   
[23] K.Washiyama,D. Lacroix, and S. Ayik,Phys.Rev.C 79, 024609 (2009).   
[24] S. Ayik, K. Washiyama, and D. Lacroix, Phys.Rev. C 79,054606 (2009).   
[25] C. Simenel, Eur.Phys. J. A 48,152 (2012).   
[26] C. Simenel, M. Dasgupta, D. J. Hinde, and E. Williams, Phys. Rev.C 88, 064604 (2013).   
[27] G.-F. Dai, L. Guo, E.-G. Zhao, and S.-G. Zhou, Phys. Rev. C 90, 044609 (2014).   
[28] G.-F. Dai,L. Guo,E.-G. Zhao, and S.-G. Zhou, Sci. China-Phys.Mech. Astron. 57,1618 (2014).   
[29] S.-J. Wang and W. Cassing, Ann. Phys. 159,328 (1985).   
[30] J. Aichelin, Phys. Rep. 202, 233 (1991).   
[31] H. Sorge,H. Stocker，and W.Greiner, Nucl. Phys.A 498, 567 (1989).   
[32] A. Ono, Phys. Rev. C 59, 853 (1999).   
[33] H. Horiuchi, NATO ASI Series 335, 215 (1994).   
[34] H. Feldmeier and J. Schnack, Rev.Mod. Phys. 72,655 (2000).   
[35] A. S. Umar and V. E. Oberacker, Phys. Rev. C 74, 021601 (2006).   
[36] A.S. Umar and V.E. Oberacker， Phys.Rev.C 76, 014614 (2007).   
[37] M. Karplus and J.A. McCammon, Nat. Struct.Mol. Biol. 9,646 (2002)； Nat. Struct. Mol. Biol. 9, 788 (2002).   
[38] P.Carloni,U.Rothlisberger， and M. Parrinello,Acc. Chem. Res.35,455 (2002).   
[39] K. Wen, F. Sakata, Z.-X.Li, X.-Z. Wu, Y.-X. Zhang, and S.-G. Zhou, Phys. Rev. Lett. 111, 012501 (2013).   
[40] J.Maldacena,JHEP 05,013 (2003).   
[41] S.Matarrese,F.Lucchin， and S.A.Bonometto,Astrophys. J. 310, L21 (1986).   
[42] T.Akimoto,E.Yamamoto,K.Yasuoka,Y.Hirano，and M. Yasui, Phys. Rev. Lett. 107, 178103 (2011).   
[43] M.A.Laakso,T.T.Heikkila，and Y.V.Nazarov, Phys. Rev. Lett.108,067002 (2012).   
[44] M. A. Stephanov, Phys.Rev.Lett.102, 032301 (2009).   
[45] L.A. Pachon,J.F. Triana,D. Zueco，and P.Brumer, “Uncertainty principle consequences at thermal equilibrium,”arXiv:1401.1418 [quant-ph] (2014),1401.1418.   
[46] F.Sakata et al.,to be published (2014).   
[47] Y. B.Wei, Y. G. Ma, W. Q. Shen,G.L. Ma, K. Wang, X. Z. Cai, C. Zhong, W. Guo， and J. G. Chen, Phys. Lett. B 586, 225 (2004).   
[48] Q. F. Li and C. W. Shen, Sci. China Ser. G-Phys. Mech. Astron.52,1530 (2009).   
[49] C.Guo, Y. Wang,Q. Li, W. Trautmann, L. Liu， and L. Wu, Sci. China-Phys. Mech. Astron. 55, 252 (2012).   
[50] Y. Wang, C.Guo, Q. Li, and H. Zhang, Sci. China-Phys. Mech. Astron. 55,2407 (2012).   
[51] Z.-Q. Feng, G.-M. Jin, and F.-S. Zhang, Nucl. Phys. A 802,91 (2008).   
[52] S. Kumar and Y. G. Ma, Phys. Rev. C 86,051601(R) (2012).   
[53] L. Zhu, J. Su, W.-J. Xie, and F.-S. Zhang, Nucl. Phys. A 915, 90 (2013).   
[54] Z.-Q. Feng, Nucl. Phys. A 919, 32 (2013).   
[55] N. Wang, Z. Li, and X. Wu, Phys. Rev. C 65,064608 (2002).   
[56] N. Wang, Z. Li, X.Wu, J. Tian,Y. Zhang,and M. Liu, Phys. Rev. C 69, 034608 (2004).   
[57] N. Wang,X. Wu, Z.Li, M.Liu, and W. Scheid, Phys. Rev. C 74, 044604 (2006).   
[58] K. Zhao, X. Wu， and Z. Li, Phys. Rev.C 80,054607 (2009).   
[59] X. Jiang,S. Yan， and J.A.Maruhn, Phys. Rev.C 88, 044611 (2013).   
[60] N. Wang, Z. Li, X.Wu, and E. Zhao, Mod.Phys. Lett. A 20,2619 (2005).   
[61] V.V. Sargsyan,G.G.Adamian,N.V.Antonenko,and D.Lacroix, Phys.Rev. A 90,022123 (2014).   
[62] M.Papa,T.Maruyama，and A.Bonasera, Phys.Rev.C 64,024612 (2001).   
[63] J.Tian,X.Wu,K. Zhao,Y. Zhang， and Z.Li, Phys. Rev. C 77,064603 (2008).   
[64] K. Zhao, Z. Li, X. Wu, and Z. Zhao, Phys. Rev.C 79, 024614 (2009).   
[65] C.W. Gardiner, Quantum Noise, Springer Series in Synergetics，Vol.56(Springer-Verlag，Berlin，New York, 1991).   
[66] H. Mori, Prog. Theor. Phys.33, 423 (1965).   
[67] F. Sakata, S. Yan, E.-G. Zhao, Y. Zhuo,and S.-G. Zhou, Prog. Theor.Phys.125,359 (2011).   
[68] A.S.Umar and V. E. Oberacker，Phys.Rev.C 74, 061601(R) (2006).   
[69]Y. Jiang, N.Wang,Z.Li, and W. Scheid,Phys.Rev.C 81,044602 (2010).   
[70] V.Zanganeh,N.Wang， and O.N.Ghodsi, Phys.Rev. C 85,034601 (2012).   
[71] H.Goldstein， Classical Mechanics(Addison-Wesley, Reading，1959).   
[72] S. E. Koonin and J.R. Nix, Phys. Rev. C 13, 209 (1976).   
[73]D.Boilley,H.Li, C.Shen,Y.Abe，and B.G.Giraud, Phys. Rev. C 84, 054608 (2011).   
[74]Y.-J.Liang,M. Zhu, Z.-H.Liu, and W.-Z.Wang,Eur. Phys. J. A 48, 133 (2012).   
[75] M. Zhu, J.-l. Fu, Z. Qu, Z.-h. Liu, and W.-z. Wang, Chin. Phys. Lett.30, 082401 (2013).   
[76]V.I. Zagrebaev,A.V.Karpov，and W.Greiner, Phys. Rev. C 85, 014608 (2012).   
[77]G.G.Adamian，N.V.Antonenko,R.V. Jolos,and W. Scheid, Nucl. Phys. A 619, 241 (1997).   
[78]G.G.Adamian,N.V.Antonenko,A.Diaz-Torres，and W. Scheid, Nucl.Phys. A 671, 233 (2000).   
[79]A.Diaz-Torres,G.G.Adamian,N.V.Antonenko，and W. Scheid, Phys. Lett. B 481, 228 (2000).   
[80]A.S.Umar，C.Simenel， and V.E.Oberacker,Phys. Rev. C 89, 034611 (2014).   
[81]X.Wu,J. Tian,N.Wang,K.Zhao， and Z.Li, High Ener. Phys.Nucl. Phys. 28, 1317 (2004).