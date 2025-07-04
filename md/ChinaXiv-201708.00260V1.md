# Spherical-box approach for resonances in presence of Coulomb interaction

Shan-Gui Zhou $\cdot ^ { 1 , 2 , 3 }$ , Jie Meng $^ { 4 , 5 , 1 , 2 , 3 }$ and En-Guang Zhao $^ { 1 , 2 , 3 , 4 }$

$^ 1$ Key Laboratory of Frontiers in Theoretical Physics, Institute of Theoretical Physics. Chinese Academy of Sciences,Beijing 100190,China   
$^ 2$ Kavli Institute for Theoretical Physics China at the Chinese Academy of Sciences, Beijing 100190, China   
（204 $^ 3$ Center of Theoretical Nuclear Physics, National Laboratory of Heavy Ion   
Accelerator, Lanzhou 730000, China   
（204号 $^ 4$ School of Physics, Peking University, Beijing 100871, China   
$^ { 5 }$ Department of Physics, University of Stellenbosch, Stellenbosch, South Africa

E-mail: sgzhou@itp.ac.cn

Abstract. The spherical-box approach is extended to calculate the resonance parameters and the real part of the wave function for single particle resonances in a potential containing the long-range Coulomb interaction. A model potential is taken to demonstrate the ability and accuracy of this approach. The calculated resonance parameters are compared with available results from other methods. It is shown that in the presence of the Coulomb interaction, the spherical-box approach works well for not so broad resonances. In particular, for very narrow resonances, the present method gives resonance parameters in a very high precision.

# 1.INTRODUCTION

