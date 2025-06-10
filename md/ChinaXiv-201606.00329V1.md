# Probing CP Violation in $h  \gamma \gamma$ with Converted Photons

Fady Bishara, ${ 1 , 2 }$ ,\* Yuval Grossman,3,† Roni Harnik $^ 2$ $\ddagger$ （20   
Dean J. Robinson, $4 , 5 , \ S$ Jing Shu,6, and Jure Zupan $^ { 1 }$ ，\*\*   
（20 $^ { 1 }$ Department of Physics， University of Cincinnati,   
Cincinnati, OH 45221,USA   
（20 $^ 2$ Theoretical Physics Department， Fermilab,   
P.O. Box 500， Batavia, IL 60510   
（204号 $^ 3$ Department of Physics， LEPP, Cornell University,   
Ithaca， NY 14853， USA   
（20 $^ 4$ Department of Physics， University of California,   
Berkeley， CA 94720， USA   
（20 $^ { 5 }$ Ernest Orlando Lawrence Berkeley National Laboratory,   
University of California， Berkeley， CA 94720， USA   
（20 $^ 6$ State Key Laboratory of Theoretical Physics and Kavli Institute for Theoretical Physics   
China (KITPC)， Institute of Theoretical Physics， Chinese Academy of Sciences,   
Beijing 100190， P. R. China   
(Dated: November 11, 2015)

Abstract

We study Higgs diphoton decays, in which both photons undergo nuclear conversion to electronpositron pairs. The kinematic distribution of the two electron-positron pairs may be used to probe the CP violating (CPV) coupling of the Higgs to photons,that may be produced by new physics. Detecting CPV in this manner requires interference between the spin-polarized helicity amplitudes for both conversions. We derive leading order,analytic forms for these amplitudes. In turn， we obtain compact, leading-order expressions for the full process rate. While performing experiments involving photon conversions may be challenging， we use the results of our analysis to construct experimental cuts on certain observables that may enhance sensitivity to CPV. We show that there exist regions of phase space on which sensitivity to CPV is of order unity. The statistical sensitivity of these cuts are verified numerically, using dedicated Monte-Carlo simulations.

# CONTENTS

I. Introduction 4

II. Higgs diphoton decay with CP violation 7

A. Motivation for measuring CP-violation in di-photons 7   
B.Helicity interference 9   
C.A thought experiment with polarizers 10

