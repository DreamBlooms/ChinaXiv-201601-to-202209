# Discussion on upper limit of the precision for $\tau$ mass measurement\*

X.H.Mo1t

1 (Institute of High Energy Physics, Chinese Academy of Sciences, Beijing 100049, China )

March 8, 2017

# Abstract

$\tau$ lepton is one of three chareged leptons in nature, the measurements of its mass have been performed since its discovery. The present relative accuracy is already at the level of $1 0 ^ { - 4 }$ ; more factors are still being studied in order to increase the accuracy. However, the available techniques for analysis and expectable luminosity from $e ^ { + } e ^ { - }$ collider indicate that the precision upper limit of $\mathit { \Delta } ^ { \prime } \mathcal { I } \mathit { \Delta }$ mass is almost reached, which means that brand new approaches should be looked for if the great improvement is yearned for.

Key words $\tau$ mass,upper limit,high precision PACS: 14.60.Fg, 13.35.Dx,13.66.Jn

# 1 Introduction

The history of $\tau$ mass $( m _ { \tau } )$ measurement has forty years. In the frst experimental paper of $\tau$ lepton [1], $m _ { \tau }$ is estimated to have a mass in the range from 1.6 to 2.0 GeV. Since then many experiments have been performed to measure $m _ { \tau }$ [2, 3, 4, 5, 6, 7, 8, 9, 10,11,12, 13,14, 15,16, 17], the results are displayed in Fig. 1.

The measurement results of $m _ { \tau }$ in the 21 century are summarized in Table 1, where two results were acquired using the method of pseudo-mass while the others using the method of threshold scan. For the pseudo-mass method, the huge amount of data from B-factories are employed [14], good statistical accuracy is acquired, but large systematic uncertainty exists,which is mainly due to the absolute calibration of the particle momentum. For the threshold-scan method, the value of $m _ { \tau }$ was extracted from the dependence of production cross section on beam energy. In the KEDR experiment [15], both resonant depolarization technique and Compton backscattering technique [2] are used to determine the beam energy. All these techniques greatly decrease the uncertainty of beam energy.

Table 1: Measurement results of $m _ { \tau }$ in the 21 century.   

<html><body><table><tr><td>Measured mr (value+statistic+systematic)</td><td>Year</td><td>Exp. Group</td><td>Data sample</td><td>Method</td></tr><tr><td>1776.91 ± 0.12±8.13</td><td>2014</td><td>BESIII [17]</td><td>23.26 pb-1</td><td>Threshold-scan</td></tr><tr><td>1776.68 ± 0.12 ±0.41 -0.13</td><td>2009</td><td>Babar [16]</td><td>423 fb-1</td><td>Pseudo-mass</td></tr><tr><td>1776.81±0:25 ± 0.15</td><td>2007</td><td>KEDR [15]</td><td>6.7 pb-1</td><td>Threshold-scan</td></tr><tr><td>1776.61 ± 0.13 ± 0.35</td><td>2007</td><td>Belle [14]</td><td>414 fb-1</td><td>Pseudo-mass</td></tr></table></body></html>

Although the accuracy of results from above two methods are at the comparable level, it is obvious that the systematic errors already dominate for the pseudo-mass method, the enhancement of luminosity is already unappealing. For the threshold-scan method, both the statistic and systematic errors still seem to have room for the further improvement. Therefore, the subsequence discussions will be devoted to the threshold-scan method.

# 2 Statistic aspect