The investigation of continuum and resonant states is an important subject in quantum physics. For the theoretical determination of resonant parameters (the energy and the width)，in addition to many approaches which are based on the connection of the unbound states (including resonances and antibound or virtual states） and the poles of the S matrix， several bound-state-like methods have been developed， e.g, the complex scaling method (CSM) [1，2, 3,4, 5,6, 7,8, 9], the complex absorbing potential (CAP) method [10,11], the analytical continuation in the coupling constant (ACCC) approach [12, 13,14,15,16,17, 18,19, 20],and the real stabilization method (RSM) [21,22,23,24,25,26,27,28,29,30].

In the real stabilization method, the Schrodinger equation (or the Dirac equation in relativistic models) of the system in question is solved in a basis [21] or a box [24] of finite size, thus a bound state problem is always imposed. The RSM is based on the fact that the energy of a “resonant” state is “stable” against the change of the size of the basis or the box. Many efforts have been made in order to calculate more effciently resonance parameters with the RSM [24, 25, 26, 27, 28, 29]. One of the effective ways to do so is the so called “spherical-box approach” [24] in which the energy and width of a resonance in finite-range potentials are determined from the variation of the discrete positive energies with the radius of the box. The spherical-box approach for short range potential has been vigorously proved [31]. In a recent work [30], the single neutron resonances in atomic nuclei were investigated by combining the RSM and the relativistic mean field model [32, 33].

In many atomic, molecular and nuclear processes, the long-range Coulomb interactions play important roles. Therefore it is necessary to develop the sphericalbox approach for resonances in the presence of the long-range interaction and check its validity and accuracy. In the present work, we extend the spherical-box approach in order to include the influence of the Coulomb force.

The paper is organized as follows. In section 2 we give the formalism of the spherical-box approach for resonances in the presence of the Coulomb interaction. The numerical details, the results for a model potential and discussions are given in section 3. Finally in section 4 we summarize our work.

# 2.Formalism

We deal with a central field problem. The radial Schrodinger equation reads (in atomic units)

$$
\left[ - \frac { 1 } { 2 } \frac { d ^ { 2 } } { d r ^ { 2 } } + \frac { l ( l + 1 ) } { 2 r ^ { 2 } } + V _ { 0 } ( r ) + \frac { Z } { r } \right] \Psi _ { k } ( r ) = E \Psi _ { k } ( r ) ,
$$

where $V _ { 0 } ( r )$ is a finite-range potential and $E = k ^ { 2 } / 2$ . Under the box boundary condition the continuum is discretized and one is left with a bound state problem. When the size of the box $\mathcal { R }$ is large enough, the energies of bound states, if there are any, do not change with $\mathcal { R }$ . In the continuum region, there are some states stable against the change of the size of the box,i.e., the energy of each of such states is almost constant with the variation of $\mathcal { R }$ ； such stable states correspond to resonances. It should be noted that the spherical-box approach is essentially different from the “variable phase approach" where the potential in question is amputated of its part extending beyond a distance $r$ and one needs to solve a series of scattering problems for different $r$ [34].

In the spherical-box approach, the resonance energy is determined by the stability condition,

$$
\left. \frac { \partial ^ { 2 } E } { \partial \mathcal { R } ^ { 2 } } \right| _ { E = E _ { \gamma } } = 0 ,
$$

the corresponding box size is labeled as $\mathcal { R }$ ,i.e., $E _ { \gamma } = E ( \mathcal { R } )$

The width can be evaluated from the stability behavior of the positive energy state against the change of the box size around $\mathcal { R }$ [24].When $r$ is large enough,the finiterange potential $V _ { 0 } ( r )$ vanishes and $\Psi _ { k } ( r )$ satisfies,

$$
\Psi _ { k } ( r ) \propto \frac { 1 } { k r } \sin ( k r - \frac { l \pi } { 2 } - \gamma \ln ( 2 k r ) + \eta _ { l } ) ,
$$

where $\boldsymbol { \eta } _ { l }$ is the phase shift. $- \gamma \ln ( 2 k r )$ comes from the long range Coulomb interaction with $\gamma = Z / k$ . The box boundary condition $\Psi _ { k } ( \mathcal { R } ) = 0$ gives

$$
k \mathcal { R } - \frac { l \pi } { 2 } - \gamma \ln ( 2 k \mathcal { R } ) + \eta _ { l } = n \pi .
$$

Thus the derivative of the phase shift with respect to the box size reads,

$$
\frac { d \eta _ { l } } { d \mathcal { R } } = \mathrm { ~ - ~ } \left( 1 - \frac { \gamma } { \sqrt { 2 E } \mathcal { R } } \right) \left( \sqrt { 2 E } + \frac { 1 } { \sqrt { 2 E } } \frac { d E } { d \mathcal { R } } \mathcal { R } \right) + \ln \left( 2 k \mathcal { R } \right) \frac { d \gamma } { d \mathcal { R } } .
$$

Around an isolated resonance， the energy $E$ and the phase shift $\eta _ { l } ( E )$ satisfy the following relation,

$$
\eta _ { l } ( E ) = \eta _ { l , \mathrm { p o t } } ( E ) + \tan ^ { - 1 } \left( \frac { \Gamma / 2 } { E - E _ { \gamma } } \right) .
$$

Under the assumption that the phase shift from the potential scattering $\eta _ { l , \mathrm { p o t } } ( E )$ varies slowly with respect to the box size, i.e, $\partial \eta _ { l , \mathrm { p o t } } / \partial \mathcal { R } \sim 0$ , one derives the formula for the width,

$$
\frac { \Gamma } { 2 } = \frac { - \sqrt { 2 E _ { \gamma } } } { \left( 1 - \frac { Z } { \sqrt { 2 E _ { \gamma } } \bar { \mathcal { R } } } \right) \left( \bar { \mathcal { R } } + 2 E _ { \gamma } \left[ \frac { d E } { d \mathcal { R } } \big | _ { \mathcal { R } = \bar { \mathcal { R } } } \right] ^ { - 1 } \right) + \frac { Z } { 2 E _ { \gamma } } \ln ( \sqrt { 8 E _ { \gamma } } \mathcal { R } ) } .
$$

Note that the above formula goes back to equation (8） in [24] when the Coulomb interaction is absent,i.e., $Z = 0$ ：

# 3．Amodel problem

In order to check the ability and the accuracy of the spherical-box approach for resonances in potentials containing a long-range interaction, we solve a model problem

and compare our results with those predicted by other methods. We choose the following potential,

$$
V ( r ) = V _ { 0 } r ^ { 2 } e ^ { - r } + \frac { Z } { r } ,
$$

which has been extensively investigated for $Z = 0$ and/or $Z = - 1$ [35, 24, 26, 36, 37].   
We take $V _ { 0 } = 7 . 5$ in the present work.

# 3.1. Numerical procedure

The Schrodinger equation (1） with the potential (8) is solved under the box boundary condition by using the shooting method [38, Chapter 18] with the forth order RungeKutta algorithm. For $Z = 0$ , the energy calculated from the shooting method converges with the step size decreasing and the relative error reaches to within $1 0 ^ { - 8 }$ with a step size $\delta r = 0 . 0 0 1$ .For $Z = - 1$ , a step size $\delta r = 0 . 0 0 0 1$ gives the relative accuracy $\leq 1 0 ^ { - 8 }$ （20 in the energy. In the following we shall present results for the potential (8) with $Z = - 1$ ： The step size $\delta r = 0 . 0 0 0 1$ will be used in order to get a high accuracy comparable to the results given in the literature.

# 3.2. Resonance parameters

![](images/e7af12bb454365c549805789e6236367d722757c93fda719cdd5a16504b5b234.jpg)  
Figure 1. The energies of s wave states calculated in a spherical-box of diferent sizes. The inset shows the first avoid crossing which is zoomed in. The red dotted curve represents the potential (8) around the barrier.

We first present results for s states. In figure 1 the potential $V ( r )$ given in (8) and the energies of s states versus the box size are presented. By examining the figure, two resonances can be found with energies about 1.8 and 4.O respectively. The former is very narrow as is indicated by the sharp avoid crossings. The latter, however, is above the barrier and very broad.

The resonance parameters evaluated at different stable regions are given in table 1 for the very narrow resonance. For comparison, the results obtained from the complex methods are also included [36,37]. With $\mathcal { R }$ increasing, the resonance energy converges to a stable value very fast. For this narrow resonance, the spherical-box approach gives very precise energy and width which are comparable to the exact values given in [37]. One achieves a seven-significant-digit accuracy for the energy at the third avoid crossing with $\mathcal { R } = 8 . 7 5 0 9$ and a four-significant-digit accuracy for the width at the ninth avoid crossing with $\mathcal { R } = 1 8 . 5 6 3 3$ . These high precisions are very encouraging. One can then safely use this spherical-box approach in studying narrow resonances with computational efforts much less than complex calculations.

Table 1. The energy and width of the first s wave resonance evaluated at different avoid crossings from (2) and (7). All quantities are in atomic units.   

<html><body><table><tr><td>R</td><td>Eq</td><td>T</td></tr><tr><td>5.0163 7.0547</td><td>1.780 531 212 1.780 525 482</td><td>6.302 9×10-5 8.764 7×10-5</td></tr><tr><td>8.7509</td><td>1.780 524 837</td><td>9.344 1×10-5</td></tr><tr><td>10.3918</td><td>1.780 524 706</td><td>9.507 7×10-5</td></tr><tr><td>12.0226</td><td>1.780 524 661</td><td>9.553 6×10-5</td></tr><tr><td>13.6542</td><td>1.780 524 606</td><td>9.566 2×10-5</td></tr><tr><td>15.2878</td><td>1.780 524 620</td><td>9.569 6×10-5</td></tr><tr><td>16.9243</td><td>1.780 524 629</td><td>9.570 7×10-5</td></tr><tr><td></td><td>1.780 524 635</td><td>9.571 1×10-5</td></tr><tr><td>18.5633</td><td>1.780 524 634</td><td>9.571 3×10-5</td></tr><tr><td>20.2045</td><td></td><td></td></tr><tr><td>[37] [36]</td><td>1.780 524 536 1.780 5</td><td>9.571 9×10-5 9.58×10-5</td></tr></table></body></html>

Table 2.The energy and width of the second s wave resonance evaluated at different avoid crossings from (2) and (7). All quantities are in atomic units.   

<html><body><table><tr><td>R</td><td>一 Eq</td><td></td></tr><tr><td>3.4784 4.9943 6.2534</td><td>4.101 765 300 4.053 255 228 4.021498 436 3.995 348 518</td><td>0.582 256 450 0.804 538 485 0.939 289 481 1.024 872 144</td></tr><tr><td>8.5939 9.7483</td><td>3.970 907 320 3.945 799 270</td><td>1.083 354 259 1.101 418 144</td></tr><tr><td>10.9117 12.0986</td><td>3.917 591 013 3.881 431 163</td><td>1.144 053 591 1.198 720 256</td></tr><tr><td>13.3808</td><td>3.807 212 130</td><td>1.329 057 297</td></tr></table></body></html>

The second s wave resonance is quite broad. In table 2 we list the resonance parameters obtained for this resonant state at different stable points $\mathcal { R }$ .When （204 $\mathcal { R } > 1 3 . 3 8 0 8$ ， one can not find a stable region satisfying the condition $\partial ^ { 2 } E / \partial \mathcal { R } ^ { 2 } =$ $0$ in the present numerical accuracy. At the last observed avoid crossing, the resonance energy deviates from the exact value by 8% and the width by 15% [37]. This may be used as a guide to estimate the accuracy of the spherical-box approach for broad resonances.

A third s wave resonance was predicted to be lying at 4.66 by the complex method [37]. It is very broad with a width 5.34. There is no hint for this resonance from figure 1. This implies that such a broad resonance is beyond the ability of the spherical-box approach. We note that for very broad resonances, the assumption that the phase shift from the potential scattering $\eta _ { l , \mathrm { p o t } } ( E )$ in (6) varies slowly with respect to the box size may not hold. This could be one of the reasons why the present method does not work well for broad resonances.

![](images/f69f2629ab888a5de80504877557ff71156e488162d2a4846bc3ee87edf016c2.jpg)  
Figure 2. The energies of p wave states calculated in a spherical-box of different sizes.The red dotted curve represents the potential (8) together with the centrifugal potential.

The energies of p states are plotted as a function of the box size $\mathcal { R }$ in figure 2. The effective potential $V _ { \mathrm { e f f } } ( r ) = V ( r ) + l ( l + 1 ) / 2 r ^ { 2 }$ with $V ( r )$ given in (8） is also shown in the same figure. Only one resonance is found which is close to the barrier and the energy is around 3.8. This state is broader than the first but narrower than the second S wave resonances. The parameters for this resonance are given in table 3. Both the energy and the width converge well with $\mathcal { R }$ increasing. At the sixth stable point with （204 $\mathcal { R } = 9 . 6 9 4 5$ , the relative deviation of the energy from the converged value (obtained from the last avoid crossing at around 19.8229) is less than $0 . 1 \%$ and that of the width less than $1 \%$

Figure 3 shows the $E \sim \mathcal { R }$ plot for the d states. There is almost no pocket in the effective potential. But one can still find slightly stable regions in the energy range 4.5\~5.0 in the first several $E \sim \mathcal { R }$ curves. Indeed we could find stable points fulfilling the condition $\partial ^ { 2 } E / \partial \mathcal { R } ^ { 2 } = 0$ at the first six avoid crossings for the d state. Thus the resonance parameters could be calculated and they are listed in table 4. At $\mathcal { R } = 9 . 3 1 6 4$ ， the relative deviation of the resonance energy is within 3% and that of the width is about 8% compared with the values obtained at the previous stable point $\mathcal { R } = 8 . 1 4 3 8$

Table 3. The energy and width of the p wave resonance evaluated at different avoid crossings from (2) and (7). All quantities are in atomic units.   

<html><body><table><tr><td>R</td><td>E</td><td>T</td></tr><tr><td>3.3342</td><td>3.8665</td><td>0.1401</td></tr><tr><td>4.9740</td><td>3.8501</td><td>0.2101</td></tr><tr><td>6.2430</td><td>3.8471</td><td>0.2388</td></tr><tr><td>7.4205</td><td>3.8457</td><td>0.2519</td></tr><tr><td>8.5641</td><td>3.8450</td><td>0.2581</td></tr><tr><td>9.6945</td><td>3.8445</td><td>0.2610</td></tr><tr><td>10.8201</td><td>3.8442</td><td>0.2608</td></tr><tr><td>11.9441</td><td>3.8440</td><td>0.2616</td></tr><tr><td>13.0681</td><td>3.8437</td><td>0.2620</td></tr><tr><td>14.1925</td><td></td><td>0.2623</td></tr><tr><td>15.3174</td><td>3.8431</td><td></td></tr><tr><td></td><td>3.8433</td><td>0.2625</td></tr><tr><td>16.4430</td><td>3.8431</td><td>0.2626</td></tr><tr><td>17.5691</td><td>3.8429</td><td>0.2628</td></tr><tr><td>18.6958 19.8229</td><td>3.8427 3.8425</td><td>0.2629 0.2631</td></tr></table></body></html>

![](images/ac3975b2e56cc8f647280aa2828cc62a2d77906f8b61e5ebed8c7333580345cb.jpg)  
Figure 3. The energies of d wave states calculated in a spherical-box of different sizes.The red dotted curve represents the potential (8) together with the centrifugal potential.

Similar to the case for the second s wave resonance, one can not find further stable behavior in the region $\mathcal { R } > 9 . 3 1 6 4$

No higher partial wave resonances are found in the present study

# 3.3. Wave functions of the resonances

Since the schrodinger equation (1） is solved within a spherical-box, we can only get the real part of the wave function for each resonant states. The wave functions for the resonances found in the present work are shown in figure 4. The behavior of the wave function is consistent with the width of the resonance. For the first s wave resonance which is quite narrow, the wave function is almost completely localized inside the range of the finite range potential $V _ { 0 } ( r ) = 7 . 5 ~ r ^ { 2 } e ^ { - r }$ . But for the broad s resonance, the radial wave function inside the potential barrier is much depressed and it oscillates very much in the asymptotic region. For the p wave resonance,one still finds a localization feature in its radial wave function, but not so prominent as the case of the first s resonant state. The wave function of the d resonance is similar to that of the second s state (note that the scales in the upper and lower panels are different), except that the former vanishes at the origin.

Table 4. The energy and width of the d wave resonance evaluated at different avoid crossings from (2) and (7). All quantities are in atomic units.   

<html><body><table><tr><td>R</td><td>E</td><td>Γ</td></tr><tr><td>3.2624</td><td>4.8689</td><td>0.7135</td></tr><tr><td>4.6913</td><td>4.8063</td><td>0.9744</td></tr><tr><td>5.8924</td><td>4.7518</td><td>1.1486</td></tr><tr><td>7.0239</td><td>4.6992</td><td>1.2779</td></tr><tr><td>8.1438</td><td>4.6391</td><td>1.3920</td></tr><tr><td>9.3164</td><td>4.5409</td><td>1.5120</td></tr></table></body></html>

![](images/29e1fc312a58d18faf1c79e76aed874089d5c34b43ae2d2928e91c949bed18d6.jpg)  
Figure 4. The radial wave function $\Psi ( r )$ of the first and the second s wave resonances (lower panel) and of the p and d wave resonances (upper panel). Note that when $r > 5 . 0 \AA$ , the wave functions for the two s resonances are multiplied by 10.

The real stabilization method is based on the fact that a resonance is more or less localized. Therefore the energy of a resonant state is only weakly affected by the variation of the size of the spherical-box. This has been shown in [24,30] as well as in the present work. Next we show the convergence of the real radial wave function with respect to the box size. The radial wave function of the p wave resonance is shown in figure 5. In order to see clearly the asymptotic behavior, the wave function $\Psi ( r )$ is multiplied by the radial coordinate $r$ .With $\mathcal { R }$ increasing,more nodes appear and the wave function inside the potential barrier decreases only slightly. This reveals that the wave function of a narrow resonance is affected little by the box size $\mathcal { R }$ due to the localization property.

![](images/5e2df33f999a1df5c21eda35c4127bc79fd9a90fcdfb371a8e05d9ba012afee9.jpg)  
Figure 5.The radial wave function of the p resonance within a box of different size. Note that the wave function is multiplied by the radial coordinate $r$ in order to see clearly the asymptotic behavior.

# 4.Summary

The spherical box-approach,which is one of the effective implementations of the real stabilization methods for single particle resonances, is extended to the case in which a long-range force such as the Coulomb interaction plays a role. The formalism is presented and the numerical realization is fulfilled for this approach.

We take a model potential (8) as an example to demonstrate the ability and the precision of this approach. It is shown that in the presence of the Coulomb interaction, the spherical-box approach still works well for narrow resonances. In particular the present method can give resonance parameters in a quite high precision for very narrow resonances. The energy and width also converge reasonably fast with the box size increasing. Within the spherical-box, the real wave functions of these resonances are obtained. The localization behavior of the radial wave function is consistent with the width of a resonance. The convergence of the radial wave function with the increases of the box size is studied, which shows that the wave function of a narrow resonance is also “stable” against the changes of the box size.

# Acknowledgments

We would like to thank Professor Shun-Jin Wang for helpful discussions. This work was partly supported by the National Natural Science Foundation (10705014， 10775004,

and 10875157)， the Major State Basic Research Development Program of China (2007CB815000) and the Knowledge Innovation Project of CAS (KJCX3-SYW-N02). The computation of this work was supported by Supercomputing Center, CNIC, CAS.

# References

[1] Kato K 2006 J. Phys: Conf. Ser. 49 73-78   
[2] Kruppa A T, Lovas R G and Gyarmati B 1988 Phys. Rev. C 37 383-389   
[3] Reinhardt W P 1982 Annu. Rev. Phys. Chem.33 223-255   
[4] Ho Y K 1983 Phys. Rep.99 1-68   
[5] Moiseyev N 1998 Phys. Rep.302 212-293   
[6] Gyarmati B and Kruppa A T 1986 Phys. Rev. C 34 95-102   
[7] Kruppa A T, Heenen P H, Flocard H and Liotta R J1997 Phys.Rev. Lett.79 2217-2220   
[8] Moiseyev N and Cederbaum L S 2005 Phys. Rev. A 72 033605-8   
[9] Arai K 2006 Phys. Rev. C 74 064311-7   
[10] Riss U V and Meyer HD 1993 J. Phys. B: At. Mol. Opt.Phys. 26 4503-4535 ISSN 0953-4075   
[11] Mueller IB, Santra R and Cederbaum L S 2003 Int. J. Quantum Chem. 94 75-92   
[12] Kukulin V I and Krasnopol'sky V M 1977 J. Phys. A: Math. Gen.10 L33-L37   
[13] Kukulin V I, Krasnopol'sky V M and Miselkhi M 1979 Sov. J. Nucl. Phys. 29 421   
[14] Kukulin V I, Krasnopol'sky V M and Horacek J 1989 Theory of Resonances: Principles and   
Applications (Kluwer Academic,Dordrecht)   
[15] Tanaka N, Suzuki Y and Varga K 1997 Phys. Rev. C 56 562-565   
[16] Tanaka N, Suzuki Y, Varga K and Lovas R G 1999 Phys. Rev. C 59 1391-1399   
[17] Yang S C,Meng Jand Zhou S G 2001 Chin. Phys. Lett.18 196-198   
[18] Cattapan G and Maglione E 200O Phys.Rev. C 61 O67301-4   
[19] Zhang S S, Meng J, Zhou S G and Hillhouse G C 2004 Phys. Rev. C 70 034308-8   
[20] Guo JY, Wang R D and Fang X Z 2005 Phys. Rev. C 72 054319-8   
[21] Hazi A U and Taylor H S 1970 Phys. Rev. A1 1109-1120   
[22]Fels MF and Hazi AU 1971 Phys.Rev.A 4662-674   
[23]Fels MF and Hazi AU1972 Phys.Rev.A5 1236-1249   
[24] Maier C H, Cederbaum L S and Domcke W 1980 J. Phys.B: At. Mol. Phys.13 L119-L124   
[25] Taylor H S and Hazi A U1976 Phys.Rev. A 14 2071-2074   
[26] Mandelshtam V A,Ravuri T R and Taylor H S 1993 Phys. Rev. Lett.7O 1932-1935   
[27] Mandelshtam V A, Taylor H S, Ryaboy V and Moiseyev N 1994 Phys. Rev. A 50 2764-2766   
[28] Kruppa A T and Arai K 1999 Phys.Rev. A 59 3556-3561   
[29] Adamson S, Kharlampidi D and Dementiev A 2008 J. Chem. Phys. 128 024101   
[30] Zhang L, Zhou S G,Meng Jand Zhao E G 2008 Phys. Reu. C 77 014312-6   
[31]Hagedorn G A and Meller B 200O J.Math.Phys.41103-117   
[32] Vretenar D,Afanasjev A,Lalazissis G and Ring P 2005 Phys. Rep. 409 101-259   
[33] Meng J, Toki H, Zhou S, Zhang S,Long W and Geng L 2006 Prog. Part. Nucl. Phys. 57 470-563   
[34] Calogero F 1967 Variable Phase Approach to Potential Scattering (New York: Academic Press)   
[35] Isaacson A D,McCurdy C W and Miller W H1978 Chem.Phys.34 311-317   
[36] Yamani H A and Abdelmonem M S 1995 J. Phys. A: Math. Gen.28 2709   
[37] Sofianos S A and Rakityansky S A 1997 J. Phys. A: Math. Gen.30 3725   
[38] Press W H, Teukolsky S A and Vetterling Willim TF B P 2007 Numerical Recipes: the Art of   
Scientific Computing 3rd ed (Cambridge University Press)