[I. Bethe-Heitler photon conversion 12

A.Photon propagation and conversion 12   
B. Angular resolution limitations 13   
C. Nuclear form factor 15

IV. The Higgs-Bethe-Heitler process 16

A. Amplitude and cross-section 16   
B. Helicity structure 18   
C. The Bethe-Heitler helicity amplitudes 20

V. Sensitivity to CPV 22

A. Differential scattering rate 23   
B. Global sensitivity to CP violation 23   
C. Differential azimuthal scattering rate 25   
D. CPV enhancing cuts 27   
1. Cuts on collective kinematics 28   
2. Cuts on individual photon conversions 29   
3.Cut scheme efficiencies 32   
E. Triple products 33   
VI. Conclusion 35   
Acknowledgments 36   
A. Spinor-helicity formalism 37   
B.BH spin-helicity amplitudes 39   
C. Polarization-decomposed HBH rate 41   
D.Numerical simulations of Bethe-Heitler conversion 42   
E. Analysis for qq → γγ 44   
F. Monte Carlo numerical schemes 46   
References 48

# I. INTRODUCTION

The recent discovery of a Higgs-like boson [1, 2] has prompted intense interest in the precise measurement of its couplings and properties. Such measurements are a direct probe of new physics (NP) beyond the Standard Model (SM), especially since many extensions of the SM modify the Higgs couplings to gauge bosons and fermions.

Of particular interest is a search for parity and CP violating Higgs decays, since these would be a clear signal of NP [3-20]. In Higgs decays to vector bosons the CP violating effects can only be due to irrelevant NP operators. Fortunately, in the SM $h  \gamma \gamma$ (and （20 $h  Z \gamma$ ） decays are also due to irrelevant operators, with the first non-zero contribution occurring at one-loop. Thus we can expect large CP violating effects from weak scale NP in $h  \gamma \gamma$ . In contrast, the $h \to Z Z ^ { * }$ and $h \to W W ^ { * }$ decays proceed in the SM through relevant tree-level operators tightly related to the $Z$ and $W$ masses. CP violating effects from NP are expected to be comparatively small in these decay modes.

In the presence of CPV, the total $h  \gamma \gamma$ decay rate must be proportional to the sum of squares of CP-even and CP-odd terms - i.e |CPeven|2+|CP $_ \mathrm { o d d } | ^ { 2 }$ - and therefore, by comparing the $h  \gamma \gamma$ rate to the SM expectation, one may probe for NP directly. However, this type of search cannot distinguish between CP-even and CP-odd NP contributions to the total rate. Moreover if the CP-odd contribution is small, then CPV signals are quadratically suppressed, and if it so happens that NP enters both the CP even and odd terms,such that the total $h  \gamma \gamma$ rate matches the SM expectation， then one cannot detect NP at all. Probing the differential $h  \gamma \gamma$ rate for CPV ameliorates these problems. In the first instance, the differential rate may feature an interference term of the form 2CP $\mathbf { \ e v e n }$ CPodd. Combined with non-interfering terms,one may distinguish CP-even and CP-odd NP contributions.

![](images/cf7a0306f2c188d06ff39ee48037c397b497ba88a652de3f2c0449121118a87f.jpg)

FIG. 1. An illustration of an example of a CPV sensitive observable in $h  \gamma \gamma  4 e$ .The Higgs decays to on-shel photons which convert in the detector. The distribution of the azimuthal angle $\varphi$ between the two planes formed by each positron and its parent photon depends on the Higgs couplings to CP even and odd operators. The electrons do not need to be co-planar with the corresponding photon-positron planes. The positron-photon plane is shown in magenta and the electron-photon plane in blue. For further details and subtleties see the main text.

Secondly, small CPV signals are only linearly suppressed in this interference term.

The $h  \gamma \gamma$ phase space distribution alone, however, is not sensitive to CP violating effects，since the Higgs decays isotropically to two photons. Nevertheless, the underlying CPV structure in the differential $h  \gamma \gamma$ rate may be determined if one is able to measure the linear polarizations of the outgoing photons.This in itself is an old idea, first proposed for the determination of the $\pi ^ { 0 }$ parity [21-23] and, more recently, to probe NP effects in radiative $B$ decays [24]. It relies on the fact that a spin-O particle decays to either two positive or two negative helicity photon states,which acquire a relative CPV phase in the presence of non-trivial CP structure. The linearly polarized photon states are a superposition of both helicities,permiting one to extract this CPV phase. It is not feasible to directly measure the linear polarization of $\mathcal { O } ( 6 0 ~ \mathrm { G e V } )$ photons from Higgs decay. However, in both the ATLAS [25] and CMS [26] detectors roughly half of the photons from Higgs decays convert via the well-known Bethe-Heitler (BH） process into $e ^ { + } e ^ { - }$ pairs inside the silicon tracker. This has an important benefit: the orientation of the produced $e ^ { + } e ^ { - }$ pairs encodes the underlying CP structure. Figure 1 illustrates an observable expected to be sensitive to CPV.

Previous proposals to measure CPV in $h  \gamma \gamma$ ，or in other neutral meson diphoton decays,via double photon conversion appear in Refs. [3,23, 27]. We extend these studies by performing an analysis of the actual manner in which the leptonic phase space encodes the CP violating efects. We examine the encoding of CPV in the doubly converted Higgs diphoton decay- hereafter the Higgs-Bethe-Heitler (HBH) process -both analytically and numerically, making use of the spinor-helicity formalism to obtain compact expressions for the full differential scattering rate and its leading order terms.

A key difficulty in extracting CPV signals from differential scattering rates like $d \Gamma / d \varphi$ ， defined in Fig. 1, is that the signal is largely washed out under integration over the other phase space variables. However, in this work we use our analytic control of the full differential scattering rate to show that large CPV signals may be achieved. We find certain observables exhibit $\mathcal { O } ( 1 )$ sensitivity to CP violating effects on small regions of the phase space, corresponding to a small fraction of the converted decays. These regions are identified by sensitivity parameters, derived from our analysis. We show analytically and confirm numerically that if one cuts the HBH event data according to these sensitivity parameters, the CPV signal is dramatically improved.

Performing such an experiment will be diffcult. For example,one must resolve the opening angles in the photon conversion， and this requires extremely accurate tracking resolution. Other subtle efects,such as soft scatterings of the electron and positron in the detector material need also to be examined. In addition, reaching a sensitivity to Higgs couplings would require obtaining a signal-rich sample of $h  \gamma \gamma$ events. Our approach here is to defer these considerations to future work, and consider mainly the theoretical aspects of this process. In doing this,our intent is to motivate a very challnging measurement, perhaps to be done after the LHC upgrade or in a future Higgs factory. We note however, that as a warm-up to Higgs studies, photon conversions can be studied in background samples as a test of the standard model (we present the phase space structure of $q q  \gamma \gamma$ with converted photons in an appendix).

This paper is structured as follows. In Section II we frst present a motivating phenomenological analysis of the expected size of CP violation in Higgs decays, followed by an analysis of the unconverted $h  \gamma \gamma$ process. This is presented in the language of helicity amplitudes and we show that the CPV terms in the differential rate arise from helicity amplitude interference. In Section II we discuss photon propagation and conversion in modern detectors,angular resolution limits,and the central role of the nuclear form factor in Bethe-Heitler conversion. In Section IV we then proceed to examine the HBH process itself, presenting explicit results within the spinor-helicity formalism for the leading order HBH square amplitude. This is followed in Section V by a derivation of CPV observables and their sensitivity parameters for the special case that the Higgs is at rest. These sensitivity parameters can be used as cuts, which extract the phase space regions on which we expect （20 $\mathcal { O } ( 1 )$ CPV effects. Numerical simulations are presented which confirm these expectations, and further compare the performance of the various sensitivity parameter cuts. In this work we focus on the $h  \gamma \gamma$ decay, but our analysis can be used to examine other searches, e.g., for $h  Z \gamma$ or other decays involving converted photons.

# II. HIGGSDIPHOTONDECAYWITH CPVIOLATION

# A. Motivation for measuring CP-violation in di-photons

The CP structure of Higgs decays was already studied experimentally in $h \to Z Z ^ { * }$ decays [28, 29],with pure pseudo-scalar coupling disfavored at more than $3 \sigma$ [29]. Still, there is strong motivation to measure CPV also in loop induced $h  \gamma \gamma$ decays. The motivation is based on the expected sizes of CP violating and CP conserving terms in $h  \gamma \gamma$ and （204号 $h \to Z Z ^ { * }$ decays. After electroweak symmetry breaking (EWSB),the relevant terms in the effective Lagrangian at the scale $\mu \simeq m _ { h } / 2$ are

$$
\begin{array} { l } { { \displaystyle { \mathcal { L } } _ { \mathrm { e f f } } \supset c _ { V } \frac { m _ { Z } ^ { 2 } } { v } h Z ^ { \mu } Z _ { \mu } + c \frac { \alpha } { \pi v } h F _ { \mu \nu } F ^ { \mu \nu } + c _ { Z Z } \frac { \alpha } { \pi v } h Z ^ { \mu \nu } Z _ { \mu \nu } } } \\ { { \displaystyle ~ + \tilde { c } _ { Z Z } \frac { \alpha } { 2 \pi v } h Z _ { \mu \nu } \tilde { Z } ^ { \mu \nu } + \tilde { c } \frac { \alpha } { 2 \pi v } h F _ { \mu \nu } \tilde { F } ^ { \mu \nu } , } } \end{array}
$$

in which $F _ { \mu \nu }$ and $Z _ { \mu \nu }$ are respectively the photon and $Z$ field strengths, and $\tilde { X } ^ { \mu \nu } = \epsilon ^ { \mu \nu \alpha \beta } X _ { \alpha \beta }$ ， （204号 $\epsilon ^ { 0 1 2 3 } = 1$ ，while $v = 2 4 6$ GeV is the Higgs vev. Taking Higgs to be a scalar,the first line of Eq.(1） contains CP even and the second line CP odd operators.1 Present data imply （20 $c _ { V } = 1 . 0 4 \pm 0 . 1 3$ [30],assuming CP conservation. If either $\tilde { c } _ { Z Z }$ or $\tilde { c }$ are found to be nonzero,² CPV in Higgs couplings and thus NP will be discovered. The couplings $c$ and $\tilde { c }$ arise at one-loop in perturbative UV theories,and can be at most $\mathcal { O } ( 1 )$ in order to agree with the observed $h  \gamma \gamma$ rate. For example, $\tilde { c }$ can arise from a massive NP fermion loop that is axially coupled to the Higgs. Note that in Eq. (1） we integrated out both $W$ and $t$ loop contributions to $c$ ，so that $c _ { \mathrm { S M } } = - 0 . 8 1$ in the SM. Similarly, the dimension 5 couplings of Higgs to $Z Z$ ， $c _ { Z Z }$ and $\tilde { c } _ { Z Z }$ ，also arise at one-loop order. In generic NP models we thus expect $c \sim c _ { Z Z }$ and $\tilde { c } \sim \tilde { c } _ { Z Z }$

The $h \to Z Z ^ { * }$ decay is dominated by the CP even renormalizable coupling $c _ { V }$ ,while the （204号 $h  \gamma \gamma$ decay is given by higher dimensional operators. The relative size of CP violating effects in any channel is given by the ratio of the interference terms to the total amplitude squared. For $h \to Z Z ^ { * }$ the CP odd interference term is proportional to $( \alpha / 2 \pi ) \tilde { c } _ { Z Z } c _ { V }$ ，while the total squared amplitude is dominated by $c _ { V } ^ { 2 }$ . The typical size of CPV observables in （20 $h \to Z Z ^ { * }$ is therefore set by the ratio of the two,

$$
r _ { Z Z ^ { * } } = \frac { \alpha } { 2 \pi } \frac { \tilde { c } _ { Z Z } } { c _ { V } } \sim \mathcal { O } ( 1 0 ^ { - 3 } ) ,
$$

for $\mathcal { O } ( 1 )$ couplings. In the diphoton channel both terms are loop suppressed and the figure of merit for CP violation is

$$
r _ { \gamma \gamma } = \frac { c \tilde { c } } { c ^ { 2 } + \tilde { c } ^ { 2 } } \sim \mathcal { O } ( 1 ) ,
$$

again assuming $\mathcal { O } ( 1 )$ couplings. As will become clear, the measurement of CPV in $h  \gamma \gamma$ （20 is a challenging one, especially in comparison to the relatively straightforward measurement in $h \to Z Z ^ { * }$ . However, the expected size of the effect may partially compensate for this.

In addition to the CPV observables discussed in this paper, the CPV operator in Eq. (1) also modifies the overall $h  \gamma \gamma$ decay rate, so that

$$
\mu _ { \gamma \gamma } \equiv \frac { \Gamma ( h \to \gamma \gamma ) } { \Gamma ( h \to \gamma \gamma ) _ { \mathrm { S M } } } = \frac { c ^ { 2 } + { \tilde { c } } ^ { 2 } } { c _ { \mathrm { S M } } ^ { 2 } } ~ ,
$$

where $\Gamma ( h \to \gamma \gamma ) _ { \mathrm { S M } }$ is the SM rate. The total rate is only quadratically sensitive to CP violating NP because the interference terms integrate to zero over phase space.In contrast, the differential rates contain CP odd terms proportional to $c \tilde { c }$ and thus may be linear in the NP coupling. This can lead to substantial increase in sensitivity for small $\tilde { c }$

Before proceeding, two remarks are in order. First, it is important to mention that there are severe constraints on $y _ { e } \tilde { c }$ from bounds on the electric dipole moment of the electron [32- 34]. Taking the electron yukawa, $y _ { e }$ , to be the SM one, this gives $\tilde { c } \lesssim 1 0 ^ { - 3 }$ . These bounds are, however,absent in the limit where the 125 GeV Higgs does not couple to electrons (for other possibilities in concrete UV models, see [32, 35]). A strong motivation for contemplating a non-zero value of $\tilde { c }$ is, for instance, that it would be generated by new CP sources in models that lead to electroweak baryogenesis, see e.g.,， [35]. An independent measurement of $\tilde { c }$ is thus desirable.

Second,we assumed here that $c$ and $\tilde { c }$ are real. In the SM $c$ obtains its dominant contribution from a $W$ loop and a smaller destructive contribution from a top quark loop. However, there is also a smaller contribution from $b$ quark and light quarks. These can go on-shell in the loop, generating complex effective couplings $c$ and $\tilde { c }$ . This means that $c$ and $\tilde { c }$ obtain a relative strong phase. The result of such a strong phase, when combined with the weak phase, would be to induce direct CPV in decay, such that the decay rate of the Higgs into two positive helicity photons is not the same as into two negative ones. These strong phases are of $\sim \mathcal { O } ( 1 \% )$ in the SM [36, 37], and we assume the strong phases are similarly small for NP effects. Consequently, we neglect direct CPV, and assume that $c$ and $\tilde { c }$ are real.

# B． Helicityinterference

We proceed to examine the unconverted $h  \gamma \gamma$ process. The effective operator mediating $h  \gamma \gamma$ decay has the general form, cf. Eq. (1),

$$
{ \mathcal H } _ { \mathrm { e f f } } = - c \frac { \alpha } { \pi v } h F _ { \mu \nu } F ^ { \mu \nu } - \frac { \tilde { c } } { 2 } \frac { \alpha } { \pi v } h F _ { \mu \nu } \tilde { F } ^ { \mu \nu } \ .
$$

For a Higgs that is a scalar,the first term is CP even and the second is CP odd. CP is therefore violated if the CP phase

$$
\xi \equiv \tan ^ { - 1 } ( \tilde { c } / c ) \ ,
$$

is found to be non-zero.

The $h  \gamma \gamma$ helicity amplitudes are (dropping the overall $\alpha / \pi v$ factor, cf. Eq. (5))

$$
\begin{array} { r l } { M ^ { \lambda _ { 1 } \lambda _ { 2 } } = } & { \cdots \cdots \cdots \widetilde { \gamma } _ { \mathcal { N } } ^ { \mathcal { N } ^ { \lambda _ { 1 } } } } \\ & { } \\ & { = c \Big [ ( k _ { 1 } \cdot k _ { 2 } ) \big ( ( \varepsilon _ { 1 } ^ { \lambda _ { 1 } } ) ^ { * } \cdot ( \varepsilon _ { 2 } ^ { \lambda _ { 2 } } ) ^ { * } \big ) - \big ( k _ { 1 } \cdot ( \varepsilon _ { 2 } ^ { \lambda _ { 2 } } ) ^ { * } \big ) \big ( k _ { 2 } \cdot ( \varepsilon _ { 1 } ^ { \lambda _ { 1 } } ) ^ { * } \big ) \Big ] + \widetilde { c } \epsilon \big [ k _ { 1 } , ( \varepsilon _ { 1 } ^ { \lambda _ { 1 } } ) ^ { * } , k _ { 2 } \big ] } \end{array}
$$

where $k _ { i }$ are the photon momenta, $\varepsilon _ { i } ^ { \lambda _ { i } }$ is the polarization vector of the $i$ th photon ( $( i = 1 , 2$ ） with helicity $\lambda _ { i } = \pm$ ，and $\epsilon [ p , q , r , s ] \equiv p _ { \mu } q _ { \nu } r _ { \rho } s _ { \sigma } \epsilon ^ { \mu \nu \rho \sigma }$ . A Latin subscript $i = 1 , 2$ hereafter

denotes the corresponding photon. To compute helicity amplitudes we employ the spinorhelicity formalism, see Appendix A for our conventions and a brief review. Using Eqs. (A5), (A6) and (A1O), one finds that the non-zero helicity amplitudes are

$$
\mathcal { M } ^ { \pm \pm } = m _ { h } ^ { 2 } ( c \pm i \tilde { c } ) = m _ { h } ^ { 2 } \sqrt { c ^ { 2 } + \tilde { c } ^ { 2 } } e ^ { \pm i \xi } \ ,
$$

while $\mathcal { M } ^ { \pm \mp } = 0$ as expected from angular momentum conservation (cf. also the results of, e.g.，[38, 39] for $h  Z Z$ ). We see that CPV introduces a relative phase, $\xi$ ，between the two-photon helicity amplitudes. Furthermore,a differential rate may depend on $\xi$ if and only if there is interference between $\mathcal { M } ^ { + + }$ and $\mathcal { M } ^ { -- }$ , or more precisely, between amplitudes involving the $^ { + + }$ and $--$ photon helicity configurations. We call such interference helicity interference.

Let us now translate Eq. (8) into a Hilbert space language. The final states of $h  \gamma \gamma$ （204号 decay are the two-photon states $| + + \rangle$ and $| - - \rangle$ ，with $\pm$ indicating the helicity of each photon, so that $\mathrm { C P } | { \pm \pm } \rangle = | \mp \mp \rangle$ . Eq. (8) then translates to

$$
\mathcal { H } _ { \mathrm { e f f } } | h \rangle \propto \sqrt { c ^ { 2 } + \tilde { c } ^ { 2 } } \Big ( e ^ { i \xi } | { + + } \rangle + e ^ { - i \xi } | { - - } \rangle \Big ) ~ .
$$

As above, the CP phase $\xi$ appears as a relative phase between the $| + + \rangle$ and $| -- \rangle$ terms. Now, the total rate for $h  \gamma \gamma$ decay is proportional to

$$
\sum _ { f = + + , -- } | \langle f | { \mathcal { H } } _ { \mathrm { e f f } } | h \rangle | ^ { 2 } = \sum _ { f = + + , -- } | { \mathcal { M } } ^ { f } | ^ { 2 } ~ .
$$

Orthogonality of $| + + \rangle$ and $| - - \rangle$ ensures that the total rate is independent of $\xi$ , i.e., there is no helicity interference. In contrast,any experiment for which the final state is a linear superposition of the two helicity states would generate helicity interference. This is the case at collider experiments in which the on-shell photons with definite helicity are intermediate states: The final state is a converted photon - an $e ^ { + } e ^ { - }$ pair with a particular set of momenta - which has non-vanishing overlap with both helicities.

# C. A thought experiment with polarizers

The overlap of each photon helicity with a BH pair will determine the strength of helicity interference and our ultimate sensitivity to the Higgs CP properties. The details at the

![](images/4f08ba256390c508677e3031810a0ed1ef99c6e80a415bd84f633f983086f34b.jpg)

FIG.2.A linear polarization thought experiment in Higgs rest frame. $\mathcal { P } _ { 1 , 2 }$ are linear polarizers oriented orthogonal to the photon momentum direction. The angle $\phi$ is measured between the linear polarization vectors εl,2.

level we need are quite involved, and will be described in Sec. IV.As a warm-up we instead consider a thought experiment in which we can measure linearly polarized photons.

Let us imagine that we have been able to manufacture a linear polarizer for gamma rays. We produce a Higgs at rest between polarizers $\mathcal { P } _ { 1 }$ and $\mathcal { P } _ { 2 }$ ，such that each photon travels through a polarizer (see Fig. 2） before being absorbed by a detector that counts photons. The polarizer $\mathcal { P } _ { i }$ ( $i = 1 , 2$ ） projects an incoming photon onto a linearly polarized state, $| \phi _ { i } \rangle = e ^ { - i \phi _ { i } } | + \rangle + e ^ { i \phi _ { i } } | - \rangle$ , that has polarization oriented at angle $\phi _ { i }$ . From Eq.(9) the amplitude of the two-photon wave function observed by the detectors is

$$
\left( e ^ { i \phi } \langle + | + e ^ { - i \phi } \langle - | \right) _ { 2 } \otimes \left( \langle + | + \langle - | \right) _ { 1 } { \mathcal { H } } _ { \mathrm { e f f } } | h \rangle \sim \sqrt { c ^ { 2 } + \widetilde { c } ^ { 2 } } \cos ( \phi + \xi ) \ ,
$$

where $\phi = \phi _ { 1 } - \phi _ { 2 }$ is a relative azimuthal angle between the two polarizers. As the angle $\phi$ （20 is changed, the differential rate in the detectors changes as $\cos ^ { 2 } ( \phi + \xi )$ . One finds

$$
\frac { d \Gamma } { d \phi } = \frac { 2 } { \pi } \Gamma _ { h  \gamma \gamma } \cos ^ { 2 } ( \phi + \xi ) ~ , \qquad \Gamma _ { h  \gamma \gamma } = \frac { \alpha ^ { 2 } } { 4 \pi ^ { 3 } } \frac { m _ { h } ^ { 3 } } { v ^ { 2 } } ( c ^ { 2 } + \tilde { c } ^ { 2 } ) ~ .
$$

Note that the CP odd term in the differential rate (12) is proportional to $\sin 2 \xi \sin 2 \phi \ \propto$ $c \tilde { c } \sin 2 \phi$ . The differential rate is thus linearly sensitive to CPV coupling $\tilde { c }$ , whereas the total rate is quadratically sensitive.

In summary, we have shown that only the terms receiving contributions from both of the definite helicity two-photon amplitudes,so that there is helicity interference,are sensitive to the CPV phase $\xi$ . These interference effects can in principle be of $\mathcal { O } ( 1 )$ in size.

![](images/0c4308052cfd36d411cb5c13a5d0917319eed69a8437477d949a20d1434cf89b.jpg)

FIG.3. The contributions to photon cross-section on $^ { 2 8 }$ Si, $\sigma _ { \gamma } ( ^ { \mathrm { 2 8 } } \mathrm { S i } )$ ,from BH $e ^ { + } e ^ { - }$ pair production in nuclear field (solid blue line), pair production due to scattering on electron cloud (red dashed), Compton scattering (dot-dashed yellow) and Rayleigh scattering (magenta double dot-dashed), as a function of photon energy $E _ { \gamma }$ . Calculated using NIST's XCOM database [40].

# III. BETHE-HEITLERPHOTON CONVERSION

We now study the process that can be used for photon polarization measurement, namely the conversion of a photon into an $e ^ { + } e ^ { - }$ pair in matter. In this section we study a conversion of single isolated photon, which we will then use in the Sec. IV for the case of $h  \gamma \gamma$ with converted photons.

# A． Photon propagation and conversion

Photon conversion to $e ^ { + } e ^ { - }$ pairs may proceed either by Dalitz conversion in vacuum, for an of-shell intermediate photon, or by BH conversion on atomic nuclei, which occurs for on-shell photons (for a review see, e.g., [41, 42]). The Dalitz conversion rate carries a suppression factor of $\mathcal { O } ( 1 0 ^ { - 4 } )$ , and is not of immediate practical interest. Moreover it mainly proceeds via a longitudinal photon so that the above helicity analysis no longer applies. In contrast, the CMS and ATLAS pixel detectors contain a significant amount of material, so that $\sim 5 0 \%$ of photons convert inside the tracking systems via the BH process [43,44]. Based on the composition of the detectors, we assume in this work that the target nucleus is always $^ { \cdot 2 8 }$ Si, at rest in the laboratory frame. This nucleus is spin-O,and has no nuclear

![](images/a16524948dca48b42d609985f5ba344da3c7908e0bd9ba844133cd74a85bf3de.jpg)

FIG. 4. Cumulative distributions of Bethe-Heitler conversion cros-section for a photon with （20 $E _ { \gamma } = 6 0$ [GeV] scattering on a $^ { \mathrm { 2 8 } }$ Si nucleus, with respect to various opening angle cuts. Three distributions are shown: $P ( \theta _ { \ell \ell } > \theta _ { \mathrm { c u t } } )$ , i.e. with photon-lepton opening angles, $\theta _ { \pm }$ , unconstrained (blue line); $P ( \theta _ { + }$ and $\theta _ { \ell \ell } > \theta _ { \mathrm { c u t } }$ ）with electron-photon opening angle $\theta _ { - }$ unconstrained (red dashed line); $P ( \theta _ { \pm }$ and $\theta _ { \ell \ell } > \theta _ { \mathrm { c u t } }$ ） (black dot-dashed line).

magnetic moment.We therefore do not consider the effects of target polarization on the BH process [45].

One might be concerned by the prospect of photon polarization decoherence for the photons propagating inside the silicon. However, at photon energies $\sim \mathcal { O } ( m _ { h } / 2 )$ the pair production in the nuclear field is by far the largest contribution to the photon scattering cross-section in an atomic lattice [46], see Fig. 3. As a result, to an excellent approximation, the photons remain coherent up until their BH conversion. We shall also assume that the BH scattering is quasi-elastic, i.e. that the target nucleus remains in a coherent state during and after the scattering. For the kinematics considered, the quasi-elastic limit is an excellent approximation of the full BH conversion [41, 42].

# B. Angular resolution limitations

Following the $h  \gamma \gamma$ experiment discussed in Sec. IC, in order to measure the CPV in a doubly converted $h  \gamma \gamma$ decay, we might expect that angular distributions between planes formed by spatial momenta need to be measured. There are several possible planar distributions that can be constructed, involving either:

1. The $e ^ { + } e ^ { - }$ plane formed by the $e ^ { + } e ^ { - }$ momenta, or;   
2. The $\gamma e ^ { \pm }$ plane formed by a lepton and its parent photon, as in Fig. 1.

The first requires resolving the orientation of the leptonic spatial momenta. The second requires the orientation of the leptons with respect to their parent photon,which could be achieved by identifying the vertex associated with the Higgs (from other tracks in the event) as well as the location of the photon conversion， giving the photon direction.

Such measurements require exquisitely precise tracking. Because the momentum transfer to the nucleus is small, the relative angular orientations between the photon and leptons are tiny in typical photon conversion: for mass $m$ and energy $E$ , the angular scale is typically （20 $m / E \sim 1 0 ^ { - 5 }$ for a 60 GeV photon conversion to electrons. There is however a distribution for these angles. In the limit of very large statistics one can hope to get a sample of events where these angles can be measured.

In the ATLAS detector, for instance, the intrinsic accuracy in silicon pixels located between 5cm and 12 cm from the interaction point is $1 0 \mu m$ in $R - \phi$ direction and 115μm in （204号 $z$ direction. The intrinsic accuracy of SCT strips located between 30cm to 5lcm from the interactions point is 17μm $( R - \phi )$ and $5 8 0 \mu m ( z )$ [47]. One may therefore hope to measure the orientations of the $e ^ { + } e ^ { - }$ plane even for opening angles as small as $\theta _ { \ell \ell } \sim 1 0 ^ { - 4 } - 1 0 ^ { - 3 }$ ， where the relative leptonic angle $\theta _ { \ell \ell }$ is defined by

$$
\cos \theta _ { \ell \ell } = \frac { \pmb { p } _ { + } \cdot \pmb { p } _ { - } } { | \pmb { p } _ { + } | | \pmb { p } _ { - } | } \mathrm { ~ , ~ }
$$

for leptonic spatial momenta $\mathbf { \delta } _ { \mathbf { p } _ { \pm } }$ . By comparison，a 60 GeV photon converting to a $e ^ { - } e ^ { + }$ pair has an opening angle of $\theta _ { \ell \ell } > 1 0 ^ { - 4 }$ in 38% of the cases and $\theta _ { \ell \ell } > 1 0 ^ { - 3 }$ in 4% of the cases. The full cumulative distribution for $\theta _ { \ell \ell } > \theta _ { \mathrm { c u t } }$ , is shown in Fig. 4.

Another experimental challenge is the multiple scattering of outgoing electrons when traversing the detector medium. This can affct the measurement of the electron direction and thus the orientation of the $e ^ { + } e ^ { - }$ or $\gamma e ^ { \pm }$ plane.Using Eq. (30.15) in [46], the width of the angular distribution is $\sim 1 0 ^ { - 4 }$ for a 30 GeV electron,assuming it traverses $\ell = 0 . 1$ （204号 radiation lengths of the material. This width roughly scales as ${ \sqrt { \ell } } / E$ ，where $E$ is the lepton energy. The measurement of polarization planes in the current and future detectors will thus be challnging, but may be achievable on a statistical basis. Bearing in mind these

![](images/30447d84c412f47be185dd60101808e3cd7ded661da4a910ec9f2881f4738b65.jpg)

FIG.5. The elastic form factor $G _ { 2 } ^ { \mathrm { e l } } ( q ^ { 2 } )$ . The dashed lines show the limiting behavior $G _ { 2 } ^ { \mathrm { e q } } \sim a ^ { 4 } q ^ { 4 }$ for $| a ^ { 2 } q ^ { 2 } | \ll 1$ (green dashed line） and $G _ { 2 } ^ { \mathrm { e l } } \sim 1$ for $| a ^ { 2 } q ^ { 2 } | \gg 1$ (red dashed line). The scale at which screening of the nucleus becomes important is denoted by $a$ ,which is smaller than the Si atomic radius, $r _ { \mathrm { a t o m } }$ . At scales well outside the atom,corresponding to small $- q ^ { \mathrm { 2 } }$ ， nuclear conversion is suppressed by the form factor screening.

experimental questions, in the remainder of this paper we adopt a theoretical approach to this problem: We consider a thought experiment where all angles can be resolved and explore the sensitivity to Higgs parameters in this best-case scenario.

# C. Nuclear form factor

The BH conversion depends on a momentum transfer, $q ^ { \mu }$ ， between the photon and the nucleus. Assuming quasi-elastic scattering, the photo-nuclear scattering is encoded in an elastic nuclear form factor $G _ { 2 } ^ { \mathrm { e l } } [ q ^ { 2 } ]$ (see Eq. (22) below). This form factor plays an important role of suppressing scattering at low $- q ^ { 2 }$ , that is,at scales larger than the Si atom.

Let us discuss briefly the behavior of the nuclear form factor. The threshold for an $E _ { \gamma } \simeq 6 0$ GeV photon to convert to an $e ^ { + } e ^ { - }$ pair is at $- q ^ { 2 } = 4 m ^ { 4 } / E _ { \gamma } ^ { 2 } \simeq 1 0 ^ { - 1 8 } \ \mathrm { G e V ^ { 2 } }$ ，with $m$ the electronic mass, but can occur at momentum transfers as large as $- q ^ { 2 } \sim 1 0 ^ { - 6 } ~ \mathrm { G e V ^ { 2 } }$ ： This should be compared with theradius of the Si atom, $r _ { \mathrm { a t o m } } \simeq 1 . 1 \mathrm { \AA }$ [48] or $r _ { \mathrm { a t o m } } ^ { - 2 } \simeq 1 0 ^ { - 1 2 }$ $\mathrm { G e V ^ { 2 } }$ ,and with the nuclear radius $r _ { \mathrm { n u c l e a r } } \simeq 4$ fm which gives $r _ { \mathrm { n u c l } } ^ { - 2 } \simeq 1 0 ^ { - 3 } ~ \mathrm { G e V ^ { 2 } }$ Within the $- q ^ { 2 }$ range of interest for conversion - $1 0 ^ { - 1 8 }$ up to $1 0 ^ { - 6 }$ GeV $^ { - 2 }$ - the nuclear charge is thus screened at low $- q ^ { 2 }$ by the atomic shell electrons. In this work we use the simple expression for the atomic form factor [49] described in detail in [41] and given by

$$
G _ { 2 } ^ { \mathrm { e l } } ( q ^ { 2 } ) = { \frac { M ^ { 2 } a ^ { 4 } q ^ { 4 } } { ( 1 - a ^ { 2 } q ^ { 2 } ) ^ { 2 } } } \ ,
$$

where $a = 1 8 4 . 1 5 ( 2 . 7 1 8 ) ^ { - 1 / 2 } Z ^ { - 1 / 3 } / m$ and $Z$ is the atomic number of the nucleus with mass （204号 $M$ For $^ { \mathrm { 2 8 } }$ Si， $a ^ { - 2 } = 1 . 2 2 \times 1 0 ^ { - 1 0 } ~ \mathrm { G e V ^ { 2 } }$ . There are two limits of interest. The first is （204号 $| a ^ { 2 } q ^ { 2 } | \gg 1$ in which $G _ { 2 } ^ { \mathrm { e l } } \sim 1$ , the second is the limit $| a ^ { 2 } q ^ { 2 } | \ll 1$ in which $G _ { 2 } ^ { \mathrm { e l } } \sim q ^ { 4 }$ ， see Fig. 5. That is, the form factor suppresses the BH cross-section for small $- q ^ { 2 } \ll a ^ { 2 }$ .To the extent that the $1 / q ^ { 4 }$ factor in the BH cross-section determines the dominant phase space configurations of the final states, this suppression significantly alters the important regions of phase space for BH conversion up to the $a ^ { - 2 }$ scale. Specifically, the form factor increases the probability of significantly acoplanar BH conversions.

# IV. THEHIGGS-BETHE-HEITLERPROCESS

In this section we present a formal analysis of the Higgs-Bethe-Heitler (HBH) process, （20 $h  \gamma \gamma$ with both photons converting to $e ^ { + } e ^ { - }$ pairs. The main result is that we obtain compact, leading order expressions for the HBH rate, and gain insight into the structure of the terms sensitive to CP violation.

# A. Amplitude and cross-section

The amplitude of interest is given by a menorah diagram, consisting of a $h  \gamma \gamma$ and two BH conversion subdiagrams, summed over internal photon polarizations, viz.

+ lepton exchanges

![](images/e4415f3bd25c5b23e31c302157d82d0bcad21df688cf2126796d6d3ccb97a32c.jpg)

$$
= \frac { 1 } { \Lambda } \sum _ { \lambda _ { 1 } , \lambda _ { 2 } } \left[ c \Big ( k _ { 1 } \cdot k _ { 2 } g ^ { \alpha \beta } - k _ { 1 } ^ { \beta } k _ { 2 } ^ { \alpha } \Big ) + \tilde { c } \Big ( k _ { 1 , p } k _ { 2 \sigma } \epsilon ^ { \rho \alpha \sigma \beta } \Big ) \right] ( \varepsilon _ { \alpha } ^ { \lambda _ { 1 } } ) ^ { * } ( \varepsilon _ { \beta } ^ { \lambda _ { 2 } } ) ^ { * } [ M _ { \mathrm { B H } } ^ { \mu } ] _ { \mathrm { 1 } r \mathrm { s } } ^ { \lambda _ { 1 } } [ M _ { \mathrm { B H } } ^ { \nu } ] _ { \mathrm { 2 } r \mathrm { s } } ^ { \lambda _ { 2 } }
$$

in which $\Lambda = \pi v / e ^ { 6 } \alpha$ , for QED coupling $e$ . The BH amplitudes are

$$
[ M _ { { \mathrm { B H } } } ^ { \mu } ] _ { i _ { r s } } ^ { \lambda _ { i } } = \bar { u } ^ { r _ { i } } ( p _ { i _ { - } } ) \left[ \notin ^ { \lambda _ { i } } \frac { i } { \displaystyle \vec { p } _ { i _ { - } } - \not k _ { i } - m } \gamma ^ { \mu } + \gamma ^ { \mu } \frac { i } { \displaystyle \vec { k } _ { i } - \not p _ { i _ { + } } - m } \phi ^ { \lambda _ { i } } \right] v ^ { s _ { i } } ( p _ { i _ { + } } ) ~ ,
$$

where we have not yet taken nuclear form factors into account,and kept explicit the corresponding Lorentz index of the nuclear electromagnetic current. The Latin subscripts, （204号 $i = 1 , 2$ , label each photon，while $s _ { i }$ ， $r _ { i } = 1 , 2$ are respectively the positron and electron spins (see Eq. (A8))， and $\lambda _ { i } = \pm$ the outgoing photon helicities from the $h  \gamma \gamma$ vertex. We have also suppressed repetitions of the photon index, such that $X _ { i _ { r s } }$ is henceforth a shorthand for $X _ { i _ { r _ { i } s _ { i } } }$ . We shall often refer to the BH subdiagrams for each photon as the photon branch.

We assume both nuclei are initially at rest in the lab frame,so $P ^ { \mu } = ( M , \mathbf { 0 } )$ where $M$ is the mass of the nucleus. The Higgs need not be at rest in the lab frame. As discussed in Sec. III A,we assume quasi-elastic scattering, that is $P _ { i } ^ { \prime 2 } = P ^ { 2 } = M ^ { 2 }$ . This implies that （204号 $2 q _ { i } \cdot P + q _ { i } ^ { 2 } = 0$ ， and so

$$
E _ { i } - E _ { i _ { + } } - E _ { i _ { - } } + q _ { i } ^ { 2 } / 2 M = 0 \ ,
$$

where $E _ { i }$ ， $E _ { i \pm }$ are the photon and lepton energies respectively. It is also convenient to define

$$
Q _ { i } ^ { \mu } \equiv \frac { 1 } { M } \biggl ( P ^ { \mu } - q _ { i } ^ { \mu } \frac { q _ { i } \cdot P } { q _ { i } ^ { 2 } } \biggr ) = \frac { 1 } { M } \biggl ( P ^ { \mu } + \frac { q _ { i } ^ { \mu } } { 2 } \biggr ) \ ,
$$

under quasi-scattering conditions. The exchange energy with the nucleus $q _ { i } ^ { 0 } \equiv P _ { i } ^ { \prime 0 } - P _ { i } ^ { 0 } \ll$ $M$ . I.e. the nucleus velocity is non-relativistic, so to an excellent approximation, it follows that

$$
E _ { i } \simeq E _ { i _ { + } } + E _ { i _ { - } } \ , \qquad Q _ { i } ^ { \mu } \simeq ( 1 , { \bf 0 } ) \ ,
$$

in the lab frame.

We define the BH nuclear form factor tensors on each photon branch [41]

$$
{ \mathcal W } _ { i } ^ { \mu \nu } = - W _ { 1 } ( q _ { i } ^ { 2 } ) \biggl ( g ^ { \mu \nu } - \frac { q _ { i } ^ { \mu } q _ { i } ^ { \nu } } { q _ { i } ^ { 2 } } \biggr ) + W _ { 2 } ( q _ { i } ^ { 2 } ) Q _ { i } ^ { \mu } Q _ { i } ^ { \nu } \ ,
$$

such that the unpolarized HBH squared amplitude

$$
| \mathcal { M } | ^ { 2 } \prod _ { i = 1 , 2 } 2 M \delta ( M ^ { 2 } - P _ { i } ^ { \prime 2 } ) = \frac { 1 } { q _ { 1 } ^ { 4 } q _ { 2 } ^ { 4 } } \sum _ { r _ { i } , s _ { i } } \mathcal { M } _ { 1 _ { r s } 2 _ { r s } } ^ { \mu \nu } \mathcal { M } _ { 1 _ { r s } 2 _ { r s } } ^ { * \mu ^ { \prime } \nu ^ { \prime } } \mathcal { W } _ { 1 _ { \mu \mu ^ { \prime } } } \mathcal { W } _ { 2 \nu \nu ^ { \prime } } \ .
$$

On the left of Eq. (21) we have factored out the $\delta -$ functions that enforce quasi-elastic scattering. The form factor $W _ { 1 } ( q ^ { 2 } ) = 0$ for quasi-elastic scattering on a spin-O nuclear target [45], while

$$
W _ { 2 } ( q ^ { 2 } ) = 2 M \delta ( M ^ { 2 } - P ^ { \prime 2 } ) G _ { 2 } ^ { \mathrm { e l } } ( q ^ { 2 } ) \ ,
$$

in which $G _ { 2 } ^ { \mathrm { e l } } ( q ^ { 2 } )$ is the form factor given in Eq. (14). Hence the unpolarized HBH squared amplitude reduces to

$$
| \mathcal { M } | ^ { 2 } = \frac { G _ { 2 } ^ { \mathrm { e l } } ( q _ { 1 } ^ { 2 } ) G _ { 2 } ^ { \mathrm { e l } } ( q _ { 2 } ^ { 2 } ) } { q _ { 1 } ^ { 4 } q _ { 2 } ^ { 4 } } \sum _ { r _ { i } , s _ { i } } \mathcal { M } _ { 1 _ { r s } 2 _ { r s } } ^ { \mu \nu } \mathcal { M } _ { 1 _ { r s } 2 _ { r s } } ^ { * \mu ^ { \prime } \nu ^ { \prime } } Q _ { 1 _ { \mu } } Q _ { 1 _ { \mu ^ { \prime } } } Q _ { 2 \nu } Q _ { 2 \nu ^ { \prime } } \ .
$$

# B． Helicity structure

One may calculate $| { \mathcal { M } } | ^ { 2 }$ via the usual Feynman method, which relies on polarization completeness relations to compute traces. This approach leads to thousands of terms， of which the naively dominant terms cancel due to Ward identities. Extracting leading order expressions is therefore diffcult，and moreover， high numerical precision is required for numerical stability. As an alternative, we employ a spin and helicity analysis combined with the spinor-helicity formalism to compute the HBH amplitudes. These may be subsequently squared and summed over external spins to produce the full HBH rate. In the folowing we provide a brief overview of these results, while details are provided in Appendices A and B.

The BH spin-helicity amplitudes are defined as

$$
\alpha _ { i _ { r s } } ^ { \pm } \equiv [ M _ { \mathrm { B H } } ^ { \mu } ] _ { i _ { r s } } ^ { \pm } Q _ { i \mu } / q _ { i } ^ { 2 } \ .
$$

With reference to Eqs. (15) and (23), the HBH spin-helicity amplitudes are correspondingly

$$
M _ { 1 _ { r s } 2 _ { r s } } ^ { \lambda _ { 1 } \lambda _ { 2 } } = \frac { \sqrt { \mathcal { G } _ { 1 } \mathcal { G } _ { 2 } } } { \Lambda } \Big [ c \Big ( k _ { 1 } \cdot k _ { 2 } g ^ { \alpha \beta } - k _ { 1 } ^ { \beta } k _ { 2 } ^ { \alpha } \Big ) + \tilde { c } \Big ( k _ { 1 _ { \rho } } k _ { 2 \sigma } e ^ { \rho \alpha \sigma \beta } \Big ) \Big ] ( \varepsilon _ { \alpha } ^ { \lambda _ { 1 } } ) ^ { * } ( \varepsilon _ { \beta } ^ { \lambda _ { 2 } } ) ^ { * } \alpha _ { 1 _ { r s } } ^ { \lambda _ { 1 } } \alpha _ { 2 _ { r s } } ^ { \lambda _ { 2 } } \ ,
$$

where we introduced the abbreviation

$$
\mathcal { G } _ { i } \equiv G _ { 2 } ^ { \mathrm { e l } } ( q _ { i } ^ { 2 } ) ~ .
$$

Making use of the spinor-helicity formalism (see Appendix A), we obtain the spin amplitudes

$$
\mathcal { M } _ { 1 _ { r s } 2 _ { r s } } \equiv \sum _ { \lambda _ { 1 } \lambda _ { 2 } } \mathcal { M } _ { 1 _ { r s } 2 _ { r s } } ^ { \lambda _ { 1 } \lambda _ { 2 } } = \frac { m _ { h } ^ { 2 } } { \Lambda } \sqrt { \mathcal { G } _ { 1 } \mathcal { G } _ { 2 } } \sqrt { c ^ { 2 } + \tilde { c } ^ { 2 } } \Big ( e ^ { i \xi } \alpha _ { 1 _ { r s } } ^ { + } \alpha _ { 2 _ { r s } } ^ { + } + e ^ { - i \xi } \alpha _ { 1 _ { r s } } ^ { - } \alpha _ { 2 _ { r s } } ^ { - } \Big ) \ .
$$

These are reminiscent of equation (9) with final leptonic spin states $\left. r _ { i } s _ { i } \right|$ and $\alpha _ { i _ { r s } } ^ { \pm } \propto \langle s _ { i } r _ { i } | \pm \rangle$ as expected. The HBH square-amplitude is correspondingly

$$
M | ^ { 2 } \equiv \sum _ { 1 _ { r s } 2 _ { r s } } \big | \sum _ { \lambda _ { 1 } \lambda _ { 2 } } \mathcal { M } _ { 1 _ { r s } 2 _ { r s } } ^ { \lambda _ { 1 } \lambda _ { 2 } } \big | ^ { 2 } = m _ { h } ^ { 4 } \mathcal { G } _ { 1 } \mathcal { G } _ { 2 } \frac { c ^ { 2 } + \tilde { c } ^ { 2 } } { 4 \Lambda ^ { 2 } } \sum _ { 1 _ { r s } 2 _ { r s } } \big | \alpha _ { 1 _ { r s } } ^ { + } \alpha _ { 2 _ { r s } } ^ { + } e ^ { i \xi } + \alpha _ { 1 _ { r s } } ^ { - } \alpha _ { 2 _ { r s } } ^ { - } e ^ { - i \xi } \big | ^ { 2 } \ .
$$

Note that the sum over photon polarizations is inside the absolute value as expected for entangled $h \to 2 \gamma \to 2 ( e ^ { + } e ^ { - } )$ decay, but the sum over lepton spins is incoherent. Eq. (28) shows that the BH spin-helicity amplitudes $\alpha _ { i _ { r s } } ^ { \pm }$ are all one needs to determine the entire HBH square amplitude. Parity invariance of the BH amplitudes relates amplitudes of opposite helicity and spins to their complex conjugates,

$$
( \alpha _ { r s } ^ { + } ) ^ { * } = \eta _ { r s } \alpha _ { \bar { r } \bar { s } } ^ { - } ~ ,
$$

where $s$ is the opposite spin to $s$ ，and $\eta _ { r s } ^ { 2 } = 1$ ， $\eta _ { r s } = \eta _ { \bar { r } \bar { s } }$ . Hence we need only determine （20 $\alpha _ { i _ { r s } } ^ { + }$ . We shall see below that spinor-helicity methods, when applied to $\alpha _ { i _ { r s } } ^ { \pm }$ , also allow for a well-controlled expansion of dominant, sub-dominant and negligible terms in $| { \mathcal { M } } | ^ { 2 }$

We see explicitly from Eq. (28) that the helicity interference terms are equivalent to the （20 $\xi$ -dependent terms,as discussed in sections IIB and IIC. For a particular leptonic spin configuration $\{ r _ { i } , s _ { i } \}$ , helicity interference occurs so long as $\alpha _ { i _ { r s } } ^ { + }$ and $\alpha _ { i _ { r s } } ^ { - }$ are both non-zero. However, we see in appendix B,and in particular in Eq. (B3),that for our particular choice of spinor basis (see Eq. (A8))

$$
| \alpha _ { i _ { 1 1 } } ^ { - } | \sim | \alpha _ { i _ { 1 2 } } ^ { - } | \sim | \alpha _ { i _ { 2 1 } } ^ { - } | \gg | \alpha _ { i _ { 2 2 } } ^ { - } | \ ,
$$

or equivalently $| \alpha _ { i _ { 2 2 } } ^ { + } | \sim | \alpha _ { i _ { 1 2 } } ^ { + } | \sim | \alpha _ { i _ { 2 1 } } ^ { + } | \gg | \alpha _ { i _ { 1 1 } } ^ { + } |$ . This hierarchy means that we may therefore discard any terms containing either $\alpha _ { i _ { 2 2 } } ^ { + }$ or $\alpha _ { i _ { 1 1 } } ^ { - }$ as subleading. It follows that the leading order squared amplitude is

$$
^ 2 \simeq m _ { h } ^ { 4 } \frac { c ^ { 2 } + \tilde { c } ^ { 2 } } { 4 \Lambda ^ { 2 } } \mathcal { G } _ { 1 } \mathcal { G } _ { 2 } \Bigg \{ 2 \Big | \alpha _ { 1 _ { 1 1 } } ^ { - } \alpha _ { 2 _ { 1 1 } } ^ { - } \Big | ^ { 2 } + 2 \sum _ { j \neq k } \Big | \alpha _ { j _ { 1 1 } } ^ { - } \alpha _ { k _ { r s } } ^ { - } \Big | ^ { 2 } + \sum _ { { r _ { 1 } \neq s } _ { 1 } } \Big | \alpha _ { 1 { r s } } ^ { + } \alpha _ { 2 { r s } } ^ { + } e ^ { i \xi } + \alpha _ { 1 { r s } } ^ { - } \alpha _ { 2 { r s } } ^ { - } e ^ { i \xi } \Big \} _ { { r _ { 2 } \neq s } _ { 2 } } \mathrm { ~ , ~ }
$$

while the leading interference term is

$$
\left. | \mathcal { M } | ^ { 2 } \right| _ { \mathrm { i n t } } \simeq 2 m _ { h } ^ { 4 } \frac { c ^ { 2 } + \tilde { c } ^ { 2 } } { \Lambda ^ { 2 } } \mathcal { G } _ { 1 } \mathcal { G } _ { 2 } \mathrm { R e } \bigg \{ \alpha _ { 1 _ { 1 2 } } ^ { - } \alpha _ { 1 _ { 2 1 } } ^ { - } \alpha _ { 2 _ { 1 2 } } ^ { - } \alpha _ { 2 _ { 2 1 } } ^ { - } e ^ { - 2 i \xi } \bigg \} \ .
$$

We see that only $\alpha _ { 1 2 , 2 1 } ^ { - }$ (or equivalently $\alpha _ { 2 1 , 1 2 } ^ { + }$ ） amplitudes enter the leading order $\xi$ dependent interference terms.

The CP odd helicity interference term in (32)is proportional to $c \tilde { c }$

$$
\left| \mathcal { M } \right| ^ { 2 } \big | _ { \mathrm { i n t , C P - o d d } } = - 2 m _ { h } ^ { 4 } \frac { c \tilde { c } } { \Lambda ^ { 2 } } \mathcal { G } _ { 1 } \mathcal { G } _ { 2 } \mathrm { I m } \Big \{ \alpha _ { 1 _ { 1 2 } } ^ { - } \alpha _ { 1 _ { 2 1 } } ^ { - } \alpha _ { 2 _ { 1 2 } } ^ { - } \alpha _ { 2 _ { 2 1 } } ^ { - } \Big \} \ .
$$

Note that interference terms between amplitudes, produced by the $F F$ and $F \tilde { F }$ operators respectively, are CP odd. However, the helicity amplitudes under consideration here receive contributions from both CP odd and CP even operators - manifestly they depend on $\xi$ -and hence helicity interference terms contain both CP-even and CP-odd pieces. Consequently, we interpret the remaining piece of the helicity interference term to be the CP-even piece,

$$
\left| \mathcal { M } \right| ^ { 2 } \middle | _ { \mathrm { i n t , C P - e v e n } } = m _ { h } ^ { 4 } \frac { c ^ { 2 } - \tilde { c } ^ { 2 } } { \Lambda ^ { 2 } } \mathcal { G } _ { 1 } \mathcal { G } _ { 2 } \mathrm { R e } \Big \{ \alpha _ { 1 _ { 1 2 } } ^ { - } \alpha _ { 1 _ { 2 1 } } ^ { - } \alpha _ { 2 _ { 1 2 } } ^ { - } \alpha _ { 2 _ { 2 1 } } ^ { - } \Big \} \ .
$$

This term has quadratic dependence on $\tilde { c } ^ { 2 }$ , albeit a different one than the total rate (12).

# C. TheBethe-Heitler helicity amplitudes

In Eqs.(31) and (32) we have expressed the leading order HBH rate and interference term in terms of individual BH helicity amplitudes, $\alpha _ { r s } ^ { \pm }$ . In this subsection we proceed to present the leading order terms of these amplitudes in a readily accessble notation， for the special case that the Higgs is at rest in the lab frame. The results below are achieved via spinor-helicity techniques; a more comprehensive presentation of the derivation of these results is provided in Appendix B. There, explicit results for each spin helicity amplitude $\alpha _ { i _ { r s } } ^ { \pm }$ are collected in Eqs. (B2), while the leading order results,obtained by power counting in （204号 $m / m _ { h }$ , are provided in (B3). The compact results below will permit us, in the next section of this paper, to study the encoding of the CPV structure in the HBH rate at an analytic level.

Before proceeding, we may first derive a new result concerning the well-studied unpolarized BH square amplitude, $\begin{array} { r } { \vert \mathcal { M } _ { \mathrm { B H } _ { i } } \vert ^ { 2 } = \sum _ { r s \lambda } \vert \alpha _ { i _ { r s } } ^ { \lambda } \vert ^ { 2 } } \end{array}$ . Using Eqs. (B2) one may show that

$$
| \mathcal { M } _ { \mathrm { B H } _ { i } } | ^ { 2 } \simeq 8 \frac { \mathcal { G } _ { i } m ^ { 2 } } { q _ { i } ^ { 4 } } \bigg [ \frac { E _ { i _ { - } } ( k _ { i } \cdot p _ { i _ { - } } ) - E _ { i _ { + } } ( k _ { i } \cdot p _ { i _ { + } } ) } { ( k _ { i } \cdot p _ { i _ { - } } ) ( k _ { i } \cdot p _ { i _ { + } } ) } \bigg ] ^ { 2 } - 4 \frac { \mathcal { G } _ { i } } { q _ { i } ^ { 2 } } \frac { E _ { i _ { + } } ^ { 2 } + E _ { i _ { - } } ^ { 2 } } { ( k _ { i } \cdot p _ { i _ { - } } ) ( k _ { i } \cdot p _ { i _ { + } } ) } ~ .
$$

This compact expression for the BH rate in the quasi-elastic scattering limit is novel to this work.A numerical analysis and validation of the resulting BH differential cross-section is provided in Appendix D.

Now,in the special case that the Higgs is at rest in the lab frame, that is $P _ { h } = { \bf 0 }$ ， Eqs.(B3) for the $\alpha _ { i _ { r s } } ^ { \pm }$ collapse to very simple expressions. Using the leading order results (B3) and assuming $\theta _ { \pm } \ll 1$ , for each branch one finds

$$
\begin{array} { l } { { \alpha _ { 1 1 } ^ { - } = - ( \alpha _ { 2 2 } ^ { + } ) ^ { * } \simeq \displaystyle \frac { 2 \sqrt { 2 \gamma _ { + } \gamma _ { - } } } { q ^ { 2 } } \bigg ( \frac { 1 } { 1 + \gamma _ { + } ^ { 2 } \theta _ { + } ^ { 2 } } - \frac { 1 } { 1 + \gamma _ { - } ^ { 2 } \theta _ { - } ^ { 2 } } \bigg ) , } } \\ { { \alpha _ { 1 2 } ^ { - } = + ( \alpha _ { 2 1 } ^ { + } ) ^ { * } \simeq \pm \displaystyle \frac { 2 \sqrt { 2 \gamma _ { + } \gamma _ { - } } } { q ^ { 2 } } \frac { \gamma _ { \mp } } { \gamma _ { + } + \gamma _ { - } } \bigg ( \frac { \gamma _ { + } \theta _ { + } e ^ { - i \phi _ { + } } } { 1 + \gamma _ { + } ^ { 2 } \theta _ { + } ^ { 2 } } + \frac { \gamma _ { - } \theta _ { - } e ^ { - i \phi _ { - } } } { 1 + \gamma _ { - } ^ { 2 } \theta _ { - } ^ { 2 } } \bigg ) , } } \\ { { \alpha _ { 2 2 } ^ { - } = - ( \alpha _ { 1 1 } ^ { + } ) ^ { * } \simeq 0 \ . } } \end{array}
$$

Here $\theta _ { \pm }$ and $\phi _ { \pm }$ are respectively the polar and azimuthal angles defined with respect to the branch parent photon momentum,as shown in Fig. 6,and $\gamma _ { \pm } \equiv E _ { \pm } / m \gg 1$ . We also assume that the $\mathcal { O } ( \theta )$ terms do not cancel completely. The latter may occur on the phase space slice $\gamma _ { + } \theta _ { + } = \gamma _ { - } \theta _ { - }$ and $| \phi _ { - } - \phi _ { + } | = \pi$ , corresponding to minimal $| q ^ { 2 } |$ . Excellent numerical validation of this expansion implies that the neighborhood of this phase space slice, on which the expansion fails, is actually of negligibly small measure. Finally, we may approximate $q ^ { 2 }$ by

$$
- q ^ { 2 } \simeq m ^ { 2 } \Bigl ( \gamma _ { + } ^ { 2 } \theta _ { + } ^ { 2 } + \gamma _ { - } ^ { 2 } \theta _ { - } ^ { 2 } + 2 \gamma _ { - } \gamma _ { + } \theta _ { - } \theta _ { + } \cos ( \phi _ { - } - \phi _ { + } ) \Bigr ) + { \frac { m ^ { 2 } } { 4 } } \biggl [ { \frac { 1 } { \gamma _ { + } } } + { \frac { 1 } { \gamma _ { - } } } \biggr ] ^ { 2 } \ .
$$

Eqs. (36) and (37)，when combined with Eq. (28)， form one of the central results of this paper: a compact form of the HBH rate, which is both numerically stable,and whose structure may now be studied analytically. For example, it is now manifest that HBH polar angular structure is dominantly controlled just by the $k \cdot p _ { + } / m ^ { 2 } \simeq 1 + \gamma _ { \pm } \theta _ { \pm }$ denominators, which produce a peak near $\theta _ { \pm \gamma _ { \pm } } \sim 1$ . More importantly, we see that the $\alpha _ { 1 2 , 2 1 } ^ { \pm }$ amplitudes, that control the helicity interference terms, contain phases which are the leptonic azimuthal orientations, $\phi _ { i \pm }$ . This non-trivial result，when combined with Eq. (32) shows us that，at leading order, $\xi$ manifests as a phase shift in the relative azimuthal orientations of leptons with different parent photons.

![](images/3971ff4b10c655234eea49ed05ac7ae6bf91697fafe814b9de235406c5e8c419.jpg)

FIG. 6. Definitions of local spherical polar angles $\{ \theta _ { i \pm } , \phi _ { i \pm } \}$ . Note in particular that azimuthal angles, $\phi _ { i \pm }$ are positively oriented with respect to their parent photons,and are defined with respect to an azimuth $\hat { \pmb x }$ common to both branches. Polar angles are defined with respect to parent photon momentum (black dotted).

# V. SENSITIVITY TO CPV

In this section we assess the potential sensitivity to CP violation. To do this, we consider a number of CPV sensitive observables and propose several sets of kinematic cuts that can enhance the CPV signal. These sets of cuts require that the lepton-lepton opening angle (13), $\theta _ { \ell \ell }$ , can be resolved, as well as the two photon-lepton angles, $\theta _ { \pm }$ . In the following we mostly consider angular resolution cuts of the form

$$
\theta _ { \ell \ell } \ , \theta _ { \pm } > \theta _ { \mathrm { c u t } } \ .
$$

Following Sec. IIIB, we apply an angular resolution cut $\theta _ { \mathrm { c u t } } = 1 0 ^ { - 4 }$ ， which is at the edge of what may be possible with present detectors, and a looser, futuristic $\theta _ { \mathrm { c u t } } = 1 0 ^ { - 5 }$ , intended to show that very large CPV effects are possible in principle.

We emphasize that as our measurement is a novel, challenging one, our goal here is not to conduct a full collider analysis including backgrounds. Rather our aim is to identify the types of observables that can probe CP violation in $h  \gamma \gamma$ , and estimate how well they do under ideal circumstances: a high efficiency in reconstructing conversions and a signal rich channel. This is in the anticipation that such circumstances might materialize in a future LHC running or at a Higgs factory.

# A． Differential scattering rate

The HBH differential scattering rate for the full $3  6$ process (Higgs plus two nuclei to two nuclei and two $e ^ { + } e ^ { - }$ pairs） in the lab frame is

$$
\begin{array} { l } { { { \displaystyle \langle | { \mathcal { M } } | ^ { 2 } d \Pi _ { h  \gamma \gamma } d \Pi _ { \mathrm { B H } _ { 1 } } d \Pi _ { \mathrm { B H } _ { 2 } } } } } \\  { { \displaystyle \langle \frac { | { \mathcal { M } } | ^ { 2 } } { ( 2 \pi ) ^ { 1 2 } M ^ { 2 } E _ { \gamma } ^ { 2 } } { \biggl [ } \prod _ { i = 1 , 2 } \frac { d ^ { 3 } p _ { i _ { \alpha } } } { 2 E _ { i _ { \alpha } } } { \biggr ] } { \biggl [ \prod _ { i = 1 , 2 } } \frac { d ^ { 3 } P _ { i } ^ { \prime } } { 2 E _ { i } ^ { \prime } } \frac { d ^ { 3 } k _ { i } } { 2 E _ { i } } \delta ^ { ( 4 ) } ( q _ { i } + p _ { i _ { + } } + p _ { i _ { - } } - k _ { i } ) { \biggr ] } \delta ^ { ( 4 ) } ( P _ { h } - k _ { 1 } - p _ { i _ { \alpha } } ) } } \\ { { { \displaystyle \alpha = \pm } } } \end{array}
$$

with $| { \mathcal { M } } | ^ { 2 }$ given by Eq. (28). Integrating over the out-going nuclear momenta and all other momenta in delta functions,we obtain in the limit $| q | \ll M$ （20

$$
d \Gamma \propto { \frac { 1 } { ( 2 \pi ) ^ { 1 2 } } } { \frac { m _ { h } } { 4 M ^ { 4 } E _ { \gamma } ^ { 2 } } } | { \mathcal { M } } | ^ { 2 } \biggl [ \prod _ { i = 1 , 2 \atop \alpha = \pm } | p _ { i _ { \alpha } } | d \Omega _ { i _ { \alpha } } \biggr ] d E _ { 1 _ { - } } d E _ { 2 _ { - } } d \Omega _ { 1 } ,
$$

with $d \Omega _ { i _ { \alpha } }$ the solid angle for each lepton momentum ${ \pmb p } _ { i _ { \alpha } }$ ，and $d \Omega _ { 1 }$ the solid angle for photon‘1'. The photon labels are extrinsic. We take photon ‘ $1 ^ { \mathrm { : } }$ ， say, as westwards going (if Higgs is not at rest one can also take it to be, e.g., the more energetic photon).

For simplicity, we assume henceforth that the Higgs is at rest in the lab frame, that is $P _ { h } = \left( m _ { h } , \mathbf { 0 } \right)$ . In the Higgs rest frame the photon angular dependence is isotropic,and the integration over $d \Omega _ { 1 }$ is trivial. Dropping the prefactors, the differential scattering rate becomes

$$
d \Gamma \propto | \mathcal { M } | ^ { 2 } \bigg [ \prod _ { \stackrel { \scriptstyle i = 1 , 2 } { \alpha = \pm } } | { \pmb p } _ { i _ { \alpha } } | d \Omega _ { i _ { \alpha } } \bigg ] d E _ { 1 _ { - } } d E _ { 2 _ { - } } \ .
$$

We may now proceed to consider CPV observables.

# B. Global sensitivity to CP violation

In principle all the information about $\tilde { c } \ne 0$ (or equivalently $\xi \neq 0$ ）is encoded in the full HBH differential distribution. The coefficient $\tilde { c }$ may be determined by a matrix element method [5O-55]，as long as backgrounds can be kept under control. Estimating the full power of the matrix element method is beyond the scope of this work.

To test the sensitivity of HBH to $\ddot { c }$ we instead introduce a parameter

$$
Z _ { B } ( c , \tilde { c } ) = \frac { \int | d \Gamma ( \mathrm { S M } ) / d \mathrm { P S } - d \Gamma ( c , \tilde { c } ) / d \mathrm { P S } | d \mathrm { P S } } { \Gamma ( \mathrm { S M } ) } \ .
$$

![](images/372a449ba9cf9ff567bb3459e3c839f178ce96af4bd1b129fcc953d03ff6d59c.jpg)  
FIG. 7. Top panel: $Z _ { B }$ in the $c - \tilde { c }$ plane, with the SM point at $( c , \tilde { c } ) = ( - 0 . 8 1 , 0 )$ . Bottom panel: （20 $Z _ { B } ^ { c }$ as a function of $\xi = \tan ^ { - 1 } ( \tilde { c } / c )$ . The scatter of the data points is a numerical artifact.

The parameter $Z _ { B }$ can be thought of as a proxy for the sensitivity of the matrix element method, once one integrates over the full phase space. In the top panel of Fig. 7 we show the value of $Z _ { B }$ in the $( c , \tilde { c } )$ plane. There we see that the deviation from the SM is mostly due to the $c ^ { 2 } + \tilde { c } ^ { 2 }$ enhancement of the $h  \gamma \gamma$ rate,which need not arise from CP violation. Such an enhancement is best detected by measuring the overall $h  \gamma \gamma$ rate, and not using our method.

To assess the sensitivity to CP violation alone, we should restrict our attention to the circular contour $c ^ { 2 } + \tilde { c } ^ { 2 } = c _ { \mathrm { S M } } ^ { 2 }$ , on which the total HBH rate matches the SM rate for any $\xi$ This contour is shown as a white circle in the top panel of Fig.7. To this end, we define a

second quantity

$$
Z _ { B } ^ { \mathrm { c } } ( \xi ) \equiv Z _ { B } ( \xi ) \bigg | _ { c ^ { 2 } + \tilde { c } ^ { 2 } = c _ { \mathrm { S M } } ^ { 2 } } = \frac { \int \left| \hat { d \Gamma } ( 0 ) / d \mathrm { P S } - \hat { d \Gamma } ( \xi ) / d \mathrm { P S } \right| d \mathrm { P S } } { \hat { \Gamma } ( 0 ) } ,
$$

where $\hat { d \Gamma } ( \xi )$ is the differential HBH rate with the enhancement of the total $h  \gamma \gamma$ rate factored out,

$$
d \Gamma ( c , \tilde { c } ) / d \mathrm { P S } = \frac { ( c ^ { 2 } + \tilde { c } ^ { 2 } ) } { c _ { \mathrm { S M } } ^ { 2 } } d \hat { \Gamma } ( \xi ) / d \mathrm { P S } .
$$

Note that in general $Z _ { B } \in [ 0 , \infty )$ ，but $Z _ { B } ^ { \mathrm { c } } \in [ 0 , 2 ]$ （24号

The bottom panel in Fig. 7 shows the value of $Z _ { B } ^ { \mathrm { c } }$ as a function of $\xi$ .The sinusoidal dependence of $Z _ { B } ^ { \mathrm { c } }$ on $\xi$ is not unexpected.For instance, in the $h  \gamma \gamma$ toy example we considered in Sec. IIC,in which the angle between linear polarizations is measured, one has from Eq. (12)

$$
Z _ { B } ^ { \mathrm { c } } ( \xi ) \bigg | _ { h  \gamma \gamma } = \frac { 1 } { \pi } \int _ { 0 } ^ { 2 \pi } | \cos ^ { 2 } ( \phi + \xi ) - \cos ^ { 2 } ( \phi ) | d \phi = \frac { 4 } { \pi } | \sin \xi | \ .
$$

By comparing this toy system with HBH,it is therefore natural to deduce that $Z _ { B } ^ { \mathrm { c } } ( \xi ) / | \sin \xi |$ provides a measure of the average CPV signal size obtainable via the matrix element method, for any $c , \tilde { c }$ . That is, this measure is independent of $\xi$ and the overall normalization $c ^ { 2 } + \tilde { c } ^ { 2 }$ ： The fit in Fig. 7 suggests this CPV signal is $\mathcal { O } ( 1 0 \% )$ for an angular resolution cut $\theta _ { \ell \ell } > 1 0 ^ { - 5 }$ ， and $\mathcal { O } ( 5 \% )$ for $\theta _ { \ell \ell } > 1 0 ^ { - 4 }$ . Hence, for the most pessimistic case that there is no deviation from the SM in the total $h  \gamma \gamma$ rate the detection of NP from the full matrix element method will be challenging, even if there is large CPV component in $h  \gamma \gamma$

# C. Differential azimuthal scattering rate

Let us also consider the sensitivity of an experiment in which just one relative azimuthal angle - the difference of the azimuthal angles between two opposite branch leptons - is reconstructed, such as the experiment described in Fig. 1. From Eqs. (28) and (36) we saw that $\xi$ manifests as a phase shift in the relative azimuthal orientation of leptons on different branches. It is instructive to write down this manifestation explicitly. Let us transform from the azimuthal coordinates $\phi _ { i \pm }$ to the coordinates

$$
\varphi \equiv \phi _ { 1 _ { + } } + \phi _ { 2 _ { + } } ~ , \qquad \varepsilon _ { i } \equiv \phi _ { i _ { - } } - \phi _ { i _ { + } } ~ ,
$$

and choose $\phi _ { 1 _ { + } } = 0$ ，without loss of generality. With this choice $\varphi$ and $\varepsilon _ { 1 } \in [ 0 , 2 \pi )$ ，while （204号 $\varepsilon _ { 2 } \in ( - 2 \pi , 2 \pi )$ . For the case that the Higgs is at rest,we find from Eqs.(31) and (36) that the HBH square amplitude, and thus the leading order differential scattering rate,takes the generic form

$$
d \Gamma / d \mathrm { P S } = \frac { 1 } { q _ { 1 } ^ { 4 } q _ { 2 } ^ { 4 } } \biggl [ a + \sum _ { j } b _ { j } \cos { \varepsilon _ { j } } + \sum _ { k } c _ { k } \cos { \left( n _ { k } \varepsilon _ { 1 } + m _ { k } \varepsilon _ { 2 } + 2 \varphi + 2 \xi \right) } \biggr ] \ ,
$$

where $a$ ， $b _ { j }$ and $c _ { k }$ are real functions of $\gamma _ { i \pm }$ and $\theta _ { i \pm }$ - they span the energy， polar angle phase space, denoted hereafter by $\mathrm { P S } _ { \gamma , \theta }$ - but are independent of the azimuthal structure, and $n _ { k }$ ， $m _ { k }$ are positive integers that satisfy $n _ { k } + m _ { k } = 0 , 1$ , or 2. From Eq. (37),one sees that the $1 / q ^ { 4 }$ factors depend on both the azimuthal and polar angles, but in a way such that $q ^ { 4 } = \eta ( 1 + \zeta \cos { \varepsilon } ) ^ { 2 }$ ，where $\zeta < 1$ . Hence $1 / q ^ { 4 }$ may be expanded in a power series of （204号 $\zeta \cos \varepsilon < 1$ . Integrating over the $\boldsymbol { \varepsilon }$ acoplanarity angles, one may then show that, with respect to the azimuthal structure, only constant or $\cos ( 2 \varphi + 2 \xi )$ terms survive. That is, the leading order differential scattering rate

$$
{ \frac { d \Gamma } { d \varphi \ d \mathrm { P S } _ { \gamma , \theta } } } = ( c ^ { 2 } + \tilde { c } ^ { 2 } ) \Big [ { \mathcal { A } } _ { \gamma , \theta } + { \mathcal { B } } _ { \gamma , \theta } \cos ( 2 \varphi + 2 \xi ) \Big ] \ ,
$$

in which the $\gamma , \theta$ subscript denotes exclusive dependence on the energy polar angle phase space, $\mathrm { P S } _ { \gamma , \theta }$ ：

The results (47) or(48) show that $\xi$ -dependence and $\gamma , \theta$ -dependence factorize. Hence $\xi$ （204号 appears only in the azimuthal structure as a phase shift. Specifically, the CPV parameter $\xi$ （204号 manifests itself in the inter-branch azimuthal structure in the differential rate

$$
\frac { d \Gamma } { d \varphi } = ( c ^ { 2 } + { \tilde { c } } ^ { 2 } ) \Big [ \big < A _ { \gamma , \theta } \big > _ { \mathrm { P S } _ { \gamma , \theta } } + \big < \mathcal { B } _ { \gamma , \theta } \big > _ { \mathrm { P S } _ { \gamma , \theta } } \cos ( 2 \varphi + 2 \xi ) \Big ] ~ ,
$$

which we have now shown is oscillatory with respect to $\varphi$ at leading order. Note that we could have chosen $\varphi$ to be any of the four inter-branch angles $\varphi _ { 1 _ { \alpha } 2 _ { \beta } } \equiv \phi _ { 1 _ { \alpha } } + \phi _ { 2 _ { \beta } }$ ，where （204号 $\alpha$ ， $\beta = \pm$ , of which three are linearly independent. Results similar to Eq. (48) follow with appropriate replacements.

In the right panel of Fig. 8 we show the differential distribution $d \Gamma / d \varphi$ for HBH events (including a loose cut on the polar angles,at $1 0 ^ { - 5 }$ ） for two values of $\xi$ . It is evident that the oscillation amplitude, $\langle B \rangle / \langle A \rangle$ , is small - approximately $\sim 2 \%$ - when averaged over all of the phase space $\mathrm { P S } _ { \gamma , \theta }$ （

The key question we now wish to address is whether such a small oscillation amplitude is because of small, $\mathcal { O } ( 1 \% )$ oscillations,or whether there is an $\mathcal { O } ( 1 \% )$ part of the phase space where deviations from the SM are $\mathcal { O } ( 1 )$ . In the language of Eq. (48), this question can be rephrased in a precise manner: Is $\langle B \rangle _ { U } / \langle A \rangle _ { U }$ small for all $U \subset \mathrm { P S }$ ，or does there exist $U \subset { \mathrm { P S } }$ such that $\langle B \rangle _ { U } / \langle A \rangle _ { U }$ is $\mathcal { O } ( 1 )$ . The latter possibility is phenomenologically preferred, since it permits the extraction of an $\mathcal { O } ( 1 )$ CPV signal on $U$ ，which would scale better with increasing statistics.

To address this question, let us begin by examining the coplanar limit. In this limit the acoplanarity angles $\varepsilon _ { 1 , 2 }$ are both zero, and we have from Eq. (47)

$$
{ \frac { d \Gamma } { d \varphi \ d \mathrm { P S } _ { \gamma , \theta } } } = { \mathcal { A } } _ { \gamma , \theta } ^ { \mathrm { c o } } + { \mathcal { B } } _ { \gamma , \theta } ^ { \mathrm { c o } } \mathrm { c o s } ( 2 \xi + 2 \varphi ) \ .
$$

In the coplanar limit the size of the modulation is given by

$$
\frac { \mathcal { B } _ { \gamma , \theta } ^ { \mathrm { c o } } } { \mathcal { A } _ { \gamma , \theta } ^ { \mathrm { c o } } } = \prod _ { i = 1 , 2 } \frac { \mathcal { R } _ { i } ( 1 - \gamma _ { i _ { + } } \theta _ { i _ { + } } \gamma _ { i _ { - } } \theta _ { i _ { - } } ) ^ { 2 } } { ( 1 + \gamma _ { i _ { + } } ^ { 2 } \theta _ { i _ { + } } ^ { 2 } ) ( 1 + \gamma _ { i _ { - } } ^ { 2 } \theta _ { i _ { - } } ^ { 2 } ) + \mathcal { R } _ { i } ( \gamma _ { i _ { - } } \theta _ { i _ { - } } + \gamma _ { i _ { + } } \theta _ { i _ { + } } ) ^ { 2 } } ~ ,
$$

where $\mathcal { R } _ { i } \equiv 2 \gamma _ { i _ { + } } \gamma _ { i _ { - } } / ( \gamma _ { i _ { + } } ^ { 2 } + \gamma _ { i _ { - } } ^ { 2 } )$ . The ratio $B ^ { \mathrm { c o } } / \mathcal { A } ^ { \mathrm { c o } }$ is small when $\gamma \theta \sim 1$ , i.e. near the peak of the square matrix element, but $\mathcal { B } ^ { \mathrm { c o } } / \mathcal { A } ^ { \mathrm { c o } } \to 1$ ，for $\gamma \theta \gg 1$ and $\gamma _ { \pm }$ not much bigger than $\gamma _ { \mp }$ . An example is shown in Fig. 8, where $E _ { i \pm }$ and $\theta _ { i \pm }$ are held fixed such that $\theta _ { i _ { \pm } } \gg m / E _ { i _ { \pm } }$ and $\gamma _ { + } \sim \gamma _ { - }$ . In this slice of phase space the azimuthal oscillation amplitude is large and there is a strong sensitivity to CPV. This shows that regions of phase space with large CPV signals exist.

# D. CPV enhancing cuts

We now use the results from Sec.IVB to design kinematic cuts that enhance the sensitivity of $d \Gamma / d \varphi$ to CP violation. That is,we seek to enhance the ratio $\langle B \rangle / \langle A \rangle$ for a particular subset of the HBH event sample. The cuts we propose fall into two classes: those which are placed on the kinematics of the whole event; and those which are placed independently on individual photons and their daughter leptons. As they use all of the information in the event, including correlations among the two photons,one might expect that the former produce better CPV signals compared to the latter. As we shall see,however, both classes of cuts perform approximately equally well in enhancing $\langle B \rangle / \langle A \rangle$ on their respective phase space subregions.

![](images/c458aae6d3442548bb09499645aea6068c8b01854c7e025271de5c7f827718b2.jpg)

FIG.8. Left: Illustration of $\mathcal { O } ( 1 )$ oscillations and phase shifts in the HBH differential rate for a sample coplanar kinematic configuration. The azimuthal angle $\varphi$ in this slice is defined as in Eq. (46). The kinematic configuration is: $E _ { i _ { + } } = E _ { i _ { - } } = m _ { h } / 4 , \ \theta _ { i _ { + } } = 1 0 ^ { - 4 } , \ \theta _ { i _ { - } } = 2 \theta _ { i _ { + } }$ so that （204号 $\gamma _ { \pm } \theta _ { \pm } \sim 1 0 \gg 1$ and $\gamma _ { + } = \gamma _ { - }$ , cf. analysis of Eq. (51). Right: The azimuthal distribution $d \Gamma / d \varphi$ （204号 for $\xi = 0$ and for $\xi = \pi / 4$ with a polar angle cut $\theta _ { i _ { \pm } } > 1 0 ^ { - 5 }$ and $\theta _ { \ell \ell } > 1 0 ^ { - 5 }$ . The modulation amplitude is 2%, but will grow to $\mathcal { O } ( 1 )$ once optimization cuts are applied, see Sec. V D.

# 1. Cuts on collective kinematics

The helicity interference terms (32) in the HBH rate arise dominantly from the term Re(αl12@1iα212α2ie-2iε).We can use this observation to pick only events in which α12@121@212α2, is comparable to the rest of the squared amplitude. With reference to Eqs. (33) and (34) we thus introduce several sensitivity parameters $\mathcal { T } _ { n }$

$$
{ \mathcal T } _ { n } \equiv { \mathcal X } _ { n } \bigg / \bigg [ \Big | \alpha _ { 1 _ { 1 1 } } ^ { - } \alpha _ { 2 _ { 1 1 } } ^ { - } \Big | ^ { 2 } + \sum _ { j \ne k \atop r _ { k } \ne s _ { k } } \Big | \alpha _ { j _ { 1 1 } } ^ { - } \alpha _ { k _ { r s } } ^ { - } \Big | ^ { 2 } + { \mathcal X } _ { n } \bigg ] ,
$$

where $n = M ^ { ( \prime ) } , R ^ { ( \prime ) } , J ^ { ( \prime ) }$ ，with

$$
\begin{array} { r l } { { \displaystyle \mathcal { X } _ { \mathrm { M } } = 4 | \alpha _ { 1 _ { 1 2 } } ^ { - } \alpha _ { 1 _ { 2 1 } } ^ { - } \alpha _ { 2 _ { 1 2 } } ^ { - } \alpha _ { 2 _ { 2 1 } } ^ { - } | \ , } } & { { \displaystyle \mathcal { X } _ { \mathrm { R } } = 4 \mathrm { R e } [ \alpha _ { 1 _ { 1 2 } } ^ { - } \alpha _ { 1 _ { 2 1 } } ^ { - } \alpha _ { 2 _ { 1 2 } } ^ { - } \alpha _ { 2 _ { 2 1 } } ^ { - } ] \ , \quad { \mathcal { X } } _ { \mathrm { J } } = 4 \mathrm { I m } [ \alpha _ { 1 _ { 1 2 } } ^ { - } \alpha _ { 1 _ { 2 1 } } ^ { - } \alpha _ { 2 _ { 2 1 } } ^ { - } ] \ , } } \\ { { \mathrm { a n d } \qquad } } & { { \displaystyle \mathcal { X } _ { \mathrm { M } ^ { \prime } , \mathrm { R } ^ { \prime } , \mathrm { J } ^ { \prime } } = \sum _ { j \neq k } \Big | \alpha _ { j { r } _ { \mathrm { s } } } ^ { - } \alpha _ { k _ { \rho \sigma } } ^ { - } \Big | ^ { 2 } + { \mathcal { X } } _ { \mathrm { M , R , J } } \ . } } \\ { { \qquad } } & { { \displaystyle r \neq s , \rho \neq \sigma } } \end{array}
$$

The first two terms of the denominator in Eq. (52) are simply the $\xi$ independent parts of the HBH squared amplitude (31),while the $\mathcal { X } _ { n }$ 's are various pieces of the interference terms. In particular, $\mathcal { T } _ { \mathrm { M } }$ is the magnitude of the full leading order interference term，while $\mathcal { T } _ { \mathrm { R , J } }$ （204号 are respectively the CP-even and CP-odd interference terms. We expect each to be useful gauge of sensitivity to CPV independent of $\xi$ . For example, cuts on $\tau _ { \mathrm { { R } } }$ and $\tau _ { \mathrm { J } }$ will enhance the azimuthal modulations in the $\xi = 0$ and $\xi = \pi / 4$ respectively,and can thus be used to distinguish among these. In all cases $\mathcal { T } _ { i } \to 1$ ( $\mathcal { T } _ { i } \to 0$ ）implies full (no) CPV sensitivity.

For all numerical analysis we use three private Monte Carlo codes that were cross-checked. The details on Monte Carlo event generation can be found in Appendix F. Placing a cut on $\mathcal { T } _ { n }$ produces an event sample with large $\langle B \rangle / \langle A \rangle$ ratio. This is shown in Fig. 9 for opening angle cut $\theta _ { \ell \ell } > 1 0 ^ { - 5 }$ and in Fig. 10 for opening angle cut of $\theta _ { \ell \ell } > 1 0 ^ { - 4 }$ . The $d \Gamma / d \varphi$ （20 distributions are shown for two choices of CPV parameters, $\xi = 0$ (blue histograms） and （204号 $\xi = \pi / 4$ (red histograms). The fits to the functional form (48) of the $d \Gamma / d \varphi$ HBH differential rate are shown as solid blue and dot-dashed red lines,respectively. The eficiencies of the cuts for the examples shown in Figs. 9 and 10 are $\sim 1 \%$ for the upper panels and $\sim 0 . 1 \%$ （20 for the lower panels (the exact values of efficiencies depend on the value of $\xi$ ). The presence of $\xi \neq 0$ exhibits itself as the expected phase shift in $d \Gamma / d \varphi$ differential rate (48).

From Figs. 9 and 1O we see that it is possible to select regions of phase space such that $\langle B \rangle / \langle A \rangle \sim \mathcal { O } ( 1 )$ . In particular the average modulation $\langle B \rangle / \langle A \rangle$ is large (small) for $\xi = 0$ （ $\xi = \pi / 4$ ）for $\mathcal { T } _ { \mathrm { R , R ^ { \prime } } }$ and vice versa for $\mathcal { T } _ { \mathrm { J } , \mathrm { J ^ { \prime } } }$ as shown most strikingly in the bottom panels. In contrast, the average modulation size does not depend on $\xi$ for the events selected by $\mathcal { T } _ { \mathrm { M } }$ . This suggests that using several of the parameters $\mathcal { T } _ { n }$ simultaneously may optimize the sensitivity to CPV further.

# 2. Cuts on individual photon conversions

We now turn to discuss cuts on individual photon branches of the HBH process. These cuts are generated by simple sufficiency conditions, that ensure a large CPV signal.

From Eqs. (31) and (32), in order to ensure that the $\xi$ -dependent terms are comparable to the full rate, it suffices to require $| \alpha _ { i _ { 1 2 } } ^ { - } \alpha _ { i _ { 2 1 } } ^ { - } | \gtrsim | \alpha _ { i _ { 1 1 } } ^ { - } | ^ { 2 }$ on each branch ( $i = 1 , 2$ ) independently. For the case that the Higgs is at rest,using (36),this suffciency condition is implied by $s \gtrsim 1$ for each branch,where

$$
S \equiv 2 ( 1 - \cos \delta ) \left[ \frac { \gamma _ { + } \gamma _ { - } } { ( \gamma _ { + } + \gamma _ { - } ) ^ { 2 } } \right] \left[ \frac { \gamma _ { + } \theta _ { + } \gamma _ { - } \theta _ { - } } { ( \gamma _ { + } ^ { 2 } \theta _ { + } ^ { 2 } - \gamma _ { - } ^ { 2 } \theta _ { - } ^ { 2 } ) ^ { 2 } } \right] ( 1 + \gamma _ { + } ^ { 2 } \theta _ { + } ^ { 2 } ) ( 1 + \gamma _ { - } ^ { 2 } \theta _ { - } ^ { 2 } ) ~ .
$$

For brevity, we have dropped the Latin branch index, and here $\delta \equiv | \phi _ { - } - \phi _ { + } | - \pi$ is the acoplanarity angle.

![](images/7ffad481eb9989ec8b91efc5bfbfe43b585f0ce071fd029775126fd912dc2c1d.jpg)

FIG.9. The differential HBH rate $d \Gamma / d \varphi$ as a function of the azimuthal angle $\varphi$ between the positrons setting the CPV parameter to $\xi = 0$ (blue histograms） and $\xi = \pi / 4$ (red histograms). The histograms are binned Monte Carlo events with different cuts on parameters $\mathcal { T } _ { n }$ ，Eq. (52), as denoted in the panels. The solid blue (red dot-dashed) curves are the result of fitting the normalized binned events to Eq. (50) for the $\xi = 0$ ( $\xi = \pi / 4$ ）cases with $\xi$ also floated in the fit. The angular resolution cut is $\theta _ { \ell \ell } > \theta _ { \mathrm { c u t } } = 1 0 ^ { - 5 }$ ：

It is notable that this sufficiency condition weights the desirable energy-polar angle regions of phase space inversely by the amount of acoplanarity. Specifically, ${ \cal { S } } = 0$ in the exact coplanar configuration $\delta = 0$ . Of course, $\boldsymbol { S }$ is not a necessary condition for a large CPV signal, so relatively coplanar events - i.e. events for which $\delta \ll \delta _ { \mathrm { c u t } }$ of the event sample ( $\delta _ { \mathrm { c u t } } = 0 . 4 \pi$ or $0 . 2 5 \pi$ for our MC, see App. F） - may in principle significantly contribute to large CPV signals in $d \Gamma / d \varphi$ . Also note that symmetric conversions,i.e. $\gamma _ { + } \theta _ { + } \simeq \gamma _ { - } \theta _ { - }$ ，are more likely to produce a large $\boldsymbol { S }$ ，and hence a strong interference effect.

Fig. 11 shows the results of the $S _ { 1 , 2 } > 1$ cut for the angular resolution cut (38) $\theta _ { \mathrm { c u t } } = 1 0 ^ { - 5 }$ （204号 for $\xi = 0$ compared to $\xi = \pi / 2 0$ (top left） or $\pi / 4$ (top right). Note we also constrain the acoplanarity $\delta _ { 1 , 2 } \in [ 3 \pi / 4 , 5 \pi / 4 ]$ ， since we do not expect extremely acoplanar events to encode polarization information. The angular resolution cut alone retains approximately $4 0 \%$ of the total HBH events on this acoplanar domain； for $\xi = \pi / 4$ ， the corresponding azimuthal distribution is shown in Fig. 8. The addition of the $S _ { 1 , 2 } > 1$ cut reduces the cut efficiency to $2 . 6 \%$ ， but unlike Fig. 8, now $\langle B \rangle / \langle A \rangle \sim \mathcal { O } ( 0 . 2 )$ . The phase shift due to non-zero $\xi$ is clearly visible in both plots,and the value of $\xi$ extracted from the fits agrees with the input values of $\xi = \pi / 2 0$ or $\pi / 4$ respectively.

![](images/2512cf2869c038bbb63a21bace037ad9f1b52d8687951525c536b072c44e2703.jpg)  
FIG. 10. The same as in Fig. 9,but with the opening angle cut $\theta _ { \ell \ell } > \theta _ { \mathrm { c u t } } = 1 0 ^ { - 4 }$

Finally, the bottom panels of Fig. 11 displays the acoplanarity on each branch for the （204号 $\xi = \pi / 4$ HBH events with no $\boldsymbol { S }$ cut compared to the $S _ { 1 , 2 } > 1$ cuts. We see that the $\boldsymbol { S }$ cut mildly favors acoplanar events, as it broadens the acoplanarity distribution and disfavors relatively coplanar events. For example, we see that events with acoplanarity $\delta < 1 \%$ are disfavored in the cut distribution,and we also see that the full width at half maximum of the acoplanar distribution increases by $5 0 \%$ ， from $0 . 0 4 \pi$ to $0 . 0 6 \pi$ ,under the $S > 1$ cut. The excellent performance of $\boldsymbol { S }$ compared to $\mathcal { T } _ { n }$ cuts (see Fig. 12 and Sec. VD3 below) therefore suggests that acoplanar events - e.g. with $\delta \ll \delta _ { \mathrm { c u t } }$ - play an important role in encoding the CPV signal.

![](images/0404825494c73549e591fc98c760857edfd8ebb79820260878952f7e21a70344.jpg)

FIG.11. Top panels: The azimuthal distributions $d \Gamma / d \varphi$ for $\xi = 0$ (grey histograms） and for （204号 $\xi = \pi / 2 0 , \pi / 4$ (blue histograms, left and right top panels） with $S _ { 1 , 2 } > 1$ on the domain $\delta _ { 1 , 2 } \in$ $[ 3 \pi / 4 , 5 \pi / 4 ]$ . The solid (dashed) curves denote fits to Eq. (48)，with $\xi$ a free parameter in the fits. The bottom left (right） panel shows the acoplanarity distributions, $d \Gamma / d \delta \phi$ ， $\delta \phi \equiv \left( \phi _ { + } - \phi _ { - } \right)$ （204号 mod $2 \pi$ for each photon branch, displayed by blue and gray histograms respectively, with $\xi = \pi / 4$ （204号 and no $\boldsymbol { S }$ cut ( $S _ { 1 , 2 } > 1$ ). Note that the scale varies between these two plots. The corresponding cumulative acoplanarity distributions $\operatorname { c d f } ( \delta \phi )$ for each branch are denoted by solid black and grey dashed lines on each plot. In all panels the angular resolution cut (38) of $\theta _ { \mathrm { c u t } } = 1 0 ^ { - 5 }$ was applied.

# 3. Cut scheme efficiencies

It remains to determine the efficiency of the above cut schemes. In Fig. 12 we show the CPV signal $\langle B \rangle / \langle A \rangle$ for the various $\mathcal { T } _ { n }$ and $\boldsymbol { S }$ schemes as a function of the fraction of the total MC event sample, not rejected by combined sensitivity and angular resolution cuts. Up to small corrections this fraction is the absolute cut efficiency, see Appendix F for details. For comparison, the data point with only angular resolution cuts is also shown for each plot.

We see that an increase of the CPV signal by an order of magnitude roughly requires an order of magnitude penalty in sample size. Moreover, for high cut efficiencies, the $S _ { i }$ scheme provides the largest CPV signal. In contrast, in the low effciency, but higher signal regions, the $\mathcal { T } _ { n }$ schemes outperform the $S _ { i }$ cuts. To give an idea about the feasibility of this analysis at the (HL/HE-)LHC, Table I gives the expected number of events after the application of the cuts discussed above. These numbers do not inlcude experimental acceptance efficiencies and so will be lower in practice.

The $S _ { i }$ parameter is defined on an individual photon branch, independently of the lepton configurations on the other branch,while $\mathcal { T } _ { n }$ is defined on the configuration of whole HBH events. We therefore might deduce that the main difference between these two schemes is whether they are afected by inter-branch leptonic configurations. If this deduction is correct,then the comparative performance of $S _ { i }$ versus $\mathcal { T } _ { n }$ cuts,shown in Fig. 12, suggest that inter-branch configurations become more important for the extraction of larger CPV signals, but are not important over most of the CPV sensitive phase space.

# E． Triple products

Finally， we briefly comment on the possibility to use CP-odd quantities such as triple products to directly search for CPV. Since the CP odd terms in $| { \mathcal { M } } | ^ { 2 }$ are $C$ even and $P$ （204号 odd,we could consider two such contractions

$$
\tau _ { 1 } = \epsilon ^ { p _ { 1 } } { - } ^ { p _ { 1 } } { + } ^ { p _ { 2 } } { - } ^ { p _ { 2 } } + ,
$$

<html><body><table><tr><td></td><td></td><td>√s|𝐶 [fb-1]σ × BR(h →γγ) [fb]</td><td>Events</td></tr><tr><td>8</td><td>20</td><td>47</td><td>0.24</td></tr><tr><td>14</td><td>3000</td><td>125</td><td>94</td></tr><tr><td>33</td><td>3000</td><td>444</td><td>333</td></tr><tr><td>100</td><td>3000</td><td>1875</td><td>1406</td></tr></table></body></html>

TABLE I. Expected number of events after the application of $\boldsymbol { S }$ or $\tau$ cuts with $\theta _ { \ell \ell } > 1 0 ^ { - 4 }$ to obtain $\langle B \rangle / \langle A \rangle \sim 2 0 \%$ . The Higgs production cross section includes the gluon fusion and VBF channels only and is taken from [56].

![](images/4b61ae08837a654dedc39d5735cccf076fd980f0d3776f70873d7e7b78fe1890.jpg)

FIG.12. Comparison of different sensitivity parameter cut schemes, in terms of cut efficiency, for various angular resolution cuts. The black data point on each plot denotes the eficiency and $\langle B \rangle / \langle A \rangle$ for its angular resolution cut alone, with no enhancements from sensitivity parameter cuts.

and

$$
\tau _ { 2 } = { \frac { 1 } { 4 } } \big ( \epsilon ^ { P p _ { 1 _ { + } } p _ { 2 _ { - } } p _ { 2 _ { + } } } + \epsilon ^ { p _ { 1 _ { - } } P p _ { 2 _ { - } } p _ { 2 _ { + } } } + \epsilon ^ { p _ { 1 _ { - } } p _ { 1 _ { + } } P p _ { 2 _ { + } } } + \epsilon ^ { p _ { 1 _ { - } } p _ { 1 _ { + } } p _ { 2 _ { - } } P } \big ) \ ,
$$

where $P ^ { \mu } = ( M , \mathbf { 0 } )$ is the nucleus momentum,and $\epsilon ^ { p q r s }$ is shorthand for the Levi-Civita contraction $\epsilon ^ { \mu \nu \rho \sigma } p _ { \mu } q _ { \nu } r _ { \rho } s _ { \sigma }$ . In terms of scalar triple products,

$$
\begin{array} { r l } & { \tau _ { 1 } = E _ { 1 _ { + } } p _ { 1 _ { - } } \cdot ( p _ { 2 _ { + } } \times p _ { 2 _ { - } } ) - E _ { 1 _ { - } } p _ { 1 _ { + } } \cdot ( p _ { 2 _ { + } } \times p _ { 2 _ { - } } ) + 1  2 \ , } \\ & { \tau _ { 2 } = M \Big [ p _ { 1 _ { - } } \cdot ( p _ { 2 _ { + } } \times p _ { 2 _ { - } } ) - p _ { 1 _ { + } } \cdot ( p _ { 2 _ { + } } \times p _ { 2 _ { - } } ) + 1  2 \Big ] \ . } \end{array}
$$

Note,that $\tau _ { 2 }$ is not strictly speaking C-even， since it involves the nucleus momentum. However, BH conversion on nucleus is the same as on anti-nucleus within our uncertainties. This is equivalent to leaving $P ^ { \mu }$ unchanged under C transformation. A detailed analysis is beyond the scope of our work, but we remark in passing that a straightforward use of the （204号 $\boldsymbol { S }$ and $\mathcal { T } _ { n }$ cuts does not lead to appreciable non-zero value of $\langle \tau \rangle$ . Further investigation is

warranted.

# VI. CONCLUSION

In this work we have studied how to probe the underlying CP couplings of the Higgs to two photons, which undergo Bethe-Heitler conversion on nuclei. We have shown that sensitivity to CP violating couplings is possible only if there is interference between conversion amplitudes with different photon helicity. Using spinor helicity methods,we have computed compact,leading order expressons for these amplitudes, which are novel to this work.Ouraalyticalcontrolof theleadingorder $h  \gamma \gamma \stackrel { B H } {  } 4 e$ flldiferentil catring rate permits us to show that: (i) the differential rate with respect to the relative azimuthal angles between leptons with different parent photons is oscillatory; (ii) CPV is encoded as a phase shift in such distributions; and (ii) we may construct various sensitivity parameter cuts that extract the regions of phase space on which such oscillations - the CPV signal - are order unity on average. These analytical results have been confrmed and explored with numerical simulations, including a comparison of the relative efectiveness of the different sensitivity parameters.

For simplicity we restricted our numerical and CP sensitivity analysis to the case that the Higgs is at rest in the lab frame. This is not the case in the LHC experiments,and this assumption needs to be lifted for more realistic studies. We note, in this vein,that Eqs. (B3) hold also for the boosted Higgs case,although Eqs. (36) do not. The sensitivity parameter cut schemes are expected to work comparatively well in the case that the Higgs is boosted, too.On a similar note,we expect these sensitivity cuts to enhance the full matrix element method. This method, as characterized by the parameter $Z _ { B } ^ { \mathrm { c } }$ ， appears to be a few times more sensitive to CPV than experiments measuring a single relative azimuthal angle. This leaves open the possbility of further improved CPV signals, compared to those shown in this work.

We do not expect a $h  \gamma \gamma \stackrel { B H } {  } 4 e$ experiment to be straightforward,and further experimental and theoretical studies are needed in order to see if the methods discussed in this paper can be used in practice. From an experimental viewpoint, it needs to be determined how well one can reconstruct the electron and positron momenta for opening angles $\sim 1 0 ^ { - 4 }$ （204号 or even down to $\sim m / m _ { h } \sim 1 0 ^ { - 5 }$ ，and whether there are significant rescatterings after BH production. Already from our preliminary studies it is clear that large statistical datasets and fine granularity of the detectors will be needed, such as at the proposed HE-LHC, VLHC or TLEP [57]. Experimentally, the situation may be more favorable in such a machine, having a larger amount of statistics and better kinematic control of the Higgs. A completely independent direction for measuring the CP violating coupling of Higgs to photons - and a direction not explored in this paper - would be the use of polarized photon beams at a photon collider. From a theoretical viewpoint,it also remains to determine and search for other CPV sensitive observables apart from the azimuthal distributions discussed here.

Lastly， while we focussed on Higgs diphoton decays in this work, most of this analysis holds for any pair of correlated photons. They can arise from a resonance, like the Higgs, or from scattering events. While the details have to be determined in a case-by-case basis, the principles, such as helicity interference,are the same.

# ACKNOWLEDGMENTS

We thank Yang Bai, Kfir Blum, John-Paul Chou, Lance Dixon, Andrei Gritsan，Ben Heidenreich， Kirill Melnikov, Michael Peskin，Mike Sokoloff,Roberto Vega-Morales and Ciaran Wiliams for helpful discussions. We also expressly thank Jacob Meisler for the development of the Monte-Carlo unweighting Java/C++ code, used in part of the numerical analysis in this work. FB is supported in part by the Fermilab Fellowship in Theoretical Physics. The work of YG and DR is supported by the U.S. National Science Foundation through grant PHY-0757868 and by the United States-Israel Binational Science Foundation (BSF) under grant No. 2010221. The work of DR is also supported by the U.S. National Science Foundation under Grant No. PHY-1002399. JZ was supported in part by the U.S. National Science Foundation under CAREER Grant PHY-1151392. We thank the Aspen Center for Physics and the NSF Grant #1066293 for hospitality during the conception of this work. We would also like to thank KITP for warm hospitality during the completion of this work and acknowledge that this research was supported in part by the National Science Foundation under Grant No. NSF PHY11-25915. Fermilab is operated by the Fermi Research Aliance,LLC under Contract No. De-AC02-07CH11359 with the United States Department of Energy.

# Appendix A:Spinor-helicity formalism

In this paper we extensively use the spinor-helicity formalism,in which the sigma matrices $\boldsymbol { \sigma } _ { a \dot { a } } ^ { \mu }$ solder null momenta to Weyl spinors, that transform under the spinor irreducible representations of the covering group SL(2, $\mathbb { C }$ ). For a review see e.g. Ref. [58] or [59].

For a null momentum $k$ , the associated Weyl spinors $\lambda _ { k }$ are soldered via

$$
k ^ { \mu } = \frac { 1 } { 2 } \langle k ^ { \pm } | \sigma ^ { \mu } | k ^ { \pm } \rangle \ , \qquad \nk \equiv k _ { \mu } \sigma _ { a \dot { a } } ^ { \mu } = ( \lambda _ { k } ) _ { a } ( \lambda _ { k } ) _ { \dot { a } } \ ,
$$

in which we have written the dotted and undotted Weyl spinors in the notation

$$
\langle k ^ { - } | \equiv ( \lambda _ { k } ) ^ { a } \ , \qquad \langle k ^ { + } | \equiv ( \lambda _ { k } ) _ { \dot { a } } \ , \qquad | k ^ { + } \rangle \equiv ( \lambda _ { k } ) _ { a } \ , \qquad | k ^ { - } \rangle \equiv ( \lambda _ { k } ) ^ { \dot { a } } \ ,
$$

s0 $\langle k ^ { + } | \sigma ^ { \mu } | \ell ^ { + } \rangle = ( \lambda _ { k } ) _ { \dot { a } } \sigma ^ { \mu \dot { a } a } ( \lambda _ { \ell } ) _ { a } $ ， $\langle k ^ { - } | \sigma ^ { \mu } | \ell ^ { - } \rangle = ( \lambda _ { k } ) ^ { a } \sigma _ { a \dot { a } } ^ { \mu } ( \lambda _ { \ell } ) ^ { \dot { a } }$ . Upper and lower indices are related by the usual epsiloncontractions,in particular $\sigma _ { \mu } ^ { \dot { a } a } \equiv \epsilon ^ { a b } \epsilon ^ { \dot { a } \dot { b } } \sigma _ { \mu _ { b } \dot { b } }$ . In this notation, the sign superscripts denote the helicities of the in-going and out-going states, corresponding to kets and bras respectively. In particular, note that $| k ^ { \pm } \rangle ^ { \dagger } = \langle k ^ { \pm } |$ by construction, $\langle k ^ { \pm } | \sigma ^ { \mu } | \ell ^ { \mp } \rangle$ do not exist，while $\langle k ^ { - } | \sigma ^ { \mu } | \ell ^ { - } \rangle = \langle \ell ^ { + } | \sigma ^ { \mu } | k ^ { + } \rangle$ . For null momenta $k$ and $\ell$ we often write the bilinears

$$
\langle k \ell \rangle \equiv \langle k ^ { - } | \ell ^ { + } \rangle = ( \lambda _ { k } ) ^ { a } ( \lambda _ { \ell } ) _ { a } \ , \qquad [ k \ell ] \equiv \langle k ^ { + } | \ell ^ { - } \rangle = ( \lambda _ { k } ) _ { \dot { a } } ( \lambda _ { \ell } ) ^ { \dot { a } } \ ,
$$

S0 $\langle \ell \ k \rangle = - \langle k \ \ell \rangle$ ， $[ \ell \ k ] = - [ k \ \ell ]$ ， $\langle k \ \ell \rangle [ \ell \ k ] = 2 k \cdot \ell$ and $\langle k \ \ell \rangle ^ { * } = [ \ell \ k ]$

In this notation, definite helicity polarization vectors associated to $k$ may have form

$$
\varepsilon ^ { \pm \mu } ( k ; r ) = \pm \frac { \langle r ^ { \mp } | \sigma ^ { \mu } | k ^ { \mp } \rangle } { \sqrt { 2 } \langle r ^ { \mp } | k ^ { \pm } \rangle } ,
$$

with $r ^ { \mu }$ a reference null momentum. One may show via the Fierz relations that these polarization vectors satisfy the axiomatic requirements $\boldsymbol { k } \cdot \varepsilon ^ { \pm } = 0$ ， $\varepsilon ^ { \pm } \cdot ( \varepsilon ^ { \pm } ) ^ { * } = \varepsilon ^ { \pm } \cdot \varepsilon ^ { \mp } = - 1$ and $\varepsilon ^ { \pm } \cdot \varepsilon ^ { \pm } = 0$ . In the present work, a particularly convenient choice of reference momenta is

$$
r _ { 1 } = k _ { 2 } \ , \qquad r _ { 2 } = k _ { 1 } \ ,
$$

where $r _ { 1 , 2 } ~ ( k _ { 1 , 2 } )$ are reference momenta (photon momenta） corresponding to polarization vectors $\varepsilon _ { 1 , 2 } ^ { \pm }$ defined in (7). We shall always make this choice of reference momenta.

The dotted and undotted Weyl spinors have explicit representations in terms of the momentum components in a particular basis,up to a free choice of phase. For example, for

a null momentum $k = \left( k ^ { 0 } , k ^ { 1 } , k ^ { 2 } , k ^ { 3 } \right)$ , a possible choice is

$$
( \lambda _ { k } ) ^ { a } = \left\{ \begin{array} { l } { { \left( \frac { k ^ { 1 } + i k ^ { 2 } } { \sqrt { k ^ { 0 } - k ^ { 3 } } } \ , \ \sqrt { k ^ { 0 } - k ^ { 3 } } \right) \ , k ^ { 3 } < 0 \ , } } \\ { { \left( \sqrt { k ^ { 0 } + k ^ { 3 } } \ , \ \frac { k ^ { 1 } - i k ^ { 2 } } { \sqrt { k ^ { 0 } + k ^ { 3 } } } \right) \ , k ^ { 3 } > 0 \ . } } \end{array} \right.
$$

The components of the upper dotted spinor are immediately specified through the relation $( \lambda _ { k } ) ^ { \dot { a } } = [ ( \lambda _ { k } ) ^ { a } ] ^ { \dagger }$ , and the lower index spinors through appropriate epsilon contractions. With this choice and a choice of basis, all spinor objects - e.g. $\langle k \ell \rangle - \mathrm { c a n }$ be evaluated explicitly, just as momentum objects may be,e.g. $k \cdot \ell$ . Note that for our Weyl spinor phase choice (A6) one has $\langle k _ { 1 } \ k _ { 2 } \rangle = [ k _ { 2 } \ k _ { 1 } ] = m _ { h }$ ：

The Dirac spinors of massive particles may also be represented in the spinor-helicity formalism, via the application of a light-cone decomposition. For a massive spinor of momentum $p$ and mass $m$ ， we define an associated null momentum

$$
{ \tilde { p } } ^ { \mu } = p ^ { \mu } - \frac { m ^ { 2 } } { 2 p \cdot \ell } \ell ^ { \mu } \ , \quad \mathrm { o r \ e q u i v a l e n t l y } \quad p ^ { \mu } = { \tilde { p } } ^ { \mu } + \frac { m ^ { 2 } } { 2 { \tilde { p } } \cdot \ell } \ell ^ { \mu } \ ,
$$

where $\ell ^ { \mu }$ is a null reference momentum. The spinors then decompose similarly as

$$
\begin{array} { l l } { { u ^ { 1 } ( p ) = | \tilde { p } ^ { + } \rangle + \displaystyle \frac { m } { | \tilde { p } \ : \ell | } | \ell ^ { - } \rangle , ~ } } & { { ~ u ^ { 2 } ( p ) = | \tilde { p } ^ { - } \rangle - \displaystyle \frac { m } { \langle \ell \ : \tilde { p } \rangle } | \ell ^ { + } \rangle , } } \\ { { \bar { u } ^ { 1 } ( p ) = \langle \tilde { p } ^ { + } | + \displaystyle \frac { m } { \langle \ell \ \tilde { p } \rangle } \langle \ell ^ { - } | , ~ } } & { { ~ \bar { u } ^ { 2 } ( p ) = \langle \tilde { p } ^ { - } | - \displaystyle \frac { m } { [ \tilde { p } \ : \ell ] } \langle \ell ^ { + } | , } } \\ { { v ^ { 1 } ( p ) = | \tilde { p } ^ { - } \rangle + \displaystyle \frac { m } { \langle \ell \ \tilde { p } \rangle } | \ell ^ { + } \rangle , ~ } } & { { ~ v ^ { 2 } ( p ) = | \tilde { p } ^ { + } \rangle - \displaystyle \frac { m } { [ \tilde { p } \ : \ell ] } | \ell ^ { - } \rangle , } } \\ { { \bar { v } ^ { 1 } ( p ) = \langle \tilde { p } ^ { - } | + \displaystyle \frac { m } { [ \tilde { p } \ : \ell ] } \langle \ell ^ { + } | , ~ } } & { { ~ \bar { v } ^ { 2 } ( p ) = \langle \tilde { p } ^ { + } | - \displaystyle \frac { m } { \langle \ell \ : \tilde { p } \rangle } \langle \ell ^ { - } | ~ . } } \end{array}
$$

One may verify that these spinors satisfy the canonical requirements ${ \bar { u } } u = 2 m$ ， $\bar { v } v = - 2 m$ ， （204号 $\bar { v } u = \bar { u } v = 0$ and the completeness relations $\textstyle \sum _ { j } u ^ { j } { \bar { u } } ^ { j } = p \not p + m$ and $\textstyle \sum _ { j } v ^ { j } { \bar { v } } ^ { j } = { p / } - m$ . Just as for the polarization vectors, one is free to choose the null reference momentum. This choice amounts to a choice of 'gauge', under which the unpolarized square amplitude must be invariant, but the polarized square amplitudes are not. In this work, we shall always make the reference momenta choices

$$
\ell _ { 1 \pm } = k _ { 2 } \quad \mathrm { ~ a n d } \quad \ell _ { 2 \pm } = k _ { 1 } \ .
$$

These are convenient choices for the purposes of extracting the leading order BH helicity amplitudes, as below.

Finally, together with the several well-known spinor identities,the following identity is especially useful for computing terms involving Levi-Civita contractions,

$$
\epsilon ^ { \alpha \beta \gamma \delta } \sigma _ { \alpha } ^ { \dot { a } a } \sigma _ { \beta } ^ { \dot { b } b } \sigma _ { \gamma } ^ { \dot { c } c } \sigma _ { \delta } ^ { \dot { d } d } \equiv 4 i \big ( \epsilon ^ { \dot { d } \dot { a } } \epsilon ^ { b a } \epsilon ^ { \dot { b } \dot { c } } \epsilon ^ { d c } - \epsilon ^ { \dot { d } \dot { c } } \epsilon ^ { b c } \epsilon ^ { \dot { b } \dot { a } } \epsilon ^ { d a } \big ) \ .
$$

# Appendix B:BH spin-helicity amplitudes

Here we write down explicit expressions for the helicity amplitudes $\alpha _ { i _ { r s } } ^ { \pm }$ . From Eqs. (16) and (24) one has (suppressing the branch index)

$$
\begin{array} { l } { \frac { \pm } { r s } = - \displaystyle \frac { i } { 2 q ^ { 2 } } \bar { u } ^ { r } ( p _ { - } ) \left[ \rlap / { \mathcal { F } } ^ { \pm } \frac { p _ { - } - k + m } { k \cdot p _ { - } } \ Q + \ Q \frac { k - p _ { + } + m } { k \cdot p _ { + } } \ q ^ { \pm } \right] v ^ { s } ( p _ { + } ) } \\ { = - \displaystyle \frac { i } { 2 q ^ { 2 } } \left[ \sum _ { j } \left( \frac { \bar { u } ^ { r } \notin ^ { \pm } u ^ { j } \bar { u } ^ { j } \notin v ^ { s } } { k \cdot p _ { - } } - \frac { \bar { u } ^ { r } \notin v ^ { j } \bar { v } ^ { j } \notin ^ { \pm } v ^ { s } } { k \cdot p _ { + } } \right) - \frac { \bar { u } ^ { r } \notin ^ { \pm } k \notin v ^ { s } } { k \cdot p _ { - } } + \frac { \bar { u } ^ { r } \notin k \notin ^ { \pm } v ^ { s } } { k \cdot p _ { + } } \right] , } \end{array}
$$

where $u = u ( p _ { - } )$ and $v = v ( p _ { + } )$ . Applying the light cone decomposition (A8) with reference choices specified in (A4) and (A9), gives the full results for each spin helicity amplitude

$$
\begin{array} { r l } { \tilde { \mathbf { a } } = } & { \{ \begin{array} { l l } { - \mathbf { a } _ { 0 } \mathbf { b } ^ { * } - \mathbf { b } _ { 0 } \mathbf { b } ^ { * } - \mathbf { b } _ { 1 } ^ { * } [ \frac { \mathbf { a } _ { 0 } ^ { * } ( \tilde { \mathbf { b } } _ { 0 } ^ { * } - \mathbf { b } _ { 2 } ) \tilde { \mathbf { b } } _ { 0 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) } { \mathbf { b } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) } ( \mathbf { a } _ { 0 } ^ { * } + \frac { \mathbf { b } _ { 1 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) \tilde { \mathbf { b } } _ { 0 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) } { \mathbf { b } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) } ( \mathbf { b } _ { 0 } ^ { * } )  } \\ {  - \mathbf { a } _ { 0 } ^ { * } \mathbf { b } _ { 0 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) - \mathbf { b } _ { 0 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) ( \mathbf { b } _ { 0 } ^ { * } ) + \mathbf { a } _ { 0 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) ( \mathbf { b } _ { 0 } ^ { * } ) ( \mathbf { b } _ { 0 } ^ { * } ) ( \mathbf { b } _ { 0 } ^ { * } ) \tilde { \mathbf { b } } _ { 0 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) } \end{array}  } \\ &  \quad \quad - \frac  \mathbf { a } _ { 0 } ^ { * } \mathbf { b } _ { 0 } ^ { * } \mathbf { b } _ { 0 } ^ { * } \mathbf { b } _ { 0 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) ^ { 2 } ( \mathbf { b } _ { 0 } ^ { * } ) ^ { 2 } ( \mathbf { b } _ { 0 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) + \frac  \mathbf { b } _ { 0 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) ^ { 2 } ( \mathbf { b } _ { 0 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) + \frac  \mathbf { b } _ { 0 } ^ { * } ( \mathbf { b } _ { 0 } ^ { * } ) ^ { 2 } ( \mathbf { b } _ { 0 } ^ { * } ) ^ { 2 } ( \mathbf { b } _ { 0 } ^  \end{array}
$$

$$
+ \frac { m [ \ell \tilde { p } _ { + } ] \langle k \tilde { p } _ { + } \rangle \langle \ell ^ { + } | \mathcal { Q } | \tilde { p } _ { + } { ^ { + } } \rangle } { k \cdot p _ { + } [ k \ell ] [ \ell \tilde { p } _ { - } ] } - \frac { m \langle k \tilde { p } _ { - } \rangle \langle \ell ^ { + } | \mathcal { Q } | \tilde { p } _ { + } { ^ { + } } \rangle } { k \cdot p _ { - } [ k \ell ] } ] .
$$

As per the main text, we have dropped the photon subscripts,and $k , \ell = k _ { 1 } , k _ { 2 }$ or $k _ { 2 } , k _ { 1 }$ for parent photon 1 and 2 respectively. Squaring these amplitudes, taking traces and summing, one obtains the full Bethe-Heitler square amplitude that is obtained by the usual Feynman methods.

We can further extract dominant terms of the BH spin-helicity amplitudes by observing that if $q _ { i } \ll m _ { h }$ ，then $\langle k _ { 1 } k _ { 2 } \rangle \gg \langle k _ { i } p _ { i _ { \pm } } \rangle$ etc. Moreover, in expressions such as $\alpha _ { 1 2 } ^ { + }$ or $\alpha _ { 2 1 } ^ { + }$ ，we may discard subdominant $\mathcal { O } ( m ^ { 2 } / k _ { i } \cdot p _ { j \neq i } )$ terms. This leads to the following leading order results in $m ^ { 2 } / k _ { i } \cdot p _ { j \neq i }$ and $\langle k _ { i } \ p _ { i } \rangle / \langle k _ { 1 } \ k _ { 2 } \rangle$ for the BH spin-helicity amplitudes

$$
\begin{array} { r l } { \iota _ { 1 1 } = - ( \alpha _ { 2 , 3 } ^ { \ast } ) ^ { \ast } \simeq \frac { m } { q ^ { 2 } \sqrt { 2 } } [ \frac { \langle k \bar { F } ; \bar { \phi } | \bar { \phi } | k ^ { \prime } \rangle } { k \cdot p _ { + } \xi \bar { k } + \bar { \phi } } - \frac { \langle \bar { F } ; \bar { \phi } | \bar { \phi } | k \bar { p } ; | \bar { \phi } | k ^ { \prime } \rangle } { k \cdot p _ { - } \xi \bar { k } - \bar { \phi } } ] , } & { } \\ { \bar { \iota } _ { 1 2 } ^ { \ast } = } & { ( \alpha _ { 2 , 1 } ^ { \ast } ) ^ { \ast } \simeq \frac { \langle k \bar { F } ; \bar { \phi } _ { - } | \bar { \phi } | k ^ { \prime } \rangle - \langle \bar { F } | \bar { \phi } | k ^ { \prime } \rangle } { q ^ { 2 } \sqrt { 2 k } \cdot p _ { + } q } - \frac { [ \langle \bar { F } - \bar { \phi } ] \bar { k } \bar { p } - \sqrt { \bar { k } \bar { p } } ; | \bar { \phi } | k ^ { \prime } \rangle } { q ^ { 2 } \sqrt { 2 k } \cdot p _ { - } [ k \bar { \xi } ] } + \frac { [ \bar { F } \bar { p } + ] \bar { k } \bar { p } + \sqrt { \bar { k } \bar { p } } ; | \bar { \phi } | k ^ { \prime } \rangle } { q ^ { 2 } \sqrt { 2 k } \cdot p _ { + } [ k \bar { F } ] } } \\ & { \qquad - \frac { m ^ { 2 } [ k \bar { F } ; \bar { \phi } ] k ^ { \prime } - [ \sigma ^ { 1 } \bar { k } ^ { \prime } ] \bar { \xi } ^ { - 1 } } { q ^ { 2 } \sqrt { 2 k } \cdot p _ { - } [ \bar { F } ; p _ { + } ] \{ \bar { \xi } ^ { - 1 } \} k ^ { \prime } } , } \\ { \bar { \iota } _ { 2 1 } ^ { \ast } = } &  ( \alpha _ { 1 , 2 } ^ { \ast } ) ^ { \ast } = - \frac { \langle \bar { F } ; \bar { \phi } | \bar { \phi } | \bar { \phi } | k ^ { \prime } \rangle } { q ^ { 2 } \sqrt { 2 k } \cdot p _ { - } \xi [ \bar { F } ; \bar { \phi } | k ^ { \prime } ] [ \bar { F } ; \bar { \phi } | k \bar { \phi } ] } + \frac { [ \bar { F } ; \bar { \phi } | \bar { \phi } | k ^ { \prime } ] \bar { \phi } }  q ^ { 2 } \sqrt { 2 k } \cdot p _ { - } \xi [ \bar { F } ; \bar { \phi } ] [ \bar { F } ; \end{array}
$$

in which we have dropped the photon subscripts,and uniform overall signs or factors of $i$ （204号 $k , \ell = k _ { 1 } , k _ { 2 }$ or $k _ { 2 } , k _ { 1 }$ for photon 1 and 2 respectively; and the spinor notation is detailed in Appendix A. The parity relations (29) are satisfied as expected. Eqs. (28) and (B3) together provide a compact expression of the leading order HBH square amplitude.

It should be understood that the particular form for the spin helicity amplitudes above depends on the choice of reference momenta, because the amplitudes explicitly depend on polarization vectors and spinors (see App. A). Moreover, the ability to straightforwardly expand the full results to the leading order results depends on a sensible choice of reference momenta. In contrast,the full unpolarized BH rate is independent of polarizations and spinors, as a result of spinor and polarization vector completeness,and therefore must be independent of any such reference momenta choice.

# Appendix C:Polarization-decomposed HBH rate

Here we give the explicit results of a Higgs-Bethe-Heitler Feynman type calculation. To preempt the loss of numerical precision from large cancellations due to the Ward identity, we do not use polarization completeness relations. Rather,we retain the polarization vectors explicitly in the HBH rate. In the case that the Higgs is at rest in the lab frame,we simply use a Cartesian basis for the polarization vectors, aligning the back-to-back photons with the $z$ -axis. That is, in the HBH square amplitude we coherently sum over the polarization basis

$$
\epsilon _ { \mu } ^ { 1 } ( k _ { 1 , 2 } ) = ( 0 , 1 , 0 , 0 ) \quad \mathrm { a n d } \quad \epsilon _ { \mu } ^ { 2 } ( k _ { 1 , 2 } ) = ( 0 , 0 , 1 , 0 ) \ .
$$

The squared matrix element for the process $h + N _ { 1 } + N _ { 2 }  \gamma ( k _ { 1 } ) \gamma ( k _ { 2 } ) + N _ { 1 } + N _ { 2 } $ $4 \ell + N _ { 1 } ^ { \prime } + N _ { 2 } ^ { \prime }$ is given by

$$
\mathcal { M } | ^ { 2 } = \mathcal { A } ^ { \mu \nu } \mathcal { A } ^ { * \alpha \beta } { \sum _ { \mathrm { { p o l s } } \atop \mathrm { { a , b , c , d } } } } \left[ \epsilon _ { \mu } ^ { a * } ( k _ { 1 } ) \epsilon _ { \nu } ^ { b * } ( k _ { 2 } ) \epsilon _ { \alpha } ^ { c } ( k _ { 1 } ) \epsilon _ { \beta } ^ { d } ( k _ { 2 } ) \epsilon _ { \mu ^ { \prime } } ^ { a } ( k _ { 1 } ) \epsilon _ { \alpha ^ { \prime } } ^ { c * } ( k _ { 1 } ) \epsilon _ { \nu ^ { \prime } } ^ { b } ( k _ { 2 } ) \epsilon _ { \beta ^ { \prime } } ^ { d * } ( k _ { 2 } ) \right] { \mathrm { B H } } _ { 1 } ^ { \mu ^ { \prime } }
$$

where the tensor ${ \mathcal { A } } ^ { \mu \nu }$ is

$$
\mathcal { A } ^ { \mu \nu } = c \left( k _ { 1 } \cdot k _ { 2 } g ^ { \mu \nu } - k _ { 2 } ^ { \mu } k _ { 1 } ^ { \nu } \right) + \tilde { c } \epsilon ^ { \alpha \mu \beta \nu } k _ { 1 \alpha } k _ { 2 \beta } \ .
$$

The $\mathrm { B H } _ { i }$ factors are the polarized Bethe-Heitler squared amplitudes for a photon $i$ , including form factor contributions, these are in general

$$
\begin{array} { r l } & { \mathrm { B H } ^ { \alpha \beta } = \frac { e ^ { \mathrm { i } \Phi } } { q ^ { 4 } \left( \tilde { S } ^ { \varepsilon } - p _ { 1 } \right) ^ { 2 } \left( k ^ { * } - p _ { 2 } \right) + q ^ { 3 } } \Bigg \{ \Big [ 2 ( k \cdot p ) \left( k \cdot p _ { 1 } \right) \left( 2 k ^ { * } \ \mathcal { F } _ { 1 } - m ^ { 2 } - p _ { 1 } \ \cdot \mathcal { F } _ { 2 } \right) E _ { k } ^ { * } } \\ & { \quad + \frac { 8 E _ { k - p _ { 1 } } } { 3 \mathrm { i } d } \langle E _ { k } \cdot p _ { 1 } \rangle ^ { 2 } ( k \cdot p _ { 2 } ) B _ { 2 p _ { k } } ^ { * } + ( k \cdot p _ { 1 } ) ^ { 2 } ( 4 k ^ { * } ) ^ { 2 } + q ^ { 2 } \| \mathcal { F } _ { \infty } ^ { * \beta } + ( p _ { 1 } \ \ j \ \rho ) } \\ & { \quad - 8 ( k \cdot p _ { 2 } ) ^ { 2 } ( k \cdot p _ { 2 } ) \frac { p _ { 2 } ^ { \prime } p _ { k } ^ { \prime } \mathcal { F } _ { 1 } } { 3 d ^ { 2 } } } \\ & { \quad - \frac { 2 } { 3 d } \langle \tilde { S } \cdot p _ { - } | ( k \cdot p _ { 2 } ) | \langle k \cdot p _ { 2 } \rangle - 2 ( 1 \mathcal { E } _ { - } ( k \cdot p _ { - } ) + \mathcal { F } _ { + } ( k \cdot p _ { - } ) ) \big ] E _ { p _ { k } } ^ { * \beta } } \\ & { \quad + 2 ( k \cdot p _ { - } ) ( k \cdot p _ { + } ) ( q ^ { 2 } - 1 \mathcal { E } _ { - } E _ { + } ) B _ { p _ { k } } ^ { * } , } \\ & { \quad + 2 ( k \cdot p _ { - } ) ( k \cdot p _ { + } ) \left( [ k \cdot p _ { - } + k \cdot p _ { - } ) ^ { 2 } + q ^ { 2 } E _ { - } ^ { * } , q ^ { \beta } \right. } \\ & { \quad \left. - 4 ( k \cdot p _ { - } ) ( k \cdot p _ { - } ) \left( 2 E _ { - } \mathcal { F } _ { + } - m ^ { 2 } - p \cdot \mathcal { F } _ { - } ^ { * } \right) E _ { - } ^ { * } \mathcal { F } _ { + } ^ { * } \right) \Bigg \} \ , } \end{array}
$$

where $\mathcal { F } _ { \ell } ^ { a b } = \ell ^ { a } k ^ { b } + \ell ^ { b } k ^ { a } - 2 \ell ^ { a } \ell ^ { b }$ and $\displaystyle B _ { \ell _ { 1 } \ell _ { 2 } } ^ { a b } = \ell _ { 1 } ^ { a } \ell _ { 2 } ^ { b } + \ell _ { 1 } ^ { b } \ell _ { 2 } ^ { a }$ . The photon momentum is denoted by $k$ and the lepton momenta by $p _ { + }$ ， $p _ { - }$ ： $M$ and $m$ are the masses of the nucleus and lepton

respectively. Assuming that the Higgs is at rest in the lab frame and that the photon is in the $z$ -direction, as in Eq. (C1), the previous expression simplifies to

$$
\simeq \frac { 2 e ^ { 6 } \mathcal { G } } { q ^ { 4 } } \left\{ \frac { g ^ { a b } \left[ E _ { \gamma } ^ { 2 } q ^ { 2 } + ( k \cdot p _ { - } + k \cdot p _ { + } ) ^ { 2 } \right] } { ( k \cdot p _ { - } ) ( k \cdot p _ { + } ) } - 4 \left( \frac { E _ { p _ { + } } p _ { - } ^ { a } } { k \cdot p _ { - } } + \frac { E _ { p _ { - } } p _ { + } ^ { a } } { k \cdot p _ { + } } \right) \left( \frac { E _ { p _ { + } } p _ { - } ^ { b } } { k \cdot p _ { - } } + \frac { E _ { p _ { - } } p _ { - } ^ { a } } { k \cdot p _ { - } } \right) \right\} ,
$$

where, in the second term，we expanded terms of the form $\sqrt { 4 E ^ { 2 } \pm q ^ { 2 } }$ to leading order in $q ^ { 2 } / E ^ { 2 }$ . We have checked that the helicity formalism results and the Feynman diagram calculation results for HBH rate agree.

Finally, the unpolarized BH rate can be obtained from Eq.(C5) simply by averaging over the photon polarization as follows

$$
\langle | { \cal M } | ^ { 2 } \rangle = 1 / 2 \left( \mathrm { B H } ^ { 1 1 } + \mathrm { B H } ^ { 2 2 } \right) \ .
$$

It is instructive to use the polarization vector completeness relation to obtain an expression in terms of Lorentz dot products. In this case, starting with Eq.(C4), the BH rate is given by

$$
\begin{array} { l } { { \displaystyle \langle | \mathcal { M } | ^ { 2 } \rangle = 2 e ^ { 6 } \mathcal { G } \Bigg ( - 2 \frac { \big ( E _ { - } ^ { 2 } + E _ { + } ^ { 2 } \big ) } { q ^ { 2 } k \cdot p _ { - } k \cdot p _ { + } } + 4 \frac { m ^ { 2 } \big ( k \cdot p _ { - } E _ { - } - k \cdot p _ { + } E _ { + } \big ) ^ { 2 } } { q ^ { 4 } ( k \cdot p _ { - } ) ^ { 2 } ( k \cdot p _ { + } ) ^ { 2 } } } } \\ { { \displaystyle ~ + \frac { m ^ { 2 } \big ( k \cdot p _ { - } + k \cdot p _ { + } \big ) ^ { 2 } } { q ^ { 2 } ( k \cdot p _ { - } ) ^ { 2 } ( k \cdot p _ { + } ) ^ { 2 } } - \frac { k \cdot p _ { - } k \cdot p _ { + } } { ( k \cdot p _ { - } ) ^ { 2 } ( k \cdot p _ { + } ) ^ { 2 } } - 2 \frac { \big ( k \cdot p _ { - } \big ) ^ { 2 } + \big ( k \cdot p _ { + } \big ) ^ { 2 } } { q ^ { 4 } \big ( k \cdot p _ { - } \big ) ( k \cdot p _ { + } ) } } } \\ { { \displaystyle ~ - 2 \frac { k \cdot p _ { - } + k \cdot p _ { + } } { q ^ { 2 } k \cdot p _ { - } k \cdot p _ { + } } \Bigg ) ~ , } } \end{array}
$$

where the leading terms - the terms on the first line - reproduce Eq. (35).

# Appendix D:Numerical simulations of Bethe-Heitler conversion

In this appendix we present numerical evaluations of several differential BH rates. The numerics were done in two ways: by numerically integrating the full tree-level analytical results - i.e. the BH rate arising from Eqs. (B2) or (C4) with appropriate integration measures - using the CUBA library [60]; and with a Monte Carlo (MC) code developed privately (the details are given in Appendix F). Fig. 13 shows the differential distribution of the positron energy fraction $\mathcal { E } _ { + } = E _ { + } / E _ { \gamma }$ . For efficiency the MC simulation (blue binned histogram) is generated with a cut on the difference of electron and positron azimuthal angles, $\delta \phi \equiv ( \phi _ { + } - \phi _ { - } )$ mod $2 \pi \in \left[ 0 . 6 \pi , 1 . 4 \pi \right]$ (see App. F). This agrees with the numerical integration (red line) for the same cuts on $\delta \phi$

![](images/20c86448fa229f1ee9721c63c9b5036cbd9c5c2458b978224cd0aece5c9f73dc.jpg)  
FIG. 13. Spectrum of the positron energy $\mathcal { E } _ { + } = E _ { + } / E _ { \gamma }$ . No opening angle cut was applied in the left hand figure and an opening angle cut of $1 0 ^ { - 4 }$ was applied in the right hand one. The histograms were created with MC events and the solid curves are results of numerically integrating the differential cross section. The dashed curve in both figures is the result of numerically integrating the differential cross section over the entire range of $\delta \phi$ as opposed over the range $[ 0 . 6 \pi , 1 . 4 \pi ]$ ：

Fig. 13 (right） shows the positron energy distribution after applying the opening angle cut of $\theta _ { \ell \ell } > 1 0 ^ { - 4 }$ on the angle between $e ^ { + }$ and $e ^ { - }$ momenta. The MC agrees with the full numerical integration of the BH rate even though the $\delta \phi$ cut is still applied in the generation of the events . Fig. 13 demonstrates that the asymmetric configurations,where one of the two leptons carries the larger part of the photon energies,are the more probable ones, especially for non-zero opening angles.

Fig. 14 shows the positron polar angle distribution and demonstrates the combined effect of the Si nuclear form factor and the smaler available phase space that suppress very small momentum transfers and thus very small polar angles. The peak is at $\sim m / E \sim 1 0 ^ { - 5 }$ both for the distribution without a cut on the $e ^ { + } e ^ { - }$ opening angle $\theta _ { \ell \ell }$ , Fig. 14 (left), and for the case where $\theta _ { \ell \ell } > 1 0 ^ { - 4 }$ is imposed, Fig. 14 (right). This cut also results in an additional peak in the distribution, cf. Fig. 14 (right).

In Fig. 15,the distribution in the relative azimuthal angle $\delta \phi$ of the two leptons is shown. The majority of the events are close to the coplanar configuration, where the photon and the two lepton momenta allie in the same plane. However, it is noteworthy that approximately （204号 $4 0 \%$ of BH events have acoplanarity of $\sim 5 \%$ or more.

![](images/79393de94c74a1c59bf1fd3bbce7bc1ce630c8fe5c053b3d50ece6139d78911f.jpg)

FIG.14. Polar angle distribution of the leptons. No opening angle cut was applied in the left hand figure and an opening angle cut of $1 0 ^ { - 4 }$ was applied in the right hand one. The histograms were created with MC events and the solid curves are results of numerically integrating the differential rate expression. The small bump in the right hand figure ( $\sim 1 0 ^ { - 4 }$ ） is a result of applying an opening angle cut. Its location is a function of the cut.

![](images/ae4989a17f69fa20cf9222ce5b273c9201c3b8dc2db1034e6e278972d1174ce7.jpg)

FIG.15. Left: Distribution of the azimuthal angle between the leptons. The histograms were created with MC events and the solid curves are results of numerically integrating the diffrential rate expression. Right: The cumulative distribution function of the relative azimuthal orientation, $P ( \delta \phi / \pi \in [ 1 - \Delta , 1 + \Delta ] )$ ， from numerical integration.

# Appendix E: Analysis for $q q \to \gamma \gamma$

Performing the measurement proposed in this work faces two main challenges: first, resolving and reconstructing the electron and positron directions; and second identifying a background-poor sample of events with Higgs decaying to diphotons. Regarding the first challenge,one might simply ask how well and with what efficiency can the LHC or a future collider detector reconstruct the details of photon conversion. To do so, the experimental collaborations may wish to test the polarization structure of a standard model (non-Higgs) amplitude. To demonstrate that there is a non-trivial structure to be measured in SM conversions, we briefly analyze here the leading production of diphotons at the LHC.

The dominant diphoton production (and dominant background for Higgs to photons events） is $q \bar { q } \to \gamma \gamma$ scattering. This has tree-level spin-helicity amplitude

$$
[ \mathcal { M } _ { \mathrm { B G } } ] _ { r s } ^ { \lambda _ { 1 } \lambda _ { 2 } } = \begin{array} { l l l l l } { P _ { + } , s } & { \longrightarrow } & { \displaystyle \bigcap _ { m = \lfloor k _ { 2 } , \lambda _ { 2 } } ^ { m = \lfloor k _ { 1 } , \lambda _ { 1 } \rfloor } } & { \quad } & { \quad } & { \quad } \\ { } & { } & { } & { \quad } & { \quad + \quad \mathrm { ~ u ~ c h a n n e l ~ } , } \\ { P _ { - } , r } & { \longrightarrow } & { } & { \quad } & { \quad k _ { 2 } , \lambda _ { 2 } } \end{array} \quad
$$

in which $r = 1 , 2$ ( $s = 1 , 2$ ）is the spin of the (anti)-fermion,and $\lambda _ { 1 , 2 } = \pm$ are the usual photon helicities. The two photons then convert in the tracker. The background rate can be written in a form similar to Eq. (28). That is, for one fermion species

$$
| \mathcal { M } _ { \mathrm { B G } } | ^ { 2 } = \mathcal { G } _ { 1 } \mathcal { G } _ { 2 } \sum _ { r , s } \sum _ { r _ { 1 } , s _ { 1 } , r _ { 2 } , s _ { 2 } } \bigg | \sum _ { \lambda _ { 1 } , \lambda _ { 2 } } [ \mathcal { M } _ { \mathrm { B G } } ] _ { r s } ^ { \lambda _ { 1 } \lambda _ { 2 } } \alpha _ { 1 _ { r s } } ^ { \lambda _ { 1 } } \alpha _ { 2 _ { r s } } ^ { \lambda _ { 2 } } \bigg | ^ { 2 } .
$$

As is well-known, the only non-zero independent amplitudes are $[ \mathcal { M } _ { \mathrm { B G } } ] _ { 1 2 } ^ { + - }$ and $[ \mathcal { M } _ { \mathrm { B G } } ] _ { 1 2 } ^ { - + }$ One finds with our usual choice of reference momenta, and the light cone decomposition (A8) for the quark momenta $P _ { \pm }$ ，

$$
\begin{array} { r l r } & { } & { [ \mathcal { M } _ { \mathrm { B G } } ] _ { 1 2 } ^ { + - } = \left( [ \mathcal { M } _ { \mathrm { B G } } ] _ { 2 1 } ^ { - + } \right) ^ { * } = \frac { \mathcal { A } _ { + } ( k _ { 2 } , k _ { 1 } ) } { P _ { + } \cdot k _ { 1 } } - \frac { \mathcal { A } _ { - } ^ { * } ( k _ { 1 } , k _ { 2 } ) } { P _ { - } \cdot k _ { 1 } } , } \\ & { } & { [ \mathcal { M } _ { \mathrm { B G } } ] _ { 1 2 } ^ { - + } = \left( [ \mathcal { M } _ { \mathrm { B G } } ] _ { 2 1 } ^ { + - } \right) ^ { * } = \frac { \mathcal { A } _ { + } ( k _ { 1 } , k _ { 2 } ) } { P _ { + } \cdot k _ { 1 } } - \frac { \mathcal { A } _ { - } ^ { * } ( k _ { 2 } , k _ { 1 } ) } { P _ { - } \cdot k _ { 1 } } , } \\ & { } & { \mathcal { A } _ { \pm } ( k , \ell ) = Q _ { f } ^ { 2 } \frac { \langle \tilde { P } _ { \pm } \ell \rangle ^ { 2 } [ \tilde { P } _ { \pm } k ] [ \tilde { P } _ { \mp } k ] } { 2 k _ { 1 } \cdot k _ { 2 } } , } \end{array}
$$

with $Q _ { f }$ the fermion electric charge. The square amplitude simplifies to

$$
| \mathcal { M } _ { \mathrm { B G } } | ^ { 2 } = 2 \mathcal { G } _ { 1 } \mathcal { G } _ { 2 } \sum _ { r _ { 1 } , s _ { 1 } , r _ { 2 } , s _ { 2 } } \left| [ \mathcal { M } _ { \mathrm { B G } } ] _ { 1 2 } ^ { + - } \alpha _ { 1 _ { r s } } ^ { + } \alpha _ { 2 _ { r s } } ^ { - } + [ \mathcal { M } _ { \mathrm { B G } } ] _ { 1 2 } ^ { - + } \alpha _ { 1 _ { r s } } ^ { - } \alpha _ { 2 _ { r s } } ^ { + } \right| ^ { 2 } .
$$

It is interesting to contrast this with the HBH result. Here the helicity interference arises in terms of the form $\alpha _ { 1 _ { 1 2 } } ^ { - } \alpha _ { 2 _ { 1 2 } } ^ { + } \alpha _ { 1 _ { 2 1 } } ^ { - } \alpha _ { 2 _ { 2 1 } } ^ { + }$ ，rather than from $\alpha _ { 1 _ { 1 2 } } ^ { - } \alpha _ { 2 _ { 1 2 } } ^ { - } \alpha _ { 1 _ { 2 1 } } ^ { - } \alpha _ { 2 _ { 2 1 } } ^ { - }$ as we found for HBH. Since $\alpha _ { 1 2 } ^ { + } = ( \alpha _ { 2 1 } ^ { - } ) ^ { * }$ , etc, it follows from the explicit results (36) that this helicity flip on branch ‘ $2 ^ { \mathfrak { g } }$ produces a phase change $\phi _ { 2 \pm }  - \phi _ { 2 \pm }$ in the background interference term, compared to the HBH interference terms.

To compare with the Higgs rest frame HBH rate (48), we assume the quark centre of mass frame aligns with the nuclear rest frame. Integrating all over azimuthal structure except （20 $\psi \equiv \phi _ { 1 _ { + } } - \phi _ { 2 _ { + } }$ (cf. $\varphi = \phi _ { 1 _ { + } } + \phi _ { 2 _ { + } }$ in Eq. (46)),one finds that the background rate has the form

$$
\frac { d \Gamma } { d \psi d \mathrm { P S } _ { \gamma , \theta } } = { \cal A } _ { \gamma , \theta } ^ { \mathrm { B G } } + { \cal B } _ { \gamma , \theta } ^ { \mathrm { B G } } \cos ( 2 \psi ) \ .
$$

We see that this diferential rate has sinusoidal dependence on the mean azimuthal orientation, $\psi$ , of the outgoing positrons, with respect to, say, the incoming quarks - the beamline - rather than the inter-branch lepton azimuthal orientation, $\varphi$ ，as in HBH. Moreover, the phase change $\phi _ { 2 \pm }  - \phi _ { 2 \pm }$ ensures background is fat in $\varphi$ . Note also that unlike the HBH process， the $[ \mathcal { M } _ { \mathrm { B G } } ] ^ { + - }$ factors ensure this background rate features higher spin waves， so that its angular differential structure will differ from the HBH structure, too.

In summary, the leading-order doubly-converted $q q \to \gamma \gamma$ square amplitude is given explicitly by Eqs. (E3) and (E4) combined with the BH spin-helicity amplitudes (B3). In the $q q$ center of mass frame, the corresponding leading order BH amplitudes are given in Eqs. (36).

# Appendix F:Monte Carlo numerical schemes

To generate Monte Carlo (MC) events for the HBH process, we first generate unpolarized BH events and then use the von Neumann rejection technique to re-weight the events according to the HBH differential rate. For a single HBH event one needs two BH events taken from disjoint MC samples. Therefore, we first describe the generation of unpolarized BH events.

The phase space for a single BH event, $\gamma N \to e ^ { + } e ^ { - } N$ ， is five dimensional. We take （204号 $z$ -axis to be the incoming photon direction. For conversion of unpolarized photons, the kinematics are invariant under overall azimuthal rotations around the $z$ axis. We therefore fix the positron azimuthal angle to zero. The remaining four coordinates are chosen to be the electron energy fraction $\mathcal { E } _ { - } = E _ { - } / E _ { \gamma }$ , two transformed polar angles, $t _ { 1 } = \log _ { 1 0 } ( \theta _ { + } )$ and （20 $t _ { 2 } = \log _ { 1 0 } ( \theta _ { - } )$ , and the azimuthal angle of the electron $\phi _ { - }$ (see Fig. 6 for definitions).

For MC we used two independent private codes. One is written in C and the other in C++/Java. To populate the BH phase space we first randomly generate the values for $\mathcal { E } _ { - }$ ， $t _ { 1 , 2 }$ （20 and $\phi _ { - }$ according to either uniform distributions or conveniently chosen initial probability density functions (PDFs) and then unweight to obtain the BH event distribution.

For the C code, the initial PDFs are as follows. For a 60 GeV photon，generating $\mathcal { E } _ { - }$

<html><body><table><tr><td rowspan="2">Parameter</td><td colspan="2">C</td><td colspan="2">C++/Java</td></tr><tr><td>Range</td><td>PDF</td><td>Range</td><td>PDF</td></tr><tr><td>m_</td><td>[m/Eγ,1-m/Eγ]</td><td>Uniform</td><td>[m/Eγ,1-m/Eγ] Uniform</td><td></td></tr><tr><td>t1</td><td>[-7,-2]</td><td>Uniform</td><td>[-6,-3]</td><td>Uniform</td></tr><tr><td>t2</td><td>[-7,-2]</td><td>Uniform</td><td>[-6,-3]</td><td>Uniform</td></tr><tr><td></td><td>[0.6π,1.4π]</td><td>Lorentzian</td><td>[3π /4,5π/4]</td><td>Uniform</td></tr></table></body></html>

TABLE II. The details on the MC generation of BH events, with phase space variables (1st column) for C(C++/Java) generated in the range given in the 2nd (4th) column according to the distribution given in the 3rd (5th) column (for details see text).

according to a uniform distribution results in an efficiency of $\sim 7 0 \%$ . We therefore generate a uniform distribution of $\mathcal { E } _ { - } \in [ m / E _ { \gamma } , 1 - m / E _ { \gamma } ]$ . The transformed polar angle variables, $t _ { 1 }$ （204 and $t _ { 2 }$ , are generated according to uniform distributions in a suitable numerical range, see Table II. Using the coordinates $t _ { 1 , 2 }$ captures the fact that electron and positron distributions are sharply peaked around $\theta _ { \pm } \sim m / E$ . The BH events are also dominated by kinematic configurations that are not too far from the coplanar one. We therefore generate $\phi _ { - }$ in the range $[ 0 . 6 \pi , 1 . 4 \pi ]$ ，which suffices for our precision. To capture the fact that the BH distribution is peaked toward $\phi _ { - } / \pi = 1$ ，the $\mathrm { C }$ code generates $\phi _ { - }$ according to a Cauchy distribution (Lorentzian) with location parameter $x _ { o } = \pi$ and scale parameter $\lambda = 0 . 0 3 \pi$ [61] to improve the effciency. The C++/Java uses similar initial data, with the exception of slightly different ranges and that $\phi _ { - }$ is populated by a uniform distribution on a slightly narrowed domain $\phi _ { - } \in [ 3 \pi / 4 , 5 \pi / 4 ]$ (see Table. II).

In the next step we unweight the events generated from initial PDFs to obtain the proper BH distribution. In the unweighting,the events are rejected with a probability that is （204号 $1 - w$ ，with $w = ( d \Gamma _ { \mathrm { B H } } / d \mathrm { P S } ) / \operatorname* { m a x } ( d \Gamma _ { \mathrm { B H } } / d \mathrm { P S } )$ . The BH MC event sample was validated by comparing the generated event distributions to the results of numerical integration of BH differential cross-sections as shown in Figs. 13,14 and 15. Additionally, in Figs. 13 and 14, the distributions with a cut on the opening angle between $e ^ { + }$ and $e ^ { - }$ of $\theta _ { \ell \ell } > 1 0 ^ { - 4 }$ are shown. The MC sample is in excellent agreement with the results of numerical integration.

In the final step, we convert the generated BH events into MC event samples for the HBH process. To do so, two disjoint BH samples were used - one sample per photon branch. The rate for two BH events is given by $( d \Gamma _ { \mathrm { B H 1 } } / d \mathrm { P S } ) ( d \Gamma _ { \mathrm { B H 2 } } / d \mathrm { P S } )$ . To obtain the proper HBH even rates, we use the standard reweighting technique where events are rejected according to the weight

$$
w = \frac { ( d \Gamma _ { \mathrm { H B H } } / d \mathrm { P S } ) [ \varphi ] } { ( d \Gamma _ { \mathrm { B H _ { 1 } } } / d \mathrm { P S } ) ( d \Gamma _ { \mathrm { B H _ { 2 } } } / d \mathrm { P S } ) } \ ,
$$

where the twist angle between the positrons, $\varphi$ , is populated by a uniform distribution on （204号 $[ 0 , 2 \pi ]$ ：

The two MC codes have been cross tested. In numerics we use $3 \times 1 0 ^ { 6 }$ HBH events from the C generator and $8 \times 1 0 ^ { 5 }$ HBH events from the C++/Java MC generator.

[1] CMS Collaboration Collaboration, S. Chatrchyan et al.， Obseruation of a new boson at a mass of 125 GeV with the CMS experiment at the LHC, Phys.Let B716 (2012) 30-61, [arXiv:1207.7235].   
[2] ATLAS Collaboration Collaboration, G. Aad et al.， Observation of a new particle in the search for the Standard Model Higgs boson with the ATLAS detector at the LHC, Phys.Lett. B716 (2012) 1-29, [arXiv:1207.7214].   
[3] M. Voloshin, CP Violation in Higgs Diphoton Decay in Models with Vectorlike Heavy Fermions, Phys. Rev. D 86 (2012) 093016, [arXiv:1208.4303].   
[4] Y. Chen and R. Vega-Morales, Extracting Effective Higgs Couplings in the Golden Channel, arXiv:1310.2893.   
[5] I. Anderson, S. Bolognesi, F.Caola, Y. Gao, A. V. Gritsan, et al.， Constraining anomalous HVV interactions at proton and lepton colliders, arXiv:1309.4819.   
[6] Y. Sun, X.-F. Wang, and D.-N. Gao, CP mixed property of the Higgs-like particle in the decay channel $h  Z Z ^ { * }  4 l$ , arXiv:1309.4171.   
[7] R. Boughezal, T. J. LeCompte, and F. Petriello, Single-variable asymmetries for measuring the Higgs’ boson spin and CP properties, arXiv:1208.4311.   
[8] S. Bolognesi, Y. Gao, A. V. Gritsan, K. Melnikov, M. Schulze, et al., On the spin and parity of a single-produced resonance at the LHC, Phys.Rev. D86 (2012) 095031, [arXiv:1208.4018].   
[9] R. Harnik, A. Martin, T. Okui, R. Primulando,and F. Yu, Measuring CP Violation in $h  \tau ^ { + } \tau ^ { - }$ at Colliders, Phys.Rev.D88 (2013) 076009, [arXiv:1308.1094].   
[10] S.Berge, W. Bernreuther, and H. Spiesberger, Higgs CP properties using the tau decay modes at the ILC, arXiv:1308.2674.   
[11] J. R. Dell'Aquila and C. A. Nelson, Usage of the TT or T Anti-t Decay Mode to Distinguish an Intermediate Mass Higgs Boson From a Technipion, Nucl.Phys. B320 (1989) 86-102.   
[12] J. R. Dell'Aquila and C. A. Nelson, CP Determination for New Spin Zero Mesons by the TT Decay Mode, Nucl.Phys. B320 (1989) 61.   
[13] B. Grzadkowski and J. Gunion, Using decay angle correlations to detect CP violation in the neutral Higgs sector, Phys.Lett B350 (1995) 218-224, [hep-ph/9501339].   
[14] G. Bower, T. Pierzchala, Z. Was, and M. Worek, Measuring the Higgs boson's parity using tau —ε rho nu, Phys.Lett. B543 (2002) 227-234, [hep-ph/0204292].   
[15] M. Worek, Higgs CP from $H / A O - \dot { \delta }$ tau tau decay, Acta Phys.Polon. B34 (2003) 4549-4560,[hep-ph/0305082].   
[16] K. Desch, Z. Was, and M. Worek, Measuring the Higgs boson parity at a linear collider using the tau impact parameter and tau -ε rho nu decay, Eur.Phys.J. C29 (2003) 491-496, [hep-ph/0302046].   
[17] S. Berge and W. Bernreuther, Determining the CP parity of Higgs bosons at the LHC in the tau to 1-prong decay channels, Phys.Lett. B671 (2009) 470-476, [arXiv:0812.1910].   
[18] S.Berge, W. Bernreuther,and J. Ziethe, Determining the CP parity of Higgs bosons at the LHC in their tau decay channels, Phys.Rev.Lett. 100 (2008) 171605,[arXiv:0801.2297].   
[19] S. Berge, W. Bernreuther, B. Niepelt, and H. Spiesberger, How to pin down the CP quantum numbers of a Higgs boson in its tau decays at the LHC, Phys.Rev. D84 (2011) 116003, [arXiv:1108.0670].   
[20] J. Brod, U. Haisch, and J. Zupan, Constraints on CP-violating Higgs couplings to the third generation, JHEP 1311, 180 (2013) [arXiv:1310.1385].   
[21] C. N. Yang, Selection rules for the dematerialization of a particle into two photons, Phys. Rev. 77 (Jan, 1950) 242-245.   
[22] C. N. Yang, Possible experimental determination of whether the neutral meson is scalar or pseudoscalar, Phys. Rev. 77 (Mar, 1950) 722-723.   
[23] N. M. Kroll and W. Wada, Internal pair production associated with the emission of high-energy gamma rays, Phys. Rev. 98 (Jun, 1955) 1355-1359.   
[24] Y. Grossman and D. Pirjol, Extracting and using photon polarization information in radiative B decays, JHEP 0006 (2000) 029, [hep-ph/0005069].   
[25] ATLAS Collaboration Collaboration, G. Aad et al., Search for the Standard Model Higgs boson in the diphoton decay channel with 4.9 $f b ^ { - 1 }$ of pp collisions at $\sqrt { s } = 7$ TeV with ATLAS, Phys.Rev.Lett. 108 (2012) 111803, [arXiv:1202.1414].   
[26] CMS Collaboration Collaboration, S. Chatrchyan et al.， Search for the standard model Higgs boson decaying into two photons in pp colisions at √s = 7 TeV, Phys.Lett. B710 (2012) 403-425,[arXiv:1202.1487].   
[27] W. N. Cottingham and I. B. Whittingham, Signals of higgs sector CP violation in neutral higgs boson decays, Phys.Rev. D 52 (Jul, 1995) 539-542.   
[28] ATLAS Collboration, Measurements of the properties of the higgs-like boson in the four lepton decay channel with the atlas detector, Tech. Rep. ATLAS-CONF-2013-013, CERN, 2013.   
[29] CMS Collaboration Collaboration, S. Chatrchyan et al., Study of the mass and spin-parity of the higgs boson candidate via its decays to z boson pairs, Phys.Rev.Lett 110 (2013) 081803,[arXiv:1212.6639].   
[30] G. Belanger, B. Dumont, U. Ellwanger, J. Gunion, and S. Kraml, Global ft to Higgs signal strengths and couplings and implications for extended Higgs sectors, arXiv:1306.2941.   
[31] A. Czarnecki and B. Krause, On the dipole moments of fermions at two loops, Acta Phys.Polon. B28 (1997) 829-834, [hep-ph/9611299].   
[32] D. McKeen, M. Pospelov,and A. Ritz, Modified Higgs branching ratios versus CP and lepton flavor violation, Phys.Rev. D86 (2012) 113004, [arXiv:1208.4597].   
[33] ACME Collaboration， Order of Magnitude Smaller Limit on the Electric Dipole Moment of the Electron, arXiv:1310.7534.   
[34] J. Fan and M. Reece, Probing Charged Matter Through Higgs Diphoton Decay， Gamma Ray Lines,and EDMs, JHEP 1306 (2013) 004, [arXiv:1301.2597].   
[35] J. Shu and Y. Zhang, Impact of a CP Violating Higgs: from LHC to Baryogenesis, Phys.Rev.Lett.111 (2013) 091801, [arXiv:1304.0773].   
[36] A. Y. Korchin and V. A. Kovalchuk, Polarization effects in the Higgs boson decay to gamma Z and test of CP and CPT symmetries, Phys.Rev. D88 (2013) 036009,[arXiv:1303.0365].   
[37] A. Y. Korchin and V. Kovalchuk, Higgs Boson Decay to γZ and Test of CP and CPT Symmetries, Acta Phys.Polon.B44 (2013), no.11 2121-2128.   
[38] W.-Y. Keung, I. Low, and J. Shu, Landau-Yang Theorem and Decays of a Z' Boson into Two Z Bos0ns, Phys.Rev.Lett. 101 (2008) 091802, [arXiv:0806.2864].   
[39] Q.-H. Cao, C. Jackson, W.-Y. Keung, I. Low, and J. Shu, The Higgs Mechanism and Loop-induced Decays of a Scalar into Two Z Bosons, Phys.Rev. D81 (2010) 015010, [arXiv:0911.3398].   
[40] M. Berger, J. Hubbell S. Seltzer, J. Chang, J. Coursey, R. Sukumar, D. Zucker, and K. Olsen， “XCOM: Photon cross section database version 1.5.” National Institute of Standards and Technology, 2010.   
[41] Y.-S. Tsai, Pair production and bremstrahlung of charged leptons, Rev. Mod. Phys. 46 (Oct, 1974) 815-851.   
[42] Y.-S. Tsai, Erratum: Pair production and bremsstrahlung of charged leptons, Rev. Mod. Phys. 49（Apr,1977) 421-423.   
[43] CMS Collaboration, Updated measurements of the Higgs boson at 125 GeV in the two photon decay channel, Tech. Rep. CMS-PAS-HIG-13-001, CERN, Geneva, 2013.   
[44] ATLAS Collaboration, Measurements of the properties of the Higgs-like boson in the two photon decay channel with the ATLAS detector using 25 fb $^ - 1$ of proton-proton collision data, Tech. Rep. ATLAS-CONF-2013-012, CERN, Geneva, Mar, 2013.   
[45] S. Drell and J. Walecka, Electrodynamic processes with nuclear targets, Annals of Physics 28 (1964), no. 1 18 - 33.   
[46] Particle Data Group Collaboration, J. Beringer et al.， The review of particle physics, Phys. Rev. D 86 (2012) 010001.   
[47] ATLAS Collaboration Collaboration, G. Aad et al.， The atlas collaboration, JINST 3 (2008)，no.08 S08003.   
[48] J.C. Slater, Atomic radii in crystals, The Journal of Chemical Physics 41 (1964), no. 10 3199-3204.   
[49] L. Schiff, Energy-angle distribution of thin target bremstrahlung, Physical Review 83 (1951), no. 2 252.   
[50] D0 Collaboration Collaboration, V. Abazov et al., A precision measurement of the mass of the top quark, Nature 429 (2004) 638-642, [hep-ex/0406031].   
[51] D0 Collaboration Collaboration, V. Abazov et al.， Helicity of the w boson in lepton $^ +$ jets euents, Physics Letters B 617 (2005), no. 1-2 1- 10.   
[52] P. Artoisenet, V. Lemaitre, F. Maltoni, and O. Mattelaer,Automation of the matrix element reweighting method, JHEP 1012 (2010) 068, [arXiv:1007 .3300].   
[53] R. H. Dalitz and G. R. Goldstein, Decay and polarization properties of the top quark, Phys. Rev. D 45(Mar,1992) 1531-1543.   
[54] F.Fiedler,A. Grohsjean,P. Haefner,and P. Schieferdecker,The Matrix Element Method and its Application in Measurements of the Top Quark Mass, Nucl.Instrum.Meth. A624 (2010) 203-218, [arXiv:1003.1316].   
[55] K. Kondo, Dynamical likelihood method for reconstruction of events with missing momentum. ii. mass spectra for $2  2$ processes, Journal of the Physical Society of Japan 60 (1991), no. 3 836-844.   
[56] R. Tanaka, C. Mariotti, S. Heinemeyer, and G. Passarino,“Lhc higgs cross section working group: Recommended values on sm higgs xs at 7/8/14/33/..100 tev for hl-lhc and he-lhc."   
[57] S. Dawson, A. Gritsan, H. Logan, J. Qian, C. Tully, et al., Higgs Working Group Report of the Snowmass 2013 Community Planning Study, arXiv:1310.8361.   
[58] L. J. Dixon, Calculating scattering amplitudes efficiently, hep-ph/9601359.   
[59] L. J. Dixon, E. N. Glover, and V. V. Khoze, MHV rules for Higgs plus multi-gluon amplitudes, JHEP 0412 (2004) 015, [hep-th/0411092].   
[60] T. Hahn, CUBA: A Library for multidimensional numerical integration, Comput.Phys.Commun. 168 (2005) 78-95, [hep-ph/0404043].   
[61] N.L. Johnson, S. Kotz, and N. Balakrishnan, Continuous Univariate Distributions， Vol. 1. Wiley-Interscience, second ed., 1994.