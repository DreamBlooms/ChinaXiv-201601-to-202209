# Theoretical Analysis of Catalytic-sRNA-Mediated Gene Silencing

Yue Hao†, Liufang Xu† and Hualin Shi\*

InstituteofTheoretical Physics,Chinese Academy of Sciences,Beijing 1Oo190,China

Received 29April 2010; receivedinrevisedform 17November 2010; accepted1December2010 Availableonline 9 December 2010

Keywords: small RNA; noise; RNA trap

Small regulatory RNA (sRNA) that acts by an antisense mechanism is critical for gene regulation at the posttranscriptional level. Recently,an Hfqdependent sRNA named MicM,which is related to the regulation of outer membrane protein,was verified as a novel antisense sRNA due to its catalytic mode of regulation.Here we propose a simple kinetic model for the enzyme-like regulation mode of sRNA and study in detail the noise properties of the target gene under various recycling rates of the regulator. We predict that the recycling rate of sRNA and other relative parameters have significant influence on the noise strength of target expression. In comparison with the stoichiometric regulatory mode,a lesser fluctuation of target expression was observed near the threshold at which the transcription rates of both sRNA and target mRNA equal each other.We also found that the new mode is better in terms of rapid response to external signals. However, it needs more time to achieve target recovery if the stimulating signal disappears.Additionally, the obtained time evolution results of the MicM-ybfM interaction system based on our model are consistent with previous experimental results, serving as experimental evidence to back up our theoretical analysis.

$\circleddash$ 2010 Elsevier Ltd.All rights reserved

# Introduction

Small regulatory RNA (sRNA) is a type of noncoding RNA with typical length varying from $\sim 5 0$ nucleotides to several hundred nucleotides.As a crucial regulator,itis involved in many biological functions_such as stress response,1 quorum sensing,5-7and soon.Approximately 80 sRNAs have been verified in Escherichia coli,most of which use an antisense mechanism by base-pairing with other RNAs.1 These sRNAs are often induced under stress conditions and respond rapidly to environmental threat.9,10 They are usually retained at a very low copy number，so stochastic effects can become prominent.

Numerous studies sought to understand the dynamic features of gene expression controlled by sRNAs that lead to coupled degradation.11-14 Comparison of protein and sRNA regulators based on simulations drew the conclusion that regulation by sRNA is advantageous when a rapid response to an external signal is required.This is in consistent with experimental data.12,14 Noise analysis indicated that the noncatalytic mode of gene regulation by sRNA has a unique feature in noise resistance.12,14"

Different from the ordinary mechanism of basepairing sRNA regulators that act stoichiometrically on their targets,1 recent studies found that，in Salmonella,ansRNAnamedMicMleadsto selective degradation of the sRNA-mRNA duplex.15-17 Its binding to chb mRNA leads to coupled degradation of both sRNA and mRNA. For another target-ybfM mRNA, the sRNA part of the RNA duplex remained undestroyed. However, the mRNA part could not escape the fate of degradation. Experimental results indicated that MicM-mediated regulation requires Hfq protein to enhance RNA duplex formation17-19 and implied that one molecule of MicM can participate in the degradation of several molecules of ybfM mRNA.15

The catalytic characteristic of sRNA enriched our understanding of gene regulation: It isa fusion of the traditional mechanism of the sRNA regulator and enzyme catalysis.It is natural to ask whether this new mode of posttranscriptional gene regulation mediated by sRNAs is well suited for biological tasks and whether this mode of gene silencing is efficient in suppressing fluctuations in its target genes.

Here we_ propose a simple kinetic model for catalytic-sRNA-mediated gene silencing to investigate the noise properties of a target gene and the time evolution of the interaction system by Monte Carlo simulations.Some unusual features of this regulatory mode are found and compared with ordinary antisense mechanism.Catalytic sRNA is promising as a more effective regulator owing to its fast response ability and low recovery capability of target expression.

# Results

# Abasic model forcatalytic-sRNA-mediated gene silencing

Our theoretical study of catalytic-sRNA-mediated repression starts with a mass action model (Fig.1). The minimal system consists of a single species of small RNA(s)，a single species of mRNA target $( m ) _ { \cdot }$ ，the duplex $( s _ { - } m )$ formed by the two species of RNA,and the protein product $( p )$ of the mRNA.As a simplified model for catalytic sRNA，an sRNA can bind the $5 ^ { \prime }$ untranslated region of an mRNA at its ribosome binding site to block translation initiation. In this model,we assume the following:

(1) Small RNA and its target mRNA are coded by independent genes using different promoters for their transcription. They are synthesized at rates $\alpha _ { s }$ and $\mathbf { \alpha } \propto _ { m } ,$ respectively.   
(2) Thebinding ofsRNAtomRNAisirreversible and fast with the binding rate $k ,$ while an sRNAmRNA duplex is degraded with the linear rate $\beta _ { s m }$ ． Aproportion of sRNA is successfully recycled as provider of sRNA regulators from the degraded duplex; the recycling ratio δ ranges from 0 to 1.   
(3)Proteins are translated at a linear rate $k _ { p }$ off mRNA molecules,and each mRNA molecule produces on average of $n$ protein molecules during its lifetime $\begin{array} { r } { \frac { 1 } { \beta _ { m } } , } \end{array}$ 50 $k _ { p } = n \bar { \beta } _ { m }$ ，   
(4)All molecules of sRNAs，mRNAs,sRNAmRNA duplexes，and proteins,are subject to degradation with linear rates $\beta _ { s } , \ \beta _ { m } , \ \beta _ { s m }$ and $\beta _ { p } ,$ respectively.

