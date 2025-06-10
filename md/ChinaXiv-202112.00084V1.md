# Terahertz permeability of FePt nanowire

Mangui HAN\*, Sen MENG

School ofMaterialsand Energy, UniversityofElectronic Scienceand Technology of China,Chengdu, China

Author contribution statements:

(1） HAN proposed the whole research ideas, provided the simulation parameters,and designed the simulation procedures.   
(2）MENG conducted the simulations under the guidance of HAN,and prepared the figures.   
（3）HAN analyzed the data.   
(4）HAN prepared the whole manuscript in English.

\*Correspondence:

Mangui HAN（韩满贵） (magnet@uestc.edu.cn), corresponding author. Sen MENG (孟森) (mengsen163@163.com)

# Abstract

Compared to the gigahertz (GHz） permeability of single Fe nanowire, terahertz (THz) permeability of single $\mathrm { L } 1 _ { 0 }$ -FePt nanowire at its remanent state ( $\mathrm { ( M r / M s = } 1 . 0$ )has been simulated in the micromagnetics approach. Due to its very large magnetocrystalline anisotropic field, it is feasible to obtain strong THz permeability at $0 . 3 4 8 \mathrm { T H z }$ ，which are ever thought only possible in some metamaterials. The THz permeability spectra of $\mathrm { L } 1 _ { 0 }$ -FePt are shown obviously different from those of Fe nanowire at gigahertz (GHz). Unusual negative imaginary parts of permeability $\scriptstyle \left( \mu ^ { \prime \prime } < 0 \right)$ is found related to the equivalent negative damping constant, which is explained from the perspective of abnormal precession of natural resonance at THz for FePt nanowire .

Key words: Terahertz; permeability; FePt nanowires; natural resonance;micromagnetics

# 1. Introduction

materials to external magnetic fields.For electromagnetic applications, it is crucial to understand how the complex permeability values (real parts and imaginary parts) vary with the frequency [1]. The resonance frequency $( f _ { r } )$ of permeability spectrum governs the operation scope of magnetic materials. For applications demanding low magnetic loss, the resonance frequency should be far away from the working frequency, such as magnetic cores of transformers, microwave magnetic devices (such as circulators). For applications demanding large magnetic loss, the resonance frequency should fallinto the operation scope so as to dissipate the electromagnetic wave energy via the magnetic resonance phenomena, for instance,the anti electromagnetic interference or stealth technology. Up to now， it is believed that the highest operating frequencies of electromagnetic devices employed naturally synthesized magnetic materials falls into the W-band $( 7 5 - 1 0 0 ~ \mathrm { G H z } )$ , which was realized by employing BaM type ( $\mathrm { \langle B a F e _ { 1 2 } O _ { 1 9 } \rangle }$ ）hexaferrites in which Fe cations are properly substituted by Al and Ga cations [2,3].With the rapid advances of technology, human beings begin to develop devices working in the terahertz (THz) spectrum (0.1 $\mathrm { T H z } \cdot 1 0 ~ \mathrm { T H z } ,$ ） of electromagnetic wave. It is well accepted that most of naturally synthesized magnetic materials can not play roles in the THz domain due to the limitation of their much lower resonance frequency. This is the reason that the metamaterials are frequently designed to obtain THz permeability [4-6]. Is it really impossible to employ the naturally synthesized materials for THz applications? In this paper, we will demonstrate how a very strong hard ferromagnetic $\mathrm { L } 1 _ { 0 }$ FePt (hereinafter called FePt) nanowire can exhibit obvious THz permeability spectra. FePt with a tetragonal structure is one of the promising materials with an ultra large areal storage density $( >$ $4 0 0 ~ \mathrm { G b / c m ^ { 2 } }$ ） in the next generation perpendicular magnetic recording industry [7]. $\mathrm { L } 1 _ { 0 }$ -FePt has a very large magnetocrystalline anisotropy constants $( K )$ and a very small critical diameter of forming single domain without superparamagnetism effect [8-10]. In order to increase the natural resonance frequency up to THz, strong shape anisotropy field could add up with the magnetocrystalline anisotropy field $( H _ { k } )$ . Nanowire is a typical shape having strong shape anisotropy field. The following table gives the $\pmb { K }$ values and coercivity values $( H _ { c } )$ of several typical hard magnet and the ease to fabricate them in shape of nanowire by electrochemical deposition techniques.

Table 1: magnetocrystalline anisotropy $( K )$ ,coercivity $( H _ { c } )$ ,resonance frequency $( f _ { r } )$ and ease in shape of nanowires 1]   

<html><body><table><tr><td>Materials</td><td>K(J/m³)[15]</td><td>Hk (kOe)</td><td>Ms (A/m)</td><td>Ease of NWs</td><td>f.(GHz)</td><td>Refs.</td></tr><tr><td>Nd2Fe14B</td><td>4.3×10</td><td>73</td><td>1.27 x106</td><td>No</td><td></td><td>[15]</td></tr><tr><td>SmC05</td><td>1.7×107</td><td>400</td><td>8.36×105</td><td>No</td><td>1132**</td><td>[15]</td></tr><tr><td>BaFe12O19</td><td>3.2×105</td><td>17</td><td>3.82x105</td><td>No</td><td>36</td><td>[15]</td></tr><tr><td>L1o-FePt</td><td>6.6x106</td><td>116</td><td>1.14 ×106</td><td>Good</td><td>348**</td><td>[15]</td></tr><tr><td>MnBi</td><td>1.6x106</td><td>--</td><td>7.16×105</td><td>No</td><td></td><td>[12]</td></tr><tr><td>L1o-FeCo</td><td>1.0×10</td><td>-</td><td>1.91x106</td><td>Good</td><td></td><td>[13]</td></tr><tr><td>L1o-FeNi (meteorite)</td><td>1.3x106</td><td>--</td><td>1.17x106</td><td>No</td><td>--</td><td>[14]</td></tr></table></body></html>

\*\* patented and to be published.

# 2. Micromagnetics theory and simulations

Micromagnetics approach uses a continuum approximation to analyze magnetization behaviors (hysteresis loops)， domain structures or dynamic responses of magnetization. Micromagnetics describe magnetization on a significant length scale which is large enough to replace atomic magnetic moments by a continuous function of position and smal enough to reveal the transitions between magnetic domains. The micromagnetics simulations are performed using a three-dimensional object-oriented micromagnetics framework (OOMMF) by solving the LandauLifshitz-Gilbert (LLG) equation as a function of time [15].

$$
\frac { d \overrightarrow { M _ { s } } } { d t } = \gamma \overrightarrow { M _ { s } } \times \overrightarrow { H } _ { e f } - \alpha \frac { \overrightarrow { M _ { s } } \times ( \overrightarrow { M _ { s } } \times \overrightarrow { H } _ { e f } ) } { M _ { s } }
$$

$$
H _ { \mathit { e f f } } = H _ { k } + H _ { \mathit { s h } }
$$

，where $M _ { s }$ is the magnetization and $\pmb { H } _ { \mathrm { e f f } }$ is the effective field taking into account the exchange, demagnetization field, anisotropic field and applied field terms. $\gamma$ is the Gilbert gyromagnetic ratio （204号 $( 2 . 2 1 { x } 1 0 ^ { 5 } ~ \mathrm { m } / ( \mathrm { A } . \mathrm { S } )$ ）and $\pmb { \alpha }$ is the damping constant. In this paper, $\pmb { \alpha }$ is set as 0.02 for the permeability simulations,and is set as 0.5 for the hysteresis loops simulations to save calculation time.The default parameters in OOMMF for an isolated FePt nanowire are taken in our simulations: saturation magnetization Ms is $1 . 1 4 \ x 1 0 ^ { 6 } \ \mathrm { A / m }$ ，exchange stiffness constant $\pmb { A }$ is （202 $1 { x } 1 0 ^ { - 1 1 }$ $\mathrm { J / m } ,$ ，magnetocrystallineanisotropyconstant ${ \pmb K } _ { 1 }$ is $6 . 6 x 1 0 ^ { 6 }$ $\mathrm { J } / \mathrm { m } ^ { 3 }$ [15].The magnetocrystalline anisotropy easy axis is along [Oo1] direction which is set parallel to the wire length.The initial magnetization is magnetized along the length direction of nanowire.The shape anisotropy constant $\pmb { K s }$ can be found as:

$$
K _ { s } = { \frac { 1 } { 2 } } \mu _ { 0 } \Delta N M _ { s } ^ { 2 }
$$

,where $\varDelta N$ is O.5 for a long cylindrical nanowire and is the demagnetization factor difference between the hard axis and the easy axis. The anisotropy field due to $\pmb { K } _ { I }$ or $\pmb { K s }$ can be calculated as: $H _ { k } = 2 K / ( \mu o M s ) .$ 、A cubic cell size of $2 \mathrm { n m } \times 2 \mathrm { n m } \times 2 \mathrm { n m }$ is adopted for all simulations. For comparisons,an isolated Fe nanowire is also simulated. The physical parameters for Fe are listed as: $M s = 1 . 7 \ x 1 0 ^ { 6 } \mathrm { A / m } .$ $\scriptstyle A = 2 . 1 \times 1 0 ^ { - 1 1 } { \mathrm { ~ J } } / { \mathrm { m } }$ $K _ { 1 } = 4 . 8 { \times } 1 0 ^ { 4 } \mathrm { J } / \mathrm { m } ^ { 3 }$ .Both FePt and Fe nanowires are 100 nm long with a diameter of $1 0 \ \mathrm { n m }$ to ensure strong shape anisotropy. To obtain the permeability spectra, we adopt the following procedures. Firstly, a remanent state is chosen as the equilibrium configuration of magnetizations,which is obtained by reducing the applied saturation magnetic field to zero. Secondly, a weak pulse magnetic field ( $\mathbf { \mathit { \Phi } } ( \mathbf { \mathit { h } } ( t ) = 5 0 \exp ( - 1 0 ^ { 1 1 } \mathrm { t } )$ ,where $\pmb { t }$ in seconds, $\pmb { h }$ in $\mathbf { A } / \mathbf { m } _ { , } ^ { \ast }$ is applied as a small perturbation to the equilibrium state. $\pmb { h } ( t )$ is perpendicular to the length direction of NWs. The dynamic responses of magnetization in time domain are recorded under perturbations.Finaly, the fast Fourier transform (FFT) approach is used to convert the recorded data into the data in frequency domain,and then the permeability spectra can be drawn. For the hysteresis loops simulations, the magnetic field $( H )$ is applied along the length and vary between （204号 $- 2 0 0 \ \mathrm { k O e }$ and $+ 2 0 0 \ \mathrm { k O e }$ for FePt nanowire, and vary between $- 4 0 \ \mathrm { k O e }$ and $+ ~ 4 0 ~ \mathrm { k O e }$ for Fe nanowire. The step size of $\pmb { H }$ field is $0 . 1 \mathrm { k O e }$

# 3.Results and discussions

Firstly,we have simulated the hysteresis loops,as shown in Fig.1,of single FePt nanowire and single Fe nanowire respectively. For these simulations, the external magnetic field is applied along the longitudinal direction. Clearly, both nanowires exhibit perfectly rectangular loops and indicate both have a strong shape anisotropy field. The easy magnetization direction is along the length of nanowire. The remanence (Mr/Ms) is equal to 1.O (see “A” point)，which will be a good equilibrium state for dynamic simulation (i.e. $\pmb { \mu } \sim \pmb { f } \cdot \$ ） because almost all magnetic moments' directions are along the same direction which will give rise to a strong response.The simulated coercivity value is $1 2 2 . 5 1 \mathrm { k O e }$ for FePt nanowire which is larger than the reported value $( 2 3 \mathrm { ~ k O e } )$ found in the bulk materials with multi magnetic domains and with very weak shape anisotropy field [16]. Same fact found in Fe nanowire: the simulated Hc is $1 0 . 6 5 \mathrm { k O e }$ ，which is much larger than the measured value（ $( 3 5 6 ~ \mathrm { O e } )$ of Fe nanowire array with millions of nanowires.Detailed explanations were given in our previous paper [17,18].

![](images/1d1800d1805723d646ad75c92632a62729432829fb12f42326cafcb8cf07dc86.jpg)  
Fig.1 Hysteresis loops of single FePt and Fe nanowire

Secondly，, the remanent state of FePt or Fe nanowire is illustrated in Fig.2. Clearly，each magnetization vector is pointing toward the longitudinal direction. No domain wall is found. For magnetic materials with multi domains, the frequency dependence of permeability will be dominated by the domain wall resonance frequency which is far below the natural resonance frequency. For instance,we have studied the resonance frequency of domain wall $( \pmb { f } _ { D W } )$ and natural resonance frequency $( f _ { r } )$ for NiZn spinel ferrite,and have revealed that $\mathbf { \Delta } f _ { D W }$ is lower than $\pmb { f } _ { r }$ by an order of magnitude [19].Therefore, it can be inferred that single magnetic domain structure is prerequisite to obtain obvious THz permeability for naturally synthesized magnetic materials with extremely large $\pmb { K }$ values shown in Table 1.

![](images/7bc41138189f341eb4f2c2511d0de47260e070944c187b02979fb89eabefdf78.jpg)

Fig. 2 Magnetization equilibrium configurations at remanent state of FePt NW When the remanent state (an equilibrium state） show in Fig.2 is used to study the dynamic magnetic responses, the complex susceptibility $( x ^ { - } x ^ { \prime } - j x ^ { \prime \prime } )$ can be defined as:

$$
\chi ( \omega ) = \frac { m _ { _ { y } } } { h _ { _ { y } } } _ { _ { \ \mathrm { ~ -- ~ } } } (
$$

Accordingly, the respective expression for the real parts ( $( \mu ^ { \prime } { = } I { + } \chi )$ and imaginary parts $( \mu ^ { \prime \prime } = \chi ^ { \prime \prime } )$ of permeability are given as below [20].

$$
\mu ^ { \prime } = 1 + { \frac { 1 } { D } } [ M \gamma ^ { 2 } H _ { 0 } ( \gamma ^ { 2 } H _ { 0 } ^ { 2 } - \omega ^ { 2 } ) + 2 \omega ^ { 2 } { \frac { \alpha ^ { 2 } } { \chi _ { 0 } } } ]
$$

$$
\mu ^ { \prime \prime } = \frac { 1 } { D } \alpha \omega ( \gamma ^ { 2 } H _ { 0 } ^ { 2 } + \omega ^ { 2 } ) _ { - }
$$

$$
\mathbf { D } = ( \gamma ^ { 2 } H _ { 0 } ^ { 2 } - \omega ^ { 2 } ) ^ { 2 } + 4 \omega ^ { 2 } \frac { \alpha ^ { 2 } } { \chi _ { 0 } ^ { 2 } }
$$

When the following condition is satisfied,the imaginary part of permeability $( \mu ^ { \prime \prime } )$ reaches a maximal value. When it happens, this physical phenomenon is termed as “natural resonance".

$$
\omega = \omega _ { 0 } = 2 \pi f _ { r } = \gamma H _ { 0 } \qquad \ldots ( 8 )
$$

The natural resonance frequency $( f r )$ can be calculated according to Eq.(8), in which $\mathbf { \nabla } _ { H \mathbf { \nabla } }$ is expressed as follows [20].

$$
H _ { \scriptscriptstyle 0 } = \sqrt [ 2 \pi f _ { r } ^ { \prime } ] _ { \gamma } = H _ { e f f } ( 1 + \frac { \alpha ^ { 2 } } { \gamma ^ { 2 } M ^ { 2 } } ) ^ { 1 / 2 } \approx H _ { e f f }
$$

Since the damping constant $( \pmb { \alpha } )$ is extremely small compared to the product of $\gamma$ and M, see above

Eqs.9.Ho can be approximately represented by Hef In other words, the natural resonance frequency $( f r )$ and the permeability spectrum can NOT be adjusted by controlling the damping constant, and only be possibly changed by controlling the effective anisotropic field $( H e f f )$ which can arise from Hk,Hshape,and (or) other sources,such as stress induced anisotropic field. The frequency dependence spectra of permeability are compared for both nanowires and shown in Fig.3a. Obviously, the natural resonance frequency of Fe nanowire is about $3 1 ~ \mathrm { G H z }$ and much smaller than that of FePt nanowire ( $\langle 3 4 8 \ \mathrm { G H z } = 0 . 3 4 8 \ \mathrm { T H z } \$ ). According to Eqs.(2,8 and 9), the calculated $f \mathbf { \hat { r } }$ value is 31.49 GHz and 0.344 THz for Fe and FePt nanowires respectively, which agree very well with the simulated values and corroborate that these observed peaks originating from the natural resonance phenomenon related to their Heff field. However,the shape anisotropy field $( H s h )$ plays an important role in enhancing $f \mathbf { \hat { r } }$ value of Fe nanowire, but it can be neglected in FePt nanowire because Hsh is much smaller than the magnetocrystalline anisotropy field (Hk). Therefore, only one natural resonance frequency is found in FePt. The other resonance peak found at $1 8 ~ \mathrm { { G H z } }$ is thought as the “edge mode". As indicated in Eq.(7), D is always a positive value. Hence, $\mu ^ { \prime \prime }$ is always a positive value (see Eq.6) since damping constant $( \pmb { \alpha } )$ is generally thought as a positive value to represent the energy dissipation during precession. Such a widely accepted fact $( \mu ^ { \prime \prime } > 0 )$ is found in the permeability spectrum of Fe nanowire as shown by the inset in Fig. 3a. However, the THz permeability of FePt shows something different: $\mu ^ { \prime \prime }$ firstly reaches a negative dip $( \mu ^ { \prime \prime } < 0 )$ and then jumps back to a normal positive peak at resonance frequency $( f r )$ .To interpret this abnormal behavior, we need to compare the precessons between Fe and FePt nanowires. As shown in Fig.3b， time dependence of $M z$ component of Fe nanowire “symmetrically” oscillates around the zero value, and finally reaches to a static state ( $\scriptstyle { M z = 0 }$ ）when the precession of Ms completely stops. For FePt nanowire, $M z$ firstly shows an “asymmetrical” Oscillation above zero value and then returns back to a normal symmetrical oscillation around zero. Putting the time dependence of $M z$ and $M \boldsymbol { y }$ together will be more useful to demonstrate the abnormal precession of FePt nanowire,as shown in Fig.4a. For Fe nanowire, both $M y ( \mathrm { t } )$ and $\pmb { M } \ o { z } { ( \mathrm { t } ) }$ follow the same precession behavior as shown by their overlapped time dependence curves in Fig.4h. For FePt nanowire. $M y ( \mathrm { t } )$ and $\pmb { M } \ o { z ( \mathrm { t } ) }$ are not overlanned at the heginning of nrecession.

![](images/69c8be2b0b93d65123d413ce7208b172755e8ae853814551e446f954472942cd.jpg)  
Fig.3 THz permeability of FePt nanowire and damping of magnetization component compared with Fe nanowire.

![](images/5c04b49906565059d6a3121103708187e2fd5f80f12a2d5b3565d4fb4b1c1f90.jpg)  
Fig.4 Damping behaviors of magnetization components of FePt and Fe nanowires.

By comparing the precession pattrns, the THz permeability of FePt nanowire is anticipated to be different from those of Fe nanowire. Under the excitation of external pulse magnetic field, the magnetization $( M )$ will deflect from its equilibrium direction with an angle (termed as “precession angle"） and start to precess around this direction (called Lamor precession). In our case, the effective anisotropy field direction is along the ‘ $\scriptstyle \mathbf { \dot { x } } ^ { \prime }$ axis direction.The other one torque is termed as “damping torque”, which is pointing toward to the circumference center of precession, and reduce the precession angle when the absorbed energy from external field is dissipated away. In other word, gradually decreasing precession angle denotes the positive damping constant, vice versa. The imagninary parts $( \mu ^ { \prime \prime } )$ of permeability representing the energy loss is therefore always positive for normal precession. From Eq. 6, the positive damping constant ensures the positive $\mu ^ { \prime \prime }$ values. Therefore,it is widely accepted as a natural law that $\mu ^ { \prime \prime }$ can NOT be negative for general physical scenarios. However, if the precession angle can be enlarged during an abnormal THz precession as shown in FePt nanowire, it is equivalent to have a negative damping constant and therefore it will result in a negative $\mu ^ { \prime \prime } .$ Negative $\mu ^ { \prime \prime }$ phenomenon has also been proposed by us in other paper for normal precession where the spin transfer torque of spin-poloarized current were used to enlarge the precession angle [21]. Furthermore，from the standing point of energy dissipation, when the external energy (e.g. spin transfer torque effect) is larger than the dissipated energy, it will result in an enlarged precession angle and an equivalently negative damping constant. Accordingly, negative $\mu ^ { \prime \prime }$ will be observed as per Eq.6. In addition, it should be noticed that the damping time of magnetization shown in Fig.4 is different for FePt and Fe nanowires. It is almost 10 times longer for Fe nanowire.

![](images/e90050576a2dba6a4bdbe36d8d03ecef619ba1b173ec6d94ac683d00f8fc8ba8.jpg)

Fig. 5 Variation of total Gibbs energy under perturbation of external magnetic field The differences in precession between FePt and Fe nanowire also can be viewed from the perspective of Gibbs energy $( E _ { t o t } )$ ,as shown in Fig. 5. When the normal nature resonance occurs, $E _ { t o t }$ has a sudden jump due to the energy coupled from the pulse magnetic field excitation, then $E _ { t o t }$ is dissipated by magnetic loss and the precession angle gradually decreases to zero. Hence, it gives rise to positive $\mu ^ { \prime \prime }$ values. However, several peaks of $E _ { t o t }$ are found for FePt,which means the precession angle is not gradually decreasing. At some moments, the angle is enlarged which can be inferred from the suddenly increased $\scriptstyle { E _ { t o t } }$ .As stated before,it is equivalent to have a negative damping $( \pmb { \alpha } )$ constant which will result in negative $\mu ^ { \prime \prime }$ values. Obviously, from the point 4 $\mathbf { \vec { \nabla } } D ^ { \prime }$ to the point $\ " { \mathbf { \nabla } } \mathbf { F } ^ { \prime }$ in Fig.5a, $E _ { t o t }$ gradually dissipates as normal, therefore, we observe a normal

positive $\mu ^ { \prime \prime }$ values again.

# 4. Conclusions

Under the remanent state (Mr/Ms) with 1.0, $\mathrm { L } 1 _ { 0 }$ -FePt nanowire with a large $\pmb { H _ { k } }$ value and a square M-H loop can exhibit an obvious THz permeability spectrum $( \mu \sim f )$ with a natural resonance frequency $( f _ { r } )$ of 0.348 THz. Below some frequency around $f _ { r } , \mu ^ { \prime \prime }$ is surprisingly found negative which is thought due to the abnormal precession behaviors and has been compared with an isolated Fe nanowire which shows normal precession behaviors.We believe that if the precession angle is enlarged during the Lamor precession,and it is equivalent to have a negative damping constant and therefore it will result in negative $\mu ^ { \prime \prime }$ values.

# Acknowledgments

This work is supported by National Science Foundation of China (NSFC, Grant No. 61271039).

# References

[1] Man-Gui Han, Electromagnetic Materials and Devices, published by IntechOpen, United Kingdom, 2020. https://doi.org/10.5772/intechopen.79786   
[2] V. G. Harris,"Modern Microwave Ferites", IEEE Trans. Magn., vol. 48,no.3, pp.1075-1104, March 2012, https://doi.0rg/10.1109/TMAG.2011.2180732   
[3] Koichi Haneda and Hiroshi Kojima,"Intrinsic coercivity of substituted BaFel2O19", Jpn. J. Appl. Phys., 12(1973)355. https://doi.0rg/10.1143/JJAP.12.355   
[4] Jiawei Cong，Binfeng Yun，and Yiping Cui, "Negative-index metamaterial at visible frequencies based on high order plasmon resonance"， Appl. Opt.,51 (2012)2469-2476. https://doi.0rg/10.1364/AO.51.002469   
[5] Atsushi Ishikawa, Shuang Zhang, Dentcho A. Genov, Guy Bartal, and Xiang Zhang,“ Deep Subwavelength Terahertz Waveguides Using Gap Magnetic Plasmon", Phys. Rev. Lett.，102, 043904(2009). https://doi.0rg/10.1103/PhysRevLett.102.043904   
[6] Xiaoyu Zhang, Yajie Chen, Lei Zhao, Yang Tan, Qiang Zhang, Chunlan Ma, and Vincent G. Harris, "Giant low-field tunability of THz transmission in patterned magnetic split-ring metastructures", Opt. Express,28,(2020)34035-34044. https://doi.0rg/10.1364/OE.409312 [7] R.H. Victora, Jianhua Xue and M. Patwari, "Areal density limits for perpendicular magnetic recording", IEEE Trans. Magn., Vol. 38, No. 5, (2002)1886-1891. https://doi.0rg/10.1109/TMAG.2002.802791.   
[8] S. Sun, C.B. Murray,D. Weller, L. Folksand, A. Moser, "Monodisperse FePt nanoparticles and Ferromagnetic FePt nanocrystal superlatices", Science, Vol. 287, Issue 5460 (2000)1989-1992. https://doi.org/10.1126/science.287.5460.1989.   
[9] David E. Laughlin, Kumar Srinivasan, Mihaela Tanase, Lisha Wang, "Crystallographic aspects of L10 magnetic materials", Scripta Materialia,Vol. 53， Issue 4 (2005)383-388. https://doi.0rg/10.1016/j.scriptamat.2005.04.039.   
[10] Alexander B. Shick and Oleg N. Mryasov, "Coulomb correlations and magnetic anisotropy in orderedL10CoPtandFePtalloys"，Phys.Rev.B，67(2002)172407. https://doi.0rg/10.1103/PhysRevB.67.172407   
[11] R. Wood,"The feasibility of magnetic recording at 1 Terabit per square inch", IEEE Trans. Magn., Vol. 36,No. 1,(2000) pp. 36-42, htps://oi.0rg/10.1109/20.824422   
[12]C. Chinnasamy, M. M. Jasinski,A. Ulmer, W. Li, G. Hadjipanayis and J. Liu, "Mn-Bi Magnetic Powders With High Coercivity and Magnetization at Room Temperature", IEEE Trans. Magn., 48(2012)3641-3643. https://doi.0rg/10.1109/TMAG.2012.2201146   
[13] Till Burkert, Lars Nordstrom, Olle Eriksson, Olle Heinonen， "Giant magnetic anisotropy in tetragonal FeCoalloys"，Phys.Rev.Lett. 93 （2） (2004) 027203. https://doi.0rg/10.1103/PhysRevLett.93.027203   
[14] M. Kotsugi, H. Maruyama, N. Ishimatsu, N. Kawamura, M. Suzuki,M. Mizumaki, K. Osaka, T. Matsumoto, T. Ohkochi, T. Ohtsuki, T. Kojima, M. Mizuguchi, K. Takanashi and Y. Watanabe, "Structural， magnetic and electronic state characterization of L10-type ordered FeNi alloy extracted from a natural meteorite",J. Phys. Condens. Matter.， 26 (6) (2014） 064206. https://doi.0rg/10.1088/0953-8984/26/6/064206   
[15] H. Kronmuler, M. Fähnle, (2003) Magnetism and the Microstructure of Ferromagnetic Solids ( $1 ^ { \mathrm { s t } }$ ed.). Cambridge, Cambridge University Press. http://hdl.handle.net/11858/00-001M0000-0010-2F17-C   
[16] Y. K. Takahashi, T. O. Seki, K. Hono, T. Shima and K. Takanashi, "Microstructure and magnetic properties of FePt and Fe/FePt polycrystalline films with high coercivity",J. Appl. Phys. 96, 475 (2004). https://doi.0rg/10.1063/1.176688   
[17] Mangui Han,"Ultra high frequency properties of periodically ordered Fe nanowires",J.

Magn. Magn. Mater., Vol. 527(2021)167704. https://doi.0rg/10.1016/j.jmmm.2020.167704

[18] D.J. Sellmyer, M. Zheng,R. Skomski, "Magnetism of Fe, Co and Ni nanowires in selfassembled arrays",J.Phys.:Condens. Matter. 13 (2001) R433-R460. https://doi.0rg/10.1088/0953-8984/13/25/201   
[19] Mangui Han, Difei Liang, and Longjiang Deng, "Analyses on the dispersion spectra of permeability and permitivity for NiZn spinel ferrites doped with SiO2", Appl. Phys. Lett. 90, 192507(2007). https://doi.0rg/10.1063/1.2722703   
[20] Guo Yi Cheng, Ferromagnetism,Peking University Press, 2014.   
[21] Mangui Han, Wu Zhou, "Unusual negative permeability of single magnetic nanowire excited by the spin transfer torque efect", J. Magn. Magn. Mater， Vol. 457(2018)52-56. https://doi.0rg/10.1016/j.jmmm.2018.02.031

# Supplementary information FIGURES

![](images/6bfbd53a7f67333506b56f4e34b0c7274b6b3f11f1b6407690cb19372398d3ed.jpg)  
(FIG. 1)

![](images/924b93170ebe8e1d9042f87fb52061e0d4b1cc331aebd1c0185fff7c2779f554.jpg)

![](images/dbf15914b110868f71493ec4d22703f31b8ac66fa43fbe1c5ac1412964b2df6d.jpg)

![](images/536db0dddf00bfbf2f1d1f1a1ba644a4931313995b0136120bc37581738ca281.jpg)