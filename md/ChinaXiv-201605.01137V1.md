# A new approach for detecting compressed bino/wino at the LHC

Chengcheng Han $\cdot ^ { 1 }$ ， Lei Wu $^ 2$ ， Jin Min Yang $^ 3$ ， Mengchao Zhang $^ 3$ ， Yang Zhang $^ 3$

（204号 $^ { 1 }$ Asia Pacific Center for Theoretical Physics， San 31, Hyoja-dong， Nam-gu, Pohang 790-784， Republic of Korea （204号 $^ 2$ ARC Centre of Excellence for Particle Physics at the Terascale, School of Physics， The University of Sydney， NSW 2006， Australia （ $^ 3$ State Key Laboratory of Theoretical Physics, Institute of Theoretical Physics， Academia Sinica, Beijing 100190, China

Abstract

In some supersymmetric models like split supersymmetry or models with non-universal gaugino mass,bino (LSP) and winos (NLSP) may have rather small mass splitting in order to provide the correct dark matter relic density through bino/wino co-annihilation. Such a scenario with the compressed bino/wino is difficult to explore at the LHC. In this work we propose to probe this scenario from $p p  j \tilde { \chi } _ { 2 } ^ { 0 } \tilde { \chi } _ { 1 } ^ { \pm }$ followed by $\tilde { \chi } _ { 2 } ^ { 0 }  \gamma \tilde { \chi } _ { 1 } ^ { 0 }$ and $\tilde { \chi } _ { 1 } ^ { \pm }  W ^ { * } \tilde { \chi } _ { 1 } ^ { 0 }  \ell ^ { \pm } \nu \tilde { \chi } _ { 1 } ^ { 0 }$ (this method is also applicable to the compressed bino/higgsino scenario). Through a detailed Monte Carlo simulation for both the signal and the backgrounds,we find that for a mass splitting $\Delta M \sim 5 - 1 5$ GeV between bino (LSP) and wino (NLSP),the 14 TeV LHC with luminosity of $5 0 0 f b ^ { - 1 }$ can probe the wino up to 150 GeV (the sensitivity can reach $5 \sigma$ for $\Delta M = 5$ GeV and $2 \sigma$ for $\Delta M = 1 5$ GeV). We also investigate the dark matter detection sensitivities for this scenario and find that the planned XENON-1T(2017) cannot fully cover the parameter space with wino below 150 GeV allowed by relic density and the LUX limits.

PACS numbers:

# I. INTRODUCTION

Supersymmetry (SUSY) is a leading candidate beyond the Standard Model (SM), which can simultaneously solve the naturalness problem，explain the cosmic dark matter and achieve the gauge coupling unification. However， current searches at the LHC have not yet found any evidence of SUSY particles (sparticles). The first two generation squarks and gluino mass bounds have been pushed up to TeV region by searching for multi-jets with large missing energy [1]. The light third generation squarks and the non-colored sparticles have also been excluded in the simplifed models [2-5]. In addition,the observation of a 125 GeV Higgs boson [6,7] requires rather heavy stops and/or large stop mixing. These results seem to indicate some sparticle spectrum (like split-SUSY) not favored by the naturalness. Therefore, it is imperative to explore all possible corners of SUSY parameter space and for some special scenarios new search strategies are needed.