![](images/05f8d38c8e42eb506974adff510870d2eb96c8ceea039da3f1d0620c855f847f.jpg)  
Fig.1. Schematic diagram of catalytic-sRNA-mediated gene regulation.

The process,as shown schematically in Fig. 1, can be quantitatively described with a system of differential equations:

![](images/6b611c89cb757582ef6c7e4b49317d89abbee053887817ba2079985a47e1892f.jpg)  
Fig.2.Steady states with different recycling ratios. (a-c) Steady-state solutionsofmRNA(left ordinate),sRNA,and sRNA-mRNA (right ordinate) with $\delta = 0 , ~ 0 . 5 ,$ and 1, respectively.(d) The levels of target mRNA in steady state with different recycling ratios of sRNA.The lines are obtained from steady-state solutions (Eqs.(3) and (4)). The symbols are obtained from Monte Carlo simulations, where ${ { 1 0 } ^ { 6 } }$ steps of simulation were used for each recycling ratio S.Parameters are set as $\alpha _ { s } = 1 \ \mathrm { \ n M } \ \mathrm { \ m i n } ^ { - 1 }$ and $k { = } 0 . 1$ $( \mathrm { n M \ m i n } ) ^ { - 1 }$ . The other parameters are estimated from experiments.15 We set $\mathsf { \xi } \mathsf { \xi } _ { \mathsf { B } _ { s } = \mathsf { B } _ { m } = 0 . 0 2 \ \mathrm { \ m i n } ^ { - 1 } }$ and $\beta _ { s m } = 0 . 1$ $( \mathrm { n M ~ m i n } ) ^ { - 1 }$ . The half-lives of both sRNA and mRNA are about $2 7 \ \mathrm { m i n } ,$ and the half-life of the RNA duplex is about 4 min.15

$$
\begin{array} { c } { \displaystyle \frac { \mathrm { d } s } { \mathrm { d } t } = \alpha _ { s } - \beta _ { s } s - k s m + \delta \beta _ { s m } ( s . m ) } \\ { \displaystyle \frac { \mathrm { d } m } { \mathrm { d } t } = \alpha _ { m } - \beta _ { m } m - k s m } \\ { \displaystyle \frac { \mathrm { d } ( s . m ) } { \mathrm { d } t } = k s m - \beta _ { s m } ( s . m ) - \beta _ { \mathrm { g d } } ( s . m ) } \\ { \displaystyle \frac { \mathrm { d } p } { \mathrm { d } t } = k _ { p } m - \beta _ { p } p } \end{array}
$$

Here,we assumed that the other proteins involved (Hfq,degradosome,etc.)are present at levels that are sufficient not to limit reaction rates. The degradation of all molecules is caused by direct degradation and growth dilution. Direct degradation of the sRNA-mRNA duplex will save a fraction of sRNAs,but growth dilution will not. In order to show this difference,we explicitly write the growth dilution term for the sRNA-mRNA duplex，where $\beta _ { \mathrm { g d } }$ is related to the growth rate. Usually,direct degradation of the sRNA-mRNA duplex is much faster than growth dilution,and we neglect it in the ensuing discussion. The steady-state solutions for $s$ and $m$ canbededuced from the following equations:

$$
\begin{array} { l } { { \alpha _ { s } - \beta _ { s } s - k ( 1 - \delta ) s m = 0 } } \\ { { \alpha _ { m } - \beta _ { m } m - k s m = 0 } } \end{array}
$$