By the virtue of optimization theory [23], the relation between the absolute error of $m _ { \tau }$ (denoted by $u$ ）and the total luminosity (denoted by $L$ ）is given by the following formula

$$
u = { \frac { A } { \sqrt { L } } } \ ,
$$

where $A$ is a constant depending on the cross section, the derivative of cross section to $m _ { \tau }$ , and some other quantities [23].

An effective error variation that is called $L$ -profit,is introduced and defined as

$$
\nu \equiv \operatorname * { l i m } _ { \Delta L  0 } [ - \frac { \Delta u } { \Delta L } ] = - \frac { d u } { d L } = \frac { A } { 2 } L ^ { - \frac { 3 } { 2 } } \ .
$$

The minus in the above definition indicates that when $L$ increases $u$ always decreases. This quantity discloses the variation of $u$ for a unit luminosity. Although it is reasonable to expect the reduction of error when the luminosity accumulates,but $L$ -profit will also be small for larger $L$ . Refer to Fig.2, when $u$ is considerably large, the enhancement of

![](images/ae4cd2388a453a88110e15f15392994bbcbd588a754985a447c6932034aa7ffa.jpg)  
(b) $m _ { \tau }$ measured in the 21 century   
Figure 1: $m _ { \tau }$ measured in the last and this century. In (a) the red line indicates the average value of $m _ { \tau }$ in PDG2000 [18]: $m _ { \tau } = 1 7 7 7 . 0 3 _ { - 0 . 2 6 } ^ { + 0 . 3 0 }$ MeV.For comparison, the measured value from BES in 1996 is also plotted in (b) but with blank blue circle for distinction. The average value of $m _ { \tau }$ in PDG2015 [19]: $m _ { \tau } = 1 7 7 6 . 8 6 \pm 0 . 1 2$ MeV is also indicated by the red line in (b). It should be noted that since PDG1996 [20, 21], the results from experiements performed before 1990 were removed except for the result of DELCO.

$L$ can effectively lead to the prominent improvement of $u$ . But step by step,when $u$ is already accurate enough,a great mount of $L$ has to be consumed for reducing the error while the improvement is very limited, which is rather uneconomical.

The above analysis is not the whole story. As a matter of fact, the increment of $L$ （20 means that more machine time must be used,more data must be dealt with,and more analysis must be performed. Moreover, the improvement of $u$ means that a lot of work concerning systematic uncertainty analysis must be finished, which in turn leads to the necessary demand for improvement of Monte Carlo simulation. A great amount of details has to be taken into account, sometime the upgrade of software is indispensable as well. Intuitively the work consumed for error improvement increases exponentially，and this is even more real when error is already small enough1. Under such a consideration， a work-factor $D$ is designated as

$$
D = e ^ { \frac { B } { u } } = e ^ { C \sqrt { L } } , \ \mathrm { w h e r e } \ C = { \frac { B } { A } } \ .
$$

Here the constant $B$ will be related to concrete analysis procedure. Similar to Eq. (2),

1There is no induction model or deduction proof for this exponential assumption, since the work done for a certain target is usually hard to be quantified. But for such an assumption,an interesting fact is worthy of mentioning which may be edificatory for understanding the exponential accretion. In the standard model the contribution to the anomalous magnetic moment $a _ { e }$ comes from three types of interactions, electromagnetic,hadronic,and electroweak:

$$
a _ { e } = a _ { e } ( \mathrm { Q E D } ) + a _ { e } ( \mathrm { h a d r o n i c } ) + a _ { e } ( \mathrm { e l c t r o w e a k } ) .
$$

The QED contribution can be evaluated by the perturbative expansion in $\alpha / \pi$

$$
a _ { e } ( \mathrm { Q E D } ) = \sum _ { n = 1 } ^ { \infty } \left( \frac { \alpha } { \pi } \right) ^ { n } a _ { e } ^ { ( 2 n ) } \ ,
$$

where $a _ { e } ^ { ( 2 n ) }$ is finite due to the renormalizabilityof QED and may be writen in general as

$$
a _ { e } ^ { ( 2 n ) } = A _ { 1 } ^ { ( 2 n ) } + A _ { 2 } ^ { ( 2 n ) } ( m _ { e } / m _ { \mu } ) + A _ { 2 } ^ { ( 2 n ) } ( m _ { \mu } / m _ { \tau } ) + A _ { 3 } ^ { ( 2 n ) } ( m _ { e } / m _ { \mu } , m _ { \mu } / m _ { \tau } )
$$

to show the mas-dependence explicitly. $A _ { 1 } ^ { ( 2 n ) }$ can be calculated by QED theory perturbatively with the increase of the order $n$ . It is noticeable that the number of Feynman diagrams increase even more rapidly than the exponential increase with respect to $n$ . The following table shows the interesting comparison [24, 25].

<html><body><table><tr><td colspan="5">Number of Feynman diagrams (N.F.D.) forA（2n）</td></tr><tr><td>order</td><td>n=1</td><td>n=2</td><td>n=3 n=4</td><td>n=5</td></tr><tr><td>A（2n)</td><td>A2</td><td>A</td><td>A8 A</td><td>A（10)</td></tr><tr><td>N.F.D.</td><td>1</td><td>5 72</td><td>891</td><td>12672</td></tr><tr><td>e2(n-1)</td><td>1</td><td>7.39</td><td>54.60 403.43</td><td>2980.96</td></tr></table></body></html>

