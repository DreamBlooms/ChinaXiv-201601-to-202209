# Phase Transitions in a Mixture of Hard-Sphere Dipoles and Neutral Hard Spheres

LI Li, $^ *$ LI Liang-Sheng,† and CHEN Xiao-Song‡

Institute of Theoretical Physics,Chinese Academy of Sciences,P.O.Box 2735,Beijing 100190, China

(Received May 11, 2009)

AbstractUsing the reference hyperneted chain (RHNC) integral equation theory and a rigorous stability analysis method，we investigate the phase behavior of a mixture of hard-sphere dipolesand neutral hard spheres based on thecorrelations of the homogeneous isotropic phase.Lowering the temperature down to the points where the RHNC equations failto haveasolution,several fuctuationsstrongly increase.Atlowdensitiesourresults indicatetheonsetof chain formation,which is similar with the pure DHS system.At high densities,theresults indicate the appearance of isotropic-to-ferroelectric transitions (smallneutralhardspheres concentrations)anddemixing transitions (large neutral hard spheres concentrations).

PACS numbers: 64.70.-p, 02.30.Rz, 82.60.Nh, 61.20.-p Key words: integral equations,phase transition,dipolar fluids

Recently, several publications have discussed the stability of fluids whose components carry permanent dipolar moments.It has been shown that the low temperature behavior of dipolar model fluids is much more complex than previously expected. For the most simple dipolar model fluids (i.e. dipolar hard sphere fluids)，the simulation results have shown that the system can spontaneous polarize in dense liquid states $[ 1 - 3 ]$ and theoretical research has confirmed the appearance of a ferroelectric phase transition. $[ 4 - 8 ]$ On the other hand, chain formation has been pronounced by recent theoretical research in the dilute gas states, $[ 3 , 8 - 1 0 ]$ the particles associate into chains and the conventional gas-liquid coexistence (which was assumed since the orientational interaction between two particles is a van der Waals-like attraction $\lfloor 1 1 \rfloor$ ）is absent.[12] This behavior was also found by simulations.[3,9,13-15]

The phase behavior of dipolar fluid mixtures is much more complex.As a simple model,DHS-HS mixture which has been considered by integral equation,[16-18] the results shown that the system demix within the isotropic phase at sufficiently large densities and coupling strengths. This phenomenon has been proved by Monte Carlo simulation.[19] It seems that the effect of dipolar forces in mixture may be very different from that in pure fluids.Indeed,given that pure DHS fluids spontaneous polarize in dense liquid states and associated into chains with head-to-tail aligned dipoles in the dilute gas,an important question is that whether DHS-HS mixtures can exhibit the similar phase behavior under certain conditions.

To address these topics we employ reference hypernetted chain (RHNC) integral theory,which is used to calculate approximate two-particle correlation functions in the homogeneous isotropic fluid phase.Combining with a rigorous stability analysis which is on the base of diverging fluctuations,we can characterize the phase transition at the low temperatures. Previous application of this approach have shown that the phase behavior is correctly predicted and the results are consist with the computer simulations.[7,8,20] We note that the RHNC integral equation theory is reliable to predict the low temperature phase behavior of DHS fluid mixtures.

We consider a mixture of dipolar hard spheres $( d )$ with dipolar moment $\mu$ and neutral hard spheres $( n )$ ，the two species have the same diameter $\sigma$ . The pair potential between two particles with coordinates $\mathbf { \Pi } ( 1 ) \mathbf { \Pi } = \mathbf { \Pi } ( \mathbf { r } _ { 1 } , \omega _ { 1 } )$ and $\mathbf { \Sigma } ( 2 ) = ( \mathbf { r } _ { 2 } , \omega _ { 2 } )$ is given as

$$
\begin{array} { r } { u _ { a b } ( 1 2 ) = \left\{ \begin{array} { l l } { \infty , } & { r _ { 1 2 } < \sigma , } \\ { u _ { \mathrm { d i p } } ( { \bf r } _ { 1 2 } , \omega _ { 1 } , \omega _ { 2 } ) , } & { r _ { 1 2 } > \sigma , } \end{array} \right. } \end{array}
$$

where $r _ { 1 2 } = \left| \mathbf { r } _ { 1 2 } \right| = \left| \mathbf { r } _ { 2 } - \mathbf { r } _ { 1 } \right|$ is the particle separation, $\omega = ( \theta , \phi )$ represents the orientation of a dipole in a spatially fixed coordinate system,and the subscripts $a$ and （204号 $b$ denote the components considered $[ a , b \ : = \ : n , d ]$ ．The dipolar potential is given by

$$
\begin{array} { l } { { \displaystyle { u } _ { \mathrm { d i p } } ( { \bf r } _ { 1 2 } , \omega _ { 1 } , \omega _ { 2 } ) = \frac { \mu ^ { 2 } } { r _ { 1 2 } ^ { 3 } } \{ \hat { \mu } ( \omega _ { 1 } ) \cdot \hat { \mu } ( \omega _ { 2 } ) - 3 [ \hat { \mu } ( \omega _ { 1 } ) \cdot \hat { \bf r } _ { 1 2 } ] } } \\ { { \displaystyle ~ \times \left[ \hat { \mu } ( \omega _ { 2 } ) \cdot \hat { \bf r } _ { 1 2 } ] \right\} , } } \end{array}
$$

where $\hat { \mu } ( \omega )$ and $\hat { \mathbf { r } } _ { 1 2 }$ are unit vectors in the direction of $\omega$ and $\mathbf { r } _ { 1 2 }$ ：

The full information about the system is contained in the total and direct correlation functions $h _ { a b } ( 1 2 )$ and $c _ { a b } ( 1 2 )$ ．We calculate these correlation functions in the homogeneous,high-temperature fluid phase via a numerical solution of the Ornstein-Zernike (O-Z) equation[21]

$$
h _ { a b } ( 1 2 ) = c _ { a b } ( 1 2 ) + \sum _ { c } \int d 3 c _ { a c } ( 1 3 ) \rho _ { c } ( 3 ) h _ { c b } ( 3 2 ) ,
$$

combined with the RHNC closure approximation.

$$
\begin{array} { r l } & { c _ { a b } ( 1 2 ) = - 1 - \eta _ { a b } ( 1 2 ) , \quad r _ { 1 2 } \leqslant \sigma _ { a b } , } \\ & { c _ { a b } ( 1 2 ) = - \beta u _ { a b } ( 1 2 ) - \ln [ 1 + h _ { a b } ( 1 2 ) ] + h _ { a b } ( 1 2 ) } \end{array}
$$

$$
+ \mathrm { B } _ { a b } ( 1 2 ) , \quad r _ { 1 2 } > \sigma _ { a b } ,
$$

where $\eta _ { a b } ( 1 2 ) = h _ { a b } ( 1 2 ) - c _ { a b } ( 1 2 )$ ， $\beta = ( k _ { B } T ) ^ { - 1 }$ is the inverse temperature (with $k _ { B }$ being Boltzmann's constant), and $\mathrm { B } _ { a b } ( 1 2 )$ is so-called Bridge function，which are approximated by the Verlet-Weis hard sphere correlation functions.[22] To solve equations (3)-(5) we expand the angle dependent functions in rotational invariants[23]

$$
f _ { a b } ( 1 2 ) = \sum _ { l _ { 1 } l _ { 2 } l } f _ { a b } ^ { l _ { 1 } l _ { 2 } l } ( r ) \Phi ^ { l _ { 1 } l _ { 2 } l } ( \omega _ { 1 } \omega _ { 2 } \omega _ { r } ) ,
$$

where $\textit { f } = \textit { h }$ or $c$ or $u$ ， $\Phi ^ { l _ { 1 } l _ { 2 } l } ( \omega _ { 1 } \omega _ { 2 } \omega _ { r } )$ are the rotational invariants,a linear combination of the spherical harmonics.[23,24]

$$
\begin{array} { r l } {  { \Phi ^ { l _ { 1 } l _ { 2 } l } \bigl ( \omega _ { 1 } \omega _ { 2 } \omega _ { r } \bigr ) = \sum _ { m _ { 1 } m _ { 2 } m } C \bigl ( l _ { 1 } l _ { 2 } l ; m _ { 1 } m _ { 2 } m \bigr ) } \quad } & { } \\ & { \times D _ { m _ { 1 } 0 } ^ { l _ { 1 } } \bigl ( \omega _ { 1 } \bigr ) D _ { m _ { 2 } 0 } ^ { l _ { 2 } } \bigl ( \omega _ { 2 } \bigr ) \Upsilon _ { l m } \bigl ( \omega _ { r } \bigr ) . } \end{array}
$$

The angels $\omega _ { 1 } , \omega _ { 2 } , \omega _ { r }$ respectively describe orientations of the dipole at $\mathbf { r } _ { 1 }$ ， $\mathbf { r } _ { 2 }$ ,and the jointing vector $\mathbf { r }$ with respect to a space fixed coordinate system.The $C ( l _ { 1 } l _ { 2 } l ; m _ { 1 } m _ { 2 } m )$ are the Clebsch-Gordan coefficients. Then finally after expansion, the RHNC equations combined with the O-Z relations become a system of integral equations for the $r$ dependent coefficient,which is solved by iteration，here the expansion is truncated with $l _ { 1 } , l _ { 2 } \leqslant 3$ . Details of the solution procedure can be found elsewhere.[16,17,25-27]

In the present work,our aim is to characterize the phase behavior of the system upon cooling from an isotropic high-temperature state. In order to do this, we apply a stability analysis developed by Chen and Forstmann[17] which gives us a rigorous criterion and then we can infer the character of the phase transition.

The central idea is to consider the fluctuation $\delta \Omega =$ $\Omega - \Omega ^ { e q }$ of the grand canonical free energy caused by small density fluctuation $\delta \rho _ { a } ( 1 )$ around the homogeneous and isotropic equilibrium state,characterized by the equilibrium density $\rho _ { a } ( 1 ) = \rho _ { a } / 4 \pi$ . Up to the second order, $\delta \Omega$ is given by

$$
\begin{array} { l } { { \delta \Omega \approx \displaystyle \frac { 1 } { 2 } \sum _ { a b } \int d 1 \int d 2 \delta \rho _ { a } ( 1 ) \frac { \delta ^ { 2 } \Omega } { \delta \rho _ { a } ( 1 ) \delta \rho _ { b } ( 2 ) } \Big \vert _ { e q } \delta \rho _ { b } ( 2 ) } } \\ { { = \displaystyle \frac { k _ { B } T } { 2 } \sum _ { a b } \int d 1 \int d 2 \delta \rho _ { a } ( 1 ) \Big [ \frac { \delta _ { a b } \delta ( 1 2 ) } { \rho _ { a } / 4 \pi } - c _ { a b } ( 1 } } \\ { { \times \delta \rho _ { b } ( 2 ) . } } \end{array}
$$

Stability (or metastability) implies that $\delta \Omega$ is positive for any small fluctuation with arbitrary direction in density space.

Introducing Fourier transforms of the density fluctuations and correlation functions,respectively,and expanding these quantities along the $\mathbf { k }$ -frame (which is defined by choosing the polar axis along $\mathbf { k }$ ),then Eq.(8) transforms to

$$
\delta \Omega = { \frac { 2 \pi k _ { B } T } { V } } \sum _ { k } \sum _ { \chi } \sum _ { i j } \delta \bar { \rho } _ { i } ^ { * } ( \chi , k ) [ { \cal M } ( \chi , k ) ] _ { i j } \delta \bar { \rho } _ { j } ( \chi , k ) ,
$$

here the indices $i = ( a , l _ { 1 } )$ and $j = ( b , l _ { 2 } )$ is a combination of particle kind index and angular index,and the fluctuations $\delta { \bar { \rho } } _ { i } ( \chi , k ) = \delta \rho _ { a } ^ { l _ { 1 } , \chi } ( k ) / \sqrt { \rho _ { a } }$ . The elements of the

matrices $M [ \chi , k ]$ are defined as

$$
\begin{array} { r } { [ M ( \chi , k ) ] _ { i j } = \delta _ { i j } - ( - 1 ) ^ { \chi } \sqrt { \frac { \rho _ { a } \rho _ { b } } { ( 2 l _ { 1 } + 1 ) ( 2 l _ { 2 } + 1 ) } } } \\ { \times \tilde { c } _ { a b } ^ { l _ { 1 } l _ { 2 } , \chi } ( k ) . \qquad } \end{array}
$$

With the help of the expansion of the free energy fuctuation Eq. (9),we are able to study phase transitions like the gas-liquid condensation, demixing or orientational phase transitions in detail. The mean value of some fluctuations will diverge at the point of phase instability. But usually the condensation is accompanied by a change of concentration, or orientational phase transition and segregation appear simultaneously. Generally several fluctuations diverge at the phase transition. Only if $\delta \Omega$ isa sum of pure squares of fluctuations,a vanishing prefactor of one fluctuation will lead to the divergence of just this fluctuation,which can be obtained by diagonalizing the matrix $M$ in Eq. (9). The stable phase possess only positive eigenvalues. The phase transition is indicated by one eigenvalue going to zero.The related eigenvector defines the combination of fluctuation,which will become singular at the transition point.

For number density fluctuations we consider the $2 \times 2$ （204号 submatrix $D _ { 0 }$ of $M ( 0 , 0 )$ which is given as

$$
D _ { 0 } = \left( \begin{array} { c c } { 1 - \rho _ { n } \tilde { c } _ { n n } ^ { 0 0 , 0 } ( 0 ) } & { - \sqrt { \rho _ { n } \rho _ { d } } \tilde { c } _ { n d } ^ { 0 0 , 0 } ( 0 ) } \\ { - \sqrt { \rho _ { n } \rho _ { d } } \tilde { c } _ { n d } ^ { 0 0 , 0 } ( 0 ) } & { 1 - \rho _ { d } \tilde { c } _ { d d } ^ { 0 0 , 0 } ( 0 ) } \end{array} \right) .
$$

A vanishing of the smaller eigenvalue $\lambda _ { D }$ of $D _ { 0 }$ indicates demixing or condensation of the system.This can be clar ified by investigating the direction of the eigenvector related to $\lambda _ { D }$ ：

For polarization fluctuations,we consider the two eigenvalues $\lambda _ { F _ { 0 } }$ of the $2 \times 2$ submatrix $F _ { 0 }$ of $M ( 0 , 0 )$ and $\lambda _ { F _ { 1 } }$ of the matrix $M ( 1 , 0 )$ =

$$
\begin{array} { l } { { \displaystyle \lambda _ { F _ { 0 } } = 1 - \frac { 3 } { \rho _ { d } } \tilde { c } _ { d d } ^ { 1 1 , 0 } ( 0 ) , } } \\ { { \displaystyle \lambda _ { F _ { 1 } } = 1 + \frac { 3 } { \rho _ { d } } \tilde { c } _ { d d } ^ { 1 1 , 1 } ( 0 ) . } } \end{array}
$$

Ferroelectric transition of the system is indicated when eigenvalue $\lambda _ { F _ { 1 } }$ goes to zero. To see this we consider the physical precursor of ferroelectric order— that is,the mixture's dielectric constant $\epsilon$ . The relation of this quantity and the two eigenvalues is[8-18]

$$
\epsilon = \frac { \lambda _ { F _ { 0 } } } { \lambda _ { F _ { 1 } } } .
$$

Numerical investigation shows that $\lambda _ { F _ { 0 } }$ remains finite at all states considered. Therefore,a vanishing of $\lambda _ { F _ { 1 } }$ can be uniquely related to a divergence of the dielectric constant.

$$
\epsilon  \infty \Leftrightarrow \lambda _ { F _ { 1 } }  0 ,
$$

which indicates an isotropic-to-ferroelectric transition

The state of the mixtures of dipolar hard spheres and neutral hard spheres is characterized by three physical parameters: the reduced dipole moment $\mu ^ { * }$ defined by （204号 $\mu ^ { * 2 } ~ = ~ \mu ^ { 2 } / \sigma ^ { 3 } k _ { B } T ~ = ~ 1 / T ^ { * }$ （ $T ^ { * }$ is the reduced temperature)，the reduced density of the whole mixture $\rho ^ { * } =$ $( \rho _ { n } + \rho _ { d } ) \cdot \sigma ^ { 3 } = \rho \cdot \sigma ^ { 3 }$ and the concentration of neutral particles $c = c _ { n } = \rho _ { n } / \rho$ . Lowing the temperature at constant total density and concentration we find a temperature $T _ { S } ^ { * } ( \rho ^ { * } , c _ { n } )$ below which the RHNC equation have no solution，where the homogeneous isotropic mixtures become unstable due to a phase transition.In the following we discuss results obtained by varying the concentration of neutral particles and temperature at two representative values of $\rho ^ { * }$ ，one is dilute system with very low densities $\rho ^ { * } = 0 . 0 4$ ，and the other is hight densities $\rho ^ { * } = 0 . 8$ ：

We start by considering the mixtures at $\rho ^ { * } = 0 . 0 4$ The behavior of pure dipolar hard sphere fluids with $\rho ^ { * } = 0 . 0 4$ is investigated by the RHNC integral equation approach $[ 8 ]$ and the Monte Carlo simulations.[3,9] The results from these two methods all indicate that at low densities and certain low temperatures dipolar hard spheres form pairs and chainlike clusters instead of an ordinary gas-liquid transition.

Turning now to mixtures of dipolar hard spheres and neutral hard spheres,we determine the stability limits of the mixed isotropic phase — i.e., the temperatures $T _ { s } ^ { * } ( c _ { n } )$ where the RHNC equations have no solution lowering $T ^ { * }$ towards $T _ { s } ^ { * }$ . Here we consider two representative concentrations $c _ { n } = 0 . 1$ and $c _ { n } = 0 . 8$ . These two systems considered indeed exhibit pair formation which can be seen mostdirectly via the pair correlation functions $h _ { d d } ^ { 2 0 2 } ( r )$ (see Figs.1 and 2).These functions are the projections of the total correlation functions $h _ { d d } ( 1 2 )$ onto the spherical invariant $\Phi ^ { 2 0 2 }$ defined by

$$
\Phi ^ { 2 0 2 } = \frac { 5 } { 4 \pi } \frac { 1 } { 2 } [ 3 ( \widehat { \mu } ( \omega _ { 1 } ) \cdot \widehat { r } _ { 1 2 } ) ^ { 2 } - 1 ] .
$$

From the definition of $\Phi ^ { 2 0 2 }$ , large values of $h _ { d d } ^ { 2 0 2 } ( r )$ thus indicate that the dipolar hard spheres in the neighbor hood of a certain dipolar hard sphere arrange preferably at the “poles”of the sphere.Both in Figs.1 and 2 we see that the first maximum in $h _ { d d } ^ { 2 0 2 } ( r )$ , located at $r = \sigma$ ， grows drastically for $T ^ { * } \to T _ { s } ^ { * }$ , it reflects the growing tendency of two dipolar hard spheres in contact to have a “nose-to-tail-alignment”. Such an arrangement is not surprising because it represents the configuration with the lowest energy of the system.

We now compare our results with those for the pure dipolar hard sphere system ( $c _ { n } = 0$ ） from RHNC approach by S.Klapp and F.Forstmann.[8] In the case $\rho ^ { * } = 0 . 0 4$ $c _ { n } = 0$ , the value of $\boldsymbol { T } _ { s } ^ { * }$ is 0.329,which is higher than the case $c _ { n } = 0 . 1$ and $c _ { n } = 0 . 8$ ，we have $T _ { s } ^ { * } ( c _ { n } = 0 ) > T _ { s } ^ { * }$ $( c _ { n } = 0 . 1 ) > T _ { s } ^ { * } ( c _ { n } = 0 . 8 )$ . We understand this as a consequence of increasing frustration effects: the more dipolar hard spheres are replaced by the neutral hard spheres, the more the two particle interaction which leads to pairing and cluster formation,becomes disturbed.Therefore the temperatures which are necessary to reach the“chainstate”become lower.

To discuss the phase behavior of mixtures at high densities we consider the value $\rho ^ { * } = 0 . 8$ asa representative example.We first determined the instability line of the systems at $\rho ^ { * } = 0 . 8$ for each concentration $c _ { n }$ .Results are shown in Fig.3. Upon lowering $T ^ { * }$ towards $T _ { S } ^ { * }$ ，the RHNC equation have no solution. For the case $c _ { n } = 0$ ,the system is again pure DHS fluids. Turning back to Fig. 3, our results show that the ferroelectric instability appears on the left-hand side of the diagram (small $c _ { n }$ ), just as in the pure DHS system. But on the right-hand side of the diagram (large $c _ { n }$ ),the isotropic demixing appears. This is evidenced by the inverse temperature dependence of the eigenvalues $\lambda _ { F _ { 1 } }$ [see Eq.(21)] and $\lambda _ { D }$ [see Eq.(17)],which are plotted in Fig. 4 for the representative case of $c _ { n } = 0 . 2$ （204号 and $c _ { n } = 0 . 8$ ：

![](images/1e068b478f7dd54c629899760c2a8e9231d2e982b3d4abc1cefe7ed00e1724a1.jpg)  
Fig.1 The coefficient $h _ { d d } ^ { 2 0 2 } ( r )$ at $\rho ^ { * } = 0 . 0 4$ ， $c _ { n } = 0 . 1$ ， and $T ^ { * } \to T _ { S } ^ { * }$ . The inset shows the development of the maximum of the first peak vs inverse temperature.

![](images/bd0b4fd2ad31de507599cd23b1c51ea45c143d19fae41ce764184d6856d90fe7.jpg)  
Fig.2 The coefficient $h _ { d d } ^ { 2 0 2 } ( r )$ at $\rho ^ { * } = 0 . 0 4$ ， $c _ { n } = 0 . 8$ （204号 and $T ^ { * } \to T _ { S } ^ { * }$ . The inset shows the development of the maximum of the first peak vs inverse temperature.

The results in Fig. 4(a) clearly show that $\lambda _ { F _ { 1 } }$ goes to zero significantly faster than $\lambda _ { D }$ at the case $c _ { n } = 0 . 2$ ， the polarization fluctuations become dominating for $T ^ { * } $ $T _ { S } ^ { * }$ .The system thus transform directly into ferroelectric phases as do in the pure DHS system.On the other hand,at the large concentration $c _ { n } = 0 . 8$ (Fig.4(b)) $\lambda _ { D }$ goes to zero firstly,and using the direction of the related eigenvector,indicating that the diverging fluctuations related to $\lambda _ { D }$ are essentially concentration (rather than total density） fluctuations.All our results are consistant with the RHNC study of monodisperse DHS mixtures[18] with small interaction parameters.

Finally,it is worth to note from Fig.3 that on the left hand side of the diagram,the instability temperatures $T _ { S } ^ { * }$ are slowly increased upon replacing dipolar hard spheres more and more by neutral hard spheres.It indicates that the appearance of the neutral hard spheres is helpful for aferroelectric transition.

![](images/9bc48b33fada3d14981d39751761141d8808f4dd6e15ec9ee21a768a0b34cce5.jpg)  
Fig.3 The instability line of dipolar and neutral hard spheres mixtures with the total density $\rho ^ { * } = 0 . 8$ in the concentration-temperature plane.

In conclusion,we have seen that for DHS and neutral hard sphere mixtures, the RHNC theory is capable to predict the phase transition both at small and high densities. At very low total density $\rho ^ { * } = 0 . 0 4$ which is in the range where the pure DHS system associate into short clusters at sufficiently low temperatures.The same type of phase behavior is found to occur in our DHS and neutral hard sphere mixtures for all concentration $c _ { n }$ ，and the instability temperature $T _ { S } ^ { * }$ is gradually decreased when more and more dipolar hard spheres are replaced by the neutral hard spheres.At the large total density $\rho ^ { * } = 0 . 8$ ,our results show that the phase behavior of the mixtures is dependent on the concentration $c _ { n }$ .The ferroelectric instability appears when the concentration $c _ { n }$ is small. The main difference to the pure DHS system is the isotropic-toferroelectric temperature towards larger values upon replacing the dipolar hard spheres more and more by the neutral hard spheres. The RHNC fluctuations also indicate the ferroelectric transition to be accompanied by a change of composition.But with the large concentration $c _ { n }$ , the isotropic demixing appears when lowering the temperature. This is consistant with a recent RHNC study[18] of binary mixtures of dipolar hard spheres.

![](images/cee7ec00927ff1b1449b0f0db9c71d880ba832ad9ef0ec6abc1688b50ca40555.jpg)  
Fig.4 The eigenvalues $\lambda _ { F _ { 1 } }$ (solid lines）and $\lambda _ { D }$ (dashedlines） as functions of the inverse temperature at $\rho ^ { * } = 0 . 8$ （204号and $c _ { n } = 0 . 2$ (a)and $c _ { n } = 0 . 8$ (b).

# References

[1]J.J.Weis,D.Levesque,and G.J. Zarragoicoechea,Phys. Rev.Lett.69(1992) 913.   
[2] J.J.Weis and D.Levesque,Phys.Rev. E 48 (1993) 3728.   
[3]D.Levesque and J.J.Weis,Phys.Rev.E 49(1994) 5131.   
[4] H. Zhang and M. Widom,Phys.Rev. E 49 (1994) 3591.   
[5] B.Groh and S. Dietrich, Phys. Rev. Lett. 72 (1994) 2422.   
[6] B.Groh and S. Dietrich,Phys.Rev.E 50(1994) 3814.   
[7] D.Weis and G.N. Patey, Phys. Rev. E 47(1993) 506.   
[8] Sabine Klapp and Frank Forstmann,J.Chem.Phys.106 (1997) 9742.   
[9] J.J.Weis and D.Levesque,Phys.Rev.Lett. 71 (1993) 2729.   
10]J.M. Tavares,J.J.Weis,and M.M.Telo da Gama,Phys. Rev.E 59(1999) 4388.   
11] P.G.de Gennes and P.A.Pincus,Phys.Kindens.Mater. 11 (1970) 189.   
12] T.Tlusty and S.A. Safran,Science 290 (2000) 1328.   
13]J.M.Caillol,J.Chem.Phys.98（1993) 9835.   
14] M.E. van Leeuwen and B.Smit，Phys.Rev.Lett.71 (1993) 3991.   
[15] M.J. Stevens and G.S.Grest，Phys.Rev. E 51 (1995) 5962.   
[16] X.S. Chen, M. Kasch,and F.Forstmann, Phys. Rev. Lett. 67(1991) 2674.   
[17] X.S. Chen and F. Forstmann,Mol. Phys. 76 (1992) 1203.   
[18] Gabriel M. Range and Sabine H.L.Klapp,Phys.Rev.E 70(2004）031201.   
[19] M.J. Blair and G.N. Patey, Phys. Rev. E 57 (1998) 5682.   
[20] M.Kinoshita and M.Harada,Mol.Phys.79(1993)145.   
[21] J.P. Hansen and I.R. McDonald, Theory of Simple Liquids,Academic, London (1976).   
[22] L.Verlet and J.J. Weis,Phys. Rev.A 5 (1972) 939.   
[23] C.G.Gray and K.E.Gubbins,Theory of Molecular Fluids, Oxford University, London (1984).   
[24]L.Blum and A.J.Torruella,J.Chem.Phys.56 (1972) 303.   
[25] P.H. Fries and G.N. Patey, J. Chem. Phys. 82 (1985) 429.   
[26] J.M. Caillol, Chem.Phys.Lett.121(1985) 347.   
[27] M.Kasch and F.Forstmann,J.Chem.Phys.99 (1993) 3037.   
[28] D.Weis and G.N. Patey,Phys. Rev. Lett. 68(1992) 2043.   
[29]D.Weis and G.N. Patey, Phys.Rev.A 46 (1992) 7783.