For mRNA，the rate $k$ here is the same as the coupled degradation rate in the previous stoichiometric mode12 (Fig. 2a); however, for sRNA, part of the sRNAs (δksm） can be recycled from the degraded RNA duplex.Thus,the solutions under reaction equilibrium conditions are (for $\delta { \in } [ 0 , 1 )$ ）

$$
\begin{array} { r l } & { n ^ { \mu } = \frac { 1 } { 2 \mathrm { R e } } [ ( 2 \sigma _ { - } - \frac { 1 } { 1 - \tilde { n } } \tilde { \sigma } _ { - } - \frac { \lambda } { 1 - \tilde { \sigma } _ { - } } )  } \\ &  \qquad + \sqrt { ( \zeta _ { - } - \frac { 1 } { 1 - \tilde { \sigma } _ { - } } \gamma _ { - } - \frac { \lambda } { 1 - \tilde { \sigma } _ { - } } ) ^ { 2 } + 4 \sigma _ { \pi } \frac { \lambda } { 1 - \tilde { \sigma } _ { - } } \Bigg ] } \\ & { s ^ { \mu } = \frac { 1 } { 2 \mathrm { R e } } [ ( 4 \sigma - ( 1 - \tilde { \sigma } _ { - } ) q _ { \alpha } - \lambda ) ^ { 2 } + 4 q _ { \alpha } \lambda ] } \\ & { \qquad + \sqrt { ( \zeta _ { - } - ( 1 - \tilde { \sigma } _ { ) / \alpha } - \tilde { \sigma } _ { - } ) ^ { 2 } + 4 q _ { \alpha } \lambda } ] } \\ & { s _ { \mu } \mathrm { m } ^ { \mu } = \frac { Q _ { \alpha } - \tilde { \sigma } _ { - } \mu \mathrm { m } ^ { \mu } } { \mathrm { R e } } } \\ & { \qquad \quad \mathrm { ~ s } ^ { \mu } - \frac { \tilde { \sigma } _ { - } \mu } { \mathrm { R e } } } \\ & { \qquad p ^ { s ^ { \mu } - \frac { \lambda } { \tilde { \sigma } _ { - } } \mathrm { R e } } , } \end{array}
$$

where $\begin{array} { r } { \mathsf { \lambda } \lambda = \frac { \beta _ { m } \beta _ { s } } { k } } \end{array}$ is the leakage rate of mRNA expression12 (Fig.2a).The efect of the leakage expression rate of mRNA can be neglected,since the binding reaction is fast due to the participation of Hfq.In this study, $k$ is set as $0 . 1 ~ ( \mathrm { n \dot { M } ~ m i n } ) ^ { - 1 }$ to represent a fast combination between sRNA and mRNA.The catalytic mechanism maintains the characteristic of a "threshold-linear response." 12,20

The threshold here,however,is characterized by $\frac { 1 } { 1 . - \delta } \alpha _ { s } ,$ not by $\alpha _ { s }$ It rises as S increases. Above the threshold,the mRNA level will start to increase linearly with this production rate $\alpha _ { m }$ .It is obvious thatat a fixed value of $\alpha _ { s } ,$ a higher recycling ratio of sRNA leads to a higher level of gene silencing (Fig. 2).

The sRNA of the degraded RNA duplex will be $1 0 0 \%$ recycled if $\delta = 1$ ,and the recycled sRNA will exertitseffectagain onothermRNAmolecules.This process is similar to a protein regulator taking part in posttranscriptional regulation,which results in the degradation of targetmRNAs.Taking limit $\delta \to 1$ in Eq. (3) or deriving directly,we have:

$$
\begin{array} { c } { \displaystyle { s ^ { * } = \frac { \alpha _ { s } } { \beta _ { s } } } } \\ { \displaystyle { m ^ { * } = \frac { m _ { 0 } } { 1 + \frac { k } { \beta _ { m } } s ^ { * } } = \frac { m _ { 0 } } { 1 + \frac { \alpha _ { s } } { \lambda } } } } \end{array}
$$

where $\begin{array} { r } { m _ { 0 } = \frac { \alpha _ { m } } { \beta _ { m } } } \\ { . } \end{array}$ denotes the stationary level of mRNA in the absence of the regulator. Thus, the level of sRNA molecules remains constant even when $\alpha _ { m }$ isvaried,whereas the number of sRNAmRNA duplex linearly increases with $\alpha _ { m }$ (Fig. 2c). With parameters estimated based on experiments, mRNA is suppressed at a low level even when $\mathbf { \alpha } \propto \mathbf { \alpha } \mathbf { \alpha } _ { s }$ (Fig. 2d).It is interesting that the steady state of this modeis similar to that of protein-based transcriptional inhibition,which is characterized by $m ^ { * } = \frac { { m _ { 0 } } } { 1 + { { \left( { \frac { r } { a } } \right) } ^ { n } } }$ .Here $r$ is the concentration of the transcription factor, $a$ isrelated to binding affinity, and $n$ isthe Hill coefficient.21,22It should be emphasized that，in both cases,the efficiency of regulators is closely related not only to the concentration of the regulator but also to the binding rate with its target. Catalytic sRNA interpolates between the conventional protein regulator and the sRNA regulator.

# Description of noise strength

It is well known that gene regulation is intrinsicallynoisy due to the stochastic nature of underlyingbiochemalaios5Ithslewe define intrinsic noise as fluctuations in mRNA number and output protein number at a fixed input of $\alpha _ { m } , \alpha _ { s } ,$ and so on.

The master equation for the distribution of the mRNA,sRNA, sRNA-mRNA duplex,and protein copies $( m , s , c ,$ and $p ,$ ：respectively)in this model is given by:

$$
\begin{array} { r l } { \frac { \mathrm { d } } { \mathrm { d } t } P ( m , s , p , c ) = \bigg [ \mathfrak { z } _ { m } \big ( h _ { m } ^ { - } - 1 \big ) + \mathsf { \mathsf { \mathsf { B } } } _ { m } \big ( h _ { m } ^ { + } - 1 \big ) m } & { } \\ { + \mathfrak { z } _ { s } \big ( h _ { s } ^ { - } - 1 \big ) + \mathsf { \mathsf { B } } _ { s } \big ( h _ { s } ^ { + } - 1 \big ) s } & { } \\ { + \mathsf { k } \big ( h _ { m } ^ { + } h _ { s } ^ { + } h _ { c } ^ { - } - 1 \big ) m s } & { } \\ { + \mathsf { \mathsf { s } } \mathsf { \mathsf { B } } _ { s m } \big ( h _ { s } ^ { - } h _ { c } ^ { + } - 1 \big ) c + \mathsf { \mathsf { B } } _ { s m } \big ( h _ { c } ^ { + } - 1 \big ) c } & { } \\ { + \mathsf { \lambda } _ { \mathrm { { P } } } \mathbf { m } \Big ( \mathsf { h } _ { \mathrm { { P } } } ^ { - } - 1 \Big ) } & { } \\ { + \mathsf { \mathsf { B } } _ { \mathrm { { P } } } \Big ( \mathsf { h } _ { \mathrm { { P } } } ^ { + } - 1 \Big ) \mathsf { P } \Big ] \mathsf { P } ( \mathfrak { m } , \mathfrak { s } , \mathrm { { P } } , \mathsf { c } ) } & { \quad \mathsf { ( f o r ~ a l l ~ \mathfrak { s } ~ , ~ c . ~ ) } . } \end{array}
$$

where $h ^ { + }$ and $h ^ { - }$ are,respectively, the lowering and raising operators defined through $h _ { x } ^ { + } f ( x ) = f ( x + 1 ) ,$ $h _ { x } ^ { - } f ( x ) { = } f ( { \dot { x } } - 1 ) .$ and $h _ { x } ^ { - } f ( 0 ) = 0$ for any function $f ( x )$ All time derivatives are set to zero here,as we focus on the steady-state properties of gene expression.

To describe noise strength,we use a sensitive measure pf noise,the Fano factor,which is defined as $\begin{array} { r } { F _ { x } = \frac { \sigma _ { x } ^ { 2 } } { \mu _ { x } } } \end{array}$ for stochastic variable $x ,$ where $\mathbf { \sigma } _ { \mathbf { { \mathcal { X } } } } ^ { 2 }$ is the variance and $\mu _ { x }$ is the mean. For the Poisson process, the factor equals 1.

# Dependence of noise strength on recycling ratio

It has been previously found that sRNA-based regulation is more efficient than transcription-factorbased regulation both in responding rapidly to signals and in filtering out noise from the environment.12,20 Here we focus on therecycling rate of the sRNA regulator in the catalytic mechanismand quantitativelydescribe its influence on the noise strength of target expression.

It is difficult to directly solve the master equation describing the intrinsic stochastic behavior of smallRNA-mediated regulation, so we use the well-known stochastic simulation algorithm (SSA) Gillespie direct method26 to generate the stochastic trajectory of the regulation process and then analyze the characteristic of noise (see details in Materials andMethods).

The threshold-linear mode of gene expression regulated by ordinary antisense sRNA has been carefully analyzed.It has been concluded that the fluctuation of target gene expression depends largely on the ratio of the transcription rate of the target mRNA $\left( \alpha _ { m } \right)$ to the transcription rate of the sRNA regulator (αs).12,20,27 A similar behavior is now also predicted for gene expression controlled by catalytic sRNA. Based on the master equation (Eq. (5)),the average number of mRNA or the first moment of $m$ was drawn in Fig.2d.The result shows that the average numbers of species provided by stochastic simulationsareconsistentwiththe solutions of the deterministic equation.

We present the relationship between the Fano factors of mRNA and the production rate $\alpha _ { m }$ under different recycling ratios in Fig. 3a.It shows that the inflection points of these curves move rightward along the $\alpha _ { m }$ axis.The peak position changes as 1-αsand the peak value becomes larger as 8 increases.Note that in the regime where the transcription rates of mRNA and sRNA are comparable, the value of the Fano factor decreases as δ increases.This result may be important in biological function,as is mentioned in the literature (that most actual biological parameters are near this point when sRNA silences its target gene). In other words, the catalytic-sRNA-mediated regulation mechanism tends to attenuate noise more than ordinary sRNA regulation when gene silencing happens. Due to the large stochastic fluctuation in the cell, it is important to ensure that the silencing function is reliable.

Protein noise has a similar behavior,except for αm>1-αs (Fig.3b),where the Fano factor of protein approaches $\begin{array} { r } { 1 + \frac { b } { 1 + \frac { \beta _ { p } } { \beta _ { m } } } } \end{array}$ (equal to about 2 here) instead of 1.The same result can be deduced from the master equation in the following manner: Multiplying the master equation by $m , m ^ { 2 } , s ,$ and $s ^ { 2 }$ respectively,and summing over $m , s , p ,$ and $\mathbf { \Psi } _ { c , \mathbf { \Psi } }$ with some approximations，we can derive that for $\alpha _ { m } \ll \frac { 1 } { 1 - \delta } \alpha _ { s }$ and $\alpha _ { m } { \gg } \frac { 1 } { 1 - \delta } \alpha _ { s } , F _ { \mathrm { m } }$ indeed approaches 1. It was found that $F _ { p } \approx 1$ for $\alpha _ { m } \ll \frac { 1 } { 1 - \delta } \alpha _ { s }$ and that $\begin{array} { r } { F _ { p } \approx 1 + \frac { b } { 1 + \frac { \beta _ { p } } { \beta _ { m } } } } \end{array}$ $\alpha _ { m } \gg \frac { 1 } { 1 - \delta } \alpha _ { s } ,$ $\begin{array} { r } { \dot { b } = \frac { k _ { p } } { \beta _ { m } } } \end{array}$ average number of proteins produced from one transcript (called "burst size"by some authors).20,23 The "burst" of protein in an mRNA translation process causes amplification of noise in gene expression, which has been elucidated in detail.23,27

A previous work on stoichiometric sRNA-mediated gene regulation²7 found that there is bimodality of target mRNA under certain parameters near the threshold，and the high correlation between sRNA and its target mRNA will form an effective potential barrier to shape the bimodal distribution. Wealso found bimodality in this catalytic-sRNA mediated regulationmechanism,which needs to be tested by future experiments (Fig. 4).

![](images/bf6b5c60630585443b365d37d16cb1862916e42f16a07679fd223f8c04b5afae.jpg)  
Fig.3.Fano factors for target mRNA (a) and protein (b)with different recycling ratios. The gray broken line in(a) represents the Poissonian limit $\bar { F _ { \mathrm { m } } } \mathrm { = } \bar { 1 } ,$ .and that in (b) represents the limit $1 + \frac { b } { 1 + \frac { \beta p } { \beta m } }$ 1.βp is set to0.02,and the other parameters are set as in"Fig.2. These results are obtained from ${ 1 0 } ^ { 8 }$ steps of Monte Carlo simulations.

# Comparison between stoichiometric mode and full catalyticmode

We then focus on two limit cases in our model and find out their different behaviors.In our model (Eq. (1)), $\delta = 0$ and $\delta = 1$ correspond to a stoichiometric mode²7 and a fully catalytic mode, respectively.In a real biological system,degradation of the sRNA-mRNA duplex is caused by direct degradation and growth dilution. Direct degradation will save a fraction of sRNAs,but growth dilution will not. Thus, the recycling ratio of sRNAs will never exactly equal1.But direct degradation is usually much faster than growth dilution, and δ is possibly close to 1. Thus,it is still helpful to study the behavior of the system at the limit case of $\delta = \dot { 1 }$

![](images/87c43589e310c35a263fc460dde7705a304977cde89b7729bfbf3bb8193c096e.jpg)  
Fig.4.Bimodal distribution of target mRNA.The parameters are set as: $\alpha _ { s } { = } 1 \ \mathrm { n M } \ \mathrm { m i n } ^ { - 1 }$ $\alpha _ { m } { = } 3 \ \mathrm { n M } \ \mathrm { m i n } ^ { - 1 } .$ $\stackrel { \bullet } { \beta } _ { s } = \beta _ { m } = 0 . 0 2 \ \mathrm { \ m i n } ^ { - 1 } .$ 、 $\beta _ { s m } = 0 . 1$ $( \mathrm { n M \ m i n } ) ^ { - 1 }$ 、 $\lambda = 0 . 0 0 0 1$ nM $\operatorname* { m i n } ^ { - 1 } ,$ and $\delta = 0 . 6$ .The ordinate is scaled by the total number of mRNA molecules.

As $\delta = 0$ ,it becomes the previous model that was studied in detail.27When $\mathbf { \alpha } \propto \mathbf { \alpha } \mathbf { \alpha } _ { s } ,$ almost all mRNA molecules will be targeted by small ${ \mathrm { R N A } } ,$ and only a thimbleful of mRNA,whose amount is not correlative to small RNA fluctuation, leak out. Alternately, when $\mathbf { \alpha } \mathbf { \alpha } \propto \mathbf { \alpha } \mathbf { \alpha } _ { s } ,$ small RNA is used up, and the majority of mRNA is alive for translation. These two situations are close to the Poisson process，which leads the Fano factors'approach to 1 (Fig. 5, black line).

In the case of $\begin{array} { r } { \delta = 1 . } \end{array}$ ,ourresult shows that the Fano factor remains close to 1，although the mRNA production rate $\left( \alpha _ { m } \right)$ changes (Fig. 5). When $\alpha _ { m } < \alpha _ { s } ,$ the result is similar to Levine's model,27 where mRNA molecules are mostly degraded, resulting in its fluctuation being irrelevant to small RNA fluctuation. While $\alpha _ { m } > \alpha _ { s } ,$ over quite a large range，mRNA will be consumed，as sRNA can remain at a constant level. The sRNA here can be recycled likean enzymeafter the degradation of the mRNA-sRNA duplex. According to our simulations, $F _ { \mathrm { m } }$ remains close to below 1 even when $\mathbf { \alpha } \mathbf { \alpha } \gg \mathbf { \alpha } \mathbf { \alpha } _ { s }$

Toobtain a better understanding of full catalytic mode, we will return to deterministic results (Eq. (4) and Fig. 2c).It is obvious that more and more mRNAmoleculeswillbindtosRNAmoleculesand then degradeas $\alpha _ { m }$ increases.However, the level of free sRNA molecules stays the same because the effects of binding to mRNA and recycling from the duplex will cancel out each other. Small RNA pairing with its target mRNA produces a double effect:enhanced degradation of mRNA and protection from direct degradation (Eq. (4)).The latter effect enables sRNA to always satisfy theneed for silencing byadjusting the level of the mRNA-sRNA duplex.That is,when $\delta = 1$ ，although free sRNAs stayat the samelevel, the total sRNA concentration does increase with $\mathbf { \alpha } \propto _ { m } ,$ andthis is why mRNAs are always repressed by sRNA and mRNA noise remainsat a quite lowlevel.

# Influence of other parameters on noise

We analyzed the influence of the sRNA recycling rate on noise and found that a strong fluctuation of gene expression can be produced by a large δ.With fixed transcription rates $\langle \alpha _ { s }$ and $ { \alpha } _ { m } )$ ，as more regulators are recycled，more targets will be influenced. It must be noted that sRNA recycling onlyhappens with the degradation of the sRNAmRNA duplex. Thus, the rate parameters of sRNAmRNA duplex formation $( k )$ and degradation $( \beta _ { s m } )$ should be considered as well. Here we give a quantitative view of how these parametersaffect the noise of both mRNA and its protein product.

