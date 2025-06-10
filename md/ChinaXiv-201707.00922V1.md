# Dissipation dynamics and spin-orbit force in time-dependent Hartree-Fock theory

Gao-Feng Dai $^ 1$ ，Lu Guo $^ { 2 , 1 }$ ,\* En-Guang Zhao $^ { 1 , 3 }$ ，and Shan-Gui Zhou $^ { 1 , 3 }$ （204 （20 $^ { 1 }$ State Key Laboratory of Theoretical Physics, Institute of Theoretical Physics, Chinese Academy of Sciences，Beijing 100190，China $^ 2$ School of Physics， University of Chinese Academy of Sciences， Beijing 10o049， China and $^ 3$ Centerof Theoretical Nuclear Pysics，NationalLaboratoryfHeayIonAceeratoranzou3oCina (Dated:July 30, 2017)

We investigate the one-body dissipation dynamics in heavy-ion collisions of $^ { 1 6 }$ O $+ ^ { 1 6 }$ O using a fully three-dimensional time-dependent Hartree-Fock (TDHF） theory with the modern Skyrme energy functional and without any symmetry restrictions. The energy disspation is revealed to decrease in deep-inelastic collsions of the light systems as the bombarding energy increases owing to the competition between collective motion and single-particle degrees of freedom.The role of spin-orbit force is given particular emphasis in deep-inelastic colisions.The spin-orbit force causes a significant enhancement of the dissipation.The time-even coupling of spin-orbit force plays a dominant role at low energies,while the influence of time-odd terms is notable at high energies.About 40-65% of the total dissipation depending on the different parameter sets is predicted to arise from the spin-orbit force.The theoretical fusion cross section has a reasonably good agreement with the experimental data,considering that no free parameters are adjusted to reaction dynamics in the TDHF approach.

PACS numbers: 24.10.-i, 25.70.-z, 21.60.Jz

# I. INTRODUCTION

Time-dependent Hartree-Fock （TDHF） theory,originally proposed by Dirac [1]，has been widely applied to describe the fusion excitation functions,deepinelastic collisions, fission,collective excitation,and nuclear molecular resonances； for reviews see Refs. [2,3]. It provides,from a fully microscopic point of view,the dynamical foundation of large amplitude collective motion [4]. TDHF theory has exactly treated the onebody dissipation caused by the collisions of nucleons with mean-field potential and nucleon transfer between the colliding partners.The two-body dissipation,which was included in quantum molecular dynamics models [5-7] and is likely to play a significant role at high energies, has been neglected within the framework of mean-field dynamics.

A number of approaches based on TDHF have been developed to investigate the dissipation mechanism in heavy-ion collisions and resonance dynamics. Densityconstrained TDHF (DC-TDHF) [8] has utilized the timedependent instantaneous densities as the constraints to perform the static Hartree-Fock minimization,thus capable of extracting the excitation energy [9] and the underlying nucleus-nucleus interaction potential [8]. The method is the dynamical analog of static adiabatic approximation and has been applied to calculate the fusion cross section at both sub- and above-barrier energies [10 12]. In the dissipative dynamics TDHF (DD-TDHF) ap proach [13,14],mean-field evolution was assumed to be properly reduced to one-dimensional dissipative dynamics.By using the macroscopic reduction procedure,the one-body dissipation in the entrance channel of heavyion fusion reactions has been extracted from the simulations of microscopic TDHF [13,14]. The technique of Wigner distribution function [15,16] has been applied to probe the single-particle dissipation in TDHF from a phase-space perspective. As indicated by Loebl and collaborators,the one-body dissipation is not enough to achieve the true equilibrium as the reaction proceeds to longer contact times [15]. The tensor force has been included in recent TDHF calculations [17-19]. The timeeven contribution of the tensor force was found to have important roles in heavy-ion collisions [17, 18]. The full tensor expression was introduced to study the resonance dynamics [19].

Since TDHF theory is based on the independentparticle approximation，the expectation value of onebody observables can be well described.However, the de scription of dynamical fluctuation and two-body dissipa tion requires the theoretical development beyond TDHF. The stochastic extension of TDHF theory [20,21] has been proposed to include the dynamical fluctuations of collective variables beyond mean field in a fully microscopic framework.The Balian-Vénéroni variational principle [22,23] was first applied to realistic calculations of fragment mass and charge distributions in heavy-ion collisions by Simenel [24]. By comparing with the standard TDHF calculations,an increase of the fluctuations has been found and the agreement with experimental data has been much improved. The two-body dissipation arising from nucleon-nucleon collisions has been taken into account in a quantum mechanical way with the extended TDHF [25,26] or time-dependent density matrix (TDDM) approaches [27-29]. So far only a few studies on the dynamical fluctuation and two-body dissipation have been implemented because beyond TDHF calculations require a lot of numerical efforts and computational time.

The dissipation dynamics has an influence on the behavior of nucleus-nucleus collision. The energy dissipation,closely associated with the interplay between the collective motion and the single-particle motion,depends on the delicate balance between reaction time and rearrangement time of the mean field.When the collective motion is slow enough so that the mean field has enough time to rearrange itself, the reaction dynamics follows the adiabatic motion.For example,the experimentally observed Landau-Zener effect [30,31] in inelastic cross section is due to the breakdown of adiabatic condition. The Landau-Zener effect and its applications to heavyion collisions were,for the first time,investigated with TDHF theory by constructing the boost-invariant adiabatic single-particle states [32].

Earlier TDHF calculations systematically underestimated the dissipation of energy from the relative collective motion into internal degrees of freedom due to the simplified effective interaction and symmetry restrictions [33-36]. For example, there has been the puzzle of the fusion window anomaly,which was later solved by including the time-even terms of spin-orbit force in TDHF calculations [37]. The fusion excitation function was enhanced by as much as $2 0 \%$ for the $^ { 4 0 } \mathrm { C a } + ^ { 4 0 }$ Ca system by removing the isospin symmetry restriction on the nuclear wave functions [33]. In Ref. [38] it was demonstrated that,despite using various approximations, the time-even spin-orbit force has a significant effect on the dissipation dynamics in heavy-ion scattering.However，the timeeven spin-orbit interaction and the three-dimensional geometry have not been incorporated simultaneously in these earlier TDHF calculations,and also the time-odd terms of spin-orbit force have been neglected.The frst three-dimensional TDHF calculations including the full spin-orbit interaction [39,40] have been performed using the TDHF3D code.The role of spin-orbit interaction on single-particle states inheavy-ion collisionswasdiscussed in Ref. [41]. The time-odd terms of spin-orbit force was addressed to be the origin of the spin excitation mechanism [42].

With the development of computer ability,a fully three-dimensional TDHF calculation with modern energy functional and without any symmetry restrictions has been realized in recent years.It is expected to provide a better description of heavy-ion collisions [43-50] and resonance dynamics [51-56]. The purpose of present article is to systematically investigate the dissipation dynamics in deep-inelastic collisions and the role of spinorbit force by using modern TDHF calculations.The article is organized as follows. In Sec.II, we briefly explain TDHF theory and the details in numerical calculations. In Sec.II,we illustrate the dissipation dynamics and the role of time-even and time-odd terms of spin-orbit force.The fusion cross section obtained from modern TDHF calculations is compared with experimental data. A summary is given in Sec. IV.

# II. THE TIME-DEPENDENTHARTREE-FOCKAPPROACH

Most TDHF calculations employ Skyrme effective interaction [57]. The Skyrme energy functional provides a good description of nuclear ground state properties and collective excitations. Various parametrizations of Skyrme effective interaction have been fitted with a different emphasis on nuclear structure properties. There are no free parameters adjusted on the reaction dynamics. In order to see the parameter dependence,three Skyrme parametrizations of SLy4 [58], SkM $^ *$ [59]，and UNEDF1 [60] have been implemented to study the dissipation dynamics in heavy-ion collisions in this work.We will not show the calculations with other parametrizations since they do not produce a significant difference for the purpose of the present work.

The time evolution of self-consistent mean-field generated byall the particles is described by the TDHF equation

$$
i \hbar \partial _ { t } \psi _ { \alpha } = h ( \rho , \tau , \vec { \sigma } , \vec { j } , \vec { J } ) \psi _ { \alpha } ,
$$

where the time-dependent single-particle Hamiltonian $h$ consists of density $\rho$ ，kinetic density $\tau$ ，spin density $\vec { \sigma }$ ， current $\vec { j }$ ，and spin-orbit density $\bar { J }$ [61]. The main approximation of TDHF theory is to treat the many-body wave function as an independent particle state at any time.Starting from a proper initial state obtained from the static HF equation,the TDHF equation is solved to determine the wave functions at each time of dynamical evolution.The mean-field Hamiltonian $h$ is derived from the energy density functional (EDF)

$$
E = \int d ^ { 3 } r { \mathcal { H } } ( \rho , \tau , { \vec { \sigma } } , { \vec { j } } , { \vec { J } } ) ,
$$

by using the time-dependent variation

$$
h _ { i j } = \frac { \partial E } { \partial \rho _ { j i } } .
$$

The energy functional $\mathcal { H }$ consists of free kinetic energy, Skyrme interaction,and Coulomb energy with exchange in the Slater approximation. Note that the TDHF approach treats the static properties and reaction dynamics in a unified theoretical framework and the same energy functional.

For the sake of later discussions,the time-even and time-odd terms of spin-orbit force

$$
{ \mathcal { H } } _ { \mathrm { l s } } ^ { \mathrm { e v e n } } = - { \frac { 1 } { 2 } } t _ { 4 } \left( \rho \nabla \cdot { \vec { J } } + \sum _ { q } \rho _ { q } \nabla \cdot { \vec { J } } _ { q } \right) ,
$$

$$
\mathcal { H } _ { \mathrm { l s } } ^ { \mathrm { o d d } } = - \frac { 1 } { 2 } t _ { 4 } \left( \vec { s } \cdot \nabla \times \vec { j } + \sum _ { q } \vec { s } _ { q } \cdot \nabla \times \vec { j } _ { q } \right) ,
$$

are expressed in terms of various densities and Skyrme parameter $t _ { 4 }$ ．The index $q$ denotes protons and neutrons. The inclusion of both time-even and time-odd terms guarantees the Galilean invariance which should be met in a meaningful theory of heavy-ion collisions [61]. The odd-odd terms of spin-orbit force are important to assure the energy conservation in the free translation of a nucleus over the grids as reported in Ref. [42].

The set of nonlinear TDHF equations is solved on a three-dimensional Cartesian coordinate-space without any symmetry restrictions.The derivative is solved with fast Fourier transformation in Fourier representation. The numerical box of coordinate space is 32×24×24 fm3 for the present calculations of the light system $^ { 1 6 } \mathrm { O } + { } ^ { 1 6 } \mathrm { O }$ The colliding nuclei locate at an initial center of mass distance of 16 fm.Before reaching this distance,the colliding nuclei follow the Rutherford trajectory. The grid spacing is taken as 1 fm and a time step of dynamical evolution as O.2 fm/c. The dynamical unitary propagator is expanded up to the sixth order of Taylor expansion. The choice of these parameters guarantees good numerical accuracy during the dynamical evolution for all the cases studied here.The shift of particle number and total energy is less than，respectively, O.O1 and O.1 MeV during the time evolution.

Fusion occurs when the collective kinetic energy is entirely converted into the internal excitation of a welldefined compound nucleus. TDHF fusion cross section is calculated at each energy by the sharp-cutoff approximation [62]

$$
\sigma _ { \mathrm { f u s } } = \frac { \pi \hbar ^ { 2 } } { 2 \mu E _ { \mathrm { c . m . } } } [ ( l _ { \mathrm { m a x } } + 1 ) ^ { 2 } - ( l _ { \mathrm { m i n } } + 1 ) ^ { 2 } ] ,
$$

where $\mu$ is the reduced mass of the system and $E _ { \mathrm { c . m } }$ is the initial center-of-mass energy. The quantities ${ l } _ { \mathrm { m a x } }$ and $l _ { \mathrm { m i n } }$ denote the maximum and minimum orbital angular momentum for which fusion happens. At low collision energy, the minimum orbital angular momentum is zero. As the increase of incident energy, there usually appears the nonzero lower limit of orbital angular momentum due to the transparency behavior in central collisions [36, 63, 64].

# III. RESULTS AND DISCUSSIONS

We have performed fully three-dimensional TDHF calculations using Sky3D code [65] for heavy-ion collisions of $^ { 1 6 }$ O ${ 1 + ^ { 1 6 } }$ O with modern Skyrme EDF and without any symmetry restrictions.This system has been studied with TDHF by several groups on fusion，deep-inelastic collision, the associated dissipation mechanisms,and the extensive comparison with experimental data [8,9,12, 13,15,18,29,32,36-38,42-44,46,62]. The present studies will be compared with the earlier calculations and the available experimental data in order to clarify the impact of new terms in Skyrme EDF and the geometric symmetries on the reaction dynamics.

![](images/228b3173c68d1495a384bc7c7b53bcc8f17e570579da3d661da5193fa8f8a5a1.jpg)  
FIG.1.(Color online）Final relative kinetic energy asa function of center-of-mass energy for head-on collisions of 16O+16O. The solid lines show the results of present studies using three Skyrme parametrizations,and the dashed lines are taken from Ref.[38] for comparison.

One of the most interesting experimental observables in heavy-ion scattering is the relative kinetic energy of the separating ions.Figure 1 shows the final relative kinetic energy as a function of initial center-of-mass (c.m.) energy for head-on collisions of $^ { 1 6 }$ O $+ ^ { 1 6 }$ O.The solid lines with different symbols denote the present studies using three Skyrme parametrizations SLy4，SkM $^ *$ ，and UNEDF1. For comparison the dashed lines from earlier TDHF calculations [38] are also displayed. The difference between present studies and earlier calculations mainly lies in three points. First, the axial symmetry was assumed in earlier calculations,while the present study does not impose any symmetry restrictions.Second,we include the full spin-orbit ( ${ \mathrm { l } } ^ { * } { \mathrm { , } }$ s） force,and yet only time even terms of l\*s force were incorporated in earlier studies.Third, the terms involving the gradient of density in Skyrme EDF were replaced with the finite-range Yukawafolding form in earlier studies to simplify the numerical calculations,compared with the full treatment in present studies.

The heavy-ion scattering behavior studied here is for energies from the threshold of inelastic scattering to an initial c.m.energy of 2Oo MeV.It should be noted that TDHF dynamics can only be used to discuss the onebody dissipative mechanism. In the energy range of the present study, the two-body collision terms are likely to playa significant role.However,as presented in the Introduction,beyond TDHF calculations still remain a numerical difficulty. We then present this work as a study of one-body dissipation dynamics.

As seen in Fig.1, the overall trend of solid lines is sim ilar for the three parametrizations,and yet there gradually appears a distinct discrepancy as the increase of c.m.

![](images/fe058819ea110d8483a77f50507ba666a75c1e1b3a9877b22c83e9d9724acb52.jpg)  
FIG.2.(Color online） Percentage of energy dissipation as a function of center-of-mass energy for head-on collisions of （204号 $^ { 1 6 } \mathrm { O } + ^ { 1 6 } \mathrm { O }$ with parametrization SLy4. The black, red, and blue lines represent the TDHF calculations involving full $\mathrm { l ^ { * } s }$ time-even $\mathrm { l ^ { * } s }$ ,and no l\*s force.

energy. In the energy range studied here,the outgoing ions carry the largest kinetic energies using SLy4,and the smallest with the newly fitted parametrization UNEDF1. We may therefore expect that the energy dissipation will be the most distinguished with UNEDF1,and the weakest using SLy4 among the three parametrizations. The dashed lines from the earlier studies are shifted notably depending on the Skyrme parametrizations.By comparing the results of the present and earlier studies, the sensitivity of earlier calculations on Skyrme parametrizations is attributed to the approximations stated above on the effective interaction and geometric symmetry. It should be noted that the final energy has an uncertainty of 2-3 MeVbecause the nucleons emitted from the highly excited fragments are reflected from the boundaries of the numerical box,as seen in deep-inelastic collisions [44] and giant resonance calculations [66]. This will not cause an essential distinction for the purpose of present studies. In the following,the results with SLy4 will be taken as an example for further discussions.

In order to understand the systematic variation of energy dissipation as the increase of incident energy, we define a quantity which measures the extent of energy dissipation in deep-inelastic collisions as $P _ { \mathrm { d i s } } = 1 { - } E _ { \mathrm { f i n } } / E _ { \mathrm { c . m . } }$ ， where $E _ { \mathrm { f i n } }$ and $E _ { \mathrm { c . m } }$ . denote,respectively, the final and initial kinetic energy already shown in Fig.1. The percentage of energy dissipation as a function of incident energy is plotted in Fig.2 for head-on collisions of $^ { 1 6 }$ O+160 with parametrization SLy4. The black,red,and blue lines represent the TDHF calculations involving full 1\*s, time-even l\*s,and no $1 ^ { * }$ s force in Skyrme EDF.As can be seen, the inclusion ofl\*s force results in a significant enhancement of energy dissipation in deep-inelastic collisions. For all three cases the percentage of energy dissipation decreases as the incident energy increases. To clarify the dissipation mechanism,Fig.3 displays the density distribution of separating ions at the same relative distance of 8.3 fm for three incident energies of 90,130,and 170 MeV in the upper,middle,and bottom panels. The three energies locate around the start,middle,and end point of the black line shown in Fig.2.As the increase of incident energy the nucleon density around the neck region becomes lower and at c.m.energy of 170 MeV the nuclei are essentially spherical without a neck formation, indicating that fewer nucleons have been transferred between the colliding partners.The dynamical mechanism in the exit channel of heavy-ion scattering visualized in Fig.3 may be interpreted by the concept of dissipative diabatic dynamics which was introduced in the 1980s[67] and later applied in the fusion of heavy nuclei [68]. As the increase of incident energy, the collective motion is so fast that the mean-field does not have enough time to rearrange itself and has to keep its identity as much as possible.This energy dependence of density evolution has also been presented in the entrance channel of fusion reactions at lower energies for the same and heavier systems [13, 14, 50].

![](images/3a20b9e88858e5b8bcff1221266ccce5773f8b0f07bbe055a2e69e9b289598e3.jpg)  
FIG.3.(Color online）Density profile of the separating ions at the same relative distance $R = 8 . 3$ fm for three incident energies $E _ { \mathrm { c . m . } } = 9 0 \$ MeV (top),130 MeV (middle),and 170 MeV(bottom) for the head-on collisions of $^ { 1 6 }$ O+ $\boldsymbol { \mathbf { \ell } } _ { - } { } ^ { 1 6 }$ O with the full $\mathrm { l ^ { * } s }$ force.

The percentage of energy dissipation arising solely from the time-even and time-odd contributions of l\*s force are shown in Fig. 4. The energy dissipation caused by the time-odd l\*s force is equal to the percentage of energy dissipation with TDHF calculations involving full 1\*s force minus that with time-even l\*s,which can be extracted from the black and red lines in Fig.2.The dissipation from the time-even contribution is the difference between $P _ { \mathrm { d i s } }$ with even l\*s and without l\*s.As seen in Fig.4, the time-even l\*s force provides more important contributions to the dissipation than the time-odd terms when the relative c.m.energy is less than 160 MeV for the $^ { 1 6 }$ O+16O collisions. At low energies the time-even $\mathrm { l ^ { * } s }$ force plays a dominant role and the effect of time-odd $1 ^ { * }$ U becomes more pronounced at high energies.This might be the reason that earlier TDHF calculations at low collision energy [37], though the time-odd 1\*s force was neglected,can account for, to some extent,the experimental data [69]. The dissipation from the time-odd contribution increases as the incident energy,as we expected, because the current density appearing in the time-odd l\*s functional is proportional to the velocity for the case of a nucleus moving with constant velocity.

![](images/231eb4bb1e01427fbaefc046234a4e728ad062f286429093dba295ca03522ff2.jpg)  
FIG.4. (Color online) Percentage of energy dissipation caused by the time-odd and time-even contributions of l\*s force as a function of center-of-mass energy for head-on collisions of （20 $^ { 1 6 } \mathrm { O } + ^ { 1 6 } \mathrm { O }$ with parametrization SLy4.

A quantity which expresses the proportion of dissipated energy coming from $\mathrm { l ^ { * } }$ s force is defined as $P _ { \mathrm { s . o . } } =$ $1 - P _ { \mathrm { d i s } } ^ { \mathrm { ( n o \ l * s ) } } / P _ { \mathrm { d i s } } ^ { \mathrm { ( f u l l \ l * s ) } }$ ,where $P _ { \mathrm { d i s } } ^ { \mathrm { ( n o ~ l * s ) } }$ and $P _ { \mathrm { d i s } } ^ { \mathrm { ( f u l l ~ l * s ) } }$ correspond to the blue and black lines in Fig.2. The results are displayed in Fig.5 for head-on collisions of $^ { 1 6 }$ O+160 with the parametrizations SkM $^ *$ ，SLy4,and UNEDF1. The percentage of dissipated energy coming from l\*s force has similar trend for SkM $^ *$ and SLy4,but evident distinction appears for UNEDF1.As the increase of incident energy, the dissipation from l\*s force increases and then start to decrease after reaching the maximum value of $6 5 \%$ for SkM $^ *$ ，63% for SLy4,and 48% for UNEDF1. The UNEDF1 calculations predict an overall smaller dissipation arising from $1 ^ { * }$ s force and lower incident energy at the peak of dissipation due to the largest total dissipation (denominator in the definition of $P _ { \mathrm { s . o . } }$ ）as seen in Fig.1 and the smallest dissipated energy from l\*s force (numerator in $P _ { \mathrm { s . o . } }$ ).The new UNEDF1 parametrization was obtained by additional fitting to the experimental excitation energies of fission isomers in the actinides and is suitable for studies of strongly deformed nuclei [6O]. The origin of the discrepancy between UNEDF1 results and those with SkM $^ *$ and SLy4 parameter sets is still unclear.In spite of the sensitivity of force parameters,it is impressed that more than half of the total dissipation for SkM $^ *$ and SLy4, and slightly less than half for UNEDF1 are attributed to the l\*s force.

We also performed fusion calculations for the $^ { 1 6 }$ O ${ ^ { 1 + ^ { 1 6 } } }$ 0 system at a c.m. energy of 70.5 MeV.The reason for choosing this collision energy is due to the availability of experimental data at the energy range studied here.The fusion cross section using three Skyrme parametrizations at a c.m. energy of 70.5 MeV is listed in Table I, together the available experimental cross section with errors [70]. TDHF calculations with SkM $^ *$ and UNEDF1 parametrizations predict the central fusion collisions at the energy of 70.5 MeV because the high-energy fusion threshold,as shown in Fig.1,is higher than 70.5 MeV. For SLy4 calculations the central transparency predicted by early TDHF calculations [36,63,64] appears and the lower limit of angular momentum will become nonzero. Hence,in the SLy4 calculation of fusion cross section,we search both the maximum and minimum impact parameter $b _ { \mathrm { m a x } }$ and $b _ { \mathrm { m i n } }$ at which fusion happens.Here the fusion is defined as the compound system evolves long enough to offer convincing evidence that the system will not undergo separation. The fusion window for angular momentum is found to be $b _ { \mathrm { m i n } }$ =1.2 fm and $b _ { \mathrm { m a x } }$ =6.5 fm for SLy4, $b _ { \mathrm { m a x } }$ =6.5fm forSkM $^ *$ ，and 6.4 fm for UNEDF1 within a precision of O.1 fm. The fusion cross section obtained with the three parametrizations overestimates the experimental value by about $2 0 \%$ ,which is a reasonable agreement considering that no free parameters are adjusted for the reaction dynamics in TDHF calculations.The cross section for transparency at 70.5 MeV is predicted to be quite small with 45 mb for SLy4. Whether this effect is real or not would not change much the conclusion that the fusion cross section is reasonably reproduced by TDHF calculations at this energy.

The heavy-ion fusion at energies of several times the barrier height is a challenge both for theoretical and experimental studies.As shown by Simenel et al.[12],for the $^ { 1 6 }$ O ${ + ^ { 1 6 } }$ O system at $E _ { \mathrm { c . m . } } { = } 3 5$ MeV, the compound nucleus cannot achieve a complete thermal equilibration between collective motion and internal excitation after the long-time evolution and finally settles at an energy difference of about 10 MeV between the c.m. energy and the excitation energy. Due to the large remaining collective kinetic energy, the compound system is likely to undergo various breakup and fission events which are beyond the description of TDHF theory. Since these events are regarded as fusion in TDHF,a larger fusion cross section is expected at high energies in TDHF calculations. In addition,two-body collisions which are likely to play an important role at high energies have been neglected

# IV.SUMMARY

![](images/99922a966bb6e2efa35eb587a591b17529b13f84c1e4a780ed934928a4e08214.jpg)  
FIG.5.(Color online） Percentage of dissipated energy arising from $\mathrm { l ^ { * } s }$ force as a function of center-of-mass energy for headon collisions of $^ { 1 6 } \mathrm { O } + ^ { 1 6 } \mathrm { O }$ with parametrizations SkM $^ *$ ,SLy4, and UNEDF1.

TABLE I. Calculations of fusion cross section for $^ { 1 6 } \mathrm { O } + ^ { 1 6 } \mathrm { C }$ at $E _ { \mathrm { c . m . } } = 7 0 . 5$ MeV with three Skyrme parametrizations and experimental data with errors [70].   

<html><body><table><tr><td>Force</td><td>Ofus (mb)</td></tr><tr><td>SLy4</td><td>1282</td></tr><tr><td>SkM*</td><td>1287</td></tr><tr><td>UNEDF1</td><td>1327</td></tr><tr><td>Expt.</td><td>1056 ± 125</td></tr></table></body></html>

We have investigated the dissipation dynamics in heavy-ion collisions of $^ { 1 6 }$ O+16O using the modern TDHF approach. The numerical calculations have been implemented in a fully three-dimensional coordinate space with the modern Skyrme energy functional and without any symmetry restrictions. The dissipation dynamics exhibits a universal behavior by using three Skyrme parametrizations SkM $^ *$ ，SLy4，and UNEDF1. We revealed that the percentage of energy dissipation in deepinelastic collisions of the light systems decreases as the increase of incident energy due to the interplay between the collective motion and the single particle degrees of freedom. TDHF calculations with the newly fitted parametrization UNEDF1 predict the largest energy dissipation,while the smallest with SLy4 among the three parametrizations.The energy dissipation in the present studies has been compared with the results in earlier calculations.Special attention is paid to the role of timeeven and time-odd spin-orbit force.The spin-orbit force significantly enhances the energy dissipation.The timeeven coupling of spin-orbit force plays a dominant role at low energies,while the effect of time-odd terms becomes more pronounced at high energies.More than half of the total dissipation for SkM $^ *$ and SLy4,and slightly less than half for UNEDF1 are predicted to come from spinorbit force.We also performed the fusion calculations for this system.The theoretical fusion cross section obtained from the parameter-free TDHF approach agrees reasonably well with the experimental data.

in mean-field dynamics.From the experimental point of view, the fusion cross sections for the $^ { 1 6 }$ O+160 system have been measured by several groups using different experimental approaches and techniques [71-73]. The different sets of experimental data are not consistent with each other at energies of two to four times barrier height, leading to a large uncertainty on the experimental cross sections [12]. The experimental cross section at c.m.energy of 7O.5 MeV,although only one set data is available, is expected to have large variations as the cases at lower energies.Reliable experimental data at well above the barrier energy are highly desired.

The dissipation dynamics has also been investigated for medium-mass system of $^ { 4 0 }$ Ca+40Ca in order to see the systematic variations.There is no qualitative distinction compared with the light system of $^ { 1 6 } \mathrm { O } + ^ { 1 6 }$ O.Therefore, the results for heavier system will not be incorporated in thisarticle.

# V.ACKNOWLEDGMENTS

This work was supported by Natural Science Foundation of China(Grants No.11175252,No.11121403,No. 11120101005,No.11211120152,and No.11275248)，the National Key Basic Research Program of China (Grant No. 2013CB834400),the Knowledge Innovation Project of the Chinese Academy of Sciences (Grant No. KJCX2- EW-N01)，the President Fund of UCAS,the Scientific Research Foundation for the Returned Overseas Chinese Scholars,Ministry of Education of China,and the Open Project Program of State Key Laboratory of Theoretical Physics，Institute of Theoretical Physics,Chinese Academy of Sciences,China (Grant No.Y4KF041CJ1). The results described in this paper were obtained on the High-performance Computing Clusters of SKLTP/ITPCAS and the ScGrid of the Supercomputing Center, Computer Network Information Center of the Chinese Academy of Sciences.

![](images/192f32cbf22bb068495c88a43ca00df96155a4a9e72b4f10596aeddcc11dcef7.jpg)  
[1] P.A. M Dirac，Proc. Cambridge Phil. Soc. 26，376 (1930).   
[2]J.W. Negele, Rev. Mod.Phys. 54, 913 (1982).

[3] C. Simenel, Eur. Phys. J. A 48, 152 (2012). [4] P.Bonche, S. Koonin，and J.W.Negele, Phys.Rev. C 13, 1226 (1976). [5] J. Aichelin, Phys. Rep. 202, 233 (1991). [6] N. Wang, Z. Li, and X. Wu, Phys. Rev. C 65, 064608 (2002).   
[7] K. Wen, F. Sakata, Z.-X. Li, X.-Z. Wu, Y.-X. Zhang, and S.-G. Zhou, Phys. Rev. Lett.111, 012501 (2013); arXiv:1407.5912 [nucl-th]. [8] A. S. Umar and V. E. Oberacker, Phys. Rev. C 74, 021601(R) (2006). [9] A.S.Umar,V.E. Oberacker, J.A.Maruhn，and P.G. Reinhard, Phys. Rev. C 80, 041601(R) (2009).   
[10] A. S. Umar, V. E. Oberacker, J. A. Maruhn,and P.-G. Reinhard, Phys. Rev. C 81, 064607 (2010).   
[11] A. S. Umar, V. E. Oberacker， and C. J. Horowitz, Phys. Rev. C 85, 055801 (2012).   
[12] C. Simenel, R. Keser, A. S. Umar, and V. E. Oberacker, Phys. Rev. C 88, 024617 (2013).   
[13] K.Washiyama and D. Lacroix, Phys.Rev. C 78, 024610 (2008).   
[14] K. Washiyama, D. Lacroix, and S. Ayik, Phys. Rev. C 79,024609 (2009).   
[15] N.Loebl, J. A. Maruhn, and P.-G. Reinhard, Phys. Rev. C 84, 034608 (2011).   
[16] N.Loebl,A.S.Umar,J.A.Maruhn,P.-G.Reinhard, P. D. Stevenson, and V. E. Oberacker, Phys. Rev. C 86, 024608 (2012).   
[17] Y. Iwata and J. A. Maruhn, Phys. Rev. C 84, 014616 (2011).   
[18] G.-F. Dai, L. Guo,E.-G. Zhao, and S.-G. Zhou, Sci. China-Phys. Mech. Astron. 57, 1618 (2014).   
[19] S.Fracasso, E. B. Suckling， and P. D. Stevenson, Phys. Rev. C 86, 044303 (2012).   
[20] S. Ayik, K. Washiyama, and D. Lacroix, Phys. Rev. C 79, 054606 (2009).   
[21] K.Washiyama, S. Ayik, and D. Lacroix, Phys. Rev. C 80,031602 (2009).   
[22] R.Balian and M. Vénéroni, Phys. Lett.B 136,301 (1984).   
[23] J. M. A. Broomfield and P. D. Stevenson, J. Phys. G 35, 095102 (2008).   
[24] C. Simenel, Phys. Rev. Lett.106,112502 (2011).   
[25] D. Lacroix, S. Ayik， and P. Chomaz, Prog. Part. Nucl. Phys. 52,497 (2004).   
[26] M. Assié and D. Lacroix, Phys. Rev. Lett.102, 202501 (2009).   
[27] M. Tohyama, Phys. Rev. C36,187 (1987).   
[28] M. Tohyama and A. Umar， Phys.Lett. B 516,415 (2001).   
[29] M. Tohyama and A. S. Umar, Phys. Rev. C 65, 037601 (2002).   
[30] L. Landau, Phys. Z. Sow.2,46 (1932).   
[31] C. Zener, Proc. Roy. Soc.(London) A 137, 696 (1932).   
[32] L. Guo, J. A. Maruhn,and P.-G. Reinhard, Phys. Rev. C 76, 014601 (2007).   
[33] S. J. Krieger and K. T. R. Davies, Phys. Rev. C 18, 2567 (1978).   
[34]K.T.R.Davies,H.T.Feldmeier,H. Flocard,and M.S. Weiss, Phys. Rev. C 18, 2631 (1978).   
[35] K. T. R. Davies and S. E. Koonin, Phys. Rev. C 23, 2042 (1981).   
[36] J.A.Maruhn,K.T.R.Davies,and M.R. Strayer, Phys. Rev. C 31, 1289 (1985).   
[37] A.S.Umar, M.R. Strayer, and P.G.Reinhard, Phys. Rev. Lett. 56, 2793 (1986).   
[38] P.-G.Reinhard,A. S. Umar,K. T.R. Davies,M. R. Strayer, and S.-J. Lee, Phys. Rev. C 37,1026 (1988).   
[39] K.-H. Kim, T. Otsuka, and P. Bonche, J. Phys.G 23, 1267 (1997).   
[40] C.Simenel, P.Chomaz， and G. de France, Phys.Rev. Lett. 86, 2971 (2001).   
[41] Y. Iwata, N. Itagaki, J.A. Maruhn,and T. Otsuka, Int. J. Mod.Phys.E 17,1660 (2008).   
[42] J.A. Maruhn, P.-G.Reinhard,P. D. Stevenson， and M. R. Strayer, Phys. Rev. C 74, 027601 (2006).   
[43] A. S. Umar and V. E. Oberacker, Phys. Rev.C 73, 054607 (2006).   
[44] L. Guo,J.A. Maruhn，P.-G.Reinhard, and Y. Hashimoto, Phys. Rev. C 77, 041301(R) (2008).   
[45] C. Simenel, Phys. Rev. Lett. 105, 192701 (2010).   
[46] L. Guo and T. Nakatsukasa, EPJ Web Conf. 38, 09003 (2012).   
[47] C. Simenel,M. Dasgupta,D.J.Hinde,and E.Williams, Phys. Rev. C 88, 064604 (2013).   
[48]K.Sekizawa and K. Yabana, Phys. Rev. C 88, 014614 (2013).   
[49] C. Simenel and A. S. Umar, Phys. Rev. C 89,031601 (2014).   
[50] A. S.Umar, C. Simenel，and V. E. Oberacker, Phys. Rev. C 89,034611 (2014).   
[51] C.Simenel and P. Chomaz， Phys. Rev. C 68,024302 (2003).   
[52] T. Nakatsukasa and K. Yabana, Phys. Rev. C 71, 024301 (2005).   
[53] J. A. Maruhn, P. G. Reinhard, P. D. Stevenson, J. R. Stone， and M. R. Strayer, Phys. Rev.C 71，064328 (2005).   
[54] A. S. Umar and V. E. Oberacker, Phys. Rev. C 71, 034314 (2005).   
[55] P.-G. Reinhard, L. Guo, and J. Maruhn, Eur.Phys. J. A 32,19 (2007).   
[56] C.Simenel and P. Chomaz， Phys. Rev. C 80,064309 (2009).   
[57] T. H. R. Skyrme, Philos. Mag. 1, 1043 (1956).   
[58] E.Chabanat，P.Bonche，P.Haensel,J.Meyer，and R. Schaeffer, Nucl. Phys. A 635, 231 (1998)； Nucl.Phys. A 643, 441 (1998).   
[59] J.Bartel,P.Quentin,M.Brack,C.Guet，and H.-B. Hakansson, Nucl. Phys. A 386,79 (1982).   
[60] M.Kortelainen，J. McDonnell,W.Nazarewicz,P.-G. Reinhard,J. Sarich,N. Schunck,M.V.Stoitsov，and S. M.Wild, Phys. Rev. C 85, 024304 (2012).   
[61] Y.Engel,D.Brink,K.Goeke,S.Krieger，and D.Vautherin, Nucl. Phys. A 249,215 (1975).   
[62] P. Bonche, B. Grammaticos, and S. Koonin, Phys. Rev. C 17, 1700 (1978).   
[63]K.T.R.Davies,K.R. S.Devi,and M.R. Strayer,Phys. Rev. Lett. 44, 23 (1980).   
[64] S. K. R. Devi, M. R. Strayer, J. M. Irvine, and K. T.R. Davies, Phys.Rev. C 23, 1064 (1981).   
[65] J. Maruhn,P.-G. Reinhard,P. Stevenson, and A. Umar, Comput. Phys. Commun.185, 2195 (2014).   
[66] P.-G. Reinhard,P.D. Stevenson，D.Almehed,J.A. Maruhn， and M. R. Strayer, Phys. Rev. E 73,036709 (2006).   
[67] W. Norenberg, Phy. Lett.B 104,107 (1981).   
[68]A．Diaz-Torres，G.Adamian，N.Antonenko, and W. Scheid, Phys. Lett. B 481, 228 (2000).   
[69] A.Lazzarini，H.Doubre，K.T.Lesko，V.Metag, A.Seamster,R.Vandenbosch，and W.Merryfield,Phys. Rev. C 24, 309 (1981).   
[70] F.Saint-Laurent，M.Conjeaud,S.Harar,J.Loiseaux, J. Menet， and J. Viano, Nucl. Phys. A 327, 517 (1979).   
[71]I.Tserruya,Y.Eisen,D.Pelte,A.Gavron,H.Oeschler, D.Berndt， and H. L. Harney, Phys.Rev.C 18，1688 (1978).   
[72]B.Fernandez,C.Gaarde,J.Larsen,S.Pontoppidan,and F. Videbaek, Nucl. Phys. A 306, 259 (1978).   
[73]J.J.Kolata,R.M.Freeman,F.Haas,B.Heusch，and A. Gallmann, Phys.Rev. C 19, 2237 (1979).