# Theoretical studies on sRNA-mediated regulation in bacteria

This content has been downloaded from lOPscience.Please scroll down to see the fulltext.

2015 Chinese Phys.B 24 128703

(http://iopscience.iop.0rg/1674-1056/24/12/128703)

View the table of contents for this issue,or go to the journal homepage for more

Download details:

IP Address:124.16.143.57   
This content was downloaded on 08/05/2016 at 12:41

Please note that terms and conditions apply.

# TOPICAL REVIEW— 8th IUPAP International Conference on Biological Physics

# Theoretical studies on sRNA-mediated regulation in bacteria\*

Chang Xiao-Xue(常晓雪)b)，Xu Liu-Fang(徐留芳)a)b)†，and Shi Hua-Lin(史华林)b)\$

a)DepartmentoficsandoreticalPysicsCenteJinUiversityChangchn0 b)StateKebli (Received 4 May 2015;revised manuscript received 27 August 2015; published online 20 October 2015)

Small RNA(sRNA)-mediated post-transcriptionalregulation differs from protein-mediated regulation.Through basepairing,sRNAcanregulate thetargetmRNA inacatalyticorstoichiometric manner.Sometheoretical models werebuiltfor comparison of theprotein-mediated and sRNA-mediated modes in the steady-state behaviors and noise properties.Many experimentsdemonstrated that a single sRNAcanregulate several mRNAs,which causes crosstalk between the targets. Here,we focus on some models in which two target mRNAs are silenced by the same sRNA to discusstheir crosstalk features.Aditionaly,the sequence-functionrelationshipofsRNAand its role inthe kinetic processof base-pairing have been highlighted in model building.

Keywords:sRNA-mediated regulation,kinetic model, crosstalk

PACS: 87.14.gn, 87.15.A-, 87.16.Yc

DOI:10.1088/1674-1056/24/12/128703

# 1. Introduction

