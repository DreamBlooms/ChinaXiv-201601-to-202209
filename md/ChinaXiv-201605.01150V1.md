# Full one-loop electroweak corrections to $e ^ { + } e ^ { - } \to Z H \gamma$ at a Higgs factory

Ning Liu $^ { 1 , 2 }$ ， Jie Ren $^ { 1 , 3 }$ ， Lei Wu $^ 2$ ， Peiwen Wu $^ 3$ ， Jin Min Yang³

（20 $^ { 1 }$ College of Physics & Electronic Engineering, Henan Normal University， Xinxiang 453007, China （20 $^ 2$ ARC Centre of Excellence for Particle Physics at the Terascale, School of Physics， The University of Sydney， NSW 20o6, Australia （ $^ 3$ State Key Laboratory of Theoretical Physics, Institute of Theoretical Physics， Academia Sinica, Beijing 100190, China

# Abstract

Motivated by the future precision test of the Higgs boson at an $e ^ { + } e ^ { - }$ Higgs factory, we calculate the production $e ^ { + } e ^ { - }  Z H \gamma$ in the Standard Model with complete next-to-leading order electroweak corrections. We find that for $\sqrt { s } = 2 4 0$ (350)GeV the cross section of this production is sizably reduced by the electroweak corrections,which is 1.03 (5.32) fb at leading order and 0.72 (4.79） fb at next-to-leading order. The transverse momentum distribution of the photon in the final states is also presented.

PACS numbers:

# I. INTRODUCTION

Recently， a Standard Model (SM)-like Higgs boson around 125 GeV was observed by ATLAS and CMS collaborations at the LHC [1, 2]. This discovery is a great step towards the understanding of electroweak symmetry breaking of the SM. So far, most measurements of the properties of this new boson are consistent with the SM prediction. The new physics that affects the Higgs couplings has been cornered to a decoupling region [3, 4]. Besides, since many extensions of the SM (like the supersymmetric models) contain a SM-like Higgs boson [5] whose properties can be quite similar to the SM Higgs boson, it is difficult for the LHC to verify whether or not this new boson is the SM one. In order to precisely study this newly discovered Higgs boson，an $e ^ { + } e ^ { - }$ collider, the so-called Higgs factory, is needed.

In such an $e ^ { + } e ^ { - }$ Higgs factory, the properties of Higgs boson can be measured with rather high precisions [6-8]. The dominant Higgs production is the Higgs-strahlung process $e ^ { + } e ^ { - } \to$ $Z H$ ,where the $Z H$ events can be inclusively detected by tagging a leptonic $Z$ decay without the assumption of the Higgs decay mode. The individual Higgs decay branching ratios can then be directly measured as the fractions of the total $e ^ { + } e ^ { - }  Z H$ cross section by observing the specific states. For $\sqrt { s } \sim 2 4 0 - 2 5 0$ GeV with an integrated luminosity of $\mathrm { 5 0 0 ~ f b ^ { - 1 } }$ , about （204号 $O ( 1 0 ^ { 5 } )$ Higgs bosons can be produced per year, which allows to measure the Higgs couplings at a few percent [8]. So the electroweak radiative corrections should be taken into account in the theoretical calculations of the production rate. For the process $e ^ { + } e ^ { - }  Z H$ ，the leading order calculation was performed in [9] and the one-loop electroweak corrections were calculated with the soft-photon approximation in [10-12] (a compact analytical formula for the electromagnetic corrections was given in [11] and a numerical calculation algorithm for the real photon emission was proposed in [13]).

For an $e ^ { + } e ^ { - }$ Higgs factory with $\sqrt { s } \sim 2 4 0 - 2 5 0$ GeV another possibly important process is （204号 $e ^ { + } e ^ { - } \to H Z \gamma$ . On one hand, it is an important part of the inclusive process $e ^ { + } e ^ { - } \to Z H + X$ or can be distinguished for a hard photon; On the other hand, since the $H Z \gamma$ vertex occurs at one loop in the SM, the $H Z \gamma$ couplings is particularly sensitive to possible new physics contributions, such as the existence of new heavy particles propagating in the loop [14,15]. In this work we calculate this production in the SM with the complete next-to-leading order electroweak (NLO EW) corrections. In Sec. II we will give a description for the analytic calculations. The numerical results and discussions are given in Sec. III. Finally, we draw

![](images/019ae27eea9fd9496ca4c283b8320b2ccee7279cde4039ac46def005e101a241.jpg)  
FIG. 1: The pentagon diagrams for the process $e ^ { + } e ^ { - }  H Z \gamma$

our conclusions in Sec. IV.

# I. A DESCRIPTION OF ANALYTICAL CALCULATIONS

In the SM the process $e ^ { + } e ^ { - } \to H Z \gamma$ is induced by the electroweak interaction at leading order (LO). Due to the small Yukawa couplings, we ignore the contributions from the Feynman diagrams involving the Yukawa couplings of light fermions. We denote the fourmomenta of initial and final states in the process as

$$
e ^ { + } ( q _ { 1 } ) + e ^ { - } ( q _ { 2 } )  H ( q _ { 3 } ) + Z ( q _ { 4 } ) + \gamma ( q _ { 5 } )
$$

The NLO EW corrections $( \Delta \sigma _ { E W } )$ include two parts:

· Virtual correction $( \Delta \sigma _ { v i r } )$ We adopt the dimensional regularization to isolate the ultraviolet divergences (UV) in the one-loop amplitudes. Then we remove the UV singularities by using the on-massshell renormalization scheme [16]. The pentagon Feynman diagrams in the calculation are presented in Fig.1. The reductions of N-point ( $N \leq 4$ ） tensor integrals are implemented by using the Passarino-Veltman algorithm [17]. But for the calculation of the 5-point tensor functions, we adopt the Denner-Dittmaier method developed in Ref.[18] to reduce the tensor integrals and use our fortran subroutines to perform numerical study, which has been validated in our previous works [19, 20]. We also numerically checked that our results are UV finite.

Real photon radiation $\left( \Delta \sigma _ { r e a l } \right)$

Due to the exchange of virtual photon in the loops, the infrared (IR) divergences can appear in the virtual correction. According to the Kinoshita-Lee-Nauenberg (KLN) theorem [21], these IR divergences wil be canceled by the real photon bremsstrahlung corrections in the soft photon limit. We denote the momenta of initial and final states for the real photon radiation process as

$$
e ^ { + } ( q _ { 1 } ) + e ^ { - } ( q _ { 2 } )  H ( q _ { 3 } ) + Z ( q _ { 4 } ) + \gamma ( q _ { 5 } ) + \gamma ( q _ { 6 } ) .
$$

We take the phase-space-slicing method [22, 23] to isolate the IR singularity in the above process. An arbitrarily small cut-off parameter $\delta _ { s }$ is introduced to split the phase space into soft region ( ${ \cal E } _ { 6 } \le \delta _ { s } \sqrt { s } / 2 )$ and hard region ( ${ \cal E } _ { 6 } > \delta _ { s } \sqrt { s } / 2 { , }$ . So the real photon emission correction can be decomposed into the soft and hard parts:

$$
\Delta \sigma _ { r e a l } = \Delta \sigma _ { s o f t } + \Delta \sigma _ { h a r d } .
$$

In the soft photon approximation [24],we can calculate the soft part of the correction by using the following equation

$$
d \Delta \sigma _ { s o f t } = d \sigma _ { 0 } \frac { \alpha } { 2 \pi ^ { 2 } } \int _ { E _ { 6 } \le \delta _ { s } \sqrt { s } / 2 } \frac { d ^ { 3 } \vec { q _ { 6 } } } { 2 E _ { 6 } } \left( \frac { q _ { 1 } } { q _ { 1 } \cdot q _ { 6 } } - \frac { q _ { 2 } } { q _ { 2 } \cdot q _ { 6 } } \right) ^ { 2 } .
$$

where ${ \cal E } _ { 6 } = \sqrt { | \vec { q _ { 6 } } | ^ { 2 } + m _ { \gamma } ^ { 2 } }$ and we give a small mass $m _ { \gamma }$ to the photon to eliminate the IR divergence (we checked that the dependence on this non-physical mass $m _ { \gamma }$ is exactly canceled when the real radiation correction and the virtual correction are combined). Since the hard part of the correction is insensitive to this fictitious photon mass, it can be directly evaluated by the numerical Monte Carlo method [25]. We notice that there are two photons in the real emission process and one of them should be tagged as the observed hard photon with $p _ { T } > 1 0$ GeV and $| \eta | < 2$ . The phase space integral of these two identical photons in hard part of real emission can be expressed as:

$$
\begin{array} { r } { I _ { 5 6 } \sim \displaystyle \frac { 1 } { 2 } \left[ \int _ { E _ { c } } ^ { \infty } \frac { d ^ { 3 } \vec { q } _ { 5 } ^ { > } } { 2 E _ { 5 } } \int _ { \delta _ { s } \sqrt { s } / 2 } ^ { E _ { 5 } } \frac { d ^ { 3 } \vec { q } _ { 6 } ^ { < } } { 2 E _ { 6 } } | \mathcal { M } | ^ { 2 } \theta ( E _ { 5 } - E _ { 6 } ) \right. } \\ { \displaystyle \left. + \int _ { E _ { c } } ^ { \infty } \frac { d ^ { 3 } \vec { q } _ { 6 } ^ { < } } { 2 E _ { 6 } } \int _ { \delta _ { s } \sqrt { s } / 2 } ^ { E _ { 6 } } \frac { d ^ { 3 } \vec { q } _ { 5 } ^ { > } } { 2 E _ { 5 } } | \mathcal { M } | ^ { 2 } \theta ( E _ { 6 } - E _ { 5 } ) \right] , } \end{array}
$$

where the factor $\textstyle { \frac { 1 } { 2 } }$ is from the identical photons in the final states, and $E _ { c }$ is the energy cut that corresponds to the above hard $p _ { T }$ cut. In order to improve the numerical stability of Eq.(5)，we adopt the method in the Ref.[26] to carry out the integral Eq.(5). Since each of the two photons in the final states can be softer or harder than the other one with an equal probability, the Eq.(5) can be equivalent to:

$$
I _ { 5 6 } \sim \frac { 1 } { 2 } \times 2 \times \int _ { E _ { c } } ^ { \infty } \frac { d ^ { 3 } \vec { q _ { 5 } } } { 2 E _ { 5 } } \int _ { \delta _ { s } \sqrt { s } / 2 } ^ { E _ { 5 } } \frac { d ^ { 3 } \vec { q _ { 6 } } } { 2 E _ { 6 } } | \mathcal { M } | ^ { 2 } .
$$

This means that we can technically assume the photon $\gamma ( q _ { 5 } )$ to be the tagged hard photon and impose a transverse momentum cut $p _ { T } > 1 0$ GeV and pseudo-rapidity cut $| \eta | < 2$ on $\gamma ( q _ { 5 } )$ in the numerical calculations [26, 27].

Finally, the total NLO EW correction of the process $e ^ { + } e ^ { - } \to H Z \gamma$ is obtained by

$$
\Delta \sigma _ { t o t } = \Delta \sigma _ { v i r } + \Delta \sigma _ { s o f t } + \Delta \sigma _ { h a r d } .
$$

We do the calculations by using the packages FeynArts-3.8 [28]， FormCalc-8.2 [29] and LoopTools-2.8 [30] (we have the experience for using such packages [19, 20, 31, 32]). We analytically checked the gauge independence of our LO result by using the Ward identities. We also numerically checked our LO calculations in Feynman gauge(F.G.) with the package CompHEP 4.5.2 in unitary gauge(U.G.) [33]. In Tab.I, we present the comparison results and find that they are wel consistent and are gauge-independent. In addition, by simultaneously interchanging the momenta and the polarization vectors of the two photons, we exploit Bose symmetry of the amplitudes of the real emission processes and found the values of the corresponding amplitudes do not change within numerical precision. We also numerically checked our result for the real radiation correction by using the Comphep program and found good agreement.

<html><body><table><tr><td>√s</td><td>E8 (our)</td><td>σUG. (CompHEP)</td></tr><tr><td>250</td><td>2.172(2)</td><td>2.172(4)</td></tr><tr><td>350</td><td>5.316(5)</td><td>5.316(9)</td></tr><tr><td>500</td><td>3.562(3)</td><td>3.561(6)</td></tr><tr><td>600</td><td>2.705(3)</td><td>2.705(4)</td></tr><tr><td>800</td><td>1.708(2)</td><td>1.708(3)</td></tr><tr><td>1000</td><td>1.184(1)</td><td>1.184(2)</td></tr></table></body></html>

TABLE I: The comparison of our LO cross section of $e ^ { + } e ^ { - } \to H Z \gamma$ in Feynman gauge with those calculated by CompHEP 4.5.2 in unitary gauge.

![](images/c9382a8d721ae2972bb97e2f923da29de8e113ce4ebe86071c99ae3b9e177e75.jpg)  
FIG.2: The one-loop electroweak correction to the cross section of $e ^ { + } e ^ { - } \  \ H Z \gamma$ versus the soft cutoff $\log \delta _ { s }$ for $M _ { H } = 1 2 5 . 6 6$ GeV and $\sqrt { s } = 5 0 0$ GeV: (a） showing respectively $\Delta \sigma _ { h a r d }$ ， （204号 $\Delta \sigma _ { v i r } + \Delta \sigma _ { s o f t }$ and $\Delta \sigma _ { t o t }$ ; (b) showing $\Delta \sigma _ { t o t }$ with the calculation errors.

# III. NUMERICAL RESULTS AND DISCUSSIONS

In the numerical calculations we take the input parameters of the SM as [34]

$$
\begin{array} { r } { m _ { t } = 1 7 1 . 2 ~ \mathrm { G e V } , ~ m _ { e } = 0 . 5 1 9 9 9 1 ~ \mathrm { M e V } , ~ m _ { Z } = 9 1 . 1 9 ~ \mathrm { G e V } , } \\ { \sin ^ { 2 } \theta _ { W } = 0 . 2 2 2 8 , ~ \alpha ( m _ { Z } ^ { 2 } ) ^ { - 1 } = 1 2 7 . 9 1 8 . \qquad } \end{array}
$$

The Higgs mass is taken as $m _ { H } = 1 2 5 . 6 6 \pm 0 . 3 4$ GeV [4],which is the combined result of the measurements of the ATLAS and CMS collaborations.

We numerically check the stability of the results versus the soft photon cutoff parameter in

![](images/b8a6a0c09fef2bcda52abcac34359b9f9cdaf3916ed818b6e70f83976ef5416a.jpg)  
FIG.3: The cross section of $e ^ { + } e ^ { - } \to H Z \gamma$ versus $\sqrt { s }$ ， showing respectively the LO result and the NLO EW corrections. The uncertainty caused by the $2 \sigma$ range of the Higgs mass (124.98 GeV $< m _ { H } < 1 2 6 . 4 4 \mathrm { \ G e V } ;$ ）is also shown (the shaded bands).

Fig.2, where we assume $\sqrt { s } = 5 0 0$ GeV and $m _ { \gamma } = 1 0 ^ { - 8 }$ GeV. From the left panel of Fig.2 it can be seen that the values of $\Delta \sigma _ { v i r }$ ， $\Delta \sigma _ { h a r d }$ and $\Delta \sigma _ { s o f t }$ depend on the soft cutoff $\log \delta _ { s }$ ,while the total NLO EW correction $\Delta \sigma _ { t o t }$ is independent of $\log \delta _ { s }$ within reasonable calculation errors. Besides，we checked that the total correction is independent of $m _ { \gamma }$ for a fixed $\delta _ { s }$ Therefore, in the following calculations we take the $\delta _ { s } = 2 \times 1 0 ^ { - 3 }$ and $m _ { \gamma } = 1 0 ^ { - 8 }$ GeV.

In Fig.3 we plot the cross section of $e ^ { + } e ^ { - } \to H Z \gamma$ versus the center-of-mass energy $\sqrt { s }$ ， showing respectively the LO result and the NLO EW corrections. We can see that the production rate can reach a few fb in the threshold region $\sqrt { s } \sim 3 0 0 - 3 5 0$ GeV (maximally it can reach 5.5 fb at LO and 4.8 fb at NLO),and the corresponding EW correction can reach $- 1 2 \%$ .For $\sqrt { s } > 4 0 0$ GeV, the cross section decreases rapidly due to the suppression of $1 / s$ At a 240 GeV Higgs factory, like the proposed LEP3 or China Higgs Factory (CHF), the cross section of $e ^ { + } e ^ { - } \to H Z \gamma$ can reach 1.03 fb at LO and 0.72 fb at NLO (the corresponding EW correction is $- 3 0 \%$ ), while at a 350 GeV Higgs factory, such as the ILC and TLEP, the cross section of $e ^ { + } e ^ { - } \to H Z \gamma$ will reach 5.32 fb at LO and 4.79 fb at NLO (the corresponding EW correction is $- 9 . 8 \%$ ). We can also find that the uncertainty of the cross section caused by the Higgs mass becomes small with the increase of $\sqrt { s }$

![](images/897df66f039e5acb292ff90390c5f8dadf4da3b1c80c045640a0a0bdcf9b1c85.jpg)  
FIG.4: The transverse momentum distribution of the photon at LO and NLO for the process （204号 $e ^ { + } e ^ { - } \to H Z \gamma$ with $\sqrt { s } = 2 4 0 , 3 5 0$ GeV. The shaded bands correspond to the uncertainty caused by the $2 \sigma$ range of the Higgs mass $( 1 2 4 . 9 8 ~ \mathrm { G e V } < m _ { H } < 1 2 6 . 4 4 ~ \mathrm { G e V } )$ ：

Finally in Fig.4 we show the transverse momentum distribution of the photon in the process $e ^ { + } e ^ { - } \to H Z \gamma$ at LO and NLO for $\sqrt { s } = 2 4 0 , 3 5 0 \ \mathrm { G e V }$ . It can be seen that the NLO EW correction can greatly reduce the LO differential cross section at low $p _ { T }$ region. The impact of the uncertainty of the Higgs mass on the $p _ { T }$ distribution becomes weak as the collider energy increases. For $\sqrt { s } = 2 4 0$ GeV most of the events are produced in the region of $p _ { T } ^ { \gamma } < 2 0$ GeV due to the center-of-mass energy close to the production threshold; while for $\sqrt { s } = 3 5 0$ GeV the $p _ { T }$ value of the photon gets much harder.

# IV. CONCLUSION

In this work we calculated the cross section of $e ^ { + } e ^ { - }  Z H \gamma$ with complete next-toleading order electroweak corrections in the SM. We found that for $\sqrt { s } = 2 4 0$ (350) GeV the cross section of this production can reach 1.03 (5.32) fb at leading order and 0.72 (4.79) fb at next-to-leading order. In a future $e ^ { + } e ^ { - }$ Higgs factory, this process can be measured as a precision test of the SM.

# Acknowledgement

We appreciate the helpful discussion with Chengcheng Han. Ning Liu would like to thank Dr Archil Kobakhidze for his warm hospitality in Sydney node of CoEPP in Australia. This work is supported by the National Natural Science Foundation of China (NNSFC) under grant Nos.11305049,11275057, 11275245,10821504 and 1135003, by Specialized Research Fund for the Doctoral Program of Higher Education under Grant No.20134104120002, and by the Startup Foundation for Doctors of Henan Normal University under contract No.11112.

[1] G. Aad et al. [ATLAS Collaboration], Phys. Lett. B 716,1 (2012).   
[2] S. Chatrchyan et al. [CMS Collaboration], Phys. Lett. B 716, 30 (2012).   
[3] G. Belanger et al. Phys. Rev. D 88, 075008 (2013).   
[4] P. P. Giardino et al.,arXiv:1303.3570 [hep-ph].   
[5] See,e.g.，M. Carena et al. JHEP 1203, 014 (2012); JHEP 1207,175 (2012); J. Cao et al., JHEP 1210,079 (2012); JHEP 1203,086 (2012); Phys. Lett.B 710,665 (2012); U. Ellwanger, JHEP 1203, 044 (2012); G. Belanger et al., arXiv:1210.1976; arXiv:1208.4952; J. F. Gunion, Y. Jiang, S. Kraml, Phys.Rev. D86,071702 (2012); Phys. Rev. Lett. 110, 051801 (2013). J. Cao, C. Han,L. Wu,J. M. Yang and Y. Zhang, JHEP 1211, 039 (2012) [arXiv:1206.3865 [hepphl; C. Han, A. Kobakhidze, N. Liu, A. Saavedra, L. Wu and J. M. Yang, arXiv:1310.4274 [hep-ph]; C. Han, K. -i. Hikasa,L. Wu, J. M. Yang and Y. Zhang, JHEP 1310, 216 (2013) [arXiv:1308.5307 [hep-ph].   
[6] A. Blondel et al., arXiv:1302.3318 [physics.acc-ph].   
[7] S. Dawson et al., arXiv:1310.8361 [hep-ex].   
[8] M.E. Peskin, arXiv:1207.2516 [hep-ph].   
[9] J.R. Ellis, M. K. Gaillard and D. V. Nanopoulos, Nucl. Phys. B 106 (1976) 292;   
[10] J. Fleischer and F. Jegerlehner, Nucl. Phys. B 216, 469 (1983);   
[11] B. A. Kniehl, Z. Phys. C 55, 605 (1992).   
[12] A. Denner, J. Küblbeck,R. Mertig and M. Böhm, Z. Phys. C 56(1992) 261.   
[13] F. A. Berends and R. Kleiss, Nucl. Phys. B 260 (1985) 32.   
[14] J. Cao,L. Wu,P.Wu and J. M. Yang, JHEP 1309, 043 (2013) [arXiv:1301.4641 [hep-ph].   
[15] C. Han, N. Liu, L. Wu, J. M. Yang and Y. Zhang,arXiv:1212.6728.   
[16] M.Bohm,H. Spiesberger and W. Hollik, Fortsch. Phys.34 (1986) 687;W. Holik, Fortsch. Phys. 38(1990) 165; B. Grzadkowski and W. Hollik, Nucl. Phys.B 384 (1992）101.   
[17] G.t Hooft and M. Veltman, Nucl. Phys.B153,365 (1979); A. Denner,Fortschr. Phys.41,307 (1993).   
[18] A. Denner and S. Dittmaier, Nucl. Phys.B 658,175 (2003) [hep-ph/0212259].   
[19] N. Liu, L. Wu,P. Wu and J. M. Yang, JHEP 1301,161 (2013) [arXiv:1208.3413 [hep-ph].   
[20] N. Liu et al., Phys. Rev. D 82, 015009 (2010).   
[21] T. Kinoshita, J. Math.Phys. 3(1962) 650; T.D.Lee and M. Nauenberg, Phys. Rev.133(1964) 1549.   
[22] B. W. Harris and J.F. Owens, Phys. Rev. D65, 094032(2002);   
[23] W. T. Giele and E. W. N. Glover, Phys.Rev. D46,1980 (1992)；W. T. Giele, E. W. Glover and D. A. Kosower, Nucl. Phys. B403, 633 (1993); S. Keller and E. Laenen, Phys. Rev. D59, 114004 (1999).   
[24] S. Dawson and L. Reina, Phys. Rev. D59, 054012 (1999).   
[25] G.P. Legage, J. Comput. Phys. 27, 192(1978).   
[26] P.H. Khiem, J. Fujimoto, T. Ishikawa, T. Kaneko, K. Kato, Y. Kurihara, Y. Shimizu and T. Ueda et al., Eur. Phys. J. C 73, 2400 (2013)[arXiv:1211.1112 [hep-ph].   
[27] W. Hollik and C. Meier, Phys.Lett. B 590 (2004) 69-75   
[28] T. Hahn, Comput. Phys. Commun. 140 (2001) 418-431.   
[29] T.Hahn,M. Perez-Victoria, Comput.Phys. Commun. 118 (1999) 153-165.   
[30] G.J. van Oldenborgh,Phys Commun 66,1, NIKHEF-H-90-15 (1991)；G.t Hooft and M. Veltman, Nucl. Phys.B 153, 365 (1979)； A. Denner,Fortschr. Phys.41, 307 (1993).   
[31] N. Liu, Phys. Lett.B 707,137 (2012) [arXiv:1112.3702 [hep-ph].   
[32] N. Liu, J. Ren and B. Yang,arXiv:1310.6192 [hep-ph].   
[33] A. Pukhov et al., hep-ph/9908288.   
[34] J.Beringer et al. (Particle Data Group), Phys. Rev. D 86, O10001 (2012).