another effective error variation that is called $D$ -profit, is introduced and defined as

$$
\xi \equiv \operatorname * { l i m } _ { \Delta D  0 } [ - \frac { \Delta u } { \Delta D } ] = - \frac { d u / d L } { d D / d L } = \frac { A ^ { 2 } } { B } ( L e ^ { C \sqrt { L } } ) ^ { - 1 } \ .
$$

If refer to Fig.2, it is fairly clear that the decrease of $\xi$ with $L$ is violent,which indicates the increase of luminosity will play smaller and smaller efect on the improvement of $m _ { \tau }$ In another word the error improvement of $m _ { \tau }$ in $e ^ { + } e ^ { - }$ collider is no room using current method.

![](images/a181959c7e43ccf330a80ea0989dbf59aff53eaebbdfa2cd65e6e1cdd76a98f4.jpg)  
Figure 2: The relation between luminosity and error. The black solid line denotes the variation of $u$ against $L$ ; the red dash line the variation of $\nu$ against $L$ ; the blue dotted line the variation of $\xi$ against $L$ . In calculation $A = 1$ and $B = 1$ are adopted.

To have a concrete impression of above analysis, we compare two pedagogical experiments, the first one intends to decrease the error from 2 MeV to 1 MeV, while the second one intends to decrease the error from 0.2 MeV to 0.1 MeV. The coefficients $A$ and $B$ are chosen to be 1 for the unit of MeV. The ratio of aforementioned quantities is defined as

$$
R _ { X } ^ { i } \equiv { \frac { X _ { a } ^ { i } } { X _ { b } ^ { i } } } ~ ,
$$