In the minimal supersymmetric model (MSSM) with $R$ -parity the direct search of sparticles is mainly influenced by the nature of the lightest sparticle (LSP） and the shape (compressed or not) of the sparticle spectrum. In many popular SUSY models the electroweak gauginos are the most likely candidates for the LSP and the next-to-lightest sparticle (NLSP). The gold-plated’ tri-lepton signature from the associated production of $\tilde { \chi } _ { 2 } ^ { 0 } \tilde { \chi } _ { 1 } ^ { \pm }$ is usually expected to have the best sensitivity for probing the electroweak gaugino sector at the LHC [8]. The ATLAS and CMS collaborations have performed such a study in the simplified wino-like chargino/neutralino scenario, whose nullresults excluded $m _ { \tilde { \chi } _ { 1 } ^ { \pm } }$ ， $_ { \tilde { \chi } _ { 2 } ^ { 0 } } < 3 4 5$ （20 GeV （ATLAS）[9] and $m _ { \tilde { \chi } _ { 1 } ^ { \pm } }$ ， $_ { \tilde { \chi } _ { 2 } ^ { 0 } } < 2 7 0$ GeV (CMS)[10] when the winos decay via intermediate gauge bosons and the LSP is almost a massless bino. As mentioned above, the tri-lepton sensitivity strongly depends on the mass difference $( \Delta M )$ between NLSP and LSP. A large $\Delta M$ is typically required to produce the hard leptons in the final states of the process $p p  { \tilde { \chi } } _ { 2 } ^ { 0 } { \tilde { \chi } } _ { 1 } ^ { \pm }$ followed by $\tilde { \chi } _ { 2 } ^ { 0 }  Z ^ { ( * ) } ( \ell ^ { + } \ell ^ { - } ) \tilde { \chi } _ { 1 } ^ { 0 }$ and $\tilde { \chi } _ { 1 } ^ { \pm }  W ^ { ( * ) } ( \ell ^ { \pm } \nu ) \tilde { \chi } _ { 1 } ^ { 0 }$ .When $\Delta M$ （20 becomes small, a squeezed spectrum of electroweak gauginos would lead to a small missing energy and soft leptons. For such a compressed ( $\Delta M \sim 1 - 5$ GeV） electroweak gauginos one may look for (albeit quite challenging at the LHC) the mono-jet [11,12], mono-photon [13] or mono- $Z$ [14,15] final states,where a visible jet,photon or $Z$ -boson form initial state radiation (ISR） is employed to trigger the process. In addition，an alternative searching strategy $p p  \tilde { \chi } _ { 2 } ^ { 0 } \tilde { \chi } _ { 3 } ^ { 0 }  \ell ^ { + } \ell ^ { - } + \gamma + / { E } _ { T }$ has also been proposed to detect the compressed bino-higgsino in [16],where the dilepton comes from the three body decay $\tilde { \chi } _ { 2 , 3 } ^ { 0 }  \ell ^ { + } \ell ^ { - } \tilde { \chi } _ { 1 } ^ { 0 }$ and the photon is from the loop-induced decay $\tilde { \chi } _ { 2 , 3 } ^ { 0 }  \gamma \tilde { \chi } _ { 1 } ^ { 0 }$ . But this method is suitable only for a‘well-forged’ mass difference $\Delta M \sim 2 5 - 7 0$ GeV.

In this work we propose a new search channel $p p  j \tilde { \chi } _ { 2 } ^ { 0 } \tilde { \chi } _ { 1 } ^ { \pm }$ followed by $\tilde { \chi } _ { 2 } ^ { 0 }  \gamma \tilde { \chi } _ { 1 } ^ { 0 }$ and （204号 $\tilde { \chi } _ { 1 } ^ { \pm }  W ^ { * } ( \ell ^ { \pm } \nu ) \tilde { \chi } _ { 1 } ^ { 0 }$ to probe the compressed （ $\Delta M \sim 5 - 2 0$ GeV） bino (LSP)-winos (NLSP) at the LHC. Note that such a compressed scenario may readily happen in split-SUSY or models with non-universal gaugino masses at the boundary where the correct dark matter relic abundance can be achieved from the bino-wino co-annihilation [17,18]. The final states of this channel are characterized by a hard jet with a soft photon and lepton: $j + \gamma + \ell ^ { \pm } + \not { E } _ { T }$ The detectability of this channel comes from three sides: (1） For the cross section of $j \tilde { \chi } _ { 2 } ^ { 0 } \tilde { \chi } _ { 1 } ^ { \pm }$ ， the winos usually has larger cross section than other electroweakinos; (2) The chargino $\tilde { \chi } _ { 1 } ^ { \pm }$ dominantly decays (with a branching ratio near $1 0 0 \%$ ) into the neutralino LSP plus a virtual （20 $W$ -boson (comparatively the decays $\tilde { \chi } _ { 2 , 3 } ^ { 0 }  \ell ^ { + } \ell ^ { - } \tilde { \chi } _ { 1 } ^ { 0 }$ have very small branching ratios); (3) A hard ISR jet in the final states can avoid the conventional huge electroweak $W \gamma$ background that is the most severe handicap for the $\tilde { \chi } _ { 2 } ^ { 0 } (  \ \gamma \tilde { \chi } _ { 1 } ^ { 0 } ) \tilde { \chi } _ { 1 } ^ { \pm } (  \ \ell ^ { \pm } \nu \tilde { \chi } _ { 1 } ^ { 0 } )$ production. On the contrary, the background $W j \gamma$ can be efficiently removed by requiring large missing energy.

The rest of this work is organized as follows. In Sec.2 we study the observability of this channel at the 14 TeV LHC. In Sec.3 we show the dark matter direct detection sensitivity to the compressed bino-wino scenario. Finally, we draw our conclusion in Sec.4.

# II. PROBING COMPRESSED BINO/WINO AT LHC

A. The production channel and its signal

$$
\frac { W ^ { k } } { \tilde { \chi } _ { k } ^ { 0 } } \int \limits _ { \tilde { \chi } _ { k } ^ { \pm } } ^ { \tilde { \chi } _ { k } ^ { 0 } } \sqrt { \int \limits _ { \tilde { \chi } _ { k } ^ { 0 } } ^ { \tilde { \chi } _ { k } ^ { 0 } } \frac { \tilde { \chi } _ { k } ^ { \pm } } { \tilde { \chi } _ { k } ^ { 0 } } } \int \limits _ { \tilde { \chi } _ { k } ^ { 0 } } ^ { \tilde { \chi } _ { k } ^ { 0 } } \sqrt { \int \displaylimits _ { \tilde { \chi } _ { k } ^ { 0 } } ^ { \tilde { \chi } _ { k } ^ { 0 } } \frac { \tilde { \chi } _ { k } ^ { 0 } } { \tilde { \chi } _ { k } ^ { 0 } } }
$$

FIG.1: The relevant Feynman diagrams for the loop decay $\tilde { \chi } _ { 2 } ^ { 0 }  \gamma \tilde { \chi } _ { 0 } ^ { 1 }$ in our study. Here $k = 1 , 2$ （204号

Concentrating on a small mass splitting between bino and winos (≤ 20 GeV), we consider

the $j + \ell + \gamma + \not { E } _ { T } ^ { m i s s }$ signal from the $\tilde { \chi } _ { 1 } ^ { \pm } \tilde { \chi } _ { 2 } ^ { 0 } j$ production followed by the decays

$$
\begin{array} { r l } & { \tilde { \chi } ^ { \pm }  W ^ { * } \tilde { \chi } _ { 1 } ^ { 0 }  \ell \nu \tilde { \chi } _ { 1 } ^ { 0 } , } \\ & { } \\ & { \tilde { \chi } _ { 2 } ^ { 0 }  \gamma \tilde { \chi } _ { 0 } ^ { 1 } } \end{array}
$$

where the decay channel $\tilde { \chi } _ { 2 } ^ { 0 }  \gamma \tilde { \chi } _ { 0 } ^ { 1 }$ is a loop process [19],as shown in Fig.1. Note that the branching ratio of this decay is sensitive to the mass splitting of $\tilde { \chi } _ { 2 } ^ { 0 }$ and $\tilde { \chi } _ { 0 } ^ { 1 }$ . As shown in Fig.2, when the mass splitting is small enough, this decay has a sizable branching ratio because the tree level three-body decay $\tilde { \chi } _ { 2 } ^ { 0 }  Z ^ { * } \tilde { \chi } _ { 0 } ^ { 1 }  f f \tilde { \chi } _ { 0 } ^ { 1 }$ is suppressed. From Fig.2 we see that for $\Delta m < 2 0$ GeV, the decay $\tilde { \chi } _ { 2 } ^ { 0 }  \gamma \tilde { \chi } _ { 0 } ^ { 1 }$ can have a branching ratio as large as （204号 $1 0 \%$ . As the mass splitting gets large, the decay branching ratio reduces rapidly. We should also note that when the mass splitting is very small ( $< 5$ GeV), the decay branching ratio will reduce a bit. This is because for such a tiny mass splitting $\tilde { \chi } _ { 2 } ^ { 0 }$ would have sizable bino component which will suppress the coupling of ${ \tilde { \chi } _ { 2 } } ^ { 0 } { \tilde { \chi } _ { 1 } } ^ { + } W$ in the loops of Fig.1.

![](images/4dafa2f599c93f434169ea98b8a5daf0676efc8cb2405ed424470a9cb8274938.jpg)

FIG. 2: The dependence of branching ratio of $\tilde { \chi } _ { 2 } ^ { 0 }  \gamma \tilde { \chi } _ { 0 } ^ { 1 }$ on the masses of $\tilde { \chi } _ { 1 , 2 } ^ { 0 }$ . We use SUSYHIT [20] to calculate the branching ratio. The gluino and higgsinio mass parameters $M _ { 3 }$ and $\mu$ are assumed at 2 TeV and 1 TeV, respectively. We vary parameter $\tan \beta$ from 3 to 50 and the gaugino masses $M _ { 1 , 2 }$ from 100 GeV to 300 GeV. All the samples are required to satisfy the Higg mass $1 2 5 \pm 2$ GeV.The slepton and the first two generation squark sectors are set a common mass （204号 $M _ { S U S Y } = 2$ TeV.

In the following we choose four benchmark points to perform Monte Carlo simulation. These points are listed in Table I. Here the masses of $\tilde { \chi } _ { 1 , 2 } ^ { 0 }$ are obtained by tuning the bino

and wino masses.

TABLE I: Four benchmark points used in our Monte Carlo simulation. Here $\mu$ and $\tan \beta$ are se to be 1 TeV and 30, respectively.

<html><body><table><tr><td>(mxi,mxg） in GeV</td><td>(130,150)</td><td>(135,150)</td><td>(140,150)</td><td>(145,150)</td></tr><tr><td>Br(x→xγ)</td><td>0.101</td><td>0.2266</td><td>0.495</td><td>0.834</td></tr></table></body></html>

# B. Monte Carlo simulation for the signal and backgrounds

Our signal is a soft lepton, a soft photon, a hard jet plus large missing energy. The largest background is from the $W \gamma j$ production (the $W$ -boson here can be on-shell or virtual). To suppress this background, we require a rather hard jet $P _ { T } > 3 0 0$ GeV and a large missing energy. Although this requirement can also hurt our signal, the S/B ratio can be enhanced. In addition, since the photon and lepton are typically soft in our signal, we require them to be softer than 40 GeV and 25 GeV, respectively. Our selection criteria are summarized as

(i) One hard jet. We require a hard jet with $P _ { T } ( j _ { 1 } ) > 3 0 0$ GeV and $| \eta ( j _ { 1 } ) | < 2 . 5$ (not （204号 $b$ -tagged). Any events with more visible jets ( $P _ { T } ( j _ { 2 } ) > 3 0$ GeV, $| \eta ( j _ { 2 } ) | < 2 . 5 \$ ）will be vetoed.   
(ii) Large $\boldsymbol { \notin } _ { T } ^ { m i s s }$ . The final state has two massive LSP neutralinos,which recoil to the leading jet and then induce alarge missng energy. Here we require $\mathcal { k } _ { T } ^ { m i s s } > 3 0 0 \mathrm { G e V }$ ．   
(iii) One isolated lepton. We require an isolated electron with $P _ { T } ^ { e } > 1 0 \$ GeV, $| \eta ^ { e } | < 1 . 3 7$ (or $1 . 5 2 < | \eta ^ { e } | < 2 . 4 \$ 7) or an isolated muon with $P _ { T } ^ { \mu } > 1 0$ GeV, $| \eta ^ { \mu } | < 2 . 4$ . An upper limit cut of 25 GeV is also imposed on the lepton $P _ { T } ^ { e , \mu }$   
(iv) One isolated photon. We require an isolated photon with $| \eta ^ { \gamma } | < 2 . 3 7$ (excluding the calorimeter transition region $1 . 3 7 < | \eta ^ { \gamma } | < 1 . 5 2 )$ and $P _ { T } ^ { \gamma } > 1 0 \$ GeV.Also an upper limit cut of 40 GeV is imposed on the photon $P _ { T } ^ { \gamma }$

Fig.3 shows the production rate of $\tilde { \chi } _ { 1 } ^ { \pm } \tilde { \chi } _ { 2 } ^ { 0 } j$ at the 14 TeV LHC for different wino masses. Here the cross section is calculated at tree level by using MadGraph5 (in order to obtain reasonable statistics,we imposed a cut $p _ { T } ( j _ { 1 } ) > 2 5 0$ GeV on the first leading jet for signals and backgrounds in the parton-level events generation). From this figure we see that the production rate can reach O.1 pb when the $\tilde { \chi } _ { 2 } ^ { 0 }$ mass is below $1 3 0 \mathrm { \ G e V }$ . In our benchmark points where the $\tilde { \chi } _ { 2 } ^ { 0 }$ mass is 150 GeV, the cross section can reach 0.074 pb before multiplying the decay branching ratios.

![](images/7262582f40d53af20661bd2c4532da8b5b4292a3201fe24400f2ec4352f40ebd.jpg)  
FIG. 3: The dependence of the cross section of $\tilde { \chi } _ { 1 } ^ { \pm } \tilde { \chi } _ { 2 } ^ { 0 } j$ on the $m _ { \tilde { \chi } _ { 2 } ^ { 0 } }$ at 14 TeV LHC.

As mentioned above, the dominate background is from the $W \gamma j$ production whose cross section is about O.75 pb at tree level (with $P _ { T } ( j _ { 1 } ) > 2 5 0 ~ \mathrm { G e V } ,$ ). Another sizable background is $Z ( \tau \tau )$ +jets with $\tau$ decays in the lepton channel and one of the leptons mistagged as a photon (the large missing energy can arise from the neutrinos from the $\tau$ leptonic decays). Although the $\tau$ decay branching ratio and the efficiency of a lepton misidentified as a photon can suppress the $Z ( \tau \tau )$ +jets background, this background cannot be ignored because its production rate is quite large (0.84 pb with $P _ { T } ( j _ { 1 } ) > 2 5 0 ~ \mathrm { G e V } ,$

About other possible backgrounds we have the following comments:

· W+jets background. The ATLAS performed the measurement of $W \gamma$ production [21] where W+jets is the background. In the experiment an inclusive measurement is performed after requiring: exactly one lepton with $P _ { T } > 2 5$ GeV,at least one isolated photon with $E _ { T } ^ { \gamma } > 1 5 \$ GeV and $\boldsymbol { \mathbf { \mathit { \mathbb { E } } } _ { T } ^ { m i s s } }$ above 35 GeV. Other selection requirements include: $m _ { T }$ should be larger than 40 GeV and $m _ { e \gamma }$ is not within 15 GeV of $Z$ -boson mass. We note that the W+jets events can mimic $W \gamma$ signal when a jet is mistagged as a photon. We calculate the $\sigma _ { W + j e t s } / \sigma _ { W \gamma }$ value after these cuts (for W+jets events we choose a jet as a photon) and compare with the final counting events in the experiment. We find the efficiency of the jets mistagged as a photon to be $\sim 1 0 ^ { - 4 }$ . We recalculate the $\sigma _ { W + j e t s } / \sigma _ { W \gamma j }$ value at 14 TeV after our cuts and find it $\lesssim 1 0 0$ . After multiplying the mistagged factor we find that the W+jets background is much smaller than the $W \gamma j$ background.

· Top quark background. The $t t$ background can mimic our signal when top quarks decay leptonically and one of the leptons is mis-tagged as a photon. We calculate the （204 $t t$ cross sectionunder the requirement ${ \not { E } } _ { T } ^ { m i s s } > 2 0 0$ GeV at parton level andfind it to be 0.32 pb.Thecut efcency with $\notin _ { T } ^ { m a s s } > 3 0 0$ GeV and $P _ { T } ( j _ { 1 } ) > 3 0 0$ GeV (for the leading jet） is about O.1. The probability to find a pre-selection lepton and photon is 0.02. The cut effciency for the lepton and photon is O.15 and 0.3, respectively. The jet veto and $b$ -jet veto takes factor more than 40. After all the cuts, this background is approximately smaller than O.001 fb. So we can safely ignore this background. Another background is $t t \gamma$ whose production rate is 4 fb after requiring $\notin _ { T } ^ { m i s s } > 2 0 0$ （ GeV at parton level. The efficiency with all the cuts is $6 . 0 \times 1 0 ^ { - 4 }$ . So its contribution is also negligible.

· WW/ZZ/ZW. The production rate of these gauge bosons is at fb level after requiring a leading jet harder than 250 GeV and a factor smaller than 0.O6 should be multiplied to include the lepton mistagging as a photon.   
· $Z \gamma j$ . This background has a fb production rate after requiring a leading jet larger than 250 GeV and can be suppressed by requiring large $E _ { T } ^ { m i s s }$ . So it can be safely neglected.

Other backgrounds like Z+jets when Z decays to electrons or muons and a lepton can be faked as a photon and the $\gamma$ +jets background when a jet is misidentified as a lepton，are highly suppressed by the requirement of $\sharp _ { T } ^ { m i s s } > 3 0 0 \$ GeV and also by a smallmistag factor.

We use MadGraph5 [22] to simulate the signal and the backgrounds. We carry out the parton shower and the fast detector simulation through PYTHlA [23] and Delphes [24], respectively. We also use the anti- $k _ { t }$ algorithm [25] to cluster jets and match our matrix element with parton shower in MLM scheme [26]. The cross sections of the signal and backgrounds are evaluated at tree level in our simulation.

In Table II we show the cut flows of backgrounds and signal. We see that the background $W \gamma j$ can be suppressed by requiring the lepton and photon to be soft. With all the cuts the efficiency of the signal is about an order larger than the $W \gamma j$ background.

TABLE I: Thecut effciencyforthe ackgroundsandthe signal $j + \ell + \gamma + \not { E } _ { T } ^ { m \imath s s }$ . The signal efficiency is displayed for the four benchmark points listed in Table I.   

<html><body><table><tr><td>cuts</td><td>Wyj</td><td>Z(T𝑇)+j(130,150)</td><td></td><td>(135,150)</td><td>(140,150)</td><td>(145,150)</td></tr><tr><td>an isolated lepton p > 10 GeV51.9%</td><td></td><td>28.5%</td><td>35.7%</td><td>31.7%</td><td>25.9%</td><td>16.1%</td></tr><tr><td>p<25 GeV</td><td>5.5%</td><td>5.74%</td><td>20.4%</td><td>20.89%</td><td>20.0%</td><td>14.3%</td></tr><tr><td>an isolated photon p² >10 GeV</td><td>3.4%</td><td>1.56%</td><td>14.8%</td><td>14.3%</td><td>11.7%</td><td>6.2%</td></tr><tr><td>p<40 GeV</td><td>1.1%</td><td>0.3%</td><td>7.9%</td><td>9.0%</td><td>8.4%</td><td>4.8%</td></tr><tr><td>Pr(j1)>300GeV (veto additional jets)</td><td>0.26%</td><td>0.044%</td><td>1.9%</td><td>2.2%</td><td>2.1%</td><td>1.32%</td></tr><tr><td>Emiss > 300 GeV</td><td>0.15%</td><td>0.004%</td><td>1.5%</td><td>1.8%</td><td>1.87%</td><td>1.28%</td></tr></table></body></html>

# C Statistical significance at the LHC

TABLE II: The cross sections of the signal and backgrounds at the 14 TeV LHC with all the cuts. The statistical significance with $\mathrm { 3 0 0 ~ f b ^ { - 1 } }$ and $\mathrm { 5 0 0 ~ f b ^ { - 1 } }$ are also shown. The signal is displayed for the four benchmark points listed in Table I.

<html><body><table><tr><td></td><td></td><td>Wγj (fb)Z(τt)+j (fb)</td><td>Signal (fb)</td><td></td><td>S/B|S/√B (300fb-1) S/√B (500fb-1)</td><td></td></tr><tr><td>(130,150)</td><td>1.14</td><td>0.03</td><td>0.04</td><td>0.03</td><td>0.58</td><td>0.75</td></tr><tr><td>(135,150)</td><td>1.14</td><td>0.03</td><td>0.10</td><td>0.09</td><td>1.66</td><td>2.15</td></tr><tr><td>(140,150)</td><td>1.14</td><td>0.03</td><td>0.22</td><td>0.19</td><td>3.54</td><td>4.57</td></tr><tr><td>(145,150)</td><td>1.14</td><td>0.03</td><td>0.26</td><td>0.22</td><td>4.16</td><td>5.38</td></tr></table></body></html>

Finally, in Table II we show the cross sections and the statistical significance after all cuts. From this table we see that with all the cuts the signal with a small mass splitting has a good S/B and could be probed at the future LHC. Since the cut effciency of the four benchmark points does not vary greatly, the results largely depend on the production rate of the signal. In other words, the decay branching ratio $\tilde { \chi } _ { 2 } ^ { 0 }  \gamma \tilde { \chi } _ { 1 } ^ { 0 }$ determines the observability. It is clearly shown that the benchmark point with the smallst mass splitting gives the best result， whose statistical significance can reach $4 \sigma$ for 300 $f b ^ { - 1 }$ and $5 \sigma$ for 500 $f b ^ { - 1 }$ . When the mass splitting is enlarged to 15 GeV, the sensitivity can still reach $2 \sigma$ for 500 $f b ^ { - 1 }$ ：

# III. PROBING COMPRESSED BINO/WINO IN DARK MATTER DETECTION

As a complementary search for the electroweak gauginos,we also investigate the sensitivity of dark matter direct detection experiments to the compressed bino/wino. Here we focus on the bino LSP and wino NLSP case. In order to account for the dark matter relic density, we scan the parameter space in the following ranges:

$$
1 0 0 ~ { \mathrm { G e V } } < \mathrm { M } _ { 1 } < 3 0 0 ~ { \mathrm { G e V } } , ~ 1 0 0 ~ { \mathrm { G e V } } < \mathrm { M } _ { 2 } < 3 0 0 ~ { \mathrm { G e V } } , ~ 3 < \tan \beta < 5 0
$$

Other SUSY mass parameters except the stop sector are fix at 2 TeV ( $\mu$ is fixed at 1 TeV). The parameters in the stop sector are scanned in the following ranges

$$
7 0 0 ~ \mathrm { G e V } < ( M _ { { \tilde { Q } } _ { 3 } } , M _ { { \tilde { t } } _ { R } } ) < 2 ~ \mathrm { T e V } , \ : \ : \ : - 3 ~ \mathrm { T e V } < A _ { t } < 3 ~ \mathrm { T e V }
$$

where we choose the lower bound by considering the direct stop search limit. In our scan we consider the following constraints:

(1） The SM-like Higgs mass in the range of 123-127 GeV. We use FeynHiggs2.8.9 [27] to calculate the Higgs mass and impose the experimental constraints from LEP, Tevatron and LHC by HiggsBounds-3.8.0 [28].   
(2） Various $B$ -physics constraints at $2 \sigma$ level. We implement the constraints by using the package Superlso v3.3 [29], including $B  X _ { s } \gamma$ and the latest measurements of $B _ { s } \to \mu ^ { + } \mu ^ { - }$ ， $B _ { d } \to X _ { s } \mu ^ { + } \mu ^ { - }$ and $B ^ { + } \to \tau ^ { + } \nu$ ：   
(3） The constraints from the precision electroweak observables such as $\rho _ { \ell }$ ， $\sin ^ { 2 } \theta _ { \mathrm { e f f } } ^ { \ell }$ ， $m _ { W }$ （20 and $R _ { b }$ [30] at $2 \sigma$ level.   
(4） The thermal relic density of the lightest neutralino (as the dark matter candidate) is within the $2 \sigma$ range of the Planck value [31]. We also consider the direct dark matter search limits from LUX [32]. We use the code MicrOmega v2.4 [33] to calculate the relic abundance and DM-nucleon scattering.

![](images/7647cb9df04a3349fa80dc457ddb601dbc590da35e34d054385d96b6d98df493.jpg)  
FIG. 4: The scatter plots of the samples allowed by the $2 \sigma$ dark matter relic density and various collder constraints listed in the context.The left panel shows the plots in the plane of mxo versus $m _ { \tilde { \chi } _ { 2 } ^ { 0 } }$ while the right panel shows the neutralino dark matter-nucleon scattering cross section versus the neutralino mass.

In Fig.4 we show the scatter plots of the samples allowed by the $2 \sigma$ dark matter relic density and various collider constraints (1)-(4) listed above. From Fig.4, it can be seen that, for our region with $\tilde { \chi } _ { 2 } ^ { 0 } \lesssim 1 5 0$ GeV, the dark matter relic density can be guaranteed by the co-annihilation among $\tilde { \chi } _ { 2 } ^ { 0 }$ ， $\tilde { \chi } _ { 1 } ^ { \pm }$ and $\tilde { \chi } _ { 1 } ^ { 0 }$ due to their small mass spliting $\Delta M \sim 5 - 1 5$ （20 GeV. However, such a region could not be covered by the current LUX and future XENON1T(2017) experiments because of the suppression of the coupling. So, our proposed method can be served as a complementary way to probe this compressed bino/wino scenario at the LHC.

Finally, we would like to stress that in our analysis we worked in the framework of MSSM, in which the neutralino LSP (dark matter candidate) is bino-like ( $M _ { 1 } < M _ { 2 } < \mu$ ). In some extensions of the MSSM, for example, the popular next-to-minimal supersymmetric model, the property of the neutralino LSP (dark matter candidate) may be quite different because it tends to be singlino-like and rather light [34].Then the bino-wino co-annihilation is no longer the mechanism to give the correct dark matter relic abundance and also the signature of the production $p p  j \tilde { \chi } _ { 2 } ^ { 0 } \tilde { \chi } _ { 1 } ^ { \pm }$ is different from what we studied. Also, some recent studies [35] discussed the phenomenology of electroweak gauginos in other miscellneous scenarios.

# IV. CONCLUSION

In this work we proposed to use the signal $\ell + j + \gamma + \not { E } _ { T } ^ { m \imath s s }$ to probe the compressed bino/wino scenario at the LHC. From detailed Monte Carlo simulations we find that the 14 TeV LHC with luminosity of $5 0 0 ~ \mathrm { f b ^ { - 1 } }$ can probe the wino NLSP up to 150 GeV for a wino-bino mass splitting 5-15 GeV. Such a method is also applicable to the compressed bino/higgsino scenario. We investigated the dark matter detection sensitivities for this scenario and found that the planned XENON-1T(2017) cannot fully cover the parameter space with wino below 150 GeV allowed by relic density and the LUX limits.

# Acknowledgement

This work was supported by the Korea Ministry of Education， Science and Technology (MEST) under the Young Scientist Training Program at the Asia Pacific Center for Theoretical Physics (APCTP),by the Australian Research Council, by the National Natural Science Foundation of China (NNSFC) under grants Nos. 11222548,11305049, 11405047, 11275245, 10821504，1135003 and by the Specialized Research Fund for the Doctoral Program of Higher Education under Grant No.20134104120002.

J. T. Ruderman, JHEP 1111, 012 (2011) [arXiv:1105.5135 [hep-ph]; M. Drees,M. Hanussek and J. S. Kim,Phys. Rev.D 86,035024 (2012) [arXiv:1201.5714 [hep-ph].   
[5] ATLAS Collaboration, ATLAS-CONF-2013-053.   
[6] G. Aad et al. [ATLAS Collaboration], Phys. Lett. B 716,1 (2012).   
[7] S. Chatrchyan et al.[CMS Collaboration], Phys. Lett.B 716, 30 (2012).   
[8] See recent examples after 125 GeV Higgs, J. S. Kim and T. S. Ray, arXiv:1405.3700 [hep-ph]; G. Barenboim，et al.， Phys. Rev.D 90 (2014) 035020 [arXiv:1407.1218 [hep-phl]； T.Han, S. Padhi and S. Su,Phys.Rev. D 88 (2013) 115010 [arXiv:1309.5966 [hep-phl]； T. Han, Z. Liu and S. Su, JHEP 1408 (2014) 093 [arXiv:1406.1181 [hep-ph]]; M. Berggren， et al., arXiv:1309.7342 [hep-ph]; U. Ellwanger and A. M. Teixeira,arXiv:1406.7221 [hep-ph]; U. Ellwanger，JHEP 1311,108 (2013) [arXiv:1309.1665 [hep-phl]； K. Hikasa et al.， JHEP 1407, 065 (2014) [arXiv:1403.5731 [hep-phl]; C. Cheung, L. J. Hall, D. Pinner and J. T. Ruderman, JHEP 1305,100 (2013) [arXiv:1211.4873 [hep-ph].   
[9]G.Aad et al. [ATLAS Collaboration], JHEP 1404,169 (2014) [arXiv:1402.7029 [hep-ex].   
[10] V. Khachatryan et al. [CMS Collaboration], arXiv:1405.7570 [hep-ex].   
[11] G.Brooijmans et al.，arXiv:1405.1617 [hep-ph]; C. Han， et al.， JHEP 1402 (2014) 049 [arXiv:1310.4274 [hep-ph]； P. Schwaller and J. Zurita，JHEP 1403 (2014）060 [arXiv:1312.7350 [hep-phl]；G. F. Giudice et al.， Phys.Rev.D 81，115011 (2010) [arXiv:1004.4902 [hep-ph]].   
[12] S. Gori, S. Jung and L. T. Wang, JHEP 1310 (2013) 191 [arXiv:1307.5952 [hep-ph]; Z. Han, et al.,Phys.Rev.D89 (2014) 075007 arXiv:1401.1235 [hep-phl].   
[13] H. Baer, A. Mustafayev and X. Tata, Phys. Rev. D 89 (2014) 055007 [arXiv:1401.1162 [hepph]].   
[14] A. Anandakrishnan，L. M. Carpenter and S. Raby， Phys. Rev. D 90， 055004 (2014) [arXiv:1407.1833 [hep-ph].   
[15] T.Liu,L. Wang and J. M. Yang, Phys. Lett. B 726, 228 (2013) [arXiv:1301.5479 [hep-ph].   
[16] J. Bramante, et al., arXiv:1408.6530 [hep-ph].   
[17] N.Arkani-Hamed，A. Delgado and G. F. Giudice，Nucl. Phys.B 741 (2006） 108 [hep-ph/0601041]； C.Cheung，et al.，JHEP 1305 （2013）100 [arXiv:1211.4873 [hep-ph]; T. Han, Z. Liu and A. Natarajan, JHEP 1311 (2013) 008 [arXiv:1303.3040 [hep-ph]]; F. Wang, W. Wang and J. M. Yang, arXiv:1310.1750 [hep-ph]; P. Huang and C. E. M. Wagner, Phys. Rev. D 90 (2014) 015018 [arXiv:1404.0392 [hep-phl]; J. Edsjo and P. Gondolo, Phys. Rev. D 56(1997) 1879 [hep-ph/9704361]; K. Griest and D. Seckel, Phys. Rev. D 43 (1991) 3191.   
[18] H. Baer et al., JHEP 0512 (2005) 011 [hep-ph/0511034].   
[19] S. Ambrosanio and B. Mele, Phys. Rev. D 55 (1997) 1399 [Erratum-ibid. D 56 (1997) 3157] [hep-ph/9609212]； M. A. Diaz,B. Panes and P. Urrejola,Eur. Phys. J. C 67 (2010）181 [arXiv:0910.1554 [hep-ph].   
[20] A.Djouadi， M. M. Muhlleitner and M. Spira， Acta Phys.Polon.B 38 (2007） 635 [hep-ph/0609292].   
[21] G. Aad et al. [ATLAS Collaboration], Phys. Rev. D 87 (2013)11, 112003 [arXiv:1302.1283 [hep-ex]].   
[22] J. Alwall et al., JHEP 1106,128 (2011).   
[23] T. Sjostrand, S. Mrenna and P. Z. Skands, JHEP 0605, 026 (2006).   
[24] S. Ovyn, X. Rouby and V. Lemaitre, arXiv:0903.2225 [hep-ph].   
[25] M. Cacciari, G. P. Salam and G. Soyez, JHEP 0804, 063 (2008).   
[26] F. Caravaglios, et al.,， Nucl. Phys. B 539, 215 (1999).   
[27] M. Frank et al., JHEP 0702, 047 (2007); G. Degrassi et al., Eur.Phys. J. C 28,133 (2003); S. Heinemeyer，W. Hollik and G. Weiglein, Comput. Phys. Commun.124, 76 (2000); Eur. Phys. J. C9,343 (1999).   
[28] P. Bechtle et al., Comput. Phys. Commun. 182, 2605 (2011); Comput. Phys. Commun.181, 138 (2010).   
[29] F.Mahmoudi, Comput. Phys. Commun.180,1579 (2009)；Comput.Phys. Commun. 178, 745 (2008).   
[30] J. Cao and J. M. Yang, JHEP 0812, 006 (2008).   
[31] P. A. R. Ade et al. [Planck Collaboration], arXiv:1303.5076 [astro-ph.CO].   
[32] D.S.Akerib et al. [LUX Collaboration],Phys.Rev. Lett.112 (2014) 091303 [arXiv:1310.8214 [astro-ph.CO].   
[33] G. Belanger et al., Comput. Phys. Commun. 182, 842 (2011).   
[34] See, e.g., J. Cao et al., JHEP 1405,056 (2014) [arXiv:1311.0678 [hep-ph]]; JHEP 1203, 086 (2012）[arXiv:1202.5821 [hep-ph].   
[35] H. Baer et al.， JHEP 1406,172 (2014)； A. Mustafayev and X. Tata, Indian J. Phys. 88,

991 (2014); S. P. Martin, Phys. Rev. D 89, 035011 (2014)； A. Arbey, M. Battaglia and F. Mahmoudi, Phys.Rev. D 89, 077701 (2014)； Q. j. Xu et al., arXiv:1310.5414 [hep-ph]; T. Cheng, J. Li and T. Li, arXiv:1407.0888 [hep-ph]; L. Calibbi et al., arXiv:1405.3884 [hepph].