In bacteria,small RNAs (sRNA） post-transcriptionally regulate target mRNAs through base-pairing，which plays an important role in physiological processes,such as iron metabolism,[1] acid stress,[2] quorum sensing,[3] and outer membrane protein expression.[4] sRNA have been categorized into two types according to the location in the genome: cisencoded sRNA and trans-encoded sRNA.The former is located in the same region as its target mRNA in the genome and completely bases pairing with the target,while the latter is located in regions different from those of its targets and partially bases pairs with the targets.[5] Here,we focused on trans-encoded sRNAs, which usually have three basic regions: the core interaction region,the Hfq-binding site,and a rhoindependent terminal. The core interaction region,also called the“seed ” region,helps sRNA to specifically discern target mRNAs and initiates the base-pairing with mRNAs.6] The Hfq-binding site usually an AU-rich region,helps sRNA bind at the proximal face of Hfq.[7] Hfq is a donut-shaped homohexamer that facilitates the base-pairing of sRNA and mRNA through improving sRNA stabilization or structural transformation of mRNA.[8.9] However, the exact mechanism underlying the effect of Hfq is not clear. Recently, some experiments have revealed that polyU of the terminal of sRNA is another Hfq-binding site and is necessary for the efficacy of sRNA.[10.11] sRNA has two effects on the translation of mRNA: negative regulation,in which sRNA base pairing with mRNA near the ribosome binding site (RBS）inhibits the loading of ribosomes,and thus the translation of mRNA is repressed,[12,13] and active regulation,[14-16] in which the binding of sRNA loosens the intra-base-pairing of RBS of mRNA so that the ribosome can carry out the translation.In the scenario of negative regulation,most of the sRNA-mRNA duplex is stoichiometrically degraded by endonuclease.[17] Various models of sRNA-mediated regulation are shown in Fig.1.

Recently，another model has demonstrated that ChiX (MicM） sRNA catalytically regulates chip(ybfM） mRNA, which indicates that sRNA does not undergo codegradation with mRNA in a stoichiometric manner but with recycling.[18,19] Based on the results of these experiments, Hao et al. built a catalytic-sRNA-mediated gene silencing (CSMGS) model to analyze its novel properties.[20] For transencoded sRNAs,they usually regulated several mRNAs that comprise a network,[21,22] such as ChiX sRNA which is also codegraded with another targetchbBmRNA,and is exhausted in a stoichiometric model to release chiP mRNA.[19,23]

With the accumulation of experimental data, several models have been built to characterize the regulatory system. In this review, first, we have presented an sRNA-mediated regulatory model in a stoichiometric manner,[24] and compared it with the protein-mediated post-transcription model. Second, we have discussed the features of the catalytic model and stoichiometric model with respect to sRNA-mediated regulation from both steady-state analysis and noise analysis.Third, we have introduced a model depicting the simplest network of two target mRNAs regulated by a single sRNA,which shows the hierarchical crosstalk behavior between the target mRNAs.Fourth,we have discussed the latest research on the sequence-function relationship of sRNA in gene silencing, which should provide the foundation and basis of modeling the sRNA-mediated regulation.

![](images/32ed18c8f67cd76dc4eec9ac3c282a50e8103b7b042936b4ac30736fb350365a.jpg)  
Fig.1.(coloronline)SmallRNA-basedregulatorymechanismsofmRNAexpresion.(a)RNAblocks translationofRAbydirectly bindingtotheribosomebindingsite(RBS)ofmRNA.(b)and(c)ThebindingofsRNAonmRNAsequesterstheibosome,becauseofwhich endonucleaseitesreexposdtoegadatiobyaseEinpassveorctivemaer.(d)TeRrioofAsosintra-bapaiing intheabsenceofsNAthatinibits translationofmRNA.TebndingofsRNAloosenstheRBsotatitisavailableinaforofasingle strandfortranslatiobytbosoe.TegreovalsindiatetebosoesthatareinvoledintraslatioofA.Tepupes indicate the proteins generated.AUG is the start codon for translation of mRNA.[17]

# 2. Comparison of sRNA-mediated and proteinmediated regulation

sRNAs post-transcriptionally regulated the expression of mRANs,which differs from the transcriptional regulation of transcription factors (TFs)，a kind of protein-mediated regulation. Levine et al. found that sRNA-mediated regulation exhibited novel properties,such as the threshold-linear property and that it more tightly repressed target mRNA below the threshold and showed better robust noise resistance than protein-mediated regulation.24] For further discussion of the characteristics,we introduce the work of Mehta et al.; they treated TF-mediated and sRNA-mediated regulation asa signal-processing system and accordingly discussed the steady-state behavior,noise properties,frequency-dependent gain, and dynamical response to the input signals.[25]

Mehta et al.built a model forsRNA-mediated regulation by using mass action equations combined with intrinsic noise defined byLangevin termsas fellows:

$$
\frac { \mathrm { d } s } { \mathrm { d } t } = \alpha _ { s } - \tau _ { s } ^ { - 1 } s - \mu m s + \hat { \eta } _ { s } + \hat { \eta } _ { \mu } ,
$$

$$
\begin{array} { l } { \displaystyle \frac { \mathrm { d } m } { \mathrm { d } t } = \alpha _ { m } - \tau _ { m } ^ { - 1 } m - \mu m s + \hat { \eta } _ { m } + \hat { \eta } _ { \mu } , } \\ { \displaystyle \frac { \mathrm { d } p } { \mathrm { d } t } = \alpha _ { p } m - \tau _ { p } ^ { - 1 } p + \hat { \eta } _ { p } . } \end{array}
$$

In this model, the sRNA(mRNA) transcription rate is set as $\alpha _ { s }$ 0 $( \alpha _ { m } )$ ,and degradation rate is set as $\tau _ { s } ^ { - 1 } ( \tau _ { m } ^ { - 1 } )$ ： $\mu$ is the binding strength of sRNA and mRNA.The protein is translated from mRNA at the rate $\alpha _ { p }$ .s, $m$ ，and $p$ refer to the amount of sRNA,mRNA,and protein, respectively. $\hat { \eta } _ { s } , \hat { \eta } _ { m }$ $\hat { \eta } _ { \mu }$ ，and $\hat { \eta } _ { p }$ characterize the noise related to the creation and degradation of sRNA,mRNA,sRNA-mRNA,and protein, respectively. The Langevin terms are formatted by the time correlation functions $( j = s , m , p , \mu )$ ：

$$
\langle \hat { \eta } _ { j } ( t ) \hat { \eta } _ { j } ( t ^ { \prime } ) \rangle = \sigma _ { j } ^ { 2 } \delta ( t - t ^ { \prime } ) .
$$

The TF-mediated transcriptional regulation is modeled using the Langevin equations:[26-29]

$$
\begin{array} { l } { \displaystyle { \frac { \mathrm { d } m } { \mathrm { d } t } = \alpha _ { m } - \tau _ { m } ^ { - 1 } m + \hat { \eta } _ { m } , } } \\ { \displaystyle { \frac { \mathrm { d } p } { \mathrm { d } t } = \alpha _ { p } m - \tau _ { p } ^ { - 1 } p + \hat { \eta } _ { p } , } } \end{array}
$$

where $\hat { \eta } _ { m }$ and $\hat { \eta } _ { p }$ model noise in the synthesis and degradation of mRNA and protein respectively,and obey the equations $( j = m , p )$ （204号

$$
\langle \hat { \eta } _ { j } ( t ) \hat { \eta } _ { j } ( t ^ { \prime } ) \rangle = 2 \tau _ { j } ^ { - 1 } j \delta ( t - t ^ { \prime } ) .
$$

Ignoring the Langevin terms and setting the derivatives to zero in Eqs.(1) and(2),we can determine the amount of proteins in the steady state in both sRNA-mediated and TFmediated regulation. Consistent with the study ofLevine et al., sRNA-mediated regulation shows the linear-threshold property for the target mRNA expression level with the threshold around $\alpha _ { m } \sim \alpha _ { s }$ [24] When $\alpha _ { m } \leq \alpha _ { s }$ , the translation of mRNA is repressed; when $\alpha _ { m } \gg \alpha _ { s }$ , the expression level of protein is linear to $\left( \alpha _ { m } - \alpha _ { s } \right)$ . The binding strength $\mu$ just determines the smoothness of the crossover around the threshold $\alpha _ { s }$ .By contrast, the amount of mRNA in the TF-regulated steady state is a linear function of $\alpha _ { m }$ .[26-29]

Based on the equations above,they also studied the intrinsic noise properties,[30-32] frequency-dependent gain (amplification),[33] and dynamical response to large input signals of sRNA-mediated and protein-mediated regulation.[34] Taken together, their characteristics are summarized in Table 1 cited from Mehta et al.[25]

Table1.SummaryoftedantagesanddisadvantagesofsNAssomparedwithtranscriptioalproteinegulators(transcriptiofactors)   

<html><body><table><tr><td>Advantages of sRNAs</td><td>Advantages of protein regulators</td></tr><tr><td>·sRNAs are beter than protein regulators at keeping proteins “off" because a large pool of sRNA shortens the effective mRNA lifetime and buffers against target mRNA fluctuations. ·sRNAs can filter high-frequency noise without compromising the ability to rapidly respond to large changes in input signals. →sRNAs likely fill a “niche” in allowing cels to transition quickly yet reliably between distinct states.</td><td>·The intrinsic noise for sRNA based regulation is much larger than that for transcriptional regulation in a large (intermediate to high) range of expression levels of the regulated protein,especially in the presence of transcriptional bursting. ·Protein regulators are better than sRNAs at transducing small input signals. ⇒Protein regulators are likely better suited for quantitative adjustment</td></tr></table></body></html>

# 3. Models of sRNA-mediated gene silencing: Stoichiometric and catalytic modes

# 3.1.Steady-state behavior of target mRNA regulated by sRNA

sRNA-mediated gene silencing was initially believed to occur in the stoichiometric mode,which differs from the protein-mediated catalytic mode. However, some experiments in bacteria showed that sRNA can exert its effects in the catalytic mode also,which means that sRNA can promote the degradation of mRNA with a certain ratio of sRNA survival.[18,19]

![](images/e8fd655334275011a1d8cbb6f3e800d63307b23b636530c0d22d455e888e44e5.jpg)  
Fig.2.(color online）Catalytic-sRNA-mediated gene silencing (CSMGS) model,[20]

To investigate the characteristics of sRNA-mediated regulation with recycling，Hao et al. developed the catalyticsRNA-mediated gene silencing model (CSMGS),[20l based on Levine's model (Fig. 2).[24] They introduced the recycling rate $\delta$ referring to how much sRNA is surviving from the sRNA-mRNA combo degradation. The resulting recycling item $\delta \beta _ { s m } ( s _ { - } m )$ was added in the catalytic model shown in Eqs.(3)，in which $\beta _ { s m } ( s \lrcorner m )$ means the degradation rate of sRNA-mRNA combo． Therefore,setting $\delta$ to O transforms the catalytic model into the stoichiometric model. As mentioned above,Hfq is necessary for most of the trans-encoded sRNA regulation,but the mechanism is not very clear. Here both models assumed that Hfq is abundant.[35]

The mass action equations of CSMGS model are

$$
\begin{array} { c } { \displaystyle \frac { \mathrm { d } s } { \mathrm { d } t } = \alpha _ { s } - \beta _ { s } s - k \cdot s \cdot m + \delta \beta _ { s m } ( s . m ) , } \\ { \displaystyle \frac { \mathrm { d } m } { \mathrm { d } t } = \alpha _ { m } - \beta _ { m } m - k \cdot s \cdot m , } \\ { \displaystyle \frac { \mathrm { d } ( s . m ) } { \mathrm { d } t } = k \cdot s \cdot m - \beta _ { s m } ( s . m ) , } \\ { \displaystyle \frac { \mathrm { d } p } { \mathrm { d } t } = k _ { p } m - \beta _ { p } p . } \end{array}
$$

In this model,s $( m ) , \alpha _ { s } ( \alpha _ { m } )$ ，and $\beta _ { s } \ ( \beta _ { m } )$ indicate the sRNA(mRNA) concentration,the transcription rate,and the degradation rate, respectively. The binding rate $k$ refers to the strength of sRNA-mRNA interaction which is relevant to the kinetic process of base-pairing of sRNA with mRNA.

Setting the differential equations to zero yields

$$
\begin{array} { l } { \alpha _ { s } - \beta _ { s } s - k ( 1 - \delta ) \cdot s \cdot m = 0 , } \\ { \alpha _ { m } - \beta _ { m } m - k \cdot s \cdot m = 0 . } \end{array}
$$

When $0 \leqslant \delta < 1$ ，the stationary solution of sRNA, mRNA, sRNA-mRNA duplex,and protein can be obtained as

follows:

$$
\begin{array} { r l } & { s = \frac { 1 } { 2 \beta _ { s } } \Big [ ( \alpha _ { s } - ( 1 - \delta ) \alpha _ { m } - \lambda ) } \\ & { \qquad + \sqrt { ( \alpha _ { s } - ( 1 - \delta ) \alpha _ { m } - \lambda ) ^ { 2 } + 4 \alpha _ { s } \lambda } \Big ] , } \\ & { m = \frac { 1 } { 2 \beta _ { m } } \Bigg [ \left( \alpha _ { m } - \frac { \alpha _ { s } } { 1 - \delta } - \frac { \lambda } { 1 - \delta } \right) } \\ & { \qquad + \sqrt { \left( \alpha _ { m } - \frac { \alpha _ { s } } { 1 - \delta } - \frac { \lambda } { 1 - \delta } \right) ^ { 2 } + \frac { 4 \alpha _ { m } \lambda } { 1 - \delta } } \Bigg ] } \\ & { \left( s , m \right) \stackrel { \circ } { \sim } \frac { \alpha _ { m } - \beta _ { m } m ^ { * } } { \beta _ { m } } , } \\ & { p = \frac { k _ { p } } { \beta _ { p } } s ^ { * } = m m ^ { * } . } \end{array}
$$

![](images/348d79335dbe5ba9fb2e4195c4fdc19dcd60161734603b39875cc5bafc8d2354.jpg)  
Fig.3.Stationary solutions and Fano factors of target mRNA vary with its transcription rate $\alpha _ { m }$ in different recycling ratio in the CSMGS model.[20]

The parameter $\lambda$ is defined as $\lambda = \beta _ { m } \beta _ { s } / k$ ，which indicates the ratio of the spontaneous and codegradation rates. $n = k _ { p } / \beta _ { p }$ refers to the burst size of target protein production. Some experiments have suggested that the base-pairing of sRNA with mRNA is strong and fast; therefore, we can approximate $\lambda$ to zero.[20l Then the stationary solution of mRNA can be written as follows:

$$
m = \left\{ \begin{array} { l l } { 0 , } & { \displaystyle \alpha _ { m } < \frac { \alpha _ { s } } { 1 - \delta } , } \\ { \displaystyle \frac { \alpha _ { m } - \alpha _ { s } / ( 1 - \delta ) } { \beta _ { m } } , } & { \displaystyle \alpha _ { m } > \frac { \alpha _ { s } } { 1 - \delta } . } \end{array} \right.
$$

Figure 3(a) shows the steady-state expression level of mRNA responding to its transcription rate for different recycling ratios of sRNA.In the case of $\delta = 0$ ,the CSMGS model refers to the stoichiometrical regulation mode of sRNA,whose threshold-linear property has been discussed in the model of Levine et al.[24] The CSMGS model exhibited the similar threshold-linear property,but with the threshold characterized by $\alpha _ { s } / ( 1 - \delta )$ . When the transcription rate of mRNA crosses the threshold, the amount of mRNA is linearly related to $\alpha _ { m }$ Compared to the stoichiometric mode,in the catalytic mode, gene silencing by sRNA is more rapid because a lesser number of sRNA are required to degrade mRNA with a given $\alpha _ { m }$ .[20,36]

# 3.2.Intrinsic noise analysis for the models of sRNAmediated gene silencing

It is believed that noise significantly affects the dynam ics behavior of molecules in vivo such as sRNAs,mRNAs and proteins.[37,38] There are mainly two types of noise: intrinsic noise,which is related to the low reactant number and reactant stochastic bursting,[38-40] and output noise, which is related to diffusion between reactant pools and the neighbor ing environment.[41] Here we focus on the intrinsic noise in sRNA-mediated gene silencing.

Generally, there are three approaches to study the noise of the biochemical reactions.The first approach is by means of Langevin equations (as in Eq.(1)),[42] which was further developed as the linear noise approximation (LNA).[39,43] This method can provide analytical results for both the mean value and variance of each reactant.The second approach is to use the master equation.[38,44l All biochemical reactions can be depicted in the master equation,which gives the evolution of the joint probability of all the reactant species.Generally, it is difficult to solve the master equation analytically; therefore, many researchers will choose the third approach of stochastic simulation with the Gillespie algorithm.[45-47]

One can choose the appropriate strategy according to the research objective；all these objectives can provide the mean value $\textstyle { \overline { { x } } }$ and variances $\sigma _ { x } ^ { 2 }$ of the reactant species $\langle x =$ $s , m , p , \ldots )$ , and the Fano factor $F _ { x } = \sigma _ { x } ^ { 2 } / \overline { { x } }$ ,which signifies the noise strength of each biochemical reactant.In the CSMGS model,Hao et al. applied the Gillespie algorithm to the noise properties of catalytic-sRNA mediated regulation.[20]

Inprevious studies,it was believed that the transcription ofRNA is a standard Poisson process,which means that the Fano factor $F _ { s } = F _ { m } = 1$ [38.39] However, the sRNA-mediated gene silencing is not a pure Poisson process. Only when the parameter $\alpha _ { m }$ is far away from the regulatory threshold, the Fano factor is close to 1,while the Fano factor around the threshold is much larger than 1 (Fig.3(b)). The burst of the noise of target mRNA around the threshold is due to the anticorrelation between the number of mRNAs and that of sRNAs.48] This conclusion can be fit to both Levine et al.'s model and the CSMGS model.

Comparison of the noise properties of the two models suggested that the catalytic sRNA can more strictly repress the target mRNA at the threshold site of $\alpha _ { m } \sim \alpha _ { s }$ [20.46] Figure 3(b) exhibits a right-shift threshold of the noise amplifica tion effect for the CSMGS.

Another important question that arises pertains to the noise transmitted in the process of sRNA-mediated gene regulation,for example,whether the noise at the mRNA level would be transmitted to the protein level.Therefore，in the scenario of sRNA,the noise strength of protein expression includes the bursting noise of the mRNA and protein production.[20] However, for protein-mediated regulation, the noise is calculated byFp ≈ 1+n.[26,39,44]

# 4. Crosstalk between multiple target mRNAs mediatedbyasinglesRNA

Many trans-encoded sRNAs target several mRNAs,and a single mRNA can also be regulated by different sRNAs,which form a complex network.[6.34,49] In the case of multiple mRNAs repressed by a single sRNA,mRNAs will crosstalk with each other through sRNA competition.[50l Considering some cases of double-target mRNAs,sRNA may regulate both mRNAs in the stoichiometric mode,for example,RyhB undergoes codegradation with sodB and sdhCDAB mRNA;[1] however,in some other cases,sRNA can catalytically regulate one mRNA,while stoichiometrically regulating the other mRNA, for example ChiX represses chiP and chbB.[18,19]

Levine et al. extended the kinetic model (Eq. (3)) into a two-targetmRNAs model and found thatmRNAs exhibit hierarchical cross-talk that is determined by the binding rate $k$ [24] When the reporter mRNA binds with sRNA more strongly than another mRNA $( k _ { R } > k _ { T } )$ ，the reporter mRNA can exhaust the sRNA pool quickly and release the repression of the later target mRNA， the function of which is similar to the “switch effect”, [24,51]

The CSMGS model has been taken in discussing the crosstalk of two mRNAs by setting of one of the mRNAs regulated in the catalytic mode and the other in the stoichiometric mode.[51l In the completely catalytic model, as $\delta = 1$ ,the crosstalk is one-directional. The mRNA in the stoichiometric mode exhausts sRNA to“switch on”the mRNA in the catalytic mode.This has been experimentally demonstrated in the ChiX-chiP-chb system.[18,19] Before adequate induction, chb as a target mRNA is repressed by ChiX through base-pairing On growth in chitobiose medium, the chb operon is induced. Along with the increase in chb,chb mRNA transforms from target mRNA completely repressed by ChiX sRNA to “trapmRNA",which causes the degradation of ChiX. When the amount of chb mRNA exceeds that of ChiX,signifying across the threshold depicted byLevine et al., the translation of chiP mRNA is released.[18-20,24]

Based on the noise study of the single-target model, researchers have provided a new noise profile for two target mRNAs competing to exhaust the same sRNA pool. Same as the single target model, of which the noise around the threshold （204号 $( \alpha _ { m } \simeq \alpha _ { s } )$ ）tends to be amplified,the noise of the two-targets model also presents a series of peaks in the crossover region $( ( \alpha _ { m 1 } + \alpha _ { m 1 } ) \simeq \alpha _ { s } )$ .[51] This remarkable feature can be used in experiments to explore the crosstalk of double targets mediated by sRNA.

Recently, there has been further novel progress in the multi-targets model where the target numberis far greater than two.[47,50l Bosia et al. found that one target mRNA above its regulatory threshold is able to drive other common target crossover thresholds,and that hierarchical crosstalk among the multiple targets is much more notable.[47] Jost et al. proposed that sRNA weakly regulates many mRNAs as auxiliary targets,which have no effect on the phenotype of the organism but provide a buffer to confer robustness to few“principal” targets.[50] These developments have improved the understanding of sRNA-mediated gene regulation.

# 5. Sequence-function relation of sRNA in regulating target mRNA

sRNA-mediated regulation is dependent on base-pairing with mRNA；therefore the functional efficiency of sRNA should be determined by the kinetic process of base-pairing. Some experiments highlighted the factors working on sRNAmediated regulation,such as the length of the core interaction region, the secondary structure and the duplex formation energy.[20.52] The factors and the relevant energies could be used in the algorithms for searching the latent sRNA-mRNA system in vivo and were also modeled to artificially synthesize the sRNA-mRNA system.[53-55] Therefore,here we introduced some work involving quantification of the sequencefunction relationship in sRNA-mediated regulation to discern the primary factors.

Hao et al.constructed a series of mutants of RyhB and sodB,especially the complementary mutants in the core interaction region,and suggested that fold-repression is exponentially correlated with the duplex energy $\Delta E$ in the case of no interruption in the core interaction region. They also found the energy related the secondary structure of the Hfq-binding region to be a good predictor for the efficacy of sRNA.[56] Further study suggested that the local secondary structure of sRNA may weaken the efficiency of sRNA owing to its unavailability in the kinetic process of base-pairing.According to the experimental results, an energetic term, $\Delta E _ { \mathrm { o p e n } }$ ，was introduced to characterize the energy of opening of the local structure.We hypothesized that the competition between $\Delta E _ { \mathrm { o p e n } }$ and the base-pairing energy of the core interaction region determined the parameters $k _ { \mathrm { o n } }$ and $k _ { \mathrm { o f f } }$ in the first step of the base-pairing process. Currently, the work is under preparation for submission.

Many studies have emphasized the importance of the successive base-pairing of the core interaction region,but Peterman et al. found that the loosened stem-loop structure harboring the core interaction region tolerates mismatch in the core interaction region to maintain the function of sRNA.[52l Peterman et al.signified the binding energy of the core interaction and the stability of the first and third stem-loop structures of RyhB.A two-state binding model was built to fit the experimental data,which assumed that the relative probability of an unbound state to the bound state is determined by the energy difference $\Delta E$ between the bound and unbound states.

$$
P _ { \mathrm { u n b o u n d } } = \frac { 1 } { 1 + \mathrm { e } ^ { - \beta \Delta E } } , .
$$

In the heuristic model, the energy term can be written as

$$
\begin{array} { r l } & { S _ { \mathrm { h e u r } } = \beta _ { 1 } ( \Delta G _ { \mathrm { s e e d } } ) + \log ( 1 + \exp ( \beta _ { 2 } ( \Delta G _ { \mathrm { S L 1 } } - \alpha _ { 2 } ) ) ) } \\ & { \qquad + \log ( 1 + \exp ( \beta _ { 3 } ( \Delta G _ { \mathrm { S L 3 } } - \alpha _ { 3 } ) ) ) + T . } \end{array}
$$

The first term depicts the binding energy of the core interaction region,and the second and third depict the stability of the stem-loop structures. The addictive parameters are combined into Γ.[32]

# 6.Conclusion

sRNA-mediated and protein-mediated regulations are important for bacteria to adapt to the environment. The two regulatoryapproacheshave different features,and each of themhas advantages and disadvantages,for example sRNA can rapidly respond to large changes in the input signal and shut down downstream expression,while protein-mediated regulation is better at transmitting small input signals for quantitative adjustment. Itis known that, sRNA functions in diverse modes of activating or repressing the translation of mRNA,but there has been less theoretical study on active regulation.Here we focused on the models of sRNA-mediated gene silencing.

Two types of sRNA-mediated gene silencing have been demonstrated by mass equations: stoichiometric regulation, in which sRNA undergoes codegradation with mRNA,and catalytic regulation,in which partial sRNA codegradation of mRNA is recycled as free state sRNA.The catalytic model (CSMGS） inherits the linear-threshold property of the stoichiometric model, but presents stronger repression of the target mRNA,not only in inhibiting the mRNA expression but also in restricting its noise strength.Although both the models we introduced concern the scenarios of degradation of mRNA caused by sRNA，Equation (3）can also be used to depict another kind of sRNA-mediated gene silencing where it represses the translation without degradation of mRNA,which also exhibits the linear-threshold property.[24]

When multiple mRNAs are regulated by a single sRNA, they may affect the translation of each other through sRNA competition. The crosstalk of mRNAs exhibits hierarchy property,which means the sRNA shows regulation prioritization among multiple mRNAs. This property has been observed in different experiments and models.[24.57] The theoretical model proposed that only strongly binding mRNA can efficiently release the repression of the weak binding mRNA regulated by the same sRNA,but the reverse is invalid.Therefore，the strong binding mRNA can be considered as a switch for the weakly binding mRNA in both stoichiometric and catalytic modes.

In the context of a single target, theoretical models demonstrated that the binding rate $k$ of sRNA-mRNA interaction has no influence on the threshold value,but just determines the stiffness of the transition from repression to release.[20,24] However, when multiple targets are expressed simultaneously, the relative binding rate contributes to the hierarchic crosstalk of mRNAs. In the last section of the paper,we have introduced some studies on the factors related to the efficacy of sRNA,most of which were believed to determine the binding rate of the kinetic process.Recently, Fei et al.applied single-molecular fluorescence in situ hybridization and single-molecular localization-based super-resolution microscopy to measure the numbers of sRNA,mRNA,and sRNA-mRNA complex,and then fitted them in the kinetic model to obtain kinetic parameters,which is the first time that the kinetic parameters in sRNA-mediated regulation have been measured in vivo. The results suggested that the base-pairing of SgrS sRNA with ptsG mRNA is a reversible process with a large dissociation constant.[58] This work inspired us to combine the measured kinetic parameters and secondary structures of sRNA to further study the kinetic process of base-pairing and the internal correlation,which will promote the development of the theoretical model.

# References

[1]MasseE,Vanderpool CKand Gottesman S20O5J.Bacteriol.187 6962 [2]OpdykeJA,KangJG and Storz G2004 J.Bacteriol.186 6698 [3]Bejerano-Sagie Mand Xavier KB 20O7 Curr: Opin. Microbiol.10 189 [4]VogelJandPapenfortK2006 Curr.Opin.Microbiol.9605 [5]Brantl S 2009 Future Microbiol. 4 85 [6]StorzG,VogelJand WassarmanKM2011 Mol.Cell 43 880 [7]De Lay N, Schu DJand Gottesman S 2013 J.Biol. Chem.288 7996 [8]Geissmann TA and TouatiD2004 EMBOJ.23396 [9]Henderson CA,VincentHA,Casamento A,Stone CM,Phillips JO, CaryPD,SobottF,GowersDM,TaylorJE and CallaghanAJ2013 RNA191089   
10]OtakaH,IshikawaH,Morita Tand Aiba H2O11 Proc.Natl.Acad.Sci. USA 108 13059   
11]Sauer E, Schmidt S and Weichenrieder O 2012 Proc.Natl.Acad. Sci. USA 109 9396   
[12] Aiba H2007 Curr: Opin. Microbiol.10 134   
[13]Desnoyers G and Masse E 2012 Genes Dev.26 726   
[14]PrevostK,Salvail H,Desnoyers G,Jacques JF,PhaneufE and Masse E 2007Mol. Microbiol. 641260   
[15] Soper T,MandinP,Majdalani N,Gottesman S and Woodson SA 2010 Proc. Natl. Acad. Sci. USA 107 9602   
[16] Guantes R, Cayrol B,Busi F,et al.2012 Mol.BioSyst.8(6)1707   
[17]Lalaouna D,Simoneau-Roy M,Lafontaine D and Masse E 2O13 BBAGene Regul. Mech. 1829 742   
[18]Overgaard M,Johansen J,Moller-Jensen Jand Valentin-HansenP2009 Mol.Microbiol. 73 790   
[19]Figueroa-Bossi N,Valentini M,MalleretL and Bossi L 2OO9 Genes Dev. 232004   
[20]Hao Y,XuL and ShiH2011J.Mol.Biol.406195   
[21]Beisel CL and Storz G 2011 Mol. Cell 41 286   
[22]Gogol EB,RhodiusVA,PapenfortK,Vogel Jand Gross CA 2011 Proc. Natl. Acad. Sci. USA 108 12875   
[23]Plumbridge J,BossiL,Oberto J,Wade JTand Figueroa-BossiN 2014 Mol. Microbiol. 92 648   
[24]Levine E,Zhang Z,Kuhlman Tand Hwa T20O7PLoS.Biol.5 e229   
[25]Mehta P,Goyal S and Wingreen N S 20O8 Mol. Syst. Biol. 4 221   
[26] Thattai M and Van Oudenaarden A 2004 Genetics 167 523   
[27]Elowitz MB,Levine AJ, Siggia ED and SwainP S 2002 Science 297 1183   
[28] Swain P S,Elowitz MB and Siggia ED 2002 Proc.Natl.Acad. Sci. USA 99 12795   
[29] Paulsson J2004 Nature 427 415   
[30] Paulsson J2005 Phys.Life Rev.2157   
[31]GoldingI,PaulssonJ,Zawilski S Mand Cox EC 2005 Cell 1231025   
[32]Elf Jand Ehrenberg M 2003 Genome Res.13 2475   
[33]DetwilerPB,Ramanathan S,Sengupta A and Shraiman BI2OOO Biophys. J.79 2801   
[34] Shimoni Y,Friedlander G,Hetzroni G,Niv G,Altuvia S,Biham O and Margalit H 2007 Mol. Syst. Biol. 3138   
[35]Ali Azam T,Iwata A,Nishimura A,Ueda S and Ishihama A1999 $J .$ Bacteriol. 181 6361   
[36]VogelJ2009Mol.Microbiol. 73737   
[37]Elowitz MB,Levine AJ, Siggia ED,et al.2002 Science 2971183   
[38]ThattaiM and Van Oudenaarden A.20O1 Proc.Natl.Acad.Sci.USA 98 8614   
[39] Swain P S 2004 J. Mol.Biol. 344 965   
[40]PedrazaJM,Paulsson J.2O08 Science 319 339   
[41] SoL,Ghosh A,Zong C,et al.2011 Nat. Genet. 43 554   
[42] van Kampen NG 1981 Stochastic Processes in Physics and Chemistry (Amsterdam:North-Holland) p.219   
[43] Jia Y,Liu W,Li A, et al. 2009 Biophys. Chem. 143 60   
[44] LiR,Xu L and Shi H 2015 J. Theor Biol. 365 377   
[45] Gillespie D T1977 J.Phys. Chem. 81 2340   
[46]Klironomos FD and Berg J2013 Biophys.J.104 951   
[47]Bosia C,Pagnani A and Zecchina R 2013 PLoS One 8 e66609   
[48]Levine E,Huang M,Huang Y,et al. 2Oo8 URL matisse.ucsd.edu/ hwa/pub/sRNA-noise.pdf Preprint   
[49] Gottesman S 2004 Ann. Rev. Microbiol. 58 303   
[50]JostD,Nowojewski A 2013 Biophys.J. 104 1773   
[51]NoorbakhshJ,Lang AH and MehtaP 2013PloS One 8 e72676   
[52]Peterman N,Lavi-Itzkovitz A and Levine E 2O14 Nucleic Acids Res. 42 12177   
[53]Rodrigo G,Landrain TE and Jaramillo A2012 Proc.Natl.Acad. Sci. USA 10915271   
[54]Busch A,Richter A S and BackofenR 2008 Bioinformatics 24 2849   
[55]RichterAandBackofenR2012RNABiol.9 954   
[56]Hao Y, Zhang ZJ,Erickson D W,et al.2O11 Proc.Natl.Acad. Sci. USA 108 12473   
[57]RiceJB and Vanderpool CK 2011 Nucleic Acids Res.39 3806   
[58]Fei J,Singh D,ZhangQ,Park S,Balasubramanian D,Golding I,Vanderpool C K and Ha T 2015 Science 3471371