where superscript $i$ indicates the first ( $i = 1$ ） or the second ( $i = 2$ ）experiment； subscript （204号 $a$ means the value after experiment,while $b$ the value before experiment. The symbol $X$ denotes the quantity $L$ ， $\nu$ ， $D$ ，and $\xi$ respectively. The evaluations are presented in Table 2.

Based on Table 2 we know that if the error is improved to be one half of the previous experiment, four fold luminosity is required,and luminosity profit is one eighth. Actually according to quantities $L$ and $\nu$ ，as long as the improvement proportion is the same, $R _ { L }$ and $R _ { \nu }$ are the same. This also implies that these two quantities can reflect neither the realistic working strength nor working profit. Turning to another two quantities $R _ { D }$ and $R _ { \xi }$ ,the situation becomes rather different. Although the improvement proportion is the same for the two experiments, the work have to be done for the second experiment is ninety times more than that for the first one, while $D$ -profit for the second one is merely one ninetieth of the first one! This reminds us of the statement,that is,when $u$ is already accurate enough the further increase of luminosity is uneconomical and ineffective.

Table 2: Evaluations for pedagogical experiments.   

<html><body><table><tr><td>Ratio value</td><td>First Exp. 2 →1 MeV</td><td>Second Exp. 0.2 → 0.1 MeV</td></tr><tr><td>RL = (ub/ua)²</td><td>4</td><td>4</td></tr><tr><td>Rv = (ua/ub)3</td><td>1/8</td><td>1/8</td></tr><tr><td>RD = e(1/ua-1/ub)</td><td>1.65</td><td>148</td></tr><tr><td>Rg = (ua/ub)².e(1/ub-1/ua)</td><td>0.15</td><td>1.69 × 10-3</td></tr></table></body></html>

A remark is in order here. During the study of $m _ { \tau }$ scan，BESIII collaboration have make methodical and meticulous studies on optimization process, to guarantee the effective usage of available luminosity [23,26, 27, 28, 29]. Nevertheless, this effort is not helped with the low $R _ { \xi }$ issue.

# 3 Limit due to systematic errors

For BESIII collaboration, before the actual scan of $m _ { \tau }$ , many studies have been made, one of which is the systematic estimation [26] as listed in Table 3. It can be seen that the error due to energy scale dominates. To decrease such an uncertainty, starting from year 2007,a high accuracy beam energy measurement system (BEMS） located at the north crossing point (NCP） of BEPC-II was designed, constructed, and put into the commissioning at the end of 2010 [30,31, 32,33]. The launching of the system is excellently well,two days are utilized to perform $\psi ^ { \prime }$ resonance scan. The mass difference between the PDG201O value [34] and the measured result by BEMS is $1 \pm 3 6$ keV, the deviation of which indicates that the relative accuracy of BEMS is at the level of $2 \times 1 0 ^ { - 5 }$ [32].

In the actual data taking process, it is found that the measurement accuracy of BEMS is sensitive to the running status of accelerator [35]. At the end of 2011, a test scan of $m _ { \tau }$ （20 was performed. The integrated luminosity around of $2 3 . 2 6 ~ \mathrm { p b ^ { - 1 } }$ is collected in the vicinity of $\tau$ -pair threshold, together with $1 . 5 ~ \mathrm { p b } ^ { - 1 }$ and $7 . 5 ~ \mathrm { p b } ^ { - 1 }$ data sets for the $J / \psi$ and $\psi ^ { \prime }$ resonance scans respectively, by virtue of which the systematic uncertainty due to beam energy is determined. The mass of $\tau$ lepton is measured from a maximum likelihood fit to the $\tau$ pair production crossection tobe $m _ { \tau } = ( 1 7 7 6 . 9 1 \pm 0 . 1 2 _ { - 0 . 1 3 } ^ { + 0 . 1 0 } ,$ MeV [17], among which the systematic uncertainty due to energy scale also dominates all relevant terms, as shown in Table 4. This tough situation is the same for all other $e ^ { + } e ^ { - }$ colliders that adopt the threshold-scan method, which can not be circumvented either for the pseudo-mass method.

Table 3: Systematic uncertainty estimation for $m _ { \tau }$ measurement from Ref. [26].   

<html><body><table><tr><td>Source</td><td>smt (10-³ MeV)</td><td>Smr/mr (10-6)</td></tr><tr><td>Luminosity</td><td>14.0</td><td>7.9</td></tr><tr><td>Efficiency</td><td>14.0</td><td>7.9</td></tr><tr><td>Branching Fraction</td><td>3.5</td><td>2.0</td></tr><tr><td>Background</td><td>1.7</td><td>1.0</td></tr><tr><td>Energy spread</td><td>3.0</td><td>1.7</td></tr><tr><td>Theoretical accuracy</td><td>3.0</td><td>1.7</td></tr><tr><td>Energy scale</td><td>100</td><td>56.3</td></tr><tr><td>Summation</td><td>102</td><td>57.5</td></tr></table></body></html>

The crucial issue here lies in the uncertainty of energy scale. For BESIII at BEPCII, BEMS was established to control this uncertainty. The working scheme of this system can be described briefly as follows [36]: firstly, the laser source provides the laser beam and the optics system focuses the laser beam and guides it to make head-on collisions with the electron (or positron） beam in the vacuum pipe, here the Compton backscattering process happens; after that the backscattering high energy photon will be detected by the HPGe detector, the detection capacity of which pins down the accuracy of beam energy. For the time being, the limit of relative accuracy for HPGe detector is at the level of $1 0 ^ { - 5 }$ ， which in turn restricts the limit for determination of beam energy². Another juxtaposing restriction at the level of $1 0 ^ { - 5 }$ comes from the long term stability of electric power supply of BEPCII [41]. This stability directly controls that of magnets, which determines the energy of beam.

Table 4: Summary of the $\tau$ mass systematic errors. The meanings of each term can be found in Ref. [17].   

<html><body><table><tr><td>Source △mr (MeV/c²)</td></tr><tr><td>Theoretical accuracy 0.010</td></tr><tr><td>Energy scale ±0.022</td></tr><tr><td>Energy spread 0.016</td></tr><tr><td></td></tr><tr><td>Luminosity 0.006</td></tr><tr><td>Cut on number of good photons 0.002</td></tr><tr><td>Cuts on PTEM and acoplanarity angle 0.05</td></tr><tr><td>mis-ID efficiency 0.048</td></tr><tr><td>Background shape 0.04</td></tr><tr><td>Fitted efficiency parameter ±0.038 Total ±0.14</td></tr></table></body></html>

# 4 Way out for accuracy improvement

The preceding analyses obviously indicate that the efforts spent on $e ^ { + } e ^ { - }$ collider are not to bring the promising improvement on the accuracy of $m _ { \tau }$ . Therefore, the new approach indeed needs to be figured out in order to increase the accuracy of $m _ { \tau }$ significantly. Without any plausible precedent or theoretical implication, we would like to look at some relevant measurements with high accuracy to fsh out some clues for $m _ { \tau }$ experiments in the future.

# 4.1 Experimental aspect

According to PDG2012 [42]

$$
\begin{array} { l } { { 0 . 5 1 0 9 9 8 9 1 0 \pm 0 . 0 0 0 0 0 0 0 1 3 ~ \mathrm { M e V } \quad ( { \delta m _ { e } } / { m _ { e } } \approx 2 . 5 5 4 \times 1 0 ^ { - 8 } ) } } \\ { { 1 0 5 . 6 5 8 3 6 7 \pm 0 . 0 0 0 0 0 4 ~ \mathrm { M e V } \quad ( { \delta m _ { \mu } } / { m _ { \mu } } \approx 3 . 7 8 6 \times 1 0 ^ { - 8 } ) ~ , } } \end{array}
$$

Such a highly precise determination of an electron's mass comes from measuring the ratio of the mass to that of a nucleus,so that the result is obtained in $m _ { u }$ (atomic mass units). For example， by comparing cyclotron frequencies of electrons and single $C ^ { 6 + }$ （204号 ions alternately confined to the same uniform magnetic field in a Penning trap [43], the electron's mass is determined as

$$
m _ { e } = 0 . 0 0 0 5 4 8 5 7 9 9 1 1 1 ( 1 2 ) m _ { u } .
$$

Then a convert factor 941.494013 ± 0.000037 MeV/ $m _ { u }$ is used [42, 44] to transform unit $m _ { u }$ into MeV.

As far as the muon's mass is concerned, it is obtained from the muon-electron mass ratio as determined from the measurement of Zeeman transition frequencies in muonium ( $\mu ^ { + } e ^ { - }$ atom). Unfortunately, the life time of $\tau$ lepton is too short to form such an atom, so the mass of $\tau$ lepton can not be determined accurately in the similar way.

Anyway, it is fairly enlightened that we should find a relation of $m _ { \tau }$ with another sensitive quantity which can be measured accurately, or their ratio can be measured accurately. This might be the new direction for the further accurate measurement of $m _ { \tau }$ ：

# 4.2 Theoretical aspect

Similar to the situation of experiment, theoretically speaking, if a certain relation can be found for $m _ { \tau }$ , the excellent accuracy may be expected. Here we mention an interesting formula of masses of three leptons [45, 46, 47, 48]:

$$
m _ { e } + m _ { \mu } + m _ { \tau } = \frac { 2 } { 3 } ( \sqrt { m _ { e } } + \sqrt { m _ { \mu } } + \sqrt { m _ { \tau } } ) ^ { 2 } \ ,
$$

In the light of which it is easy to find

$$
\sqrt { m _ { \tau } } = 2 ( \sqrt { m _ { e } } + \sqrt { m _ { \mu } } ) + \sqrt { 3 ( m _ { e } + m _ { \mu } ) + 1 2 \sqrt { m _ { e } \cdot m _ { \mu } } } \ .
$$

Using this formula together with the mass values for electron and muon in Eq. (6) the $m _ { \tau }$ can be obtained together with the corresponding error as follows

$$
m _ { \tau } = 1 7 7 6 . 9 6 8 8 8 4 \pm 0 . 0 0 0 0 5 8 \ \mathrm { M e V } \quad ( { \delta m _ { \tau } } / { m _ { \tau } } \approx 3 . 2 6 \times 1 0 ^ { - 8 } ) .
$$

Unfortunately, the formula (7) itself is not obtained from the first principle of particle physics,so this kind of efforts can only be treated as an attempt direction in the future?.

$$
m ( N ) = m _ { e } \left( 1 + \frac { 3 } { 2 } \alpha ^ { - 1 } \sum _ { n = 0 } ^ { N } n ^ { 4 } \right) \ ,
$$

where $m _ { e }$ is the mass of electron and $\alpha \approx 1 / 1 3 7$ the electromagnetic fine structure constant.The masses of electron,muon,and tauon correspond to $N = 0$ ， $^ { 1 }$ ，and 2,respectively.

# 5 Summary

In this paper, the issue concerned the upper limit of the error of $m _ { \tau }$ measuremen（20 $\mathrm { t }$ is discussed from unconventional point of view. The main conclusions acquired are summarized below:

1. Statistically speaking, the increase of luminosity have no effective effect on the accuracy improvement of $m _ { \tau }$ . Moreover, from point view of efficiency and profitability, the input-output ratio will considerably decrease as the accuracy of $m _ { \tau }$ increases.   
2. Systematically speaking, the limit at the level of $1 0 ^ { - 5 }$ of both calibration of HPGe detector and energy stability of accelerator circumscribes the accuracy limit of $m _ { \tau }$ ： For experiments at $e ^ { + } e ^ { - }$ collider, this is the insurmountable limit for the systematic uncertainty.   
3. The absolutely distinctive train of thought from both theoretical and experimental aspects is needed to seek a new direction to increase the accuracy of $m _ { \tau }$ ：

# References

[1] M. L. Perl et al., Phys. Rev. Lett. 35,1489 (1975).   
[2] M. L. Perl et al., Phys. Lett. B 70, 487 (1977).   
[3] DASP Collaboration,R. Brandelik et al., Phys.Lett. B 73,109 (1978).   
[4] W. Bartel et al., Phys. Lett. B 77, 331 (1978).   
[5] W. Bacino et al., Phys. Rev. Lett. 41 (1978) 13.

Besides the dynamic-inspired heuristic researches, there are also phenomenological efects towards a systematic comprehension of the variety of elementary particles,two of which are to be recapitulated herein． The first one is the $\alpha$ -quantized scheme suggested by M.H.Mac Gregor [54, 55, 56, 57]. Based on investigating 36 metastable threshold-state (lifetimes great than $1 0 ^ { - 2 1 }$ second), $\alpha$ -spaced groups are found, which exhibit a factor-of-3 c-quark-to-b-quark “favor structure” and a pervasive factor-of-2 “hyperfine structure”. And these structures can be parameterized by two-variable-quantum scheme.

The second one is the shell-quantized scheme proposed by P.Palazz [58,59,60]. Edifying by nuclear shell-structure,the stability analysis of the mass spectrum reveals the clear mesonic shel-structure. A type-specifc mass unit in the vicinity of 35 MeV is verifed for all the meson-states listed by the PDG with fairly good accuracy except for only 5 abnormal mesons. Furthermore,the quantization of mass unit can be geometrically qualified by the face-centered-cubic model of the nucleus [61].

Up till now, no breakthrough achievement has been acquired.Nevertheless,the explorations related to the mass spectrum indicates another direction on the understanding of high energy physics,which might bring an unprecedented result some day in the future.

[6] C.A. BLOCKER et al., Phys. Lett. B 109,119 (1978).   
[7] ARGUS Collaboration, H. Albrecht et al., Phys. Lett. B292 (1992) 221.   
[8] BES collaboraton, J.Z. Bai et al.,Phys. Rev.Lett. 69 (1992) 3021.   
[9] BES collaboraton, J.Z. Bai et al., Phys. Rev. D53 (1996) 20.   
[10] BES collaboraton, J.Z. Bai et al., HEP&NP 16 （1992） 343.   
[11] CLEO Collaboration, R. Balest et al., Phys. Rev. D47 (1993) 3671;   
[12] CLEO Collaboration, A. Anastassov et al., Phys. Rev. D55 (1997) 2559; Phys. Rev. D58 (1998) 119904 (Erratum).   
[13] OPAL Collaboration, G. Abbiendi et al., Phys. Lett. B492 (2000) 23.   
[14] Belle collaboraton, K. Belous et al.,Phys. Rev. Lett. 99 (2007) 011801.   
[15] KEDR collaboraton, V.V. Anashin et al. J. Exp. The. Phys. Lett. 85 (2007) 347.   
[16] Babar collaboraton,B. Aubert et al., Phys. Rev. D80 (2009) 092005.   
[17] M.Ablikim et al. [BESIII Collaboration]，Phys. Rev. D 90,no. 1， O12001 (2014) [arXiv:1405.1076 [hep-ex].   
[18] D.E. Groom et al. (Particle Data Group), Eur. Phys. J. C,15,(2000).   
[19] K.A. Olive et al. (Particle Data Group), Chin. Phys. C,38, 090001 (2014) and 2015 update.   
[20] R.M. Barnett al. (Particle Data Group), Phys. Rev. D, 54,1 (1996).   
[21] L. Montanet al. (Particle Data Group), Phys. Rev. D, 50, 1173 (1994).   
[22] A. Bogomyagkov et al.， “Research of Possibility to use Beam Polarization for Absolute Energy Calibration in High-precision Measurement of Tau Lepton Mass at VEPP-4M.”, Presented at the 9th European Particle Accelerator Conference (EPAC 2004),Lucerne, Switzerland, July 5-9, 2004.   
[23] X.H. Mo, Int. J. Mod. Phys. A 30,1550149 (2015) [arXiv:1505.00059 [hep-phl].   
[24] T. Aoyama, M. Hayakawa, T. Kinoshita and M. Nio, Phys. Rev. Lett.109, 111807 (2012) [arXiv:1205.5368 [hep-ph]].   
[25] W.Greiner, J. Reinhardt, Quantum Electrodynamics, Springer-Verlag, Berlin, 2003.   
[26] Y.K. Wang, X.H. Mo, C.Z. Yuan, J.P. Liu, Nucl. Instr. Methd. A 583, 479 (2007).   
[27] Y.K. Wang, J.Y. Zhang, X.H. Mo, C.Z. Yuan, Chin. Phys. C 33, 501 (2009).   
[28] B.Q. Wang, X.H. Mo, C.Z. Yuan, Int. J. Mod. Phys. A 27, 1250150 (2012).   
[29] B.Q. Wang, X.H. Mo, Chin. Phys. C 37, 026202 (2013).   
[30] Achasov M.N. et al.,Nucl. phys. B (Proc. Suppl.) 189 (2009) 366-370.   
[31] MO Xiao-Hu et al., Chinese Physics C, 2010, 34: 912-917.   
[32] ABAKUMOVA E.V. et al.,Nucl. Instr. Meth. A 659 (2011) 21-29.   
[33] Zhang J.Y. et al., Nuclear Physics B -Proceedings Supplements Volumes 225-227, April-June 2012, Pages 309-314   
[34] K. Nakamura et al. (Particle Data Group), J. Phys. G 37, 075021 (2010)   
[35] MO Xiao-Hu, Chinese Physics C 2014 28: 106203   
[36] MO Xiao-Hu et al., Chinese Physics C, 2008, 32: 995.   
[37] Y. Nambu, Prog. Theor. Phys. 7, 131 (1952).   
[38] A.O. Barut, Surveys in High Energy Physics, 1980, 1(2):113-140   
[39] A. Bettini Riv.Nuovo Cim. 32 (2009) 295-337   
[40] Luis J. Boya, Cristian Rivera, Physics of Particles and Nuclei, 2011, Vol. 42, No. 5, pp. 800C811.   
[41] C.Zhang and L.Ma, Accelerator design and research of Beijing electron-positron collider significant reform project, Shanghai Scientific and technical Publishers, Shanghai, 2015 (in Chinese).   
[42] J. Beringer et al. (Particle Data Group), Phys. Rev. D 86, O10001 (2012) and 2013 update.   
[43] D. L. Farnham, R. S. Van Dyck and P. B. Schwinberg, Phys. Rev. Lett. 75, 3598 (1995).   
[44] P. J. Mohr and B. N. Taylor, Rev. Mod. Phys. 72,351 (2000).   
[45] Y. Koide, Mod. Phys. Lett. A 5, 2319 (1990).   
[46] Y. Koide, Lett. Nuovo Cimento 34, 201 (1982).   
[47] Y. Koide, Phys. Lett. 120B,161 (1983).   
[48] Y. Koide, Phys. Rev. D 28, 252 (1983).   
[49] A. Rivero and A. Gsponer, arXiv:hep-ph/O505220.   
[50] Y. Koide and H. Nishiura, Phys. Rev. D 91, no.11, 116002 (2015) [arXiv:1503.04900 [hep-ph]].   
[51] A.O. Barut,Phys.Rev. Lett. 42 (1979) 1251.   
[52] A. Gsponer and J.-P. Hurni, Hadronic Journal 19 (1996) 367-373, e-print arXiv:hepph/0201193.   
[53] G. Rosen, Int. J. Theor. Phys. 34,31 (1995).   
[54] M.H.Mac Gregor, International Journal of Modern Physics A 20,(2005) 719-798 and 2893-2894.   
[55] M. H. Mac Gregor, Phys. Rev. D9, 1259 (1974), Sec. XII.   
[56] M. H. Mac Gregor, Phys. Rev. D13, 574 (1976).   
[57] M. H. Mac Gregor, Nuovo Cimento A103, 988 (1990).   
[58] P.Palazzi， Particles and Shells， http://cdsweb.cern.ch， CERN-OPEN-2003-006 (2003).   
[59] P. Palazzi, Patterns in the Meson Mass Spectrum, http://particlez.org ， p3a-2004-001 (2004).   
[60] P. Palazzi, Meson Shells, http://particlez.org ，p3a-2005-001 (2005).   
[61] N. D. Cook and V. Dallacasa, Phys. Rev. C 35, 1883 (1987).