# Thermal rectification in coupled rotor lattices with gradient mass

M. An,1 J. N. Zhou,1 F. G. Li,1 and J. W. Xiong1 （204号 $^ { 1 }$ School of Physics and Telecommunication Engineering, South China Normal University， 510oo6 Guangzhou, China

Abstract

Heat conduction through one-dimensional (1D） coupled rotator lattces is investigated in the presence of mass gradient. It is found that thermal current in the direction of mass increasing is not asymmetric with heat flux though mass decreasing system, which is called thermal rectification. Moreover,we find that the larger is the mass gradient,the more evident is the thermal rectification effect,which is consistent with FPU lattce with mass gradient. Based on the influences of the thermal rectification on shape parameters $K$ and $A$ of nearest-neighbor interactions, the average temperature of atomic chain and the system size,a optimum thermal rectifier is designed,which thermal rectification eficiency has reached 70. These investigations would contribute to controlling and manipulating thermal current.

PACS numbers:05.40.Fb,02.50.Ey,05.40.-a

# I. INTRODUCTION

Heat conduction is an ancient physical question, which was described by Fourier Law as （204号 $J = \kappa \Delta T$ where $\kappa$ is a constant, independent of system size. However, in recent years plenty of investigations have suggested that heat conduction in low dimensional systems diverges as the system size, for example FPU- $\alpha$ ,FPU- $\beta$ , diatomic Toda and so on[1]. These discoveries have attracted massive attention on heat conduction in low dimensional systems. Especially, the proposal[2] of processing information by controlling and manipulating phonons(heat carrier） has motivated people to have designed various thermal devices, similar to electronic counterparts, thermal transistors[3], thermal logic gates[4], thermal memory[5] and thermal limiters[6]. To our delighted, the solid state thermal rectifier from carbon nanotubes(CNTS) with nonuniform axial mass distribution has been realized experimentally[7].

There exists various studies of designing various thermal rectifiers and negative differential thermal resistance [8-25]. Li and his-coworker firstly presented the model[8] consisting of three segment FK chain of different interaction parameters to control the strength of the substrate potential. Later on, another models[9,10] coupled two nonlinear one dimensional lattices increase the thermal rectification magnitude greatly. These investigations have been explained by mismatch/match of frequency spectrum at the two ends of the chain. Yang and his-coworker[19] theoretically showed thermal rectification in graded mass of FPU- $\beta$ lattices, and found that the larger is the mass gradient, the more obvious is the thermal rectification effect. Subsequently, Shah[20] studied the FPU- $\beta$ lattices with exponential mass graded lattices，and showed that the exponential mass graded material is a better and genuine choice for thermal rectification. Hu[21] explored the thermal rectifiacion in one dimensional mass-graded harmonic lattice with harmonic and anharmonic on-site potential. It was found that thermal rectification occurs in the model with the anharmonic on-site potential and vanishes with the harmonic one,which suggests nonlinearity is necessary for thermal rectification. On the other hand, extensive investigations have done to determine the mechanisms that lead to thermal rectification in graded mass systems. Nan and Wang found that thermal rectification results from the transmission of high-frequency phonons by applying the nonequilibrium Green's function method[24]. Emmanuel have showed the graded anharmonic systems as genuine thermal rectifier by applying self-consistent reservoirs[22]. Zhong and co-workers [25] found that graphene nanoribbons with thickness-asymmetry have a good thermal rectification and the thermal rectification factor depends on temperature as well as the thickness-ratio of the two-segment.

In this paper, we investigate one-dimensional (1D） graded mass lattices with nonlinear nearest-neighbor interactions,and discover thermal rectification. In order to amplify the thermal rectification effect, the dependence of thermal rectification on the mass gradient, the shape parameter $A$ and $K$ , the average temperature $T _ { 0 }$ and the system size have been investigated.

# II. MODEL AND METHODS

The Hamilton of one-dimensional (1D) chain under consideration is of the form [1, 2]

$$
H = \sum _ { i = 1 } ^ { N } \frac { P _ { i } ^ { 2 } } { 2 M _ { i } } + V ( x _ { i + 1 } - x _ { i } ) + U ( x _ { i } ) ,
$$

where $x _ { i }$ is the instantaneous displacement of the ith particle from its equilibrium position, $P _ { i }$ denotes the ith particle's instantaneous momentum, $M _ { i }$ is the $i t h$ mass of the particle. $V ( x _ { i + 1 } - x _ { i } )$ is the nearest-neighbor interaction potential, $U ( x _ { i } )$ is the on-site potential. $N$ is the total number of particles in the chain. In the coupled rotator model $V$ takes an anharmonic form [1, 2]

$$
V = K ( 1 - \cos A ( x _ { i } - x _ { i - 1 } ) ) , U ( x _ { i } ) = 0 .
$$

For linear mass gradient, the mass of the ith particle is given by $M _ { i } = M _ { m a x } - ( i - 1 ) ( M _ { m a x } -$ （20 $M _ { m i n } ) / ( N - 1 )$ ，where $M _ { m a x }$ is the mass of the particle at left end (first particle) and $M _ { m i n }$ （204 is the mass of the particle at right end (last particle) of the chain. In our simulation, Langevin heat baths[1] were imposed on the two ends and the fixed-boundary conditions $x _ { 0 } = x _ { N + 1 } = 0$ were adopted. Therefore the equations of motion are:

$$
M _ { i } \ddot { x } _ { i } = - \frac { \partial H } { \partial x _ { i } } - \gamma _ { i } \dot { x } _ { i } + \eta _ { i } ,
$$

where $\gamma _ { i } = \gamma ( \delta _ { i , 1 } + \delta _ { i , N } )$ and $\eta _ { i } = \eta _ { H } \delta _ { i , 1 } + \eta _ { L } \delta _ { i , N }$ . The equations of motion for the central particles ( $\mathbf { \zeta } i = 2 , 3 . . . , N - 1 )$ are,

$$
M _ { i } \ddot { x } _ { i } = K A [ \sin A ( x _ { i + 1 } - x _ { i } ) - \sin A ( x _ { i } - x _ { i - 1 } ) ] ,
$$

the equations of motion for $i = 1$ and $i = N$ particles are given by,

$$
\begin{array} { c } { { M _ { 1 } \ddot { x } _ { 1 } = K A [ \sin A ( x _ { 2 } - x _ { 1 } ) - \sin A ( x _ { 1 } - x _ { 0 } ) ] - \gamma \dot { x } _ { 1 } } } \\ { { { } } } \\ { { + \eta _ { H } ( t ) , } } \end{array}
$$

$$
\begin{array} { c } { { M _ { N } \ddot { x } _ { N } = K A [ \sin A ( x _ { N + 1 } - x _ { N } ) - \sin A ( x _ { N } - x _ { N - 1 } ) ] } } \\ { { { } } } \\ { { - \gamma \dot { x } _ { N } + \eta _ { L } ( t ) , } } \end{array}
$$

where $\gamma$ is the friction coefficient. The dot stands for the derivation with respect to time $t$ The noise terms $\eta _ { \pm } ( t )$ denote a Gaussian white noise that satisfies the fluctuation dissipation relations

$$
\begin{array} { r l r } & { } & { \langle \eta _ { H } ( t ) \eta _ { H } ( t ^ { ' } ) \rangle = 2 \gamma k _ { B } T _ { H } \delta ( t - t ^ { ' } ) , } \\ & { } & { \langle \eta _ { L } ( t ) \eta _ { L } ( t ^ { ' } ) \rangle = 2 \gamma k _ { B } T _ { L } \delta ( t - t ^ { ' } ) , } \end{array}
$$

$k _ { B }$ denotes Boltzmann's constant and we set $k _ { B }$ =1 and $\gamma = 1$ in our simulations.

In this paper,we set $T _ { H } = T _ { 0 } ( 1 + \Delta T )$ and $T _ { L } = T _ { 0 } ( 1 - \Delta T )$ ，where $T _ { 0 } = ( T _ { H } + T _ { L } ) / 2$ is the average temperature and $\Delta T = T _ { H } - T _ { L }$ is the temperature bias of the two ends of particle chain. We set $J _ { L }$ as the thermal current in the direction of mass decreasing when the high temperature bath (on the left） was imposed on $M _ { m a x }$ (the maximum particle mass), and $J _ { R }$ as the heat flux in the direction of mass increasing when the high temperature bath (on the right) was coupled with $M _ { m i n }$ (the minimum particle mass).

For simplicity, the local heat flux is defined as $j _ { i } = \langle \dot { x } _ { i } F ( x _ { i } - x _ { i - 1 } ) \rangle$ ，where F=- $\partial V / \partial x$ and the notation $\langle . . . \rangle$ denotes a steady-state average. After the system reaches a stationary state, $j _ { i }$ is independent of site position $i$ ， so that the local flux can be denoted as $j$ and the total heat flux $J = N j$ . In our simulations, the equations of motion(4-6) are integrated by using a second-order stochastic Runge-Kutta algorithm[26] with a small time step (h=0.002). The simulations are performed long enough to allow the system to reach a nonequilibrium steady state in which the local heat flux is a constant along the chain.

# III. NUMERICAL RESULTS AND DISCUSSION

Figure 1 presents the dependence of the heat fluxes $( J _ { R } , J _ { L } )$ ( $J _ { L }$ denotes the thermal current from left to right and $J _ { R }$ is the heat flux from right to left） on the temperature gradient $\Delta T$ . It is observed that the heat fluxes increase as the temperature difference $\Delta T$ （204号

![](images/6555a46f7435be339db5abb4aa59ca327af60d73f4a698484fc51085b9ec8c1b.jpg)

FIG.1: The heat flux $J$ as a function of the temperature gradient $\Delta T$ .The parameters are（204号 $T _ { 0 } = 0 . 5$ ， $A = 1 . 0$ ， $K = 1 . 0$ ， $M _ { m a x } = 1 0 . 0$ ， $M _ { m i n } = 1 . 0$ ， $N = 3 2$ ：

![](images/0127cdbaca33c0bb2bff2c379abe6eba1b76c4b2996213bcd171ec6aa4e8ede2.jpg)  
FIG. 2: (a)The heat fluxes $( J _ { R } , J _ { L } )$ as a function of the mass gradient $\Delta M$ . （b） The dependence of the heat rectification efficiency $R = \mid J _ { R } / J _ { L } \mid$ on the mass gradient $\Delta M$ . The parameters are （20 $T _ { 0 } = 0 . 5$ ， $A = 1 . 0$ ， $K = 1 . 0$ ， $M _ { m i n } = 1 . 0$ ， $N = 3 2$ ：

increases. However, compared on $J _ { L }$ , the amplitude of $J _ { R }$ is much larger,which is called thermal rectification depicting thermal currents are not asymmetry when the heat baths are reversed.

Figure $2 ( \mathrm { a } )$ shows the dependence of the heat fluxes J on the mass gradient $\Delta M =$ （204号 $M _ { m a x } / M _ { m i n }$ at $M _ { m i n } ~ = ~ 1 . 0$ for $T _ { H } ~ = ~ 0 . 5$ and $T _ { L } ~ = ~ 0 . 1$ .If the mass gradient $\Delta M$ is increased,heat currents $( J _ { R } , J _ { L } )$ through systems decrease monotonically. Obviously, the heat flux fows more easily in the direction of mass increasing for any values of mass gradient. It might be assumed: the uniform distribution of atomic masses and the nonlinear nearestneighbor interaction lead to the mismatch of power spectrum at the two ends of atomic chain. Therefore there exists asymmetric thermal currents. In order to describe quantitatively the thermal rectification efficiency, we introduce the ratio $R = \mid J _ { R } / J _ { L } \mid$ ，when $R = 1$ shows no thermal rectification effect,and the larger is the value of $R = \mid J _ { R } / J _ { L } \mid$ , the better is thermal rectification effect.

![](images/280b8f368807a5a70476e656dcd8f30e4ea6b31e636b9794c387710066891357.jpg)  
FIG.3: (a) The heat fluxes $( J _ { R } , J _ { L } )$ as a function of the shape parameter $A$ of the nearestneighbor interaction. (b） the dependence of the heat rectification efficiency $R = \mid J _ { R } / J _ { L } \mid$ on the shape parameter $A$ . The parameters are $T _ { L } = 0 . 1$ ， $T _ { H } = 0 . 5$ ， $K = 1 . 0$ ， $M _ { m a x } = 1 0 . 0$ ， $M _ { m i n } = 1 . 0$ （204号 $N = 3 2$ ：

Figure 2(b) shows the dependence of the rectification efficiency $R$ on the mass gradient （20 $\Delta M$ . As the mass gradient $\Delta M$ becomes larger， the thermal rectification efficiency R increases. It is found that the mass gradient $\Delta M$ contributes to thermal rectification,which is consistent with previous investigations[19-21].

Figure 3(a) depicts the dependence of the heat currents $( J _ { R } , J _ { L } )$ on the shape parameter $A$ .The heat fluxes $( J _ { R } , J _ { L } ) \mathrm { a l l }$ increases with increment of the shape parameter $A$ .It is observed easily that $J _ { L }$ and $J _ { R }$ do not increase at the same pace,which suggests the shape parameter $A$ could have effects on thermal rectification. Because the augment of the shape parameter $A$ gives rise to a larger nonlinearity of the nearest-neighbor interaction. It improves the probability of the umklapp processes,which increases the degree of the mismatch of power spectrum of the two ends of atomic chain. Based on Figure 3(b), the more evident is the thermal rectification effect，the larger is the shape parameter $A$ of

![](images/2a5f3b515e75383db767a2be8c557f7b08eaaf013c24f38514b540f42dcc1806.jpg)

FIG. 4: (a)The heat fluxes $( J _ { R } , J _ { L } )$ as a function of the strength $K$ of the nearest-neighbor interaction.(b) the dependence of the thermal rectification efficiency $R = \mid J _ { R } / J _ { L } \mid$ on the strength $K$ of the nearest-neighbor interaction. The parameters are $T _ { L } = 0 . 1$ ， $T _ { H } = 0 . 5$ ， $A = 1 . 0$ ， $M _ { m a x } = 1 0 . 0$ （204号 $M _ { m i n } = 1 . 0$ ， $N = 3 2$ ：

nearest-neighbor interactions.

Figure $4 ( \mathrm { a } )$ shows the dependence of the heat fluxes $J _ { L }$ and $J _ { R }$ on the strength $K$ of the nearest-neighbor interaction at $T _ { H } = 0 . 5$ and $T _ { L } = 0 . 1$ ： $J _ { L }$ that is the heat flux in the direction of decreasing mass increases for $K = [ 0 . 1 , 1 . 0 ]$ , and barely changes with increasing the strength $K$ of the nearest-neighbor interaction. More interestingly， $J _ { R }$ that is the average thermal current in the direction of increasing mass decreases with the increment of the strength $K$ of the nearest-neighbor interaction (further investigations see Fig. 5). Figure 4(b) describes that the thermal rectification ratio $R$ as a function of the strength （204 $K$ of the nearest-neighbor interaction. It is found that the thermal rectification effect performs better at the minimum and maximum limit of the strength $K$ of nearest-neighbor interactions.

Figure 5(a) depicts the dependence of the thermal currents $( J _ { R } , J _ { L } )$ on the average temperature $\boldsymbol { { \mathit { I } } } _ { 0 } ^ { \prime }$ of chain. For a larger $\boldsymbol { { \mathit { I } } } _ { 0 } ^ { \prime }$ ，both $J _ { L }$ and $J _ { R }$ decrease with increasing the average temperature $T _ { 0 }$ ， which is related to nonlinear localized rotational modes of chain[27, 28]. Figure 5(b) presents thermal rectification efficiency $R$ as a function of the average temperature $T _ { 0 }$ . The rectification efficiency $R$ monotonically increases as the average temperature

![](images/e961c2949871506f4a151feed430915e6a18ba7a74b6396643cb308c7cd6acdd.jpg)

FIG. 5: (a)The heat fluxes $( J _ { R } , J _ { L } )$ as a function of the average temperature $T _ { 0 } = ( T _ { H } + T _ { L } ) / 2$ (b) the dependence of the thermal rectification $R = \mid J _ { R } / J _ { L } \mid$ on the average temperature $T _ { 0 }$ . The parameters are $\Delta T { = } 0 . 4$ ， $T _ { H } = T _ { 0 } ( 1 + \Delta T )$ ， $T _ { L } = T _ { 0 } ( 1 - \Delta T )$ ， $A = 1 . 0$ ， $K = 1 . 0$ ， $M _ { m a x } = 1 0 . 0$ （204 $M _ { m i n } = 1 . 0$ ， $N = 3 2$ ：

![](images/850ad86633e90069aef2aba74f6e7faa061180fd4e069e39a2f3e2a013480565.jpg)  
FIG.6: The heat fluxes $J$ as a function of the strength $K$ of the nearest-neighbor interaction for different values of the heaviest mass. (a) $M _ { m a x }$ =1.0, 3.0, 5.0 and 8.0. (b) $M _ { m a x }$ =10.0, 15.0, 20.0 and 40.0. The parameters are $A = 1 . 0$ ， $T _ { L } = 0 . 1$ ， $T _ { H } = 0 . 5$ ， $M _ { m i n } = 1 . 0$ ， $N = 3 2$ ：

（204号 $\mathrm { \Delta } T _ { 0 }$ increases. It might be inferred: more phonons would be generated with rising the average temperature $\boldsymbol { { \mathit { I } } } _ { 0 } ^ { \prime }$ . Large mounts of phonons of low-frequency collides and would be converted to phonons of high-frequency, which increases the weight of phonons of high-frequency and reduces the weight of phonons of low-frequency in entire phonons spectrum.

In order to investigate the effects of the mass gradient on the phenomenon that $J _ { R }$ decreases with increasing the strength $K$ of nearest-neighbor interactions, we obtained Figure $\mathrm { 6 ( a ) }$ and Figure 6(b) by nonequilibrium molecular dynamics simulations(NEMD). Figure 6 shows the dependence of $J _ { R }$ on the strength $K$ of nearest-neighbor interactions for various values of mass gradient. When the mass gradient is small (e $. g . \Delta M < 5 . 0$ ),thephenomenon that $J _ { R }$ decreases with $K$ increasing does not occur. However, in case of( $e . g . \Delta M > 5 . 0$ ), that phenomenon emerges and the maximum value of the average thermal current is gained at （204号 $K = 1 . 0$ for different mass gradients. It might be regarded as the result of the competition of the increment of thermal conductance originating from increasing $K$ [23] and the decrement of thermal conductance resulting from the existence of localized gradons modes[29] caused by mass gradient. In case of $\Delta M < 5$ , the rising thermal conductance induced by increment of $K$ dominates the system. However， for increasing $\Delta M$ ， localized gradons modes[29] is such non-ignorable that leads to the decrement of the thermal currents.

![](images/5c663832d6d9f9adfaeff4f3407512405b21d0d5c1e619e093031e0e6e17565f.jpg)  
FIG. 7: (a)The heat fluxes $( J _ { R } , J _ { L } )$ as a function of the total particles number $N$ . (b） the dependence of the thermal rectification efficiency $R$ on the system size $N$ . The parameters are $A = 1 0 . 0$ ， （204号 $K = 1 . 0$ ， $M _ { m a x } = 1 0 . 0$ ， $M _ { m i n } = 1 . 0$ ， $T _ { L } = 0 . 1$ ， $T _ { H } = 0 . 5$ ：

Figure 7(a) depicts the average thermal currents $( J _ { R } , J _ { L } )$ as a function of the system size （20 $N$ for $K = 1 . 0$ ， $A = 1 . 0$ ， $M _ { m a x } = 1 0 . 0$ ， $M _ { m i n } = 1 . 0$ ， $T _ { H } = 0 . 5$ ， $T _ { L } = 0 . 1$ . It is found that the heat fluxes $J _ { R } / J _ { L }$ all decrease if the system size increases. Obviously, the difference of amplitude of $J _ { L }$ and $J _ { R }$ gradually becomes smaller and smaller, which indicates thermal rectification effect gradually vanishes at a larger system size.

According to above investigations on how the shape parameters influence the thermal

![](images/dd9da84aff3dc67ac52230ed15bac8ef84c82ed5d66d6f3582c14267e263e35d.jpg)

FIG. 8: The heat fluxes $( J _ { R } , J _ { L } )$ as a function of $\Delta T$ with $T _ { L }$ being fixed. The parameters are $A = 1 0 . 0$ ， $K = 1 . 0$ ， $M _ { m a x } = 2 0 . 0$ ， $M _ { m i n } = 1 . 0$ ， $T _ { L } = 0 . 1$ ， $N = 3 2$ ：

rectification efficiency, the optimum parameters are selected to construct the thermal rectifier, whose rectification efficiency has reached $R = 7 0$ (see Fig. 8).

# IV. CONCLUDING REMARKS

Heat conduction in the coupled rotator model with mass gradient has been investigation. Using nonequilibrium molecular dynamic simulation, the thermal currents through graded mass coupled rotator chain largely difer when the heat baths are reversed，which shows the thermal rectification effect. As for the coupled rotator model with graded mass，it is firstly found that the heat flux $J _ { R }$ in the direction of mass increasing is much larger than the heat current $J _ { L }$ in the direction of mass decreasing,which is opposite to that of the one-dimensional (1D） FPU lattices with graded mass[19]. It might be explained by match/mismatch of the frequency spectra. By further investigation, the larger is the mass gradient $\Delta M$ ， the more evident is the thermal rectification effect，which is in accordance with the graded mass FPU- $\beta$ lattices[19, 20]. Secondly, the shape parameter $A$ and $K$ of nearest-neighbor interaction have influences on the thermal rectification. However, the phenomenon that the heat fux $J _ { R }$ decreases with $K$ increasing is surprised. The reason is that the competition of the increasing thermal conductance arisen from the increment of $K$ and localized gradons modes induced by uniform mass distribution. Thirdly, It is found that the thermal rectification efficiency becomes larger with increasing the average temperature.

Due to increment of the average temperature, the proportion of high-frequency phonons in entire phonons spectrum enhances. It leads to enhancement of the degree of mismatch of frequency spectrum at the two ends of atomic chain. Finally, based on above investigations, a relative optimum thermal rectifier has been constructed and its thermal rectification efficiency $R = \mid J _ { R } / J _ { L } \mid = 7 0$

[1] S. Lepri, R. Livi,and A. Politi, Phys,Rep.371, 1 (2003); A, Dhar, Adv. Phys. 57, 457 (2008) [2] N. Li, J. Ren, L. Wang, G. Zhang, P. Hanggi,and B. W. Li, Rev. Mod. Phys. 84,1045 (2012) [3] B. W. Li, L wang,and G. Casati, Appl. Phys. lett. 88 (2006) 143501.   
[4] L.Wang,and B.W. Li, Phys. Rev. Lett.101 (2008) 267203.   
[5] L. Wang, and B. W. Li, Phys. Rev. Lett. 99 (2007) 177208.   
[6] J. P. Wu, L. Wang, and B. W. Li, Phys. Rev. E 85 (2012) 061112.   
[7] C. W. Chang, D. Okawa, A. Majumda, and A. Zettl, science 314, 1121(2006).   
[8] M. Terraneo, M. Peyrard,and G. Casati, Phys. Rev. Lett. 88, 094302 (2002).   
[9] B. W. Li, L. Wang,and G. Casati, Phys.Rev. Lett. 93 (2004) 184301.   
[10] B. Li, J. H. Lan, and L. wang, Phys.Rev. Lett. 95,(2005) 104302.   
[11] W. Kobayashi, Y. Teraoka, and I. Tereasaki, Appl. Phys. Lett. 95,(2009) 171905.   
[12] B. Hu,and L. Yang, chaos.15,(2005) 015119.   
[13] J. Lan, and B. Li, Phys. Rev. B. 74,(2006) 214305.   
[14] J. Lan and B. Li, Phys.Rev. B. 74,(2007) 214302.   
[15] T. S. Komatsu and N. Ito, Phys. Rev. E. 81, (2010) 010103.   
[16] G. Casati, C. Mejia-Monasterio,and T. Prosen, Phys. Rev. Lett. 98,(2007) 104302.   
[17] C.R. Otey, W. T. Lau,and S.H. Fan, Phys. Rev. Lett. 104,(2010) 154301.   
[18] M. R. Bastida,and J. M. Arizmendi-Carvajal, J. Phys.A: Math. Theor. 46,(2013)115006.   
[19] N. Yang, N. Li, L. Wang, and B. Li, Phys. Rev. B 76,(2007) 020301(R) .   
[20] Tejal N. Shah and P.N. Gajjar, Phys. Lett. A. 376, (2012) 438-441.   
[21] T. Hu, K. Hu,and Y. Tang, physica. B. 405, (2010) 4407-4412.   
[22] Emmanuel Pereira,Phys.Rev.E 82 (2010) 040101.   
[23] B. Q.Ai,W. R. Zhong, B. Hu, J. Phys. Chem. C 116,13810 (2012); B.Q. Ai and B. Hu

Phys.Rev. E 83, 011131 (2011)； B. Q. Ai, W. R. Zhong, B. Hu,Phys. Rev. E 83, 052102 (2011). [24] Z. Nan, and J. S. Wang, Phys. Rev. B. 78 (2008) 024305. [25] W. R. Zhong,W. T. Huang, X. R. Dong, B. Q. Ai, Appl. Phys. Lett. 99,193104(2011); W. R. Zhong, M. P. Zhang,B.Q. Ai,D. Q. Zhen,Appl. Phys.Lett. 98, 113107 (2011). [26] R. L. Honeycutt,Phys. Rev. A 45 (1992) 600. [27] O.V. Gendelman,Phys. Rev. Lett 84(2000) 2381. [28] C. Giardina, R. Livi,A. Politi, and M. Vassalli, Phys. Rev. Lett 84 (2000) 2144. [29] J. J. Xiao,K. Yakubo, and K. W. Yu, Phys. Rev. B. 73 (2006) 054201.