Figure 6a shows that noise is enhanced when the degradation of the duplex isenhanced.For certain recyclingratios,a fast degradation will speed sRNA recycling without changing the inflexion of the Fano factor curve,which is only decided by the recycling ratio.An upper limit of $\beta _ { s m } ,$ above which sRNA recyclingrates will not increase further, is expected. When $\beta _ { s m } \simeq 0$ ，the model reduces to an ordinary sRNA-mediated model.27

Figure 6b shows how the binding rate $k$ influences the fluctuation of output protein. We calculate the Fano factor of protein at a different binding rate $k$ for $\delta = 0 . 5$ .Over a range of $\alpha _ { m } < \alpha _ { s } ,$ the Fano factor of the output protein decreases with increasing $k$ There are two limits of $F _ { p } ,$ as the binding rate $( \bar { k } )$ is varied over a large range $( \mathrm { f r o m ~ } 0 . 0 0 0 1 \$ to 10 $( \mathrm { { n M } \ m i n } ) ^ { - 1 }$ ） When the process of binding is very fast, the few proteins produced for mRNA are fully repressed, and the noise curve approaches the Poissonian limit. For $k \simeq 0 .$ ，mRNAis freelytranslated,andtheFano factor approaches the limit of $1 + b ( \approx 2 )$ .In the silencing region, sRNA-based regulation can filter noise in the mRNA.12 A larger binding rate $k$ means a more efficient sRNA,which leads to a smaller fluctuation of mRNA in the silencing region.

![](images/4d0efcf5a8317d98502b249f22d671456f64005f14f6955128eed5b92efc9c77.jpg)  
Fig.5.Fano factors of mRNA for stoichiometric mode (black continuous line) and catalytic mode (gray continuous line).The light-gray broken line represents the Poissonian limit $F _ { \mathrm { m } } { = } 1$ ：

![](images/d220e60801b2040aad820624b254affa92295b6301a73d5009a7c055c3aace47.jpg)  
Fig.6.Influence of $\beta _ { s m }$ and $k$ on noise at a fixed recycling ratio $\delta { = } 0 . 5$ (a) $F _ { \mathrm { m } }$ isaffectedby the degradation rate $\beta _ { s m }$ of the sRNA-mRNA duplex. (b) $F _ { p }$ isaffected by the binding rate $k$ Here $\alpha _ { s } { = } \dot { 1 } \ \mathrm { \ n M \ m i n } ^ { - 1 }$ ．All other parameters are set as in Fig.2.

On the contrary, the result shows that over a range of $\alpha _ { m } > \alpha _ { s } ,$ a larger binding rate $k$ of mRNA with sRNA produces a larger fluctuation of the output protein.At this region of $\alpha _ { m } ,$ the noise of sRNA will propagate to the mRNA,and the efficiency of noise propagation depends on the binding rate.As $k$ approaches infinity,the numberof freemRNA that canwork for translation is the difference between thenumberofmRNA and the numberof sRNA. Thus, it will keep all noise originating from mRNA and sRNA in the free mRNA. With a decreasing combination rate $k ,$ the coupling between mRNA and sRNAbecomesweaker,and the noise of mRNA propagated from sRNAbecomes smaller.

# Response and recovery of target expression

It is important for a cell to be sensitive and to rapidly respond to an external signal. For the new sRNA regulation mechanism，the response time characterizes how long it takes for mRNA to change from an sRNA-free state to an sRNA-bound state. Below，we will use the mean first passage time (MFPT) to measure this important characteristic time.

Because of stochastic reactions and molecular fluctuation,it is necessary to calculate the time it takes to reach a new state in probabilistic meaning. The previous work provided information on response time through experiments.15 However, solving the master equation to obtain an analytic result for response time is difficult.Here we still use the Gillespie direct method to solve the problem concerning both stochastic reaction and molecular fluctuation. From the results of Fig. 7a, we see that a faster response of the target always corresponds to a higher recycling ratio of the regulator.A smaller responsetimemeansamoresensitiveand effective regulatory mode.

Recovery time is the time required for output recoveryafter the external signalhasbeenremoved. It is calculated similarly as the response time (see Fig. 7b).As the recycling ratio increases, the target mRNA will decrease，and more time will be required for the recovery of this target gene expression.In the limit case of $\delta = 1$ ，thelevel of protein cannot recover from the repressed state even in several cell cycles (Fig. 7b). However，if the binding of the two RNA molecules or the degradation of the RNA duplex is slow and ineffective, the recovery of target expression may be fast even when the sRNA regulator is fully recycled.

![](images/07025f6f6b57aea939d6786371c33aef55501f1c9ac84a4c778738ef4931b27f.jpg)  
Fig.7.Response time (a) and recovery time (b) of target gene expression.In the simulations, the threshold is set to $7 0 \%$ of the difference between the initial-state mRNA level and the final-state mRNA level. $\alpha _ { m }$ is set to $0 . 5 \mathrm { n M } \mathrm { m i n } ^ { - 1 }$ and the other parameters are set as in Fig.2.

# Simulation results versus experimental results

To test our model, we simulate the time evolutions of sRNA and its target mRNA,respectively,when theyare expressed alone and together in the system. As shown in Fig. 8a, according to our simulation with reasonable parameters,more than half of mRNA molecules are inhibited after $^ { 1 \mathrm { ~ h ~ } }$ of expression. For the fully recycling ratio $\delta = 1$ , our simulation result shown in Fig. 8a is consistent with experimen tal results.15

![](images/dad90d4bb209874cbb81b68959d58a13358ff551dd5ba4deb25856bb5f0816a1.jpg)  
Fig.8.Time evolutions of sRNA and its target mRNA. First, sRNA was expressed over $1 0 \mathrm { ~ h ~ }$ to arrive at steady state.Then at time O, the sRNA gene was shut off,and mRNA was expressed for $6 5 ~ \mathrm { m i n }$ .Parametersare set as: $\alpha _ { s } { = } 4 \mathrm { n M m i n } ^ { - 1 }$ 1 $\begin{array} { r } { \alpha _ { m } { = } 7 \pi \mathrm { M } \mathrm { m i n } ^ { - 1 } , } \end{array}$ and $k { = } 0 . 0 0 1 ( \mathrm { n M m i n } ) ^ { - 1 }$ Other parameters are set as in Fig.2.(a) Time evolution of sRNA and mRNA with $\delta = 1$ .Superscript $^ { \prime \prime } { + } ^ { \prime \prime }$ or $^ { \prime \prime } - \prime \prime$ indicates the presence ortheabsence of relevant RNA, respectively.(b) Effects of δ on time evolutions.Empty symbols represent sRNA，and filled symbols represent mRNA.

We focus on the time point where the number of mRNA and the number of sRNA are equal to each other in a cell.After that point,mRNA continues to accumulate,while sRNA is still actively degraded (see Fig. $8 \mathsf { b } ,$ ，gray rhombus). Consistent with the previous analysis, the more effective is the recycling the more time it takes to reach the time point to start gene expression.Under the same condition,it takes twice aslong for target mRNA to recover from the state of suppression with null recycling $( \delta = 0 )$ than with full recycling $( \delta = 1 )$ ：

# Discussion

MicM was first proven to be an unusual antisense sRNAwhenit did not destabilizeevenwhen target ybfM mRNA was overexpressed. However，for another target gene that belongs to a chb operon and possesses complementarity to the same region of MicM，annealing of MicM causes coupled degradation.15 For the most identified antisense sRNA-mediated gene silencing in bacteria, the Smlike protein Hfq binds efficiently to both types of RNAs to stabilize them_17-19 and to accelerate annealing between them.17,18 Here we start with a basicmodel of MicM-ybfM mRNA interaction and study in detail the noise properties of target expression by simulation.Our calculation shows thatthe inhibitioneffectof sRNAwillbeweakeven withahigh recycling rate (targetmRNA will escape easily as $k$ is reduced;data not shown).It implies that the inhibitory efficiency of catalytic sRNA depends more on the efficiency of sRNA-mRNA duplex formation than on the recycling ratio. On the other hand,it has been shown in Fig.6b that a weaker binding betweensRNA and mRNAusually causes more noise on target expression in the silencing region. All these findings may contribute to a better understanding of physiological significance and further design of the small RNA gene regulatory network.

It is interesting to note that all curves of mRNA in Fig.2 can be considered equivalent if we scale $\alpha _ { s }$ to $\frac { \alpha _ { s } ^ { \smile } } { 1 - \delta }$ and if we scale $\lambda$ to $\frac { \lambda } { 1 - \delta }$ In other words, the recycling ratio linearly affects the steady-state behavior of mRNA，but its influence on noise is distinctive; both the peak width and the peak value of the noise curve are significantly affected by the recycling ratio in a somewhat complicated manner, whichwillbeconsideredinfurtherstudies.

It is known that sRNA is prevalent in bacteria, and it acts by various mechanisms besides basepairing with other RNAs.For example,a few of the sRNAs are part of ribonucleoproteins that carry out specific housekeeping functions. Some others act by mimicking the structures of other nucleic acids to sequester their cognate proteins. All these regulatory modes are supposed to make sense in the selective evolution of life.Intricate regulatory infor mation canbe deciphered regardless of whether the regulator is a protein or an sRNA，the level of regulation,and whether the regulationis enzyme-like or not.In this sense,different noise performances may ensure life activity, diversity,and complexity.

the threshold.It theoretically represents the time it takes, onaverage,to reach a boundary the first time. The threshold valuesheremean certainboundaryconditions. However,by simulation,we only use the stochastic state sequenceproducedby SSA and seta thresholdvalue for thechemical reactant that we wantto analyzeand then calculate the time when it crosses the threshold the first time.Finally，we obtain the MFPT by averaging the results that are repeatedlyderived.

# MaterialsandMethods

Theanalysis was carried out using a simplified rate equation model and Monte Carlo (Gillespie algorithm26) simulations.All simulation parameters were_obtained from a reasonable estimation of experiments.12,15

The Gillespie algorithm，developed by Daniel T. Gillespie in the 1970s,is well known as an effective SSA. By calculating the reaction probability density function $P \bar { ( \tau , \mu ) }$ using the current reaction rate and reactant species combination number，we can determine the probability of when the next reaction will occur $\left( \tau \right)$ and which reaction will occur $( \mu )$ .Then we renew the molecular number of relevant species.The Gillespie direct method needs two uniform random numbers to generate the random values $\intercal$ and $\mu$ that obey the reaction probability density function,so it is also a type of Monte Carlo algorithm.In this way，we obtain statistically correct trajectories of the chemical system's time evolution，which is rigorously equivalent to that produced by the grand probability function $P ( X _ { 1 } , . . . , X _ { N } ; t )$ as the solution of the master equation.

It is quite difficult to obtain an integrated analytic solution for even a simple master equation.The most important advantage of SSA is that it is an exact algorithm that takes full account of fluctuations and is easy to code in a computer program. It is also effective for calculating other relevant physical variables suchas the Fano factor andresponse time.

Based on the ergodic hypothesis of equilibrium statistical physics,the ensemble average coincides with the time average (see Eq.(6)).To obtain themean and variance of the molecules of a biochemical system,we only apply the frequency statistics (for a long-enough time) of the stochastic state sequence produced by SSA in steady state,with state waiting time as weight:

$$
\langle X \rangle = \sum f ( X ) P ( X ) = \operatorname* { \ l i m } _ { T \to \infty } { \frac { 1 } { T } } \int _ { 0 } ^ { T } f ( X ( t ) ) \mathrm { d } t
$$

where $X$ represents the value of any reaction species here and the function $f ( X )$ may represent its mean value or variance.

We use a so-called MFPT to describe the response characteristic of the biochemical system.MFPT is defined as:28

$$
\langle T _ { f } \rangle = \int _ { 0 } ^ { \infty } t ( - \mathrm { d } P _ { t } ) , { \mathrm { ~ w h e r e } } P _ { t } = \sum _ { X _ { i } = 0 } ^ { T h _ { X _ { i } } } P ( X _ { 1 } , \dots , X _ { N } ; t )
$$

Here, $X _ { i }$ is the variable of interest，and $T h _ { X _ { i } }$ isits threshold value,while $\left. T _ { f } \right.$ represents its MFPT crossing

# Acknowledgements

This work was supported by the National Basic Research Program of China (grant 2007CB814800). H.S.is grateful to Zhongcan Ouyang，Weimou Zheng,and Terry Hwa for useful discussions.

# References

1.Gottesman, S. (2004). The small RNA regulators of Escherichia coli roles and mechanisms. Annu. Rev. Microbiol. 58,303-328.   
2.Majdalani,N.& Gottesman,S. (2005). The Rcs phosphorelay:a complex signal transduction system Annu.Rev.Microbiol.59,379-405.   
3.Gottesman，S.，McCullen，C.A.，Guillier，M., Vanderpool, C.K.，Majdalani,N.，Benhammou,J. et al.(2006). Small RNA regulators and the bacterial response to stress. Cold Spring Harb.Symp. Quant.Biol. 71, 1-11.   
4. Vanderpool, C. K. (2007). Physiological consequences of small RNA-mediated regulation of glucosephosphate stress. Curr. Opin.Microbiol.10,146-151.   
5. Singh,P.K., Schaefer,A.L.,Parsek, M.R.,Moninger, T.O.,Welsh,M.J.& Greenberg,E.P.(2000).Quorumsensing signals indicate that cystic fibrosis lungs are infected with bacterial biofilms.Nature,407,762-764.   
6.Miller,M.B.& Bassler, B.L.(2001). Quorum sensing in bacteria.Annu.Rev.Microbiol. 55,165-199.   
7.Lenz,D.H.,Mok,K.C.,Lilley, B.N.,Kulkarni,R.V, Wingreen,N.S.& Bassler,B.L. (2004). The small RNA chaperone Hfq and multiple small RNAs control quorum sensing in Vibrio haroeyi and Vibrio cholerae. Cell, 118, 69-82.   
8.Waters,L. S.& Storz, G. (2009). Regulatory RNAs in bacteria. Cell,136,615-628.   
9.Gottesman, S. (2005). Micros for microbes: non-coding regulatory RNAs in bacteria. Trends Genet. 21, 399-404.   
l0．Aiba,H. (2007).Mechanism of RNA silencing by Hfq-binding small RNAs. Curr. Opin. Microbiol. 10, 134-139.   
[1.Semsey,S.,Andersson,A.M.,Krishna,S.,Jensen,M.H., Masse, E.& Sneppen, K. (2006). Genetic regulation of fluxes: iron homeostasis of Escherichia coli.Nucleic Acids Res. 34,4960-4967.   
l2.Levine,E., Zhang, Z.,Kuhlman, T.& Hwa,T. (2007). Quantitative_characteristics of gene regulation by small RNA. PLoS Biol.5,e229.   
13. Shimoni,Y.,Friedlander,G.,Hetzroni,G.,Niv,G. Altuvia, S.,Biham, O.& Margalit,H. (2007).Regulation of gene expression by small non-coding RNAs: a quantitative view.Mol. Syst.Biol.3,138.   
14.Mitarai, N.,Andersson,A.M.,Krishna, S., Semsey, S &Sneppen，K.(2oo7).Efficient degradation and expression prioritization with small RNAs.Phys. Biol. 4,164-171.   
15.Overgaard，M.，Johansen，J.，Moller-Jensen,J.& Valentin-Hansen，P. (2009). Switching off small RNA regulation with trap-mRNA. Mol. Microbiol. 73,790-800.   
16.Vogel, J. (2009). An RNA trap helps bacteria get the most out of chitosugars.Mol. Microbiol. 73,737-741.   
17.Rasmussen，A.A.，Johansen，J.，Nielsen，J.S. Overgaard,M.,Kallipolitis,B.& Valentin-Hansen,P. (2009).A conserved small RNA promotes silencing of the outer membrane protein YbfM.Mol.Microbiol.72, 566-577.   
18.Mandin，P.& Gottesman，S. (2009).A genetic approach for finding small RNAs regulators of genes of interest identifies RybC as regulating the DpiA/DpiB two-component system. Mol. Microbiol. 72, 551-565.   
19. Sittka,A., Lucchini, S.,Papenfort,K., Sharma, C.M Rolle,K.,Binnewies,T.T.,Hinton,J.C.& Vogel,J (2008). Deep sequencing analysis of small noncoding RNA and mRNA targets_of the_ global posttranscriptional regulator，Hfq. PLoS Genet. 4, e1000163.   
20.Mehta,P.，Goyal,S.& Wingreen,N.S.(2008)．A quantitative comparison of sRNA-based and protein based generegulation. Mol. Syst.Biol.4,221.   
21.Bintu, L.,Buchler, N. E., Garcia,H. G., Gerland, U., Hwa,T.,Kondev,J.& Phillips,R. (2005).Transcriptional regulation by the numbers:models. Curr Opin Genet Dev.15,116-124.   
22.Bintu,L., Buchler,N.E.,Garcia,H. G.,Gerland, U., Hwa，T.，Kondev，J.et al. (2005).Transcriptional regulation by the_numbers: applications. Curr. Opin. Genet. Dev.15,125-135.   
23.Ozbudak,E.M.,Thattai,M.,Kurtser,I.,Grossman,A.D &van Oudenaarden,A. (2oo2).Regulation of noise in the expression of a single gene. Nat. Genet. 31, 69-73.   
24.Thattai,M.& van Oudenaarden,A.(20o1).Intrinsic noise in gene regulatory networks.Proc.Natl.Acad. Sci. USA,98, 8614-8619.   
25.Raser, J.M.& O'Shea,E.K.(2005).Noise in gene expression: origins, consequences,and control. Science, 309,2010-2013.   
26.Gillespie,D.T.(1977).Exact stochastic simulation of coupled chemical reactions.J.Phys.Chem．81, 2340-2361.   
27.Levine,E.,Huang,M.,Huang,Y.W.,Kuhlman, T., Shi,H.,Zhang,Z.,Hwa,T. On noise and silence in small RNA regulation. Submitted. http://matisse. ucsd.edu/hwa/pub/sRNA-noise.pdf   
28.Lan, Y.& Papoian, G.A. (20o7). Stochastic resonant signaling in enzyme cascades.Phys.Rev.Lett.98 228301.